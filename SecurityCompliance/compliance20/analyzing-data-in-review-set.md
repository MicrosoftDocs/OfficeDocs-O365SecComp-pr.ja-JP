---
title: 高度な電子情報開示のレビューセットのデータを分析する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: cfed07d473f2af367de4cb2e9fe924a29e4123cd
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155209"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>高度な電子情報開示のレビューセットのデータを分析する

収集されたドキュメントの数が多い場合は、それらをすべて確認するのは非常に困難です。 Advanced eDiscovery には、ドキュメントを分析して、情報が失われずにレビューされるドキュメントのボリュームを減らし、一貫性のある方法でドキュメントを整理するのに役立つさまざまなツールが用意されています。 これらの機能の詳細については、以下を参照してください。

- [準重複の検出](near-duplicates.md)

- [電子メールのスレッド化](email-threading.md)

- [テーマ](themes.md)

レビューセット内のデータを分析するには、次のようにします。

1. ケースの分析設定を構成します。 詳細については、「 [Configure search and analytics settings](configure-search-analytics-settings.md)」を参照してください。

2. 分析するレビューセットを開きます。

3. [**レビューセットの管理**] をクリックします。

4. [**分析**] をクリックします。

ケースの [**ジョブ**] タブで、分析の進行状況を確認できます。

 分析が完了したら、analytics レポートを表示し、分析の出力に対してレビューセット内でクエリを実行し ([レビューセット内のクエリ](review-set-search.md)を参照)、特定のドキュメントの関連ドキュメントを表示できます (「[レビューセット内のデータ](reviewing-data-in-review-set.md)のレビュー」を参照)。

## <a name="analytics-report"></a>分析レポート

レビューセットの分析レポートを表示するには、次のようにします。

1. レビューセットを開きます。

2. [**レビューセットの管理**] をクリックします。

3. [**レポート**] をクリックします。

レポートには、分析の4つのコンポーネントがあります。

- **内訳**: レビューセットに含まれている電子メールメッセージ、添付ファイル、およびルースドキュメントの数。

- **ドキュメント (添付ファイルを除く)** -ピボットされたルースドキュメントの数、ピボットの一意の重複、または別のドキュメントの正確な複製。

- **電子**メール-inclusives の電子メールメッセージの数、包括的なコピー、包括的な minuses、または上記のいずれも含まれません。

- **添付ファイル**: レビューセット内の別の電子メール添付ファイルの一意または重複した電子メール添付ファイルの数。