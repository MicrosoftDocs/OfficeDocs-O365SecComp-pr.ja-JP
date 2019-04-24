---
title: Set Office 365 の詳細な電子情報開示の設定を分析する
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
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: 'Office 365 advanced eDiscovery の分析プロセスについて、ほぼ重複、電子メールスレッド、テーマなどの高度な設定を構成する方法について説明します。 '
ms.openlocfilehash: d8dfb9f3ecfcda0f267dfccdc716eda40fe450b2
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260862"
---
# <a name="set-analyze-advanced-settings-in-office-365-advanced-ediscovery"></a><span data-ttu-id="e90c6-103">Set Office 365 の詳細な電子情報開示の設定を分析する</span><span class="sxs-lookup"><span data-stu-id="e90c6-103">Set Analyze advanced settings in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="e90c6-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="e90c6-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="e90c6-106">advanced eDiscovery は、モジュール設定を分析するための既定の高度なパラメーターを提供します。</span><span class="sxs-lookup"><span data-stu-id="e90c6-106">Advanced eDiscovery provides default advanced parameters for Analyze module settings.</span></span> <span data-ttu-id="e90c6-107">次の手順では、指定可能な設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="e90c6-107">The following procedure describes settings that can be specified.</span></span>
  
1. <span data-ttu-id="e90c6-108">[ \*\* \> Analyze \> **の設定の準備] タブで、[**詳細設定\*\*] (ページの下部) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e90c6-108">In the **Prepare \> Analyze \> Setup** tab, click **Advanced settings** (at the bottom of the page).</span></span> <span data-ttu-id="e90c6-109">次のパネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e90c6-109">The following panel is displayed.</span></span> 
    
    ![分析設定の拡張設定](media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. <span data-ttu-id="e90c6-111">[**ほぼ重複] および [電子メールスレッド] パラメーター**で、必要に応じて次の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="e90c6-111">In **Near-duplicates and Email threads parameters**, select values for the following as necessary:</span></span>
    
  - <span data-ttu-id="e90c6-112">**少なく**とも1つの単語の最小数: ファイルがほぼ重複した分析のために送信されません。</span><span class="sxs-lookup"><span data-stu-id="e90c6-112">**Minimum number of words**: Minimum number for words, below which a file is not submitted for Near-duplicate analysis.</span></span> 
    
  - <span data-ttu-id="e90c6-113">**単語の**最大数: 単語の最大数。これは、ほぼ重複した分析のためにファイルが送信されません。</span><span class="sxs-lookup"><span data-stu-id="e90c6-113">**Maximum number of words**: Maximum number for words, above which a file is not submitted for Near-duplicate analysis.</span></span>
    
  - <span data-ttu-id="e90c6-114">**電子メールの類似性**: 2 通の電子メールについては、resemblance の最低限のレベルで類似したものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="e90c6-114">**Email similarity**: Minimal level of resemblance for two emails to be considered similar.</span></span> <span data-ttu-id="e90c6-115">値は常に等しいか、ドキュメントの類似性よりも大きい値です。</span><span class="sxs-lookup"><span data-stu-id="e90c6-115">Value is always equal to, or larger than document similarity.</span></span> <span data-ttu-id="e90c6-116">既定値は 90% です。</span><span class="sxs-lookup"><span data-stu-id="e90c6-116">Default is 90%.</span></span>
    
3. <span data-ttu-id="e90c6-117">[テーマの**パラメーター**] で、[**テーマの分析に数字を含める**] チェックボックスをオンにして、分析中のテーマの処理に番号を含めます。</span><span class="sxs-lookup"><span data-stu-id="e90c6-117">In **Themes parameters**, select the **Include numbers in theme analysis** check box to include numbers in the processing of Themes during Analyze.</span></span> 
    
4. <span data-ttu-id="e90c6-118">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e90c6-118">Click **Save**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="e90c6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e90c6-119">See also</span></span>

[<span data-ttu-id="e90c6-120">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e90c6-120">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="e90c6-121">ドキュメントの類似点について</span><span class="sxs-lookup"><span data-stu-id="e90c6-121">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e90c6-122">分析オプションの設定</span><span class="sxs-lookup"><span data-stu-id="e90c6-122">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e90c6-123">無視するテキストの設定</span><span class="sxs-lookup"><span data-stu-id="e90c6-123">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e90c6-124">分析結果の表示</span><span class="sxs-lookup"><span data-stu-id="e90c6-124">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

