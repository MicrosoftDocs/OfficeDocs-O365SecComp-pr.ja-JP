---
title: Exchange Online Protection を使用して社内メールボックスを保護する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/1/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
description: 一部またはすべてのメールボックスを社内でホストすることを計画している場合でも、Exchange Online Protection (EOP) を使用してメールボックスを保護することができます。コネクタを構成するには、アカウントが Office 365 グローバル管理者、または Exchange 会社の管理者 (Organization Management 役割グループ) である必要があります。office 365 のアクセス許可と Exchange のアクセス許可との関係の詳細については、「office 2013 で運用されている管理者ロールの割り当て」を参照してください。すべての Exchange メールボックスがオンプレミスである場合は、次の手順に従って EOP サービスを設定します。
ms.openlocfilehash: 40fb5471a084cf245d9aef7f7b2b88effb5c4a83
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276037"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a>Exchange Online Protection を使用して社内メールボックスを保護する

> [!NOTE]
> この記事は、中国で21vianet が運営する Office 365 にのみ適用されます。 
  
一部またはすべてのメールボックスを社内でホストすることを計画している場合でも、Exchange Online Protection (EOP) を使用してメールボックスを保護することができます。コネクタを構成するには、アカウントが Office 365 グローバル管理者、または Exchange 会社の管理者 (Organization Management 役割グループ) である必要があります。office 365 のアクセス許可と Exchange のアクセス許可との関係の詳細については、「 [office 2013 で運用されている管理者ロールの割り当て](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac)」を参照してください。すべての Exchange メールボックスがオンプレミスである場合は、次の手順に従って EOP サービスを設定します。 
  
## <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a>手順 1: Office 365 管理センターを使用してドメインを追加して管理する

1. Office 365 管理センターで、 [セットアップ] に移動して、サービスにドメインを追加します。
    
2.  ポータルの手順に従って、ドメインの所有権を確認するために、該当する dns レコードを dns ホストプロバイダーに追加します。 
    
> [!TIP]
> 「 [21vianet が運用する office 365 にドメインとユーザーを追加](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78)する」と「 [office の dns レコードを作成](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)する」を参照してください。 dns レコードを管理するときは、ドメインをサービスに追加して dns を構成する際に参照するのに役立つリソースです。 
  
### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>手順 2: 受信者を追加してドメインの種類を構成する

EOP サービスとの間のメール フローを設定する前に、受信者をサービスに追加することお勧めします。「[EOP でメール ユーザーを管理する](https://go.microsoft.com/fwlink/?LinkId=506782)」に記載されているように、これを行うにはいくつかの方法があります。さらに、受信者を追加した後にサービス内で受信者の検証を行うために、ディレクトリ ベースのエッジ ブロック (Directory Based Edge Blocking (DBEB)) を有効にする場合、ドメインの種類を [権限あり] に設定する必要があります。DBEB の詳細については、「[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781)」を参照してください。
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>手順 3:EAC を使用してメール フローをセットアップする

Exchange 管理センター (EAC) で、EOP とオンプレミスのメールサーバー間のメールフローを有効にするコネクタを作成します。詳細な手順については、「 [EOP による基本的なメールフローの設定に必要なコネクタを作成する](https://go.microsoft.com/fwlink/?LinkId=506780)」を参照してください。
  
 このタスクの検証方法 
  
 サービスと環境の間のメールフローを確認するテストを実行するには、リモート接続アナライザーを使用します。詳細については、「 [test mail flow with the remote Connectivity analyzer](https://go.microsoft.com/fwlink/?LinkId=506784)」の「リモート接続アナライザーを使用して電子メール配信をテストする」を参照してください。
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a>手順 4: 受信ポート 25 SMTP アクセスを許可する

コネクタを構成した後、DNS レコードの更新が伝達されるように、72時間待機します。次に、ファイアウォールまたはメールサーバー上の受信ポート-25 SMTP トラフィックを制限して、EOP データセンターからのメールのみを受け入れるようにします。具体的には、21vianet が運用している[Office 365 の url および ip アドレス範囲](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection)に記載されている ip アドレスからのものです。これにより、受信可能な受信メッセージの範囲を制限することで、オンプレミス環境を保護します。また、メールリレーの接続を許可する IP アドレスを制御する設定がメールサーバーにある場合は、それらの設定も更新します。
  
> [!TIP]
> SMTP サーバーの設定を、60 秒で接続タイムアウトが発生するように構成します。この設定はほとんどの状況で使用可能ですが、メッセージをサイズの大きな添付書類とともに送信した場合などに備えて、ある程度の遅延を設けてください。 
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>手順 5: シェルを使用してスパムがそれぞれのユーザーの迷惑メール フォルダーにルーティングされることを確認する

スパム (迷惑) メールがそれぞれのユーザーの迷惑メールフォルダーに正しくルーティングされるようにするには、いくつかの構成手順を実行する必要があります。この手順は、[スパムが各ユーザーの迷惑メールフォルダーにルーティングされるよう](https://go.microsoft.com/fwlink/?LinkId=506804)にするためのものです。メッセージを各ユーザーの [迷惑メール] フォルダーに移動しない場合は、Exchange 管理センターでコンテンツフィルターポリシーを編集して、別のアクションを選択することができます。詳細については、「 [Configure Content Filter Policies](https://go.microsoft.com/fwlink/?LinkId=506805)」を参照してください。 
  
## <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a>手順 6: Office 365 管理センターを使用して、MX レコードが EOP をポイントするようにする

Office 365 ドメイン構成手順に従って、ドメインの MX レコードを更新し、受信メールが EOP を通過するようにします。詳細については、「dns レコードを[管理するときに、Office 365 の dns レコードを作成](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)する」を参照してください。
  
このタスクの検証方法
  
 MX レコードを検証するテストを実行するには、リモート接続アナライザーを使用します。詳細については、「 [test mail flow with the remote Connectivity analyzer](https://go.microsoft.com/fwlink/?LinkId=506784)」の「リモート接続アナライザーを使用して MX レコードおよび送信コネクタをテストする」セクションを参照してください。 
  
ここまでに、適切に構成された社内送信コネクタのサービス配信の検証と、MX レコードが EOP を指していることの検証が完了しました。次に、電子メールがサービスによって社内環境に正常に配信されることを検証する、以下の追加テストの実行を選択します。
  
- リモート接続アナライザーで **[Office 365]** タブをクリックし、次に **[インターネット電子メールのテスト]** の下にある **[受信 SMTP 電子メール]** を実行します。
    
- Web に基づく電子メール アカウントから、ドメインがサービスに追加したドメインと一致する、組織内のメール受信者に電子メール メッセージを送信します。Microsoft Outlook または別の電子メール クライアントを使って、社内メールボックスへのメッセージの配信を確認します。
    
- 送信電子メールのテストを実行する場合は、組織内のユーザーから Web ベースの電子メール アカウントに電子メールを送信し、メッセージが受信されたかを確認できます。
    
## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>あまり一般的ではない: オンプレミスのメールボックスとクラウド内のハイブリッドセットアップ

exchange Online で exchange メールボックスがオンプレミスにあり、クラウド内に1つ以上のメールボックスがある場合は、*ハイブリッド*セットアップがあります。ハイブリッドセットアップでは、オンプレミス環境とクラウド環境で、空き時間情報予定表共有やメールルーティングなどの機能が一緒に機能します。メールボックスを Exchange Online に移行する際に、ハイブリッドセットアップが行われている場合があります。ハイブリッド環境は、EOP スタンドアロンの保護とは異なる方法で設定されます。 
  
多くの従業員に対してクラウドベースの電子メールを活用するために、ハイブリッドシナリオを選択することができます。この操作は、オンプレミスのメールボックスの一部をホストするときに実行することもできます。たとえば、法務部門の場合です。 
  
ハイブリッドセットアップは複雑になることがありますが、多くの利点があります。exchange を使用したハイブリッドシナリオのセットアップの詳細については、「 [21vianet が運用している Office 365 を使用して exchange ハイブリッド展開機能を構成](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d)する」を参照してください。
  

