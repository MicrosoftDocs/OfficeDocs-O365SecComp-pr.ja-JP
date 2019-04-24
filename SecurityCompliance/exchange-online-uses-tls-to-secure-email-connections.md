---
title: Office 365 で電子メール接続をセキュリティで保護するために、Exchange Online が TLS を使用する方法
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Exchange Online および Office 365 で、トランスポート層セキュリティ (TLS) とフォワード機密性 (FS) を使用して電子メール通信をセキュリティで保護する方法について説明します。 また、Microsoft によって発行された Exchange Online 用の証明書に関する情報も取得します。
ms.openlocfilehash: e80f477c807f3a7ad5f751e0987b191024c816d9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255635"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections-in-office-365"></a>Office 365 で電子メール接続をセキュリティで保護するために、Exchange Online が TLS を使用する方法

Exchange Online および Office 365 で、トランスポート層セキュリティ (TLS) とフォワード機密性 (FS) を使用して電子メール通信をセキュリティで保護する方法について説明します。 また、Microsoft によって発行された Exchange Online 用の証明書に関する情報も提供します。
  
## <a name="tls-basics-for-office-365-and-exchange-online"></a>Office 365 および Exchange Online の TLS の基礎

トランスポート層セキュリティ (TLS) と、TLS に先立つ SSL は、セキュリティ証明書を使用してコンピューター間の接続を暗号化することによって、ネットワークを介した通信のセキュリティを確保する暗号化プロトコルです。 TLS は ssl (Secure Sockets layer) に優先され、ssl 3.1 と呼ばれることがよくあります。 exchange Online の場合、TLS を使用して、exchange サーバーと、社内 exchange サーバーや受信者のメールサーバーなどの他のサーバーとの間の接続を暗号化します。 接続が暗号化されると、その接続を介して送信されるすべてのデータが暗号化チャネル経由で送信されます。 ただし、TLS で暗号化された接続を介して送信されたメッセージを転送する場合、そのメッセージは必ずしも暗号化されません。 これは、単純に言うと、TLS はメッセージを暗号化せず、接続だけであるからです。
  
メッセージを暗号化する場合は、メッセージの内容を暗号化する暗号化テクノロジを使用する必要があります (たとえば、Office メッセージの暗号化など)。 office 365 のメッセージ暗号化オプションの詳細については、「 [office 365 の電子メールの暗号化](email-encryption.md)」および「 [office 365 message encryption (OME)](ome.md) 」を参照してください。 
  
Office 365 とオンプレミスの組織またはパートナーなどの他の組織との間の通信のセキュリティで保護されたチャネルを設定する必要がある場合は、TLS を使用することをお勧めします。 Exchange Online は常に tls を使用して電子メールをセキュリティで保護しようとしますが、相手が tls セキュリティを提供していない場合は常にこれを実行することはできません。 *コネクタ*を使用して、オンプレミスのサーバーまたは重要なパートナーへのすべてのメールをセキュリティで保護する方法については、読み続けてください。 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>exchange online のお客様と exchange online の間で TLS を使用する方法

exchange online サーバーは、常に、TLS 1.2 を使用してデータセンター内の他の exchange online サーバーへの接続を暗号化します。 Office 365 組織内の受信者にメールを送信すると、その電子メールは、TLS を使用して暗号化された接続を介して自動的に送信されます。 また、他の Office 365 のお客様に送信するすべての電子メールは、TLS を使用して暗号化された接続を介して送信され、Forward 機密性を使用してセキュリティ保護されます。
  
## <a name="how-office-365-uses-tls-between-office-365-and-external-trusted-partners"></a>office 365 が office 365 と外部の信頼されたパートナーの間で TLS を使用する方法

既定では、Exchange Online は常に便宜的な TLS を使用します。 そのため、Exchange Online は常に最も安全なバージョンの tls を使用して接続を暗号化しようとし、両方の当事者が同意することが検出されるまで、tls 暗号のリストを下に移動します。 その受信者宛てのメッセージがセキュリティで保護された接続を介してのみ送信されるように Exchange Online を構成していない限り、受信者の組織が TLS 暗号化をサポートしていない場合、既定ではメッセージは暗号化されずに送信されます。 多くの企業にとって、便宜的な TLS は十分です。 ただし、医療、バンキング、行政機関などのコンプライアンス要件があるビジネスでは、Exchange Online を構成して、TLS を要求するか強制することができます。 手順については、「 [Office 365 でコネクタを使用してメールフローを構成する](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)」を参照してください。
  
組織と信頼できるパートナー組織との間で tls を構成する場合、Exchange Online は強制的な tls を使用して信頼された通信チャネルを作成できます。 強制 TLS では、パートナー組織がメールを送信するために、セキュリティ証明書を使用して Exchange Online に対して認証を行う必要があります。 そのためには、パートナーが自分の証明書を管理する必要があります。 Exchange Online では、コネクタを使用して、受信者の電子メールプロバイダーに到着する前に、承認されていないアクセスから送信されたメッセージを保護します。 コネクタを使用してメールフローを構成する方法については、「 [configure mail flow using コネクタ using Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)」を参照してください。
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS およびハイブリッド Exchange Server の展開

ハイブリッド exchange 展開を管理している場合、オンプレミスの exchange サーバーは、office 365 にのみメールボックスがある受信者にメールを送信するために、セキュリティ証明書を使用して office 365 に認証する必要があります。 そのため、オンプレミスの Exchange サーバーの独自のセキュリティ証明書を管理する必要があります。 また、これらのサーバー証明書を安全に保存および維持する必要があります。 ハイブリッド展開での証明書の管理の詳細については、「[ハイブリッド展開の証明書要件](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx)」を参照してください。
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Office 365 で Exchange Online の強制 TLS をセットアップする方法

Exchange Online のお客様の場合、すべての送受信メールをセキュリティで保護するために強制的に tls を使用するには、tls を必要とする複数のコネクタを設定する必要があります。 ユーザーのメールボックスに送信される電子メール用のコネクタと、ユーザーのメールボックスから送信される電子メール用のコネクタが1つ必要になります。 Office 365 の Exchange 管理センターでこれらのコネクタを作成します。 手順については、「 [Office 365 でコネクタを使用してメールフローを構成する](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)」を参照してください。
  
## <a name="tls-certificate-information-for-exchange-online"></a>Exchange Online の TLS 証明書情報

次の表では、Exchange Online で使用される証明書情報について説明します。 ビジネスパートナーが電子メールサーバーで強制的に TLS を設定している場合は、この情報をユーザーに提供する必要があります。 セキュリティ上の理由から、証明書は随時変更されることに注意してください。 データセンター内での証明書への更新をロールアウトしました。 新しい証明書は2018年9月3日から有効になっています。
  
 **2018年9月3日から有効な現在の証明書情報**
  
|**Attribute**|**値**|
|:-----|:-----|
|証明機関のルート発行者  <br/> |globalsign ルート CA – R1 <br/> |
|証明書の名前  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織単位  <br/> |  <br/> |
|証明書キーの強度  <br/> |2048  <br/> |
   
 **非推奨の証明書情報は、2018年9月3日まで有効です。**
  
移行を円滑に行うために、しばらくの間、参照用の古い証明書情報を引き続き提供する予定です。ただし、現時点では現在の証明書情報を使用する必要があります。
  
****

|**Attribute**|**値**|
|:-----|:-----|
|証明機関のルート発行者  <br/> |Baltimore CyberTrust Root  <br/> |
|証明書の名前  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織単位  <br/> |Microsoft Corporation  <br/> |
|証明書キーの強度  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>新しい Exchange Online 証明書の準備

新しい証明書は、Exchange Online で使用される以前の証明書から、別の証明機関 (CA) によって発行されます。 そのため、新しい証明書を使用するためにいくつかの操作を実行する必要があります。

新しい証明書では、証明書の検証の一環として、新しい CA のエンドポイントに接続する必要があります。 これを怠ると、メールフローが悪影響を受けてしまう可能性があります。 メールサーバーに特定の宛先のみが接続できるようにするファイアウォールを使用してメールサーバーを保護する場合は、サーバーが新しい証明書を検証できるかどうかを確認する必要があります。 サーバーが新しい証明書を使用できることを確認するには、次の手順を実行します。

1. Windows PowerShell を使用してローカルの Exchange サーバーに接続し、次のコマンドを実行します。  
  `certutil -URL http://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. 表示されるウィンドウで、[**取得**] を選択します。
3. ユーティリティがチェックを完了すると、状態が返されます。 状態が **[OK]** と表示されている場合、メールサーバーは新しい証明書を正常に検証できます。 それ以外の場合は、接続が失敗する原因を特定する必要があります。 多くの場合、ファイアウォールの設定を更新する必要があります。 アクセスする必要があるエンドポイントの完全なリストは次のとおりです。
    - ocsp.globalsign.com
     - crl.globalsign.com
     - secure.globalsign.com   

通常、Windows Update を使用してルート証明書の更新を自動的に受信します。 ただし、一部の展開では、これらの更新が自動的に実行されないようにするための追加のセキュリティがあります。 Windows Update でルート証明書を自動更新できない、ロックダウンされたこれらの展開では、次の手順を実行して、正しいルート CA 証明書がインストールされていることを確認する必要があります。
1.  Windows PowerShell を使用してローカルの Exchange サーバーに接続し、次のコマンドを実行します。  
  `certmgr.msc`
2. [**信頼されたルート証明機関/証明書**] の下で、新しい証明書が表示されていることを確認します。

## <a name="get-more-information-about-tls-and-office-365"></a>TLS と Office 365 の詳細情報を取得する

サポートされている暗号スイートの一覧については、「 [Office 365 の暗号化に関するテクニカルリファレンスの詳細](technical-reference-details-about-encryption.md)」を参照してください。
  
[パートナー組織とのセキュリティで保護されたメール フロー用のコネクタを設定する](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[電子メール セキュリティを強化したコネクタ](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Office 365 での暗号化](encryption.md)
  

