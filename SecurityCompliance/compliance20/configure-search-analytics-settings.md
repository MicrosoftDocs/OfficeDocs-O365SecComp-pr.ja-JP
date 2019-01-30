---
title: 検索および分析の設定を構成します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d9528a4bcfaa77f2e232b25d03eda46cce42ebb9
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608015"
---
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="43585-102">検索および分析の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="43585-102">Configure search and analytics settings</span></span>


## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="43585-103">複製し、電子メールのスレッドに近い</span><span class="sxs-lookup"><span data-stu-id="43585-103">Near duplicates and email threading</span></span>

<span data-ttu-id="43585-104">ここでは、近くにある重複データの検出、および電子メールのスレッド、重複データ検出のパラメーターを設定できます。</span><span class="sxs-lookup"><span data-stu-id="43585-104">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="43585-p101">: を有効または無効には、重複データの検出、および電子メールのスレッドが有効な場合の分析フローの一部として近くの重複データ検出が含まれてください。互いの上に構築されるためは、それらのすべてを有効にするまたはそれらのすべてを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43585-p101">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled. Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="43585-107">しきい値: 2 つのドキュメントの類似性のレベルがしきい値を超える場合は、それらを保存する複製セットの近くにある同じです。</span><span class="sxs-lookup"><span data-stu-id="43585-107">Threshold: if the similarity level of two documents are above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="43585-p102">既定で重複データを非表示: 動作中の既定の設定で重複するドキュメントを非表示にフィルターを適用する、この設定がオンの場合。ワーキング セットのために必要な場合に、フィルターを手動で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="43585-p102">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default. The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="43585-p103">単語の最小/最大数: 単語の最小数と最大の単語の最大数以上になっているドキュメント上でのみ実行スレッド重複および e メールの近くです。詳細については、[重複データ検出の近く](near-duplicates.md)には」および「[電子メールのスレッド](email-threading.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43585-p103">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words. For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="43585-112">テーマ</span><span class="sxs-lookup"><span data-stu-id="43585-112">Themes</span></span>

<span data-ttu-id="43585-113">このセクションでは、テーマのパラメーターを設定できます。</span><span class="sxs-lookup"><span data-stu-id="43585-113">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="43585-114">: を有効または無効には、テーマが有効になっている場合、分析フローの一部としてのクラスタ リングが含まれてください。</span><span class="sxs-lookup"><span data-stu-id="43585-114">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>
- <span data-ttu-id="43585-p104">テーマの最大数を動的に動的に調整する: 特定の状況では、あるないテーマの必要な数を生成するための十分なドキュメントです。この設定がオンの場合、テーマの目的の最大数を強制するのではなくシステムを調整テーマの最大数に動的に。</span><span class="sxs-lookup"><span data-stu-id="43585-p104">Adjust maximum number of themes dynamically dynamically: in certain cases, there are not enough documents to produce the desired number of themes. If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>
- <span data-ttu-id="43585-117">テーマの最大数: 目的のテーマの数</span><span class="sxs-lookup"><span data-stu-id="43585-117">Maximum number of themes: desired number of themes</span></span>
- <span data-ttu-id="43585-118">テーマに番号を含める: 有効にすると、テーマを生成するときに数値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="43585-118">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="43585-119">光学式文字認識 (OCR)</span><span class="sxs-lookup"><span data-stu-id="43585-119">Optical character recognition (OCR)</span></span>

<span data-ttu-id="43585-120">この設定を有効にすると検索できるので、ワーキング セットに取り込まれ、イメージに OCR が実行されます。</span><span class="sxs-lookup"><span data-stu-id="43585-120">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="43585-121">テキストを無視します。</span><span class="sxs-lookup"><span data-stu-id="43585-121">Ignore text</span></span>

<span data-ttu-id="43585-p105">インスタンスの特定のテキストが電子メールの内容に関係なく特定の電子メールに追加する時間がかかるの免責事項など、分析の質を低下があります。このような場合に注意してください場合から除外することこのテキスト分析 (正規表現がサポートされている) テキストとを指定してモジュールのテキストを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43585-p105">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email. If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>