---
title: セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: セキュリティ/コンプライアンス センターのグラフィカル ユーザー インターフェイスで DLP のカスタム機密情報の種類を作成、変更、削除、およびテストする方法について説明します。
ms.openlocfilehash: 55e54bf8b49ec21bb5ed4f161efc4e5924ee52fb
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077743"
---
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する

## <a name="summary"></a>概要

セキュリティ/コンプライアンス センターで[カスタムの機密情報の種類](custom-sensitive-info-types.md)を作成するために、この記事をお読みください(「[https://protection.office.com](https://protection.office.com)」)。 この方法を使用して作成されるカスタムの機密情報の種類は、`Microsoft.SCCManaged.CustomRulePack`という名前のルール パッケージに追加されます。

PowerShell および Exact Data Match の機能を使用して、カスタムの機密情報の種類を作成することもできます。 これらの方法の詳細については、次を参照してください。
- [セキュリティ/コンプライアンス センター PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Exact Data Match (EMD) を使用して、DPL 向けのカスタムの機密情報の種類を作成する](create-custom-sensitive-info-type-edm.md)

## <a name="before-you-begin"></a>開始する前に

- 組織には、データ損失防止 (DLP) を含む Office 365 Enterprise などのサブスクリプションが必要です。 [メッセージング ポリシーとコンプライアンス サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)を参照してください。 

- カスタムの機密情報の種類では、正規表現 (RegEx) に精通している必要があります。テキストの処理に使用される Boost.RegEx (旧称 RegEx++) エンジンの詳細については、「[Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)」を参照してください。

  Microsoft カスタマー サービス & サポートは、カスタムのコンテンツ一致定義 (カスタムの分類や正規表現パターンの作成) の提供を支援できません。サポート エンジニアは、機能の制限付きサポート (たとえば、テスト目的でサンプルの正規表現パターンを提供したり、期待どおりにトリガーされない既存の正規表現パターンのトラブルシューティングを支援するなど) は提供できますが、カスタムのコンテンツ一致の開発がユーザーの要件を満たしたり、義務を果たすことを確約できるわけではありません。

- DLP は検索クローラーを使用して、SharePoint Online サイトと OneDrive for Business サイトの機密情報を識別および分類します。既存のコンテンツで新しいカスタムの機密情報の種類を特定するには、コンテンツを再クロールする必要があります。コンテンツはスケジュールに基づいて再クロールされますが、サイト コレクション、リスト、またはライブラリのコンテンツは手動で再クロールできます。詳細については、「[サイト、ライブラリ、またはリストのクロールとインデックス再作成を手動で要求する](https://docs.microsoft.com/sharepoint/crawl-site-content)」を参照してください。

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する

セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して **[作成]** をクリックします。

各設定については説明するまでもありませんが、ウィザードの関連ページには説明が記載されています。

- **[名前]**

- **[説明]**

- **[近接性]**

- **[信頼度]**

- **[プライマリ パターン要素]** (キーワード、正規表現、またはディクショナリ)

- オプションの **[補強パターン要素]** (キーワード、正規表現、またはディクショナリ) および対応する **[最小コスト]** 値。

この例のシナリオ: キーワードの「従業員」、「ID」および「社員証」と共に、コンテンツに含まれる 9 桁の従業員番号を検出するために、カスタムの機密情報の種類が必要になりました。このカスタムの機密情報の種類を作成するには、次の手順を実行します。

1. セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して **[作成]** をクリックします。

    ![機密情報の種類と [作成] ボタンの場所](media/scc-cust-sens-info-type-new.png)

2. **[名前と説明の選択]** ページが開いたら、次の値を入力します。

  - **[名前]**: 従業員 ID。

  - **[説明]**: 9 桁の Contoso 従業員 ID 番号を検出します。

    ![名前と説明のページ](media/scc-cust-sens-info-type-new-name-desc.png)

    完了したら、**[次へ]** をクリックします。

3. **[一致の要件]** ページが開いたら、**[要素の追加]** をクリックして、次の設定を構成します。

    - **次を含むコンテンツを検出する**:
 
      a. **[これらのいずれか]** をクリックして、**[正規表現]** を選択します。

      b. 正規表現ボックスに、`(\s)(\d{9})(\s)` (空白文字で囲まれた 9 桁の数字) を入力します。
  
    - **[補強要素]**: **[補強要素の追加]** をクリックして、**[このキーワード リストを含める]** を選択します。

    - **[このキーワード リストを含める]** 領域が表示されたら、次の設定を構成します。

      - **[キーワード リスト]**: 次の値を入力します: 従業員、ID、社員証。

      - **[最低数]**: 既定値 1 のままにします。

    - 既定の **[信頼度]** 値 60 のままにします。 

    - 既定の **[文字の近接]** 値 300 のままにします。

    ![[一致の要件] ページ](media/scc-cust-sens-info-type-new-reqs.png)

    完了したら、**[次へ]** をクリックします。

4. **[確認と最終処理]** ページが開いたら、設定を確認して **[完了]** をクリックします。

    ![[確認と最終処理] ページ](media/scc-cust-sens-info-type-new-review.png)

5. 次のページでは、[**はい**] をクリックして新しいカスタムの機密情報の種類をテストするように促されます。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする](#test-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。ルールのテストを後で行うには、[**いいえ**] をクリックします。

    ![推奨をテストするページ](media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

新しい機密情報の種類が正常に作成されたことを確認するには、次に示す手順のいずれかを実行します。

  - **[分類]** \> **[機密情報の種類]** に移動して、新しいカスタムの機密情報の種類が一覧に表示されていることを確認します。

  - 新しいカスタムの機密情報の種類をテストします。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする](#test-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を変更する

**注**:

- カスタムの機密情報の種類のみを変更できます。組み込みの機密情報の種類は変更できません。ただし、PowerShell を使用して組み込みの機密情報の種類をエクスポートし、エクスポートしたものをカスタムの機密情報の種類としてインポートすることができます。詳細については、「[組み込みの機密情報の種類をカスタマイズする](customize-a-built-in-sensitive-information-type.md)」を参照してください。

- 変更できるのは、UI で作成したカスタムの機密情報の種類のみです。カスタムの機密情報の種類のルール パッケージをインポートするのに [PowerShell プロシージャ](create-a-custom-sensitive-information-type-in-scc-powershell.md)を使用した場合、エラーが表示されます。

セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して、変更するカスタムの機密情報の種類を選択し、[**編集**] をクリックします。

  ![機密情報の種類と [編集] ボタンの場所](media/scc-cust-sens-info-type-edit.png)

ここでは、セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成したときと同じオプションを選択できます。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する](#create-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

機密情報の種類が正常に変更されたことを確認するには、次に示す手順のいずれかを実行します。

  - **[分類]** \> **[機密情報の種類]** に移動して、変更したカスタムの機密情報の種類のプロパティを確認します。 

  - 変更したカスタムの機密情報の種類をテストします。詳細については、「[セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする](#test-custom-sensitive-information-types-in-the-security--compliance-center)」を参照してください。

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を削除する 

**注**:

- カスタムの機密情報の種類のみを削除できます。組み込みの機密情報の種類は削除できません。

- カスタムの機密情報の種類を削除する前に、その機密情報の種類を参照している DLP ポリシーまたは Exchange メール フロー ルール (別名: トランスポート ルール) がないことを確認してください。

1. セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して、削除するカスタムの機密情報の種類を 1 つ以上選択します。

2. ポップアップが開いたら、**[削除]** (複数選択した場合は **[機密情報の種類の削除]**) をクリックします。

    ![機密情報の種類と [削除] ボタンの場所](media/scc-cust-sens-info-type-delete.png)

3. 警告メッセージが表示されたら、**[はい]** をクリックします。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

カスタムの機密情報の種類が正常に削除されたことを確認するには、**[分類]** \> **[機密情報の種類]** に移動して、そのカスタムの機密情報の種類が一覧に表示されていないことを確認します。

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする

1. セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動します。

2. テストするカスタムの機密情報の種類を 1 つ以上選択します。ポップアップが開いたら、**[種類のテスト]** (複数選択した場合は **[機密情報の種類のテスト]**) をクリックします。

    ![機密情報の種類と [種類のテスト] ボタンの場所](media/scc-cust-sens-info-type-test.png)

3. [**テストの対象ファイルのアップロード**] ページが開いたら、ファイルをドラッグ アンド ドロップするか、または [**参照**] をクリックしてファイルを選択し、テストの対象ドキュメントをアップロードします。

    ![[テストの対象ファイルのアップロード] ページ](media/scc-cust-sens-info-type-test-upload.png)

4. **[テスト]** ボタンをクリックして、ファイル内のパターン マッチについてドキュメントをテストします。

5. [**照合結果**] ページで、[**完了**] をクリックします。

    ![照合結果](media/scc-cust-sens-info-type-test-results.png)