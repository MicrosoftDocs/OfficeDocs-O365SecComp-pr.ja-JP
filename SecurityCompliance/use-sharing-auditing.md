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
ms.collection: M365-security-compliance
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: '共有は、SharePoint Online と OneDrive for business の主要なアクティビティです。 管理者は、Office 365 監査ログで共有監査を使用して、組織外のユーザーと共有しているリソースを識別できるようになりました。 '
ms.openlocfilehash: 48fc1a67f501c807e76ba2333170df83a1248428
ms.sourcegitcommit: 60c701e9808d505cf96990d0643be10b8fbc0180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "36447364"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a>共有を監査して外部ユーザーと共有されているリソースを見つける

共有は、SharePoint Online と OneDrive for business の主要なアクティビティであり、Office 365 組織で広く使用されています。 管理者は、Office 365 監査ログで共有監査を使用して、組織での共有の使用方法を決定できます。 
  
## <a name="the-sharepoint-sharing-schema"></a>SharePoint 共有スキーマ

共有イベント (共有ポリシーと共有リンクに関連するイベントは含まれません) は、1人のユーザーが別のユーザーに影響を与えるアクションを実行しているという主な方法で、ファイルとフォルダーに関連するイベントとは異なります。 たとえば、リソースユーザー A がファイルへのアクセス権をユーザー B に付与したとします。 この例では、ユーザー A は、動作している*ユーザー*で、ユーザー B は*対象ユーザー*です。 SharePoint ファイルスキーマでは、動作しているユーザーの操作だけがファイル自体に影響します。 ユーザーがファイルを開くと、 **Fileaccessed**イベントに必要な情報は、動作しているユーザーのみになります。 この違いに対処するために、共有イベントに関する詳細情報を収集する、 *SharePoint 共有スキーマ*と呼ばれる別のスキーマがあります。 これにより、管理者がリソースを共有しているユーザーや、リソースが共有されていたユーザーを表示できるようになります。 
  
共有スキーマは、イベントの共有に関連する監査レコードに2つの追加フィールドを提供します。 
  
- **TargetUserOrGroupType:** 対象のユーザーまたはグループが、Member、Guest、SharePointGroup、Microsoft.rtc.management.writableconfig.settings.centralizedlogging.securitygroup、または Partner であるかどうかを識別します。

- **Targetuserorgroupname:** リソースが共有されていたターゲットユーザーまたはグループの UPN または名前を格納します (前の例では User B)。 

これら2つのフィールドは、ユーザー、操作、日付などの Office 365 監査ログスキーマの他のプロパティに加えて、*どの*ユーザーがどのリソースを*どのよう*な** *とき*に共有したかについての完全なストーリーを伝えることができます。 
  
共有ストーリーにとって重要なスキーマプロパティは他にもあります。 監査ログの検索結果をエクスポートすると、エクスポートされた CSV ファイルの**Auditdata**列に、共有イベントに関する情報が保存されます。 たとえば、ユーザーが別のユーザーとサイトを共有する場合は、ターゲットユーザーを SharePoint グループに追加することによって実現します。 **Auditdata**列は、管理者向けにコンテキストを提供するために、この情報を取り込みます。 **Auditdata**列の情報を解析する手順については、[手順 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log)を参照してください。

## <a name="sharepoint-sharing-events"></a>SharePoint 共有イベント

共有は、ユーザー (*動作*しているユーザー) が別のユーザー (*ターゲット*ユーザー) とリソースを共有しようとしたときに定義されます。 外部ユーザーとのリソースの共有に関連する監査レコード (組織外のユーザーが組織の Azure Active Directory にゲストアカウントを持っていない場合) は、Office 365 に記録されている次のイベントによって識別されます。監査ログ:

- **SharingInvitationCreated:** 組織内のユーザーが外部ユーザーとリソース (通常はサイト) を共有しようとしました。 この結果、外部共有への招待がターゲットユーザーに送信されます。 この時点では、リソースへのアクセスは許可されません。

- **SharingInvitationAccepted:** 外部ユーザーが、動作しているユーザーによって送信された共有の招待を承諾し、リソースにアクセスできるようになりました。

- **AnonymousLinkCreated:** 匿名リンク ([すべてのユーザー] リンクとも呼ばれます) は、リソースに対して作成されます。 匿名リンクを作成してコピーすることができるので、匿名リンクが設定されているドキュメントは、ターゲットユーザーと共有していることを前提としては十分です。

- **AnonymousLinkUsed:** その名前が示すように、このイベントは、匿名リンクを使用してリソースにアクセスしたときに記録されます。 

- **Securelinkcreated:** ユーザーが、特定のユーザーとリソースを共有するための "特定のユーザーリンク" を作成しました。 このターゲットユーザーには、組織の外部にいる人がいる可能性があります。 リソースを共有しているユーザーは、 **Addedtosecurelink**イベントの監査レコードで識別されます。 これら2つのイベントのタイムスタンプはほぼ同じです。

- **Addedtosecurelink:** ユーザーが特定の人物リンクに追加されました。 このイベントの**Targetuserorgroupname**フィールドを使用して、対応する特定の people リンクに追加されたユーザーを識別します。 このターゲットユーザーには、組織の外部にいる人がいる可能性があります。

## <a name="sharing-auditing-work-flow"></a>共有監査ワークフロー
  
ユーザー (動作しているユーザー) が別のユーザー (ターゲットユーザー) とリソースを共有しようとしている場合、SharePoint (または OneDrive for Business) は最初に、対象ユーザーの電子メールアドレスが組織のディレクトリ内のユーザーアカウントに関連付けられているかどうかを確認します。 ターゲットユーザーがディレクトリ内にあり、対応するゲストユーザーアカウントを持っている場合、SharePoint は次のことを行います。
  
-  ターゲットユーザーを適切な SharePoint グループに追加して、リソースにアクセスするためのターゲットユーザーのアクセス許可を即時に割り当て、 **Addedtogroup**イベントをログに記録します。 
    
- ターゲットユーザーの電子メールアドレスに共有通知を送信します。
    
- **Sharingset**イベントをログに記録します。 このイベントには、監査ログ検索ツールの [アクティビティの選択] の [**共有とアクセスの要求のアクティビティ**] の [共有ファイル、フォルダー、またはサイト] のフレンドリ名が表示されます。 [手順 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file)のスクリーンショットを参照してください。 
    
ターゲットユーザーのユーザーアカウントがディレクトリにない場合、SharePoint は次の処理を行います。 
    
   - リソースがどのように共有されているかに基づいて、次のいずれかのイベントを記録します。
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated**(このイベントは、共有リソースがサイトである場合にのみ記録されます)
    
   - ターゲットユーザーが (招待のリンクをクリックすることによって) 送信された共有の招待を承諾すると、SharePoint は**SharingInvitationAccepted**イベントをログに記録し、リソースにアクセスするためのアクセス許可をターゲットユーザーに割り当てます。 ターゲットユーザーが匿名リンクを送信している場合、ターゲットユーザーがリンクを使用してリソースにアクセスした後、 **AnonymousLinkUsed**イベントがログに記録されます。 セキュリティで保護され**** たリンクの場合、外部ユーザーがリンクを使用してリソースにアクセスするときに、fileaccessed イベントが記録されます。

対象ユーザーに関する追加情報もログに記録されます。たとえば、招待されたユーザーの id、招待を承諾したユーザーの id などが記録されます。 場合によっては、これらのユーザー (またはメールアドレス) が異なる場合があります。 

## <a name="how-to-identify-resources-shared-with-external-users"></a>外部ユーザーと共有されるリソースを特定する方法

管理者にとって一般的な要件は、組織外のユーザーと共有されているすべてのリソースの一覧を作成することです。 Office 365 で共有監査を使用すると、管理者はこの一覧を生成できます。 ここでは、使用方法について説明します。
  
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
    
    [エクスポート] オプションを選択すると、ウィンドウの下部にメッセージが表示され、CSV ファイルを開いたり保存したりするように求められます。
    
8. [名前を付け**て**保存] をクリックし、CSV ファイルをローカルコンピューター上のフォルダーに保存します。 **** \> 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>手順 2: PowerQuery Editor を使用して、エクスポートされた監査ログを書式設定する

次の手順では、Excel の Power Query エディターで JSON 変換機能を使用して、 **Auditdata**列 (複数のプロパティを持つ JSON オブジェクトから構成される) の各プロパティをそれぞれの列に分割します。 これにより、共有に関連するレコードを表示するための列をフィルター処理できます。

詳細な手順については、「[エクスポート、構成、および監査ログレコードの表示](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)」の「手順 2: エクスポートされた監査ログを Power Query エディターを使用して書式設定する」を参照してください。

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>手順 3: 外部ユーザーと共有しているリソースの CSV ファイルをフィルター処理する

次の手順では、 [SharePoint 共有イベント](#sharepoint-sharing-events)セクションに記載されている、さまざまな共有関連イベントに対して CSV をフィルター処理します。 または、 **TargetUserOrGroupType**列をフィルター処理して、このプロパティの値が**Guest**になっているすべてのレコードを表示することもできます。 

前の手順の手順に従って、PowerQuery エディターを使用して CSV ファイルを準備した後、次の操作を行います。
    
1. 手順2で作成した Excel ファイルを開きます。 

2. [**ホーム**] タブで、[**並べ替え & フィルター**] をクリックし、[**フィルター**] をクリックします。
    
3. [**操作**] 列の [**並べ替え & フィルター** ] ボックスの一覧で、すべての選択をオフにし、次に共有関連のイベントを1つ以上選択して、[ **Ok]** をクリックします。
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel には、選択したイベントの行が表示されます。
    
4. **TargetUserOrGroupType**という名前の列に移動し、それを選択します。 
    
5. [**並べ替え & フィルター** ] ドロップダウンリストで、すべての選択をオフにし、[ **TargetUserOrGroupType: Guest**] を選択して、[ **Ok**] をクリックします。
    
    ここでは、外部ユーザーは**TargetUserOrGroupType: GUEST**という値で識別されるため、共有イベントの行と、対象ユーザーが組織外にある場所が表示されます。 
  
> [!TIP]
> 表示されている監査レコードについては、 **ObjectId**列に、ターゲットユーザーと共有されているリソースが示されます。例`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`を示します。
