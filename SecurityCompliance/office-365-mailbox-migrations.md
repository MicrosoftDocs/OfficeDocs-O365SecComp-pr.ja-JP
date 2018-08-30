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
# <a name="office-365-mailbox-migrations"></a><span data-ttu-id="5bdd2-103">Office 365 のメールボックスの移行</span><span class="sxs-lookup"><span data-stu-id="5bdd2-103">Office 365 Mailbox Migrations</span></span>
<span data-ttu-id="5bdd2-p101">Exchange ベースのハイブリッド展開では、お客様は、オンプレミスの Exchange メールボックスを[Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)組織に移動するか、[社内の Exchange](https://docs.microsoft.com/Exchange/exchange-server)組織に Exchange Online のメールボックスを移動して選択できます。設置型および Exchange Online 組織間でメールボックスを移動する場合は、移行バッチが使用されます。お客様には、統計情報と、次のコマンドレットを使用してメールボックスの移行に関するその他の情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-p101">With an Exchange-based hybrid deployment, customers can choose to either move on-premises Exchange mailboxes to an [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) organization or move Exchange Online mailboxes to an [Exchange on-premises](https://docs.microsoft.com/Exchange/exchange-server) organization. Migration batches are used when moving mailboxes between on-premises and Exchange Online organizations. Customers can review statistics and other information about mailbox migrations using the following cmdlets:</span></span>

- <span data-ttu-id="5bdd2-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) - は、状態、メールボックスのサイズが含まれている、ユーザーのメールボックスの既定の統計情報のアーカイブ メールボックスのサイズと割合を完了します。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) - Provides default statistics for a user mailbox, which includes the status, mailbox size, archive mailbox size and percentage complete.</span></span>
- <span data-ttu-id="5bdd2-108">[Get メールボックス](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
)- には、メールボックス オブジェクトと組織内の属性の一覧が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) - Provides a summary list of mailbox objects and attributes in the organization.</span></span>
- <span data-ttu-id="5bdd2-109">[受信者の取得](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps)には、メールボックス、メール ユーザー、連絡先および配布グループなどの既存のメールが有効なオブジェクトの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps) - Provides a list of existing mail-enabled objects such as mailboxes, mail users, contacts and distribution groups.</span></span>
- <span data-ttu-id="5bdd2-110">[Get MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps)では、継続的なメールボックスの移行の詳細なステータスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) - Provides a detailed status of an ongoing mailbox migration.</span></span>
- <span data-ttu-id="5bdd2-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) - は、移動や移行のユーザーのメールボックスに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) - Provides information about the mailbox move and migration users.</span></span>
- <span data-ttu-id="5bdd2-112">[Get MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) - 現在の移行バッチのステータスに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) - Provides information on the status of current migration batch.</span></span>
- <span data-ttu-id="5bdd2-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) - は、特定のユーザーの移行のステータスに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) - Provides detailed information about the migration status for a specific user.</span></span>
- <span data-ttu-id="5bdd2-114">[Get MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) ・ サイズ、メッセージの数、および最終アクセス日時など、メールボックスに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) - Provides information about mailboxes, such as size, the number of messages, and the last accessed time.</span></span>

<span data-ttu-id="5bdd2-115">追加のコマンドレットの詳細については、 [Exchange のオンラインでの移動と移行のコマンドレット](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bdd2-115">For more information on additional cmdlets, see [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
