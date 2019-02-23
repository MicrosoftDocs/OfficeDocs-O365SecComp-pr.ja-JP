---
title: コンテンツ検索を使用して Office 365 にインポートされたサードパーティデータを検索する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: コンテンツ検索電子情報開示ツールを使用して、サードパーティのデータソースから Office 365 のメールボックスにインポートされたアイテムを検索します。クエリを作成して、インポートされたすべてのアイテムを検索したり、特定のサードパーティのデータ型を検索するクエリを作成したりすることができます。この記事では、Office 365 にインポートできるサードパーティのデータ型を検索するために、キーワードクエリで使用できる値の一覧を示します。
ms.openlocfilehash: 793024f765aa1d016f7a043d14eb75ca6c2435c3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214877"
---
# <a name="use-content-search-to-search-third-party-data-that-was-imported-to-office-365"></a>コンテンツ検索を使用して Office 365 にインポートされたサードパーティデータを検索する

office 365 セキュリティ&amp;コンプライアンスセンターの[コンテンツ検索電子情報開示ツール](content-search.md)を使用して、サードパーティのデータソースから office 365 のメールボックスにインポートされたアイテムを検索することができます。インポートされたサードパーティのデータアイテムをすべて検索するクエリを作成するか、特定のサードパーティデータアイテムのみを検索するクエリを作成することができます。また、Office 365 でサードパーティのデータを保持するために、クエリベースの保持ポリシーまたはクエリベースの電子情報開示の保持を作成することもできます。 
  
サードパーティのデータのインポート、および office 365 にインポートできるサードパーティのデータ型のリストの詳細については、「 [office 365 でサードパーティのデータをアーカイブ](archiving-third-party-data.md)する」を参照してください。 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>すべてのサードパーティデータを検索するクエリを作成する

Office 365 にインポートしたすべての種類のサードパーティデータを検索 (または保留) するには、コンテンツ検索の場合は`kind:externaldata`キーワードボックスでメッセージプロパティと値のペアを使用し、クエリベースの保持を作成する場合はそのようにします。たとえば、インポートされたアイテムの Subject プロパティに "contoso" という単語を含むサードパーティのデータソースからインポートされたアイテムを検索するには、次のクエリを使用します。 
  
```
kind:externaldata AND subject:contoso
```

前述のキーワードクエリの例には、subject プロパティが含まれています。キーワードクエリに含めることができるサードパーティのデータアイテムに関するその他のプロパティの一覧については、「 [Office 365 でのサードパーティデータのアーカイブ](archiving-third-party-data.md#more-information)」の「詳細情報」セクションを参照してください。
  
サードパーティのデータを検索して保持するためのクエリを作成するときに、条件を使用して検索結果を絞り込むこともできます。コンテンツ検索クエリの作成の詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>特定の種類のサードパーティデータを検索するためのクエリを作成する

すべての種類のサードパーティデータを検索するのではなく、コンテンツ検索のキーワードボックスで次のメッセージのプロパティと値のペアを使用して、サードパーティデータの種類を指定したものだけを検索するクエリを作成できます。
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

たとえば、Subject プロパティに "contoso" という単語が含まれる Facebook データのみを検索するには、次のクエリを使用します。
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

次の表に、検索可能なサードパーティのデータ型と、そのサードパーティデータの種類を`itemclass:`特定するためにメッセージプロパティに対して使用する値を示します。クエリ構文では大文字と小文字が区別されないことに注意してください。 
  
|**サードパーティのデータ型**|**プロパティの`itemclass:`値**|
|:-----|:-----|
|AIM  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL with Pivot クライアント  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|を持つ (Placeholder) プレースホルダー  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|bittorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|Blackberry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|BlackBerry 呼び出しログ  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry メッセンジャー  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry PIN  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg メール
  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|Bloomberg Messaging  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|検索ボックス  <br/> | `ipm.externaldata.Box*` <br/> |
|Cisco IM &amp;プレゼンスサーバー  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud for Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Direct Connect  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr
  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google+
  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM 接続  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM sametime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|ICE チャット  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|Indii Messenger
  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram
  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg
  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive
  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|履歴  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|マインド揃え  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|MSN  <br/> | `ipm.externaldata.MSN*` <br/> |
|myspace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|opennap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|Pivot  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|Skype for Business  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|
Squawker
  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony
  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger
  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS チャット
  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|winmx  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
