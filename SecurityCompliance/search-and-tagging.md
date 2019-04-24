---
title: 検索とタグ付け
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 高度な電子情報開示では、検索とタグ付けモジュールを使用して、ケースでドキュメントを検索、プレビュー、および整理することができます。 現時点では、このモジュールはベータ版です。
ms.openlocfilehash: 58913a01f30b4169470592f5fc271e3ce785ac5d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261372"
---
# <a name="search-and-tagging"></a>検索とタグ付け

高度な電子情報開示では、検索とタグ付けモジュールを使用して、ケースでドキュメントを検索、プレビュー、および整理することができます。 現時点では、このモジュールはベータ版です。 検索とタグ付けの概要については、「 [Advanced eDiscovery ビデオでデータを管理](https://www.youtube.com/watch?v=VaPYL3DHP6I)する」を参照してください。

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
## <a name="search-the-documents-in-your-case"></a>ケースでドキュメントを検索する

高度な電子情報開示ケースでドキュメントを処理した後 (必要に応じて Analyze または関連性モジュールを実行すると)、検索とタグ付けを使用してドキュメントを検索し、大文字と小文字を区別したタグ (ラベルとも呼ばれます) を適用することで、それらを整理することができます。 検索クエリは、指定された条件カードを使用するか、またはキーワードの条件カードで kql のようなクエリ言語を使用して定義できます。 and、OR、NOT、NEAR (n) などの一般的な kql 構文がサポートされています。また、末尾の複数文字ワイルドカード (*) もサポートされています。 

次の表に、kql キーワードクエリを使用して検索できるプロパティを示します。 または、高度な電子情報開示検索ツールで条件カードを使用して、検索クエリに条件 (選択したプロパティの場合) を追加することもできます。

|**プロパティ**|**説明**|
|:-----|:-----|
|**caselabel** <br/> | 文書にタグ付けするときに作成/適用されるタグの名前を指定します。 <br/> |
|**保管担当者** <br/> | ドキュメントに関連付けられている保管担当者。制限の対象となります。 <br/> |
|**date** <br/> | 電子メールの送信日。サイトドキュメントの変更された日付。 <br/> |
|**fileid** <br/> | ケース内のファイル ID。 <br/> |
|**filetype** <br/> | ネイティブファイル拡張子。 <br/> |
|**fileclass** <br/> | 電子メール、ドキュメント、または添付ファイル。 <br/> |
|**senderauthor** <br/> | 電子メールの送信者。サイトドキュメントの作成者。 <br/> |
|**size** <br/> | ファイルのサイズ (KB 単位)。 <br/> |
|**subjecttitle** <br/> | 電子メールの件名。サイトドキュメントのタイトル。 <br/> |
|**bcc** <br/> | 電子メールの Bcc フィールド。 <br/> |
|**cc** <br/> | 電子メールの Cc フィールド。 <br/> |
|**participants** <br/> | 電子メールスレッド内のすべての参加者の電子メールアドレス (存在しないリンクを含む)。 <br/> |
|**received** <br/> | 電子メールが受信された日付。 <br/> |
|**recipients** <br/> | [宛先]、[Cc]、または [Bcc] フィールドに含まれている電子メールの受信者。 <br/> |
|**sender** <br/> | 電子メールの送信者。 <br/> |
|**lastmodifieddate** <br/> | サイトドキュメントの最終更新日。 <br/> |
|**sent** <br/> | 電子メールの送信日。 <br/> |
|**to** <br/> | 電子メールの宛先フィールドに記載されている受信者。 <br/> |
|**判別** <br/> | サイトドキュメントの作成者。 <br/> |
|**title** <br/> | サイトドキュメントのタイトル。 <br/> |
|**dominanttheme**\* <br/> | アイテムの主要なテーマ。 <br/> |
|**テーマ一覧**\* <br/> | アイテムに関連付けられているテーマ。 <br/> |
|**readpercentile_ [# enum]**\*\* <br/> | アイテムの閲覧の百分位。 [設定] で定義されている問題を示します。 <br/> |
|**relevancescore_ [# enum]**\*\* <br/> | アイテムの関連性スコア。 [/設定] で定義されている問題について。 <br/> |
|**relevancetag_ [tagname]**\*\* <br/> | 関連性に対して手動でタグ付けされたアイテムの場合は、[tagname] で定義されているタグ。 <br/> |
|||

\*Themes モジュールが実行されている場合にのみ使用できます。

\*\*関連性モジュールが実行されている場合にのみ使用できます。

または、高度な電子情報開示検索ツールの条件カードを使用して、検索クエリに条件 (選択したプロパティの場合) を追加することもできます。 次のスクリーンショットは、クエリに追加できる条件を示しています。 [**グループ]** 列は、プロパティが電子メール、サイトドキュメント、またはその両方に適用されるかどうかを示します (*共通*の値で示されます)。 この列は、関連性モジュールを実行した後に使用できる検索可能なプロパティも識別します。

![高度な電子情報開示検索ツールの検索条件](media/AeDSearchConditions.png)

検索可能なプロパティの詳細については、「[キーワードクエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。
  
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[関連性の評価について](assessment-in-relevance-in-advanced-ediscovery.md)
  
[タグ付けと評価](tagging-and-assessment-in-advanced-ediscovery.md)
  
[タグ付けと関連性トレーニング](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[関連性分析の追跡](track-relevance-analysis-in-advanced-ediscovery.md)
  
[結果に基づいて決定する](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[関連性分析のテスト](test-relevance-analysis-in-advanced-ediscovery.md)

