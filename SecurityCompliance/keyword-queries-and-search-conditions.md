---
title: コンテンツ検索のキーワード クエリと検索条件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.SearchQueryLearnMore
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
description: 'Exchange Online メールボックスおよび SharePoint と OneDrive を検索するには Office 365 のセキュリティ コンテンツの検索ツールを使用してビジネス サイトの電子メールとファイルのプロパティの詳細については&amp;コンプライアンス センターです。  '
ms.openlocfilehash: c1b5c3721a892929535a7e699201d0bcfc39937b
ms.sourcegitcommit: a2afa4c06e9b762cf689b0d2a0653076f9b00c49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2019
ms.locfileid: "28328163"
---
# <a name="keyword-queries-and-search-conditions-for-content-search"></a>コンテンツ検索のキーワード クエリと検索条件

Exchange のオンライン ドキュメントを SharePoint に保存されている電子メール アイテムを検索することができます電子メールとドキュメントのプロパティについて説明し、Office 365 のセキュリティ コンテンツの検索機能を使用してサイトのビジネスのための OneDrive&amp;コンプライアンスセンターです。使用することも、 ** \*- ComplianceSearch**セキュリティのコマンドレット&amp;コンプライアンス センター PowerShell のこれらのプロパティを検索します。についても説明します。   
  
- ブール検索演算子、検索条件、およびその他の検索クエリの手法を使用して、検索結果を絞り込みます。
    
- 機密性の高いデータ型と SharePoint およびビジネスのための OneDrive でのカスタムの機密性の高いデータ型を検索します。
    
- 組織外のユーザーと共有されているサイトのコンテンツを検索します。
    
コンテンツの検索を作成する方法の詳細については、 [Office 365 でのコンテンツの検索](content-search.md)を参照してください。 |

  
> [!NOTE]
> コンテンツのセキュリティの検索&amp;コンプライアンス センターと、対応する**\*- ComplianceSearch**セキュリティのコマンドレット&amp;コンプライアンス センター PowerShell を使用して、キーワード クエリ言語 (KQL)。詳細な情報は、[キーワード クエリ言語の構文のリファレンス](https://go.microsoft.com/fwlink/?LinkId=269603)を参照してください。 
  
## <a name="searchable-email-properties"></a>検索可能なメール プロパティ

次の表に、電子メール メッセージのプロパティのセキュリティ コンテンツの検索機能を使用して検索できる&amp;コンプライアンス センターまたは**新規 ComplianceSearch**または**セット ComplianceSearch**コマンドレットを使用しています。テーブルには、各プロパティとその説明の例で返される検索結果の_プロパティと値_の構文の例が含まれています。これらを入力することができます`property:value`コンテンツの検索ボックスでキーワードの組み合わせです。 
  
|**プロパティ**|**プロパティの説明**|**例**|**例で返される検索結果**|
|:-----|:-----|:-----|:-----|
|AttachmentNames  <br/> |電子メール メッセージに添付されているファイルの名前。  <br/> |`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual*`  <br/> |annualreport.ppt という名前の添付ファイルのあるメッセージ。2 番目の例では、ワイルドカードを使用して、添付ファイルのファイル名に「annual」の語が含まれるメッセージを返します。  <br/> |
|Bcc  <br/> |メール メッセージの BCC フィールド。<sup>1</sup> <br/> |`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`  <br/> |どの例も Bcc フィールドに「Pilar Pinilla」が含まれているメッセージを返します。  <br/> |
|Category  <br/> | 検索するカテゴリ。カテゴリは、ユーザーが Outlook または Outlook Web アプリを使用して決めることができます。値は次のいずれかです。  <br/><br/>  blue  <br/>  green  <br/>  orange  <br/>  purple  <br/>  red  <br/>  yellow  <br/> |`category:"Red Category"`  <br/> |元のメールボックスで「red」のカテゴリが割り当てられているメッセージ。  <br/> |
|CC  <br/> |メール メッセージの CC フィールド。<sup>1</sup> <br/> |`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`  <br/> |どちらの例も、CC フィールドに Pilar Pinilla が指定されたメッセージ。  <br/> |
|Folderid  <br/> |フォルダーの特定のメールボックスのフォルダー ID (GUID) です。このプロパティを使用する場合に指定したフォルダーが配置されているメールボックスを検索することを確認します。指定したフォルダーのみを検索することに注意してください。フォルダー内のすべてのサブフォルダーは検索されません。フォルダーにサブフォルダーを検索するには、フォルダー Id プロパティを使用して、サブフォルダーを検索するのにする必要があります。<br/> フォルダー Id のプロパティを検索して、特定のメールボックスのフォルダー Id を取得するスクリプトを使用する方法の詳細については、[コレクションの対象となる Office 365 の使用コンテンツの検索](use-content-search-for-targeted-collections.md)を参照してください。  <br/> |`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`  <br/> |最初の例では、指定したメールボックス フォルダー内のすべての項目を返します。2 番目の例では、garthf@contoso.com によって送受信された、指定したメールボックス フォルダー内のすべての項目を返します。  <br/> |
|From  <br/> |メール メッセージの送信者。<sup>1</sup> <br/> |`from:pilarp@contoso.com`  <br/> `from:contoso.com`  <br/> |指定されたユーザーによって送信された、または指定されたドメインから送信されたメッセージ。  <br/> |
|添付ファイルあり  <br/> |メッセージに添付ファイルがあるかどうかを示します。値**true**または**false**を使用します。<br/> |`from:pilar@contoso.com AND hasattachment:true`  <br/> |添付ファイルの指定されたユーザーによって送信されたメッセージです。  <br/> |
|Importance  <br/> |送信者がメッセージを送信するときに指定できる電子メール メッセージの重要度。既定では、送信者が重要度を **high** または **low** に設定していない限り、メッセージは普通の重要度で送信されます。  <br/> |`importance:high`  <br/> `importance:medium`  <br/> `importance:low`  <br/> |高重要度、中重要度、または低重要度とマークされているメッセージ。  <br/> |
|IsRead  <br/> |メッセージが読み取られたかどうかを示します。値**true**または**false**を使用します。<br/> |`isread:true`  <br/> `isread:false`  <br/> |最初の例では、IsRead プロパティを**True**に設定を持つメッセージを返します。2 番目の例では、IsRead プロパティを**False**に設定を持つメッセージを返します。<br/> |
|ItemClass  <br/> |組織が Office 365 にインポートする特定のサード ・ パーティ製データ型を検索するのにには、このプロパティを使用します。このプロパティには、次の構文を使用します。`itemclass:ipm.externaldata.<third-party data type>*` <br/> |`itemclass:ipm.externaldata.Facebook* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter* AND from:"Ann Beebe" AND "Northwind Traders"`  <br/> |最初の例は、[主題] プロパティに"contoso"の単語が含まれている Facebook の項目を返します。2 番目の例では、Ann Beebe が投稿されたことと、キーワード フレーズ「Northwind traders 社」が含まれている Twitter の項目を返します。<br/> ItemClass プロパティのサード ・ パーティ製のデータ型に使用する値の一覧は、 [Office 365 にインポートされたサード ・ パーティ製のデータを検索するコンテンツの検索の使用](use-content-search-to-search-third-party-data-that-was-imported.md)を参照してください。  <br/> |
|Kind  <br/> | 検索する電子メール メッセージの種類。使用可能な値は:  <br/>  contacts  <br/>  docs  <br/>  email  <br/>  externaldata  <br/>  faxes  <br/>  im  <br/>  journals  <br/>  meetings  <br/>  (チャット、会議、およびマイクロソフトのチームでの呼び出しからの項目を返します) microsoftteams  <br/>  notes  <br/>  posts  <br/>  rssfeeds  <br/>  tasks  <br/>  voicemail  <br/> |`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`  <br/> |最初の例では、検索条件に一致する電子メール メッセージを返します。2 番目の使用例を返します。 電子メール メッセージ、インスタント メッセージの会話が (ビジネス会話とマイクロソフトのチームでのチャットの Skype を含む) と、検索条件を満たすメッセージを音声します。3 番目の例では、サード ・ パーティ製データなどのソースから、Twitter、Facebook、および Cisco の Jabber、検索条件を満たす Office 365 のメールボックスにインポートされたアイテムを返します。詳細については、 [Office 365 のサード ・ パーティ製データのアーカイブ](https://go.microsoft.com/fwlink/p/?linkid=716918)を参照してください。<br/> |
|Participants  <br/> |メール メッセージ内のすべての送受信者フィールド。すなわち、From、To、CC、BCC の各フィールドです。<sup>1</sup> <br/> |`participants:garthf@contoso.com`  <br/> `participants:contoso.com`  <br/> |garthf@contoso.com が送信元または送信先のメッセージ。2 番目の例は、contoso.com ドメイン内のユーザーが送信元または送信先のすべてのメッセージを返します。  <br/> |
|Received  <br/> |電子メール メッセージが受信者によって受信された日付。  <br/> |`received:04/15/2016`  <br/> `received>=01/01/2016 AND received<=03/31/2016`  <br/> |2016 年 4 月 15 日に受信したメッセージです。2 番目の例では、2016 年 1 月 1 日、2016 年 3 月 31 日間に受信したすべてのメッセージを返します。  <br/> |
|Recipients  <br/> |メール メッセージ内のすべての受信者フィールド。すなわち、To、CC、BCC の各フィールドです。<sup>1</sup> <br/> |`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`  <br/> |garthf@contoso.com に送信されたメッセージ。2 番目の例では、contoso.com ドメイン内のすべての受信者に送信されたメッセージを返します。  <br/> |
|Sent  <br/> |送信者によって電子メール メッセージが送信された日付。  <br/> |`sent:07/01/2016`  <br/> `sent>=06/01/2016 AND sent<=07/01/2016`  <br/> |指定された日付に送信された、または指定された日付範囲内に送信されたメッセージ。  <br/> |
|Size  <br/> |アイテムのサイズ (バイト数)。  <br/> |`size>26214400`  <br/> `size:1..1048567`  <br/> |25 を超えるメッセージでは [概要] タブMB です。2 番目の例は、1,048,567 バイト (1 MB) のサイズを 1 からのメッセージを返します。  <br/> |
|Subject  <br/> |電子メール メッセージの件名行に含まれるテキスト。  <br/> **注:** サブタイトルのプロパティをクエリで使用するとき、???the の検索には、件名の行に検索対象となるテキストが含まれているすべてのメッセージが返されます。つまり、クエリは、完全に一致するメッセージのみに返しません。検索する場合など、 `subject:"Quarterly Financials"`、「四半期財務 2018」という件名のメッセージ検索結果が含まれます。<br/> |`subject:"Quarterly Financials"`  <br/> `subject:northwind`  <br/> |件名行のテキストの任意の場所に「四半期別財務」「語句を含むメッセージです。2 番目の例では、件名の行に word の northwind が含まれているすべてのメッセージを返します。  <br/> |
|To  <br/> |メール メッセージの To フィールド。<sup>1</sup> <br/> |`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`  <br/> |どの例も、To: 行に「Ann Beebe」が指定されているメッセージを返します。  <br/> |
   
> [!NOTE]
> <sup>1</sup> 、受信者のプロパティの値のすることができますもと呼ばれる*ユーザー プリンシパル名*(UPN)、電子メール アドレスを使用して、名、またはユーザーを指定するエイリアスを表示します。たとえば、Ann Beebe のユーザを指定するのに annb@contoso.com、annb、または「Ann Beebe」を使用することができます。<br/><br/>いずれかを検索するときの受信者のプロパティ (と、Cc、Bcc、参加者、および受信者) では、Office 365 が各ユーザーの id を調べることによって展開しよう Azure Active Directory 内のことです。 Azure Active Directory でユーザーが見つかると場合、クエリを拡張して、ユーザーの電子メール アドレス (または UPN) は、エイリアス、表示名、および legacyexchangedn が渡されます。<br/><br/>など、クエリでは、`participants:ronnie@contoso.com`は、 `participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"`。

## <a name="searchable-site-properties"></a>検索可能なサイトのプロパティ

次の表、SharePoint と OneDrive のいくつかのセキュリティ コンテンツの検索機能を使用して検索可能なプロパティをビジネスの&amp;コンプライアンス センターまたは**新規 ComplianceSearch**または、**を使用してセット ComplianceSearch**コマンドレットです。テーブルには、各プロパティとその説明の例で返される検索結果の_プロパティと値_の構文の例が含まれています。 
  
検索可能な SharePoint プロパティの一覧は、[クロールされ SharePoint 内のプロパティの管理の概要](https://go.microsoft.com/fwlink/p/?LinkId=331599)を参照してください。**[はい]** **Queryable** ] 列に設定されているプロパティを検索できます。 
  
|**プロパティ**|**プロパティの説明**|**例**|**例で返される検索結果**|
|:-----|:-----|:-----|:-----|
|作成者  <br/> |作成者フィールド Office ドキュメントからドキュメントをコピーする場合が引き続き発生します。などのユーザー ドキュメントと電子メールを作成する場合は、SharePoint のドキュメントをアップロードし、他の人にもが保持されます元の作成者です。このプロパティのユーザーの表示名を使用することを確認します。  <br/> |`author:"Garth Fort"`  <br/> |Garth Fort によって作成されたすべてのドキュメント。  <br/> |
|ContentType  <br/> |アイテム、ドキュメント、またはビデオなどの項目の SharePoint コンテンツ タイプです。  <br/> |`contenttype:document`  <br/> |すべてのドキュメントが返されます。  <br/> |
|Created  <br/> |アイテムが作成された日付。  <br/> |`created\>=06/01/2016`  <br/> |2016 年 6 月 1 日以降に作成されたすべてのアイテムです。  <br/> |
|CreatedBy  <br/> |アイテムをアップロードまたは作成する人。このプロパティのユーザーの表示名を使用することを確認します。  <br/> |`createdby:"Garth Fort"`  <br/> |Garth Fort によって作成またはアップロードされたすべてのアイテム。  <br/> |
|DetectedLanguage  <br/> |アイテムの言語。  <br/> |`detectedlanguage:english`  <br/> |英語のすべてのアイテム。  <br/> |
|FileExtension  <br/> |ファイルの拡張子たとえば、docx、1 つ、pptx、または xlsx です。  <br/> |`fileextension:xlsx`  <br/> |すべての Excel ファイル (Excel 2007 およびそれ以降)  <br/> |
|ファイル名  <br/> |ファイルの名前。  <br/> |`filename:"marketing plan"`  <br/> `filename:estimate`  <br/> |最初の例では、タイトルに "marketing plan" と完全一致する語句が含まれるファイルが返されます。2 番目の例では、ファイル名に "estimate" という単語を含むファイルが返されます。  <br/> |
|LastModifiedTime  <br/> |アイテムが最後に変更された日付。  <br/> |`lastmodifiedtime>=05/01/2016`  <br/> `lastmodifiedtime>=05/10/2016 AND lastmodifiedtime<=06/1/2016`  <br/> |最初の例では、2016 年 5 月月 1 日以降に変更されたアイテムを返します。2 番目の例では、2016 5 月 1 日、2016 年 6 月 1 日の間で変更された項目を返します。  <br/> |
|ModifiedBy  <br/> |アイテムを最後に変更した人。このプロパティのユーザーの表示名を使用することを確認します。  <br/> |`modifiedby:"Garth Fort"`  <br/> |Garth Fort によって最後に変更されたすべてのアイテム。  <br/> |
|Path  <br/> |ビジネス サイトの SharePoint または OneDrive 上の特定のフォルダーのパス (URL) です。このプロパティを使用する場合は、指定したフォルダーにあるサイトを検索することを確認します。<br/> [パス] プロパティに指定したフォルダー内のサブフォルダー内にある項目を取得するには、追加する必要が/\* 、指定したフォルダーの URL を例えば`path: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/> **注:** 使用して、 `Path` OneDrive の場所を検索するプロパティが検索結果に、.png、.tiff、または .wav ファイルなどのメディア ファイルを返しません。OneDrive フォルダー内のメディア ファイルを検索する検索クエリに別のサイトのプロパティを使用します。<br/> <br/> 詳細については、Path プロパティを検索し、特定のサイト上のフォルダーのパスの Url を取得するスクリプトを使用して、[コレクションの対象となる Office 365 の使用コンテンツの検索](use-content-search-for-targeted-collections.md)を参照してください。  <br/> |`path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private"`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/*" AND filename:confidential`  <br/> |最初の例では、仕事フォルダーを指定した OneDrive ですべての項目を返します。2 番目の例では、ファイル名に「社外秘」という単語が含まれているサイトが指定したフォルダー (およびすべてのサブフォルダー) 内のドキュメントを返します。  <br/> |
|SharedWithUsersOWSUser  <br/> |指定されたユーザーと共有およびビジネス サイトのユーザーの OneDrive に**私の共有**] ページに表示されているドキュメントです。これらは、共有されている明示的に指定したユーザーと他のユーザーが組織内のドキュメントです。SharedWithUsersOWSUser プロパティを使用する検索クエリに一致するドキュメントをエクスポートする場合は、指定したユーザーとドキュメントを共有するユーザーの元のコンテンツの場所からドキュメントがエクスポートされます。詳細については、[サイトのコンテンツを検索していますが、組織内で共有](keyword-queries-and-search-conditions.md#internal)を参照してください。<br/> |`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`  <br/> |どちらの例は、折笠と明示的に共有されていることと、折笠の**私との共有**ページに表示されるすべての内部文書を返すビジネス アカウント用の OneDrive です。  <br/> |
|Site  <br/> |組織内のサイトかサイトのグループの URL。  <br/> |`site:"https://contoso-my.sharepoint.com"`  <br/> `site:"https://contoso.sharepoint.com/sites/teams"`  <br/> |最初の例は、組織内のすべてのユーザーのためのビジネス サイトの OneDrive からの項目を返します。2 番目の例では、すべてのチーム サイトからアイテムを返します。  <br/> |
|Size  <br/> |アイテムのサイズ (バイト数)。  <br/> |`size>=1`  <br/> `size:1..10000`  <br/> |最初の例では、1 バイトより大きいアイテムが返されます。2 番目の例では、1 ～ 10,000 バイトのサイズのメッセージが返されます。  <br/> |
|Title  <br/> |ドキュメントのタイトルです。Title プロパティは、Microsoft Office ドキュメントで指定されているメタデータです。異なり、ドキュメントのファイル名から。  <br/> |`title:"communication plan"`  <br/> |Office ドキュメントの Title メタデータ プロパティに "communication plan" という語句が含まれるすべてのドキュメント。  <br/> |
   
## <a name="searchable-contact-properties"></a>連絡先のプロパティを検索可能

次の表は、インデックス付けされた連絡先のプロパティとコンテンツの検索を使用して検索することできます。以下は、(個人の連絡先とも呼ばれます) ユーザーのメールボックスの個人用アドレス帳にある連絡先を構成するのにはユーザーの利用可能なプロパティです。連絡先を検索するには、検索、キーワード クエリで 1 つまたは複数の連絡先のプロパティを使用してメールボックスを選択できます。
  
> [!TIP]
> スペースまたは特殊文字が含まれる値を検索するには、二重引用符を使用して、("") には語句を含むたとえば、 `businessaddress:"123 Main Street"`。 
  
|**プロパティ**|**プロパティの説明**|
|:-----|:-----|
|BusinessAddress  <br/> |**勤務先住所**プロパティ内のアドレス。プロパティも、[連絡先のプロパティ] ページで、**勤務**先住所を呼び出されます。<br/> |
|BusinessPhone  <br/> |**勤務先電話番号**のいずれかで電話番号は番号のプロパティです。  <br/> |
|[得意先名]  <br/> |**Company**プロパティの名前です。  <br/> |
|部署  <br/> |**部署**のプロパティの名前です。  <br/> |
|DisplayName  <br/> |連絡先の表示名。これは、連絡先の**完全な名前**のプロパティの名前です。<br/> |
|EmailAddress  <br/> |連絡先の電子メール アドレス プロパティのアドレスです。連絡先の複数の電子メール アドレスを追加できることに注意してください。このプロパティを使用すると、連絡先の電子メール アドレスのいずれかに一致する連絡先が返されます。  <br/> |
|表題  <br/> |**としてファイル**のプロパティです。このプロパティを使用すると、ユーザーの連絡先リストに連絡先を表示する方法を指定します。たとえば、取引先担当者は、 *[部署名]、[氏名]* 、または*姓, 名*として扱われることです。<br/> |
|GivenName  <br/> |**最初の Name**プロパティの名前です。  <br/> |
|かまいません  <br/> |**ホーム**アドレスのプロパティのいずれかのアドレスです。  <br/> |
|HomePhone  <br/> |**自宅**電話番号のいずれかで電話番号は番号のプロパティです。  <br/> |
|IMAddress  <br/> |IM アドレス プロパティは、通常、インスタント メッセージングに使用される電子メール アドレスです。  <br/> |
|ミドル ネーム  <br/> |**中央**の name プロパティの名前です。  <br/> |
|MobilePhone  <br/> |プロパティの番号を**携帯**電話の電話番号にします。  <br/> |
|Nickname  <br/> |プロパティの名前、**ニックネーム**です。  <br/> |
|事業所  <br/> |**Office**または**Office の場所**のプロパティの値です。  <br/> |
|かまいません  <br/> |**その他の**アドレスのプロパティの値です。  <br/> |
|Surname  <br/> |**最後**の name プロパティの名前です。  <br/> |
|役職  <br/> |[**役職**] プロパティのタイトルです。  <br/> |
   

## <a name="searchable-sensitive-data-types"></a>検索可能な機密性の高いデータ型

セキュリティ コンテンツの検索機能を使用することができます&amp;ビジネス サイトの SharePoint と OneDrive のドキュメントに格納されている社会保障番号、クレジット カード番号などの機密性の高いデータを検索するコンプライアンス センターです。使用してこれを行う、`SensitiveType`のキーワード クエリのプロパティは、機密情報の名前を入力します。クエリでは、 `SensitiveType:"Credit Card Number"` 、クレジット カード番号を含むドキュメントが返されます。クエリ`SensitiveType:"U.S. Social Security Number (SSN)"`米国の社会保障番号を含むドキュメントが返されます。**クラス**に機密性の高いデータ型を検索することができますがの一覧を表示するには、 \> 、セキュリティの**機密性の高い情報の種類**&amp;コンプライアンス センターです。**Get DlpSensitiveInformationType**コマンドレットを使用するには、セキュリティまたは&amp;コンプライアンス センター PowerShell の機密性の高い情報の種類の一覧を表示します。 
  
使用することも、 `SensitiveType` (または他の管理者) は、組織用に作成するカスタムの機密性の高い情報の種類の名前を検索するプロパティです。**機密性の高い情報の種類**] ページで、セキュリティ、[**発行元**] 列を使用することができます&amp;組み込みおよびカスタムの依存を区別するためにコンプライアンス センター (または PowerShell の**パブリッシャー**のプロパティ)情報の種類です。詳細については、[機密情報のカスタム タイプを作成する](create-a-custom-sensitive-information-type.md)を参照してください。
  
使用するクエリの作成の詳細については、`SensitiveType`プロパティは、[フォームのサイトに保存された機密データを検索するクエリ](form-a-query-to-find-sensitive-data-stored-on-sites.md)を参照してください。
  
## <a name="search-operators"></a>検索演算子

ブール検索演算子は、 **AND**、 **OR**、および**ない**などを含む、または検索クエリに特定の文字を除外してより正確な検索を定義できます。プロパティの演算子を使用するなど、その他の手法 (次のように\>= や..)、引用符、かっこ、およびワイルドカード、検索クエリを修正するに役立ちます。絞り込んだり、検索結果の範囲を広げるに使用できる演算子を次の表に一覧します。 
  
|**演算子**|**用途**|**説明**|
|:-----|:-----|:-----|
|AND  <br/> |keyword1 AND keyword2  <br/> |指定されたキーワードがすべて含まれている項目を取得または`property:value`式です。たとえば、 `from:"Ann Beebe" AND subject:northwind` 、件名の行に word の northwind が含まれている Ann Beebe によって送信されたすべてのメッセージを返します。<sup>2</sup> <br/> |
|+  <br/> |keyword1 + keyword2 keyword3  <br/> |*いずれか*を含むアイテムを返します。`keyword2`または`keyword3`*と*も含まれている`keyword1`。したがって、次の使用例は、クエリと同じ`(keyword2 OR keyword3) AND keyword1`。  <br/> 注意してクエリ`keyword1 + keyword2`(の後ろのスペースに、**+** シンボル) を使用することとは異なり、* * と * * 演算子です。このクエリと同じことに`"keyword1 + keyword2"`、正確なフェーズでの返品と`"keyword1 + keyword2"`。<br/> |
|OR  <br/> |keyword1 OR keyword2  <br/> |指定されたキーワードのいずれかを含むアイテムを取得または`property:value`式です。<sup>2</sup> <br/> |
|NOT  <br/> |keyword1 NOT keyword2  <br/> NOT from:"Ann Beebe"  <br/> しない種類: im  <br/> |キーワードで指定された項目を除外する、または`property:value`式です。2 番目の例は、Ann Beebe によって送信されたメッセージを除外します。3 番目の例では、Skype の会話の履歴メールボックス フォルダーに保存されているビジネス会話など、インスタント メッセージングの会話を除外します。<sup>2</sup> <br/> |
|-  <br/> |keyword1 -keyword2  <br/> |**NOT**演算子と同じです。このクエリが含まれる項目が返され、`keyword1`を含むアイテムを除外すると、 `keyword2`。<br/> |
|NEAR  <br/> |keyword1 NEAR(n) keyword2  <br/> |N は単語の間隔の数、互いの近くにある単語を持つアイテムを返します。たとえば、 `best NEAR(5) worst` 「最悪」という単語が「最高」の 5 つの単語内では、任意の項目を返します。番号が指定されていない場合は 8 ワードの既定の距離です。<sup>2</sup> <br/> |
|ONEAR  <br/> |keyword1 ONEAR(n) keyword2  <br/> |同様に**近く**、ですが、近くにある他の指定された順序で文字が含まれる項目を返します。たとえば、 `best ONEAR(5) worst` 、「最高」という単語が「最悪」の単語の前に発生して 2 つの単語が互いの 5 つの単語内にある任意の項目を返します。番号が指定されていない場合は 8 ワードの既定の距離です。<sup>2</sup> <br/> > [!NOTE]_gt **ONEAR**演算子には、メールボックスを検索する場合はサポートされていませんそれは、ビジネス サイトの SharePoint と OneDrive を検索するときにのみ機能します。同じ検索で、メールボックス、およびサイトを検索するいるし、 **ONEAR**演算子がクエリに含まれています、 **NEAR**演算子を使用していた場合、検索はメールボックスのアイテムを返します。つまり、検索には、先に指定された単語は互いに近い単語の順序に関係なくアイテムが返されます。           |
|:  <br/> |property:value  <br/> |コロン (:)、`property:value`の構文では、検索対象のプロパティの値に指定された値が含まれているを指定します。たとえば、 `recipients:garthf@contoso.com` garthf@contoso.com に送信されたメッセージを返します。<br/> |
|=  <br/> |property=value  <br/> |**::** の演算子と同じです。  <br/> |
|\<  <br/> |property\<value  <br/> |検索対象のプロパティが指定の値より小さいことを意味します。<sup>1</sup> <br/> |
|\>  <br/> |property\>value  <br/> |検索対象のプロパティが指定の値より大きいことを意味します。<sup>1</sup> <br/> |
|\<=  <br/> |property\<=value  <br/> |検索対象のプロパティが特定の値以下であることを意味します。<sup>1</sup> <br/> |
|\>=  <br/> |property\>=value  <br/> |検索対象のプロパティが特定の値以上であることを意味します。<sup>1</sup> <br/> |
|..  <br/> |プロパティ: 値 1.値 2  <br/> |検索対象のプロパティが value1 以上で value2 以下であることを意味します。<sup>1</sup> <br/> |
|"  "  <br/> |"fair value"  <br/> subject:"Quarterly Financials"  <br/> |二重引用符 () を使用して ("") の正確な語句またはキーワードの用語を検索して`property:value`検索クエリです。  <br/> |
|\*  <br/> |cat\*  <br/> subject:set\*  <br/> |(アスタリスクは、単語の末尾に配置)、プレフィックス ワイルドカード検索はキーワードで 0 個以上の文字の一致または`property:value`クエリします。たとえば、`title:set*`ドキュメントのタイトルの word の設定、セットアップ、設定および「設定」で始まる他の単語) を含むドキュメントを返します。<br/><br/> **注:** プレフィックス ワイルドカード検索のみを使用することができます。たとえば、 **cat\*** または**を設定\***。サフィックスを検索 ( ** \*cat** )、検索を挿入辞 ( **c\*t** )、検索文字列を指定し、( ** \*cat\* ** ) はサポートされていません。           |
|(  )  <br/> | (fair OR free) AND (from:contoso.com)  <br/> (IPO OR initial) AND (stock OR shares)  <br/> (quarterly financials)  <br/> |括弧は、ブール演算子の文字列、 `property:value` アイテム、およびキーワードをグループにまとめます。たとえば、  `(quarterly financials)` は quarterly および financials の語を含むアイテムを返します。  <br/> |
   
> [!NOTE]
> <sup>1</sup>は、日付または数値の値を持つプロパティに対して、この演算子を使用します。<br/> <sup>2</sup>ブール検索演算子は、大文字と小文字である必要があります。など**と**します。など**と**、小文字、演算子を使用する場合は、検索クエリのキーワードとして扱われます。 
  
## <a name="search-conditions"></a>検索条件

検索を絞り込むより洗練された結果セットを返す検索クエリに条件を追加できます。各条件は、KQL 検索クエリが作成され、検索を開始するときに実行するに句を追加します。
  
[共通プロパティの条件 ](#conditions-for-common-properties)

[メール プロパティの条件](#conditions-for-mail-properties)

[ドキュメント プロパティの条件](#conditions-for-document-properties)

[条件で使用する演算子](#operators-used-with-conditions)

[条件を使用するためのガイドライン](#guidelines-for-using-conditions)

[検索クエリでの条件の使用例](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>共通プロパティの条件 

同じ検索で、メールボックス、およびサイトを検索するときに共通のプロパティを使用して条件を作成します。条件を追加するときに使用する利用可能なプロパティを次の表に一覧します。
  
|**条件**|**説明**|
|:-----|:-----|
|日付  <br/> |E メール、メッセージ、日付受信者によって受信されたか、送信者によって送信されました。ドキュメントについては、ドキュメントが最後に修正された日付。  <br/> |
|Sender/Author  <br/> |E メール、メッセージを送信したユーザー。ドキュメントについては、Office ドキュメントから [作成者] フィールドに示されている人です。コンマで区切られた複数の名前を入力できます。2 つ以上の値は、 **OR**演算子で論理的に接続されています。<br/> |
|サイズ (バイト単位)  <br/> |メールとドキュメントのいずれの場合も、アイテムのサイズ (バイト単位)。  <br/> |
|Subject/Title  <br/> |E メール、メッセージの件名行のテキスト。ドキュメントについては、ドキュメントのタイトルです。説明したようは、Title プロパティは、Microsoft Office ドキュメントで指定されているメタデータです。複数のサブジェクトとのタイトルのコンマで区切られた名前を入力することができます。2 つ以上の値は、 **OR**演算子で論理的に接続されています。<br/> |
|コンプライアンス タグ  <br/> |電子メールとドキュメントの両方のラベル ラベル ポリシーによって自動的にメッセージやドキュメントに割り当てられた、またはラベルを付けることをユーザーが手動で割り当てられています。電子メールとデータ管理のためのドキュメントを分類し、ラベルで定義されている分類に基づく保存ルールを適用するラベルを使用します。ラベル名の一部を入力し、ワイルドカードを使用したり、完全なラベル名を入力できます。詳細については、 [Office 365 でのラベルの概要](labels.md)を参照してください。<br/> |
  
### <a name="conditions-for-mail-properties"></a>メール プロパティの条件

メールボックスやパブリック フォルダーを検索する場合は、メール プロパティを使って条件を作成します。条件で使うメール プロパティを次の表に一覧表示します。これらのプロパティは上記で説明されているメール プロパティのサブセットであることに注意してください。これらの説明は、必要に応じて繰り返されます。
  
|**条件**|**説明**|
|:-----|:-----|
|メッセージの種類  <br/> | 検索するメッセージの種類です。これは、プロパティの種類の電子メール プロパティと同じです。使用可能な値は:  <br/><br/>  contacts  <br/>  docs  <br/>  email  <br/>  externaldata  <br/>  faxes  <br/>  im  <br/>  journals  <br/>  meetings  <br/>  microsoftteams  <br/>  notes  <br/>  posts  <br/>  rssfeeds  <br/>  tasks  <br/>  voicemail  <br/> |
|Participants  <br/> |電子メール メッセージ内のすべての送受信者フィールド。すなわち、From、To、CC、および BCC の各フィールドです。  <br/> |
|Type  <br/> |電子メール アイテムのメッセージ クラスのプロパティです。ItemClass email プロパティと同じプロパティは、これ。また、複数値の条件です。複数のメッセージ クラスを選択するために**CTRL**キーを押しながら、条件に追加するドロップダウン リストで 2 つ以上のメッセージ クラス] をクリックします。一覧で選択した各メッセージ クラスは、対応する検索クエリで**OR**演算子で論理的に接続されます。<br/> 一覧については、メッセージ クラス (およびその対応するメッセージ クラス ID) の Exchange で使用されると、[**メッセージ クラス**] ボックスの一覧で選択可能な[項目の種類とメッセージ クラス](https://go.microsoft.com/fwlink/?linkid=848143)を参照してください。  <br/> |
|Received  <br/> |メール メッセージが受信者によって受信された日付。これは、Received メール プロパティと同じプロパティです。  <br/> |
|受信者  <br/> |ユーザーの電子メール メッセージが送信されました。これは、プロパティに電子メールのプロパティと同じです。  <br/> |
|Sender  <br/> |電子メール メッセージの差出人。  <br/> |
|Sent  <br/> |電子メール メッセージが送信者によって送信された日付です。これは、プロパティは、送信された電子メールのプロパティと同じです。  <br/> |
|Subject  <br/> |電子メール メッセージの件名行に含まれるテキスト。  <br/> |
|To  <br/> |電子メール メッセージの受信者。  <br/> |
  
### <a name="conditions-for-document-properties"></a>ドキュメント プロパティの条件

ビジネス サイトの SharePoint と OneDrive のドキュメントを検索するときにドキュメントのプロパティを使用して条件を作成します。条件を使用できるドキュメントのプロパティを次の表に一覧します。これらのプロパティは上記で説明されているサイトのプロパティのサブセットであることに注意してください。これらの説明は、必要に応じて繰り返されます。
  
|**条件**|**説明**|
|:-----|:-----|
|作成者  <br/> |作成者フィールド Office ドキュメントからドキュメントをコピーする場合が引き続き発生します。などのユーザー ドキュメントと電子メールを作成する場合は、SharePoint のドキュメントをアップロードし、他の人にもが保持されます元の作成者です。  <br/> |
|役職  <br/> |ドキュメントのタイトルです。Title プロパティは、Office ドキュメントで指定されているメタデータです。ドキュメントのファイル名とは異なるが。  <br/> |
|Created  <br/> |ドキュメントが作成された日付。  <br/> |
|最終更新日  <br/> |ドキュメントが最後に変更された日付。  <br/> |
|ファイルの種類  <br/> |ファイルの拡張子たとえば、docx、1 つ、pptx、または xlsx です。これは、プロパティ、FileExtension サイトのプロパティと同じです。  <br/> |
  
### <a name="operators-used-with-conditions"></a>条件で使用する演算子

条件を追加するときは、条件のプロパティの種類に関連した演算子を選択します。条件とともに使用される演算子を次の表で説明します。また、検索クエリで使用される同等物の一覧も表示します。
  
|**演算子**|**クエリの同等物**|**説明**|
|:-----|:-----|:-----|
|After  <br/> |`property>date`  <br/> |日付の条件で使用されます。指定された日付の後に送信、受信、変更された項目を返します。   <br/> |
|Before  <br/> |`property<date`  <br/> |日付の条件で使用されます。指定された日付の前に送信、受信、変更された項目を返します。  <br/> |
|Between  <br/> |`date..date`  <br/> |日付とサイズの条件を使用します。日付条件と共に使用するとを返します。 が送信、受信、または変更されました。 指定した日付範囲内にあります。サイズ条件と共に使用すると、サイズの範囲は、指定した項目を返します。  <br/> |
|Contains any of  <br/> |`(property:value) OR (property:value)`  <br/> |文字列値を指定するプロパティの条件を使用します。指定した文字列の値を 1 つ以上の任意の部分が含まれている項目を返します。  <br/> |
|Doesn't contain any of  <br/> |`-property:value`  <br/> `NOT property:value`  <br/> |文字列値を指定するプロパティの条件で使用されます。指定された文字列のどの部分も含まれない項目を返します。  <br/> |
|Doesn't equal any of
  <br/> |`-property=value`  <br/> `NOT property=value`  <br/> |文字列値を指定するプロパティの条件で使用されます。特定の文字列が含まれない項目を返します。  <br/> |
|Equals  <br/> |`size=value`  <br/> |指定されたサイズに等しい項目を返します。<sup>1</sup> <br/> |
|Equals any of  <br/> |`(property=value) OR (property=value)`  <br/> |文字列値を指定するプロパティの条件で使用されます。1 つ以上の指定された文字列の値と完全に一致する項目を返します。  <br/> |
|Greater  <br/> |`size>value`  <br/> |指定されたプロパティが指定された値より大きい項目を返します。<sup>1</sup> <br/> |
|Greater or equal  <br/> |`size>=value`  <br/> |指定されたプロパティが指定された値以上の項目を返します。<sup>1</sup> <br/> |
|Less  <br/> |`size<value`  <br/> |特定の値以上の項目を返します。<sup>1</sup> <br/> |
|Less or equal  <br/> |`size<=value`  <br/> |特定の値以上の項目を返します。<sup>1</sup> <br/> |
|Not equal  <br/> |`size<>value`  <br/> |指定されたサイズと等しくない項目を返します。<sup>1</sup> <br/> |
   
> [!NOTE]
> <sup>1</sup>この演算子は、Size プロパティを使用する条件でのみ使用します。 
  
### <a name="guidelines-for-using-conditions"></a>条件を使用するためのガイドライン

検索条件を使用する際は、以下の点に留意してください。
  
- 条件の論理的な**AND**演算子によってキーワード クエリ ([キーワード] ボックスで指定) に接続します。キーワード クエリと結果に含まれる条件の両方を満たすために項目があることを意味します。これは、結果を絞り込む条件がどのように役立つか。 
    
- (別のプロパティを指定する条件) の検索クエリに 2 つ以上の一意の条件を追加する場合は、 **AND**演算子でこれらの条件が論理的に接続します。つまりだけでなく任意のキーワード クエリでは) すべての条件を満たすアイテムだけが返されます。 
    
- 同じプロパティの 1 つ以上の条件を追加する場合、 **OR**演算子でこれらの条件が論理的に接続します。つまり、キーワード クエリとクエリの条件のいずれかに一致する項目が返されます。**OR**演算子で同じ条件のグループが互いに接続されているし、 **AND**演算子によって、一意の条件のセットを接続します。 
    
- 1 つの条件に複数の値を (カンマまたはセミコロンで区切る) を追加すると、これらの値は**OR**演算子で接続されています。つまり、含まれている場合、条件のプロパティに指定された値のいずれかの項目が返されます。 
    
- **検索**ページで、選択した検索の詳細ウィンドウで [キーワード] ボックスの条件を使用して作成される検索クエリが表示されます。クエリでは、表記の右側にすべての`(c:c)`は、クエリに追加する条件を示します。 
    
- 条件は、検索クエリにプロパティを追加するだけ演算子を追加しません。詳細ウィンドウに表示されているクエリは演算子の右側に表示されない理由は、`(c:c)`表記します。KQL は、論理演算子 (、前に説明した規則に従って) を追加クエリを実行します。 
    
- ドラッグ アンド条件の順序を再シーケンスへのコントロールをドロップすることができます。条件のコントロールをクリックし、上または下に移動するだけです。
    
- いくつかの条件のプロパティでは、前に説明したように複数の値を入力できます。各値は、 **OR**演算子で論理的に接続されています。これは、結果、同じ条件の複数のインスタンスを持つ単一の値を持つ各と同じロジック。次の図は、複数値を持つ 1 つの条件の例と 1 つの値 (同じプロパティ) の複数の条件の例を示しています。どちらの例では、同じクエリで発生します。`(filetype="docx") OR (filetype="pptx") OR (filetype="xlsx")`
    
    ![複数の値を持つ 1 つの条件](media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![同じプロパティに対する複数の検索条件](media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> 条件が複数の値を受け入れる場合、1 つの条件を使用し、(コンマまたはセミコロンで区切って) 複数の値を指定することをお勧めします。これにより、適用されるクエリ ロジックが確実に意図するものとなるようにすることができます。 
  
### <a name="examples-of-using-conditions-in-search-queries"></a>検索クエリでの条件の使用例

次の例に示します (これもが**Get ComplianceSearch**コマンドレットによって返されます)、選択した検索の詳細ウィンドウに表示される検索クエリの構文の条件で検索クエリの GUI ベースのバージョンとのロジック、KQL クエリの対応します。 
  
#### <a name="example-1"></a>例 1

この例では、2016 年 1 月 1 日前に最後に変更されたクレジット カード番号が格納されているビジネス サイトの SharePoint と OneDrive のドキュメントを返します。
  
 **GUI**
  
![検索条件の最初の例](media/099515ba-d4ee-474e-af25-3aa48816b87b.gif)
  
 **検索クエリ構文**
  
 `SensitiveType:"Credit Card Number(c:c)(lastmodifiedtime<2016-01-01)`
  
 **検索クエリ ロジック**
  
 `SensitiveType:"Credit Card Number" AND (lastmodifiedtime<2016-01-01)`
  
#### <a name="example-2"></a>例 2

この例では、キーワード "report" を含み、2105 年 4 月 1 日より前に送信または作成され、メール メッセージの件名フィールドかドキュメントのタイトル プロパティに "northwind" という単語を含む、メールのアイテムやドキュメントを返します。クエリは、他の検索条件に一致する Web ページを除外します。 
  
 **GUI**
  
![検索条件の 2 番目の例](media/fe07d495-df81-42da-8106-3cdb409c6e7f.gif)
  
 **検索クエリ構文**
  
 `report(c:c)(date<2016-04-01)(subjecttitle:"northwind")(-filetype="aspx")`
  
 **検索クエリ ロジック**
  
 `report AND (date<2016-04-01) AND (subjecttitle:"northwind") NOT (filetype="aspx")`
  
#### <a name="example-3"></a>例 3
<a name="conditionexamples"> </a>

この例では、電子メール メッセージまたは予定表の会議 2016/12/1 と 2016/11/30 の間で送信されると、「電話」または「スマート フォン」で始まる単語が含まれているを返します。
  
 **GUI**
  
![検索条件の 3 番目の例](media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **検索クエリ構文**
  
 `phone* OR smartphone*(c:c)(sent=2016-12-01..2016-11-30)(kind="email")(kind="meetings")`
  
 **検索クエリ ロジック**
  
 `phone* OR smartphone* AND (sent=2016-12-01..2016-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="searching-for-site-content-shared-with-external-users"></a>外部ユーザーと共有されているサイト コンテンツの検索

セキュリティ コンテンツの検索機能を使用することもできます&amp;コンプライアンス センターを組織の外部ユーザーと共有されているビジネス サイトの SharePoint と OneDrive に格納されているドキュメントを検索します。組織外で共有されている機密情報や専有情報を識別できます。使用してこれを行う、`ViewableByExternalUsers`のキーワード クエリのプロパティです。このプロパティには、ドキュメントまたは次のいずれかの共有を使用して外部ユーザーと共有されているサイトが返されます。 
  
- 共有への招待を認証済みユーザーとして、組織にサインインする必要があります。
    
- 認証を受けることがなく、リソースにアクセスするには、このリンクですべてのユーザーが匿名ゲスト リンクします。
    
次に、いくつかの例を示します。
  
- クエリ`ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"`、組織外のユーザーと共有されているし、クレジット カード番号が含まれているすべての項目が返されます。 
    
- クエリ`ViewableByExternalUsers:true AND ContentType:document AND site:"https://contoso.sharepoint.com/Sites/Teams"`は、組織内の外部ユーザーと共有されているすべてのチーム サイトにドキュメントの一覧を返します。 
    
> [!TIP]
> 検索クエリなど、`ViewableByExternalUsers:true AND ContentType:document`の検索結果に多数の .aspx ファイルを返すことがあります。これら (または他の種類のファイル) を削除するのには使用することができます、`FileExtension`プロパティが特定のファイルの種類を除外するのにはたとえば`ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx`。 
  
組織外のユーザーと共有されているコンテンツと見なされるでしょうか。ビジネス サイトの共有の招待状を送信することによって共有されているか、公共の場所で共有されているため、組織の SharePoint と OneDrive 内のドキュメント。などの外部のユーザーに表示されるコンテンツの次のユーザーのアクティビティが発生します。
  
- ユーザーが組織外のユーザーとファイルやフォルダーを共有する。

    
- ユーザーが作成し、組織外のユーザーに共有ファイルへのリンクを送信します。このリンクは、外部ユーザーがファイルを表示する (または編集) を使用します。
    
- ユーザーが、共有ファイルを表示 (または編集) するための共有への招待やゲスト リンクを組織外のユーザーに送信する。
    
### <a name="issues-using-the-viewablebyexternalusers-property"></a>ViewableByExternalUsers プロパティを使用しての問題

中に、`ViewableByExternalUsers`プロパティは、外部ユーザーにドキュメントやサイトを共有するかどうかの状態を表しますが、いくつか注意事項をどのようなこのプロパティは反映されません。次のシナリオでは、値で、`ViewableByExternalUsers`プロパティはありませんが更新され、このプロパティを使用するコンテンツの検索クエリの結果が正確でない可能性があります。 
  
- 共有ポリシーは、サイトまたは組織の外部で共有を無効にするように変更します。プロパティには、まだ外部からのアクセスが失効されている場合でも、着脱可能な対象として共有されていたドキュメントが表示されます。
    
- 追加することや、外部ユーザーが Office 365 のグループ、または Office 365 のセキュリティ グループを削除するなど、グループのメンバーシップを変更します。プロパティは、グループへのアクセス権を持っているアイテムを自動的に更新されません。
    
- 受信者が招待を承諾していないし、まだないため、外部ユーザーに送信する共有の招待状には、コンテンツへのアクセスがあります。
    
これらのシナリオで、`ViewableByExternalUsers`プロパティは、サイトまで現在の共有状態を反映しません、またはドキュメント ライブラリが再クロールし、インデックスを再作成します。 

## <a name="searching-for-site-content-shared-within-your-organization"></a>組織内で共有するサイトのコンテンツを検索します。

使用することができます前に説明したよう、`SharedWithUsersOWSUser`プロパティは、組織内のユーザー間で共有されているドキュメントを検索します。ユーザーは、組織内の他のユーザーとファイル (またはフォルダー) を共有する場合は、**自分と共有**] ページでファイルを共有した人のアカウントをビジネスの OneDrive で共有ファイルへのリンクが表示されます。たとえば、佐々木 davis が共同で共有されているドキュメントを検索することができますクエリを使用する`SharedWithUsersOWSUser:"sarad@contoso.com"`。この検索の結果をエクスポートする場合は、(佐々木さんに、ドキュメントを共有するユーザーのコンテンツの場所にあります)、元のドキュメントがダウンロードされます。
  
ドキュメントを明示的を使用する場合に、検索結果で返される特定のユーザーと共有する必要があります注意してください、`SharedWithUsersOWSUser`プロパティ。たとえば、人は、OneDrive アカウントにドキュメントを共有する場合、(内部または外部組織のユーザーと共有、組織内のユーザーとのみ共有する、または特定の人と共有するオプションがあります。ここでは、次の 3 つの共有オプションを表示するには、OneDrive の [**共有**] ウィンドウのスクリーン ショットです。 
  
![SharedWithUsersOWSUser プロパティを使用する検索クエリによって返される特定のユーザーと共有する唯一のファイル](media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
(**特定の人**と共有)、3 番目のオプションを使用して、共有されているドキュメントのみを使用する検索クエリで返されます、`SharedWithUsersOWSUser`プロパティ。 

## <a name="searching-for-skype-for-business-conversations"></a>Skype ビジネス会話の検索

次のキーワード クエリを使用して、Skype でのビジネス会話の内容を具体的に検索できます。

```
kind:im
```

前の検索クエリはマイクロソフトのチームからチャットを返すも注意してください。これを防止するには、次のキーワード クエリを使用して、ビジネス会話の Skype のみを含むように検索結果を絞ることができます。

```
kind:im AND subject:conversation
```

前のキーワード クエリは、ビジネス会話の Skype は「会話」という単語で始まる件名行の付いた電子メール メッセージとして保存されるため、マイクロソフトのチームでチャットを除外します。

Skype の特定の日付範囲内で発生したビジネス会話を検索するには、次のキーワード クエリを使用します。

```
kind:im AND subject:conversation AND (received=startdate..enddate)
```

## <a name="search-tips-and-tricks"></a>検索のヒントと秘訣

- キーワード検索では大文字と小文字は区別されません。たとえば、「 **cat** 」と「 **CAT** 」では同じ結果が返されます。 
    
- ブール演算子**AND**、**または**、**ない**、 **NEAR**、および**ONEAR**を大文字にする必要があります。 
    
- 2 つのキーワード、または 2 つの間にスペース`property:value`式は、 **AND**を使用する場合と同じです。たとえば、`from:"Sara Davis" subject:reorganization`件名の行に word の再編成を含む、佐々木さんのデービスによって送信されたすべてのメッセージを返します。 
    
- 一致する構文を使用して、`property:value`の形式です。値は、大文字小文字を区別しないと、演算子の後、スペースがあることはできません。スペースがある場合、目的の値はフルテキスト検索をするだけ。たとえば`to: pilarp`pilarp に送信されたメッセージではなく、キーワードとして「pilarp」のを検索します。 
    
- To、From、Cc、Recipients などの受信者プロパティを検索するとき、SMTP アドレス、別名、または表示名を使用して受信者を指定できます。たとえば、pilarp@contoso.com、pilarp、または "Pilar Pinilla" を使用できます。
    
- プレフィックス ワイルドカード検索のみを使用することができます。たとえば、 **cat\*** または**を設定\***。サフィックスを検索 ( ** \*cat** )、検索を挿入辞 ( **c\*t** )、検索文字列を指定し、( ** \*cat\* ** ) はサポートされていません。 
    
- プロパティを検索する場合は、二重引用符を使用して ("") 場合は、検索する値は、複数の単語で構成されています。たとえば`subject:budget Q1`で**予算**を含むメッセージを返すを [件名] 行に含まれている**第 1 四半期**任意の場所、メッセージまたはメッセージのプロパティのいずれかで。使用して`subject:"budget Q1"`、件名の行で任意の場所の**第 1 四半期の予算**が含まれているすべてのメッセージを返します。 
    
- 検索結果から特定のプロパティ値でマークされているコンテンツを除外するには、プロパティの名前の前にマイナス記号 (-) を配置します。たとえば、`-from:"Sara Davis"`佐々木 Davis によって送信されたメッセージが除外されます。
- 項目の種類に基づいてアイテムをエクスポートできます。など Skype IM メッセージの recived のユーザーをエクスポートするには、' の種類: IM' の構文を使用します。この検索では、すべての IM メッセージ returen を照会します。 
