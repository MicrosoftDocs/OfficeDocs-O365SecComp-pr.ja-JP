---
title: Office 365 でのコンテンツ検索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
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
description: Office 365 セキュリティ&amp;コンプライアンスセンターでコンテンツ検索を使用して、メールボックス、SharePoint Online サイト、OneDrive アカウント、Microsoft Teams、Office 365 グループ、Skype for business の会話のコンテンツを検索します。キーワード検索クエリと検索条件を使用して、検索結果を絞り込むことができます。その後、検索結果をプレビューしてエクスポートできます。コンテンツ検索は、GDPR データ主体要求に関連する可能性があるコンテンツを検索するための効果的なツールでもあります。
ms.openlocfilehash: b7ecfc68c143225f097508e2cca0e87b7ce250d6
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296360"
---
# <a name="content-search-in-office-365"></a><span data-ttu-id="dc6be-106">Office 365 でのコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="dc6be-106">Content Search in Office 365</span></span>

<span data-ttu-id="dc6be-p102">office 365 セキュリティ&amp;コンプライアンスセンターのコンテンツ検索電子情報開示ツールを使用して、office 365 組織の電子メール、ドキュメント、インスタントメッセージの会話など、インプレースアイテムを検索することができます。このツールを使用して、これらの Office 365 サービスのアイテムを検索します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p102">You can use the Content Search eDiscovery tool in the Office 365 Security &amp; Compliance Center to search for in-place items such as email, documents, and instant messaging conversations in your Office 365 organization. Use this tool to search for items in these Office 365 services:</span></span>
  
- <span data-ttu-id="dc6be-109">Exchange Online メールボックスとパブリックフォルダー</span><span class="sxs-lookup"><span data-stu-id="dc6be-109">Exchange Online mailboxes and public folders</span></span>
    
- <span data-ttu-id="dc6be-110">SharePoint Online サイトと OneDrive for business アカウント</span><span class="sxs-lookup"><span data-stu-id="dc6be-110">SharePoint Online sites and OneDrive for Business accounts</span></span>
    
- <span data-ttu-id="dc6be-111">Skype for business の会話</span><span class="sxs-lookup"><span data-stu-id="dc6be-111">Skype for Business conversations</span></span>
    
- <span data-ttu-id="dc6be-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc6be-112">Microsoft Teams</span></span> 
    
- <span data-ttu-id="dc6be-113">Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="dc6be-113">Office 365 Groups</span></span>
    
<span data-ttu-id="dc6be-p103">コンテンツ検索を実行すると、コンテンツの場所の数と予想される検索結果の数が検索プロファイルに表示されます。検索クエリと一致するアイテムが最も多いコンテンツの場所など、統計情報をすばやく表示することもできます。検索を実行した後、結果をプレビューしたり、ローカルコンピューターにエクスポートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p103">After you run a Content Search, the number of content locations and an estimated number of search results are displayed in the search profile. You can also quickly view statistics, such as the content locations that have the most items that match the search query. After you run a search, you can preview the results or export them to a local computer.</span></span>


## <a name="create-a-new-search"></a><span data-ttu-id="dc6be-117">新しい検索を作成する</span><span class="sxs-lookup"><span data-stu-id="dc6be-117">Create a new search</span></span>

<span data-ttu-id="dc6be-p104">検索を実行して検索結果をプレビューおよびエクスポートするために**コンテンツ検索**ページにアクセスするには、管理者、コンプライアンス責任者、または電子情報開示マネージャーが、セキュリティ&amp;コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p104">To have access to the **Content search** page to run searches and preview and export search results, an administrator, compliance officer, or eDiscovery manager must be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center. For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
1. <span data-ttu-id="dc6be-120">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-120">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="dc6be-121">Office 365 メールアドレスとパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="dc6be-121">Sign in using your Office 365 email address and password.</span></span> 
    
3. <span data-ttu-id="dc6be-122">セキュリティ&amp; /コンプライアンスセンターで、[**検索&amp;調査** \> **コンテンツ検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc6be-122">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**.</span></span>
    
4. <span data-ttu-id="dc6be-123">[**検索**] ページで、[追加] アイコン![[](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **新しい検索**] の横にある矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc6be-123">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span> 
    
    ![新しい検索ドロップダウンリスト](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    <span data-ttu-id="dc6be-125">以下のいずれかのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-125">You can choose one of the following options:</span></span>
    
  - <span data-ttu-id="dc6be-p105">[**ガイド付き検索**]-このオプションを選択すると、検索を作成するための手順が示されたウィザードが起動します。コンテンツの場所を選択して検索クエリを作成するためのユーザーインターフェイスは、**新しい検索**オプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p105">**Guided search** - This option starts a wizard that guides you through the creating the search. The user interface to select content locations and build the search query are the same as the **New search** option.</span></span> 
    
  - <span data-ttu-id="dc6be-p106">[**新しい検索**]-新しい検索を作成するために更新されたユーザーインターフェイスが表示されます。これは、[**新しい検索**] をクリックした場合の既定のオプションです。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p106">**New search** - This option displays an updated user interface to create a new search. This is the default option if you click **New search**.</span></span>
    
  - <span data-ttu-id="dc6be-p107">**ID リストによる検索**-このオプションでは、Exchange id のリストを使用して特定の電子メールメッセージやその他のメールボックスアイテムを検索できます。ID リスト検索 (正式には対象化検索と呼ばれていました) を作成するには、検索する特定のメールボックスアイテムを識別するコンマ区切り値 (CSV) ファイルを送信します。手順については、「 [Office 365 で ID リストコンテンツ検索の CSV ファイルを準備する](csv-file-for-an-id-list-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p107">**Search by ID List** - This option lets you search for specific email messages and other mailbox items using a list of Exchange IDs. To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for. For instructions, see [Prepare a CSV file for an ID list Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
    
    <span data-ttu-id="dc6be-133">この手順の残りの手順は、既定の新しい検索ワークフローに従います。</span><span class="sxs-lookup"><span data-stu-id="dc6be-133">The remainder of the steps in this procedure will follow the default new search workflow.</span></span>
    
5. <span data-ttu-id="dc6be-134">ドロップダウンリストで [**新しい検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc6be-134">Click **New search** in the drop-down list.</span></span> 
    
6. <span data-ttu-id="dc6be-135">[**検索クエリ**] で、次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-135">Under **Search query**, specify the following things.</span></span>
    
    ![検索するキーワード、条件、場所を指定する](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
- <span data-ttu-id="dc6be-p108">**検索するキーワード**-[**キーワード**] ボックスに検索クエリを入力します。キーワード、メッセージプロパティ (送信日時や受信日時など)、またはファイル名、ドキュメントが最後に変更された日付などのドキュメントプロパティを指定できます。**and**、 **OR**、 **NOT**、 **NEAR**などのブール演算子を使用するより複雑なクエリを使用することができます。また、ドキュメント内の機密情報 (社会保障番号など) を検索したり、外部で共有されているドキュメントを検索したりすることもできます。[キーワード] ボックスを空のままにすると、指定したコンテンツの場所にあるすべてのコンテンツが検索結果に含まれます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p108">**Keywords to search for** - Type a search query in **Keywords** box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**. You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally. If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
    <span data-ttu-id="dc6be-p109">または、[**キーワードリストを表示**する] チェックボックスをオンにして、各行にキーワードを入力することもできます。このようにすると、各行のキーワードは、作成された検索クエリの**or**演算子の機能に似た論理演算子 ( **c:s**) によって接続されます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p109">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row. If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
    <span data-ttu-id="dc6be-p110">キーワードリストを使用する理由各キーワードに一致するアイテムの数を示す統計情報を取得することができます。これにより、どのキーワードが最もよく (かつ最も少ない) 有効であるかをすばやく識別することができます。また、行内のキーワード句 (かっこで囲む) を使用することもできます。検索統計の詳細については、「[コンテンツ検索結果のキーワード統計情報を表示](view-keyword-statistics-for-content-search.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p110">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>

    [!NOTE] <span data-ttu-id="dc6be-149">大きなキーワードリストによって発生する問題を減らすために、キーワード一覧では最大20行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="dc6be-149">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list.</span></span>
    
- <span data-ttu-id="dc6be-p111">**条件**-検索条件を追加して、検索結果を絞り込んだり、より洗練された結果セットを返すことができます。各条件は、検索を開始するときに作成され、実行される句を検索クエリに追加します。条件は、論理演算子 ( **c:c**) によって論理的に (キーワードボックスで指定された) キーワードクエリに関連付けられています。これは、 **and 演算子と**機能が似ています。つまり、アイテムは、キーワードクエリと、結果に含まれる1つ以上の条件を満たす必要があることを意味します。このようにすると、条件によって結果を絞り込むことができます。検索クエリで使用できる条件の一覧と説明については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md#search-conditions)」の「検索条件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p111">**Conditions** - You can add search conditions to narrow a search and return a more refined set of results. Each condition adds a clause to the search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator ( **c:c**) that is similar in functionality to the **AND** operator. That means that items have to satisfy both the keyword query and one or more conditions to be included in the results. This is how conditions help to narrow your results. For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
    
- <span data-ttu-id="dc6be-156">**場所**-検索するコンテンツの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-156">**Locations** - Choose the content locations to search.</span></span>
    
  - <span data-ttu-id="dc6be-p112">[**すべての場所**] 組織内のすべてのコンテンツの場所を検索するには、このオプションを使用します。これには、すべての Exchange メールボックス (非アクティブなすべてのメールボックス、すべての Office 365 グループのメールボックス、すべての Microsoft Teams のメールボックスなど)、すべての Skype for business の会話、すべての SharePoint および OneDrive for business サイト (サイトを含む) などのメールが含まれます。すべての Office 365 グループと Microsoft Teams)、およびすべての Exchange パブリックフォルダー内のアイテム。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p112">**All locations** - Use this option to search all content locations in your organization. This includes email in all Exchange mailboxes (including all inactive mailboxes, mailboxes for all Office 365 Groups, mailboxes for all Microsoft Teams), all Skype for Business conversations, all SharePoint and OneDrive for Business sites (including the sites for all Office 365 Groups and Microsoft Teams), and items in all Exchange public folders.</span></span>
    
  - <span data-ttu-id="dc6be-p113">**特定の場所**-特定のコンテンツの場所を検索するには、このオプションを使用します。特定の office 365 サービスのすべてのコンテンツの場所を検索できます (すべての Exchange メールボックスを検索したり、すべての SharePoint サイトを検索したりするなど)。または、表示されている office 365 サービスの特定の場所を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p113">**Specific locations** - Use this option to search specific content locations. You can search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or search all SharePoint sites) or you can search specific locations in any of the Office 365 services that are displayed.</span></span> 
    
    ![検索するコンテンツの場所を選択するためのユーザーインターフェイス](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
    <span data-ttu-id="dc6be-p114">また、検索する Exchange メールボックスの一覧に配布グループを追加することもできます。配布グループの場合、グループメンバーのメールボックスが検索されます。動的配布グループはサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p114">Note that you can also add distribution groups to the list of Exchange mailboxes to search. For distribution groups, the mailboxes of group members are searched. Note that dynamic distribution groups aren't supported.</span></span>
    
    <span data-ttu-id="dc6be-p115">**重要:** すべてのメールボックスの場所または特定のメールボックスだけを検索すると、コンテンツ検索の結果をエクスポートするときに、myanalytics と、ユーザーのメールボックスに保存されている他の Office 365 アプリケーションのデータが含まれます。このデータは、推定検索結果には含まれません。プレビューでは使用できません。これは、検索結果をエクスポートおよびダウンロードするときにのみ含まれます。「コンテンツ検索に関する詳細情報」の「 [myanalytics およびその他の Office 365 アプリケーションからのデータのエクスポート](#exporting-data-from-myanalytics-and-other-office-365-applications)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p115">**Important:** When you search all mailbox locations or just specific mailboxes, data from MyAnalytics and other Office 365 applications that's saved to user mailboxes will be included when you export the results of a Content Search. This data will not be included in the estimated search results and it won't be available for preview. It will only be included when you export and download the search results; see [Exporting data from MyAnalytics and other Office 365 applications](#exporting-data-from-myanalytics-and-other-office-365-applications) in the "More information about content search" section.</span></span> 
    
7. <span data-ttu-id="dc6be-168">検索クエリを設定したら、[ **Save &amp; run**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc6be-168">After you've set up your search query, click **Save &amp; run**.</span></span>
    
8. <span data-ttu-id="dc6be-p116">[**検索の保存**] ページで、検索の名前と、検索を識別するために使用できる説明 (オプション) を入力します。検索の名前は、組織内で一意である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p116">On the **Save search** page, type a name for the search, and an optional description that helps identify the search. Note that the name of the search has to be unique in your organization.</span></span> 
    
9. <span data-ttu-id="dc6be-171">[**保存**] をクリックして検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-171">Click **Save** to start the search.</span></span> 
    
    <span data-ttu-id="dc6be-p117">検索を保存して実行すると、検索によって返された結果が結果ウィンドウに表示されます。プレビュー設定の構成方法によっては、検索結果が表示されるか、[**結果のプレビュー** ] をクリックして表示する必要があります。詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p117">After you save and run the search, any results returned by the search are displayed in the results pane. Depending on how you have the preview setting configured, the search results are display or you have to click **Preview results** to view them. See the next section for details.</span></span> 
    
<span data-ttu-id="dc6be-175">このコンテンツ検索に再度アクセスするか、**コンテンツ検索**ページにリストされている他のコンテンツ検索にアクセスするには、検索を選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc6be-175">To access this content search again or access other content searches listed on the **Content search** page, select the search and then click **Open**.</span></span> 
  
<span data-ttu-id="dc6be-176">結果をクリアするか、新しい検索を作成する![には](media/O365-MDM-CreatePolicy-AddIcon.gif) 、[追加] アイコン [**新しい検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc6be-176">To clear the results or create a new search, click ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif) **New search**.</span></span> 

  
## <a name="preview-search-results"></a><span data-ttu-id="dc6be-177">検索結果のプレビュー</span><span class="sxs-lookup"><span data-stu-id="dc6be-177">Preview search results</span></span>

<span data-ttu-id="dc6be-p118">検索結果をプレビューするには、2つの構成設定を行います。新しい検索を実行するか、既存の検索を開いた後、\* \* 個別の結果 \* \* をクリックして、次のプレビュー設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p118">There are two configuration settings for previewing search results. After you run a new a new search or open an existing search, click \*\* Individual results \*\* to view the following preview settings:</span></span> 
  
![検索結果の設定をプレビューする](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. <span data-ttu-id="dc6be-181">[**結果を自動的にプレビュー**する]-この設定は、検索を実行した後に検索結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-181">**Preview results automatically** - This setting displays the search results after you a run a search.</span></span>
    
2. <span data-ttu-id="dc6be-p119">[**結果を手動でプレビュー**する]-この設定を使用すると、[検索結果] ウィンドウにプレースホルダーが表示され、検索結果を表示するためにクリックする必要がある [結果の**プレビュー** ] ボタンが表示されます。これは既定の設定です。既存の検索を開いたときに検索結果が自動的に表示されないため、検索のパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p119">**Preview results manually** - This setting displays placeholders in the search results pane, and displays the **Preview results** button that you have to click to display the search results. This is the default setting; it helps enhance search performance by not automatically displaying the search results when you open an existing search.</span></span> 
    
<span data-ttu-id="dc6be-p120">プレビューできるアイテムの数に関連する制限があります。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターでの検索の制限](limits-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p120">There are limits related to how many items are available to be previewed. For more information, see [Limits for Search in the Office 365 Security &amp; Compliance Center](limits-for-content-search.md).</span></span> 
  
<span data-ttu-id="dc6be-p121">プレビューできるサポートされているファイルの種類の一覧については、「コンテンツ検索に関する詳細情報」の「[検索結果のプレビュー](#previewing-search-results) 」を参照してください。ファイルの種類がプレビューでサポートされていない場合や、ドキュメントのコピーをダウンロードする場合は、[**元のファイルをダウンロード**] をクリックして、ローカルコンピューターにダウンロードします。.aspx Web ページの場合は、ページの URL が含まれますが、ページにアクセスするアクセス許可を持っていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p121">For a list of supported file types that can be previewed, see [Previewing search results](#previewing-search-results) in the "More information about content search" section. If a file type isn't supported for preview or to download a copy of a document, you can click **Download original file** to download it to your local computer. For .aspx Web pages, the URL for the page is included though you might not have permissions to access the page.</span></span> 
  
<span data-ttu-id="dc6be-189">また、インデックスを持たないアイテムはプレビューできないことにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-189">Also note that unindexed items aren't available for previewing.</span></span>
  
## <a name="view-information-and-statistics-about-a-search"></a><span data-ttu-id="dc6be-190">検索に関する情報と統計情報を表示する</span><span class="sxs-lookup"><span data-stu-id="dc6be-190">View information and statistics about a search</span></span>

<span data-ttu-id="dc6be-p122">コンテンツ検索を作成して実行すると、予想される検索結果に関する統計情報を表示できます。これには、検索結果の概要、検索クエリと一致するアイテムが含まれるコンテンツの場所の数、最も一致するアイテムを含むコンテンツの場所の名前などが含まれます。1つまたは複数のコンテンツ検索の統計を表示できます。これにより、複数の検索の結果をすばやく比較し、検索クエリの有効性を判断することができます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p122">After you create and run a content search, you can view statistics about the estimated search results. This includes a summary of the search results, the query statistics such as the number of content locations with items that match the search query, and the name of content locations that have the most matching items. You can display statistics for one or more content searches. This lets you to quickly compare the results for multiple searches and make decisions about the effectiveness of your search queries.</span></span>
  
<span data-ttu-id="dc6be-p123">また、検索の統計情報とキーワードの統計情報を CSV ファイルにダウンロードできます。これにより、Excel のフィルター機能や並べ替え機能を使用して結果を比較し、検索結果のレポートを準備できます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p123">You can also download the search statistics and keyword statistics to a CSV file. This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
<span data-ttu-id="dc6be-197">検索の統計情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="dc6be-197">To view search statistics:</span></span>
  
1. <span data-ttu-id="dc6be-198">セキュリティ&amp; /コンプライアンスセンターの [**コンテンツ検索**] ページで、[**開く**] をクリックし、統計情報を表示する検索をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc6be-198">On the **Content search** page in the Security &amp; Compliance Center, click **Open** and then click the search that you want to view the statistic for.</span></span> 
    
2. <span data-ttu-id="dc6be-199">[フライアウト] ページで、[**クエリを開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc6be-199">On the fly out page, click **Open query**.</span></span> 
    
3. <span data-ttu-id="dc6be-200">[**個々の結果**] ドロップダウンリストで、[**検索プロファイル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc6be-200">In the **Individual results** drop down list, click **Search profile**.</span></span>
    
4. <span data-ttu-id="dc6be-201">[**種類**] ドロップダウンリストで、表示する検索統計に応じて、次のいずれかのオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc6be-201">In the **Type** drop down list, click one of the following options depending on the search statistics you want to view.</span></span> 
    
  - <span data-ttu-id="dc6be-p124">**Summary** -検索したコンテンツの場所の種類ごとに統計情報を表示します。このコンテンツには、検索クエリに一致したアイテムが含まれているコンテンツの場所の数と、検索結果のアイテムの合計数とサイズが表示されます。これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p124">**Summary** - Displays statistics for each type of content locations searched. This contents the number of content locations that contained items that matched the search query, and the total number and size of search result items. This is the default setting.</span></span>
    
  - <span data-ttu-id="dc6be-p125">**クエリ**-検索クエリについての統計を表示します。これには、クエリの統計が適用されるコンテンツの場所の種類、統計を適用できる検索クエリの一部 (**プライマリ**は検索クエリ全体を示すことに注意してください)、アイテムが含まれるコンテンツの場所の数が含まれます。検索クエリと一致し、検索クエリに一致する合計数とサイズ、および検出されたアイテムの総数 (指定されたコンテンツの場所)。インデックスが設定されていないアイテム (部分的にインデックスが付いているアイテム) の統計も表示されることに注意してください。ただし、統計情報には、メールボックスの一部のインデックス付きアイテムのみが含まれています。SharePoint および OneDrive からの部分的にインデックスが作成されたアイテムは統計に含まれません。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p125">**Queries** - Displays statistics about the search query. This includes the type of content location the query statistics are applicable to, part of the search query the statistics are applicable to (note that **Primary** indicates the entire search query), the number of the content locations that contain items that match the search query, and the total number and size and items that were found (in the specified content location) that match the search query. Note that statistics for unindexed items (also called partially indexed items) are also displayed. However, only partially indexed items from mailboxes are included in the statistics. Partially indexed items from SharePoint and OneDrive are not included in the statistics.</span></span>
    
  - <span data-ttu-id="dc6be-p126">[**上位の場所**-検索された各コンテンツの場所の検索クエリと一致するアイテムの数に関する統計を表示します。上位の1000の場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p126">**Top locations** - Displays statistics about the number of items that match the search query in each content location that was searched. The top 1,000 locations are displayed.</span></span>
    
<span data-ttu-id="dc6be-212">検索統計の詳細については、「[コンテンツ検索結果のキーワード統計](view-keyword-statistics-for-content-search.md)情報を表示する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-212">For more detailed information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>
  
  
## <a name="export-search-results"></a><span data-ttu-id="dc6be-213">検索結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="dc6be-213">Export search results</span></span>

<span data-ttu-id="dc6be-p127">検索が正常に実行されたら、検索結果をローカルコンピューターにエクスポートできます。電子メールの結果をエクスポートする場合は、PST ファイルとして、または個別のメッセージ (.msg ファイル) としてコンピューターにダウンロードできます。SharePoint および OneDrive サイトからコンテンツをエクスポートすると、ネイティブの Office ドキュメントのコピーがエクスポートされます。エクスポートされた検索結果には、追加のドキュメントとレポートも含まれています。実際のアイテムではなく、検索結果レポートをエクスポートするだけでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p127">After a search is successfully run, you can export the search results to a local computer. When you export email results, they can be downloaded to your computer as PST files or as individual messages (.msg files). When you export content from SharePoint and OneDrive sites, copies of native Office documents are exported. There are also additional documents and reports that are included with the exported search results. You can also just export the search results report and not the actual items.</span></span>
  
<span data-ttu-id="dc6be-219">検索結果をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="dc6be-219">To export search results:</span></span>
  
1. <span data-ttu-id="dc6be-220">セキュリティ&amp; /コンプライアンスセンターの [**コンテンツ検索**] ページで、[**開く**] をクリックし、検索結果をエクスポートする検索をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc6be-220">On the **Content search** page in the Security &amp; Compliance Center, click **Open** and then click the search that you want to export the search results for.</span></span> 
    
2. <span data-ttu-id="dc6be-p128">[フライアウト] ページで、 ![[検索結果アイコン](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \*\*\*\* のエクスポート] をクリックし、[**結果のエクスポート**] をクリックします。なお、検索結果レポートをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p128">On the fly out page, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then click **Export results**. Note that you can also export a search results report.</span></span>
    
3. <span data-ttu-id="dc6be-p129">**[結果のエクスポート]** ポップアップ ページの各セクションに入力します。スクロール バーを使用して、すべてのエクスポート オプションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p129">Complete the sections on the **Export results** fly out page. Be sure to use the scroll bar to view all export options.</span></span> 
    
<span data-ttu-id="dc6be-225">詳細な手順とトラブルシューティングのヒントについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-225">For more detailed instructions and troubleshooting tips, see:</span></span>
  
- [<span data-ttu-id="dc6be-226">Office 365 セキュリティ&amp;コンプライアンスセンターから検索結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="dc6be-226">Export search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
- [<span data-ttu-id="dc6be-227">コンテンツ検索のレポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="dc6be-227">Export a Content Search report</span></span>](export-a-content-search-report.md)
    

  
## <a name="more-information-about-content-search"></a><span data-ttu-id="dc6be-228">コンテンツ検索の詳細情報</span><span class="sxs-lookup"><span data-stu-id="dc6be-228">More information about content search</span></span>

<span data-ttu-id="dc6be-229">コンテンツ検索の詳細については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-229">See the following sections for more information about content searches.</span></span>
  
[<span data-ttu-id="dc6be-230">コンテンツ検索の制限</span><span class="sxs-lookup"><span data-stu-id="dc6be-230">Content search limits</span></span>](#content-search-limits)
  
[<span data-ttu-id="dc6be-231">検索クエリを作成する</span><span class="sxs-lookup"><span data-stu-id="dc6be-231">Building a search query</span></span>](#building-a-search-query)
  
[<span data-ttu-id="dc6be-232">OneDrive アカウントの検索</span><span class="sxs-lookup"><span data-stu-id="dc6be-232">Searching OneDrive accounts</span></span>](#searching-onedrive-accounts)
  
[<span data-ttu-id="dc6be-233">Microsoft Teams と Office 365 グループの検索</span><span class="sxs-lookup"><span data-stu-id="dc6be-233">Searching Microsoft Teams and Office 365 Groups</span></span>](#searching-microsoft-teams-and-office-365-groups)
  
[<span data-ttu-id="dc6be-234">非アクティブなメールボックスの検索</span><span class="sxs-lookup"><span data-stu-id="dc6be-234">Searching inactive mailboxes</span></span>](#searching-inactive-mailboxes)
  
[<span data-ttu-id="dc6be-235">検索結果のプレビュー</span><span class="sxs-lookup"><span data-stu-id="dc6be-235">Previewing search results</span></span>](#previewing-search-results)
  
[<span data-ttu-id="dc6be-236">部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="dc6be-236">Partially indexed items</span></span>](#partially-indexed-items)
  
[<span data-ttu-id="dc6be-237">myanalytics およびその他の Office 365 アプリケーションからのデータのエクスポート</span><span class="sxs-lookup"><span data-stu-id="dc6be-237">Exporting data from MyAnalytics and other Office 365 applications</span></span>](#exporting-data-from-myanalytics-and-other-office-365-applications)
  
### <a name="content-search-limits"></a><span data-ttu-id="dc6be-238">コンテンツ検索の制限</span><span class="sxs-lookup"><span data-stu-id="dc6be-238">Content search limits</span></span>

- <span data-ttu-id="dc6be-239">コンテンツ検索機能に適用される制限の説明については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターでの検索の制限](limits-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-239">For a description of the limits that are applied to the Content Search feature, see [Limits for Search in the Office 365 Security &amp; Compliance Center](limits-for-content-search.md).</span></span>
    
- <span data-ttu-id="dc6be-p130">Microsoft は、すべての Office 365 組織で実行されるコンテンツ検索のパフォーマンス情報を収集します。検索クエリの複雑さは検索時間に影響する場合がありますが、検索時間に影響を与える最大要因は、検索するメールボックスの数です。Microsoft は検索時間のサービスレベル契約を提供していませんが、次の表に、検索に含まれるメールボックスの数に基づいて、コンテンツ検索の平均検索時間を示します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p130">Microsoft collects performance information for Content Searches run by all Office 365 organizations. While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched. Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for a Content Search based on the number of mailboxes included in the search.</span></span>
    
|<span data-ttu-id="dc6be-243">**メールボックスの数**</span><span class="sxs-lookup"><span data-stu-id="dc6be-243">**Number of mailboxes**</span></span>|<span data-ttu-id="dc6be-244">**平均検索時間**</span><span class="sxs-lookup"><span data-stu-id="dc6be-244">**Average search time**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dc6be-245">100</span><span class="sxs-lookup"><span data-stu-id="dc6be-245">100</span></span>  <br/> |<span data-ttu-id="dc6be-246">30 秒</span><span class="sxs-lookup"><span data-stu-id="dc6be-246">30 seconds</span></span>  <br/> |
|<span data-ttu-id="dc6be-247">1,000</span><span class="sxs-lookup"><span data-stu-id="dc6be-247">1,000</span></span>  <br/> |<span data-ttu-id="dc6be-248">45秒</span><span class="sxs-lookup"><span data-stu-id="dc6be-248">45 seconds</span></span>  <br/> |
|<span data-ttu-id="dc6be-249">10,000</span><span class="sxs-lookup"><span data-stu-id="dc6be-249">10,000</span></span>  <br/> |<span data-ttu-id="dc6be-250">4 分</span><span class="sxs-lookup"><span data-stu-id="dc6be-250">4 minutes</span></span>  <br/> |
|<span data-ttu-id="dc6be-251">25000</span><span class="sxs-lookup"><span data-stu-id="dc6be-251">25,000</span></span>  <br/> |<span data-ttu-id="dc6be-252">10 分</span><span class="sxs-lookup"><span data-stu-id="dc6be-252">10 minutes</span></span>  <br/> |
|<span data-ttu-id="dc6be-253">5万</span><span class="sxs-lookup"><span data-stu-id="dc6be-253">50,000</span></span>  <br/> |<span data-ttu-id="dc6be-254">20 分</span><span class="sxs-lookup"><span data-stu-id="dc6be-254">20 minutes</span></span>  <br/> |
|<span data-ttu-id="dc6be-255">100,000</span><span class="sxs-lookup"><span data-stu-id="dc6be-255">100,000</span></span>  <br/> |<span data-ttu-id="dc6be-256">25 分</span><span class="sxs-lookup"><span data-stu-id="dc6be-256">25 minutes</span></span>  <br/> |
  
### <a name="building-a-search-query"></a><span data-ttu-id="dc6be-257">検索クエリを作成する</span><span class="sxs-lookup"><span data-stu-id="dc6be-257">Building a search query</span></span>

<span data-ttu-id="dc6be-258">検索クエリの作成、ブール検索演算子と検索条件の使用、組織外のユーザーと共有する機密情報の種類とコンテンツの検索の詳細については、「[キーワードクエリと検索条件」を参照してください。コンテンツ検索の場合](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="dc6be-258">For detailed information about creating a search query, using Boolean search operators and search conditions, and searching for sensitive information types and content shared with users outside your organization, see [Keyword queries and search conditions for Content Search ](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="dc6be-259">キーワードリストを使用して検索クエリを作成する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-259">Keeping the following things in mind when using the keyword list to create a search query.</span></span>
  
- <span data-ttu-id="dc6be-p131">[**キーワードリストを表示**する] チェックボックスをオンにしてから、それぞれの行に各キーワードを入力して検索クエリを作成し、各行のキーワード (またはキーワードフレーズ) が**or**演算子で接続されていることを確認する必要があります。キーワードの一覧をキーワードボックスに貼り付けるだけの場合、またはキーワードを入力した後に**enter**キーを押した場合、 **or**演算子によって接続されることはありません。以下に、キーワードの一覧を追加する間違った正しい例を示します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p131">You have to select the **Show keyword list** checkbox and then type each keyword in a separate row to create a search query where the keywords (or keyword phrases) in each row are connected by the **OR** operator. If you just paste a list of keywords in the keyword box or press the **Enter** key after typing a keyword, they won't be connected by the **OR** operator. Here are incorrect and correct example of adding a list of keywords.</span></span> 
    
    <span data-ttu-id="dc6be-263">**不正確**</span><span class="sxs-lookup"><span data-stu-id="dc6be-263">**Incorrect**</span></span>
    
    ![キーワードリストを書式設定する方法が正しくありません ([キーワード] ボックスにリストを貼り付けます)。](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    <span data-ttu-id="dc6be-265">**そうです**</span><span class="sxs-lookup"><span data-stu-id="dc6be-265">**Correct**</span></span>
    
    ![キーワードリストを書式設定する正しい方法 (チェックボックスをオンにしてからリストを貼り付ける)](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- <span data-ttu-id="dc6be-p132">また、Excel ファイルまたはプレーンテキストファイル内のキーワードやキーワード語句の一覧を準備し、そのリストをキーワードリストにコピーして貼り付けることもできます。これを行うには、[**キーワードリストを表示**する] チェックボックスをオンにする必要があります。次に、[キーワード] ボックスの最初の行をクリックし、リストを貼り付けます。Excel またはテキストファイルの各行は、キーワードリストの別の行に貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p132">You can also prepare a list of keywords or keyword phrases in an Excel file or a plain text file, and then copy and paste your list in to the keyword list. To do this, you have to select the **Show keyword list** check box. Then, click the first row in the keyword list and paste your list. Each line from the Excel or text file will be pasted in to separate row in the keyword list.</span></span> 
    
- <span data-ttu-id="dc6be-p133">キーワードリストを使用してクエリを作成した後は、検索クエリの構文を確認して検索クエリを実行することをお勧めします。詳細ウィンドウの [**クエリ**] の下に表示される検索クエリでは、キーワードはテキスト **(c:s)** で区切られています。これは、キーワードが論理演算子によって接続されていることを示します。この値**は、or**演算子との機能のようになります。同様に、検索クエリに条件が含まれている場合、キーワードと条件はテキスト **(c:c)** によって区切られます。これは、キーワードが**と**の機能と同様に、論理演算子を使用して条件に接続されていることを示します。演算子.キーワードリストと条件を使用した場合に発生する検索クエリ (詳細ウィンドウに表示される) の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p133">After you create a query using the keyword list, it's a good idea to verify the search query syntax to make the search query is what you intended. In the search query that's displayed under **Query** in the details pane, the keywords are separated by the text **(c:s)**. This indicates that the keywords are connected by a logical operator similar in functionality to the **OR** operator. Similarly, if your search query includes conditions, the keywords and the conditions are separated by the text **(c:c)**. This indicates that the keywords are connected to the conditions with a logical operator similar in functionality to the **AND** operator. Here's an example of the search query (displayed in the Details pane) that results when using the keyword list and a condition.</span></span> 
    
    ![キーワードリストと条件を使用して作成されたクエリの例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- <span data-ttu-id="dc6be-p134">コンテンツ検索を実行すると、Office 365 は、サポートされていない文字および大文字にならないブール演算子について、検索クエリを自動的にチェックします。サポートされていない文字は通常は非表示になり、通常は検索エラーが発生するか、予期しない結果が返されます。チェックされているサポートされていない文字の詳細については、「[コンテンツ検索クエリでエラーをチェック](check-your-content-search-query-for-errors.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p134">When you run a content search, Office 365 automatically checks your search query for unsupported characters and for Boolean operators that might not be capitalized. Unsupported characters are often hidden and typically cause a search error or return unintended results. For more information about the unsupported characters that are checked, see [Check your Content Search query for errors](check-your-content-search-query-for-errors.md).</span></span>
    
- <span data-ttu-id="dc6be-p135">英語以外の文字 (中国語文字など) のキーワードが含まれている検索クエリがある場合は、[**クエリ言語-国/地域**![クエリ言語] をクリックし、[コンテンツ検索](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) ] の国/地域アイコンを選択して、検索の言語-国のカルチャコード値。既定の言語/地域はニュートラルであることに注意してください。コンテンツ検索の言語設定を変更する必要があるかどうかを判断するには、どうすればよいですか。特定のコンテンツの場所に英語以外の文字が含まれていて、検索結果が返されない場合は、言語設定が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p135">If you have a search query that contains keywords for non-English characters (such as Chinese characters), you can click **Query language-country/region**![Query language-country/region icon in Content search](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) and select a language-country culture code value for the search. Note that the default language/region is neutral. How can you tell if you need to change the language setting for a content search? If you're certain content locations contain the non-English characters you're searching for, but the search returns no results, the language setting might be the cause.</span></span> 
  
### <a name="searching-onedrive-accounts"></a><span data-ttu-id="dc6be-285">OneDrive アカウントの検索</span><span class="sxs-lookup"><span data-stu-id="dc6be-285">Searching OneDrive accounts</span></span>

- <span data-ttu-id="dc6be-p136">組織内の onedrive サイトの url の一覧を収集するには、「[組織内のすべての onedrive の場所の一覧を作成](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)する」を参照してください。この記事のこのスクリプトでは、すべての OneDrive サイトの一覧を含むテキストファイルを作成します。このスクリプトを実行するには、SharePoint Online 管理シェルをインストールして使用する必要があります。検索する各 OneDrive サイトに、組織の個人用サイトドメインの URL を追加してください。これは、すべての OneDrive を含むドメインです。たとえば、 `https://contoso-my.sharepoint.com`のようになります。ユーザーの OneDrive サイト`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`の URL の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p136">To collect a list of the URLs for the OneDrive sites in your organization, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). This script in this article creates a text file that contains a list of all OneDrive sites. To run this script, you'll have to install and use the SharePoint Online Management Shell. Be sure to append the URL for your organization's MySite domain to each OneDrive site that you want to search. This is the domain that contains all your OneDrive; for example,  `https://contoso-my.sharepoint.com`. Here's an example of a URL for a user's OneDrive site:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.</span></span>
    
    <span data-ttu-id="dc6be-p137">ユーザープリンシパル名 (UPN) が変更された場合、そのユーザーの OneDrive の場所の URL も新しい upn を組み込むように変更されます。このような場合は、ユーザーの新しい OneDrive URL を追加して古いバージョンを削除することによって、コンテンツ検索を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p137">In the rare case that a person's user principal name (UPN) is changed, the URL for their OneDrive location will also be changed to incorporate the new UPN. If this happens, you'll have to modify a content search by adding the user's new OneDrive URL and removing the old one.</span></span>
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a><span data-ttu-id="dc6be-294">Microsoft Teams と Office 365 グループの検索</span><span class="sxs-lookup"><span data-stu-id="dc6be-294">Searching Microsoft Teams and Office 365 Groups</span></span>

<span data-ttu-id="dc6be-p138">Office 365 グループまたは Microsoft チームに関連付けられているメールボックスを検索できます。Microsoft Teams は Office 365 グループ上に構築されているため、それらを検索するのは非常によく似ています。どちらの場合も、グループまたはチームのメールボックスのみが検索されます。グループまたはチームメンバーのメールボックスは検索されません。検索するには、それらを検索に明示的に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p138">You can search the mailbox that's associated with an Office 365 Group or a Microsoft Team. Because Microsoft Teams are built on Office 365 Groups, searching them is very similar. In both cases, only the group or team mailbox is searched; the mailboxes of the group or team members aren't searched. To search them, you have to specifically add them to the search.</span></span>
  
<span data-ttu-id="dc6be-299">Microsoft Teams と Office 365 グループのコンテンツを検索する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-299">Keep the following things in mind when searching for content in Microsoft Teams and Office 365 Groups.</span></span>
  
- <span data-ttu-id="dc6be-300">Microsoft Teams および Office 365 グループにあるコンテンツを検索するには、チームまたはグループに関連付けられているメールボックスと SharePoint サイトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc6be-300">To search for content located in Microsoft Teams and Office 365 Groups, you have to specify the mailbox and SharePoint site that are associated with a team or group.</span></span>
    
- <span data-ttu-id="dc6be-p139">Microsoft teams または Office 365 グループのプロパティを表示するには、Exchange Online で**set-unifiedgroup**コマンドレットを実行します。チームまたはグループに関連付けられているサイトの URL を取得するには、この方法を使用することをお勧めします。たとえば、次のコマンドを実行すると、シニアリーダーシップチームという名前の Office 365 グループに対して選択されたプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p139">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for a Microsoft Team or an Office 365 Group. This is a good way to get the URL for the site that's associated with a team or a group. For example, the following command displays selected properties for an Office 365 Group named Senior Leadership Team:</span></span> 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > <span data-ttu-id="dc6be-304">**set-unifiedgroup**コマンドレットを実行するには、Exchange Online で表示専用受信者の役割が割り当てられているか、または表示専用の受信者の役割が割り当てられている役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc6be-304">To run the **Get-UnifiedGroup** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="dc6be-p140">ユーザーのメールボックスを検索すると、そのユーザーがメンバーになっている Microsoft teams または Office 365 グループは検索されません。同様に、Microsoft teams または Office 365 グループを検索すると、指定したグループメールボックスとグループサイトのみが検索されます。グループメンバーのメールボックスと OneDrive for business アカウントは、検索に明示的に追加しない限り、検索されません。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p140">When a user's mailbox is searched, any Microsoft Team or Office 365 Group that the user is a member of won't be searched. Similarly, when you search a Microsoft Team or an Office 365 Group, only the group mailbox and group site that you specify is searched; the mailboxes and OneDrive for Business accounts of group members aren't searched unless you explicitly add them to the search.</span></span>
    
- <span data-ttu-id="dc6be-p141">Microsoft teams または office 365 グループのメンバーの一覧を取得するには、office 365 管理センターの [**ホーム\>グループ**] ページでプロパティを表示します。または、Exchange Online PowerShell で次のコマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p141">To get a list of the members of a Microsoft Team or an Office 365 Group, you can view the properties on the **Home \> Groups** page in the Office 365 admin center. Alternatively, you can run the following command in Exchange Online PowerShell:</span></span> 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > <span data-ttu-id="dc6be-309">**UnifiedGroupLinks**コマンドレットを実行するには、Exchange Online で表示専用受信者の役割が割り当てられているか、または表示専用の受信者の役割が割り当てられている役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc6be-309">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="dc6be-p142">microsoft Teams チャネルの一部である会話は、microsoft Teams に関連付けられているメールボックスに保存されます。同様に、チームメンバーがチャネルで共有するファイルは、チームの SharePoint サイトに格納されます。そのため、チャネル内の会話やファイルを検索するには、コンテンツの場所として Microsoft teams メールボックスと SharePoint サイトを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p142">Conversations that are part of a Microsoft Teams channel are stored in the mailbox that's associated with the Microsoft Team. Similarly, files that team members share in a channel are stored on the team's SharePoint site. Therefore, you have to add the Microsoft Team mailbox and SharePoint site as a content location to search conversations and files in a channel.</span></span>
    
- <span data-ttu-id="dc6be-p143">または、Microsoft Teams のチャットリストに含まれる会話が、チャットに参加しているユーザーの Exchange Online メールボックスに保存されます。また、ユーザーがチャット会話で共有しているファイルは、そのファイルを共有しているユーザーの OneDrive for business アカウントに保存されます。そのため、会話やファイルを検索するためのコンテンツの場所として、個々のユーザーのメールボックスと OneDrive for business のアカウントを、チャットリストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p143">Alternatively, conversations that are part of the Chat list in Microsoft Teams are stored in the Exchange Online mailbox of the users who participate in the chat. And files that a user shares in Chat conversations are stored in the OneDrive for Business account of the user who shares the file. Therefore, you have to add the individual user mailboxes and OneDrive for Business accounts as content locations to search conversations and files in the Chat list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dc6be-p144">Exchange ハイブリッド展開では、オンプレミスのメールボックスを使用しているユーザーは、Microsoft Teams のチャットリストの一部である会話に参加できます。この場合、オンプレミスのメールボックスを持つユーザーのために、これらの会話のコンテンツは、クラウドベースのストレージ領域 (*オンプレミスユーザーのクラウドベースのメールボックス*と呼ばれます) に保存されるため、検索可能になります。詳細については、「 [Office 365 でのオンプレミスユーザーのクラウドベースのメールボックスの検索](search-cloud-based-mailboxes-for-on-premises-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p144">In an Exchange hybrid deployment, users with an on-premises mailbox might participate in conversations that are part of the Chat list in Microsoft Teams. In this case, content from these conversations is also searchable because it's saved to a cloud-based storage area (called a *cloud-based mailbox for on-premises users*) for users who have an on-premises mailbox. For more information, see [Searching cloud-based mailboxes for on-premises users in Office 365](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
  
- <span data-ttu-id="dc6be-p145">Microsoft のすべてのチームまたはチームのチャネルには、メモを取り、共同作業のための Wiki が含まれています。Wiki コンテンツは、.mht 形式のファイルに自動的に保存されます。このファイルは、チームの SharePoint サイト上の Teams Wiki データドキュメントライブラリに格納されます。コンテンツ検索ツールを使用して Wiki を検索するには、検索するコンテンツの場所としてチームの SharePoint サイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p145">Every Microsoft Team or team channel contains a Wiki for note-taking and collaboration. The Wiki content is automatically saved to a file with a .mht format. This file is stored in the Teams Wiki Data document library on the team's SharePoint site. You can use the Content Search tool to search the Wiki by specifying the team's SharePoint site as the content location to search.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="dc6be-p146">Wiki で Microsoft teams または Channel (チームの SharePoint サイトを検索する場合) を検索する機能は、2017年6月22日にリリースされました。その日付またはそれ以降に保存または更新された Wiki ページは検索できるようになります。その日付以前に保存または更新された Wiki ページは、検索には使用できません。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p146">The capability to search the Wiki for a Microsoft Team or Channel (when you search the team's SharePoint site) was released on June 22, 2017. Wiki pages that were saved or updated on that date or after are available to be searched. Wiki pages last saved or updated before that date aren't available for search.</span></span> 
 
- <span data-ttu-id="dc6be-p147">Microsoft Teams チャネルでの会議と通話の概要情報は、会議または通話にダイヤルしたユーザーのメールボックスにも保存されます。これは、コンテンツ検索を使用してこれらの要約レコードを検索できることを意味します。概要情報は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p147">Summary information for meetings and calls in a Microsoft Teams channel are also stored in the mailboxes of users who dialed into the meeting or call. This means you can use Content Search to search these summary records. Summary information includes:</span></span> 
  - <span data-ttu-id="dc6be-329">日付、開始時刻、終了時刻、および会議または通話の期間</span><span class="sxs-lookup"><span data-stu-id="dc6be-329">Date, start time, end time, and duration of a meeting or call</span></span>

  - <span data-ttu-id="dc6be-330">各参加者が会議または電話会議に参加または退出した日時</span><span class="sxs-lookup"><span data-stu-id="dc6be-330">The date and time when each participant joined or left the meeting or call</span></span>

  - <span data-ttu-id="dc6be-331">ボイスメールに送信された通話</span><span class="sxs-lookup"><span data-stu-id="dc6be-331">Calls sent to voice mail</span></span>

  - <span data-ttu-id="dc6be-332">不在着信または不在着信</span><span class="sxs-lookup"><span data-stu-id="dc6be-332">Missed or unanswered calls</span></span>

  - <span data-ttu-id="dc6be-333">2つの個別の通話として表される通話転送</span><span class="sxs-lookup"><span data-stu-id="dc6be-333">Call transfers, which are represented as two separate calls</span></span>

  <span data-ttu-id="dc6be-334">会議と通話のサマリーレコードが検索できるようになるまで最大8時間かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-334">Note that it can take up to 8 hours for meeting and call summary records to be available to be searched.</span></span>

  <span data-ttu-id="dc6be-p148">検索結果では、[**種類] フィールド**で会議の概要が**会議**として識別されます。通話の概要は、**通話**として識別されます。また、Teams チャネルと1xn チャットの一部である会話は、[**種類**] フィールドで**IM**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p148">In the search results, meeting summaries are identified as **Meeting** in the **Type field**; call summaries are identified as **Call**. Additionally, conversations that are part of a Teams channel and 1xN chats are identified as **IM** in the **Type** field.</span></span>
  
  ![Teams の会議、通話、および1xn のチャットは、[種類] フィールドで特定されます。](media/O365-ContentSearch-Teams-MessageKind.png)

- <span data-ttu-id="dc6be-338">**Kind** email プロパティまたは**Message kind**検索条件を使用して、Microsoft Teams のコンテンツを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-338">You can use the **Kind** email property or the **Message kind** search condition to search specifically for content in Microsoft Teams.</span></span> 
  - <span data-ttu-id="dc6be-339">キーワード検索クエリの一部として**Kind**プロパティを使用するには、検索クエリの [**キーワード**] ボックス`kind:microsoftteams`に「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-339">To use the **Kind** property as part of the keyword search query, in the **Keywords** box of a search query, type `kind:microsoftteams`.</span></span>

    ![[キーワード] ボックスに次のような種類を使用します。](media/O365-ContentSearch-Teams-Keywords.png)
  
  - <span data-ttu-id="dc6be-341">検索条件を使用するには、**メッセージの種類**の条件を追加`microsoftteams`し、値を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-341">To use a search condition, add the **Message kind** condition and use the value `microsoftteams`.</span></span> 

    ![「microsoft teams」という値を使用して、メッセージの種類の条件を使用します。](media/O365-ContentSearch-Teams-MessageKindCondition.png)

<span data-ttu-id="dc6be-p149">条件は、 **and**演算子によってキーワードクエリに論理的に接続されていることに注意してください。これは、アイテムが検索結果で返されるように、キーワードクエリと検索条件の両方に一致する必要があることを意味します。詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)」の「条件を使用するためのガイドライン」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p149">Note that conditions are logically connected to the keyword query by the **AND** operator. That means an item must match both the keyword query and the search condition to be returned in the search results. For more information, see the "Guidelines for using conditions" section in [Keyword queries and search conditions for Content Search.](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)</span></span>

  
### <a name="searching-inactive-mailboxes"></a><span data-ttu-id="dc6be-346">非アクティブなメールボックスの検索</span><span class="sxs-lookup"><span data-stu-id="dc6be-346">Searching inactive mailboxes</span></span>

<span data-ttu-id="dc6be-p150">コンテンツ検索で非アクティブなメールボックスを検索できます。組織内の非アクティブなメールボックスの一覧を取得するには`Get-Mailbox -InactiveMailboxOnly` 、Exchange Online PowerShell でコマンドを実行します。または\> 、セキュリティ&amp;コンプライアンスセンターの [**データガバナンス** \> **の保持**] に移動して、 **[その他**![の](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)ナビゲーションバーの**非アクティブなメールボックス**] をクリックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p150">You can search inactive mailboxes in a content search. To get a list of the inactive mailboxes in your organization, run the command  `Get-Mailbox -InactiveMailboxOnly` in Exchange Online PowerShell. Alternatively, you can go to **Data governance** \> **Retention** in the Security &amp; Compliance Center, and then click **More**![Navigation Bar ellipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Inactive mailboxes**.</span></span>
  
<span data-ttu-id="dc6be-350">非アクティブなメールボックスを検索する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-350">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>
  
- <span data-ttu-id="dc6be-351">コンテンツ検索にユーザーのメールボックスが含まれていて、そのメールボックスが非アクティブになっている場合、コンテンツ検索は、非アクティブになった後に検索を再実行すると、非アクティブなメールボックスの検索を続行します。</span><span class="sxs-lookup"><span data-stu-id="dc6be-351">If a content search includes a user mailbox and that mailbox is then made inactive, the content search will continue to search the inactive mailbox when you re-run the search after it becomes inactive.</span></span>
    
- <span data-ttu-id="dc6be-p151">場合によっては、ユーザーが同じ SMTP アドレスを持つアクティブなメールボックスと非アクティブなメールボックスを持っている場合があります。この場合、コンテンツ検索の場所として指定した特定のメールボックスのみが検索されます。言い換えると、ユーザーのメールボックスを検索に追加した場合、アクティブなメールボックスと非アクティブなメールボックスの両方が検索されるとは限りません。検索に明示的に追加したメールボックスのみが検索されます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p151">In some cases, a user may have an active mailbox and an inactive mailbox that have the same SMTP address. In this case, only the specific mailbox that you select as a location for a content search will be searched. In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes will be searched; only the mailbox that you explicitly add to the search will be searched.</span></span>
    
- <span data-ttu-id="dc6be-p152">同じ SMTP アドレスを持つアクティブなメールボックスと非アクティブなメールボックスを使用しないことを強くお勧めします。非アクティブなメールボックスに現在割り当てられている SMTP アドレスを再利用する必要がある場合は、非アクティブなメールボックスを回復するか、非アクティブなメールボックスのコンテンツをアクティブなメールボックス (またはアクティブなメールボックスのアーカイブ) に復元することをお勧めします。非アクティブなメールボックス。詳細については、以下のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p152">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address. If you need to reuse the SMTP address that is currently assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox. For more information, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="dc6be-358">Office 365 で非アクティブなメールボックスを回復する</span><span class="sxs-lookup"><span data-stu-id="dc6be-358">Recover an inactive mailbox in Office 365</span></span>](recover-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="dc6be-359">Office 365 で非アクティブなメールボックスを復元する</span><span class="sxs-lookup"><span data-stu-id="dc6be-359">Restore an inactive mailbox in Office 365</span></span>](restore-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="dc6be-360">Office 365 で非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="dc6be-360">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

  
### <a name="previewing-search-results"></a><span data-ttu-id="dc6be-361">検索結果のプレビュー</span><span class="sxs-lookup"><span data-stu-id="dc6be-361">Previewing search results</span></span>

<span data-ttu-id="dc6be-p153">サポートされているファイルの種類は、プレビューウィンドウでプレビューできます。ファイルの種類がサポートされていない場合は、ファイルのコピーをローカルコンピューターにダウンロードして表示する必要があります。次のファイルの種類がサポートされており、[検索結果] ウィンドウでプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p153">You can preview supported file types in the preview pane. If a file type isn't supported, you'll have to download a copy of the file to your local computer to view it. The following file types are supported and can be previewed in the search results pane.</span></span>
  
- <span data-ttu-id="dc6be-365">.txt、.html、mhtml</span><span class="sxs-lookup"><span data-stu-id="dc6be-365">.txt, .html, .mhtml</span></span>
    
- <span data-ttu-id="dc6be-366">.eml</span><span class="sxs-lookup"><span data-stu-id="dc6be-366">.eml</span></span>
    
- <span data-ttu-id="dc6be-367">.doc、.docx、.docm</span><span class="sxs-lookup"><span data-stu-id="dc6be-367">.doc, .docx, .docm</span></span>
    
- <span data-ttu-id="dc6be-368">. pptm、.pptx</span><span class="sxs-lookup"><span data-stu-id="dc6be-368">.pptm, .pptx</span></span>
    
- <span data-ttu-id="dc6be-369">.pdf</span><span class="sxs-lookup"><span data-stu-id="dc6be-369">.pdf</span></span>
    
<span data-ttu-id="dc6be-p154">さらに、次のファイルコンテナーの種類がサポートされています。[プレビュー] ウィンドウで、コンテナー内のファイルの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p154">Additionally, the following file container types are supported. You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="dc6be-372">.zip</span><span class="sxs-lookup"><span data-stu-id="dc6be-372">.zip</span></span>
    
- <span data-ttu-id="dc6be-373">gzip</span><span class="sxs-lookup"><span data-stu-id="dc6be-373">.gzip</span></span>
    
### <a name="partially-indexed-items"></a><span data-ttu-id="dc6be-374">部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="dc6be-374">Partially indexed items</span></span>

- <span data-ttu-id="dc6be-375">前述のように、メールボックス内の一部のインデックス付きアイテムは、推定される検索結果に含まれています。SharePoint と OneDrive からの部分的にインデックスが作成されたアイテムは、推定検索結果には含まれません。</span><span class="sxs-lookup"><span data-stu-id="dc6be-375">As previously explained, partially indexed items in mailboxes are included in the estimated search results; partially indexed items from SharePoint and OneDrive are not included in the estimated search results.</span></span> 
    
- <span data-ttu-id="dc6be-p155">部分的なアイテムが検索クエリに一致した場合 (他のメッセージまたはドキュメントのプロパティが検索条件を満たしているため)、インデックスが設定されていないアイテムの推定数に含まれません。部分的なアイテムが検索条件によって除外されても、部分的にインデックスが作成されたアイテムの推定数に含まれません。詳細については、「 [Office 365 のコンテンツ検索での一部のインデックス付きアイテム](partially-indexed-items-in-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p155">If a partially item matches the search query (because other message or document properties meet the search criteria), it won't be included in the estimated number of unindexed items. If an partially item is excluded by the search criteria, it also won't be included in the estimated number of partially indexed items. For more information, see [Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md).</span></span>
    
### <a name="exporting-data-from-myanalytics-and-other-office-365-applications"></a><span data-ttu-id="dc6be-379">myanalytics およびその他の Office 365 アプリケーションからのデータのエクスポート</span><span class="sxs-lookup"><span data-stu-id="dc6be-379">Exporting data from MyAnalytics and other Office 365 applications</span></span>

- <span data-ttu-id="dc6be-p156">myanalytics からのデータ (ユーザーが自分のメールボックス内のメールおよび予定表のデータに基づいてどのように時間を費やしているかについての洞察など)、および他の Office 365 アプリケーションからのデータは、ユーザーのクラウドベースのメールボックスの非表示の場所 (IPM サブツリー内) に保存されます。コンテンツ検索を実行した後は、このデータは推定検索結果、クエリ統計情報には含まれず、プレビューでは使用できません。ただし、このデータは、検索の結果をエクスポートするときにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p156">Data from MyAnalytics (such as insights on how users spend their time based on mail and calendar data in their mailbox) and data from other Office 365 applications is a saved to a hidden location (in a non-IPM subtree) in user's cloud-based mailbox. After you run a Content Search, this data isn't included in the estimated search results, the query statistics, and it isn't available for preview. However this data will be exported when you export the results of a search.</span></span>
    
- <span data-ttu-id="dc6be-p157">myanalytics データと他の office 365 アプリケーションからのデータは、"その他の office 365 データ" という名前のフォルダーにエクスポートされます。このフォルダーには、各ユーザーのサブフォルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc6be-p157">The MyAnalytics data and the data from other Office 365 applications is exported to a folder named "Other Office 365 data". This folder includes subfolders for each user.</span></span>
  
