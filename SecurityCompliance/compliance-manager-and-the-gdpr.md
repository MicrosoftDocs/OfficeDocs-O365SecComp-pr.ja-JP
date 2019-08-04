---
title: Microsoft コンプライアンスマネージャーと GDPR
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンスマネージャーは、Microsoft Service Trust Portal の無料のワークフローベースのリスク評価ツールです。 コンプライアンスマネージャーを使用すると、Microsoft クラウドサービスに関連する規制コンプライアンスアクティビティを追跡、割り当て、検証することができます。
ms.openlocfilehash: af0efa2711215946930c091fc7c38cc1b9f575fd
ms.sourcegitcommit: f0d23e57b00f07cef5b1b2d366eaeeeacda37e3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2019
ms.locfileid: "35786652"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="5d993-104">Microsoft コンプライアンスマネージャーと GDPR</span><span class="sxs-lookup"><span data-stu-id="5d993-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="5d993-105">欧州連合による一般的なデータ保護規則 (GDPR) は、コンプライアンス戦略に影響を与え、コンプライアンスマネージャーで使用されるユーザーおよび顧客情報を管理するための特定のアクションを義務付けることができます。</span><span class="sxs-lookup"><span data-stu-id="5d993-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="5d993-106">ユーザー プライバシーの設定</span><span class="sxs-lookup"><span data-stu-id="5d993-106">User Privacy settings</span></span>

<span data-ttu-id="5d993-107">特定の規制では、組織がユーザー履歴データを削除できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d993-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="5d993-108">コンプライアンスマネージャーは、管理者が次のことを行えるように、**ユーザーのプライバシー設定**機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="5d993-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="5d993-109">ユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="5d993-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="5d993-110">アカウント データ履歴のレポートのエクスポート</span><span class="sxs-lookup"><span data-stu-id="5d993-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="5d993-111">ユーザー データの履歴の削除</span><span class="sxs-lookup"><span data-stu-id="5d993-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="5d993-112">ユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="5d993-112">Search for a user</span></span>

<span data-ttu-id="5d993-113">ユーザー アカウントを検索するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="5d993-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="5d993-114">ユーザーの電子メールエイリアス (@ 記号の左側にある情報) を入力し、右側のドメインサフィックスリストからドメイン名を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d993-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="5d993-115">複数の登録済みドメインを持つ組織の場合は、ドメイン名サフィックスをもう一度確認して、正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5d993-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="5d993-116">ユーザー名が正しく入力されたら、[**検索**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d993-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="5d993-117">ユーザーアカウントが返されない場合は、[ユーザーが見つかりません] がページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d993-117">For user accounts not returned, 'User not found' is displayed on the page.</span></span> <span data-ttu-id="5d993-118">ユーザーの電子メールアドレス情報を確認し、必要に応じて修正してください。</span><span class="sxs-lookup"><span data-stu-id="5d993-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="5d993-119">再試行するには、[**検索**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d993-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="5d993-120">ユーザーアカウントが返されると、ボタンのテキストは [**検索**] から [**クリア**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="5d993-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="5d993-121">これは、返されるユーザーアカウントが追加機能の操作コンテキストであり、これらの関数がこのユーザーアカウントに適用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5d993-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="5d993-122">検索結果をクリアして別のユーザーを検索するには、[**クリア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d993-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="5d993-123">アカウント データ履歴のレポートのエクスポート</span><span class="sxs-lookup"><span data-stu-id="5d993-123">Export a report of account data history</span></span>

<span data-ttu-id="5d993-124">識別されたユーザーアカウントごとに、このアカウントにリンクされている依存関係のレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="5d993-124">For each user account identified, you can generate a report of dependencies linked to this account.</span></span> <span data-ttu-id="5d993-125">この情報を使用すると、開いているアクションアイテムを再割り当てしたり、以前にアップロードした証拠にアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d993-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="5d993-126">レポートを生成してエクスポートするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5d993-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="5d993-127">[**エクスポート**] を選択して、返されたユーザーアカウントに現在割り当てられているコンプライアンスマネージャーコントロールアクションアイテムのレポートと、そのユーザーによってアップロードされたドキュメントのリストを生成し、ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5d993-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="5d993-128">割り当てられたアクションまたはアップロードされたドキュメントがない場合、エラーメッセージに「このユーザーにはデータがありません」というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d993-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="5d993-129">レポートは、アクティブなブラウザーウィンドウのバックグラウンドでダウンロードされます。ブラウザーのダウンロード履歴を確認するダウンロードポップアップが表示されない場合。</span><span class="sxs-lookup"><span data-stu-id="5d993-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="5d993-130">ドキュメントを開いてレポート データを確認します。</span><span class="sxs-lookup"><span data-stu-id="5d993-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d993-131">レポートデータは、アクションアイテム割り当て履歴に対する状態変更を保持および表示する履歴リストではありません。</span><span class="sxs-lookup"><span data-stu-id="5d993-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="5d993-132">生成されたレポートは、レポートが実行されたときに割り当てられたコントロールのアクションアイテムのスナップショットです (レポートに書き込まれる日付とタイムスタンプ)。</span><span class="sxs-lookup"><span data-stu-id="5d993-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="5d993-133">たとえば、同じユーザーに対してレポートが再度生成された場合、アクションアイテムの再割り当てを行うと、別のスナップショットレポートデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="5d993-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="5d993-134">ユーザー データの履歴の削除</span><span class="sxs-lookup"><span data-stu-id="5d993-134">Delete user data history</span></span>

<span data-ttu-id="5d993-135">返されたユーザーに割り当てられているすべてのコントロールのアクションアイテムを "割り当てなし" に設定します。</span><span class="sxs-lookup"><span data-stu-id="5d993-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="5d993-136">返されたユーザーによってアップロードされたすべてのドキュメントの**アップロード**値を "ユーザーの削除済み" に設定します。</span><span class="sxs-lookup"><span data-stu-id="5d993-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="5d993-137">ユーザーアカウントのアクションアイテムとドキュメントのアップロード履歴を削除するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5d993-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="5d993-138">**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d993-138">Select **Delete**.</span></span>

    <span data-ttu-id="5d993-139">確認ダイアログが表示されます。 "これにより、*選択したユーザーのすべてのコントロール操作アイテムの割り当てとドキュメントのアップロード履歴が削除されます。この操作は永続的です。続行しますか?*"</span><span class="sxs-lookup"><span data-stu-id="5d993-139">A confirmation dialog is displayed, "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="5d993-140">続行する場合は [ **OK]** を選択し、それ以外の場合は [**キャンセル**] を選択</span><span class="sxs-lookup"><span data-stu-id="5d993-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
