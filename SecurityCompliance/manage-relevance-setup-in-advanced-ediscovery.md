---
title: Office 365 Advanced eDiscovery で関連度の設定を管理する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
description: ファイルをそれぞれの関連度でスコアリングして分析結果を生成するには、Office 365 Advanced eDiscovery で関連度トレーニングを設定するための推奨事項を参照してください。
ms.openlocfilehash: 189c81bd415f94d4ded06fd13eaf5aea861b283d
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "27446348"
---
# <a name="manage-relevance-setup-in-office-365-advanced-ediscovery"></a>Office 365 Advanced eDiscovery で関連度の設定を管理する

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
 Advanced eDiscovery の関連度テクノロジでは、ファイルをそれぞれの関連度でスコアリングするためのエキスパート ガイド型ソフトウェアを使用しています。Advanced eDiscovery の関連度は、早期ケース評価 (ECA)、選別、ファイル サンプル レビューに使用できます。 
  
 Advanced eDiscovery には、ケースに関連するファイルの関連度トレーニングとタグ付けのためのコンポーネントが含まれます。Advanced eDiscovery は、関連ファイルと非関連ファイルのトレーニング サンプルから学習し、各ファイルの関連度スコアを示して、分析結果を生成します。この分析結果は、ファイル レビュー プロセスの最中や後で使用できます。 
  
## <a name="guidelines-for-setting-up-relevance-training"></a>関連度トレーニングを設定するためのガイドライン

 Advanced eDiscovery の **[ケース]** ウィンドウで、ケースを選択し、**[ケースに移動]** をクリックします。**[関連度]** \> **[関連度の設定]** をクリックします。以下の推奨ガイドラインに従って、関連度を設定してください。 
  
- **タグ付け**: 繰り返し行われる関連度トレーニング プロセスの効率は、正確性と一貫性を持ってファイル サンプルにタグ付けするエキスパートの能力に依存します。
    
- **ケースの問題**: 
    
  - 問題ごとに、関連度トレーニング プロセス全体を通して同じエキスパートを使用してください。複数のエキスパートが同じ問題に同時にタグ付けすることはできません。
    
  - ファイルの各グループが特定の問題にのみ関連するかどうかを判断してください。 
    
  - 問題の定義が一般的すぎると、Advanced eDiscovery は実際は関連のないファイルを大量に生成する場合があります。問題の定義が狭すぎると、関連度トレーニング プロセスに時間がかかる場合があります。 
    
  - 関連度トレーニング サイクル中、Advanced eDiscovery は 1 つのアクティブな問題に焦点を合わせ、サンプルの中間結果が適宜表示されます。
    
  - 問題が複数あるシナリオでは、サンプリング モードを使用することで、処理に含める問題を選択できます。「オフ」として定義された問題は、サンプリング モードが変更されるまで扱われません。1 人のエキスパートに対してのみ問題を「アイドル」または「オン」にすることができます。
    
  -  Advanced eDiscovery を使用して、特権ファイル候補を生成できます。特権を目的とした別個の問題を設定します。可能であれば、まず関連度を目的としてトレーニングして選別し、次に、選別したセットのみを対象に特権を目的としてトレーニングします (選別したセットを別個のケースとして再読み込みします)。 
    
  - バッチ計算を行えるのは、開いているサンプルがないときだけです ([バッチ計算] をクリックすると、サンプルを開いているユーザーの一覧が表示されます)。他のユーザーのサンプルを「閉じる」場合 (この操作は他のユーザーがそれらのサンプルにタグ付けしていない場合のみ行う必要があります)、管理者は「すべてのユーザーのサンプル」オプションを指定した「関連度の変更」ユーティリティを使用できます。
    
- **メタデータ**: Advanced eDiscovery はコンテンツに焦点を合わせます。メタデータは関連度抽出条件の一部として考慮されません。 
    
- **リッチ度**: 評価の結果、問題のリッチ度が 3% 未満の場合は、既知の関連ファイルと非関連ファイルで関連度トレーニングをシードすることを検討してください。
    
- **ファイル サイズ**: 大きなファイル (抽出されたテキストが 5,242,880 文字を超えるファイル) は関連度で無視されます。このようなファイルは関連度トレーニング プロセスに参加しないため、バッチ計算後に関連度スコアは表示されません。評価セットには 5 MB を超えるファイルを含めることができます。
    
## <a name="setting-up-case-issues"></a>ケースの問題の設定

このセクションで説明するパラメーターは、Advanced eDiscovery の **[関連度]** \> **[関連度の設定]** で使用できます。 
  
- ファイルをトレーニングするユーザーに問題を割り当てる必要があります。
    
- 次に、インポートしたファイルを、処理中のロードに追加する必要があります。
    
- 慎重に問題を定義して編成してください。関連度トレーニングの結果に影響を及ぼす可能性があるからです。
    
パラメーターの設定後、レビュー担当者/エキスパートは **[関連度]** タブでファイルのトレーニングを開始できます。 
  
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[問題の定義とユーザーの割り当て](define-issues-and-assign-users.md)
  
[インポートしたファイルを追加するためのロードの設定](set-up-loads-to-add-imported-files.md)
  
[強調表示されたキーワードと詳細オプションの定義](define-highlighted-keywords-and-advanced-options.md)

