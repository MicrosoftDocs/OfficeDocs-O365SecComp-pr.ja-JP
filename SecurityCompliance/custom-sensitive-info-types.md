---
title: DLP 用のカスタムの機密情報の種類
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: DLP 用のカスタムの機密情報の種類の概要です。
ms.openlocfilehash: a31817b2de1f48a5f49c02af150ce40a9d58c24a
ms.sourcegitcommit: 666bc17da0ab0969cf46f99f8726f463327cf599
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "33829130"
---
# <a name="custom-sensitive-information-types"></a><span data-ttu-id="531b3-103">カスタムの機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="531b3-103">Custom Sensitive Information Types:</span></span>

## <a name="overview"></a><span data-ttu-id="531b3-104">概要</span><span class="sxs-lookup"><span data-stu-id="531b3-104">Overview</span></span>

<span data-ttu-id="531b3-105">Office 365 には機密情報の種類が多数組み込まれており、[データ損失防止](data-loss-prevention-policies.md) (DLP)、あるいは [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) 用に組織内で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="531b3-105">Office 365 includes many built-in sensitive information types that are ready for you to use in your organization, such as for [data loss prevention](data-loss-prevention-policies.md) (DLP), or with [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="531b3-106">組み込まれている機密情報の種類は、クレジットカード番号、銀行口座番号、パスポート番号などを特定して保護するのに役立ちます。これらの情報の特定と保護は、正規表現 (regex) または関数によって定義されたパターンに基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="531b3-106">Built-in sensitive information types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more, based on patterns that are defined by a regular expression (regex) or a function.</span></span> <span data-ttu-id="531b3-107">詳細については、「[機密情報の種類で検索される情報](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="531b3-107">To learn more, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="531b3-108">ただし、組織固有の形式で、異なる機密情報の種類 (従業員 ID やプロジェクト番号など) を特定して保護する必要がある場合は、</span><span class="sxs-lookup"><span data-stu-id="531b3-108">But what if you need to identify and protect a different type of sensitive information, such as for employee IDs or project numbers, using a format that's specific to your organization?</span></span> <span data-ttu-id="531b3-109">カスタムの機密情報の種類を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="531b3-109">To do this, you can create a custom sensitive information type.</span></span>

<span data-ttu-id="531b3-110">カスタムの機密情報の種類の基本的な部分は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="531b3-110">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="531b3-111">**プライマリ パターン**: 従業員 ID 番号、プロジェクト番号など。これは通常、正規表現 (RegEx) によって識別されますが、キーワード リストにもできます。</span><span class="sxs-lookup"><span data-stu-id="531b3-111">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="531b3-p103">**追加の証拠**: 9 桁の従業員 ID 番号を探していると仮定します。9 桁の数字がすべて従業員 ID 番号ではないので、「従業員」、「社員証」、「ID」などのキーワードや追加の正規表現を基にして、別のテキスト パターンを検索できます。この補強証拠 (_補強_または_裏付け_証拠とも呼ばれる) は、コンテンツに含まれる 9 桁の数字が実際に従業員 ID 番号である可能性を高めます。</span><span class="sxs-lookup"><span data-stu-id="531b3-p103">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="531b3-p104">**文字の近接**: プライマリ パターンと補強証拠が互いに近いほど、検出されたコンテンツが探しているものになる可能性が高くなります。次の図に示すように、プライマリ パターンと補強証拠との文字の距離 (_近接ウィンドウ_とも呼ばれる) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="531b3-p104">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![補強証拠と近接ウィンドウの図](media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="531b3-p105">**信頼レベル**: 持っている補強証拠が多ければ多いほど、探している機密情報と一致する可能性が高くなります。より多くの証拠を使用して検出された一致には、より高いレベルの信頼を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="531b3-p105">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="531b3-p106">パターンを満たす場合は、数と信頼度が返され、DLP ポリシーの条件に使用できます。機密情報の種類を検出する条件を DLP ポリシーに追加する場合、次の図に示すように、数と信頼度を編集できます。</span><span class="sxs-lookup"><span data-stu-id="531b3-p106">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![インスタンス数と一致精度オプション](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="531b3-123">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="531b3-123">Creating custom sensitive information types</span></span>

<span data-ttu-id="531b3-124">次のオプションを使用して、セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="531b3-124">To create custom sensitive information types in the Security & Compliance Center, you have the following options:</span></span>

- <span data-ttu-id="531b3-125">**EDM を使用する** (新規) データ一致 (EDM) に基づく分類によって、カスタム機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="531b3-125">**Use EDM** (NEW!) You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="531b3-126">この方法では、定期的に更新できる安全なデータベースを使用して、動的な機密情報の種類を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="531b3-126">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="531b3-127">詳細については、「[データ一致に基づく分類 (プレビュー) で、カスタムの機密情報の種類を作成する](create-custom-sensitive-info-type-edm.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="531b3-127">See [Create a custom sensitive information type with Exact Data Match based classification (Preview)](create-custom-sensitive-info-type-edm.md).</span></span>

- <span data-ttu-id="531b3-128">**PowerShell を使用する** PowerShell を使用して、カスタムの機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="531b3-128">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="531b3-129">この方法は、UI を使用する場合よりも複雑ですが、より多くの構成オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="531b3-129">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="531b3-130">詳細については、「[セキュリティ/コンプライアンス センターの PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="531b3-130">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>

- <span data-ttu-id="531b3-131">**UI を使用する** セキュリティ/コンプライアンス センターの UI を使用して、カスタムの機密情報の種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="531b3-131">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="531b3-132">この方法では、正規表現、キーワード、キーワード辞書を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="531b3-132">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="531b3-133">詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="531b3-133">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>



