---
title: EOP のメール フロー
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/13/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: Exchange Online Protection (EOP) のお客様の場合、組織に送信されたすべてのメッセージは EOP を通って従業員に配信されます。クラウド内のすべてのメールボックスを Exchange Online を使用してホストしているか、既存のインフラストラクチャの利用を継続するためなどの理由で、メールボックスを社内でホストしている (いわゆるスタンドアロン シナリオ) かに関係なく、処理のために EOP を通過してから従業員の受信トレイに配信されるメッセージのルーティング方法に関するオプションがあります。
ms.openlocfilehash: b223efc62ff875ed345ce27a17263b3876829999
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255895"
---
# <a name="mail-flow-in-eop"></a>EOP のメール フロー

Exchange Online Protection (EOP) のお客様の場合、組織に送信されたすべてのメッセージは EOP を通って従業員に配信されます。クラウド内のすべてのメールボックスを Exchange Online を使用してホストしているか、既存のインフラストラクチャの利用を継続するためなどの理由で、メールボックスを社内でホストしている (いわゆるスタンドアロン シナリオ) かに関係なく、処理のために EOP を通過してから従業員の受信トレイに配信されるメッセージのルーティング方法に関するオプションがあります。
  
メッセージングをビジネス要件に適合させるためにカスタム メール ルーティングを構成したい場合があります。たとえば、すべての送信メールをポリシー フィルタリング アプライアンスを通過させるようにすることができます。 
  
## <a name="working-with-messages-and-message-access-options"></a>メッセージとメッセージ アクセス オプションの操作

EOP はメッセージのルーティング方法の柔軟性を高めます。以下のトピックで、メール フロー プロセスの手順について説明します。
  
[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx) ディレクトリ ベースのエッジ ブロック機能を使って無効な受信者宛てのメッセージをサービス ネットワーク境界で拒否する方法について説明します。 
  
「[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)」では、EOP サービスに関連付けられたドメインの管理方法について説明します。 
  
組織にサブドメインを追加する場合にも、それらの管理に EOP サービスを活用できます。サブドメインの詳細については、「[Enable Mail Flow for Subdomains in Exchange Online](http://technet.microsoft.com/library/4033a30a-f506-481c-8ef0-fd9a0508ae38.aspx)」を参照してください。
  
「[Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx)」では、コネクタについて概説し、それを使ってメール ルーティングをカスタマイズする方法を示します。シナリオには、パートナー組織との安全な通信の保証とスマート ホストのセットアップが含まれます。 
  
迷惑メールがそれぞれのユーザーの迷惑メール フォルダーに正しくルーティングされることを保証するには、一組の構成手順を実行する必要があります。 これらは、[スパムが各ユーザーの迷惑メールフォルダーにルーティングされる](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)ことを確認するために詳細に記載されています。 メッセージをそれぞれのユーザーの迷惑メール フォルダーに移動しない場合は、Exchange 管理センターでコンテンツ フィルター ポリシーを編集することによって別のアクションを選択できます。 詳細については、「 [スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)」を参照してください。
  
## <a name="verify-mail-flow"></a>メール フローを確認する

コネクタ構成を含む EOP セットアップが正しく機能していることを確認するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」の「このタスクの検証方法」セクションを参照してください。 
  
「[Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)」では、メール フローが正しくセットアップされているかどうかのテスト手順を示します。 
  

