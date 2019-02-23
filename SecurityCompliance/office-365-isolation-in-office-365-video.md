---
title: office 365 のテナント分離 (office 365)
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
description: '概要: Office 365 Video でのテナントの分離について説明します。'
ms.openlocfilehash: ffdc87c0a5e63336552268dafab1293699f262ba
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220117"
---
# <a name="tenant-isolation-in-office-365-video"></a><span data-ttu-id="eb8de-103">Office 365 でのテナントの分離のビデオ</span><span class="sxs-lookup"><span data-stu-id="eb8de-103">Tenant Isolation in Office 365 Video</span></span>

> [!NOTE]
> <span data-ttu-id="eb8de-p101">Office 365 のビデオは、Microsoft Stream に置き換えられます。ビデオコラボレーションにインテリジェンスを追加する新しいエンタープライズビデオサービスの詳細と、現在の office 365 ビデオのお客様の移行計画については、「 [office 365 からストリームへの移行](https://docs.microsoft.com/stream/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb8de-p101">Office 365 Video will be replaced by Microsoft Stream. To learn more about the new enterprise video service that adds intelligence to video collaboration and learn about the transition plans for current Office 365 Video customers, see [Migrate to Stream from Office 365 Video](https://docs.microsoft.com/stream/).</span></span>

## <a name="introduction"></a><span data-ttu-id="eb8de-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="eb8de-106">Introduction</span></span>
<span data-ttu-id="eb8de-p102">Azure Storage は、office 365 ビデオおよび Sway を含む複数の office 365 サービスのデータを格納するために使用されます。Azure ストレージには、構造化されていないデータを格納するために使用される拡張性の高い REST ベースのクラウドオブジェクトストアである Blob ストレージが含まれています。Azure ストレージは、シンプルなアクセス制御モデルを使用します。各 Azure サブスクリプションは、1つ以上のストレージアカウントを作成できます。各ストレージアカウントには、そのストレージアカウントのすべてのデータへのアクセスを制御するために使用される単一のシークレットキーがあります。これは、ストレージがアプリケーションに関連付けられており、それらのアプリケーションが関連するデータを完全に制御する一般的なシナリオをサポートします。たとえば、Sway は Azure ストレージにコンテンツを格納します。Sway のすべての顧客コンテンツは、共有の Azure ストレージアカウントに保存されます。各ユーザーのコンテンツは、Azure ストレージ内の blob の独立したディレクトリツリーにあります。</span><span class="sxs-lookup"><span data-stu-id="eb8de-p102">Azure Storage is used to store data for multiple Office 365 services, including Office 365 Video and Sway. Azure Storage includes Blob storage, which is a highly-scalable, REST-based, cloud object store that is used for storing unstructured data. Azure Storage uses a simple access control model; each Azure subscription can create one or more Storage Accounts. Each Storage Account has a single secret key that is used to control access to all data in that Storage Account. This supports the typical scenario where storage is associated with applications and those applications have full control over their associated data; for example, Sway storing content in Azure Storage. All customer content for Sway is stored in shared Azure storage accounts. Each user's content is in a separate directory tree of blobs in Azure storage.</span></span>

<span data-ttu-id="eb8de-p103">お客様の環境へのアクセスを管理するシステム (たとえば、azure Portal、SMAPI など) は、Microsoft が運用している azure アプリケーション内で分離されています。これにより、顧客のアクセスインフラストラクチャが顧客アプリケーションとストレージ層から論理的に分離されます。</span><span class="sxs-lookup"><span data-stu-id="eb8de-p103">The systems managing access to customer environments (e.g., the Azure Portal, SMAPI, etc.) are isolated within an Azure application operated by Microsoft. This logically separates the customer access infrastructure from the customer applications and storage layer.</span></span>

## <a name="tenant-isolation-in-office-365-video"></a><span data-ttu-id="eb8de-116">Office 365 でのテナントの分離のビデオ</span><span class="sxs-lookup"><span data-stu-id="eb8de-116">Tenant Isolation in Office 365 Video</span></span>
<span data-ttu-id="eb8de-p104">[Office 365 video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)は、企業に対して、セキュリティで保護された、組織全体で、ビデオコンテンツを投稿、共有、および検出するための、高度にセキュリティで保護された場所を提供するエンタープライズポータルです。Office 365 のビデオでは、各テナントのビデオはすべての場所で分離され、暗号化されています。また、組織のビデオに対するアクセス許可とアクセス許可を持つ認証されたユーザーのみが使用できます。Office 365 Video は、次のようなテクノロジを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="eb8de-p104">[Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) is an enterprise portal that provides organizations with a highly secure, organization-wide destination for posting, sharing, and discovering video content. In Office 365 Video, each tenant's videos are kept isolated and encrypted in all locations, and are only available to authenticated users that have access and permissions to the organization's videos. Office 365 Video uses a combination of technologies to accomplish this:</span></span>
- <span data-ttu-id="eb8de-p105">SharePoint Online は、ビデオファイルとメタデータ (ビデオタイトル、説明など) を格納するために使用されます。また、セキュリティおよびコンプライアンス層 (認証を含む) と検索機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="eb8de-p105">SharePoint Online is used for storing the video file and metadata (video title, description, etc.). It also provides the security and compliance layer (including authentication), and search features.</span></span>
- <span data-ttu-id="eb8de-122">Azure Media Services では、トランスコーディング、アダプティブストリーミング、セキュリティで保護された配信 (AES 暗号化を使用)、およびサムネイル機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="eb8de-122">Azure Media Services provides transcoding, adaptive streaming, secure delivery (using AES encryption), and thumbnail features.</span></span>

<span data-ttu-id="eb8de-p106">[Azure media Services](https://azure.microsoft.com/services/media-services/)は、クラウドでエンドツーエンドのメディアワークフローを有効にするためのサービスとしてのプラットフォームです。プラットフォームは、アップロード、エンコード、暗号化 (PlayReady を使用)、および世界中の Azure データセンターを使用したメディアの配信用の REST API を提供します。</span><span class="sxs-lookup"><span data-stu-id="eb8de-p106">[Azure Media Services](https://azure.microsoft.com/services/media-services/) is a platform-as-a-service offering for enabling end-to-end media workflows in the cloud. The platform provides a REST API for uploading, encoding, encrypting (with PlayReady), and delivery of media through Azure datacenters around the world.</span></span>

<span data-ttu-id="eb8de-p107">Office 365 ビデオのすべてのアップロードは HTTPS 経由で行われます。ビデオファイルがアップロードされると、SharePoint Online に格納され、ファイルのコピーが暗号化されたチャネルを介して Azure メディアサービスに送信されます。Azure Media Services は、ビデオをコード変換の表示用に最適化された複数の形式 (モバイル、低帯域幅、高帯域幅など) に変換します。これらのファイルは、アップロード中に取得した元のファイルと共に、Azure Blob ストレージに格納されます。これらのファイルは、再生用の MPEG 共通暗号化パッケージアルゴリズム (または以前の PlayReady バージョン) ごとに aes 128 を使用して暗号化され、Azure Blob ストレージに保存される前に aes 256 ストレージ暗号化を使用して暗号化されます。(Azure Media Services クライアント SDK を使用して、お客様はどの暗号化を使用するかを制御できます。たとえば、azure Blob ストレージをアップロードする前に、お客様は azure メディアサービスストレージ暗号化 (AES 256) を高価値メディアアセットに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="eb8de-p107">All uploads for Office 365 Video occur via HTTPS. When a video file is uploaded, it is stored in SharePoint Online, and a copy of the file is sent via an encrypted channel to Azure Media Services. Azure Media Services transcodes the video into multiple formats that are optimized for viewing experience (e.g., mobile, low-bandwidth, high-bandwidth, etc.). These files, along with the original file acquired during upload, are stored in Azure Blob storage. The files are encrypted using AES 128 per the MPEG Common Encryption packaging algorithm (or an earlier PlayReady version) for playback, and encrypted using AES 256 storage encryption before being stored in Azure Blob storage. (Using the Azure Media Services Client SDK, customers can control which encryption is used. For example, a customer could apply Azure Media Services storage encryption (AES 256) to a high-value media asset before uploading it Azure Blob storage.)</span></span>

<span data-ttu-id="eb8de-132">また、Azure Media Services はビデオのサムネイルを生成し、暗号化されたチャネルを介して SharePoint Online にサムネイルメタデータと共に送信します。</span><span class="sxs-lookup"><span data-stu-id="eb8de-132">Azure Media Services also generates a thumbnail for the video, which it transmits along with thumbnail metadata to SharePoint Online via an encrypted channel.</span></span>
