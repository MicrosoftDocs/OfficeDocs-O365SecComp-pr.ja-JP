---
title: EOP でメール ユーザーを管理する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: メール ユーザーの定義は、Exchange Online Protection (EOP) サービスを管理する上で重要な部分です。
ms.openlocfilehash: 48d530be17a7e75f6e179a50067b1b9526606cb0
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676717"
---
# <a name="manage-mail-users-in-eop"></a>EOP でメール ユーザーを管理する

メール ユーザーの定義は、Exchange Online Protection (EOP) サービスを管理する上で重要な部分です。EOP でユーザーを管理するには、いくつかの方法があります。
  
- ディレクトリ同期を使用してメールユーザーを管理する: 社内の Active Directory 環境に既存のユーザーアカウントがある場合は、それらのアカウントを Azure Active Directory (AD) と同期することができます。これにより、アカウントのコピーがクラウドに保存されます。 既存のユーザーアカウントを Azure Active Directory と同期する場合は、Exchange 管理センター (EAC) の [**受信者**] ウィンドウで、それらのユーザーを表示できます。 ディレクトリ同期の使用をお勧めします。 

- EAC を使用してメール ユーザーを管理する: EAC で直接メール ユーザーを追加して管理します。 これは、メール ユーザーを追加する最も簡単な方法で、一度に 1 ユーザーを追加する場合に役立ちます。

- リモートの Windows PowerShell を使用してメール ユーザーを管理するには: リモートの Windows PowerShell を実行してメール ユーザーを追加し、管理します。 このメソッドは、複数のレコードの追加およびスクリプトの作成に役立ちます。

> [!NOTE]
> Microsoft 365 管理センターでユーザーを追加することはできますが、これらのユーザーをメール受信者として使用することはできません。
  
## <a name="before-you-begin"></a>始める前に

- Exchange 管理センターを開くには、「exchange [Online Protection の exchange 管理センター](../exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。

- この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「ユーザー、連絡先、および役割グループ」。

- Exchange Online Protection の PowerShell コマンドレットを使用してメールユーザーを作成する場合、調整が発生する可能性があることに注意してください。

- このトピックの PowerShell コマンドでは、コマンドの結果が表示されるまでに数分の遅延が発生するバッチ処理方式を使用しています。

- Windows PowerShell を使って Exchange Online Protection に接続する方法については、「[Exchange Online Protection の PowerShell への接続](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx)」を参照してください。

- このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。

> [!TIP]
> 問題がある場合は、 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラムでヘルプを要求します。
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a>ディレクトリ同期を使用してメール ユーザーを管理する

このセクションでは、ディレクトリ同期を使用して電子メール ユーザーを管理する方法について説明します。
  
> [!NOTE]
> ディレクトリ同期を使用して受信者を管理している場合でも、Microsoft 365 管理センターでユーザーを追加および管理することはできますが、オンプレミスの Active Directory と同期されることはありません。 これは、ディレクトリ同期では社内 Active Directory からクラウドへの受信者の同期だけが実行されるためです。 <br/><br/> ディレクトリ同期は、次の機能を使用する場合にお勧めします。 <br/><br/>• **Outlook の差出人セーフリストと受信拒否リスト**: サービスに同期すると、これらのリストはサービスのスパムフィルタリングよりも優先されます。 これにより、ユーザーは独自の差出人セーフ リストとブロックする差出人リストをユーザー単位またはドメイン単位で管理できます。 <br/><br/>•**ディレクトリベースのエッジブロック (dbeb)**: DBEB の詳細については、「 [Use Directory based Edge Blocking To Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)」を参照してください。 <br/><br/>•**エンドユーザーのスパム検疫**: エンドユーザーのスパム検疫にアクセスするには、エンドユーザーが有効な Office 365 ユーザー ID とパスワードを持っている必要があります。 社内のメールボックスを保護している EOP のお客様は、有効な電子メール ユーザーである必要があります。 <br/><br/>•**メールフロールール**: ディレクトリ同期を使用すると、既存の Active directory ユーザーとグループがクラウドに自動的にアップロードされ、特定のユーザーを対象とするメールフロールール (トランスポートルールとも呼ばれる) を作成できます。または、EAC または Exchange Online Protection の PowerShell を使用して手動で追加する必要のないグループ。 [動的配布グループ](https://go.microsoft.com/fwlink/?LinkId=507569)はディレクトリ同期を使用して同期できないことに注意してください。
  
「[ディレクトリ同期を準備する](https://go.microsoft.com/fwlink/p/?LinkId=308908)」で説明されている手順に従って、必要な許可を取得し、ディレクトリ同期を準備します。
  
### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a>ユーザーディレクトリを Azure Active Directory Connect (AAD Connect) と同期するには

Azure Active Directory (AAD) にユーザーを同期するには、「 [active directory 同期をアクティブ](https://go.microsoft.com/fwlink/p/?LinkId=308909)化する」の説明に従って、**ディレクトリ同期をアクティブ化**する必要があります。

次に、AAD Connect を実行するためのオンプレミスのコンピューターのインストールと構成を行います (時間の前に確認する必要があるものがまだない場合)。 [Aad connect を設定](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)すると、このトピックでは、社内のアカウントを aad 接続を使用して Azure AD にセットアップし、同期する方法について説明します。

この作業を行う前に、[前提条件を満たし](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)ていることを確認し、[インストールの種類を選択](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)してください。 以前のリンクは、高速インストールに関する短い記事を対象としています。 [カスタムインストール](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)の記事や、必要に応じ[て認証をパススルー](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)することもできます。

> [!IMPORTANT]
> Azure Active Directory 同期ツール構成ウィザードを終了すると、Active Directory フォレストに **MSOL_AD_SYNC** アカウントが作成されます。このアカウントは、社内 Active Directory 情報の読み取りと同期に使われます。ディレクトリ同期が正しく行われるように、ローカル ディレクトリ同期サーバー上の TCP 443 が開いていることを確認してください。

同期を構成した後、EOP が正しく同期されていることを確認してください。 EAC で、 **[受信者]** \> **[連絡先]** に移動し、ユーザーの一覧が社内環境から同期されていることを確認します。

## <a name="use-the-eac-to-manage-mail-users"></a>EAC を使用してメール ユーザーを管理する

ここでは、EAC で直接電子メール ユーザーを追加し管理する方法について説明します。
  
### <a name="use-the-eac-to-add-a-mail-user"></a>EAC を使用してメールユーザーを追加する

1. 電子メール ユーザーを作成するために、EAC で **[受信者]** \> **[連絡先]** に移動し、 **[新規 +]** をクリックします。

2. **[メール ユーザーの新規作成]** ページで、以下を含むユーザー情報を入力します。 

   ****

   |**メール ユーザーのプロパティ**|**説明**|
   |:-----|:-----|
   |**[名]**、 **[イニシャル]**、 **[姓]**|該当するボックスに、ユーザーの氏名を入力します。|
   |**表示名**|名前を入力します (最大 64 文字)。既定では、このボックスには **[名]**、 **[イニシャル]**、 **[姓]** ボックスに入力した名前が表示されます。表示名は必須です。  |
   |**エイリアス**|ユーザーのエイリアスを入力します (最大 64 文字)。エイリアスは必須です。|
   |**外部電子メール アドレス**|ユーザーの外部電子メール アドレスを入力します。|
   |**ユーザー ID**|メール ユーザーがサービスにサインインするときに使用する名前を入力します。ユーザー サインイン名は、アットマーク記号 (@) の左側のユーザー名と右側のサフィックスで構成されます。一般的にサフィックスは、ユーザー アカウントが存在するドメイン名です。|
   |**新しいパスワード**|メール ユーザーがサービスにサインインするときに使用するパスワードを入力します。作成するユーザー アカウントが属するドメインでのパスワードの長さ、複雑さ、および履歴に関する要件を満たすパスワードを指定してください。|
   |**パスワードの確認入力**|確認のためのパスワードを再入力します。|

3. **[保存]** をクリックして新しい電子メール ユーザーを作成します。ユーザーの一覧に、新規ユーザーが表示されます。

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a>EAC を使用してメールユーザーを編集または削除する

- EAC で、[**受信者** \>の**連絡先**] に移動します。 ユーザーの一覧で、表示または変更するユーザーをクリックし、[編集] **** ![編集アイコン](../media/ITPro-EAC-EditIcon.gif)を選択して、必要に応じてユーザーの設定を更新します。 ユーザーの名前、エイリアス、または連絡先情報を変更したり、組織内のユーザーの役割に関する詳細情報を記録したりすることができます。 ユーザーを選択し、[削除] [ **** ![削除] アイコン](../media/ITPro-EAC-RemoveIcon.gif)を選択して削除することもできます。 

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a>Exchange Online Protection PowerShell を使用してメールユーザーを管理する

このセクションでは、リモートの Windows PowerShell を使用してメール ユーザーを追加し、管理する方法について説明します。
  
### <a name="use-eop-powershell-to-add-a-mail-user"></a>EOP PowerShell を使用してメールユーザーを追加する
  
この例では、コマンドレット [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) を使用して、以下の情報を基に、EOP で Jeffrey Zeng に対してメールが有効なユーザー アカウントを作成します。
  
- 名は Jeffrey で、姓は Zeng です。

- 名前は Jeffrey で、表示名は Jeffrey Zeng です。

- エイリアスは jeffreyz です。

- 外部の電子メール アドレスは jzeng@tailspintoys.com です。

- Office 365 のサインイン名は jeffreyz@contoso.onmicrosoft.com です。

- パスワードは Pa$$word1 です。

```Powershell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

これが正常に動作することを確認するには、次のコマンドを実行して、新しいメールユーザー Jeffrey Zeng に関する情報を表示します。
  
```Powershell
Get-User -Identity "Jeffrey Zeng"
```

構文およびパラメーターの詳細については、「[取得-ユーザー](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)」を参照してください。

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a>EOP PowerShell を使用してメールユーザーのプロパティを編集する
  
コマンドレット [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) および [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) を使用して、メール ユーザーのプロパティを表示または変更します。
  
この例では、Pilar Pinilla の外部電子メール アドレスを設定します。
  
```Powershell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

この例では、すべてのメール ユーザーの [会社] プロパティを Contoso に設定します。
  
```Powershell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```
  
これが正常に動作することを[](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)確認するには、次のコマンドレットを使用して変更を確認します。 (複数のメール連絡先に対して複数のプロパティが表示されることに注意してください)。
  
```Powershell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

前にすべてのメール ユーザーの ［会社］ プロパティを Contoso に設定した例で、次のコマンドを実行して変更を確認します。
  
```Powershell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> このコマンドレットはバッチ処理方法を使用しており、コマンドレットの結果が表示されるまで数分の送信遅延が生じます。
  
### <a name="use-eop-powershell-to-remove-a-mail-user"></a>EOP PowerShell を使用してメールユーザーを削除する
  
この例では、コマンドレット [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) を使用してユーザー Jeffrey Zeng を削除します。
  
```Powershell
Remove-EOPMailUser -Identity Jeffrey
```

 **これが機能することを確認するには**
  
これが正常に動作することを確認するには、 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)コマンドレットを実行して、メールユーザーが存在しないことを確認します。
  
```Powershell
Get-Recipient Jeffrey | Format-List
```
