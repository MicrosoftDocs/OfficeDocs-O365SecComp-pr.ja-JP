---
title: Office 365 Message Encryption を管理する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
description: Office 365 メッセージの暗号化 (ホーム) の設定が終了したら後、は、いくつかの方法で、展開の構成をカスタマイズできます。たとえば、1 回限りのパス コードを有効にする、web、およびその他の Outlook の保護] ボタンを表示するかどうかを設定できます。この資料内のタスクについて説明する方法です。
ms.openlocfilehash: ddc86bdf0d0ce5480587862a4ed438b6c138987f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531887"
---
# <a name="manage-office-365-message-encryption"></a>Office 365 Message Encryption を管理する

Office 365 メッセージの暗号化 (ホーム) の設定が終了したら後、は、いくつかの方法で、展開の構成をカスタマイズできます。たとえば、1 回限りのパス コードを有効にする、web、およびその他の Outlook の**保護**] ボタンを表示するかどうかを設定できます。この資料内のタスクについて説明する方法です。 
  
||
|:-----|
|この資料は、Office 365 のメッセージの暗号化についての記事の大規模な一連の一部です。この資料は、管理者および IT プロフェッショナル向けです。だけを行う場合、暗号化されたメッセージを送受信する情報は[Office 365 メッセージの暗号化 (ホーム)](ome.md)内のアーティクルの一覧を参照してくださいし、お客様のニーズに最も適した記事を検索します。 |
   
## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Google や Yahoo、Microsoft アカウントの受信者は、これらのアカウントを使用して、Office 365 のメッセージの暗号化のポータルにサインインするかどうかを管理します。
<a name="PermitSocialID"> </a>

既定では、新しい Office 365 のメッセージの暗号化機能を設定するとき、組織内のユーザーがメッセージを送信は、Office 365 の組織外の受信者にします。受信者がソーシャル ID を使用してホーム ポータルにサインインできる受信者は、Google アカウント、yahoo のアカウント、または Microsoft アカウントなどの*ソーシャル ID*を使用する場合する場合は、ホームのポータルにサインインするのには、ソーシャル Id を使用する受信者を許可しないように選択できます。 
  
 **ホーム ポータルにサインインするのには、ソーシャル Id を使用する受信者を許可するかどうかを管理するには**
  
1. [オンライン リモート PowerShell を使用して Exchange に接続](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。
    
2. 次のように SocialIdSignIn パラメーターを使用してセット OMEConfiguration コマンドレットを実行します。
    
  ```
  Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true |$false >
  ```

    たとえば、ソーシャル Id を無効にします。
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
  ```

    ソーシャル Id を有効にするには。
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
  ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a>Office 365 のメッセージの暗号化のポータルへのサインインに 1 回限りのパス コードの使用を管理します。
<a name="GenerateOTPC"> </a>

既定では、ホームで暗号化されたメッセージの受信者は、受信者によって使用されるアカウントに関係なく、Outlook を使用しない場合は、受信者はメッセージを確認できるようになる期間限定の web 表示のリンクを受け取ります。これには、1 回限りのパス コードが含まれます。管理者は、ホーム ポータルにサインインする 1 回限りのパス ・ コードを使用できるかどうかを管理することができます。
  
 **ホームの 1 回限りのパス ・ コードを生成するかどうかを管理するには**
  
1. [オンライン リモート PowerShell を使用して Exchange に接続](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。
    
2. 次のように OTPEnabled パラメーターを使用してセット OMEConfiguration コマンドレットを実行します。
    
  ```
  Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true |$false >
  ```

    たとえば、1 回限りのパス ・ コードを無効にします。
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
  ```

    1 回限りのパス コードを有効にするには。
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
  ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a>Web 上の Outlook で [保護] ボタンの表示を管理します。
<a name="DisplayProtectButton"> </a>

既定では、web 上の Outlook で [**保護**] ボタンが有効になっていないホームを設定するときです。管理者は、エンド ・ ユーザーには、このボタンを表示するかどうかを管理できます。 
  
 **管理するには、かどうか保護] ボタンが表示されます、web 上の Outlook で**
  
1. [オンライン リモート PowerShell を使用して Exchange に接続](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。
    
2. -SimplifiedClientAccessEnabled パラメーターを使用して次のようにセット IRMConfiguration コマンドレットを実行します。
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true |$false >
  ```

    たとえば、**保護**] ボタンを無効にします。 
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
  ```

    **保護**] ボタンを有効にするには。 
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
  ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>IOS のメール アプリケーションのユーザーの電子メール メッセージのサービス側の復号化を有効にします。
<a name="EnableServiceSideDecrypt"> </a>

IOS のメール アプリケーションでは、Office 365 のメッセージの暗号化で保護されているメッセージを暗号化解除できません。Office 365 管理者は、iOS のメール アプリケーションに配信されるメッセージのサービス側の復号化を適用できます。これを行うことを選択すると、サービスは、メッセージの復号化されたコピーを iOS デバイスに送信します。メッセージを格納するには、クライアント ・ デバイスでの暗号化が解除されます。メッセージは、iOS のメール アプリケーションがユーザーにクライアント側の使用権限を適用しない場合でもにも使用権限に関する情報を保持します。これは、ユーザーをコピーしたり、メッセージを印刷する場合でも、本来必要がないようにするための権限ことを意味します。ただし、ユーザーが Office 365 のメール サーバーのメッセージの転送などを必要とする操作が完了する場合、サーバーことはできません操作ユーザーが使用権限を最初に持っていなかった場合。ただし、エンド ・ ユーザーは、メール サービス側の復号化を設定するかどうかに関係なく、iOS のメール アプリケーションで別のアカウントからメッセージを転送することによって転送不可の使用制限を回避することが、すべての添付ファイルを暗号化および権利の保護されたメールiOS のメール アプリケーションでは表示できません。
  
送信するメッセージを復号化を許可しないように選択する場合は、iOS アプリのユーザーのメール、ユーザーにメッセージを表示する権限がないことを示すメッセージが表示されます。既定では、電子メール メッセージのサービス側の復号化は有効になっていません。
  
詳細については、およびクライアント エクスペリエンスを表示する場合にを参照してください、[iPhone または iPad 上の暗号化されたメッセージを表示](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf#iOSEncryptedMail)] で[、iPhone や iPad で暗号化されたメッセージを表示](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)します。
  
 **IOS のメール アプリケーションのユーザーであるかどうかを管理するために Office 365 のメッセージの暗号化によって保護されているメッセージを表示できます。**
  
1. [オンライン リモート PowerShell を使用して Exchange に接続](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。
    
2. 次のように AllowRMSSupportForUnenlightenedApps パラメーターを使用してセット ActiveSyncOrganizations コマンドレットを実行します。
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true |$false >
  ```

    たとえば、unenlightened アプリケーションに送信される前に、メッセージを復号化するサービスを構成するのには次のように iOS メール アプリケーション。
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
  ```

    たとえば、unenlightened アプリケーションに復号化されたメッセージを送信しないようにサービスを構成するとします。
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
  ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>電子メールの添付ファイルの web ブラウザーのメール クライアントのサービス側の復号化を有効にします。
<a name="EnableServiceSideDecrypt"> </a>

通常、Office 365 のメッセージの暗号化を使用すると、添付ファイルに自動的に暗号化されます。Office 365 管理者は、ユーザーが web ブラウザーからダウンロードする電子メールの添付ファイルのサービス側の復号化を適用できます。 
  
これを行うことを選択すると、サービスは、デバイスにファイルの復号化されたコピーを送信します。メッセージが暗号化されます。ブラウザーでユーザーにクライアント側の使用権限が適用されない場合でも、電子メールの添付ファイルからも使用権限に関する情報が保持されます。これは、ユーザーをコピーしたり、電子メールの添付ファイルを印刷する場合でも、本来必要がないようにするための権限ことを意味します。ただし、ユーザーが Office 365 のメール サーバーの添付ファイルの転送などを必要とする操作が完了する場合、サーバーことはできません操作ユーザーが使用権限を最初に持っていなかった場合。
  
添付ファイルの復号化をサービス側を設定するかどうかに関係なく任意の添付ファイルの暗号化し、iOS のメール アプリケーションでは、権限保護されたメールを表示できません。
  
既定では、復号化された電子メールの添付ファイルを許可しないを選択した場合、ユーザーには、添付ファイルを表示する権限がないことを示すメッセージが表示されます。\* \* \*の画像を挿入しますか?
  
Office 365 の電子メールと暗号化専用のオプションを使用して電子メールの添付ファイルの暗号化を実装する方法の詳細についてを参照してください[の電子メールの暗号化のみのオプションです](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。
  
 **管理するには、かどうか電子メールの添付ファイルが復号化、web ブラウザーからのダウンロード時に**
  
1. [オンライン リモート PowerShell を使用して Exchange に接続](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。
    
2. 次のように DecryptAttachmentFromPortal パラメーターを使用してセット IRMConfiguration コマンドレットを実行します。
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal <$true |$false >
  ```

    など、ユーザーの電子メールの添付ファイルを復号化するサービスを構成するのにはそれらをダウンロード、web ブラウザーから。
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal $true
  ```

    ダウンロード時に、暗号化された電子メールの添付ファイルをそのままにするサービスを構成するには。
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal $false
  ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a>電子メール メッセージおよびホーム ポータルの外観をカスタマイズします。
<a name="CustomizeAppearance"> </a>

組織のホームをカスタマイズする方法の詳細については、[暗号化されたメッセージに、組織のブランドを追加する](add-your-organization-brand-to-encrypted-messages.md)を参照してください。
  
## <a name="disabling-the-new-capabilities-for-ome"></a>ホームの新機能を無効にします。
<a name="CustomizeAppearance"> </a>

する必要があります、ホームが非常に簡単ですが、新機能を無効にすることが当然と思います。まず、ルールを削除、メール フローを作成したホームの新機能を使用する必要があります。メール フロー ルールを削除する方法の詳細については、[メール フロー ルールの管理](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)を参照してください。次に、これらの手順を完了 Exchange オンライン PowerShell。
  
 **ホームの新機能を無効にするには**
  
1. [オンライン リモート PowerShell を使用して Exchange に接続](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)します。
    
2. Web 上の Outlook で [保護] ボタンを有効にする場合は、次のように SimplifiedClientAccessEnabled パラメーターを使用してセット IRMConfiguration コマンドレットを実行して無効にします。
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
  ```

3. 次のように AzureRMSLicensingEnabled パラメーターを使用してセット IRMConfiguration コマンドレットを実行します。
    
  ```
  Set-IRMConfiguration -AzureRMSLicensingEnabled $false
  ```


