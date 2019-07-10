---
title: スパム対策ポリシーを構成する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
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
ms.openlocfilehash: f6690ddf0f50762aaa7b9ff61385c279f66716c8
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600113"
---
# <a name="configure-the-anti-spam-policies"></a>スパム対策ポリシーを設定する

スパム フィルターは、既定のスパム対策ポリシー (接続フィルター、スパム フィルター、送信スパム) により、企業全体で自動的に有効になります。管理者は既定のスパム対策ポリシーを削除できません。ただし、表示と編集は行えるため、組織のニーズを最適に満たすように既定のスパム対策ポリシーをカスタマイズすることは可能です。よりきめ細かく制御する場合は、カスタム ポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することもできます。既定で、カスタム ポリシーの方が既定のポリシーより優先されますが、ポリシーの優先度は変更できます。 
  
スパム対策ポリシーの構成の詳細については、次のトピックを参照してください。
  
[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)
  
[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> EOP スタンドアロンのお客様の場合、既定では、EOP コンテンツ フィルターはスパム検出メッセージを各受信者の迷惑メール フォルダーに送信します。 ただし、[**メッセージを迷惑メールフォルダーに移動する**] アクションがオンプレミスのメールボックスに対して機能するようにするには、オンプレミスのサーバー上で2つの Exchange メールフロールール (トランスポートルールとも呼ばれる) を構成して、によって追加されたスパムヘッダーを検出する必要があります。EOP. 詳細については、「 [スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。 
  
[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)
  

