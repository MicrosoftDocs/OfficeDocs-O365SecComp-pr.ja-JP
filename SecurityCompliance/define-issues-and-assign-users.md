---
title: Office 365 Advanced eDiscovery で問題を定義しユーザーを割り当てる
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 48d37ee7-05bd-4cb8-9723-a8959ad23fbe
description: Office 365 Advanced eDiscovery でユーザーを割り当てたり、電子情報開示ケースの問題を削除したりするなど、案件を追加または編集する方法について説明します。
ms.openlocfilehash: b8ed024983c527246236b355c81ef226c98f404b
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218237"
---
# <a name="define-issues-and-assign-users-in-office-365-advanced-ediscovery"></a><span data-ttu-id="5c98e-103">Office 365 Advanced eDiscovery で問題を定義しユーザーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5c98e-103">Define issues and assign users in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="5c98e-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="5c98e-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="5c98e-p102">詳細な電子情報開示では、1つまたは複数の問題をケース内に定義できます。問題の定義により、さらにトピックの分類を行うことができます。新しいケースに接続する場合は、1つの既定の問題が提供されます。既定の問題名を編集して、ユーザーを懸案事項に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5c98e-p102">In Advanced eDiscovery, one or more issues can be defined within a case. Defining issues allows further categorization of topics. When connecting to a new case, a single default issue is provided. You can edit the default issue name and assign users to the issue.</span></span> 
  
## <a name="adding-or-editing-an-issue-and-assigning-users"></a><span data-ttu-id="5c98e-110">懸案事項の追加または編集とユーザーの割り当て</span><span class="sxs-lookup"><span data-stu-id="5c98e-110">Adding or editing an issue and assigning users</span></span>

1. <span data-ttu-id="5c98e-111">[**関連性\>の関連性の設定**] タブ\>で、[**問題**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c98e-111">In the **Relevance \> Relevance setup** tab \> select **Issues**.</span></span>
    
    ![関連性の設定の問題](media/dfd8f9ef-b167-4ed9-980e-00ae98a97169.png)
  
2. <span data-ttu-id="5c98e-p103">問題を追加するには、\* \* + \* \* アイコンをクリックします。[**懸案事項の追加**] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c98e-p103">To add an issue, click the \*\* + \*\* icon. The **Add issue** dialog is displayed.</span></span> 
    
    ![[関連性の設定] の追加問題](media/c8e94982-139a-472a-b85d-282f2d742046.png)
  
    <span data-ttu-id="5c98e-116">問題を編集するには、[**編集**] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c98e-116">To edit an issue, click the **Edit** icon.</span></span> 
    
3. <span data-ttu-id="5c98e-117">[**発行名**] で、ケースにわかりやすく、重要な名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5c98e-117">In **Issue name**, type a name that is descriptive and significant to the case.</span></span> 
    
4. <span data-ttu-id="5c98e-118">[**説明**] に、問題に関する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="5c98e-118">In **Description**, type information about the issue.</span></span>
    
5. <span data-ttu-id="5c98e-p104">[**同時トレーニングを有効**にする] チェックボックスをオンにして、このオプションを有効にします。この設定により、複数の校閲者が同時に同じ問題に対処できます (個別のサンプル)。</span><span class="sxs-lookup"><span data-stu-id="5c98e-p104">Select the **Enable concurrent training** check box to enable the option. This setting enables multiple reviewers to work on the same issue simultaneously (in separate samples).</span></span> 
    
6. <span data-ttu-id="5c98e-p105">[**発行するユーザーの割り当て**] の [**すべてのユーザー** ] の一覧で、懸案事項に割り当てるユーザーを選択し、右側にある矢印をクリックして、**選択した**ユーザーの一覧にユーザーを追加します。必要に応じて繰り返します。上記のウィンドウでは、"Admin" が選択されたユーザーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c98e-p105">In **Assign users to issue**, in the **All users** list, select a user to be assigned to the issue and then click the right-facing arrow to add the user to the **Selected users** list. Repeat as necessary. In the window shown above, "Admin" is shown as a selected user.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5c98e-124">問題へのユーザー割り当ては、関連性トレーニングサイクルの前後で変更できます。</span><span class="sxs-lookup"><span data-stu-id="5c98e-124">User assignment to issues can be modified before or after a Relevance training cycle.</span></span> 
  
7. <span data-ttu-id="5c98e-125">[**選択したユーザー**] で、選択したユーザーの名前の横にあるドロップダウンリストから、次のいずれかのサンプリングモードを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c98e-125">In **Selected users**, from the drop-down list next to the name of the selected user, select one of the following Sampling modes:</span></span> 
    
  - <span data-ttu-id="5c98e-p106">**On**: ファイルを表示し、タグを付けることができます。これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="5c98e-p106">**On**: The files can be viewed and tagged. This is the default setting.</span></span>
    
  - <span data-ttu-id="5c98e-128">**Idle**: ファイルは表示できます。タグ付けは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5c98e-128">**Idle**: The files can be viewed; tagged is optional.</span></span>
    
  - <span data-ttu-id="5c98e-129">**Off**: ファイルを表示またはタグ付けすることができません。</span><span class="sxs-lookup"><span data-stu-id="5c98e-129">**Off**: The files cannot be viewed or tagged.</span></span>
    
8. <span data-ttu-id="5c98e-130">懸案事項の追加が完了したら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c98e-130">When done adding issues, click **OK**.</span></span>
    
## <a name="deleting-issues"></a><span data-ttu-id="5c98e-131">問題の削除</span><span class="sxs-lookup"><span data-stu-id="5c98e-131">Deleting issues</span></span>

<span data-ttu-id="5c98e-132">問題が定義された直後に削除される (つまり、データベースから削除される) 場合があり、その問題に対して実際の作業が行われていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="5c98e-132">Issues may be deleted (meaning, removed from the database) only immediately after they were defined and no actual work has been done for that issue.</span></span> 
  
1. <span data-ttu-id="5c98e-133">[**関連性\>の関連性の設定**] タブで、[**問題**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c98e-133">In the **Relevance \> Relevance setup** tab, select **Issues**.</span></span>
    
2. <span data-ttu-id="5c98e-134">データベースから削除する問題を選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c98e-134">Select the issue to delete from the database, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="5c98e-p107">確認メッセージが表示されます。[**はい]** をクリックして確認します。</span><span class="sxs-lookup"><span data-stu-id="5c98e-p107">A confirmation message is displayed. Click **Yes** to confirm.</span></span> 
    
4. <span data-ttu-id="5c98e-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c98e-137">Click **OK**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5c98e-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c98e-138">See also</span></span>

[<span data-ttu-id="5c98e-139">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="5c98e-139">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="5c98e-140">インポートしたファイルを追加するためのロードの設定</span><span class="sxs-lookup"><span data-stu-id="5c98e-140">Setting up loads to add imported files</span></span>](set-up-loads-to-add-imported-files.md)
  
[<span data-ttu-id="5c98e-141">強調表示されたキーワードと詳細オプションの定義</span><span class="sxs-lookup"><span data-stu-id="5c98e-141">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

