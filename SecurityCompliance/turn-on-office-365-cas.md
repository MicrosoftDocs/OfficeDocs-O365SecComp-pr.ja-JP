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
ms.openlocfilehash: 057a7b3311384901b4c3683c350d1f26c91bf60d
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603778"
---
# <a name="turn-on-office-365-cloud-app-security"></a><span data-ttu-id="ea9cd-103">Office 365 Cloud App Security を有効にする</span><span class="sxs-lookup"><span data-stu-id="ea9cd-103">Turn on Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="ea9cd-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="ea9cd-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="ea9cd-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="ea9cd-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="ea9cd-106">配置 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="ea9cd-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="ea9cd-107">使用率。</span><span class="sxs-lookup"><span data-stu-id="ea9cd-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="ea9cd-108">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="ea9cd-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="ea9cd-109">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="ea9cd-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="ea9cd-110">コースです!</span><span class="sxs-lookup"><span data-stu-id="ea9cd-110">You are here!</span></span>  <br/> [<span data-ttu-id="ea9cd-111">次の手順</span><span class="sxs-lookup"><span data-stu-id="ea9cd-111">Next step</span></span>](activity-policies-and-alerts.md) <br/> |[<span data-ttu-id="ea9cd-112">使用します。</span><span class="sxs-lookup"><span data-stu-id="ea9cd-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
  
## <a name="turn-on-office-365-cloud-app-security"></a><span data-ttu-id="ea9cd-113">Office 365 Cloud App Security を有効にする</span><span class="sxs-lookup"><span data-stu-id="ea9cd-113">Turn on Office 365 Cloud App Security</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea9cd-p101">次のタスクを実行するには、グローバル ・ アドミニストレーターまたはセキュリティ管理者である必要があります。詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。Office 365 のクラウド アプリケーション セキュリティを使用するために修正、**監査ログを有効にする必要があります**が、Office 365 環境にします。詳細については、[オンまたはオフ、Office 365 を有効にする監査ログの検索](turn-audit-log-search-on-or-off.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea9cd-p101">You must be a global administrator or security administrator to perform the following task. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md). In order for Office 365 Cloud App Security to work correct, **audit logging must be turned on** for your Office 365 environment. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> 
  
1. <span data-ttu-id="ea9cd-p102">グローバル管理者またはセキュリティ管理者には、[https://protection.office.com](https://security.microsoft.com)し、職場、学校のアカウントを使用して Office 365 にサインインします。(これで、セキュリティには、&amp;コンプライアンス センター)。</span><span class="sxs-lookup"><span data-stu-id="ea9cd-p102">As a global administrator or security administrator, go to [https://protection.office.com](https://security.microsoft.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="ea9cd-120">**アラート**を参照して\>**詳細なアラートを管理**します。</span><span class="sxs-lookup"><span data-stu-id="ea9cd-120">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="ea9cd-121">**Office 365 のクラウド アプリケーションのセキュリティを有効にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea9cd-121">Select **Turn on Office 365 Cloud App Security**.</span></span>
    
4. <span data-ttu-id="ea9cd-122">**Office 365 のクラウド アプリケーションのセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea9cd-122">Choose **Go to Office 365 Cloud App Security**.</span></span><br/><span data-ttu-id="ea9cd-123">![セキュリティ&amp;コンプライアンス センターでは、Office 365 のクラウド アプリケーションのセキュリティに移動するのには高度な通知の管理を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="ea9cd-123">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br/><span data-ttu-id="ea9cd-124">Office 365 のクラウド アプリケーションのセキュリティのポータル、レポートを表示および作成またはポリシーの編集をするに移動します。</span><span class="sxs-lookup"><span data-stu-id="ea9cd-124">This takes you to the Office 365 Cloud App Security portal, where you can view reports and create or edit your policies.</span></span>

<span data-ttu-id="ea9cd-125">訪問でクラウド アプリケーションのセキュリティ関連ポータルに移動することができます Office 365 のクラウド アプリケーションのセキュリティをオンにした後、[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)署名します。</span><span class="sxs-lookup"><span data-stu-id="ea9cd-125">After you have turned on Office 365 Cloud App Security, you can go to the Cloud App Security portal by visiting [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) and signing in.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ea9cd-p103">Office 365 のクラウド アプリケーションのセキュリティを有効にすると、Office 365 ユーザー アカウントおよびユーザー ・ アクティビティの監査については、[マイクロソフトのクラウド アプリケーションのセキュリティ](https://aka.ms/whatiscas)に転送されます。これにより、情報を取得し、不審なアクティビティのアクションを実行することができますので、高度なアラート、フィルター、およびその他の機能を提供する Office 365 です。</span><span class="sxs-lookup"><span data-stu-id="ea9cd-p103">When you turn on Office 365 Cloud App Security, auditing information about your Office 365 user accounts and user activities is transferred to [Microsoft Cloud App Security](https://aka.ms/whatiscas). This allows Office 365 to provide advanced alerts, filtering, and other features so you can get information and take action about suspicious activities.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="ea9cd-128">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ea9cd-128">Next steps</span></span>

- [<span data-ttu-id="ea9cd-129">活動ポリシー</span><span class="sxs-lookup"><span data-stu-id="ea9cd-129">Activity policies</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="ea9cd-130">異常検出のポリシー</span><span class="sxs-lookup"><span data-stu-id="ea9cd-130">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="ea9cd-131">SIEM サーバーを統合します。</span><span class="sxs-lookup"><span data-stu-id="ea9cd-131">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="ea9cd-132">管理を簡略化する IP アドレスをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="ea9cd-132">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

