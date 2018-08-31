---
title: 個人情報の漏えいを監視する
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: 個人データの漏えいの監視に使用できる 3 つのツールについて説明します。
ms.openlocfilehash: b2ff4e686c3131260327b1c935603693eaa7f816
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272412"
---
# <a name="monitor-for-leaks-of-personal-data"></a><span data-ttu-id="84f9a-103">個人情報の漏えいを監視する</span><span class="sxs-lookup"><span data-stu-id="84f9a-103">Monitor for leaks of personal data</span></span>

<span data-ttu-id="84f9a-p101">個人データの使用と転送を監視するために使用できるツールは数多くあります。このトピックでは、効果的な 3 つのツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p101">There are many tools that can be used to monitor the use and transport of personal data. This topic describes three tools that work well.</span></span>

![個人データの使用と転送を監視するためのツール](Media/Monitor-for-leaks-of-personal-data-image1.png)

<span data-ttu-id="84f9a-107">この図について:</span><span class="sxs-lookup"><span data-stu-id="84f9a-107">In the illustration:</span></span>

-   <span data-ttu-id="84f9a-p102">まず、SharePoint Online、OneDrive for Business、転送中の電子メールの個人データを監視するための Office 365 データ損失防止レポートから開始します。このレポートは、個人データを監視するための最も詳細なレベルの内容を提供します。ただし、このレポートには Office 365 のすべてのサービスが含まれているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p102">Start with Office 365 data loss prevention reports for monitoring personal data in SharePoint Online, OneDrive for Business, and email in transit. These provide the greatest level of detail for monitoring personal data. However, these reports don’t include all services in Office 365.</span></span>

-   <span data-ttu-id="84f9a-p103">次に、アラート ポリシーと Office 365 監査ログを使用して、Office 365 サービス全体のアクティビティを監視します。進行中の監視を設定するか、または監査ログを検索してインシデントを調査します。Office 365 監査ログは、Sway、PowerBI、電子情報開示、Dynamics 365、Microsoft Flow、Microsoft Teams、管理アクティビティ、OneDrive for Business、SharePoint Online、転送中のメール、保存メールボックスなどの Office 365 サービス全体で機能します。Skype の会話は保存メールボックスに含まれます。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p103">Next, use alert policies and the Office 365 audit log to monitor activity across Office 365 services. Setup ongoing monitoring or search the audit log to investigate an incident. The Office 365 audit log works across Office 365 services — Sway, PowerBI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Admin activity, OneDrive for Business, SharePoint Online, mail in transit, and mailboxes at rest. Skype conversations are included in mailboxes at rest.</span></span>

-   <span data-ttu-id="84f9a-p104">最後に、Microsoft Cloud App Security を使用して、他の SaaS プロバイダーの機密データを含むファイルを監視します。Office 365 の機密情報タイプと統合ラベルを Azure Information Protection と Cloud App Security が有効な Office で使用できる機能が近日公開予定です。すべての SaaS アプリまたは特定のアプリ (ボックスなど) に適用するポリシーを設定できます。Cloud App Security では、電子メールに添付されたファイルを含め、Exchange Online のファイルは検出されません。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p104">Finally, Use Microsoft Cloud App Security to monitor files with sensitive data in other SaaS providers. Coming soon is the ability to use Office 365 sensitive information types and unified labels across Azure Information Protection and Office with Cloud App Security. You can setup policies that apply to all of your SaaS apps or specific apps (like Box). Cloud App Security doesn’t discover files in Exchange Online, including files attached to email.</span></span>

## <a name="office-365-data-loss-prevention-reports"></a><span data-ttu-id="84f9a-119">Office 365 データ損失防止レポート</span><span class="sxs-lookup"><span data-stu-id="84f9a-119">Office 365 data loss prevention reports</span></span>

<span data-ttu-id="84f9a-p105">データ損失防止 (DLP) ポリシーを作成したら、意図したとおりに動作し、コンプライアンスの遵守に役立っているか確認します。Office 365 の DLP レポートを使用すると、DLP ポリシーの一致項目、上書き、誤検知の数をすぐに確認したり、時間の経過とともに増加または減少する傾向があるかどうかを見極めたりできます。また、さまざまな方法でレポートをフィルター処理したり、グラフ上の系列の特定のポイントを選択して詳細情報を表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p105">After you create your data loss prevention (DLP) policies, you’ll want to verify that they’re working as you intended and helping you to stay compliant. With the DLP reports in Office 365, you can quickly view the number of DLP policy matches, overrides, or false positives; see whether they’re trending up or down over time; filter the report in different ways; and view additional details by selecting a point on a line on the graph.</span></span>

<span data-ttu-id="84f9a-122">DLP レポートを使用すると、以下のことを行えます。</span><span class="sxs-lookup"><span data-stu-id="84f9a-122">You can use the DLP reports to:</span></span>

-   <span data-ttu-id="84f9a-123">特定の期間に絞り込み、スパイクや傾向の理由を理解します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-123">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>

-   <span data-ttu-id="84f9a-124">組織の DLP ポリシーに違反するビジネス プロセスを検出します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-124">Discover business processes that violate your organization’s DLP policies.</span></span>

-   <span data-ttu-id="84f9a-125">DLP ポリシーのビジネスに及ぼす影響を理解します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-125">Understand any business impact of the DLP policies.</span></span>

-   <span data-ttu-id="84f9a-126">ユーザーがポリシーを上書きしたり、誤検知を報告したりしてポリシーのヒントを解決するときに送信する正当な理由を表示します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy or reporting a false positive.</span></span>

-   <span data-ttu-id="84f9a-127">特定の DLP ポリシーに関する一致箇所を表示することによって、そのポリシーのコンプライアンス遵守を確認します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-127">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>

-   <span data-ttu-id="84f9a-128">詳細ウィンドウで、DLP ポリシーに一致する機密データを含むファイルの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-128">View a list of files with sensitive data that matches your DLP policies in the details pane.</span></span>

<span data-ttu-id="84f9a-129">さらに、テスト モードで実行するときに、DLP レポートを使用して DLP ポリシーを微調整することができます。</span><span class="sxs-lookup"><span data-stu-id="84f9a-129">In addition, you can use the DLP reports to fine tune your DLP policies as you run them in test mode.</span></span>

<span data-ttu-id="84f9a-p106">DLP レポートは、セキュリティ/コンプライアンス センターにあります。[レポート] \> [レポートの表示] に移動し、[データ損失防止 (DLP)] の下で [DLP ポリシーおよびルールの一致] または [DLP の誤検知と上書き] に移動します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p106">DLP reports are in Security and Compliance center. Navigate to Reports \> View reports. Under Data loss prevention (DLP), go to either DLP policy and rule matches or DLP false positives and overrides.</span></span>

<span data-ttu-id="84f9a-133">詳細については、「[データ損失防止のレポートの表示](https://support.office.com/ja-JP/article/View-the-reports-for-data-loss-prevention-41eb4324-c513-4fa5-91c8-8fbd8aaba83b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84f9a-133">For more information, see [View the reports for data loss prevention](https://support.office.com/ja-JP/article/View-the-reports-for-data-loss-prevention-41eb4324-c513-4fa5-91c8-8fbd8aaba83b).</span></span>

![DLP ポリシーと一致することを示すレポート](Media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="office-365-audit-log-and-alert-policies"></a><span data-ttu-id="84f9a-135">Office 365 監査ログおよびアラートのポリシー</span><span class="sxs-lookup"><span data-stu-id="84f9a-135">Office 365 audit log and alert policies</span></span>

<span data-ttu-id="84f9a-136">Office 365 監査ログには、Exchange Online、SharePoint Online、OneDrive for Business、Azure Active Directory、Microsoft Teams、Power BI、Sway などの Office 365 サービスからのイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="84f9a-136">The Office 365 audit log contains events from Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway, and other Office 365 services.</span></span>

<span data-ttu-id="84f9a-137">Office 365 セキュリティ/コンプライアンス センターでは、Office 365 監査ログを監視およびレポートする 2 つの方法を提供しています。</span><span class="sxs-lookup"><span data-stu-id="84f9a-137">The Office 365 Security and Compliance Center provides two ways to monitor and report against the Office 365 audit log:</span></span>

-   <span data-ttu-id="84f9a-138">アラート ポリシーの設定、アラートの表示、トレンドの監視には、Office 365 セキュリティ/コンプライアンス センターにある新しいアラート ポリシーとアラート ダッシュボード ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-138">Setup alert policies, view alerts, and monitor trends — Use the new alert policy and alert dashboard tools in the Office 365 Security & Compliance Center.</span></span>

-   <span data-ttu-id="84f9a-p107">監査ログを直接検索するには、指定した日付の範囲ですべてのイベントを検索します。また、操作を実行したユーザー、操作、または対象オブジェクトなど、特定の条件に基づいて結果をフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p107">Search the audit log directly — Search for all events in a specified date rage. Or you can filter the results based on specific criteria, such as the user who performed the action, the action, or the target object.</span></span>

<span data-ttu-id="84f9a-p108">情報セキュリティおよびコンプライアンス チームは、これらのツールを使用して、エンド ユーザーと管理者の両方が Office 365 サービスで実行したアクティビティを予防的に確認することができます。特定のアクティビティが特定のサイト コレクションで発生した場合に (たとえば、GDPR 関連情報が含まれていることがわかっているサイトからコンテンツを共有する場合など)、電子メール通知を送信するように自動アラートを設定できます。これによってチームは、ユーザーをフォローアップして、企業のセキュリティ ポリシー遵守の徹底、追加のトレーニング提供などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p108">Information security and compliance teams can use these tools to proactively review activities performed by both end users and administrators across Office 365 services. Automatic alerts can be configured to send email notifications when certain activities occur on specific site collections - for example when content is shared from sites known to contain GDPR related information. This allows those teams to follow up with users to ensure that corporate security policies are followed, or to provide additional training.</span></span>

<span data-ttu-id="84f9a-p109">情報セキュリティ チームは、監査ログを検索して疑いのあるデータ侵害を調査し、根本原因と違反の程度の両方を判断することもできます。この組み込み機能は、GDPR の第 33 条および第 34 条の遵守を円滑にします。これらの条項では、データ違反について GDPR 監督当局およびデータ主体に、特定期間内に通知することが要求されています。監査ログ エントリは、サービス内で 90 日間のみ保持されます。多くの場合、これらのログをより長期間保持することが推奨され、多くの企業もそれを必要としていました。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p109">Information security teams can also search the audit log to investigate suspected data breaches and determine both root cause and the extent of the breach. This built in capability facilitates compliance with article 33 and 34 of the GDPR, which require notifications be provided to the GDPR supervisory authority and to the data subjects themselves of a data breach within a specific time period. Audit log entries are only retained for 90 days within the service - it is often recommended and many organizations required that these logs be retained for longer periods of time.</span></span>

<span data-ttu-id="84f9a-p110">Microsoft 管理アクティビティ API を使用して統一監査ログを購読し、必要に応じてログ エントリを保存し、高度なダッシュボードとアラートを提供することができるソリューションを活用できます。たとえば、[Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/ja-JP/azure/operations-management-suite/oms-solution-office-365) などです。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p110">Solutions are available which subscribe to the Unified Audit Logs through the Microsoft Management Activity API and can both store log entries as needed, and provide advanced dashboards and alerts. One example is [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/ja-JP/azure/operations-management-suite/oms-solution-office-365).</span></span>

<span data-ttu-id="84f9a-149">アラート ポリシーと監査ログの検索については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84f9a-149">More information about alert policies and searching the audit log:</span></span>

-   [<span data-ttu-id="84f9a-150">Office 365 セキュリティ/コンプライアンス センターのアラート ポリシー</span><span class="sxs-lookup"><span data-stu-id="84f9a-150">Alert policies in the Office 365 Security & Compliance Center</span></span>](https://support.office.com/ja-JP/article/Alert-policies-in-the-Office-365-Security-Compliance-Center-8927B8B9-C5BC-45A8-A9F9-96C732E58264)

-   <span data-ttu-id="84f9a-151">[Office 365 で監査ログを検索してユーザーと管理者のアクティビティを確認する](https://support.office.com/ja-JP/article/Search-the-audit-log-for-user-and-admin-activity-in-Office-365-57CA5138-0AE0-4D34-BD40-240441EF2FB6) (概要)</span><span class="sxs-lookup"><span data-stu-id="84f9a-151">[Search the audit log for user and admin activity in Office 365](https://support.office.com/ja-JP/article/Search-the-audit-log-for-user-and-admin-activity-in-Office-365-57CA5138-0AE0-4D34-BD40-240441EF2FB6) (introduction)</span></span>

-   [<span data-ttu-id="84f9a-152">Office 365 監査ログの検索を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="84f9a-152">Turn Office 365 audit log search on or off</span></span>](https://support.office.com/ja-JP/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)

-   <span data-ttu-id="84f9a-153">
  [Office 365 セキュリティ/コンプライアンス センターで監査ログを検索する](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US)</span><span class="sxs-lookup"><span data-stu-id="84f9a-153">[Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US)</span></span>

-   <span data-ttu-id="84f9a-154">
  [Search-UnifiedAuditLog](https://technet.microsoft.com/en-us/library/mt238501(v=exchg.160).aspx) (コマンドレット)</span><span class="sxs-lookup"><span data-stu-id="84f9a-154">[Search-UnifiedAuditLog](https://technet.microsoft.com/en-us/library/mt238501(v=exchg.160).aspx) (cmdlet)</span></span> 

-   [<span data-ttu-id="84f9a-155">Office 365 監査ログの詳細なプロパティ</span><span class="sxs-lookup"><span data-stu-id="84f9a-155">Detailed properties in the Office 365 audit log</span></span>](https://support.office.com/ja-JP/article/Detailed-properties-in-the-Office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3)

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="84f9a-156">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="84f9a-156">Microsoft Cloud App Security</span></span>

<span data-ttu-id="84f9a-157">Microsoft Cloud App Security は、ネットワーク上で使用されている他の SaaS アプリや、これらのアプリとの間でやり取りされる機密データを検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="84f9a-157">Microsoft Cloud App Security helps you discover other SaaS apps in use across your networks and sensitive data that is sent to and from these apps.</span></span>

<span data-ttu-id="84f9a-p111">Microsoft Cloud App Security は、クラウド アプリのための詳細な可視化、きめ細かいコントロール、高度な脅威の防止を提供する包括的なサービスです。ネットワーク上のすべてのデバイスから 15,000 以上のクラウド アプリケーションを識別し、リスク スコアリングや継続的なリスク評価と分析を提供します。ファイアウォールやプロキシから情報を収集して、クラウドの使用状況とシャドー IT に関する完全な可視性とコンテキストを提供するため、仲介は不要です。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p111">Microsoft Cloud App Security is a comprehensive service providing deep visibility, granular controls and enhanced threat protection for your cloud apps. It identifies more than 15,000 cloud applications in your network-from all devices-and provides risk scoring and ongoing risk assessment and analytics. No agents required: information is collected from your firewalls and proxies to give you complete visibility and context for cloud usage and shadow IT.</span></span>

<span data-ttu-id="84f9a-p112">クラウド環境をよりよく理解するために、Cloud App Security の調査機能は、承認および管理されているアプリのすべてのアクティビティ、ファイル、アカウントの詳細内容を可視化します。ファイル レベルの詳細な情報を取得し、クラウド アプリでのデータの移動を把握できます。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p112">To better understand your cloud environment, Cloud App Security investigate feature provides deep visibility into all activities, files and accounts for sanctioned and managed apps. You can gain detailed information on a file level and discover where data travels in the cloud apps.</span></span>

<span data-ttu-id="84f9a-163">たとえば、次の図は GDPR に役立つ 2 つのクラウド アプリケーション セキュリティ ポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="84f9a-163">For examples, the following illustration demonstrates two Cloud App Security policies that can help with GDPR.</span></span>

![クラウド アプリケーション セキュリティ ポリシーの例](Media/Monitor-for-leaks-of-personal-data-image3.png)

<span data-ttu-id="84f9a-165">1 番目のポリシーは、選択した事前定義の PII 属性またはカスタム式を持つファイルが、選択した SaaS アプリから組織外で共有されると警告します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-165">The first policy alerts when files with a predefined PII attribute or custom expression that you choose is shared outside the organization from the SaaS apps that you choose.</span></span>

<span data-ttu-id="84f9a-p113">2 番目のポリシーは、管理対象外のデバイスへのファイル ダウンロードをブロックします。検索するファイル内の属性と、ポリシーを適用する SaaS アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p113">The second policy blocks downloads of files to any unmanaged device. You choose the attributes within the files to look for and the SaaS apps you want the policy to apply to.</span></span>

<span data-ttu-id="84f9a-168">これらの属性タイプは、Cloud App Security に近日公開されます。</span><span class="sxs-lookup"><span data-stu-id="84f9a-168">These attribute types are coming soon to Cloud App Security:</span></span>

-   <span data-ttu-id="84f9a-169">Office 365 の機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="84f9a-169">Office 365 sensitive information types</span></span>

-   <span data-ttu-id="84f9a-170">Office 365 および Azure Information Protection での統一ラベル</span><span class="sxs-lookup"><span data-stu-id="84f9a-170">Unified labels across Office 365 and Azure Information Protection</span></span>

### <a name="cloud-app-security-dashboard"></a><span data-ttu-id="84f9a-171">Cloud App Security ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="84f9a-171">Cloud App Security dashboard</span></span>

<span data-ttu-id="84f9a-p114">まだ Cloud App Security の使用を開始していない場合は、まず開始してください。Cloud App Security には <https://portal.cloudappsecurity.com> からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p114">If you haven’t yet started to use Cloud App Security, begin by starting it up. To access Cloud App Security: <https://portal.cloudappsecurity.com>.</span></span>

<span data-ttu-id="84f9a-p115">メモ: Cloud App Security の使用を開始するときやラベルを割り当てる前に、[一般設定] の [Azure Information Protection 分類ラベルについてファイルを自動的にスキャンする] を有効にしてください。設定後は、Cloud App Security は、変更されるまで既存ファイルを再スキャンしません。</span><span class="sxs-lookup"><span data-stu-id="84f9a-p115">Note: Be sure to enable ‘Automatically scan files for Azure Information Protection classification labels’ (in General settings) when getting started with Cloud App Security or before you assign labels. After setup, Cloud App Security does not scan existing files again until they are modified.</span></span>

![アラートに関する情報を表示するダッシュボード](Media/Monitor-for-leaks-of-personal-data-image4.png)

<span data-ttu-id="84f9a-177">詳しくは、以下の資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84f9a-177">More information:</span></span>

-   [<span data-ttu-id="84f9a-178">Cloud App Security を展開する</span><span class="sxs-lookup"><span data-stu-id="84f9a-178">Deploy Cloud App Security</span></span>](https://docs.microsoft.com/ja-JP/cloud-app-security/getting-started-with-cloud-app-security)

-   [<span data-ttu-id="84f9a-179">Microsoft Cloud App Security の詳細情報</span><span class="sxs-lookup"><span data-stu-id="84f9a-179">More information about Microsoft Cloud App Security</span></span>](https://www.microsoft.com/ja-JP/cloud-platform/cloud-app-security)

-   [<span data-ttu-id="84f9a-180">Microsoft Cloud App Security プロキシを使用して機密情報のダウンロードをブロックする</span><span class="sxs-lookup"><span data-stu-id="84f9a-180">Block downloads of sensitive information using the Microsoft Cloud App Security proxy</span></span>](https://docs.microsoft.com/ja-JP/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a><span data-ttu-id="84f9a-181">個人データの共有を検出するためのファイル ポリシーとアクティビティ ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="84f9a-181">Example file and activity policies to detect sharing of personal data</span></span>

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a><span data-ttu-id="84f9a-182">PII (クレジット カード番号) を含むファイルの共有を検出する</span><span class="sxs-lookup"><span data-stu-id="84f9a-182">Detect sharing of files containing PII — Credit card number</span></span>

<span data-ttu-id="84f9a-183">承認されたクラウド アプリから、クレジット カード番号を含むファイルが共有されたときに警告します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-183">Alert when a file containing a credit card number is shared from an approved cloud app.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="84f9a-184"><strong>コントロール</strong></span><span class="sxs-lookup"><span data-stu-id="84f9a-184"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="84f9a-185"><strong>設定</strong></span><span class="sxs-lookup"><span data-stu-id="84f9a-185"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="84f9a-186">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="84f9a-186">Policy type</span></span></td>
<td align="left"><span data-ttu-id="84f9a-187">ファイル ポリシー</span><span class="sxs-lookup"><span data-stu-id="84f9a-187">File policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="84f9a-188">ポリシー テンプレート</span><span class="sxs-lookup"><span data-stu-id="84f9a-188">Policy template</span></span></td>
<td align="left"><span data-ttu-id="84f9a-189">テンプレートなし</span><span class="sxs-lookup"><span data-stu-id="84f9a-189">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="84f9a-190">ポリシーの重要度</span><span class="sxs-lookup"><span data-stu-id="84f9a-190">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="84f9a-191">高</span><span class="sxs-lookup"><span data-stu-id="84f9a-191">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="84f9a-192">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="84f9a-192">Category</span></span></td>
<td align="left"><span data-ttu-id="84f9a-193">DLP</span><span class="sxs-lookup"><span data-stu-id="84f9a-193">DLP</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="84f9a-194">フィルター設定</span><span class="sxs-lookup"><span data-stu-id="84f9a-194">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="84f9a-195">Access level = Public (Internet), Public, External</span><span class="sxs-lookup"><span data-stu-id="84f9a-195">Access level = Public (Internet), Public, External</span></span></p>
<p><span data-ttu-id="84f9a-196">App = &lt;select apps&gt; (特定の SaaS アプリに監視を制限する場合は、この設定を使用します)</span><span class="sxs-lookup"><span data-stu-id="84f9a-196">App = &lt;select apps&gt; (use this setting if you want to limit monitoring to specific SaaS apps)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="84f9a-197">適用先</span><span class="sxs-lookup"><span data-stu-id="84f9a-197">Apply to</span></span></td>
<td align="left"><span data-ttu-id="84f9a-198">すべてのファイル、すべての所有者</span><span class="sxs-lookup"><span data-stu-id="84f9a-198">All files, all owners</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="84f9a-199">内容の検査</span><span class="sxs-lookup"><span data-stu-id="84f9a-199">Content inspection</span></span></td>
<td align="left"><p><span data-ttu-id="84f9a-200">現在の式に一致するファイルを含む: All countries: Finance: Credit card number</span><span class="sxs-lookup"><span data-stu-id="84f9a-200">Includes files that match a present expression: All countries: Finance: Credit card number</span></span></p>
<p><span data-ttu-id="84f9a-201">関連するコンテキストを必要としない: オフ (これはキーワードと正規表現に一致します)</span><span class="sxs-lookup"><span data-stu-id="84f9a-201">Don’t require relevant context: unchecked (this will match keywords as well as regex)</span></span></p>
<p><span data-ttu-id="84f9a-202">1 つでも一致するファイルを含む</span><span class="sxs-lookup"><span data-stu-id="84f9a-202">Includes files with at least 1 match</span></span></p>
<p><span data-ttu-id="84f9a-203">違反の最後の 4 文字をマスク解除する: オン</span><span class="sxs-lookup"><span data-stu-id="84f9a-203">Unmask the last 4 characters of the violation: checked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="84f9a-204">アラート</span><span class="sxs-lookup"><span data-stu-id="84f9a-204">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="84f9a-205">一致するファイルごとにアラートを作成する: オン</span><span class="sxs-lookup"><span data-stu-id="84f9a-205">Create an alert for each matching file: checked</span></span></p>
<p><span data-ttu-id="84f9a-206">1 日のアラート制限: 1000</span><span class="sxs-lookup"><span data-stu-id="84f9a-206">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="84f9a-207">電子メールとしてアラートを選択する: オン</span><span class="sxs-lookup"><span data-stu-id="84f9a-207">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="84f9a-208">宛先: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="84f9a-208">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="84f9a-209">ガバナンス</span><span class="sxs-lookup"><span data-stu-id="84f9a-209">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="84f9a-210">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="84f9a-210">Microsoft OneDrive for Business</span></span></p>
<p><span data-ttu-id="84f9a-211">非公開にする: 外部ユーザーの削除をオン</span><span class="sxs-lookup"><span data-stu-id="84f9a-211">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="84f9a-212">その他のすべての設定: オフ</span><span class="sxs-lookup"><span data-stu-id="84f9a-212">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="84f9a-213">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="84f9a-213">Microsoft SharePoint Online</span></span></p>
<p><span data-ttu-id="84f9a-214">非公開にする: 外部ユーザーの削除をオン</span><span class="sxs-lookup"><span data-stu-id="84f9a-214">Make private: check Remove External Users</span></span></p>
<p><span data-ttu-id="84f9a-215">その他のすべての設定: オフ</span><span class="sxs-lookup"><span data-stu-id="84f9a-215">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84f9a-216">類似のポリシー:</span><span class="sxs-lookup"><span data-stu-id="84f9a-216">Similar policies:</span></span>

-   <span data-ttu-id="84f9a-217">PII (メール アドレス) を含むファイルの共有を検出する</span><span class="sxs-lookup"><span data-stu-id="84f9a-217">Detect sharing of Files containing PII - Email Address</span></span>

-   <span data-ttu-id="84f9a-218">PII (パスポート番号) を含むファイルの共有を検出する</span><span class="sxs-lookup"><span data-stu-id="84f9a-218">Detect sharing of Files containing PII - Passport Number</span></span>

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a><span data-ttu-id="84f9a-219">Box for Business または OneDrive for Business の顧客データや人事データを検出する</span><span class="sxs-lookup"><span data-stu-id="84f9a-219">Detect Customer or HR Data in Box or OneDrive for Business</span></span>

<span data-ttu-id="84f9a-220">OneDrive for Business または Box for Business に Customer Data (顧客データ) または HR Data (人事データ) という名前のファイルがアップロードされたときに警告します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-220">Alert when a file labeled as Customer Data or HR Data is uploaded to OneDrive for Business or Box.</span></span>

<span data-ttu-id="84f9a-221">注:</span><span class="sxs-lookup"><span data-stu-id="84f9a-221">Notes:</span></span>

-   <span data-ttu-id="84f9a-222">Box の監視では、API Connector SDK を使用してコネクタを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84f9a-222">Box monitoring requires a connector be configured using the API Connector SDK.</span></span>

-   <span data-ttu-id="84f9a-223">このポリシーには、現在プライベート プレビューになっている機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="84f9a-223">This policy requires capabilities that are currently in private preview.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="84f9a-224"><strong>コントロール</strong></span><span class="sxs-lookup"><span data-stu-id="84f9a-224"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="84f9a-225"><strong>設定</strong></span><span class="sxs-lookup"><span data-stu-id="84f9a-225"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="84f9a-226">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="84f9a-226">Policy type</span></span></td>
<td align="left"><span data-ttu-id="84f9a-227">アクティビティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="84f9a-227">Activity policy</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="84f9a-228">ポリシー テンプレート</span><span class="sxs-lookup"><span data-stu-id="84f9a-228">Policy template</span></span></td>
<td align="left"><span data-ttu-id="84f9a-229">テンプレートなし</span><span class="sxs-lookup"><span data-stu-id="84f9a-229">No template</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="84f9a-230">ポリシーの重要度</span><span class="sxs-lookup"><span data-stu-id="84f9a-230">Policy severity</span></span></td>
<td align="left"><span data-ttu-id="84f9a-231">高</span><span class="sxs-lookup"><span data-stu-id="84f9a-231">High</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="84f9a-232">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="84f9a-232">Category</span></span></td>
<td align="left"><span data-ttu-id="84f9a-233">制御を共有</span><span class="sxs-lookup"><span data-stu-id="84f9a-233">Sharing Control</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="84f9a-234">操作対象</span><span class="sxs-lookup"><span data-stu-id="84f9a-234">Act on</span></span></td>
<td align="left"><span data-ttu-id="84f9a-235">1 つのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="84f9a-235">Single activity</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="84f9a-236">フィルター設定</span><span class="sxs-lookup"><span data-stu-id="84f9a-236">Filter settings</span></span></td>
<td align="left"><p><span data-ttu-id="84f9a-237">アクティビティの種類 = ファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="84f9a-237">Activity type = Upload File</span></span></p>
<p><span data-ttu-id="84f9a-238">アプリ = Microsoft OneDrive for Business および Box</span><span class="sxs-lookup"><span data-stu-id="84f9a-238">App = Microsoft OneDrive for Business and Box</span></span></p>
<p><span data-ttu-id="84f9a-239">分類ラベル (現在はプライベート プレビュー): Azure Information Protection = 顧客データ、人事—給与データ、人事—従業員データ</span><span class="sxs-lookup"><span data-stu-id="84f9a-239">Classification Label (currently in private preview): Azure Information Protection = Customer Data, Human Resources—Salary Data, Human Resources—Employee Data</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="84f9a-240">アラート</span><span class="sxs-lookup"><span data-stu-id="84f9a-240">Alerts</span></span></td>
<td align="left"><p><span data-ttu-id="84f9a-241">アラートを作成する: オン</span><span class="sxs-lookup"><span data-stu-id="84f9a-241">Create an alert: checked</span></span></p>
<p><span data-ttu-id="84f9a-242">1 日のアラート制限: 1000</span><span class="sxs-lookup"><span data-stu-id="84f9a-242">Daily alert limit: 1000</span></span></p>
<p><span data-ttu-id="84f9a-243">電子メールとしてアラートを選択する: オン</span><span class="sxs-lookup"><span data-stu-id="84f9a-243">Select an alert as email: checked</span></span></p>
<p><span data-ttu-id="84f9a-244">宛先: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="84f9a-244">To: infosec@contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="84f9a-245">ガバナンス</span><span class="sxs-lookup"><span data-stu-id="84f9a-245">Governance</span></span></td>
<td align="left"><p><span data-ttu-id="84f9a-246">すべてのアプリ</span><span class="sxs-lookup"><span data-stu-id="84f9a-246">All apps</span></span></p>
<p><span data-ttu-id="84f9a-247">ユーザーを検疫に入れる: オン</span><span class="sxs-lookup"><span data-stu-id="84f9a-247">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="84f9a-248">その他のすべての設定: オフ</span><span class="sxs-lookup"><span data-stu-id="84f9a-248">All other settings: unchecked</span></span></p>
<p><span data-ttu-id="84f9a-249">Office 365</span><span class="sxs-lookup"><span data-stu-id="84f9a-249">Office 365</span></span></p>
<p><span data-ttu-id="84f9a-250">ユーザーを検疫に入れる: オン</span><span class="sxs-lookup"><span data-stu-id="84f9a-250">Put user in quarantine: check</span></span></p>
<p><span data-ttu-id="84f9a-251">その他のすべての設定: オフ</span><span class="sxs-lookup"><span data-stu-id="84f9a-251">All other settings: unchecked</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84f9a-252">類似のポリシー:</span><span class="sxs-lookup"><span data-stu-id="84f9a-252">Similar policies:</span></span>

-   <span data-ttu-id="84f9a-253">顧客データや人事データの大量ダウンロードを検出する — 顧客データや人事データを含む多数のファイルが、単一ユーザーによって短時間にダウンロードされたことが検出されたときに警告します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-253">Detect large downloads of Customer data or HR Data — Alert when a large number of files containing customer data or HR data have been detected being downloaded by a single user within a short period of time.</span></span>

-   <span data-ttu-id="84f9a-254">顧客および人事データの共有を検出する — 顧客または人事データを含むファイルが共有されたときに警告します。</span><span class="sxs-lookup"><span data-stu-id="84f9a-254">Detect Sharing of Customer and HR Data — Alert when files containing Customer or HR Data are shared.</span></span>
