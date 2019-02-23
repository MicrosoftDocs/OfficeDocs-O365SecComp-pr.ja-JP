---
title: Office 365 Advanced eDiscovery でのドキュメントの類似性について理解する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 'ドキュメントの類似性の値を確認します。2つのファイルの resemblance の最小レベルは、重複していると見なされ、Office 365 の高度な電子情報開示で機能します。 '
ms.openlocfilehash: eb8f07ceedb10bd0152693dd1e82a28797d86a5a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220427"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a><span data-ttu-id="a8127-103">Office 365 Advanced eDiscovery でのドキュメントの類似性について理解する</span><span class="sxs-lookup"><span data-stu-id="a8127-103">Understand document similarity in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="a8127-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="a8127-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="a8127-106">詳細な電子情報開示では、ドキュメントの類似性は、2つのドキュメントがほぼ重複していると見なされるために必要な resemblance の最小レベルです。</span><span class="sxs-lookup"><span data-stu-id="a8127-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="a8127-p102">ほとんどのビジネスアプリケーションでは、類似性値 60%-75% を使用することをお勧めします。非常に低品質な光学式文字認識 (OCR) 資料の場合は、類似性の値を低くして適用できます。</span><span class="sxs-lookup"><span data-stu-id="a8127-p102">For most business applications, it is recommended to use a Similarity value of 60%-75%. For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a8127-109">特定のケースに対して設定して実行した後、類似性の値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a8127-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="a8127-p103">同一の複製 (ND) セット内では、類似性のしきい値の下に resemblance レベルのドキュメントが存在することがあります。文書を nd セットに参加させるには、その類似性を超えるレベルの resemblance で、nd セットに少なくとも1つのドキュメントが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8127-p103">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold. For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="a8127-112">たとえば、類似性が 80% に設定されている場合、document F1 はレベル 85% のドキュメント f2 に似ていますが、ドキュメント f2 はドキュメント F3 のレベルが 90% であると仮定します。</span><span class="sxs-lookup"><span data-stu-id="a8127-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="a8127-p104">ただし、document F1 は、しきい値を下回る 70% のレベルで、document F3 のようになります。しかし、この例では、ドキュメント F1、F2、および F3 はすべて、一方の ND セットに表示されます。同様に、類似性値 80% を使用すると、2つのセットが作成されている可能性があります。設定-1 には、E1 および E2 というドキュメントが含まれています。[設定] は、ドキュメント F1、F2、および F3 を含みます。</span><span class="sxs-lookup"><span data-stu-id="a8127-p104">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold. Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set. Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2. EquiSet-1 contains documents E1 and E2. Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="a8127-118">resemblance のレベルは次のように示されています。</span><span class="sxs-lookup"><span data-stu-id="a8127-118">The levels of resemblance are illustrated as follows:</span></span>
  
![ドキュメントの類似性](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="a8127-p105">別のドキュメント X1 が挿入されたと仮定します。X1 と E3 の間の resemblance は 87% です。同様に、X1 と F1 の間の resemblance は 92% です。その結果として、すべての設定が1つの ND セットに結合されるようにします。</span><span class="sxs-lookup"><span data-stu-id="a8127-p105">Assume that another document, X1, is now inserted. The resemblance between X1 and E3 is 87%. Similarly, the resemblance between X1 and F1 is 92%. As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![ドキュメントの類似性](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="a8127-125">1つの nd セットに2つのドキュメントが割り当てられている場合は、そのセットに追加のドキュメントが追加された場合でも、セットが結合された場合でも、同じ nd セットに残ります。</span><span class="sxs-lookup"><span data-stu-id="a8127-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="a8127-126">設定が結合されると、新しい文書がセットに追加されたときにピボットドキュメントが変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="a8127-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a8127-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8127-127">See also</span></span>

[<span data-ttu-id="a8127-128">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a8127-128">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a8127-129">分析オプションの設定</span><span class="sxs-lookup"><span data-stu-id="a8127-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a8127-130">無視するテキストの設定</span><span class="sxs-lookup"><span data-stu-id="a8127-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
<span data-ttu-id="a8127-131">[[詳細設定の分析] の設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="a8127-131">[Setting Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md)</span></span>
  
[<span data-ttu-id="a8127-132">分析結果の表示</span><span class="sxs-lookup"><span data-stu-id="a8127-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

