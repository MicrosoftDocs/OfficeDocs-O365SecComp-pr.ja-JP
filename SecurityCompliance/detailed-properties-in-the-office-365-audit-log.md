---
title: Office 365 監査ログの詳細なプロパティ
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: Office 365 監査ログ レコードに含まれている追加のプロパティについて説明します。
ms.openlocfilehash: 0c50001a51c0b4097da1080c9dc1f9247506dd08
ms.sourcegitcommit: ca97beff215d154b6ab006ce1222056434fde1a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2019
ms.locfileid: "29740859"
---
# <a name="detailed-properties-in-the-office-365-audit-log"></a>Office 365 監査ログの詳細なプロパティ

Office 365 のセキュリティ/コンプライアンス センターから監査ログの検索結果をエクスポートする際は、検索条件を満たすすべての結果をダウンロードするオプションを選択できます。このオプションを使用するには、セキュリティ/コンプライアンス センターの **[監査ログ検索]** ページで、**[結果のエクスポート]** \> **[すべての結果をダウンロードする]** を選択します。詳細については、「[Office 365 セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)」をご覧ください。
  
 監査ログの検索結果をすべてエクスポートする場合、Office 365 の統合監査ログの生データがコンマ区切り値 (CSV) ファイルにコピーされ、そのファイルがローカル コンピューターにダウンロードされます。ダウンロードされたファイル内の **[詳細]** という列には、監査ログ エントリから追加情報が取り込まれます。この列には、監査ログ レコードの複数のプロパティを表す複数値プロパティが含まれます。この複数値プロパティ内の**プロパティ:値**のそれぞれのペアはコンマで区切られています。 
  
次の表に、この複数値プロパティ列 **[詳細]** に格納されるプロパティ (イベントが発生した Office 365 サービスによって異なります) の説明を記載します。**このプロパティ列を使用する Office 365 サービス**では、該当するプロパティを含むアクティビティ (ユーザーまたは管理者) のサービスと種類が示されます。これらのプロパティやこのトピックには記載されていない可能性があるプロパティの詳細については、「[Office 365 管理アクティビティ API のスキーマ](https://go.microsoft.com/fwlink/p/?LinkId=717993)」をご覧ください。
  
> [!TIP]
> Excel で Power Query を使用すると、この列を複数の列に分割して、それぞれのプロパティを個別の列に表示できます。このように分割すると、1 つまたは複数のプロパティに基づく並び替えやフィルター処理が可能になります。分割方法については、「[テキストの列を分割する (Power Query)](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662)」のセクション「列を区切り記号で分割する」をご覧ください。 
  
|**プロパティ**|**説明**|**このプロパティを使用する Office 365 サービス**|
|:-----|:-----|:-----|
|Actor  <br/> |アクションを実行したユーザーまたはサービス アカウント。 |Azure Active Directory  <br/> |
|AddOnName  <br/> |チームで追加、削除、または更新されたアドオンの名前。Microsoft Teams でのアドオンの種類は、ボット、コネクタ、またはタブです。  <br/> |Microsoft Teams  <br/> |
|AddOnType  <br/> |チームで追加、削除、または更新されたアドオンの種類。次の値によって、アドオンの種類が示されます。<br/> **1** -ボットを意味します。<br/> **2** -コネクタを意味します。<br/> **3** -タブを意味します。 |Microsoft Teams  <br/> |
|AzureActiveDirectoryEventType  <br/> |Azure Active Directory のイベントの種類。次の値によって、イベントの種類が示されます。<br/> **0** - アカウント ログイン イベントを意味します。<br/> **1** - Azure アプリケーション セキュリティ イベントを意味します。 |Azure Active Directory  <br/> |
|ChannelGuid  <br/> |Microsoft Teams のチャネルの ID。チャネルが置かれているチームは、**TeamName** プロパティと **TeamGuid** プロパティによって識別されます。<br/> |Microsoft Teams  <br/> |
|ChannelName  <br/> |Microsoft Teams のチャネルの名前。チャネルが置かれているチームは、**TeamName** プロパティと **TeamGuid** プロパティによって識別されます。<br/> |Microsoft Teams  <br/> |
|Client  <br/> |ログイン イベントに使用されたクライアント デバイスと、そのデバイスの OS およびブラウザー (例: Nokia Lumia 920、Windows Phone 8、IE Mobile 11)。  <br/> |Azure Active Directory  <br/> |
|ClientInfoString  <br/> |操作を実行するために使用されたメール クライアントに関する情報 (ブラウザーのバージョン、Outlook のバージョン、およびモバイル デバイスの情報など)。  <br/> |Exchange (メールボックス アクティビティ)  <br/> |
|ClientIP  <br/> |アクティビティがログに記録されたときに使用されたデバイスの IP アドレス。IP アドレスは、IPv4 または IPv6 アドレスの形式で表示されます。  <br/> |Exchange と Azure Active Directory  <br/> |
|ClientIPAddress  <br/> |ClientIP と同じ。  <br/> |SharePoint  <br/> |
|CreationTime  <br/> |ユーザーがアクティビティを実行した、世界協定時刻 (UTC) での日時。  <br/> |すべて  <br/> |
|DestinationFileExtension  <br/> |コピーまたは移動されたファイルのファイル拡張子。このプロパティは、FileCopied および FileMoved ユーザー アクティビティに対してのみ表示されます。  <br/> |SharePoint  <br/> |
|DestinationFileName  <br/> |コピーまたは移動されたファイルの名前。このプロパティは、FileCopied および FileMoved アクションに対してのみ表示されます。  <br/> |SharePoint  <br/> |
|DestinationRelativeUrl  <br/> |ファイルのコピー先または移動先フォルダーの URL。**SiteURL**、**DestinationRelativeURL**、および **DestinationFileName** プロパティの値の組み合わせは、**ObjectID** プロパティの値と同じであり、コピーされたファイルの完全パス名です。このプロパティは、FileCopied および FileMoved ユーザー アクティビティに対してのみ表示されます。<br/> |SharePoint  <br/> |
|EventSource  <br/> |SharePoint でイベントが発生したことを示します。有効な値は、**SharePoint** と **ObjectModel** です。<br/> |SharePoint  <br/> |
|ExternalAccess  <br/> |Exchange 管理者のアクティビティの場合は、組織内のユーザー、Microsoft データセンター担当者またはデータセンター サービス アカウント、あるいは代理管理者によってコマンドレットが実行されたことを示します。値 **False** は、コマンドレットが組織内のユーザーによって実行されたことを意味します。値 **True** は、コマンドレットがデータセンター担当者、データセンター サービス アカウント、または代理管理者によって実行されたことを意味します。<br/> Exchange メールボックス アクティビティの場合は、メールボックスにアクセスしたのが組織外のユーザーであるかどうかを示します。  <br/> |Exchange  <br/> |
|ExtendedProperties  <br/> |Azure Active Directory イベントの拡張プロパティ。  <br/> |Azure Active Directory  <br/> |
|ID  <br/> |レポート エントリの ID。この ID は、レポート エントリを一意に識別します。  <br/> |すべて  <br/> |
|InternalLogonType  <br/> |内部使用のため予約済み。  <br/> |Exchange (メールボックス アクティビティ)  <br/> |
|ItemType  <br/> |アクセスまたは変更されたオブジェクトの種類。有効な値は、**File**、**Folder**、**Web**、**Site**、**Tenant**、**DocumentLibrary** です。<br/> |SharePoint  <br/> |
|LoginStatus  <br/> |発生した可能性のあるログイン失敗を識別します。  <br/> |Azure Active Directory  <br/> |
|LogonType  <br/> |メールボックス アクセスの種類。次の値によって、メールボックスにアクセスしたユーザーの種類が示されます。<br/><br/> **0** - メールボックスの所有者を意味します。<br/> **1** - 管理者を意味します。<br/> **2** - 代理人を意味します。 <br/>**3** - Microsoft データセンターのトランスポート サービスを意味します。<br/> **4** - Microsoft データセンターのサービス アカウントを意味します。 <br/>**6** - 代理管理者を意味します。 |Exchange (メールボックス アクティビティ)  <br/> |
|MailboxGuid  <br/> |アクセスされたメールボックスの Exchange GUID。  <br/> |Exchange (メールボックス アクティビティ)  <br/> |
|MailboxOwnerUPN  <br/> |アクセスされたメールボックスの所有者のメール アドレス。  <br/> |Exchange (メールボックス アクティビティ)  <br/> |
|Members  <br/> |チームで追加または削除されたユーザーが一覧表示されます。次の値によって、ユーザーに割り当てられているロールの種類が示されます。<br/><br/> **1** - 所有者ロールを意味します。<br/> **2** - メンバー ロールを意味します。<br/> **3** - ゲスト ロールを意味します。 <br/><br/>Members プロパティには、組織の名前とメンバーのメール アドレスも含まれます。  <br/> |Microsoft Teams  <br/> |
|ModifiedProperties (Name、NewValue、OldValue)  <br/> |このプロパティは、管理イベント (サイトまたはサイト コレクションの管理者グループのメンバーとしてユーザーを追加するなど) に対して表示されます。このプロパティには、変更されたプロパティの名前 (サイト管理者グループなど)、変更されたプロパティの新しい値 (サイト管理者として追加されたユーザーなど)、および変更されたオブジェクトの以前の値が格納されます。  <br/> |すべて (管理者のアクティビティ)  <br/> |
|ObjectID  <br/> |Exchange 管理者監査ログの場合は、コマンドレットによって変更されたオブジェクトの名前。  <br/> SharePoint アクティビティの場合は、ユーザーがアクセスしたファイルまたはフォルダーの完全な URL パス名。  <br/> Azure AD アクティビティの場合は、変更されたユーザー アカウントの名前。  <br/> |すべて  <br/> |
|Operation  <br/> |ユーザーまたは管理者のアクティビティの名前。このプロパティの値は、**[アクティビティ]** ドロップダウン リストで選択された値に対応します。**[すべてのアクティビティの結果を表示]** が選択された場合、すべてのサービスでのすべてのユーザーと管理者のアクティビティがレポートに含まれます。Office 365 監査ログに記録される操作やアクティビティについては、「[Office 365 セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)」の「**監査されるアクティビティ**」タブをご覧ください。<br/> Exchange 管理者のアクティビティの場合、このプロパティは実行されたコマンドレットの名前を示します。  <br/> |すべて  <br/> |
|OrganizationID  <br/> |Office 365 組織の GUID。  <br/> |すべて  <br/> |
|Path  <br/> |アクセスされたメッセージが置かれているメールボックス フォルダーの名前。このプロパティは、メッセージの作成先、コピー先、移動先のフォルダーも識別します。  <br/> |Exchange (メールボックス アクティビティ)  <br/> |
|Parameters  <br/> |Exchange 管理者のアクティビティの場合、Operation プロパティで識別されたコマンドレットで使用された、すべてのパラメーターの名前と値。  <br/> |Exchange (管理者のアクティビティ)  <br/> |
|RecordType  <br/> |レコードで示されている操作の種類。次の値によって、レコードの種類が示されます。<br/><br/> **1** - Exchange 管理者監査ログのレコードを意味します。 <br/>**2** - Exchange メールボックス監査ログの、単一のメールボックス アイテムに対して行われた操作に関するレコードを意味します。 <br/>**3** - この値も Exchange 管理者監査ログのレコードを意味します。ただし、このレコードの種類は、ソース メールボックス内の複数のアイテムに対して操作が行われたこと (複数のアイテムを削除済みアイテム フォルダーに移動する操作や、複数のアイテムを完全に削除する操作など) を意味します。<br/>**4** - SharePoint でのサイト管理者の操作 (管理者またはユーザーがサイトに対するアクセス許可を割り当てるなど) を意味します。 <br/>**6** - SharePoint でのファイルまたはフォルダーに関連する操作 (ユーザーの表示、ファイルの変更など) を意味します。 <br/>**8** - Azure Active Directory で行われた管理者の操作を意味します。 <br/>**9** - Azure Active Directory での OrgId ログオン イベントを意味します。このレコードの種類は非推奨となっています。<br/>**10** - データ センターで Microsoft 担当者が行ったセキュリティ コマンドレット イベントを意味します。 <br/>**11** - SharePoint でのデータ損失防止 (DLP) イベントを意味します。<br/> **12** - Sway のイベントを意味します。 <br/>**13** - 統合 DLP ポリシーを使用して構成されている場合、Exchange の DLP イベントを意味します。Exchange トランスポート ルールに基づく DLP イベントはサポートされません。<br>**14** - SharePoint の共有イベントを意味します。<br/> **15** - Azure Active Directory の Secure Token Service (STS) ログオン イベントを意味します。 <br/>**18** - セキュリティ/コンプライアンス センターのイベントを意味します。 <br/>**20** - Power BI のイベントを意味します。 <br/>**21**- Dynamics 365 のイベントを意味します。<br/>**22** - Yammer のイベントを意味します。 <br/>**23** - Skype for Business のイベントを意味します。 <br/>**24** - 電子情報開示イベントを意味します。このレコードの種類は、セキュリティ/コンプライアンス センターでコンテンツ検索を実行し電子情報開示ケースを管理することによって行われたアクティビティを意味します。詳細については、Office 365 監査ログ内の電子情報開示アクティビティの検索に関する記事を参照してください。<br/>**25、26、27** - Microsoft Teams のイベントを意味します。 <br/>**28** - Exchange Online Protection イベントと Office 365 Advanced Threat Protection イベントからのフィッシングとマルウェアのイベントを意味します。<br/> **30** - Microsoft Flow のイベントを意味します。<br/> **32** - Microsoft Stream のイベントを意味します。<br/> **35** - Microsoft Project のイベントを意味します。 <br/> **36** - Sharepoint リストのイベントを意味します。<br/> **40** - セキュリティ/コンプライアンス アラートのシグナルに起因するイベントを意味します。<br/> **41** - Office 365 Advanced Threat Protection でのブロック時の安全なリンクと上書きのブロック イベントを意味します。<br/>**47** - SharePoint、OneDrive、および Microsoft Teams 内のファイルに対する、Office 365 Advanced Threat Protection からのフィッシングとマルウェアのイベントを意味します。 |すべて  <br/> |
|ResultStatus  <br/> |(**Operation** プロパティで指定された) アクションが正常に終了したかどうかを示します。  <br/> Exchange 管理者アクティビティでは、値は **True** (成功) または **False** (失敗) のいずれかになります。  <br/> |すべて  <br/>|
|SecurityComplianceCenterEventType  <br/> |アクティビティがセキュリティ/コンプライアンス センターのイベントであったことを示します。セキュリティ/コンプライアンス センターのすべてのアクティビティでは、このプロパティの値は **0** になります。<br/> |Office 365 セキュリティ/コンプライアンス センター  <br/> |
|SharingType  <br/> |リソースが共有されたユーザーに割り当てられているアクセス許可の種類。このユーザーは、**UserSharedWith** プロパティによって識別されます。<br/> |SharePoint  <br/> |
|Site  <br/> |ユーザーがアクセスしたファイルまたはフォルダーが置かれているサイトの GUID。  <br/> |SharePoint  <br/> |
|SiteUrl  <br/> |ユーザーがアクセスしたファイルまたはフォルダーが置かれているサイトの URL。  <br/> |SharePoint  <br/> |
|SourceFileExtension  <br/> |ユーザーがアクセスしたファイルのファイル拡張子。アクセスされたオブジェクトがフォルダーの場合、このプロパティは空白になります。  <br/> |SharePoint  <br/> |
|SourceFileName  <br/> |ユーザーがアクセスしたファイルまたはフォルダーの名前。  <br/> |SharePoint  <br/> |
|SourceRelativeUrl  <br/> |ユーザーがアクセスしたファイルが格納されているフォルダーの URL。**SiteURL**、**SourceRelativeURL**、および **SourceFileName** のプロパティの値の組み合わせは、**ObjectID** プロパティの値と同じであり、ユーザーがアクセスしたファイルの完全パス名です。<br/> |SharePoint  <br/> |
|Subject  <br/> |アクセスされたメッセージの件名。  <br/> |Exchange (メールボックス アクティビティ)  <br/> |
|TabType  <br/> | チームで追加、削除、または更新されたタブの種類。このプロパティの有効な値は次のとおりです。<br/><br/> **Excelpin** - Excel のタブ。  <br/> **Extension** - すべてのファースト パーティおよびサード パーティのアプリ (Planner、VSTS、Forms など)。  <br/> **Notes** - OneNote のタブ。  <br/> **Pdfpin** - PDF のタブ。  <br/> **Powerbi** - PowerBI のタブ。  <br/> **Powerpointpin** - PowerPoint のタブ。  <br/> **Sharepointfiles** - SharePoint のタブ。  <br/> **Webpage** - ピン留めされた Web サイトのタブ。  <br/> **Wiki-tab** - Wiki のタブ。  <br/> **Wordpin** - Word のタブ。  <br/> |Microsoft Teams  <br/> |
|Target  <br/> |(**Operation** プロパティで識別された) アクションの実行対象となったユーザー。たとえば、SharePoint または Microsoft Team にゲスト ユーザーが追加されると、このプロパティにそのユーザーが一覧表示されます。<br/> |Azure Active Directory  <br/> |
|TeamGuid  <br/> |Microsoft Teams のチームの ID。  <br/> |Microsoft Teams  <br/> |
|TeamName  <br/> |Microsoft Teams のチームの名前。  <br/> |Microsoft Teams  <br/> |
|UserAgent  <br/> |ユーザーのブラウザーに関する情報。この情報は、ブラウザーによって提供されます。  <br/> |SharePoint  <br/> |
|UserDomain  <br/> |アクションを実行したユーザー (アクター) のテナント組織に関する情報を示します。  <br/> |Azure Active Directory  <br/> |
|UserID  <br/> |レコードがログに記録される原因となった、(**Operation** プロパティで指定された) アクションを実行したユーザー。監査ログには、システム アカウント (SHAREPOINT\system または NT AUTHORITY\SYSTEM など) で実行されたアクティビティのレコードも含まれることに注意してください。<br/> |すべて  <br/> |
|UserKey  <br/> |**UserID** プロパティで識別されたユーザーの別の ID。このプロパティには、たとえば SharePoint でユーザーによって発生したイベントの Passport 固有 ID (PUID) が格納されます。このプロパティは、他のサービスで発生したイベントや、システム アカウントによって発生したイベントの **UserID** プロパティと同じ値を示す場合もあります。<br/> |すべて  <br/> |
|UserSharedWith  <br/> |リソースが共有されたユーザー。**Operation** プロパティの値が **SharingSet** の場合は、このプロパティが含まれます。このユーザーは、レポートの **[共有ユーザー]** 列にも表示されます。<br/> |SharePoint  <br/> |
|UserType  <br/> |操作を実行したユーザーの種類。次の値によって、ユーザーの種類が示されます。<br/> <br/> **0** - 標準のユーザー。 <br/>**2** - Office 365 組織の管理者。 <br/>**3** - Microsoft データセンター管理者またはデータセンターのシステム アカウント。 <br/>**4** - システム アカウント。 <br/>**5** - アプリケーション。 <br/>**6** - サービス プリンシパル。<br/>**7** - カスタム ポリシー。<br/>**8** - システム ポリシー。 |すべて  <br/> |
|Version  <br/> |ログに記録された (**Operation** プロパティで識別された) アクティビティのバージョン番号を示します。  <br/> |すべて  <br/> |
|Workload  <br/> |アクティビティが発生した Office 365 サービス。このプロパティの有効な値は次のとおりです。<br/> <br/>**SharePoint<br/>OneDrive<br/>Exchange<br/>AzureActiveDirectory<br/>DataCenterSecurity<br/>Compliance<br/>Sway<br/>Skype for Business<br/>SecurityComplianceCenter<br/>PowerBI<br/>CRM<br/>Yammer<br/>MicrosoftTeams<br/>ThreatIntelligence<br/>MicrosoftFlow<br/>MicrosoftStream<br/>DlpSharePointClassificationData<br/>Project<br/>PowerApps**|すべて  <br/> |
   
上記のプロパティは、特定のイベントの詳細が表示されている状態で **[詳細情報]** をクリックした場合にも表示されます。 
  
![[詳細情報] をクリックして監査ログのイベント レコードの詳細なプロパティを表示する](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
  

