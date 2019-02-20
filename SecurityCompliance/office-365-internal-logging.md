---
title: office 365 の office 365 エンジニアリングの内部ログ
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Office 365 エンジニアリングチームの内部ログのしくみについて説明します。
ms.openlocfilehash: cf11a52541f6434a580435688db0f986f670bd31
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090759"
---
# <a name="internal-logging-for-office-365-engineering"></a><span data-ttu-id="7132a-103">Office 365 のエンジニアリングのための内部ログ記録</span><span class="sxs-lookup"><span data-stu-id="7132a-103">Internal Logging for Office 365 Engineering</span></span>
<span data-ttu-id="7132a-p101">お客様が利用できるイベントとログデータに加えて、Office 365 のエンジニアが利用できる内部ログデータ収集システムもあります。Office 365 サーバーから、Cosmos と呼ばれる内部の大規模なデータコンピューティングサービスに、さまざまな種類のログデータがアップロードされています。各サービスチームは、それぞれのサーバーからの監査ログを Cosmos データベースにアップロードして、集約と分析を行います。このデータ転送は、「Office データローダー (ODL)」と呼ばれる独自の自動化ツールを使用して、明示的に承認されたポートとプロトコルに基づいて、FIPS 140-2 で検証された TLS 接続を介して行われます。Office 365 で監査レコードを収集して処理するために使用されるツールでは、元の監査レコードのコンテンツまたは時間の順序を永続的に変更したり、取り消したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7132a-p101">In addition to the events and log data available for customers, there is also an internal log data collection system that is available to Office 365 engineers. Many different types of log data are uploaded from Office 365 servers to an internal, big data computing service called Cosmos. Each service team uploads audit logs from their respective servers into the Cosmos database for aggregation and analysis. This data transfer occurs over a FIPS 140-2-validated TLS connection on specifically approved ports and protocols using a proprietary automation tool called the Office Data Loader (ODL). The tools used in Office 365 to collect and process audit records do not allow permanent or irreversible changes to the original audit record content or time ordering.</span></span>

<span data-ttu-id="7132a-p102">サービスチームは、Cosmos を一元的なリポジトリとして使用して、アプリケーションの使用状況の分析、システムおよび運用上のパフォーマンスの測定、問題やセキュリティの問題を示す異常なパターンの調査を行います。各サービスチームは、分析の対象に応じてログのベースラインを Cosmos にアップロードします。これには、多くの場合、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7132a-p102">Service teams use Cosmos as a centralized repository to conduct an analysis of application usage, to measure system and operational performance, and to look for abnormalities and patterns that may indicate problems or security issues. Each service team uploads a baseline of logs into Cosmos, depending on what they are looking to analyze, that often include:</span></span>
- <span data-ttu-id="7132a-111">イベントログ</span><span class="sxs-lookup"><span data-stu-id="7132a-111">Event logs</span></span>
- <span data-ttu-id="7132a-112">AppLocker ログ</span><span class="sxs-lookup"><span data-stu-id="7132a-112">AppLocker logs</span></span>
- <span data-ttu-id="7132a-113">パフォーマンス データ</span><span class="sxs-lookup"><span data-stu-id="7132a-113">Performance data</span></span>
- <span data-ttu-id="7132a-114">System Center データ</span><span class="sxs-lookup"><span data-stu-id="7132a-114">System Center data</span></span>
- <span data-ttu-id="7132a-115">通話詳細レコード</span><span class="sxs-lookup"><span data-stu-id="7132a-115">Call detail records</span></span>
- <span data-ttu-id="7132a-116">qoe (Quality of experience) データ</span><span class="sxs-lookup"><span data-stu-id="7132a-116">Quality of experience data</span></span>
- <span data-ttu-id="7132a-117">IIS Web サーバーのログ</span><span class="sxs-lookup"><span data-stu-id="7132a-117">IIS Web Server logs</span></span>
- <span data-ttu-id="7132a-118">SQL Server ログ</span><span class="sxs-lookup"><span data-stu-id="7132a-118">SQL Server logs</span></span>
- <span data-ttu-id="7132a-119">Syslog データ</span><span class="sxs-lookup"><span data-stu-id="7132a-119">Syslog data</span></span>
- <span data-ttu-id="7132a-120">セキュリティ監査ログ</span><span class="sxs-lookup"><span data-stu-id="7132a-120">Security audit logs</span></span>

<span data-ttu-id="7132a-p103">データを Cosmos にアップロードする前に、ODL アプリケーションはスクラブサービスを使用して、テナント情報やエンドユーザー識別情報などの顧客データを含むフィールドを難読化し、それらのフィールドをハッシュ値で置換します。匿名化とハッシュ化されたログが書き直され、Cosmos にアップロードされます。サービスチームは、Cosmos 内のデータに対してスコープ指定クエリを実行して、関連付け、警告、およびレポートを作成します。Cosmos での監査ログデータの保持期間は、サービスチームによって決定されます。ほとんどの監査ログデータは、セキュリティインシデント調査のサポートおよび規制保持要件への対応のために、90日間またはそれ以上保持されます。</span><span class="sxs-lookup"><span data-stu-id="7132a-p103">Prior to uploading data into Cosmos, the ODL application uses a scrubbing service to obfuscate any fields that contain customer data, such as tenant information and end-user identifiable information, and replace those fields with a hash value. The anonymized and hashed logs are rewritten and then uploaded into Cosmos. Service teams run scoped queries against their data in Cosmos for correlation, alerting, and reporting. The period of audit log data retention in Cosmos is determined by the service teams; most audit log data is retained for 90 days or longer to support security incident investigations and to meet regulatory retention requirements.</span></span>

<span data-ttu-id="7132a-p104">Cosmos に格納されている Office 365 データへのアクセスは、権限のある人物に制限されます。Microsoft は、監査機能の管理を、監査機能を担当するサービスチームメンバーの制限されたサブセットに制限します。これらのチームメンバーは、Cosmos のデータを変更または削除することはできません。また、Cosmos のログメカニズムに加えられたすべての変更は記録および監査されます。</span><span class="sxs-lookup"><span data-stu-id="7132a-p104">Access to Office 365 data stored in Cosmos is restricted to authorized personnel. Microsoft restricts the management of audit functionality to the limited subset of service team members that are responsible for audit functionality. These team members do not have the ability to modify or delete data from Cosmos, and all changes to logging mechanisms for Cosmos are recorded and audited.</span></span>

<span data-ttu-id="7132a-p105">各サービスチームは、特定のアプリケーションが特定の分析を実行することを承認することによって、分析用のログデータにアクセスします。たとえば、office 365 セキュリティチームは、独自のイベントログパーサーを使用して Cosmos のデータを使用して、office 365 運用環境で疑わしい可能性のあるアクティビティに関する操作可能なレポートを関連付け、警告、および生成します。このデータからのレポートは、脆弱性を修正し、サービスの全体的なパフォーマンスを向上させるために使用されます。特定の警告またはレポートでさらに調査が必要な場合、サービス担当者は、そのデータを Office 365 サービスにインポートし直すように要求できます。Cosmos からインポートされる特定のログは暗号化されており、サービス担当者は復号化キーにアクセスできないため、対象のログは、スコープが設定された結果を承認済みのサービス担当者に返す復号化サービスを介してプログラムによって渡されます。この課題から見つかった脆弱性は、Microsoft の標準セキュリティインシデント管理チャネルを使用して報告およびエスカレートされます。</span><span class="sxs-lookup"><span data-stu-id="7132a-p105">Each service team accesses its log data for analysis by authorizing certain applications to conduct specific analysis. For example, the Office 365 Security team uses data from Cosmos through a proprietary event log parser to correlate, alert, and generate actionable reports on possible suspicious activity in the Office 365 production environment. The reports from this data are used to correct vulnerabilities, and to improve the overall performance of the service. If a specific alert or report requires further investigation, service personnel can request that data be imported back into the Office 365 service. Since the specific log being imported from Cosmos is in encrypted and service personnel do not have access to decryption keys, the target log is programmatically passed through a decryption service that returns scoped results to the authorized service personnel. Any vulnerabilities found from this exercise are reported and escalated using Microsoft's standard security incident management channels.</span></span>
