---
title: Office 365 Advanced eDiscovery で分析結果を表示する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 'Office 365 の高度な電子的証拠開示、表示されているタスクのオプションの定義の分析処理の結果を表示する場所を理解します。  '
ms.openlocfilehash: 8f1de53e5548c8721f8fbfdb83374edb18379114
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532535"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="c48cc-103">Office 365 Advanced eDiscovery で分析結果を表示する</span><span class="sxs-lookup"><span data-stu-id="c48cc-103">View Analyze results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="c48cc-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="c48cc-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="c48cc-106">高度な電子的証拠開示、進捗状況と分析のプロセスの結果を表示できますさまざまな表示で次のように。</span><span class="sxs-lookup"><span data-stu-id="c48cc-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="c48cc-107">分析タスクの進捗状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="c48cc-107">View Analyze task status</span></span>

<span data-ttu-id="c48cc-108">**準備\>分析\>結果\>タスクの状態**中、および分析のプロセスの実行後の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c48cc-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![タスクの進捗状況の分析](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="c48cc-110">表示するタスクは、選択したオプションによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c48cc-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="c48cc-111">**ND/ET: セットアップ**: たとえば、実行の準備、実行、サポート ・ リクエストのパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="c48cc-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="c48cc-112">**ND/ET: ND 計算**: ファイルの複製に近い分析のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="c48cc-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="c48cc-113">**ND/ET: ET 計算**: 全体の電子メール設定の分析を電子メールのスレッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c48cc-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="c48cc-114">**ND/ET: ピボットと類似点**: ピボットおよびファイル関連の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="c48cc-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="c48cc-115">**ND/ET: メタデータの更新**: データベース内のファイルに収集される新しいデータを終了します。</span><span class="sxs-lookup"><span data-stu-id="c48cc-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="c48cc-p102">**テーマ: テーマの計算**: テーマの分析を実行します。(選択されている場合にのみ表示されます)。</span><span class="sxs-lookup"><span data-stu-id="c48cc-p102">**Themes: themes calculation**: Runs themes analysis. (Displayed only if selected.)</span></span>
    
- <span data-ttu-id="c48cc-p103">**タスクの進捗状況**: タスクの完了時にこの行が表示されます。タスクの実行中は、実行の継続時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c48cc-p103">**Task status**: This line is displayed after task completion. While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c48cc-p104">重複の近くと電子メールのスレッド (ND ED) の分析結果は、処理するドキュメントの数に適用されます。正確な重複しているファイルは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c48cc-p104">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed. It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="c48cc-122">重複の近くに表示され、電子メール スレッドの状態</span><span class="sxs-lookup"><span data-stu-id="c48cc-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="c48cc-123">**ターゲット**人口の結果は、対象になる母集団のドキュメント、メール、添付ファイル、およびエラーの数を表示します。</span><span class="sxs-lookup"><span data-stu-id="c48cc-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="c48cc-124">**ドキュメント**の結果は、ピボット、一意の近くの重複、およびファイルの正確な複製の数を表示します。</span><span class="sxs-lookup"><span data-stu-id="c48cc-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="c48cc-p105">**電子メール**の結果では、包括的、マイナスは、独自の包括的なコピーでは、包括的な数、および電子メール メッセージの残りの部分を表示します。メールの結果の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c48cc-p105">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages. The different types of email results are:</span></span> 
  
- <span data-ttu-id="c48cc-p106">**包括**: 包括的な電子メールは、電子メール スレッドの終端のノードし、そのスレッドのすべての以前の履歴が含まれています。その結果、校閲者はスレッドで前のメッセージを開封することがなく、包括的な電子メールを安全に集中できます。</span><span class="sxs-lookup"><span data-stu-id="c48cc-p106">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread. As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="c48cc-p107">**-包括**: 包括的なメッセージの親に関連付けられている 1 つまたは複数の異なる添付がある場合、包括的なマイナスとして包括的な電子メールが指定されています。このコンテキストには、という用語は、親の上に配置すると、電子メールのスレッドまたは会話でのメッセージに含まれているその特定の包括的なメールです。校閲者は、包括的、包括的な電子メールの親の内容を確認する必要はありませんが、役に立ちます、包括的なパスの親に関連付けられている添付ファイルを確認するシグナルとして示すマイナスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c48cc-p107">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message. In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email. A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="c48cc-p108">**包括的なコピー**: 包括的なコピーが別のメッセージのコピーがある場合マークされているため、包括的またはマイナスの包括的、包括的な電子メールを指定します。つまり、このメッセージ、同じ件名と本文を別の包括的なメッセージとしてがあり、共同で次のような同じノード内に存在します。包括的なコピーのメッセージに同じコンテンツが含まれているため、通常スキップできますレビュー プロセスにします。</span><span class="sxs-lookup"><span data-stu-id="c48cc-p108">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus. In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node. Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="c48cc-p109">**残り**: 電子メールを独自のコンテンツが含まれていないし、したがって、前の 3 つのカテゴリのいずれかに該当しないことを示します。これらの電子メール メッセージを確認する必要はありません。メッセージに後で包括的な電子メールの添付ファイルが含まれている場合、添付ファイルは、情報を確認する必要があります。これは、包括的な電子メール スレッド内でマイナスの存在によって示されます。</span><span class="sxs-lookup"><span data-stu-id="c48cc-p109">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories. These email messages don't need to be reviewed. If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed. This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="c48cc-139">**添付ファイル**の結果は、このような一意の種類と重複によって、添付ファイルの数を表示します。</span><span class="sxs-lookup"><span data-stu-id="c48cc-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![類似および電子メールのスレッド](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="c48cc-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="c48cc-141">See also</span></span>

[<span data-ttu-id="c48cc-142">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c48cc-142">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="c48cc-143">ドキュメントの類似性を理解します。</span><span class="sxs-lookup"><span data-stu-id="c48cc-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c48cc-144">分析オプションの設定</span><span class="sxs-lookup"><span data-stu-id="c48cc-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c48cc-145">設定は無視します。</span><span class="sxs-lookup"><span data-stu-id="c48cc-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c48cc-146">分析の設定の詳細設定</span><span class="sxs-lookup"><span data-stu-id="c48cc-146">Setting Analyze advanced settings</span></span>](view-analyze-results-in-advanced-ediscovery.md)

