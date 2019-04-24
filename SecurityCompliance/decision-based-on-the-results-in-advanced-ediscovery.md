---
title: Office 365 の高度な電子情報開示の結果に基づく決定
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 'Office 365 の Advanced eDiscovery の [判断] タブで、ケースファイルのレビューセットの適切なサイズを決定するのに役立つデータを提供する方法について説明します。 '
ms.openlocfilehash: a9250a45129320517f96b9a335db95d164d2dae7
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257822"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a>Office 365 の高度な電子情報開示の結果に基づく決定

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
 上級電子情報開示の場合、[判断] タブでは、サポートの判断に関する詳細情報を提供して、ケースファイルのレビューセットのサイズを決定します。 
  
## <a name="using-the-decide-tab"></a>[判断] タブの使用

![関連性の決定](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
このタブには次のものが含まれます。
  
- **問題**: ここから、対象の問題をリストから選択できます。 
    
- **レビュー-取り消し率**: 関連性スコアによる高度な電子情報開示レビューの比較。 グラフのカットオフポイントは、関連性スコアにマッピングされた、確認するファイルのパーセンテージを表します。 これは、関連性テストフェーズで、カリングのエクスポートしきい値として使用されます。 既定のカットオフポイントは、確認するファイル数に対して、呼び戻しと精度の間のバランスが最適であるポイントです。 実際のカットオフポイントは、目標とコストのトレードオフ (% レビュー) およびリスク (% のリコール) に応じて、ユーザーによって決定される必要があります。スライダーを使用して、カットオフポイントを調整し、グラフおよびパラメータに対する影響を確認したり、取得する関連ファイルの割合を調整したり、決定を検証したりすることができます。
    
- **パラメーター**: review、呼び戻し、次の関連性、およびコストの合計パラメーターは、ケース全体のコレクションに対するレビューセットに関連する累積計算された統計情報です。 これらのパラメーターの定義は次のとおりです。
    
    **レビュー**: このカットオフに基づいてレビューするファイルのパーセンテージ。 
    
    [**呼び戻し**: 校閲セット内の関連ファイルのパーセンテージ。 
    
    **次に関連**する: 現在レビューセットに含まれていない追加の関連ファイルを確認して識別するためのコスト。 
    
    **合計コスト**: この割合のケースファイルを確認するためのコスト。 コストパラメーターの設定は、ケースマネージャーで設定できます。
    
- **関連性スコア別の配布**: 濃い灰色表示のファイルは、左側にカットオフスコアの下にあります。 ツールヒントには、関連スコアと、レビューファイルセット内のファイルの関連パーセンテージが、ファイル総数に対して表示されます。
    
拡張された詳細ウィンドウには、追加の詳細が表示されます。 コレクションの図のファイルには、空または nebulous ファイルは含まれません。 ファミリーファイル図は、関連性がなく、ファミリーの一部としてカウントされているファイルを表します。
  
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[関連性の評価について](assessment-in-relevance-in-advanced-ediscovery.md)
  
[タグ付けと評価](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[関連性トレーニングの実行](tagging-and-assessment-in-advanced-ediscovery.md)
  
[関連性分析の追跡](track-relevance-analysis-in-advanced-ediscovery.md)
  
[関連性分析のテスト](test-relevance-analysis-in-advanced-ediscovery.md)

