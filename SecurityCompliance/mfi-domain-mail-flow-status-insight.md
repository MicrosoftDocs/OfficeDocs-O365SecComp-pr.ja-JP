---
title: トップドメインメールフローのステータスの洞察
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある上位のドメインメールフローの状態について理解できます。
ms.openlocfilehash: 851ef1438f111a36f69563670bbd0835a9956edc
ms.sourcegitcommit: e05e83212e7ca4e84f2ddb0de0297895b995338d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "33868594"
---
# <a name="top-domain-mail-flow-status-insight"></a>トップドメインメールフローのステータスの洞察

**上位ドメインのメールフローの状態**に関する情報は、メールフローの観点から、組織のドメインの現在の状態を示します。 この洞察は、***メールフローに影響を与える***(たとえば、外部電子メールを受信できない) 問題が発生しているドメインを特定してトラブルシューティングするのに役立ちます。特に、ドメインの有効期限、または間違った MX レコードがあるドメイン。

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある上位ドメインフローの状態の洞察](media/domain-mail-flow-status-selected.png)

[**詳細**] をクリックすると、各ドメインの状態の詳細が表示されるポップアップが表示されます。

ドメインに緑のチェックマークが表示されている場合は、現在の MX レコード (メールフローインサイトダッシュボードを参照した場合) がレコードに設定されている値と一致し、ドメインが過去2時間以内に電子メールを受信したことを示します。

ドメインの赤色の x は、MX レコードが変更されており、過去6時間以内にドメインがメールを受信していないことを示します。 これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。 ドメインレジストラーまたは DNS ホスティングサービスを使用して、ドメインの有効期限が切れていないか、またはドメインの MX レコードが正しくないかどうかを確認します。

![トップドメインフローの状態に関する詳細ポップアップ](media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a>関連項目

メールフローダッシュボードの他のメールフローインサイトの詳細については、「 [Security &/コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
