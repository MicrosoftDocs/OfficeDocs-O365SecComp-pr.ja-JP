---
title: 保持ラベルと DLP による SharePoint Online ファイルの保護
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
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
description: '概要: 情報保護のレベルが多様な SharePoint Online チーム サイトには、保持ラベルとデータ損失防止 (DLP) ポリシーを適用してください。'
ms.openlocfilehash: 118911f6430c9ae79dec1fa4a32cd0ba8fa536da
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156899"
---
# <a name="protect-sharepoint-online-files-with-retention-labels-and-dlp"></a><span data-ttu-id="5d90f-103">保持ラベルと DLP による SharePoint Online ファイルの保護</span><span class="sxs-lookup"><span data-stu-id="5d90f-103">Protect SharePoint Online files with retention labels and DLP</span></span>

 <span data-ttu-id="5d90f-104">**概要:** 情報保護のレベルが多様な SharePoint Online チーム サイトには、保持ラベルとデータ損失防止 (DLP) ポリシーを適用してください。</span><span class="sxs-lookup"><span data-stu-id="5d90f-104">**Summary:** Apply retention labels and data loss prevention (DLP) policies for SharePoint Online team sites with various levels of information protection.</span></span>
  
<span data-ttu-id="5d90f-105">この記事に示した手順を使用して、ベースライン、機密、および高機密の SharePoint Online チーム サイトに対応する保持ラベルと DLP ポリシーを設計および展開します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-105">Use the steps in this article to design and deploy retention labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="5d90f-106">この 3 層の保護の詳細については、「[SharePoint Online サイトとファイルをセキュリティで保護する](secure-sharepoint-online-sites-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d90f-106">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="5d90f-107">そのしくみ</span><span class="sxs-lookup"><span data-stu-id="5d90f-107">How this works</span></span>
1. <span data-ttu-id="5d90f-108">目的の保持ラベルを作成して、そのラベルを発行します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-108">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="5d90f-109">発行されるまでに最大 12 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="5d90f-109">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="5d90f-110">目的の SharePoint サイトで、ドキュメント ライブラリの設定を編集して、そのライブラリ内のアイテムに目的の保持ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-110">For the desired SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="5d90f-111">保持ラベルに基づいてアクションを実行する DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-111">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="5d90f-112">ユーザーがライブラリにドキュメントを追加すると、そのドキュメントには割り当てられた保持ラベルが既定で付けられます。</span><span class="sxs-lookup"><span data-stu-id="5d90f-112">When users add a document to the library, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="5d90f-113">ユーザーは、このラベルを必要に応じて変更できます。</span><span class="sxs-lookup"><span data-stu-id="5d90f-113">Users can change the label, if needed.</span></span> <span data-ttu-id="5d90f-114">ユーザーが組織の外部とドキュメントを共有するときには、DLP によってラベルが割り当てられているかどうかが確認され、そのラベルと DLP ポリシーが一致するとアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5d90f-114">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="5d90f-115">DLP では、クレジット カード番号が含まれているファイルなど、その他のポリシーの一致も確認されます (この種のポリシーが構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="5d90f-115">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="5d90f-116">SharePoint Online サイトの保持ラベル</span><span class="sxs-lookup"><span data-stu-id="5d90f-116">Retention labels for your SharePoint Online sites</span></span>

<span data-ttu-id="5d90f-117">保持ラベルを作成して、SharePoint Online チーム サイトにラベルを割り当てるためのフェーズは 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="5d90f-117">There are three phases to creating and then assigning retention labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-retention-label-names"></a><span data-ttu-id="5d90f-118">フェーズ 1: 保持ラベルの名前を決定する</span><span class="sxs-lookup"><span data-stu-id="5d90f-118">Phase 1: Determine the retention label names</span></span>

<span data-ttu-id="5d90f-119">このフェーズでは、SharePoint Online チーム サイトに適用される情報保護の 4 つのレベルに応じた保持ラベルの名前を決定します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-119">In this phase, you determine the names of your retention labels for the four levels of information protection applied to SharePoint Online team sites.</span></span> <span data-ttu-id="5d90f-120">次の表は、各レベルに推奨される名前の一覧です。</span><span class="sxs-lookup"><span data-stu-id="5d90f-120">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="5d90f-121">**SharePoint Online チーム サイトの保護レベル**</span><span class="sxs-lookup"><span data-stu-id="5d90f-121">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="5d90f-122">**ラベル名**</span><span class="sxs-lookup"><span data-stu-id="5d90f-122">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5d90f-123">ベースライン - パブリック</span><span class="sxs-lookup"><span data-stu-id="5d90f-123">Baseline-Public</span></span>  <br/> |<span data-ttu-id="5d90f-124">内部パブリック</span><span class="sxs-lookup"><span data-stu-id="5d90f-124">Internal public</span></span>  <br/> |
|<span data-ttu-id="5d90f-125">ベースライン - プライベート</span><span class="sxs-lookup"><span data-stu-id="5d90f-125">Baseline-Private</span></span>  <br/> |<span data-ttu-id="5d90f-126">プライベート</span><span class="sxs-lookup"><span data-stu-id="5d90f-126">Private</span></span>  <br/> |
|<span data-ttu-id="5d90f-127">機密</span><span class="sxs-lookup"><span data-stu-id="5d90f-127">Sensitive</span></span>  <br/> |<span data-ttu-id="5d90f-128">機密</span><span class="sxs-lookup"><span data-stu-id="5d90f-128">Sensitive</span></span>  <br/> |
|<span data-ttu-id="5d90f-129">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="5d90f-129">Highly Confidential</span></span>  <br/> |<span data-ttu-id="5d90f-130">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="5d90f-130">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-retention-labels"></a><span data-ttu-id="5d90f-131">フェーズ 2: 保持ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="5d90f-131">Phase 2: Create the retention labels</span></span>

<span data-ttu-id="5d90f-132">このフェーズでは、情報保護の各レベルに応じて決定したラベルを作成して発行します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-132">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="5d90f-133">セキュリティ管理者または会社の管理者のロールが付与されたアカウントで [Microsoft 365 コンプライアンス ポータル](https://compliance.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-133">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="5d90f-134">ブラウザーの **[ホーム - Microsoft 365 コンプライアンス]** タブで、**[分類] > [ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-134">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="5d90f-135">**[保持ラベル] > [ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-135">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="5d90f-136">**[ラベルの名前の設定]** ウィンドウで、ラベルの名前と、管理者およびユーザーの説明を入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-136">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="5d90f-137">**[ファイル計画の記述子]** ウィンドウで、必要事項を入力してから **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-137">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="5d90f-138">**[ラベルの設定]** ウィンドウで、**[保持]** を **[オン]** にして保持設定を構成します (必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="5d90f-138">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="5d90f-139">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-139">Click **Next**.</span></span>
    
7. <span data-ttu-id="5d90f-140">**[設定の確認]** ウィンドウで、**[ラベルを作成する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-140">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="5d90f-141">追加のラベルごとに、**[ラベルの作成]** をクリックして、必要に応じて手順 3 から 7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-141">For your additional labels, click **Create a label**, and then repeat steps 3-7 as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="5d90f-142">新しいラベルを発行する</span><span class="sxs-lookup"><span data-stu-id="5d90f-142">Publish your new labels</span></span>

<span data-ttu-id="5d90f-143">次は、新しい保持ラベルを発行するために、次に示す手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-143">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="5d90f-144">**[ラベル]** ウィンドウで、**[保持ラベル]** タブをクリックして、**[ラベルの発行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-144">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="5d90f-145">**[発行するラベルの選択]** ウィンドウで、**[発行するラベルの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-145">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="5d90f-146">**[ラベルの選択]** ウィンドウで **[追加]** をクリックして、4 つのラベルをすべて選択してから **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-146">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="5d90f-147">[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-147">Click **Done**.</span></span>
    
5. <span data-ttu-id="5d90f-148">**[発行するラベルを選択]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-148">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="5d90f-149">**[場所の選択]** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-149">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="5d90f-150">**[ポリシーに名前をつける]** ウィンドウで、**[名前]** にラベルのセットの名前を入力し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-150">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5d90f-151">**[設定の確認]** ウィンドウで、 **[ラベルの発行]** をクリックしてから **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-151">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-retention-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="5d90f-152">フェーズ 3: SharePoint Online サイトに保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="5d90f-152">Phase 3: Apply the retention labels to your SharePoint Online sites</span></span>

<span data-ttu-id="5d90f-153">次の手順を使用して、SharePoint Online チーム サイトのドキュメント フォルダーに保持ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-153">Use these steps to apply the retention labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="5d90f-154">[Office 365 ポータル](https://www.office.com)にサインインして、**[SharePoint]** アプリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-154">Sign in to the [Office 365 portal](https://www.office.com), click the **SharePoint** app.</span></span>
    
2. <span data-ttu-id="5d90f-155">ブラウザーの新しい **[SharePoint]** タブで、ラベルを割り当てる必要のあるサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-155">On the new **SharePoint** tab in your browser, click a site that needs a retention label assigned.</span></span>
    
3. <span data-ttu-id="5d90f-156">ブラウザーの新しい SharePoint サイト タブで、**[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-156">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="5d90f-157">設定アイコンをクリックし、**[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-157">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="5d90f-158">**[権限と管理]** をクリックして、 **[このライブラリ内の項目にラベルを適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-158">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="5d90f-159">**[設定 - ラベルの適用]** で、適切なラベルを選択してから **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-159">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="5d90f-160">SharePoint Online サイトのタブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5d90f-160">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="5d90f-161">手順 2 から 8 を繰り返して、追加の SharePoint Online サイトに保持ラベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5d90f-161">Repeat steps 2-8 to assign retention labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="5d90f-162">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-162">Here is your resulting configuration.</span></span>
  
![4 種類の SharePoint Online チーム サイト用の保持ラベル。](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="5d90f-164">SharePoint Online サイトの DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="5d90f-164">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="5d90f-165">以下の手順で、SharePoint Online の機密チーム サイト上のドキュメントを組織外と共有するときにユーザーに通知する DLP ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-165">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="5d90f-166">セキュリティ管理者または会社の管理者のロールが付与されたアカウントで [Microsoft 365 コンプライアンス ポータル](https://compliance.microsoft.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-166">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="5d90f-167">ブラウザーの新しい **[Microsoft 365 コンプライアンス]** タブで、**[ポリシー] > [データ損失防止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-167">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="5d90f-168">**[ホーム] > [データ損失防止]** ウィンドウで、**[ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-168">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="5d90f-169">**[テンプレートを利用するか、カスタム ポリシーを作成します]** ウィンドウで、**[カスタム]** をクリックしてから **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-169">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="5d90f-170">**[ポリシーに名前をつける]** ウィンドウの **[名前]** に機密レベル DLP ポリシーの名前を入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-170">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="5d90f-171">**[場所の選択]** ウィンドウで、**[特定の場所を選択]** をクリックしてから **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-171">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="5d90f-172">場所の一覧で、**[Exchange メール]**、**[OneDrive アカウント]**、および **[Teams のチャットとチャネルのメッセージ]** の場所を無効にして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-172">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5d90f-173">**[保護するコンテンツの種類をカスタマイズする]** ウィンドウで、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-173">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="5d90f-174">**[保護するコンテンツの種類を選ぶ]** ウィンドウのドロップダウン ボックスで **[追加]** をクリックしてから、**[保持ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-174">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="5d90f-175">**[保持ラベル]** ウィンドウで、**[追加]** をクリックして **[機密]** ラベルを選択し、**[追加]** をクリックしてから **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-175">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="5d90f-176">**[保護するコンテンツの種類を選択する]** ウィンドウで、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-176">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="5d90f-177">**保護するコンテンツの種類をカスタマイズする** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-177">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="5d90f-178">**機密性の高い情報が検出された場合に実行する操作** ウィンドウで、**ヒントと電子メールをカスタマイズする** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-178">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="5d90f-179">**[ポリシー ヒントと電子メール通知をカスタマイズする]** ウィンドウで、**[ポリシー ヒント テキストをカスタマイズする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-179">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="5d90f-180">機密性の高いファイルを保護するために Azure Information Protection を実装したかどうかに応じて、テキスト ボックスに、次のいずれかのヒントを入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5d90f-180">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="5d90f-p106">組織外のユーザーと共有するには、ファイルをダウンロードしてから開きます。[ファイル]、[文書の保護]、[パスワードを使用して暗号化] の順にクリックし、強力なパスワードを指定します。別の電子メールまたはその他の通信手段でパスワードを送信します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="5d90f-p107">機密性の高いファイルは、暗号化によって保護されます。IT 部門によってこれらのファイルへのアクセス許可が与えられている外部ユーザーのみが、それらを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="5d90f-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="5d90f-186">あるいは、ファイルを共有する方法について組織外のユーザーに指示する独自のポリシー ヒントを入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5d90f-186">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="5d90f-187">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-187">Click **OK**.</span></span>
    
17. <span data-ttu-id="5d90f-188">**[機密性の高い情報が検出された場合に実行する操作]** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-188">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="5d90f-189">**[ポリシーを有効にしますか、または最初にテストしますか?]** ウィンドウで、 **[すぐ有効にします]** をクリックし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-189">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="5d90f-190">**[設定の確認]** ウィンドウで、**[作成]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-190">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="5d90f-191">機密 SharePoint Online チーム サイトの最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-191">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![「機密」保持ラベルを使用して分離されている SharePoint Online チーム サイトの DLP ポリシー。](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="5d90f-193">次に、以下の手順で、SharePoint Online の非常に機密性の高い社外秘チーム サイト上のドキュメントを組織外と共有するときにユーザーをブロックする DLP ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-193">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="5d90f-194">ブラウザーの新しい **[Microsoft 365 コンプライアンス]** タブで、**[ポリシー] > [データ損失防止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-194">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="5d90f-195">**[データ損失防止]** ウィンドウで、**[ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-195">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="5d90f-196">**[テンプレートを使って開始するか、カスタム ポリシーを作成する]** ウィンドウで、 **[カスタム]** をクリックしてから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-196">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="5d90f-197">**[ポリシーに名前をつける]** ウィンドウの **[名前]** に高機密レベル DLP ポリシーの名前を入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-197">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="5d90f-198">**[場所の選択]** ウィンドウで、 **[自分で特定の場所を選択する]** をクリックしてから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-198">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="5d90f-199">場所の一覧で、**[Exchange メール]**、**[OneDrive アカウント]**、および **[Teams のチャットとチャネルのメッセージ]** の場所を無効にして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-199">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="5d90f-200">**[保護する機密情報の種類をカスタマイズする]** ウィンドウで、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-200">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="5d90f-201">**[保護するコンテンツの種類を選ぶ]** ウィンドウのドロップダウン ボックスで **[追加]** をクリックしてから、**[保持ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-201">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="5d90f-202">**[保持ラベル]** ウィンドウで、**[追加]** をクリックして **[高機密]** ラベルを選択し、**[追加]** をクリックしてから **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-202">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="5d90f-203">**[保護するコンテンツの種類を選択する]** ウィンドウで、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-203">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="5d90f-204">**保護する機密情報の種類のカスタマイズ** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-204">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="5d90f-205">**機密情報が検出された場合の処理** ウィンドウで、**ヒントと電子メールをカスタマイズする** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-205">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="5d90f-206">**ポリシー ヒントと電子メール通知のカスタマイズ** ウィンドウで、**ポリシー ヒントのテキストをカスタマイズする** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-206">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="5d90f-207">次の内容をテキスト ボックスに入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5d90f-207">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="5d90f-p108">組織外のユーザーと共有するには、ファイルをダウンロードしてから開きます。[ファイル]、[文書の保護]、[パスワードを使用して暗号化] の順にクリックし、強力なパスワードを指定します。別の電子メールまたはその他の通信手段でパスワードを送信します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="5d90f-211">あるいは、ファイルを共有する方法について組織外のユーザーに指示する独自のポリシー ヒントを入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5d90f-211">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="5d90f-212">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-212">Click **OK**.</span></span>
    
17. <span data-ttu-id="5d90f-213">**[機密性の高い情報が検出された場合に実行する操作]** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-213">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="5d90f-214">**[ポリシーを有効にしますか、または最初にテストしますか?]** ウィンドウで、 **[すぐ有効にします]** をクリックし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-214">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="5d90f-215">**[設定の確認]** ウィンドウで、**[作成]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d90f-215">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="5d90f-216">非常に機密性の高い社外秘 SharePoint Online チーム サイトの最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="5d90f-216">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![「高機密」保持ラベルを使用して分離されている SharePoint Online チーム サイトの DLP ポリシー。](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="5d90f-218">次の手順</span><span class="sxs-lookup"><span data-stu-id="5d90f-218">Next step</span></span>

[<span data-ttu-id="5d90f-219">Azure Information Protection を使用して SharePoint Online ファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="5d90f-219">Protect SharePoint Online files with Azure Information Protection</span></span>](protect-sharepoint-online-files-with-azure-information-protection.md)
    
## <a name="see-also"></a><span data-ttu-id="5d90f-220">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d90f-220">See Also</span></span>

[<span data-ttu-id="5d90f-221">SharePoint Online サイトとファイルをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="5d90f-221">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="5d90f-222">選挙運動、非営利組織、およびその他のアジャイル組織のための Microsoft Security ガイダンス</span><span class="sxs-lookup"><span data-stu-id="5d90f-222">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="5d90f-223">クラウド導入およびハイブリッド ソリューション</span><span class="sxs-lookup"><span data-stu-id="5d90f-223">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


