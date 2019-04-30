---
title: Microsoft コンプライアンスマネージャーリリースノート
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: microsoft コンプライアンスマネージャーは、microsoft Service Trust Portal の無料のワークフローベースのリスク評価ツールです。 コンプライアンスマネージャーを使用すると、Microsoft クラウドサービスに関連する規制コンプライアンスアクティビティを追跡、割り当て、検証することができます。
ms.openlocfilehash: 5e18445e3f9ad2848f18174788ec6dd40bc4a178
ms.sourcegitcommit: 696c1ed6b270be3f9da7395b49a7d8fec98e6db0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2019
ms.locfileid: "33473142"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="d3106-104">コンプライアンスマネージャーのリリースノート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d3106-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="d3106-105">コンプライアンスマネージャーの公開プレビューでは、今後の機能と更新プログラムに早期にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d3106-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="d3106-106">[Service Trust Portal](https://servicetrust.microsoft.com)の更新された[コンプライアンスマネージャー](https://servicetrust.microsoft.com/ComplianceManager)ツールを使用して、Microsoft クラウドサービスに関連する規制コンプライアンスアクティビティを追跡、割り当て、検証することができます。</span><span class="sxs-lookup"><span data-stu-id="d3106-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="d3106-107">コンプライアンスマネージャーの新機能 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d3106-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="d3106-108">**Microsoft のセキュリティで保護されたスコアとの統合:** コンプライアンスマネージャーは、カスタマーが管理するアクションを50以上のセキュリティで保護されたスコアアクションにマッピングすることで、 [Microsoft のセキュリティスコア](microsoft-secure-score.md)との統合をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d3106-108">**Integration with Microsoft Secure Score:** Compliance Manager supports integration with [Microsoft Secure Score](microsoft-secure-score.md) by mapping customer-managed Actions to more than 50 Secure Score actions.</span></span> <span data-ttu-id="d3106-109">[Secure Score] でマップされたアクションを完了すると、対応するコンプライアンスマネージャーアクションが自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="d3106-109">When you complete a mapped action in Secure Score, the corresponding Compliance Manager Action is automatically updated.</span></span>

- <span data-ttu-id="d3106-110">**カスタム評価のインポート:** 組み込みの評価に加えて、コンプライアンスマネージャーはカスタムテンプレートのインポートをサポートするようになったため、製品またはサービスおよび標準または規制のカスタム評価を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d3106-110">**Import custom Assessments:** In addition to built-in Assessments, Compliance Manager now supports importing custom Templates, enabling you to create custom Assessments for any product or service and any standard or regulation.</span></span>

- <span data-ttu-id="d3106-111">**アクションアイテム:** アクションアイテムは現在、個別のアイテムで、多くの Microsoft Secure Score Graph API からのテレメトリコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3106-111">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="d3106-112">可能であれば、技術的なアクションの推奨事項が Office 365 サービスの該当する構成ページへのリンクを持つようになります。</span><span class="sxs-lookup"><span data-stu-id="d3106-112">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="d3106-113">**テナント管理:** コンプライアンスマネージャー (プレビュー) で新しいデータ要素を管理するための新しいインターフェイス:</span><span class="sxs-lookup"><span data-stu-id="d3106-113">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="d3106-114">**次元:** テンプレート、評価、およびアクションアイテムのメタデータを表示、追加、およびカスタマイズして、フィルターのカスタムピボットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d3106-114">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="d3106-115">**所有者:** 各アクションアイテムの所有者を指定します。</span><span class="sxs-lookup"><span data-stu-id="d3106-115">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="d3106-116">**お客様のアクション:** コンプライアンスマネージャー (プレビュー) に含まれるアクションアイテムの完全なリストを管理し、セキュリティで保護されたスコアと統合されたアクションアイテムのセキュリティで保護されたスコア監視を有効/無効にします。</span><span class="sxs-lookup"><span data-stu-id="d3106-116">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items that are integrated with Secure Score.</span></span>

- <span data-ttu-id="d3106-117">**更新されたコンプライアンススコア**: 手法は、Microsoft セキュリティスコアとの同期をサポートするように変更されました。</span><span class="sxs-lookup"><span data-stu-id="d3106-117">**Updated Compliance Score**: The methodology has changed to support syncing with Microsoft Secure Score.</span></span> <span data-ttu-id="d3106-118">スコアリングシステムは、Microsoft が管理する統制クレジットを削除し、お客様が管理する統制の完了のみに焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="d3106-118">The scoring system removes the Microsoft-managed control credits and focuses solely on the completion of customer-managed controls.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="d3106-119">コンプライアンスマネージャーの既知の問題 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d3106-119">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="d3106-120">次のセクションでは、コンプライアンスマネージャーの今後のリリースで解決される既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3106-120">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="d3106-121">コンプライアンススコア</span><span class="sxs-lookup"><span data-stu-id="d3106-121">Compliance Score</span></span>

- <span data-ttu-id="d3106-122">アクションアイテムが**スコープ内にない**とマークされている場合、そのアクションアイテムに割り当てられているスコアは、コンプライアンススコアの計算から除外されません。</span><span class="sxs-lookup"><span data-stu-id="d3106-122">When Action Items are marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the Compliance Score calculation.</span></span> <span data-ttu-id="d3106-123">**スコープにない**アクションアイテムは、コンプライアンススコアを増やさないでください。</span><span class="sxs-lookup"><span data-stu-id="d3106-123">Action Items marked **Not in Scope** should not increase your Compliance Score.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="d3106-124">Microsoft 管理コントロール</span><span class="sxs-lookup"><span data-stu-id="d3106-124">Microsoft-managed Controls</span></span>

- <span data-ttu-id="d3106-125">Microsoft 管理コントロールのテスト日は、評価に含まれていても UI には表示されません。</span><span class="sxs-lookup"><span data-stu-id="d3106-125">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="d3106-126">テスト日付情報を表示するには、評価をエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3106-126">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="d3106-127">カスタマイズ</span><span class="sxs-lookup"><span data-stu-id="d3106-127">Customization</span></span>

- <span data-ttu-id="d3106-128">カスタムコントロールを追加することで、新しいコントロールを既存のコントロールファミリに追加することはできますが、新しいコントロールファミリを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="d3106-128">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="d3106-129">このリリースでは、アクションアイテムのリンクや、アクションアイテムまたはコントロールの評価への追加はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d3106-129">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="d3106-130">カスタムアクションを作成した場合、それを編集または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="d3106-130">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="d3106-131">評価に表示されていないコントロールファミリ</span><span class="sxs-lookup"><span data-stu-id="d3106-131">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="d3106-132">テンプレートをインポートすると、そのテンプレートに基づくすべての評価に、テンプレートの一部であるすべてのコントロールファミリが反映されます。</span><span class="sxs-lookup"><span data-stu-id="d3106-132">When you import a Template, all Assessments based on that Template will reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="d3106-133">ただし、新しいコントロールファミリをテンプレートに追加した場合、既存の評価には変更が反映されません。</span><span class="sxs-lookup"><span data-stu-id="d3106-133">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="d3106-134">更新されたテンプレートから作成された新しい評価のみが変更を反映します。</span><span class="sxs-lookup"><span data-stu-id="d3106-134">Only new Assessments created off the updated Template will reflect the changes.</span></span>

### <a name="filters"></a><span data-ttu-id="d3106-135">フィルター</span><span class="sxs-lookup"><span data-stu-id="d3106-135">Filters</span></span>

- <span data-ttu-id="d3106-136">アクションアイテムまたはコントロールに対するフィルター処理によって、一貫して正しい結果が得られない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d3106-136">Filtering on Action Items or Controls does not consistently produce correct results.</span></span>

### <a name="templates"></a><span data-ttu-id="d3106-137">テンプレート</span><span class="sxs-lookup"><span data-stu-id="d3106-137">Templates</span></span>

- <span data-ttu-id="d3106-138">アーカイブされたテンプレートは編集可能で、編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="d3106-138">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="d3106-139">ロックされたテンプレートは、評価を行うべきではない場合に、評価の作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d3106-139">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="d3106-140">テンプレートのロックは、評価の作成に使用されないようにすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="d3106-140">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="d3106-141">エクスポート</span><span class="sxs-lookup"><span data-stu-id="d3106-141">Export</span></span>

- <span data-ttu-id="d3106-142">テンプレートの状態が [**インポート**済みまたは**保留中の承認**] に設定されている場合、JSON へのテンプレートのエクスポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="d3106-142">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="d3106-143">サポート対象ブラウザー</span><span class="sxs-lookup"><span data-stu-id="d3106-143">Supported browsers</span></span>

- <span data-ttu-id="d3106-144">Microsoft Edge、Chrome、および Safari の最新バージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d3106-144">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="d3106-145">ブラウザーが更新されるまで、更新されたデータが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d3106-145">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="d3106-146">Microsoft Edge のプレビューバージョンはサポートされていませんが、既知の問題はありません。</span><span class="sxs-lookup"><span data-stu-id="d3106-146">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="d3106-147">Internet Explorer はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d3106-147">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="d3106-148">セッションのタイムアウト</span><span class="sxs-lookup"><span data-stu-id="d3106-148">Session timeout</span></span>

- <span data-ttu-id="d3106-149">セッションがタイムアウトになると、"問題が発生しました" というエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d3106-149">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="d3106-150">解決するには、[[コンプライアンスマネージャー](https://servicetrust.microsoft.com/ComplianceManager) ] に移動して、再度ログインします。</span><span class="sxs-lookup"><span data-stu-id="d3106-150">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>