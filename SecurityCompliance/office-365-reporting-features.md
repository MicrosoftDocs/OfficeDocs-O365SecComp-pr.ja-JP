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
ms.collection: Strat_O365_Enterprise
description: レポート Office 365 の機能の説明。
ms.openlocfilehash: 5a448089de5d517b81551269416c4a6f91599725
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532736"
---
# <a name="office-365-reporting-features"></a>Office 365 のレポート作成機能 

## <a name="introduction"></a>概要
レポート機能は、Office 365 では、Azure Active Directory (AD)、Exchange Online では、デバイスの管理、監督者の確認、およびデータ損失防止 (DLP) の監査レポートのさまざまなを提供します。これらは、さまざまな Office 365 の利用状況レポートとは別です。

## <a name="office-365-reports-dashboard"></a>Office 365 のレポートのダッシュ ボード
Office 365 の管理センターのプレビューでレポートのダッシュ ボードには、Office 365 の間で状況が表示されます。Office 365 のグローバル管理者、Exchange のオンライン、SharePoint Online では、またはビジネス管理者の場合は、Skype は、そのサービスの利用状況の詳細な洞察を取得できます。レポートには、特定の Office 365 サービス、メールの量は、組織を通じて転送されると Office Professional Plus を有効にするユーザーの数を消費しているユーザーの数などの情報を提供できます。レポートは、最終 7、30、90、および 180 日間利用できます。

次のレポートがあります。
- [電子メール活動のレポート](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Microsoft Office のライセンス認証のレポート](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [オンラインの SharePoint サイトの使用状況レポート](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [ビジネスの利用状況のレポートの OneDrive](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Yammer の活動レポート](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [Skype のビジネス活動のレポート](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [Skype ビジネス ピア ツー ピア アクティビティ レポート](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [Skype ビジネス会議の主催者レポート](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [Skype の会議の参加者がビジネス活動のレポート](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

詳細については、 [Office 365 の管理センターでの活動レポート](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)を参照してください。


## <a name="azure-active-directory-reports"></a>Azure Active Directory のレポート
Office 365 は、認証および id 管理のための Azure AD を使用します。Office 365 の管理者は、異常な動作と、データへの不正アクセスを検索する、Azure によって生成されたレポートを使用できます。Azure AD でのアクセスと使用率レポートを使用するには完全性と、組織のディレクトリのセキュリティを把握します。この情報により、管理者がより適切に判断、考えられるセキュリティ上のリスクがありますそれらのリスクを軽減するために十分に考慮することができるようにします。

Azure AD レポートを Excel にエクスポートし、アクセス、認証、およびアプリケーション レベルのアクティビティに関する洞察を提供するのには、監査ログの検索の結果などから、Office 365 は、他のデータと相関関係します。Azure AD プレミアムを有効にすると高度な異常とリソースの利用状況レポートを利用できます。これらの詳細なレポートが組織のセキュリティ体制と組織を向上させるためにヘルプがデバイスへのアクセスとアプリケーションの使用状況の分析機能を活用することで潜在的な脅威に対応します。詳細については、 [Azure Active Directory のレポート](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/)を参照してください。

## <a name="exchange-online-audit-reports"></a>Exchange オンライン監査レポート
Exchange Online の監査レポートには、メールボックスへのアクセスと組織の Exchange Online のテナントに、管理者によって行われた変更の詳細が含まれます。メールボックスの監査を有効にすると、レポートを実行し、Exchange Online の監査ログをエクスポートするのには次の表に、タスクを使用できます。

>**注**: メールボックス監査ログ メールボックスごとに監査対象のイベントは、そのメールボックスの監査ログに保存できるようにするを有効にする必要があります。メールボックスの監査ログは、メールボックスを有効になっていない、そのメールボックスのイベントが監査ログに保存されませんし、メールボックスの監査レポートには表示されません。詳細については、[メールボックスの監査を有効にする](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918)を参照してください。

| タスク | 説明 |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [所有者以外のメールボックス アクセスのレポートの実行](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | メールボックスの所有者以外のユーザーによってアクセスされたメールボックスの一覧を表示します。レポートには、メールボックスにアクセスしたユーザーに関する情報が含まれている、メールボックスに行った操作、操作が成功したかどうかと。 |
| [メールボックス監査ログのエクスポート](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | メールボックス監査ログには、アクセス、およびメールボックスの所有者以外のユーザーによるメールボックス内のアクションに関する情報が含まれています。管理者は、メールボックスとは、レポートを生成する日付範囲を指定できます。ログは XML にエクスポートをメッセージに添付、管理者によって決定される特定のユーザーに送信します。 |
| [管理者の役割グループ レポートの実行](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | 管理者の役割グループを使用して、ユーザーに管理者権限を付与します。これらの特権は、ユーザーがパスワードをリセットするなどの管理タスクを実行、作成、または、メールボックスを変更できるようにし、他のユーザーに管理者権限を割り当てます。管理者の役割グループ レポートでは、役割グループに追加またはメンバーの削除を含む変更が表示されます。 |
| [管理者の監査ログを表示します。](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | 管理監査ログ レポートの一覧を作成、更新し、Exchange online 管理者によって実行される機能を削除します。ログ エントリでは、どのコマンドレットが実行された、どのようなパラメーターが使用された、コマンドレットを実行するとどのようなオブジェクトが影響を受けた情報を提供します。 |
| [メールボックスのコンテンツの検索と保留リスト](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | メールボックスの場所に電子的証拠開示またはインプレース保持の設定への変更の詳細を提供します。 |
| [管理者の監査ログをエクスポートします。](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | 特定の管理操作は次のように作成、管理監査ログ レコードは、更新し、Exchange のオンラインを削除します。ログからの結果は、XML にエクスポートし、ユーザーのセットにこのログを送信するのには管理者が選択できます。 |
| [メールボックスごとの訴訟ホールド レポートの実行](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | 訴訟への変更の詳細については、メールボックスの設定を保持を提供します。 |
| [外部の管理者監査ログの表示とエクスポート](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | 外部の管理者によって実行されるアクションの詳細が含まれています。エントリは、どのコマンドレットでは実行、作成、変更、または Exchange Online 内のオブジェクトを削除するアクション、およびどのようなパラメーターが使用された、情報を提供します。 |

## <a name="device-compliance-reports"></a>デバイスのコンプライアンス ・ レポート
管理し、Office 365 のモバイル デバイス管理 (MDM) を使用して、Office 365 の組織に接続しているときにモバイル デバイスをセキュリティで保護できます。スマート フォンや仕事の電子メール、予定表、連絡先にアクセスするために使用されているタブレットなどのモバイル デバイスとドキュメントは、従業員が、いつでも使用することであることを確認することで、任意の場所からの重要な部分を再生します。その結果、組織の情報を保護することが重要です。デバイスのセキュリティ ポリシーとアクセス ルールを設定するのには、紛失や盗難にしている場合は、モバイル デバイスをワイプするのには、Office 365 の MDM を使用できます。

MDM コンプライアンス ・ レポートは、Office 365 のデータにアクセスしているモバイル デバイスをセキュリティで保護するように組織で設定されているポリシーの概要を提供します。レポートは、準拠の状態、報告された違反、ブロックされたデバイス、およびデバイスの数は、セキュリティ ポリシーの結果として消去されたデバイスのフィルター処理できます。詳細については、[概要のモバイル デバイスの管理](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)を参照してください。

## <a name="data-loss-prevention"></a>データ損失防止
DLP ポリシーは、組織内の情報のフローとセキュリティの管理に役立ちます。コンテンツへのアクセスをブロックし、データを暗号化または、ポリシーとアプリケーションの DLP ポリシーのヒントを使用してポリシー違反をユーザーに通知のポリシーを設定することができます。DLP のレポートでは、ポリシーとルールの一致、オーバーライド、および偽陽性の数に関する洞察を提供します。

Office 365 の管理センターを使用すると、グラフまたは表形式のいずれかで DLP ポリシーによって検出されたメッセージの数に関する情報を表示します。具体的には、DLP ポリシーの一致するが送信され、メールを受信し、送信および受信したメールの DLP ルールに一致します。Exchange 管理センターを使用して、過去 24 時間以内、マッチ、オーバーライド、および各ポリシーに対して偽陽性の数を表示することもできます。ただし、このデータはグラフとして使用可能ではありません。Excel でレポートをダウンロードする場合など、どのような 1 日にどのようなメッセージの送信者、さらに多くの詳細を表示することができ、トリガーがどのようなポリシーと一致します。詳細については、 [DLP ポリシーの検出に関するレポートを表示する](https://technet.microsoft.com/en-us/library/jj889415(v=exchg.150).aspx)を参照してください。

## <a name="auditing-in-yammer-enterprise"></a>Yammer の企業での監査
エンタープライズ[データ エクスポート API の Yammer](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2)のまたは手動で、Yammer ネットワークの管理] ページでは、Yammer ネットワークからユーザーの利用状況データをエクスポートする機能を管理者に提供 Yammer。ログをエクスポートする機能は、Yammer ネットワークの管理者に制限されます。(Office 365 のすべてのグローバル管理者は、Yammer ネットワーク管理者です)。

次のデータをエクスポートすることができます。

| ファイル名 | 説明 |
|----------------------------|-------------------------------------------------------------------------|
| ユーザー.csv | ネットワーク上のすべての新しい保留中のおよび中断されたユーザー |
| Messages.csv | ネットワーク内のすべてのメッセージ |
| Files.csv (メタデータ) | ファイル名などのメタデータはファイル API の URL、アップローダーの ID にアップロードされたなどです。 |
| Files.csv (元のファイル) | Yammer にユーザーによってアップロードされた元のファイルの zip ファイル |
| Topics.csv | ネットワーク上に作成されたトピック |
| Pages.csv | ネットワーク内のユーザーによって作成されたページ (メモ) |
| Admins.csv | ネットワーク上の管理者ことを確認できました |
| Networks.csv | Yammer のすべての外部ネットワーク |

*表 3 - 顧客からのエクスポートに利用できる Yammer ネットワークのデータ ファイル*

Yammer のエンタープライズ データも Office 365 の活動レポートを使用できます。また、Yammer 電源双を使用してデータを Office 365 の管理アクティビティ API を使用して追加のログ記録を公開することとするために機能を熱心に取り組んでいるとします。これらの機能の詳細については、 [Office のロードマップ](https://fasttrack.microsoft.com/roadmap?filters=yammer)を参照してください。
