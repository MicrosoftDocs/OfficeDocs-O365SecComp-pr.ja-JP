---
title: Office 365 Advanced eDiscovery でケース データを分析する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dce7a700-3b6e-435f-88ba-e4b82c0f2b26
description: 'パラメーターを設定、実行オプション、および電子的証拠開示の Office 365 の詳細設定で、結果を表示するのには、Analyze の処理の概要を取得します。 '
ms.openlocfilehash: d20ce3acb9c21e8c35b098df2ffae3fa6c871c3e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532674"
---
# <a name="analyze-case-data-with-office-365-advanced-ediscovery"></a><span data-ttu-id="d34ce-103">Office 365 Advanced eDiscovery でケース データを分析する</span><span class="sxs-lookup"><span data-stu-id="d34ce-103">Analyze case data with Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="d34ce-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="d34ce-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="d34ce-106">**準備**の\>で高度な電子的証拠開示プロセスを**分析**が含まれているファイルに次の機能を適用します。</span><span class="sxs-lookup"><span data-stu-id="d34ce-106">The **Prepare** \> **Analyze** process in Advanced eDiscovery applies the following functionality to the included files:</span></span> 
  
- <span data-ttu-id="d34ce-107">識別し、グループの一意のファイル、重複、および重複の近くに読み込まれているファイルを整理します。</span><span class="sxs-lookup"><span data-stu-id="d34ce-107">Identifies and organizes the loaded files into groups of unique files, duplicates, and near-duplicates.</span></span>
    
- <span data-ttu-id="d34ce-108">識別し、電子メールのスレッド、電子メールのプログレッシブ inclusiveness に基づいて階層的に構造化されたグループに電子メールを整理します。</span><span class="sxs-lookup"><span data-stu-id="d34ce-108">Identifies and organizes emails into hierarchically structured groups of email threads, based on the progressive inclusiveness of the emails.</span></span>
    
- <span data-ttu-id="d34ce-109">高度な電子的証拠開示処理し、ファイルのバッチ処理でのテーマの使用を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d34ce-109">Enables the use of Themes in Advanced eDiscovery processing and file batching.</span></span>
    
 <span data-ttu-id="d34ce-110">分析オプションを実行し、結果を次のように表示のパラメーターを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="d34ce-110">Analyze allows you to set parameters, run options, and view the results, as follows:</span></span> 
  
- <span data-ttu-id="d34ce-111">**分析の設定**: 設定ファイルの解析を実行する前に指定することができます。</span><span class="sxs-lookup"><span data-stu-id="d34ce-111">**Analyze setup**: Allows settings to be specified before running Analyze on the files.</span></span>
    
- <span data-ttu-id="d34ce-112">**結果の分析**: 分析の指標が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d34ce-112">**Analyze results**: Displays metrics of the analysis.</span></span> 
    
<span data-ttu-id="d34ce-113">Analyze を実行する前に条件を選択して、読み込まれたファイルを分析するなどのファイルを処理および分析の各種類のファイルを送信する先の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="d34ce-113">Before running Analyze, define the criteria for selecting and processing files, including which loaded files will be analyzed and the type of analysis to which each type of file will be submitted.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d34ce-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d34ce-114">See also</span></span>

[<span data-ttu-id="d34ce-115">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d34ce-115">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="d34ce-116">ドキュメントの類似性を理解します。</span><span class="sxs-lookup"><span data-stu-id="d34ce-116">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d34ce-117">設定は無視します。</span><span class="sxs-lookup"><span data-stu-id="d34ce-117">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d34ce-118">分析の設定の詳細設定</span><span class="sxs-lookup"><span data-stu-id="d34ce-118">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d34ce-119">分析のタスクを表示します。</span><span class="sxs-lookup"><span data-stu-id="d34ce-119">Viewing Analyze tasks</span></span>](view-analyze-results-in-advanced-ediscovery.md)

