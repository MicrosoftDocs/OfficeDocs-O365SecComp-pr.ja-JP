---
title: Office 365 のセキュリティのベスト プラクティス
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
description: 以下の推奨されるベストプラクティスに従って、データ違反または侵害されたアカウントの可能性を最小限に抑えます。
ms.openlocfilehash: d40fa5e4534bef1bb8389989022c44967a162aee
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30212817"
---
# <a name="security-best-practices-for-office-365"></a><span data-ttu-id="40423-103">Office 365 のセキュリティのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="40423-103">Security best practices for Office 365</span></span>

<span data-ttu-id="40423-104">以下の推奨されるベストプラクティスに従って、データ違反または侵害されたアカウントの可能性を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="40423-104">Minimize the potential of a data breach or a compromised account by following these recommended best practices.</span></span>
  
<span data-ttu-id="40423-p101">この記事には、ベストプラクティスの簡単な一覧が記載されています。詳細な分析とセキュリティの設定に関する情報については、「 [Office 365 セキュリティロードマップ: 最初の30日間、90日以降の優先度の高いもの](security-roadmap.md)を参照してください。この記事では、Microsoft Office 365 cybersecurity のトップの専門家が、リスクを評価し、最も重要なセキュリティ、コンプライアンス、情報を実装する方法について指導する、現実世界の攻撃の調査に基づく情報を提供します。Office 365 テナントを保護するための保護制御。脅威の優先度を設定し、脅威を技術的戦略に変換した後、機能と制御を実装するための体系的なアプローチを採用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="40423-p101">This article contains a quick list of best practices. For more in-depth analysis and information on setting up security, see [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md). In that article, you'll find information based on investigations of real-world attacks, where our top Microsoft Office 365 cybersecurity experts provide coaching on how to assess risk and implement the most critical security, compliance, and information protection controls to protect your Office 365 tenant. You'll learn how to prioritize threats, translate threats into technical strategy, and then take a systematic approach to implementing features and controls.</span></span>
  
## <a name="use-office-365-secure-score"></a><span data-ttu-id="40423-109">Office 365 のセキュリティで保護されたスコアの使用</span><span class="sxs-lookup"><span data-stu-id="40423-109">Use Office 365 Secure Score</span></span>

<span data-ttu-id="40423-p102">セキュリティで保護されたスコアは、リスクをさらに軽減するために推奨されるセキュリティ分析ツールです。セキュリティで保護されたスコアは、Office 365 の設定とアクティビティを調べて、Microsoft によって確立された基準と比較します。最適なセキュリティプラクティスの調整に基づいて、スコアが得られます。セキュリティで保護されたスコアを取得し、それを使用して office 365 組織のセキュリティを強化する方法の詳細については、「 [office 365 のセキュリティで保護さ](office-365-secure-score.md)れたスコアを導入する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40423-p102">Secure Score is a security analytics tool that recommends what you can do to further reduce risk. Secure Score looks at your Office 365 settings and activities and compares them to a baseline established by Microsoft. You'll get a score based on how aligned you are with best security practices. For more information about how to get Secure Score and use it to increase the security of your Office 365 organization, see [Introducing the Office 365 Secure Score](office-365-secure-score.md).</span></span>
  
<span data-ttu-id="40423-114">セキュリティで保護されたスコアを試す場合</span><span class="sxs-lookup"><span data-stu-id="40423-114">Want to try out Secure Score?</span></span>
  
<span data-ttu-id="40423-115">office 365 について office の[管理者の役割](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)の役割に割り当てられている職場または学校のアカウントを使用して、 [office 365 にサインイン](https://www.office.com/signin)します。</span><span class="sxs-lookup"><span data-stu-id="40423-115">Using a work or school account that has been assigned the Office 365 [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) role, [sign in to Office 365](https://www.office.com/signin).</span></span>
  
<span data-ttu-id="40423-116">セキュリティで保護さ[https://SecureScore.office.com](https://SecureScore.office.com)れたスコアへのアクセス</span><span class="sxs-lookup"><span data-stu-id="40423-116">Access Secure Score at [https://SecureScore.office.com](https://SecureScore.office.com).</span></span>
  
## <a name="use-multi-factor-authentication-mfa"></a><span data-ttu-id="40423-117">多要素認証 (MFA) を使用する</span><span class="sxs-lookup"><span data-stu-id="40423-117">Use multi-factor authentication (MFA)</span></span>

<span data-ttu-id="40423-p103">MFA は、パスワードを正確に入力した後に、スマートフォンでの通話、テキストメッセージ、またはアプリの通知の確認をユーザーに要求することで、強力なパスワード戦略に保護の層を追加します。MFA が設定されていると、ユーザーのパスワードが侵害された場合でも、Office 365 のユーザーアカウントは承認されていないアクセスから保護されたままです。アカウントが保護されるのは、追加のチャレンジが満たされるまでアカウントへのアクセスが許可されないためです。侵害または盗難にあったパスワードが十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="40423-p103">MFA adds an additional layer of protection to a strong password strategy by requiring users to acknowledge a phone call, text message, or an app notification on their smart phone after correctly entering their password. With MFA in place, Office 365 user accounts are still protected against unauthorized access even if a user's password is compromised. Accounts are protected because access is not granted to an account until after the additional challenge has been satisfied. A compromised or stolen password is not enough.</span></span>
  
- [<span data-ttu-id="40423-122">Office 365 展開用の多要素認証の計画</span><span class="sxs-lookup"><span data-stu-id="40423-122">Plan for multi-factor authentication for Office 365 Deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [<span data-ttu-id="40423-123">Office 365 の多要素認証を設定する</span><span class="sxs-lookup"><span data-stu-id="40423-123">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
## <a name="use-office-365-cloud-app-security"></a><span data-ttu-id="40423-124">Office 365 Cloud App Security の使用</span><span class="sxs-lookup"><span data-stu-id="40423-124">Use Office 365 Cloud App Security</span></span>

<span data-ttu-id="40423-p104">ビジネスニーズに基づいてポリシーを設定し、異常なアクティビティを追跡して、それに対処します。Office 365 Cloud App Security を使用して通知を設定することで、管理者は大量のデータのダウンロード、サインイン試行の失敗、不明または危険な IP アドレスからのサインインなど、不審で、または危険なユーザーアクティビティを確認できます。office 365 Enterprise E5 プランを持つ組織では、すぐに office 365 Cloud App Security の使用を開始することができます。エンタープライズプランが異なる場合は、Office 365 Cloud App Security をアドオンとして購入できます。</span><span class="sxs-lookup"><span data-stu-id="40423-p104">Set up policies based on your business needs to track anomalous activity and act on it. Set up alerts with Office 365 Cloud App Security so that admins can review unusual or risky user activity, such as downloading large amounts of data, multiple failed sign-in attempts, or sign-ins from an unknown or dangerous IP address. For organizations with an Office 365 Enterprise E5 plan, you can start using Office 365 Cloud App Security right away. If you have a different enterprise plan, you can purchase Office 365 Cloud App Security as an add-on.</span></span>
  
- [<span data-ttu-id="40423-129">O365 Cloud App Security の概要</span><span class="sxs-lookup"><span data-stu-id="40423-129">Overview of O365 Cloud App Security</span></span>](office-365-cas-overview.md)
    
- [<span data-ttu-id="40423-130">Office 365 Cloud App Security を有効にする</span><span class="sxs-lookup"><span data-stu-id="40423-130">Turn on Office 365 Cloud App Security</span></span>](turn-on-office-365-cas.md)
    
## <a name="secure-mail-flow"></a><span data-ttu-id="40423-131">セキュリティで保護されたメールフロー</span><span class="sxs-lookup"><span data-stu-id="40423-131">Secure mail flow</span></span>

<span data-ttu-id="40423-132">Exchange Online Protection の豊富な機能セットを実装し、各電子メールメッセージの送信者の id についての保証を強化し、電子メールによって送信される不明なマルウェア、ウイルス、および悪意のある url から保護します。</span><span class="sxs-lookup"><span data-stu-id="40423-132">Implement the rich feature set in Exchange Online Protection and gain greater assurance about the identity of the sender of each email message, and protect against unknown malware, viruses, and malicious URLs transmitted through emails.</span></span>
  
- <span data-ttu-id="40423-133">組織の[Office 365 電子メールのスパム対策保護](anti-spam-protection.md)ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="40423-133">Configure [Office 365 Email Anti-Spam Protection](anti-spam-protection.md) policies for your organization.</span></span> 
    
- <span data-ttu-id="40423-134">[「安全な添付ファイルと安全なリンク](https://technet.microsoft.com/library/mt148491.aspx)」について説明し、Advanced threat protection を使用します。</span><span class="sxs-lookup"><span data-stu-id="40423-134">Learn about and then use [Advanced threat protection for safe attachments and safe links](https://technet.microsoft.com/library/mt148491.aspx).</span></span>
    
- <span data-ttu-id="40423-135">[組織にマルウェア対策保護を追加](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="40423-135">[Add anti-malware protection to your organization](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx).</span></span>
    
- <span data-ttu-id="40423-136">ユーザーのために[Office 365 の電子メールメッセージの安全性](safety-tips-in-office-365.md)に関するヒントについて説明し、有効にします。</span><span class="sxs-lookup"><span data-stu-id="40423-136">Learn about and enable [Safety tips in email messages in Office 365](safety-tips-in-office-365.md) for your users.</span></span> 
    
- <span data-ttu-id="40423-137">Office 365 で組織のカスタムドメインを使用している場合は、SPF、dkim、DMARC を設定して、組織によって送信されたメールを検証し、スプーフィングを防止するために、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="40423-137">If you're using a custom domain for your organization in Office 365, set up SPF, DKIM, and then DMARC to validate mail sent by your organization and to help prevent spoofing:</span></span>
    
  - <span data-ttu-id="40423-138">[スプーフィングを防止するために、Office 365 で SPF をセットアップ](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)します。</span><span class="sxs-lookup"><span data-stu-id="40423-138">[Set up SPF in Office 365 to help prevent spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).</span></span>
    
  - <span data-ttu-id="40423-139">[dkim を使用して、Office 365 でカスタムドメインから送信される送信電子メールを検証](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)します。</span><span class="sxs-lookup"><span data-stu-id="40423-139">[Use DKIM to validate outbound email sent from your custom domain in Office 365](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).</span></span>
    
  - <span data-ttu-id="40423-140">[DMARC を使用して、Office 365 で電子メールを検証](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="40423-140">[Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>
    
## <a name="enable-mailbox-audit-logging"></a><span data-ttu-id="40423-141">メールボックス監査ログを有効にする</span><span class="sxs-lookup"><span data-stu-id="40423-141">Enable mailbox audit logging</span></span>

<span data-ttu-id="40423-p105">Office 365 では、一部の監査ログが自動的に有効になります。ただし、メールボックス監査ログは既定で有効になっていません。Office 365 のすべてのユーザーメールボックスの監査ログをオンにするには、Exchange Online PowerShell を使用します。詳細については、「 [Enable mailbox auditing in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=626109)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40423-p105">Some audit logging is automatically enabled for you in Office 365; however, mailbox audit logging is not turned on by default. You turn on audit logging for all user mailboxes in Office 365 by using Exchange Online PowerShell. For information, see [Enable mailbox auditing in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=626109).</span></span>
  
<span data-ttu-id="40423-p106">監査ログを有効にした後、 [Office 365 セキュリティ&amp;コンプライアンスセンターで監査ログを検索](search-the-audit-log-in-security-and-compliance.md)して、ユーザーのメールボックス、送信済みメッセージ、およびメールボックスの所有者が実行したその他のアクティビティ (委任されたユーザー) によって実行されたユーザーを見つけることができます。または管理者。既定で Office 365 監査ログに含まれるメールボックスアクティビティの一覧については、「 [Exchange mailbox アクティビティ](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40423-p106">After you've enabled audit logging you can [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md) to find out who has logged into your user mailboxes, sent messages, and other activities performed by the mailbox owner, a delegated user, or an administrator. For a list of mailbox activities that are included in the Office 365 audit log by default, see [Exchange mailbox activities](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities).</span></span>
  
<span data-ttu-id="40423-147">監査ログで実行できるその他のアクションの詳細については、「 [Exchange 2016 のメールボックス監査ログ](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40423-147">For information about other actions you can perform with the audit log, such as changing the amount of time to save entries in the audit log, see [Mailbox audit logging in Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx).</span></span>
  
## <a name="configure-data-loss-prevention-dlp"></a><span data-ttu-id="40423-148">データ損失防止 (DLP) を構成する</span><span class="sxs-lookup"><span data-stu-id="40423-148">Configure Data Loss Prevention (DLP)</span></span>

<span data-ttu-id="40423-p107">DLP を使用すると、機密データを識別し、ポリシーを作成して、ユーザーが偶然または故意にデータを共有するのを防ぐのに役立ちます。DLP は、Exchange online、SharePoint Online、および OneDrive を含む Office 365 に対して機能するため、ワークフローを中断することなく、ユーザーが準拠し続けることができます。詳細については、「[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40423-p107">DLP allows you to identify sensitive data and create policies that help prevent your users from accidentally or intentionally sharing the data. DLP works across Office 365 including Exchange Online, SharePoint Online, and OneDrive so that your users can stay compliant without interrupting their workflow. For more information, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
## <a name="use-customer-lockbox"></a><span data-ttu-id="40423-152">カスタマーロックボックスを使用する</span><span class="sxs-lookup"><span data-stu-id="40423-152">Use Customer Lockbox</span></span>

<span data-ttu-id="40423-p108">Office 365 管理者は、カスタマーロックボックスを使用して、Microsoft サポートエンジニアがヘルプセッション中にデータにアクセスする方法を制御できます。トラブルシューティングを行って問題を修正するためにエンジニアがデータにアクセスする必要がある場合は、カスタマーロックボックスを使用してアクセス要求を承認または拒否することができます。承認すると、エンジニアはデータにアクセスできるようになります。各要求には有効期限があり、問題が解決されると、要求は閉じられ、アクセスは取り消されます。お客様のロックボックスは office 365 enterprise E5 プランに含まれています。または、他の office 365 Enterprise プランと別のサブスクリプションを購入することもできます。詳細については、「 [Office 365 の顧客ロックボックス要求](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40423-p108">As an Office 365 admin, you can use Customer Lockbox to control how a Microsoft support engineer accesses your data during a help session. In cases where the engineer requires access to your data to troubleshoot and fix an issue, Customer Lockbox allows you to approve or reject the access request. If you approve it, the engineer can access the data. Each request has an expiration time, and once the issue is resolved, the request is closed and access is revoked. Customer Lockbox is included in the Office 365 Enterprise E5 plan, or you can purchase a separate subscription with any other Office 365 enterprise plan. For information, see [Office 365 Customer Lockbox Requests](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2).</span></span>
  
## <a name="try-it-yourself"></a><span data-ttu-id="40423-159">自分で試してみる</span><span class="sxs-lookup"><span data-stu-id="40423-159">Try it yourself</span></span>
<span data-ttu-id="40423-160"><a name="SecureScore"> </a></span><span class="sxs-lookup"><span data-stu-id="40423-160"></span></span>

<span data-ttu-id="40423-161">これらのセキュリティ機能を運用環境で採用する前に、Office 365 試用版サブスクリプションで作業してください。</span><span class="sxs-lookup"><span data-stu-id="40423-161">See these security features working in an Office 365 trial subscription prior to adopting them in production.</span></span>
  
- [<span data-ttu-id="40423-162">Office 365 試用版サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="40423-162">Create an Office 365 trial subscription</span></span>](https://technet.microsoft.com/library/mt736406.aspx)
    
- [<span data-ttu-id="40423-163">ユーザーアカウントの MFA を構成およびテストする</span><span class="sxs-lookup"><span data-stu-id="40423-163">Configure and test MFA for a user account</span></span>](https://technet.microsoft.com/library/mt492459.aspx)
    
- [<span data-ttu-id="40423-164">Office 365 Cloud App Security を構成およびテストして、グローバル管理者のアクティビティを通知する</span><span class="sxs-lookup"><span data-stu-id="40423-164">Configure and test Office 365 Cloud App Security to notify you of global admin activity</span></span>](https://technet.microsoft.com/library/mt757250.aspx)
    
- [<span data-ttu-id="40423-165">疑わしい電子メールの ATP を構成およびテストする</span><span class="sxs-lookup"><span data-stu-id="40423-165">Configure and test ATP for suspicious email</span></span>](https://technet.microsoft.com/library/mt490479.aspx)
    
- <span data-ttu-id="40423-166">上記の各手順について、試用版サブスクリプションの[Office 365 セキュリティスコア](https://securescore.office.com/)を確認する</span><span class="sxs-lookup"><span data-stu-id="40423-166">Check the [Office 365 Secure Score](https://securescore.office.com/) for your trial subscription for each of the above steps</span></span> 
    

