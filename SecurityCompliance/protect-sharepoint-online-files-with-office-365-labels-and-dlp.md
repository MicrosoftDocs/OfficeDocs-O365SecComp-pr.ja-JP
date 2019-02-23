---
title: Office 365 ラベルと DLP による SharePoint ファイルの保護
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2018
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
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: '概要: 情報保護のレベルが多様な SharePoint Online チーム サイトに、Office 365 ラベルとデータ損失防止 (DLP) ポリシーを適用します。'
ms.openlocfilehash: 759722e7e3ba7c07b869d56a271af7d40692d39e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214438"
---
# <a name="protect-sharepoint-online-files-with-office-365-labels-and-dlp"></a><span data-ttu-id="3f6a5-103">Office 365 ラベルと DLP による SharePoint ファイルの保護</span><span class="sxs-lookup"><span data-stu-id="3f6a5-103">Protect SharePoint Online files with Office 365 labels and DLP</span></span>

 <span data-ttu-id="3f6a5-104">**概要:** 情報保護のレベルが多様な SharePoint Online チーム サイトに、Office 365 ラベルとデータ損失防止 (DLP) ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-104">**Summary:** Apply Office 365 labels and data loss prevention (DLP) policies for SharePoint Online team sites with various levels of information protection.</span></span>
  
<span data-ttu-id="3f6a5-p101">この記事にある手順を使用して、ベースライン、機密、および高機密の SharePoint Online チーム サイト用の Office 365 ラベルおよび DLP ポリシーを設計および展開します。これらの 3 つの層の保護について詳しくは、「[Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-p101">Use the steps in this article to design and deploy Office 365 labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="3f6a5-107">そのしくみ</span><span class="sxs-lookup"><span data-stu-id="3f6a5-107">How this works</span></span>
1. <span data-ttu-id="3f6a5-p102">目的のラベルを作成して発行します。それらが発行されるまでに、最大 12 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-p102">Create the desired labels and publish these. It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="3f6a5-110">目的の SharePoint サイトについて、ドキュメント ライブラリの設定を編集して、ライブラリ内の項目にラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-110">For the desired SharePoint sites, edit the document library settings to apply a label to items in the library.</span></span>
3. <span data-ttu-id="3f6a5-111">ラベルに基づいてアクションを実行する DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-111">Create DLP policies to take action based on the labels.</span></span>

<span data-ttu-id="3f6a5-p103">ユーザーがドキュメントをライブラリに追加すると、文書は既定で割り当てられるラベルを受け取ります。ユーザーは、必要に応じてラベルを変更できます。ユーザーが組織外のドキュメントを共有する場合、DLP はラベルが割り当てられているかどうかを確認し、DLP ポリシーがラベルに一致する場合にアクションを実行します。DLP は同様に、他のポリシーの一致を探します。たとえば、クレジット カード番号によるファイルの保護などです (この種類のポリシーが設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-p103">When users add a document to the library, the document will receive the assigned label by default. Users can change the label, if needed. When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label. DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="office-365-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="3f6a5-116">SharePoint Online サイトの Office 365 ラベル</span><span class="sxs-lookup"><span data-stu-id="3f6a5-116">Office 365 labels for your SharePoint Online sites</span></span>

<span data-ttu-id="3f6a5-117">Office 365 のラベルを作成し、SharePoint Online チーム サイトにラベルを割り当てるためのフェーズは 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-117">There are three phases to creating and then assigning Office 365 labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-office-365-label-names"></a><span data-ttu-id="3f6a5-118">フェーズ 1: Office 365 ラベル名を決定する</span><span class="sxs-lookup"><span data-stu-id="3f6a5-118">Phase 1: Determine the Office 365 label names</span></span>

<span data-ttu-id="3f6a5-p104">このフェーズでは、SharePoint Online チーム サイトに適用される 4 レベルの情報保護用に、Office 365 ラベルの名前を決定します。 次の表は、各レベルに推奨される名前の一覧です。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-p104">In this phase, you determine the names of your Office 365 labels for the four levels of information protection applied to SharePoint Online team sites. The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="3f6a5-121">**SharePoint Online チーム サイトの保護レベル**</span><span class="sxs-lookup"><span data-stu-id="3f6a5-121">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="3f6a5-122">**ラベル名**</span><span class="sxs-lookup"><span data-stu-id="3f6a5-122">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3f6a5-123">ベースライン - パブリック</span><span class="sxs-lookup"><span data-stu-id="3f6a5-123">Baseline-Public</span></span>  <br/> |<span data-ttu-id="3f6a5-124">内部パブリック</span><span class="sxs-lookup"><span data-stu-id="3f6a5-124">Internal public</span></span>  <br/> |
|<span data-ttu-id="3f6a5-125">ベースライン - プライベート</span><span class="sxs-lookup"><span data-stu-id="3f6a5-125">Baseline-Private</span></span>  <br/> |<span data-ttu-id="3f6a5-126">Kirkland</span><span class="sxs-lookup"><span data-stu-id="3f6a5-126">Private</span></span>  <br/> |
|<span data-ttu-id="3f6a5-127">機密</span><span class="sxs-lookup"><span data-stu-id="3f6a5-127">Sensitive</span></span>  <br/> |<span data-ttu-id="3f6a5-128">機密</span><span class="sxs-lookup"><span data-stu-id="3f6a5-128">Sensitive</span></span>  <br/> |
|<span data-ttu-id="3f6a5-129">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="3f6a5-129">Highly Confidential</span></span>  <br/> |<span data-ttu-id="3f6a5-130">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="3f6a5-130">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-office-365-labels"></a><span data-ttu-id="3f6a5-131">フェーズ 2: Office 365 のラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="3f6a5-131">Phase 2: Create the Office 365 labels</span></span>

<span data-ttu-id="3f6a5-132">このフェーズでは、さまざまなレベルの情報保護について決定したラベルを作成し、発行します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-132">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
<span data-ttu-id="3f6a5-133">ラベルを作成するには、Office 365 管理センターまたは Microsoft PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-133">To create the labels, you can use the Office 365 Admin center or Microsoft PowerShell.</span></span>
  
### <a name="create-office-365-labels-with-the-office-365-admin-center"></a><span data-ttu-id="3f6a5-134">Office 365 管理センターで Office 365 のラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="3f6a5-134">Create Office 365 labels with the Office 365 Admin center</span></span>

1. <span data-ttu-id="3f6a5-p105">セキュリティ管理者または会社管理者のロールのアカウントを使用して、Office 365 ポータルにサインインします。ヘルプを表示するには、「[Office 365 にサインインする場所](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-p105">Sign in to the Office 365 portal with an account that has the Security Administrator or Company Administrator role. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="3f6a5-137">**[Microsoft Office Home]** タブで、**[管理者]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-137">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="3f6a5-138">ブラウザーの新しい **[Office 管理者センター]** タブで、**[管理センター] > [セキュリティとコンプライアンス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-138">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="3f6a5-139">ブラウザーの新しい **[ホーム – セキュリティとコンプライアンス]** タブをクリックして、**[分類] > [ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-139">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="3f6a5-140">**[ホーム] > [ラベル]** ウィンドウで、**[保持]** タブをクリックして、**[ラベルを作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-140">From the **Home > Labels** pane, click the **Retention** tab, and then click **Create a label**.</span></span>
    
6. <span data-ttu-id="3f6a5-141">**[ラベルに名前をつける]** ウィンドウで、ラベルの名前および管理者とユーザーの説明を入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-141">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

7. <span data-ttu-id="3f6a5-142">**[ラベル設定]** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-142">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="3f6a5-143">**[設定の確認]** ウィンドウで、**[作成]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-143">On the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="3f6a5-144">追加ラベルについて手順 5 から 8 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-144">Repeat steps 5-8 for your additional labels.</span></span>
    
### <a name="create-office-365-labels-with-powershell"></a><span data-ttu-id="3f6a5-145">PowerShell で Office 365 のラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="3f6a5-145">Create Office 365 labels with PowerShell</span></span>

1. <span data-ttu-id="3f6a5-146">[リモート PowerShell を使用して Office 365 セキュリティ &amp; コンプライアンス センターに接続](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)し、セキュリティ管理者ロールまたは会社の管理者ロールを持つアカウントの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-146">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409) and specify the credentials of an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="3f6a5-147">ラベル名の一覧を入力し、PowerShell コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-147">Fill out the list of label names, and then run these commands at the PowerShell command prompt:</span></span>
    
  ```
  $labelNames=@(<list of label names, each enclosed in quotes and separated by commas>)
ForEach ($element in $labelNames){ New-ComplianceTag -Name $element }
  ```

### <a name="publish-your-new-labels"></a><span data-ttu-id="3f6a5-148">新しいラベルを発行する</span><span class="sxs-lookup"><span data-stu-id="3f6a5-148">Publish your new labels</span></span>

<span data-ttu-id="3f6a5-149">次に、以下の手順で新しい Office 365 ラベルを発行します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-149">Next, use these steps to publish the new Office 365 labels.</span></span>
  
1. <span data-ttu-id="3f6a5-150">セキュリティ &amp; コンプライアンス センターの **[ホーム] > [ラベル]** ウィンドウで、 **[保持]** タブをクリックして、**[ラベルの発行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-150">From the **Home > Labels** pane of the Security &amp; Compliance Center, click the **Retention** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="3f6a5-151">**[発行するラベルを選択]** ウィンドウで、**[発行するラベルを選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-151">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="3f6a5-152">**[Choose labels]\(ラベルの選択\)** ウィンドウで、**[追加]** をクリックして 4 つのラベルをすべて選択します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-152">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
4. <span data-ttu-id="3f6a5-153">[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-153">Click **Done**.</span></span>
    
5. <span data-ttu-id="3f6a5-154">**[発行するラベルを選択]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-154">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="3f6a5-155">**[場所の選択]** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-155">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="3f6a5-156">**[ポリシーに名前をつける]** ウィンドウで、**[名前]** にラベルのセットの名前を入力し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-156">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="3f6a5-157">**[設定の確認]** ウィンドウで、**[ラベルの発行]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-157">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-office-365-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="3f6a5-158">フェーズ 3: SharePoint Online サイトに Office 365 ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="3f6a5-158">Phase 3: Apply the Office 365 labels to your SharePoint Online sites</span></span>

<span data-ttu-id="3f6a5-159">以下の手順で Office 365 ラベルを SharePoint Online チーム サイトのドキュメント フォルダーに適用します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-159">Use these steps to apply the Office 365 labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="3f6a5-160">ブラウザーの **Microsoft Office ホーム**のタブで、**[SharePoint]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-160">From the **Microsoft Office Home** tab of your browser, click the **SharePoint** tile.</span></span>
    
2. <span data-ttu-id="3f6a5-161">ブラウザーの新しい **SharePoint** タブで、Office 365 ラベルを割り当てる必要があるサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-161">On the new **SharePoint** tab in your browser, click a site that needs an Office 365 label assigned.</span></span>
    
3. <span data-ttu-id="3f6a5-162">ブラウザーの新しい SharePoint サイト タブで、**[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-162">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="3f6a5-163">設定アイコンをクリックし、**[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-163">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="3f6a5-164">**[権限と管理]** をクリックして、**[このライブラリ内の項目にラベルを適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-164">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="3f6a5-165">**[設定 - ラベルの適用]** で適切なラベルを選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-165">In **Settings-Apply Label**, select the appropriate label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="3f6a5-166">SharePoint Online サイトのタブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-166">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="3f6a5-167">手順 3 - 8 を繰り返して、その他の SharePoint Online サイトに Office 365 ラベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-167">Repeat steps 3-8 to assign Office 365 labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="3f6a5-168">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-168">Here is your resulting configuration.</span></span>
  
![4 種類の SharePoint Online チーム サイト用の Office 365 ラベル。](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="3f6a5-170">SharePoint Online サイトの DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="3f6a5-170">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="3f6a5-171">以下の手順で、SharePoint Online の機密チーム サイト上のドキュメントを組織外と共有するときにユーザーに通知する DLP ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-171">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="3f6a5-172">**[Microsoft Office Home]** タブで、**[管理者]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-172">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
2. <span data-ttu-id="3f6a5-173">ブラウザーの新しい **[Office 管理者センター]** タブで、**[管理センター] > [セキュリティ &amp; コンプライアンス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-173">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
3. <span data-ttu-id="3f6a5-174">ブラウザーの新しい **[セキュリティ &amp; コンプライアンス]** タブで、**[データ損失防止] > [ポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-174">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
4. <span data-ttu-id="3f6a5-175">**[データ損失防止]** ウィンドウで、 **[+ ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-175">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
5. <span data-ttu-id="3f6a5-176">**[テンプレートを使って開始するか、カスタム ポリシーを作成する]** ウィンドウで、**[カスタム]** をクリックして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-176">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="3f6a5-177">**[ポリシーに名前をつける]** ウィンドウの **[名前]** に機密レベル DLP ポリシーの名前を入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-177">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="3f6a5-178">**[場所の選択]** ウィンドウで、**[自分で特定の場所を選択する]** をクリックして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-178">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="3f6a5-179">場所の一覧で、**Exchange メール**と **OneDrive アカウント**の場所を無効にし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-179">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="3f6a5-180">**[Customize the type of content you want to protect]\(保護するコンテンツの種類をカスタマイズする\)** ウィンドウで、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-180">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="3f6a5-181">**[Choose the types of content to protect]\(保護するコンテンツの種類を選択する\)** ウィンドウのドロップダウン ボックスで **[追加]** をクリックしてから、**[ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-181">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="3f6a5-182">**[ラベル]** ウィンドウで、 **[+ 追加]** をクリックして、 **[機密]** ラベルを選択し、 **[追加]** をクリックしてから、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-182">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="3f6a5-183">**[Choose the types of content to protect]\(保護するコンテンツの種類を選択する\)** ウィンドウで、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-183">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="3f6a5-184">**[Customize the type of content you want to protect]\(保護するコンテンツの種類をカスタマイズする\)** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-184">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="3f6a5-185">**[What do you want to do if we detect sensitive info?]\(機密性の高い情報が検出された場合に実行する操作\)** ウィンドウで、**[Customize the tip and email]\(ヒントと電子メールをカスタマイズする\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-185">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="3f6a5-186">**[ポリシー ヒントと電子メール通知をカスタマイズする]** ウィンドウで、**[ポリシー ヒント テキストをカスタマイズする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-186">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="3f6a5-187">機密性の高いファイルを保護するために Azure Information Protection を実装したかどうかに応じて、テキスト ボックスに、次のいずれかのヒントを入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-187">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="3f6a5-p106">組織外のユーザーと共有するには、ファイルをダウンロードしてから開きます。[ファイル]、[文書の保護]、[パスワードを使用して暗号化] の順にクリックし、強力なパスワードを指定します。別の電子メールまたはその他の通信手段でパスワードを送信します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="3f6a5-p107">機密性の高いファイルは、暗号化によって保護されます。IT 部門によってこれらのファイルへのアクセス許可が与えられている外部ユーザーのみが、それらを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="3f6a5-193">あるいは、ファイルを共有する方法について組織外のユーザーに指示する独自のポリシー ヒントを入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-193">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="3f6a5-194">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-194">Click **OK**.</span></span>
    
17. <span data-ttu-id="3f6a5-195">**[機密性の高い情報が検出された場合に実行する操作]** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-195">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="3f6a5-196">**[ポリシーを有効にしますか、または最初にテストしますか?]** ウィンドウで、 **[すぐ有効にします]** をクリックし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-196">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="3f6a5-197">**[設定の確認]** ウィンドウで、**[作成]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-197">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="3f6a5-198">機密 SharePoint Online チーム サイトの最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-198">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![機密 Office 365 ラベルを使用している、独立した SharePoint Online チーム サイトの DLP ポリシー。](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="3f6a5-200">次に、以下の手順で、SharePoint Online の非常に機密性の高い社外秘チーム サイト上のドキュメントを組織外と共有するときにユーザーをブロックする DLP ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-200">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="3f6a5-201">ブラウザーの **[Microsoft Office Home]** タブで、**[セキュリティとコンプライアンス]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-201">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="3f6a5-202">ブラウザーの新しい **[セキュリティとコンプライアンス]** タブで、**[データ損失防止] > [ポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-202">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="3f6a5-203">**[データ損失防止]** ウィンドウで、 **[+ ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-203">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="3f6a5-204">**[テンプレートを使って開始するか、カスタム ポリシーを作成する]** ウィンドウで、**[カスタム]** をクリックして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-204">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="3f6a5-205">**[ポリシーに名前をつける]** ウィンドウの **[名前]** に高機密レベル DLP ポリシーの名前を入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-205">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="3f6a5-206">**[場所の選択]** ウィンドウで、**[自分で特定の場所を選択する]** をクリックして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-206">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="3f6a5-207">場所の一覧で、 **Exchange メール**と **OneDrive アカウント**の場所を無効にし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-207">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="3f6a5-208">**[保護する機密性の高い情報の種類をカスタマイズする]** ウィンドウで、 **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-208">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="3f6a5-209">**[保護するコンテンツの種類を選択する]** ウィンドウのドロップダウン ボックスで **[追加]** をクリックしてから、 **[ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-209">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="3f6a5-210">**[ラベル]** ウィンドウで、 **[+ 追加]** をクリックして、 **[高機密]** ラベルを選択し、 **[追加]** をクリックしてから、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-210">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="3f6a5-211">**[保護するコンテンツの種類を選択する]** ウィンドウで、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-211">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="3f6a5-212">**[Customize the types of sensitive info you want to protect]\(保護する機密情報の種類のカスタマイズ\)** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-212">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="3f6a5-213">**[What do you want to do if we detect sensitive info?]\(機密情報が検出された場合の処理\)** ウィンドウで、**[Customize the tip and email]\(ヒントと電子メールをカスタマイズする)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-213">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="3f6a5-214">**[Customize policy tips and email notifications]\(ポリシー ヒントと電子メール通知のカスタマイズ\)** ウィンドウで、**[Customize the policy tip text]\(ポリシー ヒントのテキストをカスタマイズする\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-214">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="3f6a5-215">次の内容をテキスト ボックスに入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-215">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="3f6a5-p108">組織外のユーザーと共有するには、ファイルをダウンロードしてから開きます。[ファイル]、[文書の保護]、[パスワードを使用して暗号化] の順にクリックし、強力なパスワードを指定します。別の電子メールまたはその他の通信手段でパスワードを送信します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="3f6a5-219">あるいは、ファイルを共有する方法について組織外のユーザーに指示する独自のポリシー ヒントを入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-219">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="3f6a5-220">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-220">Click **OK**.</span></span>
    
17. <span data-ttu-id="3f6a5-221">**[機密性の高い情報が検出された場合に実行する操作]** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-221">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="3f6a5-222">**[ポリシーを有効にしますか、または最初にテストしますか?]** ウィンドウで、 **[すぐ有効にします]** をクリックし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-222">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="3f6a5-223">**[設定の確認]** ウィンドウで、**[作成]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-223">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="3f6a5-224">非常に機密性の高い社外秘 SharePoint Online チーム サイトの最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="3f6a5-224">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![高機密 Office 365 ラベルを使用している、独立した SharePoint Online チーム サイトの DLP ポリシー。](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="3f6a5-226">次の手順</span><span class="sxs-lookup"><span data-stu-id="3f6a5-226">Next step</span></span>

[<span data-ttu-id="3f6a5-227">Azure Information Protection を使用して SharePoint Online ファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="3f6a5-227">Protect SharePoint Online files with Azure Information Protection</span></span>](protect-sharepoint-online-files-with-azure-information-protection.md)
    
## <a name="see-also"></a><span data-ttu-id="3f6a5-228">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f6a5-228">See Also</span></span>

[<span data-ttu-id="3f6a5-229">SharePoint Online サイトとファイルをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="3f6a5-229">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="3f6a5-230">開発/テスト環境の SharePoint Online サイトをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="3f6a5-230">Secure SharePoint Online sites in a dev/test environment</span></span>](secure-sharepoint-online-sites-in-a-dev-test-environment.md)
  
[<span data-ttu-id="3f6a5-231">選挙運動、非営利組織、およびその他のアジャイル組織のための Microsoft Security ガイダンス</span><span class="sxs-lookup"><span data-stu-id="3f6a5-231">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="3f6a5-232">クラウド導入およびハイブリッド ソリューション</span><span class="sxs-lookup"><span data-stu-id="3f6a5-232">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


