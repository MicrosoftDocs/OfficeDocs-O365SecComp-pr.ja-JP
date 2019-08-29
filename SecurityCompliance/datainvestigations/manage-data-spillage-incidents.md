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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: この記事では、セキュリティ & コンプライアンスセンターで新しいデータ調査 (プレビュー) ツールを使用してデータ流出インシデントを管理する方法について説明します。
ms.openlocfilehash: 93199ad1f548e999dce9ad79ab311a57345b8772
ms.sourcegitcommit: 3962de88a143f0eb416b5cfdfd777d731f560ec8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "36649929"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a><span data-ttu-id="c4815-103">Microsoft 365 でデータ流出インシデントを管理する</span><span class="sxs-lookup"><span data-stu-id="c4815-103">Manage a data spillage incident in Microsoft 365</span></span>

<span data-ttu-id="c4815-104">データ流出は、機密、機密、または悪意のある情報を含むドキュメントが信頼されていない環境で解放されるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="c4815-104">Data spillage is when a document containing confidential, sensitive, or malicious information is released in an untrusted environment.</span></span> <span data-ttu-id="c4815-105">データ流出インシデントが検出されたら、環境をすばやく格納し、流出のサイズと場所を評価し、その周囲のユーザーアクティビティを調べて、そのサービスからこぼれたデータを削除することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c4815-105">When a data spillage incident is detected, it's important to quickly contain the environment, assess the size and locations of the spillage, examine user activities around it, and then delete the spilled data from the service.</span></span> <span data-ttu-id="c4815-106">データ調査 (プレビュー) ツールを使用すると、Office 365 全体の機密データ、悪意のあるデータ、誤ったデータを検索し、何が起こったかを調べて、適切なアクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="c4815-106">Using the Data Investigations (Preview) tool, you can search for sensitive, malicious, or misplaced data across Office 365, investigate to find out what happened, and then take appropriate actions.</span></span>  

## <a name="scope-of-this-article"></a><span data-ttu-id="c4815-107">この記事の対象範囲</span><span class="sxs-lookup"><span data-stu-id="c4815-107">Scope of this article</span></span>

<span data-ttu-id="c4815-108">この記事では、Office 365 メールボックスからアイテムを完全に削除して、ユーザーまたは管理者がアクセスまたは回復できないようにする手順の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="c4815-108">This article provides a list of instructions on how to permanently delete items from Office 365 mailboxes so they are no longer accessible or recoverable by users or admins.</span></span> 

> [!NOTE]
> <span data-ttu-id="c4815-109">SharePoint または OneDrive for business サイトにあるアイテムを削除すると、元の場所から削除した時点から93日以内に保持されます。</span><span class="sxs-lookup"><span data-stu-id="c4815-109">When you delete items located in a SharePoint or OneDrive for Business site, they are retained for 93 days from the time you delete them from their original location.</span></span>

## <a name="scenario"></a><span data-ttu-id="c4815-110">シナリオ</span><span class="sxs-lookup"><span data-stu-id="c4815-110">Scenario</span></span>

<span data-ttu-id="c4815-111">従業員が知らずに大量の機密ドキュメントを電子メールで共有しているデータ流出インシデントについて通知されています。</span><span class="sxs-lookup"><span data-stu-id="c4815-111">You're informed of a data spillage incident where an employee unknowingly shared a highly confidential document with multiple people through email.</span></span> <span data-ttu-id="c4815-112">組織の内部と外部の両方で、このドキュメントを受信したユーザーをすばやく評価する必要がある。</span><span class="sxs-lookup"><span data-stu-id="c4815-112">You want to quickly assess who received this document, both inside and outside of your organization.</span></span> <span data-ttu-id="c4815-113">インシデントを調査した後は、発見した結果を他の調査担当者と共有して、自分の Office 365 組織からこぼれたデータを完全に削除することを計画します。</span><span class="sxs-lookup"><span data-stu-id="c4815-113">After you've investigate the incident, you plan to share your findings with other investigators to review, and then permanently remove the spilled data from your Office 365 organization.</span></span> <span data-ttu-id="c4815-114">調査が完了したら、すべての証拠を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4815-114">After the investigation is complete, you want to remove all evidence.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c4815-115">自分の組織内でこぼれたデータを完全に削除することはできますが、組織外に含まれるデータは、これらの機能を使用して削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4815-115">While you'll be able to permanently remove the spilled data within your own organization, any data spilled outside your organization can't be removed with these capabilities.</span></span>

## <a name="workflow"></a><span data-ttu-id="c4815-116">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="c4815-116">Workflow</span></span>

<span data-ttu-id="c4815-117">データ調査 (プレビュー) を使用してデータ流出インシデントを管理するためのワークフローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c4815-117">Here's the workflow for using Data Investigations (Preview) to manage a data spillage incident:</span></span>

1.  <span data-ttu-id="c4815-118">データ調査を作成します。</span><span class="sxs-lookup"><span data-stu-id="c4815-118">Create a data investigation.</span></span>

2.  <span data-ttu-id="c4815-119">機密、悪意、または誤ったデータを検索し、証拠として収集します。</span><span class="sxs-lookup"><span data-stu-id="c4815-119">Search for sensitive, malicious, or misplaced data and collect them as evidence.</span></span>

3.  <span data-ttu-id="c4815-120">証拠を確認して調査します。</span><span class="sxs-lookup"><span data-stu-id="c4815-120">Review and investigate the evidence.</span></span>

4.  <span data-ttu-id="c4815-121">こぼれたデータを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="c4815-121">Permanently delete the spilled data.</span></span>

5.  <span data-ttu-id="c4815-122">調査を終了または削除します。</span><span class="sxs-lookup"><span data-stu-id="c4815-122">Close or delete the investigation.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="c4815-123">始める前に</span><span class="sxs-lookup"><span data-stu-id="c4815-123">Before you begin</span></span>

- <span data-ttu-id="c4815-124">データ調査の作成、コンテンツの検索、およびこぼれたデータの削除を行うには、セキュリティ & コンプライアンスセンターのデータ調査者の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4815-124">To create a data investigation, search for content, and delete spilled data, you have to be a member of the Data Investigator role group in the Security & Compliance Center.</span></span>

- <span data-ttu-id="c4815-125">調査担当が検索できるユーザーメールボックスおよび OneDrive アカウントを制御するには、組織でコンプライアンスの境界を設定できます。</span><span class="sxs-lookup"><span data-stu-id="c4815-125">To control which user mailboxes and OneDrive accounts an investigator can search, your organization can set up compliance boundaries.</span></span> <span data-ttu-id="c4815-126">詳細については、[電子情報開示調査のためにコンプライアンスの境界を設定](../set-up-compliance-boundaries.md)します。</span><span class="sxs-lookup"><span data-stu-id="c4815-126">For more information, [Set up compliance boundaries for eDiscovery investigations](../set-up-compliance-boundaries.md).</span></span> 

## <a name="step-1-create-a-data-investigation"></a><span data-ttu-id="c4815-127">手順 1: データ調査を作成する</span><span class="sxs-lookup"><span data-stu-id="c4815-127">Step 1: Create a data investigation</span></span>

<span data-ttu-id="c4815-128">データ調査 (プレビュー) ツールで調査を作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c4815-128">To create an investigation in the Data Investigations (Preview) tool:</span></span>

1. <span data-ttu-id="c4815-129">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4815-129">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c4815-130">データ調査者の役割グループのメンバーであるアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c4815-130">Sign in to Office 365 using an account that is a member of the Data Investigator role group.</span></span>
    
3. <span data-ttu-id="c4815-131">セキュリティ/コンプライアンスセンターで、[**データ調査**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4815-131">In the security and compliance center, click **Data Investigations**.</span></span>
 
4. <span data-ttu-id="c4815-132">[**データ調査 (プレビュー)** ] ページで、[**新しい調査の作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4815-132">On the **Data Investigations (Preview)** page, click **Create new investigation**.</span></span>
    
5. <span data-ttu-id="c4815-133">[**新しいデータ調査**のポップアップ] ページで、調査の名前 (必須) を指定し、オプションの調査番号と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4815-133">On the **New data investigation** flyout page, give the investigation a name (required), and then type an optional investigation number and description.</span></span> <span data-ttu-id="c4815-134">この名前は、組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4815-134">The name must be unique in your organization.</span></span>

6. <span data-ttu-id="c4815-135">[**この調査を作成した後、追加の設定を構成しますか?**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c4815-135">Under **Do you want to configure additional settings after creating this investigation?**, do one of the following:</span></span>

    - <span data-ttu-id="c4815-136">[**はい**] をクリックして調査を作成し、新しいケースで [**設定**] ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="c4815-136">Click **Yes** to create the investigation, and display the **Settings** page in the new case.</span></span> <span data-ttu-id="c4815-137">これにより、調査にメンバーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c4815-137">This allows you to add members to the investigation.</span></span>
    
    - <span data-ttu-id="c4815-138">調査を作成して [**データ調査 (プレビュー)** ] ページのケースの一覧に表示するには、[**いいえ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4815-138">Click **No** to create the investigation and display it in the list of cases on the **Data Investigations (Preview)** page.</span></span> <span data-ttu-id="c4815-139">このオプションを選択すると、調査の唯一のメンバーとして追加され、既定の検索と分析の設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4815-139">If you choose this option, you will be added as the only member of the investigation and the default search and analytics settings will be used.</span></span> <span data-ttu-id="c4815-140">調査が作成されたらいつでもメンバーを追加したり、設定を変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="c4815-140">You can add members or change settings anytime after the investigation is created.</span></span>

7. <span data-ttu-id="c4815-141">[**保存**] をクリックして、調査を作成します。</span><span class="sxs-lookup"><span data-stu-id="c4815-141">Click **Save** to create the investigation.</span></span>

    <span data-ttu-id="c4815-142">新しい調査は、[**データ調査 (プレビュー)** ] ページの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4815-142">The new investigation is displayed in the list on the **Data Investigations (Preview)** page.</span></span> 

8. <span data-ttu-id="c4815-143">調査を開くには、調査の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4815-143">To open an investigation, click the name of the investigation.</span></span> 

    <span data-ttu-id="c4815-144">調査の [**ホーム**] タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4815-144">The **Home** tab for the investigation is displayed.</span></span> 

> [!TIP]
> <span data-ttu-id="c4815-145">調査の名前付け規則を確立し、必要に応じて後で検索して参照できるように、名前と説明に記載されている限り多くの情報を提供することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c4815-145">Consider establishing a naming convention for investigations and provide as much information as you can in the name and description so you can locate and refer to them in the future if necessary.</span></span>
 
## <a name="step-2-search-for-the-spilled-data"></a><span data-ttu-id="c4815-146">手順 2: こぼれたデータを検索する</span><span class="sxs-lookup"><span data-stu-id="c4815-146">Step 2: Search for the spilled data</span></span> 
 
<span data-ttu-id="c4815-147">保存されていないデータを検索するユーザーがわかっている場合は、それらを関心のあるユーザーとして追加し、データソースを調査にマップして、自分のメールボックスと OneDrive アカウントをすばやく検索することができます。</span><span class="sxs-lookup"><span data-stu-id="c4815-147">If you know which users you want to search for spilled data, you can add them as people of interest to map their data sources to the investigation and quickly search their mailbox and OneDrive account.</span></span> <span data-ttu-id="c4815-148">調査対象のユーザーを追加するには、[**関心**のある人] をクリックし、[**関心のある**人を追加する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4815-148">To add people of interest to the investigation, click **People of interest**, and then click **Add people of interest**.</span></span> <span data-ttu-id="c4815-149">詳細については、「[関心のある人を管理](manage-people-of-interest.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4815-149">For more information, see [Manage people of interest](manage-people-of-interest.md).</span></span>

<span data-ttu-id="c4815-150">[**検索**] タブでは、検索を作成して、こぼれたデータを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="c4815-150">On the **Searches** tab, you can create searches to find the spilled data.</span></span> <span data-ttu-id="c4815-151">検索を作成する方法の詳細については、「[調査時にデータを検索](search-for-data.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4815-151">For more information about creating searches, see [Search for data in an investigation](search-for-data.md).</span></span>

<span data-ttu-id="c4815-152">検索を実行した後、検索結果のサンプルをプレビューし、検索の統計を表示して、検索クエリの効果を評価できます。</span><span class="sxs-lookup"><span data-stu-id="c4815-152">After you run the search, you can preview samples of search results and view search statistics to evaluate the effectiveness of your search query.</span></span> <span data-ttu-id="c4815-153">Office 365 から削除するアイテムを特定した後、検索結果を証拠セットに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c4815-153">After you identify the items that you want to delete from Office 365, you can add the search results to an evidence set.</span></span> <span data-ttu-id="c4815-154">これを行うには、調査する検索をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4815-154">To do this, click the search that you want to investigate.</span></span> <span data-ttu-id="c4815-155">[ポップアップ] ページで、[**結果を証拠に追加**] をクリックし、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="c4815-155">On the flyout page, click **Add results to evidence** and follow the instructions.</span></span> <span data-ttu-id="c4815-156">次に、証拠セットで、個々のドキュメントの確認、ドキュメントへのアクセス権を持っているユーザーの調査、ドキュメントのエクスポートを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c4815-156">Then in the evidence set, you can review individual documents, investigate who had access to documents, and export the documents.</span></span> <span data-ttu-id="c4815-157">ドキュメント (またはドキュメントのサブセット) を確認するのではなく削除するには、[手順 4](#step-4-delete-the-spilled-data)に進みます。</span><span class="sxs-lookup"><span data-stu-id="c4815-157">To delete the documents (or a subset of documents) instead of reviewing them, go to [Step 4](#step-4-delete-the-spilled-data).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c4815-158">検索クエリで使用するキーワードには、検索している実際のこぼれたデータが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="c4815-158">The keywords that you use in the search query may contain the actual spilled data that you're searching for.</span></span> <span data-ttu-id="c4815-159">たとえば、社会保障番号を含むドキュメントを検索し、検索クエリでキーワードとして使用する場合は、さらに流出を回避するために、後でクエリを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4815-159">For example, if you search for documents containing a social security number and you use it as a keyword in the search query, you must delete the query afterwards to avoid further spillage.</span></span> <span data-ttu-id="c4815-160">[手順 5](#step-5-close-or-delete-the-investigation)では、検索を削除するか、調査全体を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c4815-160">You can delete the search or delete the entire investigation in [Step 5](#step-5-close-or-delete-the-investigation).</span></span> 

## <a name="step-3-review-and-investigate"></a><span data-ttu-id="c4815-161">手順 3: レビューと調査</span><span class="sxs-lookup"><span data-stu-id="c4815-161">Step 3: Review and investigate</span></span> 

<span data-ttu-id="c4815-162">調査中に、[**エビデンス**] タブに移動し、前の手順で作成した証拠セットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4815-162">In the investigation, go to the **Evidence** tab and click the evidence set that you created in the previous step.</span></span> <span data-ttu-id="c4815-163">処理ジョブが完了し、検索結果が証拠に追加されると、個々のドキュメントをネイティブ形式、テキスト形式、またはほぼネイティブ形式で確認できます。</span><span class="sxs-lookup"><span data-stu-id="c4815-163">After the processing job is completed and the search results are added to the evidence, you can review individual documents in their native format, text format, or a near-native format.</span></span> <span data-ttu-id="c4815-164">追加のクエリを作成してドキュメントの一覧を絞り込んだり、調査結果を示すためにドキュメントにタグを付けたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4815-164">You can create additional queries to narrow the list of documents, and tag documents to indicate findings from your investigation.</span></span> <span data-ttu-id="c4815-165">詳細については、「[証拠データのレビュー](review-data-in-evidence.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4815-165">For more information, see [Review data in evidence](review-data-in-evidence.md)</span></span>

<span data-ttu-id="c4815-166">ドキュメントをグループ化して、レビューのための詳細を取得するには、[**証明の管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4815-166">To group documents and get more assistance for your review, click **Manage evidence**.</span></span> <span data-ttu-id="c4815-167">[**分析**] タイルで、[**分析**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4815-167">In the **Analytics** tile, click **Analyze**.</span></span> <span data-ttu-id="c4815-168">これにより、重複データ検出、電子メールスレッド、テーマ分析などの高度な分析が実行されます。</span><span class="sxs-lookup"><span data-stu-id="c4815-168">This runs advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="c4815-169">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4815-169">For more information, see:</span></span>

- [<span data-ttu-id="c4815-170">アナリティクスを使って、調査をより速く行います</span><span class="sxs-lookup"><span data-stu-id="c4815-170">Run analytics to investigate faster</span></span>](run-analytics-to-investigate-faster.md)
- [<span data-ttu-id="c4815-171">準重複の検出</span><span class="sxs-lookup"><span data-stu-id="c4815-171">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="c4815-172">電子メールのスレッド化</span><span class="sxs-lookup"><span data-stu-id="c4815-172">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="c4815-173">テーマ</span><span class="sxs-lookup"><span data-stu-id="c4815-173">Themes</span></span>](themes.md)

<span data-ttu-id="c4815-174">データ流出に関係しているユーザーを特定するには、証拠セット内にクエリを作成してから送信者/作成者と受信者の条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4815-174">To determine which users are involved in the data spillage, you can create a query in the evidence set and then use the Sender/Author and Recipients conditions.</span></span> <span data-ttu-id="c4815-175">これにより、証拠に追加された収集データに含まれるすべての送信者、受信者、および作成者の一覧が作成されます。</span><span class="sxs-lookup"><span data-stu-id="c4815-175">This creates a list of all senders, recipients, and authors found in collected data that was added to the evidence.</span></span> <span data-ttu-id="c4815-176">リストを調べて、外部ユーザーがいるかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c4815-176">Be sure to examine the list to determine if there are any external users.</span></span> <span data-ttu-id="c4815-177">条件を使用して検索結果を絞り込む方法の詳細については、「[検索条件](../keyword-queries-and-search-conditions.md#search-conditions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4815-177">For more information about using conditions to narrow search results, see [Search conditions](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>

## <a name="step-4-delete-the-spilled-data"></a><span data-ttu-id="c4815-178">手順 4: こぼれたデータを削除する</span><span class="sxs-lookup"><span data-stu-id="c4815-178">Step 4: Delete the spilled data</span></span>

<span data-ttu-id="c4815-179">データ調査ツールを使用して、元の場所からアイテムを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c4815-179">Using the data investigations tool, you can delete items from their original locations.</span></span> <span data-ttu-id="c4815-180">たとえば、組織全体のメールボックス、SharePoint サイト、および OneDrive アカウントからアイテムを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c4815-180">For example, you can delete items from mailboxes, SharePoint sites, and OneDrive accounts across your organization.</span></span> <span data-ttu-id="c4815-181">アイテムを証拠として収集したため (手順2で検索結果を証拠セットに追加することで)、証拠セット内のアイテムのコピーをさらに調査または保存することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c4815-181">Keep in mind that because you collected items as evidence (by adding the search results to the evidence set in Step 2), you have copies of the items in the evidence set to further investigate or preserve them.</span></span>

<span data-ttu-id="c4815-182">アイテムを元の場所から削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c4815-182">To delete items from their original locations:</span></span>

1. <span data-ttu-id="c4815-183">[証拠セット] で、削除するアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="c4815-183">In the evidence set, select the items that you want to delete.</span></span> <span data-ttu-id="c4815-184">電子メールメッセージに添付されているアイテムを選択すると、親の電子メールメッセージも選択され、削除されます。</span><span class="sxs-lookup"><span data-stu-id="c4815-184">If you select items that are attached to an email message, the parent email message will also be selected and deleted.</span></span> 
 
2. <span data-ttu-id="c4815-185">[**アクション**] をクリックし、[**元の場所からアイテムを削除**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4815-185">Click **Action** and then click **Delete items from original locations**.</span></span>

   ![[アクション] をクリックし、[元の場所からアイテムを削除する] をクリックします。](../media/DataInvestigationsDeleteItems1.png)

3. <span data-ttu-id="c4815-187">[ポップアップ] ページで、削除されるアイテムと関連する子ドキュメントの数を確認し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4815-187">On the flyout page, verify the number of items and related child documents that will be deleted, and then click **Delete**.</span></span>

<span data-ttu-id="c4815-188">この時点で、アイテムを元の場所から削除すると、アイテムはソフト削除されます。</span><span class="sxs-lookup"><span data-stu-id="c4815-188">At this time, when you delete items from their original location, the items are soft-deleted.</span></span> <span data-ttu-id="c4815-189">これは、アイテムの削除済みアイテムの復元期間が経過するまで、削除されたアイテムが保持されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c4815-189">This means that the deleted items will be retained until the deleted item recovery period for the item expires.</span></span> <span data-ttu-id="c4815-190">これは、ユーザーがこれらのアイテムを回復できることも意味します。</span><span class="sxs-lookup"><span data-stu-id="c4815-190">This also means it's possible for users to recover these items.</span></span> <span data-ttu-id="c4815-191">メールボックスおよびサイトからアイテムが削除されたときの処理の詳細については、「[元の場所からアイテムを削除](delete-items-from-original-locations.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4815-191">For more information about what happens when items are deleted from mailboxes and sites, see [Delete items from their original location](delete-items-from-original-locations.md).</span></span>

## <a name="step-5-close-or-delete-the-investigation"></a><span data-ttu-id="c4815-192">手順 5: 調査を終了または削除する</span><span class="sxs-lookup"><span data-stu-id="c4815-192">Step 5: Close or delete the investigation</span></span>

<span data-ttu-id="c4815-193">運用サービスのソースコンテンツの場所 (メールボックスまたはサイト) 内のドキュメントを削除した後も、調査の一環としてエビデンスに追加したこれらのドキュメントのコピーが残ります。</span><span class="sxs-lookup"><span data-stu-id="c4815-193">After you delete documents in the source content locations (mailboxes or sites) in the live service, you will still have copies of these documents that you added to evidence as part of your investigation.</span></span> <span data-ttu-id="c4815-194">その他のデータ流出を回避するには、調査自体を削除することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4815-194">To avoid further data spillage, you should consider deleting the investigation itself.</span></span>

<span data-ttu-id="c4815-195">調査を削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c4815-195">To delete an investigation:</span></span>

1. <span data-ttu-id="c4815-196">[**設定**] タブで、[**調査情報**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4815-196">On the **Settings** tab, click **Investigation information**.</span></span>

2. <span data-ttu-id="c4815-197">[**調査の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4815-197">Click  **Delete investigation**.</span></span> 

<span data-ttu-id="c4815-198">調査を削除する必要がない場合や、調査時に収集した情報を保存する場合は、[case を**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4815-198">If you don't need to delete the investigation or if you want to save the information that you collected during the investigation, you can click **Close case**.</span></span> <span data-ttu-id="c4815-199">その後、クローズした調査を再度開くことができます。</span><span class="sxs-lookup"><span data-stu-id="c4815-199">Then later, you can reopen closed investigations.</span></span>
