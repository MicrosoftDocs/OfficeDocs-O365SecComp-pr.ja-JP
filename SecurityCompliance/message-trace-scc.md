---
title: セキュリティ/コンプライアンス センター のメッセージ追跡
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
description: 管理者は、セキュリティ & コンプライアンスセンターのメッセージ追跡を使用して、メッセージに何が起こったかを確認できます。
ms.openlocfilehash: af3739174203d7c8d81086a5bf7d036bc2bdd76f
ms.sourcegitcommit: 73dcdafb15b462223d1a670c781db260eb73c2f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "36048219"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="19779-103">セキュリティ/コンプライアンス センター のメッセージ追跡</span><span class="sxs-lookup"><span data-stu-id="19779-103">Message trace in the Security & Compliance Center</span></span>

## <a name="overview"></a><span data-ttu-id="19779-104">概要</span><span class="sxs-lookup"><span data-stu-id="19779-104">Overview</span></span>

<span data-ttu-id="19779-105">セキュリティ & コンプライアンスセンターのメッセージ追跡は、Exchange Online 組織を通過する電子メールメッセージに従います。</span><span class="sxs-lookup"><span data-stu-id="19779-105">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="19779-106">メッセージがサービスによって受信、拒否、延期、または配信されたかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="19779-106">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="19779-107">メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。</span><span class="sxs-lookup"><span data-stu-id="19779-107">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="19779-108">セキュリティ & コンプライアンスセンターのメッセージ追跡は、Exchange 管理センター (EAC) で使用可能だったメッセージ追跡によって改善されています。</span><span class="sxs-lookup"><span data-stu-id="19779-108">Message trace in the Security & Compliance Center improves upon message trace that was available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="19779-109">メッセージ追跡からの情報を使用して、メッセージに何が起こったか、メールフローの問題のトラブルシューティング、およびポリシーの変更の検証について、ユーザーからの質問に効率よく回答することができます。</span><span class="sxs-lookup"><span data-stu-id="19779-109">You can use the information from message trace to efficiently answer user questions about what happened to their messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
> <span data-ttu-id="19779-110">返されるメッセージの量の制限は5万です。</span><span class="sxs-lookup"><span data-stu-id="19779-110">The limit for the amount of messages returned is 50,000.</span></span> <span data-ttu-id="19779-111">コンソールで非常に大きなクエリを実行している場合、Start-historicalsearch コマンドレットレポートメッセージ数が24万を超えています。</span><span class="sxs-lookup"><span data-stu-id="19779-111">In the console, when running a very large query, the Get-HistoricalSearch cmdlet report message count exceeds 240,000.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="19779-112">メッセージ追跡を開く</span><span class="sxs-lookup"><span data-stu-id="19779-112">Open message trace</span></span>

1. <span data-ttu-id="19779-113">職場や学校のアカウントで [Office 365 にサインインします](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="19779-113">[Sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="19779-114">左上のアプリ起動ツールのアイコン ![Office 365 アプリ起動ツール アイコン](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) を選び、[ **管理者**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="19779-114">Select the app launcher icon ![Office 365 app launcher icon](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="19779-115">左下のナビゲーションで、[**管理センター** ] を展開し、[**セキュリティ & コンプライアンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19779-115">In the lower-left navigation, expand **Admin centers** and select **Security & Compliance**.</span></span>

4. <span data-ttu-id="19779-116">表示される [**セキュリティ & コンプライアンス**] ページで、[**メールフロー**] を展開して、[**メッセージの追跡**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19779-116">In the **Security & Compliance** page that opens, expand **Mail flow**, and select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="19779-117">メッセージ追跡ページ</span><span class="sxs-lookup"><span data-stu-id="19779-117">Message trace page</span></span>

<span data-ttu-id="19779-118">[**トレースの開始**] ボタンをクリックすると、新しい既定のトレースを開始できます。</span><span class="sxs-lookup"><span data-stu-id="19779-118">From here you can start a new default trace by clicking on the **Start a trace** button.</span></span> <span data-ttu-id="19779-119">これにより、すべての送信者と受信者について、過去2日間のすべてのメッセージが検索されます。</span><span class="sxs-lookup"><span data-stu-id="19779-119">This will search for all messages for all senders and recipients for the last two days.</span></span> <span data-ttu-id="19779-120">または、使用可能なクエリカテゴリから、保存されているクエリのいずれかを使用して、それをで実行するか、独自のクエリの開始点として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="19779-120">Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="19779-121">**既定のクエリ**: Office 365 で提供される組み込みクエリ。</span><span class="sxs-lookup"><span data-stu-id="19779-121">**Default queries**: Built-in queries provided by Office 365.</span></span>

- <span data-ttu-id="19779-122">**カスタムクエリ**: 今後の使用のために組織内の管理者によって保存されたクエリ。</span><span class="sxs-lookup"><span data-stu-id="19779-122">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="19779-123">**自動保存クエリ**: 最後に実行された最後の10個のクエリ。</span><span class="sxs-lookup"><span data-stu-id="19779-123">**Autosaved queries**: The last ten most recently run queries.</span></span> <span data-ttu-id="19779-124">このリストにより、中断したところから簡単に選択できます。</span><span class="sxs-lookup"><span data-stu-id="19779-124">This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="19779-125">また、このページには、提出した要求のダウンロード可能な**レポート**セクションと、ダウンロードが可能な場合にレポート自体も表示されます。</span><span class="sxs-lookup"><span data-stu-id="19779-125">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="19779-126">新しいメッセージ追跡のオプション</span><span class="sxs-lookup"><span data-stu-id="19779-126">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="19779-127">送信者と受信者によるフィルター</span><span class="sxs-lookup"><span data-stu-id="19779-127">Filter by senders and recipients</span></span>

<span data-ttu-id="19779-128">既定値は**すべて送信者**と**すべての受信者**ですが、次のフィールドを使用して結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="19779-128">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="19779-129">**これらのユーザーによって**: このフィールドをクリックして、組織から1人以上の送信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="19779-129">**By these people**: Click in this field to select one or more senders from your organization.</span></span> <span data-ttu-id="19779-130">名前の入力を開始することもできます。また、リスト内のアイテムは、検索ページの動作と同じように、入力したものによってフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="19779-130">You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="19779-131">**ユーザーへ**: このフィールドをクリックして、組織内の1人または複数の受信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="19779-131">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="19779-132">外部の送信者と受信者の電子メールアドレスを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="19779-132">You can also type the email addresses of external senders and recipients.</span></span> <span data-ttu-id="19779-133">ワイルドカードはサポート`*@contoso.com`さ`scot?@contoso.com`れていますが、同じフィールドで複数のワイルドカードエントリを同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="19779-133">Wildcards are supported (`*@contoso.com` or `scot?@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span><br/><span data-ttu-id="19779-134">複数の送信者または受信者リストをセミコロン (`;`) で区切って貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="19779-134">You can paste multiple senders or recipients list separated with semicolon (`;`).</span></span> <span data-ttu-id="19779-135">スペース (`\s`)、キャリッジリターン (`\r`)、または次`\n`の行 () 記号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="19779-135">Spaces (`\s`), carriage return (`\r`) or next lines (`\n`) symbols are allowed.</span></span>

### <a name="time-range"></a><span data-ttu-id="19779-136">時間の範囲</span><span class="sxs-lookup"><span data-stu-id="19779-136">Time range</span></span>

<span data-ttu-id="19779-137">既定値は**2 日**ですが、最大90日までの日付/時刻範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="19779-137">The default value is **2 days**, but you can specify date/time ranges of up to 90 days.</span></span> <span data-ttu-id="19779-138">日付/時刻範囲を使用する場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="19779-138">When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="19779-139">既定では、タイムラインを使用して、**スライダー**ビューで時間範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="19779-139">By default, you select the time range in **Slider** view using a time line.</span></span> <span data-ttu-id="19779-140">表示される日時の設定のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="19779-140">You can only select the day or time settings that are displayed.</span></span> <span data-ttu-id="19779-141">[Between] 間の値を選択すると、[開始/終了] のバブルが、最も近い表示設定にスナップされます。</span><span class="sxs-lookup"><span data-stu-id="19779-141">Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

   ![セキュリティ & コンプライアンスセンターでの新しいメッセージ追跡のスライダー時間の範囲](media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

   <span data-ttu-id="19779-143">ただし、[**開始日**] と\*\*\*\* [**終了日**] の値 (時刻を含む) を指定することもできます。また、日付/時刻範囲の**タイムゾーン**を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="19779-143">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range.</span></span> <span data-ttu-id="19779-144">**タイムゾーン**の設定は、クエリの入力とクエリの結果の両方に適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="19779-144">Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

   ![セキュリティ & コンプライアンスセンターでの新しいメッセージ追跡のカスタム時間範囲](media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

   <span data-ttu-id="19779-146">10日間以下の場合、結果はすぐに**概要**レポートとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="19779-146">For 10 days or less, the results are available instantly as a **Summary** report.</span></span> <span data-ttu-id="19779-147">時間の範囲を10日よりも少し長く指定すると、ダウンロード可能な CSV ファイル (拡張された**概要**または**拡張**レポート) としてのみ利用できるため、結果の遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="19779-147">If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

   <span data-ttu-id="19779-148">さまざまなレポートの種類の詳細については、このトピックの「[レポートの種類を選択](#choose-report-type)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19779-148">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this topic.</span></span>

   <span data-ttu-id="19779-149">**注**: 拡張された概要および拡張レポートはアーカイブされたメッセージの追跡データを使用して準備されるため、レポートをダウンロードできるようになるまでに最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="19779-149">**Note**: Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download.</span></span> <span data-ttu-id="19779-150">同時にレポート要求を送信した他の管理者の数によっては、キューに入れられた要求の処理が開始されるまでの時間が長くなることもあります。</span><span class="sxs-lookup"><span data-stu-id="19779-150">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="19779-151">**スライダー**ビューでクエリを保存すると、相対時間範囲 (たとえば、今日から3日間) が保存されます。</span><span class="sxs-lookup"><span data-stu-id="19779-151">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today).</span></span> <span data-ttu-id="19779-152">**ユーザー設定**のビューにクエリを保存すると、絶対日付/時刻範囲 (たとえば、2018-05-06 13:00 ~ 2018-05-08 18:00) が保存されます。</span><span class="sxs-lookup"><span data-stu-id="19779-152">Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="19779-153">その他の検索オプション</span><span class="sxs-lookup"><span data-stu-id="19779-153">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="19779-154">配信状態</span><span class="sxs-lookup"><span data-stu-id="19779-154">Delivery status</span></span>

<span data-ttu-id="19779-155">既定値を**すべて**選択したままにすることも、次のいずれかの値を選択して結果をフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="19779-155">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="19779-156">**配信**済み: メッセージは、意図した宛先に正常に配信されました。</span><span class="sxs-lookup"><span data-stu-id="19779-156">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="19779-157">[**保留中**]: メッセージの配信が試行または再試行されています。</span><span class="sxs-lookup"><span data-stu-id="19779-157">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="19779-158">**拡張**: 配布グループの受信者が、グループの個々のメンバーに配信される前に展開されました。</span><span class="sxs-lookup"><span data-stu-id="19779-158">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="19779-159">**失敗**: メッセージは配信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="19779-159">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="19779-160">**検疫**済み: メッセージが検疫されました (スパム、バルクメール、またはフィッシングとして)。</span><span class="sxs-lookup"><span data-stu-id="19779-160">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing).</span></span> <span data-ttu-id="19779-161">For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).</span><span class="sxs-lookup"><span data-stu-id="19779-161">For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).</span></span>

- <span data-ttu-id="19779-162">**スパムとしてフィルター処理**: メッセージがスパムとして検出され、拒否またはブロックされました (検疫されていません)。</span><span class="sxs-lookup"><span data-stu-id="19779-162">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="19779-163">**状態の取得:** メッセージは Office 365 によって最近受信されましたが、他の状態データはまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="19779-163">**Getting status:** The message was recently received by Office 365, but no other status data is yet available.</span></span> <span data-ttu-id="19779-164">数分後にもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="19779-164">Check back in a few minutes.</span></span>

<span data-ttu-id="19779-165">**注**:**スパムとして\*\*\*\*保留、** **検疫**済み、およびフィルター処理される値は、10日未満の検索でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="19779-165">**Note**: The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days.</span></span> <span data-ttu-id="19779-166">また、実績と報告された配信状態の間に 5 ~ 10 分の遅延が発生することもあります。</span><span class="sxs-lookup"><span data-stu-id="19779-166">Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="19779-167">メッセージ ID</span><span class="sxs-lookup"><span data-stu-id="19779-167">Message ID</span></span>

<span data-ttu-id="19779-168">これは、メッセージヘッダー内の**メッセージ id:** header フィールドに含まれるインターネットメッセージ Id (クライアント ID とも呼ばれます) です。</span><span class="sxs-lookup"><span data-stu-id="19779-168">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header.</span></span> <span data-ttu-id="19779-169">ユーザーはこの値を指定して、特定のメッセージを調査できます。</span><span class="sxs-lookup"><span data-stu-id="19779-169">Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="19779-170">この値は、メッセージの有効期間全体にわたって不変です。</span><span class="sxs-lookup"><span data-stu-id="19779-170">This value is constant for the lifetime of the message.</span></span> <span data-ttu-id="19779-171">Office 365 または Exchange で作成されたメッセージの場合、値`<GUID@ServerFQDN>`は山かっこ (\< \>) を含む形式になります。</span><span class="sxs-lookup"><span data-stu-id="19779-171">For messages created in Office 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>).</span></span> <span data-ttu-id="19779-172">たとえば、`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>` などです。</span><span class="sxs-lookup"><span data-stu-id="19779-172">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span> <span data-ttu-id="19779-173">他のメッセージングシステムでは、異なる構文や値を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="19779-173">Other messaging systems might use different syntax or values.</span></span> <span data-ttu-id="19779-174">この値は一意であると想定されていますが、すべての電子メールシステムがこの要件を厳密に従うわけではありません。</span><span class="sxs-lookup"><span data-stu-id="19779-174">This value is supposed to be unique, but not all email systems strictly follow this requirement.</span></span> <span data-ttu-id="19779-175">**メッセージ ID:** header フィールドが存在しない場合、または外部ソースからの受信メッセージに対して空白の場合は、任意の値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="19779-175">If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="19779-176">**メッセージ ID**を使用して結果をフィルター処理する場合は、山かっこを含む完全な文字列を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="19779-176">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="19779-177">Direction</span><span class="sxs-lookup"><span data-stu-id="19779-177">Direction</span></span>

<span data-ttu-id="19779-178">既定値を**すべて**選択したままにするか、[**受信**(組織内の受信者に送信されるメッセージ)] または [**送信**] (組織内のユーザーから送信されるメッセージ) を選択して結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="19779-178">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="19779-179">元のクライアント IP アドレス</span><span class="sxs-lookup"><span data-stu-id="19779-179">Original client IP address</span></span>

<span data-ttu-id="19779-180">クライアント IP アドレスによって結果をフィルターして、大量のスパムまたはマルウェアを送信しているハッキングされたコンピューターを調査できます。</span><span class="sxs-lookup"><span data-stu-id="19779-180">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware.</span></span> <span data-ttu-id="19779-181">メッセージは複数の送信者から送信されているように見えますが、同じコンピューターがすべてのメッセージを生成している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19779-181">Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

<span data-ttu-id="19779-182">**注**: クライアント IP アドレス情報は10日間のみ利用可能であり、拡張された**概要**または**拡張**レポート (ダウンロード可能な CSV ファイル) でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="19779-182">**Note**: The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="19779-183">レポートの種類を選択する</span><span class="sxs-lookup"><span data-stu-id="19779-183">Choose report type</span></span>

<span data-ttu-id="19779-184">使用可能なレポートの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="19779-184">The available report types are:</span></span>

- <span data-ttu-id="19779-185">**概要**: 時間範囲が10日未満の場合に使用できます。これには、追加のフィルターオプションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="19779-185">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options.</span></span> <span data-ttu-id="19779-186">[**検索**] をクリックすると、ほぼ瞬時に結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="19779-186">The results are available almost immediately after you click **Search**.</span></span>

- <span data-ttu-id="19779-187">拡張された**概要**または**拡張**: これらのレポートはダウンロード可能な CSV ファイルとしてのみ利用可能であり、時間範囲に関係\*\*\*\* なく、次の\*\*\*\* フィルターオプションの1つ以上を必要とします。これらのユーザーには、これらのユーザー、または**メッセージ ID**。</span><span class="sxs-lookup"><span data-stu-id="19779-187">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**.</span></span> <span data-ttu-id="19779-188">送信者または受信者に対してワイルドカードを使用できます\*(たとえば、@contoso .com)。</span><span class="sxs-lookup"><span data-stu-id="19779-188">You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span>

<span data-ttu-id="19779-189">**注**:</span><span class="sxs-lookup"><span data-stu-id="19779-189">**Notes**:</span></span>

- <span data-ttu-id="19779-190">拡張された概要および拡張レポートは、アーカイブされたメッセージの追跡データを使用して準備されるため、レポートをダウンロードできるようになるまでに最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="19779-190">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download.</span></span> <span data-ttu-id="19779-191">同時にレポート要求を送信した他の管理者の数によっては、キュー要求の処理が開始されるまでの時間が長くなることがあります。</span><span class="sxs-lookup"><span data-stu-id="19779-191">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>

- <span data-ttu-id="19779-192">拡張されたサマリーまたは拡張レポートを任意の日付/時刻範囲で選択できますが、通常、アーカイブデータの過去4時間は、これら2種類のレポートでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="19779-192">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="19779-193">[**次へ**] をクリックすると、選択したフィルターオプション、レポートの一意の (編集可能な) タイトル、およびメッセージの追跡が完了したときに通知を受信する電子メールアドレス (編集可能な場合もあります) を一覧表示する概要ページが表示されます。、組織の承認済みドメインのいずれかに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="19779-193">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains).</span></span> <span data-ttu-id="19779-194">[**レポートの準備**] をクリックして、メッセージの追跡を送信します。</span><span class="sxs-lookup"><span data-stu-id="19779-194">Click **Prepare report** to submit the message trace.</span></span> <span data-ttu-id="19779-195">メインの**メッセージ追跡**ページで、[ダウンロード可能な**レポート**] セクションにレポートの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="19779-195">On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="19779-196">さまざまなレポートの種類で返される情報の詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19779-196">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="19779-197">メッセージの追跡結果</span><span class="sxs-lookup"><span data-stu-id="19779-197">Message trace results</span></span>

<span data-ttu-id="19779-198">さまざまなレポートの種類は、さまざまなレベルの情報を返します。</span><span class="sxs-lookup"><span data-stu-id="19779-198">The different report types return different levels of information.</span></span> <span data-ttu-id="19779-199">次のセクションでは、さまざまなレポートで使用できる情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="19779-199">The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="19779-200">概要レポートの出力</span><span class="sxs-lookup"><span data-stu-id="19779-200">Summary report output</span></span>

<span data-ttu-id="19779-201">メッセージ追跡を実行すると、結果が一覧表示され、降順 (最新の日付/時刻) で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="19779-201">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![セキュリティ & コンプライアンスセンターでのメッセージ追跡に関する概要レポートの結果](media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="19779-203">概要レポートには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19779-203">The summary report contains the following information:</span></span>

- <span data-ttu-id="19779-204">**日付**: 構成済みの UTC タイムゾーンを使用して、メッセージがサービスによって受信された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="19779-204">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="19779-205">**Sender**: 送信者の電子メールアドレス (*エイリアス*@*ドメイン*)。</span><span class="sxs-lookup"><span data-stu-id="19779-205">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="19779-206">**Recipient**: 受信者または受信者の電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="19779-206">**Recipient**: The email address of the recipient or recipients.</span></span> <span data-ttu-id="19779-207">複数の受信者に送信されるメッセージの場合、受信者ごとに1つの行があります。</span><span class="sxs-lookup"><span data-stu-id="19779-207">For a message sent to multiple recipients, there's one line per recipient.</span></span> <span data-ttu-id="19779-208">受信者が配布グループ、動的配布グループ、またはメールが有効なセキュリティグループの場合、グループは最初の受信者になり、グループの各メンバーは別の行になります。</span><span class="sxs-lookup"><span data-stu-id="19779-208">If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="19779-209">**Subject**: メッセージの**subject:** フィールドの最初の256文字。</span><span class="sxs-lookup"><span data-stu-id="19779-209">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="19779-210">**状態**: これらの値については、「[配信状態](#delivery-status)」セクションで説明されています。</span><span class="sxs-lookup"><span data-stu-id="19779-210">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="19779-211">既定では、最初の250結果が読み込まれ、すぐに使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="19779-211">By default, the first 250 results are loaded and readily available.</span></span> <span data-ttu-id="19779-212">下にスクロールすると、結果の次のバッチが読み込まれるときに若干の一時停止が発生します。</span><span class="sxs-lookup"><span data-stu-id="19779-212">When you scroll down, there's a slight pause as the next batch of results are loaded.</span></span> <span data-ttu-id="19779-213">スクロールするのではなく、[**すべて読み込み**] をクリックして、最大で1万のすべての結果を読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="19779-213">Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="19779-214">列見出しをクリックすると、その列の値の昇順または降順で結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="19779-214">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="19779-215">[結果の**フィルター** ] をクリックすると、結果を1つまたは複数の列でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="19779-215">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="19779-216">1つまたは複数の行を選択した後に結果をエクスポートするには、[**結果のエクスポート**] をクリックし、[**すべての結果**のエクスポート] または [エクスポート**した\*\*\*\*結果のエクスポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19779-216">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="19779-217">このメッセージの関連レコードを検索する</span><span class="sxs-lookup"><span data-stu-id="19779-217">Find related records for this message</span></span>

<span data-ttu-id="19779-218">関連するメッセージレコードは、同じメッセージ ID を共有しているレコードです。</span><span class="sxs-lookup"><span data-stu-id="19779-218">Related message records are records that shared the same Message ID.</span></span> <span data-ttu-id="19779-219">2人のユーザーの間で送信される1つのメッセージで、複数のレコードを生成できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="19779-219">Remember, even a single message sent between two people can generate multiple records.</span></span> <span data-ttu-id="19779-220">配布グループの展開、転送、メールフロールール (トランスポートルールとも呼ばれます) などによってメッセージが影響を受けると、レコード数が増加します。</span><span class="sxs-lookup"><span data-stu-id="19779-220">The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="19779-221">行のチェックボックスをオンにした後は、表示された [関連レコードの**検索**] ボタンをクリックするか、[**その他** ![](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **の**オプション] を選択することによって、メッセージの関連レコードを検索できます。</span><span class="sxs-lookup"><span data-stu-id="19779-221">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="19779-222">メッセージ ID の詳細については、このトピックで前述した「メッセージ ID」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19779-222">For more information about the Message ID, see the Message ID section earlier in this topic.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="19779-223">メッセージ追跡の詳細</span><span class="sxs-lookup"><span data-stu-id="19779-223">Message trace details</span></span>

<span data-ttu-id="19779-224">概要レポートの出力では、次のいずれかの方法を使用して、メッセージの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="19779-224">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="19779-225">行を選択します (チェックボックス以外の行の任意の場所をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="19779-225">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="19779-226">行のチェックボックスをオンにして、[](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \>その他の**オプション** ![] をクリックします。**メッセージの詳細を表示**します。</span><span class="sxs-lookup"><span data-stu-id="19779-226">Select the row's check box and click **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![概要レポートメッセージ追跡の行をダブルクリックした後の詳細セキュリティ & コンプライアンスセンターの結果](media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="19779-228">メッセージ追跡の詳細には、概要レポートに表示されない次の追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19779-228">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="19779-229">**メッセージイベント**: このセクションには、サービスがメッセージに対して実行するアクションを分類するための分類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19779-229">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages.</span></span> <span data-ttu-id="19779-230">次のようないくつかの興味深いイベントが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="19779-230">Some of the more interesting events that you might encounter are:</span></span>

   - <span data-ttu-id="19779-231">**Receive**: メッセージはサービスによって受信されました。</span><span class="sxs-lookup"><span data-stu-id="19779-231">**Receive**: The message was received by the service.</span></span>

   - <span data-ttu-id="19779-232">**送信**: メッセージはサービスによって送信されました。</span><span class="sxs-lookup"><span data-stu-id="19779-232">**Send**: The message was sent by the service.</span></span>

   - <span data-ttu-id="19779-233">**Fail**: メッセージを配信できませんでした。</span><span class="sxs-lookup"><span data-stu-id="19779-233">**Fail**: The message failed to be delivered.</span></span>

   - <span data-ttu-id="19779-234">**配信**: メッセージがメールボックスに配信されました。</span><span class="sxs-lookup"><span data-stu-id="19779-234">**Deliver**: The message was delivered to a mailbox.</span></span>

   - <span data-ttu-id="19779-235">**Expand**: 展開された配布グループにメッセージが送信されました。</span><span class="sxs-lookup"><span data-stu-id="19779-235">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

   - <span data-ttu-id="19779-236">**転送**: コンテンツ変換、メッセージ受信者の制限、またはエージェントが原因で、受信者が bifurcated メッセージに移動されました。</span><span class="sxs-lookup"><span data-stu-id="19779-236">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

   - <span data-ttu-id="19779-237">**Defer**: メッセージの配信が延期され、後で再試行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19779-237">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

   - <span data-ttu-id="19779-238">**解決済み**: Active Directory に基づいて、メッセージは新しい受信者アドレスにリダイレクトされました。</span><span class="sxs-lookup"><span data-stu-id="19779-238">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up.</span></span> <span data-ttu-id="19779-239">このイベントが発生した場合、メッセージ トレースの別の行に、メッセージの最終配信状態と併せて、元の受信者のアドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19779-239">When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

   <span data-ttu-id="19779-240">書き込まメッセージが正常に配信された場合でも、メッセージ追跡に複数の**イベント**エントリが生成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="19779-240">Note that even an uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>

- <span data-ttu-id="19779-241">**詳細**: このセクションには、次の詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19779-241">**More information**: This section contains the following details:</span></span>

   - <span data-ttu-id="19779-242">[**メッセージ id**]: この値については、このトピックで前述した「[メッセージ id](#message-id) 」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="19779-242">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this topic.</span></span> <span data-ttu-id="19779-243">たとえば、`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>` などです。</span><span class="sxs-lookup"><span data-stu-id="19779-243">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

   - <span data-ttu-id="19779-244">**メッセージ サイズ**   添付ファイルを含むキロバイト (KB) 単位のメッセージのサイズ。</span><span class="sxs-lookup"><span data-stu-id="19779-244">**Message size**</span></span>

   - <span data-ttu-id="19779-245">**FROM ip**: メッセージを送信したコンピューターの ip アドレス。</span><span class="sxs-lookup"><span data-stu-id="19779-245">**From IP**: The IP address of the computer that sent the message.</span></span> <span data-ttu-id="19779-246">Exchange Online から送信された送信メッセージの場合、この値は空白です。</span><span class="sxs-lookup"><span data-stu-id="19779-246">For outbound messages sent from Exchange Online, this value is blank.</span></span>

   - <span data-ttu-id="19779-247">**TO IP**: サービスがメッセージを配信しようとした ip アドレスまたはアドレス。</span><span class="sxs-lookup"><span data-stu-id="19779-247">**To IP**: The IP address or addresses where the service attempted to deliver the message.</span></span> <span data-ttu-id="19779-248">メッセージに複数の受信者が含まれている場合は、それらが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19779-248">If the message has multiple recipients, these are displayed.</span></span> <span data-ttu-id="19779-249">Exchange Online に送信された受信メッセージの場合、この値は空白です。</span><span class="sxs-lookup"><span data-stu-id="19779-249">For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="19779-250">拡張された概要レポート</span><span class="sxs-lookup"><span data-stu-id="19779-250">Enhanced summary reports</span></span>

<span data-ttu-id="19779-251">利用可能 (完了) 強化された概要レポートについては、最初のメッセージ追跡の「ダウンロード可能な**レポート**」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19779-251">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace.</span></span> <span data-ttu-id="19779-252">レポートでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="19779-252">The following information is available in the report:</span></span>

- <span data-ttu-id="19779-253">**origin_timestamp**<sup>\*</sup>: 構成済みの UTC タイムゾーンを使用して、メッセージが最初にサービスによって受信された日時。</span><span class="sxs-lookup"><span data-stu-id="19779-253">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="19779-254">**sender_address**: 送信者の電子メールアドレス (*エイリアス*@*ドメイン*)。</span><span class="sxs-lookup"><span data-stu-id="19779-254">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="19779-255">**Recipient_status**: 受信者へのメッセージの配信状態。</span><span class="sxs-lookup"><span data-stu-id="19779-255">**Recipient_status**: The status of the delivery of the message to the recipient.</span></span> <span data-ttu-id="19779-256">メッセージが複数の受信者に送信された場合は、[ \<*電子メールアドレス*\>##\<の*状態*\>] の形式で、それぞれの受信者と対応するステータスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19779-256">If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>.</span></span> <span data-ttu-id="19779-257">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="19779-257">For example:</span></span>

   - <span data-ttu-id="19779-258">**# #Receive, Send**は、メッセージがサービスによって受信され、意図した宛先に送信されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="19779-258">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

   - <span data-ttu-id="19779-259">**# #Receive、Fail**は、メッセージがサービスによって受信されたが、意図した宛先への配信に失敗したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="19779-259">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

   - <span data-ttu-id="19779-260">**# #Receive 配信**とは、メッセージがサービスによって受信され、受信者のメールボックスに配信されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="19779-260">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="19779-261">**message_subject**: メッセージの**subject**フィールドの最初の256文字。</span><span class="sxs-lookup"><span data-stu-id="19779-261">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="19779-262">**total_bytes**: 添付ファイルを含む、メッセージのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="19779-262">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="19779-263">**message_id**: この値については、このトピックで前述した「[メッセージ id](#message-id) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19779-263">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this topic.</span></span> <span data-ttu-id="19779-264">たとえば、`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>` などです。</span><span class="sxs-lookup"><span data-stu-id="19779-264">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="19779-265">**network_message_id**: 分割または配布グループの展開によって作成される可能性がある、メッセージのすべてのコピーで保持される一意のメッセージ id 値。</span><span class="sxs-lookup"><span data-stu-id="19779-265">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion.</span></span> <span data-ttu-id="19779-266">値の例を`1341ac7b13fb42ab4d4408cf7f55890f`次に示します。</span><span class="sxs-lookup"><span data-stu-id="19779-266">An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="19779-267">**original_client_ip**: 送信者のクライアントの ip アドレス。</span><span class="sxs-lookup"><span data-stu-id="19779-267">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="19779-268">**方向性**: メッセージが組織に受信 (1) 送信されたかどうか、または組織から送信 (2) されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="19779-268">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="19779-269">**connector_id**: 転送元または転送先コネクタの名前。</span><span class="sxs-lookup"><span data-stu-id="19779-269">**connector_id**: The name of the source or destination connector.</span></span> <span data-ttu-id="19779-270">Exchange Online のコネクタの詳細については、「 [Configure mail flow using connector Using Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19779-270">For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="19779-271">**delivery_priority**<sup>\*</sup>: メッセージが**高**、**低**、または**通常**の優先度で送信されたかどうか。</span><span class="sxs-lookup"><span data-stu-id="19779-271">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="19779-272"><sup>\*</sup>これらのプロパティは、拡張された概要レポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="19779-272"><sup>\*</sup>These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="19779-273">拡張レポート</span><span class="sxs-lookup"><span data-stu-id="19779-273">Extended reports</span></span>

<span data-ttu-id="19779-274">利用可能 (完了) された拡張レポートは、メッセージ追跡の先頭にあるダウンロード可能な**レポート**セクションから入手できます。</span><span class="sxs-lookup"><span data-stu-id="19779-274">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace.</span></span> <span data-ttu-id="19779-275">拡張された概要レポートの情報は、ほぼすべて ( **origin_timestamp**と**delivery_priority**を除く) 拡張レポートで利用できます。</span><span class="sxs-lookup"><span data-stu-id="19779-275">Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**).</span></span> <span data-ttu-id="19779-276">次の追加情報は、拡張レポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="19779-276">The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="19779-277">**client_ip**: メッセージを送信した電子メールサーバーまたはメッセージングクライアントの ip アドレス。</span><span class="sxs-lookup"><span data-stu-id="19779-277">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="19779-278">**client_hostname**: メッセージを送信した電子メールサーバーまたはメッセージングクライアントのホスト名または FQDN。</span><span class="sxs-lookup"><span data-stu-id="19779-278">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="19779-279">**server_ip**: 転送元または転送先サーバーの ip アドレス。</span><span class="sxs-lookup"><span data-stu-id="19779-279">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="19779-280">**server_hostname**: 宛先サーバーのホスト名または FQDN。</span><span class="sxs-lookup"><span data-stu-id="19779-280">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="19779-281">**source_context**:**ソース**フィールドに関連付けられている付加情報。</span><span class="sxs-lookup"><span data-stu-id="19779-281">**source_context**: Extra information associated with the **source** field.</span></span> <span data-ttu-id="19779-282">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="19779-282">For example:</span></span>

   - `Protocol Filter Agent`

   - `3489061114359050000`

- <span data-ttu-id="19779-283">**source**: イベントを担当する Exchange Online コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="19779-283">**source**: The Exchange Online component that's responsible for the event.</span></span> <span data-ttu-id="19779-284">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="19779-284">For example:</span></span>

   - `AGENT`

   - `MAILBOXRULE`

   - `SMTP`

- <span data-ttu-id="19779-285">**event_id**: これらは、「[このメッセージの関連レコードを検索](#find-related-records-for-this-message)する」セクションで説明されている**メッセージイベント**値に対応しています。</span><span class="sxs-lookup"><span data-stu-id="19779-285">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="19779-286">**internal_message_id**: 現在メッセージを処理している Exchange Online サーバーによって割り当てられたメッセージ識別子。</span><span class="sxs-lookup"><span data-stu-id="19779-286">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="19779-287">**recipient_address**: メッセージの受信者の電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="19779-287">**recipient_address**: The email addresses of the message's recipients.</span></span> <span data-ttu-id="19779-288">複数の電子メール アドレスがある場合は、セミコロン (;) で区切られます。</span><span class="sxs-lookup"><span data-stu-id="19779-288">Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="19779-289">**recipient_count**: メッセージ内の受信者の合計数。</span><span class="sxs-lookup"><span data-stu-id="19779-289">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="19779-290">**related_recipient_address**:、 `EXPAND` `REDIRECT`、および`RESOLVE`イベントを使用して、メッセージに関連付けられている他の受信者の電子メールアドレスを表示します。</span><span class="sxs-lookup"><span data-stu-id="19779-290">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="19779-291">**参照**: このフィールドには、特定の種類のイベントに関する追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19779-291">**reference**: This field contains additional information for specific types of events.</span></span> <span data-ttu-id="19779-292">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="19779-292">For example:</span></span>

   - <span data-ttu-id="19779-293">**Dsn**: このイベントの後に dsn が生成された場合に、関連付けられている配信状態通知 (dsn、配信不能レポート、NDR、またはバウンスメッセージとも呼ばれる) の**message_id**値であるレポートリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="19779-293">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event.</span></span> <span data-ttu-id="19779-294">これが DSN メッセージの場合、このフィールドには、DSN が生成された元のメッセージの**message_id**値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19779-294">If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

   - <span data-ttu-id="19779-295">**EXPAND**: 関連するメッセージの**related_recipient_address**値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19779-295">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

   - <span data-ttu-id="19779-296">**RECEIVE**: 他のプロセス (たとえば、受信トレイルール) によってメッセージが生成された場合に、関連するメッセージの**message_id**値が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19779-296">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

   - <span data-ttu-id="19779-297">**SEND**: DSN メッセージの**internal_message_id**値を格納します。</span><span class="sxs-lookup"><span data-stu-id="19779-297">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

   - <span data-ttu-id="19779-298">**TRANSFER**: fork されているメッセージの**internal_message_id**値が含まれています (たとえば、コンテンツの変換、メッセージ受信者の制限、エージェント)。</span><span class="sxs-lookup"><span data-stu-id="19779-298">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

   - <span data-ttu-id="19779-299">**MAILBOXRULE**: 受信トレイルールが送信メッセージを生成する原因となった受信メッセージの**internal_message_id**値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19779-299">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

   <span data-ttu-id="19779-300">その他の種類のイベントの場合、このフィールドは通常空白です。</span><span class="sxs-lookup"><span data-stu-id="19779-300">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="19779-301">**return_path**: メッセージを送信した**MAIL FROM**コマンドによって指定された返信電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="19779-301">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message.</span></span> <span data-ttu-id="19779-302">このフィールドは空になることはありませんが、null の送信者アドレス`<>`値をとして表すことができます。</span><span class="sxs-lookup"><span data-stu-id="19779-302">Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="19779-303">**message_info**: メッセージに関する追加情報。</span><span class="sxs-lookup"><span data-stu-id="19779-303">**message_info**: Additional information about the message.</span></span> <span data-ttu-id="19779-304">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="19779-304">For example:</span></span>

   - <span data-ttu-id="19779-305">メッセージの発信元の日付と`DELIVER` `SEND`イベントの UTC の日時。</span><span class="sxs-lookup"><span data-stu-id="19779-305">The message origination date-time in UTC for `DELIVER` and `SEND` events.</span></span> <span data-ttu-id="19779-306">発信日時は、メッセージが最初に Exchange Online 組織に入った時刻です。</span><span class="sxs-lookup"><span data-stu-id="19779-306">The origination date-time is the time when the message first entered the Exchange Online organization.</span></span> <span data-ttu-id="19779-307">UTC の日時は、ISO 8601 の日付と時刻の形式で表され`yyyy-mm-ddThh:mm:ss.fffZ`ます。 `yyyy`ここで、 `mm` = year、 `dd` = month、 `T` = day は、時間コンポーネントの開始`hh`を示し、 `mm` = hour、 `ss` = minute、 `fff` = second、=2番目`Z` `Zulu`の分数は、UTC を示す別の方法です。</span><span class="sxs-lookup"><span data-stu-id="19779-307">The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

   - <span data-ttu-id="19779-308">認証エラー。</span><span class="sxs-lookup"><span data-stu-id="19779-308">Authentication errors.</span></span> <span data-ttu-id="19779-309">たとえば、認証エラーが発生した`11a`ときに使用された認証の値と種類が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="19779-309">For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="19779-310">**tenant_id**: Exchange Online 組織を表す GUID 値 (例: `39238e87-b5ab-4ef6-a559-af54c6b07b42`)。</span><span class="sxs-lookup"><span data-stu-id="19779-310">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="19779-311">**original_server_ip**: 元のサーバーの ip アドレス。</span><span class="sxs-lookup"><span data-stu-id="19779-311">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="19779-312">**custom_data**: 特定のイベントの種類に関連するデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="19779-312">**custom_data**: Contains data related to specific event types.</span></span> <span data-ttu-id="19779-313">詳細については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19779-313">For more information, see the following sections.</span></span>

#### <a name="customdata-values"></a><span data-ttu-id="19779-314">custom_data の値</span><span class="sxs-lookup"><span data-stu-id="19779-314">custom_data values</span></span>

<span data-ttu-id="19779-315">イベントの custom_data フィールドは、メッセージ処理の詳細をログに記録するために、Exchange Online のさまざまなエージェントによって使用されます。 \*\*\*\* `AGENTINFO`</span><span class="sxs-lookup"><span data-stu-id="19779-315">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details.</span></span> <span data-ttu-id="19779-316">次のセクションでは、いくつかの興味深いエージェントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="19779-316">Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="19779-317">スパムフィルターエージェント</span><span class="sxs-lookup"><span data-stu-id="19779-317">Spam filter agent</span></span>

<span data-ttu-id="19779-318">で\*\*\*\* `S:SFA`始まる custom_data 値は、スパムフィルターエージェントからのものです。</span><span class="sxs-lookup"><span data-stu-id="19779-318">A **custom_data** value that starts with `S:SFA` is from the spam filter agent.</span></span> <span data-ttu-id="19779-319">重要な詳細については、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="19779-319">The key details are described in the following table:</span></span>

|<span data-ttu-id="19779-320">**値**</span><span class="sxs-lookup"><span data-stu-id="19779-320">**Value**</span></span>|<span data-ttu-id="19779-321">**説明**</span><span class="sxs-lookup"><span data-stu-id="19779-321">**Description**</span></span>|
|:-----|:-----|
|`SFV=NSPM`|<span data-ttu-id="19779-322">メッセージがスパムではないとしてマークされ、意図された受信者に送信されました。</span><span class="sxs-lookup"><span data-stu-id="19779-322">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="19779-323">コンテンツ フィルターによって、メッセージがスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="19779-323">The message was marked as spam by the content filter.</span></span>|
|`SFV=BLK`|<span data-ttu-id="19779-324">ブロックする差出人から発信されたメッセージであるため、フィルター処理が省略され、メッセージはブロックされました。</span><span class="sxs-lookup"><span data-stu-id="19779-324">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="19779-p152">コンテンツ フィルターによって処理される前に、メッセージがスパムとしてマークされました。これには、メッセージを自動的にスパムとしてマークし、他のすべてのフィルター処理を省略するトランスポート ルールに適合したメッセージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="19779-p152">The message was marked as spam prior to being processed by the content filter. This includes messages where the message matched a Transport rule to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="19779-327">さまざまな SCL の値とその意味の詳細については、「[Spam Confidence Level](https://technet.microsoft.com/library/jj200686.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19779-327">For more information about the different SCL values and what they mean, see [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`PCL=<number>`|<span data-ttu-id="19779-p153">メッセージの Phishing Confidence Level (PCL) 値。これらの値は、「[Spam Confidence Level](https://technet.microsoft.com/library/jj200686.aspx)」に記載されている SCL 値と同様に解釈できます。  </span><span class="sxs-lookup"><span data-stu-id="19779-p153">The Phishing Confidence Level (PCL) value of the message. These can be interpreted the same way as the SCL values documented in [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`DI=SB`|<span data-ttu-id="19779-330">メッセージの送信者はブロックされました。</span><span class="sxs-lookup"><span data-stu-id="19779-330">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="19779-331">メッセージは検疫されました。</span><span class="sxs-lookup"><span data-stu-id="19779-331">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="19779-332">メッセージは削除されました。</span><span class="sxs-lookup"><span data-stu-id="19779-332">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="19779-333">メッセージは受信者の迷惑メール フォルダーに送信されました。</span><span class="sxs-lookup"><span data-stu-id="19779-333">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="19779-334">メッセージがより危険度の高い配信プールを経由してルーティングされました。</span><span class="sxs-lookup"><span data-stu-id="19779-334">The message was routed through the higher risk delivery pool.</span></span> <span data-ttu-id="19779-335">詳細については、「[送信メッセージ用の高リスク配信プール](https://technet.microsoft.com/library/jj200746.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19779-335">For more information, see [High-risk delivery pool for outbound messages](https://technet.microsoft.com/library/jj200746.aspx).</span></span>|
|`DI=SO`|<span data-ttu-id="19779-336">メッセージは通常の送信用の配信プールを通じて送信されました。</span><span class="sxs-lookup"><span data-stu-id="19779-336">The message was routed through the normal outbound delivery pool.</span></span>|
|`SFS=[a]|SFS=[b]`|<span data-ttu-id="19779-337">これはスパム ルールが一致したことを示します。</span><span class="sxs-lookup"><span data-stu-id="19779-337">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="19779-338">このメッセージの IP アドレスは接続フィルターの IP 許可一覧に指定されているため、スパム フィルターの通過を許可されました。</span><span class="sxs-lookup"><span data-stu-id="19779-338">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="19779-339">接続している電子メールサーバーの HELO または EHLO 文字列。</span><span class="sxs-lookup"><span data-stu-id="19779-339">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="19779-340">送信元の IP アドレスの PTR レコード (逆引き DNS アドレスともいう) です。</span><span class="sxs-lookup"><span data-stu-id="19779-340">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|

<span data-ttu-id="19779-341">次のようなスパムのフィルターが適用されたメッセージの**custom_data**値の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="19779-341">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="19779-342">マルウェアフィルターエージェント</span><span class="sxs-lookup"><span data-stu-id="19779-342">Malware filter agent</span></span>

<span data-ttu-id="19779-343">で\*\*\*\* `S:AMA`始まる custom_data 値は、マルウェアフィルターエージェントからのものです。</span><span class="sxs-lookup"><span data-stu-id="19779-343">A **custom_data** value that starts with `S:AMA` is from the malware filter agent.</span></span> <span data-ttu-id="19779-344">重要な詳細については、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="19779-344">The key details are described in the following table:</span></span>

|<span data-ttu-id="19779-345">**値**</span><span class="sxs-lookup"><span data-stu-id="19779-345">**Value**</span></span>|<span data-ttu-id="19779-346">**説明**</span><span class="sxs-lookup"><span data-stu-id="19779-346">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="19779-347">`AMA=SUM|v=1|` または `AMA=EV|v=1`</span><span class="sxs-lookup"><span data-stu-id="19779-347">`AMA=SUM|v=1|` or `AMA=EV|v=1`</span></span>|<span data-ttu-id="19779-348">このメッセージは、マルウェアが含まれていると判断されました。</span><span class="sxs-lookup"><span data-stu-id="19779-348">The message was determined to contain malware.</span></span> <span data-ttu-id="19779-349">`SUM`マルウェアが、任意の数のエンジンによって検出された可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="19779-349">`SUM` indicates the malware could've been detected by any number of engines.</span></span> <span data-ttu-id="19779-350">`EV`特定のエンジンによってマルウェアが検出されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="19779-350">`EV` indicates the malware was detected by a specific engine.</span></span> <span data-ttu-id="19779-351">エンジンでマルウェアが検出された場合は、後続のアクションをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="19779-351">When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="19779-352">メッセージは置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="19779-352">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="19779-353">メッセージはバイパスされました。</span><span class="sxs-lookup"><span data-stu-id="19779-353">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="19779-354">メッセージは延期されました。</span><span class="sxs-lookup"><span data-stu-id="19779-354">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="19779-355">メッセージは削除されました。</span><span class="sxs-lookup"><span data-stu-id="19779-355">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="19779-356">メッセージはバイパスされました。</span><span class="sxs-lookup"><span data-stu-id="19779-356">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="19779-357">メッセージはバイパスされました。</span><span class="sxs-lookup"><span data-stu-id="19779-357">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="19779-358">メッセージは拒否されました。</span><span class="sxs-lookup"><span data-stu-id="19779-358">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="19779-359">メッセージは拒否されました。</span><span class="sxs-lookup"><span data-stu-id="19779-359">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="19779-360">メッセージはブロックされました。</span><span class="sxs-lookup"><span data-stu-id="19779-360">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="19779-361">検出されたマルウェアの名前。</span><span class="sxs-lookup"><span data-stu-id="19779-361">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="19779-362">マルウェアを含むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="19779-362">The name of the file that contained the malware.</span></span>|

<span data-ttu-id="19779-363">マルウェアを含むメッセージの**custom_data**値の例は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="19779-363">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="19779-364">トランスポートルールエージェント</span><span class="sxs-lookup"><span data-stu-id="19779-364">Transport Rule agent</span></span>

<span data-ttu-id="19779-365">で\*\*\*\* `S:TRA`始まる custom_data 値は、メールフロールール (トランスポートルールとも呼ばれる) のトランスポートルールエージェントからの値です。</span><span class="sxs-lookup"><span data-stu-id="19779-365">A **custom_data** value that starts with`S:TRA` is from the Transport Rule agent for mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="19779-366">重要な詳細については、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="19779-366">The key details are described in the following table:</span></span>

|<span data-ttu-id="19779-367">**値**</span><span class="sxs-lookup"><span data-stu-id="19779-367">**Value**</span></span>|<span data-ttu-id="19779-368">**説明**</span><span class="sxs-lookup"><span data-stu-id="19779-368">**Description**</span></span>|
|:-----|:-----|
|`ETR|ruleId=<guid>`|<span data-ttu-id="19779-369">一致したルールの ID。</span><span class="sxs-lookup"><span data-stu-id="19779-369">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="19779-370">ルールの一致が発生した日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="19779-370">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="19779-371">適用されたアクション。</span><span class="sxs-lookup"><span data-stu-id="19779-371">The action that was applied.</span></span> <span data-ttu-id="19779-372">使用可能なアクションの一覧については、「 [Exchange Online のメールフロールールのアクション](https://technet.microsoft.com/library/jj919237.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19779-372">For a list of available actions, see [Mail flow rule actions in Exchange Online](https://technet.microsoft.com/library/jj919237.aspx).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="19779-373">ルールのモード。</span><span class="sxs-lookup"><span data-stu-id="19779-373">The mode of the rule.</span></span> <span data-ttu-id="19779-374">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="19779-374">Valid values are:</span></span> <br/><span data-ttu-id="19779-375">•**強制**: ルールのすべてのアクションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="19779-375">• **Enforce**: All actions on the rule will be enforced.</span></span> <br/><span data-ttu-id="19779-376">•**ポリシーヒントを使用してテストする:**: ポリシーヒントアクションは送信されますが、他の強制アクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="19779-376">• **Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span> <br/><span data-ttu-id="19779-377">•**ポリシーヒントなしのテスト**: アクションがログファイルにリストされますが、送信者には何も通知されず、強制アクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="19779-377">• **Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span>|

<span data-ttu-id="19779-378">メールフロールールの条件に一致するメッセージの**custom_data**値の例は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="19779-378">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
