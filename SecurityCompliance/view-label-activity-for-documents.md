---
title: ドキュメントのラベル アクティビティを表示する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 5/9/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Office 365 セキュリティ&amp;コンプライアンス センターのラベル アクティビティ エクスプローラーを使用すると、過去 30 日間の SharePoint および OneDrive for Business のすべてコンテンツのラベル アクティビティをすばやく検索して表示することができます。リアルタイム データが表示され、テナントで生じている事柄を明確に把握できます。
ms.openlocfilehash: 55888ff2ef8118389a88955a8f4e047170606524
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32267341"
---
# <a name="view-label-activity-for-documents"></a><span data-ttu-id="92e86-104">ドキュメントのラベル アクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="92e86-104">View label activity for documents</span></span>

<span data-ttu-id="92e86-p102">ラベルを作成した後、意図したとおりにラベルがコンテンツに適用されているかどうかを確認することをお勧めします。Office 365 セキュリティ&amp;コンプライアンス センターのラベル アクティビティ エクスプローラーを使用すると、過去 30 日間の SharePoint および OneDrive for Business のすべてコンテンツのラベル アクティビティをすばやく検索して表示することができます。リアルタイム データが表示され、テナントで生じている事柄を明確に把握できます。</span><span class="sxs-lookup"><span data-stu-id="92e86-p102">After you create your labels, you'll want to verify that they're being applied to content as you intended. With the Label Activity Explorer in the Office 365 Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days. This is real-time data that gives you a clear view into what's happening in your tenant.</span></span>
  
<span data-ttu-id="92e86-108">たとえば、ラベル アクティビティ エクスプローラーで以下のことができます:</span><span class="sxs-lookup"><span data-stu-id="92e86-108">For example, with the Label Activity Explorer, you can:</span></span>
  
- <span data-ttu-id="92e86-109">それぞれのラベルが適用された回数を日ごとに表示 (最大 30 日間)。</span><span class="sxs-lookup"><span data-stu-id="92e86-109">View how many times each label was applied on each day (up to 30 days).</span></span>
    
- <span data-ttu-id="92e86-110">誰がいつ、どのファイルにラベルを付けたかを正確に表示。ファイルが存在するサイトへのリンクも表示。</span><span class="sxs-lookup"><span data-stu-id="92e86-110">See who labeled exactly which file on which date, along with a link to the site where that file resides.</span></span>
    
- <span data-ttu-id="92e86-111">ラベルが変更されたり削除されたりしたファイル、古いラベルおよび新しいラベル、変更を行ったユーザーの表示。</span><span class="sxs-lookup"><span data-stu-id="92e86-111">View which files had labels changed or removed, what the old and new labels are, and who made the change.</span></span>
    
- <span data-ttu-id="92e86-p103">データをフィルター処理して、特定のレベル、ファイル、ユーザーのラベル アクティビティすべてを表示。場所 (SharePoint または OneDrive for Business) や、ラベルが適用された方法 (手動か自動) でラベル アクティビティをフィルター処理することも可能。</span><span class="sxs-lookup"><span data-stu-id="92e86-p103">Filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
    
- <span data-ttu-id="92e86-p104">各ドキュメントだけでなくフォルダーのラベル アクティビティも表示。今後は、ラベルが付けられたフォルダーの中のファイル数が表示される予定。</span><span class="sxs-lookup"><span data-stu-id="92e86-p104">View label activity for folders as well as individual documents. Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span></span>
    
<span data-ttu-id="92e86-116">ラベル アクティビティ エクスプローラーにアクセスするには、セキュリティ&amp;コンプライアンス センター>**[データ ガバナンス]** > **[ラベル アクティビティ エクスプローラー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="92e86-116">You can find the Label Activity Explorer in the Security &amp; Compliance Center > **Data governance** > **Label Activity Explorer**.</span></span>
  
<span data-ttu-id="92e86-117">なお、ラベル アクティビティ エクスプローラーには、Office 365 Enterprise E5 サブスクリプションが必要となります。</span><span class="sxs-lookup"><span data-stu-id="92e86-117">Note that the Label Activity Explorer requires an Office 365 Enterprise E5 subscription.</span></span>
  
![ラベル アクティビティ エクスプローラー](media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a><span data-ttu-id="92e86-119">ファイルまたはフォルダーのラベル アクティビティの表示</span><span class="sxs-lookup"><span data-stu-id="92e86-119">View label activities for files or folders</span></span>

<span data-ttu-id="92e86-p105">ラベル アクティビティ エクスプローラーの上部で、ファイルまたはフォルダーのアクティビティを表示するかどうかを選択できます。フォルダーのアクティビティではフォルダーのみが表示されます。フォルダー内のファイルは表示されません。</span><span class="sxs-lookup"><span data-stu-id="92e86-p105">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders. Note that folder activity includes only the folder itself, not the files inside the folder.</span></span>
  
<span data-ttu-id="92e86-p106">フォルダーにラベルを付けると、そのフォルダー内のすべてのファイルもそのラベルを取得するため (明示的に適用されているラベルがあるファイルを除く)、フォルダーのラベル アクティビティを表示したい場合があります。したがって、フォルダーにラベルを付けると、多数のファイルに影響を及ぼす可能性があります。詳細については、「[SharePoint ライブラリ、フォルダー、またはドキュメント セット内のすべてのコンテンツへの既定の保持ラベルの適用](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92e86-p106">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them). Therefore, labeling folders might affect a significant number of files. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
  
![ファイルとフォルダーのラベル アクティビティを表示するドロップダウン メニュー](media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a><span data-ttu-id="92e86-126">ラベル アクティビティ</span><span class="sxs-lookup"><span data-stu-id="92e86-126">Label activities</span></span>

 <span data-ttu-id="92e86-p107">ラベルの**追加**、**削除**、**変更**の、ラベルに関するすべての操作が**ラベル アクティビティ**に該当します。このビューを使用して、それぞれのラベルがどのぐらいの数のファイルに適用されたかの包括的な確認を日別で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="92e86-p107">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label. You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span></span> 
  
### <a name="label-changes"></a><span data-ttu-id="92e86-129">ラベルの変更</span><span class="sxs-lookup"><span data-stu-id="92e86-129">Label changes</span></span>

 <span data-ttu-id="92e86-p108">**ラベルの変更**には、ラベルの**削除**または**変更**によって危険が生じる可能性のある操作の情報が含まれています。このビューを使用すれば、そのような危険な操作と実行したユーザーをすぐに確認できます。グラフの下にあるアクティビティ リストでファイルを選択し、右側の詳細ウィンドウにあるそのファイルのリンクをクリックすると、詳細情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="92e86-p108">**Label changes** includes the potentially risky actions of **removing** or **changing** a label. You can use this view to quickly see such risky actions and the user who performed them. In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span></span> 
  
![ラベル アクティビティの詳細ウィンドウ](media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a><span data-ttu-id="92e86-134">ラベル アクティビティのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="92e86-134">Filter label activity</span></span>

<span data-ttu-id="92e86-p109">データをすばやくフィルター処理して、特定のレベル、ファイル、ユーザーのラベル アクティビティすべてを表示できます。場所 (SharePoint または OneDrive for Business) や、ラベルが適用された方法 (手動か自動) でラベル アクティビティをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="92e86-p109">You can quickly filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
  
![ラベル アクティビティのフィルター](media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  

