---
title: 高度な電子情報開示 (プレビュー) ケースへの保管担当者の追加
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
ms.openlocfilehash: 730e1fe40756bcb38f3b071137828072f4e2dcb5
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296720"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="27faf-102">高度な電子情報開示 (プレビュー) ケースへの保管担当者の追加</span><span class="sxs-lookup"><span data-stu-id="27faf-102">Add custodians to an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="27faf-p101">Advanced eDiscovery (プレビュー) を使用すると、組み込みの保管担当者管理ツールを活用して、保管担当者の管理に関するワークフローを調整したり、ケース内で関連する custodial データソースを特定したりできます。保管担当者を追加すると、システムによって自動的に識別が行われ、プライマリ Exchange メールボックスと OneDrive for business サイトが保持されます。検出を実行するときに、保管担当者が今日のメンバーである、過去または複数のチームで保管担当者がアクセスしたメールボックスやサイトを発見してマップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="27faf-p101">Using Advanced eDiscovery (Preview), you can leverage the built-in custodian management tool to coordinate your workflows around managing custodians and identifying relevant, custodial data sources within a case. When you add a custodian, the system can automatically identify, and place holds on their primary Exchange mailbox and OneDrive for Business site. As you conduct your discovery, you might also uncover and map additional mailboxes or sites that a custodian accessed in the past or Teams that a custodian is a member of today.</span></span>

<span data-ttu-id="27faf-106">次のワークフローを使用して、セキュリティ & コンプライアンスセンター内の高度な電子情報開示 (プレビュー) ケースで保管担当者を追加および管理します。</span><span class="sxs-lookup"><span data-stu-id="27faf-106">Use the following workflow to add and manage custodians in Advanced eDiscovery (Preview) cases within the Security & Compliance Center.</span></span> 

![[保管担当者の管理] タブ](../media/CustodianMgtPage.png)


## <a name="step-1-identify-potential-custodians"></a><span data-ttu-id="27faf-108">手順 1: 潜在的な保管担当者を特定する</span><span class="sxs-lookup"><span data-stu-id="27faf-108">Step 1: Identify potential custodians</span></span>

<span data-ttu-id="27faf-p102">最初の手順として、適切な保管担当者を特定します。ケースに保管担当者を追加するには、電子情報開示マネージャーまたは電子情報開示管理者の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="27faf-p102">The first step is to identify the appropriate custodians for your matter. To add custodians to a case, you must be a member of the eDiscovery Managers or eDiscovery Admins role group.</span></span>   

![潜在的な保管担当者を特定する](../media/AddCustodianStep1.png)

<span data-ttu-id="27faf-112">既存の高度な電子情報開示 (プレビュー) ケースに保管担当者を追加するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="27faf-112">To add custodians to an existing Advanced eDiscovery (Preview) case:</span></span>

1. <span data-ttu-id="27faf-113">**[高度な電子情報開示 (プレビュー)** ] ページで、ケースに移動します。</span><span class="sxs-lookup"><span data-stu-id="27faf-113">From the **Advanced eDiscovery (Preview)** page, go to your case.</span></span>
 
2. <span data-ttu-id="27faf-114">ケースを選択した後、[**保管担当者**] タブに移動し、[ **+ Add 保管担当者**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27faf-114">After you have selected a case, go to the **Custodians** tab and click **+ Add Custodian**.</span></span> 
 
3. <span data-ttu-id="27faf-p103">ケースに追加する保管担当者を選択します。開始するには、組織の Azure Active Directory からユーザーを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="27faf-p103">Choose the custodians that you want to add to the case. You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="27faf-117">保管担当者の一覧が完成したら、[**次**へ] をクリックして、潜在的なデータソースの識別を開始します。</span><span class="sxs-lookup"><span data-stu-id="27faf-117">After you have finalized the list of custodians, click **Next** to begin identifying potential data sources.</span></span> 
  
## <a name="optional-step-2-select-custodian-data-sources"></a><span data-ttu-id="27faf-118">オプション手順 2: 保管担当者データソースを選択する</span><span class="sxs-lookup"><span data-stu-id="27faf-118">(Optional) Step 2: Select custodian data sources</span></span>

<span data-ttu-id="27faf-p104">ケースに保管担当者を追加した後は、Office 365 を活用して、プライマリ保管担当者データソースを特定して保持することができます。このワークフローの次の手順では、手順1で指定した保管担当者によって所有されるデータソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="27faf-p104">After you have added custodians to a case, you can leverage Office 365 to help you identify and preserve the primary custodian data sources. The next step in this workflow is to select the data sources owned by the custodians specified in Step 1.</span></span> 

![custodial データソースの選択](../media/AddCustodianStep2.png)

<span data-ttu-id="27faf-122">保管担当者データソースを識別するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="27faf-122">To identify custodian data sources:</span></span> 

1. <span data-ttu-id="27faf-123">保管担当者ごとに、保管担当者のプライマリ exchange メールボックスを自動的に識別して追加したい場合は、[ **Exchange** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="27faf-123">For each custodian, select **Exchange** if you would like the system to automatically identify and add the custodian's primary Exchange mailbox.</span></span> 
 
2. <span data-ttu-id="27faf-124">保管担当者ごとに、保管担当者のプライマリ onedrive URL を自動的に識別して追加する場合は、[ **onedrive** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="27faf-124">For each custodian, select **OneDrive** if you would like the system to automatically identify and add the custodian's primary OneDrive URL.</span></span> 

    <span data-ttu-id="27faf-125">選択した後、システムはデータソースを自動的に識別してケースに追加します。</span><span class="sxs-lookup"><span data-stu-id="27faf-125">After you've made your selections, they system will automatically try to identify the data sources and add them to your case.</span></span>
 
4. <span data-ttu-id="27faf-126">[**次**へ] をクリックして、保管担当者への追加のデータソースのマッピングを開始します。</span><span class="sxs-lookup"><span data-stu-id="27faf-126">Click **Next** to begin mapping additional data sources to your custodian.</span></span>

## <a name="optional-step-3-map-additional-data-sources"></a><span data-ttu-id="27faf-127">オプション手順 3: 追加のデータソースをマップする</span><span class="sxs-lookup"><span data-stu-id="27faf-127">(Optional) Step 3: Map additional data sources</span></span>

<span data-ttu-id="27faf-p105">ケースによっては、特定の保管担当者が以前に使用していたメールボックス、保管担当者が現在メンバーであるグループ、以前に保管担当者にアクセスしたことがあったサイトを追加することもできます。プライマリ保管担当者データソースに加えて、office 365 データソースを保管担当者に追加したり、office 365 を利用して、潜在的な関連データソースの特定に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="27faf-p105">Depending on your case, you may also want to add mailboxes that a given custodian may have used in the past, groups where a custodian is currently a member, or sites that a custodian had access to in the past. In addition to primary custodian data sources, you can add additional Office 365 data sources to a custodian or leverage Office 365 to help you identify potentially relevant data sources as well.</span></span> 

![追加のデータソースをマップする](../media/AddCustodianStep3.PNG)

<span data-ttu-id="27faf-131">メールボックス、サイト、またはチームを特定の保管担当者にマップするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="27faf-131">To map mailboxes, sites, or teams to a specific custodian:</span></span>

1. <span data-ttu-id="27faf-132">メールボックス、サイト、Teams などのコンテンツの場所を特定の保管担当者に割り当てるには、[**更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="27faf-132">Select **Update** to assign content locations, like mailboxes, sites, and Teams to a specific custodian.</span></span> 

2. <span data-ttu-id="27faf-133">ポップアップで、以下を指定します。</span><span class="sxs-lookup"><span data-stu-id="27faf-133">In the flyout, specify the following:</span></span>
   
    -  <span data-ttu-id="27faf-p106">**Exchange メールボックス**-[**ユーザー、グループ、またはチームを選択**する] をクリックし、[**ユーザー、グループ、または teams を再度選択**] をクリックします。選択した保管担当者に割り当てるメールボックスを指定するには、検索ボックスを使用してユーザーのメールボックスと配布グループを検索します。Office 365 グループまたは Microsoft チームに関連付けられているメールボックスを割り当てることもできます。[ユーザー、グループ、チーム] チェックボックスをオンにし、[**選択**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27faf-p106">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again. To specify mailboxes to assign to the selected custodian, use the search box to find user mailboxes and distribution groups. You can also assign the associated mailbox for an Office 365 Group or a Microsoft Team. Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="27faf-p107">[ユーザー、グループ、またはチームの選択] をクリックしてメールボックスを指定すると、表示されているメールボックスピッカーが空になります。これは、パフォーマンスを向上させるための仕様です。このリストにユーザーを追加するには、検索ボックスに名前 (少なくと3文字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="27faf-p107">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
     - <span data-ttu-id="27faf-p108">**sharepoint サイト**-[**サイトの選択**] をクリックし、[**サイトの選択**] をもう一度クリックして、選択した保管担当者に割り当てる追加の SharePoint および OneDrive for business サイトを指定します。Office 365 グループまたは Microsoft チームの SharePoint サイトの URL を追加することもできます。割り当てる各サイトの URL を入力します。[**選択**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27faf-p108">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you would like to assign to the selected custodian. You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team. Type the URL for each site that you want to assign. Click **Choose**, and then click **Done**.</span></span>
     - <span data-ttu-id="27faf-p109">**microsoft Teams** – [**チームの選択**] をクリックし、[ **teams の選択**] をもう一度クリックして、保管担当者が現在のメンバーである Microsoft チームグループの一覧を表示します。保管担当者に追加する Teams を選択します。このチェックボックスをオンにすると、システムは & を自動的に識別します。関連付けられている SharePoint サイトとグループメールボックスを選択して、その Microsoft チームに関連付けます。[**選択**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27faf-p109">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the custodian is a member of today. Select the Teams that you would like to add to your custodian. Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team. Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="27faf-149">Microsoft Teams を追加するには、上記のように、メールボックスと SharePoint サイトを個別に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27faf-149">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="27faf-p110">ソースのマッピングが終了したら、追加した保管担当者のメールボックス、サイト、および Teams の合計を表示できます。特定の保管担当者に関連するデータソースの最終処理が完了すると、このマッピングは保持され、電子情報開示のコレクション、処理、およびレビューのワークフローに拡張されます。</span><span class="sxs-lookup"><span data-stu-id="27faf-p110">After you have finished mapping your sources, you can view the total mailboxes, sites, and Teams for the custodians that you have just added. When you've finalized the data sources relevant for a specific custodian, this mapping will be maintained and extended to the eDiscovery collection, processing, and review workflows.</span></span> 

## <a name="optional-step-4-place-custodians-on-hold"></a><span data-ttu-id="27faf-152">オプション手順 4: 保管担当者を保留にする</span><span class="sxs-lookup"><span data-stu-id="27faf-152">(Optional) Step 4: Place custodians on hold</span></span>

<span data-ttu-id="27faf-p111">ケースに追加する保管担当者とデータソースの最終処理が完了したら、必要に応じて、一部またはすべての保管担当者を保留にすることができます。保管担当者を保留にすると、そのユーザーにマップされたコンテンツは、ケースから保管担当者を解放するか、ホールドを削除するまで保持されます。場合によっては、保管担当者をホールドの対象にしないで、ケースに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="27faf-p111">After you have finalized the custodians and data sources that you would like to add to your case, you can optionally place some or all of your custodians on hold. When you place a custodian on hold, the content mapped to that user is held until you release the custodian from the case or until you delete the hold. In some cases, you may want to add custodians to a case without placing them on hold.</span></span> 

<span data-ttu-id="27faf-156">選択した保管担当者とデータソースを保持するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="27faf-156">To place the selected custodians and data sources on hold:</span></span>

1. <span data-ttu-id="27faf-p112">保管担当者の選択を確認し、[各保管担当者を保持する] チェックボックスをオンにします。保管担当者が保留になると、すべての custodial ソースを含む保管担当者保持ポリシーが自動的に作成されます。オプションがチェックされていない場合は、保管担当者と選択されたデータソースがケースに追加されますが、コンテンツは保持されません。</span><span class="sxs-lookup"><span data-stu-id="27faf-p112">Verify your custodian selections and select the checkbox to place each custodian on hold. After a custodian is placed on hold, a custodian hold policy containing all custodial sources will be automatically created. If the option is not checked, the custodian and selected data sources will be added to the case but the content will not be preserved.</span></span>

2. <span data-ttu-id="27faf-160">[**保留**] タブに移動して、**保管担当者ホールドポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="27faf-160">Go to the **Holds** tab and select the **Custodian Hold Policy**.</span></span> 

3. <span data-ttu-id="27faf-161">[**編集**] をクリックして、選択したすべての保管担当者データソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="27faf-161">Click **Edit** to view all the selected custodian data sources.</span></span>

    ![インプレースホールド](../media/AddCustodianStep4.PNG)
