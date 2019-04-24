---
title: キーワード ディクショナリを作成する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/11/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 機密情報を識別する際、特に汎用コンテンツ (医療関連のコミュニケーションなど) や不適切または露骨な言語を識別するのに、キーワードの検索が必要になることがあります。機密情報の種類でもキーワード リストを作成できますが、キーワード リストにはサイズ制限があり、作成や編集のためには XML を変更する必要があります。キーワード ディクショナリでは、よりシンプルかつより大規模にキーワードを管理することができます。ディクショナリあたり最大 100,000 語をサポートします。
ms.openlocfilehash: 142f471d80c7278cabd4c437f0ae0ee9af3ff219
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258165"
---
# <a name="create-a-keyword-dictionary"></a>キーワード ディクショナリを作成する

Office 365 のデータ損失防止 (DLP) は、機密情報を識別、監視、保護することができます。 機密情報を特定するには、特に、一般的なコンテンツ (医療関連の通信など) や不適切または明示的な言語を特定するときにキーワードの検索が必要になることがあります。 キーワードリストは機密情報の種類に作成できますが、キーワードリストのサイズは制限されており、作成または編集するには XML を変更する必要があります。 キーワード辞書を使用すると、キーワードを簡単に管理でき、より大きなスケールで、1つの辞書に最大10万用語をサポートします。
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>キーワード ディクショナリを作成する基本的な手順

ディクショナリのキーワードを、さまざまなソースから作成することができます。一般的な例として、サービスにインポートされたファイルや PowerShell コマンドレットでインポートされたファイル (.csv または .txt リストなど)、PowerShell コマンドレットで直接入力するリスト、または既存のディクショナリなどがあります。キーワード ディクショナリを作成するときには、次の同じ基本手順に従います。
  
1. **セキュリティ & コンプライアンスセンター** ([https://protection.office.com](https://protection.office.com)) を使用するか、 **Office 365 セキュリティ&amp;コンプライアンスセンターの PowerShell**に接続します。
    
2. **目的のソースからキーワードを定義または読み込み**ます。 ウィザードとコマンドレットはどちらも、ユーザー設定のキーワード辞書を作成するためのキーワードのコンマ区切りのリストを受け入れます。この手順は、キーワードの取得元に応じて若干異なります。 いったん読み込まれたキーワードは、インポートされる前にエンコードされてバイト配列に変換されます。
    
3. **辞書を作成**します。 名前と説明を選択し、辞書を作成します。

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターを使用してキーワードディクショナリを作成する

ユーザー辞書のキーワードを作成してインポートするには、次の手順を実行します。

1. セキュリティ & コンプライアンスセンター ([https://protection.office.com](https://protection.office.com)) に接続します。

2. **[分類] > [機密情報の種類]** の順に移動します。

3. **[作成]** を選択し、機密情報の**名前**と**説明**を入力してから、**[次へ]** を選択します。

4. **[要素を追加する]** を選択し、**[次を含むコンテンツを検出する]** ドロップダウン リストの中から **[辞書 (大規模なキーワード)]** を選択します。

5. **[辞書を追加する]** を選択します。

6. 検索コントロールで、**[ここで新しいキーワード ディクショナリを作成する]** を選択します。

7. ユーザー辞書の**名前**を入力します。

8. **[インポート]** を選択し、キーワード ファイルの種類に応じて **[テキストから]** か **[csv から]** のいずれかを選択します。

9. ファイル ダイアログで、ローカル PC またはネットワーク ファイル共有からキーワード ファイルを選択し、**[開く]** を選択します。

10. **[保存]** を選択し、**[キーワード ディクショナリ]** リストから該当するユーザー辞書を選択します。

11. **[追加]** を選択し、**[次へ]** を選択します。

12. 機密情報の種類の選択を最終的に確認し、**[終了]** を選択します。
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>PowerShell を使用してファイルからキーワード ディクショナリを作成する

多くの場合、大きい辞書を作成する必要がある場合は、ファイルまたは他のソースからエクスポートされたリストのキーワードを使用することをお勧めします。 この例では、外部電子メールで画面に表示するのに適していない言語のリストを含むキーワードディクショナリを作成します。 最初[に Office 365 セキュリティ&amp;コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)する必要があります。
  
1. キーワードをテキスト ファイルにコピーし、各キーワードが別個の行にあるかどうかを確認します。
    
2. テキスト ファイルを、Unicode エンコードで、メモ帳 \> **名前を付けて保存** \> **エンコード** \> **Unicode** に保存します。
    
3. このコマンドレットを実行して、ファイルを変数として読み取ります。
    
    ```
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. このコマンドレットを実行して、ディクショナリを作成します。
    
    ```
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a>既存のキーワード ディクショナリを変更する

キーワード ディクショナリのいずれかでキーワードを変更したり、組み込みのディクショナリのいずれかを変更したりする必要が生じることがあります。 現在のところ、PowerShell を使用してのみ、カスタム キーワード ディクショナリを更新できます。 

たとえば、いくつかの用語を PowerShell で変更し、それらをエディターで変更できるようにローカルに保存してから、以前の用語をインプレースで更新します。 

最初に、ディクショナリ オブジェクトを取得します。
  
```
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

印刷`$dict`にはさまざまな変数が表示されます。 キーワード自体はバックエンドのオブジェクトに格納されますが`$dict.KeywordDictionary` 、辞書を変更するために使用する文字列表現が含まれています。 

辞書を変更する前に、 `.split(',')`メソッドを使用して用語の文字列を配列に戻す必要があります。 その後、 `.trim()`メソッドを使用してキーワード間の不要なスペースをクリーンアップし、操作するキーワードだけを残します。 
  
```
$terms = $dict.KeywordDictionary.split(',').trim()
```

ここでは、ディクショナリから一部の用語を削除します。例のディクショナリには少しのキーワードしかないので、ディクショナリのエクスポートとノートパッドでの編集に簡単にスキップすることができますが、通常、ディクショナリには大量のテキストが含まれているので PowerShell で簡単に編集を行うこの方法をまず確認しておいてください。
  
最後の手順で、キーワードを配列に保存しました。[配列から項目を削除する](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))にはいくつか方法がありますが、簡単なのは、ディクショナリから削除する用語の配列を作成して、削除する用語のリストには含まれないディクショナリの用語だけをそこにコピーする方法です。
  
コマンド `$terms` を実行して、現在の用語のリストを表示します。コマンドの出力は次のようになります。 
  
```
aarskog's syndrome
abandonment
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipoproteinemia
abiotrophy
ablatio
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

このコマンドを実行して、削除する用語を指定します。
  
```
$termsToRemove = @('abandonment', 'ablatio')
```

リストから用語を実際に削除するには、このコマンドを実行します。
  
```
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

コマンド `$updatedTerms` を実行して、更新された用語のリストを表示します。コマンドの出力は次のようになります (指定した用語は削除されています)。 
  
```
aarskog's syndrome
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipo proteinemia
abiotrophy
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

ここでは、ディクショナリをローカルに保存して、用語をいくつか追加します。PowerShell で直接用語を追加できますが、確実に Unicode エンコードで保存し BOM が含まれるようにするために、ファイルをローカルでエクスポートする必要があります。
  
次のように実行してディクショナリをローカルに保存します。
  
```
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

次にファイルを開いて、補足する用語を追加し、Unicode エンコード (UTF-16) で保存します。それから更新した用語をアップロードして、ディクショナリを所定の場所で更新します。
  
```
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

これでディクショナリが、所定の場所で更新されました。`Identity` フィールドは、ディクショナリの名前になります。`set-` コマンドレットを使ってディクショナリの名前を変更したい場合は、`-Name` パラメーターを新しいディクショナリの名前と合わせて上記に追加します。 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>カスタムの機密情報の種類と DLP ポリシーでキーワード ディクショナリを使う

キーワード辞書は、カスタムの機密情報の種類の一致要件の一部として、または機密情報の種類自体として使用できます。 どちらの場合も、[カスタムの機密情報の種類](create-a-custom-sensitive-information-type-in-scc-powershell.md)を作成する必要があります。 リンクされた記事の手順に従って、機密情報の種類を作成します。 XML を取得したら、それを使用するには、ディクショナリの GUID 識別子が必要になります。
  
```
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

ディクショナリの ID を取得するには、このコマンドを実行して **ID** のプロパティ値をコピーします。 
  
```
Get-DlpKeywordDictionary -Name "Diseases"
```

コマンドの出力は次のようになります。
  
```
RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255
Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f
Name              : Diseases
Description       : Names of diseases and injuries from ICD-10-CM lexicon
KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo
                    proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,
                    abrami's disease, abramo
IsValid           : True
ObjectState       : Unchanged
```

カスタムの機密情報の種類の XML に ID を貼り付けて、アップロードします。これで、ディクショナリは機密情報の種類のリストに表示され、それをポリシーで使用して、一致するキーワードがいくつ必要かを指定することができます。
  
```
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```


