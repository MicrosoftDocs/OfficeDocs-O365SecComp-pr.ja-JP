---
title: Microsoft 365 コンプライアンスセンターの新機能
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Microsoft 365 コンプライアンスセンターに新機能を継続的に追加し、学習した問題を修正し、フィードバックに基づいて変更を加えています。 今月の内容を確認してください。
ms.openlocfilehash: c5abb71c21e6c65d46768d584101f6902c0422c2
ms.sourcegitcommit: 30fc793d3e77e223dee6c96a94e50cda2de34bb6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "37011719"
---
# <a name="whats-new-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="bddb4-104">Microsoft 365 コンプライアンスセンターの新機能</span><span class="sxs-lookup"><span data-stu-id="bddb4-104">What's new in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="bddb4-105">[Microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md)に新機能を継続的に追加し、学習した問題を修正し、フィードバックに基づいて変更を加えています。</span><span class="sxs-lookup"><span data-stu-id="bddb4-105">We're continuously adding new features to the [Microsoft 365 compliance center](microsoft-365-compliance-center.md), fixing issues we learn about, and making changes based on your feedback.</span></span> <span data-ttu-id="bddb4-106">お客様が現在利用できるものを確認するには、次のようにしてください。</span><span class="sxs-lookup"><span data-stu-id="bddb4-106">Take a look below to see what's available for you today.</span></span> <span data-ttu-id="bddb4-107">一部の機能は、お客様のさまざまなスピードでロールアウトされます。</span><span class="sxs-lookup"><span data-stu-id="bddb4-107">Some features get rolled out at different speeds to our customers.</span></span> <span data-ttu-id="bddb4-108">機能がまだ表示されていない場合は、[対象のリリース](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)に追加してみてください。</span><span class="sxs-lookup"><span data-stu-id="bddb4-108">If you aren't seeing a feature yet, try adding yourself to [targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365).</span></span>

> [!TIP]
> <span data-ttu-id="bddb4-109">他の管理センターでは何が起こっているのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="bddb4-109">Interested in what's going on in other admin centers?</span></span> <span data-ttu-id="bddb4-110">次の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bddb4-110">Check out these articles:</span></span><br>[<span data-ttu-id="bddb4-111">Microsoft 365 管理センターの新機能</span><span class="sxs-lookup"><span data-stu-id="bddb4-111">What's new in the Microsoft 365 admin center</span></span>](https://docs.microsoft.com/office365/admin/whats-new-in-preview?view=o365-worldwide)<br>[<span data-ttu-id="bddb4-112">SharePoint 管理センターの新機能</span><span class="sxs-lookup"><span data-stu-id="bddb4-112">What's new in the SharePoint admin center</span></span>](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)

## <a name="august-2019"></a><span data-ttu-id="bddb4-113">2019年8月</span><span class="sxs-lookup"><span data-stu-id="bddb4-113">August 2019</span></span>

<span data-ttu-id="bddb4-114">今月リリースのリリース前に静かになる理由をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="bddb4-114">Wondering why it's quiet on the release front this month?</span></span> <span data-ttu-id="bddb4-115">マイクロソフトは、11月に[Microsoft Ignite](https://www.microsoft.com/ignite)で最近される新しい革新的なコンプライアンスソリューションの構築に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="bddb4-115">We're heads down building new, innovative compliance solutions that'll be unveiled at [Microsoft Ignite](https://www.microsoft.com/ignite) in November.</span></span> <span data-ttu-id="bddb4-116">引き続きご調整ください。</span><span class="sxs-lookup"><span data-stu-id="bddb4-116">Stay tuned!</span></span>

### <a name="data-investigations"></a><span data-ttu-id="bddb4-117">データ調査</span><span class="sxs-lookup"><span data-stu-id="bddb4-117">Data investigations</span></span>

<span data-ttu-id="bddb4-118">データの調査を実行すると、元の場所からアイテムを削除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bddb4-118">When performing a data investigation, you can now delete items from their original locations.</span></span> <span data-ttu-id="bddb4-119">これは、組織全体の Exchange メールボックス、SharePoint サイト、および OneDrive アカウントからアイテムを削除できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bddb4-119">This means you can delete items from Exchange mailboxes, SharePoint sites, and OneDrive accounts across your organization.</span></span> <span data-ttu-id="bddb4-120">アイテムを証拠として収集したため、証拠セットに保存されたアイテムのコピーが、さらに参考になるか、参照として保持することができます。</span><span class="sxs-lookup"><span data-stu-id="bddb4-120">Because you collected the items as evidence, you’ll have copies of them retained in the evidence set to you can investigate further or just keep as a reference.</span></span> [<span data-ttu-id="bddb4-121">詳細情報</span><span class="sxs-lookup"><span data-stu-id="bddb4-121">Learn more</span></span>](datainvestigations/delete-items-from-original-locations.md)

## <a name="july-2019"></a><span data-ttu-id="bddb4-122">2019年7月</span><span class="sxs-lookup"><span data-stu-id="bddb4-122">July 2019</span></span>

### <a name="new-admin-roles"></a><span data-ttu-id="bddb4-123">新しい管理者の役割</span><span class="sxs-lookup"><span data-stu-id="bddb4-123">New admin roles</span></span>

<span data-ttu-id="bddb4-124">組織のセキュリティとコンプライアンスを管理するために、2つの新しい管理者の役割をリリースしました。すべての友人に連絡します。</span><span class="sxs-lookup"><span data-stu-id="bddb4-124">We released two new admin roles to help manage security and compliance in your org. Tell all your friends.</span></span>

- <span data-ttu-id="bddb4-125">**コンプライアンスデータ管理者**。この役割を持つユーザーは、Microsoft 365 コンプライアンスセンター、Microsoft 365 管理センター、および Azure のデータを保護および追跡するためのアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="bddb4-125">**Compliance data admin**. Users with this role have permissions to protect and track data in the Microsoft 365 compliance center, Microsoft 365 admin center, and Azure.</span></span> <span data-ttu-id="bddb4-126">また、Exchange 管理センター、コンプライアンスマネージャー、Teams & Skype for Business 管理センターを管理したり、Azure および Microsoft 365 のサポートチケットを作成したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bddb4-126">They can also manage everything the Exchange admin center, Compliance Manager, Teams & Skype for Business admin center and create support tickets for Azure and Microsoft 365.</span></span>
- <span data-ttu-id="bddb4-127">**セキュリティオペレーター**。</span><span class="sxs-lookup"><span data-stu-id="bddb4-127">**Security operator**.</span></span> <span data-ttu-id="bddb4-128">この役割を持つユーザーは、通知を管理し、Microsoft 365 セキュリティセンター、Azure Active Directory、Id 保護、特権 Id 管理、Office 365 のすべてを含む、セキュリティ関連機能へのグローバルな読み取り専用アクセスを行うことができます。セキュリティ & コンプライアンスセンター。</span><span class="sxs-lookup"><span data-stu-id="bddb4-128">Users with this role can manage alerts and have global read-only access to security-related features, including everything in the Microsoft 365 security center, Azure Active Directory, Identity Protection, Privileged Identity Management and Office 365 Security & Compliance Center.</span></span>

[<span data-ttu-id="bddb4-129">これらの役割の詳細情報</span><span class="sxs-lookup"><span data-stu-id="bddb4-129">Learn more about these roles</span></span>](https://docs.microsoft.com/office365/securitycompliance/permissions-microsoft-365-compliance-security)

### <a name="search-and-filtering-for-reports"></a><span data-ttu-id="bddb4-130">レポートの検索とフィルター処理</span><span class="sxs-lookup"><span data-stu-id="bddb4-130">Search and filtering for reports</span></span>

<span data-ttu-id="bddb4-131">必要なレポートを見つけるために、大量のレポートをスクロールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bddb4-131">No more scrolling through a sea of reports to find the ones you want.</span></span> <span data-ttu-id="bddb4-132">これで、(タイトルに基づいて) レポートを検索し、「ラベル」や「コンプライアンス」、「Office 365」や「Microsoft Cloud App Security」などのソースのカテゴリにフィルターを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="bddb4-132">You can now search for reports (based on their titles) and filter on categories like ‘Labels’ and ‘Compliance’ and sources like ‘Office 365’ and 'Microsoft Cloud App Security’.</span></span>

![適用されたフィルターを使用したレポートの検索とフィルターのボタンの画面キャプチャ](media/mcc_report_filtering.png)

### <a name="help-content"></a><span data-ttu-id="bddb4-134">ヘルプコンテンツ</span><span class="sxs-lookup"><span data-stu-id="bddb4-134">Help content</span></span>

<span data-ttu-id="bddb4-135">椅子を引き上げ、コーヒーをつかんで、最新のコンプライアンスに関するドキュメントをすぐに使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="bddb4-135">Pull up a chair, grab a cup of coffee, and let our latest compliance docs sweep you away.</span></span>

<span data-ttu-id="bddb4-136">**Advanced eDiscovery**</span><span class="sxs-lookup"><span data-stu-id="bddb4-136">**Advanced eDiscovery**</span></span>
- <span data-ttu-id="bddb4-137">[高度な電子情報開示で会話を確認](compliance20/conversation-review-sets.md)する新規</span><span class="sxs-lookup"><span data-stu-id="bddb4-137">[Review conversations in Advanced eDiscovery](compliance20/conversation-review-sets.md) (New)</span></span>
- [<span data-ttu-id="bddb4-138">Advanced eDiscovery での AzCopy のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bddb4-138">Troubleshoot AzCopy in Advanced eDiscovery</span></span>](compliance20/troubleshooting-azcopy.md)
- [<span data-ttu-id="bddb4-139">レビュー セットに Office 365 以外のデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="bddb4-139">Load non-Office 365 data into a review set</span></span>](compliance20/load-non-office365-data.md)
- [<span data-ttu-id="bddb4-140">データ処理中のエラー修復</span><span class="sxs-lookup"><span data-stu-id="bddb4-140">Error remediation when processing data</span></span>](compliance20/error-remediation.md)

<span data-ttu-id="bddb4-141">**サードパーティのデータをアーカイブする**</span><span class="sxs-lookup"><span data-stu-id="bddb4-141">**Archiving 3rd-party data**</span></span>
- [<span data-ttu-id="bddb4-142">Office 365 でインスタント Bloomberg データをアーカイブするためのコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="bddb4-142">Set up a connector to archive Instant Bloomberg data in Office 365</span></span>](archive-instant-bloomberg-data.md)

<span data-ttu-id="bddb4-143">**監査**</span><span class="sxs-lookup"><span data-stu-id="bddb4-143">**Auditing**</span></span>
- [<span data-ttu-id="bddb4-144">共有を監査して外部ユーザーと共有されているリソースを見つける</span><span class="sxs-lookup"><span data-stu-id="bddb4-144">Use sharing auditing in the Office 365 audit log</span></span>](use-sharing-auditing.md)
- [<span data-ttu-id="bddb4-145">Office 365 管理アクティビティ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="bddb4-145">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)
- [<span data-ttu-id="bddb4-146">Office 365 管理アクティビティ API のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bddb4-146">Troubleshooting the Office 365 Management Activity API</span></span>](https://docs.microsoft.com/office/office-365-management-api/troubleshooting-the-office-365-management-activity-api)
- [<span data-ttu-id="bddb4-147">セキュリティ & コンプライアンスセンターで監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="bddb4-147">Search the audit log in the Security & Compliance Center</span></span>](search-the-audit-log-in-security-and-compliance.md)

<span data-ttu-id="bddb4-148">**暗号化**</span><span class="sxs-lookup"><span data-stu-id="bddb4-148">**Encryption**</span></span>
- [<span data-ttu-id="bddb4-149">Office 365 Message Encryption の旧来の情報</span><span class="sxs-lookup"><span data-stu-id="bddb4-149">Legacy information for Office 365 Message Encryption</span></span>](legacy-information-for-message-encryption.md)

<span data-ttu-id="bddb4-150">**部門**</span><span class="sxs-lookup"><span data-stu-id="bddb4-150">**Classification**</span></span>
- [<span data-ttu-id="bddb4-151">正確なデータ一致に基づく分類を使用してカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="bddb4-151">Create custom sensitive information types with Exact Data Match based classification</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

<span data-ttu-id="bddb4-152">**データガバナンス**</span><span class="sxs-lookup"><span data-stu-id="bddb4-152">**Data governance**</span></span>
- [<span data-ttu-id="bddb4-153">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="bddb4-153">Overview of retention policies</span></span>](retention-policies.md)

<span data-ttu-id="bddb4-154">**マネージ**</span><span class="sxs-lookup"><span data-stu-id="bddb4-154">**Supervision**</span></span>
- [<span data-ttu-id="bddb4-155">Office 365 の監督ポリシー</span><span class="sxs-lookup"><span data-stu-id="bddb4-155">Supervision policies in Office 365</span></span>](supervision-policies.md)