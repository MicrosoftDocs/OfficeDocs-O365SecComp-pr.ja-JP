---
title: 3 層の保護用に SharePoint Online サイトを展開する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: '概要: SharePoint Online チーム サイトを作成し、さまざまなレベルの情報保護用に構成します。'
ms.openlocfilehash: 69da99c29d3527285547ed824e45fb7aa31e1910
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257203"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a><span data-ttu-id="de4f5-103">3 層の保護用に SharePoint Online サイトを展開する</span><span class="sxs-lookup"><span data-stu-id="de4f5-103">Deploy SharePoint Online sites for three tiers of protection</span></span>

 <span data-ttu-id="de4f5-104">**概要:** SharePoint Online チーム サイトを作成し、さまざまなレベルの情報保護用に構成します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-104">**Summary:** Create and configure SharePoint Online team sites for various levels of information protection.</span></span>
  
<span data-ttu-id="de4f5-p101">ベースライン、機密、および非常に機密性の高い社外秘の SharePoint Online チーム サイトを設計および展開するには、この記事の手順を実行してください。 これらの 3 層の保護の詳細については、「[Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md)」(SharePoint Online サイトとファイルのセキュリティ保護) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de4f5-p101">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="baseline-sharepoint-online-team-sites"></a><span data-ttu-id="de4f5-107">ベースラインの SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="de4f5-107">Baseline SharePoint Online team sites</span></span>

<span data-ttu-id="de4f5-p102">ベースラインの保護には、パブリックおよびプライベートのチーム サイトが含まれます。 パブリック チーム サイトは、組織内の全ユーザーが検出し、アクセスすることができます。 プライベート サイトは、チーム サイトに関連付けられている Office 365 グループのメンバーのみが検出し、アクセスすることができます。 いずれの種類のチーム サイトも、メンバーがサイトを他のユーザーと共有することを許可しています。</span><span class="sxs-lookup"><span data-stu-id="de4f5-p102">Baseline protection includes both public and private team sites. Public team sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the Office 365 group associated with the team site. Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="de4f5-112">公開</span><span class="sxs-lookup"><span data-stu-id="de4f5-112">Public</span></span>

<span data-ttu-id="de4f5-113">パブリック アクセスとアクセス許可を使用するベースライン SharePoint Online チーム サイトを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-113">To create a baseline SharePoint Online team site with public access and permissions, do the following:</span></span>
  
1. <span data-ttu-id="de4f5-114">SharePoint Online チーム サイト (SharePoint Online 管理者) の管理にも使用されるアカウントを使用して、管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-114">Sign in to the admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="de4f5-115">詳細については、「[一般法人向け Office 365 にサインインする場所](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de4f5-115">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="de4f5-116">タイルの一覧で、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-116">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="de4f5-117">ブラウザーの新しい **SharePoint** タブで、**[+ サイトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-117">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="de4f5-118">**[サイトの作成]** ページで、 **[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-118">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="de4f5-119">**[サイト名]** にパブリック チーム サイト名を入力します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-119">In **Site name**, type a name for the public team site.</span></span> 
    
6. <span data-ttu-id="de4f5-120">**[Team site description]\(チーム サイトの説明\)** に、サイトの目的の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-120">In **Team site description**, type a description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="de4f5-121">**[プライバシー設定]** で、**[パブリック - 組織の全ユーザーがこのサイトにアクセス可能]** を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-121">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="de4f5-122">**[誰を追加しますか]** ウィンドウで、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-122">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="de4f5-123">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-123">Here is your resulting configuration.</span></span>
  
![パブリック SharePoint Online チーム サイトのベースライン レベルの保護。](media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a><span data-ttu-id="de4f5-125">Private</span><span class="sxs-lookup"><span data-stu-id="de4f5-125">Private</span></span>

<span data-ttu-id="de4f5-126">プライベート アクセスとアクセス許可を使用するベースライン SharePoint Online チーム サイトを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-126">To create a baseline SharePoint Online team site with private access and permissions, do the following:</span></span>
  
1. <span data-ttu-id="de4f5-127">SharePoint Online チーム サイト (SharePoint Online 管理者) の管理にも使用されるアカウントを使用して、管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-127">Sign in to the admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="de4f5-128">詳細については、「[一般法人向け Office 365 にサインインする場所](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de4f5-128">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="de4f5-129">タイルの一覧で、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-129">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="de4f5-130">ブラウザーの新しい **SharePoint** タブで、**[+ サイトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-130">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="de4f5-131">**[サイトの作成]** ページで、 **[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-131">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="de4f5-132">**[サイト名]** にプライベート チーム サイト名を入力します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-132">In **Site name**, type a name for the private team site.</span></span> 
    
6. <span data-ttu-id="de4f5-133">**[チーム サイトの説明]** で、サイトの目的の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-133">In **Team site description,** type a description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="de4f5-134">**[プライバシー設定]** で、**[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-134">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="de4f5-135">**[Who do you want to add?]\(追加するユーザー\)** ウィンドウの **[メンバーの追加]** に、このプライベート チーム サイトにアクセスできるユーザー アカウント名を入力します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-135">On the **Who do you want to add?** pane, in **Add members**, type the names of user accounts that have access to this private team site.</span></span>
    
9. <span data-ttu-id="de4f5-136">初期の一連のメンバーをサイトに追加し、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-136">When you are done adding the initial set of members to the site, click **Finish**</span></span>
    
<span data-ttu-id="de4f5-137">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-137">Here is your resulting configuration.</span></span>
  
![プライベート SharePoint Online チーム サイトのベースライン レベルの保護。](media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a><span data-ttu-id="de4f5-139">機密 SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="de4f5-139">Sensitive SharePoint Online team sites</span></span>

<span data-ttu-id="de4f5-140">機密 SharePoint Online チーム サイトは、独立したチーム サイトです。つまり、アクセス許可は、チーム サイトに関連付けられている Office 365 グループのメンバーシップではなく、SharePoint グループのメンバーシップを介して制御されます。</span><span class="sxs-lookup"><span data-stu-id="de4f5-140">A sensitive SharePoint Online team site is an isolated team site, which means that permissions are controlled through membership in SharePoint groups instead of membership in the Office 365 group associated with the team site.</span></span>
  
<span data-ttu-id="de4f5-141">独立したチーム サイトを作成するには、2 つの主な手順があります。</span><span class="sxs-lookup"><span data-stu-id="de4f5-141">To create an isolated team site, there are two main steps.</span></span>
  
### <a name="step-1-design-your-isolated-site"></a><span data-ttu-id="de4f5-142">手順 1: 分離されたサイトを設計する</span><span class="sxs-lookup"><span data-stu-id="de4f5-142">Step 1: Design your isolated site</span></span>

<span data-ttu-id="de4f5-143">分離されたチーム サイトを設計するには、以下を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de4f5-143">To design your isolated team site, you need to determine:</span></span>
  
- <span data-ttu-id="de4f5-144">SharePoint グループとアクセス許可レベル。</span><span class="sxs-lookup"><span data-stu-id="de4f5-144">Your SharePoint groups and permission levels.</span></span>
    
- <span data-ttu-id="de4f5-145">SharePoint グループのメンバーにするアクセス グループのセット。</span><span class="sxs-lookup"><span data-stu-id="de4f5-145">The set of access groups that will be members of your SharePoint groups.</span></span>
    
     <span data-ttu-id="de4f5-146">推奨されるアクセス グループのセットは、サイト メンバー用、サイト閲覧者用、およびサイト管理者用です。</span><span class="sxs-lookup"><span data-stu-id="de4f5-146">The recommended set of access groups is one for site members, one for site viewers, and one for site administrators.</span></span>
    
- <span data-ttu-id="de4f5-147">アクセス グループ内で入れ子のグループを使用するかどうか。</span><span class="sxs-lookup"><span data-stu-id="de4f5-147">Whether you will use nested groups within your access groups.</span></span>
    
<span data-ttu-id="de4f5-148">たとえば、次のような推奨されるグループ構造とアクセス レベルです。</span><span class="sxs-lookup"><span data-stu-id="de4f5-148">For example, the recommended group structure and permission levels look like this:</span></span>
  
|<span data-ttu-id="de4f5-149">**SharePoint グループ**</span><span class="sxs-lookup"><span data-stu-id="de4f5-149">**SharePoint group**</span></span>|<span data-ttu-id="de4f5-150">**アクセス許可レベル**</span><span class="sxs-lookup"><span data-stu-id="de4f5-150">**Permission level**</span></span>|<span data-ttu-id="de4f5-151">**アクセス グループ (例)**</span><span class="sxs-lookup"><span data-stu-id="de4f5-151">**Access group (examples)**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="de4f5-152">[サイト名] のメンバー</span><span class="sxs-lookup"><span data-stu-id="de4f5-152">[site name] Members</span></span>  <br/> |<span data-ttu-id="de4f5-153">編集</span><span class="sxs-lookup"><span data-stu-id="de4f5-153">Edit</span></span>  <br/> |<span data-ttu-id="de4f5-154">[サイト名] のメンバー</span><span class="sxs-lookup"><span data-stu-id="de4f5-154">[site name] Members</span></span>  <br/> |
|<span data-ttu-id="de4f5-155">[サイト名] の閲覧者</span><span class="sxs-lookup"><span data-stu-id="de4f5-155">[site name] Visitors</span></span>  <br/> |<span data-ttu-id="de4f5-156">読み取り</span><span class="sxs-lookup"><span data-stu-id="de4f5-156">Read</span></span>  <br/> |<span data-ttu-id="de4f5-157">[サイト名] の閲覧者</span><span class="sxs-lookup"><span data-stu-id="de4f5-157">[site name] Viewers</span></span>  <br/> |
|<span data-ttu-id="de4f5-158">[サイト名] の所有者</span><span class="sxs-lookup"><span data-stu-id="de4f5-158">[site name] Owners</span></span>  <br/> |<span data-ttu-id="de4f5-159">フル コントロール</span><span class="sxs-lookup"><span data-stu-id="de4f5-159">Full control</span></span>  <br/> |<span data-ttu-id="de4f5-160">[サイト名] の管理者</span><span class="sxs-lookup"><span data-stu-id="de4f5-160">[site name] Admins</span></span>  <br/> |
   
<span data-ttu-id="de4f5-p105">チーム サイトの既定で、SharePoint グループとアクセス許可レベルが作成されます。 アクセス グループの名前を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de4f5-p105">The SharePoint groups and permission levels are created by default for a team site. You need to determine the names of your access groups.</span></span>
  
<span data-ttu-id="de4f5-163">設計プロセスの詳細については、「[分離した SharePoint Online チーム サイトの設計](design-an-isolated-sharepoint-online-team-site.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de4f5-163">For the details of the design process, see [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
### <a name="step-2-deploy-your-isolated-site"></a><span data-ttu-id="de4f5-164">手順 2: 分離されたサイトを展開する</span><span class="sxs-lookup"><span data-stu-id="de4f5-164">Step 2: Deploy your isolated site</span></span>

<span data-ttu-id="de4f5-165">分離されたサイトを展開するには、まず以下を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de4f5-165">To deploy your isolated site, you first need to:</span></span>
  
- <span data-ttu-id="de4f5-166">各アクセス グループに追加するユーザー アカウントとグループを決定します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-166">Determine the user accounts and groups to add to each of your access groups.</span></span>
    
- <span data-ttu-id="de4f5-167">アクセス グループを作成し、ユーザーとグループ メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-167">Create the access groups and add the user and group members.</span></span>
    
<span data-ttu-id="de4f5-168">詳細な手順については、「[分離した SharePoint Online チーム サイトの展開](deploy-an-isolated-sharepoint-online-team-site.md)」の「**フェーズ 1**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de4f5-168">For the detailed steps, see **Phase 1** of [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
<span data-ttu-id="de4f5-169">次に、次の手順で SharePoint Online チーム サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-169">Next, you create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="de4f5-170">SharePoint Online チーム サイト (SharePoint Online 管理者) の管理にも使用されるアカウントを使用して、管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-170">Sign in to the admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="de4f5-171">詳細については、「[一般法人向け Office 365 にサインインする場所](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de4f5-171">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="de4f5-172">タイルのリストで、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-172">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="de4f5-173">ブラウザーの新しい **[SharePoint]** タブで、 **[+ サイトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-173">In the new **SharePoint** tab of your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="de4f5-174">**[サイトの作成]** ページで、**[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-174">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="de4f5-175">**[サイト名]** にプライベート チーム サイト名を入力します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-175">In **Site name**, type a name for the private team site.</span></span>
    
6. <span data-ttu-id="de4f5-176">**[チーム サイトの説明]** に任意の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-176">In **Team site description**, type an optional description.</span></span>
    
7. <span data-ttu-id="de4f5-177">**[プライバシー設定]** で、**[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-177">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="de4f5-178">**[誰を追加しますか]** ウィンドウで、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-178">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="de4f5-179">次に、新しい SharePoint Online チーム サイトから、これらの手順を使用してアクセス許可を構成します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-179">Next, from the new SharePoint Online team site, configure permissions with these steps.</span></span>
  
1. <span data-ttu-id="de4f5-180">サイトへのアクセス要求への対応を担当する IT 管理者または他のユーザーのユーザー プリンシパル名 (UPN) を決定します (belindan@contoso.com は、UPN の一例です)。</span><span class="sxs-lookup"><span data-stu-id="de4f5-180">Determine the User Principal Name (UPN) of the IT administrator or other person who will be responsible for responding to and addressing requests for access to the site (belindan@contoso.com is an example of a UPN).</span></span> 
    
2. <span data-ttu-id="de4f5-181">ツールバーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-181">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
3. <span data-ttu-id="de4f5-182">**[サイトの権限]** ウィンドウで、 **[高度な権限の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-182">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
4. <span data-ttu-id="de4f5-183">ブラウザーの新しい **[権限]** タブで、**[アクセス要求の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-183">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
    
5. <span data-ttu-id="de4f5-184">**[アクセス要求の設定]** ダイアログ ボックスで次のようにします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-184">In the **Access Requests Settings** dialog box:</span></span>
    
  - <span data-ttu-id="de4f5-185">**[サイトと個別のファイルおよびフォルダーの共有をメンバーに許可します]** および **[メンバーが、他のユーザーをサイト メンバー グループ <グループ名> に招待することを許可します]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-185">Clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes.</span></span>
    
  - <span data-ttu-id="de4f5-186">**[すべてのアクセス権要求を以下の電子メール アドレスに送信する]** に手順 1 の IT 管理者の UPN を入力します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-186">Type the UPN of your IT administrator from step 1 in **Send all requests for access**.</span></span>
    
  - <span data-ttu-id="de4f5-187">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-187">Click **OK**.</span></span>
    
6. <span data-ttu-id="de4f5-188">ブラウザーの **[権限]** タブで、一覧の **[[サイト名] のメンバー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-188">On the **Permissions** tab of your browser, click **[site name] Members** in the list.</span></span>
    
7. <span data-ttu-id="de4f5-189">**[ユーザーとグループ]** の **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-189">In **People and Groups**, click **New**.</span></span>
    
8. <span data-ttu-id="de4f5-190">**[共有]** ダイアログ ボックスに、このサイトのサイト メンバー アクセス グループの名前を入力し、選択して **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-190">In the **Share** dialog box, type the name of your site members access group for this site, select it, and then click **Share**.</span></span>
    
9. <span data-ttu-id="de4f5-191">ブラウザーの戻るボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-191">Click the back button on your browser.</span></span>
    
10. <span data-ttu-id="de4f5-192">リスト内の **[[サイト名] の所有者]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-192">Click **[site name] Owners** in the list.</span></span>
    
11. <span data-ttu-id="de4f5-193">**[ユーザーとグループ]** で、**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-193">In **People and Groups**, click **New**.</span></span>
    
12. <span data-ttu-id="de4f5-194">**[共有]** ダイアログ ボックスに、このサイトのサイト管理者アクセス グループの名前を入力し、選択して **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-194">In the **Share** dialog box, type the name of the site administrators access group for this site, select it, and then click **Share**.</span></span>
    
13. <span data-ttu-id="de4f5-195">ブラウザーの戻るボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-195">Click the back button on your browser.</span></span>
    
14. <span data-ttu-id="de4f5-196">リスト内の **[[サイト名] の閲覧者]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-196">Click **[site name] Visitors** in the list.</span></span>
    
15. <span data-ttu-id="de4f5-197">**[ユーザーとグループ]** で、**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-197">In **People and Groups**, click **New**.</span></span>
    
16. <span data-ttu-id="de4f5-198">**[共有]** ダイアログ ボックスに、このサイトのサイト閲覧者アクセス グループの名前を入力し、選択して **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de4f5-198">In the **Share** dialog box, type the name of the site viewers access group for this site, select it, and then click **Share**.</span></span>
    
17. <span data-ttu-id="de4f5-199">ブラウザーの **[アクセス権]** タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="de4f5-199">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="de4f5-200">これらのアクセス権の設定の結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="de4f5-200">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="de4f5-201">**[[サイト名] の所有者]** SharePoint グループには、サイト管理者アクセス グループが含まれます。このアクセス グループのすべてのメンバーは**フル コントロール** アクセス許可レベルを持っています。</span><span class="sxs-lookup"><span data-stu-id="de4f5-201">The **[site name] Owners** SharePoint group contains the site administrators access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="de4f5-202">**[[site name] Members]\([サイト名] のメンバー\)** SharePoint グループには、サイト メンバー アクセス グループが含まれ、このアクセス グループのすべてのメンバーは**編集**アクセス許可レベルを持っています。</span><span class="sxs-lookup"><span data-stu-id="de4f5-202">The **[site name] Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="de4f5-203">**[[サイト名] の閲覧者]** SharePoint グループには、サイト閲覧者アクセス グループが含まれ、このアクセス グループのすべてのメンバーは**読み取り**アクセス許可レベルを持っています。</span><span class="sxs-lookup"><span data-stu-id="de4f5-203">The **[site name] Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="de4f5-204">メンバーが他のメンバーを招待する機能は無効にされています。</span><span class="sxs-lookup"><span data-stu-id="de4f5-204">The ability for members to invite other members is disabled.</span></span>
    
- <span data-ttu-id="de4f5-205">メンバー以外がアクセスを要求する機能は有効にされています。</span><span class="sxs-lookup"><span data-stu-id="de4f5-205">The ability for non-members to request access is enabled.</span></span>
    
<span data-ttu-id="de4f5-206">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-206">Here is your resulting configuration.</span></span>
  
![独立した SharePoint Online チーム サイトの機密レベルの保護。](media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
<span data-ttu-id="de4f5-208">サイトのメンバーは、いずれかのアクセス グループのグループ メンバーシップを使用して、サイトのリソースについて安全に共同作業できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de4f5-208">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a><span data-ttu-id="de4f5-209">非常に機密性の高い社外秘 SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="de4f5-209">Highly confidential SharePoint Online team sites</span></span>

<span data-ttu-id="de4f5-210">非常に機密性の高い社外秘 SharePoint Online チーム サイトは、分離されたチーム サイトです。つまり、チーム サイトに関連付けられた Office 365 グループのメンバーシップではなく、SharePoint グループのメンバーシップを使用してアクセス許可を制御しています。</span><span class="sxs-lookup"><span data-stu-id="de4f5-210">A highly confidential SharePoint Online team site is an isolated team site, which means that permissions are controlled through membership in SharePoint groups instead of membership in the Office 365 group associated with the team site.</span></span>
  
<span data-ttu-id="de4f5-211">非常に機密性の高い社外秘情報とコラボレーション用の分離されたチーム サイトを作成するには、主に 2 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="de4f5-211">To create an isolated team site for highly confidential information and collaboration, there are two main steps.</span></span>
  
### <a name="step-1-design-your-isolated-site"></a><span data-ttu-id="de4f5-212">手順 1: 分離されたサイトを設計する</span><span class="sxs-lookup"><span data-stu-id="de4f5-212">Step 1: Design your isolated site</span></span>

<span data-ttu-id="de4f5-213">分離されたチーム サイトを設計するには、以下を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de4f5-213">To design your isolated team site, you need to determine:</span></span>
  
- <span data-ttu-id="de4f5-214">SharePoint グループとアクセス許可レベル。</span><span class="sxs-lookup"><span data-stu-id="de4f5-214">Your SharePoint groups and permission levels.</span></span>
    
- <span data-ttu-id="de4f5-215">SharePoint グループのメンバーにするアクセス グループのセット。</span><span class="sxs-lookup"><span data-stu-id="de4f5-215">The set of access groups that will be members of your SharePoint groups.</span></span>
    
     <span data-ttu-id="de4f5-216">推奨されるアクセス グループのセットは、サイト メンバー用、サイト閲覧者用、およびサイト管理者用です。</span><span class="sxs-lookup"><span data-stu-id="de4f5-216">The recommended set of access groups is one for site members, one for site viewers, and one for site administrators.</span></span>
    
- <span data-ttu-id="de4f5-217">アクセス グループ内で入れ子のグループを使用するかどうか。</span><span class="sxs-lookup"><span data-stu-id="de4f5-217">Whether you will use nested groups within your access groups.</span></span>
    
<span data-ttu-id="de4f5-218">たとえば、次のような推奨されるグループ構造とアクセス レベルです。</span><span class="sxs-lookup"><span data-stu-id="de4f5-218">For example, the recommended group structure and permission levels look like this:</span></span>
  
|<span data-ttu-id="de4f5-219">**SharePoint グループ**</span><span class="sxs-lookup"><span data-stu-id="de4f5-219">**SharePoint group**</span></span>|<span data-ttu-id="de4f5-220">**アクセス許可レベル**</span><span class="sxs-lookup"><span data-stu-id="de4f5-220">**Permission level**</span></span>|<span data-ttu-id="de4f5-221">**アクセス グループ (例)**</span><span class="sxs-lookup"><span data-stu-id="de4f5-221">**Access group (examples)**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="de4f5-222">[サイト名] のメンバー</span><span class="sxs-lookup"><span data-stu-id="de4f5-222">[site name] Members</span></span>  <br/> |<span data-ttu-id="de4f5-223">編集</span><span class="sxs-lookup"><span data-stu-id="de4f5-223">Edit</span></span>  <br/> |<span data-ttu-id="de4f5-224">[サイト名] のメンバー</span><span class="sxs-lookup"><span data-stu-id="de4f5-224">[site name] Members</span></span>  <br/> |
|<span data-ttu-id="de4f5-225">[サイト名] の閲覧者</span><span class="sxs-lookup"><span data-stu-id="de4f5-225">[site name] Visitors</span></span>  <br/> |<span data-ttu-id="de4f5-226">読み取り</span><span class="sxs-lookup"><span data-stu-id="de4f5-226">Read</span></span>  <br/> |<span data-ttu-id="de4f5-227">[サイト名] の閲覧者</span><span class="sxs-lookup"><span data-stu-id="de4f5-227">[site name] Viewers</span></span>  <br/> |
|<span data-ttu-id="de4f5-228">[サイト名] の所有者</span><span class="sxs-lookup"><span data-stu-id="de4f5-228">[site name] Owners</span></span>  <br/> |<span data-ttu-id="de4f5-229">フル コントロール</span><span class="sxs-lookup"><span data-stu-id="de4f5-229">Full control</span></span>  <br/> |<span data-ttu-id="de4f5-230">[サイト名] の管理者</span><span class="sxs-lookup"><span data-stu-id="de4f5-230">[site name] Admins</span></span>  <br/> |
   
<span data-ttu-id="de4f5-p107">チーム サイトの既定で、SharePoint グループとアクセス許可レベルが作成されます。 アクセス グループの名前を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de4f5-p107">The SharePoint groups and permission levels are created by default for a team site. You need to determine the names of your access groups.</span></span>
  
<span data-ttu-id="de4f5-233">設計プロセスの詳細については、「[分離した SharePoint Online チーム サイトの設計](design-an-isolated-sharepoint-online-team-site.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de4f5-233">For the details of the design process, see [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
### <a name="step-2-deploy-your-isolated-site"></a><span data-ttu-id="de4f5-234">手順 2: 分離されたサイトを展開する</span><span class="sxs-lookup"><span data-stu-id="de4f5-234">Step 2: Deploy your isolated site</span></span>

<span data-ttu-id="de4f5-235">分離されたサイトを展開するには、まず以下を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de4f5-235">To deploy your isolated site, you first need to:</span></span>
  
- <span data-ttu-id="de4f5-236">それぞれのアクセス グループに追加するユーザーとグループ メンバーを決定する</span><span class="sxs-lookup"><span data-stu-id="de4f5-236">Determine the user and group members of each of your access groups</span></span>
    
- <span data-ttu-id="de4f5-237">アクセス グループを作成し、ユーザーおよびグループ メンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="de4f5-237">Create the access groups and add the user and group members</span></span>
    
- <span data-ttu-id="de4f5-238">アクセス グループを使用する独立したチーム サイトを作成する</span><span class="sxs-lookup"><span data-stu-id="de4f5-238">Create an isolated team site that uses your access groups</span></span>
    
<span data-ttu-id="de4f5-239">詳細な手順については、「[分離した SharePoint Online チーム サイトの展開](deploy-an-isolated-sharepoint-online-team-site.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de4f5-239">For the detailed steps, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
<span data-ttu-id="de4f5-240">このアクセス権の設定の結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="de4f5-240">The results of the permission settings are:</span></span>
  
- <span data-ttu-id="de4f5-241">**[[サイト名] の所有者]** SharePoint グループには、サイト管理者アクセス グループが含まれます。このアクセス グループのすべてのメンバーは**フル コントロール** アクセス許可レベルを持っています。</span><span class="sxs-lookup"><span data-stu-id="de4f5-241">The **[site name] Owners** SharePoint group contains the site administrators access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="de4f5-242">**[[site name] Members]\([サイト名] のメンバー\)** SharePoint グループには、サイト メンバー アクセス グループが含まれ、このアクセス グループのすべてのメンバーは**編集**アクセス許可レベルを持っています。</span><span class="sxs-lookup"><span data-stu-id="de4f5-242">The **[site name] Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="de4f5-243">**[[サイト名] の閲覧者]** SharePoint グループには、サイト閲覧者アクセス グループが含まれ、このアクセス グループのすべてのメンバーは**読み取り**アクセス許可レベルを持っています。</span><span class="sxs-lookup"><span data-stu-id="de4f5-243">The **[site name] Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="de4f5-244">メンバーが他のメンバーを招待する機能は無効にされています。</span><span class="sxs-lookup"><span data-stu-id="de4f5-244">The ability for members to invite other members is disabled.</span></span>
    
- <span data-ttu-id="de4f5-245">メンバー以外がアクセスを要求する機能は無効にされています。</span><span class="sxs-lookup"><span data-stu-id="de4f5-245">The ability for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="de4f5-246">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="de4f5-246">Here is your resulting configuration.</span></span>
  
![独立した SharePoint Online チーム サイトの高機密レベルの保護。](media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
<span data-ttu-id="de4f5-248">サイトのメンバーは、いずれかのアクセス グループのグループ メンバーシップを使用して、サイトのリソースについて安全に共同作業できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de4f5-248">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="de4f5-249">次の手順</span><span class="sxs-lookup"><span data-stu-id="de4f5-249">Next step</span></span>

[<span data-ttu-id="de4f5-250">Office 365 ラベルと DLP による SharePoint ファイルの保護</span><span class="sxs-lookup"><span data-stu-id="de4f5-250">Protect SharePoint Online files with Office 365 labels and DLP</span></span>](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a><span data-ttu-id="de4f5-251">関連項目</span><span class="sxs-lookup"><span data-stu-id="de4f5-251">See also</span></span>

[<span data-ttu-id="de4f5-252">SharePoint Online サイトとファイルをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="de4f5-252">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="de4f5-253">選挙運動、非営利組織、およびその他のアジャイル組織のための Microsoft Security ガイダンス</span><span class="sxs-lookup"><span data-stu-id="de4f5-253">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="de4f5-254">クラウド導入およびハイブリッド ソリューション</span><span class="sxs-lookup"><span data-stu-id="de4f5-254">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
