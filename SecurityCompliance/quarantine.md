---
title: 検疫
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9eecdde-dcc2-4283-a820-98d1e740e4f
ms.collection:
- M365-security-compliance
description: exchange online および exchange online Protection のホストされた検疫について説明します。
ms.openlocfilehash: 7a92704c7a3cf978ed028b094cac9f6c9ed4b47b
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32265669"
---
# <a name="quarantine"></a><span data-ttu-id="81e1a-103">検疫</span><span class="sxs-lookup"><span data-stu-id="81e1a-103">Quarantine</span></span>

<span data-ttu-id="81e1a-104">次のトピックでは、Exchange Online と Exchange Online Protection (EOP) の管理者およびエンド ユーザーの両方のためにホストされる検疫について説明します</span><span class="sxs-lookup"><span data-stu-id="81e1a-104">The following topics provide information about the hosted quarantine for both Exchange Online and Exchange Online Protection (EOP) admins and end users:</span></span>
  
- <span data-ttu-id="81e1a-105">[検疫に関する FAQ](quarantine-faq.md) - 管理者およびエンド ユーザーの両方のための検疫に関する一般的な質問と回答を提供します。</span><span class="sxs-lookup"><span data-stu-id="81e1a-105">[Quarantine FAQ](quarantine-faq.md) - Provides general questions and answers about the quarantine for both admins and end users</span></span> 
    
- <span data-ttu-id="81e1a-106">[管理者として検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-an-administrator.md) - 管理者が、Exchange 管理センター (EAC) の検疫にあるメッセージを検出して解放するための方法を説明します。さらにオプションとして、偽陽性 (迷惑メールではない) メッセージとして Microsoft に報告することができます。</span><span class="sxs-lookup"><span data-stu-id="81e1a-106">[Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md) - Describes how admins can find and release any message that resides in the quarantine in the Exchange admin center (EAC), and optionally report it as a false positive (not junk) message to Microsoft.</span></span> 
    
- <span data-ttu-id="81e1a-107">[検疫済みメッセージを検索して解放する (エンドユーザー)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx) -エンドユーザーがスパム検疫ユーザーインターフェイスで自分のスパム検疫メッセージを検索して解放し、それらを迷惑メールではないとして Microsoft に報告する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="81e1a-107">[Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx) - Describes how end users can find and release their own spam-quarantined messages in the spam quarantine user interface, and report them as not junk to Microsoft.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="81e1a-108">エンドユーザーのスパム検疫にアクセスするには、エンドユーザーが有効な Office 365 ユーザー ID とパスワードを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="81e1a-108">In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="81e1a-109">社内メールボックスを保護している EOP のお客様は、ディレクトリ同期または EAC を使用して作成された有効な電子メールユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="81e1a-109">EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC.</span></span> <span data-ttu-id="81e1a-110">ユーザーの管理の詳細については、EOP 管理者が[EOP でメールユーザーを管理](eop/manage-mail-users-in-eop.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81e1a-110">For more information about managing users, EOP admins can refer to [Manage mail users in EOP](eop/manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="81e1a-111">EOP スタンドアロンのお客様の場合は、ディレクトリ同期を使用し、ディレクトリベースのエッジブロックを有効にすることをお勧めします。詳細については、「[ディレクトリベースのエッジブロックを使用して無効な受信者に送信されたメッセージを拒否する](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81e1a-111">For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span> 
  
    

