---
title: Office 365 でオンプレミスのユーザーのクラウドベースのメールボックスを検索する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/4/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: Exchange ハイブリッド展開のオンプレミスのユーザーについて、Microsoft Teams のチャットデータ (1xN チャット) を検索してエクスポートするには、Security & コンプライアンスセンターのコンテンツ検索ツールを使用します。
ms.openlocfilehash: eb53daa381b89d8ded4f2400ed7781e2306eb263
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158739"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a><span data-ttu-id="ad77e-103">Office 365 でオンプレミスのユーザーのクラウドベースのメールボックスを検索する</span><span class="sxs-lookup"><span data-stu-id="ad77e-103">Searching cloud-based mailboxes for on-premises users in Office 365</span></span>

<span data-ttu-id="ad77e-104">組織に Exchange ハイブリッド展開があり、Microsoft Teams が有効になっている場合、ユーザーはインスタントメッセージング用に Teams chat アプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-104">If your organization has an Exchange hybrid deployment and has enabled Microsoft Teams, users can use the Teams chat application for instant messaging.</span></span> <span data-ttu-id="ad77e-105">クラウドベースのユーザーの場合、Teams のチャットデータ (1xN チャットとも呼ばれます) は、プライマリクラウドベースのメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-105">For the cloud-based user, the Teams chat data (also called 1xN chats) is saved to their primary cloud-based mailbox.</span></span> <span data-ttu-id="ad77e-106">オンプレミスのユーザーがチームチャットアプリケーションを使用する場合、プライマリメールボックスはオンプレミスに配置されます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-106">When an on-premises user uses the Team chat application, their primary mailbox is located on-premises.</span></span> <span data-ttu-id="ad77e-107">この制限を回避するために、Microsoft は、オンプレミスのユーザーのために Teams のチャットデータを保存するために、クラウドベースのストレージ領域 (オンプレミスユーザー用のクラウドベースのメールボックスと呼ばれる) を作成する新機能をリリースしました。</span><span class="sxs-lookup"><span data-stu-id="ad77e-107">To get around this limitation, Microsoft has released a new feature where a cloud-based storage area (called a cloud-based mailbox for on-premises users) is created to store Teams chat data for on-premises users.</span></span> <span data-ttu-id="ad77e-108">これにより、Security & コンプライアンスセンターのコンテンツ検索ツールを使用して、オンプレミスのユーザーのために Teams のチャットデータを検索してエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-108">This lets you use the Content Search tool in the Security & Compliance Center to search and export Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="ad77e-109">以下に、クラウドベースのメールボックスをオンプレミスのユーザー用に設定および検索するための要件と制限事項を示します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-109">Here are the requirements and limitation for setting up and to set up and search cloud-based mailboxes for on-premises users:</span></span>
  
- <span data-ttu-id="ad77e-110">オンプレミスのディレクトリサービス (Active Directory など) のユーザーアカウントは、Office 365 のディレクトリサービスである Azure Active Directory と同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad77e-110">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Office 365.</span></span> <span data-ttu-id="ad77e-111">これは、メールユーザーアカウントが Office 365 で作成され、プライマリメールボックスが社内組織内にあるユーザーに関連付けられることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-111">This means that a mail user account is created in Office 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>
    
- <span data-ttu-id="ad77e-112">オンプレミスのユーザーのクラウドベースのメールボックスは、Teams のチャットデータのみを格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-112">The cloud-based mailbox for on-premises users is used only store Teams chat data.</span></span> <span data-ttu-id="ad77e-113">オンプレミスのユーザーは、クラウドベースのメールボックスにはサインインできません。また、何らかの方法でアクセスすることもできません。</span><span class="sxs-lookup"><span data-stu-id="ad77e-113">An on-premises user can't sign in to the cloud-based mailbox or access in any way.</span></span> <span data-ttu-id="ad77e-114">電子メールメッセージを送受信するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ad77e-114">It can't be used to send or receive email messages.</span></span> 
    
- <span data-ttu-id="ad77e-115">組織がオンプレミスユーザーのクラウドベースのメールボックスで Teams のチャットデータを検索できるようにするには、Microsoft サポートに要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad77e-115">You have to submit a request to Microsoft Support to enable your organization to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="ad77e-116">この記事の[この機能を有効にするには、「Microsoft サポートによる要求のファイリング」を](#filing-a-request-with-microsoft-support-to-enable-this-feature)参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad77e-116">See [Filing a request with Microsoft Support to enable this feature](#filing-a-request-with-microsoft-support-to-enable-this-feature) in this article.</span></span> 
    
 <span data-ttu-id="ad77e-117">**注:** Teams チャネルの会話は、チームに関連付けられたクラウドベースのメールボックスに常に格納されます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-117">**Note:** Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team.</span></span> <span data-ttu-id="ad77e-118">これは、コンテンツ検索を使用して、サポート要求をファイルしなくてもチャネル会話を検索できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-118">That means you can use Content Search to search channel conversations without have to file a support request.</span></span> <span data-ttu-id="ad77e-119">Teams チャネル会話の検索の詳細については、「 [Microsoft teams および Office 365 グループの検索](content-search.md#searching-microsoft-teams-and-office-365-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad77e-119">For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Office 365 Groups](content-search.md#searching-microsoft-teams-and-office-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="ad77e-120">メカニズム</span><span class="sxs-lookup"><span data-stu-id="ad77e-120">How it works</span></span>

<span data-ttu-id="ad77e-121">Microsoft Teams が有効なユーザーがオンプレミスのメールボックスを持ち、そのユーザーアカウントまたは id がクラウドに同期されている場合、Microsoft は、1xN Teams のチャットデータを格納するためのクラウドベースのメールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-121">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates a cloud-based mailbox to store 1xN Teams chat data.</span></span> <span data-ttu-id="ad77e-122">Teams のチャットデータは、クラウドベースのメールボックスに格納された後、検索用にインデックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-122">After the Teams chat data is stored in the cloud-based mailbox, it's indexed for search.</span></span> <span data-ttu-id="ad77e-123">これにより、コンテンツ検索 (および電子情報開示ケースに関連付けられた検索) を使用して、オンプレミスユーザーの Teams チャットデータの検索、プレビュー、エクスポートを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-123">This lets you Use Content Search (and searches associated with eDiscovery cases) to search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="ad77e-124">また、Security & コンプライアンスセンターの PowerShell で\*\* \*new-compliancesearch\*\*コマンドレットを使用して、オンプレミスユーザーの Teams チャットデータを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-124">You can also use **\*ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="ad77e-125">次の図は、オンプレミスユーザーの Teams チャットデータを検索、プレビュー、およびエクスポートできるようにするワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="ad77e-125">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![Microsoft Teams でのオンプレミスユーザー向けのクラウドベースのストレージ](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
<span data-ttu-id="ad77e-127">この新しい機能に加えて、コンテンツ検索を使用して、各 Microsoft Teams に関連付けられたクラウドベースの SharePoint サイトと Exchange メールボックス内の Teams コンテンツを検索、プレビュー、およびエクスポートすることもできます。また、Exchange Online メールボックスで、クラウドベースのユーザー。</span><span class="sxs-lookup"><span data-stu-id="ad77e-127">In addition to this new capability, you can still use Content Search to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a><span data-ttu-id="ad77e-128">この機能を有効にするために Microsoft サポートによる要求を提出する</span><span class="sxs-lookup"><span data-stu-id="ad77e-128">Filing a request with Microsoft Support to enable this feature</span></span>

<span data-ttu-id="ad77e-129">組織で、セキュリティ & コンプライアンスセンターのグラフィカルユーザーインターフェイスを使用して、社内ユーザーのクラウドベースのメールボックスで Teams のチャットデータを検索できるようにするには、Microsoft サポートを使用して要求をファイルにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad77e-129">You must file a request with Microsoft Support to enable your organization to use the graphical user interface in the Security & Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="ad77e-130">この機能は、Security & コンプライアンスセンターの PowerShell で利用できます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-130">Note that this feature is available in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="ad77e-131">PowerShell を使用してオンプレミスユーザーの Teams チャットデータを検索するために、サポート要求を送信する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ad77e-131">You don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="ad77e-132">Microsoft サポートに要求を送信するときに、次の情報を含めます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-132">Include the following information when you submit the request to Microsoft Support:</span></span>
  
- <span data-ttu-id="ad77e-133">Office 365 組織の既定のドメイン名。</span><span class="sxs-lookup"><span data-stu-id="ad77e-133">The default domain name of your Office 365 organization.</span></span>
    
- <span data-ttu-id="ad77e-134">Office 365 組織のテナント名とテナント ID。</span><span class="sxs-lookup"><span data-stu-id="ad77e-134">The tenant name and tenant ID of your Office 365 organization.</span></span> <span data-ttu-id="ad77e-135">これらは、Azure Active Directory ポータル ([**プロパティ**の**管理** \> ] の下) から見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-135">You can find these in the Azure Active Directory portal (under **Manage** \> **Properties**).</span></span> <span data-ttu-id="ad77e-136">「 [Office の Office 365 テナント ID を検索する](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad77e-136">See [Find your Office 365 tenant ID](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>
    
- <span data-ttu-id="ad77e-137">サポートリクエストの目的のタイトルまたは説明: 「オンプレミスユーザーのためにアプリケーションコンテンツ検索を有効にする」。</span><span class="sxs-lookup"><span data-stu-id="ad77e-137">The following title or description of the purpose of the support request: "Enable Application Content Search for On-premises Users".</span></span> <span data-ttu-id="ad77e-138">これは、要求を実装する Office 365 eDiscovery エンジニアリングチームに要求をルーティングするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-138">This will help route the request to the Office 365 eDiscovery engineering team who will implement the request.</span></span> 
    
<span data-ttu-id="ad77e-139">エンジニアリングの変更が行われた後、Microsoft サポートは展開の推定日付を送信します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-139">After the engineering change is made, Microsoft Support will send you an estimated deployment date.</span></span> <span data-ttu-id="ad77e-140">通常、サポート要求を送信した後、展開プロセスは2-3 週間かかることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ad77e-140">Note that the deployment process usually takes 2-3 weeks after you submit the support request.</span></span> 
  
### <a name="what-happens-after-this-feature-is-enabled"></a><span data-ttu-id="ad77e-141">この機能を有効にした後はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="ad77e-141">What happens after this feature is enabled?</span></span>

<span data-ttu-id="ad77e-142">この機能が Office 365 組織に展開されると、次の変更が、セキュリティ & コンプライアンスセンターの電子情報開示ケースに関連付けられたコンテンツ検索と検索で行われます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-142">After this feature is deployed in your Office 365 organization, the following changes are made in Content Search and in searches associated with an eDiscovery case in the Security & Compliance Center:</span></span>
  
- <span data-ttu-id="ad77e-143">**[オンプレミスユーザーの Office アプリコンテンツを追加**する] チェックボックスが [コンテンツ検索] の**場所**の下に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-143">The **Add Office app content for on-premises users** checkbox is added under the **Locations** in Content Search.</span></span> 
    
    ![コンテンツ検索 UI に「オンプレミスユーザーの Office アプリコンテンツを追加する」チェックボックスが追加されている](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- <span data-ttu-id="ad77e-145">オンプレミスのユーザーは、検索するユーザーメールボックスを選択するために使用するコンテンツの場所選択ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-145">On-premises users are displayed in the content locations picker that you use to select user mailboxes to search.</span></span> 
    

  
## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="ad77e-146">オンプレミスユーザーのクラウドベースのメールボックスで Teams のチャットコンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="ad77e-146">Searching for Teams chat content in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="ad77e-147">機能が有効になったら、Security & コンプライアンスセンターでコンテンツ検索を使用して、社内ユーザーのクラウドベースのメールボックスで Teams のチャットデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-147">After the feature has been enabled, you can use Content Search in the Security & Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> 
  
1. <span data-ttu-id="ad77e-148">セキュリティ & コンプライアンスセンターで、[**検索** \> **コンテンツ検索**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-148">In the Security & Compliance Center, go to **Search** \> **Content search**</span></span>
    
2. <span data-ttu-id="ad77e-149">[**検索**] ページで、 ![[追加](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) ] アイコン [**新しい検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad77e-149">On the **Search** page, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span>
    
    <span data-ttu-id="ad77e-150">前述のように、[**場所**] の下に、 **[オンプレミスユーザーの Office アプリコンテンツを追加**する] チェックボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-150">As previously explained, the **Add Office app content for on-premises users** checkbox is displayed under **Locations**.</span></span> <span data-ttu-id="ad77e-151">既定では選択されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ad77e-151">Note that it is selected by default.</span></span>
    
3. <span data-ttu-id="ad77e-152">キーワードクエリを作成し、必要に応じて検索クエリに条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-152">Create the keyword query and add conditions to the search query if necessary.</span></span> <span data-ttu-id="ad77e-153">チームのチャットデータのみを検索するには、[**キーワード**] ボックスに次のクエリを追加します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-153">To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span> 
    
    ```
    kind:im
    ``` 

4. <span data-ttu-id="ad77e-154">この時点で、[**場所**] の下にある次のオプションのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-154">At this point, you can choose one of the following options under **Locations**:</span></span>
    
    - <span data-ttu-id="ad77e-155">[**すべての場所**] 組織内のすべてのユーザーのメールボックスを検索するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-155">**All locations** - Select this option to search the mailboxes of all users in your organization.</span></span> <span data-ttu-id="ad77e-156">このチェックボックスをオンにすると、オンプレミスのユーザーのすべてのクラウドベースのメールボックスも検索されます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-156">When the checkbox is selected, all cloud-based mailboxes for on-premises users will also be searched.</span></span> 
    
    - <span data-ttu-id="ad77e-157">**特定の場所**-このオプションを選択し、[**変更** \> ] をクリックして、特定のメールボックスを検索するユーザー、グループ、またはチームを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-157">**Specific locations** - Select this option and then click **Modify** \> Choose user, groups, or teams to search specific mailboxes.</span></span> <span data-ttu-id="ad77e-158">前述したように、場所の選択ウィンドウを使用すると、オンプレミスのユーザーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-158">As previously explained, the locations picker will let you search for on-premises users.</span></span> 
    
5. <span data-ttu-id="ad77e-159">検索を保存して実行します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-159">Save and run the search.</span></span> <span data-ttu-id="ad77e-160">オンプレミスのユーザーのクラウドベースのメールボックスからの検索結果は、他の検索結果と同様にプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-160">Any search results from the cloud-based mailboxes for on-premises users can be previewed like any other search results.</span></span> <span data-ttu-id="ad77e-161">さらに、検索結果 (Teams のチャットデータを含む) を PST ファイルにエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-161">Additionally, you can you can export the search results (including any Teams chat data) to a PST file.</span></span> <span data-ttu-id="ad77e-162">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad77e-162">For more information, see:</span></span> 
    
    - [<span data-ttu-id="ad77e-163">新しい検索を作成する</span><span class="sxs-lookup"><span data-stu-id="ad77e-163">Create a new search</span></span>](content-search.md#create-a-new-search)
    
    - [<span data-ttu-id="ad77e-164">検索結果のプレビュー</span><span class="sxs-lookup"><span data-stu-id="ad77e-164">Preview search results</span></span>](content-search.md#preview-search-results)
    
    - [<span data-ttu-id="ad77e-165">コンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="ad77e-165">Export Content Search results</span></span>](export-search-results.md)
    
## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="ad77e-166">PowerShell を使用してオンプレミスユーザーのクラウドベースのメールボックスで Teams チャットデータを検索する</span><span class="sxs-lookup"><span data-stu-id="ad77e-166">Using PowerShell to search for Teams chat data in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="ad77e-167">セキュリティ & コンプライアンスセンターの PowerShell で**new-compliancesearch**および**new-compliancesearch**コマンドレットを使用して、オンプレミスのユーザーのクラウドベースのメールボックスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-167">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search the cloud-based mailbox for on-premises users.</span></span> <span data-ttu-id="ad77e-168">前述のように、PowerShell を使用してオンプレミスユーザーの Teams チャットデータを検索するためのサポート要求を送信する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ad77e-168">As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
1. <span data-ttu-id="ad77e-169">[Security _AMP_ コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-169">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="ad77e-170">次の PowerShell コマンドを実行して、新しいコンテンツを作成し、オンプレミスユーザーのクラウドベースのメールボックスを検索します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-170">Run the following PowerShell command to create a new content searches the cloud-based mailboxes of on-premises users.</span></span>
    
    ```
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```
   
    <span data-ttu-id="ad77e-171">*Includeuserappcontent*パラメーターは、 *exchangelocation*パラメーターで指定されたユーザーまたはユーザーのクラウドベースのメールボックスを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-171">The  *IncludeUserAppContent*  parameter is used to specify the cloud-based mailbox for the user or users who are specified by the  *ExchangeLocation*  parameter.</span></span> <span data-ttu-id="ad77e-172">*AllowNotFoundExchangeLocationsEnabled*では、クラウドベースのメールボックスがオンプレミスのユーザーに対して許可されています。</span><span class="sxs-lookup"><span data-stu-id="ad77e-172">The  *AllowNotFoundExchangeLocationsEnabled*  allows cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="ad77e-173">このパラメーターの`$true`値を使用する場合、検索では、メールボックスが実行される前に、存在しているかどうかの検証は試行されません。</span><span class="sxs-lookup"><span data-stu-id="ad77e-173">When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs.</span></span> <span data-ttu-id="ad77e-174">この種類のメールボックスは通常のメールボックスとして解決されないため、オンプレミスのユーザーのクラウドベースのメールボックスを検索するには、これが必要になります。</span><span class="sxs-lookup"><span data-stu-id="ad77e-174">This is required to search the cloud-based mailboxes for on-premises users because these types of mailboxes don't resolve as regular mailboxes.</span></span> 
    
    <span data-ttu-id="ad77e-175">次の例では、Contoso 組織のオンプレミスのユーザーである Sara Davis のクラウドベースのメールボックスに、キーワード "redstone" を含む Teams チャット (インスタントメッセージ) を検索します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-175">The following example searches for Teams chats (which are instant messages) that contain keyword "redstone" in the cloud-based mailbox of Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="ad77e-176">新しい検索を作成したら、 **new-compliancesearch**コマンドレットを使用して検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad77e-176">After you create a new search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span> 
  
<span data-ttu-id="ad77e-177">これらのコマンドレットの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad77e-177">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="ad77e-178">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="ad77e-178">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)
    
- [<span data-ttu-id="ad77e-179">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="ad77e-179">Set-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)
    
- [<span data-ttu-id="ad77e-180">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="ad77e-180">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)
    

## <a name="known-issues"></a><span data-ttu-id="ad77e-181">既知の問題</span><span class="sxs-lookup"><span data-stu-id="ad77e-181">Known issues</span></span>

- <span data-ttu-id="ad77e-182">現在、社内ユーザーのクラウドベースのメールボックスに対してのみ、コンテンツの検索、プレビュー、およびエクスポートを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-182">Currently, you can only search, preview, and export content in cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="ad77e-183">電子情報開示ケースに関連付けられている保留リストにクラウドベースのメールボックスを配置したり、Office 365 アイテム保持ポリシーに割り当てたりすることはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ad77e-183">Placing a cloud-based mailbox for an on-premises user on a hold associated with an eDiscovery case or assigning it to an Office 365 retention policy is not supported.</span></span> 
    
- <span data-ttu-id="ad77e-184">電子情報開示保持用のコンテンツの場所の選択は、オンプレミスのユーザーを表示し、それらを選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ad77e-184">The content location picker for eDiscovery holds displays on-premises users and will let you select them.</span></span> <span data-ttu-id="ad77e-185">ただし、以前に説明したように、保留はオンプレミスのユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="ad77e-185">However, as previously explained the hold will not be applied to the on-premises user.</span></span>
    
## <a name="frequently-asked-questions"></a><span data-ttu-id="ad77e-186">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="ad77e-186">Frequently asked questions</span></span>

 <span data-ttu-id="ad77e-187">**オンプレミスのユーザーのためのクラウドベースのメールボックスはどこにありますか?**</span><span class="sxs-lookup"><span data-stu-id="ad77e-187">**Where are cloud-based mailboxes for on-premises users located?**</span></span>
  
<span data-ttu-id="ad77e-188">クラウドベースのメールボックスが作成され、Office 365 組織と同じデータセンターに保存されます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-188">Cloud-based mailboxes are created and stored in the same datacenter as your Office 365 organization.</span></span> 
  
 <span data-ttu-id="ad77e-189">**サポートリクエストを提出する以外に、その他の要件があるかどうか。**</span><span class="sxs-lookup"><span data-stu-id="ad77e-189">**Are there any other requirements other than submitting a support request?**</span></span>
  
 <span data-ttu-id="ad77e-190">前述したように、オンプレミスのメールボックスを使用するユーザーの id は、Office 365 の社内ユーザーアカウントごとに、対応するメールユーザーアカウントが作成されるように、クラウドベースの組織に同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad77e-190">As previously explained, the identities of users with on-prem mailboxes must be synchronized to your cloud-based organization so that a corresponding mail user account is created for each on-premises user account in Office 365.</span></span> <span data-ttu-id="ad77e-191">また、組織には office 365 enterprise E1、E3、または E5 サブスクリプションなど365の office enterprise サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="ad77e-191">Additionally, your organization must have an Office 365 enterprise subscription, such as an Office 365 Enterprise E1, E3, or E5 subscription.</span></span> 
  
 <span data-ttu-id="ad77e-192">**ユーザーのオンプレミスのメールボックスがクラウドに移行された場合、Teams のチャットデータを失う危険性がありますか。**</span><span class="sxs-lookup"><span data-stu-id="ad77e-192">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="ad77e-193">いいえ。</span><span class="sxs-lookup"><span data-stu-id="ad77e-193">No.</span></span> <span data-ttu-id="ad77e-194">オンプレミスのユーザーのプライマリメールボックスをクラウドに移行すると、そのユーザーの Teams チャットデータが新しいクラウドベースのプライマリメールボックスに移行されます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-194">When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="ad77e-195">**社内ユーザーに電子情報開示の保持ポリシーまたは Office 365 のアイテム保持ポリシーを適用できますか。**</span><span class="sxs-lookup"><span data-stu-id="ad77e-195">**Can I apply an eDiscovery hold or Office 365 retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="ad77e-196">いいえ。</span><span class="sxs-lookup"><span data-stu-id="ad77e-196">No.</span></span>
  
 <span data-ttu-id="ad77e-197">**コンテンツ検索は、組織がこの機能を有効にする要求を送信した時間前に、オンプレミスのユーザーのために古い Teams のチャットを見つけることができますか?**</span><span class="sxs-lookup"><span data-stu-id="ad77e-197">**Can Content Search find older Teams chats for on-premises users before the time my organization submitted the request to enable this feature?**</span></span>
  
<span data-ttu-id="ad77e-198">Microsoft は、2018年1月31日に社内ユーザーの Teams チャットデータの保存を開始しました。</span><span class="sxs-lookup"><span data-stu-id="ad77e-198">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018.</span></span> <span data-ttu-id="ad77e-199">そのため、この日付以降に Active Directory と Azure Active Directory との間でオンプレミスの Teams ユーザーの id が同期されている場合、Teams のチャットデータはクラウドベースのメールボックスに保存され、コンテンツ検索を使用して検索可能になります。</span><span class="sxs-lookup"><span data-stu-id="ad77e-199">So, if the identity of an on-premises Teams user has been synched between Active Directory and Azure Active Directory since this date, then their Teams chat data will be stored in a cloud-based mailbox and will be searchable using Content Search.</span></span> <span data-ttu-id="ad77e-200">Microsoft は、社内ユーザーのクラウドベースのメールボックスで2018年1月31日より前の Teams のチャットデータを保存することにも取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-200">Microsoft is also working on storing Teams chat data from prior to January 31, 2018 in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="ad77e-201">詳細については、近日中にご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="ad77e-201">More information about this will be available soon.</span></span>
