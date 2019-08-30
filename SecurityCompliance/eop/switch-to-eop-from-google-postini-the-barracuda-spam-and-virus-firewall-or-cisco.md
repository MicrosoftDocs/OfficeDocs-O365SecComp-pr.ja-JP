---
title: Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
description: このトピックの目的は、社内の電子メール検疫アプライアンスまたはクラウドベースの保護サービスから Exchange Online Protection (EOP) に切り替えるプロセスを理解していただくことと、着手に役立つリソースを提供することにあります。
ms.openlocfilehash: d7a1f4c281a50a8a835acd848f2c1c0d0407bcf1
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676525"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Google Postini、Barracuda Spam、 Virus Firewall、または Cisco IronPort から EOP に切り替える

 このトピックの目的は、社内の電子メール検疫アプライアンスまたはクラウドベースの保護サービスから Exchange Online Protection (EOP) に切り替えるプロセスを理解していただくことと、着手に役立つリソースを提供することにあります。多数のスパム対策フィルター ソリューションがありますが、多くの場合 EOP への切り替えプロセスは同様です。
  
EOP を初めて使用する場合に、その機能の概要をお読みになる前に、 [Exchange Online Protection の概要](exchange-online-protection-overview.md)のトピックから始めてください。
  
EOP に切り替える前に、Exchange Online、社内、またはハイブリッド シナリオによってクラウド内で EOP 保護されたメールボックスをホストするかどうかを検討することが重要です (ハイブリッドとは、社内でいくつかのメールボックスをホストし、Exchange Online で別の部分をホストすることを意味します)。候補となるこれらの各ホスト シナリオ:クラウド、社内、およびハイブリッドは、セットアップの手順が異なる場合があります。適切な展開を選択するための、いくつかの考慮事項を次に示します。
  
- **オンプレミスメールボックスを使用した EOP の保護**: 既存のメールホスティングインフラストラクチャを使用する必要がある場合や、メールボックスをオンプレミスで保持するビジネス要件があり、EOP のクラウドベースの電子メール保護が必要な場合は、このシナリオが適しています。. 「 [EOP スタンドアロンに切り替える](#switch-to-eop-standalone)」で、このシナリオの詳細を説明しています。

- **EOP protection In Exchange Online メールボックス**: このシナリオは、EOP 保護とすべてのメールボックスをクラウドでホストする場合に適しています。 社内メッセージング サーバーを維持する必要がないため、複雑さを軽減できます。 このシナリオについては、「 [Exchange Online に切り替える](#switch-to-exchange-online)」で説明しています。

- **ハイブリッドメールボックスを使用した EOP の保護**: クラウドメールボックスが必要な場合もありますが、オンプレミスのユーザーのメールボックスを保持する必要があります。 いくつかのメールボックスを社内でホストし、別の部分を Exchange Online でホストする場合は、このシナリオを選択してください。 このシナリオについては、「 [ハイブリッド ソリューションに切り替える](#switch-to-a-hybrid-solution)」で説明しています。

## <a name="switch-to-eop-standalone"></a>EOP スタンドアロンに切り替える

現在、メールボックスを社内でホストし、社内保護アプライアンスまたはクラウド メッセージング保護サービスを使用している場合は、EOP に切り替えて、その保護機能と可用性を活かすことができます。スタンドアロン シナリオ、つまり、社内でメールボックスをホストし EOP を使用して電子メール保護を提供するように EOP を設定するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」で概説されている手順に従います。このトピックでは、サインアップ、ドメインの追加、コネクタとのメール フローの設定などの、EOP 保護の設定に関する手順を概説しています。
  
## <a name="switch-to-exchange-online"></a>Exchange Online に切り替える

社内のメールボックスがオンプレミスのアプライアンスによって保護されていて、Exchange Online クラウドホスト型メールボックスと EOP 保護にジャンプして、Office 365 cloud messaging and protection 機能を活用したいと考えています。 開始するには、Office 365 にサインアップして、ドメインを追加します。 このシナリオでは、オンプレミスのメールボックスに対するルーティングがないので、コネクタを設定する必要はありません。 [Office 365 サインアップページ](https://www.microsoft.com/office365/online-software.aspx)から開始します。 「 [Office 365 の使用を開始](https://go.microsoft.com/fwlink/p/?LinkId=275407)する」では、その機能について理解するためのリソースが提供されています。
  
Office 365 の設定プロセスでは、クラウド ベースのメールボックス ユーザーを作成できます。
  
## <a name="switch-to-a-hybrid-solution"></a>ハイブリッド ソリューションに切り替える

ビジネス要件または規制に関する考慮事項があるため、メールボックスの一部のみをクラウドに移行したい場合があります。このようなケースでは、ハイブリッド シナリオを展開すると、ビジネス要件に従ってメールボックスをクラウドに移行できます。EOP 保護を使用したハイブリッド シナリオへの移行は、すべてにおいてクラウドを採用するシナリオより複雑ですが、Microsoft には、ハイブリッドへの移行が簡単に行える数多くのハイブリッド サポートとリソースが用意されています。
  
ハイブリッド展開を検討している場合は、 [Exchange Server のハイブリッド展開](https://docs.microsoft.com/exchange/exchange-hybrid)を最初に開始することをお勧めします。 さらに、ハイブリッド シナリオではメールをルーティングできるいくつかの異なる方法があり、それらを理解しておくことが重要です。 「 [Exchange ハイブリッド展開でのトランスポートルーティング」で](https://docs.microsoft.com/exchange/transport-routing)は、ビジネス要件に基づいて最適なルーティングシナリオを選択できるように、各タイプについて説明します。
  
## <a name="migration-planning"></a>移行の計画

EOP への切り替えを決定したら、特に次の分野について考慮する必要があります。
  
- **カスタムフィルター規則**: 特定のスパムをキャッチするためのカスタムフィルターまたはビジネスポリシールールがある場合は、ルールを移行する前に、EOP では、期間の既定の設定を使用して実行することをお勧めします。 EOP は既定の設定でエンタープライズ レベルのスパム対策を提供しているため、一部のルールを EOP に移行する必要がない場合があります。 当然、特定のカスタム ビジネス ポリシーを適用するルールがある場合には、それらを作成できます。 [「Exchange Online Protection のメールフロールール (トランスポートルール)](mail-flow-rules-transport-rules-0.md) 」では、EOP でメールフロールールを作成するための詳細な手順を説明します。

- **Ip 許可一覧と ip 禁止一覧**: ユーザー単位の許可リストとブロックリストがある場合は、セットアッププロセスの一環として、EOP へのリストのコピーをしばらく許可します。 IP 許可一覧と IP 禁止一覧の詳細については、「 [Configure the connection filter policy](../configure-the-connection-filter-policy.md)」を参照してください。

- **セキュリティで保護された通信**: 暗号化されたメッセージングを必要とするパートナーがいる場合は、Exchange 管理センターでこの設定を行うことをお勧めします。 このシナリオを構成するには、「[パートナー組織とのセキュリティで保護されたメールフロー用のコネクタをセットアップ](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)する」を参照してください。

> [!TIP]
> 社内アプライアンスから EOP に切り替える場合は、ビジネス ルールのチェックを実行するアプライアンスまたはサーバーを配置したままにしておくことができます。 たとえば、アプライアンスが送信メールに対してカスタムフィルター処理を実行していて、それを続行したい場合は、インターネットにルーティングする前に、追加のフィルター処理を行うためにアプライアンスに直接メールを送信するように EOP を構成できます。
