---
title: Office 365 の SharePoint データの復元
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
description: Office 365 で SharePoint のオンラインでのデータの復元の概要について説明します。
ms.openlocfilehash: ba6259e8e582a4abcf0f184b162177119a57718f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532150"
---
# <a name="sharepoint-online-data-resiliency"></a>SharePoint のオンライン ・ データのリカバリ性
SharePoint Online の重要な原則は、どの部分のデータの単一のコピーをしないことです。SharePoint Online を使用して SQL Server レプリケーションでは、コピーと、1 つのデータベースからのデータおよびデータベース オブジェクトを配布すると一貫性を維持するためにデータベース間で同期化し、テクノロジのセットであります。 

たとえば、ユーザーは、SharePoint Online でファイルを保存、ファイルはチャンク、暗号化され、Azure のブロブ ストレージに格納されています。Azure Blob サービスでは、両方のアプリケーション層とトランスポート層でのデータ整合性を確認するメカニズムを提供します。この投稿は、サービスとクライアントの観点からこれらのメカニズムの詳細に説明します。PUT と GET の両方の操作のオプションは、MD5 をチェックただし、HTTP を使用する場合、ネットワーク経由でデータの整合性を確保するのには便利な機能が提供します。さらに、HTTPS トランスポート層セキュリティの詳細を提供するため MD5 のチェックは必要ありません冗長であるように、HTTPS 経由で接続中にします。Azure Blob サービスでは、永続的なストレージ メディアを提供し、独自の整合性が保存されているデータのチェックを使用します。MD5 のアプリケーションとやり取りするときに使用されているは、HTTP 経由でのアプリケーションとサービスの間でデータを転送するとき、データの整合性をチェックするために提供されます。 

Azure Blob データの整合性を確保するのには、サービスは、いくつかの異なる方法でデータの MD5 ハッシュを使用します。これらの値は計算、送信、保存、および方法適切に利用するデータの整合性を提供するため、アプリケーションを設計するのには最終的に適用されるを理解する重要です。詳細については、 [Windows Azure Blob の MD5 の概要](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx)を参照してください。 

メタデータとファイルへのポインターは、SQL Server データベース (コンテンツのデータベース) に格納されます。-ファイル、ファイル、および更新のデルタの-すべてのチャンクは、複数の Azure ストレージ アカウントにランダムに分散された Azure ストレージの blob として保存されます。SQL データベースは、同じデータ センター内の別のラック内の別の RAID 10 ストレージ ・ アレイにミラーリングは同期的に RAID 10 ストレージ ・ アレイ上でホストされています。非同期のログ配布を使用して、2 番目のデータ センター内の別の RAID 10 ストレージ ・ アレイにデータをレプリケートします。RAID 10 と同期および非同期のレプリケーションを使用してデータを保護するだけでなく 2 番目のデータ センターにも非同期でレプリケートするスケジュールされたデータのバックアップを実行します。 

SharePoint online では、データのバックアップは 12 時間ごとを実行し、14 日間保持されます。SharePoint Online もシステムを使用してホット スタンバイ領域内にある同じ顧客データの場所 (たとえば、シカゴとサンアントニオはアメリカ合衆国では、テナントが準備されているお客様の) のペアの別の地理的にデータ センターを含むアクティブ/アクティブとして構成されます。などは、プライマリ データ センターとフェールオーバー データ センター、として San Antonio とシカゴとをプライマリ データ センターと、フェールオーバー データ センターとシカゴとサンアントニオを持つユーザーを live ライブのユーザーがあります。 