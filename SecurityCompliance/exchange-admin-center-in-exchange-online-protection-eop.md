---
title: 'オンライン保護を Exchange で Exchange 管理センター '
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
description: Exchange 管理センター (EAC) は、Microsoft Exchange Online Protection (EOP) 向けの Web ベース管理コンソールです。
ms.openlocfilehash: 99640e561b41e47a74e7c22f0bbdcacd0dd80bd7
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026314"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="397ae-103">オンライン保護を Exchange で Exchange 管理センター</span><span class="sxs-lookup"><span data-stu-id="397ae-103">Exchange admin center in Exchange Online Protection</span></span> 

<span data-ttu-id="397ae-104">Exchange 管理センター (EAC) は、Microsoft Exchange Online Protection (EOP) 向けの Web ベース管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="397ae-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span> 
  
<span data-ttu-id="397ae-p101">このトピックの Exchange 2013 バージョンについては、「[Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="397ae-p101">Looking for the Exchange 2013 version of this topic? See [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).</span></span>
  
<span data-ttu-id="397ae-p102">このトピックの Exchange Online バージョンについては、「[Exchange admin center in Exchange Online](http://technet.microsoft.com/library/ace44f6b-4084-4f9c-89b3-e0317962472b.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="397ae-p102">Looking for the Exchange Online version of this topic? See [Exchange admin center in Exchange Online](http://technet.microsoft.com/library/ace44f6b-4084-4f9c-89b3-e0317962472b.aspx).</span></span>
  
## <a name="accessing-the-eac"></a><span data-ttu-id="397ae-109">EACへのアクセスについて</span><span class="sxs-lookup"><span data-stu-id="397ae-109">Accessing the EAC</span></span>

<span data-ttu-id="397ae-p103">ほとんどの場合、EOP ユーザーは Office 365 管理センターを通じて EAC にアクセスします。EOP へのリンクは、 **[自分]** タイルの横にある **[管理]** タイルのドロップ ダウン メニューから選択できます。 **[管理]** タイルをクリックし、ドロップ ダウン メニューから **[Exchange Online Protection]** を選択すると、EAC にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="397ae-p103">In most cases, EOP customers will access the EAC through the Office 365 admin center. You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile. Click the **Admin** tile and select **Exchange Online Protection** from the drop down menu to be taken to the EAC.</span></span> 
  
<span data-ttu-id="397ae-p104">EAC のサインイン ページを次の URL から直接アクセスすることもできます: https://admin.protection.outlook.com/ecp/\<companydomain\>。たとえば、 https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com。ユーザーの資格情報を指定した後は、するは、EAC に直接取得されます。</span><span class="sxs-lookup"><span data-stu-id="397ae-p104">You can also access the EAC sign in page directly via the following URL: https://admin.protection.outlook.com/ecp/\<companydomain\>. For example, https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com. After specifying your user credentials you will be taken directly into the EAC.</span></span>
  
## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="397ae-116">EAC で共通のユーザー インターフェイス要素</span><span class="sxs-lookup"><span data-stu-id="397ae-116">Common user interface elements in the EAC</span></span>
<span data-ttu-id="397ae-117"><a name="BKMK_CommonUserInterfaceElements"> </a></span><span class="sxs-lookup"><span data-stu-id="397ae-117"></span></span>

<span data-ttu-id="397ae-118">ここでは、EAC のユーザー インターフェイス要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="397ae-118">This section describes the user interface elements that are found in the EAC.</span></span>
  
![EOP AdminCenter](media/EOP-AdminCenter.png)
  
### <a name="feature-pane"></a><span data-ttu-id="397ae-120">機能ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="397ae-120">Feature Pane</span></span>

<span data-ttu-id="397ae-p105">EAC で実行する多くのタスクで、これがナビゲーションの第 1 階層になります。[機能] ウィンドウは、機能領域ごとに整理されています。</span><span class="sxs-lookup"><span data-stu-id="397ae-p105">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>
  
1. <span data-ttu-id="397ae-123">**受信者** 社内ユーザーおよび社外の連絡先を確認します。</span><span class="sxs-lookup"><span data-stu-id="397ae-123">**Recipients** This is where you'll view internal users and external contacts.</span></span> 
    
2. <span data-ttu-id="397ae-124">**アクセス許可** 管理者の役割を管理します。</span><span class="sxs-lookup"><span data-stu-id="397ae-124">**Permissions** This where you'll manage administrator roles.</span></span> 
    
3. <span data-ttu-id="397ae-125">**コンプライアンス マネジメント** 監査ログや、管理者役割グループ レポートなどの各種レポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="397ae-125">**Compliance Management** This is where you'll find audit logs and reports, such as the administrator role group report.</span></span> 
    
4. <span data-ttu-id="397ae-126">**保護** 組織のマルウェア対策保護やスパム対策保護、および検疫のメッセージを管理します。</span><span class="sxs-lookup"><span data-stu-id="397ae-126">**Protection** This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span> 
    
5. <span data-ttu-id="397ae-127">**メール フロー** ルール、承認済みドメイン、コネクタ、およびメッセージ トレースの実行方法を管理します。</span><span class="sxs-lookup"><span data-stu-id="397ae-127">**Mail Flow** This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span> 
    
### <a name="tabs"></a><span data-ttu-id="397ae-128">タブ</span><span class="sxs-lookup"><span data-stu-id="397ae-128">Tabs</span></span>

<span data-ttu-id="397ae-p106">タブは、ナビゲーションの第 2 階層になります。各機能領域にはさまざまなタブがあり、それぞれのタブは各機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="397ae-p106">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>
  
### <a name="toolbar"></a><span data-ttu-id="397ae-131">ツールバー</span><span class="sxs-lookup"><span data-stu-id="397ae-131">Toolbar</span></span>

<span data-ttu-id="397ae-p107">ほとんどのタブは、クリックするとツールバーが表示されます。ツールバーには、特定のアクションを実行する複数のアイコンがあります。次の表は、各アイコンとそのアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="397ae-p107">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>
  
|<span data-ttu-id="397ae-135">**アイコン**</span><span class="sxs-lookup"><span data-stu-id="397ae-135">**Icon**</span></span>|<span data-ttu-id="397ae-136">**名前**</span><span class="sxs-lookup"><span data-stu-id="397ae-136">**Name**</span></span>|<span data-ttu-id="397ae-137">**Action**</span><span class="sxs-lookup"><span data-stu-id="397ae-137">**Action**</span></span>|
|:-----|:-----|:-----|
|![[追加] アイコン](media/ITPro-EAC-AddIcon.png)           <br/> |<span data-ttu-id="397ae-139">追加、新規</span><span class="sxs-lookup"><span data-stu-id="397ae-139">Add, New</span></span>  <br/> |<span data-ttu-id="397ae-p108">このアイコンを使用して、新しいオブジェクトを作成します。これらの一部のアイコンには下方向キーが関連付けられており、これをクリックして、作成可能な追加のオブジェクトを表示できます。</span><span class="sxs-lookup"><span data-stu-id="397ae-p108">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>  <br/> |
|![編集アイコン](media/ITPro-EAC-EditIcon.png)           <br/> |<span data-ttu-id="397ae-143">編集</span><span class="sxs-lookup"><span data-stu-id="397ae-143">Edit</span></span>  <br/> |<span data-ttu-id="397ae-144">このアイコンを使用してオブジェクトを編集します。</span><span class="sxs-lookup"><span data-stu-id="397ae-144">Use this icon to edit an object.</span></span>  <br/> |
|![[削除] アイコン](media/ITPro-EAC-DeleteIcon.png)           <br/> |<span data-ttu-id="397ae-146">削除</span><span class="sxs-lookup"><span data-stu-id="397ae-146">Delete</span></span>  <br/> |<span data-ttu-id="397ae-p109">このアイコンを使用してオブジェクトを削除します。一部の削除アイコンには下方向キーがあり、これをクリックして追加オプションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="397ae-p109">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>  <br/> |
|![[検索] アイコン](media/ITPro-EAC-.png)           <br/> |<span data-ttu-id="397ae-150">検索</span><span class="sxs-lookup"><span data-stu-id="397ae-150">Search</span></span>  <br/> |<span data-ttu-id="397ae-151">このアイコンを使用して、検索するオブジェクトの検索文字列を入力できる検索ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="397ae-151">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>  <br/> |
|![[最新の情報に更新] アイコン](media/ITPro-EAC-RefreshIcon.png)           <br/> |<span data-ttu-id="397ae-153">最新の情報に更新</span><span class="sxs-lookup"><span data-stu-id="397ae-153">Refresh</span></span>  <br/> |<span data-ttu-id="397ae-154">このアイコンを使用してリスト ビューを更新します。</span><span class="sxs-lookup"><span data-stu-id="397ae-154">Use this icon to refresh the list view.</span></span>  <br/> |
|![[その他のオプション] アイコン](media/ITPro-EAC-MoreOptionsIcon.png)           <br/> |<span data-ttu-id="397ae-156">その他のオプション</span><span class="sxs-lookup"><span data-stu-id="397ae-156">More options</span></span>  <br/> |<span data-ttu-id="397ae-p110">このアイコンを使用して、そのタブのオブジェクトに対して実行できる他のアクションを表示します。たとえば、 **受信者 \> ユーザー**のアイコンをクリックすると、 **詳細検索**のオプションが表示されます。  </span><span class="sxs-lookup"><span data-stu-id="397ae-p110">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.  </span></span><br/> |
|![上矢印アイコン](media/ITPro-EAC-UpArrowIcon.png)![下矢印アイコン](media/ITPro-EAC-DownArrowIcon.png)           <br/> |<span data-ttu-id="397ae-161">上方向キーと下方向キー</span><span class="sxs-lookup"><span data-stu-id="397ae-161">Up arrow and down arrow</span></span>  <br/> |<span data-ttu-id="397ae-162">これらのアイコンを使用して、オブジェクトの優先度を上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="397ae-162">Use these icons to move an object's priority up or down.</span></span>  <br/> |
|![[削除] アイコン](media/ITPro-EAC-RemoveIcon.png)           <br/> |<span data-ttu-id="397ae-164">削除</span><span class="sxs-lookup"><span data-stu-id="397ae-164">Remove</span></span>  <br/> |<span data-ttu-id="397ae-165">このアイコンを使用して、一覧からオブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="397ae-165">Use this icon to remove objects from a list.</span></span>  <br/> |
   
### <a name="list-view"></a><span data-ttu-id="397ae-166">リスト ビュー</span><span class="sxs-lookup"><span data-stu-id="397ae-166">List View</span></span>

<span data-ttu-id="397ae-p111">タブを選択すると、通常、リスト ビューが表示されます。EAC リスト ビューの表示可能限度は、ほぼ 10,000 オブジェクトです。さらに、ページングが含まれているため、結果をページングできます。</span><span class="sxs-lookup"><span data-stu-id="397ae-p111">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>
  
### <a name="details-pane"></a><span data-ttu-id="397ae-170">詳細ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="397ae-170">Details Pane</span></span>

<span data-ttu-id="397ae-p112">リスト ビューからオブジェクトを選択すると、そのオブジェクトに関する情報が詳細ウィンドウに表示されます。場合によっては、[詳細] ウィンドウに管理タスクが含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="397ae-p112">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>
  
### <a name="me-tile-and-help"></a><span data-ttu-id="397ae-173">[自分] タイルとヘルプ</span><span class="sxs-lookup"><span data-stu-id="397ae-173">Me tile and Help</span></span>

<span data-ttu-id="397ae-p113">**[自分]** タイルでは、EAC からのサインアウトおよび他のユーザーとしてサインインが行えます。 **[ヘルプ]**![ヘルプ アイコン](media/ITPro-EAC-HelpIcon.png) ドロップ ダウン メニューから次のアクションを行えます。</span><span class="sxs-lookup"><span data-stu-id="397ae-p113">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](media/ITPro-EAC-HelpIcon.png) drop-down menu, you can perform the following actions:</span></span> 
  
1. <span data-ttu-id="397ae-176">**ヘルプ**![ヘルプ アイコン](media/ITPro-EAC-HelpIcon.png) をクリックして、オンライン ヘルプ コンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="397ae-176">**Help** Click ![Help Icon](media/ITPro-EAC-HelpIcon.png) to view the online help content.</span></span> 
    
2. <span data-ttu-id="397ae-p114">**ヘルプ バブルを無効にする** ヘルプ バブルは、オブジェクトを作成または編集する際に、フィールドのコンテキスト ヘルプを表示します。ヘルプ バブルをオフにしたり、無効になっている場合はオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="397ae-p114">**Disable Help bubble** The Help bubble displays contextual help for fields when you create or edit an object. You can turn off the Help bubble or turn it on if it has been disabled.</span></span> 
    
3. <span data-ttu-id="397ae-179">**著作権** このリンクをクリックして、Exchange Online Protection に関する著作権の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="397ae-179">**Copyright** Click this link to read the copyright notice for Exchange Online Protection.</span></span> 
    
4. <span data-ttu-id="397ae-180">**プライバシー** ここをクリックして、Exchange Online Protection に関するプライバシー ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="397ae-180">**Privacy** Click to read the privacy policy for Exchange Online Protection.</span></span> 
    
## <a name="supported-browsers"></a><span data-ttu-id="397ae-181">サポートされているブラウザー</span><span class="sxs-lookup"><span data-stu-id="397ae-181">Supported Browsers</span></span>
<span data-ttu-id="397ae-182"><a name="BKMK_SupportedBrowsers"> </a></span><span class="sxs-lookup"><span data-stu-id="397ae-182"></span></span>

<span data-ttu-id="397ae-p115">EAC を最大限に活用できるように、常に最新のブラウザー、Office クライアント、アプリを使用することをお勧めします。また、ソフトウェア更新プログラムも、利用可能になり次第インストールすることをお勧めします。サービスでサポートされるブラウザー要件とシステム要件の詳細については、「[Office 365 のシステム要件](https://go.microsoft.com/fwlink/p/?LinkID=402699)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="397ae-p115">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps. We also recommend that you install software updates when they become available. For more information about the supported browsers and system requirements for the service, see [Office 365 System Requirements](https://go.microsoft.com/fwlink/p/?LinkID=402699).</span></span> 
  
## <a name="supported-languages-in-eop"></a><span data-ttu-id="397ae-186">EOP でサポートされている言語</span><span class="sxs-lookup"><span data-stu-id="397ae-186">Supported languages in EOP</span></span>
<span data-ttu-id="397ae-187"><a name="BKMK_SupportedLanguages"> </a></span><span class="sxs-lookup"><span data-stu-id="397ae-187"></span></span>

<span data-ttu-id="397ae-188">Exchange Online Protection でサポートされ、利用可能な言語は、以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="397ae-188">The following languages are supported and available for Exchange Online Protection.</span></span>
  
- <span data-ttu-id="397ae-189">アムハラ語</span><span class="sxs-lookup"><span data-stu-id="397ae-189">Amharic</span></span>
    
- <span data-ttu-id="397ae-190">アラビア語</span><span class="sxs-lookup"><span data-stu-id="397ae-190">Arabic</span></span>
    
- <span data-ttu-id="397ae-191">バスク語 (バスク)</span><span class="sxs-lookup"><span data-stu-id="397ae-191">Basque (Basque)</span></span>
    
- <span data-ttu-id="397ae-192">バングラ語 (インド)</span><span class="sxs-lookup"><span data-stu-id="397ae-192">Bengali (India)</span></span>
    
- <span data-ttu-id="397ae-193">ブルガリア語</span><span class="sxs-lookup"><span data-stu-id="397ae-193">Bulgarian</span></span>
    
- <span data-ttu-id="397ae-194">カタルニア語</span><span class="sxs-lookup"><span data-stu-id="397ae-194">Catalan</span></span>
    
- <span data-ttu-id="397ae-195">簡体字中国語</span><span class="sxs-lookup"><span data-stu-id="397ae-195">Chinese (Simplified)</span></span>
    
- <span data-ttu-id="397ae-196">繁体字中国語</span><span class="sxs-lookup"><span data-stu-id="397ae-196">Chinese (Traditional)</span></span>
    
- <span data-ttu-id="397ae-197">クロアチア語</span><span class="sxs-lookup"><span data-stu-id="397ae-197">Croatian</span></span>
    
- <span data-ttu-id="397ae-198">チェコ語</span><span class="sxs-lookup"><span data-stu-id="397ae-198">Czech</span></span>
    
- <span data-ttu-id="397ae-199">デンマーク語</span><span class="sxs-lookup"><span data-stu-id="397ae-199">Danish</span></span>
    
- <span data-ttu-id="397ae-200">オランダ語</span><span class="sxs-lookup"><span data-stu-id="397ae-200">Dutch</span></span>
    
- <span data-ttu-id="397ae-201">オランダ語</span><span class="sxs-lookup"><span data-stu-id="397ae-201">Dutch</span></span>
    
- <span data-ttu-id="397ae-202">英語</span><span class="sxs-lookup"><span data-stu-id="397ae-202">English</span></span>
    
- <span data-ttu-id="397ae-203">エストニア語</span><span class="sxs-lookup"><span data-stu-id="397ae-203">Estonian</span></span>
    
- <span data-ttu-id="397ae-204">フィリピン語 (フィリピン)</span><span class="sxs-lookup"><span data-stu-id="397ae-204">Filipino (Philippines)</span></span>
    
- <span data-ttu-id="397ae-205">フィンランド語</span><span class="sxs-lookup"><span data-stu-id="397ae-205">Finnish</span></span>
    
- <span data-ttu-id="397ae-206">フランス語</span><span class="sxs-lookup"><span data-stu-id="397ae-206">French</span></span>
    
- <span data-ttu-id="397ae-207">ガリシア語</span><span class="sxs-lookup"><span data-stu-id="397ae-207">Galician</span></span>
    
- <span data-ttu-id="397ae-208">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="397ae-208">German</span></span>
    
- <span data-ttu-id="397ae-209">ギリシャ語</span><span class="sxs-lookup"><span data-stu-id="397ae-209">Greek</span></span>
    
- <span data-ttu-id="397ae-210">グジャラート語</span><span class="sxs-lookup"><span data-stu-id="397ae-210">Gujarati</span></span>
    
- <span data-ttu-id="397ae-211">ヘブライ語</span><span class="sxs-lookup"><span data-stu-id="397ae-211">Hebrew</span></span>
    
- <span data-ttu-id="397ae-212">ヒンディー語</span><span class="sxs-lookup"><span data-stu-id="397ae-212">Hindi</span></span>
    
- <span data-ttu-id="397ae-213">ハンガリー語</span><span class="sxs-lookup"><span data-stu-id="397ae-213">Hungarian</span></span>
    
- <span data-ttu-id="397ae-214">アイスランド語</span><span class="sxs-lookup"><span data-stu-id="397ae-214">Icelandic</span></span>
    
- <span data-ttu-id="397ae-215">インドネシア語</span><span class="sxs-lookup"><span data-stu-id="397ae-215">Indonesian</span></span>
    
- <span data-ttu-id="397ae-216">イタリア語</span><span class="sxs-lookup"><span data-stu-id="397ae-216">Italian</span></span>
    
- <span data-ttu-id="397ae-217">日本語</span><span class="sxs-lookup"><span data-stu-id="397ae-217">Japanese</span></span>
    
- <span data-ttu-id="397ae-218">カンナダ語</span><span class="sxs-lookup"><span data-stu-id="397ae-218">Kannada</span></span>
    
- <span data-ttu-id="397ae-219">カザフ語</span><span class="sxs-lookup"><span data-stu-id="397ae-219">Kazakh</span></span>
    
- <span data-ttu-id="397ae-220">スワヒリ語</span><span class="sxs-lookup"><span data-stu-id="397ae-220">Kiswahili</span></span>
    
- <span data-ttu-id="397ae-221">韓国語</span><span class="sxs-lookup"><span data-stu-id="397ae-221">Korean</span></span>
    
- <span data-ttu-id="397ae-222">ラトビア語</span><span class="sxs-lookup"><span data-stu-id="397ae-222">Latvian</span></span>
    
- <span data-ttu-id="397ae-223">リトアニア語</span><span class="sxs-lookup"><span data-stu-id="397ae-223">Lithuanian</span></span>
    
- <span data-ttu-id="397ae-224">マレー語 (ブルネイ・ダルサラーム国)</span><span class="sxs-lookup"><span data-stu-id="397ae-224">Malay (Brunei Darussalam)</span></span>
    
- <span data-ttu-id="397ae-225">マレー語 (マレーシア)</span><span class="sxs-lookup"><span data-stu-id="397ae-225">Malay (Malaysia)</span></span>
    
- <span data-ttu-id="397ae-226">マラヤーラム語</span><span class="sxs-lookup"><span data-stu-id="397ae-226">Malayalam</span></span>
    
- <span data-ttu-id="397ae-227">マラーティー語</span><span class="sxs-lookup"><span data-stu-id="397ae-227">Marathi</span></span>
    
- <span data-ttu-id="397ae-228">ノルウェー語 (ブークモール)</span><span class="sxs-lookup"><span data-stu-id="397ae-228">Norwegian (Bokmål)</span></span>
    
- <span data-ttu-id="397ae-229">ノルウェー語 (ニーノシュク)</span><span class="sxs-lookup"><span data-stu-id="397ae-229">Norwegian (Nynorsk)</span></span>
    
- <span data-ttu-id="397ae-230">オリヤー語</span><span class="sxs-lookup"><span data-stu-id="397ae-230">Oriya</span></span>
    
- <span data-ttu-id="397ae-231">ペルシャ語</span><span class="sxs-lookup"><span data-stu-id="397ae-231">Persian</span></span>
    
- <span data-ttu-id="397ae-232">ポーランド語</span><span class="sxs-lookup"><span data-stu-id="397ae-232">Polish</span></span>
    
- <span data-ttu-id="397ae-233">ポルトガル語 (ブラジル)</span><span class="sxs-lookup"><span data-stu-id="397ae-233">Portuguese (Brazil)</span></span>
    
- <span data-ttu-id="397ae-234">ポルトガル語 (ポルトガル)</span><span class="sxs-lookup"><span data-stu-id="397ae-234">Portuguese (Portugal)</span></span>
    
- <span data-ttu-id="397ae-235">ルーマニア語</span><span class="sxs-lookup"><span data-stu-id="397ae-235">Romanian</span></span>
    
- <span data-ttu-id="397ae-236">ロシア語</span><span class="sxs-lookup"><span data-stu-id="397ae-236">Russian</span></span>
    
- <span data-ttu-id="397ae-237">セルビア語 (キリル、セルビア)</span><span class="sxs-lookup"><span data-stu-id="397ae-237">Serbian (Cyrillic, Serbia)</span></span>
    
- <span data-ttu-id="397ae-238">セルビア語 (ラテン)</span><span class="sxs-lookup"><span data-stu-id="397ae-238">Serbian (Latin)</span></span>
    
- <span data-ttu-id="397ae-239">スロバキア語</span><span class="sxs-lookup"><span data-stu-id="397ae-239">Slovak</span></span>
    
- <span data-ttu-id="397ae-240">スロベニア語</span><span class="sxs-lookup"><span data-stu-id="397ae-240">Slovenian</span></span>
    
- <span data-ttu-id="397ae-241">スペイン語</span><span class="sxs-lookup"><span data-stu-id="397ae-241">Spanish</span></span>
    
- <span data-ttu-id="397ae-242">スウェーデン語</span><span class="sxs-lookup"><span data-stu-id="397ae-242">Swedish</span></span>
    
- <span data-ttu-id="397ae-243">タミール語</span><span class="sxs-lookup"><span data-stu-id="397ae-243">Tamil</span></span>
    
- <span data-ttu-id="397ae-244">テルグ語</span><span class="sxs-lookup"><span data-stu-id="397ae-244">Telugu</span></span>
    
- <span data-ttu-id="397ae-245">タイ語</span><span class="sxs-lookup"><span data-stu-id="397ae-245">Thai</span></span>
    
- <span data-ttu-id="397ae-246">トルコ語</span><span class="sxs-lookup"><span data-stu-id="397ae-246">Turkish</span></span>
    
- <span data-ttu-id="397ae-247">ウクライナ語</span><span class="sxs-lookup"><span data-stu-id="397ae-247">Ukrainian</span></span>
    
- <span data-ttu-id="397ae-248">ウルドゥ語</span><span class="sxs-lookup"><span data-stu-id="397ae-248">Urdu</span></span>
    
- <span data-ttu-id="397ae-249">ベトナム語</span><span class="sxs-lookup"><span data-stu-id="397ae-249">Vietnamese</span></span>
    
- <span data-ttu-id="397ae-250">ウェールズ語</span><span class="sxs-lookup"><span data-stu-id="397ae-250">Welsh</span></span>
    

