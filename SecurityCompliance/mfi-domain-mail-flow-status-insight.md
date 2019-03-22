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
description: 管理者は、Office 365 Security & コンプライアンスセンターのメールフローダッシュボードにある上位ドメインのメールフローの状態に関する洞察を得ることができます。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 04aa986982465a4c66fbf99f517fb34622d65e19
ms.sourcegitcommit: fec1010e405f14e792d650aee0312b78fced3343
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "30722959"
---
# <a name="top-domain-mail-flow-status-insight"></a>トップドメインメールフローのステータスの洞察

> [!NOTE]
> このトピックで説明する機能は、すべての Office 365 組織に展開されていないため、変更される可能性があります。

**上位ドメインのメールフローの状態**に関する情報は、メールフローの観点から、組織のドメインの現在の状態を示します。 この洞察は、***メールフローに影響を与える***(たとえば、外部電子メールを受信できない) 問題が発生しているドメインを特定してトラブルシューティングするのに役立ちます。特に、ドメインの有効期限、または間違った MX レコードがあるドメイン。

![Office 365 Security & コンプライアンスセンターのメールフローダッシュボードにある上位ドメインフローの状態の洞察](media/domain-mail-flow-status-selected.png)

[**詳細**] をクリックすると、各ドメインの状態の詳細が表示されるポップアップが表示されます。

ドメインに緑のチェックマークが表示されている場合は、現在の MX レコード (メールフローインサイトダッシュボードを参照した場合) がレコードに設定されている値と一致し、ドメインが過去2時間以内に電子メールを受信したことを示します。

ドメインの赤色の x は、MX レコードが変更されており、過去6時間以内にドメインがメールを受信していないことを示します。 これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。 ドメインレジストラーまたは DNS ホスティングサービスを使用して、ドメインの有効期限が切れていないか、またはドメインの MX レコードが正しくないかどうかを確認します。

![トップドメインフローの状態に関する詳細ポップアップ](media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a>関連項目

メールフローダッシュボードの他のメールフローインサイトの詳細については、「 [Security &/コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
