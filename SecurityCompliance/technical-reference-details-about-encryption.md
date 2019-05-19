---
title: Office 365 の暗号化についてのテクニカル リファレンスの詳細
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Office 365 の encyption に関する技術的な詳細情報を表示します。
ms.openlocfilehash: 84416c67eb646c757da93fc9e4029c08efaa70a2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158229"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a>Office 365 の暗号化についてのテクニカル リファレンスの詳細

この記事では、 [Office 365 の暗号化](encryption.md)に使用される証明書、テクノロジ、および TLS 暗号スイートについて説明します。 この記事では、計画した deprecations の詳細についても説明します。
  
- 概要情報を探している場合は、「 [Encryption In Office 365](encryption.md)」を参照してください。
- セットアップ情報を探している場合は、「 [Office 365 Enterprise で暗号化を設定](set-up-encryption.md)する」を参照してください。
- 特定のバージョンの Windows でサポートされている暗号スイートの詳細については、「 [TLS/SSL (SCHANNEL SSP)」の「Cipher suite](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)」を参照してください。
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 証明書の所有権と管理

Microsoft は独自の証明書を使用するため、お客様が Office 365 用の証明書を購入したり保持したりする必要はありません。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>現在の暗号化標準と予定されている deprecations

Office 365 のクラス最高の暗号化を引き続き提供するために、Microsoft は、サポートされている暗号化基準を定期的にレビューします。 古い標準は古くなっており、セキュリティが低いため、廃止する必要があります。 このトピックでは、現在サポートされている暗号スイートとその他の標準、および計画した deprecations に関する詳細について説明します。 

## <a name="fips-compliance-for-office-365"></a>Office 365 の FIPS コンプライアンス
Office 365 でサポートされているすべての暗号スイートは、FIPS 140-2 で使用可能なアルゴリズムを使用します。 Office 365 は、Windows (Schannel 経由) から FIPS 検証を継承します。 Schannel の詳細については、「 [TLS/SSL (SCHANNEL SSP)」の「Cipher suite](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)」を参照してください。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 でサポートされる TLS のバージョン

トランスポート層セキュリティ (TLS) と、TLS に先立つ SSL は、セキュリティ証明書を使用してコンピューター間の接続を暗号化することによって、ネットワークを介した通信のセキュリティを確保する暗号化プロトコルです。Office 365 は、以下の TLS バージョンをサポートしています。
  
- TLS バージョン 1.2 (TLS 1.2)
    
- TLS バージョン 1.1 (TLS 1.1)
    
- TLS バージョン 1.0 (TLS 1.0)
    
 TLS 1.0 および TLS 1.1 のサポートは、2018年10月31日に廃止されます。 詳細については、「[廃止 support FOR TLS 1.0」と「1.1](technical-reference-details-about-encryption.md#TLS11and12deprecation) 」を参照してください。 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>廃止での TLS 1.0 および1.1 のサポートとその意味
<a name="TLS11and12deprecation"> </a>

2018年10月31日以降、Office 365 は TLS 1.0 および1.1 をサポートしなくなりました。 これは、Microsoft が、TLS 1.0 および1.1 を使用して Office 365 に接続するクライアント、デバイス、またはサービスに関する新しい問題を修正しないことを意味します。

メモこれは、Office 365 が TLS 1.0 および1.1 の接続をブロックすることを意味するわけではありません。 TLS サービスでは、顧客接続に対して TLS 1.0 および1.1 を無効にしたり、削除したりする正式な日付はありません。 最終的に廃止される日付は、顧客のテレメトリによって決定され、まだ知られていません。 決定した後、既知の侵害を認識しない限り、6か月前にアナウンスが行われます。この場合、サービスを使用するお客様を保護するために6か月以内に行動する必要があります。

Office 365 サービスへの接続を維持するために、すべてのクライアントサーバーとブラウザーサーバーの組み合わせが TLS 1.2 (またはそれ以降のバージョン) を使用していることを確認する必要があります。 特定のクライアントサーバーとブラウザーサーバーの組み合わせを更新する必要がある場合があります。 この影響の詳細については、「 [Office 365 での TLS 1.2 の必須使用の準備](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365)」を参照してください。
  
## <a name="deprecating-support-for-3des"></a>3DES の廃止サポート
<a name="TLS11and12deprecation"> </a>

2018年10月31日以降、Office 365 は office 365 への通信に3DES 暗号化スイートの使用をサポートしなくなりました。 具体的には、Office 365 は TLS_RSA_WITH_3DES_EDE_CBC_SHA cipher スイートをサポートしなくなりました。 2019年2月28日以降、この暗号スイートは Office 365 で無効になっています。 この日付の後に O365 と通信するクライアントおよびサーバーは、このトピックに記載されている、より安全な暗号の少なくとも1つをサポートする必要があります (「 [Office 365 でサポートされている TLS 暗号スイート](technical-reference-details-about-encryption.md#TLSCipherSuites)」を参照してください)。
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365 における SHA-1 証明書サポートの廃止
<a name="TLS11and12deprecation"> </a>

2016年6月の時点で、Office 365 は、送信接続または受信接続に対して SHA-1 証明書を受け入れなくなりました。 現在、証明書チェーンの SHA-1 で証明書を使用している場合は、SHA-1 (Secure Hash Algorithm 2) またはより強力なハッシュアルゴリズムを使用するようにチェーンを更新する必要があります。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 でサポートされている TLS 暗号スイート
<a name="TLSCipherSuites"> </a>

Cipher suite は、セキュリティで保護された接続を確立するために TLS が使用する暗号化アルゴリズムの集合です。 Office 365 でサポートされている暗号スイートについては、次の表に、最強の暗号スイートが最初に表示された場合の強度を示します。 Office 365 が接続要求を受信すると、Office 365 は最初に最上位の暗号スイートを使用して接続しようとします。失敗した場合は、リスト内の2番目の暗号スイートを一覧の下まで試します。 Office 365 が別のサーバーまたはクライアントに接続要求を送信する場合は、受信側のサーバーまたはクライアントが暗号スイートを選択するか、TLS を使用するかを選択します。

> [!IMPORTANT]
> TLS のバージョンが廃止され、使用され*なく*なったバージョンを使用して新しいバージョンを入手できないことに注意してください。 つまり、TLS 1.0、1.1、1.2 がサポートされている任意の場所で、*最新*バージョン (tls 1.2) を選択します。
  
|**プロトコル**|**暗号スイート名**|**キー交換アルゴリズム/強度**|**完全なフォワード機密サポート**|**認証アルゴリズム/強度**|**暗号/強度**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> |ECDH/192  <br/> |はい  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> |ECDH/128  <br/> |はい  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |はい  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |はい  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |はい  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |はい  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |いいえ  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |いいえ  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |いいえ  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |いいえ  <br/> |RSA/112  <br/> |AES/128  <br/> |
   
## <a name="related-topics"></a>関連項目
[Windows 10 v1607 の TLS 暗号スイート](https://docs.microsoft.com/windows/desktop/SecAuthN/tls-cipher-suites-in-windows-10-v1607)

[Office 365 での暗号化](encryption.md)
  
[Office 365 Enterprise で暗号化を設定する](set-up-encryption.md)
  
[Windows セキュリティ状態更新プログラムでの TLS 1.0 の Schannel 実装:11 月24日、2015](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL 暗号化の強化 (Windows IT センター)](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

