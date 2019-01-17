---
title: セキュリティ & コンプライアンス センターでのメッセージのトレース
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
description: 管理者は、メッセージに何が起こったかを確認するのには、セキュリティ & コンプライアンス センターでメッセージのトレースを使用できます。
ms.openlocfilehash: 9dfdab4adc5caba55664e93b49c8428791670ab3
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685545"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="e8bd2-103">セキュリティ & コンプライアンス センターでのメッセージのトレース</span><span class="sxs-lookup"><span data-stu-id="e8bd2-103">Message trace in the Security & Compliance Center</span></span>

<span data-ttu-id="e8bd2-p101">セキュリティ & コンプライアンス センターでのメッセージのトレースは、Exchange Online 組織全体を移動する電子メール メッセージを従います。かどうかメッセージが受信した、拒否、延期、またはサービスによって提供されるを指定できます。最終的な状態に到達する前に、メッセージに対してどのようなアクションを実行したことも示しています。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p101">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization. You can determine if a message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="e8bd2-p102">セキュリティ & コンプライアンス センターでのメッセージのトレースは、Exchange 管理センター (EAC) で利用できたメッセージ トレースに強化しました。メッセージ トレースの情報を使用するには効率的に質問にユーザーがメッセージに何が起こったか、トラブルシューティングについては、メール フローの問題、ポリシーの変更を検証します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p102">Message trace in the Security & Compliance Center improves upon message trace that was available in the Exchange admin center (EAC). You can use the information from message trace to efficiently answer user questions about what happened to their messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="e8bd2-109">開いているメッセージのトレース</span><span class="sxs-lookup"><span data-stu-id="e8bd2-109">Open message trace</span></span>

1. <span data-ttu-id="e8bd2-110">職場や学校のアカウントで [Office 365 にサインインします](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-110">[Sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="e8bd2-111">左上のアプリ起動ツールのアイコン ![Office 365 アプリ起動ツール アイコン](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) を選び、[ **管理者**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-111">Select the app launcher icon ![Office 365 app launcher icon](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="e8bd2-112">左ナビゲーションでは、**管理センター**を展開し、 **& 準拠のセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-112">In the lower-left navigation, expand **Admin centers** and select **Security & Compliance**.</span></span>

4. <span data-ttu-id="e8bd2-113">**_AMP_ 準拠のセキュリティ**] ページを開くには、**メールの流れ**を展開し、**メッセージのトレース**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-113">In the **Security & Compliance** page that opens, expand **Mail flow**, and select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="e8bd2-114">メッセージ トレースのページ</span><span class="sxs-lookup"><span data-stu-id="e8bd2-114">Message trace page</span></span>

<span data-ttu-id="e8bd2-p103">ここからは、[**トレースの開始**] ボタンをクリックして新しい既定のトレースを開始できます。これは、検索されますすべてのメッセージの送信者と受信者のすべての最後の 2 日間。またはクエリを使用可能なカテゴリの中から保存されたクエリのいずれかを使用することができ、としてそれらを実行するか、独自のクエリの開始点として使用するか。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p103">From here you can start a new default trace by clicking on the **Start a trace** button. This will search for all messages for all senders and recipients for the last two days. Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="e8bd2-118">**既定のクエリ**: Office 365 によって提供される組み込みのクエリです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-118">**Default queries**: Built-in queries provided by Office 365.</span></span>

- <span data-ttu-id="e8bd2-119">**カスタム クエリ**: クエリは、将来使用するため、組織内の管理者が保存されます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-119">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="e8bd2-p104">**自動保存されたクエリ**: 最後の 10 が最後にクエリを実行します。このリストでは、中断した場所を選択する単純なです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p104">**Autosaved queries**: The last ten most recently run queries. This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="e8bd2-122">このページでは、レポート自体と同様に、登録した要求の**レポートをダウンロード可能なフォント**のセクションでダウンロード可能がある場合に。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-122">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="e8bd2-123">新しいメッセージ トレースのオプション</span><span class="sxs-lookup"><span data-stu-id="e8bd2-123">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="e8bd2-124">送信者と受信者をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-124">Filter by senders and recipients</span></span>

<span data-ttu-id="e8bd2-125">既定値は、**すべての送信者**と**すべての受信者**が、結果をフィルター処理するのには次のフィールドを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-125">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="e8bd2-p105">**これらの人々 によって**: 組織の 1 つまたは複数の送信者を選択するには、このフィールドをクリックします。名前を入力して起動することも、リスト内の項目は何を入力したら、かなりの検索ページがどのように動作するように、フィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p105">**By these people**: Click in this field to select one or more senders from your organization. You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="e8bd2-128">**これらの人々 に**: 組織内の 1 つまたは複数の受信者を選択するには、このフィールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-128">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

<span data-ttu-id="e8bd2-p106">外部の送信者と受信者の電子メール アドレスを入力することもできます。ワイルドカードがサポートされている (`*@contoso.com`または`scot?@contoso.com`)、同時に同じフィールドに複数のワイルドカード エントリは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p106">You can also type the email addresses of external senders and recipients. Wildcards are supported (`*@contoso.com` or `scot?@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span>

### <a name="time-range"></a><span data-ttu-id="e8bd2-131">時間範囲</span><span class="sxs-lookup"><span data-stu-id="e8bd2-131">Time range</span></span>

<span data-ttu-id="e8bd2-p107">既定値は**2 日**、ですが、最大 90 日間の日付/時刻範囲を指定することができます。日付/時刻範囲を使用する場合は、これらの問題を考慮します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p107">The default value is **2 days**, but you can specify date/time ranges of up to 90 days. When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="e8bd2-p108">既定では、タイム ラインを使用して**スライダー**の表示に時間の範囲を選択します。のみ曜日を選択するか、時刻が表示されている設定できます。開始/終了のバブルのスナップが中間の値を選択しようとしています。 最も近い設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p108">By default, you select the time range in **Slider** view using a time line. You can only select the day or time settings that are displayed. Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

   ![セキュリティ & コンプライアンス センターに新しいメッセージ トレースにスライダーの時間範囲](media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

   <span data-ttu-id="e8bd2-p109">ですが、また、(時間を含む)、**開始日**と**終了日**の値を指定することができ、**タイム ゾーン**の日付と時刻の範囲を選択することも、**ユーザー設定**のビューに切り替えることができます。**タイム ゾーン**の設定が、クエリの入力値と、クエリの結果の両方に適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p109">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range. Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

   ![セキュリティ & コンプライアンス センターに新しいメッセージ トレースにユーザー設定の時間範囲](media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

   <span data-ttu-id="e8bd2-p110">10 日以内の結果は、**サマリ**・ レポートとしてすぐに利用できます。10 日間よりも少しでも時間の範囲を指定する場合はダウンロード可能な CSV ファイル (レポート**サマリーの拡張**または**拡張**) として利用可能なだけに結果が延期されます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p110">For 10 days or less, the results are available instantly as a **Summary** report. If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

   <span data-ttu-id="e8bd2-143">異なるレポートの種類の詳細については、このトピックの [[レポートの種類の選択](#choose-report-type)] セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-143">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this topic.</span></span>

   <span data-ttu-id="e8bd2-p111">**注**: 強化の概要と拡張のレポートは、アーカイブされたメッセージのトレース データを使用して準備し、レポートがダウンロードされる前に、数時間かかることができます。同時にレポートの提出依頼も送信、他の多くの管理者によって可能性がありますも待ち時間が発生する、キューに入れられた要求の処理が開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p111">**Note**: Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download. Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="e8bd2-p112">**スライダー**のビューでクエリを保存すると、相対的な時間の範囲 (たとえば、今日から 3 日) が保存されます。絶対日付と時刻の範囲を保存する**カスタム**ビューでクエリを保存する (たとえば、2018-05-06 以降に 2018-05-08 13時 00分 18時 00分)。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p112">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today). Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="e8bd2-148">他の検索オプション</span><span class="sxs-lookup"><span data-stu-id="e8bd2-148">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="e8bd2-149">配信ステータス</span><span class="sxs-lookup"><span data-stu-id="e8bd2-149">Delivery status</span></span>

<span data-ttu-id="e8bd2-150">**すべて**が選択されている既定値のままにすることができますか、結果をフィルター処理するのには次の値のいずれかを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-150">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="e8bd2-151">**配信済み**: メッセージが正常に目的の宛先に配信します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-151">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="e8bd2-152">**保留中**: メッセージの配信がされているしようとしましたまたは再実行しようとします。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-152">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="e8bd2-153">**展開**: 配布グループの受信者のグループの個々 のメンバーに配信する前に展開します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-153">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="e8bd2-154">**失敗しました**: メッセージが配信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-154">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="e8bd2-p113">**検疫**: (スパム、迷惑メール、フィッシング詐欺と)、メッセージが検疫されました。詳細については、 [Office 365 で電子メール メッセージの検疫](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p113">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing). For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).</span></span>

- <span data-ttu-id="e8bd2-157">**スパムとしてフィルター条件**: メッセージが、迷惑メールを識別し、拒否されたりブロック (検疫ではありません)。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-157">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="e8bd2-p114">**状態の取得:**、Office 365 でメッセージを受信した最近ですが、他の状態まだデータはありません。数分後に再度確認してください。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p114">**Getting status:** The message was recently received by Office 365, but no other status data is yet available. Check back in a few minutes.</span></span>

<span data-ttu-id="e8bd2-p115">**注**:**保留中、** **検疫**、および**迷惑メール フィルター**の値は検索に使用できる 10 日以内。また、可能性があります 5 ~ 10 分の遅延配信の実績と報告された状態の間。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p115">**Note**: The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days. Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="e8bd2-162">メッセージ ID</span><span class="sxs-lookup"><span data-stu-id="e8bd2-162">Message ID</span></span>

<span data-ttu-id="e8bd2-p116">内にあるインターネット メッセージ ID (クライアント ID とも呼ばれます) は、**メッセージ ID:** 、メッセージ ヘッダーのヘッダー フィールド。ユーザーでことができます、特定のメッセージを調査するには、この値を提供します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p116">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header. Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="e8bd2-p117">メッセージの有効期間の値が定数です。Office 365 または Exchange で作成されたメッセージは、値の形式で`<GUID@ServerFQDN>`、山かっこを含む (\< \>)。たとえば、 `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。他のメッセージング システムには、さまざまな構文または値を使用できます。この値は、一意であるはずですが、すべての電子メール システムがこの要件に従わない。場合、**メッセージ ID:** 、ヘッダー フィールドが存在しないか、外部ソースから受信したメッセージの場合は空白では、任意の値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p117">This value is constant for the lifetime of the message. For messages created in Office 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>). For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Other messaging systems might use different syntax or values. This value is supposed to be unique, but not all email systems strictly follow this requirement. If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="e8bd2-171">結果をフィルター処理する**メッセージの ID**を使用すると、山かっこを含む完全な文字列を含めることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-171">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="e8bd2-172">Direction</span><span class="sxs-lookup"><span data-stu-id="e8bd2-172">Direction</span></span>

<span data-ttu-id="e8bd2-173">**すべて**が選択されている既定値のままにすることができますまたは**受信**(メッセージは、組織内の受信者に送信される) または**送信**(メッセージは、組織内のユーザーから送信される) を選択することができます、結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-173">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="e8bd2-174">元のクライアント IP アドレス</span><span class="sxs-lookup"><span data-stu-id="e8bd2-174">Original client IP address</span></span>

<span data-ttu-id="e8bd2-p118">できますファイラー結果大量のスパムやマルウェアを送信するコンピューターのハッキングを調査するのにはクライアントの IP アドレス。複数の送信者からのメッセージが表示される、すべてのメッセージを同じコンピューターで生成が可能性が高いです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p118">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware. Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

<span data-ttu-id="e8bd2-177">**注**: クライアントの IP アドレスの情報のみ利用可能時間が、10 日は**拡張の概要**または**拡張**のレポート (ダウンロード可能な CSV ファイル) でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-177">**Note**: The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="e8bd2-178">レポートの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-178">Choose report type</span></span>

<span data-ttu-id="e8bd2-179">使用可能なレポートの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-179">The available report types are:</span></span>

- <span data-ttu-id="e8bd2-p119">**概要**: 時間範囲は、10 日未満であり、追加のフィルタ オプションを必要としない場合に使用します。結果は、**検索**をクリックした後すぐに使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p119">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options. The results are available almost immediately after you click **Search**.</span></span>

- <span data-ttu-id="e8bd2-p120">**概要拡張**または**拡張**: これらのレポートのみダウンロード可能な CSV ファイルとしては、使用期間に関係なく次のフィルター オプションのいずれかを必要とする:**これらの人々 によって\*\*\*\*これらの人々 に**、または**メッセージ ID**。送信者または受信者のワイルドカードを使用することができます (たとえば、 \*@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p120">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**. You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span>

<span data-ttu-id="e8bd2-184">**注**:</span><span class="sxs-lookup"><span data-stu-id="e8bd2-184">**Notes**:</span></span>

- <span data-ttu-id="e8bd2-p121">強化の概要と拡張のレポートは、アーカイブされたメッセージのトレース データを使用する準備が、レポートがダウンロード用に提供する前にいくつかの時間かかることができます。同時にレポートの提出依頼も送信、他の多くの管理者によって可能性がありますも待ち時間が発生する、キューに入れられた要求の処理が開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p121">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download. Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>

- <span data-ttu-id="e8bd2-187">選択することができます拡張サマリーまたは拡張されたレポートのいずれかの日付と時刻の範囲、よくアーカイブ ・ データの最後の 4 時間は表示されませんはまだこれら 2 種類のレポートに使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-187">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="e8bd2-p122">**次へ**] をクリックすると、概要ページで、選択したフィルターのオプションを一覧表示するレポート、およびメッセージのトレースが完了すると (また、編集可能な通知を受信する電子メール アドレスの固有の (編集可能) タイトルを表示します。組織の承認済みドメインのいずれかである必要があります)。メッセージ トレースを送信する**準備のレポート**をクリックします。メイン [**メッセージ トレース**] ページで、**レポートをダウンロード可能なフォント**のセクションで、レポートの状態を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p122">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains). Click **Prepare report** to submit the message trace. On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="e8bd2-191">異なるレポートの種類で返される情報の詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-191">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="e8bd2-192">メッセージ トレースの結果</span><span class="sxs-lookup"><span data-stu-id="e8bd2-192">Message trace results</span></span>

<span data-ttu-id="e8bd2-p123">異なるレポートの種類は、異なるレベルの情報を返します。さまざまなレポートで使用可能な情報については、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p123">The different report types return different levels of information. The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="e8bd2-195">サマリー レポートの出力</span><span class="sxs-lookup"><span data-stu-id="e8bd2-195">Summary report output</span></span>

<span data-ttu-id="e8bd2-196">メッセージ トレースを実行すると、(最新順) の日付と時刻の降順で並べ替えられて、結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-196">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![セキュリティ & コンプライアンス センターでのメッセージのトレースの概要レポートの結果](media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="e8bd2-198">サマリー レポートには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-198">The summary report contains the following information:</span></span>

- <span data-ttu-id="e8bd2-199">**日付**: 日付と時刻が設定されている UTC タイム ゾーンを使用して、サービスによってメッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-199">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="e8bd2-200">**送信者**: 送信者の電子メール アドレス (*別名*@*ドメイン*)。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-200">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="e8bd2-p124">**宛先**: 受信者の電子メール アドレスです。複数の受信者に送信されたメッセージは、受信者ごとに 1 行があります。受信者が配布グループ、動的配布グループ、またはメールが有効なセキュリティ グループの場合は、グループが最初の受信者になり、グループの各メンバーが別々 の行には、します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p124">**Recipient**: The email address of the recipient or recipients. For a message sent to multiple recipients, there's one line per recipient. If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="e8bd2-204">**件名**: メッセージの最初の 256 文字**件名:** フィールドです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-204">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="e8bd2-205">**状態**: これらの値は、[配信状態](#delivery-status)] セクションに記載されています。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-205">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="e8bd2-p125">既定では、250 の最初の結果は、読み込まれるとすぐに利用できます。下にスクロールするときは少し時間の結果の次のバッチで読み込まれますです。スクロールするには、最大で 10,000 の結果のすべてをロードする**すべてを読み込む**のをクリックできます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p125">By default, the first 250 results are loaded and readily available. When you scroll down, there's a slight pause as the next batch of results are loaded. Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="e8bd2-209">昇順または降順の列の値で結果を並べ替えるには列見出しをクリックすることができます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-209">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="e8bd2-210">1 つまたは複数の列によって結果をフィルター処理する**フィルターの結果**をクリックすることができます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-210">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="e8bd2-211">**結果のエクスポート**] をクリックし、**すべての結果をエクスポートする**、**エクスポートの結果をロードする**か、**選択項目をエクスポート**を選択し、1 つまたは複数の行を選択した後、結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-211">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="e8bd2-212">このメッセージに関連するレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-212">Find related records for this message</span></span>

<span data-ttu-id="e8bd2-p126">関連メッセージのレコードは、同じメッセージ ID を共有するレコード2 人の間で送信される 1 つのメッセージは、複数のレコードを生成できることを忘れないでください。メッセージが配布グループの展開、転送、メール フロー ルール (トランスポート ルールでとも呼ばれます) などの影響を受ける場合、レコードの数が増加します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p126">Related message records are records that shared the same Message ID. Remember, even a single message sent between two people can generate multiple records. The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="e8bd2-216">行のチェック ボックスをオンにすると、レコードを検索できます関連メッセージの**検索関連**のボタンが表示されたらをクリックすると、または**その他のオプション**を選択することによって![詳細](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **このメッセージに関連するレコードを検索**)。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-216">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="e8bd2-217">メッセージ ID の詳細については、このトピックで前述したメッセージ ID を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-217">For more information about the Message ID, see the Message ID section earlier in this topic.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="e8bd2-218">メッセージ トレースの詳細</span><span class="sxs-lookup"><span data-stu-id="e8bd2-218">Message trace details</span></span>

<span data-ttu-id="e8bd2-219">サマリー レポート出力は、次の方法のいずれかの方法を使用してメッセージに関する詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-219">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="e8bd2-220">(チェック ボックスを除く行内の任意の場所] をクリック) の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-220">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="e8bd2-221">行のチェック ボックスをオンにし、**他のオプション**をクリックして![詳細](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **メッセージの詳細を表示**します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-221">Select the row's check box and click **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![セキュリティ & コンプライアンス センターの概要のレポート メッセージ トレースの結果の行をダブルクリックすると詳細情報](media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="e8bd2-223">メッセージ トレースの詳細には、サマリー レポートには次のような追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-223">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="e8bd2-p127">**メッセージ イベント**: このセクションには、メッセージに、サービスの動作を分類するための分類が含まれています。発生する可能性がさらに興味深いイベントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p127">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages. Some of the more interesting events that you might encounter are:</span></span>

   - <span data-ttu-id="e8bd2-226">**受信**: サービスがメッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-226">**Receive**: The message was received by the service.</span></span>

   - <span data-ttu-id="e8bd2-227">**送信**: メッセージがサービスによって送信されました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-227">**Send**: The message was sent by the service.</span></span>

   - <span data-ttu-id="e8bd2-228">**失敗**: メッセージを配信できませんでした。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-228">**Fail**: The message failed to be delivered.</span></span>

   - <span data-ttu-id="e8bd2-229">**配信**: メッセージがメールボックスに配信されました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-229">**Deliver**: The message was delivered to a mailbox.</span></span>

   - <span data-ttu-id="e8bd2-230">**展開**: 展開された配布グループにメッセージが送信されました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-230">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

   - <span data-ttu-id="e8bd2-231">**転送**: コンテンツ変換、メッセージ受信者の制限、またはエージェントによって受信者が分岐されたメッセージに移動されました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-231">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

   - <span data-ttu-id="e8bd2-232">**遅延**: メッセージの配信が延期され、後で再実行可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-232">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

   - <span data-ttu-id="e8bd2-p128">**解決済み**: メッセージは、Active Directory 検索に基づいて、新しい受信者のアドレスにリダイレクトされました。このような場合、元の受信者のアドレスがのメッセージの配信ステータス メッセージ トレースに別々 の行に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p128">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up. When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

   <span data-ttu-id="e8bd2-235">でも、順調に進んでいればメッセージは正常に配信がメッセージ トレースに複数の**イベント**エントリを生成するに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-235">Note that even an uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>

- <span data-ttu-id="e8bd2-236">**詳細**: このセクションには、以下の詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-236">**More information**: This section contains the following details:</span></span>

   - <span data-ttu-id="e8bd2-p129">**メッセージ ID**: この値は、このトピックで前述した[メッセージ ID](#message-id) ] セクションに記載されています。たとえば、 `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p129">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this topic. For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

   - <span data-ttu-id="e8bd2-239">**[メッセージ サイズ]**</span><span class="sxs-lookup"><span data-stu-id="e8bd2-239">**Message size**</span></span>

   - <span data-ttu-id="e8bd2-p130">**IP**: メッセージを送信したコンピューターの IP アドレスです。オンライン Exchange から送信された送信メッセージに対しては、この値は空白です。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p130">**From IP**: The IP address of the computer that sent the message. For outbound messages sent from Exchange Online, this value is blank.</span></span>

   - <span data-ttu-id="e8bd2-p131">**IP**: IP アドレスまたはアドレスは、サービスがメッセージを配信しようとします。メッセージは、複数の受信者には、これらが表示されます。受信メッセージを Exchange Online に送信される、この値は空白です。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p131">**To IP**: The IP address or addresses where the service attempted to deliver the message. If the message has multiple recipients, these are displayed. For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="e8bd2-245">拡張のサマリー レポート</span><span class="sxs-lookup"><span data-stu-id="e8bd2-245">Enhanced summary reports</span></span>

<span data-ttu-id="e8bd2-p132">(完成した) の拡張サマリ レポートを使用できるは、最初のメッセージのトレースで**レポートをダウンロード可能なフォント**のセクションで利用できます。次の情報は、レポートで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p132">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace. The following information is available in the report:</span></span>

- <span data-ttu-id="e8bd2-248">**origin_timestamp**<sup>\*</sup>: 日付と時刻のメッセージが最初に構成されている UTC タイム ゾーンを使用して、サービスが受信しました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-248">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="e8bd2-249">**sender_address**: 送信者の電子メール アドレス (*別名*@*ドメイン*)。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-249">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="e8bd2-p133">**Recipient_status**: メッセージの受信者への配信のステータス。複数の受信者にメッセージが送信された、する場合が表示されますすべての受信者と、対応するステータスの形式で、それぞれの: \<*メール アドレス*\>##\<*ステータス*\>。例えば：</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p133">**Recipient_status**: The status of the delivery of the message to the recipient. If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>. For example:</span></span>

   - <span data-ttu-id="e8bd2-253">メッセージがサービスによって受信され、目的の宛先に送信された、 **##Receive、送信**を意味します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-253">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

   - <span data-ttu-id="e8bd2-254">**##Receive、失敗**すると、サービスが失敗しました、目的の宛先への配信でメッセージを受信したを意味します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-254">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

   - <span data-ttu-id="e8bd2-255">メッセージがサービスによって受信された、受信者のメールボックスに配信された、 **##Receive、配信**を意味します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-255">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="e8bd2-256">**message_subject**: メッセージの**件名**フィールドの最初の 256 文字です。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-256">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="e8bd2-257">**total_bytes**: 添付ファイルを含むバイト数で、メッセージのサイズ。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-257">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="e8bd2-p134">**メッセージ id**: この値は、このトピックで前述した[メッセージ ID](#message-id) ] セクションに記載されています。たとえば、 `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p134">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this topic. For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="e8bd2-p135">**network_message_id**: 一意のメッセージ ID の値の分割または配布グループの拡張のために作成される可能性があるメッセージのすべてのコピーの間で保持されます。値の例は、 `1341ac7b13fb42ab4d4408cf7f55890f`。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p135">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion. An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="e8bd2-262">**original_client_ip**: 送信者のクライアントの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-262">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="e8bd2-263">**方向**: メッセージが受信 (1)、組織に送信されたかどうか、またはかどうかから送信された送信 (2) 組織を示します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-263">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="e8bd2-p136">**connector_id**: 送信元または送信先コネクタの名前です。Exchange Online 内のコネクタの詳細については、 [Office 365 のコネクタを使用してメールの流れを構成する](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p136">**connector_id**: The name of the source or destination connector. For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="e8bd2-266">**delivery_priority**<sup>\*</sup>:**高\*\*\*\*低**、または**通常**の優先度のメッセージが送信されたかどうか。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-266">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="e8bd2-267"><sup>\*</sup>これらのプロパティは、拡張の概要レポートで使用できるのみです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-267"><sup>\*</sup>These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="e8bd2-268">拡張レポート</span><span class="sxs-lookup"><span data-stu-id="e8bd2-268">Extended reports</span></span>

<span data-ttu-id="e8bd2-p137">利用可能な (完成した) 拡張レポートは、メッセージ トレースの先頭に、**ダウンロード可能なフォントのレポート**セクションで利用できます。拡張のサマリー レポートの情報のほぼすべては、( **origin_timestamp**および**delivery_priority**) を除いて拡張のレポートで使用できます。次の追加情報は、拡張のレポートで使用可能なのみ。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p137">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace. Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**). The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="e8bd2-272">**client_ip**: 電子メール サーバーまたはメッセージを送信するメッセージング クライアントの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-272">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="e8bd2-273">**client_hostname**: ホストの名前または電子メール サーバーまたはメッセージを送信するメッセージング クライアントの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-273">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="e8bd2-274">**server_ip**: 送信元または送信先のサーバーの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-274">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="e8bd2-275">**server_hostname**: ホスト名または送信先サーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-275">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="e8bd2-p138">**source_context**: [**ソース**] フィールドに関連付けられた追加情報。例えば：</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p138">**source_context**: Extra information associated with the **source** field. For example:</span></span>

   - `Protocol Filter Agent`

   - `3489061114359050000`

- <span data-ttu-id="e8bd2-p139">**ソース**: イベントを担当する Exchange Online のコンポーネントです。例えば：</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p139">**source**: The Exchange Online component that's responsible for the event. For example:</span></span>

   - `AGENT`

   - `MAILBOXRULE`

   - `SMTP`

- <span data-ttu-id="e8bd2-280">**event_id**: これらは、[このメッセージに関連するレコードの検索](#find-related-records-for-this-message)のセクションで説明する**メッセージ イベント**の値に対応しています。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-280">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="e8bd2-281">**internal_message_id**: メッセージを現在処理しているオンラインの Exchange サーバーによって割り当てられているメッセージの識別子です。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-281">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="e8bd2-p140">**recipient_address**: メッセージの受信者の電子メール アドレスです。複数の電子メール アドレスは、セミコロン (;) で区切られます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p140">**recipient_address**: The email addresses of the message's recipients. Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="e8bd2-284">**recipient_count**: メッセージ内の受信者の合計数です。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-284">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="e8bd2-285">**related_recipient_address**: で使用される`EXPAND`、`REDIRECT`と`RESOLVE`その他の受信者を表示するイベント メッセージに関連付けられているアドレスを電子メールで送信します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-285">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="e8bd2-p141">**参照**: このフィールドには、特定の種類のイベントに関する追加情報が含まれています。例えば：</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p141">**reference**: This field contains additional information for specific types of events. For example:</span></span>

   - <span data-ttu-id="e8bd2-p142">**DSN**: このイベントの後に、DSN が生成された場合は、関連付けられている配信状態通知 (とも呼ばれる DSN、配信不能レポート、NDR、またはバウンス メッセージ) の**メッセージ id**の値をレポートのリンクが含まれています。DSN メッセージの場合は、このフィールドには、DSN が生成された元のメッセージの**メッセージ id**の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p142">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event. If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

   - <span data-ttu-id="e8bd2-290">**展開**: 関連するメッセージの**related_recipient_address**の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-290">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

   - <span data-ttu-id="e8bd2-291">**受信**: メッセージは、他のプロセス (たとえば、受信トレイ ルール) が生成した場合、関連するメッセージの**メッセージ id**の値が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-291">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

   - <span data-ttu-id="e8bd2-292">**送信**: すべての DSN メッセージの**internal_message_id**の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-292">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

   - <span data-ttu-id="e8bd2-293">**転送**: **internal_message_id**の値 (たとえば、コンテンツ変換、メッセージ受信者の制限、またはエージェント) を分割するメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-293">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

   - <span data-ttu-id="e8bd2-294">**MAILBOXRULE**: 送信メッセージを生成する受信トレイ ルールの原因となった受信メッセージの**internal_message_id**の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-294">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

   <span data-ttu-id="e8bd2-295">その他の種類のイベントの場合、このフィールドは通常空白です。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-295">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="e8bd2-p143">**return_path**: メッセージを送信した**MAIL FROM**コマンドで指定されているリターン電子メール アドレスです。として表される null 送信者アドレスの値を持つことができますが、このフィールドが空ではありません、 `<>`。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p143">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message. Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="e8bd2-p144">**message_info**: メッセージに関する追加情報です。例えば：</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p144">**message_info**: Additional information about the message. For example:</span></span>

   - <span data-ttu-id="e8bd2-p145">メッセージの発信日付・時刻を UTC に`DELIVER`と`SEND`のイベントです。供給元の日付と時刻は、Exchange Online 組織が最初に入力メッセージと時間です。UTC の日付と時刻が ISO 8601 形式の日付と時刻の形式で表される: `yyyy-mm-ddThh:mm:ss.fffZ`、どこで`yyyy`= 年、 `mm` = 月、 `dd` = 日、 `T` 、時刻要素の開始を示します`hh`= 1 時間、 `mm` = 1 分、 `ss` = 1 秒、 `fff`、秒の端数を = と`Z`を示します`Zulu`、UTC を表すために別の方法であります。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p145">The message origination date-time in UTC for `DELIVER` and `SEND` events. The origination date-time is the time when the message first entered the Exchange Online organization. The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

   - <span data-ttu-id="e8bd2-p146">認証エラーです。値が表示ことがありますたとえば、`11a`と認証エラーが発生したときに使用された認証の種類です。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p146">Authentication errors. For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="e8bd2-305">**tenant_id**: オンラインの Exchange 組織を表す GUID 値 (たとえば、 `39238e87-b5ab-4ef6-a559-af54c6b07b42`)。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-305">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="e8bd2-306">**original_server_ip**: 元のサーバーの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-306">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="e8bd2-p147">**custom_data**: 特定のイベントの種類に関連するデータが含まれています。詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p147">**custom_data**: Contains data related to specific event types. For more information, see the following sections.</span></span>

#### <a name="customdata-values"></a><span data-ttu-id="e8bd2-309">custom_data 値</span><span class="sxs-lookup"><span data-stu-id="e8bd2-309">custom_data values</span></span>

<span data-ttu-id="e8bd2-p148">**Custom_data**フィールド、`AGENTINFO`イベントは、メッセージ処理の詳細をログに記録するさまざまな Exchange Online のエージェントによって使用されます。さらに興味深いエージェントのいくつかについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p148">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details. Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="e8bd2-312">スパム フィルター エージェント</span><span class="sxs-lookup"><span data-stu-id="e8bd2-312">Spam filter agent</span></span>

<span data-ttu-id="e8bd2-p149">**Custom_data**の値で始まる`S:SFA`は、スパム フィルター エージェントからです。キーの詳細は、次の表のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p149">A **custom_data** value that starts with `S:SFA` is from the spam filter agent. The key details are described in the following table:</span></span>

|<span data-ttu-id="e8bd2-315">**値**</span><span class="sxs-lookup"><span data-stu-id="e8bd2-315">**Value**</span></span>|<span data-ttu-id="e8bd2-316">**説明**</span><span class="sxs-lookup"><span data-stu-id="e8bd2-316">**Description**</span></span>|
|:-----|:-----|
|`SFV=NSPM`|<span data-ttu-id="e8bd2-317">メッセージがスパムではないとしてマークされ、意図された受信者に送信されました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-317">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="e8bd2-318">コンテンツ フィルターによって、メッセージがスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-318">The message was marked as spam by the content filter.</span></span>|
|`SFV=BLK`|<span data-ttu-id="e8bd2-319">ブロックする差出人から発信されたメッセージであるため、フィルター処理が省略され、メッセージはブロックされました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-319">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="e8bd2-p150">コンテンツ フィルターによって処理される前に、メッセージがスパムとしてマークされました。これには、メッセージを自動的にスパムとしてマークし、他のすべてのフィルター処理を省略するトランスポート ルールに適合したメッセージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p150">The message was marked as spam prior to being processed by the content filter. This includes messages where the message matched a Transport rule to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="e8bd2-322">さまざまな SCL の値とその意味の詳細については、「[Spam Confidence Level](https://technet.microsoft.com/library/jj200686.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-322">For more information about the different SCL values and what they mean, see [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`PCL=<number>`|<span data-ttu-id="e8bd2-p151">メッセージの Phishing Confidence Level (PCL) 値。これらの値は、「[Spam Confidence Level](https://technet.microsoft.com/library/jj200686.aspx)」に記載されている SCL 値と同様に解釈できます。  </span><span class="sxs-lookup"><span data-stu-id="e8bd2-p151">The Phishing Confidence Level (PCL) value of the message. These can be interpreted the same way as the SCL values documented in [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`DI=SB`|<span data-ttu-id="e8bd2-325">メッセージの送信者はブロックされました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-325">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="e8bd2-326">メッセージは検疫されました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-326">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="e8bd2-327">メッセージは削除されました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-327">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="e8bd2-328">メッセージは受信者の迷惑メール フォルダーに送信されました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-328">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="e8bd2-p152">高リスク配信プールを通じてメッセージがルーティングされました。詳細については、[送信メッセージの危険度の高い配信プール](https://technet.microsoft.com/library/jj200746.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p152">The message was routed through the higher risk delivery pool. For more information, see [High-risk delivery pool for outbound messages](https://technet.microsoft.com/library/jj200746.aspx).</span></span>|
|`DI=SO`|<span data-ttu-id="e8bd2-331">メッセージは通常の送信用の配信プールを通じて送信されました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-331">The message was routed through the normal outbound delivery pool.</span></span>|
|<span data-ttu-id="e8bd2-332">' SFS = []</span><span class="sxs-lookup"><span data-stu-id="e8bd2-332">\`SFS=[a]</span></span>|<span data-ttu-id="e8bd2-333">SFS = [b]'</span><span class="sxs-lookup"><span data-stu-id="e8bd2-333">SFS=[b]\`</span></span>|<span data-ttu-id="e8bd2-334">これはスパム ルールが一致したことを示します。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-334">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="e8bd2-335">このメッセージの IP アドレスは接続フィルターの IP 許可一覧に指定されているため、スパム フィルターの通過を許可されました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-335">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="e8bd2-336">接続するメール ・ サーバの helo コマンドまたは EHLO 文字列です。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-336">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="e8bd2-337">送信元の IP アドレスの PTR レコード (逆引き DNS アドレスともいう) です。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-337">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|

<span data-ttu-id="e8bd2-338">このような迷惑メールのフィルター処理されたメッセージの例の**custom_data**値:</span><span class="sxs-lookup"><span data-stu-id="e8bd2-338">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="e8bd2-339">マルウェア フィルター エージェント</span><span class="sxs-lookup"><span data-stu-id="e8bd2-339">Malware filter agent</span></span>

<span data-ttu-id="e8bd2-p153">**Custom_data**の値で始まる`S:AMA`は、マルウェアのフィルター エージェントからです。キーの詳細は、次の表のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p153">A **custom_data** value that starts with `S:AMA` is from the malware filter agent. The key details are described in the following table:</span></span>

|<span data-ttu-id="e8bd2-342">**値**</span><span class="sxs-lookup"><span data-stu-id="e8bd2-342">**Value**</span></span>|<span data-ttu-id="e8bd2-343">**説明**</span><span class="sxs-lookup"><span data-stu-id="e8bd2-343">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e8bd2-344">' AMA = 合計</span><span class="sxs-lookup"><span data-stu-id="e8bd2-344">\`AMA=SUM</span></span>|<span data-ttu-id="e8bd2-345">v=1</span><span class="sxs-lookup"><span data-stu-id="e8bd2-345">v=1</span></span>|<span data-ttu-id="e8bd2-346">` or `AMA=EV</span><span class="sxs-lookup"><span data-stu-id="e8bd2-346">` or `AMA=EV</span></span>|<span data-ttu-id="e8bd2-347">v = 1'</span><span class="sxs-lookup"><span data-stu-id="e8bd2-347">v=1\`</span></span>|<span data-ttu-id="e8bd2-p154">メッセージは、マルウェアが含まれていると判断されました。`SUM`エンジンによって、マルウェアが検出された可能性がありますしたことを示します。`EV` 、マルウェアは、特定のエンジンによって検出されたことを示します。マルウェアが検出された場合、エンジンによって後続のアクションをトリガーこの。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p154">The message was determined to contain malware. `SUM` indicates the malware could've been detected by any number of engines. `EV` indicates the malware was detected by a specific engine. When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="e8bd2-352">メッセージは置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-352">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="e8bd2-353">メッセージはバイパスされました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-353">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="e8bd2-354">メッセージは延期されました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-354">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="e8bd2-355">メッセージは削除されました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-355">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="e8bd2-356">メッセージはバイパスされました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-356">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="e8bd2-357">メッセージはバイパスされました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-357">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="e8bd2-358">メッセージは拒否されました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-358">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="e8bd2-359">メッセージは拒否されました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-359">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="e8bd2-360">メッセージはブロックされました。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-360">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="e8bd2-361">検出されたマルウェアの名前。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-361">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="e8bd2-362">マルウェアを含むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-362">The name of the file that contained the malware.</span></span>|

<span data-ttu-id="e8bd2-363">マルウェアを含むメッセージの**custom_data**値の例は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-363">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="e8bd2-364">トランスポート ルール エージェント</span><span class="sxs-lookup"><span data-stu-id="e8bd2-364">Transport rule agent</span></span>

<span data-ttu-id="e8bd2-p155">**Custom_data**の値で始まる`S:TRA`は、メール フロー ルール (トランスポート ルールでとも呼ばれます) のトランスポート ルール エージェントからです。キーの詳細は、次の表のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p155">A **custom_data** value that starts with`S:TRA` is from the transport rule agent for mail flow rules (also known as transport rules). The key details are described in the following table:</span></span>

|<span data-ttu-id="e8bd2-367">**値**</span><span class="sxs-lookup"><span data-stu-id="e8bd2-367">**Value**</span></span>|<span data-ttu-id="e8bd2-368">**説明**</span><span class="sxs-lookup"><span data-stu-id="e8bd2-368">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e8bd2-369">' ETR</span><span class="sxs-lookup"><span data-stu-id="e8bd2-369">\`ETR</span></span>|<span data-ttu-id="e8bd2-370">規則 Id =<guid>\`</span><span class="sxs-lookup"><span data-stu-id="e8bd2-370">ruleId=<guid>\`</span></span>|<span data-ttu-id="e8bd2-371">一致したルールの ID。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-371">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="e8bd2-372">日付と時刻 (utc) のルールの一致が発生したとき。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-372">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="e8bd2-p156">適用されたアクション。使用可能なアクションのリストは、[メール フローの処理では、Exchange オンライン](https://technet.microsoft.com/library/jj919237.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p156">The action that was applied. For a list of available actions, see [Mail flow rule actions in Exchange Online](https://technet.microsoft.com/library/jj919237.aspx).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="e8bd2-p157">ルールのモードです。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-p157">The mode of the rule. Valid values are: </span></span><br/><span data-ttu-id="e8bd2-377">•**適用**: すべてのアクションをルールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-377">• **Enforce**: All actions on the rule will be enforced.</span></span> <br/><span data-ttu-id="e8bd2-378">•**ポリシー ヒントを使用してテスト:**: アクションのいずれかのポリシーのヒントを送信するが、他の強制操作に影響しません。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-378">• **Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span> <br/><span data-ttu-id="e8bd2-379">•**ポリシー ヒントなしのテスト**: アクションのログ ファイルの一覧が表示されますが、何らかの方法で送信者に通知されませんし強制操作に影響しません。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-379">• **Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span>|

<span data-ttu-id="e8bd2-380">(例**custom_data** ) の値をメッセージのメール フロー ルールの条件に一致する次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e8bd2-380">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
