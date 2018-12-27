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
ms.openlocfilehash: 2e3c6d9d42b22aa8bb666211431197744471e84f
ms.sourcegitcommit: 25f72d20e76463c2f0a075dfc0116f00c934bd77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/27/2018
ms.locfileid: "27447045"
---
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a><span data-ttu-id="d4248-103">Office 365 Cloud App Security を使用して OAuth アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="d4248-103">Manage OAuth apps using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="d4248-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d4248-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="d4248-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d4248-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="d4248-106">配置 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d4248-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="d4248-107">使用率。</span><span class="sxs-lookup"><span data-stu-id="d4248-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="d4248-108">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="d4248-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="d4248-109">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="d4248-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="d4248-110">展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="d4248-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="d4248-111">コースです!</span><span class="sxs-lookup"><span data-stu-id="d4248-111">You are here!</span></span>  <br/> [<span data-ttu-id="d4248-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="d4248-112">Next steps</span></span>](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="d4248-p101">人のアプリが大好き、多くの場合ダウンロードする人は考慮してくださいアプリケーション特に職場の取得や学校の情報を簡単にすることで時間が短縮されます。ただし、組織にセキュリティ上のリスクの可能性があるいくつかのアプリケーション、に応じてどのような情報にアクセスして、その情報をどのように対処します。[Office 365 のクラウド アプリケーションのセキュリティ](office-365-cas-overview.md)の場合は、グローバル管理者またはセキュリティ管理者、管理できます OAuth アプリ組織の。アプリケーションのユーザーが使用しているを参照してください Office 365 のデータをどのようなアクセス許可アプリケーションがあるとします。</span><span class="sxs-lookup"><span data-stu-id="d4248-p101">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information. However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information. With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage OAuth apps for your organization. You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="d4248-117">この資料では、OAuth のアプリケーションを管理するための場所、承認、アクセス禁止、または、アプリケーションを報告する方法、およびアプリケーションのクエリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4248-117">This article describes where to go to manage OAuth apps, how to approve, ban, or report an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a><span data-ttu-id="d4248-118">OAuth の管理アプリケーションのページを検索する方法</span><span class="sxs-lookup"><span data-stu-id="d4248-118">How to find the Manage OAuth apps page</span></span>

> [!NOTE]
> <span data-ttu-id="d4248-p102">OAuth のアプリケーションは、Office 365 のクラウド アプリケーションのセキュリティ関連ポータルで管理されます。次のタスクを実行するには、グローバル ・ アドミニストレーターまたはセキュリティ管理者である必要があります。については多くを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="d4248-p102">OAuth apps are managed in the Office 365 Cloud App Security portal. You must be a global administrator or security administrator to perform the following task. To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="d4248-p103">[https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用して Office 365 にサインインします。(これで、セキュリティには、&amp;コンプライアンス センター)。</span><span class="sxs-lookup"><span data-stu-id="d4248-p103">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="d4248-124">**アラート**を参照して\>**詳細なアラートを管理**します。</span><span class="sxs-lookup"><span data-stu-id="d4248-124">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="d4248-125">をクリックして (またはタップ) **Office 365 のクラウド アプリケーションのセキュリティに移動**します。</span><span class="sxs-lookup"><span data-stu-id="d4248-125">Click (or tap) **Go to Office 365 Cloud App Security**.</span></span><br/><span data-ttu-id="d4248-126">![セキュリティ&amp;コンプライアンス センターでは、Office 365 のクラウド アプリケーションのセキュリティに移動するのには高度な通知の管理を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="d4248-126">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br/><span data-ttu-id="d4248-p104">**注**: Office 365 のクラウド アプリケーションのセキュリティがまだオンにしない場合は、行うことができますこのページにします。[Office 365 のクラウド アプリケーションのセキュリティの準備](get-ready-for-office-365-cas.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4248-p104">**NOTE**: If Office 365 Cloud App Security is not turned on yet, you can do that on this page. See [Get ready for Office 365 Cloud App Security](get-ready-for-office-365-cas.md).</span></span> 
  
4. <span data-ttu-id="d4248-129">**調査**を選択して\> **OAuth のアプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="d4248-129">Choose **Investigate** \> **OAuth apps**.</span></span><br/><span data-ttu-id="d4248-130">![O365 CA ポータルでは、調査を選択します。](media/OCAS-OAuthApps.png)</span><span class="sxs-lookup"><span data-stu-id="d4248-130">![In the O365 CAS portal, choose Investigate.](media/OCAS-OAuthApps.png)</span></span><br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a><span data-ttu-id="d4248-131">OAuth の管理の [アプリ] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4248-131">What you'll see on the Manage OAuth apps page</span></span>

<span data-ttu-id="d4248-132">次の表では、OAuth の管理アプリケーションのページにコントロールと使用可能なオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d4248-132">The following table describes the controls and options available on the Manage OAuth apps page.</span></span>
  
|<span data-ttu-id="d4248-133">**アイテム**</span><span class="sxs-lookup"><span data-stu-id="d4248-133">**Item**</span></span>|<span data-ttu-id="d4248-134">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4248-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4248-135">アプリケーション クエリのバーでの基本のアイコン</span><span class="sxs-lookup"><span data-stu-id="d4248-135">Basic icon in the app query bar</span></span>  <br/> ![照会するための基本的なクエリ ビューを示すアイコン](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="d4248-137">詳細表示に切り替えるにはこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4248-137">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="d4248-138">(**基本的な**表示される場合は、ビューを使用して高度です)</span><span class="sxs-lookup"><span data-stu-id="d4248-138">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="d4248-139">アプリケーション クエリ バーの [詳細設定のアイコン</span><span class="sxs-lookup"><span data-stu-id="d4248-139">Advanced icon in the app query bar</span></span>  <br/> ![照会するための高度なクエリ ビューを示すアイコン](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="d4248-141">基本的なビューに切り替えるにはこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4248-141">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="d4248-142">(**詳細設定**を表示する場合は、ビューを使用して基本。)</span><span class="sxs-lookup"><span data-stu-id="d4248-142">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="d4248-143">開いたり閉じたりするアプリケーションのリスト内のすべての詳細アイコン</span><span class="sxs-lookup"><span data-stu-id="d4248-143">Open or close all details icon in the app list</span></span>  <br/> ![すべてのアプリケーションのすべての詳細を開いたり、閉じたりするには、このアイコンをクリックします。](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="d4248-145">各アプリケーションについてのより多くのまたはより少ない詳細を表示するには、このアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4248-145">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="d4248-146">アプリケーションの一覧のアイコンをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d4248-146">Export icon in the app list</span></span>  <br/> ![すべての csv ファイルをエクスポートするには、このアイコンをクリックします。](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="d4248-148">アプリケーション、各アプリケーション、アプリケーション、アクセス許可のレベル、アプリケーションの状態に関連付けられているアクセス許可のユーザー数の一覧を含む CSV ファイルにエクスポートするには、このアイコンを選択し、コミュニティは、レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4248-148">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="d4248-149">名前</span><span class="sxs-lookup"><span data-stu-id="d4248-149">Name</span></span>  <br/> |<span data-ttu-id="d4248-p105">これを使用して、アプリケーションの選択の名前を参照してください、名前、説明、発行元、アプリケーションの web サイトおよびアプリケーション ID などの詳細情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="d4248-p105">Use this to see the name of an app. Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="d4248-152">によって承認されています。</span><span class="sxs-lookup"><span data-stu-id="d4248-152">Authorized by</span></span>  <br/> |<span data-ttu-id="d4248-p106">ユーザーの Office 365 アカウントにアクセスするのにアプリケーションが承認されているユーザーの数を表示するのにには、これを使用します。ユーザー アカウントの一覧などの詳細情報を表示するのには番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4248-p106">Use this to see how many users have authorized an app to access their Office 365 account. Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="d4248-155">アクセス許可のレベル</span><span class="sxs-lookup"><span data-stu-id="d4248-155">Permissions Level</span></span>  <br/> ![アプリケーションの permisiions のレベルを示すアイコン](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="d4248-p107">これを使用して、アプリケーションがどの程度のアクセスが、Office 365 のデータを参照してください。アクセス許可レベルは、**低\*\*\*\*中**、または**高\*\*\*\*低**が、アプリケーションにアクセスするだけ、ユーザーのプロファイルと名前を示す可能性がありますを示します。アプリケーション、コミュニティ、および[ログの管理](suspend-or-restore-an-account-in-ocas.md)に関連する活動に与えられるアクセス許可などの詳細情報を表示するレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4248-p107">Use this to see how much access an app has to Office 365 data. Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name. Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).  </span></span><br/> |
|<span data-ttu-id="d4248-160">最終承認</span><span class="sxs-lookup"><span data-stu-id="d4248-160">Last authorized</span></span> <br/> |<span data-ttu-id="d4248-161">OAuth アプリケーションが組織の Office 365 のデータにアクセスするのに承認された最後の日時を表示するのにには、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4248-161">Use this to see the date and time an OAuth app was last authorized to access your organization's Office 365 data.</span></span> <br/>  |
|<span data-ttu-id="d4248-162">操作</span><span class="sxs-lookup"><span data-stu-id="d4248-162">Actions</span></span><br/>![OAuth のアプリケーション](media/OCAS-OAuthAppApproveBanReport.png)<br/> |<span data-ttu-id="d4248-164">参照するか、承認済み] または [禁止、としてアプリケーションをマークするためにマイクロソフトでは、OAuth アプリケーションを報告するときに使用、または未決定の状態そのままです。</span><span class="sxs-lookup"><span data-stu-id="d4248-164">Use this to see or to mark an app as Approved or Banned, report an OAuth app to Microsoft, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="d4248-165">アプリケーションを承認済みとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="d4248-165">Mark an app as approved</span></span>

<span data-ttu-id="d4248-166">**OAuth の管理アプリケーション**] ページで、承認するアプリケーションを見つけて**としてマーク アプリケーションの承認**] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4248-166">On the **Manage OAuth apps** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![承認済みのアイコンとしてマーク アプリケーションを選択します。](media/OCAS-MarkOAuthApproved.png)
  
<span data-ttu-id="d4248-168">アイコンが緑色になると、およびすべての Office 365 ユーザーが承認されているアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="d4248-168">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4248-p108">アプリを承認済みとしてマークすると、エンド ・ ユーザーへの影響はありません。承認されているアプリケーションを視覚的にマークは、まだ確認されていないアプリケーションからそれらを分離するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d4248-p108">When you mark an app as approved, there is no effect on the end user. Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="d4248-171">アプリケーションの使用を禁止します。</span><span class="sxs-lookup"><span data-stu-id="d4248-171">Ban an app</span></span>

1. <span data-ttu-id="d4248-172">**OAuth の管理アプリケーション**] ページで、アクセスを禁止するアプリケーションを見つけます、**マーク アプリケーションを禁止されている**アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4248-172">On the **Manage OAuth apps** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span><br/><span data-ttu-id="d4248-173">![禁止のアイコンとしてマーク アプリケーションを選択します。](media/OCAS-MarkOAuthBanned.png)</span><span class="sxs-lookup"><span data-stu-id="d4248-173">![Choose the Mark app as banned icon](media/OCAS-MarkOAuthBanned.png)</span></span>
  
2. <span data-ttu-id="d4248-p109">通知メッセージ] ボックスでは、既存のテキストを保持またはテキストをカスタマイズします。自社のアプリケーションが禁止されているユーザーを通知するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4248-p109">In the notification message box, keep the existing text as it is, or customize the text. Choose whether to let users know that their app has been banned.</span></span> <br/>![禁止されているアプリケーションのメール ・ テンプレート](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. <span data-ttu-id="d4248-177">**禁止ユーザーのアプリケーション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4248-177">Choose **Ban app**.</span></span>

## <a name="report-an-oauth-app-to-microsoft"></a><span data-ttu-id="d4248-178">OAuth アプリケーションをマイクロソフトに報告します。</span><span class="sxs-lookup"><span data-stu-id="d4248-178">Report an OAuth app to Microsoft</span></span>

<span data-ttu-id="d4248-179">分析のためのマイクロソフトに OAuth アプリケーションを送信する場合は、そのアプリケーションを報告できます。</span><span class="sxs-lookup"><span data-stu-id="d4248-179">If you want to submit an OAuth app to Microsoft for analysis, you can report that app.</span></span>

1. <span data-ttu-id="d4248-180">**OAuth の管理アプリケーション**] ページで、[分析のために提出するアプリケーションを探します。</span><span class="sxs-lookup"><span data-stu-id="d4248-180">On the **Manage OAuth apps** page, locate the app you want to submit for analysis.</span></span>

2. <span data-ttu-id="d4248-181">縦の省略記号ボタンを選択し、**レポート アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4248-181">Choose the vertical ellipsis, and then choose **Report app...**.</span></span><br/><span data-ttu-id="d4248-182">![OAuth アプリを報告します。](media/OCAS-MarkOAuthReported.png)</span><span class="sxs-lookup"><span data-stu-id="d4248-182">![Report an OAuth app](media/OCAS-MarkOAuthReported.png)</span></span><br/>

3. <span data-ttu-id="d4248-p110">**このアプリケーションのレポート**] ダイアログ ボックスで、問題を示すためにドロップダウン リストを使用します。既定では、**このアプリケーションは、悪意のある**が選択されます。ただし、他の利用可能なオプションのいずれかで選択できます。</span><span class="sxs-lookup"><span data-stu-id="d4248-p110">In the **Report this app** dialog box, use the drop-down list to indicate your concern. By default, **This app is malicious** is selected. However, you can choose on one of the other available options. </span></span><br/><span data-ttu-id="d4248-186">![OAuth アプリを報告します。](media/OCAS-ReportOAuthApp.png)</span><span class="sxs-lookup"><span data-stu-id="d4248-186">![Report an OAuth app](media/OCAS-ReportOAuthApp.png)</span></span><br/>

4. <span data-ttu-id="d4248-187">(推奨)オプションを選択すると、ユーザーへの連絡をしてくださいと記載されている電子メール アドレスを確認 (または編集) します。</span><span class="sxs-lookup"><span data-stu-id="d4248-187">(Recommended) Keep the option to contact you selected, and confirm (or edit) the email address listed.</span></span>

5. <span data-ttu-id="d4248-188">[ **Submit**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d4248-188">Choose **Submit**.</span></span> 
    
## <a name="create-an-app-query"></a><span data-ttu-id="d4248-189">アプリケーション クエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4248-189">Create an app query</span></span>

<span data-ttu-id="d4248-190">詳細の表示は、次のようなを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d4248-190">We recommend using the Advanced view, which looks like this:</span></span> 

![詳細表示](media/OCAS-OAuthAppsAdvQueryView.png)

<span data-ttu-id="d4248-p111">アプリケーション クエリ ・ バーで**詳細設定**] を参照してください使用する場合、基本的なビューです。詳細ビューに移動するには、**詳細設定**のをクリックして (またはタップ) します。</span><span class="sxs-lookup"><span data-stu-id="d4248-p111">In the app query bar, if you see **Advanced**, you're using the Basic view. Click (or tap) **Advanced** to go to the Advanced view.</span></span> 

![基本ビュー](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. <span data-ttu-id="d4248-195">クエリ ・ バーでは、オプションを選択するのに**フィルターを選択**] ボックスの一覧を使用します。</span><span class="sxs-lookup"><span data-stu-id="d4248-195">In the query bar, use the **Select a filter** list to choose an option.</span></span> 
    - <span data-ttu-id="d4248-196">**アプリケーション**アプリケーションでは特定の名前</span><span class="sxs-lookup"><span data-stu-id="d4248-196">**App** Apps with certain names</span></span>
    - <span data-ttu-id="d4248-197">**アプリケーションの状態**状態 (承認済み、禁止、または不定) に基づくアプリケーション</span><span class="sxs-lookup"><span data-stu-id="d4248-197">**App state** Apps based on their state (Approved, Banned, or Undetermined)</span></span>
    - <span data-ttu-id="d4248-198">**コミュニティを使用して**コミュニティに基づくアプリケーションを使用して、レベル (Rare、Uncommon、または共通)</span><span class="sxs-lookup"><span data-stu-id="d4248-198">**Community use** Apps based on community use levels (Rare, Uncommon, or Common)</span></span>
    - <span data-ttu-id="d4248-199">**アクセス許可のレベル**特定のアクセス許可レベルに基づいてアプリケーション</span><span class="sxs-lookup"><span data-stu-id="d4248-199">**Permission level** Apps based on certain permission levels</span></span> 
    - <span data-ttu-id="d4248-200">**アクセス許可**特定のアクセス許可を必要とするアプリケーション</span><span class="sxs-lookup"><span data-stu-id="d4248-200">**Permissions** Apps that require certain permissions</span></span>
    - <span data-ttu-id="d4248-201">**発行元** 特定の発行元からのアプリ</span><span class="sxs-lookup"><span data-stu-id="d4248-201">**Publisher**  Apps from certain publishers</span></span>
    - <span data-ttu-id="d4248-202">**ユーザー**特定のユーザーが承認されているアプリケーション</span><span class="sxs-lookup"><span data-stu-id="d4248-202">**User** Apps that a certain user authorized</span></span>
   
2. <span data-ttu-id="d4248-203">**等しい**か**等しくない**がを選択し、[フィルターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4248-203">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
3. <span data-ttu-id="d4248-204">他のフィルターを追加するのには、プラス記号 (を選択します</span><span class="sxs-lookup"><span data-stu-id="d4248-204">To add more filters, select the plus sign (</span></span>![アプリケーションを照会するためのフィルター アイコンを追加します。](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="d4248-206">)、し、手順 2 と 3 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d4248-206">), and then repeat steps 2 and 3.</span></span>
    
4. <span data-ttu-id="d4248-207">フィルターを削除するのには、x (を選択します</span><span class="sxs-lookup"><span data-stu-id="d4248-207">To remove a filter, select the x (</span></span>![アプリケーションを照会するためのフィルター アイコンを削除します。](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="d4248-209">) フィルター名の横にします。</span><span class="sxs-lookup"><span data-stu-id="d4248-209">) next to a filter name.</span></span>
    
<span data-ttu-id="d4248-210">フィルターが自動的に適用し、アプリ一覧がそれに応じて更新します。</span><span class="sxs-lookup"><span data-stu-id="d4248-210">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="d4248-211">次の手順</span><span class="sxs-lookup"><span data-stu-id="d4248-211">Next steps</span></span>

- [<span data-ttu-id="d4248-212">確認し、アラート アクションを実行</span><span class="sxs-lookup"><span data-stu-id="d4248-212">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="d4248-213">お客様の[Web トラフィックのログ、および Office 365 のクラウド アプリケーションのセキュリティのデータ ソース](web-traffic-logs-and-data-sources-for-ocas.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="d4248-213">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="d4248-214">[Office 365 のクラウド アプリケーションのセキュリティの使用率のアクティビティ](utilization-activities-for-ocas.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="d4248-214">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

