---
title: 高度な電子的証拠開示 (プレビュー) での作業セット内のデータを分析します。
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
ms.openlocfilehash: 68a8b7586700a9bffe78f2b3a4ff419a1f85ba8a
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695143"
---
# <a name="analyze-data-in-a-working-set-in-advanced-ediscovery-preview"></a>高度な電子的証拠開示 (プレビュー) での作業セット内のデータを分析します。

収集したドキュメントの数が大きい場合は、それらすべてを確認するのには非常に困難ができます。高度な電子的証拠開示 (プレビュー) には、さまざまな情報を損なうことがなく情報を確認して、一貫した方法でドキュメントを整理するために、ドキュメントの量を減らすためにドキュメントを分析するツールが用意されています。これらの機能に関する詳細についてを参照してください。

- [準重複の検出](near-duplicates.md)
- [電子メールのスレッド化](email-threading.md)
- [テーマ](themes.md)

ワーキング セット内のデータを分析するには。

1. ケースの分析の設定を構成します。詳細については、[検索および分析の設定の構成](configure-search-analytics-settings.md)を参照してください。
2. 分析するワーキング セットを開きます。
3. 管理作業の設定] に移動します。
4. [分析] をクリックします。

場合は、[ジョブ] タブで分析の進行状況を確認できます。

 分析が完了すると、分析レポートを表示することができますが作業中のクエリを実行の詳細については[、作業中のクエリを設定](working-set-search.md)) は、「分析の出力に設定し (詳細についてはを参照してください[の特定のドキュメントに関連するドキュメントを参照してください。ワーキング セット内のデータを確認する](reviewing-data-in-working-set.md))。

## <a name="analytics-report"></a>分析レポート

ワーキング セットの分析レポートを表示します。

1. ワーキング セットを開きます。
2. 管理作業の設定] に移動します。
3. [レポート] をクリックします。

レポートには、分析からの 4 つのコンポーネントがあります。

- **内訳**の数の e メール、添付ファイル、および柔軟なドキュメントは、ワーキング セットに見つかりませんでした。

- **ドキュメント (を添付ファイルを除く)** の緩やかなドキュメントの数が、ピボットの重複または別のドキュメントの完全な複製に近い独自のピボットをしました。

- **メール**・ inclusives、包括的なコピー、包括的な短所は、上記のいずれかに e メールの数がいた。

- **添付ファイル**を電子メールの添付ファイルをどのように多くの固有またはワーキング セット内の別の電子メールの添付ファイルの重複を許可します。