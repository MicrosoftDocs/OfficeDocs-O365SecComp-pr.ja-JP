---
title: Office 365 Advanced eDiscovery で関連度の設定を管理する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
description: ファイルをそれぞれの関連度でスコアリングして分析結果を生成するには、Office 365 Advanced eDiscovery で関連度トレーニングを設定するための推奨事項を参照してください。
ms.openlocfilehash: 7e06be032cc653681c19ee2d17547ca22421e0ae
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259665"
---
# <a name="manage-relevance-setup-in-office-365-advanced-ediscovery"></a><span data-ttu-id="4c084-103">Office 365 Advanced eDiscovery で関連度の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="4c084-103">Manage Relevance setup in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="4c084-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="4c084-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="4c084-p102">Advanced eDiscovery の関連度テクノロジでは、ファイルをそれぞれの関連度でスコアリングするためのエキスパート ガイド型ソフトウェアを使用しています。Advanced eDiscovery の関連度は、早期ケース評価 (ECA)、選別、ファイル サンプル レビューに使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c084-p102">Advanced eDiscovery Relevance technology employs expert-guided software for scoring files by their relevance. Advanced eDiscovery Relevance can be used for Early Case Assessment (ECA), culling, and file sample review.</span></span> 
  
 <span data-ttu-id="4c084-p103">Advanced eDiscovery には、ケースに関連するファイルの関連度トレーニングとタグ付けのためのコンポーネントが含まれます。Advanced eDiscovery は、関連ファイルと非関連ファイルのトレーニング サンプルから学習し、各ファイルの関連度スコアを示して、分析結果を生成します。この分析結果は、ファイル レビュー プロセスの最中や後で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c084-p103">Advanced eDiscovery includes components for the Relevance training and tagging of files relevant to a case. Advanced eDiscovery learns from the trained samples of Relevant and Not Relevant files to provide Relevance scores for each file, and generates analytical results that can be used during and after the file review process.</span></span> 
  
## <a name="guidelines-for-setting-up-relevance-training"></a><span data-ttu-id="4c084-110">関連度トレーニングを設定するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="4c084-110">Guidelines for setting up Relevance training</span></span>

 <span data-ttu-id="4c084-p104">Advanced eDiscovery の **[ケース]** ウィンドウで、ケースを選択し、**[ケースに移動]** をクリックします。**[関連度]** \> **[関連度の設定]** をクリックします。以下の推奨ガイドラインに従って、関連度を設定してください。</span><span class="sxs-lookup"><span data-stu-id="4c084-p104">In Advance eDiscovery, in the **Cases** window, select a case and click **Go to case**. Click **Relevance** \> **Relevanace setup**. Follow these recommended guidelines to setup Relevance.</span></span> 
  
- <span data-ttu-id="4c084-114">**タグ付け**: 繰り返し行われる関連度トレーニング プロセスの効率は、正確性と一貫性を持ってファイル サンプルにタグ付けするエキスパートの能力に依存します。</span><span class="sxs-lookup"><span data-stu-id="4c084-114">**Tagging**: The effectiveness of the iterative Relevance training process is dependent on the ability of the expert to tag the file samples with precision and consistency.</span></span>
    
- <span data-ttu-id="4c084-115">**ケースの問題**:</span><span class="sxs-lookup"><span data-stu-id="4c084-115">**Case issues**:</span></span> 
    
  - <span data-ttu-id="4c084-p105">問題ごとに、関連度トレーニング プロセス全体を通して同じエキスパートを使用してください。複数のエキスパートが同じ問題に同時にタグ付けすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4c084-p105">For each issue, use the same expert throughout the entire Relevance training process. Simultaneous tagging of the same issue by multiple experts is not permitted.</span></span>
    
  - <span data-ttu-id="4c084-118">ファイルの各グループが特定の問題にのみ関連するかどうかを判断してください。</span><span class="sxs-lookup"><span data-stu-id="4c084-118">Determine if each group of files is pertinent only to a specific issue.</span></span> 
    
  - <span data-ttu-id="4c084-p106">問題の定義が一般的すぎると、Advanced eDiscovery は実際は関連のないファイルを大量に生成する場合があります。問題の定義が狭すぎると、関連度トレーニング プロセスに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4c084-p106">If an issue is defined too generally, Advanced eDiscovery may yield too many files that are actually not relevant. If an issue is defined too narrowly, the Relevance training process may take more time.</span></span> 
    
  - <span data-ttu-id="4c084-121">関連度トレーニング サイクル中、Advanced eDiscovery は 1 つのアクティブな問題に焦点を合わせ、サンプルの中間結果が適宜表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c084-121">During each Relevance training cycle, Advanced eDiscovery focuses on a single active issue and interim sample results are displayed accordingly.</span></span>
    
  - <span data-ttu-id="4c084-p107">問題が複数あるシナリオでは、サンプリング モードを使用することで、処理に含める問題を選択できます。「オフ」として定義された問題は、サンプリング モードが変更されるまで扱われません。1 人のエキスパートに対してのみ問題を「アイドル」または「オン」にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4c084-p107">In a multiple-issue scenario, the Sampling mode enables the selection of issues to be included in processing. Issues defined as "off" are not handled until their Sampling mode is changed. An issue can be "idle" or "on" for only one expert.</span></span>
    
  -  <span data-ttu-id="4c084-p108">Advanced eDiscovery を使用して、特権ファイル候補を生成できます。特権を目的とした別個の問題を設定します。可能であれば、まず関連度を目的としてトレーニングして選別し、次に、選別したセットのみを対象に特権を目的としてトレーニングします (選別したセットを別個のケースとして再読み込みします)。</span><span class="sxs-lookup"><span data-stu-id="4c084-p108">Advanced eDiscovery can be used to generate candidate privilege files. Set up a separate issue for privilege. If possible, train and cull for relevance first, and then train for privilege on the culled set only (reload the culled set as a separate case).</span></span> 
    
  - <span data-ttu-id="4c084-p109">バッチ計算を行えるのは、開いているサンプルがないときだけです ([バッチ計算] をクリックすると、サンプルを開いているユーザーの一覧が表示されます)。他のユーザーのサンプルを「閉じる」場合 (この操作は他のユーザーがそれらのサンプルにタグ付けしていない場合のみ行う必要があります)、管理者は「すべてのユーザーのサンプル」オプションを指定した「関連度の変更」ユーティリティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c084-p109">Batch calculation can be performed only when there are no open samples (when clicking Batch Calculation, there will be a list displayed of users with open samples). To "close" samples of other users (this should be performed only if these users are not tagging these samples), an Administrator can use the "Modify relevance" utility with the "All users sample" option.</span></span>
    
- <span data-ttu-id="4c084-p110">**メタデータ**: Advanced eDiscovery はコンテンツに焦点を合わせます。メタデータは関連度抽出条件の一部として考慮されません。</span><span class="sxs-lookup"><span data-stu-id="4c084-p110">**Metadata**: Advanced eDiscovery focuses on content. It does not consider metadata as part of the relevance criteria.</span></span> 
    
- <span data-ttu-id="4c084-132">**リッチ度**: 評価の結果、問題のリッチ度が 3% 未満の場合は、既知の関連ファイルと非関連ファイルで関連度トレーニングをシードすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4c084-132">**Richness**: If the Richness for an issue is less than 3% after Assessment, consider seeding the Relevance training with known Relevant and Not Relevant files.</span></span>
    
- <span data-ttu-id="4c084-p111">**ファイル サイズ**: 大きなファイル (抽出されたテキストが 5,242,880 文字を超えるファイル) は関連度で無視されます。このようなファイルは関連度トレーニング プロセスに参加しないため、バッチ計算後に関連度スコアは表示されません。評価セットには 5 MB を超えるファイルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4c084-p111">**File size**: Large files (over 5,242,880 characters of extracted text) are ignored in Relevance. The files do not participate in the Relevance training process and do not receive a Relevance score after Batch Calculation. Files over 5MB can be included in the Assessment set.</span></span>
    
## <a name="setting-up-case-issues"></a><span data-ttu-id="4c084-136">ケースの問題の設定</span><span class="sxs-lookup"><span data-stu-id="4c084-136">Setting up case issues</span></span>

<span data-ttu-id="4c084-137">このセクションで説明するパラメーターは、Advanced eDiscovery の **[関連度]** \> **[関連度の設定]** で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c084-137">The parameters described in this section are available in the Advanced eDiscovery **Relevance** \> **Relevance setup**.</span></span> 
  
- <span data-ttu-id="4c084-138">ファイルをトレーニングするユーザーに問題を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c084-138">Issues must be assigned to a user who will train the files.</span></span>
    
- <span data-ttu-id="4c084-139">次に、インポートしたファイルを、処理中のロードに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c084-139">Imported files must then be added to the load being processed.</span></span>
    
- <span data-ttu-id="4c084-140">慎重に問題を定義して編成してください。関連度トレーニングの結果に影響を及ぼす可能性があるからです。</span><span class="sxs-lookup"><span data-stu-id="4c084-140">Define and organize issues carefully, as this can impact the Relevance training results.</span></span>
    
<span data-ttu-id="4c084-141">パラメーターの設定後、レビュー担当者/エキスパートは **[関連度]** タブでファイルのトレーニングを開始できます。</span><span class="sxs-lookup"><span data-stu-id="4c084-141">After parameters are set, the reviewer / expert can start training the files in the **Relevance** tab.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4c084-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c084-142">See also</span></span>

[<span data-ttu-id="4c084-143">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4c084-143">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="4c084-144">問題の定義とユーザーの割り当て</span><span class="sxs-lookup"><span data-stu-id="4c084-144">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="4c084-145">インポートしたファイルを追加するためのロードの設定</span><span class="sxs-lookup"><span data-stu-id="4c084-145">Setting up loads to add imported files</span></span>](set-up-loads-to-add-imported-files.md)
  
[<span data-ttu-id="4c084-146">強調表示されたキーワードと詳細オプションの定義</span><span class="sxs-lookup"><span data-stu-id="4c084-146">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

