---
title: スパム対策ポリシーを構成する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/9/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: スパム フィルターは、既定のスパム対策ポリシー (接続フィルター、スパム フィルター、送信スパム) により、企業全体で自動的に有効になります。管理者は既定のスパム対策ポリシーを削除できません。ただし、表示と編集は行えるため、組織のニーズを最適に満たすように既定のスパム対策ポリシーをカスタマイズすることは可能です。よりきめ細かく制御する場合は、カスタム ポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することもできます。既定で、カスタム ポリシーの方が既定のポリシーより優先されますが、ポリシーの優先度は変更できます。
ms.openlocfilehash: 73154ae18d6aff3d983ed8a9f175469056fb9487
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153849"
---
# <a name="configure-the-anti-spam-policies"></a><span data-ttu-id="b2f9a-106">スパム対策ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="b2f9a-106">Configure the anti-spam policies</span></span>

<span data-ttu-id="b2f9a-p102">スパム フィルターは、既定のスパム対策ポリシー (接続フィルター、スパム フィルター、送信スパム) により、企業全体で自動的に有効になります。管理者は既定のスパム対策ポリシーを削除できません。ただし、表示と編集は行えるため、組織のニーズを最適に満たすように既定のスパム対策ポリシーをカスタマイズすることは可能です。よりきめ細かく制御する場合は、カスタム ポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することもできます。既定で、カスタム ポリシーの方が既定のポリシーより優先されますが、ポリシーの優先度は変更できます。</span><span class="sxs-lookup"><span data-stu-id="b2f9a-p102">Spam filtering is automatically enabled company-wide through the default anti-spam policies (connection filter, spam filter, and outbound spam). As an administrator, you can view and edit, but not delete, the default anti-spam policies so that they are tailored to best meet the needs of your organization. For greater granularity, you can also create custom policies and apply them to specified users, groups, or domains in your organization. By default, custom policies take precedence over the default policy, but you can change the priority of your policies.</span></span> 
  
<span data-ttu-id="b2f9a-111">スパム対策ポリシーの構成の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2f9a-111">For more about configuring your anti-spam policies, see the following topics:</span></span>
  
[<span data-ttu-id="b2f9a-112">接続フィルター ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="b2f9a-112">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="b2f9a-113">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="b2f9a-113">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> <span data-ttu-id="b2f9a-114">EOP スタンドアロンのお客様の場合、既定では、EOP コンテンツ フィルターはスパム検出メッセージを各受信者の迷惑メール フォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="b2f9a-114">For EOP standalone customers: By default, the EOP content filters send spam-detected messages to each recipients' Junk Email folder.</span></span> <span data-ttu-id="b2f9a-115">ただし、[**メッセージを迷惑メールフォルダーに移動する**] アクションがオンプレミスのメールボックスに対して機能するようにするには、オンプレミスのサーバー上で2つの Exchange メールフロールール (トランスポートルールとも呼ばれる) を構成して、によって追加されたスパムヘッダーを検出する必要があります。EOP.</span><span class="sxs-lookup"><span data-stu-id="b2f9a-115">However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange mail flow rules (also known as transport rules) on your on-premises servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="b2f9a-116">詳細については、「 [スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2f9a-116">For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
[<span data-ttu-id="b2f9a-117">送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="b2f9a-117">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  

