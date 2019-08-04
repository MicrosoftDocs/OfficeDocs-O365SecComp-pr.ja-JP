---
title: コンテンツ検索を使用して Office 365 にインポートされたサードパーティのデータを検索する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: コンテンツ検索電子情報開示ツールを使用して、サードパーティのデータソースから Office 365 のメールボックスにインポートされたアイテムを検索します。 クエリを作成して、インポートされたすべてのアイテムを検索したり、特定のサードパーティのデータ型を検索するクエリを作成したりすることができます。 この記事では、Office 365 にインポートできるサードパーティのデータ型を検索するために、キーワードクエリで使用できる値の一覧を示します。
ms.openlocfilehash: 2d531557054398be4ca963a9b09943f1bf583d10
ms.sourcegitcommit: ab16ddf4c050a995471a058150767a0778be0b88
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35425545"
---
# <a name="use-content-search-to-search-third-party-data-imported-to-office-365"></a><span data-ttu-id="7d2fa-105">コンテンツ検索を使用して Office 365 にインポートされたサードパーティのデータを検索する</span><span class="sxs-lookup"><span data-stu-id="7d2fa-105">Use Content Search to search third-party data imported to Office 365</span></span>

<span data-ttu-id="7d2fa-106">セキュリティ & コンプライアンスセンターの[コンテンツ検索電子情報開示ツール](content-search.md)を使用して、サードパーティのデータソースから Office 365 のメールボックスにインポートされたアイテムを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="7d2fa-106">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="7d2fa-107">インポートされたサードパーティのすべてのデータアイテムを検索するクエリを作成するか、特定のサードパーティデータアイテムを検索するためのクエリを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="7d2fa-107">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="7d2fa-108">また、Office 365 でサードパーティのデータを保持するために、クエリベースの Office 365 アイテム保持ポリシーまたはクエリベースの電子情報開示の保持を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="7d2fa-108">Also, you can also create a query-based Office 365 retention policy or a query-based eDiscovery hold to preserve third-party data in Office 365.</span></span> 
  
<span data-ttu-id="7d2fa-109">サードパーティのデータのインポート、および Office 365 にインポートできるサードパーティのデータ型のリストの詳細については、「 [office を使用してサードパーティのデータをアーカイブする (office 365](work-with-partner-to-archive-third-party-data.md))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d2fa-109">For more information about importing third-party data and a list of the third-party data types that you can import to Office 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span> 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="7d2fa-110">すべてのサードパーティデータを検索するクエリを作成する</span><span class="sxs-lookup"><span data-stu-id="7d2fa-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="7d2fa-111">Office 365 にインポートしたすべての種類のサードパーティデータを検索 (または保留) するには、[キーワード] `kind:externaldata`ボックスで [メッセージのプロパティと値のペア] を使用して、コンテンツ検索を実行するか、クエリベースのホールドを作成します。</span><span class="sxs-lookup"><span data-stu-id="7d2fa-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="7d2fa-112">たとえば、インポートされたアイテムの Subject プロパティに "contoso" という単語を含む、サードパーティのデータソースからインポートされたアイテムを検索するには、次のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d2fa-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```
kind:externaldata AND subject:contoso
```

<span data-ttu-id="7d2fa-113">前述のキーワードクエリの例には、subject プロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d2fa-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="7d2fa-114">キーワードクエリに含めることができるサードパーティのデータアイテムに関するその他のプロパティの一覧については、「 [partner と連携してサードパーティのデータを Office 365 でアーカイブする](work-with-partner-to-archive-third-party-data.md#more-information)」の「詳細情報」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d2fa-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="7d2fa-115">サードパーティのデータを検索して保持するためのクエリを作成するときに、条件を使用して検索結果を絞り込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="7d2fa-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="7d2fa-116">コンテンツ検索クエリの作成の詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d2fa-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="7d2fa-117">特定の種類のサードパーティデータを検索するためのクエリを作成する</span><span class="sxs-lookup"><span data-stu-id="7d2fa-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="7d2fa-118">すべての種類のサードパーティデータを検索するのではなく、次のメッセージ*プロパティ*を使用して、サードパーティデータの種類のみを検索するクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7d2fa-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property:value* pair in the keyword box for a Content Search:</span></span>
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="7d2fa-119">たとえば、Subject プロパティに "contoso" という単語が含まれる Facebook データを検索するには、次のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d2fa-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="7d2fa-120">次の表に、検索可能なサードパーティのデータ型と、そのサードパーティデータの種類を`itemclass:`特定するためにメッセージプロパティに対して使用する値を示します。</span><span class="sxs-lookup"><span data-stu-id="7d2fa-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="7d2fa-121">クエリ構文では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="7d2fa-121">The query syntax isn't case sensitive.</span></span> 
  
|<span data-ttu-id="7d2fa-122">**サードパーティのデータ型**</span><span class="sxs-lookup"><span data-stu-id="7d2fa-122">**Third-party data type**</span></span>|<span data-ttu-id="7d2fa-123">**プロパティの`itemclass:`値**</span><span class="sxs-lookup"><span data-stu-id="7d2fa-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7d2fa-124">目的</span><span class="sxs-lookup"><span data-stu-id="7d2fa-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="7d2fa-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="7d2fa-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="7d2fa-126">AOL with Pivot クライアント</span><span class="sxs-lookup"><span data-stu-id="7d2fa-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="7d2fa-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="7d2fa-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="7d2fa-128">アレス</span><span class="sxs-lookup"><span data-stu-id="7d2fa-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="7d2fa-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="7d2fa-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="7d2fa-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="7d2fa-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="7d2fa-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="7d2fa-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="7d2fa-132">を持つ (Placeholder) プレースホルダー</span><span class="sxs-lookup"><span data-stu-id="7d2fa-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="7d2fa-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="7d2fa-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="7d2fa-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="7d2fa-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="7d2fa-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="7d2fa-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="7d2fa-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="7d2fa-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="7d2fa-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="7d2fa-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="7d2fa-138">BlackBerry 呼び出しログ</span><span class="sxs-lookup"><span data-stu-id="7d2fa-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="7d2fa-139">BlackBerry メッセンジャー</span><span class="sxs-lookup"><span data-stu-id="7d2fa-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="7d2fa-140">BlackBerry PIN</span><span class="sxs-lookup"><span data-stu-id="7d2fa-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="7d2fa-141">BlackBerry SMS</span><span class="sxs-lookup"><span data-stu-id="7d2fa-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="7d2fa-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="7d2fa-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="7d2fa-143">Bloomberg メール</span><span class="sxs-lookup"><span data-stu-id="7d2fa-143">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="7d2fa-144">Bloomberg Messaging</span><span class="sxs-lookup"><span data-stu-id="7d2fa-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="7d2fa-145">検索ボックス</span><span class="sxs-lookup"><span data-stu-id="7d2fa-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="7d2fa-146">Cisco IM &amp;プレゼンスサーバー</span><span class="sxs-lookup"><span data-stu-id="7d2fa-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="7d2fa-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="7d2fa-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="7d2fa-148">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="7d2fa-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="7d2fa-149">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="7d2fa-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="7d2fa-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="7d2fa-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="7d2fa-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="7d2fa-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="7d2fa-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="7d2fa-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="7d2fa-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="7d2fa-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="7d2fa-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="7d2fa-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="7d2fa-155">Google +</span><span class="sxs-lookup"><span data-stu-id="7d2fa-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="7d2fa-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="7d2fa-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="7d2fa-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="7d2fa-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="7d2fa-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="7d2fa-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="7d2fa-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="7d2fa-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="7d2fa-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="7d2fa-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="7d2fa-161">IBM 接続</span><span class="sxs-lookup"><span data-stu-id="7d2fa-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="7d2fa-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="7d2fa-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="7d2fa-163">ICE チャット</span><span class="sxs-lookup"><span data-stu-id="7d2fa-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="7d2fa-164">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="7d2fa-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="7d2fa-165">Instagram</span><span class="sxs-lookup"><span data-stu-id="7d2fa-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="7d2fa-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="7d2fa-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="7d2fa-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="7d2fa-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="7d2fa-168">IRC</span><span class="sxs-lookup"><span data-stu-id="7d2fa-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="7d2fa-169">Jive</span><span class="sxs-lookup"><span data-stu-id="7d2fa-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="7d2fa-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="7d2fa-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="7d2fa-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="7d2fa-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="7d2fa-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="7d2fa-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="7d2fa-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="7d2fa-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="7d2fa-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="7d2fa-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="7d2fa-175">マインド揃え</span><span class="sxs-lookup"><span data-stu-id="7d2fa-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="7d2fa-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="7d2fa-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="7d2fa-177">ウェブ</span><span class="sxs-lookup"><span data-stu-id="7d2fa-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="7d2fa-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="7d2fa-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="7d2fa-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="7d2fa-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="7d2fa-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="7d2fa-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="7d2fa-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="7d2fa-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="7d2fa-182">ピボット</span><span class="sxs-lookup"><span data-stu-id="7d2fa-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="7d2fa-183">QQ</span><span class="sxs-lookup"><span data-stu-id="7d2fa-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="7d2fa-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="7d2fa-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="7d2fa-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="7d2fa-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="7d2fa-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7d2fa-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="7d2fa-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="7d2fa-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="7d2fa-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="7d2fa-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="7d2fa-189">Squawker</span><span class="sxs-lookup"><span data-stu-id="7d2fa-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="7d2fa-190">Symphony</span><span class="sxs-lookup"><span data-stu-id="7d2fa-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="7d2fa-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="7d2fa-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="7d2fa-192">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="7d2fa-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="7d2fa-193">終わり</span><span class="sxs-lookup"><span data-stu-id="7d2fa-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="7d2fa-194">TTT</span><span class="sxs-lookup"><span data-stu-id="7d2fa-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="7d2fa-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="7d2fa-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="7d2fa-196">UBS チャット</span><span class="sxs-lookup"><span data-stu-id="7d2fa-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="7d2fa-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="7d2fa-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="7d2fa-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="7d2fa-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="7d2fa-199">Winny</span><span class="sxs-lookup"><span data-stu-id="7d2fa-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="7d2fa-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="7d2fa-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="7d2fa-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="7d2fa-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="7d2fa-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="7d2fa-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="7d2fa-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="7d2fa-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
