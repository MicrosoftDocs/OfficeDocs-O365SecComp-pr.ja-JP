---
title: Office 365 Cloud App Security のアクティビティの調査
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 15fa4545-28b4-4dd4-bf85-88e0926bd5fc
description: 'office 365 Cloud App Security では、アクティビティとアカウントを調べて調査することで、office 365 環境で起こっていることを確認できます。 '
ms.openlocfilehash: 0cc3860d953b40b0b0c247af6fb2b157d1abb235
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254839"
---
# <a name="investigate-an-activity-in-office-365-cloud-app-security"></a><span data-ttu-id="c2d0f-103">Office 365 Cloud App Security のアクティビティの調査</span><span class="sxs-lookup"><span data-stu-id="c2d0f-103">Investigate an activity in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="c2d0f-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c2d0f-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="c2d0f-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c2d0f-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="c2d0f-106">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c2d0f-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="c2d0f-107">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="c2d0f-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="c2d0f-108">評価の開始</span><span class="sxs-lookup"><span data-stu-id="c2d0f-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="c2d0f-109">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="c2d0f-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="c2d0f-110">展開を開始する</span><span class="sxs-lookup"><span data-stu-id="c2d0f-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="c2d0f-111">ここでは、</span><span class="sxs-lookup"><span data-stu-id="c2d0f-111">You are here!</span></span>  <br/> [<span data-ttu-id="c2d0f-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="c2d0f-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="c2d0f-113">office 365 Cloud App Security は[office 365 監査ログ](detailed-properties-in-the-office-365-audit-log.md)と連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="c2d0f-113">Office 365 Cloud App Security works with your [Office 365 audit log](detailed-properties-in-the-office-365-audit-log.md).</span></span> <span data-ttu-id="c2d0f-114">office 365 Cloud App Security では、全体管理者またはセキュリティ管理者として、アクティビティログページを使用して、組織が Office 365 を使用する方法に関する潜在的な問題を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c2d0f-114">With Office 365 Cloud App Security, as a global administrator or security administrator, you can use the Activity log page to see potential issues in how your organization is using Office 365.</span></span>
  
## <a name="how-to-get-to-the-activity-log-page"></a><span data-ttu-id="c2d0f-115">アクティビティログページにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="c2d0f-115">How to get to the Activity log page</span></span>

1. <span data-ttu-id="c2d0f-116">Cloud App Security ポータル ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="c2d0f-116">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="c2d0f-117">画面上部のナビゲーションバーで、[**アクティビティログ**の**調査** \> ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d0f-117">In the navigation bar across the top of the screen, choose **Investigate** \> **Activity log**.</span></span><br/><span data-ttu-id="c2d0f-118">![O365 CAS ポータルで、[調査] を選択します。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span><span class="sxs-lookup"><span data-stu-id="c2d0f-118">![In the O365 CAS portal, choose Investigate.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span></span>
  
## <a name="review-and-investigate-activities"></a><span data-ttu-id="c2d0f-119">アクティビティの確認と調査</span><span class="sxs-lookup"><span data-stu-id="c2d0f-119">Review and investigate activities</span></span>

<span data-ttu-id="c2d0f-120">[アクティビティログ] ページには、Office 365 を使用して組織内で実行されているさまざまなアクティビティの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2d0f-120">On the Activity log page, you can see a list of various activities that are taking place within your organization using Office 365.</span></span> <span data-ttu-id="c2d0f-121">画面の上部でフィルターを使用して、特定の種類のアクティビティまたは特定のユーザーに焦点を当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c2d0f-121">You can use filters across the top of the screen to focus on a specific type of activity or a specific user.</span></span> <span data-ttu-id="c2d0f-122">たとえば、次の図は、組織の Office 365 管理者アカウントのパスワード変更に関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="c2d0f-122">For example, the following image shows information about an organization's Office 365 admin account's password change:</span></span>
  
![Office 365 Cloud App Security で、[アクティビティ\>ログの調査] を選択します。](media/5d54600c-59cd-4f33-b4f0-29b75c37baae.png)
  
<span data-ttu-id="c2d0f-124">アクティビティログの各アイテムを確認するときに、省略記号をクリックして、関連するその他のアクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c2d0f-124">As you look at each item in the Activity log, you can click the ellipses to find other related activities.</span></span> <span data-ttu-id="c2d0f-125">たとえば、同じ IP アドレスまたは同じ国/地域の同じ種類の他のアクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c2d0f-125">For example, you can view other activities of the same type, from the same IP address, or from the same country/region.</span></span>
  
<span data-ttu-id="c2d0f-126">その他のさまざまなアクティビティについての情報を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="c2d0f-126">You can view information about many other kinds of activities, too.</span></span> <span data-ttu-id="c2d0f-127">たとえば、アクティビティログに表示できるアクティビティのいくつかを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c2d0f-127">For example, here are some of the activities you can view in the Activity log:</span></span>
  
- <span data-ttu-id="c2d0f-128">グループに追加された、またはグループから削除されたメンバー</span><span class="sxs-lookup"><span data-stu-id="c2d0f-128">Members added to or removed from groups</span></span>
    
- <span data-ttu-id="c2d0f-129">ユーザーライセンスの変更</span><span class="sxs-lookup"><span data-stu-id="c2d0f-129">Changes in user licenses</span></span>
    
- <span data-ttu-id="c2d0f-130">内部または外部で共有しているファイルまたはフォルダー</span><span class="sxs-lookup"><span data-stu-id="c2d0f-130">Files or folders shared internally or externally</span></span>
    
- <span data-ttu-id="c2d0f-131">作成または削除されたサイトまたはサイトコレクション</span><span class="sxs-lookup"><span data-stu-id="c2d0f-131">Created or deleted sites or site collections</span></span>
    
- <span data-ttu-id="c2d0f-132">メール転送ルール</span><span class="sxs-lookup"><span data-stu-id="c2d0f-132">Email forwarding rules</span></span>
    
<span data-ttu-id="c2d0f-133">アクティビティログページを使用すると、組織内のユーザーが Office 365 をどのように使用しているか、また、どのような問題が発生しているかについて理解できます。</span><span class="sxs-lookup"><span data-stu-id="c2d0f-133">Use the Activity log page to get acquainted with how people in your organization are using Office 365 and what issues they might be having along the way.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="c2d0f-134">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c2d0f-134">Next steps</span></span>

- [<span data-ttu-id="c2d0f-135">Office 365 Cloud App Security の警告の確認と処理</span><span class="sxs-lookup"><span data-stu-id="c2d0f-135">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="c2d0f-136">[Office 365 Cloud App Security の使用率のアクティビティを](utilization-activities-for-ocas.md)確認する</span><span class="sxs-lookup"><span data-stu-id="c2d0f-136">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

