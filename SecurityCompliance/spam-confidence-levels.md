---
title: Spam Confidence Level
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
description: 電子メール メッセージがスパム フィルターを通過すると、その電子メール メッセージにはスパム スコアが割り当てられます。そのスコアは個別の Spam Confidence Level (SCL) 評価にマップされ、X-ヘッダーにスタンプされます。サービスは SCL 評価のスパム信頼度の解釈を基に、メッセージに対してアクションを実施します。次の表は、さまざまな SCL 評価がフィルターによって解釈される方法、および評価ごとに受信メッセージに対して実行される既定のアクションを示しています。
ms.openlocfilehash: cd33f440828761ab8cb496d9eff07288d974514c
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026284"
---
# <a name="spam-confidence-levels"></a>Spam Confidence Level

電子メール メッセージがスパム フィルターを通過すると、その電子メール メッセージにはスパム スコアが割り当てられます。そのスコアは個別の Spam Confidence Level (SCL) 評価にマップされ、X-ヘッダーにスタンプされます。サービスは SCL 評価のスパム信頼度の解釈を基に、メッセージに対してアクションを実施します。次の表は、さまざまな SCL 評価がフィルターによって解釈される方法、および評価ごとに受信メッセージに対して実行される既定のアクションを示しています。
  
|**SCL 評価**|**スパム信頼度の解釈**|**既定のアクション**|
|:-----|:-----|:-----|
|-1  <br/> |安全な送信者、安全な受信者、安全であると表示されている IP アドレス (信頼できるパートナー) からのメッセージであり、スパムではない  <br/> |受信者の受信トレイにメッセージを配信します。  <br/> |
|0, 1  <br/> |メッセージがスキャンされ、クリーンであると判断されたため、スパムではない  <br/> |受信者の受信トレイにメッセージを配信します。  <br/> |
|5, 6  <br/> | スパム  <br/> |受信者の迷惑メール フォルダーにメッセージを配信します。  <br/> |
|7, 8, 9  <br/> |信頼度の高いスパム  <br/> |受信者の迷惑メール フォルダーにメッセージを配信します。  <br/> |
   
> [!TIP]
> サービスでは、2、3、4、7、および 8 の scl は設定されていません。5 または 6 の SCL レベルより特定の迷惑メールとみなされ、9 の SCL レベルのスパムである保証は、疑いのある迷惑メールと見なされます。スパムと精度の高いスパムの別のアクションは、Exchange 管理センターでコンテンツ フィルター ポリシーを使用して構成できます。詳細については、[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)を参照してください。[メッセージでスパム信頼レベル (SCL) を設定するのにはメールの流れの規則を使用する](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)で説明するようトランスポート ルールを使用して特定の条件に一致するメッセージの SCL レベルを設定することもできます。7、8、または 9 の SCL が設定するのにはトランスポート ルールを使用する場合、メッセージは精度の高い迷惑メールとして扱われます。 
  
||
|:-----|
|![LinkedIn Learning の小さいアイコン](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Office 365 を初めて使用する場合は、**         LinkedIn Learning が提供する **Office 365 admins and IT pros** のための無料のビデオ コースをご覧ください。 |
   

