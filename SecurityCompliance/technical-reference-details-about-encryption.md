---
title: Office 365 の暗号化についてのテクニカル リファレンスの詳細
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/15/2019
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Office 365 では、暗号化に関する技術的な詳細を表示します。
ms.openlocfilehash: bb4629d89d2ed625cc1b817c53d2355484bfdf6c
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "28326938"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a>Office 365 の暗号化についてのテクニカル リファレンスの詳細

についての証明書、技術、および TLS 暗号スイートを[Office 365 での暗号化](encryption.md)に使用するには、この資料を参照してください。この資料では、計画的な deprecations の詳細も提供します。
  
- 概要情報を探している場合は、 [Office 365 での暗号化](encryption.md)を参照してください。
- セットアップ情報を探している場合は、 [Office 365 のエンタープライズでの暗号化の設定](set-up-encryption.md)を参照してください。
- 特定のバージョンの Windows でサポートされている暗号については、 [TLS と SSL (Schannel SSP) での暗号化方式群](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)を参照してください。
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 証明書の所有権と管理

Microsoft は独自の証明書を使用するため、お客様が Office 365 用の証明書を購入したり保持したりする必要はありません。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>現在の暗号化の標準、計画的な deprecations

続行すると、Office 365 のクラス最高レベルの暗号化を提供する、するためにマイクロソフトは定期的にサポートされている暗号化の規格を確認します。場合によっては、最新のそのため安全性が低くなると、古い基準を廃止する必要があります。ここでは、計画的な deprecations は現在サポートされている暗号およびその他の標準と同様に詳細を説明します。 

## <a name="fips-compliance-for-office-365"></a>Office 365 の FIPS 準拠
Office 365 によってサポートされているすべての暗号は、FIPS 140-2 の下で許容可能なアルゴリズムを使用します。Office 365 では、(Schannel) 使用して、Windows の FIPS 検証を継承します。Schannel の詳細については、 [TLS と SSL (Schannel SSP) での暗号化方式群](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)を参照してください。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 でサポートされる TLS のバージョン

トランスポート層セキュリティ (TLS) と、TLS に先立つ SSL は、セキュリティ証明書を使用してコンピューター間の接続を暗号化することによって、ネットワークを介した通信のセキュリティを確保する暗号化プロトコルです。Office 365 は、以下の TLS バージョンをサポートしています。
  
- TLS バージョン 1.2 (TLS 1.2)
    
- TLS バージョン 1.1 (TLS 1.1)
    
- TLS バージョン 1.0 (TLS 1.0)
    
 TLS 1.0 と 1.1 の TLS のサポートは 2018 年 10 月 31日使用されなくなりました。詳細については、 [TLS 1.0 および 1.1 であり、これが意味するのに Deprecating のサポート](technical-reference-details-about-encryption.md#TLS11and12deprecation)を参照してください。 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>TLS 1.0 および 1.1 であり、これが意味するのためのサポートを非推奨
<a name="TLS11and12deprecation"> </a>

現在 2018 年 10 月 31日 TLS 1.0 および 1.1 Office 365 はサポートしません。これは、Microsoft クライアント、デバイス、または TLS 1.0 および 1.1 を使用して Office 365 に接続するサービスである、新たな問題は解決しないことを意味します。

Office 365 は、TLS 1.0 と 1.1 の接続をブロックはこれといって注意してください。無効にするか、お客様の接続に TLS サービスで TLS 1.0 および 1.1 を削除するための正式な日付がありません。最終的な廃止日は、お客様の遠隔測定によって決定され、未知です。意思決定が行われると、あるお知らせ 6 か月前に既知の侵害の認識となることがない限りは、機能、サービスを使用しているお客様を保護するために 6 ヶ月以内に必要な場合。

すべてのクライアントとサーバーとブラウザーとサーバーの組み合わせが Office 365 サービスに、接続を維持するために TLS 1.2 (またはそれ以降のバージョン) を使用することを確認する必要があります。特定のクライアントとサーバーとブラウザーとサーバーの組み合わせを更新する必要があります。この影響する方法については、 [Office 365 の TLS 1.2 の使用義務の準備](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365)を参照してください。
  
## <a name="deprecating-support-for-3des"></a>3 des のサポートを非推奨
<a name="TLS11and12deprecation"> </a>

2018 年 10 月 31日現在 Office 365 サポートしなくなります 3 des 暗号を使用して Office 365 への通信です。具体的には、Office 365 はもはや TLS_RSA_WITH_3DES_EDE_CBC_SHA 暗号をサポートします。ここで記載されているクライアントとサーバー通信 O365 後、この日付より安全な暗号の 1 つ以上をサポートする必要があります ( [TLS の暗号スイートを Office 365 でサポートされている](technical-reference-details-about-encryption.md#TLSCipherSuites)を参照してください)。
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365 における SHA-1 証明書サポートの廃止
<a name="TLS11and12deprecation"> </a>

6 月の 2016 年 Office 365 は sha-1 証明書の発信または着信接続を受け付けなくなりました。Sha-1 と証明書チェーンに証明書を使用している現在場合、は、sha-2 (セキュリティで保護されたハッシュ アルゴリズム 2) またはより強力なハッシュ アルゴリズムを使用してチェーンを更新する必要があります。
  
## <a name="deprecating-rc4-support-in-office-365"></a>Office 365 における RC4 サポートの廃止
<a name="TLS11and12deprecation"> </a>

2015 年 7 月に、次の RC4 暗号スイートのサポートは廃止されました。
  
- TLS_RSA_WITH_RC4_128_SHA
    
- TLS_RSA_WITH_RC4_128_MD5
    
## <a name="deprecating-secure-sockets-layer-ssl-30-support-in-office-365"></a>Office 365 の Secure Sockets Layer (SSL) 3.0 のサポートを非推奨
<a name="TLS11and12deprecation"> </a>

2014 年 12 月 1 日の開始 Office 365 は、Secure Sockets Layer (SSL) 3.0 では、TLS に先行タスクのサポートを無効にすることを始めました。詳細については、[セキュリティ アドバイザリの 3009008](https://technet.microsoft.com/library/security/3009008.aspx)を参照してください。確認する方法の詳細については、クライアントは TLS 1.0 またはそれ以降を使用しているし、SSL 3.0 では、無効にするのには、 [SSL 3.0 の保護の脆弱性](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/)を参照してください。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>TLS 暗号スイートを Office 365 でサポートされています。
<a name="TLSCipherSuites"> </a>

暗号スイートは、TLS がセキュリティで保護された接続を確立するために使用する暗号アルゴリズムのコレクションです。Office 365 でサポートされている暗号スイートを以下の表にまとめます。強度の高い暗号スイートから順に示しています。Office 365 が接続要求を受信すると、まず Office 365 は最初に挙げられている暗号スイートを使用して接続を試行します。接続できないと、一覧の 2 番目以降の暗号スイートを順に試行します。Office 365 が別のサーバーまたはクライアントに接続要求を送信する場合、受信側のサーバーまたはクライアントが、暗号スイートを選択するか、TLS を使用するかどうかを選択します。
  
|**プロトコル**|**暗号スイート名**|**鍵交換アルゴリズム/強度**|**PFS (Perfect Forward Secrecy) サポート**|**認証アルゴリズム/強度**|**暗号/強度**|
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
[Windows 10 v1607 で TLS 暗号スイート](https://docs.microsoft.com/windows/desktop/SecAuthN/tls-cipher-suites-in-windows-10-v1607)

[Office 365 での暗号化](encryption.md)
  
[Office 365 Enterprise で暗号化を設定する](set-up-encryption.md)
  
[TLS 1.0 の Windows セキュリティのステータスの更新プログラムでの Schannel の実装: 2015 年 11 月 24 日](https://support.microsoft.com/kb/3117336)
  
[TLS と SSL 暗号化の強化 (Windows IT センター)](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

