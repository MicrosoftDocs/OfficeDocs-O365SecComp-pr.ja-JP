---
title: Spam Confidence Level
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: 電子メール メッセージがスパム フィルターを通過すると、その電子メール メッセージにはスパム スコアが割り当てられます。そのスコアは個別の Spam Confidence Level (SCL) 評価にマップされ、X-ヘッダーにスタンプされます。サービスは SCL 評価のスパム信頼度の解釈を基に、メッセージに対してアクションを実施します。次の表は、さまざまな SCL 評価がフィルターによって解釈される方法、および評価ごとに受信メッセージに対して実行される既定のアクションを示しています。
ms.openlocfilehash: beb322341f4d0de25d7bac9681c0beed93c48e5f
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600877"
---
# <a name="spam-confidence-levels"></a>Spam Confidence Levels

電子メール メッセージがスパム フィルターを通過すると、その電子メール メッセージにはスパム スコアが割り当てられます。そのスコアは個別の Spam Confidence Level (SCL) 評価にマップされ、X-ヘッダーにスタンプされます。サービスは SCL 評価のスパム信頼度の解釈を基に、メッセージに対してアクションを実施します。次の表は、さまざまな SCL 評価がフィルターによって解釈される方法、および評価ごとに受信メッセージに対して実行される既定のアクションを示しています。
  
|**SCL 評価**|**スパム信頼度の解釈**|**既定のアクション**|
|:-----|:-----|:-----|
|-1|安全な送信者、安全な受信者、または安全なリストの IP アドレス (信頼できるパートナー) から送られてくる非スパム。|受信者の受信トレイにメッセージを配信します。|
|0, 1|非スパムメッセージがスキャンされ、クリーンであると判断された場合。|受信者の受信トレイにメッセージを配信します。|
|5, 6|スパム|受信者の迷惑メール フォルダーにメッセージを配信します。|
|7, 8, 9|信頼度の高いスパム|受信者の迷惑メール フォルダーにメッセージを配信します。|
   
> [!TIP]
> SCL ランク2、3、4、7、および8は、サービスによって設定されません。 SCL レベルが5または6の場合は、スパムの疑いがあると見なされます。これは、特定のスパムと見なされる SCL レベル9よりも短いスパムであると見なされます。 Exchange 管理センターのコンテンツフィルターポリシーを使用して、スパムや信頼度の高いスパムに対するさまざまなアクションを構成できます。 詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。 「[メールフロールールを使用してメッセージにスパム信頼レベル (SCL) を設定する](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)」で説明されているように、メールフロールール (トランスポートルールとも呼ばれます) を使用して、特定の条件に一致するメッセージの SCL レベルを設定することもできます。 メールフロールールを使用して、7、8、または9の SCL を設定すると、メッセージは信頼度の高いスパムとして処理されます。 
  
||
|:-----|
|![LinkedIn Learning の小さいアイコン](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Office 365 を初めて使用する場合は、**         LinkedIn Learning が提供する **Office 365 admins and IT pros** のための無料のビデオ コースをご覧ください。|
   

