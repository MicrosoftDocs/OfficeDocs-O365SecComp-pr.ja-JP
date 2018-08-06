---
title: EOP のメール フロー
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/13/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: Exchange Online Protection (EOP) のお客様の場合、組織に送信されたすべてのメッセージは EOP を通って従業員に配信されます。クラウド内のすべてのメールボックスを Exchange Online を使用してホストしているか、既存のインフラストラクチャの利用を継続するためなどの理由で、メールボックスを社内でホストしている (いわゆるスタンドアロン シナリオ) かに関係なく、処理のために EOP を通過してから従業員の受信トレイに配信されるメッセージのルーティング方法に関するオプションがあります。
ms.openlocfilehash: d35e6f2fdbe7bb991ebf3d766fadae34638831ef
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027344"
---
# <a name="mail-flow-in-eop"></a>EOP のメール フロー

Exchange Online Protection (EOP) のお客様の場合、組織に送信されたすべてのメッセージは EOP を通って従業員に配信されます。クラウド内のすべてのメールボックスを Exchange Online を使用してホストしているか、既存のインフラストラクチャの利用を継続するためなどの理由で、メールボックスを社内でホストしている (いわゆるスタンドアロン シナリオ) かに関係なく、処理のために EOP を通過してから従業員の受信トレイに配信されるメッセージのルーティング方法に関するオプションがあります。
  
メッセージングをビジネス要件に適合させるためにカスタム メール ルーティングを構成したい場合があります。たとえば、すべての送信メールをポリシー フィルタリング アプライアンスを通過させるようにすることができます。 
  
## <a name="working-with-messages-and-message-access-options"></a>メッセージとメッセージ アクセス オプションの操作

EOP はメッセージのルーティング方法の柔軟性を高めます。以下のトピックで、メール フロー プロセスの手順について説明します。
  
[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx) ディレクトリ ベースのエッジ ブロック機能を使って無効な受信者宛てのメッセージをサービス ネットワーク境界で拒否する方法について説明します。 
  
「[View or Edit Managed Domains in EOP](http://technet.microsoft.com/library/69523bec-07ee-46f9-ae08-40437e39b87c.aspx)」では、EOP サービスに関連付けられたドメインの管理方法について説明します。 
  
組織にサブドメインを追加する場合にも、それらの管理に EOP サービスを活用できます。サブドメインの詳細については、「[Enable Mail Flow for Subdomains in Exchange Online](http://technet.microsoft.com/library/4033a30a-f506-481c-8ef0-fd9a0508ae38.aspx)」を参照してください。
  
「[Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx)」では、コネクタについて概説し、それを使ってメール ルーティングをカスタマイズする方法を示します。シナリオには、パートナー組織との安全な通信の保証とスマート ホストのセットアップが含まれます。 
  
各ユーザーの迷惑メール フォルダーに迷惑メールが正しくルーティングされることを確認するには、いくつかの構成手順を行う必要があります。詳細については、[各ユーザーの迷惑メール フォルダーに迷惑メールがルーティングされるようにします](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。メッセージを各ユーザーの迷惑メール フォルダーに移動したくない場合は、Exchange 管理センターでコンテンツ フィルター ポリシーを編集することによって別のアクションができます。詳細については、[スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)を参照してください。
  
## <a name="verify-mail-flow"></a>メール フローを確認する

コネクタ構成を含む EOP セットアップが正しく機能していることを確認するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」の「このタスクの検証方法」セクションを参照してください。 
  
「[Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)」では、メール フローが正しくセットアップされているかどうかのテスト手順を示します。 
  

