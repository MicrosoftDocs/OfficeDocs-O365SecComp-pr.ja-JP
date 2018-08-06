---
title: Exchange Online の差出人セーフ リストと受信拒否リスト
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
description: Exchange Online または Exchange Online Protection (EOP) の管理者は、サービスを通過する電子メール メッセージがスパムとしてマークされないようにできます。そのための方法の 1 つに、組織内のユーザーの中で、信頼できる差出人とブロックする差出人のリストを作成する、というものがあります。
ms.openlocfilehash: fcb43f990750782788dc6f459dd5c7d296146a38
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22028084"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="63608-104">Exchange Online の差出人セーフ リストと受信拒否リスト</span><span class="sxs-lookup"><span data-stu-id="63608-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="63608-p102">Exchange Online または Exchange Online Protection (EOP) の管理者は、サービスを通過する電子メール メッセージがスパムとしてマークされないようにできます。そのための方法の 1 つに、組織内のユーザーの中で、信頼できる差出人とブロックする差出人のリストを作成する、というものがあります。</span><span class="sxs-lookup"><span data-stu-id="63608-p102">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam. One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span> 
  
 <span data-ttu-id="63608-107">*管理者としてこのリストで作業を行う方法のヒントと手順の更新されたバージョンについては、「* [EOP と Office 365 でメールが迷惑メールとして検出されないようにする](https://go.microsoft.com/fwlink/p/?LinkID=534224)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63608-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [Prevent false positive email marked as spam with a safelist or other techniques](https://go.microsoft.com/fwlink/p/?LinkID=534224).</span></span> 
  
<span data-ttu-id="63608-108">管理者でないユーザーが、信頼できる差出人のリストを使用して Outlook で迷惑メールを管理するだけの場合は、「[迷惑メール フィルターの概要](https://go.microsoft.com/fwlink/?LinkId=817222)」の手順をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="63608-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in this overview of [the Junk Email Filter](https://go.microsoft.com/fwlink/?LinkId=817222).</span></span> 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="63608-109">Exchange Online での信頼できる差出人とブロックする差出人の制限について</span><span class="sxs-lookup"><span data-stu-id="63608-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="63608-p103">Exchange Online での信頼できる差出人とブロックする差出人の制限は、Active Directory の制限や Outlook の制限と異なります。以下にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="63608-p103">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits. They are:</span></span>
  
- <span data-ttu-id="63608-112">差出人セーフ リストの制限: 1,024</span><span class="sxs-lookup"><span data-stu-id="63608-112">Safe sender limit: 1,024</span></span>
    
- <span data-ttu-id="63608-113">ブロックする差出人の制限: 500</span><span class="sxs-lookup"><span data-stu-id="63608-113">Blocked sender limit: 500</span></span>
    
<span data-ttu-id="63608-114">注:</span><span class="sxs-lookup"><span data-stu-id="63608-114">Note:</span></span>
  
<span data-ttu-id="63608-p104">KB 2590466 (「Outlook Web App for Exchange Server 2010 で「迷惑メールの検証エラー」を受信する」) で説明するエラーが発生することがあります。この問題を解決するには、「自分の連絡先からのメールを信頼する」チェック ボックスをオフにします。あるいは、既定の連絡先フォルダーに含まれている電子メール アドレスの数を、Exchange Online の制限である 1,024 以下に減らします。この制限は 「MaxSafeSenders」属性で設定されています。この属性と Set-Mailbox コマンドレットの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63608-p104">You may experience the error that is described in KB 2590466 ("You receive the error "Junk e-mail validation error" in Outlook Web App for Exchange Server 2010"). To resolve this issue, clear the "Trust emails from my contacts" check box. Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1,024 in Exchange Online that is set for "MaxSafeSenders" attribute. For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>
  
[<span data-ttu-id="63608-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="63608-119">Set-Mailbox</span></span>](https://docs.microsoft.com/en-us/powershell/module/exchange/mailboxes/Set-Mailbox?view=exchange-ps)
  
## <a name="see-also"></a><span data-ttu-id="63608-120">See also</span><span class="sxs-lookup"><span data-stu-id="63608-120">See also</span></span>

[<span data-ttu-id="63608-121">Sender filtering in Exchange 2016</span><span class="sxs-lookup"><span data-stu-id="63608-121">Sender filtering in Exchange 2016</span></span>](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)

