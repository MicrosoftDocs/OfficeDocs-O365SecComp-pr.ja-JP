---
title: Office 365 の SharePoint のオンライン ・ データの削除
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
description: SharePoint Online でのデータ削除の詳細については。
ms.openlocfilehash: c281f6de9cd9e4978ac4a6997333d71d8835420f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531746"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a><span data-ttu-id="91f8c-103">Office 365 で SharePoint のオンライン ・ データの削除</span><span class="sxs-lookup"><span data-stu-id="91f8c-103">SharePoint Online Data Deletion in Office 365</span></span>

<span data-ttu-id="91f8c-p101">SharePoint Online は、アプリケーション データベースの抽象化されたコードとオブジェクトを格納します。SharePoint Online にファイルをアップロードすると、そのファイルは分解し、アプリケーション コードに変換し、複数のデータベース間で複数のテーブルに格納されています。SharePoint Online では、お客様にアップロードするすべてのコンテンツが (可能性のある複数 AES の 256 ビットのキー) で暗号化されているチャンクに分割し、データ センターに分散します。チャンクに分割し、暗号化のプロセスに関する詳細については、[マイクロソフトのクラウドでの暗号化](office-365-encryption-in-the-microsoft-cloud-overview.md)を参照してください。データ保護サービスは、SharePoint Online のデータの損失を防ぐために提供されます。具体的には、バックアップは 12 時間ごとを実行し、14 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="91f8c-p101">SharePoint Online stores objects as abstracted code within application databases. When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases. In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter. For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](office-365-encryption-in-the-microsoft-cloud-overview.md). Data protection services are provided to prevent the loss of SharePoint Online data. Specifically, backups are performed every 12 hours and retained for 14 days.</span></span>

<span data-ttu-id="91f8c-p102">SharePoint Online サイトからコンテンツを削除する場合は削除されませんすぐに。必要な場合は、サイトのごみ箱、復元することに送信されます。([削除済みのサイト コレクションのごみ箱からアイテムを復元](https://support.office.com/article/Restore-deleted-items-from-the-site-collection-recycle-bin-5fa924ee-16d7-487b-9a0a-021b9062d14b)の「復元の手順)既定のサイトのごみ箱の保存期間は、約 90 日です。コンテンツをサイトのごみ箱から削除する場合、サイト コレクションのごみ箱は保管期間は 30 日間に送信されます。管理者がごみ箱の内容を保持する時間の長さを構成することができますが、ことのない場合は、既定の保存期間は、約 90 日です。サイトのごみ箱の記憶域は、サイト コレクションの記憶域のクォータと[リスト ビューのしきい値](https://support.office.com/article/List-View-Threshold-b8588dae-9387-48c2-9248-c24122f07c59)に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="91f8c-p102">When you delete content from a SharePoint Online site, it's not deleted immediately. It's sent to a Site Recycle Bin, where it can be restored, if needed. (See [Restore deleted items from the site collection recycle bin](https://support.office.com/article/Restore-deleted-items-from-the-site-collection-recycle-bin-5fa924ee-16d7-487b-9a0a-021b9062d14b) for restore steps.) The default Site Recycle Bin retention time is about 90 days. If you delete content from a Site Recycle Bin, it's sent to the Site Collection Recycle Bin, which has a retention time of 30 days. The length of time to keep things in the recycle bin can be configured by an administrator, but in the absence of that, the default retention period is about 90 days. The site recycle bin storage counts against site collection storage quota and the [List View Threshold](https://support.office.com/article/List-View-Threshold-b8588dae-9387-48c2-9248-c24122f07c59).</span></span>

<span data-ttu-id="91f8c-116">サイト コレクションを削除するときもすべてのコンテンツおよびユーザー情報を含む、コレクション内のサイトの階層を削除しています。</span><span class="sxs-lookup"><span data-stu-id="91f8c-116">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, including all content and user information:</span></span>
- <span data-ttu-id="91f8c-117">ドキュメントおよびドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="91f8c-117">Documents and document libraries</span></span>
- <span data-ttu-id="91f8c-118">リストとリスト データ</span><span class="sxs-lookup"><span data-stu-id="91f8c-118">Lists and list data</span></span>
- <span data-ttu-id="91f8c-119">サイト構成の設定</span><span class="sxs-lookup"><span data-stu-id="91f8c-119">Site configuration settings</span></span>
- <span data-ttu-id="91f8c-120">サイトまたはサブサイトに関連付けられているロールおよびセキュリティの情報</span><span class="sxs-lookup"><span data-stu-id="91f8c-120">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="91f8c-121">サブサイト最上位の web サイト、コンテンツ、およびユーザー情報の</span><span class="sxs-lookup"><span data-stu-id="91f8c-121">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="91f8c-p103">サイト コレクションを削除する前に、SharePoint のオンライン サービスの説明を確認する、計画では、SharePoint Online サイトはマイクロソフトが管理しているデータのバックアップ ・ スケジュールの概要を説明するをお勧めします。バックアップから復元できることを確認、専用のサイト コレクションまたはファイル、リスト、またはライブラリではなく、サブのサイトです。それらを回復する場合は、ごみ箱を使用します。</span><span class="sxs-lookup"><span data-stu-id="91f8c-p103">Before you delete a site collection, we recommend you review the SharePoint Online Service Description for your plan, which outlines the data backup schedule maintained by Microsoft for SharePoint Online sites. Also note that restorations from backups can are only for site collections or sub-sites, not for files, lists, or libraries. If you need to recover those, use the Recycle Bin.</span></span>

<span data-ttu-id="91f8c-p104">サイト コレクションを削除してしまった場合、復元できるサイト コレクションのごみ箱からサイト コレクションの管理者によって 30 日以内。30 日後に復元するサイト コレクションが必要な場合に復元できますマイクロソフト 30 日間有効期限からの 14 日以内、サービス ・ リクエストを使用してマイクロソフトに連絡しています。</span><span class="sxs-lookup"><span data-stu-id="91f8c-p104">If you accidentally delete a site collection, it can be restored from the Site Collection Recycle Bin by a Site Collection Administrator within 30 days. If you need a site collection restored after 30 days, it can be restored by Microsoft within 14 days from the 30-day expiration by contacting Microsoft via a Service Request.</span></span>

<span data-ttu-id="91f8c-p105">ハード削除は、ユーザーがサイトのごみ箱から削除されたアイテムを削除し、保存とバックアップの期間が期限切れ、または管理者が完全に[削除 SPODeletedSite コマンドレット](https://docs.microsoft.com/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)を使用してサイト コレクションを削除するときに発生します。ハードのユーザーを削除すると、完全に削除 (パージ) SharePoint Online のコンテンツの削除されたチャンクのすべての暗号化キーも削除されます。以前削除されたチャンクを格納するディスク上のブロックは、使用されていないために使用できる再使用としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="91f8c-p105">Hard deletion occurs when a user purges deleted items from the Site Recycle Bin, and the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](https://docs.microsoft.com/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted. The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
