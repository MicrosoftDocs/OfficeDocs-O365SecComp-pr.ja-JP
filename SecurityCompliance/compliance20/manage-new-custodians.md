---
title: 高度な電子情報開示ケースで保管担当者を管理する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d9806ecbc23f46ee2d39f8d7e6be07af0d6a83e8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151619"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="ae2de-102">高度な電子情報開示ケースで保管担当者を管理する</span><span class="sxs-lookup"><span data-stu-id="ae2de-102">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="ae2de-103">Advanced eDiscovery の [保管担当者] タブには、ケースに追加されているすべての保管担当者の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ae2de-103">The Custodians tab in Advanced eDiscovery contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="ae2de-104">保管担当者をケースに追加すると、各保管担当者の詳細が Azure Active Directory から自動的に収集され、高度な電子情報開示で表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ae2de-104">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![保管担当者の管理](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="ae2de-106">保管担当者の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="ae2de-106">View custodian details</span></span>

<span data-ttu-id="ae2de-107">保管担当者の詳細を表示するには、[**保管担当者**] タブのリストで保管担当者をクリックします。ポップアップページが表示され、保管担当者に関する次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ae2de-107">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="ae2de-108">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="ae2de-108">Contact information</span></span>

  - <span data-ttu-id="ae2de-109">[**表示名**保管担当者のアドレス帳に表示される名前。</span><span class="sxs-lookup"><span data-stu-id="ae2de-109">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="ae2de-110">通常は、保管担当者の名、ミドルネーム、姓の組み合わせになります。</span><span class="sxs-lookup"><span data-stu-id="ae2de-110">This is usually the combination of the custodian’s first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="ae2de-111">**Mail/SMTP** -保管担当者のプライマリ SMTP アドレス (例: brianj@contoso.onmicrosoft.com)。</span><span class="sxs-lookup"><span data-stu-id="ae2de-111">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="ae2de-112">保管担当者のユーザープリンシパル名 (UPN) もリストされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ae2de-112">Note that the custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="ae2de-113">**Title** -保管担当者の役職。</span><span class="sxs-lookup"><span data-stu-id="ae2de-113">**Title** - The custodian’s job title.</span></span>

  - <span data-ttu-id="ae2de-114">**Department** -保管担当者が機能する部署の名前。</span><span class="sxs-lookup"><span data-stu-id="ae2de-114">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="ae2de-115">**上司**-保管担当者の上司。</span><span class="sxs-lookup"><span data-stu-id="ae2de-115">**Manager** - The custodian’s manager.</span></span> <span data-ttu-id="ae2de-116">指定した上司は、この保管担当者のエスカレーション情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ae2de-116">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="ae2de-117">場所情報</span><span class="sxs-lookup"><span data-stu-id="ae2de-117">Location information</span></span>

  - <span data-ttu-id="ae2de-118">**City** -保管担当者が配置されている市区町村。</span><span class="sxs-lookup"><span data-stu-id="ae2de-118">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="ae2de-119">**State** -保管担当者の住所の都道府県を示します。</span><span class="sxs-lookup"><span data-stu-id="ae2de-119">**State** - The state or province in the custodian’s address.</span></span>

  - <span data-ttu-id="ae2de-120">**国/地域**-保管担当者が配置されている国/地域。</span><span class="sxs-lookup"><span data-stu-id="ae2de-120">**Country/Region** - The country/region where the custodian’s is located.</span></span>

  - <span data-ttu-id="ae2de-121">**Office** -保管担当者の事業所のオフィスの場所。</span><span class="sxs-lookup"><span data-stu-id="ae2de-121">**Office** - The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="ae2de-122">ケース情報</span><span class="sxs-lookup"><span data-stu-id="ae2de-122">Case information</span></span>

  - <span data-ttu-id="ae2de-123">**ホールド状態**-保管担当者が保留中であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ae2de-123">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="ae2de-124">**通信の状態**: 保管担当者に保留通知が発行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ae2de-124">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="ae2de-125">保管担当者に通知が発行されている場合は、このプロパティの値が**公開**されます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-125">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="ae2de-126">保管担当者に通知が発行されていない場合、状態\*\*\*\* は未発行になります。</span><span class="sxs-lookup"><span data-stu-id="ae2de-126">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="ae2de-127">**状態**-ケース内の保管担当者の状態。</span><span class="sxs-lookup"><span data-stu-id="ae2de-127">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="ae2de-128">状態が "**アクティブ**" は、保管担当者がケースの一部であることを示します。</span><span class="sxs-lookup"><span data-stu-id="ae2de-128">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="ae2de-129">保管担当者がケースからリリースされている場合は、ステータスが [**リリース**済み] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-129">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="ae2de-130">データソースとインデックス作成に関する情報</span><span class="sxs-lookup"><span data-stu-id="ae2de-130">Data sources and indexing information</span></span>

    - <span data-ttu-id="ae2de-131">**データソース**-保管担当者に関連付けられていて、ケースの一部であるデータソース (メールボックス、サイト、およびチーム) の数と種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-131">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="ae2de-132">**インデックスの更新時刻**-高度なインデックス作成ジョブが最後にトリガーされた日時を示します。</span><span class="sxs-lookup"><span data-stu-id="ae2de-132">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="ae2de-133">このプロパティは、高度なインデックス処理が現在進行中であることも示します。</span><span class="sxs-lookup"><span data-stu-id="ae2de-133">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="ae2de-134">保管担当者を編集する</span><span class="sxs-lookup"><span data-stu-id="ae2de-134">Edit a custodian</span></span>

<span data-ttu-id="ae2de-135">ケースの進行に応じて、特定の保管担当者 & に関連する追加のデータソースが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae2de-135">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="ae2de-136">その他のシナリオでは、確認され、関連性がないと見なされた特定のデータソースを削除することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae2de-136">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="ae2de-137">保管担当者に関連付けられているデータソースを更新するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ae2de-137">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="ae2de-138">**EDiscovery _GT_ Advanced ediscovery**に移動し、ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-138">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="ae2de-139">[**保管担当者**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae2de-139">Click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="ae2de-140">リストから保管担当者を選択し、フライアウトページの [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae2de-140">Select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![データソースの編集](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="ae2de-142">[**データソースの選択**] タブをクリックして、保管担当者の Exchange メールボックスと OneDrive アカウントの設定を変更し、[**データソースの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae2de-142">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="ae2de-143">保管担当者に関連付けられている Teams、SharePoint、または Exchange メールボックスを追加または削除するには、[**その他のデータソースの選択**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae2de-143">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="ae2de-144">保管担当者に関連付けられているデータソースの詳細については、「 [Add 保管担当者 to case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian)」の「手順 3: 追加のデータソースを保管担当者に関連付ける」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae2de-144">For more information about data sources associated with a custodian, see "Step 3: Associate additional data sources to a custodian" in [Add custodians to a case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span></span> 
  
6. <span data-ttu-id="ae2de-145">保管担当者のホールドを有効または無効にするには、[ **custodial ホールドを配置**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae2de-145">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="resolve-custodian-processing-errors"></a><span data-ttu-id="ae2de-146">保管担当者処理エラーを解決する</span><span class="sxs-lookup"><span data-stu-id="ae2de-146">Resolve custodian processing errors</span></span>

<span data-ttu-id="ae2de-147">法的調査のためのほとんどの電子情報開示ワークフローでは、保管担当者が訴訟に追加された後、保管担当者のデータのサブセットが検索されます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-147">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="ae2de-148">非常に大きなファイルサイズまたはデータの破損が原因で、保管担当者に関連付けられているデータソース内の一部のアイテムが部分的にインデックス処理されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ae2de-148">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="ae2de-149">高度な電子情報開示の[高度なインデックス](indexing-custodian-data.md)機能を使用すると、ほとんどのインデックス付きアイテムは、必要に応じてこれらのアイテムのインデックスを再作成することで、自動的に修復できます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-149">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="ae2de-150">保管担当者がケースに追加されると、保管担当者に関連付けられているデータソース内のデータは自動的に再インデックス化されます (高度なインデックス作成プロセスによって)。</span><span class="sxs-lookup"><span data-stu-id="ae2de-150">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="ae2de-151">つまり、データをダウンロードして修復してからオフラインで検索する代わりに、データをインプレースのままにしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-151">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="ae2de-152">ただし、訴訟のライフサイクルの間に、新しいデータソースが保管担当者に関連付けられる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae2de-152">However, during the lifecycle of a legal case new data sources might be associated to a custodian.</span></span> <span data-ttu-id="ae2de-153">この場合は、高度なインデックス処理を再実行して、保管担当者のデータを再インデックス化して、部分的にインデックス付けされたアイテムを修復し、保管担当者のデータのインデックスを更新します。</span><span class="sxs-lookup"><span data-stu-id="ae2de-153">In this case, you re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="ae2de-154">部分的なインデックスが作成されたアイテムを処理するために、再インデックス処理をトリガーするには</span><span class="sxs-lookup"><span data-stu-id="ae2de-154">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="ae2de-155">**EDiscovery _GT_ Advanced ediscovery**に移動し、ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-155">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="ae2de-156">[**保管担当者] タブ**をクリックし、データが再インデックス化にする必要がある保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae2de-156">Click to **Custodians tab**, and then select a custodian whose data must be reindexed.</span></span> 

3. <span data-ttu-id="ae2de-157">[フライアウト] ページで、[**インデックスの更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae2de-157">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="ae2de-158">インデックスジョブが作成されたことを示すダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-158">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="ae2de-159">保管担当者データの再インデックス作成は、長時間実行されるプロセスです。作成された対応するジョブには、**保管担当者データの再インデックス**という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-159">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="ae2de-160">[**ジョブ**] タブまたは [**保管担当者**] タブで進行状況を追跡するには、[**インデックス作成ジョブの状態**] 列の状態を監視します。</span><span class="sxs-lookup"><span data-stu-id="ae2de-160">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="ae2de-161">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae2de-161">For more information, see:</span></span>

- [<span data-ttu-id="ae2de-162">処理中のエラーの操作</span><span class="sxs-lookup"><span data-stu-id="ae2de-162">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="ae2de-163">ジョブを管理する</span><span class="sxs-lookup"><span data-stu-id="ae2de-163">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="ae2de-164">ケースからの保管担当者のリリース</span><span class="sxs-lookup"><span data-stu-id="ae2de-164">Release a custodian from a case</span></span>

<span data-ttu-id="ae2de-165">保管担当者がリリースされるのは、ケースがクローズされた場合、保管担当者がケースのコンテンツを保持する義務がなくなった場合、または保管担当者がケースに関連していないと判断された場合です。</span><span class="sxs-lookup"><span data-stu-id="ae2de-165">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="ae2de-166">保留通知が公開された後に保管担当者をリリースした場合は、リリース通知が保管担当者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-166">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="ae2de-167">さらに、保管担当者に関連付けられたデータソースに配置されたすべての保留リストが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-167">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="ae2de-168">保管担当者が、法的情報保留通知を発行していない*サイレントホールド*に配置されていた場合、リリース通知は送信されませんが、その保管担当者に関連付けられていたデータソースに配置された保留リストは削除されます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-168">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="ae2de-169">保管担当者をリリースするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ae2de-169">To release a custodian:</span></span> 

1. <span data-ttu-id="ae2de-170">**EDiscovery _GT_ Advanced ediscovery**に移動し、ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-170">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2.  <span data-ttu-id="ae2de-171">[**保管担当者**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="ae2de-171">Go to the **Custodians** tab.</span></span>

3.  <span data-ttu-id="ae2de-172">[**保管担当者] タブ**をクリックし、ケースからリリースされる保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae2de-172">Click to **Custodians tab**, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="ae2de-173">[フライアウト] ページで、[ **Release 保管担当者**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae2de-173">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="ae2de-174">保管担当者に関連付けられたデータソースにホールドが設定されている場合、保留が解除され、別の高度な電子情報開示ケースに関連付けられている他のすべての保留が引き続き適用されることを説明する警告ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-174">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="ae2de-175">Office 365 (Office 365 アイテム保持ポリシーなど) の他の種類の保持および保持機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ae2de-175">That includes other types of preservation and retention features in Office 365 (such as an Office 365 retention policy).</span></span>

5. <span data-ttu-id="ae2de-176">[**はい**] をクリックして、保管担当者を解放することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae2de-176">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="ae2de-177">[**保管担当者**] タブでこのユーザーの状態が [**リリース**済み] に設定されていて、フライアウトページの**ホールド状態**が**False**に変更されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ae2de-177">Note that status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="ae2de-178">保管担当者は、いくつかの法的なケースに同時に関与する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae2de-178">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="ae2de-179">保管担当者がケースからリリースされた場合、他の事柄の保留と通知は影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="ae2de-179">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="ae2de-180">一括編集保管担当者</span><span class="sxs-lookup"><span data-stu-id="ae2de-180">Bulk-edit custodians</span></span>

<span data-ttu-id="ae2de-181">一括エディターを使用して、同時に複数の保管担当者を編集できます。</span><span class="sxs-lookup"><span data-stu-id="ae2de-181">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="ae2de-182">これを行うには、[**保管担当者**] タブで2つ以上の保管担当者を選択して一括エディターを表示し、タスクの1つをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae2de-182">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![複数の保管担当者の設定を編集するためのフライアウトページ](../media/AeDBulkEditCustodians.png)