---
title: バルク メール業者の差出人セーフ リストを管理する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: '差出人セーフ リストを使用する場合は、Exchange Online Protection (EOP) と Outlook で処理が異なることを認識しておく必要があります。サービスでは RFC 5321.MailFrom アドレスと RFC 5322.From アドレスを検査することによって信頼できる差出人とドメインを尊重するのに対して、Outlook では RFC 5322.From アドレスをユーザーの差出人セーフ リストに追加します (注 : サービスは、ブロックする差出人とドメインについては、5321.MailFrom アドレスと 5322.From アドレスの両方を検査します)。'
ms.openlocfilehash: 006c2b9520f1e1f71f5ec745baaf84f906f31eb4
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692876"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="31da6-105">バルク メール業者の差出人セーフ リストを管理する</span><span class="sxs-lookup"><span data-stu-id="31da6-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="31da6-106">差出人セーフリストを使用する場合は、Exchange Online Protection (EOP) と Outlook が異なる方法で処理することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="31da6-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="31da6-107">Office 365 サービスは、rfc 5321.mailfrom アドレスと rfc 5322.from from アドレスを検査することによって、安全な送信者とドメインを尊重しますが、Outlook は rfc 5322.from アドレスをユーザーの [差出人セーフリスト] に追加します。</span><span class="sxs-lookup"><span data-stu-id="31da6-107">The Office 365 service respects safe senders and domains by inspecting the RFC 5321.MailFrom address and the RFC 5322.From address, while Outlook adds the RFC 5322.From address to a user's safe sender list.</span></span> <span data-ttu-id="31da6-108">(注: サービスは、ブロックされた送信者とドメインの5321.mailfrom アドレスと5322.from アドレスの両方を調べます。)</span><span class="sxs-lookup"><span data-stu-id="31da6-108">(Note: The service inspects both the 5321.MailFrom address and 5322.From address for blocked senders and domains.)</span></span>
  
<span data-ttu-id="31da6-p103">RFC 5321.MailFrom アドレスとも呼ばれる SMTP MAIL FROM アドレスは、SPF チェックの実行に使用される電子メール アドレスで、メールが配信できない場合に返送されるメッセージが配信されるパスです。メッセージ ヘッダーの Return-Path に既定で配置されるのはこの電子メール アドレスですが、差出人は異なる Return-Path アドレスを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="31da6-p103">The SMTP MAIL FROM address, otherwise known as the RFC 5321.MailFrom address, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered. It's this email address that is placed into the Return-Path in the message headers by default, though it's possible for the sender to designate a different Return-Path address.</span></span>
  
<span data-ttu-id="31da6-111">RFC 5322.From アドレスとも呼ばれるメッセージ ヘッダー内の差出人アドレスは、Outlook などのメール クライアントに表示される電子メール アドレスです。</span><span class="sxs-lookup"><span data-stu-id="31da6-111">The From: address in the message headers, otherwise known as the RFC 5322.From address, is the email address that is displayed in the mail client such as Outlook.</span></span>
  
<span data-ttu-id="31da6-p104">大抵の場合、5321.MailFrom アドレスと 5322.From アドレスは同じです。このことは、人間同士のコミュニケーションではよく見られることです。ただし、他のユーザーに代わって電子メールが送信される場合は、これらのアドレスが異なるのが普通です。大部分のバルク メール メッセージでは、ほとんどの場合にそのようになります。</span><span class="sxs-lookup"><span data-stu-id="31da6-p104">Much of the time, the 5321.MailFrom and 5322.From addresses are the same. This is typical for person-to-person communication. However, when email is sent on behalf of someone else, the addresses are frequently different. This usually happens most often for bulk email messages.</span></span>
  
<span data-ttu-id="31da6-116">たとえば、Blue Yonder Airlines 航空が Margie's Travel に電子メール広告の配信を外注したとします。</span><span class="sxs-lookup"><span data-stu-id="31da6-116">For example, suppose that the airline Blue Yonder Airlines has contracted out Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="31da6-117">受信トレイに入るメッセージの差出人は blueyonder@news.blueyonderairlines.com です。</span><span class="sxs-lookup"><span data-stu-id="31da6-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="31da6-118">この例では、MailFrom address は blueyonder.airlines@margiestravel.com、blueyonder@news.blueyonderairlines.com は5321.mailfrom アドレスで、これは Outlook に表示されます。</span><span class="sxs-lookup"><span data-stu-id="31da6-118">In this case, 5321.MailFrom address is blueyonder.airlines@margiestravel.com, and blueyonder@news.blueyonderairlines.com is the 5322.From address which is the one, you see in Outlook.</span></span> <span data-ttu-id="31da6-119">このサービスは rfc 5322.from アドレスを尊重するため、このメッセージがフィルター処理されないようにするには、rfc 5322.from アドレスを Outlook (ユーザーとして)、または管理者が、スパム対策に示されているようにメールフロールールを設定している場合には、信頼できる差出人として登録します。 [保護](anti-spam-protection.md)] セクション</span><span class="sxs-lookup"><span data-stu-id="31da6-119">Because the service respects the RFC 5322.From address, to prevent this message from getting filtered, you can add the RFC 5322.From address as a safe sender in Outlook (as a user) or, if you're an administrator set up a mailflow rule as shown on the [Anti-spam Protection](anti-spam-protection.md) section.</span></span>
  

