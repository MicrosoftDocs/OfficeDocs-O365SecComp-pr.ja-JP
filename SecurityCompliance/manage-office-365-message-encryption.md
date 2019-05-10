---
title: Office 365 Message Encryption を管理する
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Office 365 Message Encryption (OME) の設定を終了すると、いくつかの方法で展開の構成をカスタマイズできます。 たとえば、1回限りのパスコードを有効にするかどうかを構成したり、Outlook on the web に [保護] ボタンを表示したり、その他の設定を行ったりすることができます。 この記事のタスクでは、その方法について説明します。
ms.openlocfilehash: 1afaaea3cd744878630598acd3f02dc7dc70e9cb
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834926"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="95c3c-105">Office 365 Message Encryption を管理する</span><span class="sxs-lookup"><span data-stu-id="95c3c-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="95c3c-106">Office 365 Message Encryption (OME) の設定を終了すると、いくつかの方法で展開の構成をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-106">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="95c3c-107">たとえば、1回限りのパスコードを有効にするかどうかを構成したり、Outlook on the web に [**保護**] ボタンを表示したり、その他の設定を行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-107">For example, you can configure whether to enable one-time pass codes, display the **Protect** button in Outlook on the web, and more.</span></span> <span data-ttu-id="95c3c-108">この記事のタスクでは、その方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-108">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="95c3c-109">Google、Yahoo、Microsoft アカウントの受信者がこれらのアカウントを使用して Office 365 メッセージ暗号化ポータルにサインインできるかどうかを管理する</span><span class="sxs-lookup"><span data-stu-id="95c3c-109">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="95c3c-110">新しい Office 365 メッセージ暗号化機能をセットアップすると、組織内のユーザーは、Office 365 組織外の受信者にメッセージを送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="95c3c-110">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization.</span></span> <span data-ttu-id="95c3c-111">受信者が Google account、Yahoo アカウント、Microsoft アカウントなどの*ソーシャル id*を使用している場合、受信者はソーシャル ID で OME ポータルにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-111">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="95c3c-112">必要に応じて、受信者がソーシャル Id を使用して OME ポータルにサインインすることを許可しないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-112">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="95c3c-113">受信者がソーシャル Id を使用して OME ポータルにサインインできるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="95c3c-113">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="95c3c-114">[リモート PowerShell を使用して Exchange Online に接続](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-114">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="95c3c-115">次のように、指定された引数を指定して、OMEConfiguration/コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-115">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="95c3c-116">たとえば、ソーシャル Id を無効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="95c3c-116">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="95c3c-117">ソーシャル Id を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="95c3c-117">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="95c3c-118">Office 365 メッセージ暗号化ポータルの1回限りのパスコードの使用を管理する</span><span class="sxs-lookup"><span data-stu-id="95c3c-118">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="95c3c-119">OME によって暗号化されたメッセージの受信者が Outlook を使用していない場合は、受信者によって使用されるアカウントに関係なく、受信者は、メッセージを読むことができる限られた時間の web 表示リンクを受信します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-119">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="95c3c-120">このリンクには、1回限りのパスコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="95c3c-120">This link includes a one-time pass code.</span></span> <span data-ttu-id="95c3c-121">管理者は、受信者がワンタイムパスコードを使用して OME ポータルにサインインできるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-121">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="95c3c-122">OME がワンタイムパスコードを生成するかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="95c3c-122">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="95c3c-123">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-123">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="95c3c-124">手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c3c-124">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="95c3c-125">OTPEnabled パラメーターを指定して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-125">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="95c3c-126">たとえば、ワンタイムパスコードを無効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="95c3c-126">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="95c3c-127">1回限りのパスコードを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="95c3c-127">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-protect-button-in-outlook-on-the-web"></a><span data-ttu-id="95c3c-128">Outlook on the web で [保護] ボタンの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="95c3c-128">Manage the display of the Protect button in Outlook on the web</span></span>

<span data-ttu-id="95c3c-129">OME をセットアップすると、web 上の Outlook の [**保護**] ボタンは無効になります。</span><span class="sxs-lookup"><span data-stu-id="95c3c-129">The **Protect** button in Outlook on the web is disabled when you set up OME.</span></span> <span data-ttu-id="95c3c-130">管理者は、このボタンをエンドユーザーに表示するかどうかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-130">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-protect-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="95c3c-131">Outlook on the web に [保護] ボタンが表示されるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="95c3c-131">To manage whether the Protect button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="95c3c-132">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-132">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="95c3c-133">手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c3c-133">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="95c3c-134">SimplifiedClientAccessEnabled パラメーターを指定して、Set-IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-134">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="95c3c-135">たとえば、[**保護**] ボタンを無効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="95c3c-135">For example, to disable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="95c3c-136">[**保護**] ボタンを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="95c3c-136">To enable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="95c3c-137">IOS メールアプリユーザーの電子メールメッセージのサービス側の復号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="95c3c-137">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="95c3c-138">IOS メールアプリは、Office 365 メッセージの暗号化で保護されたメッセージを解読できません。</span><span class="sxs-lookup"><span data-stu-id="95c3c-138">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="95c3c-139">Office 365 管理者は、iOS メールアプリに配信されるメッセージに対してサービス側の復号化を適用できます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-139">As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="95c3c-140">サービス側の復号化を使用することを選択すると、サービスは、復号化されたメッセージのコピーを iOS デバイスに送信します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-140">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="95c3c-141">クライアントデバイスは、復号化されたメッセージのコピーを格納します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-141">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="95c3c-142">また、iOS メールアプリでユーザーにクライアント側の使用権限が適用されない場合でも、メッセージは使用権限に関する情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-142">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="95c3c-143">ユーザーは、メッセージをコピーまたは印刷する権限を持っていない場合でも、メッセージをコピーまたは印刷することができます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-143">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="95c3c-144">ただし、ユーザーが Office 365 メールサーバーを必要とする操作 (メッセージの転送など) を実行しようとした場合、ユーザーが最初に使用権限を持っていなかった場合、サーバーはアクションを許可しません。</span><span class="sxs-lookup"><span data-stu-id="95c3c-144">However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="95c3c-145">ただし、エンドユーザーは、iOS メールアプリ内の別のアカウントからメッセージを転送することによって、"転送不可" の使用制限を回避できます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-145">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="95c3c-146">メールのサービス側の復号化を設定しているかどうかに関係なく、暗号化されたメールの添付ファイルと権限保護されたメールは、iOS メールアプリでは表示できません。</span><span class="sxs-lookup"><span data-stu-id="95c3c-146">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="95c3c-147">IOS メールアプリユーザーに暗号化されたメッセージを送信することを許可しない場合、ユーザーには、メッセージを表示する権限がないことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-147">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="95c3c-148">既定では、電子メールメッセージのサービス側の復号化は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="95c3c-148">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="95c3c-149">詳細と、クライアント環境の表示の詳細については、「 [iPhone または iPad で暗号化されたメッセージを表示](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c3c-149">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="95c3c-150">Office 365 メッセージの暗号化によって保護されたメッセージを iOS メールアプリのユーザーが表示できるかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="95c3c-150">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="95c3c-151">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-151">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="95c3c-152">手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c3c-152">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="95c3c-153">AllowRMSSupportForUnenlightenedApps パラメーターを指定して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-153">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="95c3c-154">たとえば、iOS メールアプリなどの unenlightened アプリに送信される前にメッセージを復号化するようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="95c3c-154">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="95c3c-155">また、暗号化されていないメッセージを unenlightened アプリに送信しないようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="95c3c-155">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="95c3c-156">Web ブラウザメールクライアントの電子メール添付ファイルのサービス側復号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="95c3c-156">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="95c3c-157">通常、Office 365 メッセージの暗号化を使用すると、添付ファイルは自動的に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-157">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="95c3c-158">Office 365 管理者は、ユーザーが web ブラウザーからダウンロードした電子メール添付ファイルに対して、サービス側の復号化を適用できます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-158">As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="95c3c-159">サービス側の復号化を使用すると、ファイルの復号化されたコピーがサービスによってデバイスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-159">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="95c3c-160">メッセージはまだ暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="95c3c-160">The message is still encrypted.</span></span> <span data-ttu-id="95c3c-161">また、電子メールの添付ファイルは、ブラウザーがクライアント側の使用権限をユーザーに適用しない場合でも、使用権限に関する情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-161">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="95c3c-162">ユーザーは、元の権限がない場合でも、電子メールの添付ファイルをコピーまたは印刷することができます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-162">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="95c3c-163">ただし、ユーザーが Office 365 メールサーバーを必要とするアクション (添付ファイルの転送など) を完了しようとした場合、ユーザーの使用権限が最初に付与されていなかった場合、サーバーはアクションを許可しません。</span><span class="sxs-lookup"><span data-stu-id="95c3c-163">However, if the user tries to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="95c3c-164">添付ファイルのサービス側の復号化を設定しているかどうかに関係なく、ユーザーは、暗号化されていて、権限で保護されたメールの添付ファイルを iOS メールアプリで表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="95c3c-164">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="95c3c-165">暗号化された電子メール添付ファイルを許可しない場合、既定では、ユーザーには添付ファイルを表示する権限がないというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-165">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="95c3c-166">Office 365 で、[暗号化のみ] オプションを使用してメールおよび電子メール添付ファイルの暗号化を実装する方法の詳細については、「encryption [-only](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c3c-166">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="95c3c-167">Web ブラウザーからのダウンロード時に電子メールの添付ファイルの暗号化を解除するかどうかを管理するには</span><span class="sxs-lookup"><span data-stu-id="95c3c-167">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="95c3c-168">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-168">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="95c3c-169">手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c3c-169">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="95c3c-170">DecryptAttachmentFromPortal パラメーターを指定して、Set-IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-170">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="95c3c-171">たとえば、ユーザーが web ブラウザーから電子メールの添付ファイルをダウンロードするときに、添付ファイルを復号化するようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="95c3c-171">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="95c3c-172">暗号化された電子メール添付ファイルをダウンロード時に残すようにサービスを構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="95c3c-172">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only"></a><span data-ttu-id="95c3c-173">すべての外部受信者が OME ポータルを使用して暗号化されたメールを読み取ることを確認する-Office 365 Advanced Message Encryption のみ</span><span class="sxs-lookup"><span data-stu-id="95c3c-173">Ensure all external recipients use the OME Portal to read encrypted mail — Office 365 Advanced Message Encryption only</span></span>

<span data-ttu-id="95c3c-174">Office 365 の高度なメッセージ暗号化を使用している場合は、カスタムブランド化テンプレートを使用して、受信者が Outlook または web 上の Outlook を使用するのではなく、OME ポータルで暗号化された電子メールを読むように指示するラッパーメールを受信者に送信させることができます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-174">If you have Office 365 Advanced Message Encryption, you can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="95c3c-175">受信者が受信するメールの使用方法をより細かく制御する場合は、この操作を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="95c3c-175">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="95c3c-176">たとえば、外部の受信者が web ポータルで電子メールを表示する場合、電子メールの有効期限を設定し、電子メールを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-176">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="95c3c-177">これらの機能は、OME ポータルでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="95c3c-177">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="95c3c-178">メールフロールールを作成するときは、[暗号化] オプションと [転送不可] オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="95c3c-178">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="create-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email-to-be-revocable-and-expire-in-7-days"></a><span data-ttu-id="95c3c-179">カスタムテンプレートを作成して、すべての外部受信者が OME ポータルを使用するようにし、暗号化された電子メールを revocable に、7日間で期限切れにするようにします。</span><span class="sxs-lookup"><span data-stu-id="95c3c-179">Create a custom template to force all external recipients to use the OME Portal and for encrypted email to be revocable and expire in 7 days</span></span>

1. <span data-ttu-id="95c3c-180">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-180">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="95c3c-181">手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c3c-181">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="95c3c-182">新しい-OMEConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-182">Run the New-OMEConfiguration cmdlet:</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<template name>" -ExternalMailExpiryInDays 7
   ```

   <span data-ttu-id="95c3c-183">`template name`は、Office 365 メッセージ暗号化カスタムブランド化テンプレートに使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="95c3c-183">where `template name` is the name you want to use for the Office 365 Message Encryption custom branding template.</span></span> <span data-ttu-id="95c3c-184">For example,</span><span class="sxs-lookup"><span data-stu-id="95c3c-184">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<One week expiration>" -ExternalMailExpiryInDays 7
   ```

3. <span data-ttu-id="95c3c-185">New-transportrule コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-185">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="95c3c-186">各部分の意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="95c3c-186">where:</span></span>

   - <span data-ttu-id="95c3c-187">`mail flow rule name`は、新しいメールフロールールに使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="95c3c-187">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="95c3c-188">`option name`は、 `Encrypt`また`Do Not Forward`はのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="95c3c-188">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="95c3c-189">`template name`は、カスタムブランド化テンプレートに指定した名前です`One week expiration`(例:)。</span><span class="sxs-lookup"><span data-stu-id="95c3c-189">`template name` is the name you gave the custom branding template, for example `One week expiration`.</span></span>

   <span data-ttu-id="95c3c-190">[1 週間の有効期限] テンプレートを使用してすべての外部電子メールを暗号化し、暗号化のみのオプションを適用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="95c3c-190">To encrypt all external email with the "One week expiration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

   <span data-ttu-id="95c3c-191">[1 週間の有効期限] テンプレートを使用してすべての外部電子メールを暗号化し、[転送しない] オプションを適用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-191">To encrypt all external email with the "One week expiration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="95c3c-192">電子メールメッセージと OME ポータルの外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="95c3c-192">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="95c3c-193">組織に合わせて OME をカスタマイズする方法の詳細については、「[組織のブランドを暗号化されたメッセージに追加](add-your-organization-brand-to-encrypted-messages.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c3c-193">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="95c3c-194">OME の新機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="95c3c-194">Disable the new capabilities for OME</span></span>

<span data-ttu-id="95c3c-195">この記事は提供されていませんが、必要な場合は、OME の新機能を無効にすることは非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="95c3c-195">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="95c3c-196">最初に、新しい OME 機能を使用するように作成したメールフロールールを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95c3c-196">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="95c3c-197">メールフロールールの削除の詳細については、「[メールフロールールの管理](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c3c-197">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="95c3c-198">次に、Exchange Online の PowerShell で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-198">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="95c3c-199">OME の新機能を無効にするには</span><span class="sxs-lookup"><span data-stu-id="95c3c-199">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="95c3c-200">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-200">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="95c3c-201">手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c3c-201">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="95c3c-202">Web 上の Outlook で [**保護**] ボタンを有効にした場合は、SimplifiedClientAccessEnabled パラメーターを指定して、Set-IRMConfiguration コマンドレットを実行することによって、これを無効にします。</span><span class="sxs-lookup"><span data-stu-id="95c3c-202">If you enabled the **Protect** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="95c3c-203">それ以外の場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="95c3c-203">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="95c3c-204">OME の新機能を無効にするには、AzureRMSLicensingEnabled パラメーターを false に設定して、Set-IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="95c3c-204">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
