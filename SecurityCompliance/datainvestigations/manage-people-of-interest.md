---
title: データ調査で関心のあるユーザーを管理する (プレビュー)
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
ms.openlocfilehash: d06dde60ae75cfea1bf1d79f445b613d20a76363
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257675"
---
# <a name="manage-people-of-interest-in-data-investigations-preview"></a><span data-ttu-id="27c2a-102">データ調査で関心のあるユーザーを管理する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="27c2a-102">Manage people of interest in Data Investigations (Preview)</span></span>

<span data-ttu-id="27c2a-103">データ調査は、多くの場合、関心を持っています。</span><span class="sxs-lookup"><span data-stu-id="27c2a-103">Data investigations often involve people of interest.</span></span> <span data-ttu-id="27c2a-104">通常、これは、調査中または修正しようとしている、置き忘れ、機密、または悪意のあるデータを所有するユーザーです。</span><span class="sxs-lookup"><span data-stu-id="27c2a-104">Usually they are people who own the misplaced, sensitive or malicious data that you're investigating or looking to remediate.</span></span> <span data-ttu-id="27c2a-105">**データ調査 (プレビュー)** で、それらを追加して、検索の範囲を指定したり、連絡先、場所、アクティビティログなどの追加情報を表示したりするために、データソースを見つけ出すことができます。</span><span class="sxs-lookup"><span data-stu-id="27c2a-105">In **Data Investigations (Preview)**, you can add them to discover their data sources to use in scoping your search or view additional information such as contact, location and activity logs.</span></span> 


## <a name="add-people-of-interest"></a><span data-ttu-id="27c2a-106">関心のある人を追加する</span><span class="sxs-lookup"><span data-stu-id="27c2a-106">Add people of interest</span></span>

<span data-ttu-id="27c2a-107">[**関心のあるユーザー** ] タブでは、関心のある人を追加して、検索範囲を特定するために使用できる Exchange メールボックスや OneDrive for business サイトなどのデータソースを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="27c2a-107">In **People of interest** tab, you can add people of interest and discover their data sources such as Exchange mailboxes or OneDrive for Business site that you can use to scope your search.</span></span> <span data-ttu-id="27c2a-108">対象のユーザーによってスコープが設定されている場合は、画像やサポートされていないファイルの種類などのインデックスが設定されていないデータが再処理されるため、検索のパフォーマンスと正確性が向上します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-108">When scoped down by people of interest, searches are more performant and accurate because the tool re-processes any unindexed data such as images or unsupported file types.</span></span> <span data-ttu-id="27c2a-109">また、コミュニケーションを開始したり、アクティビティをさらに調べたりするために使用できる、連絡先情報、場所情報、およびアクティビティログを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="27c2a-109">You can also see their contact information, location information and activity logs that you can use to initiate communications or further investigate their activities.</span></span> 

<span data-ttu-id="27c2a-110">調査対象のユーザーを追加するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="27c2a-110">To add people of interest to an investigation:</span></span>

1. <span data-ttu-id="27c2a-111">[**データ調査 (プレビュー)** ] ページで、調査に移動します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-111">From the **Data Investigations (Preview)** page, go to your investigation.</span></span>
 
2. <span data-ttu-id="27c2a-112">調査を選択したら、[関心のある**ユーザー** ] タブに移動し、[**関心のある人を追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c2a-112">After you have selected a investigation, go to the **People of interest** tab and click **+ Add people of interest**.</span></span> 
 
3. <span data-ttu-id="27c2a-113">調査に追加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-113">Choose people that you want to add to the investigation.</span></span> <span data-ttu-id="27c2a-114">開始するには、組織の Azure Active Directory からユーザーを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-114">You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="27c2a-115">関心のある人物のリストを完成させると、[**次へ**] をクリックしてデータソースをマップします。</span><span class="sxs-lookup"><span data-stu-id="27c2a-115">After you have finalized the list of people of interest, click **Next** to map their data sources.</span></span> 

5. <span data-ttu-id="27c2a-116">オプション各ユーザーについて、[ **exchange** ] を選択して、ユーザーのプライマリ Exchange メールボックスを追加し、 **onedrive**を使用してユーザーのプライマリ onedrive for business サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-116">[Optional] For each person, select **Exchange** to add person's primary Exchange mailbox, and **OneDrive** to add person's primary OneDrive for Business site.</span></span>

6. <span data-ttu-id="27c2a-117">オプション[**次へ**] をクリックして、関心のあるユーザーに関連する追加のデータソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-117">[Optional] Click **Next** to add any additional data sources that you want to associate with your people of interest.</span></span>

7. <span data-ttu-id="27c2a-118">オプションメールボックス、サイト、Teams などのコンテンツの場所をユーザーに割り当てるには、[**更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-118">[Optional] Select **Update** to assign content locations, like mailboxes, sites, and Teams to a person.</span></span> 

8. <span data-ttu-id="27c2a-119">オプションフライアウトの場合:</span><span class="sxs-lookup"><span data-stu-id="27c2a-119">[Optional] In the flyout:</span></span>
   
    -  <span data-ttu-id="27c2a-120">**Exchange メールボックス**-[**ユーザー、グループ、またはチームを選択**する] をクリックし、[**ユーザー、グループ、または teams を再度選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c2a-120">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again.</span></span> <span data-ttu-id="27c2a-121">メールボックスをさらに追加するには、検索ボックスを使用してユーザーのメールボックスと配布グループを検索します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-121">To add more mailboxes, use the search box to find user mailboxes and distribution groups.</span></span> <span data-ttu-id="27c2a-122">また、Office 365 グループまたは Microsoft チーム情報を格納するために使用されるメールボックスを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="27c2a-122">You can also add mailboxes used to store an Office 365 Group or a Microsoft Team information.</span></span> <span data-ttu-id="27c2a-123">[ユーザー、グループ、チーム] チェックボックスをオンにし、[**選択**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c2a-123">Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="27c2a-124">[ユーザー、グループ、またはチームの選択] をクリックしてメールボックスを指定すると、表示されているメールボックスピッカーが空になります。</span><span class="sxs-lookup"><span data-stu-id="27c2a-124">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty.</span></span> <span data-ttu-id="27c2a-125">これは、パフォーマンスを向上させるための仕様です。</span><span class="sxs-lookup"><span data-stu-id="27c2a-125">This is by design to enhance performance.</span></span> <span data-ttu-id="27c2a-126">このリストにユーザーを追加するには、検索ボックスに名前 (少なくと3文字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-126">To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
     - <span data-ttu-id="27c2a-127">**sharepoint サイト**-[**サイトの選択**] をクリックし、[**サイトの選択**] をもう一度クリックして、ユーザーに追加する SharePoint および OneDrive for business サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-127">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you wwant to add to a person.</span></span> <span data-ttu-id="27c2a-128">Office 365 グループまたは Microsoft チームの SharePoint サイトの URL を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="27c2a-128">You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="27c2a-129">割り当てる各サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-129">Type the URL for each site that you want to assign.</span></span> <span data-ttu-id="27c2a-130">[**選択**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c2a-130">Click **Choose**, and then click **Done**.</span></span>
     - <span data-ttu-id="27c2a-131">**microsoft Teams** – [**チームの選択**] をクリックし、[ **teams の選択**] をもう一度クリックして、その人物が現在参加している microsoft チームグループの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-131">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the person is a member of today.</span></span> <span data-ttu-id="27c2a-132">ユーザーに追加するチームを選択します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-132">Select the Teams that you want to add to the person.</span></span> <span data-ttu-id="27c2a-133">このチェックボックスをオンにすると、システムは & を自動的に識別します。関連付けられている SharePoint サイトとグループメールボックスを選択して、その Microsoft チームに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="27c2a-133">Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team.</span></span> <span data-ttu-id="27c2a-134">[**選択**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c2a-134">Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="27c2a-135">Microsoft Teams を追加するには、上記のように、メールボックスと SharePoint サイトを個別に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27c2a-135">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="27c2a-136">関心のあるユーザーにデータソースのマッピングを完了すると、追加したメールボックス、サイト、およびチームの合計の概要を確認できます。</span><span class="sxs-lookup"><span data-stu-id="27c2a-136">After you have finished mapping data sources to people of interest, you can see the summary of total mailboxes, sites, and Teams that you just added.</span></span> <span data-ttu-id="27c2a-137">関心のあるユーザーに対して追加のデータソースをマップし、関心のあるユーザーによる検索の範囲を決定した場合、関心のあるユーザーへのドキュメントのマッピングは、調査全体を通じて保持されるため、興味のある人が証拠を整理したりレポートを生成したりすることが容易になります。.</span><span class="sxs-lookup"><span data-stu-id="27c2a-137">If you map any additional data sources to people of interest and scope your search by people of interest, the mapping of document to people of interest persist throughout the investigation, making it easier to organize evidence or generate report by people of interest.</span></span> 

## <a name="view-additional-people-of-interest-information"></a><span data-ttu-id="27c2a-138">その他の関心のある人の情報を表示する</span><span class="sxs-lookup"><span data-stu-id="27c2a-138">View additional people of interest information</span></span>

<span data-ttu-id="27c2a-139">[**関心のあるユーザー** ] タブで、adeed のある人物をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27c2a-139">In **People of interest** tab, click on a person that you adeed.</span></span> <span data-ttu-id="27c2a-140">フライアウトの場合は、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="27c2a-140">In a flyout, you'll see:</span></span>

- <span data-ttu-id="27c2a-141">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="27c2a-141">Contact information</span></span>

  - <span data-ttu-id="27c2a-142">[**表示名**: アドレス帳に表示される peron の名前です。</span><span class="sxs-lookup"><span data-stu-id="27c2a-142">**Display Name**: The peron's name displayed in the address book.</span></span> <span data-ttu-id="27c2a-143">これは通常、姓、ミドルネーム、姓の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="27c2a-143">This is usually the combination of first name, middle initial and last name.</span></span>
  - <span data-ttu-id="27c2a-144">[**メール/SMTP**]: ユーザーの SMTP アドレスです。たとえば、jeff@contoso.onmicrosoft.com のようになります。</span><span class="sxs-lookup"><span data-stu-id="27c2a-144">**Mail/SMTP**: The SMTP address of the person, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="27c2a-145">**タイトル**: 役職</span><span class="sxs-lookup"><span data-stu-id="27c2a-145">**Title**: Job title.</span></span>
  - <span data-ttu-id="27c2a-146">**department**: ユーザーが働く部署の名前。</span><span class="sxs-lookup"><span data-stu-id="27c2a-146">**Department**: The name of the department in which the person works.</span></span>
  - <span data-ttu-id="27c2a-147">**上司**: ユーザーの上司。</span><span class="sxs-lookup"><span data-stu-id="27c2a-147">**Manager**: The person's manager.</span></span> <span data-ttu-id="27c2a-148">上司がこの人物のすべてのエスカレーション情報を受信します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-148">Manager receives any escalation communications for this person.</span></span>
  
- <span data-ttu-id="27c2a-149">場所情報</span><span class="sxs-lookup"><span data-stu-id="27c2a-149">Location information</span></span>

  - <span data-ttu-id="27c2a-150">**city**: 人物が配置されている市区町村。</span><span class="sxs-lookup"><span data-stu-id="27c2a-150">**City**: The city in which the person is located.</span></span>
  - <span data-ttu-id="27c2a-151">[**状態**: 人物が配置されている都道府県を指定します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-151">**State**: The state or province in which the person is located.</span></span>
  - <span data-ttu-id="27c2a-152">[**国/地域**]: 人物が配置されている国/地域。たとえば、"US" や "UK" などです。</span><span class="sxs-lookup"><span data-stu-id="27c2a-152">**Country/Region**: The country/region in which the person is located; for example, “US” or “UK”.</span></span>
  - <span data-ttu-id="27c2a-153">**office**: ユーザーの勤務先所在地。</span><span class="sxs-lookup"><span data-stu-id="27c2a-153">**Office**: The office location of the person.</span></span>

- <span data-ttu-id="27c2a-154">処理状態</span><span class="sxs-lookup"><span data-stu-id="27c2a-154">Processing status</span></span>

  - <span data-ttu-id="27c2a-155">**インデックスの状態**: データソースの詳細なインデックス作成の状態</span><span class="sxs-lookup"><span data-stu-id="27c2a-155">**Indexing status**: Status of deep indexing the data sources</span></span>
  - <span data-ttu-id="27c2a-156">**インデックス作成の最終更新日時**: ディープインデックス作成ジョブが最後にトリガーされた時点のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="27c2a-156">**Indexing Last Updated Time**: Timestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="27c2a-157">**データソース**: ユーザーにマップされたメールボックス、サイト、およびチームの数を示します。</span><span class="sxs-lookup"><span data-stu-id="27c2a-157">**Data sources**: Shows the count of mailboxes, sites, and Teams mapped to the person</span></span>

- <span data-ttu-id="27c2a-158">インデックスの更新</span><span class="sxs-lookup"><span data-stu-id="27c2a-158">Update index</span></span>
    - <span data-ttu-id="27c2a-159">このユーザーのデータソースのインデックスを再作成することができます。</span><span class="sxs-lookup"><span data-stu-id="27c2a-159">You can re-index this person's data sources.</span></span> 

- <span data-ttu-id="27c2a-160">アクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="27c2a-160">View activity</span></span> 

    - <span data-ttu-id="27c2a-161">ユーザーのアクティビティログを表示し、検索することができます。</span><span class="sxs-lookup"><span data-stu-id="27c2a-161">You can view and search user's activity logs.</span></span> <span data-ttu-id="27c2a-162">詳細については、「[ユーザーの重要なアクティビティを表示](view-people-of-interest-activity.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27c2a-162">For more information, see [View people of interest activity](view-people-of-interest-activity.md)</span></span> 
