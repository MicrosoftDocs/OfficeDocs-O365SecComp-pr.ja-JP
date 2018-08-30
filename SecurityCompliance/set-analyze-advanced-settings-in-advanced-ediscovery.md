---
title: Office 365 Advanced eDiscovery の分析で詳細オプションを設定する
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
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: '重複の近くに、電子メールのスレッド、分析プロセスを Office 365 に高度な電子的証拠開示では、テーマなど、高度な設定を構成する方法について説明します。 '
ms.openlocfilehash: 7ffb80230a43eacb98a9c4ecb569f03cff134aac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531613"
---
# <a name="set-analyze-advanced-settings-in-office-365-advanced-ediscovery"></a><span data-ttu-id="c2bcd-103">Office 365 Advanced eDiscovery の分析で詳細オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="c2bcd-103">Set Analyze advanced settings in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="c2bcd-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="c2bcd-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="c2bcd-p102">高度な電子的証拠開示では、分析モジュールの設定の詳細設定の既定のパラメーターを提供します。次の手順では、指定できる設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2bcd-p102">Advanced eDiscovery provides default advanced parameters for Analyze module settings. The following procedure describes settings that can be specified.</span></span>
  
1. <span data-ttu-id="c2bcd-p103">**の準備\>分析\>セットアップ**] タブで、(ページの下部) の **[詳細設定**] をクリックします。次のパネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2bcd-p103">In the **Prepare \> Analyze \> Setup** tab, click **Advanced settings** (at the bottom of the page). The following panel is displayed.</span></span> 
    
    ![分析設定の拡張設定](media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. <span data-ttu-id="c2bcd-111">**重複の近く、電子メール スレッドのパラメーター**は、必要に応じて、次の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2bcd-111">In **Near-duplicates and Email threads parameters**, select values for the following as necessary:</span></span>
    
  - <span data-ttu-id="c2bcd-112">**単語の最小数**: 重複の近くの分析のため送信されませんファイルを次の単語の最小数。</span><span class="sxs-lookup"><span data-stu-id="c2bcd-112">**Minimum number of words**: Minimum number for words, below which a file is not submitted for Near-duplicate analysis.</span></span> 
    
  - <span data-ttu-id="c2bcd-113">**単語の最大数**: 上にファイルを複製に近い分析のため送信できません、単語の最大数です。</span><span class="sxs-lookup"><span data-stu-id="c2bcd-113">**Maximum number of words**: Maximum number for words, above which a file is not submitted for Near-duplicate analysis.</span></span>
    
  - <span data-ttu-id="c2bcd-p104">**電子メールの類似性**: 最小レベルのような考慮すべき 2 つの電子メールの場合とは異なるのです。値は常に、またはドキュメントの類似性よりも大きい。既定では 90% です。</span><span class="sxs-lookup"><span data-stu-id="c2bcd-p104">**Email similarity**: Minimal level of resemblance for two emails to be considered similar. Value is always equal to, or larger than document similarity. Default is 90%.</span></span>
    
3. <span data-ttu-id="c2bcd-117">**テーマのパラメーター**では、テーマの解析中に処理に番号を追加する [**テーマの分析に番号を含める**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="c2bcd-117">In **Themes parameters**, select the **Include numbers in theme analysis** check box to include numbers in the processing of Themes during Analyze.</span></span> 
    
4. <span data-ttu-id="c2bcd-118">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2bcd-118">Click **Save**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="c2bcd-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2bcd-119">See also</span></span>

[<span data-ttu-id="c2bcd-120">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c2bcd-120">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="c2bcd-121">ドキュメントの類似性を理解します。</span><span class="sxs-lookup"><span data-stu-id="c2bcd-121">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c2bcd-122">分析オプションの設定</span><span class="sxs-lookup"><span data-stu-id="c2bcd-122">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c2bcd-123">設定は無視します。</span><span class="sxs-lookup"><span data-stu-id="c2bcd-123">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c2bcd-124">分析結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="c2bcd-124">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

