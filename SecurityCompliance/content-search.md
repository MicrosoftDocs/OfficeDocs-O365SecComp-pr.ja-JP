---
title: Office 365 のコンテンツ検索
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: Office 365 または Microsoft 365 のコンプライアンスセンターでコンテンツ検索ツールを使用して、メールボックス、SharePoint Online サイト、OneDrive アカウント、Microsoft Teams、Office 365 グループ、Skype for Business の会話のコンテンツを検索します。 キーワード検索クエリと検索条件を使用して、検索結果を絞り込むことができます。 その後、検索結果をプレビューしてエクスポートできます。 コンテンツ検索は、GDPR データ主体要求に関連するコンテンツを検索するための効果的なツールでもあります。
ms.openlocfilehash: 76c3ddbbd6cd7432a06506be62c63fbfa0291b46
ms.sourcegitcommit: 6b2ca6bd153d24a717d6c537efd2d41d35c20a0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35587821"
---
# <a name="content-search-in-office-365"></a><span data-ttu-id="5cafa-106">Office 365 のコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="5cafa-106">Content Search in Office 365</span></span>

<span data-ttu-id="5cafa-107">Office 365 または Microsoft 365 のコンプライアンスセンターでコンテンツ検索電子情報開示ツールを使用して、Office 365 組織の電子メール、ドキュメント、インスタントメッセージの会話など、インプレースアイテムを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-107">You can use the Content Search eDiscovery tool in the compliance center in Office 365 or Microsoft 365 to search for in-place items such as email, documents, and instant messaging conversations in your Office 365 organization.</span></span> <span data-ttu-id="5cafa-108">このツールを使用して、これらの Office 365 サービスのアイテムを検索します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-108">Use this tool to search for items in these Office 365 services:</span></span>
  
- <span data-ttu-id="5cafa-109">Exchange Online メールボックスとパブリック フォルダー</span><span class="sxs-lookup"><span data-stu-id="5cafa-109">Exchange Online mailboxes and public folders</span></span>
    
- <span data-ttu-id="5cafa-110">SharePoint Online サイトと OneDrive for Business アカウント</span><span class="sxs-lookup"><span data-stu-id="5cafa-110">SharePoint Online sites and OneDrive for Business accounts</span></span>
    
- <span data-ttu-id="5cafa-111">Skype for Business の会話</span><span class="sxs-lookup"><span data-stu-id="5cafa-111">Skype for Business conversations</span></span>
    
- <span data-ttu-id="5cafa-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5cafa-112">Microsoft Teams</span></span> 
    
- <span data-ttu-id="5cafa-113">Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="5cafa-113">Office 365 Groups</span></span>
    
<span data-ttu-id="5cafa-p103">コンテンツ検索を実行すると、コンテンツの場所の数と予想される検索結果の数が検索プロファイルに表示されます。検索クエリと一致するアイテムが最も多いコンテンツの場所など、統計情報をすばやく表示することもできます。検索を実行した後、結果をプレビューしたり、ローカルコンピューターにエクスポートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-p103">After you run a Content Search, the number of content locations and an estimated number of search results are displayed in the search profile. You can also quickly view statistics, such as the content locations that have the most items that match the search query. After you run a search, you can preview the results or export them to a local computer.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="5cafa-117">Create a search</span><span class="sxs-lookup"><span data-stu-id="5cafa-117">Create a search</span></span>

<span data-ttu-id="5cafa-118">検索を実行して検索結果をプレビューおよびエクスポートするために**コンテンツ検索**ページにアクセスできるようにするには、管理者、コンプライアンス責任者、または電子情報開示マネージャーが、セキュリティ & コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-118">To have access to the **Content search** page to run searches and preview and export search results, an administrator, compliance officer, or eDiscovery manager must be a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="5cafa-119">詳細については、「[電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-119">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
  
1. <span data-ttu-id="5cafa-120">に[https://protection.office.com](https://protection.office.com)移動し、Office 365 の電子メールアドレスとパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-120">Go to [https://protection.office.com](https://protection.office.com) and sign in using your Office 365 email address and password.</span></span>
    
2. <span data-ttu-id="5cafa-121">[**検索** \> **コンテンツ検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-121">Click **Search** \> **Content search**.</span></span>
    
3. <span data-ttu-id="5cafa-122">**[検索]** ページで、![[追加アイコン](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **新しい検索]** の横にある矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-122">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span> 
    
    ![新しい検索のドロップダウン リスト](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    <span data-ttu-id="5cafa-124">以下のいずれかのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-124">You can choose one of the following options:</span></span>
    
    - <span data-ttu-id="5cafa-125">\* \* [ガイド付き検索] —このオプションは、検索を作成する手順を示すウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-125">\*\*Guided search — This option starts a wizard that guides you through the creating the search.</span></span> <span data-ttu-id="5cafa-126">コンテンツの場所を選択して検索クエリを作成するためのユーザーインターフェイスは、**新しい検索**オプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="5cafa-126">The user interface to select content locations and build the search query are the same as the **New search** option.</span></span> 
    
    - <span data-ttu-id="5cafa-127">[**新しい検索**] –検索を作成するために更新されたユーザーインターフェイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-127">**New search** – This option displays an updated user interface to create a search.</span></span> <span data-ttu-id="5cafa-128">これは、[**新しい検索**] をクリックした場合の既定のオプションです。</span><span class="sxs-lookup"><span data-stu-id="5cafa-128">This is the default option if you click **New search**.</span></span>
    
    - <span data-ttu-id="5cafa-129">**ID リストによる検索**-このオプションでは、Exchange id のリストを使用して特定の電子メールメッセージやその他のメールボックスアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-129">**Search by ID List** – This option lets you search for specific email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="5cafa-130">ID リスト検索 (正式には対象化検索と呼ばれていました) を作成するには、検索する特定のメールボックスアイテムを識別するコンマ区切り値 (CSV) ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-130">To create an ID list search (formally called a targeted search), you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="5cafa-131">手順については、「 [Office 365 で ID リストコンテンツ検索の CSV ファイルを準備する](csv-file-for-an-id-list-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-131">For instructions, see [Prepare a CSV file for an ID list Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
    
    <span data-ttu-id="5cafa-132">この手順の残りの手順では、既定の新しい検索ワークフローに従います。</span><span class="sxs-lookup"><span data-stu-id="5cafa-132">The remainder of the steps in this procedure follows the default new search workflow.</span></span>
    
4. <span data-ttu-id="5cafa-133">ドロップダウン リストで **[新しい検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-133">Click **New search** in the drop-down list.</span></span> 
    
5. <span data-ttu-id="5cafa-134">[**検索クエリ**] で、次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-134">Under **Search query**, specify the following things:</span></span>
    
    ![キーワード、条件、および検索する場所を指定します。](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
   - <span data-ttu-id="5cafa-136">**検索するキーワード**– [**キーワード**] ボックスに検索クエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-136">**Keywords to search for** – Type a search query in **Keywords** box.</span></span> <span data-ttu-id="5cafa-137">キーワード、メッセージ プロパティ (送信日付や受信日付など)、ドキュメント プロパティ (ファイル名や、ドキュメントの最終変更日など) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-137">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="5cafa-138">**And**、 **OR**、 **NOT**、 **NEAR**などのブール演算子を使用するより複雑なクエリを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-138">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="5cafa-139">また、ドキュメント内の機密情報 (社会保障番号など) を検索したり、外部で共有されているドキュメントを検索したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-139">You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally.</span></span> <span data-ttu-id="5cafa-140">[キーワード] ボックスを空のままにすると、指定されたコンテンツの場所にあるすべてのコンテンツが検索結果に含まれます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-140">If you leave the keyword box empty, all content located in the specified content locations is included in the search results.</span></span>
    
      <span data-ttu-id="5cafa-141">または、[**キーワードリストを表示**する] チェックボックスをオンにして、各行にキーワードを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-141">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row.</span></span> <span data-ttu-id="5cafa-142">このようにすると、各行のキーワードは、作成された検索クエリの**or**演算子の機能に似た論理演算子 (**c:s**) によって接続されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-142">If you do this, the keywords on each row are connected by a logical operator (**c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
      <span data-ttu-id="5cafa-p110">キーワード リストを使用するのはなぜですか。各キーワードと一致するアイテム数を示す統計情報を取得することができます。これは、最も有効な (および最も有効でない) キーワードをすばやく識別するのに役立ちます。行で (かっこで囲まれた) キーワード フレーズを使用することもできます。検索統計の詳細については、「[コンテンツ検索結果のキーワード統計の表示](view-keyword-statistics-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-p110">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="5cafa-148">大規模なキーワード リストによって生じる問題を軽減するため、キーワード リストの行は最大 20 行に設定されています。</span><span class="sxs-lookup"><span data-stu-id="5cafa-148">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list.</span></span>
    
    - <span data-ttu-id="5cafa-149">**条件**–検索条件を追加して、検索結果を絞り込んだり、より洗練された結果セットを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-149">**Conditions** – You can add search conditions to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="5cafa-150">各条件は、検索を開始するときに作成され、実行される句を検索クエリに追加します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-150">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="5cafa-151">条件は、論理演算子 (**c:c**) によって論理的に (キーワードボックスで指定された) キーワードクエリに関連付けられています。これは、 **and 演算子と**機能が似ています。</span><span class="sxs-lookup"><span data-stu-id="5cafa-151">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="5cafa-152">つまり、アイテムは、キーワードクエリと、結果に含まれる1つ以上の条件を満たす必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-152">That means that items have to satisfy both the keyword query and one or more conditions to be included in the results.</span></span> <span data-ttu-id="5cafa-153">このように条件は、結果を絞り込むのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-153">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="5cafa-154">検索クエリで使用できる条件の一覧と説明については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md#search-conditions)」の「検索条件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-154">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
    
       - <span data-ttu-id="5cafa-155">[**場所**]: 検索するコンテンツの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-155">**Locations** – Choose the content locations to search.</span></span>
    
      - <span data-ttu-id="5cafa-156">[**すべての場所**]: このオプションを使用して、組織内のすべてのコンテンツの場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-156">**All locations** – Use this option to search all content locations in your organization.</span></span> <span data-ttu-id="5cafa-157">これには、すべての Exchange メールボックス (非アクティブなすべてのメールボックス、すべての Office 365 グループのメールボックス、すべての Microsoft Teams のメールボックスなど)、すべての Skype for Business の会話、すべての SharePoint および OneDrive for business サイト (サイトを含む) などのメールが含まれます。すべての Office 365 グループと Microsoft Teams)、およびすべての Exchange パブリックフォルダー内のアイテム。</span><span class="sxs-lookup"><span data-stu-id="5cafa-157">This includes email in all Exchange mailboxes (including all inactive mailboxes, mailboxes for all Office 365 Groups, mailboxes for all Microsoft Teams), all Skype for Business conversations, all SharePoint and OneDrive for Business sites (including the sites for all Office 365 Groups and Microsoft Teams), and items in all Exchange public folders.</span></span>
    
      - <span data-ttu-id="5cafa-158">**特定の場所**–特定のコンテンツの場所を検索するには、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-158">**Specific locations** – Use this option to search specific content locations.</span></span> <span data-ttu-id="5cafa-159">特定の Office 365 サービスのすべてのコンテンツの場所を検索できます (すべての Exchange メールボックスを検索したり、すべての SharePoint サイトを検索したりするなど)。または、表示されている Office 365 サービスの特定の場所を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-159">You can search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or search all SharePoint sites) or you can search specific locations in any of the Office 365 services that are displayed.</span></span> 
    
        ![検索するコンテンツの場所を選択するためのユーザー インターフェイス](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
         <span data-ttu-id="5cafa-161">また、検索する Exchange メールボックスの一覧に配布グループを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-161">You can also add distribution groups to the list of Exchange mailboxes to search.</span></span> <span data-ttu-id="5cafa-162">配布グループの場合、グループメンバーのメールボックスが検索されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-162">For distribution groups, the mailboxes of group members are searched.</span></span> <span data-ttu-id="5cafa-163">動的配布グループはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5cafa-163">Dynamic distribution groups aren't supported.</span></span>
    
       > [!NOTE]
       > <span data-ttu-id="5cafa-164">すべてのメールボックスの場所または特定のメールボックスだけを検索する場合は、コンテンツ検索の結果をエクスポートするときに、ユーザーのメールボックスに保存されている他の Office 365 アプリケーションのデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-164">When you search all mailbox locations or just specific mailboxes, data from other Office 365 applications that's saved to user mailboxes is included when you export the results of a Content Search.</span></span> <span data-ttu-id="5cafa-165">このデータは、推定検索結果には含まれず、プレビューでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5cafa-165">This data won't be included in the estimated search results and isn't available for preview.</span></span> <span data-ttu-id="5cafa-166">これは、検索結果をエクスポートしてダウンロードするときに含まれます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-166">It is included when you export and download the search results.</span></span> <span data-ttu-id="5cafa-167">詳細については、「 [Exchange Online メールボックスに格納されているコンテンツ](what-is-stored-in-exo-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-167">For more information, see [Content stored in Exchange Online mailboxes](what-is-stored-in-exo-mailbox.md).</span></span>

    
6. <span data-ttu-id="5cafa-168">検索クエリを設定したら、[ **Save & 実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-168">After you've set up your search query, click **Save & run**.</span></span>
    
7. <span data-ttu-id="5cafa-169">[**検索の保存**] ページで、検索の名前と、検索を識別するために使用できる説明 (オプション) を入力します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-169">On the **Save search** page, type a name for the search, and an optional description that helps identify the search.</span></span> <span data-ttu-id="5cafa-170">検索の名前は、組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-170">The name of the search has to be unique in your organization.</span></span> 
    
8. <span data-ttu-id="5cafa-171">**[保存]** をクリックして検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-171">Click **Save** to start the search.</span></span> 
    
    <span data-ttu-id="5cafa-p117">検索を保存して実行すると、検索によって返された結果が結果ウィンドウに表示されます。プレビュー設定の構成方法によっては、検索結果が表示されるか、**[結果のプレビュー]** をクリックして表示する必要があります。詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-p117">After you save and run the search, any results returned by the search are displayed in the results pane. Depending on how you have the preview setting configured, the search results are display or you have to click **Preview results** to view them. See the next section for details.</span></span> 
    
<span data-ttu-id="5cafa-175">このコンテンツ検索に再度アクセスするか、**コンテンツ検索**ページにリストされている他のコンテンツ検索にアクセスするには、検索を選択し、**[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-175">To access this content search again or access other content searches listed on the **Content search** page, select the search and then click **Open**.</span></span> 
  
<span data-ttu-id="5cafa-176">結果をクリアするか、別の検索を![作成する](media/O365-MDM-CreatePolicy-AddIcon.gif)には、[追加] アイコン [**新しい検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-176">To clear the results or create another search, click ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif) **New search**.</span></span> 

  
## <a name="preview-search-results"></a><span data-ttu-id="5cafa-177">検索結果のプレビュー</span><span class="sxs-lookup"><span data-stu-id="5cafa-177">Preview search results</span></span>

<span data-ttu-id="5cafa-p118">検索結果のプレビューには、2 つの構成設定があります。新しい検索を実行するか、既存の検索を開いた後、[個別の結果] をクリックして、次のプレビュー設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-p118">There are two configuration settings for previewing search results. After you run a new a new search or open an existing search, click \*\* Individual results \*\* to view the following preview settings:</span></span> 
  
![検索結果設定のプレビュー](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. <span data-ttu-id="5cafa-181">[**結果を自動的にプレビュー**する]: この設定は、検索を実行した後に検索結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-181">**Preview results automatically** – This setting displays the search results after you a run a search.</span></span>
    
2. <span data-ttu-id="5cafa-182">[**結果を手動でプレビュー**する]: この設定では、検索結果ウィンドウにプレースホルダーが表示され、検索結果を表示するためにクリックする必要がある [**結果のプレビュー** ] ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-182">**Preview results manually** – This setting displays placeholders in the search results pane, and displays the **Preview results** button that you have to click to display the search results.</span></span> <span data-ttu-id="5cafa-183">既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="5cafa-183">This is the default setting.</span></span> <span data-ttu-id="5cafa-184">既存の検索を開いたときに検索結果が自動的に表示されないため、検索のパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-184">It helps enhance search performance by not automatically displaying the search results when you open an existing search.</span></span> 
    
<span data-ttu-id="5cafa-185">プレビューできるアイテムの数に関連する制限があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-185">There are limits related to how many items are available to be previewed.</span></span> <span data-ttu-id="5cafa-186">詳細については、「[コンテンツ検索の制限](limits-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-186">For more information, see [Limits for Content Search](limits-for-content-search.md).</span></span> 
  
<span data-ttu-id="5cafa-p121">プレビューできるサポートされているファイルの種類のリストについては、「コンテンツ検索に関する詳細情報」セクションの「[検索結果のプレビュー](#previewing-search-results)」を参照してください。プレビューがサポートされないファイルの種類の場合、またはドキュメントのコピーをダウンロードする場合は、**[元のファイルのダウンロード]** をクリックしてローカル コンピューターにダウンロードします。.aspx Web ページの場合、ページの URL が含まれていても、ページへのアクセス許可を持っていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-p121">For a list of supported file types that can be previewed, see [Previewing search results](#previewing-search-results) in the "More information about content search" section. If a file type isn't supported for preview or to download a copy of a document, you can click **Download original file** to download it to your local computer. For .aspx Web pages, the URL for the page is included though you might not have permissions to access the page.</span></span> 
  
<span data-ttu-id="5cafa-190">また、インデックスのないアイテムはプレビューできないことにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-190">Also note that unindexed items aren't available for previewing.</span></span>
  
## <a name="view-information-and-statistics-about-a-search"></a><span data-ttu-id="5cafa-191">検索に関する情報と統計情報を表示する</span><span class="sxs-lookup"><span data-stu-id="5cafa-191">View information and statistics about a search</span></span>

<span data-ttu-id="5cafa-192">コンテンツ検索を作成して実行すると、予想される検索結果に関する統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-192">After you create and run a content search, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="5cafa-193">これには、検索結果の概要、検索クエリと一致するアイテムが含まれるコンテンツの場所の数、最も一致するアイテムを含むコンテンツの場所の名前などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-193">This includes a summary of the search results, the query statistics such as the number of content locations with items that match the search query, and the name of content locations that have the most matching items.</span></span> <span data-ttu-id="5cafa-194">1つまたは複数のコンテンツ検索の統計を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-194">You can display statistics for one or more content searches.</span></span> <span data-ttu-id="5cafa-195">これにより、複数の検索の結果をすばやく比較し、検索クエリの有効性を判断することができます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-195">This lets you quickly compare the results for multiple searches and make decisions about the effectiveness of your search queries.</span></span>
  
<span data-ttu-id="5cafa-p123">また、検索の統計情報とキーワードの統計情報を CSV ファイルにダウンロードできます。これにより、Excel のフィルター機能や並べ替え機能を使用して結果を比較し、検索結果のレポートを準備できます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-p123">You can also download the search statistics and keyword statistics to a CSV file. This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
<span data-ttu-id="5cafa-198">検索の統計情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="5cafa-198">To view search statistics:</span></span>
  
1. <span data-ttu-id="5cafa-199">[**コンテンツ検索**] ページで、[**開く**] をクリックして、統計を表示する検索をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-199">On the **Content search** page, click **Open** and then click the search that you want to view the statistic for.</span></span> 
    
2. <span data-ttu-id="5cafa-200">[ポップアップ] ページで、[**クエリを開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-200">On the flyout page, click **Open query**.</span></span> 
    
3. <span data-ttu-id="5cafa-201">**[個々の結果]** ドロップダウン リストで、**[検索プロファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-201">In the **Individual results** drop down list, click **Search profile**.</span></span>
    
4. <span data-ttu-id="5cafa-202">**[種類]** ドロップダウン リストで、表示する検索統計に応じて、次のいずれかのオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-202">In the **Type** drop down list, click one of the following options depending on the search statistics you want to view.</span></span> 
    
  - <span data-ttu-id="5cafa-203">**概要**: 検索したコンテンツの場所の種類ごとに統計情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-203">**Summary** – Displays statistics for each type of content locations searched.</span></span> <span data-ttu-id="5cafa-204">このコンテンツには、検索クエリに一致したアイテムが含まれているコンテンツの場所の数と、検索結果のアイテムの合計数とサイズが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-204">This contents the number of content locations that contained items that matched the search query, and the total number and size of search result items.</span></span> <span data-ttu-id="5cafa-205">既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="5cafa-205">This is the default setting.</span></span>
    
  - <span data-ttu-id="5cafa-206">**クエリ**–検索クエリについての統計を表示します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-206">**Queries** – Displays statistics about the search query.</span></span> <span data-ttu-id="5cafa-207">これには、クエリの統計が適用されるコンテンツの場所の種類、統計を適用できる検索クエリの一部 (**プライマリ**は検索クエリ全体を示すことに注意してください)、アイテムが含まれるコンテンツの場所の数が含まれます。検索クエリと一致し、検索クエリに一致する合計数とサイズ、および検出されたアイテムの総数 (指定されたコンテンツの場所)。</span><span class="sxs-lookup"><span data-stu-id="5cafa-207">This includes the type of content location the query statistics are applicable to, part of the search query the statistics are applicable to (note that **Primary** indicates the entire search query), the number of the content locations that contain items that match the search query, and the total number and size and items that were found (in the specified content location) that match the search query.</span></span> <span data-ttu-id="5cafa-208">インデックス付けされていないアイテム (*部分的にインデックス*が付いたアイテムとも呼ばれます) の統計情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-208">Statistics for unindexed items (also called *partially indexed items*) are also displayed.</span></span> <span data-ttu-id="5cafa-209">ただし、統計情報には、メールボックスの一部のインデックス付きアイテムのみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5cafa-209">However, only partially indexed items from mailboxes are included in the statistics.</span></span> <span data-ttu-id="5cafa-210">SharePoint および OneDrive からの部分的にインデックスが作成されたアイテムは統計に含まれません。</span><span class="sxs-lookup"><span data-stu-id="5cafa-210">Partially indexed items from SharePoint and OneDrive are not included in the statistics.</span></span>
    
  - <span data-ttu-id="5cafa-211">[**上位の場所**]-各コンテンツの場所の検索クエリに一致するアイテムの数に関する統計情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-211">**Top locations** – Displays statistics about the number of items that match the search query in each content location.</span></span> <span data-ttu-id="5cafa-212">上位の1000の場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-212">The top 1,000 locations are displayed.</span></span>
    
<span data-ttu-id="5cafa-213">検索統計の詳細については、「[コンテンツ検索結果のキーワード統計の表示](view-keyword-statistics-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-213">For more detailed information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>
  
  
## <a name="export-search-results"></a><span data-ttu-id="5cafa-214">検索結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5cafa-214">Export search results</span></span>

<span data-ttu-id="5cafa-215">検索が正常に実行されたら、検索結果をローカルコンピューターにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-215">After a search is successfully run, you can export the search results to a local computer.</span></span> <span data-ttu-id="5cafa-216">電子メールの結果をエクスポートする場合は、PST ファイルとして、または個別のメッセージ (.msg ファイル) としてコンピューターにダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-216">When you export email results, they can be downloaded to your computer as PST files or as individual messages (.msg files).</span></span> <span data-ttu-id="5cafa-217">SharePoint および OneDrive サイトからコンテンツをエクスポートすると、ネイティブの Office ドキュメントのコピーがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-217">When you export content from SharePoint and OneDrive sites, copies of native Office documents are exported.</span></span> <span data-ttu-id="5cafa-218">エクスポートされた検索結果に含まれている他のドキュメントやレポートもあります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-218">There are also other documents and reports that are included with the exported search results.</span></span> <span data-ttu-id="5cafa-219">実際のアイテムではなく、検索結果レポートをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-219">You can also export the search results report and not the actual items.</span></span>
  
<span data-ttu-id="5cafa-220">検索結果をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="5cafa-220">To export search results:</span></span>
  
1. <span data-ttu-id="5cafa-221">[**コンテンツ検索**] ページで、検索結果をエクスポートする検索をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-221">On the **Content search** page, click the search that you want to export the search results for.</span></span> 
    
2. <span data-ttu-id="5cafa-222">フライアウトページで、[ ![検索結果のエクスポート](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \*\*\*\*] アイコンをクリックし、[**結果のエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-222">On the flyout page, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then click **Export results**.</span></span> <span data-ttu-id="5cafa-223">検索結果レポートをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-223">You can also export a search results report.</span></span>
    
3. <span data-ttu-id="5cafa-p129">**[結果のエクスポート]** ポップアップ ページの各セクションに入力します。スクロール バーを使用して、すべてのエクスポート オプションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-p129">Complete the sections on the **Export results** fly out page. Be sure to use the scroll bar to view all export options.</span></span> 
    
<span data-ttu-id="5cafa-226">詳細な手順とトラブルシューティングのヒントについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-226">For more detailed instructions and troubleshooting tips, see:</span></span>
  
- [<span data-ttu-id="5cafa-227">コンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5cafa-227">Export Content Search results</span></span>](export-search-results.md)
    
- [<span data-ttu-id="5cafa-228">コンテンツ検索のレポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5cafa-228">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
  
## <a name="more-information-about-content-search"></a><span data-ttu-id="5cafa-229">コンテンツ検索に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="5cafa-229">More information about content search</span></span>

<span data-ttu-id="5cafa-230">コンテンツ検索の詳細については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-230">See the following sections for more information about content searches.</span></span>
  
[<span data-ttu-id="5cafa-231">コンテンツ検索の制限</span><span class="sxs-lookup"><span data-stu-id="5cafa-231">Content search limits</span></span>](#content-search-limits)
  
[<span data-ttu-id="5cafa-232">検索クエリの作成</span><span class="sxs-lookup"><span data-stu-id="5cafa-232">Building a search query</span></span>](#building-a-search-query)
  
[<span data-ttu-id="5cafa-233">OneDrive アカウントの検索</span><span class="sxs-lookup"><span data-stu-id="5cafa-233">Searching OneDrive accounts</span></span>](#searching-onedrive-accounts)
  
[<span data-ttu-id="5cafa-234">Microsoft Teams と Office 365 グループの検索</span><span class="sxs-lookup"><span data-stu-id="5cafa-234">Searching Microsoft Teams and Office 365 Groups</span></span>](#searching-microsoft-teams-and-office-365-groups)
  
[<span data-ttu-id="5cafa-235">非アクティブなメールボックスの検索</span><span class="sxs-lookup"><span data-stu-id="5cafa-235">Searching inactive mailboxes</span></span>](#searching-inactive-mailboxes)
  
[<span data-ttu-id="5cafa-236">検索結果のプレビュー</span><span class="sxs-lookup"><span data-stu-id="5cafa-236">Previewing search results</span></span>](#previewing-search-results)
  
[<span data-ttu-id="5cafa-237">部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="5cafa-237">Partially indexed items</span></span>](#partially-indexed-items)
  
### <a name="content-search-limits"></a><span data-ttu-id="5cafa-238">コンテンツ検索の制限</span><span class="sxs-lookup"><span data-stu-id="5cafa-238">Content search limits</span></span>

- <span data-ttu-id="5cafa-239">コンテンツ検索機能に適用される制限については、「[コンテンツ検索の制限](limits-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-239">For a description of the limits that are applied to the Content Search feature, see [Limits for Content Search](limits-for-content-search.md).</span></span>
    
- <span data-ttu-id="5cafa-p130">すべての Office 365 組織が実行するコンテンツ検索について、Microsoft はパフォーマンス情報を収集しています。検索クエリが複雑になると、検索時間が長くなる可能性がありますが、検索時間が長くなる最も大きな要因は、検索するメールボックス数です。Microsoft は検索時間についてサービス レベル アグリーメントを提供していませんが、検索に含まれるメールボックス数に基づくコンテンツ検索の平均検索時間を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-p130">Microsoft collects performance information for Content Searches run by all Office 365 organizations. While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched. Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for a Content Search based on the number of mailboxes included in the search.</span></span>
    
|<span data-ttu-id="5cafa-243">**メールボックスの数**</span><span class="sxs-lookup"><span data-stu-id="5cafa-243">**Number of mailboxes**</span></span>|<span data-ttu-id="5cafa-244">**検索平均時間**</span><span class="sxs-lookup"><span data-stu-id="5cafa-244">**Average search time**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5cafa-245">100</span><span class="sxs-lookup"><span data-stu-id="5cafa-245">100</span></span>  <br/> |<span data-ttu-id="5cafa-246">30 秒</span><span class="sxs-lookup"><span data-stu-id="5cafa-246">30 seconds</span></span>  <br/> |
|<span data-ttu-id="5cafa-247">1,000</span><span class="sxs-lookup"><span data-stu-id="5cafa-247">1,000</span></span>  <br/> |<span data-ttu-id="5cafa-248">45 秒</span><span class="sxs-lookup"><span data-stu-id="5cafa-248">45 seconds</span></span>  <br/> |
|<span data-ttu-id="5cafa-249">10,000</span><span class="sxs-lookup"><span data-stu-id="5cafa-249">10,000</span></span>  <br/> |<span data-ttu-id="5cafa-250">4 分</span><span class="sxs-lookup"><span data-stu-id="5cafa-250">4 minutes</span></span>  <br/> |
|<span data-ttu-id="5cafa-251">25,000</span><span class="sxs-lookup"><span data-stu-id="5cafa-251">25,000</span></span>  <br/> |<span data-ttu-id="5cafa-252">10 分</span><span class="sxs-lookup"><span data-stu-id="5cafa-252">10 minutes</span></span>  <br/> |
|<span data-ttu-id="5cafa-253">50,000</span><span class="sxs-lookup"><span data-stu-id="5cafa-253">50,000</span></span>  <br/> |<span data-ttu-id="5cafa-254">20 分</span><span class="sxs-lookup"><span data-stu-id="5cafa-254">20 minutes</span></span>  <br/> |
|<span data-ttu-id="5cafa-255">100,000</span><span class="sxs-lookup"><span data-stu-id="5cafa-255">100,000</span></span>  <br/> |<span data-ttu-id="5cafa-256">25 分</span><span class="sxs-lookup"><span data-stu-id="5cafa-256">25 minutes</span></span>  <br/> |
  
### <a name="building-a-search-query"></a><span data-ttu-id="5cafa-257">検索クエリの作成</span><span class="sxs-lookup"><span data-stu-id="5cafa-257">Building a search query</span></span>

<span data-ttu-id="5cafa-258">検索クエリの作成、ブール検索演算子と検索条件の使用、組織外のユーザーと共有する機密情報の種類とコンテンツの検索の詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-258">For detailed information about creating a search query, using Boolean search operators and search conditions, and searching for sensitive information types and content shared with users outside your organization, see [Keyword queries and search conditions for Content Search ](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="5cafa-259">キーワードリストを使用して検索クエリを作成する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-259">Keep the following things in mind when using the keyword list to create a search query.</span></span>
  
- <span data-ttu-id="5cafa-260">[**キーワードリストを表示**する] チェックボックスをオンにしてから、それぞれの行に各キーワードを入力して検索クエリを作成し、各行のキーワード (またはキーワードフレーズ) が**or**演算子で接続されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-260">You have to select the **Show keyword list** checkbox and then type each keyword in a separate row to create a search query where the keywords (or keyword phrases) in each row are connected by the **OR** operator.</span></span> <span data-ttu-id="5cafa-261">キーワードボックスにキーワードの一覧を貼り付ける場合、またはキーワードを入力した後に**enter**キーを押した場合、 **or**演算子によって接続されることはありません。</span><span class="sxs-lookup"><span data-stu-id="5cafa-261">If you paste a list of keywords in the keyword box or press the **Enter** key after typing a keyword, they won't be connected by the **OR** operator.</span></span> <span data-ttu-id="5cafa-262">以下に、キーワードの一覧を追加する方法について、正しくない正しい例を示します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-262">Here are incorrect and correct examples of how to add a list of keywords.</span></span> 
    
    <span data-ttu-id="5cafa-263">**正しくない例**</span><span class="sxs-lookup"><span data-stu-id="5cafa-263">**Incorrect**</span></span>
    
    ![キーワード リストの正しくない書式設定方法 (キーワード ボックスにリストを貼り付ける)](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    <span data-ttu-id="5cafa-265">**正しい例**</span><span class="sxs-lookup"><span data-stu-id="5cafa-265">**Correct**</span></span>
    
    ![キーワード リストの正しい書式設定方法 (チェックボックスをオンにしてからリストを貼り付ける)](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- <span data-ttu-id="5cafa-267">また、Excel ファイルまたはプレーンテキストファイル内のキーワードやキーワード語句の一覧を準備し、そのリストをコピーしてキーワードリストに貼り付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-267">You can also prepare a list of keywords or keyword phrases in an Excel file or a plain text file, and then copy and paste your list into the keyword list.</span></span> <span data-ttu-id="5cafa-268">これを行うには、[**キーワードリストを表示**する] チェックボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-268">To do this, you have to select the **Show keyword list** check box.</span></span> <span data-ttu-id="5cafa-269">次に、[キーワード] ボックスの最初の行をクリックし、リストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-269">Then, click the first row in the keyword list and paste your list.</span></span> <span data-ttu-id="5cafa-270">Excel またはテキストファイルの各行は、キーワードリストの別の行に貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-270">Each line from the Excel or text file is pasted into separate row in the keyword list.</span></span> 
    
- <span data-ttu-id="5cafa-p133">キーワード リストを使用してクエリを作成したら、検索クエリが意図したものであることを確認することをお勧めします。詳細ウィンドウの **[クエリ]** の下に表示される検索クエリでは、キーワードは **(c:s)** というテキストで区切られます。これは、キーワードが **OR** 演算子と機能的に同様の論理演算子で接続されていることを示します。同様に、検索クエリに条件が含まれている場合、キーワードと条件は **(c:c)** というテキストで区切られます。これは、キーワードが **AND** 演算子と機能的に同様の論理演算子で条件に接続されていることを示します。キーワード リストと条件を使用した場合の結果として (詳細ウィンドウに) 表示される検索クエリの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-p133">After you create a query using the keyword list, it's a good idea to verify the search query syntax to make the search query is what you intended. In the search query that's displayed under **Query** in the details pane, the keywords are separated by the text **(c:s)**. This indicates that the keywords are connected by a logical operator similar in functionality to the **OR** operator. Similarly, if your search query includes conditions, the keywords and the conditions are separated by the text **(c:c)**. This indicates that the keywords are connected to the conditions with a logical operator similar in functionality to the **AND** operator. Here's an example of the search query (displayed in the Details pane) that results when using the keyword list and a condition.</span></span> 
    
    ![キーワード リストと条件を使用して作成するクエリの例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- <span data-ttu-id="5cafa-278">コンテンツ検索を実行すると、Office 365 によって、サポートされていない文字および大文字になっていないブール演算子の検索クエリが自動的にチェックされます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-278">When you run a content search, Office 365 automatically checks your search query for unsupported characters and for Boolean operators that may not be capitalized.</span></span> <span data-ttu-id="5cafa-279">サポートされていない文字は通常は非表示になり、通常は検索エラーが発生するか、予期しない結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-279">Unsupported characters are often hidden and typically cause a search error or return unintended results.</span></span> <span data-ttu-id="5cafa-280">チェックされているサポートされていない文字の詳細については、「[コンテンツ検索クエリでエラーをチェック](check-your-content-search-query-for-errors.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-280">For more information about the unsupported characters that are checked, see [Check your Content Search query for errors](check-your-content-search-query-for-errors.md).</span></span>
    
- <span data-ttu-id="5cafa-281">英語以外の文字 (中国語文字など) のキーワードが含まれている検索クエリがある場合は、[**クエリ言語-国/地域**![クエリ言語] をクリックし、[コンテンツ検索](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) ] の国/地域アイコンを選択して、検索の言語-国のカルチャコード値。</span><span class="sxs-lookup"><span data-stu-id="5cafa-281">If you have a search query that contains keywords for non-English characters (such as Chinese characters), you can click **Query language-country/region**![Query language-country/region icon in Content search](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) and select a language-country culture code value for the search.</span></span> <span data-ttu-id="5cafa-282">既定の言語/地域はニュートラルです。</span><span class="sxs-lookup"><span data-stu-id="5cafa-282">The default language/region is neutral.</span></span> <span data-ttu-id="5cafa-283">コンテンツ検索の言語設定を変更する必要があるかどうかを判断するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="5cafa-283">How can you tell if you need to change the language setting for a content search?</span></span> <span data-ttu-id="5cafa-284">特定のコンテンツの場所に英語以外の文字が含まれていて、検索結果が返されない場合は、言語設定が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-284">If you're certain content locations contain the non-English characters you're searching for, but the search returns no results, the language setting might be the cause.</span></span> 
  
### <a name="searching-onedrive-accounts"></a><span data-ttu-id="5cafa-285">OneDrive アカウントの検索</span><span class="sxs-lookup"><span data-stu-id="5cafa-285">Searching OneDrive accounts</span></span>

- <span data-ttu-id="5cafa-286">組織内の OneDrive サイトの Url の一覧を収集するには、「[組織内のすべての onedrive の場所の一覧を作成](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-286">To collect a list of the URLs for the OneDrive sites in your organization, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a).</span></span> <span data-ttu-id="5cafa-287">この記事のこのスクリプトでは、すべての OneDrive サイトの一覧を含むテキストファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-287">This script in this article creates a text file that contains a list of all OneDrive sites.</span></span> <span data-ttu-id="5cafa-288">このスクリプトを実行するには、SharePoint Online 管理シェルをインストールして使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-288">To run this script, you have to install and use the SharePoint Online Management Shell.</span></span> <span data-ttu-id="5cafa-289">検索する各 OneDrive サイトに、組織の個人用サイトドメインの URL を追加してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-289">Be sure to append the URL for your organization's MySite domain to each OneDrive site that you want to search.</span></span> <span data-ttu-id="5cafa-290">これは、すべての OneDrive を含むドメインです。たとえば、 `https://contoso-my.sharepoint.com`のようになります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-290">This is the domain that contains all your OneDrive; for example,  `https://contoso-my.sharepoint.com`.</span></span> <span data-ttu-id="5cafa-291">ユーザーの OneDrive サイト`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`の URL の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-291">Here's an example of a URL for a user's OneDrive site:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.</span></span>
    
    <span data-ttu-id="5cafa-292">ユーザープリンシパル名 (UPN) が変更された場合、そのユーザーの OneDrive の場所の URL が新しい UPN を組み込むように変更されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-292">In the rare case that a person's user principal name (UPN) is changed, the URL for their OneDrive location is changed to incorporate the new UPN.</span></span> <span data-ttu-id="5cafa-293">このような場合は、ユーザーの新しい OneDrive の URL を追加し、古いものを削除することで、コンテンツ検索を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-293">If this happens, you have to modify a content search by adding the user's new OneDrive URL and removing the old one.</span></span>
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a><span data-ttu-id="5cafa-294">Microsoft Teams と Office 365 グループの検索</span><span class="sxs-lookup"><span data-stu-id="5cafa-294">Searching Microsoft Teams and Office 365 Groups</span></span>

<span data-ttu-id="5cafa-295">Office 365 グループまたは Microsoft チームに関連付けられているメールボックスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-295">You can search the mailbox that's associated with an Office 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="5cafa-296">Microsoft Teams は Office 365 グループ上に構築されているため、それらを検索するのは似ています。</span><span class="sxs-lookup"><span data-stu-id="5cafa-296">Because Microsoft Teams is built on Office 365 Groups, searching them is similar.</span></span> <span data-ttu-id="5cafa-297">どちらの場合も、グループまたはチームのメールボックスのみが検索されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-297">In both cases, only the group or team mailbox is searched.</span></span> <span data-ttu-id="5cafa-298">グループまたはチームメンバーのメールボックスは検索されません。</span><span class="sxs-lookup"><span data-stu-id="5cafa-298">The mailboxes of the group or team members aren't searched.</span></span> <span data-ttu-id="5cafa-299">検索するには、それらを検索に明示的に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-299">To search them, you have to specifically add them to the search.</span></span>
  
<span data-ttu-id="5cafa-300">Microsoft Teams と Office 365 グループのコンテンツを検索する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-300">Keep the following things in mind when searching for content in Microsoft Teams and Office 365 Groups.</span></span>
  
- <span data-ttu-id="5cafa-301">Teams および Office 365 グループにあるコンテンツを検索するには、チームまたはグループに関連付けられているメールボックスと SharePoint サイトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-301">To search for content located in Teams and Office 365 Groups, you have to specify the mailbox and SharePoint site that are associated with a team or group.</span></span>
    
- <span data-ttu-id="5cafa-302">Exchange Online で**set-unifiedgroup**コマンドレットを実行して、チームまたは Office 365 グループのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-302">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for a team or an Office 365 Group.</span></span> <span data-ttu-id="5cafa-303">チームまたはグループに関連付けられているサイトの URL を取得するには、この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-303">This is a good way to get the URL for the site that's associated with a team or a group.</span></span> <span data-ttu-id="5cafa-304">たとえば、次のコマンドを実行すると、シニアリーダーシップチームという名前の Office 365 グループに対して選択されたプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-304">For example, the following command displays selected properties for an Office 365 Group named Senior Leadership Team:</span></span> 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > <span data-ttu-id="5cafa-305">**Get-UnifiedGroup** コマンドレットを実行するには、Exchange Online で View-Only Recipients という役割が割り当てられているか、View-Only Recipients という役割が割り当てられている役割グループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-305">To run the **Get-UnifiedGroup** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="5cafa-306">ユーザーのメールボックスを検索すると、そのユーザーがメンバーになっているチームまたは Office 365 グループは検索されません。</span><span class="sxs-lookup"><span data-stu-id="5cafa-306">When a user's mailbox is searched, any team or Office 365 Group that the user is a member of won't be searched.</span></span> <span data-ttu-id="5cafa-307">同様に、チームまたは Office 365 グループを検索すると、指定したグループメールボックスとグループサイトのみが検索されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-307">Similarly, when you search a team or an Office 365 Group, only the group mailbox and group site that you specify is searched.</span></span> <span data-ttu-id="5cafa-308">グループメンバーのメールボックスと OneDrive for Business アカウントは、検索に明示的に追加しない限り、検索されません。</span><span class="sxs-lookup"><span data-stu-id="5cafa-308">The mailboxes and OneDrive for Business accounts of group members aren't searched unless you explicitly add them to the search.</span></span>
    
- <span data-ttu-id="5cafa-309">チームまたは Office 365 グループのメンバーの一覧を取得するには、Microsoft 365 管理センターの [**ホーム\>グループ**] ページでプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-309">To get a list of the members of a team or an Office 365 Group, you can view the properties on the **Home \> Groups** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5cafa-310">または、Exchange Online PowerShell で次のコマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-310">Alternatively, you can run the following command in Exchange Online PowerShell:</span></span> 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > <span data-ttu-id="5cafa-311">**Get-UnifiedGroupLinks** コマンドレットを実行するには、Exchange Online で View-Only Recipients という役割が割り当てられているか、View-Only Recipients という役割が割り当てられている役割グループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-311">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="5cafa-312">Teams チャネルの一部である会話は、チームに関連付けられているメールボックスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-312">Conversations that are part of a Teams channel are stored in the mailbox that's associated with the team.</span></span> <span data-ttu-id="5cafa-313">同様に、チームメンバーがチャネルで共有するファイルは、チームの SharePoint サイトに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-313">Similarly, files that team members share in a channel are stored on the team's SharePoint site.</span></span> <span data-ttu-id="5cafa-314">そのため、チャネル内の会話やファイルを検索するには、コンテンツの場所としてチームメールボックスと SharePoint サイトを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-314">Therefore, you have to add the team mailbox and SharePoint site as a content location to search conversations and files in a channel.</span></span>
    
- <span data-ttu-id="5cafa-315">または、Teams のチャットリストに含まれる会話は、チャットに参加しているユーザーの Exchange Online メールボックスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-315">Alternatively, conversations that are part of the Chat list in Teams are stored in the Exchange Online mailbox of the users who participate in the chat.</span></span> <span data-ttu-id="5cafa-316">また、ユーザーがチャット会話で共有しているファイルは、そのファイルを共有しているユーザーの OneDrive for Business アカウントに保存されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-316">And files that a user shares in Chat conversations are stored in the OneDrive for Business account of the user who shares the file.</span></span> <span data-ttu-id="5cafa-317">そのため、会話やファイルを検索するためのコンテンツの場所として、個々のユーザーのメールボックスと OneDrive for Business のアカウントを、チャットリストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-317">Therefore, you have to add the individual user mailboxes and OneDrive for Business accounts as content locations to search conversations and files in the Chat list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5cafa-318">Exchange ハイブリッド展開では、オンプレミスのメールボックスを使用しているユーザーは、Teams のチャットリストの一部である会話に参加できます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-318">In an Exchange hybrid deployment, users with an on-premises mailbox might participate in conversations that are part of the Chat list in Teams.</span></span> <span data-ttu-id="5cafa-319">この場合、オンプレミスのメールボックスを持つユーザーのために、これらの会話のコンテンツは、クラウドベースのストレージ領域 (*オンプレミスユーザーのクラウドベースのメールボックス*と呼ばれます) に保存されるため、検索可能になります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-319">In this case, content from these conversations is also searchable because it's saved to a cloud-based storage area (called a *cloud-based mailbox for on-premises users*) for users who have an on-premises mailbox.</span></span> <span data-ttu-id="5cafa-320">詳細については、「 [Office 365 でのオンプレミスユーザーのクラウドベースのメールボックスの検索](search-cloud-based-mailboxes-for-on-premises-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-320">For more information, see [Searching cloud-based mailboxes for on-premises users in Office 365](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
  
- <span data-ttu-id="5cafa-321">各チームまたはチームチャネルには、ノートの作成とコラボレーションのための Wiki が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5cafa-321">Every team or team channel contains a Wiki for note-taking and collaboration.</span></span> <span data-ttu-id="5cafa-322">Wiki コンテンツは、.mht 形式のファイルに自動的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-322">The Wiki content is automatically saved to a file with a .mht format.</span></span> <span data-ttu-id="5cafa-323">このファイルは、チームの SharePoint サイト上の Teams Wiki データドキュメントライブラリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-323">This file is stored in the Teams Wiki Data document library on the team's SharePoint site.</span></span> <span data-ttu-id="5cafa-324">コンテンツ検索ツールを使用して Wiki を検索するには、検索するコンテンツの場所としてチームの SharePoint サイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-324">You can use the Content Search tool to search the Wiki by specifying the team's SharePoint site as the content location to search.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5cafa-325">Wiki をチームまたはチャネルで検索する機能 (チームの SharePoint サイトを検索する場合) は、2017年6月22日にリリースされました。</span><span class="sxs-lookup"><span data-stu-id="5cafa-325">The capability to search the Wiki for a team or channel (when you search the team's SharePoint site) was released on June 22, 2017.</span></span> <span data-ttu-id="5cafa-326">その日付またはそれ以降に保存または更新された Wiki ページは検索できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-326">Wiki pages that were saved or updated on that date or after are available to be searched.</span></span> <span data-ttu-id="5cafa-327">その日付以前に保存または更新された Wiki ページは、検索には使用できません。</span><span class="sxs-lookup"><span data-stu-id="5cafa-327">Wiki pages last saved or updated before that date aren't available for search.</span></span> 
 
- <span data-ttu-id="5cafa-328">Teams チャネルでの会議と通話の概要情報は、会議または通話にダイヤルしたユーザーのメールボックスにも保存されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-328">Summary information for meetings and calls in a Teams channel are also stored in the mailboxes of users who dialed into the meeting or call.</span></span> <span data-ttu-id="5cafa-329">これは、コンテンツ検索を使用してこれらの要約レコードを検索できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-329">This means you can use Content Search to search these summary records.</span></span> <span data-ttu-id="5cafa-330">概要情報は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5cafa-330">Summary information includes:</span></span> 
  
  - <span data-ttu-id="5cafa-331">会議または通話の日付、開始時刻、終了時刻、および継続時間</span><span class="sxs-lookup"><span data-stu-id="5cafa-331">Date, start time, end time, and duration of a meeting or call</span></span>

  - <span data-ttu-id="5cafa-332">各参加者の会議または通話の参加日時と退出日時</span><span class="sxs-lookup"><span data-stu-id="5cafa-332">The date and time when each participant joined or left the meeting or call</span></span>

  - <span data-ttu-id="5cafa-333">ボイスメールに送信された通話</span><span class="sxs-lookup"><span data-stu-id="5cafa-333">Calls sent to voice mail</span></span>

  - <span data-ttu-id="5cafa-334">不在着信</span><span class="sxs-lookup"><span data-stu-id="5cafa-334">Missed or unanswered calls</span></span>

  - <span data-ttu-id="5cafa-335">2 つの個別の通話として表される呼び出し転送</span><span class="sxs-lookup"><span data-stu-id="5cafa-335">Call transfers, which are represented as two separate calls</span></span>

  <span data-ttu-id="5cafa-336">会議と通話のサマリーレコードが検索できるようになるまで最大8時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-336">It can take up to 8 hours for meeting and call summary records to be available to be searched.</span></span>

  <span data-ttu-id="5cafa-337">検索結果では、[**種類] フィールド**で会議の概要が**会議**として識別され、通話の要約が**通話**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-337">In the search results, meeting summaries are identified as **Meeting** in the **Type field**, and call summaries are identified as **Call**.</span></span> <span data-ttu-id="5cafa-338">また、Teams チャネルと1xN のチャットの一部である会話は、[**種類**] フィールドで [ **IM** ] として識別されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-338">Also, conversations that are part of a Teams channel and 1xN chats are identified as **IM** in the **Type** field.</span></span>
  
  ![Teams の会議、通話および 1xN チャットは [種類] フィールドで識別されます。](media/O365-ContentSearch-Teams-MessageKind.png)

- <span data-ttu-id="5cafa-340">**Kind** email プロパティまたは**Message kind**検索条件を使用して、Teams のコンテンツを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-340">You can use the **Kind** email property or the **Message kind** search condition to search specifically for content in Teams.</span></span> 
  
  - <span data-ttu-id="5cafa-341">キーワード検索クエリの一部として **Kind** プロパティを使用するには、検索クエリの **[キーワード]** ボックスに `kind:microsoftteams` と入力します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-341">To use the **Kind** property as part of the keyword search query, in the **Keywords** box of a search query, type `kind:microsoftteams`.</span></span>

    ![[キーワード] ボックスで kind:microsoftteams を使用する](media/O365-ContentSearch-Teams-Keywords.png)
  
  - <span data-ttu-id="5cafa-343">検索条件を使用するには、**[メッセージの種類]** 条件を追加し、値 `microsoftteams` を使用します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-343">To use a search condition, add the **Message kind** condition and use the value `microsoftteams`.</span></span> 

    ![値 microsoftteams で [メッセージの種類] 条件を使用します。](media/O365-ContentSearch-Teams-MessageKindCondition.png)

<span data-ttu-id="5cafa-p149">条件が **AND** 演算子によってキーワード クエリに論理的に接続されていることに注意してください。つまり、アイテムは検索結果で返されるキーワード クエリと検索条件の両方に一致する必要があります。詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)」の「条件を使用するためのガイドライン」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-p149">Note that conditions are logically connected to the keyword query by the **AND** operator. That means an item must match both the keyword query and the search condition to be returned in the search results. For more information, see the "Guidelines for using conditions" section in [Keyword queries and search conditions for Content Search.](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)</span></span>

  
### <a name="searching-inactive-mailboxes"></a><span data-ttu-id="5cafa-348">非アクティブなメールボックスの検索</span><span class="sxs-lookup"><span data-stu-id="5cafa-348">Searching inactive mailboxes</span></span>

<span data-ttu-id="5cafa-349">コンテンツ検索で非アクティブなメールボックスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-349">You can search inactive mailboxes in a content search.</span></span> <span data-ttu-id="5cafa-350">組織内の非アクティブなメールボックスの一覧を取得するには`Get-Mailbox -InactiveMailboxOnly` 、Exchange Online PowerShell でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-350">To get a list of the inactive mailboxes in your organization, run the command  `Get-Mailbox -InactiveMailboxOnly` in Exchange Online PowerShell.</span></span> <span data-ttu-id="5cafa-351">または、セキュリティ & コンプライアンスセンターの [**データガバナンス** \>の**保持**] に移動して、 **[その他**![の](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \>ナビゲーションバーの**非アクティブなメールボックス**] をクリックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-351">Alternatively, you can go to **Data governance** \> **Retention** in the Security & Compliance Center, and then click **More**![Navigation Bar ellipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Inactive mailboxes**.</span></span>
  
<span data-ttu-id="5cafa-352">次に示しているのは、非アクティブなメールボックスを検索するときの留意点です。</span><span class="sxs-lookup"><span data-stu-id="5cafa-352">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>
  
- <span data-ttu-id="5cafa-353">コンテンツ検索にユーザーのメールボックスが含まれていて、そのメールボックスが非アクティブになっている場合、コンテンツ検索は、非アクティブになった後に検索を再実行すると、非アクティブなメールボックスの検索を続行します。</span><span class="sxs-lookup"><span data-stu-id="5cafa-353">If a content search includes a user mailbox and that mailbox is, then made inactive, the content search will continue to search the inactive mailbox when you rerun the search after it becomes inactive.</span></span>
    
- <span data-ttu-id="5cafa-354">ユーザーが、同じ SMTP アドレスを持つアクティブなメールボックスと非アクティブなメールボックスを持っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-354">Sometimes a user may have an active mailbox and an inactive mailbox that have the same SMTP address.</span></span> <span data-ttu-id="5cafa-355">この場合、コンテンツ検索の場所として指定した特定のメールボックスのみが検索されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-355">In this case, only the specific mailbox that you select as a location for a content search is searched.</span></span> <span data-ttu-id="5cafa-356">言い換えると、ユーザーのメールボックスを検索に追加した場合、アクティブなメールボックスと非アクティブなメールボックスの両方が検索されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="5cafa-356">In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes are searched.</span></span> <span data-ttu-id="5cafa-357">検索に明示的に追加したメールボックスのみが検索されます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-357">Only the mailbox that you explicitly add to the search is searched.</span></span>
    
- <span data-ttu-id="5cafa-358">同じ SMTP アドレスを持つアクティブなメールボックスと非アクティブなメールボックスを使用しないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5cafa-358">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address.</span></span> <span data-ttu-id="5cafa-359">非アクティブなメールボックスに割り当てられた SMTP アドレスを再利用する必要がある場合は、非アクティブなメールボックスを回復するか、非アクティブなメールボックスのコンテンツをアクティブなメールボックス (またはアクティブなメールボックスのアーカイブ) に復元することをお勧めします。メール.</span><span class="sxs-lookup"><span data-stu-id="5cafa-359">If you need to reuse the SMTP address that is assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox.</span></span> <span data-ttu-id="5cafa-360">詳細については、以下のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-360">For more information, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="5cafa-361">Office 365 で非アクティブなメールボックスを回復する</span><span class="sxs-lookup"><span data-stu-id="5cafa-361">Recover an inactive mailbox in Office 365</span></span>](recover-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="5cafa-362">Office 365 の非アクティブなメールボックスを復元する</span><span class="sxs-lookup"><span data-stu-id="5cafa-362">Restore an inactive mailbox in Office 365</span></span>](restore-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="5cafa-363">Office 365 の非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="5cafa-363">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

  
### <a name="previewing-search-results"></a><span data-ttu-id="5cafa-364">検索結果のプレビュー</span><span class="sxs-lookup"><span data-stu-id="5cafa-364">Previewing search results</span></span>

<span data-ttu-id="5cafa-365">サポートされているファイルの種類は、プレビューウィンドウでプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-365">You can preview supported file types in the preview pane.</span></span> <span data-ttu-id="5cafa-366">ファイルの種類がサポートされていない場合は、ファイルのコピーをローカルコンピューターにダウンロードして表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cafa-366">If a file type isn't supported, you have to download a copy of the file to your local computer to view it.</span></span> <span data-ttu-id="5cafa-367">次のファイルの種類がサポートされており、[検索結果] ウィンドウでプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-367">The following file types are supported and can be previewed in the search results pane.</span></span>
  
- <span data-ttu-id="5cafa-368">.txt、.html、.mhtml</span><span class="sxs-lookup"><span data-stu-id="5cafa-368">.txt, .html, .mhtml</span></span>
    
- <span data-ttu-id="5cafa-369">.eml</span><span class="sxs-lookup"><span data-stu-id="5cafa-369">.eml</span></span>
    
- <span data-ttu-id="5cafa-370">.doc、.docx、.docm</span><span class="sxs-lookup"><span data-stu-id="5cafa-370">.doc, .docx, .docm</span></span>
    
- <span data-ttu-id="5cafa-371">.pptm、.pptx</span><span class="sxs-lookup"><span data-stu-id="5cafa-371">.pptm, .pptx</span></span>
    
- <span data-ttu-id="5cafa-372">.pdf</span><span class="sxs-lookup"><span data-stu-id="5cafa-372">.pdf</span></span>
    
<span data-ttu-id="5cafa-373">また、次のファイルコンテナーの種類もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5cafa-373">Also, the following file container types are supported.</span></span> <span data-ttu-id="5cafa-374">[プレビュー] ウィンドウで、コンテナー内のファイルの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5cafa-374">You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="5cafa-375">.zip</span><span class="sxs-lookup"><span data-stu-id="5cafa-375">.zip</span></span>
    
- <span data-ttu-id="5cafa-376">.gzip</span><span class="sxs-lookup"><span data-stu-id="5cafa-376">.gzip</span></span>
    
### <a name="partially-indexed-items"></a><span data-ttu-id="5cafa-377">部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="5cafa-377">Partially indexed items</span></span>

- <span data-ttu-id="5cafa-378">前述のように、メールボックス内の一部のインデックス付きアイテムは、推定される検索結果に含まれています。</span><span class="sxs-lookup"><span data-stu-id="5cafa-378">As previously explained, partially indexed items in mailboxes are included in the estimated search results.</span></span> <span data-ttu-id="5cafa-379">SharePoint および OneDrive からの部分的にインデックスが作成されたアイテムは、推定検索結果に含まれていません。</span><span class="sxs-lookup"><span data-stu-id="5cafa-379">Partially indexed items from SharePoint and OneDrive aren't included in the estimated search results.</span></span> 
    
- <span data-ttu-id="5cafa-380">部分的にインデックスが作成されたアイテムが検索クエリと一致する場合 (他のメッセージまたはドキュメントのプロパティが検索条件を満たしているため)、インデックスが作成されていないアイテムの推定数に含まれていません。</span><span class="sxs-lookup"><span data-stu-id="5cafa-380">If a partially indexed item matches the search query (because other message or document properties meet the search criteria), it isn't included in the estimated number of unindexed items.</span></span> <span data-ttu-id="5cafa-381">部分的にインデックスが作成されたアイテムが検索条件によって除外されている場合、インデックスが作成されていないアイテムの推定数に含まれません。</span><span class="sxs-lookup"><span data-stu-id="5cafa-381">If a partially indexed item is excluded by the search criteria, it isn't included in the estimated number of unindexed items.</span></span> <span data-ttu-id="5cafa-382">詳細については、「 [Office 365 のコンテンツ検索での一部のインデックス付きアイテム](partially-indexed-items-in-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cafa-382">For more information, see [Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md).</span></span>