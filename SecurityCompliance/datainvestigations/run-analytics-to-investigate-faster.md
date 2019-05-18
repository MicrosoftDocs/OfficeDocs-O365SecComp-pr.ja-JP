---
title: アナリティクスを使用して、より速い調査を実行する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 7462b415c2e5b0a66c08bb9b5abb647f366e9785
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153659"
---
# <a name="run-analytics-to-investigate-faster"></a><span data-ttu-id="3ccfb-102">アナリティクスを使用して、より速い調査を実行する</span><span class="sxs-lookup"><span data-stu-id="3ccfb-102">Run analytics to investigate faster</span></span>

<span data-ttu-id="3ccfb-103">証拠のコレクションが大きい場合、それらをすべて確認するのは困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-103">When an evidence collection is large, it can be difficult to review them all.</span></span> <span data-ttu-id="3ccfb-104">多くの場合、証拠のセットには、同じまたは類似の電子メールメッセージまたはドキュメントの複数のコピーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-104">A set of evidence often includes multiple copies of the same or similar email messages or documents.</span></span> <span data-ttu-id="3ccfb-105">データ調査 (プレビュー) には、情報が失われないように、確認が必要なドキュメントのボリュームを減らすために役立つ分析ツールが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-105">Data Investigations (Preview) provides a number of analytics tools that can help you reduce the volume of documents that need to be reviewed without any loss in information.</span></span> <span data-ttu-id="3ccfb-106">これらの機能の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-106">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="3ccfb-107">準重複の検出</span><span class="sxs-lookup"><span data-stu-id="3ccfb-107">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="3ccfb-108">電子メールのスレッド化</span><span class="sxs-lookup"><span data-stu-id="3ccfb-108">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="3ccfb-109">テーマ</span><span class="sxs-lookup"><span data-stu-id="3ccfb-109">Themes</span></span>](themes.md)

<span data-ttu-id="3ccfb-110">証拠セット内のデータを分析するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-110">To analyze data in an evidence set:</span></span>

1. <span data-ttu-id="3ccfb-111">調査のための分析設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-111">Configure the analytics settings for your investigation.</span></span> <span data-ttu-id="3ccfb-112">詳細については、「 [Configure search and analytics settings](configure-search-analytics-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-112">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="3ccfb-113">証拠セットを開きます。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-113">Open the evidence set.</span></span>

3. <span data-ttu-id="3ccfb-114">[**証明の管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-114">Click **Manage evidence**.</span></span>

4. <span data-ttu-id="3ccfb-115">[**分析**] の [**分析**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-115">Under **Analytics**, click **Analyze**.</span></span>

<span data-ttu-id="3ccfb-116">調査中に [**ジョブ**] タブで分析の進行状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-116">You can check the progress of analysis on the **Jobs** tab in your investigation.</span></span> <span data-ttu-id="3ccfb-117">トリガーされるジョブの種類は、 **analytics の実行**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-117">The job type that's triggered is named **Running analytics**.</span></span>

 <span data-ttu-id="3ccfb-118">分析が完了すると、右側のパネルに表示されている、確認しているドキュメントの完全に重複またはほぼ重複したリストが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-118">After analysis is completed, you can see a list of exact duplicates or near-duplicates of the document that you're reviewing located in the panel on the right.</span></span> <span data-ttu-id="3ccfb-119">表示しているドキュメントのすべての複製を選択するには、このパネルを使用して簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-119">To select all duplicates of the document you're viewing, you can easily do so using this panel.</span></span> <span data-ttu-id="3ccfb-120">このパネルの他の機能の詳細については、「[証拠データのレビュー](review-data-in-evidence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-120">To learn more about other features on this panel, see [Review data in evidence](review-data-in-evidence.md).</span></span> 

<span data-ttu-id="3ccfb-121">また、テーマなどの分析の出力を使用して、証拠内で追加のクエリを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-121">You can also run additional queries within your evidence using the outputs of the analysis such as themes.</span></span> <span data-ttu-id="3ccfb-122">詳細については、「[証拠でデータを照会する](evidence-query.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-122">For more information, see [Query the data in evidence](evidence-query.md).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="3ccfb-123">分析レポート</span><span class="sxs-lookup"><span data-stu-id="3ccfb-123">Analytics report</span></span>

<span data-ttu-id="3ccfb-124">証拠の分析レポートを表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-124">To view an analytics report for your evidence:</span></span>

1. <span data-ttu-id="3ccfb-125">証拠セットを開きます。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-125">Open the evidence set.</span></span>

2. <span data-ttu-id="3ccfb-126">[**証明の管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-126">Click **Manage evidence**.</span></span>

3. <span data-ttu-id="3ccfb-127">[**分析**] の [**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-127">Under **Analytics**, click **View report**.</span></span>

<span data-ttu-id="3ccfb-128">レポートには、分析の4つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-128">The report has four components from analysis:</span></span>

- <span data-ttu-id="3ccfb-129">[**内訳**]-証拠セットに含まれる生の電子メール、添付ファイル、およびドキュメントの数。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-129">**Breakdown** - The number of raw emails, attachments, and documents found in the evidence set.</span></span>

- <span data-ttu-id="3ccfb-130">**電子メール**-inclusives で使用される eamil メッセージの数、包括的なコピー、または上記に該当しないものがあります。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-130">**Emails** - The number of eamil messages that are inclusives, inclusive minuses, inclusive copies, or none of the above.</span></span>
   - <span data-ttu-id="3ccfb-131">Inclusives: 以前のすべての履歴を含む電子メールスレッドの最後のメッセージ。レビューが必要です。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-131">Inclusives: The last message in the email thread that contains all previous history and requires review.</span></span>
   - <span data-ttu-id="3ccfb-132">包括的な使用法: 確認が必要な1つ以上の異なる添付ファイルが含まれているスレッド内のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-132">Inclusive minuses: The message in the thread that contains one or more different attachments that requires review.</span></span>
   - <span data-ttu-id="3ccfb-133">包括的コピー: 別の包括的または包括的なマイナスメッセージのコピーであるメッセージ (件名と本文)。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-133">Inclusive copies: The message that is a copy of another inclusive or inclusive minus message (subject and body).</span></span>

- <span data-ttu-id="3ccfb-134">**添付ファイル**-同じ証拠に含まれる異なる電子メール添付ファイルの一意の数または重複した電子メール添付ファイルの数。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-134">**Attachments** - The number of email attachments that are unique or duplicates of a different email attachment within the same evidence same.</span></span>

- <span data-ttu-id="3ccfb-135">**ドキュメント (電子メール添付ファイルを除く)** : 校閲を必要とする一意のドキュメントの数。たとえば、ほぼ重複したセットの代表的なドキュメント、または別のドキュメントの完全な重複があります。</span><span class="sxs-lookup"><span data-stu-id="3ccfb-135">**Documents (excluding email attachments)** - The number of unique documents that require review, for example, the most representative document of the near-duplicate set or an exact duplicate of another document).</span></span>