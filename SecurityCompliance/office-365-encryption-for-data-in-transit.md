---
title: 転送中のデータの Office 365 暗号化
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: 転送中に Microsoft がデータを暗号化する方法を簡単に説明します。'
ms.openlocfilehash: 987e923e242b47b07ad1ef65e5c7ce791c27d5bd
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217507"
---
# <a name="office-365-encryption-for-data-in-transit"></a>転送中のデータの Office 365 暗号化

お客様のデータを保存して保護することに加えて、Microsoft は暗号化テクノロジを使用して、転送中の Office 365 顧客データを保護します。 

データの送信中:
- クライアントコンピューターが Office 365 サーバーと通信する場合
- office 365 サーバーが別の office 365 サーバーと通信する場合。そして
- office 365 サーバーが office 以外の365サーバーと通信する場合 (Exchange Online が電子メールを外部電子メールサーバーに配信する場合など)。

Office 365 サーバー間のデータセンター間通信は tls または IPsec 経由で行われ、すべてのお客様向けのサーバーは、クライアントマシンとの tls を使用してセキュリティで保護されたセッションをネゴシエートします (例: Exchange Online では、256ビットの暗号強度で tls 1.2 が使用されます) (FIPS140-2 レベル 2-検証)。(office 365 でサポートされている TLS 暗号スイートの一覧については、「 [office 365 の暗号化に関する技術リファレンスの詳細](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221)」を参照してください)。これは、outlook、Skype for business、web 上の outlook などのクライアントによって使用されるプロトコル (例: HTTP、POP3 など) に適用されます。

公開証明書は、microsoft IT SSL によって発行された microsoft IT SSL で、送信された情報の機密性を保護するための内部 microsoft ツールです。microsoft によって発行されるすべての証明書の長さは2048ビットです。また、 [webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf)コンプライアンスでは、証明書が microsoft によって所有されるパブリック IP アドレスにのみ発行されるようにするために、ssladmin が必要になります。この条件を満たすことができない IP アドレスは、例外プロセスを経由してルーティングされます。

使用されている TLS のバージョン、転送機密性 (FS) が有効になっているかどうか、暗号スイートの順番など、すべての実装の詳細を公開できます。これらの詳細を確認する方法の1つは、Qualys SSL Labs (www.ssllabs.com) などのサードパーティの web サイトを使用することです。次のサービスの情報を表示する Qualys からの自動テストページへのリンクを以下に示します。
- [Office 365 ポータル](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [Skype for business (SIP)](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [Skype for business (Web)](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Exchange Online Protection](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

Exchange Online Protection の場合、url はテナント名によって異なります。ただし、すべてのお客様は、 **microsoft-com.mail.protection.outlook.com**を使用して Office 365 をテストできます。
