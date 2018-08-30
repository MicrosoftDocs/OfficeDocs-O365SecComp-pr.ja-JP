---
title: Office 365 Cloud App Security を使用してアプリのアクセス許可を管理する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: Office 365 のクラウド アプリケーションのセキュリティのアクセス許可をアプリケーションでは、ユーザーが Office 365 のデータを使用するためにダウンロードするアプリケーションを管理できます。
ms.openlocfilehash: 7bda35bbbf3a16cd1d386adcb03b1c7c4176913a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532540"
---
# <a name="manage-app-permissions-using-office-365-cloud-app-security"></a><span data-ttu-id="74d32-103">Office 365 Cloud App Security を使用してアプリのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="74d32-103">Manage app permissions using Office 365 Cloud App Security</span></span>

<span data-ttu-id="74d32-104">セキュリティ管理の高度な office 365 は、Office 365 のクラウド アプリケーションのセキュリティをされます。</span><span class="sxs-lookup"><span data-stu-id="74d32-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="74d32-105">評価 * *\>**</span><span class="sxs-lookup"><span data-stu-id="74d32-105">****Evaluation** \>**</span></span>|<span data-ttu-id="74d32-106">計画 * *\>**</span><span class="sxs-lookup"><span data-stu-id="74d32-106">****Planning** \>**</span></span>|<span data-ttu-id="74d32-107">配置 * *\>**</span><span class="sxs-lookup"><span data-stu-id="74d32-107">****Deployment** \>**</span></span>|<span data-ttu-id="74d32-108">使用率。</span><span class="sxs-lookup"><span data-stu-id="74d32-108">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="74d32-109">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="74d32-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="74d32-110">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="74d32-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="74d32-111">展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="74d32-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="74d32-112">コースです!</span><span class="sxs-lookup"><span data-stu-id="74d32-112">You are here!</span></span>  <br/> [<span data-ttu-id="74d32-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="74d32-113">Next steps</span></span>](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="74d32-p101">人のアプリが大好き、多くの場合ダウンロードする人は考慮してくださいアプリケーション特に職場の取得や学校の情報を簡単にすることで時間が短縮されます。ただし、組織にセキュリティ上のリスクの可能性があるいくつかのアプリケーション、に応じてどのような情報にアクセスして、その情報をどのように対処します。[Office 365 のクラウド アプリケーションのセキュリティ](office-365-cas-overview.md)の場合は、グローバル管理者またはセキュリティ管理者、管理できますアプリケーションのアクセス許可、組織の。アプリケーションのユーザーが使用しているを参照してください Office 365 のデータをどのようなアクセス許可アプリケーションがあるとします。</span><span class="sxs-lookup"><span data-stu-id="74d32-p101">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information. However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information. With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage app permissions for your organization. You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="74d32-118">この資料では、アプリケーションのアクセス許可を管理するための場所、承認、または、アプリケーションのアクセスを禁止する方法、およびアプリケーションのクエリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="74d32-118">This article describes where to go to manage app permissions, how to approve or ban an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-app-permissions-page"></a><span data-ttu-id="74d32-119">アプリケーションのアクセス許可の管理] ページを検索する方法</span><span class="sxs-lookup"><span data-stu-id="74d32-119">How to find the Manage app permissions page</span></span>
<span data-ttu-id="74d32-120"><a name="findappperms"> </a></span><span class="sxs-lookup"><span data-stu-id="74d32-120"></span></span>

> [!NOTE]
> <span data-ttu-id="74d32-p102">アプリケーションのアクセス許可は、Office 365 のクラウド アプリケーションのセキュリティ関連ポータルで管理されます。次のタスクを実行するには、グローバル ・ アドミニストレーターまたはセキュリティ管理者である必要があります。については多くを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="74d32-p102">App permissions are managed in the Office 365 Cloud App Security portal. You must be a global administrator or security administrator to perform the following task. To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="74d32-p103">[https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用して Office 365 にサインインします。(これで、セキュリティには、&amp;コンプライアンス センター)。</span><span class="sxs-lookup"><span data-stu-id="74d32-p103">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="74d32-126">**アラート**を参照して\>**詳細なアラートを管理**します。</span><span class="sxs-lookup"><span data-stu-id="74d32-126">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="74d32-127">をクリックして (またはタップ) **Office 365 のクラウド アプリケーションのセキュリティに移動**します。</span><span class="sxs-lookup"><span data-stu-id="74d32-127">Click (or tap) **Go to Office 365 Cloud App Security**.</span></span>
    
    ![セキュリティ&amp;コンプライアンス センターでは、Office 365 のクラウド アプリケーションのセキュリティに移動するのには高度な通知の管理を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    > [!NOTE]
    > <span data-ttu-id="74d32-p104">Office 365 のクラウド アプリケーションのセキュリティがまだオンにしない場合は、このページで行うことができます。[Office 365 のクラウド アプリケーションのセキュリティの準備](get-ready-for-office-365-cas.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74d32-p104">If Office 365 Cloud App Security is not turned on yet, you can do that on this page. See [Get ready for Office 365 Cloud App Security](get-ready-for-office-365-cas.md).</span></span> 
  
4. <span data-ttu-id="74d32-131">**調査**を選択して\>**アプリケーションのアクセスを許可**します。</span><span class="sxs-lookup"><span data-stu-id="74d32-131">Choose **Investigate** \> **App permissions**.</span></span>
    
    ![O365 CA ポータルでは、調査を選択します。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
## <a name="what-youll-see-on-the-manage-app-permissions-page"></a><span data-ttu-id="74d32-133">アプリケーションのアクセス許可の管理] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="74d32-133">What you'll see on the Manage app permissions page</span></span>
<span data-ttu-id="74d32-134"><a name="whatsonpage"> </a></span><span class="sxs-lookup"><span data-stu-id="74d32-134"></span></span>

<span data-ttu-id="74d32-135">次の表では、アプリケーションのアクセス許可の管理] ページでコントロールと使用可能なオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="74d32-135">The following table describes the controls and options available on the Manage app permissions page.</span></span>
  
|<span data-ttu-id="74d32-136">**アイテム**</span><span class="sxs-lookup"><span data-stu-id="74d32-136">**Item**</span></span>|<span data-ttu-id="74d32-137">**説明**</span><span class="sxs-lookup"><span data-stu-id="74d32-137">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="74d32-138">アプリケーション クエリのバーでの基本のアイコン</span><span class="sxs-lookup"><span data-stu-id="74d32-138">Basic icon in the app query bar</span></span>  <br/> ![アプリケーションのアクセス許可を照会するための基本的なクエリ ビューを示すアイコン](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="74d32-140">詳細表示に切り替えるにはこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="74d32-140">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="74d32-141">(**基本的な**表示される場合は、ビューを使用して高度です)</span><span class="sxs-lookup"><span data-stu-id="74d32-141">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="74d32-142">アプリケーション クエリ バーの [詳細設定のアイコン</span><span class="sxs-lookup"><span data-stu-id="74d32-142">Advanced icon in the app query bar</span></span>  <br/> ![アプリケーションのアクセス許可を照会するためのクエリ ビューの詳細を示すアイコン](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="74d32-144">基本的なビューに切り替えるにはこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="74d32-144">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="74d32-145">(**詳細設定**を表示する場合は、ビューを使用して基本。)</span><span class="sxs-lookup"><span data-stu-id="74d32-145">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="74d32-146">開いたり閉じたりするアプリケーションのリスト内のすべての詳細アイコン</span><span class="sxs-lookup"><span data-stu-id="74d32-146">Open or close all details icon in the app list</span></span>  <br/> ![すべてのアプリケーションのすべての詳細を開いたり、閉じたりするには、このアイコンをクリックします。](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="74d32-148">各アプリケーションについてのより多くのまたはより少ない詳細を表示するには、このアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="74d32-148">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="74d32-149">アプリケーションの一覧のアイコンをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="74d32-149">Export icon in the app list</span></span>  <br/> ![すべての csv ファイルをエクスポートするには、このアイコンをクリックします。](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="74d32-151">アプリケーション、各アプリケーション、アプリケーション、アクセス許可のレベル、アプリケーションの状態に関連付けられているアクセス許可のユーザー数の一覧を含む CSV ファイルにエクスポートするには、このアイコンを選択し、コミュニティは、レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="74d32-151">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="74d32-152">Name</span><span class="sxs-lookup"><span data-stu-id="74d32-152">Name</span></span>  <br/> |<span data-ttu-id="74d32-p105">これを使用して、アプリケーションの選択の名前を参照してください、名前、説明、発行元、アプリケーションの web サイトおよびアプリケーション ID などの詳細情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="74d32-p105">Use this to see the name of an app. Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="74d32-155">によって承認されています。</span><span class="sxs-lookup"><span data-stu-id="74d32-155">Authorized by</span></span>  <br/> |<span data-ttu-id="74d32-p106">ユーザーの Office 365 アカウントにアクセスするのにアプリケーションが承認されているユーザーの数を表示するのにには、これを使用します。ユーザー アカウントの一覧などの詳細情報を表示するのには番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="74d32-p106">Use this to see how many users have authorized an app to access their Office 365 account. Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="74d32-158">アクセス許可のレベル</span><span class="sxs-lookup"><span data-stu-id="74d32-158">Permissions Level</span></span>  <br/> ![アプリケーションの permisiions のレベルを示すアイコン](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="74d32-p107">これを使用して、アプリケーションがどの程度のアクセスが、Office 365 のデータを参照してください。アクセス許可レベルは、**低****中**、または**高****低**が、アプリケーションにアクセスするだけ、ユーザーのプロファイルと名前を示す可能性がありますを示します。アプリケーション、コミュニティ、および[ログの管理](suspend-or-restore-an-account-in-ocas.md)に関連する活動に与えられるアクセス許可などの詳細情報を表示するレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="74d32-p107">Use this to see how much access an app has to Office 365 data. Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name. Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).  </span></span><br/> |
|<span data-ttu-id="74d32-163">アプリケーションの状態 (**禁止**、**承認済み**、または**不定**)</span><span class="sxs-lookup"><span data-stu-id="74d32-163">App state ( **Banned**, **Approved**, or **Undetermined**)</span></span>  <br/> <span data-ttu-id="74d32-164">![許可、ブロックされているか、何もが管理者によって実行された後のアプリケーションのアクセス許可のアイコン](media/5748bd02-cd59-4bd1-a36f-d25a186e8055.png)</span><span class="sxs-lookup"><span data-stu-id="74d32-164">![App permissions icons after being allowed, blocked, or no action has been taken by an admin](media/5748bd02-cd59-4bd1-a36f-d25a186e8055.png)</span></span>|<span data-ttu-id="74d32-165">承認済み] または [禁止、としてアプリケーションをマークするのにはこれを使用して、または未決定の状態そのままです。</span><span class="sxs-lookup"><span data-stu-id="74d32-165">Use this to mark an app as Approved or Banned, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="74d32-166">アプリケーションを承認済みとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="74d32-166">Mark an app as approved</span></span>
<span data-ttu-id="74d32-167"><a name="approveapp"> </a></span><span class="sxs-lookup"><span data-stu-id="74d32-167"></span></span>

<span data-ttu-id="74d32-168">**アプリケーションのアクセス権の管理**] ページで、承認するアプリケーションを見つけて**としてマーク アプリケーションの承認**] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="74d32-168">On the **Manage app permissions** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![承認済みのアイコンとしてマーク アプリケーションを選択します。](media/dd1b7690-441a-48c9-9c3a-58466513c63d.png)
  
<span data-ttu-id="74d32-170">アイコンが緑色になると、およびすべての Office 365 ユーザーが承認されているアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="74d32-170">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74d32-p108">アプリを承認済みとしてマークすると、エンド ・ ユーザーへの影響はありません。承認されているアプリケーションを視覚的にマークは、まだ確認されていないアプリケーションからそれらを分離するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="74d32-p108">When you mark an app as approved, there is no effect on the end user. Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="74d32-173">アプリケーションの使用を禁止します。</span><span class="sxs-lookup"><span data-stu-id="74d32-173">Ban an app</span></span>
<span data-ttu-id="74d32-174"><a name="banapp"> </a></span><span class="sxs-lookup"><span data-stu-id="74d32-174"></span></span>

1. <span data-ttu-id="74d32-175">[**アプリケーションのアクセス権の管理**] ページで、アクセスを禁止するアプリケーションを見つけます、**マーク アプリケーションを禁止されている**アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="74d32-175">On the **Manage app permissions** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span> 
    
    ![禁止のアイコンとしてマーク アプリケーションを選択します。](media/b9b1c5f6-fde7-46d5-8589-1564d05702b3.png)
  
2. <span data-ttu-id="74d32-177">自社のアプリケーションが禁止されているユーザーを通知するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="74d32-177">Choose whether to let users know that their app has been banned.</span></span>
    
    <span data-ttu-id="74d32-178">(推奨)ユーザーを通知するには、]**この禁止されているアプリケーションへのアクセスを許可したユーザーに通知する**とを追加、またはカスタムの通知メッセージを編集します。</span><span class="sxs-lookup"><span data-stu-id="74d32-178">(Recommended) To let users know, select **Notify users who granted access to this banned app**, and add or edit a custom notification message.</span></span>
    
    <span data-ttu-id="74d32-179">ユーザーに通知されません、**この禁止されているアプリケーションへのアクセスを許可したユーザーに通知する**をオフにします。</span><span class="sxs-lookup"><span data-stu-id="74d32-179">To not let users know, clear **Notify users who granted access to this banned app**.</span></span>
    
    ![禁止されているアプリケーションのメール ・ テンプレート](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)
  
3. <span data-ttu-id="74d32-181">**禁止ユーザーのアプリケーション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="74d32-181">Choose **Ban app**.</span></span>
    
## <a name="create-an-app-query"></a><span data-ttu-id="74d32-182">アプリケーション クエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="74d32-182">Create an app query</span></span>
<span data-ttu-id="74d32-183"><a name="createapp"> </a></span><span class="sxs-lookup"><span data-stu-id="74d32-183"></span></span>

1. <span data-ttu-id="74d32-p109">アプリケーション クエリ ・ バーで**詳細設定**を表示する場合] をクリックして (またはタップ) 高度なビューに移動すること。(詳細の表示を使用している基本を表示する場合は、ですので、ビューを保持)。</span><span class="sxs-lookup"><span data-stu-id="74d32-p109">In the app query bar, if you see **Advanced**, click (or tap) it to go to the Advanced view. (If you see Basic, you are using the Advanced view; keep your view as it is.)</span></span>
    
2. <span data-ttu-id="74d32-p110">オプションを選択するのにには、**フィルターの選択**] ボックスの一覧を使用します。次の表は、利用可能なフィルター オプションをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="74d32-p110">Use the **Select a filter** list to choose an option. The following table summarizes your available filter options.</span></span> 
    
|<span data-ttu-id="74d32-188">**このフィルターを使用します。**</span><span class="sxs-lookup"><span data-stu-id="74d32-188">**Use this filter**</span></span>|<span data-ttu-id="74d32-189">**表示内容**</span><span class="sxs-lookup"><span data-stu-id="74d32-189">**To display**</span></span>|
|:-----|:-----|
|<span data-ttu-id="74d32-190">**App**</span><span class="sxs-lookup"><span data-stu-id="74d32-190">**App**</span></span> <br/> |<span data-ttu-id="74d32-191">アプリケーションでは特定の名前</span><span class="sxs-lookup"><span data-stu-id="74d32-191">Apps with certain names</span></span>  <br/> |
|<span data-ttu-id="74d32-192">**アプリケーションの状態**</span><span class="sxs-lookup"><span data-stu-id="74d32-192">**App state**</span></span> <br/> |<span data-ttu-id="74d32-193">状態 (承認済み、禁止、または不定) に基づくアプリケーション</span><span class="sxs-lookup"><span data-stu-id="74d32-193">Apps based on their state (Approved, Banned, or Undetermined)</span></span>  <br/> |
|<span data-ttu-id="74d32-194">**コミュニティの使用**</span><span class="sxs-lookup"><span data-stu-id="74d32-194">**Community use**</span></span> <br/> |<span data-ttu-id="74d32-195">コミュニティに基づくアプリケーションを使用して、レベル (Rare、Uncommon、または共通)</span><span class="sxs-lookup"><span data-stu-id="74d32-195">Apps based on community use levels (Rare, Uncommon, or Common)</span></span>  <br/> |
|<span data-ttu-id="74d32-196">**アクセス許可レベル**</span><span class="sxs-lookup"><span data-stu-id="74d32-196">**Permission level**</span></span> <br/> |<span data-ttu-id="74d32-197">特定のアクセス許可レベルに基づいてアプリケーション</span><span class="sxs-lookup"><span data-stu-id="74d32-197">Apps based on certain permission levels</span></span>  <br/> |
|<span data-ttu-id="74d32-198">**アクセス許可**</span><span class="sxs-lookup"><span data-stu-id="74d32-198">**Permissions**</span></span> <br/> |<span data-ttu-id="74d32-199">特定のアクセス許可を必要とするアプリケーション</span><span class="sxs-lookup"><span data-stu-id="74d32-199">Apps that require certain permissions</span></span>  <br/> |
|<span data-ttu-id="74d32-200">**発行元**</span><span class="sxs-lookup"><span data-stu-id="74d32-200">**Publisher**</span></span> <br/> |<span data-ttu-id="74d32-201">特定の発行元からのアプリ</span><span class="sxs-lookup"><span data-stu-id="74d32-201">Apps from certain publishers</span></span>  <br/> |
|<span data-ttu-id="74d32-202">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="74d32-202">**User**</span></span> <br/> |<span data-ttu-id="74d32-203">特定のユーザーが承認されているアプリケーション</span><span class="sxs-lookup"><span data-stu-id="74d32-203">Apps that a certain user authorized</span></span>  <br/> |
   
3. <span data-ttu-id="74d32-204">**等しい**か**等しくない**がを選択し、[フィルターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="74d32-204">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
4. <span data-ttu-id="74d32-205">他のフィルターを追加するのには、プラス記号 (を選択します</span><span class="sxs-lookup"><span data-stu-id="74d32-205">To add more filters, select the plus sign (</span></span>![アプリケーションを照会するためのフィルター アイコンを追加します。](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="74d32-207">)、し、手順 2 と 3 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="74d32-207">), and then repeat steps 2 and 3.</span></span>
    
5. <span data-ttu-id="74d32-208">フィルターを削除するのには、x (を選択します</span><span class="sxs-lookup"><span data-stu-id="74d32-208">To remove a filter, select the x (</span></span>![アプリケーションを照会するためのフィルター アイコンを削除します。](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="74d32-210">) フィルター名の横にします。</span><span class="sxs-lookup"><span data-stu-id="74d32-210">) next to a filter name.</span></span>
    
<span data-ttu-id="74d32-211">フィルターが自動的に適用し、アプリ一覧がそれに応じて更新します。</span><span class="sxs-lookup"><span data-stu-id="74d32-211">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="74d32-212">次の手順</span><span class="sxs-lookup"><span data-stu-id="74d32-212">Next steps</span></span>
<span data-ttu-id="74d32-213"><a name="nextsteps"> </a></span><span class="sxs-lookup"><span data-stu-id="74d32-213"></span></span>

- [<span data-ttu-id="74d32-214">確認し、アラート アクションを実行</span><span class="sxs-lookup"><span data-stu-id="74d32-214">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="74d32-215">お客様の[Web トラフィックのログ、および Office 365 のクラウド アプリケーションのセキュリティのデータ ソース](web-traffic-logs-and-data-sources-for-ocas.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="74d32-215">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="74d32-216">[Office 365 のクラウド アプリケーションのセキュリティの使用率のアクティビティ](utilization-activities-for-ocas.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="74d32-216">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

