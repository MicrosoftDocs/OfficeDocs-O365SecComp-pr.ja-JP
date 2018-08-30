---
title: Office 365 のデータ管理を管理します。
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 5/9/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 48064107-fed2-4db0-9e5c-aa5ddd5ccb09
description: データ ・ ガバナンスが必要なときにデータの管理と取得に関するすべてを削除しないとき。Office 365 のデータ ・ ガバナンスからインポートして保持し、最後にコンテンツを完全に削除するポリシーを作成するのには、最初にデータを格納する、完全なコンテンツのライフ サイクルを管理できます。
ms.openlocfilehash: ca3443c3b90a067bf171ddf89be604d262a7b9a4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532667"
---
# <a name="manage-data-governance-in-office-365"></a><span data-ttu-id="effcd-104">Office 365 のデータ管理を管理します。</span><span class="sxs-lookup"><span data-stu-id="effcd-104">Manage data governance in Office 365</span></span>

<span data-ttu-id="effcd-p102">データ ・ ガバナンスが必要なときにデータの管理と取得に関するすべてを削除しないとき。Office 365 のデータ ・ ガバナンスからインポートして保持し、最後にコンテンツを完全に削除するポリシーを作成するのには、最初にデータを格納する、完全なコンテンツのライフ サイクルを管理できます。</span><span class="sxs-lookup"><span data-stu-id="effcd-p102">Data governance is all about keeping your data around when you need it and getting rid of it when you don't. With data governance in Office 365, you can manage the full content lifecycle, from importing and storing data at the beginning, to creating policies that retain and then permanently delete content at the end.</span></span>
  
## <a name="import"></a><span data-ttu-id="effcd-107">インポート</span><span class="sxs-lookup"><span data-stu-id="effcd-107">Import</span></span>

<span data-ttu-id="effcd-p103">クラウド、オンプレミスのサーバーと同様に、またはサード ・ パーティ製のアプリケーションでの外部の場所でいくつかのデータの格納されている可能性があります。インポート サービスでは、メッセージ、SharePoint、および OneDrive のビジネス データをネットワーク経由で直接アップロードすることに暗号化されたドライブを出荷するか、Office 365 に簡単です。インテリジェントなインポート機能を使用サービスのインポートの対象のメールボックスに実際にインポートを取得する PST ファイル内のアイテムをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="effcd-p103">Some of your data might be stored in places outside the cloud, like on-premises servers or in third-party apps. The Import service makes it easy to bring your messaging, SharePoint, and OneDrive for Business data into Office 365, either by uploading it directly over the network or shipping an encrypted drive to us. You can also use the Intelligent Import feature in the Import service to filter the items in PST files that actually get imported to the target mailboxes.</span></span> 
  
- [<span data-ttu-id="effcd-111">Office 365 の PST ファイルのインポートの概要</span><span class="sxs-lookup"><span data-stu-id="effcd-111">Overview of importing PST files to Office 365</span></span>](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)
    
- [<span data-ttu-id="effcd-112">ネットワーク アップロードを使用して PST ファイルを Office 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="effcd-112">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
- [<span data-ttu-id="effcd-113">ドライブ送付を使用して PST ファイルを Office 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="effcd-113">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- [<span data-ttu-id="effcd-114">PST コレクション ツールを使用して、検索、コピー、および組織内の PST ファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="effcd-114">Use the PST Collection Tool to find, copy, and delete PST files in your organization</span></span>](find-copy-and-delete-pst-files-in-your-organization.md)
    
- [<span data-ttu-id="effcd-115">Office 365 に PST ファイルをインポートするときにデータをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="effcd-115">Filter data when importing PST files to Office 365</span></span>](filter-data-when-importing-pst-files.md)
    
- [<span data-ttu-id="effcd-116">PowerShell コマンドレットを使用して、オンプレミス コンテンツを SharePoint Online にアップロードする</span><span class="sxs-lookup"><span data-stu-id="effcd-116">Upload on-premises content to SharePoint Online using PowerShell cmdlets</span></span>](https://support.office.com/article/555049c6-15ef-45a6-9a1f-a1ef673b867c)
    
## <a name="govern-i-store-data"></a><span data-ttu-id="effcd-117">I: ストアのデータを制御します。</span><span class="sxs-lookup"><span data-stu-id="effcd-117">Govern I: Store data</span></span>

<span data-ttu-id="effcd-p104">データをインポートした後は、お客様のストレージを増やす必要があります。アーカイブ機能は、制限はありません (と呼ばれる自動拡張のアーカイブ)、Office 365 は、無制限の量のアーカイブ メールボックス内のストレージを提供します。</span><span class="sxs-lookup"><span data-stu-id="effcd-p104">After you import data, you might need to increase your storage. The unlimited archiving feature in Office 365 (called auto-expanding archiving) provides an unlimited amount of storage in archive mailboxes.</span></span>
  
- [<span data-ttu-id="effcd-120">Office 365 のセキュリティ、アーカイブ メールボックスを有効にする&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="effcd-120">Enable archive mailboxes in the Office 365 Security &amp; Compliance Center</span></span>](enable-archive-mailboxes.md)

- [<span data-ttu-id="effcd-121">Office 365 の無制限のアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="effcd-121">Overview of unlimited archiving in Office 365</span></span>](unlimited-archiving.md)
    
- [<span data-ttu-id="effcd-122">Office 365 の無制限のアーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="effcd-122">Enable unlimited archiving in Office 365</span></span>](enable-unlimited-archiving.md)
    

    
## <a name="govern-ii-create-policies-and-labels-to-retain-content"></a><span data-ttu-id="effcd-123">ポリシーとコンテンツを保持するラベルを作成する II を制御します。</span><span class="sxs-lookup"><span data-stu-id="effcd-123">Govern II: Create policies and labels to retain content</span></span>

<span data-ttu-id="effcd-p105">リテンション ・ ポリシーでは、限り必要がない場合よりもコンテンツを保持することを確保することにより業界の規制や社内ポリシーに準拠して積極的にできます。1 つの保持ポリシーは、組織全体をカバーできます。さらに、ガバナンス、組織全体にわたってデータのクラス分けと、その分類に基づく保存ルールを適用してファイル計画を実装するためにラベルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="effcd-p105">A retention policy helps you to comply proactively with industry regulations and internal policies by ensuring that you retain content as long as required but no longer than that. A single retention policy can cover your entire organization. In addition, you can use labels to implement a file plan by classifying data across your organization for governance, and then enforcing retention rules based on that classification.</span></span>
  
- [<span data-ttu-id="effcd-127">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="effcd-127">Overview of retention policies</span></span>](retention-policies.md)
    
- [<span data-ttu-id="effcd-128">ラベルの概要</span><span class="sxs-lookup"><span data-stu-id="effcd-128">Overview of labels</span></span>](labels.md)
    
- [<span data-ttu-id="effcd-129">一括作成し、PowerShell を使用してラベルを発行します。</span><span class="sxs-lookup"><span data-stu-id="effcd-129">Bulk create and publish labels by using PowerShell</span></span>](https://support.office.com/article/8986701b-ffa1-46ec-8fd0-8f7e81d5b25f.aspx)
    
- [<span data-ttu-id="effcd-130">廃棄レビューの概要</span><span class="sxs-lookup"><span data-stu-id="effcd-130">Overview of disposition reviews</span></span>](disposition-reviews.md)
    
- [<span data-ttu-id="effcd-131">イベント ベースの保持の概要</span><span class="sxs-lookup"><span data-stu-id="effcd-131">Overview of event-driven retention</span></span>](event-driven-retention.md)
    
## <a name="govern-iii-retain-the-email-of-former-employees"></a><span data-ttu-id="effcd-132">退職した従業員の電子メール アドレスを保持する 3 世が制御されます。</span><span class="sxs-lookup"><span data-stu-id="effcd-132">Govern III: Retain the email of former employees</span></span>

<span data-ttu-id="effcd-p106">人が組織を離れたときに非アクティブなメールボックスを作成することによって自分の電子メールを保持できます。メールボックス、証拠保全、Office 365 のリテンション ・ ポリシーと、使用頻度の低いまたは保留中の他の種類が適用されることになり、対応する Office 365 ユーザー アカウントが削除されます。非アクティブなメールボックス内のアイテムが非アクティブにされる前に、メールボックスに格納された、保留中または保存ポリシーの期間中保持されます。</span><span class="sxs-lookup"><span data-stu-id="effcd-p106">When a person leaves your organization, you can retain their email by creating an inactive mailbox. A mailbox becomes inactive when a Litigation Hold, Office 365 retention policy, or other type of hold is applied to it, and then the corresponding Office 365 user account is deleted. Items in an inactive mailbox are retained for the duration of the hold or retention policy that was placed on the mailbox before it was made inactive.</span></span>
  
- [<span data-ttu-id="effcd-136">Office 365 のメールボックスを非アクティブの概要</span><span class="sxs-lookup"><span data-stu-id="effcd-136">Overview of inactive mailboxes in Office 365</span></span>](inactive-mailboxes-in-office-365.md)
    
- [<span data-ttu-id="effcd-137">作成し、Office 365 の非アクティブなメールボックスの管理</span><span class="sxs-lookup"><span data-stu-id="effcd-137">Create and manage inactive mailboxes in Office 365</span></span>](create-and-manage-inactive-mailboxes.md)

- [<span data-ttu-id="effcd-138">Office 365 での非アクティブなメールボックスの保持期間を変更します。</span><span class="sxs-lookup"><span data-stu-id="effcd-138">Change the hold duration for an inactive mailbox in Office 365</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)
  
- [<span data-ttu-id="effcd-139">Office 365 で、非アクティブなメールボックスをリカバリします。</span><span class="sxs-lookup"><span data-stu-id="effcd-139">Recover an inactive mailbox in Office 365</span></span>](recover-an-inactive-mailbox.md)
 
- [<span data-ttu-id="effcd-140">Office 365 で、非アクティブなメールボックスを復元します。</span><span class="sxs-lookup"><span data-stu-id="effcd-140">Restore an inactive mailbox in Office 365</span></span>](restore-an-inactive-mailbox.md)

- [<span data-ttu-id="effcd-141">Office 365 で、非アクティブなメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="effcd-141">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

## <a name="monitor"></a><span data-ttu-id="effcd-142">監視</span><span class="sxs-lookup"><span data-stu-id="effcd-142">Monitor</span></span>

<span data-ttu-id="effcd-p107">監督では、内部または外部の校閲者が調査できるように、電子メールや、組織内のサード パーティ製の通信をキャプチャするためのポリシーを定義することができます。校閲者これらの通信を分類、組織のポリシーに準拠しているかどうかを確認し、必要な場合は、問題のある材料をエスカレートします。</span><span class="sxs-lookup"><span data-stu-id="effcd-p107">Supervision lets you define policies that capture email and 3rd-party communications in your organization so they can be examined by internal or external reviewers. Reviewers can then classify these communications, make sure they're compliant with your organization's policies, and escalate questionable material if necessary.</span></span>
  
<span data-ttu-id="effcd-145">意図したとおりに、ラベルは、コンテンツに適用されているかを監視するのにデータ ・ ガバナンス ・ レポートとラベルのアクティビティのエクスプ ローラーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="effcd-145">You can also use the data governance reports and the Label Activity Explorer to monitor that your labels are being applied to content as you intended.</span></span>
  
- [<span data-ttu-id="effcd-146">組織用に監督ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="effcd-146">Configure supervision policies for your organization</span></span>](configure-supervision-policies.md)
    
- [<span data-ttu-id="effcd-147">監督レポート</span><span class="sxs-lookup"><span data-stu-id="effcd-147">Supervision reports</span></span>](supervision-reports.md)
    
- [<span data-ttu-id="effcd-148">ドキュメントのラベルのアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="effcd-148">View label activity for documents</span></span>](view-label-activity-for-documents.md)
    
- [<span data-ttu-id="effcd-149">データ ガバナンスのレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="effcd-149">View the data governance reports</span></span>](view-the-data-governance-reports.md)
    
## <a name="more-information"></a><span data-ttu-id="effcd-150">詳細情報</span><span class="sxs-lookup"><span data-stu-id="effcd-150">More information</span></span>

- [<span data-ttu-id="effcd-151">Microsoft のデータ ガバナンス チームによるビデオを見る</span><span class="sxs-lookup"><span data-stu-id="effcd-151">Watch videos from the Microsoft Data Governance team</span></span>](https://go.microsoft.com/fwlink/?linkid=867039)
    
- [<span data-ttu-id="effcd-152">Office 365 のデータ管理の概要を見る</span><span class="sxs-lookup"><span data-stu-id="effcd-152">Watch an overview of data governance in Office 365</span></span>](https://go.microsoft.com/fwlink/?linkid=852644)
    
- [<span data-ttu-id="effcd-153">Office 365 のセキュリティ&amp;コマンドレットのコンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="effcd-153">Office 365 Security &amp; Compliance Center cmdlets</span></span>](https://go.microsoft.com/fwlink/?linkid=852310)
    

