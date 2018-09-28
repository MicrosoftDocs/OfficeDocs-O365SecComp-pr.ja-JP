---
title: ファイル計画マネージャーの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 9/25/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: ファイル計画マネージャーは、アイテム保持ラベルおよびポリシーのための高度な管理機能を提供します。作成に始まり、コラボレーション、レコード宣言、保持、そして廃棄に至るまでのコンテンツのライフ サイクル全体におけるラベルとコンテンツのラベリングを網羅する統合的な機能を提供します。
ms.openlocfilehash: 4feacf20444591f6da2d55a928a81e86b56c5d9a
ms.sourcegitcommit: 9f34ace6bbe3d5e07e24ebaae96613750869cddf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25019278"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="aba67-103">ファイル計画マネージャーの概要</span><span class="sxs-lookup"><span data-stu-id="aba67-103">Overview of file plan manager</span></span>

<span data-ttu-id="aba67-104">ファイル計画マネージャーは、アイテム保持ラベルおよびポリシーのための高度な管理機能を提供します。作成に始まり、コラボレーション、レコード宣言、保持、そして廃棄に至るまでのコンテンツのライフ サイクル全体におけるラベルとコンテンツのラベリングを網羅する統合的な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="aba67-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![[ファイル計画] ページ](media/file-plan-page.png)

## <a name="important-this-feature-is-currently-available-only-as-part-of-the-office-365-preview-program"></a><span data-ttu-id="aba67-106">重要: 現在、この機能は Office 365 Preview プログラムの一部としてのみ提供されています</span><span class="sxs-lookup"><span data-stu-id="aba67-106">Important: This feature is currently available only as part of the Office 365 Preview program</span></span>

<span data-ttu-id="aba67-107">お客様の組織が Office 365 Preview プログラムに登録されている場合にのみ、テナントでこの機能が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aba67-107">You will see this feature in your tenant only if your organization has enrolled in the Office 365 Preview program.</span></span>

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="aba67-108">ファイル計画マネージャーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="aba67-108">Accessing file plan manager</span></span>

<span data-ttu-id="aba67-109">ファイル計画マネージャーにアクセスするには次の 2 つの要件があります。</span><span class="sxs-lookup"><span data-stu-id="aba67-109">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="aba67-110">Office 365 Enterprise E5 サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="aba67-110">An Office 365 Enterprise E5 subscription with user licenses.</span></span>
- <span data-ttu-id="aba67-111">次のいずれかのセキュリティ &amp;コンプライアンス センターの役割がユーザーに割り当てられている状態。</span><span class="sxs-lookup"><span data-stu-id="aba67-111">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span> 
    - <span data-ttu-id="aba67-112">保持マネージャー</span><span class="sxs-lookup"><span data-stu-id="aba67-112">Retention Manager</span></span>
    - <span data-ttu-id="aba67-113">閲覧限定保持マネージャー</span><span class="sxs-lookup"><span data-stu-id="aba67-113">View-only Retention Manager</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="aba67-114">ファイル計画の中の移動</span><span class="sxs-lookup"><span data-stu-id="aba67-114">Navigating your file plan</span></span>

<span data-ttu-id="aba67-115">ファイル計画マネージャーでは、すべてのアイテム保持ラベルとポリシーの設定を 1 つのビューから簡単に参照できます。</span><span class="sxs-lookup"><span data-stu-id="aba67-115">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="aba67-116">ファイル計画の外で作成されたアイテム保持ラベルはファイル計画上で利用可能で、また、その逆も同様であることに注意します。</span><span class="sxs-lookup"><span data-stu-id="aba67-116">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="aba67-117">[**ファイル計画ラベル**] タブで、次の追加の情報と機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="aba67-117">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="aba67-118">ラベル設定列</span><span class="sxs-lookup"><span data-stu-id="aba67-118">Label settings columns</span></span>
 
- <span data-ttu-id="aba67-p101">[**分類方法**] は保持期間を起動するトリガーの種類を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aba67-p101">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="aba67-121">イベント</span><span class="sxs-lookup"><span data-stu-id="aba67-121">Event</span></span>
    - <span data-ttu-id="aba67-122">作成日時</span><span class="sxs-lookup"><span data-stu-id="aba67-122">When created</span></span>
    - <span data-ttu-id="aba67-123">更新日時</span><span class="sxs-lookup"><span data-stu-id="aba67-123">When last modified</span></span>
    - <span data-ttu-id="aba67-124">ラベルが付けられた日時</span><span class="sxs-lookup"><span data-stu-id="aba67-124">When labeled</span></span>
- <span data-ttu-id="aba67-p102">**レコード** は、ラベルが適用されときにアイテムが宣言されたレコードが宣言されたレコードになるかどうかを識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aba67-p102">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="aba67-127">いいえ</span><span class="sxs-lookup"><span data-stu-id="aba67-127">No</span></span>
    - <span data-ttu-id="aba67-128">はい</span><span class="sxs-lookup"><span data-stu-id="aba67-128">Yes</span></span>
    - <span data-ttu-id="aba67-129">はい (法的)</span><span class="sxs-lookup"><span data-stu-id="aba67-129">Yes(Regulatory)</span></span>
- <span data-ttu-id="aba67-p103">[**保持**] は保持の種類を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aba67-p103">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="aba67-132">保持</span><span class="sxs-lookup"><span data-stu-id="aba67-132">Keep</span></span>
    - <span data-ttu-id="aba67-133">保持および削除</span><span class="sxs-lookup"><span data-stu-id="aba67-133">Keep and delete</span></span>
    - <span data-ttu-id="aba67-134">削除</span><span class="sxs-lookup"><span data-stu-id="aba67-134">Delete</span></span>
- <span data-ttu-id="aba67-p104">[**廃棄**] は保持期間終了時のコンテンツの取り扱い方法を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aba67-p104">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="aba67-137">null</span><span class="sxs-lookup"><span data-stu-id="aba67-137">Null</span></span>
    - <span data-ttu-id="aba67-138">アクションなし</span><span class="sxs-lookup"><span data-stu-id="aba67-138">No action necessary.</span></span>
    - <span data-ttu-id="aba67-139">自動削除</span><span class="sxs-lookup"><span data-stu-id="aba67-139">Auto-delete</span></span>
    - <span data-ttu-id="aba67-140">要確認 (廃棄レビューも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="aba67-140">Review required (aka Disposition review)</span></span>

![ファイル計画でのラベル設定](media/file-plan-label-columns.png)

### <a name="label-file-plan-descriptors-columns"></a><span data-ttu-id="aba67-142">ファイル計画記述子列にラベルを付ける</span><span class="sxs-lookup"><span data-stu-id="aba67-142">Label file plan descriptors columns</span></span>

<span data-ttu-id="aba67-p105">より多くの情報をアイテム保持ラベルの構成に含めることができます。ファイル計画記述子をラベルに挿入することにより、ファイル計画の管理性が向上し整理がしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="aba67-p105">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="aba67-p106">すぐに利用開始できるように、ファイル計画マネージャーでは次の既定値が提供されています: 役割/部門、カテゴリ、権限の種類、および規定/是正勧告。アイテム保持ラベルを作成または編集するときに、ファイル計画記述子の値を新たに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="aba67-p106">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="aba67-147">アイテム保持ラベルを作成または編集時のファイル計画記述子に関するステップの画面です。</span><span class="sxs-lookup"><span data-stu-id="aba67-147">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![ファイル計画記述子](media/file-plan-descriptors.png)

<span data-ttu-id="aba67-149">ファイル計画マネージャーの [ラベル] タブのファイル計画記述子列の画面です。</span><span class="sxs-lookup"><span data-stu-id="aba67-149">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-labels-out-of-your-file-plan"></a><span data-ttu-id="aba67-151">ファイル計画からラベルをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="aba67-151">Export labels out of your file plan</span></span>

<span data-ttu-id="aba67-152">組織内のデータ ガバナンス関係者との定期的なコンプライアンス レビューが円滑に行えるように、ファイル計画マネージャーではすべてのアイテム保持ラベルの詳細を .csv ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="aba67-152">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="aba67-153">すべてのアイテム保持ラベルをエクスポートするには、[**ファイル計画マネージャー**] \> [**ファイル計画アクション**] \> [**ラベルのエクスポート**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="aba67-153">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![ファイル計画をエクスポートするオプション](media/file-plan-export-labels-option.png)

<span data-ttu-id="aba67-155">既存のすべてのアイテム保持ラベルを含む \*.csv ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="aba67-155">A \*.csv file containing all existing retention labels will open.</span></span>

![すべてのアイテム保持ラベルが表示されたCSV ファイル](media/file-plan-csv-file.png)

## <a name="import-labels-into-your-file-plan"></a><span data-ttu-id="aba67-157">ファイル計画にラベルをインポートする</span><span class="sxs-lookup"><span data-stu-id="aba67-157">Import labels into your file plan</span></span>

<span data-ttu-id="aba67-158">ファイル計画マネージャーでは新しいラベルの一括インポートおよび既存のアイテム保持ラベルの変更が行えます。</span><span class="sxs-lookup"><span data-stu-id="aba67-158">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="aba67-159">新しいアイテム保持ラベルのインポートおよび既存のアイテム保持ラベルの更新を行うには、[**ファイル計画マネージャー**] \> [**ファイル計画アクション**] \> [**ラベルのインポート**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="aba67-159">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![ファイル計画のインポートのオプション](media/file-plan-import-labels-option.png)

![空白のファイル計画テンプレートをダウンロードするオプション](media/file-plan-blank-template-option.png)

<span data-ttu-id="aba67-162">空白のテンプレートをダウンロードします (または現在のファイル計画のエクスポートを使います)。</span><span class="sxs-lookup"><span data-stu-id="aba67-162">Download a blank template (or start from an export of your current file plan).</span></span>

![Excel で開かれた空白のファイル計画テンプレート](media/file-plan-blank-template.png)

<span data-ttu-id="aba67-164">テンプレートに入力します (“準備中”とは、記載事項の有効値についてのリファレンス情報です)。</span><span class="sxs-lookup"><span data-stu-id="aba67-164">Fill-out the template (coming soon is reference information about valid values for entries).</span></span>

![情報が入力されたファイル計画テンプレート](media/file-plan-filled-out-template.png)

<span data-ttu-id="aba67-166">入力済みのテンプレートをアップロードすると、ファイル計画マネージャーで記載事項が検証され、インポートの統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aba67-166">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![ファイル計画のインポートの統計情報](media/file-plan-import-statistics.png)

<span data-ttu-id="aba67-168">インポートが完了したらファイル計画マネージャーに戻り、新規または既存のポリシーに新しいラベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="aba67-168">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![ラベルを公開するオプション](media/file-plan-publish-labels-option.png)
