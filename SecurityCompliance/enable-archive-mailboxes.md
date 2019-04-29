---
title: セキュリティ & コンプライアンスセンターでアーカイブメールボックスを有効にする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: Office 365 のセキュリティ & コンプライアンスセンターを使用して、組織のメッセージ保持、電子情報開示、および保持要件をサポートするアーカイブメールボックスを有効にします。
ms.openlocfilehash: f4f02e5107526f2f45b0a46579e0676b791f0dd1
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402925"
---
# <a name="enable-archive-mailboxes-in-the-security--compliance-center"></a><span data-ttu-id="74569-103">セキュリティ & コンプライアンスセンターでアーカイブメールボックスを有効にする</span><span class="sxs-lookup"><span data-stu-id="74569-103">Enable archive mailboxes in the Security & Compliance Center</span></span>
  
<span data-ttu-id="74569-104">Office 365 のアーカイブ (インプレースアーカイブとも呼ばれます) を使用すると、ユーザーはメールボックスの格納域を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="74569-104">Archiving in Office 365 (also called In-Place Archiving) provides users with additional mailbox storage space.</span></span> <span data-ttu-id="74569-105">アーカイブメールボックスを有効にすると、ユーザーは Microsoft outlook と web 上の outlook (旧称 outlook web App) を使用して、アーカイブメールボックス内のメッセージにアクセスして保存することができます。</span><span class="sxs-lookup"><span data-stu-id="74569-105">After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="74569-106">ユーザーは、プライマリメールボックスとアーカイブメールボックスの間でメッセージを移動またはコピーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="74569-106">Users can also move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="74569-107">また、[削除済みアイテムの復元] ツールを使用して、アーカイブメールボックスの回復可能なアイテムフォルダーから削除済みアイテムを復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="74569-107">They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="74569-108">Office 365 では、自動拡張アーカイブ機能を使用して、無制限の数のアーカイブストレージを提供しています。</span><span class="sxs-lookup"><span data-stu-id="74569-108">Office 365 provides an unlimited amount of archive storage with the auto-expanding archiving feature.</span></span> <span data-ttu-id="74569-109">自動拡張アーカイブが有効になっている場合に、ユーザーのアーカイブメールボックス内の最初の記憶域のクォータに達すると、Office 365 は自動的に追加の記憶域を追加します。</span><span class="sxs-lookup"><span data-stu-id="74569-109">When auto-expanding archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space.</span></span> <span data-ttu-id="74569-110">これは、ユーザーがメールボックスの記憶域を使い切ることがなく、アーカイブメールボックスを最初に有効にして、組織の自動拡張アーカイブを有効にした後でも、すべてを管理する必要がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="74569-110">This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization.</span></span> <span data-ttu-id="74569-111">詳しくは、「[Office 365 での無制限アーカイブの概要](unlimited-archiving.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="74569-111">For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="74569-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="74569-112">Before you begin</span></span>

<span data-ttu-id="74569-113">アーカイブメールボックスを有効または無効にするには、Exchange Online の Mail Recipients 役割を割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="74569-113">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes.</span></span> <span data-ttu-id="74569-114">既定では、この役割は Exchange 管理センターの [**アクセス許可**] ページの [受信者管理] および [組織の管理] 役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="74569-114">By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="74569-115">セキュリティ & コンプライアンスセンターに [**アーカイブ**] ページが表示されない場合は、必要なアクセス許可を割り当てるように管理者に依頼してください。</span><span class="sxs-lookup"><span data-stu-id="74569-115">If you don't see the **Archive** page in the Security & Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="74569-116">アーカイブ メールボックスの有効化</span><span class="sxs-lookup"><span data-stu-id="74569-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="74569-117">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="74569-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="74569-118">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="74569-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="74569-119">セキュリティ & コンプライアンスセンターの左側のウィンドウで、[ **Data ガバナンス** \> **アーカイブ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74569-119">In the left pane of the Security & Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="74569-120">**[アーカイブ]** ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74569-120">The **Archive** page is displayed.</span></span> <span data-ttu-id="74569-121">**[アーカイブ メールボックス]** 列は、各ユーザーに対してアーカイブ メールボックスが有効か無効かを示します。</span><span class="sxs-lookup"><span data-stu-id="74569-121">The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="74569-122">メールボックスの一覧で、アーカイブ メールボックスを有効にする対象のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="74569-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![選択したユーザーの詳細ウィンドウで [有効] をクリックして、アーカイブメールボックスを有効にします。](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="74569-124">選択したユーザーの詳細ウィンドウで、[**有効**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74569-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="74569-125">アーカイブメールボックスを有効にすると、メールボックスに割り当てられたアーカイブポリシーより古いユーザーのメールボックス内のアイテムが新しいアーカイブメールボックスに移動されることを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="74569-125">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox.</span></span> <span data-ttu-id="74569-126">Exchange Online メールボックスに割り当てられたアイテム保持ポリシーの一部である既定のアーカイブポリシーは、アイテムがメールボックスに配信された日付またはユーザーによって作成された後、2年後にアイテムをアーカイブメールボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="74569-126">The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="74569-127">詳細については、この記事の「**詳細**情報」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74569-127">For more information, see the **More info** section in this article.</span></span> 
    
6. <span data-ttu-id="74569-128">[**はい**] をクリックしてアーカイブ メールボックスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="74569-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="74569-129">アーカイブ メールボックスの作成にはしばらくかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="74569-129">It might take a few moments to create the archive mailbox.</span></span> <span data-ttu-id="74569-130">この機能が作成されると、選択したユーザーの [詳細] ウィンドウに [**アーカイブメールボックス: 有効**] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="74569-130">When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="74569-131">[更新] アイコン\*\*\*\* ![](media/O365-MDM-Policy-RefreshIcon.gif)をクリックして、詳細ウィンドウの情報を更新する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="74569-131">You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="74569-p107">Shift キーまたは Ctrl キーを使用して、アーカイブ メールボックスが無効になっている複数のユーザーを選択して、アーカイブ メールボックスを一括して有効にすることもできます。複数のメールボックスを選択した後に、詳細ウィンドウで **[有効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74569-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="74569-134">アーカイブ メールボックスを無効にする</span><span class="sxs-lookup"><span data-stu-id="74569-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="74569-135">セキュリティ & コンプライアンスセンターの [**アーカイブ**] ページを使用して、ユーザーのアーカイブメールボックスを無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="74569-135">You can also use the **Archive** page in the Security & Compliance Center to disable a user's archive mailbox.</span></span> <span data-ttu-id="74569-136">アーカイブ メールボックスを無効にしてから 30 日以内なら、ユーザーのプライマリ メールボックスにそれを再接続できます。</span><span class="sxs-lookup"><span data-stu-id="74569-136">After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it.</span></span> <span data-ttu-id="74569-137">この場合、アーカイブ メールボックスの元の内容が復元されます。</span><span class="sxs-lookup"><span data-stu-id="74569-137">In this case, the original contents of the archive mailbox are restored.</span></span> <span data-ttu-id="74569-138">30 日後、元のアーカイブ メールボックスの内容は完全に削除され、回復不可能になります。</span><span class="sxs-lookup"><span data-stu-id="74569-138">After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered.</span></span> <span data-ttu-id="74569-139">したがって、アーカイブを無効にした後、30 日を超えてから再度有効にすると、新しいアーカイブ メールボックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="74569-139">So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="74569-140">ユーザーのメールボックスに割り当てられた既定のアーカイブポリシーによって、アイテムが配信された日付の2年後にアーカイブメールボックスにアイテムが移動されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="74569-140">Note that the default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered.</span></span> <span data-ttu-id="74569-141">ユーザーのアーカイブメールボックスを無効にすると、メールボックスアイテムに対して実行されるアクションはなく、ユーザーのプライマリメールボックスに残ります。</span><span class="sxs-lookup"><span data-stu-id="74569-141">If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>
  
<span data-ttu-id="74569-142">アーカイブメールボックスを無効にするには:</span><span class="sxs-lookup"><span data-stu-id="74569-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="74569-143">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="74569-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="74569-144">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="74569-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="74569-145">セキュリティ & コンプライアンスセンターの左側のウィンドウで、[ **Data ガバナンス** \> **アーカイブ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74569-145">In the left pane of the Security & Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="74569-p110">**[アーカイブ]** ページが表示されます。**[アーカイブ メールボックス]** 列は、各ユーザーに対してアーカイブ メールボックスが有効か無効かを示します。</span><span class="sxs-lookup"><span data-stu-id="74569-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="74569-148">メールボックスの一覧で、アーカイブ メールボックスを無効にする対象のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="74569-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="74569-149">[詳細] ウィンドウで、**[無効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74569-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="74569-150">アーカイブメールボックスを再度有効にするのに30日間が発生し、30日が経過すると、アーカイブ内のすべての情報が完全に削除されるという警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74569-150">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="74569-151">**[はい]** をクリックしてアーカイブ メールボックスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="74569-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="74569-152">アーカイブ メールボックスの無効化にはしばらくかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="74569-152">It might take a few moments to disable the archive mailbox.</span></span> <span data-ttu-id="74569-153">無効にすると、**アーカイブメールボックス: disabled**が、選択したユーザーの詳細ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="74569-153">When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="74569-154">[更新] アイコン\*\*\*\* ![](media/O365-MDM-Policy-RefreshIcon.gif)をクリックして、詳細ウィンドウの情報を更新する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="74569-154">You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="74569-p112">Shift キーまたは Ctrl キーを使用して、アーカイブ メールボックスが有効になっている複数のユーザーを選択して、アーカイブ メールボックスを一括して無効にすることもできます。複数のメールボックスを選択した後に、詳細ウィンドウで **[無効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74569-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="74569-157">Exchange Online の PowerShell を使用してアーカイブメールボックスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="74569-157">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="74569-158">また、Exchange Online PowerShell を使用して、アーカイブメールボックスを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="74569-158">You can also use Exchange Online PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="74569-159">PowerShell を使用する主な理由は、組織内のすべてのユーザーに対してアーカイブメールボックスをすばやく有効にできるということです。</span><span class="sxs-lookup"><span data-stu-id="74569-159">The primary reason to use PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="74569-160">最初の手順として、Exchange Online PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="74569-160">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="74569-161">手順については、「 [Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74569-161">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="74569-162">Exchange Online に接続した後、以下のセクションのコマンドを実行して、アーカイブメールボックスを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="74569-162">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="74569-163">アーカイブ メールボックスの有効化</span><span class="sxs-lookup"><span data-stu-id="74569-163">Enable archive mailboxes</span></span>

<span data-ttu-id="74569-164">1人のユーザーのアーカイブメールボックスを有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="74569-164">Run the following command to enable the archive mailbox for a single user.</span></span>
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="74569-165">次のコマンドを実行して、組織内のすべてのユーザーのアーカイブメールボックスを有効にします (アーカイブメールボックスが現在有効になっていない場合)。</span><span class="sxs-lookup"><span data-stu-id="74569-165">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a><span data-ttu-id="74569-166">アーカイブメールボックスを無効にする</span><span class="sxs-lookup"><span data-stu-id="74569-166">Disable archive mailboxes</span></span>

<span data-ttu-id="74569-167">1人のユーザーのアーカイブメールボックスを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="74569-167">Run the following command to disable the archive mailbox for a single user.</span></span>
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="74569-168">次のコマンドを実行して、組織内のすべてのユーザーのアーカイブメールボックスを無効にします (アーカイブメールボックスが現在有効になっている場合)。</span><span class="sxs-lookup"><span data-stu-id="74569-168">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a><span data-ttu-id="74569-169">詳細情報</span><span class="sxs-lookup"><span data-stu-id="74569-169">More information</span></span>
  
- <span data-ttu-id="74569-170">アーカイブメールボックスが有効になっている場合、ユーザーはアーカイブメールボックスにメッセージを保存できます。</span><span class="sxs-lookup"><span data-stu-id="74569-170">When an archive mailbox is enabled, users can store messages in their archive mailbox.</span></span> <span data-ttu-id="74569-171">ユーザーは、Microsoft outlook と web 上の outlook を使用して、アーカイブメールボックスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="74569-171">Users can access their archive mailboxes by using Microsoft Outlook and Outlook on the web.</span></span> <span data-ttu-id="74569-172">これらのクライアント アプリケーションのいずれかを使用して、ユーザーは自分のアーカイブ メールボックスでメッセージを表示したり、プライマリ メールボックスとアーカイブ メールボックス間でメッセージを移動またはコピーできます。</span><span class="sxs-lookup"><span data-stu-id="74569-172">Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="74569-173">また、ユーザーは削除済みアイテム復元ツール使用して、アーカイブ メールボックスの [回復可能なアイテム] フォルダーから削除済みのアイテムを復元できます。</span><span class="sxs-lookup"><span data-stu-id="74569-173">Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span>

   <span data-ttu-id="74569-174">インプレースアーカイブをサポートする outlook ライセンスの一覧については、「 [Exchange の機能の outlook ライセンス要件](https://support.office.com/article/outlook-license-requirements-for-exchange-features-46b6b7c5-c3ca-43e5-8424-1e2807917c99)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74569-174">For a list of Outlook licenses that support In-Place Archiving, see [Outlook license requirements for Exchange features](https://support.office.com/article/outlook-license-requirements-for-exchange-features-46b6b7c5-c3ca-43e5-8424-1e2807917c99).</span></span>

- <span data-ttu-id="74569-175">アーカイブメールボックスは、ユーザーが組織の保持、電子情報開示、およびホールドの要件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="74569-175">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements.</span></span> <span data-ttu-id="74569-176">たとえば、組織の Exchange アイテム保持ポリシーを使用して、メールボックスの内容をユーザーのアーカイブメールボックスに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="74569-176">For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox.</span></span> <span data-ttu-id="74569-177">セキュリティ & コンプライアンスセンターのコンテンツ検索ツールを使用して、ユーザーのメールボックスで特定のコンテンツを検索すると、そのユーザーのアーカイブメールボックスも検索されます。</span><span class="sxs-lookup"><span data-stu-id="74569-177">When you use the Content Search tool in the Security & Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched.</span></span> <span data-ttu-id="74569-178">また、訴訟ホールドを配置するか、Office 365 アイテム保持ポリシーをユーザーのメールボックスに適用すると、アーカイブメールボックス内のアイテムも保持されます。</span><span class="sxs-lookup"><span data-stu-id="74569-178">And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="74569-179">アーカイブメールボックスを有効にすると、組織は、すべてのメールボックスに自動的に割り当てられる既定の Exchange アイテム保持ポリシー (Messaging Records Management または mrm ポリシーとも呼ばれます) を利用できます。</span><span class="sxs-lookup"><span data-stu-id="74569-179">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox.</span></span> <span data-ttu-id="74569-180">アーカイブメールボックスを有効にすると、既定の Exchange アイテム保持ポリシーでは次の処理が自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="74569-180">When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="74569-181">2 年間以上経過したアイテムを、ユーザーのプライマリ メールボックスからアーカイブ メールボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="74569-181">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="74569-182">14 日以上経過したアイテムを、ユーザーのプライマリ メールボックスの [回復可能なアイテム] フォルダーから、アーカイブ メールボックスの [回復可能なアイテム] フォルダーへ自動的に移動します</span><span class="sxs-lookup"><span data-stu-id="74569-182">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="74569-183">アーカイブメールボックスと Exchange アイテム保持ポリシーの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74569-183">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
    
  - [<span data-ttu-id="74569-184">保持タグおよびアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="74569-184">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [<span data-ttu-id="74569-185">Exchange Online の既定のアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="74569-185">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [<span data-ttu-id="74569-186">Office 365 組織のメールボックスのアーカイブおよび削除ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="74569-186">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
