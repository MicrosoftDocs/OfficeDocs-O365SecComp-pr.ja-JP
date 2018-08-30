---
title: Office 365 の電子的証拠開示と検索機能の概要
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
description: 電子的証拠開示機能、およびその他の検索機能を Office 365 内での使用の監査と透明度の概要について説明します。
ms.openlocfilehash: 2d5cc2533c195b51f685aebd8da4462518116905
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532181"
---
# <a name="ediscovery-and-search-features"></a>電子情報開示と検索機能 

## <a name="ediscovery"></a>電子情報開示
電子的証拠開示機能は、管理者は、コンプライアンス責任者、1 つの場所を提供し、他の認定ユーザーが Office 365 のユーザーの活動に包括的な調査を実施します。適切なアクセス許可を持つセキュリティ担当者は、検索を実行でき、コンテンツの場所が保持しています。検索結果が、同じから取得した結果、コンテンツの検索、電子的証拠開示の場合は適用される、保留リストの作成します。セキュリティ、電子的証拠開示検索の結果を暗号化し、[高度な電子的証拠開示](https://support.office.com/article/office-365-advanced-ediscovery-fd53438a-a760-45f6-9df4-861b50161ae4)を使用してエクスポートしたデータを分析することができます。

## <a name="content-search"></a>コンテンツ検索
[コンテンツの検索](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)は、以前の電子的証拠開示検索ツールでセキュリティとコンプライアンス センター強化された拡張を提供するパフォーマンス機能の新しい電子的証拠開示検索ツールです。ビジネス ・ サイトのメールボックス、パブリック フォルダー、SharePoint Online サイト、および OneDrive を検索するのにコンテンツの検索を使用できます。コンテンツの検索は、非常に大規模な検索用に作られています。メールボックスおよび検索できるサイトの数に制限はありません。同時に実行できる検索の数に制限はありません。検索、コンテンツ ソースの数、および検索の結果が [検索] ページで、結果をプレビューしたり、それらをローカル コンピューターにエクスポートの詳細ペインで表示されますの推定数を実行するとします。組織に、Office 365 エンタープライズ E5 のサブスクリプションがある場合は、することも[Office 365 の高度な電子的証拠の開示](http://go.microsoft.com/fwlink/p/?LinkID=620116)の強力な分析機能を使用して分析の[結果の準備](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a#prepare)をします。

## <a name="audit-log-search"></a>監査ログの検索
だけでなく、Office 365 の組織内の変更を追跡するには、お客様も監査レポートを表示でき、監査ログをエクスポートします。Office 365 テナントの監査を有効にすると、ユーザーとテナントの管理アクティビティがイベント ログに記録されているし、検索可能にします。たとえば、メールボックスの監査ログをメールボックスの所有者以外のユーザーのメールボックスに対して実行するアクションを追跡するために使用できます。さらに、コンプライアンス担当役員では、検索およびフィルター機能を使用して、管理者がユーザーの管理作業を実行または過去 90 日間でのテナント構成に変更を行った場合に、ユーザーが表示したり、特定のドキュメントをダウンロードした場合、またはを参照してください。検索結果には、ユーザーまたは管理者によって実行された特定の活動についての重要な法的情報を含めることができます。ユーザーと Office 365 にログインしている管理者の活動の説明については、 [Office 365 の Audited の活動](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c#auditlogevents)を参照してください。

SharePoint Online およびビジネスのための OneDrive からのイベントは、その発生の 30 分以内でログに表示されます。Exchange Online からイベントは、発生から 24 時間以内は、監査ログに表示されます。Azure AD からのログイン イベントは、使用可能な回数については、数分、Azure AD からの他のディレクトリ イベント利用可能な発生から 24 時間以内。監査ログの検索結果内のイベントは、詳細な分析もエクスポートできます。(最大 50,000 の項目は、単一の監査ログの検索対象からエクスポートできます。この制限以上のエントリをエクスポートするのには、日付の範囲を減らすか複数の監査ログの検索を実行します。)

次の表では、利用状況のレポートに表示される情報の一部について説明します。[監査ログの詳細なプロパティを Office 365 の](https://support.office.com/article/detailed-properties-in-the-office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3
)詳細については、プロパティが収集した各 Office 365 の作業負荷を参照してください。

| プロパティ | 説明 |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| 日付 | イベントの日付と時刻 |
| ユーザー | アクションを実行したユーザー |
| ClientIP | アクティビティのログが記録されたときに使用されたデバイスの IPv4 または IPv6 アドレスです。 |
| CreationTime | 日付と時刻を世界協定時刻 (UTC) で、ユーザーがアクティビティを実行するとき。 |
| EventSource | イベントが発生したことを識別します。使用可能な値は、SharePoint ObjectModel です。 |
| ID | レポート エントリの ID。ID は、レポートのエントリを一意に識別します。 |
| Operation | ユーザーまたはこのユーザーの活動の結果を表示で選択した値に対応する、活動の名前です。 |
| OrganizationId | イベントが発生した、組織の Office 365 サービスの GUID です。 |
| UserAgent | ブラウザーによって提供されるため、ユーザーのブラウザーに関する情報です。 |
| ユーザー Id | レコードをログに記録される原因となった (、[操作] プロパティで指定された) アクションを実行したユーザー。 |
| UserType | 操作を実行したユーザーの種類です。次の値は、ユーザーの種類を示します。 |
|  | 0 では、通常のユーザーを示します。 |
|  | 2 では、組織の Office 365 の管理者を示します。 |
|  | 3 では、Microsoft データ センター管理者またはデータ センター システム アカウントを示します。 |
| ワークロード | Office 365 サービスのアクティビティが発生しました。このプロパティに指定できる値は次のとおりです。 |
|  | Exchange Online |
|  | SharePoint Online |
|  | OneDrive for Business |
|  | Azure Active Directory のレポート |


Office 365 を検索する詳細な手順のログを監査し、 [Office 365 のセキュリティとコンプライアンス センターで検索の監査ログに記録](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)を参照してください。

## <a name="search-unified-audit-log"></a>統一された監査ログを検索します。
統一された監査ログを検索するのには、監査ログの検索機能は、セキュリティとコンプライアンスの中心を使用できます。Office 365 では、リモート PowerShell を使用してこのログを検索する機能も提供します。具体的には、ビジネス、および Azure AD Exchange Online、SharePoint のオンライン、OneDrive からのユーザーの操作に関連するイベントの統合された監査ログを検索するのには Exchange のオンライン PowerShell の[検索 UnifiedAuditLog コマンドレット](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/Search-UnifiedAuditLog?view=exchange-ps)を使用できます。、指定した日付範囲内のすべてのイベントを検索することや、特定のアクション、アクション、または対象のオブジェクトを実行したユーザーなど、特定の条件に基づいて結果をフィルター処理することができます。管理者は、大規模な日付の範囲指定検索を分割するのには、Exchange オンラインの PowerShell セッションを同時に実行する 3 までを使用できます。
