---
title: Office 365 でサードパーティのデータをアーカイブする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 管理者は、ソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Office 365 組織のメールボックスにサードパーティのデータをインポートできます。 これにより、Office 365 の Facebook、Twitter、データソースからデータをアーカイブすることができます。 その後、Office 365 のコンプライアンス機能 (法的情報保留、コンテンツ検索、アイテム保持ポリシーなど) をサードパーティのデータに適用することができます。
ms.openlocfilehash: 06ac436b1583187e89cb7f1beb26411ba02becec
ms.sourcegitcommit: 86ff2eba1d57b9d5288840788529e69ad9d836b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2019
ms.locfileid: "31818614"
---
# <a name="archiving-third-party-data-in-office-365"></a><span data-ttu-id="5d7ed-105">Office 365 でサードパーティのデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="5d7ed-105">Archiving third-party data in Office 365</span></span>

<span data-ttu-id="5d7ed-106">office 365 を使用すると、管理者はソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから office 365 組織のメールボックスにサードパーティのデータをインポートしてアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-106">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization.</span></span> <span data-ttu-id="5d7ed-107">Office 365 にインポートできるサードパーティのデータソースの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-107">Examples of third-party data sources that you can import to Office 365 include the following:</span></span> 
  
- <span data-ttu-id="5d7ed-108">**ソーシャル**Twitter、Facebook、Yammer、および LinkedIn</span><span class="sxs-lookup"><span data-stu-id="5d7ed-108">**Social** - Twitter, Facebook, Yammer, and LinkedIn</span></span> 
    
- <span data-ttu-id="5d7ed-109">**インスタントメッセージング**-Yahoo メッセンジャー、GoogleTalk、および Cisco jabber</span><span class="sxs-lookup"><span data-stu-id="5d7ed-109">**Instant messaging** - Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="5d7ed-110">**ドキュメントのコラボレーション**-ボックスとドロップボックス</span><span class="sxs-lookup"><span data-stu-id="5d7ed-110">**Document collaboration** - Box and DropBox</span></span> 
    
- <span data-ttu-id="5d7ed-111">**垂直産業**-顧客関係管理 (Salesforce チャターなど)、金融サービス (Thomson Reuters、Bloomberg など)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-111">**Vertical industries** - Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Thomson Reuters and Bloomberg)</span></span> 
    
- <span data-ttu-id="5d7ed-112">**SMS/text messaging** -BlackBerry</span><span class="sxs-lookup"><span data-stu-id="5d7ed-112">**SMS/text messaging** - BlackBerry</span></span> 
    
<span data-ttu-id="5d7ed-113">サードパーティのデータをインポートした後は、このデータに、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、および Office 365 アイテム保持ポリシーなどの office 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-113">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data.</span></span> <span data-ttu-id="5d7ed-114">たとえば、メールボックスが訴訟ホールドに配置されると、サード パーティ のデータは保存されます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-114">For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved.</span></span> <span data-ttu-id="5d7ed-115">コンテンツ検索を使用して、サードパーティのデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-115">You can search third-party data by using Content Search.</span></span> <span data-ttu-id="5d7ed-116">Microsoft のデータの場合と同じように、アーカイブ ポリシーと保持ポリシーをサード パーティのデータに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-116">Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="5d7ed-117">簡単に言えば、Office 365 でサードパーティのデータをアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-117">In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>
  
<span data-ttu-id="5d7ed-118">このプロセスの概要と、Office 365 にサードパーティのデータをインポートするために必要な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-118">Here's an overview of the process and the steps necessary to import third-party data to Office 365.</span></span>

[<span data-ttu-id="5d7ed-119">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="5d7ed-119">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="5d7ed-120">Step 2: Create and configure a third-party data mailbox in Office 365</span><span class="sxs-lookup"><span data-stu-id="5d7ed-120">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="5d7ed-121">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="5d7ed-121">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="5d7ed-122">手順 4: パートナーに情報を提供する</span><span class="sxs-lookup"><span data-stu-id="5d7ed-122">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="5d7ed-123">手順 5: Azure Active Directory にサードパーティのデータコネクタを登録する</span><span class="sxs-lookup"><span data-stu-id="5d7ed-123">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="5d7ed-124">サードパーティのデータのインポート プロセスが実行される方法</span><span class="sxs-lookup"><span data-stu-id="5d7ed-124">How the third-party data import process works</span></span>

<span data-ttu-id="5d7ed-125">以下の図および説明は、サードパーティのデータのインポート プロセスが実行される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-125">The following illustration and description explain how the third-party data import process works.</span></span>
  
![サードパーティのデータのインポート プロセスが実行される方法](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="5d7ed-127">お客様は、選択したパートナーと連携して、サードパーティのデータソースからアイテムを抽出し、それらのアイテムを Office 365 にインポートするコネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-127">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="5d7ed-128">パートナーコネクタは、サードパーティの API を使用してサードパーティのデータソースに接続し (スケジュールに従って、または構成されている場合)、データソースからアイテムを抽出します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-128">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="5d7ed-129">パートナー コネクタは、アイテムのコンテンツを電子メール メッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-129">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="5d7ed-130">メッセージ形式スキーマの説明については、「[More information](#more-information)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-130">See the [More information](#more-information) section for a description of the message format schema.</span></span> 
    
3. <span data-ttu-id="5d7ed-131">パートナーコネクタは、既知のエンドポイントを介して Exchange Web サービス (EWS) を使用して、Office 365 の Azure サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-131">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="5d7ed-p105">アイテムは特定のユーザーのメールボックスまたは "catch-all" というサードパーティ データのメールボックスにインポートされます。アイテムが特定のユーザーのメールボックスにインポートされるか、またはサードパーティ データのメールボックスにインポートされるかは、以下の条件に基づきます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-p105">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="5d7ed-134">a:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-134">a.</span></span> <span data-ttu-id="5d7ed-135">**office 365 ユーザーアカウントに対応するユーザー id を持つアイテム**。パートナーコネクタがサードパーティデータソース内のアイテムのユーザー id を office 365 の特定のユーザー id にマップできる場合、そのアイテムはユーザーのレコードの [削除] \*\*\*\* フォルダーにコピーされます。overable アイテムフォルダー。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-135">**Items that have a user ID that corresponds to an Office 365 user account** - If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="5d7ed-136">ユーザーがパージフォルダー内のアイテムにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-136">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="5d7ed-137">ただし、Office 365 電子情報開示ツールを使用して、[削除] フォルダー内のアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-137">However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="5d7ed-138">b:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-138">b.</span></span> <span data-ttu-id="5d7ed-139">**office 365 ユーザーアカウントに対応するユーザー id を持たないアイテム**。パートナーコネクタがアイテムのユーザー id を office 365 の特定のユーザー id にマップできない場合、そのアイテムはサードパーティデータメールボックスの**受信トレイ**フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-139">**Items that don't have a user ID that corresponds to an Office 365 user account** - If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="5d7ed-140">受信トレイにアイテムをインポートすると、組織内のユーザーがサードパーティのメールボックスにサインインしてこれらのアイテムを表示および管理できるようになります。また、パートナーコネクタ構成で調整が必要かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-140">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="5d7ed-141">手順 1: サード パーティのデータのパートナーを見つける</span><span class="sxs-lookup"><span data-stu-id="5d7ed-141">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="5d7ed-142">office 365 でサードパーティのデータをアーカイブするための主要なコンポーネントは、サードパーティのデータソースからデータを取得して office 365 にインポートすることに特化した Microsoft パートナーを検索して作業することです。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-142">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="5d7ed-143">インポートされたデータは、組織の他の Microsoft データ (Exchange からの電子メールや SharePoint および OneDrive for business からのメールなど) と共にアーカイブおよび保存することができます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-143">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="5d7ed-144">パートナーは、組織のサードパーティのデータソース (BlackBerry、Facebook、Google +、Thomson Reuters、Twitter、YouTube など) からデータを抽出し、そのデータを、Exchange メールボックスにアイテムをインポートする Office 365 API に渡すコネクタを作成します。電子メールメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-144">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="5d7ed-145">次のセクションでは、Office 365 でサードパーティのデータをアーカイブするためのプログラムに参加している Microsoft パートナーと、そのパートナーがサポートするサードパーティのデータソースを示します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-145">The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="5d7ed-146">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="5d7ed-146">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="5d7ed-147">Actiance</span><span class="sxs-lookup"><span data-stu-id="5d7ed-147">Actiance</span></span>](#actiance)
  
[<span data-ttu-id="5d7ed-148">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="5d7ed-148">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="5d7ed-149">Globanet</span><span class="sxs-lookup"><span data-stu-id="5d7ed-149">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="5d7ed-150">OpenText</span><span class="sxs-lookup"><span data-stu-id="5d7ed-150">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="5d7ed-151">verba</span><span class="sxs-lookup"><span data-stu-id="5d7ed-151">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="5d7ed-152">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="5d7ed-152">17a-4 LLC</span></span>

<span data-ttu-id="5d7ed-153">17a-4 LLC は、次のサードパーティ データ ソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-153">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="5d7ed-154">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="5d7ed-154">BlackBerry</span></span>
    
- <span data-ttu-id="5d7ed-155">Bloomberg データ ストリーム</span><span class="sxs-lookup"><span data-stu-id="5d7ed-155">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="5d7ed-156">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="5d7ed-156">Cisco Jabber</span></span>
    
- <span data-ttu-id="5d7ed-157">FactSet</span><span class="sxs-lookup"><span data-stu-id="5d7ed-157">FactSet</span></span>
    
- <span data-ttu-id="5d7ed-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="5d7ed-158">HipChat</span></span>
    
- <span data-ttu-id="5d7ed-159">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="5d7ed-159">InvestEdge</span></span>
    
- <span data-ttu-id="5d7ed-160">LivePerson</span><span class="sxs-lookup"><span data-stu-id="5d7ed-160">LivePerson</span></span>
    
- <span data-ttu-id="5d7ed-161">MessageLabs データ ストリーム</span><span class="sxs-lookup"><span data-stu-id="5d7ed-161">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="5d7ed-162">OpenText</span><span class="sxs-lookup"><span data-stu-id="5d7ed-162">OpenText</span></span>
    
- <span data-ttu-id="5d7ed-163">Oracle/ATG 'click-to-call' Live ヘルプ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-163">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="5d7ed-164">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="5d7ed-164">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="5d7ed-165">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="5d7ed-165">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="5d7ed-166">MindAlign</span><span class="sxs-lookup"><span data-stu-id="5d7ed-166">MindAlign</span></span>
    
- <span data-ttu-id="5d7ed-167">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-167">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="5d7ed-168">Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-168">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="5d7ed-169">Skype for Business Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-169">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="5d7ed-170">SQL データベース</span><span class="sxs-lookup"><span data-stu-id="5d7ed-170">SQL Databases</span></span>
    
- <span data-ttu-id="5d7ed-171">Squawker</span><span class="sxs-lookup"><span data-stu-id="5d7ed-171">Squawker</span></span>
    
- <span data-ttu-id="5d7ed-172">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="5d7ed-172">Thomson Reuters Eikon Messenger</span></span>
  
### <a name="actiance"></a><span data-ttu-id="5d7ed-173">Actiance</span><span class="sxs-lookup"><span data-stu-id="5d7ed-173">Actiance</span></span>

<span data-ttu-id="5d7ed-174">[Actiance](https://www.actiance.com)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-174">[Actiance](https://www.actiance.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="5d7ed-175">目的</span><span class="sxs-lookup"><span data-stu-id="5d7ed-175">AIM</span></span>
    
- <span data-ttu-id="5d7ed-176">American Idol</span><span class="sxs-lookup"><span data-stu-id="5d7ed-176">American Idol</span></span>
    
- <span data-ttu-id="5d7ed-177">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="5d7ed-177">Apple Juice</span></span>
    
- <span data-ttu-id="5d7ed-178">AOL with Pivot クライアント</span><span class="sxs-lookup"><span data-stu-id="5d7ed-178">AOL with Pivot client</span></span>
    
- <span data-ttu-id="5d7ed-179">アレス</span><span class="sxs-lookup"><span data-stu-id="5d7ed-179">Ares</span></span>
    
- <span data-ttu-id="5d7ed-180">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="5d7ed-180">Bazaar Voice</span></span>
    
- <span data-ttu-id="5d7ed-181">Bearshare</span><span class="sxs-lookup"><span data-stu-id="5d7ed-181">Bear Share</span></span>
    
- <span data-ttu-id="5d7ed-182">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="5d7ed-182">Bit Torrent</span></span>
    
- <span data-ttu-id="5d7ed-183">BlackBerry 呼び出しログ (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-183">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="5d7ed-184">BlackBerry メッセンジャー (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-184">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="5d7ed-185">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-185">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="5d7ed-186">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-186">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="5d7ed-187">Bloomberg メール</span><span class="sxs-lookup"><span data-stu-id="5d7ed-187">Bloomberg Mail</span></span>
    
- <span data-ttu-id="5d7ed-188">celltrust</span><span class="sxs-lookup"><span data-stu-id="5d7ed-188">CellTrust</span></span>
    
- <span data-ttu-id="5d7ed-189">チャットのインポート</span><span class="sxs-lookup"><span data-stu-id="5d7ed-189">Chat Import</span></span>
    
- <span data-ttu-id="5d7ed-190">チャットのリアルタイム ロギングとポリシー</span><span class="sxs-lookup"><span data-stu-id="5d7ed-190">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="5d7ed-191">チャター</span><span class="sxs-lookup"><span data-stu-id="5d7ed-191">Chatter</span></span>
    
- <span data-ttu-id="5d7ed-192">Cisco IM &amp;プレゼンスサーバー (v 9.0.1、v 9.1、v 9.1.1 SU1、v10、v v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-192">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="5d7ed-193">Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-193">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="5d7ed-194">共同作業のインポート</span><span class="sxs-lookup"><span data-stu-id="5d7ed-194">Collaboration Import</span></span>
    
- <span data-ttu-id="5d7ed-195">共同作業のリアルタイム ロギング</span><span class="sxs-lookup"><span data-stu-id="5d7ed-195">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="5d7ed-196">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="5d7ed-196">Direct Connect</span></span>
    
- <span data-ttu-id="5d7ed-197">Facebook</span><span class="sxs-lookup"><span data-stu-id="5d7ed-197">Facebook</span></span>
    
- <span data-ttu-id="5d7ed-198">FactSet</span><span class="sxs-lookup"><span data-stu-id="5d7ed-198">FactSet</span></span>
    
- <span data-ttu-id="5d7ed-199">FastTrack</span><span class="sxs-lookup"><span data-stu-id="5d7ed-199">FastTrack</span></span>
    
- <span data-ttu-id="5d7ed-200">gnutella</span><span class="sxs-lookup"><span data-stu-id="5d7ed-200">Gnutella</span></span>
    
- <span data-ttu-id="5d7ed-201">Google +</span><span class="sxs-lookup"><span data-stu-id="5d7ed-201">Google+</span></span>
    
- <span data-ttu-id="5d7ed-202">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="5d7ed-202">GoToMyPC</span></span>
    
- <span data-ttu-id="5d7ed-203">Hopster</span><span class="sxs-lookup"><span data-stu-id="5d7ed-203">Hopster</span></span>
    
- <span data-ttu-id="5d7ed-204">HubConnex</span><span class="sxs-lookup"><span data-stu-id="5d7ed-204">HubConnex</span></span>
    
- <span data-ttu-id="5d7ed-205">IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-205">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="5d7ed-206">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="5d7ed-206">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="5d7ed-207">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="5d7ed-207">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="5d7ed-208">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="5d7ed-208">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="5d7ed-209">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="5d7ed-209">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="5d7ed-210">IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-210">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="5d7ed-211">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="5d7ed-211">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="5d7ed-212">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="5d7ed-212">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="5d7ed-213">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="5d7ed-213">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="5d7ed-214">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="5d7ed-214">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="5d7ed-215">IM のインポート</span><span class="sxs-lookup"><span data-stu-id="5d7ed-215">IM Import</span></span>
    
- <span data-ttu-id="5d7ed-216">IM のリアルタイム ロギングとポリシー</span><span class="sxs-lookup"><span data-stu-id="5d7ed-216">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="5d7ed-217">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="5d7ed-217">Indii Messenger</span></span>
    
- <span data-ttu-id="5d7ed-218">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="5d7ed-218">Instant Bloomberg</span></span>
    
- <span data-ttu-id="5d7ed-219">IRC</span><span class="sxs-lookup"><span data-stu-id="5d7ed-219">IRC</span></span>
    
- <span data-ttu-id="5d7ed-220">Jive</span><span class="sxs-lookup"><span data-stu-id="5d7ed-220">Jive</span></span>
    
- <span data-ttu-id="5d7ed-221">Jive 6 Real Time Logging (v6、v7)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-221">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="5d7ed-222">Jive のインポート</span><span class="sxs-lookup"><span data-stu-id="5d7ed-222">Jive Import</span></span>
    
- <span data-ttu-id="5d7ed-223">jxta</span><span class="sxs-lookup"><span data-stu-id="5d7ed-223">JXTA</span></span>
    
- <span data-ttu-id="5d7ed-224">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="5d7ed-224">LinkedIn</span></span>
    
- <span data-ttu-id="5d7ed-225">Microsoft Lync (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-225">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="5d7ed-226">mftp</span><span class="sxs-lookup"><span data-stu-id="5d7ed-226">MFTP</span></span>
    
- <span data-ttu-id="5d7ed-227">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="5d7ed-227">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="5d7ed-228">Microsoft SharePoint (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-228">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="5d7ed-229">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5d7ed-229">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="5d7ed-230">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-230">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="5d7ed-231">MindAlign</span><span class="sxs-lookup"><span data-stu-id="5d7ed-231">MindAlign</span></span>
    
- <span data-ttu-id="5d7ed-232">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="5d7ed-232">Mobile Guard</span></span>
    
- <span data-ttu-id="5d7ed-233">ウェブ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-233">MSN</span></span>
    
- <span data-ttu-id="5d7ed-234">My Space</span><span class="sxs-lookup"><span data-stu-id="5d7ed-234">My Space</span></span>
    
- <span data-ttu-id="5d7ed-235">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="5d7ed-235">NEONetwork</span></span>
    
- <span data-ttu-id="5d7ed-236">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="5d7ed-236">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="5d7ed-237">Office 365 Shared IM</span><span class="sxs-lookup"><span data-stu-id="5d7ed-237">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="5d7ed-238">pinterest</span><span class="sxs-lookup"><span data-stu-id="5d7ed-238">Pinterest</span></span>
    
- <span data-ttu-id="5d7ed-239">ピボット</span><span class="sxs-lookup"><span data-stu-id="5d7ed-239">Pivot</span></span>
    
- <span data-ttu-id="5d7ed-240">QQ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-240">QQ</span></span>
    
- <span data-ttu-id="5d7ed-241">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="5d7ed-241">Skype for Business 2015</span></span>
    
- <span data-ttu-id="5d7ed-242">SoftEther</span><span class="sxs-lookup"><span data-stu-id="5d7ed-242">SoftEther</span></span>
    
- <span data-ttu-id="5d7ed-243">Symphony</span><span class="sxs-lookup"><span data-stu-id="5d7ed-243">Symphony</span></span>
    
- <span data-ttu-id="5d7ed-244">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="5d7ed-244">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="5d7ed-245">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="5d7ed-245">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="5d7ed-246">終わり</span><span class="sxs-lookup"><span data-stu-id="5d7ed-246">Tor</span></span>
    
- <span data-ttu-id="5d7ed-247">TTT</span><span class="sxs-lookup"><span data-stu-id="5d7ed-247">TTT</span></span>
    
- <span data-ttu-id="5d7ed-248">Twitter</span><span class="sxs-lookup"><span data-stu-id="5d7ed-248">Twitter</span></span>
    
- <span data-ttu-id="5d7ed-249">winmx</span><span class="sxs-lookup"><span data-stu-id="5d7ed-249">WinMX</span></span>
    
- <span data-ttu-id="5d7ed-250">winny</span><span class="sxs-lookup"><span data-stu-id="5d7ed-250">Winny</span></span>
    
- <span data-ttu-id="5d7ed-251">Yahoo</span><span class="sxs-lookup"><span data-stu-id="5d7ed-251">Yahoo</span></span>
    
- <span data-ttu-id="5d7ed-252">Yammer</span><span class="sxs-lookup"><span data-stu-id="5d7ed-252">Yammer</span></span>
    
- <span data-ttu-id="5d7ed-253">YouTube</span><span class="sxs-lookup"><span data-stu-id="5d7ed-253">YouTube</span></span>
    
  
### <a name="archivesocial"></a><span data-ttu-id="5d7ed-254">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="5d7ed-254">ArchiveSocial</span></span>

<span data-ttu-id="5d7ed-255">[ArchiveSocial](https://www.archivesocial.com)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-255">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="5d7ed-256">Facebook</span><span class="sxs-lookup"><span data-stu-id="5d7ed-256">Facebook</span></span>
    
- <span data-ttu-id="5d7ed-257">Flickr</span><span class="sxs-lookup"><span data-stu-id="5d7ed-257">Flickr</span></span>
    
- <span data-ttu-id="5d7ed-258">Instagram</span><span class="sxs-lookup"><span data-stu-id="5d7ed-258">Instagram</span></span>
    
- <span data-ttu-id="5d7ed-259">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="5d7ed-259">LinkedIn</span></span>
    
- <span data-ttu-id="5d7ed-260">pinterest</span><span class="sxs-lookup"><span data-stu-id="5d7ed-260">Pinterest</span></span>
    
- <span data-ttu-id="5d7ed-261">Twitter</span><span class="sxs-lookup"><span data-stu-id="5d7ed-261">Twitter</span></span>
    
- <span data-ttu-id="5d7ed-262">YouTube</span><span class="sxs-lookup"><span data-stu-id="5d7ed-262">YouTube</span></span>
    
- <span data-ttu-id="5d7ed-263">Vimeo</span><span class="sxs-lookup"><span data-stu-id="5d7ed-263">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="5d7ed-264">Globanet</span><span class="sxs-lookup"><span data-stu-id="5d7ed-264">Globanet</span></span>

<span data-ttu-id="5d7ed-265">[Globanet](https://www.globanet.com)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-265">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="5d7ed-266">AOL with Pivot クライアント</span><span class="sxs-lookup"><span data-stu-id="5d7ed-266">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="5d7ed-267">BlackBerry 呼び出しログ (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-267">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="5d7ed-268">BlackBerry メッセンジャー (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-268">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="5d7ed-269">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-269">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="5d7ed-270">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-270">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="5d7ed-271">Bloomberg チャット</span><span class="sxs-lookup"><span data-stu-id="5d7ed-271">Bloomberg Chat</span></span>
    
- <span data-ttu-id="5d7ed-272">Bloomberg メール</span><span class="sxs-lookup"><span data-stu-id="5d7ed-272">Bloomberg Mail</span></span>
    
- <span data-ttu-id="5d7ed-273">検索ボックス</span><span class="sxs-lookup"><span data-stu-id="5d7ed-273">Box</span></span>
    
- <span data-ttu-id="5d7ed-274">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="5d7ed-274">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="5d7ed-275">Cisco IM &amp;プレゼンスサーバー (v10、v v10.5.1 SU1、v 11.0、v 11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-275">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="5d7ed-276">Cisco Webex Teams</span><span class="sxs-lookup"><span data-stu-id="5d7ed-276">Cisco Webex Teams</span></span>

- <span data-ttu-id="5d7ed-277">Citrix ワーク&amp;スペースの編集ファイル</span><span class="sxs-lookup"><span data-stu-id="5d7ed-277">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="5d7ed-278">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="5d7ed-278">CrowdCompass</span></span>

- <span data-ttu-id="5d7ed-279">カスタムの区切り記号付きテキスト ファイル</span><span class="sxs-lookup"><span data-stu-id="5d7ed-279">Custom delimited text files</span></span>
    
- <span data-ttu-id="5d7ed-280">カスタムの XML ファイル</span><span class="sxs-lookup"><span data-stu-id="5d7ed-280">Custom XML files</span></span>
    
- <span data-ttu-id="5d7ed-281">Facebook (ページ)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-281">Facebook (Pages)</span></span>
    
- <span data-ttu-id="5d7ed-282">Factset</span><span class="sxs-lookup"><span data-stu-id="5d7ed-282">Factset</span></span>
    
- <span data-ttu-id="5d7ed-283">fxconnect</span><span class="sxs-lookup"><span data-stu-id="5d7ed-283">FXConnect</span></span>
    
- <span data-ttu-id="5d7ed-284">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="5d7ed-284">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="5d7ed-285">Jive</span><span class="sxs-lookup"><span data-stu-id="5d7ed-285">Jive</span></span>
    
- <span data-ttu-id="5d7ed-286">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="5d7ed-286">Macgregor XIP</span></span>

- <span data-ttu-id="5d7ed-287">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="5d7ed-287">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="5d7ed-288">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="5d7ed-288">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="5d7ed-289">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d7ed-289">Microsoft Teams</span></span>
       
- <span data-ttu-id="5d7ed-290">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="5d7ed-290">Microsoft Yammer</span></span>
    
- <span data-ttu-id="5d7ed-291">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="5d7ed-291">Mobile Guard</span></span>
    
- <span data-ttu-id="5d7ed-292">ピボット</span><span class="sxs-lookup"><span data-stu-id="5d7ed-292">Pivot</span></span>
    
- <span data-ttu-id="5d7ed-293">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="5d7ed-293">Salesforce Chatter</span></span>

- <span data-ttu-id="5d7ed-294">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5d7ed-294">Skype for Business Online</span></span>
    
- <span data-ttu-id="5d7ed-295">Skype for Business、バージョン 2007 R2 ～ 2016 (オンプレミス)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-295">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="5d7ed-296">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="5d7ed-296">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="5d7ed-297">Symphony</span><span class="sxs-lookup"><span data-stu-id="5d7ed-297">Symphony</span></span>
    
- <span data-ttu-id="5d7ed-298">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="5d7ed-298">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="5d7ed-299">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="5d7ed-299">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="5d7ed-300">Thomson Reuters Dealings 3000 / FX トレーディング</span><span class="sxs-lookup"><span data-stu-id="5d7ed-300">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="5d7ed-301">Twitter</span><span class="sxs-lookup"><span data-stu-id="5d7ed-301">Twitter</span></span>
    
- <span data-ttu-id="5d7ed-302">UBS チャット</span><span class="sxs-lookup"><span data-stu-id="5d7ed-302">UBS Chat</span></span>
    
- <span data-ttu-id="5d7ed-303">YouTube</span><span class="sxs-lookup"><span data-stu-id="5d7ed-303">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="5d7ed-304">OpenText</span><span class="sxs-lookup"><span data-stu-id="5d7ed-304">OpenText</span></span>

<span data-ttu-id="5d7ed-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-305">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="5d7ed-306">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="5d7ed-306">Axs Encrypted</span></span>
    
- <span data-ttu-id="5d7ed-307">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="5d7ed-307">Axs Exchange</span></span>
    
- <span data-ttu-id="5d7ed-308">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="5d7ed-308">Axs Local Archive</span></span>
    
- <span data-ttu-id="5d7ed-309">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="5d7ed-309">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="5d7ed-310">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="5d7ed-310">Axs Signed</span></span>
    
- <span data-ttu-id="5d7ed-311">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="5d7ed-311">Bloomberg</span></span>
    
- <span data-ttu-id="5d7ed-312">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="5d7ed-312">Thomson Reuters</span></span>
  
### <a name="verba"></a><span data-ttu-id="5d7ed-313">verba</span><span class="sxs-lookup"><span data-stu-id="5d7ed-313">Verba</span></span>

<span data-ttu-id="5d7ed-314">[verba](https://www.verba.com)は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-314">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="5d7ed-315">Avaya Aura ビデオ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-315">Avaya Aura Video</span></span>
    
- <span data-ttu-id="5d7ed-316">Avaya Aura 音声</span><span class="sxs-lookup"><span data-stu-id="5d7ed-316">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="5d7ed-317">Avtec ラジオ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-317">Avtec Radio</span></span>
    
- <span data-ttu-id="5d7ed-318">Bosch/Telex ラジオ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-318">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="5d7ed-319">BroadSoft ビデオ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-319">BroadSoft Video</span></span>
    
- <span data-ttu-id="5d7ed-320">BroadSoft 音声</span><span class="sxs-lookup"><span data-stu-id="5d7ed-320">BroadSoft Voice</span></span>
    
- <span data-ttu-id="5d7ed-321">Centile 音声</span><span class="sxs-lookup"><span data-stu-id="5d7ed-321">Centile Voice</span></span>
    
- <span data-ttu-id="5d7ed-322">Cisco Jabber IM</span><span class="sxs-lookup"><span data-stu-id="5d7ed-322">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="5d7ed-323">Cisco UC ビデオ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-323">Cisco UC Video</span></span>
    
- <span data-ttu-id="5d7ed-324">Cisco UC 音声</span><span class="sxs-lookup"><span data-stu-id="5d7ed-324">Cisco UC Voice</span></span>
    
- <span data-ttu-id="5d7ed-325">Cisco uccx/uccx ビデオ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-325">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="5d7ed-326">Cisco uccx/uccx 音声</span><span class="sxs-lookup"><span data-stu-id="5d7ed-326">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="5d7ed-327">ESChat ラジオ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-327">ESChat Radio</span></span>
    
- <span data-ttu-id="5d7ed-328">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="5d7ed-328">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="5d7ed-329">IP Trade 音声</span><span class="sxs-lookup"><span data-stu-id="5d7ed-329">IP Trade Voice</span></span>
    
- <span data-ttu-id="5d7ed-330">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="5d7ed-330">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="5d7ed-331">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-331">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="5d7ed-332">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-332">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="5d7ed-333">Oracle / Acme Packet Session Border Controller ビデオ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-333">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="5d7ed-334">Oracle / Acme Packet Session Border Controller 音声</span><span class="sxs-lookup"><span data-stu-id="5d7ed-334">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="5d7ed-335">Singtel モバイル ボイス</span><span class="sxs-lookup"><span data-stu-id="5d7ed-335">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="5d7ed-336">SIPREC ビデオ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-336">SIPREC Video</span></span>
    
-  <span data-ttu-id="5d7ed-337">SIPREC 音声</span><span class="sxs-lookup"><span data-stu-id="5d7ed-337">SIPREC Voice</span></span> 
    
- <span data-ttu-id="5d7ed-338">Skype for Business / Lync IM</span><span class="sxs-lookup"><span data-stu-id="5d7ed-338">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="5d7ed-339">Skype for Business / Lync ビデオ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-339">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="5d7ed-340">Skype for Business / Lync 音声</span><span class="sxs-lookup"><span data-stu-id="5d7ed-340">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="5d7ed-341">Speakerbus 音声</span><span class="sxs-lookup"><span data-stu-id="5d7ed-341">Speakerbus Voice</span></span>
    
- <span data-ttu-id="5d7ed-342">標準的な SIP/H.323 ビデオ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-342">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="5d7ed-343">標準的な SIP/H.323 音声</span><span class="sxs-lookup"><span data-stu-id="5d7ed-343">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="5d7ed-344">Truphone 音声</span><span class="sxs-lookup"><span data-stu-id="5d7ed-344">Truphone Voice</span></span>
    
- <span data-ttu-id="5d7ed-345">TwistedPair ラジオ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-345">TwistedPair Radio</span></span>
    
- <span data-ttu-id="5d7ed-346">Windows デスクトップ コンピューターの画面</span><span class="sxs-lookup"><span data-stu-id="5d7ed-346">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="5d7ed-347">手順 2: Office 365 でサード パーティ データのメールボックスを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="5d7ed-347">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="5d7ed-348">Office 365 にデータをインポートするためにサードパーティ製のデータメールボックスを作成して構成する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-348">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="5d7ed-349">前に説明したように、パートナーコネクタがアイテムのユーザー ID を Office 365 ユーザーアカウントにマップできない場合、アイテムはこのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-349">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 **<span data-ttu-id="5d7ed-350">Microsoft 365 管理センターでこれらのタスクを完了する</span><span class="sxs-lookup"><span data-stu-id="5d7ed-350">Complete these tasks in the Microsoft 365 admin center</span></span>**
  
1. <span data-ttu-id="5d7ed-351">Office 365 で新しいユーザーアカウントを作成し、Exchange Online プラン2のライセンスを割り当てます。「 [Office 365 にユーザーを追加する」を](https://go.microsoft.com/fwlink/p/?LinkId=692098)参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-351">Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="5d7ed-352">プラン2ライセンスは、メールボックスを訴訟ホールドの対象にするため、または記憶域クォータが無制限のアーカイブメールボックスを有効にするために必要です。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-352">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="5d7ed-353">Office 365 で、サードパーティのデータメールボックスのユーザーアカウントを**Exchange 管理**者の役割に追加します。「 [Office 365 で管理者ロールを割り当てる」を](https://go.microsoft.com/fwlink/p/?LinkId=532393)参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-353">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="5d7ed-354">このユーザー アカウントの資格情報を控えておきます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-354">Write down the credentials for this user account.</span></span> <span data-ttu-id="5d7ed-355">手順 4 で説明するように、この情報をパートナーに提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-355">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 **<span data-ttu-id="5d7ed-356">Exchange 管理センターでこれらのタスクを完了する</span><span class="sxs-lookup"><span data-stu-id="5d7ed-356">Complete these tasks in the Exchange admin center</span></span>**
  
1. <span data-ttu-id="5d7ed-357">組織内のアドレス帳およびその他のアドレス一覧から、サードパーティのデータメールボックスを非表示にします。「[ユーザーメールボックスの管理](https://go.microsoft.com/fwlink/p/?LinkId=616058)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-357">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="5d7ed-358">または、次の PowerShell コマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-358">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="5d7ed-359">サードパーティのデータメールボックスに**fullaccess**のアクセス許可を割り当てて、管理者またはコンプライアンス責任者が Outlook デスクトップクライアントでサードパーティのデータメールボックスを開くことができるようにします。「[管理者のアクセス許可を管理する」を](https://go.microsoft.com/fwlink/p/?LinkId=692104)参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-359">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="5d7ed-360">サードパーティのデータメールボックスに対して、次のコンプライアンス関連の Office 365 機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-360">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="5d7ed-361">アーカイブメールボックスを有効にします。「[アーカイブメールボックスを有効に](enable-archive-mailboxes.md)する」および「[無制限アーカイブを有効にする](enable-unlimited-archiving.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-361">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="5d7ed-362">これにより、サードパーティのデータアイテムをアーカイブメールボックスに移動するアーカイブポリシーを設定することで、プライマリメールボックスの記憶域スペースを解放できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-362">This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="5d7ed-363">これにより、サードパーティのデータに対して無制限のストレージが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-363">This will provide you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="5d7ed-364">サードパーティ データのメールボックスを訴訟ホールドの対象にします。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-364">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="5d7ed-365">セキュリティ/コンプライアンスセンターで Office 365 アイテム保持ポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-365">You can also apply an Office 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="5d7ed-366">このメールボックスを保留にすると、サードパーティのデータアイテム (無期限または指定した期間中) が保持され、それらがメールボックスから削除されるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-366">Placing this mailbox on hold will retain third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="5d7ed-367">次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-367">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="5d7ed-368">メールボックスを訴訟ホールドの対象にする</span><span class="sxs-lookup"><span data-stu-id="5d7ed-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="5d7ed-369">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="5d7ed-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="5d7ed-370">サードパーティデータメールボックスへの所有者、代理人、および管理者のアクセスに対してメールボックス監査ログを有効にします。「 [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-370">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="5d7ed-371">これにより、サードパーティのデータメールボックスにアクセスできるすべてのユーザーによって実行されたすべてのアクティビティを監査できます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-371">This will allow you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="5d7ed-372">手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="5d7ed-372">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="5d7ed-373">次の手順は、サード パーティのデータをサポートするためにユーザーのメールボックスを構成します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-373">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="5d7ed-374">Exchange 管理センターまたは対応する Windows PowerShell コマンドレットを使用して、これらのタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-374">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="5d7ed-375">各ユーザーのアーカイブメールボックスを有効にします。「[アーカイブメールボックスを有効に](enable-archive-mailboxes.md)する」および「[無制限アーカイブを有効にする](enable-unlimited-archiving.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-375">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="5d7ed-376">ユーザーメールボックスを訴訟ホールドの対象にするか、Office 365 アイテム保持ポリシーを適用します。次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-376">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="5d7ed-377">メールボックスを訴訟ホールドの対象にする</span><span class="sxs-lookup"><span data-stu-id="5d7ed-377">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="5d7ed-378">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="5d7ed-378">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="5d7ed-379">前述のように、メールボックスをホールドの対象にすると、サードパーティ データ ソースからのアイテムを保持する期間を設定したり、アイテムを無期限に保持したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-379">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="5d7ed-380">手順 4: パートナーに情報を提供する</span><span class="sxs-lookup"><span data-stu-id="5d7ed-380">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="5d7ed-381">最後の手順は、パートナーが Office 365 の組織に接続するコネクタを構成し、ユーザーのメールボックスおよびサード パーティのデータのメールボックスにデータをインポートできるように、パートナーに以下の情報を提供することです。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-381">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="5d7ed-382">Office 365 の Azure サービスに接続するために使用されるエンドポイント:</span><span class="sxs-lookup"><span data-stu-id="5d7ed-382">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="5d7ed-383">手順2で作成したサードパーティ製データメールボックスのサインイン資格情報 (Office 365 ユーザー ID とパスワード)。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-383">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="5d7ed-384">パートナーのコネクタがアイテムにアクセスして、アイテムをユーザーのメールボックスとサード パーティ データのメールボックスにインポートするには、これらの資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-384">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="5d7ed-385">手順 5: Azure Active Directory にサードパーティのデータコネクタを登録する</span><span class="sxs-lookup"><span data-stu-id="5d7ed-385">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="5d7ed-386">2018年9月30日以降、office 365 の Azure サービスは、Exchange Online での先進認証の使用を開始して、office 365 組織に接続してデータをインポートするサードパーティ製データコネクタを認証します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-386">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data.</span></span> <span data-ttu-id="5d7ed-387">この変更によって、モダン認証は現在のメソッドよりも高いセキュリティを提供しています。これは、以前に説明したエンドポイントを使用して Azure サービスに接続するサードパーティコネクタに基づいていました。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-387">The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="5d7ed-388">新しいモダン認証方法を使用してサードパーティ製データコネクタを office 365 に接続できるようにするには、office 365 組織の管理者が、Azure Active Directory の信頼済みサービスアプリケーションとしてそのコネクタを登録するために同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-388">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="5d7ed-389">これを行うには、アクセス許可要求を受け入れ、コネクタが Azure Active Directory 内の組織のデータにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-389">This is done by accepting a permissions request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="5d7ed-390">この要求を承諾すると、サードパーティのデータコネクタがエンタープライズアプリケーションとして Azure Active Directory に追加され、サービスプリンシパルとして表されます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-390">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="5d7ed-391">同意プロセスの詳細については、「[テナント管理者の同意](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-391">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="5d7ed-392">コネクタを登録するための要求をアクセスして受け入れる手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-392">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="5d7ed-393">[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Office 365 グローバル管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-393">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="5d7ed-394">次のダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-394">The following dialog box is displayed.</span></span> <span data-ttu-id="5d7ed-395">carets を展開して、コネクタに割り当てられているアクセス許可を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-395">You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/>![[アクセス許可の要求] ダイアログが表示されます。](media/O365_ThirdPartyDataConnector_OptIn1.png)
2. <span data-ttu-id="5d7ed-397">[**Accept**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-397">Click **Accept**.</span></span>

<span data-ttu-id="5d7ed-398">要求を受け入れると、 [Azure portal](https://portal.azure.com)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-398">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="5d7ed-399">組織のアプリケーションの一覧を表示するには、[ **Azure Active Directory** > **エンタープライズアプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-399">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="5d7ed-400">Office 365 サードパーティデータコネクタは、**エンタープライズアプリケーション**ブレードに一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-400">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d7ed-401">2018年9月30日以降、サードパーティのデータコネクタを Azure Active Directory に登録しない場合、組織内のメールボックスにサードパーティのデータがインポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-401">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="5d7ed-402">注: 既存のサードパーティのデータコネクタ (2018 年9月30日より前に作成されたもの) は、手順5の手順に従って Azure Active Directory に登録する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-402">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="5d7ed-403">サードパーティのデータコネクタの同意を取り消す</span><span class="sxs-lookup"><span data-stu-id="5d7ed-403">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="5d7ed-404">組織がアクセス許可要求に同意して、Azure Active Directory にサードパーティデータコネクタを登録すると、組織はいつでもその同意を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-404">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="5d7ed-405">ただし、コネクタの同意を取り消すと、サードパーティのデータソースからのデータは Office 365 にインポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-405">However, revoking the consent for a connector will mean that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="5d7ed-406">サードパーティのデータコネクタの同意を取り消すには、azure ポータルの [**エンタープライズアプリケーション**] ブレードまたはを使用[して、azure Active Directory からアプリケーション (対応するサービスプリンシパルを削除) を削除するか、または](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal)Office 365 PowerShell で new-msolserviceprincipal を削除します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-406">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="5d7ed-407">Azure Active Directory PowerShell で[AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal)コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-407">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="5d7ed-408">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5d7ed-408">More information</span></span>

- <span data-ttu-id="5d7ed-409">前述のように、サード パーティのデータ ソースのアイテムは、メール メッセージとして Exchange メールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-409">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="5d7ed-410">パートナーコネクタは、Office 365 API によって必要とされるスキーマを使用してアイテムをインポートします。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-410">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="5d7ed-411">次の表では、メール メッセージとして Exchange メールボックスにインポートされた後の、サード パーティのデータ ソースのアイテムのメッセージのプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-411">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="5d7ed-412">この表では、メッセージのプロパティが必須かどうかも示します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-412">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="5d7ed-413">必須プロパティは設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-413">Mandatory properties must be populated.</span></span> <span data-ttu-id="5d7ed-414">必須のプロパティが設定されていないアイテムは、Office 365 にインポートされません。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-414">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="5d7ed-415">インポート プロセスによって、アイテムがインポートされなかった理由と、どのプロパティが欠落しているのかを記したエラー メッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-415">The import process will return an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |**<span data-ttu-id="5d7ed-416">メッセージのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5d7ed-416">Message property</span></span>**|**<span data-ttu-id="5d7ed-417">必須かどうか?</span><span class="sxs-lookup"><span data-stu-id="5d7ed-417">Mandatory?</span></span>**|**<span data-ttu-id="5d7ed-418">説明</span><span class="sxs-lookup"><span data-stu-id="5d7ed-418">Description</span></span>**|**<span data-ttu-id="5d7ed-419">値の例</span><span class="sxs-lookup"><span data-stu-id="5d7ed-419">Example value</span></span>**|
    |:-----|:-----|:-----|:-----|
    |**<span data-ttu-id="5d7ed-420">差出人</span><span class="sxs-lookup"><span data-stu-id="5d7ed-420">FROM</span></span>** <br/> |<span data-ttu-id="5d7ed-421">はい</span><span class="sxs-lookup"><span data-stu-id="5d7ed-421">Yes</span></span>  <br/> |<span data-ttu-id="5d7ed-422">最初にサード パーティのデータ ソース内のアイテムを作成または送信したユーザー。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-422">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="5d7ed-423">パートナーコネクタは、ソースアイテム (Twitter ハンドルなど) から、すべての参加者 ([差出人] および [宛先] フィールド内のユーザー) の Office 365 ユーザーアカウントにユーザー ID をマップしようとします。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-423">The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="5d7ed-424">メッセージのコピーが、すべての参加者のメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-424">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="5d7ed-425">そのアイテムの参加者が office 365 ユーザーアカウントにマップできない場合、そのアイテムは office 365 のサードパーティのアーカイブメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-425">If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="5d7ed-426">アイテムの送信者として識別される参加者は、アイテムがインポートされる Office 365 組織にアクティブなメールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-426">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to.</span></span> <span data-ttu-id="5d7ed-427">送信者がアクティブなメールボックスを持っていない場合は、次のエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-427">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**<span data-ttu-id="5d7ed-428">宛先</span><span class="sxs-lookup"><span data-stu-id="5d7ed-428">TO</span></span>** <br/> |<span data-ttu-id="5d7ed-429">はい</span><span class="sxs-lookup"><span data-stu-id="5d7ed-429">Yes</span></span>  <br/> |<span data-ttu-id="5d7ed-430">アイテムを受信したユーザー (データ ソース内のアイテムに該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-430">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |**<span data-ttu-id="5d7ed-431">件名</span><span class="sxs-lookup"><span data-stu-id="5d7ed-431">SUBJECT</span></span>** <br/> |<span data-ttu-id="5d7ed-432">なし</span><span class="sxs-lookup"><span data-stu-id="5d7ed-432">No</span></span>  <br/> |<span data-ttu-id="5d7ed-433">ソース アイテムの件名。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-433">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**<span data-ttu-id="5d7ed-434">状態</span><span class="sxs-lookup"><span data-stu-id="5d7ed-434">DATE</span></span>** <br/> |<span data-ttu-id="5d7ed-435">はい</span><span class="sxs-lookup"><span data-stu-id="5d7ed-435">Yes</span></span>  <br/> |<span data-ttu-id="5d7ed-436">アイテムが最初に作成されたか、または顧客データ ソースに投稿された日付 (たとえば、Twitter のメッセージがツイートされた日付)。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-436">The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |**<span data-ttu-id="5d7ed-437">物体</span><span class="sxs-lookup"><span data-stu-id="5d7ed-437">BODY</span></span>** <br/> |<span data-ttu-id="5d7ed-438">なし</span><span class="sxs-lookup"><span data-stu-id="5d7ed-438">No</span></span>  <br/> |<span data-ttu-id="5d7ed-439">メッセージまたは投稿のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-439">The contents of the message or post.</span></span> <span data-ttu-id="5d7ed-440">一部のデータ ソースでは、このプロパティのコンテンツは **SUBJECT** プロパティのコンテンツと同じになります。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-440">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="5d7ed-441">インポート プロセス時に、パートナー コネクタは、できるだけコンテンツ ソースからの完全な再現性を維持しようとします。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-441">During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="5d7ed-442">可能な場合には、ソース アイテムの本文からのファイル、グラフィック、またはその他のコンテンツが、このプロパティに含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-442">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="5d7ed-443">それ以外の場合、ソース アイテムからのコンテンツは **ATTACHMENT** プロパティに含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-443">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="5d7ed-444">このプロパティの内容は、パートナーコネクタとソースプラットフォームの機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-444">The contents of this property will depend on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**<span data-ttu-id="5d7ed-445">資料</span><span class="sxs-lookup"><span data-stu-id="5d7ed-445">ATTACHMENT</span></span>** <br/> |<span data-ttu-id="5d7ed-446">なし</span><span class="sxs-lookup"><span data-stu-id="5d7ed-446">No</span></span>  <br/> |<span data-ttu-id="5d7ed-447">データソース内のアイテム (Twitter のツイート、インスタントメッセージングの会話など) に添付ファイルがあり、画像が含まれている場合、パートナー接続は最初に**BODY**プロパティに添付ファイルを含めようとします。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-447">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="5d7ed-448">これができない場合は、\* \* ATTACHMENT \* \* プロパティに追加されます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-448">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="5d7ed-449">添付ファイルの例として、他にも Facebook の「いいね」、コンテンツ ソースからのメタデータ、およびメッセージまたは投稿への返信などがあります。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-449">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |**<span data-ttu-id="5d7ed-450">MESSAGECLASS</span><span class="sxs-lookup"><span data-stu-id="5d7ed-450">MESSAGECLASS</span></span>** <br/> |<span data-ttu-id="5d7ed-451">はい</span><span class="sxs-lookup"><span data-stu-id="5d7ed-451">Yes</span></span>  <br/> | <span data-ttu-id="5d7ed-452">これは、パートナーコネクタによって作成および設定される複数値プロパティです。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-452">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="5d7ed-453">このプロパティの形式は`IPM.NOTE.Source.Event`です。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-453">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="5d7ed-454">(このプロパティはで`IPM.NOTE`始まる必要があります。この形式は、 `IPM.NOTE.X`メッセージクラスのものと似ています)。このプロパティには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-454">(This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/>`Source` <span data-ttu-id="5d7ed-455">-サードパーティのデータソースを示します。たとえば、Twitter、Facebook、BlackBerry などです。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-455">- Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  `Event` <span data-ttu-id="5d7ed-456">-アイテムを生成したサードパーティのデータソースで実行されたアクティビティの種類を示します。たとえば、Twitter のツイート、または Facebook の投稿。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-456">- Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="5d7ed-457">イベントは、データソースに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-457">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="5d7ed-458">このプロパティの目的の1つは、アイテムが発生元であるデータソースに基づいて、またはイベントの種類に基づいて、特定のアイテムをフィルター処理することです。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-458">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="5d7ed-459">たとえば、電子情報開示検索では、検索クエリを作成して、特定のユーザーによって投稿されたすべてのツイートなど) を検索できます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-459">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="5d7ed-460">アイテムが Office 365 のメールボックスに正常にインポートされると、一意識別子が HTTP 応答の一部として発信者に戻されます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-460">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="5d7ed-461">この識別子`x-IngestionCorrelationID`は、アイテムのエンドツーエンドの追跡のためにパートナーによって、以降のトラブルシューティングのために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-461">This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="5d7ed-462">パートナーがこの情報をキャプチャし、パートナーの側で記録することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-462">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="5d7ed-463">この識別子を示す HTTP 応答の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-463">Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="5d7ed-464">セキュリティ/コンプライアンスセンターのコンテンツ検索ツールを使用して、サードパーティのデータソースから Office 365 のメールボックスにインポートされたアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-464">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="5d7ed-465">これらのインポートされたアイテムを検索するには、次のようなメッセージのプロパティと値のペアをキーワードボックスで使用します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-465">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="5d7ed-466">**`kind:externaldata`**-このプロパティと値のペアを使用して、すべてのサードパーティのデータ型を検索します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-466">**`kind:externaldata`** - Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="5d7ed-467">たとえば、サードパーティのデータソースからインポートされ、インポートされたアイテムの Subject プロパティに "contoso" という単語が含まれているアイテムを検索するには、 `kind:externaldata AND subject:contoso`キーワードクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-467">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="5d7ed-468">**`itemclass:ipm.externaldata.<third-party data type>`**-このプロパティと値のペアを使用して、サードパーティのデータの指定した種類のみを検索します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-468">**`itemclass:ipm.externaldata.<third-party data type>`** - Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="5d7ed-469">たとえば、Subject プロパティに "contoso" という単語が含まれる Facebook データのみを検索するには、キーワードクエリ`itemclass:ipm.externaldata.Facebook* AND subject:contoso`を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-469">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="5d7ed-470">`itemclass`プロパティのサードパーティデータ型に使用する値の完全な一覧については、「[コンテンツ検索を使用して、Office 365 にインポートされたサードパーティのデータを検索する](use-content-search-to-search-third-party-data-that-was-imported.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-470">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="5d7ed-471">コンテンツ検索の使用方法とキーワード検索クエリの作成方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7ed-471">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="5d7ed-472">Office 365 のコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="5d7ed-472">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="5d7ed-473">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="5d7ed-473">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
