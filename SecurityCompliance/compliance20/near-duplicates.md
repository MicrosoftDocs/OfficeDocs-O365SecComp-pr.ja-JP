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
# <a name="near-duplicate-detection"></a>重複データ検出の近く

サブセットを同じテンプレートに基づくし、はほとんど同じ定型言語、いくつかの違い、あちこちで情報を確認するドキュメントのセットを検討してください。校閲者でしたこのサブセット、徹底的に、それらのいずれかを確認し、残りの部分の違いを確認する場合はないが欠落していない固有の情報は、時間の一部のみを取るまでカバーするカバーのすべてのドキュメントを読み取るために。近くの重複データ検出は、レビュー プロセスをより効率的に行うことができます一緒にテキストのようなドキュメントをグループ化します。

## <a name="how-does-it-work"></a>どのように動作するか。

近くにある重複データ検出を実行すると、システムはすべてのドキュメントのテキストを解析します。次に、これらの類似性が設定されたしきい値より大きいかどうかを決定するためにすべてのドキュメントを比較します。場合は、ドキュメントがまとめてグループ化されます。各グループからのドキュメントが「ピボット」; としてマークされているすべてのドキュメントを比較され、グループ化されたが後、ドキュメントを確認するには、ピボットをまず確認し、ピボットとレビューに含まれるドキュメントの違いに焦点を当てるに重複する設定は、ほぼ同じで、他のドキュメントを確認できます。