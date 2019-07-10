---
title: Office 365 へのメール送信
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/09/2016
audience: ITPro
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f9d4b5b6-8f4c-44df-9b06-2f9b3058ca20
ms.collection:
- M365-security-compliance
description: これらの記事は、外部の送信者が自身の評価や Office 365 のユーザーにメールを送信する能力を高めるために役立ちます。また、Office 365 ユーザーでない場合であっても、迷惑メールとフィッシング行為を報告する方法に関する情報も提供します。
ms.openlocfilehash: 6ccc3a087ae0142081369592d79601102b3942d9
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600473"
---
# <a name="sending-mail-to-office-365"></a><span data-ttu-id="59bce-104">Office 365 へのメール送信</span><span class="sxs-lookup"><span data-stu-id="59bce-104">Sending mail to Office 365</span></span>

<span data-ttu-id="59bce-p102">これらの記事は、外部の送信者が自身の評価や Office 365 のユーザーにメールを送信する能力を高めるために役立ちます。また、Office 365 ユーザーでない場合であっても、迷惑メールとフィッシング行為を報告する方法に関する情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="59bce-p102">These articles help external senders improve their reputation and increase their ability to deliver email to users in Office 365. They also provide some information about how you can report junk email and phishing attempts even if you aren't an Office 365 user yourself.</span></span>
  
<span data-ttu-id="59bce-107">Office 365 を利用していないが、Office 365 内のユーザーにメールを送信しようとする場合、この記事の情報は役立ちます。</span><span class="sxs-lookup"><span data-stu-id="59bce-107">If you are not an Office 365 customer, but are trying to send mail to someone in who is, you are in the right place.</span></span> <span data-ttu-id="59bce-108">Office 365 の管理者であり、スパムへの対処に関してサポートが必要な場合は、このセクションの情報は当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="59bce-108">If you are an Office 365 administrator and you need help fighting spam, this is not the right section for you.</span></span> <span data-ttu-id="59bce-109">代わりに、[Anti-spam and anti-malware protection](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="59bce-109">Instead, go to [Anti-spam and anti-malware protection](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx).</span></span>
  
|<span data-ttu-id="59bce-110">**以下についての関連情報...**</span><span class="sxs-lookup"><span data-stu-id="59bce-110">**For information about...**</span></span>|<span data-ttu-id="59bce-111">**参照...**</span><span class="sxs-lookup"><span data-stu-id="59bce-111">**See...**</span></span>|
|:-----|:-----|
|<span data-ttu-id="59bce-112">個別のメールやバルク メールを Office 365 ユーザーに送信するメール システムの管理者に対して提供するサービス。</span><span class="sxs-lookup"><span data-stu-id="59bce-112">Services we provide to administrators of email systems that are sending individual and bulk email to Office 365 customers.</span></span>  <br/> |[<span data-ttu-id="59bce-113">Office 365 にメールを送信するユーザー以外に対するサービス</span><span class="sxs-lookup"><span data-stu-id="59bce-113">Services for non-customers sending mail to Office 365</span></span>](services-for-non-customers.md) <br/> |
|<span data-ttu-id="59bce-p104">Office 365 ユーザーへのメールの配信に関する問題の解決方法。Office 365 の受信者にバルク メールを送信するためのベスト プラクティス。</span><span class="sxs-lookup"><span data-stu-id="59bce-p104">How to fix problems reaching customers in Office 365 through email. Best practices for sending bulk mail to Office 365 recipients.</span></span>  <br/> |[<span data-ttu-id="59bce-116">Office 365 に送信されるメールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="59bce-116">Troubleshooting mail sent to Office 365</span></span>](troubleshooting-mail-sent-to-office-365.md) <br/> |
|<span data-ttu-id="59bce-117">Office 365 において、フィッシングやスプーフィング メールなどの迷惑メールがユーザーに送信されないようにする方法。</span><span class="sxs-lookup"><span data-stu-id="59bce-117">How Office 365 prevent junk email, including phishing and spoofing email, from being sent to our customers.</span></span>  <br/> |[<span data-ttu-id="59bce-118">Office 365 に送信される迷惑メールへの対処</span><span class="sxs-lookup"><span data-stu-id="59bce-118">Fighting junk email sent to Office 365</span></span>](fighting-junk-email.md) <br/> |
|<span data-ttu-id="59bce-p105">Office 365 ユーザーにメールを送信する管理者が、スパム対策ポリシーに従ってメールがブロックされるのを回避する方法。これは、理解しておく必要のある法的事項です。</span><span class="sxs-lookup"><span data-stu-id="59bce-p105">How you, an administrator sending email to Office 365 customers, can avoid having email blocked by adhering to our anti-spam policies. This is the legal stuff you need to know.</span></span>  <br/> |[<span data-ttu-id="59bce-121">リファレンス:ポリシー、プラクティス、ガイドライン</span><span class="sxs-lookup"><span data-stu-id="59bce-121">Reference: Policies, practices, and guidelines</span></span>](reference-policies-practices-and-guidelines.md) <br/> |
   

