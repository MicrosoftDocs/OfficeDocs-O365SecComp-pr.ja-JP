---
title: Office 365 Cloud App Security を有効にする
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ba919c73-d021-404d-9850-eec57e78678c
description: Office 365 高度なセキュリティの管理] で、Microsoft Azure クラウド アプリケーションのセキュリティでの電源をオンにする方法については、この資料を参照してください。
ms.openlocfilehash: 8964a0b413b0350188c7f61638d04032534e5374
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014789"
---
# <a name="turn-on-office-365-cloud-app-security"></a><span data-ttu-id="9d2c9-103">Office 365 Cloud App Security を有効にする</span><span class="sxs-lookup"><span data-stu-id="9d2c9-103">Turn on Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="9d2c9-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="9d2c9-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="9d2c9-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="9d2c9-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="9d2c9-106">配置 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="9d2c9-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="9d2c9-107">使用率。</span><span class="sxs-lookup"><span data-stu-id="9d2c9-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="9d2c9-108">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="9d2c9-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="9d2c9-109">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="9d2c9-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="9d2c9-110">コースです!</span><span class="sxs-lookup"><span data-stu-id="9d2c9-110">You are here!</span></span>  <br/> [<span data-ttu-id="9d2c9-111">次の手順</span><span class="sxs-lookup"><span data-stu-id="9d2c9-111">Next step</span></span>](activity-policies-and-alerts.md) <br/> |[<span data-ttu-id="9d2c9-112">使用します。</span><span class="sxs-lookup"><span data-stu-id="9d2c9-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
  
## <a name="turn-on-office-365-cloud-app-security"></a><span data-ttu-id="9d2c9-113">Office 365 Cloud App Security を有効にする</span><span class="sxs-lookup"><span data-stu-id="9d2c9-113">Turn on Office 365 Cloud App Security</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d2c9-p101">次のタスクを実行するには、グローバル ・ アドミニストレーターまたはセキュリティ管理者である必要があります。詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。Office 365 のクラウド アプリケーション セキュリティを使用するために修正、**監査ログを有効にする必要があります**が、Office 365 環境にします。詳細については、[オンまたはオフ、Office 365 を有効にする監査ログの検索](turn-audit-log-search-on-or-off.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d2c9-p101">You must be a global administrator or security administrator to perform the following task. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md). In order for Office 365 Cloud App Security to work correct, **audit logging must be turned on** for your Office 365 environment. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> 
  
1. <span data-ttu-id="9d2c9-p102">グローバル管理者またはセキュリティ管理者には、[https://protection.office.com](https://security.microsoft.com)し、職場、学校のアカウントを使用して Office 365 にサインインします。(これで、セキュリティには、&amp;コンプライアンス センター)。</span><span class="sxs-lookup"><span data-stu-id="9d2c9-p102">As a global administrator or security administrator, go to [https://protection.office.com](https://security.microsoft.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="9d2c9-120">**アラート**を参照して\>**詳細なアラートを管理**します。</span><span class="sxs-lookup"><span data-stu-id="9d2c9-120">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="9d2c9-121">**Office 365 のクラウド アプリケーションのセキュリティを有効にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d2c9-121">Select **Turn on Office 365 Cloud App Security**.</span></span>
    
4. <span data-ttu-id="9d2c9-122">**Office 365 のクラウド アプリケーションのセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d2c9-122">Choose **Go to Office 365 Cloud App Security**.</span></span><br/><span data-ttu-id="9d2c9-123">![セキュリティ&amp;コンプライアンス センターでは、Office 365 のクラウド アプリケーションのセキュリティに移動するのには高度な通知の管理を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="9d2c9-123">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br/><span data-ttu-id="9d2c9-124">Office 365 のクラウド アプリケーションのセキュリティのポータル、レポートを表示および作成またはポリシーの編集をするに移動します。</span><span class="sxs-lookup"><span data-stu-id="9d2c9-124">This takes you to the Office 365 Cloud App Security portal, where you can view reports and create or edit your policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9d2c9-p103">Office 365 のクラウド アプリケーションのセキュリティを有効にすると、Office 365 ユーザー アカウントおよびユーザー ・ アクティビティの監査については、[マイクロソフトのクラウド アプリケーションのセキュリティ](https://aka.ms/whatiscas)に転送されます。これにより、情報を取得し、不審なアクティビティのアクションを実行することができますので、高度なアラート、フィルター、およびその他の機能を提供する Office 365 です。</span><span class="sxs-lookup"><span data-stu-id="9d2c9-p103">When you turn on Office 365 Cloud App Security, auditing information about your Office 365 user accounts and user activities is transferred to [Microsoft Cloud App Security](https://aka.ms/whatiscas). This allows Office 365 to provide advanced alerts, filtering, and other features so you can get information and take action about suspicious activities.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="9d2c9-127">次の手順</span><span class="sxs-lookup"><span data-stu-id="9d2c9-127">Next steps</span></span>

- [<span data-ttu-id="9d2c9-128">活動ポリシー</span><span class="sxs-lookup"><span data-stu-id="9d2c9-128">Activity policies</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="9d2c9-129">異常検出のポリシー</span><span class="sxs-lookup"><span data-stu-id="9d2c9-129">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="9d2c9-130">SIEM サーバーを統合します。</span><span class="sxs-lookup"><span data-stu-id="9d2c9-130">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="9d2c9-131">管理を簡略化する IP アドレスをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="9d2c9-131">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

