---
title: Office 365 Message Encryption によって暗号化された電子メールを取り消す
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: office 365 管理者は、office 365 メッセージの暗号化を使用して暗号化された特定の電子メールを取り消すことができます。
ms.openlocfilehash: 75b5e46e25f447ddac0de5a7911d0df8385da6b9
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214897"
---
# <a name="office-365-message-encryption-email-revocation"></a><span data-ttu-id="22ebe-103">Office 365 メッセージ暗号化の電子メールの取り消し</span><span class="sxs-lookup"><span data-stu-id="22ebe-103">Office 365 Message Encryption email revocation</span></span>

<span data-ttu-id="22ebe-p101">この記事は、 [Office 365 メッセージの暗号化](ome.md)についてのより大きな一連の記事の一部です。これで、暗号化された電子メールの取り消しがプレビューに表示されます。サービスを改善していく中で、機能とコンテンツに対する更新や変更が予想されます。</span><span class="sxs-lookup"><span data-stu-id="22ebe-p101">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md). Right now, encrypted email revocation is in preview. Expect updates and changes to the feature and the content as we continue to improve our offering.</span></span>

<span data-ttu-id="22ebe-p102">既に送信されている電子メールを取り消す必要がある場合があります。office 365 メッセージの暗号化を使用して電子メールを暗号化していて、office 365 管理者である場合は、特定の条件下で電子メールに対してこれを行うことができます。この記事では、これが可能な状況とその方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="22ebe-p102">You may find it necessary to revoke an email that has already been sent. If the email was encrypted using Office 365 Message Encryption, and you are an Office 365 admin, you can do this for email under certain conditions. This article describes under what circumstances this is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="22ebe-110">取り消すことができる暗号化された電子メール</span><span class="sxs-lookup"><span data-stu-id="22ebe-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="22ebe-p103">受信者がリンクベースの、ブランド化された電子メールを受信した場合は、暗号化された電子メールを取り消すことができます。受信者が、サポートされている Outlook クライアントでネイティブインライン環境を受信した場合は、それらの電子メールを取り消すことはできません。</span><span class="sxs-lookup"><span data-stu-id="22ebe-p103">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email. If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="22ebe-p104">受信者がリンクベースの機能を受信するか、またはインラインでの使用を許可するかは、受信者の id の種類によって異なります。 Office 365 と Microsoft アカウントの受信者 (たとえば、outlook.com users) は、サポートされている outlook クライアントでインラインの動作を取得します。Gmail 受信者など、他のすべての受信者の種類は、リンクベースの処理を行います。</span><span class="sxs-lookup"><span data-stu-id="22ebe-p104">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients. All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

<span data-ttu-id="22ebe-p105">近日中に、組織は、受信者の id に関係なく、リンクベースの操作を強制できるようになります。これにより、すべての受信者は Office 365 メッセージ暗号化ポータルへのリンクを持つブランド化された電子メールを取得し、暗号化された電子メールの読み取りと返信を行うことができます。このような暗号化された電子メールはすべて revocable になります。</span><span class="sxs-lookup"><span data-stu-id="22ebe-p105">Coming soon, organizations will have the ability to force a link-based experience regardless of the recipient identity. This way, all recipients will get a branded email with a link to the Office 365 Message Encryption portal where they will be able to read and reply to encrypted emails. All such encrypted emails will be revocable.</span></span>
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="22ebe-118">取り消された暗号化された電子メールの受信者向けの手順</span><span class="sxs-lookup"><span data-stu-id="22ebe-118">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="22ebe-119">電子メールが失効されると、受信者は Office 365 メッセージ暗号化ポータルを経由して暗号化された電子メールにアクセスしようとすると、エラーが発生します。 "メッセージは送信者によって取り消されました" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="22ebe-119">Once an email has been revoked, the recipient will get an error when trying to access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![取り消された暗号化された電子メールを示すスクリーンショット。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="22ebe-121">暗号化された電子メールを取り消す方法</span><span class="sxs-lookup"><span data-stu-id="22ebe-121">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="22ebe-p106">手順1電子メールのメッセージ ID を取得する</span><span class="sxs-lookup"><span data-stu-id="22ebe-p106">Step 1. Obtain the Message ID of the email</span></span>

<span data-ttu-id="22ebe-p107">暗号化されたメールを取り消すには、メールのメッセージ ID を収集する必要があります。MessageId は通常、次の形式になります。</span><span class="sxs-lookup"><span data-stu-id="22ebe-p107">Before you can revoke an encrypted mail you need to gather the Message ID of the mail. The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="22ebe-p108">取り消したい電子メールのメッセージ ID を複数の方法で見つけることができます。このセクションでは、いくつかのオプションについて説明しますが、ID を提供する任意の方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="22ebe-p108">There are multiple ways to find the Message ID of the email that you want to revoke. This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="22ebe-128">セキュリティ&amp; /コンプライアンスセンターのメッセージ追跡を使用して取り消す電子メールのメッセージ ID を特定するには</span><span class="sxs-lookup"><span data-stu-id="22ebe-128">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="22ebe-129">[Office 365 セキュリティ & コンプライアンスセンターで、新しいメッセージの追跡](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)を使用して、送信者または受信者別に電子メールを検索します。</span><span class="sxs-lookup"><span data-stu-id="22ebe-129">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>
2. <span data-ttu-id="22ebe-p109">メールを見つけたら、それを選択して**メッセージ追跡の詳細**ウィンドウを開きます。**詳細情報**を展開して、メッセージ ID を見つけます。</span><span class="sxs-lookup"><span data-stu-id="22ebe-p109">Once you've located the email select it to bring up the **Message trace details** pane. Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="22ebe-132">セキュリティ&amp; /コンプライアンスセンターで Office メッセージの暗号化レポートを使用して取り消す電子メールのメッセージ ID を特定するには</span><span class="sxs-lookup"><span data-stu-id="22ebe-132">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="22ebe-133">セキュリティ&amp; /コンプライアンスセンターで、[メッセージの**暗号化] レポート**に移動します。</span><span class="sxs-lookup"><span data-stu-id="22ebe-133">In the Security &amp; Compliance Center, navigate to the **Message Encryption Report**.</span></span>
2. <span data-ttu-id="22ebe-134">[**詳細の表示**] テーブルを選択し、取り消すメッセージを識別します。</span><span class="sxs-lookup"><span data-stu-id="22ebe-134">Choose the **View details** table and identify the message that you want to revoke.</span></span>
3. <span data-ttu-id="22ebe-135">メッセージをダブルクリックして、メッセージ ID を含む詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="22ebe-135">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="22ebe-p110">手順2メールが revocable かどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="22ebe-p110">Step 2. Verify that the mail is revocable</span></span>

<span data-ttu-id="22ebe-138">特定の電子メールメッセージを取り消すことができるかどうかを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="22ebe-138">To verify whether or not you can revoke a particular email message, complete these steps.</span></span>

1. <span data-ttu-id="22ebe-p111">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22ebe-p111">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="22ebe-141">次のように、Set-omemessagestatus コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="22ebe-141">Run the Set-OMEMessageStatus cmdlet as follows:</span></span>
     ```powershell
     Get-OMEMessageStatus -MessageId "<messagieid>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="22ebe-p112">これにより、メッセージの件名と、メッセージが revocable かどうかが返されます。例えば</span><span class="sxs-lookup"><span data-stu-id="22ebe-p112">This returns the subject of the message and whether the message is revocable. For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="22ebe-p113">手順3メールを取り消す</span><span class="sxs-lookup"><span data-stu-id="22ebe-p113">Step 3. Revoke the mail</span></span>  

<span data-ttu-id="22ebe-146">取り消す電子メールのメッセージ ID がわかっていて、メッセージが revocable であることを確認したら、OMEMessageRevocation コマンドレットを使用してその電子メールを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="22ebe-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="22ebe-147">[Exchange Online PowerShell に接続します](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="22ebe-147">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="22ebe-148">OMEMessageRevocation コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="22ebe-148">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="22ebe-149">電子メールが失効したかどうかを確認するには、次のようにして、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="22ebe-149">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```  
    <span data-ttu-id="22ebe-150">失効が成功した場合、コマンドレットは次の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="22ebe-150">If revocation was successful, the cmdlet returns the following result:</span></span>  

    `Revoked: True`
