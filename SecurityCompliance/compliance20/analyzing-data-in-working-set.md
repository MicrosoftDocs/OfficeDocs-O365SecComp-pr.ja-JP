---
title: 高度な電子情報開示で作業セット内のデータを分析する (プレビュー)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e3f3e863423fe4312a944eb6f04a58182e11665c
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295480"
---
# <a name="analyze-data-in-a-working-set-in-advanced-ediscovery-preview"></a>高度な電子情報開示で作業セット内のデータを分析する (プレビュー)

収集されたドキュメントの数が多い場合は、それらをすべて確認するのは非常に困難です。Advanced eDiscovery (プレビュー) には、ドキュメントを分析して、情報が失われずにレビューされるドキュメントのボリュームを減らし、一貫性のある方法でドキュメントを整理するのに役立つさまざまなツールが用意されています。これらの機能の詳細については、以下を参照してください。

- [準重複の検出](near-duplicates.md)
- [電子メールのスレッド化](email-threading.md)
- [テーマ](themes.md)

作業セット内のデータを分析するには、次のようにします。

1. ケースの分析設定を構成します。詳細については、「 [Configure search and analytics settings](configure-search-analytics-settings.md)」を参照してください。
2. 分析する作業セットを開きます。
3. [作業セットの管理] に移動します。
4. [分析] をクリックします。

ケースの [ジョブ] タブで、分析の進行状況を確認できます。

 分析が完了すると、分析レポートを表示し、分析の出力に対して作業セット内でクエリを実行できます (詳細については[、「作業セット内のクエリ](working-set-search.md)」を参照してください)。詳細については、「関連ドキュメント」を参照してください[。作業セット内のデータを確認](reviewing-data-in-working-set.md)します)。

## <a name="analytics-report"></a>分析レポート

作業セットの分析レポートを表示するには、次のようにします。

1. ワーキングセットを開きます。
2. [作業セットの管理] に移動します。
3. [レポート] をクリックします。

レポートには、分析の4つのコンポーネントがあります。

- **内訳**: 作業セットに含まれているメール、添付ファイル、および圧縮されていないドキュメントの数。

- **ドキュメント (添付ファイルを除く)** -ピボットされたルースドキュメントの数、ピボットの一意の重複、または別のドキュメントの正確な複製。

- **電子メール**: inclusives、包括的なコピー、包括的に使用、または上記のいずれも含まれないメールの数。

- **添付ファイル**: 作業セット内の別の電子メール添付ファイルの一意の、または重複した電子メール添付ファイルの数。