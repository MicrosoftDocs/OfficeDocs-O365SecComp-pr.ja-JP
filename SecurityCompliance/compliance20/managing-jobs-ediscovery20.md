---
title: Advanced eDiscovery でジョブを管理する (プレビュー)
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
ms.openlocfilehash: 84e2a8dc389d738b8bda1ab21101b2e5e40eee03
ms.sourcegitcommit: cf9d9b545a7c153d314aa9c08c7fb16fcd785b3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "30737647"
---
# <a name="manage-jobs-in-advanced-ediscovery-preview"></a>Advanced eDiscovery でジョブを管理する (プレビュー)

高度な電子情報開示 (プレビュー) のケースの [**ジョブ**] タブで追跡されるジョブの一覧を次に示します。

| ジョブの種類 | 説明 | このジョブが適用されるワークロード |
| :- | :- | :- |
| 保管担当者データの再インデックス作成 | 保管担当者がケースに追加された場合は、すべてのインデックスアイテムが、高度な電子情報開示のインデックスを使用して再インデックス化されます。詳細については、「 [advanced indexing of 保管担当者 data](indexing-custodian-data.md)」を参照してください。 | 詳細な電子情報開示 |
| 検索結果の見積もり | 検索結果の見積もりは、Exchange、SharePoint、OneDrive for business などのワークロードに対して検索を作成して実行した結果です。  推定値には、検索とサイズによって返されるアイテム数などの統計情報が含まれます。  検索の詳細については、「 [Advanced 電子情報開示のケースのデータを収集する](collecting-data-for-ediscovery.md)」を参照してください。 | 詳細な電子情報開示 |
| 検索プレビューの準備 | 検索プレビュージョブを準備することは、Exchange、SharePoint、OneDrive for business などのワークロードに対して検索を作成して実行することによって行われます。  検索結果のプレビューを使用して、検索の有効性を判断することができます。  検索の詳細については、「 [Advanced 電子情報開示のケースのデータを収集する](collecting-data-for-ediscovery.md)」を参照してください。 | 詳細な電子情報開示 |
| 作業セットへのデータの追加 | 作業セットジョブにデータを追加すると、検索の結果が作業セットに追加されたときに発生します。  作業セットの管理の詳細については、「 [Advanced eDiscovery で作業セットを管理](managing-working-sets.md)する」を参照してください。 | 詳細な電子情報開示 |
| 別の作業セットへのデータの追加 | 他の作業セットジョブへのデータの追加は、ユーザーが1つの作業セットから別の作業セットにデータを追加することを選択したときに作成されます。 | 詳細な電子情報開示 |
| Office 以外の365データを作業セットに追加する | office 以外の365データを作業セットジョブに追加するには、ケースに関連する可能性があるクライアントコンピューターからアップロードされた作業セットへのデータの処理と追加、および office 以外の365データの追加の詳細については、「 [office 以外の365データをに読み込む」を参照してください。作業セット](load-non-office365-data.md)。 | 詳細な電子情報開示 |
| エラー解決の準備 |  | 詳細な電子情報開示 |
| 修復されたデータを作業セットに追加する | 修復済みデータをワーキングセットに追加すると、エラーが発生したファイルが修復され、Office 365 Advanced eDiscovery 作業セットに戻されたときに作成されたジョブを参照します。  エラー修復の詳細については、「[データ処理時のエラー修復](error-remediation.md)」を参照してください。 | 詳細な電子情報開示 |
| 荷重セットの比較 | 荷重セットを比較すると、ユーザーは負荷セットへの負荷の違いを調べることができます。ロードセットの詳細については、「 [Manage load sets](manage-load-sets.md)」を参照してください。 | 詳細な電子情報開示 |
| ドキュメントにタグを付けます。 | 作業セット内の複数のドキュメントにタグ付けを行うと、ドキュメントのタグ付けジョブが発生します。  詳細については、「[作業セット内のドキュメントにタグを設定する](tagging-documents.md)」を参照してください。 | 詳細な電子情報開示 |
| 分析の実行 | analytics ジョブの実行は、ほぼ重複した識別の処理、電子メールスレッドの分析とテーマの分析、分析の詳細については、「 [Advanced eDiscovery の作業セットのデータを分析](analyzing-data-in-working-set.md)する」を参照してください。 | 詳細な電子情報開示 |
| エクスポート用のデータを準備する | エクスポートジョブのデータを準備する作業セットからデータをエクスポートすることにより、エクスポートの詳細については、「 [Advanced eDiscovery でケースデータをエクスポート](exporting-data-ediscover20.md)する」を参照してください。 | 詳細な電子情報開示 |
