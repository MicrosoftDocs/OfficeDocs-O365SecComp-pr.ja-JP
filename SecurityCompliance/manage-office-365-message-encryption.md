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
description: Office 365 Message Encryption (OME) の設定を終了すると、さまざまな方法で展開の構成をカスタマイズできます。たとえば、1回限りのパスコードを有効にするかどうかを構成したり、Outlook on the web に [保護] ボタンを表示したり、その他の設定を行ったりすることができます。この記事のタスクでは、その方法について説明します。
ms.openlocfilehash: 7b5297ae42d3efa071408540863c6ff7dbdee407
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275977"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="f7088-105">Office 365 Message Encryption を管理する</span><span class="sxs-lookup"><span data-stu-id="f7088-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="f7088-p102">Office 365 Message Encryption (OME) の設定を終了すると、さまざまな方法で展開の構成をカスタマイズできます。たとえば、1回限りのパスコードを有効にするかどうかを構成したり、Outlook on the web に [**保護**] ボタンを表示したり、その他の設定を行ったりすることができます。この記事のタスクでは、その方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7088-p102">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in a number of ways. For example, you can configure whether to enable one-time pass codes, display the **Protect** button in Outlook on the web, and more. The tasks in this article describe how.</span></span>
  
||
|:-----|
|<span data-ttu-id="f7088-p103">この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。この記事は、管理者および it 担当者を対象としています。暗号化されたメッセージの送信または受信に関する情報をお探しの場合は、「 [Office 365 message Encryption (OME)](ome.md) 」の記事の一覧を参照し、ニーズに最も適した記事を見つけてください。</span><span class="sxs-lookup"><span data-stu-id="f7088-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="f7088-112">Google、Yahoo、Microsoft アカウントの受信者が、これらのアカウントを使用して Office 365 メッセージ暗号化ポータルにサインインできるかどうかを管理する</span><span class="sxs-lookup"><span data-stu-id="f7088-112">Managing whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="f7088-p104">既定では、新しい office 365 メッセージ暗号化機能をセットアップすると、組織内のユーザーは、office 365 組織の外部にいる受信者にメッセージを送信できます。受信者が Google account、Yahoo アカウント、Microsoft アカウントなどの*ソーシャル id*を使用している場合、受信者はソーシャル id を使用して OME ポータルにサインインできます。必要に応じて、受信者がソーシャル id を使用して OME ポータルにサインインすることを許可しないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f7088-p104">By default, when you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization. If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal using the social ID. If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-to-allow-recipients-to-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="f7088-116">受信者がソーシャル id を使用して OME ポータルにサインインすることを許可するかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="f7088-116">To manage whether or not to allow recipients to use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="f7088-117">[リモート PowerShell を使用して Exchange Online に接続](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="f7088-117">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="f7088-118">次のように、指定された引数を指定して、omeconfiguration/コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7088-118">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true | $false>
   ```

   <span data-ttu-id="f7088-119">たとえば、ソーシャル id を無効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f7088-119">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="f7088-120">ソーシャル id を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="f7088-120">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="f7088-121">Office 365 メッセージ暗号化ポータルへのサインインのワンタイムパスコードの使用を管理する</span><span class="sxs-lookup"><span data-stu-id="f7088-121">Managing the use of one-time pass codes for signing in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="f7088-p105">既定では、OME によって暗号化されたメッセージの受信者が Outlook を使用しない場合、受信者によって使用されるアカウントに関係なく、受信者は、メッセージを読むことができる限られた時間の web 表示リンクを受信します。これには、1回限りのパスコードが含まれます。管理者は、1回限りのパスコードを使用して OME ポータルにサインインできるかどうかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f7088-p105">By default, if the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message. This includes a one-time pass code. As an administrator, you can manage whether or not one-time pass codes can be used to sign-in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-one-time-pass-codes-are-generated-for-ome"></a><span data-ttu-id="f7088-125">OME に対して1回限りのパスコードが生成されるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="f7088-125">To manage whether or not one-time pass codes are generated for OME</span></span>
  
1. <span data-ttu-id="f7088-p106">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7088-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f7088-128">OTPEnabled パラメーターを指定して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7088-128">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="f7088-129">たとえば、ワンタイムパスコードを無効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f7088-129">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="f7088-130">1回限りのパスコードを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="f7088-130">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a><span data-ttu-id="f7088-131">Outlook on the web で保護ボタンの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="f7088-131">Managing the display of the Protect button in Outlook on the web</span></span>

<span data-ttu-id="f7088-p107">既定では、OME をセットアップすると、web 上の Outlook の [**保護**] ボタンは有効になりません。管理者は、このボタンをエンドユーザーに表示するかどうかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f7088-p107">By default, the **Protect** button in Outlook on the web is not enabled when you set up OME. As an administrator, you can manage whether or not to display this button to end users.</span></span>
  
### <a name="to-manage-whether-or-not-the-protect-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="f7088-134">Outlook on the web に [保護] ボタンが表示されるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="f7088-134">To manage whether or not the Protect button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="f7088-p108">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7088-p108">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f7088-137">SimplifiedClientAccessEnabled パラメーターを指定して、Set-irmconfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7088-137">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="f7088-138">たとえば、[**保護**] ボタンを無効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f7088-138">For example, to disable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="f7088-139">[**保護**] ボタンを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="f7088-139">To enable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="f7088-140">iOS メールアプリユーザーの電子メールメッセージのサービス側の復号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="f7088-140">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="f7088-p109">iOS メールアプリは、Office 365 メッセージの暗号化で保護されたメッセージを解読できません。Office 365 管理者は、iOS メールアプリに配信されるメッセージに対してサービス側の復号化を適用できます。これを実行することを選択すると、サービスは、暗号化解除されたメッセージのコピーを iOS デバイスに送信します。このメッセージは、クライアントデバイスに復号化されて格納されます。また、iOS メールアプリでユーザーにクライアント側の使用権限が適用されない場合でも、メッセージは使用権限に関する情報を保持します。これは、ユーザーが元の権限を持たない場合でも、メッセージをコピーまたは印刷できることを意味します。ただし、ユーザーが Office 365 メールサーバーを必要とする操作 (メッセージの転送など) を実行しようとした場合、そのユーザーの使用権限が設定されていない場合、サーバーはアクションを許可しません。ただし、エンドユーザーは、iOS メールアプリの別のアカウントからメッセージを転送することにより、使用制限を転送しないようにすることができます。メールのサービス側の復号化を設定するかどうかに関係なく、暗号化された、権限が保護されたメールへのすべての添付ファイルiOS メールアプリでは表示できません。</span><span class="sxs-lookup"><span data-stu-id="f7088-p109">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption. As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app. When you choose to do this, the service sends a decrypted copy of the message to the iOS device. The message is stored decrypted on the client device. The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user. This means that the user can copy or print the message even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server will not permit the action if the user did not originally have the usage right to do so. However, end-users can work around Do Not Forward usage restriction by forwarding the message from a different account in their iOS mail app. Regardless of whether you set up service-side decryption of mail, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="f7088-p110">iOS メールアプリユーザーに暗号化されたメッセージを送信することを許可しない場合、ユーザーには、メッセージを表示する権限がないことを示すメッセージが表示されます。既定では、電子メールメッセージのサービス側の復号化は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="f7088-p110">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message. By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="f7088-152">詳細と、クライアント環境の表示の詳細については、「 [iPhone または iPad で暗号化されたメッセージを表示](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7088-152">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-or-not-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="f7088-153">iOS メールアプリユーザーが Office 365 で保護されたメッセージを表示できるかどうかを管理するには、メッセージの暗号化</span><span class="sxs-lookup"><span data-stu-id="f7088-153">To manage whether or not iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="f7088-p111">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7088-p111">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f7088-156">AllowRMSSupportForUnenlightenedApps パラメーターを指定して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7088-156">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="f7088-157">たとえば、iOS メールアプリなどの unenlightened アプリに送信される前にメッセージを復号化するようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f7088-157">For example, to configure the service to decrypt messages before they are sent to unenlightened apps such as the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="f7088-158">また、暗号化されていないメッセージを unenlightened アプリに送信しないようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f7088-158">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="f7088-159">web ブラウザメールクライアントの電子メール添付ファイルのサービス側復号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="f7088-159">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="f7088-p112">通常、Office 365 メッセージの暗号化を使用すると、添付ファイルは自動的に暗号化されます。Office 365 管理者は、ユーザーが web ブラウザーからダウンロードした電子メール添付ファイルに対して、サービス側の復号化を適用できます。</span><span class="sxs-lookup"><span data-stu-id="f7088-p112">Normally, when you use Office 365 message encryption, attachments are automatically encrypted. As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="f7088-p113">これを選択すると、ファイルの復号化されたコピーがサービスによってデバイスに送信されます。メッセージはまだ暗号化されています。また、電子メール添付ファイルには、ブラウザーがクライアント側の使用権限をユーザーに適用しない場合でも、使用権限に関する情報が保持されます。これは、ユーザーが元の権限を持っていない場合でも、電子メールの添付ファイルをコピーまたは印刷できることを意味します。ただし、ユーザーが Office 365 メールサーバーを必要とするアクション (添付ファイルの転送など) を実行しようとした場合、そのユーザーが元の使用権限を持っていなかった場合、サーバーはアクションを許可しません。</span><span class="sxs-lookup"><span data-stu-id="f7088-p113">When you choose to do this, the service sends a decrypted copy of the file to the device. The message is still encrypted. The email attachment also retains information about usage rights even though the browser does not apply client-side usage rights to the user. This means that the user can copy or print the email attachment even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server will not permit the action if the user did not originally have the usage right to do so.</span></span>
  
<span data-ttu-id="f7088-167">添付ファイルのサービス側の復号化を設定しているかどうかに関係なく、暗号化された、権限が保護されたメールの添付ファイルは、iOS メールアプリでは表示できません。</span><span class="sxs-lookup"><span data-stu-id="f7088-167">Regardless of whether you set up service-side decryption of attachments, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="f7088-168">暗号化された電子メール添付ファイルを許可しない場合、既定では、ユーザーには添付ファイルを表示する権限がないというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7088-168">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="f7088-169">Office 365 で、[暗号化のみ] オプションを使用してメールおよび電子メール添付ファイルの暗号化を実装する方法の詳細については、「encryption [-only](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7088-169">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-or-not-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="f7088-170">web ブラウザーからのダウンロード時に電子メールの添付ファイルの暗号化を解除するかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="f7088-170">To manage whether or not email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="f7088-p114">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7088-p114">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f7088-173">DecryptAttachmentFromPortal パラメーターを指定して、Set-irmconfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7088-173">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="f7088-174">たとえば、ユーザーが web ブラウザーから電子メールの添付ファイルをダウンロードするときに、添付ファイルを復号化するようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f7088-174">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="f7088-175">暗号化された電子メール添付ファイルをダウンロード時に残すようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f7088-175">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="f7088-176">電子メールメッセージと OME ポータルの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="f7088-176">Customizing the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="f7088-177">組織に合わせて OME をカスタマイズする方法の詳細については、「[組織のブランドを暗号化されたメッセージに追加](add-your-organization-brand-to-encrypted-messages.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7088-177">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disabling-the-new-capabilities-for-ome"></a><span data-ttu-id="f7088-178">OME の新機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="f7088-178">Disabling the new capabilities for OME</span></span>

<span data-ttu-id="f7088-p115">この記事は提供されていませんが、必要な場合は、OME の新機能を無効にすることは非常に簡単です。最初に、新しい OME 機能を使用するように作成したメールフロールールを削除する必要があります。メールフロールールの削除の詳細については、「[メールフロールールの管理](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)」を参照してください。次に、Exchange Online の PowerShell で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7088-p115">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward. First, you'll need to remove any mail flow rules you've created that use the new OME capabilities. For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="f7088-183">OME の新機能を無効にするには</span><span class="sxs-lookup"><span data-stu-id="f7088-183">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="f7088-p116">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7088-p116">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f7088-p117">web 上の Outlook で [**保護**] ボタンを有効にした場合は、SimplifiedClientAccessEnabled パラメーターを指定して、Set-irmconfiguration コマンドレットを実行することによって、これを無効にします。それ以外の場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="f7088-p117">If you enabled the **Protect** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter. Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="f7088-188">OME の新機能を無効にするには、AzureRMSLicensingEnabled パラメーターを false に設定して、set-irmconfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7088-188">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
