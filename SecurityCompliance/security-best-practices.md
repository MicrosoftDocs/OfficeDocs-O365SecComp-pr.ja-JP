---
title: Office 365 のセキュリティのベスト プラクティス
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
description: これらの推奨されるベスト プラクティスに従って、データ漏洩やセキュリティを侵害されたアカウントの可能性を最小限に抑えます。
ms.openlocfilehash: 245302af0b08a4ee8183345fc386fe47985c93dd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532711"
---
# <a name="security-best-practices-for-office-365"></a><span data-ttu-id="3cd14-103">Office 365 のセキュリティのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="3cd14-103">Security best practices for Office 365</span></span>

<span data-ttu-id="3cd14-104">これらの推奨されるベスト プラクティスに従って、データ漏洩やセキュリティを侵害されたアカウントの可能性を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="3cd14-104">Minimize the potential of a data breach or a compromised account by following these recommended best practices.</span></span>
  
<span data-ttu-id="3cd14-p101">この資料には、ベスト ・ プラクティスの簡単な一覧が含まれています。詳細な詳細な分析とセキュリティの設定の詳細についてを参照してください[Office 365 のセキュリティ ロードマップ: 最初の 30 日、90 日間での内外の優先順位のトップ](security-roadmap.md)。その記事で情報を入手できます、実際の攻撃の調査に基づいて、上の Microsoft Office 365 cybersecurity エキスパートがリスクを評価し、最も重要なセキュリティ、コンプライアンス、および情報を実装する方法についての指導を提供Office 365 テナントを保護するためのコントロールを保護します。脅威の優先順位を付ける、技術戦略は、脅威に変換し、体系的なアプローチの機能とコントロールを実装する方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-p101">This article contains a quick list of best practices. For more in-depth analysis and information on setting up security, see [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md). In that article, you'll find information based on investigations of real-world attacks, where our top Microsoft Office 365 cybersecurity experts provide coaching on how to assess risk and implement the most critical security, compliance, and information protection controls to protect your Office 365 tenant. You'll learn how to prioritize threats, translate threats into technical strategy, and then take a systematic approach to implementing features and controls.</span></span>
  
## <a name="use-office-365-secure-score"></a><span data-ttu-id="3cd14-109">Office 365 のセキュリティで保護されたスコアを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-109">Use Office 365 Secure Score</span></span>

<span data-ttu-id="3cd14-p102">セキュリティで保護されたスコアは、さらにリスクの軽減を行うことができることをお勧めするセキュリティ分析ツールです。セキュリティで保護されたスコアを使用して、Office 365 の設定と活動を調べ、マイクロソフトによって確立されたベースラインを比較します。調整方法に問題が、セキュリティのベスト プラクティスに基づくスコアが表示されます。セキュリティで保護されたスコアを取得し、Office 365 の組織のセキュリティを強化するために使用する方法の詳細については、 [Office 365 のセキュリティで保護されたスコアを導入すること](office-365-secure-score.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cd14-p102">Secure Score is a security analytics tool that recommends what you can do to further reduce risk. Secure Score looks at your Office 365 settings and activities and compares them to a baseline established by Microsoft. You'll get a score based on how aligned you are with best security practices. For more information about how to get Secure Score and use it to increase the security of your Office 365 organization, see [Introducing the Office 365 Secure Score](office-365-secure-score.md).</span></span>
  
<span data-ttu-id="3cd14-114">セキュリティで保護されたスコアを試したいですか。</span><span class="sxs-lookup"><span data-stu-id="3cd14-114">Want to try out Secure Score?</span></span>
  
<span data-ttu-id="3cd14-115">[Office 365 にサインイン](https://www.office.com/signin)、Office 365 の[Office 365 の管理者の役割](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)の役割が割り当てられている、職場、学校のアカウントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="3cd14-115">Using a work or school account that has been assigned the Office 365 [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) role, [sign in to Office 365](https://www.office.com/signin).</span></span>
  
<span data-ttu-id="3cd14-116">アクセス時に得点をセキュリティで保護された[https://SecureScore.office.com](https://SecureScore.office.com)。</span><span class="sxs-lookup"><span data-stu-id="3cd14-116">Access Secure Score at [https://SecureScore.office.com](https://SecureScore.office.com).</span></span>
  
## <a name="use-multi-factor-authentication-mfa"></a><span data-ttu-id="3cd14-117">多要素認証を使用する (MFA)</span><span class="sxs-lookup"><span data-stu-id="3cd14-117">Use multi-factor authentication (MFA)</span></span>

<span data-ttu-id="3cd14-p103">MFA では、電話、テキスト メッセージ、または自分のパスワードを正しく入力した後、スマート フォン上のアプリ通知を確認するユーザーを要求することによって強力なパスワード方式に追加の保護レイヤーを追加します。MFA は、ユーザーのパスワードが危険にさらされた場合でも、Office 365 ユーザー アカウントがまだ不正アクセスから保護します。追加の課題が満たされた後までのアカウントにアクセスを許可しないために、アカウントが保護されています。危険にさらされた、または盗まれたパスワードは、十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="3cd14-p103">MFA adds an additional layer of protection to a strong password strategy by requiring users to acknowledge a phone call, text message, or an app notification on their smart phone after correctly entering their password. With MFA in place, Office 365 user accounts are still protected against unauthorized access even if a user's password is compromised. Accounts are protected because access is not granted to an account until after the additional challenge has been satisfied. A compromised or stolen password is not enough.</span></span>
  
- [<span data-ttu-id="3cd14-122">Office 365 の展開の多要素認証の計画</span><span class="sxs-lookup"><span data-stu-id="3cd14-122">Plan for multi-factor authentication for Office 365 Deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [<span data-ttu-id="3cd14-123">Office 365 のユーザーに対して多要素認証を設定します</span><span class="sxs-lookup"><span data-stu-id="3cd14-123">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
## <a name="use-office-365-cloud-app-security"></a><span data-ttu-id="3cd14-124">Office 365 のクラウド アプリケーションのセキュリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-124">Use Office 365 Cloud App Security</span></span>

<span data-ttu-id="3cd14-p104">異常なアクティビティを追跡し、それに基づいて行動する、ビジネス ・ ニーズに基づいてポリシーを設定します。管理者が大量のデータのダウンロードなど、異常なまたは危険なユーザー アクティビティを確認するよう Office 365 のクラウド アプリケーションのセキュリティの警告を設定複数サインインの試行、または不明なまたは危険な IP アドレスからのサインインができませんでした。組織で Office 365 エンタープライズ E5 計画には、Office 365 のクラウド アプリケーションのセキュリティをすぐに使用を開始できます。企業のさまざまな計画があれば、Office 365 のクラウド アプリケーションのセキュリティのアドオンとして購入できます。</span><span class="sxs-lookup"><span data-stu-id="3cd14-p104">Set up policies based on your business needs to track anomalous activity and act on it. Set up alerts with Office 365 Cloud App Security so that admins can review unusual or risky user activity, such as downloading large amounts of data, multiple failed sign-in attempts, or sign-ins from an unknown or dangerous IP address. For organizations with an Office 365 Enterprise E5 plan, you can start using Office 365 Cloud App Security right away. If you have a different enterprise plan, you can purchase Office 365 Cloud App Security as an add-on.</span></span>
  
- [<span data-ttu-id="3cd14-129">O365 クラウド アプリケーションのセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="3cd14-129">Overview of O365 Cloud App Security</span></span>](office-365-cas-overview.md)
    
- [<span data-ttu-id="3cd14-130">Office 365 Cloud App Security を有効にする</span><span class="sxs-lookup"><span data-stu-id="3cd14-130">Turn on Office 365 Cloud App Security</span></span>](turn-on-office-365-cas.md)
    
## <a name="secure-mail-flow"></a><span data-ttu-id="3cd14-131">セキュリティで保護されたメールの流れ</span><span class="sxs-lookup"><span data-stu-id="3cd14-131">Secure mail flow</span></span>

<span data-ttu-id="3cd14-132">リッチでは、Exchange のオンライン保護機能、各電子メール メッセージの送信者の身元についてより確実な保証を得るし、不明なマルウェア、ウイルス、および悪意のある Url を電子メール経由で送信される保護を実装します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-132">Implement the rich feature set in Exchange Online Protection and gain greater assurance about the identity of the sender of each email message, and protect against unknown malware, viruses, and malicious URLs transmitted through emails.</span></span>
  
- <span data-ttu-id="3cd14-133">組織の[Office 365 の電子メール スパム対策の保護](anti-spam-protection.md)ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-133">Configure [Office 365 Email Anti-Spam Protection](anti-spam-protection.md) policies for your organization.</span></span> 
    
- <span data-ttu-id="3cd14-134">について説明し、[安全な添付ファイルと安全なリンクの高度な脅威保護](https://technet.microsoft.com/library/mt148491.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-134">Learn about and then use [Advanced threat protection for safe attachments and safe links](https://technet.microsoft.com/library/mt148491.aspx).</span></span>
    
- <span data-ttu-id="3cd14-135">[組織に対するマルウェア対策保護を追加](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-135">[Add anti-malware protection to your organization](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx).</span></span>
    
- <span data-ttu-id="3cd14-136">について学習し、ユーザーの[Office 365 の電子メール メッセージでの安全性のヒント](safety-tips-in-office-365.md)を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3cd14-136">Learn about and enable [Safety tips in email messages in Office 365](safety-tips-in-office-365.md) for your users.</span></span> 
    
- <span data-ttu-id="3cd14-137">Office 365 の組織のカスタム ドメインを使用する場合は、組織から送信されたメールを検証し、なりすましを防ぐには SPF、DKIM、および DMARC を設定します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-137">If you're using a custom domain for your organization in Office 365, set up SPF, DKIM, and then DMARC to validate mail sent by your organization and to help prevent spoofing:</span></span>
    
  - <span data-ttu-id="3cd14-138">[スプーフィングを防止するために Office 365 の SPF を設定](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-138">[Set up SPF in Office 365 to help prevent spoofing](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx).</span></span>
    
  - <span data-ttu-id="3cd14-139">[カスタム ドメインを Office 365 から送信された送信の電子メールを検証するために DKIM を使用](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-139">[Use DKIM to validate outbound email sent from your custom domain in Office 365](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx).</span></span>
    
  - <span data-ttu-id="3cd14-140">[Office 365 で電子メールを検証するために DMARC を使用](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-140">[Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>
    
## <a name="enable-mailbox-audit-logging"></a><span data-ttu-id="3cd14-141">メールボックス監査ログを有効にする</span><span class="sxs-lookup"><span data-stu-id="3cd14-141">Enable mailbox audit logging</span></span>

<span data-ttu-id="3cd14-p105">Office 365; でのいくつかの監査ログが自動的に有効にただし、メールボックスの監査ログ収集既定で有効にできません。Office 365 のすべてのユーザーのメールボックスの監査ログにするには、Exchange オンライン PowerShell を使用します。については、[メールボックスを Office 365 で監査を有効にする](https://go.microsoft.com/fwlink/p/?LinkID=626109)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cd14-p105">Some audit logging is automatically enabled for you in Office 365; however, mailbox audit logging is not turned on by default. You turn on audit logging for all user mailboxes in Office 365 by using Exchange Online PowerShell. For information, see [Enable mailbox auditing in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=626109).</span></span>
  
<span data-ttu-id="3cd14-p106">監査ログを収集することができますを有効にした後[では、Office 365 のセキュリティ監査ログを検索する&amp;コンプライアンス センター](search-the-audit-log-in-security-and-compliance.md)メッセージ、および委任されたユーザー、メールボックスの所有者によって実行されるその他の活動を送信する、ユーザーのメールボックスにログオンしたことを確認するにはまたは管理者を選択します。Office 365 に含まれるメールボックス アクティビティの一覧については、監査ログを既定では、 [Exchange メールボックスの動作](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cd14-p106">After you've enabled audit logging you can [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md) to find out who has logged into your user mailboxes, sent messages, and other activities performed by the mailbox owner, a delegated user, or an administrator. For a list of mailbox activities that are included in the Office 365 audit log by default, see [Exchange mailbox activities](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities).</span></span>
  
<span data-ttu-id="3cd14-147">監査ログ、監査ログにエントリを保存するのには時間の変更などで実行できるその他のアクションについては、[メールボックスが Exchange 2016 のログを監査](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cd14-147">For information about other actions you can perform with the audit log, such as changing the amount of time to save entries in the audit log, see [Mailbox audit logging in Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx).</span></span>
  
## <a name="configure-data-loss-prevention-dlp"></a><span data-ttu-id="3cd14-148">データ損失防止 (DLP) を構成します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-148">Configure Data Loss Prevention (DLP)</span></span>

<span data-ttu-id="3cd14-p107">DLP では、機密性の高いデータを識別し、ユーザーが誤ってまたは意図的にデータを共有することを防ぐためのポリシーを作成できます。DLP は、ユーザーは、ワークフローを中断することがなく準拠で維持できるようにするため Exchange Online、SharePoint Online では、および OneDrive を含む Office 365 の間で動作します。詳細については、[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cd14-p107">DLP allows you to identify sensitive data and create policies that help prevent your users from accidentally or intentionally sharing the data. DLP works across Office 365 including Exchange Online, SharePoint Online, and OneDrive so that your users can stay compliant without interrupting their workflow. For more information, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
## <a name="use-customer-lockbox"></a><span data-ttu-id="3cd14-152">お客様のロック ボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-152">Use Customer Lockbox</span></span>

<span data-ttu-id="3cd14-p108">Office 365 管理者の場合は、マイクロソフトのサポート エンジニアがヘルプ セッション中に、データにアクセスする方法を制御するのに顧客のロック ボックスを使用できます。エンジニアがトラブルシューティングし、問題を修正するのには、データへのアクセスを必要とする場合、お客様のロック ボックスを使用すると、承認またはアクセス権の要求を拒否できます。それを承認すると、エンジニアがデータにアクセスできます。各要求には、有効期限、および問題が解決されると、要求は閉じられ、アクセスが無効にします。お客様のロック ボックスは、計画に含まれる、Office 365 エンタープライズ 5、またはその他の Office 365 エンタープライズ プランに個別のサブスクリプションを購入することができます。については、 [Office 365 ユーザーのロック ボックス要求](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cd14-p108">As an Office 365 admin, you can use Customer Lockbox to control how a Microsoft support engineer accesses your data during a help session. In cases where the engineer requires access to your data to troubleshoot and fix an issue, Customer Lockbox allows you to approve or reject the access request. If you approve it, the engineer can access the data. Each request has an expiration time, and once the issue is resolved, the request is closed and access is revoked. Customer Lockbox is included in the Office 365 Enterprise 5 plan, or you can purchase a separate subscription with any other Office 365 enterprise plan. For information, see [Office 365 Customer Lockbox Requests](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2).</span></span>
  
## <a name="try-it-yourself"></a><span data-ttu-id="3cd14-159">試してみよう</span><span class="sxs-lookup"><span data-stu-id="3cd14-159">Try it yourself</span></span>
<span data-ttu-id="3cd14-160"><a name="SecureScore"> </a></span><span class="sxs-lookup"><span data-stu-id="3cd14-160"></span></span>

<span data-ttu-id="3cd14-161">これらのセキュリティ機能を運用環境に導入する前に、Office 365 の試用版サブスクリプションでの作業を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cd14-161">See these security features working in an Office 365 trial subscription prior to adopting them in production.</span></span>
  
- [<span data-ttu-id="3cd14-162">Office 365 の試用版サブスクリプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-162">Create an Office 365 trial subscription</span></span>](https://technet.microsoft.com/library/mt736406.aspx)
    
- [<span data-ttu-id="3cd14-163">構成およびユーザー アカウントの MFA をテストします。</span><span class="sxs-lookup"><span data-stu-id="3cd14-163">Configure and test MFA for a user account</span></span>](https://technet.microsoft.com/library/mt492459.aspx)
    
- [<span data-ttu-id="3cd14-164">構成およびグローバル管理者のアクティビティを通知するのには Office 365 のクラウド アプリケーションのセキュリティをテストします。</span><span class="sxs-lookup"><span data-stu-id="3cd14-164">Configure and test Office 365 Cloud App Security to notify you of global admin activity</span></span>](https://technet.microsoft.com/library/mt757250.aspx)
    
- [<span data-ttu-id="3cd14-165">構成および不審な電子メールの分析ツールをテストします。</span><span class="sxs-lookup"><span data-stu-id="3cd14-165">Configure and test ATP for suspicious email</span></span>](https://technet.microsoft.com/library/mt490479.aspx)
    
- <span data-ttu-id="3cd14-166">上記の手順のそれぞれの試用版サブスクリプションの[Office 365 のセキュリティで保護されたスコア](https://securescore.office.com/)を確認します。</span><span class="sxs-lookup"><span data-stu-id="3cd14-166">Check the [Office 365 Secure Score](https://securescore.office.com/) for your trial subscription for each of the above steps</span></span> 
    

