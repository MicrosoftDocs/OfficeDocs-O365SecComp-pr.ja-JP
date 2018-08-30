---
title: オンプレミス ユーザーのクラウド ベースのメールボックスを Office 365 で検索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/4/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: コンテンツの検索ツールを使用して、Office 365 のセキュリティで&amp;コンプライアンス ・ センターを検索し、Exchange ハイブリッド展開で、オンプレミス ユーザーの (1xN のチャットと呼ばれる) MicrosoftTeams チャットのデータをエクスポートします。
ms.openlocfilehash: a504dfcf4c82bec036137b90312c01a0b2326ccc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531958"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a><span data-ttu-id="6a3d0-103">オンプレミス ユーザーのクラウド ベースのメールボックスを Office 365 で検索</span><span class="sxs-lookup"><span data-stu-id="6a3d0-103">Searching cloud-based mailboxes for on-premises users in Office 365</span></span>

<span data-ttu-id="6a3d0-p101">組織に Exchange ハイブリッド展開があり、マイクロソフトのチームが有効になった場合、ユーザーはインスタント メッセージングのチーム チャット アプリケーションを使用できます。クラウド ベースのユーザーの場合、その主なクラウド ベースのメールボックスに (1xN のチャットとも呼ばれます) チーム チャットのデータが保存されます。オンプレミスのユーザーは、チームのチャット アプリケーションを使用する場合、プライマリ メールボックスは、オンプレミスであります。この制限を回避するには、オンプレミス ユーザーのチーム チャットのデータを格納する (オンプレミス ユーザーのクラウド ベースのメールボックスと呼ばれます)、クラウド ・ ベースのストレージ領域が作成される新しい機能をリリースしました。これにより、Office 365 のセキュリティのコンテンツの検索ツールを使用する&amp;を検索し、エクスポートするコンプライアンス センター チームは、オンプレミス ユーザーのチャットのデータです。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p101">If your organization has an Exchange hybrid deployment and has enabled Microsoft Teams, users can use the Teams chat application for instant messaging. For the cloud-based user, the Teams chat data (also called 1xN chats) is saved to their primary cloud-based mailbox. When an on-premises user uses the Team chat application, their primary mailbox is located on-premises. To get around this limitation, Microsoft has released a new feature where a cloud-based storage area (called a cloud-based mailbox for on-premises users) is created to store Teams chat data for on-premises users. This lets you use the Content Search tool in the Office 365 Security &amp; Compliance Center to search and export Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="6a3d0-109">要件および制限を設定しを設定し、オンプレミス ユーザーのメールボックスをクラウド ベースの検索を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-109">Here are the requirements and limitation for setting up and to set up and search cloud-based mailboxes for on-premises users:</span></span>
  
- <span data-ttu-id="6a3d0-p102">設置などのディレクトリ サービス (Active Directory) のユーザー アカウントは、Azure Active Directory ディレクトリ サービスには、Office 365 と同期させる必要があります。これは、メール ・ ユーザー ・ アカウントが Office 365 が作成され、プライマリ メールボックスが設置型の組織であるユーザーに関連付けられたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p102">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Office 365. This means that a mail user account is created in Office 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>
    
- <span data-ttu-id="6a3d0-p103">オンプレミス ユーザーのクラウド ベースのメールボックスは、チーム チャットのデータを保管しますだけです。オンプレミスのユーザーは、クラウド ベースのメールボックスへのサインインまたは何らかの方法でアクセスできません。電子メール メッセージを送受信するには使用できません。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p103">The cloud-based mailbox for on-premises users is used only store Teams chat data. An on-premises user can't sign in to the cloud-based mailbox or access in any way. It can't be used to send or receive email messages.</span></span> 
    
- <span data-ttu-id="6a3d0-p104">オンプレミス ユーザーのクラウド ベースのメールボックス内のチームのチャットのデータを検索する組織を有効にするには、マイクロソフト サポートに要求を送信する必要があります。参照してください[セキュリティでは、この機能を有効にするには、マイクロソフトのサポートと要求を提出&amp;コンプライアンス センター](#filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center)この資料に記載されています。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p104">You have to submit a request to Microsoft Support to enable your organization to search for Teams chat data in the cloud-based mailboxes for on-premises users. See [Filing a request with Microsoft Support to enable this feature in the Security &amp; Compliance Center](#filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center) in this article.</span></span> 
    
 <span data-ttu-id="6a3d0-p105">**注:** チームのチャネルの会話は、常にチームに関連付けられているクラウド ベースのメールボックスに格納します。つまり、会話は、サポート リクエストを提出することがなくが検索チャンネルにコンテンツの検索を使用することができます。チャネルの会話のチームの検索の詳細については、[マイクロソフトのチームを検索し Office 365 のグループ](content-search.md#searching-microsoft-teams-and-office-365-groups)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p105">**Note:** Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team. That means you can use Content Search to search channel conversations without have to file a support request. For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Office 365 Groups](content-search.md#searching-microsoft-teams-and-office-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="6a3d0-120">しくみ</span><span class="sxs-lookup"><span data-stu-id="6a3d0-120">How it works</span></span>

<span data-ttu-id="6a3d0-p106">マイクロソフトのチームが有効なユーザーには、オンプレミスのメールボックスとユーザー アカウントと id がクラウドに同期されて、マイクロソフトは、1xN チーム チャット データを格納する、クラウド ベースのメールボックスを作成します。チーム チャットのデータは、クラウド ベースのメールボックスに格納されている後、は、検索用インデックスされます。これにより、コンテンツの検索を使用 (および電子的証拠開示のサポート案件に関連する検索) を検索するには、プレビュー、およびオンプレミス ユーザーのチーム チャットのデータをエクスポートします。使用することができます**\*ComplianceSearch**コマンドレットでは、Office 365 のセキュリティ&amp;コンプライアンス センター PowerShell チーム、オンプレミス ユーザーのチャットのデータを検索します。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p106">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates a cloud-based mailbox to store 1xN Teams chat data. After the Teams chat data is stored in the cloud-based mailbox, it's indexed for search. This lets you Use Content Search (and searches associated with eDiscovery cases) to search, preview, and export Teams chat data for on-premises users. You can also use **\*ComplianceSearch** cmdlets in the Office 365 Security &amp; Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="6a3d0-125">チームによる、オンプレミス ユーザーのデータのチャットのワークフローでは、検索、プレビュー、およびエクスポートに使用可能な次の図を示しています。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-125">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![マイクロソフトのチームで、オンプレミス ユーザーのクラウド ベースのストレージ](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
<span data-ttu-id="6a3d0-127">この新しい機能だけでなくことができますもを使用するコンテンツの検索検索、プレビュー、およびチームの各マイクロソフト チーム 1xN のチームとのオンラインの Exchange メールボックス内のチャットのデータに関連付けられた Exchange メールボックスとクラウド ベースの SharePoint サイトのコンテンツをエクスポートするにはクラウド ベースのユーザーです。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-127">In addition to this new capability, you can still use Content Search to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center"></a><span data-ttu-id="6a3d0-128">セキュリティでは、この機能を有効にするには、マイクロソフトのサポートと要求を提出&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="6a3d0-128">Filing a request with Microsoft Support to enable this feature in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="6a3d0-p107">セキュリティでは、グラフィカル ユーザー インターフェイスを使用する組織を有効にするには、マイクロソフトのサポートの要求を提出する必要があります&amp;コンプライアンス ・ センターでクラウド ベースのメールボックスをオンプレミス ユーザーのチームのチャットのデータを検索します。この機能は、Office 365 のセキュリティで使用できることに注意してください&amp;コンプライアンス センター PowerShell。PowerShell を使用して、オンプレミス ユーザーのチーム チャットのデータを検索するのには、サポート要求を送信する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p107">You must file a request with Microsoft Support to enable your organization to use the graphical user interface in the Security &amp; Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users. Note that this feature is available in Office 365 Security &amp; Compliance Center PowerShell. You don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="6a3d0-132">マイクロソフトのサポート要求を送信する場合については、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-132">Include the following information when you submit the request to Microsoft Support:</span></span>
  
- <span data-ttu-id="6a3d0-133">Office 365 組織の既定のドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-133">The default domain name of your Office 365 organization.</span></span>
    
- <span data-ttu-id="6a3d0-p108">テナントの名前と組織の Office 365 のテナント ID。Azure Active Directory のポータルでは、これらを見つけることができます (**管理**下にある\>**プロパティ**)。[Office 365 のテナント ID を検索する](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p108">The tenant name and tenant ID of your Office 365 organization. You can find these in the Azure Active Directory portal (under **Manage** \> **Properties**). See [Find your Office 365 tenant ID](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>
    
- <span data-ttu-id="6a3d0-p109">次のタイトルまたはサポート要求の目的の説明:"オンプレミス ユーザーのアプリケーション コンテンツの検索を有効にする]。要求を実装する Office 365 電子的証拠開示エンジニア リング チームに要求をルーティングするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p109">The following title or description of the purpose of the support request: "Enable Application Content Search for On-premises Users". This will help route the request to the Office 365 eDiscovery engineering team who will implement the request.</span></span> 
    
<span data-ttu-id="6a3d0-p110">エンジニア リングの変更が加えられると、Microsoft サポート送信すると、展開が予想される日付。展開プロセスは、サポート リクエストを送信した後、2 ~ 3 週間を通常は注意してください。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p110">After the engineering change is made, Microsoft Support will send you an estimated deployment date. Note that the deployment process usually takes 2-3 weeks after you submit the support request.</span></span> 
  
### <a name="what-happens-after-this-feature-is-enabled"></a><span data-ttu-id="6a3d0-141">この機能を有効にした後はどうなるか</span><span class="sxs-lookup"><span data-stu-id="6a3d0-141">What happens after this feature is enabled?</span></span>

<span data-ttu-id="6a3d0-142">次の変更がコンテンツの検索で行われ、セキュリティの場合は、電子的証拠開示に関連する検索で、Office 365 の組織でこの機能が配置されると、&amp;コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-142">After this feature is deployed in your Office 365 organization, the following changes are made in Content Search and in searches associated with an eDiscovery case in the Security &amp; Compliance Center:</span></span>
  
- <span data-ttu-id="6a3d0-143">**オンプレミス ユーザーの追加の Office アプリケーションのコンテンツ**のチェック ボックスをオンは、コンテンツの検索**場所**の下に追加されます。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-143">The **Add Office app content for on-premises users** checkbox is added under the **Locations** in Content Search.</span></span> 
    
    !["オンプレミス ユーザーの Office アプリケーションのコンテンツを追加する] チェック ボックスがコンテンツの検索 UI を追加します。](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- <span data-ttu-id="6a3d0-145">コンテンツの場所の選択を使用して検索するユーザーのメールボックスを選択するには、オンプレミス ユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-145">On-premises users are displayed in the content locations picker that you use to select user mailboxes to search.</span></span> 
    

  
## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="6a3d0-146">オンプレミス ユーザーのメールボックスをクラウド ベースのコンテンツ チーム チャットを検索します。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-146">Searching for Teams chat content in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="6a3d0-147">セキュリティ コンテンツの検索を使用するには、機能が有効にすると、 &amp; 、オンプレミス ユーザーのクラウド ベースのメールボックスでチームのチャットのデータを検索するコンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-147">After the feature has been enabled, you can use Content Search in the Security &amp; Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> 
  
1. <span data-ttu-id="6a3d0-148">セキュリティ&amp;コンプライアンス センター] に移動**検索&amp;調査** \> **コンテンツの検索**</span><span class="sxs-lookup"><span data-stu-id="6a3d0-148">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Content search**</span></span>
    
2. <span data-ttu-id="6a3d0-149">[**検索**] ページをクリックして![の追加アイコン](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新しい検索**します。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-149">On the **Search** page, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span>
    
    <span data-ttu-id="6a3d0-p111">説明したよう**場所**の下 **、オンプレミス ユーザーの追加の Office アプリケーションのコンテンツ**のチェック ボックスが表示されます。既定で選択されていることを注意してください。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p111">As previously explained, the **Add Office app content for on-premises users** checkbox is displayed under **Locations**. Note that it is selected by default.</span></span>
    
3. <span data-ttu-id="6a3d0-p112">キーワード クエリを作成し、必要な場合は、検索クエリに条件を追加します。チームの検索のみにチャットのデータは、**キーワード**ボックスに次のクエリを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p112">Create the keyword query and add conditions to the search query if necessary. To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span> 
    
    ```
    kind:im
    ``` 

4. <span data-ttu-id="6a3d0-154">この時点で、**場所**の下の次のオプションのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-154">At this point, you can choose one of the following options under **Locations**:</span></span>
    
    - <span data-ttu-id="6a3d0-p113">**すべての場所**に、組織内のすべてのユーザーのメールボックスを検索するには、このオプションを選択します。チェック ボックスをオンにすると、オンプレミスのユーザーのすべてのクラウド ベースのメールボックスも検索されます。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p113">**All locations** - Select this option to search the mailboxes of all users in your organization. When the checkbox is selected, all cloud-based mailboxes for on-premises users will also be searched.</span></span> 
    
    - <span data-ttu-id="6a3d0-p114">**特定の場所**には、このオプションを選択し、[**変更**] をクリックして\>特定のメールボックスを検索するには、ユーザー、グループ、またはチームを選択します。説明したようの場所の選択、オンプレミスのユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p114">**Specific locations** - Select this option and then click **Modify** \> Choose user, groups, or teams to search specific mailboxes. As previously explained, the locations picker will let you search for on-premises users.</span></span> 
    
5. <span data-ttu-id="6a3d0-p115">保存し、検索を実行します。その他の検索結果のように、オンプレミス ユーザーのクラウド ベースのメールボックスからすべての検索結果をプレビューできます。さらに、することができます (データを含むすべてのチーム チャット) の検索結果を PST ファイルにエクスポートできます。詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p115">Save and run the search. Any search results from the cloud-based mailboxes for on-premises users can be previewed like any other search results. Additionally, you can you can export the search results (including any Teams chat data) to a PST file. For more information, see:</span></span> 
    
    - [<span data-ttu-id="6a3d0-163">検索の新規作成します。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-163">Create a new search</span></span>](content-search.md#create-a-new-search)
    
    - [<span data-ttu-id="6a3d0-164">検索結果のプレビュー</span><span class="sxs-lookup"><span data-stu-id="6a3d0-164">Preview search results</span></span>](content-search.md#preview-search-results)
    
    - [<span data-ttu-id="6a3d0-165">Office 365 のセキュリティ コンテンツの検索結果をエクスポートする&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="6a3d0-165">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="6a3d0-166">PowerShell を使用して、オンプレミス ユーザーのメールボックスをクラウド ベースのチームのチャット データを検索するには</span><span class="sxs-lookup"><span data-stu-id="6a3d0-166">Using PowerShell to search for Teams chat data in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="6a3d0-p116">**新規 ComplianceSearch**と**セット ComplianceSearch**コマンドレットを使用するには Office 365 のセキュリティで&amp;コンプライアンス センター PowerShell オンプレミス ユーザーのクラウド ベースのメールボックスを検索します。説明したように PowerShell を使用して、オンプレミス ユーザーのチーム チャットのデータを検索するサポート要求を送信する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p116">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Office 365 Security &amp; Compliance Center PowerShell to search the cloud-based mailbox for on-premises users. As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
1. <span data-ttu-id="6a3d0-169">[Office 365 のセキュリティへの接続&amp;コンプライアンス センター PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-169">[Connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="6a3d0-170">次の PowerShell を実行する新しいコンテンツを作成するコマンドは、クラウド ベースのメールボックスは、オンプレミスのユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-170">Run the following PowerShell command to create a new content searches the cloud-based mailboxes of on-premises users.</span></span>
    
    ```
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```
   
    <span data-ttu-id="6a3d0-p117">*IncludeUserAppContent*パラメーターを使用して、ユーザーまたは*ExchangeLocation*パラメーターで指定されているユーザーのクラウド ベースのメールボックスを指定します。*AllowNotFoundExchangeLocationsEnabled*は、オンプレミス ユーザーのクラウド ベースのメールボックスを使用します。使用する場合、`$true`を実行する前にメールボックスの存在を検証しようとしていない検索は、このパラメーターの値です。これは、機能は、通常のメールボックスとメールボックスのこれらの型が解決しないために、オンプレミス ユーザーのクラウド ベースのメールボックスを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p117">The  *IncludeUserAppContent*  parameter is used to specify the cloud-based mailbox for the user or users who are specified by the  *ExchangeLocation*  parameter. The  *AllowNotFoundExchangeLocationsEnabled*  allows cloud-based mailboxes for on-premises users. When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs. This is required to search the cloud-based mailboxes for on-premises users because these types of mailboxes don't resolve as regular mailboxes.</span></span> 
    
    <span data-ttu-id="6a3d0-175">次の使用例は、チームのキーワード「redstone」、クラウド ベースのメールボックス Contoso の組織で、オンプレミス ユーザーである早川さん岡崎のが含まれているチャット (これは、インスタント メッセージ) を検索します。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-175">The following example searches for Teams chats (which are instant messages) that contain keyword "redstone" in the cloud-based mailbox of Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="6a3d0-176">新しい検索を作成したら、必ず**開始 ComplianceSearch**コマンドレットを使用して検索を実行してください。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-176">After you create a new search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span> 
  
<span data-ttu-id="6a3d0-177">これらのコマンドレットを使用しての詳細については、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-177">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="6a3d0-178">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="6a3d0-178">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)
    
- [<span data-ttu-id="6a3d0-179">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="6a3d0-179">Set-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)
    
- [<span data-ttu-id="6a3d0-180">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="6a3d0-180">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)
    

## <a name="known-issues"></a><span data-ttu-id="6a3d0-181">既知の問題</span><span class="sxs-lookup"><span data-stu-id="6a3d0-181">Known issues</span></span>

- <span data-ttu-id="6a3d0-p118">現時点では、検索、プレビュー、およびクラウド ベースのメールボックス用のコンテンツのエクスポート、オンプレミスのユーザーだけでできます。電子的証拠開示に関連する保留リストに、オンプレミスのユーザーのためのクラウド ベースのメールボックスを配置する場合、または Office 365 のリテンション ・ ポリシーを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p118">Currently, you can only search, preview, and export content in cloud-based mailboxes for on-premises users. Placing a cloud-based mailbox for an on-premises user on a hold associated with an eDiscovery case or assigning it to an Office 365 retention policy is not supported.</span></span> 
    
- <span data-ttu-id="6a3d0-p119">電子的証拠開示のコンテンツの場所の選択は、オンプレミス ユーザーの表示を保持し、それらを選択することが。ただし、保留リストは、オンプレミス ユーザーには適用されませんを説明したようします。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p119">The content location picker for eDiscovery holds displays on-premises users and will let you select them. However, as previously explained the hold will not be applied to the on-premises user.</span></span>
    
## <a name="frequently-asked-questions"></a><span data-ttu-id="6a3d0-186">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="6a3d0-186">Frequently asked questions</span></span>

 <span data-ttu-id="6a3d0-187">**オンプレミス ユーザーのクラウド ベースのメールボックスが配置される場所ですか。**</span><span class="sxs-lookup"><span data-stu-id="6a3d0-187">**Where are cloud-based mailboxes for on-premises users located?**</span></span>
  
<span data-ttu-id="6a3d0-188">クラウド ベースのメールボックスが作成され、Office 365 の組織と同じデータ センターに格納されています。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-188">Cloud-based mailboxes are created and stored in the same datacenter as your Office 365 organization.</span></span> 
  
 <span data-ttu-id="6a3d0-189">**サポート要求を送信する以外の他の要件はありますか。**</span><span class="sxs-lookup"><span data-stu-id="6a3d0-189">**Are there any other requirements other than submitting a support request?**</span></span>
  
 <span data-ttu-id="6a3d0-p120">説明したようは Office 365 で、オンプレミス ユーザー アカウントに対応するメール ユーザー アカウントを作成するために prem にメールボックスを持つユーザーの id クラウド ベースの組織に同期する必要があります。さらに、組織では、Office 365 のエンタープライズの E1、E3、E5 のサブスクリプションなど、Office 365 のエンタープライズ サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p120">As previously explained, the identities of users with on-prem mailboxes must be synchronized to your cloud-based organization so that a corresponding mail user account is created for each on-premises user account in Office 365. Additionally, your organization must have an Office 365 enterprise subscription, such as an Office 365 Enterprise E1, E3, or E5 subscription.</span></span> 
  
 <span data-ttu-id="6a3d0-192">**クラウドに移行するユーザーのオンプレミスのメールボックスを移行する場合、チーム チャット データを失う可能性がありますか。**</span><span class="sxs-lookup"><span data-stu-id="6a3d0-192">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="6a3d0-p121">違います。オンプレミス ユーザーのプライマリ メールボックスをクラウドに移行するとき、新しいクラウド ベースのプライマリ メールボックスにそのユーザーのチーム チャットのデータが移行されます。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p121">No. When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="6a3d0-195">**適用できる電子的証拠開示の保留中または保存ポリシーを Office 365 をオンプレミス ユーザーでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="6a3d0-195">**Can I apply an eDiscovery hold or Office 365 retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="6a3d0-196">いいえ。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-196">No.</span></span>
  
 <span data-ttu-id="6a3d0-197">**古いチームのチャット、オンプレミス ユーザーの時間の前に自分の所属組織のコンテンツの検索検索がこの機能を有効にする要求を送信することができますか。**</span><span class="sxs-lookup"><span data-stu-id="6a3d0-197">**Can Content Search find older Teams chats for on-premises users before the time my organization submitted the request to enable this feature?**</span></span>
  
<span data-ttu-id="6a3d0-p122">マイクロソフトでは、2018 年 1 月 31 日に、チーム チャット、オンプレミスのユーザーのデータを格納する開始しました。設置チームのユーザーの id は、この日付以降 Active Directory と Active Directory の Azure の間で同期されたが、チーム チャット データによってクラウド ベースのメールボックスに保存してコンテンツの検索を使用して検索可能になります。マイクロソフトは、オンプレミス ユーザーのクラウド ベースのメールボックスで、2018 年 1 月 31 日前からチーム チャットのデータを格納する方法についても取り組んでいます。詳細については、間もなく提供されます。</span><span class="sxs-lookup"><span data-stu-id="6a3d0-p122">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018. So, if the identity of an on-premises Teams user has been synched between Active Directory and Azure Active Directory since this date, then their Teams chat data will be stored in a cloud-based mailbox and will be searchable using Content Search. Microsoft is also working on storing Teams chat data from prior to January 31, 2018 in the cloud-based mailboxes for on-premises users. More information about this will be available soon.</span></span>
