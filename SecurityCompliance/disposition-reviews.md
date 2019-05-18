---
title: 廃棄レビューの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 のコンテンツを保持する保持ラベルを作成する場合、保持期間の終了時に廃棄のレビューを開始することを選択できます。
ms.openlocfilehash: 6d4a8993efb3046e7f79f4e76a921921abf6d3e6
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153429"
---
# <a name="overview-of-disposition-reviews"></a><span data-ttu-id="e25ac-103">廃棄レビューの概要</span><span class="sxs-lookup"><span data-stu-id="e25ac-103">Overview of disposition reviews</span></span>

<span data-ttu-id="e25ac-104">コンテンツが保存期間の最後に達すると、いくつかの理由から、そのコンテンツを確認して、安全に削除できるかどうかを判断する必要があります (「廃棄済み」)。</span><span class="sxs-lookup"><span data-stu-id="e25ac-104">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="e25ac-105">たとえば、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e25ac-105">For example, you might need to:</span></span>
  
- <span data-ttu-id="e25ac-106">訴訟や監査の際に、関連するコンテンツの削除 ("廃棄") を中断します。</span><span class="sxs-lookup"><span data-stu-id="e25ac-106">Suspend the deletion ("disposition") of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="e25ac-107">コンテンツにリサーチまたは履歴の値がある場合は、廃棄リストからコンテンツを削除してアーカイブに保存します。</span><span class="sxs-lookup"><span data-stu-id="e25ac-107">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="e25ac-108">元のポリシーが一時的または暫定ソリューションだった場合は、コンテンツに異なる保存期間を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-108">Assign a different retention period to the content, if the original policy was a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="e25ac-109">クライアントにコンテンツを返すか、または別の組織に転送します。</span><span class="sxs-lookup"><span data-stu-id="e25ac-109">Return the content to clients or transfer it to another organization.</span></span>
    
<span data-ttu-id="e25ac-110">Microsoft 365 コンプライアンスセンター、Microsoft 365 セキュリティセンター、または Office 365 Security & コンプライアンスセンターで保持ラベルを作成する場合、保持期間の終了時に廃棄レビューを開始することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-110">When you create a retention label in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center, you can choose to trigger a disposition review at the end of the retention period.</span></span> <span data-ttu-id="e25ac-111">廃棄レビューの場合:</span><span class="sxs-lookup"><span data-stu-id="e25ac-111">In a disposition review:</span></span>
  
- <span data-ttu-id="e25ac-112">選択したユーザーには、閲覧するコンテンツがあることを示す電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-112">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="e25ac-113">これらのレビュー担当者は、個別のユーザー、配布グループまたはセキュリティグループ、または Office 365 グループにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-113">These reviewers can be individual users, distribution or security groups, or Office 365 groups.</span></span> <span data-ttu-id="e25ac-114">通知は週単位で送信されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e25ac-114">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="e25ac-115">レビュー担当者は、 \*\*\*\* セキュリティ&amp;コンプライアンスセンターの [廃棄] ページに移動して、コンテンツを確認します。</span><span class="sxs-lookup"><span data-stu-id="e25ac-115">The reviewers go to the **Disposition** page in the Security &amp; Compliance Center to review the content.</span></span> <span data-ttu-id="e25ac-116">レビュー担当者は、廃棄を待機している各保持ラベルのアイテム数を確認し、そのラベルを持つすべてのコンテンツを表示する保持ラベルを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-116">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>
    
- <span data-ttu-id="e25ac-117">レビュー担当者は、ドキュメントまたは電子メールごとに次のことを行えます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-117">For each document or email, the reviewer can:</span></span>
    
  - <span data-ttu-id="e25ac-118">別の保持ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="e25ac-118">Apply a different retention label.</span></span>
    
  - <span data-ttu-id="e25ac-119">その保持期間を延長します。</span><span class="sxs-lookup"><span data-stu-id="e25ac-119">Extend its retention period.</span></span>
    
  - <span data-ttu-id="e25ac-120">完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="e25ac-120">Permanently delete it.</span></span>
    
- <span data-ttu-id="e25ac-121">レビュー担当者は、保留中または完了した処理のいずれかを表示し、その一覧を .csv ファイルとしてエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-121">Reviewers can view either pending or completed dispositions, and export that list as a .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="e25ac-122">廃棄レビューには、Office 365 Enterprise E5 サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="e25ac-122">Disposition reviews require an Office 365 Enterprise E5 subscription.</span></span>
  
<span data-ttu-id="e25ac-123">廃棄レビューには、Exchange メールボックス、SharePoint サイト、OneDrive アカウント、および Office 365 グループのコンテンツを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-123">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Office 365 groups.</span></span> <span data-ttu-id="e25ac-124">これらの場所の廃棄レビューを待機しているコンテンツは、レビュー担当者がコンテンツを完全に削除することを選択した場合にのみ削除されます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-124">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>
  
![セキュリティ/コンプライアンスセンターの [配置] ページ](media/Retention_Dispositions_v2_page.png)

## <a name="setting-up-the-disposition-review-by-creating-a-retention-label"></a><span data-ttu-id="e25ac-126">保持ラベルを作成して廃棄レビューを設定する</span><span class="sxs-lookup"><span data-stu-id="e25ac-126">Setting up the disposition review by creating a retention label</span></span>

<span data-ttu-id="e25ac-127">これは、廃棄レビューを設定するための基本的なワークフローです。</span><span class="sxs-lookup"><span data-stu-id="e25ac-127">This is the basic workflow for setting up a disposition review.</span></span> <span data-ttu-id="e25ac-128">このフローには、公開されている保持ラベルと、ユーザーによって手動で適用されるものが示されることに注意してください。または、廃棄レビューをトリガーする保持ラベルをコンテンツに自動適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-128">Note that this flow shows a retention label being published and then manually applied by a user; alternatively, a retention label that triggers a disposition review can be auto-applied to content.</span></span>
  
![廃棄のしくみを示す図](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="e25ac-130">廃棄のレビューは、Office 365 で保持ラベルを作成する場合のオプションです。</span><span class="sxs-lookup"><span data-stu-id="e25ac-130">A disposition review is an option when you create a retention label in Office 365.</span></span> <span data-ttu-id="e25ac-131">このオプションは、アイテム保持ポリシーでは使用できませんが、コンテンツを保持するように構成された保持ラベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-131">Note that this option is not available in a retention policy but only in a retention label that's configured to retain content.</span></span>
  
<span data-ttu-id="e25ac-132">保持ラベルの詳細については、「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e25ac-132">For more information about retention labels, see [Overview of retention labels](labels.md).</span></span>
  
![ラベルの保持設定](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a><span data-ttu-id="e25ac-134">コンテンツを破棄する</span><span class="sxs-lookup"><span data-stu-id="e25ac-134">Disposing content</span></span>

<span data-ttu-id="e25ac-135">コンテンツがレビューできる状態であることをレビュー担当者に電子メールで通知する場合\*\*\*\* は、セキュリティ&amp;コンプライアンスセンターの [廃棄] ページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-135">When a reviewer is notified by email that content is ready to review, they can go to the **Disposition** page in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="e25ac-136">レビュー担当者は、廃棄を待機している各保持ラベルのアイテム数を確認し、そのラベルを持つすべてのコンテンツを表示する保持ラベルを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-136">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="e25ac-137">保持ラベルを選択すると、次のページにそのラベルの保留中のすべての実行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-137">After you select a retention label, the next page shows all pending dispositions for that label.</span></span>

![ディスポジションオプション](media/Retention_Disposition_options_v2.png)

<span data-ttu-id="e25ac-139">レビュー担当者は次のことができます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-139">The reviewer can then:</span></span> 
  
- <span data-ttu-id="e25ac-140">別の保持ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="e25ac-140">Apply a different retention label.</span></span>
    
- <span data-ttu-id="e25ac-141">保持期間を延長します。</span><span class="sxs-lookup"><span data-stu-id="e25ac-141">Extend the retention period.</span></span>
    
- <span data-ttu-id="e25ac-142">アイテムを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="e25ac-142">Permanently delete the item.</span></span>

<span data-ttu-id="e25ac-143">レビューアーは複数のアイテムを選択し、それらを同時に破棄することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e25ac-143">Note that a reviewer can select multiple items and dispose them at the same time.</span></span>
    
<span data-ttu-id="e25ac-144">レビュー担当者は、このリンクを使用して、その場所へのアクセス許可がある場合に、元の場所にドキュメントを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-144">A reviewer can also use the link to view the document in its original location, if the reviewer has permissions for that location.</span></span> <span data-ttu-id="e25ac-145">廃棄レビュー中は、コンテンツは元の場所から移動されません。また、レビュー担当者がそのように選択しない限り、削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="e25ac-145">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>
  
<span data-ttu-id="e25ac-146">電子メール通知は、1週間ごとにレビュー担当者に自動的に送信されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e25ac-146">Note that the email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="e25ac-147">そのため、コンテンツが保持期間の最後に達すると、コンテンツが廃棄を待機しているというメール通知をレビューアーが受け取るまでに最大7日かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e25ac-147">Therefore, when content reaches the end of its retention period, it may take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="e25ac-148">また、すべての廃棄アクションが監査されることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="e25ac-148">Also note that all disposition actions are audited.</span></span> <span data-ttu-id="e25ac-149">このことを確認するには、最初の廃棄アクションの前に少なくとも1日前に監査を有効にする必要があります。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e25ac-149">To ensure this, you must turn on auditing at least one day prior to the first disposition action - for more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 
  
## <a name="permissions-for-disposition"></a><span data-ttu-id="e25ac-150">廃棄のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e25ac-150">Permissions for disposition</span></span>

<span data-ttu-id="e25ac-151">[**廃棄**] ページへのアクセスを取得するには、レビュー担当者が**廃棄管理**役割および**表示専用の監査ログ**役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e25ac-151">To get access to the **Disposition** page, reviewers must be members of the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="e25ac-152">廃棄レビュー担当者という新しい役割グループを作成し、この2つの役割をその役割グループに追加して、役割グループにメンバーを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e25ac-152">We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="e25ac-153">詳細については、「[ユーザーに Office 365 セキュリティ&amp;コンプライアンスセンターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e25ac-153">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md)</span></span>
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="e25ac-154">破棄されたコンテンツが完全に削除されるまでの時間</span><span class="sxs-lookup"><span data-stu-id="e25ac-154">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="e25ac-155">廃棄レビューを待機しているコンテンツは、レビュー担当者がコンテンツを完全に削除することを選択した場合にのみ削除されます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-155">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="e25ac-156">レビュー担当者がこのオプションを選択すると、SharePoint サイトまたは OneDrive アカウントのコンテンツは、このセクションで説明されている標準的なクリーンアッププロセスの対象となります。[アイテム保持ポリシーがコンテンツをインプレースでどのように動作するか](retention-policies.md#how-a-retention-policy-works-with-content-in-place)を指定します。</span><span class="sxs-lookup"><span data-stu-id="e25ac-156">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in this section: [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>
  
<span data-ttu-id="e25ac-157">これは、次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e25ac-157">This means that:</span></span>
  
- <span data-ttu-id="e25ac-158">ドキュメントライブラリ内のコンテンツは、廃棄の**7 日以内**に第1段階のごみ箱に移動され、その後は**93 日**後に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-158">Content in a document library will be moved to the first-stage Recycle Bin **within 7 days** of disposition, and then permanently deleted **93 days** after that.</span></span> <span data-ttu-id="e25ac-159">ごみ箱には検索によってインデックスが作成されないため、電子情報開示ホールドでそのコンテンツを使用できません。</span><span class="sxs-lookup"><span data-stu-id="e25ac-159">The Recycle Bin is not indexed by search and therefore its contents are not available to an eDiscovery hold.</span></span>

- <span data-ttu-id="e25ac-160">保持保持ライブラリのコンテンツは、廃棄から**7 日以内**に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-160">Content in the Preservation Hold library will be permanently deleted **within 7 days** of disposition.</span></span>

- <span data-ttu-id="e25ac-161">Exchange メールボックス内のアイテムは、廃棄から**14 日以内**に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-161">Items in an Exchange mailbox will be permanently deleted **within 14 days** of disposition.</span></span> <span data-ttu-id="e25ac-162">(既定の設定は14日であることに注意してくださいが、最大30日間構成できます)。</span><span class="sxs-lookup"><span data-stu-id="e25ac-162">(Note that 14 days is the default setting but it can be configured up to 30 days.)</span></span>
    
## <a name="view-pending-dispositions-and-disposed-items"></a><span data-ttu-id="e25ac-163">保留中の廃棄と破棄されたアイテムを表示する</span><span class="sxs-lookup"><span data-stu-id="e25ac-163">View pending dispositions and disposed items</span></span>

<span data-ttu-id="e25ac-164">[**保留中の廃棄**] ページでは、特定の保持ラベルについて、保留中および完了済みの両方の処理を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-164">On the **Pending disposition** page, you can view both pending and completed dispositions for a specific retention label:</span></span> 
  
- <span data-ttu-id="e25ac-165">**保留中の廃棄**は、保持期間の最後に達し、廃棄レビューを必要とするアイテムを示します。</span><span class="sxs-lookup"><span data-stu-id="e25ac-165">The **Pending disposition** shows items that have reached the end of their retention period and require a disposition review.</span></span> <span data-ttu-id="e25ac-166">各項目を確認した後、別の保持ラベルを適用するか、その保持期間を延長するか、または完全に削除するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e25ac-166">After reviewing each item, decide if you want to apply a different retention label to it, extend its retention period, or permanently delete it.</span></span> <span data-ttu-id="e25ac-167">複数のアイテムを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-167">You can select multiple items.</span></span>
    
- <span data-ttu-id="e25ac-168">[**破棄**されたアイテム] タブには、廃棄レビュー中に削除が承認され、完全に削除処理中であることが示されます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-168">The **Disposed items** tab shows dispositions were approved for deletion during a disposition review and are now in the process of being permanently deleted.</span></span> <span data-ttu-id="e25ac-169">別の保持ラベルが適用されたアイテム、またはレビューの一部として延長されたアイテムの保持期間は、ここに表示されません。</span><span class="sxs-lookup"><span data-stu-id="e25ac-169">Items that had a different retention label applied or their retention period extended as part of a review won't appear here.</span></span>

![ディスポジションタブ](media/Retention_Disposition_tabs.png)
    
### <a name="filter-the-disposition-views"></a><span data-ttu-id="e25ac-171">廃棄ビューをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="e25ac-171">Filter the disposition views</span></span>

<span data-ttu-id="e25ac-172">これらのビューは、保持ラベルまたは時間範囲によってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-172">You can filter these views by retention label or time range.</span></span> <span data-ttu-id="e25ac-173">保留中の処理の場合、時間の範囲は有効期限に基づきます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-173">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="e25ac-174">破棄されたアイテムの場合、時間範囲は、削除日に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e25ac-174">For disposed items, the time range is based on the deletion date.</span></span>
  
![廃棄フィルターオプション](media/Retention_filter_options.png)

### <a name="export-the-disposition-items"></a><span data-ttu-id="e25ac-176">廃棄アイテムをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e25ac-176">Export the disposition items</span></span>

<span data-ttu-id="e25ac-177">また、いずれかのビューのアイテムを .csv ファイルとしてエクスポートして、Excel で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="e25ac-177">In addition, you can export the items in either view as a .csv file that you can open in Excel.</span></span>
  
![Excel でエクスポートされた廃棄データ](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

