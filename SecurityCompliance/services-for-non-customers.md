---
title: Office 365 にメールを送信するユーザー以外に対するサービス
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/2/2016
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 電子メールをユーザーが安心して使用できるようにするため、Microsoft は各種ポリシーやテクノロジを用いて、ユーザーを保護しています。
ms.openlocfilehash: 868f5491ae9433e115090567b40abcd39ef2ebf8
ms.sourcegitcommit: 5eb664b6ecef94aef4018a75684ee4ae66c486bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "30492796"
---
# <a name="services-for-non-customers-sending-mail-to-office-365"></a><span data-ttu-id="a31cb-103">Office 365 にメールを送信するユーザー以外に対するサービス</span><span class="sxs-lookup"><span data-stu-id="a31cb-103">Services for non-customers sending mail to Office 365</span></span>
  
<span data-ttu-id="a31cb-p101">電子メールの不正使用、迷惑メール、詐欺メール (フィッシング詐欺) は、引き続き電子メール エコシステム全体にとって負担となっています。電子メールをユーザーが安心して使用できるようにするため、Microsoft は各種ポリシーやテクノロジを用いて、ユーザーを保護しています。ただし、正当な電子メールが不利を被らないようにするべきであることも理解しています。そのため、送信者が送信評価をプロアクティブに管理して、Office 365 ユーザーに電子メールを配信する機能の向上を支援する一連のサービスを確立してきました。</span><span class="sxs-lookup"><span data-stu-id="a31cb-p101">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem. To help maintain user trust in the use of email, Microsoft has put in place various policies and technologies to help protect our users. However, Microsoft understands that legitimate email should not be negatively affected. Therefore, we have established a suite of services to help senders improve their ability to deliver email to Office 365 users by proactively managing their sending reputation.</span></span>
  
<span data-ttu-id="a31cb-108">Office 365 ユーザーではなくても組織に利点があります。その概要を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a31cb-108">This overview provides information about benefits we provide to your organization even if you aren't an Office 365 customer.</span></span>
  
## <a name="sender-solutions"></a><span data-ttu-id="a31cb-109">送信者のソリューション</span><span class="sxs-lookup"><span data-stu-id="a31cb-109">Sender solutions</span></span>
<span data-ttu-id="a31cb-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="a31cb-110"></span></span>

|<span data-ttu-id="a31cb-111">**サービス**</span><span class="sxs-lookup"><span data-stu-id="a31cb-111">**Service**</span></span>|<span data-ttu-id="a31cb-112">**利点**</span><span class="sxs-lookup"><span data-stu-id="a31cb-112">**Benefits**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a31cb-113">このオンライン ヘルプ コンテンツ</span><span class="sxs-lookup"><span data-stu-id="a31cb-113">This online help content</span></span>  <br/> | <span data-ttu-id="a31cb-114">提供内容：</span><span class="sxs-lookup"><span data-stu-id="a31cb-114">Provides:</span></span>  <br/>  <span data-ttu-id="a31cb-115">EOP ユーザーへの通信の配信に関する質問の起点</span><span class="sxs-lookup"><span data-stu-id="a31cb-115">A starting point for any questions related to delivering communications to EOP users</span></span>  <br/>  <span data-ttu-id="a31cb-116">Microsoft のポリシーと要件が記載された簡単なオンライン ガイドが含まれる</span><span class="sxs-lookup"><span data-stu-id="a31cb-116">Includes a simple online guide with our policies and requirements</span></span>  <br/>  <span data-ttu-id="a31cb-117">Microsoft によって導入されている迷惑メール フィルターと認証テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="a31cb-117">An overview of the junk email filters and authentication technologies employed by Microsoft</span></span>  <br/> |
|[<span data-ttu-id="a31cb-118">Microsoft サポート</span><span class="sxs-lookup"><span data-stu-id="a31cb-118">Microsoft support</span></span>](services-for-non-customers.md#AboutSupport) <br/> |<span data-ttu-id="a31cb-119">配信の問題に対するセルフヘルプと充実したサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="a31cb-119">Provides self-help and escalation support for delivery issues.</span></span>  <br/> |
|[<span data-ttu-id="a31cb-120">Office 365 スパム対策用 IP リストから除外ポータル</span><span class="sxs-lookup"><span data-stu-id="a31cb-120">Office 365 Anti-Spam IP Delist Portal</span></span>](services-for-non-customers.md#DelistPortal) <br/> |<span data-ttu-id="a31cb-p102">IP リストからの除外要求を送信するためのツール。この要求を送信する前に、送信者は、疑わしい IP から不正なメールや悪意のあるメールが送信されないことを確認する責任があります。</span><span class="sxs-lookup"><span data-stu-id="a31cb-p102">A tool to submit IP delist request. Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>  <br/> |
|[<span data-ttu-id="a31cb-123">Exchange Online からの迷惑メールの不正使用とスパムの報告</span><span class="sxs-lookup"><span data-stu-id="a31cb-123">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](services-for-non-customers.md#ReportOurJunk) <br/> |<span data-ttu-id="a31cb-124">スパムや他の望ましくないメールが Exchange Online から送信されたり、インターネットや電子メール システムが混乱したりしないようにします。</span><span class="sxs-lookup"><span data-stu-id="a31cb-124">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the Internet and your mail system.</span></span>  <br/> |
   
## <a name="microsoft-support"></a><span data-ttu-id="a31cb-125">Microsoft サポート</span><span class="sxs-lookup"><span data-stu-id="a31cb-125">Microsoft support</span></span>
<span data-ttu-id="a31cb-126"><a name="AboutSupport"> </a></span><span class="sxs-lookup"><span data-stu-id="a31cb-126"></span></span>

<span data-ttu-id="a31cb-p103">Microsoft は、Office 365 受信トレイに電子メールを送信するユーザーのためにいくつかのサポート オプションを提供しています。次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a31cb-p103">Microsoft offers several support options for people having trouble sending mail to Office 365 inboxes. We recommend that you:</span></span>
  
- <span data-ttu-id="a31cb-129">受信するあらゆる配信不能レポートの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="a31cb-129">Follow the instructions in any non-delivery report you receive.</span></span>
    
- <span data-ttu-id="a31cb-130">「[Office 365 に送信されるメールのトラブルシューティング](troubleshooting-mail-sent-to-office-365.md)」で、ユーザー以外が経験する一般的な問題について確認します。</span><span class="sxs-lookup"><span data-stu-id="a31cb-130">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>
    
- <span data-ttu-id="a31cb-131">[Office 365 のリストから除外ポータル](https://sender.office.com)を使用して、ご使用の IP を、ブロックされる送信者リストから除外する要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="a31cb-131">Use the [Office 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span> 
    
- <span data-ttu-id="a31cb-132">[Microsoft コミュニティ フォーラム](https://community.office365.com/en-us/f/)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a31cb-132">Read the [Microsoft community forums](https://community.office365.com/en-us/f/).</span></span>
    
- <span data-ttu-id="a31cb-p104">電子メールを送信しようとしている Office 365 ユーザーに別の方法で連絡と取り、Microsoft サポートに連絡して自分の代わりにサポート チケットをオープンするよう依頼します。場合によっては、Microsoft サポートは法的な理由から、ブロックされている IP 領域を所有している送信者と直接やり取りする必要が生じます。ただし通常は、ユーザー以外はサポート チケットをオープンできません。</span><span class="sxs-lookup"><span data-stu-id="a31cb-p104">Contact the Office 365 customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf. In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked. However, non-customers typically can't open support tickets.</span></span>
    
     <span data-ttu-id="a31cb-136">Office 365 の Microsoft 製品サポートについて詳しくは、「 [サポート](https://technet.microsoft.com/library/office-365-support.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a31cb-136">For more information about Microsoft Technical support for Office 365, see [Support](https://technet.microsoft.com/library/office-365-support.aspx).</span></span>
    
## <a name="office-365-anti-spam-ip-delist-portal"></a><span data-ttu-id="a31cb-137">Office 365 スパム対策用 IP リストから除外ポータル</span><span class="sxs-lookup"><span data-stu-id="a31cb-137">Office 365 Anti-Spam IP Delist Portal</span></span>
<span data-ttu-id="a31cb-138"><a name="DelistPortal"> </a></span><span class="sxs-lookup"><span data-stu-id="a31cb-138"></span></span>

<span data-ttu-id="a31cb-p105">これは、自分自身を Office 365 でブロックされている送信者リストから除外するために使用できるセルフサービス ポータルです。このポータルは、Office 365 に電子メール アドレスがある受信者に電子メールを送信するとエラー・メッセージを受け取るものの、エラーではないと思われる場合に使用します。詳細については、「[リストから除外のポータルを使って、Office 365 の受信拒否リストから自分自身を削除する](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a31cb-p105">This is a self-service portal you can use to remove yourself from the Office 365 blocked senders list. Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Office 365 and you don't think you should be. For more information, see [Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>
  
## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="a31cb-142">Exchange Online からの迷惑メールの不正使用とスパムの報告</span><span class="sxs-lookup"><span data-stu-id="a31cb-142">Abuse and spam reporting for junk email originating from Exchange Online</span></span>
<span data-ttu-id="a31cb-143"><a name="ReportOurJunk"> </a></span><span class="sxs-lookup"><span data-stu-id="a31cb-143"></span></span>

<span data-ttu-id="a31cb-144">ある場合、当社の使用条件およびポリシーに違反した迷惑メールをサード パーティーが送信するのに Office 365 が使用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="a31cb-144">Sometimes Office 365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="a31cb-145">Office 365 から迷惑メールを受信する場合、そうしたメッセージに関して [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) に報告できます。</span><span class="sxs-lookup"><span data-stu-id="a31cb-145">If you receive any junk email from Office 365, you can report these messages to [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com).</span></span> <span data-ttu-id="a31cb-146">RFC 5322 や ARF 形式でメッセージ ヘッダー全体を含め、問題のあるメッセージを添付してください。</span><span class="sxs-lookup"><span data-stu-id="a31cb-146">Please attach the offending messages, including the full message header, in RFC 5322 or ARF format.</span></span> <span data-ttu-id="a31cb-147">Outlook on the web ユーザーは、組み込みツールを使用して迷惑メールを報告できます。</span><span class="sxs-lookup"><span data-stu-id="a31cb-147">Outlook on the web users can use built-in tools to report junk email.</span></span> <span data-ttu-id="a31cb-148">詳細については、「 [Outlook on the web で迷惑メールとフィッシング詐欺を報告する](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a31cb-148">For information, see [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span>
  

