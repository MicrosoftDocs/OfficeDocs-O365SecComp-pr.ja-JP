---
title: 廃棄レビューの概要
ms.author: stephow
author: stephow-MSFT
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
ms.assetid: d0c6095b-bfee-4906-a2c7-89c2d7f411c1
description: Office 365 内のコンテンツを保持するラベルを作成すると保存期間の終了時の廃棄の確認をトリガーすることができます。
ms.openlocfilehash: c0a2933f597c9b314ac4ce2e72de9619fac90082
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013721"
---
# <a name="overview-of-disposition-reviews"></a><span data-ttu-id="f6d4f-103">廃棄レビューの概要</span><span class="sxs-lookup"><span data-stu-id="f6d4f-103">Overview of disposition reviews</span></span>

<span data-ttu-id="f6d4f-p101">コンテンツには、保存期間の最後に達すると、いくつか考えられますかどうか安全に削除するかを決定するには、そのコンテンツを確認する理由 (「破棄」)。たとえば、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p101">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed"). For example, you might need to:</span></span>
  
- <span data-ttu-id="f6d4f-106">訴訟や監査に関連するコンテンツの削除 (「廃棄」) を中断します。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-106">Suspend the deletion ("disposition") of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="f6d4f-107">研究または履歴の値にそのコンテンツがある場合は、アーカイブに格納する廃棄リストからコンテンツを削除します。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-107">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="f6d4f-108">元のポリシーは、一時的、または仮のソリューションをした場合、コンテンツを別の保存期間を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-108">Assign a different retention period to the content, if the original policy was a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="f6d4f-109">コンテンツをクライアントに返すか、別の組織に転送します。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-109">Return the content to clients or transfer it to another organization.</span></span>
    
<span data-ttu-id="f6d4f-p102">Office 365 内のコンテンツを保持するラベルを作成すると保存期間の終了時の廃棄の確認をトリガーすることができます。廃棄の確認。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p102">When you create a label that retains content in Office 365, you can choose to trigger a disposition review at the end of the retention period. In a disposition review:</span></span>
  
- <span data-ttu-id="f6d4f-p103">電子メール通知を確認するのにはコンテンツがあることを選択したユーザーに表示されます。これらのレビュー担当者には、個々 のユーザー、配布またはセキュリティ グループ、または Office 365 のグループができます。毎週通知を送信することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p103">The people you choose receive an email notification that they have content to review. These reviewers can be individual users, distribution or security groups, or Office 365 groups. Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="f6d4f-115">校閲者ページに移動、**廃棄**セキュリティで&amp;の内容を確認するのにはコンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-115">The reviewers go to the **Disposition** page in the Security &amp; Compliance Center to review the content.</span></span> 
    
- <span data-ttu-id="f6d4f-116">ドキュメントごとに、レビュー担当者は次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-116">For each document, the reviewer can:</span></span>
    
  - <span data-ttu-id="f6d4f-117">別のラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-117">Apply a different label.</span></span>
    
  - <span data-ttu-id="f6d4f-118">保存期間が延長されます。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-118">Extend its retention period.</span></span>
    
  - <span data-ttu-id="f6d4f-119">完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-119">Permanently delete it.</span></span>
    
- <span data-ttu-id="f6d4f-120">校閲者は、保留中または過去のいずれかの処理方法を表示し、そのリストを .csv ファイルとしてエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-120">Reviewers can view either pending or historical dispositions, and export that list as a .csv file.</span></span>
    
<span data-ttu-id="f6d4f-121">その廃棄に注意してくださいレビューは、Office 365 エンタープライズ E5 のサブスクリプションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-121">Note that disposition reviews require an Office 365 Enterprise E5 subscription.</span></span>
  
<span data-ttu-id="f6d4f-p104">廃棄の確認では、Exchange メールボックス、SharePoint サイト、OneDrive アカウント、および Office 365 のグループにコンテンツを含めることができます。コンテンツを完全に削除する校閲者を選択した後にのみ、これらの場所での廃棄の確認を待機しているコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p104">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Office 365 groups. Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>
  
![廃棄のページ](media/b7436fb2-1f35-4146-8ca2-32c9d10f7e09.png)
  
## <a name="setting-up-the-disposition-review-by-creating-a-label"></a><span data-ttu-id="f6d4f-125">ラベルを作成することによって、廃棄の確認を設定します。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-125">Setting up the disposition review by creating a label</span></span>

<span data-ttu-id="f6d4f-p105">これは、廃棄の確認を設定するための基本的なワークフローです。公開され、ユーザーが手動で適用このフローのラベルの中に表示されている注意してください。また、廃棄の確認をトリガーするためのラベルでは、コンテンツへの自動適用もあります。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p105">This is the basic workflow for setting up a disposition review. Note that this flow shows a label being published and then manually applied by a user; alternatively, a label that triggers a disposition review can be auto-applied to content.</span></span>
  
![廃棄の動作の流れを示すグラフ](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="f6d4f-p106">廃棄の確認は、Office 365 でラベルを作成するときのオプションです。このオプションは、保存期間の設定のラベルでは、リテンション ・ ポリシーで利用可能ないないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p106">A disposition review is an option when you create a label in Office 365. Note that this option is not available in a retention policy but only in a label with retention settings.</span></span>
  
<span data-ttu-id="f6d4f-131">ラベルの詳細については、[ラベルの概要](labels.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-131">For more information about labels, see [Overview of labels](labels.md).</span></span>
  
![ラベルの保存期間の設定](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a><span data-ttu-id="f6d4f-133">コンテンツの破棄</span><span class="sxs-lookup"><span data-stu-id="f6d4f-133">Disposing content</span></span>

<span data-ttu-id="f6d4f-p107">校閲者に電子メールで通知するとコンテンツを確認する準備は、移動することが、**廃棄**のページに、セキュリティ&amp;コンプライアンス センターと 1 つまたは複数の項目を選択します。校閲者が、ことができます。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p107">When a reviewer is notified by email that content is ready to review, they can go to the **Disposition** page in the Security &amp; Compliance Center and select one or more items. The reviewer can then:</span></span> 
  
- <span data-ttu-id="f6d4f-136">別のラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-136">Apply a different label.</span></span>
    
- <span data-ttu-id="f6d4f-137">保存期間を延長します。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-137">Extend the retention period.</span></span>
    
- <span data-ttu-id="f6d4f-138">アイテムを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-138">Permanently delete the item.</span></span>
    
<span data-ttu-id="f6d4f-p108">校閲者が校閲者がその場所に対するアクセス許可を持つ場合、元の場所にドキュメントを表示するのにはリンクを使用できます。廃棄の確認では、実行中にコンテンツが元の場所から移動しないと、校閲者が選択するまでは削除されません。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p108">A reviewer can use the link to view the document in its original location, if the reviewer has permissions for that location. During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>
  
<span data-ttu-id="f6d4f-p109">毎週のレビュー担当者に電子メール通知が自動的に送信するに注意してください。したがって、コンテンツには、保存期間の最後に達すると、かかる場合があります最大 7 日間の校閲者に電子メール通知を受信するコンテンツを廃棄待ちの状態です。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p109">Note that the email notifications are sent automatically to reviewers on a weekly basis. Therefore, when content reaches the end of its retention period, it may take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="f6d4f-p110">廃棄のすべてのアクションを監査することにも注意してください。、そのためには、詳細については最初の廃棄アクションの前に少なくとも 1 日に監査を有効に、を参照してくださいする必要があります[では、Office 365 のセキュリティ監査ログを検索する&amp;コンプライアンス センター](search-the-audit-log-in-security-and-compliance.md)です。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p110">Also note that all disposition actions are audited. To ensure this, you must turn on auditing at least one day prior to the first disposition action - for more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 
  
![ドキュメントの廃棄オプション](media/771630fd-a9b0-47cf-983b-fe85eb4cdafd.png)
  
## <a name="permissions-for-disposition"></a><span data-ttu-id="f6d4f-146">廃棄の許可</span><span class="sxs-lookup"><span data-stu-id="f6d4f-146">Permissions for disposition</span></span>

<span data-ttu-id="f6d4f-p111">**廃棄**のページへのアクセスを取得するには、校閲者は、**廃棄の管理**役割と**監査ログの参照**ロールのメンバーをする必要があります。廃棄の承認者と呼ばれる新しい役割グループを作成して、その役割グループにこれらの 2 つの役割を追加する、役割グループにメンバーを追加をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p111">To get access to the **Disposition** page, reviewers must be members of the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="f6d4f-149">詳細についてを参照してください[Office 365 のセキュリティにアクセスできるように&amp;コンプライアンス センター](grant-access-to-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="f6d4f-149">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md)</span></span>
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="f6d4f-150">破棄されたコンテンツが完全に削除するまでの時間</span><span class="sxs-lookup"><span data-stu-id="f6d4f-150">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="f6d4f-p112">コンテンツを完全に削除する校閲者を選択した後にのみ、廃棄の確認を待機しているコンテンツが削除されます。レビュー担当者は、このオプションを選択、OneDrive アカウントと SharePoint サイトのコンテンツにこのセクションで説明されている標準的なクリーンアップ処理の対象となります:[リテンション ・ ポリシーのしくみにコンテンツを配置](retention-policies.md#how-a-retention-policy-works-with-content-in-place)します。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p112">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content. When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in this section: [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>
  
<span data-ttu-id="f6d4f-153">これは、ことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-153">This means that:</span></span>
  
- <span data-ttu-id="f6d4f-p113">ドキュメント ライブラリ内のコンテンツが表示される最初のステージのごみ箱にある**7 日以内**の廃棄に移動し、その後**93 日間**を完全に削除します。ごみ箱は、検索でインデックス付けされていないあり、その内容、電子的証拠開示の保留リストに使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p113">Content in a document library will be moved to the first-stage Recycle Bin **within 7 days** of disposition, and then permanently deleted **93 days** after that. The Recycle Bin is not indexed by search and therefore its contents are not available to an eDiscovery hold.</span></span> 
    
- <span data-ttu-id="f6d4f-156">コンテンツ ・ ライブラリは完全には保持保持では、 **7 日以内**の廃棄削除。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-156">Content in the Preservation Hold library will be permanently deleted **within 7 days** of disposition.</span></span> 
    
## <a name="view-pending-and-completed-dispositions"></a><span data-ttu-id="f6d4f-157">保留中の表示と完了した処理方法</span><span class="sxs-lookup"><span data-stu-id="f6d4f-157">View pending and completed dispositions</span></span>

<span data-ttu-id="f6d4f-158">[**廃棄**] ページで、セキュリティの&amp;コンプライアンス センターでは、保留中および完了済みの両方の処理方法を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-158">On the **Disposition** page of the Security &amp; Compliance Center, you can view both pending and completed dispositions:</span></span> 
  
- <span data-ttu-id="f6d4f-p114">**保留中**の処理方法は、保存期間の終わりに達しましたし、廃棄の確認を必要とします。各項目を確認するには後に、別のラベルを適用、その保有期間を延長または完全に削除するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p114">**Pending** dispositions have reached the end of their retention period and require a disposition review. After reviewing each item, decide if you want to apply a different label to it, extend its retention period, or permanently delete it.</span></span> 
    
- <span data-ttu-id="f6d4f-p115">**完了**の処理方法は、廃棄の確認中に削除のために承認され、して完全に削除されるようになりましたが。別のラベルを適用またはその期間のレビューの一部がここに表示されないように拡張される項目。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p115">**Completed** dispositions were approved for deletion during a disposition review and are now in the process of being permanently deleted. Items that had a different label applied or their retention period extended as part of a review won't appear here.</span></span> 
    
### <a name="filter-the-disposition-views"></a><span data-ttu-id="f6d4f-163">廃棄のビューにフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-163">Filter the disposition views</span></span>

<span data-ttu-id="f6d4f-p116">ラベルまたは時間の範囲では、これらのビューをフィルターできます。保留中の処理方法、時間の範囲はベースの有効期限日です。履歴の処理方法については、時間範囲は削除の日付に基づいています。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-p116">You can filter these views by label or time range. For pending dispositions, the time range is based on the expiry date. For historical dispositions, the time range is based on the deletion date.</span></span>
  
![[廃棄] ページのフィルター オプション](media/8682a9f5-a77d-45ae-b902-8418a3ebbea1.png)
  
### <a name="export-the-disposition-items"></a><span data-ttu-id="f6d4f-168">廃棄の項目をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-168">Export the disposition items</span></span>

<span data-ttu-id="f6d4f-169">さらに、いずれかのビュー内の項目を Excel で開くことができる .csv ファイルとしてエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="f6d4f-169">In addition, you can export the items in either view as a .csv file that you can open in Excel.</span></span>
  
![データを Excel にエクスポートした廃棄](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

