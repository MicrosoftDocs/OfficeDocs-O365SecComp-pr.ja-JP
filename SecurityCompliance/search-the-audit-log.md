---
title: Office 365 のユーザーと管理者のアクティビティの監査ログを検索します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: Office 365 の監査ログは、統合された監査ログです。理由統一された監査ログを記録しますか。あなたの組織は、ほとんどの Office 365 サービスからのイベントをサブスクライブするためは、検索可能な単一の監査ログに記録されます。つまり、ユーザーとこれらのサービスの管理者のアクティビティを検索できます。
ms.openlocfilehash: 7a6a552b1d2569c9e21fe20b39d474dafc026172
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532002"
---
# <a name="search-the-audit-log-for-user-and-admin-activity-in-office-365"></a><span data-ttu-id="7be56-106">Office 365 のユーザーと管理者のアクティビティの監査ログを検索します。</span><span class="sxs-lookup"><span data-stu-id="7be56-106">Search the audit log for user and admin activity in Office 365</span></span>

<span data-ttu-id="7be56-p102">Office 365 の監査ログは、統合された監査ログです。理由統一された監査ログを記録しますか。あなたの組織は、ほとんどの Office 365 サービスからのイベントをサブスクライブするためは、検索可能な単一の監査ログに記録されます。つまり、ユーザーとこれらのサービスの管理者のアクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="7be56-p102">The Office 365 audit log is a unified audit log. Why a unified audit log? Because events from most Office 365 services that you're organization subscribes to are recorded in a single audit log that you can search. That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="7be56-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7be56-111">SharePoint</span></span>
- <span data-ttu-id="7be56-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="7be56-112">OneDrive</span></span>
- <span data-ttu-id="7be56-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="7be56-113">Exchange</span></span>
- <span data-ttu-id="7be56-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7be56-114">Azure Active Directory</span></span>
- <span data-ttu-id="7be56-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7be56-115">Microsoft Teams</span></span>
- <span data-ttu-id="7be56-116">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="7be56-116">eDiscovery</span></span>
- <span data-ttu-id="7be56-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="7be56-117">Power BI</span></span>
- <span data-ttu-id="7be56-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="7be56-118">Yammer</span></span>
- <span data-ttu-id="7be56-119">Sway</span><span class="sxs-lookup"><span data-stu-id="7be56-119">Sway</span></span>
- <span data-ttu-id="7be56-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="7be56-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="7be56-121">監査を設定します。</span><span class="sxs-lookup"><span data-stu-id="7be56-121">Set up auditing</span></span>
  
<span data-ttu-id="7be56-122">Office 365 の監査ログを検索する前に実行する必要があるほとんどの点がありません。</span><span class="sxs-lookup"><span data-stu-id="7be56-122">There's few things you have to do before you can search the Office 365 audit log.</span></span>
  
- <span data-ttu-id="7be56-123">検索可能なイベントの記録を開始するのには[監査ログの検索の有効化](turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="7be56-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="7be56-124">メールボックスに関連するイベントを検索することができますので、[メールボックスの監査を有効にする](enable-mailbox-auditing.md)をなどとユーザーがサインイン、メールボックスまたはパージの項目に、[回復可能なアイテム] フォルダーから</span><span class="sxs-lookup"><span data-stu-id="7be56-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="7be56-125">監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="7be56-125">Search the audit log</span></span>
  
<span data-ttu-id="7be56-126">監査を有効にした後は何百もの個々 の複数の Office 365 サービスからのイベントの種類を検索します。</span><span class="sxs-lookup"><span data-stu-id="7be56-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Office 365 services.</span></span>
  
- <span data-ttu-id="7be56-127">ユーザーと管理者のアクティビティの[監査ログを検索](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="7be56-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="7be56-128">各監査レコードが検索結果に含まれている[詳細なプロパティを理解する](detailed-properties-in-the-office-365-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="7be56-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="7be56-129">管理者およびコンプライアンス マネージャーによって実行される[アクティビティの電子的証拠開示に関連する検索](search-for-ediscovery-activities-in-the-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="7be56-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 
