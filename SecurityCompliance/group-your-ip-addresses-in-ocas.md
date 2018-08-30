---
title: IP アドレスをグループ化して Office 365 Cloud App Security の管理を簡素化する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: など、物理的なオフィスの IP アドレスでは、Office 365 のクラウド アプリケーションのセキュリティ、使用する IP アドレスのセットを簡単に識別するには、IP アドレスの範囲のグループを設定できます。
ms.openlocfilehash: 76cb9625a46d1f5eceaab696de5dcbb72f4d2b47
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531570"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a><span data-ttu-id="a4b86-103">IP アドレスをグループ化して Office 365 Cloud App Security の管理を簡素化する</span><span class="sxs-lookup"><span data-stu-id="a4b86-103">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="a4b86-104">評価 * *\>**</span><span class="sxs-lookup"><span data-stu-id="a4b86-104">****Evaluation** \>**</span></span>|<span data-ttu-id="a4b86-105">計画 * *\>**</span><span class="sxs-lookup"><span data-stu-id="a4b86-105">****Planning** \>**</span></span>|<span data-ttu-id="a4b86-106">配置 * *\>**</span><span class="sxs-lookup"><span data-stu-id="a4b86-106">****Deployment** \>**</span></span>|<span data-ttu-id="a4b86-107">使用率。</span><span class="sxs-lookup"><span data-stu-id="a4b86-107">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="a4b86-108">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="a4b86-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="a4b86-109">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="a4b86-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="a4b86-110">コースです!</span><span class="sxs-lookup"><span data-stu-id="a4b86-110">You are here!</span></span>  <br/> [<span data-ttu-id="a4b86-111">次の手順</span><span class="sxs-lookup"><span data-stu-id="a4b86-111">Next steps</span></span>](#next-steps) <br/> |[<span data-ttu-id="a4b86-112">使用します。</span><span class="sxs-lookup"><span data-stu-id="a4b86-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="a4b86-p101">など、物理的なオフィスの IP アドレスでは、Office 365 のクラウド アプリケーションのセキュリティ、使用する IP アドレスのセットを簡単に識別するには、IP アドレスの範囲のグループを設定できます。これらの範囲の使用を定義するタグ付けして分類したり、タグを使用することができますしと、アクティビティのログし、警告をカスタマイズするのにはカテゴリが表示され、調査します。</span><span class="sxs-lookup"><span data-stu-id="a4b86-p101">To easily identify sets of IP addresses that you'll use in Office 365 Cloud App Security, such as your physical office IP addresses, you can set up groups of IP address ranges. Defining these ranges lets you tag and categorize them, and then you can use tags and categories to customize how your activity logs and alerts are displayed and investigated.</span></span>
  
<span data-ttu-id="a4b86-p102">IP の範囲の各グループ タグを設定するを選択して、IP のカテゴリ (企業、管理、Risky、VPN など) の既定のリストに基づいたタグを分類できますし、タグ名です。IPv4 と IPv6 アドレスの両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a4b86-p102">Each group of IP ranges can be tagged with tag names that you choose, and then the tags can be categorized based on a default list of IP categories (such as Corporate, Administrative, Risky, and VPN). Both IPv4 and IPv6 addresses are supported.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4b86-p103">この資料の手順を実行するには、グローバル ・ アドミニストレーターまたはセキュリティ管理者である必要があります。詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="a4b86-p103">You must be a global administrator or security administrator to perform the procedures in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a><span data-ttu-id="a4b86-119">Office 365 のクラウド アプリケーションのセキュリティでは、IP アドレスの範囲を設定するには</span><span class="sxs-lookup"><span data-stu-id="a4b86-119">To set up an IP address range in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="a4b86-p104">グローバル管理者またはセキュリティ管理者に移動します。[https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用してサインインします。(これで、セキュリティには、&amp;コンプライアンス センター)。</span><span class="sxs-lookup"><span data-stu-id="a4b86-p104">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="a4b86-122">セキュリティで&amp;コンプライアンス センターでは、**アラート**を選択して\>**管理警告の詳細**です。</span><span class="sxs-lookup"><span data-stu-id="a4b86-122">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="a4b86-123">**Office 365 のクラウド アプリケーションのセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4b86-123">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    ![セキュリティ&amp;コンプライアンス センターでは、Office 365 のクラウド アプリケーションのセキュリティに移動するのには高度な通知の管理を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. <span data-ttu-id="a4b86-125">ページの右上、上の [**設定**] をクリックします\> **IP アドレスの範囲**です。</span><span class="sxs-lookup"><span data-stu-id="a4b86-125">On the upper right of the page, click **Settings** \> **IP address ranges**.</span></span>
    
    ![O365 クラウド アプリケーションのセキュリティでは、システムおよびデータの設定にアクセスするための設定を選択します](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)
  
5. <span data-ttu-id="a4b86-127">プラス記号のような新しい] ボタンをクリックして ( **+**)。</span><span class="sxs-lookup"><span data-stu-id="a4b86-127">Click the new button, which resembles a plus sign ( **+**).</span></span>
    
6. <span data-ttu-id="a4b86-128">ウィンドウで、**新しい IP アドレスの範囲**は、次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4b86-128">In the **New IP address range** window, specify the following values:</span></span> 
    
|<span data-ttu-id="a4b86-129">**フィールドまたはリスト**</span><span class="sxs-lookup"><span data-stu-id="a4b86-129">**Field or list**</span></span>|<span data-ttu-id="a4b86-130">**行うこと**</span><span class="sxs-lookup"><span data-stu-id="a4b86-130">**What to do**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a4b86-131">**名前**</span><span class="sxs-lookup"><span data-stu-id="a4b86-131">**Name**</span></span> <br/> |<span data-ttu-id="a4b86-p105">IP アドレスの範囲と設定を管理するのにには、このフィールドを使用します。(アクティビティ ログには、この値は表示されません)。</span><span class="sxs-lookup"><span data-stu-id="a4b86-p105">Use this field to manage your IP address range and settings. (You won't see this value in activities logs.)</span></span>  <br/> |
|<span data-ttu-id="a4b86-134">**IP アドレスの範囲**</span><span class="sxs-lookup"><span data-stu-id="a4b86-134">**IP address ranges**</span></span> <br/> |<span data-ttu-id="a4b86-p106">ネットワーク プレフィックス表記法 (CIDR 表記法とも呼ばれます) を使用して範囲を指定します。たとえば、192.168.1.0/27 には、192.168.1.0 192.168.1.31 (両端を含む) での値の範囲が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a4b86-p106">Specify a range, using network prefix notation (also known as CIDR notation). For example, 192.168.1.0/27 includes the range of values 192.168.1.0 through 192.168.1.31 (inclusive).</span></span>  <br/> |
|<span data-ttu-id="a4b86-137">**場所**と**ISP の登録**</span><span class="sxs-lookup"><span data-stu-id="a4b86-137">**Location** and **Registered ISP**</span></span> <br/> |<span data-ttu-id="a4b86-p107">IP アドレスの範囲のインターネット サービス プロバイダー (ISP) と保存場所を指定します。これよりも優先アドレスに対して定義されているパブリック フィールドなど、アイルランドで一般に公開と見なされますが、米国では実際には、IP アドレスがある場合は、役に立つは</span><span class="sxs-lookup"><span data-stu-id="a4b86-p107">Specify the location and Internet Service Provider (ISP) for the IP address range. This overrides the public fields defined for the addresses, which is helpful for cases, such as an IP address is that is considered publicly to be in Ireland but is actually in the U.S.</span></span>  <br/> |
|<span data-ttu-id="a4b86-140">**タグ**</span><span class="sxs-lookup"><span data-stu-id="a4b86-140">**Tags**</span></span> <br/> |<span data-ttu-id="a4b86-p108">タグを使用すると、IP アドレスのグループの名前を指定します。(「名前」フィールドと異なりが表示されるタグ アクティビティ ログに記録します。)タグを使用する語句を入力します。各 IP アドレスの範囲を好きなように多くのタグを追加することができます。既に設定したタグと、この IP アドレス範囲を追加する、入力を開始するように表示される現在のタグの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="a4b86-p108">Use tags to name your groups of IP addresses. (Unlike the Name field, you will see Tags in activity logs.) Type a word or phrase that you want to use for a tag. You can add as many tags as you like for each IP address range. And if you've already set up a tag and you want to add this IP address range to it, choose it from the list of current tags that appear as you start typing.</span></span>  <br/> |
|<span data-ttu-id="a4b86-145">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="a4b86-145">**Category**</span></span> <br/> | <span data-ttu-id="a4b86-p109">特定の IP アドレスからの活動を認識しやすくには、タグにカテゴリを割り当てます。次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="a4b86-p109">Assign categories to your tags to make it easier to recognize activities that come from certain IP addresses. Choose from the following options:  </span></span><br/> <span data-ttu-id="a4b86-148">**管理**すべての管理者の IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="a4b86-148">**Administrative** All of the IP addresses of your admins.</span></span>  <br/> <span data-ttu-id="a4b86-149">**クラウド プロバイダー**クラウドで、プロキシの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="a4b86-149">**Cloud provider** The IP address of your proxy in the cloud.</span></span>  <br/> <span data-ttu-id="a4b86-150">**企業**すべての IP アドレスしますの内部ネットワーク、支店、および、Wi-fi ローミングのアドレス。</span><span class="sxs-lookup"><span data-stu-id="a4b86-150">**Corporate** All of the IP addresses in your internal network, your branch offices, and your Wi-Fi roaming addresses.</span></span>  <br/> <span data-ttu-id="a4b86-p110">**危険**不審な IP アドレスをするなど、何らかの危険性をすることを検討する任意の IP アドレスは、以前は、競合企業のネットワークで IP アドレスを見たし、に。既定では、何らかの危険性のカテゴリには、IP の 2 つのタグが含まれます:**匿名のプロキシ**と**Tor**</span><span class="sxs-lookup"><span data-stu-id="a4b86-p110">**Risky** Any IP addresses that you consider to be risky, such as suspicious IP addresses you've seen in the past, IP addresses in your competitors' networks, and so on. By default, the Risky categories includes two IP tags: **Anonymous proxy** and **Tor**</span></span> <br/> <span data-ttu-id="a4b86-153">**VPN**リモート作業者が使用する IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="a4b86-153">**VPN** Any IP addresses that your remote workers use.</span></span>  <br/> |
   
7. <span data-ttu-id="a4b86-154">[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4b86-154">Choose **Save**.</span></span>
    
<span data-ttu-id="a4b86-155">IP アドレスの範囲を設定した後は、これらの変更のみの今後のイベントが発生することに留意してください。</span><span class="sxs-lookup"><span data-stu-id="a4b86-155">After you set up your IP address ranges, keep in mind that only future events are affected by these changes.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="a4b86-156">次の手順</span><span class="sxs-lookup"><span data-stu-id="a4b86-156">Next steps</span></span>

- [<span data-ttu-id="a4b86-157">活動ポリシーとアラート</span><span class="sxs-lookup"><span data-stu-id="a4b86-157">Activity policies and alerts</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="a4b86-158">異常検出のポリシー</span><span class="sxs-lookup"><span data-stu-id="a4b86-158">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="a4b86-159">SIEM サーバーを統合します。</span><span class="sxs-lookup"><span data-stu-id="a4b86-159">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="a4b86-160">Office 365 Cloud App Security の警告の確認と処理</span><span class="sxs-lookup"><span data-stu-id="a4b86-160">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    

