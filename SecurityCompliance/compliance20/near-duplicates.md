---
title: 重複データ検出の近く
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: a3f5945ee4ba0a1bc78ab6c8ccc9af934d392232
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608008"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="1548f-102">重複データ検出の近く</span><span class="sxs-lookup"><span data-stu-id="1548f-102">Near duplicate detection</span></span>

<span data-ttu-id="1548f-p101">サブセットを同じテンプレートに基づくし、はほとんど同じ定型言語、いくつかの違い、あちこちで情報を確認するドキュメントのセットを検討してください。校閲者でしたこのサブセット、徹底的に、それらのいずれかを確認し、残りの部分の違いを確認する場合はないが欠落していない固有の情報は、時間の一部のみを取るまでカバーするカバーのすべてのドキュメントを読み取るために。近くの重複データ検出は、レビュー プロセスをより効率的に行うことができます一緒にテキストのようなドキュメントをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="1548f-p101">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there. If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover. Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="1548f-106">どのように動作するか。</span><span class="sxs-lookup"><span data-stu-id="1548f-106">How does it work?</span></span>

<span data-ttu-id="1548f-p102">近くにある重複データ検出を実行すると、システムはすべてのドキュメントのテキストを解析します。次に、これらの類似性が設定されたしきい値より大きいかどうかを決定するためにすべてのドキュメントを比較します。場合は、ドキュメントがまとめてグループ化されます。各グループからのドキュメントが「ピボット」; としてマークされているすべてのドキュメントを比較され、グループ化されたが後、ドキュメントを確認するには、ピボットをまず確認し、ピボットとレビューに含まれるドキュメントの違いに焦点を当てるに重複する設定は、ほぼ同じで、他のドキュメントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1548f-p102">When near duplicate detection is run, the system parses every document with text. Then, it compares every document against each other to determine whether their similarity is greater than the set threshold. If it is, the documents are grouped together. Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>