---
title: Office 365 Cloud App Security を使用して OAuth アプリを管理する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: OAuth のアプリケーションで Office 365 のクラウド アプリケーションのセキュリティでは、ユーザーが Office 365 のデータを使用するためにダウンロードするアプリケーションを管理できます。
ms.openlocfilehash: ae32e3c6b15f4ad4794a3dd08c3992adaeba655c
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603688"
---
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a><span data-ttu-id="64496-103">Office 365 Cloud App Security を使用して OAuth アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="64496-103">Manage OAuth apps using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="64496-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="64496-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="64496-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="64496-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="64496-106">配置 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="64496-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="64496-107">使用率。</span><span class="sxs-lookup"><span data-stu-id="64496-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="64496-108">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="64496-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="64496-109">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="64496-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="64496-110">展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="64496-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="64496-111">コースです!</span><span class="sxs-lookup"><span data-stu-id="64496-111">You are here!</span></span>  <br/> [<span data-ttu-id="64496-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="64496-112">Next steps</span></span>](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="64496-p101">人のアプリが大好き、多くの場合ダウンロードする人は考慮してくださいアプリケーション特に職場の取得や学校の情報を簡単にすることで時間が短縮されます。ただし、組織にセキュリティ上のリスクの可能性があるいくつかのアプリケーション、に応じてどのような情報にアクセスして、その情報をどのように対処します。[Office 365 のクラウド アプリケーションのセキュリティ](office-365-cas-overview.md)の場合は、グローバル管理者またはセキュリティ管理者、管理できます OAuth アプリ組織の。アプリケーションのユーザーが使用しているを参照してください Office 365 のデータをどのようなアクセス許可アプリケーションがあるとします。</span><span class="sxs-lookup"><span data-stu-id="64496-p101">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information. However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information. With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage OAuth apps for your organization. You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="64496-117">この資料では、OAuth のアプリケーションを管理するための場所、承認、アクセス禁止、または、アプリケーションを報告する方法、およびアプリケーションのクエリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="64496-117">This article describes where to go to manage OAuth apps, how to approve, ban, or report an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a><span data-ttu-id="64496-118">OAuth の管理アプリケーションのページを検索する方法</span><span class="sxs-lookup"><span data-stu-id="64496-118">How to find the Manage OAuth apps page</span></span>

> [!NOTE]
> <span data-ttu-id="64496-p102">OAuth のアプリケーションは、Office 365 のクラウド アプリケーションのセキュリティ関連ポータルで管理されます。次のタスクを実行するには、グローバル ・ アドミニストレーターまたはセキュリティ管理者である必要があります。については多くを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="64496-p102">OAuth apps are managed in the Office 365 Cloud App Security portal. You must be a global administrator or security administrator to perform the following task. To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="64496-122">クラウド アプリケーションのセキュリティ関連ポータルに移動 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="64496-122">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="64496-123">**調査**を選択して\> **OAuth のアプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="64496-123">Choose **Investigate** \> **OAuth apps**.</span></span><br/><span data-ttu-id="64496-124">![O365 CA ポータルでは、調査を選択します。](media/OCAS-OAuthApps.png)</span><span class="sxs-lookup"><span data-stu-id="64496-124">![In the O365 CAS portal, choose Investigate.](media/OCAS-OAuthApps.png)</span></span><br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a><span data-ttu-id="64496-125">OAuth の管理の [アプリ] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="64496-125">What you'll see on the Manage OAuth apps page</span></span>

<span data-ttu-id="64496-126">次の表では、OAuth の管理アプリケーションのページにコントロールと使用可能なオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="64496-126">The following table describes the controls and options available on the Manage OAuth apps page.</span></span>
  
|<span data-ttu-id="64496-127">**アイテム**</span><span class="sxs-lookup"><span data-stu-id="64496-127">**Item**</span></span>|<span data-ttu-id="64496-128">**説明**</span><span class="sxs-lookup"><span data-stu-id="64496-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="64496-129">アプリケーション クエリのバーでの基本のアイコン</span><span class="sxs-lookup"><span data-stu-id="64496-129">Basic icon in the app query bar</span></span>  <br/> ![照会するための基本的なクエリ ビューを示すアイコン](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="64496-131">詳細表示に切り替えるにはこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="64496-131">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="64496-132">(**基本的な**表示される場合は、ビューを使用して高度です)</span><span class="sxs-lookup"><span data-stu-id="64496-132">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="64496-133">アプリケーション クエリ バーの [詳細設定のアイコン</span><span class="sxs-lookup"><span data-stu-id="64496-133">Advanced icon in the app query bar</span></span>  <br/> ![照会するための高度なクエリ ビューを示すアイコン](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="64496-135">基本的なビューに切り替えるにはこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="64496-135">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="64496-136">(**詳細設定**を表示する場合は、ビューを使用して基本。)</span><span class="sxs-lookup"><span data-stu-id="64496-136">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="64496-137">開いたり閉じたりするアプリケーションのリスト内のすべての詳細アイコン</span><span class="sxs-lookup"><span data-stu-id="64496-137">Open or close all details icon in the app list</span></span>  <br/> ![すべてのアプリケーションのすべての詳細を開いたり、閉じたりするには、このアイコンをクリックします。](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="64496-139">各アプリケーションについてのより多くのまたはより少ない詳細を表示するには、このアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="64496-139">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="64496-140">アプリケーションの一覧のアイコンをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="64496-140">Export icon in the app list</span></span>  <br/> ![すべての csv ファイルをエクスポートするには、このアイコンをクリックします。](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="64496-142">アプリケーション、各アプリケーション、アプリケーション、アクセス許可のレベル、アプリケーションの状態に関連付けられているアクセス許可のユーザー数の一覧を含む CSV ファイルにエクスポートするには、このアイコンを選択し、コミュニティは、レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="64496-142">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="64496-143">名前</span><span class="sxs-lookup"><span data-stu-id="64496-143">Name</span></span>  <br/> |<span data-ttu-id="64496-p103">これを使用して、アプリケーションの選択の名前を参照してください、名前、説明、発行元、アプリケーションの web サイトおよびアプリケーション ID などの詳細情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="64496-p103">Use this to see the name of an app. Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="64496-146">によって承認されています。</span><span class="sxs-lookup"><span data-stu-id="64496-146">Authorized by</span></span>  <br/> |<span data-ttu-id="64496-p104">ユーザーの Office 365 アカウントにアクセスするのにアプリケーションが承認されているユーザーの数を表示するのにには、これを使用します。ユーザー アカウントの一覧などの詳細情報を表示するのには番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="64496-p104">Use this to see how many users have authorized an app to access their Office 365 account. Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="64496-149">アクセス許可のレベル</span><span class="sxs-lookup"><span data-stu-id="64496-149">Permissions Level</span></span>  <br/> ![アプリケーションの permisiions のレベルを示すアイコン](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="64496-p105">これを使用して、アプリケーションがどの程度のアクセスが、Office 365 のデータを参照してください。アクセス許可レベルは、**低\*\*\*\*中**、または**高\*\*\*\*低**が、アプリケーションにアクセスするだけ、ユーザーのプロファイルと名前を示す可能性がありますを示します。アプリケーション、コミュニティ、および[ログの管理](suspend-or-restore-an-account-in-ocas.md)に関連する活動に与えられるアクセス許可などの詳細情報を表示するレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="64496-p105">Use this to see how much access an app has to Office 365 data. Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name. Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).  </span></span><br/> |
|<span data-ttu-id="64496-154">最終承認</span><span class="sxs-lookup"><span data-stu-id="64496-154">Last authorized</span></span> <br/> |<span data-ttu-id="64496-155">OAuth アプリケーションが組織の Office 365 のデータにアクセスするのに承認された最後の日時を表示するのにには、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="64496-155">Use this to see the date and time an OAuth app was last authorized to access your organization's Office 365 data.</span></span> <br/>  |
|<span data-ttu-id="64496-156">操作</span><span class="sxs-lookup"><span data-stu-id="64496-156">Actions</span></span><br/>![OAuth のアプリケーション](media/OCAS-OAuthAppApproveBanReport.png)<br/> |<span data-ttu-id="64496-158">参照するか、承認済み] または [禁止、としてアプリケーションをマークするためにマイクロソフトでは、OAuth アプリケーションを報告するときに使用、または未決定の状態そのままです。</span><span class="sxs-lookup"><span data-stu-id="64496-158">Use this to see or to mark an app as Approved or Banned, report an OAuth app to Microsoft, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="64496-159">アプリケーションを承認済みとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="64496-159">Mark an app as approved</span></span>

<span data-ttu-id="64496-160">**OAuth の管理アプリケーション**] ページで、承認するアプリケーションを見つけて**としてマーク アプリケーションの承認**] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="64496-160">On the **Manage OAuth apps** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![承認済みのアイコンとしてマーク アプリケーションを選択します。](media/OCAS-MarkOAuthApproved.png)
  
<span data-ttu-id="64496-162">アイコンが緑色になると、およびすべての Office 365 ユーザーが承認されているアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="64496-162">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64496-p106">アプリを承認済みとしてマークすると、エンド ・ ユーザーへの影響はありません。承認されているアプリケーションを視覚的にマークは、まだ確認されていないアプリケーションからそれらを分離するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="64496-p106">When you mark an app as approved, there is no effect on the end user. Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="64496-165">アプリケーションの使用を禁止します。</span><span class="sxs-lookup"><span data-stu-id="64496-165">Ban an app</span></span>

1. <span data-ttu-id="64496-166">**OAuth の管理アプリケーション**] ページで、アクセスを禁止するアプリケーションを見つけます、**マーク アプリケーションを禁止されている**アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="64496-166">On the **Manage OAuth apps** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span><br/><span data-ttu-id="64496-167">![禁止のアイコンとしてマーク アプリケーションを選択します。](media/OCAS-MarkOAuthBanned.png)</span><span class="sxs-lookup"><span data-stu-id="64496-167">![Choose the Mark app as banned icon](media/OCAS-MarkOAuthBanned.png)</span></span>
  
2. <span data-ttu-id="64496-p107">通知メッセージ] ボックスでは、既存のテキストを保持またはテキストをカスタマイズします。自社のアプリケーションが禁止されているユーザーを通知するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="64496-p107">In the notification message box, keep the existing text as it is, or customize the text. Choose whether to let users know that their app has been banned.</span></span> <br/>![禁止されているアプリケーションのメール ・ テンプレート](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. <span data-ttu-id="64496-171">**禁止ユーザーのアプリケーション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="64496-171">Choose **Ban app**.</span></span>

## <a name="report-an-oauth-app-to-microsoft"></a><span data-ttu-id="64496-172">OAuth アプリケーションをマイクロソフトに報告します。</span><span class="sxs-lookup"><span data-stu-id="64496-172">Report an OAuth app to Microsoft</span></span>

<span data-ttu-id="64496-173">分析のためのマイクロソフトに OAuth アプリケーションを送信する場合は、そのアプリケーションを報告できます。</span><span class="sxs-lookup"><span data-stu-id="64496-173">If you want to submit an OAuth app to Microsoft for analysis, you can report that app.</span></span>

1. <span data-ttu-id="64496-174">**OAuth の管理アプリケーション**] ページで、[分析のために提出するアプリケーションを探します。</span><span class="sxs-lookup"><span data-stu-id="64496-174">On the **Manage OAuth apps** page, locate the app you want to submit for analysis.</span></span>

2. <span data-ttu-id="64496-175">縦の省略記号ボタンを選択し、**レポート アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="64496-175">Choose the vertical ellipsis, and then choose **Report app...**.</span></span><br/><span data-ttu-id="64496-176">![OAuth アプリを報告します。](media/OCAS-MarkOAuthReported.png)</span><span class="sxs-lookup"><span data-stu-id="64496-176">![Report an OAuth app](media/OCAS-MarkOAuthReported.png)</span></span><br/>

3. <span data-ttu-id="64496-p108">**このアプリケーションのレポート**] ダイアログ ボックスで、問題を示すためにドロップダウン リストを使用します。既定では、**このアプリケーションは、悪意のある**が選択されます。ただし、他の利用可能なオプションのいずれかで選択できます。</span><span class="sxs-lookup"><span data-stu-id="64496-p108">In the **Report this app** dialog box, use the drop-down list to indicate your concern. By default, **This app is malicious** is selected. However, you can choose on one of the other available options. </span></span><br/><span data-ttu-id="64496-180">![OAuth アプリを報告します。](media/OCAS-ReportOAuthApp.png)</span><span class="sxs-lookup"><span data-stu-id="64496-180">![Report an OAuth app](media/OCAS-ReportOAuthApp.png)</span></span><br/>

4. <span data-ttu-id="64496-181">(推奨)オプションを選択すると、ユーザーへの連絡をしてくださいと記載されている電子メール アドレスを確認 (または編集) します。</span><span class="sxs-lookup"><span data-stu-id="64496-181">(Recommended) Keep the option to contact you selected, and confirm (or edit) the email address listed.</span></span>

5. <span data-ttu-id="64496-182">[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="64496-182">Choose **Submit**.</span></span> 
    
## <a name="create-an-app-query"></a><span data-ttu-id="64496-183">アプリケーション クエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="64496-183">Create an app query</span></span>

<span data-ttu-id="64496-184">詳細の表示は、次のようなを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64496-184">We recommend using the Advanced view, which looks like this:</span></span> 

![詳細表示](media/OCAS-OAuthAppsAdvQueryView.png)

<span data-ttu-id="64496-p109">アプリケーション クエリ ・ バーで**詳細設定**] を参照してください使用する場合、基本的なビューです。詳細ビューに移動するには、**詳細設定**のをクリックして (またはタップ) します。</span><span class="sxs-lookup"><span data-stu-id="64496-p109">In the app query bar, if you see **Advanced**, you're using the Basic view. Click (or tap) **Advanced** to go to the Advanced view.</span></span> 

![基本ビュー](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. <span data-ttu-id="64496-189">クエリ ・ バーでは、オプションを選択するのに**フィルターを選択**] ボックスの一覧を使用します。</span><span class="sxs-lookup"><span data-stu-id="64496-189">In the query bar, use the **Select a filter** list to choose an option.</span></span> 
    - <span data-ttu-id="64496-190">**アプリケーション**アプリケーションでは特定の名前</span><span class="sxs-lookup"><span data-stu-id="64496-190">**App** Apps with certain names</span></span>
    - <span data-ttu-id="64496-191">**アプリケーションの状態**状態 (承認済み、禁止、または不定) に基づくアプリケーション</span><span class="sxs-lookup"><span data-stu-id="64496-191">**App state** Apps based on their state (Approved, Banned, or Undetermined)</span></span>
    - <span data-ttu-id="64496-192">**コミュニティを使用して**コミュニティに基づくアプリケーションを使用して、レベル (Rare、Uncommon、または共通)</span><span class="sxs-lookup"><span data-stu-id="64496-192">**Community use** Apps based on community use levels (Rare, Uncommon, or Common)</span></span>
    - <span data-ttu-id="64496-193">**アクセス許可のレベル**特定のアクセス許可レベルに基づいてアプリケーション</span><span class="sxs-lookup"><span data-stu-id="64496-193">**Permission level** Apps based on certain permission levels</span></span> 
    - <span data-ttu-id="64496-194">**アクセス許可**特定のアクセス許可を必要とするアプリケーション</span><span class="sxs-lookup"><span data-stu-id="64496-194">**Permissions** Apps that require certain permissions</span></span>
    - <span data-ttu-id="64496-195">**発行元** 特定の発行元からのアプリ</span><span class="sxs-lookup"><span data-stu-id="64496-195">**Publisher**  Apps from certain publishers</span></span>
    - <span data-ttu-id="64496-196">**ユーザー**特定のユーザーが承認されているアプリケーション</span><span class="sxs-lookup"><span data-stu-id="64496-196">**User** Apps that a certain user authorized</span></span>
   
2. <span data-ttu-id="64496-197">**等しい**か**等しくない**がを選択し、[フィルターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="64496-197">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
3. <span data-ttu-id="64496-198">他のフィルターを追加するのには、プラス記号 (を選択します</span><span class="sxs-lookup"><span data-stu-id="64496-198">To add more filters, select the plus sign (</span></span>![アプリケーションを照会するためのフィルター アイコンを追加します。](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="64496-200">)、し、手順 2 と 3 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="64496-200">), and then repeat steps 2 and 3.</span></span>
    
4. <span data-ttu-id="64496-201">フィルターを削除するのには、x (を選択します</span><span class="sxs-lookup"><span data-stu-id="64496-201">To remove a filter, select the x (</span></span>![アプリケーションを照会するためのフィルター アイコンを削除します。](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="64496-203">) フィルター名の横にします。</span><span class="sxs-lookup"><span data-stu-id="64496-203">) next to a filter name.</span></span>
    
<span data-ttu-id="64496-204">フィルターが自動的に適用し、アプリ一覧がそれに応じて更新します。</span><span class="sxs-lookup"><span data-stu-id="64496-204">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="64496-205">次のステップ</span><span class="sxs-lookup"><span data-stu-id="64496-205">Next steps</span></span>

- [<span data-ttu-id="64496-206">確認し、アラート アクションを実行</span><span class="sxs-lookup"><span data-stu-id="64496-206">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="64496-207">お客様の[Web トラフィックのログ、および Office 365 のクラウド アプリケーションのセキュリティのデータ ソース](web-traffic-logs-and-data-sources-for-ocas.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="64496-207">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="64496-208">[Office 365 のクラウド アプリケーションのセキュリティの使用率のアクティビティ](utilization-activities-for-ocas.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="64496-208">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

