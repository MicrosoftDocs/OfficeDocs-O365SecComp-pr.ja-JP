---
title: Outlook on the web を使用して、Exchange Online の S/MIME 設定を構成する
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange online の Outlook on the web で S/MIME 設定を表示および構成するために必要な Exchange Online 管理者の簡単な説明。
ms.openlocfilehash: 6e390e377369dc0de73d5e063a6a21fd549c3bef
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600133"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Outlook on the web を使用して、Exchange Online の S/MIME 設定を構成する

Exchange Online の管理者は、S/MIME で保護されたメッセージを送受信できるように、Outlook on the web (旧称 Outlook Web App) をセットアップできます。 Exchange Online PowerShell でこの機能を表示および管理するには、 **-smimeconfig**コマンドレットおよび**Set-smimeconfig**コマンドレットを使用します。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。

構文およびパラメーターの詳細については、「 [Get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) 」および「 [Set-smimeconfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx)」を参照してください。

## <a name="considerations-for-chrome"></a>Chrome の考慮事項

Google Chrome web ブラウザーで Outlook on the web で S/MIME を使用するには、ユーザー (または別の管理者) が**Extensioninstallforcelist**という名前の Chromium ポリシーを設定および構成して、Microsoft S/mime 拡張機能を Chrome にインストールする必要があります。 ポリシーの値は`maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`です。 このポリシーを適用するには、ドメインに参加しているコンピューターが必要であるため、Chrome で S/MIME を使用するとドメインに参加しているコンピューターが効果的に必要になります。

**Extensioninstallforcelist**ポリシーの詳細については、「 [extensioninstallforcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist)」を参照してください。

この手順は、Chrome を使用するための前提条件です。ユーザーによってインストールされた S/MIME コントロールは置き換えられません。 S/MIME の初めての使用時に、S/MIME コントロールをダウンロードして、web 上の Outlook にインストールするようにユーザーに求められます。 または、ユーザーが Outlook on the web 設定で**S/MIME**を事前に参照して、コントロールのダウンロードリンクを取得することができます。

## <a name="for-more-information"></a>関連情報

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)
