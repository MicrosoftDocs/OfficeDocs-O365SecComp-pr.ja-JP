---
title: パートナーと連携して、Office 365 でサードパーティのデータをアーカイブする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 組織は Microsoft パートナーと協力して、Salesforce チャター、Yahoo Messenger、Yammer などのデータソースからサードパーティのデータをインポートするカスタムコネクタを設定できます。 これにより、Office 365 でサードパーティのデータソースからデータをアーカイブできるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどの Office 365 コンプライアンス機能を使用して、組織のサードパーティデータのガバナンスを管理できます。
ms.openlocfilehash: 9bc8dddfed4b9721237f06ecf03c1ca41df091d6
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155999"
---
# <a name="work-with-a-partner-to-archive-third-party-data-in-office-365"></a><span data-ttu-id="a3683-104">パートナーと連携して、Office 365 でサードパーティのデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="a3683-104">Work with a partner to archive third-party data in Office 365</span></span>

<span data-ttu-id="a3683-105">Microsoft パートナーと協力して、サードパーティのデータソースから Office 365 にデータをインポートしてアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="a3683-105">You can work with a Microsoft Partner to import and archive data from a third-party data source to Office 365.</span></span> <span data-ttu-id="a3683-106">パートナーは、サードパーティのデータソースからアイテムを抽出するように構成されたカスタムコネクタ (定期的に) を提供して、それらのアイテムを Office 365 にインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="a3683-106">A partner can provide you with an custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items to Office 365.</span></span> <span data-ttu-id="a3683-107">パートナーコネクタは、アイテムのコンテンツをデータソースから電子メールメッセージ形式に変換してから、Office 365 のメールボックスにアイテムを保存します。</span><span class="sxs-lookup"><span data-stu-id="a3683-107">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes in Office 365.</span></span> <span data-ttu-id="a3683-108">サードパーティのデータをインポートした後は、このデータに、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、および Office 365 アイテム保持ポリシーなどの Office 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="a3683-108">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data.</span></span>
  
<span data-ttu-id="a3683-109">ここでは、サードパーティのデータを Office 365 にインポートするために Microsoft パートナーと連携するために必要なプロセスと手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="a3683-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data to Office 365.</span></span>

[<span data-ttu-id="a3683-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="a3683-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="a3683-111">Step 2: Create and configure a third-party data mailbox in Office 365</span><span class="sxs-lookup"><span data-stu-id="a3683-111">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="a3683-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="a3683-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="a3683-113">手順 4: パートナーに情報を提供する</span><span class="sxs-lookup"><span data-stu-id="a3683-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="a3683-114">手順 5: Azure Active Directory にサードパーティのデータコネクタを登録する</span><span class="sxs-lookup"><span data-stu-id="a3683-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="a3683-115">サードパーティのデータのインポート プロセスが実行される方法</span><span class="sxs-lookup"><span data-stu-id="a3683-115">How the third-party data import process works</span></span>

<span data-ttu-id="a3683-116">次の図と説明は、パートナーと連携している場合にサードパーティのデータインポートプロセスがどのように動作するかを説明します。</span><span class="sxs-lookup"><span data-stu-id="a3683-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![サードパーティのデータのインポート プロセスが実行される方法](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="a3683-118">お客様は、選択したパートナーと連携して、サードパーティのデータソースからアイテムを抽出し、それらのアイテムを Office 365 にインポートするコネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="a3683-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="a3683-119">パートナーコネクタは、サードパーティの API を使用してサードパーティのデータソースに接続し (スケジュールに従って、または構成されている場合)、データソースからアイテムを抽出します。</span><span class="sxs-lookup"><span data-stu-id="a3683-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="a3683-120">パートナー コネクタは、アイテムのコンテンツを電子メール メッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="a3683-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="a3683-121">メッセージ形式スキーマの説明については、「[More information](#more-information)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3683-121">See the [More information](#more-information) section for a description of the message format schema.</span></span> 
    
3. <span data-ttu-id="a3683-122">パートナーコネクタは、既知のエンドポイントを介して Exchange Web サービス (EWS) を使用して、Office 365 の Azure サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="a3683-122">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="a3683-p104">アイテムは特定のユーザーのメールボックスまたは "catch-all" というサードパーティ データのメールボックスにインポートされます。アイテムが特定のユーザーのメールボックスにインポートされるか、またはサードパーティ データのメールボックスにインポートされるかは、以下の条件に基づきます。</span><span class="sxs-lookup"><span data-stu-id="a3683-p104">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="a3683-125">a.</span><span class="sxs-lookup"><span data-stu-id="a3683-125">a.</span></span> <span data-ttu-id="a3683-126">**Office 365 ユーザーアカウントに対応するユーザー id を持つアイテム**。パートナーコネクタがサードパーティデータソース内のアイテムのユーザー Id を office 365 の特定のユーザー id にマップできる場合、そのアイテムはユーザーのレコードの [削除] \*\*\*\* フォルダーにコピーされます。overable アイテムフォルダー。</span><span class="sxs-lookup"><span data-stu-id="a3683-126">**Items that have a user ID that corresponds to an Office 365 user account** - If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="a3683-127">ユーザーがパージフォルダー内のアイテムにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="a3683-127">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="a3683-128">ただし、Office 365 電子情報開示ツールを使用して、[削除] フォルダー内のアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="a3683-128">However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="a3683-129">b.</span><span class="sxs-lookup"><span data-stu-id="a3683-129">b.</span></span> <span data-ttu-id="a3683-130">**Office 365 ユーザーアカウントに対応するユーザー id を持たないアイテム**。パートナーコネクタがアイテムのユーザー Id を office 365 の特定のユーザー id にマップできない場合、そのアイテムはサードパーティデータメールボックスの**受信トレイ**フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="a3683-130">**Items that don't have a user ID that corresponds to an Office 365 user account** - If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="a3683-131">受信トレイにアイテムをインポートすると、組織内のユーザーがサードパーティのメールボックスにサインインしてこれらのアイテムを表示および管理できるようになります。また、パートナーコネクタ構成で調整が必要かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3683-131">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="a3683-132">手順 1: サード パーティのデータのパートナーを見つける</span><span class="sxs-lookup"><span data-stu-id="a3683-132">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="a3683-133">Office 365 でサードパーティのデータをアーカイブするための主要なコンポーネントは、サードパーティのデータソースからデータを取得して Office 365 にインポートすることに特化した Microsoft パートナーを検索して作業することです。</span><span class="sxs-lookup"><span data-stu-id="a3683-133">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="a3683-134">インポートされたデータは、組織の他の Microsoft データ (Exchange からの電子メールや SharePoint および OneDrive for business からのメールなど) と共にアーカイブおよび保存することができます。</span><span class="sxs-lookup"><span data-stu-id="a3683-134">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="a3683-135">パートナーは、組織のサードパーティのデータソース (BlackBerry、Facebook、Google +、Thomson Reuters、Twitter、YouTube など) からデータを抽出し、そのデータを、Exchange メールボックスにアイテムをインポートする Office 365 API に渡すコネクタを作成します。電子メールメッセージ。</span><span class="sxs-lookup"><span data-stu-id="a3683-135">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="a3683-136">次のセクションでは、Office 365 でサードパーティのデータをアーカイブするためのプログラムに参加している Microsoft パートナーと、そのパートナーがサポートするサードパーティのデータソースを示します。</span><span class="sxs-lookup"><span data-stu-id="a3683-136">The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="a3683-137">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="a3683-137">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="a3683-138">Actiance</span><span class="sxs-lookup"><span data-stu-id="a3683-138">Actiance</span></span>](#actiance)
  
[<span data-ttu-id="a3683-139">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="a3683-139">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="a3683-140">Globanet</span><span class="sxs-lookup"><span data-stu-id="a3683-140">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="a3683-141">OpenText</span><span class="sxs-lookup"><span data-stu-id="a3683-141">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="a3683-142">Verba</span><span class="sxs-lookup"><span data-stu-id="a3683-142">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="a3683-143">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="a3683-143">17a-4 LLC</span></span>

<span data-ttu-id="a3683-144">17a-4 LLC は、次のサードパーティ データ ソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a3683-144">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="a3683-145">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="a3683-145">BlackBerry</span></span>
    
- <span data-ttu-id="a3683-146">Bloomberg データ ストリーム</span><span class="sxs-lookup"><span data-stu-id="a3683-146">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="a3683-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="a3683-147">Cisco Jabber</span></span>
    
- <span data-ttu-id="a3683-148">FactSet</span><span class="sxs-lookup"><span data-stu-id="a3683-148">FactSet</span></span>
    
- <span data-ttu-id="a3683-149">HipChat</span><span class="sxs-lookup"><span data-stu-id="a3683-149">HipChat</span></span>
    
- <span data-ttu-id="a3683-150">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="a3683-150">InvestEdge</span></span>
    
- <span data-ttu-id="a3683-151">LivePerson</span><span class="sxs-lookup"><span data-stu-id="a3683-151">LivePerson</span></span>
    
- <span data-ttu-id="a3683-152">MessageLabs データ ストリーム</span><span class="sxs-lookup"><span data-stu-id="a3683-152">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="a3683-153">OpenText</span><span class="sxs-lookup"><span data-stu-id="a3683-153">OpenText</span></span>
    
- <span data-ttu-id="a3683-154">Oracle/ATG 'click-to-call' Live ヘルプ</span><span class="sxs-lookup"><span data-stu-id="a3683-154">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="a3683-155">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="a3683-155">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="a3683-156">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="a3683-156">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="a3683-157">MindAlign</span><span class="sxs-lookup"><span data-stu-id="a3683-157">MindAlign</span></span>
    
- <span data-ttu-id="a3683-158">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="a3683-158">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="a3683-159">Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="a3683-159">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="a3683-160">Skype for Business Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="a3683-160">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="a3683-161">SQL データベース</span><span class="sxs-lookup"><span data-stu-id="a3683-161">SQL Databases</span></span>
    
- <span data-ttu-id="a3683-162">Squawker</span><span class="sxs-lookup"><span data-stu-id="a3683-162">Squawker</span></span>
    
- <span data-ttu-id="a3683-163">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="a3683-163">Thomson Reuters Eikon Messenger</span></span>
  
### <a name="actiance"></a><span data-ttu-id="a3683-164">Actiance</span><span class="sxs-lookup"><span data-stu-id="a3683-164">Actiance</span></span>

<span data-ttu-id="a3683-165">[Actiance](https://www.actiance.com)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a3683-165">[Actiance](https://www.actiance.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a3683-166">目的</span><span class="sxs-lookup"><span data-stu-id="a3683-166">AIM</span></span>
    
- <span data-ttu-id="a3683-167">American Idol</span><span class="sxs-lookup"><span data-stu-id="a3683-167">American Idol</span></span>
    
- <span data-ttu-id="a3683-168">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="a3683-168">Apple Juice</span></span>
    
- <span data-ttu-id="a3683-169">AOL with Pivot クライアント</span><span class="sxs-lookup"><span data-stu-id="a3683-169">AOL with Pivot client</span></span>
    
- <span data-ttu-id="a3683-170">アレス</span><span class="sxs-lookup"><span data-stu-id="a3683-170">Ares</span></span>
    
- <span data-ttu-id="a3683-171">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="a3683-171">Bazaar Voice</span></span>
    
- <span data-ttu-id="a3683-172">Bearshare</span><span class="sxs-lookup"><span data-stu-id="a3683-172">Bear Share</span></span>
    
- <span data-ttu-id="a3683-173">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="a3683-173">Bit Torrent</span></span>
    
- <span data-ttu-id="a3683-174">BlackBerry 呼び出しログ (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="a3683-174">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a3683-175">BlackBerry メッセンジャー (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="a3683-175">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a3683-176">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="a3683-176">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a3683-177">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="a3683-177">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a3683-178">Bloomberg メール</span><span class="sxs-lookup"><span data-stu-id="a3683-178">Bloomberg Mail</span></span>
    
- <span data-ttu-id="a3683-179">CellTrust</span><span class="sxs-lookup"><span data-stu-id="a3683-179">CellTrust</span></span>
    
- <span data-ttu-id="a3683-180">チャットのインポート</span><span class="sxs-lookup"><span data-stu-id="a3683-180">Chat Import</span></span>
    
- <span data-ttu-id="a3683-181">チャットのリアルタイム ロギングとポリシー</span><span class="sxs-lookup"><span data-stu-id="a3683-181">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="a3683-182">チャター</span><span class="sxs-lookup"><span data-stu-id="a3683-182">Chatter</span></span>
    
- <span data-ttu-id="a3683-183">Cisco IM &amp;プレゼンスサーバー (v 9.0.1、v 9.1、v 9.1.1 SU1、v10、v v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="a3683-183">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="a3683-184">Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="a3683-184">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="a3683-185">共同作業のインポート</span><span class="sxs-lookup"><span data-stu-id="a3683-185">Collaboration Import</span></span>
    
- <span data-ttu-id="a3683-186">共同作業のリアルタイム ロギング</span><span class="sxs-lookup"><span data-stu-id="a3683-186">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="a3683-187">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="a3683-187">Direct Connect</span></span>
    
- <span data-ttu-id="a3683-188">Facebook</span><span class="sxs-lookup"><span data-stu-id="a3683-188">Facebook</span></span>
    
- <span data-ttu-id="a3683-189">FactSet</span><span class="sxs-lookup"><span data-stu-id="a3683-189">FactSet</span></span>
    
- <span data-ttu-id="a3683-190">FastTrack</span><span class="sxs-lookup"><span data-stu-id="a3683-190">FastTrack</span></span>
    
- <span data-ttu-id="a3683-191">Gnutella</span><span class="sxs-lookup"><span data-stu-id="a3683-191">Gnutella</span></span>
    
- <span data-ttu-id="a3683-192">Google +</span><span class="sxs-lookup"><span data-stu-id="a3683-192">Google+</span></span>
    
- <span data-ttu-id="a3683-193">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="a3683-193">GoToMyPC</span></span>
    
- <span data-ttu-id="a3683-194">Hopster</span><span class="sxs-lookup"><span data-stu-id="a3683-194">Hopster</span></span>
    
- <span data-ttu-id="a3683-195">HubConnex</span><span class="sxs-lookup"><span data-stu-id="a3683-195">HubConnex</span></span>
    
- <span data-ttu-id="a3683-196">IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)</span><span class="sxs-lookup"><span data-stu-id="a3683-196">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="a3683-197">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="a3683-197">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="a3683-198">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="a3683-198">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="a3683-199">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="a3683-199">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="a3683-200">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="a3683-200">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="a3683-201">IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)</span><span class="sxs-lookup"><span data-stu-id="a3683-201">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="a3683-202">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="a3683-202">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="a3683-203">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="a3683-203">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="a3683-204">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="a3683-204">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="a3683-205">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="a3683-205">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="a3683-206">IM のインポート</span><span class="sxs-lookup"><span data-stu-id="a3683-206">IM Import</span></span>
    
- <span data-ttu-id="a3683-207">IM のリアルタイム ロギングとポリシー</span><span class="sxs-lookup"><span data-stu-id="a3683-207">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="a3683-208">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="a3683-208">Indii Messenger</span></span>
    
- <span data-ttu-id="a3683-209">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a3683-209">Instant Bloomberg</span></span>
    
- <span data-ttu-id="a3683-210">IRC</span><span class="sxs-lookup"><span data-stu-id="a3683-210">IRC</span></span>
    
- <span data-ttu-id="a3683-211">Jive</span><span class="sxs-lookup"><span data-stu-id="a3683-211">Jive</span></span>
    
- <span data-ttu-id="a3683-212">Jive 6 Real Time Logging (v6、v7)</span><span class="sxs-lookup"><span data-stu-id="a3683-212">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="a3683-213">Jive のインポート</span><span class="sxs-lookup"><span data-stu-id="a3683-213">Jive Import</span></span>
    
- <span data-ttu-id="a3683-214">JXTA</span><span class="sxs-lookup"><span data-stu-id="a3683-214">JXTA</span></span>
    
- <span data-ttu-id="a3683-215">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="a3683-215">LinkedIn</span></span>
    
- <span data-ttu-id="a3683-216">Microsoft Lync (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="a3683-216">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="a3683-217">MFTP</span><span class="sxs-lookup"><span data-stu-id="a3683-217">MFTP</span></span>
    
- <span data-ttu-id="a3683-218">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="a3683-218">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="a3683-219">Microsoft SharePoint (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="a3683-219">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="a3683-220">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3683-220">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="a3683-221">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="a3683-221">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="a3683-222">MindAlign</span><span class="sxs-lookup"><span data-stu-id="a3683-222">MindAlign</span></span>
    
- <span data-ttu-id="a3683-223">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="a3683-223">Mobile Guard</span></span>
    
- <span data-ttu-id="a3683-224">ウェブ</span><span class="sxs-lookup"><span data-stu-id="a3683-224">MSN</span></span>
    
- <span data-ttu-id="a3683-225">My Space</span><span class="sxs-lookup"><span data-stu-id="a3683-225">My Space</span></span>
    
- <span data-ttu-id="a3683-226">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="a3683-226">NEONetwork</span></span>
    
- <span data-ttu-id="a3683-227">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="a3683-227">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="a3683-228">Office 365 Shared IM</span><span class="sxs-lookup"><span data-stu-id="a3683-228">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="a3683-229">Pinterest</span><span class="sxs-lookup"><span data-stu-id="a3683-229">Pinterest</span></span>
    
- <span data-ttu-id="a3683-230">ピボット</span><span class="sxs-lookup"><span data-stu-id="a3683-230">Pivot</span></span>
    
- <span data-ttu-id="a3683-231">QQ</span><span class="sxs-lookup"><span data-stu-id="a3683-231">QQ</span></span>
    
- <span data-ttu-id="a3683-232">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="a3683-232">Skype for Business 2015</span></span>
    
- <span data-ttu-id="a3683-233">SoftEther</span><span class="sxs-lookup"><span data-stu-id="a3683-233">SoftEther</span></span>
    
- <span data-ttu-id="a3683-234">Symphony</span><span class="sxs-lookup"><span data-stu-id="a3683-234">Symphony</span></span>
    
- <span data-ttu-id="a3683-235">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="a3683-235">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="a3683-236">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="a3683-236">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="a3683-237">終わり</span><span class="sxs-lookup"><span data-stu-id="a3683-237">Tor</span></span>
    
- <span data-ttu-id="a3683-238">TTT</span><span class="sxs-lookup"><span data-stu-id="a3683-238">TTT</span></span>
    
- <span data-ttu-id="a3683-239">Twitter</span><span class="sxs-lookup"><span data-stu-id="a3683-239">Twitter</span></span>
    
- <span data-ttu-id="a3683-240">WinMX</span><span class="sxs-lookup"><span data-stu-id="a3683-240">WinMX</span></span>
    
- <span data-ttu-id="a3683-241">Winny</span><span class="sxs-lookup"><span data-stu-id="a3683-241">Winny</span></span>
    
- <span data-ttu-id="a3683-242">Yahoo</span><span class="sxs-lookup"><span data-stu-id="a3683-242">Yahoo</span></span>
    
- <span data-ttu-id="a3683-243">Yammer</span><span class="sxs-lookup"><span data-stu-id="a3683-243">Yammer</span></span>
    
- <span data-ttu-id="a3683-244">YouTube</span><span class="sxs-lookup"><span data-stu-id="a3683-244">YouTube</span></span>
    
  
### <a name="archivesocial"></a><span data-ttu-id="a3683-245">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="a3683-245">ArchiveSocial</span></span>

<span data-ttu-id="a3683-246">[ArchiveSocial](https://www.archivesocial.com)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a3683-246">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a3683-247">Facebook</span><span class="sxs-lookup"><span data-stu-id="a3683-247">Facebook</span></span>
    
- <span data-ttu-id="a3683-248">Flickr</span><span class="sxs-lookup"><span data-stu-id="a3683-248">Flickr</span></span>
    
- <span data-ttu-id="a3683-249">Instagram</span><span class="sxs-lookup"><span data-stu-id="a3683-249">Instagram</span></span>
    
- <span data-ttu-id="a3683-250">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="a3683-250">LinkedIn</span></span>
    
- <span data-ttu-id="a3683-251">Pinterest</span><span class="sxs-lookup"><span data-stu-id="a3683-251">Pinterest</span></span>
    
- <span data-ttu-id="a3683-252">Twitter</span><span class="sxs-lookup"><span data-stu-id="a3683-252">Twitter</span></span>
    
- <span data-ttu-id="a3683-253">YouTube</span><span class="sxs-lookup"><span data-stu-id="a3683-253">YouTube</span></span>
    
- <span data-ttu-id="a3683-254">Vimeo</span><span class="sxs-lookup"><span data-stu-id="a3683-254">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="a3683-255">Globanet</span><span class="sxs-lookup"><span data-stu-id="a3683-255">Globanet</span></span>

<span data-ttu-id="a3683-256">[Globanet](https://www.globanet.com)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a3683-256">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a3683-257">AOL with Pivot クライアント</span><span class="sxs-lookup"><span data-stu-id="a3683-257">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="a3683-258">BlackBerry 呼び出しログ (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="a3683-258">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a3683-259">BlackBerry メッセンジャー (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="a3683-259">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a3683-260">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="a3683-260">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a3683-261">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="a3683-261">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="a3683-262">Bloomberg チャット</span><span class="sxs-lookup"><span data-stu-id="a3683-262">Bloomberg Chat</span></span>
    
- <span data-ttu-id="a3683-263">Bloomberg メール</span><span class="sxs-lookup"><span data-stu-id="a3683-263">Bloomberg Mail</span></span>
    
- <span data-ttu-id="a3683-264">検索ボックス</span><span class="sxs-lookup"><span data-stu-id="a3683-264">Box</span></span>
    
- <span data-ttu-id="a3683-265">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="a3683-265">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="a3683-266">Cisco IM &amp;プレゼンスサーバー (v10、v v10.5.1 SU1、v 11.0、v 11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="a3683-266">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="a3683-267">Cisco Webex Teams</span><span class="sxs-lookup"><span data-stu-id="a3683-267">Cisco Webex Teams</span></span>

- <span data-ttu-id="a3683-268">Citrix ワーク&amp;スペースの編集ファイル</span><span class="sxs-lookup"><span data-stu-id="a3683-268">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="a3683-269">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="a3683-269">CrowdCompass</span></span>

- <span data-ttu-id="a3683-270">カスタムの区切り記号付きテキスト ファイル</span><span class="sxs-lookup"><span data-stu-id="a3683-270">Custom delimited text files</span></span>
    
- <span data-ttu-id="a3683-271">カスタムの XML ファイル</span><span class="sxs-lookup"><span data-stu-id="a3683-271">Custom XML files</span></span>
    
- <span data-ttu-id="a3683-272">Facebook (ページ)</span><span class="sxs-lookup"><span data-stu-id="a3683-272">Facebook (Pages)</span></span>
    
- <span data-ttu-id="a3683-273">Factset</span><span class="sxs-lookup"><span data-stu-id="a3683-273">Factset</span></span>
    
- <span data-ttu-id="a3683-274">FXConnect</span><span class="sxs-lookup"><span data-stu-id="a3683-274">FXConnect</span></span>
    
- <span data-ttu-id="a3683-275">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="a3683-275">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="a3683-276">Jive</span><span class="sxs-lookup"><span data-stu-id="a3683-276">Jive</span></span>
    
- <span data-ttu-id="a3683-277">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="a3683-277">Macgregor XIP</span></span>

- <span data-ttu-id="a3683-278">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a3683-278">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="a3683-279">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="a3683-279">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="a3683-280">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a3683-280">Microsoft Teams</span></span>
       
- <span data-ttu-id="a3683-281">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="a3683-281">Microsoft Yammer</span></span>
    
- <span data-ttu-id="a3683-282">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="a3683-282">Mobile Guard</span></span>
    
- <span data-ttu-id="a3683-283">ピボット</span><span class="sxs-lookup"><span data-stu-id="a3683-283">Pivot</span></span>
    
- <span data-ttu-id="a3683-284">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="a3683-284">Salesforce Chatter</span></span>

- <span data-ttu-id="a3683-285">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a3683-285">Skype for Business Online</span></span>
    
- <span data-ttu-id="a3683-286">Skype for Business、バージョン 2007 R2 ～ 2016 (オンプレミス)</span><span class="sxs-lookup"><span data-stu-id="a3683-286">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="a3683-287">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="a3683-287">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="a3683-288">Symphony</span><span class="sxs-lookup"><span data-stu-id="a3683-288">Symphony</span></span>
    
- <span data-ttu-id="a3683-289">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="a3683-289">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="a3683-290">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="a3683-290">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="a3683-291">Thomson Reuters Dealings 3000 / FX トレーディング</span><span class="sxs-lookup"><span data-stu-id="a3683-291">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="a3683-292">Twitter</span><span class="sxs-lookup"><span data-stu-id="a3683-292">Twitter</span></span>
    
- <span data-ttu-id="a3683-293">UBS チャット</span><span class="sxs-lookup"><span data-stu-id="a3683-293">UBS Chat</span></span>
    
- <span data-ttu-id="a3683-294">YouTube</span><span class="sxs-lookup"><span data-stu-id="a3683-294">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="a3683-295">OpenText</span><span class="sxs-lookup"><span data-stu-id="a3683-295">OpenText</span></span>

<span data-ttu-id="a3683-296">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a3683-296">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a3683-297">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="a3683-297">Axs Encrypted</span></span>
    
- <span data-ttu-id="a3683-298">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="a3683-298">Axs Exchange</span></span>
    
- <span data-ttu-id="a3683-299">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="a3683-299">Axs Local Archive</span></span>
    
- <span data-ttu-id="a3683-300">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="a3683-300">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="a3683-301">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="a3683-301">Axs Signed</span></span>
    
- <span data-ttu-id="a3683-302">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a3683-302">Bloomberg</span></span>
    
- <span data-ttu-id="a3683-303">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="a3683-303">Thomson Reuters</span></span>
  
### <a name="verba"></a><span data-ttu-id="a3683-304">Verba</span><span class="sxs-lookup"><span data-stu-id="a3683-304">Verba</span></span>

<span data-ttu-id="a3683-305">[Verba](https://www.verba.com)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a3683-305">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="a3683-306">Avaya Aura ビデオ</span><span class="sxs-lookup"><span data-stu-id="a3683-306">Avaya Aura Video</span></span>
    
- <span data-ttu-id="a3683-307">Avaya Aura 音声</span><span class="sxs-lookup"><span data-stu-id="a3683-307">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="a3683-308">Avtec ラジオ</span><span class="sxs-lookup"><span data-stu-id="a3683-308">Avtec Radio</span></span>
    
- <span data-ttu-id="a3683-309">Bosch/Telex ラジオ</span><span class="sxs-lookup"><span data-stu-id="a3683-309">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="a3683-310">BroadSoft ビデオ</span><span class="sxs-lookup"><span data-stu-id="a3683-310">BroadSoft Video</span></span>
    
- <span data-ttu-id="a3683-311">BroadSoft 音声</span><span class="sxs-lookup"><span data-stu-id="a3683-311">BroadSoft Voice</span></span>
    
- <span data-ttu-id="a3683-312">Centile 音声</span><span class="sxs-lookup"><span data-stu-id="a3683-312">Centile Voice</span></span>
    
- <span data-ttu-id="a3683-313">Cisco Jabber IM</span><span class="sxs-lookup"><span data-stu-id="a3683-313">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="a3683-314">Cisco UC ビデオ</span><span class="sxs-lookup"><span data-stu-id="a3683-314">Cisco UC Video</span></span>
    
- <span data-ttu-id="a3683-315">Cisco UC 音声</span><span class="sxs-lookup"><span data-stu-id="a3683-315">Cisco UC Voice</span></span>
    
- <span data-ttu-id="a3683-316">Cisco UCCX/UCCX ビデオ</span><span class="sxs-lookup"><span data-stu-id="a3683-316">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="a3683-317">Cisco UCCX/UCCX 音声</span><span class="sxs-lookup"><span data-stu-id="a3683-317">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="a3683-318">ESChat ラジオ</span><span class="sxs-lookup"><span data-stu-id="a3683-318">ESChat Radio</span></span>
    
- <span data-ttu-id="a3683-319">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="a3683-319">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="a3683-320">IP Trade 音声</span><span class="sxs-lookup"><span data-stu-id="a3683-320">IP Trade Voice</span></span>
    
- <span data-ttu-id="a3683-321">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="a3683-321">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="a3683-322">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="a3683-322">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="a3683-323">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="a3683-323">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="a3683-324">Oracle / Acme Packet Session Border Controller ビデオ</span><span class="sxs-lookup"><span data-stu-id="a3683-324">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="a3683-325">Oracle / Acme Packet Session Border Controller 音声</span><span class="sxs-lookup"><span data-stu-id="a3683-325">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="a3683-326">Singtel モバイル ボイス</span><span class="sxs-lookup"><span data-stu-id="a3683-326">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="a3683-327">SIPREC ビデオ</span><span class="sxs-lookup"><span data-stu-id="a3683-327">SIPREC Video</span></span>
    
-  <span data-ttu-id="a3683-328">SIPREC 音声</span><span class="sxs-lookup"><span data-stu-id="a3683-328">SIPREC Voice</span></span> 
    
- <span data-ttu-id="a3683-329">Skype for Business / Lync IM</span><span class="sxs-lookup"><span data-stu-id="a3683-329">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="a3683-330">Skype for Business / Lync ビデオ</span><span class="sxs-lookup"><span data-stu-id="a3683-330">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="a3683-331">Skype for Business / Lync 音声</span><span class="sxs-lookup"><span data-stu-id="a3683-331">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="a3683-332">Speakerbus 音声</span><span class="sxs-lookup"><span data-stu-id="a3683-332">Speakerbus Voice</span></span>
    
- <span data-ttu-id="a3683-333">標準的な SIP/H.323 ビデオ</span><span class="sxs-lookup"><span data-stu-id="a3683-333">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="a3683-334">標準的な SIP/H.323 音声</span><span class="sxs-lookup"><span data-stu-id="a3683-334">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="a3683-335">Truphone 音声</span><span class="sxs-lookup"><span data-stu-id="a3683-335">Truphone Voice</span></span>
    
- <span data-ttu-id="a3683-336">TwistedPair ラジオ</span><span class="sxs-lookup"><span data-stu-id="a3683-336">TwistedPair Radio</span></span>
    
- <span data-ttu-id="a3683-337">Windows デスクトップ コンピューターの画面</span><span class="sxs-lookup"><span data-stu-id="a3683-337">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="a3683-338">手順 2: Office 365 でサード パーティ データのメールボックスを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="a3683-338">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="a3683-339">Office 365 にデータをインポートするためにサードパーティ製のデータメールボックスを作成して構成する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a3683-339">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="a3683-340">前に説明したように、パートナーコネクタがアイテムのユーザー ID を Office 365 ユーザーアカウントにマップできない場合、アイテムはこのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="a3683-340">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="a3683-341">**Microsoft 365 管理センターでこれらのタスクを完了する**</span><span class="sxs-lookup"><span data-stu-id="a3683-341">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="a3683-342">Office 365 で新しいユーザーアカウントを作成し、Exchange Online プラン2のライセンスを割り当てます。「 [Office 365 にユーザーを追加する」を](https://go.microsoft.com/fwlink/p/?LinkId=692098)参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3683-342">Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="a3683-343">プラン2ライセンスは、メールボックスを訴訟ホールドの対象にするため、または記憶域クォータが無制限のアーカイブメールボックスを有効にするために必要です。</span><span class="sxs-lookup"><span data-stu-id="a3683-343">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="a3683-344">Office 365 で、サードパーティのデータメールボックスのユーザーアカウントを**Exchange 管理**者の役割に追加します。「 [Office 365 で管理者ロールを割り当てる」を](https://go.microsoft.com/fwlink/p/?LinkId=532393)参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3683-344">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a3683-345">このユーザー アカウントの資格情報を控えておきます。</span><span class="sxs-lookup"><span data-stu-id="a3683-345">Write down the credentials for this user account.</span></span> <span data-ttu-id="a3683-346">手順 4 で説明するように、この情報をパートナーに提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3683-346">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="a3683-347">**Exchange 管理センターでこれらのタスクを完了する**</span><span class="sxs-lookup"><span data-stu-id="a3683-347">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="a3683-348">組織内のアドレス帳およびその他のアドレス一覧から、サードパーティのデータメールボックスを非表示にします。「[ユーザーメールボックスの管理](https://go.microsoft.com/fwlink/p/?LinkId=616058)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3683-348">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="a3683-349">または、次の PowerShell コマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3683-349">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="a3683-350">サードパーティのデータメールボックスに**Fullaccess**のアクセス許可を割り当てて、管理者またはコンプライアンス責任者が Outlook デスクトップクライアントでサードパーティのデータメールボックスを開くことができるようにします。「[管理者のアクセス許可を管理する」を](https://go.microsoft.com/fwlink/p/?LinkId=692104)参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3683-350">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="a3683-351">サードパーティのデータメールボックスに対して、次のコンプライアンス関連の Office 365 機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a3683-351">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="a3683-352">アーカイブメールボックスを有効にします。「[アーカイブメールボックスを有効に](enable-archive-mailboxes.md)する」および「[無制限アーカイブを有効にする](enable-unlimited-archiving.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a3683-352">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="a3683-353">これにより、サードパーティのデータアイテムをアーカイブメールボックスに移動するアーカイブポリシーを設定することで、プライマリメールボックスの記憶域スペースを解放できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a3683-353">This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="a3683-354">これにより、サードパーティのデータに対して無制限のストレージが提供されます。</span><span class="sxs-lookup"><span data-stu-id="a3683-354">This will provide you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="a3683-355">サードパーティ データのメールボックスを訴訟ホールドの対象にします。</span><span class="sxs-lookup"><span data-stu-id="a3683-355">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="a3683-356">セキュリティ/コンプライアンスセンターで Office 365 アイテム保持ポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3683-356">You can also apply an Office 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="a3683-357">このメールボックスを保留にすると、サードパーティのデータアイテム (無期限または指定した期間中) が保持され、それらがメールボックスから削除されるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="a3683-357">Placing this mailbox on hold will retain third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="a3683-358">次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3683-358">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="a3683-359">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="a3683-359">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="a3683-360">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="a3683-360">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="a3683-361">サードパーティデータメールボックスへの所有者、代理人、および管理者のアクセスに対してメールボックス監査ログを有効にします。「 [Enable mailbox auditing In Office 365](enable-mailbox-auditing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3683-361">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="a3683-362">これにより、サードパーティのデータメールボックスにアクセスできるすべてのユーザーによって実行されたすべてのアクティビティを監査できます。</span><span class="sxs-lookup"><span data-stu-id="a3683-362">This will allow you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="a3683-363">手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="a3683-363">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="a3683-364">次の手順は、サード パーティのデータをサポートするためにユーザーのメールボックスを構成します。</span><span class="sxs-lookup"><span data-stu-id="a3683-364">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="a3683-365">Exchange 管理センターまたは対応する Windows PowerShell コマンドレットを使用して、これらのタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="a3683-365">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="a3683-366">各ユーザーのアーカイブメールボックスを有効にします。「[アーカイブメールボックスを有効に](enable-archive-mailboxes.md)する」および「[無制限アーカイブを有効にする](enable-unlimited-archiving.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a3683-366">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="a3683-367">ユーザーメールボックスを訴訟ホールドの対象にするか、Office 365 アイテム保持ポリシーを適用します。次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3683-367">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="a3683-368">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="a3683-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="a3683-369">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="a3683-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="a3683-370">前述のように、メールボックスをホールドの対象にすると、サードパーティ データ ソースからのアイテムを保持する期間を設定したり、アイテムを無期限に保持したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a3683-370">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="a3683-371">手順 4: パートナーに情報を提供する</span><span class="sxs-lookup"><span data-stu-id="a3683-371">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="a3683-372">最後の手順は、パートナーが Office 365 の組織に接続するコネクタを構成し、ユーザーのメールボックスおよびサード パーティのデータのメールボックスにデータをインポートできるように、パートナーに以下の情報を提供することです。</span><span class="sxs-lookup"><span data-stu-id="a3683-372">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="a3683-373">Office 365 の Azure サービスに接続するために使用されるエンドポイント:</span><span class="sxs-lookup"><span data-stu-id="a3683-373">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="a3683-374">手順2で作成したサードパーティ製データメールボックスのサインイン資格情報 (Office 365 ユーザー ID とパスワード)。</span><span class="sxs-lookup"><span data-stu-id="a3683-374">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="a3683-375">パートナーのコネクタがアイテムにアクセスして、アイテムをユーザーのメールボックスとサード パーティ データのメールボックスにインポートするには、これらの資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="a3683-375">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="a3683-376">手順 5: Azure Active Directory にサードパーティのデータコネクタを登録する</span><span class="sxs-lookup"><span data-stu-id="a3683-376">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="a3683-377">2018年9月30日以降、Office 365 の Azure サービスは、Exchange Online での先進認証の使用を開始して、Office 365 組織に接続してデータをインポートするサードパーティ製データコネクタを認証します。</span><span class="sxs-lookup"><span data-stu-id="a3683-377">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data.</span></span> <span data-ttu-id="a3683-378">この変更によって、モダン認証は現在のメソッドよりも高いセキュリティを提供しています。これは、以前に説明したエンドポイントを使用して Azure サービスに接続するサードパーティコネクタに基づいていました。</span><span class="sxs-lookup"><span data-stu-id="a3683-378">The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="a3683-379">新しいモダン認証方法を使用してサードパーティ製データコネクタを Office 365 に接続できるようにするには、Office 365 組織の管理者が、Azure Active Directory の信頼済みサービスアプリケーションとしてそのコネクタを登録するために同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3683-379">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="a3683-380">これを行うには、アクセス許可要求を受け入れ、コネクタが Azure Active Directory 内の組織のデータにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="a3683-380">This is done by accepting a permissions request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="a3683-381">この要求を承諾すると、サードパーティのデータコネクタがエンタープライズアプリケーションとして Azure Active Directory に追加され、サービスプリンシパルとして表されます。</span><span class="sxs-lookup"><span data-stu-id="a3683-381">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="a3683-382">同意プロセスの詳細については、「[テナント管理者の同意](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3683-382">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="a3683-383">コネクタを登録するための要求をアクセスして受け入れる手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a3683-383">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="a3683-384">[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Office 365 グローバル管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="a3683-384">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="a3683-385">次のダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3683-385">The following dialog box is displayed.</span></span> <span data-ttu-id="a3683-386">Carets を展開して、コネクタに割り当てられているアクセス許可を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a3683-386">You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/><span data-ttu-id="a3683-387">![[アクセス許可の要求] ダイアログが表示されます。](media/O365_ThirdPartyDataConnector_OptIn1.png)</span><span class="sxs-lookup"><span data-stu-id="a3683-387">![The permissions request dialog is displayed](media/O365_ThirdPartyDataConnector_OptIn1.png)</span></span>
2. <span data-ttu-id="a3683-388">[**Accept**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3683-388">Click **Accept**.</span></span>

<span data-ttu-id="a3683-389">要求を受け入れると、 [Azure portal](https://portal.azure.com)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3683-389">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="a3683-390">組織のアプリケーションの一覧を表示するには、[ **Azure Active Directory** > **エンタープライズアプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3683-390">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="a3683-391">Office 365 サードパーティデータコネクタは、**エンタープライズアプリケーション**ブレードに一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="a3683-391">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3683-392">2018年9月30日以降、サードパーティのデータコネクタを Azure Active Directory に登録しない場合、組織内のメールボックスにサードパーティのデータがインポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="a3683-392">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="a3683-393">注: 既存のサードパーティのデータコネクタ (2018 年9月30日より前に作成されたもの) は、手順5の手順に従って Azure Active Directory に登録する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="a3683-393">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="a3683-394">サードパーティのデータコネクタの同意を取り消す</span><span class="sxs-lookup"><span data-stu-id="a3683-394">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="a3683-395">組織がアクセス許可要求に同意して、Azure Active Directory にサードパーティデータコネクタを登録すると、組織はいつでもその同意を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="a3683-395">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="a3683-396">ただし、コネクタの同意を取り消すと、サードパーティのデータソースからのデータは Office 365 にインポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="a3683-396">However, revoking the consent for a connector will mean that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="a3683-397">サードパーティのデータコネクタの同意を取り消すには、Azure ポータルの [**エンタープライズアプリケーション**] ブレードまたはを使用[して、azure Active Directory からアプリケーション (対応するサービスプリンシパルを削除) を削除するか、または](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal)Office 365 PowerShell で new-msolserviceprincipal を削除します。</span><span class="sxs-lookup"><span data-stu-id="a3683-397">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="a3683-398">Azure Active Directory PowerShell で[AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal)コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3683-398">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="a3683-399">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a3683-399">More information</span></span>

- <span data-ttu-id="a3683-400">前述のように、サード パーティのデータ ソースのアイテムは、メール メッセージとして Exchange メールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="a3683-400">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="a3683-401">パートナーコネクタは、Office 365 API によって必要とされるスキーマを使用してアイテムをインポートします。</span><span class="sxs-lookup"><span data-stu-id="a3683-401">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="a3683-402">次の表では、メール メッセージとして Exchange メールボックスにインポートされた後の、サード パーティのデータ ソースのアイテムのメッセージのプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a3683-402">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="a3683-403">この表では、メッセージのプロパティが必須かどうかも示します。</span><span class="sxs-lookup"><span data-stu-id="a3683-403">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="a3683-404">必須プロパティは設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3683-404">Mandatory properties must be populated.</span></span> <span data-ttu-id="a3683-405">必須のプロパティが設定されていないアイテムは、Office 365 にインポートされません。</span><span class="sxs-lookup"><span data-stu-id="a3683-405">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="a3683-406">インポート プロセスによって、アイテムがインポートされなかった理由と、どのプロパティが欠落しているのかを記したエラー メッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="a3683-406">The import process will return an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="a3683-407">**メッセージのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="a3683-407">**Message property**</span></span>|<span data-ttu-id="a3683-408">**必須かどうか?**</span><span class="sxs-lookup"><span data-stu-id="a3683-408">**Mandatory?**</span></span>|<span data-ttu-id="a3683-409">**説明**</span><span class="sxs-lookup"><span data-stu-id="a3683-409">**Description**</span></span>|<span data-ttu-id="a3683-410">**値の例**</span><span class="sxs-lookup"><span data-stu-id="a3683-410">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a3683-411">**FROM**</span><span class="sxs-lookup"><span data-stu-id="a3683-411">**FROM**</span></span> <br/> |<span data-ttu-id="a3683-412">はい</span><span class="sxs-lookup"><span data-stu-id="a3683-412">Yes</span></span>  <br/> |<span data-ttu-id="a3683-413">最初にサード パーティのデータ ソース内のアイテムを作成または送信したユーザー。</span><span class="sxs-lookup"><span data-stu-id="a3683-413">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="a3683-414">パートナーコネクタは、ソースアイテム (Twitter ハンドルなど) から、すべての参加者 ([差出人] および [宛先] フィールド内のユーザー) の Office 365 ユーザーアカウントにユーザー ID をマップしようとします。</span><span class="sxs-lookup"><span data-stu-id="a3683-414">The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="a3683-415">メッセージのコピーが、すべての参加者のメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="a3683-415">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="a3683-416">そのアイテムの参加者が Office 365 ユーザーアカウントにマップできない場合、そのアイテムは Office 365 のサードパーティのアーカイブメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="a3683-416">If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="a3683-417">アイテムの送信者として識別される参加者は、アイテムがインポートされる Office 365 組織にアクティブなメールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3683-417">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to.</span></span> <span data-ttu-id="a3683-418">送信者がアクティブなメールボックスを持っていない場合は、次のエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="a3683-418">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="a3683-419">**TO**</span><span class="sxs-lookup"><span data-stu-id="a3683-419">**TO**</span></span> <br/> |<span data-ttu-id="a3683-420">はい</span><span class="sxs-lookup"><span data-stu-id="a3683-420">Yes</span></span>  <br/> |<span data-ttu-id="a3683-421">アイテムを受信したユーザー (データ ソース内のアイテムに該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="a3683-421">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="a3683-422">**件名**</span><span class="sxs-lookup"><span data-stu-id="a3683-422">**SUBJECT**</span></span> <br/> |<span data-ttu-id="a3683-423">いいえ</span><span class="sxs-lookup"><span data-stu-id="a3683-423">No</span></span>  <br/> |<span data-ttu-id="a3683-424">ソース アイテムの件名。</span><span class="sxs-lookup"><span data-stu-id="a3683-424">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="a3683-425">**DATE**</span><span class="sxs-lookup"><span data-stu-id="a3683-425">**DATE**</span></span> <br/> |<span data-ttu-id="a3683-426">はい</span><span class="sxs-lookup"><span data-stu-id="a3683-426">Yes</span></span>  <br/> |<span data-ttu-id="a3683-427">アイテムが最初に作成されたか、または顧客データ ソースに投稿された日付 (たとえば、Twitter のメッセージがツイートされた日付)。</span><span class="sxs-lookup"><span data-stu-id="a3683-427">The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="a3683-428">**物体**</span><span class="sxs-lookup"><span data-stu-id="a3683-428">**BODY**</span></span> <br/> |<span data-ttu-id="a3683-429">いいえ</span><span class="sxs-lookup"><span data-stu-id="a3683-429">No</span></span>  <br/> |<span data-ttu-id="a3683-430">メッセージまたは投稿のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="a3683-430">The contents of the message or post.</span></span> <span data-ttu-id="a3683-431">一部のデータ ソースでは、このプロパティのコンテンツは **SUBJECT** プロパティのコンテンツと同じになります。</span><span class="sxs-lookup"><span data-stu-id="a3683-431">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="a3683-432">インポート プロセス時に、パートナー コネクタは、できるだけコンテンツ ソースからの完全な再現性を維持しようとします。</span><span class="sxs-lookup"><span data-stu-id="a3683-432">During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="a3683-433">可能な場合には、ソース アイテムの本文からのファイル、グラフィック、またはその他のコンテンツが、このプロパティに含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3683-433">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="a3683-434">それ以外の場合、ソース アイテムからのコンテンツは **ATTACHMENT** プロパティに含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3683-434">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="a3683-435">このプロパティの内容は、パートナーコネクタとソースプラットフォームの機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a3683-435">The contents of this property will depend on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="a3683-436">**資料**</span><span class="sxs-lookup"><span data-stu-id="a3683-436">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="a3683-437">いいえ</span><span class="sxs-lookup"><span data-stu-id="a3683-437">No</span></span>  <br/> |<span data-ttu-id="a3683-438">データソース内のアイテム (Twitter のツイート、インスタントメッセージングの会話など) に添付ファイルがあり、画像が含まれている場合、パートナー接続は最初に**BODY**プロパティに添付ファイルを含めようとします。</span><span class="sxs-lookup"><span data-stu-id="a3683-438">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="a3683-439">これができない場合は、\* \* ATTACHMENT \* \* プロパティに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a3683-439">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="a3683-440">添付ファイルの例として、他にも Facebook の「いいね」、コンテンツ ソースからのメタデータ、およびメッセージまたは投稿への返信などがあります。</span><span class="sxs-lookup"><span data-stu-id="a3683-440">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="a3683-441">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="a3683-441">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="a3683-442">はい</span><span class="sxs-lookup"><span data-stu-id="a3683-442">Yes</span></span>  <br/> | <span data-ttu-id="a3683-443">これは、パートナーコネクタによって作成および設定される複数値プロパティです。</span><span class="sxs-lookup"><span data-stu-id="a3683-443">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="a3683-444">このプロパティの形式は`IPM.NOTE.Source.Event`です。</span><span class="sxs-lookup"><span data-stu-id="a3683-444">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="a3683-445">(このプロパティはで`IPM.NOTE`始まる必要があります。この形式は、 `IPM.NOTE.X`メッセージクラスのものと似ています)。このプロパティには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3683-445">(This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="a3683-446">`Source`-サードパーティのデータソースを示します。たとえば、Twitter、Facebook、BlackBerry などです。</span><span class="sxs-lookup"><span data-stu-id="a3683-446">`Source` - Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="a3683-447">`Event`-アイテムを生成したサードパーティのデータソースで実行されたアクティビティの種類を示します。たとえば、Twitter のツイート、または Facebook の投稿。</span><span class="sxs-lookup"><span data-stu-id="a3683-447">`Event` - Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="a3683-448">イベントは、データソースに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="a3683-448">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="a3683-449">このプロパティの目的の1つは、アイテムが発生元であるデータソースに基づいて、またはイベントの種類に基づいて、特定のアイテムをフィルター処理することです。</span><span class="sxs-lookup"><span data-stu-id="a3683-449">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="a3683-450">たとえば、電子情報開示検索では、検索クエリを作成して、特定のユーザーによって投稿されたすべてのツイートなど) を検索できます。</span><span class="sxs-lookup"><span data-stu-id="a3683-450">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="a3683-451">アイテムが Office 365 のメールボックスに正常にインポートされると、一意識別子が HTTP 応答の一部として発信者に戻されます。</span><span class="sxs-lookup"><span data-stu-id="a3683-451">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="a3683-452">この識別子`x-IngestionCorrelationID`は、アイテムのエンドツーエンドの追跡のためにパートナーによって、以降のトラブルシューティングのために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3683-452">This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="a3683-453">パートナーがこの情報をキャプチャし、パートナーの側で記録することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3683-453">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="a3683-454">この識別子を示す HTTP 応答の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a3683-454">Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="a3683-455">セキュリティ/コンプライアンスセンターのコンテンツ検索ツールを使用して、サードパーティのデータソースから Office 365 のメールボックスにインポートされたアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="a3683-455">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="a3683-456">これらのインポートされたアイテムを検索するには、次のようなメッセージのプロパティと値のペアをキーワードボックスで使用します。</span><span class="sxs-lookup"><span data-stu-id="a3683-456">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="a3683-457">**`kind:externaldata`**-このプロパティと値のペアを使用して、すべてのサードパーティのデータ型を検索します。</span><span class="sxs-lookup"><span data-stu-id="a3683-457">**`kind:externaldata`** - Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="a3683-458">たとえば、サードパーティのデータソースからインポートされ、インポートされたアイテムの Subject プロパティに "contoso" という単語が含まれているアイテムを検索するには、 `kind:externaldata AND subject:contoso`キーワードクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3683-458">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="a3683-459">**`itemclass:ipm.externaldata.<third-party data type>`**-このプロパティと値のペアを使用して、サードパーティのデータの指定した種類のみを検索します。</span><span class="sxs-lookup"><span data-stu-id="a3683-459">**`itemclass:ipm.externaldata.<third-party data type>`** - Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="a3683-460">たとえば、Subject プロパティに "contoso" という単語が含まれる Facebook データのみを検索するには、キーワードクエリ`itemclass:ipm.externaldata.Facebook* AND subject:contoso`を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3683-460">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="a3683-461">`itemclass`プロパティのサードパーティデータ型に使用する値の完全な一覧については、「[コンテンツ検索を使用して、Office 365 にインポートされたサードパーティのデータを検索する](use-content-search-to-search-third-party-data-that-was-imported.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3683-461">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="a3683-462">コンテンツ検索の使用方法とキーワード検索クエリの作成方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3683-462">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="a3683-463">Office 365 のコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="a3683-463">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="a3683-464">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="a3683-464">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
