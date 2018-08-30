---
title: Office 365 のビデオでは、office 365 テナント分離
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
description: '概要: Office 365 のビデオでは、テナントの分離の説明。'
ms.openlocfilehash: 9476047d56161ec2589fdf743d7ee837ea558865
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532413"
---
# <a name="tenant-isolation-in-office-365-video"></a><span data-ttu-id="2b9a2-103">Office 365 でのテナントの分離のビデオ</span><span class="sxs-lookup"><span data-stu-id="2b9a2-103">Tenant Isolation in Office 365 Video</span></span>

> [!NOTE]
> <span data-ttu-id="2b9a2-p101">Microsoft ストリームでは、office 365 のビデオが置き換えられます。ビデオ コラボレーションにインテリジェンスを付加し、Office 365 のビデオの現在の顧客の移行の計画について説明する新しいエンタープライズ ビデオ サービスに関する詳細については、 [Office 365 のビデオのストリームへ移行する](https://docs.microsoft.com/stream/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b9a2-p101">Office 365 Video will be replaced by Microsoft Stream. To learn more about the new enterprise video service that adds intelligence to video collaboration and learn about the transition plans for current Office 365 Video customers, see [Migrate to Stream from Office 365 Video](https://docs.microsoft.com/stream/).</span></span>

## <a name="introduction"></a><span data-ttu-id="2b9a2-106">概要</span><span class="sxs-lookup"><span data-stu-id="2b9a2-106">Introduction</span></span>
<span data-ttu-id="2b9a2-p102">Azure ストレージを使用して、Office 365 のビデオおよび影響を与えるなど、複数の Office 365 サービスのデータを格納します。Azure ストレージには、非構造化データを格納するために使用される拡張性の高い、REST ベースのクラウド オブジェクト ストアは、Blob の記憶域が含まれています。Azure ストレージを使用して、単純なアクセス制御モデルです。Azure サブスクリプションごとに 1 つまたは複数のストレージ アカウントを作成できます。各ストレージ アカウントは、そのストレージ アカウントのすべてのデータへのアクセスを制御するために使用される単一の秘密キーを持ちます。ストレージ ・ アプリケーションに関連付けられているあり、それらのアプリケーションが、関連付けられたデータを完全に制御をある一般的なシナリオをサポートしていますたとえば、Azure ストレージにファイルを格納するコンテンツをかきたてます。影響を与えるのすべての顧客のコンテンツは、共有の Azure ストレージ アカウントに格納されます。Azure ストレージの blob の別のディレクトリ ツリーでは、各ユーザーのコンテンツです。</span><span class="sxs-lookup"><span data-stu-id="2b9a2-p102">Azure Storage is used to store data for multiple Office 365 services, including Office 365 Video and Sway. Azure Storage includes Blob storage, which is a highly-scalable, REST-based, cloud object store that is used for storing unstructured data. Azure Storage uses a simple access control model; each Azure subscription can create one or more Storage Accounts. Each Storage Account has a single secret key that is used to control access to all data in that Storage Account. This supports the typical scenario where storage is associated with applications and those applications have full control over their associated data; for example, Sway storing content in Azure Storage. All customer content for Sway is stored in shared Azure storage accounts. Each user's content is in a separate directory tree of blobs in Azure storage.</span></span>

<span data-ttu-id="2b9a2-p103">お客様の環境 (例えば、Azure ポータル、SMAPI など) へのアクセスを管理するシステムでは、マイクロソフトによって運営されて、Azure アプリケーション内で分離されています。これは、論理的に、お客様のアプリケーションとストレージ ・ レイヤーから顧客のアクセスのインフラストラクチャを分離します。</span><span class="sxs-lookup"><span data-stu-id="2b9a2-p103">The systems managing access to customer environments (e.g., the Azure Portal, SMAPI, etc.) are isolated within an Azure application operated by Microsoft. This logically separates the customer access infrastructure from the customer applications and storage layer.</span></span>

## <a name="tenant-isolation-in-office-365-video"></a><span data-ttu-id="2b9a2-116">Office 365 でのテナントの分離のビデオ</span><span class="sxs-lookup"><span data-stu-id="2b9a2-116">Tenant Isolation in Office 365 Video</span></span>
<span data-ttu-id="2b9a2-p104">[Office 365 のビデオ](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)は、投稿、共有、およびビデオ コンテンツを検出するため、組織全体の安全性の高いターゲットを持つ組織を提供するエンタープライズ ・ ポータルです。Office 365 のビデオでは各テナントのビデオに維持されます分離され、暗号化されたですべての場所でのみ使用可能なアクセスと組織のビデオへのアクセス許可を持つ認証されたユーザー。Office 365 のビデオでは、これを実現するのにテクノロジの組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="2b9a2-p104">[Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) is an enterprise portal that provides organizations with a highly secure, organization-wide destination for posting, sharing, and discovering video content. In Office 365 Video, each tenant's videos are kept isolated and encrypted in all locations, and are only available to authenticated users that have access and permissions to the organization's videos. Office 365 Video uses a combination of technologies to accomplish this:</span></span>
- <span data-ttu-id="2b9a2-p105">SharePoint Online は、ビデオ ファイルとメタデータ (ビデオのタイトル、説明など) を格納するため使用されます。セキュリティとコンプライアンスの層を (認証など)、また、検索機能とします。</span><span class="sxs-lookup"><span data-stu-id="2b9a2-p105">SharePoint Online is used for storing the video file and metadata (video title, description, etc.). It also provides the security and compliance layer (including authentication), and search features.</span></span>
- <span data-ttu-id="2b9a2-122">Azure のメディア サービスでは、トランス コード、アダプティブ ストリーミング、セキュリティで保護された配信 (AES 暗号化を使用して)、およびサムネイル機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="2b9a2-122">Azure Media Services provides transcoding, adaptive streaming, secure delivery (using AES encryption), and thumbnail features.</span></span>

<span data-ttu-id="2b9a2-p106">[Azure のメディア サービス](https://azure.microsoft.com/services/media-services/)では、プラットフォームとしてのサービス、クラウドでのエンド ・ ツー ・ エンドのメディア ・ ワークフローを有効にするために提供します。プラットフォームでは、アップロード、エンコーディング、(PlayReady) を使用して暗号化および世界中の Azure データ センターでメディアの配信の REST API を提供します。</span><span class="sxs-lookup"><span data-stu-id="2b9a2-p106">[Azure Media Services](https://azure.microsoft.com/services/media-services/) is a platform-as-a-service offering for enabling end-to-end media workflows in the cloud. The platform provides a REST API for uploading, encoding, encrypting (with PlayReady), and delivery of media through Azure datacenters around the world.</span></span>

<span data-ttu-id="2b9a2-p107">Office 365 のビデオのすべてのアップロードは、HTTPS 経由で発生します。ビデオ ファイルがアップロードされると、SharePoint Online に格納されていると、Azure のメディア サービスに暗号化されたチャネル経由でファイルのコピーが送信されます。Azure メディア サービスのトランス コード ビデオ エクスペリエンス (例えば、モバイル、低帯域幅の高帯域幅など) を表示するために最適化された複数のフォーマットに変換します。元のファイルのアップロード時に取得されると、これらのファイルは、Azure のブロブ ストレージに格納されます。ファイルは、AES 128 を使用してパッケージ化する MPEG の一般的な暗号化アルゴリズム (または PlayReady の以前のバージョン) の再生、ごと暗号化され、Azure のブロブ ストレージに保存される前にストレージの暗号化を AES の 256 を使用して暗号化します。(Azure のメディア サービスのクライアント SDK を使用して、顧客を制御できますどの暗号化方式を使用します。たとえば、顧客適用メディア サービスの Azure ストレージの暗号化 (AES 256) 価値の高いメディア資産に Azure Blob ストレージにアップロードする前に。)</span><span class="sxs-lookup"><span data-stu-id="2b9a2-p107">All uploads for Office 365 Video occur via HTTPS. When a video file is uploaded, it is stored in SharePoint Online, and a copy of the file is sent via an encrypted channel to Azure Media Services. Azure Media Services transcodes the video into multiple formats that are optimized for viewing experience (e.g., mobile, low-bandwidth, high-bandwidth, etc.). These files, along with the original file acquired during upload, are stored in Azure Blob storage. The files are encrypted using AES 128 per the MPEG Common Encryption packaging algorithm (or an earlier PlayReady version) for playback, and encrypted using AES 256 storage encryption before being stored in Azure Blob storage. (Using the Azure Media Services Client SDK, customers can control which encryption is used. For example, a customer could apply Azure Media Services storage encryption (AES 256) to a high-value media asset before uploading it Azure Blob storage.)</span></span>

<span data-ttu-id="2b9a2-132">Azure のメディア サービスには、SharePoint Online に暗号化されたチャネル経由での縮小表示のメタデータと共に送信すると、ビデオのサムネイルも生成されます。</span><span class="sxs-lookup"><span data-stu-id="2b9a2-132">Azure Media Services also generates a thumbnail for the video, which it transmits along with thumbnail metadata to SharePoint Online via an encrypted channel.</span></span>
