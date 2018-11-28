---
title: Office 365 Cloud App Security のアクティビティの調査
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 15fa4545-28b4-4dd4-bf85-88e0926bd5fc
description: 'Office 365 のクラウド アプリケーションのセキュリティ、経由での検索について調査中の活動とアカウントで Office 365 環境内で起こってを確認できます。 '
ms.openlocfilehash: 6b5aca33a73fbfaecf8133368a33956ddc92da7a
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706461"
---
# <a name="investigate-an-activity-in-office-365-cloud-app-security"></a><span data-ttu-id="0db07-103">Office 365 Cloud App Security のアクティビティの調査</span><span class="sxs-lookup"><span data-stu-id="0db07-103">Investigate an activity in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="0db07-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0db07-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="0db07-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0db07-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="0db07-106">配置 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0db07-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="0db07-107">使用率。</span><span class="sxs-lookup"><span data-stu-id="0db07-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="0db07-108">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="0db07-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="0db07-109">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="0db07-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="0db07-110">展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="0db07-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="0db07-111">コースです!</span><span class="sxs-lookup"><span data-stu-id="0db07-111">You are here!</span></span>  <br/> [<span data-ttu-id="0db07-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="0db07-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="0db07-p101">Office 365 クラウド アプリケーションのセキュリティは、 [Office 365 は監査ログ](detailed-properties-in-the-office-365-audit-log.md)で動作します。グローバル管理者またはセキュリティ管理者は、Office 365 のクラウド アプリケーションのセキュリティとに、組織が Office 365 を使用する方法の潜在的な問題が解決されないアクティビティ ・ ログ ・ ページを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0db07-p101">Office 365 Cloud App Security works with your [Office 365 audit log](detailed-properties-in-the-office-365-audit-log.md). With Office 365 Cloud App Security, as a global administrator or security administrator, you can use the Activity log page to see potential issues in how your organization is using Office 365.</span></span>
  
## <a name="how-to-get-to-the-activity-log-page"></a><span data-ttu-id="0db07-115">アクティビティ ログのページを表示する方法</span><span class="sxs-lookup"><span data-stu-id="0db07-115">How to get to the Activity log page</span></span>

1. <span data-ttu-id="0db07-p102">グローバル管理者またはセキュリティ管理者に移動します。[https://security.microsoft.com](https://security.microsoft.com)し、職場、学校のアカウントを使用してサインインします。(を参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md).)</span><span class="sxs-lookup"><span data-stu-id="0db07-p102">As a global administrator or security administrator, go to [https://security.microsoft.com](https://security.microsoft.com) and sign in using your work or school account. (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>
    
2. <span data-ttu-id="0db07-118">セキュリティで&amp;コンプライアンス センターでは、**アラート**を選択して\>**管理警告の詳細**です。</span><span class="sxs-lookup"><span data-stu-id="0db07-118">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="0db07-119">**Office 365 のクラウド アプリケーションのセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0db07-119">Choose **Go to Office 365 Cloud App Security**.</span></span><br/><span data-ttu-id="0db07-120">![セキュリティ&amp;コンプライアンス センターでは、Office 365 のクラウド アプリケーションのセキュリティに移動するのには高度な通知の管理を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="0db07-120">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span>
  
4. <span data-ttu-id="0db07-121">**調査**を選択して、画面の上部にナビゲーション ・ バーで\>**のアクティビティのログ**です。</span><span class="sxs-lookup"><span data-stu-id="0db07-121">In the navigation bar across the top of the screen, choose **Investigate** \> **Activity log**.</span></span><br/><span data-ttu-id="0db07-122">![O365 CA ポータルでは、調査を選択します。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span><span class="sxs-lookup"><span data-stu-id="0db07-122">![In the O365 CAS portal, choose Investigate.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span></span>
  
## <a name="review-and-investigate-activities"></a><span data-ttu-id="0db07-123">確認し、活動の調査</span><span class="sxs-lookup"><span data-stu-id="0db07-123">Review and investigate activities</span></span>

<span data-ttu-id="0db07-p103">アクティビティ ログ] ページでは、Office 365 を使用して、組織内で行われるさまざまな活動の一覧を表示できます。活動または特定のユーザーの特定の種類に焦点を画面の上部にフィルターを使用できます。たとえば、組織の Office 365 管理者アカウントのパスワードの変更に関する情報は次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="0db07-p103">On the Activity log page, you can see a list of various activities that are taking place within your organization using Office 365. You can use filters across the top of the screen to focus on a specific type of activity or a specific user. For example, the following image shows information about an organization's Office 365 admin account's password change:</span></span>
  
![調査の選択では、Office 365 のクラウド アプリケーションのセキュリティ、\>のアクティビティのログです。](media/5d54600c-59cd-4f33-b4f0-29b75c37baae.png)
  
<span data-ttu-id="0db07-p104">アクティビティ ・ ログ内の各項目を見ると、他の関連する活動項目を検索するのには 2 つの楕円をクリックできます。たとえば、同じ種類、同じ IP アドレスとは、同じ国/地域からの他のアクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="0db07-p104">As you look at each item in the Activity log, you can click the ellipses to find other related activities. For example, you can view other activities of the same type, from the same IP address, or from the same country/region.</span></span>
  
<span data-ttu-id="0db07-p105">すぎる、アクティビティの他の多くの種類に関する情報を表示できます。たとえば、ここではアクティビティをアクティビティ ・ ログを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="0db07-p105">You can view information about many other kinds of activities, too. For example, here are some of the activities you can view in the Activity log:</span></span>
  
- <span data-ttu-id="0db07-132">メンバーを追加またはグループから削除</span><span class="sxs-lookup"><span data-stu-id="0db07-132">Members added to or removed from groups</span></span>
    
- <span data-ttu-id="0db07-133">ユーザー ライセンスの変更</span><span class="sxs-lookup"><span data-stu-id="0db07-133">Changes in user licenses</span></span>
    
- <span data-ttu-id="0db07-134">ファイルまたはフォルダーの内部または外部の共有</span><span class="sxs-lookup"><span data-stu-id="0db07-134">Files or folders shared internally or externally</span></span>
    
- <span data-ttu-id="0db07-135">作成または削除されたサイトまたはサイト コレクション</span><span class="sxs-lookup"><span data-stu-id="0db07-135">Created or deleted sites or site collections</span></span>
    
- <span data-ttu-id="0db07-136">電子メールの転送ルール</span><span class="sxs-lookup"><span data-stu-id="0db07-136">Email forwarding rules</span></span>
    
<span data-ttu-id="0db07-137">途中と、Office 365 の組織内のユーザーの使用方法を習得するアクティビティのログ ページを発行する使用が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0db07-137">Use the Activity log page to get acquainted with how people in your organization are using Office 365 and what issues they might be having along the way.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="0db07-138">次の手順</span><span class="sxs-lookup"><span data-stu-id="0db07-138">Next steps</span></span>

- [<span data-ttu-id="0db07-139">Office 365 Cloud App Security の警告の確認と処理</span><span class="sxs-lookup"><span data-stu-id="0db07-139">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="0db07-140">[Office 365 のクラウド アプリケーションのセキュリティの使用率のアクティビティ](utilization-activities-for-ocas.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="0db07-140">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

