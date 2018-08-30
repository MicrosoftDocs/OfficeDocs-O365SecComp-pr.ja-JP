---
title: Office 365 のデータ破損に対処します。
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
description: データの破損で、Office 365 との防止と回復の Microsoft の取り組みの説明。
ms.openlocfilehash: 087be23ce5dad1daf62357cb08e27c0a15962792
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532241"
---
# <a name="dealing-with-data-corruption-in-office-365"></a><span data-ttu-id="27350-103">Office 365 のデータ破損に対処します。</span><span class="sxs-lookup"><span data-stu-id="27350-103">Dealing with Data Corruption in Office 365</span></span>

<span data-ttu-id="27350-p101">大規模なクラウド サービスを実行するの難しい側面の 1 つは、データと独立したシステムの大規模なボリュームを指定したデータの破損を処理する方法です。データの破損は、によって発生することができます。</span><span class="sxs-lookup"><span data-stu-id="27350-p101">One of the challenging aspects of running a large-scale cloud service is how to handle data corruption, given the large volume of data and independent systems. Data corruption can be caused by:</span></span>
- <span data-ttu-id="27350-106">アプリケーションの状態の一部またはすべての破損、アプリケーションまたはインフラストラクチャのバグ</span><span class="sxs-lookup"><span data-stu-id="27350-106">Application or infrastructure bugs, corrupting some or all of the application state</span></span> 
- <span data-ttu-id="27350-107">ハードウェアの問題、データ損失やデータを読み取ることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="27350-107">Hardware issues that result in lost data or an inability to read data</span></span> 
- <span data-ttu-id="27350-108">運用上のミス</span><span class="sxs-lookup"><span data-stu-id="27350-108">Human operational errors</span></span> 
- <span data-ttu-id="27350-109">悪意のあるハッカーや悪意のある従業員</span><span class="sxs-lookup"><span data-stu-id="27350-109">Malicious hackers and disgruntled employees</span></span> 
- <span data-ttu-id="27350-110">データの一部が失われると、外部のサービスの問題</span><span class="sxs-lookup"><span data-stu-id="27350-110">Incidents in external services that result in some loss of data</span></span> 

<span data-ttu-id="27350-p102">データの整合性のリカバリ性の向上が少ないデータの破損の問題なので、Microsoft Office 365 の保護メカニズムから発生していると同様にシステムとプロセスが存在する場合は、データを回復することが可能の破損を防ぐために作成しました。データの破損に対して弾力性を向上させるエンジニア リングのリリース プロセスのさまざまな段階でチェックし、プロセスの存在を含みます。</span><span class="sxs-lookup"><span data-stu-id="27350-p102">Because greater resiliency in data integrity means fewer data corruption incidents, Microsoft has built into Office 365 protection mechanisms to prevent corruption from happening, as well as systems and processes that enable us to recover data if it does. Checks and processes exist within the various stages of the engineering release process to increase resiliency against data corruption, including:</span></span>
- <span data-ttu-id="27350-113">システムの設計</span><span class="sxs-lookup"><span data-stu-id="27350-113">System Design</span></span>
- <span data-ttu-id="27350-114">コードの組織と構造</span><span class="sxs-lookup"><span data-stu-id="27350-114">Code organization and structure</span></span> 
- <span data-ttu-id="27350-115">コード レビュー</span><span class="sxs-lookup"><span data-stu-id="27350-115">Code review</span></span> 
- <span data-ttu-id="27350-116">単体テスト、統合テストとシステム テスト</span><span class="sxs-lookup"><span data-stu-id="27350-116">Unit tests, integration tests, and system tests</span></span>
- <span data-ttu-id="27350-117">トリップ ワイヤのテスト/ゲート</span><span class="sxs-lookup"><span data-stu-id="27350-117">Trip wires tests/gates</span></span> 

<span data-ttu-id="27350-p103">Office 365 の本番環境では、データ センター間でのピア レプリケーションは、複数のライブ データのコピーは常が保証されます。標準画像とスクリプトを使用して、失われたサーバーを回復して、レプリケートされたデータは顧客データを復元するために使用します。Microsoft では、組み込みのデータ復元機能のチェック、プロセスのため、SharePoint Online と内部のコードは、組み込みのレプリケーションを使用して Office 365 の情報システムのドキュメント (セキュリティ関連のドキュメントを含む) ののみのバックアップリポジトリ ツールでは、ソース ・ デポです。SharePoint online では、システムのドキュメントが格納されているし、ソース ・ デポには、システムとアプリケーションのイメージが含まれています。SharePoint Online とソース ・ デポ バージョン管理を使用し、ほぼリアルタイムにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="27350-p103">Within Office 365 production environments, peer replication between datacenters ensures that there are always multiple live copies of any data. Standard images and scripts are used to recover lost servers, and replicated data is used to restore customer data. Because of the built-in data resiliency checks and processes, Microsoft maintains backups only of Office 365 information system documentation (including security-related documentation), using built-in replication in SharePoint Online and our internal code repository tool, Source Depot. System documentation is stored in SharePoint Online, and Source Depot contains system and application images. Both SharePoint Online and Source Depot use versioning and are replicated in near real-time.</span></span> 