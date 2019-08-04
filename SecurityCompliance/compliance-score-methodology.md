---
title: コンプライアンススコアの方法論
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンスマネージャーは、Microsoft Service Trust Portal の無料のワークフローベースのリスク評価ツールです。 コンプライアンスマネージャーを使用すると、Microsoft クラウドサービスに関連する規制コンプライアンスアクティビティを追跡、割り当て、検証することができます。
ms.openlocfilehash: 55f90996997a60fd95347941bdcad7707c890166
ms.sourcegitcommit: f0d23e57b00f07cef5b1b2d366eaeeeacda37e3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2019
ms.locfileid: "35786642"
---
# <a name="compliance-score-methodology-preview"></a><span data-ttu-id="cf2df-104">コンプライアンススコアの方法論 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="cf2df-104">Compliance Score Methodology (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="cf2df-p102">組織が特定の標準や規制を遵守しているかの絶対的測定値は、コンプライアンス スコアでは表せません。ユーザーが設定した、個人のデータやプライバシーに関するリスクを軽減できるコントロールをどの程度採用したかがコンプライアンス スコアによって表されます。標準や規制に準じていることを保証するサービスは提供されておらず、コンプライアンス スコアも何かを保証するものではありませんので、ご注意ください。</span><span class="sxs-lookup"><span data-stu-id="cf2df-p102">The Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation. It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy. No service can guarantee that you are compliant with a standard or regulation, and the Compliance Score should not be interpreted as a guarantee in any way.</span></span>

<span data-ttu-id="cf2df-108">コンプライアンスマネージャーダッシュボードには、各評価タイルの評価の合計コンプライアンススコアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf2df-108">The Compliance Manager dashboard displays a total compliance score for Assessments in each Assessment tile.</span></span> <span data-ttu-id="cf2df-109">これは評価の全体的なコンプライアンススコアで、評価で実装およびテストされた各統制についてのポイントの累積となります。</span><span class="sxs-lookup"><span data-stu-id="cf2df-109">This is the overall Compliance Score for the Assessment and is the accumulation of points received for each implemented and tested control in the Assessment.</span></span> <span data-ttu-id="cf2df-110">新しい評価の場合、コンプライアンススコアには、独立したサードパーティによってテストされた、組み込みの Microsoft 管理コントロールの初期値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="cf2df-110">For a new Assessment, the Compliance Score has an initial value for the included Microsoft-managed controls tested by independent third parties.</span></span> <span data-ttu-id="cf2df-111">コンプライアンススコアは、コンプライアンスの全体的な姿勢を改善するために、どの評価や統制を重視するかを優先して判断します。</span><span class="sxs-lookup"><span data-stu-id="cf2df-111">Compliance Score can help prioritize which Assessments and controls to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="cf2df-112">コントロールの表示されるコンプライアンススコアの値は、合格/不合格の合計コンプライアンススコアに*完全*に適用されます。</span><span class="sxs-lookup"><span data-stu-id="cf2df-112">The displayed Compliance Score values for the control are applied *in their entirety* to the total Compliance Score on a pass/fail basis.</span></span> <span data-ttu-id="cf2df-113">コントロールが実装されていて、以降の評価テストに合格しているかどうか。</span><span class="sxs-lookup"><span data-stu-id="cf2df-113">Either the control is implemented and passes the subsequent assessment test or it does not.</span></span> <span data-ttu-id="cf2df-114">部分的な実装には、一部のクレジットがありません。</span><span class="sxs-lookup"><span data-stu-id="cf2df-114">There is no partial credit for a partial implementation.</span></span> <span data-ttu-id="cf2df-115">割り当てられたポイントは、コントロールが次の場合にコンプライアンススコアに追加されます。</span><span class="sxs-lookup"><span data-stu-id="cf2df-115">Assigned points are added to the Compliance Score when the Control has:</span></span>

- <span data-ttu-id="cf2df-116">**実装の状態**は、**実装**済みまたは**代替の実装**と同じで、</span><span class="sxs-lookup"><span data-stu-id="cf2df-116">**Implementation Status** equals **Implemented** or **Alternative Implementation** and,</span></span>
- <span data-ttu-id="cf2df-117">**テスト結果**が**渡さ**れた値に等しい。</span><span class="sxs-lookup"><span data-stu-id="cf2df-117">**Test Result** equals **Passed**.</span></span>

## <a name="compliance-score"></a><span data-ttu-id="cf2df-118">コンプライアンススコア</span><span class="sxs-lookup"><span data-stu-id="cf2df-118">Compliance score</span></span>
  
<span data-ttu-id="cf2df-119">コンプライアンスマネージャーでは、ベースラインスコアはコントロールレベルからアクションアイテムレベルに移動します。</span><span class="sxs-lookup"><span data-stu-id="cf2df-119">In Compliance Manager, baseline scores move from the Control level to the Action Item level.</span></span> <span data-ttu-id="cf2df-120">スコアは、目的 (検出、予防的、または是正) と、アクションアイテムの実施 (随意または必須) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="cf2df-120">Scores are based on the purpose (Detective, Preventative, or Corrective) and enforcement (Discretionary or Mandatory) of the Action Item.</span></span>

<span data-ttu-id="cf2df-121">アクションアイテムはコントロールにマップされます。また、複数のアクションアイテムにコントロールがマップされている場合、アクションアイテムスコアの合計はコントロールスコアになります。</span><span class="sxs-lookup"><span data-stu-id="cf2df-121">Action Items are mapped to Controls, and when a Control is mapped to multiple Action Items, the sum of the Action Item Scores is the Control Score.</span></span> <span data-ttu-id="cf2df-122">特定の評価のすべてのコントロールのコントロールスコアの合計は評価スコアです。</span><span class="sxs-lookup"><span data-stu-id="cf2df-122">The sum of the Control Score for all Controls in a given Assessment is the Assessment Score.</span></span> <span data-ttu-id="cf2df-123">グループ内のすべての評価の平均スコアは、そのグループのコンプライアンススコアです。</span><span class="sxs-lookup"><span data-stu-id="cf2df-123">The average score of all Assessments in a Group is the Compliance Score for that group.</span></span>
  
### <a name="mandatory-or-discretionary-controls"></a><span data-ttu-id="cf2df-124">必須または任意のコントロール</span><span class="sxs-lookup"><span data-stu-id="cf2df-124">Mandatory or discretionary Controls</span></span>
  
 <span data-ttu-id="cf2df-125">**必須コントロール**は、意図的でも誤っても使用できないアクションです。</span><span class="sxs-lookup"><span data-stu-id="cf2df-125">**Mandatory Controls** are actions that cannot be bypassed either intentionally or accidentally.</span></span> <span data-ttu-id="cf2df-126">一般的な必須コントロールの例として、パスワードの長さ、複雑さ、および有効期限の要件を設定する一元的に管理されたパスワードポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="cf2df-126">An example of a common mandatory control is a centrally managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="cf2df-127">ユーザーがシステムにアクセスするには、これらの要件に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf2df-127">Users must comply with these requirements to access the system.</span></span>
  
 <span data-ttu-id="cf2df-128">**随意制御**は、ポリシーを理解し、それに応じて行動することをユーザーに依存します。</span><span class="sxs-lookup"><span data-stu-id="cf2df-128">**Discretionary Controls** rely upon users to understand policy and act accordingly.</span></span> <span data-ttu-id="cf2df-129">たとえば、ユーザーが自分のコンピューターを離れるときにロックすることを要求するポリシーは、ユーザーに依存しているため、随意制御です。</span><span class="sxs-lookup"><span data-stu-id="cf2df-129">For example, a policy requiring users to lock their computer when they leave it is a discretionary control because it relies on the user.</span></span>
  
### <a name="preventative-detective-or-corrective-controls"></a><span data-ttu-id="cf2df-130">予防的、検出、または是正の各コントロール</span><span class="sxs-lookup"><span data-stu-id="cf2df-130">Preventative, detective, or corrective Controls</span></span>
  
 <span data-ttu-id="cf2df-131">**予防的制御**とは、特定のリスクを回避するアクションのことです。</span><span class="sxs-lookup"><span data-stu-id="cf2df-131">**Preventative Controls** are actions that prevent specific risks.</span></span> <span data-ttu-id="cf2df-132">たとえば、暗号化を使用して情報を保護することは、攻撃、侵害に対する予防的な制御です。</span><span class="sxs-lookup"><span data-stu-id="cf2df-132">For example, protecting information at rest using encryption is a preventative control against attacks, breaches.</span></span> <span data-ttu-id="cf2df-133">仕事の分離は、利益の競合を管理し、詐欺対策を防御する予防的な制御です。</span><span class="sxs-lookup"><span data-stu-id="cf2df-133">Separation of duties is a preventative control to manage conflict of interest and to guard against fraud.</span></span>
  
 <span data-ttu-id="cf2df-134">**検出コントロール**は、システムをアクティブに監視して、異常な状態や、リスクを示す、または違反が発生したかどうかを検出するために使用できる、変則的な条件や動作を識別するアクションです。</span><span class="sxs-lookup"><span data-stu-id="cf2df-134">**Detective Controls** are actions that actively monitor systems to identify irregular conditions or behaviors that represent risk or that can be used to detect intrusions or determine if a breach has occurred.</span></span> <span data-ttu-id="cf2df-135">システムアクセスの監査および特権管理アクションの監査は、検出の監視コントロールの種類です。</span><span class="sxs-lookup"><span data-stu-id="cf2df-135">System access auditing and privileged administrative actions auditing are types of detective monitoring controls.</span></span> <span data-ttu-id="cf2df-136">コンプライアンス監査は、プロセスの問題を検出するために使用される検出コントロールの1種類です。</span><span class="sxs-lookup"><span data-stu-id="cf2df-136">Regulatory compliance audits are a type of detective control used to find process issues.</span></span>
  
<span data-ttu-id="cf2df-137">**是正制御**とは、セキュリティインシデントの悪影響を最小限に抑え、是正措置を行って直ちに影響を軽減し、可能であれば損害を元に戻すことができるようにする統制のことです。</span><span class="sxs-lookup"><span data-stu-id="cf2df-137">**Corrective Controls** are Controls that try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage, if possible.</span></span> <span data-ttu-id="cf2df-138">プライバシーインシデント対応は、違反が発生した後にシステムを運用状態にして復元するための是正的な制御です。</span><span class="sxs-lookup"><span data-stu-id="cf2df-138">Privacy incident response is a corrective control to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="cf2df-139">各コントロールは、次のリスクに基づいてコンプライアンスマネージャーで値を割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="cf2df-139">Each Control has an assigned value in Compliance Manager based on the risk that it represents:</span></span>

|<span data-ttu-id="cf2df-140">**Type**</span><span class="sxs-lookup"><span data-stu-id="cf2df-140">**Type**</span></span>|<span data-ttu-id="cf2df-141">**割り当てられたスコア**</span><span class="sxs-lookup"><span data-stu-id="cf2df-141">**Assigned Score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="cf2df-142">予防必須</span><span class="sxs-lookup"><span data-stu-id="cf2df-142">Preventative Mandatory</span></span> | <span data-ttu-id="cf2df-143">27</span><span class="sxs-lookup"><span data-stu-id="cf2df-143">27</span></span> |
| <span data-ttu-id="cf2df-144">予防的裁量</span><span class="sxs-lookup"><span data-stu-id="cf2df-144">Preventative Discretionary</span></span> | <span data-ttu-id="cf2df-145">9 </span><span class="sxs-lookup"><span data-stu-id="cf2df-145">9</span></span> |
| <span data-ttu-id="cf2df-146">検出必須</span><span class="sxs-lookup"><span data-stu-id="cf2df-146">Detective Mandatory</span></span> | <span data-ttu-id="cf2df-147">1/3</span><span class="sxs-lookup"><span data-stu-id="cf2df-147">3</span></span> |
| <span data-ttu-id="cf2df-148">検出随意</span><span class="sxs-lookup"><span data-stu-id="cf2df-148">Detective Discretionary</span></span> | <span data-ttu-id="cf2df-149">1-d</span><span class="sxs-lookup"><span data-stu-id="cf2df-149">1</span></span> |
| <span data-ttu-id="cf2df-150">修正必須</span><span class="sxs-lookup"><span data-stu-id="cf2df-150">Corrective Mandatory</span></span> | <span data-ttu-id="cf2df-151">1/3</span><span class="sxs-lookup"><span data-stu-id="cf2df-151">3</span></span> |
| <span data-ttu-id="cf2df-152">随意随意</span><span class="sxs-lookup"><span data-stu-id="cf2df-152">Corrective Discretionary</span></span> | <span data-ttu-id="cf2df-153">1-d</span><span class="sxs-lookup"><span data-stu-id="cf2df-153">1</span></span> |
  
## <a name="action-item-workflow"></a><span data-ttu-id="cf2df-154">アクションアイテムワークフロー</span><span class="sxs-lookup"><span data-stu-id="cf2df-154">Action Item workflow</span></span>

<span data-ttu-id="cf2df-155">一般的なアクションアイテムの基本的なワークフローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cf2df-155">Here's the basic workflow for a typical Action Item:</span></span>
  
1. <span data-ttu-id="cf2df-156">組織のコンプライアンス、リスク、プライバシー、またはデータ保護責任者は、組織内のユーザーにタスクを割り当てて、コントロールを実装します。</span><span class="sxs-lookup"><span data-stu-id="cf2df-156">The Compliance, Risk, Privacy, and/or Data Protection Officer of an organization assigns a task to someone in the organization to implement a control.</span></span> <span data-ttu-id="cf2df-157">その人物は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cf2df-157">That person could be:</span></span>

    - <span data-ttu-id="cf2df-158">ビジネスポリシーの所有者。</span><span class="sxs-lookup"><span data-stu-id="cf2df-158">A business policy owner.</span></span>
    - <span data-ttu-id="cf2df-159">IT の実装者。</span><span class="sxs-lookup"><span data-stu-id="cf2df-159">An IT implementer.</span></span>
    - <span data-ttu-id="cf2df-160">組織内でタスクを実行する責任を持つ別の個人。</span><span class="sxs-lookup"><span data-stu-id="cf2df-160">Another individual in the organization with responsibility to perform the task.</span></span>

2. <span data-ttu-id="cf2df-161">このユーザーは、コントロールを実装するために必要なタスクを実行し、実装の証拠をコンプライアンスマネージャーにアップロードして、アクションアイテムに関連付けられたコントロールを実装済みとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="cf2df-161">That individual performs the tasks necessary to implement the control, uploads evidence of implementation into Compliance Manager, and marks the Control tied to the Action Item as implemented.</span></span> <span data-ttu-id="cf2df-162">これらのタスクが完了すると、検証の査定者に対してアクションアイテムが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="cf2df-162">Once these tasks are completed, they assign the Action Item to an Assessor for validation.</span></span>

    <span data-ttu-id="cf2df-163">一環は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cf2df-163">Assessors can be:</span></span>

    - <span data-ttu-id="cf2df-164">組織内のコントロールの検証を実行する内部一環。</span><span class="sxs-lookup"><span data-stu-id="cf2df-164">Internal assessors that perform validation of controls within an organization.</span></span>
    - <span data-ttu-id="cf2df-165">Microsoft のクラウドサービスを監査するサードパーティの独立した組織など、コンプライアンスを調査、検証、および認定する外部一環。</span><span class="sxs-lookup"><span data-stu-id="cf2df-165">External assessors that examine, verify, and certify compliance, such as the third-party independent organizations that audit Microsoft's cloud services.</span></span>

3. <span data-ttu-id="cf2df-166">査定官は、コントロールを検証し、証拠を調べて、制御を評価および評価の結果としてマークします。</span><span class="sxs-lookup"><span data-stu-id="cf2df-166">The Assessor validates the control and examines the evidence and marks the control as assessed and the results of the assessment.</span></span>

<span data-ttu-id="cf2df-167">評価に関連付けられたすべてのコントロールが評価されると、評価は完了です。</span><span class="sxs-lookup"><span data-stu-id="cf2df-167">Once all the Controls associated with an Assessment are assessed, the Assessment is complete.</span></span>