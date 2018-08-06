---
title: Outlook Web App 用 S/MIME 設定値の構成
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/8/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
description: MIME 保護されたメッセージの送受信を許可する Exchange 2013 および Exchange オンライン組織管理者は、Outlook Web App を設定できます。SMIMEConfig コマンドレットを使用すると、Exchange 管理シェル インターフェイスを使用してこの機能を管理できます。
ms.openlocfilehash: d351129c7e12a66b530e0e4f82107728fd8387ae
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027134"
---
# <a name="configure-smime-settings-for-outlook-web-app"></a>Outlook Web App 用 S/MIME 設定値の構成

Exchange 2013 と Exchange Online の両方の組織管理者は、S/MIME 保護メッセージの送受信が可能になるように、Outlook Web App をセット アップできます。Exchange 管理シェル インターフェイスによってこの機能を管理するには、 `SMIMEConfig` コマンドレットを使用します。 
  
`get-SMIMEConfig` および  `set-SMIMEConfig` のパラメーターの詳しい説明と例など、詳細については、 [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) および [Set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx) の文書を参照してください。 
  
この手順を実行するには、シェルを使用する必要があります。 オンプレミスの Exchange 組織で Exchange 管理シェル を開く方法については、「 **Open the Shell**」を参照してください。 Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。
  
## <a name="for-more-information"></a>詳細情報

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)
  

