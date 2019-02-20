---
title: Office 365 SharePoint データの復元
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Office 365 の SharePoint Online のデータ復元の概要について説明します。
ms.openlocfilehash: c550cb6572cb71b53cd544af64339129f72b888f
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090889"
---
# <a name="sharepoint-online-data-resiliency"></a>SharePoint Online データの復元
SharePoint Online の主要な原則は、データの一部を1つのコピーで保持することではありません。SharePoint Online では、SQL Server レプリケーションを使用します。これは、データベース間でデータおよびデータベースオブジェクトをコピーして分散させるための一連のテクノロジで、一貫性を維持するためにデータベース間で同期します。 

たとえば、ユーザーが SharePoint Online にファイルを保存すると、ファイルがチャンクされ、暗号化されて、Azure Blob ストレージ内に格納されます。Azure Blob サービスは、アプリケーション層とトランスポート層の両方でデータの整合性を確保するメカニズムを提供します。この投稿では、サービスとクライアントの観点からこれらのメカニズムについて詳細に説明します。MD5 チェックは、PUT と GET の両方の操作ではオプションです。ただし、HTTP を使用する際にネットワーク全体でデータの整合性を確保するための便利な機能が提供されています。また、https がトランスポート層セキュリティを提供するため、https を使用して接続すると、余分な MD5 チェックは不要になります。Azure Blob サービスは永続的なストレージメディアを提供し、保存されたデータに対して独自の整合性チェックを使用します。アプリケーションと対話するときに使用される MD5's は、アプリケーションとサービス間で HTTP 経由でデータを転送するときに、データの整合性を確認するために提供されています。 

データの整合性を確保するために、Azure Blob サービスはさまざまな方法でデータの MD5 ハッシュを使用します。これらの値がどのように計算、転送、保存され、最終的に、それらの値を使用してデータの整合性を提供するようにアプリケーションを設計することが重要であることを理解することが重要です。詳細については、「 [Windows Azure Blob MD5 の概要](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx)」を参照してください。 

ファイルへのメタデータとポインターは、SQL Server データベース (コンテンツデータベース) に格納されます。すべてのチャンク–ファイル、ファイル、および更新のデルタは、複数の azure ストレージアカウント間でランダムに分散される azure ストレージに blob として格納されます。SQL データベースは raid 10 ストレージアレイ上でホストされており、同じデータセンター内の別のラックにある別の raid 10 ストレージアレイに同期ミラーリングされます。次に、非同期ログ配布を使用して、第2データセンター内の別の RAID 10 ストレージアレイにデータをレプリケートします。RAID 10 および同期および非同期レプリケーションを使用してデータを保護することに加えて、2番目のデータセンターに非同期的にレプリケートされるスケジュールされたデータバックアップも行われます。 

SharePoint Online では、データバックアップは12時間ごとに実行され、14日間保持されます。SharePoint Online では、同一の顧客データの場所 (米国でのテナントを準備しているお客様のために、シカゴおよび San Antonio など) 内に、地理的に独立した複数のデータセンターを含むホットスタンバイシステムも使用します。アクティブ/アクティブとして構成されます。たとえば、プライマリデータセンターとしてシカゴを持つ live ユーザーと、フェールオーバーデータセンターとして、san Antonio がプライマリデータセンターとして存在する live ユーザーと、フェールオーバーデータセンターとしての Antonio があります。 