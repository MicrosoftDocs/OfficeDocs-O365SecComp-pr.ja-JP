---
title: Office 365 での管理アクセス制御
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
description: '概要: Office 365 の管理者のアクセス制御とデータの分類の概要です。'
ms.openlocfilehash: afa15d37aa8542985c59dbd9e3d82368421530e8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532156"
---
# <a name="administrative-access-controls-in-office-365"></a>Office 365 での管理アクセス制御 

## <a name="introduction"></a>概要
マイクロソフトに投資を行って大きくし、それに応じてシステムと Office 365 のほとんどの操作を自動化するとともに、お客様のコンテンツへのアクセスを意図的に制限することをコントロールします。人間は、サービスを管理し、ソフトウェア、サービスの動作します。これにより、マイクロソフト、マイクロソフトのエンジニア リングなどのためのスピアー フィッシング詐欺など悪意のあるアクターは、顧客コンテンツへの内部の脅威のリスクを管理するだけでなく、規模で Office 365 を管理します。

既定では、マイクロソフトのエンジニアは Office 365 のゼロ位置の管理者特権とお客様のコンテンツへのアクセスをゼロ位置をあります。マイクロソフトのエンジニアの制限、監査し、時間、限られた量のコンテンツが、サービス業務に必要な場合にのみ、マイクロソフトの経営陣の (および、お客様のメンバーが承認された場合にのみ、お客様へのアクセスをセキュリティで保護できますライセンス顧客ロック ボックス機能は、顧客)。

マイクロソフトでは、クラウド配信の複数のフォームを使用して、Office 365 をなどのオンライン サービスを提供します。

- **パブリック クラウド**- には、マルチ テナント型のバージョン Office 365、Azure および北アメリカ、南アメリカ、ヨーロッパ、アジア、オーストラリアなどでホストされている他のサービスにはが含まれています。
- **国内雲の中**に (21Vianet が運用している)、中国では、Office 365 とドイツでは、Office 365 などその上で説明した)、米国以外のすべての君主およびサード ・ パーティ ・運用クラウドが含まれます (マイクロソフトが運用しているが、モデルでのドイツ語のデータ、トラスティ、Deutsche telekom 社が制御し、顧客データや顧客データが含まれているシステムにマイクロソフトのアクセスを監視する)。
- **政府雲**- には、アメリカ合衆国政府の顧客に利用可能な Office 365 と Azure のサービスが含まれています。

この資料の目的は、Office 365 サービスには、 [Exchange のオンライン](https://docs.microsoft.com/Exchange/exchange-online) [Exchange のオンライン保護](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)、 [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) ([ビジネスの OneDrive](https://docs.microsoft.com/OneDrive/onedrive)を含む)、[ビジネスの Skype](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)では、追加情報を[Yammer のエンタープライズ](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)のアクセス制御はいくつか。その他の Office 365 サービスでは、この資料の対象外です。

## <a name="office-365-access-controls"></a>Office 365 のアクセス制御
アクセス制御のため、Office 365 のデータは、お客様のデータまたはその他の種類のデータのいずれかとして分類されます。顧客データ、または Office 365 などのサービス、お客様のコンテンツ (コンテンツを直接作成または Office 365 を含むユーザーが SharePoint Online コンテンツ、電子メール、インスタント メッセージによってアップロードされたお客様の使用することで顧客のために提供されるすべてのデータでは予定表のアイテム、ドキュメント、および Office 365 に格納されている連絡先) とエンド ・ ユーザーを特定できる情報 (EUII) (データは、ユーザーに固有であるかを個々 のユーザーにリンク可能なですが、お客様のコンテンツは含まれません)。 

その他の種類のデータを含めアカウント (管理用のデータには、サインアップ、または購買サービスと支払データは、クレジットなど、支払機関に関する情報は、カードの詳細情報とは、管理者によって提供される情報が含まれています)組織的に特定できる情報 (はテナントの識別に使用できるデータや利用状況のデータは個々 のユーザーにリンク可能なことではなく、お客様のコンテンツは含まれません)、およびシステムのメタデータ (構成設定を含むサービスのログが含まれていますシステムのステータス、Microsoft IP アドレス、およびサブスクリプションと、テナントに関する技術情報)。

マイクロソフトは誰を持っていることを確認するのにはアクセス制御のメカニズムを確立顧客データやアクセス コントロールのデータへのアクセスを許可されていない (他の種類のデータや環境では、お客様のコンテンツまたは EUII; へのアクセスを含む関数へのアクセスを管理するために使用します。Microsoft のパスワード、セキュリティ証明書、およびその他の認証に関連するデータが含まれています)、または Office 365 の実稼働環境への未承認の物理、論理、またはリモート アクセスします。

Office 365 を操作するためにマイクロソフトによって使用されるアクセス制御は、次の 3 つのカテゴリに分類できます。
- 分離コントロール
- スタッフのコントロール
- テクノロジ制御

組み合わせることで、これらのコントロールを防止し、Office 365 での悪意のある行為の検出を支援します。分離、スタッフ、および Microsoft で使用されるテクノロジのコントロールで、他は、コントロールの 4 番目のカテゴリ: お客様が実装されているものです。

Office 365 を使用すると、オンプレミス環境で管理する同じ方法データの多くのデータを管理できます。Office 365 の組織を自動的に署名した人は、グローバル ・ アドミニストレーター (管理者) になります。グローバル管理者 (管理者・ センターやリモート PowerShell など) は、管理ポータルのすべての機能へのアクセス権を持つとを作成またはユーザーの編集、他のユーザーに管理者の役割を割り当てる、ユーザーのパスワードをリセット、ユーザー ライセンスの管理、ドメインを管理および承認できます顧客ロック ボックスその他のものの中に要求します。各組織に少なくとも 2 つの管理者アカウントを指定して、組織のサイズによって異なる機能を提供するいくつかの管理者を指定するのにはすることがあることをお勧めします。管理者の役割およびアクセス許可の割り当てについては、 [Office 365 の管理者の役割を割り当てる](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504)と、 [Office 365 の管理者の役割](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D)を参照してください。


## <a name="related-links"></a>関連リンク

- [分離コントロール](office-365-isolation-controls.md)
- [スタッフのコントロール](office-365-personnel-controls.md)
- [テクノロジ制御](office-365-technology-controls.md)
- [アクセス制御の監視と監査](office-365-monitoring-and-auditing-access-controls.md)
- [Yammer Enterprise でのアクセス制御](office-365-yammer-enterprise-access-controls.md)