---
title: S/MIME によるメッセージの署名と暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 秒/MIME を使用すると、電子メールの暗号化し、デジタル署名を有効にできます。電子メール メッセージに S/MIME を使用すると、受信トレイに表示される送信者を開始する正確なメッセージを特定するのには、そのメッセージを受信する人に役立ちます。
ms.openlocfilehash: 3ce95132476417df8949cdc12f2d825047f6b76d
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027594"
---
# <a name="smime-for-message-signing-and-encryption"></a>S/MIME によるメッセージの署名と暗号化

S/MIME (Secure Multipurpose とインターネット メールの拡張機能) は、広く受け入れられているメソッド、またはより正確には、プロトコル、デジタル署名され、暗号化されたメッセージです。秒/MIME を使用すると、電子メールの暗号化し、デジタル署名を有効にできます。電子メール メッセージに S/MIME を使用すると、受信トレイに表示される送信者を開始する正確なメッセージを特定するのには、そのメッセージを受信する人に役立ちます。なることを確認するメッセージを受信するユーザーと、特定の送信者から送信元を装って誰かからではなく、メッセージが付属しています。これを行うには、秒/MIME は、認証、メッセージの整合性、および否認 (デジタル署名を使用して) 元の暗号化セキュリティ サービスを提供します。高めることにつながりますプライバシーとデータ セキュリティ (暗号化を使用して) の電子メッセージングです。履歴と S/MIME の電子メールのコンテキストでのアーキテクチャに関する詳細については、[理解すると、S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)を参照してください。 
  
管理者は、Exchange 2013 の SP1 または Exchange Online、Office 365 の一部のいずれかのメールボックスがある場合、組織の MIME ベースのセキュリティを有効にできます。秒/MIME を設定するのには Exchange 管理シェルとは、ここにリンクされているトピックのガイダンスを使用します。署名と暗号化の目的で発行された証明書と、オンプレミスの Active Directory に公開するデータ サポート対象のバージョンの Outlook または Exchange 2013 SP1 または Exchange Online では、いずれかで、ActiveSync で S/MIME を使用するには、組織内のユーザーが必要ドメイン サービス (AD DS)。AD DS は、物理的な場所を制御することで、リモート ・ サイトまたはインターネット上のどこかにクラウド ベースのサービスではなく、コンピューター上になければなりません。AD DS の詳細については、 [Active Directory ドメイン サービス](https://go.microsoft.com/fwlink/?LinkID=394064)を参照してください。
  
## <a name="supported-scenarios-and-technical-considerations"></a>サポートされるシナリオと技術的な考慮事項
<a name="sectionSection0"> </a>

組織は、Exchange 2013 SP1 または Exchange Online を使用する場合は、次の端点のいずれかで動作する、秒/MIME を設定できます。 
  
- Outlook 2010
    
- Outlook 2013
    
- Outlook Web App
    
- Exchange ActiveSync (EAS)
    
これらの各エンドポイントに S/MIME をセットアップする手順は、どのエンドポイントを選択するかにより、若干異なってきます。一般的には、次の作業をする必要があります。
  
- Windows ベースの証明機関をインストールし、S/MIME 証明書を発行する公開キー基盤を設定します。サード パーティの証明書プロバイダーによって発行された証明書もサポートされています。詳細については、 [Active Directory 証明書サービスの概要](https://technet.microsoft.com/library/hh831740.aspx)を参照してください。
    
- UserSMIMECertificate および/または UserCertificate 属性の社内 AD DS アカウントでユーザー証明書を発行します。
    
- Exchange Online 組織では、Azure Active Directory への AD DS からユーザー証明書をディレクトリ同期の適切なバージョンを使用して同期します。これらの証明書が Exchange のオンライン ディレクトリに同期 Azure Active Directory から取得し、し、受信者にメッセージを暗号化するときに使用されます。
    
- S/MIME を検証するためには、仮想の証明書のコレクションを設定します。この情報は、電子メールの署名を検証する際に OWA により使用され、そのメールが信頼される証明書により署名されたことが確認されます。
    
- S/MIME を使用する Outlook エンド ポイントまたは EA エンド ポイントを設定します。 
    
## <a name="setup-smime-with-outlook-web-app"></a>Outlook Web App で S/MIME を設定する
<a name="sectionSection1"> </a>

Exchange 2013 SP1 または Exchange Online では、Outlook Web App の S/MIME を設定するには、次のキーの手順が含まれます。
  
1. [Outlook Web App 用 S/MIME 設定値の構成](configure-s-mime-settings-for-outlook-web-app.md)
    
2. [S/MIME を検証するための仮想証明書コレクションをセットアップする](set-up-virtual-certificate-collection-to-validate-s-mime.md)
    
3. [秒/MIME の Office 365 にユーザー証明書を同期](sync-user-certificates-to-office-365-for-s-mime.md)この手順は、Exchange Online にのみ適用されます。 
    
## <a name="related-message-encryption-technologies"></a>関連するメッセージ暗号化テクノロジ
<a name="sectionSection2"> </a>

メッセージのセキュリティがさらに重要になると、管理者は、原則とセキュリティで保護されたメッセージングの概念を理解しておく必要があります。増大するさまざまな保護に関連するテクノロジ、S-MIME など使用可能になったため、この理解は特に重要です。S/MIME および電子メールのコンテキストでのしくみについて理解を深めるには、[理解すると、S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)を参照してください。さまざまな暗号化テクノロジは、残りの部分と、転送中のメッセージの保護を提供する共同作業です。秒/MIME では、次のテクノロジを同時に操作できますが、それらに依存しません。
  
> **トランスポート層セキュリティ (TLS)** は、盗聴防止に役立てるために電子メール サーバー間のトンネルまたはルートを暗号化します。 
    
> **Secure Sockets Layer (SSL)** は、電子メール クライアントと Office 365 サーバーとの間の接続を暗号化します。 
    
> **BitLocker**は、不正なアクセスを取得誰かがある場合、読み取ることができないように、データ ・ センターのハード ドライブ上のデータを暗号化します。 
    
### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME と Office 365 のメッセージ暗号化との比較

秒/MIME では、企業間および企業消費者の状況で使用される証明書と公開のインフラストラクチャが必要です。ユーザーは、S/MIME で暗号化キーを制御し、各メッセージの送信に使用するかどうかを選択できます。Outlook などの電子メール プログラムでは、デジタル署名と署名の検証を実行する信頼されたルート証明機関の場所を検索します。Office 365 メッセージの暗号化は、管理者、および各ユーザーではなく、組織内または組織の外部ユーザーに送信されたメールを暗号化するために、構成可能なポリシー ・ ベースの暗号化サービスです。Azure 権利管理 (RM) の構築および公開キー基盤に依存しないオンライン サービスすることをお勧めします。Office 365 のメッセージの暗号化では、組織のブランドとのメールをカスタマイズする機能などの追加機能も提供します。Office 365 のメッセージの暗号化の詳細については、 [Office 365 のメッセージの暗号化](https://go.microsoft.com/fwlink/?LinkID=392525)を参照してください。
  
## <a name="more-information"></a>詳細情報
<a name="sectionSection3"> </a>

[Outlook Web App](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)
  
[セキュリティで保護されたメール (2000)](https://technet.microsoft.com/en-us/library/cc962043.aspx)
  

