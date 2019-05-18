---
title: OneDrive for Business および SharePoint Online におけるデータ暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
description: OneDrive for Business および SharePoint Online におけるデータセキュリティの暗号化の基本要素について説明します。
ms.openlocfilehash: c8ac6f0a4364117c475637e0288d7a1a790d57c2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151099"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a><span data-ttu-id="5705e-103">OneDrive for Business および SharePoint Online におけるデータ暗号化</span><span class="sxs-lookup"><span data-stu-id="5705e-103">Data Encryption in OneDrive for Business and SharePoint Online</span></span>

<span data-ttu-id="5705e-104">OneDrive for Business および SharePoint Online におけるデータセキュリティの暗号化の基本要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5705e-104">Understand the basic elements of encryption for data security in OneDrive for Business and SharePoint Online.</span></span>
  
## <a name="overview"></a><span data-ttu-id="5705e-105">概要</span><span class="sxs-lookup"><span data-stu-id="5705e-105">Overview</span></span>

<span data-ttu-id="5705e-106">Office 365 は、高度なセキュリティで保護された環境で、物理データセンターのセキュリティ、ネットワークセキュリティ、アクセスセキュリティ、アプリケーションセキュリティ、およびデータセキュリティがあります。</span><span class="sxs-lookup"><span data-stu-id="5705e-106">Office 365 is a highly secure environment that offers extensive protection in multiple layers: physical data center security, network security, access security, application security, and data security.</span></span> <span data-ttu-id="5705e-107">この記事では特に、OneDrive for Business および SharePoint Online のデータセキュリティの、送信中およびインプレース暗号化側に焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="5705e-107">This article specifically focuses on the in-transit and at-rest encryption side of data security for OneDrive for Business and SharePoint Online.</span></span>
  
<span data-ttu-id="5705e-108">Office 365 のセキュリティの詳細については、「 [security In office 365 ホワイトペーパー](https://go.microsoft.com/fwlink/p/?LinkId=270895)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5705e-108">For a description of Office 365 security as a whole, see [Security in Office 365 White Paper](https://go.microsoft.com/fwlink/p/?LinkId=270895).</span></span>
  
<span data-ttu-id="5705e-109">データの暗号化の仕組みについて、次のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5705e-109">Watch how data encryption works in the following video.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a><span data-ttu-id="5705e-110">転送中データの暗号化</span><span class="sxs-lookup"><span data-stu-id="5705e-110">Encryption of data in transit</span></span>

<span data-ttu-id="5705e-111">OneDrive for Business と SharePoint Online では、データを入力してデータセンターを終了する2つのシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="5705e-111">In OneDrive for Business and SharePoint Online, there are two scenarios in which data enters and exits the datacenters.</span></span>
  
- <span data-ttu-id="5705e-112">**クライアントとサーバーとの通信**インターネット経由での OneDrive for business への通信では、SSL/TLS 接続が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5705e-112">**Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections.</span></span> <span data-ttu-id="5705e-113">すべての SSL 接続は、2048ビットのキーを使用して確立されます。</span><span class="sxs-lookup"><span data-stu-id="5705e-113">All SSL connections are established using 2048-bit keys.</span></span>

- <span data-ttu-id="5705e-114">**データセンター間のデータ移動**データセンター間でデータを移動する主な理由は、geo レプリケーションを使用して障害復旧を可能にすることです。</span><span class="sxs-lookup"><span data-stu-id="5705e-114">**Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery.</span></span> <span data-ttu-id="5705e-115">たとえば、SQL Server のトランザクションログと blob ストレージのデルタは、このパイプに沿って移動します。</span><span class="sxs-lookup"><span data-stu-id="5705e-115">For instance, SQL Server transaction logs and blob storage deltas travel along this pipe.</span></span> <span data-ttu-id="5705e-116">このデータは、プライベートネットワークを使用して既に送信されていますが、クラス最高の暗号化を使用してさらに保護されています。</span><span class="sxs-lookup"><span data-stu-id="5705e-116">While this data is already transmitted by using a private network, it is further protected with best-in-class encryption.</span></span> 

## <a name="encryption-of-data-at-rest"></a><span data-ttu-id="5705e-117">保管中データの暗号化</span><span class="sxs-lookup"><span data-stu-id="5705e-117">Encryption of data at rest</span></span>

<span data-ttu-id="5705e-118">保管中の暗号化には、ユーザー コンテンツの BitLocker ディスク レベル暗号化と、ファイル単位暗号化が関係しています。</span><span class="sxs-lookup"><span data-stu-id="5705e-118">Encryption at rest includes two components: BitLocker disk-level encryption and per-file encryption of customer content.</span></span>
  
<span data-ttu-id="5705e-119">BitLocker は、OneDrive for business と SharePoint Online のサービス全体に展開されます。</span><span class="sxs-lookup"><span data-stu-id="5705e-119">BitLocker is deployed for OneDrive for Business and SharePoint Online across the service.</span></span> <span data-ttu-id="5705e-120">ファイル単位の暗号化は、OneDrive for Business と SharePoint Online の Office 365 マルチテナントと、マルチテナントテクノロジに基づいて構築された新しい専用環境にも含まれています。</span><span class="sxs-lookup"><span data-stu-id="5705e-120">Per-file encryption is also in OneDrive for Business and SharePoint Online in Office 365 multi-tenant and new dedicated environments that are built on multi-tenant technology.</span></span>
  
<span data-ttu-id="5705e-121">BitLocker 暗号化はディスク上のすべてのデータを暗号化し、ファイル単位暗号化の場合にはファイルごとに固有の暗号化キーを含めてさらに細かく暗号化を行えます。</span><span class="sxs-lookup"><span data-stu-id="5705e-121">While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file.</span></span> <span data-ttu-id="5705e-122">つまり、各ファイルを更新するたびに独自の暗号化キーを使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="5705e-122">Further, every update to every file is encrypted using its own encryption key.</span></span> <span data-ttu-id="5705e-123">保存される前に、暗号化されたコンテンツに対するキーがコンテンツとは物理的に離れた場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="5705e-123">Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content.</span></span> <span data-ttu-id="5705e-124">この暗号化の各ステップでは、256 ビット キーによる高度暗号化標準 (Advanced Encryption Standard: AES) が使用され、Federal Information Processing Standard (FIPS) 140-2 に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="5705e-124">Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant.</span></span> <span data-ttu-id="5705e-125">暗号化されたコンテンツは、データセンターにある多数のコンテナーに配布され、各コンテナーでは固有の資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5705e-125">The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials.</span></span> <span data-ttu-id="5705e-126">これらの資格情報はコンテンツまたはコンテンツ キーとは物理的に別の場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="5705e-126">These credentials are stored in a separate physical location from either the content or the content keys.</span></span>
  
<span data-ttu-id="5705e-127">FIPS 140-2 準拠の詳細については、「 [fips 140-2 コンプライアンス](https://go.microsoft.com/fwlink/?LinkId=517625)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5705e-127">For additional information about FIPS 140-2 compliance, see [FIPS 140-2 Compliance](https://go.microsoft.com/fwlink/?LinkId=517625).</span></span>
  
<span data-ttu-id="5705e-128">ファイル レベルでの保管中の暗号化では Blob ストレージを活用し、事実上無制限のストレージ拡張を行ったり、前例のないレベルの保護機能を提供したりできます。</span><span class="sxs-lookup"><span data-stu-id="5705e-128">File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection.</span></span> <span data-ttu-id="5705e-129">OneDrive for Business と SharePoint Online のすべてのお客様のコンテンツは blob ストレージに移行されます。</span><span class="sxs-lookup"><span data-stu-id="5705e-129">All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage.</span></span> <span data-ttu-id="5705e-130">データのセキュリティ保護の方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5705e-130">Here's how that data is secured:</span></span>
  
1. <span data-ttu-id="5705e-p107">すべてのコンテンツが暗号化されます。その場合、複数のキーを使用して暗号化されることもあります。暗号化されたデータはデータセンターで分散されます。格納される各ファイルはサイズに応じて 1 つ以上のチャンクに分けられます。その後、各チャンクは固有のキーを使用して暗号化されます。更新作業も同様に処理されます。つまり、ユーザーによって送信された一連の変更または差分がチャンクに分けられ、それぞれが独自のキーで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="5705e-p107">All content is encrypted, potentially with multiple keys, and distributed across the datacenter. Each file to be stored is broken into one or more chunks, depending its size. Then, each chunk is encrypted using its own unique key. Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.</span></span>

2. <span data-ttu-id="5705e-p108">これらのチャンク ファイル、ファイル セット、更新差分すべては Blob ストア内で Blob として格納されます。これらのファイルはまた、複数の Blob コンテナーでランダムに分散されます。</span><span class="sxs-lookup"><span data-stu-id="5705e-p108">All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store. They also are randomly distributed across multiple blob containers.</span></span>

3. <span data-ttu-id="5705e-137">コンポーネントからファイルを再構築するために使用される "マップ" は、コンテンツデータベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5705e-137">The "map" used to re-assemble the file from its components is stored in the Content Database.</span></span>

4. <span data-ttu-id="5705e-p109">それぞれの Blob コンテナーには、アクセスの種類 (読み取り、書き込み、列挙、削除) ごとに独自の資格情報があります。各資格情報セットはセキュリティが確保されたキー ストアで保管され、定期的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="5705e-p109">Each blob container has its own unique credentials per access type (read, write, enumerate, and delete). Each set of credentials is held in the secure Key Store and is regularly refreshed.</span></span>

<span data-ttu-id="5705e-140">つまり、ファイル単位の保管中の暗号化には以下のように 3 つの異なる種類のストアがあり、それぞれ別の機能を持っています。</span><span class="sxs-lookup"><span data-stu-id="5705e-140">In other words, there are three different types of stores involved in per-file encryption at rest, each with a distinct function:</span></span>
  
- <span data-ttu-id="5705e-p110">Blob ストアには、コンテンツが暗号化 Blob として格納されます。コンテンツの各チャンクのキーが暗号化されて、コンテンツ データベースに別個に格納されます。コンテンツ自体は、暗号化解除方法に関する糸口を含めずに保持されます。</span><span class="sxs-lookup"><span data-stu-id="5705e-p110">Content is stored as encrypted blobs in the blob store. The key to each chunk of content is encrypted and stored separately in the content database. The content itself holds no clue as to how it can be decrypted.</span></span>

- <span data-ttu-id="5705e-144">コンテンツデータベースは SQL Server データベースです。</span><span class="sxs-lookup"><span data-stu-id="5705e-144">The Content Database is a SQL Server database.</span></span> <span data-ttu-id="5705e-145">Blob ストアに保管されているコンテンツ Blob すべてを見つけて再構築するために必要なマップと、それらの Blob を暗号化解除するために必要なキーが一緒に保管されます。</span><span class="sxs-lookup"><span data-stu-id="5705e-145">It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.</span></span>

<span data-ttu-id="5705e-p112">これら 3 つのコンポーネント (Blob ストア、コンテンツ データベース、キー ストア) はそれぞれ物理的に別の場所にあります。いずれかのコンポーネントに保管されている情報は、それ自体では使用できません。それにより、これまでにないレベルのセキュリティが実現します。これら 3 つのすべてのコンポーネントにアクセスしない限りは、チャンクのカギを取得すること、キーを暗号化解除して使用できるようにすること、キーと対応するチャンクを関連付けること、チャンクを暗号化解除すること、構成チャンクからドキュメントを再構築することはいずれも不可能です。</span><span class="sxs-lookup"><span data-stu-id="5705e-p112">Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate. The information held in any one of the components is unusable on its own. This provides an unprecedented level of security. Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.</span></span>