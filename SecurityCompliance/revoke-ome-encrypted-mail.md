---
title: Office 365 のメッセージの暗号化によって暗号化された電子メールを取り消す
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/24/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
description: Office 365 管理者は、Office 365 のメッセージの暗号化で暗号化された電子メールの一部を取り消すことができます。
ms.openlocfilehash: 19eb874fa15a21c29a9eb2823829e81ff244a555
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011823"
---
# <a name="office-365-message-encryption-email-revocation"></a><span data-ttu-id="7ba6f-103">Office 365 のメッセージの暗号化メールの取り消し</span><span class="sxs-lookup"><span data-stu-id="7ba6f-103">Office 365 Message Encryption email revocation</span></span>

<span data-ttu-id="7ba6f-p101">この資料は、 [Office 365 のメッセージの暗号化](ome.md)についての記事の大規模な一連の一部です。プレビューでは、現在、暗号化された電子メールの取り消しです。当社の製品を改善していく機能と、コンテンツに対する更新や変更を期待してください。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-p101">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md). Right now, encrypted email revocation is in preview. Expect updates and changes to the feature and the content as we continue to improve our offering.</span></span>

<span data-ttu-id="7ba6f-p102">必要がありますが既に送信されている電子メールを無効にします。電子メールが Office 365 のメッセージの暗号化を使用して暗号化された Office 365 管理者は、する場合は、これを行う特定の条件下でメールをします。[どのような状況は考えられるとそれを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-p102">You may find it necessary to revoke an email that has already been sent. If the email was encrypted using Office 365 Message Encryption, and you are an Office 365 admin, you can do this for email under certain conditions. This article describes under what circumstances this is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="7ba6f-110">暗号化された電子メールを無効にすること</span><span class="sxs-lookup"><span data-stu-id="7ba6f-110">Encrypted emails that you can revoke</span></span>
<span data-ttu-id="7ba6f-p103">受信者を受信した場合、リンク ・ ベース、暗号化された電子メールのブランドは、暗号化された電子メールを取り消すことができます。受信者は、サポートされている Outlook クライアントで、インラインのネイティブ機能を受信する場合は、これらの e メールを取り消すことはできません。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-p103">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email. If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="7ba6f-113">リンク ベースの操作性を受け取った受信者かどうか、またはインライン経験は、受信者の id の種類によって異なります: Office 365 と Microsoft アカウントの受信者 (たとえば、outlook.com ユーザー) がサポートされている Outlook クライアントでインライン経験を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span>  
<span data-ttu-id="7ba6f-114">すべての他の受信者の種類など Gmail の受信者は、リンク ベースの操作性を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span> 

<span data-ttu-id="7ba6f-p104">まもなく、組織は、受信者の id に関係なくリンク ベースのエクスペリエンスを強制する機能があります。この方法では、すべての受信者にブランドの電子メールと暗号化された電子メールを読み、返信できないこと、Office 365 のメッセージの暗号化のポータルへのリンクが表示されます。このようなすべての暗号化された電子メールは取り消しになります。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-p104">Coming soon, organizations will have the ability to force a link-based experience regardless of the recipient identity. This way, all recipients will get a branded email with a link to the Office 365 Message Encryption portal where they will be able to read and reply to encrypted emails. All such encrypted emails will be revocable.</span></span> 
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="7ba6f-118">失効した暗号化された電子メールの受信者の経験</span><span class="sxs-lookup"><span data-stu-id="7ba6f-118">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="7ba6f-119">電子メールが取り消された後、受信者エラーが表示されます Office 365 のメッセージの暗号化のポータルを通じて、暗号化された電子メールにアクセスしようとしています:「メッセージは、送信者によって失効されています」。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-119">Once an email has been revoked, the recipient will get an error when trying to access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![失効した暗号化された電子メールを表示するスクリーン ショットです。](media/revoked-encrypted-email.png)
    
## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="7ba6f-121">暗号化された電子メールを破棄する方法</span><span class="sxs-lookup"><span data-stu-id="7ba6f-121">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="7ba6f-p105">手順 1 です。電子メールのメッセージ ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-p105">Step 1. Obtain the Message ID of the email</span></span>

<span data-ttu-id="7ba6f-p106">暗号化されたメールを取り消すことができる前に、メールのメッセージ ID を収集する必要があります。メッセージ Id は、通常の形式。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-p106">Before you can revoke an encrypted mail you need to gather the Message ID of the mail. The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="7ba6f-p107">無効にする電子メールのメッセージ ID を検索する複数の方法があります。いくつかのオプションの説明ですが、ID を提供する任意のメソッドを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-p107">There are multiple ways to find the Message ID of the email that you want to revoke. This section describes a couple of options, but you can use any method that provides the ID.</span></span>

  #### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="7ba6f-128">セキュリティ メッセージのトレースを使用して無効に電子メールのメッセージ ID を識別する&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="7ba6f-128">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="7ba6f-129">送信者または受信者が[Office 365 のセキュリティとコンプライアンス センターに新しいメッセージのトレース](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)を使用して電子メールを検索します。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-129">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>
2. <span data-ttu-id="7ba6f-p108">見つけた後、電子メールは**メッセージのトレースの詳細**ペインを表示を選択します。メッセージ ID を検索するのには**詳細情報**を展開します。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-p108">Once you've located the email select it to bring up the **Message trace details** pane. Expand **More Information** to locate the Message ID.</span></span>

  #### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="7ba6f-132">セキュリティで Office のメッセージの暗号化のレポートを使用して解除しメールのメッセージ ID を識別する&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="7ba6f-132">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>
1. <span data-ttu-id="7ba6f-133">セキュリティ&amp;コンプライアンス センターでは、**メッセージの暗号化のレポート**に移動します。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-133">In the Security &amp; Compliance Center, navigate to the **Message Encryption Report**.</span></span>
2. <span data-ttu-id="7ba6f-134">**詳細を表示する**テーブルを選択し、無効にするメッセージを識別します。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-134">Choose the **View details** table and identify the message that you want to revoke.</span></span> 
3. <span data-ttu-id="7ba6f-135">メッセージ ID を含む詳細を表示するメッセージをダブルクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-135">Double-click the message to view details that include the Message ID.</span></span> 

### <a name="step-2-revoke-the-mail"></a><span data-ttu-id="7ba6f-p109">手順 2 です。メールを取り消す</span><span class="sxs-lookup"><span data-stu-id="7ba6f-p109">Step 2. Revoke the mail</span></span>  

<span data-ttu-id="7ba6f-138">無効に電子メールのメッセージ ID がわかったら、セット OMEMessageRevocation コマンドレットを使用して電子メールを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-138">Once you know the Message ID of the email you want to revoke, you can revoke the email by using the Set-OMEMessageRevocation cmdlet.</span></span> 

1. <span data-ttu-id="7ba6f-139">[オンライン リモート PowerShell を使用して Exchange に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-139">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="7ba6f-140">とおりセット OMEMessageRevocation コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-140">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>
    
    ```
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```  

3. <span data-ttu-id="7ba6f-141">電子メールが無効になっているかどうかを確認するには、次のように Get OMEMessageStatus コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-141">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>
    
    ```
    Get-OMEMessageStatus -MessageId "<messageId>"
    ```  
    <span data-ttu-id="7ba6f-142">取り消しが成功した場合、コマンドレットは、次の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="7ba6f-142">If revocation was successful, the cmdlet returns the following result:</span></span>  

    ```The encrypted email with the subject "<subject>" and Message ID "<messageId>" was successfully revoked.```
