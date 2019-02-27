---
title: Advanced eDiscovery (プレビュー) ケースで保管担当者を管理する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 95a1bcbbc279ad4e476fc479e701b0f8a921c83b
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295680"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="d4242-102">Advanced eDiscovery (プレビュー) ケースで保管担当者を管理する</span><span class="sxs-lookup"><span data-stu-id="d4242-102">Manage custodians in an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="d4242-p101">[保管担当者] タブには、ケース内のすべての保管担当者の並べ替え可能なリストが含まれています。保管担当者をケースに追加すると、各保管担当者の詳細が Azure Active Directory から自動的に収集されます。</span><span class="sxs-lookup"><span data-stu-id="d4242-p101">The Custodians tab contains a sortable list of all the custodians in the case. After you add custodians to a case, details about each custodian will automatically be collected from Azure Active Directory.</span></span>

## <a name="viewing-custodian-details"></a><span data-ttu-id="d4242-105">保管担当者の詳細の表示</span><span class="sxs-lookup"><span data-stu-id="d4242-105">Viewing custodian details</span></span>

<span data-ttu-id="d4242-p102">保管担当者の詳細を含むフライアウトページは、保管担当者をケースに追加して [**保管担当者**] タブのリストから選択すると表示されます。ここから、その保管担当者に関連するすべての詳細を表示できます。フライアウトページには、次のフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4242-p102">The flyout page that contains custodian details appears after you add a custodian to a case and select them from the list on the **Custodians** tab. From here, you can view all the details related to that custodian. The flyout page contains the following fields:</span></span>

- <span data-ttu-id="d4242-108">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="d4242-108">Contact information</span></span>

  - <span data-ttu-id="d4242-p103">[**表示名**: 保管担当者のアドレス帳に表示される名前。これは通常、保管担当者の名、ミドルネーム、姓の組み合わせになります。</span><span class="sxs-lookup"><span data-stu-id="d4242-p103">**Display Name**: The name displayed in the address book for the custodian. This is usually the combination of the custodian’s first name, middle initial and last name.</span></span>
  - <span data-ttu-id="d4242-111">[**メール/SMTP**]: 保管担当者の SMTP アドレスです。たとえば、jeff@contoso.onmicrosoft.com のようになります。</span><span class="sxs-lookup"><span data-stu-id="d4242-111">**Mail/SMTP**: The SMTP address for the custodian, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="d4242-112">**title**: 保管担当者の役職。</span><span class="sxs-lookup"><span data-stu-id="d4242-112">**Title**: The custodian’s job title.</span></span>
  - <span data-ttu-id="d4242-113">**department**: 保管担当者が機能する部署の名前。</span><span class="sxs-lookup"><span data-stu-id="d4242-113">**Department**: The name for the department in which the custodian works.</span></span>
  - <span data-ttu-id="d4242-p104">**マネージャー**: 保管担当者の上司。指定した上司は、この保管担当者のエスカレーション情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d4242-p104">**Manager**: The custodian’s manager. The designated manager will receive any Escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="d4242-116">場所情報</span><span class="sxs-lookup"><span data-stu-id="d4242-116">Location information</span></span>

  - <span data-ttu-id="d4242-117">**city**: 保管担当者が配置されている市区町村。</span><span class="sxs-lookup"><span data-stu-id="d4242-117">**City**: The city in which the custodian is located.</span></span>
  - <span data-ttu-id="d4242-118">**state**: 保管担当者の住所の都道府県。</span><span class="sxs-lookup"><span data-stu-id="d4242-118">**State**: The state or province in the custodian’s address.</span></span>
  - <span data-ttu-id="d4242-119">**国/地域**: 保管担当者が配置されている国/地域。たとえば、"US" や "UK" などです。</span><span class="sxs-lookup"><span data-stu-id="d4242-119">**Country/Region**: The country/region in which the custodian’s is located; for example, “US” or “UK”.</span></span>
  - <span data-ttu-id="d4242-120">**office**: 保管担当者の事業所にあるオフィスの場所。</span><span class="sxs-lookup"><span data-stu-id="d4242-120">**Office**: The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="d4242-121">ケース情報</span><span class="sxs-lookup"><span data-stu-id="d4242-121">Case information</span></span>

  - <span data-ttu-id="d4242-122">**ホールド状態**: 保管担当者が保留中であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d4242-122">**Hold status**: Indicates if the custodian has been placed on hold.</span></span> 
  - <span data-ttu-id="d4242-p105">**通信の状態**: 保管担当者に保留通知が発行されているかどうかを示します。保管担当者に通知が発行されている場合、これは*公開済み*としてマークされます。保管担当者に通知が発行されていない場合、この状態は\*\* 未発行になります。</span><span class="sxs-lookup"><span data-stu-id="d4242-p105">**Communication status**: Indicates if the custodian has been issued a hold notice. If the custodian has been issued a notice, then this will be marked as *Published*. If the custodian has not been issued a notice, then this status will be *Un-Published*.</span></span> 
  - <span data-ttu-id="d4242-p106">**状態**: ケース内での保管担当者の状態。保管担当者がケースに対して保留中の場合、これは*アクティブ*になります。保管担当者がケースから削除されると、その状態は「*リリース*済み」に変わります。</span><span class="sxs-lookup"><span data-stu-id="d4242-p106">**Status**: The status of the custodian within the case. This will be *Active* if the custodian is still on hold for the case. If a custodian is removed from a case, their status will change to *Released*.</span></span> 

- <span data-ttu-id="d4242-129">処理状態</span><span class="sxs-lookup"><span data-stu-id="d4242-129">Processing status</span></span>

  - <span data-ttu-id="d4242-130">**インデックス作成の状態**: deep indexing ジョブの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="d4242-130">**Indexing status**: Indicates the status of the deep indexing job.</span></span>  
  - <span data-ttu-id="d4242-131">**インデックス作成の最終更新日時**: ディープインデックス作成ジョブが最後にトリガーされたときの datestamp を示します。</span><span class="sxs-lookup"><span data-stu-id="d4242-131">**Indexing Last Updated Time**: Indicates the datestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="d4242-132">**データソース**: 保管担当者に対して選択されたメールボックス、サイト、およびチームの数を示します。</span><span class="sxs-lookup"><span data-stu-id="d4242-132">**Data sources**: Shows the count of mailboxes, sites, and Teams that have been selected for the custodian.</span></span>

## <a name="updating-a-custodian"></a><span data-ttu-id="d4242-133">保管担当者の更新</span><span class="sxs-lookup"><span data-stu-id="d4242-133">Updating a custodian</span></span>

<span data-ttu-id="d4242-p107">ケースの進行に応じて、特定の保管担当者 & に関連する追加のデータソースが存在する場合があります。その他のシナリオでは、確認され、関連性がないと見なされた特定のデータソースを削除することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d4242-p107">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case. In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="d4242-136">保管担当者および選択したデータソースを更新するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d4242-136">To update a custodian and the selected data sources:</span></span>

1. <span data-ttu-id="d4242-137">**電子情報開示 > Advanced ediscovery (プレビュー)** から既存のケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4242-137">Select an existing case from the **eDiscovery > Advanced eDiscovery (Preview)**.</span></span>
  
2. <span data-ttu-id="d4242-138">その場合は、[**保管担当者**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4242-138">In the case, click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="d4242-139">リストから保管担当者を選択し、[**ソースの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4242-139">Select the custodian(s) from the list and click **Edit sources**.</span></span>
  
4. <span data-ttu-id="d4242-140">**[データソースの選択]** をクリックして、Exchange および OneDrive の場所の選択を更新します。</span><span class="sxs-lookup"><span data-stu-id="d4242-140">Update selections for Exchange and OneDrive locations by clicking **Choose data sources**.</span></span>
  
5. <span data-ttu-id="d4242-p108">ユーザーに割り当てられている Teams、SharePoint、または Exchange のメールボックスを追加または削除するには、[**追加のデータソース]** をクリックして選択します。データソースを保管担当者にマップする方法の詳細については、「 [Add 保管担当者 to a case](add-custodians-to-case.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4242-p108">Add or remove Teams, SharePoint, or Exchange mailboxes mapped the user by clicking to **Select additional data sources**. For more information about how you to map data sources to a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span>
  
6. <span data-ttu-id="d4242-143">保管担当者 hold の状態を更新するには、[ **custodial**hold を配置する] をクリックし、保管担当者のホールドを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="d4242-143">To update the custodian hold status, click **Place custodial holds**, and enable or disable the hold for custodians.</span></span>

> [!TIP]
> <span data-ttu-id="d4242-144">複数の保管担当者を選択して、保管担当者の再インデックス、リリース、編集などの一括操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d4242-144">You can select multiple custodians to perform bulk actions, like re-indexing, releasing, or editing a set of custodians.</span></span>

## <a name="resolving-custodian-processing-errors"></a><span data-ttu-id="d4242-145">保管担当者処理エラーを解決する</span><span class="sxs-lookup"><span data-stu-id="d4242-145">Resolving custodian processing errors</span></span>

<span data-ttu-id="d4242-p109">ほとんどの法律ワークフローでは、特定の調査のために保管担当者を追加した後、ユーザーのデータのサブセットが検索されます。大きなファイルサイズまたは破損の可能性があるため、保管担当者のデータソース内の一部の項目は、部分的にインデックス処理される場合があります。Advanced eDiscovery (プレビュー) ディープインデックス作成機能を使用すると、これらのアイテムを再クロールし、必要に応じてインデックスを再作成することで、これらの部分的なインデックスが作成されたアイテムを自動的に修復できます。</span><span class="sxs-lookup"><span data-stu-id="d4242-p109">In most Legal workflows, after custodians are added for a specific investigation, a subset of the users’ data will be searched. Due to large file sizes or possible corruption, some items within the custodians’ data sources may be partially indexed. Using the Advanced eDiscovery (Preview) deep indexing capability, these partially indexed items can be automatically remediated by re-crawling and re-indexing these items on demand.</span></span> 

<span data-ttu-id="d4242-p110">保管担当者がケースに追加されると、そのデータは自動的に "ディープインデックス" になり、ユーザーは Office 365 の外部で検索をダウンロード、修復、および再実行する必要がなく、これらの部分的なインデックスが作成されたアイテムをそのまま残しておくことができます。ケースのライフサイクル中に、ユーザーは特定の保管担当者のアイテムを修復したり、新しいデータソースを追加したりすることができます。これには、保管担当者インデックスを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4242-p110">When a custodian is added to a case, their data will automatically be "deep indexed”, allowing users to leave these partially indexed items in place instead of having to download, remediate and re-run searches outside of Office 365. During the lifecycle of a case, a user may remediate items or add new data sources for a given custodian. This may require the Custodian Index to be updated.</span></span> 

<span data-ttu-id="d4242-152">部分的なインデックスが作成されたアイテムを処理するために、再インデックス処理をトリガーするには</span><span class="sxs-lookup"><span data-stu-id="d4242-152">To trigger a re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="d4242-153">**電子情報開示 > Advanced ediscovery (プレビュー)** に移動し、既存のケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4242-153">Go to **eDiscovery > Advanced eDiscovery (Preview)** and select an existing case.</span></span>

2. <span data-ttu-id="d4242-154">ケースでは、[**保管担当者] タブ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4242-154">In the case, click to **Custodians tab**.</span></span> 

3. <span data-ttu-id="d4242-155">再インデックス化する必要がある保管担当者を選択し、フライアウトページの [**インデックスの更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4242-155">Select the custodian(s) that needs to be re-indexed, and then click **Update index** on the flyout page.</span></span>

4. <span data-ttu-id="d4242-156">保管担当者インデックスの状態を確認するために、[**保管担当者**] タブの [**インデックス作成ジョブの状態**] 列のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4242-156">Check the status of the custodian index by clicking the link in the **Indexing job Status** column on the **Custodians** tab.</span></span>  

5. <span data-ttu-id="d4242-157">再インデックス処理の状態は、[**ジョブ**] タブで追跡することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4242-157">The status for the re-indexing process can also be tracked on the **Jobs** tab.</span></span>

<span data-ttu-id="d4242-158">インデックスが作成されたアイテムのインデックスの再作成と修復の詳細については、「[処理エラーを修正](processing-data-for-case.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4242-158">For more information about re-indexing and remediating partially indexed items, see [Fix processing errors](processing-data-for-case.md).</span></span>

## <a name="releasing-a-custodian-from-a-case"></a><span data-ttu-id="d4242-159">ケースからの保管担当者の解放</span><span class="sxs-lookup"><span data-stu-id="d4242-159">Releasing a custodian from a case</span></span>

<span data-ttu-id="d4242-160">保管担当者は、ケースがクローズされた場合や、ケースのコンテンツを保持する義務が保管担当者ではなくなった場合、または保管担当者が特定のケースに関連していないと判断された場合にリリースされます。</span><span class="sxs-lookup"><span data-stu-id="d4242-160">A custodian is released in situations where a case is closed, a custodian is no longer under obligation to preserve content for a case, or when a custodian is deemed to no longer be relevant to a particular case.</span></span> 

<span data-ttu-id="d4242-p111">保留通知が公開された後に保管担当者をリリースした場合は、リリース通知が保管担当者に送信されます。さらに、リリースされた保管担当者に属性付きのすべての custodial 保持も削除されます。</span><span class="sxs-lookup"><span data-stu-id="d4242-p111">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian. In addition, any custodial holds attributed to the released custodians will also be removed.</span></span>

<span data-ttu-id="d4242-163">保管担当者が、法的情報保留通知が発行されていないサイレントホールドに設定されている場合は、リリースされた保管担当者に分類されたすべての custodial 保持が削除されます。</span><span class="sxs-lookup"><span data-stu-id="d4242-163">If the custodian was placed on a silent hold, where they were not issued any legal hold notifications, then any custodial holds attributed to the released custodians will be removed.</span></span>  

<span data-ttu-id="d4242-164">保管担当者をリリースするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d4242-164">To release a custodian:</span></span> 

1.  <span data-ttu-id="d4242-165">[**保管担当者**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="d4242-165">Go to the **Custodians** tab.</span></span>

2.  <span data-ttu-id="d4242-166">リストから保管担当者を選択し、フライアウトページの [ **Release 保管担当者**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4242-166">Select the custodian from the list and click **Release custodians** on the flyout page.</span></span>

    <span data-ttu-id="d4242-167">**保管担当者**タブの保管担当者の状態は [**解放**済み] に設定されており、フライアウトページの**保持状態**が**非アクティブ**に変更されます。</span><span class="sxs-lookup"><span data-stu-id="d4242-167">The status of the custodian on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **Inactive**.</span></span> 

> [!TIP]
> <span data-ttu-id="d4242-p112">保管担当者は、いくつかの法的情報保持事項に同時に関与する場合があります。保管担当者がケースからリリースされた場合、他の事項における保留と通知は影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="d4242-p112">A custodian might be simultaneously be involved in several legal hold matters. When a custodian is released from a case, the holds and notifications across other matters will not be impacted.</span></span>

## <a name="related-information"></a><span data-ttu-id="d4242-170">関連情報</span><span class="sxs-lookup"><span data-stu-id="d4242-170">Related information</span></span>

 - [<span data-ttu-id="d4242-171">データ処理中のエラー修復</span><span class="sxs-lookup"><span data-stu-id="d4242-171">Error remediation when processing data</span></span>](error-remediation.md) 
- [<span data-ttu-id="d4242-172">通信の操作</span><span class="sxs-lookup"><span data-stu-id="d4242-172">Work with communications</span></span>](managing-custodian-communications.md)
