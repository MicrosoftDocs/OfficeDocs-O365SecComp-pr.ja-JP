---
title: SMTP Auth クライアントのレポート
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードの SMTP 認証クライアントレポートについて学習できます。
ms.openlocfilehash: 21d2446bd7441f17c2371186d098118c6403de0c
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598133"
---
# <a name="smtp-auth-clients-report"></a><span data-ttu-id="59d50-103">SMTP Auth クライアントのレポート</span><span class="sxs-lookup"><span data-stu-id="59d50-103">SMTP Auth clients report</span></span>

<span data-ttu-id="59d50-104">**Smtp auth clients**レポートでは、組織内のユーザーまたはシステムアカウントによる smtp auth クライアント送信プロトコルの使用が強調されています。</span><span class="sxs-lookup"><span data-stu-id="59d50-104">The **SMTP Auth clients** report highlights the use of the SMTP Auth client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="59d50-105">この従来のプロトコル (エンドポイント smtp.office365.com を使用します) は基本認証のみを提供し、侵害されたアカウントが電子メールを送信するために使用されやすくなります。</span><span class="sxs-lookup"><span data-stu-id="59d50-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span>  <span data-ttu-id="59d50-106">このレポートでは、異常な動作を確認できます。</span><span class="sxs-lookup"><span data-stu-id="59d50-106">This report allows you to check for unusual activity.</span></span> <span data-ttu-id="59d50-107">また、SMTP 認証を使用するクライアントまたはデバイスの TLS 使用状況データも表示されます。</span><span class="sxs-lookup"><span data-stu-id="59d50-107">It also shows the TLS usage data for clients or devices using SMTP Auth.</span></span>

<span data-ttu-id="59d50-108">メールフローダッシュボードに表示されるウィジェットは、過去7日間に SMTP 認証プロトコルを使用したユーザーまたはサービスアカウントの数を示します。</span><span class="sxs-lookup"><span data-stu-id="59d50-108">The widget that's shown in the Mail Flow dashboard indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードの SMTP 認証クライアントのレポート](media/smtp-auth-clients-report-selected.png)

<span data-ttu-id="59d50-110">ウィジェットをクリックすると、過去1週間の TLS 使用量とボリュームの集計ビューを表示するポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="59d50-110">Clicking on the widget opens a flyout that provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![SMTP Auth clients レポートのポップアップ](media/smtp-auth-clients-flyout.png)

<span data-ttu-id="59d50-112">[ **SMTP Auth Clients] レポート**リンクをクリックすると、2つの主要なデータビューと2つのデータビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="59d50-112">When you click on the **SMTP Auth Clients Report** link, you'll see two main data pivots and two data views.</span></span> <span data-ttu-id="59d50-113">データピボットは、**送信ボリューム**と**TLS 使用率**です。</span><span class="sxs-lookup"><span data-stu-id="59d50-113">The data pivots are the **Sending Volume** and **TLS Usage**.</span></span> <span data-ttu-id="59d50-114">データビューは、グラフと詳細の表です。</span><span class="sxs-lookup"><span data-stu-id="59d50-114">The data views are the chart and the details table.</span></span>

<span data-ttu-id="59d50-115">**送信ボリューム**ビューには、指定された時間範囲に関して SMTP Auth を使用して送信されたメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="59d50-115">The **Sending Volume** view shows the number of messages that were sent using SMTP Auth for the specified time range.</span></span> <span data-ttu-id="59d50-116">範囲を調整するには、[**フィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59d50-116">You can adjust the range by clicking **Filters**.</span></span> <span data-ttu-id="59d50-117">このグラフは、送信者のドメインによって整理されています。</span><span class="sxs-lookup"><span data-stu-id="59d50-117">The chart is organized by sender domain.</span></span> <span data-ttu-id="59d50-118">ドメインごとに個別のデータを表示するには、[**データの表示**] ドロップダウンでそのドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="59d50-118">You can see separate data for each domain by selecting the domain in the **Show data for** drop down.</span></span>

![SMTP Auth Clients レポートでのボリュームの送信](media/smtp-auth-clients-report-sending-volume.png)

<span data-ttu-id="59d50-120">[**詳細テーブルの表示**] をクリックすると、送信者とそのメッセージカウントに関する詳細な情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="59d50-120">You can view detailed information about the senders and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="59d50-121">グラフに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59d50-121">To return to the chart, click **View report**.</span></span>

![SMTP Auth Clients レポートでのボリューム送信の詳細表](media/smtp-auth-clients-report-details-sending-volume.png)

<span data-ttu-id="59d50-123">Tls**使用率**ピボットは、Office 365 の tls 1.0 と tls 1.1 の今後の廃止によって重要です。</span><span class="sxs-lookup"><span data-stu-id="59d50-123">The **TLS Usage** pivot is important due to the upcoming deprecation of TLS1.0 and TLS1.1 in Office 365.</span></span> <span data-ttu-id="59d50-124">多くのレガシデバイスおよびアプリケーションは、SMTP Auth で TLS 1.0 を使用できる場合にのみ電子メールを送信できなくなります。このピボットにより、以前のバージョンの TLS を使用しているユーザーとシステムアカウントを識別し、アクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="59d50-124">Many legacy devices and applications will be unable to send email if they are only capable of using TLS1.0 with SMTP Auth. This pivot allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

![SMTP Auth Clients レポートでの TLS の使用](media/smtp-auth-clients-report-tls-usage.png)

<span data-ttu-id="59d50-126">[**詳細テーブルの表示**] をクリックすると、送信者、SMTP 認証で使用している TLS のバージョン、およびそれらのメッセージ数に関する詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="59d50-126">You can view detailed information about the senders, the versions of TLS they are using with SMTP Auth, and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="59d50-127">グラフに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59d50-127">To return to the chart, click **View report**.</span></span>

<span data-ttu-id="59d50-128">[要求レポート] をクリックして、レポートの詳細バージョンをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="59d50-128">You can also download a more detailed version of the report by clicking Request report.</span></span>

![SMTP Auth Clients レポートでの TLS 使用の詳細表](media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a><span data-ttu-id="59d50-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="59d50-130">See also</span></span>

<span data-ttu-id="59d50-131">メールフローダッシュボードのその他のメールフローインサイトの詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59d50-131">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
