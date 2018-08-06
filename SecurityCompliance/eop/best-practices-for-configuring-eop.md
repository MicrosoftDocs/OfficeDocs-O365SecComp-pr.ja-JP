---
title: EOP を構成するためのベスト プラクティス
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Exchange Online Protection (EOP) のベスト プラクティス推奨に従って正しく設定し、一般的な構成エラーを防止してください。
ms.openlocfilehash: ef58e2cd5a3ffdbbeb02124442c355974d174073
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027274"
---
# <a name="best-practices-for-configuring-eop"></a><span data-ttu-id="59829-103">EOP を構成するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="59829-103">Best practices for configuring EOP</span></span>
  
<span data-ttu-id="59829-p101">Exchange Online Protection (EOP) のベスト プラクティス推奨に従って正しく設定し、一般的な構成エラーを防止してください。原則として、既定の構成設定を使用することをお勧めします。このトピックでは、セットアップ プロセスが既に完了したことを前提としています。まだ EOP の設定が完了していない場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59829-p101">Follow these best-practice recommendations for Exchange Online Protection (EOP) in order to set yourself up for success and avoid common configuration errors. We recommend using the default configuration settings as a general rule. This topic assumes that you've already completed the setup process. If you haven't completed EOP setup, see [Set up your EOP service](set-up-your-eop-service.md).</span></span>
  
## <a name="use-a-test-domain"></a><span data-ttu-id="59829-108">テスト ドメインの使用</span><span class="sxs-lookup"><span data-stu-id="59829-108">Use a test domain</span></span>

<span data-ttu-id="59829-109">大容量の運用ドメインにサービス機能を実装する前に、それらを試すためテスト ドメイン、サブドメイン、または容量の小さいドメインを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59829-109">We recommend that you use a test domain, subdomain, or low volume domain for trying out service features before implementing them on your higher-volume, production domains.</span></span>
  
## <a name="synchronize-recipients"></a><span data-ttu-id="59829-110">受信者の同期</span><span class="sxs-lookup"><span data-stu-id="59829-110">Synchronize recipients</span></span>

<span data-ttu-id="59829-p102">オンプレミスの Active Directory 環境に既存のユーザー アカウントがある場合、そのアカウント情報とクラウドの Azure Active Directory を同期させることができます。ディレクトリ同期の使用をお勧めします。ディレクトリ同期を使用することのメリットおよびそのセットアップの手順の詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59829-p102">If your organization has existing user accounts in an on-premisesActive Directory environment, you can synchronize those accounts to Azure Active Directory in the cloud. Using directory synchronization is recommended. To learn more about the benefits of using directory synchronization, and the steps for setting it up, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>
  
## <a name="spf-record-customization-to-help-prevent-spoofing"></a><span data-ttu-id="59829-114">スプーフィングを防止するための SPF レコードのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="59829-114">SPF record customization to help prevent spoofing</span></span>

<span data-ttu-id="59829-p103">EOP をセットアップするときに DNS レコードの EOP の SPF (送信者ポリシー フレームワーク) レコードが追加されます。SPF レコードは、スプーフィングの防止に役立ちます。SPF レコードが悪用を防止する方法と、SPF レコードを設置型の IP アドレスを追加する方法の詳細については、[スプーフィングを防止するために Office 365 の SPF の設定](../set-up-spf-in-office-365-to-help-prevent-spoofing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59829-p103">When you set up EOP, you added an SPF (sender policy framework) record for EOP to your DNS records. The SPF record helps prevent spoofing. For more information about how an SPF record prevents spoofing and how you can add your on-premises IP addresses to the SPF record, see [Set up SPF in Office 365 to help prevent spoofing](../set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> 
  
## <a name="set-anti-spam-options"></a><span data-ttu-id="59829-118">スパム対策オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="59829-118">Set anti-spam options</span></span>

<span data-ttu-id="59829-p104">管理、接続フィルターの設定で IP を許可して、IP 禁止一覧に IP アドレスを追加して誤検知 (スパムとして分類されている適切なメール) の数を減らす必要があります、**セーフ リストを有効にする**オプションを選択することによって表示されます。[接続フィルター ポリシーの構成](../configure-the-connection-filter-policy.md)の詳細を表示します。組織全体に適用するより多くの迷惑メール設定を見て[、メッセージがスパムとしてマークされたされていないことを確保する方法](https://go.microsoft.com/fwlink/p/?LinkId=534224)または[false の負の問題を防ぐために Office 365 のスパム フィルターを使用してスパム電子メールをブロック](https://go.microsoft.com/fwlink/p/?LinkId=534225)します。これらは、管理者レベルの制御があり、偽陽性や漏れを防止したい場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="59829-p104">Mange your connection filter settings by adding IP addresses to IP Allow and IP Block lists, and by selecting the **Enable safe list** option, which should reduce the number of false positives (good mail that's classified as spam) you receive. Learn more at [Configure the connection filter policy](../configure-the-connection-filter-policy.md). For more spam settings that apply to the whole organization, take a look at [How to help ensure that a message isn't marked as spam](https://go.microsoft.com/fwlink/p/?LinkId=534224) or [Block email spam with the Office 365 spam filter to prevent false negative issues](https://go.microsoft.com/fwlink/p/?LinkId=534225). These are helpful if you have administrator-level control and you want to prevent false positives or false negatives.</span></span>
  
<span data-ttu-id="59829-p105">コンテンツ フィルターを管理するを確認し、必要に応じて既定の設定を変更します。などのアクションは、メッセージを迷惑メール検出の動作を変更できます。スパムのフィルタ リングの積極的なアプローチを追求する場合は、高度な迷惑メールのフィルタ リングのオプションを構成できます。最初にそれらを実装する、運用環境で (電源を入れること) でオプションをお勧めフィッシング詐欺を懸念している組織を有効にするこれらをテストすることをお勧め、 **SPF レコード: ハード失敗**オプションです。[スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)と[高度な迷惑メール フィルターのオプション](../advanced-spam-filtering-asf-options.md)の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="59829-p105">Manage your content filters by reviewing and optionally changing the default settings. For example, you can change the action for what happens to spam-detected messages. If you want to pursue an aggressive approach to spam filtering, you can configure advanced spam filtering  options. We recommend that you test these options first before implementing them in your production environment (by turning them on) It's recommended that organizations who are concerned about phishing turn on the **SPF record: hard fail** option. Learn more at [Configure your spam filter policies](../configure-your-spam-filter-policies.md) and [Advanced spam filtering  options](../advanced-spam-filtering-asf-options.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="59829-p106">オンプレミスのメールボックスにこのアクションが動作することを確認するのには **[迷惑メール フォルダーにメッセージを移動**するには、デフォルトのコンテンツのフィルター処理を使用する場合、設置型のトランスポート ルールとも呼ばれます Exchange メール フロー ルールを構成する必要があります。EOP によって追加された迷惑メールのヘッダーを検出するサーバーです。詳細については、[各ユーザーの迷惑メール フォルダーに迷惑メールがルーティングされるようにする](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59829-p106">If you are using the default content filter action, **Move message to Junk Email folder**, in order to ensure that this action will work with on-premises mailboxes, you must configure Exchange mail flow rules, also called transport rules, on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
<span data-ttu-id="59829-130">[スパム対策の保護に関する FAQ](../anti-spam-protection-faq.md)など、送信宛名ベスト プラクティス セクションにより、送信メールが配信されることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59829-130">We recommend that you review the [Anti-spam protection FAQ](../anti-spam-protection-faq.md), including the outbound mailing best practices section, which will help ensure that your outbound mail is delivered.</span></span>
  
<span data-ttu-id="59829-p107">漏れ (スパム) と誤検知 (スパムではない) マイクロソフトにいくつかの方法で分析するために送信できます。詳細については、[迷惑メールの送信、スパム以外の場合、および分析のためのマイクロソフトのフィッシング詐欺メッセージ](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59829-p107">You can submit false negatives (spam) and false positives (non-spam) to Microsoft for analysis in several ways. For details, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span>
  
## <a name="set-anti-malware-options"></a><span data-ttu-id="59829-133">マルウェア対策オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="59829-133">Set anti-malware options</span></span>

<span data-ttu-id="59829-p108">確認し、Exchange 管理者の center(EAC) では、マルウェアのフィルター設定を調整します。[マルウェア対策ポリシーの構成](../configure-anti-malware-policies.md)の詳細を表示します。に関するその他のよく寄せられる質問と回答、[よく寄せられる質問のマルウェア対策保護](../anti-malware-protection-faq-eop.md)のマルウェア対策保護に関連する読み取りお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59829-p108">Review and fine tune your malware filter settings in the Exchange admin center(EAC). Learn more at [Configure anti-malware policies](../configure-anti-malware-policies.md). We also recommend reading about other frequently asked questions and answers pertaining to anti-malware protection in our [Anti-malware protection FAQ ](../anti-malware-protection-faq-eop.md).</span></span>
  
<span data-ttu-id="59829-p109">マルウェアを含む実行可能ファイルを懸念している場合は、実行可能なコンテンツを含むすべての電子メール添付ファイルをブロックする Exchange メール フロー ルールを作成できます。「[Exchange Online Protection または Forefront Online Protection for Exchange の添付ファイルのブロック機能でマルウェアの脅威を低減する方法](https://support.microsoft.com/kb/2959596)」の手順に従って、「[Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)」の「トランスポート ルールによる検査でサポートされている実行可能ファイルの種類」にリストされたファイル タイプをブロックします。</span><span class="sxs-lookup"><span data-stu-id="59829-p109">If you're concerned about executable files containing malware, you can create an Exchange mail flow rule that blocks any email attachment that has executable content. Follow the steps in [How to reduce malware threats through file attachment blocking in Exchange Online Protection](https://support.microsoft.com/kb/2959596) in order to block the file types listed under "Supported executable file types for transport rule inspection" in [Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx).</span></span>
  
<span data-ttu-id="59829-p110">EAC の一般的な添付ファイルの種類フィルターを使用できます。 **[保護]** \> **[マルウェア フィルター]** と選択します。実行可能なコンテンツが含まれるすべての電子メール添付ファイルをブロックする Exchange メール フロー ルール (別名: トランスポート ルール) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="59829-p110">You can use the Common Attachment Types Filter in the EAC. Select **protection** \> **malware filters**. You can create an Exchange mail flow rule, also known as transport rule, that blocks any email attachment that has executable content.</span></span> 
  
<span data-ttu-id="59829-p111">保護を強化するために、メール フロー ルールを使用して、以下の拡張子のすべてまたは一部をブロックすることもお勧めします。ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、ht、hta、inf、ins、isp、job、js、jse、lnk、mda、mdb、mde、mdz、msc、msi、msp、mst、pcd、reg、scr、sct、shs、url、vb、vbe、vbs、wsc、wsf、wsh。これは、 **[任意の添付ファイルの拡張子に次の単語が含まれる場合]** の条件を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="59829-p111">For increased protection, we also recommend using mail flow rules to block some or all of the following extensions: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh. This can be done by using the **Any attachment file extension includes these words** condition.</span></span> 
  
<span data-ttu-id="59829-p112">管理者およびエンド ユーザーは、分析のためにそのファイルを Microsoft に送信することによって、フィルターを通過したマルウェアやマルウェアとして誤判定されたと思われるファイルを報告できます。詳細については、「[Submitting malware and non-malware to Microsoft for analysis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59829-p112">Administrators and end users can submit malware that made it past the filters, or submit a file that you think was incorrectly identified as malware, by sending it to Microsoft for analysis. For more information, see [Submitting malware and non-malware to Microsoft for analysis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md).</span></span>
  
## <a name="create-mail-flow-rules"></a><span data-ttu-id="59829-146">メール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="59829-146">Create mail flow rules</span></span>

<span data-ttu-id="59829-147">ビジネス ニーズを満たすために、メール フロー ルール (カスタム フィルターともいう) を作成します。</span><span class="sxs-lookup"><span data-stu-id="59829-147">Create mail flow rules, also called transport rules or custom filters, to meet your business needs.</span></span>
  
<span data-ttu-id="59829-p113">新しいルールを運用環境に展開するときは、最初にテスト モードの 1 つを選択してルールの効果を確認します。ルールが意図したとおりに機能したら、ルールのモードを **[強制]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="59829-p113">When you deploy a new rule to production, select one of the test modes first to see the effect of the rule. Once you are satisfied that the rule is working in the manner intended, change the rule mode to **Enforce**.</span></span>
  
<span data-ttu-id="59829-150">新しいルールを展開した場合は、適用中のルールを監視するために **[インシデント レポートの生成]** の追加を検討してください。</span><span class="sxs-lookup"><span data-stu-id="59829-150">When you deploy new rules, consider adding the additional action of **Generate Incident Report** to monitor the rule in action.</span></span> 
  
<span data-ttu-id="59829-p114">ハイブリッド展開構成で、組織の構成がオンプレミスと Office 365 の場合は、組織全体に適用するルールを作成できます。これを行うには、オンプレミスと Office 365 の両方で使用できる条件を使用します。ほとんどの条件は両方の展開で使用可能ですが、特定の展開シナリオに固有の条件もいくつかあります。詳細については、「[Mail flow or Transport rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59829-p114">If you are in a hybrid deployment configuration, with part of your organization on-premises and part in Office 365, you can create rules that apply to the entire organization. To do this, use conditions that are available both on-premises and in Office 365. While most conditions are available in both deployments, there is a small set that is specific to a particular deployment scenario. Learn more at [Mail flow or Transport rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).</span></span>
  
<span data-ttu-id="59829-p115">組織内で送信中のメッセージのメール添付ファイルを検査する場合には、メール フロー ルールを設定します。その後、添付ファイルの内容や特性に基づいて検査されたメッセージに対してアクションを実行できます。詳細については、「[Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59829-p115">If you want to inspect email attachments for messages in-transit within your organization, you can do this by setting up mail flow rules. Then, take action on the messages that were inspected based on the content or characteristics of those attachments. Learn more at [Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx).</span></span>
  
### <a name="phishing-and-spoofing-prevention"></a><span data-ttu-id="59829-158">フィッシングとスプーフィングの防止</span><span class="sxs-lookup"><span data-stu-id="59829-158">Phishing and Spoofing Prevention</span></span>

<span data-ttu-id="59829-p116">電子メールで個人情報が組織から外部に出ていくときに、それを検出することで、フィッシング詐欺対策保護を強化できます。たとえば、次の正規表現をメール フロー ルールで使用すると、個人の金融データやプライバシーを侵害する可能性のある情報の伝送を検出できます。</span><span class="sxs-lookup"><span data-stu-id="59829-p116">You can improve anti-phishing protection by the detecting when personal information exits the organization in email. For example, you can use the following regular expressions in mail flow rules to detect transmission of personal financial data or information that may compromise privacy:</span></span>
  
- <span data-ttu-id="59829-161">\d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d (MasterCard Visa)</span><span class="sxs-lookup"><span data-stu-id="59829-161">\d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d (MasterCard Visa)</span></span>
    
- <span data-ttu-id="59829-162">\d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d (American Express)</span><span class="sxs-lookup"><span data-stu-id="59829-162">\d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d (American Express)</span></span>
    
- <span data-ttu-id="59829-163">\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d (任意の 16 桁の数字)</span><span class="sxs-lookup"><span data-stu-id="59829-163">\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d (any 16-digit number)</span></span>
    
- <span data-ttu-id="59829-164">\d\d\d\-\d\d\-\d\d\d\d (社会保障番号)</span><span class="sxs-lookup"><span data-stu-id="59829-164">\d\d\d\-\d\d\-\d\d\d\d (Social Security Numbers)</span></span>
    
<span data-ttu-id="59829-p117">組織的なスパムやフィッシング詐欺行為による被害は、ユーザー自身のドメインから送信されたように見せかけた悪意のある電子メールの受信をブロックすることによっても減らせます。たとえば、ユーザーの会社のドメインから同じ会社のドメインに送信されたメッセージを拒否するメール フロー ルールを作成して、この種の送信者偽装をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="59829-p117">Successful spam and phishing campaigns can also be reduced by blocking inbound, malicious emails that appear to have been sent from your own domain. For example, you can create a mail flow rule that rejects messages from your company domain sent to the same company domain to block this type of sender forgery.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="59829-p118">この拒否ルールは、ドメインからの正規の電子メールがインターネットからメール サーバーに送信されないことが確認されている場合にのみ作成することをお勧めします。この状況は、メッセージが組織内部のユーザーから外部の受信者に送信され、その後、組織内部の別の受信者に転送される場合が該当します。</span><span class="sxs-lookup"><span data-stu-id="59829-p118">We recommend creating this reject rule only in cases where you are certain that no legitimate email from your domain is sent from the Internet to your mail server. This can happen in cases where a message is sent from a user in your organization to an outside recipient and subsequently forwarded to another recipient in your organization.</span></span> 
  
### <a name="extension-blocking"></a><span data-ttu-id="59829-169">拡張子ブロック</span><span class="sxs-lookup"><span data-stu-id="59829-169">Extension Blocking</span></span>

<span data-ttu-id="59829-p119">マルウェアが含まれている実行可能ファイルのファイルについて心配がある場合、電子メールの添付ファイルを持つ実行可能なコンテンツをブロックするマルウェア対策ポリシーを構成できます。[マルウェア対策ポリシーを構成する](../configure-anti-malware-policies.md)手順に従います。</span><span class="sxs-lookup"><span data-stu-id="59829-p119">If you're concerned about executable files containing malware, you can configure anti-malware policies to block any email attachment that has executable content. Follow the steps in [Configure anti-malware policies](../configure-anti-malware-policies.md).</span></span>
  
<span data-ttu-id="59829-172">保護を強化するために、次の拡張子の一部または全部をブロックすることもお勧めします。 ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、ht、hta、inf、ins、isp、job、js、jse、lnk、mda、mdb、mde、mdz、msc、msi、msp、mst、pcd、reg、scr、sct、shs、url、vb、vbe、vbs、wsc、wsf、wsh</span><span class="sxs-lookup"><span data-stu-id="59829-172">For increased protection, we also recommend that you block some or all of the following extensions: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh.</span></span>
  
## <a name="reporting-and-troubleshooting"></a><span data-ttu-id="59829-173">レポートとトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="59829-173">Reporting and troubleshooting</span></span>

<span data-ttu-id="59829-p120">Office 365 の管理センターのレポートを使って、一般的な課題と傾向のトラブルシューティングを行います。メッセージについて単一の固有なデータを探すには、メッセージ トレース ツールを使用します。レポートの詳細については、「[Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md)」を参照してください。メッセージ トレース ツールの詳細については、「[Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59829-p120">Troubleshoot general issues and trends by using the reports in the Office 365 admin center. Find single point specific data about a message by using the message trace tool. Learn more about reporting at [Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Learn more about the message trace tool at [Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="59829-178">詳細情報</span><span class="sxs-lookup"><span data-stu-id="59829-178">For more information</span></span>

[<span data-ttu-id="59829-179">EOP の一般的な FAQ</span><span class="sxs-lookup"><span data-stu-id="59829-179">EOP general FAQ</span></span>](eop-general-faq.md)
  
[<span data-ttu-id="59829-180">EOP のヘルプとサポート</span><span class="sxs-lookup"><span data-stu-id="59829-180">Help and support for EOP</span></span>](help-and-support-for-eop.md)
  
[<span data-ttu-id="59829-181">EOP の使用を開始するためのビデオ</span><span class="sxs-lookup"><span data-stu-id="59829-181">Videos for getting started with EOP</span></span>](videos-for-getting-started-with-eop.md)
  
[<span data-ttu-id="59829-182">メッセージがスパムとしてマークされないようにする方法</span><span class="sxs-lookup"><span data-stu-id="59829-182">How to help ensure that a message isn't marked as spam</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[<span data-ttu-id="59829-183">検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする</span><span class="sxs-lookup"><span data-stu-id="59829-183">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

