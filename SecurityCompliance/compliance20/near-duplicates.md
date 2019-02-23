---
title: 準重複の検出
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 40270fa1e3a6f7cdf0dd2a83650aa36a935d9a6d
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213127"
---
# <a name="near-duplicate-detection"></a>準重複の検出

サブセットが同じテンプレートを基にしていて、ほとんど同じ定型表現を持っており、ここではいくつかの違いがある、ドキュメントのセットをレビューすることを検討してください。レビュー担当者がこのサブセットを特定し、そのうちの1つを徹底的に確認して、残りの相違点を確認した場合は、すべてのドキュメントカバーの読み取りにかかる時間が限られているため、固有の情報が失われることはありません。ほぼ重複した検出グループでは、よく似たドキュメントが一緒に表示され、レビュープロセスの効率を高めることができます。

## <a name="how-does-it-work"></a>どのように動作するか。

近い重複検出が実行されると、システムによってすべてのドキュメントがテキストで解析されます。次に、すべてのドキュメントを比較して、類似性が設定されたしきい値より大きいかどうかを判断します。その場合、ドキュメントはグループ化されています。すべてのドキュメントを比較してグループ化すると、各グループのドキュメントが "pivot" としてマークされます。ドキュメントを確認するには、ピボットを最初に確認して、同じ付近にある重複セット内の他のドキュメントを確認して、ピボットとレビュー中のドキュメントの違いに焦点を合わせます。