---
title: Office 365 のセキュリティ コンテンツの検索結果をエクスポートするときに、レポートを無効にする&amp;コンプライアンス センター
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: Office 365 のセキュリティ コンテンツの検索結果をエクスポートするときにレポートを無効にするローカル コンピューターの Windows レジストリを編集する&amp;Comliance センター。これらのレポートを無効にすると、ダウンロード時間を短縮し、ディスク領域を節約できます。
ms.openlocfilehash: 3c09e0563ddd4469f21950dc3a698ce08b0014df
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532675"
---
# <a name="disable-reports-when-you-export-content-search-results-in-the-office-365-security-amp-compliance-center"></a>Office 365 のセキュリティ コンテンツの検索結果をエクスポートするときに、レポートを無効にする&amp;コンプライアンス センター

セキュリティ コンテンツの検索結果をエクスポートするのには Office 365 の電子的証拠開示のエクスポート ツールを使用すると&amp;コンプライアンス センター、ツール自動的に作成し、エクスポートされたコンテンツに関する追加情報が含まれている 2 つのレポートをエクスポートします。これらのレポートは、Results.csv ファイル Manifest.xml ファイル (これらのレポートの詳細な説明については、このトピックの[よく寄せられる質問に関するレポートをエクスポートを無効にする](#frequently-asked-questions-about-disabling-export-reports)セクションを参照してください)。これらのファイルであるため非常に大きく、ダウンロード時間を短縮し、これらのファイルがエクスポートされるようにすることでディスク領域を節約できます。検索結果のエクスポートに使用するコンピューターの Windows レジストリを変更することによってこれを行うことができます。後で、レポートを含める場合は、レジストリ設定を編集できます。 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>エクスポート レポートを無効にするレジストリ設定を作成します。

コンテンツの検索結果をエクスポートするのには使用するコンピューターで次の手順を実行します。
  
1. 開いている場合は、Office 365 の電子的証拠開示のエクスポート ツールを閉じます。
    
2. いずれかまたは両方を無効にするレポートのエクスポートによって、次の手順を実行します。
    
    - **Results.csv**
    
      次のテキストを .reg のファイル名サフィックスを使用して Windows レジストリ ファイルを保存します。たとえば、DisableResultsCsv.reg です。
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      次のテキストを .reg のファイル名サフィックスを使用して Windows レジストリ ファイルを保存します。たとえば、DisableManifestXml.reg です。
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. Windows エクスプ ローラーで、をクリックしてまたは前の手順で作成した .reg ファイルをダブルクリックします。
    
4. ユーザー アクセスの制御] ウィンドウで **[はい]** に変更した場合、レジストリ エディターを使用をクリックします。 
    
5. 続行するメッセージが表示されたら、[**はい**] をクリックします。
    
    レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>エクスポート レポートを再度有効にするレジストリ設定を編集します。

前の手順で .reg ファイルを作成することによって、Results.csv と Manifest.xml レポートを無効にした場合は、レポートを再度有効にするには、検索結果と共にエクスポートするためにそれらのファイルを編集できます。もう一度、コンテンツの検索結果をエクスポートするのには使用するコンピューターで次の手順を実行します。
  
1. 開いている場合は、Office 365 の電子的証拠開示のエクスポート ツールを閉じます。
    
2. 1 つまたは 2 つの .reg ファイルの編集前の手順で作成したを編集します。
    
    - **Results.csv**
    
        開いているメモ帳で DisableResultsCsv.reg ファイルの値を変更`False`を`True`、し、ファイルを保存します。などのファイルを編集した後に次のようになります。
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        開いているメモ帳で DisableManifestXml.reg ファイルの値を変更`False`を`True`、し、ファイルを保存します。などのファイルを編集した後に次のようになります。
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. Windows エクスプ ローラーでをクリックしてまたは前の手順で編集した内容の .reg ファイルをダブルクリックします。
    
4. ユーザー アクセスの制御] ウィンドウで **[はい]** に変更した場合、レジストリ エディターを使用をクリックします。 
    
5. 続行するメッセージが表示されたら、[**はい**] をクリックします。
    
    レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>エクスポート レポートの無効化についてよく寄せられる質問
<a name="faqs"> </a>

 **Results.csv と Manifest.xml レポートとは**
  
Results.csv、Manifest.xml ファイルには、エクスポートされたコンテンツに関する追加情報が含まれています。
  
- **Results.csv**する Excel ドキュメントを検索結果としては、ダウンロードする各アイテムに関する情報が含まれています。電子メールでは、結果のログに、各メッセージに関する情報が含まれているなど。 
    
  - 移行元のメールボックス内のメッセージの場所 (メッセージがプライマリ メールボックスとアーカイブ メールボックスのどちらであるかを含みます)。
    
  - メッセージが送信または受信された日付。
    
  - メッセージの件名行。
    
  - メッセージの送信者と受信者。
    
  - かどうか、メッセージは、検索結果をエクスポートするときに重複除外を有効にした場合、重複するメッセージです。重複したメッセージは、**親アイテムの Id**列を重複メッセージを識別する値があります。**親アイテムの Id**列の値は、エクスポートされたメッセージの**項目 DocumentId**列の値と同じです。 
    
    各ドキュメントに関する情報が含まれますビジネス サイトのドキュメント SharePoint と OneDrive から、には結果のログには含みます。
    
  - ドキュメントの URL。
    
  - ドキュメントがあるサイト コレクションの URL。
    
  - ドキュメントが最後に変更された日付。
    
  - ドキュメントの名前 (これは、結果のログの [件名] 列にあります)。
    
- **Manifest.xml**内のマニフェスト ファイル (XML 形式) を検索結果に含まれる各アイテムに関する情報が含まれています。このレポートの情報は、Results.csv レポートと同じですが、指定されている形式の電子証拠開示の参照モデル (優れた) で。優れたについての詳細についてを参照して[https://www.edrm.net](https://www.edrm.net)。
    
 **無効にすべきこれらのレポートをエクスポートしますか。**
  
お客様固有のニーズによって異なります。多くの組織では、検索結果に関する追加情報を必要としないし、これらのレポートは必要ありません。
  
 **どのようなコンピューターでこれを行うにあるでしょうか。**
  
 Office 365 の電子的証拠開示のエクスポート ツールを実行する任意のローカル コンピューターのレジストリ設定を変更する必要があります。 
  
 **この設定を変更した後コンピューターを再起動する必要ですか。**
  
いいえ、コンピューターを再起動する必要はありません。閉じ、レジストリ設定を変更した後に再起動する必要がある Office 365 の電子的証拠開示のエクスポート ツールを実行する場合。
  
 **既存のレジストリ キーを編集を取得して新しいキーを作成を取得してか。**
  
最初にこのトピックの手順で作成した .reg ファイルを実行するとき、新しいレジストリ キーが作成されます。設定を変更および編集の .reg ファイルを再実行するたびに編集します。
