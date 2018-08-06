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
description: Microsoft Exchange Online Protection (EOP) には、メールの受信者を管理するためのいくつかの方法が備わっています。管理者は、Exchange 管理センター (EAC) 内で、またはリモートの Windows PowerShell を使用して、特定の管理タスクを実行するとともに、Microsoft Office 365 管理センターで実行されたその他の管理タスクを確認できます。
ms.openlocfilehash: 0159604eaa4e021d9ccef544306e8b274af11f18
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027574"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="74945-104">EOP で受信者を管理する</span><span class="sxs-lookup"><span data-stu-id="74945-104">Manage recipients in EOP</span></span>

<span data-ttu-id="74945-p102">Microsoft Exchange Online Protection (EOP) には、メールの受信者を管理するためのいくつかの方法が備わっています。管理者は、Exchange 管理センター (EAC) 内で、またはリモートの Windows PowerShell を使用して、特定の管理タスクを実行するとともに、Microsoft Office 365 管理センターで実行されたその他の管理タスクを確認できます。</span><span class="sxs-lookup"><span data-stu-id="74945-p102">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients. As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft Office 365 admin center.</span></span>
  
<span data-ttu-id="74945-107">EOP は次の受信者の種類をサポートします。</span><span class="sxs-lookup"><span data-stu-id="74945-107">EOP supports the following types of recipients:</span></span>
  
- <span data-ttu-id="74945-p103">**メール ユーザー**メール ユーザーとは、EOP 内の受信者のドメインを管理します。これらの受信者がログオン資格情報を Office 365 の組織内にあるが、外部の電子メール アドレス、受信者のメールボックスがクラウド組織の外にあることを意味します。メール ユーザーを追加するには、メールを受信することができ、特定のユーザーに対してトランスポート ルールを作成することもできるようにします。組織内で、メール ユーザーにロールを割り当てることができますも管理役割グループの特権を持つユーザーでは、Exchange 管理センター (EAC) にアクセスでき、特定の管理タスクを実行することができます。ユーザー ロールおよび EOP でユーザーのロールを割り当てる方法に関する詳細については、 [EOP の管理者の役割グループ権限の管理](manage-admin-role-group-permissions-in-eop.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74945-p103">**Mail Users** Mail users are recipients in your EOP managed domains. These recipients have logon credentials in your Office 365 organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization. You can add mail users so that they can receive mail and you can also create transport rules for specific users. You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks. To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>
    
    <span data-ttu-id="74945-113">EOP でのメール ユーザーの管理方法については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74945-113">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>
    
- <span data-ttu-id="74945-114">**グループ** メール ユーザーは、配布グループまたはセキュリティ グループに分類できます。</span><span class="sxs-lookup"><span data-stu-id="74945-114">**Groups** Mail users can be grouped together into distribution groups or security groups.</span></span> 
    
    <span data-ttu-id="74945-115">EOP でのグループの管理方法については、「[EOP でグループを管理する](manage-groups-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74945-115">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
    
<span data-ttu-id="74945-p104">このトピックの Exchange Online バージョンについては、「[Recipients in Exchange Online](http://technet.microsoft.com/library/50d16941-5cd7-435d-8715-e2b69f8410ab.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74945-p104">Looking for the Exchange Online version of this topic? See [Recipients in Exchange Online](http://technet.microsoft.com/library/50d16941-5cd7-435d-8715-e2b69f8410ab.aspx).</span></span>
  
<span data-ttu-id="74945-p105">このトピックの Exchange サーバー バージョンについては、「[Recipients](http://technet.microsoft.com/library/40300ed4-85a5-463d-bb3a-cf787bd44e9d.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74945-p105">Looking for the Exchange Server version of this topic? See [Recipients](http://technet.microsoft.com/library/40300ed4-85a5-463d-bb3a-cf787bd44e9d.aspx).</span></span>
  

