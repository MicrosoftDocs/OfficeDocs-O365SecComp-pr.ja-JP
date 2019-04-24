---
title: Office 365 セキュア スコア
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: Office 365 で組織が実際にセキュリティで保護されているかどうかが疑問になるかもしれません。 セキュリティで保護されたスコアは、ヘルプを提供します。 セキュリティで保護されたスコア Office 365 の通常のアクティビティとセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てます。
ms.openlocfilehash: dd0dc87910853eba9f2ec3ec6752e857462b46e5
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262471"
---
# <a name="office-365-secure-score"></a><span data-ttu-id="2d7d0-105">Office 365 セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="2d7d0-105">Office 365 Secure Score</span></span>

<span data-ttu-id="2d7d0-106">**概要**Office 365 で組織が実際にセキュリティで保護されているかどうかが疑問になるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-106">**Summary** Ever wonder how secure your organization really is in Office 365?</span></span> <span data-ttu-id="2d7d0-107">セキュリティで保護されたスコアは、ヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-107">Secure Score is here to help.</span></span> <span data-ttu-id="2d7d0-108">セキュリティで保護されたスコア Office 365 の通常のアクティビティとセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-108">Secure Score analyzes your organization's security  based on your regular activities and security settings in Office 365, and assigns a score.</span></span> <span data-ttu-id="2d7d0-109">この記事では、セキュリティで保護されたスコアの概要とその使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-109">Read this article to get an overview of Secure Score and how you can use it.</span></span>
  
## <a name="how-to-get-to-secure-score"></a><span data-ttu-id="2d7d0-110">セキュリティで保護されたスコアを得る方法</span><span class="sxs-lookup"><span data-stu-id="2d7d0-110">How to get to Secure Score</span></span>

<span data-ttu-id="2d7d0-111">[office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/)、 [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/)、または office 365 Business Premium を含むサブスクリプションが組織にあり、[必要なアクセス許可](#required-permissions)を持っている場合は、にアクセスして、組織のセキュリティスコアを表示することができます。[https://securescore.office.com](https://securescore.office.com).</span><span class="sxs-lookup"><span data-stu-id="2d7d0-111">If your organization has a subscription that includes [Office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/), or Office 365 Business Premium, and you have the [necessary permissions](#required-permissions), you can view your organization's secure score by visiting [https://securescore.office.com](https://securescore.office.com).</span></span> 

<span data-ttu-id="2d7d0-112">または、セキュリティ & コンプライアンスセンター ([https://protection.office.com](https://protection.office.com)) にアクセスすることもできます。ここでは、現在のスコアを提供するセキュリティで保護されたスコアウィジェットを検索できます。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-112">Alternatively, you can visit the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), where you'll find a Secure Score widget that provides you with your current score.</span></span>

![セキュリティで保護されたスコアウィジェット](media/SecureScoreWidget-o365.png)

<span data-ttu-id="2d7d0-114">ウィジェットには、セキュリティで保護されたスコアダッシュボードへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-114">The widget includes a link to your Secure Score dashboard.</span></span>

![セキュリティスコアダッシュボード](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a><span data-ttu-id="2d7d0-116">メカニズム</span><span class="sxs-lookup"><span data-stu-id="2d7d0-116">How it works</span></span>

<span data-ttu-id="2d7d0-117">セキュリティで保護されたスコアは、使用している Office 365 サービス (OneDrive、SharePoint、Exchange など) を決定し、Microsoft によって確立されたベースラインに設定とアクティビティを比較します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-117">Secure Score determines what Office 365 services you're using (such as OneDrive, SharePoint, and Exchange) then compares your settings and activities to a baseline established by Microsoft.</span></span> <span data-ttu-id="2d7d0-118">セキュリティのベストプラクティスを使用して、組織がどの程度適切に調整されているかに基づいてスコアを得られます。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-118">You'll get a score based on how well aligned your organization is with security best practices.</span></span> <span data-ttu-id="2d7d0-119">組織のスコアを向上させるための手順についても、推奨事項を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-119">You'll also get recommendations on steps you can take to improve your organization's score.</span></span> 
  
![Office 365 のセキュリティスコアツールのアクションキュー](media/SecureScore-ActionsToTake.png)
  
<span data-ttu-id="2d7d0-121">セキュリティで保護されたスコアは、購入したサービスに基づいてスコアを計算します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-121">Secure Score calculates your score based on the services you purchased.</span></span> <span data-ttu-id="2d7d0-122">たとえば、Exchange online プランのみを購入した場合、SharePoint online のセキュリティ機能はスコアされません。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-122">For example, if you only purchased an Exchange Online plan, you won't be scored for SharePoint Online security features.</span></span> <span data-ttu-id="2d7d0-123">スコアの分母は、購入した製品に適用されるコントロールのすべてのベースラインの合計です。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-123">The denominator of the score is the sum of all the baselines for the controls that apply to the products you purchased.</span></span> <span data-ttu-id="2d7d0-124">分子は、完了または部分的に完了したすべてのコントロールを合計したもので、そのコントロールを満たす操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-124">The numerator is the sum of all the controls for which you completed, or partially completed, the actions to fulfill that control.</span></span>

<span data-ttu-id="2d7d0-125">アクションを展開して、実行する手順、保護に役立つ脅威、および推奨事項に従ってスコアを上げるポイント数について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-125">Expand an action to learn about what steps to take, the threats it'll help protect you from, and how many points your score will increase once you follow the recommendation.</span></span>
  
![Office 365 のセキュリティスコアツールの拡張されたアクション](media/SecureScore-DetailedActionToTake.png)
  
<span data-ttu-id="2d7d0-127">組織のセキュリティに対する操作の影響を確認するには、[**スコアアナライザー** ] タブを選択し、履歴を確認します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-127">To see the impact of your actions on your organization's security, select the **Score Analyzer** tab and review your history.</span></span> 
  
![Office 365 セキュリティスコアツールのスコアアナライザータブ](media/SecureScore-ScoreAnalyzer-7days.png)
  
<span data-ttu-id="2d7d0-129">グラフの下に、カテゴリ別のスコアとアクションの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-129">Below the chart, you'll see a list of scores and actions by category.</span></span> 
  
![データポイントが選択されたことを示すスコアアナライザータブのグラフ](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
<span data-ttu-id="2d7d0-131">**[採点なし]** というラベルの付いたアクションは、組織に対して実行できるものですが、セキュリティで保護されたスコアに接続されていないため、スコアされません。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-131">Actions that are labeled as **[Not Scored]** are ones you can perform for your organization, but because they are not connected to Secure Score, they are not scored.</span></span>  

<span data-ttu-id="2d7d0-132">[**スコアアナライザー** ] ページで、特定の日のデータポイントをクリックし、下にスクロールして、その日の完了および未完了のアクションを確認し、変更内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-132">On the **Score Analyzer** page, click a data point for a specific day, then scroll down to see the completed and incomplete actions for that day to find out what changed.</span></span> <span data-ttu-id="2d7d0-133">スコアは1日に1回 (約 1:00 AM PST) 計算されます。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-133">The score is calculated once per day (around 1:00 AM PST).</span></span> <span data-ttu-id="2d7d0-134">測定されたアクションに変更を加えると、スコアは翌日を自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-134">If you make a change to a measured action, the score will automatically update the next day.</span></span> <span data-ttu-id="2d7d0-135">スコアに変更を反映するには、最大48時間かかります。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-135">It takes up to 48 hours for a change to be reflected in your score.</span></span>

<span data-ttu-id="2d7d0-136">セキュリティで保護されたスコアは、どの程度違反が発生する可能性があるかを絶対的に測定するものではありません。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-136">Secure Score does not express an absolute measure of how likely you are to get breached.</span></span> <span data-ttu-id="2d7d0-137">これは、侵害される危険性を相殺できる機能を採用した範囲を表します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-137">It expresses the extent to which you have adopted features that can offset the risk of being breached.</span></span> <span data-ttu-id="2d7d0-138">サービスは違反しないことを保証できず、セキュリティで保護されたスコアは何らかの保証として解釈されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-138">No service can guarantee that you will not be breached, and the Secure Score should not be interpreted as a guarantee in any way.</span></span>
 
## <a name="how-secure-score-helps"></a><span data-ttu-id="2d7d0-139">セキュリティで保護されたスコアの活用</span><span class="sxs-lookup"><span data-stu-id="2d7d0-139">How Secure Score helps</span></span>

<span data-ttu-id="2d7d0-140">セキュリティで保護されたスコアを使用すると、Office 365 の組み込みのセキュリティ機能を使用することによって、組織のセキュリティ状況を向上させることができます (既に購入しているが、認識されない場合があります)。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-140">With Secure Score, you can help improve your organization's security posture by using the built-in security features in Office 365 (many of which you already purchased but might not be aware of).</span></span> <span data-ttu-id="2d7d0-141">これらの機能の詳細を理解することで、組織を脅威から保護するための適切な手順を実行していることを安心していただくことができます。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-141">Learning more about these features can help give you peace of mind that you're taking the right steps to protect your organization from threats.</span></span>
  
<span data-ttu-id="2d7d0-142">しかし、そのような単語を取得するだけではありません。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-142">But don't just take our word for it.</span></span> <span data-ttu-id="2d7d0-143">セキュリティで保護されたスコアを使用しているお客様は、そのスコアを使用していないお客様よりも5倍増加しています。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-143">Customers who are using Secure Score have seen their score increase five times more than customers who aren't using it.</span></span> <span data-ttu-id="2d7d0-144">(スコアが増加するのは、組織で使用されているセキュリティ機能に対応します)。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-144">(The increase in their score corresponds with the security features being used in their organizations.)</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d7d0-145">セキュリティで保護されたスコアは、どの程度違反が発生する可能性があるかを絶対的に測定するものではありません。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-145">Secure Score does not express an absolute measure of how likely you are to get breached.</span></span> <span data-ttu-id="2d7d0-146">これは、侵害される可能性があるリスクを相殺できる制御を採用した範囲を表します。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-146">It expresses the extent to which you have adopted controls which can offset the risk of being breached.</span></span> <span data-ttu-id="2d7d0-147">サービスは違反しないことを保証できず、セキュリティで保護されたスコアは何らかの保証として解釈されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-147">No service can guarantee that you will not be breached, and Secure Score should not be interpreted as a guarantee in any way.</span></span> 
  
## <a name="required-permissions"></a><span data-ttu-id="2d7d0-148">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="2d7d0-148">Required permissions</span></span>

<span data-ttu-id="2d7d0-149">セキュリティで保護されたスコアダッシュボードを表示して使用するには、 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)に次のいずれかのロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-149">In order to view and use your Secure Score dashboard, you must be assigned one of the following roles in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles):</span></span>
- <span data-ttu-id="2d7d0-150">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="2d7d0-150">Global Administrator</span></span>
- <span data-ttu-id="2d7d0-151">課金管理者</span><span class="sxs-lookup"><span data-stu-id="2d7d0-151">Billing Administrator</span></span>
- <span data-ttu-id="2d7d0-152">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="2d7d0-152">User Administrator</span></span>
- <span data-ttu-id="2d7d0-153">パスワード管理者</span><span class="sxs-lookup"><span data-stu-id="2d7d0-153">Password Administrator</span></span>
- <span data-ttu-id="2d7d0-154">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="2d7d0-154">Security Administrator</span></span>
- <span data-ttu-id="2d7d0-155">セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="2d7d0-155">Security Reader</span></span>
- <span data-ttu-id="2d7d0-156">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="2d7d0-156">Exchange Administrator</span></span>
- <span data-ttu-id="2d7d0-157">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="2d7d0-157">SharePoint Administrator</span></span>

 <span data-ttu-id="2d7d0-158">管理者の役割を割り当てられていないユーザーは、セキュリティで保護されたスコアにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="2d7d0-158">Users who aren't assigned an admin role won't be able to access Secure Score.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2d7d0-159">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2d7d0-159">Related topics</span></span>

[<span data-ttu-id="2d7d0-160">セキュリティ ダッシュボードの概要</span><span class="sxs-lookup"><span data-stu-id="2d7d0-160">Security dashboard overview</span></span>](security-dashboard.md)

[<span data-ttu-id="2d7d0-161">取得しているサブスクリプションが不明な場合</span><span class="sxs-lookup"><span data-stu-id="2d7d0-161">What subscription do I have?</span></span>](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)
