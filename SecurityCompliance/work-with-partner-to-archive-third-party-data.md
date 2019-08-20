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
ms.openlocfilehash: 99596953ce0f18c0cd7220f0955d251dbccb0e37
ms.sourcegitcommit: 372691a3a886e5cc299961032ee334aef26fb904
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464700"
---
# <a name="work-with-a-partner-to-archive-third-party-data-in-office-365"></a><span data-ttu-id="d1f84-104">パートナーと連携して、Office 365 でサードパーティのデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="d1f84-104">Work with a partner to archive third-party data in Office 365</span></span>

<span data-ttu-id="d1f84-105">Microsoft パートナーと協力して、サードパーティのデータソースから Office 365 にデータをインポートしてアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-105">You can work with a Microsoft Partner to import and archive data from a third-party data source to Office 365.</span></span> <span data-ttu-id="d1f84-106">パートナーは、サードパーティのデータソースからアイテムを抽出するように構成されたカスタムコネクタ (定期的に) を提供して、それらのアイテムを Office 365 にインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-106">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items to Office 365.</span></span> <span data-ttu-id="d1f84-107">パートナーコネクタは、アイテムのコンテンツをデータソースから電子メールメッセージ形式に変換してから、Office 365 のメールボックスにアイテムを保存します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-107">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes in Office 365.</span></span> <span data-ttu-id="d1f84-108">サードパーティのデータがインポートされた後、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、Office 365 アイテム保持ポリシーなどの Office 365 コンプライアンス機能をこのデータに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-108">After third-party data is imported, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies to this data.</span></span>
  
<span data-ttu-id="d1f84-109">ここでは、サードパーティのデータを Office 365 にインポートするために Microsoft パートナーと連携するために必要なプロセスと手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data to Office 365.</span></span>

[<span data-ttu-id="d1f84-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="d1f84-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="d1f84-111">Step 2: Create and configure a third-party data mailbox in Office 365</span><span class="sxs-lookup"><span data-stu-id="d1f84-111">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="d1f84-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="d1f84-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="d1f84-113">手順 4: パートナーに情報を提供する</span><span class="sxs-lookup"><span data-stu-id="d1f84-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="d1f84-114">手順 5: Azure Active Directory にサードパーティのデータコネクタを登録する</span><span class="sxs-lookup"><span data-stu-id="d1f84-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="d1f84-115">サードパーティのデータのインポート プロセスが実行される方法</span><span class="sxs-lookup"><span data-stu-id="d1f84-115">How the third-party data import process works</span></span>

<span data-ttu-id="d1f84-116">次の図と説明は、パートナーと連携している場合にサードパーティのデータインポートプロセスがどのように動作するかを説明します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![サードパーティのデータのインポート プロセスが実行される方法](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="d1f84-118">お客様は、選択したパートナーと連携して、サードパーティのデータソースからアイテムを抽出し、それらのアイテムを Office 365 にインポートするコネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="d1f84-119">パートナーコネクタは、サードパーティの API を使用してサードパーティのデータソースに接続し (スケジュールに従って、または構成されている場合)、データソースからアイテムを抽出します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="d1f84-120">パートナー コネクタは、アイテムのコンテンツを電子メール メッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="d1f84-121">メッセージ形式スキーマの詳細については、「 [More information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1f84-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="d1f84-122">パートナーコネクタは、既知のエンドポイントを介して Exchange Web サービス (EWS) を使用して、Office 365 の Azure サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-122">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="d1f84-p104">アイテムは特定のユーザーのメールボックスまたは "catch-all" というサードパーティ データのメールボックスにインポートされます。アイテムが特定のユーザーのメールボックスにインポートされるか、またはサードパーティ データのメールボックスにインポートされるかは、以下の条件に基づきます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-p104">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="d1f84-125">a.</span><span class="sxs-lookup"><span data-stu-id="d1f84-125">a.</span></span> <span data-ttu-id="d1f84-126">**Office 365 ユーザーアカウントに対応するユーザー ID を持つアイテム:** パートナーコネクタがサードパーティのデータソース内のアイテムのユーザー ID を Office 365 の特定のユーザー ID にマップできる場合、そのアイテムはユーザーの [回復\*\*\*\* 可能なアイテム] フォルダー内の [削除] フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-126">**Items that have a user ID that corresponds to an Office 365 user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="d1f84-127">ユーザーがパージフォルダー内のアイテムにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="d1f84-127">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="d1f84-128">ただし、Office 365 電子情報開示ツールを使用して、[削除] フォルダー内のアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-128">However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="d1f84-129">b.</span><span class="sxs-lookup"><span data-stu-id="d1f84-129">b.</span></span> <span data-ttu-id="d1f84-130">**Office 365 ユーザーアカウントに対応するユーザー ID を持たないアイテム:** パートナーコネクタが Office 365 の特定のユーザー ID にアイテムのユーザー ID をマップできない場合、そのアイテムはサードパーティデータメールボックスの**受信トレイ**フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-130">**Items that don't have a user ID that corresponds to an Office 365 user account:** If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="d1f84-131">受信トレイにアイテムをインポートすると、組織内のユーザーがサードパーティのメールボックスにサインインしてこれらのアイテムを表示および管理できるようになります。また、パートナーコネクタ構成で調整が必要かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-131">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="d1f84-132">手順 1: サード パーティのデータのパートナーを見つける</span><span class="sxs-lookup"><span data-stu-id="d1f84-132">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="d1f84-133">Office 365 でサードパーティのデータをアーカイブするための主要なコンポーネントは、サードパーティのデータソースからデータを取得して Office 365 にインポートすることに特化した Microsoft パートナーを検索して作業することです。</span><span class="sxs-lookup"><span data-stu-id="d1f84-133">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="d1f84-134">インポートされたデータは、組織の他の Microsoft データ (Exchange からの電子メールや SharePoint および OneDrive for business からのメールなど) と共にアーカイブおよび保存することができます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-134">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="d1f84-135">パートナーは、組織のサードパーティのデータソース (BlackBerry、Facebook、Google +、Thomson Reuters、Twitter、YouTube など) からデータを抽出し、そのデータを、Exchange メールボックスにアイテムをインポートする Office 365 API に渡すコネクタを作成します。電子メールメッセージ。</span><span class="sxs-lookup"><span data-stu-id="d1f84-135">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="d1f84-136">次のセクションでは、Office 365 でサードパーティのデータをアーカイブするためにプログラムに参加している Microsoft パートナー (およびサポートされているサードパーティのデータソース) を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-136">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="d1f84-137">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="d1f84-137">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="d1f84-138">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="d1f84-138">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="d1f84-139">Globanet</span><span class="sxs-lookup"><span data-stu-id="d1f84-139">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="d1f84-140">OpenText</span><span class="sxs-lookup"><span data-stu-id="d1f84-140">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="d1f84-141">Smarsh</span><span class="sxs-lookup"><span data-stu-id="d1f84-141">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="d1f84-142">Verba</span><span class="sxs-lookup"><span data-stu-id="d1f84-142">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="d1f84-143">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="d1f84-143">17a-4 LLC</span></span>

<span data-ttu-id="d1f84-144">17a-4 LLC は、次のサードパーティ データ ソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d1f84-144">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="d1f84-145">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="d1f84-145">BlackBerry</span></span>
    
- <span data-ttu-id="d1f84-146">Bloomberg データ ストリーム</span><span class="sxs-lookup"><span data-stu-id="d1f84-146">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="d1f84-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="d1f84-147">Cisco Jabber</span></span>
    
- <span data-ttu-id="d1f84-148">FactSet</span><span class="sxs-lookup"><span data-stu-id="d1f84-148">FactSet</span></span>
    
- <span data-ttu-id="d1f84-149">HipChat</span><span class="sxs-lookup"><span data-stu-id="d1f84-149">HipChat</span></span>
    
- <span data-ttu-id="d1f84-150">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="d1f84-150">InvestEdge</span></span>
    
- <span data-ttu-id="d1f84-151">LivePerson</span><span class="sxs-lookup"><span data-stu-id="d1f84-151">LivePerson</span></span>
    
- <span data-ttu-id="d1f84-152">MessageLabs データ ストリーム</span><span class="sxs-lookup"><span data-stu-id="d1f84-152">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="d1f84-153">OpenText</span><span class="sxs-lookup"><span data-stu-id="d1f84-153">OpenText</span></span>
    
- <span data-ttu-id="d1f84-154">Oracle/ATG 'click-to-call' Live ヘルプ</span><span class="sxs-lookup"><span data-stu-id="d1f84-154">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="d1f84-155">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="d1f84-155">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="d1f84-156">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="d1f84-156">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="d1f84-157">MindAlign</span><span class="sxs-lookup"><span data-stu-id="d1f84-157">MindAlign</span></span>
    
- <span data-ttu-id="d1f84-158">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="d1f84-158">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="d1f84-159">Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="d1f84-159">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="d1f84-160">Skype for Business Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="d1f84-160">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="d1f84-161">SQL データベース</span><span class="sxs-lookup"><span data-stu-id="d1f84-161">SQL Databases</span></span>
    
- <span data-ttu-id="d1f84-162">Squawker</span><span class="sxs-lookup"><span data-stu-id="d1f84-162">Squawker</span></span>
    
- <span data-ttu-id="d1f84-163">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="d1f84-163">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="d1f84-164">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="d1f84-164">ArchiveSocial</span></span>

<span data-ttu-id="d1f84-165">[ArchiveSocial](https://www.archivesocial.com)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d1f84-165">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="d1f84-166">Facebook</span><span class="sxs-lookup"><span data-stu-id="d1f84-166">Facebook</span></span>
    
- <span data-ttu-id="d1f84-167">Flickr</span><span class="sxs-lookup"><span data-stu-id="d1f84-167">Flickr</span></span>
    
- <span data-ttu-id="d1f84-168">Instagram</span><span class="sxs-lookup"><span data-stu-id="d1f84-168">Instagram</span></span>
    
- <span data-ttu-id="d1f84-169">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="d1f84-169">LinkedIn</span></span>
    
- <span data-ttu-id="d1f84-170">Pinterest</span><span class="sxs-lookup"><span data-stu-id="d1f84-170">Pinterest</span></span>
    
- <span data-ttu-id="d1f84-171">Twitter</span><span class="sxs-lookup"><span data-stu-id="d1f84-171">Twitter</span></span>
    
- <span data-ttu-id="d1f84-172">YouTube</span><span class="sxs-lookup"><span data-stu-id="d1f84-172">YouTube</span></span>
    
- <span data-ttu-id="d1f84-173">Vimeo</span><span class="sxs-lookup"><span data-stu-id="d1f84-173">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="d1f84-174">Globanet</span><span class="sxs-lookup"><span data-stu-id="d1f84-174">Globanet</span></span>

<span data-ttu-id="d1f84-175">[Globanet](https://www.globanet.com)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d1f84-175">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="d1f84-176">AOL with Pivot クライアント</span><span class="sxs-lookup"><span data-stu-id="d1f84-176">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="d1f84-177">BlackBerry 呼び出しログ (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d1f84-177">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d1f84-178">BlackBerry メッセンジャー (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d1f84-178">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d1f84-179">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d1f84-179">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d1f84-180">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d1f84-180">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d1f84-181">Bloomberg チャット</span><span class="sxs-lookup"><span data-stu-id="d1f84-181">Bloomberg Chat</span></span>
    
- <span data-ttu-id="d1f84-182">Bloomberg メール</span><span class="sxs-lookup"><span data-stu-id="d1f84-182">Bloomberg Mail</span></span>
    
- <span data-ttu-id="d1f84-183">検索ボックス</span><span class="sxs-lookup"><span data-stu-id="d1f84-183">Box</span></span>
    
- <span data-ttu-id="d1f84-184">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="d1f84-184">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="d1f84-185">Cisco IM &amp;プレゼンスサーバー (v10、v v10.5.1 SU1、v 11.0、v 11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="d1f84-185">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="d1f84-186">Cisco Webex Teams</span><span class="sxs-lookup"><span data-stu-id="d1f84-186">Cisco Webex Teams</span></span>

- <span data-ttu-id="d1f84-187">Citrix ワーク&amp;スペースの編集ファイル</span><span class="sxs-lookup"><span data-stu-id="d1f84-187">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="d1f84-188">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="d1f84-188">CrowdCompass</span></span>

- <span data-ttu-id="d1f84-189">カスタム区切りのテキストファイル</span><span class="sxs-lookup"><span data-stu-id="d1f84-189">Custom-delimited text files</span></span>
    
- <span data-ttu-id="d1f84-190">カスタムの XML ファイル</span><span class="sxs-lookup"><span data-stu-id="d1f84-190">Custom XML files</span></span>
    
- <span data-ttu-id="d1f84-191">Facebook (ページ)</span><span class="sxs-lookup"><span data-stu-id="d1f84-191">Facebook (Pages)</span></span>
    
- <span data-ttu-id="d1f84-192">Factset</span><span class="sxs-lookup"><span data-stu-id="d1f84-192">Factset</span></span>
    
- <span data-ttu-id="d1f84-193">FXConnect</span><span class="sxs-lookup"><span data-stu-id="d1f84-193">FXConnect</span></span>
    
- <span data-ttu-id="d1f84-194">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="d1f84-194">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="d1f84-195">Jive</span><span class="sxs-lookup"><span data-stu-id="d1f84-195">Jive</span></span>
    
- <span data-ttu-id="d1f84-196">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="d1f84-196">Macgregor XIP</span></span>

- <span data-ttu-id="d1f84-197">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d1f84-197">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="d1f84-198">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d1f84-198">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="d1f84-199">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1f84-199">Microsoft Teams</span></span>
       
- <span data-ttu-id="d1f84-200">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="d1f84-200">Microsoft Yammer</span></span>
    
- <span data-ttu-id="d1f84-201">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="d1f84-201">Mobile Guard</span></span>
    
- <span data-ttu-id="d1f84-202">ピボット</span><span class="sxs-lookup"><span data-stu-id="d1f84-202">Pivot</span></span>
    
- <span data-ttu-id="d1f84-203">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="d1f84-203">Salesforce Chatter</span></span>

- <span data-ttu-id="d1f84-204">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d1f84-204">Skype for Business Online</span></span>
    
- <span data-ttu-id="d1f84-205">Skype for Business、バージョン 2007 R2 ～ 2016 (オンプレミス)</span><span class="sxs-lookup"><span data-stu-id="d1f84-205">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="d1f84-206">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="d1f84-206">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="d1f84-207">Symphony</span><span class="sxs-lookup"><span data-stu-id="d1f84-207">Symphony</span></span>
    
- <span data-ttu-id="d1f84-208">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="d1f84-208">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="d1f84-209">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="d1f84-209">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="d1f84-210">Thomson Reuters Dealings 3000 / FX トレーディング</span><span class="sxs-lookup"><span data-stu-id="d1f84-210">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="d1f84-211">Twitter</span><span class="sxs-lookup"><span data-stu-id="d1f84-211">Twitter</span></span>
    
- <span data-ttu-id="d1f84-212">UBS チャット</span><span class="sxs-lookup"><span data-stu-id="d1f84-212">UBS Chat</span></span>
    
- <span data-ttu-id="d1f84-213">YouTube</span><span class="sxs-lookup"><span data-stu-id="d1f84-213">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="d1f84-214">OpenText</span><span class="sxs-lookup"><span data-stu-id="d1f84-214">OpenText</span></span>

<span data-ttu-id="d1f84-215">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d1f84-215">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="d1f84-216">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="d1f84-216">Axs Encrypted</span></span>
    
- <span data-ttu-id="d1f84-217">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="d1f84-217">Axs Exchange</span></span>
    
- <span data-ttu-id="d1f84-218">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="d1f84-218">Axs Local Archive</span></span>
    
- <span data-ttu-id="d1f84-219">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="d1f84-219">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="d1f84-220">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="d1f84-220">Axs Signed</span></span>
    
- <span data-ttu-id="d1f84-221">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="d1f84-221">Bloomberg</span></span>
    
- <span data-ttu-id="d1f84-222">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="d1f84-222">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="d1f84-223">Smarsh</span><span class="sxs-lookup"><span data-stu-id="d1f84-223">Smarsh</span></span>

<span data-ttu-id="d1f84-224">[Smarsh](https://www.smarsh.com)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d1f84-224">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="d1f84-225">目的</span><span class="sxs-lookup"><span data-stu-id="d1f84-225">AIM</span></span>
    
- <span data-ttu-id="d1f84-226">American Idol</span><span class="sxs-lookup"><span data-stu-id="d1f84-226">American Idol</span></span>
    
- <span data-ttu-id="d1f84-227">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="d1f84-227">Apple Juice</span></span>
    
- <span data-ttu-id="d1f84-228">AOL with Pivot クライアント</span><span class="sxs-lookup"><span data-stu-id="d1f84-228">AOL with Pivot client</span></span>
    
- <span data-ttu-id="d1f84-229">アレス</span><span class="sxs-lookup"><span data-stu-id="d1f84-229">Ares</span></span>
    
- <span data-ttu-id="d1f84-230">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="d1f84-230">Bazaar Voice</span></span>
    
- <span data-ttu-id="d1f84-231">Bearshare</span><span class="sxs-lookup"><span data-stu-id="d1f84-231">Bear Share</span></span>
    
- <span data-ttu-id="d1f84-232">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="d1f84-232">Bit Torrent</span></span>
    
- <span data-ttu-id="d1f84-233">BlackBerry 呼び出しログ (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d1f84-233">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d1f84-234">BlackBerry メッセンジャー (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d1f84-234">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d1f84-235">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d1f84-235">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d1f84-236">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="d1f84-236">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="d1f84-237">Bloomberg メール</span><span class="sxs-lookup"><span data-stu-id="d1f84-237">Bloomberg Mail</span></span>
    
- <span data-ttu-id="d1f84-238">CellTrust</span><span class="sxs-lookup"><span data-stu-id="d1f84-238">CellTrust</span></span>
    
- <span data-ttu-id="d1f84-239">チャットのインポート</span><span class="sxs-lookup"><span data-stu-id="d1f84-239">Chat Import</span></span>
    
- <span data-ttu-id="d1f84-240">チャットのリアルタイム ロギングとポリシー</span><span class="sxs-lookup"><span data-stu-id="d1f84-240">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="d1f84-241">チャター</span><span class="sxs-lookup"><span data-stu-id="d1f84-241">Chatter</span></span>
    
- <span data-ttu-id="d1f84-242">Cisco IM &amp;プレゼンスサーバー (v 9.0.1、v 9.1、v 9.1.1 SU1、v10、v v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="d1f84-242">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="d1f84-243">Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="d1f84-243">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="d1f84-244">共同作業のインポート</span><span class="sxs-lookup"><span data-stu-id="d1f84-244">Collaboration Import</span></span>
    
- <span data-ttu-id="d1f84-245">共同作業のリアルタイム ロギング</span><span class="sxs-lookup"><span data-stu-id="d1f84-245">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="d1f84-246">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="d1f84-246">Direct Connect</span></span>
    
- <span data-ttu-id="d1f84-247">Facebook</span><span class="sxs-lookup"><span data-stu-id="d1f84-247">Facebook</span></span>
    
- <span data-ttu-id="d1f84-248">FactSet</span><span class="sxs-lookup"><span data-stu-id="d1f84-248">FactSet</span></span>
    
- <span data-ttu-id="d1f84-249">FastTrack</span><span class="sxs-lookup"><span data-stu-id="d1f84-249">FastTrack</span></span>
    
- <span data-ttu-id="d1f84-250">Gnutella</span><span class="sxs-lookup"><span data-stu-id="d1f84-250">Gnutella</span></span>
    
- <span data-ttu-id="d1f84-251">Google +</span><span class="sxs-lookup"><span data-stu-id="d1f84-251">Google+</span></span>
    
- <span data-ttu-id="d1f84-252">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="d1f84-252">GoToMyPC</span></span>
    
- <span data-ttu-id="d1f84-253">Hopster</span><span class="sxs-lookup"><span data-stu-id="d1f84-253">Hopster</span></span>
    
- <span data-ttu-id="d1f84-254">HubConnex</span><span class="sxs-lookup"><span data-stu-id="d1f84-254">HubConnex</span></span>
    
- <span data-ttu-id="d1f84-255">IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)</span><span class="sxs-lookup"><span data-stu-id="d1f84-255">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="d1f84-256">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="d1f84-256">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="d1f84-257">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="d1f84-257">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="d1f84-258">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="d1f84-258">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="d1f84-259">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="d1f84-259">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="d1f84-260">IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)</span><span class="sxs-lookup"><span data-stu-id="d1f84-260">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="d1f84-261">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="d1f84-261">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="d1f84-262">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="d1f84-262">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="d1f84-263">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="d1f84-263">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="d1f84-264">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="d1f84-264">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="d1f84-265">IM のインポート</span><span class="sxs-lookup"><span data-stu-id="d1f84-265">IM Import</span></span>
    
- <span data-ttu-id="d1f84-266">IM のリアルタイム ロギングとポリシー</span><span class="sxs-lookup"><span data-stu-id="d1f84-266">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="d1f84-267">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="d1f84-267">Indii Messenger</span></span>
    
- <span data-ttu-id="d1f84-268">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="d1f84-268">Instant Bloomberg</span></span>
    
- <span data-ttu-id="d1f84-269">IRC</span><span class="sxs-lookup"><span data-stu-id="d1f84-269">IRC</span></span>
    
- <span data-ttu-id="d1f84-270">Jive</span><span class="sxs-lookup"><span data-stu-id="d1f84-270">Jive</span></span>
    
- <span data-ttu-id="d1f84-271">Jive 6 Real Time Logging (v6、v7)</span><span class="sxs-lookup"><span data-stu-id="d1f84-271">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="d1f84-272">Jive のインポート</span><span class="sxs-lookup"><span data-stu-id="d1f84-272">Jive Import</span></span>
    
- <span data-ttu-id="d1f84-273">JXTA</span><span class="sxs-lookup"><span data-stu-id="d1f84-273">JXTA</span></span>
    
- <span data-ttu-id="d1f84-274">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="d1f84-274">LinkedIn</span></span>
    
- <span data-ttu-id="d1f84-275">Microsoft Lync (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="d1f84-275">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="d1f84-276">MFTP</span><span class="sxs-lookup"><span data-stu-id="d1f84-276">MFTP</span></span>
    
- <span data-ttu-id="d1f84-277">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="d1f84-277">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="d1f84-278">Microsoft SharePoint (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="d1f84-278">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="d1f84-279">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d1f84-279">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="d1f84-280">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="d1f84-280">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="d1f84-281">MindAlign</span><span class="sxs-lookup"><span data-stu-id="d1f84-281">MindAlign</span></span>
    
- <span data-ttu-id="d1f84-282">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="d1f84-282">Mobile Guard</span></span>
    
- <span data-ttu-id="d1f84-283">ウェブ</span><span class="sxs-lookup"><span data-stu-id="d1f84-283">MSN</span></span>
    
- <span data-ttu-id="d1f84-284">My Space</span><span class="sxs-lookup"><span data-stu-id="d1f84-284">My Space</span></span>
    
- <span data-ttu-id="d1f84-285">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="d1f84-285">NEONetwork</span></span>
    
- <span data-ttu-id="d1f84-286">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="d1f84-286">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="d1f84-287">Office 365 Shared IM</span><span class="sxs-lookup"><span data-stu-id="d1f84-287">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="d1f84-288">Pinterest</span><span class="sxs-lookup"><span data-stu-id="d1f84-288">Pinterest</span></span>
    
- <span data-ttu-id="d1f84-289">ピボット</span><span class="sxs-lookup"><span data-stu-id="d1f84-289">Pivot</span></span>
    
- <span data-ttu-id="d1f84-290">QQ</span><span class="sxs-lookup"><span data-stu-id="d1f84-290">QQ</span></span>
    
- <span data-ttu-id="d1f84-291">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="d1f84-291">Skype for Business 2015</span></span>
    
- <span data-ttu-id="d1f84-292">SoftEther</span><span class="sxs-lookup"><span data-stu-id="d1f84-292">SoftEther</span></span>
    
- <span data-ttu-id="d1f84-293">Symphony</span><span class="sxs-lookup"><span data-stu-id="d1f84-293">Symphony</span></span>
    
- <span data-ttu-id="d1f84-294">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="d1f84-294">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="d1f84-295">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="d1f84-295">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="d1f84-296">終わり</span><span class="sxs-lookup"><span data-stu-id="d1f84-296">Tor</span></span>
    
- <span data-ttu-id="d1f84-297">TTT</span><span class="sxs-lookup"><span data-stu-id="d1f84-297">TTT</span></span>
    
- <span data-ttu-id="d1f84-298">Twitter</span><span class="sxs-lookup"><span data-stu-id="d1f84-298">Twitter</span></span>
    
- <span data-ttu-id="d1f84-299">WinMX</span><span class="sxs-lookup"><span data-stu-id="d1f84-299">WinMX</span></span>
    
- <span data-ttu-id="d1f84-300">Winny</span><span class="sxs-lookup"><span data-stu-id="d1f84-300">Winny</span></span>
    
- <span data-ttu-id="d1f84-301">Yahoo</span><span class="sxs-lookup"><span data-stu-id="d1f84-301">Yahoo</span></span>
    
- <span data-ttu-id="d1f84-302">Yammer</span><span class="sxs-lookup"><span data-stu-id="d1f84-302">Yammer</span></span>
    
- <span data-ttu-id="d1f84-303">YouTube</span><span class="sxs-lookup"><span data-stu-id="d1f84-303">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="d1f84-304">Verba</span><span class="sxs-lookup"><span data-stu-id="d1f84-304">Verba</span></span>

<span data-ttu-id="d1f84-305">[Verba](https://www.verba.com)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d1f84-305">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="d1f84-306">Avaya Aura ビデオ</span><span class="sxs-lookup"><span data-stu-id="d1f84-306">Avaya Aura Video</span></span>
    
- <span data-ttu-id="d1f84-307">Avaya Aura 音声</span><span class="sxs-lookup"><span data-stu-id="d1f84-307">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="d1f84-308">Avtec ラジオ</span><span class="sxs-lookup"><span data-stu-id="d1f84-308">Avtec Radio</span></span>
    
- <span data-ttu-id="d1f84-309">Bosch/Telex ラジオ</span><span class="sxs-lookup"><span data-stu-id="d1f84-309">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="d1f84-310">BroadSoft ビデオ</span><span class="sxs-lookup"><span data-stu-id="d1f84-310">BroadSoft Video</span></span>
    
- <span data-ttu-id="d1f84-311">BroadSoft 音声</span><span class="sxs-lookup"><span data-stu-id="d1f84-311">BroadSoft Voice</span></span>
    
- <span data-ttu-id="d1f84-312">Centile 音声</span><span class="sxs-lookup"><span data-stu-id="d1f84-312">Centile Voice</span></span>
    
- <span data-ttu-id="d1f84-313">Cisco Jabber IM</span><span class="sxs-lookup"><span data-stu-id="d1f84-313">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="d1f84-314">Cisco UC ビデオ</span><span class="sxs-lookup"><span data-stu-id="d1f84-314">Cisco UC Video</span></span>
    
- <span data-ttu-id="d1f84-315">Cisco UC 音声</span><span class="sxs-lookup"><span data-stu-id="d1f84-315">Cisco UC Voice</span></span>
    
- <span data-ttu-id="d1f84-316">Cisco UCCX/UCCX ビデオ</span><span class="sxs-lookup"><span data-stu-id="d1f84-316">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="d1f84-317">Cisco UCCX/UCCX 音声</span><span class="sxs-lookup"><span data-stu-id="d1f84-317">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="d1f84-318">ESChat ラジオ</span><span class="sxs-lookup"><span data-stu-id="d1f84-318">ESChat Radio</span></span>
    
- <span data-ttu-id="d1f84-319">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="d1f84-319">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="d1f84-320">IP Trade 音声</span><span class="sxs-lookup"><span data-stu-id="d1f84-320">IP Trade Voice</span></span>
    
- <span data-ttu-id="d1f84-321">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="d1f84-321">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="d1f84-322">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="d1f84-322">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="d1f84-323">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="d1f84-323">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="d1f84-324">Oracle / Acme Packet Session Border Controller ビデオ</span><span class="sxs-lookup"><span data-stu-id="d1f84-324">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="d1f84-325">Oracle / Acme Packet Session Border Controller 音声</span><span class="sxs-lookup"><span data-stu-id="d1f84-325">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="d1f84-326">Singtel モバイル ボイス</span><span class="sxs-lookup"><span data-stu-id="d1f84-326">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="d1f84-327">SIPREC ビデオ</span><span class="sxs-lookup"><span data-stu-id="d1f84-327">SIPREC Video</span></span>
    
-  <span data-ttu-id="d1f84-328">SIPREC 音声</span><span class="sxs-lookup"><span data-stu-id="d1f84-328">SIPREC Voice</span></span> 
    
- <span data-ttu-id="d1f84-329">Skype for Business / Lync IM</span><span class="sxs-lookup"><span data-stu-id="d1f84-329">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="d1f84-330">Skype for Business / Lync ビデオ</span><span class="sxs-lookup"><span data-stu-id="d1f84-330">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="d1f84-331">Skype for Business / Lync 音声</span><span class="sxs-lookup"><span data-stu-id="d1f84-331">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="d1f84-332">Speakerbus 音声</span><span class="sxs-lookup"><span data-stu-id="d1f84-332">Speakerbus Voice</span></span>
    
- <span data-ttu-id="d1f84-333">標準的な SIP/H.323 ビデオ</span><span class="sxs-lookup"><span data-stu-id="d1f84-333">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="d1f84-334">標準的な SIP/H.323 音声</span><span class="sxs-lookup"><span data-stu-id="d1f84-334">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="d1f84-335">Truphone 音声</span><span class="sxs-lookup"><span data-stu-id="d1f84-335">Truphone Voice</span></span>
    
- <span data-ttu-id="d1f84-336">TwistedPair ラジオ</span><span class="sxs-lookup"><span data-stu-id="d1f84-336">TwistedPair Radio</span></span>
    
- <span data-ttu-id="d1f84-337">Windows デスクトップ コンピューターの画面</span><span class="sxs-lookup"><span data-stu-id="d1f84-337">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="d1f84-338">手順 2: Office 365 でサード パーティ データのメールボックスを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="d1f84-338">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="d1f84-339">Office 365 にデータをインポートするためにサードパーティ製のデータメールボックスを作成して構成する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-339">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="d1f84-340">前に説明したように、パートナーコネクタがアイテムのユーザー ID を Office 365 ユーザーアカウントにマップできない場合、アイテムはこのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-340">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="d1f84-341">**Microsoft 365 管理センターでこれらのタスクを完了する**</span><span class="sxs-lookup"><span data-stu-id="d1f84-341">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="d1f84-342">Office 365 でユーザーアカウントを作成し、Exchange Online プラン2のライセンスを割り当てます。「 [Office 365 にユーザーを追加する」を](https://go.microsoft.com/fwlink/p/?LinkId=692098)参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1f84-342">Create a user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="d1f84-343">プラン2ライセンスは、メールボックスを訴訟ホールドの対象にするため、または記憶域クォータが無制限のアーカイブメールボックスを有効にするために必要です。</span><span class="sxs-lookup"><span data-stu-id="d1f84-343">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="d1f84-344">Office 365 で、サードパーティのデータメールボックスのユーザーアカウントを**Exchange 管理**者の役割に追加します。「 [Office 365 で管理者ロールを割り当てる」を](https://go.microsoft.com/fwlink/p/?LinkId=532393)参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1f84-344">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="d1f84-345">このユーザー アカウントの資格情報を控えておきます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-345">Write down the credentials for this user account.</span></span> <span data-ttu-id="d1f84-346">手順 4 で説明するように、この情報をパートナーに提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1f84-346">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="d1f84-347">**Exchange 管理センターでこれらのタスクを完了する**</span><span class="sxs-lookup"><span data-stu-id="d1f84-347">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="d1f84-348">組織内のアドレス帳およびその他のアドレス一覧から、サードパーティのデータメールボックスを非表示にします。「[ユーザーメールボックスの管理](https://go.microsoft.com/fwlink/p/?LinkId=616058)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1f84-348">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="d1f84-349">または、次の PowerShell コマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-349">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="d1f84-350">サードパーティのデータメールボックスに**Fullaccess**のアクセス許可を割り当てて、管理者またはコンプライアンス責任者が Outlook デスクトップクライアントでサードパーティのデータメールボックスを開くことができるようにします。「[管理者のアクセス許可を管理する」を](https://go.microsoft.com/fwlink/p/?LinkId=692104)参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1f84-350">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="d1f84-351">サードパーティのデータメールボックスに対して、次のコンプライアンス関連の Office 365 機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d1f84-351">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="d1f84-352">アーカイブメールボックスを有効にします。「[アーカイブメールボックスを有効に](enable-archive-mailboxes.md)する」および「[無制限アーカイブを有効にする](enable-unlimited-archiving.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1f84-352">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="d1f84-353">これにより、サードパーティのデータアイテムをアーカイブメールボックスに移動するアーカイブポリシーを設定することによって、プライマリメールボックスの記憶域スペースを解放できます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-353">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="d1f84-354">これにより、サードパーティのデータに対して無制限のストレージが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-354">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="d1f84-355">サードパーティ データのメールボックスを訴訟ホールドの対象にします。</span><span class="sxs-lookup"><span data-stu-id="d1f84-355">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="d1f84-356">セキュリティ/コンプライアンスセンターで Office 365 アイテム保持ポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-356">You can also apply an Office 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="d1f84-357">このメールボックスを保留にすると、サードパーティのデータアイテム (無期限または指定した期間中) が保持され、それらがメールボックスから削除されるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-357">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="d1f84-358">次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1f84-358">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="d1f84-359">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="d1f84-359">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="d1f84-360">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="d1f84-360">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="d1f84-361">サードパーティデータメールボックスへの所有者、代理人、および管理者のアクセスに対してメールボックス監査ログを有効にします。「 [Enable mailbox auditing In Office 365](enable-mailbox-auditing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1f84-361">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="d1f84-362">これにより、サードパーティのデータメールボックスにアクセスできるすべてのユーザーによって実行されたすべてのアクティビティを監査できます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-362">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="d1f84-363">手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="d1f84-363">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="d1f84-364">次の手順は、サード パーティのデータをサポートするためにユーザーのメールボックスを構成します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-364">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="d1f84-365">Exchange 管理センターまたは対応する Windows PowerShell コマンドレットを使用して、これらのタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-365">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="d1f84-366">各ユーザーのアーカイブメールボックスを有効にします。「[アーカイブメールボックスを有効に](enable-archive-mailboxes.md)する」および「[無制限アーカイブを有効にする](enable-unlimited-archiving.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1f84-366">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="d1f84-367">ユーザーメールボックスを訴訟ホールドの対象にするか、Office 365 アイテム保持ポリシーを適用します。次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1f84-367">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="d1f84-368">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="d1f84-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="d1f84-369">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="d1f84-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="d1f84-370">前述のように、メールボックスをホールドの対象にすると、サードパーティ データ ソースからのアイテムを保持する期間を設定したり、アイテムを無期限に保持したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-370">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="d1f84-371">手順 4: パートナーに情報を提供する</span><span class="sxs-lookup"><span data-stu-id="d1f84-371">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="d1f84-372">最後の手順は、パートナーが Office 365 の組織に接続するコネクタを構成し、ユーザーのメールボックスおよびサード パーティのデータのメールボックスにデータをインポートできるように、パートナーに以下の情報を提供することです。</span><span class="sxs-lookup"><span data-stu-id="d1f84-372">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="d1f84-373">Office 365 の Azure サービスに接続するために使用されるエンドポイント:</span><span class="sxs-lookup"><span data-stu-id="d1f84-373">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="d1f84-374">手順2で作成したサードパーティ製データメールボックスのサインイン資格情報 (Office 365 ユーザー ID とパスワード)。</span><span class="sxs-lookup"><span data-stu-id="d1f84-374">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="d1f84-375">パートナーのコネクタがアイテムにアクセスして、アイテムをユーザーのメールボックスとサード パーティ データのメールボックスにインポートするには、これらの資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="d1f84-375">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="d1f84-376">手順 5: Azure Active Directory にサードパーティのデータコネクタを登録する</span><span class="sxs-lookup"><span data-stu-id="d1f84-376">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="d1f84-377">2018年9月30日以降、Office 365 の Azure サービスは、Exchange Online での先進認証の使用を開始して、Office 365 組織に接続してデータをインポートするサードパーティ製データコネクタを認証します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-377">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data.</span></span> <span data-ttu-id="d1f84-378">この変更によって、モダン認証は現在のメソッドよりも高いセキュリティを提供しています。これは、以前に説明したエンドポイントを使用して Azure サービスに接続するサードパーティコネクタに基づいていました。</span><span class="sxs-lookup"><span data-stu-id="d1f84-378">The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="d1f84-379">新しいモダン認証方法を使用してサードパーティ製データコネクタを Office 365 に接続できるようにするには、Office 365 組織の管理者が、Azure Active Directory の信頼済みサービスアプリケーションとしてそのコネクタを登録するために同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1f84-379">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="d1f84-380">これを行うには、アクセス許可要求を受け入れ、コネクタが Azure Active Directory 内の組織のデータにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="d1f84-380">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="d1f84-381">この要求を承諾すると、サードパーティのデータコネクタがエンタープライズアプリケーションとして Azure Active Directory に追加され、サービスプリンシパルとして表されます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-381">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="d1f84-382">同意プロセスの詳細については、「[テナント管理者の同意](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1f84-382">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="d1f84-383">コネクタを登録するための要求をアクセスして受け入れる手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-383">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="d1f84-384">[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Office 365 グローバル管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="d1f84-384">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="d1f84-385">次のダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-385">The following dialog box is displayed.</span></span> <span data-ttu-id="d1f84-386">Carets を展開して、コネクタに割り当てられているアクセス許可を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-386">You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/><span data-ttu-id="d1f84-387">![[アクセス許可の要求] ダイアログが表示されます。](media/O365-ThirdPartyDataConnector-OptIn1.png)</span><span class="sxs-lookup"><span data-stu-id="d1f84-387">![The permissions request dialog is displayed](media/O365-ThirdPartyDataConnector-OptIn1.png)</span></span>
2. <span data-ttu-id="d1f84-388">[**Accept**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1f84-388">Click **Accept**.</span></span>

<span data-ttu-id="d1f84-389">要求を受け入れると、 [Azure portal](https://portal.azure.com)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-389">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="d1f84-390">組織のアプリケーションの一覧を表示するには、[ **Azure Active Directory** > **エンタープライズアプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1f84-390">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="d1f84-391">Office 365 サードパーティデータコネクタは、**エンタープライズアプリケーション**ブレードに一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="d1f84-391">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1f84-392">2018年9月30日以降、サードパーティのデータコネクタを Azure Active Directory に登録しない場合、組織内のメールボックスにサードパーティのデータがインポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="d1f84-392">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="d1f84-393">注: 既存のサードパーティのデータコネクタ (2018 年9月30日より前に作成されたもの) は、手順5の手順に従って Azure Active Directory に登録する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="d1f84-393">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="d1f84-394">サードパーティのデータコネクタの同意を取り消す</span><span class="sxs-lookup"><span data-stu-id="d1f84-394">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="d1f84-395">組織がアクセス許可要求に同意して、Azure Active Directory にサードパーティデータコネクタを登録すると、組織はいつでもその同意を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-395">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="d1f84-396">ただし、コネクタの同意を取り消すということは、サードパーティのデータソースからのデータが Office 365 にインポートされなくなることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-396">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="d1f84-397">サードパーティのデータコネクタの同意を取り消すには、Azure ポータルの [**エンタープライズアプリケーション**] ブレードまたはを使用[して、azure Active Directory からアプリケーション (対応するサービスプリンシパルを削除) を削除するか、または](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal)Office 365 PowerShell で new-msolserviceprincipal を削除します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-397">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="d1f84-398">Azure Active Directory PowerShell で[AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal)コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-398">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="d1f84-399">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d1f84-399">More information</span></span>

- <span data-ttu-id="d1f84-400">前述のように、サード パーティのデータ ソースのアイテムは、メール メッセージとして Exchange メールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-400">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="d1f84-401">パートナーコネクタは、Office 365 API によって必要とされるスキーマを使用してアイテムをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d1f84-401">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="d1f84-402">次の表では、メール メッセージとして Exchange メールボックスにインポートされた後の、サード パーティのデータ ソースのアイテムのメッセージのプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-402">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="d1f84-403">この表では、メッセージのプロパティが必須かどうかも示します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-403">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="d1f84-404">必須プロパティは設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1f84-404">Mandatory properties must be populated.</span></span> <span data-ttu-id="d1f84-405">必須のプロパティが設定されていないアイテムは、Office 365 にインポートされません。</span><span class="sxs-lookup"><span data-stu-id="d1f84-405">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="d1f84-406">インポートプロセスでは、アイテムがインポートされなかった理由と、不足しているプロパティがあることを示すエラーメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-406">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="d1f84-407">**メッセージのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="d1f84-407">**Message property**</span></span>|<span data-ttu-id="d1f84-408">**必須かどうか?**</span><span class="sxs-lookup"><span data-stu-id="d1f84-408">**Mandatory?**</span></span>|<span data-ttu-id="d1f84-409">**説明**</span><span class="sxs-lookup"><span data-stu-id="d1f84-409">**Description**</span></span>|<span data-ttu-id="d1f84-410">**値の例**</span><span class="sxs-lookup"><span data-stu-id="d1f84-410">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d1f84-411">**FROM**</span><span class="sxs-lookup"><span data-stu-id="d1f84-411">**FROM**</span></span> <br/> |<span data-ttu-id="d1f84-412">はい</span><span class="sxs-lookup"><span data-stu-id="d1f84-412">Yes</span></span>  <br/> |<span data-ttu-id="d1f84-413">最初にサード パーティのデータ ソース内のアイテムを作成または送信したユーザー。</span><span class="sxs-lookup"><span data-stu-id="d1f84-413">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="d1f84-414">パートナーコネクタは、ユーザー ID をソースアイテム (Twitter ハンドルなど) から、すべての参加者 ([差出人] および [宛先] フィールド内のユーザー) の Office 365 ユーザーアカウントにマップしようとします。</span><span class="sxs-lookup"><span data-stu-id="d1f84-414">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="d1f84-415">メッセージのコピーが、すべての参加者のメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-415">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="d1f84-416">そのアイテムの参加者が Office 365 ユーザーアカウントにマップできない場合、そのアイテムは Office 365 のサードパーティのアーカイブメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-416">If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="d1f84-417">アイテムの送信者として識別される参加者は、アイテムがインポートされる Office 365 組織にアクティブなメールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1f84-417">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to.</span></span> <span data-ttu-id="d1f84-418">送信者がアクティブなメールボックスを持っていない場合は、次のエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-418">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="d1f84-419">**TO**</span><span class="sxs-lookup"><span data-stu-id="d1f84-419">**TO**</span></span> <br/> |<span data-ttu-id="d1f84-420">はい</span><span class="sxs-lookup"><span data-stu-id="d1f84-420">Yes</span></span>  <br/> |<span data-ttu-id="d1f84-421">アイテムを受信したユーザー (データ ソース内のアイテムに該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="d1f84-421">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="d1f84-422">**件名**</span><span class="sxs-lookup"><span data-stu-id="d1f84-422">**SUBJECT**</span></span> <br/> |<span data-ttu-id="d1f84-423">いいえ</span><span class="sxs-lookup"><span data-stu-id="d1f84-423">No</span></span>  <br/> |<span data-ttu-id="d1f84-424">ソース アイテムの件名。</span><span class="sxs-lookup"><span data-stu-id="d1f84-424">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="d1f84-425">**DATE**</span><span class="sxs-lookup"><span data-stu-id="d1f84-425">**DATE**</span></span> <br/> |<span data-ttu-id="d1f84-426">はい</span><span class="sxs-lookup"><span data-stu-id="d1f84-426">Yes</span></span>  <br/> |<span data-ttu-id="d1f84-427">アイテムが最初に作成または顧客データソースに投稿された日付。</span><span class="sxs-lookup"><span data-stu-id="d1f84-427">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="d1f84-428">たとえば、Twitter メッセージがツイートされた日時です。</span><span class="sxs-lookup"><span data-stu-id="d1f84-428">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="d1f84-429">**物体**</span><span class="sxs-lookup"><span data-stu-id="d1f84-429">**BODY**</span></span> <br/> |<span data-ttu-id="d1f84-430">いいえ</span><span class="sxs-lookup"><span data-stu-id="d1f84-430">No</span></span>  <br/> |<span data-ttu-id="d1f84-431">メッセージまたは投稿のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="d1f84-431">The contents of the message or post.</span></span> <span data-ttu-id="d1f84-432">一部のデータ ソースでは、このプロパティのコンテンツは **SUBJECT** プロパティのコンテンツと同じになります。</span><span class="sxs-lookup"><span data-stu-id="d1f84-432">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="d1f84-433">インポート処理中に、パートナーコネクタは、可能な限りコンテンツソースの完全な忠実性を維持しようとします。</span><span class="sxs-lookup"><span data-stu-id="d1f84-433">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="d1f84-434">可能な場合には、ソース アイテムの本文からのファイル、グラフィック、またはその他のコンテンツが、このプロパティに含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-434">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="d1f84-435">それ以外の場合、ソース アイテムからのコンテンツは **ATTACHMENT** プロパティに含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-435">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="d1f84-436">このプロパティの内容は、パートナーコネクタとソースプラットフォームの機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d1f84-436">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="d1f84-437">**資料**</span><span class="sxs-lookup"><span data-stu-id="d1f84-437">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="d1f84-438">いいえ</span><span class="sxs-lookup"><span data-stu-id="d1f84-438">No</span></span>  <br/> |<span data-ttu-id="d1f84-439">データソース内のアイテム (Twitter のツイート、インスタントメッセージングの会話など) に添付ファイルがあり、画像が含まれている場合、パートナー接続は最初に**BODY**プロパティに添付ファイルを含めようとします。</span><span class="sxs-lookup"><span data-stu-id="d1f84-439">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="d1f84-440">これができない場合は、\* \* ATTACHMENT \* \* プロパティに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-440">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="d1f84-441">添付ファイルの例として、他にも Facebook の「いいね」、コンテンツ ソースからのメタデータ、およびメッセージまたは投稿への返信などがあります。</span><span class="sxs-lookup"><span data-stu-id="d1f84-441">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="d1f84-442">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="d1f84-442">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="d1f84-443">はい</span><span class="sxs-lookup"><span data-stu-id="d1f84-443">Yes</span></span>  <br/> | <span data-ttu-id="d1f84-444">これは、パートナーコネクタによって作成および設定される複数値プロパティです。</span><span class="sxs-lookup"><span data-stu-id="d1f84-444">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="d1f84-445">このプロパティの形式は`IPM.NOTE.Source.Event`です。</span><span class="sxs-lookup"><span data-stu-id="d1f84-445">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="d1f84-446">(このプロパティはで`IPM.NOTE`始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1f84-446">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="d1f84-447">この形式は、 `IPM.NOTE.X`メッセージクラスの形式と似ています)。このプロパティには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-447">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="d1f84-448">`Source`: サードパーティのデータソースを示します。たとえば、Twitter、Facebook、BlackBerry などです。</span><span class="sxs-lookup"><span data-stu-id="d1f84-448">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="d1f84-449">`Event`: アイテムを生成したサードパーティのデータソースで実行されたアクティビティの種類を示します。たとえば、Twitter のツイート、または Facebook の投稿。</span><span class="sxs-lookup"><span data-stu-id="d1f84-449">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="d1f84-450">イベントは、データソースに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="d1f84-450">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="d1f84-451">このプロパティの目的の1つは、アイテムが発生元であるデータソースに基づいて、またはイベントの種類に基づいて、特定のアイテムをフィルター処理することです。</span><span class="sxs-lookup"><span data-stu-id="d1f84-451">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="d1f84-452">たとえば、電子情報開示検索では、検索クエリを作成して、特定のユーザーによって投稿されたすべてのツイートなど) を検索できます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-452">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="d1f84-453">アイテムが Office 365 のメールボックスに正常にインポートされると、一意識別子が HTTP 応答の一部として発信者に戻されます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-453">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="d1f84-454">と呼ば`x-IngestionCorrelationID`れるこの識別子は、アイテムのエンドツーエンドの追跡のためにパートナーによって、以降のトラブルシューティングのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-454">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="d1f84-455">パートナーがこの情報をキャプチャし、パートナーの側で記録することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1f84-455">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="d1f84-456">この識別子を示す HTTP 応答の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-456">Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="d1f84-457">セキュリティ/コンプライアンスセンターのコンテンツ検索ツールを使用して、サードパーティのデータソースから Office 365 のメールボックスにインポートされたアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="d1f84-457">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="d1f84-458">これらのインポートされたアイテムを検索するには、次のようなメッセージのプロパティと値のペアをキーワードボックスで使用します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-458">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="d1f84-459">**`kind:externaldata`**: このプロパティと値のペアを使用して、すべてのサードパーティのデータ型を検索します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-459">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="d1f84-460">たとえば、サードパーティのデータソースからインポートされ、インポートされたアイテムの Subject プロパティに "contoso" という単語が含まれているアイテムを検索するには、 `kind:externaldata AND subject:contoso`キーワードクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-460">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="d1f84-461">**`itemclass:ipm.externaldata.<third-party data type>`**: このプロパティと値のペアを使用して、サードパーティのデータの指定した種類のみを検索します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-461">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="d1f84-462">たとえば、Subject プロパティに "contoso" という単語が含まれる Facebook データのみを検索するには、キーワードクエリ`itemclass:ipm.externaldata.Facebook* AND subject:contoso`を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1f84-462">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="d1f84-463">`itemclass`プロパティのサードパーティデータ型に使用する値の完全な一覧については、「[コンテンツ検索を使用して、Office 365 にインポートされたサードパーティのデータを検索する](use-content-search-to-search-third-party-data-that-was-imported.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1f84-463">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="d1f84-464">コンテンツ検索の使用方法とキーワード検索クエリの作成方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1f84-464">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="d1f84-465">Office 365 のコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="d1f84-465">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="d1f84-466">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="d1f84-466">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
