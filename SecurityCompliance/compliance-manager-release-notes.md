---
title: Microsoft コンプライアンスマネージャーリリースノート
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
ms.openlocfilehash: f01e70b7852e6421c7c77dbe5ed4b6ca2aa395b2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152069"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="3fdde-104">コンプライアンスマネージャーのリリースノート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="3fdde-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="3fdde-105">コンプライアンスマネージャーの公開プレビューでは、今後の機能と更新プログラムに早期にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3fdde-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="3fdde-106">[Service Trust Portal](https://servicetrust.microsoft.com)の更新された[コンプライアンスマネージャー](https://servicetrust.microsoft.com/ComplianceManager)ツールを使用して、Microsoft クラウドサービスに関連する規制コンプライアンスアクティビティを追跡、割り当て、検証することができます。</span><span class="sxs-lookup"><span data-stu-id="3fdde-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="3fdde-107">コンプライアンスマネージャーの新機能 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="3fdde-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="3fdde-108">**Microsoft のセキュリティで保護されたスコアとの統合:** コンプライアンスマネージャーは、カスタマーが管理するアクションを50以上のセキュリティで保護されたスコアアクションにマッピングすることで、 [Microsoft のセキュリティスコア](microsoft-secure-score.md)との統合をサポートします。</span><span class="sxs-lookup"><span data-stu-id="3fdde-108">**Integration with Microsoft Secure Score:** Compliance Manager supports integration with [Microsoft Secure Score](microsoft-secure-score.md) by mapping customer-managed Actions to more than 50 Secure Score actions.</span></span> <span data-ttu-id="3fdde-109">[Secure Score] でマップされたアクションを完了すると、対応するコンプライアンスマネージャーアクションが自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="3fdde-109">When you complete a mapped action in Secure Score, the corresponding Compliance Manager Action automatically updates.</span></span>

- <span data-ttu-id="3fdde-110">**カスタム評価のインポート:** 組み込みの評価に加えて、コンプライアンスマネージャーはカスタムテンプレートのインポートをサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="3fdde-110">**Import custom Assessments:** In addition to built-in Assessments, Compliance Manager now supports importing custom Templates.</span></span> <span data-ttu-id="3fdde-111">任意の製品またはサービスおよび標準または規制のカスタム評価を作成できます。</span><span class="sxs-lookup"><span data-stu-id="3fdde-111">You can create custom Assessments for any product or service and any standard or regulation.</span></span>

- <span data-ttu-id="3fdde-112">**アクションアイテム:** アクションアイテムは現在、個別のアイテムで、多くの Microsoft Secure Score Graph API からのテレメトリコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3fdde-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="3fdde-113">可能であれば、技術的なアクションの推奨事項が Office 365 サービスの該当する構成ページへのリンクを持つようになります。</span><span class="sxs-lookup"><span data-stu-id="3fdde-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="3fdde-114">**テナント管理:** コンプライアンスマネージャー (プレビュー) で新しいデータ要素を管理するための新しいインターフェイス:</span><span class="sxs-lookup"><span data-stu-id="3fdde-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="3fdde-115">**次元:** テンプレート、評価、およびアクションアイテムのメタデータを表示、追加、およびカスタマイズして、フィルターのカスタムピボットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3fdde-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="3fdde-116">**所有者:** 各アクションアイテムの所有者を指定します。</span><span class="sxs-lookup"><span data-stu-id="3fdde-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="3fdde-117">**お客様のアクション:** コンプライアンスマネージャー (プレビュー) に含まれるアクションアイテムの完全なリストを管理し、セキュリティで保護されたスコアと統合されたアクションアイテムのセキュリティで保護されたスコア監視を有効/無効にします。</span><span class="sxs-lookup"><span data-stu-id="3fdde-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

- <span data-ttu-id="3fdde-118">**更新されたコンプライアンススコア**: 手法は、Microsoft セキュリティスコアとの同期をサポートするように変更されました。</span><span class="sxs-lookup"><span data-stu-id="3fdde-118">**Updated Compliance Score**: The methodology has changed to support syncing with Microsoft Secure Score.</span></span> <span data-ttu-id="3fdde-119">スコアリングシステムは、Microsoft が管理する統制クレジットを削除し、お客様が管理する統制の完了のみに焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="3fdde-119">The scoring system removes the Microsoft-managed control credits and focuses solely on the completion of customer-managed controls.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="3fdde-120">コンプライアンスマネージャーの既知の問題 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="3fdde-120">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="3fdde-121">次のセクションでは、コンプライアンスマネージャーの今後のリリースで解決される既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="3fdde-121">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="3fdde-122">コンプライアンススコア</span><span class="sxs-lookup"><span data-stu-id="3fdde-122">Compliance Score</span></span>

- <span data-ttu-id="3fdde-123">**スコープ内にない**とマークされたアクションアイテムの場合、アクションアイテムに割り当てられているスコアは、コンプライアンススコアの計算から除外されません。</span><span class="sxs-lookup"><span data-stu-id="3fdde-123">For Action Items marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the Compliance Score calculation.</span></span> <span data-ttu-id="3fdde-124">**スコープにない**アクションアイテムは、コンプライアンススコアを増加しません。</span><span class="sxs-lookup"><span data-stu-id="3fdde-124">Action Items marked **Not in Scope** do not increase your Compliance Score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="3fdde-125">セキュリティ スコア</span><span class="sxs-lookup"><span data-stu-id="3fdde-125">Secure Score</span></span>

- <span data-ttu-id="3fdde-126">セキュリティで保護されたスコアの結果は、一部の Microsoft 365 および Office 365 サブスクリプションの一部のアクションアイテムでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="3fdde-126">Secure Score results are not available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="3fdde-127">このような場合、セキュリティで保護されたスコアの結果は「検出できません」です。</span><span class="sxs-lookup"><span data-stu-id="3fdde-127">The Secure Score result is 'Could not be detected' in these cases.</span></span>
- <span data-ttu-id="3fdde-128">セキュリティで保護されたスコアの結果が、対応するポリシーおよび完了していないアクションアイテムに対して返されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3fdde-128">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="3fdde-129">Microsoft 管理コントロール</span><span class="sxs-lookup"><span data-stu-id="3fdde-129">Microsoft-managed Controls</span></span>

- <span data-ttu-id="3fdde-130">Microsoft 管理コントロールのテスト日は、評価に含まれていても UI には表示されません。</span><span class="sxs-lookup"><span data-stu-id="3fdde-130">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="3fdde-131">テスト日付情報を表示するには、評価をエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fdde-131">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="3fdde-132">カスタマイズ</span><span class="sxs-lookup"><span data-stu-id="3fdde-132">Customization</span></span>

- <span data-ttu-id="3fdde-133">カスタムコントロールを追加することで、新しいコントロールを既存のコントロールファミリに追加することはできますが、新しいコントロールファミリを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="3fdde-133">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="3fdde-134">このリリースでは、アクションアイテムのリンクや、アクションアイテムまたはコントロールの評価への追加はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3fdde-134">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="3fdde-135">カスタムアクションを作成した場合、それを編集または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="3fdde-135">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="3fdde-136">評価に表示されていないコントロールファミリ</span><span class="sxs-lookup"><span data-stu-id="3fdde-136">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="3fdde-137">テンプレートをインポートすると、そのテンプレートに基づくすべての評価に、テンプレートの一部であるすべてのコントロールファミリが反映されます。</span><span class="sxs-lookup"><span data-stu-id="3fdde-137">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="3fdde-138">ただし、新しいコントロールファミリをテンプレートに追加した場合、既存の評価には変更が反映されません。</span><span class="sxs-lookup"><span data-stu-id="3fdde-138">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="3fdde-139">更新されたテンプレートから作成された新しい評価のみが変更を反映しています。</span><span class="sxs-lookup"><span data-stu-id="3fdde-139">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="filters"></a><span data-ttu-id="3fdde-140">フィルター</span><span class="sxs-lookup"><span data-stu-id="3fdde-140">Filters</span></span>

- <span data-ttu-id="3fdde-141">アクションアイテムまたはコントロールに対するフィルター処理によって、一貫して正しい結果が得られない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3fdde-141">Filtering on Action Items or Controls does not consistently produce correct results.</span></span>

### <a name="templates"></a><span data-ttu-id="3fdde-142">テンプレート</span><span class="sxs-lookup"><span data-stu-id="3fdde-142">Templates</span></span>

- <span data-ttu-id="3fdde-143">アーカイブされたテンプレートは編集可能で、編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="3fdde-143">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="3fdde-144">ロックされたテンプレートは、評価を行うべきではない場合に、評価の作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3fdde-144">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="3fdde-145">テンプレートのロックは、評価の作成に使用されないようにすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="3fdde-145">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="3fdde-146">エクスポート</span><span class="sxs-lookup"><span data-stu-id="3fdde-146">Export</span></span>

- <span data-ttu-id="3fdde-147">テンプレートの状態が [**インポート**済みまたは**保留中の承認**] に設定されている場合、JSON へのテンプレートのエクスポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="3fdde-147">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="3fdde-148">サポート対象ブラウザー</span><span class="sxs-lookup"><span data-stu-id="3fdde-148">Supported browsers</span></span>

- <span data-ttu-id="3fdde-149">Microsoft Edge、Chrome、および Safari の最新バージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3fdde-149">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="3fdde-150">ブラウザーが更新されるまで、更新されたデータが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3fdde-150">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="3fdde-151">Microsoft Edge のプレビューバージョンはサポートされていませんが、既知の問題はありません。</span><span class="sxs-lookup"><span data-stu-id="3fdde-151">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="3fdde-152">Internet Explorer はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3fdde-152">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="3fdde-153">セッションのタイムアウト</span><span class="sxs-lookup"><span data-stu-id="3fdde-153">Session timeout</span></span>

- <span data-ttu-id="3fdde-154">セッションがタイムアウトになると、"問題が発生しました" というエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3fdde-154">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="3fdde-155">解決するには、[[コンプライアンスマネージャー](https://servicetrust.microsoft.com/ComplianceManager) ] に移動して、再度ログインします。</span><span class="sxs-lookup"><span data-stu-id="3fdde-155">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="3fdde-156">言語サポート</span><span class="sxs-lookup"><span data-stu-id="3fdde-156">Language support</span></span>

- <span data-ttu-id="3fdde-157">すべての web ページですべての言語がサポートされているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="3fdde-157">All languages are not supported for all webpages.</span></span> <span data-ttu-id="3fdde-158">ローカル言語がサポートされていない場合は、英語 (米国) で表示されます。</span><span class="sxs-lookup"><span data-stu-id="3fdde-158">If your local language is unsupported, view in US English.</span></span>