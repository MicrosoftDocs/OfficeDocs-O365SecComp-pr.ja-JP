---
title: Exchange Online でのメッセージの署名と暗号化の S/MIME
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: S/MIME では、電子メールを暗号化し、デジタル署名することができます。S/MIME を電子メールメッセージと共に使用すると、そのメッセージを受信したユーザーは、受信トレイに表示される内容が送信者から始まる正確なメッセージであることを確認するのに役立ちます。
ms.openlocfilehash: 41a84d5332092748f9a8cc8fe4936c39e5fd2012
ms.sourcegitcommit: 06d6e63225f912d0f3c6bb836c61eb11c1dbe97a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "30206510"
---
# <a name="smime-for-message-signing-and-encryption"></a>S/MIME によるメッセージの署名と暗号化

S/MIME (セキュリティ保護された/汎用インターネットメール内線番号) は、デジタル署名および暗号化されたメッセージを送信するための、広く使用されている方法で、正確にプロトコルでもあります。S/MIME では、電子メールを暗号化し、デジタル署名することができます。S/MIME を電子メールメッセージと共に使用すると、そのメッセージを受信したユーザーは、受信トレイに表示される内容が送信者から始まる正確なメッセージであることを確認するのに役立ちます。また、メッセージを受信したユーザーが特定の送信者からのメッセージではなく、送信者として偽装していることを確認できるようにすることもできます。これを行うために、S/MIME は認証、メッセージの整合性、送信元の否認不可 (デジタル署名を使用) などの暗号化セキュリティサービスを提供します。また、電子メールメッセージのプライバシーとデータセキュリティ (暗号化を使用) を強化するのにも役に立ちます。電子メールのコンテキストでの s/mime の履歴とアーキテクチャについての詳細な背景情報については、「 [s/mime につい](https://go.microsoft.com/fwlink/?LinkID=393948)て」を参照してください。 
  
exchange 2013 SP1 または exchange Online (Office 365 の一部) にメールボックスがある場合は、管理者として、組織の S/MIME ベースのセキュリティを有効にすることができます。S/MIME をセットアップするには、Exchange 管理シェルと共にリンクされているトピックのガイダンスを使用します。サポートされているバージョンの Outlook または ActiveSync で S/MIME を使用するには、exchange 2013 SP1 または exchange Online を使用して、組織内のユーザーに、署名と暗号化のために発行された証明書と、オンプレミスの Active Directory に公開されたデータを含める必要があります。ドメインサービス (AD DS)。AD DS は、インターネット上のリモート施設またはクラウドベースのサービスではなく、自分が管理する物理的な場所にあるコンピューター上に配置する必要があります。AD DS の詳細については、「 [Active Directory ドメインサービス](https://go.microsoft.com/fwlink/?LinkID=394064)」を参照してください。
  
## <a name="supported-scenarios-and-technical-considerations"></a>サポートされるシナリオと技術的な考慮事項
<a name="sectionSection0"> </a>

次の任意のエンドポイントで機能するように S/MIME をセットアップできます。 
  
- Outlook 2010 以降
    
- Web 上の Outlook (旧称 Outlook Web App)
    
- Exchange ActiveSync (EAS)
    
これらの各エンドポイントに S/MIME をセットアップする手順は、どのエンドポイントを選択するかにより、若干異なってきます。一般的には、次の作業をする必要があります。
  
- Windows ベースの証明機関をインストールし、S/MIME 証明書を発行するための公開キー基盤を設定します。サードパーティの証明書プロバイダーによって発行された証明書もサポートされています。詳細については、「 [Active Directory 証明書サービスの概要](https://technet.microsoft.com/library/hh831740.aspx)」を参照してください。
    
- UserSMIMECertificate および/または UserCertificate 属性の社内 AD DS アカウントでユーザー証明書を発行します。
    
- Exchange Online 組織の場合は、適切なバージョンの DirSync を使用して、ユーザー証明書を AD DS から Azure Active Directory に同期させます。これらの証明書は、Azure Active directory から Exchange Online ディレクトリに同期され、受信者へのメッセージの暗号化時に使用されます。
    
- S/MIME を検証するために、仮想証明書コレクションを設定します。この情報は、web 上の outlook (旧称 outlook on the web) で、電子メールの署名を検証し、信頼できる証明書によって署名されていることを確認するときに使用されます。
    
- S/MIME を使用する Outlook エンド ポイントまたは EAS エンド ポイントを設定します。 
    
## <a name="setup-smime-with-outlook-on-the-web"></a>Outlook on the web で S/MIME をセットアップする
<a name="sectionSection1"> </a>

Outlook on the web を使用して Exchange Online の S/MIME をセットアップするには、次の主要な手順を実行します。
  
1. [Configure S/MIME settings for Outlook on the web](configure-s-mime-settings-for-outlook-web-app.md)
    
2. [S/MIME を検証するための仮想証明書コレクションを設定する](set-up-virtual-certificate-collection-to-validate-s-mime.md)
    
3. [S/MIME 用にユーザー証明書を Office 365 に同期させる](sync-user-certificates-to-office-365-for-s-mime.md)この手順は、Exchange Online にのみ適用されます。 
    
## <a name="related-message-encryption-technologies"></a>関連するメッセージ暗号化テクノロジ
<a name="sectionSection2"> </a>

メッセージセキュリティがより重要になると、管理者はセキュリティで保護されたメッセージングの原則と概念を理解する必要があります。S/MIME などのさまざまな保護関連テクノロジが利用可能になったため、この点を理解することは特に重要です。s/mime の詳細と、電子メールのコンテキストでの動作の詳細については、「 [s/mime につい](https://go.microsoft.com/fwlink/?LinkID=393948)て」を参照してください。さまざまな暗号化テクノロジが連携して、保存中のメッセージと送信中のメッセージに対する保護を提供します。S/MIME は、次のテクノロジと同時に機能しますが、それらに依存するものではありません。
  
> **トランスポート層セキュリティ (TLS)** は、盗聴防止に役立てるために電子メール サーバー間のトンネルまたはルートを暗号化します。 
    
> **Secure Sockets Layer (SSL)** は、電子メール クライアントと Office 365 サーバーとの間の接続を暗号化します。 
    
> **BitLocker**は、データセンターのハードディスク上のデータを暗号化して、第三者が許可されていないアクセス権を取得した場合でも読み取りできないようにします。 
    
### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME と Office 365 のメッセージ暗号化との比較

S/MIME には、企業間および企業間の状況でよく使用される証明書と発行のインフラストラクチャが必要です。ユーザーは S/MIME の暗号化キーを制御し、送信する各メッセージにそれらを使用するかどうかを選択できます。Outlook などの電子メールプログラムは、信頼できるルート証明機関の場所を検索して、デジタル署名と署名の検証を実行します。Office 365 Message encryption は、個々のユーザーではなく、組織内外のすべてのユーザーに送信されるメールを暗号化するために、管理者が構成できるポリシーベースの暗号化サービスです。Azure Rights Management (RMS) 上に構築されているオンラインサービスであり、公開キー基盤に依存していません。Office 365 メッセージの暗号化では、組織のブランドを使用してメールをカスタマイズする機能など、追加機能も提供されます。office 365 メッセージの暗号化の詳細については、「 [office 365 message encryption](https://go.microsoft.com/fwlink/?LinkID=392525)」を参照してください。
  
## <a name="more-information"></a>詳細情報
<a name="sectionSection3"> </a>

[Outlook on the web](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)
  
[セキュリティで保護されたメール (2000)](https://technet.microsoft.com/en-us/library/cc962043.aspx)
  

