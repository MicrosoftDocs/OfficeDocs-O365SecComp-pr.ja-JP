---
title: スパム対策ポリシーを構成する
ms.author: tracyp
author: MSFTTracyP
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
ms.collection:
- M365-security-compliance
description: スパム フィルターは、既定のスパム対策ポリシー (接続フィルター、スパム フィルター、送信スパム) により、企業全体で自動的に有効になります。管理者は既定のスパム対策ポリシーを削除できません。ただし、表示と編集は行えるため、組織のニーズを最適に満たすように既定のスパム対策ポリシーをカスタマイズすることは可能です。よりきめ細かく制御する場合は、カスタム ポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することもできます。既定で、カスタム ポリシーの方が既定のポリシーより優先されますが、ポリシーの優先度は変更できます。
ms.openlocfilehash: ebd65050fb5a0d3862653e0279ef530fbcabc042
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215427"
---
# <a name="configure-the-anti-spam-policies"></a>スパム対策ポリシーを構成する

スパム フィルターは、既定のスパム対策ポリシー (接続フィルター、スパム フィルター、送信スパム) により、企業全体で自動的に有効になります。管理者は既定のスパム対策ポリシーを削除できません。ただし、表示と編集は行えるため、組織のニーズを最適に満たすように既定のスパム対策ポリシーをカスタマイズすることは可能です。よりきめ細かく制御する場合は、カスタム ポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することもできます。既定で、カスタム ポリシーの方が既定のポリシーより優先されますが、ポリシーの優先度は変更できます。 
  
スパム対策ポリシーの構成の詳細については、次のトピックを参照してください。
  
[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)
  
[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> EOP スタンドアロンのお客様の場合、既定では、EOP コンテンツ フィルターはスパム検出メッセージを各受信者の迷惑メール フォルダーに送信します。ただし、社内メールボックスで **[メッセージを [迷惑メール] フォルダーに移動する]** アクションを確実に機能させるには、社内サーバーで 2 つの Exchange トランスポート ルールを構成して、EOP が追加したスパム ヘッダーを検出する必要があります。詳細については、「 [スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。 
  
[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)
  

