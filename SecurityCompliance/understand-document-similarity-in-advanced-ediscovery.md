---
title: Office 365 Advanced eDiscovery でのドキュメントの類似性について理解する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 'ドキュメントの類似性の値、最小レベルの近くに、重複を考慮すべき 2 つのファイルに似ているが電子的証拠開示の Office 365 の詳細設定でどのように動作する方法を確認します。 '
ms.openlocfilehash: 39cd8c31204f0164f6b52c71fa707253cb22758a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531979"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a><span data-ttu-id="65b90-103">Office 365 Advanced eDiscovery でのドキュメントの類似性について理解する</span><span class="sxs-lookup"><span data-stu-id="65b90-103">Understand document similarity in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="65b90-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="65b90-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="65b90-106">高度な電子的証拠開示は、ドキュメントの類似性はの似ているが同じの近くで考慮すべき 2 つの文書に必要な最低限のレベルです。</span><span class="sxs-lookup"><span data-stu-id="65b90-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="65b90-p102">ほとんどのビジネス アプリケーションでは、類似性の値の 60% から 75% を使用することをお勧めします。非常に低品質の光学式文字認識 (OCR) の資料、類似性の低い値を適用できます。</span><span class="sxs-lookup"><span data-stu-id="65b90-p102">For most business applications, it is recommended to use a Similarity value of 60%-75%. For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="65b90-109">設定されているし、特定のケースを実行して、類似性の値は変更できません。</span><span class="sxs-lookup"><span data-stu-id="65b90-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="65b90-p103">Near (ND) を複製し、セット内では、ドキュメント レベルの類似性のしきい値を下回ると似ているところがある可能性があります。ND セットに参加するのにはドキュメントの必要がありますが少なくとも 1 つのドキュメント レベルの類似性を超えるとは異なる設定 ND で。</span><span class="sxs-lookup"><span data-stu-id="65b90-p103">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold. For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="65b90-112">たとえば、類似性が 80% に設定されて、f1 キーをドキュメント レベルの 85%、f2 キーをドキュメントのようなドキュメント F2 F3 の 90% のレベルでのドキュメントのようになります。</span><span class="sxs-lookup"><span data-stu-id="65b90-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="65b90-p104">ただし、f1 キーをドキュメントの F3 をドキュメント レベルのみが 70% のしきい値以下であるようになります。とはいえ、この例では、F1、F2、f3 キーを 1 つの ND すべてが表示されます、ドキュメントを設定します。同様に、80% の類似性の値を使用すると、可能性がありますを作成しました、EquiSet 1、EquiSet 2 の 2 つのセット。EquiSet-1 には、E1、E2 のドキュメントが含まれています。Equiset-2 には、F1、F2 および F3 のドキュメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="65b90-p104">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold. Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set. Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2. EquiSet-1 contains documents E1 and E2. Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="65b90-118">似ているところのレベルは次のようにについて説明します。</span><span class="sxs-lookup"><span data-stu-id="65b90-118">The levels of resemblance are illustrated as follows:</span></span>
  
![ドキュメントの類似性](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="65b90-p105">X1、別のドキュメントが現在挿入されていると仮定します。X1 と E3 の間で似ているとは、87% です。同様に、X1 と F1 の間で似ているは、92% です。その結果、EquiSet-1、-2 の EquiSet と X1 に結合されている 1 つの ND に設定します。</span><span class="sxs-lookup"><span data-stu-id="65b90-p105">Assume that another document, X1, is now inserted. The resemblance between X1 and E3 is 87%. Similarly, the resemblance between X1 and F1 is 92%. As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![ドキュメントの類似性](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="65b90-125">場合、2 つのドキュメントは、ND の 1 つのセットに割り当てられて、同じ ND セットに残りますセットに追加の場合でもドキュメントを追加、セットをマージするかどうかです。</span><span class="sxs-lookup"><span data-stu-id="65b90-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="65b90-126">セットがマージされると後、ピボットのドキュメントは、セットに新しいドキュメントが追加されたときに変更できます。</span><span class="sxs-lookup"><span data-stu-id="65b90-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="65b90-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="65b90-127">See also</span></span>

[<span data-ttu-id="65b90-128">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="65b90-128">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="65b90-129">分析オプションの設定</span><span class="sxs-lookup"><span data-stu-id="65b90-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="65b90-130">設定は無視します。</span><span class="sxs-lookup"><span data-stu-id="65b90-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="65b90-131">分析の設定の詳細設定</span><span class="sxs-lookup"><span data-stu-id="65b90-131">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="65b90-132">分析結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="65b90-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

