---
title: 上級電子情報開示のリリースノート
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
description: この記事には、上級電子情報開示のリリースノートが記載されています。
ms.openlocfilehash: f3d26b1c84746581ccf32e1d4aada079fc21dfb3
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154889"
---
# <a name="release-notes-for-advanced-ediscovery"></a><span data-ttu-id="883d2-103">上級電子情報開示のリリースノート</span><span class="sxs-lookup"><span data-stu-id="883d2-103">Release notes for Advanced eDiscovery</span></span>

<span data-ttu-id="883d2-104">上級電子情報開示用のパブリックプレビュープログラムは、予定されている機能および更新プログラムへの早期アクセスを得るための方法です。</span><span class="sxs-lookup"><span data-stu-id="883d2-104">The Public Preview program for Advanced eDiscovery is the way to get early access to the upcoming functionality and updates.</span></span> <span data-ttu-id="883d2-105">最新の機能にいち早くアクセスするには、Security & コンプライアンスセンターで高度な電子情報開示ケースを作成して使用するだけです。</span><span class="sxs-lookup"><span data-stu-id="883d2-105">To get early access to the newest features, just create and use an Advanced eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="883d2-106">「[新しいケースを作成する」を](create-new-ediscovery-case.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="883d2-106">See [Create a new case](create-new-ediscovery-case.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="883d2-107">既知の問題</span><span class="sxs-lookup"><span data-stu-id="883d2-107">Known issues</span></span>

<span data-ttu-id="883d2-108">**Microsoft Forms**</span><span class="sxs-lookup"><span data-stu-id="883d2-108">**Microsoft Forms**</span></span>

- <span data-ttu-id="883d2-109">上級電子情報開示の検索ツールを使用して保管担当者メールボックスを検索する場合、2019年1月31日より前に作成されたフォームに対応するデータは検索できません。</span><span class="sxs-lookup"><span data-stu-id="883d2-109">The data corresponding to a form created before January 31, 2019 will not be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span> <span data-ttu-id="883d2-110">この日付以降に作成されたフォームは、検索に使用できます。</span><span class="sxs-lookup"><span data-stu-id="883d2-110">Forms created after this date will be available to search.</span></span>

- <span data-ttu-id="883d2-111">ユーザーが作成したフォームは、フォームを作成したユーザーが削除された後でも、応答を受信できます。</span><span class="sxs-lookup"><span data-stu-id="883d2-111">A form created by a user can still receive responses even after the user who created the Form is deleted.</span></span> <span data-ttu-id="883d2-112">ただし、Advanced 電子情報開示の検索ツールを使用して保管担当者メールボックスを検索する場合、これらの応答に対応するデータは検索できません (保管担当者メールボックスが削除された後に発生します)。</span><span class="sxs-lookup"><span data-stu-id="883d2-112">However, the corresponding data for those responses (that occurred after the custodian mailbox was deleted) will not be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span>
 
<span data-ttu-id="883d2-113">**Microsoft Sway**</span><span class="sxs-lookup"><span data-stu-id="883d2-113">**Microsoft Sway**</span></span>

- <span data-ttu-id="883d2-114">ユーザーが sway の所有者のユーザーアカウントを削除する直前に sway を編集した場合、上級電子情報開示の検索ツールを使用して保管担当者メールボックスを検索するときに、これらの変更は検索できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="883d2-114">If a user edits a sway just prior to the deletion of the user account for the owner of that sway, then those changes may not be be searchable when using the Search tool in Advanced eDiscovery to search custodian mailboxes.</span></span> <span data-ttu-id="883d2-115">アカウントが削除されたことを示す通知を受信すると、sway は sway への変更を直ちにブロックします。</span><span class="sxs-lookup"><span data-stu-id="883d2-115">Sway blocks changes to to a sway as soon as it receives a signal that the account was deleted.</span></span> <span data-ttu-id="883d2-116">ただし、このシグナルを受信する前に sway を編集できる可能性が小さい。</span><span class="sxs-lookup"><span data-stu-id="883d2-116">However, there's a small chance that a sway can be edited before this signal is received.</span></span>

## <a name="issues-fixed-in-this-release"></a><span data-ttu-id="883d2-117">このリリースで修正される問題</span><span class="sxs-lookup"><span data-stu-id="883d2-117">Issues fixed in this release</span></span>

- <span data-ttu-id="883d2-118">DCR: インデックスのないアイテムおよび孤立したアイテムの例外処理</span><span class="sxs-lookup"><span data-stu-id="883d2-118">DCR: Exception handling for unindexed items and orphaned items</span></span>
- <span data-ttu-id="883d2-119">DCR: 保留通知</span><span class="sxs-lookup"><span data-stu-id="883d2-119">DCR: Hold notifications</span></span>
- <span data-ttu-id="883d2-120">DCR: 電子情報開示の保管担当者</span><span class="sxs-lookup"><span data-stu-id="883d2-120">DCR: Custodians in eDiscovery</span></span>

## <a name="whats-new"></a><span data-ttu-id="883d2-121">新機能</span><span class="sxs-lookup"><span data-stu-id="883d2-121">What’s new</span></span>

- <span data-ttu-id="883d2-122">**セキュリティ _AMP_ コンプライアンスセンターで**の再設計されたナビゲーション: Advanced eDiscovery は新しいルックアンドフィールを備えています。</span><span class="sxs-lookup"><span data-stu-id="883d2-122">**Redesigned navigation in the Security & Compliance Center** – Advanced eDiscovery has a new look and feel.</span></span> <span data-ttu-id="883d2-123">高度な電子情報開示を使用して、ケースワークフローを管理します。</span><span class="sxs-lookup"><span data-stu-id="883d2-123">Use Advanced eDiscovery to manage more of your case workflow.</span></span>

- <span data-ttu-id="883d2-124">**ケース管理**–新しいケースの種類のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="883d2-124">**Case management** – There’s additional support for new case types.</span></span> <span data-ttu-id="883d2-125">また、最近とよく使用するケースを選択して保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="883d2-125">You can also select and save your recent and favorite cases.</span></span> <span data-ttu-id="883d2-126">新しいダッシュボードを使用して、ケース内およびケース間でのアクティビティを追跡および監視します。</span><span class="sxs-lookup"><span data-stu-id="883d2-126">Track and monitor activity within and across cases using new dashboards.</span></span>

- <span data-ttu-id="883d2-127">**保管担当者 management** –ケース内のデータ保管担当者としてユーザーを追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="883d2-127">**Custodian management** – Add and remove users as data custodians within a case.</span></span>

- <span data-ttu-id="883d2-128">**Exchange、onedrive、Teams の統合**–ユーザーの現在のメールボックス、Onedrive for business アカウント、および Microsoft Teams サイトをケースに自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="883d2-128">**Exchange, OneDrive, and Teams Integration** – Automatically add a user’s current mailbox, OneDrive for Business account, and Microsoft Teams sites to a case.</span></span> 

- <span data-ttu-id="883d2-129">**保管担当者 communications** –組織の代わりに法的情報保留通知を送信および管理します。</span><span class="sxs-lookup"><span data-stu-id="883d2-129">**Custodian communications** – Send and manage legal hold notifications on behalf of your organization.</span></span>

- <span data-ttu-id="883d2-130">**保管担当者ポータル**–アクティブな保留通知にアクセスするための保管担当者の新しいポータル。</span><span class="sxs-lookup"><span data-stu-id="883d2-130">**Custodian portal** – New portal for custodians to access their active hold notices.</span></span>

- <span data-ttu-id="883d2-131">**ディープインデックス作成**–必要に応じて、部分的にインデックスが作成されたアイテムを再クロールします。</span><span class="sxs-lookup"><span data-stu-id="883d2-131">**Deep indexing** – Re-crawl partially indexed items on demand.</span></span>

- <span data-ttu-id="883d2-132">**エラーの修復**–処理エラーを修復またはダウンロードします。これには、大規模なファイルの種類、パスワードで保護されたファイルなどの修復のサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="883d2-132">**Error remediation** – Remediate or download processing errors; this include remediation support for large file types, password protected files, and more.</span></span> 

- <span data-ttu-id="883d2-133">**検索の強化**: 保管担当者と場所を識別することによって検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="883d2-133">**Improvements to search** – Create a search by identifying custodians and/or locations.</span></span>

- <span data-ttu-id="883d2-134">**レビューセット**-ドキュメントの静的なセットを管理、追跡、および監査します。</span><span class="sxs-lookup"><span data-stu-id="883d2-134">**Review sets** – Manage, track, and audit static sets of documents.</span></span>

- <span data-ttu-id="883d2-135">**レビュー** –ネイティブ、テキスト、およびネイティブのネイティブビューを使用して、校閲セットに追加されたドキュメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="883d2-135">**Review** – Use a native, text, and near-native view to review documents added to your review set.</span></span>

- <span data-ttu-id="883d2-136">**墨消し、タグ、および注釈**: ドキュメントの校閲時に、テキストの墨消し、タグの適用、注釈の作成を行います。</span><span class="sxs-lookup"><span data-stu-id="883d2-136">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="883d2-137">**Analytics によるレビュー**: 高度な電子情報開示分析を活用して、レビューセット内の結果を検索、検索、および選別します。</span><span class="sxs-lookup"><span data-stu-id="883d2-137">**Analytics-powered review**– Leverage Advanced eDiscovery analytics to find, search, and cull results within a review set.</span></span>

- <span data-ttu-id="883d2-138">**ジョブ**–長時間実行されているプロセスの状態を追跡します。</span><span class="sxs-lookup"><span data-stu-id="883d2-138">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="883d2-139">**新しい監査アクティビティ**: 高度な電子情報開示のための新しい監査アクティビティを追跡および表示します。</span><span class="sxs-lookup"><span data-stu-id="883d2-139">**New audit activities** – Track and view new audit activity for Advanced eDiscovery.</span></span>
