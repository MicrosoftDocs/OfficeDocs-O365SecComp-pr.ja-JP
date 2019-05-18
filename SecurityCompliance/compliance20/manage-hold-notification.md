---
title: 保留通知を管理する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 0b1b20a8b41803a945bc9f5c39cd0618c420b0c0
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151739"
---
# <a name="manage-hold-notifications"></a>保留通知を管理する

法的情報開示通知ワークフローを開始したら、Advanced eDiscovery を活用して、コミュニケーションの状態を追跡できます。 [通信] タブでは、高度な電子情報開示ケース内のすべての保留通知が対象になります。 ここでは、割り当てられている、または通知を確認した保管担当者の数などの詳細を確認できます。

## <a name="view-communication-details"></a>コミュニケーションの詳細を表示する

### <a name="track-acknowledgements"></a>確認を追跡する

[**通信**] タブで通信を選択すると、保留通知が確認されている保管担当者の一覧を表示できます。 

### <a name="preview-acknowledgements"></a>確認のプレビュー

[通信の詳細] ポップアップでは、法的情報保留通信に関する詳細をプレビューできます。 **プレビュー**パネルでは、法的情報保留の通知の簡易スナップショット、およびワークフロー通知の設定とコンテンツを表示できます。 プレビューパネルには、保管担当者が既に通知を確認済みであることに関する詳細も表示されます。

## <a name="taking-action-on-existing-communications"></a>既存の通信に対してアクションを実行する

### <a name="re-send-a-hold-notice"></a>保留通知を再送信する

場合によっては、保管担当者が電子メールを毎日の作業で追跡できなくなります。 または、長期間訴訟が発生した場合は、保管担当者が到着して、通知を再送信するよう求められることがあります。 法的情報保持通知に関するワークフローを管理する際には、「ユーザーのメールボックスの先頭」に戻るために通知を再送信する必要がある場合があります。

保留通知は、次の方法で保管担当者に再送信できます。
1. **セキュリティ/コンプライアンス _GT_ Advanced eDiscovery**でケースに移動します。
2. ケースを選択したら、[**通信**] タブに移動します。
3. 法的情報保留通知を保管担当者に再送信するには、通信を選択し、[**再送信**] オプションをクリックします。
4. 保管担当者が保留通知をまだ確認していない場合は、アラームとエスカレーションフローが再起動されます。 保管担当者が既に保留通知を受信確認している場合、保管担当者は最初のホールド通知のコピーを受け取ります。

> [!NOTE]
> 法的情報保留通知は、通信に割り当てられている保管担当者に再送信することのみできます。 

### <a name="edit-a-communication"></a>通信を編集する

#### <a name="update-preservation-requirements"></a>更新保持要件
  
ケースが進行するにつれて、保管担当者は、以前に指示されていたのとは別のデータを保持する必要がある場合があります。 電子情報開示の用語では、更新されたコンテンツを含む保留通知を再発行する必要があります。

最初の保留通知の内容を更新するには、次のようにします。

1. **セキュリティ/コンプライアンス _GT_ Advanced eDiscovery**でケースに移動します。
2. ケースを選択したら、[**通信**] タブに移動します。
3. 更新するホールド通知を選択し、[**編集**] をクリックします。
4. 編集ワークフローで、[**ポータルコンテンツを定義**する] を選択し、通知の内容を更新します。 
5. **[保存]** をクリックします。 保存された後、法的情報保留通知に対して現在割り当てられているすべての保管担当者に再発行通知が送信されます。 また、アラーム/エスカレーションの通知が有効になっている場合は、これらのワークフローも再起動されます。 


#### <a name="update-legal-hold-notifications-and-settings"></a>法的情報保留通知と設定を更新する

発行、リリース、再発行、アラーム、またはエスカレーションの通知のコンテンツまたは設定を更新すると、これらの変更は、ワークフローによって生成された以降のすべての通信に適用されます。

## <a name="related-information"></a>関連情報 

- [法的情報保留通知を作成する](create-hold-notification.md)
    
- [保留通知を確認する](acknowledge-hold-notification.md)
    
- [ケースにカストディアンを追加する](add-custodians-to-case.md)