---
title: コンテンツの検索を使用して Office 365 にインポートされたサード パーティのデータを検索するには
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: サードパーティのデータ ソースから Office 365 のメールボックスにインポートされたアイテムを検索するのには電子的証拠開示されているコンテンツの検索ツールを使用します。インポートされたすべての項目を検索するか、特定のサード ・ パーティ製データ型を検索するクエリを作成するクエリを作成することができます。この資料では、キーワード クエリでを使用して Office 365 にインポート可能なサード ・ パーティ製のデータの種類を検索する値が一覧表示されます。
ms.openlocfilehash: 6829e894ba687fb09184c32201f76394e37bbbf8
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25037970"
---
# <a name="use-content-search-to-search-third-party-data-that-was-imported-to-office-365"></a>コンテンツの検索を使用して Office 365 にインポートされたサード パーティのデータを検索するには

[EDiscovery ツールのコンテンツの検索](content-search.md)を使用するには Office 365 のセキュリティで&amp;、サード ・ パーティ製のデータ ソースから Office 365 のメールボックスにインポートされたアイテムを検索するコンプライアンス センターです。インポートされたすべてのサード ・ パーティ製のデータ項目を検索するクエリを作成することができます。 またはサード ・ パーティ製の特定のデータ項目のみ検索するクエリを作成できます。さらに、クエリ ベースの保持ポリシーを作成することもできます。 または、Office 365 のサード ・ パーティ製のデータを保持するためにクエリに基づく電子的証拠開示を保持します。 
  
サード ・ パーティ製のデータと、Office 365 にインポート可能なサード ・ パーティ製のデータ型の一覧をインポートする方法の詳細については、 [Office 365 のサード ・ パーティ製データのアーカイブ](archiving-third-party-data.md)を参照してください。 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>すべてのサード ・ パーティ製データを検索するクエリを作成します。

検索 (または保留中の場所) を Office 365 にインポートしたサード ・ パーティ製データの任意の型では、することができますを使用できます、`kind:externaldata`メッセージのプロパティと値のペアを [キーワード] ボックスにコンテンツの検索、またはクエリ ベースの保留リストを作成するときです。たとえば、任意のサードパーティのデータ ソースからインポートされたアイテムを検索し、インポートされたアイテムの Subject プロパティで"contoso"という単語が含まれているするには、次のクエリを使用します。 
  
```
kind:externaldata AND subject:contoso
```

前のキーワード クエリの例には、件名のプロパティが含まれています。キーワード クエリでサード パーティのデータの他のプロパティの一覧については可能性のある項目が含まれている、 [Office 365 のサード ・ パーティ製データのアーカイブ](archiving-third-party-data.md#more-information)の「関連情報」を参照してください。
  
検索し、サード ・ パーティ製のデータを保持するためのクエリを作成するは、検索結果を絞り込む条件を使用することもできます。コンテンツ検索クエリを作成する方法の詳細については、[キーワード クエリとコンテンツの検索の検索条件](keyword-queries-and-search-conditions.md)を参照してください。
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>サード ・ パーティ製データの特定の種類を検索するクエリを作成します。

すべての種類のサード ・ パーティ製データを検索するには、クエリを作成できますを指定する種類のサード ・ パーティ製データのみの検索はそのコンテンツの検索のキーワード] ボックスで次のメッセージ プロパティと値のペアを使用しています。
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

たとえば、のみ [件名] プロパティには、"contoso"という単語を含む Facebook のデータを検索するには、次のクエリを使用します。
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

次の表は、サード ・ パーティ製のデータ型を検索することができる値に使用する、`itemclass:`メッセージのプロパティをその種類のサード ・ パーティ製データの検索では具体的には。クエリの構文が大文字と小文字が区別されていないことに注意してください。 
  
|**サード ・ パーティ製のデータ型**|**値`itemclass:`プロパティ**|
|:-----|:-----|
|AIM  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL with Pivot クライアント  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|済みのプレース ホルダー  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|Blackberry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|BlackBerry の呼び出しのログ  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry メッセンジャー  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry 暗証番号 (pin)  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|ブラックベリー SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg メール
  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|Bloomberg のメッセージング  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box
  <br/> | `ipm.externaldata.Box*` <br/> |
|Cisco IM&amp;プレゼンス サーバー  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
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
|Google トーク  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM の接続  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|氷のチャット  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
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
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|マイクロソフトの統合コミュニケーション  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|点を配置します。  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|MSN  <br/> | `ipm.externaldata.MSN*` <br/> |
|マイスペース  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
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
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
