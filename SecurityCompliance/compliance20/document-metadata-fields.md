---
title: 高度な電子情報開示のドキュメントメタデータフィールド
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e45400726537a3b1ebadcc3d828d9cb8110e2100
ms.sourcegitcommit: 09fd88272187f82b6e635af83edabea08c2cc49c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884755"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>高度な電子情報開示のドキュメントメタデータフィールド

次の表は、高度な電子情報開示のケースにおけるレビューセット内のドキュメントのメタデータフィールドの一覧です。 テーブルには、メタデータフィールドの名前、検証セットでクエリを実行するときにフィールドを検索できるかどうか、または、選択したドキュメントのファイルメタデータを校閲セットに表示するときにフィールドが存在するかどうか、およびそのフィールドがドキュメントに含まれているかどうかが示されます。再エクスポート済み。

| フィールド名 | 検索可能なフィールド名 | エクスポートされたフィールド名 | 表示フィールド名 | 説明 |
| :- |  :- |  :- |  :- |  :- |
| 添付ファイルのコンテンツ Id | AttachmentContentId |  | 添付ファイルのコンテンツ Id | アイテムの添付ファイルのコンテンツ Id。 |
| 添付ファイル名 | AttachmentNames | Attachment_Names | 添付ファイル名 | 添付ファイルの名前の一覧。 |
| 弁護士クライアント特権スコア | AttorneyClientPrivilegeScore |  | 弁護士クライアント特権スコア | 委任状-クライアント特権モデルのコンテンツスコア。 |
| 設定元 | 設定元 | Doc_authors | 設定元 | ドキュメントのメタデータから作成します。 |
| BCC | BCC | Email_bcc | BCC | メッセージの種類の場合は、[Bcc] フィールド。  表示形式**は\<DisplayName SMTPAddress>** です。 |
| CC | CC | Email_cc | CC | メッセージの種類の Cc フィールド。  表示形式**は\<DisplayName SMTPAddress>** です。 |
| コンプライアンスラベル | ComplianceLabels | Compliance_labels | コンプライアンスラベル | Office 365 で適用されるコンプライアンスラベル |
| 複合パス | CompoundPath | Compound_path | 複合パス | アイテムのソースを記述する、人間が判読できるパス。 |
| コンテンツ | コンテンツ |  |  | アイテムの抽出されたテキスト。 |
| 会話本文 | 会話本文 |  | 会話本文 | アイテムの会話本文。 |
| 会話のトピック | 会話のトピック |  | 会話のトピック | アイテムの会話のトピック。 |
| 会話 ID | ConversationId | Conversation_ID | 会話 ID | メッセージからの会話 Id。 |
| 会話インデックス |  | Conversation_index | 会話インデックス | メッセージからの会話インデックス。 |
| 会話 Pdf の時間 | ConversationPdfTime |  | 会話 Pdf の時間 | 会話の PDF 版が作成された日付。 |
| 会話の墨消しの書き込み時間 | ConversationRedactionBurnTime |  | 会話の墨消しの書き込み時間 | 会話の PDF 版がチャット用に作成された日付。 |
| 文書作成日 | CreatedTime | Doc_date_created | 文書作成日 | ドキュメントのメタデータから日付を作成します。 |
| Custodian | Custodian | Custodian | Custodian | アイテムが関連付けられていた保管担当者の名前。 |
| 日付 | 日付 | 日付 | 日付 | 日付は、ファイルの種類に応じた計算フィールドです。<br />**メール**: 送信日<br />**電子メールの添付ファイル**: ドキュメントの最終更新日。利用できない場合は、親の送信日<br />**埋め込ま**れたドキュメント: ドキュメントの最終更新日。利用できない場合は、親の最終変更日です。<br />**Spo ドキュメント (モダン添付ファイルを含む)**: SharePoint の最終更新日 (利用できない場合)、ドキュメントの最終変更日<br />**Office 以外のドキュメント**: 最終変更日<br />**会議**: 会議の開始日<br />**ボイスメール**: 送信日<br />**IM**: 送信日。 |
| その他のパス | Dedupedcompoundpath | Deduped_compound_path | その他のパス | 完全に重複しているドキュメント (コンテンツ、ドキュメントに基づいた電子メール: ハッシュに基づく) の複合パスのリスト。 |
| その他の保管担当者 | DedupedCustodians | Deduped_custodians | その他の保管担当者 | 完全に重複しているドキュメントの保管担当者 (コンテンツに基づく、ドキュメントの場合はハッシュに基づく) の一覧。 |
| その他のファイル Id | DedupedFileIds | Deduped_file_IDs | その他のファイル Id | 完全に重複しているドキュメント (コンテンツに基づく、ドキュメントの場合はハッシュに基づく) のファイル Id のリスト。 |
| ドキュメントコメント | DocComments | Doc_comments | ドキュメントコメント | ドキュメントのメタデータからのコメント。 |
| ドキュメント会社 |  | Doc_company | ドキュメント会社 | ドキュメントメタデータからの会社。 |
| DocIndex |  |  |  | ファミリ内のインデックス。 -1 または0は、それがルートであることを意味します。 |
| ドキュメントのキーワード |  | Doc_keywords | ドキュメントのキーワード | ドキュメントのメタデータからのキーワード。 |
| ドキュメントの更新者 |  | Doc_modified_by | ドキュメントの更新者 | ドキュメントメタデータからの最終更新日。 |
| ドキュメントのリビジョン |  | Doc_revision | ドキュメントのリビジョン | ドキュメントのメタデータからのリビジョン。 |
| ドキュメントの件名 |  | Doc_subject | ドキュメントの件名 | ドキュメントのメタデータの件名。 |
| ドキュメント テンプレート |  | Doc_template | ドキュメント テンプレート | ドキュメントのメタデータからのテンプレート。 |
| 基準となるテーマ | DominantTheme | Dominant_theme | 基準となるテーマ | 分析に対して計算された、基準となるテーマ。 |
| サブセットの複製 |  | Duplicate_subset | サブセットの複製 | 完全に重複した場合のグループ ID。 |
| EmailAction |  | Email_action |  | なし、返信、メッセージの件名行に基づいて転送します。 |
| 電子メール配信確認 |  | Email_delivery_receipt | 電子メール配信確認 | 配信確認のためにインターネットヘッダーで提供される電子メールアドレス。 |
| Importance | EmailImportance | Email_importance | Importance | メッセージの重要度: **0**: 低。**1**: 標準**2**: 高 |
| EmailLevel |  | Email_level |  | 属する電子メールスレッド内のメッセージレベルを示します。添付ファイルは親メッセージの値を継承します。 |
| 電子メールメッセージ Id |  | Email_message_ID | 電子メールメッセージ Id | メッセージのインターネットメッセージ Id。 |
| EmailReadReceipt |  | Email_read_receipt |  | 開封確認のためにインターネットヘッダーで提供される電子メールアドレス。 |
| 電子メールのセキュリティ | EmailSecurity | Email_security | 電子メールのセキュリティ | メッセージのセキュリティ設定: **0**: なし。**1**: 署名されています。**2**: 暗号化されています。**3**: 暗号化して署名します。 |
| メールの秘密度 | 電子メールの秘密度 | email_sensitivity | メールの秘密度 | メッセージの秘密度設定: **0**: なし。**1**: Personal。**2**: プライベート。**3**: 社外秘。 |
| メールセット | EmailSet | Email_set | メールセット | 同じメールセット内のすべてのメッセージのグループ ID。 |
| EmailThread |  | Email_thread |  | メールセット内のメッセージの位置。ルートから現在のメッセージまでのすべてのノード Id をピリオドで区切って構成します。 |
| 抽出されたコンテンツタイプ |  | Extracted_content_type | 抽出されたコンテンツタイプ | 抽出されたコンテンツタイプ (mime タイプの形式)。たとえば、image/jpeg。 |
| ExtractedTextLength |  | Extracted_text_length |  | 抽出した文字列の文字数を指定します。 |
| ファミリー関連性スコアケース問題1 |  | Family_relevance_score_case_issue_1 |  | 関連性のない家族の関連性スコアケースの問題1。 |
| FamilyDuplicateSet |  | Family_duplicate_set |  | 相互に正確に重複するファミリの数値識別子 (同じコンテンツとすべて同じ添付ファイル)。 |
| ファミリ ID | FamilyId | Family_ID | ファミリ ID | ファミリ Id はすべてのアイテムをグループにまとめます。電子メールの場合、これにはメッセージとすべての添付ファイルが含まれます。ドキュメントの場合は、ドキュメントと埋め込みアイテムが含まれます。 |
| ファミリーサイズ |  | Family_size | ファミリーサイズ | ファミリ内のドキュメントの数。 |
| ファイル関連性スコアケース問題1 |  | File_relevance_score_case_issue_1 |  | 関連性のないファイル関連性スコアケース問題1。 |
| File クラス | FileClass | File_class | File クラス | SharePoint および OneDrive のコンテンツの場合:**ドキュメント**;Exchange からのコンテンツ:**電子メール**または**添付ファイル**。 |
| ファイル ID | FileId | File_ID | ファイル ID | ケース内で一意のドキュメント識別子。|
| 作成されたファイルシステムの日付 |  | File_system_date_created | 作成されたファイルシステムの日付 | ファイルシステムから作成された日付 (Office 以外の365データにのみ適用されます)。 |
| ファイルシステムの日付が変更されました |  | File_system_date_modified | ファイルシステムの日付が変更されました | ファイルシステムからの変更日付 (Office 以外の365データにのみ適用されます)。 |
| ファイルの種類 | FileType |  | ファイルの種類 | ファイル拡張子に基づいて、アイテムのファイルの種類。 |
| 添付ファイルあり | HasAttachment | Email_has_attachment | 添付ファイルあり | メッセージに添付ファイルがあるかどうかを示します。 |
| 弁護士 | HasAttorney |  | 弁護士 | True の場合、少なくとも1人の参加者が弁護士リストに含まれています。それ以外の場合、値は False になります。 |
| HasText |  | Has_text |  | アイテムにテキストが含まれているかどうかを示します。可能な値は True と False です。 |
| 不変 ID | ImmutableId | Immutable_ID | 不変 ID | Office 365 に格納されている不変 Id。 |
| 包括型 | InclusiveType | Inclusive_type | 包括型 | 分析に対して計算される包括型: **0** -包括的ではありません。**1** -包含;**2** -包括負;**3** -包括的コピー。 |
| [返信先 Id |  | In_reply_to_ID | [返信先 Id | [メッセージの返信先 Id。 |
| 担当者 | IsRepresentative 者 | Is_representative | 担当者 | 完全に重複したすべてのセットに含まれる1つのドキュメントは、担当者としてマークされます。 |
| アイテム クラス | ItemClass | Item_class | アイテム クラス | Exchange server によって提供される Item クラス。たとえば、 **IPM.メモ** |
| Last modified date | LastModifiedDate | Doc_date_modified | Last modified date | ドキュメントメタデータからの最終変更日。 |
| ロード ID | LoadId | Load_ID | ロード ID | 読み込み Id。アイテムがレビューセットに読み込まれています。 |
| 場所 | 場所 | 場所 | 場所 | ドキュメントのソースとなる場所の種類を示す文字列。<br />_GT_ 以外のインポートされたデータ<br />Teams-> Teams<br />EXO-> Exchange<br />SPO-> SharePoint<br />OneDrive for Business-> OneDrive |
| 場所の名前 | Msrtcsip-locationname | Location_name | 場所の名前 | アイテムのソースを識別する文字列。  Exchange の場合、これはメールボックスの SMTP アドレスになります。  SharePoint および OneDrive の場合、サイトコレクションの URL。 |
| 担当者としてマーク | MarkAsRepresentative |  | 担当者としてマーク | 正確な重複のセットごとに1つのドキュメントが担当者としてマークされます。 |
| プリタグ付きケースの問題としてマークされています1 |  | Marked_as_pre_tagged_Case_issue_1 |  | 関連性のない、タグ付きケースの問題1としてマークされました。 |
| シードケースの問題1としてマークされています |  | Marked_as_seed_Case_issue_1 |  | シードケース問題1と関連性があるとマークされています。 |
| 会議の終了日 | 会議の終了日 | Meeting_end_date | 会議の終了日 | 会議の会議の終了日。 |
| 会議の開始日 | 会議の開始日 | Meeting_start_date | 会議の開始日 | 会議の会議の開始日。 |
| メッセージの種類 | MessageKind | Message_kind | メッセージの種類 | 検索するメッセージの種類を示します。<br />可能な値: <br />contacts <br />docs <br />email <br />externaldata <br />faxes <br />im <br />journals <br />meetings <br />Microsoft teams (Microsoft Teams でチャット、会議、通話のアイテムを返す) <br />notes <br />posts <br />rssfeeds <br />tasks <br />voicemail |
| ネイティブ拡張機能 | /モジュール | Native_extension | ネイティブ拡張機能 | アイテムのネイティブな内線番号。 |
| ネイティブファイル名 | ファイル名 | Native_file_name | ネイティブファイル名 | アイテムのネイティブファイル名。 |
| NativeMD5 |  | Native_MD5 |  | ファイルストリームの MD5 ハッシュ。 |
| ND/ET 並べ替え: 添付ファイルを除外する | NdEtSortExclAttach | ND_ET_sort_excl_attach | ND/ET 並べ替え: 添付ファイルを除外する | レビュー時に効率的に並べ替えるための電子メールセットと ND セットの連結。D が ND セットにプレフィックスとして追加され、E が電子メールセットに追加されます。 |
| ND/ET ソート: 添付ファイルを含む | NdEtSortInclAttach | ND_ET_sort_incl_attach | ND/ET ソート: 添付ファイルを含む | レビュー時に効率的に並べ替えるための電子メールセットと ND セットの連結。D が ND セットにプレフィックスとして追加され、E が電子メールセットに追加されます。 メールセット内の各電子メールの後に、適切な添付ファイルが続きます。 |
| 正規化関連性スコアケース問題1 |  | Normalized_relevance_score_case_issue_1 |  | 関連性から正規化された関連性スコアケースの問題1。 |
| O365 作成者 |  | O365_authors | O365 作成者 | SharePoint からの作成者。 |
| O365 の作成者 |  | O365_created_by | O365 の作成者 | SharePoint から作成されました。 |
| O365 の作成日 |  | O365_date_created | O365 の作成日 | SharePoint から作成された日付。 |
| O365 日付が変更されました |  | O365_date_modified | O365 日付が変更されました | SharePoint から最終変更された日付。 |
| O365 更新者 |  | O365_modified_by | O365 更新者 | SharePoint から更新しました。 |
| 親 ID | ParentId | Parent_ID | 親 ID | アイテムの親の Id。 |
| ParentNode |  | Parent_node |  | 電子メールスレッド内の最も近い先行電子メールメッセージ。 |
| 親パス | ParentPath | Parent_path | 親パス | アイテムの直接の親の複合パス。 |
| 参加者のドメイン | ParticipantDomains | Email_participant_domains | 参加者のドメイン | メッセージの参加者のすべてのドメインの一覧。 |
| 参加者 | 参加者 | Email_participants | 参加者 | メッセージのすべての参加者のリスト。たとえば、[送信者]、[宛先]、[Cc]、[Bcc] などです。 |
| ピボット ID | PivotId | Pivot_ID | ピボット ID | ピボットの ID。 |
| 潜在的に権限のある | PotentiallyPrivileged | Potentially_privileged | 潜在的に権限のある | ドキュメントが権限を持つ可能性があると見なされるようにする場合は True、委任状の特権検出モデル |
| 処理状態 | ProcessingStatus | Error_code | 処理状態 | アイテムが校閲セットに追加された後の処理状態。 |
| 読み取り率の問題1 |  | Read_percent_Case_issue_1 |  | 関連性からパーセンテージケース1を読み取ります。 |
| 閲覧の百分位 | ReadPercentile 位 |  | 閲覧の百分位 | 関連性に基づいてドキュメントの百分位を読み取ります。 |
| 受信者の数 |  | Recipient_count | 受信者の数 | メッセージ内の受信者の数。 |
| 受信者のドメイン | 受信者ドメイン | Email_recipient_domains | 受信者のドメイン | メッセージの受信者のすべてのドメインの一覧。 |
| 受信者 | 受信者 | Email_recipients | 受信者 | メッセージのすべての受信者のリスト (宛先、Cc、Bcc)。 |
| 関連性負荷グループケースの問題1 |  | Relevance_load_group_case_issue_1 |  | 関連性からの関連性負荷グループケースの問題1。 |
| 関連性状態の説明ケース問題1 |  | Relevance_status_description_Case_issue_1 |  | 関連性の状態に関する説明ケース問題1。 |
| 関連性タグケースの問題1 |  | Relevance_tag_case_issue_1 |  | 関連性が関連性のある関連性タグケースの問題1。 |
| 関連性のコメント |  | Relevance_comment | 関連性のコメント | [コメント] フィールドが関連性から出ます。 |
| 関連性スコア | RelevanceScore |  | 関連性スコア | 関連性に基づいたドキュメントの関連性スコア。 |
| 関連性タグ | RelevanceTag |  | 関連性タグ | 関連性に基づいたドキュメントの関連性スコア。 |
| 代表 ID | RepresentativeId |  | 代表 ID | 正確な重複の各セットの数値識別子。 |
| Sender | Sender | Email_sender | Sender | メッセージの種類の Sender (差出人) フィールド。  表示形式**は\<DisplayName SmtpAddress>** です。 |
| 送信者/作成者 | SenderAuthor |  | 送信者/作成者 | アイテムの送信者または作成者から構成される集計フィールド。 |
| 送信者ドメイン | SenderDomain | Email_sender_domain | 送信者ドメイン | 送信者のドメイン。 |
| 送信日時 | 送信日時 | Email_date_sent | 送信日時 | メッセージの送信日。 |
| 順序の設定: 最初を含む | SetOrderInclusivesFirst | Set_order_inclusives_first | 順序を最初に設定します。 | フィールドの並べ替え-電子メールと添付ファイル: カウンター-時系列、ドキュメント: ピボット最初、類似性スコア、降順。 |
| SimilarityPercent |  | Similarity_percent |  | オブジェクトがほぼ重複している場合のピボットの類似点を示します。 |
| ネイティブファイルサイズ | サイズ | Native_size | ネイティブファイルサイズ | ネイティブアイテムのバイト数。 |
| 件名 | 件名 | Email_subject | 件名 | メッセージの件名。 |
| 件名/タイトル | SubjectTitle |  | 件名/タイトル | アイテムの件名またはタイトルから構成される集計フィールド。 |
| ケースの問題1のタグ付き |  | Tagged_by_Case_issue_1 |  | このドキュメントに関連するケースの問題1に対してタグ付けされたユーザー。 |
| タグ | タグ | タグ | タグ | レビューセットで適用されるタグ。 |
| テーマリスト | テーマ一覧 | Themes_list | テーマリスト | 分析に対して計算されたテーマのリスト。 |
| タイトル | タイトル | Doc_title | タイトル | ドキュメントのメタデータからのタイトル。 |
| 宛先 | 宛先 | Email_to | 宛先 | To フィールドをメッセージの種類として入力します。  DisplayName の形式は**DisplayName\<SmtpAddress>** |
| メールセット内で一意 | UniqueInEmailSet |  | メールセット内で一意 | 電子メールセットに添付ファイルが重複している場合は False。 |
| 修復されました | (修復) | Was_Remediated | 修復されました | アイテムが修復された場合は True、それ以外の場合は False。 |
| 文字カウント | WordCount | Word_count | 文字カウント | アイテム内の単語数。 |
||||||

  > [!NOTE]
  > Office 365 を直接検索する場合の検索可能フィールドの詳細については、「[コンテンツ検索のキーワードクエリと検索条件](https://docs.microsoft.com/en-us/office365/securitycompliance/keyword-queries-and-search-conditions)」を参照してください。