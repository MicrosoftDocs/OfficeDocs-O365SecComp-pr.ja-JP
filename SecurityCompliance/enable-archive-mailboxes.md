---
title: セキュリティ/コンプライアンス センターでアーカイブ メールボックスを有効にする
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
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
description: Office 365 のセキュリティ/コンプライアンス センターを使用して、組織でのメッセージの保持、電子情報開示、保留に関する要件をサポートするためにアーカイブ メールボックスを有効にします。
ms.openlocfilehash: 5cf399b311b6c342aff2d84477edaa945f8e0cd4
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153289"
---
# <a name="enable-archive-mailboxes-in-the-security--compliance-center"></a><span data-ttu-id="751d4-103">セキュリティ/コンプライアンス センターでアーカイブ メールボックスを有効にする</span><span class="sxs-lookup"><span data-stu-id="751d4-103">Enable archive mailboxes in the Security &  Compliance Center</span></span>
  
<span data-ttu-id="751d4-104">Office 365 でのアーカイブ (インプレース アーカイブとも呼ばれます) では、追加のメールボックスの記憶域がユーザーに提供されます。</span><span class="sxs-lookup"><span data-stu-id="751d4-104">Archiving in Exchange Online (called In-Place Archiving) provides users with additional mailbox storage space.</span></span> <span data-ttu-id="751d4-105">アーカイブ メールボックスを有効にすると、ユーザーは Microsoft Outlook と Outlook on the web (以前の Outlook Web App) を使用してアーカイブ メールボックスのメッセージにアクセスし、保存することができます。</span><span class="sxs-lookup"><span data-stu-id="751d4-105">After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="751d4-106">ユーザーは、自分のプライマリ メールボックスとアーカイブ メールボックスの間でメッセージを移動したりコピーしたりもできます。</span><span class="sxs-lookup"><span data-stu-id="751d4-106">Users can view an archive mailbox and move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="751d4-107">ユーザーはまた、削除済みアイテムの復元ツールを使用して、アーカイブ メールボックスの [回復可能なアイテム] フォルダーから削除済みのアイテムを復元できます。</span><span class="sxs-lookup"><span data-stu-id="751d4-107">Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="751d4-108">自動拡張アーカイブ機能により、Office 365 では無制限のアーカイブ記憶域が提供されています。</span><span class="sxs-lookup"><span data-stu-id="751d4-108">Office 365 provides an unlimited amount of archive storage with the auto-expanding archiving feature.</span></span> <span data-ttu-id="751d4-109">自動拡張アーカイブが有効な状態で、ユーザーのアーカイブメールボックスの記憶域クォータの初期値に達すると、Office 365 は追加の記憶域を自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="751d4-109">When auto-expanding archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space.</span></span> <span data-ttu-id="751d4-110">つまり、管理者が最初にアーカイブ メールボックスを有効にし、自動拡張アーカイブを組織で有効にしておくと、ユーザーのメールボックスの記憶域が足りなくなることも、管理者による管理の必要もなくなります。</span><span class="sxs-lookup"><span data-stu-id="751d4-110">This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization.</span></span> <span data-ttu-id="751d4-111">詳細については、「[Office 365 での無制限アーカイブの概要](unlimited-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="751d4-111">For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="751d4-112">始める前に</span><span class="sxs-lookup"><span data-stu-id="751d4-112">Before you begin</span></span>

<span data-ttu-id="751d4-113">アーカイブ メールボックスを有効または無効にするには、Exchange Online でメール受信者役割が自分に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="751d4-113">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes.</span></span> <span data-ttu-id="751d4-114">既定では、この役割は、Exchange 管理センターの [**アクセス許可**] ページで受信者管理役割グループまたは組織管理役割グループに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="751d4-114">By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="751d4-115">セキュリティ/コンプライアンス センターの [**アーカイブ**] ページが表示されない場合、必要なアクセス許可を自分に割り当ててもらうよう管理者に依頼します。</span><span class="sxs-lookup"><span data-stu-id="751d4-115">If you don't see the **Archive** page in the Security & Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="751d4-116">アーカイブ メールボックスの有効化</span><span class="sxs-lookup"><span data-stu-id="751d4-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="751d4-117">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="751d4-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="751d4-118">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="751d4-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="751d4-119">セキュリティ/コンプライアンス センターの左のウィンドウで、[**データ ガバナンス**] \> [**アーカイブ**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="751d4-119">In the left pane of the Security  Compliance Center, click Data governance  Archive.</span></span>
    
    <span data-ttu-id="751d4-120">[**アーカイブ**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="751d4-120">The **Archive** page is displayed.</span></span> <span data-ttu-id="751d4-121">[**アーカイブ メールボックス**] 列は、各ユーザーに対してアーカイブ メールボックスが有効か無効かを示します。</span><span class="sxs-lookup"><span data-stu-id="751d4-121">The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="751d4-122">メールボックスの一覧で、アーカイブ メールボックスを有効にする対象のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="751d4-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![アーカイブ メールボックスを有効にするには、選択したユーザーの詳細ウィンドウで [有効にする] をクリックします。](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="751d4-124">選択したユーザーの [詳細] ウィンドウで、[**有効化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="751d4-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="751d4-125">アーカイブ メールボックスを有効にすると、ユーザーのメールボックス内にあるメールボックスに割り当てられているアーカイブ ポリシーより古いアイテムは、新しいアーカイブ メールボックスに移動されるという警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="751d4-125">A warning is displayed saying that if you enable the archive mailbox, items in the user’s mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox.</span></span> <span data-ttu-id="751d4-126">アイテムがメールボックスに配信またはユーザーによって作成された日付から 2 年間経過すると、Exchange Online のメールボックスに割り当てられているアイテム保持ポリシーの一部である既定のアーカイブ ポリシーにより、アイテムはアーカイブ メールボックスに移動されます。</span><span class="sxs-lookup"><span data-stu-id="751d4-126">As previously explained, the default archive policy that is part of the retention policy assigned to ExchangeOnline mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="751d4-127">詳細については、この記事の「**詳細情報**」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="751d4-127">For more information, see the  **Web fonts** section in this article.</span></span> 
    
6. <span data-ttu-id="751d4-128">[**はい**] をクリックしてアーカイブ メールボックスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="751d4-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="751d4-129">アーカイブ メールボックスの作成にはしばらくかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="751d4-129">It might take a few moments to create the archive mailbox.</span></span> <span data-ttu-id="751d4-130">作成されると、選択したユーザーの詳細ウィンドウに [**アーカイブ メールボックス: 有効**] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="751d4-130">When it’s created, **Archive mailbox: enabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="751d4-131">詳細ウィンドウの情報を更新するには、[**更新**] ![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif) をクリックする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="751d4-131">You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="751d4-p107">Shift キーまたは Ctrl キーを使用して、アーカイブ メールボックスが無効になっている複数のユーザーを選択して、アーカイブ メールボックスを一括して有効にすることもできます。複数のメールボックスを選択した後に、詳細ウィンドウで **[有効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="751d4-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="751d4-134">アーカイブ メールボックスを無効にする</span><span class="sxs-lookup"><span data-stu-id="751d4-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="751d4-135">ユーザーのアーカイブ メールボックスを無効にするために、セキュリティ/コンプライアンス センターの [**アーカイブ**] ページを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="751d4-135">You can also use the **Archive** page in the Security & Compliance Center to disable a user's archive mailbox.</span></span> <span data-ttu-id="751d4-136">アーカイブ メールボックスを無効にしてから 30 日以内なら、ユーザーのプライマリ メールボックスにそれを再接続できます。</span><span class="sxs-lookup"><span data-stu-id="751d4-136">After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it.</span></span> <span data-ttu-id="751d4-137">この場合、アーカイブ メールボックスの元の内容が復元されます。</span><span class="sxs-lookup"><span data-stu-id="751d4-137">In this case, the original contents of the archive mailbox are restored.</span></span> <span data-ttu-id="751d4-138">30 日後には、元のアーカイブ メールボックスの内容は完全に削除され、回復不可能になります。</span><span class="sxs-lookup"><span data-stu-id="751d4-138">After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered.</span></span> <span data-ttu-id="751d4-139">したがって、アーカイブを無効にした後、30 日を超えてから再度有効にすると、新しいアーカイブ メールボックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="751d4-139">So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="751d4-140">ユーザーのメールボックスに割り当てられる既定のアーカイブ ポリシーは、アイテムが配信された日付から 2 年間後にアイテムをアーカイブ メールボックスに移動する点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="751d4-140">As previously explained, the default archive policy assigned to users’ mailboxes moves items to the archive mailbox two years after the date the item is delivered.</span></span> <span data-ttu-id="751d4-141">ユーザーのアーカイブ メールボックスを無効にすると、メールボックスのアイテムに対してアクションは何も実行されず、そのままユーザーのプライマリ メールボックスに残ります。</span><span class="sxs-lookup"><span data-stu-id="751d4-141">If you disable a user’s archive mailbox, no action will be taken on mailbox items and they will remain in the user’s primary mailbox.</span></span>
  
<span data-ttu-id="751d4-142">アーカイブ メールボックスを無効にするには: </span><span class="sxs-lookup"><span data-stu-id="751d4-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="751d4-143">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="751d4-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="751d4-144">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="751d4-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="751d4-145">セキュリティ/コンプライアンス センターの左のウィンドウで、[**データ ガバナンス**] \> [**アーカイブ**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="751d4-145">In the left pane of the Security  Compliance Center, click Data governance  Archive.</span></span>
    
    <span data-ttu-id="751d4-p110">**[アーカイブ]** ページが表示されます。**[アーカイブ メールボックス]** 列は、各ユーザーに対してアーカイブ メールボックスが有効か無効かを示します。</span><span class="sxs-lookup"><span data-stu-id="751d4-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="751d4-148">メールボックスの一覧で、アーカイブ メールボックスを無効にする対象のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="751d4-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="751d4-149">[詳細] ウィンドウで、**[無効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="751d4-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="751d4-150">30 日以内であればアーカイブ メールボックスを再度有効にでき、30 日が経過するとアーカイブ内のすべての情報が完全に削除されることを示す警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="751d4-150">A warning message is displayed saying that you'll have 30 days  to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="751d4-151">
            \*\*[はい]\*\* をクリックしてアーカイブ メールボックスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="751d4-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="751d4-152">アーカイブ メールボックスの無効化にはしばらくかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="751d4-152">It might take a few moments to disable the archive mailbox.</span></span> <span data-ttu-id="751d4-153">無効になると、選択したユーザーの詳細ウィンドウに [**アーカイブ メールボックス: 無効]** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="751d4-153">When it’s disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="751d4-154">詳細ウィンドウの情報を更新するには、[**更新**] ![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif) をクリックする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="751d4-154">You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="751d4-p112">Shift キーまたは Ctrl キーを使用して、アーカイブ メールボックスが有効になっている複数のユーザーを選択して、アーカイブ メールボックスを一括して無効にすることもできます。複数のメールボックスを選択した後に、詳細ウィンドウで **[無効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="751d4-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="751d4-157">Exchange Online PowerShell を使用してアーカイブ メールボックスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="751d4-157">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="751d4-158">アーカイブ メールボックスを有効にするには、PowerShell を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="751d4-158">You can use the Exchange admin center (EAC) or Windows PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="751d4-159">PowerShell を使用する主な理由は、組織内のすべてのユーザーのためにアーカイブ メールボックスをすばやく有効にできるということです。</span><span class="sxs-lookup"><span data-stu-id="751d4-159">The primary reason to use Windows PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="751d4-160">最初の手順は、Exchange Online PowerShell へ接続することです。</span><span class="sxs-lookup"><span data-stu-id="751d4-160">The first step is to connect to your Exchange Online organization using Windows PowerShell.</span></span> <span data-ttu-id="751d4-161">手順については、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="751d4-161">For instructions, see [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="751d4-162">Exchange Online に接続したら、次のセクションのコマンドを実行してアーカイブメール ボックスを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="751d4-162">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="751d4-163">アーカイブ メールボックスの有効化</span><span class="sxs-lookup"><span data-stu-id="751d4-163">Enable archive mailboxes</span></span>

<span data-ttu-id="751d4-164">特定のユーザーのアーカイブ メールボックスを有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="751d4-164">Run the following command to enable the archive mailbox for a single user.</span></span>
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="751d4-165">組織内の、アーカイブ メールボックスが現在有効になっていないすべてのユーザーについてアーカイブ メールボックスを有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="751d4-165">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a><span data-ttu-id="751d4-166">アーカイブ メールボックスの無効化</span><span class="sxs-lookup"><span data-stu-id="751d4-166">Disable archive mailboxes</span></span>

<span data-ttu-id="751d4-167">特定のユーザーのアーカイブメールボックスを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="751d4-167">Run the following command to disable the archive mailbox for a single user.</span></span>
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="751d4-168">組織内の、アーカイブ メールボックスが現在有効になっているすべてのユーザーについてアーカイブ メールボックスを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="751d4-168">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a><span data-ttu-id="751d4-169">詳細情報</span><span class="sxs-lookup"><span data-stu-id="751d4-169">More information</span></span>
  
- <span data-ttu-id="751d4-170">アーカイブ メールボックスが有効になっている場合、ユーザーはメッセージをアーカイブ メールボックスに保存できます。</span><span class="sxs-lookup"><span data-stu-id="751d4-170">When their archive mailbox  is enabled, users can store messages in their archive mailbox (also called an In-Place Archive).</span></span> <span data-ttu-id="751d4-171">ユーザーは、Microsoft Outlook と Outlook on the web を使用してアーカイブ メールボックスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="751d4-171">Users can access their archive mailboxes by using Outlook and Outlook Web App.</span></span> <span data-ttu-id="751d4-172">これらのクライアント アプリケーションのいずれかを使用して、ユーザーは自分のアーカイブ メールボックスでメッセージを表示したり、プライマリ メールボックスとアーカイブ メールボックス間でメッセージを移動またはコピーできます。</span><span class="sxs-lookup"><span data-stu-id="751d4-172">Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="751d4-173">また、ユーザーは削除済みアイテム復元ツール使用して、アーカイブ メールボックスの [回復可能なアイテム] フォルダーから削除済みのアイテムを復元できます。</span><span class="sxs-lookup"><span data-stu-id="751d4-173">Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span>

   <span data-ttu-id="751d4-174">インプレース アーカイブをサポートしている Outlook のライセンスの一覧については、「[Outlook の Exchange 機能に関するライセンス要件](https://support.office.com/article/outlook-license-requirements-for-exchange-features-46b6b7c5-c3ca-43e5-8424-1e2807917c99)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="751d4-174">For a list of Outlook licenses that support In-Place Archiving, see [Outlook license requirements for Exchange features](https://support.office.com/article/outlook-license-requirements-for-exchange-features-46b6b7c5-c3ca-43e5-8424-1e2807917c99).</span></span>

- <span data-ttu-id="751d4-175">インプレース アーカイブは、組織のアイテム保持、電子情報開示、および保留に関する要件を管理者やユーザーが満たすためのサポートをします。</span><span class="sxs-lookup"><span data-stu-id="751d4-175">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements.</span></span> <span data-ttu-id="751d4-176">たとえば、組織の Exchange アイテム保持ポリシーを使用して、メールボックスの内容をユーザーのアーカイブ メールボックスに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="751d4-176">You can use your organization's mailbox retention policy to move mailbox content to users' archive mailbox.</span></span> <span data-ttu-id="751d4-177">セキュリティ/コンプライアンス センターでコンテンツ検索ツールを使用してユーザーのメールボックスで特定のコンテンツを検索するすると、ユーザーのアーカイブ メールボックスも検索されます。</span><span class="sxs-lookup"><span data-stu-id="751d4-177">When you use the Content Search tool in the Security & Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched.</span></span> <span data-ttu-id="751d4-178">また、ユーザーのメールボックスに訴訟ホールドを配置したり Office 365 アイテム保持ポリシーを適用したりすると、アーカイブ メールボックス内のアイテムも保持されます。</span><span class="sxs-lookup"><span data-stu-id="751d4-178">And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="751d4-179">アーカイブ メールボックスを有効にした後は、組織では、すべてのメールボックスに自動的に割り当てられる 既定の Exchange アイテム保持ポリシー (メッセージング レコード管理 (MRM) ポリシーとも呼ばれています) を活用できます。</span><span class="sxs-lookup"><span data-stu-id="751d4-179">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox.</span></span> <span data-ttu-id="751d4-180">アーカイブ メールボックスを有効にすると、既定の Exchange アイテム保持ポリシーは自動的に次を行います。</span><span class="sxs-lookup"><span data-stu-id="751d4-180">When an archive mailbox is enabled, the default retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="751d4-181">2 年間以上経過したアイテムを、ユーザーのプライマリ メールボックスからアーカイブ メールボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="751d4-181">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="751d4-182">14 日以上経過したアイテムを、ユーザーのプライマリ メールボックスの [回復可能なアイテム] フォルダーから、アーカイブ メールボックスの [回復可能なアイテム] フォルダーへ自動的に移動します</span><span class="sxs-lookup"><span data-stu-id="751d4-182">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="751d4-183">アーカイブ メールボックスと Exchange アイテム保持ポリシーの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="751d4-183">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
    
  - [<span data-ttu-id="751d4-184">保持タグおよびアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="751d4-184">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - <span data-ttu-id="751d4-185">[Exchange Online の既定のアイテム保持ポリシー](https://go.microsoft.com/fwlink/?linkid=839418)</span><span class="sxs-lookup"><span data-stu-id="751d4-185">[](https://go.microsoft.com/fwlink/?linkid=839418)Default Retention Policy in Exchange Online and Exchange Server</span></span>
    
  - <span data-ttu-id="751d4-186">[Office 365 の組織のメールボックスについて、アーカイブ削除ポリシーを設定する](set-up-an-archive-and-deletion-policy-for-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="751d4-186">[Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>
