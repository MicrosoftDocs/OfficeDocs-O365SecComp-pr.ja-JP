---
title: Office 365 での監査とレポート
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
description: 監査とレポート作成サービスの保証と同様に、Office 365 内での機能の概要について説明します。
ms.openlocfilehash: 055a24523260bf14220d5436dcdd010f31f5d8cd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532427"
---
# <a name="auditing-and-reporting-in-office-365"></a>Office 365 での監査とレポート

## <a name="introduction"></a>概要
マイクロソフトのクラウド サービスには、いくつかの監査とレポートのユーザーと、Exchange のオンラインと、SharePoint Online のテナント構成設定への変更など、テナント内の管理作業を追跡するために顧客が使用できる機能が含まれています。およびユーザーによって変更されたドキュメントおよびその他のアイテムにします。お客様より効果的なユーザー エクスペリエンスを管理、リスクの軽減および遵守義務を満たすために、クラウド サービスで利用できるレポートと監査情報を使用できます。

## <a name="office-365-security--compliance-center"></a>Office 365 のセキュリティ センターとコンプライアンス センター
[Office 365 のセキュリティとコンプライアンスの中心](https://support.office.com/article/Go-to-the-Office-365-Security-Compliance-Center-7e696a40-b86b-4a20-afcc-559218b7b1b8)は、Office 365 で、データを保護するためのワンストップ ポータルと、多くの監査およびレポート機能が含まれています。Office 365 のコンプライアンス センターの発展することをお勧めします。セキュリティとコンプライアンス センターが組織ではデータが格納されるように設計されています保護やコンプライアンスのニーズ、またはユーザーと管理者のアクティビティを監査します。組織の Office 365 のデータのすべてのコンプライアンスを管理するためには、セキュリティとコンプライアンスの中心を使用できます。セキュリティとコンプライアンス ・ センターにアクセスすることができます[http://protection.office.com](http://protection.office.com/)、Office 365 管理者アカウントを使用します。

セキュリティとコンプライアンスのセンターには、いくつかの機能へのアクセスを提供するナビゲーション ペインが含まれています。
- **アラート**を使用すると、アラートの管理、セキュリティ関連の警告を表示、および[高度なセキュリティ管理](https://support.office.com/article/overview-of-office-365-cloud-app-security-81f0ee9a-9645-45ab-ba56-de9cbccab475)を使用して、高度なアラートを管理できます。 
- **アクセス許可**- は、[アクセス許可を割り当てる](https://support.office.com/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76)コンプライアンス管理者、電子的証拠開示マネージャー、およびその他のユーザーなど、組織内のユーザーにセキュリティとコンプライアンス センターでのタスクを実行できるようにするようにできます。セキュリティとコンプライアンスの中心でほとんどの機能のアクセス許可を割り当てることができますが、Exchange 管理センターと SharePoint の管理センターを使用して他のアクセス許可を構成する必要があります。
- **脅威の管理**のを作成し、電子メールのフィルタ リングを構成するのには、組織の[データ損失防止](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)(DLP) ポリシーを設定するのには[Office 365 のモバイル デバイスの管理](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)] を使用してデバイス管理のポリシーを適用することができます。マルウェア対策、DomainKeys 確認メール (DKIM)、安全な添付ファイル、安全なリンク、およびアプリケーションのアクセス許可。
- **データ ・ ガバナンス**の[電子メールや Office 365 には、他のシステムから SharePoint データをインポート](https://support.office.com/article/Import-PST-files-or-SharePoint-data-to-Office-365-ba688e0a-0fcb-4bd7-8e57-2b669564ea84)するに[アーカイブ メールボックスを構成](https://support.office.com/article/Enable-archive-mailboxes-in-the-Office-365-Security-Compliance-Center-268a109e-7843-405b-bb3d-b9393b2342ce)するには、でき、電子メールやその他のコンテンツを組織内の[アイテム保持ポリシー](https://support.office.com/article/Retention-in-the-Office-365-Security-Compliance-Center-2a0fc432-f18c-45aa-a539-30ab035c608c)を設定します。
- **検索と調査**の Exchange Online のメールボックス、グループ、および SharePoint のパブリック フォルダーの間でのアクティビティに即座に表示する[コンテンツの検索](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)、[監査ログ](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)検疫、および[電子的証拠開示のサポート ・ リクエスト管理](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)のツールが用意されていますオンライン、およびビジネスのための OneDrive です。
- **レポート**- を使用すると、SharePoint のオンライン、OneDrive のビジネス、オンラインの Exchange と Azure AD の[レポート](https://support.office.com/article/Reports-in-the-Office-365-Security-Compliance-Center-7acd33ce-1ec8-49fb-b625-43bac7b58c5a)を簡単にアクセスできます。
- **サービスの保証**- マイクロソフトがセキュリティ、プライバシー、および Office 365、Azure、Microsoft Dynamics CRM Online、Microsoft Intune、およびその他のクラウド サービスの世界標準の遵守を維持する方法について説明します。サード ・ パーティ製の ISO、SOC、他の監査レポートとテストされ、Office 365 のサード パーティの監査人が確認されているさまざまなコントロールの詳細について説明監査対象のコントロールへのアクセスが含まれています。

## <a name="service-assurance"></a>サービス保証
規制が厳しい業界のお客様の多くは、広範なコンプライアンス要件が適用されます。顧客には独自のリスク評価を実行するには、Office 365 で、データのプライバシーおよびセキュリティを維持する方法に関する詳細な情報が必要があります。マイクロソフトのクラウド サービスでお客様のデータのプライバシーおよびセキュリティにし、操作、および独立したコンプライアンス ・ レポートと評価に簡単にアクセスの透明なビューを提供することで顧客の信頼を獲得するに努めています。

サービスの保証は、操作し、マイクロソフトがセキュリティ、プライバシー、および Office 365 の顧客データのコンプライアンスを維持する方法についての情報の透明度を提供します。ホワイト ・ ペーパー、Faq、およびその他の資料のライブラリとデータの暗号化、データの復元、セキュリティ ・ インシデント管理などのトピックを Office 365 でのサード ・ パーティによる監査レポートが含まれています。お客様は、独自の規制のリスク評価を実行するのには、この情報を使用できます。コンプライアンス担当者は、アクセスできるようにサービスを保証するサービス保証ユーザー ロールを割り当てることができます。テナント管理者は、 [Microsoft クラウド サービスの信頼ポータル](http://aka.ms/STP)(STP) を通じてサービスの保証のダッシュ ボード内の情報へのアクセスにも、独立した監査役など、外部のユーザーを提供できます。STP にアクセスする方法の詳細についてを参照してください[ビジネス、Azure では、Dynamics CRM オンラインの Office 365 のサービスを信頼のポータルを開始サブスクリプション](http://aka.ms/STPHelp)。

## <a name="onedrive-for-business-admin-center"></a>ビジネス管理センターの OneDrive
新しい Microsoft OneDrive 管理センターでは、迅速に解決できますし、ビジネスの設定を 1 つの場所の組織の OneDrive を簡単に管理します。OneDrive 管理センターを使用するには、onedrive.com へのアクセスを許可する必要があります。組織のグローバル管理者または SharePoint 管理者ロールを持つユーザー設定の管理も必要です。アクセス ビジネス管理センターにある [プレビューの OneDrive [https://admin.onedrive.com](https://admin.onedrive.com/)。

キーの機能には、監査ログを検索、DLP、保存、電子的証拠開示、使用、および警告のような主要なシナリオのリンクを Office 365 のセキュリティとコンプライアンスのセンターを管理者に提供する、コンプライアンスの領域が含まれます。

## <a name="related-links"></a>関連リンク
- [電子情報開示と検索機能](office-365-ediscovery-and-search-features.md)
- [Office 365 のレポート作成機能](office-365-reporting-features.md)
- [Office 365 マネージメント アクティビティ API](office-365-management-activity-api.md)
- [Office 365 のメールボックスの移行](office-365-mailbox-migrations.md)
- [Office 365 のエンジニアリングのための内部ログ記録](office-365-internal-logging.md)