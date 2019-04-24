---
title: Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
description: このトピックの目的は、社内の電子メール検疫アプライアンスまたはクラウドベースの保護サービスから Exchange Online Protection (EOP) に切り替えるプロセスを理解していただくことと、着手に役立つリソースを提供することにあります。
ms.openlocfilehash: 0c33d89be5cb4ebf7719e6742532ebfc7a2e5c20
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256205"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Google Postini、Barracuda Spam、 Virus Firewall、または Cisco IronPort から EOP に切り替える

 このトピックの目的は、社内の電子メール検疫アプライアンスまたはクラウドベースの保護サービスから Exchange Online Protection (EOP) に切り替えるプロセスを理解していただくことと、着手に役立つリソースを提供することにあります。多数のスパム対策フィルター ソリューションがありますが、多くの場合 EOP への切り替えプロセスは同様です。
  
EOP を初めてお使いで、切り替えを決定する前に機能の概要を確認したい場合は、まず TechNet の「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」をご覧ください。 
  
EOP に切り替える前に、Exchange Online、社内、またはハイブリッド シナリオによってクラウド内で EOP 保護されたメールボックスをホストするかどうかを検討することが重要です (ハイブリッドとは、社内でいくつかのメールボックスをホストし、Exchange Online で別の部分をホストすることを意味します)。候補となるこれらの各ホスト シナリオ:クラウド、社内、およびハイブリッドは、セットアップの手順が異なる場合があります。適切な展開を選択するための、いくつかの考慮事項を次に示します。
  
- **社内メールボックスを使用した EOP 保護** このシナリオは、使用したい既存のメール ホスティング インフラストラクチャがあるか、または社内のメールボックスを保持しなければならないビジネス要件があり、さらに EOP のクラウドベースの電子メール保護を希望する場合に適しています。「 [EOP スタンドアロンに切り替える](#switch-to-eop-standalone)」で、このシナリオの詳細を説明しています。 
    
- **Exchange Online メールボックスを使用した EOP 保護** このシナリオは、EOP 保護とすべてのメールボックスをクラウドでホストしたい場合に適しています。社内メッセージング サーバーを維持する必要がないため、複雑さを軽減できます。このシナリオについては、「 [Exchange Online に切り替える](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md#BKMK_SwitchEXO)」で説明しています。 
    
- **ハイブリッド メールボックスを使用した EOP 保護** クラウド メールボックスを希望していても、一部のユーザーのためにメールボックスを社内で保持する必要がある場合があります。いくつかのメールボックスを社内でホストし、別の部分を Exchange Online でホストする場合は、このシナリオを選択してください。このシナリオについては、「 [ハイブリッド ソリューションに切り替える](#switch-to-a-hybrid-solution)」で説明しています。 
    
## <a name="switch-to-eop-standalone"></a>EOP スタンドアロンに切り替える

現在、メールボックスを社内でホストし、社内保護アプライアンスまたはクラウド メッセージング保護サービスを使用している場合は、EOP に切り替えて、その保護機能と可用性を活かすことができます。スタンドアロン シナリオ、つまり、社内でメールボックスをホストし EOP を使用して電子メール保護を提供するように EOP を設定するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」で概説されている手順に従います。このトピックでは、サインアップ、ドメインの追加、コネクタとのメール フローの設定などの、EOP 保護の設定に関する手順を概説しています。
  
## <a name="switch-to-exchange-online"></a>Exchange Online に切り替える
<a name="BKMK_SwitchEXO"> </a>

社内アプライアンスによって保護された社内メールボックスがあり、Exchange Online クラウドホスト型メールボックスと EOP 保護に切り替えて Office 365 クラウド メッセージングおよび保護機能を利用したいと考えていることでしょう。ここでは始めに、Office 365 にサインアップして、ドメインを追加できます。このシナリオでは、社内メールボックスへのルーティングがないため、コネクタを設定する必要はありません。「[Office 365 のサインアップ ページ](https://www.microsoft.com/en-us/office365/online-software.aspx)」から始めます。(「[Office 365 の使用を開始](https://go.microsoft.com/fwlink/p/?LinkId=275407)」では、さらに機能を理解するためのリソースを提供しています。) 
  
Office 365 の設定プロセスでは、クラウド ベースのメールボックス ユーザーを作成できます。
  
## <a name="switch-to-a-hybrid-solution"></a>ハイブリッド ソリューションに切り替える
<a name="BKMK_SwitchHybrid"> </a>

ビジネス要件または規制に関する考慮事項があるため、メールボックスの一部のみをクラウドに移行したい場合があります。このようなケースでは、ハイブリッド シナリオを展開すると、ビジネス要件に従ってメールボックスをクラウドに移行できます。EOP 保護を使用したハイブリッド シナリオへの移行は、すべてにおいてクラウドを採用するシナリオより複雑ですが、Microsoft には、ハイブリッドへの移行が簡単に行える数多くのハイブリッド サポートとリソースが用意されています。
  
ハイブリッド展開を検討している場合は、まず「[Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx)」をご確認ください。さらに、ハイブリッド シナリオではメールをルーティングできるいくつかの異なる方法があり、それらを理解しておくことが重要です。「[Transport Routing in Exchange 2013 Hybrid Deployments](http://technet.microsoft.com/library/36c2cea3-2e2f-40ac-88bd-7e1b6bd27828.aspx)」では、ビジネス要件に基づいて最適なルーティング シナリオを選択できるように、各タイプについて説明しています。 
  
## <a name="migration-planning"></a>移行の計画
<a name="sectionSection3"> </a>

EOP への切り替えを決定したら、特に次の分野について考慮する必要があります。
  
- **カスタム フィルター処理ルール** 特定のスパムを検知するためのカスタム フィルター処理またはビジネス ポリシー ルールがある場合は、一定期間、既定の設定で EOP を試行してからルールを移行することをお勧めします。 EOP は既定の設定でエンタープライズ レベルのスパム対策を提供しているため、一部のルールを EOP に移行する必要がない場合があります。 当然、特定のカスタム ビジネス ポリシーを適用するルールがある場合には、それらを作成できます。 [「Exchange Online Protection のメールフロールール (トランスポートルール)](mail-flow-rules-transport-rules-0.md) 」では、EOP でメールフロールールを作成するための詳細な手順を説明します。 
    
- **IP 許可一覧と IP 禁止一覧** ユーザーごとの許可一覧と禁止一覧がある場合は、設定プロセスの一部としてその一覧を EOP にコピーできます。 ip 許可一覧と ip 禁止一覧の詳細については、「 [Configure the connection filter policy](../configure-the-connection-filter-policy.md)」を参照してください。
    
- **セキュリティで保護された通信** 暗号化メッセージングが必要なパートナーがいる場合は、これを Exchange 管理センターで設定することをお勧めします。このシナリオを構成するには、「 [Create connectors for a secure mail channel using transport layer security (TLS)](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx)」を参照してください。
    
> [!TIP]
> 社内アプライアンスから EOP に切り替える場合は、ビジネス ルールのチェックを実行するアプライアンスまたはサーバーを配置したままにしておくことができます。たとえば、アプライアンスが送信メールのカスタム フィルター処理を実行しており、それを継続して実行させたい場合は、メールをインターネットにルーティングする前に、直接アプライアンスに送信し、追加のフィルター処理を行うように EOP を構成できます。この場合のメール フローの設定方法については、「[Exchange Online Protection Connectors - Outbound Smart Host Scenario](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx)」で説明しています。 
  

