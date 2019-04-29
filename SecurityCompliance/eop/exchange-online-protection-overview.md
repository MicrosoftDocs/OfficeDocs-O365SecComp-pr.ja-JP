---
title: Exchange Online Protection の概要
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 01/31/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: マイクロソフト Exchange Online Protection (EOP) は、クラウドベースの電子メール フィルタリング サービスであり、スパムやマルウェアから組織を保護するのに役立ち、メッセージング ポリシー違反から組織を保護する機能が含まれています。
ms.openlocfilehash: a0b736eb9773ace87f32f1272b3f4326532206d2
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402885"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection の概要

マイクロソフト Exchange Online Protection (EOP) は、クラウドベースの電子メール フィルタリング サービスであり、スパムやマルウェアから組織を保護するのに役立ち、メッセージング ポリシー違反から組織を保護する機能が含まれています。EOP はメッセージング環境の管理を簡素化し、社内のハードウェアおよびソフトウェアの維持に伴う負荷の多くを軽減します。
  
メッセージング保護に EOP を使用できる基本的な方法として、次のようなものがあります。
  
- **スタンドアロンのシナリオで**EOP は、社内の Microsoft exchange server 2013 環境、レガシ Exchange server バージョン、またはその他の社内 SMTP 電子メールソリューションに対して、クラウドベースの電子メール保護を提供します。 
    
- **Microsoft Exchange Online の一部として** 既定で、EOP は Microsoft Exchange Online クラウドホスト型メールボックスを保護します。 Exchange Online の機能の構成については、「[脅威から保護](../protect-against-threats.md)する」を参照してください。 
    
- **ハイブリッド展開で** EOP はメッセージング環境を保護し、社内メールボックスとクラウド メールボックスが混在している場合のメール ルーティングを制御するように構成できます。 

これらの Exchange Online Protection の記事は、ハイブリッド環境およびオンプレミス環境に適用されます。 
    
## <a name="how-eop-works"></a>EOP の仕組み

EOP の仕組みを理解すると、受信メールの処理方法がわかりやすくなります。
  
![EOP-電子メール処理](../media/EOP-email-processing.png)
  
受信メッセージは、最初は、送信者の評価をチェックし、マルウェアのメッセージを検査することによって、接続フィルターによって渡されます。 スパムの大部分は、この時点で停止し、EOP によって削除されます。 メッセージはポリシーのフィルター処理によって続行されます。これにより、テンプレートから作成または適用するカスタムメールフロールール (トランスポートルールとも呼ばれる) に対してメッセージが評価されます。 たとえば、特定の送信者からのメールが到着すると、管理者に通知を送信するルールを作成できます。 (この機能を使用している場合は、この時点でデータ損失防止チェックも行われます。機能の可用性の詳細については、「 [Exchange Online Protection サービスの説明](https://go.microsoft.com/fwlink/p/?LinkId=320619)」を参照してください)。次に、メッセージはコンテンツフィルターを通過し、スパムに共通の用語やプロパティがないかどうかが確認されます。 コンテンツフィルターによってスパムと判断されたメッセージは、設定に基づいて、ユーザーの迷惑メールフォルダーまたは検疫に送信できます。 このような保護層をすべて正常に通過すると、メッセージは受信者に配信されます。
  
### <a name="eop-datacenters"></a>EOP データセンター

EOP は、最良の可用性を提供するために設計された複数のデータセンターから成る世界規模のネットワーク上で稼働します。たとえば、あるデータセンターが使用できなくなった場合、電子メール メッセージはサービスの中断なく、自動的に別のデータセンターにルーティングされます。各データセンターのサーバーがユーザーの代わりにメッセージを受け付け、組織とインターネットの間を分離するレイヤーが提供されるため、組織のサーバーの負荷が軽減されます。この高可用性のネットワークによって、Microsoft は適切なタイミングで組織に電子メールが配信されることを保証できます。 
  
EOP はデータセンター間の負荷分散を実行しますが、1 つの地域内でのみ行います。1 つの地域でサービスが提供されている場合は、すべてのメッセージがその地域のメール ルーティングを使用して処理されます。EOP データセンターの地域メール ルーティングの動作を以下に示します。
  
    
- ヨーロッパ、中東、およびアフリカ (EMEA) では、すべての Exchange Online メールボックスが EMEA データセンターに配置され、すべてのメッセージが EOP フィルター処理のために EMEA データセンター経由でルーティングされます。
    
- アジア太平洋 (apac) では、すべての Exchange Online メールボックスが apac データセンターに配置されていますが、現在、メッセージは EOP フィルター処理のために apac データセンター経由でルーティングされます。

- 南北アメリカでは、すべての Exchange Online メールボックスは米国のデータセンターに配置されており、ブラジルとチリのデータセンターが使用されている南米と、カナダのデータセンターが使用されているカナダには例外があります。 南米およびカナダの顧客宛てのメッセージを含むすべての電子メールメッセージは、EOP フィルター処理のためにローカルデータセンターを経由してルーティングされます。quaratined 電子メールは、テナントが配置されているデータセンターに格納されます。
    
- ヨーロッパ、中東、およびアフリカ (EMEA) では、すべての Exchange Online メールボックスが EMEA データセンターに配置され、すべてのメッセージが EOP フィルター処理のために EMEA データセンター経由でルーティングされます。
    
- アジア太平洋 (apac) では、すべての Exchange Online メールボックスが apac データセンターに配置されており、現在、メッセージは EOP フィルター処理のために apac データセンター経由でルーティングされます。
    
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
  
[EOP の一般的な FAQ](eop-general-faq.md)
  
[EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.md)
  
[代理管理に関する FAQ](delegated-administration-faq.md)
  
[ドメインと設定を 1 つの EOP 組織から別の EOP 組織に移動する](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
  

