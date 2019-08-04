---
title: Office 365 のコンテンツ検索
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: Office 365 または Microsoft 365 のコンプライアンス センターのコンテンツ検索ツールを使用すると、メールボックス、SharePoint Online サイト、OneDrive アカウント、Microsoft Teams、Office 365 グループ、および Skype for Business の会話内のコンテンツを検索できます。キーワード検索クエリと検索条件を使用して検索結果を絞り込むことができます。さらに検索結果をプレビューしたり、エクスポートしたりすることができます。コンテンツ検索は、GDPR データ主体の要求に関連するコンテンツを検索するための効果的なツールでもあります。
ms.openlocfilehash: 3df1ee02cc7b31a8dd316bac5ccd4455c26922c5
ms.sourcegitcommit: 73dcdafb15b462223d1a670c781db260eb73c2f5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "36048189"
---
# <a name="content-search-in-office-365"></a><span data-ttu-id="8086a-106">Office 365 のコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="8086a-106">Content Search in Office 365</span></span>

<span data-ttu-id="8086a-p102">Office 365 または Microsoft 365 のコンプライアンス センターのコンテンツ検索電子情報開示ツールを使用して、Office 365 組織の電子メール、文書、インスタント メッセージングの会話などのインプレース アイテムを検索できます。このツールを使用すると、以下の Office 365 サービス内のアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="8086a-p102">You can use the Content Search eDiscovery tool in the Office 365 Security  Compliance Center to search for in-place items such as email, documents, and instant messaging conversations in your Office 365 organization. Use this tool to search for items in these Office 365 services:</span></span>
  
- <span data-ttu-id="8086a-109">Exchange Online メールボックスとパブリック フォルダー</span><span class="sxs-lookup"><span data-stu-id="8086a-109">Exchange Online mailboxes and public folders</span></span>
    
- <span data-ttu-id="8086a-110">SharePoint Online サイトと OneDrive for Business アカウント</span><span class="sxs-lookup"><span data-stu-id="8086a-110">SharePoint Online sites and OneDrive for Business accounts</span></span>
    
- <span data-ttu-id="8086a-111">Skype for Business の会話</span><span class="sxs-lookup"><span data-stu-id="8086a-111">Skype for Business conversations</span></span>
    
- <span data-ttu-id="8086a-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8086a-112">Microsoft Teams</span></span> 
    
- <span data-ttu-id="8086a-113">Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="8086a-113">Office 365 Groups</span></span>
    
<span data-ttu-id="8086a-p103">コンテンツ検索を実行すると、コンテンツの場所の数と予想される検索結果の数が検索プロファイルに表示されます。検索クエリと一致するアイテムが最も多いコンテンツの場所など、統計情報をすばやく表示することもできます。検索を実行した後、結果をプレビューしたり、ローカルコンピューターにエクスポートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="8086a-p103">After you run a Content Search, the number of content locations and an estimated number of search results are displayed in the search profile. You can also quickly view statistics, such as the content locations that have the most items that match the search query. After you run a search, you can preview the results or export them to a local computer.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="8086a-117">検索を作成する</span><span class="sxs-lookup"><span data-stu-id="8086a-117">Create a search</span></span>

<span data-ttu-id="8086a-p104">検索を実行して検索結果をプレビューおよびエクスポートするために [**コンテンツ検索**] ページにアクセスするには、管理者、コンプライアンス責任者、または電子情報開示マネージャーが、セキュリティ/コンプライアンス センターの電子情報開示マネージャーの役割グループのメンバーである必要があります。詳細については、「[電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-p104">To have access to the Content search page to run searches and preview and export search results, an administrator, compliance officer, or eDiscovery manager must be a member of the eDiscovery Manager role group in the Security  Compliance Center. For more information, see Assign eDiscovery permissions in the Office‍ 365 Security  Compliance Center.</span></span>
  
1. <span data-ttu-id="8086a-120">[https://protection.office.com](https://protection.office.com) にアクセスし、Office 365 の電子メール アドレスとパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="8086a-120">Go to [https://protection.office.com](https://protection.office.com) and sign in using your Office 365 email address and password.</span></span>
    
2. <span data-ttu-id="8086a-121">[**検索**] \> [**コンテンツ検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8086a-121">Click **Search** \> **Content search**.</span></span>
    
3. <span data-ttu-id="8086a-122">**[検索]** ページで、![[追加アイコン](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **新しい検索]** の横にある矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8086a-122">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span> 
    
    ![新しい検索のドロップダウン リスト](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    <span data-ttu-id="8086a-124">以下のいずれかのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8086a-124">You can choose one of the following options:</span></span>
    
    - <span data-ttu-id="8086a-125">\*\*[誘導検索] – このオプションを選択すると、検索を作成するための手順を案内するウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="8086a-125">\*\*Guided search — This option starts a wizard that guides you through the creating the search.</span></span> <span data-ttu-id="8086a-126">コンテンツの場所を選択して検索クエリを作成するためのユーザー インターフェイスは、 [**新しい検索**] オプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="8086a-126">Guided search - This option starts a wizard that guides you through the creating the search. The user interface to select content locations and build the search query are the same as the **New search** option.</span></span> 
    
    - <span data-ttu-id="8086a-127">[**新しい検索**] – 検索を作成するために更新されたユーザー インターフェイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-127">**New search** - This option displays an updated user interface to create a new search. This is the default option if you click New search.</span></span> <span data-ttu-id="8086a-128">これは、 [**新しい検索**] をクリックした場合の既定のオプションです。</span><span class="sxs-lookup"><span data-stu-id="8086a-128">This is the default option if you click **New search**.</span></span>
    
    - <span data-ttu-id="8086a-129">[**ID のリストで検索**] – このオプションでは、Exchange ID のリストを使用して特定の電子メール メッセージやその他のメールボックス アイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="8086a-129">**Search by ID List** – This option lets you search for specific email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="8086a-130">ID リスト検索 (以前は対象指定検索と呼ばれていました) を作成するには、検索する特定のメールボックス アイテムを識別するコンマ区切り値 (CSV) ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="8086a-130">To create an ID list search (formally called a targeted search), you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="8086a-131">手順については、「[Office 365 で ID リスト コンテンツ検索の CSV ファイルを準備する](csv-file-for-an-id-list-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-131">For instructions, see [Prepare a CSV file for an ID list Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
    
    <span data-ttu-id="8086a-132">この手順の残りの部分は、既定の新しい検索ワークフローに従います。</span><span class="sxs-lookup"><span data-stu-id="8086a-132">The remainder of the steps in this procedure will follow the default new search workflow.</span></span>
    
4. <span data-ttu-id="8086a-133">ドロップダウン リストで [**新しい検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8086a-133">Click **New search** in the drop-down list.</span></span> 
    
5. <span data-ttu-id="8086a-134">[**検索クエリ**] で、次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="8086a-134">Under **Search query**, specify the following things.</span></span>
    
    ![キーワード、条件、および検索する場所を指定します。](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
   - <span data-ttu-id="8086a-136">**検索するキーワード** - [**キーワード**] ボックスに検索クエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="8086a-136">**Keywords to search for** – Type a search query in **Keywords** box.</span></span> <span data-ttu-id="8086a-137">キーワード、送信日や受信日などのメッセージ プロパティ、またはファイル名や文書の最終更新日などのドキュメント プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8086a-137">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="8086a-138">**AND**、**OR**、**NOT**、**NEAR** などのブール演算子を使用するより複雑なクエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8086a-138">You can  use a more complex queries that use a Boolean operator, such as AND, OR,  NOT, NEAR, and ONEAR.</span></span> <span data-ttu-id="8086a-139">また、ドキュメント内の機密情報 (社会保障番号など) を検索したり、外部共有されているドキュメントを検索したりできます。</span><span class="sxs-lookup"><span data-stu-id="8086a-139">You can also search for sensitive information (such as social security numbers) in  documents, or search for documents that have been shared externally.</span></span> <span data-ttu-id="8086a-140">このキーワード ボックスを空のままにすると、指定したコンテンツの場所にあるすべてのコンテンツが検索結果に入ります。</span><span class="sxs-lookup"><span data-stu-id="8086a-140">If you leave the keyword  box empty, then all content  located in the specified  content sources will be included in  the search results.</span></span>
    
      <span data-ttu-id="8086a-141">また、[**キーワード リストの表示**] チェック ボックスをオンにして、各行にキーワードを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="8086a-141">Click the Show keyword list checkbox and type a keyword in each row</span></span> <span data-ttu-id="8086a-142">この場合、作成される検索クエリでは、各行のキーワードは **OR** 演算子の機能に似た論理演算子 (**c:s**) によって接続されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-142">Alternatively, you can click the Show keyword list checkbox and the type a keyword in each row. If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
      <span data-ttu-id="8086a-p110">キーワード リストを使用するのはなぜですか。各キーワードと一致するアイテム数を示す統計情報を取得することができます。これは、最も有効な (および最も有効でない) キーワードをすばやく識別するのに役立ちます。行で (かっこで囲まれた) キーワード フレーズを使用することもできます。検索統計の詳細については、「[コンテンツ検索結果のキーワード統計の表示](view-keyword-statistics-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-p110">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="8086a-148">大規模なキーワード リストによって生じる問題を軽減するため、キーワード リストの行は最大 20 行に設定されています。</span><span class="sxs-lookup"><span data-stu-id="8086a-148">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list.</span></span>
    
    - <span data-ttu-id="8086a-149">[**条件**] – 検索クエリに条件を追加して、検索を絞り込み、さらに絞り込まれた結果のセットを返すようにできます。</span><span class="sxs-lookup"><span data-stu-id="8086a-149">You can also add conditions to a search query to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="8086a-150">各条件によって、作成された検索クエリに句が追加され、ユーザーが検索を開始するとそのクエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-150">Each condition adds a clause to the KQL search query that is created and run when you start the search.</span></span> <span data-ttu-id="8086a-151">条件は、 **AND** 演算子の機能に似た論理演算子 (**c:c**) によってキーワードのクエリ (キーワード ボックスで指定される) と論理的に接続されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-151">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="8086a-152">つまり、検索結果に含まれるためには、アイテムはキーワード クエリと 1 つまたは複数の条件の両方を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-152">That means that items have to satisfy both the keyword query and the condition to be included in the results.</span></span> <span data-ttu-id="8086a-153">このように、条件を使用して結果を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="8086a-153">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="8086a-154">検索クエリで使用できる条件のリストと説明については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md#search-conditions)」の「検索条件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-154">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
    
       - <span data-ttu-id="8086a-155">**場所** – 検索するコンテンツの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="8086a-155">**Locations** - Choose the content locations to search.</span></span>
    
      - <span data-ttu-id="8086a-156">[**すべての場所**] – 組織内のすべてのコンテンツの場所を検索するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8086a-156">**All locations** – Use this option to search all content locations in your organization.</span></span> <span data-ttu-id="8086a-157">これには、すべての Exchange メールボックス (非アクティブなすべてのメールボックス、すべての Office 365 グループのメールボックス、すべての Microsoft Teams のメールボックスなど)、すべての Skype for Business の会話、すべての SharePoint および OneDrive for Business サイト (すべての Office 365 グループと Microsoft Teams のサイトなど) 内の電子メール、およびすべての Exchange パブリック フォルダー内のアイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8086a-157">All locations - Use this option to search all content locations in your organization. This includes email in all Exchange mailboxes (including all inactive mailboxes, mailboxes for all Office 365 Groups, mailboxes for all Microsoft Teams), all Skype for Business conversations, all SharePoint and OneDrive for Business sites (including the sites for all Office 365 Groups and Microsoft Teams), and items in all Exchange public folders.</span></span>
    
      - <span data-ttu-id="8086a-158">[**特定の場所**] – 特定のコンテンツの場所を検索するには、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="8086a-158">**Specific locations** – Use this option to search specific content locations.</span></span> <span data-ttu-id="8086a-159">特定の Office 365 サービスのすべてのコンテンツの場所を検索できます (すべての Exchange メールボックスを検索したり、すべての SharePoint サイトを検索したりするなど)。または、表示されている Office 365 サービスの特定の場所を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="8086a-159">Specific locations - Use this option to search specific content locations. You can search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or search all SharePoint sites) or you can search specific locations in any of the Office 365 services that are displayed.</span></span> 
    
        ![検索するコンテンツの場所を選択するためのユーザー インターフェイス](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
         <span data-ttu-id="8086a-161">検索する Exchange メールボックスのリストに配布グループを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="8086a-161">You can also add distribution groups to the list of Exchange mailboxes to search.</span></span> <span data-ttu-id="8086a-162">配布グループの場合、グループ メンバーのメールボックスが検索されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-162">For distribution groups, the mailboxes of group members are searched.</span></span> <span data-ttu-id="8086a-163">動的配布グループはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8086a-163">Dynamic distribution groups aren't supported.</span></span>
    
       > [!NOTE]
       > <span data-ttu-id="8086a-164">すべてのメールボックスを検索する場合も、特定のメールボックスだけを検索する場合も、コンテンツ検索の結果をエクスポートする際に、ユーザー メールボックスに保存されている他の Office 365 アプリケーションのデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8086a-164">When you search all mailbox locations or just specific mailboxes, data from other Office 365 applications that's saved to user mailboxes is included when you export the results of a Content Search.</span></span> <span data-ttu-id="8086a-165">このデータは、予想される検索結果には含まれず、プレビューも行えません。</span><span class="sxs-lookup"><span data-stu-id="8086a-165">This data won't be included in the estimated search results and isn't available for preview.</span></span> <span data-ttu-id="8086a-166">このデータは、検索結果をエクスポートおよびダウンロードする際には含まれます。</span><span class="sxs-lookup"><span data-stu-id="8086a-166">It is included when you export and download the search results.</span></span> <span data-ttu-id="8086a-167">詳細については、「[Content stored in Exchange Online mailboxes (Exchange Online のメールボックスに格納されているコンテンツ)](what-is-stored-in-exo-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-167">For more information, see [Manage inactive mailboxes in Exchange Online](what-is-stored-in-exo-mailbox.md).</span></span>

    
6. <span data-ttu-id="8086a-168">検索クエリを設定したら、[**保存と実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8086a-168">After you've set up your search query, click Save  run.</span></span>
    
7. <span data-ttu-id="8086a-p116">[**検索の保存**] ページで、検索の名前と、検索を識別するための説明 (省略可能) を入力します。検索の名前は、組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-p116">On the **Save search** page, type a name for the search, and an optional description that helps identify the search. Note that the name of the search has to be unique in your organization.</span></span> 
    
8. <span data-ttu-id="8086a-171">**[保存]** をクリックして検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="8086a-171">Click **Save** to start the search.</span></span> 
    
    <span data-ttu-id="8086a-p117">検索を保存して実行すると、検索によって返された結果が結果ウィンドウに表示されます。プレビュー設定の構成方法によっては、検索結果が表示されるか、**[結果のプレビュー]** をクリックして表示する必要があります。詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-p117">After you save and run the search, any results returned by the search are displayed in the results pane. Depending on how you have the preview setting configured, the search results are display or you have to click **Preview results** to view them. See the next section for details.</span></span> 
    
<span data-ttu-id="8086a-175">このコンテンツ検索に再度アクセスするか、**コンテンツ検索**ページにリストされている他のコンテンツ検索にアクセスするには、検索を選択し、**[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8086a-175">To access this content search again or access other content searches listed on the **Content search** page, select the search and then click **Open**.</span></span> 
  
<span data-ttu-id="8086a-176">結果をクリアするか、新しい検索を作成するには、[![追加アイコン](media/O365-MDM-CreatePolicy-AddIcon.gif)] [**新しい検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8086a-176">To clear the results or create a new search, click ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif) **New search**.</span></span> 

  
## <a name="preview-search-results"></a><span data-ttu-id="8086a-177">検索結果のプレビュー</span><span class="sxs-lookup"><span data-stu-id="8086a-177">Preview search results</span></span>

<span data-ttu-id="8086a-p118">検索結果のプレビューには、2 つの構成設定があります。新しい検索を実行するか、既存の検索を開いた後、[個々の結果] をクリックして、次のプレビュー設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="8086a-p118">There are two configuration settings for previewing search results. After you run a new a new search or open an existing search, click \*\* Individual results \*\* to view the following preview settings:</span></span> 
  
![検索結果設定のプレビュー](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. <span data-ttu-id="8086a-181">[**自動的に結果をプレビュー**] – この設定は、検索を実行した後に検索結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="8086a-181">**Preview results automatically** - This setting displays the search results after you a run a search.</span></span>
    
2. <span data-ttu-id="8086a-p119">[**手動で結果をプレビュー**] – この設定を使用すると、[検索結果] ウィンドウにプレースホルダーが表示され、検索結果を表示するためにクリックする必要がある [**結果のプレビュー**] ボタンが表示されます。これは既定の設定で、既存の検索を開いたときに検索結果が自動的に表示されないため、検索のパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="8086a-p119">**Preview results manually** - This setting displays placeholders in the search results pane, and displays the **Preview results** button that you have to click to display the search results. This is the default setting; it helps enhance search performance by not automatically displaying the search results when you open an existing search.</span></span> 
    
<span data-ttu-id="8086a-185">プレビューできるアイテムの数に関連する制限があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-185">There are limits related to how many items are available to be previewed. For more information, see Limits for Search in the Office 365 Security  Compliance Center.</span></span> <span data-ttu-id="8086a-186">詳細については、「[検索の制限](limits-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-186">For more information, see [Keyword queries and search conditions for Content Search](limits-for-content-search.md).</span></span> 
  
<span data-ttu-id="8086a-p121">プレビューできるサポートされているファイルの種類のリストについては、「コンテンツ検索に関する詳細情報」セクションの「[検索結果のプレビュー](#previewing-search-results)」を参照してください。プレビューがサポートされないファイルの種類の場合、またはドキュメントのコピーをダウンロードする場合は、**[元のファイルのダウンロード]** をクリックしてローカル コンピューターにダウンロードします。.aspx Web ページの場合、ページの URL が含まれていても、ページへのアクセス許可を持っていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="8086a-p121">For a list of supported file types that can be previewed, see [Previewing search results](#previewing-search-results) in the "More information about content search" section. If a file type isn't supported for preview or to download a copy of a document, you can click **Download original file** to download it to your local computer. For .aspx Web pages, the URL for the page is included though you might not have permissions to access the page.</span></span> 
  
<span data-ttu-id="8086a-190">また、インデックスのないアイテムはプレビューできないことにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-190">Also note that unindexed items aren't available for previewing.</span></span>
  
## <a name="view-information-and-statistics-about-a-search"></a><span data-ttu-id="8086a-191">検索に関する情報と統計情報を表示する</span><span class="sxs-lookup"><span data-stu-id="8086a-191">View information and statistics about a search</span></span>

<span data-ttu-id="8086a-192">コンテンツ検索を作成して実行した後は、予想される検索結果の統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="8086a-192">After you create and run a content search, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="8086a-193">これには、検索結果の概要、アイテムが検索クエリと一致したコンテンツの場所の数などのクエリ統計情報、最も多くのアイテムが一致したコンテンツの場所の名前が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8086a-193">After you create and run a content search, you can view statistics about the estimated search results. This includes a summary of the search results, the query statistics such as the number of content locations with items that match the search query, and the name of content locations that have the most matching items. You can display statistics for one or more content searches. This lets you to quickly compare the results for multiple searches and make decisions about the effectiveness of your search queries.</span></span> <span data-ttu-id="8086a-194">1 つまたは複数のコンテンツ検索に対して統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="8086a-194">You can display statistics for one or more content searches.</span></span> <span data-ttu-id="8086a-195">これにより、複数の検索の結果を簡単に比較して、検索クエリの有効性を判断できます。</span><span class="sxs-lookup"><span data-stu-id="8086a-195">This lets you quickly compare the results for multiple searches and make decisions about the effectiveness of your search queries.</span></span>
  
<span data-ttu-id="8086a-p123">また、検索の統計情報とキーワードの統計情報を CSV ファイルにダウンロードできます。これにより、Excel のフィルター機能や並べ替え機能を使用して結果を比較し、検索結果のレポートを準備できます。</span><span class="sxs-lookup"><span data-stu-id="8086a-p123">You can also download the search statistics and keyword statistics to a CSV file. This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
<span data-ttu-id="8086a-198">検索の統計情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="8086a-198">To view search statistics:</span></span>
  
1. <span data-ttu-id="8086a-199">[**コンテンツ検索**] ページで [**開く**] をクリックし、統計情報を表示する対象の検索をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8086a-199">On the **Content search** page in the Security  Compliance Center, click **Open** and then click the search that you want to view the statistic for.</span></span> 
    
2. <span data-ttu-id="8086a-200">[ポップアップ] ページで、[**クエリを開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8086a-200">On the fly out page, click **Open query**.</span></span> 
    
3. <span data-ttu-id="8086a-201">**[個々の結果]** ドロップダウン リストで、**[検索プロファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8086a-201">In the **Individual results** drop down list, click **Search profile**.</span></span>
    
4. <span data-ttu-id="8086a-202">**[種類]** ドロップダウン リストで、表示する検索統計に応じて、次のいずれかのオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8086a-202">In the **Type** drop down list, click one of the following options depending on the search statistics you want to view.</span></span> 
    
  - <span data-ttu-id="8086a-203">[**概要**] – 検索したコンテンツの場所の種類ごとに統計情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="8086a-203">**Summary** – Displays statistics for each type of content locations searched.</span></span> <span data-ttu-id="8086a-204">統計情報には、検索クエリに一致したアイテムが含まれているコンテンツの場所の数と、検索結果のアイテムの合計数とサイズが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8086a-204">Summary - Displays statistics for each type of content locations searched. This contents the number of content locations that contained items that matched the search query, and the total number and size of search result items. This is the default setting.</span></span> <span data-ttu-id="8086a-205">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="8086a-205">This is the default setting.</span></span>
    
  - <span data-ttu-id="8086a-206">[**クエリ**] – 検索クエリに関する統計情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="8086a-206">**Queries** – Displays statistics about the search query.</span></span> <span data-ttu-id="8086a-207">これには、クエリの統計情報が該当するコンテンツの場所の種類、統計情報が該当する検索クエリの一部 (**プライマリ**は検索クエリ全体を示します)、検索クエリと一致したアイテムが含まれるコンテンツの場所の数、および検索クエリに一致する (指定されたコンテンツの場所で) 検出されたアイテムの合計数とサイズが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8086a-207">Queries - Displays statistics about the search query. This includes the type of content location the query statistics are applicable to, part of the search query the statistics are applicable to (note that **Primary** indicates the entire search query), the number of the content locations that contain items that match the search query, and the total number and size and items that were found (in the specified content location) that match the search query. Note that statistics for unindexed items (also called partially indexed items) are also displayed. However, only partially indexed items from mailboxes are included in the statistics. Partially indexed items from SharePoint and OneDrive are not included in the statistics.</span></span> <span data-ttu-id="8086a-208">インデックスのないアイテム (*部分的にインデックスが作成されたアイテム*とも呼ばれます) の統計も表示されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-208">Statistics for unindexed items (also called *partially indexed items*) are also displayed.</span></span> <span data-ttu-id="8086a-209">ただし、統計情報には、メールボックスの部分的にインデックスが作成されたアイテムのみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8086a-209">However, only partially indexed items from mailboxes are included in the statistics.</span></span> <span data-ttu-id="8086a-210">SharePoint および OneDrive からの部分的にインデックスが作成されたアイテムは統計情報に含まれません。</span><span class="sxs-lookup"><span data-stu-id="8086a-210">Partially indexed items from SharePoint and OneDrive are not included in the statistics.</span></span>
    
  - <span data-ttu-id="8086a-211">[**上位の場所**] – 各コンテンツの場所で検索クエリに一致したアイテムの数に関する統計情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="8086a-211">**Top locations** - Displays statistics about the number of items that match the search query in each content location that was searched. The top 1,000 locations are displayed.</span></span> <span data-ttu-id="8086a-212">上位 1,000 の場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-212">The top 1,000 locations are displayed.</span></span>
    
<span data-ttu-id="8086a-213">検索統計の詳細については、「[コンテンツ検索結果のキーワード統計の表示](view-keyword-statistics-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-213">For more detailed information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>
  
  
## <a name="export-search-results"></a><span data-ttu-id="8086a-214">検索結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="8086a-214">Export search results</span></span>

<span data-ttu-id="8086a-215">検索が正常に実行されると、検索結果をローカル コンピューターにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="8086a-215">After a search is successfully run, you can  export the  search results to a local computer.</span></span> <span data-ttu-id="8086a-216">メールの結果をエクスポートする場合は、PST ファイルまたは個々のメッセージ (.msg ファイル) としてコンピューターにダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="8086a-216">When you export email results, they can be downloaded to your computer as PST files or as individual messages (.msg files).</span></span> <span data-ttu-id="8086a-217">SharePoint と OneDrive のサイトからコンテンツをエクスポートする場合は、ネイティブの Office ドキュメントがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="8086a-217">When you export content from SharePoint and skydrive_pro sites, copies of native Office documents are  exported.</span></span> <span data-ttu-id="8086a-218">エクスポートされた検索結果には、上記以外のドキュメントやレポートも含まれます。</span><span class="sxs-lookup"><span data-stu-id="8086a-218">There are also additional documents and reports that are included with the exported search results.</span></span> <span data-ttu-id="8086a-219">実際のアイテムではなく、検索結果レポートをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8086a-219">You can also export the search results report and not the actual items.</span></span>
  
<span data-ttu-id="8086a-220">検索結果をエクスポートする方法。</span><span class="sxs-lookup"><span data-stu-id="8086a-220">To export search results:</span></span>
  
1. <span data-ttu-id="8086a-221">[**コンテンツ検索**] ページで、検索結果をエクスポートする対象の検索をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8086a-221">On the **Content search** page in the Security  Compliance Center, click the search that you want to export the search results for.</span></span> 
    
2. <span data-ttu-id="8086a-222">ポップアップ ページで、![検索結果のエクスポート アイコン](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) [**詳細**] をクリックしてから、[**結果のエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8086a-222">On the fly out page, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then click **Export results**. Note that you can also export a search results report.</span></span> <span data-ttu-id="8086a-223">検索結果レポートをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8086a-223">You can also export a search results report.</span></span>
    
3. <span data-ttu-id="8086a-p129">**[結果のエクスポート]** ポップアップ ページの各セクションに入力します。スクロール バーを使用して、すべてのエクスポート オプションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-p129">Complete the sections on the **Export results** fly out page. Be sure to use the scroll bar to view all export options.</span></span> 
    
<span data-ttu-id="8086a-226">詳細な手順とトラブルシューティングのヒントについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-226">For more detailed instructions and troubleshooting tips, see:</span></span>
  
- [<span data-ttu-id="8086a-227">コンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="8086a-227">Export Content Search results</span></span>](export-search-results.md)
    
- [<span data-ttu-id="8086a-228">コンテンツ検索のレポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="8086a-228">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
  
## <a name="more-information-about-content-search"></a><span data-ttu-id="8086a-229">コンテンツ検索に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="8086a-229">More information about content search</span></span>

<span data-ttu-id="8086a-230">コンテンツ検索の詳細については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-230">See the following sections for more information about content searches.</span></span>
  
[<span data-ttu-id="8086a-231">コンテンツ検索の制限</span><span class="sxs-lookup"><span data-stu-id="8086a-231">Content search limits</span></span>](#content-search-limits)
  
[<span data-ttu-id="8086a-232">検索クエリの作成</span><span class="sxs-lookup"><span data-stu-id="8086a-232">Building a search query</span></span>](#building-a-search-query)
  
[<span data-ttu-id="8086a-233">OneDrive アカウントの検索</span><span class="sxs-lookup"><span data-stu-id="8086a-233">Searching OneDrive accounts</span></span>](#searching-onedrive-accounts)
  
[<span data-ttu-id="8086a-234">Microsoft Teams と Office 365 グループの検索</span><span class="sxs-lookup"><span data-stu-id="8086a-234">Searching Microsoft Teams and Office 365 Groups</span></span>](#searching-microsoft-teams-and-office-365-groups)
  
[<span data-ttu-id="8086a-235">非アクティブなメールボックスの検索</span><span class="sxs-lookup"><span data-stu-id="8086a-235">Searching inactive mailboxes</span></span>](#searching-inactive-mailboxes)
  
[<span data-ttu-id="8086a-236">検索結果のプレビュー</span><span class="sxs-lookup"><span data-stu-id="8086a-236">Previewing search results</span></span>](#previewing-search-results)
  
[<span data-ttu-id="8086a-237">部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="8086a-237">Partially indexed items</span></span>](#partially-indexed-items)
  
### <a name="content-search-limits"></a><span data-ttu-id="8086a-238">コンテンツ検索の制限</span><span class="sxs-lookup"><span data-stu-id="8086a-238">Content search limits</span></span>

- <span data-ttu-id="8086a-239">コンテンツ検索機能に適用される制限については、「[コンテンツ検索の制限](limits-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-239">For a description of the limits that are applied to the Content Search feature, see [Limits for Search in the Office 365 Compliance Center](limits-for-content-search.md).</span></span>
    
- <span data-ttu-id="8086a-p130">すべての Office 365 組織が実行するコンテンツ検索について、Microsoft はパフォーマンス情報を収集しています。検索クエリが複雑になると、検索時間が長くなる可能性がありますが、検索時間が長くなる最も大きな要因は、検索するメールボックス数です。Microsoft は検索時間についてサービス レベル アグリーメントを提供していませんが、検索に含まれるメールボックス数に基づくコンテンツ検索の平均検索時間を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="8086a-p130">Microsoft collects performance information for Content Searches run by all Office 365 organizations. While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched. Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for a Content Search based on the number of mailboxes included in the search.</span></span>
    
|<span data-ttu-id="8086a-243">**メールボックスの数**</span><span class="sxs-lookup"><span data-stu-id="8086a-243">**Number of mailboxes**</span></span>|<span data-ttu-id="8086a-244">**検索平均時間**</span><span class="sxs-lookup"><span data-stu-id="8086a-244">**Average search time**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8086a-245">100</span><span class="sxs-lookup"><span data-stu-id="8086a-245">100</span></span>  <br/> |<span data-ttu-id="8086a-246">30 秒</span><span class="sxs-lookup"><span data-stu-id="8086a-246">30 seconds</span></span>  <br/> |
|<span data-ttu-id="8086a-247">1,000</span><span class="sxs-lookup"><span data-stu-id="8086a-247">1,000</span></span>  <br/> |<span data-ttu-id="8086a-248">45 秒</span><span class="sxs-lookup"><span data-stu-id="8086a-248">45 seconds</span></span>  <br/> |
|<span data-ttu-id="8086a-249">10,000</span><span class="sxs-lookup"><span data-stu-id="8086a-249">10,000</span></span>  <br/> |<span data-ttu-id="8086a-250">4 分</span><span class="sxs-lookup"><span data-stu-id="8086a-250">4 minutes</span></span>  <br/> |
|<span data-ttu-id="8086a-251">25,000</span><span class="sxs-lookup"><span data-stu-id="8086a-251">25,000</span></span>  <br/> |<span data-ttu-id="8086a-252">10 分</span><span class="sxs-lookup"><span data-stu-id="8086a-252">10 minutes</span></span>  <br/> |
|<span data-ttu-id="8086a-253">50,000</span><span class="sxs-lookup"><span data-stu-id="8086a-253">50,000</span></span>  <br/> |<span data-ttu-id="8086a-254">20 分</span><span class="sxs-lookup"><span data-stu-id="8086a-254">20 minutes</span></span>  <br/> |
|<span data-ttu-id="8086a-255">100,000</span><span class="sxs-lookup"><span data-stu-id="8086a-255">100,000</span></span>  <br/> |<span data-ttu-id="8086a-256">25 分</span><span class="sxs-lookup"><span data-stu-id="8086a-256">25 minutes</span></span>  <br/> |
  
### <a name="building-a-search-query"></a><span data-ttu-id="8086a-257">検索クエリの作成</span><span class="sxs-lookup"><span data-stu-id="8086a-257">Building a search query</span></span>

<span data-ttu-id="8086a-258">検索クエリの作成、ブール検索演算子と検索条件の使用、組織外のユーザーと共有する機密情報の種類とコンテンツの検索の詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-258">For detailed information about creating a search query, using Boolean search operators and search conditions, and searching for sensitive information types and content shared with users outside your organization, see [Keyword queries and search conditions for Content Search ](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="8086a-259">キーワード リストを使用して検索クエリを作成する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-259">Keeping the following things in mind when using the keyword list to create a search query.</span></span>
  
- <span data-ttu-id="8086a-p131">各行のキーワード (またはキーワード フレーズ) が **OR** 演算子でつながれる検索クエリを作成するには、[**キーワード リストの表示**] チェックボックスをオンにしてから、キーワードをそれぞれ別の行に入力する必要があります。キーワード ボックスにキーワードのリストを貼り付けたり、キーワードの入力後に **Enter** キーを押したりする場合、キーワードは **OR** 演算子でつながれません。キーワードのリストを追加する場合の正しくない例と正しい例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="8086a-p131">You have to select the **Show keyword list** checkbox and then type each keyword in a separate row to create a search query where the keywords (or keyword phrases) in each row are connected by the **OR** operator. If you just paste a list of keywords in the keyword box or press the **Enter** key after typing a keyword, they won't be connected by the **OR** operator. Here are incorrect and correct example of adding a list of keywords.</span></span> 
    
    <span data-ttu-id="8086a-263">**正しくない例**</span><span class="sxs-lookup"><span data-stu-id="8086a-263">**Incorrect**</span></span>
    
    ![キーワード リストの正しくない書式設定方法 (キーワード ボックスにリストを貼り付ける)](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    <span data-ttu-id="8086a-265">**正しい例**</span><span class="sxs-lookup"><span data-stu-id="8086a-265">**Correct**</span></span>
    
    ![キーワード リストの正しい書式設定方法 (チェックボックスをオンにしてからリストを貼り付ける)](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- <span data-ttu-id="8086a-p132">Excel ファイルまたはテキスト形式ファイルでキーワードまたはキーワード フレーズのリストを準備してから、キーワード リストに自分のリストをコピーして貼り付けることもできます。これを行うには、[**キーワード リストの表示**] チェックボックスをオンにする必要があります。次に、キーワード リストの最初の行をクリックして、リストを貼り付けます。Excel またはテキスト ファイルの行はそれぞれ、キーワード リストで異なる行に貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="8086a-p132">You can also prepare a list of keywords or keyword phrases in an Excel file or a plain text file, and then copy and paste your list in to the keyword list. To do this, you have to select the **Show keyword list** check box. Then, click the first row in the keyword list and paste your list. Each line from the Excel or text file will be pasted in to separate row in the keyword list.</span></span> 
    
- <span data-ttu-id="8086a-p133">キーワード リストを使用してクエリを作成したら、検索クエリが意図したものであることを確認することをお勧めします。詳細ウィンドウの **[クエリ]** の下に表示される検索クエリでは、キーワードは **(c:s)** というテキストで区切られます。これは、キーワードが **OR** 演算子と機能的に同様の論理演算子で接続されていることを示します。同様に、検索クエリに条件が含まれている場合、キーワードと条件は **(c:c)** というテキストで区切られます。これは、キーワードが **AND** 演算子と機能的に同様の論理演算子で条件に接続されていることを示します。キーワード リストと条件を使用した場合の結果として (詳細ウィンドウに) 表示される検索クエリの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="8086a-p133">After you create a query using the keyword list, it's a good idea to verify the search query syntax to make the search query is what you intended. In the search query that's displayed under **Query** in the details pane, the keywords are separated by the text **(c:s)**. This indicates that the keywords are connected by a logical operator similar in functionality to the **OR** operator. Similarly, if your search query includes conditions, the keywords and the conditions are separated by the text **(c:c)**. This indicates that the keywords are connected to the conditions with a logical operator similar in functionality to the **AND** operator. Here's an example of the search query (displayed in the Details pane) that results when using the keyword list and a condition.</span></span> 
    
    ![キーワード リストと条件を使用して作成するクエリの例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- <span data-ttu-id="8086a-p134">コンテンツ検索を実行すると、サポートされていない文字および大文字に変換されない可能性のあるブール演算子について、Office 365 によって検索クエリが自動的にチェックされます。サポートされていない文字は非表示になっていることがよくあり、検索エラーを発生させたり、意図しない結果を返したりする原因になります。確認が行われるサポートされていない文字の詳細については、「[コンテンツ検索クエリでエラーを確認する](check-your-content-search-query-for-errors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-p134">When you run a content search, Office 365 automatically checks your search query for unsupported characters and for Boolean operators that might not be capitalized. Unsupported characters are often hidden and typically cause a search error or return unintended results. For more information about the unsupported characters that are checked, see [Check your Content Search query for errors](check-your-content-search-query-for-errors.md).</span></span>
    
- <span data-ttu-id="8086a-p135">英語以外の文字 (中国語の文字など) のキーワードが含まれている検索クエリがある場合は、![[クエリ検索] のクエリ言語-国/地域アイコン](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) [**クエリ言語-国/地域**] をクリックし、検索対象の言語-国のカルチャ コード値を選択します。既定の言語/地域はニュートラルです。コンテンツ検索の言語設定を変更する必要があるかどうかを判断するには、以下を考慮します。コンテンツの場所に検索対象の英語以外の文字が確実に含まれているにもかかわらず、検索結果が返されない場合は、言語設定が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-p135">If you have a search query that contains keywords for non-English characters (such as Chinese characters), you can click **Query language-country/region**![Query language-country/region icon in Content search](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) and select a language-country culture code value for the search. Note that the default language/region is neutral. How can you tell if you need to change the language setting for a content search? If you're certain content locations contain the non-English characters you're searching for, but the search returns no results, the language setting might be the cause.</span></span> 
  
### <a name="searching-onedrive-accounts"></a><span data-ttu-id="8086a-285">OneDrive アカウントの検索</span><span class="sxs-lookup"><span data-stu-id="8086a-285">Searching OneDrive accounts</span></span>

- <span data-ttu-id="8086a-p136">組織内にある OneDrive サイトの URL リストの収集については、「[組織内にあるすべての OneDrive の場所のリストを作成する](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)」を参照してください。この記事のスクリプトでは、すべての OneDrive サイトのリストが含まれるテキスト ファイルが作成されます。このスクリプトを実行するには、SharePoint Online 管理シェルをインストールして使用する必要があります。検索する各 OneDrive サイトに、組織の MySite ドメインの URL を必ず追加するようにします。これは、組織のすべての OneDrive を含むドメインのことです (`https://contoso-my.sharepoint.com`)。以下は、ユーザーの OneDrive サイトの URL の例です: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`</span><span class="sxs-lookup"><span data-stu-id="8086a-p136">To collect a list of the URLs for the OneDrive sites in your organization, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). This script in this article creates a text file that contains a list of all OneDrive sites. To run this script, you'll have to install and use the SharePoint Online Management Shell. Be sure to append the URL for your organization's MySite domain to each OneDrive site that you want to search. This is the domain that contains all your OneDrive; for example,  `https://contoso-my.sharepoint.com`. Here's an example of a URL for a user's OneDrive site:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.</span></span>
    
    <span data-ttu-id="8086a-p137">まれにですが、ユーザーのユーザー プリンパル名 (UPN) が変更される場合があります。その場合、ユーザーの OneDrive の場所の URL は、新しい UPN を組み込むために変更されます。このような場合は、ユーザーの新しい OneDrive URL を追加し、古いものを削除して、コンテンツ検索を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-p137">In the rare case that a person's user principal name (UPN) is changed, the URL for their OneDrive location will also be changed to incorporate the new UPN. If this happens, you'll have to modify a content search by adding the user's new OneDrive URL and removing the old one.</span></span>
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a><span data-ttu-id="8086a-294">Microsoft Teams と Office 365 グループの検索</span><span class="sxs-lookup"><span data-stu-id="8086a-294">Searching Microsoft Teams and Office 365 Groups</span></span>

<span data-ttu-id="8086a-p138">Office 365 グループまたは Microsoft チームに関連付けられているメールボックスを検索することができます。Microsoft Teams は Office 365 グループ上に構築されているため、検索方法がよく似ています。どちらの場合も、グループまたはチームのメールボックスのみが検索されます。グループ メンバーまたはチーム メンバーのメールボックスは検索されません。検索するには、検索に明示的に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-p138">You can search the mailbox that's associated with an Office 365 Group or a Microsoft Team. Because Microsoft Teams are built on Office 365 Groups, searching them is very similar. In both cases, only the group or team mailbox is searched; the mailboxes of the group or team members aren't searched. To search them, you have to specifically add them to the search.</span></span>
  
<span data-ttu-id="8086a-300">Microsoft Teams と Office 365 グループのコンテンツを検索する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-300">Keep the following things in mind when searching for content in Microsoft Teams and Office 365 Groups.</span></span>
  
- <span data-ttu-id="8086a-301">Teams と Office 365 グループにあるコンテンツを検索するには、チームまたはグループに関連付けられているメールボックスと SharePoint サイトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-301">To search for content located in Microsoft Teams and Office 365 Groups, you have to specify the mailbox and SharePoint site that are associated with a team or group.</span></span>
    
- <span data-ttu-id="8086a-302">チームまたは Office 365 グループのプロパティを表示するには、Exchange Online で **set-unifiedgroup** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8086a-302">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for a team or an Office 365 Group.</span></span> <span data-ttu-id="8086a-303">これは、チームまたはグループに関連付けられているサイトの URL を取得するのに適した方法です。</span><span class="sxs-lookup"><span data-stu-id="8086a-303">This is a good way to get the URL for the site that's associated with a team or a group.</span></span> <span data-ttu-id="8086a-304">たとえば、次のコマンドは、上級管理職チームという名前の Office 365 グループの選択されたプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="8086a-304">For example, the following command displays selected properties for an Office365 group named Senior Leadership Team:</span></span> 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > <span data-ttu-id="8086a-305">**Get-UnifiedGroup** コマンドレットを実行するには、Exchange Online で View-Only Recipients という役割が割り当てられているか、View-Only Recipients という役割が割り当てられている役割グループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-305">To run the **Get-UnifiedGroup** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="8086a-306">ユーザーのメールボックスを検索すると、ユーザーがメンバーとなっているチームまたは Office 365 グループは検索されません。</span><span class="sxs-lookup"><span data-stu-id="8086a-306">When a user's mailbox is searched, any team or Office 365 Group that the user is a member of won't be searched.</span></span> <span data-ttu-id="8086a-307">同様に、チームまたは Office 365 グループを検索するときは、指定したグループ メールボックスとグループ サイトのみが検索されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-307">Similarly, when you search a team or an Office 365 Group, only the group mailbox and group site that you specify is searched.</span></span> <span data-ttu-id="8086a-308">グループ メンバーのメールボックスと OneDrive for Business アカウントは、検索に明示的に追加しない限り検索されません。</span><span class="sxs-lookup"><span data-stu-id="8086a-308">The mailboxes and OneDrive for Business accounts of group members aren't searched unless you explicitly add them to the search.</span></span>
    
- <span data-ttu-id="8086a-309">チームまたは Office 365 グループのメンバーの一覧を取得するには、Microsoft 365 管理センターの **[ホーム] \> [グループ]** ページでプロパティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="8086a-309">To get a list of the members of a Microsoft Team or an Office 365 Group, you can view the properties on the **Home \> Groups** page in the Office 365 admin center. Alternatively, you can run the following command in Exchange Online PowerShell:</span></span> <span data-ttu-id="8086a-310">または、Exchange Online PowerShell で次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8086a-310">To turn on audit search again, you can run the following command in Exchange Online PowerShell:</span></span> 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > <span data-ttu-id="8086a-311">**Get-UnifiedGroupLinks** コマンドレットを実行するには、Exchange Online で View-Only Recipients という役割が割り当てられているか、View-Only Recipients という役割が割り当てられている役割グループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-311">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="8086a-312">Teams チャネルに含まれる会話は、チームに関連付けられているメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-312">Conversations that are part of a Teams channel are stored in the mailbox that's associated with the team.</span></span> <span data-ttu-id="8086a-313">同様に、メンバーがチャネルで共有するファイルは、チームの SharePoint サイトに保存されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-313">Similarly, files that team members share in a channel are stored on the team's SharePoint site.</span></span> <span data-ttu-id="8086a-314">そのため、チャネルの会話やファイルを検索するには、チームのメールボックスと SharePoint サイトをコンテンツの場所として追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-314">Therefore, you have to add the team mailbox and SharePoint site as a content location to search conversations and files in a channel.</span></span>
    
- <span data-ttu-id="8086a-315">または、Teams のチャット リストに含まれる会話は、チャットに参加するユーザーの Exchange Online メールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-315">Alternatively, conversations that are part of the Chat list in Teams are stored in the Exchange Online mailbox of the users who participate in the chat.</span></span> <span data-ttu-id="8086a-316">チャットの会話でユーザーが共有するファイルは、ファイルを共有するユーザーの OneDrive for Business アカウントに保存されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-316">And files that a user shares in Chat conversations are stored in the OneDrive for Business account of the user who shares the file.</span></span> <span data-ttu-id="8086a-317">そのため、チャット リストの会話やファイルを検索するには、個々のユーザーのメールボックスと OneDrive for Business アカウントをコンテンツの場所として追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-317">Therefore, you have to add the individual user mailboxes and OneDrive for Business accounts as content locations to search conversations and files in the Chat list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8086a-318">Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャット リストの一部である会話に参加する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-318">In an Exchange hybrid deployment, users with an on-premises mailbox might participate in conversations that are part of the Chat list in Teams.</span></span> <span data-ttu-id="8086a-319">この場合も、これらの会話のコンテンツは、オンプレミスのメールボックスを持つユーザーのためにクラウドベースの記憶域 (*オンプレミス ユーザーのクラウドベースのメールボックス*と呼ばれます) に保存されるため、検索可能です。</span><span class="sxs-lookup"><span data-stu-id="8086a-319">In an Exchange hybrid deployment, users with an on-premises mailbox might participate in conversations that are part of the Chat list in Microsoft Teams. In this case, content from these conversations is also searchable because it's saved to a cloud-based storage area (called a *cloud-based mailbox for on-premises users*) for users who have an on-premises mailbox. For more information, see Searching cloud-based mailboxes for on-premises users in Office 365.</span></span> <span data-ttu-id="8086a-320">詳細については、「[Office 365 でのオンプレミス ユーザーのクラウドベースのメールボックスの検索](search-cloud-based-mailboxes-for-on-premises-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-320">For more information, see [Searching cloud-based mailboxes for on-premises users in Office 365](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
  
- <span data-ttu-id="8086a-321">各 チームまたはチーム チャネルには、メモと共同作業用の Wiki が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8086a-321">Every team or team channel contains a Wiki for note-taking and collaboration.</span></span> <span data-ttu-id="8086a-322">Wiki コンテンツは、.mht 形式のファイルに自動的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-322">The Wiki content is automatically saved to a file with a .mht format.</span></span> <span data-ttu-id="8086a-323">このファイルは、チームの SharePoint サイトの Teams Wiki データ ドキュメント ライブラリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-323">This file is stored in the Teams Wiki Data document library on the team's SharePoint site.</span></span> <span data-ttu-id="8086a-324">検索するコンテンツの場所としてチームの SharePoint サイトを指定すると、コンテンツ検索ツールを使用して Wiki を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="8086a-324">You can use the Content Search tool to search the Wiki by specifying the team's SharePoint site as the content location to search.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8086a-325">(チームの SharePoint サイトを検索する際に) チームまたはチャネルについて Wiki を検索する機能は、2017 年 6 月 22 日にリリースされました。</span><span class="sxs-lookup"><span data-stu-id="8086a-325">The capability to search the Wiki for a team or channel (when you search the team's SharePoint site) was released on June 22, 2017.</span></span> <span data-ttu-id="8086a-326">その日付以降に保存または更新された Wiki ページは検索可能です。</span><span class="sxs-lookup"><span data-stu-id="8086a-326">Wiki pages that were saved or updated on that date or after are available to be searched.</span></span> <span data-ttu-id="8086a-327">その日付より前に保存または更新された Wiki ページは、検索できません。</span><span class="sxs-lookup"><span data-stu-id="8086a-327">Wiki pages last saved or updated before that date aren't available for search.</span></span> 
 
- <span data-ttu-id="8086a-328">Teams チャネルでの会議と通話の概要情報は、会議または通話にダイヤルしたユーザーのメールボックスにも保存されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-328">Summary information for meetings and calls in a Microsoft Teams channel are also stored in the mailboxes of users who dialed into the meeting or call. This means you can use Content Search to search these summary records. Summary information includes:</span></span> <span data-ttu-id="8086a-329">つまり、コンテンツ検索を使用してこれらの概要レコードを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="8086a-329">This means you can use Content Search to search these summary records.</span></span> <span data-ttu-id="8086a-330">概要情報には次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8086a-330">Summary information includes:</span></span> 
  
  - <span data-ttu-id="8086a-331">会議または通話の日付、開始時刻、終了時刻、および継続時間</span><span class="sxs-lookup"><span data-stu-id="8086a-331">Date, start time, end time, and duration of a meeting or call</span></span>

  - <span data-ttu-id="8086a-332">各参加者の会議または通話の参加日時と退出日時</span><span class="sxs-lookup"><span data-stu-id="8086a-332">The date and time when each participant joined or left the meeting or call</span></span>

  - <span data-ttu-id="8086a-333">ボイスメールに送信された通話</span><span class="sxs-lookup"><span data-stu-id="8086a-333">Calls sent to voice mail</span></span>

  - <span data-ttu-id="8086a-334">不在着信</span><span class="sxs-lookup"><span data-stu-id="8086a-334">Missed or unanswered calls</span></span>

  - <span data-ttu-id="8086a-335">2 つの個別の通話として表される呼び出し転送</span><span class="sxs-lookup"><span data-stu-id="8086a-335">Call transfers, which are represented as two separate calls</span></span>

  <span data-ttu-id="8086a-336">会議と通話の概要レコードが検索できるようになるまで最大 8 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-336">Note that it can take up to 8 hours for meeting and call summary records to be available to be searched.</span></span>

  <span data-ttu-id="8086a-337">検索結果では、会議の概要は "**種類**" フィールドで [**会議**] として識別されます。通話の概要は [**通話**] として識別されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-337">In the search results, meeting summaries are identified as **Meeting** in the **Type field**; call summaries are identified as **Call**. Additionally, conversations that are part of a Teams channel and 1xN chats are identified as IM in the Type field.</span></span> <span data-ttu-id="8086a-338">また、Teams チャネルと 1xN チャットに含まれる会話は、"**種類**" フィールドで [**IM**] として識別されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-338">In the search results, meeting summaries are identified as Meeting in the Type field; call summaries are identified as Call. Additionally, conversations that are part of a Teams channel and 1xN chats are identified as **IM** in the **Type** field.</span></span>
  
  ![Teams の会議、通話および 1xN チャットは "種類" フィールドで識別されます。](media/O365-ContentSearch-Teams-MessageKind.png)

- <span data-ttu-id="8086a-340">"**Kind**" 電子メール プロパティまたは "**メッセージの種類**" 検索条件を使用すると、Teams のコンテンツのみを検索できます。</span><span class="sxs-lookup"><span data-stu-id="8086a-340">You can use the **Kind** email property or the **Message kind** search condition to search specifically for content in Microsoft Teams.</span></span> 
  
  - <span data-ttu-id="8086a-341">キーワード検索クエリの一部として **Kind** プロパティを使用するには、検索クエリの **[キーワード]** ボックスに `kind:microsoftteams` と入力します。</span><span class="sxs-lookup"><span data-stu-id="8086a-341">To use the **Kind** property as part of the keyword search query, in the **Keywords** box of a search query, type `kind:microsoftteams`.</span></span>

    ![[キーワード] ボックスで kind:microsoftteams を使用する](media/O365-ContentSearch-Teams-Keywords.png)
  
  - <span data-ttu-id="8086a-343">検索条件を使用するには、**[メッセージの種類]** 条件を追加し、値 `microsoftteams` を使用します。</span><span class="sxs-lookup"><span data-stu-id="8086a-343">To use a search condition, add the **Message kind** condition and use the value `microsoftteams`.</span></span> 

    ![値 microsoftteams で [メッセージの種類] 条件を使用します。](media/O365-ContentSearch-Teams-MessageKindCondition.png)

<span data-ttu-id="8086a-p149">条件が **AND** 演算子によってキーワード クエリに論理的に接続されていることに注意してください。つまり、アイテムは検索結果で返されるキーワード クエリと検索条件の両方に一致する必要があります。詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)」の「条件を使用するためのガイドライン」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-p149">Note that conditions are logically connected to the keyword query by the **AND** operator. That means an item must match both the keyword query and the search condition to be returned in the search results. For more information, see the "Guidelines for using conditions" section in [Keyword queries and search conditions for Content Search.](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)</span></span>

  
### <a name="searching-inactive-mailboxes"></a><span data-ttu-id="8086a-348">非アクティブなメールボックスの検索</span><span class="sxs-lookup"><span data-stu-id="8086a-348">Searching inactive mailboxes</span></span>

<span data-ttu-id="8086a-349">コンテンツ検索で非アクティブなメールボックスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="8086a-349">You can search inactive mailboxes in a content search.</span></span> <span data-ttu-id="8086a-350">組織内の非アクティブなメールボックスのリストを取得するには、Exchange Online PowerShell でコマンド `Get-Mailbox -InactiveMailboxOnly` を実行します。</span><span class="sxs-lookup"><span data-stu-id="8086a-350">To get a list of the inactive mailboxes in your organization so that can manage them, run the following command in Exchange Online PowerShell.</span></span> <span data-ttu-id="8086a-351">または、セキュリティ/コンプライアンス センターの [**データガバナンス**] \> [**保持**] に移動して、[**詳細**] ![ナビゲーション バーの省略記号](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> [**非アクティブなメールボックス**] をクリックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8086a-351">Alternatively, you can go to **Data governance** \> **Retention** in the Security & Compliance Center, and then click **More**![Navigation Bar ellipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Inactive mailboxes**.</span></span>
  
<span data-ttu-id="8086a-352">非アクティブなメールボックスを検索するときの留意点を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="8086a-352">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>
  
- <span data-ttu-id="8086a-353">コンテンツ検索にユーザー メールボックスが含まれ、そのメールボックスが非アクティブになった場合、非アクティブになった後に検索を再実行すると、コンテンツ検索は非アクティブなメールボックスの検索を続行します。</span><span class="sxs-lookup"><span data-stu-id="8086a-353">If a content search includes a user mailbox and that mailbox is then made inactive, the content search will continue to search the inactive mailbox when you re-run the search after it becomes inactive.</span></span>
    
- <span data-ttu-id="8086a-354">ユーザーが所有するアクティブなメールボックスと非アクティブなメールボックスの SMTP アドレスが同じ場合があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-354">Sometimes a user may have an active mailbox and an inactive mailbox that have the same SMTP address.</span></span> <span data-ttu-id="8086a-355">この場合、コンテンツ検索の場所として選択した特定のメールボックスのみが検索されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-355">In this case, only the specific mailbox that you select as a location for a content search is searched.</span></span> <span data-ttu-id="8086a-356">つまり、検索にユーザーのメールボックスを追加する場合に、アクティブなメールボックスと非アクティブなメールボックスの両方が検索されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="8086a-356">In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes are searched.</span></span> <span data-ttu-id="8086a-357">検索に明示的に追加したメールボックスのみが検索されます。</span><span class="sxs-lookup"><span data-stu-id="8086a-357">Only the mailbox that you explicitly add to the search is searched.</span></span>
    
- <span data-ttu-id="8086a-358">同じ SMTP アドレスを持つアクティブなメールボックスと非アクティブなメールボックスを所有しないようにすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8086a-358">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address.</span></span> <span data-ttu-id="8086a-359">非アクティブなメールボックスに割り当てられている SMTP アドレスを再使用する必要がある場合は、非アクティブなメールボックスを復元するか、非アクティブなメールボックスのコンテンツをアクティブなメールボックス (またはアクティブなメールボックスのアーカイブ) に復元して、非アクティブなメールボックスを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8086a-359">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address. If you need to reuse the SMTP address that is currently assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox. For more information, see one of the following topics:</span></span> <span data-ttu-id="8086a-360">詳細については、以下のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-360">For more information, see the following topics:</span></span>
    
  - [<span data-ttu-id="8086a-361">Office 365 で非アクティブなメールボックスを回復する</span><span class="sxs-lookup"><span data-stu-id="8086a-361">Recover an inactive mailbox in Office 365</span></span>](recover-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="8086a-362">Office 365 の非アクティブなメールボックスを復元する</span><span class="sxs-lookup"><span data-stu-id="8086a-362">Restore an inactive mailbox in Office 365</span></span>](restore-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="8086a-363">Office 365 の非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="8086a-363">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

  
### <a name="previewing-search-results"></a><span data-ttu-id="8086a-364">検索結果のプレビュー</span><span class="sxs-lookup"><span data-stu-id="8086a-364">Previewing search results</span></span>

<span data-ttu-id="8086a-365">サポートされているファイルの種類は、プレビュー ウィンドウでプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="8086a-365">You can preview supported file types in the preview pane.</span></span> <span data-ttu-id="8086a-366">サポートされていないファイルの種類の場合は、ファイルのコピーをローカル コンピューターにダウンロードして表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8086a-366">You can preview supported file types in the preview pane. If a file type isn't supported, you'll have to download a copy of the file to your local computer to view it. The following file types are supported and can be previewed in the search results pane.</span></span> <span data-ttu-id="8086a-367">次のファイルの種類はサポートされており、検索結果ウィンドウでプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="8086a-367">The following file types are supported and can be previewed in the search results pane.</span></span>
  
- <span data-ttu-id="8086a-368">.txt、.html、.mhtml</span><span class="sxs-lookup"><span data-stu-id="8086a-368">.txt, .html, .mhtml</span></span>
    
- <span data-ttu-id="8086a-369">.eml</span><span class="sxs-lookup"><span data-stu-id="8086a-369">.eml</span></span>
    
- <span data-ttu-id="8086a-370">.doc、.docx、.docm</span><span class="sxs-lookup"><span data-stu-id="8086a-370">.doc, .docx, .docm</span></span>
    
- <span data-ttu-id="8086a-371">.pptm、.pptx</span><span class="sxs-lookup"><span data-stu-id="8086a-371">.pptm, .pptx</span></span>
    
- <span data-ttu-id="8086a-372">.pdf</span><span class="sxs-lookup"><span data-stu-id="8086a-372">.pdf</span></span>
    
<span data-ttu-id="8086a-373">また、次のファイル コンテナーの種類もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8086a-373">Also, the following file container types are supported.</span></span> <span data-ttu-id="8086a-374">コンテナー内のファイルの一覧は、プレビュー ウィンドウで表示できます。</span><span class="sxs-lookup"><span data-stu-id="8086a-374">Additionally, the following file container types are supported. You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="8086a-375">.zip</span><span class="sxs-lookup"><span data-stu-id="8086a-375">.zip</span></span>
    
- <span data-ttu-id="8086a-376">.gzip</span><span class="sxs-lookup"><span data-stu-id="8086a-376">.gzip</span></span>
    
### <a name="partially-indexed-items"></a><span data-ttu-id="8086a-377">部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="8086a-377">Partially indexed items</span></span>

- <span data-ttu-id="8086a-378">前述のとおり、予想される検索結果には、メールボックス内の部分的にインデックスが作成されたアイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8086a-378">As previously explained, partially indexed items in mailboxes are included in the estimated search results; partially indexed items from SharePoint and OneDrive are not included in the estimated search results.</span></span> <span data-ttu-id="8086a-379">SharePoint と OneDrive からの部分的にインデックスが作成されたアイテムは、予想される検索結果に含まれません。</span><span class="sxs-lookup"><span data-stu-id="8086a-379">Partially indexed items from SharePoint and OneDrive aren't included in the estimated search results.</span></span> 
    
- <span data-ttu-id="8086a-380">(メッセージまたはドキュメントの他のプロパティが検索条件と一致するため) 部分的にインデックスが作成されたアイテムが検索クエリと一致する場合、そのアイテムはインデックスなしアイテムの推定数には含まれません。</span><span class="sxs-lookup"><span data-stu-id="8086a-380">If an unindexed item matches the search query (because other message or document properties meet the search criteria), it won't be include in the estimated number of unindexed items.</span></span> <span data-ttu-id="8086a-381">部分的にインデックスが作成されたアイテムが検索条件によって除外された場合は、そのアイテムはインデックスなしアイテムの推定数には含まれません。</span><span class="sxs-lookup"><span data-stu-id="8086a-381">If a partially indexed item is excluded by the search criteria, it isn't included in the estimated number of unindexed items.</span></span> <span data-ttu-id="8086a-382">詳細については、「[Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム](partially-indexed-items-in-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8086a-382">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md)</span></span>
