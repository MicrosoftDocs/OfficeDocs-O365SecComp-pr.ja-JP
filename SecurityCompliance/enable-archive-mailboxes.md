---
title: Office 365 セキュリティ&amp;コンプライアンスセンターでアーカイブメールボックスを有効にする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: Office 365 セキュリティ&amp;コンプライアンスセンターを使用して、組織のメッセージ保持、電子情報開示、および保持要件をサポートするアーカイブメールボックスを有効にします。
ms.openlocfilehash: 10e20d09c531d6758d8011030aea64a6c30cdf9b
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217287"
---
# <a name="enable-archive-mailboxes-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="95207-103">Office 365 セキュリティ&amp;コンプライアンスセンターでアーカイブメールボックスを有効にする</span><span class="sxs-lookup"><span data-stu-id="95207-103">Enable archive mailboxes in the Office 365 Security &amp; Compliance Center</span></span>
  
<span data-ttu-id="95207-p101">Office 365 のアーカイブ (インプレースアーカイブとも呼ばれます) を使用すると、ユーザーはメールボックスの格納域を追加することができます。アーカイブメールボックスを有効にすると、ユーザーは Microsoft outlook と web 上の outlook (旧称 outlook web App) を使用して、アーカイブメールボックス内のメッセージにアクセスして保存することができます。ユーザーは、プライマリメールボックスとアーカイブメールボックスの間でメッセージを移動またはコピーすることもできます。また、[削除済みアイテムの復元] ツールを使用して、アーカイブメールボックスの回復可能なアイテムフォルダーから削除済みアイテムを復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="95207-p101">Archiving in Office 365 (also called In-Place Archiving) provides users with additional mailbox storage space. After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook on the web (formerly known as Outlook Web App). Users can also move or copy messages between their primary mailbox and their archive mailbox. They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="95207-p102">Office 365 では、自動拡張アーカイブ機能を使用して、無制限の数のアーカイブストレージを提供しています。自動拡張アーカイブが有効になっている場合に、ユーザーのアーカイブメールボックス内の最初の記憶域のクォータに達すると、Office 365 は自動的に追加の記憶域を追加します。これは、ユーザーがメールボックスの記憶域を使い切ることがなく、アーカイブメールボックスを最初に有効にして、組織の自動拡張アーカイブを有効にした後でも、すべてを管理する必要がないことを意味します。詳細については、「 [Office 365 での無制限アーカイブの概要](unlimited-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95207-p102">Office 365 provides an unlimited amount of archive storage with the auto-expanding archiving feature. When auto-expanding archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space. This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization. For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="95207-112">始める前に</span><span class="sxs-lookup"><span data-stu-id="95207-112">Before you begin</span></span>

<span data-ttu-id="95207-p103">アーカイブメールボックスを有効または無効にするには、Exchange Online の Mail Recipients 役割を割り当てられている必要があります。既定では、この役割は Exchange 管理センターの [**アクセス許可**] ページの [受信者管理] および [組織の管理] 役割グループに割り当てられます。セキュリティ&amp; /コンプライアンスセンターに [**アーカイブ**] ページが表示されない場合は、必要なアクセス許可を割り当てるように管理者に依頼してください。</span><span class="sxs-lookup"><span data-stu-id="95207-p103">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes. By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. If you don't see the **Archive** page in the Security &amp; Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="95207-116">アーカイブ メールボックスの有効化</span><span class="sxs-lookup"><span data-stu-id="95207-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="95207-117">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="95207-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="95207-118">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="95207-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="95207-119">セキュリティ/コンプライアンス センターの左のウィンドウで、[**データ ガバナンス**]、[**アーカイブ**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="95207-119">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="95207-p104">**[アーカイブ]** ページが表示されます。**[アーカイブ メールボックス]** 列は、各ユーザーに対してアーカイブ メールボックスが有効か無効かを示します。</span><span class="sxs-lookup"><span data-stu-id="95207-p104">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="95207-122">メールボックスの一覧で、アーカイブ メールボックスを有効にする対象のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="95207-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![選択したユーザーの詳細ウィンドウで [有効] をクリックして、アーカイブメールボックスを有効にします。](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="95207-124">選択したユーザーの詳細ウィンドウで、[**有効**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95207-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="95207-p105">アーカイブメールボックスを有効にすると、メールボックスに割り当てられたアーカイブポリシーより古いユーザーのメールボックス内のアイテムが新しいアーカイブメールボックスに移動されることを示す警告が表示されます。Exchange Online メールボックスに割り当てられたアイテム保持ポリシーの一部である既定のアーカイブポリシーは、アイテムがメールボックスに配信された日付またはユーザーによって作成された後、2年後にアイテムをアーカイブメールボックスに移動します。詳細については、この記事の「**詳細**情報」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95207-p105">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox. The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see the **More info** section in this article.</span></span> 
    
6. <span data-ttu-id="95207-128">[**はい**] をクリックしてアーカイブ メールボックスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="95207-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="95207-p106">アーカイブメールボックスを作成するには、しばらく時間がかかる場合があります。この機能が作成されると、選択したユーザーの [詳細] ウィンドウに [**アーカイブメールボックス: 有効**] が表示されます。[更新] アイコン\*\*\*\* ![](media/O365-MDM-Policy-RefreshIcon.gif)をクリックして、詳細ウィンドウの情報を更新する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="95207-p106">It might take a few moments to create the archive mailbox. When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="95207-p107">Shift キーまたは Ctrl キーを使用して、アーカイブ メールボックスが無効になっている複数のユーザーを選択して、アーカイブ メールボックスを一括して有効にすることもできます。複数のメールボックスを選択した後に、詳細ウィンドウで **[有効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95207-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="95207-134">アーカイブ メールボックスを無効にする</span><span class="sxs-lookup"><span data-stu-id="95207-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="95207-p108">また、セキュリティ&amp;コンプライアンスセンターの [**アーカイブ**] ページを使用して、ユーザーのアーカイブメールボックスを無効にすることもできます。アーカイブメールボックスを無効にした後、そのメールボックスを無効にしてから30日以内に、ユーザーのプライマリメールボックスに再接続することができます。この場合、アーカイブメールボックスの元のコンテンツが復元されます。30日後、元のアーカイブメールボックスの内容は完全に削除され、回復することはできません。そのため、アーカイブを無効にした後、30日を超えて再度有効にすると、新しいアーカイブメールボックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="95207-p108">You can also use the **Archive** page in the Security &amp; Compliance Center to disable a user's archive mailbox. After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it. In this case, the original contents of the archive mailbox are restored. After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered. So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="95207-p109">ユーザーのメールボックスに割り当てられた既定のアーカイブポリシーによって、アイテムが配信された日付の2年後にアーカイブメールボックスにアイテムが移動されることに注意してください。ユーザーのアーカイブメールボックスを無効にすると、メールボックスアイテムに対して実行されるアクションはなく、ユーザーのプライマリメールボックスに残ります。</span><span class="sxs-lookup"><span data-stu-id="95207-p109">Note that the default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered. If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>
  
<span data-ttu-id="95207-142">アーカイブメールボックスを無効にするには:</span><span class="sxs-lookup"><span data-stu-id="95207-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="95207-143">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="95207-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="95207-144">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="95207-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="95207-145">セキュリティ/コンプライアンス センターの左のウィンドウで、[**データ ガバナンス**]、[**アーカイブ**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="95207-145">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="95207-p110">**[アーカイブ]** ページが表示されます。**[アーカイブ メールボックス]** 列は、各ユーザーに対してアーカイブ メールボックスが有効か無効かを示します。</span><span class="sxs-lookup"><span data-stu-id="95207-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="95207-148">メールボックスの一覧で、アーカイブ メールボックスを無効にする対象のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="95207-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="95207-149">[詳細] ウィンドウで、**[無効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95207-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="95207-150">アーカイブメールボックスを再度有効にするのに30日間が発生し、30日が経過すると、アーカイブ内のすべての情報が完全に削除されるという警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95207-150">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="95207-151">**[はい]** をクリックしてアーカイブ メールボックスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="95207-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="95207-p111">アーカイブメールボックスを無効にするには、しばらく時間がかかる場合があります。無効にすると、**アーカイブメールボックス: disabled**が、選択したユーザーの詳細ウィンドウに表示されます。[更新] アイコン\*\*\*\* ![](media/O365-MDM-Policy-RefreshIcon.gif)をクリックして、詳細ウィンドウの情報を更新する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="95207-p111">It might take a few moments to disable the archive mailbox. When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="95207-p112">Shift キーまたは Ctrl キーを使用して、アーカイブ メールボックスが有効になっている複数のユーザーを選択して、アーカイブ メールボックスを一括して無効にすることもできます。複数のメールボックスを選択した後に、詳細ウィンドウで **[無効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95207-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="95207-157">Exchange Online の PowerShell を使用してアーカイブメールボックスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="95207-157">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="95207-p113">また、Exchange Online PowerShell を使用して、アーカイブメールボックスを有効にすることもできます。PowerShell を使用する主な理由は、組織内のすべてのユーザーに対してアーカイブメールボックスをすばやく有効にできるということです。</span><span class="sxs-lookup"><span data-stu-id="95207-p113">You can also use Exchange Online PowerShell to enable archive mailboxes. The primary reason to use PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="95207-p114">最初の手順として、Exchange Online PowerShell に接続します。手順については、「 [Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95207-p114">The first step is to connect to Exchange Online PowerShell. For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="95207-162">Exchange Online に接続した後、以下のセクションのコマンドを実行して、アーカイブメールボックスを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="95207-162">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="95207-163">アーカイブ メールボックスの有効化</span><span class="sxs-lookup"><span data-stu-id="95207-163">Enable archive mailboxes</span></span>

<span data-ttu-id="95207-164">1人のユーザーのアーカイブメールボックスを有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="95207-164">Run the following command to enable the archive mailbox for a single user.</span></span>
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="95207-165">次のコマンドを実行して、組織内のすべてのユーザーのアーカイブメールボックスを有効にします (アーカイブメールボックスが現在有効になっていない場合)。</span><span class="sxs-lookup"><span data-stu-id="95207-165">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a><span data-ttu-id="95207-166">アーカイブ メールボックスの無効化</span><span class="sxs-lookup"><span data-stu-id="95207-166">Disable archive mailboxes</span></span>

<span data-ttu-id="95207-167">1人のユーザーのアーカイブメールボックスを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="95207-167">Run the following command to disable the archive mailbox for a single user.</span></span>
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="95207-168">次のコマンドを実行して、組織内のすべてのユーザーのアーカイブメールボックスを無効にします (アーカイブメールボックスが現在有効になっている場合)。</span><span class="sxs-lookup"><span data-stu-id="95207-168">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a><span data-ttu-id="95207-169">詳細情報</span><span class="sxs-lookup"><span data-stu-id="95207-169">More information</span></span>
  
- <span data-ttu-id="95207-p115">アーカイブメールボックスは、ユーザーが組織の保持、電子情報開示、およびホールドの要件を満たすのに役立ちます。たとえば、組織の Exchange アイテム保持ポリシーを使用して、メールボックスの内容をユーザーのアーカイブメールボックスに移動することができます。セキュリティ&amp; /コンプライアンスセンターのコンテンツ検索ツールを使用してユーザーのメールボックスで特定のコンテンツを検索すると、そのユーザーのアーカイブメールボックスも検索されます。また、訴訟ホールドを配置するか、Office 365 アイテム保持ポリシーをユーザーのメールボックスに適用すると、アーカイブメールボックス内のアイテムも保持されます。</span><span class="sxs-lookup"><span data-stu-id="95207-p115">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements. For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox. When you use the Content Search tool in the Security &amp; Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched. And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="95207-p116">アーカイブメールボックスが有効になっている場合、ユーザーはアーカイブメールボックスにメッセージを保存できます。ユーザーは、Microsoft outlook と web 上の outlook を使用して、アーカイブメールボックスにアクセスできます。これらのクライアントアプリケーションのいずれかを使用して、ユーザーはアーカイブメールボックス内のメッセージを表示したり、プライマリメールボックスとアーカイブメールボックスの間でメッセージを移動またはコピーしたりできます。ユーザーは、削除済みアイテムの回復ツールを使用して、アーカイブメールボックスの回復可能なアイテムフォルダーから削除済みアイテムを復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="95207-p116">When an archive mailbox is enabled, users can store messages in their archive mailbox. Users can access their archive mailboxes by using Microsoft Outlook and Outlook on the web. Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox. Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
- <span data-ttu-id="95207-p117">アーカイブメールボックスを有効にすると、組織は、すべてのメールボックスに自動的に割り当てられる既定の Exchange アイテム保持ポリシー (Messaging Records Management または mrm ポリシーとも呼ばれます) を利用できます。アーカイブメールボックスを有効にすると、既定の Exchange アイテム保持ポリシーでは次の処理が自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="95207-p117">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox. When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="95207-180">2 年間以上経過したアイテムを、ユーザーのプライマリ メールボックスからアーカイブ メールボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="95207-180">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="95207-181">14 日以上経過したアイテムを、ユーザーのプライマリ メールボックスの [回復可能なアイテム] フォルダーから、アーカイブ メールボックスの [回復可能なアイテム] フォルダーへ自動的に移動します</span><span class="sxs-lookup"><span data-stu-id="95207-181">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="95207-182">アーカイブメールボックスと Exchange アイテム保持ポリシーの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95207-182">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
  
    
  - [<span data-ttu-id="95207-183">保持タグおよびアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="95207-183">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [<span data-ttu-id="95207-184">Exchange Online の既定のアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="95207-184">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [<span data-ttu-id="95207-185">Office 365 組織のメールボックスのアーカイブおよび削除ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="95207-185">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
