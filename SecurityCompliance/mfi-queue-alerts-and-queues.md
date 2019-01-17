---
title: 通知のキューおよびキュー
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 管理者は、Office 365 のセキュリティ & コンプライアンス センターでメール フローのダッシュ ボードで、通知のキューおよびキューについて学習できます。
ms.openlocfilehash: fe750e32136af095bb0ccff8544306db76a7a667
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685539"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="f7d35-103">通知のキューおよびキュー</span><span class="sxs-lookup"><span data-stu-id="f7d35-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="f7d35-104">キューの通知</span><span class="sxs-lookup"><span data-stu-id="f7d35-104">Queue alerts</span></span>

<span data-ttu-id="f7d35-p101">設置に、Office 365 の組織からメッセージを送信できない場合、コネクタを使用してパートナーの電子メール サーバーは、Office 365 で、メッセージがキューにします。この状態が発生する一般的な例としては次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f7d35-p101">When messages can't be sent from your Office 365 organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365. Common examples that cause this condition are:</span></span>

- <span data-ttu-id="f7d35-107">コネクタが正しく構成されていません。</span><span class="sxs-lookup"><span data-stu-id="f7d35-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="f7d35-108">オンプレミス環境ではネットワークやファイアウォールの変更をされています。</span><span class="sxs-lookup"><span data-stu-id="f7d35-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="f7d35-p102">Office 365 は、48 時間の配信を再試行するのには続行されます。48 時間後、メッセージの有効期限し、配信不能レポートの送信者に返されます (、Ndr とも呼ばれるメッセージをバウンスまたは)。</span><span class="sxs-lookup"><span data-stu-id="f7d35-p102">Office 365 will continue to retry to delivery for 48 hours. After 48 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="f7d35-p103">メールがキューに入っているボリュームでは、定義済みのしきい値 (既定値は、2000 のメッセージ) を超えている場合、アラートで**最新の通知**は、メール フローのダッシュ ボードで使用可能な管理者 (その他の電子メール アドレスなど) を電子メールで通知を受け取ります。.警告のしきい値、毎日の通知の制限、警告の受信者を構成するには、以下の**キューの通知をカスタマイズする**セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7d35-p103">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address). To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![Office 365 のセキュリティ & コンプライアンス センターでメール フローのダッシュ ボードの最近の通知領域内のキューの警告](media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="f7d35-114">キューの通知をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="f7d35-114">Customize queue alerts</span></span>

<span data-ttu-id="f7d35-p104">メール フローの分析、アラート ・ ポリシー**の警告**については、名前付き**のメッセージが遅れている**(例以下のスクリーン ショットで**電子メール通知を送信**] チェック ボックス) を作成する\>**アラート ポリシー**です。しきい値とアラートの受信者を変更するには、[ポリシー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7d35-p104">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**. You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![アラートのナビゲーション](media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="f7d35-118">新しいポリシー情報のブレードが表示されます、**ポリシーの編集**] をクリックしてできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7d35-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![ポリシーの編集 ](media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="f7d35-p105">情報のブレードは、**ポリシーの編集**に変更されます。(200 以上) の警告をトリガーするのには、1 日最小しきい値に送信された通知の数の制限、警告の電子メールの受信者を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f7d35-p105">The information blade will change to the **Edit Policy**. You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![ブレードのポリシーを編集します。](media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="f7d35-123">キューのアラートの詳細</span><span class="sxs-lookup"><span data-stu-id="f7d35-123">Queue alert details</span></span>

<span data-ttu-id="f7d35-124">アラートをクリックすると、フライアウト ウィンドウでアラートの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7d35-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![Office 365 のセキュリティ & コンプライアンス センターでメール フローのダッシュ ボードの最近の通知領域でキューの警告を選択します。](media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![Office 365 のセキュリティ & コンプライアンス センターでキューの警告詳細フライアウト](media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="f7d35-127">**再生待ちの表示**をクリックすると、キューの詳細、問題、および新しいフライアウト ウィンドウの利用可能な修正プログラムへのリンクを表示するアラートの詳細にできます。</span><span class="sxs-lookup"><span data-stu-id="f7d35-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![Office 365 のセキュリティ & コンプライアンス センターでキューの警告詳細フライアウト](media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![アラートの詳細に再生待ちの表示](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="f7d35-130">キュー</span><span class="sxs-lookup"><span data-stu-id="f7d35-130">Queues</span></span>

<span data-ttu-id="f7d35-p106">メッセージをキューに入れられたボリュームがしきい値を超えていない場合でも、メール フローのダッシュ ボードの [**キュー** ] 領域を使用する 1 時間以上のキューに登録されたメッセージを表示することができます。(値 0 は、メール フローは、[ok] を示します)、キュー内のメッセージの数を監視し、キュー内のメッセージの数が大きくなりすぎる前にアクションを実行するのには、[**キュー** ] 領域を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7d35-p106">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour. You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![Office 365 のセキュリティ & コンプライアンス センターでメール フローのダッシュ ボード内のキュー](media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="f7d35-134">キュー内のメッセージ**キュー**キューの詳細の数をクリックして、フライアウト ウィンドウ (キューの警告の詳細を**再生待ちの表示**] をクリックした後に表示される同じフライアウト) で、問題を解決するためのガイダンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7d35-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![キューの詳細](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)
