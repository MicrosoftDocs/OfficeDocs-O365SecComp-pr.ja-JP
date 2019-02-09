---
title: Office 365 の ATP のフィッシング詐欺対策機能
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
description: ATP フィッシング詐欺対策は、Office 365 の高度な脅威保護の一環です。ATP フィッシング詐欺対策には、商品とスピアー フィッシング攻撃に対する保護を提供する受信したメッセージに偽装検出アルゴリズムとコンピューターの学習モデルのセットが適用されます。すべてのメッセージは予告なしに広範囲にわたる機械学習モデルのさまざまなユーザーおよびドメインの偽装攻撃から保護するために使用する高度なアルゴリズムのセットと、フィッシング詐欺メッセージを検出するためにトレーニングをされることがあります。
ms.openlocfilehash: c3e44a313bf9c823fbfda138fc5a10294993d509
ms.sourcegitcommit: c1c41744c2de89c9e172f817c8f73bb0ada81a58
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792272"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a><span data-ttu-id="1b3e1-105">Office 365 の ATP のフィッシング詐欺対策機能</span><span class="sxs-lookup"><span data-stu-id="1b3e1-105">ATP anti-phishing capabilities in Office 365</span></span>

<span data-ttu-id="1b3e1-p102">ATP フィッシング詐欺対策は、 [Office 365 の高度な脅威保護](office-365-atp.md)の一環です。ATP フィッシング詐欺対策には、商品とスピアー フィッシング攻撃に対する保護を提供する受信したメッセージに偽装検出アルゴリズムとコンピューターの学習モデルのセットが適用されます。すべてのメッセージは予告なしに広範囲にわたる機械学習モデルのさまざまなユーザーおよびドメインの偽装攻撃から保護するために使用する高度なアルゴリズムのセットと、フィッシング詐欺メッセージを検出するためにトレーニングをされることがあります。ATP フィッシング詐欺対策は、設定に基づいて、組織を保護する、Office 365 のグローバルまたはセキュリティ管理者によって設定され、ポリシーにします。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-p102">ATP anti-phishing is part of [Office 365 Advanced Threat Protection](office-365-atp.md). ATP anti-phishing applies a set of machine learning models together with impersonation detection algorithms to incoming messages to provide protection for commodity and spear phishing attacks. All messages are subject to an extensive set of machine learning models trained to detect phishing messages, together with a set of advanced algorithms used to protect against various user and domain impersonation attacks. ATP anti-phishing protects your organization according to polices that are set by your Office 365 global or security administrators.</span></span>
  
<span data-ttu-id="1b3e1-110">詳細については、 [Office 365 でのフィッシング詐欺対策ポリシーの設定](set-up-anti-phishing-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-110">To learn more, see [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1b3e1-p103">ATP フィッシング詐欺対策は高度な脅威保護[365 企業の Microsoft](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 ビジネス](https://www.microsoft.com/microsoft-365/business)、Office 365 エンタープライズ E5、Office 365 の教育 A5 など、サブスクリプションに含まれています。組織が Office 365 の分析ツールが含まれていない Office 365 のサブスクリプションの場合は、アドオンとして可能性のある ATP を購入できます。詳細については、 [Office 365 の高度な脅威保護の計画と価格設定](https://products.office.com/exchange/advance-threat-protection)と[Office 365 高度な脅威保護サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-p103">ATP anti-phishing is only available in Advanced Threat Protection, which is included in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

## <a name="how-atp-anti-phishing-works"></a><span data-ttu-id="1b3e1-113">ATP フィッシング詐欺対策のしくみ</span><span class="sxs-lookup"><span data-stu-id="1b3e1-113">How ATP anti-phishing works</span></span>

<span data-ttu-id="1b3e1-p104">ATP フィッシング詐欺対策は、メッセージはフィッシング詐欺である可能性があります評価指標の受信メッセージをチェックします。かどうかメッセージにポリシーを適用し、適切な処置を決定するのにはメッセージを分析するモデルを学習する複数のコンピューターで受信メッセージを評価するユーザーは、ATP のポリシー (安全な添付ファイル、安全なリンクまたはフィッシング詐欺対策) で説明するたびに構成済みのポリシーに基づいて取得されます。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-p104">ATP anti-phishing checks incoming messages for indicators that the message may be phishing. Whenever a user is covered by an ATP policy (safe attachments, safe links or anti-phishing) the incoming message is evaluated by multiple machine learning models that analyze the message to determine if the policy applies to the message and the appropriate action is taken, based on the configured policy.</span></span>
  
<span data-ttu-id="1b3e1-p105">ATP フィッシング詐欺対策には、ユーザーまたはドメインのいずれかの偽装は、フィッシング攻撃に対する保護を提供するポリシーを定義するには、Office 365 のグローバル管理者またはセキュリティ管理者ができます。(またはその両方) します。Office 365 のグローバル管理者またはセキュリティ管理者は、固定リストのユーザーまたはドメインまたはメールボックスのインテリジェンスを使用していずれかの方法を使用して偽装攻撃からは、どのユーザーやドメインを保護する必要がありますポリシー内で定義します。メールボックスの情報は、ユーザーの電子メールの習慣や個人の連絡先の詳細に理解することです。分析ツールは、個々 のユーザーの組織の内外の他のユーザーと通信してこれらの関係の地図を作成して学習します。このマップは、右のメッセージが偽装として識別されることを確認する方法の詳細を理解する分析ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-p105">ATP anti-phishing allows Office 365 global administrators or security admins to define policies that provide protection against phishing attacks that include impersonation of either users or domains. (or both). Office 365 global administrators or security admins define within the policy which user and domains should be protected from impersonation attacks using either a fixed list of users or domains or by using mailbox intelligence. Mailbox intelligence is an advanced understanding of a user's email habits and personal contacts. ATP learns how each individual user communicates with other users inside and outside the organization and builds up a map of these relationships. This map allows ATP to understand more details about how to ensure the right messages are identified as impersonation.</span></span>
  
<span data-ttu-id="1b3e1-p106">ATP フィッシング詐欺対策ポリシーをユーザーまたはグループ、組織内の特定のセットに、またはドメイン全体またはすべてのカスタム ドメインに適用することができます。詳細については、 [Office 365 でのフィッシング詐欺対策ポリシーの設定](set-up-anti-phishing-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-p106">ATP anti-phishing polices can be applied to a specific set of people or groups in your organization, or to an entire domain or all of your custom domains. To learn more, see [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
## <a name="how-to-get-atp-anti-phishing"></a><span data-ttu-id="1b3e1-124">フィッシング詐欺対策の ATP を取得する方法</span><span class="sxs-lookup"><span data-stu-id="1b3e1-124">How to get ATP anti-phishing</span></span>

<span data-ttu-id="1b3e1-p107">ATP のフィッシング対策機能は、[高度な脅威保護](office-365-atp.md)の一部ただし、ATP フィッシング防止対策には、フィッシング詐欺対策のポリシーが定義されている場合が適用されます。(1 つの例は、偽装に基づくポリシーです)。[Office 365 でのフィッシング詐欺対策ポリシーの設定](set-up-anti-phishing-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-p107">ATP Anti-Phishing features are part of [Advanced Threat Protection](office-365-atp.md); however, ATP anti-phishing protection applies when anti-phishing policies are defined. (One example is an impersonation-based policy.) See [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a><span data-ttu-id="1b3e1-127">ATP フィッシングの場所で確認する方法</span><span class="sxs-lookup"><span data-stu-id="1b3e1-127">How to know if ATP anti-phishing is in place</span></span>

<span data-ttu-id="1b3e1-p108">ATP のフィッシング詐欺対策のポリシーは、保護を有効にするために定義しなければなりません。保護を確認するのには、まずこれが設定されてを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-p108">ATP anti-phishing policies must be defined in order for protection to be in effect. Check this first to verify protection is in place.</span></span>

<span data-ttu-id="1b3e1-p109">さらに、レポートは、組織のサービスを使用する方法を表示するため。詳細については、 [Office 365 の高度な脅威保護のためのレポートを表示する](view-reports-for-atp.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-p109">In addition, reports are available to show how the service is working for your organization. To learn more, see [View reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md).</span></span>

<span data-ttu-id="1b3e1-132">ATP フィッシング詐欺対策のマシンが特定のユーザーに対してアクティブなモデルの学習、そのユーザーが定義されている[安全な添付ファイルの分析ツール](atp-safe-attachments.md)、[分析ツールの安全なリンク](atp-safe-links.md)、または ATP フィッシング詐欺対策ポリシーの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-132">For ATP anti-phishing machine learning models to be active for a particular user, that user must be part of a defined [ATP Safe Attachements](atp-safe-attachments.md), [ATP Safe Links](atp-safe-links.md), or ATP Anti-Phishing policy.</span></span> 

<span data-ttu-id="1b3e1-p110">次の表では、いくつかのサンプル シナリオについて説明します。これらの例では、それぞれの組織は、脅威の高度な保護が含まれています Office 365 エンタープライズ E5 を使用しています。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-p110">The following table describes a few example scenarios. In each of these examples, the organization is using Office 365 Enterprise E5, which includes Advanced Threat Protection.</span></span>
  
|<span data-ttu-id="1b3e1-135">**シナリオ例**</span><span class="sxs-lookup"><span data-stu-id="1b3e1-135">**Example scenario**</span></span>|<span data-ttu-id="1b3e1-136">**ATP フィッシング詐欺対策はここで適用しますか。**</span><span class="sxs-lookup"><span data-stu-id="1b3e1-136">**Does ATP anti-phishing apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b3e1-137">Pat の組織には、Office 365 のエンタープライズ E5 ですが、誰が ATP 安全な添付ファイル、ATP の安全なリンクやフィッシング詐欺をまだ高度な分析ツール用にポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-137">Pat's organization has Office 365 Enterprise E5, but no one has defined any policies for ATP safe attachments, ATP safe links or ATP advanced phishing yet.</span></span>|<span data-ttu-id="1b3e1-p111">違います。機能が利用可能ですが、動作する ATP のマシンのモデルを学習するために少なくとも 1 つの ATP のポリシーを定義しなければなりません。偽装の ATP のフィッシング詐欺対策ポリシーする必要がありますもあります。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-p111">No. Although the feature is available, at least one ATP policy must be defined in order for the ATP machine learning models to work. For impersonation an ATP anti-phishing policy must also be in place.</span></span>|
|<span data-ttu-id="1b3e1-p112">Contoso の営業部門の従業員です。Lee の組織では、財務部門の従業員のみに適用されるように、ATP のフィッシング詐欺対策のポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-p112">Lee is an employee in the sales department at Contoso. Lee's organization has an ATP anti-phishing policy in place that applies to finance employees only.</span></span>|<span data-ttu-id="1b3e1-p113">違います。この例では、ATP フィッシング (マシン モデルと偽装保護) は、財務部門の従業員に適用されるが、販売部門を含め、他の従業員がいないとします。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-p113">No. In this case, ATP anti-phishing (machine models and impersonation protection) would apply to finance employees, but other employees, including the sales department, would not.</span></span>|
|<span data-ttu-id="1b3e1-p114">昨日、ジャンの組織で Office 365 管理者は、すべての従業員に適用される ATP のフィッシング詐欺対策ポリシーを設定します。今日以前のバージョンでは、Jean は、偽装によって、ポリシーを含む電子メール メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-p114">Yesterday, an Office 365 administrator at Jean's organization set up an ATP anti-phishing policy that applies to all employees. Earlier today, Jean received an email message that includes an impersonation covered by the policy.</span></span>|<span data-ttu-id="1b3e1-p115">うん。この例では、ジャンが高度な脅威を保護するためのライセンスを持つし、ジャンを含む ATP フィッシング詐欺対策のポリシーが定義されています。新しいポリシーを有効にするデータ センターの間を約 30 分がかかります1 日はここで渡される、ため、ポリシーが有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-p115">Yes. In this example, Jean has a license for Advanced Threat Protection, and an ATP anti-phishing policy that includes Jean has been defined. It typically takes about 30 minutes for a new policy to take effect across datacenters; since a day has passed in this case, the policy should be in effect.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="1b3e1-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b3e1-150">Related topics</span></span>

[<span data-ttu-id="1b3e1-151">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1b3e1-151">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="1b3e1-152">Office 365 でのフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="1b3e1-152">Anti-phishing protection in Office 365</span></span>](anti-phishing-protection.md)
  
[<span data-ttu-id="1b3e1-153">Office 365 でのフィッシング詐欺対策ポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="1b3e1-153">Set up anti-phishing policies in Office 365</span></span>](set-up-anti-phishing-policies.md)
  
[<span data-ttu-id="1b3e1-154">Office 365 の ATP の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="1b3e1-154">ATP safe links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="1b3e1-155">Office 365 の ATP の安全なリンク ポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="1b3e1-155">Set up ATP safe links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="1b3e1-156">安全な添付ファイルを Office 365 で ATP</span><span class="sxs-lookup"><span data-stu-id="1b3e1-156">ATP safe attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="1b3e1-157">Office 365 の ATP の安全な添付ファイル ポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="1b3e1-157">Set up ATP safe attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
  
[<span data-ttu-id="1b3e1-158">脅威の高度な保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="1b3e1-158">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
