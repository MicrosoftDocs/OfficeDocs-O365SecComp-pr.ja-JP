---
title: Office 365 Advanced eDiscovery で結果をエクスポートする
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: 'エクスポート バッチのパラメーターを指定するための手順を含む、Office 365 の詳細の開示から結果をエクスポートするためのオプションを定義する方法について説明します。 '
ms.openlocfilehash: 92ee107ad096393fbccbc9a3dbe81d8e7dd28da9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532741"
---
# <a name="export-results-in-office-365-advanced-ediscovery"></a>Office 365 Advanced eDiscovery で結果をエクスポートする

> [!NOTE]
> 高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。 
  
このトピックでは、高度な電子的証拠開示の設定のエクスポート オプションについて説明します。
  
 **このトピックの内容**
  
- [エクスポート バッチとのセッションを定義します。](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [増分バックアップとその他のエクスポート](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [バッチ エクスポートのパラメーターを設定します](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [レポートの出力ファイルをエクスポートします。](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a>エクスポート バッチとのセッションを定義します。
<a name="BK_Define"> </a>

エクスポートのバッチは、エクスポートの処理が定義されているパラメーターのセットを使用できます。高度な電子的証拠開示では、各エクスポートをカスタマイズするのにはバッチを定義できます。
  
パラメーターは、エクスポートのバッチごとに定義します。既定では、大文字と小文字の最初のバッチのエクスポート バッチ 01] という名前のバッチが作成されます。バッチの名前と説明を編集することもできます。
  
エクスポート セッションは、高度な電子的証拠開示エクスポートするエクスポートのバッチ内での実行です。
  
## <a name="incremental-and-additional-exports"></a>増分バックアップとその他のエクスポート
<a name="BK_IncrementalReports"> </a>

同じテンプレートのエクスポートとパラメーターに基づく結果の一貫性を確保するのには、エクスポートのバッチ内で複数のエクスポート ・ セッションを実行することができます。新しくケース データを処理し、それぞれを「差分」処理のバッチ内での各セッションの分析をエクスポートすることができます。
  
パラメーターの異なるセットを使用して、エクスポートするためには、まず、新しいバッチを作成する必要があります。最初のセッションで新しいバッチ ファイルをこれらのファイルがインポートされ、1 つまたは複数のインポートを処理するかどうかの場合はこれまで、処理の結果が生成されます。各バッチには、ピボット、類似性、inclusives などが再計算されます。セッションでは、バッチに対して定義されているパラメーターを使用して、ピボット、類似性、inclusives などの各セッションの実行が再計算されません。
  
たとえば、サポート案件がインポートされましたが、そのデータを分析します。重複の近くとインクリメンタル データの結果を電子メールのスレッドを取得するために使われていたデータをエクスポートするのには同じバッチ内で**作成するセッションをエクスポートする**をクリックします。 
  
## <a name="set-up-batch-export-parameters"></a>バッチ エクスポートのパラメーターを設定します
<a name="BK_SetUpExport"> </a>

電子証拠開示のエクスポート ツールは、ローカル コンピューターに高度な電子的証拠開示から検索結果をエクスポートするのには使用されます。増やすには、データ転送のスループットとをエクスポート処理の高速化、検索結果のエクスポートに使用するコンピューターの Windows レジストリ設定を構成できます。ダウンロード時間を短縮したい場合は、エクスポートのパラメーターを設定する前に、レジストリ設定を構成します。詳細については、 [Office 365 からの電子的証拠開示検索結果をエクスポートするときのダウンロード速度を向上させる](increase-download-speeds-when-exporting-ediscovery-results.md)を参照してください。
  
1. 高度な電子的証拠開示で、大文字と小文字を選択し、[**エクスポート**] をクリックして\>**セットアップ**します。
    
  - **バッチのエクスポート**] ボックスの一覧で、バッチの名前を選択またはエクスポート バッチ 01、(既定のバッチ) に結果をエクスポートします。 
    
  - 既存のケースに追加した新しいファイルの結果をエクスポートするには、現在のバッチを続行します。バッチ内のセッションを作成、同じバッチ番号を選択および**作成するセッションのエクスポート**] をクリックするには、前のバッチでは、増分方式で同じパラメーターをエクスポートするのにはこのオプションを使用することができます。 
    
  - 新しいバッチにエクスポートする場合の [**追加**] をクリックします![のアイコンを追加](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)および**バッチ名**に新しい名前を入力 (または既定値をそのまま使用) と**バッチの説明**で説明します。**[Ok]** をクリックします。
    
  - バッチの名前または説明を編集するには、**バッチのエクスポート**の名前を選択して、[**編集**] をクリックして![[編集] アイコン](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)、し、フィールドを変更します。
    
    > [!NOTE]
    > エクスポート バッチのセッションを実行すると、それらを削除することはできません。さらに、最初のセッションが実行されるにはいくつかのパラメーターのみを編集できます。 
  
  - 重複データのエクスポートのバッチを作成するには、**重複データのエクスポートのバッチ**を選択します![重複データのエクスポートのバッチ アイコンを作成する](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)パネルの名前と重複するバッチの説明を入力するとします。 
    
  - [**削除**] に、エクスポートのバッチを削除するには、![バッチ エクスポート アイコンを削除](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)。
    
  - バッチの履歴を表示するには、**バッチの履歴**を選択して![の履歴の表示アイコン](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)。
    
2. エクスポートのバッチの設定を微調整する場合は、[**カタログの作成**、**関連性の高いカットオフ スコアの上のファイルのみを含める**と**絞り込みのエクスポートのバッチ**を選択します。 
    
3. **カットオフ スコアの妥当性上のファイルのみを含む**を選択した場合、**問題**になっています。ファイルの関連性スコアが選択されている問題に対するカットオフ スコアより高い場合は、'レビュー' のフィルターによって除外されていない限り、ファイルがエクスポートされます。 
  
**エクスポートのバッチを絞り込み**を選択した場合、**重複除外**とフィルターの確認] で、フィールドのオプション ボタンは有効になっています。選択した場合 **、重複除外**、定義したポリシーによって除外されるファイルの複製し、[レベル (既定値) の場合: 全体の場合は、重複するファイルのすべてのセットから 1 つを除くすべてのファイルは除外に対してされます。管理者レベル: 同じ書の重複したファイルのすべてのセットから 1 つを除くすべてのファイルは除外に対してされます]。エクスポートの出力には、重複するファイルのすべてのレコードが含まれています。**'レビュー' のフィルター**フィールドを選択した場合は、 **'レビュー' の**フィールドの設定を入力するのには、**メタデータの変更**を選択します。パッケージ コンテンツのソース ファイルを含めることを**含む入力ファイル**を選択します。エクスポート処理を高速化するには、この設定をオフにすることができます。ネイティブのファイルがどのような場合にエクスポートされることに注意してください。 
    
4. **メタデータ**では、下には、**テンプレートをエクスポート**します (セッション) ごとに次のオプションから選択します。 
    
  - **標準**: 基本的な項目のデータ、メタデータ、およびプロパティのセットです。インポート データが高度な電子的証拠開示で既に処理されて、ファイルが既に含まれているシステムにアップロードされているデータをエクスポートするときは、このオプションを使用します。既定では、列が作成され、入力のテンプレートをエクスポートします。
    
  - **すべて**: すべてのデータ処理を行うと分析との関連性のスコアを含む標準のメタデータの完全なセットです。このテンプレートは、高度な電子的証拠開示の処理を実行すると、最初に、外部システムにアップロードするファイル データに必要です。
    
  - **問題**:**すべての懸案事項**を選択または作成した特定の問題を選択します。 
    
5. [**宛先**:]
    
  - **ローカル マシンにダウンロードします。**
    
  - **Azure blob のユーザー定義をエクスポート**します。 これをオンにした場合は、コンテナーの URL と SAS のトークンを指定できます。
    
    > [!NOTE]
    > エクスポート パッケージが格納されているユーザーには、Azure blob が定義されている、高度な電子的証拠開示は、データが管理されていません。Azure blob が管理します。つまり場合は、大文字と小文字を削除すると、書き出されたファイルもに残ります Azure blob です。 
  
  - **将来のエクスポート ・ セッションのトークンを SAS の保存**: チェックすると、SAS のトークンが将来使用するための高度な電子的証拠開示の内部データベースに暗号化されます。
    
    > [!NOTE]
    > 現在 SAS のトークンは、1 か月後に有効期限が切れます。最後のセッションを取り消す必要が複数の月の後にダウンロードしようとする場合は、もう一度エクスポートし、します。 
  
6. 設定の**変更**] をクリックして、[確認のため ' フィールドの設定です。 
    
> ![エクスポート バッチの確認フィールドの seetings の設定します。](media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
    In **For review field settings** panel, in **Select scenario**, select the scenario and scope of the review. The settings are displayed based on your selection.
    
    **Review all** (default): All emails, attachments, and documents are selected by default. 
    
    **Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.
    
    **Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.
    
    **Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.
    
    **Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection. 
    
    If you select custom, you can then customize the settings for emails, documents, attachments and miscellaneous.
    
> **電子メール**で電子メールをエクスポートするを選択します。 
    
    **All emails**: (default) All emails are selected.
    
    **Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.
    
    **Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .
    
> **ドキュメント**では、エクスポートするドキュメントを選択します。 
    
    **All documents**: (default) All documents are selected.
    
    **Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.
    
    **Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).
    
> **添付ファイル**の添付ファイルをエクスポートするを選択します 
    
    **All attachments**: (default) All attachments are selected.
    
    **Unique attachment in case level**: Unique attachment files within the specified case.
    
    **Unique attachment in email set level**: Unique attachment files within the specified email case.
    
> **Micellaneous**では、**ドキュメントと添付ファイルを扱う****ドキュメントと電子メールを扱う**、または**ファミリ ファイルを含むように展開**できます。ファイルごとにフラグが設定されている確認のため **、ファミリのファイルの展開**を選択すると、同じファミリのすべてのファイルはフラグが設定もします。
    
    Choose **Save** to save the settings. 
    
7. エクスポート パラメーターを指定すると、エクスポートのバッチを開始する] をクリック**を作成するセッションをエクスポートします**。
    
    書き出し時に、**タスクの進捗状況**のステータスが表示されます。**エクスポートの概要**では、結果が表示されます。
    
8. **ファイルのダウンロード**ウィンドウで、エクスポート キーのコピーを**クリップボードにコピー**をクリックします。 
    
    ![ファイルをダウンロードします。](media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
9. **[閉じる]** をクリックします。 
    
    電子的証拠開示のエクスポート ツールを起動します。
    
    ![電子情報開示のエクスポート ツール](media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
10. **エクスポート ツールで電子的証拠開示**します。
    
1. **ソースへの接続に使用される、共有アクセス署名を貼り付ける**には、内には、クリップボードにその youcopied エクスポート キーを貼り付け、手順 7 で。
    
2. ローカル コンピューターにダウンロードしたエクスポート ファイルを保存するターゲットの場所を選択する**参照**をクリックします。 
    
11. [**開始**] をクリックします。エクスポート ファイルは、ローカル コンピューターにダウンロードされます。手順 4 で**ユーザー定義の Azure blob へのエクスポート**を選択した場合は、Blob ストレージ URL 先を選択してセッションがエクスポートされます。 
    
エクスポート レポート内のフィールドの完全な説明は、[レポートのフィールドをエクスポートする](export-report-fields-in-advanced-ediscovery.md)を参照してください。
  
## <a name="export-report-output-files"></a>レポートの出力ファイルをエクスポートします。
<a name="BK_ExportOutputFIles"> </a>

エクスポートのバッチを実行するときに生成される出力ファイルを次の表に一覧します。
  
|**ファイル名**|**ファイルの種類**|**説明**|
|:-----|:-----|:-----|
|エクスポートの概要  <br/> |csv  <br/> |ログ ファイルは、エクスポート ・ ツールを電子的証拠開示によって生成されます。  <br/> |
|トレース  <br/> |txt  <br/> |ログ ファイルは、エクスポート ・ ツールを電子的証拠開示によって生成されます。  <br/> |
|抽出されたテキスト ファイル  <br/> |ファイル フォルダー  <br/> |書き出されたファイルの抽出されたテキスト ファイルを含むフォルダーです。  <br/> |
|入力またはネイティブ ファイル  <br/> |ファイル フォルダー  <br/> |エクスポートしたファイルのネイティブと入力ファイルを含むフォルダーです。  <br/> |
|ボックスの一覧をエクスポートします。  <br/> |xlsx  <br/> |Xlsx 形式でエクスポートされたファイルのメタデータ。ファイル内のフィールドはエクスポートするテンプレートのユーザーの選択に従っています。必要な場合は、いくつかのファイルが作成される、それぞれに 100-150 K の行が含まれています。Excel のセルを含めることができますを超える文字が特定の値に含まれているかどうか (現在の制限は 32,767 文字) をし、値を許可する最大の長さにトリミングされます。値をトリミングすると、セルの背景色が赤に、これをユーザーに示す」参加者の電子メール"は、大規模な配布する電子メールが送信された場合の長さの制限を超えている可能性があるフィールドの例です。出力フィールドの詳細については、[レポートのフィールドをエクスポートする](export-report-fields-in-advanced-ediscovery.md)を参照してください。<br/> |
|ファイルの読み込み  <br/> |csv  <br/> |別のアプリケーションに読み込む csv 形式でエクスポートされたファイルのメタデータ。ファイル内のフィールドはエクスポートするテンプレートのユーザーの選択に従っています。  <br/> |
|成功インジケーター  <br/> |txt  <br/> |サードパーティの Azure blob にエクスポートするときにのみ作成します。エクスポートが完全に成功した場合は、ファイルが作成されます。障害発生時、または部分的な成功した場合、ファイルは作成されません。別のエクスポートのバッチまたはセッション状態の自動追跡を許可する、ルート フォルダーにファイルが作成されます。これは、空のファイルです。名前: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt。  <br/> |
   
## <a name="see-also"></a>関連項目
<a name="BK_ExportOutputFIles"> </a>

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[バッチ履歴を表示して、以前の結果をエクスポートします。](view-batch-history-and-export-past-results.md)
  
[Office 365 Advanced eDiscovery のクイック セットアップ](quick-setup-for-advanced-ediscovery.md)

[レポートのフィールドをエクスポートします。](export-report-fields-in-advanced-ediscovery.md)
  
[Office 365 から電子的証拠開示検索結果をエクスポートするときは、ダウンロード速度を上げる](increase-download-speeds-when-exporting-ediscovery-results.md)

