---
title: Office 365 組織内のメールボックスのアーカイブと削除ポリシーを設定します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
description: アーカイブを作成し、Office 365 の削除ポリシーがユーザーのアーカイブ メールボックスにアイテムを自動的に移動します。
ms.openlocfilehash: 903a91c590c47ad5de0b89ae51a25983221d2ffe
ms.sourcegitcommit: 031781d0eecf33baabcd03ea53546d41076062b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240580"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-office-365-organization"></a><span data-ttu-id="564b4-103">Office 365 組織内のメールボックスのアーカイブと削除ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="564b4-103">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>

 <span data-ttu-id="564b4-p101">Office 365 の管理者は、自動的にユーザーのアーカイブ メールボックスにアイテムを移動し、メールボックスからアイテムを自動的に削除、アーカイブと削除のポリシーを作成できます。管理者は、メールボックスに割り当てられているし、一定の時間とするも後を削除アイテムのメールボックスから特定の保存期間の制限に到達する後、ユーザーのアーカイブ メールボックスにアイテムを移動する保持ポリシーを作成することによって行われます。どのような項目を決定する実際の規則は、移動または削除され、するような場合と呼ばれる保持タグです。保持タグは、次に、ユーザーのメールボックスに割り当てられているリテンション ・ ポリシーにリンクされています。保持タグでは、個々 のメッセージとユーザーのメールボックス内のフォルダーに保存期間の設定が適用されます。メールボックスのメッセージは、どのくらいの時間と、メッセージが指定された保有期間に達したときに実行される処理を定義します。メッセージには、その保有期間に達すると、ユーザーのアーカイブ メールボックスに移動するか、または削除されます。</span><span class="sxs-lookup"><span data-stu-id="564b4-p101">In Office 365, admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox. The admin does this by creating a retention policy that's assigned to mailboxes, and moves items to a user's archive mailbox after a certain period of time and that also deletes items from the mailbox after they reach a certain age limit. The actual rules that determine what items are moved or deleted and when that happens are called retention tags. Retention tags are linked to a retention policy, that in turn is assigned to a user's mailbox. A retention tag applies retention settings to individual messages and folders in a user's mailbox. It defines how long a message remains in the mailbox and what action is taken when the message reaches the specified retention age. When a message reaches its retention age, it's either moved to the user's archive mailbox or it's deleted.</span></span> 
  
<span data-ttu-id="564b4-p102">この資料の手順には、アルペン ハウスという名前の架空の組織のアーカイブおよび保存ポリシーを設定します。このポリシーを設定すると、次のタスクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="564b4-p102">The steps in this article will set up an archiving and retention policy for a fictitious organization named Alpine House. Setting up this policy includes the following tasks:</span></span>
  
- <span data-ttu-id="564b4-p103">組織内のすべてのユーザーのアーカイブ メールボックスを有効にします。これにより、ユーザーはメールボックスの格納域の追加、およびリテンション ・ ポリシーは、アーカイブ メールボックスにアイテムを移動できますようにします。それについての説明も移動することによって、ユーザー ストアのアーカイブ情報アイテムのアーカイブ メールボックスにします。</span><span class="sxs-lookup"><span data-stu-id="564b4-p103">Enabling an archive mailbox for every user in the organization. This gives users addition mailbox storage, and is required so that a retention policy can move items to the archive mailbox. It also let's a user store archival information by moving items to their archive mailbox.</span></span> 
    
- <span data-ttu-id="564b4-116">次の 3 つのユーザー設定の保持タグを作成します。</span><span class="sxs-lookup"><span data-stu-id="564b4-116">Creating three custom retention tags that do the following:</span></span> 
    
  - <span data-ttu-id="564b4-p104">3 歳のユーザーのアーカイブ メールボックスにアイテムを自動的に移動します。アーカイブ メールボックスにアイテムを移動は、ユーザーのプライマリ メールボックス内の領域を解放します。</span><span class="sxs-lookup"><span data-stu-id="564b4-p104">Automatically moves items that are 3 years old to the user's archive mailbox. Moving items to the archive mailbox frees up space in a user's primary mailbox.</span></span>
    
  - <span data-ttu-id="564b4-p105">自動的に削除済みアイテム フォルダーから 5 年前のアイテムを削除します。これは、また、ユーザーのプライマリ メールボックス内の領域を解放します。ユーザーは、必要に応じて、これらのアイテムを回復する機会を与えられます。詳細については[詳細](#more-information)セクションの脚注を参照してください。</span><span class="sxs-lookup"><span data-stu-id="564b4-p105">Automatically deletes items that are 5 years old from the Deleted Items folder. This also frees up space in the user's primary mailbox. User's will have the opportunity to recover these items if necessary. See the footnote in the [More information](#more-information) section for more details.</span></span> 
    
  - <span data-ttu-id="564b4-p106">自動的に (かつ完全に) は、両方のプライマリから 7 歳とアーカイブ先のメールボックスのアイテムを削除します。規制のコンプライアンスのためいくつかの組織は、一定の時間の電子メールを保持する必要があります。この期間が過ぎると、組織することもこれらの項目のユーザーのメールボックスを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="564b4-p106">Automatically (and permanently) deletes items that are 7 years old from both the primary and archive mailbox. Because of compliance regulations, some organization's are required to retain email for a certain period of time. After this time period expires, an organization might want to permanently remove these items user mailboxes.</span></span> 
    
- <span data-ttu-id="564b4-p107">新しい保持ポリシーを作成してに新しいカスタム保持期間のタグを追加します。さらに、新しい保持ポリシーに組み込みの保持タグを追加することもあります。これには、ユーザーが各自のメールボックス内のアイテムに割り当てることができます個人用のタグが含まれます。アーカイブ メールボックスの回復可能なアイテム] フォルダーに、ユーザーのプライマリ メールボックスの回復可能なアイテム] フォルダーからアイテムを移動する保持タグを追加することもあります。このを使用するは、保留中のユーザーのメールボックスが配置されると、ユーザーの回復可能なアイテム] フォルダー内の領域を解放します。</span><span class="sxs-lookup"><span data-stu-id="564b4-p107">Creating a new retention policy and adding the new custom retention tags to it. Additionally, you'll also add built-in retention tags to the new retention policy. This includes personal tags that users can assign to items in their mailbox. You'll also add a retention tag that moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox. This helps free up space in a user's Recoverable Items folder when their mailbox is placed on hold.</span></span>
    
<span data-ttu-id="564b4-p108">組織内のメールボックスのアーカイブと削除ポリシーを設定するには、この資料の手順の一部またはすべてを実行することができます。組織内のすべてのメールボックスに実装する前にいくつかのメールボックスに対してこの手順をテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="564b4-p108">You can follow some or all of the steps in this article to set up an archive and deletion policy for mailboxes in your own organization. We recommend that you test this process on a few mailboxes before implementing it on all mailboxes in your organization.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="564b4-133">はじめに</span><span class="sxs-lookup"><span data-stu-id="564b4-133">Before you begin</span></span>

- <span data-ttu-id="564b4-134">このトピックの手順を実行するのには Office 365 の組織のグローバル管理者があります。</span><span class="sxs-lookup"><span data-stu-id="564b4-134">You have to be a global administrator in your Office 365 organization to perform the steps in this topic.</span></span> 
    
-  <span data-ttu-id="564b4-p109">Office 365 に新しいユーザー アカウントを作成して Exchange Online ライセンスをユーザーに割り当てる、ユーザーのメールボックスが自動的に作成します。メールボックスが作成されると、MRM ポリシーを既定の名前、デフォルトの保持ポリシーが割り当てに自動的にします。この記事では、新しい保持ポリシーを作成し、し、ユーザーのメールボックスに割り当てること、MRM の既定のポリシーを置き換えることです。メールボックスは、任意の時点でそれに割り当てられている 1 つだけのリテンション ・ ポリシーを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="564b4-p109">When you create a new user account in Office 365 and assign the user an Exchange Online license, a mailbox is automatically created for the user. When the mailbox is created, it's automatically assigned a default retention policy, named Default MRM Policy. In this article, you will create a new retention policy and then assign it to user mailboxes, replacing the Default MRM policy. A mailbox can have only one retention policy assigned to it at any one time.</span></span>
    
- <span data-ttu-id="564b4-139">詳細については、保持タグおよびアイテム保持ポリシーに関する Exchange オンラインでは、[保持タグとアイテム保持ポリシー](https://go.microsoft.com/fwlink/p/?LinkId=404424)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="564b4-139">To learn more about retention tags and retention policies in Exchange Online, see [Retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkId=404424).</span></span>
    
## <a name="step-1-enable-archive-mailboxes-for-users"></a><span data-ttu-id="564b4-140">手順 1: 有効にするアーカイブ メールボックスは、ユーザーの</span><span class="sxs-lookup"><span data-stu-id="564b4-140">Step 1: Enable archive mailboxes for users</span></span>

<span data-ttu-id="564b4-p110">最初の手順は、組織内の各ユーザーのアーカイブ メールボックスを有効にするのには。ユーザーのアーカイブ メールボックスを有効にするため、保有期間の有効期限が切れた後、保持タグ保持アクションが「アーカイブへ移動」アイテムを移動できます。</span><span class="sxs-lookup"><span data-stu-id="564b4-p110">The first step is to enable the archive mailbox for each user in your organization. A user's archive mailbox has to be enabled so that a retention tag with a "Move to Archive" retention action can move the item after the retention age expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="564b4-p111">だけである限り、プロセスを完了する前にいくつかの時点では有効にしているは、アーカイブ メールボックスの過程でいつでもを有効にできます。アーカイブ先のメールボックスが有効でない場合、アーカイブ ポリシーが割り当てられているすべてのアイテムに何は実行されません。</span><span class="sxs-lookup"><span data-stu-id="564b4-p111">You can enable archive mailboxes any time during this process, just as long as they're enabled at some point before you complete the process. If an archive mailbox isn't enabled, no action is taken on any items that have an archive policy assigned to it.</span></span> 
  
1. <span data-ttu-id="564b4-145">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="564b4-145">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="564b4-146">グローバル管理者アカウントを使用して Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="564b4-146">Sign in to Office 365 using your global administrator account.</span></span>
    
    
3. <span data-ttu-id="564b4-147">セキュリティ&amp;コンプライアンス部門、**データ ・ ガバナンス**へ移動\>**アーカイブ**します。</span><span class="sxs-lookup"><span data-stu-id="564b4-147">In the Security &amp; Compliance Center, go to **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="564b4-148">組織内のメールボックスの一覧が表示されると、対応するアーカイブ メールボックスを有効または無効にするかどうか。</span><span class="sxs-lookup"><span data-stu-id="564b4-148">A list of the mailboxes in your organization is displayed and whether the corresponding archive mailbox is enabled or disabled.</span></span> 
    
4. <span data-ttu-id="564b4-149">**Shift**キーを押し、一覧の最初のクリックし、リスト内の最後の 1 つですべてのメールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="564b4-149">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="564b4-p112">この手順では、アーカイブ メールボックスが有効にしないことを前提としています。、有効なアーカイブにすべてのメールボックスがある場合、 **Ctrl**キーを押し各メールボックスを無効にしたアーカイブ メールボックスを持つをクリックします。または、アーカイブ先のメールボックスが有効またはメールボックスを選択しやすくには無効になっているかどうかに基づいて行を並べ替えるには**アーカイブ メールボックス**の列見出しをクリックすることができます。</span><span class="sxs-lookup"><span data-stu-id="564b4-p112">This step assumes that no archive mailboxes are enabled. If you have any mailboxes with the archive enabled, hold down the **Ctrl** key and click each mailbox that has a disabled archive mailbox. Or you can click the **Archive mailbox** column header to sort the rows based on whether the archive mailbox is enabled or disabled to make it easier to select mailboxes.</span></span> 
  
5. <span data-ttu-id="564b4-153">詳細ウィンドウで、[**一括編集**を、[**有効**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-153">In the details pane, under **Bulk Edit**, click **Enable**.</span></span>
    
    <span data-ttu-id="564b4-p113">2 年より古い項目を新しいアーカイブ メールボックスに移動されることを示す警告が表示されます。デフォルトの保存ポリシーが割り当てられている新しいユーザーのメールボックスが作成されたときに 2 年間の保有期間のあるアーカイブの既定ポリシー タグを持つためにです。手順 2 で作成するカスタム ・ アーカイブの既定ポリシー タグは、3 年間の保有期間を持ちます。3 年間のアイテムは、古いまたはアーカイブ メールボックスに移動されます。</span><span class="sxs-lookup"><span data-stu-id="564b4-p113">A warning is displayed saying that items that are older than two years will be moved to the new archive mailbox. This is because the default retention policy that's assigned a new user mailbox when it's created has an archive default policy tag that has a retention age of 2 years. The custom archive default policy tag that you'll create in Step 2 has a retention age of 3 years. That means items that are 3 years or older will be moved to the archive mailbox.</span></span>
    
6. <span data-ttu-id="564b4-158">**[はい]** 警告メッセージを閉じるし、選択したメールボックスのアーカイブ メールボックスを有効にするプロセスを開始する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-158">Click **Yes** to close the warning message and start the process to enable the archive mailbox for each selected mailbox.</span></span> 
    
7. <span data-ttu-id="564b4-159">**更新**をクリックして、プロセスが完了すると、![更新](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)[**アーカイブ**] ページで、一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="564b4-159">When the process is complete, click **Refresh** ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the list on the **Archive** page.</span></span> 
    
    <span data-ttu-id="564b4-160">アーカイブ先のメールボックスは、組織内のすべてのユーザーに対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="564b4-160">The archive mailbox is enabled for all user's in your organization.</span></span>
    
    ![アーカイブ メールボックスが有効なメールボックスの一覧](media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)
  
8. <span data-ttu-id="564b4-p114">セキュリティのままにして&amp;コンプライアンス センターを開く。次の手順では、それを使用します。</span><span class="sxs-lookup"><span data-stu-id="564b4-p114">Leave the Security &amp; Compliance Center open. You'll use it in the next step.</span></span>
    
## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a><span data-ttu-id="564b4-164">手順 2: アーカイブと削除のポリシーの新しい保持タグを作成します。</span><span class="sxs-lookup"><span data-stu-id="564b4-164">Step 2: Create new retention tags for the archive and deletion policies</span></span>

<span data-ttu-id="564b4-165">この手順では、以前に説明した 3 つのユーザー設定の保持タグを作成します。</span><span class="sxs-lookup"><span data-stu-id="564b4-165">In this step, you'll create the three custom retention tags that were previously described.</span></span>
  
- <span data-ttu-id="564b4-166">アルペン家 3 年間アーカイブに移動 (カスタム ・ アーカイブ ・ ポリシー)</span><span class="sxs-lookup"><span data-stu-id="564b4-166">Alpine House 3 Year Move to Archive (custom archive policy)</span></span>
    
- <span data-ttu-id="564b4-167">アルペン家 7 年間を完全に削除 (カスタムの削除ポリシー)</span><span class="sxs-lookup"><span data-stu-id="564b4-167">Alpine House 7 Year Permanently Delete (custom deletion policy)</span></span>
    
- <span data-ttu-id="564b4-168">アルペン家削除項目 5 年を削除し、復元 (削除済みアイテム フォルダーのカスタム タグ)</span><span class="sxs-lookup"><span data-stu-id="564b4-168">Alpine House Deleted Items 5 Years Delete and Allow Recovery (custom tag for the Deleted Items folder)</span></span>
    
<span data-ttu-id="564b4-169">新しい保持タグを作成するには、Exchange Online 組織内で Exchange 管理センター (EAC) を使用します。</span><span class="sxs-lookup"><span data-stu-id="564b4-169">To create new retention tags, you'll use the Exchange admin center (EAC) in your Exchange Online organization.</span></span>
  
1. <span data-ttu-id="564b4-170">セキュリティ&amp;コンプライアンス センターでは、左上隅のアプリケーション起動ツールをクリックし、**管理**面です。</span><span class="sxs-lookup"><span data-stu-id="564b4-170">In the Security &amp; Compliance Center, click the app launcher  in the upper left corner, and then click the **Admin** tile .</span></span> 
    
2. <span data-ttu-id="564b4-171">[Office 365 の管理ページの左側のナビゲーション ウィンドウ、**管理センター**をを [ **Exchange**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-171">In the left navigation pane of the Office 365 admin center, click **Admin centers**, and then click **Exchange**.</span></span>
    
    ![Screenshot shows the Office 365 admin center with the Admin centers option expanded and Exchange selected.](media/47399df2-0bc4-42e2-b183-07750a46bc68.png)
  
3. <span data-ttu-id="564b4-173">**コンプライアンス管理**には、EAC で\>**保持タグ**</span><span class="sxs-lookup"><span data-stu-id="564b4-173">In the EAC, go to **Compliance management** \> **Retention tags**</span></span>
    
    <span data-ttu-id="564b4-174">組織の保持タグの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="564b4-174">A list of the retention tags for your organization is displayed.</span></span>
    
### <a name="create-a-custom-archive-default-policy-tag"></a><span data-ttu-id="564b4-175">カスタム ・ アーカイブの既定のポリシー タグを作成します。</span><span class="sxs-lookup"><span data-stu-id="564b4-175">Create a custom archive default policy tag</span></span>
  
<span data-ttu-id="564b4-176">最初に、3 年後のアーカイブ メールボックスにアイテムを移動するカスタム アーカイブ既定ポリシー タグ (DPT) を作成します。</span><span class="sxs-lookup"><span data-stu-id="564b4-176">First, you'll create a custom archive default policy tag (DPT) that will move items to the archive mailbox after 3 years.</span></span> 
  
1. <span data-ttu-id="564b4-177">**タグの保存**] ページで、[**新しいタグ**] をクリックします![新しいアイコン](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)、し、**メールボックスの全体 (既定値) に自動的に適用**を選択します。</span><span class="sxs-lookup"><span data-stu-id="564b4-177">On the **Retention tags** page, click **New tag**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span> 
    
2. <span data-ttu-id="564b4-178">**(既定値) をメールボックス全体に自動的に適用されるタグを新しい**ページで、次のフィールドを完了します。</span><span class="sxs-lookup"><span data-stu-id="564b4-178">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 
    
    ![新しいアーカイブの既定のポリシー タグを作成するための設定](media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
1. <span data-ttu-id="564b4-180">**名**新しい保持タグの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="564b4-180">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="564b4-181">**保存アクション**保存期間が終了すると、アーカイブ メールボックスにアイテムを移動するのには**アーカイブに移動する**を選択します。</span><span class="sxs-lookup"><span data-stu-id="564b4-181">**Retention action** Select **Move to Archive** to move items to the archive mailbox when the retention period expires.</span></span> 
    
3. <span data-ttu-id="564b4-p115">**保存期間\*\*\*\*アイテムが、次の有効期間 (日) に達する**を選択し、保存期間の期間を入力します。このシナリオでは、[1095 日間 (3 年) の後の項目アーカイブ メールボックスに移動されます。</span><span class="sxs-lookup"><span data-stu-id="564b4-p115">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period. For this scenario, items will be moved to the archive mailbox after 1095 days (3 years).</span></span>
    
4. <span data-ttu-id="564b4-184">**コメント**(省略可能)カスタム保持期間のタグの目的を説明するコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="564b4-184">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="564b4-185">カスタム アーカイブ DPT を作成して**保存**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-185">Click **Save** to create the custom archive DPT.</span></span> 
    
    <span data-ttu-id="564b4-186">新しいアーカイブ DPT は、保持タグの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="564b4-186">The new archive DPT is displayed in the list of retention tags.</span></span>
    
### <a name="create-a-custom-deletion-default-policy-tag"></a><span data-ttu-id="564b4-187">カスタムの削除の既定のポリシー タグを作成します。</span><span class="sxs-lookup"><span data-stu-id="564b4-187">Create a custom deletion default policy tag</span></span>
  
<span data-ttu-id="564b4-188">次に、別のカスタムの DPT を作成しますが、この 7 年後のアイテムを完全に削除する削除ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="564b4-188">Next, you'll create another custom DPT but this one will be a deletion policy that permanently deletes items after 7 years.</span></span>
  
1. <span data-ttu-id="564b4-189">**タグの保存**] ページで、[**新しいタグ**] をクリックします![新しいアイコン](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)、し、**メールボックスの全体 (既定値) に自動的に適用**を選択します。</span><span class="sxs-lookup"><span data-stu-id="564b4-189">On the **Retention tags** page, click **New tag**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span> 
    
2. <span data-ttu-id="564b4-190">**(既定値) をメールボックス全体に自動的に適用されるタグを新しい**ページで、次のフィールドを完了します。</span><span class="sxs-lookup"><span data-stu-id="564b4-190">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 
    
    ![新しい削除の既定のポリシー タグを作成するための設定](media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
1. <span data-ttu-id="564b4-192">**名**新しい保持タグの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="564b4-192">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="564b4-193">**保存アクション**保存期間が終了するときに、メールボックスからアイテムを削除するのに**完全に削除**を選択します。</span><span class="sxs-lookup"><span data-stu-id="564b4-193">**Retention action** Select **Permanently Delete** to purge items from the mailbox when the retention period expires.</span></span> 
    
3. <span data-ttu-id="564b4-p116">**保存期間\*\*\*\*アイテムが、次の有効期間 (日) に達する**を選択し、保存期間の期間を入力します。このシナリオでは、2555 日 (7 年間) 後のアイテムは削除されます。</span><span class="sxs-lookup"><span data-stu-id="564b4-p116">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period. For this scenario, items will be purged after 2555 days (7 years).</span></span>
    
4. <span data-ttu-id="564b4-196">**コメント**(省略可能)カスタム保持期間のタグの目的を説明するコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="564b4-196">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="564b4-197">DPT のカスタムの削除を作成するのには**保存**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-197">Click **Save** to create the custom deletion DPT.</span></span> 
    
    <span data-ttu-id="564b4-198">新しい削除の DPT は、保持タグの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="564b4-198">The new deletion DPT is displayed in the list of retention tags.</span></span>
    
### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a><span data-ttu-id="564b4-199">削除済みアイテム フォルダーのユーザー設定の保持ポリシー タグを作成します。</span><span class="sxs-lookup"><span data-stu-id="564b4-199">Create a custom retention policy tag for the Deleted Items folder</span></span>
  
<span data-ttu-id="564b4-p117">最後保持タグを作成しますが、削除済みアイテム フォルダー、ユーザー設定の保持ポリシー タグ (RPT) です。このタグは、5 年後、削除済みアイテム フォルダー内の項目を削除し、ユーザーがアイテムを回復する、削除済みアイテムの回復ツールを使用する場合、回復期間が用意されています。</span><span class="sxs-lookup"><span data-stu-id="564b4-p117">The last retention tag that you'll create is a custom retention policy tag (RPT) for the Deleted Items folder. This tag will delete items in the Deleted Items folder after 5 years, and provides a recovery period when users can use the Recover Deleted Items tool to recover an item.</span></span>
  
1. <span data-ttu-id="564b4-202">**タグの保存**] ページで、[**新しいタグ**] をクリックします![アイコンの新しい](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)、し、**既定のフォルダーに自動的に適用**を選択します。</span><span class="sxs-lookup"><span data-stu-id="564b4-202">On the **Retention tags** page, click **New tag** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to a default folder**.</span></span> 
    
2. <span data-ttu-id="564b4-203">[**新しいタグの既定のフォルダーに自動的に適用**] ページで、次のフィールドを完了します。</span><span class="sxs-lookup"><span data-stu-id="564b4-203">On the **New tag applied automatically to a default folder** page, complete the following fields:</span></span> 
    
    ![削除済みアイテム フォルダーに新しい保持ポリシー タグを作成するための設定](media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
1. <span data-ttu-id="564b4-205">**名**新しい保持タグの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="564b4-205">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="564b4-206">**次の既定フォルダーには、このタグを適用**ボックスの一覧で、**削除済みアイテム**を選択します。</span><span class="sxs-lookup"><span data-stu-id="564b4-206">**Apply this tag to the following default folder** In the drop-down list, select **Deleted Items**.</span></span>
    
3. <span data-ttu-id="564b4-207">**保存アクション\*\*\*\*削除しリカバリ**保存期間が期限切れになったが、削除済みアイテムの保存期間 (つまり既定では 14 日間) 内で削除済みアイテムを回復できるようにすると、アイテムを削除するを選択します。</span><span class="sxs-lookup"><span data-stu-id="564b4-207">**Retention action** Select **Delete and Allow Recovery** to delete items when the retention period expires, but allow users to recover a deleted item within the deleted item retention period (which by default is 14 days).</span></span> 
    
4. <span data-ttu-id="564b4-p118">**保存期間\*\*\*\*アイテムが、次の有効期間 (日) に達する**を選択し、保存期間の期間を入力します。このシナリオでは、1825 日 (5 年) の後の項目が削除されます。</span><span class="sxs-lookup"><span data-stu-id="564b4-p118">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period. For this scenario, items will be deleted after 1825 days (5 years).</span></span>
    
5. <span data-ttu-id="564b4-210">**コメント**(省略可能)カスタム保持期間のタグの目的を説明するコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="564b4-210">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="564b4-211">削除済みアイテム フォルダーのカスタムの RPT を作成するのには**保存**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-211">Click **Save** to create the custom RPT for the Deleted Items folder.</span></span> 
    
    <span data-ttu-id="564b4-212">新しい RPT は、保持タグの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="564b4-212">The new RPT is displayed in the list of retention tags.</span></span>

## <a name="step-3-create-a-new-retention-policy"></a><span data-ttu-id="564b4-213">手順 3: 新しい保持ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="564b4-213">Step 3: Create a new retention policy</span></span>

<span data-ttu-id="564b4-p119">カスタム保持期間のタグを作成すると、次の手順、新しい保持ポリシーを作成および保持タグを追加します。手順 2 で作成した 3 つのカスタム保持期間のタグと最初のセクションに記載されている組み込みのタグを追加します。手順 4 では、ユーザーのメールボックスにこの新しい保存ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="564b4-p119">After you create the custom retention tags, the next step is to create a new retention policy and add the retention tags. You'll add the three custom retention tags that you created in Step 2, and the built-in tags that were mentioned in the first section. In Step 4, you'll assign this new retention policy to user mailboxes.</span></span>
  
1. <span data-ttu-id="564b4-217">**コンプライアンス管理**には、EAC で\> **・ リテンション ・ ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="564b4-217">In the EAC, go to **Compliance management** \> **Retention policies**.</span></span>
    
2. <span data-ttu-id="564b4-218">[**リテンション ポリシー** ] ページで [**新規**] をクリックします![新しいアイコン](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)。</span><span class="sxs-lookup"><span data-stu-id="564b4-218">On the **Retention policies** page, click **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>
    
3. <span data-ttu-id="564b4-219">**[名前**] ボックスで、新しい保存ポリシーの名前を入力しますなどの**高山の家のアーカイブと削除のポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="564b4-219">In the **Name** box, type a name for the new retention policy; for example, **Alpine House Archive and Deletion Policy**.</span></span> 
    
4. <span data-ttu-id="564b4-220">**保持タグ**では、下の [**追加**] をクリックします![新しいアイコン](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)。</span><span class="sxs-lookup"><span data-stu-id="564b4-220">Under **Retention tags**, click **Add** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>
    
    <span data-ttu-id="564b4-p120">組織内の保持タグの一覧が表示されます。手順 2 で作成したカスタムのタグが表示されるに注意してください。</span><span class="sxs-lookup"><span data-stu-id="564b4-p120">A list of the retention tags in your organization is displayed. Note the custom tags that you created in Step 2 are displayed.</span></span>
    
5. <span data-ttu-id="564b4-p121">(これらのタグは「[詳細](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo)」で詳しく説明します)、次のスクリーン ショットで強調表示されている 9 の保持タグを追加します。保存期間タグを追加するには、選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-p121">Add the 9 retention tags that are highlighted in the following screenshot (these tags are described in more detail in the [More information](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo) section). To add a retention tag, select it and then click **Add**.</span></span> 
    
    ![新しい保持ポリシーに保持タグを追加します。](media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > <span data-ttu-id="564b4-226">**Ctrl**キーを押したまま各タグをクリックし、複数の保持タグを選択します。</span><span class="sxs-lookup"><span data-stu-id="564b4-226">You can select multiple retention tags by holding down the **Ctrl** key and then clicking each tag.</span></span> 
  
6. <span data-ttu-id="564b4-227">保存期間タグを追加したら、[ **OK**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-227">After you've added the retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="564b4-228">**新しい保持ポリシー** ] ページで、新しいポリシーを作成して**保存**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-228">On the **New retention policy** page, click **Save** to create the new policy.</span></span> 
    
    <span data-ttu-id="564b4-p122">新しい保持ポリシーは、一覧に表示されます。詳細ペインで、リンクしている保持タグを表示するを選択します。</span><span class="sxs-lookup"><span data-stu-id="564b4-p122">The new retention policy is displayed in the list. Select it to display the retention tags linked to it in the details pane.</span></span>
    
    ![新しいリテンション ・ ポリシーとリンクされた保持タグの一覧](media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a><span data-ttu-id="564b4-232">手順 4: ユーザーのメールボックスに新しい保存ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="564b4-232">Step 4: Assign the new retention policy to user mailboxes</span></span>

<span data-ttu-id="564b4-p123">新しいメールボックスを作成するときは、既定でをという名前の既定の MRM ポリシー、リテンション ・ ポリシーが割り当てられます。この手順でに置き換えますこの保持ポリシー (メールボックスでは、それに割り当てられている 1 つの保持ポリシーを持つことができます) ため、組織内のユーザーのメールボックスに手順 3 で作成した新規のリテンション ・ ポリシーを割り当てることによって。この手順では、新しいポリシー、組織内のすべてのメールボックスに割り当てるが想定しています。</span><span class="sxs-lookup"><span data-stu-id="564b4-p123">When a new mailbox is created, a retention policy named Default MRM policy is assigned to it by default. In this step, you'll replace this retention policy (because a mailbox can have only one retention policy assigned to it) by assigning the new retention policy that you created in Step 3 to the user mailboxes in your organization. This step assumes that you'll assign the new policy to all mailboxes in your organization.</span></span>
  
1. <span data-ttu-id="564b4-236">EAC で、**[受信者]** \> **[メールボックス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="564b4-236">In the EAC, go to **Recipients** \> **Mailboxes**.</span></span>
    
    <span data-ttu-id="564b4-237">組織内のすべてのユーザー メールボックスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="564b4-237">A list of all user mailboxes in your organization is displayed.</span></span> 
    
2. <span data-ttu-id="564b4-238">**Shift**キーを押し、一覧の最初のクリックし、リスト内の最後の 1 つですべてのメールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="564b4-238">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 
    
3. <span data-ttu-id="564b4-239">詳細ペインで、[**一括編集**を、[EAC の右側にある**他のオプション**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-239">In the details pane on the right side of the EAC, under **Bulk Edit**, click **More options**.</span></span>
    
4. <span data-ttu-id="564b4-240">**[アイテム保持ポリシー]** 下で **[更新]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-240">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="564b4-241">**一括でリテンション ・ ポリシーを割り当てる**] ページで、**リテンション ・ ポリシーを選択**」ドロップ ダウン ボックスの一覧で、リテンション ポリシーを選択手順 3 で作成しました。などの**高山の家のアーカイブと保存ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="564b4-241">On the **Bulk assign retention policy** page, in the **Select the retention policy** drop-down list, select the retention policy that you created in Step 3; for example, **Alpine House Archive and Retention Policy**.</span></span>
    
6. <span data-ttu-id="564b4-242">新しい保存ポリシーの割り当てを保存する**保存**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-242">Click **Save** to save the new retention policy assignment.</span></span> 
    
7. <span data-ttu-id="564b4-243">新しい保持ポリシーがメールボックスに割り当てられていることを確認するには、次を行うことができます: [メールボックス] ページでメールボックスを選択して、[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-243">To verify that the new retention policy was assigned to mailboxes, you can do the following: select a mailbox on the Mailboxes page, and then click Edit.</span></span> 
    
1. <span data-ttu-id="564b4-244">[**メールボックス**] ページでメールボックスを選択して**編集**] をクリックし、![の編集](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png)。</span><span class="sxs-lookup"><span data-stu-id="564b4-244">Select a mailbox on the **Mailboxes** page, and then click **Edit** ![Edit](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png).</span></span> 
    
2. <span data-ttu-id="564b4-245">選択したユーザーのメールボックスのプロパティ ページで [**メールボックスの機能**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-245">On the mailbox properties page for the selected user, click **Mailbox features**.</span></span>
    
    <span data-ttu-id="564b4-246">メールボックスに割り当てられている新しいポリシーの名前は、**リテンション ・ ポリシー**のドロップダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="564b4-246">The name of the new policy assigned to the mailbox is displayed in the **Retention policy** drop-down list.</span></span> 

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a><span data-ttu-id="564b4-247">(省略可能)手順 5: 実行する管理フォルダー アシスタントを新しい設定を適用するには</span><span class="sxs-lookup"><span data-stu-id="564b4-247">(Optional) Step 5: Run the Managed Folder Assistant to apply the new settings</span></span>

<span data-ttu-id="564b4-p124">手順 4 でのメールボックスに新しい保存ポリシーを適用すると、かかることが最大 7 日間 Exchange オンライン、新しい保存期間の設定、メールボックスに適用するのです。これは、プロセスがプロセスの管理フォルダー アシスタントのメールボックスを 7 日間に 1 回呼び出されるためにです。管理フォルダー アシスタントを実行するを待つ代わりに、このコマンドレットを実行して**開始 ManagedFolderAssistant** Exchange オンライン PowerShell ようを強制できます。</span><span class="sxs-lookup"><span data-stu-id="564b4-p124">After you apply the new retention policy to mailboxes in Step 4, it can take up to 7 days in Exchange Online for the new retention settings to be applied to the mailboxes. This is because a process called the Managed Folder Assistant processes mailboxes once every 7 days. Instead of waiting for the Managed Folder Assistant to run, you can force this to happen by running the **Start-ManagedFolderAssistant** cmdlet in Exchange Online PowerShell.</span></span> 
  
 <span data-ttu-id="564b4-p125">**管理フォルダー アシスタントを実行するときの動作ですか?** メールボックス内のアイテムを検査し、保存の対象となるかどうかを判断するでは、リテンション ・ ポリシーの設定が適用されます。適切な保持タグの保存期間が適用されるアイテムをスタンプし、その保有期間を過ぎたアイテムの指定された保存操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="564b4-p125">**What happens when you run the Managed Folder Assistant?** It applies the settings in the retention policy by inspecting items in the mailbox and determining whether they're subject to retention. It then stamps items subject to retention with the appropriate retention tag, and then takes the specified retention action on items past their retention age.</span></span> 
  
<span data-ttu-id="564b4-254">Exchange オンラインの PowerShell に接続し、組織内のすべてのメールボックスに管理フォルダー アシスタントを実行する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="564b4-254">Here are the steps to connect to Exchange Online PowerShell, and then run the Managed Folder Assistant on every mailbox in your organization.</span></span>
  
1. <span data-ttu-id="564b4-255">ローカル コンピューターで、Windows PowerShell を開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="564b4-255">On your local computer, open Windows PowerShell and run the following command.</span></span>
    
    ```
    $UserCredential = Get-Credential
    ```

    <span data-ttu-id="564b4-256">**Windows PowerShell の資格情報の要求**] ダイアログ ボックスで、Office 365 のグローバル管理者アカウントのパスワードとユーザー名を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="564b4-256">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global admin account, and then click **OK**.</span></span>
    
2. <span data-ttu-id="564b4-257">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="564b4-257">Run the following command.</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. <span data-ttu-id="564b4-258">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="564b4-258">Run the following command.</span></span>
    
    ```
    Import-PSSession $Session
    ```

4. <span data-ttu-id="564b4-259">Exchange Online 組織に接続されたことを検証するために、次のコマンドを実行して、組織内のすべてのメールボックスのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="564b4-259">To verify that you're connected to your Exchange Online organization, run the following command to get a list of all the mailboxes in your organization.</span></span>
    
    ```
    Get-Mailbox
    ```

    > [!NOTE]
    > <span data-ttu-id="564b4-260">詳細についてはまたは、オンラインの Exchange 組織への接続に問題がある場合は、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=517283)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="564b4-260">For more information or if you have problems connecting to your Exchange Online organization, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span> 
  
5. <span data-ttu-id="564b4-261">組織の管理フォルダー アシスタントのすべてのユーザーのメールボックスを開始する次の 2 つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="564b4-261">Run the following two commands to start the Managed Folder Assistant for all user mailboxes in your organization.</span></span>
    
    ```
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

<span data-ttu-id="564b4-p126">それです！高山の家の組織に、アーカイブと削除のポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="564b4-p126">That's it! You've set up an archive and deletion policy for the Alpine House organization.</span></span>
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a><span data-ttu-id="564b4-264">(省略可能)既定の組織の新しい保存ポリシーを作成する手順 6。</span><span class="sxs-lookup"><span data-stu-id="564b4-264">(Optional) Step 6: Make the new retention policy the default for your organization</span></span>

<span data-ttu-id="564b4-p127">手順 4 では、既存のメールボックスに新しい保存ポリシーを割り当てる必要が。構成することが Exchange Online で今後作成される新しいメールボックスに新しい保持ポリシーが割り当てられているようにします。Exchange オンライン PowerShell を使用して、組織の既定のメールボックス プランを更新するこれを行います。*メールボックス プラン*は、自動的に新しいメールボックスのプロパティを構成するテンプレートです。 このオプションの手順では、手順 3 で作成した保持ポリシーに既定で、既定の MRM ポリシー メールボックス プランに割り当てられている現在の保持ポリシーを置き換えることができます。メールボックスの計画を更新した後は、新しいメールボックスに新しい保持ポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="564b4-p127">In Step 4, you have to assign the new retention policy to existing mailboxes. But you can configure Exchange Online so that the new retention policy is assigned to new mailboxes that are created in the future. You do this by using Exchange Online PowerShell to update your organization's default mailbox plan. A *mailbox plan* is a template that automatically configures properties on new mailboxes.  In this optional step, you can replace the current retention policy that's assigned to the mailbox plan (by default, the Default MRM Policy) with the retention policy that you created in Step 3. After you update the mailbox plan, the new retention policy will be assigned to new mailboxes.</span></span>

1. <span data-ttu-id="564b4-271">[Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=517283)または手順 5 を参照します。</span><span class="sxs-lookup"><span data-stu-id="564b4-271">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) or see Step 5.</span></span>

2. <span data-ttu-id="564b4-272">組織内のメールボックスの計画に関する情報を表示するのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="564b4-272">Run the following command to display information about the mailbox plans in your organization.</span></span>

    ```
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```
    <span data-ttu-id="564b4-273">既定値として設定されているメールボックス プランに注意してください。</span><span class="sxs-lookup"><span data-stu-id="564b4-273">Note the mailbox plan that's set as the default.</span></span>

3. <span data-ttu-id="564b4-p128">既定のメールボックス プランに (たとえば**高山の家のアーカイブ、保持ポリシー**)、手順 3 で作成した新規のリテンション ・ ポリシーを割り当てるには次のコマンドを実行します。次の使用例では、既定のメールボックス プランの名前は、 **ExchangeOnlineEnterprise**を前提としています。</span><span class="sxs-lookup"><span data-stu-id="564b4-p128">Run the following command to assign the new retention policy that you created in Step 3 (for example, **Alpine House Archive and Retention Policy**) to the default mailbox plan. This example assumes the name of the default mailbox plan is **ExchangeOnlineEnterprise**.</span></span>

    ```
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```
4. <span data-ttu-id="564b4-276">既定のメールボックス プランに割り当てられているリテンション ・ ポリシーが変更されたことを確認するのには 2 の手順でコマンドを再実行することができます。</span><span class="sxs-lookup"><span data-stu-id="564b4-276">You can re-run the command in step 2 to verify that the retention policy assigned to the default mailbox plan was changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="564b4-277">詳細情報</span><span class="sxs-lookup"><span data-stu-id="564b4-277">More information</span></span>

- <span data-ttu-id="564b4-p129">保有期間はどのように計算されるのでしょうか。メールボックス アイテムの保有期間は、出荷日または送信されていない下書きメッセージなどのアイテムの作成の日付から計算されますが、ユーザーが作成されます。管理フォルダー アシスタントは、メールボックス内のアイテムを処理するときは、開始日と保持タグを削除し、回復を許可する、または完全に削除の保存操作をしているすべてのアイテムの有効期限の日付をスタンプします。アーカイブ タグを持っているアイテムには、移動の日付がスタンプされます。</span><span class="sxs-lookup"><span data-stu-id="564b4-p129">How is retention age calculated? The retention age of mailbox items is calculated from the date of delivery or the date of creation for items such as draft messages that aren't sent but are created by the user. When the Managed Folder Assistant processes items in a mailbox, it stamps a start date and an expiration date for all items that have retention tags with the Delete and Allow Recovery or Permanently Delete retention action. Items that have an archive tag are stamped with a move date.</span></span> 
    
- <span data-ttu-id="564b4-282">次の表は、このトピックの手順を実行して作成されたカスタムのリテンション ・ ポリシーに追加される各保持タグの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="564b4-282">The following table provides more information about each retention tag that is added to the custom retention policy that was created by following the steps in this topic.</span></span>
    
    |<span data-ttu-id="564b4-283">**保持タグ**</span><span class="sxs-lookup"><span data-stu-id="564b4-283">**Retention tag**</span></span>|<span data-ttu-id="564b4-284">**このタグはどのような**</span><span class="sxs-lookup"><span data-stu-id="564b4-284">**What this tag does**</span></span>|<span data-ttu-id="564b4-285">**組み込みまたはユーザー設定を設定しますか。**</span><span class="sxs-lookup"><span data-stu-id="564b4-285">**Built-in or custom?**</span></span>|<span data-ttu-id="564b4-286">**型**</span><span class="sxs-lookup"><span data-stu-id="564b4-286">**Type**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="564b4-287">高山の家 3 年間を移動して、アーカイブ</span><span class="sxs-lookup"><span data-stu-id="564b4-287">Alpine House 3 Year Move to Archive</span></span>  <br/> |<span data-ttu-id="564b4-288">1095 日 (3 年) アーカイブ メールボックスにアイテムを移動します。</span><span class="sxs-lookup"><span data-stu-id="564b4-288">Moves items that are 1095 days (3 years) old to the archive mailbox.</span></span>  <br/> |<span data-ttu-id="564b4-289">カスタム (を参照してください[手順 2: アーカイブと削除のポリシーの新しい保持タグを作成する](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span><span class="sxs-lookup"><span data-stu-id="564b4-289">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="564b4-290">既定ポリシー タグ (アーカイブ)。このタグは、メールボックス全体に適用します。</span><span class="sxs-lookup"><span data-stu-id="564b4-290">Default Policy Tag (archive); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="564b4-291">アルペン ハウス 7 年間を完全に削除</span><span class="sxs-lookup"><span data-stu-id="564b4-291">Alpine House 7 Year Permanently Delete</span></span>  <br/> |<span data-ttu-id="564b4-292">7 歳がプライマリ メールボックスまたはアーカイブ メールボックス内のアイテムを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="564b4-292">Permanently deletes items in the primary mailbox or the archive mailbox when they are 7 years old.</span></span>  <br/> |<span data-ttu-id="564b4-293">カスタム (を参照してください[手順 2: アーカイブと削除のポリシーの新しい保持タグを作成する](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span><span class="sxs-lookup"><span data-stu-id="564b4-293">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="564b4-294">既定ポリシー タグ (削除) します。このタグは、メールボックス全体に適用します。</span><span class="sxs-lookup"><span data-stu-id="564b4-294">Default Policy Tag (deletion); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="564b4-295">アルペン ハウス 5 年間削除の項目を削除し、リカバリ</span><span class="sxs-lookup"><span data-stu-id="564b4-295">Alpine House Deleted Items 5 Years Delete and Allow Recovery</span></span>  <br/> |<span data-ttu-id="564b4-p130">5 年前は、削除済みアイテム フォルダーからアイテムを削除します。これらのアイテムを削除した後、14 日間のリカバリできます。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="564b4-p130">Deletes items from the Deleted Items folder that are 5 years old. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="564b4-298">カスタム (を参照してください[手順 2: アーカイブと削除のポリシーの新しい保持タグを作成する](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span><span class="sxs-lookup"><span data-stu-id="564b4-298">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="564b4-299">保持ポリシー タグ (削除済みアイテム)。このタグは自動的に削除済みアイテム フォルダー内のアイテムに適用されます。</span><span class="sxs-lookup"><span data-stu-id="564b4-299">Retention Policy Tag (Deleted Items); this tag is automatically applied to items in the Deleted items folder.</span></span>  <br/> |
    |<span data-ttu-id="564b4-300">回復可能なアイテムの 14 日は、アーカイブに移動します。</span><span class="sxs-lookup"><span data-stu-id="564b4-300">Recoverable Items 14 days Move to Archive</span></span>  <br/> |<span data-ttu-id="564b4-301">アーカイブ メールボックスの回復可能なアイテム] フォルダーに 14 日間の回復可能なアイテム フォルダーに保存されている項目を移動します。</span><span class="sxs-lookup"><span data-stu-id="564b4-301">Moves items that have been in the Recoverable Items folder for 14 days to the Recoverable Items folder in the archive mailbox.</span></span>  <br/> |<span data-ttu-id="564b4-302">組み込み</span><span class="sxs-lookup"><span data-stu-id="564b4-302">Built-in</span></span>  <br/> |<span data-ttu-id="564b4-303">保持ポリシー タグ (回復可能なアイテム)。このタグは、回復可能なアイテム] フォルダー内のアイテムに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="564b4-303">Retention Policy Tag (Recoverable Items); this tag is automatically applied to items in the Recoverable Items folder.</span></span>  <br/> |
    |<span data-ttu-id="564b4-304">迷惑メール</span><span class="sxs-lookup"><span data-stu-id="564b4-304">Junk Email</span></span>  <br/> |<span data-ttu-id="564b4-p131">30 日間の [迷惑メール] フォルダーにされているアイテムを完全に削除します。これらのアイテムを削除した後、14 日間のリカバリできます。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="564b4-p131">Permanently deletes items that have been in the Junk Email folder for 30 days. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="564b4-307">組み込み</span><span class="sxs-lookup"><span data-stu-id="564b4-307">Built-in</span></span>  <br/> |<span data-ttu-id="564b4-308">保持ポリシー タグ (迷惑メール) です。このタグは自動的に [迷惑メール] フォルダー内のアイテムに適用されます。</span><span class="sxs-lookup"><span data-stu-id="564b4-308">Retention Policy Tag (Junk Email); this tag is automatically applied to items in Junk Email folder.</span></span>  <br/> |
    |<span data-ttu-id="564b4-309">1 か月で削除</span><span class="sxs-lookup"><span data-stu-id="564b4-309">1 Month Delete</span></span>  <br/> |<span data-ttu-id="564b4-p132">30 日間の古いアイテムを完全に削除します。これらのアイテムを削除した後、14 日間のリカバリできます。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="564b4-p132">Permanently deletes items that are 30 days old. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="564b4-312">組み込み</span><span class="sxs-lookup"><span data-stu-id="564b4-312">Built-in</span></span>  <br/> |<span data-ttu-id="564b4-313">個人。このタグは、ユーザーが適用することができます。</span><span class="sxs-lookup"><span data-stu-id="564b4-313">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="564b4-314">1 年で削除</span><span class="sxs-lookup"><span data-stu-id="564b4-314">1 Year Delete</span></span>  <br/> |<span data-ttu-id="564b4-p133">365 日の古いアイテムを完全に削除します。これらのアイテムを削除した後、14 日間のリカバリできます。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="564b4-p133">Permanently deletes items that are 365 days old. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="564b4-317">組み込み</span><span class="sxs-lookup"><span data-stu-id="564b4-317">Built-in</span></span>  <br/> |<span data-ttu-id="564b4-318">個人。このタグは、ユーザーが適用することができます。</span><span class="sxs-lookup"><span data-stu-id="564b4-318">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="564b4-319">削除しない</span><span class="sxs-lookup"><span data-stu-id="564b4-319">Never Delete</span></span>  <br/> |<span data-ttu-id="564b4-320">このタグは、アイテムがアイテム保持ポリシーによって削除されることを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="564b4-320">This tag prevent items from being deleted by a retention policy.</span></span>  <br/> |<span data-ttu-id="564b4-321">組み込み</span><span class="sxs-lookup"><span data-stu-id="564b4-321">Built-in</span></span>  <br/> |<span data-ttu-id="564b4-322">個人。このタグは、ユーザーが適用することができます。</span><span class="sxs-lookup"><span data-stu-id="564b4-322">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="564b4-323">個人 - 1 年でアーカイブへ移動</span><span class="sxs-lookup"><span data-stu-id="564b4-323">Personal 1 year move to archive</span></span>  <br/> |<span data-ttu-id="564b4-324">1 年後、アーカイブ メールボックスにアイテムを移動します。</span><span class="sxs-lookup"><span data-stu-id="564b4-324">Moves items to the archive mailbox after 1 year.</span></span>  <br/> |<span data-ttu-id="564b4-325">組み込み</span><span class="sxs-lookup"><span data-stu-id="564b4-325">Built-in</span></span>  <br/> |<span data-ttu-id="564b4-326">個人。このタグは、ユーザーが適用することができます。</span><span class="sxs-lookup"><span data-stu-id="564b4-326">Personal; this tag can be applied by users.</span></span>  <br/> |
   
    > <span data-ttu-id="564b4-p134"><sup>\*</sup>ユーザーは、既定では 14 日、オンライン Exchange を削除済みアイテムの保存期間内で削除済みアイテムを回復するのに Outlook および Outlook Web App で [削除済みアイテムの回復ツールを使用できます。管理者は、最大 30 日以内に削除済みアイテムの保存期間を変更するのには、Windows PowerShell を使用できます。詳細についてを参照してください:[リカバリは、Outlook のウィンドウ内の項目を削除](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)し、 [Exchange オンラインのメールボックスの削除済みアイテム保存期間を変更](https://go.microsoft.com/fwlink/p/?LinkId=286940)</span><span class="sxs-lookup"><span data-stu-id="564b4-p134"><sup>\*</sup> Users can use the Recover Deleted Items tool in Outlook and Outlook Web App to recover a deleted item within the deleted item retention period, which by default is 14 days in Exchange Online. An administrator can use Windows PowerShell to increase the deleted item retention period to a maximum of 30 days. For more information, see: [Recover deleted items in Outlook for Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) and [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940)</span></span>
  
- <span data-ttu-id="564b4-p135">**回復可能のアイテム 14 日がアーカイブに移動**保持タグにより自由を使用して、ユーザーのプライマリ メールボックスの回復可能なアイテム] フォルダー内のストレージ ・ スペースをします。これは、機能は、これまで完全には何も意味は、ユーザーのメールボックスを削除、保留中のユーザーのメールボックスが配置されると便利です。アーカイブ メールボックスにアイテムを移動することがないプライマリ メールボックスの回復可能なアイテム フォルダーの記憶域のクォータに達した。これとこれを回避する方法の詳細については、[上のメールボックスのクォータを保持する回復可能な項目を増やす](https://go.microsoft.com/fwlink/p/?LinkId=786479)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="564b4-p135">Using the **Recoverable Items 14 days Move to Archive** retention tag helps free up storage space in the Recoverable Items folder in the user's primary mailbox. This is useful when a user's mailbox is placed on hold, which means nothing is ever permanently deleted the user's mailbox. Without moving items to the archive mailbox, it's possible the storage quota for the Recoverable Items folder in the primary mailbox will be reached. For more information about this and how to avoid it, see [Increase the Recoverable Items quota for mailboxes on hold](https://go.microsoft.com/fwlink/p/?LinkId=786479).</span></span>
