---
title: Office 365 の高度な電子情報開示を使用してケースデータを分析する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dce7a700-3b6e-435f-88ba-e4b82c0f2b26
description: '分析プロセスの概要を説明します。これにより、Office 365 の Advanced eDiscovery でパラメーター、実行オプション、および結果の表示を設定できます。 '
ms.openlocfilehash: 11ef6f9bd052134625012742e64c466ae1e54f91
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30998930"
---
# <a name="analyze-case-data-with-office-365-advanced-ediscovery"></a><span data-ttu-id="05a3f-103">Office 365 の高度な電子情報開示を使用してケースデータを分析する</span><span class="sxs-lookup"><span data-stu-id="05a3f-103">Analyze case data with Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="05a3f-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="05a3f-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="05a3f-106">高度な電子情報開示の**準備** \> **分析**プロセスは、次の機能を添付ファイルに適用します。</span><span class="sxs-lookup"><span data-stu-id="05a3f-106">The **Prepare** \> **Analyze** process in Advanced eDiscovery applies the following functionality to the included files:</span></span> 
  
- <span data-ttu-id="05a3f-107">読み込まれたファイルを識別し、一意のファイル、重複、およびほぼ重複したグループに整理します。</span><span class="sxs-lookup"><span data-stu-id="05a3f-107">Identifies and organizes the loaded files into groups of unique files, duplicates, and near-duplicates.</span></span>
    
- <span data-ttu-id="05a3f-108">メールのプログレッシブ inclusiveness に基づいて、メールスレッドの階層構造のグループに電子メールを識別して整理します。</span><span class="sxs-lookup"><span data-stu-id="05a3f-108">Identifies and organizes emails into hierarchically structured groups of email threads, based on the progressive inclusiveness of the emails.</span></span>
    
- <span data-ttu-id="05a3f-109">高度な電子情報開示処理およびファイルのバッチ処理でテーマを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="05a3f-109">Enables the use of Themes in Advanced eDiscovery processing and file batching.</span></span>
    
 <span data-ttu-id="05a3f-110">Analyze では、次のようにパラメーターを設定し、オプションを実行し、結果を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="05a3f-110">Analyze allows you to set parameters, run options, and view the results, as follows:</span></span> 
  
- <span data-ttu-id="05a3f-111">**セットアップの分析**: ファイルの分析を実行する前に設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="05a3f-111">**Analyze setup**: Allows settings to be specified before running Analyze on the files.</span></span>
    
- <span data-ttu-id="05a3f-112">**結果の分析**: 分析の測定基準を表示します。</span><span class="sxs-lookup"><span data-stu-id="05a3f-112">**Analyze results**: Displays metrics of the analysis.</span></span> 
    
<span data-ttu-id="05a3f-113">Analyze を実行する前に、どのロードされたファイルを分析するか、それぞれの種類のファイルを送信する分析の種類など、ファイルを選択して処理するための基準を定義します。</span><span class="sxs-lookup"><span data-stu-id="05a3f-113">Before running Analyze, define the criteria for selecting and processing files, including which loaded files will be analyzed and the type of analysis to which each type of file will be submitted.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="05a3f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="05a3f-114">See also</span></span>

[<span data-ttu-id="05a3f-115">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="05a3f-115">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="05a3f-116">ドキュメントの類似点について</span><span class="sxs-lookup"><span data-stu-id="05a3f-116">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="05a3f-117">無視するテキストの設定</span><span class="sxs-lookup"><span data-stu-id="05a3f-117">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
<span data-ttu-id="05a3f-118">[[詳細設定の分析] の設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="05a3f-118">[Setting Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md)</span></span>
  
[<span data-ttu-id="05a3f-119">分析タスクを表示する</span><span class="sxs-lookup"><span data-stu-id="05a3f-119">Viewing Analyze tasks</span></span>](view-analyze-results-in-advanced-ediscovery.md)

