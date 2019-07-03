---
title: 共有を監査して外部ユーザーと共有されているリソースを見つける
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: '共有は、SharePoint Online と OneDrive for business の主要なアクティビティです。 管理者は、Office 365 監査ログで共有監査を使用して、組織での共有の使用状況を確認できるようになりました。 '
ms.openlocfilehash: e2865d35e988d8c0e42a6c51f78507db8b170d4c
ms.sourcegitcommit: b262d40f6daf06be26e7586f37b736e09f8a4511
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35435243"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a>共有を監査して外部ユーザーと共有されているリソースを見つける

共有は、SharePoint Online と OneDrive for business の主要なアクティビティであり、Office 365 組織で広く使用されています。 管理者は、Office 365 監査ログで共有監査を使用して、組織での共有の使用状況を確認できるようになりました。 
  
## <a name="the-sharepoint-sharing-schema"></a>SharePoint 共有スキーマ

共有イベント (共有ポリシーと共有リンクイベントを除く) は、1つのユーザーが別のユーザーに対して何らかの影響を与えるアクションを実行しているという主な方法で、ファイルとフォルダーに関連するイベントとは異なります。 たとえば、User A はユーザー B にファイルへのアクセス権を与えます。 この例では、ユーザー A は、動作している*ユーザー*で、ユーザー B は*対象ユーザー*です。 SharePoint ファイルスキーマでは、動作しているユーザーの操作だけがファイル自体に影響します。 ユーザーがファイルを開くと、 **Fileaccessed**イベントに必要な情報は、動作しているユーザーのみになります。 この違いに対処するために、共有イベントに関する詳細情報を収集する、 *SharePoint 共有スキーマ*と呼ばれる別のスキーマがあります。 これにより、管理者はリソースを共有しているユーザーとリソースを共有していたユーザーについて、より洞察を得ることができます。 
  
共有スキーマは、イベントの共有に関連する2つの追加フィールドを監査ログに提供します。 
  
- **Targetuserorgroupname** –リソースが共有されていた対象ユーザーまたはグループの UPN または名前を格納します (前の例では、ユーザー B)。 
    
- **TargetUserOrGroupType** –対象のユーザーまたはグループが、メンバー、ゲスト、グループ、またはパートナーであるかどうかを識別します。 
    
これら2つのフィールドは、ユーザー、操作、日付などの Office 365 監査ログスキーマの他のプロパティに加えて、*どの*ユーザーがどのリソースを*どのよう*な** *とき*に共有したかについての完全なストーリーを伝えることができます。 
  
共有ストーリーにとって重要なスキーマプロパティは他にもあります。 **EventData**プロパティは、共有イベントに関する追加情報を格納します。 たとえば、ユーザーが別のユーザーとサイトを共有する場合は、ターゲットユーザーを SharePoint グループに追加することによって実現します。 **EventData**プロパティは、管理者にコンテキストを提供するために、この追加情報をキャプチャします。 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a>SharePoint 共有モデルと共有イベント

共有は、 **Sharingset**、 **SharingInvitationCreated**、および**SharingInvitaitonAccepted**の3つの個別のイベントによって定義されます。 Office 365 監査ログに共有イベントを記録する方法については、次のワークフローを参照してください。 
  
![共有の監査のしくみを示すフローチャート](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
ユーザー (動作しているユーザー) が別のユーザー (ターゲットユーザー) とリソースを共有しようとしている場合、SharePoint (または OneDrive for Business) は最初に、対象ユーザーの電子メールアドレスが組織のディレクトリ内のユーザーアカウントに関連付けられているかどうかを確認します。 ターゲットユーザーが組織のディレクトリにある場合、SharePoint は次の処理を行います。
  
-  リソースにアクセスするためのターゲットユーザーのアクセス許可を即時に割り当てます。 
    
- ターゲットユーザーの電子メールアドレスに共有通知を送信します。
    
- **Sharingset**イベントをログに記録します。 
    
 ターゲットユーザーのユーザーアカウントが組織のディレクトリにない場合、SharePoint は次の処理を行います。 
  
- 共有への招待を作成し、対象ユーザーの電子メールアドレスに送信します。
    
- **SharingInvitationCreated**イベントをログに記録します。 
    
    > [!NOTE]
    > **SharingInvitationCreated**イベントは、ターゲットユーザーが共有されているリソースにアクセスできない場合、常に外部またはゲストの共有に関連付けられます。 
  
ターゲットユーザーが (招待のリンクをクリックすることによって) 送信された共有の招待を承諾すると、SharePoint は**SharingInvitationAccepted**イベントをログに記録し、リソースにアクセスするためのアクセス許可をターゲットユーザーに割り当てます。 対象ユーザーに関する追加情報も記録されます。たとえば、招待状が送信されたユーザーの id や、招待を実際に受諾したユーザーなどが記録されます。 場合によっては、これらのユーザー (またはメールアドレス) が異なる場合があります。 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a>外部ユーザーと共有されるリソースを特定する方法

管理者にとって一般的な要件は、組織外のユーザーと共有されているすべてのリソースの一覧を作成することです。 Office 365 で共有監査を使用すると、管理者がこのリストを生成できるようになります。 ここでは、使用方法について説明します。
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>手順 1: 共有イベントを検索し、結果を CSV ファイルにエクスポートする

最初の手順として、Office 365 監査ログで共有イベントを検索します。 監査ログの検索に関する詳細 (必要なアクセス許可を含む) については、「[セキュリティ & のコンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。
  
1. [https://protection.office.com](https://protection.office.com) に移動します。
    
2. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
3. セキュリティ & コンプライアンスセンターの左側のウィンドウで、[**検索**  > **監査ログの検索**] をクリックします。
    
    [**監査ログの検索**] ページが表示されます。 
    
4. [**アクティビティ**] の下の [**共有とアクセス要求アクティビティ**] をクリックして、共有関連イベントを検索します。 
    
    ![[アクティビティ] の下で、[共有とアクセスの要求のアクティビティ] を選択します。](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  日付と時刻の範囲を選択して、その期間内に発生した共有イベントを検索します。 
    
6. [**検索**] をクリックして検索を実行します。 
    
7. 検索の実行が完了し、結果が表示されたら、[**結果** \>のエクスポート] をクリックして**すべての結果をダウンロード**します。
    
    [エクスポート] オプションを選択すると、CSV ファイルを開いたり保存したりするように求めるメッセージがウィンドウの下部に表示されます。
    
8. [名前を付け**て**保存] をクリックし、CSV ファイルをローカルコンピューター上のフォルダーに保存します。 **** \> 

### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a>手順 2: 外部ユーザーと共有しているリソースの CSV ファイルをフィルター処理する

次の手順では、 **Sharingset**イベントと**SharingInvitationCreated**イベントに対して CSV をフィルター処理し、 **TargetUserOrGroupType**プロパティが**Guest**であるイベントを表示します。 これを行うには、Excel の Power Query Editor ツールを使用します。 詳細な手順については、「 [Export, configure, and view audit log records](export-view-audit-log-records.md)」を参照してください。 

前のトピックの手順に従って CSV ファイルを準備した後、次の操作を行います。
    
1. Power Query Editor で準備した CSV ファイルを開きます。 

2. [**ホーム**] タブで、[**並べ替え & フィルター**] をクリックし、[**フィルター**] をクリックします。
    
3. [**操作**] 列の [ **& フィルターの並べ替え**] ドロップダウンリストで、すべての選択を解除し、[ **Sharingset** ] と [ **SharingInvitationCreated**] を選択して、[ **OK**] をクリックします。
    
    **Sharingset**および**SharingInvitationCreated**イベントの行が Excel に表示されます。 
    
4. **TargetUserOrGroupType**という名前の列に移動し、それを選択します。 
    
5. [**並べ替え & フィルター** ] ドロップダウンリストで、すべての選択をオフにし、[ **TargetUserOrGroupType: Guest**] を選択して、[ **OK**] をクリックします。
    
    ここでは、外部ユーザーが**TargetUserOrGroupType: Guest**という値で識別されるため、 **SharingInvitationCreated**および**SHARINGSET**イベントの行と、ターゲットユーザーが組織外にある場所に表示されます。 
    
次の表に、指定された日付範囲内のゲストユーザーとリソースを共有している、組織内のすべてのユーザーを示します。
  
![Office での共有イベント365監査ログ](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
**ObjectId**プロパティは、前の表には含まれていませんが、ターゲットユーザーと共有されたリソースを識別します。例`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`を示します。
  
> [!TIP]
> ゲストユーザーが実際にリソースにアクセスするためのアクセス許可が割り当てられているかどうかを確認するには (リソースと共有しているリソースだけでなく)、手順2、3、4を繰り返し、 **SharingInvitationAccepted**と**sharingset**でフィルター処理します。手順5のイベント 
