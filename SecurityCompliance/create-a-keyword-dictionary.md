---
title: キーワード ディクショナリを作成する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: c8a95d1b-c3b6-4613-98ab-0331d1872cf3
description: 機密情報を識別する際、特に汎用コンテンツ (医療関連のコミュニケーションなど) や不適切または露骨な言語を識別するのに、キーワードの検索が必要になることがあります。機密情報の種類でもキーワード リストを作成できますが、キーワード リストにはサイズ制限があり、作成や編集のためには XML を変更する必要があります。キーワード ディクショナリでは、よりシンプルかつより大規模にキーワードを管理することができます。ディクショナリあたり最大 100,000 語をサポートします。
ms.openlocfilehash: 5dd0459c801b433b8f0a477aeb2ab4192236bd28
ms.sourcegitcommit: 4be502d1fc6cbaef4c72d599758d51efe3a173c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "23849400"
---
# <a name="create-a-keyword-dictionary"></a>キーワード ディクショナリを作成する

Office 365 のデータ損失防止 (DLP) では、ユーザーの機密情報を識別し、監視し、保護します。機密情報を識別する際、特に汎用コンテンツ (医療関連のコミュニケーションなど) や不適切または露骨な言語を識別するのに、キーワードの検索が必要になることがあります。機密情報の種類でもキーワード リストを作成できますが、キーワード リストにはサイズ制限があり、作成や編集のためには XML を変更する必要があります。キーワード ディクショナリでは、よりシンプルかつより大規模にキーワードを管理することができます。ディクショナリあたり最大 100,000 語をサポートします。
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>キーワード ディクショナリを作成する基本的な手順

ディクショナリのキーワードは、最も一般的なものではファイル (.csv や .txt リストなど) から、コマンドレットに直接入力したリストから、または既存のディクショナリからなど、さまざまなソースからのものがあります。キーワード ディクショナリを作成するときは、同じ基本手順を実行します。
  
1. **セキュリティ &amp; コンプライアンス センター PowerShell に接続する** - [次のトピック](https://docs.microsoft.com/ja-JP/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)を参照してください。
    
2. **対象となるソースからキーワードを定義する、または読み込む** - キーワード ディクショナリを作成するコマンドレットは、コンマ区切りのキーワード リストを指定できるので、この手順はキーワードがどこから来ているかによって多少異なります。 
    
3. **キーワードをエンコードする** - 読み込まれると、インポートする前にバイト配列に変換されます。 
    
4. **ディクショナリを作成する** - 名前と説明を選択し、ディクショナリを作成します。 
    
## <a name="create-a-keyword-dictionary-from-a-file"></a>ファイルからキーワード ディクショナリを作成する

大きなディクショナリを作成する必要がある場合はたいてい、ファイルからのキーワードや、その他のソースからエクスポートしたリストを使うことになります。その場合、外部電子メールでスクリーニングを行うための不適切な言葉のリストを含むキーワード ディクショナリを作成します。まず[Office 365 セキュリティ/ コンプライアンス センターの PowerShell に接続する](https://docs.microsoft.com/ja-JP/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)必要があります。
  
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

いずれかのキーワード ディクショナリでキーワードの変更や、組み込みのディクショナリの変更が必要になる場合があります。この例では、PowerShell で一部の用語を変更し、ローカルの場所に保存します。用語はエディターで変更した場所に保存し、以前の用語を更新します。まず、ディクショナリ オブジェクトを取得します。
  
```
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

`$dict` を印刷すると、さまざまな変数が確認できます。キーワード自体は、バックエンド上のオブジェクトに保存されますが、`$dict.KeywordDictionary` にはキーワードの文字列表現も含まれているので、これを使ってディクショナリを変更します。ディクショナリを変更する前に、`.split(',')` メソッドを使って、用語の文字列を配列に戻す必要があります。それから、`.trim()` メソッドを使ってキーワード間から不要なスペースを取り除き、作業に使うキーワードだけを残します。 
  
```
$terms = $dict.KeywordDictionary.split(',').trim()
```

ここでは、ディクショナリから一部の用語を削除します。例のディクショナリには少しのキーワードしかないので、ディクショナリのエクスポートとノートパッドでの編集に簡単にスキップすることができますが、通常、ディクショナリには大量のテキストが含まれているので PowerShell で簡単に編集を行うこの方法をまず確認しておいてください。
  
最後の手順で、キーワードを配列に保存しました。[配列から項目を削除する](https://go.microsoft.com/fwlink/p/?linkid=852620)にはいくつか方法がありますが、簡単なのは、ディクショナリから削除する用語の配列を作成して、削除する用語のリストには含まれないディクショナリの用語だけをそこにコピーする方法です。
  
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

キーワード ディクショナリは、カスタムの機密情報の種類の合致要件の一部として、または機密情報の種類そのものとして使用することができます。どちらの場合も、[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)必要があります。リンク先の記事にある手順に従って、機密情報の種類を作成できます。XML ができたら、それを使うためにディクショナリの GUID 識別子が必要になります。
  
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


