---
title: 監督レポート
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2a762db5-e1c9-4c09-aa8e-bef49ce97209
description: 監督レポートを使用してメールを表示するには、コンプライアンスの確認し、どのユーザーが実行する必要がありますが必要があります。
ms.openlocfilehash: e18d083c0aad8be945c628516e593462da8e3898
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531747"
---
# <a name="supervision-reports"></a><span data-ttu-id="af9e9-103">監督レポート</span><span class="sxs-lookup"><span data-stu-id="af9e9-103">Supervision reports</span></span>

<span data-ttu-id="af9e9-p101">監督のポリシーを定義する、組織内の通信に準拠するためのレビューを必要があり、誰がそれらのレビューを実行します。監督レポートを使用して、ポリシーとレビュー担当者のレベルでのレビュー」アクティビティを参照してください。ポリシーごとに、レビュー」アクティビティの現在の状態で、ライブの統計情報を表示することも。[監督のポリシーに関する詳細を表示](configure-supervision-policies.md)します。</span><span class="sxs-lookup"><span data-stu-id="af9e9-p101">Supervision policies define which communications in your organization need review for compliance, and who will perform those reviews. Use the supervision reports to see the review activity at the policy and reviewer level. For each policy, you can also view live statistics on the current state of review activity. [Learn more about supervision policies ](configure-supervision-policies.md) .</span></span> 
  
> [!NOTE]
> <span data-ttu-id="af9e9-p102">監督ポリシーを使用して、組織に、Office 365 の E5 のサブスクリプションが必要です。しない計画して監視を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="af9e9-p102">Using supervision policies requires an Office 365 E5 subscription for your organization. If you don't have that plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="af9e9-110">監督レポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af9e9-110">You can use the supervision reports to:</span></span>
  
- <span data-ttu-id="af9e9-111">ポリシーが意図したとおりに動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="af9e9-111">Verify that your policies are working as you intended.</span></span> 
    
- <span data-ttu-id="af9e9-112">確認の e メールの数が識別されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="af9e9-112">Find out how many emails are being identified for review.</span></span>
    
- <span data-ttu-id="af9e9-p103">E メールの数は対応機能とレビューを渡すことを確認します。この情報は、ポリシーを微調整または校閲者の数を変更するかどうかを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="af9e9-p103">Find out how many emails aren't compliant and which ones are passing review. This information can help you decide whether to fine-tune your policies or change the number of reviewers.</span></span>
    
## <a name="view-the-supervision-report"></a><span data-ttu-id="af9e9-115">監督レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="af9e9-115">View the Supervision report</span></span>

1. <span data-ttu-id="af9e9-116">サインイン、[セキュリティ&amp;コンプライアンス センター](https://protection.office.com/)監督のレポートを表示するアクセス許可を持つ、Office 365 の組織の管理者アカウントの資格情報を使用して.</span><span class="sxs-lookup"><span data-stu-id="af9e9-116">Sign into the [Security &amp; Compliance Center](https://protection.office.com/) using the credentials for an admin account in your Office 365 organization that has permissions to view supervision reports..</span></span> 
    
2. <span data-ttu-id="af9e9-p104">**レポート**に\>**のダッシュ ボード**です。監督のレポートのウィジェットが表示され、他のレポートへのアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="af9e9-p104">Go to **Reports** \> **Dashboard**. You'll see a reporting widget for supervision and other reports you have access to.</span></span>
    
3. <span data-ttu-id="af9e9-119">**監督**ウィジェットを開くには、レポートの詳細ページをクリックします。</span><span class="sxs-lookup"><span data-stu-id="af9e9-119">Click the **Supervision** widget to open the detailed report page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="af9e9-p105">**レポート**] ページにアクセスできない場合は、監督機関による監査の役割グループのメンバーであることの手順に従って確認[監督は、組織で使用可能な](configure-supervision-policies.md#SRavailable)のです。このロール グループで作成し、監督を管理するに含まれているポリシーし、レポートを実行します。</span><span class="sxs-lookup"><span data-stu-id="af9e9-p105">If you aren't able to access the **Reports** page, check that you're a member of the Supervisory Review role group, as described in [Make supervision available in your organization](configure-supervision-policies.md#SRavailable). Being included in this role group lets you create and manage supervision polices and run the report.</span></span> 
  
## <a name="how-to-use-the-report"></a><span data-ttu-id="af9e9-122">レポートを使用する方法</span><span class="sxs-lookup"><span data-stu-id="af9e9-122">How to use the report</span></span>

<span data-ttu-id="af9e9-p106">Outlook と Outlook での校閲者の監視フォルダーに電子メールが配信される監視ポリシーでは、確認の電子メールを識別するときに web アプリケーションです。このレポートには、確認プロセスの各段階での各ポリシーの名前との通信の数が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="af9e9-p106">When a supervision policy identifies an email for review, the email is delivered to the reviewer's Supervision folder in Outlook and Outlook web app. This report lists each policy's name and the number of communications at each stage in the review process.</span></span>
  
<span data-ttu-id="af9e9-125">レポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="af9e9-125">Use the report to:</span></span>
  
- <span data-ttu-id="af9e9-126">すべてのデータを表示、または特定のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="af9e9-126">View data for all or specific policies.</span></span>
    
- <span data-ttu-id="af9e9-127">準拠、Questionable など) などのタグの種類、レビュー担当者、またはメッセージの種類によってグループ化されたデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="af9e9-127">View data grouped by tag type (such as Compliant, Questionable, etc.), reviewer, or message type.</span></span>
    
- <span data-ttu-id="af9e9-128">データを CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="af9e9-128">Export data to a CSV file.</span></span>
    
- <span data-ttu-id="af9e9-129">に基づいてデータをフィルター処理では、アクティビティの日付、タグの種類、レビュー担当者、メッセージの種類を確認します。</span><span class="sxs-lookup"><span data-stu-id="af9e9-129">Filter data based on review activity date, tag type, reviewer, message type.</span></span>
    
<span data-ttu-id="af9e9-130">**タグの種類**] 列に表示される値の内訳を次に示します。</span><span class="sxs-lookup"><span data-stu-id="af9e9-130">Here's a breakdown of the values you might see in the **Tag type** column.</span></span> 
  
|<span data-ttu-id="af9e9-131">**タグの種類**</span><span class="sxs-lookup"><span data-stu-id="af9e9-131">**Tag type**</span></span>|<span data-ttu-id="af9e9-132">**意味**</span><span class="sxs-lookup"><span data-stu-id="af9e9-132">**What it means**</span></span>|
|:-----|:-----|
|<span data-ttu-id="af9e9-133">確認していません</span><span class="sxs-lookup"><span data-stu-id="af9e9-133">Not Reviewed</span></span>  <br/> |<span data-ttu-id="af9e9-p107">まだ確認されていない電子メールの数。これらの電子メールは、Outlook での校閲者の監視フォルダー内の確認を待機しています。</span><span class="sxs-lookup"><span data-stu-id="af9e9-p107">The number of emails that have not been reviewed yet. These emails are awaiting review in the reviewer's supervision folder in Outlook.</span></span>  <br/> |
|<span data-ttu-id="af9e9-136">準拠</span><span class="sxs-lookup"><span data-stu-id="af9e9-136">Compliant</span></span>  <br/> |<span data-ttu-id="af9e9-p108">電子メールの数は、確認し、準拠としてマークします。それ以上の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="af9e9-p108">The number of emails reviewed and marked as compliant. No further action is needed.</span></span>  <br/> |
|<span data-ttu-id="af9e9-139">問題があります。</span><span class="sxs-lookup"><span data-stu-id="af9e9-139">Questionable</span></span>  <br/> |<span data-ttu-id="af9e9-p109">電子メールの数は、確認し、疑わしいとマークします。フラグとして機能し他のレビュー担当者に役立つことができます電子メールがコンプライアンスのための調査を必要があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="af9e9-p109">The number of emails reviewed and marked questionable. This acts as a flag; other reviewers can help check whether an email needs investigation for compliance.</span></span>  <br/> |
|<span data-ttu-id="af9e9-142">非準拠 (アクティブ)</span><span class="sxs-lookup"><span data-stu-id="af9e9-142">Non-Compliant (Active)</span></span>  <br/> |<span data-ttu-id="af9e9-143">校閲者について現在調査中は、非準拠の電子メールの数。</span><span class="sxs-lookup"><span data-stu-id="af9e9-143">The number of non-compliant emails that reviewers are currently investigating.</span></span>  <br/> |
|<span data-ttu-id="af9e9-144">非準拠 (解決)</span><span class="sxs-lookup"><span data-stu-id="af9e9-144">Non-Compliant (Resolved)</span></span>  <br/> |<span data-ttu-id="af9e9-145">校閲者を調査し、解決する非準拠の電子メールの数。</span><span class="sxs-lookup"><span data-stu-id="af9e9-145">The number of non-compliant emails that reviewers investigated and resolved.</span></span>  <br/> |
   
## <a name="more-details"></a><span data-ttu-id="af9e9-146">詳細について</span><span class="sxs-lookup"><span data-stu-id="af9e9-146">More details</span></span>

- <span data-ttu-id="af9e9-147">このレポートに表示される前に、監督のポリシーを準備する必要があります最初。</span><span class="sxs-lookup"><span data-stu-id="af9e9-147">Supervision policies must first be provisioned before they will appear in this report.</span></span>
    
- <span data-ttu-id="af9e9-p110">ポリシーが削除されると、履歴データはそのまま表示します。ただし、「が存在しないのポリシー」として示されていると、**エクスポート**関数は使用できません。</span><span class="sxs-lookup"><span data-stu-id="af9e9-p110">If policies are deleted, historical data is still shown. However, they're indicated as a "Non-existent policy", and the **Export** function isn't available.</span></span> 
    
- <span data-ttu-id="af9e9-p111">レポートは、既定ですべてのデータを表示されていない場合、は、現在の日付範囲を表示する任意のデータがない可能性があります。これらの場合、日付の範囲を変更するのには、**フィルター**コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="af9e9-p111">If the report doesn't show any data by default, it might be because the current date range doesn't have any data to show. In these cases, use the **Filters** control to change the date range.</span></span> 
    

