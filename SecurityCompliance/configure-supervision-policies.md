---
title: 組織用に監督ポリシーを構成する
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: 監督機関による監査ポリシーを設定すると、確認のため、従業員の通信をキャプチャします。
ms.openlocfilehash: 898ef9951ea20dec1e0cc6c28ad1ed6f9a0ded6e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29768038"
---
# <a name="configure-supervision-policies-for-your-organization"></a><span data-ttu-id="e2eb3-103">組織用に監督ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="e2eb3-103">Configure supervision policies for your organization</span></span>

<span data-ttu-id="e2eb3-p101">監督ポリシーを使用すると、内部または外部の校閲者による、従業員の通信をキャプチャします。監督のポリシーが、組織内の通信の監視にどのように役立つかについての詳細については、 [Office 365 での監視ポリシー](supervision-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p101">Use supervision policies to capture employee communications for examination by internal or external reviewers. For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e2eb3-p102">監督ポリシーで監視対象のユーザーは、準拠の高度なアドオンをいずれかの Office 365 エンタープライズ E3 ライセンスを取得する必要がありますか、Office 365 エンタープライズ E5 のサブスクリプションに含まれます。しない既存のエンタープライズ E5 計画して監視を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p102">Users monitored by supervision policies must have either an Office 365 Enterprise E3 license with the Advanced Compliance add-on or be included in an Office 365 Enterprise E5 subscription. If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="e2eb3-108">設定し、Office 365 の組織の監視を使用してこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-108">Follow these steps to set up and use supervision in your Office 365 organization:</span></span>
  
- <span data-ttu-id="e2eb3-109">**手順 (省略可能) 1** - [監督のグループを設定します](configure-supervision-policies.md#exampledist)</span><span class="sxs-lookup"><span data-stu-id="e2eb3-109">**Step 1 (optional)** - [Set up groups for Supervision](configure-supervision-policies.md#exampledist)</span></span>

    <span data-ttu-id="e2eb3-p103">監督の使用を開始する前に、ユーザーは、通信内容を確認し、それらのレビューを実行する人を決定します。監督の動作を確認するのには、いくつかのユーザーを開始する場合は、ここではグループの設定を省略できます。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p103">Before you start using supervision, determine who will have their communications reviewed and who will perform those reviews. If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="e2eb3-112">**手順 2 (必須)** - [監督は、組織で使用可能なを作成します。](configure-supervision-policies.md#MakeAvailable)</span><span class="sxs-lookup"><span data-stu-id="e2eb3-112">**Step 2 (required)** - [Make supervision available in your organization](configure-supervision-policies.md#MakeAvailable)</span></span>

    <span data-ttu-id="e2eb3-p104">自身に追加、監督機関による監査の役割のグループ ポリシーを設定することができますように。このロールが割り当てられているを持つ任意のユーザー ページにアクセスできます、**監督\*\*\*\*データの管理**下にあるセキュリティ & コンプライアンス センターで。情報を確認する電子メールが Exchange のオンラインでホストされている場合は、その各校閲者が[Exchange Online にリモート PowerShell のアクセス](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p104">Add yourself to the Supervisory Review role group so you can set up policies. Anyone who has this role assigned can access the **Supervision** page under **Data Governance** in the Security & Compliance Center. If email to be reviewed is hosted on Exchange Online, each reviewer must also have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="e2eb3-116">**手順 3 (省略可能)** - [の構成機密情報のカスタム型またはカスタム キーワード辞書と辞書](configure-supervision-policies.md#sensitiveinfo)</span><span class="sxs-lookup"><span data-stu-id="e2eb3-116">**Step 3 (optional)** - [Configure custom sensitive information types or custom keyword dictionaries/lexicons](configure-supervision-policies.md#sensitiveinfo)</span></span>

    <span data-ttu-id="e2eb3-117">監督ポリシーの機密情報のカスタム型またはカスタム キーワードの辞書を使用する場合は、監督のウィザードを開始する前に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-117">If you need to use a custom sensitive info type or a custom keyword dictionary for your supervision policy, you'll need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="e2eb3-118">**手順 4 (必須)** - [監督のポリシーを設定します。](configure-supervision-policies.md#setupsuper)</span><span class="sxs-lookup"><span data-stu-id="e2eb3-118">**Step 4 (required)** - [Set up a supervision policy](configure-supervision-policies.md#setupsuper)</span></span>

    <span data-ttu-id="e2eb3-p105">セキュリティ & コンプライアンス センターでは、監督のポリシーを作成します。これらのポリシーでは、通信は、組織の見直しの対象とし、レビューを実行する必要がありますを指定を定義します。電子メール、マイクロソフトのチームのコミュニケーションと Facebook、Twitter など) などのサード パーティ プラットフォームの通信の通信が含まれます</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p105">You'll create supervision policies in the Security & Compliance Center. These policies define which communications are subject to review in your organization and specifies who should perform reviews. Communications include email and Microsoft Teams communications, as well as 3rd-party platform communications (such as Facebook, Twitter, etc.)</span></span>

- <span data-ttu-id="e2eb3-122">**手順 5: (省略可能)**[新しい監視ポリシーのテスト](configure-supervision-policies.md#TestPolicy)</span><span class="sxs-lookup"><span data-stu-id="e2eb3-122">**Step 5 - (optional)** [Test your new supervision policy](configure-supervision-policies.md#TestPolicy)</span></span>

    <span data-ttu-id="e2eb3-123">コンプライアンス戦略、標準を満たすことができることを保証する重要な部分は、必要に応じて、それが機能しているかどうかを確認するのには、監督のポリシーをテストします。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-123">Testing your supervision policy to make sure it is functioning as desired is an important part of ensuring that your compliance strategy is meeting your standards.</span></span>

- <span data-ttu-id="e2eb3-124">**ステップ 6 - (省略可能)**[Outlook アドインを Office 365 の監視のダッシュ ボードや通信のコールを管理するには、OWA を使用しない場合の校閲者の設定](configure-supervision-policies.md#UseOutlook)</span><span class="sxs-lookup"><span data-stu-id="e2eb3-124">**Step 6 - (optional)** [Set up Outlook add-in for reviewers who do not want to use Office 365 supervision dashboard or OWA to review supervised communications](configure-supervision-policies.md#UseOutlook)</span></span>

    <span data-ttu-id="e2eb3-125">監視アドインを Outlook のレビュー担当者にアクセスできます Outlook クライアントの監視機能の右を評価し、各項目を分類することができます。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-125">The Supervision add-in for Outlook gives reviewers access to the supervision functionality right within the Outlook client so they can assess and categorize each item.</span></span>

<span data-ttu-id="e2eb3-126"><a name="exampledist"> </a></span><span class="sxs-lookup"><span data-stu-id="e2eb3-126"></span></span>

## <a name="step-1---set-up-groups-for-supervision-optional"></a><span data-ttu-id="e2eb3-127">ステップ 1 - (省略可能) の監視のグループを設定</span><span class="sxs-lookup"><span data-stu-id="e2eb3-127">Step 1 - Set up groups for Supervision (optional)</span></span>

 <span data-ttu-id="e2eb3-p106">監督ポリシーを作成する場合、通信の確認を持って、それらのレビューを実行する人を決定します。ポリシーでは、個人またはグループのユーザーを識別するのに電子メール アドレスを使用します。セットアップを簡略化するのには、通信が確認されたユーザーのグループとは、それらの通信を確認するユーザーのグループを作成します。グループを使用している場合、いくつかを必要があります-たとえば、人の 2 つの異なるグループ間の通信を監視する場合、または管理するしようとしていないグループを指定する場合は、します。このしくみの詳細については、[配布グループの使用例](configure-supervision-policies.md#GroupExample)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p106">When you create a supervision policy, you'll determine who will have their communications reviewed and who will perform those reviews. In the policy, you'll use email addresses to identify individuals or groups of people. To simplify your setup, create groups for people who will have their communication reviewed and groups for people who will review those communications. If you're using groups, you might need several—for example, if you want to monitor communications between two distinct groups of people, or if you want to specify a group that isn't going to be supervised. See [Example distribution groups](configure-supervision-policies.md#GroupExample) for details about how this works.</span></span>
  
<span data-ttu-id="e2eb3-p107">Exchange 管理センターで配布グループを設定します間または組織内のグループ内での通信を監督する (**受信者**に\>**グループ**)。配布グループを設定する方法の詳細については、[配布グループの管理](http://go.microsoft.com/fwlink/?LinkId=613635)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p107">To supervise communications between or within groups in your organization, set up distribution groups in the Exchange admin center (go to **recipients** \> **groups**). For more information about setting up distribution groups, see [Manage distribution groups](http://go.microsoft.com/fwlink/?LinkId=613635)</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2eb3-p108">使用できます動的配布グループまたはセキュリティ グループを監督したい場合。組織に合わせてこれらかどうかを判断するには、必要があります、[メールが有効なセキュリティ グループの管理](http://go.microsoft.com/fwlink/?LinkId=627033)、および[動的配布グループの管理](http://go.microsoft.com/fwlink/?LinkId=627058)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p108">You can also use dynamic distribution groups or security groups for supervision if you prefer. To help you decide if these better fit your organization needs, see [Manage mail-enabled security groups](http://go.microsoft.com/fwlink/?LinkId=627033), and [Manage dynamic distribution groups](http://go.microsoft.com/fwlink/?LinkId=627058).</span></span>
  
<span data-ttu-id="e2eb3-137"><a name="GroupExample"> </a></span><span class="sxs-lookup"><span data-stu-id="e2eb3-137"></span></span>

### <a name="example-distribution-groups"></a><span data-ttu-id="e2eb3-138">配布グループの例</span><span class="sxs-lookup"><span data-stu-id="e2eb3-138">Example distribution groups</span></span>

<span data-ttu-id="e2eb3-139">この例には、contoso 社の財務国際と呼ばれる、金融機関に設定されている配布グループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-139">This example includes a distribution group that has been set up for a financial organization called Contoso Financial International.</span></span>
  
<span data-ttu-id="e2eb3-p109">Contoso Financial International では、米国のブローカー間の通信のサンプリングを監視する必要があります。しかし、そのグループ内の法令遵守責任者を監視する必要はありません。この例の場合、次のグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p109">In Contoso Financial International, a sampling of communications between brokers in the United States must be supervised. However, compliance officers within that group do not require supervision. For this example, we can create the following groups:</span></span>
  
|<span data-ttu-id="e2eb3-143">**セットアップする配布グループ**</span><span class="sxs-lookup"><span data-stu-id="e2eb3-143">**Set up this distribution group**</span></span>|<span data-ttu-id="e2eb3-144">**グループのアドレス (エイリアス)**</span><span class="sxs-lookup"><span data-stu-id="e2eb3-144">**Group address (alias)**</span></span>|<span data-ttu-id="e2eb3-145">**説明**</span><span class="sxs-lookup"><span data-stu-id="e2eb3-145">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e2eb3-146">米国のブローカー全員</span><span class="sxs-lookup"><span data-stu-id="e2eb3-146">All US brokers</span></span> | <span data-ttu-id="e2eb3-147">US_Brokers@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2eb3-147">US_Brokers@Contoso.com</span></span> | <span data-ttu-id="e2eb3-148">このグループには Contoso に勤務し米国を拠点とするブローカー全員の電子メール アドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-148">This group includes email addresses for all US-based brokers who work for Contoso.</span></span> |
| <span data-ttu-id="e2eb3-149">米国の法令遵守責任者全員</span><span class="sxs-lookup"><span data-stu-id="e2eb3-149">All US compliance officers</span></span> | <span data-ttu-id="e2eb3-150">US_Compliance@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2eb3-150">US_Compliance@Contoso.com</span></span>  | <span data-ttu-id="e2eb3-p110">このグループには、contoso 社のすべての英語ベースのコンプライアンス担当者の電子メール アドレスが含まれます。このグループがすべての米国のブローカーのサブセットであるため、監督のポリシーから控除コンプライアンス責任者にこのエイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p110">This group includes email addresses for all US-based compliance officers who work for Contoso. Because this group is a subset of all US-based brokers, you can use this alias to exempt compliance officers from a supervision policy.</span></span> |
  
<span data-ttu-id="e2eb3-153"><a name="MakeAvailable"> </a></span><span class="sxs-lookup"><span data-stu-id="e2eb3-153"></span></span>

## <a name="step-2---make-supervision-available-in-your-organization-required"></a><span data-ttu-id="e2eb3-154">ステップ 2 - (必須)、組織で利用可能な Make の監督</span><span class="sxs-lookup"><span data-stu-id="e2eb3-154">Step 2 - Make supervision available in your organization (required)</span></span>

<span data-ttu-id="e2eb3-155">**監督**として使用するメニュー オプション セキュリティ & コンプライアンス センターは、監督者の確認の管理者の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-155">To make **Supervision** available as a menu option in the Security & Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="e2eb3-156">これを行うには、監督機関による監査の役割グループのメンバーとして追加自分でするか、新しい役割グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-156">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a new role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="e2eb3-157">監督機関による監査の役割グループにメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-157">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="e2eb3-158">サインイン[https://protection.office.com](https://protection.office.com)組織の Office 365 の管理者アカウントの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-158">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="e2eb3-159">セキュリティ & コンプライアンス センターでは、**アクセス許可**に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-159">In the Security & Compliance Center, go to **Permissions**.</span></span>

3. <span data-ttu-id="e2eb3-160">**監督機関による監査**の役割グループを選択し、編集アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-160">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="e2eb3-161">[**メンバー** ] セクションでは、組織の監督を管理する人を追加します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-161">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="e2eb3-162">新しい役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-162">Create a new role group</span></span>

1. <span data-ttu-id="e2eb3-163">サインイン[https://protection.office.com](https://protection.office.com)組織の Office 365 の管理者アカウントの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-163">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="e2eb3-164">セキュリティ & コンプライアンス センターでは、**アクセス許可**に移動し、し、[追加] をクリックして (**+**)。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-164">In the Security & Compliance Center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="e2eb3-p111">[**役割**] セクションの [追加] をクリックします (**+**) をスクロールして [**レビュー管理者を監督**します。この役割を役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p111">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**. Add this role to the role group.</span></span>

4. <span data-ttu-id="e2eb3-167">[**メンバー** ] セクションでは、組織の監督を管理する人を追加します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-167">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

<span data-ttu-id="e2eb3-168">役割グループおよびアクセス許可の詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-168">For more information about role groups and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="e2eb3-169">(Exchange Online でメールがホストされている) 場合、校閲者の PowerShell のリモート アクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-169">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="e2eb3-170">[有効にするか Exchange のオンライン PowerShell へのアクセスを無効にする](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-170">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

<span data-ttu-id="e2eb3-171"><a name="sensitiveinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="e2eb3-171"></span></span>
  
## <a name="step-3---create-custom-sensitive-information-types-or-custom-keyword-dictionaries-optional"></a><span data-ttu-id="e2eb3-172">手順 3 - (省略可能) カスタムの機密性の高い情報の種類やキーワードのカスタム辞書を作成</span><span class="sxs-lookup"><span data-stu-id="e2eb3-172">Step 3 - Create custom sensitive information types or custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="e2eb3-173">既存のユーザー設定の機密性の高い情報の種類または監視ポリシー ウィザードでは、キーワードのカスタム辞書を選択するためにまず必要な場合にこれらの項目を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-173">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="e2eb3-174">カスタムの機密性の高い情報の種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-174">Create custom sensitive information types</span></span>

1. <span data-ttu-id="e2eb3-p112">Office 365 のセキュリティ & コンプライアンス センターでは、新しい種類の機密情報を作成します。**分類**に移動\>**機密性の高い情報の種類\*\*\*\*機密性の高い情報の種類の新規作成ウィザード**の手順に従います。ここで行います。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p112">Create a new sensitive information type in the Office 365 Security & Compliance Center. Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**. Here you will:</span></span>

    - <span data-ttu-id="e2eb3-178">機密性の高い情報の種類の説明と名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-178">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="e2eb3-179">近接、信頼レベル、および主なパターン要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-179">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="e2eb3-180">選択内容を確認し、機密性の高い情報の種類を作成</span><span class="sxs-lookup"><span data-stu-id="e2eb3-180">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="e2eb3-181">詳細な情報は、[機密情報のカスタム タイプを作成する](create-a-custom-sensitive-information-type.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-181">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

### <a name="create-custom-keyword-dictionarylexicon"></a><span data-ttu-id="e2eb3-182">カスタム キーワード辞書と用語集を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-182">Create custom keyword dictionary/lexicon</span></span>

1. <span data-ttu-id="e2eb3-p113">テキスト エディター (メモ帳など) を使用すると、監督のポリシーで監視するにはキーワードの用語を含む新しいファイルを作成します。別の行には、各用語かどうかを確認し、 **Unicode と utf-16 (リトルエンディアン)** 形式でファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p113">Using a text editor (like Notepad), create a new file that includes the keyword terms you'd like to monitor in a supervision policy. Make sure each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>
2. <span data-ttu-id="e2eb3-p114">PowerShell を使用して、Office 365 テナントには、キーワードのファイルをインポートします。PowerShell で Office 365 に接続するには、 [Office 365 のセキュリティ & コンプライアンス センター PowerShell への接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p114">Import the keyword file into your Office 365 tenant using PowerShell. To connect to Office 365 with PowerShell, see [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

    <span data-ttu-id="e2eb3-187">PowerShell で Office 365 に接続した後、キーワードの辞書をインポートするのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-187">After you've connected to Office 365 with PowerShell, run the following commands to import your keyword dictionary:</span></span>

    ```
    $fileData = Get-Content "your keyword path and file name" -Encoding Byte -ReadCount 0

    New-DlpKeywordDictionary -Name "Name for your keyword dictionary" -Description "optional description for your keyword dictionary" -FileData $fileData
    ```
    <span data-ttu-id="e2eb3-188">詳細な情報は、[キーワード辞書を作成する](create-a-keyword-dictionary.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-188">For more detailed information, see [Create a keyword dictionary](create-a-keyword-dictionary.md).</span></span>

3. <span data-ttu-id="e2eb3-p115">Office 365 のセキュリティ & コンプライアンス センターでは、新しい種類の機密情報を作成します。**分類**に移動\>**機密性の高い情報の種類\*\*\*\*機密性の高い情報の種類の新規作成ウィザード**の手順に従います。ここで行います。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p115">Create a new sensitive information type in the Office 365 Security & Compliance Center. Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**. Here you will:</span></span>

    - <span data-ttu-id="e2eb3-192">機密性の高い情報の種類の説明と名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-192">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="e2eb3-193">一致する要素の要件として、ユーザー辞書を追加します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-193">Add your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="e2eb3-194">選択内容を確認し、機密性の高い情報の種類を作成</span><span class="sxs-lookup"><span data-stu-id="e2eb3-194">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="e2eb3-195">ユーザー辞書と辞書が作成されると、 [Get DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary)コマンドレットを使用して構成されているキーワードを表示またはを追加したり[セット DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary)コマンドレットを使用して条件を削除します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-195">After the custom dictionary/lexicon is created, you can view the configured keywords using the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet.</span></span>

    <span data-ttu-id="e2eb3-196">詳細な情報は、[機密情報のカスタム タイプを作成する](create-a-custom-sensitive-information-type.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-196">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

<span data-ttu-id="e2eb3-197"><a name="setupsuper"> </a></span><span class="sxs-lookup"><span data-stu-id="e2eb3-197"></span></span>

## <a name="step-4---set-up-a-supervision-policy-required"></a><span data-ttu-id="e2eb3-198">ステップ 4 - (必須) の監視ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-198">Step 4 - Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="e2eb3-199">サインイン[https://protection.office.com](https://protection.office.com)組織の Office 365 の管理者アカウントの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-199">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="e2eb3-200">セキュリティ & コンプライアンス センターでは、**監督**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-200">In the Security & Compliance Center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="e2eb3-p116">**作成**] を選択し、ウィザードで、ポリシーの以下のページを設定します。ウィザードを使用すると、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p116">Select **Create** and then follow the wizard to set up the following pages of the policy. Using the wizard, you will:</span></span>

    - <span data-ttu-id="e2eb3-203">名前と説明は、ポリシーを提供します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-203">Give the policy a name and description.</span></span>
    - <span data-ttu-id="e2eb3-204">ユーザーまたはグループを除外するかを選択するなど、監督には、ユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-204">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="e2eb3-205">監督のポリシーの条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-205">Define the supervision policy conditions.</span></span>
    - <span data-ttu-id="e2eb3-p117">機密性の高い情報の種類を含めるかを選択します。これは、既定およびカスタムの機密性の高い情報の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p117">Choose if you'd like to include sensitive information types. This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="e2eb3-208">確認するのには通信の割合を定義します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-208">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="e2eb3-p118">ポリシーのレビュー担当者を選択します。レビュー担当者は、個々 のユーザーまたは[メールが有効なセキュリティ グループ](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)にあります。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p118">Choose the reviewers for the policy. Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span>
    - <span data-ttu-id="e2eb3-211">ポリシー選択内容を確認し、ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-211">Review your policy selections and create the policy.</span></span>

<span data-ttu-id="e2eb3-212"><a name="TestPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="e2eb3-212"></span></span>

## <a name="step-5---test-your-supervision-policy-optional"></a><span data-ttu-id="e2eb3-213">手順 5: (省略可能)、監督ポリシーをテストします。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-213">Step 5 - Test your supervision policy (optional)</span></span>

<span data-ttu-id="e2eb3-p119">監督ポリシーを作成した後に定義した条件は、ポリシーによって正しく強制されているかどうかを確認するテストすることをお勧めです。することも[、データ損失防止 (DLP) のポリシーをテスト](create-test-tune-dlp-policy.md)する場合は、監督のポリシーには、機密性の高い情報の種類が含まれます。監督ポリシーをテストするのには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p119">After you create a supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy. You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types. Follow the steps below to test your supervision policy:</span></span>

1. <span data-ttu-id="e2eb3-217">開いている電子メール クライアント、またはマイクロソフトのチーム、コールを管理のユーザーとしてログインをテストするポリシーで定義されています。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-217">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="e2eb3-p120">電子メールまたは監督のポリシーで定義した条件に適合するマイクロソフトのチーム チャットを送信します。キーワード、添付ファイルのサイズ、ドメインなどを指定できます。かどうか、ポリシーで構成されている条件付き設定は制限が多すぎてまたは寛大すぎると判断したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p120">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy. This can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy is too restrictive or too lenient.</span></span>

    > [!Note]
    > <span data-ttu-id="e2eb3-p121">定義されているポリシーの対象となるメールはほぼリアルタイムで処理され、ポリシーを構成した後すぐにテストすることができます。マイクロソフトのチームでのチャットは、ポリシーに完全に処理するのには最大 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p121">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured. Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="e2eb3-p122">監督のポリシーで指定されているレビュー担当者として、Office 365 のテナントにログインします。**監督**に移動 > *、カスタム ポリシー* > **オープン**ポリシーのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p122">Log into your Office 365 tenant as a reviewer designated in the supervision policy. Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

<span data-ttu-id="e2eb3-224"><a name="UseOutlook"> </a></span><span class="sxs-lookup"><span data-stu-id="e2eb3-224"></span></span>

## <a name="step-6---set-up-outlook-add-in-for-reviewers-optional"></a><span data-ttu-id="e2eb3-225">ステップ 6 - Outlook 用のアドインのレビュー担当者を設定する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="e2eb3-225">Step 6 - Set up Outlook add-in for reviewers (optional)</span></span>

<span data-ttu-id="e2eb3-226">通信を確認するのには、監督でダッシュ ボードまたは web 上の Outlook の Office 365 を使用する代わりに Outlook を使用する校閲者は、自分の Outlook クライアントの監視アドインをインストールしなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-226">Reviewers that want to use Outlook instead of using the Supervision dashboard in Office 365 or Outlook on the web to review communications must install the Supervision add-in for their Outlook client.</span></span>

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a><span data-ttu-id="e2eb3-227">監督のメールボックスのアドレスをコピーする手順 1。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-227">Step 1: Copy the address for the supervision mailbox</span></span>

<span data-ttu-id="e2eb3-228">Outlook デスクトップ用のアドインをインストールするには、監督のポリシー設定の一部として作成された監督のメールボックスのアドレスを必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-228">To install the add-in for Outlook desktop, you'll need the address for the supervision mailbox that was created as part of the supervision policy setup.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2eb3-229">だれかそれ以外の場合、ポリシーを作成する場合は、アドインをインストールするのにはこれらのファイルからこのアドレスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-229">If someone else created the policy, you'll need to get this address from them to install the add-in.</span></span>

 <span data-ttu-id="e2eb3-230">**監督のメールボックスのアドレスを検索するには**</span><span class="sxs-lookup"><span data-stu-id="e2eb3-230">**To find the supervision mailbox address**</span></span>
  
1. <span data-ttu-id="e2eb3-231">サインイン、[セキュリティ&amp;コンプライアンス センター](https://protection.office.com)組織の Office 365 の管理者アカウントの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-231">Sign into the [Security &amp; Compliance Center](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="e2eb3-232">**監督**に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-232">Go to **Supervision**.</span></span>

3. <span data-ttu-id="e2eb3-233">監督ポリシーを確認する通信を収集する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-233">Click the supervision policy that's gathering the communications you want to review.</span></span>

4. <span data-ttu-id="e2eb3-234">ポリシーの詳細フライアウトの**メールボックスの監督**の下で、アドレスをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-234">In the policy details flyout, under **Supervision mailbox**, copy the address.</span></span><br/><span data-ttu-id="e2eb3-235">![監督ポリシーの詳細のフライアウトが強調表示されている監督のメールボックスのアドレスが表示されているの「メールボックスの監視」セクション](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span><span class="sxs-lookup"><span data-stu-id="e2eb3-235">![The 'Supervision Mailbox' section of a supervision policy's details flyout showing the supervision mailbox address highlighted](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span></span>
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a><span data-ttu-id="e2eb3-236">ステップ 2: Outlook デスクトップからのアクセスの監視のメールボックスを構成します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-236">Step 2: Configure the supervision mailbox for Outlook desktop access</span></span>

<span data-ttu-id="e2eb3-237">次に、校閲者は、監督のメールボックスを Outlook に接続するためにはいくつかの Exchange のオンラインの PowerShell コマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-237">Next, reviewers will need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.</span></span>
  
1. <span data-ttu-id="e2eb3-p123">オンライン PowerShell を交換するために接続します。[これはどのようにしますか?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p123">Connect to Exchange Online PowerShell. [How do I do this?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span></span>

2. <span data-ttu-id="e2eb3-240">*SupervisoryReview{GUID}@domain.onmicrosoft.com*が、上記の手順 1 でコピーしたアドレスであり、*ユーザー*は、手順 3 で監督のメールボックスに接続する人の校閲者の名前を次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-240">Run the following commands, where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will be connecting to the supervision mailbox in Step 3.</span></span>

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. <span data-ttu-id="e2eb3-241">以下の手順 3 移動する前に 1 時間以上まで待機します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-241">Wait at least an hour before moving on to Step 3 below.</span></span>

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a><span data-ttu-id="e2eb3-242">監督のメールボックスに接続する Outlook プロファイルを作成する手順 3。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-242">Step 3: Create an Outlook profile to connect to the supervision mailbox</span></span>

<span data-ttu-id="e2eb3-243">最後の手順では、校閲者は、監督のメールボックスに接続する Outlook プロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-243">For the final step, reviewers will need to create an Outlook profile to connect to the supervision mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="e2eb3-p124">新しい Outlook プロファイルを作成するには、Windows コントロール パネルの [メールの設定を使用します。これらの設定を取得するためのパスは、Windows オペレーティング システム (Windows 7、Windows 8 の場合、または Windows の 10) を使用して、Outlook のバージョンがインストールされているによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p124">To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel. The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using, and which version of Outlook is installed.</span></span>
  
1. <span data-ttu-id="e2eb3-246">[コントロール パネル] を開き、ウィンドウの上部にある [**検索**] ボックスで**メール**を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-246">Open the Control Panel, and in the **Search** box at the top of the window, type **Mail**.</span></span><br/><span data-ttu-id="e2eb3-p125">(されないことを確認してコントロール パネルを取得する方法ですか。参照してください[場所は、コントロール パネルの [?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p125">(Not sure how to get to the Control Panel? See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span></span>
  
2. <span data-ttu-id="e2eb3-249">**メール**アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-249">Open the **Mail** app.</span></span>

3. <span data-ttu-id="e2eb3-250">**メール設定 - Outlook\*\*\*\*プロファイルの表示**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-250">In **Mail Setup - Outlook**, click **Show Profiles**.</span></span><br/><span data-ttu-id="e2eb3-251">![' メール設定 - Outlook] ダイアログ ボックスに、プロファイルの表示] ボタンがハイライトされます](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span><span class="sxs-lookup"><span data-stu-id="e2eb3-251">![The 'Mail Setup - Outlook' dialog box with the 'Show Profiles' button highlighted](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span></span>
  
4. <span data-ttu-id="e2eb3-p126">[**メール**] の [**追加**を] をクリックします。**新しいプロファイル**(**監督**) などの監督のメールボックスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p126">In **Mail**, click **Add**. Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).</span></span><br/><span data-ttu-id="e2eb3-254">!['監督' の名前を示す、[プロファイル名] ボックスで [新しいプロファイル] ダイアログ ボックス](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span><span class="sxs-lookup"><span data-stu-id="e2eb3-254">![The 'New Profile' dialog showing the name 'Supervision' in the 'Profile Name' box](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span></span>
  
5. <span data-ttu-id="e2eb3-255">**Outlook に接続**、**別のアカウントへの接続**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-255">In **Connect Outlook to Office 365**, click **Connect to a different account**.</span></span><br/><span data-ttu-id="e2eb3-256">![強調表示されている別のアカウントへ接続] リンクを使用して Office 365 に Outlook を接続する ' メッセージ](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span><span class="sxs-lookup"><span data-stu-id="e2eb3-256">![The 'Connect Outlook to Office 365' message with the 'Connect to a different account' link highlighted](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span></span>
  
6. <span data-ttu-id="e2eb3-257">**自動アカウント セットアップ**では、**手動設定] または [その他のサーバー**を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-257">In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.</span></span>

7. <span data-ttu-id="e2eb3-p127">**アカウント タイプの選択**] では、 **Office 365**を選択します。**電子メール アドレス**] ボックスで、以前にコピーした監督のメールボックスのアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-p127">In **Choose Your Account Type**, choose **Office 365**. Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously.</span></span><br/><span data-ttu-id="e2eb3-260">![強調表示されている [電子メール アドレス] ボックスを表示する Outlook の [アカウントの追加] ダイアログ ボックスの ' のアカウントの種類の選択] ページです。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span><span class="sxs-lookup"><span data-stu-id="e2eb3-260">![The 'Choose Your Account Type' page of the 'Add Account' dialog in Outlook showing the 'Email Address' box highlighted.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span></span>
  
8. <span data-ttu-id="e2eb3-261">ダイアログ ボックスが表示されたら、Office 365 のユーザーの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-261">When prompted, enter your Office 365 credentials.</span></span>

9. <span data-ttu-id="e2eb3-262">成功すると、表示されます、**監督 -\<ポリシー名\>** フォルダーが Outlook のフォルダー一覧ビューで表示します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-262">If successful, you'll see the **Supervision - \<policy name\>** folder listed in the Folder List view in Outlook.</span></span>

## <a name="powershell-reference"></a><span data-ttu-id="e2eb3-263">PowerShell の参照</span><span class="sxs-lookup"><span data-stu-id="e2eb3-263">PowerShell reference</span></span>

<span data-ttu-id="e2eb3-264">必要な場合は、作成し、次の PowerShell コマンドレットを使用して監視ポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="e2eb3-264">If needed, you can create and manage supervision policies using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="e2eb3-265">新しい-SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="e2eb3-265">New-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="e2eb3-266">Get SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="e2eb3-266">Get-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="e2eb3-267">セット SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="e2eb3-267">Set-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="e2eb3-268">削除 SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="e2eb3-268">Remove-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="e2eb3-269">新しい-SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="e2eb3-269">New-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="e2eb3-270">セット SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="e2eb3-270">Set-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="e2eb3-271">Get SupervisoryReviewActivity</span><span class="sxs-lookup"><span data-stu-id="e2eb3-271">Get-SupervisoryReviewActivity</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [<span data-ttu-id="e2eb3-272">Get SupervisoryReviewOverallProgressReport</span><span class="sxs-lookup"><span data-stu-id="e2eb3-272">Get-SupervisoryReviewOverallProgressReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [<span data-ttu-id="e2eb3-273">Get SupervisoryReviewTopCasesReport</span><span class="sxs-lookup"><span data-stu-id="e2eb3-273">Get-SupervisoryReviewTopCasesReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)