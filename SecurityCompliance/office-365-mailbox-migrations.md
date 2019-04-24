---
title: Office 365 のメールボックスの移行
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Office 365 メールボックスの移行に使用されるコマンドレットの概要を簡単に説明します。
ms.openlocfilehash: f21462b1f4a1838ee617e0d429ba73f01ca2db90
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262579"
---
# <a name="office-365-mailbox-migrations"></a>Office 365 のメールボックスの移行
exchange ベースのハイブリッド展開では、オンプレミスの exchange メールボックスを[exchange online](https://docs.microsoft.com/Exchange/exchange-online)組織に移動するか、exchange online メールボックスを exchange[のオンプレミス](https://docs.microsoft.com/Exchange/exchange-server)の組織に移動するかを選択できます。 移行バッチは、オンプレミスの組織と Exchange Online 組織間でメールボックスを移動するときに使用されます。 お客様は、次のコマンドレットを使用して、メールボックスの移行に関する統計情報やその他の情報を確認できます。

- [get-moverequeststatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) -ユーザーメールボックスの既定の統計情報を提供します。これには、ステータス、メールボックスのサイズ、アーカイブメールボックスのサイズ、完了率が含まれます。
- [Get-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) -組織内のメールボックスオブジェクトと属性の要約リストを提供します。
- [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps) -メールボックス、メールユーザー、連絡先、配布グループなどの既存のメールが有効なオブジェクトの一覧を提供します。
- [new-moverequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) -継続的なメールボックスの移行の詳細な状態を提供します。
- [MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) -メールボックスの移動および移行ユーザーに関する情報を提供します。
- [new-migrationbatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) -現在の移行バッチの状態に関する情報を提供します。
- [get-migrationuserstatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) -特定のユーザーの移行状態に関する詳細情報を提供します。
- [get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) -サイズ、メッセージ数、最終アクセス日時などのメールボックスに関する情報を提供します。

その他のコマンドレットの詳細については、「[移動と移行のコマンドレット (Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))」を参照してください。
