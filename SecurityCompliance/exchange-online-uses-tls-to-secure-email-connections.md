---
title: Exchange Online で電子メール接続をセキュリティで保護するために Office 365 で TLS を使用する方法
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
description: Exchange Online と Office 365 の使用方法トランスポート層セキュリティ (TLS) と前方秘密 (FS) の電子メールによる通信をセキュリティで保護するかを説明します。Exchange Online は、Microsoft が発行した証明書に関する情報を取得します。
ms.openlocfilehash: 079a6f574838f5710dbbbcb53726799abfae1d3a
ms.sourcegitcommit: ddfa0ac1f8ef95a78dcc1468241ef29363d56b5b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "23520146"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections-in-office-365"></a>Exchange Online で電子メール接続をセキュリティで保護するために Office 365 で TLS を使用する方法

Exchange Online と Office 365 の使用方法トランスポート層セキュリティ (TLS) と前方秘密 (FS) の電子メールによる通信をセキュリティで保護するかを説明します。Exchange Online は、Microsoft が発行した証明書に関する情報を提供します。
  
## <a name="tls-basics-for-office-365-and-exchange-online"></a>Office 365 および Exchange Online の TLS の基礎

トランスポート層セキュリティ (TLS) と SSL、TLS の前に付属しているは、コンピューター間の接続を暗号化するためにセキュリティ証明書を使用してネットワーク経由で通信をセキュリティで保護する暗号化プロトコルです。TLS では、Secure Sockets Layer (SSL) を優先して、SSL 3.1 とも呼ば。Exchange online では、Exchange サーバーと、オンプレミスの Exchange サーバーまたは受信者のメール サーバーなどの他のサーバーとの間、Exchange サーバーとの間の接続、接続を暗号化するために TLS を使用します。接続が暗号化されると、その接続を介して送信されるすべてのデータは暗号化されたチャネルを通じて送信されます。ただし、TLS で暗号化された接続を介して送信されたメッセージを転送する場合は、そのメッセージは暗号化とは限りませんはありません。これは、TLS では、簡単に言えば、接続だけで、メッセージは暗号化されません。
  
メッセージを暗号化する場合は、メッセージの内容を暗号化する、Office Message Encryption のような暗号化技術を使用する必要があります。Office 365 におけるメッセージ暗号化のオプションについては、「[Email encryption in Office 365](email-encryption.md)」と「[Office 365 Message Encryption (OME)](ome.md)」をご覧ください。 
  
Office 365 と設置型の組織またはパートナーなど、別の組織との間の通信のセキュリティで保護されたチャネルを設定する必要がある場合に、TLS を使用することをお勧めします。Exchange オンライン常に最初に TLS を使用して電子メールをセキュリティで保護しようとしていますが、常にこれができない場合は、他のパーティでは、TLS のセキュリ ティーを提供していません。*コネクタ*を使用して、オンプレミスのサーバーや重要なパートナーにすべてのメールをセキュリティで保護する方法について読んでをしてください。 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Exchange Online で Exchange Online 顧客間において TLS を使用する方法

Exchange Online サーバーでは、Microsoft のデータセンター内にある他の Exchange Online サーバーに対する接続を TLS 1.2 を使用して常に暗号化します。Office 365 組織内で電子メールを受信側に送信すると、そのメールは TLS を使用して暗号化された接続を介して自動的に送信されます。また、他の Office 365 の顧客に送信するすべての電子メールは TSL を使用して暗号化された接続を使用して送信され、FS (Forward Secrecy) を使用してセキュリティ保護されます。
  
## <a name="how-office-365-uses-tls-between-office-365-and-external-trusted-partners"></a>Office 365 が Office 365 と、外部の信頼できるパートナーとの間の TLS を使用する方法

既定では、Exchange オンライン常に TLS を使用便宜的です。これは、Exchange オンライン常に最初に、最もセキュリティで保護された TLS のバージョンとの接続を暗号化しようとしていますし正常に機能 TLS 暗号形式の一覧を下方向いずれかの当事者の双方が同意するものが見つかるまでを意味します。した場合、その受信者にメッセージをセキュリティで保護された接続を介してのみ送信されるようにするのには Exchange のオンラインでない限り、既定でメッセージが暗号化されずに送信受信者の組織は、TLS 暗号化をサポートしない場合。便宜的な TLS は、ほとんどの企業にとって十分です。ただし、医療などのコンプライアンス要件、銀行、政府機関のあるビジネスの構成を必要とすると、Exchange のオンラインしたり、TLS を強制できます。手順については、 [Office 365 のコネクタを使用してメールの流れを構成する](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)を参照してください。
  
組織と信頼されたパートナー組織間で TLS を構成する場合は、Exchange Online が TLS を使用して強制信頼された通信チャネルを作成します。強制 TLS では、パートナーの組織にメールを送信するためにセキュリティ証明書を Exchange Online に認証が必要です。パートナーは、これを実行するために独自の証明書を管理する必要があります。Exchange online では、受信者の電子メール プロバイダーに到達する前に、不正なアクセスから送信するメッセージを保護するためにコネクタを使用します。コネクタを使用してメール フローを構成する方法の詳細については、 [Office 365 のコネクタを使用してメールの流れを構成する](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)を参照してください。
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS と Exchange Server ハイブリッド展開

ハイブリッドの Exchange の展開を管理している場合、オンプレミス Exchange server に必要なメールボックスの受信者にメールを送信するためにセキュリティ証明書を使用して Office 365 に認証するためには、Office 365 でのみです。その結果、オンプレミス Exchange サーバーに独自のセキュリティ証明書を管理する必要があります。格納し、これらのサーバー証明書を管理する必要がありますも安全にします。ハイブリッド展開での証明書の管理の詳細については、[ハイブリッド展開の証明書の要件](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx)を参照してください。
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Office 365 における Exchange Online 用強制 TLS のセットアップ方法

Exchange オンラインのお客様の作業に TLS を強制するためにすべての送信および受信した電子メールをセキュリティで保護する必要があります TLS を必要とする 1 つ以上のコネクタを設定します。コネクタが 1 つ、ユーザーのメールボックスと、ユーザーのメールボックスから送信された電子メールを別のコネクタに送信される電子メールにする必要があります。Office 365 で、Exchange 管理センターでは、これらのコネクタを作成します。手順については、 [Office 365 のコネクタを使用してメールの流れを構成する](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)を参照してください。
  
## <a name="tls-certificate-information-for-exchange-online"></a>Exchange Online の TLS 証明書情報

Exchange Online によって使用される証明書の情報は次の表で説明します。ビジネス パートナーには、電子メール サーバー間で TLS を強制が設定される場合は、それらに情報を提供する必要があります。なるセキュリティ上の理由から、当社の証明書は変更に注意します。展開しました、更新、証明書を当社のデータ センター内で。新しい証明書は、2018 年 9 月 3日から有効です。
  
 **2018 年 9 月 3日から有効な現在の証明書情報**
  
|**Attribute**|**値**|
|:-----|:-----|
|証明機関ルート発行者  <br/> |GlobalSign のルート CA: R1 <br/> |
|証明書名  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織単位  <br/> |  <br/> |
|証明書キーの強度  <br/> |2048  <br/> |
   
 **使用されていない証明書については、2018 年 9 月 3 日まで有効です。**
  
スムーズな移行を確実には、引き続きしばらくの間では、参照用に古い証明書情報を提供するただし、現在の証明書情報を基を使用する必要があります。
  
****

|**Attribute**|**値**|
|:-----|:-----|
|証明機関ルート発行者  <br/> |Baltimore CyberTrust Root  <br/> |
|証明書名  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織単位  <br/> |Microsoft Corporation  <br/> |
|証明書キーの強度  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>新しい Exchange のオンライン証明書を準備します。

新しい証明書は、Exchange のオンラインで使用されている以前の証明書から別の証明機関 (CA) によって発行されます。その結果、新しい証明書を使用するためにいくつかの操作を実行する必要があります。

新しい証明書は、新しい CA 証明書の検証の一部としてのエンドポイントに接続する必要があります。失敗これを行うには、メール フローが悪影響を受ける可能性があります。メール サーバーのみを実行できるファイアウォールとサーバーの特定の宛先に接続してメールを保護する場合、サーバーが新しい証明書を検証することを確認する必要があります。サーバーが新しい証明書を使用できることを確認するには、これらの操作を行います。

1. 次のコマンドを実行して、Windows PowerShell を使用して、ローカルの Exchange Server に接続します。  
  `certutil -URL http://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. このウィンドウは表示されますが、**取得**をクリックします。
3. ユーティリティには、そのチェックが完了すると、ステータスを返します。ステータスは、 **[ok]** を表示する場合新しい証明書が正常に自分のメール サーバーに検証します。それ以外の場合は、接続に失敗する原因を特定する必要があります。ほとんどの場合、ファイアウォールの設定を更新する必要があります。エンドポイントにアクセスできる必要があるの完全な一覧は次のとおりです。
    - ocsp.globalsign.com
     - crl.globalsign.com
     - secure.globalsign.com   

通常、ルート証明書を Windows の更新プログラムを自動的に更新プログラムを受け取ります。ただし一部の展開では、これらの更新プログラムが自動的に発生することを防止する追加のセキュリティがあります。これらのロック ダウンは、Windows の更新は自動的に更新のルート証明書を展開、これらの手順を実行して、正しいルート CA 証明書がインストールされていることを確認する必要があります。
1.  次のコマンドを実行して、Windows PowerShell を使用して、ローカルの Exchange Server に接続します。  
  `certmgr.msc`
2. [**信頼されたルート証明機関と証明書**を新しい証明書が表示されていることを確認します。

## <a name="get-more-information-about-tls-and-office-365"></a>TLS と Office 365 に関する追加情報

サポートされている暗号のリストは、 [Office 365 での暗号化に関するテクニカル リファレンスの詳細](technical-reference-details-about-encryption.md)を参照してください。
  
[パートナー組織とのセキュリティで保護されたメール フロー用のコネクタを設定する](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[電子メール セキュリティを強化したコネクタ](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Office 365 での暗号化](encryption.md)
  

