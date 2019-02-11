---
title: Office 365 セキュリティ スコア
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/25/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: どのようにセキュリティで保護された組織実際には、Office 365 を知りたいですか。セキュリティで保護されたスコアがお手伝いします。セキュリティで保護されたスコアは、通常の活動と、Office 365 のセキュリティ設定に基づいて、組織のセキュリティを分析し、スコアが割り当てられます。
ms.openlocfilehash: bc0379e40b09e63e5fded1b1a289d40c306def91
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29559090"
---
# <a name="office-365-secure-score"></a><span data-ttu-id="5fb26-105">Office 365 セキュリティ スコア</span><span class="sxs-lookup"><span data-stu-id="5fb26-105">Office 365 Secure Score</span></span>

<span data-ttu-id="5fb26-p102">**概要**どのようにセキュリティで保護された組織実際には、Office 365 を知りたいですか。セキュリティで保護されたスコアがお手伝いします。セキュリティで保護されたスコアは、通常の活動と、Office 365 のセキュリティ設定に基づいて、組織のセキュリティを分析し、スコアが割り当てられます。スコアをセキュリティで保護し、それを使用する方法の概要を取得するには、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fb26-p102">**Summary** Ever wonder how secure your organization really is in Office 365? Secure Score is here to help. Secure Score analyzes your organization's security  based on your regular activities and security settings in Office 365, and assigns a score. Read this article to get an overview of Secure Score and how you can use it.</span></span>
  
## <a name="how-to-get-to-secure-score"></a><span data-ttu-id="5fb26-110">セキュリティで保護されたスコアを取得する方法</span><span class="sxs-lookup"><span data-stu-id="5fb26-110">How to get to Secure Score</span></span>

<span data-ttu-id="5fb26-111">訪問によって、組織のセキュリティで保護されたスコアを表示するには場合は、組織が[Office 365 の企業](https://docs.microsoft.com/office365/enterprise/)、[マイクロソフトの 365 のビジネス](https://docs.microsoft.com/microsoft-365/business/)、または Office 365 のビジネス プレミアムを含むサブスクリプションを保持し、[必要なアクセス許可](#required-permissions)がある場合、[https://securescore.office.com](https://securescore.office.com).</span><span class="sxs-lookup"><span data-stu-id="5fb26-111">If your organization has a subscription that includes [Office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/), or Office 365 Business Premium, and you have the [necessary permissions](#required-permissions), you can view your organization's secure score by visiting [https://securescore.office.com](https://securescore.office.com).</span></span> 

<span data-ttu-id="5fb26-112">または、セキュリティ & コンプライアンス センターにアクセスすることができます ([https://protection.office.com](https://protection.office.com))、現在のスコアを提供するセキュリティで保護されたスコアのウィジェットを見つけるでしょう。</span><span class="sxs-lookup"><span data-stu-id="5fb26-112">Alternatively, you can visit the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), where you'll find a Secure Score widget that provides you with your current score.</span></span>

![スコアのウィジェットをセキュリティで保護します。](media/SecureScoreWidget-o365.png)

<span data-ttu-id="5fb26-114">ウィジェットには、セキュリティで保護されたスコア、ダッシュ ボードへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5fb26-114">The widget includes a link to your Secure Score dashboard.</span></span>

![セキュリティで保護されたスコアのダッシュ ボード](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a><span data-ttu-id="5fb26-116">しくみ</span><span class="sxs-lookup"><span data-stu-id="5fb26-116">How it works</span></span>

<span data-ttu-id="5fb26-p103">セキュリティで保護されたスコアは、(OneDrive、SharePoint では、Exchange など) し、使用しているどのような Office 365 サービスの比較、設定と Microsoft によって確立された基準計画を保存する活動を決定します。方法に基づくスコアが表示されます組織はセキュリティのベスト プラクティスでは正しく調整されています。組織のスコアを向上させるための対策の推奨事項が得られます。</span><span class="sxs-lookup"><span data-stu-id="5fb26-p103">Secure Score determines what Office 365 services you're using (such as OneDrive, SharePoint, and Exchange) then compares your settings and activities to a baseline established by Microsoft. You'll get a score based on how well aligned your organization is with security best practices. You'll also get recommendations on steps you can take to improve your organization's score.</span></span> 
  
![スコアをセキュリティで保護された Office 365 ツール内のアクションのキュー](media/SecureScore-ActionsToTake.png)
  
<span data-ttu-id="5fb26-p104">セキュリティで保護されたスコアは、購入したサービスに基づいて、得点を計算します。たとえば、購入した場合のみ、Exchange のオンラインの計画は、オンラインの SharePoint のセキュリティ機能のするスコアはありません。スコアの分母は、購入した製品に適用されるコントロールのすべてのベースラインの合計です。分子は、すべてのコントロールを完了すると、または部分的に完了したら、そのコントロールを実行するために操作の合計です。</span><span class="sxs-lookup"><span data-stu-id="5fb26-p104">Secure Score calculates your score based on the services you purchased. For example, if you only purchased an Exchange Online plan, you won't be scored for SharePoint Online security features. The denominator of the score is the sum of all the baselines for the controls that apply to the products you purchased. The numerator is the sum of all the controls for which you completed, or partially completed, the actions to fulfill that control.</span></span>

<span data-ttu-id="5fb26-125">についてはどのような手順を実行する手伝いをして脅威を保護してから、アクションを展開し、ポイントの数、スコアも上がるので、推奨する対応策を実行するとします。</span><span class="sxs-lookup"><span data-stu-id="5fb26-125">Expand an action to learn about what steps to take, the threats it'll help protect you from, and how many points your score will increase once you follow the recommendation.</span></span>
  
![スコアをセキュリティで保護された Office 365 ツールで展開されているアクション](media/SecureScore-DetailedActionToTake.png)
  
<span data-ttu-id="5fb26-127">操作の影響を表示するには、組織のセキュリティ上、**スコア分析**] タブを選択して、履歴を確認します。</span><span class="sxs-lookup"><span data-stu-id="5fb26-127">To see the impact of your actions on your organization's security, select the **Score Analyzer** tab and review your history.</span></span> 
  
![スコアのスコアをセキュリティで保護された Office 365 ツールの [アナライザー] タブ](media/SecureScore-ScoreAnalyzer-7days.png)
  
<span data-ttu-id="5fb26-129">、グラフの下のカテゴリでのスコアおよびアクションの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fb26-129">Below the chart, you'll see a list of scores and actions by category.</span></span> 
  
![[スコアの分析] タブの選択されているデータ ポイントを示すグラフします。](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
<span data-ttu-id="5fb26-131">組織で実行できるものは、 **[スコアではありません]** とラベル付けされているアクションが、スコアがないため、セキュリティで保護されたスコアに接続されていない、します。</span><span class="sxs-lookup"><span data-stu-id="5fb26-131">Actions that are labeled as **[Not Scored]** are ones you can perform for your organization, but because they are not connected to Secure Score, they are not scored.</span></span>  

<span data-ttu-id="5fb26-p105">**スコアの分析**] ページで、特定の日のデータ ポイントをクリックし、意味を調べるには、その日の完了済みと進行中の動作の変更を参照してくださいにスクロールします。1 日 (約 1時 00分 AM PST) 1 回、スコアが計算されます。測定の操作に変更を加えた場合、スコアは自動的に次の日を更新します。あなたのスコアに反映させる変更には、最大で 48 時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="5fb26-p105">On the **Score Analyzer** page, click a data point for a specific day, then scroll down to see the completed and incomplete actions for that day to find out what changed. The score is calculated once per day (around 1:00 AM PST). If you make a change to a measured action, the score will automatically update the next day. It takes up to 48 hours for a change to be reflected in your score.</span></span>

<span data-ttu-id="5fb26-p106">セキュリティで保護されたスコアは絶対的な測定値を表現していない可能性ユーザーが侵害される可能性を取得します。これは、侵害されるリスクを相殺することができる機能を採用したエクステントを表現します。サービスはありませんするは侵害しない、およびセキュリティで保護されたスコアを何らかの方法で保証されたものとして解釈されない必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fb26-p106">Secure Score does not express an absolute measure of how likely you are to get breached. It expresses the extent to which you have adopted features that can offset the risk of being breached. No service can guarantee that you will not be breached, and the Secure Score should not be interpreted as a guarantee in any way.</span></span>
 
## <a name="how-secure-score-helps"></a><span data-ttu-id="5fb26-139">セキュリティで保護されたスコアがどのように役立つか</span><span class="sxs-lookup"><span data-stu-id="5fb26-139">How Secure Score helps</span></span>

<span data-ttu-id="5fb26-p107">スコアがセキュリティで保護された、(うちの多くを既に購入したを認識できない場合があります)、Office 365 に組み込まれているセキュリティ機能を使用して、組織のセキュリティ体制を強化することができます。これらの機能に関する詳細情報は、脅威から組織を保護するために適切な方法を行っているという安心感を与えるに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5fb26-p107">With Secure Score, you can help improve your organization's security posture by using the built-in security features in Office 365 (many of which you already purchased but might not be aware of). Learning more about these features can help give you peace of mind that you're taking the right steps to protect your organization from threats.</span></span>
  
<span data-ttu-id="5fb26-p108">持てないだけので、それにします。セキュリティで保護されたスコアを使用しているユーザーは、そのスコアを 5 つの時間よりもそれを使用していないお客様の増加を見てきました。(そのスコアの増加は、組織で使用されているセキュリティ機能と対応しています。)</span><span class="sxs-lookup"><span data-stu-id="5fb26-p108">But don't just take our word for it. Customers who are using Secure Score have seen their score increase five times more than customers who aren't using it. (The increase in their score corresponds with the security features being used in their organizations.)</span></span>
  
> [!NOTE]
> <span data-ttu-id="5fb26-p109">セキュリティで保護されたスコアは絶対的な測定値を表現していない可能性ユーザーが侵害される可能性を取得します。これは、侵害されるリスクを相殺することがあるコントロールを採用したエクステントを表現します。サービスはありませんは侵害しない、そのスコアをセキュリティで保護された何らかの方法で保証されたものとして解釈する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fb26-p109">Secure Score does not express an absolute measure of how likely you are to get breached. It expresses the extent to which you have adopted controls which can offset the risk of being breached. No service can guarantee that you will not be breached, and Secure Score should not be interpreted as a guarantee in any way.</span></span> 
  
## <a name="required-permissions"></a><span data-ttu-id="5fb26-148">必要な権限:</span><span class="sxs-lookup"><span data-stu-id="5fb26-148">Required permissions</span></span>

<span data-ttu-id="5fb26-149">表示し、スコアをセキュリティで保護されたダッシュ ボードを使用して、割り当てる必要があります Azure Active Directory 内の次のロールのいずれか。</span><span class="sxs-lookup"><span data-stu-id="5fb26-149">In order to view and use your Secure Score dashboard, you must be assigned one of the following roles in Azure Active Directory:</span></span>
- <span data-ttu-id="5fb26-150">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="5fb26-150">Global Administrator</span></span>
- <span data-ttu-id="5fb26-151">支払い管理者</span><span class="sxs-lookup"><span data-stu-id="5fb26-151">Billing Administrator</span></span>
- <span data-ttu-id="5fb26-152">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="5fb26-152">User Administrator</span></span>
- <span data-ttu-id="5fb26-153">管理者のパスワード</span><span class="sxs-lookup"><span data-stu-id="5fb26-153">Password Administrator</span></span>
- <span data-ttu-id="5fb26-154">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="5fb26-154">Security Administrator</span></span>
- <span data-ttu-id="5fb26-155">セキュリティ リーダー</span><span class="sxs-lookup"><span data-stu-id="5fb26-155">Security Reader</span></span>
- <span data-ttu-id="5fb26-156">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="5fb26-156">Exchange Administrator</span></span>
- <span data-ttu-id="5fb26-157">SharePoint の管理者</span><span class="sxs-lookup"><span data-stu-id="5fb26-157">SharePoint Administrator</span></span>

 <span data-ttu-id="5fb26-158">管理者の役割が割り当てられていないユーザーをセキュリティで保護されたスコアにアクセスすることができません。</span><span class="sxs-lookup"><span data-stu-id="5fb26-158">Users who aren't assigned an admin role won't be able to access Secure Score.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5fb26-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fb26-159">Related topics</span></span>

[<span data-ttu-id="5fb26-160">ダッシュ ボードのセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="5fb26-160">Security dashboard overview</span></span>](security-dashboard.md)

[<span data-ttu-id="5fb26-161">取得しているサブスクリプションが不明な場合</span><span class="sxs-lookup"><span data-stu-id="5fb26-161">What subscription do I have?</span></span>](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)