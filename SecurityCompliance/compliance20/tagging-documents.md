---
title: レビュー セット内のドキュメントをタグ付けする
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
ms.openlocfilehash: a3b588f4b8e24783cd0d7198ea995f0fd6c8ae3e
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154029"
---
# <a name="tag-documents-in-a-review-set"></a><span data-ttu-id="2fcd2-102">レビュー セット内のドキュメントをタグ付けする</span><span class="sxs-lookup"><span data-stu-id="2fcd2-102">Tag documents in a review set</span></span>

<span data-ttu-id="2fcd2-103">レビューセットのコンテンツを整理することは、電子情報開示プロセスでさまざまなワークフローを完了するために重要です。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-103">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="2fcd2-104">これには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-104">This includes:</span></span>

-  <span data-ttu-id="2fcd2-105">不要なコンテンツのカリング</span><span class="sxs-lookup"><span data-stu-id="2fcd2-105">Culling unnecessary content</span></span>

- <span data-ttu-id="2fcd2-106">関連するコンテンツを特定する</span><span class="sxs-lookup"><span data-stu-id="2fcd2-106">Identifying relevant content</span></span>
 
-  <span data-ttu-id="2fcd2-107">専門家または弁護士が確認する必要があるコンテンツを特定する</span><span class="sxs-lookup"><span data-stu-id="2fcd2-107">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="2fcd2-108">専門家、弁護士、または他のユーザーがレビューセットのコンテンツをレビューする場合、コンテンツに関連する意見をタグを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-108">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="2fcd2-109">たとえば、不要なコンテンツをカリングすることが目的の場合、ユーザーは "応答不可" などのタグを持つドキュメントにタグを付けます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-109">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as “non-responsive”.</span></span> <span data-ttu-id="2fcd2-110">コンテンツをレビューしてタグ付けした後は、レビューセット検索を作成して、"応答不可" とタグ付けされたコンテンツを除外することができます。これにより、電子情報開示ワークフローの次のステップからそのコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-110">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as “non-responsive”, which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="2fcd2-111">タグパネルは、すべてのケースについてカスタマイズできます。そのため、タグが目的のレビューワークフローをサポートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-111">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="2fcd2-112">タグの種類</span><span class="sxs-lookup"><span data-stu-id="2fcd2-112">Tag types</span></span>

<span data-ttu-id="2fcd2-113">上級電子情報開示には、次の2種類のタグがあります。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-113">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="2fcd2-114">**単一選択タグ**-ユーザーがグループ内の1つのタグを選択できるように制限します。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-114">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="2fcd2-115">これは、ユーザーが "応答可能" や "応答不可" などの競合するタグを選択しないようにするのに便利です。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-115">This can be useful to ensure users don’t select conflicting tags such as “responsive” and “non-responsive”.</span></span> 

- <span data-ttu-id="2fcd2-116">**複数選択タグ**-ユーザーがグループ内で複数のタグを選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-116">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="2fcd2-117">タグ構造</span><span class="sxs-lookup"><span data-stu-id="2fcd2-117">Tag structure</span></span>

<span data-ttu-id="2fcd2-118">タグの種類に加えて、タグパネルでタグを構成する方法の構造を使用すると、タグ付きドキュメントをより直観的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-118">In addition to the tag types, the structure of how tags are organization in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="2fcd2-119">タグはセクションごとにグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-119">Tags are grouped by sections.</span></span> <span data-ttu-id="2fcd2-120">レビューセット検索は、タグとタグで検索する機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-120">review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="2fcd2-121">つまり、レビューセット検索を作成して、セクション内のタグでタグ付けされたドキュメントを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-121">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![タグパネル内のタグセクション](../media/Tagtypes.png)

<span data-ttu-id="2fcd2-123">タグは、セクション内にネストすることで、さらに整理することができます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-123">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="2fcd2-124">たとえば、権限のあるコンテンツを識別し、タグ付けすることを目的としている場合は、ネストを使用して、ユーザーがドキュメントを "特権付き" としてタグ設定し、適切なネストされたタグをチェックすることで特権の種類を選択できることを明確にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-124">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as “Privileged” and select the type of privilege by checking the appropriate nested tag.</span></span>

![タグセクション内の入れ子になったタグ](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="2fcd2-126">タグの適用</span><span class="sxs-lookup"><span data-stu-id="2fcd2-126">Applying tags</span></span>

<span data-ttu-id="2fcd2-127">コンテンツにタグを適用するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-127">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="2fcd2-128">1つのドキュメントにタグを付けます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-128">Tagging a single document</span></span>

<span data-ttu-id="2fcd2-129">レビューセット内のドキュメントを表示するときに、[**コーディングパネル]** をクリックすると、レビューで使用できるタグを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-129">When viewing a document in a review set, you can display the tags that a review can use by clicking **Coding panel**.</span></span>

![[タグパネル] をクリックして、タグパネルを表示します。](../media/Singledoctag.png)

<span data-ttu-id="2fcd2-131">これにより、ビューアーに表示されるドキュメントにタグを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-131">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="2fcd2-132">一括タグ付け</span><span class="sxs-lookup"><span data-stu-id="2fcd2-132">Bulk tagging</span></span>

<span data-ttu-id="2fcd2-133">一括タグ付けを行うには、結果グリッドで複数のファイルを選択し、1つのドキュメントにタグ付けするのと同じように、**コーディングパネル**のタグを使用します。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-133">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Coding panel** similar to tagging single documents.</span></span> <span data-ttu-id="2fcd2-134">タグを2回選択することで一括でのタグの解除を行うことができます。最初のクリックでタグが適用され、2番目の選択によって、選択されているすべてのファイルのタグがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-134">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![携帯電話の説明のスクリーンショットが自動的に生成される](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="2fcd2-136">一括タグ付けの場合、タグ付けパネルには、パネル内の各タグに対してタグ付けされたファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-136">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="2fcd2-137">他のレビューパネルでのタグ付け</span><span class="sxs-lookup"><span data-stu-id="2fcd2-137">Tagging in other review panels</span></span>

<span data-ttu-id="2fcd2-138">ドキュメントを確認するときは、他のレビューパネルを使用して、結果グリッド内のドキュメントの他の特性を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-138">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="2fcd2-139">これには、その他の関連ドキュメント、電子メールスレッド、ほぼ重複、ハッシュの重複の確認が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-139">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="2fcd2-140">たとえば、[**ドキュメントファミリ**レビュー] パネルを使用して関連ドキュメントをレビューしている場合は、関連するドキュメントを一括でタグ付けすることによってレビュー時間を大幅に短縮できます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-140">For example, when your reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="2fcd2-141">たとえば、電子メールメッセージに複数の添付ファイルがあり、ファミリー全体が一貫してタグ付けされるようにする場合などです。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-141">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="2fcd2-142">たとえば、**ドキュメントファミリー**レビューパネルの使用時に**コーディングパネル**を表示する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-142">For example, here's how to display the **Coding panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="2fcd2-143">選択したドキュメントに対してレビューパネルを開き (たとえば、関連するコンテンツのリストを**ドキュメントファミリー**レビューパネルに表示する)、現在のレビューパネルの上部にある [**コードドキュメント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-143">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Code documents** at the top of the current review panel.</span></span>

   <span data-ttu-id="2fcd2-144">コーディングパネルはポップアップウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-144">The Coding panel is displayed is a pop-up window.</span></span>

2. <span data-ttu-id="2fcd2-145">1つ以上のタグを選択して、選択したドキュメントを適用します。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-145">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="2fcd2-146">すべてのドキュメントにタグ付けするには、**ドキュメントファミリー**パネルで [すべてのドキュメント] を選択し、[**コードドキュメント**] をクリックして、ドキュメントのファミリー全体に適用するタグを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fcd2-146">To tag all documents, select all documents in the **Document family** panel, click **Code documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![ソーシャルメディア投稿の説明が自動的に生成されたスクリーンショット](../media/Relatedtag.png)
