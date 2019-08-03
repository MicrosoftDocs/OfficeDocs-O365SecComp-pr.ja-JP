---
title: コンテンツ検索のキーワード クエリと検索条件
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.SearchQueryLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
description: 'セキュリティ & コンプライアンスセンターのコンテンツ検索ツールを使用して、Exchange Online メールボックスおよび SharePoint または OneDrive for Business サイトで検索できる電子メールとファイルプロパティについて説明します。  '
ms.openlocfilehash: 70f005d6875735dfe95e10bf4487c8e1373431ea
ms.sourcegitcommit: 97b9f88b9beee23de13ecf6d0759ac0fad5cf08d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2019
ms.locfileid: "36168185"
---
# <a name="keyword-queries-and-search-conditions-for-content-search"></a>コンテンツ検索のキーワード クエリと検索条件

このトピックでは、セキュリティ & コンプライアンスセンターのコンテンツ検索機能を使用して、Exchange Online の電子メールアイテムで検索したり、SharePoint および OneDrive for Business サイトに保存されているドキュメントを検索したりするための電子メールとドキュメントプロパティについて説明します。 セキュリティ & コンプライアンスセンターの PowerShell で** \*-new-compliancesearch**コマンドレットを使用して、これらのプロパティを検索することもできます。 このトピックでは、以下についても説明します。   
  
- ブール検索演算子、検索条件、およびその他の検索クエリ手法を使用して、検索結果を調整します。
    
- SharePoint と OneDrive for business で機密性の高いデータ型とカスタムの機密データ型を検索します。
    
- 組織外のユーザーと共有しているサイトコンテンツを検索する
    
コンテンツ検索を作成する方法の詳細な手順については、「 [Office 365 のコンテンツ検索](content-search.md)」を参照してください。

  
> [!NOTE]
> セキュリティ & コンプライアンスセンターのコンテンツ検索と、セキュリティ & コンプライアンスセンター PowerShell の** \*new-compliancesearch**コマンドレットは、キーワードクエリ言語 (kql) を使用します。 詳細については、「 [Keyword Query Language 構文 reference](https://go.microsoft.com/fwlink/?LinkId=269603)」を参照してください。 
  
## <a name="searchable-email-properties"></a>検索可能なメール プロパティ

次の表に、セキュリティ & コンプライアンスセンターでコンテンツ検索機能を使用するか、 **new-compliancesearch**または**new-compliancesearch**コマンドレットを使用して検索できる電子メールメッセージプロパティの一覧を示します。 表には、各プロパティの  _property:value_ 構文の例、およびその例で返される検索結果の説明が含まれています。 これら`property:value`のペアは、コンテンツ検索の [キーワード] ボックスに入力できます。 

> [!NOTE]
> 電子メールのプロパティを検索する場合、指定されたプロパティが empty または blank のアイテムを検索することはできません。 たとえば、subject 行が空の電子メールメッセージを検索するには、 **""** という件名の*プロパティ: 値*のペアを使用すると、ゼロの結果が返されます。 これは、サイトおよび連絡先のプロパティを検索する場合にも適用されます。
  
|**プロパティ**|**プロパティの説明**|**例**|**例で返される検索結果**|
|:-----|:-----|:-----|:-----|
|AttachmentNames|電子メール メッセージに添付されているファイルの名前。|`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual*`|annualreport.ppt という名前の添付ファイルのあるメッセージ。2 番目の例では、ワイルドカードを使用して、添付ファイルのファイル名に「annual」の語が含まれるメッセージを返します。|
|Bcc|メール メッセージの BCC フィールド。<sup>1</sup>|`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`|どの例も Bcc フィールドに「Pilar Pinilla」が含まれているメッセージを返します。|
|Category| 検索するカテゴリ。 カテゴリは、Outlook または web 上の Outlook (旧称 Outlook Web App) を使用してユーザーが定義できます。 値は次のいずれかです。  <br/><br/>  blue  <br/>  green  <br/>  orange  <br/>  purple  <br/>  red  <br/>  yellow|`category:"Red Category"`|元のメールボックスで「red」のカテゴリが割り当てられているメッセージ。|
|CC|メール メッセージの CC フィールド。<sup>1</sup>|`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`|どちらの例も、CC フィールドに Pilar Pinilla が指定されたメッセージ。|
|Folderid|特定のメールボックスフォルダーのフォルダー ID (GUID)。 このプロパティを使用する場合は、指定したフォルダーが配置されているメールボックスを検索してください。 指定したフォルダーのみが検索されることに注意してください。 フォルダー内のサブフォルダーは検索されません。 サブフォルダーを検索するには、検索するサブフォルダーの Folderid プロパティを使用する必要があります。  <br/> Folderid プロパティを検索する方法と、スクリプトを使用して特定のメールボックスのフォルダー Id を取得する方法の詳細については、「[対象化コレクションの Office 365 でコンテンツ検索を使用](use-content-search-for-targeted-collections.md)する」を参照してください。|`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`|最初の例では、指定されたメールボックスフォルダー内のすべてのアイテムを返します。 2番目の例では、garthf@contoso.com によって送受信された、指定されたメールボックスフォルダー内のすべてのアイテムを返します。|
|From|メール メッセージの送信者。<sup>1</sup>|`from:pilarp@contoso.com`  <br/> `from:contoso.com`|指定されたユーザーによって送信された、または指定されたドメインから送信されたメッセージ。|
|HasAttachment|メッセージに添付ファイルがあるかどうかを示します。 **True**または**false**の値を使用します。|`from:pilar@contoso.com AND hasattachment:true`|添付ファイルを持つ、指定されたユーザーによって送信されたメッセージ。|
|Importance|送信者がメッセージを送信するときに指定できる電子メール メッセージの重要度。既定では、送信者が重要度を **high** または **low** に設定していない限り、メッセージは普通の重要度で送信されます。  |`importance:high`  <br/> `importance:medium`  <br/> `importance:low`|高重要度、中重要度、または低重要度とマークされているメッセージ。|
|IsRead|メッセージが開封されたかどうかを示します。 **True**または**false**の値を使用します。|`isread:true`  <br/> `isread:false`|最初の例では、IsRead プロパティが**True**に設定されたメッセージを返します。 2番目の例では、IsRead プロパティが**False**に設定されたメッセージを返します。|
|ItemClass|このプロパティを使用して、組織が Office 365 にインポートした特定のサードパーティのデータ型を検索します。 このプロパティには、次の構文を使用します。`itemclass:ipm.externaldata.<third-party data type>*`|`itemclass:ipm.externaldata.Facebook* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter* AND from:"Ann Beebe" AND "Northwind Traders"`|最初の例では、Subject プロパティに "contoso" という単語が含まれる Facebook のアイテムを返します。 2番目の例では、彩 Beebe によって投稿され、キーワード "Northwind Traders" が含まれている Twitter アイテムを返します。  <br/> ItemClass プロパティのサードパーティデータ型に使用する値の完全な一覧については、「[コンテンツ検索を使用して、Office 365 にインポートされたサードパーティのデータを検索する](use-content-search-to-search-third-party-data-that-was-imported.md)」を参照してください。|
|Kind| 検索する電子メールメッセージの種類。 可能な値:  <br/>  contacts  <br/>  docs  <br/>  email  <br/>  externaldata  <br/>  faxes  <br/>  im  <br/>  journals  <br/>  meetings  <br/>  Microsoft teams (Microsoft Teams でチャット、会議、通話のアイテムを返す)  <br/>  notes  <br/>  posts  <br/>  rssfeeds  <br/>  tasks  <br/>  voicemail|`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`|最初の例では、検索条件に一致する電子メールメッセージを返します。 2番目の例では、電子メールメッセージ、インスタントメッセージの会話 (Microsoft Teams での Skype for Business の会話やチャットを含む)、および検索条件に一致する音声メッセージを返します。 3番目の例では、検索条件を満たす Twitter、Facebook、Cisco Jabber などのサードパーティのデータソースから、Office 365 のメールボックスにインポートされたアイテムを返します。 詳細については、「 [Office 365 でサードパーティのデータをアーカイブ](https://go.microsoft.com/fwlink/p/?linkid=716918)する」を参照してください。|
|Participants|メール メッセージ内のすべての送受信者フィールド。すなわち、From、To、CC、BCC の各フィールドです。<sup>1</sup>|`participants:garthf@contoso.com`  <br/> `participants:contoso.com`|garthf@contoso.com が送信元または送信先のメッセージ。2 番目の例は、contoso.com ドメイン内のユーザーが送信元または送信先のすべてのメッセージを返します。|
|Received|電子メール メッセージが受信者によって受信された日付。|`received:04/15/2016`  <br/> `received>=01/01/2016 AND received<=03/31/2016`|2016年4月15日に受信したメッセージ。 2番目の例では、2016年1月1日から2016年3月31日までの間に受信したすべてのメッセージを返します。|
|Recipients|メール メッセージ内のすべての受信者フィールド。すなわち、To、CC、BCC の各フィールドです。<sup>1</sup>|`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`|garthf@contoso.com に送信されたメッセージ。2 番目の例では、contoso.com ドメイン内のすべての受信者に送信されたメッセージを返します。|
|Sent|送信者によって電子メール メッセージが送信された日付。|`sent:07/01/2016`  <br/> `sent>=06/01/2016 AND sent<=07/01/2016`|指定された日付に送信された、または指定された日付範囲内に送信されたメッセージ。|
|Size|アイテムのサイズ (バイト数)。|`size>26214400`  <br/> `size:1..1048567`|25より大きいメッセージ8mb. 2 番目の例は 1 ～ 1,048,567 バイト (1 MB) のサイズのメッセージを返します。|
|Subject|電子メール メッセージの件名行に含まれるテキスト。  <br/> **注:** クエリで Subject プロパティを使用する場合、???検索では、検索しているテキストが件名に含まれているすべてのメッセージが返されます。 つまり、クエリは、完全に一致するメッセージのみを返しません。 たとえば、を検索`subject:"Quarterly Financials"`すると、件名が "四半期財務 2018" のメッセージが結果に含まれます。|`subject:"Quarterly Financials"`  <br/> `subject:northwind`|件名行のテキスト内の任意の場所に "四半期財務" という語句が含まれるメッセージ。 2 番目の例では、件名行に「northwind」の語が含まれているすべてのメッセージを返します。|
|To|メール メッセージの To フィールド。<sup>1</sup>|`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`|どの例も、To: 行に「Ann Beebe」が指定されているメッセージを返します。|
|||||
   
> [!NOTE]
> <sup>1</sup>受信者プロパティの値には、電子メールアドレス (*ユーザープリンシパル名*または UPN とも呼ばれる)、表示名、またはエイリアスを使用して、ユーザーを指定できます。 たとえば、ユーザー Ann Beebe を指定するために、annb@contoso.com、annb、または "Ann Beebe" を使用できます。<br/><br/>受信者のプロパティ (From、To、Cc、Bcc、参加者、および受信者) を検索する場合、Office 365 は Azure Active Directory で検索して各ユーザーの id を拡張しようとします。  ユーザーが Azure Active Directory で見つかった場合、そのユーザーの電子メールアドレス (または UPN)、エイリアス、表示名、および LegacyExchangeDN を含むようにクエリが拡張されます。<br/><br/>たとえば、のようなクエリが`participants:ronnie@contoso.com`に`participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"`展開されます。<br/><br/>受信者を拡張しないようにするには、検索クエリの電子メールアドレスの末尾にワイルドカード文字 (アスタリスク) を追加します。たとえば、 `participants:ronnie@contoso.com*`のようになります。

## <a name="searchable-site-properties"></a>検索可能なサイトのプロパティ

次の表に、セキュリティ & コンプライアンスセンターでコンテンツ検索機能を使用するか、 **new-compliancesearch**または new-compliancesearch を使用して検索できる SharePoint および OneDrive for business のプロパティを示します。 **** コマンドレット。 表には、各プロパティの  _property:value_ 構文の例、およびその例で返される検索結果の説明が含まれています。 
  
検索できる SharePoint プロパティの完全な一覧については、「 [sharepoint のクロールされたプロパティと管理プロパティの概要](https://go.microsoft.com/fwlink/p/?LinkId=331599)」を参照してください。 **クエリ**可能な列で**Yes**が設定されているプロパティを検索することができます。 
  
|**プロパティ**|**プロパティの説明**|**例**|**例で返される検索結果**|
|:-----|:-----|:-----|:-----|
|設定元|ドキュメントがコピーされた場合に保持される Office ドキュメントの作成者フィールドです。 たとえば、ユーザーがドキュメントを作成し、そのドキュメントを他のユーザーが SharePoint にアップロードした場合、そのドキュメントは元の作成者を保持したままになります。 このプロパティには、必ずユーザーの表示名を使用してください。|`author:"Garth Fort"`|Garth Fort によって作成されたすべてのドキュメント。|
|ContentType|アイテム、ドキュメント、ビデオなどのアイテムの SharePoint コンテンツタイプ。|`contenttype:document`|すべてのドキュメントが返されます。|
|作成済み|アイテムが作成された日付。|`created\>=06/01/2016`|2016年6月1日以降に作成されたすべてのアイテム。|
|CreatedBy|アイテムを作成またはアップロードした人。 このプロパティには、必ずユーザーの表示名を使用してください。|`createdby:"Garth Fort"`|Garth Fort によって作成またはアップロードされたすべてのアイテム。|
|DetectedLanguage|アイテムの言語。|`detectedlanguage:english`|英語のすべてのアイテム。|
|DocumentLink|SharePoint または OneDrive for business サイトの特定のフォルダーのパス (URL)。 このプロパティを使用する場合は、指定したフォルダーが配置されているサイトを検索するようにしてください。  <br/> Documentlink プロパティに指定したフォルダーのサブフォルダーにあるアイテムを返すには、指定したフォルダー\*の URL にを追加する必要があります。例えば`documentlink: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/>Documentlink プロパティを検索する方法と、スクリプトを使用して特定のサイト上のフォルダーの documentlink Url を取得する方法の詳細については、「[対象化コレクション用に Office 365 のコンテンツ検索を使用](use-content-search-for-targeted-collections.md)する」を参照してください。|`documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private"`  <br/> `documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/*" AND filename:confidential`|最初の例では、指定した OneDrive for Business フォルダー内のすべてのアイテムを返します。 2番目の例では、指定されたサイトフォルダー (およびすべてのサブフォルダー) に、ファイル名に "confidential" という単語が含まれるドキュメントを返します。|
|FileExtension|ファイルの拡張子。例: .docx、one、.pptx、または .xlsx。|`fileextension:xlsx`|すべての Excel ファイル (Excel 2007 以降)|
|FileName|ファイルの名前。|`filename:"marketing plan"`  <br/> `filename:estimate`|最初の例では、タイトルに "marketing plan" と完全一致する語句が含まれるファイルが返されます。2 番目の例では、ファイル名に "estimate" という単語を含むファイルが返されます。|
|LastModifiedTime|アイテムが最後に変更された日付。|`lastmodifiedtime>=05/01/2016`  <br/> `lastmodifiedtime>=05/10/2016 AND lastmodifiedtime<=06/1/2016`|最初の例では、2016年5月1時以降に変更されたアイテムを返します。 2番目の例では、2016年5月1日から2016年6月1日までの間に変更されたアイテムを返します。|
|ModifiedBy|アイテムを最後に変更した人。 このプロパティには、必ずユーザーの表示名を使用してください。|`modifiedby:"Garth Fort"`|Garth Fort によって最後に変更されたすべてのアイテム。|
|パス|SharePoint または OneDrive for Business サイトの特定のサイトのパス (URL)。  <br/> Path プロパティに指定したサイト内のフォルダーにあるアイテムを返すには、指定したサイト\*の URL を追加する必要があります。例えば`path: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/> **注:** OneDrive の`Path`場所を検索するためにプロパティを使用しても、検索結果には .png, tiff ファイル、.wav ファイルなどのメディアファイルは返されません。 検索クエリで別のサイトプロパティを使用して、OneDrive フォルダーのメディアファイルを検索します。 <br/>|`path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/"`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/*" AND filename:confidential`|最初の例では、指定した OneDrive for Business サイト内のすべてのアイテムを返します。 2番目の例では、指定したサイト (およびサイト内のフォルダー) に、ファイル名に "confidential" という単語が含まれるドキュメントを返します。|
|SharedWithUsersOWSUser|指定したユーザーと共有され、ユーザーの OneDrive for Business サイトの [**自分と共有**] ページに表示されるドキュメント。 これらは、組織内の他のユーザーによって指定されたユーザーが明示的に共有しているドキュメントです。 SharedWithUsersOWSUser プロパティを使用する検索クエリに一致するドキュメントをエクスポートすると、指定されたユーザーとドキュメントを共有しているユーザーの元のコンテンツの場所からドキュメントがエクスポートされます。 詳細については、「[組織内で共有しているサイトコンテンツを検索する](#searching-for-site-content-shared-within-your-organization)」を参照してください。|`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`|両方の例では、Garth 砦と明示的に共有されており、Garth 砦の OneDrive for Business アカウントの [**自分と共有**] ページに表示されるすべての内部ドキュメントを返します。|
|Site|組織内のサイトかサイトのグループの URL。|`site:"https://contoso-my.sharepoint.com"`  <br/> `site:"https://contoso.sharepoint.com/sites/teams"`|最初の例では、組織内のすべてのユーザーについて、OneDrive for Business サイトからアイテムを返します。 2 番目の例では、すべてのチーム サイトからアイテムが返されます。|
|Size|アイテムのサイズ (バイト数)。|`size>=1`  <br/> `size:1..10000`|最初の例では、1 バイトより大きいアイテムが返されます。2 番目の例では、1 ～ 10,000 バイトのサイズのメッセージが返されます。|
|タイトル|ドキュメントのタイトル。 Title プロパティは、Microsoft Office ドキュメントで指定されているメタデータです。 ドキュメントのファイル名とは異なります。|`title:"communication plan"`|Office ドキュメントの Title メタデータ プロパティに "communication plan" という語句が含まれるすべてのドキュメント。|
|||||
   
## <a name="searchable-contact-properties"></a>検索可能な連絡先のプロパティ

次の表に、インデックスが作成され、コンテンツ検索を使用して検索できる、連絡先のプロパティを示します。 ユーザーのメールボックスの個人用アドレス帳にある連絡先 (個人用連絡先とも呼ばれます) に対してユーザーが構成できるプロパティを次に示します。 連絡先を検索するには、検索するメールボックスを選択し、キーワードクエリで1つ以上の連絡先プロパティを使用します。
  
> [!TIP]
> スペースまたは特殊文字を含む値を検索するには、二重引用符 ("") を使用して語句を入力します。たとえば、 `businessaddress:"123 Main Street"`のようになります。 
  
|**プロパティ**|**プロパティの説明**|
|:-----|:-----|
|BusinessAddress|"**会社住所**" プロパティの住所。 このプロパティは、連絡先のプロパティページの [**勤務**先住所] とも呼ばれます。|
|BusinessPhone|任意の**勤務先電話**番号のプロパティの電話番号。|
|CompanyName|**Company**プロパティの名前。|
|部署|**Department**プロパティの名前。|
|DisplayName|連絡先の表示名。 これは、連絡先の**氏名**プロパティの名前です。|
|EmailAddress|連絡先の任意の電子メールアドレスプロパティのアドレス。 ユーザーが連絡先に複数の電子メールアドレスを追加できることに注意してください。 このプロパティを使用すると、連絡先の電子メールアドレスのいずれかに一致する連絡先が返されます。|
|FileAs|プロパティ**としてのファイル**。 このプロパティは、連絡先をユーザーの連絡先リストに表示する方法を指定するために使用されます。 たとえば、連絡先を姓 *、lastname* 、または*lastname、firstname*として一覧表示することができます。|
|GivenName|"名" プロパティ**** の名前を指定します。|
|HomeAddress|任意の**ホーム**アドレスプロパティのアドレス。|
|HomePhone|任意の**自宅**電話番号のプロパティの電話番号。|
|IMAddress|IM アドレスプロパティ。通常は、インスタントメッセージングに使用される電子メールアドレスです。|
|MiddleName|"**ミドル**ネーム" プロパティの名前を指定します。|
|MobilePhone|**携帯**電話番号プロパティの電話番号。|
|Nickname|**ニックネーム**プロパティの名前を指定します。|
|OfficeLocation|**Office**または office の**location**プロパティの値。|
|OtherAddress|**Other** address プロパティの値。|
|Surname|" **Last** name/名前" プロパティの名前を指定します。|
|タイトル|役職プロパティのタイトル**** 。|
|||||

## <a name="searchable-sensitive-data-types"></a>検索可能な機密性の高いデータ型

セキュリティ/コンプライアンスセンターのコンテンツ検索機能を使用して、SharePoint および OneDrive for Business サイトのドキュメントに格納されている機密データ (クレジットカード番号や社会保障番号など) を検索できます。 これを行うには、キーワード`SensitiveType`クエリで、プロパティと機密情報の種類の名前を使用します。 たとえば、クエリ`SensitiveType:"Credit Card Number"`は、クレジットカード番号が含まれるドキュメントを返します。 このクエリ`SensitiveType:"U.S. Social Security Number (SSN)"`は、米国の社会保障番号が含まれるドキュメントを返します。 検索可能な機密性の高いデータ型の一覧を表示するには、セキュリティ & コンプライアンスセンターで、[**分類** \>の**機密情報の種類**] に移動します。 または、セキュリティ & コンプライアンスセンターの PowerShell で**set-dlpsensitiveinformationtype**コマンドレットを使用して、機密情報の種類の一覧を表示することもできます。 
  
`SensitiveType`プロパティを使用して、組織に対して作成したカスタムの機密情報の種類の名前を検索することもできます (または別の管理者)。 セキュリティ & コンプライアンスセンター (または PowerShell の**publisher**プロパティ) の [**機密性の高い情報の種類**] ページで**publisher**列を使用して、組み込みの機密情報とカスタムの機密情報を区別することに注意してください。各種. 詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」を参照してください。
  
`SensitiveType`プロパティを使用してクエリを作成する方法の詳細については、「[サイトに保存されている機密データを検索するためのクエリを形成する](form-a-query-to-find-sensitive-data-stored-on-sites.md)」を参照してください。

> [!NOTE]
> 機密データの種類と`SensitiveType`検索プロパティを使用して、Exchange Online メールボックス内の保存されていない機密データを検索することはできません。 ただし、データ損失防止 (DLP) ポリシーを使用して、機密性の高い電子メールデータを送信中で保護することができます。 詳細については、「[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)」および「[検索して個人データ](search-for-and-find-personal-data.md)を検索する」を参照してください。
  
## <a name="search-operators"></a>検索演算子

**And**、 **OR**、 **NOT**などのブール型の検索演算子を使用すると、検索クエリで特定の単語を含めたり除外したりして、より正確な検索を定義できます。 その他の手法 (たとえば、 \>= または..)、引用符、かっこ、ワイルドカードなどを使用して、検索クエリを絞り込むことができます。 次の表に、検索結果を絞り込んだり広げたりするために使用できる演算子を示します。 
  
|**演算子**|**用途**|**説明**|
|:-----|:-----|:-----|
|AND|keyword1 AND keyword2|指定されたすべてのキーワードまたは`property:value`式を含むアイテムを返します。 たとえば、は`from:"Ann Beebe" AND subject:northwind` 、件名行に "northwind" が含まれている、彩 Beebe が送信したすべてのメッセージを返します。 <sup>2</sup>|
|+|keyword1 + keyword2 + keyword3|Returns items that contain  *either*  `keyword2` or  `keyword3` *and*  that also contain  `keyword1`. Therefore, this example is equivalent to the query  `(keyword2 OR keyword3) AND keyword1`.  <br/> Note that the query  `keyword1 + keyword2` (with a space after the **+** symbol) isn't the same as using the ** AND ** operator. This query would be equivalent to  `"keyword1 + keyword2"` and return items with the exact phase  `"keyword1 + keyword2"`.  |
|OR|keyword1 OR keyword2|指定した1つ以上のキーワードまた`property:value`は式を含むアイテムを返します。 <sup>2</sup>|
|NOT|keyword1 NOT keyword2  <br/> NOT from:"Ann Beebe"  <br/> NOT kind: im|キーワードまたは`property:value`式で指定された項目を除外します。 2番目の例では、彩 Beebe によって送信されたメッセージを除外します。 3番目の例では、会話履歴メールボックスフォルダーに保存されている Skype for Business の会話など、インスタントメッセージングの会話を除外します。 <sup>2</sup>|
|-|keyword1 -keyword2|**NOT** 演算子と同じです。 そのため`keyword1` 、このクエリは、を含むアイテムを返し、 `keyword2`を含むアイテムを除外します。|
|NEAR|keyword1 NEAR(n) keyword2|互いに近い単語を含む項目を返します。 n は単語の数と等しくなります。 たとえば、 `best NEAR(5) worst` "最下位" という単語が5単語の "best" に含まれているアイテムを返します。 数値が指定されていない場合、既定の間隔は 8 単語です。 <sup>2</sup>|
|ONEAR|keyword1 ONEAR(n) keyword2|**Near**に似ていますが、指定された順序で互いに近い単語を持つアイテムを返します。 たとえば、" `best ONEAR(5) worst` best" という単語の前に "best" が出現し、2つの単語がそれぞれ互いの5つの単語の中にある場合は、"best" という単語を返します。 数値が指定されていない場合、既定の間隔は 8 単語です。 <sup>2</sup> <br/> > [!NOTE]>、 **Onear**演算子はメールボックスの検索時にサポートされていません。SharePoint と OneDrive for business サイトを検索する場合にのみ機能します。 同じ検索でメールボックスとサイトを検索していて、クエリに**Onear**演算子が含まれている場合、検索では、 **NEAR**演算子を使用している場合と同様にメールボックスアイテムが返されます。 つまり、検索では、単語が出現する順序に関係なく、指定した単語が互いに近くにあるアイテムが返されます。|
|:|property:value|コロン (:)`property:value`構文では、検索対象のプロパティの値に指定された値が含まれることを指定します。 たとえば、  `recipients:garthf@contoso.com` は garthf@contoso.com に送信されたすべてのメッセージを返します。|
|=|property=value|**:** 演算子と同じです。|
|\<|property\<value|検索対象のプロパティが指定の値より小さいことを意味します。<sup>1</sup>|
|\>|property\>value|検索対象のプロパティが指定の値より大きいことを意味します。<sup>1</sup>|
|\<=|property\<=value|検索対象のプロパティが特定の値以下であることを意味します。<sup>1</sup>|
|\>=|property\>=value|検索対象のプロパティが特定の値以上であることを意味します。<sup>1</sup>|
|..|プロパティ: value1..value2|検索対象のプロパティが value1 以上で value2 以下であることを意味します。<sup>1</sup>|
|"  "|"fair value"  <br/> subject:"Quarterly Financials"|二重引用符 ("") を使用して、キーワードおよび`property:value`検索クエリの完全に一致する語句を検索します。|
|\*|cat\*  <br/> subject:set\*|前方一致ワイルドカード検索 (アスタリスクが語尾にある) は、キーワードや  `property:value` クエリで、0 個以上の文字に一致します。 たとえば、ドキュメント`title:set*`タイトルで、word の set、setup、setting (および "set" で始まるその他の単語) を含むドキュメントを返します。  <br/><br/> **注:** プレフィックスワイルドカード検索のみ使用できます。例: **cat\* **または**set\***。 サフィックス検索 ( ** \*cat** )、挿入辞検索 **(\*c t** )、および部分文字列検索 ( ** \*\* cat** ) はサポートされていません。|
|(  )| (fair OR free) AND (from:contoso.com)  <br/> (IPO OR initial) AND (stock OR shares)  <br/> (quarterly financials)|括弧は、ブール演算子の文字列、 `property:value` アイテム、およびキーワードをグループにまとめます。たとえば、  `(quarterly financials)` は quarterly および financials の語を含むアイテムを返します。  |
|||||
   
> [!NOTE]
> <sup>1</sup>日付または数値を含むプロパティには、この演算子を使用します。<br/> <sup>2</sup>ブール検索演算子は大文字である必要があります。たとえば、**と**のようになります。 **と**などの小文字演算子を使用すると、検索クエリではキーワードとして扱われます。 
  
## <a name="search-conditions"></a>検索条件

検索クエリに条件を追加して、検索を絞り込んだり、より絞り込みのある結果セットを返すことができます。 各条件によって、作成された KQL 検索クエリに句が追加され、ユーザーが検索を開始するとそのクエリが実行されます。
  
[共通プロパティの条件 ](#conditions-for-common-properties)

[メール プロパティの条件](#conditions-for-mail-properties)

[ドキュメント プロパティの条件](#conditions-for-document-properties)

[条件で使用する演算子](#operators-used-with-conditions)

[条件を使用するためのガイドライン](#guidelines-for-using-conditions)

[例](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>共通プロパティの条件

同じ検索でメールボックスとサイトを検索する場合は、共通プロパティを使って条件を作成します。 次の表に、条件を追加するときに使用できるプロパティを示します。
  
|**条件**|**説明**|
|:-----|:-----|
|Date|メールの場合、受信者によってメッセージが受信された日付か、送信者によってメッセージが送信された日付。 ドキュメントの場合は、ドキュメントが最後に変更された日付。|
|送信者/作成者|メールの場合、メッセージの送信者。 ドキュメントの場合、Office ドキュメントから作成者フィールドに示されている人。 複数の名前をコンマで区切って入力できます。 2 つ以上の値は **OR** 演算子によって論理的に接続されます。|
|サイズ (バイト数)|メールとドキュメントのいずれの場合も、アイテムのサイズ (バイト単位)。|
|件名/タイトル|メールの場合、メッセージの件名行のテキスト。 ドキュメントの場合、ドキュメントのタイトル。 前述のとおり、Title プロパティは、Microsoft Office ドキュメントで指定されたメタデータです。 複数の件名またはタイトルの名前をコンマで区切って入力することができます。 2 つ以上の値は **OR** 演算子によって論理的に接続されます。|
|コンプライアンス タグ|電子メールとドキュメントの両方について、ユーザーによって手動で割り当てられたラベルポリシーまたはラベルによって、メッセージやドキュメントに自動的に割り当てられたラベル。 ラベルは、データガバナンスのために電子メールとドキュメントを分類し、ラベルで定義された分類に基づいて保持ルールを適用するために使用されます。 ラベル名の一部を入力し、ワイルドカードを使用するか、完全なラベル名を入力できます。 詳細については、「 [Office 365 のラベルの概要](labels.md)」を参照してください。|
|||
  
### <a name="conditions-for-mail-properties"></a>メール プロパティの条件

メールボックスやパブリック フォルダーを検索する場合は、メール プロパティを使って条件を作成します。条件で使うメール プロパティを次の表に一覧表示します。これらのプロパティは上記で説明されているメール プロパティのサブセットであることに注意してください。これらの説明は、必要に応じて繰り返されます。
  
|**条件**|**説明**|
|:-----|:-----|
|メッセージの種類| 検索するメッセージの種類。 これは、Kind メール プロパティと同じプロパティです。 可能な値:  <br/><br/>  contacts  <br/>  docs  <br/>  email  <br/>  externaldata  <br/>  faxes  <br/>  im  <br/>  journals  <br/>  meetings  <br/>  microsoftteams  <br/>  notes  <br/>  posts  <br/>  rssfeeds  <br/>  tasks  <br/>  voicemail|
|参加者|メール メッセージ内のすべての送受信者フィールド。すなわち、From、To、CC、BCC の各フィールドです。|
|型|電子メールアイテムのメッセージクラスプロパティ。 このプロパティは、ItemClass email プロパティと同じです。 複数値の条件でもあります。 そのため、複数のメッセージクラスを選択するには、 **CTRL**キーを押したまま、条件に追加するドロップダウンリストで2つ以上のメッセージクラスをクリックします。 リストで選択した各メッセージクラスは、対応する検索クエリの**or**演算子によって論理的に接続されます。  <br/> Exchange によって使用されるメッセージクラス (および対応するメッセージクラス ID) の一覧については、「アイテムの**** [種類とメッセージクラス](https://go.microsoft.com/fwlink/?linkid=848143)」を参照してください。|
|Received|電子メール メッセージが受信者によって受信された日付。 これは、Received メール プロパティと同じプロパティです。|
|受信者|電子メールメッセージが送信されたユーザー。 これは、To メール プロパティと同じプロパティです。|
|Sender|電子メール メッセージの差出人。|
|Sent|送信者によって電子メール メッセージが送信された日付。 これは、Sent メール プロパティと同じプロパティです。|
|Subject|電子メール メッセージの件名行に含まれるテキスト。|
|宛先|電子メールメッセージの受信者。|
|||
  
### <a name="conditions-for-document-properties"></a>ドキュメント プロパティの条件

SharePoint および OneDrive for Business サイトでドキュメントを検索するときに、ドキュメントプロパティを使用して条件を作成します。 次の表に、条件に使用できるドキュメントプロパティを示します。 これらのプロパティは、前に説明したサイトプロパティのサブセットであることに注意してください。これらの説明は、利便性のために繰り返されています。
  
|**条件**|**説明**|
|:-----|:-----|
|設定元|ドキュメントがコピーされた場合に保持される Office ドキュメントの作成者フィールドです。 たとえば、ユーザーがドキュメントを作成し、そのドキュメントを他のユーザーが SharePoint にアップロードした場合、そのドキュメントは元の作成者を保持したままになります。|
|タイトル|ドキュメントのタイトル。 Title プロパティは、Office ドキュメントに 指定されているメタデータです。 ドキュメントのファイル名とは異なります。|
|作成済み|ドキュメントが作成された日付。|
|最終更新日時|ドキュメントが最後に変更された日付。|
|ファイルの種類|ファイルの拡張子。例: .docx、one、.pptx、または .xlsx。 これは、FileExtension サイト プロパティと同じプロパティです。|
|||
  
### <a name="operators-used-with-conditions"></a>条件で使用する演算子

条件を追加するときは、条件のプロパティの種類に関連した演算子を選択します。条件とともに使用される演算子を次の表で説明します。また、検索クエリで使用される同等物の一覧も表示します。
  
|**演算子**|**クエリの同等物**|**説明**|
|:-----|:-----|:-----|
|After|`property>date`|日付の条件で使用されます。指定された日付の後に送信、受信、変更された項目を返します。 |
|Before|`property<date`|日付の条件で使用されます。指定された日付の前に送信、受信、変更された項目を返します。|
|の|`date..date`|日付条件およびサイズ条件で使用します。 日付条件で使用すると、指定された日付範囲内に送信、受信、変更された項目を返します。 サイズ条件で使用すると、サイズが指定範囲内にある項目を返します。|
|Contains any of|`(property:value) OR (property:value)`|文字列値を指定するプロパティの条件で使用されます。 1 つ以上の指定された文字列の値の任意の部分が含まれる項目を返します。|
|Doesn't contain any of|`-property:value`  <br/> `NOT property:value`|文字列値を指定するプロパティの条件で使用されます。 指定された文字列のどの部分も含まれない項目を返します。|
|Doesn't equal any of|`-property=value`  <br/> `NOT property=value`|文字列値を指定するプロパティの条件で使用されます。特定の文字列が含まれない項目を返します。|
|等しい|`size=value`|指定されたサイズと等しいアイテムを返します。<sup>1</sup>|
|Equals any of|`(property=value) OR (property=value)`|文字列値を指定するプロパティの条件で使用されます。1 つ以上の指定された文字列の値と完全に一致する項目を返します。|
|大きい|`size>value`|指定されたプロパティが指定された値より大きいアイテムを返します。<sup>1</sup>|
|Greater or equal|`size>=value`|指定されたプロパティが指定された値以上の場合にアイテムを返します。<sup>1</sup>|
|なる|`size<value`|特定の値以上の項目を返します。<sup>1</sup>|
|Less or equal|`size<=value`|特定の値以上の項目を返します。<sup>1</sup>|
|Not equal|`size<>value`|指定したサイズと等しくない項目を返します。<sup>1</sup>|
|||
   
> [!NOTE]
> <sup>1</sup>この演算子は、Size プロパティを使用する条件に対してのみ使用できます。 
  
### <a name="guidelines-for-using-conditions"></a>条件を使用するためのガイドライン

検索条件を使用する際は、以下の点に留意してください。
  
- 条件は、**AND** 演算子によってキーワードのクエリ (キーワード ボックスで指定される) と論理的に接続されます。 つまり、キーワード クエリと条件の両方を満たす項目が結果に入ります。 このように条件は、結果を絞り込むのに役立ちます。 
    
- 検索クエリに2つ以上の一意の条件を追加すると、それらの条件は**and**演算子によって論理的に接続されます。 これは、(キーワードのクエリに加えて) すべての条件が満たされる項目だけが返されることを意味します。 
    
- 同じプロパティに複数の条件を追加する場合、これらの条件は、**OR** 演算子によって論理的に接続されます。 これは、キーワードのクエリおよびいずれかの条件を満たす項目が返されることを意味します。 それで、同じ条件のグループが **OR** 演算子によって互いに接続され、その後、固有の条件のセットが **AND** 演算子によって接続されます。 
    
- 複数の値をコンマまたはセミコロンで区切って1つの条件に追加すると、それらの値は**or**演算子によって接続されます。 これは、条件のプロパティの指定された値のいずれかが項目に含まれる場合にその項目が返されることを意味します。 
    
- [キーワード] ボックスと条件を使用して作成された検索クエリは、選択した検索の詳細ウィンドウの [**検索**] ページに表示されます。 クエリでは、表記`(c:c)`の右にあるものはすべて、クエリに追加された条件を示します。 
    
- 条件によって検索クエリに追加されるのはプロパティだけであり、演算子は追加されません。 このため、詳細ウィンドウに表示されるクエリには、 `(c:c)`表記の右側に演算子は表示されません。 KQL は、クエリの実行時に (前述の規則に従って) 論理演算子を追加します。 
    
- ドラッグ アンド ドロップを使用して、条件を並び替えることができます。 条件のコントロールをクリックするだけで上または下に移動できます。
    
- 前述のとおり、いくつかの条件プロパティでは複数の値を入力することができます。 各値は **OR** 演算子によって論理的に接続されます。 これは、同じ条件の複数のインスタンス (値はそれぞれ 1 つ) の場合と同じロジックになります。 次の図は、複数の値を持つ 1 つの条件の例と、1 つの値を持つ (同じプロパティの) 複数の条件の例を示しています。 両方の例は、同じクエリになります。`(filetype="docx") OR (filetype="pptx") OR (filetype="xlsx")`
    
    ![メッセージは、ルールのすべての条件に一致しなければなりません。別々の条件に一致させる必要がある場合は、条件ごとに個別のルールを使用します。たとえば、ファイルが添付されたメッセージと、コンテンツがパターンと一致するメッセージに同じ免責事項を追加するには、それぞれの条件ごとに 1 つのルールを作成します。ルールは簡単にコピーできます。](media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![同じプロパティに対する複数の検索条件](media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> 条件が複数の値を受け入れる場合、1 つの条件を使用し、(コンマまたはセミコロンで区切って) 複数の値を指定することをお勧めします。これにより、適用されるクエリ ロジックが確実に意図するものとなるようにすることができます。 
  
### <a name="examples-of-using-conditions-in-search-queries"></a>例

次の例は、条件を使用した検索クエリの GUI ベースのバージョン、および選択した検索の詳細ウィンドウに表示される検索クエリ構文 ( **new-compliancesearch**コマンドレットによっても返されます) と、対応する KQL クエリ。 
  
#### <a name="example-1"></a>例 1

この例では、クレジットカード番号が含まれ、2016年1月1日より前に最終変更された SharePoint および OneDrive for business サイトのドキュメントを返します。
  
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

この例では、12/1/2016 と11/30/2016 の間に送信され、"phone" または "smartphone" で始まる単語を含む電子メールメッセージまたは予定表会議を返します。
  
 **GUI**
  
![検索条件の 3 番目の例](media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **検索クエリ構文**
  
 `phone* OR smartphone*(c:c)(sent=2016-12-01..2016-11-30)(kind="email")(kind="meetings")`
  
 **検索クエリ ロジック**
  
 `phone* OR smartphone* AND (sent=2016-12-01..2016-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="searching-for-site-content-shared-with-external-users"></a>外部ユーザーと共有されているサイト コンテンツの検索

また、セキュリティ & コンプライアンスセンターのコンテンツ検索機能を使用して、組織外のユーザーと共有している SharePoint および OneDrive for business サイトに保存されているドキュメントを検索することもできます。 これにより、組織外で共有されている重要な情報や機密情報を識別できます。 これを行うには、キーワード`ViewableByExternalUsers`クエリでプロパティを使用します。 このプロパティは、次のいずれかの共有方法を使用して、外部ユーザーと共有されているドキュメントまたはサイトを返します。 
  
- ユーザーが認証されたユーザーとして組織にサインインすることを要求する共有の招待。
    
- 匿名ゲストリンク。このリンクを持つすべてのユーザーが、認証なしでリソースにアクセスできるようにします。
    
次に例を示します。
  
- このクエリ`ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"`は、組織外のユーザーと共有されていて、クレジットカード番号が含まれているすべてのアイテムを返します。 
    
- このクエリ`ViewableByExternalUsers:true AND ContentType:document AND site:"https://contoso.sharepoint.com/Sites/Teams"`は、外部ユーザーと共有されている、組織内のすべてのチームサイトのドキュメントの一覧を返します。 
    
> [!TIP]
> 検索クエリでは、 `ViewableByExternalUsers:true AND ContentType:document`検索結果に多くの .aspx ファイルが返されることがあります。 これら (または他の種類のファイル) を削除するには`FileExtension` 、プロパティを使用して特定のファイルの種類を除外できます。例`ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx`を示します。 
  
組織外のユーザーと共有されているコンテンツとはどのようなものですか。 組織の SharePoint および OneDrive for Business サイト内のドキュメント。共有への招待を送信するか、またはパブリックの場所で共有されます。 たとえば、次のユーザーアクティビティは、外部ユーザーに表示されるコンテンツになります。
  
- ユーザーが組織外のユーザーとファイルやフォルダーを共有する。
    
- ユーザーが共有ファイルへのリンクを作成し、組織外のユーザーに送信する。 外部ユーザーはこのリンクからファイルを表示 (または編集) できるようになります。
    
- ユーザーが、共有ファイルを表示 (または編集) するための共有への招待やゲスト リンクを組織外のユーザーに送信する。
    
### <a name="issues-using-the-viewablebyexternalusers-property"></a>ViewableByExternalUsers プロパティを使用した問題

この`ViewableByExternalUsers`プロパティは、ドキュメントまたはサイトが外部ユーザーと共有されているかどうかの状態を表しますが、このプロパティが何をしていても反映されないいくつかの注意点があります。 次のシナリオでは、 `ViewableByExternalUsers`プロパティの値は更新されず、このプロパティを使用するコンテンツ検索クエリの結果が正しくない可能性があります。 
  
- サイトまたは組織の外部共有をオフにするなど、共有ポリシーに対する変更。 このプロパティには、外部アクセスが取り消された場合でも、以前共有されていたドキュメントが外部からアクセス可能であると表示されます。
    
- Office 365 グループまたは Office 365 セキュリティグループに外部ユーザーを追加したり、削除したりするなど、グループメンバーシップに対する変更。 このプロパティは、そのグループがアクセス権を持つアイテムに対して自動的には更新されません。
    
- 受信者が招待を受け入れていないために、共有への招待を外部ユーザーに送信しているため、まだコンテンツにアクセスできません。
    
このようなシナリオで`ViewableByExternalUsers`は、サイトまたはドキュメントライブラリが再クロールされてインデックスが再作成されるまで、プロパティは現在の共有の状態を反映しません。 

## <a name="searching-for-site-content-shared-within-your-organization"></a>組織内で共有しているサイトコンテンツを検索する

前述したように、この`SharedWithUsersOWSUser`プロパティを使用すると、組織内のユーザー間で共有されているドキュメントを検索できます。 ユーザーが自分の組織内の別のユーザーとファイル (またはフォルダー) を共有すると、共有ファイルへの**** リンクが、そのファイルが共有されていたユーザーの OneDrive for business アカウントの OneDrive for business アカウントに表示されます。 たとえば、Sara Davis と共有されているドキュメントを検索するには、クエリ`SharedWithUsersOWSUser:"sarad@contoso.com"`を使用できます。 この検索の結果をエクスポートすると、元のドキュメント (Sara を使用してドキュメントを共有しているユーザーのコンテンツの場所にあります) がダウンロードされます。
  
`SharedWithUsersOWSUser`プロパティを使用するときに、検索結果で返される特定のユーザーとドキュメントを明示的に共有する必要があることに注意してください。 たとえば、ユーザーが自分の OneDrive アカウントでドキュメントを共有している場合、そのユーザーは、組織内または組織外のユーザーと共有したり、組織内のユーザーと共有したり、特定のユーザーと共有したりすることができます。 OneDrive の [**共有**] ウィンドウのスクリーンショットでは、3つの共有オプションが表示されています。 
  
![SharedWithUsersOWSUser プロパティを使用する検索クエリによって、特定のユーザーと共有されているファイルのみが返されます。](media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
この`SharedWithUsersOWSUser`プロパティを使用する検索クエリでは、3番目のオプション (**特定のユーザー**と共有) を使用して共有されているドキュメントのみが返されます。 

## <a name="searching-for-skype-for-business-conversations"></a>Skype for Business の会話を検索する

次のキーワードクエリを使用して、Skype for Business の会話で特にコンテンツを検索することができます。

```
kind:im
```

メモ以前の検索クエリは、Microsoft Teams からのチャットも返します。 これを防ぐには、次のキーワードクエリを使用して、Skype for Business の会話のみを含めるように検索結果を絞り込むことができます。

```
kind:im AND subject:conversation
```

前のキーワードクエリでは、Microsoft Teams のチャットが除外されています。 Skype for Business の会話は、"会話" という件名で始まる件名の電子メールメッセージとして保存されるためです。

特定の日付範囲内で発生した Skype for Business の会話を検索するには、次のキーワードクエリを使用します。

```
kind:im AND subject:conversation AND (received=startdate..enddate)
```

## <a name="search-tips-and-tricks"></a>検索のヒントと秘訣

- キーワード検索では大文字と小文字は区別されません。たとえば、「**cat**」と「**CAT**」では同じ結果が返されます。 
    
- ブール演算子**AND**、 **OR**、 **NOT**、 **NEAR**、 **onear**は大文字である必要があります。 
    
- A space between two keywords or two  `property:value` expressions is the same as using **AND**. たとえば、次`from:"Sara Davis" subject:reorganization`の例では、件名行に "再編成" が含まれている Sara Davis が送信したすべてのメッセージを返します。 
    
- 形式に`property:value`一致する構文を使用します。 値の大文字と小文字は区別されず、演算子の後にスペースを含めることはできません。 スペースがある場合、目的の値はフルテキスト検索だけになります。 たとえば`to: pilarp` 、pilarp がに送信されたメッセージではなく、キーワードとして "pilarp が" を検索します。 
    
- To、From、Cc、Recipients などの受信者プロパティを検索するとき、SMTP アドレス、別名、または表示名を使用して受信者を指定できます。たとえば、pilarp@contoso.com、pilarp、または "Pilar Pinilla" を使用できます。
    
- プレフィックスワイルドカード検索のみ使用できます。例: **cat\* **または**set\***。 サフィックス検索 ( ** \*cat** )、挿入辞検索 **(\*c t** )、および部分文字列検索 ( ** \*\* cat** ) はサポートされていません。 
    
- プロパティを検索するときに、検索値が複数の単語で構成されている場合は、二重引用符 ("") を使用します。 たとえば、 `subject:budget Q1` [件名] 行に**予算**が含まれているメッセージを返します。また、メッセージの [Q1] または [ **Q1** ] を含むメッセージのいずれかのプロパティを取得します。 Using `subject:"budget Q1"`は、[件名の後のすべての場所にある**予算 (四半期**) を含むすべてのメッセージを返します。 
    
- 特定のプロパティ値でマークされているコンテンツを検索結果から除外するには、プロパティの名前の前にマイナス記号 (-) を置きます。 たとえば、は`-from:"Sara Davis"` 、Sara Davis によって送信されたメッセージを除外します。

- 一部の特殊文字は検索インデックスに含まれていないため検索できないため、検索演算子 (+-=) を含みます (+-=:)また、次の文字は $null に置き換えられます。また、検索した場合は、エラーが発生することがあります。 @ #% ^ &;_ / ?

- アイテムは、メッセージの種類に基づいてエクスポートできます。 たとえば、Microsoft Teams で Skype の会話とチャットをエクスポートするには、 `kind:im`構文を使用します。 電子メールメッセージのみを返すには、 `kind:email`を使用します。 Microsoft Teams でチャット、会議、通話を取得するには`kind:microsoftteams`、を使用します。
