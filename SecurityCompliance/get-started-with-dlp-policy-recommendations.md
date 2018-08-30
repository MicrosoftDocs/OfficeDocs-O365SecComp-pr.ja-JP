---
title: DLP の推奨ポリシーの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/7/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2ea4459b-cb13-4ce2-b9d1-0619316df88c
description: この見解を優先する推奨設定を使用すると保存されているし、通知することにより可能なギャップがない場合、Office 365 の共有は、機密性の高いコンテンツを安全に保つ、DLP ポリシーの適用範囲。セキュリティのホーム ページにこの推奨事項が表示されます&amp;コンプライアンス センター、ドキュメントのトップ 5 の最も一般的な種類の機密情報が含まれている DLP ポリシーで保護されていない場合。
ms.openlocfilehash: 842387397b9b95d236660c5809174c2b356cf14a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532694"
---
# <a name="get-started-with-dlp-policy-recommendations"></a><span data-ttu-id="70f8f-104">DLP の推奨ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="70f8f-104">Get started with DLP policy recommendations</span></span>

<span data-ttu-id="70f8f-p102">この見解を優先する推奨設定を使用すると保存されているし、通知することにより可能なギャップがない場合、Office 365 の共有は、機密性の高いコンテンツを安全に保つ、DLP ポリシーの適用範囲。セキュリティの [**ホーム**] ページでこの推奨事項が表示されます&amp;コンプライアンス センター、文書は、トップ 5 の最も一般的な種類の機密情報のいずれかが含まれているが、データ損失防止 (DLP) ポリシーで保護されていない場合。</span><span class="sxs-lookup"><span data-stu-id="70f8f-p102">This insight-driven recommendation helps your organization keep sensitive content secure when it's stored and shared in Office 365 by informing you when there's a possible gap in your DLP policy coverage. You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center, if your documents contain any of the top-five most common types of sensitive information but aren't protected by a data loss prevention (DLP) policy.</span></span> 
  
<span data-ttu-id="70f8f-p103">このウィジェットを使用するにはクリックするだけの 2 つのカスタマイズされた DLP ポリシーを簡単に作成して、この DLP ポリシーを作成した後は、完全にカスタマイズ可能です。最初は、推奨事項が表示されない場合は、**詳細と****推奨する**] セクションの下部にあるをクリックすると実行してくださいに注意してください。</span><span class="sxs-lookup"><span data-stu-id="70f8f-p103">You can use this widget to quickly create a customized DLP policy in just a click or two, and after you create this DLP policy, it's fully customizable. Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![という名前の機密情報が保護されていないウィジェット](media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a><span data-ttu-id="70f8f-110">推奨の DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="70f8f-110">Create the recommended DLP policy</span></span>

<span data-ttu-id="70f8f-111">ウィジェットでは、機密情報の保護を解除して表示されている場合は、DLP ポリシーを簡単に作成するのには一番下にある**開始**を選択します。</span><span class="sxs-lookup"><span data-stu-id="70f8f-111">When the widget shows you unprotected sensitive information, choose **Get started** at the bottom to quickly create a DLP policy.</span></span> 
  
<span data-ttu-id="70f8f-112">この DLP ポリシーの機密情報を保護するためには。</span><span class="sxs-lookup"><span data-stu-id="70f8f-112">To help protect the sensitive information, this DLP policy:</span></span>
  
- <span data-ttu-id="70f8f-113">Exchange、SharePoint、および機密情報の保護されていない種類のいずれかを含む OneDrive のコンテンツは、組織外のユーザーと共有されている場合を検出します。</span><span class="sxs-lookup"><span data-stu-id="70f8f-113">Detects when content in Exchange, SharePoint, and OneDrive that contains one of the unprotected types of sensitive information is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="70f8f-p104">組織外のユーザーとコンテンツを共有して、行ったことのようなものを追跡することができるように、詳細な利用状況レポートを生成します。DLP の[レポート](view-the-dlp-reports.md)と[監査ログのデータ](search-the-audit-log-in-security-and-compliance.md)を使用することができます (場所**活動** = **DLP**) にこの情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70f8f-p104">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it. You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="70f8f-116">DLP ポリシーを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="70f8f-116">You can also choose to have the DLP policy:</span></span>
  
- <span data-ttu-id="70f8f-117">電子メールで送信インシデント レポート、組織外のユーザーとユーザーが機密性の高い情報の多くを共有する場合。</span><span class="sxs-lookup"><span data-stu-id="70f8f-117">Send you an incident report email when users share a lot of this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="70f8f-118">電子メール インシデント レポートには、他のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="70f8f-118">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="70f8f-p105">ポリシー ヒントを表示して、この機密情報を組織外のユーザーと共有するとき、ユーザーに電子メール通知を送信します。これらのオプションの詳細については、[送信する電子メール通知と DLP ポリシーのポリシー ヒントの表示](use-notifications-and-policy-tips.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70f8f-p105">Show a policy tip and send an email notification to users when they attempt to share this sensitive information with people outside your organization. For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
<span data-ttu-id="70f8f-p106">後でこれらのオプションを変更する場合は、作成後、DLP ポリシーを編集できます。たとえば、行うことができます、ポリシーによる機密性の高い情報が含まれるコンテンツの共有もブロックの方がより制限の厳しい最初の段階で、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="70f8f-p106">If you want to change these options later, you can edit the DLP policy after it's created. For example, you can make the policy more restrictive by even blocking people from sharing content that contains sensitive information in the first place - see the next section.</span></span>
  
![ウィジェットの設定が保護されていない機密情報を名前付き](media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a><span data-ttu-id="70f8f-124">推奨の DLP ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="70f8f-124">Edit the recommended DLP policy</span></span>

<span data-ttu-id="70f8f-125">DLP ポリシーを作成するウィジェットを使用するポリシー下に表示されます**データ損失の防止**セキュリティ**ポリシー**のページに&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="70f8f-125">After you use the widget to create a DLP policy, the policy appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="70f8f-p107">既定では、ポリシーがという名前の**システムの機密情報の共有ポリシーをお勧め**します。このポリシーは、完全にカスタマイズ可能なすべての DLP ポリシーが自分を最初から作成することと同じです。たとえば、ウィジェットを使用する場合は、インシデント レポートと、ポリシーのヒントをオンにしないようにする場合、常にポリシーを編集していつでもこれらのオプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="70f8f-p107">By default, the policy is named **System Recommended Policy for Sharing Sensitive Information**. This policy is fully customizable, the same as any DLP policy that you create yourself from scratch. For example, if you decided not to turn on incident reports and policy tips when you used the widget, you can always edit the policy and turn on those options at any time.</span></span>
  
![システムの機密情報を共有するためのポリシーの推奨](media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="70f8f-130">ウィジェットは、表示されない.</span><span class="sxs-lookup"><span data-stu-id="70f8f-130">When the widget does and does not appear</span></span>

<span data-ttu-id="70f8f-131">Widget という名前の**機密情報が保護されていない**セクションに表示されます、**推奨する**セキュリティの [**ホーム**] ページの&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="70f8f-131">The widget named **Unprotected Sensitive Information** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="70f8f-132">このウィジェットでは、場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="70f8f-132">This widget appears only when:</span></span>
  
- <span data-ttu-id="70f8f-133">SharePoint または OneDrive では、過去 30 日間の 5 つの最も一般的な種類の機密情報を含む新規ドキュメントが検出されます。</span><span class="sxs-lookup"><span data-stu-id="70f8f-133">New documents containing any of the five most common types of sensitive information are detected in SharePoint or OneDrive over the past 30 days.</span></span>
    
- <span data-ttu-id="70f8f-134">機微な情報は、現在既存の DLP ポリシーによって保護されていません。</span><span class="sxs-lookup"><span data-stu-id="70f8f-134">That sensitive information is not already protected by an existing DLP policy.</span></span>
    
<span data-ttu-id="70f8f-135">データのスキャンは、常に DLP ポリシーとは異なりこの推奨事項をスキャンし、DLP ポリシーの適用範囲のギャップの約 48 時間ごとに新しいコンテンツをアップロードすると後が表示されることを推奨の最大 2 日間がかかる場合がありますので。</span><span class="sxs-lookup"><span data-stu-id="70f8f-135">Unlike DLP policies that are constantly scanning your data, this recommendation scans for gaps in your DLP policy coverage roughly every 48 hours, so after new content is uploaded, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="70f8f-136">最後に、ウィジェットを使用して推奨される DLP ポリシーを作成した後、ウィジェットは、**ホーム**ページから削除されます。</span><span class="sxs-lookup"><span data-stu-id="70f8f-136">Finally, after you use the widget to create a recommended DLP policy, the widget disappears from the **Home** page.</span></span> 
  

