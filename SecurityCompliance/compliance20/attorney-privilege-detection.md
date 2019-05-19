---
title: 高度な電子情報開示で、弁護士クライアント特権の検出を設定する
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: ee5f2257e73467c50a0ecc296d8d3b70b7c3d0f8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155189"
---
# <a name="set-up-attorney-client-privilege-detection-preview-in-advanced-ediscovery"></a><span data-ttu-id="f02e1-102">上級電子情報開示で、弁護士クライアント特権の検出 (プレビュー) を設定する</span><span class="sxs-lookup"><span data-stu-id="f02e1-102">Set up attorney-client privilege detection (preview) in Advanced eDiscovery</span></span>

<span data-ttu-id="f02e1-103">探索プロセスのレビュー部分には、重要かつ高コストの要素があり、権限のあるコンテンツを検討しています。</span><span class="sxs-lookup"><span data-stu-id="f02e1-103">A major and costly aspect of the review portion of any discovery process is reviewing for privileged content.</span></span> <span data-ttu-id="f02e1-104">上級電子情報開示を使用すると、このプロセスをより効率的に行うことができるように、お客様のための権限のあるコンテンツを AI ベースで検出できます。</span><span class="sxs-lookup"><span data-stu-id="f02e1-104">Advanced eDiscovery provides an AI-based detection of privileged content in your case so that you can make this process more efficient.</span></span> <span data-ttu-id="f02e1-105">この機能は現在ベータ版であるため、電子情報開示管理者はこの機能を使用するように機能を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f02e1-105">As this feature is currently in beta, an eDiscovery Administrator has to opt into the feature to use it.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="f02e1-106">どのように動作するか。</span><span class="sxs-lookup"><span data-stu-id="f02e1-106">How does it work?</span></span>

<span data-ttu-id="f02e1-107">機能が有効になっている場合、ケース内のレビューセットを分析すると、すべてのドキュメントは、弁護士クライアント特権検出モデルによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="f02e1-107">With the feature turned on, when you analyze a review set within a case, all documents run through the attorney-client privilege detection model.</span></span> <span data-ttu-id="f02e1-108">このモデルは、次の2つの点を確認します。</span><span class="sxs-lookup"><span data-stu-id="f02e1-108">The model looks at two things:</span></span>

- <span data-ttu-id="f02e1-109">コンテンツ: ML モデルは、ドキュメントのコンテンツが実際に有効かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f02e1-109">Content: the ML model determines the likelihood of the document's content being legal in nature.</span></span>

- <span data-ttu-id="f02e1-110">参加者: テナントに対してユーザーがアップロードした弁護士のリストがある場合、モデルはドキュメントの参加者をリストと比較して、ドキュメントに少なくとも1人の弁護士参加者がいるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f02e1-110">Participants: if there is a user-uploaded list of attorneys for the tenant, the model compares the participants of the document against the list to determine whether the document has at least one attorney participant.</span></span>
<span data-ttu-id="f02e1-111">このモデルでは、すべてのドキュメントに対して3つの値が出力されます。これらはすべて、レビューセット内で検索できます。</span><span class="sxs-lookup"><span data-stu-id="f02e1-111">The model outputs three values for every document, all of which will be searchable within a review set:</span></span>

- <span data-ttu-id="f02e1-112">コンテンツのスコア: ドキュメントが実際に訴訟になる可能性 (0 ~ 1 のスコア)</span><span class="sxs-lookup"><span data-stu-id="f02e1-112">Content score: the likelihood of the document being legal in nature (score between 0 and 1)</span></span>

- <span data-ttu-id="f02e1-113">弁護士がある場合: 参加者の1人がアップロードされた弁護士リストで見つかった場合は True、それ以外の場合、または弁護士リストがない場合は True。</span><span class="sxs-lookup"><span data-stu-id="f02e1-113">Has Attorney: True if one of the participants is found in the uploaded attorney list, false otherwise, or if there is no attorney list.</span></span>

-  <span data-ttu-id="f02e1-114">潜在的な特権: コンテンツスコアがしきい値を超える場合、または弁護士の参加者がいる場合は True、それ以外の場合は false。</span><span class="sxs-lookup"><span data-stu-id="f02e1-114">Potentially Privileged: True if content score is above threshold or has an attorney participant, false otherwise.</span></span>

## <a name="opting-into-attorney-client-privilege-detection"></a><span data-ttu-id="f02e1-115">弁護士クライアント特権の検出をオプトインする</span><span class="sxs-lookup"><span data-stu-id="f02e1-115">Opting into Attorney-client privilege detection</span></span>

### <a name="step-1-opt-into-attorney-client-privilege-detection-ediscovery-admin"></a><span data-ttu-id="f02e1-116">手順 1: 弁護士-クライアント特権検出 (電子情報開示管理者) を選択する</span><span class="sxs-lookup"><span data-stu-id="f02e1-116">Step 1: Opt into Attorney-client privilege detection (eDiscovery Admin)</span></span>

<span data-ttu-id="f02e1-117">委任状の特権の検出はプレビュー機能であるため、電子情報開示管理者は、その機能を使用できるようにするために選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f02e1-117">Because Attorney-client privilege detection is a preview feature, your eDiscovery Administrator needs to opt in to make the feature available in your cases.</span></span>

- <span data-ttu-id="f02e1-118">高度な電子情報開示ページから [実験的な機能を構成] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f02e1-118">Go to "Configure experimental features" from Advanced eDiscovery page</span></span>

- <span data-ttu-id="f02e1-119">[弁護士-クライアント特権検出の管理] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f02e1-119">Click on "Manage Attorney-Client Privilege detection".</span></span>

- <span data-ttu-id="f02e1-120">この機能をオンにするには、トグルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f02e1-120">Click on the toggle to turn the feature on.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="f02e1-121">手順 2: 弁護士の一覧をアップロードする (オプション)</span><span class="sxs-lookup"><span data-stu-id="f02e1-121">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="f02e1-122">弁護士と顧客の特権の検出を十分に活用するには、会社に勤務している電子メールアドレスの弁護士または法的ペルソナの一覧を提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f02e1-122">In order to take full advantage of attorney-client privilege detection we recommend providing a list of email addresses lawyers or legal personas who work for the company.</span></span> <span data-ttu-id="f02e1-123">このリストは、ヘッダーなしの CSV で、1行に1つの電子メールアドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f02e1-123">The list should be a header-less CSV, with one email address per line.</span></span>

## <a name="leveraging-attorney-client-privilege-detection"></a><span data-ttu-id="f02e1-124">弁護士クライアント特権検出の活用</span><span class="sxs-lookup"><span data-stu-id="f02e1-124">Leveraging attorney-client privilege detection</span></span> 

### <a name="step-1-analyze-a-review-set"></a><span data-ttu-id="f02e1-125">手順 1: レビューセットを分析する</span><span class="sxs-lookup"><span data-stu-id="f02e1-125">Step 1: Analyze a review set</span></span>

<span data-ttu-id="f02e1-126">レビューセットを分析すると、弁護士側の特権の検出も実行されます。</span><span class="sxs-lookup"><span data-stu-id="f02e1-126">When you analyze your review set, attorney-client privilege detection will be run as well.</span></span> <span data-ttu-id="f02e1-127">レビューセットでのデータ分析の詳細については、 [「Advanced eDiscovery でデータを分析セットに分析](analyzing-data-in-review-set.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f02e1-127">To learn more about analyzing data in review set, please refer to [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-2-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="f02e1-128">手順 2: 弁護士クライアント特権検出モデルを使用してスマートタググループを作成する</span><span class="sxs-lookup"><span data-stu-id="f02e1-128">Step 2: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="f02e1-129">レビュープロセスにおいて、弁護士クライアント特権の検出結果を使用する主な方法の1つは、スマートタググループを使用することです。</span><span class="sxs-lookup"><span data-stu-id="f02e1-129">One of the main ways you can consume the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="f02e1-130">スマートタググループは ML モデルの結果を取得し、タグの横にモデルの結果を表示して、関連性がある場合にモデルの結果を簡単に使用できるようにします。また、タグは、タグ付けパネルの他のタグと同じようにレビュープロセスで使用します。</span><span class="sxs-lookup"><span data-stu-id="f02e1-130">Smart tag groups take the results of an ML model and show the results of the model in-line next to the tags, so that you can easily consume the results of the model where relevant, and use the tags in your review process as you would any other tags in your tagging panel.</span></span> <span data-ttu-id="f02e1-131">詳細については、 [「Advanced eDiscovery での ML サポートのスマートタグの設定」](smart-tags.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f02e1-131">Please refer to [Set up smart tags for ML-assisted review in Advanced eDiscovery](smart-tags.md) for more information.</span></span>

- <span data-ttu-id="f02e1-132">[タグの管理] で、[スマートタグセクションの追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f02e1-132">In "Manage tags", click on "Add smart tag section".</span></span>

- <span data-ttu-id="f02e1-133">[弁護士-クライアント特権検出] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f02e1-133">Select "Attorney-client privilege detection".</span></span> <span data-ttu-id="f02e1-134">モデルの可能な結果に対応するタググループと2つのタグが作成されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="f02e1-134">You will see that a tag group and two tags, corresponding to the possible results of the model, have been created.</span></span>

- <span data-ttu-id="f02e1-135">レビューに合わせて、タググループとタグの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="f02e1-135">Rename the tag group and tags as you see fit for your review.</span></span>

### <a name="step-3-use-the-smart-tag-group-for-privilege-review"></a><span data-ttu-id="f02e1-136">手順 3: 特権レビューにスマートタググループを使用する</span><span class="sxs-lookup"><span data-stu-id="f02e1-136">Step 3: Use the smart tag group for privilege review</span></span>

<span data-ttu-id="f02e1-137">ドキュメントのレビュー時に、モデルでドキュメントに潜在的な権限があると判断された場合、対応するスマートタグは結果を公開します。</span><span class="sxs-lookup"><span data-stu-id="f02e1-137">When you review a document, if the model has determined that the document is potentially privileged, the corresponding smart tag will expose the result:</span></span>

- <span data-ttu-id="f02e1-138">ドキュメントに有効なコンテンツが含まれている場合は、対応するスマートタグの横に "Legal content" ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f02e1-138">If the document has content that may be legal in nature, a "Legal content" label will appear next to the corresponding smart tag.</span></span>

- <span data-ttu-id="f02e1-139">アップロードされた弁護士リストに含まれている参加者がドキュメントにある場合、対応するスマートタグの横に「弁護士」というラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f02e1-139">If the document has a participant that is found in the uploaded attorney list, an "Attorney" label will appear next to the corresponding smart tag.</span></span>