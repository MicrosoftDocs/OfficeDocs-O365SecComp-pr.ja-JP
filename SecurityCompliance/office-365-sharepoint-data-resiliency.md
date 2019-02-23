---
title: Office 365 SharePoint データの復元
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Office 365 の SharePoint Online のデータ復元の概要について説明します。
ms.openlocfilehash: 4fd17b50551639f6e11975acbc3822fb6ffa8bb2
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214807"
---
# <a name="sharepoint-online-data-resiliency"></a><span data-ttu-id="9d44c-103">SharePoint Online データの復元</span><span class="sxs-lookup"><span data-stu-id="9d44c-103">SharePoint Online Data Resiliency</span></span>
<span data-ttu-id="9d44c-p101">SharePoint Online の主要な原則は、データの一部を1つのコピーで保持することではありません。SharePoint Online では、SQL Server レプリケーションを使用します。これは、データベース間でデータおよびデータベースオブジェクトをコピーして分散させるための一連のテクノロジで、一貫性を維持するためにデータベース間で同期します。</span><span class="sxs-lookup"><span data-stu-id="9d44c-p101">A key principle for SharePoint Online is to never have a single copy of any piece of data. SharePoint Online uses SQL Server replication, which is a set of technologies for copying and distributing data and database objects from one database to another, and then synchronizing between databases to maintain consistency.</span></span> 

<span data-ttu-id="9d44c-p102">たとえば、ユーザーが SharePoint Online にファイルを保存すると、ファイルがチャンクされ、暗号化されて、Azure Blob ストレージ内に格納されます。Azure Blob サービスは、アプリケーション層とトランスポート層の両方でデータの整合性を確保するメカニズムを提供します。この投稿では、サービスとクライアントの観点からこれらのメカニズムについて詳細に説明します。MD5 チェックは、PUT と GET の両方の操作ではオプションです。ただし、HTTP を使用する際にネットワーク全体でデータの整合性を確保するための便利な機能が提供されています。また、https がトランスポート層セキュリティを提供するため、https を使用して接続すると、余分な MD5 チェックは不要になります。Azure Blob サービスは永続的なストレージメディアを提供し、保存されたデータに対して独自の整合性チェックを使用します。アプリケーションと対話するときに使用される MD5's は、アプリケーションとサービス間で HTTP 経由でデータを転送するときに、データの整合性を確認するために提供されています。</span><span class="sxs-lookup"><span data-stu-id="9d44c-p102">For example, when a user saves a file in SharePoint Online, the file is chunked, encrypted, and stored within Azure Blob storage. Azure Blob service provides mechanisms to ensure data integrity both at the application and transport layers. This post will detail these mechanisms from the service and client perspective. MD5 checking is optional on both PUT and GET operations; however, it does provide a convenience facility to ensure data integrity across the network when using HTTP. Additionally, since HTTPS provides transport layer security additional MD5 checking is not needed while connecting over HTTPS as it would be redundant. Azure Blob service provides a durable storage medium, and uses its own integrity checking for stored data. The MD5's that are used when interacting with an application are provided for checking the integrity of the data when transferring that data between the application and service via HTTP.</span></span> 

<span data-ttu-id="9d44c-p103">データの整合性を確保するために、Azure Blob サービスはさまざまな方法でデータの MD5 ハッシュを使用します。これらの値がどのように計算、転送、保存され、最終的に、それらの値を使用してデータの整合性を提供するようにアプリケーションを設計することが重要であることを理解することが重要です。詳細については、「 [Windows Azure Blob MD5 の概要](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d44c-p103">To ensure data integrity the Azure Blob service uses MD5 hashes of the data in a couple different manners. It is important to understand how these values are calculated, transmitted, stored, and eventually enforced to appropriately design your application to utilize them to provide data integrity. For more information, see [Windows Azure Blob MD5 Overview](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx).</span></span> 

<span data-ttu-id="9d44c-p104">ファイルへのメタデータとポインターは、SQL Server データベース (コンテンツデータベース) に格納されます。すべてのチャンク–ファイル、ファイル、および更新のデルタは、複数の azure ストレージアカウント間でランダムに分散される azure ストレージに blob として格納されます。SQL データベースは raid 10 ストレージアレイ上でホストされており、同じデータセンター内の別のラックにある別の raid 10 ストレージアレイに同期ミラーリングされます。次に、非同期ログ配布を使用して、第2データセンター内の別の RAID 10 ストレージアレイにデータをレプリケートします。RAID 10 および同期および非同期レプリケーションを使用してデータを保護することに加えて、2番目のデータセンターに非同期的にレプリケートされるスケジュールされたデータバックアップも行われます。</span><span class="sxs-lookup"><span data-stu-id="9d44c-p104">Metadata and pointers to the file are stored in a SQL Server database (the content database). All the chunks – files, pieces of files, and update deltas – are stored as blobs in Azure storage that are randomly distributed across multiple Azure storage accounts. The SQL database is hosted on a RAID 10 storage array which is synchronously mirrored to another RAID 10 storage array in a separate rack within the same datacenter. Asynchronous log shipping is then used to replicate the data to another RAID 10 storage array in a second datacenter. In addition to protecting data with RAID 10 and synchronous and asynchronous replication, scheduled data backups are taken which are also asynchronously replicated to the second datacenter.</span></span> 

<span data-ttu-id="9d44c-p105">SharePoint Online では、データバックアップは12時間ごとに実行され、14日間保持されます。SharePoint Online では、同一の顧客データの場所 (米国でのテナントを準備しているお客様のために、シカゴおよび San Antonio など) 内に、地理的に独立した複数のデータセンターを含むホットスタンバイシステムも使用します。アクティブ/アクティブとして構成されます。たとえば、プライマリデータセンターとしてシカゴを持つ live ユーザーと、フェールオーバーデータセンターとして、san Antonio がプライマリデータセンターとして存在する live ユーザーと、フェールオーバーデータセンターとしての Antonio があります。</span><span class="sxs-lookup"><span data-stu-id="9d44c-p105">In SharePoint Online, data backups are performed every 12 hours and retained for 14 days. SharePoint Online also uses a hot standby system that includes paired geographically-separate datacenters within the same customer data location region (for example, Chicago and San Antonio for customers who have provisioned their tenant in the United States) configured as active/active. For example, there are live users that have Chicago as their primary datacenter and San Antonio as a failover datacenter, and live users that have San Antonio as their primary datacenter and Chicago as their failover datacenter.</span></span> 