---
title: Office 365 でレポートフィールドをエクスポートする高度な電子情報開示
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 840a5aff-ecd0-4e56-ad22-fe99bc143687
description: 高度な電子情報開示のエクスポートレポートに含まれるすべてのフィールドについて説明します。
ms.openlocfilehash: 3e73cc1c106dfa98bd35f84c352fc89d0e45b74d
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154474"
---
# <a name="export-report-fields-in-office-365-advanced-ediscovery"></a>Office 365 でレポートフィールドをエクスポートする高度な電子情報開示

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
このトピックでは、標準およびすべてのテンプレートの高度な電子情報開示エクスポートレポートのフィールドについて説明します。
  
## <a name="export-report-fields"></a>レポートのフィールドのエクスポート

次の表に、各エクスポートテンプレートのフィールドを示します。
  
|**フィールド名をエクスポートする**|**グループ**|**説明**|**標準テンプレートで使用可能**|**すべてのテンプレートで使用可能**|
|:-----|:-----|:-----|:-----|:-----|
|Row_number  <br/> |全般  <br/> |行番号を指定します。  <br/> |はい  <br/> |はい  <br/> |
|File_ID  <br/> |全般  <br/> |ファイル ID。  <br/> |はい  <br/> |はい  <br/> |
|File_class  <br/> |Processing  <br/> |File クラス。  <br/> |はい  <br/> |はい  <br/> |
|Family_ID  <br/> |Processing  <br/> |ファイルをグループ化するために使用される数値識別子 (通常はメールインスタンスとその添付ファイル)。  <br/> |はい  <br/> |はい  <br/> |
|For_review  <br/> |Processing  <br/> |フィールドがレビューのためにエクスポートに含まれることを示すフラグ。  <br/> |はい  <br/> |はい  <br/> |
|Native_file_name  <br/> |Processing  <br/> |ネイティブファイル名。フォルダーと拡張子を参照しません。  <br/> |はい  <br/> |はい  <br/> |
|保管担当者  <br/> |全般  <br/> |ファイルの保管担当者。  <br/> |はい  <br/> |はい  <br/> |
|Set_ID  <br/> |分析  <br/> |"ND set" または "Email set" id。  <br/> |はい  <br/> |はい  <br/> |
|Inclusive_type  <br/> |Email  <br/> |次の値に従ってファイルが包含されているかどうかを示します。 0-包含ではない、1-包括、2: 包括的コピー。  <br/> |はい  <br/> |はい  <br/> |
|Marked_as_pivot  <br/> |重複の近似  <br/> |ファイルがピボットかどうかを示します。  <br/> |はい  <br/> |はい  <br/> |
|Similarity_percent  <br/> |重複の近似  <br/> |ピボットに対する類似性の割合。  <br/> |はい  <br/> |はい  <br/> |
|Duplicate_subset  <br/> |重複の近似  <br/> |重複したサブセットの一意の識別子。 ファイルが完全にテキストの複製であるかどうかを示します。  <br/> |はい  <br/> |はい  <br/> |
|日付  <br/> |全般  <br/> |ファイルの日付 (ファイルの種類によって異なります-電子メール: 送信日、ドキュメント: 日付が変更されます)。  <br/> |はい  <br/> |はい  <br/> |
|Dominant_theme  <br/> |分析  <br/> |ファイルの主なテーマ。  <br/> |はい  <br/> |はい  <br/> |
|Themes_list  <br/> |テーマ  <br/> |テーマ名のリスト。  <br/> |はい  <br/> |はい  <br/> |
|ND_set  <br/> |設定  <br/> |Nearduplicate セットの一意の数値識別子。  <br/> |はい  <br/> |はい  <br/> |
|Email_set  <br/> |Email  <br/> |電子メールセットの一意の数値識別子。  <br/> |はい  <br/> |はい  <br/> |
|Email_thread  <br/> |Email  <br/> |メールセット内の電子メールの位置について説明します。これは、ルートから現在の電子メールへのすべてのノード Id で構成され、ピリオドで区切られています。  <br/> |はい  <br/> |はい  <br/> |
|Email_subject  <br/> |Email  <br/> |電子メールの件名。  <br/> |はい  <br/> |はい  <br/> |
|Email_date_sent  <br/> |Email  <br/> |電子メールが送信された日付。  <br/> |はい  <br/> |はい  <br/> |
|Email_participants  <br/> |Email  <br/> |電子メールスレッド内のすべての参加者の電子メールアドレス (欠落したリンクを含む)。  <br/> |はい  <br/> |はい  <br/> |
|Email_participant_domains  <br/> |Email  <br/> |電子メールスレッド内のすべての参加者のドメイン (欠落したリンクを含む)。  <br/> |はい  <br/> |はい  <br/> |
|Email_sender  <br/> |Email  <br/> |電子メールの送信者の名前またはアドレス。  <br/> |はい  <br/> |はい  <br/> |
|Email_sender_domain  <br/> |Email  <br/> |電子メールの送信者のドメイン。  <br/> |はい  <br/> |はい  <br/> |
|Email_to  <br/> |Email  <br/> |電子メールの受信者に送信します。  <br/> |はい  <br/> |はい  <br/> |
|Email_cc  <br/> |Email  <br/> |電子メールの CC 受信者。  <br/> |はい  <br/> |はい  <br/> |
|Email_bcc  <br/> |Email  <br/> |電子メールの BCC 受信者。  <br/> |はい  <br/> |はい  <br/> |
|Email_recipient_domains  <br/> |Email  <br/> |電子メール受信者ドメイン (宛先、CC、および BCC)。  <br/> |はい  <br/> |はい  <br/> |
|Email_date_received  <br/> |Email  <br/> |電子メールが受信された日付。  <br/> |はい  <br/> |はい  <br/> |
|Email_action  <br/> |Email  <br/> |値: メールの件名に従ってください。 "Forward" ("FW:")、"Reply" ("RE:" の場合) または "その他" (他の件名テキスト)。  <br/> |はい  <br/> |はい  <br/> |
|Meeting_Start_Date/Time  <br/> ||会議アイテムが開始された日付と時刻。  <br/> |はい  <br/> |はい  <br/> |
|Meeting_End_Date/Time  <br/> ||会議アイテムが終了した日付と時刻。  <br/> |はい  <br/> |はい  <br/> |
|File_relevance_score  <br/> |関連性  <br/> |関連性スコア (0-100)。 問題ごと。  <br/> |はい  <br/> |はい  <br/> |
|Family_relevance_score  <br/> |関連性  <br/> |最大ファミリの関連性スコア (0-100)。 問題ごと。  <br/> |はい  <br/> |はい  <br/> |
|Relevance_tag  <br/> |関連性  <br/> |関連性のあるファイルに手動でタグ付けされたファイルのタグ付け。 問題ごと。  <br/> |はい  <br/> |はい  <br/> |
|Relevance_load_group  <br/> |関連性  <br/> |問題ごとにフィールドを指定したファイルの関連性負荷グループ。  <br/> |はい  <br/> |はい  <br/> |
|Normalized_relevance_score  <br/> |関連性  <br/> |正規化された関連性スコア (0-100)。これは、問題と負荷の間で比較できます。  <br/> |はい  <br/> |はい  <br/> |
|Marked_as_seed  <br/> |関連性  <br/> |ファイルのタグ付け (issue/category ごとに関連するシードファイルとして設定されている場合)。  <br/> |はい  <br/> |はい  <br/> |
|Marked_as_pre タグ付き  <br/> |関連性  <br/> |ファイルのタグ付け (issue/category ごとに関連性のあるタグ付け済みとして設定されている場合)。  <br/> |はい  <br/> |はい  <br/> |
|Relevance_status_description  <br/> |関連性  <br/> |関連性状態の説明。  <br/> |はい  <br/> |はい  <br/> |
|Comment  <br/> |全般  <br/> |ユーザーによって入力されたコメント。  <br/> |はい  <br/> |はい  <br/> |
|Export_input_path  <br/> |Processing  <br/> |入力パスをエクスポートします。  <br/> |はい  <br/> |はい  <br/> |
|Pivot_ID  <br/> |重複の近似  <br/> |ファイルのピボット ID。  <br/> |はい  <br/> |はい  <br/> |
|Family_size  <br/> |Processing  <br/> |ファミリ内のファイルの数。  <br/> |はい  <br/> |はい  <br/> |
|Native_type  <br/> |Processing  <br/> |ネイティブファイルの種類。 たとえば、スプレッドシートやプレゼンテーションなどです。  <br/> |はい  <br/> |はい  <br/> |
|Native_MD5  <br/> |Processing  <br/> |ネイティブファイルの MD5 ハッシュ値。  <br/> |はい  <br/> |はい  <br/> |
|Native_size  <br/> |Processing  <br/> |ネイティブファイルサイズ。  <br/> |はい  <br/> |はい  <br/> |
|Native_extension  <br/> |Processing  <br/> |ネイティブファイル拡張子。  <br/> |はい  <br/> |はい  <br/> |
|Doc_date_modified  <br/> |ドキュメントのプロパティ  <br/> |日付ネイティブファイルが変更されたので、ファイルのメタデータから取得しました。  <br/> |はい  <br/> |はい  <br/> |
|Doc_date_created  <br/> |ドキュメントのプロパティ  <br/> |ファイルのメタデータから取得した、日付のネイティブファイルが作成されました。  <br/> |はい  <br/> |はい  <br/> |
|Doc_modified_by  <br/> |ドキュメントのプロパティ  <br/> |ファイルのメタデータから取得した、ネイティブファイルを変更したユーザー。  <br/> |はい  <br/> |はい  <br/> |
|O365_date_modified  <br/> |ドキュメントのプロパティ  <br/> |日付ネイティブファイルが変更されました。 SharePoint または Exchange フィールドのいずれかを使用します。  <br/> |はい  <br/> |はい  <br/> |
|O365_date_created  <br/> |ドキュメントのプロパティ  <br/> |日付ネイティブファイルが作成されました。これは、SharePoint または Exchange フィールドから取得されます。  <br/> |はい  <br/> |はい  <br/> |
|O365_modified_by  <br/> |ドキュメントのプロパティ  <br/> |SharePoint または Exchange のいずれかのフィールドから取得した、ネイティブファイルを最後に変更したユーザー。  <br/> |はい  <br/> |はい  <br/> |
|Compound_path  <br/> |Processing  <br/> |複合ソースを含むネイティブファイルパス。  <br/> |はい  <br/> |はい  <br/> |
|Input_path  <br/> |Processing  <br/> |入力ファイルのパス。  <br/> |はい  <br/> |はい  <br/> |
|Input_date_modified  <br/> |Processing  <br/> |日付入力ファイルが最後に変更されました。  <br/> |はい  <br/> |はい  <br/> |
|ND_ET_sort_excl_attach  <br/> |分析  <br/> |校閲用の電子メールセットと ND セットの連結。 ' D ' は ND セットにプレフィックスとして追加され、"E" が電子メールセットに追加されます。  <br/> |はい  <br/> |はい  <br/> |
|ND_ET_sort_incl_attach  <br/> |分析  <br/> |電子メールセットとレビュー用の ND セットの連結は、ND セットにプレフィックスとして追加され、"E" が電子メールセットに追加されます。 さらに、Email_set 内の各電子メールの後に適切な添付ファイルが続きます。  <br/> |はい  <br/> |はい  <br/> |
|Deduped_custodians  <br/> |全般  <br/> |保管担当者の duped ファイル  <br/> |はい  <br/> |はい  <br/> |
|Deduped_file_IDs  <br/> |全般  <br/> |Duped ファイルの Id  <br/> |はい  <br/> |はい  <br/> |
|Deduped_paths  <br/> |全般  <br/> |Duped ファイルのパス  <br/> |はい  <br/> |はい  <br/> |
|File_key  <br/> |全般  <br/> |今後の使用のための内部識別子。  <br/> |はい  <br/> |はい  <br/> |
|Export_native_path  <br/> |Processing  <br/> |エクスポートパッケージ内のネイティブファイルのパス。  <br/> |はい  <br/> |はい  <br/> |
|Extracted_text_path  <br/> |Processing  <br/> |抽出されたファイルのパス。  <br/> |はい  <br/> |はい  <br/> |
|Process_batch  <br/> |Processing  <br/> |インポートバッチのバッチ識別子。  <br/> |はい  <br/> |はい  <br/> |
|Process_status_ID  <br/> |Processing  <br/> |プロセスステージの状態を表す識別子。  <br/> |はい  <br/> |はい  <br/> |
|Process_status_description  <br/> |Processing  <br/> |プロセスステージの状態の説明: 成功またはエラーの説明。  <br/> |はい  <br/> |はい  <br/> |
|Export_status_ID  <br/> |Processing  <br/> |エクスポートの状態の ID。  <br/> |はい  <br/> |はい  <br/> |
|Export_status_description  <br/> |Processing  <br/> |エクスポートの状態の説明。成功またはエラーの説明。  <br/> |はい  <br/> |はい  <br/> |
|Read_percent  <br/> |関連性  <br/> |読み取り% (0-100)。 問題ごと。  <br/> |はい  <br/> |はい  <br/> |
|Doc_author  <br/> |ドキュメント プロパティ  <br/> |ドキュメントのプロパティ: 作成者。  <br/> |いいえ  <br/> |はい  <br/> |
|Doc_comments  <br/> |ドキュメント プロパティ  <br/> |ドキュメントのプロパティ: コメント。  <br/> |いいえ  <br/> |はい  <br/> |
|Doc_keywords  <br/> |ドキュメント プロパティ  <br/> |ドキュメントのプロパティ: キーワード。  <br/> |いいえ  <br/> |はい  <br/> |
|Doc_last_saved_by  <br/> |ドキュメント プロパティ  <br/> |ドキュメントのプロパティ: 最終保存者。  <br/> |いいえ  <br/> |はい  <br/> |
|Doc_revision  <br/> |ドキュメント プロパティ  <br/> |ドキュメントのプロパティ: リビジョン番号。  <br/> |いいえ  <br/> |はい  <br/> |
|Doc_subject  <br/> |ドキュメント プロパティ  <br/> |ドキュメントのプロパティ: subject。  <br/> |いいえ  <br/> |はい  <br/> |
|Doc_template  <br/> |ドキュメント プロパティ  <br/> |ドキュメントのプロパティ: テンプレート。  <br/> |いいえ  <br/> |はい  <br/> |
|Doc_title  <br/> |ドキュメント プロパティ  <br/> |ドキュメントのプロパティ: title。  <br/> |いいえ  <br/> |はい  <br/> |
|Email_has_attachment  <br/> |Email  <br/> |電子メールに1つ以上の添付ファイルがあるかどうかを示します。  <br/> |いいえ  <br/> |はい  <br/> |
|Email_importance  <br/> |Email  <br/> |電子メールの重要度プロパティ。  <br/> |いいえ  <br/> |はい  <br/> |
|Email_level  <br/> |Email  <br/> |電子メールスレッド内の電子メールレベルを示します。 添付ファイルの場合は、添付された電子メールの値。  <br/> |いいえ  <br/> |はい  <br/> |
|Email_recipients  <br/> |Email  <br/> |電子メール受信者の名前またはアドレス (宛先、CC、および BCC)。  <br/> |いいえ  <br/> |はい  <br/> |
|Email_security  <br/> |Email  <br/> |電子メールのセキュリティプロパティ。  <br/> |いいえ  <br/> |はい  <br/> |
|Email_sensitivity  <br/> |Email  <br/> |電子メールの秘密度のプロパティ。  <br/> |いいえ  <br/> |はい  <br/> |
|Export_batch  <br/> |Processing  <br/> |ファイルの最終エクスポートバッチ名。  <br/> |いいえ  <br/> |はい  <br/> |
|Export_session  <br/> |Processing  <br/> |ファイルの最終エクスポートセッション Id (日付を含む)。  <br/> |いいえ  <br/> |はい  <br/> |
|Extracted_text_length  <br/> |Processing  <br/> |抽出されたテキストファイルの文字の長さ。  <br/> |いいえ  <br/> |はい  <br/> |
|Family_duplicate_set  <br/> |Processing  <br/> |完全なテキストの重複があるファミリの数値識別子 (それぞれのファミリのすべてのメンバーは完全に重複しています)。  <br/> |いいえ  <br/> |はい  <br/> |
|Has_Text  <br/> |Processing  <br/> |ファイルにテキストがあるかどうかを示します。 0-いいえ。1-はい。  <br/> |いいえ  <br/> |はい  <br/> |
|Input_file_ID  <br/> |Processing  <br/> |ファイルの抽出元の入力ファイルの ID。  <br/> |いいえ  <br/> |はい  <br/> |
|Native_SHA_256  <br/> |Processing  <br/> |SHA-256 ネイティブファイルのハッシュ値。  <br/> |いいえ  <br/> |はい  <br/> |
|O365_authors  <br/> |ドキュメント プロパティ  <br/> |SharePoint または Exchange のいずれかのフィールドから取得した、ネイティブファイルを変更したユーザー。  <br/> |いいえ  <br/> |はい  <br/> |
|O365_created_by  <br/> |ドキュメント プロパティ  <br/> |ネイティブファイルを作成したユーザー。 SharePoint または Exchange のいずれかのフィールドから取得されます。  <br/> |いいえ  <br/> |はい  <br/> |
|Parent_node  <br/> |Email  <br/> |電子メールスレッド内のノードを、リンクがない最も近い親ノードに関連付けます。  <br/> |いいえ  <br/> |はい  <br/> |
|Set_order_inclusives_first  <br/> |Email  <br/> |メールと添付ファイル: 時系列順 (Inclusives first)。 ドキュメント: 最初にピボットと rest を類似性スコアで降順に並べ替えます。  <br/> |いいえ  <br/> |はい  <br/> |
|Tagged_By  <br/> |関連性  <br/> |特定の問題に関連するファイルをタグ付けしたユーザー。  <br/> |いいえ  <br/> |はい  <br/> |
|Word_count  <br/> |分析  <br/> |文書内の単語数を指定します。  <br/> |いいえ  <br/> |はい  <br/> |
|||||||||||
||||||
||||||
   
## <a name="related-topics"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[高度な電子情報開示を使用してケースデータをエクスポートする](export-case-data-in-advanced-ediscovery.md)
  
[結果のエクスポート](export-results-in-advanced-ediscovery.md)
  
[バッチ履歴の表示と過去の結果のエクスポート](view-batch-history-and-export-past-results.md)
  

