---
title: 検索とタグ付け
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 高度な電子的証拠開示、検索し、名札管理モジュールを使用すると、検索、プレビュー、および、ケース内のドキュメントを整理できます。現時点では、このモジュールは、ベータ版です。
ms.openlocfilehash: 013e559ca55e9a877dfb2f8747c4696f81e1e095
ms.sourcegitcommit: 25f1028643d8a20d17306e8b09cafea46eaf7a58
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2019
ms.locfileid: "29666147"
---
# <a name="search-and-tagging"></a>検索とタグ付け

高度な電子的証拠開示、検索し、名札管理モジュールを使用すると、検索、プレビュー、および、ケース内のドキュメントを整理できます。現時点では、このモジュールは、ベータ版です。検索とタグ付けの簡単なデモでは、[高度な電子的証拠開示を使用してデータの管理](https://www.youtube.com/watch?v=VaPYL3DHP6I)のビデオを参照してください。

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
## <a name="search-the-documents-in-your-case"></a>場合、ドキュメントを検索します。

した後、高度な電子的証拠開示のケース内のドキュメントの処理 (分析や関連性のモジュールを必要に応じて実行)、ドキュメントを検索し、(ラベルとも呼ばれます) に固有の大文字と小文字のタグを適用することによって整理を検索し、名札を使用できます。指定された条件のカードを使用して検索クエリを定義したり、キーワードで KQL のようなクエリ言語を使用して、カードの条件します。AND、OR、NOT などの一般的な KQL 構文はサポートされていると同様に後続複数文字のワイルドカード (*)、NEAR(n) とします。 

KQL キーワード クエリを使用するために検索可能なプロパティを次の表に一覧します。代わりに、検索クエリ (選択したプロパティ) の条件を追加するのには、高度な電子的証拠開示検索ツールでの条件のカードを使用できます。

|**プロパティ**|**説明**|
|:-----|:-----|
|**caselabel** <br/> | 文書をタグ付けするときに作成/適用するタグの名前。 <br/> |
|**保管担当者** <br/> | ドキュメントに関連付けられている保管担当者制限にさらされます。 <br/> |
|**日付** <br/> | 送信日時のメールです。サイトのドキュメントの変更された日付です。 <br/> |
|**ファイル id** <br/> | ケース内のファイル ID です。 <br/> |
|**ファイルの種類** <br/> | ネイティブ ファイルの拡張子。 <br/> |
|**fileclass** <br/> | 電子メール、ドキュメント、または添付ファイルです。 <br/> |
|**senderauthor** <br/> | 送信者の電子メールです。サイトのドキュメントの作成者です。 <br/> |
|**サイズ** <br/> | KB のファイルのサイズ。 <br/> |
|**subjecttitle** <br/> | 電子メールの件名サイトのドキュメントのタイトル。 <br/> |
|**Bcc** <br/> | 電子メールの Bcc フィールドです。 <br/> |
|**Cc** <br/> | 電子メールの Cc フィールドです。 <br/> |
|**参加者** <br/> | 無効なリンクを含む、電子メール スレッドのすべての参加者の電子メール アドレスです。 <br/> |
|**受信しました** <br/> | 電子メールが受信された日付。 <br/> |
|**受信者** <br/> | 宛先、Cc、または Bcc のフィールドには、電子メールの受信者が含まれています。 <br/> |
|**送信者** <br/> | 電子メールの送信者です。 <br/> |
|**lastmodifieddate** <br/> | 最終では、サイトのドキュメントの日付を変更します。 <br/> |
|**送信** <br/> | 電子メールの送信日。 <br/> |
|**宛先** <br/> | 受信する電子メールの [宛先] フィールドに記載されています。 <br/> |
|**作成者** <br/> | サイトのドキュメントの作成者です。 <br/> |
|**title** <br/> | サイトのドキュメントのタイトルです。 <br/> |
|**dominanttheme**\* <br/> | アイテムの優先度の高いテーマです。 <br/> |
|**themeslist**\* <br/> | アイテムに関連付けられているテーマです。 <br/> |
|**readpercentile_ [issuenum]**\*\* <br/> | [Issuenum] で定義されている現象で、アイテムの読み取りの百分位です。 <br/> |
|**relevancescore_ [issuenum]**\*\* <br/> | [Issuenum] で定義されている現象で、アイテムの関連性スコアです。 <br/> |
|**relevancetag_ [tagname]**\*\* <br/> | 項目がある場合手動でタグが付けられて、[タグ名] で定義されているタグの関連性について。 <br/> |
|||

\*テーマ モジュールが実行された場合にのみ使用できます。

\*\*関連モジュールが実行された場合にのみ使用できます。

代わりに、検索クエリ (選択したプロパティ) の条件を追加するのには、高度な電子的証拠開示検索ツールの条件のカードを使用できます。次のスクリーン ショットは、クエリに追加できる条件を示しています。**[グループ**] 列では、電子メール、サイトのドキュメント、または両方 (*共通*の値で示されます) にプロパティが適用されるかどうかを示します。この列は、関連性の高いモジュールを実行した後に表示される検索可能なプロパティを識別します。

![高度な電子的証拠開示検索ツールで検索条件](media/AeDSearchConditions.png)

検索可能なプロパティの詳細については、[キーワード クエリと検索条件](keyword-queries-and-search-conditions.md)を参照してください。
  
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[関連性の評価を理解します。](assessment-in-relevance-in-advanced-ediscovery.md)
  
[タグ付けおよび評価](tagging-and-assessment-in-advanced-ediscovery.md)
  
[タグ付けと関連性の高いトレーニング](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[追跡の関連性の分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[結果に基づいて決定します。](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[テストの関連性の分析](test-relevance-analysis-in-advanced-ediscovery.md)

