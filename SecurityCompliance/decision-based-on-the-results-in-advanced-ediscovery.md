---
title: Office 365 Advanced eDiscovery の結果に基づく判断
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 'レビュー一連の大文字のファイルの正確なサイズを決定する際に役立つデータを電子的証拠開示の Office 365 の詳細設定で [決定] タブが提供するしくみについて説明します。 '
ms.openlocfilehash: 58a181e00ad5843ccbbde4dcb47050eccf199225
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531864"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a>Office 365 Advanced eDiscovery の結果に基づく判断

> [!NOTE]
> 高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。 
  
 高度な電子的証拠開示を決定するタブは、表示して、レビューのケースのファイルのサイズを決定する意思決定支援の統計情報を使用してに関する詳細情報を提供します。 
  
## <a name="using-the-decide-tab"></a>決定] タブを使用

![関連性の決定](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
このタブには次のものが含まれています。
  
- **問題**: ここでは、一覧から目的の問題を選択することができます。 
    
- **レビュー リコール率**: 妥当性の度合いによって電子的証拠開示の比較の高度なレビューです。グラフ内のカットオフ ポイントは、関連性のスコアにマップを確認して、ファイルの割合を表します。カリングは、エクスポートのしきい値と関連性のテスト フェーズで使用されます。ファイルの数を確認するのには、既定カットオフ ポイントでは、リコールと精度のバランスが最適な位置にします。目標とコストのトレードオフ (% レビュー) とリスク (% リコール) によってユーザーが実際のカットオフ ポイントを決定してください。スライダーを使用すると、カットオフ ポイントを調整し、意思決定を検証する前に取得するには、関連するファイルの % を調整するときにグラフやパラメーターへの影響を参照してください。
    
- **パラメーター**: を確認し、呼び戻すには、次の関連性の合計コスト パラメーターは、コレクション全体のケースを基準に設定の確認に関連する計算された統計情報の累積的な。これらのパラメーターの定義は次のとおりです。
    
    **確認**: このカットオフ値に基づいて、ファイルの割合を確認します。 
    
    **取り消し**: レビューのセットに関連するファイルの割合。 
    
    **次関連**: を確認し、レビューにも設定されていないその他の関連のファイルを識別するためのコストです。 
    
    **総コスト**: 大文字のファイルの割合を確認するためのコストです。ケース マネージャーでは、コストのパラメーターの設定を設定できます。
    
- **関連性のスコアを使用した配分**: カットオフ スコアの下の左側に、濃いグレーで表示内のファイルです。ツール ヒントは、ファイルの合計数を基準に設定確認ファイル内の関連性スコアと関連ファイルの割合を表示します。
    
展開の詳細ウィンドウには、追加の詳細が表示されます。図表のコレクション内のファイルでは、空であるか、または漠然としたファイルは含まれません。ファミリのファイルの図は、関連性の高さに読み込まれていないファミリの一部として入っているファイルを表します。
  
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[関連性の評価を理解します。](assessment-in-relevance-in-advanced-ediscovery.md)
  
[タグ付けおよび評価](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[関連性の高いトレーニングを実行します。](tagging-and-assessment-in-advanced-ediscovery.md)
  
[追跡の関連性の分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[テストの関連性の分析](test-relevance-analysis-in-advanced-ediscovery.md)

