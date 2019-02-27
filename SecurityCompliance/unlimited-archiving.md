---
title: Office 2010 での無制限アーカイブの概要 (機械翻訳) 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
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
description: Office 365 の自動拡張アーカイブについて説明します。これにより、Exchange Online メールボックスには無制限のアーカイブストレージが提供されます。
ms.openlocfilehash: 4ed1260cdf348d0bd29d88952ab69d234f044c26
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296650"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="7d761-103">Office 2010 での無制限アーカイブの概要 (機械翻訳) 365</span><span class="sxs-lookup"><span data-stu-id="7d761-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="7d761-p101">Office 365 では、アーカイブメールボックスにより、ユーザーはメールボックスの格納領域を追加できます。ユーザーのアーカイブメールボックスが有効になると、最大 100 GB の追加のストレージを使用できます。100 GB の記憶域クォータに到達すると、組織はアーカイブメールボックス用の追加の記憶域を要求するために Microsoft に連絡する必要がありました。そのようなケースはなくなりました。Office 365 の新しい無制限のアーカイブ機能 (*自動拡張アーカイブ*と呼ばれます) は、アーカイブメールボックスで無制限の記憶域を提供します。これで、アーカイブメールボックスの記憶域のクォータに到達すると、Office 365 によってアーカイブのサイズが自動的に増加します。つまり、ユーザーはメールボックスの記憶域を使い超えないようにし、管理者はアーカイブメールボックスに追加の記憶域を要求する必要がなくなります。.</span><span class="sxs-lookup"><span data-stu-id="7d761-p101">In Office 365, archive mailboxes provide users with additional mailbox storage space. After a user's archive mailbox is enabled, up to 100 GB of additional storage is available. When the 100 GB storage quota is reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox. That's no longer the case. The new unlimited archiving feature in Office 365 (called *auto-expanding archiving*) provides an unlimited amount of storage in archive mailboxes. Now, when the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>
  
<span data-ttu-id="7d761-110">自動拡張アーカイブを有効にするための詳細な手順については、「 [Office 365 で無制限アーカイブを有効にする](enable-unlimited-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d761-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7d761-p102">自動拡張アーカイブは、共有メールボックスもサポートします。共有メールボックスのアーカイブを有効にするには、exchange online プラン2ライセンスまたは exchange online プラン1ライセンスを持つ exchange online プラン1ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7d761-p102">Auto-expanding archiving also supports shared mailboxes. To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span> 
  
## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="7d761-113">自動拡張アーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="7d761-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="7d761-p103">前述したように、ユーザーのアーカイブメールボックスが有効になっている場合は、追加のメールボックスストレージ容量が作成されます。自動拡張アーカイブが有効になっている場合、Office 365 は定期的にアーカイブメールボックスのサイズをチェックします。アーカイブメールボックスが格納域の制限に近づいた場合、Office 365 によってアーカイブ用の追加の記憶域が自動的に作成されます。ユーザーがこの追加の記憶域を使い超えた場合は、Office 365 によってユーザーのアーカイブに格納領域が追加されます。この処理は自動的に行われるため、管理者は追加のアーカイブストレージを要求したり、自動拡張アーカイブを管理したりする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="7d761-p103">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled. When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox. When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive. If the user runs out of this additional storage space, Office 365 adds more storage space to the user's archive. This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span> 
  
<span data-ttu-id="7d761-119">プロセスの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7d761-119">Here's a quick overview of the process.</span></span>
  
![自動拡張アーカイブプロセスの概要](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. <span data-ttu-id="7d761-p104">ユーザーメールボックスまたは共有メールボックスに対してアーカイブが有効になっている。100 GB の容量のアーカイブメールボックスが作成され、アーカイブメールボックスの警告クォータは 90 GB に設定されます。</span><span class="sxs-lookup"><span data-stu-id="7d761-p104">Archiving is enabled for a user mailbox or a shared mailbox. An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>
    
2. <span data-ttu-id="7d761-p105">管理者は、メールボックスの自動拡張アーカイブを有効にします。その後、アーカイブメールボックス (回復可能なアイテムフォルダーを含む) が 90 GB に達すると、自動拡張アーカイブに変換され、Office 365 はアーカイブに記憶域スペースを追加します。追加のストレージ容量をプロビジョニングするには、最大で30日かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7d761-p105">An administrator enables auto-expanding archiving for the mailbox. Then, when the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive. Note that it can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
3. <span data-ttu-id="7d761-126">Office 365 では、必要に応じてアーカイブに格納領域が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="7d761-126">Office 365 automatically adds more storage space to the archive when necessary.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7d761-p106">メールボックスが保持されている場合、または Office 365 アイテム保持ポリシーに割り当てられている場合、自動拡張アーカイブが有効になっていると、アーカイブ maibox の記憶域クォータは 110 GB に増加します。同様に、アーカイブ警告クォータは 100 GB に増加します。</span><span class="sxs-lookup"><span data-stu-id="7d761-p106">If a mailbox is placed on hold or assigned to an Office 365 retention policy, the storage quota for the archive maibox is increased to 110 GB when auto-expanding archiving is enabled. Similarly, the archive warning quota is increased to 100 GB.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="7d761-129">その他のアーカイブ記憶域に移動することはありますか。</span><span class="sxs-lookup"><span data-stu-id="7d761-129">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="7d761-p107">自動拡張アーカイブストレージを効率的に使用するために、フォルダーが移動する場合があります。Office 365 は、アーカイブに追加の記憶域が追加されたときに移動するフォルダーを決定します。フォルダーが移動されると、Outlook のフォルダー一覧のアーカイブ部分にある元のフォルダーの下にサブフォルダーが自動的に作成されます。この新しいサブフォルダーは、移動されたアイテムを指します。Office 365 でこのフォルダーの名前付けに使用される命名規則は\*\* \<、フォルダー\>名 _ (mmm dd, yyyy h_mm で作成される)\*\* で、次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="7d761-p107">To make efficient use of auto-expanding archive storage, folders might get moved. Office 365 determines which folders get moved when additional storage is added to the archive. When a folder is moved, a subfolder is automatically created under the original folder in the archive portion of the folder list in Outlook. This new subfolder points to the items that were moved. The naming convention that Office 365 uses to name this folder is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span> 
  
- <span data-ttu-id="7d761-135">**yyyy**は、フォルダー内のメッセージが受信された年です。</span><span class="sxs-lookup"><span data-stu-id="7d761-135">**yyyy** is the year the messages in the folder were received.</span></span> 
    
- <span data-ttu-id="7d761-136">**mmm dd, yyyy h_m**は、Outlook のユーザーのタイムゾーンと地域の設定に基づいて、Office 365 によってサブフォルダーが作成された日時 (UTC 形式) です。</span><span class="sxs-lookup"><span data-stu-id="7d761-136">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span> 
    
<span data-ttu-id="7d761-137">次のスクリーンショットは、自動拡張アーカイブでメッセージが移動される前と後のフォルダー一覧を示しています。</span><span class="sxs-lookup"><span data-stu-id="7d761-137">The following screen shots show a folder list before and after messages are moved in an auto-expanded archive.</span></span>
  
 <span data-ttu-id="7d761-138">**追加の記憶域が追加される前**</span><span class="sxs-lookup"><span data-stu-id="7d761-138">**Before additional storage is added**</span></span>
  
![自動拡張アーカイブがプロビジョニングされる前のアーカイブメールボックスのフォルダー一覧](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 <span data-ttu-id="7d761-140">**追加の記憶域が追加された後**</span><span class="sxs-lookup"><span data-stu-id="7d761-140">**After additional storage is added**</span></span>
  
![自動拡張アーカイブがプロビジョニングされた後のアーカイブメールボックスのフォルダー一覧](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="7d761-142">自動拡張アーカイブのアイテムにアクセスするための Outlook の要件</span><span class="sxs-lookup"><span data-stu-id="7d761-142">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="7d761-143">自動拡張アーカイブに格納されているメッセージにアクセスするには、ユーザーは次のいずれかの Outlook クライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d761-143">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>
  
- <span data-ttu-id="7d761-144">outlook 2016 または outlook 2019 for Windows</span><span class="sxs-lookup"><span data-stu-id="7d761-144">Outlook 2016 or Outlook 2019 for Windows</span></span>
    
- <span data-ttu-id="7d761-145">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="7d761-145">Outlook on the web</span></span> 
    
- <span data-ttu-id="7d761-146">outlook 2016 または outlook 2019 for Mac</span><span class="sxs-lookup"><span data-stu-id="7d761-146">Outlook 2016 or Outlook 2019 for Mac</span></span> 
    
> [!NOTE]
> <span data-ttu-id="7d761-p108">Outlook 2013 ユーザーは、最初にアーカイブメールボックスに格納されたアイテムにのみアクセスできます。追加のアーカイブストレージに移動されたアイテムにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7d761-p108">Outlook 2013 users can only access items that were originally stored in their archive mailbox. They won't be able to access items that are moved to additional archive storage.</span></span> 
  
<span data-ttu-id="7d761-149">outlook または outlook on the web を使用して、自動拡張アーカイブに格納されているメッセージにアクセスするときに考慮する事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7d761-149">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>
  
- <span data-ttu-id="7d761-150">アーカイブメールボックス内の任意のフォルダーにアクセスできます。これには、自動拡張ストレージ領域に移動したものも含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d761-150">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>
    
- <span data-ttu-id="7d761-p109">その他のストレージ領域に移動されたアイテムは、フォルダー自体を検索することによってのみ検索できます。これは、検索範囲として [**現在のフォルダー** ] オプションを選択するには、フォルダー一覧の [アーカイブ] フォルダーを選択する必要があることを意味します。同様に、自動拡張記憶域領域内のフォルダーにサブフォルダーが含まれている場合は、各サブフォルダーを個別に検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d761-p109">You can search for items that were moved to an additional storage area only by searching the folder itself. This means you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope. Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span> 
    
- <span data-ttu-id="7d761-154">自動展開されたアーカイブでは、outlook および開封/未読のアイテム数 (outlook と web 上の outlook) は正確でないことがあります。</span><span class="sxs-lookup"><span data-stu-id="7d761-154">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web ) in an auto-expanded archive might not be accurate.</span></span>
    
- <span data-ttu-id="7d761-155">自動拡張記憶域をポイントするサブフォルダー内のアイテムを削除することはできますが、フォルダー自体を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="7d761-155">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>
    
- <span data-ttu-id="7d761-156">削除済みアイテムの回復機能を使用して、自動拡張ストレージ領域から削除されたアイテムを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="7d761-156">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="7d761-157">自動拡張アーカイブおよびその他の Office 365 コンプライアンス機能</span><span class="sxs-lookup"><span data-stu-id="7d761-157">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="7d761-158">このセクションでは、自動拡張アーカイブとその他の Office 365 コンプライアンスおよびデータガバナンス機能の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d761-158">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>
  
- <span data-ttu-id="7d761-159">**電子情報開示**-コンテンツ検索やインプレース電子情報開示などの Office 365 電子情報開示ツールを使用すると、自動拡張アーカイブ内の追加のストレージ領域も検索されます。</span><span class="sxs-lookup"><span data-stu-id="7d761-159">**eDiscovery** - When you use an Office 365 eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>
    
- <span data-ttu-id="7d761-160">**保持**-Office 365 セキュリティ & コンプライアンスセンターで、Exchange Online または電子情報開示のケースホールドやアイテム保持ポリシーなどのツールを使用してメールボックスを保留にした場合、自動拡張アーカイブに配置されているコンテンツも保留になっています。</span><span class="sxs-lookup"><span data-stu-id="7d761-160">**Retention** - When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the Office 365 Security & Compliance Center, content located in an auto-expanded archive is also placed on hold.</span></span>
    
- <span data-ttu-id="7d761-161">**メッセージングレコード管理 (mrm)** -Exchange Online で mrm 削除ポリシーを使用して、期限切れのメールボックスアイテムを完全に削除すると、自動拡張アーカイブにある期限切れのアイテムも削除されます。</span><span class="sxs-lookup"><span data-stu-id="7d761-161">**Messaging records management (MRM)** - If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>
    
- <span data-ttu-id="7d761-p110">**import service** -Office 365 インポートサービスを使用して、PST ファイルをユーザーの自動拡張アーカイブにインポートできます。PST ファイルからユーザーのアーカイブメールボックスに最大 100 GB のデータをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="7d761-p110">**Import service** - You can use the Office 365 Import service to import PST files to a user's auto-expanded archive. You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span> 

## <a name="more-information"></a><span data-ttu-id="7d761-164">詳細情報</span><span class="sxs-lookup"><span data-stu-id="7d761-164">More information</span></span>

<span data-ttu-id="7d761-165">自動拡張アーカイブの技術的な詳細については、「 [Office 365: 自動拡張アーカイブ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)に関する FAQ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d761-165">For more technical details about auto-expanding archiving, see [Office 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>