---
title: Office 365 の ATP のフィッシング詐欺対策機能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
description: ATP フィッシング詐欺対策が Office 365 の高度な脅威保護の一部として提供されます。ATP フィッシング詐欺対策には、商品とスピアー フィッシング攻撃に対する保護を提供する受信したメッセージに偽装検出アルゴリズムとコンピューターの学習モデルのセットが適用されます。すべてのメッセージは予告なしに広範囲にわたる機械学習モデルのさまざまなユーザーおよびドメインの偽装攻撃から保護するために使用する高度なアルゴリズムのセットと、フィッシング詐欺メッセージを検出するためにトレーニングをされることがあります。ATP フィッシング詐欺対策は、設定に基づいて、組織を保護する、Office 365 のグローバルまたはセキュリティ管理者によって設定され、ポリシーにします。
ms.openlocfilehash: cff25316f9a03bdfafd195eb408584ab8bca6343
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531989"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a><span data-ttu-id="5b597-106">Office 365 の ATP のフィッシング詐欺対策機能</span><span class="sxs-lookup"><span data-stu-id="5b597-106">ATP anti-phishing capabilities in Office 365</span></span>

<span data-ttu-id="5b597-p102">ATP フィッシング詐欺対策が[Office 365 の高度な脅威保護](https://technet.microsoft.com/en-us/library/exchange-online-advanced-threat-protection-service-description.aspx)の一部として提供されます。ATP フィッシング詐欺対策には、商品とスピアー フィッシング攻撃に対する保護を提供する受信したメッセージに偽装検出アルゴリズムとコンピューターの学習モデルのセットが適用されます。すべてのメッセージは予告なしに広範囲にわたる機械学習モデルのさまざまなユーザーおよびドメインの偽装攻撃から保護するために使用する高度なアルゴリズムのセットと、フィッシング詐欺メッセージを検出するためにトレーニングをされることがあります。ATP フィッシング詐欺対策は、設定に基づいて、組織を保護する、Office 365 のグローバルまたはセキュリティ管理者によって設定され、ポリシーにします。</span><span class="sxs-lookup"><span data-stu-id="5b597-p102">ATP anti-phishing is offered as part of [Office 365 Advanced Threat Protection](https://technet.microsoft.com/en-us/library/exchange-online-advanced-threat-protection-service-description.aspx). ATP anti-phishing applies a set of machine learning models together with impersonation detection algorithms to incoming messages to provide protection for commodity and spear phishing attacks. All messages are subject to an extensive set of machine learning models trained to detect phishing messages, together with a set of advanced algorithms used to protect against various user and domain impersonation attacks. ATP anti-phishing protects your organization according to polices that are set by your Office 365 global or security administrators.</span></span>
  
<span data-ttu-id="5b597-111">詳細については、 [Office 365 の ATP のフィッシング詐欺対策ポリシーの設定](set-up-atp-anti-phishing-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b597-111">To learn more, see [Set up ATP anti-phishing policies in Office 365](set-up-atp-anti-phishing-policies.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b597-p103">ATP フィッシング詐欺対策には、高度な脅威保護、Office 365 エンタープライズ E5 で使用可能にできるだけです。組織は、別の Office 365 エンタープライズ サブスクリプションで使用されている場合は、アドオンとして脅威の高度な保護を購入できます。(グローバル管理者の場合は、Office 365 管理センターで、選択**請求** \> **サブスクリプションを追加**します)。プランのオプションの詳細については、[ビジネス プランのすべての Office 365 の比較](https://go.microsoft.com/fwlink/?linkid=844053)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b597-p103">ATP anti-phishing is only available in Advanced Threat Protection, available with Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Advanced Threat Protection can be purchased as an add-on. (As a global admin, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information about plan options, see [Compare All Office 365 for Business Plans](https://go.microsoft.com/fwlink/?linkid=844053).</span></span> 
    
## <a name="how-atp-anti-phishing-works"></a><span data-ttu-id="5b597-115">ATP フィッシング詐欺対策のしくみ</span><span class="sxs-lookup"><span data-stu-id="5b597-115">How ATP anti-phishing works</span></span>
<span data-ttu-id="5b597-116"><a name="Howantiphishworks"> </a></span><span class="sxs-lookup"><span data-stu-id="5b597-116"></span></span>

<span data-ttu-id="5b597-p104">ATP フィッシング詐欺対策は、メッセージはフィッシング詐欺である可能性があります評価指標の受信メッセージをチェックします。かどうかメッセージにポリシーを適用し、適切な処置を決定するのにはメッセージを分析するモデルを学習する複数のコンピューターで受信メッセージを評価するユーザーは、ATP のポリシー (安全な添付ファイル、安全なリンクまたはフィッシング詐欺対策) で説明するたびに構成済みのポリシーに基づいて取得されます。</span><span class="sxs-lookup"><span data-stu-id="5b597-p104">ATP anti-phishing checks incoming messages for indicators that the message may be phishing. Whenever a user is covered by an ATP policy (safe attachments, safe links or anti-phishing) the incoming message is evaluated by multiple machine learning models that analyze the message to determine if the policy applies to the message and the appropriate action is taken, based on the configured policy.</span></span>
  
<span data-ttu-id="5b597-p105">ATP フィッシング詐欺対策には、ユーザーまたはドメインのいずれかの偽装は、フィッシング攻撃に対する保護を提供するポリシーを定義するには、Office 365 のグローバル管理者またはセキュリティ管理者ができます。(またはその両方) します。Office 365 のグローバル管理者またはセキュリティ管理者は、固定リストのユーザーまたはドメインまたはメールボックスのインテリジェンスを使用していずれかの方法を使用して偽装攻撃からは、どのユーザーやドメインを保護する必要がありますポリシー内で定義します。メールボックスの情報は、ユーザーの電子メールの習慣や個人の連絡先の詳細に理解することです。分析ツールは、個々 のユーザーの組織の内外の他のユーザーと通信してこれらの関係の地図を作成して学習します。このマップは、右のメッセージが偽装として識別されることを確認する方法の詳細を理解する分析ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b597-p105">ATP anti-phishing allows Office 365 global administrators or security admins to define policies that provide protection against phishing attacks that include impersonation of either users or domains. (or both). Office 365 global administrators or security admins define within the policy which user and domains should be protected from impersonation attacks using either a fixed list of users or domains or by using mailbox intelligence. Mailbox intelligence is an advanced understanding of a user's email habits and personal contacts. ATP learns how each individual user communicates with other users inside and outside the organization and builds up a map of these relationships. This map allows ATP to understand more details about how to ensure the right messages are identified as impersonation.</span></span>
  
<span data-ttu-id="5b597-p106">ATP フィッシング詐欺対策ポリシーをユーザーまたはグループ、組織内の特定のセットに、またはドメイン全体またはすべてのカスタム ドメインに適用することができます。詳細については、 [Office 365 の ATP のフィッシング詐欺対策ポリシーの設定](set-up-atp-anti-phishing-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b597-p106">ATP anti-phishing polices can be applied to a specific set of people or groups in your organization, or to an entire domain or all of your custom domains. To learn more, see [Set up ATP anti-phishing policies in Office 365](set-up-atp-anti-phishing-policies.md).</span></span>
  
## <a name="how-to-get-atp-anti-phishing"></a><span data-ttu-id="5b597-127">フィッシング詐欺対策の ATP を取得する方法</span><span class="sxs-lookup"><span data-stu-id="5b597-127">How to get ATP anti-phishing</span></span>
<span data-ttu-id="5b597-128"><a name="Howtogetantiphish"> </a></span><span class="sxs-lookup"><span data-stu-id="5b597-128"></span></span>

<span data-ttu-id="5b597-p107">ATP フィッシング詐欺対策は、高度な脅威保護の Office 365 エンタープライズ E5 に含まれている部分です。Office 365 エンタープライズ E1 または Office 365 エンタープライズ E3 へのアドオンとして高度な脅威保護を購入することもできます。プランのオプションの詳細については、[ビジネス プランのすべての Office 365 の比較](https://go.microsoft.com/fwlink/?linkid=844053)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b597-p107">ATP anti-phishing is part of Advanced Threat Protection, which is included in Office 365 Enterprise E5. Advanced Threat Protection can also be purchased as an add-on to Office 365 Enterprise E1 or Office 365 Enterprise E3. For more information about plan options, see [Compare All Office 365 for Business Plans](https://go.microsoft.com/fwlink/?linkid=844053).</span></span>
  
<span data-ttu-id="5b597-p108">フィッシング詐欺対策ポリシーでは、ATP のフィッシング対策が適用される、偽装・ ベースのポリシーの設定などです。( [Office 365 の ATP のフィッシング詐欺対策ポリシーの設定](set-up-atp-anti-phishing-policies.md)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="5b597-p108">ATP anti-phishing applies when an anti-phishing policy, such as an impersonation-based policy are set up. (See [Set up ATP anti-phishing policies in Office 365](set-up-atp-anti-phishing-policies.md).)</span></span>
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a><span data-ttu-id="5b597-134">ATP フィッシングの場所で確認する方法</span><span class="sxs-lookup"><span data-stu-id="5b597-134">How to know if ATP anti-phishing is in place</span></span>
<span data-ttu-id="5b597-135"><a name="IsantiphishOn"> </a></span><span class="sxs-lookup"><span data-stu-id="5b597-135"></span></span>

<span data-ttu-id="5b597-p109">ATP のフィッシング詐欺対策のポリシーは、保護をアクティブにするために定義しなければなりません。ユーザーに対してアクティブなフィッシング詐欺対策の機械学習モデルで ATP は、そのユーザーが定義済みの安全な添付ファイル、安全なリンク、またはフィッシング詐欺対策ポリシーの一部である必要があります。次の表では、いくつかのサンプル シナリオについて説明します。これらの例では、それぞれの組織は、脅威の高度な保護が含まれています Office 365 エンタープライズ E5 を使用しています。</span><span class="sxs-lookup"><span data-stu-id="5b597-p109">ATP anti-phishing policies must be defined in order for protection to be active. For ATP anti-phishing machine learning models to be active for a user, that user must be part of a defined safe attachment, safe links, or anti-phishing policy. The following table describes a few example scenarios. In each of these examples, the organization is using Office 365 Enterprise E5, which includes Advanced Threat Protection.</span></span>
  
|<span data-ttu-id="5b597-140">**シナリオ例**</span><span class="sxs-lookup"><span data-stu-id="5b597-140">**Example scenario**</span></span>|<span data-ttu-id="5b597-141">**ATP フィッシング詐欺対策はここで適用しますか。**</span><span class="sxs-lookup"><span data-stu-id="5b597-141">**Does ATP anti-phishing apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5b597-142">Pat の組織には、Office 365 のエンタープライズ E5 ですが、誰が ATP 安全な添付ファイル、ATP の安全なリンクやフィッシング詐欺をまだ高度な分析ツール用にポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="5b597-142">Pat's organization has Office 365 Enterprise E5, but no one has defined any policies for ATP safe attachments, ATP safe links or ATP advanced phishing yet.</span></span>|<span data-ttu-id="5b597-p110">違います。機能が利用可能ですが、動作する ATP のマシンのモデルを学習するために少なくとも 1 つの ATP のポリシーを定義しなければなりません。偽装の ATP のフィッシング詐欺対策ポリシーする必要がありますもあります。</span><span class="sxs-lookup"><span data-stu-id="5b597-p110">No. Although the feature is available, at least one ATP policy must be defined in order for the ATP machine learning models to work. For impersonation an ATP anti-phishing policy must also be in place.</span></span>|
|<span data-ttu-id="5b597-p111">Contoso の営業部門の従業員です。Lee の組織では、財務部門の従業員のみに適用されるように、ATP のフィッシング詐欺対策のポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="5b597-p111">Lee is an employee in the sales department at Contoso. Lee's organization has an ATP anti-phishing policy in place that applies to finance employees only.</span></span>|<span data-ttu-id="5b597-p112">違います。この例では、ATP フィッシング (マシン モデルと偽装保護) は、財務部門の従業員に適用されるが、販売部門を含め、他の従業員がいないとします。</span><span class="sxs-lookup"><span data-stu-id="5b597-p112">No. In this case, ATP anti-phishing (machine models and impersonation protection) would apply to finance employees, but other employees, including the sales department, would not.</span></span>|
|<span data-ttu-id="5b597-p113">昨日、ジャンの組織で Office 365 管理者は、すべての従業員に適用される ATP のフィッシング詐欺対策ポリシーを設定します。今日以前のバージョンでは、Jean は、偽装によって、ポリシーを含む電子メール メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="5b597-p113">Yesterday, an Office 365 administrator at Jean's organization set up an ATP anti-phishing policy that applies to all employees. Earlier today, Jean received an email message that includes an impersonation covered by the policy.</span></span>|<span data-ttu-id="5b597-p114">うん。この例では、ジャンが高度な脅威を保護するためのライセンスを持つし、ジャンを含む ATP フィッシング詐欺対策のポリシーが定義されています。新しいポリシーを有効にするデータ センターの間を約 30 分がかかります1 日はここで渡される、ため、ポリシーが有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b597-p114">Yes. In this example, Jean has a license for Advanced Threat Protection, and an ATP anti-phishing policy that includes Jean has been defined. It typically takes about 30 minutes for a new policy to take effect across datacenters; since a day has passed in this case, the policy should be in effect.</span></span>|
   
## <a name="related-topics"></a><span data-ttu-id="5b597-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b597-155">Related topics</span></span>
<span data-ttu-id="5b597-156"><a name="IsantiphishOn"> </a></span><span class="sxs-lookup"><span data-stu-id="5b597-156"></span></span>

[<span data-ttu-id="5b597-157">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5b597-157">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="5b597-158">Office 365 でのフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="5b597-158">Anti-phishing protection in Office 365</span></span>](anti-phishing-protection.md)
  
[<span data-ttu-id="5b597-159">Office 365 の ATP のフィッシング詐欺対策ポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="5b597-159">Set up ATP anti-phishing policies in Office 365</span></span>](set-up-atp-anti-phishing-policies.md)
  
[<span data-ttu-id="5b597-160">Office 365 の ATP の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="5b597-160">ATP safe links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="5b597-161">Office 365 の ATP の安全なリンク ポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="5b597-161">Set up ATP safe links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="5b597-162">安全な添付ファイルを Office 365 で ATP</span><span class="sxs-lookup"><span data-stu-id="5b597-162">ATP safe attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="5b597-163">Office 365 の ATP の安全な添付ファイル ポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="5b597-163">Set up ATP safe attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
  
[<span data-ttu-id="5b597-164">脅威の高度な保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="5b597-164">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

