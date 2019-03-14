---
title: 組織用に監督ポリシーを構成する
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: 監督レビューポリシーを設定して、レビューのために従業員のコミュニケーションをキャプチャします。
ms.openlocfilehash: 2e321989934402b833d6190f65d696f4eb7919ca
ms.sourcegitcommit: 547a05da067a8f66fdaccf1cc399afcf863f5a87
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30474158"
---
# <a name="configure-supervision-policies-for-your-organization"></a><span data-ttu-id="3be2f-103">組織用に監督ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="3be2f-103">Configure supervision policies for your organization</span></span>

<span data-ttu-id="3be2f-104">監督ポリシーを使用して、内部または外部のレビューアーによる検査のために従業員の通信をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-104">Use supervision policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="3be2f-105">監督ポリシーが組織内の通信を監視するのに役立つ方法の詳細については、「 [Office 365 の監督ポリシー](supervision-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be2f-105">For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3be2f-106">監督ポリシーによって監視されるユーザーは、Microsoft 365 E5 コンプライアンスライセンス、Advanced コンプライアンスアドオンを備えた office 365 Enterprise E3 ライセンス、または office 365 Enterprise E5 サブスクリプションに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be2f-106">Users monitored by supervision policies must have either a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription.</span></span>
<span data-ttu-id="3be2f-107">既存の Enterprise e5 プランを所有しておらず、監督を試みる場合は、 [Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-107">If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="3be2f-108">Office 365 組織の監督をセットアップして使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-108">Follow these steps to set up and use supervision in your Office 365 organization:</span></span>
  
- <span data-ttu-id="3be2f-109">**手順 1 (オプション)** - [監督のグループをセットアップする](configure-supervision-policies.md#exampledist)</span><span class="sxs-lookup"><span data-stu-id="3be2f-109">**Step 1 (optional)** - [Set up groups for Supervision](configure-supervision-policies.md#exampledist)</span></span>

    <span data-ttu-id="3be2f-110">監督の使用を開始する前に、誰が通信をレビューし、それらのレビューを実行するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-110">Before you start using supervision, determine who will have their communications reviewed and who will perform those reviews.</span></span> <span data-ttu-id="3be2f-111">監督がどのように機能するかを確認するために、少数のユーザーのみを使用して作業を開始する場合は、現時点ではグループの設定を省略できます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-111">If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="3be2f-112">**手順 2 (必須)** - [組織内で監督を利用できるようにする](configure-supervision-policies.md#MakeAvailable)</span><span class="sxs-lookup"><span data-stu-id="3be2f-112">**Step 2 (required)** - [Make supervision available in your organization](configure-supervision-policies.md#MakeAvailable)</span></span>

    <span data-ttu-id="3be2f-113">ポリシーをセットアップできるように、自分を監督レビュー役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-113">Add yourself to the Supervisory Review role group so you can set up policies.</span></span> <span data-ttu-id="3be2f-114">この役割が割り当てられているすべてのユーザーは、Security & コンプライアンスセンターの**データガバナンス**の下にある [**監督**] ページにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-114">Anyone who has this role assigned can access the **Supervision** page under **Data Governance** in the Security & Compliance Center.</span></span> <span data-ttu-id="3be2f-115">確認する電子メールが exchange online でホストされている場合、各レビュー担当者も[exchange online へのリモート PowerShell アクセス権](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be2f-115">If email to be reviewed is hosted on Exchange Online, each reviewer must also have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="3be2f-116">**手順 3 (省略可能)** - [カスタムの機密情報の種類またはユーザー設定のキーワードディクショナリ/辞書を構成する](configure-supervision-policies.md#sensitiveinfo)</span><span class="sxs-lookup"><span data-stu-id="3be2f-116">**Step 3 (optional)** - [Configure custom sensitive information types or custom keyword dictionaries/lexicons](configure-supervision-policies.md#sensitiveinfo)</span></span>

    <span data-ttu-id="3be2f-117">監督ポリシーにカスタムの機密情報の種類またはカスタムキーワード辞書を使用する必要がある場合は、監督のウィザードを開始する前に、それを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be2f-117">If you need to use a custom sensitive info type or a custom keyword dictionary for your supervision policy, you'll need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="3be2f-118">**手順 4 (必須)** - [監督ポリシーをセットアップする](configure-supervision-policies.md#setupsuper)</span><span class="sxs-lookup"><span data-stu-id="3be2f-118">**Step 4 (required)** - [Set up a supervision policy](configure-supervision-policies.md#setupsuper)</span></span>

    <span data-ttu-id="3be2f-119">「Security & コンプライアンスセンターで監督ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-119">You'll create supervision policies in the Security & Compliance Center.</span></span> <span data-ttu-id="3be2f-120">これらのポリシーは、組織内で検討する必要のある通信を定義し、レビューを実行するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-120">These policies define which communications are subject to review in your organization and specifies who should perform reviews.</span></span> <span data-ttu-id="3be2f-121">コミュニケーションには、電子メールと Microsoft Teams の通信、およびサードパーティ製のプラットフォーム通信 (Facebook、Twitter など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-121">Communications include email and Microsoft Teams communications, as well as 3rd-party platform communications (such as Facebook, Twitter, etc.)</span></span>

- <span data-ttu-id="3be2f-122">**手順 5-(省略可能)**[新しい監督ポリシーをテストする](configure-supervision-policies.md#TestPolicy)</span><span class="sxs-lookup"><span data-stu-id="3be2f-122">**Step 5 - (optional)** [Test your new supervision policy](configure-supervision-policies.md#TestPolicy)</span></span>

    <span data-ttu-id="3be2f-123">監督ポリシーをテストして、必要に応じて機能していることを確認してください。これは、コンプライアンス戦略が標準を満たしていることを確認するための重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="3be2f-123">Testing your supervision policy to make sure it is functioning as desired is an important part of ensuring that your compliance strategy is meeting your standards.</span></span>

- <span data-ttu-id="3be2f-124">**手順 6-(省略可能)**[Office 365 監督ダッシュボードまたは web 上の outlook (以前の outlook web App) を使用しないで、監視された通信を確認するには、outlook を構成](configure-supervision-policies.md#UseOutlook)します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-124">**Step 6 - (optional)** [Configure Outlook for reviewers who do not want to use Office 365 supervision dashboard or Outlook on the web (formerly known as Outlook Web App) to review supervised communications](configure-supervision-policies.md#UseOutlook)</span></span>

    <span data-ttu-id="3be2f-125">outlook を構成して、レビューアーが outlook クライアント内の監督機能にアクセスできるようにして、各アイテムを評価および分類できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-125">Outlook can be configured to give reviewers access to the supervision functionality within the Outlook client so they can assess and categorize each item.</span></span>

<span data-ttu-id="3be2f-126"><a name="exampledist"> </a></span><span class="sxs-lookup"><span data-stu-id="3be2f-126"></span></span>

## <a name="step-1---set-up-groups-for-supervision-optional"></a><span data-ttu-id="3be2f-127">手順 1-監督のグループをセットアップする (オプション)</span><span class="sxs-lookup"><span data-stu-id="3be2f-127">Step 1 - Set up groups for Supervision (optional)</span></span>

 <span data-ttu-id="3be2f-128">監督ポリシーを作成すると、誰が通信をレビューし、それらのレビューを実行するかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-128">When you create a supervision policy, you'll determine who will have their communications reviewed and who will perform those reviews.</span></span> <span data-ttu-id="3be2f-129">このポリシーでは、電子メールアドレスを使用して個人またはユーザーのグループを識別します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-129">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="3be2f-130">セットアップを簡単にするために、コミュニケーションをレビューするユーザーのためのグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-130">To simplify your setup, create groups for people who will have their communication reviewed and groups for people who will review those communications.</span></span> <span data-ttu-id="3be2f-131">グループを使用している場合は、たとえば、2つの異なるグループ間の通信を監視する場合、または、監視しないグループを指定する場合などに、いくつかの必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3be2f-131">If you're using groups, you might need several—for example, if you want to monitor communications between two distinct groups of people, or if you want to specify a group that isn't going to be supervised.</span></span> <span data-ttu-id="3be2f-132">このしくみの詳細については、「[配布グループの例](configure-supervision-policies.md#GroupExample)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be2f-132">See [Example distribution groups](configure-supervision-policies.md#GroupExample) for details about how this works.</span></span>
  
<span data-ttu-id="3be2f-133">組織内のグループ間の通信を監督するには、Exchange 管理センターで配布グループを設定します (**受信者** \> **グループ**に移動します)。</span><span class="sxs-lookup"><span data-stu-id="3be2f-133">To supervise communications between or within groups in your organization, set up distribution groups in the Exchange admin center (go to **recipients** \> **groups**).</span></span> <span data-ttu-id="3be2f-134">配布グループの設定の詳細については、「[配布グループの管理](http://go.microsoft.com/fwlink/?LinkId=613635)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be2f-134">For more information about setting up distribution groups, see [Manage distribution groups](http://go.microsoft.com/fwlink/?LinkId=613635)</span></span>
  
> [!NOTE]
> <span data-ttu-id="3be2f-135">必要に応じて、監視に動的配布グループまたはセキュリティグループを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-135">You can also use dynamic distribution groups or security groups for supervision if you prefer.</span></span> <span data-ttu-id="3be2f-136">組織のニーズに適したものかどうかを判断するには、「[メールが有効なセキュリティグループの管理](http://go.microsoft.com/fwlink/?LinkId=627033)」と「[動的配布グループの管理](http://go.microsoft.com/fwlink/?LinkId=627058)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be2f-136">To help you decide if these better fit your organization needs, see [Manage mail-enabled security groups](http://go.microsoft.com/fwlink/?LinkId=627033), and [Manage dynamic distribution groups](http://go.microsoft.com/fwlink/?LinkId=627058).</span></span>
  
<span data-ttu-id="3be2f-137"><a name="GroupExample"> </a></span><span class="sxs-lookup"><span data-stu-id="3be2f-137"></span></span>

### <a name="example-distribution-groups"></a><span data-ttu-id="3be2f-138">配布グループの例</span><span class="sxs-lookup"><span data-stu-id="3be2f-138">Example distribution groups</span></span>

<span data-ttu-id="3be2f-139">この例には、Contoso の金融地域に設定されている配布グループが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3be2f-139">This example includes a distribution group that has been set up for a financial organization called Contoso Financial International.</span></span>
  
<span data-ttu-id="3be2f-140">Contoso 社の金融地域では、米国の仲立人間での通信のサンプリングを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be2f-140">In Contoso Financial International, a sampling of communications between brokers in the United States must be supervised.</span></span> <span data-ttu-id="3be2f-141">ただし、そのグループ内のコンプライアンス責任者は監督を必要としません。</span><span class="sxs-lookup"><span data-stu-id="3be2f-141">However, compliance officers within that group do not require supervision.</span></span> <span data-ttu-id="3be2f-142">この例では、次のグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-142">For this example, we can create the following groups:</span></span>
  
|<span data-ttu-id="3be2f-143">**この配布グループをセットアップする**</span><span class="sxs-lookup"><span data-stu-id="3be2f-143">**Set up this distribution group**</span></span>|<span data-ttu-id="3be2f-144">**グループアドレス (エイリアス)**</span><span class="sxs-lookup"><span data-stu-id="3be2f-144">**Group address (alias)**</span></span>|<span data-ttu-id="3be2f-145">**説明**</span><span class="sxs-lookup"><span data-stu-id="3be2f-145">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3be2f-146">すべての US ブローカー</span><span class="sxs-lookup"><span data-stu-id="3be2f-146">All US brokers</span></span> | <span data-ttu-id="3be2f-147">US_Brokers@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="3be2f-147">US_Brokers@Contoso.com</span></span> | <span data-ttu-id="3be2f-148">このグループには、Contoso に勤務しているすべての US ベースのブローカーの電子メールアドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3be2f-148">This group includes email addresses for all US-based brokers who work for Contoso.</span></span> |
| <span data-ttu-id="3be2f-149">すべての US コンプライアンス責任者</span><span class="sxs-lookup"><span data-stu-id="3be2f-149">All US compliance officers</span></span> | <span data-ttu-id="3be2f-150">US_Compliance@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="3be2f-150">US_Compliance@Contoso.com</span></span>  | <span data-ttu-id="3be2f-151">このグループには、Contoso に勤務しているすべての米準拠責任者の電子メールアドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3be2f-151">This group includes email addresses for all US-based compliance officers who work for Contoso.</span></span> <span data-ttu-id="3be2f-152">このグループはすべての US ベースのブローカーのサブセットであるため、このエイリアスを使用して、監督ポリシーからコンプライアンス担当者を除外することができます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-152">Because this group is a subset of all US-based brokers, you can use this alias to exempt compliance officers from a supervision policy.</span></span> |
  
<span data-ttu-id="3be2f-153"><a name="MakeAvailable"> </a></span><span class="sxs-lookup"><span data-stu-id="3be2f-153"></span></span>

## <a name="step-2---make-supervision-available-in-your-organization-required"></a><span data-ttu-id="3be2f-154">手順 2-組織で監督を利用できるようにする (必須)</span><span class="sxs-lookup"><span data-stu-id="3be2f-154">Step 2 - Make supervision available in your organization (required)</span></span>

<span data-ttu-id="3be2f-155">セキュリティ & コンプライアンスセンターで、**監督**をメニューオプションとして利用できるようにするには、監督レビュー管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be2f-155">To make **Supervision** available as a menu option in the Security & Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="3be2f-156">これを行うには、自分を監督レビュー役割グループのメンバーとして追加するか、新しい役割グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-156">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a new role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="3be2f-157">監督レビュー役割グループにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="3be2f-157">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="3be2f-158">Office 365 [https://protection.office.com](https://protection.office.com)組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-158">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="3be2f-159">セキュリティ & コンプライアンスセンターで、[**アクセス許可**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-159">In the Security & Compliance Center, go to **Permissions**.</span></span>

3. <span data-ttu-id="3be2f-160">[**監督レビュー** ] 役割グループを選択し、[編集] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-160">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="3be2f-161">[**メンバー** ] セクションで、組織の監督を管理するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-161">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="3be2f-162">新しい役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="3be2f-162">Create a new role group</span></span>

1. <span data-ttu-id="3be2f-163">Office 365 [https://protection.office.com](https://protection.office.com)組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-163">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="3be2f-164">セキュリティ & コンプライアンスセンターで、[**アクセス許可**] に移動し、[**+** 追加] () をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-164">In the Security & Compliance Center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="3be2f-165">[**役割**] セクションで、[追加**+**] () をクリックし、[**監督レビュー管理者**] まで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-165">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**.</span></span> <span data-ttu-id="3be2f-166">この役割を役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-166">Add this role to the role group.</span></span>

4. <span data-ttu-id="3be2f-167">[**メンバー** ] セクションで、組織の監督を管理するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-167">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

<span data-ttu-id="3be2f-168">役割グループとアクセス許可の詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be2f-168">For more information about role groups and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="3be2f-169">レビューアーのリモート PowerShell アクセスを有効にする (電子メールが Exchange Online でホストされている場合)</span><span class="sxs-lookup"><span data-stu-id="3be2f-169">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="3be2f-170">「 [Exchange Online PowerShell へのアクセスを有効または無効](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)にする」のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="3be2f-170">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

<span data-ttu-id="3be2f-171"><a name="sensitiveinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="3be2f-171"></span></span>
  
## <a name="step-3---create-custom-sensitive-information-types-or-custom-keyword-dictionaries-optional"></a><span data-ttu-id="3be2f-172">手順 3-カスタムの機密情報の種類またはユーザー設定のキーワードディクショナリを作成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="3be2f-172">Step 3 - Create custom sensitive information types or custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="3be2f-173">監督ポリシーウィザードで既存のカスタムの機密情報の種類またはカスタムキーワードディクショナリから選択するには、最初に、必要に応じてこれらの項目を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be2f-173">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="3be2f-174">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="3be2f-174">Create custom sensitive information types</span></span>

1. <span data-ttu-id="3be2f-175">Office 365 Security & コンプライアンスセンターで、新しい機密情報の種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-175">Create a new sensitive information type in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="3be2f-176">[**分類** \> **機密情報の種類**] に移動し、**新しい機密情報の種類ウィザード**の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3be2f-176">Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**.</span></span> <span data-ttu-id="3be2f-177">ここでは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3be2f-177">Here you will:</span></span>

    - <span data-ttu-id="3be2f-178">機密情報の種類の名前と説明を定義する</span><span class="sxs-lookup"><span data-stu-id="3be2f-178">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="3be2f-179">近接、信頼度、およびプライマリパターン要素を定義する</span><span class="sxs-lookup"><span data-stu-id="3be2f-179">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="3be2f-180">選択内容を確認し、機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="3be2f-180">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="3be2f-181">詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be2f-181">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

### <a name="create-custom-keyword-dictionarylexicon"></a><span data-ttu-id="3be2f-182">ユーザー設定のキーワード辞書または辞書を作成する</span><span class="sxs-lookup"><span data-stu-id="3be2f-182">Create custom keyword dictionary/lexicon</span></span>

1. <span data-ttu-id="3be2f-183">テキストエディター (メモ帳など) を使用して、監督ポリシーで監視するキーワード用語を含む新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-183">Using a text editor (like Notepad), create a new file that includes the keyword terms you'd like to monitor in a supervision policy.</span></span> <span data-ttu-id="3be2f-184">各用語が別々の行にあることを確認し、 **Unicode/utf-16 (リトルエンディアン)** 形式でファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-184">Make sure each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>
2. <span data-ttu-id="3be2f-185">PowerShell を使用して、Office 365 テナントにキーワードファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-185">Import the keyword file into your Office 365 tenant using PowerShell.</span></span> <span data-ttu-id="3be2f-186">powershell を使用して office 365 に接続する方法については、「 [connect to office 365 Security & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be2f-186">To connect to Office 365 with PowerShell, see [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

    <span data-ttu-id="3be2f-187">PowerShell を使用して Office 365 に接続した後、次のコマンドを実行してキーワード辞書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-187">After you've connected to Office 365 with PowerShell, run the following commands to import your keyword dictionary:</span></span>

    ```
    $fileData = Get-Content "your keyword path and file name" -Encoding Byte -ReadCount 0

    New-DlpKeywordDictionary -Name "Name for your keyword dictionary" -Description "optional description for your keyword dictionary" -FileData $fileData
    ```
    <span data-ttu-id="3be2f-188">詳細については、「 [Create a keyword dictionary](create-a-keyword-dictionary.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be2f-188">For more detailed information, see [Create a keyword dictionary](create-a-keyword-dictionary.md).</span></span>

3. <span data-ttu-id="3be2f-189">Office 365 Security & コンプライアンスセンターで、新しい機密情報の種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-189">Create a new sensitive information type in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="3be2f-190">[**分類** \> **機密情報の種類**] に移動し、**新しい機密情報の種類ウィザード**の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3be2f-190">Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**.</span></span> <span data-ttu-id="3be2f-191">ここでは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3be2f-191">Here you will:</span></span>

    - <span data-ttu-id="3be2f-192">機密情報の種類の名前と説明を定義する</span><span class="sxs-lookup"><span data-stu-id="3be2f-192">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="3be2f-193">マッチング要素の要件としてカスタム辞書を追加する</span><span class="sxs-lookup"><span data-stu-id="3be2f-193">Add your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="3be2f-194">選択内容を確認し、機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="3be2f-194">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="3be2f-195">ユーザー辞書または辞書を作成した後で、 [get-dlpkeyworddictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary)コマンドレットを使用して構成済みのキーワードを表示するか、 [get-dlpkeyworddictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary)コマンドレットを使用して用語を追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-195">After the custom dictionary/lexicon is created, you can view the configured keywords using the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet.</span></span>

    <span data-ttu-id="3be2f-196">詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be2f-196">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

<span data-ttu-id="3be2f-197"><a name="setupsuper"> </a></span><span class="sxs-lookup"><span data-stu-id="3be2f-197"></span></span>

## <a name="step-4---set-up-a-supervision-policy-required"></a><span data-ttu-id="3be2f-198">手順 4-監督ポリシーを設定する (必須)</span><span class="sxs-lookup"><span data-stu-id="3be2f-198">Step 4 - Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="3be2f-199">Office 365 [https://protection.office.com](https://protection.office.com)組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-199">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="3be2f-200">セキュリティ & コンプライアンスセンターで、[**監督**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-200">In the Security & Compliance Center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="3be2f-201">[**作成**] を選択し、ウィザードの指示に従って、ポリシーの次のページを設定します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-201">Select **Create** and then follow the wizard to set up the following pages of the policy.</span></span> <span data-ttu-id="3be2f-202">ウィザードを使用すると、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-202">Using the wizard, you will:</span></span>

    - <span data-ttu-id="3be2f-203">ポリシーに名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-203">Give the policy a name and description.</span></span>
    - <span data-ttu-id="3be2f-204">監督するユーザーまたはグループを選択します。これには、除外するユーザーまたはグループを選択することも含まれます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-204">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="3be2f-205">監督ポリシー条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-205">Define the supervision policy conditions.</span></span>
    - <span data-ttu-id="3be2f-206">機密情報の種類を含めるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-206">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="3be2f-207">ここでは、既定およびカスタムの機密情報の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-207">This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="3be2f-208">レビューする通信の割合を定義します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-208">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="3be2f-209">ポリシーのレビュー担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-209">Choose the reviewers for the policy.</span></span> <span data-ttu-id="3be2f-210">レビュー担当者は、個々のユーザーまたは[メールが有効なセキュリティグループに](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)することができます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-210">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span>
    - <span data-ttu-id="3be2f-211">ポリシーの選択を確認し、ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-211">Review your policy selections and create the policy.</span></span>

<span data-ttu-id="3be2f-212"><a name="TestPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="3be2f-212"></span></span>

## <a name="step-5---test-your-supervision-policy-optional"></a><span data-ttu-id="3be2f-213">手順 5-監督ポリシーをテストする (オプション)</span><span class="sxs-lookup"><span data-stu-id="3be2f-213">Step 5 - Test your supervision policy (optional)</span></span>

<span data-ttu-id="3be2f-214">監督ポリシーを作成したら、定義した条件がポリシーによって適切に適用されているかどうかをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-214">After you create a supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="3be2f-215">監督ポリシーに機密情報の種類が含まれている場合は、[データ損失防止 (DLP) ポリシーをテスト](create-test-tune-dlp-policy.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-215">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types.</span></span> <span data-ttu-id="3be2f-216">監督ポリシーをテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-216">Follow the steps below to test your supervision policy:</span></span>

1. <span data-ttu-id="3be2f-217">テストするポリシーで定義された、監視対象のユーザーとしてログインした電子メールクライアントまたは Microsoft Teams を開きます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-217">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="3be2f-218">監督ポリシーで定義した条件を満たすメールまたは Microsoft Teams のチャットを送信します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-218">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy.</span></span> <span data-ttu-id="3be2f-219">これには、キーワード、添付ファイルのサイズ、ドメインなどを指定できます。ポリシーに構成された条件設定が制限を超えているか、厳しすぎるかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3be2f-219">This can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy is too restrictive or too lenient.</span></span>

    > [!Note]
    > <span data-ttu-id="3be2f-220">定義されたポリシーの対象となるメールは、ほぼリアルタイムで処理され、ポリシーの構成後すぐにテストできます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-220">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured.</span></span> <span data-ttu-id="3be2f-221">Microsoft Teams でのチャットは、ポリシー内で完全に処理されるまでに最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3be2f-221">Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="3be2f-222">監督ポリシーに指定されたレビュー担当者として Office 365 テナントにログインします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-222">Log into your Office 365 tenant as a reviewer designated in the supervision policy.</span></span> <span data-ttu-id="3be2f-223">[*カスタムポリシー* > \*\*\*\* の**監視** > ] に移動して、ポリシーのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-223">Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

<span data-ttu-id="3be2f-224"><a name="UseOutlook"> </a></span><span class="sxs-lookup"><span data-stu-id="3be2f-224"></span></span>

## <a name="step-6---configure-outlook-for-reviewers-optional"></a><span data-ttu-id="3be2f-225">手順 6-レビュー担当者用に Outlook を構成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="3be2f-225">Step 6 - Configure Outlook for reviewers (optional)</span></span>

<span data-ttu-id="3be2f-226">Office 365 で監督ダッシュボードを使用しないで outlook を使用して通信を確認するには、outlook クライアントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be2f-226">Reviewers that want to use Outlook instead of using the Supervision dashboard in Office 365 to review communications must configure their Outlook client.</span></span>

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a><span data-ttu-id="3be2f-227">手順 1: 監督メールボックスのアドレスをコピーする</span><span class="sxs-lookup"><span data-stu-id="3be2f-227">Step 1: Copy the address for the supervision mailbox</span></span>

<span data-ttu-id="3be2f-228">outlook デスクトップまたは web 用の outlook のレビューを構成するには、監督ポリシーのセットアップの一部として作成された監督メールボックスのアドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="3be2f-228">To configure review for Outlook desktop or Outlook for the web, you'll need the address for the supervision mailbox that was created as part of the supervision policy setup.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3be2f-229">他のユーザーがポリシーを作成した場合は、そのポリシーからこのアドレスを取得してアドインをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be2f-229">If someone else created the policy, you'll need to get this address from them to install the add-in.</span></span>

 <span data-ttu-id="3be2f-230">**監督メールボックスのアドレスを検索するには**</span><span class="sxs-lookup"><span data-stu-id="3be2f-230">**To find the supervision mailbox address**</span></span>
  
1. <span data-ttu-id="3be2f-231">Office 365 組織の管理者アカウントの資格情報を使用して、 [ &amp;セキュリティコンプライアンスセンター](https://protection.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-231">Sign into the [Security &amp; Compliance Center](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="3be2f-232">[**監督**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-232">Go to **Supervision**.</span></span>

3. <span data-ttu-id="3be2f-233">確認する通信を収集する監督ポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-233">Click the supervision policy that's gathering the communications you want to review.</span></span>

4. <span data-ttu-id="3be2f-234">[ポリシーの詳細] ポップアップの [**監督メールボックス**] で、アドレスをコピーします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-234">In the policy details flyout, under **Supervision mailbox**, copy the address.</span></span><br/><span data-ttu-id="3be2f-235">![強調表示されている監督ポリシーの詳細ポップアップの [監督メールボックス] セクション](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span><span class="sxs-lookup"><span data-stu-id="3be2f-235">![The 'Supervision Mailbox' section of a supervision policy's details flyout showing the supervision mailbox address highlighted](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span></span>
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-access"></a><span data-ttu-id="3be2f-236">手順 2: Outlook アクセス用に監督メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="3be2f-236">Step 2: Configure the supervision mailbox for Outlook access</span></span>

<span data-ttu-id="3be2f-237">次に、レビューアーは、Outlook を監督メールボックスに接続できるように、Exchange Online の PowerShell コマンドをいくつか実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be2f-237">Next, reviewers will need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.</span></span>
  
1. <span data-ttu-id="3be2f-238">Exchange Online PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-238">Connect to Exchange Online PowerShell.</span></span> [<span data-ttu-id="3be2f-239">タスクの実行方法</span><span class="sxs-lookup"><span data-stu-id="3be2f-239">How do I do this?</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. <span data-ttu-id="3be2f-240">次のコマンドを実行し*ます。ここで、SupervisoryReview {GUID} @domain*は上記の手順1でコピーしたアドレスで、 *User*は、手順3で監督メールボックスに接続するレビュー担当者の名前になります。</span><span class="sxs-lookup"><span data-stu-id="3be2f-240">Run the following commands, where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will be connecting to the supervision mailbox in Step 3.</span></span>

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. <span data-ttu-id="3be2f-241">少なくとも1時間待ってから、手順3に進みます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-241">Wait at least an hour before moving on to Step 3 below.</span></span>

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a><span data-ttu-id="3be2f-242">手順 3: 監督メールボックスに接続するための Outlook プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="3be2f-242">Step 3: Create an Outlook profile to connect to the supervision mailbox</span></span>

<span data-ttu-id="3be2f-243">最後の手順では、監督者は、監督メールボックスに接続するための Outlook プロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be2f-243">For the final step, reviewers will need to create an Outlook profile to connect to the supervision mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="3be2f-244">新しい Outlook プロファイルを作成するには、Windows のコントロールパネルの [メール] 設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-244">To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel.</span></span> <span data-ttu-id="3be2f-245">これらの設定にアクセスするために必要なパスは、使用している windows オペレーティングシステム (windows 7、windows 8、または windows 10)、およびインストールされている Outlook のバージョンによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3be2f-245">The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using, and which version of Outlook is installed.</span></span>
  
1. <span data-ttu-id="3be2f-246">[コントロールパネル] を開き、ウィンドウ上部の [**検索**] ボックスに「 **Mail**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-246">Open the Control Panel, and in the **Search** box at the top of the window, type **Mail**.</span></span><br/><span data-ttu-id="3be2f-247">(コントロールパネルへのアクセス方法がわからない場合はどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="3be2f-247">(Not sure how to get to the Control Panel?</span></span> <span data-ttu-id="3be2f-248">[[コントロールパネルの場所] を](https://support.microsoft.com/help/13764/windows-where-is-control-panel)参照)</span><span class="sxs-lookup"><span data-stu-id="3be2f-248">See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span></span>
  
2. <span data-ttu-id="3be2f-249">**メール**アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-249">Open the **Mail** app.</span></span>

3. <span data-ttu-id="3be2f-250">[**メールの設定-Outlook**] で、[**プロファイルの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-250">In **Mail Setup - Outlook**, click **Show Profiles**.</span></span><br/><span data-ttu-id="3be2f-251">![[プロファイルの表示] ボタンが強調表示されている [メールの設定-Outlook] ダイアログボックス](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span><span class="sxs-lookup"><span data-stu-id="3be2f-251">![The 'Mail Setup - Outlook' dialog box with the 'Show Profiles' button highlighted](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span></span>
  
4. <span data-ttu-id="3be2f-252">[**メール**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-252">In **Mail**, click **Add**.</span></span> <span data-ttu-id="3be2f-253">次に、[**新しいプロファイル**] で、監督メールボックスの名前 (「**監督**」など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-253">Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).</span></span><br/><span data-ttu-id="3be2f-254">![[プロファイル名] ボックスに "監督" という名前が表示されている [新しいプロファイル] ダイアログ](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span><span class="sxs-lookup"><span data-stu-id="3be2f-254">![The 'New Profile' dialog showing the name 'Supervision' in the 'Profile Name' box](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span></span>
  
5. <span data-ttu-id="3be2f-255">[ **Outlook を Office 365 に接続**する] で、[**別のアカウントに接続する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-255">In **Connect Outlook to Office 365**, click **Connect to a different account**.</span></span><br/><span data-ttu-id="3be2f-256">![[別のアカウントへの接続] リンクが強調表示されている [Outlook から Office への接続 365] メッセージ](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span><span class="sxs-lookup"><span data-stu-id="3be2f-256">![The 'Connect Outlook to Office 365' message with the 'Connect to a different account' link highlighted](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span></span>
  
6. <span data-ttu-id="3be2f-257">[**自動アカウントセットアップ**] で、[**手動セットアップ] または [サーバーの種類の追加**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3be2f-257">In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.</span></span>

7. <span data-ttu-id="3be2f-258">[**アカウントの種類を選択して**ください] で、[ **Office 365**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-258">In **Choose Your Account Type**, choose **Office 365**.</span></span> <span data-ttu-id="3be2f-259">その後、[**電子メールアドレス**] ボックスに、先ほどコピーした監督メールボックスのアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-259">Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously.</span></span><br/><span data-ttu-id="3be2f-260">![Outlook の [アカウントの種類の追加] ページで、[メールアドレス] ボックスが強調表示されています。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span><span class="sxs-lookup"><span data-stu-id="3be2f-260">![The 'Choose Your Account Type' page of the 'Add Account' dialog in Outlook showing the 'Email Address' box highlighted.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span></span>
  
8. <span data-ttu-id="3be2f-261">メッセージが表示されたら、Office 365 資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="3be2f-261">When prompted, enter your Office 365 credentials.</span></span>

9. <span data-ttu-id="3be2f-262">成功した場合、Outlook のフォルダー一覧ビューに、 \*\* \<監督ポリシー名\> \*\*フォルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-262">If successful, you'll see the **Supervision - \<policy name\>** folder listed in the Folder List view in Outlook.</span></span>

## <a name="powershell-reference"></a><span data-ttu-id="3be2f-263">PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="3be2f-263">PowerShell reference</span></span>

<span data-ttu-id="3be2f-264">必要に応じて、次の PowerShell コマンドレットを使用して、監督ポリシーを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="3be2f-264">If needed, you can create and manage supervision policies using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="3be2f-265">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="3be2f-265">New-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="3be2f-266">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="3be2f-266">Get-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="3be2f-267">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="3be2f-267">Set-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="3be2f-268">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="3be2f-268">Remove-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="3be2f-269">SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="3be2f-269">New-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="3be2f-270">SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="3be2f-270">Set-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="3be2f-271">SupervisoryReviewActivity</span><span class="sxs-lookup"><span data-stu-id="3be2f-271">Get-SupervisoryReviewActivity</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [<span data-ttu-id="3be2f-272">SupervisoryReviewOverallProgressReport</span><span class="sxs-lookup"><span data-stu-id="3be2f-272">Get-SupervisoryReviewOverallProgressReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [<span data-ttu-id="3be2f-273">SupervisoryReviewTopCasesReport</span><span class="sxs-lookup"><span data-stu-id="3be2f-273">Get-SupervisoryReviewTopCasesReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)