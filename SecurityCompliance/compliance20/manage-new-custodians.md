---
title: 高度な電子的証拠開示 (プレビュー) 場合は、通告を管理します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 742f6bc35b67071fba528e6a0ce543ecc6915762
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608059"
---
# <a name="managing-custodians-in-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="d4e7e-102">高度な電子的証拠開示 (プレビュー) 場合は、通告を管理します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-102">Managing custodians in an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="d4e7e-p101">通告] タブには、大文字と小文字のすべての通告の並べ替え可能な一覧が含まれています。通告をケースに追加すると後の詳細については、各管理者は Azure Active Directory から自動的に収集されます。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-p101">The Custodians tab contains a sortable list of all the custodians in the case. After you add custodians to a case, details about each custodian will automatically be collected from Azure Active Directory.</span></span>

## <a name="viewing-custodian-details"></a><span data-ttu-id="d4e7e-105">管理者の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-105">Viewing custodian details</span></span>

<span data-ttu-id="d4e7e-p102">**通告**タブの一覧から選択して場合に、管理者を追加する管理者の詳細を含むフライアウトのページが表示されます。ここでは、その管理者に関連するすべての詳細を表示できます。フライアウトのページには、次のフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-p102">The flyout page that contains custodian details appears after you add a custodian to a case and select them from the list on the **Custodians** tab. From here, you can view all the details related to that custodian. The flyout page contains the following fields:</span></span>

- <span data-ttu-id="d4e7e-108">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="d4e7e-108">Contact information</span></span>

  - <span data-ttu-id="d4e7e-p103">**表示名**: 名前、管理者のアドレス帳に表示されます。これは、通常、保管担当者の姓、ミドル ネームの頭文字とラスト ネームの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-p103">**Display Name**: The name displayed in the address book for the custodian. This is usually the combination of the custodian’s first name, middle initial and last name.</span></span>
  - <span data-ttu-id="d4e7e-111">**メールと SMTP**: 保管担当者、jeff@contoso.onmicrosoft.com などの SMTP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-111">**Mail/SMTP**: The SMTP address for the custodian, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="d4e7e-112">**タイトル**: 保管担当者の役職名です。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-112">**Title**: The custodian’s job title.</span></span>
  - <span data-ttu-id="d4e7e-113">**部門**: 書が使用される部門の名前です。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-113">**Department**: The name for the department in which the custodian works.</span></span>
  - <span data-ttu-id="d4e7e-p104">**マネージャー**: 管理者のマネージャーです。この保管担当者にエスカレーションした通信は、指定したマネージャーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-p104">**Manager**: The custodian’s manager. The designated manager will receive any Escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="d4e7e-116">場所情報</span><span class="sxs-lookup"><span data-stu-id="d4e7e-116">Location information</span></span>

  - <span data-ttu-id="d4e7e-117">**都市**: 書が含まれている都市です。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-117">**City**: The city in which the custodian is located.</span></span>
  - <span data-ttu-id="d4e7e-118">**状態**: 保管担当者の住所の都道府県です。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-118">**State**: The state or province in the custodian’s address.</span></span>
  - <span data-ttu-id="d4e7e-119">**国/地域**: 国/地域の保管担当者のされています。たとえば、「米国」または「大阪府」です。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-119">**Country/Region**: The country/region in which the custodian’s is located; for example, “US” or “UK”.</span></span>
  - <span data-ttu-id="d4e7e-120">**Office**: ビジネス書の場所にオフィスの場所。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-120">**Office**: The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="d4e7e-121">ケース情報</span><span class="sxs-lookup"><span data-stu-id="d4e7e-121">Case information</span></span>

  - <span data-ttu-id="d4e7e-122">**保留状態**: 保留中の書が配置されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-122">**Hold status**: Indicates if the custodian has been placed on hold.</span></span> 
  - <span data-ttu-id="d4e7e-p105">**通信状態**: 保留中の通知書が発行されているかどうかを示します。通知書が発行されている場合、このとしてマークされます*公開*します。書に、通知が発行されていないかどうかは、この状態になります*が発行されていません*。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-p105">**Communication status**: Indicates if the custodian has been issued a hold notice. If the custodian has been issued a notice, then this will be marked as *Published*. If the custodian has not been issued a notice, then this status will be *Un-Published*.</span></span> 
  - <span data-ttu-id="d4e7e-p106">**状態**: ケース内での保管担当者の状態。書が保留中の場合でもある場合は*アクティブ*になります。サポート案件から、管理者が削除されると、*リリース済み*のステータスが変更されます。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-p106">**Status**: The status of the custodian within the case. This will be *Active* if the custodian is still on hold for the case. If a custodian is removed from a case, their status will change to *Released*.</span></span> 

- <span data-ttu-id="d4e7e-129">処理ステータス</span><span class="sxs-lookup"><span data-stu-id="d4e7e-129">Processing status</span></span>

  - <span data-ttu-id="d4e7e-130">**インデックスの作成状況**: 高度なインデックス作成ジョブのステータスを示します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-130">**Indexing status**: Indicates the status of the deep indexing job.</span></span>  
  - <span data-ttu-id="d4e7e-131">**最終更新時刻のインデックスの作成**: 高度なインデックス作成ジョブが最後に呼び出されたときの日付スタンプを示します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-131">**Indexing Last Updated Time**: Indicates the datestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="d4e7e-132">**データ ソース**: メールボックス、サイト、および書の選択されているチームの数を示しています。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-132">**Data sources**: Shows the count of mailboxes, sites, and Teams that have been selected for the custodian.</span></span>

## <a name="updating-a-custodian"></a><span data-ttu-id="d4e7e-133">保管担当者を更新</span><span class="sxs-lookup"><span data-stu-id="d4e7e-133">Updating a custodian</span></span>

<span data-ttu-id="d4e7e-p107">ケースの進行に伴って、あることを他のデータ ソースの特定の管理者の & に関連する、大文字と小文字を検出する可能性があります。他のシナリオでは、レビューおよび関係のないと見なされる場合がある特定のデータ ソースを削除する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-p107">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case. In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="d4e7e-136">管理者と、選択したデータ ソースを更新します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-136">To update a custodian and the selected data sources:</span></span>

1. <span data-ttu-id="d4e7e-137">**電子的証拠開示 _gt 高度な電子情報開示 (プレビュー)** には、既存のケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-137">Select an existing case from the **eDiscovery > Advanced eDiscovery (Preview)**.</span></span>
  
2. <span data-ttu-id="d4e7e-138">場合、**通告**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-138">In the case, click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="d4e7e-139">一覧から、custodian(s) を選択し、**ソースの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-139">Select the custodian(s) from the list and click **Edit sources**.</span></span>
  
4. <span data-ttu-id="d4e7e-140">**データ ソースの選択**] をクリックして、Exchange と OneDrive の場所の選択を更新します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-140">Update selections for Exchange and OneDrive locations by clicking **Choose data sources**.</span></span>
  
5. <span data-ttu-id="d4e7e-p108">追加または削除、チーム、SharePoint、または Exchange メールボックスは、**他のデータ ソースを選択**する] をクリックしてユーザーをマップします。保管担当者にソース データをマップする方法の詳細についてを参照してください[、高度な電子的証拠開示 (プレビュー) に通告を追加する場合](add-custodians-to-case.md)。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-p108">Add or remove Teams, SharePoint, or Exchange mailboxes mapped the user by clicking to **Select additional data sources**. For more information about how you to map data sources to a custodian, see [Add custodians to an Advanced eDiscovery (Preview) Case](add-custodians-to-case.md).</span></span>
  
6. <span data-ttu-id="d4e7e-143">管理者の保留中の状態を更新するに**信託の場所を保持する**が、をクリックしを有効または通告の保持を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-143">To update the custodian hold status, click **Place custodial holds**, and enable or disable the hold for custodians.</span></span>

> [!TIP]
> <span data-ttu-id="d4e7e-144">通告のセットを編集するインデックスの再作成、解放、またはのように、一括操作を実行する複数の通告を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-144">You can select multiple custodians to perform bulk actions, like re-indexing, releasing, or editing a set of custodians.</span></span>

## <a name="resolving-custodian-processing-errors"></a><span data-ttu-id="d4e7e-145">保管担当者の処理エラーの解決</span><span class="sxs-lookup"><span data-stu-id="d4e7e-145">Resolving custodian processing errors</span></span>

<span data-ttu-id="d4e7e-p109">ほとんどの有効なワークフローで通告を特定の調査を追加した後、ユーザーのデータのサブセットが検索されます。サイズの大きなファイルや破損している可能性、通告のデータ ソース内のいくつかの項目が部分的にインデックスを作成します。高度なインデックス作成の高度な電子的証拠開示 (プレビュー) 機能を使用すると、部分的にインデックス付けされたアイテムが自動的に改善する再クロールし、必要に応じてこれらの項目のインデックスを再作成します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-p109">In most Legal workflows, after custodians are added for a specific investigation, a subset of the users’ data will be searched. Due to large file sizes or possible corruption, some items within the custodians’ data sources may be partially indexed. Using the Advanced eDiscovery (Preview) deep indexing capability, these partially indexed items can be automatically remediated by re-crawling and re-indexing these items on demand.</span></span> 

<span data-ttu-id="d4e7e-p110">場合に、管理者を追加するのデータは自動的に「深いインデックス」と、アイテムをダウンロード、修正、および Office 365 以外での検索を再実行することではなく部分的にこれらのままにするユーザーを許可するインデックスが作成されます。サポート案件のライフ サイクルは、ユーザーが項目を修正するか、指定された管理者の新しいデータ ソースを追加します。保管担当者のインデックスを更新するこの必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-p110">When a custodian is added to a case, their data will automatically be "deep indexed”, allowing users to leave these partially indexed items in place instead of having to download, remediate and re-run searches outside of Office 365. During the lifecycle of a case, a user may remediate items or add new data sources for a given custodian. This may require the Custodian Index to be updated.</span></span> 

<span data-ttu-id="d4e7e-152">部分的にアドレスの再インデックス作成のプロセスをトリガーするには、インデックスの項目を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-152">To trigger a re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="d4e7e-153">**電子的証拠開示 _gt 高度な電子情報開示 (プレビュー)** に移動し、既存のケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-153">Go to **eDiscovery > Advanced eDiscovery (Preview)** and select an existing case.</span></span>

2. <span data-ttu-id="d4e7e-154">場合、**通告**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-154">In the case, click to **Custodians tab**.</span></span> 

3. <span data-ttu-id="d4e7e-155">再インデックス付けする必要がある custodian(s) を選択し、ポップアップ ページの**索引の更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-155">Select the custodian(s) that needs to be re-indexed, and then click **Update index** on the flyout page.</span></span>

4. <span data-ttu-id="d4e7e-156">**通告**] タブで [**インデックス作成ジョブの状態**] 列にあるリンクをクリックすると、管理者のインデックスのステータスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-156">Check the status of the custodian index by clicking the link in the **Indexing job Status** column on the **Custodians** tab.</span></span>  

5. <span data-ttu-id="d4e7e-157">**ジョブ**] タブの再インデックス処理のステータスを追跡することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-157">The status for the re-indexing process can also be tracked on the **Jobs** tab.</span></span>

<span data-ttu-id="d4e7e-158">部分的にインデックス付きのアイテムを再インデックス作成と修正の詳細については、[高度な電子的証拠開示 (プレビュー) で発生したエラーの処理の修正](processing-data-for-case.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-158">For more information about re-indexing and remediating partially indexed items, see [Fixing processing errors in Advanced eDiscovery (Preview)](processing-data-for-case.md).</span></span>

## <a name="releasing-a-custodian-from-a-case"></a><span data-ttu-id="d4e7e-159">サポート案件からの保管担当者を解放します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-159">Releasing a custodian from a case</span></span>

<span data-ttu-id="d4e7e-160">状況で、管理者がリリースされた場合は、ケースを終了、管理者の場合は、コンテンツを保持する義務がない、または特定に関連している、保管担当者と判断した場合になった。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-160">A custodian is released in situations where a case is closed, a custodian is no longer under obligation to preserve content for a case, or when a custodian is deemed to no longer be relevant to a particular case.</span></span> 

<span data-ttu-id="d4e7e-p111">保留中の通知が発行された後に、管理者をリリースする場合のリリースの通知書に送信されます。さらに、リリースされた通告に属する信託、保留リストも削除されます。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-p111">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian. In addition, any custodial holds attributed to the released custodians will also be removed.</span></span>

<span data-ttu-id="d4e7e-163">書が追加された場合、サイレントの保留リストにない発行したすべての法的保持義務通告、リリースされた通告に属する信託、保留リストが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-163">If the custodian was placed on a silent hold, where they were not issued any legal hold notifications, then any custodial holds attributed to the released custodians will be removed.</span></span>  

<span data-ttu-id="d4e7e-164">管理者を解放します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-164">To release a custodian:</span></span> 

1.  <span data-ttu-id="d4e7e-165">**通告**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-165">Go to the **Custodians** tab.</span></span>

2.  <span data-ttu-id="d4e7e-166">書を一覧から選択、ポップアップ ページの**リリースの通告**をクリックします.</span><span class="sxs-lookup"><span data-stu-id="d4e7e-166">Select the custodian from the list and click **Release custodians** on the flyout page.</span></span>

    <span data-ttu-id="d4e7e-167">**通告**] タブの [管理者の状態は、**リリース済み**に設定されてし、**保留状態**のフライアウトのページが**非アクティブ**に変更されました。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-167">The status of the custodian on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **Inactive**.</span></span> 

> [!TIP]
> <span data-ttu-id="d4e7e-p112">保管担当者、同時にあります法的保存要件のいくつかの問題に関係します。サポート案件から、管理者が解放されると、保留リストおよびその他の事柄の間での通知は影響されません。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-p112">A custodian might be simultaneously be involved in several legal hold matters. When a custodian is released from a case, the holds and notifications across other matters will not be impacted.</span></span>

## <a name="related-information"></a><span data-ttu-id="d4e7e-170">関連情報</span><span class="sxs-lookup"><span data-stu-id="d4e7e-170">Related information</span></span>

 - <span data-ttu-id="d4e7e-171">Active Directory のユーザー属性</span><span class="sxs-lookup"><span data-stu-id="d4e7e-171">User Attributes in Active Directory</span></span> 
 - [<span data-ttu-id="d4e7e-172">データの処理中にエラーの修復</span><span class="sxs-lookup"><span data-stu-id="d4e7e-172">Error remediation when processing data</span></span>](error-remediation.md) 
 - [<span data-ttu-id="d4e7e-173">通信を使用します。</span><span class="sxs-lookup"><span data-stu-id="d4e7e-173">Working with communications</span></span>](managing-custodian-communications.md)
