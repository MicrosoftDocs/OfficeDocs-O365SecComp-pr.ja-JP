---
title: Office 365 で分析の [テキストを無視] オプションを設定する Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: 'Office 365 の Advanced eDiscovery で Analyze および Process モジュールを使用するときに、特定のテキストを無視するルールを定義する方法について説明します。  '
ms.openlocfilehash: 70d9879f1cb6b3def06ff978fc2f7fa8f20a92f0
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156679"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a>Office 365 で分析の [テキストを無視] オプションを設定する Advanced eDiscovery

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
[テキストを無視] 機能は、次の高度な電子情報開示モジュールのすべてまたはいずれかに適用できます: Analyze (重複、電子メールスレッド、テーマ) および関連性。 無視されたテキストは、関連性に表示されているファイルには表示されず、解析/計算では無視されたテキストが破棄されます。
  
既に実行しているモジュールに対して、[テキストを無視] 機能が以前に定義されていた場合は、[無視] テキスト設定が変更されないようになります。 ただし、関連性モジュールの [テキストを無視] 機能は、いつでも変更できます。
  
## <a name="how-ignore-text-filters-are-applied"></a>テキストフィルターの適用方法

複数の Ignore テキストフィルターは、入力された順序で適用されます。 適用される順序を変更するには、それらを削除して、必要な順序で再入力する必要があります。
  
たとえば、テキストコンテンツが "DAVE BOB ALICE CAROL イブ" の場合、次に示すのは、無視するテキストエントリと結果の例です。
  
||||
|:-----|:-----|:-----|
|**テキストの入力を無視する** <br/> |**==\>** <br/> |**結果** <br/> |
|"ALICE"、"BOB CAROL"  <br/> |==\>  <br/> |"DAVE イブ"  <br/> |
|"ALICE"、"BOB ALICE CAROL"  <br/> |==\>  <br/> |"DAVE BOB CAROL イブ"  <br/> |
   
最初の無視テキストが適用された後に、文字列が見つからないため、2番目の無視テキストエントリは実装されません。
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a>無視するテキストを定義するときに正規表現を使用する

無視テキストを定義するときは、正規表現がサポートされています。 正規表現の構文と使用法の例を次に示します。
  
- 行頭から行末までテキストを削除 (無視) するには、次のようにします。
    
     `Begin(.*)$`
    
    ここで、"Begin" は行でこの文字列を最初に出現した位置です。
    
    たとえば、次のようなテキストを入力します。
    
    **"これは最初の文と最初の行です。**
    
    **これは2番目の文と2行目です。**
    
    正規表現の最初 (.\*)$ は次のようになります。
    
    **"これは**
    
    **これは2番目の文と2行目です。**
    
- 電子メールスレッドの最後に自動的に挿入される免責事項と法的なステートメントを削除するには、次のようにします。
    
     `Begin(.|\s)*End`
    
    "Begin" と "End" は、折り返したテキストの段落の先頭と末尾にある一意の文字列です。 
    
    たとえば、次の正規表現は、電子メールスレッドの Begin および End 文字列間の免責事項および法的なステートメントを削除します。
    
    **このメッセージには機密情報が含まれています (. |\s)\*確認が必要な場合は、ハードコピーバージョンを要求してください。**
    
- 免責事項 (特殊文字を含む) を削除するには、次のようにします。 
    
    たとえば、次のようなテキストが含まれているとします (この免責事項は x で表されています)。 
    
    **/\*\ このメッセージには機密情報が含まれています。xxxx xxxx**
    
    **xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxxx**
    
    **xxxx xxxx 確認が必要な場合は、ハードコピーバージョンを要求してください。/\*\**
    
    上記の免責事項を削除する正規表現は、次のようになります。 
    
    **\/\\*\\このメッセージには機密\.情報が含まれています (. |\s)\*確認が必要な場合は、ハードコピーバージョン\.を要求してください。\/\\*\\**
    
- 正規表現ルール:
    
  - アルファベットの一部ではない文字 (スペースを除く)、"_"、および "-" は "" の前にする\"必要があります。
    
  - 通常の eExpression フィールドの長さに制限はありません。
    
> [!TIP]
> 正規表現の説明と詳細な構文については、「[正規表現言語-クイックリファレンス](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx)」を参照してください。 
  
## <a name="define-ignore-text-rule"></a>無視するテキストルールを定義する

1. [ ** \>分析分析\>オプションの管理**] タブの [**無視するテキスト**] セクションで**+** 、アイコンをクリックしてルールを追加します。 
    
2. [**無視するテキストを追加**] ダイアログの [**名前**] フィールドに、ignore テキストルールの名前を入力します。 
    
    ![無視されたテキストの追加](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. **テキスト**ボックスに、無視するテキストを入力します。 Text フィールドに使用できる文字数に制限はありません。 
    
    > [!TIP]
    > 上記のウィンドウに表示されているように、[**電球**] をクリックすると、Ignore テキストルールの一般的な構文のガイドラインが表示されます。 
  
4. 必要に応じて、[**大文字小文字を区別**する] チェックボックスをオンにします。 
    
5. [**適用先**] ボックスの一覧で、定義を適用するアドバンスド電子情報開示モジュールを選択します。 
    
6. サンプルテキストに対してテストを実行する場合は、**入力**テキストボックスに「sample text」と入力し、[**テスト**] をクリックします。 結果が [**出力**] テキストボックスに表示されます。 
    
7. [ **OK]** をクリックして、Ignore テキストルールを保存します。 定義済みの Ignore テキストルールが表示されます。 
    
    ![無視されたテキスト名を設定する](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[ドキュメントの類似点について](understand-document-similarity-in-advanced-ediscovery.md)
  
[分析オプションの設定](set-analyze-options-in-advanced-ediscovery.md)
  
[[詳細設定の分析] の設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[分析結果の表示](view-analyze-results-in-advanced-ediscovery.md)

