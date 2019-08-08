---
title: 既定の DLP ポリシーの使用を開始する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
description: 最初のデータ損失防止 (DLP) ポリシーを作成する前に、DLP は既定のポリシーを使用して機密情報を保護するのに役立ちます。 この既定のポリシーとその推奨事項 (以下を参照) は、クレジットカード番号を含む電子メールやドキュメントが組織外のユーザーと共有されたことを通知することにより、機密コンテンツの安全性を確保するのに役立ちます。
ms.openlocfilehash: 32e5fef1cbfb8fe13928100dbfdae0d620e79762
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230501"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="3b2c1-104">既定の DLP ポリシーの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="3b2c1-104">Get started with the default DLP policy</span></span>

<span data-ttu-id="3b2c1-105">最初のデータ損失防止 (DLP) ポリシーを作成する前に、DLP は既定のポリシーを使用して機密情報を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-105">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="3b2c1-106">この既定のポリシーとその推奨事項 (以下を参照) は、クレジットカード番号を含む電子メールやドキュメントが組織外のユーザーと共有されたことを通知することにより、機密コンテンツの安全性を確保するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-106">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="3b2c1-107">この推奨事項は、セキュリティ&amp;コンプライアンスセンターの**ホーム**ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-107">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="3b2c1-108">このウィジェットを使用すると、共有された機密性の高い情報をすばやく表示し、1回または2つの方法で既定の DLP ポリシーを調整することができます。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-108">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="3b2c1-109">完全にカスタマイズできるので、いつでも既定の DLP ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-109">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="3b2c1-110">最初に推奨事項が表示されない場合は、[**推奨する**方法] セクションの下部にある [ **+ More** ] をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-110">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![共有コンテンツの保護という名前のウィジェット](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="3b2c1-112">レポートを表示し、既定の DLP ポリシーを調整する</span><span class="sxs-lookup"><span data-stu-id="3b2c1-112">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="3b2c1-113">ユーザーが組織外のユーザーと機密情報を共有していることがウィジェットに表示されたら、下部にある [ **DLP ポリシーの調整**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-113">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="3b2c1-114">詳細レポートでは、過去30日間にクレジットカード番号が共有されたコンテンツの日時と量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-114">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="3b2c1-115">ルールの一致がウィジェットに表示されるまでに最大48時間かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-115">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="3b2c1-116">機密情報を保護するために、既定の DLP ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-116">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="3b2c1-117">少なくとも1つのクレジットカード番号が含まれている Exchange、SharePoint、OneDrive のコンテンツが組織外のユーザーと共有されていることを検出します。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-117">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="3b2c1-118">ポリシーヒントを表示し、その機密情報を組織外のユーザーと共有しようとしたときに、ユーザーに電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-118">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="3b2c1-119">これらのオプションの詳細については、「[電子メール通知を送信する」と「DLP ポリシーのポリシーヒントを表示する](use-notifications-and-policy-tips.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-119">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="3b2c1-120">詳細なアクティビティレポートを生成して、組織外のユーザーとコンテンツを共有しているユーザーや、自分が行ったことなどを追跡できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-120">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="3b2c1-121">[DLP レポート](view-the-dlp-reports.md)および[監査ログデータ](search-the-audit-log-in-security-and-compliance.md)(**アクティビティ** = **DLP**) を使用して、この情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-121">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="3b2c1-122">既定の DLP ポリシーをすばやく変更するには、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-122">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="3b2c1-123">この機密情報をユーザーが組織外のユーザーと共有する場合は、インシデントレポート電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-123">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="3b2c1-124">他のユーザーを電子メールインシデントレポートに追加します。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-124">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="3b2c1-125">機密情報を含むコンテンツへのアクセスをブロックします。ただし、必要に応じて、ユーザーによる上書きと共有または送信を許可します。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-125">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="3b2c1-126">インシデントレポートの詳細については、「[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-126">For more information on incident reports or restricting access, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="3b2c1-127">これらのオプションを後で変更する場合は、既定の DLP ポリシーをいつでも編集できます。次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-127">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![その他の保護共有コンテンツという名前のウィジェットの設定](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="3b2c1-129">既定の DLP ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="3b2c1-129">Edit the default DLP policy</span></span>

<span data-ttu-id="3b2c1-130">このポリシーは、 **Default Office 365 DLP ポリシー**という名前で、セキュリティ&amp;コンプライアンスセンターの [**ポリシー** ] ページの [**データ損失防止**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-130">This policy is named **Default Office 365 DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="3b2c1-131">このポリシーは完全にカスタマイズ可能ですが、最初から自分で作成した DLP ポリシーと同じです。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-131">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="3b2c1-132">また、ポリシーを無効にするか削除して、ユーザーがポリシーヒントや電子メール通知を受信しなくなるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-132">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![既定の Office 365 DLP ポリシーという名前の DLP ポリシー](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="3b2c1-134">ウィジェットが表示されない場合</span><span class="sxs-lookup"><span data-stu-id="3b2c1-134">When the widget does and does not appear</span></span>

<span data-ttu-id="3b2c1-135">その他の保護された**共有コンテンツ**という名前のウィジェットは\*\*\*\* 、セキュリティ&amp; /コンプライアンスセンターのホームページにある [**推奨事項**] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-135">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="3b2c1-136">このウィジェットは、次の場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-136">This widget appears only when:</span></span>
  
- <span data-ttu-id="3b2c1-137">セキュリティ&amp;コンプライアンスセンターまたは Exchange 管理センターにデータ損失防止ポリシーはありません。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-137">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="3b2c1-138">このウィジェットは DLP の使用を開始するためのものなので、既に DLP ポリシーがある場合には表示されません。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-138">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="3b2c1-139">過去30日間に、少なくとも1つのクレジットカードが含まれるコンテンツが組織外のユーザーと共有されています。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-139">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="3b2c1-140">ルールの一致がウィジェットで利用できるようになるまでに最大48時間かかる場合があるため、外部で共有される機密情報が検出された後は、推奨事項が表示されるまで最大で2日かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-140">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="3b2c1-141">最後に、ウィジェットを使用して既定の DLP ポリシーを調整すると、そのウィジェットは**ホーム**ページに表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="3b2c1-141">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

