---
title: Office 365 でサードパーティのデータをアーカイブする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 管理者は、Office 365 の組織内のメールボックスに、ソーシャル メディアのプラットフォーム、インスタント メッセージング ・ プラットフォーム、およびドキュメントのコラボレーション プラットフォームからサード ・ パーティ製のデータをインポートできます。Facebook、Twitter やデータ ソースから Office 365 のデータをアーカイブできます。サード ・ パーティ製のデータを appply Office 365 のコンプライアンス機能 (法的保存要件、コンテンツの検索、保存ポリシーなど) ができます。
ms.openlocfilehash: 7af88338333e90bd208d693fbfd5bb691d44b538
ms.sourcegitcommit: 4c6c937ec51e8b754332e4c1c8d286e73e197e2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "23827091"
---
# <a name="archiving-third-party-data-in-office-365"></a><span data-ttu-id="3d9aa-105">Office 365 でサードパーティのデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="3d9aa-105">Archiving third-party data in Office 365</span></span>

<span data-ttu-id="3d9aa-p102">Office 365 では、管理者がインポートし、インスタント メッセージングのプラットフォーム、およびドキュメントのコラボレーション プラットフォームでは、Office 365 の組織内のメールボックスに、ソーシャル メディアのプラットフォームからのサード ・ パーティ製のデータをアーカイブできます。Office 365 にインポートすることができますサードパーティのデータ ソースの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p102">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization. Examples of third-party data sources that you can import to Office 365 include the following:</span></span> 
  
- <span data-ttu-id="3d9aa-108">**ソーシャル**・ Twitter、Facebook、Yammer、LinkedIn</span><span class="sxs-lookup"><span data-stu-id="3d9aa-108">**Social** - Twitter, Facebook, Yammer, and LinkedIn</span></span> 
    
- <span data-ttu-id="3d9aa-109">**インスタント メッセージング**の yahoo メッセンジャー、GoogleTalk、および Cisco の Jabber</span><span class="sxs-lookup"><span data-stu-id="3d9aa-109">**Instant messaging** - Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="3d9aa-110">**ドキュメントの共同作業**のボックスとドロップ ボックス</span><span class="sxs-lookup"><span data-stu-id="3d9aa-110">**Document collaboration** - Box and DropBox</span></span> 
    
- <span data-ttu-id="3d9aa-111">**業種**の Salesforce Chatter) などの顧客関係管理、トムソンガゼル Reuters および Bloomberg) などの金融サービス</span><span class="sxs-lookup"><span data-stu-id="3d9aa-111">**Vertical industries** - Customer Relationship Management (such as Salesforce Chatter) and Financials (such as Thomson Reuters and Bloomberg)</span></span> 
    
- <span data-ttu-id="3d9aa-112">**SMS/テキスト メッセージ**の BlackBerry</span><span class="sxs-lookup"><span data-stu-id="3d9aa-112">**SMS/text messaging** - BlackBerry</span></span> 
    
<span data-ttu-id="3d9aa-p103">サード ・ パーティ製のデータがインポートされると、Office 365 のコンプライアンス機能を割り当てることができます-証拠保全、コンテンツの検索、埋め込み先のアーカイブ、監査、および Office 365 のリテンション ・ ポリシーなど、このデータにします。たとえば、証拠保全にメールボックスが格納されると、サード パーティのデータは保持されます。コンテンツの検索を使用して、サード パーティのデータを検索できます。アーカイブを適用することや、Microsoft のデータの場合と同様に、サード ・ パーティ製データ保存のポリシーします。つまり、Office 365 のサード ・ パーティ製データのアーカイブを支援して政府や規制ポリシーに準拠したままです。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p103">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data. For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved. You can search third-party data by using Content Search. Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data. In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>
  
<span data-ttu-id="3d9aa-118">ここでは、サード ・ パーティ製データを Office 365 にインポートするために必要なプロセスと手順の概要を説明です。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-118">Here's an overview of the process and the steps necessary to import third-party data to Office 365.</span></span>

[<span data-ttu-id="3d9aa-119">手順 1: サード パーティのデータのパートナーを見つける</span><span class="sxs-lookup"><span data-stu-id="3d9aa-119">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="3d9aa-120">手順 2: Office 365 でサード パーティ データのメールボックスを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="3d9aa-120">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="3d9aa-121">手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="3d9aa-121">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="3d9aa-122">手順 4: パートナーに情報を提供する</span><span class="sxs-lookup"><span data-stu-id="3d9aa-122">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="3d9aa-123">手順 5: サード ・ パーティ製データ コネクタを Azure Active Directory に登録します。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-123">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="3d9aa-124">動作するサードパーティ製のデータがプロセスをインポートする方法 ></span><span class="sxs-lookup"><span data-stu-id="3d9aa-124">How the third-party data import process works></span></span>

<span data-ttu-id="3d9aa-125">以下の図および説明は、サードパーティのデータのインポート プロセスが実行される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-125">The following illustration and description explain how the third-party data import process works.</span></span>
  
![サードパーティのデータのインポート プロセスが実行される方法](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="3d9aa-127">お客様は、サードパーティのデータ ソースから項目を抽出し、それらのアイテムを Office 365 にインポートするコネクタを構成するのには最適なパートナーと連携します。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-127">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="3d9aa-p104">パートナー コネクタは、(スケジュールまたはで構成された単位で)、サードパーティ製の API を使用してサードパーティのデータ ソースに接続し、データ ソースから項目を抽出します。パートナーのコネクタは、アイテムの内容を電子メールのメッセージ形式に変換します。メッセージ形式のスキーマの詳細については、[詳細について](#more-information)はを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p104">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source. The partner connector converts the content of an item to an email message format. See the [More information](#more-information) section for a description of the message format schema.</span></span> 
    
3. <span data-ttu-id="3d9aa-131">パートナーのコネクタは、既知のエンドポイントを使用して Exchange Web サービス (EWS) を使用して、Office 365 で Azure のサービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-131">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="3d9aa-p105">アイテムは特定のユーザーのメールボックスまたは "catch-all" というサードパーティ データのメールボックスにインポートされます。アイテムが特定のユーザーのメールボックスにインポートされるか、またはサードパーティ データのメールボックスにインポートされるかは、以下の条件に基づきます。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p105">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="3d9aa-p106">**Office 365 ユーザー アカウントに対応するユーザー ID を持っているアイテム**の場合はパートナーのコネクタは、Office 365 では、アイテムの ID がフォルダーにコピー、**削除**ユーザーの特定のユーザーにサード パーティのデータ ソース内の項目のユーザー ID をマップできます a.回復可能なアイテム] フォルダー。削除フォルダー内のアイテムにアクセスできません。ただし、削除フォルダー内のアイテムを検索するのには、Office 365 の電子的証拠開示のツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p106">a. **Items that have a user ID that corresponds to an Office 365 user account** - If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder. Users can't access items in the Purges folder. However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="3d9aa-p107">b. の**項目が、Office 365 のユーザー アカウントに対応するユーザー ID を必要はありません**- パートナーのコネクタは、特定のユーザーが Office 365 では、アイテムの ID は、サード ・ パーティ製データ メールボックスの**受信トレイ**フォルダーにコピーするアイテムのユーザー ID をマップできない場合。受信トレイにアイテムをインポートすることができますまたは他の組織とパートナーのコネクタの構成で実行する調整が必要なかどうかを参照してくださいの表示および、これらの項目を管理するサード ・ パーティ製のメールボックスにサインインします。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p107">b. **Items that don't have a user ID that corresponds to an Office 365 user account** - If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox. Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="3d9aa-141">手順 1: サード パーティのデータのパートナーを見つける</span><span class="sxs-lookup"><span data-stu-id="3d9aa-141">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="3d9aa-p108">Office 365 のサード ・ パーティ製データのアーカイブの重要なコンポーネントは検索と、サード ・ パーティ製のデータ ソースからデータをキャプチャし、Office 365 にインポートすることで専門とするマイクロソフトのパートナーと連携します。データがインポートされると、そのアーカイブし、とともに保持、組織が Exchange からの電子メールやドキュメントを SharePoint とビジネスの OneDrive など、他の Microsoft のデータの。パートナー (BlackBerry、Facebook、Google +、トムソンガゼル Reuters、Twitter、および YouTube) などの組織のサード ・ パーティ製のデータ ソースからデータを抽出し、そのデータを Office 365 の API としての Exchange メールボックスにアイテムをインポートするコネクタを作成します。メッセージを電子メールで送信します。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p108">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365. After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business. A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="3d9aa-145">次の各項では、マイクロソフトのパートナー- とをサポートしているサード ・ パーティ製のデータ ソース: Office 365 のサード ・ パーティ製のデータをアーカイブするためのプログラムに参加していること。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-145">The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="3d9aa-146">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="3d9aa-146">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="3d9aa-147">Actiance</span><span class="sxs-lookup"><span data-stu-id="3d9aa-147">Actiance</span></span>](#actiance)
  
[<span data-ttu-id="3d9aa-148">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="3d9aa-148">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="3d9aa-149">Globanet</span><span class="sxs-lookup"><span data-stu-id="3d9aa-149">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="3d9aa-150">OpenText</span><span class="sxs-lookup"><span data-stu-id="3d9aa-150">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="3d9aa-151">Verba</span><span class="sxs-lookup"><span data-stu-id="3d9aa-151">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="3d9aa-152">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="3d9aa-152">17a-4 LLC</span></span>

<span data-ttu-id="3d9aa-153">17a-4 LLC は、次のサードパーティ データ ソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-153">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="3d9aa-154">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="3d9aa-154">BlackBerry</span></span>
    
- <span data-ttu-id="3d9aa-155">Bloomberg データ ストリーム</span><span class="sxs-lookup"><span data-stu-id="3d9aa-155">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="3d9aa-156">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="3d9aa-156">Cisco Jabber</span></span>
    
- <span data-ttu-id="3d9aa-157">FactSet</span><span class="sxs-lookup"><span data-stu-id="3d9aa-157">FactSet</span></span>
    
- <span data-ttu-id="3d9aa-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="3d9aa-158">HipChat</span></span>
    
- <span data-ttu-id="3d9aa-159">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="3d9aa-159">InvestEdge</span></span>
    
- <span data-ttu-id="3d9aa-160">LivePerson</span><span class="sxs-lookup"><span data-stu-id="3d9aa-160">LivePerson</span></span>
    
- <span data-ttu-id="3d9aa-161">
MessageLabs データ ストリーム
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-161">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="3d9aa-162">OpenText</span><span class="sxs-lookup"><span data-stu-id="3d9aa-162">OpenText</span></span>
    
- <span data-ttu-id="3d9aa-163">Oracle/ATG 'click-to-call' Live ヘルプ
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-163">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="3d9aa-164">Pivot IMTRADER
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-164">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="3d9aa-165">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="3d9aa-165">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="3d9aa-166">MindAlign</span><span class="sxs-lookup"><span data-stu-id="3d9aa-166">MindAlign</span></span>
    
- <span data-ttu-id="3d9aa-167">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-167">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="3d9aa-168">
Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-168">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="3d9aa-169">
Skype for Business Online (Lync Online)
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-169">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="3d9aa-170">SQL データベース</span><span class="sxs-lookup"><span data-stu-id="3d9aa-170">SQL Databases</span></span>
    
- <span data-ttu-id="3d9aa-171">
Squawker
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-171">Squawker</span></span>
    
- <span data-ttu-id="3d9aa-172">Thomson Reuters Eikon Messenger
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-172">Thomson Reuters Eikon Messenger</span></span>
  
### <a name="actiance"></a><span data-ttu-id="3d9aa-173">Actiance</span><span class="sxs-lookup"><span data-stu-id="3d9aa-173">Actiance</span></span>

<span data-ttu-id="3d9aa-174">[Actiance](https://www.actiance.com)には、以下のサードパーティのデータ ソースがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-174">[Actiance](https://www.actiance.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3d9aa-175">AIM</span><span class="sxs-lookup"><span data-stu-id="3d9aa-175">AIM</span></span>
    
- <span data-ttu-id="3d9aa-176">American Idol</span><span class="sxs-lookup"><span data-stu-id="3d9aa-176">American Idol</span></span>
    
- <span data-ttu-id="3d9aa-177">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="3d9aa-177">Apple Juice</span></span>
    
- <span data-ttu-id="3d9aa-178">
AOL with Pivot クライアント
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-178">AOL with Pivot client</span></span>
    
- <span data-ttu-id="3d9aa-179">Ares</span><span class="sxs-lookup"><span data-stu-id="3d9aa-179">Ares</span></span>
    
- <span data-ttu-id="3d9aa-180">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="3d9aa-180">Bazaar Voice</span></span>
    
- <span data-ttu-id="3d9aa-181">Bearshare</span><span class="sxs-lookup"><span data-stu-id="3d9aa-181">Bear Share</span></span>
    
- <span data-ttu-id="3d9aa-182">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="3d9aa-182">Bit Torrent</span></span>
    
- <span data-ttu-id="3d9aa-183">BlackBerry 呼び出しログ (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-183">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d9aa-184">BlackBerry メッセンジャー (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-184">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d9aa-185">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-185">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d9aa-186">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-186">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d9aa-187">Bloomberg メール
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-187">Bloomberg Mail</span></span>
    
- <span data-ttu-id="3d9aa-188">CellTrust</span><span class="sxs-lookup"><span data-stu-id="3d9aa-188">CellTrust</span></span>
    
- <span data-ttu-id="3d9aa-189">チャットのインポート
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-189">Chat Import</span></span>
    
- <span data-ttu-id="3d9aa-190">チャットのリアルタイム ロギングとポリシー
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-190">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="3d9aa-191">チャター
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-191">Chatter</span></span>
    
- <span data-ttu-id="3d9aa-192">Cisco IM&amp;プレゼンス サーバー (v9.0.1、v9.1、v9.1.1 SU1、v10、v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-192">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="3d9aa-193">Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-193">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="3d9aa-194">共同作業のインポート
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-194">Collaboration Import</span></span>
    
- <span data-ttu-id="3d9aa-195">共同作業のリアルタイム ロギング
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-195">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="3d9aa-196">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="3d9aa-196">Direct Connect</span></span>
    
- <span data-ttu-id="3d9aa-197">Facebook</span><span class="sxs-lookup"><span data-stu-id="3d9aa-197">Facebook</span></span>
    
- <span data-ttu-id="3d9aa-198">FactSet</span><span class="sxs-lookup"><span data-stu-id="3d9aa-198">FactSet</span></span>
    
- <span data-ttu-id="3d9aa-199">FastTrack</span><span class="sxs-lookup"><span data-stu-id="3d9aa-199">FastTrack</span></span>
    
- <span data-ttu-id="3d9aa-200">Gnutella</span><span class="sxs-lookup"><span data-stu-id="3d9aa-200">Gnutella</span></span>
    
- <span data-ttu-id="3d9aa-201">Google+
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-201">Google+</span></span>
    
- <span data-ttu-id="3d9aa-202">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="3d9aa-202">GoToMyPC</span></span>
    
- <span data-ttu-id="3d9aa-203">Hopster</span><span class="sxs-lookup"><span data-stu-id="3d9aa-203">Hopster</span></span>
    
- <span data-ttu-id="3d9aa-204">HubConnex</span><span class="sxs-lookup"><span data-stu-id="3d9aa-204">HubConnex</span></span>
    
- <span data-ttu-id="3d9aa-205">IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-205">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="3d9aa-206">IBM Connections Chat Cloud
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-206">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="3d9aa-207">IBM Connections Social Cloud
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-207">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="3d9aa-208">IBM SameTime Advanced 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-208">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="3d9aa-209">IBM SameTime Communicate 9.0
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-209">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="3d9aa-210">IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-210">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="3d9aa-211">IBM SameTime Complete 9.0
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-211">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="3d9aa-212">IBM SameTime Conference 9.0
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-212">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="3d9aa-213">IBM SameTime Meeting 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-213">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="3d9aa-214">アイス/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="3d9aa-214">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="3d9aa-215">IM のインポート
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-215">IM Import</span></span>
    
- <span data-ttu-id="3d9aa-216">IM のリアルタイム ロギングとポリシー
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-216">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="3d9aa-217">Indii Messenger
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-217">Indii Messenger</span></span>
    
- <span data-ttu-id="3d9aa-218">Instant Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-218">Instant Bloomberg</span></span>
    
- <span data-ttu-id="3d9aa-219">IRC</span><span class="sxs-lookup"><span data-stu-id="3d9aa-219">IRC</span></span>
    
- <span data-ttu-id="3d9aa-220">Jive
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-220">Jive</span></span>
    
- <span data-ttu-id="3d9aa-221">Jive 6 Real Time Logging (v6、v7)
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-221">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="3d9aa-222">Jive のインポート</span><span class="sxs-lookup"><span data-stu-id="3d9aa-222">Jive Import</span></span>
    
- <span data-ttu-id="3d9aa-223">JXTA</span><span class="sxs-lookup"><span data-stu-id="3d9aa-223">JXTA</span></span>
    
- <span data-ttu-id="3d9aa-224">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="3d9aa-224">LinkedIn</span></span>
    
- <span data-ttu-id="3d9aa-225">
Microsoft Lync (2010、2013)
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-225">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="3d9aa-226">MFTP</span><span class="sxs-lookup"><span data-stu-id="3d9aa-226">MFTP</span></span>
    
- <span data-ttu-id="3d9aa-227">Microsoft Lync 2013 Voice
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-227">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="3d9aa-228">Microsoft SharePoint (2010、2013)
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-228">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="3d9aa-229">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3d9aa-229">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="3d9aa-230">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-230">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="3d9aa-231">MindAlign</span><span class="sxs-lookup"><span data-stu-id="3d9aa-231">MindAlign</span></span>
    
- <span data-ttu-id="3d9aa-232">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="3d9aa-232">Mobile Guard</span></span>
    
- <span data-ttu-id="3d9aa-233">MSN</span><span class="sxs-lookup"><span data-stu-id="3d9aa-233">MSN</span></span>
    
- <span data-ttu-id="3d9aa-234">My Space</span><span class="sxs-lookup"><span data-stu-id="3d9aa-234">My Space</span></span>
    
- <span data-ttu-id="3d9aa-235">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="3d9aa-235">NEONetwork</span></span>
    
- <span data-ttu-id="3d9aa-236">Office 365 Lync Dedicated
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-236">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="3d9aa-237">Office 365 Shared IM
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-237">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="3d9aa-238">Pinterest</span><span class="sxs-lookup"><span data-stu-id="3d9aa-238">Pinterest</span></span>
    
- <span data-ttu-id="3d9aa-239">Pivot</span><span class="sxs-lookup"><span data-stu-id="3d9aa-239">Pivot</span></span>
    
- <span data-ttu-id="3d9aa-240">QQ</span><span class="sxs-lookup"><span data-stu-id="3d9aa-240">QQ</span></span>
    
- <span data-ttu-id="3d9aa-241">Skype for Business 2015
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-241">Skype for Business 2015</span></span>
    
- <span data-ttu-id="3d9aa-242">SoftEther</span><span class="sxs-lookup"><span data-stu-id="3d9aa-242">SoftEther</span></span>
    
- <span data-ttu-id="3d9aa-243">Symphony
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-243">Symphony</span></span>
    
- <span data-ttu-id="3d9aa-244">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-244">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="3d9aa-245">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-245">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="3d9aa-246">Tor</span><span class="sxs-lookup"><span data-stu-id="3d9aa-246">Tor</span></span>
    
- <span data-ttu-id="3d9aa-247">TTT</span><span class="sxs-lookup"><span data-stu-id="3d9aa-247">TTT</span></span>
    
- <span data-ttu-id="3d9aa-248">Twitter</span><span class="sxs-lookup"><span data-stu-id="3d9aa-248">Twitter</span></span>
    
- <span data-ttu-id="3d9aa-249">WinMX</span><span class="sxs-lookup"><span data-stu-id="3d9aa-249">WinMX</span></span>
    
- <span data-ttu-id="3d9aa-250">Winny</span><span class="sxs-lookup"><span data-stu-id="3d9aa-250">Winny</span></span>
    
- <span data-ttu-id="3d9aa-251">Yahoo
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-251">Yahoo</span></span>
    
- <span data-ttu-id="3d9aa-252">Yammer</span><span class="sxs-lookup"><span data-stu-id="3d9aa-252">Yammer</span></span>
    
- <span data-ttu-id="3d9aa-253">YouTube</span><span class="sxs-lookup"><span data-stu-id="3d9aa-253">YouTube</span></span>
    
  
### <a name="archivesocial"></a><span data-ttu-id="3d9aa-254">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="3d9aa-254">ArchiveSocial</span></span>

<span data-ttu-id="3d9aa-255">[ArchiveSocial](https://www.archivesocial.com)には、以下のサードパーティのデータ ソースがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-255">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3d9aa-256">Facebook</span><span class="sxs-lookup"><span data-stu-id="3d9aa-256">Facebook</span></span>
    
- <span data-ttu-id="3d9aa-257">Flickr
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-257">Flickr</span></span>
    
- <span data-ttu-id="3d9aa-258">Instagram
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-258">Instagram</span></span>
    
- <span data-ttu-id="3d9aa-259">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="3d9aa-259">LinkedIn</span></span>
    
- <span data-ttu-id="3d9aa-260">Pinterest</span><span class="sxs-lookup"><span data-stu-id="3d9aa-260">Pinterest</span></span>
    
- <span data-ttu-id="3d9aa-261">Twitter</span><span class="sxs-lookup"><span data-stu-id="3d9aa-261">Twitter</span></span>
    
- <span data-ttu-id="3d9aa-262">YouTube</span><span class="sxs-lookup"><span data-stu-id="3d9aa-262">YouTube</span></span>
    
- <span data-ttu-id="3d9aa-263">Vimeo</span><span class="sxs-lookup"><span data-stu-id="3d9aa-263">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="3d9aa-264">Globanet</span><span class="sxs-lookup"><span data-stu-id="3d9aa-264">Globanet</span></span>

<span data-ttu-id="3d9aa-265">[Globanet](https://www.globanet.com)には、以下のサードパーティのデータ ソースがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-265">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3d9aa-266">AOL with Pivot クライアント</span><span class="sxs-lookup"><span data-stu-id="3d9aa-266">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="3d9aa-267">BlackBerry 呼び出しログ (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-267">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d9aa-268">BlackBerry メッセンジャー (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-268">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d9aa-269">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-269">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d9aa-270">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-270">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="3d9aa-271">Bloomberg チャット
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-271">Bloomberg Chat</span></span>
    
- <span data-ttu-id="3d9aa-272">Bloomberg メール
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-272">Bloomberg Mail</span></span>
    
- <span data-ttu-id="3d9aa-273">Box
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-273">Box</span></span>
    
- <span data-ttu-id="3d9aa-274">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="3d9aa-274">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="3d9aa-275">Cisco IM&amp;プレゼンス サーバー (v10、v10.5.1 SU1、v11.0、v11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-275">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="3d9aa-276">Cisco Webex チーム</span><span class="sxs-lookup"><span data-stu-id="3d9aa-276">Cisco Webex Teams</span></span>

- <span data-ttu-id="3d9aa-277">Citrix ワークスペース&amp;ShareFile</span><span class="sxs-lookup"><span data-stu-id="3d9aa-277">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="3d9aa-278">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="3d9aa-278">CrowdCompass</span></span>

- <span data-ttu-id="3d9aa-279">カスタムの区切り記号付きテキスト ファイル
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-279">Custom delimited text files</span></span>
    
- <span data-ttu-id="3d9aa-280">カスタムの XML ファイル
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-280">Custom XML files</span></span>
    
- <span data-ttu-id="3d9aa-281">Facebook (ページ)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-281">Facebook (Pages)</span></span>
    
- <span data-ttu-id="3d9aa-282">Factset
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-282">Factset</span></span>
    
- <span data-ttu-id="3d9aa-283">FXConnect</span><span class="sxs-lookup"><span data-stu-id="3d9aa-283">FXConnect</span></span>
    
- <span data-ttu-id="3d9aa-284">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="3d9aa-284">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="3d9aa-285">Jive
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-285">Jive</span></span>
    
- <span data-ttu-id="3d9aa-286">Macgregor XIP
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-286">Macgregor XIP</span></span>

- <span data-ttu-id="3d9aa-287">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3d9aa-287">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="3d9aa-288">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="3d9aa-288">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="3d9aa-289">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3d9aa-289">Microsoft Teams</span></span>
       
- <span data-ttu-id="3d9aa-290">Microsoft Yammer
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-290">Microsoft Yammer</span></span>
    
- <span data-ttu-id="3d9aa-291">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="3d9aa-291">Mobile Guard</span></span>
    
- <span data-ttu-id="3d9aa-292">Pivot</span><span class="sxs-lookup"><span data-stu-id="3d9aa-292">Pivot</span></span>
    
- <span data-ttu-id="3d9aa-293">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="3d9aa-293">Salesforce Chatter</span></span>

- <span data-ttu-id="3d9aa-294">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3d9aa-294">Skype for Business Online</span></span>
    
- <span data-ttu-id="3d9aa-295">Skype for Business、バージョン 2007 R2 ～ 2016 (オンプレミス)
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-295">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="3d9aa-296">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="3d9aa-296">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="3d9aa-297">Symphony
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-297">Symphony</span></span>
    
- <span data-ttu-id="3d9aa-298">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-298">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="3d9aa-299">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-299">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="3d9aa-300">Thomson Reuters Dealings 3000 / FX トレーディング
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-300">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="3d9aa-301">Twitter</span><span class="sxs-lookup"><span data-stu-id="3d9aa-301">Twitter</span></span>
    
- <span data-ttu-id="3d9aa-302">UBS チャット
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-302">UBS Chat</span></span>
    
- <span data-ttu-id="3d9aa-303">YouTube</span><span class="sxs-lookup"><span data-stu-id="3d9aa-303">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="3d9aa-304">OpenText</span><span class="sxs-lookup"><span data-stu-id="3d9aa-304">OpenText</span></span>

<span data-ttu-id="3d9aa-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)は、以下のサードパーティのデータ ソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3d9aa-306">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="3d9aa-306">Axs Encrypted</span></span>
    
- <span data-ttu-id="3d9aa-307">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="3d9aa-307">Axs Exchange</span></span>
    
- <span data-ttu-id="3d9aa-308">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="3d9aa-308">Axs Local Archive</span></span>
    
- <span data-ttu-id="3d9aa-309">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="3d9aa-309">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="3d9aa-310">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="3d9aa-310">Axs Signed</span></span>
    
- <span data-ttu-id="3d9aa-311">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="3d9aa-311">Bloomberg</span></span>
    
- <span data-ttu-id="3d9aa-312">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="3d9aa-312">Thomson Reuters</span></span>
  
### <a name="verba"></a><span data-ttu-id="3d9aa-313">Verba</span><span class="sxs-lookup"><span data-stu-id="3d9aa-313">Verba</span></span>

<span data-ttu-id="3d9aa-314">[Verba](https://www.verba.com)には、以下のサードパーティのデータ ソースがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-314">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="3d9aa-315">Avaya Aura ビデオ
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-315">Avaya Aura Video</span></span>
    
- <span data-ttu-id="3d9aa-316">Avaya Aura 音声
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-316">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="3d9aa-317">Avtec ラジオ
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-317">Avtec Radio</span></span>
    
- <span data-ttu-id="3d9aa-318">Bosch/Telex ラジオ
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-318">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="3d9aa-319">BroadSoft ビデオ
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-319">BroadSoft Video</span></span>
    
- <span data-ttu-id="3d9aa-320">BroadSoft 音声
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-320">BroadSoft Voice</span></span>
    
- <span data-ttu-id="3d9aa-321">Centile 音声
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-321">Centile Voice</span></span>
    
- <span data-ttu-id="3d9aa-322">Cisco Jabber IM
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-322">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="3d9aa-323">Cisco UC ビデオ
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-323">Cisco UC Video</span></span>
    
- <span data-ttu-id="3d9aa-324">Cisco UC 音声
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-324">Cisco UC Voice</span></span>
    
- <span data-ttu-id="3d9aa-325">Cisco UCCX/UCCE ビデオ</span><span class="sxs-lookup"><span data-stu-id="3d9aa-325">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="3d9aa-326">Cisco UCCX/UCCE 音声</span><span class="sxs-lookup"><span data-stu-id="3d9aa-326">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="3d9aa-327">ESChat ラジオ</span><span class="sxs-lookup"><span data-stu-id="3d9aa-327">ESChat Radio</span></span>
    
- <span data-ttu-id="3d9aa-328">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="3d9aa-328">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="3d9aa-329">IP Trade 音声
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-329">IP Trade Voice</span></span>
    
- <span data-ttu-id="3d9aa-330">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="3d9aa-330">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="3d9aa-331">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-331">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="3d9aa-332">Mitel MiContact Center for Lync (prairieFyre) 
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-332">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="3d9aa-333">Oracle / Acme Packet Session Border Controller ビデオ  
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-333">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="3d9aa-334">Oracle / Acme Packet Session Border Controller 音声
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-334">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="3d9aa-335">Singtel モバイル ボイス
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-335">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="3d9aa-336">SIPREC ビデオ</span><span class="sxs-lookup"><span data-stu-id="3d9aa-336">SIPREC Video</span></span>
    
-  <span data-ttu-id="3d9aa-337">SIPREC 音声</span><span class="sxs-lookup"><span data-stu-id="3d9aa-337">SIPREC Voice</span></span> 
    
- <span data-ttu-id="3d9aa-338">Skype for Business / Lync IM
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-338">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="3d9aa-339">Skype for Business / Lync ビデオ
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-339">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="3d9aa-340">Skype for Business / Lync 音声
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-340">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="3d9aa-341">Speakerbus 音声
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-341">Speakerbus Voice</span></span>
    
- <span data-ttu-id="3d9aa-342">標準的な SIP/H.323 ビデオ 
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-342">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="3d9aa-343">標準的な SIP/H.323 音声 
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-343">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="3d9aa-344">Truphone 音声
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-344">Truphone Voice</span></span>
    
- <span data-ttu-id="3d9aa-345">TwistedPair ラジオ
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-345">TwistedPair Radio</span></span>
    
- <span data-ttu-id="3d9aa-346">Windows デスクトップ コンピューターの画面 
</span><span class="sxs-lookup"><span data-stu-id="3d9aa-346">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="3d9aa-347">手順 2: Office 365 でサード パーティ データのメールボックスを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="3d9aa-347">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="3d9aa-p109">作成し、Office 365 にデータをインポートするためのサード ・ パーティ製データ メールボックスを構成するための手順を次に示します。前に説明すると、パートナーのコネクタは、Office 365 のユーザー アカウントにアイテムのユーザー ID をマップできない場合、このメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p109">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365. As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="3d9aa-350">**Office 365 の管理ページでこれらのタスクを完了します。**</span><span class="sxs-lookup"><span data-stu-id="3d9aa-350">**Complete these tasks in the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="3d9aa-p110">Office 365 に新しいユーザー アカウントを作成し、Exchange オンライン計画 2 ライセンスを割り当てること[Office 365 のユーザーの追加](https://go.microsoft.com/fwlink/p/?LinkId=692098)を参照してください。証拠保全のメールボックスを配置するか、無制限のストレージ クォータを持つアーカイブ先のメールボックスを有効にするのには計画の 2 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p110">Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="3d9aa-353">サード ・ パーティ製データ メールボックスのユーザー アカウントを Office 365 の [ **Exchange 管理者**の管理者の役割に追加します。[Office 365 の管理者の役割の割り当て](https://go.microsoft.com/fwlink/p/?LinkId=532393)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-353">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3d9aa-p111">このユーザー アカウントの資格情報を控えておきます。手順 4 で説明するように、この情報をパートナーに提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p111">Write down the credentials for this user account. You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="3d9aa-356">**Exchange 管理センターでこれらのタスクを完了します。**</span><span class="sxs-lookup"><span data-stu-id="3d9aa-356">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="3d9aa-p112">アドレス帳と、組織内の他のアドレス一覧からサード ・ パーティ製データ メールボックスを非表示にします。[ユーザーのメールボックスの管理](https://go.microsoft.com/fwlink/p/?LinkId=616058)を参照してください。また、次の PowerShell コマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p112">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058). Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="3d9aa-359">**FullAccess**アクセス許可、メールボックスを割り当てるサード ・ パーティ製データ管理者またはコンプライアンス担当役員は、Outlook デスクトップ クライアントでサード ・ パーティ製データ メールボックスを開くことができますように[受信者のアクセス権の管理](https://go.microsoft.com/fwlink/p/?LinkId=692104)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-359">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="3d9aa-360">サード ・ パーティ製データ メールボックスの次コンプライアンスに関連する Office 365 機能を有効にするには。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-360">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="3d9aa-p113">アーカイブ先のメールボックスを有効にします。参照してください[Office 365 のセキュリティのアーカイブ メールボックスを有効にする&amp;コンプライアンス センター](enable-archive-mailboxes.md)し、 [Office 365 で無制限のアーカイブを有効に](enable-unlimited-archiving.md)します。これは、テンプレートを使用するサード ・ パーティ製のデータ項目をアーカイブ メールボックスに移動するアーカイブ ポリシーを設定することによってプライマリ メールボックスの空き記憶領域です。無制限のストレージを持つサード ・ パーティ製データの提供このされます。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p113">Enable the archive mailbox; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md). This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox. This will provide you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="3d9aa-p114">証拠保全のサード ・ パーティ製データ メールボックスを配置します。Office 365 のセキュリティでは、Office 365 の保持ポリシーを適用することも&amp;コンプライアンス センターです。保留中のこのメールボックスを配置すること、(永久にまたは指定した期間) に、サード ・ パーティ製のデータ アイテムを保持し、メールボックスからパージされないようにします。次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p114">Place the third-party data mailbox on Litigation Hold. You can also apply an Office 365 retention policy in the Office 365 Security &amp; Compliance Center. Placing this mailbox on hold will retain third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox. See one of the following topics:</span></span>
    
      - [<span data-ttu-id="3d9aa-368">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="3d9aa-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="3d9aa-369">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="3d9aa-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="3d9aa-p115">所有者、デリゲート、および管理者メールボックスへのアクセス、サード ・ パーティ製のデータはログ出力のメールボックスの監査を有効にします。[メールボックスを Office 365 で監査を有効にする](enable-mailbox-auditing.md)を参照してください。これは、オプションを選択するサード ・ パーティ製データ メールボックスにアクセスできる任意のユーザーによって実行されるすべてのアクティビティを監査することができます。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p115">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). This will allow you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="3d9aa-372">手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="3d9aa-372">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="3d9aa-p116">次の手順では、サード パーティのデータをサポートするためにユーザーのメールボックスを構成します。Exchange 管理センターを使用するか、対応する Windows PowerShell コマンドレットを使用して、これらのタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p116">The next step is to configure user mailboxes to support third-party data. Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="3d9aa-375">各ユーザーのアーカイブ メールボックスを有効にします。参照してください[Office 365 のセキュリティのアーカイブ メールボックスを有効にする&amp;コンプライアンス センター](enable-archive-mailboxes.md)し、 [Office 365 で無制限のアーカイブを有効に](enable-unlimited-archiving.md)します。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-375">Enable the archive mailbox for each user; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="3d9aa-376">証拠保全でユーザーのメールボックスを配置するか、Office 365 保持ポリシーを適用次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-376">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="3d9aa-377">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="3d9aa-377">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="3d9aa-378">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="3d9aa-378">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="3d9aa-379">前述のように、メールボックスをホールドの対象にすると、サードパーティ データ ソースからのアイテムを保持する期間を設定したり、アイテムを無期限に保持したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-379">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="3d9aa-380">手順 4: パートナーに情報を提供する</span><span class="sxs-lookup"><span data-stu-id="3d9aa-380">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="3d9aa-381">最後の手順は、パートナーが Office 365 の組織に接続するコネクタを構成し、ユーザーのメールボックスおよびサード パーティのデータのメールボックスにデータをインポートできるように、パートナーに以下の情報を提供することです。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-381">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="3d9aa-382">Office 365 では、Azure のサービスへの接続に使用されるエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-382">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="3d9aa-p117">資格情報 (Office 365 のユーザー ID とパスワード) 手順 2 で作成したサード ・ パーティ製データ メールボックス内の標識です。パートナーのコネクタにアクセスし、サード ・ パーティ製データ メールボックスにユーザーのメールボックスにアイテムをインポートするため、これらの資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p117">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2. These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="3d9aa-385">手順 5: サード ・ パーティ製データ コネクタを Azure Active Directory に登録します。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-385">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="3d9aa-p118">認証を使用して新しい Exchange オンライン データをインポートするのには、Office 365 の組織に接続しようとするサード ・ パーティ製データ コネクタを認証するために開始 2018 年 9 月 30日 Office 365 で Azure サービスが開始されます。この変更の理由は、Azure のサービスに接続する前に説明したエンドポイントを使用する whitelisting サードパーティ製のコネクタを基盤とする現在の方法よりも高いセキュリティを提供する最新の認証をします。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p118">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data. The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="3d9aa-p119">新しい近代的な認証方法を使用して Office 365 に接続するためのサード ・ パーティ製データ コネクタを有効にするには、組織の Office 365 の管理者する必要があります Azure Active Directory の信頼されたサービス アプリケーションとして、コネクタを登録するのには同意するものです。これは、は、Azure Active Directory 内の組織のデータにアクセスするためのコネクタを許可するアクセス許可の要求を受け入れることによって行われます。この依頼を承諾した後は、サード ・ パーティ製データ コネクタが Azure Active directory のエンタープライズ ・ アプリケーションとして追加され、サービス主体として表されます。承認プロセスの詳細は、[テナント管理者の承認](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p119">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory. This is done by accepting a permissions request to allow the connector to access your organization's data in Azure Active Directory. After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal. For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="3d9aa-392">アクセスし、コネクタを登録するのには依頼を承諾する手順を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-392">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="3d9aa-393">[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動し、Office 365 のグローバル管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-393">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="3d9aa-p120">次のダイアログ ボックスが表示されます。コネクタに割り当てられるアクセス許可を確認するのには、カレットを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p120">The following dialog box is displayed. You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/><span data-ttu-id="3d9aa-396">![アクセス許可の要求] ダイアログが表示されます。](media/O365_ThirdPartyDataConnector_OptIn1.png)</span><span class="sxs-lookup"><span data-stu-id="3d9aa-396">![The permissions request dialog is displayed](media/O365_ThirdPartyDataConnector_OptIn1.png)</span></span>
2. <span data-ttu-id="3d9aa-397">**受け付ける**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-397">Click **Accept**.</span></span>

<span data-ttu-id="3d9aa-p121">依頼を承諾すると、 [Azure ポータル](https://portal.azure.com)が表示されます。**Azure Active Directory**をクリックして、組織のアプリケーションの一覧を表示するのには > **エンタープライズ ・ アプリケーション**です。**エンタープライズ ・ アプリケーション**のブレードでは、Office 365 のサード ・ パーティ製データ コネクタが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p121">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed. To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**. The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d9aa-p122">後 2018 年 9 月 30日サード ・ パーティ製が不要になったにデータをインポート、組織内のメールボックス Azure Active Directory でサード ・ パーティ製データ コネクタを登録していない場合。ノートの既存のサード ・ パーティ製データ コネクタ (2018 年 9 月 30日前に作成されたもの) は、手順 5 の手順に従って、Azure Active Directory にも登録してください。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p122">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory. Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="3d9aa-403">サード ・ パーティ製データ コネクタの同意を取り消す</span><span class="sxs-lookup"><span data-stu-id="3d9aa-403">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="3d9aa-p123">Azure Active Directory のサード ・ パーティ製データ コネクタを登録するのにはアクセス許可の要求に同意の上、組織後、組織は、いつでもその承諾を取り消すことができます。ただし、コネクタの同意を取り消すと、サードパーティのデータ ソースからデータが不要になった Office 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p123">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time. However, revoking the consent for a connector will mean that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="3d9aa-p124">サード ・ パーティ製データ コネクタの同意を取り消すにはすることができますからアプリケーションを削除 (対応するサービス ・ プリンシパルを削除する) を Azure Active Directory の**エンタープライズ ・ アプリケーション**のブレードを使用して、Azure のポータルでは、または、[を使用して、削除 MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) Office 365 の PowerShell にします。Azure Active Directory PowerShell の[削除 AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal)コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p124">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell. You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="3d9aa-408">詳細情報</span><span class="sxs-lookup"><span data-stu-id="3d9aa-408">More information</span></span>

- <span data-ttu-id="3d9aa-p125">前に説明すると、アイテムからサードパーティ製のデータ ソースは、電子メール メッセージとして Exchange のメールボックスにインポートされます。パートナーのコネクタでは、Office 365 の API に必要なスキーマを使用してアイテムをインポートします。次の表は、電子メール メッセージとして Exchange メールボックスにインポートした後、サード ・ パーティ製のデータ ソースからのアイテムのメッセージのプロパティを説明します。メッセージ プロパティは必須だかどうかも示します。必須プロパティを設定する必要があります。アイテムには、必須プロパティが不足しているが場合、は、Office 365 にインポートされません。インポート プロセスでは、項目がインポートされなかった理由と、どのプロパティが不足しているを説明するエラー メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p125">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages. The partner connector imports the item using a schema required by the Office 365 API. The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message. The table also indicates if the message property is mandatory. Mandatory properties must be populated. If an item is missing a mandatory property, it won't be imported to Office 365. The import process will return an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="3d9aa-416">**メッセージのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="3d9aa-416">**Message property**</span></span>|<span data-ttu-id="3d9aa-417">**必須ですか。**</span><span class="sxs-lookup"><span data-stu-id="3d9aa-417">**Mandatory?**</span></span>|<span data-ttu-id="3d9aa-418">**説明**</span><span class="sxs-lookup"><span data-stu-id="3d9aa-418">**Description**</span></span>|<span data-ttu-id="3d9aa-419">**値の例**</span><span class="sxs-lookup"><span data-stu-id="3d9aa-419">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3d9aa-420">**FROM**</span><span class="sxs-lookup"><span data-stu-id="3d9aa-420">**FROM**</span></span> <br/> |<span data-ttu-id="3d9aa-421">はい</span><span class="sxs-lookup"><span data-stu-id="3d9aa-421">Yes</span></span>  <br/> |<span data-ttu-id="3d9aa-p126">最初に作成またはサードパーティのデータ ソースのアイテムを送信したユーザー。パートナーのコネクタはすべての参加者 (FROM および TO フィールド内のユーザー) のソースの項目 (たとえば、Twitter のハンドル) から Office 365 のユーザー アカウントにユーザー ID をマップしようとします。メッセージのコピーは、すべての参加者のメールボックスにインポートされます。アイテムから参加者をマップするには Office 365 のユーザー アカウントに、Office 365 のサード ・ パーティ製アーカイブ メールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p126">The user who originally created or sent the item in the third-party data source. The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields). A copy of the message will be imported to the mailbox of every participant. If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.  </span></span><br/> <br/> <span data-ttu-id="3d9aa-p127">アイテムの送信者として識別される参加者は、アクティブなメールボックスにインポートされているアイテムを Office 365 の組織で必要があります。送信者には、アクティブなメールボックスが割り当てられていない、次のエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p127">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to. If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="3d9aa-428">**TO**</span><span class="sxs-lookup"><span data-stu-id="3d9aa-428">**TO**</span></span> <br/> |<span data-ttu-id="3d9aa-429">はい</span><span class="sxs-lookup"><span data-stu-id="3d9aa-429">Yes</span></span>  <br/> |<span data-ttu-id="3d9aa-430">アイテムを受信したユーザー (データ ソース内のアイテムに該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-430">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="3d9aa-431">**SUBJECT**</span><span class="sxs-lookup"><span data-stu-id="3d9aa-431">**SUBJECT**</span></span> <br/> |<span data-ttu-id="3d9aa-432">いいえ</span><span class="sxs-lookup"><span data-stu-id="3d9aa-432">No</span></span>  <br/> |<span data-ttu-id="3d9aa-433">ソース アイテムの件名。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-433">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="3d9aa-434">**日付**</span><span class="sxs-lookup"><span data-stu-id="3d9aa-434">**DATE**</span></span> <br/> |<span data-ttu-id="3d9aa-435">はい</span><span class="sxs-lookup"><span data-stu-id="3d9aa-435">Yes</span></span>  <br/> |<span data-ttu-id="3d9aa-436">アイテムが最初に作成されたか、または顧客データ ソースに投稿された日付 (たとえば、Twitter のメッセージがツイートされた日付)。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-436">The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="3d9aa-437">**BODY**</span><span class="sxs-lookup"><span data-stu-id="3d9aa-437">**BODY**</span></span> <br/> |<span data-ttu-id="3d9aa-438">いいえ</span><span class="sxs-lookup"><span data-stu-id="3d9aa-438">No</span></span>  <br/> |<span data-ttu-id="3d9aa-p128">メッセージまたは投稿の内容です。一部のデータ ソースでは、このプロパティの内容が **[主題**] プロパティの内容と同じで可能性があります。インポート プロセス中にパートナーのコネクタからコンテンツのソースにできるだけ忠実に維持するために試みます。可能であればファイル、グラフィック、または他のコンテンツ ソース アイテムの本文からは、このプロパティに含まれます。それ以外の場合、**添付ファイル**のプロパティの元の項目のコンテンツが含まれます。このプロパティの内容は、パートナーのコネクタで、ソース ・ プラットフォームの機能に依存します。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p128">The contents of the message or post. For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property. During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible. If possible files, graphics, or other content from the body of the source item is included in this property. Otherwise, content from the source item is included in the **ATTACHMENT** property. The contents of this property will depend on the partner connector and on the capability of the source platform.  </span></span><br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="3d9aa-445">**ATTACHMENT**</span><span class="sxs-lookup"><span data-stu-id="3d9aa-445">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="3d9aa-446">いいえ</span><span class="sxs-lookup"><span data-stu-id="3d9aa-446">No</span></span>  <br/> |<span data-ttu-id="3d9aa-p129">Twitter やインスタント メッセージ会話でのツイート) などのデータ ソース内の項目の添付ファイルやイメージなどがあります、パートナーは、 **BODY**プロパティに添付ファイルを含めるには最初の試行を接続します。可能ではない場合に追加される、* * 添付 * * プロパティです。添付ファイルの他の例には、Facebook、コンテンツ ソースは、メッセージまたは投稿への応答からのメタデータの中になが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p129">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property. If that isn't possible, then it's added to the ** ATTACHMENT ** property. Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.  </span></span><br/> | `image.gif` <br/> |
    |<span data-ttu-id="3d9aa-450">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="3d9aa-450">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="3d9aa-451">はい</span><span class="sxs-lookup"><span data-stu-id="3d9aa-451">Yes</span></span>  <br/> | <span data-ttu-id="3d9aa-p130">これは、複数値プロパティが作成され、パートナーのコネクタによって作成されます。このプロパティの形式は、 `IPM.NOTE.Source.Event`。(このプロパティで始まる必要があります`IPM.NOTE`はこの形式はのような`IPM.NOTE.X`メッセージ クラス)。このプロパティには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p130">This is a multi-value property, which is created and populated by partner connector. The format of this property is  `IPM.NOTE.Source.Event`. (This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:  </span></span><br/><br/><span data-ttu-id="3d9aa-455">`Source`-サード ・ パーティ製のデータ ソースを指定します。たとえば、Twitter、Facebook、または BlackBerry にします。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-455">`Source` - Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="3d9aa-p131">`Event`-の項目を生成するサードパーティのデータ ソースで実行されたアクティビティの種類を指定します。たとえば、つぶやき Twitter または Facebook の投稿にします。イベントは、データ ソースに固有です。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p131">`Event` - Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook. Events are specific to the data source.  </span></span><br/> <br/>  <span data-ttu-id="3d9aa-p132">このプロパティの目的の 1 つは、アイテムが作成されたか、イベントの種類に基づいて、データ ソースに基づく特定のアイテムをフィルターするのには。たとえば、電子的証拠開示検索の [特定のユーザーによってアップロードされたすべての tweets を検索する検索クエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p132">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event. For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.  </span></span><br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="3d9aa-p133">アイテムは、Office 365 のメールボックスに正常にインポートは、HTTP 応答の一部として呼び出し元に一意の識別子が返されます。この識別子などと呼ばれる`x-IngestionCorrelationID`: 項目のエンド ・ ツー ・ エンドの追跡のためのパートナーがそれ以降のトラブルシューティングの際に使用できます。パートナーがこの情報をキャプチャし、それに応じてそれをログに記録をお勧めしますが、最後にします。この識別子を示す HTTP 応答の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p133">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response. This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items. It's recommended that partners capture this information and log it accordingly at their end. Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="3d9aa-p134">Office 365 のセキュリティ コンテンツの検索ツールを使用することができます&amp;コンプライアンス センターをサード ・ パーティ製のデータ ソースから Office 365 のメールボックスにインポートされたアイテムを検索します。具体的には、これらのインポートされたアイテムを検索するには、コンテンツ検索のキーワード] ボックスで次のメッセージ プロパティと値のペアを使用できます。.</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p134">You can use the Content Search tool in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search. .</span></span> 
    
  - <span data-ttu-id="3d9aa-p135">**`kind:externaldata`**-すべてのサード ・ パーティ製データ型を検索するのには、このプロパティと値のペアを使用します。たとえば、インポートされたアイテムの Subject プロパティで"contoso"という単語が含まれているサード パーティのデータ ソースからインポートされたアイテムを検索するにはクエリを使用するキーワード`kind:externaldata AND subject:contoso`。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p135">**`kind:externaldata`** - Use this property-value pair to search all third-party data types. For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="3d9aa-p136">**`itemclass:ipm.externaldata.<third-party data type>`**-サード ・ パーティ製のデータを指定する型の検索のみにこのプロパティと値のペアを使用します。たとえば、のみ [件名] プロパティには、"contoso"という単語を含む Facebook のデータを検索するにはクエリを使用するキーワード`itemclass:ipm.externaldata.Facebook* AND subject:contoso`。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-p136">**`itemclass:ipm.externaldata.<third-party data type>`** - Use this property-value pair to only search a specify type of third-party data. For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="3d9aa-471">サード ・ パーティ製のデータ型に使用する値の完全な一覧については、`itemclass`プロパティでは、 [Office 365 にインポートされたサード ・ パーティ製のデータを検索するコンテンツの検索の使用](use-content-search-to-search-third-party-data-that-was-imported.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-471">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="3d9aa-472">コンテンツ検索の使用方法とキーワード検索クエリの作成方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d9aa-472">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="3d9aa-473">Office 365 でのコンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="3d9aa-473">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="3d9aa-474">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="3d9aa-474">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
