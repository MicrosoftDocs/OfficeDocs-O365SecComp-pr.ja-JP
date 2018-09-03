---
title: Office 365 の無制限のアーカイブの概要
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 自動拡張の詳細については Exchange Online のメールボックスの制限なしのアーカイブ ・ ストレージを提供するアーカイブを Office 365 で、です。
ms.openlocfilehash: a762a0fb8295a645957404c1c88881f40329f7a1
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782124"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="2da59-103">Office 365 の無制限のアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="2da59-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="2da59-p101">、Office 365 では、アーカイブ メールボックスは、メールボックスの記憶域を持つユーザーを提供します。ユーザーのアーカイブ メールボックスを有効にすると、最大で 100 GB の追加ストレージは使用できます。100 GB の記憶域のクォータに達すると、組織は、アーカイブ メールボックスに対する追加の記憶域を要求するマイクロソフトに連絡する必要があります。そうではないです。(*自動拡張のアーカイブ*と呼ばれる)、Office 365 で新しい無制限のアーカイブ機能では、無制限の量のアーカイブ メールボックス内のストレージを提供します。ここで、アーカイブ メールボックスの記憶域のクォータに達すると、Office 365 に自動的にサイズが大きくなりアーカイブのユーザーは、メールボックスのストレージ容量が不足実行しないと、管理者がアーカイブ メールボックスにストレージを追加を要求する必要はありません。.</span><span class="sxs-lookup"><span data-stu-id="2da59-p101">In Office 365, archive mailboxes provide users with additional mailbox storage space. After a user's archive mailbox is enabled, up to 100 GB of additional storage is available. When the 100 GB storage quota is reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox. That's no longer the case. The new unlimited archiving feature in Office 365 (called *auto-expanding archiving*) provides an unlimited amount of storage in archive mailboxes. Now, when the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>
  
<span data-ttu-id="2da59-110">自動拡張を有効にするための手順をアーカイブするには、 [Office 365 で無制限のアーカイブを有効にする](enable-unlimited-archiving.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2da59-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2da59-p102">アーカイブ自動拡張は、共有メールボックスをサポートします。共有されているメールボックスのアーカイブを有効にするには、Exchange オンライン計画 2 ライセンスまたは Exchange Online Archiving のライセンスを持つ Exchange オンライン計画 1 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2da59-p102">Auto-expanding archiving also supports shared mailboxes. To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span> 
  
## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="2da59-113">アーカイブの動作を自動展開する方法</span><span class="sxs-lookup"><span data-stu-id="2da59-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="2da59-p103">先ほど説明した、追加のメールボックスとしてユーザーのアーカイブ メールボックスを有効にすると、記憶領域が作成されます。アーカイブの自動拡張を有効にすると、Office 365 は、アーカイブ メールボックスのサイズを定期的にチェックします。アーカイブ メールボックスが格納域の制限に近づいたときに Office 365 は、アーカイブのための追加の記憶域を自動的に作成します。ユーザーがこの追加の記憶域の空き領域が不足実行する場合、Office 365 は、ユーザーのアーカイブにより多くのストレージ領域を追加します。追加のアーカイブ ・ ストレージを要求する] または [自動拡張のアーカイブを管理する必要はありません管理者は、自動的にこの処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="2da59-p103">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled. When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox. When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive. If the user runs out of this additional storage space, Office 365 adds more storage space to the user's archive. This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span> 
  
<span data-ttu-id="2da59-119">プロセスの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2da59-119">Here's a quick overview of the process.</span></span>
  
![自動拡張のアーカイブ ・ プロセスの概要](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. <span data-ttu-id="2da59-p104">ユーザーのメールボックスまたは共有されているメールボックスのアーカイブを有効にするとします。100 GB のストレージ ・ スペースでのアーカイブ先のメールボックスが作成され、アーカイブ先のメールボックスのクォータの警告は 90 GB に設定。</span><span class="sxs-lookup"><span data-stu-id="2da59-p104">Archiving is enabled for a user mailbox or a shared mailbox. An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>
    
2. <span data-ttu-id="2da59-p105">管理者は、メールボックスのアーカイブを自動拡張を使用できます。(回復可能な項目] フォルダーを含む) のアーカイブ メールボックスには、90 GB に達すると、自動拡張のアーカイブに変換し、Office 365 は、ストレージ容量をアーカイブに追加します。準備する追加の記憶域の最大 30 日間かかることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2da59-p105">An administrator enables auto-expanding archiving for the mailbox. Then, when the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive. Note that it can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
3. <span data-ttu-id="2da59-126">Office 365 は、自動的にアーカイブが必要な場合に多くの記憶領域を追加します。</span><span class="sxs-lookup"><span data-stu-id="2da59-126">Office 365 automatically adds more storage space to the archive when necessary.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2da59-p106">保留中にまたは Office 365 のリテンション ・ ポリシーに割り当てられているメールボックスは、アーカイブの自動拡張を有効にすると 110 GB にアーカイブ メールボックスの記憶域のクォータが向上します。同様に、アーカイブ警告クォータが 100 GB に増加します。</span><span class="sxs-lookup"><span data-stu-id="2da59-p106">If a mailbox is placed on hold or assigned to an Office 365 retention policy, the storage quota for the archive maibox is increased to 110 GB when auto-expanding archiving is enabled. Similarly, the archive warning quota is increased to 100 GB.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="2da59-129">どのような追加のアーカイブ ・ ストレージ ・ スペースに移動しますか。</span><span class="sxs-lookup"><span data-stu-id="2da59-129">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="2da59-p107">自動拡張のアーカイブ ・ ストレージの効率的な使用をするためには、フォルダーが移動します。Office 365 では、アーカイブに追加の記憶域を追加すると移動するフォルダーを決定します。フォルダーを移動すると、Outlook の [フォルダー一覧のアーカイブの部分に元のフォルダーの下のサブフォルダーが自動的に作成します。この新しいサブフォルダーは、移動されたアイテムを指しています。Office 365 を使用してこのフォルダーの名前を指定する名前付け規則では、**\<フォルダー名\>_yyyy (作成に mmm dd yyyy h_mm)**、どこで。</span><span class="sxs-lookup"><span data-stu-id="2da59-p107">To make efficient use of auto-expanding archive storage, folders might get moved. Office 365 determines which folders get moved when additional storage is added to the archive. When a folder is moved, a subfolder is automatically created under the original folder in the archive portion of the folder list in Outlook. This new subfolder points to the items that were moved. The naming convention that Office 365 uses to name this folder is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span> 
  
- <span data-ttu-id="2da59-135">**yyyy**は、フォルダー内のメッセージが受信された年です。</span><span class="sxs-lookup"><span data-stu-id="2da59-135">**yyyy** is the year the messages in the folder were received.</span></span> 
    
- <span data-ttu-id="2da59-136">**mmm dd yyyy h_m**はユーザーのタイム ゾーンと Outlook の [地域の設定に基づいて、UTC 形式で、Office 365 で、サブフォルダーが作成された日時です。</span><span class="sxs-lookup"><span data-stu-id="2da59-136">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span> 
    
<span data-ttu-id="2da59-137">自動展開されたアーカイブにメッセージを移動した後、前に、次のスクリーン ショットは、[フォルダー] ボックスの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="2da59-137">The following screen shots show a folder list before and after messages are moved in an auto-expanded archive.</span></span>
  
 <span data-ttu-id="2da59-138">**追加の記憶域を追加する前に**</span><span class="sxs-lookup"><span data-stu-id="2da59-138">**Before additional storage is added**</span></span>
  
![アーカイブの自動拡張を準備する前に、アーカイブ メールボックスのフォルダーの一覧](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 <span data-ttu-id="2da59-140">**追加の記憶域を追加した後**</span><span class="sxs-lookup"><span data-stu-id="2da59-140">**After additional storage is added**</span></span>
  
![アーカイブの自動拡張を準備した後、アーカイブ メールボックスのフォルダーの一覧](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="2da59-142">自動展開されたアーカイブ内のアイテムにアクセスするための outlook の要件</span><span class="sxs-lookup"><span data-stu-id="2da59-142">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="2da59-143">自動展開されたアーカイブに保存されているメッセージにアクセスするには、ユーザーが Outlook クライアントを次のいずれかを使用する必要が。</span><span class="sxs-lookup"><span data-stu-id="2da59-143">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>
  
- <span data-ttu-id="2da59-144">Windows 版 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2da59-144">Outlook 2016 for Windows</span></span>
    
- <span data-ttu-id="2da59-145">Web 上の Outlook</span><span class="sxs-lookup"><span data-stu-id="2da59-145">Outlook on the web</span></span> 
    
- <span data-ttu-id="2da59-146">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="2da59-146">Outlook 2016 for Mac</span></span> 
    
> [!NOTE]
> <span data-ttu-id="2da59-p108">Outlook 2013 のユーザーは、アーカイブ メールボックスに最初に格納されている項目にのみアクセスできます。追加のアーカイブ ・ ストレージに移動された項目にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2da59-p108">Outlook 2013 users can only access items that were originally stored in their archive mailbox. They won't be able to access items that are moved to additional archive storage.</span></span> 
  
<span data-ttu-id="2da59-149">Outlook または自動展開されたアーカイブに格納されているメッセージにアクセスできる web 上で Outlook を使用する場合の考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2da59-149">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>
  
- <span data-ttu-id="2da59-150">自動展開されたストレージ領域に移動するものも含め、アーカイブ メールボックス内の任意のフォルダーにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="2da59-150">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>
    
- <span data-ttu-id="2da59-p109">フォルダー自体を検索することによってのみ、追加のストレージ領域に移動されたアイテムを検索することができます。これは、検索範囲として、**現在のフォルダー**オプションを選択するフォルダーの一覧で、[アーカイブ] フォルダーを選択する必要ことを意味します。同様に、自動拡張領域内のフォルダーにサブフォルダーが含まれている場合がある場合各サブフォルダーを個別に検索します。</span><span class="sxs-lookup"><span data-stu-id="2da59-p109">You can search for items that were moved to an additional storage area only by searching the folder itself. This means you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope. Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span> 
    
- <span data-ttu-id="2da59-154">Outlook の項目をカウントし、自動拡張のアーカイブ (Outlook と Outlook web 上) の読み取り/未読のカウントは正確ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2da59-154">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web ) in an auto-expanded archive might not be accurate.</span></span>
    
- <span data-ttu-id="2da59-155">自動拡張記憶域の領域をポイントするサブフォルダー内のアイテムを削除することができますが、フォルダー自体を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="2da59-155">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>
    
- <span data-ttu-id="2da59-156">自動展開されたストレージ領域から削除されたアイテムを削除済みアイテムの回復機能を使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="2da59-156">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="2da59-157">自動拡張のアーカイブとその他の Office 365 のコンプライアンス機能</span><span class="sxs-lookup"><span data-stu-id="2da59-157">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="2da59-158">このセクションでは、自動拡張のアーカイブしその他の Office 365 のコンプライアンスとデータ管理機能との間の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="2da59-158">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>
  
- <span data-ttu-id="2da59-159">**電子的証拠開示**のコンテンツの検索、またはインプレース電子証拠開示、自動展開されたアーカイブに追加のストレージ領域など、Office 365 の電子的証拠開示ツールを使用する場合でも検索されます。</span><span class="sxs-lookup"><span data-stu-id="2da59-159">**eDiscovery** - When you use an Office 365 eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>
    
- <span data-ttu-id="2da59-160">**保存**- 保留中の Exchange Online の証拠保全などのツールを使用してメールボックスを配置するか、電子的証拠開示のケースを保持すると、リテンション ・ ポリシーで Office 365 のセキュリティ&amp;コンプライアンス センター、自動展開されたアーカイブ内にあるコンテンツも保留リストに配置されます。</span><span class="sxs-lookup"><span data-stu-id="2da59-160">**Retention** - When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the Office 365 Security &amp; Compliance Center, content located in an auto-expanded archive is also placed on hold.</span></span>
    
- <span data-ttu-id="2da59-161">**メッセージング レコードの管理 (MRM)** のメールボックスの有効期限が切れたアイテム、自動展開されたアーカイブ内にある期限切れのアイテムを削除するのには、Exchange Online の MRM 削除ポリシーを使用する場合も削除されます。</span><span class="sxs-lookup"><span data-stu-id="2da59-161">**Messaging records management (MRM)** - If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>
    
- <span data-ttu-id="2da59-p110">**サービスをインポートする**ためにユーザーの自動展開アーカイブ PST ファイルをインポートするのには Office 365 のインポート サービスを使用することができます。PST ファイルから最大 100 GB のデータをインポートするにはユーザーのアーカイブ メールボックスにします。</span><span class="sxs-lookup"><span data-stu-id="2da59-p110">**Import service** - You can use the Office 365 Import service to import PST files to a user's auto-expanded archive. You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span> 

## <a name="more-information"></a><span data-ttu-id="2da59-164">詳細情報</span><span class="sxs-lookup"><span data-stu-id="2da59-164">More information</span></span>

<span data-ttu-id="2da59-165">技術的な詳細については、自動拡張、アーカイブを参照してください[Office 365: 自動拡張のアーカイブに関する FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)。</span><span class="sxs-lookup"><span data-stu-id="2da59-165">For more technical details about auto-expanding archiving, see [Office 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>