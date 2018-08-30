---
title: Office 365 の暗号化についてのテクニカル リファレンスの詳細
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/12/2018
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
ms.openlocfilehash: d86692119f7558d74e2083165b4eb6ab4a07da70
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532552"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a>Office 365 の暗号化についてのテクニカル リファレンスの詳細

についての証明書、技術、および TLS 暗号スイートを[Office 365 での暗号化](encryption.md)に使用するには、この資料を参照してください。この資料では、計画的な deprecations の詳細も提供します。
  
- 概要情報を探している場合は、 [Office 365 での暗号化](encryption.md)を参照してください。
    
- セットアップ情報を探している場合は、 [Office 365 のエンタープライズでの暗号化の設定](set-up-encryption.md)を参照してください。
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 証明書の所有権と管理

Microsoft は独自の証明書を使用するため、お客様が Office 365 用の証明書を購入したり保持したりする必要はありません。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>現在の暗号化の標準、計画的な deprecations

続行すると、Office 365 のクラス最高レベルの暗号化を提供する、するためにマイクロソフトは定期的にサポートされている暗号化の規格を確認します。場合によっては、最新のそのため安全性が低くなると、古い基準を廃止する必要があります。ここでは、計画的な deprecations は現在サポートされている暗号およびその他の標準と同様に詳細を説明します。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 でサポートされる TLS のバージョン

トランスポート層セキュリティ (TLS) と、TLS に先立つ SSL は、セキュリティ証明書を使用してコンピューター間の接続を暗号化することによって、ネットワークを介した通信のセキュリティを確保する暗号化プロトコルです。Office 365 は、以下の TLS バージョンをサポートしています。
  
- TLS バージョン 1.2 (TLS 1.2)
    
- TLS バージョン 1.1 (TLS 1.1)
    
- TLS バージョン 1.0 (TLS 1.0)
    
 TLS 1.0 と 1.1 の TLS のサポートは 2018 年 10 月 31日使用されなくなりました。詳細については、 [TLS 1.0 および 1.1 であり、これが意味するのに Deprecating のサポート](technical-reference-details-about-encryption.md#TLS11and12deprecation)を参照してください。 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>TLS 1.0 および 1.1 であり、これが意味するのためのサポートを非推奨
<a name="TLS11and12deprecation"> </a>

重要な変更は、Office 365 のサポートされている暗号化オプションに聞こえます。2018 年 10 月 31日現在 Office 365 サポートしなくなります TLS 1.0 または 1.1 を使用して Office 365 への通信です。Office 365 では、これらのプロトコルのサポートを deprecates、Office 365 のサーバーとの間のすべての通信は、TLS 1.2 を使用する必要があります。この影響する方法については、 [Office 365 の TLS 1.2 の使用義務の準備](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365)を参照してください。サーバーおよび O365 との通信は、この日付以降後のクライアントは、TLS 1.2 をサポートしなければなりません。
  
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
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |はい  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |はい  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |はい  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |はい  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |いいえ  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |いいえ  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |いいえ  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |いいえ  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_3DES_EDE_CBC_SHA  <br/> |RSA/112  <br/> |いいえ  <br/> |RSA/112  <br/> |3DES/192  <br/> |
   
## <a name="related-topics"></a>関連項目
<a name="TLSCipherSuites"> </a>

[Office 365 での暗号化](encryption.md)
  
[Office 365 Enterprise で暗号化を設定する](set-up-encryption.md)
  
[TLS 1.0 の Windows セキュリティのステータスの更新プログラムでの Schannel の実装: 2015 年 11 月 24 日](https://support.microsoft.com/kb/3117336)
  
[TLS と SSL 暗号化の強化 (Windows IT センター)](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

