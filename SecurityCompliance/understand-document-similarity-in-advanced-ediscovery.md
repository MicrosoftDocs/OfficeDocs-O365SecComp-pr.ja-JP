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
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a>Office 365 Advanced eDiscovery でのドキュメントの類似性について理解する

> [!NOTE]
> 高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。 
  
高度な電子的証拠開示は、ドキュメントの類似性はの似ているが同じの近くで考慮すべき 2 つの文書に必要な最低限のレベルです。
  
> [!TIP]
> ほとんどのビジネス アプリケーションでは、類似性の値の 60% から 75% を使用することをお勧めします。非常に低品質の光学式文字認識 (OCR) の資料、類似性の低い値を適用できます。 
  
> [!NOTE]
> 設定されているし、特定のケースを実行して、類似性の値は変更できません。 
  
Near (ND) を複製し、セット内では、ドキュメント レベルの類似性のしきい値を下回ると似ているところがある可能性があります。ND セットに参加するのにはドキュメントの必要がありますが少なくとも 1 つのドキュメント レベルの類似性を超えるとは異なる設定 ND で。 
  
たとえば、類似性が 80% に設定されて、f1 キーをドキュメント レベルの 85%、f2 キーをドキュメントのようなドキュメント F2 F3 の 90% のレベルでのドキュメントのようになります。 
  
ただし、f1 キーをドキュメントの F3 をドキュメント レベルのみが 70% のしきい値以下であるようになります。とはいえ、この例では、F1、F2、f3 キーを 1 つの ND すべてが表示されます、ドキュメントを設定します。同様に、80% の類似性の値を使用すると、可能性がありますを作成しました、EquiSet 1、EquiSet 2 の 2 つのセット。EquiSet-1 には、E1、E2 のドキュメントが含まれています。Equiset-2 には、F1、F2 および F3 のドキュメントが含まれています。 
  
似ているところのレベルは次のようにについて説明します。
  
![ドキュメントの類似性](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
X1、別のドキュメントが現在挿入されていると仮定します。X1 と E3 の間で似ているとは、87% です。同様に、X1 と F1 の間で似ているは、92% です。その結果、EquiSet-1、-2 の EquiSet と X1 に結合されている 1 つの ND に設定します。
  
![ドキュメントの類似性](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> 場合、2 つのドキュメントは、ND の 1 つのセットに割り当てられて、同じ ND セットに残りますセットに追加の場合でもドキュメントを追加、セットをマージするかどうかです。 
  
セットがマージされると後、ピボットのドキュメントは、セットに新しいドキュメントが追加されたときに変更できます。 
  
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[分析オプションの設定](set-analyze-options-in-advanced-ediscovery.md)
  
[設定は無視します。](set-ignore-text-in-advanced-ediscovery.md)
  
[分析の設定の詳細設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[分析結果を表示します。](view-analyze-results-in-advanced-ediscovery.md)

