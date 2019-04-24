---
title: EOP でメール ユーザーを管理する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: メール ユーザーの定義は、Exchange Online Protection (EOP) サービスを管理する上で重要な部分です。
ms.openlocfilehash: 2e266d4dd31c3bd614c1b4f8afa17ca747890385
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256455"
---
# <a name="manage-mail-users-in-eop"></a>EOP でメール ユーザーを管理する

メール ユーザーの定義は、Exchange Online Protection (EOP) サービスを管理する上で重要な部分です。EOP でユーザーを管理するには、いくつかの方法があります。
  
- ディレクトリ同期を使用してメールユーザーを管理する: 社内の active directory 環境に既存のユーザーアカウントがある場合は、それらのアカウントを Azure active directory (AD) と同期することができます。これにより、アカウントのコピーがクラウドに保存されます。 既存のユーザーアカウントを Azure Active Directory と同期する場合は、Exchange 管理センター (EAC) の [**受信者**] ウィンドウで、それらのユーザーを表示できます。 ディレクトリ同期の使用をお勧めします。 
    
- EAC を使用してメール ユーザーを管理する: EAC で直接メール ユーザーを追加して管理します。 これは、メール ユーザーを追加する最も簡単な方法で、一度に 1 ユーザーを追加する場合に役立ちます。
    
- リモートの Windows PowerShell を使用してメール ユーザーを管理するには: リモートの Windows PowerShell を実行してメール ユーザーを追加し、管理します。 このメソッドは、複数のレコードの追加およびスクリプトの作成に役立ちます。
    
> [!NOTE]
> Microsoft 365 管理センターでユーザーを追加することはできますが、これらのユーザーをメール受信者として使用することはできません。 
  
## <a name="before-you-begin"></a>開始する前に

- このトピックの手順には、特定のアクセス許可が必要です。アクセス許可情報については、各手順を参照してください。
    
- このトピックの手順で使用可能なキーボード ショートカットについては、「**Exchange 管理センターのキーボード ショートカット**」を参照してください。
    
> [!TIP]
> 問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a>ディレクトリ同期を使用してメール ユーザーを管理する

このセクションでは、ディレクトリ同期を使用して電子メール ユーザーを管理する方法について説明します。
  
> [!IMPORTANT]
> ディレクトリ同期を使用して受信者を管理している場合でも、Microsoft 365 管理センターでユーザーを追加および管理することはできますが、オンプレミスの Active directory と同期されることはありません。 これは、ディレクトリ同期では社内 Active Directory からクラウドへの受信者の同期だけが実行されるためです。 
  
> [!TIP]
>  次の機能を使用する場合は、ディレクトリ同期を使用することをお勧めします。 > **Outlook の信頼できる差出人と受信拒否リスト**-サービスに同期すると、これらのリストはサービスのスパムフィルタリングよりも優先されます。 これにより、ユーザーは独自の差出人セーフ リストとブロックする差出人リストをユーザー単位またはドメイン単位で管理できます。 > **ディレクトリベースのエッジブロック (dbeb)** -dbeb の詳細については、「 [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)」を参照してください。 > **エンドユーザーのスパム検疫**-エンドユーザーのスパム検疫にアクセスするには、エンドユーザーが有効な Office 365 ユーザー ID とパスワードを持っている必要があります。 社内のメールボックスを保護している EOP のお客様は、有効な電子メール ユーザーである必要があります。 > **メールフロールール**-ディレクトリ同期を使用すると、既存の Active directory ユーザーとグループがクラウドに自動的にアップロードされ、特定のユーザーを対象とするメールフロールール (トランスポートルールとも呼ばれます) を作成できます。または、EAC または Exchange Online Protection の PowerShell を使用して手動で追加する必要のないグループ。 [動的配布グループ](https://go.microsoft.com/fwlink/?LinkId=507569)はディレクトリ同期を使用して同期できないことに注意してください。 
  
 **開始する前に**
  
「[ディレクトリ同期を準備する](https://go.microsoft.com/fwlink/p/?LinkId=308908)」で説明されている手順に従って、必要な許可を取得し、ディレクトリ同期を準備します。
  
### <a name="to-synchronize-user-directories"></a>ユーザー ディレクトリを同期するには

1. 「[ディレクトリ同期をアクティブにする](https://go.microsoft.com/fwlink/p/?LinkId=308909)」で説明されている手順に従って、ディレクトリ同期をアクティブにします。
    
2. 「[ディレクトリ同期用コンピューターをセットアップする](http://go.microsoft.com/fwlink/p/?LinkId=308911)」で説明されている手順に従って、ディレクトリ同期コンピュータをセットアップします。
    
3. 「[構成ウィザードを使ってディレクトリを同期する](http://go.microsoft.com/fwlink/?LinkId=308912)」で説明されている手順に従って、ディレクトリを同期します。
    
    > [!IMPORTANT]
    > Azure Active Directory 同期ツール構成ウィザードを終了すると、Active Directory フォレストに **MSOL_AD_SYNC** アカウントが作成されます。このアカウントは、社内 Active Directory 情報の読み取りと同期に使われます。ディレクトリ同期が正しく行われるように、ローカル ディレクトリ同期サーバー上の TCP 443 が開いていることを確認してください。 
  
4. 「[同期ユーザーのアクティブ化](http://go.microsoft.com/fwlink/p/?LinkId=308913)」で説明されている手順に従って、同期ユーザーをアクティブにします。
    
5. 「[ディレクトリ同期を管理する](http://go.microsoft.com/fwlink/p/?LinkId=308915)」で説明されている手順に従って、ディレクトリ同期を管理します。
    
6. EOP が正しく同期されていることを確認します。EAC で、 **[受信者]** \> **[連絡先]** に移動し、ユーザーの一覧が社内環境から同期されていることを確認します。 
    
## <a name="use-the-eac-to-manage-mail-users"></a>EAC を使用してメール ユーザーを管理する

ここでは、EAC で直接電子メール ユーザーを追加し管理する方法について説明します。
  
 **開始する前に**
  
この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「ユーザー、連絡先、および役割グループ」。
  
### <a name="to-add-a-mail-user-in-the-eac"></a>EAC でメール ユーザーを追加するには

1. 電子メール ユーザーを作成するために、EAC で **[受信者]** \> **[連絡先]** に移動し、 **[新規 +]** をクリックします。
    
2. **[メール ユーザーの新規作成]** ページで、以下を含むユーザー情報を入力します。 
    
   ****

|**メール ユーザーのプロパティ**|**説明**|
|:-----|:-----|
|**[名]**、 **[イニシャル]**、 **[姓]** <br/> |該当するボックスに、ユーザーの氏名を入力します。  <br/> |
|**表示名** <br/> |名前を入力します (最大 64 文字)。既定では、このボックスには **[名]**、 **[イニシャル]**、 **[姓]** ボックスに入力した名前が表示されます。表示名は必須です。  <br/> |
|**エイリアス** <br/> |ユーザーのエイリアスを入力します (最大 64 文字)。エイリアスは必須です。  <br/> |
|**外部電子メール アドレス** <br/> |ユーザーの外部電子メール アドレスを入力します。  <br/> |
|**ユーザー ID** <br/> |メール ユーザーがサービスにサインインするときに使用する名前を入力します。ユーザー サインイン名は、アットマーク記号 (@) の左側のユーザー名と右側のサフィックスで構成されます。一般的にサフィックスは、ユーザー アカウントが存在するドメイン名です。  <br/> |
|**新しいパスワード** <br/> |メール ユーザーがサービスにサインインするときに使用するパスワードを入力します。作成するユーザー アカウントが属するドメインでのパスワードの長さ、複雑さ、および履歴に関する要件を満たすパスワードを指定してください。  <br/> |
|**パスワードの確認入力** <br/> |確認のためのパスワードを再入力します。  <br/> |
   
3. **[保存]** をクリックして新しい電子メール ユーザーを作成します。ユーザーの一覧に、新規ユーザーが表示されます。 
    
### <a name="to-edit-or-remove-a-mail-user-in-the-eac"></a>EAC でメール ユーザーを編集または削除するには

- EAC で、[**受信者** \>の**連絡先**] に移動します。 ユーザーの一覧で、表示または変更するユーザーをクリックし、[編集] **** ![編集アイコン](../media/ITPro-EAC-EditIcon.gif)を選択して、必要に応じてユーザーの設定を更新します。 ユーザーの名前、エイリアス、または連絡先情報を変更したり、組織内のユーザーの役割に関する詳細情報を記録したりすることができます。 ユーザーを選択し、[削除] [ ****![削除] アイコン](../media/ITPro-EAC-RemoveIcon.gif)を選択して削除することもできます。 
    
## <a name="use-remote-windows-powershell-to-manage-mail-users"></a>リモートの Windows PowerShell を使用してメール ユーザーを管理するには

このセクションでは、リモートの Windows PowerShell を使用してメール ユーザーを追加し、管理する方法について説明します。
  
 **開始する前に**
  
- この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「ユーザー、連絡先、および役割グループ」。
    
- リモートの PowerShell コマンドレットを使用してメール ユーザーを作成する際、調整が発生することに注意してください。
    
- このコマンドレットはバッチ処理方法を使用しており、コマンドレットの結果が表示されるまで数分の送信遅延が生じます。
    
- Windows PowerShell を使用して Exchange Online Protection に接続する方法については、「[リモート PowerShell を使用して Exchange Online Protection に接続する](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx)」を参照してください。
    
 **リモートの PowerShell を使用してメール ユーザーを追加するには**
  
この例では、コマンドレット [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) を使用して、以下の情報を基に、EOP で Jeffrey Zeng に対してメールが有効なユーザー アカウントを作成します。 
  
- 名は Jeffrey で、姓は Zeng です。
    
- 名前は Jeffrey で、表示名は Jeffrey Zeng です。
    
- エイリアスは jeffreyz です。
    
- 外部の電子メール アドレスは jzeng@tailspintoys.com です。
    
- Office 365 のサインイン名は jeffreyz@contoso.onmicrosoft.com です。
    
- パスワードは Pa$$word1 です。
    
```Powershell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

 **これが機能することを確認するには**
  
新しいメール ユーザー Jeffrey Zeng に関する情報を表示するには、次のようにコマンドレット [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) を実行します。 
  
```Powershell
Get-User "Jeffrey Zeng"

```

 **リモートの PowerShell を使用してメール ユーザーのプロパティを編集するには**
  
コマンドレット [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) および [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) を使用して、メール ユーザーのプロパティを表示または変更します。 
  
この例では、Pilar Pinilla の外部電子メール アドレスを設定します。
  
```Powershell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

この例では、すべてのメール ユーザーの [会社] プロパティを Contoso に設定します。
  
```Powershell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}

```

 **これが機能することを確認するには**
  
前にメール ユーザー Pilar Pinella のプロパティを変更した例で、コマンドレット [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) を使用して変更を確認します。(複数のメール連絡先に対して複数のプロパティが表示されることに注意してください)。 
  
```Powershell
Get-Recipient -Identity "Pilar Pinilla" | Format-List 

```

前にすべてのメール ユーザーの ［会社］ プロパティを Contoso に設定した例で、次のコマンドを実行して変更を確認します。
  
```Powershell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> このコマンドレットはバッチ処理方法を使用しており、コマンドレットの結果が表示されるまで数分の送信遅延が生じます。 
  
 **リモートの PowerShell を使用してメール ユーザーを削除するには**
  
この例では、コマンドレット [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) を使用してユーザー Jeffrey Zeng を削除します。 
  
```Powershell
Remove-EOPMailUser -Identity Jeffrey
```

 **これが機能することを確認するには**
  
次のようにコマンドレット [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) を実行します。ユーザーが存在しないため、エラー メッセージが表示されます。 
  
```Powershell
Get-Recipient Jeffrey | fl
```


