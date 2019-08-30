---
title: EOP で受信者を管理する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
description: Microsoft Exchange Online Protection (EOP) には、メールの受信者を管理するためのいくつかの方法が備わっています。 管理者は、Exchange 管理センター (EAC) またはリモート Windows PowerShell を使用して特定の管理タスクを実行し、Microsoft 365 管理センターで実行されたその他の管理タスクを確認できます。
ms.openlocfilehash: 6b56bcf725fe461c7e059658e7981f27bd4c07eb
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676577"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="cb02e-104">EOP で受信者を管理する</span><span class="sxs-lookup"><span data-stu-id="cb02e-104">Manage recipients in EOP</span></span>

<span data-ttu-id="cb02e-105">Microsoft Exchange Online Protection (EOP) には、メールの受信者を管理するためのいくつかの方法が備わっています。</span><span class="sxs-lookup"><span data-stu-id="cb02e-105">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients.</span></span> <span data-ttu-id="cb02e-106">管理者は、Exchange 管理センター (EAC) またはリモート Windows PowerShell を使用して特定の管理タスクを実行し、Microsoft 365 管理センターで実行されたその他の管理タスクを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cb02e-106">As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="cb02e-107">EOP は次の受信者の種類をサポートします。</span><span class="sxs-lookup"><span data-stu-id="cb02e-107">EOP supports the following types of recipients:</span></span>
  
- <span data-ttu-id="cb02e-108">**メールユーザー**: メールユーザーは、EOP 管理対象ドメインの受信者です。</span><span class="sxs-lookup"><span data-stu-id="cb02e-108">**Mail Users**: Mail users are recipients in your EOP managed domains.</span></span> <span data-ttu-id="cb02e-109">これらの受信者は、Office 365 組織にログオン資格情報を持っていますが、外部の電子メールアドレスを持っています。つまり、受信者のメールボックスはクラウド組織外にあります。</span><span class="sxs-lookup"><span data-stu-id="cb02e-109">These recipients have logon credentials in your Office 365 organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization.</span></span>

  <span data-ttu-id="cb02e-110">メールを受信できるようにメールユーザーを追加したり、特定のユーザーのメールフロールール (トランスポートルールとも呼ばれます) を作成したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cb02e-110">You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users.</span></span> <span data-ttu-id="cb02e-111">組織内のメールユーザーに役割を割り当てることもできます。管理役割グループの権限を持つユーザーは、Exchange 管理センター (EAC) にアクセスして、特定の管理タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="cb02e-111">You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks.</span></span> <span data-ttu-id="cb02e-112">ユーザーの役割と、EOP でユーザーの役割を割り当てる方法の詳細については、「 [Manage admin role group permissions IN EOP](manage-admin-role-group-permissions-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb02e-112">To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>

  <span data-ttu-id="cb02e-113">EOP でのメール ユーザーの管理方法については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb02e-113">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

- <span data-ttu-id="cb02e-114">**グループ**: メールユーザーを配布グループまたはセキュリティグループにまとめてグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="cb02e-114">**Groups**: Mail users can be grouped together into distribution groups or security groups.</span></span>

<span data-ttu-id="cb02e-115">EOP でのグループの管理方法については、「[EOP でグループを管理する](manage-groups-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb02e-115">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
