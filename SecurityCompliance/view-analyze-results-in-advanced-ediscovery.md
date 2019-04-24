---
title: Office の分析結果を表示する 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: '表示されているタスクオプションの定義を含む、Office 365 Advanced eDiscovery の分析プロセスの結果を表示する場所について説明します。  '
ms.openlocfilehash: 990bcbb3c6626521d40f7ce057c764200d5047b5
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32267111"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a>Office の分析結果を表示する 365 Advanced eDiscovery

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
詳細な電子情報開示では、以下に示すように、分析プロセスの進行状況と結果をさまざまな方法で表示できます。
  
## <a name="view-analyze-task-status"></a>タスクの進捗状況を表示する

[**結果\> \>の\>分析タスクの状態の準備**] では、プロセスの実行中および分析後に状態が表示されます。 
  
![タスクの進捗状況の分析](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
表示されるタスクは、選択したオプションによって異なる場合があります。 
  
- **ND/ET: セットアップ**: 実行の準備をします。たとえば、run および case パラメーターを設定します。
    
- **nd/ET: nd 計算**: ファイルのほぼ重複した分析を処理します。
    
- **ND/et: et 計算**: 電子メールセット全体で電子メールスレッド分析を実行します。
    
- **ND/ET: pivot and 類似性**: ピボットおよびファイル類似性処理を実行します。
    
- [ **ND/ET: metadata update**]: データベース内のファイルで収集された新しいデータがファイナライズされます。
    
- **テーマ: テーマの計算**: テーマの分析を実行します。 (選択されている場合のみ表示されます)。
    
- **タスクの状態**: この行は、タスクの完了後に表示されます。 タスクの実行中は、実行期間が表示されます。
    
> [!NOTE]
> ほぼ重複した電子メールスレッド (ND および ED) の分析結果は、処理するドキュメント数に適用されます。 完全に重複したファイルは含まれません。 
  
## <a name="view-near-duplicates-and-email-threads-status"></a>ほぼ重複した電子メールスレッドの状態を表示する

**ターゲット**の作成結果には、対象の作成におけるドキュメント、メール、添付ファイル、およびエラーの数が表示されます。 
  
**ドキュメント**の結果には、ピボットの数、一意の重複した一意のファイル、および正確な重複ファイルが表示されます。 
  
電子**メール**の結果には、包括数、包括的な一意の包括的コピー、および残りの電子メールメッセージの数が表示されます。 さまざまな種類の電子メールの結果は次のとおりです。 
  
- **包括**: 包括的な電子メールは、電子メールスレッドの終了ノードであり、そのスレッドの以前のすべての履歴が含まれています。 その結果、レビュー担当者は、スレッド内の前のメッセージを読み取らずに、包括的な電子メールに安全に集中できます。 
    
- **包括マイナス**: 包括的な電子メールの親に関連付けられた1つまたは複数の異なる添付ファイルがある場合は、包括的な電子メールが包括を差し引いたものとして指定されます。 このコンテキストでは、"Parent" という用語が、その特定の包括的な電子メールに含まれている電子メールスレッドまたは会話の上にあるメッセージに使用されます。 レビュー担当者は、包括的なマイナス表示をシグナルとして使用できますが、包括的な電子メールの親の内容を確認する必要はないかもしれませんが、この包含パスの親に関連付けられている添付ファイルを確認すると便利な場合があります。 
    
- **包括的コピー**: 包括的なメールまたは包括的なメールが含まれている別のメッセージのコピーである場合は、包括コピーとして指定します。 言い換えると、このメッセージの件名と本文は別の包括的なメッセージと同じであり、同じノードに共存しています。 包括的なコピーメッセージには同じ内容が含まれているため、通常はレビュープロセスでスキップできます。 
    
- **rest**: これは、一意のコンテンツがまったく含まれていないため、上記の3つのカテゴリに分類されないメールを示します。 これらの電子メールメッセージを確認する必要はありません。 メッセージに添付ファイルが含まれていて、それより後の包括的な電子メールに含まれていない場合は、添付ファイルのレビューが必要になる可能性があります。 これは、スレッド内に包括的なマイナスの電子メールが存在することによって示されます。
    
**添付ファイル**の結果には、重複した種類によって添付ファイルの数が表示されます。 
  
![類似および電子メールのスレッド](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[ドキュメントの類似点について](understand-document-similarity-in-advanced-ediscovery.md)
  
[分析オプションの設定](set-analyze-options-in-advanced-ediscovery.md)
  
[無視するテキストの設定](set-ignore-text-in-advanced-ediscovery.md)
  
[[詳細設定の分析] の設定](view-analyze-results-in-advanced-ediscovery.md)

