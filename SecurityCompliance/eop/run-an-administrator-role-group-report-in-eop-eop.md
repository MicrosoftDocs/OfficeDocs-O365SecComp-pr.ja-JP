---
title: 'EOP で管理者役割グループ レポートを実行する '
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: 管理者は、Exchange Online Protection (EOP) で管理者の役割グループレポートを実行する方法について説明します。 このレポートは、管理者が管理者の役割グループに対してメンバーを追加または削除したときにログに記録されます。 Microsoft Exchange Online Protection (EOP) は、各発生回数をログに記録します。
ms.openlocfilehash: 6973574ca1eeabee85dd57bd087ba5d0675da084
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676512"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="53fca-104">EOP で管理者役割グループ レポートを実行する</span><span class="sxs-lookup"><span data-stu-id="53fca-104">Run an administrator role group report in EOP</span></span>

 <span data-ttu-id="53fca-105">管理者が管理者の役割グループにメンバーを追加または削除すると、Exchange Online Protection (EOP) によって、各発生がログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="53fca-105">When an admin adds members to or removes members from administrator role groups, Exchange Online Protection (EOP) logs each occurrence.</span></span> <span data-ttu-id="53fca-106">Exchange 管理センター (EAC) で管理者の役割グループレポートを実行すると、エントリが検索結果として表示され、影響を受ける役割グループ、役割グループのメンバーシップと日時、および作成されたメンバーシップの更新が含まれます。</span><span class="sxs-lookup"><span data-stu-id="53fca-106">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="53fca-107">このレポートを使用して、組織内のユーザーに割り当てられた管理アクセス許可の変更を監視します。</span><span class="sxs-lookup"><span data-stu-id="53fca-107">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="53fca-108">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="53fca-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="53fca-109">予想所要時間:2 分</span><span class="sxs-lookup"><span data-stu-id="53fca-109">Estimated time to complete: 2 minutes</span></span>

- <span data-ttu-id="53fca-110">Exchange 管理センターを開くには、「exchange [Online Protection の exchange 管理センター](../exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53fca-110">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="53fca-p103">「この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「レポート」セクション。</span><span class="sxs-lookup"><span data-stu-id="53fca-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="53fca-113">このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53fca-113">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="53fca-114">問題がある場合は、</span><span class="sxs-lookup"><span data-stu-id="53fca-114">Having problems?</span></span> <span data-ttu-id="53fca-115">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラムでヘルプを要求します。</span><span class="sxs-lookup"><span data-stu-id="53fca-115">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>
  
## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="53fca-116">EAC を使用して管理者役割グループ レポートを実行する</span><span class="sxs-lookup"><span data-stu-id="53fca-116">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="53fca-117">管理者の役割グループレポートを実行して、組織内の管理役割グループに対する変更を特定の時間枠で検索します。</span><span class="sxs-lookup"><span data-stu-id="53fca-117">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>
  
1. <span data-ttu-id="53fca-118">EAC で、 **[コンプライアンス管理]** \> **[監査]** に移動し、 **[管理者の役割グループ レポートの実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="53fca-118">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="53fca-p105">**[開始日]** と **[終了日]** を選択します。既定では、管理者役割グループに対する過去 2 週間の変更のレポート検索が実行されます。</span><span class="sxs-lookup"><span data-stu-id="53fca-p105">Choose the **Start date** and **End date**. By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

3. <span data-ttu-id="53fca-p106">特定の役割グループに対する変更を表示するには、 **[役割グループの選択]** をクリックします。後続のダイアログ ボックスで役割グループ (複数可) を選択し、 **[OK]** をクリックします。また、変更された役割グループをすべて検索するために、フィールドを空のままにしておくこともできます。</span><span class="sxs-lookup"><span data-stu-id="53fca-p106">To view the changes for a specific role group, click **Select role groups**. Select the role group (or groups) in the subsequent dialog box, and click **OK**. You can also leave the field blank to find all changed role groups.</span></span>

4. <span data-ttu-id="53fca-124">**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53fca-124">Click **Search**.</span></span>

<span data-ttu-id="53fca-p107">指定した条件を使用して変更を検索した場合は、結果が結果ウィンドウに表示されます。検索結果内で役割グループをクリックすると、変更内容が詳細ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="53fca-p107">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="53fca-127">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="53fca-127">How do you know this worked?</span></span>

<span data-ttu-id="53fca-p108">管理者の役割グループ レポートが正常に実行されると、日付の範囲内に変更された役割グループが検索結果ウィンドウに表示されます。検索結果がない場合、指定された日付の範囲内に役割グループの変更はなかったことを意味します。検索結果があるはずであれば、日付の範囲を変更してレポートを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="53fca-p108">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>
  
## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="53fca-131">役割グループのメンバーシップに対する変更の監視</span><span class="sxs-lookup"><span data-stu-id="53fca-131">Monitor changes to role group membership</span></span>

<span data-ttu-id="53fca-p109">役割グループのメンバーが追加または削除されると、詳細ウィンドウに表示される検索結果に、役割グループのメンバーシップが更新されたことが示され、現在のメンバーが一覧表示されます。検索結果には、どのユーザーが追加または削除されたかは明示されません。</span><span class="sxs-lookup"><span data-stu-id="53fca-p109">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>
  
<span data-ttu-id="53fca-p110">ユーザーが追加または削除されたかどうかを判断するには、レポート内の 2 つの異なるエントリを比較する必要があります。たとえば、 **HelpDesk** 役割グループの次のログ エントリを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="53fca-p110">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>
  
> <span data-ttu-id="53fca-136">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="53fca-136">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="53fca-137">管理者</span><span class="sxs-lookup"><span data-stu-id="53fca-137">Administrator</span></span> <br> <span data-ttu-id="53fca-138">Updated members: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="53fca-138">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="53fca-139">2/06/2018 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="53fca-139">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="53fca-140">管理者</span><span class="sxs-lookup"><span data-stu-id="53fca-140">Administrator</span></span> <br> <span data-ttu-id="53fca-141">Updated members: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="53fca-141">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="53fca-142">2/19/2018 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="53fca-142">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="53fca-143">管理者</span><span class="sxs-lookup"><span data-stu-id="53fca-143">Administrator</span></span> <br> <span data-ttu-id="53fca-144">Updated members: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="53fca-144">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="53fca-145">この例では、管理者ユーザー アカウントによって次の変更が加えられています。</span><span class="sxs-lookup"><span data-stu-id="53fca-145">In this example, the Administrator user account made the following changes:</span></span>
  
- <span data-ttu-id="53fca-146">2/06/2018 で、ユーザー tonip を追加しました。</span><span class="sxs-lookup"><span data-stu-id="53fca-146">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="53fca-147">2/19/2018 で、ユーザー pilarp がが削除されました。</span><span class="sxs-lookup"><span data-stu-id="53fca-147">On 2/19/2018, they removed the user pilarp.</span></span>
