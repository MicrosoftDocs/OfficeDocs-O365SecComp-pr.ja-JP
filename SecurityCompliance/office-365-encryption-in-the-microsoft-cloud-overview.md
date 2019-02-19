---
title: Microsoft Cloud における暗号化
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Microsoft クラウドでの暗号化の概要について説明します。
ms.openlocfilehash: 75ed88d4755ab37f03b4821125e175a66015afa8
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2019
ms.locfileid: "29664133"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Microsoft Cloud における暗号化

Microsoft のエンタープライズクラウドサービス内の顧客データは、さまざまな形式の暗号化などのさまざまなテクノロジとプロセスによって保護されています。(このドキュメントに含まれる Office 365 の顧客データには、Exchange Online メールボックスのコンテンツ (電子メール本文、予定表のエントリ、電子メールの添付ファイルの内容、適用可能な場合は Skype for business コンテンツ)、SharePoint Online サイトのコンテンツ、および内部に格納されているファイルが含まれます。サイト、OneDrive for business または Skype for business にアップロードされたファイル)Microsoft では、顧客データがクラウドサービスを通過するためのセキュリティで保護されたパスを提供し、内部に格納されている顧客データの機密性を保護するために、製品とサービス全体で複数の暗号化の方法、プロトコル、および暗号を使用しています。クラウドサービス。Microsoft では、お客様のデータへの不正なアクセスからの障壁を得るために使用できる最強の安全な暗号化プロトコルの一部を使用しています。適切なキー管理は、暗号化のベストプラクティスの重要な要素でもあり、microsoft は、すべての microsoft 管理暗号化キーが適切にセキュリティ保護されていることを確認するために機能します。

お客様の構成に関係なく、Microsoft のエンタープライズクラウドサービス内に格納されているお客様のデータは、1つ以上の形式の暗号化を使用して保護されます。(暗号化ポリシーとその強制の検証は、複数のサードパーティの監査者によって個別に確認され、それらの監査のレポートは[サービス信頼ポータル](https://aka.ms/stp)で利用できます)。

Microsoft は、お客様のデータを保存中および転送中に暗号化するサービス側テクノロジを提供しています。たとえば、お客様のデータが保存されている場合、microsoft Azure は[bitlocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview)と[DM-Crypt](https://en.wikipedia.org/wiki/Dm-crypt)を使用し、microsoft Office 365 は bitlocker、 [Azure Storage Service 暗号化](https://azure.microsoft.com/documentation/articles/storage-service-encryption/)、 [Distributed Key Manager](https://support.office.com/article/989ba10c-f73f-4efb-ad1b-af3322e5f376) (DKM)、および Office 365 サービスを使用します。暗号化.転送中の顧客データ、Azure、Office 365、microsoft コマーシャルサポート、microsoft Dynamics 365、microsoft Power BI、Visual Studio Team Services は、業界標準のセキュリティで保護されたトランスポートプロトコル (インターネットプロトコルセキュリティ (IPsec) など) を使用します。microsoft データセンター間、ユーザーデバイスと microsoft データセンター間のトランスポート層セキュリティ (TLS)。

Microsoft によって提供される暗号化セキュリティのベースラインレベルに加えて、クラウドサービスには、管理可能な追加の暗号化オプションも含まれています。たとえば、Azure 仮想マシン (vm) とユーザーの間のトラフィックに対して暗号化を有効にすることができます。[azure 仮想ネットワーク](https://azure.microsoft.com/services/virtual-network/)では、業界標準の IPsec プロトコルを使用して、企業の VPN ゲートウェイと Azure の間、および仮想ネットワーク上に配置された vm 間のトラフィックを暗号化することができます。さらに、[新しい Office 365 メッセージの暗号化機能](set-up-new-message-encryption-capabilities.md)を使用すると、暗号化されたメールをだれにでも送信できます。

microsoft[セキュリティポリシー](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)のコンポーネントである公開キー基盤の運用セキュリティ標準に準拠して、microsoft は、証明書用の Windows オペレーティングシステムに含まれている暗号化機能を活用し、認証機構。米国政府機関の[連邦情報処理規格](http://csrc.nist.gov/publications/PubsFIPS.html)(FIPS) 140-2 標準に準拠する暗号化モジュールの使用が含まれます。(Microsoft の関連する NIST 証明書番号については、「」を参照してください。http://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> ことMicrosoft セキュリティポリシーにリソースとしてアクセスするには、職場または学校のアカウントを使用してサインインする必要があります。サブスクリプションをまだお持ちでない場合は、[無料試用版にサインアップでき](https://servicetrust.microsoft.com/Home/TrialSubscriptions)ます。

FIPS 140-2 は、これを使用する製品ではなく、暗号化を実装する製品モジュールを検証するために特別に設計された標準です。サービス内で実装されている暗号化モジュールは、ハッシュの強度、キーの管理などの要件を満たすことが認定されている場合があります。Microsoft のクラウドサービスでのデータの機密性、整合性、または可用性を保護するために暗号化機能が使用されている場合は、FIPS 140-2 標準に準拠するモジュールと暗号が使用されます。

Microsoft は、Windows オペレーティングシステムの新しいリリースごとにクラウドサービスで使用される基礎となる暗号化モジュールを認定しています。
- azure および azure 米国政府
- dynamics 365 および dynamics 365 米国政府
- office 365、office 365 米国政府機関、および office 365 米国政府機関の防御

Office 365 の顧客データの暗号化 rest では、Exchange Online、Skype for business、OneDrive for business、および SharePoint の BitLocker、DKM、Azure Storage service 暗号化、サービス暗号化など、複数のサービス側テクノロジによって提供されます。オンライン。Office 365 service encryption には、Azure Key Vault に格納されている、顧客が管理する暗号化キーを使用するオプションが含まれています。この顧客管理キーオプション ( [Office 365 顧客キー](https://support.office.com/article/f2cd475a-e592-46cf-80a3-1bfb0fa17697)) は、Exchange online、SharePoint Online、Skype for business、および OneDrive for business で使用できます。

送信中の顧客データの場合、すべての Office 365 サーバーは、既定で TLS を使用してセキュリティで保護されたセッションを、顧客データをセキュリティで保護するクライアントコンピューターを使用してネゴシエートします これは、Skype for business、outlook、web 上の outlook、モバイルクライアント、web ブラウザーなど、クライアントによって使用されるすべてのデバイスのプロトコルに適用されます。

(お客様に接しているすべてのサーバーは、既定で TLS 1.2 にネゴシエートされますが、必要に応じて、より低い標準へのネゴシエートもサポートしています)。

## <a name="related-links"></a>関連リンク

- [Azure での暗号化](office-365-azure-encryption.md)
- [BitLocker とDistributed Key Manager (DKM) による暗号化](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 でのサービスの暗号化](office-365-service-encryption.md)
- [Skype for business、OneDrive for business、SharePoint online、Exchange online の Office 365 暗号化](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [転送中データの暗号化](office-365-encryption-for-data-in-transit.md)
- [顧客により管理される暗号化機能](office-365-customer-managed-encryption-features.md)
- [暗号化のリスクと保護](office-365-encryption-risks-and-protections.md)
- [Microsoft Dynamics 365 での暗号化](office-365-encryption-in-microsoft-dynamics-365.md)