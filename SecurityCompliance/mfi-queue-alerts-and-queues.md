---
title: キューのアラートとキュー
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 管理者は、Security & コンプライアンスセンターのメールフローダッシュボードのキューのアラートとキューについて説明しています。
ms.openlocfilehash: 490665bb6b062c5a0b93c988adea9eeb9827cb86
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32267694"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="088d7-103">キューのアラートとキュー</span><span class="sxs-lookup"><span data-stu-id="088d7-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="088d7-104">キューのアラート</span><span class="sxs-lookup"><span data-stu-id="088d7-104">Queue alerts</span></span>

<span data-ttu-id="088d7-105">コネクタを使用して office 365 組織からオンプレミスまたはパートナーの電子メールサーバーにメッセージを送信できない場合、メッセージは office 365 でキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="088d7-105">When messages can't be sent from your Office 365 organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365.</span></span> <span data-ttu-id="088d7-106">このような状態になる一般的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="088d7-106">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="088d7-107">コネクタが正しく構成されていません。</span><span class="sxs-lookup"><span data-stu-id="088d7-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="088d7-108">オンプレミス環境でネットワークまたはファイアウォールの変更が行われています。</span><span class="sxs-lookup"><span data-stu-id="088d7-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="088d7-109">Office 365 は、引き続き48時間、配信を再試行します。</span><span class="sxs-lookup"><span data-stu-id="088d7-109">Office 365 will continue to retry to delivery for 48 hours.</span></span> <span data-ttu-id="088d7-110">48時間後に、メッセージは有効期限が切れて、配信不能レポート (ndr またはバウンスメッセージとも呼ばれる) で送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="088d7-110">After 48 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="088d7-111">キューに登録された電子メールのボリュームが事前に定義されたしきい値 (既定値は2000メッセージ) を超えた場合、**最近の通知**のメールフローダッシュボードで通知が使用可能になり、管理者はメール通知を受信します (ユーザーの代替メールアドレス)。.</span><span class="sxs-lookup"><span data-stu-id="088d7-111">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address).</span></span> <span data-ttu-id="088d7-112">警告のしきい値、毎日の通知の制限、または通知の受信者を構成するには、以下の「**キューの警告をカスタマイズ**する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="088d7-112">To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードの [最近の通知] 領域でのキューのアラート](media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="088d7-114">キューの通知をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="088d7-114">Customize queue alerts</span></span>

<span data-ttu-id="088d7-115">メールフローの insights メッセージという名前のアラートポリシー**が遅延して**います (以下の例のスクリーンショットの例では\*\*\*\* \> \*\*\*\*、[**電子メール通知の送信**] チェックボックスをオンにしています)。</span><span class="sxs-lookup"><span data-stu-id="088d7-115">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**.</span></span> <span data-ttu-id="088d7-116">ポリシーをクリックして、しきい値と警告の受信者を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="088d7-116">You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![通知ナビゲーション](media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="088d7-118">新しいポリシー情報ブレードが表示されるので、[**ポリシーの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="088d7-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![ポリシーの編集](media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="088d7-120">情報ブレードが**編集ポリシー**に変更されます。</span><span class="sxs-lookup"><span data-stu-id="088d7-120">The information blade will change to the **Edit Policy**.</span></span> <span data-ttu-id="088d7-121">通知メールの受信者、1日に送信される通知の数の制限、および警告をトリガーする最小しきい値 (200 以上) を変更できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="088d7-121">You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![ポリシーブレードを編集する](media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="088d7-123">キュー警告の詳細</span><span class="sxs-lookup"><span data-stu-id="088d7-123">Queue alert details</span></span>

<span data-ttu-id="088d7-124">アラートをクリックすると、アラートの詳細がフライアウトウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="088d7-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードの [最近の通知] 領域でキューのアラートを選択する](media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![セキュリティ & コンプライアンスセンターのキュー警告詳細ポップアップ](media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="088d7-127">アラート詳細の [**キューの表示**] をクリックすると、キューの詳細、問題、および新しいフライアウトウィンドウで利用可能な修正へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="088d7-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![セキュリティ & コンプライアンスセンターのキュー警告詳細ポップアップ](media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![アラートの詳細のキューを表示する](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="088d7-130">キュー</span><span class="sxs-lookup"><span data-stu-id="088d7-130">Queues</span></span>

<span data-ttu-id="088d7-131">キュー内のメッセージボリュームがしきい値を超えていない場合でも、メールフローダッシュボードの [**キュー** ] 領域を使用して、キューに入れられたメッセージを1時間以上表示することができます。</span><span class="sxs-lookup"><span data-stu-id="088d7-131">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour.</span></span> <span data-ttu-id="088d7-132">キューの領域を\*\*\*\* 使用して、キューに入れられたメッセージ数 (0 はメールフローが OK であることを示します) を監視し、キューに入れられたメッセージの数が多すぎる前に処理を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="088d7-132">You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードのキュー](media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="088d7-134">キュー内のキューに入れられた\*\*\*\* メッセージの数をクリックすると、問題の解決方法に関するキューの詳細とガイダンスが、フライアウトのウィンドウに表示されます (キューの通知の詳細については、[**キューの表示**] をクリックした後に表示されるポップアップと同じポップアップ)。</span><span class="sxs-lookup"><span data-stu-id="088d7-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![キューの詳細](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a><span data-ttu-id="088d7-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="088d7-136">See also</span></span>

<span data-ttu-id="088d7-137">メールフローダッシュボードの他のメールフローインサイトの詳細については、「 [Security &/コンプライアンスセンター」の「mail flow insights](mail-flow-insights.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="088d7-137">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights.md).</span></span>
