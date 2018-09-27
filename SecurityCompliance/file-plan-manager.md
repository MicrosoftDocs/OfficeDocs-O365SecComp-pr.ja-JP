---
title: ファイル計画マネージャーの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 9/25/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: ファイル計画マネージャーは、アイテム保持ラベルおよびポリシーのための高度な管理機能を提供します。作成に始まり、コラボレーション、レコード宣言、保持、そして廃棄に至るまでのコンテンツのライフ サイクル全体におけるラベルとコンテンツのラベリングを網羅する統合的な機能を提供します。
ms.openlocfilehash: 4feacf20444591f6da2d55a928a81e86b56c5d9a
ms.sourcegitcommit: 9f34ace6bbe3d5e07e24ebaae96613750869cddf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25019278"
---
# <a name="overview-of-file-plan-manager"></a>ファイル計画マネージャーの概要

ファイル計画マネージャーは、アイテム保持ラベルおよびポリシーのための高度な管理機能を提供します。作成に始まり、コラボレーション、レコード宣言、保持、そして廃棄に至るまでのコンテンツのライフ サイクル全体におけるラベルとコンテンツのラベリングを網羅する統合的な機能を提供します。

![[ファイル計画] ページ](media/file-plan-page.png)

## <a name="important-this-feature-is-currently-available-only-as-part-of-the-office-365-preview-program"></a>重要: 現在、この機能は Office 365 Preview プログラムの一部としてのみ提供されています

お客様の組織が Office 365 Preview プログラムに登録されている場合にのみ、テナントでこの機能が表示されます。

## <a name="accessing-file-plan-manager"></a>ファイル計画マネージャーへのアクセス

ファイル計画マネージャーにアクセスするには次の 2 つの要件があります。
- Office 365 Enterprise E5 サブスクリプション。
- 次のいずれかのセキュリティ &amp;コンプライアンス センターの役割がユーザーに割り当てられている状態。 
    - 保持マネージャー
    - 閲覧限定保持マネージャー

## <a name="navigating-your-file-plan"></a>ファイル計画の中の移動

ファイル計画マネージャーでは、すべてのアイテム保持ラベルとポリシーの設定を 1 つのビューから簡単に参照できます。

ファイル計画の外で作成されたアイテム保持ラベルはファイル計画上で利用可能で、また、その逆も同様であることに注意します。

[**ファイル計画ラベル**] タブで、次の追加の情報と機能が提供されます。

### <a name="label-settings-columns"></a>ラベル設定列
 
- [**分類方法**] は保持期間を起動するトリガーの種類を識別します。有効な値は次のとおりです。 
    - イベント
    - 作成日時
    - 更新日時
    - ラベルが付けられた日時
- **レコード** は、ラベルが適用されときにアイテムが宣言されたレコードが宣言されたレコードになるかどうかを識別します。有効な値は次のとおりです。
    - いいえ
    - はい
    - はい (法的)
- [**保持**] は保持の種類を識別します。有効な値は次のとおりです。
    - 保持
    - 保持および削除
    - 削除
- [**廃棄**] は保持期間終了時のコンテンツの取り扱い方法を識別します。有効な値は次のとおりです。 
    - null
    - アクションなし
    - 自動削除
    - 要確認 (廃棄レビューも呼ばれる)

![ファイル計画でのラベル設定](media/file-plan-label-columns.png)

### <a name="label-file-plan-descriptors-columns"></a>ファイル計画記述子列にラベルを付ける

より多くの情報をアイテム保持ラベルの構成に含めることができます。ファイル計画記述子をラベルに挿入することにより、ファイル計画の管理性が向上し整理がしやすくなります。

すぐに利用開始できるように、ファイル計画マネージャーでは次の既定値が提供されています: 役割/部門、カテゴリ、権限の種類、および規定/是正勧告。アイテム保持ラベルを作成または編集するときに、ファイル計画記述子の値を新たに追加することができます。

アイテム保持ラベルを作成または編集時のファイル計画記述子に関するステップの画面です。

![ファイル計画記述子](media/file-plan-descriptors.png)

ファイル計画マネージャーの [ラベル] タブのファイル計画記述子列の画面です。

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-labels-out-of-your-file-plan"></a>ファイル計画からラベルをエクスポートする

組織内のデータ ガバナンス関係者との定期的なコンプライアンス レビューが円滑に行えるように、ファイル計画マネージャーではすべてのアイテム保持ラベルの詳細を .csv ファイルにエクスポートできます。

すべてのアイテム保持ラベルをエクスポートするには、[**ファイル計画マネージャー**] \> [**ファイル計画アクション**] \> [**ラベルのエクスポート**] の順に移動します。

![ファイル計画をエクスポートするオプション](media/file-plan-export-labels-option.png)

既存のすべてのアイテム保持ラベルを含む *.csv ファイルが開きます。

![すべてのアイテム保持ラベルが表示されたCSV ファイル](media/file-plan-csv-file.png)

## <a name="import-labels-into-your-file-plan"></a>ファイル計画にラベルをインポートする

ファイル計画マネージャーでは新しいラベルの一括インポートおよび既存のアイテム保持ラベルの変更が行えます。

新しいアイテム保持ラベルのインポートおよび既存のアイテム保持ラベルの更新を行うには、[**ファイル計画マネージャー**] \> [**ファイル計画アクション**] \> [**ラベルのインポート**] の順に移動します。

![ファイル計画のインポートのオプション](media/file-plan-import-labels-option.png)

![空白のファイル計画テンプレートをダウンロードするオプション](media/file-plan-blank-template-option.png)

空白のテンプレートをダウンロードします (または現在のファイル計画のエクスポートを使います)。

![Excel で開かれた空白のファイル計画テンプレート](media/file-plan-blank-template.png)

テンプレートに入力します (“準備中”とは、記載事項の有効値についてのリファレンス情報です)。

![情報が入力されたファイル計画テンプレート](media/file-plan-filled-out-template.png)

入力済みのテンプレートをアップロードすると、ファイル計画マネージャーで記載事項が検証され、インポートの統計情報が表示されます。

![ファイル計画のインポートの統計情報](media/file-plan-import-statistics.png)

インポートが完了したらファイル計画マネージャーに戻り、新規または既存のポリシーに新しいラベルを割り当てます。

![ラベルを公開するオプション](media/file-plan-publish-labels-option.png)

