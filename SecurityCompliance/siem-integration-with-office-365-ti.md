---
title: Office 365 脅威インテリジェンスとSIEMの統合
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
description: Office 365 の活動の管理 API を使用して Office 365 の脅威インテリジェンスと組織の SIEM のサーバーを統合します。
ms.openlocfilehash: 82aeeea53bf87f1555fa68b2784b8fe38a435e15
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532404"
---
# <a name="siem-integration-with-office-365-threat-intelligence"></a><span data-ttu-id="18008-103">Office 365 脅威インテリジェンスとSIEMの統合</span><span class="sxs-lookup"><span data-stu-id="18008-103">SIEM integration with Office 365 Threat Intelligence</span></span>

<span data-ttu-id="18008-p101">組織がセキュリティ インシデントとイベント管理 (SIEM) サーバーを使用している場合は、SIEM サーバーと Office 365 の脅威インテリジェンスを統合できます。SIEM サーバー レポートで、Office 365 の脅威インテリジェンスによって検出されたマルウェアなどの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="18008-p101">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Threat Intelligence with your SIEM server. This enables you to view information, such as malware detected by Office 365 Threat Intelligence, in your SIEM server reports.</span></span>
  
## <a name="use-the-office-365-activity-management-api"></a><span data-ttu-id="18008-106">Office 365 の活動の管理 API を使用します。</span><span class="sxs-lookup"><span data-stu-id="18008-106">Use the Office 365 Activity Management API</span></span>

<span data-ttu-id="18008-p102">SIEM サーバーと Office 365 の脅威インテリジェンスを統合するには、Office 365 の活動の管理 API を使用します。この API は、組織の Office 365 と Azure AD 動作状況のログから、ユーザー、管理者、システム、ポリシー アクション、およびイベントに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="18008-p102">To integrate Office 365 Threat Intelligence with your SIEM server, use the Office 365 Activity Management API. This API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure AD activity logs.</span></span> 
  
<span data-ttu-id="18008-109">Office 365 のグローバル管理者であるか、セキュリティに割り当てられているセキュリティ管理者の役割を持っている必要があります&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="18008-109">You must be an Office 365 global administrator or have the security administrator role assigned in the Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="18008-110">[Office 365 の管理アクティビティの API リファレンス](https://msdn.microsoft.com/en-us/office-365/office-365-management-activity-api-reference)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18008-110">See [Office 365 Management Activity API reference](https://msdn.microsoft.com/en-us/office-365/office-365-management-activity-api-reference).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="18008-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="18008-111">Related topics</span></span>

[<span data-ttu-id="18008-112">Office 365 脅威インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="18008-112">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="18008-113">Office 365 での脅威からの保護</span><span class="sxs-lookup"><span data-stu-id="18008-113">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="18008-114">Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="18008-114">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

