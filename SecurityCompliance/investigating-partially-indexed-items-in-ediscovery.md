---
title: Office 365 の電子情報開示で部分的にインデックスが作成されたアイテムを調査する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: 一部の項目をインデックス (インデックス付けされない呼び出しの項目も) は、Exchange メールボックスのアイテムと SharePoint のドキュメントと OneDrive のサイトが何らかの理由がコンテンツの検索用にインデックス完全にいなかったのです。この記事で項目が検索用インデックスを作成することはできず、部分的にインデックス付きの項目として返される理由を説明、部分的にインデックス付きのアイテムの検索エラーを識別して PowerShell スクリプトを使用して、部分的にインデックス付きの電子メールを組織のリスクを判断するのにはアイテムです。
ms.openlocfilehash: 98f794e80ea8a6016887ff139bc5b546c438f093
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038080"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a>Office 365 の電子情報開示で部分的にインデックスが作成されたアイテムを調査する

Office 365 のセキュリティを実行するコンテンツの検索&amp;コンプライアンス センターが検索を実行すると、予定の検索結果に部分的にインデックス付きのアイテムが自動的に含まれます。部分的にインデックス付きのアイテムは、Exchange メールボックスのアイテムを何らかの理由により検索用インデックスが作成されなかった完全にビジネス サイトの SharePoint と OneDrive のドキュメントです。[電子メール メッセージのインデックス作成の制限](limits-for-content-search.md#indexinglimits)内に収まっているために、ほとんどの電子メール メッセージおよびサイトのドキュメントが正常にインデックスします。ただし、いくつかの項目は、これらのインデックスの制限を超える可能性がありますが部分的にインデックスを作成します。アイテムの検索用インデックスを作成できない理由とは、コンテンツの検索を実行すると、部分的にインデックス付きの項目として返されます、その他の理由を以下に示します。
  
- 電子メール メッセージがある添付ファイルの種類のファイルのインデックスを作成することはできません。ほとんどの場合、ファイルの種類は[認識されない、またはインデックス作成でサポートされていません](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)
    
- イメージ ファイルの有効なハンドラーがない場合、添付ファイルがある電子メール メッセージこれは、部分的にインデックス付きの電子メール アイテムの最も一般的な原因
    
- 電子メール メッセージに添付ファイルが多すぎます
    
- 電子メール メッセージの添付ファイルが大きすぎます
    
- インデックス作成のためにファイルの種類がサポートされていますが、特定のファイルのインデックス作成エラーが発生しました。
    
さまざまですが、部分的にインデックスが設定されたサイズでボリュームと内容の 12% 未満でコンテンツの 1% 未満の場合がある Office 365 の組織のほとんどのお客様です。ボリュームとサイズの違いの理由は、サイズの大きいファイルの完全にインデックスを作成できないコンテンツが含まれている可能性が高くです。
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>部分的にインデックス付きのアイテム数は、検索、なぜ変更しますか。

Office 365 のセキュリティ コンテンツの検索を実行した後&amp;コンプライアンス センターの合計数、検索された場所に部分的にインデックス付きの項目のサイズは、「検索結果統計の詳細な統計情報に表示される検索します。検索の統計情報の*項目のインデックスを持たない*呼ばれますを注意してください。検索結果に返される部分的にインデックス付きのアイテムの数に影響を与えることがいくつかを以下に示します。 
  
- アイテムのインデックスは部分的に、検索クエリに一致する場合、カウント (とサイズ) の検索結果の項目と部分的にインデックス付きの項目に含まれます。ただし、同じ検索結果がエクスポートされると、アイテムが検索結果のセットにのみ付属それが部分的にインデックス付きの項目として含まれていません。
    
- (キーワード クエリでそれを含む) や条件を使用して検索クエリの日付範囲を指定すると、日付の範囲に一致しない一部のインデックス付きの項目が部分的にインデックス付きの項目の数に含まれていません。部分的にインデックス付きの項目の数には、日付の範囲内に含まれる部分的にインデックス付きのアイテムのみが含まれます。
    
 **注:** 部分的にインデックス付きのアイテムを SharePoint に配置し、OneDrive のサイト*は*検索の詳細な統計情報に表示されている部分的にインデックス付きの項目の見積もりに含まれています。ただし、コンテンツの検索結果をエクスポートする場合は、部分的にインデックス付きのアイテムをエクスポートできます。たとえば、のみを検索する場合のサイト コンテンツの検索、推定数に部分的にインデックス付きの項目は 0 にします。 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>組織内で部分的にインデックス付きの項目の比率を計算します。

(クエリを使用して空白のキーワード) 部分的にインデックス付きの項目の組織のリスクを理解するため、すべてのメールボックス内のすべてのコンテンツを検索を実行できます。56,208 (4,830 MB) がある、次の例で完全なアイテム、470 (316 MB) のインデックスを作成インデックス項目の一部です。
  
![部分的にインデックス作成済みアイテムの検索の統計情報の表示の例](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
次の計算を使用して部分的にインデックス付きの項目のパーセンテージを指定できます。
  
 **組織内で部分的にインデックス付きの項目の比率を計算します。**

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
前の例では、検索結果を使用しています。 すべてのメールボックス アイテムの 84% が部分的にインデックス付けします。
  
 **組織内で部分的にインデックス付きのアイテムのサイズの割合を計算します。**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

前の例では、メールボックスのアイテムの合計サイズの 6.54%、部分的にインデックス付きのアイテムです。述べたように、ほとんどの Office 365 組織を部分的にインデックスが設定されたサイズでボリュームと内容の 12% より小さく、コンテンツの 1% 未満の場合があるお客様。

## <a name="working-with-partially-indexed-items"></a>インデックス作成済みアイテムを部分的に使用

場合は部分的に関連情報が含まれているは、[コンテンツの検索レポートをエクスポート](export-a-content-search-report.md)することができますを検証するために項目を確認する必要があるとき部分的にインデックス付きの項目に関する情報を格納します。コンテンツの検索レポートをエクスポートする場合は、部分的にインデックス付きのアイテムを含む、エクスポート オプションのいずれかを選択してください。 
  
![部分的にインデックス付きのアイテムをエクスポートするのには、2 番目または 3 番目のオプションを選択します。](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
コンテンツの検索結果、またはこれらのオプションのいずれかを使用してコンテンツの検索、レポートをエクスポートする場合、エクスポートには、インデックス Items.csv をという名前のレポートが含まれています。このレポートには、ResultsLog.csv ファイルと同じ情報のほとんどが含まれています。ただし、インデックス付けされない Items.csv ファイルも含まれる部分的にインデックス付きのアイテムに関連する 2 つのフィールド:**エラー タグ**および**プロパティのエラー**です。これらのフィールドには、部分的にインデックス付きの各項目のインデックス作成のエラーに関する情報が含まれています。これら 2 つのフィールドに情報を使用すると、特定のインデックス作成のエラーの調査に影響を与えるかどうかを判断することができます。場合は、対象となるコンテンツの検索を実行して取得して調査に関連するかを決定することを確認することができますように、特定の電子メール メッセージ、および SharePoint または OneDrive のドキュメントをエクスポートできます。手順については、 [Office 365 のコンテンツ検索の対象となる CSV ファイルの準備](csv-file-for-an-id-list-content-search.md)を参照してください。
  
 **注:** インデックス付けされない Items.csv ファイルには、**エラーの種類**と、**エラー メッセージ**という名前のフィールドも含まれています。これらは、あまり詳細な情報が、**タグのエラー**および**エラーのプロパティ**のフィールドに情報を次のような情報が含まれている従来のフィールドです。従来のこれらのフィールドは無視してかまいません。 
  
## <a name="errors-related-to-partially-indexed-items"></a>部分的にインデックス付きのアイテムに関連するエラー

エラー タグは、2 つの情報、エラー、およびファイルの種類で構成されています。: このエラーとファイルの種類の組み合わせで、

```
 parseroutputsize_xls
```

   
 `parseroutputsize`エラーと`xls`は、エラーが発生したファイルのファイルの種類。されたファイルの種類が認識されなかったか、ファイルの種類の場合は適用されません、エラー値が表示されます`noformat`ファイルの種類の代わりにします。 
  
エラーとエラーの原因の説明のインデックスの一覧を次に示します。
  
|**エラー タグ**|**説明**|
|:-----|:-----|
| `attachmentcount` <br/> |電子メール メッセージ、添付ファイルが多すぎる、これらの添付ファイルの一部が処理されませんでした。  <br/> |
| `attachmentdepth` <br/> |コンテンツの取得元とドキュメントのパーサーでは、添付ファイルの他の添付ファイルの入れ子のレベルが多すぎるが見つかりました。これらの添付ファイルの一部は処理されませんでした。  <br/> |
| `attachmentrms` <br/> |添付ファイルは、RM で保護されたためにデコードできませんでした。  <br/> |
| `attachmentsize` <br/> |電子メール メッセージの添付ファイルが大きすぎて、処理することができませんでした。  <br/> |
| `indexingtruncated` <br/> |インデックス処理された電子メール メッセージを作成する場合、インデックス付け可能なプロパティの 1 つが大きすぎます、切り捨てられました。切り捨てられたプロパティは、エラー プロパティ フィールドに表示されます。  <br/> |
| `invalidunicode` <br/> |電子メール メッセージには、有効な Unicode として処理することができませんでしたのテキストが含まれています。このアイテムのインデックス作成になりません。  <br/> |
| `parserencrypted` <br/> |添付ファイルまたは電子メール メッセージの内容が暗号化され、Office 365 は、コンテンツをデコードできませんでした。  <br/> |
| `parsererror` <br/> |解析中に不明なエラーが発生しました。通常、この結果から、ソフトウェアのバグ、またはサービスがクラッシュします。  <br/> |
| `parserinputsize` <br/> |を処理するパーサーの添付ファイルが大きすぎます、その添付ファイルの解析は見られませんでしたが終了しませんでした。  <br/> |
| `parsermalformed` <br/> |添付ファイルは、形式が正しくないし、パーサーによって処理されることができませんでした。互換性のないソフトウェアは、またはを装って何かを要求した以外のウイルスによって作成されたファイルは古いファイルからこの結果が書式設定します。  <br/> |
| `parseroutputsize` <br/> |添付ファイルの解析からの出力が大きすぎて、トランケートする必要があります。  <br/> |
| `parserunknowntype` <br/> |添付ファイルには、Office 365 を検出できませんでした。 ファイルの種類が必要があります。  <br/> |
| `parserunsupportedtype` <br/> |添付ファイルには、Office 365could の検出がサポートされていないファイルの種類を解析するファイルの種類が必要があります。  <br/> |
| `propertytoobig` <br/> |電子メールのプロパティの値を Exchange ストアが取得するには大きすぎると、メッセージを処理できませんでした。これは通常のみ発生、電子メール メッセージの本文のプロパティです。  <br/> |
| `retrieverrms` <br/> |コンテンツの取得元は、RM で保護されたメッセージをデコードできませんでした。  <br/> |
| `wordbreakertruncated` <br/> |インデックス作成時にドキュメントに多くの語句が確認されました。、上限に達すると、プロパティの処理が停止しているし、プロパティが切り捨てられます。  <br/> |
   
エラー フィールドは、フィールドの影響を受けるエラー タグ] フィールドに表示されている処理エラーについて説明します。プロパティを次のように検索する場合は`subject`または`participants`、エラー メッセージの本文ではありません、検索の結果に影響を与えます。これは、さらに調査する必要があります正確に部分的にインデックス付けされた項目を決定する際に役立ちます。
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>PowerShell スクリプトを使用して部分的にインデックス付きの電子メール アイテムの組織のリスクを決定するには

次の手順を表示するすべての Exchange メールボックス内のすべてのアイテムを検索 (数とサイズで)、組織の部分的にインデックス付きの電子メール アイテムの比率に関するレポートが生成され、アイテムの数を表示する PowerShell スクリプトを実行する方法 (およびファイルの種類) の各インデックスに発生するエラーです。前のセクションでエラー タグの説明を使用すると、インデックス作成のエラーを識別できます。
  
1. .Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `PartiallyIndexedItems.ps1`。

```
  write-host "**************************************************"
  write-host "     Office 365 Security &amp; Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
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
   
2. [Office 365 のセキュリティへの接続&amp;コンプライアンス センター PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084)。
    
3. セキュリティで&amp;コンプライアンス センター、手順 1 のスクリプトの保存先フォルダーに移動して、スクリプトを実行し、例えば：

    ```
    .\PartiallyIndexedItems.ps1
    ```
   
例/fo オプション、スクリプトによって返される出力します。
  
![部分的にインデックス付きの電子メール アイテムの組織のリスクに関するレポートを生成するスクリプトからの出力の例](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
次の点に注意してください。
  
1. 総数と、電子メール アイテムのサイズと、組織の (数とサイズで)、部分的にインデックス付きの電子メール アイテムの比率
    
2. リストのエラー タグと対応するファイルの種類のエラーが発生しました。
  
## <a name="see-also"></a>関連項目

[Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム](partially-indexed-items-in-content-search.md)
