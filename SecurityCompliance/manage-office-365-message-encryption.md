---
title: Office 365 Message Encryption を管理する
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
description: Office 365 メッセージの暗号化 (ホーム) の設定が終了したら後、は、いくつかの方法で、展開の構成をカスタマイズできます。たとえば、1 回限りのパス コードを有効にする、web、およびその他の Outlook の保護] ボタンを表示するかどうかを設定できます。この資料内のタスクについて説明する方法です。
ms.openlocfilehash: 6a9eddae2d3d166d96979d88b15845c3b7379bd9
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696231"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="54b8a-105">Office 365 Message Encryption を管理する</span><span class="sxs-lookup"><span data-stu-id="54b8a-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="54b8a-p102">Office 365 メッセージの暗号化 (ホーム) の設定が終了したら後、は、いくつかの方法で、展開の構成をカスタマイズできます。たとえば、1 回限りのパス コードを有効にする、web、およびその他の Outlook の**保護**] ボタンを表示するかどうかを設定できます。この資料内のタスクについて説明する方法です。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p102">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in a number of ways. For example, you can configure whether to enable one-time pass codes, display the **Protect** button in Outlook on the web, and more. The tasks in this article describe how.</span></span>
  
||
|:-----|
|<span data-ttu-id="54b8a-p103">この資料は、Office 365 のメッセージの暗号化についての記事の大規模な一連の一部です。この資料は、管理者および ITPros。だけを行う場合、暗号化されたメッセージを送受信する情報は[Office 365 メッセージの暗号化 (ホーム)](ome.md)内のアーティクルの一覧を参照してくださいし、お客様のニーズに最も適した記事を検索します。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="54b8a-112">Google や Yahoo、Microsoft アカウントの受信者は、これらのアカウントを使用して、Office 365 のメッセージの暗号化のポータルにサインインするかどうかを管理します。</span><span class="sxs-lookup"><span data-stu-id="54b8a-112">Managing whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="54b8a-p104">既定では、新しい Office 365 のメッセージの暗号化機能を設定するとき、組織内のユーザーがメッセージを送信は、Office 365 の組織外の受信者にします。受信者がソーシャル ID を使用してホーム ポータルにサインインできる受信者は、Google アカウント、yahoo のアカウント、または Microsoft アカウントなどの*ソーシャル ID*を使用する場合する場合は、ホームのポータルにサインインするのには、ソーシャル Id を使用する受信者を許可しないように選択できます。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p104">By default, when you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization. If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal using the social ID. If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-to-allow-recipients-to-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="54b8a-116">ホーム ポータルにサインインするのには、ソーシャル Id を使用する受信者を許可するかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="54b8a-116">To manage whether or not to allow recipients to use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="54b8a-117">[オンライン リモート PowerShell を使用して Exchange に接続](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="54b8a-117">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="54b8a-118">次のように SocialIdSignIn パラメーターを使用してセット OMEConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="54b8a-118">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true | $false>
   ```

   <span data-ttu-id="54b8a-119">たとえば、ソーシャル Id を無効にします。</span><span class="sxs-lookup"><span data-stu-id="54b8a-119">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="54b8a-120">ソーシャル Id を有効にするには。</span><span class="sxs-lookup"><span data-stu-id="54b8a-120">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="54b8a-121">Office 365 のメッセージの暗号化のポータルへのサインインに 1 回限りのパス コードの使用を管理します。</span><span class="sxs-lookup"><span data-stu-id="54b8a-121">Managing the use of one-time pass codes for signing in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="54b8a-p105">既定では、ホームで暗号化されたメッセージの受信者は、受信者によって使用されるアカウントに関係なく、Outlook を使用しない場合は、受信者はメッセージを確認できるようになる期間限定の web 表示のリンクを受け取ります。これには、1 回限りのパス コードが含まれます。管理者は、ホーム ポータルにサインインする 1 回限りのパス ・ コードを使用できるかどうかを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p105">By default, if the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message. This includes a one-time pass code. As an administrator, you can manage whether or not one-time pass codes can be used to sign-in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-one-time-pass-codes-are-generated-for-ome"></a><span data-ttu-id="54b8a-125">ホームの 1 回限りのパス ・ コードを生成するかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="54b8a-125">To manage whether or not one-time pass codes are generated for OME</span></span>
  
1. <span data-ttu-id="54b8a-p106">大域管理者アクセス許可を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://aka.ms/exopowershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="54b8a-128">OTPEnabled パラメーターを使用してセット OMEConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="54b8a-128">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="54b8a-129">たとえば、1 回限りのパス ・ コードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="54b8a-129">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="54b8a-130">1 回限りのパス コードを有効にするには。</span><span class="sxs-lookup"><span data-stu-id="54b8a-130">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a><span data-ttu-id="54b8a-131">Web 上の Outlook で [保護] ボタンの表示を管理します。</span><span class="sxs-lookup"><span data-stu-id="54b8a-131">Managing the display of the Protect button in Outlook on the web</span></span>

<span data-ttu-id="54b8a-p107">既定では、web 上の Outlook で [**保護**] ボタンが有効になっていないホームを設定するときです。管理者は、エンド ・ ユーザーには、このボタンを表示するかどうかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p107">By default, the **Protect** button in Outlook on the web is not enabled when you set up OME. As an administrator, you can manage whether or not to display this button to end users.</span></span>
  
### <a name="to-manage-whether-or-not-the-protect-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="54b8a-134">管理するには、かどうか保護] ボタンが表示されます、web 上の Outlook で</span><span class="sxs-lookup"><span data-stu-id="54b8a-134">To manage whether or not the Protect button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="54b8a-p108">大域管理者アクセス許可を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://aka.ms/exopowershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p108">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="54b8a-137">-SimplifiedClientAccessEnabled パラメーターを使用してセット IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="54b8a-137">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="54b8a-138">たとえば、**保護**] ボタンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="54b8a-138">For example, to disable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="54b8a-139">**保護**] ボタンを有効にするには。</span><span class="sxs-lookup"><span data-stu-id="54b8a-139">To enable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="54b8a-140">IOS のメール アプリケーションのユーザーの電子メール メッセージのサービス側の復号化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="54b8a-140">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="54b8a-p109">IOS のメール アプリケーションでは、Office 365 のメッセージの暗号化で保護されているメッセージを暗号化解除できません。Office 365 管理者は、iOS のメール アプリケーションに配信されるメッセージのサービス側の復号化を適用できます。これを行うことを選択すると、サービスは、メッセージの復号化されたコピーを iOS デバイスに送信します。メッセージを格納するには、クライアント ・ デバイスでの暗号化が解除されます。メッセージは、iOS のメール アプリケーションがユーザーにクライアント側の使用権限を適用しない場合でもにも使用権限に関する情報を保持します。これは、ユーザーをコピーしたり、メッセージを印刷する場合でも、本来必要がないようにするための権限ことを意味します。ただし、ユーザーが Office 365 のメール サーバーのメッセージの転送などを必要とする操作が完了する場合、サーバーことはできません操作ユーザーが使用権限を最初に持っていなかった場合。ただし、エンド ・ ユーザーは、メール サービス側の復号化を設定するかどうかに関係なく、iOS のメール アプリケーションで別のアカウントからメッセージを転送することによって転送不可の使用制限を回避することが、すべての添付ファイルを暗号化および権利の保護されたメールiOS のメール アプリケーションでは表示できません。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p109">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption. As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app. When you choose to do this, the service sends a decrypted copy of the message to the iOS device. The message is stored decrypted on the client device. The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user. This means that the user can copy or print the message even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server will not permit the action if the user did not originally have the usage right to do so. However, end-users can work around Do Not Forward usage restriction by forwarding the message from a different account in their iOS mail app. Regardless of whether you set up service-side decryption of mail, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="54b8a-p110">送信するメッセージを復号化を許可しないように選択する場合は、iOS アプリのユーザーのメール、ユーザーにメッセージを表示する権限がないことを示すメッセージが表示されます。既定では、電子メール メッセージのサービス側の復号化は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p110">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message. By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="54b8a-152">詳細については、およびクライアント エクスペリエンスを表示する場合に、[暗号化されたメッセージを iPhone または iPad のビュー](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54b8a-152">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-or-not-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="54b8a-153">IOS のメール アプリケーションのユーザーであるかどうかを管理するために Office 365 のメッセージの暗号化によって保護されているメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="54b8a-153">To manage whether or not iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="54b8a-p111">大域管理者アクセス許可を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://aka.ms/exopowershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p111">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="54b8a-156">AllowRMSSupportForUnenlightenedApps パラメーターを使用してセット ActiveSyncOrganizations コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="54b8a-156">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="54b8a-157">たとえば、unenlightened アプリケーションに送信される前に、メッセージを復号化するサービスを構成するのには次のように iOS メール アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="54b8a-157">For example, to configure the service to decrypt messages before they are sent to unenlightened apps such as the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="54b8a-158">または、unenlightened アプリケーションに復号化されたメッセージを送信しないようにサービスを構成するにします。</span><span class="sxs-lookup"><span data-stu-id="54b8a-158">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="54b8a-159">電子メールの添付ファイルの web ブラウザーのメール クライアントのサービス側の復号化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="54b8a-159">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="54b8a-p112">通常、Office 365 のメッセージの暗号化を使用すると、添付ファイルに自動的に暗号化されます。Office 365 管理者は、ユーザーが web ブラウザーからダウンロードする電子メールの添付ファイルのサービス側の復号化を適用できます。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p112">Normally, when you use Office 365 message encryption, attachments are automatically encrypted. As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="54b8a-p113">これを行うことを選択すると、サービスは、デバイスにファイルの復号化されたコピーを送信します。メッセージが暗号化されます。ブラウザーでユーザーにクライアント側の使用権限が適用されない場合でも、電子メールの添付ファイルからも使用権限に関する情報が保持されます。これは、ユーザーをコピーしたり、電子メールの添付ファイルを印刷する場合でも、本来必要がないようにするための権限ことを意味します。ただし、ユーザーが Office 365 のメール サーバーの添付ファイルの転送などを必要とする操作が完了する場合、サーバーことはできません操作ユーザーが使用権限を最初に持っていなかった場合。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p113">When you choose to do this, the service sends a decrypted copy of the file to the device. The message is still encrypted. The email attachment also retains information about usage rights even though the browser does not apply client-side usage rights to the user. This means that the user can copy or print the email attachment even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server will not permit the action if the user did not originally have the usage right to do so.</span></span>
  
<span data-ttu-id="54b8a-167">添付ファイルの復号化をサービス側を設定するかどうかに関係なく任意の添付ファイルの暗号化し、iOS のメール アプリケーションでは、権限保護されたメールを表示できません。</span><span class="sxs-lookup"><span data-stu-id="54b8a-167">Regardless of whether you set up service-side decryption of attachments, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="54b8a-168">既定では、復号化された電子メールの添付ファイルを許可しないを選択した場合、ユーザーには、添付ファイルを表示する権限がないことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="54b8a-168">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="54b8a-169">Office 365 の電子メールと暗号化専用のオプションを使用して電子メールの添付ファイルの暗号化を実装する方法の詳細についてを参照してください[の電子メールの暗号化のみのオプションです](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="54b8a-169">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-or-not-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="54b8a-170">管理するには、かどうか電子メールの添付ファイルが復号化、web ブラウザーからのダウンロード時に</span><span class="sxs-lookup"><span data-stu-id="54b8a-170">To manage whether or not email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="54b8a-p114">大域管理者アクセス許可を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://aka.ms/exopowershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p114">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="54b8a-173">DecryptAttachmentFromPortal パラメーターを使用してセット IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="54b8a-173">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="54b8a-174">など、ユーザーの電子メールの添付ファイルを復号化するサービスを構成するのにはそれらをダウンロード、web ブラウザーから。</span><span class="sxs-lookup"><span data-stu-id="54b8a-174">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="54b8a-175">ダウンロード時に、暗号化された電子メールの添付ファイルをそのままにするサービスを構成するには。</span><span class="sxs-lookup"><span data-stu-id="54b8a-175">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="54b8a-176">電子メール メッセージおよびホーム ポータルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="54b8a-176">Customizing the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="54b8a-177">組織のホームをカスタマイズする方法の詳細については、[暗号化されたメッセージに、組織のブランドを追加する](add-your-organization-brand-to-encrypted-messages.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54b8a-177">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disabling-the-new-capabilities-for-ome"></a><span data-ttu-id="54b8a-178">ホームの新機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="54b8a-178">Disabling the new capabilities for OME</span></span>

<span data-ttu-id="54b8a-p115">する必要があります、ホームが非常に簡単ですが、新機能を無効にすることが当然と思います。まず、ルールを削除、メール フローを作成したホームの新機能を使用する必要があります。メール フロー ルールを削除する方法の詳細については、[メール フロー ルールの管理](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)を参照してください。次に、これらの手順を完了 Exchange オンライン PowerShell。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p115">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward. First, you'll need to remove any mail flow rules you've created that use the new OME capabilities. For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="54b8a-183">ホームの新機能を無効にするには</span><span class="sxs-lookup"><span data-stu-id="54b8a-183">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="54b8a-p116">大域管理者アクセス許可を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://aka.ms/exopowershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p116">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="54b8a-p117">Web 上の Outlook で [**保護**] ボタンを有効にする場合は、SimplifiedClientAccessEnabled パラメーターを使用してセット IRMConfiguration コマンドレットを実行して無効にします。それ以外の場合、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="54b8a-p117">If you enabled the **Protect** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter. Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="54b8a-188">False に設定する AzureRMSLicensingEnabled パラメーターを使用してセット IRMConfiguration コマンドレットを実行して、ホームの新機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="54b8a-188">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
