---
title: 1つの作業セットから別の作業セットにデータを追加する
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
ms.openlocfilehash: e9e34d112cb84c27fec35e752eb2bfcbfe3136a3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243439"
---
# <a name="add-data-to-a-working-set-from-another-working-set"></a><span data-ttu-id="45b04-102">別のワーキングセットからワーキングセットにデータを追加する</span><span class="sxs-lookup"><span data-stu-id="45b04-102">Add data to a working set from another working set</span></span>
<span data-ttu-id="45b04-103">場合によっては、ドキュメントの一部を1つの作業セットから分割して、別の作業セットで個別に操作することが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="45b04-103">In some cases, it may be necessary to carve out a portion of documents from one working set and work with them individually in another working set.</span></span>  <span data-ttu-id="45b04-104">これは、作業セットのコンテンツをカリングし、データのサブセットに対して分析を実行する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="45b04-104">This is especially useful if you've culled content in a working set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="45b04-105">次のワークフローを使用して、あるワーキングセットから別の作業セットにコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="45b04-105">Use the following workflow to add content from one working set to another.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="45b04-106">始める前に</span><span class="sxs-lookup"><span data-stu-id="45b04-106">Before you start</span></span>
<span data-ttu-id="45b04-107">開始する前に、新しい作業セットを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45b04-107">Before you start, you'll need to create a new working set.</span></span>  <span data-ttu-id="45b04-108">[*作業設定*] タブを使用して新しい作業セットを追加できます。[詳細につい](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-working-sets)ては、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45b04-108">A new working set can be added through the *Working sets* tab [Learn more](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-working-sets).</span></span>

## <a name="step-1-identify-content-to-add-to-another-working-set"></a><span data-ttu-id="45b04-109">手順 1: 別の作業セットに追加するコンテンツを識別する</span><span class="sxs-lookup"><span data-stu-id="45b04-109">Step 1: Identify content to add to another working set</span></span>
<span data-ttu-id="45b04-110">ドキュメントグリッド内の電子メールとドキュメント、または検索結果のすべてのアイテムを選択することによって、作業セットにコンテンツを追加できます。</span><span class="sxs-lookup"><span data-stu-id="45b04-110">You can add content to a working set by selecting emails and documents in the document grid or all items in a search result.</span></span>  <span data-ttu-id="45b04-111">選択したアイテムを追加する場合は、アイテムを選択して [*アクション*] ドロップダウンをクリックし、*別のワーキングセットに追加*します。</span><span class="sxs-lookup"><span data-stu-id="45b04-111">If choosing to add selected items, select the items and click the *Action* drop down then *Add to another working set*.</span></span>

![別の作業セットに追加する](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-workings-set"></a><span data-ttu-id="45b04-113">手順 2: 別の動作セットに追加するためのオプションを指定する</span><span class="sxs-lookup"><span data-stu-id="45b04-113">Step 2: Specify options for adding to another workings set</span></span>
<span data-ttu-id="45b04-114">[*別の作業セットオプションに追加*] ポップアップで、アイテムを追加する作業セットを最初に選択します。</span><span class="sxs-lookup"><span data-stu-id="45b04-114">In the *Add to another working set options* flyout, first choose the working set you want to add the items to.</span></span>  <span data-ttu-id="45b04-115">すべての検索結果または選択したアイテムを追加するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="45b04-115">Choose whether to add All search results or Selected items.</span></span>  <span data-ttu-id="45b04-116">その他の情報には、アイテムのすべてのメタデータを含めるためのオプションと、ドキュメントタグを新しいワーキングセットに含める必要があるかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45b04-116">Additional information provides options to include all metadata from the items and finally whether or not the document tags should be included in the new working set.</span></span>  <span data-ttu-id="45b04-117">*[OK]* をクリックすると、作業セットにコンテンツを追加するための新しいジョブが作成され、[[ジョブ](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-jobs-ediscovery20)] タブでそのジョブ![の進行状況を監視できます。別のワーキングセットに追加する](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)</span><span class="sxs-lookup"><span data-stu-id="45b04-117">After clicking *OK* a new job will be created to add the content to a working set, you can monitor the progress of that job in the [Jobs](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-jobs-ediscovery20) tab. ![Add to another working set](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)</span></span>
