---
title: 高度な電子情報開示でスマートタグを設定する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: スマートタグを使用すると、高度な電子情報開示ケースのコンテンツをレビューする際に、machine learning 機能を適用できます。 スマートタググループを使用して、弁護士クライアント特権モデルなどの機械学習の検出モデルの結果を表示します。
ms.openlocfilehash: 68b558cc2282cc388387f8d61825b9ee569ff32a
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703830"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="c6605-104">高度な電子情報開示でスマートタグを設定する</span><span class="sxs-lookup"><span data-stu-id="c6605-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="c6605-105">高度な電子情報開示の Machine learning (ML) 機能を使用すると、レビューセット内のケースドキュメントをレビューする際に、意思決定プロセスをより効率的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c6605-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="c6605-106">スマートタグは、確認時にドキュメントにタグを付けるときに、ML 機能を判断するための方法です。</span><span class="sxs-lookup"><span data-stu-id="c6605-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="c6605-107">スマートタググループを作成すると、スマートタググループに関連付けた ML モデルの結果として、タググループ内のタグがインラインで表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6605-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="c6605-108">これにより、特定のドキュメントをレビューしているときに、ML の結果情報がインラインで表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6605-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="c6605-109">スマートタググループをセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="c6605-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="c6605-110">レビューセットで、[**レビューセットの管理**] をクリックし、[**タグの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6605-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="c6605-111">[**タググループの追加**] をクリックし、[**スマートタググループの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6605-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="c6605-112">タググループに関連付ける ML モデルを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6605-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="c6605-113">これにより、タググループと*n 個*の子タグが作成されます。ここで、 *n*はモデルの可能な出力の数です。</span><span class="sxs-lookup"><span data-stu-id="c6605-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="c6605-114">たとえば、[弁護士クライアント特権検出モデル](attorney-privilege-detection.md)には、次の2つの出力があります。</span><span class="sxs-lookup"><span data-stu-id="c6605-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="c6605-115">**正**: 弁護士クライアントの権限のあるコンテンツを含むドキュメントにタグ付けするには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6605-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="c6605-116">**負の値**: 弁護士クライアントの権限のあるコンテンツを含まないドキュメントにタグ付けするために使用します。</span><span class="sxs-lookup"><span data-stu-id="c6605-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="c6605-117">このモデルを選択すると、2つの子タグを持つタググループが作成されます (これには\*\*\*\*、レビューセットに対して、**肯定**と、もう一方の子タグが付けられます)。</span><span class="sxs-lookup"><span data-stu-id="c6605-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="c6605-118">この例では、各子タグは、弁護士クライアント特権検出モデルから得られる出力のいずれかに対応しています。</span><span class="sxs-lookup"><span data-stu-id="c6605-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="c6605-119">必要に応じて、タググループと子タグの名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c6605-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="c6605-120">たとえば、**正**のタグの名前を**Privileged**に、**負**のタグを特権**なし**に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c6605-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="c6605-121">スマートタグの使用方法</span><span class="sxs-lookup"><span data-stu-id="c6605-121">How to use smart tags</span></span>

<span data-ttu-id="c6605-122">ドキュメントをレビューするときは、適切な子タグの横にモデルの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6605-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="c6605-123">たとえば、弁護士側の権限を検出するためのスマートタググループがあり、潜在的な権限があるドキュメントを確認した場合は、その結論の理由が該当するタグの横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6605-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="c6605-124">タグがドキュメントに自動的に適用されない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c6605-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="c6605-125">レビュー担当者は、ドキュメントをタグ付けする方法について決定を行います。</span><span class="sxs-lookup"><span data-stu-id="c6605-125">The reviewer makes the decision about how to tag the document.</span></span>