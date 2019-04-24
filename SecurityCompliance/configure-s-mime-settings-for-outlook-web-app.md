---
title: Outlook on the web を使用して、Exchange Online の S/MIME 設定を構成する
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: exchange online の Outlook on the web で S/MIME 設定を表示および構成するために必要な exchange online 管理者の簡単な説明。
ms.openlocfilehash: d890b7f39d16d8c0f3866d5ff0024fe31160af6b
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258995"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="cd39e-103">Outlook on the web を使用して、Exchange Online の S/MIME 設定を構成する</span><span class="sxs-lookup"><span data-stu-id="cd39e-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="cd39e-104">Exchange Online の管理者は、S/MIME で保護されたメッセージを送受信できるように、outlook on the web (旧称 outlook web App) をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="cd39e-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="cd39e-105">Exchange Online PowerShell でこの機能を表示および管理するには、 **-smimeconfig**コマンドレットおよび**Set-smimeconfig**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd39e-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="cd39e-106">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd39e-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

<span data-ttu-id="cd39e-107">構文およびパラメーターの詳細については、「 [Get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) 」および「 [Set-smimeconfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd39e-107">For detailed syntax and parameter information, see [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) and [Set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="cd39e-108">Chrome の考慮事項</span><span class="sxs-lookup"><span data-stu-id="cd39e-108">Considerations for Chrome</span></span>

<span data-ttu-id="cd39e-109">Google Chrome web ブラウザーで Outlook on the web で S/mime を使用するには、ユーザー (または別の管理者) が**extensioninstallforcelist**という名前の Chromium ポリシーを設定および構成して、Microsoft S/mime 拡張機能を Chrome にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd39e-109">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="cd39e-110">このポリシーでは、次`<extension-id>;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`の構文を使用`maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`する必要があります。例:。</span><span class="sxs-lookup"><span data-stu-id="cd39e-110">The policy should use the syntax: `<extension-id>;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` For example: `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="cd39e-111">このポリシーを適用するには、ドメインに参加しているコンピューターが必要であるため、Chrome で S/MIME を使用するとドメインに参加しているコンピューターが効果的に必要になります。</span><span class="sxs-lookup"><span data-stu-id="cd39e-111">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="cd39e-112">この手順は、Chrome を使用するための前提条件です。ユーザーによってインストールされた S/MIME コントロールは置き換えられません。</span><span class="sxs-lookup"><span data-stu-id="cd39e-112">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="cd39e-113">**extensioninstallforcelist**ポリシーの詳細については、「 [extensioninstallforcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd39e-113">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="cd39e-114">関連情報</span><span class="sxs-lookup"><span data-stu-id="cd39e-114">For more information</span></span>

[<span data-ttu-id="cd39e-115">S/MIME によるメッセージの署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="cd39e-115">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
