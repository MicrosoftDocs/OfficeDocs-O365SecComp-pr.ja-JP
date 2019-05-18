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
ms.openlocfilehash: 93c6cbe41177103778bf96ca652d9d2889849372
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153059"
---
# <a name="set-up-your-eop-service"></a>EOP サービスを設定する

このトピックでは、Microsoft Exchange Online Protection (EOP) のセットアップ方法について説明します。Office 365 ドメイン ウィザードからここに移動してきた場合、Exchange Online Protection を使用する必要がなければ Office 365 ドメイン ウィザードに戻ってください。コネクタの構成方法の詳細については、「[Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx)」をご覧ください。
  
> [!NOTE]
> このトピックは、対象とする社内メールボックスがあり、それらをスタンドアロン シナリオとして知られている EOP で保護する場合を前提としています。Exchange Online によりクラウド上のすべてのメールボックスをホストする場合、このトピックに記載されているすべての作業を行う必要はありません。 [Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286312)に移動してサインアップして、クラウド メールボックスを購入してください。社内メールボックスの一部をホストし、一部をクラウド上に置く場合は、ハイブリッド シナリオと呼びます。この場合、より高度なメール フローの設定が必要です。ハイブリッド メール フローとその設定方法の詳細については、「 [Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx)」を参照してください。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- このタスクの予想所要時間:1 時間
    
- コネクタを構成するには、アカウントが Office 365 グローバル管理者または Exchange 会社の管理者 (Organization Management 役割グループ) である必要があります。Office 365 のアクセス許可と Exchange のアクセス許可の関連についての詳細は、「[Office 365 の権限](https://go.microsoft.com/fwlink/p/?LinkID=335814)」を参照してください。
    
- EOP に登録にしていない場合は、「[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=282660)」にアクセスして、サービスを購入するか、試用してみてください。 
    
- このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。
    
> [!TIP]
> 問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="how-do-you-do-this"></a>実行方法

### <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>手順 1: Microsoft 365 管理センターを使用してドメインを追加して確認する

1. Microsoft 365 管理センターで、[**セットアップ**] に移動して、ドメインをサービスに追加します。 
    
    Microsoft 365 管理センターの場所がわからない場合は、どうすればよいですか。 詳細につい[ては、「Microsoft 365 管理センター」を](https://go.microsoft.com/fwlink/p/?LinkId=521888)参照してください。
    
2. ドメインの所有権を確認するため、以下の手順に従って、適用可能な DNS レコードを DNS ホスティング プロバイダーに追加します。
    
> [!TIP]
> サービスへのドメインの追加と DNS の構成に役立つ情報については、「[Office 365 にドメインを追加する](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)」と「[Office 365 の DNS レコードを作成する](https://support.office.com/en-us/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)」を参照してください。 
  
### <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>手順 2:受信者を追加し、オプションとして DBEB を有効化する

EOP サービスとの間のメール フローを設定する前に、受信者をサービスに追加することお勧めします。「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」に記載されているように、これを行うにはいくつかの方法があります。さらに、受信者を追加した後にサービス内で受信者の検証を行うために、ディレクトリ ベースのエッジ ブロック (Directory Based Edge Blocking (DBEB)) を有効にする場合、ドメインの種類を [権限あり] に設定する必要があります。DBEB の詳細については、「[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)」を参照してください。
  
### <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>手順 3:EAC を使用してメール フローをセットアップする

Exchange 管理センター (EAC) でコネクタを作成し、EOP とオンプレミスのメール サーバー間のメール フローを有効にします。詳細な手順については、「[Set up connectors to route mail between Office 365 and your own email servers](http://technet.microsoft.com/library/2e93fd60-a5ef-4e64-8e62-2b862b2d1033.aspx)」を参照してください。
  
#### <a name="how-do-you-know-this-task-worked"></a>このタスクの検証方法

サービスとユーザーの環境間のメール フローを確認するテストを実行するには、リモート接続アナライザーを使用します。詳しくは、「[Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)」のトピック「リモート接続アナライザーを使用して電子メール配信をテストする」を参照してください。
  
### <a name="step-4-allow-inbound-port-25-smtp-access"></a>手順 4: 受信ポート 25 SMTP アクセスを許可する

コネクタを構成した後、DNS レコードの更新が伝達されるよう 72 時間待ちます。この後、ファイアウォールまたはメール サーバーで、EOP データセンターからの (具体的には [Exchange Online Protection の IP アドレス](exchange-online-protection-ip-addresses.md) に一覧表示されている IP アドレスからの) メールだけを受信するように、受信用ポート 25 の SMTP トラフィックを制限します。これにより、受信可能な受信メッセージの範囲が制限され、社内環境が保護されます。また、メール リレーへの接続が許可される IP アドレスを制御するようにメール サーバーを設定している場合は、その設定も更新します。
  
> [!TIP]
> SMTP サーバーの設定を、60 秒で接続タイムアウトが発生するように構成します。この設定はほとんどの状況で使用可能ですが、メッセージをサイズの大きな添付書類とともに送信した場合などに備えて、ある程度の遅延を設けてください。 
  
### <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>手順 5: シェルを使用してスパムがそれぞれのユーザーの迷惑メール フォルダーにルーティングされることを確認する

スパム (迷惑) メールがそれぞれのユーザーの迷惑メール フォルダーに正しくルーティングされることを保証するには、一組の構成手順を実行する必要があります。 この手順は、[スパムが各ユーザーの迷惑メールフォルダーにルーティングされるよう](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)にするためのものです。
  
メッセージをそれぞれのユーザーの迷惑メール フォルダーに移動しない場合は、Exchange 管理センターでコンテンツ フィルター ポリシーを編集すると別のアクションを選択できます。 詳細については、「 [スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)」を参照してください。
  
### <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>手順 6: Microsoft 365 管理センターを使用して MX レコードを EOP にポイントする

Office 365 ドメイン構成手順に従って、ドメインの MX レコードを更新し、受信メールが EOP 経由で流れるようにします。サード パーティのフィルタリング サービスを通して電子メールを EOP に送るのではなく、MX レコードが直接 EOP をポイントするようにします。詳細については、「[Office 365 の DNS レコードを作成する ](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」を参照してください。
  
#### <a name="how-do-you-know-this-task-worked"></a>このタスクの検証方法

MX レコードを検証するテストを実行するには、リモート接続アナライザーを使用します。詳しくは、「[Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)」のトピック「リモート接続アナライザーを使用して MX レコードおよび送信コネクタをテストする」を参照してください。 
  
ここまでに、適切に構成された社内送信コネクタのサービス配信の検証と、MX レコードが EOP を指していることの検証が完了しました。次に、電子メールがサービスによって社内環境に正常に配信されることを検証する、以下の追加テストの実行を選択します。
  
- リモート接続アナライザーで **[Office 365]** タブをクリックし、次に **[インターネット電子メールのテスト]** の下にある **[受信 SMTP 電子メール]** を実行します。 
    
- Web に基づく電子メール アカウントから、ドメインがサービスに追加したドメインと一致する、組織内のメール受信者に電子メール メッセージを送信します。Microsoft Outlook または別の電子メール クライアントを使って、社内メールボックスへのメッセージの配信を確認します。
    
- 送信電子メールのテストを実行する場合は、組織内のユーザーから Web ベースの電子メール アカウントに電子メールを送信し、メッセージが受信されたかを確認できます。
    
> [!TIP]
> セットアップ完了後、スパムやマルウェアを削除するために EOP で行う追加作業はありません。EOP はスパムやマルウェアを自動的に削除します。ただしビジネス要件に基づいて、EAC の設定を微調整することも可能です。詳細については、「[Anti-Spam and Anti-Malware Protection](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx)」を参照してください。 > サービスの開始後に、「[EOP を構成するためのベスト プラクティス](best-practices-for-configuring-eop.md)」を参考にされることをお勧めします。ここでは、EOP セットアップ後の推奨設定や注意点について紹介しています。 
  

