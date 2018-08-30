---
title: Office 365 のメールボックスの移行
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Office 365 のメールボックスを移行するために使用するコマンドレットの概要です。
ms.openlocfilehash: 86896d956072b5c11e3b3292363bb32312ff1187
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532403"
---
# <a name="office-365-mailbox-migrations"></a>Office 365 のメールボックスの移行
Exchange ベースのハイブリッド展開では、お客様は、オンプレミスの Exchange メールボックスを[Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)組織に移動するか、[社内の Exchange](https://docs.microsoft.com/Exchange/exchange-server)組織に Exchange Online のメールボックスを移動して選択できます。設置型および Exchange Online 組織間でメールボックスを移動する場合は、移行バッチが使用されます。お客様には、統計情報と、次のコマンドレットを使用してメールボックスの移行に関するその他の情報を確認できます。

- [Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) - は、状態、メールボックスのサイズが含まれている、ユーザーのメールボックスの既定の統計情報のアーカイブ メールボックスのサイズと割合を完了します。
- [Get メールボックス](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
)- には、メールボックス オブジェクトと組織内の属性の一覧が用意されています。
- [受信者の取得](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps)には、メールボックス、メール ユーザー、連絡先および配布グループなどの既存のメールが有効なオブジェクトの一覧を示します。
- [Get MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps)では、継続的なメールボックスの移行の詳細なステータスを提供します。
- [Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) - は、移動や移行のユーザーのメールボックスに関する情報を提供します。
- [Get MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) - 現在の移行バッチのステータスに関する情報を提供します。
- [Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) - は、特定のユーザーの移行のステータスに関する詳細情報を提供します。
- [Get MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) ・ サイズ、メッセージの数、および最終アクセス日時など、メールボックスに関する情報を提供します。

追加のコマンドレットの詳細については、 [Exchange のオンラインでの移動と移行のコマンドレット](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)を参照してください。
