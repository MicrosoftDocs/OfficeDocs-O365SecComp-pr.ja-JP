---
title: Office 365 監査ログの詳細なプロパティ
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: Office 365 監査ログ レコードに含まれている追加のプロパティについて説明します。
ms.openlocfilehash: f64b514b777c08048e0f904c17e21c235f8a6f23
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000330"
---
# <a name="detailed-properties-in-the-office-365-audit-log"></a>Office 365 監査ログの詳細なプロパティ

セキュリティ & コンプライアンスセンターから監査ログ検索の結果をエクスポートする場合、検索条件に一致するすべての結果をダウンロードするオプションがあります。 これを行うには、[**結果** \>のエクスポート] を選択して、[**監査ログの検索**] ページにある**すべての結果をダウンロード**します。 詳細については、「 [Office 365 での監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。
  
 監査ログの検索結果をすべてエクスポートする場合、Office 365 の統合監査ログの生データがコンマ区切り値 (CSV) ファイルにコピーされ、そのファイルがローカル コンピューターにダウンロードされます。ダウンロードされたファイル内の **[詳細]** という列には、監査ログ エントリから追加情報が取り込まれます。この列には、監査ログ レコードの複数のプロパティを表す複数値プロパティが含まれます。この複数値プロパティ内の**プロパティ:値**のそれぞれのペアはコンマで区切られています。 
  
次の表に、この複数値プロパティ列 **[詳細]** に格納されるプロパティ (イベントが発生した Office 365 サービスによって異なります) の説明を記載します。**このプロパティ列を使用する Office 365 サービス**では、該当するプロパティを含むアクティビティ (ユーザーまたは管理者) のサービスと種類が示されます。これらのプロパティやこのトピックには記載されていない可能性があるプロパティの詳細については、「[Office 365 管理アクティビティ API のスキーマ](https://go.microsoft.com/fwlink/p/?LinkId=717993)」をご覧ください。
  
> [!TIP]
> Excel で Power Query を使用すると、この列を複数の列に分割して、それぞれのプロパティを個別の列に表示できます。このように分割すると、1 つまたは複数のプロパティに基づく並び替えやフィルター処理が可能になります。分割方法については、「[テキストの列を分割する (Power Query)](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662)」のセクション「列を区切り記号で分割する」をご覧ください。 
  
|**プロパティ**|**説明**|**このプロパティを使用する Office 365 サービス**|
|:-----|:-----|:-----|
|Actor|アクションを実行したユーザーまたはサービス アカウント。|Azure Active Directory|
|AddOnName|チームで追加、削除、または更新されたアドオンの名前。Microsoft Teams でのアドオンの種類は、ボット、コネクタ、またはタブです。|Microsoft Teams|
|AddOnType|チームで追加、削除、または更新されたアドオンの種類。次の値によって、アドオンの種類が示されます。<br/> **1** -ボットを意味します。<br/> **2** -コネクタを意味します。<br/> **3** -タブを意味します。|Microsoft Teams|
|AzureActiveDirectoryEventType|Azure Active Directory のイベントの種類。次の値によって、イベントの種類が示されます。<br/> **0** - アカウント ログイン イベントを意味します。<br/> **1** - Azure アプリケーション セキュリティ イベントを意味します。|Azure Active Directory|
|ChannelGuid|Microsoft Teams のチャネルの ID。チャネルが置かれているチームは、**TeamName** プロパティと **TeamGuid** プロパティによって識別されます。|Microsoft Teams|
|ChannelName|Microsoft Teams のチャネルの名前。チャネルが置かれているチームは、**TeamName** プロパティと **TeamGuid** プロパティによって識別されます。|Microsoft Teams|
|Client|ログイン イベントに使用されたクライアント デバイスと、そのデバイスの OS およびブラウザー (例: Nokia Lumia 920、Windows Phone 8、IE Mobile 11)。|Azure Active Directory|
|ClientInfoString|操作を実行するために使用されたメール クライアントに関する情報 (ブラウザーのバージョン、Outlook のバージョン、およびモバイル デバイスの情報など)。|Exchange (メールボックス アクティビティ)|
|ClientIP|アクティビティがログに記録されたときに使用されたデバイスの IP アドレス。IP アドレスは、IPv4 または IPv6 アドレスの形式で表示されます。|Exchange と Azure Active Directory|
|ClientIPAddress|ClientIP と同じ。|SharePoint|
|CreationTime|ユーザーがアクティビティを実行した、世界協定時刻 (UTC) での日時。|すべて|
|DestinationFileExtension|コピーまたは移動されたファイルのファイル拡張子。このプロパティは、FileCopied および FileMoved ユーザー アクティビティに対してのみ表示されます。|SharePoint|
|DestinationFileName|コピーまたは移動されたファイルの名前。このプロパティは、FileCopied および FileMoved アクションに対してのみ表示されます。|SharePoint|
|DestinationRelativeUrl|ファイルのコピー先または移動先フォルダーの URL。**SiteURL**、**DestinationRelativeURL**、および **DestinationFileName** プロパティの値の組み合わせは、**ObjectID** プロパティの値と同じであり、コピーされたファイルの完全パス名です。このプロパティは、FileCopied および FileMoved ユーザー アクティビティに対してのみ表示されます。|SharePoint|
|EventSource|SharePoint でイベントが発生したことを示します。有効な値は、**SharePoint** と **ObjectModel** です。|SharePoint|
|ExternalAccess|Exchange 管理者のアクティビティの場合は、組織内のユーザー、Microsoft データセンター担当者またはデータセンター サービス アカウント、あるいは代理管理者によってコマンドレットが実行されたことを示します。値 **False** は、コマンドレットが組織内のユーザーによって実行されたことを意味します。値 **True** は、コマンドレットがデータセンター担当者、データセンター サービス アカウント、または代理管理者によって実行されたことを意味します。<br/> Exchange メールボックス アクティビティの場合は、メールボックスにアクセスしたのが組織外のユーザーであるかどうかを示します。|Exchange|
|ExtendedProperties|Azure Active Directory イベントの拡張プロパティ。|Azure Active Directory|
|ID|レポート エントリの ID。この ID は、レポート エントリを一意に識別します。|すべて|
|InternalLogonType|内部使用のため予約済み。|Exchange (メールボックス アクティビティ)|
|ItemType|アクセスまたは変更されたオブジェクトの種類。有効な値は、**File**、**Folder**、**Web**、**Site**、**Tenant**、**DocumentLibrary** です。|SharePoint|
|LoginStatus|発生した可能性のあるログイン失敗を識別します。|Azure Active Directory|
|LogonType|メールボックス アクセスの種類。次の値によって、メールボックスにアクセスしたユーザーの種類が示されます。<br/><br/> **0** - メールボックスの所有者を意味します。<br/> **1** - 管理者を意味します。<br/> **2** - 代理人を意味します。 <br/>**3** - Microsoft データセンターのトランスポート サービスを意味します。<br/> **4** - Microsoft データセンターのサービス アカウントを意味します。 <br/>**6** - 代理管理者を意味します。|Exchange (メールボックス アクティビティ)|
|MailboxGuid|アクセスされたメールボックスの Exchange GUID。|Exchange (メールボックス アクティビティ)|
|MailboxOwnerUPN|アクセスされたメールボックスの所有者のメール アドレス。|Exchange (メールボックス アクティビティ)|
|Members|チームで追加または削除されたユーザーが一覧表示されます。次の値によって、ユーザーに割り当てられているロールの種類が示されます。<br/><br/> **1** - 所有者ロールを意味します。<br/> **2** - メンバー ロールを意味します。<br/> **3** - ゲスト ロールを意味します。 <br/><br/>Members プロパティには、組織の名前とメンバーのメール アドレスも含まれます。|Microsoft Teams|
|ModifiedProperties (Name、NewValue、OldValue)|このプロパティは、管理イベント (サイトまたはサイト コレクションの管理者グループのメンバーとしてユーザーを追加するなど) に対して表示されます。このプロパティには、変更されたプロパティの名前 (サイト管理者グループなど)、変更されたプロパティの新しい値 (サイト管理者として追加されたユーザーなど)、および変更されたオブジェクトの以前の値が格納されます。|すべて (管理者のアクティビティ)|
|ObjectID|Exchange 管理者監査ログの場合は、コマンドレットによって変更されたオブジェクトの名前。  <br/> SharePoint アクティビティの場合は、ユーザーがアクセスしたファイルまたはフォルダーの完全な URL パス名。  <br/> Azure AD アクティビティの場合は、変更されたユーザー アカウントの名前。|すべて|
|Operation|ユーザーまたは管理者アクティビティの名前。 このプロパティの値は、[**アクティビティ**] ドロップダウンリストで選択された値に対応しています。 [**すべてのアクティビティの結果を表示]** が選択されている場合、すべてのサービスのすべてのユーザーと管理者のアクティビティのエントリがレポートに含まれます。 office 365 監査ログに記録される操作/アクティビティの説明については、「 [office 365 で監査ログを検索](search-the-audit-log-in-security-and-compliance.md)する」の「監査**対象のアクティビティ**」タブを参照してください。  <br/> Exchange 管理者のアクティビティの場合、このプロパティは実行されたコマンドレットの名前を示します。|すべて|
|OrganizationID|Office 365 組織の GUID。|すべて|
|Path|アクセスされたメッセージが置かれているメールボックス フォルダーの名前。このプロパティは、メッセージの作成先、コピー先、移動先のフォルダーも識別します。|Exchange (メールボックス アクティビティ)|
|Parameters|Exchange 管理者のアクティビティの場合、Operation プロパティで識別されたコマンドレットで使用された、すべてのパラメーターの名前と値。|Exchange (管理者のアクティビティ)|
|RecordType|レコードで示されている操作の種類。次の値によって、レコードの種類が示されます。<br/><br/> **1** - Exchange 管理者監査ログのレコードを意味します。 <br/>**2** - Exchange メールボックス監査ログの、単一のメールボックス アイテムに対して行われた操作に関するレコードを意味します。 <br/>**3** - この値も Exchange 管理者監査ログのレコードを意味します。ただし、このレコードの種類は、ソース メールボックス内の複数のアイテムに対して操作が行われたこと (複数のアイテムを削除済みアイテム フォルダーに移動する操作や、複数のアイテムを完全に削除する操作など) を意味します。<br/>**4** - SharePoint でのサイト管理者の操作 (管理者またはユーザーがサイトに対するアクセス許可を割り当てるなど) を意味します。 <br/>**6** - SharePoint でのファイルまたはフォルダーに関連する操作 (ユーザーの表示、ファイルの変更など) を意味します。 <br/>**8** - Azure Active Directory で行われた管理者の操作を意味します。 <br/>**9** - Azure Active Directory での OrgId ログオン イベントを意味します。このレコードの種類は非推奨となっています。<br/>**10** - データ センターで Microsoft 担当者が行ったセキュリティ コマンドレット イベントを意味します。 <br/>**11** - SharePoint でのデータ損失防止 (DLP) イベントを意味します。<br/> **12** - Sway のイベントを意味します。 <br/>**13** -統合された dlp ポリシーを使用して構成した場合、Exchange の dlp イベントを示します。 Exchange メールフロールール (トランスポートルールとも呼ばれる) に基づく DLP イベントはサポートされていません。<br>**14** - SharePoint の共有イベントを意味します。<br/> **15** - Azure Active Directory の Secure Token Service (STS) ログオン イベントを意味します。 <br/>**18** -セキュリティ & コンプライアンスセンターイベントを示します。 <br/>**20** - Power BI のイベントを意味します。 <br/>**21**- Dynamics 365 のイベントを意味します。<br/>**22** - Yammer のイベントを意味します。 <br/>**23** - Skype for Business のイベントを意味します。 <br/>**24** -電子情報開示イベントを示します。 このレコードの種類は、セキュリティ/コンプライアンスセンターでコンテンツ検索を実行し、電子情報開示ケースを管理することによって実行されたアクティビティを示します。 詳細については、「 [Office 365 監査ログで電子情報開示アクティビティを検索](search-for-ediscovery-activities-in-the-audit-log.md)する」を参照してください。<br/>**25、26、27** - Microsoft Teams のイベントを意味します。 <br/>**28** - Exchange Online Protection イベントと Office 365 Advanced Threat Protection イベントからのフィッシングとマルウェアのイベントを意味します。<br/> **30** - Microsoft Flow のイベントを意味します。<br/> **32** - Microsoft Stream のイベントを意味します。<br/> **35** - Microsoft Project のイベントを意味します。 <br/> **36** - Sharepoint リストのイベントを意味します。<br/> **38** -セキュリティ/コンプライアンスセンターのアイテム保持ポリシーと保持ラベルに関連するイベントを示します。  <br/>**40** - セキュリティ/コンプライアンス アラートのシグナルに起因するイベントを意味します。<br/> **41** - Office 365 Advanced Threat Protection でのブロック時の安全なリンクと上書きのブロック イベントを意味します。<br/>**44** - Workplace Analytics のイベントを意味します。 <br/>**45** -PowerApps アプリイベントを示します。 <br/> **47** - SharePoint、OneDrive、Microsoft Teams 内のファイルに対する、Office 365 Advanced Threat Protection からのフィッシングとマルウェアのイベントを意味します。|すべて|
|ResultStatus|(**Operation** プロパティで指定された) アクションが正常に終了したかどうかを示します。  <br/> Exchange 管理者アクティビティでは、値は **True** (成功) または **False** (失敗) のいずれかになります。|すべて  <br/>|
|SecurityComplianceCenterEventType|アクティビティがセキュリティ & コンプライアンスセンターイベントであったことを示します。 このプロパティでは、すべてのセキュリティ & コンプライアンスセンターアクティビティの値は**0**になります。|セキュリティ センターとコンプライアンス センター|
|SharingType|リソースが共有されたユーザーに割り当てられているアクセス許可の種類。このユーザーは、**UserSharedWith** プロパティによって識別されます。|SharePoint|
|Site|ユーザーがアクセスしたファイルまたはフォルダーが置かれているサイトの GUID。|SharePoint|
|SiteUrl|ユーザーがアクセスしたファイルまたはフォルダーが置かれているサイトの URL。|SharePoint|
|SourceFileExtension|ユーザーがアクセスしたファイルのファイル拡張子。このプロパティは、アクセスされたオブジェクトがフォルダーの場合には、空白になります。|SharePoint|
|SourceFileName|ユーザーがアクセスしたファイルまたはフォルダーの名前。|SharePoint|
|SourceRelativeUrl|ユーザーがアクセスしたファイルが格納されているフォルダーの URL。**SiteURL**、**SourceRelativeURL**、および **SourceFileName** のプロパティの値の組み合わせは、**ObjectID** プロパティの値と同じであり、ユーザーがアクセスしたファイルの完全パス名です。|SharePoint|
|Subject|アクセスされたメッセージの件名。|Exchange (メールボックス アクティビティ)|
|TabType| チームで追加、削除、または更新されたタブの種類。このプロパティの有効な値は次のとおりです。<br/><br/> **Excelpin** - Excel のタブ。  <br/> **Extension** - すべてのファースト パーティおよびサード パーティのアプリ (Planner、VSTS、Forms など)。  <br/> **Notes** - OneNote のタブ。  <br/> **Pdfpin** - PDF のタブ。  <br/> **Powerbi** - PowerBI のタブ。  <br/> **Powerpointpin** - PowerPoint のタブ。  <br/> **Sharepointfiles** - SharePoint のタブ。  <br/> **Webpage** - ピン留めされた Web サイトのタブ。  <br/> **Wiki-tab** - Wiki のタブ。  <br/> **Wordpin** - Word のタブ。|Microsoft Teams|
|Target|(**Operation** プロパティで識別された) アクションの実行対象となったユーザー。たとえば、SharePoint または Microsoft Team にゲスト ユーザーが追加されると、このプロパティにそのユーザーが一覧表示されます。|Azure Active Directory|
|TeamGuid|Microsoft Teams のチームの ID。|Microsoft Teams|
|TeamName|Microsoft Teams のチームの名前。|Microsoft Teams|
|UserAgent|ユーザーのブラウザーに関する情報。この情報は、ブラウザーによって提供されます。|SharePoint|
|UserDomain|アクションを実行したユーザー (アクター) のテナント組織に関する情報を示します。|Azure Active Directory|
|UserID|レコードがログに記録される原因となった、(**Operation** プロパティで指定された) アクションを実行したユーザー。監査ログには、システム アカウント (SHAREPOINT\system または NT AUTHORITY\SYSTEM など) で実行されたアクティビティのレコードも含まれることに注意してください。|すべて|
|UserKey|**UserID** プロパティで識別されたユーザーの別の ID。このプロパティには、たとえば SharePoint でユーザーによって発生したイベントの Passport 固有 ID (PUID) が格納されます。このプロパティは、他のサービスで発生したイベントや、システム アカウントによって発生したイベントの **UserID** プロパティと同じ値を示す場合もあります。|すべて|
|UserSharedWith|リソースが共有されたユーザー。**Operation** プロパティの値が **SharingSet** の場合は、このプロパティが含まれます。このユーザーは、レポートの **[共有ユーザー]** 列にも表示されます。|SharePoint|
|UserType|操作を実行したユーザーの種類。次の値によって、ユーザーの種類が示されます。<br/> <br/> **0** - 標準のユーザー。 <br/>**2** - Office 365 組織の管理者。 <br/>**3** - Microsoft データセンター管理者またはデータセンターのシステム アカウント。 <br/>**4** - システム アカウント。 <br/>**5** - アプリケーション。 <br/>**6** - サービス プリンシパル。<br/>**7** - カスタム ポリシー。<br/>**8** - システム ポリシー。|すべて|
|Version|ログに記録された (**Operation** プロパティで識別された) アクティビティのバージョン番号を示します。|すべて|
|Workload|アクティビティが発生した Office 365 サービス。このプロパティの有効な値は次のとおりです。<br/> <br/>**SharePoint<br/>OneDrive<br/>Exchange<br/>AzureActiveDirectory<br/>DataCenterSecurity<br/>Compliance<br/>Sway<br/>Skype for Business<br/>SecurityComplianceCenter<br/>PowerBI<br/>CRM<br/>Yammer<br/>MicrosoftTeams<br/>ThreatIntelligence<br/>MicrosoftFlow<br/>MicrosoftStream<br/>DlpSharePointClassificationData<br/>Project<br/>PowerApps<br/>Workplace Analytics**|すべて|
||||
   
上記のプロパティは、特定のイベントの詳細が表示されている状態で **[詳細情報]** をクリックした場合にも表示されます。 
  
![[詳細情報] をクリックして監査ログのイベント レコードの詳細なプロパティを表示する](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
  

