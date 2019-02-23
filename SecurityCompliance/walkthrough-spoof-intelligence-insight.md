---
title: チュートリアルのスプーフィングインテリジェンスの洞察
ms.author: krowley
author: kccross
ms.date: 7/30/2018
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
description: 新しいスプーフィングインテリジェンスの理解のしくみを参照してください。
ms.openlocfilehash: 83fa1580a0e7c4717581cc5f23b8f525d6b918e0
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220327"
---
# <a name="walkthrough-spoof-intelligence-insight"></a><span data-ttu-id="cf988-103">チュートリアル: スプーフィングインテリジェンスの洞察</span><span class="sxs-lookup"><span data-stu-id="cf988-103">Walkthrough: spoof intelligence insight</span></span>

<span data-ttu-id="cf988-p101">スプーフィングインテリジェンスによる洞察を使用して、認証されていない電子メールを正当に送信している送信者をすばやく判断できます。スプーフィングされたメッセージの送信を許可することにより、ユーザーが誤検知を行うリスクを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="cf988-p101">By using the Spoof Intelligence insight, you can quickly determine which senders are legitimately sending you unauthenticated email. By permitting them to send spoofed messages, you can reduce the risk of any false positives going to your users.</span></span>
  
<span data-ttu-id="cf988-106">さらに、スプーフィングインテリジェンスモニターを使用して、許可されたドメインペアを管理することによって、セキュリティの追加の層を提供したり、安全でないメッセージが組織に到着しないようにしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cf988-106">In addition, you can also use Spoof Intelligence monitor and manage permitted domain-pairs to provide an additional layer of security and prevent unsafe messages from arriving in your organization.</span></span>
  
<span data-ttu-id="cf988-p102">職場または学校のアカウントに Office 365 の&amp;グローバル管理者、セキュリティ管理者、またはセキュリティ閲覧者のアクセス許可が付与されている場合は、セキュリティコンプライアンスセンターでスプーフィングインテリジェンスに関する洞察を得ることができます。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf988-p102">You can use the spoof intelligence insight in the Security &amp; Compliance Center if your work or school account has been given Office 365 global administrator, security administrator, or security reader permissions. For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="cf988-109">[Office 365 セキュリティ&amp;コンプライアンスセンターのレポートと洞察](reports-and-insights-in-security-and-compliance.md)を初めて使用する場合は、ダッシュボードから洞察や推奨されるアクションに簡単にアクセスする方法を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="cf988-109">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span>
  
<span data-ttu-id="cf988-p103">セキュリティ&amp; /コンプライアンスセンターでは、複数のダッシュボードからスプーフィングインテリジェンスの洞察を確認できます。どのダッシュボードを使用しているかに関係なく、洞察は同じ情報を提供し、同じタスクをすばやく実行することができます。</span><span class="sxs-lookup"><span data-stu-id="cf988-p103">You can view the spoof intelligence insight from more than one dashboard in the Security &amp; Compliance Center. Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>
  
<span data-ttu-id="cf988-p104">これは、セキュリティ&amp;コンプライアンスセンターのいくつかのチュートリアルの1つです。レポートと分析情報の移動については、「関連項目」セクションのチュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf988-p104">This is one of several walkthroughs for the Security &amp; Compliance Center. To about navigating reports and insights, see the walkthroughs in the Related topics section.</span></span>
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a><span data-ttu-id="cf988-114">セキュリティ&amp; /コンプライアンスセンターのスプーフィングインテリジェンスについての理解を得る</span><span class="sxs-lookup"><span data-stu-id="cf988-114">Getting to the spoof intelligence insight in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="cf988-115">開始するに[は、セキュリティ&amp;コンプライアンスセンターに移動](go-to-the-securitycompliance-center.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf988-115">To get started, you'll need [go to the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="cf988-116">セキュリティ&amp; /コンプライアンスセンターで、[**脅威管理** \> ] ダッシュボードに移動し**ます。**</span><span class="sxs-lookup"><span data-stu-id="cf988-116">In the Security &amp; Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>
    
3. <span data-ttu-id="cf988-p105">[ **Insights** ] 行で、スプーフィングインテリジェンスに関する洞察を探します。スプーフィングインテリジェンスを有効にしている場合、この洞察には**過去30日間の認証に失敗したスプーフィングドメインの**資格が与えられます。スプーフィングによる保護を有効にしていない場合は、[**スプーフィング保護を有効**にする] のタイトルを使用して、これを実行するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf988-p105">In the **Insights** row, look for the spoof intelligence insight. If you have enabled spoof intelligence, then the insight is entitled **Spoofed domains that failed authentication of the past 30 days**. If you haven't enabled spoof protection, then the insight will prompt you to do so by using the title **Enable Spoof Protection**.</span></span> 
    
## <a name="about-the-insight-on-the-dashboard"></a><span data-ttu-id="cf988-120">ダッシュボードの詳細について</span><span class="sxs-lookup"><span data-stu-id="cf988-120">About the insight on the dashboard</span></span>

<span data-ttu-id="cf988-121">ダッシュボードの洞察には、このような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf988-121">The insight on the dashboard shows you information like this.</span></span>
  
![スプーフィングインテリジェンスの洞察のスクリーンショット](media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
<span data-ttu-id="cf988-123">この洞察には、次の2つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="cf988-123">This insight has two modes:</span></span>
  
 <span data-ttu-id="cf988-p106">**洞察モード**。いずれかのスプーフィングポリシーを有効にしている場合は、過去30日間のスプーフィングインテリジェンス機能によって影響を受けたメールの数が洞察によって示されます。</span><span class="sxs-lookup"><span data-stu-id="cf988-p106">**Insight mode**. If you have any spoof policy enabled, then the insight shows you how many mails were impacted by our spoof intelligence capabilities over the past 30 days.</span></span> 
  
 <span data-ttu-id="cf988-p107">**if モードについ**てスプーフィングポリシーが有効になっていない場合は、過去30日間のスプーフィングインテリジェンス\*\* 機能によって影響を受けるメールの数が洞察に示されています。</span><span class="sxs-lookup"><span data-stu-id="cf988-p107">**What if mode**. If you do not have any spoof policy enabled, then the insight shows you how many mails  *would*  have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span> 
  
<span data-ttu-id="cf988-p108">どちらの方法でも、洞察に表示される偽装ドメインは2つのカテゴリに分かれています。疑わしいドメインの組と、不審でないドメインのペア。これらのカテゴリは、確認のために3つの異なるバケットにさらに細分化されています。</span><span class="sxs-lookup"><span data-stu-id="cf988-p108">Either way, the spoofed domains displayed in the insight are separated into two categories; suspicious domain pairs and non-suspicious domain pairs. These categories are further subdivided into three different buckets for you to review.</span></span> 
  
<span data-ttu-id="cf988-130">*ドメインペア*は、"From:" アドレスと送信元インフラストラクチャの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="cf988-130">A  *domain pair*  is a combination of the "From:" address and the sending infrastructure.</span></span> 
  
- <span data-ttu-id="cf988-p109">"差出人" アドレスは、メールアプリケーションによって差出人アドレスとして表示されるアドレスです。このアドレスは、電子メールの作成者を識別します。これは、メッセージの作成を担当するユーザーまたはシステムのメールボックスです。これは、5322.from アドレスと呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="cf988-p109">The "From" address is the address displayed as the From address by your mail application. This address identifies the author of the email. That is, the mailbox of the person or system responsible for writing the message. This is sometimes called the 5322.From address.</span></span>
    
- <span data-ttu-id="cf988-p110">送信元のインフラストラクチャ (送信者) は、送信元の IP アドレスの PTR レコードの組織ドメインです。送信元の ip アドレスに PTR レコードがない場合、送信元の ip アドレスは、CIDR 表記法 (/24) で255.255.255.0 サブネットマスクを使用して識別されます。たとえば、ip アドレスが192.168.100.100 の場合、送信者の完全な ip アドレスは 192.168.100.100/24 です。</span><span class="sxs-lookup"><span data-stu-id="cf988-p110">The sending infrastructure, or sender, is the organizational domain of the PTR record of the sending IP address. If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24). For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>
    
 <span data-ttu-id="cf988-138">**疑わしいドメインペア**は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cf988-138">**Suspicious domain pairs** include:</span></span> 
  
- <span data-ttu-id="cf988-p111">**信頼度の高いスプーフィング**。Office 365 は、履歴送信パターンおよびドメインの評価スコアに基づいて、これらのドメインが疑わしいという強力な信号を受信しました。Office 365 は、ドメインがスプーフィングされており、これらのドメインから送信されたメッセージが正当ではない可能性が高いことを確信しています。</span><span class="sxs-lookup"><span data-stu-id="cf988-p111">**High-confidence spoof**. Office 365 received strong signals that these domains are suspicious, based on the historical sending patterns and the reputation score of the domains. Office 365 is highly confident that the domains are spoofing and that messages sent from these domains are less likely to be legitimate.</span></span> 
    
- <span data-ttu-id="cf988-p112">**適度に信頼度**の高いスプーフィング。Office 365 は、履歴送信パターンおよびドメインの評価スコアに基づいて、これらのドメインが疑わしいという、中程度の信号を受信しました。Office 365 は、ドメインがスプーフィングされており、これらのドメインから送信されたメッセージが正当であることを適度に確信しています。このバケットは、信頼度の高いスプーフィングバケットよりも誤検知 (FPs) を含む可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="cf988-p112">**Moderate confidence spoof**. Office 365 received moderate signals that these domains are suspicious, based on historical sending patterns and the reputation score of the domains. Office 365 is moderately confident that the domains are spoofing and that messages sent from these domains are legitimate. This bucket has a greater chance of containing false positives (FPs) than the high-confidence spoof bucket.</span></span> 
    
 <span data-ttu-id="cf988-p113">**不審ではないドメインのペアに**は、 **rescued スプーフィング**が含まれます。Rescued スプーフィングは、明示的な認証チェック ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing)、 [dkim](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) に失敗したものの、拡張された認証チェックに合格したドメインです。そのため、Office 365 では、ユーザーの代わりにメールが rescued され、メールに対するスプーフィング対策アクションは行われませんでした。</span><span class="sxs-lookup"><span data-stu-id="cf988-p113">**Non-suspicious domain pairs** include **rescued spoof**. Rescued spoof are domains that have failed the explicit authentication checks ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) but passed our extended authentication checks. As a result of this, Office 365 rescued the mail on your behalf and no anti-spoofing action was taken on the mail.</span></span> 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="cf988-149">スプーフィングインテリジェンスの洞察から、疑わしいドメインペアに関する詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="cf988-149">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="cf988-150">スプーフィングインテリジェンスの洞察で、いずれかのドメインペア (high、中、または rescued) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf988-150">On the spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>
  
<span data-ttu-id="cf988-p114">[**スプーフィングインテリジェンスの洞察**] ページに、認証されていないメールを組織に送信している送信者の一覧が表示されます。このページの情報は、スプーフィングされたメッセージが承認されているかどうかを判断したり、さらにアクションを実行する必要があるかどうかを判断するのに役立つ。メッセージ数、スプーフィングが最後に検出された日付などによって、情報を並べ替えることができます。(たとえば、[**メッセージ件数**] や [**最後に表示**] など) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf988-p114">The **Spoof Intelligence Insight** page appears showing you a list of senders that are sending unauthenticated mail into your organization. The information on this page helps you determine whether spoofed messages are authorized or not or if you need to take further action. You can sort the information by message count, the date the spoof was last detected, and more. (Click column headings, such as **Message count** or **Last seen**, for example.)</span></span> 
    
2. <span data-ttu-id="cf988-p115">このテーブル内の項目を選択すると、そのドメインのペアに関する豊富な情報が含まれる詳細ウィンドウが表示されます。これには、これをキャッチした理由、ドメインの概要、送信者に関する WhoIs データ、および同じ送信者からのテナントに表示された類似の電子メールなどがあります。ここから、ドメインペアを**allowedtospoof** safe sender リストから追加または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf988-p115">Select an item in the table to open a details pane that contains rich information about the domain pair, including why we caught this, what you need to do, a domain summary, WhoIs data about the sender, and similar emails we have seen in your tenant from the same sender. From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span> 
  
![スプーフィングインテリジェンスの詳細情報ウィンドウにあるドメインのスクリーンショット](media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a><span data-ttu-id="cf988-158">allowedtospoof safe 送信者リストにドメインを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="cf988-158">Add or remove a domain from the AllowedToSpoof safe sender list</span></span>

<span data-ttu-id="cf988-p116">ドメインを allowedtospoof safe sender リストから追加または削除すると、スプーフィングインテリジェンスの洞察の詳細ウィンドウでドメインペアを確認することができます。それに応じてトグルを設定するだけです。</span><span class="sxs-lookup"><span data-stu-id="cf988-p116">You add or remove a domain from the AllowedToSpoof safe sender list while reviewing the domain pair in the details pane of the spoof intelligence insight. Simply set the toggle accordingly.</span></span>
  
<span data-ttu-id="cf988-p117">これにより、偽装されたドメインと送信元インフラストラクチャの一意のドメインペアの組み合わせが変更されます。また、分離されたドメインまたは送信元のインフラストラクチャ全体についても対応しません。たとえば、次のドメインの組を ' allowedtospoof ' 送信者の許可一覧に追加すると、*偽装ドメイン*"gmail.com" と、インフラストラクチャ " *mx.com"* を*送信*します。そのドメインペアからのメールのみがスプーフィングに許可されます。"gmail.com" のスプーフィングを試みる他の送信者、および "tms.mx.com" がスプーフィングしようとしている他のドメインは、スプーフィングインテリジェンスによって引き続き保護されます。</span><span class="sxs-lookup"><span data-stu-id="cf988-p117">This modifies the unique domain pair combination of the spoofed domain and the sending infrastructure and does not provide coverage for the entire spoofed domain or the sending infrastructure in isolation. For example, if you add the following domain pair to the 'AllowedToSpoof' sender allow list:  *Spoofed Domain*  "gmail.com" and  *Sending Infrastructure*  "tms  *.mx.com",*  then only mail from that domain pair will be allowed to spoof. Other senders attempting to spoof "gmail.com", and other domains that "tms.mx.com" attempt to spoof will continue to be protected by spoof intelligence.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="cf988-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf988-164">Related topics</span></span>

[<span data-ttu-id="cf988-165">スプーフィング インテリジェンスの詳細情報</span><span class="sxs-lookup"><span data-stu-id="cf988-165">Learn more about spoof intelligence</span></span>](learn-about-spoof-intelligence.md)
  
[<span data-ttu-id="cf988-166">Office 365 でのスプーフィング対策保護</span><span class="sxs-lookup"><span data-stu-id="cf988-166">Anti-spoofing protection in Office 365</span></span>](anti-spoofing-protection.md)
  
[<span data-ttu-id="cf988-167">チュートリアル - ダッシュボードからインサイトへの移動</span><span class="sxs-lookup"><span data-stu-id="cf988-167">Walkthrough - From a dashboard to an insight</span></span>](from-a-dashboard-to-an-insight.md)
  
[<span data-ttu-id="cf988-168">チュートリアル - 詳細レポートからインサイトへの移動</span><span class="sxs-lookup"><span data-stu-id="cf988-168">Walkthrough - From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  
[<span data-ttu-id="cf988-169">チュートリアル - インサイトから詳細レポートへの移動</span><span class="sxs-lookup"><span data-stu-id="cf988-169">Walkthrough - From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  

