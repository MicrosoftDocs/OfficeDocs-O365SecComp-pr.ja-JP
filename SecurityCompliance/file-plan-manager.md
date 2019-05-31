---
title: ファイル計画マネージャーの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: ファイル計画マネージャーは、保持ラベルおよび保持ラベル ポリシーのための高度な管理機能を提供します。作成に始まり、コラボレーション、レコード宣言、保持、そして廃棄に至るまでのコンテンツのライフ サイクル全体におけるラベルとコンテンツのラベリングを網羅する統合的な機能を提供します。
ms.openlocfilehash: b7d80ff6a7f78e592462fe2723a87383e046015f
ms.sourcegitcommit: 6eb51931242d07abde2e37f1bd57d13bc724f0de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34547972"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="889ea-103">ファイル計画マネージャーの概要</span><span class="sxs-lookup"><span data-stu-id="889ea-103">Overview of file plan manager</span></span>

<span data-ttu-id="889ea-104">ファイル計画マネージャーは、保持ラベルおよび保持ラベル ポリシーのための高度な管理機能を提供します。作成に始まり、コラボレーション、レコード宣言、保持、そして廃棄に至るまでのコンテンツのライフ サイクル全体におけるラベルとコンテンツのラベリングを網羅する統合的な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="889ea-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![[ファイル計画] ページ](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="889ea-106">ファイル計画マネージャーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="889ea-106">Accessing file plan manager</span></span>

<span data-ttu-id="889ea-107">ファイル計画マネージャーにアクセスするには次の 2 つの要件があります。</span><span class="sxs-lookup"><span data-stu-id="889ea-107">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="889ea-108">Office 365 Enterprise E5 サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="889ea-108">An Office 365 Enterprise E5 subscription.</span></span>
- <span data-ttu-id="889ea-109">次のいずれかのセキュリティ &amp; コンプライアンス センターの役割がユーザーに割り当てられている状態。</span><span class="sxs-lookup"><span data-stu-id="889ea-109">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span>
    - <span data-ttu-id="889ea-110">保持マネージャー</span><span class="sxs-lookup"><span data-stu-id="889ea-110">Retention Manager</span></span>
    - <span data-ttu-id="889ea-111">閲覧限定保持マネージャー</span><span class="sxs-lookup"><span data-stu-id="889ea-111">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="889ea-112">デフォルトの保持ラベルとラベルポリシー</span><span class="sxs-lookup"><span data-stu-id="889ea-112">Default retention labels and label policy</span></span>

<span data-ttu-id="889ea-113">セキュリティ＆コンプライアンスセンターに保持ラベルがない場合、左ナビゲーションで**ファイルプラン**を最初に選択すると、**デフォルトデータガバナンス公開ポリシー**というラベルポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="889ea-113">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="889ea-114">このラベルポリシーには、3つの保持ラベルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="889ea-114">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="889ea-115">**運用手順**</span><span class="sxs-lookup"><span data-stu-id="889ea-115">**Operational procedure**</span></span>
- <span data-ttu-id="889ea-116">**企業一般**</span><span class="sxs-lookup"><span data-stu-id="889ea-116">**Business general**</span></span>
- <span data-ttu-id="889ea-117">**契約規定**</span><span class="sxs-lookup"><span data-stu-id="889ea-117">**Contract agreement**</span></span>

<span data-ttu-id="889ea-118">これらの保持ラベルは、コンテンツを保持するためだけに構成され、コンテンツを削除するためには構成されていません。</span><span class="sxs-lookup"><span data-stu-id="889ea-118">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="889ea-119">このラベルポリシーは組織全体に公開され、無効にすることも削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="889ea-119">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="889ea-120">アクティビティ**作成済み保持ポリシー**および**作成済み保持ポリシーの保持設定**の監査ログを確認することで、ファイルプランマネージャを開いて初めて実行環境を構築したユーザを特定できます。</span><span class="sxs-lookup"><span data-stu-id="889ea-120">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="889ea-121">お客様からのフィードバックにより、デフォルトの保持ラベルと保持ラベル ラベルポリシーを作成する上記のこの機能は削除されました。</span><span class="sxs-lookup"><span data-stu-id="889ea-121">Due to customer feedback, we have removed this feature that creates the default retention labels and label policy mentioned above.</span></span> <span data-ttu-id="889ea-122">これらの保持ラベルと保持ラベル ラベルポリシーは、ファイル計画マネージャーを 2019 年 4 月 11 日より前に開いたことがある場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="889ea-122">You will only see this policy and labels if you used file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="889ea-123">ファイル計画の中の移動</span><span class="sxs-lookup"><span data-stu-id="889ea-123">Navigating your file plan</span></span>

<span data-ttu-id="889ea-124">ファイル計画マネージャーでは、すべての保持ラベルとポリシーの設定を 1 つのビューから簡単に参照できます。</span><span class="sxs-lookup"><span data-stu-id="889ea-124">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="889ea-125">ファイル計画の外で作成された保持ラベルはファイル計画上で利用可能で、また、その逆も同様であることに注意します。</span><span class="sxs-lookup"><span data-stu-id="889ea-125">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="889ea-126">[**ファイル計画ラベル**] タブで、次の追加の情報と機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="889ea-126">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="889ea-127">ラベル設定列</span><span class="sxs-lookup"><span data-stu-id="889ea-127">Label settings columns</span></span>

- <span data-ttu-id="889ea-p103">[**分類方法**] は保持期間を起動するトリガーの種類を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="889ea-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="889ea-130">イベント</span><span class="sxs-lookup"><span data-stu-id="889ea-130">Event</span></span>
    - <span data-ttu-id="889ea-131">作成日時</span><span class="sxs-lookup"><span data-stu-id="889ea-131">When created</span></span>
    - <span data-ttu-id="889ea-132">最終更新日時</span><span class="sxs-lookup"><span data-stu-id="889ea-132">When last modified</span></span>
    - <span data-ttu-id="889ea-133">ラベルが付けられた日時</span><span class="sxs-lookup"><span data-stu-id="889ea-133">When labeled</span></span>
- <span data-ttu-id="889ea-p104">[**レコード**] は、ラベルが適用されときにアイテムが宣言されたレコードが宣言されたレコードになるかどうかを識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="889ea-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="889ea-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="889ea-136">No</span></span>
    - <span data-ttu-id="889ea-137">はい</span><span class="sxs-lookup"><span data-stu-id="889ea-137">Yes</span></span>
    - <span data-ttu-id="889ea-138">はい (法的)</span><span class="sxs-lookup"><span data-stu-id="889ea-138">Yes(Regulatory)</span></span>
- <span data-ttu-id="889ea-p105">[**保持**] は保持の種類を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="889ea-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="889ea-141">保持</span><span class="sxs-lookup"><span data-stu-id="889ea-141">Keep</span></span>
    - <span data-ttu-id="889ea-142">保持および削除</span><span class="sxs-lookup"><span data-stu-id="889ea-142">Keep and delete</span></span>
    - <span data-ttu-id="889ea-143">削除</span><span class="sxs-lookup"><span data-stu-id="889ea-143">Delete</span></span>
- <span data-ttu-id="889ea-p106">[**廃棄**] は保持期間終了時のコンテンツの取り扱い方法を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="889ea-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="889ea-146">null</span><span class="sxs-lookup"><span data-stu-id="889ea-146">null</span></span>
    - <span data-ttu-id="889ea-147">アクションなし</span><span class="sxs-lookup"><span data-stu-id="889ea-147">No action</span></span>
    - <span data-ttu-id="889ea-148">自動削除</span><span class="sxs-lookup"><span data-stu-id="889ea-148">Auto-delete</span></span>
    - <span data-ttu-id="889ea-149">要確認 (廃棄レビューとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="889ea-149">Review required (aka Disposition review)</span></span>

![ファイル計画でのラベル設定](media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a><span data-ttu-id="889ea-151">保持ラベル ファイル計画記述子列</span><span class="sxs-lookup"><span data-stu-id="889ea-151">Label file plan descriptors columns</span></span>

<span data-ttu-id="889ea-p107">より多くの情報を保持ラベルの構成に含めることができます。ファイル計画記述子を保持ラベルに挿入することにより、ファイル計画の管理性が向上し整理がしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="889ea-p107">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="889ea-p108">すぐに利用開始できるように、ファイル計画マネージャーでは次の既定値が提供されています: 役割/部門、カテゴリ、権限の種類、規定/是正勧告。保持ラベルを作成または編集するときに、ファイル計画記述子の値を新たに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="889ea-p108">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="889ea-156">保持ラベルを作成または編集時のファイル計画記述子に関する手順の画面です。</span><span class="sxs-lookup"><span data-stu-id="889ea-156">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![ファイル計画記述子](media/file-plan-descriptors.png)

<span data-ttu-id="889ea-158">ファイル計画マネージャーの [ラベル] タブのファイル計画記述子列の画面です。</span><span class="sxs-lookup"><span data-stu-id="889ea-158">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a><span data-ttu-id="889ea-160">分析したりオフライン レビューを実行したりするために、すべての既存の保持ラベルをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="889ea-160">Export all existing retention labels to analyze and/or perform offline reviews</span></span>

<span data-ttu-id="889ea-161">組織内のデータ ガバナンス関係者との定期的なコンプライアンス レビューが円滑に行えるように、ファイル計画マネージャーではすべての保持ラベルの詳細を .csv ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="889ea-161">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="889ea-162">すべての保持ラベルをエクスポートするには、[**ファイル計画マネージャー**] \> [**ファイル計画アクション**] \> [**ラベルのエクスポート**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="889ea-162">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![ファイル計画をエクスポートするオプション](media/file-plan-export-labels-option.png)

<span data-ttu-id="889ea-164">既存のすべての保持ラベルを含む \*.csv ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="889ea-164">A \*.csv file containing all existing retention labels will open.</span></span>

![すべての保持ラベルが表示された CSV ファイル](media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="889ea-166">ファイル計画に保持ラベルをインポートする</span><span class="sxs-lookup"><span data-stu-id="889ea-166">Import labels into your file plan</span></span>

<span data-ttu-id="889ea-167">ファイル計画マネージャーでは新しい保持ラベルの一括インポートおよび既存の保持ラベルの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="889ea-167">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="889ea-168">新しい保持ラベルのインポートおよび既存の保持ラベルの更新を行うには、[**ファイル計画マネージャー**] \> [**ファイル計画アクション**] \> [**ラベルのインポート**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="889ea-168">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![ファイル計画のインポートのオプション](media/file-plan-import-labels-option.png)

![空白のファイル計画テンプレートをダウンロードするオプション](media/file-plan-blank-template-option.png)

<span data-ttu-id="889ea-171">空白のテンプレートをダウンロードします (または現在のファイル計画のエクスポートを使います)。</span><span class="sxs-lookup"><span data-stu-id="889ea-171">Download a blank template (or start from an export of your current file plan).</span></span>

![Excel で開かれた空白のファイル計画テンプレート](media/file-plan-blank-template.png)

<span data-ttu-id="889ea-173">テンプレートに情報を入力します (近日公開: 1 つの保有ラベルの有効な値の組み合わせに関する参照情報)。</span><span class="sxs-lookup"><span data-stu-id="889ea-173">Fill-out the template (coming soon: reference information about valid value combinations for a single retention label).</span></span>

![情報が入力されたファイル計画テンプレート](media/file-plan-filled-out-template.png)

<span data-ttu-id="889ea-175">入力済みのテンプレートをアップロードすると、ファイル計画マネージャーで記載事項が検証され、インポートの統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="889ea-175">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![ファイル計画のインポートの統計情報](media/file-plan-import-statistics.png)

<span data-ttu-id="889ea-177">検証エラーが発生した場合、ファイル計画のインポートはインポート ファイル内のすべてのエントリを引き続き検証し、インポートファイル内でエラーを参照するラインまたは行の番号を表示し、表示されたエラー結果をコピーます。これにより、簡単にインポートファイル戻り、エラーを修正することができます。</span><span class="sxs-lookup"><span data-stu-id="889ea-177">In the event there is a validation error, file plan import will continue to validate every entry in the import file and display all errors referencing line/row numbers in the import file, copy the displayed error results so that you can easilly return to the import file and correct the errors.</span></span> 

<span data-ttu-id="889ea-178">インポートが完了したらファイル計画マネージャーに戻り、新しい保持ラベルを新規または既存の保持ポリシーと関連付けます。</span><span class="sxs-lookup"><span data-stu-id="889ea-178">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![ラベルを公開するオプション](media/file-plan-publish-labels-option.png)

