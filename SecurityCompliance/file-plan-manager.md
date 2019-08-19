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
ms.openlocfilehash: 38bfb1e6a6cde931804e518660ddf6c2b45205b0
ms.sourcegitcommit: f443de08971da2fe200a159b8efbed40effba125
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "36430014"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="685ee-103">ファイル計画マネージャーの概要</span><span class="sxs-lookup"><span data-stu-id="685ee-103">Overview of file plan manager</span></span>

<span data-ttu-id="685ee-104">ファイル計画マネージャーは、保持ラベルおよび保持ラベル ポリシーのための高度な管理機能を提供します。作成に始まり、コラボレーション、レコード宣言、保持、そして廃棄に至るまでのコンテンツのライフ サイクル全体におけるラベルとコンテンツのラベリングを網羅する統合的な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="685ee-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![[ファイル計画] ページ](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="685ee-106">ファイル計画マネージャーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="685ee-106">Accessing file plan manager</span></span>

<span data-ttu-id="685ee-107">ファイル計画マネージャーにアクセスするには次の 2 つの要件があります。</span><span class="sxs-lookup"><span data-stu-id="685ee-107">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="685ee-108">Office 365 Enterprise E5 サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="685ee-108">An Office 365 Enterprise E5 subscription.</span></span>
- <span data-ttu-id="685ee-109">次のいずれかのセキュリティ &amp; コンプライアンス センターの役割がユーザーに割り当てられている状態。</span><span class="sxs-lookup"><span data-stu-id="685ee-109">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span>
    - <span data-ttu-id="685ee-110">保持マネージャー</span><span class="sxs-lookup"><span data-stu-id="685ee-110">Retention Manager</span></span>
    - <span data-ttu-id="685ee-111">閲覧限定保持マネージャー</span><span class="sxs-lookup"><span data-stu-id="685ee-111">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="685ee-112">デフォルトの保持ラベルとラベルポリシー</span><span class="sxs-lookup"><span data-stu-id="685ee-112">Default retention labels and label policy</span></span>

<span data-ttu-id="685ee-113">セキュリティ＆コンプライアンスセンターに保持ラベルがない場合、左ナビゲーションで**ファイルプラン**を最初に選択すると、**デフォルトデータガバナンス公開ポリシー**というラベルポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="685ee-113">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="685ee-114">このラベルポリシーには、3つの保持ラベルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="685ee-114">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="685ee-115">**運用手順**</span><span class="sxs-lookup"><span data-stu-id="685ee-115">**Operational procedure**</span></span>
- <span data-ttu-id="685ee-116">**企業一般**</span><span class="sxs-lookup"><span data-stu-id="685ee-116">**Business general**</span></span>
- <span data-ttu-id="685ee-117">**契約規定**</span><span class="sxs-lookup"><span data-stu-id="685ee-117">**Contract agreement**</span></span>

<span data-ttu-id="685ee-118">これらの保持ラベルは、コンテンツを保持するためだけに構成され、コンテンツを削除するためには構成されていません。</span><span class="sxs-lookup"><span data-stu-id="685ee-118">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="685ee-119">このラベルポリシーは組織全体に公開され、無効にすることも削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="685ee-119">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="685ee-120">アクティビティ**作成済み保持ポリシー**および**作成済み保持ポリシーの保持設定**の監査ログを確認することで、ファイルプランマネージャを開いて初めて実行環境を構築したユーザを特定できます。</span><span class="sxs-lookup"><span data-stu-id="685ee-120">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="685ee-121">お客様からのフィードバックにより、デフォルトの保持ラベルと保持ラベル ラベルポリシーを作成する上記のこの機能は削除されました。</span><span class="sxs-lookup"><span data-stu-id="685ee-121">Due to customer feedback, we have removed this feature that creates the default retention labels and label policy mentioned above.</span></span> <span data-ttu-id="685ee-122">これらの保持ラベルと保持ラベル ラベルポリシーは、ファイル計画マネージャーを 2019 年 4 月 11 日より前に開いたことがある場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="685ee-122">You will only see this policy and labels if you used file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="685ee-123">ファイル計画の中の移動</span><span class="sxs-lookup"><span data-stu-id="685ee-123">Navigating your file plan</span></span>

<span data-ttu-id="685ee-124">ファイル計画マネージャーでは、すべての保持ラベルとポリシーの設定を 1 つのビューから簡単に参照できます。</span><span class="sxs-lookup"><span data-stu-id="685ee-124">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="685ee-125">ファイル計画の外で作成された保持ラベルはファイル計画上で利用可能で、また、その逆も同様であることに注意します。</span><span class="sxs-lookup"><span data-stu-id="685ee-125">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="685ee-126">[**ファイル計画ラベル**] タブで、次の追加の情報と機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="685ee-126">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="685ee-127">ラベル設定列</span><span class="sxs-lookup"><span data-stu-id="685ee-127">Label settings columns</span></span>

- <span data-ttu-id="685ee-p103">[**分類方法**] は保持期間を起動するトリガーの種類を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="685ee-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="685ee-130">イベント</span><span class="sxs-lookup"><span data-stu-id="685ee-130">Event</span></span>
    - <span data-ttu-id="685ee-131">作成日時</span><span class="sxs-lookup"><span data-stu-id="685ee-131">When created</span></span>
    - <span data-ttu-id="685ee-132">最終更新日時</span><span class="sxs-lookup"><span data-stu-id="685ee-132">When last modified</span></span>
    - <span data-ttu-id="685ee-133">ラベルが付けられた日時</span><span class="sxs-lookup"><span data-stu-id="685ee-133">When labeled</span></span>
- <span data-ttu-id="685ee-p104">[**レコード**] は、ラベルが適用されときにアイテムが宣言されたレコードが宣言されたレコードになるかどうかを識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="685ee-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="685ee-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="685ee-136">No</span></span>
    - <span data-ttu-id="685ee-137">はい</span><span class="sxs-lookup"><span data-stu-id="685ee-137">Yes</span></span>
    - <span data-ttu-id="685ee-138">はい (法的)</span><span class="sxs-lookup"><span data-stu-id="685ee-138">Yes(Regulatory)</span></span>
- <span data-ttu-id="685ee-p105">[**保持**] は保持の種類を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="685ee-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="685ee-141">保持</span><span class="sxs-lookup"><span data-stu-id="685ee-141">Keep</span></span>
    - <span data-ttu-id="685ee-142">保持および削除</span><span class="sxs-lookup"><span data-stu-id="685ee-142">Keep and delete</span></span>
    - <span data-ttu-id="685ee-143">削除</span><span class="sxs-lookup"><span data-stu-id="685ee-143">Delete</span></span>
- <span data-ttu-id="685ee-p106">[**廃棄**] は保持期間終了時のコンテンツの取り扱い方法を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="685ee-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="685ee-146">null</span><span class="sxs-lookup"><span data-stu-id="685ee-146">null</span></span>
    - <span data-ttu-id="685ee-147">アクションなし</span><span class="sxs-lookup"><span data-stu-id="685ee-147">No action</span></span>
    - <span data-ttu-id="685ee-148">自動削除</span><span class="sxs-lookup"><span data-stu-id="685ee-148">Auto-delete</span></span>
    - <span data-ttu-id="685ee-149">要確認 (廃棄レビューとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="685ee-149">Review required (aka Disposition review)</span></span>

![ファイル計画でのラベル設定](media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a><span data-ttu-id="685ee-151">保持ラベル ファイル計画記述子列</span><span class="sxs-lookup"><span data-stu-id="685ee-151">Label file plan descriptors columns</span></span>

<span data-ttu-id="685ee-p107">より多くの情報を保持ラベルの構成に含めることができます。ファイル計画記述子を保持ラベルに挿入することにより、ファイル計画の管理性が向上し整理がしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="685ee-p107">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="685ee-p108">すぐに利用開始できるように、ファイル計画マネージャーでは次の既定値が提供されています: 役割/部門、カテゴリ、権限の種類、規定/是正勧告。保持ラベルを作成または編集するときに、ファイル計画記述子の値を新たに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="685ee-p108">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="685ee-156">保持ラベルを作成または編集時のファイル計画記述子に関する手順の画面です。</span><span class="sxs-lookup"><span data-stu-id="685ee-156">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![ファイル計画記述子](media/file-plan-descriptors.png)

<span data-ttu-id="685ee-158">ファイル計画マネージャーの [ラベル] タブのファイル計画記述子列の画面です。</span><span class="sxs-lookup"><span data-stu-id="685ee-158">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a><span data-ttu-id="685ee-160">分析したりオフライン レビューを実行したりするために、すべての既存の保持ラベルをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="685ee-160">Export all existing retention labels to analyze and/or perform offline reviews</span></span>

<span data-ttu-id="685ee-161">組織内のデータ ガバナンス関係者との定期的なコンプライアンス レビューが円滑に行えるように、ファイル計画マネージャーではすべての保持ラベルの詳細を .csv ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="685ee-161">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="685ee-162">すべての保持ラベルをエクスポートするには、[**ファイル計画マネージャー**] \> [**ファイル計画アクション**] \> [**ラベルのエクスポート**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="685ee-162">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![ファイル計画をエクスポートするオプション](media/file-plan-export-labels-option.png)

<span data-ttu-id="685ee-164">既存のすべての保持ラベルを含む \*.csv ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="685ee-164">A \*.csv file containing all existing retention labels will open.</span></span>

![すべての保持ラベルが表示された CSV ファイル](media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="685ee-166">ファイル計画に保持ラベルをインポートする</span><span class="sxs-lookup"><span data-stu-id="685ee-166">Import labels into your file plan</span></span>

<span data-ttu-id="685ee-167">ファイル計画マネージャーでは新しい保持ラベルの一括インポートおよび既存の保持ラベルの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="685ee-167">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="685ee-168">新しい保持ラベルのインポートおよび既存の保持ラベルの更新を行うには、[**ファイル計画マネージャー**] \> [**ファイル計画アクション**] \> [**ラベルのインポート**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="685ee-168">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![ファイル計画のインポートのオプション](media/file-plan-import-labels-option.png)

![空白のファイル計画テンプレートをダウンロードするオプション](media/file-plan-blank-template-option.png)

<span data-ttu-id="685ee-171">空白のテンプレートをダウンロードします (または現在のファイル計画のエクスポートを使います)。</span><span class="sxs-lookup"><span data-stu-id="685ee-171">Download a blank template (or start from an export of your current file plan).</span></span>

![Excel で開かれた空白のファイル計画テンプレート](media/file-plan-blank-template.png)

<span data-ttu-id="685ee-173">テンプレートに入力します。</span><span class="sxs-lookup"><span data-stu-id="685ee-173">Fill-out the template.</span></span> <span data-ttu-id="685ee-174">このテーブルは、有効な値を提供します。</span><span class="sxs-lookup"><span data-stu-id="685ee-174">This table provides valid values.</span></span>

|<span data-ttu-id="685ee-175">**Property**</span><span class="sxs-lookup"><span data-stu-id="685ee-175">**Property**</span></span>|<span data-ttu-id="685ee-176">**種類**</span><span class="sxs-lookup"><span data-stu-id="685ee-176">**Type**</span></span>|<span data-ttu-id="685ee-177">**有効な値**</span><span class="sxs-lookup"><span data-stu-id="685ee-177">**Valid values**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="685ee-178">LabelName</span><span class="sxs-lookup"><span data-stu-id="685ee-178">LabelName</span></span>|<span data-ttu-id="685ee-179">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-179">String</span></span>|<span data-ttu-id="685ee-180">値にスペースが含まれている場合は、値を二重引用符 (") で囲んでください。</span><span class="sxs-lookup"><span data-stu-id="685ee-180">If the value contains spaces, enclose the value in quotation marks (").</span></span>|
|<span data-ttu-id="685ee-181">コメント</span><span class="sxs-lookup"><span data-stu-id="685ee-181">Comment</span></span>|<span data-ttu-id="685ee-182">String</span><span class="sxs-lookup"><span data-stu-id="685ee-182">String</span></span>|<span data-ttu-id="685ee-183">値にスペースが含まれている場合は、値を二重引用符 (") で囲んでください。</span><span class="sxs-lookup"><span data-stu-id="685ee-183">If the value contains spaces, enclose the value in quotation marks (").</span></span> |
|<span data-ttu-id="685ee-184">メモ</span><span class="sxs-lookup"><span data-stu-id="685ee-184">Notes</span></span>|<span data-ttu-id="685ee-185">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-185">String</span></span>|<span data-ttu-id="685ee-186">カスタム</span><span class="sxs-lookup"><span data-stu-id="685ee-186">Custom</span></span>|
|<span data-ttu-id="685ee-187">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="685ee-187">IsRecordLabel</span></span>|<span data-ttu-id="685ee-188">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-188">String</span></span>|<span data-ttu-id="685ee-189">$true: ラベルはレコード ラベルです。</span><span class="sxs-lookup"><span data-stu-id="685ee-189">The 
                IsRecordLabel
              parameter specifies whether the label is a record label.</span></span></br><span data-ttu-id="685ee-190">$false: ラベルはレコード ラベルではありません。</span><span class="sxs-lookup"><span data-stu-id="685ee-190">$false: The label isn't a record label.</span></span> <span data-ttu-id="685ee-191">これは既定の値です。</span><span class="sxs-lookup"><span data-stu-id="685ee-191">This is the default value.</span></span>|
|<span data-ttu-id="685ee-192">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="685ee-192">RetentionAction</span></span>|<span data-ttu-id="685ee-193">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-193">String</span></span>|<span data-ttu-id="685ee-194">削除</span><span class="sxs-lookup"><span data-stu-id="685ee-194">Delete</span></span></br><span data-ttu-id="685ee-195">保持</span><span class="sxs-lookup"><span data-stu-id="685ee-195">Keep</span></span></br><span data-ttu-id="685ee-196">KeepAndDelete</span><span class="sxs-lookup"><span data-stu-id="685ee-196">KeepAndDelete</span></span> |
|<span data-ttu-id="685ee-197">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="685ee-197">RetentionDuration</span></span>|<span data-ttu-id="685ee-198">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-198">String</span></span>|<span data-ttu-id="685ee-199">プロパティは、コンテンツを保持する日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="685ee-199">The RetentionDuration parameter specifies the number of days to retain the content.</span></span> <span data-ttu-id="685ee-200">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="685ee-200">Valid values are:</span></span></br><span data-ttu-id="685ee-201">正の整数。</span><span class="sxs-lookup"><span data-stu-id="685ee-201">A positive integer.</span></span></br><span data-ttu-id="685ee-202">値は無制限です。</span><span class="sxs-lookup"><span data-stu-id="685ee-202">The default value is unlimited.</span></span>|
|<span data-ttu-id="685ee-203">RetentionType</span><span class="sxs-lookup"><span data-stu-id="685ee-203">RetentionType</span></span>|<span data-ttu-id="685ee-204">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-204">String</span></span>|<span data-ttu-id="685ee-205">プロパティは、コンテンツ作成日、ラベルが付けられた (タグが付けされた) 日、または最終変更日のいずれから保持期間を計算するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="685ee-205">The RetentionType parameter specifies whether the retention duration is calculated  from the content creation date, tagged date, or last modification date.</span></span> <span data-ttu-id="685ee-206">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="685ee-206">Valid values are:</span></span></br><span data-ttu-id="685ee-207">CreationAgeInDays</span><span class="sxs-lookup"><span data-stu-id="685ee-207">CreationAgeInDays</span></span></br><span data-ttu-id="685ee-208">EventAgeInDays</span><span class="sxs-lookup"><span data-stu-id="685ee-208">EventAgeInDays</span></span></br><span data-ttu-id="685ee-209">ModificationAgeInDays</span><span class="sxs-lookup"><span data-stu-id="685ee-209">ModificationAgeInDays</span></span></br><span data-ttu-id="685ee-210">TaggedAgeInDays</span><span class="sxs-lookup"><span data-stu-id="685ee-210">TaggedAgeInDays</span></span> |
|<span data-ttu-id="685ee-211">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="685ee-211">ReviewerEmail</span></span>|<span data-ttu-id="685ee-212">SmtpAddress[]</span><span class="sxs-lookup"><span data-stu-id="685ee-212">SmtpAddress</span></span>|<span data-ttu-id="685ee-213">プロパティは、Delete および KeepAndDelete の保存期間用アクションのレビュー担当者の電子メール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="685ee-213">The ReviewerEmail parameter specifies the email address of a reviewer for Delete and KeepAndDelete retention actions.</span></span> <span data-ttu-id="685ee-214">複数のメール アドレスをコンマで区切って指定できます。</span><span class="sxs-lookup"><span data-stu-id="685ee-214">You can specify multiple email addresses separated by commas.</span></span>|
|<span data-ttu-id="685ee-215">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="685ee-215">ReferenceId</span></span>|<span data-ttu-id="685ee-216">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-216">String</span></span>|<span data-ttu-id="685ee-217">カスタム</span><span class="sxs-lookup"><span data-stu-id="685ee-217">Custom</span></span>|
|<span data-ttu-id="685ee-218">Departmentname</span><span class="sxs-lookup"><span data-stu-id="685ee-218">Departmentname</span></span>|<span data-ttu-id="685ee-219">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-219">String</span></span>|<span data-ttu-id="685ee-220">カスタム</span><span class="sxs-lookup"><span data-stu-id="685ee-220">Custom</span></span>|
|<span data-ttu-id="685ee-221">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="685ee-221">Category</span></span>|<span data-ttu-id="685ee-222">String</span><span class="sxs-lookup"><span data-stu-id="685ee-222">String</span></span>|<span data-ttu-id="685ee-223">カスタム</span><span class="sxs-lookup"><span data-stu-id="685ee-223">Custom</span></span>|
|<span data-ttu-id="685ee-224">下位カテゴリ</span><span class="sxs-lookup"><span data-stu-id="685ee-224">SubCategory</span></span>|<span data-ttu-id="685ee-225">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-225">String</span></span>|<span data-ttu-id="685ee-226">カスタム</span><span class="sxs-lookup"><span data-stu-id="685ee-226">Custom</span></span>|
|<span data-ttu-id="685ee-227">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="685ee-227">AuthorityType</span></span>|<span data-ttu-id="685ee-228">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-228">String</span></span>|<span data-ttu-id="685ee-229">カスタム</span><span class="sxs-lookup"><span data-stu-id="685ee-229">Custom</span></span>|
|<span data-ttu-id="685ee-230">CitationName</span><span class="sxs-lookup"><span data-stu-id="685ee-230">CitationName</span></span>|<span data-ttu-id="685ee-231">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-231">String</span></span>|<span data-ttu-id="685ee-232">カスタム</span><span class="sxs-lookup"><span data-stu-id="685ee-232">Custom</span></span>|
|<span data-ttu-id="685ee-233">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="685ee-233">CitationUrl</span></span>|<span data-ttu-id="685ee-234">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-234">String</span></span>|<span data-ttu-id="685ee-235">カスタム</span><span class="sxs-lookup"><span data-stu-id="685ee-235">Custom</span></span>|
|<span data-ttu-id="685ee-236">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="685ee-236">CitationJurisdiction</span></span>|<span data-ttu-id="685ee-237">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-237">String</span></span>|<span data-ttu-id="685ee-238">カスタム</span><span class="sxs-lookup"><span data-stu-id="685ee-238">Custom</span></span>|
|<span data-ttu-id="685ee-239">Regulatory</span><span class="sxs-lookup"><span data-stu-id="685ee-239">Regulatory</span></span>|<span data-ttu-id="685ee-240">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-240">String</span></span>|<span data-ttu-id="685ee-241">カスタム</span><span class="sxs-lookup"><span data-stu-id="685ee-241">Custom</span></span>|
|<span data-ttu-id="685ee-242">EventType</span><span class="sxs-lookup"><span data-stu-id="685ee-242">EventType</span></span>|<span data-ttu-id="685ee-243">文字列</span><span class="sxs-lookup"><span data-stu-id="685ee-243">String</span></span>|<span data-ttu-id="685ee-244">このプロパティは、ラベルに関連付けられている保持規則を指定します。</span><span class="sxs-lookup"><span data-stu-id="685ee-244">The 
                EventType
              specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="685ee-245">ルールを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="685ee-245">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="685ee-246">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="685ee-246">For example:</span></span></br><span data-ttu-id="685ee-247">名前</span><span class="sxs-lookup"><span data-stu-id="685ee-247">Name</span></span></br><span data-ttu-id="685ee-248">識別名 (DN)</span><span class="sxs-lookup"><span data-stu-id="685ee-248">Distinguished name (DN)</span></span></br><span data-ttu-id="685ee-249">GUID</span><span class="sxs-lookup"><span data-stu-id="685ee-249">GUID</span></span> </br><span data-ttu-id="685ee-250">使用可能な保持規則を確認するには、[Get-RetentionComplianceRule](https://docs.microsoft.com/ja-JP/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="685ee-250">You can use the [Get-RetentionComplianceRule](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) cmdlet to view the available retention rules.</span></span>|

![情報が入力されたファイル計画テンプレート](media/file-plan-filled-out-template.png)

<span data-ttu-id="685ee-252">入力済みのテンプレートをアップロードすると、ファイル計画マネージャーで記載事項が検証され、インポートの統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="685ee-252">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![ファイル計画のインポートの統計情報](media/file-plan-import-statistics.png)

<span data-ttu-id="685ee-254">検証エラーが発生した場合、ファイル計画のインポートはインポート ファイル内のすべてのエントリを引き続き検証し、インポートファイル内でエラーを参照するラインまたは行の番号を表示し、表示されたエラー結果をコピーます。これにより、簡単にインポートファイル戻り、エラーを修正することができます。</span><span class="sxs-lookup"><span data-stu-id="685ee-254">In the event there is a validation error, file plan import will continue to validate every entry in the import file and display all errors referencing line/row numbers in the import file, copy the displayed error results so that you can easilly return to the import file and correct the errors.</span></span> 

<span data-ttu-id="685ee-255">インポートが完了したらファイル計画マネージャーに戻り、新しい保持ラベルを新規または既存の保持ポリシーと関連付けます。</span><span class="sxs-lookup"><span data-stu-id="685ee-255">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![ラベルを公開するオプション](media/file-plan-publish-labels-option.png)

