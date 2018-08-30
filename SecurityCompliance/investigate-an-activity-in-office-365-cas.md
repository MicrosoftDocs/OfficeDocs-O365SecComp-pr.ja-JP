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
ms.openlocfilehash: 03db572ebddbdf27371f8e6fd2f0cdd91c14a12f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531739"
---
# <a name="investigate-an-activity-in-office-365-cloud-app-security"></a><span data-ttu-id="8a143-103">Office 365 Cloud App Security のアクティビティの調査</span><span class="sxs-lookup"><span data-stu-id="8a143-103">Investigate an activity in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="8a143-104">評価 * *\>**</span><span class="sxs-lookup"><span data-stu-id="8a143-104">****Evaluation** \>**</span></span>|<span data-ttu-id="8a143-105">計画 * *\>**</span><span class="sxs-lookup"><span data-stu-id="8a143-105">****Planning** \>**</span></span>|<span data-ttu-id="8a143-106">配置 * *\>**</span><span class="sxs-lookup"><span data-stu-id="8a143-106">****Deployment** \>**</span></span>|<span data-ttu-id="8a143-107">使用率。</span><span class="sxs-lookup"><span data-stu-id="8a143-107">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="8a143-108">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="8a143-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="8a143-109">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="8a143-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="8a143-110">展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="8a143-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="8a143-111">コースです!</span><span class="sxs-lookup"><span data-stu-id="8a143-111">You are here!</span></span>  <br/> [<span data-ttu-id="8a143-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="8a143-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="8a143-p101">Office 365 クラウド アプリケーションのセキュリティは、 [Office 365 は監査ログ](detailed-properties-in-the-office-365-audit-log.md)で動作します。グローバル管理者またはセキュリティ管理者は、Office 365 のクラウド アプリケーションのセキュリティとに、組織が Office 365 を使用する方法の潜在的な問題が解決されないアクティビティ ・ ログ ・ ページを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a143-p101">Office 365 Cloud App Security works with your [Office 365 audit log](detailed-properties-in-the-office-365-audit-log.md). With Office 365 Cloud App Security, as a global administrator or security administrator, you can use the Activity log page to see potential issues in how your organization is using Office 365.</span></span>
  
## <a name="how-to-get-to-the-activity-log-page"></a><span data-ttu-id="8a143-115">アクティビティ ログのページを表示する方法</span><span class="sxs-lookup"><span data-stu-id="8a143-115">How to get to the Activity log page</span></span>

1. <span data-ttu-id="8a143-p102">グローバル管理者またはセキュリティ管理者に移動します。[https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用してサインインします。(を参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md).)</span><span class="sxs-lookup"><span data-stu-id="8a143-p102">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>
    
2. <span data-ttu-id="8a143-118">セキュリティで&amp;コンプライアンス センターでは、**アラート**を選択して\>**管理警告の詳細**です。</span><span class="sxs-lookup"><span data-stu-id="8a143-118">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="8a143-119">**Office 365 のクラウド アプリケーションのセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a143-119">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    ![セキュリティ&amp;コンプライアンス センターでは、Office 365 のクラウド アプリケーションのセキュリティに移動するのには高度な通知の管理を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. <span data-ttu-id="8a143-121">**調査**を選択して、画面の上部にナビゲーション ・ バーで\>**のアクティビティのログ**です。</span><span class="sxs-lookup"><span data-stu-id="8a143-121">In the navigation bar across the top of the screen, choose **Investigate** \> **Activity log**.</span></span>
    
    ![O365 CA ポータルでは、調査を選択します。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
## <a name="review-and-investigate-activities"></a><span data-ttu-id="8a143-123">確認し、活動の調査</span><span class="sxs-lookup"><span data-stu-id="8a143-123">Review and investigate activities</span></span>

<span data-ttu-id="8a143-p103">アクティビティ ログ] ページでは、Office 365 を使用して、組織内で行われるさまざまな活動の一覧を表示できます。活動または特定のユーザーの特定の種類に焦点を画面の上部にフィルターを使用できます。たとえば、組織の Office 365 管理者アカウントのパスワードの変更に関する情報は次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="8a143-p103">On the Activity log page, you can see a list of various activities that are taking place within your organization using Office 365. You can use filters across the top of the screen to focus on a specific type of activity or a specific user. For example, the following image shows information about an organization's Office 365 admin account's password change:</span></span>
  
![調査の選択では、Office 365 のクラウド アプリケーションのセキュリティ、\>のアクティビティのログです。](media/5d54600c-59cd-4f33-b4f0-29b75c37baae.png)
  
<span data-ttu-id="8a143-p104">アクティビティ ・ ログ内の各項目を見ると、他の関連する活動項目を検索するのには 2 つの楕円をクリックできます。たとえば、同じ種類、同じ IP アドレスとは、同じ国/地域からの他のアクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="8a143-p104">As you look at each item in the Activity log, you can click the ellipses to find other related activities. For example, you can view other activities of the same type, from the same IP address, or from the same country/region.</span></span>
  
<span data-ttu-id="8a143-p105">すぎる、アクティビティの他の多くの種類に関する情報を表示できます。たとえば、ここではアクティビティをアクティビティ ・ ログを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="8a143-p105">You can view information about many other kinds of activities, too. For example, here are some of the activities you can view in the Activity log:</span></span>
  
- <span data-ttu-id="8a143-132">メンバーを追加またはグループから削除</span><span class="sxs-lookup"><span data-stu-id="8a143-132">Members added to or removed from groups</span></span>
    
- <span data-ttu-id="8a143-133">ユーザー ライセンスの変更</span><span class="sxs-lookup"><span data-stu-id="8a143-133">Changes in user licenses</span></span>
    
- <span data-ttu-id="8a143-134">ファイルまたはフォルダーの内部または外部の共有</span><span class="sxs-lookup"><span data-stu-id="8a143-134">Files or folders shared internally or externally</span></span>
    
- <span data-ttu-id="8a143-135">作成または削除されたサイトまたはサイト コレクション</span><span class="sxs-lookup"><span data-stu-id="8a143-135">Created or deleted sites or site collections</span></span>
    
- <span data-ttu-id="8a143-136">電子メールの転送ルール</span><span class="sxs-lookup"><span data-stu-id="8a143-136">Email forwarding rules</span></span>
    
<span data-ttu-id="8a143-137">途中と、Office 365 の組織内のユーザーの使用方法を習得するアクティビティのログ ページを発行する使用が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a143-137">Use the Activity log page to get acquainted with how people in your organization are using Office 365 and what issues they might be having along the way.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="8a143-138">次の手順</span><span class="sxs-lookup"><span data-stu-id="8a143-138">Next steps</span></span>

- [<span data-ttu-id="8a143-139">Office 365 Cloud App Security の警告の確認と処理</span><span class="sxs-lookup"><span data-stu-id="8a143-139">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="8a143-140">[Office 365 のクラウド アプリケーションのセキュリティの使用率のアクティビティ](utilization-activities-for-ocas.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="8a143-140">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

