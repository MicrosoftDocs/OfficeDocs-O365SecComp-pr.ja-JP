---
title: ファイル計画マネージャーの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: ファイル計画マネージャーは、保持ラベルおよびポリシーのための高度な管理機能を提供します。作成に始まり、コラボレーション、レコード宣言、保持、そして廃棄に至るまでのコンテンツのライフ サイクル全体におけるラベルとコンテンツのラベリングを網羅する統合的な機能を提供します。
ms.openlocfilehash: a6086ce73f898d261af46a1f1493b624db10931d
ms.sourcegitcommit: 799a958fcac643f62dfac6fa04020f2f4758635c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30997273"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="c0151-103">ファイル計画マネージャーの概要</span><span class="sxs-lookup"><span data-stu-id="c0151-103">Overview of file plan manager</span></span>

<span data-ttu-id="c0151-104">ファイル計画マネージャーは、保持ラベルおよびポリシーのための高度な管理機能を提供します。作成に始まり、コラボレーション、レコード宣言、保持、そして廃棄に至るまでのコンテンツのライフ サイクル全体におけるラベルとコンテンツのラベリングを網羅する統合的な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c0151-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![[ファイル計画] ページ](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="c0151-106">ファイル計画マネージャーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="c0151-106">Accessing file plan manager</span></span>

<span data-ttu-id="c0151-107">ファイル計画マネージャーにアクセスするには次の 2 つの要件があります。</span><span class="sxs-lookup"><span data-stu-id="c0151-107">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="c0151-108">Office 365 Enterprise E5 サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="c0151-108">An Office 365 Enterprise E5 subscription.</span></span>
- <span data-ttu-id="c0151-109">次のいずれかのセキュリティ &amp; コンプライアンス センターの役割がユーザーに割り当てられている状態。</span><span class="sxs-lookup"><span data-stu-id="c0151-109">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span> 
    - <span data-ttu-id="c0151-110">保持マネージャー</span><span class="sxs-lookup"><span data-stu-id="c0151-110">Retention Manager</span></span>
    - <span data-ttu-id="c0151-111">閲覧限定保持マネージャー</span><span class="sxs-lookup"><span data-stu-id="c0151-111">View-only Retention Manager</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="c0151-112">ファイル計画の中の移動</span><span class="sxs-lookup"><span data-stu-id="c0151-112">Navigating your file plan</span></span>

<span data-ttu-id="c0151-113">ファイル計画マネージャーでは、すべての保持ラベルとポリシーの設定を 1 つのビューから簡単に参照できます。</span><span class="sxs-lookup"><span data-stu-id="c0151-113">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="c0151-114">ファイル計画の外で作成された保持ラベルはファイル計画上で利用可能で、また、その逆も同様であることに注意します。</span><span class="sxs-lookup"><span data-stu-id="c0151-114">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="c0151-115">[**ファイル計画ラベル**] タブで、次の追加の情報と機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="c0151-115">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="c0151-116">ラベル設定列</span><span class="sxs-lookup"><span data-stu-id="c0151-116">Label settings columns</span></span>
 
- <span data-ttu-id="c0151-p101">[**分類方法**] は保持期間を起動するトリガーの種類を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c0151-p101">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="c0151-119">イベント</span><span class="sxs-lookup"><span data-stu-id="c0151-119">Event</span></span>
    - <span data-ttu-id="c0151-120">作成日時</span><span class="sxs-lookup"><span data-stu-id="c0151-120">When created</span></span>
    - <span data-ttu-id="c0151-121">最終更新日時</span><span class="sxs-lookup"><span data-stu-id="c0151-121">When last modified</span></span>
    - <span data-ttu-id="c0151-122">ラベルが付けられた日時</span><span class="sxs-lookup"><span data-stu-id="c0151-122">When labeled</span></span>
- <span data-ttu-id="c0151-p102">[**レコード**] は、ラベルが適用されときにアイテムが宣言されたレコードが宣言されたレコードになるかどうかを識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c0151-p102">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="c0151-125">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0151-125">No</span></span>
    - <span data-ttu-id="c0151-126">はい</span><span class="sxs-lookup"><span data-stu-id="c0151-126">Yes</span></span>
    - <span data-ttu-id="c0151-127">はい (法的)</span><span class="sxs-lookup"><span data-stu-id="c0151-127">Yes(Regulatory)</span></span>
- <span data-ttu-id="c0151-p103">[**保持**] は保持の種類を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c0151-p103">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="c0151-130">保持</span><span class="sxs-lookup"><span data-stu-id="c0151-130">Keep</span></span>
    - <span data-ttu-id="c0151-131">保持および削除</span><span class="sxs-lookup"><span data-stu-id="c0151-131">Keep and delete</span></span>
    - <span data-ttu-id="c0151-132">削除</span><span class="sxs-lookup"><span data-stu-id="c0151-132">Delete</span></span>
- <span data-ttu-id="c0151-p104">[**廃棄**] は保持期間終了時のコンテンツの取り扱い方法を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c0151-p104">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="c0151-135">null</span><span class="sxs-lookup"><span data-stu-id="c0151-135">null</span></span>
    - <span data-ttu-id="c0151-136">アクションなし</span><span class="sxs-lookup"><span data-stu-id="c0151-136">No action</span></span>
    - <span data-ttu-id="c0151-137">自動削除</span><span class="sxs-lookup"><span data-stu-id="c0151-137">Auto-delete</span></span>
    - <span data-ttu-id="c0151-138">要確認 (廃棄レビューとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="c0151-138">Review required (aka Disposition review)</span></span>

![ファイル計画でのラベル設定](media/file-plan-label-columns.png)

### <a name="label-file-plan-descriptors-columns"></a><span data-ttu-id="c0151-140">ファイル計画記述子列にラベルを付ける</span><span class="sxs-lookup"><span data-stu-id="c0151-140">Label file plan descriptors columns</span></span>

<span data-ttu-id="c0151-p105">より多くの情報を保持ラベルの構成に含めることができます。ファイル計画記述子をラベルに挿入することにより、ファイル計画の管理性が向上し整理がしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="c0151-p105">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="c0151-p106">すぐに利用開始できるように、ファイル計画マネージャーでは次の既定値が提供されています: 役割/部門、カテゴリ、権限の種類、規定/是正勧告。保持ラベルを作成または編集するときに、ファイル計画記述子の値を新たに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c0151-p106">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="c0151-145">保持ラベルを作成または編集時のファイル計画記述子に関する手順の画面です。</span><span class="sxs-lookup"><span data-stu-id="c0151-145">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![ファイル計画記述子](media/file-plan-descriptors.png)

<span data-ttu-id="c0151-147">ファイル計画マネージャーの [ラベル] タブのファイル計画記述子列の画面です。</span><span class="sxs-lookup"><span data-stu-id="c0151-147">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-labels-out-of-your-file-plan"></a><span data-ttu-id="c0151-149">ファイル計画からラベルをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="c0151-149">Export labels out of your file plan</span></span>

<span data-ttu-id="c0151-150">組織内のデータ ガバナンス関係者との定期的なコンプライアンス レビューが円滑に行えるように、ファイル計画マネージャーではすべての保持ラベルの詳細を .csv ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="c0151-150">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="c0151-151">すべての保持ラベルをエクスポートするには、[**ファイル計画マネージャー**] \> [**ファイル計画アクション**] \> [**ラベルのエクスポート**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c0151-151">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![ファイル計画をエクスポートするオプション](media/file-plan-export-labels-option.png)

<span data-ttu-id="c0151-153">既存のすべての保持ラベルを含む \*.csv ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="c0151-153">A \*.csv file containing all existing retention labels will open.</span></span>

![すべての保持ラベルが表示された CSV ファイル](media/file-plan-csv-file.png)

## <a name="import-labels-into-your-file-plan"></a><span data-ttu-id="c0151-155">ファイル計画にラベルをインポートする</span><span class="sxs-lookup"><span data-stu-id="c0151-155">Import labels into your file plan</span></span>

<span data-ttu-id="c0151-156">ファイル計画マネージャーでは新しいラベルの一括インポートおよび既存の保持ラベルの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c0151-156">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="c0151-157">新しい保持ラベルのインポートおよび既存の保持ラベルの更新を行うには、[**ファイル計画マネージャー**] \> [**ファイル計画アクション**] \> [**ラベルのインポート**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c0151-157">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![ファイル計画のインポートのオプション](media/file-plan-import-labels-option.png)

![空白のファイル計画テンプレートをダウンロードするオプション](media/file-plan-blank-template-option.png)

<span data-ttu-id="c0151-160">空白のテンプレートをダウンロードします (または現在のファイル計画のエクスポートを使います)。</span><span class="sxs-lookup"><span data-stu-id="c0151-160">Download a blank template (or start from an export of your current file plan).</span></span>

![Excel で開かれた空白のファイル計画テンプレート](media/file-plan-blank-template.png)

<span data-ttu-id="c0151-162">テンプレートに入力します (“準備中”とは、記載事項の有効値についてのリファレンス情報です)。</span><span class="sxs-lookup"><span data-stu-id="c0151-162">Fill-out the template (coming soon is reference information about valid values for entries).</span></span>

![情報が入力されたファイル計画テンプレート](media/file-plan-filled-out-template.png)

<span data-ttu-id="c0151-164">入力済みのテンプレートをアップロードすると、ファイル計画マネージャーで記載事項が検証され、インポートの統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0151-164">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![ファイル計画のインポートの統計情報](media/file-plan-import-statistics.png)

<span data-ttu-id="c0151-166">インポートが完了したらファイル計画マネージャーに戻り、新規または既存のポリシーに新しいラベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c0151-166">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![ラベルを公開するオプション](media/file-plan-publish-labels-option.png)

