---
title: Office 365 Advanced eDiscovery で分析結果を表示する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: '表示されているタスクオプションの定義を含む、Office 365 Advanced eDiscovery の分析プロセスの結果を表示する場所について説明します。  '
ms.openlocfilehash: 990bcbb3c6626521d40f7ce057c764200d5047b5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218827"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="d815f-103">Office 365 Advanced eDiscovery で分析結果を表示する</span><span class="sxs-lookup"><span data-stu-id="d815f-103">View Analyze results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="d815f-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="d815f-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="d815f-106">詳細な電子情報開示では、以下に示すように、分析プロセスの進行状況と結果をさまざまな方法で表示できます。</span><span class="sxs-lookup"><span data-stu-id="d815f-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="d815f-107">タスクの進捗状況を表示する</span><span class="sxs-lookup"><span data-stu-id="d815f-107">View Analyze task status</span></span>

<span data-ttu-id="d815f-108">[**結果\> \>の\>分析タスクの状態の準備**] では、プロセスの実行中および分析後に状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d815f-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![タスクの進捗状況の分析](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="d815f-110">表示されるタスクは、選択したオプションによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d815f-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="d815f-111">**ND/ET: セットアップ**: 実行の準備をします。たとえば、run および case パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="d815f-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="d815f-112">**nd/ET: nd 計算**: ファイルのほぼ重複した分析を処理します。</span><span class="sxs-lookup"><span data-stu-id="d815f-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="d815f-113">**ND/et: et 計算**: 電子メールセット全体で電子メールスレッド分析を実行します。</span><span class="sxs-lookup"><span data-stu-id="d815f-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="d815f-114">**ND/ET: pivot and 類似性**: ピボットおよびファイル類似性処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="d815f-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="d815f-115">[ **ND/ET: metadata update**]: データベース内のファイルで収集された新しいデータがファイナライズされます。</span><span class="sxs-lookup"><span data-stu-id="d815f-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="d815f-p102">**テーマ: テーマの計算**: テーマの分析を実行します。(選択されている場合のみ表示されます)。</span><span class="sxs-lookup"><span data-stu-id="d815f-p102">**Themes: themes calculation**: Runs themes analysis. (Displayed only if selected.)</span></span>
    
- <span data-ttu-id="d815f-p103">**タスクの状態**: この行は、タスクの完了後に表示されます。タスクの実行中は、実行期間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d815f-p103">**Task status**: This line is displayed after task completion. While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d815f-p104">ほぼ重複した電子メールスレッド (ND および ED) の分析結果は、処理するドキュメント数に適用されます。完全に重複したファイルは含まれません。</span><span class="sxs-lookup"><span data-stu-id="d815f-p104">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed. It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="d815f-122">ほぼ重複した電子メールスレッドの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="d815f-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="d815f-123">**ターゲット**の作成結果には、対象の作成におけるドキュメント、メール、添付ファイル、およびエラーの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d815f-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="d815f-124">**ドキュメント**の結果には、ピボットの数、一意の重複した一意のファイル、および正確な重複ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d815f-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="d815f-p105">電子**メール**の結果には、包括数、包括的な一意の包括的コピー、および残りの電子メールメッセージの数が表示されます。さまざまな種類の電子メールの結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d815f-p105">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages. The different types of email results are:</span></span> 
  
- <span data-ttu-id="d815f-p106">**包括**: 包括的な電子メールは、電子メールスレッドの終了ノードであり、そのスレッドの以前のすべての履歴が含まれています。その結果、レビュー担当者は、スレッド内の前のメッセージを読み取らずに、包括的な電子メールに安全に集中できます。</span><span class="sxs-lookup"><span data-stu-id="d815f-p106">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread. As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="d815f-p107">**包括マイナス**: 包括的な電子メールの親に関連付けられた1つまたは複数の異なる添付ファイルがある場合は、包括的な電子メールが包括を差し引いたものとして指定されます。このコンテキストでは、"Parent" という用語が、その特定の包括的な電子メールに含まれている電子メールスレッドまたは会話の上にあるメッセージに使用されます。レビュー担当者は、包括的なマイナス表示をシグナルとして使用できますが、包括的な電子メールの親の内容を確認する必要はないかもしれませんが、この包含パスの親に関連付けられている添付ファイルを確認すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d815f-p107">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message. In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email. A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="d815f-p108">**包括的コピー**: 包括的なメールまたは包括的なメールが含まれている別のメッセージのコピーである場合は、包括コピーとして指定します。言い換えると、このメッセージの件名と本文は別の包括的なメッセージと同じであり、同じノードに共存しています。包括的なコピーメッセージには同じ内容が含まれているため、通常はレビュープロセスでスキップできます。</span><span class="sxs-lookup"><span data-stu-id="d815f-p108">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus. In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node. Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="d815f-p109">**rest**: これは、一意のコンテンツがまったく含まれていないため、上記の3つのカテゴリに分類されないメールを示します。これらの電子メールメッセージを確認する必要はありません。メッセージに添付ファイルが含まれていて、それより後の包括的な電子メールに含まれていない場合は、添付ファイルのレビューが必要になる可能性があります。これは、スレッド内に包括的なマイナスの電子メールが存在することによって示されます。</span><span class="sxs-lookup"><span data-stu-id="d815f-p109">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories. These email messages don't need to be reviewed. If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed. This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="d815f-139">**添付ファイル**の結果には、重複した種類によって添付ファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d815f-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![類似および電子メールのスレッド](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="d815f-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="d815f-141">See also</span></span>

[<span data-ttu-id="d815f-142">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d815f-142">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="d815f-143">ドキュメントの類似点について</span><span class="sxs-lookup"><span data-stu-id="d815f-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d815f-144">分析オプションの設定</span><span class="sxs-lookup"><span data-stu-id="d815f-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d815f-145">無視するテキストの設定</span><span class="sxs-lookup"><span data-stu-id="d815f-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
<span data-ttu-id="d815f-146">[[詳細設定の分析] の設定](view-analyze-results-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="d815f-146">[Setting Analyze advanced settings](view-analyze-results-in-advanced-ediscovery.md)</span></span>

