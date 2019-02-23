---
title: OneDrive for Business および SharePoint Online におけるデータ暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
description: OneDrive for Business および SharePoint Online におけるデータ セキュリティの暗号化の基本要素について理解を深めます。
ms.openlocfilehash: a43db3da6e4663aee4437689ff51276972298872
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223216"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>OneDrive for Business および SharePoint Online におけるデータ暗号化

OneDrive for Business および SharePoint Online におけるデータ セキュリティの暗号化の基本要素について理解を深めます。
  
## <a name="overview"></a>概要

Office 365 は、物理的なデータ センター セキュリティ、ネットワーク セキュリティ、アクセス セキュリティ、アプリケーション セキュリティ、データ セキュリティといった多層にわたって拡張保護が提供されるセキュリティの高い環境です。この記事では特に、OneDrive for Business および SharePoint Online におけるデータ セキュリティの転送中の暗号化と保管中の暗号化に注目します。
  
office 365 のセキュリティの詳細については、「 [security in office 365 ホワイトペーパー](https://go.microsoft.com/fwlink/p/?LinkId=270895)」を参照してください。
  
データの暗号化の仕組みについて、次のビデオをご覧ください。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>転送中データの暗号化

OneDrive for Business および SharePoint Online では、データを入力し、データセンターを終了する 2 つのシナリオがあります。
  
- **サーバーとのクライアント通信**OneDrive for Business とインターネットを介して通信する場合、SSL/TLS 接続を使用します。すべての SSL 接続は 2048 ビット キーを使用して確立されます。 
    
- **データセンター間でのデータの移動** データセンター間でデータを移動させる主な理由は、geo レプリケーションで障害復旧を有効にするためです。たとえば、SQL Server トランザクション ログおよび Blob ストレージの差分はこのパイプで移動します。このデータは既にプライベート ネットワークにより送信されていますが、クラス最高の暗号化を使用してさらに保護されます。 
    
## <a name="encryption-of-data-at-rest"></a>保管中データの暗号化

保管中の暗号化には、ユーザー コンテンツの BitLocker ディスク レベル暗号化と、ファイル単位暗号化が関係しています。
  
BitLocker は、OneDrive for business と SharePoint Online のサービス全体に展開されます。ファイル単位の暗号化は、OneDrive for business と SharePoint Online の Office 365 マルチテナントと、マルチテナントテクノロジに基づいて構築された新しい専用環境にも含まれています。
  
BitLocker 暗号化はディスク上のすべてのデータを暗号化し、ファイル単位暗号化の場合にはファイルごとに固有の暗号化キーを含めてさらに細かく暗号化を行えます。つまり、各ファイルを更新するたびに独自の暗号化キーを使用して暗号化されます。暗号化されたコンテンツに対するキーは、コンテンツとは物理的に別の場所に格納されます。この暗号化の各ステップでは、256 ビット キーによる高度暗号化標準 (Advanced Encryption Standard: AES) が使用され、Federal Information Processing Standard (FIPS) 140-2 に準拠しています。暗号化されたコンテンツは、データセンターにある多数のコンテナーに配布され、各コンテナーでは固有の資格情報が使用されます。これらの資格情報はコンテンツまたはコンテンツ キーとは物理的に別の場所に格納されます。
  
fips 140-2 準拠の詳細については、「 [fips 140-2 コンプライアンス](https://go.microsoft.com/fwlink/?LinkId=517625)」を参照してください。
  
rest でのファイルレベルの暗号化は、blob ストレージを活用して、事実上無制限の記憶域の拡大を実現し、前例のない保護を可能にします。OneDrive for business および SharePoint online のお客様のコンテンツはすべて blob ストレージに移行されます。データのセキュリティ保護の方法は次のとおりです。
  
1. すべてのコンテンツが暗号化されます。その場合、複数のキーを使用して暗号化されることもあります。暗号化されたデータはデータセンターで分散されます。格納される各ファイルはサイズに応じて 1 つ以上のチャンクに分けられます。その後、各チャンクは固有のキーを使用して暗号化されます。更新作業も同様に処理されます。つまり、ユーザーによって送信された一連の変更または差分がチャンクに分けられ、それぞれが独自のキーで暗号化されます。
    
2. これらのチャンク ファイル、ファイル セット、更新差分すべては Blob ストア内で Blob として格納されます。これらのファイルはまた、複数の Blob コンテナーでランダムに分散されます。
    
3. コンポーネントからファイルを再構築するために使用される "マップ" は、コンテンツ データベースに保管されています。
    
4. それぞれの Blob コンテナーには、アクセスの種類 (読み取り、書き込み、列挙、削除) ごとに独自の資格情報があります。各資格情報セットはセキュリティが確保されたキー ストアで保管され、定期的に更新されます。
    
つまり、ファイル単位の保管中の暗号化には以下のように 3 つの異なる種類のストアがあり、それぞれ別の機能を持っています。
  
- Blob ストアには、コンテンツが暗号化 Blob として格納されます。コンテンツの各チャンクのキーが暗号化されて、コンテンツ データベースに別個に格納されます。コンテンツ自体は、暗号化解除方法に関する糸口を含めずに保持されます。
    
- コンテンツ データベースは SQL Server データベースです。Blob ストアに保管されているコンテンツ Blob すべてを見つけて再構築するために必要なマップと、それらの Blob を暗号化解除するために必要なキーが一緒に保管されます。
    
これら 3 つのコンポーネント (Blob ストア、コンテンツ データベース、キー ストア) はそれぞれ物理的に別の場所にあります。いずれかのコンポーネントに保管されている情報は、それ自体では使用できません。それにより、これまでにないレベルのセキュリティが実現します。これら 3 つのすべてのコンポーネントにアクセスしない限りは、チャンクのカギを取得すること、キーを暗号化解除して使用できるようにすること、キーと対応するチャンクを関連付けること、チャンクを暗号化解除すること、構成チャンクからドキュメントを再構築することはいずれも不可能です。
  

