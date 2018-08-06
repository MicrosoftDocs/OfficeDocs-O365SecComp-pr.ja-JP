---
title: EOP の機能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: 次の表は、Exchange Online Protection (EOP) でホストされた電子メール フィルタリング サービスで使用可能な機能の一覧です。
ms.openlocfilehash: 764ee616467cba29126139fdbf43f278dad30769
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026674"
---
# <a name="eop-features"></a>EOP の機能

次の表は、Exchange Online Protection (EOP) でホストされた電子メール フィルタリング サービスで使用可能な機能の一覧です。 
  
> [!TIP]
> 「[ビジネス向けの Office 365 ロードマップ](https://office.microsoft.com/en-us/products/office-365-roadmap-FX104343353.aspx)」は新機能を調べるためのお勧めの情報源です。異なる EOP サブスクリプション プランで使用可能な機能のより広範な説明については、「[Exchange Online Protection サービスの説明](https://go.microsoft.com/fwlink/p/?LinkId=320619)」を参照してください。 
  
|||
|:-----|:-----|
|**機能** <br/> |**説明** <br/> |
|**スパム対策保護** <br/> ||
|受信スパム検出  <br/> |受信スパム対策保護機能は常に有効であり、無効にすることはできません。接続フィルターやコンテンツ フィルター ポリシーを使用して、カスタムの設定を構成できます。  <br/> EOP スタンドアロン向け: 既定では、EOP のコンテンツ フィルターは各受信者の迷惑メール フォルダーにスパム検出のメッセージを送信します。ただし、オンプレミスのメールボックスの**迷惑メール フォルダーにメッセージを移動する**アクションが動作するようにするのには EOP によって追加された迷惑メールのヘッダーを検出するために、オンプレミスのサーバーに 2 つの Exchange トランスポート ルールを構成する必要があります。詳細については、[各ユーザーの迷惑メール フォルダーに迷惑メールがルーティングされるようにする](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)を参照してください。           |
|送信スパム検出  <br/> |送信メールを送信するためのサービスを使用すると、それによってサービスが、それぞれの受信者を使用している組織を保護する場合、送信スパム対策保護が常に有効にします。受信フィルタ リングを送信するよう接続フィルターおよびコンテンツ フィルターのスパム フィルターがで構成されています。送信スパムのフィルタ リング設定が構成可能なされていないが、スパムの送信疑わしいとブロックの送信メッセージの管理の通知を構成するのに使用できるポリシー設定。詳細については、[送信スパム ポリシーを構成する](../configure-the-outbound-spam-policy.md)を参照してください。<br/> |
|NDR バックスキャター保護  <br/> |Backscatter の NDR の詳細については、設定の[高度な迷惑メール フィルターのオプション](../advanced-spam-filtering-asf-options.md)と同様に[Backscatter メッセージおよび EOP](../backscatter-messages-and-eop.md)NDR backscatter を参照してください。  <br/> |
|バルク メール フィルタリング  <br/> |EOP には、大量の電子メール メッセージを識別するための検出方法が強化されました。ユーザー インターフェイスからの一括電子メール メッセージをマークするサービスを構成することができます。一括メール メッセージ ヘッダーのタイムスタンプを検索しより積極的に一括メールをフィルターするトランスポート ルールを作成することもできます。一括メールの詳細についてを参照してください[迷惑メール、一括メールの違いは何ですか?](../what-s-the-difference-between-junk-email-and-bulk-email.md)と関連するサブトピックです。<br/> |
|悪意のある URL 禁止リスト  <br/> |EOP では、メッセージ内の既知の悪意のあるリンクを検出するため、いくつかの URL 禁止リストを使用しています。  <br/> |
|フィッシング対策保護  <br/> |EOP には既知のスパム発信者 750,000 名のドメインが含まれています。  <br/> |
|**スパム管理** <br/> ||
|接続フィルター「IP 許可一覧」および「IP 禁止一覧」構成機能  <br/> |接続フィルターで指定された IP アドレスが 1 つの IP の尊重のアドレスと CIDR の IP アドレスの範囲です。サービスには、IPv6 アドレスもサポートしています。詳細については、[接続フィルター ポリシーを構成する](../configure-the-connection-filter-policy.md)を参照してください。<br/> |
|ユーザー、グループ、またはドメインごとにコンテンツ フィルター ポリシーをカスタマイズする機能  <br/> |細分性が向上、コンテンツ フィルターのカスタム ポリシーを作成し、組織内の指定したユーザー、グループ、またはドメインに適用できます。カスタム ポリシーに常に優先デフォルトのポリシーが、カスタム ポリシーの優先順位 (つまり、実行の順序) を変更することができます。詳細については、[スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)を参照してください。<br/> |
|コンテンツによりフィルター処理されたメッセージに対するアクションを構成する機能  <br/> |複数設定可能なアクションがあります。たとえば、メッセージのコンテンツ フィルターを削除または迷惑メール フォルダーや、検疫に送信できます。詳細については、[スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)を参照してください。<br/> |
|スパム メールを積極的にフィルター処理する拡張オプションの構成機能  <br/> |詳細については、[スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)は構成する) と[高度な迷惑メール フィルターのオプション](../advanced-spam-filtering-asf-options.md)(これは各オプションの動作に関する詳細を提供します) を参照してください。  <br/> |
|国際スパム フィルタリング  <br/> |EOP を構成するには特定の言語で記述された、または特定の国や地域から送信されるメッセージをフィルター処理します。86 のさまざまな言語とそれぞれの地域に 250 まで設定できます。サービスは、精度の高い迷惑メールの設定済みのアクションに適用されます。詳細については、[スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)を参照してください。<br/> |
|Outlook または Outlook Web App (OWA) を使用してスパムを管理する  <br/> |管理者およびエンド ユーザーは、安全な送信者の一覧および受信拒否送信者の一覧を作成できます。詳細情報:  <br/> OWA:「[ブロックまたは許可 (迷惑メール設定)](https://go.microsoft.com/fwlink/p/?LinkId=294862)」を参照してください。  <br/> Outlook:「[迷惑メール フィルターの概要](https://go.microsoft.com/fwlink/p/?LinkId=270065)」を参照してください。  <br/> EOP をオンプレミスのメールボックスを保護するために使用する場合は、ディレクトリ同期を使用してこれらの設定はサービスに同期されていることを確認することを確認します。ディレクトリ同期の設定に関する詳細については、 [EOP のメール ユーザーの管理](manage-mail-users-in-eop.md)で「メール ユーザーを管理するためにディレクトリ同期を使用」を参照してください。           |
|Microsoft Office Outlook の迷惑メール報告アドイン経由のスパム報告  <br/> |分析のためにマイクロソフトのスパム メッセージを送信する outlook アドインをダウンロードできます。ダウンロードしてこのツールを使用する方法の詳細については、[レポート メッセージを追加で有効にする](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)を参照してください。<br/> EOP と Exchange Server 2013 を使用する場合を右、スパム メッセージを送信するのには、OWA で[迷惑メールのレポートと web 上の Outlook でのフィッシング詐欺](../report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)で説明されているようです。  <br/> |
|電子メール エイリアスを使用したスパムおよび非スパムの報告  <br/> |スパム (迷惑メール) と電子メール経由でマイクロソフト以外のスパム (迷惑メール) メッセージを送信することができます。詳細については、[迷惑メールの送信、スパム以外の場合、および分析のためのマイクロソフトのフィッシング詐欺メッセージ](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)を参照してください。<br/> |
|OWA 迷惑メール報告を使用したスパムおよび非スパムの報告  <br/> |スパムと OWA の [迷惑メールの報告を使用して Microsoft 以外の迷惑メール メッセージを送信することができます。詳細については、[迷惑メールのレポートと web 上の Outlook でのフィッシング詐欺](../report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)を参照してください。<br/> 現在、この機能は、Exchange Server 2013 SP1 メールボックスが EOP でフィルター処理されている Outlook Web App (OWA) ユーザーが使用できます。Exchange Online OWA ユーザーも近い将来にこの機能を使用できるようになります。           |
|エンドユーザー スパム検疫通知  <br/> |エンド ・ ユーザーは、独自のスパム検疫メッセージを解放して、エンド ・ ユーザーの迷惑メールの通知メッセージを使用して迷惑メールとして報告すること。これらの通知の電子メールを構成し、[構成するエンドユーザー スパム通知 Exchange オンライン](../configure-end-user-spam-notifications-in-exchange-online.md)または[EOP で構成するエンド ・ ユーザーのスパム通知](../configure-end-user-spam-notifications-in-eop.md)の説明に従って、管理者によって有効になっています。<br/> |
|エンドユーザー スパム検疫通知頻度  <br/> |この頻度は、既定では 3 日であり、1 ～ 15 日の範囲で構成できます。  <br/> |
|エンドユーザー スパム検疫通知の言語の構成機能 (管理者向け)  <br/> |これは、エンドユーザーおよび管理者が使用できます。詳細については、「[Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md)」または「[Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)」を参照してください。  <br/> |
|検疫内のメッセージへの Web ページ経由のアクセスと管理  <br/> |これは、エンドユーザーおよび管理者が使用できます。詳細については、「[Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md)」または「[Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)」を参照してください。  <br/> |
|検疫を検索する機能  <br/> |特定のスパム メッセージの検疫を検索する機能は、管理者とエンドユーザーの両方が使用できます。詳細については、「[Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md)」または「[Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)」を参照してください。  <br/> |
|Exchange 管理センターからのスパム検疫済みメッセージ ヘッダーを表示する  <br/> |検疫内のメッセージを表示した後で、メッセージ ヘッダー テキストをコピーして[メッセージ ヘッダー アナライザー](https://testconnectivity.microsoft.com/?tabid=mha)に貼り付けます。メッセージ ヘッダー アナライザーはメッセージがどうなったかについて説明します。    <br/> |
|**マルウェア対策保護** <br/> ||
|マルウェア対策保護の複数のエンジン  <br/> |複数のマルウェア対策エンジンは、常にお客様を自動的に保護します。  <br/> |
|マルウェア フィルターを無効にするオプション  <br/> |サービスを通じてルーティングされるすべての電子メール メッセージに対するマルウェア対策スキャンは強制されるので、マルウェア フィルターを無効にすることはできません。一貫した、厳しい水準の保護をすべてのお客様に提供することは、お客様の電子メール メッセージ環境の保護に必要な綿密な防御戦略に必要不可欠であると考えています。そのため、マルウェア フィルタリングはすべてのお客様に対して自動的に有効になっています。  <br/> |
|メッセージ本文と添付ファイルのマルウェア検査  <br/> |このサービスは、メッセージ本文とすべての添付ファイルのアクティブなペイロードにマルウェアがないか検査します。  <br/> |
|既定またはカスタム マルウェア アラート通知  <br/> |メッセージがマルウェアとして検出され、配信されない場合、送信者または管理者に通知の電子メール メッセージを送信するためのオプションがあります。これらの通知は、メッセージ全体が削除されたときにのみ送信されます。詳細については、[マルウェア対策ポリシーを構成する](../configure-anti-malware-policies.md)を参照してください。<br/> |
|マルウェアが検出された場合に添付ファイルを削除するオプション  <br/> |管理者は、メッセージ全体を削除する添付ファイルを削除し、カスタマイズしたメッセージを受信者に送信するかどうかを選択できます。詳細については、[マルウェア対策ポリシーを構成する](../configure-anti-malware-policies.md)を参照してください。<br/> |
|スパイウェア対策保護  <br/> |マルウェア対策保護には、ウイルス対策保護およびスパイウェア対策保護が含まれます。  <br/> |
|ユーザー、グループ、またはドメインごとにマルウェア フィルター ポリシーをカスタマイズする機能  <br/> |大きな粒度でのカスタムのマルウェア フィルター ポリシーを作成し、組織内の指定したユーザー、グループ、またはドメインに適用できます。カスタム ポリシーに常に優先デフォルトのポリシーが、カスタム ポリシーの優先順位 (つまり、実行の順序) を変更することができます。詳細については、[マルウェア対策ポリシーを構成する](../configure-anti-malware-policies.md)を参照してください。<br/> |
|**メール ルーティングとコネクタ** <br/> ||
|条件付きメール ルーティング  <br/> |詳細については、「[Create Connectors for Conditional Mail Routing](http://technet.microsoft.com/library/905dc235-1d2b-487e-a65a-516d92e88347.aspx)」を参照してください。  <br/> |
|便宜的な TLS または強制 TLS  <br/> |便宜的または強制 TLS は、コネクタを使用できます。便宜的な TLS は、TLS 接続を試みますが、TLS 接続が失敗した場合に SMTP 接続を使用します。強制 TLS は、TLS 接続が失敗した場合に、メッセージを拒否するための TLS 接続を強制します。TLS、セキュリティ、およびコネクタに関する詳細については、[パートナー組織とセキュリティで保護されたメール フローにコネクタのセットアップ](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx)を参照してください。<br/> |
|地域ルーティング (特定の地域へのメール フローの制限)  <br/> |詳細については、「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」の「EOP データセンター」セクションを参照してください。  <br/> |
|SMTP 接続チェック ツール  <br/> |このツールを使用してメール フローをテストする方法の詳細については、「[Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)」を参照してください。  <br/> |
|一致サブドメイン  <br/> |承認済みドメインのサブドメインとの間でメール フローを有効にする方法の詳細については、「[EOP でサブドメインの電子メール フローを有効にする](http://technet.microsoft.com/library/b5684042-dadc-4111-95b3-c2fd06e368bf.aspx)」を参照してください。  <br/> |
|**トランスポート ルール** <br/> ||
|ポリシー ベースのフィルタリングとアクション  <br/> |カスタム ポリシーは、Exchange のトランスポート ルールに基づいています。ドメイン、キーワード、ファイル名、ファイルの種類、件名、メッセージ本文、送信者、受信者、ヘッダー、および IP アドレスでフィルター処理できます。詳細については、[メール フロー ルール (トランスポート ルール) では、Exchange オンライン保護](mail-flow-rules-transport-rules-0.md)を参照してください。<br/> |
|テキスト パターンによるフィルター  <br/> |トランスポート ルールは、テキストと一致する配列または正規表現を使用できます。1 つの文字列または複数の文字列の配列を使用して、アドレス、件名、本文、または添付ファイル名など、多くのメッセージ プロパティと一致させることもできます。詳細については、「[Transport Rule Conditions (Predicates)](http://technet.microsoft.com/library/04edeaba-afd4-4207-b2cb-51bcc44e483c.aspx)」を参照してください。<br/> |
|ユーザー辞書  <br/> |トランスポート ルールには、ユーザー辞書と同じ機能を提供する、テキストとキーワードの長いリストを含めることができます。  <br/> |
|ドメイン単位のポリシー ルール  <br/> |トランスポート ルールのスコープは、送信者または受信者のドメイン名、IP アドレスの範囲、アドレスのキーワードまたはパターン、グループ メンバーシップ、および他の条件と一致するようカスタマイズできます。詳細については、「[Transport Rule Conditions (Predicates)](http://technet.microsoft.com/library/04edeaba-afd4-4207-b2cb-51bcc44e483c.aspx)」を参照してください。<br/> |
|添付ファイル スキャン  <br/> |ルールを作成して、添付ファイルのファイル名、拡張子、および内容をスキャンできます。  <br/> |
|送信者へのポリシー ルール通知の送信  <br/> |**[説明を示してメッセージを拒否する]** または **[次の拡張状態コードのメッセージを拒否する]** アクションを使用して、メッセージを拒否し、配信不能レポート (NDR) を送信者に送信できます。詳細については、「[Transport rule actions](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)」を参照してください。<br/> |
|固定のアドレスへのメッセージの送信 (特定のアドレスへのメッセージのリダイレクトやコピーなど)  <br/> |トランスポート ルールではリダイレクトしたり、カーボン コピーまたはブラインド カーボン コピーで受信者を追加したり、単純に受信者を追加したり、その他のオプションを実行できます。詳細については、「[Transport rule actions](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)」を参照してください。<br/> |
|複数のルール間でルールの優先順位を簡単に調整する機能  <br/> |Exchange 管理センターを使用して、ルールが処理される順序を変更します。詳細については、「[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)」を参照してください。  <br/> |
|メッセージをフィルターしてからメッセージのルーティングまたは属性を変更する機能  <br/> |さまざまな条件に基づいてメッセージをフィルター処理し、メッセージごとに一連のアクションを適用できます。詳細については、[メール フロー ルール (トランスポート ルール) では、Exchange オンライン保護](mail-flow-rules-transport-rules-0.md)を参照してください。<br/> |
|ルールによってメッセージの Spam Confidence Level レベルを変更します。  <br/> |転送中のメッセージを検査し、選択した条件に基づいて迷惑メールの信頼レベルを割り当てることがことができます。詳細については、[メッセージにスパム信頼レベル (SCL) を設定するのにはメールの流れの規則を使用する](../use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)を参照してください。<br/> |
|メッセージの添付ファイルの検査  <br/> |添付ファイルの内容または添付ファイルの特性を調べて、調べた内容に基づいて実行するアクションを定義できます。詳細については、「[Using transport rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)」を参照してください。  <br/> |
|**管理** <br/> ||
|Web ベースの管理  <br/> |EOP の管理者には、60 の言語でサポートされている Exchange 管理センター (EAC) インターフェイスを使用してサービスを管理できます。詳細については、 [Exchange 管理センターでは、Exchange オンライン保護](../exchange-admin-center-in-exchange-online-protection-eop.md)を参照してください。<br/> |
|ディレクトリ同期  <br/> |ディレクトリ同期は、Azure Active Directory 同期ツール から利用できます。詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」の「ディレクトリ同期を使用してメール ユーザーを管理する」セクションを参照してください。  <br/> |
|ディレクトリ ベースのエッジ ブロック (DBEB)  <br/> |DBEB 機能では、サービス ネットワーク境界で無効な受信者宛てのメッセージを拒否することができます。管理者は DBEB を使用することにより、メールが有効な受信者を Office 365 に追加したり、Office 365 内に存在しない電子メール アドレスに送信されたすべてのメッセージをブロックしたりすることができます。DBEB の構成の詳細は、「[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)」を参照してください。  <br/> |
|リモート Windows PowerShell へのアクセス  <br/> |すべての EOP 機能はリモート Windows PowerShell で利用できます。詳細については、「[Exchange Online Protection の PowerShell](http://technet.microsoft.com/library/f7918a88-774a-405e-945b-bc2f5ee9f748.aspx)」を参照してください。  <br/> |
|**レポート作成とログ記録** <br/> ||
|メッセージ追跡  <br/> |メッセージ追跡機能を使用すると、管理者はサービスを経由する電子メール メッセージを追跡できます。これは、対象の電子メール メッセージがサービスによって受信、拒否、延期、または配信されたかどうかを判断する上で役立ちます。したがって、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。詳細については、「[Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)」を参照してください。  <br/> |
|Web ベースのレポート  <br/> |Office 365 管理センターのメール保護レポートは、メッセージング データを提供します。たとえば、検出されたスパムおよびマルウェアの量や、トランスポート ルールが一致した頻度を監視できます。これらの対話式レポートを使用すると、概要データに関する視覚的なレポートを素早く取得し、過去 90 日間の各メッセージの詳細を確認できます。詳細については、「[Use mail protection reports in Office 365 to view data about malware, spam, and rule detections](http://technet.microsoft.com/library/bcef7984-4bfa-4ca8-9fa5-a65af8618f5d.aspx)」を参照してください。  <br/> |
|Excel レポート作成ワークブック経由の詳細なレポート作成  <br/> |Excel 2013 レポート作成ワークブックのメール保護レポートも使用できます。しかし、拡張 Office 365 管理センターのレポートの利用をお勧めします。Excel 2013 レポート ワークブックは、今後は提供されなくなる予定です。  <br/> |
|監査ログ  <br/> |管理者の役割グループ レポートおよび管理者監査ログは、EOP 管理者が利用できます。詳細については、「[EOP の監査レポート](auditing-reports-in-eop.md)」を参照してください。  <br/> |
|**サービス レベル アグリーメント (SLA) とサポート** <br/> ||
|スパム有効性 SLA  <br/> |\>99%  <br/> |
|偽陽性率 SLA  <br/> |\<1:250,000  <br/> |
|ウイルス検出とブロック SLA  <br/> |既知のウイルスの 100%  <br/> |
|月間稼働時間 SLA  <br/> |99.999%  <br/> |
|1 日 24 時間、週 7 日の電話および Web テクニカル サポート  <br/> |EOP ヘルプおよびサポート オプションの詳細については、「[EOP のヘルプとサポート](help-and-support-for-eop.md)」を参照してください。  <br/> |
|**その他の機能** <br/> ||
|サーバーの地域冗長グローバル ネットワーク  <br/> |EOP は、最適な可用性を提供するよう設計された、複数のデータ センターから成る世界規模のネットワーク上で稼働します。詳細については、「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」の「EOP データセンター」セクションを参照してください。  <br/> |
|社内サーバーでメールが受信できない場合のメッセージ キュー  <br/> |保留にされたメッセージはキュー内で 2 日間保持されます。メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。平均では、5 分ごとにメッセージの送信が再試行されます。詳細については、「[EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.md)」を参照してください。  <br/> |
|アドオン サービスとして利用可能な Office 365 Message Encryption  <br/> |詳細については、「[Office 365 での暗号化](https://technet.microsoft.com/en-us/library/dn569286.aspx)」をご覧ください。  <br/> |
   

