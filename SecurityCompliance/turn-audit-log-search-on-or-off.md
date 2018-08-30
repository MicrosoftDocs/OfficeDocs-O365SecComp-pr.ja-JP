---
title: Office 365 監査ログの検索を有効または無効にする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: Office 365 のセキュリティの監査ログの検索機能を有効にできます&amp;コンプライアンス センターです。点を変更する場合にオフの場合はいつでもできます。監査ログの検索をオフにすると、管理者は、組織内ユーザーと管理者のアクティビティを Office 365 の監査ログを検索できません。
ms.openlocfilehash: 4fa6ac095222addce578294813cbd22dfc50a2ab
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532164"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="011ed-105">Office 365 監査ログの検索を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="011ed-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="011ed-p102">(または別の管理者) は、Office 365 の監査ログの検索を開始する前に監査ログを記録を有効にする必要があります。Office 365 のセキュリティ ログの検索をすると監査&amp;コンプライアンス センターをオンにして、組織内のユーザーと管理者のアクティビティを監査ログに記録されているし、90 日間保持されます。ただし、組織することも記録し、監査ログのデータを保持します。または監査データへのアクセスをサード ・ パーティ製のセキュリティ情報およびイベント管理 (SIEM) アプリケーションを使用する可能性があります。これらの場合では、グローバル管理者は Office 365 の監査ログの検索をオフにします。</span><span class="sxs-lookup"><span data-stu-id="011ed-p102">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log. When audit log search in the Office 365 Security &amp; Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days. However, your organization might not want to record and retain audit log data. Or you might be using a third-party security information and event management (SIEM) application to access your auditing data. In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="011ed-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="011ed-111">Before you begin</span></span>

- <span data-ttu-id="011ed-p103">監査ログの役割を割り当てる Exchange オンライン Office 365 組織の監査ログの検索を有効または無効にする必要があります。既定では、この役割は Exchange 管理センターで [**アクセス許可**] ページでのコンプライアンスの管理と組織管理の役割グループに割り当てられます。Office 365 の管理者がグローバル組織の管理役割グループのメンバーで Exchange はオンラインです。</span><span class="sxs-lookup"><span data-stu-id="011ed-p103">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization. By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="011ed-p104">ユーザーは、アクセス許可を割り当てるには、Exchange オンライン監査ログの検索を有効または無効にする必要があります。セキュリティの**アクセス許可**] ページで監査ログの役割をユーザーに割り当てる場合は、&amp;コンプライアンスの中心になる監査ログの検索を有効または無効にすることです。Exchange Online のコマンドレットは、コマンドレットを基になるためにです。</span><span class="sxs-lookup"><span data-stu-id="011ed-p104">Users have to be assigned permissions in Exchange Online to turn audit log search on or off. If you assign users the Audit Logs role on the **Permissions** page in the Security &amp; Compliance Center, they won't be able to turn audit log search on or off. This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="011ed-p105">Office 365 の監査ログの検索を無効にした場合、組織の監査のデータにアクセスするのには Office 365 の管理アクティビティの API も使用できます。この資料の手順に従って、監査ログの検索を無効にすることを意味する結果は返されません、セキュリティを使用して監査ログを検索すると、&amp;コンプライアンス センターまたは Exchange Online の**検索 UnifiedAuditLog**コマンドレットを実行するときPowerShell。ただし場合は、任意のアプリケーションを Office 365 の管理アクティビティの API を使用して、組織の監査のデータにアクセスする権限を与えて、それらのアプリケーションは引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="011ed-p105">If you turn off audit log search in Office 365, you can still use the Office 365 Management Activity API to access auditing data for your organization. Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security &amp; Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell. However, if you've authorized any application to access your organization's auditing data via the Office 365 Management Activity API , those applications will continue to work.</span></span> 
    
- <span data-ttu-id="011ed-121">Office 365 の検索の詳細については監査ログを参照してください[では、Office 365 のセキュリティ監査ログを検索する&amp;コンプライアンス センター](search-the-audit-log-in-security-and-compliance.md)です。</span><span class="sxs-lookup"><span data-stu-id="011ed-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="011ed-122">監査ログの検索を有効にします。</span><span class="sxs-lookup"><span data-stu-id="011ed-122">Turn on audit log search</span></span>

<span data-ttu-id="011ed-p106">セキュリティを使用することができます&amp;コンプライアンス センターまたは PowerShell は、Office 365 の監査ログの検索を有効にします。監査ログを検索する場合は、結果を返すことができます前に、監査ログの検索を有効にするいくつかの時間がかかる場合があります。監査ログの役割を割り当てる Exchange オンライン監査ログの検索を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="011ed-p106">You can use the Security &amp; Compliance Center or PowerShell to turn on audit log search in Office 365. It might take several hours after you turn on audit log search before you can return results when you search the audit log. You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security-amp-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="011ed-126">セキュリティを使用して、&amp;監査ログの検索を有効にするのにはコンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="011ed-126">Use the Security &amp; Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="011ed-127">セキュリティ&amp;コンプライアンス センター] に移動**検索&amp;調査** \> **監査ログの検索**します。</span><span class="sxs-lookup"><span data-stu-id="011ed-127">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Audit log search**.</span></span>
    
2. <span data-ttu-id="011ed-128">**ユーザーと管理者の活動の記録を開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="011ed-128">Click **Start recording user and admin activities**.</span></span>
    
    ![[ユーザーと管理者の活動記録を開始する] をクリックして、監査を有効にします。](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="011ed-130">ユーザーおよび組織の活動を管理される Office 365 の監査ログに記録されたとレポートの表示に使用できることを示すダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="011ed-130">A dialog box is displayed saying that user and admin activity in your organization will be recorded to the Office 365 audit log and available to view in a report.</span></span> 
    
3. <span data-ttu-id="011ed-131">監査ログ検索の下で、 **[ユーザーと管理者のアクティビティの記録を開始する]** リンクを選択します (既にこの操作を実行済みの場合は、リンクは表示されません)。</span><span class="sxs-lookup"><span data-stu-id="011ed-131">Click **Turn on**.</span></span>
    
    <span data-ttu-id="011ed-132">監査ログが準備中し、準備が完了した後の時間のいくつかの検索を実行するにはことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="011ed-132">A message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="011ed-133">PowerShell を使用して、監査ログの検索を有効にするのには</span><span class="sxs-lookup"><span data-stu-id="011ed-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="011ed-134">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="011ed-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="011ed-135">Office 365 の監査ログの検索を有効にするのには次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="011ed-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="011ed-136">変更を反映するには、最大で 60 分がかかる場合がありますというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="011ed-136">A message is displayed saying that it might take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="011ed-137">監査ログの検索をオフにします。</span><span class="sxs-lookup"><span data-stu-id="011ed-137">Turn off audit log search</span></span>

<span data-ttu-id="011ed-p107">監査ログの検索を無効にするのには、オンラインの Exchange 組織に接続されている、リモート PowerShell を使用する必要があります。監査ログの検索を有効にすると同様に、監査ログの役割を割り当てるには、Exchange オンライン監査ログの検索を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="011ed-p107">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search. Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="011ed-140">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="011ed-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="011ed-141">Office 365 の監査ログの検索を無効にするのには次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="011ed-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="011ed-p108">しばらくして、その監査ログの検索がオフ (無効) になっているを確認します。これを行う 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="011ed-p108">After a while, verify that audit log search is turned off (disabled). There are two ways to do this:</span></span>
    
    - <span data-ttu-id="011ed-144">PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="011ed-144">In PowerShell, run the following command:</span></span>

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        <span data-ttu-id="011ed-145">値`False` _UnifiedAuditLogIngestionEnabled_のプロパティを示しますその監査ログの検索が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="011ed-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="011ed-146">セキュリティ&amp;コンプライアンス センター] に移動**検索&amp;調査** \> **監査ログの検索**、し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="011ed-146">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Audit log search**, and then click **Search**.</span></span>
    
      <span data-ttu-id="011ed-147">監査ログの検索では、有効になっていないことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="011ed-147">A message is displayed saying that audit log search isn't turned on.</span></span> 
    
      ![監査を無効になっている場合、メッセージは dispayed](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
