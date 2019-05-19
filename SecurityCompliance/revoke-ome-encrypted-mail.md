---
title: Office 365 Advanced Message Encryption 機能を使って暗号化されたメールを無効にする
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Office 365 管理者は、Office 365 Advanced Message Encryption で暗号化された特定の電子メールを取り消すことができます。
ms.openlocfilehash: 098ce50791152c8bbb4e4692d6fb85e4c2c7cb58
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156789"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="2628e-103">Office 365 Advanced Message Encryption 機能を使って暗号化されたメールを無効にする</span><span class="sxs-lookup"><span data-stu-id="2628e-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="2628e-104">電子メールの取り消しは、Office 365 Advanced Message Encryption の一部として提供されます。</span><span class="sxs-lookup"><span data-stu-id="2628e-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="2628e-105">Office 365 の高度なメッセージの暗号化は、特定のサブスクリプションの Office 365 メッセージの暗号化の上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2628e-105">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="2628e-106">高度なメッセージ暗号化は、 [Microsoft 365 Enterprise e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 Enterprise e5、および Office 365 エデュケーション A5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="2628e-106">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="2628e-107">Office 365 Advanced Message Encryption を含まない Office 365 サブスクリプションが組織にある場合は、Advanced コンプライアンス SKU の E5 コンプライアンスを使用して、高度なメッセージ暗号化をアドオンとして購入できます。</span><span class="sxs-lookup"><span data-stu-id="2628e-107">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="2628e-108">この記事は、 [Office 365 メッセージの暗号化](ome.md)についてのより大きな一連の記事の一部です。</span><span class="sxs-lookup"><span data-stu-id="2628e-108">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="2628e-109">既に送信されている電子メールを取り消す必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="2628e-109">You may find it necessary to revoke an email that has already been sent.</span></span> <span data-ttu-id="2628e-110">Office 365 Advanced Message Encryption を使用して電子メールを暗号化していて、Office 365 管理者である場合は、特定の条件下で電子メールに対してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2628e-110">If the email was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do this for email under certain conditions.</span></span> <span data-ttu-id="2628e-111">この記事では、これが可能な状況とその方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2628e-111">This article describes under what circumstances this is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="2628e-112">取り消すことができる暗号化された電子メール</span><span class="sxs-lookup"><span data-stu-id="2628e-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="2628e-113">受信者がリンクベースの、ブランド化された電子メールを受信した場合は、暗号化された電子メールを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="2628e-113">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="2628e-114">受信者が、サポートされている Outlook クライアントでネイティブインライン環境を受信した場合は、それらの電子メールを取り消すことはできません。</span><span class="sxs-lookup"><span data-stu-id="2628e-114">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="2628e-115">受信者がリンクベースの機能を受信するか、またはインラインでの使用を許可するかは、受信者の id の種類によって異なります。 Office 365 と Microsoft アカウントの受信者 (たとえば、outlook.com users) は、サポートされている Outlook クライアントでインラインの動作を取得します。</span><span class="sxs-lookup"><span data-stu-id="2628e-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="2628e-116">Gmail 受信者など、他のすべての受信者の種類は、リンクベースの処理を行います。</span><span class="sxs-lookup"><span data-stu-id="2628e-116">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="2628e-117">取り消された暗号化された電子メールの受信者向けの手順</span><span class="sxs-lookup"><span data-stu-id="2628e-117">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="2628e-118">電子メールが失効されると、受信者は Office 365 メッセージ暗号化ポータルを経由して暗号化された電子メールにアクセスしようとすると、エラーが発生します。 "メッセージは送信者によって取り消されました" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2628e-118">Once an email has been revoked, the recipient will get an error when trying to access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![取り消された暗号化された電子メールを示すスクリーンショット。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="2628e-120">暗号化された電子メールを取り消す方法</span><span class="sxs-lookup"><span data-stu-id="2628e-120">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="2628e-121">手順 1.</span><span class="sxs-lookup"><span data-stu-id="2628e-121">Step 1.</span></span> <span data-ttu-id="2628e-122">電子メールのメッセージ ID を取得する</span><span class="sxs-lookup"><span data-stu-id="2628e-122">Obtain the Message ID of the email</span></span>

<span data-ttu-id="2628e-123">暗号化されたメールを取り消すには、メールのメッセージ ID を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2628e-123">Before you can revoke an encrypted mail you need to gather the Message ID of the mail.</span></span> <span data-ttu-id="2628e-124">MessageId は通常、次の形式になります。</span><span class="sxs-lookup"><span data-stu-id="2628e-124">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="2628e-125">取り消したい電子メールのメッセージ ID を複数の方法で見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="2628e-125">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="2628e-126">このセクションでは、いくつかのオプションについて説明しますが、ID を提供する任意の方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2628e-126">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="2628e-127">セキュリティ&amp; /コンプライアンスセンターのメッセージ追跡を使用して取り消す電子メールのメッセージ ID を特定するには</span><span class="sxs-lookup"><span data-stu-id="2628e-127">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="2628e-128">[Office 365 セキュリティ _AMP_ コンプライアンスセンターで、新しいメッセージの追跡](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)を使用して、送信者または受信者別に電子メールを検索します。</span><span class="sxs-lookup"><span data-stu-id="2628e-128">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="2628e-129">電子メールを見つけたら、それを選択して**メッセージ追跡の詳細**ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="2628e-129">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="2628e-130">**詳細情報**を展開して、メッセージ ID を見つけます。</span><span class="sxs-lookup"><span data-stu-id="2628e-130">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="2628e-131">セキュリティ&amp; /コンプライアンスセンターで Office メッセージの暗号化レポートを使用して取り消す電子メールのメッセージ ID を特定するには</span><span class="sxs-lookup"><span data-stu-id="2628e-131">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="2628e-132">セキュリティ&amp; /コンプライアンスセンターで、[メッセージの**暗号化] レポート**に移動します。</span><span class="sxs-lookup"><span data-stu-id="2628e-132">In the Security &amp; Compliance Center, navigate to the **Message Encryption Report**.</span></span>

2. <span data-ttu-id="2628e-133">[**詳細の表示**] テーブルを選択し、取り消すメッセージを識別します。</span><span class="sxs-lookup"><span data-stu-id="2628e-133">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="2628e-134">メッセージをダブルクリックして、メッセージ ID を含む詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="2628e-134">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="2628e-135">手順 2.</span><span class="sxs-lookup"><span data-stu-id="2628e-135">Step 2.</span></span> <span data-ttu-id="2628e-136">メールが revocable かどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="2628e-136">Verify that the mail is revocable</span></span>

<span data-ttu-id="2628e-137">特定の電子メールメッセージを取り消すことができるかどうかを確認するには、セキュリティ&amp;コンプライアンスセンターの**詳細**テーブルに [失効状態] フィールドが表示されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2628e-137">To verify whether you can revoke a particular email message, check whether the Revocation Status field is visible in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="2628e-138">Windows Powershell を使用して特定の電子メールメッセージを取り消すことができるかどうかを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2628e-138">To verify whether or not you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="2628e-139">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="2628e-139">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="2628e-140">手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2628e-140">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="2628e-141">次のように、Set-OMEMessageStatus コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="2628e-141">Run the Set-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="2628e-142">これにより、メッセージの件名と、メッセージが revocable かどうかが返されます。</span><span class="sxs-lookup"><span data-stu-id="2628e-142">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="2628e-143">For example,</span><span class="sxs-lookup"><span data-stu-id="2628e-143">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="2628e-144">手順 3.</span><span class="sxs-lookup"><span data-stu-id="2628e-144">Step 3.</span></span> <span data-ttu-id="2628e-145">メールを取り消す</span><span class="sxs-lookup"><span data-stu-id="2628e-145">Revoke the mail</span></span>  

<span data-ttu-id="2628e-146">取り消したい電子メールのメッセージ ID がわかっており、メッセージが revocable であることを確認したら、電子メールを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="2628e-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email.</span></span>

<span data-ttu-id="2628e-147">セキュリティ&amp; /コンプライアンスセンターで電子メールを取り消すには、**詳細**表で [**取り消し**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2628e-147">To revoke the email in the Security &amp; Compliance Center, in the **Details** table, choose **Revoke**.</span></span>

<span data-ttu-id="2628e-148">OMEMessageRevocation コマンドレットを使用して、Windows Powershell を使用して電子メールを失効させることができます。</span><span class="sxs-lookup"><span data-stu-id="2628e-148">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="2628e-149">[Exchange Online PowerShell への接続](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="2628e-149">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="2628e-150">OMEMessageRevocation コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="2628e-150">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="2628e-151">電子メールが失効したかどうかを確認するには、次のようにして、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="2628e-151">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="2628e-152">失効が成功した場合、コマンドレットは次の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="2628e-152">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="2628e-153">Office 365 の詳細なメッセージの暗号化に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="2628e-153">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="2628e-154">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="2628e-154">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="2628e-155">Office 365 の高度なメッセージの暗号化-電子メールの有効期限</span><span class="sxs-lookup"><span data-stu-id="2628e-155">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="2628e-156">メッセージポリシーとコンプライアンスサービスの説明</span><span class="sxs-lookup"><span data-stu-id="2628e-156">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)