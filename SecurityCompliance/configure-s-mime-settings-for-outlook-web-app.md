---
title: Outlook on the web を使用して、Exchange Online の S/MIME 設定を構成する
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: exchange online の Outlook on the web で S/MIME 設定を表示および構成するために必要な exchange online 管理者の簡単な説明。
ms.openlocfilehash: 74d2f37f0cabc0b49abdd78d2a10928b543fd615
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295360"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Outlook on the web を使用して、Exchange Online の S/MIME 設定を構成する

Exchange Online の管理者は、S/MIME で保護されたメッセージを送受信できるように、outlook on the web (旧称 outlook web App) をセットアップできます。Exchange Online PowerShell でこの機能を表示および管理するには、 **-smimeconfig**コマンドレットおよび**Set-smimeconfig**コマンドレットを使用します。exchange online powershell に接続するには、「 [exchange online powershell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。

構文およびパラメーターの詳細については、「 [Get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) 」および「 [Set-smimeconfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx)」を参照してください。

## <a name="considerations-for-chrome"></a>Chrome の考慮事項

Google Chrome web ブラウザーで Outlook on the web で S/mime を使用するには、ユーザー (または別の管理者) が**extensioninstallforcelist**という名前の Chromium ポリシーを設定および構成して、Microsoft S/mime 拡張機能を Chrome にインストールする必要があります。このポリシーでは、次`<extension-id>;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`の構文を使用`maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`する必要があります。例:。この手順は、Chrome を使用するための前提条件です。ユーザーによってインストールされた S/MIME コントロールは置き換えられません。**extensioninstallforcelist**ポリシーの詳細については、「 [extensioninstallforcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist)」を参照してください。

## <a name="for-more-information"></a>詳細情報

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)
