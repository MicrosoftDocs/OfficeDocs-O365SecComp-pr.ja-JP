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
ms.openlocfilehash: 3a4d0d309daa5af9830f98215ca09321429785ee
ms.sourcegitcommit: 25595bc8fae96bc23b7b6d7102a22f37878987c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "33641657"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="3c679-102">別のレビューセットからのレビューセットへのデータの追加</span><span class="sxs-lookup"><span data-stu-id="3c679-102">Add data to a review set from another review set</span></span>

<span data-ttu-id="3c679-103">場合によっては、ドキュメントの一部を1つのレビューセットから分割して、別のレビューセットで個別に操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c679-103">In some cases, it may be necessary to carve out a portion of documents from one review set and work with them individually in another review set.</span></span>  <span data-ttu-id="3c679-104">これは、校閲セットのコンテンツをカリングし、データのサブセットに対して分析を実行する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="3c679-104">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="3c679-105">この記事のワークフローに従って、ある校閲セットから別のレビューセットにコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="3c679-105">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3c679-106">始める前に</span><span class="sxs-lookup"><span data-stu-id="3c679-106">Before you begin</span></span>

<span data-ttu-id="3c679-107">開始する前に、データを追加するための新しいレビューセットを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c679-107">Before you start, you'll need to create a new review set to add the data to.</span></span>  <span data-ttu-id="3c679-108">ケースの [**レビューセット**] タブに新しいレビューセットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="3c679-108">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="3c679-109">詳細については、「[レビューセットを作成する](managing-review-sets.md#create-a-review-set)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c679-109">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="3c679-110">手順 1: 別のレビューセットに追加するコンテンツを識別する</span><span class="sxs-lookup"><span data-stu-id="3c679-110">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="3c679-111">ソースレビューセット内の特定のドキュメントを選択するか、レビューセットクエリによって返されるすべてのアイテムを選択することによって、1つのレビューセットから別のレビューセットにコンテンツを追加できます。</span><span class="sxs-lookup"><span data-stu-id="3c679-111">You can add content from one review set to another one by selecting specific documents in the source review set or b seleting all items returned by review set query.</span></span>  <span data-ttu-id="3c679-112">選択したアイテムを追加する場合は、アイテムを選択し、[**アクション**] をクリックしてから、[**別のレビューセットに追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="3c679-112">If you're adding selected items, select the items, click **Action**, and then click **Add to another review set**.</span></span>

![別の校閲セットに追加する](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="3c679-114">手順 2: 別のレビューセットに追加するためのオプションを指定する</span><span class="sxs-lookup"><span data-stu-id="3c679-114">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="3c679-115">[**別のレビューセットオプションポップアップに追加**] ページで、アイテムを追加するレビューセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="3c679-115">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="3c679-116">**すべての検索結果**または**選択したアイテム**を追加するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3c679-116">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="3c679-117">その他の情報には、アイテムのすべてのメタデータを含めるためのオプションと、ドキュメントが新しいレビューセットに追加されたときにソースレビューセットから (**ラベル**チェックボックスをオンにして) タグを含めるかどうかを指定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3c679-117">Additional information provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** checkbox) from the source review set when the documents are added to the new review set.</span></span>  

![別の校閲セットに追加する](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="3c679-119">[ **Ok]** をクリックすると、別のレビューセットにコンテンツを追加するための新しいジョブ (**別のレビューセットへのデータの追加**) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3c679-119">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to a another review set.</span></span>  <span data-ttu-id="3c679-120">[**ジョブ**] タブに移動して、このジョブの進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="3c679-120">You can go to **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="3c679-121">詳細については、「 [Manage jobs](managing-jobs-ediscovery20.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c679-121">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
