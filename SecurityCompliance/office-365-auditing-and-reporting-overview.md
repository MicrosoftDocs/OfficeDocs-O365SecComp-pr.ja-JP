---
title: Office 365 での監査とレポート
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 12/03/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- M365-analytics
description: Office 365 内の監査およびレポート機能の概要と、サービス保証について説明します。
ms.openlocfilehash: e2fd596279743ad72a3632ba09ec28142e9322f4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30221017"
---
# <a name="auditing-and-reporting-in-office-365"></a>Office 365 での監査とレポート

## <a name="introduction"></a>はじめに
Microsoft クラウドサービスには、Exchange online および SharePoint online テナントの構成設定に加えられた変更など、テナント内のユーザーおよび管理アクティビティを追跡するために使用できるいくつかの監査およびレポート機能が含まれています。また、ユーザーによってドキュメントやその他のアイテムに加えられた変更。お客様は、クラウドサービスで利用可能な監査情報とレポートを使用して、ユーザーの作業をより効果的に管理したり、リスクを軽減したり、コンプライアンスの義務を履行したりできます。

## <a name="office-365-security--compliance-center"></a>Office 365 のセキュリティ センターとコンプライアンス センター
[office 365 Security & コンプライアンスセンター](https://support.office.com/article/Go-to-the-Office-365-Security-Compliance-Center-7e696a40-b86b-4a20-afcc-559218b7b1b8)は、office 365 のデータを保護するためのワンストップポータルで、多くの監査およびレポート機能を備えています。これは、Office 365 コンプライアンスセンターを発展させたものです。セキュリティ & コンプライアンスセンターは、データ保護または法令遵守のニーズ、あるいはユーザーおよび管理者のアクティビティを監査する必要がある組織向けに設計されています。セキュリティ & コンプライアンスセンターを使用して、組織のすべての Office 365 データのコンプライアンスを管理することができます。Office 365 管理者アカウントを使用して[http://protection.office.com](http://protection.office.com/) 、セキュリティ & コンプライアンスセンターにアクセスできます。

セキュリティ & コンプライアンスセンターには、いくつかの機能へのアクセスを提供するナビゲーションウィンドウが含まれています。
- **通知**- [Office 365 Cloud App security](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/office-365-cas-overview)を使用して、アラートの管理、セキュリティ関連の警告の表示、高度な通知の管理を行うことができます。 
- **アクセス許可**-コンプライアンス管理者、電子情報開示マネージャー、その他の[アクセス許可](https://support.office.com/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76)を組織内のユーザーに割り当てることができるようにします。これにより、セキュリティ & コンプライアンスセンターでタスクを実行できるようになります。セキュリティ & コンプライアンスセンターでは、ほとんどの機能に対するアクセス許可を割り当てることができますが、その他のアクセス許可は Exchange 管理センターおよび SharePoint 管理センターを使用して構成する必要があります。
- **脅威管理**- [Office 365 モバイルデバイス管理](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)を使用してデバイス管理ポリシーを作成および適用し、組織の[データ損失防止](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)(DLP) ポリシーを設定し、電子メールフィルターを構成することができます。マルウェア対策、domainkeys で特定されたメール (dkim)、安全な添付ファイル、安全なリンク、および OAuth アプリ。
- **データガバナンス**-[他のシステムから Office 365 に電子メールまたは SharePoint データをインポート](https://support.office.com/article/Import-PST-files-or-SharePoint-data-to-Office-365-ba688e0a-0fcb-4bd7-8e57-2b669564ea84)して、[アーカイブメールボックスを構成](https://support.office.com/article/Enable-archive-mailboxes-in-the-Office-365-Security-Compliance-Center-268a109e-7843-405b-bb3d-b9393b2342ce)し、組織内の電子メールおよびその他のコンテンツの[保持ポリシー](https://support.office.com/article/Retention-in-the-Office-365-Security-Compliance-Center-2a0fc432-f18c-45aa-a539-30ab035c608c)を設定できます。
- **検索 & 調査**-[コンテンツ検索](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)、[監査ログ](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)、検疫、[電子情報開示のケース管理](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)ツールを提供して、Exchange Online のメールボックス、グループ、パブリックフォルダー、SharePoint にわたるアクティビティをすばやくドリルインします。オンラインおよび OneDrive for business。
- **レポート**-SharePoint Online、OneDrive for business、Exchange Online、および Azure AD の[レポート](https://support.office.com/article/Reports-in-the-Office-365-Security-Compliance-Center-7acd33ce-1ec8-49fb-b625-43bac7b58c5a)にすばやくアクセスできます。
- **サービスアシュアランス**-Microsoft が Office 365、Azure、microsoft Dynamics CRM Online、microsoft Intune、その他のクラウドサービスのグローバル標準に関するセキュリティ、プライバシー、コンプライアンスを維持する方法についての情報を提供します。また、サードパーティの ISO、SOC、その他の監査レポート、および監査対象のコントロールにアクセスすることもできます。これにより、サードパーティの監査者が Office 365 についてテストおよび検証したさまざまなコントロールに関する詳細が提供されます。

## <a name="service-assurance"></a>サービス保証
規制された業界のお客様の多くは、幅広いコンプライアンス要件に従います。独自のリスク評価を実行するために、多くの場合、Office 365 がデータのセキュリティとプライバシーをどのように維持するかについて詳細な情報をお客様に提供します。Microsoft は、クラウドサービスの顧客データのセキュリティとプライバシーに関する情報を提供し、その操作を透過的に表示することにより、お客様の信頼を得ることができます。また、コンプライアンスに関する個別のレポートや評価へのアクセスが容易になります。

サービス保証は、Microsoft が Office 365 でお客様のデータのセキュリティ、プライバシー、コンプライアンスをどのように維持しているかについて、運用の透明性と情報を提供します。この記事には、データの暗号化、データの復元、セキュリティインシデントの管理など、Office 365 に関するホワイトペーパー、faq、およびその他の資料のライブラリと共に、サードパーティの監査レポートが含まれています。お客様は、この情報を使用して、独自の規制リスク評価を実行できます。コンプライアンス責任者は、サービスアシュアランスへのアクセス権をユーザーに付与するために、"サービス保証ユーザー" 役割を割り当てることができます。また、テナント管理者は、 [Microsoft Cloud service Trust Portal](http://aka.ms/STP) (STP) を使用してサービス保証ダッシュボードの情報にアクセスすることによって、独立した監査者などの外部ユーザーを提供することもできます。STP にアクセスする方法の詳細については、「 [Service Trust Portal for Office 365 for business、Azure、および Dynamics CRM Online サブスクリプション](http://aka.ms/STPHelp)」を参照してください。

## <a name="onedrive-for-business-admin-center"></a>OneDrive for business 管理センター
新しい Microsoft OneDrive 管理センターを使用すると、組織の OneDrive for business の設定を1か所ですばやく簡単に管理できます。OneDrive 管理センターを使用するには、onedrive.com へのアクセスを許可する必要があります。また、組織のグローバル管理者、または SharePoint 管理者の役割を持つカスタムの管理者である必要があります。OneDrive for business 管理センターのプレビューにアクセス[https://admin.onedrive.com](https://admin.onedrive.com/)します。

主な機能には、監査ログの検索、DLP、保持、電子情報開示、警告の処理などの主要なシナリオについて、管理者に Office 365 セキュリティおよびコンプライアンスセンターへのリンクが提供されるコンプライアンス領域が含まれています。

## <a name="related-links"></a>関連リンク
- [電子情報開示と検索機能](office-365-ediscovery-and-search-features.md)
- [Office 365 のレポート作成機能](office-365-reporting-features.md)
- [Office 365 マネージメント アクティビティ API](office-365-management-activity-api.md)
- [Office 365 のメールボックスの移行](office-365-mailbox-migrations.md)
- [Office 365 のエンジニアリングのための内部ログ記録](office-365-internal-logging.md)