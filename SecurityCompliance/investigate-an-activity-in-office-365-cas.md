---
title: Office 365 Cloud App Security のアクティビティの調査
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 15fa4545-28b4-4dd4-bf85-88e0926bd5fc
description: 'Office 365 のクラウド アプリケーションのセキュリティ、経由での検索について調査中の活動とアカウントで Office 365 環境内で起こってを確認できます。 '
ms.openlocfilehash: e463323cf28738e1d54fcdb65ed0d15290c79994
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603658"
---
# <a name="investigate-an-activity-in-office-365-cloud-app-security"></a><span data-ttu-id="846e9-103">Office 365 Cloud App Security のアクティビティの調査</span><span class="sxs-lookup"><span data-stu-id="846e9-103">Investigate an activity in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="846e9-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="846e9-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="846e9-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="846e9-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="846e9-106">配置 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="846e9-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="846e9-107">使用率。</span><span class="sxs-lookup"><span data-stu-id="846e9-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="846e9-108">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="846e9-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="846e9-109">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="846e9-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="846e9-110">展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="846e9-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="846e9-111">コースです!</span><span class="sxs-lookup"><span data-stu-id="846e9-111">You are here!</span></span>  <br/> [<span data-ttu-id="846e9-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="846e9-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="846e9-p101">Office 365 クラウド アプリケーションのセキュリティは、 [Office 365 は監査ログ](detailed-properties-in-the-office-365-audit-log.md)で動作します。グローバル管理者またはセキュリティ管理者は、Office 365 のクラウド アプリケーションのセキュリティとに、組織が Office 365 を使用する方法の潜在的な問題が解決されないアクティビティ ・ ログ ・ ページを使用できます。</span><span class="sxs-lookup"><span data-stu-id="846e9-p101">Office 365 Cloud App Security works with your [Office 365 audit log](detailed-properties-in-the-office-365-audit-log.md). With Office 365 Cloud App Security, as a global administrator or security administrator, you can use the Activity log page to see potential issues in how your organization is using Office 365.</span></span>
  
## <a name="how-to-get-to-the-activity-log-page"></a><span data-ttu-id="846e9-115">アクティビティ ログのページを表示する方法</span><span class="sxs-lookup"><span data-stu-id="846e9-115">How to get to the Activity log page</span></span>

1. <span data-ttu-id="846e9-116">クラウド アプリケーションのセキュリティ関連ポータルに移動 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="846e9-116">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="846e9-117">**調査**を選択して、画面の上部にナビゲーション ・ バーで\>**のアクティビティのログ**です。</span><span class="sxs-lookup"><span data-stu-id="846e9-117">In the navigation bar across the top of the screen, choose **Investigate** \> **Activity log**.</span></span><br/><span data-ttu-id="846e9-118">![O365 CA ポータルでは、調査を選択します。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span><span class="sxs-lookup"><span data-stu-id="846e9-118">![In the O365 CAS portal, choose Investigate.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span></span>
  
## <a name="review-and-investigate-activities"></a><span data-ttu-id="846e9-119">確認し、活動の調査</span><span class="sxs-lookup"><span data-stu-id="846e9-119">Review and investigate activities</span></span>

<span data-ttu-id="846e9-p102">アクティビティ ログ] ページでは、Office 365 を使用して、組織内で行われるさまざまな活動の一覧を表示できます。活動または特定のユーザーの特定の種類に焦点を画面の上部にフィルターを使用できます。たとえば、組織の Office 365 管理者アカウントのパスワードの変更に関する情報は次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="846e9-p102">On the Activity log page, you can see a list of various activities that are taking place within your organization using Office 365. You can use filters across the top of the screen to focus on a specific type of activity or a specific user. For example, the following image shows information about an organization's Office 365 admin account's password change:</span></span>
  
![調査の選択では、Office 365 のクラウド アプリケーションのセキュリティ、\>のアクティビティのログです。](media/5d54600c-59cd-4f33-b4f0-29b75c37baae.png)
  
<span data-ttu-id="846e9-p103">アクティビティ ・ ログ内の各項目を見ると、他の関連する活動項目を検索するのには 2 つの楕円をクリックできます。たとえば、同じ種類、同じ IP アドレスとは、同じ国/地域からの他のアクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="846e9-p103">As you look at each item in the Activity log, you can click the ellipses to find other related activities. For example, you can view other activities of the same type, from the same IP address, or from the same country/region.</span></span>
  
<span data-ttu-id="846e9-p104">すぎる、アクティビティの他の多くの種類に関する情報を表示できます。たとえば、ここではアクティビティをアクティビティ ・ ログを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="846e9-p104">You can view information about many other kinds of activities, too. For example, here are some of the activities you can view in the Activity log:</span></span>
  
- <span data-ttu-id="846e9-128">メンバーを追加またはグループから削除</span><span class="sxs-lookup"><span data-stu-id="846e9-128">Members added to or removed from groups</span></span>
    
- <span data-ttu-id="846e9-129">ユーザー ライセンスの変更</span><span class="sxs-lookup"><span data-stu-id="846e9-129">Changes in user licenses</span></span>
    
- <span data-ttu-id="846e9-130">ファイルまたはフォルダーの内部または外部の共有</span><span class="sxs-lookup"><span data-stu-id="846e9-130">Files or folders shared internally or externally</span></span>
    
- <span data-ttu-id="846e9-131">作成または削除されたサイトまたはサイト コレクション</span><span class="sxs-lookup"><span data-stu-id="846e9-131">Created or deleted sites or site collections</span></span>
    
- <span data-ttu-id="846e9-132">電子メールの転送ルール</span><span class="sxs-lookup"><span data-stu-id="846e9-132">Email forwarding rules</span></span>
    
<span data-ttu-id="846e9-133">途中と、Office 365 の組織内のユーザーの使用方法を習得するアクティビティのログ ページを発行する使用が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="846e9-133">Use the Activity log page to get acquainted with how people in your organization are using Office 365 and what issues they might be having along the way.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="846e9-134">次のステップ</span><span class="sxs-lookup"><span data-stu-id="846e9-134">Next steps</span></span>

- [<span data-ttu-id="846e9-135">Office 365 Cloud App Security の警告の確認と処理</span><span class="sxs-lookup"><span data-stu-id="846e9-135">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="846e9-136">[Office 365 のクラウド アプリケーションのセキュリティの使用率のアクティビティ](utilization-activities-for-ocas.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="846e9-136">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

