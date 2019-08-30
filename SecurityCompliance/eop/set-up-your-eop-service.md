---
title: EOP サービスを設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/23/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: このトピックでは、Microsoft Exchange Online Protection (EOP) のセットアップ方法について説明します。 Office 365 ドメイン ウィザードからここに移動してきた場合、Exchange Online Protection を使用する必要がなければ Office 365 ドメイン ウィザードに戻ってください。 コネクタの構成方法の詳細については、「Configure mail flow using connectors in Office 365」をご覧ください。
ms.openlocfilehash: 5c17e88784c5987d48930c26e9c4319256a95c43
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676537"
---
# <a name="set-up-your-eop-service"></a>EOP サービスを設定する

このトピックでは、Microsoft Exchange Online Protection (EOP) のセットアップ方法について説明します。Office 365 ドメイン ウィザードからここに移動してきた場合、Exchange Online Protection を使用する必要がなければ Office 365 ドメイン ウィザードに戻ってください。コネクタの構成方法の詳細については、「[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)」をご覧ください。
  
> [!NOTE]
> このトピックは、対象とする社内メールボックスがあり、それらをスタンドアロン シナリオとして知られている EOP で保護する場合を前提としています。 Exchange Online によりクラウド上のすべてのメールボックスをホストする場合、このトピックに記載されているすべての作業を行う必要はありません。 [Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286312)に移動してサインアップして、クラウド メールボックスを購入してください。 社内メールボックスの一部をホストし、一部をクラウド上に置く場合は、ハイブリッド シナリオと呼びます。 この場合、より高度なメール フローの設定が必要です。 「 [Exchange Server のハイブリッド展開](https://docs.microsoft.com/exchange/exchange-hybrid)」には、ハイブリッドメールフローについての説明と、設定方法を示すリソースへのリンクがあります。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- このタスクの予想所要時間:1 時間

- コネクタを構成するには、アカウントが Office 365 グローバル管理者または Exchange 会社の管理者 (Organization Management 役割グループ) である必要があります。 詳細については、「 [Feature permissions IN EOP](feature-permissions-in-eop.md)」を参照してください。

- EOP に登録にしていない場合は、「[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=282660)」にアクセスして、サービスを購入するか、試用してみてください。

- このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。

> [!TIP]
> 問題がある場合は、 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラムでヘルプを要求します。

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>手順 1: Microsoft 365 管理センターを使用してドメインを追加して確認する

1. [Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?LinkId=521888)で、[**セットアップ**] を使用して、ドメインをサービスに追加します。

2. ドメインの所有権を確認するため、以下の手順に従って、適用可能な DNS レコードを DNS ホスティング プロバイダーに追加します。

> [!TIP]
> Office [365 にドメインを追加](https://docs.microsoft.com/office365/admin/setup/add-domain)して、[任意の dns ホスティングプロバイダーで office 365 用の Dns レコードを作成](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)することは、ドメインをサービスに追加して dns を構成する際に参照するのに便利なリソースです。
  
## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>手順 2:受信者を追加し、オプションとして DBEB を有効化する

EOP サービスとの間のメール フローを設定する前に、受信者をサービスに追加することお勧めします。「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」に記載されているように、これを行うにはいくつかの方法があります。さらに、受信者を追加した後にサービス内で受信者の検証を行うために、ディレクトリ ベースのエッジ ブロック (Directory Based Edge Blocking (DBEB)) を有効にする場合、ドメインの種類を [権限あり] に設定する必要があります。DBEB の詳細については、「[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」を参照してください。
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>手順 3:EAC を使用してメール フローをセットアップする

Exchange 管理センター (EAC) でコネクタを作成し、EOP とオンプレミスのメール サーバー間のメール フローを有効にします。詳細な手順については、「[Set up connectors to route mail between Office 365 and your own email servers](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)」を参照してください。
  
### <a name="how-do-you-know-this-task-worked"></a>このタスクの検証方法

サービスと環境の間のメールフローをチェックします。 詳細については、「 [Office 365 コネクタを検証することによるメールフローのテスト](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)」を参照してください。
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a>手順 4: 受信ポート 25 SMTP アクセスを許可する

コネクタを構成した後、DNS レコードの更新が伝達されるよう 72 時間待ちます。この後、ファイアウォールまたはメール サーバーで、EOP データセンターからの (具体的には [Exchange Online Protection の IP アドレス](exchange-online-protection-ip-addresses.md) に一覧表示されている IP アドレスからの) メールだけを受信するように、受信用ポート 25 の SMTP トラフィックを制限します。これにより、受信可能な受信メッセージの範囲が制限され、社内環境が保護されます。また、メール リレーへの接続が許可される IP アドレスを制御するようにメール サーバーを設定している場合は、その設定も更新します。
  
> [!TIP]
> SMTP サーバーの設定を、60 秒で接続タイムアウトが発生するように構成します。 この設定は、大規模な添付ファイルで送信されたメッセージの場合など、遅延が発生する場合がほとんどの場合に使用できます。
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>手順 5: シェルを使用してスパムがそれぞれのユーザーの迷惑メール フォルダーにルーティングされることを確認する

スパム (迷惑) メールがそれぞれのユーザーの迷惑メール フォルダーに正しくルーティングされることを保証するには、一組の構成手順を実行する必要があります。 この手順は、[スパムが各ユーザーの迷惑メールフォルダーにルーティングされるよう](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)にするためのものです。
  
メッセージをそれぞれのユーザーの迷惑メール フォルダーに移動しない場合は、Exchange 管理センターでコンテンツ フィルター ポリシーを編集すると別のアクションを選択できます。 詳細については、「 [スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)」を参照してください。
  
## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>手順 6: Microsoft 365 管理センターを使用して MX レコードを EOP にポイントする

Office 365 ドメイン構成手順に従って、ドメインの MX レコードを更新し、受信メールが EOP 経由で流れるようにします。サード パーティのフィルタリング サービスを通して電子メールを EOP に送るのではなく、MX レコードが直接 EOP をポイントするようにします。詳細については、「[Office 365 の DNS レコードを作成する ](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」を参照してください。
  
### <a name="how-do-you-know-this-task-worked"></a>このタスクの検証方法

ここまでに、適切に構成された社内送信コネクタのサービス配信の検証と、MX レコードが EOP を指していることの検証が完了しました。次に、電子メールがサービスによって社内環境に正常に配信されることを検証する、以下の追加テストの実行を選択します。
  
- サービスと環境の間のメールフローをチェックします。 詳細については、「 [Office 365 コネクタを検証することによるメールフローのテスト](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)」を参照してください。

- Web に基づく電子メール アカウントから、ドメインがサービスに追加したドメインと一致する、組織内のメール受信者に電子メール メッセージを送信します。Microsoft Outlook または別の電子メール クライアントを使って、社内メールボックスへのメッセージの配信を確認します。

- 送信電子メールのテストを実行する場合は、組織内のユーザーから Web ベースの電子メール アカウントに電子メールを送信し、メッセージが受信されたかを確認できます。

> [!TIP]
> セットアップが完了したら、EOP を使用してスパムやマルウェアを削除するために、特別な手順を実行する必要はありません。 EOP はスパムやマルウェアを自動的に削除します。 ただしビジネス要件に基づいて、EAC の設定を微調整することも可能です。 詳細については、「 [Office のスパム対策およびマルウェア対策保護](../anti-spam-and-anti-malware-protection.md)」を参照してください365。 <br/><br/> サービスが実行されたので、 [EOP を構成するためのベストプラクティス](best-practices-for-configuring-eop.md)を読み取ることをお勧めします。これは、EOP のセットアップ後に推奨される設定と考慮事項について説明します。
