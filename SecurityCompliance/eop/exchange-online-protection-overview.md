---
title: Exchange Online Protection の概要
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: マイクロソフト Exchange Online Protection (EOP) は、クラウドベースの電子メール フィルタリング サービスであり、スパムやマルウェアから組織を保護するのに役立ち、メッセージング ポリシー違反から組織を保護する機能が含まれています。
ms.openlocfilehash: 89852c7ba211ccb266c8b231b00d3d83987a5f20
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026694"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection の概要

Microsoft Exchange Online Protection (EOP) は、スパムやマルウェアから組織を保護するクラウドベースの電子メール フィルター処理サービスであり、メッセージング ポリシー違反から組織を保護する機能を備えています。EOP はメッセージング環境の管理を簡素化し、社内のハードウェアおよびソフトウェアの維持に伴う負荷の多くを軽減します。
  
メッセージング保護に EOP を使用できる基本的な方法として、次のようなものがあります。
  
- **スタンドアロンのシナリオ**EOP は、クラウド ベースの電子メールの保護、オンプレミスの Microsoft Exchange Server 2013 環境、従来の Exchange Server のバージョンでは、またはその他の設置型の SMTP メール ・ ソリューションを提供します。 
    
- **Microsoft Exchange Online の一部として** 既定で、EOP は Microsoft Exchange Online クラウドホスト型メールボックスを保護します。 
    
- **ハイブリッド展開で** EOP はメッセージング環境を保護し、社内メールボックスとクラウド メールボックスが混在している場合のメール ルーティングを制御するように構成できます。 
    
## <a name="how-eop-works"></a>EOP の仕組み

EOP の仕組みを理解すると、受信メールの処理方法がわかりやすくなります。
  
![EOP のメールの処理](../media/EOP-email-processing.png)
  
受信メッセージは最初に、送信者の評価をチェックし、マルウェアがメッセージを検査する、接続フィルターを通過します。スパム メールの大多数は、この時点で停止、EOP によって削除されました。メッセージは、カスタム トランスポート ルールを作成するか、テンプレートから適用することに対してメッセージが評価される場所、ポリシーのフィルター処理を続行します。たとえば、特定の送信者からメールを受信したときに、マネージャーに通知を送信するルールを持つことができます。(データ損失の防止策のチェックも場合に発生するこの時点で、機能を使用できる機能については、 [Exchange オンライン保護サービスの説明](https://go.microsoft.com/fwlink/p/?LinkId=320619)を参照してください。)次に、メッセージを通過コンテンツ フィルタ リングでは、用語集や迷惑メールに共通のプロパティのコンテンツをチェックする場所です。メッセージであると判断の設定に基づいて、その他のオプションの中から、検疫またはユーザーの迷惑メール フォルダーに、コンテンツ フィルターによって迷惑メールを送信することができます。メッセージのすべてのこれらの保護層に成功をした後、受信者に配信されます。
  
### <a name="eop-datacenters"></a>EOP データセンター

EOP は、最良の可用性を提供するために設計された複数のデータセンターから成る世界規模のネットワーク上で稼働します。たとえば、あるデータセンターが使用できなくなった場合、電子メール メッセージはサービスの中断なく、自動的に別のデータセンターにルーティングされます。各データセンターのサーバーがユーザーの代わりにメッセージを受け付け、組織とインターネットの間を分離するレイヤーが提供されるため、組織のサーバーの負荷が軽減されます。この高可用性のネットワークによって、Microsoft は適切なタイミングで組織に電子メールが配信されることを保証できます。 
  
EOP はデータセンター間の負荷分散を実行しますが、1 つの地域内でのみ行います。1 つの地域でサービスが提供されている場合は、すべてのメッセージがその地域のメール ルーティングを使用して処理されます。EOP データセンターの地域メール ルーティングの動作を以下に示します。
  
- アメリカでのすべて Exchange Online のメールボックス内にある南アメリカ以外の米国のデータ センターでブラジルとチリのデータ センターが使用されているとカナダではカナダのデータ センターが使用されています。EOP フィルタ リングの米国のデータ センター経由で、南アメリカとカナダでは、お客様のメッセージを含むすべての電子メール メッセージただし、テナントが格納されているデータ センターで quaratined の電子メールが格納されている.
    
- ヨーロッパ、中東、およびアフリカ (EMEA) では、すべての Exchange Online メールボックスが EMEA データセンターに配置され、すべてのメッセージが EOP フィルター処理のために EMEA データセンター経由でルーティングされます。
    
- アジア太平洋 (APAC) では、すべての Exchange Online メールボックスが APAC データセンターに配置されていますが、現在のところ、メッセージは EOP フィルター処理のために EMEA データセンター経由でルーティングされています。ただし、2014 年第 4 四半期に、EOP フィルター処理のために APAC データセンター経由でメッセージがルーティングされるように変更される予定です。
    
- Government Community Cloud (GCC) では、すべての Exchange Online メールボックスが米国データセンターに配置され、すべてのメッセージが EOP フィルター処理のために米国データセンター経由でルーティングされます。
    
## <a name="eop-plans-and-features"></a>EOP のプランと機能

EOP のサブスクリプション プランを次に示します。
  
- **EOP スタンドアロン** EOP が社内メールボックスを保護します。 
    
- **Exchange Online の EOP 機能** EOP が Exchange Online クラウドホスト型メールボックスを保護します。 
    
- **Exchange Enterprise CAL とサービス** EOP スタンドアロンと同様に、EOP が社内メールボックスを保護します。また、データ損失防止 (DLP) と Web サービスを使用したレポート機能を備えています。 
    
すべての EOP サブスクリプション プランについての要件、重要な制限および機能の可用性の詳細については、「[Exchange Online Protection サービスの説明](https://go.microsoft.com/fwlink/p/?LinkId=320619)」を参照してください。
  
## <a name="setting-up-eop"></a>EOP の設定

EOP のセットアップは、特にコンプライアンス ルールが少ない小規模な組織の場合に、シンプルにすることができます。ただし、複数ドメイン、カスタム コンプライアンス ルール、またはハイブリッド メール フローが存在する大規模な組織の場合は、セットアップにより多くの計画や時間が必要となることがあります。
  
すでに EOP を購入している場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照して、メッセージング環境を保護するように EOP を構成するために必要なすべての手順が完了していることを確認してください。 
  
## <a name="for-more-information"></a>詳細情報

[EOP の機能](eop-features.md)
  
[EOP の使用を開始するためのビデオ](videos-for-getting-started-with-eop.md)
  
[EOP の一般的な FAQ](eop-general-faq.md)
  
[EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.md)
  
[代理管理の FAQ](delegated-administration-faq.md)
  
[ドメインと設定を 1 つの EOP 組織から別の EOP 組織に移動する](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
  

