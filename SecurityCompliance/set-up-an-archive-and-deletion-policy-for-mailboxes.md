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
ms.openlocfilehash: a32c6607ec43634e317ee92b8fed6698e3a5c3b9
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30297010"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-office-365-organization"></a><span data-ttu-id="c808c-103">Office 365 組織のメールボックスのアーカイブおよび削除ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="c808c-103">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>

 <span data-ttu-id="c808c-p101">Office 365 では、管理者は、ユーザーのアーカイブメールボックスにアイテムを自動的に移動し、メールボックスからアイテムを自動的に削除するアーカイブおよび削除ポリシーを作成できます。管理者は、メールボックスに割り当てられたアイテム保持ポリシーを作成し、一定の期間後にユーザーのアーカイブメールボックスにアイテムを移動します。また、特定の保存期間に達した後もメールボックスからアイテムを削除します。移動または削除されたアイテム、およびその発生時に保持タグと呼ばれるアイテムを決定する実際のルール。保持タグは、ユーザーのメールボックスに割り当てられるアイテム保持ポリシーにリンクされます。保持タグは、ユーザーのメールボックス内の個々のメッセージおよびフォルダーに保持設定を適用します。メッセージがメールボックス内に残っている期間と、指定された保持期限に達したときに実行される処理を定義します。メッセージが保存期限に達すると、メッセージはユーザーのアーカイブメールボックスに移動されるか、削除されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p101">In Office 365, admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox. The admin does this by creating a retention policy that's assigned to mailboxes, and moves items to a user's archive mailbox after a certain period of time and that also deletes items from the mailbox after they reach a certain age limit. The actual rules that determine what items are moved or deleted and when that happens are called retention tags. Retention tags are linked to a retention policy, that in turn is assigned to a user's mailbox. A retention tag applies retention settings to individual messages and folders in a user's mailbox. It defines how long a message remains in the mailbox and what action is taken when the message reaches the specified retention age. When a message reaches its retention age, it's either moved to the user's archive mailbox or it's deleted.</span></span> 
  
<span data-ttu-id="c808c-p102">この記事の手順では、Alpine House という架空の組織のアーカイブとアイテム保持ポリシーを設定します。このポリシーの設定には、次のタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p102">The steps in this article will set up an archiving and retention policy for a fictitious organization named Alpine House. Setting up this policy includes the following tasks:</span></span>
  
- <span data-ttu-id="c808c-p103">組織内のすべてのユーザーに対してアーカイブメールボックスを有効にします。これにより、ユーザーにメールボックスストレージが追加され、アイテム保持ポリシーがアーカイブメールボックスにアイテムを移動できるようにする必要があります。また、ユーザーはアーカイブメールボックスにアイテムを移動することによってアーカイブ情報を格納できます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p103">Enabling an archive mailbox for every user in the organization. This gives users addition mailbox storage, and is required so that a retention policy can move items to the archive mailbox. It also let's a user store archival information by moving items to their archive mailbox.</span></span> 
    
- <span data-ttu-id="c808c-116">次の操作を実行する3つのカスタム保持タグを作成します。</span><span class="sxs-lookup"><span data-stu-id="c808c-116">Creating three custom retention tags that do the following:</span></span> 
    
  - <span data-ttu-id="c808c-p104">3年以上経過したアイテムをユーザーのアーカイブメールボックスに自動的に移動します。アイテムをアーカイブメールボックスに移動すると、ユーザーのプライマリメールボックス内の領域が解放されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p104">Automatically moves items that are 3 years old to the user's archive mailbox. Moving items to the archive mailbox frees up space in a user's primary mailbox.</span></span>
    
  - <span data-ttu-id="c808c-p105">5年前のアイテムを削除済みアイテムフォルダーから自動的に削除します。これにより、ユーザーのプライマリメールボックス内のスペースも解放されます。ユーザーは、必要に応じてこれらのアイテムを復元できます。詳細については、「 [more information](#more-information) 」セクションの脚注を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c808c-p105">Automatically deletes items that are 5 years old from the Deleted Items folder. This also frees up space in the user's primary mailbox. User's will have the opportunity to recover these items if necessary. See the footnote in the [More information](#more-information) section for more details.</span></span> 
    
  - <span data-ttu-id="c808c-p106">7年前のアイテムをプライマリメールボックスとアーカイブメールボックスの両方から、自動的に (および完全に) 削除します。コンプライアンス規制のため、一部の組織では、一定期間電子メールを保持する必要があります。この期間が過ぎると、組織はこれらのアイテムのユーザーメールボックスを完全に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p106">Automatically (and permanently) deletes items that are 7 years old from both the primary and archive mailbox. Because of compliance regulations, some organization's are required to retain email for a certain period of time. After this time period expires, an organization might want to permanently remove these items user mailboxes.</span></span> 
    
- <span data-ttu-id="c808c-p107">新しいアイテム保持ポリシーを作成し、それに新しいカスタム保持タグを追加します。また、組み込み保持タグを新しいアイテム保持ポリシーに追加することもできます。これには、ユーザーが自分のメールボックス内のアイテムに割り当てることができる個人タグが含まれています。また、ユーザーのプライマリメールボックス内の [回復可能なアイテム] フォルダーからアーカイブメールボックス内の [回復可能なアイテム] フォルダーにアイテムを移動する保持タグを追加します。これにより、ユーザーのメールボックスが保持されているときに、回復可能なアイテムフォルダーの空き領域を増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p107">Creating a new retention policy and adding the new custom retention tags to it. Additionally, you'll also add built-in retention tags to the new retention policy. This includes personal tags that users can assign to items in their mailbox. You'll also add a retention tag that moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox. This helps free up space in a user's Recoverable Items folder when their mailbox is placed on hold.</span></span>
    
<span data-ttu-id="c808c-p108">この記事の手順の一部またはすべてを実行して、組織内のメールボックスのアーカイブおよび削除ポリシーを設定できます。このプロセスは、組織内のすべてのメールボックスに実装する前に、少数のメールボックスに対してテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c808c-p108">You can follow some or all of the steps in this article to set up an archive and deletion policy for mailboxes in your own organization. We recommend that you test this process on a few mailboxes before implementing it on all mailboxes in your organization.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="c808c-133">はじめに</span><span class="sxs-lookup"><span data-stu-id="c808c-133">Before you begin</span></span>

- <span data-ttu-id="c808c-134">このトピックの手順を実行するには、Office 365 組織の全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c808c-134">You have to be a global administrator in your Office 365 organization to perform the steps in this topic.</span></span> 
    
-  <span data-ttu-id="c808c-p109">Office 365 で新しいユーザーアカウントを作成し、ユーザーに Exchange Online のライセンスを割り当てると、そのユーザーのメールボックスが自動的に作成されます。メールボックスが作成されると、default mrm policy という名前の既定のアイテム保持ポリシーが自動的に割り当てられます。この記事では、新しいアイテム保持ポリシーを作成し、それをユーザーのメールボックスに割り当てて、既定の mrm ポリシーを置き換えます。メールボックスには、一度に1つだけ保持ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p109">When you create a new user account in Office 365 and assign the user an Exchange Online license, a mailbox is automatically created for the user. When the mailbox is created, it's automatically assigned a default retention policy, named Default MRM Policy. In this article, you will create a new retention policy and then assign it to user mailboxes, replacing the Default MRM policy. A mailbox can have only one retention policy assigned to it at any one time.</span></span>
    
- <span data-ttu-id="c808c-139">Exchange Online の保持タグとアイテム保持ポリシーの詳細については、「 [retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkId=404424)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c808c-139">To learn more about retention tags and retention policies in Exchange Online, see [Retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkId=404424).</span></span>
    
## <a name="step-1-enable-archive-mailboxes-for-users"></a><span data-ttu-id="c808c-140">手順 1: ユーザーのアーカイブメールボックスを有効にする</span><span class="sxs-lookup"><span data-stu-id="c808c-140">Step 1: Enable archive mailboxes for users</span></span>

<span data-ttu-id="c808c-p110">最初の手順として、組織内の各ユーザーのアーカイブメールボックスを有効にします。ユーザーのアーカイブメールボックスを有効にして、保持期間の期限が切れた後に "アーカイブに移動する" 保持アクションを実行するアイテムを移動できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c808c-p110">The first step is to enable the archive mailbox for each user in your organization. A user's archive mailbox has to be enabled so that a retention tag with a "Move to Archive" retention action can move the item after the retention age expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c808c-p111">このプロセスの実行中は、いつでもアーカイブメールボックスを有効にすることができます。これは、プロセスが完了する前に、ある時点で有効になっている限りです。アーカイブメールボックスが有効になっていない場合、アーカイブポリシーが割り当てられているアイテムに対しては何も実行されません。</span><span class="sxs-lookup"><span data-stu-id="c808c-p111">You can enable archive mailboxes any time during this process, just as long as they're enabled at some point before you complete the process. If an archive mailbox isn't enabled, no action is taken on any items that have an archive policy assigned to it.</span></span> 
  
1. <span data-ttu-id="c808c-145">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="c808c-145">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c808c-146">グローバル管理者アカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c808c-146">Sign in to Office 365 using your global administrator account.</span></span>
    
    
3. <span data-ttu-id="c808c-147">セキュリティ&amp; /コンプライアンスセンターで、[ **Data ガバナンス** \> **アーカイブ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c808c-147">In the Security &amp; Compliance Center, go to **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="c808c-148">組織内のメールボックスの一覧、および対応するアーカイブメールボックスが有効になっているかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-148">A list of the mailboxes in your organization is displayed and whether the corresponding archive mailbox is enabled or disabled.</span></span> 
    
4. <span data-ttu-id="c808c-149">一覧の最初のメールボックスをクリックし、 **Shift**キーを押しながら、一覧の最後のメールボックスをクリックして、すべてのメールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="c808c-149">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="c808c-p112">この手順は、アーカイブメールボックスが有効になっていないことを前提としています。アーカイブが有効になっているメールボックスがある場合は、 **Ctrl**キーを押したまま、無効にされたアーカイブメールボックスを持つ各メールボックスをクリックします。または、アーカイブメール\*\*\*\* ボックスの列ヘッダーをクリックして、アーカイブメールボックスが有効か無効かに基づいて行を並べ替え、メールボックスを簡単に選択できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p112">This step assumes that no archive mailboxes are enabled. If you have any mailboxes with the archive enabled, hold down the **Ctrl** key and click each mailbox that has a disabled archive mailbox. Or you can click the **Archive mailbox** column header to sort the rows based on whether the archive mailbox is enabled or disabled to make it easier to select mailboxes.</span></span> 
  
5. <span data-ttu-id="c808c-153">詳細ウィンドウの [**一括編集**] で、[**有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c808c-153">In the details pane, under **Bulk Edit**, click **Enable**.</span></span>
    
    <span data-ttu-id="c808c-p113">2年間以上経過したアイテムが新しいアーカイブメールボックスに移動されるという警告が表示されます。これは、作成時に新しいユーザーメールボックスに割り当てられる既定の保持ポリシーに、2年間の保持期間が設定された既定のアイテム保持ポリシーがあるからです。手順2で作成するカスタムアーカイブの既定のポリシータグには、3年間の保持期限があります。これは、3年間またはそれ以前のアイテムがアーカイブメールボックスに移動されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c808c-p113">A warning is displayed saying that items that are older than two years will be moved to the new archive mailbox. This is because the default retention policy that's assigned a new user mailbox when it's created has an archive default policy tag that has a retention age of 2 years. The custom archive default policy tag that you'll create in Step 2 has a retention age of 3 years. That means items that are 3 years or older will be moved to the archive mailbox.</span></span>
    
6. <span data-ttu-id="c808c-158">[**はい]** をクリックして警告メッセージを閉じ、選択した各メールボックスのアーカイブメールボックスを有効にするプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="c808c-158">Click **Yes** to close the warning message and start the process to enable the archive mailbox for each selected mailbox.</span></span> 
    
7. <span data-ttu-id="c808c-159">処理が完了したら、[ \*\*\*\* ![最新の](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)情報に更新] をクリックして、[**アーカイブ**] ページの一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="c808c-159">When the process is complete, click **Refresh** ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the list on the **Archive** page.</span></span> 
    
    <span data-ttu-id="c808c-160">アーカイブメールボックスは、組織内のすべてのユーザーに対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="c808c-160">The archive mailbox is enabled for all user's in your organization.</span></span>
    
    ![アーカイブメールボックスが有効になっているメールボックスの一覧](media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)
  
8. <span data-ttu-id="c808c-p114">セキュリティ&amp; /コンプライアンスセンターを開いたままにします。次の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="c808c-p114">Leave the Security &amp; Compliance Center open. You'll use it in the next step.</span></span>
    
## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a><span data-ttu-id="c808c-164">手順 2: アーカイブポリシーと削除ポリシー用の新しい保持タグを作成する</span><span class="sxs-lookup"><span data-stu-id="c808c-164">Step 2: Create new retention tags for the archive and deletion policies</span></span>

<span data-ttu-id="c808c-165">この手順では、前に説明した3つのカスタム保持タグを作成します。</span><span class="sxs-lookup"><span data-stu-id="c808c-165">In this step, you'll create the three custom retention tags that were previously described.</span></span>
  
- <span data-ttu-id="c808c-166">Alpine House 3 年間のアーカイブへの移動 (カスタムアーカイブポリシー)</span><span class="sxs-lookup"><span data-stu-id="c808c-166">Alpine House 3 Year Move to Archive (custom archive policy)</span></span>
    
- <span data-ttu-id="c808c-167">Alpine House 7 年間完全に削除 (カスタム削除ポリシー)</span><span class="sxs-lookup"><span data-stu-id="c808c-167">Alpine House 7 Year Permanently Delete (custom deletion policy)</span></span>
    
- <span data-ttu-id="c808c-168">Alpine House deleted items 5 年間削除して回復を許可する (削除済みアイテムフォルダーのカスタムタグ)</span><span class="sxs-lookup"><span data-stu-id="c808c-168">Alpine House Deleted Items 5 Years Delete and Allow Recovery (custom tag for the Deleted Items folder)</span></span>
    
<span data-ttu-id="c808c-169">新しい保持タグを作成するには、exchange Online 組織の exchange 管理センター (EAC) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c808c-169">To create new retention tags, you'll use the Exchange admin center (EAC) in your Exchange Online organization.</span></span>
  
1. <span data-ttu-id="c808c-170">セキュリティ&amp; /コンプライアンスセンターで、左上隅にあるアプリ起動ツールをクリックし、[**管理者**] タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c808c-170">In the Security &amp; Compliance Center, click the app launcher  in the upper left corner, and then click the **Admin** tile .</span></span> 
    
2. <span data-ttu-id="c808c-171">Office 365 管理センターの左側のナビゲーションウィンドウで、[**管理センター**] をクリックし、[ **Exchange**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c808c-171">In the left navigation pane of the Office 365 admin center, click **Admin centers**, and then click **Exchange**.</span></span>
    
    ![Screenshot shows the Office 365 admin center with the Admin centers option expanded and Exchange selected.](media/47399df2-0bc4-42e2-b183-07750a46bc68.png)
  
3. <span data-ttu-id="c808c-173">EAC で、[**コンプライアンス管理** \> ] [**保持タグ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c808c-173">In the EAC, go to **Compliance management** \> **Retention tags**</span></span>
    
    <span data-ttu-id="c808c-174">組織の保持タグの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-174">A list of the retention tags for your organization is displayed.</span></span>
    
### <a name="create-a-custom-archive-default-policy-tag"></a><span data-ttu-id="c808c-175">カスタムアーカイブの既定のポリシータグを作成する</span><span class="sxs-lookup"><span data-stu-id="c808c-175">Create a custom archive default policy tag</span></span>
  
<span data-ttu-id="c808c-176">最初に、3年後にアーカイブメールボックスにアイテムを移動するカスタムアーカイブの既定のポリシータグ (DPT) を作成します。</span><span class="sxs-lookup"><span data-stu-id="c808c-176">First, you'll create a custom archive default policy tag (DPT) that will move items to the archive mailbox after 3 years.</span></span> 
  
1. <span data-ttu-id="c808c-177">[**保持タグ**] ページで、[**新しいタグ**![の](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)新規作成] アイコンをクリックし、[**メールボックス全体に自動的に適用する (既定)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c808c-177">On the **Retention tags** page, click **New tag**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span> 
    
2. <span data-ttu-id="c808c-178">[**メールボックス全体に自動的に適用される新しいタグ (既定)** ] ページで、以下のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="c808c-178">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 
    
    ![新しいアーカイブの既定のポリシータグを作成するための設定](media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
1. <span data-ttu-id="c808c-180">**名前**新しい保持タグの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c808c-180">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="c808c-181">**保持アクション**保持期間が経過したときにアーカイブメールボックスにアイテムを移動するには、[**アーカイブに移動**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c808c-181">**Retention action** Select **Move to Archive** to move items to the archive mailbox when the retention period expires.</span></span> 
    
3. <span data-ttu-id="c808c-p115">**保持期間\*\*\*\*アイテムが次の期間 (日数) に達したときに**選択し、保存期間の期間を入力します。このシナリオでは、アイテムは1095日 (3 年) 後にアーカイブメールボックスに移動されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p115">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period. For this scenario, items will be moved to the archive mailbox after 1095 days (3 years).</span></span>
    
4. <span data-ttu-id="c808c-184">**コメント**オプションカスタム保持タグの目的を説明するコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="c808c-184">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="c808c-185">[**保存**] をクリックして、カスタムアーカイブ DPT を作成します。</span><span class="sxs-lookup"><span data-stu-id="c808c-185">Click **Save** to create the custom archive DPT.</span></span> 
    
    <span data-ttu-id="c808c-186">新しいアーカイブ DPT が保持タグの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-186">The new archive DPT is displayed in the list of retention tags.</span></span>
    
### <a name="create-a-custom-deletion-default-policy-tag"></a><span data-ttu-id="c808c-187">カスタム削除の既定のポリシータグを作成する</span><span class="sxs-lookup"><span data-stu-id="c808c-187">Create a custom deletion default policy tag</span></span>
  
<span data-ttu-id="c808c-188">次に、もう1つのカスタム DPT を作成しますが、これは7年後にアイテムを完全に削除する削除ポリシーとなります。</span><span class="sxs-lookup"><span data-stu-id="c808c-188">Next, you'll create another custom DPT but this one will be a deletion policy that permanently deletes items after 7 years.</span></span>
  
1. <span data-ttu-id="c808c-189">[**保持タグ**] ページで、[**新しいタグ**![の](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)新規作成] アイコンをクリックし、[**メールボックス全体に自動的に適用する (既定)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c808c-189">On the **Retention tags** page, click **New tag**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span> 
    
2. <span data-ttu-id="c808c-190">[**メールボックス全体に自動的に適用される新しいタグ (既定)** ] ページで、以下のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="c808c-190">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 
    
    ![新しい削除の既定のポリシータグを作成するための設定](media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
1. <span data-ttu-id="c808c-192">**名前**新しい保持タグの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c808c-192">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="c808c-193">**保持アクション**保持期間が経過したときにメールボックスからアイテムを削除するには、[**完全に削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c808c-193">**Retention action** Select **Permanently Delete** to purge items from the mailbox when the retention period expires.</span></span> 
    
3. <span data-ttu-id="c808c-p116">**保持期間\*\*\*\*アイテムが次の期間 (日数) に達したときに**選択し、保存期間の期間を入力します。このシナリオでは、アイテムは2555日 (7 年) 後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p116">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period. For this scenario, items will be purged after 2555 days (7 years).</span></span>
    
4. <span data-ttu-id="c808c-196">**コメント**オプションカスタム保持タグの目的を説明するコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="c808c-196">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="c808c-197">[**保存**] をクリックして、カスタム削除 DPT を作成します。</span><span class="sxs-lookup"><span data-stu-id="c808c-197">Click **Save** to create the custom deletion DPT.</span></span> 
    
    <span data-ttu-id="c808c-198">新しい削除 DPT が保持タグの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-198">The new deletion DPT is displayed in the list of retention tags.</span></span>
    
### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a><span data-ttu-id="c808c-199">削除済みアイテムフォルダーのカスタムアイテム保持ポリシータグを作成する</span><span class="sxs-lookup"><span data-stu-id="c808c-199">Create a custom retention policy tag for the Deleted Items folder</span></span>
  
<span data-ttu-id="c808c-p117">作成する最後の保持タグは、削除済みアイテムフォルダーのカスタムアイテム保持ポリシータグ (RPT) です。このタグは、削除済みアイテムフォルダー内のアイテムを5年後に削除し、ユーザーが [削除済みアイテムを復元] ツールを使用してアイテムを復元するときの回復期間を提供します。</span><span class="sxs-lookup"><span data-stu-id="c808c-p117">The last retention tag that you'll create is a custom retention policy tag (RPT) for the Deleted Items folder. This tag will delete items in the Deleted Items folder after 5 years, and provides a recovery period when users can use the Recover Deleted Items tool to recover an item.</span></span>
  
1. <span data-ttu-id="c808c-202">[**保持タグ**] ページで、[**新しいタグ** ![の](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)新規作成] アイコンをクリックし、[**既定のフォルダーに自動的に適用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c808c-202">On the **Retention tags** page, click **New tag** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to a default folder**.</span></span> 
    
2. <span data-ttu-id="c808c-203">既定の**フォルダーページに自動的に適用される新しいタグ**で、以下のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="c808c-203">On the **New tag applied automatically to a default folder** page, complete the following fields:</span></span> 
    
    ![削除済みアイテムフォルダーの新しいアイテム保持ポリシータグを作成するための設定](media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
1. <span data-ttu-id="c808c-205">**名前**新しい保持タグの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c808c-205">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="c808c-206">**[次の既定フォルダーにこのタグを適用する**]ドロップダウンリストで、[**削除済みアイテム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c808c-206">**Apply this tag to the following default folder** In the drop-down list, select **Deleted Items**.</span></span>
    
3. <span data-ttu-id="c808c-207">**保持アクション**[**削除して回復を許可**する] を選択して、保存期間の期限が切れたときにアイテムを削除します。ただし、ユーザーは削除済みアイテムの保存期間 (既定では14日) 内で削除されたアイテムを復元することができます。</span><span class="sxs-lookup"><span data-stu-id="c808c-207">**Retention action** Select **Delete and Allow Recovery** to delete items when the retention period expires, but allow users to recover a deleted item within the deleted item retention period (which by default is 14 days).</span></span> 
    
4. <span data-ttu-id="c808c-p118">**保持期間\*\*\*\*アイテムが次の期間 (日数) に達したときに**選択し、保存期間の期間を入力します。このシナリオでは、1825日 (5 年) 後にアイテムが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p118">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period. For this scenario, items will be deleted after 1825 days (5 years).</span></span>
    
5. <span data-ttu-id="c808c-210">**コメント**オプションカスタム保持タグの目的を説明するコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="c808c-210">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="c808c-211">[**保存**] をクリックして、削除済みアイテムフォルダーのカスタム RPT を作成します。</span><span class="sxs-lookup"><span data-stu-id="c808c-211">Click **Save** to create the custom RPT for the Deleted Items folder.</span></span> 
    
    <span data-ttu-id="c808c-212">新しい RPT が保持タグの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-212">The new RPT is displayed in the list of retention tags.</span></span>

## <a name="step-3-create-a-new-retention-policy"></a><span data-ttu-id="c808c-213">手順 3: 新しいアイテム保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c808c-213">Step 3: Create a new retention policy</span></span>

<span data-ttu-id="c808c-p119">カスタム保持タグを作成したら、次の手順として、新しいアイテム保持ポリシーを作成し、保持タグを追加します。手順2で作成した3つのカスタム保持タグと、最初のセクションで説明した組み込みタグを追加します。ステップ4では、この新しいアイテム保持ポリシーをユーザーメールボックスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p119">After you create the custom retention tags, the next step is to create a new retention policy and add the retention tags. You'll add the three custom retention tags that you created in Step 2, and the built-in tags that were mentioned in the first section. In Step 4, you'll assign this new retention policy to user mailboxes.</span></span>
  
1. <span data-ttu-id="c808c-217">EAC で、[**コンプライアンス管理** \> ] [**アイテム保持ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c808c-217">In the EAC, go to **Compliance management** \> **Retention policies**.</span></span>
    
2. <span data-ttu-id="c808c-218">[**アイテム保持ポリシー** ] ページで\*\*\*\* ![、[新規](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)作成] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c808c-218">On the **Retention policies** page, click **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>
    
3. <span data-ttu-id="c808c-219">[**名前**] ボックスに、新しいアイテム保持ポリシーの名前を入力します。たとえば、 **Alpine House のアーカイブおよび削除ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="c808c-219">In the **Name** box, type a name for the new retention policy; for example, **Alpine House Archive and Deletion Policy**.</span></span> 
    
4. <span data-ttu-id="c808c-220">[**保持タグ**] で\*\*\*\* ![、[新規](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)アイコンの追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c808c-220">Under **Retention tags**, click **Add** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>
    
    <span data-ttu-id="c808c-p120">組織内の保持タグの一覧が表示されます。メモ手順2で作成したカスタムタグが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p120">A list of the retention tags in your organization is displayed. Note the custom tags that you created in Step 2 are displayed.</span></span>
    
5. <span data-ttu-id="c808c-p121">次のスクリーンショットで強調表示されている9つの保持タグを追加します (これらのタグの詳細については、「 [more information](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo) 」セクションを参照してください)。保持タグを追加するには、それを選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c808c-p121">Add the 9 retention tags that are highlighted in the following screenshot (these tags are described in more detail in the [More information](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo) section). To add a retention tag, select it and then click **Add**.</span></span> 
    
    ![新しいアイテム保持ポリシーに保持タグを追加する](media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > <span data-ttu-id="c808c-226">複数の保持タグを選択するには、 **Ctrl**キーを押しながら各タグをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c808c-226">You can select multiple retention tags by holding down the **Ctrl** key and then clicking each tag.</span></span> 
  
6. <span data-ttu-id="c808c-227">保持タグを追加したら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c808c-227">After you've added the retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="c808c-228">[**新しいアイテム保持ポリシー** ] ページで、[**保存**] をクリックして新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c808c-228">On the **New retention policy** page, click **Save** to create the new policy.</span></span> 
    
    <span data-ttu-id="c808c-p122">新しいアイテム保持ポリシーが一覧に表示されます。このチェックボックスをオンにすると、詳細ウィンドウにリンクされている保持タグが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p122">The new retention policy is displayed in the list. Select it to display the retention tags linked to it in the details pane.</span></span>
    
    ![新しいアイテム保持ポリシーとリンクされた保持タグのリスト](media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a><span data-ttu-id="c808c-232">手順 4: 新しいアイテム保持ポリシーをユーザーメールボックスに割り当てる</span><span class="sxs-lookup"><span data-stu-id="c808c-232">Step 4: Assign the new retention policy to user mailboxes</span></span>

<span data-ttu-id="c808c-p123">新しいメールボックスが作成されると、default mrm policy という名前のアイテム保持ポリシーが既定で割り当てられます。この手順では、手順3で作成した新しいアイテム保持ポリシーを組織内のユーザーのメールボックスに割り当てることによって、このアイテム保持ポリシーを置き換えます (メールボックスに割り当てられる保持ポリシーは1つだけです)。この手順では、組織内のすべてのメールボックスに新しいポリシーを割り当てることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c808c-p123">When a new mailbox is created, a retention policy named Default MRM policy is assigned to it by default. In this step, you'll replace this retention policy (because a mailbox can have only one retention policy assigned to it) by assigning the new retention policy that you created in Step 3 to the user mailboxes in your organization. This step assumes that you'll assign the new policy to all mailboxes in your organization.</span></span>
  
1. <span data-ttu-id="c808c-236">EAC で、**[受信者]** \> **[メールボックス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c808c-236">In the EAC, go to **Recipients** \> **Mailboxes**.</span></span>
    
    <span data-ttu-id="c808c-237">組織内のすべてのユーザーメールボックスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-237">A list of all user mailboxes in your organization is displayed.</span></span> 
    
2. <span data-ttu-id="c808c-238">一覧の最初のメールボックスをクリックし、 **Shift**キーを押しながら、一覧の最後のメールボックスをクリックして、すべてのメールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="c808c-238">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 
    
3. <span data-ttu-id="c808c-239">EAC の右側にある詳細ウィンドウの [**一括編集**] で、[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c808c-239">In the details pane on the right side of the EAC, under **Bulk Edit**, click **More options**.</span></span>
    
4. <span data-ttu-id="c808c-240">**[アイテム保持ポリシー]** 下で **[更新]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c808c-240">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="c808c-241">[**アイテム保持ポリシーの一括割り当て**] ページの [**アイテム保持ポリシーの選択**] ドロップダウンリストで、手順3で作成したアイテム保持ポリシーを選択します。たとえば、 **Alpine House のアーカイブとアイテム保持ポリシー**があります。</span><span class="sxs-lookup"><span data-stu-id="c808c-241">On the **Bulk assign retention policy** page, in the **Select the retention policy** drop-down list, select the retention policy that you created in Step 3; for example, **Alpine House Archive and Retention Policy**.</span></span>
    
6. <span data-ttu-id="c808c-242">[**保存**] をクリックして、新しいアイテム保持ポリシーの割り当てを保存します。</span><span class="sxs-lookup"><span data-stu-id="c808c-242">Click **Save** to save the new retention policy assignment.</span></span> 
    
7. <span data-ttu-id="c808c-243">新しいアイテム保持ポリシーがメールボックスに割り当てられていることを確認するには、次の操作を行います。 [メールボックス] ページでメールボックスを選択し、[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c808c-243">To verify that the new retention policy was assigned to mailboxes, you can do the following: select a mailbox on the Mailboxes page, and then click Edit.</span></span> 
    
1. <span data-ttu-id="c808c-244">[**メールボックス**] ページでメールボックスを選択し\*\*\*\* ![、[](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png)編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c808c-244">Select a mailbox on the **Mailboxes** page, and then click **Edit** ![Edit](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png).</span></span> 
    
2. <span data-ttu-id="c808c-245">選択したユーザーのメールボックスのプロパティページで、[**メールボックスの機能**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c808c-245">On the mailbox properties page for the selected user, click **Mailbox features**.</span></span>
    
    <span data-ttu-id="c808c-246">メールボックスに割り当てられた新しいポリシーの名前が、[**アイテム保持ポリシー** ] ドロップダウンリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-246">The name of the new policy assigned to the mailbox is displayed in the **Retention policy** drop-down list.</span></span> 

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a><span data-ttu-id="c808c-247">オプション手順 5: 管理フォルダーアシスタントを実行して新しい設定を適用する</span><span class="sxs-lookup"><span data-stu-id="c808c-247">(Optional) Step 5: Run the Managed Folder Assistant to apply the new settings</span></span>

<span data-ttu-id="c808c-p124">手順4で新しいアイテム保持ポリシーをメールボックスに適用した後、メールボックスに新しいアイテム保持設定を適用するには、Exchange Online で最大7日かかることがあります。これは、管理フォルダーアシスタントと呼ばれるプロセスが7日ごとにメールボックスを処理するからです。管理フォルダーアシスタントの実行を待機する代わりに、Exchange Online PowerShell で " **Start/managedfolderassistant** " コマンドレットを実行することによって、これを強制的に実行することができます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p124">After you apply the new retention policy to mailboxes in Step 4, it can take up to 7 days in Exchange Online for the new retention settings to be applied to the mailboxes. This is because a process called the Managed Folder Assistant processes mailboxes once every 7 days. Instead of waiting for the Managed Folder Assistant to run, you can force this to happen by running the **Start-ManagedFolderAssistant** cmdlet in Exchange Online PowerShell.</span></span> 
  
 <span data-ttu-id="c808c-p125">**管理フォルダーアシスタントを実行するとどうなりますか。** アイテム保持ポリシーの設定を適用するには、メールボックス内のアイテムを調べて、保持の対象であるかどうかを判断します。その後、適切な保持タグを使用してアイテムに保存期間をスタンプし、保存期間を過ぎたアイテムに対して指定された保持アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c808c-p125">**What happens when you run the Managed Folder Assistant?** It applies the settings in the retention policy by inspecting items in the mailbox and determining whether they're subject to retention. It then stamps items subject to retention with the appropriate retention tag, and then takes the specified retention action on items past their retention age.</span></span> 
  
<span data-ttu-id="c808c-254">Exchange Online PowerShell に接続し、組織内のすべてのメールボックスで管理フォルダーアシスタントを実行する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c808c-254">Here are the steps to connect to Exchange Online PowerShell, and then run the Managed Folder Assistant on every mailbox in your organization.</span></span>
  
1. <span data-ttu-id="c808c-255">ローカル コンピューターで、Windows PowerShell を開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c808c-255">On your local computer, open Windows PowerShell and run the following command.</span></span>
    
    ```
    $UserCredential = Get-Credential
    ```

    <span data-ttu-id="c808c-256">[ **Windows PowerShell 資格情報の要求**] ダイアログボックスで、Office 365 グローバル管理者アカウントのユーザー名とパスワードを入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c808c-256">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global admin account, and then click **OK**.</span></span>
    
2. <span data-ttu-id="c808c-257">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c808c-257">Run the following command.</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. <span data-ttu-id="c808c-258">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c808c-258">Run the following command.</span></span>
    
    ```
    Import-PSSession $Session
    ```

4. <span data-ttu-id="c808c-259">Exchange Online 組織に接続されたことを検証するために、次のコマンドを実行して、組織内のすべてのメールボックスのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="c808c-259">To verify that you're connected to your Exchange Online organization, run the following command to get a list of all the mailboxes in your organization.</span></span>
    
    ```
    Get-Mailbox
    ```

    > [!NOTE]
    > <span data-ttu-id="c808c-260">詳細については、または exchange online 組織への接続に問題がある場合は、「 [exchange online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=517283)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c808c-260">For more information or if you have problems connecting to your Exchange Online organization, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span> 
  
5. <span data-ttu-id="c808c-261">組織内のすべてのユーザーメールボックスに対して管理フォルダーアシスタントを開始するには、次の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c808c-261">Run the following two commands to start the Managed Folder Assistant for all user mailboxes in your organization.</span></span>
    
    ```
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

<span data-ttu-id="c808c-p126">それです！Alpine House 組織のアーカイブと削除のポリシーを設定している。</span><span class="sxs-lookup"><span data-stu-id="c808c-p126">That's it! You've set up an archive and deletion policy for the Alpine House organization.</span></span>
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a><span data-ttu-id="c808c-264">オプション手順 6: 新しいアイテム保持ポリシーを組織の既定に設定する</span><span class="sxs-lookup"><span data-stu-id="c808c-264">(Optional) Step 6: Make the new retention policy the default for your organization</span></span>

<span data-ttu-id="c808c-p127">手順4では、既存のメールボックスに新しいアイテム保持ポリシーを割り当てる必要があります。ただし、今後作成される新しいメールボックスに新しいアイテム保持ポリシーが割り当てられるように、Exchange Online を構成することができます。これを行うには、Exchange Online PowerShell を使用して組織の既定のメールボックスプランを更新します。*メールボックス計画*は、新しいメールボックスのプロパティを自動的に構成するテンプレートです。 このオプションの手順では、メールボックスプランに割り当てられている現在のアイテム保持ポリシー (既定では、既定の mrm ポリシー) を手順3で作成したアイテム保持ポリシーに置き換えることができます。メールボックスプランを更新すると、新しいアイテム保持ポリシーが新しいメールボックスに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p127">In Step 4, you have to assign the new retention policy to existing mailboxes. But you can configure Exchange Online so that the new retention policy is assigned to new mailboxes that are created in the future. You do this by using Exchange Online PowerShell to update your organization's default mailbox plan. A *mailbox plan* is a template that automatically configures properties on new mailboxes.  In this optional step, you can replace the current retention policy that's assigned to the mailbox plan (by default, the Default MRM Policy) with the retention policy that you created in Step 3. After you update the mailbox plan, the new retention policy will be assigned to new mailboxes.</span></span>

1. <span data-ttu-id="c808c-271">[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?LinkId=517283)か、手順5を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c808c-271">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) or see Step 5.</span></span>

2. <span data-ttu-id="c808c-272">組織内のメールボックスプランに関する情報を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c808c-272">Run the following command to display information about the mailbox plans in your organization.</span></span>

    ```
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```
    <span data-ttu-id="c808c-273">既定として設定されているメールボックスプランをメモします。</span><span class="sxs-lookup"><span data-stu-id="c808c-273">Note the mailbox plan that's set as the default.</span></span>

3. <span data-ttu-id="c808c-p128">次のコマンドを実行して、手順3で作成した新しいアイテム保持ポリシー (たとえば、 **Alpine House Archive and retention policy**) を既定のメールボックス計画に割り当てます。この例では、既定のメールボックスプランの名前が**exchangeonline enterprise**であると仮定しています。</span><span class="sxs-lookup"><span data-stu-id="c808c-p128">Run the following command to assign the new retention policy that you created in Step 3 (for example, **Alpine House Archive and Retention Policy**) to the default mailbox plan. This example assumes the name of the default mailbox plan is **ExchangeOnlineEnterprise**.</span></span>

    ```
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```
4. <span data-ttu-id="c808c-276">手順2のコマンドを再実行して、既定のメールボックス計画に割り当てられているアイテム保持ポリシーが変更されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c808c-276">You can re-run the command in step 2 to verify that the retention policy assigned to the default mailbox plan was changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="c808c-277">詳細情報</span><span class="sxs-lookup"><span data-stu-id="c808c-277">More information</span></span>

- <span data-ttu-id="c808c-p129">保存期間はどのように計算されますか?メールボックスアイテムの保持期間は、配信日または作成日 (送信されないが、ユーザーによって作成された下書きメッセージなど) から計算されます。管理フォルダーアシスタントは、メールボックス内のアイテムを処理するときに、保持タグを持つすべてのアイテムの開始日と有効期限を、[削除して回復を許可する] または [完全に削除する] 操作を使用してスタンプします。アーカイブタグがあるアイテムには、移動日がスタンプされます。</span><span class="sxs-lookup"><span data-stu-id="c808c-p129">How is retention age calculated? The retention age of mailbox items is calculated from the date of delivery or the date of creation for items such as draft messages that aren't sent but are created by the user. When the Managed Folder Assistant processes items in a mailbox, it stamps a start date and an expiration date for all items that have retention tags with the Delete and Allow Recovery or Permanently Delete retention action. Items that have an archive tag are stamped with a move date.</span></span> 
    
- <span data-ttu-id="c808c-282">次の表では、このトピックの手順に従って作成されたカスタムアイテム保持ポリシーに追加される各保持タグの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="c808c-282">The following table provides more information about each retention tag that is added to the custom retention policy that was created by following the steps in this topic.</span></span>
    
    |<span data-ttu-id="c808c-283">**保持タグ**</span><span class="sxs-lookup"><span data-stu-id="c808c-283">**Retention tag**</span></span>|<span data-ttu-id="c808c-284">**このタグの内容**</span><span class="sxs-lookup"><span data-stu-id="c808c-284">**What this tag does**</span></span>|<span data-ttu-id="c808c-285">**組み込みまたはユーザー設定の場合**</span><span class="sxs-lookup"><span data-stu-id="c808c-285">**Built-in or custom?**</span></span>|<span data-ttu-id="c808c-286">**Type**</span><span class="sxs-lookup"><span data-stu-id="c808c-286">**Type**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c808c-287">Alpine House 3 年間のアーカイブへの移動</span><span class="sxs-lookup"><span data-stu-id="c808c-287">Alpine House 3 Year Move to Archive</span></span>  <br/> |<span data-ttu-id="c808c-288">過去1095日 (3 年) のアイテムをアーカイブメールボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="c808c-288">Moves items that are 1095 days (3 years) old to the archive mailbox.</span></span>  <br/> |<span data-ttu-id="c808c-289">Custom (「[手順 2: アーカイブポリシーと削除ポリシーの新しい保持タグを作成](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)する」を参照)</span><span class="sxs-lookup"><span data-stu-id="c808c-289">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="c808c-290">既定のポリシータグ (アーカイブ)、このタグは、メールボックス全体に自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-290">Default Policy Tag (archive); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="c808c-291">Alpine House 7 年間完全に削除</span><span class="sxs-lookup"><span data-stu-id="c808c-291">Alpine House 7 Year Permanently Delete</span></span>  <br/> |<span data-ttu-id="c808c-292">7年前の時点でプライマリメールボックスまたはアーカイブメールボックスのアイテムを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="c808c-292">Permanently deletes items in the primary mailbox or the archive mailbox when they are 7 years old.</span></span>  <br/> |<span data-ttu-id="c808c-293">Custom (「[手順 2: アーカイブポリシーと削除ポリシーの新しい保持タグを作成](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)する」を参照)</span><span class="sxs-lookup"><span data-stu-id="c808c-293">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="c808c-294">既定のポリシータグ (削除)。このタグは、メールボックス全体に自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-294">Default Policy Tag (deletion); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="c808c-295">Alpine House Deleted Items 5 年間削除して回復を許可する</span><span class="sxs-lookup"><span data-stu-id="c808c-295">Alpine House Deleted Items 5 Years Delete and Allow Recovery</span></span>  <br/> |<span data-ttu-id="c808c-p130">5年前の削除済みアイテムフォルダーからアイテムを削除します。ユーザーは、これらのアイテムを削除してから14日後に復元できます。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c808c-p130">Deletes items from the Deleted Items folder that are 5 years old. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="c808c-298">Custom (「[手順 2: アーカイブポリシーと削除ポリシーの新しい保持タグを作成](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)する」を参照)</span><span class="sxs-lookup"><span data-stu-id="c808c-298">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="c808c-299">アイテム保持ポリシータグ (削除済みアイテム)、このタグは、[削除済みアイテム] フォルダー内のアイテムに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-299">Retention Policy Tag (Deleted Items); this tag is automatically applied to items in the Deleted items folder.</span></span>  <br/> |
    |<span data-ttu-id="c808c-300">回復可能なアイテム-14 日でアーカイブへ移動</span><span class="sxs-lookup"><span data-stu-id="c808c-300">Recoverable Items 14 days Move to Archive</span></span>  <br/> |<span data-ttu-id="c808c-301">回復可能なアイテムフォルダーにあるアイテムを、14日間、アーカイブメールボックスの [回復可能なアイテム] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c808c-301">Moves items that have been in the Recoverable Items folder for 14 days to the Recoverable Items folder in the archive mailbox.</span></span>  <br/> |<span data-ttu-id="c808c-302">組み込み</span><span class="sxs-lookup"><span data-stu-id="c808c-302">Built-in</span></span>  <br/> |<span data-ttu-id="c808c-303">アイテム保持ポリシータグ (回復可能なアイテム)、このタグは、[回復可能なアイテム] フォルダー内のアイテムに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-303">Retention Policy Tag (Recoverable Items); this tag is automatically applied to items in the Recoverable Items folder.</span></span>  <br/> |
    |<span data-ttu-id="c808c-304">迷惑メール</span><span class="sxs-lookup"><span data-stu-id="c808c-304">Junk Email</span></span>  <br/> |<span data-ttu-id="c808c-p131">[迷惑メール] フォルダーに30日間含まれていたアイテムを完全に削除します。ユーザーは、これらのアイテムを削除してから14日後に復元できます。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c808c-p131">Permanently deletes items that have been in the Junk Email folder for 30 days. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="c808c-307">組み込み</span><span class="sxs-lookup"><span data-stu-id="c808c-307">Built-in</span></span>  <br/> |<span data-ttu-id="c808c-308">アイテム保持ポリシータグ (迷惑メール);このタグは、[迷惑メール] フォルダー内のアイテムに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c808c-308">Retention Policy Tag (Junk Email); this tag is automatically applied to items in Junk Email folder.</span></span>  <br/> |
    |<span data-ttu-id="c808c-309">1 か月で削除</span><span class="sxs-lookup"><span data-stu-id="c808c-309">1 Month Delete</span></span>  <br/> |<span data-ttu-id="c808c-p132">30日以上経過したアイテムを完全に削除します。ユーザーは、これらのアイテムを削除してから14日後に復元できます。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c808c-p132">Permanently deletes items that are 30 days old. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="c808c-312">組み込み</span><span class="sxs-lookup"><span data-stu-id="c808c-312">Built-in</span></span>  <br/> |<span data-ttu-id="c808c-313">作成者このタグは、ユーザーが適用することができます。</span><span class="sxs-lookup"><span data-stu-id="c808c-313">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="c808c-314">1 年で削除</span><span class="sxs-lookup"><span data-stu-id="c808c-314">1 Year Delete</span></span>  <br/> |<span data-ttu-id="c808c-p133">過去365日のアイテムを完全に削除します。ユーザーは、これらのアイテムを削除してから14日後に復元できます。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c808c-p133">Permanently deletes items that are 365 days old. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="c808c-317">組み込み</span><span class="sxs-lookup"><span data-stu-id="c808c-317">Built-in</span></span>  <br/> |<span data-ttu-id="c808c-318">作成者このタグは、ユーザーが適用することができます。</span><span class="sxs-lookup"><span data-stu-id="c808c-318">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="c808c-319">削除しない</span><span class="sxs-lookup"><span data-stu-id="c808c-319">Never Delete</span></span>  <br/> |<span data-ttu-id="c808c-320">このタグは、アイテム保持ポリシーによってアイテムが削除されないようにします。</span><span class="sxs-lookup"><span data-stu-id="c808c-320">This tag prevent items from being deleted by a retention policy.</span></span>  <br/> |<span data-ttu-id="c808c-321">組み込み</span><span class="sxs-lookup"><span data-stu-id="c808c-321">Built-in</span></span>  <br/> |<span data-ttu-id="c808c-322">作成者このタグは、ユーザーが適用することができます。</span><span class="sxs-lookup"><span data-stu-id="c808c-322">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="c808c-323">個人 - 1 年でアーカイブへ移動</span><span class="sxs-lookup"><span data-stu-id="c808c-323">Personal 1 year move to archive</span></span>  <br/> |<span data-ttu-id="c808c-324">1年後にアイテムをアーカイブメールボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="c808c-324">Moves items to the archive mailbox after 1 year.</span></span>  <br/> |<span data-ttu-id="c808c-325">組み込み</span><span class="sxs-lookup"><span data-stu-id="c808c-325">Built-in</span></span>  <br/> |<span data-ttu-id="c808c-326">作成者このタグは、ユーザーが適用することができます。</span><span class="sxs-lookup"><span data-stu-id="c808c-326">Personal; this tag can be applied by users.</span></span>  <br/> |
   
    > <span data-ttu-id="c808c-p134"><sup>\*</sup>ユーザーは、outlook および web 上の outlook (旧称 outlook web App) で削除済みアイテムを復元するツールを使用して、削除済みアイテムの保存期間 (既定では、Exchange Online では14日) 内の削除済みアイテムを復元できます。管理者は、Windows PowerShell を使用して、削除済みアイテムの保存期間を最大で30日に増やすことができます。詳細については、「 [Windows 版 Outlook で削除済みアイテムを復元](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)する」および「 [Exchange Online のメールボックスの削除済みアイテムの保存期間を変更](https://go.microsoft.com/fwlink/p/?LinkId=286940)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c808c-p134"><sup>\*</sup> Users can use the Recover Deleted Items tool in Outlook and Outlook on the web (formerly known as Outlook Web App) to recover a deleted item within the deleted item retention period, which by default is 14 days in Exchange Online. An administrator can use Windows PowerShell to increase the deleted item retention period to a maximum of 30 days. For more information, see: [Recover deleted items in Outlook for Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) and [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940)</span></span>
  
- <span data-ttu-id="c808c-p135">回復可能なアイテムを使用して、 **14 日後にアーカイブ保持タグに移動する**と、ユーザーのプライマリメールボックス内の回復可能なアイテムフォルダーの記憶域を解放することができます。これは、ユーザーのメールボックスが保持されている場合に便利です。つまり、ユーザーのメールボックスが完全に削除されることはありません。アイテムをアーカイブメールボックスに移動せずに、プライマリメールボックスの [回復可能なアイテム] フォルダーの記憶域のクォータに到達できるようになります。詳細については、「[ホールド状態のメールボックスの回復可能なアイテムのクォータを増やす](https://go.microsoft.com/fwlink/p/?LinkId=786479)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c808c-p135">Using the **Recoverable Items 14 days Move to Archive** retention tag helps free up storage space in the Recoverable Items folder in the user's primary mailbox. This is useful when a user's mailbox is placed on hold, which means nothing is ever permanently deleted the user's mailbox. Without moving items to the archive mailbox, it's possible the storage quota for the Recoverable Items folder in the primary mailbox will be reached. For more information about this and how to avoid it, see [Increase the Recoverable Items quota for mailboxes on hold](https://go.microsoft.com/fwlink/p/?LinkId=786479).</span></span>
