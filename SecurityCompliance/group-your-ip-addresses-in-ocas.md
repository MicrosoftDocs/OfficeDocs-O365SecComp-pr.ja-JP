---
title: IP アドレスをグループ化して Office 365 Cloud App Security の管理を簡素化する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: office 365 Cloud App Security で使用する ip アドレスのセット (物理的なオフィスの ip アドレスなど) を簡単に識別するには、ip アドレス範囲のグループを設定します。
ms.openlocfilehash: b8f5c1dd46b2e3990d53a65881d12ca8f3961b16
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220447"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a><span data-ttu-id="782b2-103">IP アドレスをグループ化して Office 365 Cloud App Security の管理を簡素化する</span><span class="sxs-lookup"><span data-stu-id="782b2-103">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="782b2-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="782b2-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="782b2-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="782b2-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="782b2-106">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="782b2-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="782b2-107">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="782b2-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="782b2-108">評価の開始</span><span class="sxs-lookup"><span data-stu-id="782b2-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="782b2-109">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="782b2-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="782b2-110">ここでは、</span><span class="sxs-lookup"><span data-stu-id="782b2-110">You are here!</span></span>  <br/> [<span data-ttu-id="782b2-111">次の手順</span><span class="sxs-lookup"><span data-stu-id="782b2-111">Next steps</span></span>](#next-steps) <br/> |[<span data-ttu-id="782b2-112">利用を開始する</span><span class="sxs-lookup"><span data-stu-id="782b2-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="782b2-p101">office 365 Cloud App Security で使用する ip アドレスのセット (物理的なオフィスの ip アドレスなど) を簡単に識別するには、ip アドレス範囲のグループを設定します。これらの範囲を定義すると、それらをタグ付けして分類することができます。次に、タグとカテゴリを使用して、アクティビティのログと通知の表示方法と調査方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="782b2-p101">To easily identify sets of IP addresses that you'll use in Office 365 Cloud App Security, such as your physical office IP addresses, you can set up groups of IP address ranges. Defining these ranges lets you tag and categorize them, and then you can use tags and categories to customize how your activity logs and alerts are displayed and investigated.</span></span>
  
<span data-ttu-id="782b2-p102">ip 範囲の各グループには、選択したタグ名でタグを付けることができます。その後、ip カテゴリの既定のリスト (企業、管理、リスク、および VPN) に基づいてタグを分類できます。IPv4 と IPv6 の両方のアドレスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="782b2-p102">Each group of IP ranges can be tagged with tag names that you choose, and then the tags can be categorized based on a default list of IP categories (such as Corporate, Administrative, Risky, and VPN). Both IPv4 and IPv6 addresses are supported.</span></span>
  
> [!NOTE]
> <span data-ttu-id="782b2-p103">この記事の手順を実行するには、全体管理者またはセキュリティ管理者である必要があります。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="782b2-p103">You must be a global administrator or security administrator to perform the procedures in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a><span data-ttu-id="782b2-119">Office 365 Cloud App Security で IP アドレス範囲を設定するには</span><span class="sxs-lookup"><span data-stu-id="782b2-119">To set up an IP address range in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="782b2-120">グローバル管理者またはセキュリティ管理者は、Cloud App security ポータル ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) にアクセスして、サインインします。</span><span class="sxs-lookup"><span data-stu-id="782b2-120">As a global administrator or security administrator, go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
    
2. <span data-ttu-id="782b2-121">ページの右上で、[ **IP アドレス範囲**の**設定** \> ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="782b2-121">On the upper right of the page, click **Settings** \> **IP address ranges**.</span></span><br><span data-ttu-id="782b2-122">![O365 Cloud App Security で、[設定] を選択してシステムとデータの設定にアクセスします。](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)</span><span class="sxs-lookup"><span data-stu-id="782b2-122">![In O365 Cloud App Security, choose Settings to access your system and data settings](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)</span></span><br>
  
3. <span data-ttu-id="782b2-123">プラス記号 ( **+**) に似た [新規] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="782b2-123">Click the new button, which resembles a plus sign ( **+**).</span></span>
    
4. <span data-ttu-id="782b2-124">[**新しい IP アドレスの範囲**] ウィンドウで、次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="782b2-124">In the **New IP address range** window, specify the following values:</span></span> 
    
|<span data-ttu-id="782b2-125">**フィールドまたはリスト**</span><span class="sxs-lookup"><span data-stu-id="782b2-125">**Field or list**</span></span>|<span data-ttu-id="782b2-126">**行うこと**</span><span class="sxs-lookup"><span data-stu-id="782b2-126">**What to do**</span></span>|
|:-----|:-----|
|<span data-ttu-id="782b2-127">**名前**</span><span class="sxs-lookup"><span data-stu-id="782b2-127">**Name**</span></span> <br/> |<span data-ttu-id="782b2-p104">このフィールドを使用して、IP アドレスの範囲と設定を管理します。(この値はアクティビティログに表示されません)。</span><span class="sxs-lookup"><span data-stu-id="782b2-p104">Use this field to manage your IP address range and settings. (You won't see this value in activities logs.)</span></span>  <br/> |
|<span data-ttu-id="782b2-130">**IP アドレスの範囲**</span><span class="sxs-lookup"><span data-stu-id="782b2-130">**IP address ranges**</span></span> <br/> |<span data-ttu-id="782b2-p105">ネットワークプレフィックス表記 (CIDR 表記とも呼ばれる) を使用して、範囲を指定します。たとえば、192.168.1.0/27 では、192.168.1.31 (包含) からの値の範囲が含まれています。</span><span class="sxs-lookup"><span data-stu-id="782b2-p105">Specify a range, using network prefix notation (also known as CIDR notation). For example, 192.168.1.0/27 includes the range of values 192.168.1.0 through 192.168.1.31 (inclusive).</span></span>  <br/> |
|<span data-ttu-id="782b2-133">**場所**と**登録されている ISP**</span><span class="sxs-lookup"><span data-stu-id="782b2-133">**Location** and **Registered ISP**</span></span> <br/> |<span data-ttu-id="782b2-p106">IP アドレスの範囲の場所とインターネットサービスプロバイダー (ISP) を指定します。これは、アドレスに対して定義されているパブリックフィールドを上書きします。これは、IP アドレスがアイルランドで公開されているものの、実際には米国で使用される場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="782b2-p106">Specify the location and Internet Service Provider (ISP) for the IP address range. This overrides the public fields defined for the addresses, which is helpful for cases, such as an IP address is that is considered publicly to be in Ireland but is actually in the U.S.</span></span>  <br/> |
|<span data-ttu-id="782b2-136">**タグ**</span><span class="sxs-lookup"><span data-stu-id="782b2-136">**Tags**</span></span> <br/> |<span data-ttu-id="782b2-p107">タグを使用して、IP アドレスのグループに名前を付けます。([名前] フィールドとは異なり、アクティビティログにタグが表示されます。)タグに使用する単語または語句を入力します。各 IP アドレス範囲に対して、必要な数のタグを追加できます。また、既にタグを設定している場合に、この IP アドレス範囲を追加するには、入力を開始したときに表示される現在のタグの一覧からタグを選択します。</span><span class="sxs-lookup"><span data-stu-id="782b2-p107">Use tags to name your groups of IP addresses. (Unlike the Name field, you will see Tags in activity logs.) Type a word or phrase that you want to use for a tag. You can add as many tags as you like for each IP address range. And if you've already set up a tag and you want to add this IP address range to it, choose it from the list of current tags that appear as you start typing.</span></span>  <br/> |
|<span data-ttu-id="782b2-141">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="782b2-141">**Category**</span></span> <br/> | <span data-ttu-id="782b2-p108">タグに分類項目を割り当てることにより、特定の IP アドレスからのアクティビティを簡単に識別できるようにします。次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="782b2-p108">Assign categories to your tags to make it easier to recognize activities that come from certain IP addresses. Choose from the following options:  </span></span><br/> <span data-ttu-id="782b2-144">**管理**管理者のすべての IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="782b2-144">**Administrative** All of the IP addresses of your admins.</span></span>  <br/> <span data-ttu-id="782b2-145">**クラウドプロバイダー**クラウド内のプロキシの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="782b2-145">**Cloud provider** The IP address of your proxy in the cloud.</span></span>  <br/> <span data-ttu-id="782b2-146">**企業**内部ネットワーク内のすべての IP アドレス、ブランチオフィス、および wi-fi ローミングアドレス。</span><span class="sxs-lookup"><span data-stu-id="782b2-146">**Corporate** All of the IP addresses in your internal network, your branch offices, and your Wi-Fi roaming addresses.</span></span>  <br/> <span data-ttu-id="782b2-p109">**危険**危険性があると考えられるすべての ip アドレス (過去に表示された疑わしい ip アドレス、競合企業のネットワーク内の ip アドレスなど)。既定では、危険なカテゴリには、**匿名プロキシ**と**Tor**という2つの IP タグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="782b2-p109">**Risky** Any IP addresses that you consider to be risky, such as suspicious IP addresses you've seen in the past, IP addresses in your competitors' networks, and so on. By default, the Risky categories includes two IP tags: **Anonymous proxy** and **Tor**</span></span> <br/> <span data-ttu-id="782b2-149">**VPN**リモートワーカーが使用する任意の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="782b2-149">**VPN** Any IP addresses that your remote workers use.</span></span>  <br/> |
   
7. <span data-ttu-id="782b2-150">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="782b2-150">Choose **Save**.</span></span>
    
<span data-ttu-id="782b2-151">IP アドレスの範囲を設定した後は、これらの変更による影響を受けるのは将来のイベントだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="782b2-151">After you set up your IP address ranges, keep in mind that only future events are affected by these changes.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="782b2-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="782b2-152">Next steps</span></span>

- [<span data-ttu-id="782b2-153">アクティビティポリシーとアラート</span><span class="sxs-lookup"><span data-stu-id="782b2-153">Activity policies and alerts</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="782b2-154">異常検出ポリシー</span><span class="sxs-lookup"><span data-stu-id="782b2-154">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="782b2-155">SIEM サーバーの統合</span><span class="sxs-lookup"><span data-stu-id="782b2-155">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="782b2-156">Office 365 Cloud App Security の警告の確認と処理</span><span class="sxs-lookup"><span data-stu-id="782b2-156">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    

