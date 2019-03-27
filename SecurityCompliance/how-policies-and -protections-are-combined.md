---
title: メールが赤のフラグが設定されている場合のポリシーと保護の組み合わせ
description: 電子メールがマルウェア、スパム、信頼度の高いスパム、フィッシング、EOP によって、または ATP によってマークされたときに適用されるポリシーと実行するアクション。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、atp、Windows Defender ATP、Office 365 atp、Azure atp
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 03/26/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 7aa0f89eed379273cb069cd65c083749a9552e91
ms.sourcegitcommit: a79eb9907759d4cd849c3f948695a9ff890b19bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2019
ms.locfileid: "30926471"
---
# <a name="what-policy-applies-when-multiple-protection-methods-and-detection-scans-run-on-your-email"></a><span data-ttu-id="057ca-104">複数の保護方法および検出スキャンがメールで実行される場合に適用されるポリシー</span><span class="sxs-lookup"><span data-stu-id="057ca-104">What policy applies when multiple protection methods and detection scans run on your email</span></span>

<span data-ttu-id="057ca-105">場合によっては、受信メールに複数の形式の保護 (たとえば、EOP*と*ATP の両方)、および複数の検出スキャン (スパム*や*フィッシングなど) によってフラグが設定される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="057ca-105">Potentially, your incoming mail may be flagged by multiple forms of protection (for example both EOP *and* ATP), and multiple detection scans (such as spam *and* phishing).</span></span> <span data-ttu-id="057ca-106">これは、atp のお客様に対して atp のフィッシング対策ポリシーがあり、EOP のお客様に対して EOP のフィッシング対策ポリシーが存在するために可能です。</span><span class="sxs-lookup"><span data-stu-id="057ca-106">This is possible because there are ATP Anti-phishing policies for ATP customers, and EOP Anti-phishing policies for EOP customers.</span></span> <span data-ttu-id="057ca-107">これは、メッセージがマルウェア、フィッシング、およびユーザー偽装に対して複数の検出スキャンを移動することも意味します。</span><span class="sxs-lookup"><span data-stu-id="057ca-107">This also means the message may navigate multiple detection scans for malware, phishing, and user-impersonation, for example.</span></span> <span data-ttu-id="057ca-108">このアクティビティがすべて与えられた場合、どのポリシーが適用されるかについて混乱が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="057ca-108">Given all this activity, there may be some confusion as to which policy applies.</span></span>

<span data-ttu-id="057ca-109">一般に、メッセージに適用されるポリシーは、 **CAT (Category)** プロパティの**スパム対策**ヘッダーで識別されます。</span><span class="sxs-lookup"><span data-stu-id="057ca-109">In general, the policy applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="057ca-110">複数のフィッシング対策ポリシーがある場合は、優先度の高いものが適用されます。</span><span class="sxs-lookup"><span data-stu-id="057ca-110">If you have multiple Anti-phishing policies, the one at the highest priority will apply.</span></span>

<span data-ttu-id="057ca-111">以下のポリシーは、_すべての組織_に適用されます。</span><span class="sxs-lookup"><span data-stu-id="057ca-111">The Policies below apply to _all organizations_.</span></span>

|<span data-ttu-id="057ca-112">優先度</span><span class="sxs-lookup"><span data-stu-id="057ca-112">Priority</span></span> |<span data-ttu-id="057ca-113">ポリシー</span><span class="sxs-lookup"><span data-stu-id="057ca-113">Policy</span></span>  |<span data-ttu-id="057ca-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="057ca-114">Category</span></span>  |<span data-ttu-id="057ca-115">管理対象の場所</span><span class="sxs-lookup"><span data-stu-id="057ca-115">Where Managed</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="057ca-116">1-d</span><span class="sxs-lookup"><span data-stu-id="057ca-116">1</span></span>     | <span data-ttu-id="057ca-117">ウェア</span><span class="sxs-lookup"><span data-stu-id="057ca-117">Malware</span></span>      | <span data-ttu-id="057ca-118">悪意のある w</span><span class="sxs-lookup"><span data-stu-id="057ca-118">MALW</span></span>      | <span data-ttu-id="057ca-119">マルウェアポリシー</span><span class="sxs-lookup"><span data-stu-id="057ca-119">Malware policy</span></span>   |
|<span data-ttu-id="057ca-120">pbm-2</span><span class="sxs-lookup"><span data-stu-id="057ca-120">2</span></span>     | <span data-ttu-id="057ca-121">フィッシング</span><span class="sxs-lookup"><span data-stu-id="057ca-121">Phishing</span></span>     | <span data-ttu-id="057ca-122">phsh</span><span class="sxs-lookup"><span data-stu-id="057ca-122">PHSH</span></span>     | <span data-ttu-id="057ca-123">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="057ca-123">Configure your spam filter policies</span></span>     |
|<span data-ttu-id="057ca-124">1/3</span><span class="sxs-lookup"><span data-stu-id="057ca-124">3</span></span>     | <span data-ttu-id="057ca-125">信頼度の高いスパム</span><span class="sxs-lookup"><span data-stu-id="057ca-125">High confidence spam</span></span>      | <span data-ttu-id="057ca-126">hspm</span><span class="sxs-lookup"><span data-stu-id="057ca-126">HSPM</span></span>        | <span data-ttu-id="057ca-127">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="057ca-127">Configure your spam filter policies</span></span>        |
|<span data-ttu-id="057ca-128">2/4</span><span class="sxs-lookup"><span data-stu-id="057ca-128">4</span></span>     | <span data-ttu-id="057ca-129">なりすまし</span><span class="sxs-lookup"><span data-stu-id="057ca-129">Spoofing</span></span>        | <span data-ttu-id="057ca-130">なりすます</span><span class="sxs-lookup"><span data-stu-id="057ca-130">SPOOF</span></span>        | <span data-ttu-id="057ca-131">フィッシング対策ポリシー、スプーフィングインテリジェンス</span><span class="sxs-lookup"><span data-stu-id="057ca-131">Anti-phishing policy, spoof intelligence</span></span>        |
|<span data-ttu-id="057ca-132">5</span><span class="sxs-lookup"><span data-stu-id="057ca-132">5</span></span>     | <span data-ttu-id="057ca-133">スパム</span><span class="sxs-lookup"><span data-stu-id="057ca-133">Spam</span></span>         | <span data-ttu-id="057ca-134">SPM</span><span class="sxs-lookup"><span data-stu-id="057ca-134">SPM</span></span>         | <span data-ttu-id="057ca-135">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="057ca-135">Configure your spam filter policies</span></span>         |
|<span data-ttu-id="057ca-136">シックス</span><span class="sxs-lookup"><span data-stu-id="057ca-136">6</span></span>     | <span data-ttu-id="057ca-137">大半</span><span class="sxs-lookup"><span data-stu-id="057ca-137">Bulk</span></span>         | <span data-ttu-id="057ca-138">大半</span><span class="sxs-lookup"><span data-stu-id="057ca-138">BULK</span></span>        | <span data-ttu-id="057ca-139">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="057ca-139">Configure your spam filter policies</span></span>         |

<span data-ttu-id="057ca-140">さらに、これらのポリシーは_ATP を使用している組織_にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="057ca-140">In addition, these policies apply to _organizations with ATP_.</span></span>

|<span data-ttu-id="057ca-141">優先度</span><span class="sxs-lookup"><span data-stu-id="057ca-141">Priority</span></span> |<span data-ttu-id="057ca-142">ポリシー</span><span class="sxs-lookup"><span data-stu-id="057ca-142">Policy</span></span>  |<span data-ttu-id="057ca-143">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="057ca-143">Category</span></span>  |<span data-ttu-id="057ca-144">管理対象の場所</span><span class="sxs-lookup"><span data-stu-id="057ca-144">Where Managed</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="057ca-145">7</span><span class="sxs-lookup"><span data-stu-id="057ca-145">7</span></span>     | <span data-ttu-id="057ca-146">ドメイン偽装</span><span class="sxs-lookup"><span data-stu-id="057ca-146">Domain Impersonation</span></span>         | <span data-ttu-id="057ca-147">dimp</span><span class="sxs-lookup"><span data-stu-id="057ca-147">DIMP</span></span>         | <span data-ttu-id="057ca-148">Office 365 の ATP のフィッシング対策およびフィッシング対策ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="057ca-148">Set up Office 365 ATP anti-phishing and anti-phishing policies</span></span>        |
|<span data-ttu-id="057ca-149">~</span><span class="sxs-lookup"><span data-stu-id="057ca-149">8</span></span>     | <span data-ttu-id="057ca-150">ユーザー偽装</span><span class="sxs-lookup"><span data-stu-id="057ca-150">User Impersonation</span></span>        | <span data-ttu-id="057ca-151">uimp</span><span class="sxs-lookup"><span data-stu-id="057ca-151">UIMP</span></span>         | <span data-ttu-id="057ca-152">Office 365 の ATP のフィッシング対策およびフィッシング対策ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="057ca-152">Set up Office 365 ATP anti-phishing and anti-phishing policies</span></span>         |

<span data-ttu-id="057ca-153">例として、次の2つのポリシーがあるとします。</span><span class="sxs-lookup"><span data-stu-id="057ca-153">As an example, if you have two policies:</span></span>

|<span data-ttu-id="057ca-154">ポリシー</span><span class="sxs-lookup"><span data-stu-id="057ca-154">Policy</span></span>  |<span data-ttu-id="057ca-155">優先度</span><span class="sxs-lookup"><span data-stu-id="057ca-155">Priority</span></span>  |<span data-ttu-id="057ca-156">ユーザー/ドメインの偽装</span><span class="sxs-lookup"><span data-stu-id="057ca-156">User/Domain Impersonation</span></span>  |<span data-ttu-id="057ca-157">スプーフィング対策</span><span class="sxs-lookup"><span data-stu-id="057ca-157">Anti-spoofing</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="057ca-158">A</span><span class="sxs-lookup"><span data-stu-id="057ca-158">A</span></span>     | <span data-ttu-id="057ca-159">1-d</span><span class="sxs-lookup"><span data-stu-id="057ca-159">1</span></span>        | <span data-ttu-id="057ca-160">オン</span><span class="sxs-lookup"><span data-stu-id="057ca-160">On</span></span>        |<span data-ttu-id="057ca-161">Off</span><span class="sxs-lookup"><span data-stu-id="057ca-161">Off</span></span>         |
|<span data-ttu-id="057ca-162">B</span><span class="sxs-lookup"><span data-stu-id="057ca-162">B</span></span>     | <span data-ttu-id="057ca-163">pbm-2</span><span class="sxs-lookup"><span data-stu-id="057ca-163">2</span></span>        | <span data-ttu-id="057ca-164">Off</span><span class="sxs-lookup"><span data-stu-id="057ca-164">Off</span></span>        | <span data-ttu-id="057ca-165">On</span><span class="sxs-lookup"><span data-stu-id="057ca-165">On</span></span>        |

<span data-ttu-id="057ca-166">メッセージが_ユーザーの偽装_と_スプーフィング_の両方として識別される (上記の表の「スプーフィング対策」を参照)、ポリシー a をスコープとする同じセットのユーザーがポリシー B を対象としている場合、メッセージはフラグが付けられ、_スプーフィング_として扱われますが、アクションは、スプーフィング対策がオフになっているために適用されます。また、なりすましは、**ユーザー偽装 (8) よりも高い優先度 (4) で実行**されます。</span><span class="sxs-lookup"><span data-stu-id="057ca-166">If a message comes in identified as both _user impersonation_ and _spoofing_ (see anti-spoofing in the table above), and the same set of users scoped to policy A is scoped to policy B, then the message is flagged and treated as a _spoof_, but no action is applied since Anti-spoofing is turned off, and because **spoof runs at a higher priority (4) than User Impersonation (8)**.</span></span>

<span data-ttu-id="057ca-167">他の種類のフィッシングポリシーを適用するには、さまざまなポリシーが適用されるユーザーの設定を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="057ca-167">To make other types of phishing policy apply, you will need to adjust the settings of who the various policies apply to.</span></span>



