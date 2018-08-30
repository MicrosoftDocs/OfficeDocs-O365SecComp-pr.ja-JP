---
title: 転送中のデータの暗号化を office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: マイクロソフトが送信中のデータを暗号化する方法を簡単に説明します。'
ms.openlocfilehash: 8f4781cf1127fb1b6bf742c267c76e3df39b8209
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531603"
---
# <a name="office-365-encryption-for-data-in-transit"></a>転送中のデータの暗号化を office 365

顧客データの保護、他は、マイクロソフトは、転送中に Office 365 の顧客データを保護するのに暗号化テクノロジを使用します。 

データを転送中にいます。
- クライアント コンピューターを Office 365 サーバーと通信するとき
- Office 365 サーバーと Office 365 の別のサーバーに通信するときそして
- 場合、Office 365 のサーバーは、Office 365 以外のサーバー (外部の電子メール サーバーに提供する電子メールを Exchange Online など) と通信します。

TLS または IPsec 経由で Office 365 のサーバー間でのデータ センター間の通信が実行され、顧客向けのすべてのサーバーが TLS を使用して、クライアント コンピューターとセキュリティで保護されたセッションをネゴシエート (Exchange Online の使用など、256 ビットの暗号強度で TLS 1.2 を使用 (FIPS2 検証 140-2 レベル)。(TLS 暗号スイートを Office 365 でサポートされているリストの[テクニカル リファレンスの詳細については、Office 365 での暗号化](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221)を参照してください)。これは、ビジネス、および Outlook (たとえば、HTTP、POP3 など) は、web 上の Outlook、Skype クライアントによって使用されるプロトコルに適用されます。

公開証明書は、SSLAdmin、転送された情報の機密性を保護するために内部の Microsoft ツールを使用して Microsoft IT の SSL によって発行されます。Microsoft IT によって発行された証明書をすべて 2048 ビットの最小の長さがあり、 [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf)のコンプライアンスには、Microsoft が所有しているパブリックの IP アドレスにのみ証明書が発行されるかどうかを確認するのには SSLAdmin が必要です。例外プロセスを通じて、この条件を満たしていない任意の IP アドレスがルーティングされます。

TLS が使用されているのバージョン、前方秘密 (FS) が有効になっているかどうか、暗号などのすべての実装の詳細については、一般に使用できます。これらの詳細を表示する方法の 1 つでは、Qualys の SSL の演習 (www.ssllabs.com) などのサードパーティの web サイトを使用します。次には、以下のサービスについての情報を表示する Qualys の自動テストのページへのリンクを示します。
- [Office 365 ポータル](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [Skype ビジネス (SIP)](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [Skype ビジネス (Web)](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Exchange Online Protection](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

Exchange のオンライン保護のため、Url がテナント名によって異なりますただし、すべての顧客は、 **microsoft com.mail.protection.outlook.com**を使用して Office 365 をテストできます。
