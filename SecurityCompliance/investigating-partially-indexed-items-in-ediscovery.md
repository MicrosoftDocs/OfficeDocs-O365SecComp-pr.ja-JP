---
title: Office 365 の電子情報開示で部分的にインデックスが作成されたアイテムを調査する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: 部分的にインデックスが作成されたアイテム (インデックスのないアイテムも呼び出します) は、何らかの理由でコンテンツ検索のインデックスが完全に作成されなかった SharePoint および OneDrive サイト上の Exchange メールボックスアイテムとドキュメントです。 この記事では、検索用にインデックスを作成できず、部分的にインデックスが作成されたアイテムとして返され、部分的にインデックス付けされたアイテムの検索エラーを特定し、PowerShell スクリプトを使用して、部分的にインデックス付けされた電子メールに対する組織の公開を判断する方法について説明します。アイテム.
ms.openlocfilehash: d6b1326498780a5d40e49ff22aa1ac7d16bee8e4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254136"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a>Office 365 の電子情報開示で部分的にインデックスが作成されたアイテムを調査する

セキュリティ & コンプライアンスセンターから実行するコンテンツ検索では、検索を実行すると、予想される検索結果に、部分的にインデックスが作成されたアイテムが自動的に含まれます。 部分的にインデックスが作成されたアイテムは、何らかの理由で検索用に完全にインデックス付けされていなかった SharePoint および OneDrive for business サイトの Exchange メールボックスアイテムとドキュメントです。 ほとんどの電子メールメッセージとサイトドキュメントは、[電子メールメッセージのインデックス付けの制限](limits-for-content-search.md#indexing-limits-for-email-messages)の範囲内にあるため、正常にインデックス付けされます。 ただし、アイテムによっては、これらのインデックスの制限を超えている場合があり、部分的にインデックスが作成されます。 コンテンツ検索を実行するときに、アイテムが検索用にインデックス付けされず、部分的にインデックスが付けられたアイテムとして返されるその他の理由は次のとおりです。
  
- 電子メールメッセージには、インデックスを作成できないファイルの種類の添付ファイルがあります。ほとんどの場合、ファイルの種類が認識されない[か、インデックス処理がサポート](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)されていません。
    
- 電子メールメッセージには、有効なハンドラー (画像ファイルなど) のない添付ファイルがあります。これは、部分的にインデックスが作成された電子メールアイテムの最も一般的な原因です。
    
- 電子メールメッセージに添付されたファイルが多すぎます
    
- 電子メールメッセージに添付されたファイルが大きすぎます
    
- このファイルの種類はインデックス作成に対してサポートされていますが、特定のファイルに対してインデックス作成エラーが発生しました
    
ほとんどの Office 365 組織のお客様は、ボリュームによってコンテンツの 1% 未満、および部分的なインデックスが作成されたサイズではコンテンツの 12% 未満になっています。 ボリュームとサイズの違いがあるのは、コンテンツを完全にインデックス処理できない可能性が高いファイルの方が大きいためです。
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>検索によって、部分的にインデックス付けされたアイテム数が変化するのはなぜですか?

セキュリティ & コンプライアンスセンターでコンテンツ検索を実行した後、検索された場所に含まれる部分的にインデックスが作成されたアイテムの合計数とサイズが、検索結果の詳細な統計情報に表示されます。 メモこれらは、検索統計ではインデックスのない*アイテム*と呼ばれます。 検索結果で返される、部分的にインデックスが作成されたアイテムの数に影響を与えるいくつかの点を以下に示します。 
  
- アイテムが部分的にインデックス処理され、検索クエリと一致する場合は、検索結果アイテムの数 (およびサイズ) と、部分的にインデックスが作成されたアイテムの両方に含まれます。 ただし、同じ検索結果がエクスポートされると、アイテムは一連の検索結果にのみ含まれます。部分的にインデックスが作成されたアイテムとして含まれていません。
    
- 検索クエリに日付範囲を指定した場合 (キーワードクエリに含めるか、条件を使用して)、その日付範囲に一致しない部分的なインデックスアイテムは、部分的にインデックスが作成されたアイテムのカウントに含まれません。 部分的にインデックスが作成されたアイテムのみが、日付範囲内にある場合、インデックスが作成されたアイテムのカウントに含まれます。
    
 **注:** SharePoint および OneDrive サイトにある、部分的にインデックスが作成されたアイテムは、検索の詳細な統計情報に表示される、部分的にインデックスが作成されたアイテムの推定に含まれて*いません*。 ただし、コンテンツ検索の結果をエクスポートする場合は、部分的にインデックスが作成されたアイテムをエクスポートすることができます。 たとえば、コンテンツ検索でサイトのみを検索した場合は、推定数が部分的にインデックス付けされたアイテムは0になります。 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>組織内の部分的にインデックスが作成されたアイテムの比率を計算する

部分的にインデックスが作成されたアイテムに対する組織の影響を理解するには、すべてのメールボックス内のすべてのコンテンツについて検索を実行します (空白のキーワードクエリを使用)。 次の例では、56208 (4830 MB) の完全にインデックスが作成されたアイテムと、470 (316 mb) の一部のインデックスアイテムがあります。
  
![部分的にインデックスが作成されたアイテムを示す検索統計の例](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
次の計算を使用して、部分的にインデックスが作成されたアイテムのパーセンテージを調べることができます。
  
 **組織内で部分的にインデックスが作成されたアイテムの比率を計算するには、次のようにします。**

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
前の例からの検索結果を使用して、すべてのメールボックスアイテムの 84% が部分的にインデックス処理されます。
  
 **組織内で部分的にインデックス付けされたアイテムのサイズの割合を計算するには、次のようにします。**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

そのため、前の例では、メールボックスアイテムの合計サイズの 6.54% が、部分的にインデックス付けされたアイテムからのものです。 前述したように、ほとんどの Office 365 組織のお客様は、ボリュームによってコンテンツの 1% 未満、および部分的なインデックスが作成されたサイズによるコンテンツの 12% 未満です。

## <a name="working-with-partially-indexed-items"></a>部分的にインデックスが作成されたアイテムを処理する

部分的なアイテムを調べて、関連する情報が含まれていないことを検証する必要がある場合は、部分的にインデックスが作成されたアイテムに関する情報を含む[コンテンツ検索レポートをエクスポート](export-a-content-search-report.md)できます。 コンテンツ検索レポートをエクスポートする場合は、部分的にインデックスが作成されたアイテムを含むエクスポートオプションのいずれかを選択するようにしてください。 
  
![2番目または3番目のオプションを選択して、部分的にインデックス付けされたアイテムをエクスポート](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
これらのオプションのいずれかを使用してコンテンツ検索の結果またはコンテンツ検索レポートをエクスポートすると、エクスポートにインデックスのない Items .csv という名前のレポートが含まれます。 このレポートには、データの大部分の情報が記録されます。ただし、インデックス付きのアイテム .csv ファイルには、部分的にインデックスが作成されたアイテムに関連する**エラータグ**と**エラープロパティ**の2つのフィールドもあります。 これらのフィールドには、インデックスが設定された各アイテムのインデックス作成エラーに関する情報が含まれています。 これら2つのフィールドの情報を使用すると、特定のインデックス作成エラーが調査に影響を与えるかどうかを判断するのに役立ちます。 その場合は、対象コンテンツ検索を実行し、特定の電子メールメッセージと SharePoint または OneDrive ドキュメントを取得およびエクスポートして、調査に関連しているかどうかを確認できるようにします。 詳細な手順については、「 [Office 365 で対象コンテンツ検索の CSV ファイルを準備](csv-file-for-an-id-list-content-search.md)する」を参照してください。
  
 **注:** インデックスのないアイテム .csv ファイルには、**エラーの種類**と**エラーメッセージ**という名前のフィールドも含まれています。 これらは、**エラータグ**と**エラーのプロパティ**フィールドの情報に似た情報を含む従来のフィールドですが、詳細な情報は含まれていません。 これらの従来のフィールドは無視しても問題ありません。 
  
## <a name="errors-related-to-partially-indexed-items"></a>部分的にインデックスが作成されたアイテムに関連するエラー

エラータグは、エラーとファイルの種類の2つの情報で構成されています。 たとえば、このエラー/filetype ペアの場合は、次のようになります。

```
 parseroutputsize_xls
```

   
 `parseroutputsize`は error `xls`で、エラーが発生したファイルの種類です。 ファイルの種類が認識されなかった場合や、ファイルの種類がエラーに該当しない場合は、 `noformat`ファイルの種類の代わりに値が表示されます。 
  
次に、インデックス作成エラーの一覧と、エラーの考えられる原因についての説明を示します。
  
|**エラータグ**|**説明**|
|:-----|:-----|
| `attachmentcount` <br/> |電子メールメッセージの添付ファイルが多すぎたため、これらの添付ファイルの一部は処理されませんでした。  <br/> |
| `attachmentdepth` <br/> |コンテンツ取得とドキュメントパーサーで、他の添付ファイル内にネストされた添付ファイルのレベルが多すぎます。 これらの添付ファイルの一部は処理されませんでした。  <br/> |
| `attachmentrms` <br/> |添付ファイルは RMS で保護されていたため、デコードに失敗しました。  <br/> |
| `attachmentsize` <br/> |電子メールメッセージに添付されたファイルが大きすぎて処理できませんでした。  <br/> |
| `indexingtruncated` <br/> |処理された電子メールメッセージをインデックスに書き込むときに、インデックス可能なプロパティのいずれかが大きすぎたため、切り捨てられました。 切り捨てられたプロパティは、[Error properties] フィールドに表示されます。  <br/> |
| `invalidunicode` <br/> |有効な Unicode として処理できなかったテキストが電子メールメッセージに含まれています。 このアイテムのインデックス処理が完了していない可能性があります。  <br/> |
| `parserencrypted` <br/> |添付ファイルまたは電子メールメッセージの内容は暗号化されており、Office 365 はコンテンツをデコードできませんでした。  <br/> |
| `parsererror` <br/> |解析中に不明なエラーが発生しました。 これは通常、ソフトウェアバグまたはサービスのクラッシュによって生じます。  <br/> |
| `parserinputsize` <br/> |添付ファイルが大きすぎてパーサーで処理できなかったため、添付ファイルの解析が行われなかったか、完了しませんでした。  <br/> |
| `parsermalformed` <br/> |添付ファイルの形式が正しくないため、パーサーで処理できませんでした。 これにより、古いファイル形式、互換性のないソフトウェアによって作成されたファイル、または要求された以外のものを装ったウイルスが発生します。  <br/> |
| `parseroutputsize` <br/> |添付ファイルの解析からの出力が大きすぎたため、切り捨てる必要がありました。  <br/> |
| `parserunknowntype` <br/> |添付ファイルのファイルの種類が Office 365 で検出できませんでした。  <br/> |
| `parserunsupportedtype` <br/> |添付ファイルのファイルの種類が Office 365 によって検出されましたが、そのファイルの種類を解析することはできません。  <br/> |
| `propertytoobig` <br/> |Exchange ストアの電子メールプロパティの値が大きすぎて取得できなかったため、メッセージを処理できませんでした。 これは通常、電子メールメッセージの body プロパティにのみ発生します。  <br/> |
| `retrieverrms` <br/> |コンテンツ取得元は、RMS で保護されたメッセージのデコードに失敗しました。  <br/> |
| `wordbreakertruncated` <br/> |ドキュメントでインデックス処理中に識別された単語の数が多すぎます。 制限値に達したときにプロパティの処理が停止され、プロパティが切り捨てられます。  <br/> |
   
エラーフィールドは、error Tags フィールドにリストされている処理エラーの影響を受けるフィールドを示します。 `subject`や`participants`などのプロパティを検索する場合、メッセージ本文のエラーは検索結果に影響しません。 これは、さらに調査する必要がある、部分的にインデックスが作成されたアイテムを正確に判断する場合に役立ちます。
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>PowerShell スクリプトを使用して、部分的にインデックスが作成された電子メールアイテムに対する組織の公開を決定する

次の手順では、すべての Exchange メールボックス内のすべてのアイテムを検索する PowerShell スクリプトを実行し、組織の部分的にインデックスが作成された電子メールアイテム (カウントとサイズ順) の比率に関するレポートを生成し、アイテムの数を表示する方法を示します (およびそのファイルの種類) は、発生するインデックス作成エラーごとに発生します。 前のセクションのエラータグの説明を使用して、インデックス作成エラーを特定します。
  
1. ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `PartiallyIndexedItems.ps1`のようになります。

```
  write-host "**************************************************"
  write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```
   
2. [Security & コンプライアンスセンター PowerShell に接続](https://go.microsoft.com/fwlink/p/?linkid=627084)します。
    
3. Security & コンプライアンスセンター PowerShell で、手順1でスクリプトを保存したフォルダーに移動し、スクリプトを実行します。例えば：

    ```
    .\PartiallyIndexedItems.ps1
    ```
   
このスクリプトによって返される出力の例を次に示します。
  
![部分的にインデックスが作成された電子メールアイテムに対する組織の公開に関するレポートを生成するスクリプトからの出力の例](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
以下の点に注意してください。
  
1. 電子メールアイテムの合計数とサイズ、および部分的にインデックスが作成された電子メールアイテムの組織の比率 (カウントとサイズ順)
    
2. エラーが発生したエラータグと対応するファイルの種類を一覧表示します。
  
## <a name="see-also"></a>関連項目

[Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム](partially-indexed-items-in-content-search.md)
