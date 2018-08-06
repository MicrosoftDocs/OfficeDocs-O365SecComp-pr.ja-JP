---
title: 'EOP の管理者の役割グループ レポートを実行します。 '
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: 管理者にメンバーを追加または各 Microsoft Exchange Online ・保護 (EOP) ログの管理者の役割グループからメンバーを削除します。
ms.openlocfilehash: 49311faa4ee54fafa1c05a2314ed2f9d74cbe5a5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027204"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="bd8de-103">EOP の管理者の役割グループ レポートを実行します。</span><span class="sxs-lookup"><span data-stu-id="bd8de-103">Run an administrator role group report in EOP</span></span> 

 <span data-ttu-id="bd8de-p101">管理者が管理者役割グループに対してメンバーを追加または削除すると、操作のたびに Microsoft Exchange Online Protection (EOP) がその情報をログに記録します。Exchange 管理センターで管理者役割グループ レポートを実行すると、検索結果としてエントリが表示されます。エントリには、影響を受ける役割グループ、誰がいつ役割グループのメンバーシップを変更したか、およびどのメンバーシップが更新されたかが含まれます。このレポートを使用して、組織内のユーザーに割り当てられた管理アクセス許可に対する変更を監視します。</span><span class="sxs-lookup"><span data-stu-id="bd8de-p101">When an administrator adds members to or removes members from administrator role groups, Microsoft Exchange Online Protection (EOP) logs each occurrence. When you run an administrator role group report in the Exchange admin center, entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made. Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bd8de-107">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="bd8de-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bd8de-108">予想所要時間:2 分</span><span class="sxs-lookup"><span data-stu-id="bd8de-108">Estimated time to complete: 2 minutes</span></span>
    
- <span data-ttu-id="bd8de-p102">「この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「レポート」セクション。</span><span class="sxs-lookup"><span data-stu-id="bd8de-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="bd8de-111">このトピックの手順で使用可能なキーボード ショートカットについては、「**Exchange 管理センターのキーボード ショートカット**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8de-111">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="bd8de-p103">問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="bd8de-p103">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="bd8de-115">EAC を使用して管理者役割グループ レポートを実行する</span><span class="sxs-lookup"><span data-stu-id="bd8de-115">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="bd8de-116">管理者役割グループ レポートを実行して、特定の期間に組織の管理役割グループに加えられた変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="bd8de-116">Run the administrator role group report to find the changes to management role groups in your organization within a particular timeframe.</span></span>
  
1. <span data-ttu-id="bd8de-117">EAC で、 **[コンプライアンス管理]** \> **[監査]** に移動し、 **[管理者の役割グループ レポートの実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd8de-117">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>
    
2. <span data-ttu-id="bd8de-p104">**[開始日]** と **[終了日]** を選択します。既定では、管理者役割グループに対する過去 2 週間の変更のレポート検索が実行されます。</span><span class="sxs-lookup"><span data-stu-id="bd8de-p104">Choose the **Start date** and **End date**. By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>
    
3. <span data-ttu-id="bd8de-p105">特定の役割グループに対する変更を表示するには、 **[役割グループの選択]** をクリックします。後続のダイアログ ボックスで役割グループ (複数可) を選択し、 **[OK]** をクリックします。また、変更された役割グループをすべて検索するために、フィールドを空のままにしておくこともできます。</span><span class="sxs-lookup"><span data-stu-id="bd8de-p105">To view the changes for a specific role group, click **Select role groups**. Select the role group (or groups) in the subsequent dialog box, and click **OK**. You can also leave the field blank to find all changed role groups.</span></span>
    
4. <span data-ttu-id="bd8de-123">**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd8de-123">Click **Search**.</span></span>
    
<span data-ttu-id="bd8de-p106">指定した条件を使用して変更を検索した場合は、結果が結果ウィンドウに表示されます。検索結果内で役割グループをクリックすると、変更内容が詳細ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd8de-p106">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="bd8de-126">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="bd8de-126">How do you know this worked?</span></span>

<span data-ttu-id="bd8de-p107">管理者の役割グループ レポートが正常に実行されると、日付の範囲内に変更された役割グループが検索結果ウィンドウに表示されます。検索結果がない場合、指定された日付の範囲内に役割グループの変更はなかったことを意味します。検索結果があるはずであれば、日付の範囲を変更してレポートを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="bd8de-p107">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>
  
## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="bd8de-130">役割グループのメンバーシップに対する変更の監視</span><span class="sxs-lookup"><span data-stu-id="bd8de-130">Monitor changes to role group membership</span></span>

<span data-ttu-id="bd8de-p108">役割グループのメンバーが追加または削除されると、詳細ウィンドウに表示される検索結果に、役割グループのメンバーシップが更新されたことが示され、現在のメンバーが一覧表示されます。検索結果には、どのユーザーが追加または削除されたかは明示されません。</span><span class="sxs-lookup"><span data-stu-id="bd8de-p108">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>
  
<span data-ttu-id="bd8de-p109">ユーザーが追加または削除されたかどうかを判断するには、レポート内の 2 つの異なるエントリを比較する必要があります。たとえば、 **HelpDesk** 役割グループの次のログ エントリを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="bd8de-p109">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span> 
  
 <span data-ttu-id="bd8de-135">**1/27/2013 4:43 PM**</span><span class="sxs-lookup"><span data-stu-id="bd8de-135">**1/27/2013 4:43 PM**</span></span>
  
 <span data-ttu-id="bd8de-136">**管理者**</span><span class="sxs-lookup"><span data-stu-id="bd8de-136">**Administrator**</span></span>
  
 <span data-ttu-id="bd8de-137">**Updated members: Administrator;annb,florencef;pilarp**</span><span class="sxs-lookup"><span data-stu-id="bd8de-137">**Updated members: Administrator;annb,florencef;pilarp**</span></span>
  
 <span data-ttu-id="bd8de-138">**2/06/2013 10:09 AM**</span><span class="sxs-lookup"><span data-stu-id="bd8de-138">**2/06/2013 10:09 AM**</span></span>
  
 <span data-ttu-id="bd8de-139">**管理者**</span><span class="sxs-lookup"><span data-stu-id="bd8de-139">**Administrator**</span></span>
  
 <span data-ttu-id="bd8de-140">**Updated members: Administrator;annb;florencef;pilarp;tonip**</span><span class="sxs-lookup"><span data-stu-id="bd8de-140">**Updated members: Administrator;annb;florencef;pilarp;tonip**</span></span>
  
 <span data-ttu-id="bd8de-141">**2/19/2013 2:12 PM**</span><span class="sxs-lookup"><span data-stu-id="bd8de-141">**2/19/2013 2:12 PM**</span></span>
  
 <span data-ttu-id="bd8de-142">**管理者**</span><span class="sxs-lookup"><span data-stu-id="bd8de-142">**Administrator**</span></span>
  
 <span data-ttu-id="bd8de-143">**Updated members: Administrator;annb;florencef;tonip**</span><span class="sxs-lookup"><span data-stu-id="bd8de-143">**Updated members: Administrator;annb;florencef;tonip**</span></span>
  
<span data-ttu-id="bd8de-144">この例では、管理者ユーザー アカウントによって次の変更が加えられています。</span><span class="sxs-lookup"><span data-stu-id="bd8de-144">In this example, the Administrator user account made the following changes:</span></span>
  
- <span data-ttu-id="bd8de-145">2013 年 2 月 6 日に、ユーザー tonip が追加されました。</span><span class="sxs-lookup"><span data-stu-id="bd8de-145">On 2/06/2013, it added the user tonip.</span></span>
    
- <span data-ttu-id="bd8de-146">2013 年 2 月 19 日に、ユーザー pilarp が削除されました。</span><span class="sxs-lookup"><span data-stu-id="bd8de-146">On 2/19/2013, it removed the user pilarp.</span></span>
    

