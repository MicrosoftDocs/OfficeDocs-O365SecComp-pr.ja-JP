---
title: S/MIME 用にユーザー証明書を Office 365 に同期させる
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: S/MIME 保護されたメッセージを送信するには、適切な証明書をセットアップする必要があります。Exchange Online 経由で暗号化メッセージを送信するために、送信者の電子メール プログラムでは受信者の公開証明書を使用してメッセージを暗号化します。この公開 X.509 証明書を Office 365 に公開する必要があります。
ms.openlocfilehash: ad58b5663eaadf771ed1518edc01ce2f765f5202
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600690"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>S/MIME 用にユーザー証明書を Office 365 に同期する

すべてのユーザーが S/MIME で保護されたメッセージを Exchange Online で送信できるようにするには、適切な証明書をセットアップする必要があります。 Exchange Online を介して暗号化されたメッセージを送信する場合、送信者の電子メールアプリは受信者のパブリック証明書を使用してメッセージを暗号化します。 この公開 X.509 証明書を Office 365 に公開する必要があります。

## <a name="to-sync-certificates-that-support-smime"></a>S/MIME をサポートする証明書を同期するには

証明書を発行して、ローカルの Active Directory ドメイン サービスで公開することによって、S/MIME のセットアップを開始します。 Exchange Server での証明書の管理の詳細については、「 [Digital certificates AND SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx)」を参照してください。

証明書が公開されたら、Azure Active Directory 同期ツール を使用してオンプレミスの Exchange 環境から Office 365 にユーザー データを同期します。このプロセスの詳細については、「[DirSync: Directory 同期ツールのバージョンのリリース履歴](https://go.microsoft.com/fwlink/p/?LinkId=392587)」を参照してください。

S/MIME 用に他のディレクトリデータを同期することに加えて、ツールは各ユーザーオブジェクトの**Usercertificate**属性と**userSMIMECertificate**属性を同期し、データを使用してメッセージの署名と暗号化を行うことができるようにします。

## <a name="more-information"></a>詳細

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)

[Azure Active Directory 同期ツール](https://go.microsoft.com/fwlink/p/?LinkId=392587)
