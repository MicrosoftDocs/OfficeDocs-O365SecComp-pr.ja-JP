---
title: Office 365 Advanced eDiscovery でレポート フィールドをエクスポートする
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 840a5aff-ecd0-4e56-ad22-fe99bc143687
description: 高度な電子的証拠開示のレポートをエクスポートに含まれるすべてのフィールドについて説明します。
ms.openlocfilehash: a578523098248bcfa16ea8ba97d756d97ba060fa
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531836"
---
# <a name="export-report-fields-in-office-365-advanced-ediscovery"></a>Office 365 Advanced eDiscovery でレポート フィールドをエクスポートする

> [!NOTE]
> 高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。 
  
標準およびすべてのテンプレートの高度な電子的証拠開示のエクスポート レポートのフィールドについて説明します。
  
## <a name="export-report-fields"></a>レポートのフィールドをエクスポートします。

次の表は、各エクスポート テンプレートのフィールドを示します。
  
|**フィールド名をエクスポートします。**|**グループ**|**説明**|**標準のテンプレートで使用できます。**|**すべてのテンプレートで使用できます。**|
|:-----|:-----|:-----|:-----|:-----|
|形式で返します  <br/> |全般  <br/> |行番号です。  <br/> |はい  <br/> |はい  <br/> |
|File_ID  <br/> |全般  <br/> |ファイル id です。  <br/> |はい  <br/> |はい  <br/> |
|File_class  <br/> |処理  <br/> |ファイル クラスです。  <br/> |はい  <br/> |はい  <br/> |
|Family_ID  <br/> |処理  <br/> |(通常電子メールのインスタンスとその添付ファイル) のファイルをグループ化するために使用される数値の識別子です。  <br/> |はい  <br/> |はい  <br/> |
|For_review  <br/> |処理  <br/> |フィールドをレビューのためのエクスポートに含まれることを示すフラグです。  <br/> |はい  <br/> |はい  <br/> |
|Native_file_name  <br/> |処理  <br/> |ネイティブのファイル名、フォルダーと拡張子を参照しなくてもします。  <br/> |はい  <br/> |はい  <br/> |
|通告  <br/> |全般  <br/> |ファイルの保管担当者です。  <br/> |はい  <br/> |はい  <br/> |
|Set_ID  <br/> |分析  <br/> |ND の設定」または「セットを電子メールで送信」の id です。  <br/> |はい  <br/> |はい  <br/> |
|Inclusive_type  <br/> |電子メール  <br/> |次の値に基づいてファイルを含めたかどうかを示します: 0 -、1, 2 - マイナス、包括的なコピーの 3 つの包括的です。  <br/> |はい  <br/> |はい  <br/> |
|Marked_as_pivot  <br/> |近くの重複  <br/> |ファイルがピボットであるかどうかを示します。  <br/> |はい  <br/> |はい  <br/> |
|Similarity_percent  <br/> |近くの重複  <br/> |ピボットを基準にして類似性の割合です。  <br/> |はい  <br/> |はい  <br/> |
|Duplicate_subset  <br/> |近くの重複  <br/> |重複データのサブセットを表す一意の識別子です。ファイルに正確なテキストの重複があるかどうかを示します。  <br/> |はい  <br/> |はい  <br/> |
|日付  <br/> |全般  <br/> |ファイルの日付 (メール ・ ファイルの種類によって異なります: 送信日付; ドキュメント: 修正された日付)。  <br/> |はい  <br/> |はい  <br/> |
|Dominant_theme  <br/> |分析  <br/> |ファイルの主なテーマです。  <br/> |はい  <br/> |はい  <br/> |
|Themes_list  <br/> |テーマ  <br/> |テーマ名の一覧です。  <br/> |はい  <br/> |はい  <br/> |
|ND_set  <br/> |EquiSet  <br/> |Nearduplicate セットの一意の数値識別子です。  <br/> |はい  <br/> |はい  <br/> |
|Email_set  <br/> |電子メール  <br/> |メールの一意の数値識別子を設定します。  <br/> |はい  <br/> |はい  <br/> |
|Email_thread  <br/> |電子メール  <br/> |説明電子メール e メール内の位置をルートからをピリオドで区切られた、現在の電子メールのすべてのノード Id から構成されていますを設定します。  <br/> |はい  <br/> |はい  <br/> |
|Email_subject  <br/> |電子メール  <br/> |電子メールの件名です。  <br/> |はい  <br/> |はい  <br/> |
|Email_date_sent  <br/> |電子メール  <br/> |日付の電子メールが送信されました。  <br/> |はい  <br/> |はい  <br/> |
|Email_participants  <br/> |電子メール  <br/> |無効なリンクを含む、電子メール スレッドのすべての参加者の電子メール アドレスです。  <br/> |はい  <br/> |はい  <br/> |
|Email_participant_domains  <br/> |電子メール  <br/> |無効なリンクを含む、電子メール スレッドのすべての参加者のドメインです。  <br/> |はい  <br/> |はい  <br/> |
|Email_sender  <br/> |電子メール  <br/> |電子メールの送信者の名前またはアドレスです。  <br/> |はい  <br/> |はい  <br/> |
|Email_sender_domain  <br/> |電子メール  <br/> |送信者のドメインの電子メールを送信します。  <br/> |はい  <br/> |はい  <br/> |
|Email_to  <br/> |電子メール  <br/> |電子メールの受信者。  <br/> |はい  <br/> |はい  <br/> |
|Email_cc  <br/> |電子メール  <br/> |電子メールの CC 受信者です。  <br/> |はい  <br/> |はい  <br/> |
|Email_bcc  <br/> |電子メール  <br/> |電子メールの BCC 受信者です。  <br/> |はい  <br/> |はい  <br/> |
|Email_recipient_domains  <br/> |電子メール  <br/> |受信者 (宛先、CC、BCC) のドメインを電子メールで送信します。  <br/> |はい  <br/> |はい  <br/> |
|Email_date_received  <br/> |電子メール  <br/> |電子メールを受け取った日付です。  <br/> |はい  <br/> |はい  <br/> |
|Email_action  <br/> |電子メール  <br/> |: の値に応じて電子メールの件名:「転送」(の"FW:")、「返信」(の"RE:」) または「その他」(その他の件名のテキスト)。  <br/> |はい  <br/> |はい  <br/> |
|Meeting_Start_Date/時間  <br/> ||日付と時刻、会議アイテムが開始されます。  <br/> |はい  <br/> |はい  <br/> |
|Meeting_End_Date/時間  <br/> ||日付と会議アイテムの終了時刻。  <br/> |はい  <br/> |はい  <br/> |
|File_relevance_score  <br/> |関連性  <br/> |関連性のスコア (0-100) です。あたりの問題。  <br/> |はい  <br/> |はい  <br/> |
|Family_relevance_score  <br/> |関連性  <br/> |最大ファミリーの関連性のスコア (0-100) です。あたりの問題。  <br/> |はい  <br/> |はい  <br/> |
|Relevance_tag  <br/> |関連性  <br/> |ファイルが手動での関連性でタグ付けされた場合に、ファイルのタグ付けします。あたりの問題。  <br/> |はい  <br/> |はい  <br/> |
|Relevance_load_group  <br/> |関連性  <br/> |関連案件ごとのフィールドに、指定したファイルのロード グループです。  <br/> |はい  <br/> |はい  <br/> |
|Normalized_relevance_score  <br/> |関連性  <br/> |正規化された関連性のスコア (0-100)、問題と負荷の間で同等であります。  <br/> |はい  <br/> |はい  <br/> |
|Marked_as_seed  <br/> |関連性  <br/> |ごとの関連性の問題またはカテゴリ内のシード ファイルとして設定されている場合に、ファイルのタグ付けします。  <br/> |はい  <br/> |はい  <br/> |
|Marked_as_pre タグ  <br/> |関連性  <br/> |問題/カテゴリの関連性ごとに事前にタグ付きに設定した場合に、ファイルのタグ付けします。  <br/> |はい  <br/> |はい  <br/> |
|Relevance_status_description  <br/> |関連性  <br/> |関連性の状態の説明です。  <br/> |はい  <br/> |はい  <br/> |
|コメント  <br/> |全般  <br/> |ユーザーが入力したコメントです。  <br/> |はい  <br/> |はい  <br/> |
|Export_input_path  <br/> |処理  <br/> |入力パスをエクスポートします。  <br/> |はい  <br/> |はい  <br/> |
|Pivot_ID  <br/> |近くの重複  <br/> |ピボットのファイルの ID。  <br/> |はい  <br/> |はい  <br/> |
|Family_size  <br/> |処理  <br/> |ファミリ内のファイルの数です。  <br/> |はい  <br/> |はい  <br/> |
|Native_type  <br/> |処理  <br/> |ネイティブのファイルの種類です。たとえば、スプレッドシートまたはプレゼンテーションをします。  <br/> |はい  <br/> |はい  <br/> |
|Native_MD5  <br/> |処理  <br/> |ネイティブのファイルの MD5 ハッシュ値。  <br/> |はい  <br/> |はい  <br/> |
|Native_size  <br/> |処理  <br/> |ネイティブのファイル サイズです。  <br/> |はい  <br/> |はい  <br/> |
|Native_extension  <br/> |処理  <br/> |ネイティブのファイル拡張子です。  <br/> |はい  <br/> |はい  <br/> |
|Doc_date_modified  <br/> |ドキュメントのプロパティ  <br/> |ネイティブのファイルが変更されたファイルのメタデータから取得した日付です。  <br/> |はい  <br/> |はい  <br/> |
|Doc_date_created  <br/> |ドキュメントのプロパティ  <br/> |ネイティブ ファイルの日付が作成された、ファイルのメタデータから取得します。  <br/> |はい  <br/> |はい  <br/> |
|Doc_modified_by  <br/> |ドキュメントのプロパティ  <br/> |ファイルのメタデータから取得される、ネイティブのファイルを変更したユーザー。  <br/> |はい  <br/> |はい  <br/> |
|O365_date_modified  <br/> |ドキュメントのプロパティ  <br/> |ネイティブ ファイルの日付が変更されましたが、SharePoint または Exchange のいずれかのフィールドから取得しました。  <br/> |はい  <br/> |はい  <br/> |
|O365_date_created  <br/> |ドキュメントのプロパティ  <br/> |SharePoint または Exchange のいずれかのフィールドから取得した日付のネイティブ ファイルが作成されました。  <br/> |はい  <br/> |はい  <br/> |
|O365_modified_by  <br/> |ドキュメントのプロパティ  <br/> |ユーザーを最後には、SharePoint または Exchange のいずれかのフィールドから取得した、ネイティブのファイルが変更されました。  <br/> |はい  <br/> |はい  <br/> |
|Compound_path  <br/> |処理  <br/> |複合ソースを含むネイティブ ファイルのパスです。  <br/> |はい  <br/> |はい  <br/> |
|Input_path  <br/> |処理  <br/> |入力ファイルのパスです。  <br/> |はい  <br/> |はい  <br/> |
|Input_date_modified  <br/> |処理  <br/> |日付の入力ファイルは、最後に修正されました。  <br/> |はい  <br/> |はい  <br/> |
|ND_ET_sort_excl_attach  <br/> |分析  <br/> |電子メールの連結し ND がレビュー用に設定します。' にメールされた ND セットと 'E' にプレフィックスを追加すると表示されます。  <br/> |はい  <br/> |はい  <br/> |
|ND_ET_sort_incl_attach  <br/> |分析  <br/> |電子メールを連結したものを設定し、ND のレビューのための設定は ' ND セットと 'E' にプレフィックスを追加すると追加は、電子メールを設定します。さらに、各電子メールを Email_set 内で適切な添付ファイルが付いています。  <br/> |はい  <br/> |はい  <br/> |
|Deduped_custodians  <br/> |全般  <br/> |に対して除外するファイルの通告  <br/> |はい  <br/> |はい  <br/> |
|Deduped_file_IDs  <br/> |全般  <br/> |に対して除外するファイルの Id  <br/> |はい  <br/> |はい  <br/> |
|Deduped_paths  <br/> |全般  <br/> |に対して除外するファイルのパス  <br/> |はい  <br/> |はい  <br/> |
|File_key  <br/> |全般  <br/> |将来使用するための内部識別子です。  <br/> |はい  <br/> |はい  <br/> |
|Export_native_path  <br/> |処理  <br/> |ネイティブ エクスポート パッケージ ファイルのパスです。  <br/> |はい  <br/> |はい  <br/> |
|Extracted_text_path  <br/> |処理  <br/> |展開されたファイルのパスです。  <br/> |はい  <br/> |はい  <br/> |
|Process_batch  <br/> |処理  <br/> |インポートのバッチのバッチ識別子です。  <br/> |はい  <br/> |はい  <br/> |
|Process_status_ID  <br/> |処理  <br/> |プロセス ステージの状態を表す識別子です。  <br/> |はい  <br/> |はい  <br/> |
|Process_status_description  <br/> |処理  <br/> |処理ステージの状態の説明: 成功またはエラーの説明です。  <br/> |はい  <br/> |はい  <br/> |
|Export_status_ID  <br/> |処理  <br/> |エクスポートの状態の ID です。  <br/> |はい  <br/> |はい  <br/> |
|Export_status_description  <br/> |処理  <br/> |エクスポートのステータスの説明成功またはエラーの説明です。  <br/> |はい  <br/> |はい  <br/> |
|Read_percent  <br/> |関連性  <br/> |% (0-100) を参照してください。あたりの問題。  <br/> |はい  <br/> |はい  <br/> |
|Doc_author  <br/> |ドキュメントのプロパティ  <br/> |ドキュメント プロパティ: 作成者です。  <br/> |いいえ  <br/> |はい  <br/> |
|Doc_comments  <br/> |ドキュメントのプロパティ  <br/> |ドキュメント プロパティ: コメント。  <br/> |いいえ  <br/> |はい  <br/> |
|Doc_keywords  <br/> |ドキュメントのプロパティ  <br/> |ドキュメント プロパティ: キーワードです。  <br/> |いいえ  <br/> |はい  <br/> |
|Doc_last_saved_by  <br/> |ドキュメントのプロパティ  <br/> |ドキュメント プロパティ: 最終保存者。  <br/> |いいえ  <br/> |はい  <br/> |
|Doc_revision  <br/> |ドキュメントのプロパティ  <br/> |ドキュメント プロパティ: リビジョン番号。  <br/> |いいえ  <br/> |はい  <br/> |
|Doc_subject  <br/> |ドキュメントのプロパティ  <br/> |ドキュメント プロパティ: 情報カテゴリです。  <br/> |いいえ  <br/> |はい  <br/> |
|Doc_template  <br/> |ドキュメントのプロパティ  <br/> |ドキュメント プロパティ: テンプレートです。  <br/> |いいえ  <br/> |はい  <br/> |
|Doc_title  <br/> |ドキュメントのプロパティ  <br/> |ドキュメント プロパティ: タイトルです。  <br/> |いいえ  <br/> |はい  <br/> |
|Email_has_attachment  <br/> |電子メール  <br/> |電子メールが 1 つまたは複数の添付ファイルを持つかどうかを示します。  <br/> |いいえ  <br/> |はい  <br/> |
|Email_importance  <br/> |電子メール  <br/> |重要度のプロパティの電子メールを送信します。  <br/> |いいえ  <br/> |はい  <br/> |
|Email_level  <br/> |電子メール  <br/> |電子メールのスレッド内の電子メールのレベルを示します。添付ファイル、電子メールの添付されている値。  <br/> |いいえ  <br/> |はい  <br/> |
|Email_recipients  <br/> |電子メール  <br/> |名またはアドレス (宛先、CC、BCC) は、電子メールの受信者を実行します。  <br/> |いいえ  <br/> |はい  <br/> |
|Email_security  <br/> |電子メール  <br/> |電子メールのセキュリティのプロパティです。  <br/> |いいえ  <br/> |はい  <br/> |
|Email_sensitivity  <br/> |電子メール  <br/> |感度解析のプロパティの電子メールを送信します。  <br/> |いいえ  <br/> |はい  <br/> |
|Export_batch  <br/> |処理  <br/> |ファイルのエクスポート バッチ姓です。  <br/> |いいえ  <br/> |はい  <br/> |
|Export_session  <br/> |処理  <br/> |ファイルの最後のエクスポート ・ セッション Id を含む日付します。  <br/> |いいえ  <br/> |はい  <br/> |
|Extracted_text_length  <br/> |処理  <br/> |抽出されたテキスト ファイルの文字の長さです。  <br/> |いいえ  <br/> |はい  <br/> |
|Family_duplicate_set  <br/> |処理  <br/> |互いの正確なテキストで重複しているファミリーの数値識別子 (それぞれのファミリのすべてのメンバーは、正確な複製) します。  <br/> |いいえ  <br/> |はい  <br/> |
|Has_Text  <br/> |処理  <br/> |ファイルにテキストがあるかどうかを示します: 0 - なし。1-はい。  <br/> |いいえ  <br/> |はい  <br/> |
|Input_file_ID  <br/> |処理  <br/> |入力ファイルから抽出されたファイルの元の ID です。  <br/> |いいえ  <br/> |はい  <br/> |
|Native_SHA_256  <br/> |処理  <br/> |ネイティブ ファイルの sha-256 ハッシュ値です。  <br/> |いいえ  <br/> |はい  <br/> |
|O365_authors  <br/> |ドキュメントのプロパティ  <br/> |SharePoint または Exchange のいずれかのフィールドから取得した、ネイティブのファイルを変更したユーザーです。  <br/> |いいえ  <br/> |はい  <br/> |
|O365_created_by  <br/> |ドキュメントのプロパティ  <br/> |SharePoint または Exchange のいずれかのフィールドから取得した、ネイティブのファイルを作成したユーザー。  <br/> |いいえ  <br/> |はい  <br/> |
|Parent_node  <br/> |電子メール  <br/> |電子メール スレッド内のノードをリンクではない最も近い親ノードに関連しています。  <br/> |いいえ  <br/> |はい  <br/> |
|Set_order_inclusives_first  <br/> |電子メール  <br/> |電子メールおよび添付ファイル: カウンターの時系列順 (Inclusives 最初)。ドキュメント: は、類似性スコアを降順で最初と残りの部分を回転します。  <br/> |いいえ  <br/> |はい  <br/> |
|Tagged_By  <br/> |関連性  <br/> |関連性の特定の問題のファイルをタグ付けしたユーザーです。  <br/> |いいえ  <br/> |はい  <br/> |
|Word_count  <br/> |分析  <br/> |ドキュメント内の単語の数です。  <br/> |いいえ  <br/> |はい  <br/> |
|||||||||||
||||||
||||||
   
## <a name="related-topics"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[高度な電子的証拠開示のサポート案件のデータをエクスポートします。](export-case-data-in-advanced-ediscovery.md)
  
[結果のエクスポート](export-results-in-advanced-ediscovery.md)
  
[バッチ履歴を表示して、以前の結果をエクスポートします。](view-batch-history-and-export-past-results.md)
  

