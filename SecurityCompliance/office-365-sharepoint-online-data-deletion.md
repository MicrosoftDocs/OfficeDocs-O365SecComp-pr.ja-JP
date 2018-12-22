---
title: Office 365 の SharePoint のオンライン ・ データの削除
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: SharePoint Online でのデータ削除の詳細については。
ms.openlocfilehash: 8a84859ce170a4c3ca713c751aef2b6d5b911c55
ms.sourcegitcommit: 29ba4c36af8e90ddc8d885863ef25bac2cffbe94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2018
ms.locfileid: "27411163"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a><span data-ttu-id="173a3-103">Office 365 で SharePoint のオンライン ・ データの削除</span><span class="sxs-lookup"><span data-stu-id="173a3-103">SharePoint Online Data Deletion in Office 365</span></span>

<span data-ttu-id="173a3-p101">SharePoint Online は、アプリケーション データベースの抽象化されたコードとオブジェクトを格納します。SharePoint Online にファイルをアップロードすると、そのファイルは分解し、アプリケーション コードに変換し、複数のデータベース間で複数のテーブルに格納されています。SharePoint Online では、お客様にアップロードするすべてのコンテンツが (可能性のある複数 AES の 256 ビットのキー) で暗号化されているチャンクに分割し、データ センターに分散します。チャンクに分割し、暗号化のプロセスに関する詳細については、[マイクロソフトのクラウドでの暗号化](office-365-encryption-in-the-microsoft-cloud-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="173a3-p101">SharePoint Online stores objects as abstracted code within application databases. When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases. In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter. For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span> 

<span data-ttu-id="173a3-p102">SharePoint online では、アイテムは元の場所からそれらを削除する時間から 93 日間保持されます。ままサイトのごみ箱で全体の時間では、だれかがそこからそれらを削除または、[ごみ箱を空にしない限り、です。その場合は、項目は、サイト コレクションの 93 の日の残りの部分のまま、ごみ箱に移動します。削除済みアイテムを復元する方法の詳細情報は、 [SharePoint サイトのごみ箱のアイテムを復元](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
)し、[復元は、サイト コレクションのごみ箱からアイテムを削除](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)を参照してください。ごみ箱の保存期間は、SharePoint Online に設定可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="173a3-p102">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location. They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin. In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days. For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="173a3-113">サイト コレクションを削除する場合も、コレクション、およびその中のすべてのコンテンツ内のサイトの階層を削除しています。</span><span class="sxs-lookup"><span data-stu-id="173a3-113">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>
- <span data-ttu-id="173a3-114">ドキュメントおよびドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="173a3-114">Documents and document libraries</span></span>
- <span data-ttu-id="173a3-115">リストとリスト データ</span><span class="sxs-lookup"><span data-stu-id="173a3-115">Lists and list data</span></span>
- <span data-ttu-id="173a3-116">サイト構成の設定</span><span class="sxs-lookup"><span data-stu-id="173a3-116">Site configuration settings</span></span>
- <span data-ttu-id="173a3-117">サイトまたはサブサイトに関連付けられているロールおよびセキュリティの情報</span><span class="sxs-lookup"><span data-stu-id="173a3-117">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="173a3-118">サブサイト最上位の web サイト、コンテンツ、およびユーザー情報の</span><span class="sxs-lookup"><span data-stu-id="173a3-118">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="173a3-119">サイト コレクションを削除してしまった場合、復元できる、グローバルまたは SharePoint によって SharePoint 管理センターを使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="173a3-119">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span> 

<span data-ttu-id="173a3-p103">ハード削除は、保存とバックアップの期間が経過した場合、または管理者が完全に[削除 SPODeletedSite コマンドレット](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)を使用してサイト コレクションを削除すると、ユーザーがサイト コレクションのごみ箱から削除済みアイテムを削除するときに発生します。ハードのユーザーを削除すると、完全に削除 (パージ) SharePoint Online のコンテンツの削除されたチャンクのすべての暗号化キーも削除されます。以前削除されたチャンクを格納するディスク上のブロックは、使用されていないために使用できる再使用としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="173a3-p103">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted. The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
