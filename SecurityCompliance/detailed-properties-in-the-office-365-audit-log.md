---
title: Office 365 監査ログの詳細なプロパティ
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/8/2017
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
description: Office 365 に含まれるその他のプロパティの説明では、ログの記録を監査します。
ms.openlocfilehash: 69c5565ac71715ba2cb22d93d80f7e5dd12c6440
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532195"
---
# <a name="detailed-properties-in-the-office-365-audit-log"></a>Office 365 監査ログの詳細なプロパティ

Office 365 のセキュリティ監査ログ検索の結果をエクスポートするとき&amp;コンプライアンス センターでは、検索条件を満たすすべての結果をダウンロードするオプションがあります。**結果のエクスポート**を選択することによってこれを行う\>、セキュリティの**監査ログの検索**ページで**すべての結果のダウンロード**を&amp;コンプライアンス センターです。詳細についてを参照してください[では、Office 365 のセキュリティ監査ログを検索する&amp;コンプライアンス センター](search-the-audit-log-in-security-and-compliance.md)です。
  
 すべてエクスポートは、監査ログの検索の結果、統一された監査ログは、コンマにコピー Office 365 からの生データ値 (CSV) ファイルがローカル コンピューターにダウンロードされるとこれで区切られます。このファイルには、監査ログ ・ エントリの**詳細**をという名前の列から追加情報が含まれています。この列には、監査ログ レコードから複数のプロパティを複数値プロパティが含まれています。この複数値プロパティの**プロパティと値**のペアのそれぞれは、コンマで区切られます。 
  
次の表に含まれているプロパティの説明: でイベントが発生するサービスを Office 365 によって-マルチ プロパティの**詳細**] 列にします。**Office 365 サービスがこのプロパティを持つ**列は、サービス、およびプロパティが含まれています活動 (ユーザーまたは管理者) の種類を示します。プロパティこのトピックでは表示されませんが、またはこれらのプロパティに関する詳細については、 [Office 365 の管理アクティビティの API のスキーマ](https://go.microsoft.com/fwlink/p/?LinkId=717993)を参照してください。
  
> [!TIP]
> Excel で電源クエリを使用すると、各プロパティは独自の列を持つように、この列を複数の列に分割します。これにより並べ替えとこれらのプロパティの 1 つ以上のフィルターです。これを行う方法については、[分割テキスト (電源クエリ) の列](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662)で「区切り文字で列を分割する」セクションを参照してください。 
  
|**プロパティ**|**説明**|**このプロパティには、office 365 サービス**|
|:-----|:-----|:-----|
|アクター  <br/> |アクションを実行したユーザーまたはサービス アカウントです。 |Azure Active Directory  <br/> |
|AddOnName  <br/> |追加、削除、またはチーム内で更新するアドオンの名前です。マイクロソフトのチームでのアドオンの種類は、bot、コネクタ、またはタブです。  <br/> |Microsoft Teams  <br/> |
|AddOnType  <br/> |追加、削除、またはチーム内で更新されたアドオンの種類。次の値は、アドオンの種類を示します。<br/> **1** - では、bot を示します。<br/> **2** - では、コネクタを示します。<br/> **3** - では、タブを示します。 |Microsoft Teams  <br/> |
|AzureActiveDirectoryEventType  <br/> |Azure Active Directory のイベントの種類。次の値は、イベントの種類を示します。<br/> **0** - では、アカウント ログイン イベントを示します。<br/> **1** - は、Azure アプリケーションのセキュリティ イベントを示します。 |Azure Active Directory  <br/> |
|ChannelGuid  <br/> |マイクロソフト チームのチャネルの ID です。チャネルにあるチームは、 **TeamName**と**TeamGuid**プロパティによって識別されます。<br/> |Microsoft Teams  <br/> |
|書式は次  <br/> |マイクロソフト チームのチャネルの名前。チャネルにあるチームは、 **TeamName**と**TeamGuid**プロパティによって識別されます。<br/> |Microsoft Teams  <br/> |
|クライアント  <br/> |クライアント デバイス、デバイスの OS、およびログイン イベント (たとえば、Nokia Lumia 920; に使用されるデバイスのブラウザーWindows Phone 8 です。IE モバイル 11)。  <br/> |Azure Active Directory  <br/> |
|ClientInfoString  <br/> |ブラウザーのバージョン、Outlook のバージョン、およびモバイル デバイスの情報など、操作を実行するために使用された電子メール クライアントについての情報  <br/> |Exchange (メールボックス アクティビティ)  <br/> |
|ClientIP  <br/> |アクティビティのログが記録されたときに使用されたデバイスの IP アドレスです。IP アドレスは、IPv4 または IPv6 アドレスの形式で表示されます。  <br/> |Active Directory の Exchange と Azure  <br/> |
|ClientIPAddress  <br/> |ClientIP と同じです。  <br/> |SharePoint  <br/> |
|CreationTime  <br/> |日付と時刻を世界協定時刻 (UTC) で、ユーザーがアクティビティを実行するとします。  <br/> |All  <br/> |
|DestinationFileExtension  <br/> |コピーまたは移動したファイルのファイル拡張子。FileCopied と FileMoved のユーザーの作業に対してのみ、このプロパティが表示されます。  <br/> |SharePoint  <br/> |
|DestinationFileName  <br/> |ファイルの名前がコピーまたは移動します。FileCopied と FileMoved の操作についてのみ、このプロパティが表示されます。  <br/> |SharePoint  <br/> |
|DestinationRelativeUrl  <br/> |インストール先のフォルダー、ファイルがコピーまたは移動先の URL です。**SiteURL**、 **DestinationRelativeURL**では、 **DestinationFileName**プロパティの値の組み合わせは、コピーされたファイルの完全パス名では、**オブジェクト Id**プロパティの値と同じです。FileCopied と FileMoved のユーザーの作業に対してのみ、このプロパティが表示されます。<br/> |SharePoint  <br/> |
|EventSource  <br/> |SharePoint のイベントが発生したことを識別します。使用可能な値は、 **SharePoint** **ObjectModel**です。<br/> |SharePoint  <br/> |
|ExternalAccess  <br/> |Exchange 管理アクティビティでは、Microsoft データ センターの担当者が、組織のデータ センター サービス アカウント、ユーザーまたは委任された管理者が、コマンドレットが実行されたかどうかを指定します。**False**の値は、コマンドレットは、組織内のユーザーによって実行されたことを示します。**True**の値は、コマンドレットがデータ センターの担当者、データ センターのサービス アカウント、または委任された管理者によって実行されたことを示します。<br/> Exchange メールボックス アクティビティでは、組織外のユーザーがメールボックスにアクセスしたかどうかを指定します。  <br/> |Exchange  <br/> |
|ExtendedProperties  <br/> |拡張プロパティ、Azure Active Directory のイベントです。  <br/> |Azure Active Directory  <br/> |
|ID  <br/> |レポート エントリの ID。ID は、レポートのエントリを一意に識別します。  <br/> |All  <br/> |
|InternalLogonType  <br/> |内部使用に予約されています。  <br/> |Exchange (メールボックス アクティビティ)  <br/> |
|ItemType  <br/> |アクセスまたは変更されたオブジェクトの型。使用可能な値には、**ファイル**、**フォルダー**、 **Web**、**サイト**、**テナント**、および**DocumentLibrary**が含まれます。<br/> |SharePoint  <br/> |
|LoginStatus  <br/> |発生したログインの失敗を識別します。  <br/> |Azure Active Directory  <br/> |
|示します  <br/> |メールボックスへのアクセスの種類。次の値は、メールボックスにアクセスしたユーザーの種類を示します。<br/><br/> **0** - では、メールボックスの所有者を示します。<br/> **1** - は、管理者を示します。<br/> **2** - では、デリゲートを示します。 <br/>**3** - では、マイクロソフトのデータ センター内のトランスポート サービスを示します。<br/> **4** - マイクロソフトのデータ センター内のサービス アカウントを示します。 <br/>**6** - では、委任された管理者を示します。 |Exchange (メールボックス アクティビティ)  <br/> |
|MailboxGuid  <br/> |アクセスされているメールボックスの Exchange の GUID です。  <br/> |Exchange (メールボックス アクティビティ)  <br/> |
|MailboxOwnerUPN  <br/> |メールボックスを所有する人物の電子メール アドレスにアクセスしました。  <br/> |Exchange (メールボックス アクティビティ)  <br/> |
|メンバー  <br/> |追加またはチームから削除されたユーザーの一覧を表示します。次の値は、ユーザーに割り当てられているロールの種類を示します。<br/><br/> **1** - は、所有者の役割を示します。<br/> **2** - では、メンバーの役割を示します。<br/> **3** - では、ゲストの役割を示します。 <br/><br/>メンバー プロパティには、組織、およびメンバーの電子メール アドレスの名前も含まれています。  <br/> |Microsoft Teams  <br/> |
|ModifiedProperties (名前、新しい値は、OldValue)  <br/> |プロパティでは、サイトまたはサイト コレクションの管理者グループのメンバーとしてユーザーを追加するなどの管理イベントの含まれています。プロパティが含まれます (たとえば、サイト管理者グループなど) が変更されたプロパティの名前には変更されたプロパティ (このようなユーザーがサイトの管理、および変更されたオブジェクトの以前の値として追加します。  <br/> |すべて (管理者の活動)  <br/> |
|オブジェクト Id  <br/> |Exchange 管理者監査ログ、コマンドレットによって変更されたオブジェクトの名前です。  <br/> SharePoint アクティビティ、ファイルまたはフォルダーのユーザー アクセスの完全 URL パス名です。  <br/> Azure AD アクティビティでは、変更されたユーザー アカウントの名前。  <br/> |All  <br/> |
|Operation  <br/> |ユーザーまたは管理者のアクティビティの名前。**活動**で選択されている値にこのプロパティの値が対応するドロップダウン リストです。**すべての活動の結果を表示する**を選択した場合、レポートはすべてのサービスのユーザーと管理者の活動をすべてのエントリを含まれます。Office 365 の監査ログに記録されている操作と活動については、 **Audited アクティビティ**] タブを参照してください[では、Office 365 のセキュリティ監査ログを検索する&amp;コンプライアンス センター](search-the-audit-log-in-security-and-compliance.md)です。<br/> Exchange 管理者の活動には、このプロパティは、実行されたコマンドレットの名前を識別します。  <br/> |All  <br/> |
|OrganizationID  <br/> |Office 365 組織の GUID です。  <br/> |All  <br/> |
|Path  <br/> |アクセスしたメッセージが格納されているメールボックス フォルダーの名前です。このプロパティには、フォルダーの場所を識別もメッセージがで作成された、またはにコピーまたは移動します。  <br/> |Exchange (メールボックス アクティビティ)  <br/> |
|Parameters  <br/> |Exchange 管理者のアクティビティでは、名前とすべてのパラメーターの値、[操作] プロパティで指定されているコマンドレットを使用していた。  <br/> |Exchange (管理活動)  <br/> |
|RecordType  <br/> |レコードによって示される操作の種類です。次の値は、レコードの種類を示します。<br/><br/> **1** - では、Exchange 管理者の監査ログからレコードを示します。 <br/>**2** - では、シングルのメールボックスのアイテムに対して実行された操作は、Exchange のメールボックス監査ログからレコードを示します。 <br/>**3** - には、Exchange メールボックスの監査ログからレコードも表示されます。このレコードの種類では、(複数のアイテムを削除済みアイテム フォルダーに移動する、複数のアイテムを完全に削除するなど)、移行元のメールボックス内の複数のアイテムに対して操作が実行されたことを示します。<br/>**4** - は、管理者またはユーザーがサイトにアクセス許可を割り当てるなど、SharePoint のサイトの管理操作を示します。 <br/>**6** - は、ファイルまたはフォルダーに関連する操作を SharePoint のユーザーが表示またはファイルの変更などを示します。 <br/>**8** - では、Azure Active Directory で管理操作を示します。 <br/>**9** - Azure Active Directory のログオン イベントの OrgId のことを示します。このレコードの種類は廃止される予定です。<br/>**10** - データ ・ センター内のマイクロソフトの担当者によって実行されていたセキュリティのコマンドレットのイベントを示します。 <br/>**11** - SharePoint のデータを示す損失 (DLP) の保護のイベントです。<br/> **12** - イベントをかきたてることを示します。 <br/>**14** - では、SharePoint の共有イベントを示します。<br/> **15** - Azure Active Directory のログオン イベントを示すセキュリティで保護されたトークン サービス (STS)。 <br/>**18** - セキュリティのことを示します&amp;コンプライアンス センターのイベントです。 <br/>**20** - 電源の BI を示すイベントです。 <br/>**22** - イベントの Yammer を示します。 <br/>**24** - 電子的証拠開示のイベントを示します。このレコードの種類は、コンテンツの検索を実行して、セキュリティ、電子的証拠開示のサポート案件の管理によって実行されたアクティビティを示す&amp;コンプライアンス センターです。詳細については、Office 365 で電子的証拠開示活動を検索する監査ログを参照してください。<br/>**25、26、または 27** - マイクロソフトのチームを示すイベントです。 |All  <br/> |
|ResultStatus  <br/> |(**操作**のプロパティで指定された) アクションが正常に終了したかどうかどうかを示します。  <br/> Exchange 管理アクティビティでは、値は、 **True** (成功) または**False** (失敗) です。  <br/> |All  <br/> |
|SecurityComplianceCenterEventType  <br/> |活動が、セキュリティをしたことを示します&amp;コンプライアンス センター イベントです。すべてのセキュリティ&amp;このプロパティに**0**の値がコンプライアンス センターの活動になります。<br/> |Office 365 のセキュリティ&amp;コンプライアンス センター  <br/> |
|SharingType  <br/> |リソースが共有しているユーザーに割り当てられた共有アクセス許可の種類です。このユーザーは、 **UserSharedWith**プロパティで識別されます。<br/> |SharePoint  <br/> |
|サイト  <br/> |ファイルまたはユーザーによってアクセスされるフォルダーが配置されているサイトの GUID を指定します。  <br/> |SharePoint  <br/> |
|SiteUrl  <br/> |ファイルまたはユーザーによってアクセスされるフォルダーが配置されているサイトの URL です。  <br/> |SharePoint  <br/> |
|SourceFileExtension  <br/> |ユーザーがアクセスしたファイルのファイル拡張子。このプロパティは、アクセスされているオブジェクトがフォルダーの場合は空白です。  <br/> |SharePoint  <br/> |
|SourceFileName  <br/> |ファイルまたはユーザーによってアクセスされるフォルダーの名前です。  <br/> |SharePoint  <br/> |
|SourceRelativeUrl  <br/> |ユーザーがアクセスするファイルを含むフォルダーの URL。**SiteURL**、 **SourceRelativeURL**では、 **SourceFileName**プロパティの値の組み合わせは、ユーザーがアクセスするファイルの完全パス名では、**オブジェクト Id**プロパティの値と同じです。<br/> |SharePoint  <br/> |
|Subject  <br/> |アクセスされたメッセージの件名です。  <br/> |Exchange (メールボックス アクティビティ)  <br/> |
|タイプ  <br/> | タブの種類は、追加、削除、またはチーム内で更新します。このプロパティの有効な値は次のとおりです。<br/><br/> **Excelpin** -「Excel のタブです。  <br/> **拡張機能**- すべてのファーストパーティおよびサードパーティのアプリケーションがあります。プランナー、VSTS の場合、フォームなどです。  <br/> **ノート**を OneNote のタブです。  <br/> **Pdfpin** - A PDF タブします。  <br/> **Powerbi** - A の PowerBI のタブです。  <br/> **Powerpointpin** - A の PowerPoint のタブです。  <br/> **Sharepointfiles** - A SharePoint] タブ。  <br/> **Web ページ**の固定された web サイトのタブ。  <br/> **Wiki タブ**- wiki タブします。  <br/> **Wordpin** - 単語タブします。  <br/> |Microsoft Teams  <br/> |
|ターゲット  <br/> |上 (**操作**のプロパティで識別される) アクションを実行したユーザーです。などの SharePoint またはマイクロソフトのチームには、ゲスト ユーザーを追加する場合このプロパティでそのユーザーは表示されます。<br/> |Azure Active Directory  <br/> |
|TeamGuid  <br/> |マイクロソフトのチームでチームの ID です。  <br/> |Microsoft Teams  <br/> |
|TeamName  <br/> |マイクロソフトのチームにチームの名前。  <br/> |Microsoft Teams  <br/> |
|UserAgent  <br/> |ユーザーのブラウザーに関する情報です。この情報は、ブラウザーによって提供されます。  <br/> |SharePoint  <br/> |
|UserDomain  <br/> |ユーザー (出演者) のテナント組織の身元情報処理を実行しました。  <br/> |Azure Active Directory  <br/> |
|ユーザー Id  <br/> |レコードをログに記録される原因となった (、[**操作**] プロパティで指定された) アクションを実行するユーザーです。(Sharepoint \system または NT authority \system) などのシステム アカウントで実行されるアクティビティのレコードが監査ログにも含まれている注意してください。<br/> |All  <br/> |
|ユーザー キー  <br/> |**UserID**プロパティで識別されるユーザーの別の ID です。たとえば、このプロパティは、passport の固有 ID (PUID)、SharePoint のユーザーによって実行されるイベントが表示されます。このプロパティは、他のサービスとシステム アカウントで実行されるイベントで発生するイベントの**ユーザー Id**プロパティと同じ値を指定ことがあります。<br/> |All  <br/> |
|UserSharedWith  <br/> |リソースが共有しているユーザーです。**操作**プロパティの値が**SharingSet**である場合、このプロパティは含まれています。このユーザーがレポート内**で共有**列も表示されます。<br/> |SharePoint  <br/> |
|UserType  <br/> |操作を実行したユーザーの種類。次の値は、ユーザーの種類を示します。<br/> <br/> **0** - 通常のユーザーです。 <br/>**2** - Office 365 の組織の管理者です。 <br/>**3** - Microsoft データ センターの管理者またはシステム アカウントのデータ センターです。 <br/>**4** - システムのアカウントです。 <br/>**5** - アプリケーションです。 <br/>**6** - サービス主体です。 |All  <br/> |
|Version  <br/> |(**操作**のプロパティによって識別される) ログに記録される活動のバージョン番号を示します。  <br/> |All  <br/> |
|ワークロード  <br/> |Office 365 サービスは、アクティビティが発生しました。このプロパティの有効な値は次のとおりです。<br/> <br/>**SharePoint<br/>OneDrive<br/>Exchange<br/>AzureActiveDirectory<br/>DataCenterSecurity<br/>準拠<br/>かきたてる<br/>SecurityComplianceCenter<br/>PowerBI<br/>MicrosoftTeams<br/>ThreatIntelligence**|All  <br/> |
   
上記で説明したプロパティを特定のイベントの詳細を表示するときの**詳細について**はをクリックすると表示されます。 
  
![詳細については、監査ログのイベント レコードの詳細なプロパティを表示する] をクリックします。](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
  

