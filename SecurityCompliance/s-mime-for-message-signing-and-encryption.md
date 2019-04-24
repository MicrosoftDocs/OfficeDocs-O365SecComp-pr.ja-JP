---
title: Exchange Online でのメッセージの署名と暗号化の S/MIME
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 管理者は、Exchange Online で S/MIME を使用する方法について説明します。
ms.openlocfilehash: 7c7225efce247928e19946e695c19931f198ae32
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261385"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>Exchange Online でのメッセージの署名と暗号化の S/MIME

S/MIME (セキュリティ保護された/汎用インターネットメール内線番号) は、デジタル署名および暗号化されたメッセージを送信するための、広く使用されている方法 (厳密にはプロトコル) です。 S/MIME では電子メールを暗号化し、デジタル署名を行うことができます。 電子メール メッセージで S/MIME を使用すると、そのメッセージを受信する人は、受信トレイにあるものが送信者によって作成されたメッセージそのものであることがわかります。 また、メッセージを受信する人は、そのメッセージが確かに特定の送信者から送信されたものであり、その送信者になりすました別の誰かからのものでないこともわかります。 このために、S/MIME には認証、メッセージの整合性、発信元の否認防止 (デジタル署名を使用) などの暗号化セキュリティ サービスが用意されています。 また、これは電子メッセージングのプライバシーとデータ セキュリティ (暗号化を使用) の強化にも役立ちます。 電子メール関連での S/MIME の歴史とアーキテクチャに関する詳細な背景情報については、「[S/MIME について](https://go.microsoft.com/fwlink/?LinkID=393948)」を参照してください。

Exchange Online 管理者は、組織内のメールボックスに対して S/MIME ベースのセキュリティを有効にすることができます。 ここでリンクされているトピックのガイダンスを Exchange Online PowerShell と共に使用して、S/MIME を設定します。 サポートされている電子メールクライアントで S/MIME を使用するには、組織内のユーザーに、署名と暗号化のために発行された証明書と、オンプレミスの Active Directory ドメインサービス (AD DS) に公開されたデータを含める必要があります。 AD DS は、インターネット上のリモート施設またはクラウドベースのサービスではなく、自分が管理する物理的な場所にあるコンピューター上に配置する必要があります。 AD DS の詳細については、「 [Active Directory ドメイン サービス](https://go.microsoft.com/fwlink/?LinkID=394064)」を参照してください。

## <a name="supported-scenarios-and-technical-considerations"></a>サポートされるシナリオと技術的な考慮事項

次の任意のエンドポイントで機能するように S/MIME をセットアップできます。

- Outlook 2010 以降

- Web 上の Outlook (旧称 Outlook Web App)

- Exchange ActiveSync (EAS)

これらの各エンドポイントを使用して S/MIME をセットアップする手順は、次の手順で少し異なります。 通常は、次の手順を実行する必要があります。

- Windows ベースの証明機関をインストールし、S/MIME 証明書を発行するように公開キー基盤を設定します。 サードパーティの証明書プロバイダーによって発行された証明書もサポートされています。 詳細については、「[Active Directory 証明書サービスの概要](https://technet.microsoft.com/library/hh831740.aspx)」を参照してください。

- **UserSMIMECertificate**または**usercertificate**属性で、社内 AD DS アカウントでユーザー証明書を公開します。

- Exchange Online 組織の場合は、適切なバージョンの DirSync を使用して、ユーザー証明書を AD DS から Azure Active Directory に同期させます。 次に、これらの証明書は Azure Active Directory から Exchange Online のディレクトリに同期され、受信者へのメッセージの暗号化に使用されます。

- S/MIME を検証するためには、仮想の証明書のコレクションを設定します。この情報は、電子メールの署名を検証する際に Web 上の Outlook により使用され、そのメールが信頼される証明書により署名されたことが確認されます。

- S/MIME を使用する Outlook エンド ポイントまたは EAS エンド ポイントを設定します。

## <a name="setup-smime-with-outlook-on-the-web"></a>Outlook on the web で S/MIME をセットアップする

Outlook on the web を使用して Exchange Online の S/MIME をセットアップするには、次の主要な手順を実行します。

1. [Outlook on the web の S/MIME 設定を構成する](configure-s-mime-settings-for-outlook-web-app.md)

2. [S/MIME を検証するための仮想証明書コレクションを設定する](set-up-virtual-certificate-collection-to-validate-s-mime.md)

3. [S/MIME 用にユーザー証明書を Office 365 に同期させる](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>関連するメッセージ暗号化テクノロジ

メッセージセキュリティがより重要になると、管理者はセキュリティで保護されたメッセージングの原則と概念を理解する必要があります。 利用可能なさまざまな保護関連テクノロジ (S/MIME を含む) があるため、この点を理解することは特に重要です。 s/mime の詳細と、電子メールのコンテキストでの動作の詳細については、「 [s/mime につい](https://go.microsoft.com/fwlink/?LinkID=393948)て」を参照してください。 さまざまな暗号化テクノロジが連携して、保管されているメッセージと転送中のメッセージの保護を提供します。 S/MIME は次のようなテクノロジと同時に機能しますが、それらに依存してはいません。

- **トランスポート層セキュリティ (TLS)** は、盗聴防止に役立てるために電子メール サーバー間のトンネルまたはルートを暗号化します。

- **Secure Sockets Layer (SSL)** は、電子メール クライアントと Office 365 サーバーとの間の接続を暗号化します。

- **BitLocker**は、データセンターのハードディスク上のデータを暗号化して、第三者が許可されていないアクセス権を取得した場合でも読み取りできないようにします。

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME と Office 365 のメッセージ暗号化との比較

S/MIME には B2B (企業間取引) および B2C (企業-消費者間取引) の状況でよく使用される証明書および公開のインフラストラクチャが必要です。 ユーザーは、S/MIME で暗号化キーを制御し、送信する各メッセージにキーを使用するかどうかを選択できます。 Outlook などの電子メール プログラムはデジタル署名と署名の検証を実行するために、信頼できるルート証明機関の場所を検索します。 Office 365 のメッセージの暗号化は、組織内外の任意の受信者に送信されるメールを暗号化するための、管理者が構成できる (個々のユーザーは構成できない) ポリシー ベースの暗号化サービスです。 Azure Rights Management (RMS) 上に構築されているオンラインサービスであり、公開キー基盤に依存していません。 Office 365 メッセージの暗号化では、組織のブランドを使用してメールをカスタマイズする機能など、追加機能も提供されます。 office 365 メッセージの暗号化の詳細については、「 [office 365 message encryption](https://go.microsoft.com/fwlink/?LinkID=392525)」を参照してください。

## <a name="more-information"></a>詳細情報

[Outlook on the web](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)

[セキュリティで保護されたメール (2000)](https://technet.microsoft.com/en-us/library/cc962043.aspx)
