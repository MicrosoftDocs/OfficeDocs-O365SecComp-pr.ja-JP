---
title: Microsoft Cloud における暗号化
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
description: マイクロソフトのクラウドでの暗号化の概要について説明します。
ms.openlocfilehash: b8dee7ca7a791878763b885ada40a1d87f074e8e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532567"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Microsoft Cloud における暗号化

さまざまなテクノロジとプロセスは、さまざまな形式の暗号化を含む、Microsoft のエンタープライズ ・ クラウド ・ サービス内での顧客データが保護されています。(この文書で顧客データ office 365 にはには、Exchange Online のメールボックスの内容が含まれています (電子メールの本文、予定表エントリ、および電子メールの添付ファイルの内容と、該当する場合、Skype ビジネス ・ コンテンツの) オンラインの SharePoint サイトのコンテンツ、および、ファイル内に格納サイト、および企業またはビジネス用の Skype の OneDrive にアップロードされたファイルを使用します。)Microsoft を使用して複数の暗号化方式、プロトコル、および暗号の製品とサービスの間で顧客データ、クラウド サービスを経由するように格納されている顧客データの機密性を保護するためのセキュリティで保護されたパスを提供するためにクラウド サービスです。マイクロソフトは、いくつかの顧客データを不正アクセスからの障壁を提供する使用可能な最も強力な最も安全な暗号化プロトコルを使用します。適切なキー管理が暗号化のベスト プラクティスの重要な要素でもあり、マイクロソフトでは、すべての Microsoft で管理される暗号化キーが正しく保護されていることを確認します。

お客様の構成に関係なく、暗号化の 1 つまたは複数のフォームを使用して Microsoft のエンタープライズ ・ クラウド ・ サービス内に保存された顧客データが保護されています。(複数のサードパーティの監査役によって、暗号化のポリシーとその実施の検証が個別に検証済み、これらの監査のレポートは、[サービスの信頼のポータル](https://aka.ms/stp)の使用)。

マイクロソフトでは、転送中に、不使用時に顧客データを暗号化するサービス側のテクノロジを提供します。などの残りの部分で、顧客データの[BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview)および[DM の地下聖堂](https://en.wikipedia.org/wiki/Dm-crypt)では、Microsoft Azure を使用して Microsoft Office 365 を使用して、BitLocker、 [Azure のストレージ ・ サービスの暗号化](https://azure.microsoft.com/documentation/articles/storage-service-encryption/)、[キー マネージャーの配布](https://support.office.com/article/989ba10c-f73f-4efb-ad1b-af3322e5f376)(DKM)、および Office 365 のサービス暗号化します。輸送中の顧客データは、Azure、Office 365、マイクロソフトの商用サポート、Microsoft Dynamics 365、Microsoft 電源双、および Visual Studio Team Services を使用して、インターネット プロトコル セキュリティ (IPsec) などの業界標準のセキュリティで保護されたトランスポート プロトコルとトランスポート層セキュリティ (TLS)、マイクロソフトのデータ センター間およびユーザーのデバイスと Microsoft のデータ センターです。

クラウド サービスには、マイクロソフトによって提供される暗号化のセキュリティのベースライン レベルだけでなく管理できる追加の暗号化のオプションも含まれます。など、Azure の仮想マシン (Vm) と、ユーザー間のトラフィックの暗号化を有効にできます。[Azure の仮想ネットワーク](https://azure.microsoft.com/services/virtual-network/)では、Azure を仮想ネットワーク上にある仮想マシンの間にも、企業の VPN ゲートウェイ間のトラフィックを暗号化するために業界標準の IPsec プロトコルを使用できます。[さらに、さらに、新しい Office 365 のメッセージの暗号化機能](set-up-new-message-encryption-capabilities.md)により、すべてのユーザーに暗号化されたメールを送信することです。

に従って、公開キー インフラストラクチャ運用セキュリティ標準、 [Microsoft のセキュリティ ポリシー](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)のコンポーネントである、マイクロソフトは証明書を Windows オペレーティング システムに含まれている暗号化機能を活用して、認証メカニズムは、米国政府の[連邦情報処理規格](http://csrc.nist.gov/publications/PubsFIPS.html)(FIPS) 140-2 規格に適合している暗号モジュールの使用が含まれています。(Microsoft の証明書番号を該当する NIST にあります。http://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> [メモ]リソースとして、マイクロソフトのセキュリティ ポリシーにアクセスするに、職場、学校のアカウントを使用して署名する必要があります。場合は、サブスクリプションはまだ[無料の試用版にサインアップすることがでく](https://servicetrust.microsoft.com/Home/TrialSubscriptions)必要はありません。

FIPS 140-2 は、それらを使用する製品ではなく、暗号化を実装する製品のモジュールの検証用に設計された標準です。サービス内に実装されている暗号化モジュールは、ハッシュの強度、キー管理などの要件を満たす認定されることができます。暗号化機能は、機密性、整合性、またはマイクロソフトのクラウド サービスで、データの可用性を保護するために使用されますが、いつでもモジュールおよび暗号の使用を満たす FIPS 140-2 標準。

マイクロソフトは、クラウド サービスと Windows オペレーティング システムの新しいリリースで使用される、基になる暗号化モジュールを証明します。
- Azure と Azure 米国政府
- Dynamics 365 と米国政府の Dynamics 365
- Office 365、Office 365 の米国政府機関、および Office 365 の米国政府の防衛

他に Office 365 の顧客データの暗号化が提供されている BitLocker、DKM、Azure ストレージ ・ サービスの暗号化および暗号化のサービスを Exchange など、複数のサービス側のテクノロジーがオンライン、ビジネスの Skype、OneDrive ビジネス、および SharePoint のオンライン。Office 365 サービスの暗号化には、Azure のキーの保管場所に格納されている顧客管理の暗号化キーを使用するためのオプションが含まれています。Exchange のオンライン、オンラインの SharePoint、Skype のビジネス、およびビジネスのための OneDrive はこの顧客管理キー オプションは、 [Office 365 の顧客のキー](https://support.office.com/article/f2cd475a-e592-46cf-80a3-1bfb0fa17697)と呼ばれます。

顧客データが転送中に、Office 365 のすべてのサーバーは TLS を使用する既定ではクライアント マシンでお客様のデータをセキュリティで保護する、セキュリティで保護されたセッションをネゴシエートします。 これは、Skype のビジネス、Outlook、および、web、モバイル クライアント、および web ブラウザー上で Outlook などのクライアントによって使用される任意のデバイス上のプロトコルに適用されます。

(既定では、お客様向けのすべてのサーバーが TLS 1.2 をネゴシエートしますが、でも得られるよう、標準の下に下げるために必要な場合)。

## <a name="related-links"></a>関連リンク

- [Azure での暗号化](office-365-azure-encryption.md)
- [BitLocker とDistributed Key Manager (DKM) による暗号化](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 でのサービスの暗号化](office-365-service-encryption.md)
- [ビジネス、SharePoint のオンラインで、オンラインの Exchange のビジネス用の Skype、OneDrive の office 365 の暗号化](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [転送中データの暗号化](office-365-encryption-for-data-in-transit.md)
- [顧客により管理される暗号化機能](office-365-customer-managed-encryption-features.md)
- [暗号化のリスクと保護](office-365-encryption-risks-and-protections.md)
- [Microsoft Dynamics 365 での暗号化](office-365-encryption-in-microsoft-dynamics-365.md)