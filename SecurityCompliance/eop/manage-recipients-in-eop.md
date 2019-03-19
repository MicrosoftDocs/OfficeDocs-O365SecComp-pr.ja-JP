---
title: EOP で受信者を管理する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
description: Microsoft Exchange Online Protection (EOP) には、メールの受信者を管理するためのいくつかの方法が備わっています。 管理者は、Exchange 管理センター (EAC) またはリモート Windows PowerShell を使用して特定の管理タスクを実行し、Microsoft 365 管理センターで実行されたその他の管理タスクを確認できます。
ms.openlocfilehash: 52d423960444605382bd0314a5c12114fad755a2
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670402"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="59296-104">EOP で受信者を管理する</span><span class="sxs-lookup"><span data-stu-id="59296-104">Manage recipients in EOP</span></span>

<span data-ttu-id="59296-105">Microsoft Exchange Online Protection (EOP) には、メールの受信者を管理するためのいくつかの方法が備わっています。</span><span class="sxs-lookup"><span data-stu-id="59296-105">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients.</span></span> <span data-ttu-id="59296-106">管理者は、Exchange 管理センター (EAC) またはリモート Windows PowerShell を使用して特定の管理タスクを実行し、Microsoft 365 管理センターで実行されたその他の管理タスクを確認できます。</span><span class="sxs-lookup"><span data-stu-id="59296-106">As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="59296-107">EOP は次の受信者の種類をサポートします。</span><span class="sxs-lookup"><span data-stu-id="59296-107">EOP supports the following types of recipients:</span></span>
  
- <span data-ttu-id="59296-108">**メールユーザー**メールユーザーは、EOP 管理対象ドメイン内の受信者です。</span><span class="sxs-lookup"><span data-stu-id="59296-108">**Mail Users** Mail users are recipients in your EOP managed domains.</span></span> <span data-ttu-id="59296-109">これらの受信者は、Office 365 組織にログオン資格情報を持っていますが、外部の電子メールアドレスを持っています。つまり、受信者のメールボックスはクラウド組織外にあります。</span><span class="sxs-lookup"><span data-stu-id="59296-109">These recipients have logon credentials in your Office 365 organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization.</span></span> <span data-ttu-id="59296-110">メールを受信できるようにメールユーザーを追加したり、特定のユーザーのメールフロールール (トランスポートルールとも呼ばれます) を作成したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="59296-110">You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users.</span></span> <span data-ttu-id="59296-111">組織内のメールユーザーに役割を割り当てることもできます。管理役割グループの権限を持つユーザーは、Exchange 管理センター (EAC) にアクセスして、特定の管理タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="59296-111">You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks.</span></span> <span data-ttu-id="59296-112">ユーザーの役割と、EOP でユーザーの役割を割り当てる方法の詳細については、「 [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59296-112">To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>
    
    <span data-ttu-id="59296-113">EOP でのメール ユーザーの管理方法については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59296-113">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>
    
- <span data-ttu-id="59296-114">**グループ** メール ユーザーは、配布グループまたはセキュリティ グループに分類できます。</span><span class="sxs-lookup"><span data-stu-id="59296-114">**Groups** Mail users can be grouped together into distribution groups or security groups.</span></span> 
    
    <span data-ttu-id="59296-115">EOP でのグループの管理方法については、「[EOP でグループを管理する](manage-groups-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59296-115">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
    
<span data-ttu-id="59296-p104">このトピックの Exchange Online バージョンについては、「[Recipients in Exchange Online](http://technet.microsoft.com/library/50d16941-5cd7-435d-8715-e2b69f8410ab.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59296-p104">Looking for the Exchange Online version of this topic? See [Recipients in Exchange Online](http://technet.microsoft.com/library/50d16941-5cd7-435d-8715-e2b69f8410ab.aspx).</span></span>
  
<span data-ttu-id="59296-p105">このトピックの Exchange サーバー バージョンについては、「[Recipients](http://technet.microsoft.com/library/40300ed4-85a5-463d-bb3a-cf787bd44e9d.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59296-p105">Looking for the Exchange Server version of this topic? See [Recipients](http://technet.microsoft.com/library/40300ed4-85a5-463d-bb3a-cf787bd44e9d.aspx).</span></span>
  

