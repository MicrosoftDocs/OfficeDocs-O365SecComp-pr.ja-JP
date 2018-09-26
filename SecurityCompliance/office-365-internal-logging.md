---
title: Office 365 の Office 365 のエンジニア リング内部のログを記録します。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Office 365 のエンジニア リング チームは、どのように内部のログの詳細については。
ms.openlocfilehash: 4cade759fb4c095565b4e1f85ce15ed546177082
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038190"
---
# <a name="internal-logging-for-office-365-engineering"></a><span data-ttu-id="59f98-103">Office 365 のエンジニアリングのための内部ログ記録</span><span class="sxs-lookup"><span data-stu-id="59f98-103">Internal Logging for Office 365 Engineering</span></span>
<span data-ttu-id="59f98-p101">に加えて、イベントやログのデータが提供されていますが、Office 365 のエンジニアに提供される内部のログのデータ収集システムもあります。さまざまな種類のログ データは、Office 365 のサーバーから、大規模な内部データの世界と呼ばれるサービスをコンピューターにアップロードされます。各サービス ・ チームは、集計と分析のための世界のデータベースに、それぞれのサーバーの監査ログをアップロードします。このデータ転送は、具体的には承認済みのポートとプロトコルの Office データ ローダー (ODL) と呼ばれる独自の自動化ツールを使用して上の FIPS 140-2 検証 TLS 接続を介して行われます。ツールを収集するために Office 365 の使用プロセスの監査レコードを永続的にすることはできないし、元に戻す変更の監査レコードの内容や時間の順番です。</span><span class="sxs-lookup"><span data-stu-id="59f98-p101">In addition to the events and log data available for customers, there is also an internal log data collection system that is available to Office 365 engineers. Many different types of log data are uploaded from Office 365 servers to an internal, big data computing service called Cosmos. Each service team uploads audit logs from their respective servers into the Cosmos database for aggregation and analysis. This data transfer occurs over a FIPS 140-2-validated TLS connection on specifically approved ports and protocols using a proprietary automation tool called the Office Data Loader (ODL). The tools used in Office 365 to collect and process audit records do not allow permanent or irreversible changes to the original audit record content or time ordering.</span></span>

<span data-ttu-id="59f98-p102">サービス チームは、システムと運用のパフォーマンスを測定してのに異常との問題やセキュリティ上の問題がある可能性のあるパターンを検索するのにアプリケーションの使用状況の分析を実施するのには、一元的なリポジトリとして世界を使用します。各サービス ・ チームは、基準を含む多くの場合によっては目的の情報を分析するために世界では、ログのアップロードします。</span><span class="sxs-lookup"><span data-stu-id="59f98-p102">Service teams use Cosmos as a centralized repository to conduct an analysis of application usage, to measure system and operational performance, and to look for abnormalities and patterns that may indicate problems or security issues. Each service team uploads a baseline of logs into Cosmos, depending on what they are looking to analyze, that often include:</span></span>
- <span data-ttu-id="59f98-111">イベント ログ</span><span class="sxs-lookup"><span data-stu-id="59f98-111">Event logs</span></span>
- <span data-ttu-id="59f98-112">AppLocker のログ</span><span class="sxs-lookup"><span data-stu-id="59f98-112">AppLocker logs</span></span>
- <span data-ttu-id="59f98-113">パフォーマンス データ</span><span class="sxs-lookup"><span data-stu-id="59f98-113">Performance data</span></span>
- <span data-ttu-id="59f98-114">システム センター データ</span><span class="sxs-lookup"><span data-stu-id="59f98-114">System Center data</span></span>
- <span data-ttu-id="59f98-115">詳細レコードを呼び出す</span><span class="sxs-lookup"><span data-stu-id="59f98-115">Call detail records</span></span>
- <span data-ttu-id="59f98-116">経験データの品質</span><span class="sxs-lookup"><span data-stu-id="59f98-116">Quality of experience data</span></span>
- <span data-ttu-id="59f98-117">IIS Web サーバーのログ</span><span class="sxs-lookup"><span data-stu-id="59f98-117">IIS Web Server logs</span></span>
- <span data-ttu-id="59f98-118">SQL Server ログ</span><span class="sxs-lookup"><span data-stu-id="59f98-118">SQL Server logs</span></span>
- <span data-ttu-id="59f98-119">Syslog データ</span><span class="sxs-lookup"><span data-stu-id="59f98-119">Syslog data</span></span>
- <span data-ttu-id="59f98-120">セキュリティ監査ログ</span><span class="sxs-lookup"><span data-stu-id="59f98-120">Security audit logs</span></span>

<span data-ttu-id="59f98-p103">世界にデータをアップロードする前に ODL アプリケーションを使用してスクラブ サービス テナント情報やエンド ・ ユーザーを特定する情報など、お客様のデータを格納しているフィールドを難読化し、それらのフィールドをハッシュ値に置き換えます。匿名で扱われ、ハッシュ化されたログは書き換えるし、世界にアップロードされました。サービス チームでは、相互関係、警告、およびレポート作成の世界では、そのデータに対してスコープを設定したクエリを実行します。サービス チームは世界での監査ログ データの保存期間が決定されます。保存に関する規制要件に対応するセキュリティの問題の調査をサポートするために 90 日間以上ほとんどの監査ログのデータが保持されます。</span><span class="sxs-lookup"><span data-stu-id="59f98-p103">Prior to uploading data into Cosmos, the ODL application uses a scrubbing service to obfuscate any fields that contain customer data, such as tenant information and end-user identifiable information, and replace those fields with a hash value. The anonymized and hashed logs are rewritten and then uploaded into Cosmos. Service teams run scoped queries against their data in Cosmos for correlation, alerting, and reporting. The period of audit log data retention in Cosmos is determined by the service teams; most audit log data is retained for 90 days or longer to support security incident investigations and to meet regulatory retention requirements.</span></span>

<span data-ttu-id="59f98-p104">世界に格納されている Office 365 のデータへのアクセスは、権限のある担当者に限定されます。マイクロソフトでは、監査機能の管理を監査機能を担当するサービス チームのメンバーの制限のサブセットに制限されます。これらのチーム メンバーには、変更または世界からデータを削除することはありませんし、世界のロギング メカニズムに対するすべての変更が記録され、監査します。</span><span class="sxs-lookup"><span data-stu-id="59f98-p104">Access to Office 365 data stored in Cosmos is restricted to authorized personnel. Microsoft restricts the management of audit functionality to the limited subset of service team members that are responsible for audit functionality. These team members do not have the ability to modify or delete data from Cosmos, and all changes to logging mechanisms for Cosmos are recorded and audited.</span></span>

<span data-ttu-id="59f98-p105">各サービス ・ チームは、特定の分析を実行する特定のアプリケーションを承認することによって、ログ データを分析をアクセスします。たとえば、Office 365 のセキュリティ チームは、関連づけ、警告、および Office 365 の実稼働環境での不審な動作が可能な実践的なレポートを生成する世界から独自のイベント ログ パーサーを使用してデータを使用します。脆弱性を修正し、サービスの全体的なパフォーマンスを向上させるために、このデータからレポートが使用されます。特定のアラートやレポートが必要な場合さらに調査、サービス担当者が Office 365 サービスにデータをインポートすることを要求することができます。特定のログから世界からインポート中に暗号化されて、サービス担当者は、復号化鍵へのアクセスを必要はありませんターゲット ログが復号化サービス、認定サービス担当者にスコープを設定した結果を返すプログラムを使用して渡されます。この練習から発見された脆弱性がレポートされ、Microsoft の標準的なセキュリティ インシデントの管理チャネルを使用してエスカレートします。</span><span class="sxs-lookup"><span data-stu-id="59f98-p105">Each service team accesses its log data for analysis by authorizing certain applications to conduct specific analysis. For example, the Office 365 Security team uses data from Cosmos through a proprietary event log parser to correlate, alert, and generate actionable reports on possible suspicious activity in the Office 365 production environment. The reports from this data are used to correct vulnerabilities, and to improve the overall performance of the service. If a specific alert or report requires further investigation, service personnel can request that data be imported back into the Office 365 service. Since the specific log being imported from Cosmos is in encrypted and service personnel do not have access to decryption keys, the target log is programmatically passed through a decryption service that returns scoped results to the authorized service personnel. Any vulnerabilities found from this exercise are reported and escalated using Microsoft's standard security incident management channels.</span></span>
