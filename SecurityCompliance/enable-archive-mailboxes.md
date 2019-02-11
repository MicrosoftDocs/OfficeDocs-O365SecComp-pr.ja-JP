---
title: Office 365 のセキュリティ、アーカイブ メールボックスを有効にする&amp;コンプライアンス センター
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: Office 365 のセキュリティを使用して、&amp;コンプライアンス ・ センター要件をサポートして、組織のメッセージの保存、電子的証拠開示、アーカイブ メールボックスを有効にします。
ms.openlocfilehash: 1c290cf19b396221dac702efd1395911e8a51631
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "28327099"
---
# <a name="enable-archive-mailboxes-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="e5f1e-103">Office 365 のセキュリティ、アーカイブ メールボックスを有効にする&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="e5f1e-103">Enable archive mailboxes in the Office 365 Security &amp; Compliance Center</span></span>
  
<span data-ttu-id="e5f1e-p101">(インプレース アーカイブとも呼ばれます)、Office 365 のアーカイブでは、追加のメールボックスの記憶域を持つユーザーを提供します。アーカイブ メールボックスを有効にすると、ユーザーがアクセスして、Microsoft Outlook を使用して、アーカイブ メールボックスにメッセージを格納し、Outlook Web アプリケーションのユーザーも移動したり、プライマリ メールボックスとアーカイブ メールボックス間でメッセージをコピーします。削除済みアイテムの回復ツールを使用して、アーカイブ メールボックスの回復可能なアイテム] フォルダーから削除済みアイテムを回復、こともできます。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p101">Archiving in Office 365 (also called In-Place Archiving) provides users with additional mailbox storage space. After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook Web App. Users can also move or copy messages between their primary mailbox and their archive mailbox. They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="e5f1e-p102">Office 365 は、無制限の量の拡大の自動アーカイブ機能により、アーカイブ ・ ストレージを提供します。アーカイブの自動拡張がオンにし、ユーザーのアーカイブ メールボックス内の最初の記憶域のクォータに達すると、Office 365 は自動的に追加の記憶域を追加します。つまりユーザーは、メールボックスのストレージ容量が不足実行しないし、最初に管理した後は何もする必要はありませんが、アーカイブ メールボックスを有効にして、組織のアーカイブの自動拡張を有効にします。詳細については、 [Office 365 で無制限のアーカイブの概要](unlimited-archiving.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p102">Office 365 provides an unlimited amount of archive storage with the auto-expanding archiving feature. When auto-expanding archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space. This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization. For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="e5f1e-112">始める前に</span><span class="sxs-lookup"><span data-stu-id="e5f1e-112">Before you begin</span></span>

<span data-ttu-id="e5f1e-p103">メール受信者の役割を割り当てる Exchange オンラインを有効にするか、アーカイブ メールボックスを無効にする必要があります。既定では、この役割は Exchange 管理センターで [**アクセス許可**] ページで、受信者の管理と組織管理の役割グループに割り当てられます。セキュリティの**アーカイブ**ページが表示されないかどうかは&amp;コンプライアンスを中央揃え、必要なアクセス許可を割り当てるには、管理者に依頼します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p103">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes. By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. If you don't see the **Archive** page in the Security &amp; Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="e5f1e-116">アーカイブ メールボックスの有効化</span><span class="sxs-lookup"><span data-stu-id="e5f1e-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="e5f1e-117">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="e5f1e-118">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="e5f1e-119">セキュリティ/コンプライアンス センターの左のウィンドウで、[**データ ガバナンス**]、[**アーカイブ**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-119">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="e5f1e-p104">**[アーカイブ]** ページが表示されます。**[アーカイブ メールボックス]** 列は、各ユーザーに対してアーカイブ メールボックスが有効か無効かを示します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p104">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="e5f1e-122">メールボックスの一覧で、アーカイブ メールボックスを有効にする対象のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![アーカイブ先のメールボックスを有効にする選択したユーザーの詳細ペインで [有効]](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="e5f1e-124">選択したユーザーの詳細ペインで [**有効**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="e5f1e-p105">アーカイブ先のメールボックスを有効にした場合、メールボックスに割り当てられているアーカイブ ・ ポリシーを超過したユーザーのメールボックス内のアイテムは新しいアーカイブ メールボックスに移動することを示す警告が表示されます。Exchange Online メールボックスに割り当てられているリテンション ・ ポリシーの一部である既定のアーカイブ ポリシーは、アイテムがメールボックスに配信や、ユーザーによって作成された日付より後の 2 年間、アーカイブ メールボックスにアイテムを移動します。詳細については、この資料の**詳細情報**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p105">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox. The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see the **More info** section in this article.</span></span> 
    
6. <span data-ttu-id="e5f1e-128">[**はい**] をクリックしてアーカイブ メールボックスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="e5f1e-p106">アーカイブ先のメールボックスを作成するのには数分かかる場合があります。作成されると、**アーカイブ先のメールボックス: 有効になっている**が詳細ペインで、選択したユーザーに対して表示されます。[**更新**] をクリックする必要があります![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif)の詳細ウィンドウの情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p106">It might take a few moments to create the archive mailbox. When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="e5f1e-p107">Shift キーまたは Ctrl キーを使用して、アーカイブ メールボックスが無効になっている複数のユーザーを選択して、アーカイブ メールボックスを一括して有効にすることもできます。複数のメールボックスを選択した後に、詳細ウィンドウで **[有効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="e5f1e-134">アーカイブ メールボックスを無効にする</span><span class="sxs-lookup"><span data-stu-id="e5f1e-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="e5f1e-p108">セキュリティ**の整理**] ページを使用することも&amp;ユーザーのアーカイブ メールボックスを無効にするコンプライアンス センターです。アーカイブ メールボックスを無効にした後は、それを無効にしてから 30 日内でユーザーのプライマリ メールボックスに再接続することができます。この例では、アーカイブ メールボックスの元の内容が復元されます。、30 日後元のアーカイブ メールボックスの内容は完全に削除し、回復することはできません。再度有効にした場合、アーカイブそれを無効にした後 30 日以上、新しいアーカイブ メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p108">You can also use the **Archive** page in the Security &amp; Compliance Center to disable a user's archive mailbox. After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it. In this case, the original contents of the archive mailbox are restored. After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered. So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="e5f1e-p109">メモの既定のアーカイブ ポリシーに割り当てられているユーザーのメールボックス アーカイブ メールボックスにアイテムを移動、日付の後の 2 年間、アイテムが配信されます。ユーザーのアーカイブ メールボックスを無効にした場合、メールボックス アイテムのアクションを実行しないと、ユーザーのプライマリ メールボックスのままになります。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p109">Note that the default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered. If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>
  
<span data-ttu-id="e5f1e-142">アーカイブ メールボックスを無効にするには。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="e5f1e-143">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="e5f1e-144">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="e5f1e-145">セキュリティ/コンプライアンス センターの左のウィンドウで、[**データ ガバナンス**]、[**アーカイブ**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-145">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="e5f1e-p110">**[アーカイブ]** ページが表示されます。**[アーカイブ メールボックス]** 列は、各ユーザーに対してアーカイブ メールボックスが有効か無効かを示します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="e5f1e-148">メールボックスの一覧で、アーカイブ メールボックスを無効にする対象のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="e5f1e-149">[詳細] ウィンドウで、**[無効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="e5f1e-150">アーカイブ先のメールボックスを再び有効にするのには 30 日が表示されると、後 30 日間アーカイブ内のすべての情報はすべて削除のことを示す警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-150">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="e5f1e-151">**[はい]** をクリックしてアーカイブ メールボックスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="e5f1e-p111">アーカイブ メールボックスを無効にするのには数分かかる場合があります。無効にすると、**アーカイブ先のメールボックス: 無効になっている**が詳細ペインで、選択したユーザーに対して表示されます。[**更新**] をクリックする必要があります![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif)の詳細ウィンドウの情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p111">It might take a few moments to disable the archive mailbox. When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="e5f1e-p112">Shift キーまたは Ctrl キーを使用して、アーカイブ メールボックスが有効になっている複数のユーザーを選択して、アーカイブ メールボックスを一括して無効にすることもできます。複数のメールボックスを選択した後に、詳細ウィンドウで **[無効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="e5f1e-157">Exchange オンライン PowerShell を使用して有効にするか、アーカイブ メールボックスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-157">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="e5f1e-p113">アーカイブ メールボックスを有効にするのに Exchange オンライン PowerShell を使用することもできます。PowerShell を使用する主な理由は、できることを迅速にすべてのユーザーのアーカイブ メールボックスの組織です。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p113">You can also use Exchange Online PowerShell to enable archive mailboxes. The primary reason to use PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="e5f1e-p114">最初のステップは、オンラインの PowerShell を Exchange に接続するためです。手順については、 [Exchange オンライン PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p114">The first step is to connect to Exchange Online PowerShell. For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="e5f1e-162">Exchange Online に接続して後、を有効にするか、アーカイブ メールボックスを無効にするのには、次のセクションでコマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-162">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="e5f1e-163">アーカイブ メールボックスの有効化</span><span class="sxs-lookup"><span data-stu-id="e5f1e-163">Enable archive mailboxes</span></span>

<span data-ttu-id="e5f1e-164">1 人のユーザーのアーカイブ メールボックスを有効にするのには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-164">Run the following command to enable the archive mailbox for a single user.</span></span>
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="e5f1e-165">(アーカイブ メールボックスは、現在有効になっていない)、組織内のすべてのユーザーのアーカイブ メールボックスを有効にするのには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-165">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a><span data-ttu-id="e5f1e-166">アーカイブ メールボックスの無効化</span><span class="sxs-lookup"><span data-stu-id="e5f1e-166">Disable archive mailboxes</span></span>

<span data-ttu-id="e5f1e-167">1 人のユーザーのアーカイブ メールボックスを無効にするのには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-167">Run the following command to disable the archive mailbox for a single user.</span></span>
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="e5f1e-168">(アーカイブ メールボックスを持つが現在有効になっている)、組織内のすべてのユーザーのアーカイブ メールボックスを無効にするのには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-168">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a><span data-ttu-id="e5f1e-169">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e5f1e-169">More information</span></span>
  
- <span data-ttu-id="e5f1e-p115">アーカイブ メールボックスでは、および、ユーザー、組織の保存、電子的証拠開示を満たすために、要件を待機します。たとえば、メールボックスの内容をユーザーのアーカイブ メールボックスに移動するのには、組織の Exchange の保持ポリシーを使用できます。セキュリティでのコンテンツの検索ツールを使用すると&amp;の特定のコンテンツ、ユーザーのアーカイブ メールボックスのユーザーのメールボックスを検索するコンプライアンス センターも検索されます。アーカイブ メールボックス内のアイテムが保持されるも、証拠保全を配置した場合、またはユーザーのメールボックスを Office 365 のリテンション ・ ポリシーを適用するとします。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p115">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements. For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox. When you use the Content Search tool in the Security &amp; Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched. And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="e5f1e-p116">アーカイブ メールボックスを有効にすると、ユーザーは、アーカイブ メールボックスにメッセージを保存できます。ユーザー メールボックスにアクセスできます、アーカイブ Microsoft Outlook と Outlook Web アプリケーションを使用して使用して、これらのクライアント アプリケーションのいずれか、ユーザーのアーカイブ メールボックスにメッセージを表示および移動したり、プライマリ メールボックスとアーカイブ メールボックス間でメッセージをコピーします。ユーザーは削除済みアイテムを削除済みアイテムの回復ツールを使用して、アーカイブ メールボックスの回復可能なアイテム] フォルダーから回復もできます。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p116">When an archive mailbox is enabled, users can store messages in their archive mailbox. Users can access their archive mailboxes by using Microsoft Outlook and Outlook Web App. Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox. Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
- <span data-ttu-id="e5f1e-p117">アーカイブ メールボックスを有効にした後、組織を利用して Exchange 保持される既定のポリシー (メッセージング レコード管理または MRM ポリシーとも呼ばれます) は、すべてのメールボックスに自動的に割り当てられているのです。アーカイブ メールボックスを有効にすると、Exchange のデフォルトの保存ポリシーに自動的には、次の。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-p117">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox. When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="e5f1e-180">2 年間以上経過したアイテムを、ユーザーのプライマリ メールボックスからアーカイブ メールボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-180">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="e5f1e-181">14 日以上経過したアイテムを、ユーザーのプライマリ メールボックスの [回復可能なアイテム] フォルダーから、アーカイブ メールボックスの [回復可能なアイテム] フォルダーへ自動的に移動します</span><span class="sxs-lookup"><span data-stu-id="e5f1e-181">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="e5f1e-182">アーカイブ メールボックスと Exchange のリテンション ・ ポリシーの詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-182">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
  
    
  - [<span data-ttu-id="e5f1e-183">保持タグおよびアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="e5f1e-183">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [<span data-ttu-id="e5f1e-184">既定の保持ポリシーでは、Exchange オンライン</span><span class="sxs-lookup"><span data-stu-id="e5f1e-184">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [<span data-ttu-id="e5f1e-185">Office 365 組織内のメールボックスのアーカイブと削除ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="e5f1e-185">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
