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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '概要: Office 365 の管理アクセス制御とデータ分類の概要について説明します。'
ms.openlocfilehash: f5cac8b6161ea7eab6ea390e32caec1c5ddb9bac
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091029"
---
# <a name="administrative-access-controls-in-office-365"></a>Office 365 での管理アクセス制御 

## <a name="introduction"></a>概要
microsoft は、お客様のコンテンツへの microsoft のアクセスを意図的に制限する一方で、ほとんどの Office 365 操作を自動化するシステムと制御に、多くの投資を行ってきました。人間がサービスを制御し、ソフトウェアがサービスを運用します。これにより、microsoft は Office 365 をスケールで管理できるようになり、悪意のある俳優、Microsoft のエンジニアのスピアーフィッシングなど、お客様のコンテンツに対する内部の脅威のリスクを管理することもできます。

既定では、Microsoft のエンジニアは、Office 365 ではゼロの管理者権限と、お客様のコンテンツへの継続的なアクセス権を持ちます。microsoft のエンジニアは、限られた期間、お客様のコンテンツへのアクセスを制限、監査、およびセキュリティで保護することができます。ただし、サービスの運用に必要な場合のみで、また、microsoft シニアマネージメントのメンバーによって承認された場合にのみ、お客様のロックボックス機能のライセンスが供与されます。

Microsoft では、複数の形式のクラウド配信を使用して、Office 365 を含むオンラインサービスを提供しています。

- **パブリッククラウド**-北米、南米、ヨーロッパ、アジア、オーストラリアなどでホストされている Office 365、Azure、その他のサービスのマルチテナントバージョンが含まれています。
- **国内の雲**-米国以外のすべての独立およびサードパーティ製のクラウド (中国で運用されているものを除く)、ドイツでの office 365 (これは Microsoft が運用していますが、office 365ドイツの受付 kom がドイツのデータを含むモデルでは、顧客データを含む Microsoft の顧客データやシステムへのアクセスを制御し、監視します。
- **行政機関**-米国政府機関のお客様が利用できる Office 365 および Azure サービスが含まれています。

この記事の目的として、Office 365 サービスには、 [exchange online](https://docs.microsoft.com/Exchange/exchange-online)、 [exchange online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)、 [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) ( [OneDrive for](https://docs.microsoft.com/OneDrive/onedrive)business を含む)、 [Skype for business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)などの追加情報が含まれています。[Yammer エンタープライズ](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)アクセスコントロールの一部についてその他の Office 365 サービスは、この記事の対象外です。

## <a name="office-365-access-controls"></a>Office 365 のアクセス制御
アクセス制御の目的で、Office 365 データは、顧客データまたは他の種類のデータとして分類されます。顧客データとは、お客様が office 365 サービスを使用することによって提供される、またはお客様が office サービスを使用することによって提供されるすべてのデータ (電子メール、SharePoint Online コンテンツ、インスタントメッセージなど、office 365 ユーザーによって直接作成またはアップロードされたコンテンツ)。Office 365 に格納されている予定表アイテム、ドキュメント、および連絡先、およびエンドユーザー識別情報 (euii) (ユーザーに固有のデータ、または個人ユーザーに対して linkable されているが、顧客コンテンツは含まれません)。 

その他の種類のデータには、アカウントデータ (管理者がサインアップまたはサービスを購入するときに管理者が提供する情報)、支払いデータ (クレジットカードの詳細などの支払い手段に関する情報) などが含まれます。組織的に識別できる情報 (テナントを識別するために使用できるデータ、または個人のユーザーには linkable されず、お客様のコンテンツは含まれません)、およびシステムメタデータ (構成設定を含むサービスログを含む)、システムの状態、Microsoft IP アドレス、およびサブスクリプションとテナントに関する技術情報)。

Microsoft は、お客様のデータまたはアクセスコントロールのデータへのアクセスを許可しない (お客様のコンテンツや euii へのアクセスなど、環境内の他の種類のデータや機能へのアクセスを管理するために使用されるアクセス制御メカニズムを確立しています。Microsoft パスワード、セキュリティ証明書、およびその他の認証関連データが含まれます。または、Office 365 運用環境への承認されていない物理、論理、またはリモートアクセスがあります。

Microsoft が運用している Office 365 で使用するアクセス制御は、次の3つのカテゴリにグループ化できます。
- 分離コントロール
- 人事管理
- テクノロジコントロール

これらのコントロールを組み合わせると、Office 365 の悪意のあるアクションを防ぎ、検出することができます。Microsoft によって使用される分離、人物、およびテクノロジの各コントロールに加えて、ユーザーによって実装されるコントロールには、次の4つのカテゴリがあります。

Office 365 では、オンプレミス環境でのデータ管理と同じ方法でデータを管理できます。Office 365 の組織をサインアップするユーザーは、自動的にグローバル管理者 (管理者) になります。グローバル管理者は、管理ポータルのすべての機能 (管理センターやリモート PowerShell) にアクセスでき、ユーザーの作成または編集、ユーザーのパスワードの再設定、ユーザーのパスワードの再設定、ユーザーのパスワードの管理、ドメインの管理、顧客ロックボックスの承認を行うことができます。他にも要求。各組織で少なくとも2人の管理者アカウントを指定し、組織の規模に応じて、さまざまな機能を提供する複数の管理者を指定することをお勧めします。管理者の役割とアクセス許可の割り当てについては、「 [office 365 での管理者ロールの割り当て](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504)」および「 [office 365 管理者ロールについ](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D)て」を参照してください。


## <a name="related-links"></a>関連リンク

- [分離コントロール](office-365-isolation-controls.md)
- [人事管理](office-365-personnel-controls.md)
- [テクノロジコントロール](office-365-technology-controls.md)
- [アクセス制御の監視と監査](office-365-monitoring-and-auditing-access-controls.md)
- [Yammer Enterprise でのアクセス制御](office-365-yammer-enterprise-access-controls.md)