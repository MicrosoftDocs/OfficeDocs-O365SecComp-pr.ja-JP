---
title: Office 365 リソースの制限
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '概要: Office 365 内のさまざまなアプリケーションのリソース制限についての情報。'
ms.openlocfilehash: ee44bde8bd93d3628ed3f31f5bbbce024a3056b5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220217"
---
# <a name="resource-limits"></a><span data-ttu-id="64f07-103">リソースの制限</span><span class="sxs-lookup"><span data-stu-id="64f07-103">Resource Limits</span></span>

<span data-ttu-id="64f07-p101">リソースの制限は、クォータ (制限) と調整を使用して適用されます。Azure Active Directory と個別の Office 365 サービスは両方を使用します。新しい機能が追加されると、制限はサービスに依存し、時間の経過と共に変化します。さまざまなサービスの現在の制限の詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f07-p101">Resource limits are enforced using quotas (limits) and throttling. Azure Active Directory and the individual Office 365 services use both. Limits are service-specific and change over time as new capabilities are added. For details on the current limits for the various services, see the following topics:</span></span>
- [<span data-ttu-id="64f07-108">Azure Active Directory サービスの制限と制限事項</span><span class="sxs-lookup"><span data-stu-id="64f07-108">Azure Active Directory service limits and restrictions</span></span>](https://msdn.microsoft.com/en-us/library/azure/dn764971.aspx)
- [<span data-ttu-id="64f07-109">Exchange Online の制限</span><span class="sxs-lookup"><span data-stu-id="64f07-109">Exchange Online Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
- [<span data-ttu-id="64f07-110">Exchange Online Protection の制限</span><span class="sxs-lookup"><span data-stu-id="64f07-110">Exchange Online Protection Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-protection-limits.aspx)
- [<span data-ttu-id="64f07-111">SharePoint Online ソフトウェアの境界と制限</span><span class="sxs-lookup"><span data-stu-id="64f07-111">SharePoint Online software boundaries and limits</span></span>](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [<span data-ttu-id="64f07-112">Skype for business の制限</span><span class="sxs-lookup"><span data-stu-id="64f07-112">Skype for Business Limits</span></span>](https://technet.microsoft.com/en-us/library/skype-for-business-online-limits.aspx)
- [<span data-ttu-id="64f07-113">Yammer REST API とレート制限</span><span class="sxs-lookup"><span data-stu-id="64f07-113">Yammer REST API and Rate Limits</span></span>](https://developer.yammer.com/docs/rest-api-rate-limits)
- [<span data-ttu-id="64f07-114">Sway でのファイルサイズの制限</span><span class="sxs-lookup"><span data-stu-id="64f07-114">File Size Limits in Sway</span></span>](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

<span data-ttu-id="64f07-p102">これらの制限に加えて、Azure Active Directory と Office 365 の間では、いくつかの調整メカニズムが使用されています。Microsoft のデータセンター内のネットワークリソースが、サービスを使用する幅広い顧客向けに最適化されているため、サービス内の調整は特に重要です。調整メカニズムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="64f07-p102">In addition to these limits, several throttling mechanisms are used throughout Azure Active Directory and Office 365. Throttling within the service is especially important, given that network resources in Microsoft's datacenters are optimized for the broad set of customers that use the services. Throttling mechanisms include:</span></span>
- <span data-ttu-id="64f07-118">Azure Active Directory と Office 365 のユーザーレベルの調整。単一のユーザーが実行できるトランザクションまたは同時呼び出し (スクリプトまたはコード) の数を制限します。</span><span class="sxs-lookup"><span data-stu-id="64f07-118">Azure Active Directory and Office 365 feature user-level throttling, which limit the number of transactions or concurrent calls (by script or code) that can be performed by a single user.</span></span>
- <span data-ttu-id="64f07-p103">テナントの作成時に、各テナントに既定の PowerShell 調整ポリシーが割り当てられます。これらの設定は、1人の管理者が開くことのできる同時 PowerShell セッションの最大数など、他のアイテムに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="64f07-p103">A default PowerShell throttling policy is assigned to each tenant at tenant creation. These settings affect other items, such as the maximum number of simultaneous PowerShell sessions that can be opened by a single administrator.</span></span>
- <span data-ttu-id="64f07-121">各 exchange Online の顧客には、ews クライアントの操作用に調整された既定の exchange Web サービス (EWS) ポリシーと、すべての Outlook クライアントに適用される調整があります。</span><span class="sxs-lookup"><span data-stu-id="64f07-121">Each Exchange Online customer has a default Exchange Web Services (EWS) policy that is tuned for EWS client operations, and throttling that applies to all Outlook clients.</span></span>
