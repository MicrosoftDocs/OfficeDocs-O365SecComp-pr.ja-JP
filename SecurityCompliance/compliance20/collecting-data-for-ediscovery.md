---
title: 高度な電子情報開示でケースのデータを収集する
ms.author: esclee
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
ms.openlocfilehash: 8e67c3c8a693e627bade9e581f0f1e246bf6802a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151889"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>高度な電子情報開示でケースのデータを収集する

ケースに関係のある保管担当者とデータソースを識別したら、delve のドキュメントセットを特定してください。 上級電子情報開示の検索ツールを使用して、Office 365 の custodial および非 wi-fi ダイヤルの場所からこれらを識別することができます。

検索を実行すると、検索クエリに一致したアイテムが最も多い場所など、取得したアイテムの統計情報を表示できるようになります。 結果のサブセットをプレビューすることもできます。 さらに調べる必要のあるドキュメントセットを特定したら、検索結果をレビューセットに追加して、収集して処理することができます。

## <a name="create-a-search"></a>Create a search

[検索] タブの**** [**新しい検索**] をクリックすると、検索を作成するための手順が示されたウィザードが起動します。 検索を作成する方法の詳細については、「[データを収集するための検索を作成する](create-search-to-collect-data.md)」を参照してください。

検索が作成されると、詳細情報を含むフライアウトページが表示されます。 検索がまだ完了していないため、[**統計**] ボタンと [**プレビュー** ] ボタンは淡色で表示されます。 検索の進行状況を追跡するには、[**検索**] タブを使用します。

## <a name="view-search-results-and-statistics"></a>検索結果と統計情報を表示する
コンテンツ検索には、統計 (見積り) とプレビューという2つのコンポーネントがあります。 これらの各コンポーネントが完了すると、[**検索**] タブの対応する列に状態が [**送信****済み**] から [**進行中**] に変わります。

検索の推定が完了したら、検索をクリックしてフライアウトページを表示します。これにより、検索結果に関する大まかな統計情報が表示されます。 この時点で、[**統計**] ボタンがアクティブになります。 これをクリックすると、次のような検索統計情報を表示できます。

- Summary
- トップの場所
- クエリ

検索統計の詳細については、「[検索統計](search-statistics.md)」を参照してください。

プレビューが完了すると、[**プレビュー** ] ボタンがアクティブになります。 これをクリックして、抽出された結果のサブセットをプレビューします。

## <a name="adding-search-results-to-a-review-set"></a>検索結果をレビューセットに追加する

検索結果全体を収集して処理する準備ができたら、それをレビューセットに追加することで、それを行うことができます。 詳細については、「[レビューセットにデータを追加する](add-data-to-review-set.md)」を参照してください。 