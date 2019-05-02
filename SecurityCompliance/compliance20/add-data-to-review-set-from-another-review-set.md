---
title: 1つのレビューセットから別のレビューセットにデータを追加する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 025fd90373313f762ce1d1dab8d48286e32e3cbb
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2019
ms.locfileid: "33527225"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="140c3-102">別のレビューセットからのレビューセットへのデータの追加</span><span class="sxs-lookup"><span data-stu-id="140c3-102">Add data to a review set from another review set</span></span>

<span data-ttu-id="140c3-103">場合によっては、ドキュメントの一部を1つのレビューセットから分割して、別のレビューセットで個別に操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="140c3-103">In some cases, it may be necessary to carve out a portion of documents from one review set and work with them individually in another review set.</span></span>  <span data-ttu-id="140c3-104">これは、校閲セットのコンテンツをカリングし、データのサブセットに対して分析を実行する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="140c3-104">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="140c3-105">次のワークフローを使用して、1つのレビューセットから別のレビューセットにコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="140c3-105">Use the following workflow to add content from one review set to another.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="140c3-106">始める前に</span><span class="sxs-lookup"><span data-stu-id="140c3-106">Before you begin</span></span>

<span data-ttu-id="140c3-107">開始する前に、データを追加するための新しいレビューセットを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="140c3-107">Before you start, you'll need to create a new review set to add the data to.</span></span>  <span data-ttu-id="140c3-108">ケースの [**レビューセット**] タブに新しいレビューセットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="140c3-108">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="140c3-109">詳細については、「 [review sets を管理](managing-review-sets.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="140c3-109">For more information, see [Manage review sets](managing-review-sets.md).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="140c3-110">手順 1: 別のレビューセットに追加するコンテンツを識別する</span><span class="sxs-lookup"><span data-stu-id="140c3-110">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="140c3-111">ドキュメントグリッド内の電子メールとドキュメント、または検索結果のすべてのアイテムを選択することで、コンテンツをレビューセットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="140c3-111">You can add content to a review set by selecting emails and documents in the document grid or all items in a search result.</span></span>  <span data-ttu-id="140c3-112">選択したアイテムを追加する場合は、アイテムを選択し、[**アクション**] をクリックしてから、[**別のレビューセットに追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="140c3-112">If choosing to add selected items, select the items, click **Action**, and then click **Add to another review set**.</span></span>

![別の校閲セットに追加する](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="140c3-114">手順 2: 別のレビューセットに追加するためのオプションを指定する</span><span class="sxs-lookup"><span data-stu-id="140c3-114">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="140c3-115">[**別のレビューセットに追加**] ページで、アイテムを追加するレビューセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="140c3-115">In the **Add to another review set** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="140c3-116">**すべての検索結果**または**選択したアイテム**を追加するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="140c3-116">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="140c3-117">その他の情報には、アイテムのすべてのメタデータを含めるためのオプションと、ドキュメントタグを新しいレビューセットに含める必要があるかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="140c3-117">Additional information provides options to include all metadata from the items and finally whether or not the document tags should be included in the new review set.</span></span>  <span data-ttu-id="140c3-118">**[Ok]** をクリックすると、コンテンツをレビューセットに追加するための新しいジョブが作成されます。そのジョブの進行状況を監視するには、[**ジョブ**] タブを使用します。詳細については、「 [Manage jobs](managing-jobs-ediscovery20.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="140c3-118">After clicking **Ok** a new job will be created to add the content to a review set; you can monitor the progress of that job on the **Job** tab. For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>

![別の校閲セットに追加する](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)
