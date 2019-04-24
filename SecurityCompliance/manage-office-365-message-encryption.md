---
title: Office 365 Message Encryption を管理する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- M365-security-compliance
description: Office 365 Message Encryption (OME) の設定を終了すると、さまざまな方法で展開の構成をカスタマイズできます。 たとえば、1回限りのパスコードを有効にするかどうかを構成したり、Outlook on the web に [保護] ボタンを表示したり、その他の設定を行ったりすることができます。 この記事のタスクでは、その方法について説明します。
ms.openlocfilehash: 7b5297ae42d3efa071408540863c6ff7dbdee407
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259815"
---
# <a name="manage-office-365-message-encryption"></a>Office 365 Message Encryption を管理する

Office 365 Message Encryption (OME) の設定を終了すると、さまざまな方法で展開の構成をカスタマイズできます。 たとえば、1回限りのパスコードを有効にするかどうかを構成したり、Outlook on the web に [**保護**] ボタンを表示したり、その他の設定を行ったりすることができます。 この記事のタスクでは、その方法について説明します。
  
||
|:-----|
|この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。 この記事は、管理者および it 担当者を対象としています。 暗号化されたメッセージの送信または受信に関する情報をお探しの場合は、「 [Office 365 message Encryption (OME)](ome.md) 」の記事の一覧を参照し、ニーズに最も適した記事を見つけてください。 |
||

## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Google、Yahoo、Microsoft アカウントの受信者が、これらのアカウントを使用して Office 365 メッセージ暗号化ポータルにサインインできるかどうかを管理する

既定では、新しい office 365 メッセージ暗号化機能をセットアップすると、組織内のユーザーは、office 365 組織の外部にいる受信者にメッセージを送信できます。 受信者が Google account、Yahoo アカウント、Microsoft アカウントなどの*ソーシャル id*を使用している場合、受信者はソーシャル id を使用して OME ポータルにサインインできます。 必要に応じて、受信者がソーシャル id を使用して OME ポータルにサインインすることを許可しないようにすることもできます。
  
### <a name="to-manage-whether-or-not-to-allow-recipients-to-use-social-ids-to-sign-in-to-the-ome-portal"></a>受信者がソーシャル id を使用して OME ポータルにサインインすることを許可するかどうかを管理するには
  
1. [リモート PowerShell を使用して Exchange Online に接続](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。

2. 次のように、指定された引数を指定して、omeconfiguration/コマンドレットを実行します。

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true | $false>
   ```

   たとえば、ソーシャル id を無効にするには、次のようにします。

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   ソーシャル id を有効にするには:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a>Office 365 メッセージ暗号化ポータルへのサインインのワンタイムパスコードの使用を管理する

既定では、OME によって暗号化されたメッセージの受信者が Outlook を使用しない場合、受信者によって使用されるアカウントに関係なく、受信者は、メッセージを読むことができる限られた時間の web 表示リンクを受信します。 これには、1回限りのパスコードが含まれます。 管理者は、1回限りのパスコードを使用して OME ポータルにサインインできるかどうかを管理できます。
  
### <a name="to-manage-whether-or-not-one-time-pass-codes-are-generated-for-ome"></a>OME に対して1回限りのパスコードが生成されるかどうかを管理するには
  
1. Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。 手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。

2. OTPEnabled パラメーターを指定して、次のコマンドレットを実行します。

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   たとえば、ワンタイムパスコードを無効にするには、次のようにします。

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   1回限りのパスコードを有効にするには:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a>Outlook on the web で保護ボタンの表示を管理する

既定では、OME をセットアップすると、web 上の Outlook の [**保護**] ボタンは有効になりません。 管理者は、このボタンをエンドユーザーに表示するかどうかを管理できます。
  
### <a name="to-manage-whether-or-not-the-protect-button-appears-in-outlook-on-the-web"></a>Outlook on the web に [保護] ボタンが表示されるかどうかを管理するには
  
1. Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。 手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。

2. SimplifiedClientAccessEnabled パラメーターを指定して、Set-irmconfiguration コマンドレットを実行します。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   たとえば、[**保護**] ボタンを無効にするには、次のようにします。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   [**保護**] ボタンを有効にするには:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>iOS メールアプリユーザーの電子メールメッセージのサービス側の復号化を有効にする

iOS メールアプリは、Office 365 メッセージの暗号化で保護されたメッセージを解読できません。 Office 365 管理者は、iOS メールアプリに配信されるメッセージに対してサービス側の復号化を適用できます。 これを実行することを選択すると、サービスは、暗号化解除されたメッセージのコピーを iOS デバイスに送信します。 このメッセージは、クライアントデバイスに復号化されて格納されます。 また、iOS メールアプリでユーザーにクライアント側の使用権限が適用されない場合でも、メッセージは使用権限に関する情報を保持します。 これは、ユーザーが元の権限を持たない場合でも、メッセージをコピーまたは印刷できることを意味します。 ただし、ユーザーが Office 365 メールサーバーを必要とする操作 (メッセージの転送など) を実行しようとした場合、そのユーザーの使用権限が設定されていない場合、サーバーはアクションを許可しません。 ただし、エンドユーザーは、iOS メールアプリの別のアカウントからメッセージを転送することにより、使用制限を転送しないようにすることができます。 メールのサービス側の復号化を設定しているかどうかに関係なく、暗号化された、権限が保護されたメールの添付ファイルは、iOS メールアプリでは表示できません。
  
iOS メールアプリユーザーに暗号化されたメッセージを送信することを許可しない場合、ユーザーには、メッセージを表示する権限がないことを示すメッセージが表示されます。 既定では、電子メールメッセージのサービス側の復号化は有効になっていません。
  
詳細と、クライアント環境の表示の詳細については、「 [iPhone または iPad で暗号化されたメッセージを表示](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)する」を参照してください。
  
### <a name="to-manage-whether-or-not-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>iOS メールアプリユーザーが Office 365 で保護されたメッセージを表示できるかどうかを管理するには、メッセージの暗号化
  
1. Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。 手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。

2. AllowRMSSupportForUnenlightenedApps パラメーターを指定して、次のコマンドレットを実行します。

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   たとえば、iOS メールアプリなどの unenlightened アプリに送信される前にメッセージを復号化するようにサービスを構成するには、次のようにします。

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   また、暗号化されていないメッセージを unenlightened アプリに送信しないようにサービスを構成するには、次のようにします。

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>web ブラウザメールクライアントの電子メール添付ファイルのサービス側復号化を有効にする

通常、Office 365 メッセージの暗号化を使用すると、添付ファイルは自動的に暗号化されます。 Office 365 管理者は、ユーザーが web ブラウザーからダウンロードした電子メール添付ファイルに対して、サービス側の復号化を適用できます。
  
これを選択すると、ファイルの復号化されたコピーがサービスによってデバイスに送信されます。 メッセージはまだ暗号化されています。 また、電子メール添付ファイルには、ブラウザーがクライアント側の使用権限をユーザーに適用しない場合でも、使用権限に関する情報が保持されます。 これは、ユーザーが元の権限を持っていない場合でも、電子メールの添付ファイルをコピーまたは印刷できることを意味します。 ただし、ユーザーが Office 365 メールサーバーを必要とするアクション (添付ファイルの転送など) を実行しようとした場合、そのユーザーが元の使用権限を持っていなかった場合、サーバーはアクションを許可しません。
  
添付ファイルのサービス側の復号化を設定しているかどうかに関係なく、暗号化された、権限が保護されたメールの添付ファイルは、iOS メールアプリでは表示できません。
  
暗号化された電子メール添付ファイルを許可しない場合、既定では、ユーザーには添付ファイルを表示する権限がないというメッセージが表示されます。
  
Office 365 で、[暗号化のみ] オプションを使用してメールおよび電子メール添付ファイルの暗号化を実装する方法の詳細については、「encryption [-only](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails) 」を参照してください。
  
### <a name="to-manage-whether-or-not-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>web ブラウザーからのダウンロード時に電子メールの添付ファイルの暗号化を解除するかどうかを管理するには
  
1. Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。 手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。

2. DecryptAttachmentFromPortal パラメーターを指定して、Set-irmconfiguration コマンドレットを実行します。

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   たとえば、ユーザーが web ブラウザーから電子メールの添付ファイルをダウンロードするときに、添付ファイルを復号化するようにサービスを構成するには、次のようにします。

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   暗号化された電子メール添付ファイルをダウンロード時に残すようにサービスを構成するには、次のようにします。

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a>電子メールメッセージと OME ポータルの外観のカスタマイズ

組織に合わせて OME をカスタマイズする方法の詳細については、「[組織のブランドを暗号化されたメッセージに追加](add-your-organization-brand-to-encrypted-messages.md)する」を参照してください。
  
## <a name="disabling-the-new-capabilities-for-ome"></a>OME の新機能を無効にする

この記事は提供されていませんが、必要な場合は、OME の新機能を無効にすることは非常に簡単です。 最初に、新しい OME 機能を使用するように作成したメールフロールールを削除する必要があります。 メールフロールールの削除の詳細については、「[メールフロールールの管理](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)」を参照してください。 次に、Exchange Online の PowerShell で次の手順を実行します。
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>OME の新機能を無効にするには
  
1. Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。 手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。

2. web 上の Outlook で [**保護**] ボタンを有効にした場合は、SimplifiedClientAccessEnabled パラメーターを指定して、Set-irmconfiguration コマンドレットを実行することによって、これを無効にします。 それ以外の場合は、この手順をスキップします。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. OME の新機能を無効にするには、AzureRMSLicensingEnabled パラメーターを false に設定して、set-irmconfiguration コマンドレットを実行します。

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
