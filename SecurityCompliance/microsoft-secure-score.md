---
title: Microsoft セキュリティスコア
description: Microsoft 365 のセキュリティスコア、詳細の計算方法、およびセキュリティ管理者がどのように使用することを期待できるかについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティで保護されたスコア、セキュリティセンター、改善アクション
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: de3abe7ca0e84efd2412984e172202d8f3962476
ms.sourcegitcommit: 9d48b656406e916e93651352692c5c6bcbbd645f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "30203731"
---
# <a name="microsoft-secure-score-preview"></a><span data-ttu-id="d116c-104">Microsoft セキュリティスコア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d116c-104">Microsoft Secure Score (Preview)</span></span>

<span data-ttu-id="d116c-p101">microsoft 365 セキュリティセンターでは、microsoft セキュリティスコアを使用して、組織のセキュリティ体制をさらに可視化し、制御することができます。一元管理されたダッシュボードから、Microsoft 365 の id、データ、アプリ、デバイス、およびインフラストラクチャのセキュリティを監視し、強化することができます。</span><span class="sxs-lookup"><span data-stu-id="d116c-p101">With Microsoft Secure Score in the Microsoft 365 security center, you can have increased visibility and control over your organization’s security posture. From a centralized dashboard you can monitor and improve the security for your Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="d116c-p102">microsoft のセキュリティで保護されたスコアは、堅牢な視覚エフェクト、他の Microsoft 製品との統合、他の企業とのスコアの比較、カテゴリ別のフィルタリングなどを提供します。このツールを使用すると、組織内のセキュリティ強化アクションを完了し、スコアの履歴を追跡することができます。このスコアは、サードパーティ製のソリューションが推奨される改善アクションに対応している場合にも反映できます。</span><span class="sxs-lookup"><span data-stu-id="d116c-p102">Microsoft Secure Score gives you robust visualizations, integration with other Microsoft products, comparison of your score with other companies, filtering by category, and much more. With the tool, you can complete security improvement actions within your organization and track the history of your score. The score can also reflect when third-party solutions have addressed recommended improvement actions.</span></span>  

## <a name="how-it-works"></a><span data-ttu-id="d116c-110">しくみ</span><span class="sxs-lookup"><span data-stu-id="d116c-110">How it works</span></span>

<span data-ttu-id="d116c-p103">推奨されるセキュリティ機能を構成するためのポイント、セキュリティ関連タスクの実行 (レポートの表示など)、またはサードパーティ製のアプリケーションまたはソフトウェアを使用した改善アクションへの対応を行います。一部のアクションは、ユーザーに対して多要素認証 (MFA) を有効にするなど、部分的な完了のスコアを獲得します。セキュリティは常にユーザビリティにバランスをとる必要があり、お客様の環境ですべての推奨事項が機能するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d116c-p103">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software. Some actions are scored for partial completion, like enabling multi-factor authentication (MFA) for your users. Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="d116c-114">必要な権限:</span><span class="sxs-lookup"><span data-stu-id="d116c-114">Required permissions</span></span>

<span data-ttu-id="d116c-115">現時点では、Microsoft セキュリティスコアを表示するには、Azure Active Directory に次のいずれかのロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d116c-115">Currently, to view Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory:</span></span>

* <span data-ttu-id="d116c-116">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="d116c-116">Global Administrator</span></span>
* <span data-ttu-id="d116c-117">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="d116c-117">Security Administrator</span></span>
* <span data-ttu-id="d116c-118">セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="d116c-118">Security Reader</span></span>

## <a name="rich-experiences--additional-security-recommendations"></a><span data-ttu-id="d116c-119">豊富なエクスペリエンス & その他のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="d116c-119">Rich experiences & additional security recommendations</span></span>

<span data-ttu-id="d116c-p104">Microsoft のセキュリティで保護されたスコアでは、azure の AD、Intune、および Cloud App Security から推奨事項が追加されており、azure セキュリティセンターと Windows Defender ATP の推奨事項が近日中に提供されています。また、Office 365 のセキュリティに関する推奨事項をさらに追加しました。より広範な Microsoft 製品およびサービスのセットについて、さらに洞察を得られるようになるため、組織のセキュリティの状態についての管理者による報告を自信を持って考えることができます。[Microsoft Graph API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta)を使用してスコアを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="d116c-p104">In Microsoft Secure Score, we’ve added recommendations from Azure AD, Intune, and Cloud App Security, with recommendations from Azure Security Center and Windows Defender ATP coming soon. We've also added even more Office 365 security recommendations. With additional insights and more visibility into a broader set of Microsoft products and services, you can feel confident reporting up to management about your organization’s security health. You can also get your score using the [Microsoft Graph API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta).</span></span>

<span data-ttu-id="d116c-124">より迅速に必要な情報を提供するために、Microsoft の推奨事項がグループに分類されています。</span><span class="sxs-lookup"><span data-stu-id="d116c-124">To help you the information you need more quickly, Microsoft recommendations are organized into groups:</span></span>

* <span data-ttu-id="d116c-125">Identity (Azure AD アカウントとロールの保護状態)</span><span class="sxs-lookup"><span data-stu-id="d116c-125">Identity (protection state of your Azure AD accounts and roles)</span></span>
* <span data-ttu-id="d116c-126">データ (Office 365 ドキュメントの保護状態)</span><span class="sxs-lookup"><span data-stu-id="d116c-126">Data (protection state of your Office 365 documents)</span></span>
* <span data-ttu-id="d116c-127">デバイス (デバイスの保護状態。Windows Defender ATP の改善アクションが近日中に予定される)</span><span class="sxs-lookup"><span data-stu-id="d116c-127">Device (protection state of your devices; Windows Defender ATP improvement actions coming soon)</span></span>
* <span data-ttu-id="d116c-128">アプリ (電子メールとクラウドアプリの保護状態)</span><span class="sxs-lookup"><span data-stu-id="d116c-128">App (protection state of your email and cloud apps)</span></span>
* <span data-ttu-id="d116c-129">インフラストラクチャ (Azure リソースの保護状態、近日予定)</span><span class="sxs-lookup"><span data-stu-id="d116c-129">Infrastructure (protection state of your Azure resources; coming soon)</span></span>

<span data-ttu-id="d116c-p105">[Microsoft セキュリティスコアの概要] ページでは、これらのグループ間のポイントの分割方法と、使用可能なポイントを確認できます。また、概要ページでは、スコアの合計を表示し、セキュリティで保護されたスコアの傾向をベンチマーク比較によって把握し、スコアを向上させるために実行できる改善措置の優先順位付けを行うことができます。このデータを使用して、セキュリティに関する姿勢を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="d116c-p105">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available. The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score. You can use this data to act and make big differences in your security posture.</span></span>  

<span data-ttu-id="d116c-133">![M365 ホーム](./media/secure-score/homepage-original.png)
ページ*図 1: Microsoft のセキュリティで保護されたスコアの概要ページ*</span><span class="sxs-lookup"><span data-stu-id="d116c-133">![M365 homepage](./media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="d116c-134">スコアを向上させるためのアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="d116c-134">Take action to improve your score</span></span>

<span data-ttu-id="d116c-p106">[向上したアクション] タブには、テナントに適用可能なすべてのセキュリティ推奨が表示されます (完了、完了、未完了、サードパーティによる解決、無視)。すべてのコントロールを検索、フィルター、およびグループ化することができます。 ランク付けは、Microsoft による、セキュリティ価値と完了作業の両方の評価に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="d116c-p106">The improvement actions tab lists all the security recommendations applicable to your tenant along with their status (completed, not completed, resolved through third party, and ignored). You can search, filter, and group all the controls.  Ranking is based on Microsoft’s evaluation of both security value and effort to complete.</span></span>

<span data-ttu-id="d116c-p107">[採点なし] というラベルの付いたアクションは、Microsoft セキュリティスコアで追跡されません。それでもアクションを実行することはできますが、スコアに影響を与えることはありません。将来的に Microsoft セキュリティスコアによってアクションが追跡され、既に完了している場合は、その変更がセキュリティスコアに自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="d116c-p107">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score. You can still take action but completing them will not affect your score. If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="d116c-p108">向上アクションをクリックすると、フライアウトが表示されます。この操作を完了するには、いくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="d116c-p108">When you click on an improvement action, a fly out appears. To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="d116c-p109">[**ビューの設定**] を選択して構成画面に移動し、変更を行います。その後、スライドの上部に表示される、アクションに価値があるポイントを取得します。ポイントの更新には最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d116c-p109">Select **View settings** to go the configuration screen and make the change. You will then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="d116c-p110">向上アクションがサードパーティ製のアプリケーションまたはソフトウェアによって既に処理されているため、[**サードパーティによる解決**] を選択します。この操作に必要なポイントが得られます。したがって、セキュリティの全体的な姿勢がより適切に反映されます。サードパーティがコントロールをカバーしなくなった場合は、[改善] アクションを未完了としてマークすることができます。Microsoft は、改善アクションがサードパーティによって解決済みとしてマークされている場合に、スコア要件が満たされているかどうかを確認することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d116c-p110">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software. You will gain the points that the action is worth, so your secure score better reflects your overall security posture. If a third party no longer covers the control, you can mark the improvement action as not complete. Please keep in mind, Microsoft will have no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="d116c-p111">リスクを受け入れることを決定していて、改善アクションが実行されていないため、[**無視**] を選択します。[改善] アクションを無視すると、達成できるセキュリティで保護されたスコアポイントの合計数が減少します。このアクションは、履歴で表示するか、いつでも元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="d116c-p111">Select **Ignore** because you have decided to accept the risk and not enact the improvement action. Once you ignore an improvement action, the total number of secure score points you can achieve will be reduced. You can view this action in history or undo it at any time.</span></span>

4. <span data-ttu-id="d116c-p112">改善アクションでは、環境の一部を定期的に確認してポイントを取得および保持する必要があるので、[**確認**] を選択します。たとえば、ネットワークからデータが抜き出しされないように、メールボックス転送ルールを週単位で確認する必要があります。変更を加える必要はありませんが、アクションを実行する必要があります。ルールを定期的に確認すると、ポイントが表示されます。指定しない場合は、スコアが減少します。</span><span class="sxs-lookup"><span data-stu-id="d116c-p112">Select **Review** because the improvement action requires you to regularly review a part of your environment to gain and retain points. For example, mailbox forwarding rules should be reviewed on a weekly basis to make sure data is not being exfiltrated from your network. You do not need to make any changes, but an action will need to be performed. If you regularly review the rules, you will receive the points. If not, the score will be reduced.</span></span>

![M365 ホームページ](./media/secure-score/secure-score1x450.png) ![M365 ホームページ](./media/secure-score/secure-score2x450.png)

<span data-ttu-id="d116c-159">*図 2 & 3: 改善アクションの flyouts*</span><span class="sxs-lookup"><span data-stu-id="d116c-159">*Figures 2 & 3: Improvement action flyouts*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="d116c-160">時間の経過に伴う向上を監視する</span><span class="sxs-lookup"><span data-stu-id="d116c-160">Monitor improvements over time</span></span>

<span data-ttu-id="d116c-p113">時間の経過とともに組織のスコアをグラフで確認するには、[**履歴**] タブを使用します。このビューには、選択した時間範囲内で行われたすべてのアクションと共に、グローバルな平均、業界の平均、および同様の座席数が含まれます。日付範囲をカスタマイズしたり、カテゴリ別にフィルター処理したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d116c-p113">You can view a graph of your organization's score over time in the **History** tab. This view includes the global average, industry average, and similar seat count, along with all the actions taken in the selected time range. You can also customize a date range and filter by category.</span></span>

<span data-ttu-id="d116c-p114">スコアは1日に1回 (約 1:00 AM PST) 計算されます。測定されたアクションに変更を加えると、スコアは翌日を自動的に更新します。また、他のいくつかのポータルは Microsoft のセキュリティで保護されたスコア (Windows Defender セキュリティセンターなど) の一部を示していることにも注意する必要があります。改善アクションを完了し、これらのポータルでスコアが増加した場合は、更新されたスコアが Microsoft 365 セキュリティセンターに表示されるまでに最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d116c-p114">The score is calculated once per day (around 1:00 AM PST). If you make a change to a measured action, the score will automatically update the next day. It is also important to note that some other portals show parts of the Microsoft Secure Score (like Windows Defender Security Center). If you complete an improvement action and the score is increased in those portals, it may take up to 24 hours for the updated score to display in Microsoft 365 security center.</span></span>  

## <a name="risk-awareness"></a><span data-ttu-id="d116c-167">リスクの認識</span><span class="sxs-lookup"><span data-stu-id="d116c-167">Risk awareness</span></span>

<span data-ttu-id="d116c-p115">Microsoft Secure Score は、システム構成、ユーザーの行動、およびその他のセキュリティ関連の測定値に基づいて、セキュリティの状況を示す数値の概要です。システムまたはデータが侵害される可能性の絶対的な測定値ではありません。そうではなく、侵害されるリスクを相殺できるように、Microsoft 環境にセキュリティコントロールを採用している範囲を表しています。セキュリティ侵害から完全に保護されていないオンラインサービスはないため、セキュリティ違反に対する保証として、どのような方法でも安全スコアを解釈しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d116c-p115">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached. Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached. No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="d116c-171">ご意見をお聞かせください</span><span class="sxs-lookup"><span data-stu-id="d116c-171">We want to hear from you</span></span>

<span data-ttu-id="d116c-p116">問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)コミュニティ」に投稿してお知らせください。コミュニティを監視しており、ヘルプを提供しています。</span><span class="sxs-lookup"><span data-stu-id="d116c-p116">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community. We're monitoring the community and will provide help.</span></span>