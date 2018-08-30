---
title: Exchange のオンライン保護とオンプレミスのメールボックスを保護します。
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/1/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
description: メールボックスの設置型の一部またはすべてをホストする場合でも、Exchange オンライン保護 (EOP) のメールボックスを保護できます。コネクタを構成するのには自分のアカウントは、Office 365 グローバル管理者、または会社の Exchange 管理者 (組織の管理役割グループ) をする必要があります。Office 365 のアクセス許可が Exchange のアクセス許可に関連する方法については、21Vianet によって運営されて Office 365 の管理者ロールの割り当てを参照してください。すべての Exchange メールボックスは、オンプレミス、EOP サービスを設定する手順に従います。 場合、
ms.openlocfilehash: 4751bb2183e61d292805d1799519644b77b08c2a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532800"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a>Exchange のオンライン保護とオンプレミスのメールボックスを保護します。

> [!NOTE]
> この資料は、中国での 21Vianet によって運営されて Office 365 にのみ適用されます。 
  
メールボックスの設置型の一部またはすべてをホストする場合でも、Exchange オンライン保護 (EOP) のメールボックスを保護できます。コネクタを構成するのには自分のアカウントは、Office 365 グローバル管理者、または会社の Exchange 管理者 (組織の管理役割グループ) をする必要があります。Office 365 のアクセス許可が Exchange のアクセス許可に関連する方法については、 [21Vianet によって運営されて Office 365 の管理者ロールの割り当て](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac)を参照してください。すべての Exchange メールボックスは、オンプレミス、EOP サービスを設定する手順に従います。 場合、 
  
## <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a>手順 1: Office 365 管理センターを使用してドメインを追加して管理する

1. Office 365 管理センターで、 [セットアップ] に移動して、サービスにドメインを追加します。
    
2.  ポータルでドメインの所有権を確認するために DNS ホスティング プロバイダーに適用可能な DNS レコードを追加する手順に従います。 
    
> [!TIP]
> [自分のドメインを追加しユーザーが Office 365 の 21Vianet によって運営されて](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78)、 [Office 365 の DNS レコードを管理するときに作成する DNS レコード](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)は、サービスにドメインを追加すると DNS の構成を行うを参照するための有用なリソースです。 
  
### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>手順 2: 受信者を追加し、ドメインの種類を構成します。

EOP サービスとの間のメール フローを設定する前に、受信者をサービスに追加することお勧めします。「[EOP でメール ユーザーを管理する](https://go.microsoft.com/fwlink/?LinkId=506782)」に記載されているように、これを行うにはいくつかの方法があります。さらに、受信者を追加した後にサービス内で受信者の検証を行うために、ディレクトリ ベースのエッジ ブロック (Directory Based Edge Blocking (DBEB)) を有効にする場合、ドメインの種類を [権限あり] に設定する必要があります。DBEB の詳細については、「[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781)」を参照してください。
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>手順 3:EAC を使用してメール フローをセットアップする

EOP とオンプレミス メール サーバー間のメール フローを有効にする Exchange 管理センター (EAC) では、コネクタを作成します。詳細については、[作成に必要なコネクタ EOP で基本的なメール フローの設定を](https://go.microsoft.com/fwlink/?LinkId=506780)参照してください。
  
 このタスクの検証方法 
  
 サービスとお客様の環境との間のメール フローを確認するテストを実行するのにには、リモート接続アナライザーを使用します。詳細については、[電子メールの配信をテストするのには、リモート接続アナライザーを使用する] セクションで[、リモート接続アナライザーを使用してメール フローをテスト](https://go.microsoft.com/fwlink/?LinkId=506784)を参照してください。
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a>手順 4: 受信ポート 25 SMTP アクセスを許可する

コネクタを構成した後、DNS レコードの更新の伝達を許可するのには 72 時間を待機します。その後、EOP データ センターの[Url と IP アドレスを Office 365 を運用している 21Vianet の範囲](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection)に記載されている IP アドレスから特にからのみメールを受信するようにファイアウォールまたはメール サーバーのポート 25 で SMTP トラフィックを受信を制限します。これは、受信メッセージを受信できることの範囲を制限することで、オンプレミス環境を保護します。さらに、メールの第三者中継用の接続を許可する IP アドレスを制御する、メール サーバー上の設定をした場合にもこれらの設定を更新します。
  
> [!TIP]
> SMTP サーバーの設定を、60 秒で接続タイムアウトが発生するように構成します。この設定はほとんどの状況で使用可能ですが、メッセージをサイズの大きな添付書類とともに送信した場合などに備えて、ある程度の遅延を設けてください。 
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>手順 5: シェルを使用してスパムがそれぞれのユーザーの迷惑メール フォルダーにルーティングされることを確認する

スパム (迷惑) メールを各ユーザーの迷惑メール フォルダーに正しくルーティングされることを確認するには、いくつかの構成手順を行う必要があります。[スパムを各ユーザーの迷惑メール フォルダーにルーティングされるようにするの](https://go.microsoft.com/fwlink/?LinkId=506804)には、手順が用意されています。各ユーザーの迷惑メール フォルダーにメッセージを移動しない場合は、Exchange 管理センターでコンテンツ フィルター ポリシーを編集することによって別のアクションを選択する可能性があります。詳細については、[コンテンツ フィルター ポリシーの構成](https://go.microsoft.com/fwlink/?LinkId=506805)を参照してください。 
  
## <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a>手順 6: Office 365 管理センターを使用して、MX レコードが EOP をポイントするようにする

構成手順を Office 365 ドメイン、ドメインの MX レコードを更新する EOP で受信メールが流れるようにします。詳細については、 [Office 365 の DNS レコードを管理するときに作成する DNS レコード](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)をもう一度参照できます。
  
このタスクの検証方法
  
 MX レコードを確認するテストを実行するのにには、リモート接続アナライザーを使用します。詳細についてを参照してください"、MX レコードと送信コネクタをテストするのには、リモート接続アナライザーを使用する] [、リモート接続アナライザーを使用してメール フローをテスト](https://go.microsoft.com/fwlink/?LinkId=506784)します。 
  
ここまでに、適切に構成された社内送信コネクタのサービス配信の検証と、MX レコードが EOP を指していることの検証が完了しました。次に、電子メールがサービスによって社内環境に正常に配信されることを検証する、以下の追加テストの実行を選択します。
  
- リモート接続アナライザーで **[Office 365]** タブをクリックし、次に **[インターネット電子メールのテスト]** の下にある **[受信 SMTP 電子メール]** を実行します。
    
- Web に基づく電子メール アカウントから、ドメインがサービスに追加したドメインと一致する、組織内のメール受信者に電子メール メッセージを送信します。Microsoft Outlook または別の電子メール クライアントを使って、社内メールボックスへのメッセージの配信を確認します。
    
- 送信電子メールのテストを実行する場合は、組織内のユーザーから Web ベースの電子メール アカウントに電子メールを送信し、メッセージが受信されたかを確認できます。
    
## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>あまり一般的: メールボックスをオンプレミスとクラウドでは、ハイブリッド設定

Exchange メールボックスの設置型がある場合と 1 つまたは複数のメールボックス Exchange Online でクラウドの*ハイブリッド*に設定してあります。ハイブリッド設定では、機能など、空き時間予定表の共有と設置型で、共同作業およびクラウド環境のメール ルーティングします。Exchange Online にメールボックスを移行するときに、場所にハイブリッドの設定があります。ハイブリッド環境は EOP スタンドアロンの保護とは異なる設定ができます。 
  
ハイブリッド シナリオでは、従業員のほとんどのクラウド ベースの電子メールの利用を選択する場合があります。こうことにもホストしているいくつかのメールボックスの設置型です。たとえば、法務部門です。 
  
ハイブリッドの設定が複雑になることができますが、多くの利点があります。Exchange を使用するハイブリッド シナリオの設定に関する詳細については、 [21Vianet によって運営されて Office 365 のハイブリッド展開機能を Exchange の構成](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d)を参照してください。
  

