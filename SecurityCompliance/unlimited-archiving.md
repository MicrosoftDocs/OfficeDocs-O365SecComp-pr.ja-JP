---
title: Office 365 での無制限アーカイブの概要
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Exchange Online メールボックスに無制限のアーカイブ記憶域を提供する Office 365 の自動拡張アーカイブについて説明します。
ms.openlocfilehash: bf79ec35fe1ee55702f8a3715d62f102d1d88632
ms.sourcegitcommit: 73f1db241c0686020167d43442e7b07a2199ea3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "36658133"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="cdf1d-103">Office 365 での無制限アーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="cdf1d-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="cdf1d-104">Office 365 のアーカイブ メールボックスは、ユーザーに追加のメールボックス記憶領域を提供します。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-104">In Office 365, archive mailboxes provide users with additional mailbox storage space.</span></span> <span data-ttu-id="cdf1d-105">ユーザーのアーカイブ メールボックスを有効にすると、最大 100 GB の追加記憶域を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-105">After a user's archive mailbox is enabled, up to 100 GB of additional storage is available.</span></span> <span data-ttu-id="cdf1d-106">以前は、100 GB の記憶域クォータに到達すると、組織はアーカイブメールボックス用の追加の記憶域を要求するために Microsoft に連絡する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-106">In the past, when the 100 GB storage quota was reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox.</span></span> <span data-ttu-id="cdf1d-107">このようなことはもうなくなります。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-107">That's no longer the case.</span></span>

<span data-ttu-id="cdf1d-108">Office 365 の無制限アーカイブ機能 (*自動拡張アーカイブ*と呼ばれます) は、アーカイブメールボックスに最大 1 TB の追加ストレージを提供します。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-108">The unlimited archiving feature in Office 365 (called *auto-expanding archiving*) provides up to 1 TB of additional storage in archive mailboxes.</span></span> <span data-ttu-id="cdf1d-109">アーカイブメールボックスの格納域の制限に達すると、Office 365 によってアーカイブのサイズが自動的に増加します。つまり、ユーザーはメールボックスの格納域を使用できないため、管理者はアーカイブメールボックスに追加の記憶域を要求する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-109">When the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>
  
<span data-ttu-id="cdf1d-110">自動拡張アーカイブを有効にする詳しい手順については、「[Office 365 で無制限アーカイブを有効にする](enable-unlimited-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cdf1d-111">アーカイブの自動拡張では、共有メールボックスもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-111">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="cdf1d-112">共有メールボックスのアーカイブを有効にするには、Exchange Online プラン 2 のライセンス、または Exchange Online Archiving のライセンスの付いた Exchange Online プラン 1 のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-112">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span> 
  
## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="cdf1d-113">自動拡張アーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="cdf1d-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="cdf1d-114">前に説明したように、ユーザーのアーカイブ メールボックスが有効になっていると、追加のメールボックス記憶領域が作成されます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-114">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled.</span></span> <span data-ttu-id="cdf1d-115">自動拡張アーカイブを有効にすると、Office 365 は定期的にアーカイブ メールボックスのサイズを確認します。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-115">When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox.</span></span> <span data-ttu-id="cdf1d-116">アーカイブメールボックスが格納域の制限に近づいた場合、Office 365 によってアーカイブメールボックス用の追加の記憶域が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-116">When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive mailbox.</span></span> <span data-ttu-id="cdf1d-117">この追加スペースは、*補助アーカイブ*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-117">This additional space is called an *auxiliary archive*.</span></span> <span data-ttu-id="cdf1d-118">ユーザーが補助アーカイブの記憶領域が不足すると、Office 365 によって自動的に新しい補助アーカイブが追加されます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-118">If the user runs out of storage space in an auxiliary archive, Office 365 will automatically add a new auxiliary archive.</span></span> <span data-ttu-id="cdf1d-119">Office 365 では、合計 1 TB の追加のストレージに対して、最大20個の補助アーカイブが追加されます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-119">Office 365 will add a maximum of 20 auxiliary archives for a total of 1 TB of addtional storage.</span></span> <span data-ttu-id="cdf1d-120">このプロセスは自動的に実行されるため、管理者が自動拡張アーカイブを管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-120">This process happens automatically, which means administrators don't have to manage auto-expanding archiving.</span></span> 
  
<span data-ttu-id="cdf1d-121">処理の概要は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-121">Here's a quick overview of the process.</span></span>
  
![自動拡張アーカイブ プロセスの概要](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. <span data-ttu-id="cdf1d-123">ユーザーのメールボックスまたは共有のメールボックスに対してアーカイブが有効になります。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-123">Archiving is enabled for a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="cdf1d-124">100 GB の記憶領域を持つアーカイブ メールボックスが作成され、アーカイブ メールボックスの警告のクォータが 90 GB に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-124">An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>
    
2. <span data-ttu-id="cdf1d-125">管理者がメールボックスの自動拡張アーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-125">An administrator enables auto-expanding archiving for the mailbox.</span></span> <span data-ttu-id="cdf1d-126">アーカイブメールボックス (回復可能なアイテムフォルダーを含む) が 90 GB に達すると、自動拡張アーカイブに変換され、Office 365 はアーカイブに記憶域を追加します。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-126">When the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive.</span></span> <span data-ttu-id="cdf1d-127">追加の記憶領域がプロビジョニングされるには、最大 30 日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-127">Note that it can take up to 30 days for the additional storage space to be provisioned.</span></span>

> [!NOTE]
> <span data-ttu-id="cdf1d-128">メールボックスが保留にされているか、Office 365 のアイテム保持ポリシーに割り当てられている場合は、自動拡張アーカイブを有効にするとアーカイブ メールボックスの記憶領域のクォータが 110 GB に増やされます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-128">If a mailbox is placed on hold or assigned to an Office 365 retention policy, the storage quota for the archive maibox is increased to 110 GB when auto-expanding archiving is enabled.</span></span> <span data-ttu-id="cdf1d-129">同様に、アーカイブ警告クォータは、100 GB に増やされます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-129">Similarly, the archive warning quota is increased to 100 GB.</span></span>
    
3. <span data-ttu-id="cdf1d-130">Office 365 では、必要に応じてストレージ容量が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-130">Office 365 automatically adds more storage space when necessary.</span></span> <span data-ttu-id="cdf1d-131">前述したように、Office 365 は最大20個の補助アーカイブを追加します。これは、最大で 1 TB の追加のアーカイブストレージ容量です。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-131">As previously stated, Office 365 will add up to 20 auxiliary archives, for a maximum of 1 TB of additional archive storage space.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cdf1d-132">自動拡張アーカイブは、個々のユーザー (または共有メールボックス) に使用され、1日あたり 1 GB を超える成長率を持つメールボックスに対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-132">Auto-expanding archive is only supported for mailboxes used for individual users (or shared mailboxes) with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="cdf1d-133">ユーザーのアーカイブ メールボックスは、そのユーザー専用です。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-133">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="cdf1d-134">アーカイブメールボックスにメッセージをコピーするために、ジャーナリング、トランスポートルール、または自動転送ルールを使用することは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-134">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox is not permitted.</span></span> <span data-ttu-id="cdf1d-135">Microsoft は、ユーザーのアーカイブ メールボックスを使用して他のユーザーのアーカイブ データを格納する、インスタンスでの無制限アーカイブを拒否する権利を有します。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-135">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="cdf1d-136">追加のアーカイブ記憶領域に移動されるもの</span><span class="sxs-lookup"><span data-stu-id="cdf1d-136">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="cdf1d-137">自動拡張アーカイブ記憶域を効率的に使用するために、フォルダーは移動される場合があります。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-137">To make efficient use of auto-expanding archive storage, folders might get moved.</span></span> <span data-ttu-id="cdf1d-138">Office 365 では、追加記憶域がアーカイブに追加されたときに、どのフォルダーを移動するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-138">Office 365 determines which folders get moved when additional storage is added to the archive.</span></span> <span data-ttu-id="cdf1d-139">フォルダーが移動されると、Outlook のフォルダー一覧のアーカイブ部分の元のフォルダーの下にサブフォルダーが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-139">When a folder is moved, a subfolder is automatically created under the original folder in the archive portion of the folder list in Outlook.</span></span> <span data-ttu-id="cdf1d-140">この新しいサブフォルダーは、移動されたアイテムを参照します。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-140">This new subfolder points to the items that were moved.</span></span> <span data-ttu-id="cdf1d-141">Office 365 は、このフォルダーに **\<フォルダー名\>_yyyy (作成日: mmm dd、yyyy h_mm)** という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-141">The naming convention that Office 365 uses to name this folder is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span> 
  
- <span data-ttu-id="cdf1d-142">**yyyy** は、フォルダー内のメッセージが受信された年です。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-142">**yyyy** is the year the messages in the folder were received.</span></span> 
    
- <span data-ttu-id="cdf1d-143">**mmm dd, yyyy h_m** は、Office 365 によってサブフォルダーが作成された日時 (UTC 形式) であり、Outlook でのユーザーのタイム ゾーンと地域の設定に基づきます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-143">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span> 
    
<span data-ttu-id="cdf1d-144">次のスクリーンショットは、メッセージが自動拡張アーカイブに移動される前と後のフォルダー一覧です。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-144">The following screen shots show a folder list before and after messages are moved in an auto-expanded archive.</span></span>
  
 <span data-ttu-id="cdf1d-145">**追加記憶域が追加される前**</span><span class="sxs-lookup"><span data-stu-id="cdf1d-145">**Before additional storage is added**</span></span>
  
![自動拡張アーカイブがプロビジョニングされる前のアーカイブ メールボックスのフォルダー一覧](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 <span data-ttu-id="cdf1d-147">**追加記憶域が追加された後**</span><span class="sxs-lookup"><span data-stu-id="cdf1d-147">**After additional storage is added**</span></span>
  
![自動拡張アーカイブがプロビジョニングされた後のアーカイブ メールボックスのフォルダー一覧](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="cdf1d-149">自動拡張アーカイブ内のアイテムにアクセスするための Outlook の要件</span><span class="sxs-lookup"><span data-stu-id="cdf1d-149">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="cdf1d-150">自動拡張アーカイブに保存されているメッセージにアクセスするには、ユーザーは次のいずれかの Outlook クライアントを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-150">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>
  
- <span data-ttu-id="cdf1d-151">Windows 版の Outlook 2016、Outlook 2019</span><span class="sxs-lookup"><span data-stu-id="cdf1d-151">Outlook 2016 or Outlook 2019 for Windows</span></span>
    
- <span data-ttu-id="cdf1d-152">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="cdf1d-152">Outlook on the web</span></span> 
    
- <span data-ttu-id="cdf1d-153">Mac 版の Outlook 2016、Outlook 2019</span><span class="sxs-lookup"><span data-stu-id="cdf1d-153">Outlook 2016 or Outlook 2019 for Mac</span></span> 
    
> [!NOTE]
> <span data-ttu-id="cdf1d-154">Outlook 2013 ユーザーは、アーカイブ メールボックスにもともと保存されていたアイテムのみにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-154">Outlook 2013 users can only access items that were originally stored in their archive mailbox.</span></span> <span data-ttu-id="cdf1d-155">追加アーカイブ記憶域に移動されたアイテムにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-155">They won't be able to access items that are moved to additional archive storage.</span></span> 
  
<span data-ttu-id="cdf1d-156">Outlook または Outlook on the web を使って自動拡張アーカイブに保存されているメッセージにアクセスするときは、いくつかのことを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-156">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>
  
- <span data-ttu-id="cdf1d-157">自動拡張記憶域に移動されたものも含め、アーカイブ メールボックスの任意のフォルダーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-157">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>
    
- <span data-ttu-id="cdf1d-158">フォルダー自体を検索することによってのみ、追加記憶域に移動されたアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-158">You can search for items that were moved to an additional storage area only by searching the folder itself.</span></span> <span data-ttu-id="cdf1d-159">つまり、フォルダー一覧でアーカイブ フォルダーを選び、検索範囲として [**現在の​​フォルダー**] オプションを選ぶ必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-159">This means you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope.</span></span> <span data-ttu-id="cdf1d-160">同様に、自動拡張記憶域内のフォルダーにサブフォルダーがある場合は、各サブフォルダーを個別に検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-160">Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span> 
    
- <span data-ttu-id="cdf1d-161">自動拡張アーカイブ内の Outlook のアイテム数および閲覧済み/未読数 (Outlook および Outlook on the web) は正しくないことがあります。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-161">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web ) in an auto-expanded archive might not be accurate.</span></span>
    
- <span data-ttu-id="cdf1d-162">自動拡張記憶域を参照しているサブフォルダー内のアイテムを削除することはできますが、フォルダー自体を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-162">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>
    
- <span data-ttu-id="cdf1d-163">[削除済みアイテムを復元] 機能を使って、自動拡張記憶域から削除されたアイテムを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-163">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="cdf1d-164">自動拡張アーカイブと Office 365 のその他の法令遵守機能</span><span class="sxs-lookup"><span data-stu-id="cdf1d-164">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="cdf1d-165">ここでは、自動拡張アーカイブと、Office 365 のその他の法令遵守およびデータ ガバナンス機能の間の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-165">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>
  
- <span data-ttu-id="cdf1d-166">**電子情報開示** - コンテンツ検索やインプレース電子情報開示などの Office 365 の電子情報開示ツールを使うと、自動拡張アーカイブ内の追加記憶域も検索されます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-166">**eDiscovery** - When you use an Office 365 eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>
    
- <span data-ttu-id="cdf1d-167">**保持** - Exchange Online の訴訟ホールドや、のセキュリティ/コンプライアンス センターの電子情報開示ケースの保留リストと保持ポリシーなどのツールを使ってメールボックスを保留にすると、自動拡張アーカイブ内のコンテンツも保留になります。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-167">**Retention** - When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the security and compliance center, content located in an auto-expanded archive is also placed on hold.</span></span>
    
- <span data-ttu-id="cdf1d-168">**メッセージング レコード管理 (MRM)** - Exchange Online の MRM 削除ポリシーを使って期限切れのメールボックス アイテムを完全に削除した場合、自動拡張アーカイブにある期限切れアイテムも削除されます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-168">**Messaging records management (MRM)** - If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>
    
- <span data-ttu-id="cdf1d-169">**インポート サービス** - Office 365 のインポート サービスを使うと、ユーザーの自動拡張アーカイブに PST ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-169">**Import service** - You can use the Office 365 Import service to import PST files to a user's auto-expanded archive.</span></span> <span data-ttu-id="cdf1d-170">PST ファイルの最大 100 GB のデータをユーザーのアーカイブ メールボックスにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-170">You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span> 

## <a name="more-information"></a><span data-ttu-id="cdf1d-171">詳細情報</span><span class="sxs-lookup"><span data-stu-id="cdf1d-171">More information</span></span>

<span data-ttu-id="cdf1d-172">自動拡張アーカイブについての技術的な詳細については、「[Office 365: 自動拡張アーカイブに関する FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdf1d-172">For more technical details about auto-expanding archiving, see [Office 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>
