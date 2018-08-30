---
title: Office 365 のリソースの制限
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: Office 365 内でさまざまなアプリケーションのリソースに関する情報が制限されています。'
ms.openlocfilehash: a2e7ef42f9bf224363f3b10a5e450d6127f11585
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532814"
---
# <a name="resource-limits"></a><span data-ttu-id="e46ec-103">リソースの制限</span><span class="sxs-lookup"><span data-stu-id="e46ec-103">Resource Limits</span></span>

<span data-ttu-id="e46ec-p101">クォータ (制限) を使用し、調整、リソースの制限が適用されます。Azure Active Directory および個々 の Office 365 サービスは、両方を使用します。制限はサービス固有であるため、新機能を追加すると、時間の経過と共に変更します。さまざまなサービスの現在の制限の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e46ec-p101">Resource limits are enforced using quotas (limits) and throttling. Azure Active Directory and the individual Office 365 services use both. Limits are service-specific and change over time as new capabilities are added. For details on the current limits for the various services, see the following topics:</span></span>
- [<span data-ttu-id="e46ec-108">Azure Active Directory サービスの制限と制限</span><span class="sxs-lookup"><span data-stu-id="e46ec-108">Azure Active Directory service limits and restrictions</span></span>](https://msdn.microsoft.com/en-us/library/azure/dn764971.aspx)
- [<span data-ttu-id="e46ec-109">Exchange Online の制限</span><span class="sxs-lookup"><span data-stu-id="e46ec-109">Exchange Online Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
- [<span data-ttu-id="e46ec-110">Exchange Online Protection の制限</span><span class="sxs-lookup"><span data-stu-id="e46ec-110">Exchange Online Protection Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-protection-limits.aspx)
- [<span data-ttu-id="e46ec-111">SharePoint Online ソフトウェアの境界と制限</span><span class="sxs-lookup"><span data-stu-id="e46ec-111">SharePoint Online software boundaries and limits</span></span>](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [<span data-ttu-id="e46ec-112">Skype ビジネスの制限について</span><span class="sxs-lookup"><span data-stu-id="e46ec-112">Skype for Business Limits</span></span>](https://technet.microsoft.com/en-us/library/skype-for-business-online-limits.aspx)
- [<span data-ttu-id="e46ec-113">Yammer REST API およびレートの制限</span><span class="sxs-lookup"><span data-stu-id="e46ec-113">Yammer REST API and Rate Limits</span></span>](https://developer.yammer.com/docs/rest-api-rate-limits)
- [<span data-ttu-id="e46ec-114">ファイル サイズの制限に影響を与える</span><span class="sxs-lookup"><span data-stu-id="e46ec-114">File Size Limits in Sway</span></span>](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

<span data-ttu-id="e46ec-p102">これらの制限だけでなくいくつかの調整メカニズムは、Azure Active Directory と Office 365 の全体で使用されます。サービス内での調整が特に重要に、マイクロソフトのデータ センター内のネットワーク リソースは、広範なサービスを使用するお客様用に最適化されました。調整のメカニズムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e46ec-p102">In addition to these limits, several throttling mechanisms are used throughout Azure Active Directory and Office 365. Throttling within the service is especially important, given that network resources in Microsoft's datacenters are optimized for the broad set of customers that use the services. Throttling mechanisms include:</span></span>
- <span data-ttu-id="e46ec-118">Azure Active Directory と Office 365 機能ユーザー ・ レベルの調整、トランザクション、または 1 人のユーザーで実行できる (スクリプトまたはコード) での同時呼び出しの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="e46ec-118">Azure Active Directory and Office 365 feature user-level throttling, which limit the number of transactions or concurrent calls (by script or code) that can be performed by a single user.</span></span>
- <span data-ttu-id="e46ec-p103">既定のポリシーを調整する PowerShell は、テナントの作成時に、各テナントに割り当てられます。これらの設定は、1 人の管理者が開くことができる同時の PowerShell セッションの最大数などの項目を影響します。</span><span class="sxs-lookup"><span data-stu-id="e46ec-p103">A default PowerShell throttling policy is assigned to each tenant at tenant creation. These settings affect other items, such as the maximum number of simultaneous PowerShell sessions that can be opened by a single administrator.</span></span>
- <span data-ttu-id="e46ec-121">各 Exchange オンラインのお客様は、クライアント ・ オペレーションは EWS のチューニングは、既定の Exchange Web サービス (EWS) ポリシーを持っているし、すべての Outlook クライアントに適用する調整します。</span><span class="sxs-lookup"><span data-stu-id="e46ec-121">Each Exchange Online customer has a default Exchange Web Services (EWS) policy that is tuned for EWS client operations, and throttling that applies to all Outlook clients.</span></span>
