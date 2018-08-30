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
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
description: MIME 保護されたメッセージの送受信を許可する Exchange 2013 および Exchange オンライン組織管理者は、Outlook Web App を設定できます。SMIMEConfig コマンドレットを使用すると、Exchange 管理シェル インターフェイスを使用してこの機能を管理できます。
ms.openlocfilehash: e4bbf6cb8b0e2976b856045fc8a474bc2aa2a55a
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002514"
---
# <a name="configure-smime-settings-for-outlook-web-app"></a><span data-ttu-id="c98c3-104">Outlook Web App 用 S/MIME 設定値の構成</span><span class="sxs-lookup"><span data-stu-id="c98c3-104">Configure S/MIME settings for Outlook Web App</span></span>

<span data-ttu-id="c98c3-p102">Exchange 2013 と Exchange Online の両方の組織管理者は、S/MIME 保護メッセージの送受信が可能になるように、Outlook Web App をセット アップできます。Exchange 管理シェル インターフェイスによってこの機能を管理するには、 `SMIMEConfig` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c98c3-p102">As an organization administrator for both Exchange 2013 and Exchange Online, you can set up Outlook Web App to allow sending and receiving S/MIME-protected messages. Use the  `SMIMEConfig` cmdlet to manage this feature through the Exchange Management Shell interface.</span></span> 
  
<span data-ttu-id="c98c3-107">`get-SMIMEConfig` および  `set-SMIMEConfig` のパラメーターの詳しい説明と例など、詳細については、 [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) および [Set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx) の文書を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c98c3-107">For more information such as a detailed description of parameters and examples for  `get-SMIMEConfig` and  `set-SMIMEConfig`, see the [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) and [Set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx) documentation.</span></span> 
  
<span data-ttu-id="c98c3-p103">この手順を実行するには、シェルを使用する必要があります。 オンプレミスの Exchange 組織で Exchange 管理シェル を開く方法については、「 **Open the Shell**」を参照してください。 Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c98c3-p103">You can only use the Shell to perform this procedure. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="c98c3-111">詳細情報</span><span class="sxs-lookup"><span data-stu-id="c98c3-111">For more information</span></span>

[<span data-ttu-id="c98c3-112">S/MIME によるメッセージの署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="c98c3-112">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
  

