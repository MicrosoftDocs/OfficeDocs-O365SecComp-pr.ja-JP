---
title: スパム対策ポリシーを構成する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/9/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
description: スパム フィルターは、既定のスパム対策ポリシー (接続フィルター、スパム フィルター、送信スパム) により、企業全体で自動的に有効になります。管理者は既定のスパム対策ポリシーを削除できません。ただし、表示と編集は行えるため、組織のニーズを最適に満たすように既定のスパム対策ポリシーをカスタマイズすることは可能です。よりきめ細かく制御する場合は、カスタム ポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することもできます。既定で、カスタム ポリシーの方が既定のポリシーより優先されますが、ポリシーの優先度は変更できます。
ms.openlocfilehash: c1bec3c7e8db3222f25a423ac94068d537529cac
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002345"
---
# <a name="configure-the-anti-spam-policies"></a><span data-ttu-id="60b68-106">スパム対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="60b68-106">Configure the anti-spam policies</span></span>

<span data-ttu-id="60b68-p102">スパム フィルターは、既定のスパム対策ポリシー (接続フィルター、スパム フィルター、送信スパム) により、企業全体で自動的に有効になります。管理者は既定のスパム対策ポリシーを削除できません。ただし、表示と編集は行えるため、組織のニーズを最適に満たすように既定のスパム対策ポリシーをカスタマイズすることは可能です。よりきめ細かく制御する場合は、カスタム ポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することもできます。既定で、カスタム ポリシーの方が既定のポリシーより優先されますが、ポリシーの優先度は変更できます。</span><span class="sxs-lookup"><span data-stu-id="60b68-p102">Spam filtering is automatically enabled company-wide through the default anti-spam policies (connection filter, spam filter, and outbound spam). As an administrator, you can view and edit, but not delete, the default anti-spam policies so that they are tailored to best meet the needs of your organization. For greater granularity, you can also create custom policies and apply them to specified users, groups, or domains in your organization. By default, custom policies take precedence over the default policy, but you can change the priority of your policies.</span></span> 
  
<span data-ttu-id="60b68-111">スパム対策ポリシーの構成の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="60b68-111">For more about configuring your anti-spam policies, see the following topics:</span></span>
  
[<span data-ttu-id="60b68-112">接続フィルター ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="60b68-112">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="60b68-113">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="60b68-113">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> <span data-ttu-id="60b68-p103">EOP スタンドアロンのお客様の場合、既定では、EOP コンテンツ フィルターはスパム検出メッセージを各受信者の迷惑メール フォルダーに送信します。ただし、社内メールボックスで **[メッセージを [迷惑メール] フォルダーに移動する]** アクションを確実に機能させるには、社内サーバーで 2 つの Exchange トランスポート ルールを構成して、EOP が追加したスパム ヘッダーを検出する必要があります。詳細については、「 [スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60b68-p103">For EOP standalone customers: By default, the EOP content filters send spam-detected messages to each recipients' Junk Email folder. However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange Transport rules on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
[<span data-ttu-id="60b68-117">送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="60b68-117">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  

