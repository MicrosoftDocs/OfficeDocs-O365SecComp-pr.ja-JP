---
title: Office 365 組織のメールボックスのアーカイブおよび削除ポリシーを設定する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
description: Office 365 でアーカイブと削除のポリシーを作成します。これにより、アイテムは自動的にユーザーのアーカイブメールボックスに移動されます。
ms.openlocfilehash: 87e155869c6740dd839c09e3e31e0cb819dc5d37
ms.sourcegitcommit: 54a2cbe5d13f448e0c28655bdf88deb9e5434cac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30935272"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-office-365-organization"></a><span data-ttu-id="4dc93-103">Office 365 組織のメールボックスのアーカイブおよび削除ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="4dc93-103">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>

 <span data-ttu-id="4dc93-104">Office 365 では、管理者は、ユーザーのアーカイブメールボックスにアイテムを自動的に移動し、メールボックスからアイテムを自動的に削除するアーカイブおよび削除ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-104">In Office 365, admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span> <span data-ttu-id="4dc93-105">管理者は、メールボックスに割り当てられたアイテム保持ポリシーを作成し、一定の期間後にユーザーのアーカイブメールボックスにアイテムを移動します。また、特定の保存期間に達した後もメールボックスからアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-105">The admin does this by creating a retention policy that's assigned to mailboxes, and moves items to a user's archive mailbox after a certain period of time and that also deletes items from the mailbox after they reach a certain age limit.</span></span> <span data-ttu-id="4dc93-106">移動または削除されたアイテム、およびその発生時に保持タグと呼ばれるアイテムを決定する実際のルール。</span><span class="sxs-lookup"><span data-stu-id="4dc93-106">The actual rules that determine what items are moved or deleted and when that happens are called retention tags.</span></span> <span data-ttu-id="4dc93-107">保持タグは、ユーザーのメールボックスに割り当てられるアイテム保持ポリシーにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-107">Retention tags are linked to a retention policy, that in turn is assigned to a user's mailbox.</span></span> <span data-ttu-id="4dc93-108">保持タグは、ユーザーのメールボックス内の個々のメッセージおよびフォルダーに保持設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-108">A retention tag applies retention settings to individual messages and folders in a user's mailbox.</span></span> <span data-ttu-id="4dc93-109">メッセージがメールボックス内に残っている期間と、指定された保持期限に達したときに実行される処理を定義します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-109">It defines how long a message remains in the mailbox and what action is taken when the message reaches the specified retention age.</span></span> <span data-ttu-id="4dc93-110">メッセージが保存期限に達すると、メッセージはユーザーのアーカイブメールボックスに移動されるか、削除されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-110">When a message reaches its retention age, it's either moved to the user's archive mailbox or it's deleted.</span></span> 
  
<span data-ttu-id="4dc93-111">この記事の手順では、Alpine House という架空の組織のアーカイブとアイテム保持ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-111">The steps in this article will set up an archiving and retention policy for a fictitious organization named Alpine House.</span></span> <span data-ttu-id="4dc93-112">このポリシーの設定には、次のタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-112">Setting up this policy includes the following tasks:</span></span>
  
- <span data-ttu-id="4dc93-113">組織内のすべてのユーザーに対してアーカイブメールボックスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-113">Enabling an archive mailbox for every user in the organization.</span></span> <span data-ttu-id="4dc93-114">これにより、ユーザーにメールボックスストレージが追加され、アイテム保持ポリシーがアーカイブメールボックスにアイテムを移動できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dc93-114">This gives users addition mailbox storage, and is required so that a retention policy can move items to the archive mailbox.</span></span> <span data-ttu-id="4dc93-115">また、ユーザーはアーカイブメールボックスにアイテムを移動することによってアーカイブ情報を格納できます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-115">It also let's a user store archival information by moving items to their archive mailbox.</span></span> 
    
- <span data-ttu-id="4dc93-116">次の操作を実行する3つのカスタム保持タグを作成します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-116">Creating three custom retention tags that do the following:</span></span> 
    
  - <span data-ttu-id="4dc93-117">3年以上経過したアイテムをユーザーのアーカイブメールボックスに自動的に移動します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-117">Automatically moves items that are 3 years old to the user's archive mailbox.</span></span> <span data-ttu-id="4dc93-118">アイテムをアーカイブメールボックスに移動すると、ユーザーのプライマリメールボックス内の領域が解放されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-118">Moving items to the archive mailbox frees up space in a user's primary mailbox.</span></span>
    
  - <span data-ttu-id="4dc93-119">5年前のアイテムを削除済みアイテムフォルダーから自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-119">Automatically deletes items that are 5 years old from the Deleted Items folder.</span></span> <span data-ttu-id="4dc93-120">これにより、ユーザーのプライマリメールボックス内のスペースも解放されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-120">This also frees up space in the user's primary mailbox.</span></span> <span data-ttu-id="4dc93-121">ユーザーは、必要に応じてこれらのアイテムを復元できます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-121">User's will have the opportunity to recover these items if necessary.</span></span> <span data-ttu-id="4dc93-122">詳細については、「 [more information](#more-information) 」セクションの脚注を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dc93-122">See the footnote in the [More information](#more-information) section for more details.</span></span> 
    
  - <span data-ttu-id="4dc93-123">7年前のアイテムをプライマリメールボックスとアーカイブメールボックスの両方から、自動的に (および完全に) 削除します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-123">Automatically (and permanently) deletes items that are 7 years old from both the primary and archive mailbox.</span></span> <span data-ttu-id="4dc93-124">コンプライアンス規制のため、一部の組織では、一定期間電子メールを保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dc93-124">Because of compliance regulations, some organization's are required to retain email for a certain period of time.</span></span> <span data-ttu-id="4dc93-125">この期間が過ぎると、組織はこれらのアイテムのユーザーメールボックスを完全に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-125">After this time period expires, an organization might want to permanently remove these items user mailboxes.</span></span> 
    
- <span data-ttu-id="4dc93-126">新しいアイテム保持ポリシーを作成し、それに新しいカスタム保持タグを追加します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-126">Creating a new retention policy and adding the new custom retention tags to it.</span></span> <span data-ttu-id="4dc93-127">また、組み込み保持タグを新しいアイテム保持ポリシーに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-127">Additionally, you'll also add built-in retention tags to the new retention policy.</span></span> <span data-ttu-id="4dc93-128">これには、ユーザーが自分のメールボックス内のアイテムに割り当てることができる個人タグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4dc93-128">This includes personal tags that users can assign to items in their mailbox.</span></span> <span data-ttu-id="4dc93-129">また、ユーザーのプライマリメールボックス内の [回復可能なアイテム] フォルダーからアーカイブメールボックス内の [回復可能なアイテム] フォルダーにアイテムを移動する保持タグを追加します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-129">You'll also add a retention tag that moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="4dc93-130">これにより、ユーザーのメールボックスが保持されているときに、回復可能なアイテムフォルダーの空き領域を増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-130">This helps free up space in a user's Recoverable Items folder when their mailbox is placed on hold.</span></span>
    
<span data-ttu-id="4dc93-131">この記事の手順の一部またはすべてを実行して、組織内のメールボックスのアーカイブおよび削除ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-131">You can follow some or all of the steps in this article to set up an archive and deletion policy for mailboxes in your own organization.</span></span> <span data-ttu-id="4dc93-132">このプロセスは、組織内のすべてのメールボックスに実装する前に、少数のメールボックスに対してテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-132">We recommend that you test this process on a few mailboxes before implementing it on all mailboxes in your organization.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="4dc93-133">始める前に</span><span class="sxs-lookup"><span data-stu-id="4dc93-133">Before you begin</span></span>

- <span data-ttu-id="4dc93-134">このトピックの手順を実行するには、Office 365 組織の全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dc93-134">You have to be a global administrator in your Office 365 organization to perform the steps in this topic.</span></span> 
    
-  <span data-ttu-id="4dc93-135">Office 365 で新しいユーザーアカウントを作成し、ユーザーに Exchange Online のライセンスを割り当てると、そのユーザーのメールボックスが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-135">When you create a new user account in Office 365 and assign the user an Exchange Online license, a mailbox is automatically created for the user.</span></span> <span data-ttu-id="4dc93-136">メールボックスが作成されると、default mrm policy という名前の既定のアイテム保持ポリシーが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-136">When the mailbox is created, it's automatically assigned a default retention policy, named Default MRM Policy.</span></span> <span data-ttu-id="4dc93-137">この記事では、新しいアイテム保持ポリシーを作成し、それをユーザーのメールボックスに割り当てて、既定の mrm ポリシーを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-137">In this article, you will create a new retention policy and then assign it to user mailboxes, replacing the Default MRM policy.</span></span> <span data-ttu-id="4dc93-138">メールボックスには、一度に1つだけ保持ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-138">A mailbox can have only one retention policy assigned to it at any one time.</span></span>
    
- <span data-ttu-id="4dc93-139">Exchange Online の保持タグとアイテム保持ポリシーの詳細については、「 [retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkId=404424)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dc93-139">To learn more about retention tags and retention policies in Exchange Online, see [Retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkId=404424).</span></span>
    
## <a name="step-1-enable-archive-mailboxes-for-users"></a><span data-ttu-id="4dc93-140">手順 1: ユーザーのアーカイブメールボックスを有効にする</span><span class="sxs-lookup"><span data-stu-id="4dc93-140">Step 1: Enable archive mailboxes for users</span></span>

<span data-ttu-id="4dc93-141">最初の手順として、組織内の各ユーザーのアーカイブメールボックスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-141">The first step is to enable the archive mailbox for each user in your organization.</span></span> <span data-ttu-id="4dc93-142">ユーザーのアーカイブメールボックスを有効にして、保持期間の期限が切れた後に "アーカイブに移動する" 保持アクションを実行するアイテムを移動できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dc93-142">A user's archive mailbox has to be enabled so that a retention tag with a "Move to Archive" retention action can move the item after the retention age expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4dc93-143">このプロセスの実行中は、いつでもアーカイブメールボックスを有効にすることができます。これは、プロセスが完了する前に、ある時点で有効になっている限りです。</span><span class="sxs-lookup"><span data-stu-id="4dc93-143">You can enable archive mailboxes any time during this process, just as long as they're enabled at some point before you complete the process.</span></span> <span data-ttu-id="4dc93-144">アーカイブメールボックスが有効になっていない場合、アーカイブポリシーが割り当てられているアイテムに対しては何も実行されません。</span><span class="sxs-lookup"><span data-stu-id="4dc93-144">If an archive mailbox isn't enabled, no action is taken on any items that have an archive policy assigned to it.</span></span> 
  
1. <span data-ttu-id="4dc93-145">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-145">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="4dc93-146">Sign in to Office 365 using your global administrator account.</span><span class="sxs-lookup"><span data-stu-id="4dc93-146">Sign in to Office 365 using your global administrator account.</span></span>
    
    
3. <span data-ttu-id="4dc93-147">セキュリティ&amp; /コンプライアンスセンターで、[ **Data ガバナンス** \> **アーカイブ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-147">In the Security &amp; Compliance Center, go to **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="4dc93-148">組織内のメールボックスの一覧、および対応するアーカイブメールボックスが有効になっているかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-148">A list of the mailboxes in your organization is displayed and whether the corresponding archive mailbox is enabled or disabled.</span></span> 
    
4. <span data-ttu-id="4dc93-149">一覧の最初のメールボックスをクリックし、 **Shift**キーを押しながら、一覧の最後のメールボックスをクリックして、すべてのメールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-149">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="4dc93-150">この手順は、アーカイブメールボックスが有効になっていないことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="4dc93-150">This step assumes that no archive mailboxes are enabled.</span></span> <span data-ttu-id="4dc93-151">アーカイブが有効になっているメールボックスがある場合は、 **Ctrl**キーを押したまま、無効にされたアーカイブメールボックスを持つ各メールボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-151">If you have any mailboxes with the archive enabled, hold down the **Ctrl** key and click each mailbox that has a disabled archive mailbox.</span></span> <span data-ttu-id="4dc93-152">または、アーカイブメール\*\*\*\* ボックスの列ヘッダーをクリックして、アーカイブメールボックスが有効か無効かに基づいて行を並べ替え、メールボックスを簡単に選択できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-152">Or you can click the **Archive mailbox** column header to sort the rows based on whether the archive mailbox is enabled or disabled to make it easier to select mailboxes.</span></span> 
  
5. <span data-ttu-id="4dc93-153">詳細ウィンドウの [**一括編集**] で、[**有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-153">In the details pane, under **Bulk Edit**, click **Enable**.</span></span>
    
    <span data-ttu-id="4dc93-154">2年間以上経過したアイテムが新しいアーカイブメールボックスに移動されるという警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-154">A warning is displayed saying that items that are older than two years will be moved to the new archive mailbox.</span></span> <span data-ttu-id="4dc93-155">これは、作成時に新しいユーザーメールボックスに割り当てられる既定の保持ポリシーに、2年間の保持期間が設定された既定のアイテム保持ポリシーがあるからです。</span><span class="sxs-lookup"><span data-stu-id="4dc93-155">This is because the default retention policy that's assigned a new user mailbox when it's created has an archive default policy tag that has a retention age of 2 years.</span></span> <span data-ttu-id="4dc93-156">手順2で作成するカスタムアーカイブの既定のポリシータグには、3年間の保持期限があります。</span><span class="sxs-lookup"><span data-stu-id="4dc93-156">The custom archive default policy tag that you'll create in Step 2 has a retention age of 3 years.</span></span> <span data-ttu-id="4dc93-157">これは、3年間またはそれ以前のアイテムがアーカイブメールボックスに移動されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-157">That means items that are 3 years or older will be moved to the archive mailbox.</span></span>
    
6. <span data-ttu-id="4dc93-158">[**はい]** をクリックして警告メッセージを閉じ、選択した各メールボックスのアーカイブメールボックスを有効にするプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-158">Click **Yes** to close the warning message and start the process to enable the archive mailbox for each selected mailbox.</span></span> 
    
7. <span data-ttu-id="4dc93-159">処理が完了したら、[ \*\*\*\* ![最新の](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)情報に更新] をクリックして、[**アーカイブ**] ページの一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-159">When the process is complete, click **Refresh** ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the list on the **Archive** page.</span></span> 
    
    <span data-ttu-id="4dc93-160">アーカイブメールボックスは、組織内のすべてのユーザーに対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4dc93-160">The archive mailbox is enabled for all user's in your organization.</span></span>
    
    ![アーカイブメールボックスが有効になっているメールボックスの一覧](media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)
  
8. <span data-ttu-id="4dc93-162">セキュリティ&amp; /コンプライアンスセンターを開いたままにします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-162">Leave the Security &amp; Compliance Center open.</span></span> <span data-ttu-id="4dc93-163">次の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-163">You'll use it in the next step.</span></span>
    
## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a><span data-ttu-id="4dc93-164">手順 2: アーカイブポリシーと削除ポリシー用の新しい保持タグを作成する</span><span class="sxs-lookup"><span data-stu-id="4dc93-164">Step 2: Create new retention tags for the archive and deletion policies</span></span>

<span data-ttu-id="4dc93-165">この手順では、前に説明した3つのカスタム保持タグを作成します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-165">In this step, you'll create the three custom retention tags that were previously described.</span></span>
  
- <span data-ttu-id="4dc93-166">Alpine House 3 年間のアーカイブへの移動 (カスタムアーカイブポリシー)</span><span class="sxs-lookup"><span data-stu-id="4dc93-166">Alpine House 3 Year Move to Archive (custom archive policy)</span></span>
    
- <span data-ttu-id="4dc93-167">Alpine House 7 年間完全に削除 (カスタム削除ポリシー)</span><span class="sxs-lookup"><span data-stu-id="4dc93-167">Alpine House 7 Year Permanently Delete (custom deletion policy)</span></span>
    
- <span data-ttu-id="4dc93-168">Alpine House deleted items 5 年間削除して回復を許可する (削除済みアイテムフォルダーのカスタムタグ)</span><span class="sxs-lookup"><span data-stu-id="4dc93-168">Alpine House Deleted Items 5 Years Delete and Allow Recovery (custom tag for the Deleted Items folder)</span></span>
    
<span data-ttu-id="4dc93-169">新しい保持タグを作成するには、exchange Online 組織の exchange 管理センター (EAC) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-169">To create new retention tags, you'll use the Exchange admin center (EAC) in your Exchange Online organization.</span></span>
  
1. <span data-ttu-id="4dc93-170">セキュリティ&amp; /コンプライアンスセンターで、左上隅にあるアプリ起動ツールをクリックし、[**管理者**] タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-170">In the Security &amp; Compliance Center, click the app launcher  in the upper left corner, and then click the **Admin** tile .</span></span> 
    
2. <span data-ttu-id="4dc93-171">Office 365 管理センターの左側のナビゲーションウィンドウで、[**管理センター**] をクリックし、[ **Exchange**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-171">In the left navigation pane of the Office 365 admin center, click **Admin centers**, and then click **Exchange**.</span></span>
    
    ![Screenshot shows the Office 365 admin center with the Admin centers option expanded and Exchange selected.](media/47399df2-0bc4-42e2-b183-07750a46bc68.png)
  
3. <span data-ttu-id="4dc93-173">EAC で、[**コンプライアンス管理** \> ] [**保持タグ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-173">In the EAC, go to **Compliance management** \> **Retention tags**</span></span>
    
    <span data-ttu-id="4dc93-174">組織の保持タグの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-174">A list of the retention tags for your organization is displayed.</span></span>
    
### <a name="create-a-custom-archive-default-policy-tag"></a><span data-ttu-id="4dc93-175">カスタムアーカイブの既定のポリシータグを作成する</span><span class="sxs-lookup"><span data-stu-id="4dc93-175">Create a custom archive default policy tag</span></span>
  
<span data-ttu-id="4dc93-176">最初に、3年後にアーカイブメールボックスにアイテムを移動するカスタムアーカイブの既定のポリシータグ (DPT) を作成します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-176">First, you'll create a custom archive default policy tag (DPT) that will move items to the archive mailbox after 3 years.</span></span> 
  
1. <span data-ttu-id="4dc93-177">[**保持タグ**] ページで、[**新しいタグ**![の](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)新規作成] アイコンをクリックし、[**メールボックス全体に自動的に適用する (既定)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-177">On the **Retention tags** page, click **New tag**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span> 
    
2. <span data-ttu-id="4dc93-178">[**メールボックス全体に自動的に適用される新しいタグ (既定)** ] ページで、以下のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-178">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 
    
    ![新しいアーカイブの既定のポリシータグを作成するための設定](media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
1. <span data-ttu-id="4dc93-180">**名前**新しい保持タグの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-180">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="4dc93-181">**保持アクション**保持期間が経過したときにアーカイブメールボックスにアイテムを移動するには、[**アーカイブに移動**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-181">**Retention action** Select **Move to Archive** to move items to the archive mailbox when the retention period expires.</span></span> 
    
3. <span data-ttu-id="4dc93-182">**保持期間\*\*\*\*アイテムが次の期間 (日数) に達したときに**選択し、保存期間の期間を入力します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-182">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="4dc93-183">このシナリオでは、アイテムは1095日 (3 年) 後にアーカイブメールボックスに移動されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-183">For this scenario, items will be moved to the archive mailbox after 1095 days (3 years).</span></span>
    
4. <span data-ttu-id="4dc93-184">**コメント**オプションカスタム保持タグの目的を説明するコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-184">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="4dc93-185">[**保存**] をクリックして、カスタムアーカイブ DPT を作成します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-185">Click **Save** to create the custom archive DPT.</span></span> 
    
    <span data-ttu-id="4dc93-186">新しいアーカイブ DPT が保持タグの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-186">The new archive DPT is displayed in the list of retention tags.</span></span>
    
### <a name="create-a-custom-deletion-default-policy-tag"></a><span data-ttu-id="4dc93-187">カスタム削除の既定のポリシータグを作成する</span><span class="sxs-lookup"><span data-stu-id="4dc93-187">Create a custom deletion default policy tag</span></span>
  
<span data-ttu-id="4dc93-188">次に、もう1つのカスタム DPT を作成しますが、これは7年後にアイテムを完全に削除する削除ポリシーとなります。</span><span class="sxs-lookup"><span data-stu-id="4dc93-188">Next, you'll create another custom DPT but this one will be a deletion policy that permanently deletes items after 7 years.</span></span>
  
1. <span data-ttu-id="4dc93-189">[**保持タグ**] ページで、[**新しいタグ**![の](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)新規作成] アイコンをクリックし、[**メールボックス全体に自動的に適用する (既定)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-189">On the **Retention tags** page, click **New tag**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span> 
    
2. <span data-ttu-id="4dc93-190">[**メールボックス全体に自動的に適用される新しいタグ (既定)** ] ページで、以下のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-190">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 
    
    ![新しい削除の既定のポリシータグを作成するための設定](media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
1. <span data-ttu-id="4dc93-192">**名前**新しい保持タグの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-192">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="4dc93-193">**保持アクション**保持期間が経過したときにメールボックスからアイテムを削除するには、[**完全に削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-193">**Retention action** Select **Permanently Delete** to purge items from the mailbox when the retention period expires.</span></span> 
    
3. <span data-ttu-id="4dc93-194">**保持期間\*\*\*\*アイテムが次の期間 (日数) に達したときに**選択し、保存期間の期間を入力します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-194">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="4dc93-195">このシナリオでは、アイテムは2555日 (7 年) 後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-195">For this scenario, items will be purged after 2555 days (7 years).</span></span>
    
4. <span data-ttu-id="4dc93-196">**コメント**オプションカスタム保持タグの目的を説明するコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-196">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="4dc93-197">[**保存**] をクリックして、カスタム削除 DPT を作成します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-197">Click **Save** to create the custom deletion DPT.</span></span> 
    
    <span data-ttu-id="4dc93-198">新しい削除 DPT が保持タグの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-198">The new deletion DPT is displayed in the list of retention tags.</span></span>
    
### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a><span data-ttu-id="4dc93-199">削除済みアイテムフォルダーのカスタムアイテム保持ポリシータグを作成する</span><span class="sxs-lookup"><span data-stu-id="4dc93-199">Create a custom retention policy tag for the Deleted Items folder</span></span>
  
<span data-ttu-id="4dc93-200">作成する最後の保持タグは、削除済みアイテムフォルダーのカスタムアイテム保持ポリシータグ (RPT) です。</span><span class="sxs-lookup"><span data-stu-id="4dc93-200">The last retention tag that you'll create is a custom retention policy tag (RPT) for the Deleted Items folder.</span></span> <span data-ttu-id="4dc93-201">このタグは、削除済みアイテムフォルダー内のアイテムを5年後に削除し、ユーザーが [削除済みアイテムを復元] ツールを使用してアイテムを復元するときの回復期間を提供します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-201">This tag will delete items in the Deleted Items folder after 5 years, and provides a recovery period when users can use the Recover Deleted Items tool to recover an item.</span></span>
  
1. <span data-ttu-id="4dc93-202">[**保持タグ**] ページで、[**新しいタグ** ![の](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)新規作成] アイコンをクリックし、[**既定のフォルダーに自動的に適用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-202">On the **Retention tags** page, click **New tag** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to a default folder**.</span></span> 
    
2. <span data-ttu-id="4dc93-203">既定の**フォルダーページに自動的に適用される新しいタグ**で、以下のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-203">On the **New tag applied automatically to a default folder** page, complete the following fields:</span></span> 
    
    ![削除済みアイテムフォルダーの新しいアイテム保持ポリシータグを作成するための設定](media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
1. <span data-ttu-id="4dc93-205">**名前**新しい保持タグの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-205">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="4dc93-206">**[次の既定フォルダーにこのタグを適用する**]ドロップダウンリストで、[**削除済みアイテム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-206">**Apply this tag to the following default folder** In the drop-down list, select **Deleted Items**.</span></span>
    
3. <span data-ttu-id="4dc93-207">**保持アクション**[**削除して回復を許可**する] を選択して、保存期間の期限が切れたときにアイテムを削除します。ただし、ユーザーは削除済みアイテムの保存期間 (既定では14日) 内で削除されたアイテムを復元することができます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-207">**Retention action** Select **Delete and Allow Recovery** to delete items when the retention period expires, but allow users to recover a deleted item within the deleted item retention period (which by default is 14 days).</span></span> 
    
4. <span data-ttu-id="4dc93-208">**保持期間\*\*\*\*アイテムが次の期間 (日数) に達したときに**選択し、保存期間の期間を入力します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-208">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="4dc93-209">このシナリオでは、1825日 (5 年) 後にアイテムが削除されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-209">For this scenario, items will be deleted after 1825 days (5 years).</span></span>
    
5. <span data-ttu-id="4dc93-210">**コメント**オプションカスタム保持タグの目的を説明するコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-210">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="4dc93-211">[**保存**] をクリックして、削除済みアイテムフォルダーのカスタム RPT を作成します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-211">Click **Save** to create the custom RPT for the Deleted Items folder.</span></span> 
    
    <span data-ttu-id="4dc93-212">新しい RPT が保持タグの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-212">The new RPT is displayed in the list of retention tags.</span></span>

## <a name="step-3-create-a-new-retention-policy"></a><span data-ttu-id="4dc93-213">手順 3: 新しいアイテム保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4dc93-213">Step 3: Create a new retention policy</span></span>

<span data-ttu-id="4dc93-214">カスタム保持タグを作成したら、次の手順として、新しいアイテム保持ポリシーを作成し、保持タグを追加します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-214">After you create the custom retention tags, the next step is to create a new retention policy and add the retention tags.</span></span> <span data-ttu-id="4dc93-215">手順2で作成した3つのカスタム保持タグと、最初のセクションで説明した組み込みタグを追加します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-215">You'll add the three custom retention tags that you created in Step 2, and the built-in tags that were mentioned in the first section.</span></span> <span data-ttu-id="4dc93-216">ステップ4では、この新しいアイテム保持ポリシーをユーザーメールボックスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-216">In Step 4, you'll assign this new retention policy to user mailboxes.</span></span>
  
1. <span data-ttu-id="4dc93-217">EAC で、[**コンプライアンス管理** \> ] [**アイテム保持ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-217">In the EAC, go to **Compliance management** \> **Retention policies**.</span></span>
    
2. <span data-ttu-id="4dc93-218">[**アイテム保持ポリシー** ] ページで\*\*\*\* ![、[新規](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)作成] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-218">On the **Retention policies** page, click **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>
    
3. <span data-ttu-id="4dc93-219">[**名前**] ボックスに、新しいアイテム保持ポリシーの名前を入力します。たとえば、 **Alpine House のアーカイブおよび削除ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="4dc93-219">In the **Name** box, type a name for the new retention policy; for example, **Alpine House Archive and Deletion Policy**.</span></span> 
    
4. <span data-ttu-id="4dc93-220">[**保持タグ**] で\*\*\*\* ![、[新規](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)アイコンの追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-220">Under **Retention tags**, click **Add** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>
    
    <span data-ttu-id="4dc93-221">組織内の保持タグの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-221">A list of the retention tags in your organization is displayed.</span></span> <span data-ttu-id="4dc93-222">メモ手順2で作成したカスタムタグが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-222">Note the custom tags that you created in Step 2 are displayed.</span></span>
    
5. <span data-ttu-id="4dc93-223">次のスクリーンショットで強調表示されている9つの保持タグを追加します (これらのタグの詳細については、「 [more information](#more-information) 」セクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="4dc93-223">Add the 9 retention tags that are highlighted in the following screenshot (these tags are described in more detail in the [More information](#more-information) section).</span></span> <span data-ttu-id="4dc93-224">保持タグを追加するには、それを選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-224">To add a retention tag, select it and then click **Add**.</span></span> 
    
    ![新しいアイテム保持ポリシーに保持タグを追加する](media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > <span data-ttu-id="4dc93-226">複数の保持タグを選択するには、 **Ctrl**キーを押しながら各タグをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-226">You can select multiple retention tags by holding down the **Ctrl** key and then clicking each tag.</span></span> 
  
6. <span data-ttu-id="4dc93-227">保持タグを追加したら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-227">After you've added the retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="4dc93-228">[**新しいアイテム保持ポリシー** ] ページで、[**保存**] をクリックして新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-228">On the **New retention policy** page, click **Save** to create the new policy.</span></span> 
    
    <span data-ttu-id="4dc93-229">新しいアイテム保持ポリシーが一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-229">The new retention policy is displayed in the list.</span></span> <span data-ttu-id="4dc93-230">このチェックボックスをオンにすると、詳細ウィンドウにリンクされている保持タグが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-230">Select it to display the retention tags linked to it in the details pane.</span></span>
    
    ![新しいアイテム保持ポリシーとリンクされた保持タグのリスト](media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a><span data-ttu-id="4dc93-232">手順 4: 新しいアイテム保持ポリシーをユーザーメールボックスに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4dc93-232">Step 4: Assign the new retention policy to user mailboxes</span></span>

<span data-ttu-id="4dc93-233">新しいメールボックスが作成されると、default mrm policy という名前のアイテム保持ポリシーが既定で割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-233">When a new mailbox is created, a retention policy named Default MRM policy is assigned to it by default.</span></span> <span data-ttu-id="4dc93-234">この手順では、手順3で作成した新しいアイテム保持ポリシーを組織内のユーザーのメールボックスに割り当てることによって、このアイテム保持ポリシーを置き換えます (メールボックスに割り当てられる保持ポリシーは1つだけです)。</span><span class="sxs-lookup"><span data-stu-id="4dc93-234">In this step, you'll replace this retention policy (because a mailbox can have only one retention policy assigned to it) by assigning the new retention policy that you created in Step 3 to the user mailboxes in your organization.</span></span> <span data-ttu-id="4dc93-235">この手順では、組織内のすべてのメールボックスに新しいポリシーを割り当てることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="4dc93-235">This step assumes that you'll assign the new policy to all mailboxes in your organization.</span></span>
  
1. <span data-ttu-id="4dc93-236">EAC で、 **[受信者]** \> **[メールボックス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-236">In the EAC, go to **Recipients** \> **Mailboxes**.</span></span>
    
    <span data-ttu-id="4dc93-237">組織内のすべてのユーザーメールボックスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-237">A list of all user mailboxes in your organization is displayed.</span></span> 
    
2. <span data-ttu-id="4dc93-238">一覧の最初のメールボックスをクリックし、 **Shift**キーを押しながら、一覧の最後のメールボックスをクリックして、すべてのメールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-238">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 
    
3. <span data-ttu-id="4dc93-239">EAC の右側にある詳細ウィンドウの [**一括編集**] で、[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-239">In the details pane on the right side of the EAC, under **Bulk Edit**, click **More options**.</span></span>
    
4. <span data-ttu-id="4dc93-240">**[アイテム保持ポリシー]** 下で **[更新]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-240">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="4dc93-241">[**アイテム保持ポリシーの一括割り当て**] ページの [**アイテム保持ポリシーの選択**] ドロップダウンリストで、手順3で作成したアイテム保持ポリシーを選択します。たとえば、 **Alpine House のアーカイブとアイテム保持ポリシー**があります。</span><span class="sxs-lookup"><span data-stu-id="4dc93-241">On the **Bulk assign retention policy** page, in the **Select the retention policy** drop-down list, select the retention policy that you created in Step 3; for example, **Alpine House Archive and Retention Policy**.</span></span>
    
6. <span data-ttu-id="4dc93-242">[**保存**] をクリックして、新しいアイテム保持ポリシーの割り当てを保存します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-242">Click **Save** to save the new retention policy assignment.</span></span> 
    
7. <span data-ttu-id="4dc93-243">新しいアイテム保持ポリシーがメールボックスに割り当てられていることを確認するには、次の操作を行います。 [メールボックス] ページでメールボックスを選択し、[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-243">To verify that the new retention policy was assigned to mailboxes, you can do the following: select a mailbox on the Mailboxes page, and then click Edit.</span></span> 
    
1. <span data-ttu-id="4dc93-244">[**メールボックス**] ページでメールボックスを選択し\*\*\*\* ![、[](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png)編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-244">Select a mailbox on the **Mailboxes** page, and then click **Edit** ![Edit](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png).</span></span> 
    
2. <span data-ttu-id="4dc93-245">選択したユーザーのメールボックスのプロパティページで、[**メールボックスの機能**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-245">On the mailbox properties page for the selected user, click **Mailbox features**.</span></span>
    
    <span data-ttu-id="4dc93-246">メールボックスに割り当てられた新しいポリシーの名前が、[**アイテム保持ポリシー** ] ドロップダウンリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-246">The name of the new policy assigned to the mailbox is displayed in the **Retention policy** drop-down list.</span></span> 

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a><span data-ttu-id="4dc93-247">オプション手順 5: 管理フォルダーアシスタントを実行して新しい設定を適用する</span><span class="sxs-lookup"><span data-stu-id="4dc93-247">(Optional) Step 5: Run the Managed Folder Assistant to apply the new settings</span></span>

<span data-ttu-id="4dc93-248">手順4で新しいアイテム保持ポリシーをメールボックスに適用した後、メールボックスに新しいアイテム保持設定を適用するには、Exchange Online で最大7日かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="4dc93-248">After you apply the new retention policy to mailboxes in Step 4, it can take up to 7 days in Exchange Online for the new retention settings to be applied to the mailboxes.</span></span> <span data-ttu-id="4dc93-249">これは、管理フォルダーアシスタントと呼ばれるプロセスが7日ごとにメールボックスを処理するからです。</span><span class="sxs-lookup"><span data-stu-id="4dc93-249">This is because a process called the Managed Folder Assistant processes mailboxes once every 7 days.</span></span> <span data-ttu-id="4dc93-250">管理フォルダーアシスタントの実行を待機する代わりに、Exchange Online PowerShell で " **Start/managedfolderassistant** " コマンドレットを実行することによって、これを強制的に実行することができます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-250">Instead of waiting for the Managed Folder Assistant to run, you can force this to happen by running the **Start-ManagedFolderAssistant** cmdlet in Exchange Online PowerShell.</span></span> 
  
 <span data-ttu-id="4dc93-251">**管理フォルダーアシスタントを実行するとどうなりますか。**</span><span class="sxs-lookup"><span data-stu-id="4dc93-251">**What happens when you run the Managed Folder Assistant?**</span></span> <span data-ttu-id="4dc93-252">アイテム保持ポリシーの設定を適用するには、メールボックス内のアイテムを調べて、保持の対象であるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-252">It applies the settings in the retention policy by inspecting items in the mailbox and determining whether they're subject to retention.</span></span> <span data-ttu-id="4dc93-253">その後、適切な保持タグを使用してアイテムに保存期間をスタンプし、保存期間を過ぎたアイテムに対して指定された保持アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-253">It then stamps items subject to retention with the appropriate retention tag, and then takes the specified retention action on items past their retention age.</span></span> 
  
<span data-ttu-id="4dc93-254">Exchange Online PowerShell に接続し、組織内のすべてのメールボックスで管理フォルダーアシスタントを実行する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-254">Here are the steps to connect to Exchange Online PowerShell, and then run the Managed Folder Assistant on every mailbox in your organization.</span></span>
  
1. <span data-ttu-id="4dc93-255">ローカル コンピューターで、Windows PowerShell を開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-255">On your local computer, open Windows PowerShell and run the following command.</span></span>
    
    ```
    $UserCredential = Get-Credential
    ```

    <span data-ttu-id="4dc93-256">[ **Windows PowerShell 資格情報の要求**] ダイアログボックスで、Office 365 グローバル管理者アカウントのユーザー名とパスワードを入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-256">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global admin account, and then click **OK**.</span></span>
    
2. <span data-ttu-id="4dc93-257">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-257">Run the following command.</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. <span data-ttu-id="4dc93-258">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-258">Run the following command.</span></span>
    
    ```
    Import-PSSession $Session
    ```

4. <span data-ttu-id="4dc93-259">Exchange Online 組織に接続されたことを検証するために、次のコマンドを実行して、組織内のすべてのメールボックスのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-259">To verify that you're connected to your Exchange Online organization, run the following command to get a list of all the mailboxes in your organization.</span></span>
    
    ```
    Get-Mailbox
    ```

    > [!NOTE]
    > <span data-ttu-id="4dc93-260">詳細については、または exchange online 組織への接続に問題がある場合は、「 [exchange online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=517283)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dc93-260">For more information or if you have problems connecting to your Exchange Online organization, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span> 
  
5. <span data-ttu-id="4dc93-261">組織内のすべてのユーザーメールボックスに対して管理フォルダーアシスタントを開始するには、次の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-261">Run the following two commands to start the Managed Folder Assistant for all user mailboxes in your organization.</span></span>
    
    ```
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

<span data-ttu-id="4dc93-262">するだけです。</span><span class="sxs-lookup"><span data-stu-id="4dc93-262">That's it!</span></span> <span data-ttu-id="4dc93-263">Alpine House 組織のアーカイブと削除のポリシーを設定している。</span><span class="sxs-lookup"><span data-stu-id="4dc93-263">You've set up an archive and deletion policy for the Alpine House organization.</span></span>
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a><span data-ttu-id="4dc93-264">オプション手順 6: 新しいアイテム保持ポリシーを組織の既定に設定する</span><span class="sxs-lookup"><span data-stu-id="4dc93-264">(Optional) Step 6: Make the new retention policy the default for your organization</span></span>

<span data-ttu-id="4dc93-265">手順4では、既存のメールボックスに新しいアイテム保持ポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dc93-265">In Step 4, you have to assign the new retention policy to existing mailboxes.</span></span> <span data-ttu-id="4dc93-266">ただし、今後作成される新しいメールボックスに新しいアイテム保持ポリシーが割り当てられるように、Exchange Online を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-266">But you can configure Exchange Online so that the new retention policy is assigned to new mailboxes that are created in the future.</span></span> <span data-ttu-id="4dc93-267">これを行うには、Exchange Online PowerShell を使用して組織の既定のメールボックスプランを更新します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-267">You do this by using Exchange Online PowerShell to update your organization's default mailbox plan.</span></span> <span data-ttu-id="4dc93-268">*メールボックス計画*は、新しいメールボックスのプロパティを自動的に構成するテンプレートです。</span><span class="sxs-lookup"><span data-stu-id="4dc93-268">A *mailbox plan* is a template that automatically configures properties on new mailboxes.</span></span>  <span data-ttu-id="4dc93-269">このオプションの手順では、メールボックスプランに割り当てられている現在のアイテム保持ポリシー (既定では、既定の mrm ポリシー) を手順3で作成したアイテム保持ポリシーに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-269">In this optional step, you can replace the current retention policy that's assigned to the mailbox plan (by default, the Default MRM Policy) with the retention policy that you created in Step 3.</span></span> <span data-ttu-id="4dc93-270">メールボックスプランを更新すると、新しいアイテム保持ポリシーが新しいメールボックスに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-270">After you update the mailbox plan, the new retention policy will be assigned to new mailboxes.</span></span>

1. <span data-ttu-id="4dc93-271">[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?LinkId=517283)か、手順5を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dc93-271">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) or see Step 5.</span></span>

2. <span data-ttu-id="4dc93-272">組織内のメールボックスプランに関する情報を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-272">Run the following command to display information about the mailbox plans in your organization.</span></span>

    ```
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```
    <span data-ttu-id="4dc93-273">既定として設定されているメールボックスプランをメモします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-273">Note the mailbox plan that's set as the default.</span></span>

3. <span data-ttu-id="4dc93-274">次のコマンドを実行して、手順3で作成した新しいアイテム保持ポリシー (たとえば、 **Alpine House Archive and retention policy**) を既定のメールボックス計画に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-274">Run the following command to assign the new retention policy that you created in Step 3 (for example, **Alpine House Archive and Retention Policy**) to the default mailbox plan.</span></span> <span data-ttu-id="4dc93-275">この例では、既定のメールボックスプランの名前が**exchangeonline enterprise**であると仮定しています。</span><span class="sxs-lookup"><span data-stu-id="4dc93-275">This example assumes the name of the default mailbox plan is **ExchangeOnlineEnterprise**.</span></span>

    ```
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```
4. <span data-ttu-id="4dc93-276">手順2のコマンドを再実行して、既定のメールボックス計画に割り当てられているアイテム保持ポリシーが変更されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-276">You can re-run the command in step 2 to verify that the retention policy assigned to the default mailbox plan was changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="4dc93-277">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4dc93-277">More information</span></span>

- <span data-ttu-id="4dc93-278">保存期間はどのように計算されますか?</span><span class="sxs-lookup"><span data-stu-id="4dc93-278">How is retention age calculated?</span></span> <span data-ttu-id="4dc93-279">メールボックスアイテムの保持期間は、配信日または作成日 (送信されないが、ユーザーによって作成された下書きメッセージなど) から計算されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-279">The retention age of mailbox items is calculated from the date of delivery or the date of creation for items such as draft messages that aren't sent but are created by the user.</span></span> <span data-ttu-id="4dc93-280">管理フォルダー アシスタントがメールボックス内のアイテムを処理する際、 [削除して回復を許可する] または [完全に削除する] の保存期間用アクション付き保持タグの付いたすべてのアイテムに開始日と有効期限をスタンプします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-280">When the Managed Folder Assistant processes items in a mailbox, it stamps a start date and an expiration date for all items that have retention tags with the Delete and Allow Recovery or Permanently Delete retention action.</span></span> <span data-ttu-id="4dc93-281">アーカイブタグがあるアイテムには、移動日がスタンプされます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-281">Items that have an archive tag are stamped with a move date.</span></span> 
    
- <span data-ttu-id="4dc93-282">次の表では、このトピックの手順に従って作成されたカスタムアイテム保持ポリシーに追加される各保持タグの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-282">The following table provides more information about each retention tag that is added to the custom retention policy that was created by following the steps in this topic.</span></span>
    
    |<span data-ttu-id="4dc93-283">**保持タグ**</span><span class="sxs-lookup"><span data-stu-id="4dc93-283">**Retention tag**</span></span>|<span data-ttu-id="4dc93-284">**このタグの内容**</span><span class="sxs-lookup"><span data-stu-id="4dc93-284">**What this tag does**</span></span>|<span data-ttu-id="4dc93-285">**組み込みまたはユーザー設定の場合**</span><span class="sxs-lookup"><span data-stu-id="4dc93-285">**Built-in or custom?**</span></span>|<span data-ttu-id="4dc93-286">**Type**</span><span class="sxs-lookup"><span data-stu-id="4dc93-286">**Type**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4dc93-287">Alpine House 3 年間のアーカイブへの移動</span><span class="sxs-lookup"><span data-stu-id="4dc93-287">Alpine House 3 Year Move to Archive</span></span>  <br/> |<span data-ttu-id="4dc93-288">過去1095日 (3 年) のアイテムをアーカイブメールボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-288">Moves items that are 1095 days (3 years) old to the archive mailbox.</span></span>  <br/> |<span data-ttu-id="4dc93-289">Custom (「[手順 2: アーカイブポリシーと削除ポリシーの新しい保持タグを作成](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)する」を参照)</span><span class="sxs-lookup"><span data-stu-id="4dc93-289">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="4dc93-290">既定のポリシータグ (アーカイブ)、このタグは、メールボックス全体に自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-290">Default Policy Tag (archive); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="4dc93-291">Alpine House 7 年間完全に削除</span><span class="sxs-lookup"><span data-stu-id="4dc93-291">Alpine House 7 Year Permanently Delete</span></span>  <br/> |<span data-ttu-id="4dc93-292">7年前の時点でプライマリメールボックスまたはアーカイブメールボックスのアイテムを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-292">Permanently deletes items in the primary mailbox or the archive mailbox when they are 7 years old.</span></span>  <br/> |<span data-ttu-id="4dc93-293">Custom (「[手順 2: アーカイブポリシーと削除ポリシーの新しい保持タグを作成](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)する」を参照)</span><span class="sxs-lookup"><span data-stu-id="4dc93-293">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="4dc93-294">既定のポリシータグ (削除)。このタグは、メールボックス全体に自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-294">Default Policy Tag (deletion); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="4dc93-295">Alpine House Deleted Items 5 年間削除して回復を許可する</span><span class="sxs-lookup"><span data-stu-id="4dc93-295">Alpine House Deleted Items 5 Years Delete and Allow Recovery</span></span>  <br/> |<span data-ttu-id="4dc93-296">5年前の削除済みアイテムフォルダーからアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-296">Deletes items from the Deleted Items folder that are 5 years old.</span></span> <span data-ttu-id="4dc93-297">ユーザーは、これらのアイテムを削除してから14日後に復元できます。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4dc93-297">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="4dc93-298">Custom (「[手順 2: アーカイブポリシーと削除ポリシーの新しい保持タグを作成](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)する」を参照)</span><span class="sxs-lookup"><span data-stu-id="4dc93-298">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="4dc93-299">アイテム保持ポリシータグ (削除済みアイテム)、このタグは、[削除済みアイテム] フォルダー内のアイテムに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-299">Retention Policy Tag (Deleted Items); this tag is automatically applied to items in the Deleted items folder.</span></span>  <br/> |
    |<span data-ttu-id="4dc93-300">回復可能なアイテム-14 日でアーカイブへ移動</span><span class="sxs-lookup"><span data-stu-id="4dc93-300">Recoverable Items 14 days Move to Archive</span></span>  <br/> |<span data-ttu-id="4dc93-301">回復可能なアイテムフォルダーにあるアイテムを、14日間、アーカイブメールボックスの [回復可能なアイテム] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-301">Moves items that have been in the Recoverable Items folder for 14 days to the Recoverable Items folder in the archive mailbox.</span></span>  <br/> |<span data-ttu-id="4dc93-302">組み込み</span><span class="sxs-lookup"><span data-stu-id="4dc93-302">Built-in</span></span>  <br/> |<span data-ttu-id="4dc93-303">アイテム保持ポリシータグ (回復可能なアイテム)、このタグは、[回復可能なアイテム] フォルダー内のアイテムに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-303">Retention Policy Tag (Recoverable Items); this tag is automatically applied to items in the Recoverable Items folder.</span></span>  <br/> |
    |<span data-ttu-id="4dc93-304">迷惑メール</span><span class="sxs-lookup"><span data-stu-id="4dc93-304">Junk Email</span></span>  <br/> |<span data-ttu-id="4dc93-305">[迷惑メール] フォルダーに30日間含まれていたアイテムを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-305">Permanently deletes items that have been in the Junk Email folder for 30 days.</span></span> <span data-ttu-id="4dc93-306">ユーザーは、これらのアイテムを削除してから14日後に復元できます。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4dc93-306">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="4dc93-307">組み込み</span><span class="sxs-lookup"><span data-stu-id="4dc93-307">Built-in</span></span>  <br/> |<span data-ttu-id="4dc93-308">アイテム保持ポリシータグ (迷惑メール);このタグは、[迷惑メール] フォルダー内のアイテムに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-308">Retention Policy Tag (Junk Email); this tag is automatically applied to items in Junk Email folder.</span></span>  <br/> |
    |<span data-ttu-id="4dc93-309">1 か月で削除</span><span class="sxs-lookup"><span data-stu-id="4dc93-309">1 Month Delete</span></span>  <br/> |<span data-ttu-id="4dc93-310">30日以上経過したアイテムを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-310">Permanently deletes items that are 30 days old.</span></span> <span data-ttu-id="4dc93-311">ユーザーは、これらのアイテムを削除してから14日後に復元できます。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4dc93-311">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="4dc93-312">組み込み</span><span class="sxs-lookup"><span data-stu-id="4dc93-312">Built-in</span></span>  <br/> |<span data-ttu-id="4dc93-313">作成者このタグは、ユーザーが適用することができます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-313">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="4dc93-314">1 年で削除</span><span class="sxs-lookup"><span data-stu-id="4dc93-314">1 Year Delete</span></span>  <br/> |<span data-ttu-id="4dc93-315">過去365日のアイテムを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-315">Permanently deletes items that are 365 days old.</span></span> <span data-ttu-id="4dc93-316">ユーザーは、これらのアイテムを削除してから14日後に復元できます。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4dc93-316">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="4dc93-317">組み込み</span><span class="sxs-lookup"><span data-stu-id="4dc93-317">Built-in</span></span>  <br/> |<span data-ttu-id="4dc93-318">作成者このタグは、ユーザーが適用することができます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-318">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="4dc93-319">削除しない</span><span class="sxs-lookup"><span data-stu-id="4dc93-319">Never Delete</span></span>  <br/> |<span data-ttu-id="4dc93-320">このタグは、アイテム保持ポリシーによってアイテムが削除されないようにします。</span><span class="sxs-lookup"><span data-stu-id="4dc93-320">This tag prevent items from being deleted by a retention policy.</span></span>  <br/> |<span data-ttu-id="4dc93-321">組み込み</span><span class="sxs-lookup"><span data-stu-id="4dc93-321">Built-in</span></span>  <br/> |<span data-ttu-id="4dc93-322">作成者このタグは、ユーザーが適用することができます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-322">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="4dc93-323">個人 - 1 年でアーカイブへ移動</span><span class="sxs-lookup"><span data-stu-id="4dc93-323">Personal 1 year move to archive</span></span>  <br/> |<span data-ttu-id="4dc93-324">1年後にアイテムをアーカイブメールボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="4dc93-324">Moves items to the archive mailbox after 1 year.</span></span>  <br/> |<span data-ttu-id="4dc93-325">組み込み</span><span class="sxs-lookup"><span data-stu-id="4dc93-325">Built-in</span></span>  <br/> |<span data-ttu-id="4dc93-326">作成者このタグは、ユーザーが適用することができます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-326">Personal; this tag can be applied by users.</span></span>  <br/> |
   
    > <span data-ttu-id="4dc93-327"><sup>\*</sup>ユーザーは、outlook および web 上の outlook (旧称 outlook web App) で削除済みアイテムを復元するツールを使用して、削除済みアイテムの保存期間 (既定では、Exchange Online では14日) 内の削除済みアイテムを復元できます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-327"><sup>\*</sup> Users can use the Recover Deleted Items tool in Outlook and Outlook on the web (formerly known as Outlook Web App) to recover a deleted item within the deleted item retention period, which by default is 14 days in Exchange Online.</span></span> <span data-ttu-id="4dc93-328">管理者は、Windows PowerShell を使用して、削除済みアイテムの保存期間を最大で30日に増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-328">An administrator can use Windows PowerShell to increase the deleted item retention period to a maximum of 30 days.</span></span> <span data-ttu-id="4dc93-329">詳細については、「 [Windows 版 Outlook で削除済みアイテムを復元](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)する」および「 [Exchange Online のメールボックスの削除済みアイテムの保存期間を変更](https://go.microsoft.com/fwlink/p/?LinkId=286940)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dc93-329">For more information, see: [Recover deleted items in Outlook for Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) and [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940)</span></span>
  
- <span data-ttu-id="4dc93-330">回復可能なアイテムを使用して、 **14 日後にアーカイブ保持タグに移動する**と、ユーザーのプライマリメールボックス内の回復可能なアイテムフォルダーの記憶域を解放することができます。</span><span class="sxs-lookup"><span data-stu-id="4dc93-330">Using the **Recoverable Items 14 days Move to Archive** retention tag helps free up storage space in the Recoverable Items folder in the user's primary mailbox.</span></span> <span data-ttu-id="4dc93-331">これは、ユーザーのメールボックスが保持されている場合に便利です。つまり、ユーザーのメールボックスが完全に削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="4dc93-331">This is useful when a user's mailbox is placed on hold, which means nothing is ever permanently deleted the user's mailbox.</span></span> <span data-ttu-id="4dc93-332">アイテムをアーカイブメールボックスに移動せずに、プライマリメールボックスの [回復可能なアイテム] フォルダーの記憶域のクォータに到達できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4dc93-332">Without moving items to the archive mailbox, it's possible the storage quota for the Recoverable Items folder in the primary mailbox will be reached.</span></span> <span data-ttu-id="4dc93-333">詳細については、「[ホールド状態のメールボックスの回復可能なアイテムのクォータを増やす](https://go.microsoft.com/fwlink/p/?LinkId=786479)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dc93-333">For more information about this and how to avoid it, see [Increase the Recoverable Items quota for mailboxes on hold](https://go.microsoft.com/fwlink/p/?LinkId=786479).</span></span>
