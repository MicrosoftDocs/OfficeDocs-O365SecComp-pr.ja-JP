---
title: チュートリアルなりすましインテリジェンスの把握
ms.author: krowley
author: kccross
ms.date: 7/30/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
description: 新しいなりすましインテリジェンス情報を得ることがどのように動作を参照してください。
ms.openlocfilehash: ca9c4ae6f2d65ef2700a2e02acd5b4f1dfbfe903
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22596096"
---
# <a name="walkthrough-spoof-intelligence-insight"></a><span data-ttu-id="a0f08-103">チュートリアル: スプーフィング インテリジェンスの把握</span><span class="sxs-lookup"><span data-stu-id="a0f08-103">Walkthrough: spoof intelligence insight</span></span>

<span data-ttu-id="a0f08-p101">なりすましインテリジェンス情報を得ることを使用すると、する送信者は正当に送信する電子メールが認証されていない場合をすばやく確認できます。スプーフィングされたメッセージを送信することを許可するには、ユーザーに、誤検知のリスクを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p101">By using the Spoof Intelligence insight, you can quickly determine which senders are legitimately sending you unauthenticated email. By permitting them to send spoofed messages, you can reduce the risk of any false positives going to your users.</span></span>
  
<span data-ttu-id="a0f08-106">さらもスプーフィング インテリジェンスのモニターを使用して許可されているドメイン ・ セキュリティの追加レイヤーを提供し、安全でないメッセージが組織に着信するを防止するペアを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a0f08-106">In addition, you can also use Spoof Intelligence monitor and manage permitted domain-pairs to provide an additional layer of security and prevent unsafe messages from arriving in your organization.</span></span>
  
<span data-ttu-id="a0f08-p102">なりすましインテリジェンス情報を得ることを使用するには、セキュリティで&amp;コンプライアンス センターの場合は、Office 365 のグローバル管理者、セキュリティ管理者、またはセキュリティの読み取りアクセス許可に、職場、学校のアカウントが与えられています。詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p102">You can use the spoof intelligence insight in the Security &amp; Compliance Center if your work or school account has been given Office 365 global administrator, security administrator, or security reader permissions. For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="a0f08-109">経験がない場合に[のレポートと Office 365 のセキュリティ情報&amp;コンプライアンス センター](reports-and-insights-in-security-and-compliance.md)、移動する方法が簡単にダッシュ ボードから把握するを参照してくださいに役立つ場合があり、推奨される操作です。</span><span class="sxs-lookup"><span data-stu-id="a0f08-109">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span>
  
<span data-ttu-id="a0f08-p103">複数のダッシュ ボードからなりすましインテリジェンス情報を得ることを表示するには、セキュリティで&amp;コンプライアンス センターです。ダッシュ ボードを探しているに関係なく情報を得ることは詳細情報を提供し、同じタスクをすばやく実行することができます。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p103">You can view the spoof intelligence insight from more than one dashboard in the Security &amp; Compliance Center. Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>
  
<span data-ttu-id="a0f08-p104">これは、セキュリティのいくつかのチュートリアルのいずれかの&amp;コンプライアンス センターです。レポートと情報の移動については、"関連項目"のセクションのチュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p104">This is one of several walkthroughs for the Security &amp; Compliance Center. To about navigating reports and insights, see the walkthroughs in the Related topics section.</span></span>
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a><span data-ttu-id="a0f08-114">スプーフィング セキュリティ インテリジェンス情報を得ることに&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="a0f08-114">Getting to the spoof intelligence insight in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="a0f08-115">開始する必要があります[セキュリティを参照して&amp;コンプライアンス センター](go-to-the-securitycompliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="a0f08-115">To get started, you'll need [go to the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="a0f08-116">セキュリティ&amp;コンプライアンス センターでは、**脅威の管理**に移動\>**ダッシュ ボードです**。</span><span class="sxs-lookup"><span data-stu-id="a0f08-116">In the Security &amp; Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>
    
3. <span data-ttu-id="a0f08-p105">**情報**の行で、スプーフィング インテリジェンス情報を得ることを探します。スプーフィングのインテリジェンスを有効にしたかどうかは、情報を得ることが受けることのできる**Spoofed ドメインが過去 30 日間の認証に失敗しました**。スプーフィングの保護を有効にしていない場合、情報を得ることが表示されますタイトルの**なりすまし保護の有効化**を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p105">In the **Insights** row, look for the spoof intelligence insight. If you have enabled spoof intelligence, then the insight is entitled **Spoofed domains that failed authentication of the past 30 days**. If you haven't enabled spoof protection, then the insight will prompt you to do so by using the title **Enable Spoof Protection**.</span></span> 
    
## <a name="about-the-insight-on-the-dashboard"></a><span data-ttu-id="a0f08-120">ダッシュ ボードの情報を得ることについて</span><span class="sxs-lookup"><span data-stu-id="a0f08-120">About the insight on the dashboard</span></span>

<span data-ttu-id="a0f08-121">ダッシュ ボードの情報を得ることは、次のような情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="a0f08-121">The insight on the dashboard shows you information like this.</span></span>
  
![なりすましインテリジェンス情報のスクリーン ショット](media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
<span data-ttu-id="a0f08-123">この見解には、2 つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="a0f08-123">This insight has two modes:</span></span>
  
 <span data-ttu-id="a0f08-p106">**把握モード**です。スプーフィングのポリシーが有効にした場合、情報を得ることを示して メールの数は過去 30 日間、なりすましのインテリジェンス機能によって影響を受けた。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p106">**Insight mode**. If you have any spoof policy enabled, then the insight shows you how many mails were impacted by our spoof intelligence capabilities over the past 30 days.</span></span> 
  
 <span data-ttu-id="a0f08-p107">**場合モード**。スプーフィングのポリシーが有効ではありません、し、情報を得ることが表示*は*メール数に影響された、スプーフィングのインテリジェンス機能、過去 30 日間されます。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p107">**What if mode**. If you do not have any spoof policy enabled, then the insight shows you how many mails  *would*  have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span> 
  
<span data-ttu-id="a0f08-p108">どちらにしても、表示情報を得ることで、スプーフィングされたドメインに分割 2 つのカテゴリです。不審なドメインのペアと不審ではないドメインの組み合わせです。これらのカテゴリはさらに確認するための 3 つの異なるバケットに分割します。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p108">Either way, the spoofed domains displayed in the insight are separated into two categories; suspicious domain pairs and non-suspicious domain pairs. These categories are further subdivided into three different buckets for you to review.</span></span> 
  
<span data-ttu-id="a0f08-130">*ドメインのペア*の組み合わせでは、"から:"アドレスと送信元のインフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="a0f08-130">A  *domain pair*  is a combination of the "From:" address and the sending infrastructure.</span></span> 
  
- <span data-ttu-id="a0f08-p109">"From"アドレスは、メール アプリケーションで元のアドレスとして表示されるアドレスです。このアドレスは、電子メールの作成者を識別します。ユーザーまたはメッセージの作成を担当するシステムのメールボックスは、します。5322.From アドレスとも呼びます。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p109">The "From" address is the address displayed as the From address by your mail application. This address identifies the author of the email. That is, the mailbox of the person or system responsible for writing the message. This is sometimes called the 5322.From address.</span></span>
    
- <span data-ttu-id="a0f08-p110">送信側のインフラストラクチャ、または、送信者は、送信元 IP アドレスの PTR レコードの組織ドメインです。送信元の IP アドレスは、PTR レコードを持たないかどうかは、送信者は、送信元 IP、255.255.255.0 と識別される CIDR 表記法でサブネット マスク (24)。などの IP アドレス 192.168.100.100 の場合、この送信者の完全な IP アドレスは 192.168.100.100/24 になります。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p110">The sending infrastructure, or sender, is the organizational domain of the PTR record of the sending IP address. If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24). For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>
    
 <span data-ttu-id="a0f08-138">**不審なドメインのペア**は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a0f08-138">**Suspicious domain pairs** include:</span></span> 
  
- <span data-ttu-id="a0f08-p111">**信頼性の高いスプーフ**します。Office 365 は、過去の送信のパターンと、ドメインの評価スコアに基づいてこれらのドメインでは、不審な強力な信号を受信しました。Office 365 は、ドメインは、なりすましが行われることと、これらのドメインから送信されたメッセージは、正当性を十分に信頼できます。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p111">**High-confidence spoof**. Office 365 received strong signals that these domains are suspicious, based on the historical sending patterns and the reputation score of the domains. Office 365 is highly confident that the domains are spoofing and that messages sent from these domains are less likely to be legitimate.</span></span> 
    
- <span data-ttu-id="a0f08-p112">**中程度の信頼度のなりすまし**。Office 365 は、送信側の過去のパターンと、ドメインの評価スコアに基づいてこれらのドメインでは、不審な場合は、中程度の信号を受信しました。Office 365 は、ドメインを偽装して、これらのドメインから送信されたメッセージは、正当なことを確実に中程度。このバケットには、信頼性の高いなりすましバケットよりも偽陽性 (FPs) が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p112">**Moderate confidence spoof**. Office 365 received moderate signals that these domains are suspicious, based on historical sending patterns and the reputation score of the domains. Office 365 is moderately confident that the domains are spoofing and that messages sent from these domains are legitimate. This bucket has a greater chance of containing false positives (FPs) than the high-confidence spoof bucket.</span></span> 
    
 <span data-ttu-id="a0f08-p113">**スプーフィングを救出****以外に不審なドメインのペア**が含まれています。修復されたスプーフィングは、( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing)、 [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) の明示的な認証チェックに失敗しましたが、拡張認証チェックにパスしているドメインです。このため、Office 365 は、ユーザーに代わってメールを救出し、メールでスプーフィング対策の処理は行われません。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p113">**Non-suspicious domain pairs** include **rescued spoof**. Rescued spoof are domains that have failed the explicit authentication checks ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) but passed our extended authentication checks. As a result of this, Office 365 rescued the mail on your behalf and no anti-spoofing action was taken on the mail.</span></span> 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="a0f08-149">なりすましインテリジェンス情報を得ることから不審なドメインのペアに関する詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a0f08-149">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="a0f08-150">なりすましインテリジェンス情報を得ること、任意のドメインのペア (高、中、または修復) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0f08-150">On the spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>
  
<span data-ttu-id="a0f08-p114">**なりすましインテリジェンスの情報**ページでは、あなたの組織に認証されていないメールを送信する送信者の一覧を表示するが表示されます。このページの情報では、かどうかのアクションを実行する必要がありますか、スプーフィングされたメッセージが承認されたかどうかを決定できます。などの情報は、メッセージ数、なりすましを行う可能性が検出された最後の日付を並べ替えることができます。(クリック**メッセージをカウントする**か、**最後に表示される**などの列見出しなど)。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p114">The **Spoof Intelligence Insight** page appears showing you a list of senders that are sending unauthenticated mail into your organization. The information on this page helps you determine whether spoofed messages are authorized or not or if you need to take further action. You can sort the information by message count, the date the spoof was last detected, and more. (Click column headings, such as **Message count** or **Last seen**, for example.)</span></span> 
    
2. <span data-ttu-id="a0f08-p115">ドメインの組み合わせに関するさまざまな情報を含む詳細情報ウィンドウを開くにテーブルで項目を選択、なぜ私たちを捕捉などに必要なものは、ドメインの概要を示し、送信者、および同じ送信者からのテナントであったと同様の電子メールに関する WhoIs のデータです。ここでは、追加または**AllowedToSpoof**差出人セーフ リスト] ボックスの一覧からドメインのペアを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p115">Select an item in the table to open a details pane that contains rich information about the domain pair, including why we caught this, what you need to do, a domain summary, WhoIs data about the sender, and similar emails we have seen in your tenant from the same sender. From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span> 
  
![ドメイン スプーフィング インテリジェンス情報の詳細ペインでのスクリーン ショット](media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a><span data-ttu-id="a0f08-158">追加または AllowedToSpoof 差出人セーフ リスト] ボックスの一覧からドメインを削除します。</span><span class="sxs-lookup"><span data-stu-id="a0f08-158">Add or remove a domain from the AllowedToSpoof safe sender list</span></span>

<span data-ttu-id="a0f08-p116">追加またはなりすましインテリジェンス情報を得ることの詳細ペインで、ドメインの組み合わせを確認するときに、AllowedToSpoof 安全な送信者の一覧からドメインを削除するとします。それに応じて、表示/非表示を設定するだけです。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p116">You add or remove a domain from the AllowedToSpoof safe sender list while reviewing the domain pair in the details pane of the spoof intelligence insight. Simply set the toggle accordingly.</span></span>
  
<span data-ttu-id="a0f08-p117">これは、スプーフィングされたドメインと送信側のインフラストラクチャの一意のドメインのペアの組み合わせを変更し、スプーフィングされたドメイン全体、または単独で送信側のインフラストラクチャに対するカバレッジを提供しません。たとえば、'AllowedToSpoof' の送信者に次のドメインのペアを追加する場合は、許可リスト:*ドメインのスプーフィング*"gmail.com"と*インフラストラクチャの送信*"tm*です。 mx.com」、* を偽装するのにはそのドメインのペアからのメールのみを許可するが。"Gmail.com"、およびその他のドメインを偽装しようとしてその他の送信者になりすましのインテリジェンスを保護する"tms.mx.com"しようとするスプーフィングを続けます。</span><span class="sxs-lookup"><span data-stu-id="a0f08-p117">This modifies the unique domain pair combination of the spoofed domain and the sending infrastructure and does not provide coverage for the entire spoofed domain or the sending infrastructure in isolation. For example, if you add the following domain pair to the 'AllowedToSpoof' sender allow list:  *Spoofed Domain*  "gmail.com" and  *Sending Infrastructure*  "tms  *.mx.com",*  then only mail from that domain pair will be allowed to spoof. Other senders attempting to spoof "gmail.com", and other domains that "tms.mx.com" attempt to spoof will continue to be protected by spoof intelligence.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="a0f08-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0f08-164">Related topics</span></span>

[<span data-ttu-id="a0f08-165">スプーフィング インテリジェンスの詳細情報</span><span class="sxs-lookup"><span data-stu-id="a0f08-165">Learn more about spoof intelligence</span></span>](learn-about-spoof-intelligence.md)
  
[<span data-ttu-id="a0f08-166">Office 365 でのスプーフィング対策保護</span><span class="sxs-lookup"><span data-stu-id="a0f08-166">Anti-spoofing protection in Office 365</span></span>](anti-spoofing-protection.md)
  
[<span data-ttu-id="a0f08-167">チュートリアル - ダッシュボードからインサイトへの移動</span><span class="sxs-lookup"><span data-stu-id="a0f08-167">Walkthrough - From a dashboard to an insight</span></span>](from-a-dashboard-to-an-insight.md)
  
[<span data-ttu-id="a0f08-168">チュートリアル - 詳細レポートからインサイトへの移動</span><span class="sxs-lookup"><span data-stu-id="a0f08-168">Walkthrough - From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  
[<span data-ttu-id="a0f08-169">チュートリアル - インサイトから詳細レポートへの移動</span><span class="sxs-lookup"><span data-stu-id="a0f08-169">Walkthrough - From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  

