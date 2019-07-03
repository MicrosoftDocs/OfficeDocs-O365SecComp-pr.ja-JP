---
title: 監査ログレコードをエクスポート、構成、および表示する
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: Office 365 監査ログ検索の結果をエクスポートして CSV ファイルにダウンロードした後、Excel の Power Query エディターの JSON 変換機能を使用して、AuditData 列の JSON オブジェクトの各プロパティをそれぞれの列に分割できます。 これは、探している特定の監査データをすばやく見つけるのに役立ちます。
ms.openlocfilehash: 7dac373e8f25ead38dddbe2663e521b35b3153ef
ms.sourcegitcommit: b262d40f6daf06be26e7586f37b736e09f8a4511
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35462930"
---
# <a name="export-configure-and-view-audit-log-records"></a>監査ログレコードをエクスポート、構成、および表示する

Office 365 監査ログを検索し、検索結果を CSV ファイルにダウンロードした後、ファイルには、各イベントに関する追加情報を含む**Auditdata**という名前の列が含まれます。 この列のデータは、JSON オブジェクトとして書式設定されています。これには、*プロパティと値*のペアとして構成され、コンマで区切られた複数のプロパティが含まれています。 Excel の Power Query エディターで JSON 変換機能を使用して、 **Auditdata**列の json オブジェクトの各プロパティを複数の列に分割し、各プロパティがそれぞれの列を持つようにすることができます。 これにより、これらのプロパティの1つ以上に対して並べ替えとフィルター処理を行うことができます。これにより、探している特定の監査データをすばやく見つけることができます。

## <a name="step-1-export-audit-log-search-results"></a>手順 1: 監査ログの検索結果をエクスポートする

最初の手順として、監査ログを検索し、結果をコンマ区切り値 (CSV) ファイルとしてローカルコンピューターにエクスポートします。
  
1. [監査ログの検索](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log)を実行し、目的の結果が得られるまで、必要に応じて検索条件を修正します。
    
2. [**結果のエクスポート**] をクリックし、[**すべての結果をダウンロード**する] を選択します。 
    
   ![[すべての結果をダウンロード] をクリックします。](media/ExportAuditSearchResults.png)

   このオプションは、手順1で実行した監査ログ検索からすべての監査レコードをエクスポートし、その生データを監査ログから CSV ファイルにダウンロードするために使用します。 

   ウィンドウの下部に、CSV ファイルを開くか保存するかを確認するメッセージが表示されます。 

3. [保存] をクリックし**て名前を付けて保存 >** 、CSV ファイルをローカルコンピューターに保存します。 多くの検索結果をダウンロードするには、しばらく時間がかかります。 通常は、すべてのアクティビティまたは広範な日付範囲を検索する場合に使用します。 CSV ファイルのダウンロードが完了すると、ウィンドウの下部にメッセージが表示されます。
 
   ![CSV ファイルのダウンロードが完了したときに表示されるメッセージ](media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > 1つの監査ログ検索から CSV ファイルに最大5万エントリをダウンロードできます。 5万エントリが CSV ファイルにダウンロードされた場合は、検索条件に一致する5万イベントの数がを超える可能性があると考えられます。 この制限を超える値をエクスポートするには、日付範囲を使用して監査ログレコードの数を減らしてみてください。 5万を超えるエントリをエクスポートするには、短い日付範囲で複数の検索を実行する必要がある場合があります。

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a>手順 2: Power Query エディターを使用してエクスポートされた監査ログを書式設定する

次の手順では、Excel の Power Query エディターで JSON 変換機能を使用して、 **Auditdata**列の json オブジェクトの各プロパティをそれぞれの列に分割します。 次に、列をフィルター処理して、特定のプロパティの値に基づいてレコードを表示します。 これは、探している特定の監査データをすばやく見つけるのに役立ちます。

1. Excel for Office 365、Excel 2019、または Excel 2016 に対して空のブックを開きます。
    
2.  [**データ**] タブの [ **Get & Transform Data** ] リボングループで、[ **Text/CSV**] をクリックします。

    ![[データ] タブの [テキスト/CSV から] をクリックします。](media/JSONTransformOpenCSVFile.png)

3. 手順1でダウンロードした CSV ファイルを開きます。
    
4. 表示されたウィンドウで、[**データの変換**] をクリックします。

   ![[データの変換] をクリックします。](media/JSONOpenPowerQuery.png)

CSV ファイルが**クエリエディター**で開かれます。 **CreationDate**、 **UserIds**、 **Operations**、および**auditdata**の4つの列があります。 **Auditdata**列は、複数のプロパティを含む JSON オブジェクトです。 次の手順では、JSON オブジェクトの各プロパティに対して列を作成します。
    
5. **Auditdata**列のタイトルを右クリックし、[**変換**] をクリックして、[ **JSON**] をクリックします。 
 
   ![[AuditData] 列を右クリックし、[変換] をクリックして、[JSON] を選択します。](media/JSONTransform.png)

6. **Auditdata**列の右上隅で、[展開] アイコンをクリックします。
    
   ![[AuditData] 列で、[expand] アイコンをクリックします。](media/JSONTransformExpandIcon.png)

   **Auditdata**列の JSON オブジェクトのプロパティの一部のリストが表示されます。

7. [**詳細を読み込む**] をクリックして、[ **auditdata** ] 列の JSON オブジェクトのすべてのプロパティを表示します。

   ![[詳細を読み込む] をクリックして、JSON オブジェクトのすべてのプロパティを表示します。](media/JSONTransformLoadJSONProperties.png)

   含める必要のないプロパティの横にあるチェックボックスの選択を解除することができます。 調査に役に立たない列を削除することは、監査ログに表示されるデータの量を減らすための適切な方法です。 

   > [!NOTE]
   > 前のスクリーンショットに表示されている JSON プロパティは、CSV ファイルの最初の1000行の**Auditdata**列にあるプロパティに基づいています ([**さらに読み込む**] をクリックした後)。 最初の1000行の後のレコードに異なる JSON プロパティがある場合、 **Auditdata**列が複数の列に分割されていると、これらのプロパティ (および対応する列) は含まれません。 これを防ぐには、監査ログの検索を再実行し、返されるレコード数が少なくなるように検索条件を絞ることを検討してください。 もう1つの回避策として、[**操作**] 列のアイテムにフィルターを適用して、[ **auditdata** ] 列で JSON オブジェクトを変換する前に、行数を減らします (上記の手順5を実行する前)。

8. 次のいずれかの操作を実行して、選択されている各 JSON プロパティに対して追加される列のタイトルを書式設定します。

    - [**元の列名をプレフィックスとして使用**する] チェックボックスをオフにして、JSON プロパティの名前を列名として使用します。たとえば、 **RecordType**または**sourcefilename**のようになります。
    
   - [**元の列名をプレフィックスとして使用**する] チェックボックスをオンのままにして、auditdata プレフィックスを列名に追加します。たとえば、 **Auditdata**または**auditdata ファイル名**です。

9. **[OK]** をクリックします。
    
    **Auditdata**列は複数の列に分割されます。 新しい列はそれぞれ、AuditData JSON オブジェクトのプロパティに対応しています。 列の各行には、プロパティの値が含まれています。 プロパティに値が含まれていない場合は、 *null*値が表示されます。 Excel では、null 値を持つセルは空になります。
  
10. [**ホーム**] タブで、[**閉じる & Load** ] をクリックして Power Query Editor を閉じ、変換された CSV ファイルを Excel ブックで開きます。 

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a>監査ログをエクスポートして表示するためのヒント

ここでは、JSON 変換機能を使用して、 **Auditdata**列を複数の列に分割する前と後の監査ログをエクスポートおよび表示する際のヒントと例をいくつか示します。

- **RecordType**列をフィルター処理して、特定の Office 365 サービスまたは機能領域のレコードのみを表示します。 たとえば、SharePoint 共有に関連するイベントを表示するには、[ **14** ] (sharepoint 共有アクティビティによってトリガーされたレコードの列挙値) を選択します。 **RecordType**列に表示される列挙値に対応する office 365 サービスの一覧については、「 [office 365 監査ログの詳細なプロパティ](detailed-properties-in-the-office-365-audit-log.md)」を参照してください。

- [**操作**] 列をフィルター処理して、特定のアクティビティのレコードを表示します。 セキュリティ & コンプライアンスセンターの監査ログ検索ツールで検索可能なアクティビティに対応するほとんどの操作の一覧については、「 [security & コンプライアンスセンターで監査ログを検索](search-the-audit-log-in-security-and-compliance.md#audited-activities)する」の「監査アクティビティ」セクションを参照してください。

- セキュリティ & コンプライアンスセンターで監査ログ検索ツールを使用する代わりに、Exchange Online Powershell で[search-unifiedauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog)コマンドレットを使用して、Office 365 監査ログの検索結果を CSV ファイルにエクスポートすることができます。 その後、手順2で説明されているのと同じ手順に従って、Power Query エディターを使用して監査ログを書式設定できます。 PowerShell コマンドレットを使用する場合の利点の1つは、 *RecordType*パラメーターを使用して特定の Office 365 サービスからのイベントを検索できることです。 ここでは、PowerShell を使用して監査レコードを CSV ファイルにエクスポートする例をいくつか示します。このため、Power Query editor を使用して、「 **Auditdata** 」列の JSON オブジェクトを変換することができます (手順2を参照)。

   この例では、次のコマンドを実行して、SharePoint 共有操作に関連するすべてのレコードを返します。 
   
   ```
   $auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
   ```

   ```
   $auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
   ```

   - 検索結果は、次の4つの列 (CreationDate、UserIds、RecordType、AuditData) を含む*Powershellauditlog ログ*という名前の CSV ファイルにエクスポートされます。

   - *RecordType*パラメーターの値として、レコードの種類の名前または列挙値を使用できます。 レコードの種類の名前とそれに対応する列挙値の一覧については、「 [Office 365 Management ACTIVITY API スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)の*AuditLogRecordType*テーブル」を参照してください。
   
   - このパラメーターには、1つの値のみを含めることができます。 他のレコードの種類の監査レコードを検索するには、2つの前のコマンドを再度実行して、別のレコードの種類を指定し、それらの結果を元の CSV ファイルに追加します。 たとえば、次の2つのコマンドを実行して、同じ日付範囲の SharePoint ファイルアクティビティを PowerShellAuditlog ファイルに追加します。

       ```
      $auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
      ```

      ```
      $auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
      ```
