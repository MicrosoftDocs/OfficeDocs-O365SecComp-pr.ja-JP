---
title: Microsoft 365 でデータ流出インシデントを管理する
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
description: この記事では、Security & コンプライアンスセンターで新しいデータ調査 (プレビュー) ツールを使用してデータ流出インシデントを管理する方法について説明します。
ms.openlocfilehash: 7aada296566bb5312ab56680485798323d0ab096
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150749"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a><span data-ttu-id="8a851-103">Microsoft 365 でデータ流出インシデントを管理する</span><span class="sxs-lookup"><span data-stu-id="8a851-103">Manage a data spillage incident in Microsoft 365</span></span>

<span data-ttu-id="8a851-104">Data 流出は、機密情報を含むドキュメントが信頼されていない環境に解放されるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="8a851-104">Data spillage is when a document containing confidential, sensitive or malicious information is released into an untrusted environment.</span></span> <span data-ttu-id="8a851-105">データ流出インシデントが検出されたら、環境をすばやく格納し、流出のサイズと場所を評価し、その周囲のユーザーアクティビティを調べて、そのサービスからこぼれたデータを削除することが重要です。</span><span class="sxs-lookup"><span data-stu-id="8a851-105">When a data spillage incident is detected, it's important to quickly contain the environment, assess the size and locations of the spillage, examine user activities around it, and then delete the spilled data from the service.</span></span> <span data-ttu-id="8a851-106">データ調査 (プレビュー) ツールを使用すると、Office 365 全体の機密データや不適切なデータを検索し、何が起こったかを調べて、適切な操作を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8a851-106">Using the Data Investigations (Preview) tool, you can search for sensitive, malicious or misplaced data across Office 365, investigate to find out what happened, and then take appropriate actions.</span></span>  

## <a name="scope-of-this-article"></a><span data-ttu-id="8a851-107">この記事の対象範囲</span><span class="sxs-lookup"><span data-stu-id="8a851-107">Scope of this article</span></span>

<span data-ttu-id="8a851-108">この記事では、Office 365 メールボックスからアイテムを完全に削除して、ユーザーまたは管理者がアクセスまたは回復できないようにする手順の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="8a851-108">This article provides a list of instructions on how to permanently delete items from Office 365 mailboxes so they are no longer accessible or recoverable by users or admins.</span></span> 

> [!NOTE]
> <span data-ttu-id="8a851-109">SharePoint または OneDrive for business サイトにあるアイテムを削除すると、元の場所から削除した時点から93日以内に保持されます。</span><span class="sxs-lookup"><span data-stu-id="8a851-109">When you delete items located in a SharePoint or OneDrive for Business site, they are retained for 93 days from the time you delete them from their original location.</span></span>

## <a name="scenario"></a><span data-ttu-id="8a851-110">シナリオ</span><span class="sxs-lookup"><span data-stu-id="8a851-110">Scenario</span></span>

<span data-ttu-id="8a851-111">従業員が知らずに大量の機密ドキュメントを電子メールで共有しているデータ流出インシデントについて通知されています。</span><span class="sxs-lookup"><span data-stu-id="8a851-111">You're informed of a data spillage incident where an employee unknowingly shared a highly-confidential document with multiple people through email.</span></span> <span data-ttu-id="8a851-112">組織の内部と外部の両方で、このドキュメントを受信したユーザーをすばやく評価する必要がある。</span><span class="sxs-lookup"><span data-stu-id="8a851-112">You want to quickly assess who received this document, both inside and outside of your organization.</span></span> <span data-ttu-id="8a851-113">インシデントを調査した後は、発見した結果を他の調査担当者と共有して、自分の Office 365 組織からこぼれたデータを完全に削除することを計画します。</span><span class="sxs-lookup"><span data-stu-id="8a851-113">After you've investigate the incident, you plan to share your findings with other investigators to review, and then permanently remove the spilled data from your Office 365 organization.</span></span> <span data-ttu-id="8a851-114">調査が完了したら、すべての証拠を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a851-114">After the investigation is complete, you want to remove all evidence.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8a851-115">自分の組織内でこぼれたデータを完全に削除することはできますが、組織外に含まれるデータは、これらの機能を使用して削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="8a851-115">While you'll be able to permanently remove the spilled data within your own organization, any data spilled outside your organization can't be removed with these capabilities.</span></span>

## <a name="workflow"></a><span data-ttu-id="8a851-116">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="8a851-116">Workflow</span></span>

<span data-ttu-id="8a851-117">データ調査 (プレビュー) を使用してデータ流出インシデントを管理するためのワークフローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8a851-117">Here's the workflow for using Data Investigations (Preview) to manage a data spillage incident:</span></span>

1.  <span data-ttu-id="8a851-118">データ調査を作成します。</span><span class="sxs-lookup"><span data-stu-id="8a851-118">Create a data investigation.</span></span>

2.  <span data-ttu-id="8a851-119">機密、悪意、または誤ったデータを検索し、証拠として収集します。</span><span class="sxs-lookup"><span data-stu-id="8a851-119">Search for sensitive, malicious, or misplaced data and collect them as evidence.</span></span>

3.  <span data-ttu-id="8a851-120">証拠を確認して調査します。</span><span class="sxs-lookup"><span data-stu-id="8a851-120">Review and investigate the evidence.</span></span>

4.  <span data-ttu-id="8a851-121">こぼれたデータを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="8a851-121">Permanently delete the spilled data.</span></span>

5.  <span data-ttu-id="8a851-122">調査を終了または削除します。</span><span class="sxs-lookup"><span data-stu-id="8a851-122">Close or delete the investigation.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="8a851-123">始める前に</span><span class="sxs-lookup"><span data-stu-id="8a851-123">Before you begin</span></span>

- <span data-ttu-id="8a851-124">セキュリティ & コンプライアンスセンターのデータ調査 (プレビュー) ツールを使用して、調査を作成し、こぼれたデータを検索して、それを確認して分析します。</span><span class="sxs-lookup"><span data-stu-id="8a851-124">You'll use the Data Investigations (Preview) tool in the Security & Compliance Center to create an investigation, search for the spilled data, and review and analyze it.</span></span> <span data-ttu-id="8a851-125">その後、セキュリティ & コンプライアンスセンター PowerShell を使用して、Office 365 からこぼれたデータを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="8a851-125">Then you'll use Security & Compliance Center PowerShell to permanently delete the spilled data from Office 365.</span></span> 

- <span data-ttu-id="8a851-126">調査を作成するには、セキュリティ & コンプライアンスセンターのコンプライアンス管理者役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a851-126">To create an investigation, you have to be a member of the Compliance Administrator role group in the Security & Compliance Center.</span></span>

- <span data-ttu-id="8a851-127">メッセージを削除するには、検索と削除の役割が割り当てられているセキュリティ & コンプライアンスセンターの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a851-127">To delete messages, you have to be a member of a role group in the Security & Compliance Center that's assigned the Search and Purge role.</span></span> <span data-ttu-id="8a851-128">既定では、この役割は組織の管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8a851-128">By default, this role is assigned to the Organization Management role group.</span></span> <span data-ttu-id="8a851-129">ユーザーを役割グループに追加する方法については、「 [Security _AMP_ コンプライアンスセンターのアクセス許可](../permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a851-129">For information about adding users to a role group, see [Permissions in the Security & Compliance Center](../permissions-in-the-security-and-compliance-center.md).</span></span> 

- <span data-ttu-id="8a851-130">調査担当が検索できるユーザーメールボックスおよび OneDrive アカウントを制御するには、組織でコンプライアンスの境界を設定できます。</span><span class="sxs-lookup"><span data-stu-id="8a851-130">To control which user mailboxes and OneDrive accounts an investigator can search, your organization can set up compliance boundaries.</span></span> <span data-ttu-id="8a851-131">詳細については、[電子情報開示調査のためにコンプライアンスの境界を設定](../set-up-compliance-boundaries.md)します。</span><span class="sxs-lookup"><span data-stu-id="8a851-131">For more information, [Set up compliance boundaries for eDiscovery investigations](../set-up-compliance-boundaries.md).</span></span> 

## <a name="step-1-create-a-data-investigation"></a><span data-ttu-id="8a851-132">手順 1: データ調査を作成する</span><span class="sxs-lookup"><span data-stu-id="8a851-132">Step 1: Create a data investigation</span></span>

<span data-ttu-id="8a851-133">データ調査 (プレビュー) ツールで調査を作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8a851-133">To create an investigation in the Data Investigations (Preview) tool:</span></span>

1. <span data-ttu-id="8a851-134">[https://compliance.microsoft.com](https://compliance.microsoft.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="8a851-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com).</span></span>
    
2. <span data-ttu-id="8a851-135">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8a851-135">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="8a851-136">[コンプライアンスセンター] で、[**データ調査**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a851-136">In the compliance center, click **Data Investigations**.</span></span>
 
4. <span data-ttu-id="8a851-137">[**データ調査 (プレビュー)** ] ページで、[**新しい調査の作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a851-137">On the **Data Investigations (Preview)** page, click **Create new investigation**.</span></span>
    
5. <span data-ttu-id="8a851-138">[**新しいデータ調査**のポップアップ] ページで、調査の名前 (必須) を指定し、オプションの調査番号と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="8a851-138">On the **New data investigation** flyout page, give the investigation a name (required), and then type an optional investigation number and description.</span></span> <span data-ttu-id="8a851-139">この名前は、組織内で一意である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8a851-139">Note that the name must be unique in your organization.</span></span>

6. <span data-ttu-id="8a851-140">[**この調査を作成した後、追加の設定を構成しますか?**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8a851-140">Under **Do you want to configure additional settings after creating this investigation?**, do one of the following:</span></span>

    - <span data-ttu-id="8a851-141">[**はい**] をクリックして調査を作成し、新しいケースで [**設定**] ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="8a851-141">Click **Yes** to create the investigation, and display the **Settings** page in the new case.</span></span> <span data-ttu-id="8a851-142">これにより、調査にメンバーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="8a851-142">This allows you to add members to the investigation.</span></span>
    
    - <span data-ttu-id="8a851-143">[**いいえ**] をクリックすると、調査が作成され、[**データ調査 (プレビュー)** ] ページのケースの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a851-143">Click **No** to just create the investigation and display it in the list of cases on the **Data Investigations (Preview)** page.</span></span> <span data-ttu-id="8a851-144">このオプションを選択すると、調査の唯一のメンバーとして追加され、既定の検索と分析の設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a851-144">If you choose this option, you will be added as the only member of the investigation and the default search and analytics settings will be used.</span></span> <span data-ttu-id="8a851-145">調査が作成されたらいつでもメンバーを追加したり、設定を変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="8a851-145">You can add members or change settings any time after the investigation is created.</span></span>

7. <span data-ttu-id="8a851-146">[**保存**] をクリックして、調査を作成します。</span><span class="sxs-lookup"><span data-stu-id="8a851-146">Click **Save** to create the investigation.</span></span>

    <span data-ttu-id="8a851-147">新しい調査は、[**データ調査 (プレビュー)** ] ページの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a851-147">The new investigation is displayed in the list on the **Data Investigations (Preview)** page.</span></span> 

8. <span data-ttu-id="8a851-148">調査を開くには、調査の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a851-148">To open an investigation, click the name of the investigation.</span></span> 

    <span data-ttu-id="8a851-149">調査の [**ホーム**] タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a851-149">The **Home** tab for the investigation is displayed.</span></span> 

> [!TIP]
> <span data-ttu-id="8a851-150">調査の名前付け規則を確立し、必要に応じて後で検索して参照できるように、名前と説明に記載されている限り多くの情報を提供することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="8a851-150">Consider establishing a naming convention for investigations and provide as much information as you can in the name and description so you can locate and refer to in the future if necessary.</span></span>
 
## <a name="step-2-search-for-the-spilled-data"></a><span data-ttu-id="8a851-151">手順 2: こぼれたデータを検索する</span><span class="sxs-lookup"><span data-stu-id="8a851-151">Step 2: Search for the spilled data</span></span> 
 
<span data-ttu-id="8a851-152">保存されていないデータを検索するユーザーがわかっている場合は、それらを関心のあるユーザーとして追加し、データソースを調査にマップして、自分のメールボックスと OneDrive アカウントをすばやく検索することができます。</span><span class="sxs-lookup"><span data-stu-id="8a851-152">If you know which users you want to search for spilled data, you can add them as people of interest to map their data sources to the investigation and quickly search their mailbox and OneDrive account.</span></span> <span data-ttu-id="8a851-153">調査対象のユーザーを追加するには、[**関心**のある人] をクリックし、[**関心のある**人を追加する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a851-153">To add people of interest to the investigation, click **People of interest**, and then click **Add people of interest**.</span></span> <span data-ttu-id="8a851-154">詳細については、「[関心のある人を管理](manage-people-of-interest.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a851-154">For more information, see [Manage people of interest](manage-people-of-interest.md).</span></span>

<span data-ttu-id="8a851-155">[**検索**] タブでは、検索を作成して、こぼれたデータを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="8a851-155">On the **Searches** tab, you can create searches to find the spilled data.</span></span> <span data-ttu-id="8a851-156">[手順 4](#step-4-delete-the-spilled-data)で同じメッセージを削除するために使用したものと同じ検索クエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="8a851-156">You will use the same search query that you used to find the spilled data to delete those same messages in [Step 4](#step-4-delete-the-spilled-data).</span></span> <span data-ttu-id="8a851-157">検索を作成する方法の詳細については、「[調査時にデータを検索](search-for-data.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a851-157">For more information about creating searches, see [Search for data in an investigation](search-for-data.md).</span></span>

<span data-ttu-id="8a851-158">検索を実行した後、検索結果のサンプルをプレビューし、検索の統計を表示して、検索クエリの効果を評価できます。</span><span class="sxs-lookup"><span data-stu-id="8a851-158">After you run the search, you can preview samples of search results and view search statistics to evaluate the effectiveness of your search query.</span></span> <span data-ttu-id="8a851-159">Office 365 から削除するアイテムを特定した後、[**エビデンス**] タブをクリックし、証拠セットを作成して、そのアイテムを含む検索結果を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="8a851-159">Once you identify the items that you want to delete from Office 365, you can click the **Evidence** tab, and then create an evidence set and add search results that contain those items.</span></span> 

<span data-ttu-id="8a851-160">これを行うには、調査する検索をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a851-160">To do this, click the search that you want to investigate.</span></span> <span data-ttu-id="8a851-161">[ポップアップ] ページで、[**結果を証拠に追加**] をクリックし、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="8a851-161">On the flyout page, click **Add results to evidence** and follow the instructions.</span></span> <span data-ttu-id="8a851-162">この証拠で、個々のドキュメントの確認、ドキュメントへのアクセス権を持っているユーザーの調査、ドキュメントのエクスポートを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8a851-162">Then in the evidence, you can review individual documents, investigate who had access to documents, and export the documents.</span></span> <span data-ttu-id="8a851-163">ドキュメントを確認するのではなく、単に削除するには、[手順 4](#step-4-delete-the-spilled-data)に進みます。</span><span class="sxs-lookup"><span data-stu-id="8a851-163">To simply delete the documents instead of reviewing them, go to [Step 4](#step-4-delete-the-spilled-data).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8a851-164">検索クエリで使用するキーワードには、検索している実際のこぼれたデータが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="8a851-164">The keywords that you use in the search query may contain the actual spilled data that you're searching for.</span></span> <span data-ttu-id="8a851-165">たとえば、社会保障番号を含むドキュメントを検索し、検索クエリでキーワードとして使用する場合は、さらに流出を回避するために、後でクエリを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a851-165">For example, if you search for documents containing a social security number and you use it as a keyword in the search query, you must delete the query afterwards to avoid further spillage.</span></span> <span data-ttu-id="8a851-166">[手順 5](#step-5-close-or-delete-the-investigation)では、検索を削除するか、調査全体を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="8a851-166">You can delete the search or delete the entire investigation in [Step 5](#step-5-close-or-delete-the-investigation).</span></span> 

## <a name="step-3-review-and-investigate"></a><span data-ttu-id="8a851-167">手順 3: レビューと調査</span><span class="sxs-lookup"><span data-stu-id="8a851-167">Step 3: Review and investigate</span></span> 

<span data-ttu-id="8a851-168">調査中に、[**エビデンス**] タブに移動し、前の手順で作成した証拠セットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a851-168">In the investigation, go to **Evidence** tab and click on the evidence set that you created in the previous step.</span></span> <span data-ttu-id="8a851-169">処理ジョブが完了し、検索結果が証拠に追加されると、個々のドキュメントをネイティブ形式、テキスト形式、またはほぼネイティブ形式で確認できます。</span><span class="sxs-lookup"><span data-stu-id="8a851-169">After the processing job is completed and the search results are added to the evidence, you can review individual documents in their native format, text format, or a near-native format.</span></span> <span data-ttu-id="8a851-170">追加のクエリを作成してドキュメントの一覧を絞り込んだり、調査結果を示すためにドキュメントにタグを付けたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="8a851-170">You can create additional queries to narrow the list of documents, and tag documents to indicate findings from your investigation.</span></span> <span data-ttu-id="8a851-171">詳細については、「[証拠データのレビュー](review-data-in-evidence.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a851-171">For more information, see [Review data in evidence](review-data-in-evidence.md)</span></span>

<span data-ttu-id="8a851-172">ドキュメントをグループ化して、レビューのための詳細を取得するには、[**証明の管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a851-172">To group documents and get more assistance for your review, click **Manage evidence**.</span></span> <span data-ttu-id="8a851-173">[**分析**] タイルで、[**分析**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a851-173">In the **Analytics** tile, click **Analyze**.</span></span> <span data-ttu-id="8a851-174">これにより、重複データ検出、電子メールスレッド、テーマ分析などの高度な分析が実行されます。</span><span class="sxs-lookup"><span data-stu-id="8a851-174">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="8a851-175">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a851-175">For more information, see:</span></span>

- [<span data-ttu-id="8a851-176">アナリティクスを使って、調査をより速く行います</span><span class="sxs-lookup"><span data-stu-id="8a851-176">Run analytics to investigate faster</span></span>](run-analytics-to-investigate-faster.md)
- [<span data-ttu-id="8a851-177">準重複の検出</span><span class="sxs-lookup"><span data-stu-id="8a851-177">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="8a851-178">電子メールのスレッド化</span><span class="sxs-lookup"><span data-stu-id="8a851-178">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="8a851-179">テーマ</span><span class="sxs-lookup"><span data-stu-id="8a851-179">Themes</span></span>](themes.md)

<span data-ttu-id="8a851-180">どのユーザーがデータ流出に関係しているかを確認するには、証拠セットに新しいクエリを作成し、送信者/作成者と受信者の条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="8a851-180">To determine which users are involved in the data spillage, you can create a new query in the evidence set and then use the Sender/Author and Recipients conditions.</span></span> <span data-ttu-id="8a851-181">これにより、証拠に追加された収集データに含まれるすべての送信者、受信者、および作成者の一覧が作成されます。</span><span class="sxs-lookup"><span data-stu-id="8a851-181">This will create a list of all senders, recipients, and authors found in collected data that was added to the evidence.</span></span> <span data-ttu-id="8a851-182">リストを調べて、外部ユーザーがいるかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8a851-182">Be sure to examine the list to determine if there are any external users.</span></span> <span data-ttu-id="8a851-183">条件を使用して検索結果を絞り込む方法の詳細については、「[検索条件](../keyword-queries-and-search-conditions.md#search-conditions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a851-183">For more information about using conditions to narrow search results, see [Search conditions](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>

## <a name="step-4-delete-the-spilled-data"></a><span data-ttu-id="8a851-184">手順 4: こぼれたデータを削除する</span><span class="sxs-lookup"><span data-stu-id="8a851-184">Step 4: Delete the spilled data</span></span>

### <a name="deleting-mailbox-items"></a><span data-ttu-id="8a851-185">メールボックスアイテムの削除</span><span class="sxs-lookup"><span data-stu-id="8a851-185">Deleting mailbox items</span></span>

<span data-ttu-id="8a851-186">削除が必要な電子メールメッセージのみが検索結果に含まれていることを確認して検証した後、セキュリティ & コンプライアンスで**new-compliancesearchaction-PurgeType ハード削除**コマンドを実行して、それらを完全に削除することができます。Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a851-186">After you review and validate that the search results contain only the email messages that must be deleted, you can permanently delete them by running the **New-ComplianceSearchAction -Purge -PurgeType HardDelete** command in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="8a851-187">手順については、「[メールメッセージの検索と削除](../search-for-and-delete-messages-in-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a851-187">For instructions, see [Search for and delete email messages](../search-for-and-delete-messages-in-your-organization.md).</span></span> 

<span data-ttu-id="8a851-188">組織内のメールボックスに対して単一アイテムの回復が有効になっている場合は、削除済みアイテムの保存期間が終了するまで、完全に削除されたアイテムがユーザーの回復可能なアイテムフォルダーに保持され (管理者がアクセス可能) ます。</span><span class="sxs-lookup"><span data-stu-id="8a851-188">If single item recovery is enabled for mailboxes in your organization, permanently deleted items will be retained in the user's Recoverable items folder (and accessible by admins) until the deleted item retention period ends (the default is 14 days).</span></span> <span data-ttu-id="8a851-189">また、追加されたデータを含むメールボックスが法的情報保留になっているか、またはアイテム保持ポリシーに割り当てられている場合、削除されたメッセージは、アイテムの保持期間が切れるまで、回復可能なアイテムフォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="8a851-189">Additionally, if any mailbox that contains spilled data is on a legal hold or assigned to a retention policy, purged messages will be retained in the Recoverable items folder until the hold duration for the item expires.</span></span> <span data-ttu-id="8a851-190">メッセージを直ちにハード削除するには、追加タスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a851-190">To hard delete messages immediately, you need to perform addition tasks.</span></span> <span data-ttu-id="8a851-191">手順については、「[保持中のクラウドベースのメールボックスの回復可能なアイテムフォルダーのアイテムを削除する](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a851-191">For instructions, see [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md).</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="8a851-192">保留またはアイテム保持ポリシーを削除する前に、レコード管理または法務部門に確認してください。</span><span class="sxs-lookup"><span data-stu-id="8a851-192">Check with your records management or legal departments before removing a hold or retention policy.</span></span> <span data-ttu-id="8a851-193">組織には、保留中のメールボックスとデータ流出インシデントのどちらを優先するかを定義するポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="8a851-193">Your organization may have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 

### <a name="deleting-site-items"></a><span data-ttu-id="8a851-194">サイトアイテムの削除</span><span class="sxs-lookup"><span data-stu-id="8a851-194">Deleting site items</span></span>

<span data-ttu-id="8a851-195">SharePoint サイトまたは OneDrive アカウントからドキュメントを完全に削除するには、そのドキュメントを削除してから、サイトコレクションのごみ箱から削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a851-195">To permanently delete a document from a SharePoint site or OneDrive account, you have to delete the document and then you have to delete from the site Recycle Bin and then delete it from the site collection Recycle Bin.</span></span> <span data-ttu-id="8a851-196">詳細については、「 [SharePoint および OneDrive でドキュメントを削除](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a851-196">For more information, see [Delete documents in SharePoint and OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business).</span></span>

<span data-ttu-id="8a851-197">また、必要なデータが含まれていたサイトコレクション全体を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="8a851-197">Alternatively, you can delete an entire site collection that might contained spilled data.</span></span> <span data-ttu-id="8a851-198">手順については、「[サイトコレクションを削除する](https://docs.microsoft.com/sharepoint/delete-site-collection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a851-198">For instructions, see [Delete a site collection](https://docs.microsoft.com/sharepoint/delete-site-collection).</span></span>

## <a name="step-5-close-or-delete-the-investigation"></a><span data-ttu-id="8a851-199">手順 5: 調査を終了または削除する</span><span class="sxs-lookup"><span data-stu-id="8a851-199">Step 5: Close or delete the investigation</span></span>

<span data-ttu-id="8a851-200">運用サービスのソースコンテンツの場所 (メールボックスまたはサイト) 内のドキュメントを削除した後も、調査の一環としてエビデンスに追加したこれらのドキュメントのコピーが残ります。</span><span class="sxs-lookup"><span data-stu-id="8a851-200">After you delete documents in the source content locations (mailboxes or sites) in the live service, you will still have copies of these documents that you added to evidence as part of your investigation.</span></span> <span data-ttu-id="8a851-201">その他のデータ流出を回避するには、調査自体を削除することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a851-201">To avoid further data spillage, you should consider deleting the investigation itself.</span></span>

<span data-ttu-id="8a851-202">調査を削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8a851-202">To delete an investigation:</span></span>

1. <span data-ttu-id="8a851-203">[**設定**] タブで、[**調査情報**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a851-203">On the **Settings** tab, click **Investigation information**.</span></span>

2. <span data-ttu-id="8a851-204">[**調査の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a851-204">Click  **Delete investigation**.</span></span> 

<span data-ttu-id="8a851-205">調査を削除する必要がない場合や、調査時に収集した情報を保存する場合は、[case を**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a851-205">If you don't need to delete the investigation or if you want to save the information that you collected during the investigation, you can click **Close case**.</span></span> <span data-ttu-id="8a851-206">その後、クローズされた調査を再度開くことができます。</span><span class="sxs-lookup"><span data-stu-id="8a851-206">Then at a later date, you can re-open closed investigations.</span></span>
