---
title: Office 365 Cloud App Security を有効にする
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ba919c73-d021-404d-9850-eec57e78678c
description: この記事では、office 365 cloud app security を有効にする方法について説明します。これは、cloud app security by Microsoft Azure で提供されています。
ms.openlocfilehash: 1227545b1e4d1521dc1820342f09aabdf16ec2c6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220367"
---
# <a name="turn-on-office-365-cloud-app-security"></a><span data-ttu-id="ee3a3-103">Office 365 Cloud App Security を有効にする</span><span class="sxs-lookup"><span data-stu-id="ee3a3-103">Turn on Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="ee3a3-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="ee3a3-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="ee3a3-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="ee3a3-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="ee3a3-106">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="ee3a3-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="ee3a3-107">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="ee3a3-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="ee3a3-108">評価の開始</span><span class="sxs-lookup"><span data-stu-id="ee3a3-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="ee3a3-109">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="ee3a3-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="ee3a3-110">ここでは、</span><span class="sxs-lookup"><span data-stu-id="ee3a3-110">You are here!</span></span>  <br/> [<span data-ttu-id="ee3a3-111">次の手順</span><span class="sxs-lookup"><span data-stu-id="ee3a3-111">Next step</span></span>](activity-policies-and-alerts.md) <br/> |[<span data-ttu-id="ee3a3-112">利用を開始する</span><span class="sxs-lookup"><span data-stu-id="ee3a3-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
  
## <a name="turn-on-office-365-cloud-app-security"></a><span data-ttu-id="ee3a3-113">Office 365 Cloud App Security を有効にする</span><span class="sxs-lookup"><span data-stu-id="ee3a3-113">Turn on Office 365 Cloud App Security</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee3a3-p101">次のタスクを実行するには、全体管理者またはセキュリティ管理者である必要があります。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。office 365 Cloud App Security を正しく動作させるには、office 365 環境の**監査ログを有効にする必要があり**ます。詳細については、「 [Office 365 監査ログ検索をオンまたはオフにする](turn-audit-log-search-on-or-off.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee3a3-p101">You must be a global administrator or security administrator to perform the following task. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md). In order for Office 365 Cloud App Security to work correct, **audit logging must be turned on** for your Office 365 environment. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> 
  
1. <span data-ttu-id="ee3a3-p102">グローバル管理者またはセキュリティ管理者とし[https://protection.office.com](https://security.microsoft.com)て、Office 365 の職場または学校アカウントを使用してサインインします。(これにより、セキュリティ&amp;コンプライアンスセンターに移動できます。)</span><span class="sxs-lookup"><span data-stu-id="ee3a3-p102">As a global administrator or security administrator, go to [https://protection.office.com](https://security.microsoft.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="ee3a3-120">[**アラート** \> ] **[advanced alerts の管理**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ee3a3-120">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="ee3a3-121">[ **Office 365 Cloud App Security を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ee3a3-121">Select **Turn on Office 365 Cloud App Security**.</span></span>
    
4. <span data-ttu-id="ee3a3-122">[ **Office 365 Cloud App Security に移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ee3a3-122">Choose **Go to Office 365 Cloud App Security**.</span></span><br/><span data-ttu-id="ee3a3-123">![セキュリティ&amp; /コンプライアンスセンターで、[高度な通知の管理] を選択して Office 365 Cloud App Security に移動します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="ee3a3-123">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br/><span data-ttu-id="ee3a3-124">これにより、Office 365 Cloud App Security ポータルに移動します。ここで、レポートを表示したり、ポリシーを作成または編集したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ee3a3-124">This takes you to the Office 365 Cloud App Security portal, where you can view reports and create or edit your policies.</span></span>

<span data-ttu-id="ee3a3-125">Office 365 cloud app security を有効にした後は、cloud app security ポータルにアクセス[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)して、サインインします。</span><span class="sxs-lookup"><span data-stu-id="ee3a3-125">After you have turned on Office 365 Cloud App Security, you can go to the Cloud App Security portal by visiting [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) and signing in.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ee3a3-p103">office 365 Cloud app security を有効にすると、office 365 のユーザーアカウントとユーザーアクティビティに関する監査情報が[Microsoft Cloud App security](https://aka.ms/whatiscas)に転送されます。これにより、Office 365 は高度な通知、フィルタリング、およびその他の機能を提供して、情報を取得し、疑わしいアクティビティに関するアクションを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ee3a3-p103">When you turn on Office 365 Cloud App Security, auditing information about your Office 365 user accounts and user activities is transferred to [Microsoft Cloud App Security](https://aka.ms/whatiscas). This allows Office 365 to provide advanced alerts, filtering, and other features so you can get information and take action about suspicious activities.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="ee3a3-128">次の手順</span><span class="sxs-lookup"><span data-stu-id="ee3a3-128">Next steps</span></span>

- [<span data-ttu-id="ee3a3-129">アクティビティポリシー</span><span class="sxs-lookup"><span data-stu-id="ee3a3-129">Activity policies</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="ee3a3-130">異常検出ポリシー</span><span class="sxs-lookup"><span data-stu-id="ee3a3-130">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="ee3a3-131">SIEM サーバーの統合</span><span class="sxs-lookup"><span data-stu-id="ee3a3-131">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="ee3a3-132">IP アドレスをグループ化して管理を簡素化する</span><span class="sxs-lookup"><span data-stu-id="ee3a3-132">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

