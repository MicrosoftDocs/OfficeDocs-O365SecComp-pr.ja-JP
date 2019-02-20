---
title: Office 365 のレポート作成機能
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
- M365-analytics
description: Office 365 内のレポート機能の説明。
ms.openlocfilehash: f750ac6647199ef14bd6605535797e00c1cab961
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090899"
---
# <a name="office-365-reporting-features"></a>Office 365 のレポート作成機能 

## <a name="introduction"></a>概要
Office 365 のレポート機能には、Azure Active Directory (AD)、Exchange Online、デバイス管理、監督レビュー、データ損失防止 (DLP) のさまざまな監査レポートが用意されています。これらは、Office 365 アクティビティレポートとは異なります。

## <a name="office-365-reports-dashboard"></a>Office 365 レポートダッシュボード
office 365 管理センタープレビューの [レポート] ダッシュボードには、office 365 全体の使用状況のアクティビティが表示されます。Office 365 の全体管理者、または Exchange online、SharePoint online、または Skype for business の管理者は、そのサービスの使用状況について詳細な洞察を得ることができます。レポートでは、特定の office 365 サービスを使用しているユーザー数、office Professional Plus をアクティブ化したユーザーの数、組織を通過するメールの量などの洞察を得ることができます。レポートは、過去7日、30日、90日、および180日に使用できます。

次のレポートを使用できます。
- [電子メールアクティビティレポート](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Microsoft Office ライセンス認証レポート](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [SharePoint Online サイトの利用状況レポート](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [OneDrive for business の使用状況レポート](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Yammer アクティビティ レポート](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [Skype for business アクティビティレポート](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [Skype for business ピアツーピアアクティビティレポート](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [Skype for business 電話会議開催者レポート](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [Skype for business 電話会議参加者アクティビティレポート](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

詳細については、「 [Office 365 管理センターのアクティビティレポート](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)」を参照してください。


## <a name="azure-active-directory-reports"></a>Azure Active Directory レポート
Office 365 では、認証および id 管理に Azure AD を使用しています。Office 365 管理者は、Azure によって生成されたレポートを使用して、異常なアクティビティやデータへの不正なアクセスを検索できます。Azure AD のアクセスと使用状況レポートを使用して、組織のディレクトリの整合性とセキュリティを把握することができます。この情報を使用すると、管理者はセキュリティリスクが発生する可能性を判断して、リスクを軽減するための計画を適切に行うことができます。

Azure AD レポートは、Microsoft Excel にエクスポートして、監査ログの検索結果などの Office 365 の他のデータと相互に関連付けして、アクセス、認証、およびアプリケーションレベルのアクティビティに関する洞察を提供することができます。Azure AD Premium が有効になっている場合、高度な異常とリソース利用状況レポートを使用できます。これらの高度なレポートを使用すると、組織のセキュリティの状況を改善し、デバイスへのアクセスとアプリケーションの使用に関する分析を活用して潜在的な脅威に対処することができます。詳細については、「 [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/)」を参照してください。

## <a name="exchange-online-audit-reports"></a>Exchange Online 監査レポート
exchange online 監査レポートには、メールボックスアクセスの詳細、および組織の Exchange online テナントに対する管理者による変更の詳細が含まれています。メールボックスの監査を有効にすると、次の表のタスクを使用してレポートを実行し、Exchange Online の監査ログをエクスポートできます。

>**注**: 監査対象のイベントがそのメールボックスの監査ログに保存されるように、各メールボックスのメールボックス監査ログを有効にする必要があります。メールボックスのメールボックス監査ログが有効になっていない場合、そのメールボックスのイベントは監査ログに保存されず、メールボックス監査レポートに表示されません。詳細については、「[メールボックスの監査を有効にする](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918)」を参照してください。

| タスク | 説明 |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [所有者以外のメールボックス アクセスのレポートの実行](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | メールボックスの所有者以外のユーザーによってアクセスされたメールボックスの一覧が表示されます。このレポートには、メールボックスにアクセスしたユーザー、メールボックスで行われた操作、および操作が成功したかどうかに関する情報が含まれています。 |
| [メールボックス監査ログのエクスポート](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | メールボックス監査ログには、メールボックスの所有者以外のユーザーが実行したメールボックス内のアクセスおよびアクションに関する情報が含まれています。管理者は、レポートを生成するための日付範囲と共にメールボックスを指定できます。ログは XML でエクスポートされ、管理者によって決定されたメッセージに添付され、特定のユーザーに送信されます。 |
| [管理者の役割グループ レポートの実行](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | 管理者の役割グループは、ユーザーに管理権限を割り当てるために使用されます。これらの権限を使用すると、ユーザーは、パスワードのリセット、メールボックスの作成または変更、他のユーザーへの管理者特権の割り当てなどの管理タスクを実行できます。管理役割グループレポートには、メンバーの追加や削除など、役割グループに加えられた変更が表示されます。 |
| [管理者監査ログを表示する](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | 管理者監査ログレポートには、Exchange Online の管理者によって実行されたすべての作成、更新、および削除の機能が一覧表示されます。ログエントリは、実行されたコマンドレット、使用されたパラメーター、コマンドレットを実行したユーザー、および影響を受けたオブジェクトに関する情報を提供します。 |
| [メールボックスのコンテンツの検索と保持](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | メールボックスのインプレース電子情報開示またはインプレース保持の設定に対する変更の詳細を提供します。 |
| [管理者監査ログをエクスポートする](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | 管理者監査ログには、Exchange Online での作成、更新、削除などの特定の管理操作が記録されます。ログからの結果が XML にエクスポートされ、管理者はこのログを一連のユーザーに送信することを選択できます。 |
| [メールボックスごとの訴訟ホールド レポートの実行](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | メールボックスに対する訴訟ホールドの設定に対する変更の詳細を提供します。 |
| [外部の管理者監査ログの表示とエクスポート](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | 外部管理者によって実行されたアクションの詳細を含みます。エントリは、実行されたコマンドレット、使用されたパラメーター、Exchange Online でオブジェクトを作成、変更、または削除するアクションに関する情報を提供します。 |

## <a name="device-compliance-reports"></a>デバイスコンプライアンスレポート
office 365 モバイルデバイス管理 (MDM) を使用して office 365 組織に接続している場合は、モバイルデバイスを管理およびセキュリティ保護することができます。職場のメール、予定表、連絡先、およびドキュメントへのアクセスに使用されるスマートフォンやタブレットなどのモバイルデバイスは、従業員がいつでも、どこからでも働くことができるようにするために、大きな役割を果たします。そのため、組織の情報を保護することが重要です。Office 365 MDM を使用して、デバイスのセキュリティポリシーとアクセスルールを設定したり、紛失または盗難にあったモバイルデバイスを消去したりできます。

MDM コンプライアンスレポート Office 365 データにアクセスするモバイルデバイスをセキュリティで保護するために組織によって設定されたポリシーの概要を説明します。このレポートを使用すると、コンプライアンスの状態、報告された違反、ブロックされたデバイス、セキュリティポリシーの結果としてワイプされたデバイスの数によるデバイスのフィルター処理を行うことができます。詳細については、「Office 2010 の[モバイルデバイス管理の概要](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)」を参照してください。

## <a name="data-loss-prevention"></a>データ損失防止
DLP ポリシーは、組織内の情報のセキュリティとフローを管理するのに役立ちます。アプリケーション内 DLP ポリシーヒントを使用して、コンテンツへのアクセスをブロックしたり、データを暗号化したり、ポリシーおよびポリシー違反のユーザーに通知したりするためのポリシーを設定できます。DLP レポートでは、ポリシーとルールの一致、オーバーライド、誤検知の数についての洞察が得られます。

Office 365 管理センターを使用すると、DLP ポリシーによって検出されたメッセージ数に関する情報を、グラフィカルなグラフまたは表の形式で表示できます。具体的には、送受信されたメールの dlp ポリシーは、送受信されたメールの dlp ルールと一致します。また、Exchange 管理センターを使用して、過去24時間以内に各ポリシーの一致、オーバーライド、誤検知の数を表示することもできます。ただし、このデータはグラフとしては使用できません。レポートをダウンロードして Excel で使用する場合は、どのメッセージを送信したか、どの日に、どのポリシーがトリガーされたかなど、さらに詳細を確認できます。詳細については、「 [DLP ポリシー検出に関するレポートの表示](https://technet.microsoft.com/en-us/library/jj889415(v=exchg.150).aspx)」を参照してください。

## <a name="auditing-in-yammer-enterprise"></a>Yammer Enterprise での監査
yammer Enterprise を使用すると、管理者は yammer ネットワークからユーザーアクティビティデータを yammer[データエクスポート API](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2)経由で、または yammer ネットワーク管理ページから手動でエクスポートすることができます。ログをエクスポートする機能は、Yammer のネットワーク管理者に制限されます。(すべての Office 365 グローバル管理者は Yammer ネットワーク管理者です。)

次のデータをエクスポートできます。

| ファイル名 | 説明 |
|----------------------------|-------------------------------------------------------------------------|
| ユーザー .csv | ネットワーク内のすべての新規、保留中、および中断中のユーザー |
| メッセージ .csv | ネットワーク内のすべてのメッセージ |
| ファイル .csv (メタデータ) | ファイル名、ファイル API URL、アップローダー ID、アップロードされたファイルなどのメタデータ。 |
| ファイル .csv (元のファイル) | ユーザーが Yammer にアップロードした元のファイルの Zip ファイル |
| トピック .csv | ネットワーク上で作成されたトピック |
| .csv | ネットワーク内のユーザーによって作成されたページ (メモ) |
| 管理者 .csv | ネットワーク上のすべての検証された管理者 |
| ネットワーク csv | すべての Yammer 外部ネットワーク |

*表 3-お客様がエクスポートできる Yammer ネットワークデータファイル*

Yammer エンタープライズデータは、Office 365 アクティビティレポートからも入手できます。さらに、Yammer は、Office 365 Management Activity API を介して追加のログを公開すること、および Power BI を使用したデータの理由を示しています。これらの機能の詳細については、「 [Office ロードマップ](https://fasttrack.microsoft.com/roadmap?filters=yammer)」を参照してください。
