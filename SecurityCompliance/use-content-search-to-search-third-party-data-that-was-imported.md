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
# <a name="use-content-search-to-search-third-party-data-that-was-imported-to-office-365"></a><span data-ttu-id="e9a2f-105">コンテンツの検索を使用して Office 365 にインポートされたサード パーティのデータを検索するには</span><span class="sxs-lookup"><span data-stu-id="e9a2f-105">Use Content Search to search third-party data that was imported to Office 365</span></span>

<span data-ttu-id="e9a2f-p102">[EDiscovery ツールのコンテンツの検索](content-search.md)を使用するには Office 365 のセキュリティで&amp;、サード ・ パーティ製のデータ ソースから Office 365 のメールボックスにインポートされたアイテムを検索するコンプライアンス センターです。インポートされたすべてのサード ・ パーティ製のデータ項目を検索するクエリを作成することができます。 またはサード ・ パーティ製の特定のデータ項目のみ検索するクエリを作成できます。さらに、クエリ ベースの保持ポリシーを作成することもできます。 または、Office 365 のサード ・ パーティ製のデータを保持するためにクエリに基づく電子的証拠開示を保持します。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-p102">You can use the [Content Search eDiscovery tool](content-search.md) in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. You can create a query to search all imported third-party data items or you can create a query to only search specific third-party data items. Additionally, you can also create a query-based Preservation Policy or a query-based eDiscovery hold to preserve third-party data in Office 365.</span></span> 
  
<span data-ttu-id="e9a2f-109">サード ・ パーティ製のデータと、Office 365 にインポート可能なサード ・ パーティ製のデータ型の一覧をインポートする方法の詳細については、 [Office 365 のサード ・ パーティ製データのアーカイブ](archiving-third-party-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-109">For more information about importing third-party data and a list of the third-party data types that can be imported to Office 365, see [Archiving third-party data in Office 365](archiving-third-party-data.md).</span></span> 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="e9a2f-110">すべてのサード ・ パーティ製データを検索するクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="e9a2f-p103">検索 (または保留中の場所) を Office 365 にインポートしたサード ・ パーティ製データの任意の型では、することができますを使用できます、`kind:externaldata`メッセージのプロパティと値のペアを [キーワード] ボックスにコンテンツの検索、またはクエリ ベースの保留リストを作成するときです。たとえば、任意のサードパーティのデータ ソースからインポートされたアイテムを検索し、インポートされたアイテムの Subject プロパティで"contoso"という単語が含まれているするには、次のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-p103">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold. For example, to search for items that were imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```
kind:externaldata AND subject:contoso
```

<span data-ttu-id="e9a2f-p104">前のキーワード クエリの例には、件名のプロパティが含まれています。キーワード クエリでサード パーティのデータの他のプロパティの一覧については可能性のある項目が含まれている、 [Office 365 のサード ・ パーティ製データのアーカイブ](archiving-third-party-data.md#more-information)の「関連情報」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-p104">The previous keyword query example includes the subject property. For a list of other properties for third-party data items that can included in a keyword query, see the "More information" section in [Archiving third-party data in Office 365](archiving-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="e9a2f-p105">検索し、サード ・ パーティ製のデータを保持するためのクエリを作成するは、検索結果を絞り込む条件を使用することもできます。コンテンツ検索クエリを作成する方法の詳細については、[キーワード クエリとコンテンツの検索の検索条件](keyword-queries-and-search-conditions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-p105">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results. For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="e9a2f-117">サード ・ パーティ製データの特定の種類を検索するクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="e9a2f-118">すべての種類のサード ・ パーティ製データを検索するには、クエリを作成できますを指定する種類のサード ・ パーティ製データのみの検索はそのコンテンツの検索のキーワード] ボックスで次のメッセージ プロパティと値のペアを使用しています。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message property-value pair in the keyword box for a Content Search:</span></span>
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="e9a2f-119">たとえば、のみ [件名] プロパティには、"contoso"という単語を含む Facebook のデータを検索するには、次のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-119">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="e9a2f-p106">次の表は、サード ・ パーティ製のデータ型を検索することができる値に使用する、`itemclass:`メッセージのプロパティをその種類のサード ・ パーティ製データの検索では具体的には。クエリの構文が大文字と小文字が区別されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-p106">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data. Note that the query syntax isn't case sensitive.</span></span> 
  
|<span data-ttu-id="e9a2f-122">**サード ・ パーティ製のデータ型**</span><span class="sxs-lookup"><span data-stu-id="e9a2f-122">**Third-party data type**</span></span>|<span data-ttu-id="e9a2f-123">**値`itemclass:`プロパティ**</span><span class="sxs-lookup"><span data-stu-id="e9a2f-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e9a2f-124">AIM</span><span class="sxs-lookup"><span data-stu-id="e9a2f-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="e9a2f-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="e9a2f-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="e9a2f-126">AOL with Pivot クライアント</span><span class="sxs-lookup"><span data-stu-id="e9a2f-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="e9a2f-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="e9a2f-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="e9a2f-128">Ares</span><span class="sxs-lookup"><span data-stu-id="e9a2f-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="e9a2f-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="e9a2f-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="e9a2f-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="e9a2f-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="e9a2f-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="e9a2f-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="e9a2f-132">済みのプレース ホルダー</span><span class="sxs-lookup"><span data-stu-id="e9a2f-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="e9a2f-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="e9a2f-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="e9a2f-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="e9a2f-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="e9a2f-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="e9a2f-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="e9a2f-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="e9a2f-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="e9a2f-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="e9a2f-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="e9a2f-138">BlackBerry の呼び出しのログ</span><span class="sxs-lookup"><span data-stu-id="e9a2f-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="e9a2f-139">BlackBerry メッセンジャー</span><span class="sxs-lookup"><span data-stu-id="e9a2f-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="e9a2f-140">BlackBerry 暗証番号 (pin)</span><span class="sxs-lookup"><span data-stu-id="e9a2f-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="e9a2f-141">ブラックベリー SMS</span><span class="sxs-lookup"><span data-stu-id="e9a2f-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="e9a2f-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="e9a2f-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="e9a2f-143">Bloomberg メール
</span><span class="sxs-lookup"><span data-stu-id="e9a2f-143">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="e9a2f-144">Bloomberg のメッセージング</span><span class="sxs-lookup"><span data-stu-id="e9a2f-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="e9a2f-145">Box
</span><span class="sxs-lookup"><span data-stu-id="e9a2f-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="e9a2f-146">Cisco IM&amp;プレゼンス サーバー</span><span class="sxs-lookup"><span data-stu-id="e9a2f-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="e9a2f-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="e9a2f-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="e9a2f-148">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="e9a2f-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="e9a2f-149">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="e9a2f-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="e9a2f-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="e9a2f-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="e9a2f-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="e9a2f-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="e9a2f-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="e9a2f-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="e9a2f-153">Flickr
</span><span class="sxs-lookup"><span data-stu-id="e9a2f-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="e9a2f-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="e9a2f-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="e9a2f-155">Google+
</span><span class="sxs-lookup"><span data-stu-id="e9a2f-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="e9a2f-156">Google トーク</span><span class="sxs-lookup"><span data-stu-id="e9a2f-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="e9a2f-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="e9a2f-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="e9a2f-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="e9a2f-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="e9a2f-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="e9a2f-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="e9a2f-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="e9a2f-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="e9a2f-161">IBM の接続</span><span class="sxs-lookup"><span data-stu-id="e9a2f-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="e9a2f-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="e9a2f-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="e9a2f-163">氷のチャット</span><span class="sxs-lookup"><span data-stu-id="e9a2f-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="e9a2f-164">Indii Messenger
</span><span class="sxs-lookup"><span data-stu-id="e9a2f-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="e9a2f-165">Instagram
</span><span class="sxs-lookup"><span data-stu-id="e9a2f-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="e9a2f-166">Instant Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="e9a2f-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="e9a2f-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="e9a2f-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="e9a2f-168">IRC</span><span class="sxs-lookup"><span data-stu-id="e9a2f-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="e9a2f-169">Jive
</span><span class="sxs-lookup"><span data-stu-id="e9a2f-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="e9a2f-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="e9a2f-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="e9a2f-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="e9a2f-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="e9a2f-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="e9a2f-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="e9a2f-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="e9a2f-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="e9a2f-174">マイクロソフトの統合コミュニケーション</span><span class="sxs-lookup"><span data-stu-id="e9a2f-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="e9a2f-175">点を配置します。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="e9a2f-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="e9a2f-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="e9a2f-177">MSN</span><span class="sxs-lookup"><span data-stu-id="e9a2f-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="e9a2f-178">マイスペース</span><span class="sxs-lookup"><span data-stu-id="e9a2f-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="e9a2f-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="e9a2f-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="e9a2f-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="e9a2f-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="e9a2f-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="e9a2f-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="e9a2f-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="e9a2f-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="e9a2f-183">QQ</span><span class="sxs-lookup"><span data-stu-id="e9a2f-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="e9a2f-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="e9a2f-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="e9a2f-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="e9a2f-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="e9a2f-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e9a2f-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="e9a2f-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="e9a2f-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="e9a2f-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="e9a2f-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="e9a2f-189">
Squawker
</span><span class="sxs-lookup"><span data-stu-id="e9a2f-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="e9a2f-190">Symphony
</span><span class="sxs-lookup"><span data-stu-id="e9a2f-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="e9a2f-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="e9a2f-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="e9a2f-192">Thomson Reuters Eikon Messenger
</span><span class="sxs-lookup"><span data-stu-id="e9a2f-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="e9a2f-193">Tor</span><span class="sxs-lookup"><span data-stu-id="e9a2f-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="e9a2f-194">TTT</span><span class="sxs-lookup"><span data-stu-id="e9a2f-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="e9a2f-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="e9a2f-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="e9a2f-196">UBS チャット
</span><span class="sxs-lookup"><span data-stu-id="e9a2f-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="e9a2f-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="e9a2f-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="e9a2f-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="e9a2f-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="e9a2f-199">Winny</span><span class="sxs-lookup"><span data-stu-id="e9a2f-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="e9a2f-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="e9a2f-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="e9a2f-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="e9a2f-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="e9a2f-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="e9a2f-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="e9a2f-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="e9a2f-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
