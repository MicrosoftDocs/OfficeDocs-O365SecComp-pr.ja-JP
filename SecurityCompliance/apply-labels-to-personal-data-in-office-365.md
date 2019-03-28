---
title: Office 365 の個人データにラベルを適用する
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Office のラベルを GDPR 保護計画の一部として使用する方法について説明します。
ms.openlocfilehash: 4167ace41c5d7534b7e90130c189e3c04e5c5100
ms.sourcegitcommit: ae7ebae8801a69a825a363443e2676379197de19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2019
ms.locfileid: "30800289"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a><span data-ttu-id="180ab-103">Office 365 の個人データにラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="180ab-103">Apply labels to personal data in Office 365</span></span>

 <span data-ttu-id="180ab-104">GDPR 保護計画の一環として、分類ラベルを使用している場合は、このトピックを使用します。</span><span class="sxs-lookup"><span data-stu-id="180ab-104">Use this topic if you are using classification labels as part of your GDPR protection plan.</span></span> 

<span data-ttu-id="180ab-105">Office 365 で個人用データを保護するためにラベルを使用している場合は、[保持ラベル](labels.md)を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="180ab-105">If you are using labels for protection of personal data in Office 365, Microsoft recommends you start with [retention labels](labels.md).</span></span> <span data-ttu-id="180ab-106">保持ラベルを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="180ab-106">With retention labels, you can:</span></span>
- <span data-ttu-id="180ab-107">アドバンスト データ ガバナンスを使用して、機密情報の種類やその他の基準に基づいてラベルを自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="180ab-107">Use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria.</span></span>
- <span data-ttu-id="180ab-108">データ損失防止機能を備えた保持ラベルを使用して、保護を適用できます。</span><span class="sxs-lookup"><span data-stu-id="180ab-108">Use retention labels with data loss prevention to apply protection.</span></span> 
- <span data-ttu-id="180ab-109">電子情報開示とコンテンツの検索でラベルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="180ab-109">Use labels with eDiscovery and Content Search.</span></span> 

<span data-ttu-id="180ab-110">現在、Cloud App Security は保持ラベルをサポートしていません。ただし、Office 365 の機密情報を Cloud App Security と併用して、別の SaaS アプリにある個人データを監視することはできます。</span><span class="sxs-lookup"><span data-stu-id="180ab-110">Cloud App Security doesn't currently support retention labels, but you can use Office 365 sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="180ab-111">[機密ラベル](sensitivity-labels.md)は現在、オンプレミスのファイル、その他のクラウド サービスのファイル、プロバイダーにラベルを適用する場合に推奨されています。</span><span class="sxs-lookup"><span data-stu-id="180ab-111">[Sensitivity labels](sensitivity-labels.md) are currently recommended for applying labels to files on premises and in other cloud services and providers.</span></span> <span data-ttu-id="180ab-112">また、営業秘密ファイルなどのデータ保護用の Azure Information Protection (AIP) 暗号化を必要とする Office 365 のファイルにも推奨されます。</span><span class="sxs-lookup"><span data-stu-id="180ab-112">These are also recommended for files in Office 365 that require Azure Information Protection (AIP) encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="180ab-113">現時点では、GDPR の対象となるデータを含む Office 365 のファイルに対して Azure Information Protection を使用して暗号化を適用することは、推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="180ab-113">At this time, using Azure Information Protection to apply encryption is not recommended for files in Office 365 with data that is subject to the GDPR.</span></span> <span data-ttu-id="180ab-114">現在、Office 365 サービスでは AIP で暗号化されたファイルへの読み取りはできません。</span><span class="sxs-lookup"><span data-stu-id="180ab-114">Office 365 services currently cannot read into AIP-encrypted files.</span></span> <span data-ttu-id="180ab-115">そのため、サービスでこれらのファイル内の機密データを検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="180ab-115">Therefore, the service can’t find sensitive data in these files.</span></span>

<span data-ttu-id="180ab-116">保持ラベルは Exchange Online のメールに適用できます。これらのラベルは Office 365 のデータ損失防止と連動することができます。</span><span class="sxs-lookup"><span data-stu-id="180ab-116">Sensitivity labels can be applied to mail in Exchange Online and these labels work with Office 365 data loss prevention.</span></span> 

![Office 365 のラベルと Azure Information Protection のラベル](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)


<span data-ttu-id="180ab-118">この図について:</span><span class="sxs-lookup"><span data-stu-id="180ab-118">In the illustration:</span></span>

-   <span data-ttu-id="180ab-119">SharePoint Online および OneDrive for Business では、個人データや厳しく規制された営業秘密ファイルに保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="180ab-119">Use retention labels for personal data and for highly regulated & trade secret files in SharePoint Online and OneDrive for Business.</span></span>
-   <span data-ttu-id="180ab-120">Office 365 の機密情報の種類を Office 365 内と Cloud App Security で使用して、別の SaaS アプリにある個人データを監視できます。</span><span class="sxs-lookup"><span data-stu-id="180ab-120">Office 365 sensitive information types can be used within Office 365 and with Cloud App Security to monintor personal data that resides in other SaaS apps.</span></span>
-   <span data-ttu-id="180ab-121">厳しく規制された営業秘密ファイル、Exchange Online 電子メール、他の SaaS サービスのファイル、オンプレミスのデータセンターのファイル、他のクラウド プロバイダーのファイルには、機密ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="180ab-121">Use sensitivity labels for highly regulated & trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="180ab-122">情報を保護するために Microsoft 365 全体で保持ラベルと機密情報の種類を使用する</span><span class="sxs-lookup"><span data-stu-id="180ab-122">Use retention labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="180ab-123">次の図は、ラベル ポリシー、データ損失防止ポリシー、Cloud App Security ポリシーで保持ラベルと機密情報の種類を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="180ab-123">The following illustration shows how retention labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Office のラベルと機密情報の種類](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="180ab-125">次の表では、図での例と同じものを見やすいように記載しています。</span><span class="sxs-lookup"><span data-stu-id="180ab-125">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="180ab-126"><strong>分類の要素</strong></span><span class="sxs-lookup"><span data-stu-id="180ab-126"><strong>Classification elements</strong></span></span></th>
<th align="left"><span data-ttu-id="180ab-127"><strong>ラベル ポリシー — 2 つの例</strong></span><span class="sxs-lookup"><span data-stu-id="180ab-127"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="180ab-128"><strong>データ損失防止ポリシー — 2 つの例</strong></span><span class="sxs-lookup"><span data-stu-id="180ab-128"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="180ab-129"><strong>すべての SaaS アプリの Cloud App Security ポリシー — 1 つの例</strong></span><span class="sxs-lookup"><span data-stu-id="180ab-129"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="180ab-130">保持ラベル。</span><span class="sxs-lookup"><span data-stu-id="180ab-130">Retention labels.</span></span> <span data-ttu-id="180ab-131">例: 個人、公開、顧客のデータ、人事データ、社外秘、非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="180ab-131">Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="180ab-p105">このラベルを自動で . . .</span><span class="sxs-lookup"><span data-stu-id="180ab-p105">Auto apply this label . . .</span></span></p>
<p><span data-ttu-id="180ab-135">顧客データ</span><span class="sxs-lookup"><span data-stu-id="180ab-135">Customer data</span></span></p>
<p><span data-ttu-id="180ab-p106">. . . これらの機密情報の種類に一致する文書に適用します . . .</span><span class="sxs-lookup"><span data-stu-id="180ab-p106">. . . to documents that match these sensitive information types . . .</span></span></p>
<p><span data-ttu-id="180ab-142">&lt;機密情報の種類の例の一覧&gt;</span><span class="sxs-lookup"><span data-stu-id="180ab-142">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="180ab-p107">この保護を . . .</span><span class="sxs-lookup"><span data-stu-id="180ab-p107">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="180ab-146">&lt;保護の定義&gt;</span><span class="sxs-lookup"><span data-stu-id="180ab-146">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="180ab-p108">. . . このラベルを持つドキュメントに適用します . . .</span><span class="sxs-lookup"><span data-stu-id="180ab-p108">. . . to documents with this label . . .</span></span></p>
<p><span data-ttu-id="180ab-153">顧客データ</span><span class="sxs-lookup"><span data-stu-id="180ab-153">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="180ab-p109">承認された SaaS アプリのこれらの属性を持つファイルが . . .</span><span class="sxs-lookup"><span data-stu-id="180ab-p109">Alert when files with these attributes . . .</span></span></p>
<p><span data-ttu-id="180ab-157">1 つまたは複数の属性を選択します: 定義済みの PII 属性、Office 365 の機密情報の種類、機密ラベル (AIP)、カスタム式</span><span class="sxs-lookup"><span data-stu-id="180ab-157">Choose one or more attribute: predefined PII attribute, Office 365 sensitive information type, sensitivity label (AIP), custom expression</span></span></p>
<p><span data-ttu-id="180ab-158">。</span><span class="sxs-lookup"><span data-stu-id="180ab-158"></span></span> <span data-ttu-id="180ab-159">。</span><span class="sxs-lookup"><span data-stu-id="180ab-159"></span></span> <span data-ttu-id="180ab-160">。</span><span class="sxs-lookup"><span data-stu-id="180ab-160"></span></span> <span data-ttu-id="180ab-161">組織外で共有された際に警告します</span><span class="sxs-lookup"><span data-stu-id="180ab-161">. . . in any sanctioned SaaS app are shared outside the organization</span></span></p><p><span data-ttu-id="180ab-162">注: 現在、保持ラベルは Cloud App Security ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="180ab-162">Note: Retention labels are currently not supported in Cloud App Security.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="180ab-p111">機密情報の種類。例: ベルギーの国民番号、クレジット カード番号、クロアチアの身分証明書番号、フィンランドの国民 ID</span><span class="sxs-lookup"><span data-stu-id="180ab-p111">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="180ab-p112">これらのラベルを発行して、ユーザーが . . .</span><span class="sxs-lookup"><span data-stu-id="180ab-p112">Publish these labels for users to manually apply . . .</span></span></p>
<p><span data-ttu-id="180ab-168">&lt;ラベルの選択&gt;</span><span class="sxs-lookup"><span data-stu-id="180ab-168">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="180ab-p113">. . . これらの場所に手動で適用するようにします . . .</span><span class="sxs-lookup"><span data-stu-id="180ab-p113">. . . to these locations . . .</span></span></p>
<p><span data-ttu-id="180ab-175">&lt;すべての場所、あるいは特定の場所を選択&gt;</span><span class="sxs-lookup"><span data-stu-id="180ab-175">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="180ab-p114">この保護を . . .</span><span class="sxs-lookup"><span data-stu-id="180ab-p114">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="180ab-179">&lt;保護の定義&gt;</span><span class="sxs-lookup"><span data-stu-id="180ab-179">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="180ab-p115">. . . これらの機密情報の種類に一致する文書に適用します&gt;</span><span class="sxs-lookup"><span data-stu-id="180ab-p115">. . . to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="180ab-184">自動適用ラベル ポリシーの優先順位付け</span><span class="sxs-lookup"><span data-stu-id="180ab-184">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="180ab-p116">GDPR の対象となる個人データについては、環境に合わせて設定した機密情報の種類を使用してラベルを自動適用することをお勧めします。自動適用ラベル ポリシーは、意図した動作が確実に行われるように、適切に設計され、テストされていることが重要です。</span><span class="sxs-lookup"><span data-stu-id="180ab-p116">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="180ab-p117">自動適用ポリシーが作成される順序と、ユーザーもこれらのラベルを適用するかどうかによって結果が異なってきます。したがって、ポリシーの作成とラベルの適用を慎重に計画する必要があります。重要なポイントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="180ab-p117">The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it is important to carefully plan the roll-out. Here’s what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="180ab-189">一度に 1 つのラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="180ab-189">One label at a time</span></span>

<span data-ttu-id="180ab-190">ドキュメントに割り当てることができるラベルの数は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="180ab-190">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="180ab-191">優先されるのは古いポリシー</span><span class="sxs-lookup"><span data-stu-id="180ab-191">Older auto-apply policies win</span></span>

<span data-ttu-id="180ab-p118">自動適用ラベルを割り当てるルールが複数あり、コンテンツが複数のルールの条件を満たす場合は、最も古いルールのラベルが割り当てられます。このため、ラベル ポリシーを構成する前に注意深く計画することが重要です。組織がラベル ポリシーの優先順位を変更する必要がある場合は、ラベル ポリシーを削除して再度作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="180ab-p118">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it is important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they will need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="180ab-195">自動適用ラベルよりもユーザーが手動で適用したラベルが優先される</span><span class="sxs-lookup"><span data-stu-id="180ab-195">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="180ab-p119">ユーザーが手動で適用したラベルは、自動適用ラベルよりも優先されます。自動適用ポリシーでは、ユーザーがすでに適用しているラベルを置き換えることはできませんが、ユーザーは、自動適用されたラベルを置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="180ab-p119">Manual user applied labels trump auto-applied labels. Auto-apply policies cannot replace a label that is already applied by a user. Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="180ab-199">自動的に割り当てられたラベルは更新可能</span><span class="sxs-lookup"><span data-stu-id="180ab-199">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="180ab-200">自動的に割り当てられたラベルは、新しいラベル ポリシーにより、または既存のポリシーを更新することによって最新の状態にすることができます。</span><span class="sxs-lookup"><span data-stu-id="180ab-200">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="180ab-201">ラベルを実装する際に重要な点:</span><span class="sxs-lookup"><span data-stu-id="180ab-201">Be sure your plan for implementing labels includes:</span></span>

-   <span data-ttu-id="180ab-202">自動適用ポリシーが作成される順序の優先順位付けを行います。</span><span class="sxs-lookup"><span data-stu-id="180ab-202">Prioritizing the order that auto-apply policies are created.</span></span>

-   <span data-ttu-id="180ab-p120">ユーザーが手動でラベルを適用する前に、ラベルが自動適用されるまで十分な時間の余裕があります。条件に一致するすべてのコンテンツにラベルが適用されるまでに最大 7 日間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="180ab-p120">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="180ab-205">自動適用ポリシー作成の優先順位の例</span><span class="sxs-lookup"><span data-stu-id="180ab-205">Example priority for creating the auto-apply policies</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="180ab-206"><strong>ラベル</strong></span><span class="sxs-lookup"><span data-stu-id="180ab-206"><strong>Labels</strong></span></span></th>
<th align="left"><span data-ttu-id="180ab-207"><strong>自動適用ポリシーの作成順序の優先順位</strong></span><span class="sxs-lookup"><span data-stu-id="180ab-207"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="180ab-208">人事 — 従業員データ</span><span class="sxs-lookup"><span data-stu-id="180ab-208">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="180ab-209">1</span><span class="sxs-lookup"><span data-stu-id="180ab-209">-1</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="180ab-210">顧客データ</span><span class="sxs-lookup"><span data-stu-id="180ab-210">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="180ab-211">2</span><span class="sxs-lookup"><span data-stu-id="180ab-211">-2</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="180ab-212">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="180ab-212">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="180ab-213">3</span><span class="sxs-lookup"><span data-stu-id="180ab-213">-3</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="180ab-214">人事 — 給与データ</span><span class="sxs-lookup"><span data-stu-id="180ab-214">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="180ab-215">4</span><span class="sxs-lookup"><span data-stu-id="180ab-215">4.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="180ab-216">社外秘</span><span class="sxs-lookup"><span data-stu-id="180ab-216">Confidential</span></span></td>
<td align="left"><span data-ttu-id="180ab-217">5</span><span class="sxs-lookup"><span data-stu-id="180ab-217">5.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="180ab-218">公開</span><span class="sxs-lookup"><span data-stu-id="180ab-218">Public</span></span></td>
<td align="left"><span data-ttu-id="180ab-219">6</span><span class="sxs-lookup"><span data-stu-id="180ab-219">6.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="180ab-220">個人</span><span class="sxs-lookup"><span data-stu-id="180ab-220">Personal</span></span></td>
<td align="left"><span data-ttu-id="180ab-221">自動適用ポリシーなし</span><span class="sxs-lookup"><span data-stu-id="180ab-221">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="180ab-222">ラベルおよび自動適用ラベル ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="180ab-222">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="180ab-223">セキュリティ/コンプライアンス センターで、ラベルおよびポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="180ab-223">Create labels and policies in the Security & Compliance Center.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="180ab-224"><strong>手順</strong></span><span class="sxs-lookup"><span data-stu-id="180ab-224"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="180ab-225"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="180ab-225"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="180ab-226">コンプライアンス チームのメンバーにアクセス許可を与えます。</span><span class="sxs-lookup"><span data-stu-id="180ab-226">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="180ab-p121">ラベルを作成するコンプライアンス チームのメンバーには、セキュリティ &amp; コンプライアンス センターを使用するためのアクセス許可が必要です。[セキュリティ/コンプライアンス センターのアクセス許可] に移動し、コンプライアンス管理者グループのメンバーを変更します。</span><span class="sxs-lookup"><span data-stu-id="180ab-p121">Members of your compliance team who will create labels need permissions to use the Security &amp; Compliance Center. Go to Permissions in Security and Compliance Center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="180ab-229">「<a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">ユーザーに Office 365 セキュリティ センター &amp; コンプライアンス センターへのアクセスを許可する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="180ab-229">See <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Give users access to the Office 365 Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="180ab-230">保持ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="180ab-230">Create retention labels.</span></span></p></td>
<td align="left"><span data-ttu-id="180ab-231">セキュリティ/コンプライアンス センターの [分類] に移動し、[保持ラベル] を選択して、使用している環境のラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="180ab-231">Go to Classifications in Security and Compliance Center, choose Retention labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="180ab-232">ラベルの自動適用ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="180ab-232">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="180ab-p122">セキュリティ/コンプライアンスセンターの [分類] に移動し、[ラベル ポリシー] を選択し、自動適用ラベルのポリシーを作成します。これらのポリシーは、優先順位に従って作成してください。</span><span class="sxs-lookup"><span data-stu-id="180ab-p122">Go to Classification in Security and Compliance Center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="180ab-235">次の図は、顧客データ ラベル用の自動適用ラベルを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="180ab-235">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![顧客データのラベルの作成と適用](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="180ab-237">この図について:</span><span class="sxs-lookup"><span data-stu-id="180ab-237">In the illustration:</span></span>

-   <span data-ttu-id="180ab-238">“顧客データ” ラベルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="180ab-238">The “Customer data” label is created.</span></span>

-   <span data-ttu-id="180ab-239">GDPR の必要な機密情報の種類 (ベルギーの国民番号、クレジット カード番号、クロアチアの身分証明書番号、フィンランドの国民 ID) が記載されています。</span><span class="sxs-lookup"><span data-stu-id="180ab-239">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

-   <span data-ttu-id="180ab-240">自動適用ポリシーを作成すると、ポリシーに追加する機密情報の種類のいずれかを含むファイルに、“顧客データ” ラベルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="180ab-240">Create an auto-apply policy assigns the label “Customer data” to any file that includes one of the sensitive information types that you add to the policy.</span></span>
