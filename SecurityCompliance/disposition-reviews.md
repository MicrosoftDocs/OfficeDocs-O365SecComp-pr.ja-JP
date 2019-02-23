---
title: 廃棄レビューの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: d0c6095b-bfee-4906-a2c7-89c2d7f411c1
description: Office 365 のコンテンツを保持するラベルを作成する場合、保持期間の終了時に廃棄レビューを開始することを選択できます。
ms.openlocfilehash: 0948d61131595d4111f656c385c58258c5cce99c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215007"
---
# <a name="overview-of-disposition-reviews"></a><span data-ttu-id="7cbc0-103">廃棄レビューの概要</span><span class="sxs-lookup"><span data-stu-id="7cbc0-103">Overview of disposition reviews</span></span>

<span data-ttu-id="7cbc0-p101">コンテンツが保存期間の最後に達すると、いくつかの理由から、そのコンテンツを確認して、安全に削除できるかどうかを判断する必要があります (「廃棄済み」)。たとえば、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p101">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed"). For example, you might need to:</span></span>
  
- <span data-ttu-id="7cbc0-106">訴訟や監査の際に、関連するコンテンツの削除 ("廃棄") を中断します。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-106">Suspend the deletion ("disposition") of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="7cbc0-107">コンテンツにリサーチまたは履歴の値がある場合は、廃棄リストからコンテンツを削除してアーカイブに保存します。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-107">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="7cbc0-108">元のポリシーが一時的または暫定ソリューションだった場合は、コンテンツに異なる保存期間を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-108">Assign a different retention period to the content, if the original policy was a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="7cbc0-109">クライアントにコンテンツを返すか、または別の組織に転送します。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-109">Return the content to clients or transfer it to another organization.</span></span>
    
<span data-ttu-id="7cbc0-p102">Office 365 のコンテンツを保持するラベルを作成する場合、保持期間の終了時に廃棄レビューを開始することを選択できます。廃棄レビューの場合:</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p102">When you create a label that retains content in Office 365, you can choose to trigger a disposition review at the end of the retention period. In a disposition review:</span></span>
  
- <span data-ttu-id="7cbc0-p103">選択したユーザーには、閲覧するコンテンツがあることを示す電子メール通知が送信されます。これらのレビュー担当者は、個別のユーザー、配布グループまたはセキュリティグループ、または Office 365 グループにすることができます。通知は週単位で送信されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p103">The people you choose receive an email notification that they have content to review. These reviewers can be individual users, distribution or security groups, or Office 365 groups. Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="7cbc0-115">レビュー担当者は、 \*\*\*\* セキュリティ&amp;コンプライアンスセンターの [廃棄] ページに移動して、コンテンツを確認します。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-115">The reviewers go to the **Disposition** page in the Security &amp; Compliance Center to review the content.</span></span> 
    
- <span data-ttu-id="7cbc0-116">レビュー担当者は、ドキュメントごとに次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-116">For each document, the reviewer can:</span></span>
    
  - <span data-ttu-id="7cbc0-117">別のラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-117">Apply a different label.</span></span>
    
  - <span data-ttu-id="7cbc0-118">その保持期間を延長します。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-118">Extend its retention period.</span></span>
    
  - <span data-ttu-id="7cbc0-119">完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-119">Permanently delete it.</span></span>
    
- <span data-ttu-id="7cbc0-120">レビュー担当者は保留中または履歴の廃棄を表示し、その一覧を .csv ファイルとしてエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-120">Reviewers can view either pending or historical dispositions, and export that list as a .csv file.</span></span>
    
<span data-ttu-id="7cbc0-121">廃棄レビューには Office 365 Enterprise E5 サブスクリプションが必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-121">Note that disposition reviews require an Office 365 Enterprise E5 subscription.</span></span>
  
<span data-ttu-id="7cbc0-p104">廃棄レビューには、Exchange メールボックス、SharePoint サイト、OneDrive アカウント、および Office 365 グループのコンテンツを含めることができます。これらの場所の廃棄レビューを待機しているコンテンツは、レビュー担当者がコンテンツを完全に削除することを選択した場合にのみ削除されます。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p104">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Office 365 groups. Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>
  
![ディスポジションページ](media/b7436fb2-1f35-4146-8ca2-32c9d10f7e09.png)
  
## <a name="setting-up-the-disposition-review-by-creating-a-label"></a><span data-ttu-id="7cbc0-125">ラベルを作成して廃棄レビューを設定する</span><span class="sxs-lookup"><span data-stu-id="7cbc0-125">Setting up the disposition review by creating a label</span></span>

<span data-ttu-id="7cbc0-p105">これは、廃棄レビューを設定するための基本的なワークフローです。このフローには、公開されているラベルと、ユーザーが手動で適用したラベルが表示されることに注意してください。または、廃棄レビューをトリガーするラベルをコンテンツに自動的に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p105">This is the basic workflow for setting up a disposition review. Note that this flow shows a label being published and then manually applied by a user; alternatively, a label that triggers a disposition review can be auto-applied to content.</span></span>
  
![廃棄のしくみを示す図](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="7cbc0-p106">廃棄レビューは、Office 365 でラベルを作成する場合のオプションです。このオプションは、アイテム保持ポリシーでは使用できませんが、アイテム保持設定のラベルにのみ表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p106">A disposition review is an option when you create a label in Office 365. Note that this option is not available in a retention policy but only in a label with retention settings.</span></span>
  
<span data-ttu-id="7cbc0-131">ラベルの詳細については、「[ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-131">For more information about labels, see [Overview of labels](labels.md).</span></span>
  
![ラベルの保持設定](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a><span data-ttu-id="7cbc0-133">コンテンツを破棄する</span><span class="sxs-lookup"><span data-stu-id="7cbc0-133">Disposing content</span></span>

<span data-ttu-id="7cbc0-p107">コンテンツがレビューできる状態であることをレビュー担当者に電子メールで通知する場合\*\*\*\* は、セキュリティ&amp;コンプライアンスセンターの [廃棄] ページに移動して、1つ以上のアイテムを選択できます。レビュー担当者は次のことができます。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p107">When a reviewer is notified by email that content is ready to review, they can go to the **Disposition** page in the Security &amp; Compliance Center and select one or more items. The reviewer can then:</span></span> 
  
- <span data-ttu-id="7cbc0-136">別のラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-136">Apply a different label.</span></span>
    
- <span data-ttu-id="7cbc0-137">保持期間を延長します。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-137">Extend the retention period.</span></span>
    
- <span data-ttu-id="7cbc0-138">アイテムを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-138">Permanently delete the item.</span></span>
    
<span data-ttu-id="7cbc0-p108">レビュー担当者は、リンクを使用して、校閲者がその場所に対する権限を持っていれば、元の場所でドキュメントを表示することができます。廃棄レビュー中は、コンテンツは元の場所から移動されません。また、レビュー担当者がそのように選択しない限り、削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p108">A reviewer can use the link to view the document in its original location, if the reviewer has permissions for that location. During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>
  
<span data-ttu-id="7cbc0-p109">電子メール通知は、1週間ごとにレビュー担当者に自動的に送信されることに注意してください。そのため、コンテンツが保持期間の最後に達すると、コンテンツが廃棄を待機しているというメール通知をレビューアーが受け取るまでに最大7日かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p109">Note that the email notifications are sent automatically to reviewers on a weekly basis. Therefore, when content reaches the end of its retention period, it may take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="7cbc0-p110">また、すべての廃棄アクションが監査されることにも注意してください。このことを確認するには、最初の廃棄アクションの前に少なくとも1日前に監査を有効にする必要があります。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p110">Also note that all disposition actions are audited. To ensure this, you must turn on auditing at least one day prior to the first disposition action - for more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 
  
![ドキュメントの廃棄オプション](media/771630fd-a9b0-47cf-983b-fe85eb4cdafd.png)
  
## <a name="permissions-for-disposition"></a><span data-ttu-id="7cbc0-146">廃棄のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="7cbc0-146">Permissions for disposition</span></span>

<span data-ttu-id="7cbc0-p111">[**廃棄**] ページへのアクセスを取得するには、レビュー担当者が**廃棄管理**役割および**表示専用の監査ログ**役割のメンバーである必要があります。廃棄レビュー担当者という新しい役割グループを作成し、この2つの役割をその役割グループに追加して、役割グループにメンバーを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p111">To get access to the **Disposition** page, reviewers must be members of the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="7cbc0-149">詳細については、「[ユーザーに Office 365 セキュリティ&amp;コンプライアンスセンターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-149">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md)</span></span>
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="7cbc0-150">破棄されたコンテンツが完全に削除されるまでの時間</span><span class="sxs-lookup"><span data-stu-id="7cbc0-150">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="7cbc0-p112">廃棄レビューを待機しているコンテンツは、レビュー担当者がコンテンツを完全に削除することを選択した場合にのみ削除されます。レビュー担当者がこのオプションを選択すると、SharePoint サイトまたは OneDrive アカウントのコンテンツは、このセクションで説明されている標準的なクリーンアッププロセスの対象となります。[アイテム保持ポリシーがコンテンツをインプレースでどのように動作するか](retention-policies.md#how-a-retention-policy-works-with-content-in-place)を指定します。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p112">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content. When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in this section: [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>
  
<span data-ttu-id="7cbc0-153">これは、次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-153">This means that:</span></span>
  
- <span data-ttu-id="7cbc0-p113">ドキュメントライブラリ内のコンテンツは、廃棄の**7 日以内**に第1段階のごみ箱に移動され、その後は**93 日**後に完全に削除されます。ごみ箱には検索によってインデックスが作成されないため、電子情報開示ホールドでそのコンテンツを使用できません。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p113">Content in a document library will be moved to the first-stage Recycle Bin **within 7 days** of disposition, and then permanently deleted **93 days** after that. The Recycle Bin is not indexed by search and therefore its contents are not available to an eDiscovery hold.</span></span> 
    
- <span data-ttu-id="7cbc0-156">保持保持ライブラリのコンテンツは、廃棄から**7 日以内**に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-156">Content in the Preservation Hold library will be permanently deleted **within 7 days** of disposition.</span></span> 
    
## <a name="view-pending-and-completed-dispositions"></a><span data-ttu-id="7cbc0-157">保留中および完了した廃棄を表示する</span><span class="sxs-lookup"><span data-stu-id="7cbc0-157">View pending and completed dispositions</span></span>

<span data-ttu-id="7cbc0-158">セキュリティ&amp; /コンプライアンスセンターの [**廃棄**] ページでは、保留中および完了した処理の両方を表示できます。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-158">On the **Disposition** page of the Security &amp; Compliance Center, you can view both pending and completed dispositions:</span></span> 
  
- <span data-ttu-id="7cbc0-p114">**保留中**のディスポジションは、保持期間の最後に達したため、廃棄レビューを必要としています。各項目を確認した後、別のラベルを適用するかどうかを決定し、その保持期間を延長するか、完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p114">**Pending** dispositions have reached the end of their retention period and require a disposition review. After reviewing each item, decide if you want to apply a different label to it, extend its retention period, or permanently delete it.</span></span> 
    
- <span data-ttu-id="7cbc0-p115">**完了**した処理は、廃棄の確認中に削除のために承認され、完全に削除中の状態になりました。別のラベルが適用されたアイテム、またはレビューの一部として拡張されたアイテムの保持期間は、ここに表示されません。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p115">**Completed** dispositions were approved for deletion during a disposition review and are now in the process of being permanently deleted. Items that had a different label applied or their retention period extended as part of a review won't appear here.</span></span> 
    
### <a name="filter-the-disposition-views"></a><span data-ttu-id="7cbc0-163">廃棄ビューをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="7cbc0-163">Filter the disposition views</span></span>

<span data-ttu-id="7cbc0-p116">これらのビューは、ラベルまたは時間の範囲によってフィルター処理できます。保留中の処理の場合、時間範囲は有効期限日に基づきます。歴史的な種類の場合、期間は削除日に基づいています。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-p116">You can filter these views by label or time range. For pending dispositions, the time range is based on the expiry date. For historical dispositions, the time range is based on the deletion date.</span></span>
  
![[廃棄] ページのフィルターオプション](media/8682a9f5-a77d-45ae-b902-8418a3ebbea1.png)
  
### <a name="export-the-disposition-items"></a><span data-ttu-id="7cbc0-168">廃棄アイテムをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="7cbc0-168">Export the disposition items</span></span>

<span data-ttu-id="7cbc0-169">また、いずれかのビューのアイテムを .csv ファイルとしてエクスポートして、Excel で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="7cbc0-169">In addition, you can export the items in either view as a .csv file that you can open in Excel.</span></span>
  
![Excel でエクスポートされた廃棄データ](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

