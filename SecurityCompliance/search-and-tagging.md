---
title: 検索とタグ付け
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 高度な電子的証拠開示、検索し、名札管理モジュールを使用すると、検索、プレビュー、および、ケース内のドキュメントを整理できます。現時点では、このモジュールは、ベータ版です。
ms.openlocfilehash: fde887e496e9a40aa88d841053a0c66e48f04200
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532229"
---
# <a name="search-and-tagging"></a>検索とタグ付け

高度な電子的証拠開示、検索し、名札管理モジュールを使用すると、検索、プレビュー、および、ケース内のドキュメントを整理できます。現時点では、このモジュールは、ベータ版です。

> [!NOTE]
> 高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。 
  
## <a name="search-the-documents-in-your-case"></a>場合、ドキュメントを検索します。

高度な電子的証拠開示のドキュメントを処理すると、分析モジュール、または関連性の高いモジュールを必要に応じて実行する、検索を使用することができ、名札ケース内のドキュメントを検索し、それらを整理する場合に固有のタグを使用しています。指定された条件のカードを使用するクエリを定義したり、カードの条件を [キーワード] KQL のようなクエリ言語を使用してできます。AND、OR、NOT などの一般的な KQL 構文はサポートされていると同様に後続複数文字のワイルドカード (*)、NEAR(n) とします。クエリ言語のプロパティ名では、これらのプロパティがサポートされています。

- caselabel: このサポート案件の検索し、名札の作成と適用される同じタグ 
- 通告: 制限の場合は、割り当てられている通告
- 日付: 送信メールの日付、ドキュメントの日付を変更します。
- ファイル id: ファイル ID の大文字と小文字の
- ファイルの種類: ネイティブのファイルの拡張子
- fileclass: 電子メール、ドキュメント、または添付ファイル
- senderauthor: 送信者の e メール、ドキュメントの作成者
- サイズ: KB のファイルのサイズ
- subjecttitle: 電子メールの場合、ドキュメントのタイトルは件名
- Bcc
- Cc
- 参加者: 無効なリンクを含む、電子メール スレッドのすべての参加者のアドレスを電子メールで送信
- 受信: 受信日
- 宛先: 受信者の名前またはアドレス (宛先、cc、bcc) の電子メールを送信
- 送信者
- lastmodifieddate: ドキュメントの日付が最終更新日
- 送信: 送信メールの日付
- から
- 作成者: 電子メールの作成者
- タイトル: ドキュメントのタイトル
- dominanttheme: 項目の優先度の高いテーマ\*
- themeslist: 項目に関連付けられているテーマ\*
- readpercentile_ [issuenum]: 読み取りの問題 [issuenum] の項目には、百分位数\*\*
- relevancescore_ [issuenum]: 問題 [issuenum] の項目の関連性スコア\*\*
- relevancetag_ [issuenum]: [issuenum] には、そのタグの関連性の項目を手動でタグしてかどうか\*\*

\*テーマ モジュールが実行された場合にのみ使用可能な\*\*関連性の高いモジュールが実行された場合にのみ使用可能
  
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[関連性の評価を理解します。](assessment-in-relevance-in-advanced-ediscovery.md)
  
[タグ付けおよび評価](tagging-and-assessment-in-advanced-ediscovery.md)
  
[タグ付けと関連性の高いトレーニング](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[追跡の関連性の分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[結果に基づいて決定します。](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[テストの関連性の分析](test-relevance-analysis-in-advanced-ediscovery.md)

