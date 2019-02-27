---
title: Microsoft 365 のデータ調査用リリースノート (プレビュー)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: この記事では、Microsoft 365 の高度な電子情報開示 (プレビュー) の新バージョンについて説明します。
ms.openlocfilehash: 900031815ef1a2bbbd770c22db958659d8a0ef99
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30297030"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a><span data-ttu-id="6dbb6-103">Microsoft 365 のデータ調査用リリースノート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="6dbb6-103">Release notes for Data Investigations (Preview) in Microsoft 365</span></span>

<span data-ttu-id="6dbb6-p101">Microsoft 365 の新しいデータ調査 (プレビュー) ツールを使用して、データ流出インシデントや内部調査などのデータ関連インシデントのトリアージ、調査、および修復を行うことができます。データ調査のパブリックプレビューを使用すると、今後予定されている機能と更新プログラムに早期にアクセスできます。最新の機能にいち早くアクセスするには、Office 365 Security & コンプライアンスセンターでデータの調査 (プレビュー) に新しい調査を作成します。その方法については、「 [Manage a data 流出 incident in Microsoft 365](manage-data-spillage-incidents.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dbb6-p101">You can use the new Data Investigations (Preview) tool in in Microsoft 365 to triage, investigate, and remediate data related incidents, such as a data spillage incident or an internal investigation. The Public Preview of Data investigations provides you with early access to the upcoming functionality and updates. To get early access to the newest features, create a new investigation in Data investigations (Preview) in the Office 365 Security & Compliance Center. To learn how, see [Manage a data spillage incident in Microsoft 365](manage-data-spillage-incidents.md).</span></span>

## <a name="whats-new"></a><span data-ttu-id="6dbb6-108">新機能</span><span class="sxs-lookup"><span data-stu-id="6dbb6-108">What’s new</span></span> 

- <span data-ttu-id="6dbb6-p102">\*\*\*\* 調査-調査を作成することで、検索とインシデントをグループ化できます。メンバーを追加または削除することで、調査にアクセスできるユーザーを管理します。 お気に入りの調査を選択してマークすることもできます。新しいダッシュボードを使用して、調査内および調査間でのアクティビティを追跡および監視します。調査を完了したら、それをクローズまたは削除することができます。</span><span class="sxs-lookup"><span data-stu-id="6dbb6-p102">**Investigations** - You can group searches and incidents by creating an investigation. Manage who can access the investigation by adding or removing members.  You can also select and mark your favorite investigations. Track and monitor activity within and across investigations using new dashboards. After you complete your investigation, you can close or delete it.</span></span>

- <span data-ttu-id="6dbb6-p103">**関心のある**ユーザー–調査に関心のあるユーザーを追加すると、そのユーザーのメールボックス、OneDrive for business アカウント、および Microsoft Teams サイトが表示されます。それらを使用して、調査対象のコンテンツ検索の範囲を作成できます。関心のある人物をさらに調査するには、Office 365 およびその他の Microsoft サービスでのアクティビティに関連する監査レコードを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="6dbb6-p103">**People of interest** – When you add users to investigations as people of interest, you can see their mailbox, OneDrive for Business account, and Microsoft Teams sites. You can use them to scope your investigative content searches. To further investigate a person of interest, you can also view audit records related to their activities in Office 365 and other Microsoft services.</span></span>

- <span data-ttu-id="6dbb6-p104">**検索**–さまざまな検索条件を使用して組織全体の検索を作成します。検索するユーザーまたはサイトがわかっている場合は、それらのユーザーを関心のあるユーザーとして追加したり、検索作成ウィザードでサイトの場所を指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="6dbb6-p104">**Searches** – Create a organization-wide search using various search condition. If you know users or sites that you want to search, you can do so by adding those users as people of interest or specifying site locations in search creation wizard.</span></span> 

- <span data-ttu-id="6dbb6-p105">**インシデント**–新しいインシデントを作成し、確認する検索結果を追加します。個々のドキュメントを確認し、調査メモを残すように注釈を付け、結果をエクスポートして別の環境に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="6dbb6-p105">**Incidents** – Create a new incident and add search results that you want to review. You can review individual documents, annotate to leave investigation notes, and export results to move to a different environment.</span></span> 

- <span data-ttu-id="6dbb6-p106">**レビュー** -ネイティブ、テキスト、およびネイティブのビューを使用して、インシデントに追加されたドキュメントを確認します。分析をドキュメントに適用して、重複、電子メールスレッド、およびテーマによってアイテムをグループ化することもできます。これは、インシデントのレビューを支援するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6dbb6-p106">**Review** – Use a native, text, and near-native view to review the documents added to an incident. You can also apply analytics to documents to group items by duplicates, email threads, and themes, which can help assist your review of the incident.</span></span> 

- <span data-ttu-id="6dbb6-123">**墨消し、タグ、および注釈**: ドキュメントの校閲時に、テキストの墨消し、タグの適用、注釈の作成を行います。</span><span class="sxs-lookup"><span data-stu-id="6dbb6-123">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="6dbb6-124">**ディープインデックス作成**–部分的にインデックスが作成されたアイテムがある場合は、すべてのデータが検索に使用されるように、必要に応じてインデックスが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="6dbb6-124">**Deep indexing** – If there are any partially indexed items, they will be re-indexed on demand so that all data will be available for searching.</span></span>

- <span data-ttu-id="6dbb6-p107">**エラーの修復**–処理エラーを修復またはダウンロードします。これには、大きなファイルの種類、パスワードで保護されたファイル、およびインデックス作成エラーに関連するその他の問題の修復サポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6dbb6-p107">**Error remediation** – Remediate or download processing errors. This includes remediation support for large file types, password protected files, and other issues related to indexing errors.</span></span> 

- <span data-ttu-id="6dbb6-127">**ジョブ**–長時間実行されているプロセスの状態を追跡します。</span><span class="sxs-lookup"><span data-stu-id="6dbb6-127">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="6dbb6-p108">**ハードディスクを削除するメールボックスアイテム**-緊急事態の場合、誤って削除されたアイテムを完全に削除する必要があります。これを行うには、Security & コンプライアンスセンターの PowerShell で**new-compliancesearchaction-PurgeType ハード削除**コマンドを実行して、メールボックスからアイテムを完全に削除することができます。詳細については、「 [new-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dbb6-p108">**Hard-delete mailbox items** - In urgent situations, you might need to permanently delete misplaced items. To do this, you can run the **New-ComplianceSearchAction -Purge -PurgeType HardDelete** command in Security & Compliance Center PowerShell to permanently remove items from mailboxes. For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction).</span></span>
