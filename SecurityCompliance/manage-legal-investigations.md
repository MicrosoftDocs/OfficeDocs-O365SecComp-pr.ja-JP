---
title: Office 365 で法的調査を管理する
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
description: Office 365 のセキュリティ & コンプライアンスセンターで電子情報開示ケースを使用して、組織の法的調査を管理します。 E5 サブスクリプションを持っている場合は、高度な電子情報開示のテキスト分析、machine learning、および予測コーディング機能を使用して、ケースデータをさらに分析できます。
ms.openlocfilehash: 6f5b7bc7b1c8d672efe60629b1ccf1315c8b74dd
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155729"
---
# <a name="manage-legal-investigations-in-office-365"></a>Office 365 で法的調査を管理する

組織には、組織内の特定の役員または他の従業員に関連する訴訟に対応する理由が多数あります。 これにより、電子メール、ドキュメント、インスタントメッセージの会話、ユーザーが毎日の作業タスクで使用したその他のコンテンツの場所についての詳細な調査をすばやく見つけて保持することができます。 セキュリティ & コンプライアンスセンターの電子情報開示ケースツールを使用すると、このような他の多くの操作を実行できます。
  
[電子情報開示ケースを使用して法的調査を管理する](#manage-legal-investigations-with-ediscovery-cases)
  
[Office 365 の高度な電子情報開示を使用してケースデータを分析する](#analyze-case-data-using-office-365-advanced-ediscovery)
  
**Microsoft が電子情報開示の調査を管理する方法を知りたいですか。** 同じ Office 365 検索ツールと調査ツールを使用して内部電子情報開示ワークフローを管理する方法について説明する[テクニカルホワイトペーパー](https://go.microsoft.com/fwlink/?linkid=852161)をダウンロードすることができます。
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>電子情報開示ケースを使用して法的調査を管理する

電子情報開示ケースを使用すると、組織内で電子情報開示ケースを作成、アクセス、および管理できるユーザーを制御できます。 ケースを使用して、メンバーを追加したり、実行できるアクションの種類を制御したり、法的訴訟に関連するコンテンツの場所を保持したり、コンテンツ検索ツールを使用して、ケースに応答する可能性があるコンテンツを保持している場所を検索したりすることができます。 さらに、外部のレビューアーによる詳細な調査のために、それらの結果をエクスポートしてダウンロードすることもできます。 Office 365 組織に E5 サブスクリプションがある場合は、高度な電子情報開示で分析のための検索結果を準備することもできます。
  
- 組織が行う必要のあるすべての法的調査に対して電子情報開示のケースを作成して使用することによって[、電子情報開示ワークフローを管理](ediscovery-cases.md)する 
    
- [電子情報開示のアクセス許可を割り当て](assign-ediscovery-permissions.md)て、組織内で電子情報開示ケースを作成および管理できるユーザーを制御します。 
    
- [コンプライアンスの境界を設定](set-up-compliance-boundaries.md)して、電子情報開示マネージャーが検索できるユーザーコンテンツの場所を制御する 
    
- 組織内の[コンテンツを検索する](search-for-content.md) 
    
- 詳細な電子情報開示の強力な分析ツール (光学式文字認識、電子メールスレッド、予測コーディングなど) を使用して分析を実行できるように、[上級電子情報開示のケースコンテンツを準備](prepare-search-results-for-advanced-ediscovery.md)します。 
    
### <a name="use-scripts-for-advanced-scenarios"></a>高度なシナリオでスクリプトを使用する

コンテンツ検索シナリオのスクリプトを記載した前のセクションと同様に、電子情報開示ケースの管理に役立つセキュリティ & コンプライアンスセンターの PowerShell スクリプトも作成しました。
  
- 組織内の電子情報開示ケースに関連付けられたすべての保留リストに関する情報を含む[電子情報開示保持レポートを作成し](create-a-report-on-holds-in-ediscovery-cases.md)ます。 
    
- 電子情報開示ホールドにユーザーのリストの[メールボックスと OneDrive の場所を追加](use-a-script-to-add-users-to-a-hold-in-ediscovery.md)する 
  
## <a name="analyze-case-data-using-office-365-advanced-ediscovery"></a>Office 365 の高度な電子情報開示を使用してケースデータを分析する

Office 365 Advanced eDiscovery は、前のセクションで説明したコンテンツ検索および電子情報開示機能に基づいて構築されます。 電子情報開示ケースを作成し、保管担当者の場所を保留にして、ケースに応答する可能性があるデータを収集したら、テキスト分析、machine learning、および高度な予測コーディング機能を使用して、さらにデータを分析することができます。情報. これにより、組織は、多数の電子メールメッセージ、ドキュメント、およびその他の種類のデータを簡単に処理して、特定のケースに関連する可能性が最も高いアイテムを見つけることができます。 また、統合されたケース管理と高度な電子情報開示を使用して、セキュリティ & コンプライアンスセンター内で同じケースをシームレスに管理することができました。
  
> [!NOTE]
> Advanced eDiscovery を使用してユーザーのデータを分析するには、ユーザー (データの保管担当者) に Office365 E5 ライセンスが割り当てられている必要があります。または、Office365 E1 または E3 ライセンスを持つユーザーに Advanced eDiscovery 単体のライセンスを割り当てることもできます。ケースに割り当てられ、Advanced eDiscovery を使用してデータを分析する管理者および法令遵守責任者には E5 ライセンスは不要です。 
  
### <a name="get-started"></a>作業の開始

上級電子情報開示を開始する最も簡単な方法は、「セキュリティ & コンプライアンスセンターでのケースの作成と検索結果の準備」、「Advanced eDiscovery にその結果を読み込む」、および「case データを分析するためのエクスプレス分析を実行する」というものです。外部レビュー用。
  
- 高度な電子情報開示ワークフローの[簡単な概要を取得する](quick-setup-for-advanced-ediscovery.md) 
    
- セキュリティ & コンプライアンスセンターを使用して、ケースの作成、電子情報開示のアクセス許可の割り当て、ケースメンバーの追加を行うことで、高度な電子情報開示の[ユーザーおよびケースをセットアップ](set-up-users-and-cases-in-advanced-ediscovery.md)する 
    
- 高度な電子情報開示のケースへの[検索データの準備と読み込み](prepare-data-for-advanced-ediscovery.md) 
    
- [Office 以外の365データ](import-non-office-365-data-into-advanced-ediscovery.md)をケースに読み込み、高度な電子情報開示で分析する 
    
- [エクスプレス分析を使用](use-express-analysis-in-advanced-ediscovery.md)してデータをケースにすばやく分析し、結果を簡単にエクスポートする 
    
### <a name="analyze-data"></a>データを分析する

高度な電子情報開示のケースに検索データが読み込まれたら、Analyze モジュールを使用して分析を開始します。 分析プロセスの最初の部分では、ファイルを一意のファイルのグループに分類し、重複して、重複しないようにします (ドキュメントの類似性とも呼ばれます)。 その後、データを再度階層的に構造化された電子メールのスレッドとテーマにして、必要に応じて、特定のテキストを分析から除外するように無視するテキストフィルターを設定します。 次に、分析を実行して結果を表示します。
  
- 詳細な電子情報開示でのデータの分析を準備するための[ドキュメントの類似](understand-document-similarity-in-advanced-ediscovery.md)点について 
    
- ほぼ重複、テーマ、および電子メールのスレッド処理の[オプションを設定](set-analyze-options-in-advanced-ediscovery.md)してから、Analyze モジュールを実行します。 
    
- テキストおよびテキスト文字列を分析対象から除外するように、[無視するテキストフィルターを設定](set-ignore-text-in-advanced-ediscovery.md)します。このフィルターでは、関連性分析を実行するときにもテキストは無視されます。 
    
- 分析プロセスの[結果を表示する](view-analyze-results-in-advanced-ediscovery.md) 
    
- 分析プロセスの[詳細設定を構成する](set-analyze-advanced-settings-in-advanced-ediscovery.md) 
    
### <a name="set-up-relevance-training"></a>関連トレーニングの設定

上級電子情報開示の予測コーディング (関連性と呼ばれる) を使用すると、ドキュメントの小さなセットに対して意思決定 (関連性があるかどうかに関する決定) を行うことができます。
  
- 関連性トレーニングのセットアップ、ケースに関連するタグ付けファイル、ケース問題の定義[について説明](manage-relevance-setup-in-advanced-ediscovery.md)します。 
    
- [ケースの問題を定義](define-issues-and-assign-users.md)し、各問題をファイルをトレーニングするユーザーに割り当てる 
    
- インポートされたファイルを、関連性トレーニングに追加する[現在のまたは新しい負荷に追加し](set-up-loads-to-add-imported-files.md)ます。ロードは、ケースに追加され、関連トレーニングに使用されるファイルの新しいバッチです。 
    
- 関連性トレーニングに追加できる[強調表示](define-highlighted-keywords-and-advanced-options.md)されたキーワードを定義します。これにより、ケースに関連するファイルを特定しやすくなります。 
    
### <a name="run-the-relevance-module"></a>関連性モジュールを実行する

トレーニングを設定すると、関連性モジュールを実行して、トレーニングの設定の効果を評価する準備ができました。これにより、追加のトレーニングを実行する必要があるかどうかを判断したり、ファイルへのタグ付けを開始する準備が整っている場合に、この結果が得られます。ケースに関連しています。
  
- サンプルのファイルセットに基づいた評価、タグ付け、追跡、および再トレーニングの関連性プロセスと反復プロセス[について説明](use-relevance-in-advanced-ediscovery.md)します。 
    
- ケースに精通したエキスパートがケースファイルのセットをレビューし、関連性トレーニングの効果を判断する[評価について説明](assessment-in-relevance-in-advanced-ediscovery.md)します。 
    
- [ケースファイルを評価](tagging-and-assessment-in-advanced-ediscovery.md)して、トレーニング設定の有効性 (*豊富*さ) を計算し、該当する場合は関連するファイルにマークを付けます。これにより、現在のトレーニングが十分かどうか、またはトレーニングの設定を調整する必要があるかどうかを判断できます。 
    
- 評価が完了した後に[関連性トレーニングを実行](tagging-and-relevance-training-in-advanced-ediscovery.md)し、そのケースに対して定義した問題に関連するファイルまたは関連していないファイルに再度タグ付けする 
    
- 関連性[の分析プロセスを追跡して、](track-relevance-analysis-in-advanced-ediscovery.md)関連性トレーニングが評価目標を達成したか (安定した*トレーニング状態*)、さらにトレーニングが必要かどうかを判断します。各ケースの問題に関する関連性の結果を表示することもできます。 
    
- レビュー用にエクスポートできるケースファイルの結果セットのサイズを決定するために、[関連性分析に基づいて決定を行い](decision-based-on-the-results-in-advanced-ediscovery.md)ます。 
    
- 関連性[分析の品質をテスト](test-relevance-analysis-in-advanced-ediscovery.md)して、関連性プロセス中に行われたカリングの決定を検証する 
    
### <a name="export-results"></a>結果のエクスポート

Advanced eDiscovery でケースデータを分析する最後の手順は、外部レビューの分析結果をエクスポートすることです。
  
- [ケースデータのエクスポートについて](export-case-data-in-advanced-ediscovery.md)
    
- [ケース データをエクスポートする](export-results-in-advanced-ediscovery.md)
    
- [バッチ履歴を表示し、過去の結果をエクスポートする](view-batch-history-and-export-past-results.md)
    
- [レポート フィールドのエクスポート](export-report-fields-in-advanced-ediscovery.md)
    
### <a name="other-advanced-ediscovery-tools"></a>その他の高度な電子情報開示ツール

Advanced eDiscovery は、ケースデータの分析、関連性分析、データのエクスポート以外に、追加のツールと機能を提供します。
  
- [高度な電子情報開示レポートを実行する](run-reports-in-advanced-ediscovery.md)
    
- [ケースとテナントの設定を定義する](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [高度な電子情報開示ユーティリティ](use-advanced-ediscovery-utilities.md)
