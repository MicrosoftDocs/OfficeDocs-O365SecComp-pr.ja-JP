---
title: 送信者が送信スパムの送信をブロックされる場合の通知例
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: 送信スパムを送信しようとしたために送信者がサービスからブロックされる場合、「送信スパム ポリシーを構成する」で指定したドメイン管理者は、次のような通知の電子メールを受信します。
ms.openlocfilehash: 04d8bde8e9cadd3525191a5bee7d368229e85056
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260975"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a><span data-ttu-id="2599e-103">送信者が送信スパムの送信をブロックされる場合の通知例</span><span class="sxs-lookup"><span data-stu-id="2599e-103">Sample notification when a sender is blocked sending outbound spam</span></span>

<span data-ttu-id="2599e-104">送信スパムを送信しようとしたために送信者がサービスからブロックされる場合、「[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)」で指定したドメイン管理者は、次のような通知の電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="2599e-104">When a sender is blocked from the service due to sending outbound spam, the domain admin specified when you [Configure the outbound spam policy](configure-the-outbound-spam-policy.md) will receive a notification email similar to the following:</span></span> 
  
 <span data-ttu-id="2599e-105">**送信者アドレス:** spamalerts@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2599e-105">**Sender address:** spamalerts@microsoft.com</span></span> 
  
 <span data-ttu-id="2599e-106">**件名:** 送信スパムの通知 - \<  *account name*  \> の送信メールの送信がブロックされました</span><span class="sxs-lookup"><span data-stu-id="2599e-106">**Subject:** Outbound spam notification - \<  *account name*  \> blocked from sending outbound mail</span></span> 
  
 <span data-ttu-id="2599e-107">**本文:** これは、Exchange Online Protection スパム分析システムからの自動応答です。</span><span class="sxs-lookup"><span data-stu-id="2599e-107">**Body:** This is an automated reply from the Exchange Online Protection Spam Analysis System.</span></span> 
  
<span data-ttu-id="2599e-p101">あなたの組織を発信元とする、スパムとしてマークされた大量の電子メールまたはその他の疑わしい動作が検出されたたため、連絡しました。以下の電子メール アカウントは、電子メールの送信が禁止されています (電子メールの受信は可能です)。</span><span class="sxs-lookup"><span data-stu-id="2599e-p101">You are being contacted because we have detected high volumes of email marked as spam, or other suspicious behavior, originating from your organization. The following email accounts have been blocked from sending email (they can still receive email):</span></span>
  
<span data-ttu-id="2599e-110">\< *アカウント名*  \></span><span class="sxs-lookup"><span data-stu-id="2599e-110">\< *account name*  \></span></span> 
  
<span data-ttu-id="2599e-p102">この電子メール アカウントが侵害されている可能性があります。次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="2599e-p102">It is likely that this email account has been compromised. Please follow these steps:</span></span>
  
1. <span data-ttu-id="2599e-113">以下のことを実行して、この問題をご自分で解決します。</span><span class="sxs-lookup"><span data-stu-id="2599e-113">Resolve this issue on your side by:</span></span>
    
  - <span data-ttu-id="2599e-114">アカウントのパスワードを変更する。</span><span class="sxs-lookup"><span data-stu-id="2599e-114">Changing the password of the account.</span></span>
    
  - <span data-ttu-id="2599e-115">アカウントがどのように侵害されたかを確認する。</span><span class="sxs-lookup"><span data-stu-id="2599e-115">Determining how the account was compromised.</span></span>
    
  - <span data-ttu-id="2599e-116">この脆弱性が再び悪用されないようにするための予防策を講じる。</span><span class="sxs-lookup"><span data-stu-id="2599e-116">Taking precautions to ensure that this vulnerability will not be exploited again.</span></span>
    
  - <span data-ttu-id="2599e-117">送信メールのキューから、問題のあるメッセージがすべて消去されていることを確認する。</span><span class="sxs-lookup"><span data-stu-id="2599e-117">Confirming that your outbound mail queue has been cleared of all offending messages.</span></span>
    
2. <span data-ttu-id="2599e-118">通常の連絡手段を使用して Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="2599e-118">Contact Microsoft support by using your regular contact channel.</span></span>
    
3. <span data-ttu-id="2599e-119">メールの送信がブロックされているユーザーがいること、また問題が処理されたことを説明します。</span><span class="sxs-lookup"><span data-stu-id="2599e-119">Explain that you have a user that is blocked from sending mail and that the problem has been dealt with.</span></span>
    
4. <span data-ttu-id="2599e-120">エージェントは、提供された情報でサポート チケットを作成し、当該の電子メール アドレスまたはドメインのブロックが解除されるようにそのチケットをエスカレートします。</span><span class="sxs-lookup"><span data-stu-id="2599e-120">The agent will create a support ticket with the information that you provide and escalate it to have the email address or domain unblocked.</span></span>
    
5. <span data-ttu-id="2599e-121">アドレスのブロックが解除され、保留中の他の問題がなくなると、連絡があり、ブロック解除に関する通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2599e-121">After the address has been unblocked, and pending no other issues, you will be contacted and alerted to the unblocking.</span></span>
    
<span data-ttu-id="2599e-122">迷惑メールを制御することにご協力いただき、ありがとうございました。</span><span class="sxs-lookup"><span data-stu-id="2599e-122">Thank you for assisting us in controlling unwanted email.</span></span>
  
<span data-ttu-id="2599e-123">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2599e-123">Exchange Online Protection.</span></span>
  
<span data-ttu-id="2599e-124">\*\*注意: この電子メールは監視されていないアドレスから送信されているため、このメールには返信しないでください\*\*</span><span class="sxs-lookup"><span data-stu-id="2599e-124">\*\*NOTE - Please do not respond to this email as it is sent from an unmonitored address\*\*</span></span>
  
> [!TIP]
> <span data-ttu-id="2599e-125">「 [Help and support for EOP](eop/help-and-support-for-eop.md)」に記載されているオプションを使用してサポートに連絡することもできます。</span><span class="sxs-lookup"><span data-stu-id="2599e-125">You can also contact support via the options documented at [Help and support for EOP](eop/help-and-support-for-eop.md).</span></span> 
  

