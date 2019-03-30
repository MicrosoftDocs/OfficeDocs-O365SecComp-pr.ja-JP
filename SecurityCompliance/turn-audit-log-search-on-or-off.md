---
title: Office 365 監査ログの検索を有効または無効にする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: セキュリティ & コンプライアンスセンターで、監査ログ検索機能を有効にすることができます。 変更した場合は、いつでもオフにすることができます。 監査ログ検索がオフになっている場合、管理者は、組織内のユーザーおよび管理者のアクティビティに対して Office 365 監査ログを検索することはできません。
ms.openlocfilehash: a77114ac9b5de18d4718a543983f7a1f94ebc41f
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000930"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="999a8-105">Office 365 監査ログの検索を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="999a8-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="999a8-106">Office 365 監査ログの検索を開始する前に、自分 (または別の管理者) が監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="999a8-106">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log.</span></span> <span data-ttu-id="999a8-107">セキュリティ & コンプライアンスセンターで監査ログの検索が有効になっている場合、組織からのユーザーおよび管理者のアクティビティが監査ログに記録され、90日間保存されます。</span><span class="sxs-lookup"><span data-stu-id="999a8-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days.</span></span> <span data-ttu-id="999a8-108">ただし、監査ログデータを記録して保持したくない組織もあります。</span><span class="sxs-lookup"><span data-stu-id="999a8-108">However, your organization might not want to record and retain audit log data.</span></span> <span data-ttu-id="999a8-109">または、サードパーティのセキュリティ情報およびイベント管理 (SIEM) アプリケーションを使用して、監査データにアクセスしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="999a8-109">Or you might be using a third-party security information and event management (SIEM) application to access your auditing data.</span></span> <span data-ttu-id="999a8-110">そのような場合、グローバル管理者は Office 365 で監査ログの検索を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="999a8-110">In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="999a8-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="999a8-111">Before you begin</span></span>

- <span data-ttu-id="999a8-112">Office 365 組織で監査ログの検索をオンまたはオフにするには、Exchange Online の audit Logs 役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="999a8-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization.</span></span> <span data-ttu-id="999a8-113">既定では、この役割は、Exchange 管理センターの [**アクセス許可**] ページで、コンプライアンス管理および組織の管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="999a8-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="999a8-114">Office 365 のグローバル管理者は、Exchange Online の Organization Management 役割グループのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="999a8-114">Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="999a8-115">監査ログの検索を有効または無効にするには、Exchange Online のアクセス許可をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="999a8-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="999a8-116">セキュリティ & コンプライアンスセンターの [**アクセス許可**] ページで監査ログの役割をユーザーに割り当てると、監査ログの検索をオンまたはオフにすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="999a8-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="999a8-117">これは、基礎となるコマンドレットが Exchange Online のコマンドレットであるためです。</span><span class="sxs-lookup"><span data-stu-id="999a8-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="999a8-118">office 365 で監査ログの検索を無効にしても、office 365 Management Activity API を使用して組織の監査データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="999a8-118">If you turn off audit log search in Office 365, you can still use the Office 365 Management Activity API to access auditing data for your organization.</span></span> <span data-ttu-id="999a8-119">この記事の手順に従って監査ログの検索を無効にすると、Security & コンプライアンスセンターを使用して監査ログを検索したとき、または Exchange Online で**search-unifiedauditlog**コマンドレットを実行したときに結果が返されないことを意味します。PowerShell.</span><span class="sxs-lookup"><span data-stu-id="999a8-119">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="999a8-120">ただし、Office 365 Management Activity API を使用して組織の監査データにアクセスするアプリケーションを承認した場合、これらのアプリケーションは引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="999a8-120">However, if you've authorized any application to access your organization's auditing data via the Office 365 Management Activity API , those applications will continue to work.</span></span> 
    
- <span data-ttu-id="999a8-121">Office 365 監査ログの検索の詳細な手順については、「 [Security & コンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="999a8-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="999a8-122">監査ログ検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="999a8-122">Turn on audit log search</span></span>

<span data-ttu-id="999a8-123">Security & コンプライアンスセンターまたは PowerShell を使用して、Office 365 で監査ログの検索を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="999a8-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Office 365.</span></span> <span data-ttu-id="999a8-124">監査ログの検索を有効にすると、監査ログの検索時に結果を返す前に、数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="999a8-124">It might take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="999a8-125">監査ログ検索を有効にするには、Exchange Online で audit Logs 役割を割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="999a8-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="999a8-126">セキュリティ & コンプライアンスセンターを使用して監査ログの検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="999a8-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="999a8-127">セキュリティ & コンプライアンスセンターで、[**検索** \> **監査ログの検索**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="999a8-127">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
2. <span data-ttu-id="999a8-128">[**ユーザーと管理者のアクティビティの記録を開始**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="999a8-128">Click **Start recording user and admin activities**.</span></span>
    
    ![[ユーザーと管理者のアクティビティの記録を開始する] をクリックして、監査を有効にします。](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="999a8-130">組織内のユーザーおよび管理者のアクティビティが Office 365 の監査ログに記録され、レポートで表示できることを示すダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="999a8-130">A dialog box is displayed saying that user and admin activity in your organization will be recorded to the Office 365 audit log and available to view in a report.</span></span> 
    
3. <span data-ttu-id="999a8-131">監査ログ検索の下で、 **[ユーザーと管理者のアクティビティの記録を開始する]** リンクを選択します (既にこの操作を実行済みの場合は、リンクは表示されません)。</span><span class="sxs-lookup"><span data-stu-id="999a8-131">Click **Turn on**.</span></span>
    
    <span data-ttu-id="999a8-132">監査ログが準備されていて、準備が完了してから数時間で検索を実行できることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="999a8-132">A message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="999a8-133">PowerShell を使用して監査ログの検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="999a8-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="999a8-134">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="999a8-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="999a8-135">Office 365 で監査ログの検索を有効にするには、次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="999a8-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="999a8-136">変更が有効になるまでに最大60分かかる可能性があることを伝えるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="999a8-136">A message is displayed saying that it might take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="999a8-137">監査ログの検索を無効にする</span><span class="sxs-lookup"><span data-stu-id="999a8-137">Turn off audit log search</span></span>

<span data-ttu-id="999a8-138">監査ログの検索を無効にするには、Exchange Online 組織に接続されたリモート PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="999a8-138">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="999a8-139">監査ログ検索を有効にするのと同様に、監査ログ検索を無効にするには、Exchange Online の audit Logs 役割を割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="999a8-139">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="999a8-140">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="999a8-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="999a8-141">Office 365 で監査ログの検索を無効にするには、次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="999a8-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="999a8-142">しばらくした後、監査ログの検索がオフ (無効) になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="999a8-142">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="999a8-143">これを行うには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="999a8-143">There are two ways to do this:</span></span>
    
    - <span data-ttu-id="999a8-144">PowerShell で、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="999a8-144">In PowerShell, run the following command:</span></span>

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        <span data-ttu-id="999a8-145">UnifiedAuditLogIngestionEnabled プロパティの`False`の値__ は、監査ログの検索がオフになっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="999a8-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="999a8-146">セキュリティ & コンプライアンスセンターで、[ \*\*\*\* \> **監査ログ**の検索] に移動し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="999a8-146">In the Security & Compliance Center, go to **Search** \> **Audit log search**, and then click **Search**.</span></span>
    
      <span data-ttu-id="999a8-147">監査ログの検索が有効になっていないことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="999a8-147">A message is displayed saying that audit log search isn't turned on.</span></span> 
    
      ![監査がオフになっている場合は、メッセージが表示されます。](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
