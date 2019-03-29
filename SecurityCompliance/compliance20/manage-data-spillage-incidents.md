---
title: Microsoft 365 でデータ流出インシデントを管理する
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
description: この記事では、Office 365 Security & コンプライアンスセンターで新しいデータ調査 (プレビュー) ツールを使用してデータ流出インシデントを管理する方法について説明します。
ms.openlocfilehash: 33943ee4367e01f413cfa7840c796d5197323185
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862559"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a><span data-ttu-id="3331f-103">Microsoft 365 でデータ流出インシデントを管理する</span><span class="sxs-lookup"><span data-stu-id="3331f-103">Manage a data spillage incident in Microsoft 365</span></span> 

<span data-ttu-id="3331f-104">データ流出は、信頼できない環境に機密ドキュメントがリリースされるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3331f-104">Data spillage is when a confidential document is released into an untrusted environment.</span></span> <span data-ttu-id="3331f-105">データ流出インシデントが検出された場合、流出のサイズと場所をすばやく評価し、その周囲のユーザーアクティビティを調べて、システムから完全に削除されたデータを完全に削除することが重要です。</span><span class="sxs-lookup"><span data-stu-id="3331f-105">When a data spillage incident is detected, it's important to quickly assess the size and locations of the spillage, examine user activities around it, and then permanently purge the spilled data from the system.</span></span>

## <a name="scope-of-this-article"></a><span data-ttu-id="3331f-106">この記事の対象範囲</span><span class="sxs-lookup"><span data-stu-id="3331f-106">Scope of this article</span></span>

<span data-ttu-id="3331f-107">この記事では、Office 365 メールボックスからアイテムを完全に削除して、ユーザーまたは管理者がアクセスまたは回復できないようにする手順の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3331f-107">This article provides a list of instructions on how to permanently remove items from Office 365 mailboxes so they are no longer accessible or recoverable by users or admins.</span></span> 

> [!NOTE]
> <span data-ttu-id="3331f-108">SharePoint または OneDrive for business サイトにあるアイテムを削除すると、元の場所から削除した時点から93日以内に保持されます。</span><span class="sxs-lookup"><span data-stu-id="3331f-108">When you delete items located in a SharePoint or OneDrive for Business site, they are retained for 93 days from the time you delete them from their original location.</span></span>

## <a name="scenario"></a><span data-ttu-id="3331f-109">シナリオ</span><span class="sxs-lookup"><span data-stu-id="3331f-109">Scenario</span></span>

<span data-ttu-id="3331f-110">従業員が知らずに大量の機密ドキュメントを電子メールで共有しているデータ流出インシデントについて通知されています。</span><span class="sxs-lookup"><span data-stu-id="3331f-110">You're informed of a data spillage incident where an employee unknowingly shared a highly-confidential document with multiple people through email.</span></span> <span data-ttu-id="3331f-111">組織の内部と外部の両方で、このドキュメントを受信したユーザーをすばやく評価する必要がある。</span><span class="sxs-lookup"><span data-stu-id="3331f-111">You want to quickly assess who received this document, both inside and outside of your organization.</span></span> <span data-ttu-id="3331f-112">インシデントを調査した後、調査対象を他の捜査官と共有し、こぼれたデータを Office 365 から完全に削除することを計画します。</span><span class="sxs-lookup"><span data-stu-id="3331f-112">After you've investigate the incident, you plan to share your findings with other investigators to review, and then permanently remove the spilled data from Office 365.</span></span> <span data-ttu-id="3331f-113">調査が完了したら、すべての証拠を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3331f-113">After the investigation is complete, you want to remove all evidence.</span></span> 

## <a name="workflow"></a><span data-ttu-id="3331f-114">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="3331f-114">Workflow</span></span>

<span data-ttu-id="3331f-115">データ調査 (プレビュー) を使用してデータ流出インシデントを管理するためのワークフローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="3331f-115">Here's the workflow for using Data Investigations (Preview) to manage a data spillage incident:</span></span>

1.  <span data-ttu-id="3331f-116">データ調査を作成します。</span><span class="sxs-lookup"><span data-stu-id="3331f-116">Create a data investigation.</span></span>

2.  <span data-ttu-id="3331f-117">こぼれたデータを検索します。</span><span class="sxs-lookup"><span data-stu-id="3331f-117">Search for the spilled data.</span></span>

3.  <span data-ttu-id="3331f-118">インシデントを確認して調査します。</span><span class="sxs-lookup"><span data-stu-id="3331f-118">Review and investigate the incident.</span></span>

4.  <span data-ttu-id="3331f-119">こぼれたデータを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="3331f-119">Permanently delete the spilled data.</span></span>

5.  <span data-ttu-id="3331f-120">調査を終了または削除します。</span><span class="sxs-lookup"><span data-stu-id="3331f-120">Close or delete the investigation.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="3331f-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="3331f-121">Before you begin</span></span>

- <span data-ttu-id="3331f-122">Office 365 Security & コンプライアンスセンターのデータ調査 (プレビュー) ツールを使用して、調査を作成し、こぼれたデータを検索して、それを確認して分析します。</span><span class="sxs-lookup"><span data-stu-id="3331f-122">You'll use the Data Investigations (Preview) tool in the Office 365 Security & Compliance Center to create an investigation, search for the spilled data, and review and analyze it.</span></span> <span data-ttu-id="3331f-123">その後、セキュリティ & コンプライアンスセンター PowerShell を使用して、Office 365 からこぼれたデータを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="3331f-123">Then you'll use Security & Compliance Center PowerShell to permanently delete the spilled data from Office 365.</span></span> 

- <span data-ttu-id="3331f-124">調査を作成するには、セキュリティ & コンプライアンスセンターのコンプライアンス管理者役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3331f-124">To create an investigation, you have to be a member of the Compliance Administrator role group in the Security & Compliance Center.</span></span>

- <span data-ttu-id="3331f-125">メッセージを削除するには、Security & コンプライアンスセンターで組織の管理役割グループのメンバーであるか、検索と削除の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3331f-125">To delete messages, you have to be a member of the Organization Management role group in the Security & Compliance Center or be assigned the Search and Purge role.</span></span> <span data-ttu-id="3331f-126">役割グループへのユーザーの追加の詳細については、「[ユーザーにセキュリティ & コンプライアンスセンターへのアクセス権を付与する](../grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3331f-126">For information about adding users to a role group, see [Give users access to the Security & Compliance Center](../grant-access-to-the-security-and-compliance-center.md).</span></span> 

- <span data-ttu-id="3331f-127">調査担当が検索できるユーザーメールボックスおよび OneDrive アカウントを制御するには、組織でコンプライアンスの境界を設定できます。</span><span class="sxs-lookup"><span data-stu-id="3331f-127">To control which user mailboxes and OneDrive accounts an investigator can search, your organization can set up compliance boundaries.</span></span> <span data-ttu-id="3331f-128">詳細については、[電子情報開示調査のためにコンプライアンスの境界を設定](../set-up-compliance-boundaries.md)します。</span><span class="sxs-lookup"><span data-stu-id="3331f-128">For more information, [Set up compliance boundaries for eDiscovery investigations](../set-up-compliance-boundaries.md).</span></span> 

## <a name="step-1-create-a-data-investigation"></a><span data-ttu-id="3331f-129">手順 1: データ調査を作成する</span><span class="sxs-lookup"><span data-stu-id="3331f-129">Step 1: Create a data investigation</span></span>

<span data-ttu-id="3331f-130">データ調査を作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3331f-130">To create a data investigation:</span></span>

1. <span data-ttu-id="3331f-131">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="3331f-131">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="3331f-132">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="3331f-132">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="3331f-133">セキュリティ & コンプライアンスセンターで、[**データ調査**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3331f-133">In the Security & Compliance Center, click **Data Investigations**.</span></span>
 
4. <span data-ttu-id="3331f-134">[**データ調査 (プレビュー)** ] ページで、[**新しい調査の作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3331f-134">On the **Data Investigations (Preview)** page, click **Create a new investigation**.</span></span>
    
5. <span data-ttu-id="3331f-135">[**新しいデータ調査**のポップアップ] ページで、調査の名前 (必須) を指定し、オプションの調査番号と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="3331f-135">On the **New data investigation** flyout page, give the investigation a name (required), and then type an optional investigation number and description.</span></span> <span data-ttu-id="3331f-136">この名前は、組織内で一意である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3331f-136">Note that the name must be unique in your organization.</span></span>

6. <span data-ttu-id="3331f-137">[**この調査を作成した後、追加の設定を構成しますか?**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3331f-137">Under **Do you want to configure additional settings after creating this investigation?**, do one of the following:</span></span>

    - <span data-ttu-id="3331f-138">[**はい**] をクリックして調査を作成し、新しいケースで [**設定**] ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="3331f-138">Click **Yes** to create the investigation, and display the **Settings** page in the new case.</span></span> <span data-ttu-id="3331f-139">これにより、調査にメンバーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="3331f-139">This allows you to add members to the investigation.</span></span>
    
    - <span data-ttu-id="3331f-140">[**いいえ**] をクリックすると、調査が作成され、[**データ調査 (プレビュー)** ] ページのケースの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3331f-140">Click **No** to just create the investigation and display it in the list of cases on the **Data Investigations (Preview)** page.</span></span> <span data-ttu-id="3331f-141">このオプションを選択すると、調査の唯一のメンバーとして追加され、既定の検索と分析の設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3331f-141">If you choose this option, you will be added as the only member of the investigation and the default search and analytics settings will be used.</span></span> <span data-ttu-id="3331f-142">調査が作成されたらいつでもメンバーを追加したり、設定を変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="3331f-142">You can add members or change settings any time after the investigation is created.</span></span>

7. <span data-ttu-id="3331f-143">[**保存**] をクリックして、調査を作成します。</span><span class="sxs-lookup"><span data-stu-id="3331f-143">Click **Save** to create the investigation.</span></span>

    <span data-ttu-id="3331f-144">新しい調査は、[**データ調査 (プレビュー)** ] ページの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3331f-144">The new investigation is displayed in the list on the **Data Investigations (Preview)** page.</span></span> 

8. <span data-ttu-id="3331f-145">調査を開くには、調査の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3331f-145">To open an investigation, click the name of the investigation.</span></span> 

    <span data-ttu-id="3331f-146">調査の [**ホーム**] タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3331f-146">The **Home** tab for the investigation is displayed.</span></span> 

> [!TIP]
> <span data-ttu-id="3331f-147">調査の名前付け規則を確立し、必要に応じて後で検索して参照できるように、名前と説明に記載されている限り多くの情報を提供することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="3331f-147">Consider establishing a naming convention for investigations and provide as much information as you can in the name and description so you can locate and refer to in the future if necessary.</span></span>
 
## <a name="step-2-search-for-the-spilled-data"></a><span data-ttu-id="3331f-148">手順 2: こぼれたデータを検索する</span><span class="sxs-lookup"><span data-stu-id="3331f-148">Step 2: Search for the spilled data</span></span> 
 
<span data-ttu-id="3331f-149">保存されていないデータを検索するユーザーがわかっている場合は、それらを関心のあるユーザーとして追加し、データソースを調査にマップして、自分のメールボックスと OneDrive アカウントをすばやく検索することができます。</span><span class="sxs-lookup"><span data-stu-id="3331f-149">If you know which users you want to search for spilled data, you can add them as people of interest to map their data sources to the investigation and quickly search their mailbox and OneDrive account.</span></span> <span data-ttu-id="3331f-150">調査対象のユーザーを追加するには、[**関心**のある人] をクリックし、[**関心のある**人を追加する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3331f-150">To add people of interest to the investigation, click **People of interest**, and then click **Add people of interest**.</span></span> 

<span data-ttu-id="3331f-151">[**検索**] タブでは、検索を作成して、こぼれたデータを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="3331f-151">On the **Searches** tab, you can create searches to find the spilled data.</span></span> <span data-ttu-id="3331f-152">[手順 4](#step-4-permanently-delete-the-spilled-data)で同じメッセージを削除するために使用したものと同じ検索クエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="3331f-152">You will use the same search query that you used to find the spilled data to delete those same messages in [Step 4](#step-4-permanently-delete-the-spilled-data).</span></span> <span data-ttu-id="3331f-153">検索を作成する方法の詳細については、「[データを収集するための検索を作成する](create-search-to-collect-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3331f-153">For more information about creating searches, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="3331f-154">検索を実行した後、検索結果のサンプルをプレビューし、検索の統計を表示して、検索クエリの効果を評価できます。</span><span class="sxs-lookup"><span data-stu-id="3331f-154">After you run the search, you can preview samples of search results and view search statistics to evaluate the effectiveness of your search query.</span></span> <span data-ttu-id="3331f-155">Office 365 から削除するアイテムを特定したら、[**インシデント**] タブをクリックして、インシデントを作成し、それらのアイテムを含む検索結果を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="3331f-155">Once you identify the items that you want to delete from Office 365, you can click the **Incidents** tab, and then create an incident and add search results that contain those items.</span></span> 

<span data-ttu-id="3331f-156">これを行うには、調査する検索をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3331f-156">To do this, click the search that you want to investigate.</span></span> <span data-ttu-id="3331f-157">[ポップアップ] ページで、[**結果をインシデントに追加する**] をクリックし、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="3331f-157">On the flyout page, click **Add results to incident** and follow the instructions.</span></span> <span data-ttu-id="3331f-158">インシデントでは、個々のドキュメントを確認したり、ドキュメントにアクセスしたユーザーを調べたり、ドキュメントをエクスポートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3331f-158">Then in the incident, you can review individual documents, investigate who had access to documents, and export the documents.</span></span> <span data-ttu-id="3331f-159">ドキュメントを確認するのではなく、単に削除するには、[手順 4](#step-4-permanently-delete-the-spilled-data)に進みます。</span><span class="sxs-lookup"><span data-stu-id="3331f-159">To simply delete the documents instead of reviewing them, go to [Step 4](#step-4-permanently-delete-the-spilled-data).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3331f-160">検索クエリで使用するキーワードには、検索している実際のこぼれたデータが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="3331f-160">The keywords that you use in the search query may contain the actual spilled data that you're searching for.</span></span> <span data-ttu-id="3331f-161">たとえば、社会保障番号を含むドキュメントを検索し、検索クエリでキーワードとして使用する場合は、さらに流出を回避するために、後でクエリを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3331f-161">For example, if you searching for documents containing a social security number and you use it as a keyword in the search query, you must delete the query afterwards to avoid further spillage.</span></span> <span data-ttu-id="3331f-162">[手順 5](#step-5-close-or-delete-the-investigation)では、検索を削除するか、調査全体を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="3331f-162">You can delete search or delete the entire investigation in [Step 5](#step-5-close-or-delete-the-investigation).</span></span> 

## <a name="step-3-review-and-investigate"></a><span data-ttu-id="3331f-163">手順 3: レビューと調査</span><span class="sxs-lookup"><span data-stu-id="3331f-163">Step 3: Review and investigate</span></span> 

<span data-ttu-id="3331f-164">調査中に、[**インシデント**] タブに移動し、前の手順で作成したインシデントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3331f-164">In the investigation, go to **Incidents** tab and click on the incident that you created in the previous step.</span></span> <span data-ttu-id="3331f-165">処理ジョブが完了し、検索結果がインシデントに追加されると、個々のドキュメントをネイティブ形式、テキスト形式、またはほぼネイティブ形式で確認できます。</span><span class="sxs-lookup"><span data-stu-id="3331f-165">After the processing job is completed and the search results are added to the incident, you can review individual documents in their native format, text format, or a near-native format.</span></span> <span data-ttu-id="3331f-166">追加のクエリを作成してドキュメントの一覧をさらに絞り込んだり、調査結果を示すためにドキュメントにタグを付けたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3331f-166">You can create additional queries to further narrow the list of documents, and tag documents to indicate findings from your investigation.</span></span>

<span data-ttu-id="3331f-167">ドキュメントをグループ化し、レビューの詳細を取得するには、[**インシデントの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3331f-167">To group documents and get more assistance for your review, click **Manage incident**.</span></span> <span data-ttu-id="3331f-168">[**分析**] タイルで、[**分析**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3331f-168">In the **Analytics** tile, click **Analyze**.</span></span> <span data-ttu-id="3331f-169">これにより、重複データ検出、電子メールスレッド、テーマ分析などの高度な分析が実行されます。</span><span class="sxs-lookup"><span data-stu-id="3331f-169">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="3331f-170">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3331f-170">For more information, see:</span></span>

- [<span data-ttu-id="3331f-171">準重複の検出</span><span class="sxs-lookup"><span data-stu-id="3331f-171">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="3331f-172">電子メールのスレッド化</span><span class="sxs-lookup"><span data-stu-id="3331f-172">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="3331f-173">テーマ</span><span class="sxs-lookup"><span data-stu-id="3331f-173">Themes</span></span>](themes.md)

<span data-ttu-id="3331f-174">データ流出に関係しているユーザーを特定するには、インシデントで新しいクエリを作成し、送信者/作成者と受信者の条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="3331f-174">To determine which users are involved in the data spillage, you can create a new query in the incident and then use the Sender/Author and Recipients conditions.</span></span> <span data-ttu-id="3331f-175">これにより、インシデントに追加された収集データに含まれるすべての送信者、受信者、および作成者の一覧が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3331f-175">This will create a list of all senders, recipients and authors found in collected data that was added to the incident.</span></span> <span data-ttu-id="3331f-176">リストを調べて、リストに外部ユーザーが存在するかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3331f-176">Be sure to examine the list to determine if there are any external users in the list.</span></span> <span data-ttu-id="3331f-177">詳細については、「[検索条件](../keyword-queries-and-search-conditions.md#search-conditions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3331f-177">For more information, see [Search conditions](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>

## <a name="step-4-permanently-delete-the-spilled-data"></a><span data-ttu-id="3331f-178">手順 4: こぼれたデータを完全に削除する</span><span class="sxs-lookup"><span data-stu-id="3331f-178">Step 4: Permanently delete the spilled data</span></span>

### <a name="deleting-mailbox-items"></a><span data-ttu-id="3331f-179">メールボックスアイテムの削除</span><span class="sxs-lookup"><span data-stu-id="3331f-179">Deleting mailbox items</span></span>

<span data-ttu-id="3331f-180">削除が必要な電子メールメッセージのみが検索結果に含まれていることを確認して検証した後、セキュリティ & コンプライアンスで**new-compliancesearchaction-PurgeType ハード削除**コマンドを実行して、それらを完全に削除することができます。Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="3331f-180">After you review and validate that the search results contain only the email messages that must be deleted, you can permanently delete them by running the **New-ComplianceSearchAction -Purge -PurgeType HardDelete** command in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="3331f-181">手順については、「[メールメッセージの検索と削除](../search-for-and-delete-messages-in-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3331f-181">For instructions, see [Search for and delete email messages](../search-for-and-delete-messages-in-your-organization.md).</span></span> 

<span data-ttu-id="3331f-182">単一アイテムの回復が組織内のメールボックスに対して有効になっている場合は、削除済みアイテムの保存期間が終了するまで、完全に削除されたアイテムはユーザーの回復可能なアイテムフォルダーに保持され (管理者がアクセス可能)、削除済みアイテムの保存期間が終了します (既定値は14日)。</span><span class="sxs-lookup"><span data-stu-id="3331f-182">Note that if single item recovery is enabled for mailboxes in your organization, permanently deleted items will be retained in the user's Recoverable items folder (and accessible by admins) until the deleted item retention period ends (default is 14 days).</span></span> <span data-ttu-id="3331f-183">また、保存されているデータを含むメールボックスのいずれかが legal hold にある場合、またはアイテム保持ポリシーに割り当てられている場合、削除されたメッセージは保持が削除されるか、またはメールボックスがアイテム保持ポリシーから除外されるまで、回復可能なアイテムフォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="3331f-183">Additionally, if any of the mailboxes that contain spilled data are on a legal hold or assigned to a retention policy, purged message will be retained in Recoverable items folder until the hold is removed or the mailbox is excluded from retention policies.</span></span> <span data-ttu-id="3331f-184">メッセージを直ちにハード削除するには、追加タスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3331f-184">To hard delete messages immediately, you need to perform addition tasks.</span></span> <span data-ttu-id="3331f-185">手順については、「[保持中のクラウドベースのメールボックスの回復可能なアイテムフォルダーのアイテムを削除する](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3331f-185">For instructions, see [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold ](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md).</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="3331f-186">保留またはアイテム保持ポリシーを削除する前に、レコード管理または法務部門に確認してください。</span><span class="sxs-lookup"><span data-stu-id="3331f-186">Check with your records management or legal departments before removing a hold or retention policy.</span></span> <span data-ttu-id="3331f-187">組織には、保留中のメールボックスとデータ流出インシデントのどちらを優先するかを定義するポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="3331f-187">Your organization may have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 

### <a name="deleting-site-items"></a><span data-ttu-id="3331f-188">サイトアイテムの削除</span><span class="sxs-lookup"><span data-stu-id="3331f-188">Deleting site items</span></span>

<span data-ttu-id="3331f-189">SharePoint サイトまたは OneDrive for business アカウントからドキュメントを完全に削除するには、削除する必要があります。その後、サイトコレクションのごみ箱から削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3331f-189">To permanently delete a document from a SharePoint site or OneDrive for Business account, you have to delete it and then you have to delete from the site and then delete it from the site collection Recycle Bin.</span></span> <span data-ttu-id="3331f-190">手順については、「 [SharePoint および OneDrive でドキュメントを削除](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3331f-190">For instructions, see [Delete documents in SharePoint and OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business).</span></span>

<span data-ttu-id="3331f-191">また、必要なデータが含まれていたサイトコレクション全体を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="3331f-191">Alternatively, you can delete an entire site collection that might contained spilled data.</span></span> <span data-ttu-id="3331f-192">手順については、「[サイトコレクションを削除する](https://docs.microsoft.com/sharepoint/delete-site-collection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3331f-192">For instructions, see [Delete a site collection](https://docs.microsoft.com/sharepoint/delete-site-collection).</span></span>

## <a name="step-5-close-or-delete-the-investigation"></a><span data-ttu-id="3331f-193">手順 5: 調査を終了または削除する</span><span class="sxs-lookup"><span data-stu-id="3331f-193">Step 5: Close or delete the investigation</span></span>

<span data-ttu-id="3331f-194">ソースコンテンツの場所 (メールボックスまたはサイト) のドキュメントを削除した後も、調査の一環としてインシデントに追加したこれらのドキュメントのコピーが残ります。</span><span class="sxs-lookup"><span data-stu-id="3331f-194">After you delete documents in the source content locations (mailboxes or sites), you will still have copies of these documents that you added to incidents as part of your investigation.</span></span> <span data-ttu-id="3331f-195">その他のデータ流出を回避するには、調査を削除することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3331f-195">To avoid further data spillage, you should consider deleting the investigation.</span></span>

<span data-ttu-id="3331f-196">調査を削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3331f-196">To delete an investigation:</span></span>

1. <span data-ttu-id="3331f-197">[**設定**] タブで、[**調査情報**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3331f-197">On the **Settings** tab, click **Investigation information**.</span></span>

2. <span data-ttu-id="3331f-198">[ **case の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3331f-198">Click  **Delete case**.</span></span> 

<span data-ttu-id="3331f-199">調査を削除する必要がない場合や、調査時に収集した情報を保存する場合は、[case を**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3331f-199">If you don't need to delete the investigation or if you want to save the information that you collected during the investigation, you can click **Close case**.</span></span> <span data-ttu-id="3331f-200">後で、クローズした調査を再度開くことができます。</span><span class="sxs-lookup"><span data-stu-id="3331f-200">At a later date, you can re-open closed investigations.</span></span>