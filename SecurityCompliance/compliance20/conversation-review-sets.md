---
title: 高度な電子情報開示で会話を確認する
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
ms.openlocfilehash: 62f0dc9e32e89954b2838b70757d3a7c17d79cc4
ms.sourcegitcommit: 6302a43d947a908dd10a8e40550b806f491692fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2019
ms.locfileid: "35672978"
---
# <a name="review-conversations-in-advanced-ediscovery"></a><span data-ttu-id="53069-102">高度な電子情報開示で会話を確認する</span><span class="sxs-lookup"><span data-stu-id="53069-102">Review conversations in Advanced eDiscovery</span></span> 

<span data-ttu-id="53069-103">インスタントメッセージングは、質問の確認、アイデアの共有、または大規模な対象ユーザー間での迅速なコミュニケーションを行うのに便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="53069-103">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="53069-104">Microsoft Teams などのインスタントメッセージングプラットフォームがエンタープライズコラボレーションの中核となるように、組織は、電子情報開示ワークフローがどのように新しい形式のコミュニケーションとコラボレーションを実現するかを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53069-104">As instant messaging platforms, like Microsoft Teams, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span> 

<span data-ttu-id="53069-105">上級電子情報開示の会話の再構築機能は、コンテキストコンテンツを特定し、個別の会話ビューを作成するのに役立つように設計されています。</span><span class="sxs-lookup"><span data-stu-id="53069-105">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="53069-106">この機能により、Microsoft Teams などのプラットフォームで生成された完全なインスタントメッセージ会話 (*スレッド*とも呼ばれます) を効率的かつ迅速に確認することができます。</span><span class="sxs-lookup"><span data-stu-id="53069-106">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="53069-107">会話の再構築では、スレッド化された会話の再構築、レビュー、およびエクスポートに組み込み機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="53069-107">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="53069-108">高度な電子情報開示会話の再構築を次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="53069-108">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="53069-109">会話内のすべてのメッセージに対して、一意のメッセージレベルのメタデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="53069-109">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="53069-110">検索結果の周囲のコンテキストメッセージを収集します。</span><span class="sxs-lookup"><span data-stu-id="53069-110">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="53069-111">スレッド化された会話の確認、注釈付け、および墨消しを行います。</span><span class="sxs-lookup"><span data-stu-id="53069-111">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="53069-112">個々のメッセージまたはスレッド化会話をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="53069-112">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="53069-113">用語集</span><span class="sxs-lookup"><span data-stu-id="53069-113">Terminology</span></span>

<span data-ttu-id="53069-114">ここでは、会話の再構築の使用を開始する際に役立つ定義について説明します。</span><span class="sxs-lookup"><span data-stu-id="53069-114">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="53069-115">**メッセージ:** 会話の最小単位を表します。</span><span class="sxs-lookup"><span data-stu-id="53069-115">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="53069-116">メッセージは、サイズ、構造、およびメタデータによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="53069-116">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="53069-117">**会話:** 1つまたは複数のメッセージのグループを表します。</span><span class="sxs-lookup"><span data-stu-id="53069-117">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="53069-118">アプリケーションによって、会話はさまざまな方法で表現されることがあります。</span><span class="sxs-lookup"><span data-stu-id="53069-118">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="53069-119">アプリケーションによっては、既存のメッセージに返信することによって明示的にアクションが実行されることがあります。</span><span class="sxs-lookup"><span data-stu-id="53069-119">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="53069-120">このユーザーの操作の結果として、会話は明示的に形成されます。</span><span class="sxs-lookup"><span data-stu-id="53069-120">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="53069-121">たとえば、Microsoft Teams でのチャネル会話のスクリーンショットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="53069-121">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft Teams チャネルの会話](../media/threadedchat.png)

   <span data-ttu-id="53069-123">他のアプリ (Teams における1xN チャットメッセージなど) には、正式な返信チェーンはありません。代わりに、メッセージは1つのスレッド内に "フラット川メッセージ" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="53069-123">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="53069-124">これらの種類のアプリでは、会話は特定の時間内に発生するメッセージのグループから推論されます。</span><span class="sxs-lookup"><span data-stu-id="53069-124">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="53069-125">メッセージの "ソフトグループ化" (返信チェーンではなく) は、関心のある特定のトピックに関する "前後の" 会話を表します。</span><span class="sxs-lookup"><span data-stu-id="53069-125">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span> 

## <a name="step-1-run-a-search"></a><span data-ttu-id="53069-126">手順 1: 検索を実行する</span><span class="sxs-lookup"><span data-stu-id="53069-126">Step 1: Run a search</span></span>

<span data-ttu-id="53069-127">関連する保管担当者およびコンテンツの場所を特定したら、関連する可能性があるコンテンツを検索するための検索を作成できます。</span><span class="sxs-lookup"><span data-stu-id="53069-127">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="53069-128">高度な電子情報開示のケースの [**検索**] タブで、[**新しい検索**] をクリックし、ウィザードに従って検索を作成できます。</span><span class="sxs-lookup"><span data-stu-id="53069-128">On the **Searches** tab in the Advanced eDiscovery case, you can create a search by clicking **New search** and following the wizard.</span></span> <span data-ttu-id="53069-129">検索を作成し、検索クエリを作成し、検索結果を表示する方法については、「[ケースのデータを収集](create-search-to-collect-data.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53069-129">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span></span>

## <a name="step-2-create-a-conversation-review-set"></a><span data-ttu-id="53069-130">手順 2: 会話レビューセットを作成する</span><span class="sxs-lookup"><span data-stu-id="53069-130">Step 2: Create a conversation review set</span></span>

<span data-ttu-id="53069-131">校閲セットでは、ドキュメント、電子メールメッセージ、チャット会話を検索、タグ付け、注釈設定、および墨消しすることができます。</span><span class="sxs-lookup"><span data-stu-id="53069-131">In a review set, you can search, tag, annotate, and redact documents, email messages, and chat conversations.</span></span> <span data-ttu-id="53069-132">詳細な電子情報開示では、個々のメッセージまたはスレッド化された会話に基づいて、会話のレビューをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="53069-132">In Advanced eDiscovery, you can customize your review of conversations, based in individual messages or threaded conversations.</span></span> <span data-ttu-id="53069-133">これは、手順1で作成した検索結果を追加するレビューセットの種類によって決まります。</span><span class="sxs-lookup"><span data-stu-id="53069-133">This is determined by the type of review set that you add the results of the search created in Step 1 to.</span></span> <span data-ttu-id="53069-134">2つの異なる種類のレビューセットがあります。</span><span class="sxs-lookup"><span data-stu-id="53069-134">There are two different types of review sets:</span></span> 
  
  - <span data-ttu-id="53069-135">**標準レビューセット:** スレッド内のメッセージは処理され、個別のアイテムとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="53069-135">**Standard review sets:** Messages in conversations are processed and displayed as individual items.</span></span> 
  
  -  <span data-ttu-id="53069-136">**会話レビューセット:** スレッド内のメッセージは個別に処理されますが、スレッドビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="53069-136">**Conversation review sets:** Messages in conversations are processed individually but displayed in a conversation view.</span></span> <span data-ttu-id="53069-137">会話のレビューセットでは、スレッド化されたスレッドビューでメッセージに注釈を付け、タグを付けて、墨消しすることができます。</span><span class="sxs-lookup"><span data-stu-id="53069-137">In a conversation review set, you can annotate, tag, and redact messages in a threaded conversation view.</span></span> 

<span data-ttu-id="53069-138">レビューセットのコンテンツを確認および管理する方法の詳細については、「 [review sets を管理](managing-review-sets.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53069-138">For more information about how to review and manage content in a review set, see [Manage review sets](managing-review-sets.md).</span></span> 

## <a name="step-3-enable-conversation-retrieval-options"></a><span data-ttu-id="53069-139">手順 3: 会話取得オプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="53069-139">Step 3: Enable conversation retrieval options</span></span>

<span data-ttu-id="53069-140">検索クエリを確認して終了したら、検索結果をレビューセットに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="53069-140">After you have reviewed and finalized your search query, you can add the search results to a review set.</span></span> <span data-ttu-id="53069-141">検索結果をレビューセットに追加すると、元のデータが Azure ストレージ領域にコピーされ、レビューと分析のプロセスが容易になります。</span><span class="sxs-lookup"><span data-stu-id="53069-141">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="53069-142">検索結果をレビューセットに追加する方法の詳細については、「[レビューセットに検索結果を追加](add-data-to-review-set.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53069-142">For more information about adding search results to a review set, see [Add search results to a review set](add-data-to-review-set.md).</span></span> 

<span data-ttu-id="53069-143">会話のデータをレビューセットに追加するときは、会話の取得オプションを使用して、検索を展開し、コンテキストメッセージを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="53069-143">When you add data from conversations to a review set, you can use the conversation retrieval options to expand your search and include contextual messages.</span></span> <span data-ttu-id="53069-144">会話の取得オプションを設定すると、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="53069-144">After you set the conversation retrieval options, the following things can happen:</span></span>

  ![会話の取得](../media/messagesandconversations.png)
  
1. <span data-ttu-id="53069-146">キーワードと日付範囲のクエリを使用して、検索によって*メッセージ 3*でヒットが返されました。</span><span class="sxs-lookup"><span data-stu-id="53069-146">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="53069-147">このメッセージは、 *CRC1*で示されている、より大きな会話の一部でした。</span><span class="sxs-lookup"><span data-stu-id="53069-147">This message was part of a larger conversation, illustrated by *CRC1*.</span></span> 
  
2. <span data-ttu-id="53069-148">データをレビューセットに追加し、会話の取得オプションを有効にすると、Advanced eDiscovery は*CRC1*の他のアイテムを収集して収集します。</span><span class="sxs-lookup"><span data-stu-id="53069-148">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span> 
  
3. <span data-ttu-id="53069-149">アイテムがレビューセットに追加されたら、 *CRC1*からすべての個別のメッセージを確認できます。</span><span class="sxs-lookup"><span data-stu-id="53069-149">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span> 



<span data-ttu-id="53069-150">会話の取得を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="53069-150">To enable conversation retrieval:</span></span>
  
1. <span data-ttu-id="53069-151">高度な電子情報開示ケースの [**検索**] タブで、検索を選択し、フライアウトページの [**レビューセットに追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="53069-151">On the **Searches** tab in the Advanced eDiscovery case, select a search, and then click **Add to review set** on the flyout page.</span></span>
  
2. <span data-ttu-id="53069-152">既存のレビューセットを選択するか、レビューセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="53069-152">Select an existing review set or create a review set.</span></span> <span data-ttu-id="53069-153">検索結果を標準または会話のレビューセットに追加するときに、取得オプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="53069-153">You can configure retrieval options when adding search results to a standard or a conversation review set.</span></span>
  
3. <span data-ttu-id="53069-154">検索で展開するコンテンツソースの会話取得オプションを構成し、[**追加**] をクリックしてプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="53069-154">Configure the conversation retrieval options for the content sources that you would like to expand in your search, and then click **Add** to start the process.</span></span>  
  
4. <span data-ttu-id="53069-155">[**ジョブ**] タブの [**レビューの設定**] ジョブの追加が完了したら、会話の確認を開始できます。</span><span class="sxs-lookup"><span data-stu-id="53069-155">After the **Add to review set** job on the **Jobs** tab has finished, you can start reviewing the conversations.</span></span>

## <a name="step-4-review-conversations-in-the-review-set"></a><span data-ttu-id="53069-156">手順 4: レビューセットの会話をレビューする</span><span class="sxs-lookup"><span data-stu-id="53069-156">Step 4: Review conversations in the review set</span></span>

<span data-ttu-id="53069-157">コンテンツが処理されてからレビューセットに追加されると、レビューセット内のデータの確認を開始できます。</span><span class="sxs-lookup"><span data-stu-id="53069-157">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="53069-158">レビュー機能は、コンテンツが標準のレビューセットまたは会話のレビューセットに追加されたかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="53069-158">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span> 

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="53069-159">標準の校閲セットで会話を確認する</span><span class="sxs-lookup"><span data-stu-id="53069-159">Reviewing conversations in a standard review Set</span></span>

<span data-ttu-id="53069-160">標準の校閲セットでは、メッセージが処理され、メールボックスフォルダーに格納されているのと同じように、個別のアイテムとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="53069-160">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="53069-161">このワークフローでは、各メッセージは個別のアイテムとして処理されます。</span><span class="sxs-lookup"><span data-stu-id="53069-161">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="53069-162">その結果、スレッド化された概要およびエクスポートオプションは、標準のレビューセットでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="53069-162">As a result, the threaded summary and export options aren't available in a standard review set.</span></span> 

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="53069-163">会話レビューセット内の会話のレビュー</span><span class="sxs-lookup"><span data-stu-id="53069-163">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="53069-164">会話レビューセットでは、個々のメッセージが連結され、スレッドとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="53069-164">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="53069-165">これにより、コンテキスト会話を確認およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="53069-165">This lets you review and export contextual conversations.</span></span> <span data-ttu-id="53069-166">次のセクションでは、会話レビューセットでの会話のレビューとエクスポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="53069-166">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="53069-167">会話のレビュー</span><span class="sxs-lookup"><span data-stu-id="53069-167">Reviewing conversations</span></span>

<span data-ttu-id="53069-168">会話レビューセットでは、次のオプションを使用して、レビュープロセスを円滑化できます。</span><span class="sxs-lookup"><span data-stu-id="53069-168">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="53069-169">**会話でグループ化:** 同じ会話内のメッセージをグループ化して、ユーザーがレビュープロセスを簡略化して速やかに実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="53069-169">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span> 

- <span data-ttu-id="53069-170">**概要ビュー:** スレッドのスレッドを表示します。</span><span class="sxs-lookup"><span data-stu-id="53069-170">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="53069-171">このビューには、会話全体が表示され、個々のメッセージのメタデータにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="53069-171">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="53069-172">個々のメッセージのメタデータを表示する</span><span class="sxs-lookup"><span data-stu-id="53069-172">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="53069-173">個別のメッセージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="53069-173">Download individual messages</span></span>

- <span data-ttu-id="53069-174">**テキストビュー:** 会話全体の抽出テキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="53069-174">**Text view:** Provides the extracted text for the entire conversation.</span></span> 

- <span data-ttu-id="53069-175">**ビューに注釈を付ける:** 会話のスレッド化されたビューをマークアップできます。</span><span class="sxs-lookup"><span data-stu-id="53069-175">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="53069-176">会話内のすべてのメッセージは、同じ注釈付きドキュメントを共有します。</span><span class="sxs-lookup"><span data-stu-id="53069-176">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="53069-177">**タグ:** 校閲セットで会話を表示する場合は、[**コーディング] パネル**をクリックしてタグを表示し、適用することができます。</span><span class="sxs-lookup"><span data-stu-id="53069-177">**Tag:** When viewing conversations in a review set, you can view and apply tags by clicking the **Coding panel**.</span></span>

- <span data-ttu-id="53069-178">**会話の再実行変換:** メッセージが会話のレビューセットに追加されると、変換ジョブが自動的に実行され、スレッド化された概要が作成され、ビューに注釈が付けられます。</span><span class="sxs-lookup"><span data-stu-id="53069-178">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="53069-179">会話の再構築ジョブが失敗した場合は、[> アクション] をクリックして [レビューセットに**会話 pdf を作成**する] をクリックすると、変換ジョブを再実行できます。</span><span class="sxs-lookup"><span data-stu-id="53069-179">If the Conversation Reconstruction job fails, you can rerun the conversion job by clicking **Action > Create conversation PDFs** in the review set.</span></span>


#### <a name="exporting-conversations"></a><span data-ttu-id="53069-180">会話をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="53069-180">Exporting conversations</span></span>

<span data-ttu-id="53069-181">会話のレビューセットでは、次のオプションを設定して会話をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="53069-181">In a conversation review set, you can set the following options to export conversations:</span></span>

![エクスポート](../media/export.png)

<span data-ttu-id="53069-183">a.</span><span class="sxs-lookup"><span data-stu-id="53069-183">a.</span></span> <span data-ttu-id="53069-184">メタデータオプション</span><span class="sxs-lookup"><span data-stu-id="53069-184">Metadata options</span></span>

   - <span data-ttu-id="53069-185">**ファイルの読み込み:** 各メッセージ、電子メール、およびドキュメントのメタデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="53069-185">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="53069-186">会話内のメッセージごとに1つの行があります。</span><span class="sxs-lookup"><span data-stu-id="53069-186">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="53069-187">**タグ:** レビュープロセスからのタグはメタデータファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="53069-187">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="53069-188">スレッド内のメッセージは、同じタグを共有します。</span><span class="sxs-lookup"><span data-stu-id="53069-188">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="53069-189">b.</span><span class="sxs-lookup"><span data-stu-id="53069-189">b.</span></span> <span data-ttu-id="53069-190">会話オプション</span><span class="sxs-lookup"><span data-stu-id="53069-190">Conversation options</span></span>
  
   - <span data-ttu-id="53069-191">**会話ファイル:** 会話ファイルをエクスポートすると、注釈付きのビューは PDF ファイルに変換され、エクスポートフォルダーにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="53069-191">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="53069-192">1つのスレッドファイル内のメッセージは、同じ会話ファイルの PDF バージョンをポイントします。</span><span class="sxs-lookup"><span data-stu-id="53069-192">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="53069-193">**個別のチャットメッセージ:** 個々のメッセージをエクスポートすると、スレッド内の一意の各メッセージがスタンドアロンのアイテムとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="53069-193">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="53069-194">ファイルは、メールボックスに保存されたのと同じ形式でエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="53069-194">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="53069-195">特定の会話では、複数の .msg ファイルを受信します。</span><span class="sxs-lookup"><span data-stu-id="53069-195">For a specific conversation, you receive multiple .msg files.</span></span> 

     >[!NOTE]
     > <span data-ttu-id="53069-196">会話ファイルにコメントを適用した場合、これらの注釈は個別のメッセージに転送されません。</span><span class="sxs-lookup"><span data-stu-id="53069-196">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span> 

<span data-ttu-id="53069-197">c.</span><span class="sxs-lookup"><span data-stu-id="53069-197">c.</span></span> <span data-ttu-id="53069-198">その他のオプション</span><span class="sxs-lookup"><span data-stu-id="53069-198">Other options</span></span>

   - <span data-ttu-id="53069-199">エクスポートされた**すべてのコンテンツのテキストファイルを生成します。** レビューセットからエクスポートされた各会話のテキストファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="53069-199">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span> 

   - <span data-ttu-id="53069-200">**エクスポートされたコンテンツをが pdf に置換する:** レビュープロセス中にが会話ファイルが生成された場合、これらのファイルはエクスポート中に利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="53069-200">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="53069-201">このオプションを選択しないでネイティブファイルのみをエクスポートするか、ネイティブファイルをがバージョンのネイティブファイル (このオプションを選択することによって) に置き換えるかを決定できます。これは、PDF ファイルとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="53069-201">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="53069-202">詳細情報</span><span class="sxs-lookup"><span data-stu-id="53069-202">More information</span></span>

<span data-ttu-id="53069-203">上級電子情報開示でケースデータを確認する方法の詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53069-203">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="53069-204">ケースデータを表示する</span><span class="sxs-lookup"><span data-stu-id="53069-204">View case data</span></span>](view-documents-in-review-set.md) 

- [<span data-ttu-id="53069-205">ケース データを分析する</span><span class="sxs-lookup"><span data-stu-id="53069-205">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="53069-206">ケース データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="53069-206">Export case data</span></span>](exporting-data-ediscover20.md)
