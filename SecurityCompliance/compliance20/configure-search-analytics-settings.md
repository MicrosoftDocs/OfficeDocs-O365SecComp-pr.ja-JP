---
title: 検索と分析の設定を構成する
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
ms.openlocfilehash: 5aa83f4f736c239b1cdfe940f27cfaa4b981ff64
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155119"
---
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="82e7e-102">検索と分析の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="82e7e-102">Configure search and analytics settings</span></span>


## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="82e7e-103">ほぼ重複、電子メールスレッド</span><span class="sxs-lookup"><span data-stu-id="82e7e-103">Near duplicates and email threading</span></span>

<span data-ttu-id="82e7e-104">このセクションでは、重複データ検出、重複の検出、電子メールのスレッド処理のパラメーターを設定できます。</span><span class="sxs-lookup"><span data-stu-id="82e7e-104">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="82e7e-105">Enable/disable: 重複データ検出、ほぼ重複検出、および電子メールスレッド処理を分析フローの一部として有効にします (有効にした場合)。</span><span class="sxs-lookup"><span data-stu-id="82e7e-105">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled.</span></span> <span data-ttu-id="82e7e-106">これらは互いの上に構築されているため、すべてを有効にするか、すべての設定を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82e7e-106">Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="82e7e-107">しきい値: 2 つのドキュメントの類似性レベルがしきい値を超えている場合は、同じ近くにある重複セットに配置されます。</span><span class="sxs-lookup"><span data-stu-id="82e7e-107">Threshold: if the similarity level of two documents are above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="82e7e-108">既定で重複を非表示にする: この設定をオンにすると、重複したドキュメントを非表示にするためのフィルターが既定でチェックセットに適用されます。</span><span class="sxs-lookup"><span data-stu-id="82e7e-108">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the review set by default.</span></span> <span data-ttu-id="82e7e-109">このフィルターは、必要に応じてレビューセットで手動で削除できます。</span><span class="sxs-lookup"><span data-stu-id="82e7e-109">The filter can be removed manually in the review set if necessary.</span></span>

- <span data-ttu-id="82e7e-110">最小/最大単語数: 重複および電子メールスレッド処理は、少なくとも単語の最小数が少なく、最大で単語数が多いドキュメントに対してのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="82e7e-110">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words.</span></span>
<span data-ttu-id="82e7e-111">詳細については、「[重複の検出](near-duplicates.md)と[電子メールのスレッド処理](email-threading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82e7e-111">For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="82e7e-112">テーマ</span><span class="sxs-lookup"><span data-stu-id="82e7e-112">Themes</span></span>

<span data-ttu-id="82e7e-113">このセクションでは、テーマのパラメーターを設定できます。</span><span class="sxs-lookup"><span data-stu-id="82e7e-113">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="82e7e-114">Enable/disable: 有効になっている場合は、分析フローの一部としてテーマのクラスターを含めます。</span><span class="sxs-lookup"><span data-stu-id="82e7e-114">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>
- <span data-ttu-id="82e7e-115">テーマの最大数を動的に調整する: 場合によっては、必要な数のテーマを作成するだけのドキュメントが存在しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="82e7e-115">Adjust maximum number of themes dynamically dynamically: in certain cases, there are not enough documents to produce the desired number of themes.</span></span> <span data-ttu-id="82e7e-116">この設定が有効になっている場合は、必要なテーマの最大数を強制するのではなく、テーマの最大数をシステムが動的に調整します。</span><span class="sxs-lookup"><span data-stu-id="82e7e-116">If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>
- <span data-ttu-id="82e7e-117">テーマの最大数: 必要なテーマの数</span><span class="sxs-lookup"><span data-stu-id="82e7e-117">Maximum number of themes: desired number of themes</span></span>
- <span data-ttu-id="82e7e-118">テーマに数字を含める: 有効にすると、テーマを生成するときに数字が含まれます。</span><span class="sxs-lookup"><span data-stu-id="82e7e-118">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="82e7e-119">光学式文字認識 (OCR)</span><span class="sxs-lookup"><span data-stu-id="82e7e-119">Optical character recognition (OCR)</span></span>

<span data-ttu-id="82e7e-120">この設定をオンにすると、取り込まれたが検索可能になるように、校閲セットに入れられている画像に対して OCR が実行されます。</span><span class="sxs-lookup"><span data-stu-id="82e7e-120">When this setting is turned on, OCR will be run on images that are ingested into review sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="82e7e-121">テキストを無視する</span><span class="sxs-lookup"><span data-stu-id="82e7e-121">Ignore text</span></span>

<span data-ttu-id="82e7e-122">特定のテキストに、電子メールの内容に関係なく特定の電子メールに追加される長い免責事項など、特定のテキストが分析の品質を低下させる場合があります。</span><span class="sxs-lookup"><span data-stu-id="82e7e-122">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email.</span></span> <span data-ttu-id="82e7e-123">そのような場合は、テキストを指定することによって、分析からこのテキストを除外することができます (RegEx はサポートされています)。また、テキストを除外するモジュールを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="82e7e-123">If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>