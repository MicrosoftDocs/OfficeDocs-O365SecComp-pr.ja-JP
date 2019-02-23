---
title: Advanced eDiscovery で保留リストを管理する (プレビュー)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8dbcc73dac14dddfeb8dd86bbf03d9e845dac510
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215847"
---
# <a name="manage-holds-in-advanced-ediscovery-preview"></a><span data-ttu-id="889d4-102">Advanced eDiscovery で保留リストを管理する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="889d4-102">Manage holds in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="889d4-p101">高度な電子情報開示 (プレビュー) ケースを使用して、ケースに関連する可能性があるコンテンツを保持するためのホールドを作成できます。Advanced eDiscovery (プレビュー) 保持機能を使用すると、保管担当者とそのデータソースに保持を配置できます。さらに、メールボックスおよび OneDrive for business サイトに、非 wi-fi ダイヤルを保持することができます。また、Office 365 グループのグループメールボックス、SharePoint サイト、OneDrive for business サイトにホールドを配置することもできます。同様に、Microsoft Teams に関連付けられているメールボックスおよびサイトにホールドを配置することができます。コンテンツの場所を保持する場合、コンテンツは保管担当者を解放するか、特定のデータの場所を削除するか、保留ポリシー全体を削除するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="889d4-p101">You can use an Advanced eDiscovery (Preview) case to create holds to preserve content that might be relevant to your case. Using the Advanced eDiscovery (Preview) hold capabilities, you can place holds on custodians and their data sources. Additionally, you can place a non-custodial hold on mailboxes and OneDrive for Business sites. You can also place a hold on the group mailbox, SharePoint site, and OneDrive for Business site for an Office 365 Group. Similarly, you can place a hold on the mailbox and site that are associated with Microsoft Teams. When you place content locations on hold, content is held until you release the custodian, remove a specific data location, or delete the hold policy entirely.</span></span>

## <a name="manage-custodian-based-holds"></a><span data-ttu-id="889d4-109">保管担当者ベースの保持を管理する</span><span class="sxs-lookup"><span data-stu-id="889d4-109">Manage custodian-based holds</span></span>

<span data-ttu-id="889d4-p102">場合によっては、特定して保持するように設定した一連のデータ保管担当者が存在することがあります。Advanced eDiscovery (プレビュー) では、これらの保管担当者が保留になっている場合、ユーザーと選択されたデータソースが保管担当者保留ポリシーに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="889d4-p102">In some cases, you may have a set of data custodians that you have identified and choosen to preserve. In Advanced eDiscovery (Preview), when these custodians are placed on hold, the user and their selected data sources are automatically added to a custodian hold policy.</span></span> 

<span data-ttu-id="889d4-112">保管担当者ホールドポリシーを表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="889d4-112">To view the custodian hold policy:</span></span>

1. <span data-ttu-id="889d4-113">**セキュリティ & コンプライアンスセンター**で、[**電子情報開示 > Advanced ediscovery (プレビュー)** ] をクリックして、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="889d4-113">In the **Security & Compliance Center**, click **eDiscovery > Advanced eDiscovery (Preview)** to display the list of cases in your organization.</span></span>
   
2. <span data-ttu-id="889d4-p103">ケース内に保管担当者を追加するには、[**保管担当者**] タブに移動します。高度な電子情報開示 (プレビュー) ケース内で保管担当者を追加して保存する方法については、「 [add 保管担当者 to a advanced ediscovery (preview) ケース](add-custodians-to-case.md)」を参照してください。保管担当者を既に追加していて、保留リストに配置している場合は、手順3に進みます。</span><span class="sxs-lookup"><span data-stu-id="889d4-p103">Go to the **Custodians** tab to add custodians within your case. To learn how you can add and place custodians on hold within an Advanced eDiscovery (Preview) case, see [Add Custodians to an Advanced eDiscovery (Preview) Case](add-custodians-to-case.md). If you have already added custodians and placed them on hold, go to step 3.</span></span>
   
3. <span data-ttu-id="889d4-117">[**保留**] タブに移動し、[保管担当者 Policy] を選択します。</span><span class="sxs-lookup"><span data-stu-id="889d4-117">Go to the **Holds** tab and select the 'Custodian Policy'.</span></span>
   
4. <span data-ttu-id="889d4-p104">フライアウトページには、ポリシーの [ホールド] の統計が表示されます。また、保管担当者ベースのホールドにクエリを適用するなどの操作を実行することもできます。保留クエリの作成と条件の使用の詳細については、「[コンテンツ検索のキーワードクエリと検索条件](../keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="889d4-p104">In the flyout page, you can see hold statistics for the policy. You can also perform actions like apply a query to your custodian-based hold. For more information about creating a hold query and using conditions, see [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md).</span></span>
 
## <a name="manage-non-custodial-holds"></a><span data-ttu-id="889d4-121">非 wi-fi ダイヤルの保持を管理する</span><span class="sxs-lookup"><span data-stu-id="889d4-121">Manage non-custodial holds</span></span>

<span data-ttu-id="889d4-122">保留リストを作成する場合は、次のオプションを使用して、指定されたコンテンツの場所に保持されているコンテンツの範囲を設定します。</span><span class="sxs-lookup"><span data-stu-id="889d4-122">When you create a hold, you have the following options to scope the content that is held in the specified content locations:</span></span>

  - <span data-ttu-id="889d4-p105">すべてのコンテンツを保留にする無限ホールドを作成します。または、検索クエリに一致するコンテンツのみが保持されるように、クエリベースの保持を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="889d4-p105">You create an infinite hold where all content is placed on hold. Alternatively, you can create a query-based hold where only content that matches a search query is placed on hold.</span></span>
  - <span data-ttu-id="889d4-p106">日付範囲を指定して、その期間内に送信、受信、または作成されたコンテンツのみを保持することができます。または、送信、受信、または作成の日時に関係なく、すべてのコンテンツを保持できます。</span><span class="sxs-lookup"><span data-stu-id="889d4-p106">You can specify a date range to hold only the content that was sent, received, or created within that date range. Alternatively, you can hold all content regardless of when it was sent, received, or created.</span></span>

<span data-ttu-id="889d4-127">高度な電子情報開示 (プレビュー) ケースの保留リストを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="889d4-127">To create a hold for an Advanced eDiscovery (Preview) case:</span></span>

1. <span data-ttu-id="889d4-128">**セキュリティ & コンプライアンスセンター**で、[**電子情報開示 > Advanced ediscovery (プレビュー)** ] をクリックして、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="889d4-128">In the **Security & Compliance Center**, click **eDiscovery > Advanced eDiscovery (Preview)** to display the list of cases in your organization.</span></span>
  
2. <span data-ttu-id="889d4-129">ホールドを作成するケースの横にある [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="889d4-129">Click **Open** next to the case that you want to create the holds in.</span></span>
  
3. <span data-ttu-id="889d4-130">大文字と小文字のホームページから、[**保留**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="889d4-130">From the home page for the case, click the **Holds** tab.</span></span>
  
4. <span data-ttu-id="889d4-131">[**保留**] タブで、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="889d4-131">On the **Holds** tab, click **Create**.</span></span>
  
5. <span data-ttu-id="889d4-p107">[**保留リストに名前**を付ける] ページで、ホールドに名前を付けます。保留の名前は、組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="889d4-p107">On the **Name your hold** page, give the hold a name. The name of the hold must be unique in your organization.</span></span>
 
6. <span data-ttu-id="889d4-134">オプション[**説明**] ボックスに、保留リストの説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="889d4-134">(Optional) In the **Description** box, add a description of the hold.</span></span>
  
7. <span data-ttu-id="889d4-135">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="889d4-135">Click **Next**.</span></span>
  
8. <span data-ttu-id="889d4-p108">保持するコンテンツの場所を選択します。メールボックス、サイト、パブリックフォルダーを保持に配置することができます。</span><span class="sxs-lookup"><span data-stu-id="889d4-p108">Choose the content locations that you want to place on hold. You can place mailboxes, sites, and public folders on hold.</span></span>

   <span data-ttu-id="889d4-p109">a. **Exchange 電子メール**-[**ユーザー、グループ、またはチームを選択**] をクリックし、[**ユーザー、グループ、または teams**を再度選択する] をもう一度クリックして、保持するメールボックスを指定します。検索ボックスを使用して、ユーザーのメールボックスと配布グループを検索します (グループメンバーのメールボックスを保留にする場合)。また、Office 365 グループまたは Microsoft チームに対して、関連付けられたメールボックスにホールドを配置することもできます。[ユーザー、グループ、チーム] チェックボックスをオンにし、[**選択**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="889d4-p109">a. **Exchange email** - Click **Choose users, groups, or teams** and then click **Choose users, groups, or teams** again to specify mailboxes to place on hold. Use the search box to find user mailboxes and distribution groups (to place a hold on the mailboxes of group members) to place on hold. You can also place a hold on the associated mailbox for an Office 365 Group or a Microsoft Team. Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="889d4-p110">[**ユーザー、グループ、またはチームの選択**] をクリックしてメールボックスを保留にするように指定すると、表示されているメールボックスピッカーは空になります。これは、パフォーマンスを向上させるための仕様です。このリストにユーザーを追加するには、検索ボックスに名前 (少なくと3文字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="889d4-p110">When you click **Choose users, groups, or teams** to specify mailboxes to place on hold, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>

    <span data-ttu-id="889d4-p111">b. **sharepoint サイト**-[**サイトの選択**] をクリックし、[**サイトの選択**] をもう一度クリックして、保持する SharePoint および OneDrive for business サイトを指定します。保持する各サイトの URL を入力します。Office 365 グループまたは Microsoft チームの SharePoint サイトの URL を追加することもできます。[**選択**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="889d4-p111">b. **SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify SharePoint and OneDrive for Business sites to place on hold. Type the URL for each site that you want to place on hold. You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team. Click **Choose**, and then click **Done**.</span></span>
    
     <span data-ttu-id="889d4-151">Office 365 グループと Microsoft Teams を保持する方法に関するヒントについては、 **FAQ**セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="889d4-151">See the **FAQ** section for tips on putting Office 365 Groups and Microsoft Teams on hold.</span></span>

    > [!NOTE]
    > <span data-ttu-id="889d4-p112">ユーザープリンシパル名 (UPN) が変更された場合、そのユーザーの OneDrive アカウントの URL も新しい upn を組み込むように変更されます。このような場合は、ユーザーの新しい OneDrive URL を追加して古いバージョンを削除することによって、保留リストを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="889d4-p112">In the rare case that a person's user principal name (UPN) has changed, the URL for their OneDrive account will also be changed to incorporate the new UPN. If this happens, you'll have to modify the hold by adding the user's new OneDrive URL and removing the old one.</span></span>

     <span data-ttu-id="889d4-p113">c. **exchange パブリックフォルダー** -切り替えスイッチをすべての位置に移動して、Exchange Online 組織内のすべてのパブリックフォルダーを保持します。特定のパブリックフォルダーを保持の対象にすることはできないことに注意してください。パブリックフォルダーを保持しない場合は、トグルスイッチを **[なし**] のままにします。</span><span class="sxs-lookup"><span data-stu-id="889d4-p113">c. **Exchange public folders** - Move the toggle switch to the All position to put all public folders in your Exchange Online organization on hold. Note that you can't choose specific public folders to put on hold. Leave the toggle switch set to **None** if you don't want to put a hold on public folders.</span></span>

9. <span data-ttu-id="889d4-158">保留リストにコンテンツの場所を追加し終わったら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="889d4-158">When you're done adding content locations to the hold, click **Next**.</span></span>
  
10. <span data-ttu-id="889d4-p114">条件を使用してクエリベースの保持を作成するには、次の手順を実行します。それ以外の場合は、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="889d4-p114">To create a query-based hold with conditions, complete the following. Otherwise, just click **Next**.</span></span>
    
    - <span data-ttu-id="889d4-p115">検索条件に一致するコンテンツのみが保持されるようにするには、[**キーワード**] の下のボックスに検索クエリを入力します。ファイル名などの、キーワード、メッセージプロパティ、またはドキュメントプロパティを指定できます。ブール演算子 (AND、or、NOT など) を使用するより複雑なクエリを使用することもできます。[キーワード] ボックスを空白のままにすると、指定したコンテンツの場所にあるすべてのコンテンツが保持されます。</span><span class="sxs-lookup"><span data-stu-id="889d4-p115">In the box under **Keywords**, type a search query in the box so that only the content that meets the search criteria is placed on hold. You can specify keywords, message properties, or document properties, such as file names. You can also use more complex queries that use a Boolean operator, such as AND, OR, or NOT. If you leave the keyword box empty, then all content located in the specified content locations will be placed on hold.</span></span>

    - <span data-ttu-id="889d4-p116">[条件の**追加**] をクリックして、1つまたは複数の条件を追加して、保留リストの検索クエリを絞り込みます。各条件は、保留を作成するときに作成および実行される kql 検索クエリに句を追加します。たとえば、日付範囲を指定して、指定した期間内に作成された電子メールまたはサイトのドキュメントが保留リストに配置されるようにすることができます。and 演算子を使って、条件が論理的にキーワードクエリ (キーワード box で指定) に接続されています。これは、アイテムがキーワードクエリと条件の両方に一致する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="889d4-p116">Click  **Add** conditions to add one or more conditions to narrow the search query for the hold. Each condition adds a clause to the KQL search query that is created and run when you create the hold. For example you can specify a date range so that email or site documents that were created within the date ranged are placed on hold. A condition is logically connected to the keyword query (specified in the keyword box) by the AND operator. That means that items have to satisfy both the keyword query and the condition to be placed on hold.</span></span>

     <span data-ttu-id="889d4-170">検索クエリの作成と条件の使用の詳細については、「[コンテンツ検索のキーワードクエリと検索条件](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="889d4-170">For more information about creating a search query and using conditions, see [Keyword queries and search conditions for Content Search](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions).</span></span>

12. <span data-ttu-id="889d4-171">クエリベースの保持を構成した後、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="889d4-171">After configuring a query-based hold, click **Next**.</span></span>
 
13. <span data-ttu-id="889d4-172">設定内容を確認し、[**このホールドを作成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="889d4-172">Review your settings, and then click **Create this hold**.</span></span>


## <a name="view-hold-statistics"></a><span data-ttu-id="889d4-173">保留の統計を表示する</span><span class="sxs-lookup"><span data-stu-id="889d4-173">View hold statistics</span></span>

<span data-ttu-id="889d4-p117">しばらくすると、選択した保留リストの [**保留**] タブの [詳細] ウィンドウに、新しい保留リストに関する情報が表示されます。この情報には、保留になっているアイテムの合計数とサイズ、保持統計情報が最後に計算されたときなど、保留中のコンテンツに関するメールボックスとサイトの数および統計情報が含まれます。これらの保持統計情報は、電子情報開示ケースに関連するコンテンツの量を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="889d4-p117">After some time, information about the new hold is displayed in the details pane on the **Holds** tab for the selected hold. This information includes the number of mailboxes and sites on hold and statistics about the content that was placed on hold, such as the total number and size of items placed on hold and the last time the hold statistics were calculated. These hold statistics help you identify how much content that's related to the eDiscovery case is being held.</span></span>

<span data-ttu-id="889d4-177">保持の統計情報については、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="889d4-177">Keep the following things in mind about hold statistics:</span></span>

- <span data-ttu-id="889d4-p118">保留中のアイテムの合計数は、保留になっているすべてのコンテンツソースからのアイテムの数を示します。クエリベースの保持を作成した場合、この統計情報はクエリに一致するアイテムの数を示します。</span><span class="sxs-lookup"><span data-stu-id="889d4-p118">The total number of items on hold indicates the number of items from all content sources that are placed on hold. If you've created a query-based hold, this statistic indicates the number of items that match the query.</span></span>
  
- <span data-ttu-id="889d4-p119">保留中のアイテム数には、コンテンツの場所にあるインデックスがないアイテムも含まれます。クエリベースの保持を作成すると、コンテンツの場所にあるすべてのインデックスのないアイテムが保持されます。これには、クエリベースの保持の検索条件に一致しないインデックスのないアイテムと、日付範囲の範囲外にある可能性のあるインデックスを持たないアイテムが含まれます。これは、検索クエリと一致しない、または日付範囲の条件によって除外されたインデックスのないアイテムが検索結果に含まれていない場合に、コンテンツ検索を実行したときの動作とは異なります。インデックスが設定されていないアイテムの詳細については、「 [Office 365 のコンテンツ検索でのインデックスのあるアイテム](../partially-indexed-items-in-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="889d4-p119">The number of items on hold also includes unindexed items found in the content locations. Note that if you create a query-based hold, all unindexed items in the content locations are placed on hold. This includes unindexed items that don't match the search criteria of a query-based hold and unindexed items that might fall outside of a date range condition. This is different than what happens when you run a Content Search, in which unindexed items that don't match the search query or are excluded by a date range condition aren't included in the search results. For more information about unindexed items, see [Partially indexed items in Content Search in Office 365](../partially-indexed-items-in-content-search.md).</span></span> 

- <span data-ttu-id="889d4-185">最新の保持統計情報を取得するには、[統計情報の更新] をクリックして、保留中の現在のアイテム数を計算する検索推定を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="889d4-185">You can get the latest hold statistics by clicking Update statistics to re-run a search estimate that calculates the current number of items on hold.</span></span>

- <span data-ttu-id="889d4-186">必要に応じて、ツールバーの [更新] をクリックして、[詳細] ウィンドウで保持の統計情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="889d4-186">If necessary, click Refresh in the toolbar to update the hold statistics in the details pane.</span></span>

- <span data-ttu-id="889d4-187">メールボックスまたはサイトが保持されているユーザーは、通常、新しい電子メールメッセージを送信または受信し、新しい SharePoint および OneDrive for business ドキュメントを作成することによって、保留中のアイテム数が増加します。</span><span class="sxs-lookup"><span data-stu-id="889d4-187">It's normal for the number of items on hold to increase over time because users whose mailbox or site is on hold are typically sending or receiving new email message and creating new SharePoint and OneDrive for Business documents.</span></span>

- <span data-ttu-id="889d4-p120">SharePoint サイトまたは OneDrive アカウントが複数地域環境の別の地域に移動されても、そのサイトの統計情報は保持の統計情報には含まれません。ただし、サイト内のコンテンツは保留中のままになります。また、サイトが別の地域に移動された場合、保留リストに表示される URL は更新されません。ホールドを編集して、URL を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="889d4-p120">If a SharePoint site or OneDrive account is moved to a different region in a multi-geo environment, the statistics for that site won't be included in the hold statistics. However, the content in the site will still be on hold. Also, if a site is moved to a different region the URL that's displayed in the hold will not be updated. You'll have to edit the hold and update the URL.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="889d4-192">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="889d4-192">Frequently asked questions</span></span>

- <span data-ttu-id="889d4-p121">**追加の Office 365 グループまたは Microsoft Teams サイトを保管担当者にマップするにはどうすればよいですか。Office 365 グループおよび Microsoft Teams には、非 wi-fi ダイヤルを含めることができます。** Microsoft Teams は、Office 365 グループ上に構築されています。そのため、電子情報開示ケースでそれらを保持することは非常によく似ています。Office 365 グループと Microsoft Teams を保持する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="889d4-p121">**How do I map an additional Office 365 Groups or Microsoft Teams site to a custodian? And what about placing a non-Custodial hold on Office 365 Groups and Microsoft Teams?** Microsoft Teams are built on Office 365 Groups. Therefore, placing them on hold in an eDiscovery case is very similar. Keep the following things in mind when placing Office 365 Groups and Microsoft Teams on hold.</span></span>
  - <span data-ttu-id="889d4-197">Office 365 グループおよび Microsoft Teams にあるコンテンツを保持するには、グループまたはチームに関連付けられているメールボックスと SharePoint サイトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="889d4-197">To place content located in Office 365 Groups and Microsoft Teams on hold, you have to specify the mailbox and SharePoint site that associated with a group or team.</span></span>
  
  - <span data-ttu-id="889d4-p122">Office 365 グループまたは Microsoft teams のプロパティを表示するには、Exchange Online で**set-unifiedgroup**コマンドレットを実行します。これは、Office 365 グループまたは Microsoft チームに関連付けられているサイトの URL を取得するための適切な方法です。たとえば、次のコマンドを実行すると、シニアリーダーシップチームという名前の Office 365 グループに対して選択されたプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="889d4-p122">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for an Office 365 Group or Microsoft Team. This is a good way to get the URL for the site that's associated with an Office 365 Group or a Microsoft Team. For example, the following command displays selected properties for an Office 365 Group named Senior Leadership Team:</span></span>


    ```
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > <span data-ttu-id="889d4-201">set-unifiedgroup コマンドレットを実行するには、Exchange Online で表示専用受信者の役割が割り当てられているか、または表示専用の受信者の役割が割り当てられている役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="889d4-201">To run the Get-UnifiedGroup cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span>

 - <span data-ttu-id="889d4-p123">ユーザーのメールボックスを検索すると、そのユーザーがメンバーになっているすべての Office 365 グループまたは Microsoft チームは検索されません。同様に、Office 365 グループまたは Microsoft teams ホールドを配置すると、グループメールボックスとグループサイトのみが保持されます。グループメンバーのメールボックスと OneDrive for business サイトは、保管担当者として明示的に追加したり、データソースを保持したりしない限り、保留リストには置かれません。そのため、特定の保管担当者に対して Office 365 グループまたは Microsoft teams を保持する必要がある場合は、グループメールボックスを保管担当者にマッピングすることを検討してください (「Advanced eDiscovery (プレビュー) での保管担当者の管理」を参照してください)。Office 365 グループまたは Microsoft teams が1つの保管担当者に属さない場合は、そのソースを非 custodial ホールドに追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="889d4-p123">When a user's mailbox is searched, any Office 365 Group or Microsoft Team that the user is a member of won't be searched. Similarly, when you place an Office 365 Group or Microsoft Team hold, only the group mailbox and group site are placed on hold; the mailboxes and OneDrive for Business sites of group members aren't placed on hold unless you explicitly add them as custodians or place their data sources hold. Therefore, if you the need to place an Office 365 Group or Microsoft Team on hold for a specific custodian, consider mapping the group site and group mailbox to the custodian (See Managing Custodians in Advanced eDiscovery (Preview)). If the Office 365 Group or Microsoft Team is not attributable to a single custodian, consider adding the source to a non-custodial hold.</span></span> 
 
 - <span data-ttu-id="889d4-p124">office 365 グループまたは Microsoft チームのメンバーの一覧を取得するには、office 365 管理センターの [ホーム > グループ] ページでプロパティを表示します。または、Exchange Online PowerShell で次のコマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="889d4-p124">To get a list of the members of a Office 365 Group or Microsoft Team, you can view the properties on the Home > Groups page in the Office 365 admin center. Alternatively, you can run the following command in Exchange Online PowerShell:</span></span>

   ``` 
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > <span data-ttu-id="889d4-208">**UnifiedGroupLinks**コマンドレットを実行するには、Exchange Online で表示専用受信者の役割が割り当てられているか、または表示専用の受信者の役割が割り当てられている役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="889d4-208">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span>

- <span data-ttu-id="889d4-p125">Microsoft Teams チャネルの一部であるチャネル会話は、チームに関連付けられているメールボックスに格納されます。同様に、チームメンバーがチャネルで共有するファイルは、チームの SharePoint サイトに格納されます。そのため、チャネル内の会話やファイルを保持するには、Microsoft teams メールボックスと SharePoint サイトを保留にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="889d4-p125">Channel conversations that are part of a Microsoft Teams channel are stored in the mailbox that's associated with the Team. Similarly, files that team members share in a channel are stored on the team's SharePoint site. Therefore, you have to place the Microsoft Team mailbox and SharePoint site on hold to retain conversations and files in a channel.</span></span>
  
- <span data-ttu-id="889d4-p126">または、Microsoft Teams のチャットリストに含まれる会話が、チャットに参加しているユーザーのメールボックスに保存されます。 ユーザーがチャット会話で共有しているファイルは、そのファイルを共有しているユーザーの OneDrive for business サイトに保存されます。そのため、会話やファイルをチャットリストに保持するには、個々のユーザーメールボックスと OneDrive for business サイトを保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="889d4-p126">Alternatively, conversations that are part of the Chat list in Microsoft Teams are stored in the mailbox of the user's who participate in the chat.  Files that a user shares in Chat conversations are stored in the OneDrive for Business site of the user who shares the file. Therefore, you have to place the individual user mailboxes and OneDrive for Business sites on hold to retain conversations and files in the Chat list.</span></span> 
  
- <span data-ttu-id="889d4-p127">Microsoft のすべてのチームまたはチームのチャネルには、メモを取り、共同作業のための Wiki が含まれています。Wiki コンテンツは、.mht 形式のファイルに自動的に保存されます。このファイルは、チームの SharePoint サイト上の Teams Wiki データドキュメントライブラリに格納されます。チームの SharePoint サイトを保持することによって、Wiki のコンテンツを保留にすることができます。</span><span class="sxs-lookup"><span data-stu-id="889d4-p127">Every Microsoft Team or team channel contains a Wiki for note-taking and collaboration. The Wiki content is automatically saved to a file with a .mht format. This file is stored in the Teams Wiki Data document library on the team's SharePoint site. You can place the content in the Wiki on hold by placing the team's SharePoint site on hold.</span></span>

  > [!NOTE]
  > <span data-ttu-id="889d4-p128">Microsoft チームまたはチームチャネルの Wiki コンテンツを保持する機能 (チームの SharePoint サイトを保持する場合) は、2017年6月22日にリリースされました。チームサイトが保留中の場合、Wiki コンテンツはその日付以降に保持されます。ただし、チームサイトが保留中で、2017年6月22日より前に wiki コンテンツが削除された場合、wiki コンテンツは保持されませんでした。</span><span class="sxs-lookup"><span data-stu-id="889d4-p128">The capability to retain Wiki content for a Microsoft Team or team channel (when you place the team's SharePoint site on hold) was released on June 22, 2017. If a team site is on hold, the Wiki content will be retained starting on that date. However, if a team site is on hold and the Wiki content was deleted before June 22, 2017, the Wiki content was not retained.</span></span>
