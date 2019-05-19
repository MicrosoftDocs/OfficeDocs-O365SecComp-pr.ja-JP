---
title: 高度な電子情報開示での弁護士に対するクライアント特権の検出にスマートタグを設定する
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
ms.openlocfilehash: 5310acad1aa1bc2e01cbabee69dd7bb38084bd9a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153969"
---
# <a name="set-up-smart-tags-for-ml-assisted-review-in-advanced-ediscovery"></a><span data-ttu-id="3ca41-102">高度な電子情報開示での ML サポートのスマートタグの設定</span><span class="sxs-lookup"><span data-stu-id="3ca41-102">Set up smart tags for ML-assisted review in Advanced eDiscovery</span></span>

<span data-ttu-id="3ca41-103">高度な電子情報開示の機械学習機能は、ドキュメントの意思決定プロセスを効率化するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3ca41-103">Machine learning capabilities in Advanced eDiscovery are meant to help make decision process on documents more efficient.</span></span> <span data-ttu-id="3ca41-104">スマートタグを使うと、決定事項を記録するための機械学習機能を、タグとタググループにまとめることができます。</span><span class="sxs-lookup"><span data-stu-id="3ca41-104">Smart tags is a way to bring the machine learning capabilities into where the decisions are recorded: tags and tag groups.</span></span> <span data-ttu-id="3ca41-105">スマートタググループを作成すると、グループにマッピングされた ML モデルの決定は、インラインでわかりやすく表示されるように、情報をインラインで表示するために、グループ内のタグと一緒に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ca41-105">When you create a smart tag group, then the decisions of the ML model mapped to the group will be shown in-line with the tags in the group to help you see the information in-line, where they contextually make most sense.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="3ca41-106">スマートタググループをセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="3ca41-106">How to set up a smart tag group</span></span>

1. <span data-ttu-id="3ca41-107">レビューセットで、[レビューの**管理] セット** -> の [**タグの管理**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="3ca41-107">In a review set, go to **Manage review set** -> **Manage tags**.</span></span>

2. <span data-ttu-id="3ca41-108">[**タググループの追加**] の横にあるドロップダウンをクリックして、[**スマートタググループの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ca41-108">Click on the drop-down next to **Add tag group** and select **Add smart tag group**.</span></span>

3. <span data-ttu-id="3ca41-109">このグループにマップするモデルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3ca41-109">Select the model you want to map to this group.</span></span> <span data-ttu-id="3ca41-110">これにより、タグセクションと N 個の子タグが作成されます。ここで、N はモデルの可能な出力の数です。</span><span class="sxs-lookup"><span data-stu-id="3ca41-110">This will create a tag section and N child tags, where N is the number of possible outputs of the model.</span></span> <span data-ttu-id="3ca41-111">たとえば、弁護士-クライアント特権検出モデルには、2つの出力があり、特権がなく、特権がありません。このモデルを選択すると、レビューセット内に2つの子タグが作成されます。各タグは、考えられる出力のいずれかに対応します。</span><span class="sxs-lookup"><span data-stu-id="3ca41-111">For instance, attorney-client privilege detection model has two possible outputs - privileged and not privileged; selecting this model will create two child tags in the review set, each corresponding to one of the possible outputs.</span></span>

4. <span data-ttu-id="3ca41-112">必要に応じて、タググループとタグの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="3ca41-112">Rename the tag group and tags as you see fit.</span></span>

## <a name="how-to-use-a-smart-tag-group"></a><span data-ttu-id="3ca41-113">スマートタググループを使用する方法</span><span class="sxs-lookup"><span data-stu-id="3ca41-113">How to use a smart tag group</span></span>

<span data-ttu-id="3ca41-114">ドキュメントのレビュー時に、モデルの結果が適切なタグ値の横に公開されます。</span><span class="sxs-lookup"><span data-stu-id="3ca41-114">When reviewing a document, the model's results will be exposed next to the appropriate tag value.</span></span> <span data-ttu-id="3ca41-115">たとえば、弁護士側の権限を検出するためのスマートタググループがあり、そのモデルで決定されたドキュメントを確認した場合は、該当するタグの横にその理由が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ca41-115">For instance, if you have a smart tag group for attorney-client privilege detection and you review a document that the model has decided is potentially privileged, you will see the reason for that next to the appropriate tag.</span></span> <span data-ttu-id="3ca41-116">タグは自動的に適用されないことに注意することが重要です。すべての目的において、スマートタググループ内のタグは、通常のタグと同じように動作しますが、必要に応じて、その横にモデルの結果が表示される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="3ca41-116">It is important to note that the tag is not automatically applied; for all intents and purposes, tags within a smart tag group act just like normal tags, except that they expose the model results next to them when appropriate.</span></span>