---
title: Office 365 Cloud App Security を使用して OAuth アプリを管理する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: office 365 の OAuth アプリ Cloud App Security は、ユーザーが office 365 データで使用するためにダウンロードするアプリを管理するのに役立ちます。
ms.openlocfilehash: 0d9916414d55abb73fd99eaf30c3b6df0648b191
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260187"
---
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a><span data-ttu-id="8a7ba-103">Office 365 Cloud App Security を使用して OAuth アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="8a7ba-103">Manage OAuth apps using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="8a7ba-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="8a7ba-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="8a7ba-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="8a7ba-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="8a7ba-106">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="8a7ba-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="8a7ba-107">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="8a7ba-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="8a7ba-108">評価の開始</span><span class="sxs-lookup"><span data-stu-id="8a7ba-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="8a7ba-109">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="8a7ba-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="8a7ba-110">展開を開始する</span><span class="sxs-lookup"><span data-stu-id="8a7ba-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="8a7ba-111">ここでは、</span><span class="sxs-lookup"><span data-stu-id="8a7ba-111">You are here!</span></span>  <br/> [<span data-ttu-id="8a7ba-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="8a7ba-112">Next steps</span></span>](#next-steps)<br/> |
   
<span data-ttu-id="8a7ba-113">多くのユーザーは、アプリとアプリをよく利用しています。特に、ユーザーが職場または学校の情報を使いやすくすることにより、時間の節約になると考えられるアプリです。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-113">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information.</span></span> <span data-ttu-id="8a7ba-114">ただし、アプリケーションによっては、ユーザーがアクセスする情報やその情報を処理する方法によっては、組織にとってセキュリティ上のリスクが生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-114">However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information.</span></span> <span data-ttu-id="8a7ba-115">[Office 365 Cloud App Security](office-365-cas-overview.md)では、グローバルまたはセキュリティの管理者である場合、組織のために OAuth アプリを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-115">With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage OAuth apps for your organization.</span></span> <span data-ttu-id="8a7ba-116">ユーザーが Office 365 データで使用しているアプリ、それらのアプリのアクセス許可などが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-116">You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="8a7ba-117">この記事では、OAuth アプリの管理方法、アプリの承認、禁止、またはレポートの方法、およびアプリのクエリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-117">This article describes where to go to manage OAuth apps, how to approve, ban, or report an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a><span data-ttu-id="8a7ba-118">[OAuth アプリの管理] ページの検索方法</span><span class="sxs-lookup"><span data-stu-id="8a7ba-118">How to find the Manage OAuth apps page</span></span>

> [!NOTE]
> <span data-ttu-id="8a7ba-119">OAuth アプリは、Office 365 Cloud App Security ポータルで管理されます。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-119">OAuth apps are managed in the Office 365 Cloud App Security portal.</span></span> <span data-ttu-id="8a7ba-120">次のタスクを実行するには、全体管理者またはセキュリティ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-120">You must be a global administrator or security administrator to perform the following task.</span></span> <span data-ttu-id="8a7ba-121">詳細について[は、「Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-121">To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="8a7ba-122">Cloud App Security ポータル ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-122">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="8a7ba-123">[ \*\*\*\* \> **OAuth アプリ**の調査] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-123">Choose **Investigate** \> **OAuth apps**.</span></span><br/><span data-ttu-id="8a7ba-124">![O365 CAS ポータルで、[調査] を選択します。](media/OCAS-OAuthApps.png)</span><span class="sxs-lookup"><span data-stu-id="8a7ba-124">![In the O365 CAS portal, choose Investigate.](media/OCAS-OAuthApps.png)</span></span><br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a><span data-ttu-id="8a7ba-125">[OAuth アプリの管理] ページに表示される内容</span><span class="sxs-lookup"><span data-stu-id="8a7ba-125">What you'll see on the Manage OAuth apps page</span></span>

<span data-ttu-id="8a7ba-126">次の表では、[OAuth アプリの管理] ページで使用できるコントロールとオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-126">The following table describes the controls and options available on the Manage OAuth apps page.</span></span>
  
|<span data-ttu-id="8a7ba-127">**Item**</span><span class="sxs-lookup"><span data-stu-id="8a7ba-127">**Item**</span></span>|<span data-ttu-id="8a7ba-128">**説明**</span><span class="sxs-lookup"><span data-stu-id="8a7ba-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8a7ba-129">アプリクエリバーの [基本] アイコン</span><span class="sxs-lookup"><span data-stu-id="8a7ba-129">Basic icon in the app query bar</span></span>  <br/> ![クエリの基本的なクエリビューを示すアイコン](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="8a7ba-131">[詳細] ビューに切り替えるには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-131">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="8a7ba-132">( **Basic**が表示されている場合は、[詳細設定] ビューを使用しています)</span><span class="sxs-lookup"><span data-stu-id="8a7ba-132">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="8a7ba-133">アプリクエリバーの [詳細] アイコン</span><span class="sxs-lookup"><span data-stu-id="8a7ba-133">Advanced icon in the app query bar</span></span>  <br/> ![クエリの高度なクエリビューを示すアイコン](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="8a7ba-135">[基本] ビューに切り替えるには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-135">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="8a7ba-136">( **[詳細**] が表示されている場合は、基本ビューを使用しています)。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-136">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="8a7ba-137">アプリリストのすべての詳細アイコンを開くか閉じる</span><span class="sxs-lookup"><span data-stu-id="8a7ba-137">Open or close all details icon in the app list</span></span>  <br/> ![すべてのアプリの詳細を開いたり閉じたりするには、このアイコンをクリックします。](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="8a7ba-139">このアイコンを選択すると、各アプリの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-139">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="8a7ba-140">アプリリストの [エクスポート] アイコン</span><span class="sxs-lookup"><span data-stu-id="8a7ba-140">Export icon in the app list</span></span>  <br/> ![すべてのアプリの csv ファイルをエクスポートするには、このアイコンをクリックします。](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="8a7ba-142">アプリのリスト、各アプリのユーザー数、アプリに関連付けられているアクセス許可、アクセス許可レベル、アプリの状態、コミュニティの使用レベルを含む CSV ファイルをエクスポートするには、このアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-142">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="8a7ba-143">名前</span><span class="sxs-lookup"><span data-stu-id="8a7ba-143">Name</span></span>  <br/> |<span data-ttu-id="8a7ba-144">これを使用して、アプリの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-144">Use this to see the name of an app.</span></span> <span data-ttu-id="8a7ba-145">名前を選択して、説明、発行元、アプリ web サイト、アプリ ID などの詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-145">Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="8a7ba-146">承認者</span><span class="sxs-lookup"><span data-stu-id="8a7ba-146">Authorized by</span></span>  <br/> |<span data-ttu-id="8a7ba-147">これを使用して、Office 365 アカウントにアクセスするためにアプリを承認したユーザーの数を確認します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-147">Use this to see how many users have authorized an app to access their Office 365 account.</span></span> <span data-ttu-id="8a7ba-148">ユーザーアカウントの一覧などの詳細情報を表示する番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-148">Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="8a7ba-149">アクセス許可レベル</span><span class="sxs-lookup"><span data-stu-id="8a7ba-149">Permissions Level</span></span>  <br/> ![アプリの permisiions レベルを示すアイコン](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="8a7ba-151">これを使用して、アプリが Office 365 データにアクセスするのにかかった時間を確認します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-151">Use this to see how much access an app has to Office 365 data.</span></span> <span data-ttu-id="8a7ba-152">アクセス許可レベルは、**低**、**中**、**高**のいずれかを示します。**低**は、アプリがユーザーのプロファイルと名前にのみアクセスすることを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-152">Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name.</span></span> <span data-ttu-id="8a7ba-153">[レベル] を選択して、アプリに付与されたアクセス許可、コミュニティの使用、および[ガバナンスログ](suspend-or-restore-an-account-in-ocas.md)の関連するアクティビティなど、詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-153">Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).</span></span>  <br/> |
|<span data-ttu-id="8a7ba-154">前回の承認済み</span><span class="sxs-lookup"><span data-stu-id="8a7ba-154">Last authorized</span></span> <br/> |<span data-ttu-id="8a7ba-155">これを使用して、OAuth アプリが、組織の Office 365 データにアクセスするために最後に承認された日時を表示します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-155">Use this to see the date and time an OAuth app was last authorized to access your organization's Office 365 data.</span></span> <br/>  |
|<span data-ttu-id="8a7ba-156">アクション</span><span class="sxs-lookup"><span data-stu-id="8a7ba-156">Actions</span></span><br/>![OAuth アプリ](media/OCAS-OAuthAppApproveBanReport.png)<br/> |<span data-ttu-id="8a7ba-158">これを使用して、アプリを承認済みまたは禁止済みとしてマークしたり、OAuth アプリを Microsoft に報告したり、未確定のままにしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-158">Use this to see or to mark an app as Approved or Banned, report an OAuth app to Microsoft, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="8a7ba-159">アプリを承認済みとしてマークする</span><span class="sxs-lookup"><span data-stu-id="8a7ba-159">Mark an app as approved</span></span>

<span data-ttu-id="8a7ba-160">[ **OAuth アプリの管理**] ページで、承認するアプリを見つけて、[**アプリを承認済みとしてマーク**する] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-160">On the **Manage OAuth apps** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![[アプリを承認済みとしてマークする] アイコンを選択する](media/OCAS-MarkOAuthApproved.png)
  
<span data-ttu-id="8a7ba-162">アイコンは緑になり、アプリはすべての Office 365 ユーザーに対して承認されます。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-162">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8a7ba-163">アプリを承認済みとしてマークした場合、エンドユーザーに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-163">When you mark an app as approved, there is no effect on the end user.</span></span> <span data-ttu-id="8a7ba-164">承認されたアプリを視覚的にマークすることで、まだレビューされていないアプリから分離することができます。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-164">Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="8a7ba-165">アプリの禁止</span><span class="sxs-lookup"><span data-stu-id="8a7ba-165">Ban an app</span></span>

1. <span data-ttu-id="8a7ba-166">[ **OAuth アプリの管理**] ページで、禁止するアプリを見つけ、[アプリを**禁止済みとしてマーク**] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-166">On the **Manage OAuth apps** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span><br/><span data-ttu-id="8a7ba-167">![アプリを禁止済みとしてマークするアイコンを選択する](media/OCAS-MarkOAuthBanned.png)</span><span class="sxs-lookup"><span data-stu-id="8a7ba-167">![Choose the Mark app as banned icon](media/OCAS-MarkOAuthBanned.png)</span></span>
  
2. <span data-ttu-id="8a7ba-168">[通知メッセージ] ボックスで、既存のテキストをそのまま使用するか、テキストをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-168">In the notification message box, keep the existing text as it is, or customize the text.</span></span> <span data-ttu-id="8a7ba-169">アプリが禁止されていることをユーザーに知らせるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-169">Choose whether to let users know that their app has been banned.</span></span> <br/>![禁止されたアプリのメールテンプレート](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. <span data-ttu-id="8a7ba-171">[**アプリの禁止**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-171">Choose **Ban app**.</span></span>

## <a name="report-an-oauth-app-to-microsoft"></a><span data-ttu-id="8a7ba-172">OAuth アプリを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="8a7ba-172">Report an OAuth app to Microsoft</span></span>

<span data-ttu-id="8a7ba-173">分析のために OAuth アプリを Microsoft に提出する場合は、そのアプリを報告することができます。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-173">If you want to submit an OAuth app to Microsoft for analysis, you can report that app.</span></span>

1. <span data-ttu-id="8a7ba-174">[ **OAuth アプリの管理**] ページで、分析のために提出するアプリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-174">On the **Manage OAuth apps** page, locate the app you want to submit for analysis.</span></span>

2. <span data-ttu-id="8a7ba-175">上下の省略記号を選択してから、[**レポートアプリ...**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-175">Choose the vertical ellipsis, and then choose **Report app...**.</span></span><br/><span data-ttu-id="8a7ba-176">![OAuth アプリを報告する](media/OCAS-MarkOAuthReported.png)</span><span class="sxs-lookup"><span data-stu-id="8a7ba-176">![Report an OAuth app](media/OCAS-MarkOAuthReported.png)</span></span><br/>

3. <span data-ttu-id="8a7ba-177">[**このアプリを報告**する] ダイアログボックスで、ドロップダウンリストを使用して問題を示します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-177">In the **Report this app** dialog box, use the drop-down list to indicate your concern.</span></span> <span data-ttu-id="8a7ba-178">既定では、[**このアプリは悪意**があります] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-178">By default, **This app is malicious** is selected.</span></span> <span data-ttu-id="8a7ba-179">ただし、利用可能なその他のオプションのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-179">However, you can choose on one of the other available options.</span></span> <br/><span data-ttu-id="8a7ba-180">![OAuth アプリを報告する](media/OCAS-ReportOAuthApp.png)</span><span class="sxs-lookup"><span data-stu-id="8a7ba-180">![Report an OAuth app](media/OCAS-ReportOAuthApp.png)</span></span><br/>

4. <span data-ttu-id="8a7ba-181">勧め[連絡先] を選択した状態のままにして、リストされている電子メールアドレスを確認 (または編集) します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-181">(Recommended) Keep the option to contact you selected, and confirm (or edit) the email address listed.</span></span>

5. <span data-ttu-id="8a7ba-182">[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-182">Choose **Submit**.</span></span> 
    
## <a name="create-an-app-query"></a><span data-ttu-id="8a7ba-183">アプリクエリを作成する</span><span class="sxs-lookup"><span data-stu-id="8a7ba-183">Create an app query</span></span>

<span data-ttu-id="8a7ba-184">詳細ビューは、次のように使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-184">We recommend using the Advanced view, which looks like this:</span></span> 

![詳細ビュー](media/OCAS-OAuthAppsAdvQueryView.png)

<span data-ttu-id="8a7ba-186">アプリケーションクエリバーで、 **[詳細設定**] が表示されている場合は、[基本] ビューを使用しています。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-186">In the app query bar, if you see **Advanced**, you're using the Basic view.</span></span> <span data-ttu-id="8a7ba-187">[詳細] ビューに移動するには、[**詳細**] をクリック (またはタップ) します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-187">Click (or tap) **Advanced** to go to the Advanced view.</span></span> 

![基本ビュー](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. <span data-ttu-id="8a7ba-189">クエリバーで、 **[フィルターの選択**] の一覧を使用してオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-189">In the query bar, use the **Select a filter** list to choose an option.</span></span> 
    - <span data-ttu-id="8a7ba-190">**アプリ**特定の名前を持つアプリ</span><span class="sxs-lookup"><span data-stu-id="8a7ba-190">**App** Apps with certain names</span></span>
    - <span data-ttu-id="8a7ba-191">**アプリの状態**状態に基づくアプリ (承認済み、禁止、または未定義)</span><span class="sxs-lookup"><span data-stu-id="8a7ba-191">**App state** Apps based on their state (Approved, Banned, or Undetermined)</span></span>
    - <span data-ttu-id="8a7ba-192">**コミュニティの使用**コミュニティの使用に基づくアプリのレベル (珍しい、珍しい、または Common)</span><span class="sxs-lookup"><span data-stu-id="8a7ba-192">**Community use** Apps based on community use levels (Rare, Uncommon, or Common)</span></span>
    - <span data-ttu-id="8a7ba-193">**アクセス許可レベル**特定のアクセス許可レベルに基づくアプリ</span><span class="sxs-lookup"><span data-stu-id="8a7ba-193">**Permission level** Apps based on certain permission levels</span></span> 
    - <span data-ttu-id="8a7ba-194">**アクセス許可**特定のアクセス許可を必要とするアプリ</span><span class="sxs-lookup"><span data-stu-id="8a7ba-194">**Permissions** Apps that require certain permissions</span></span>
    - <span data-ttu-id="8a7ba-195">**Publisher** 特定の発行元のアプリ</span><span class="sxs-lookup"><span data-stu-id="8a7ba-195">**Publisher**  Apps from certain publishers</span></span>
    - <span data-ttu-id="8a7ba-196">**ユーザー**特定のユーザーが承認したアプリ</span><span class="sxs-lookup"><span data-stu-id="8a7ba-196">**User** Apps that a certain user authorized</span></span>
   
2. <span data-ttu-id="8a7ba-197">[ \*\*\*\* 次の\*\*\*\* 値に等しいかどうか] を選択し、フィルターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-197">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
3. <span data-ttu-id="8a7ba-198">さらにフィルターを追加するには、プラス記号 (</span><span class="sxs-lookup"><span data-stu-id="8a7ba-198">To add more filters, select the plus sign (</span></span>![アプリを照会するためのフィルタアイコンを追加する](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="8a7ba-200">) をクリックしてから、手順2と3を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-200">), and then repeat steps 2 and 3.</span></span>
    
4. <span data-ttu-id="8a7ba-201">フィルターを削除するには、[x] (</span><span class="sxs-lookup"><span data-stu-id="8a7ba-201">To remove a filter, select the x (</span></span>![アプリを照会するためのフィルターアイコンを削除する](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="8a7ba-203">) を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-203">) next to a filter name.</span></span>
    
<span data-ttu-id="8a7ba-204">フィルターは自動的に適用され、それに応じてアプリの一覧が更新されます。</span><span class="sxs-lookup"><span data-stu-id="8a7ba-204">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="8a7ba-205">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8a7ba-205">Next steps</span></span>

- [<span data-ttu-id="8a7ba-206">通知を確認して処理を実行する</span><span class="sxs-lookup"><span data-stu-id="8a7ba-206">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="8a7ba-207">[Office 365 Cloud App Security の Web トラフィックログとデータソースを](web-traffic-logs-and-data-sources-for-ocas.md)確認する</span><span class="sxs-lookup"><span data-stu-id="8a7ba-207">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="8a7ba-208">[Office 365 Cloud App Security の使用率のアクティビティを](utilization-activities-for-ocas.md)確認する</span><span class="sxs-lookup"><span data-stu-id="8a7ba-208">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

