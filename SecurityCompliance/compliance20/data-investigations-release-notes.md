---
title: Microsoft 365 のデータ調査 (プレビュー) のリリース ノート
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: この資料では、高度な電子的証拠開示 (プレビュー) Microsoft 365 での新しいバージョンについて説明します。
ms.openlocfilehash: bcf10f5154723709b1cde761b0e8d02540341a26
ms.sourcegitcommit: 98ec28932ae20e848f9f489c3c78e4a7edab6d18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "29636629"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a><span data-ttu-id="f5043-103">Microsoft 365 のデータ調査 (プレビュー) のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="f5043-103">Release notes for Data Investigations (Preview) in Microsoft 365</span></span>

<span data-ttu-id="f5043-p101">新しいデータ調査 (プレビュー) ツールを使用することで優先順位を決定、調査、およびデータを修正する Microsoft 365 で関連する問題により、データのこぼした事故や内部調査など。パブリック プレビューのデータの調査は、今後の機能と更新プログラムの早期アクセスを提供します。最新機能への初期のアクセスを取得するには、Office 365 のセキュリティ & コンプライアンス センターでデータ調査 (プレビュー) で新しい調査を作成します。学習する方法については、[マイクロソフトの 365 のデータのこぼしたインシデントを管理する](manage-data-spillage-incidents.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5043-p101">You can use the new Data Investigations (Preview) tool in in Microsoft 365 to triage, investigate, and remediate data related incidents, such as a data spillage incident or an internal investigation. The Public Preview of Data investigations provides you with early access to the upcoming functionality and updates. To get early access to the newest features, create a new investigation in Data investigations (Preview) in the Office 365 Security & Compliance Center. To learn how, see [Managing a data spillage incident in Microsoft 365](manage-data-spillage-incidents.md).</span></span>

## <a name="whats-new"></a><span data-ttu-id="f5043-108">新機能</span><span class="sxs-lookup"><span data-stu-id="f5043-108">What’s new</span></span> 

- <span data-ttu-id="f5043-p102">**調査**の調査を作成することで検索し、インシデントをグループ化できます。追加またはメンバーを削除して、調査にアクセスできるユーザーを管理します。 選択でき、お気に入りの調査をマークできます。追跡とモニター活動内で、新しいダッシュ ボードを使用して調査の間でです。調査を完了したら、閉じるまたは削除できます。</span><span class="sxs-lookup"><span data-stu-id="f5043-p102">**Investigations** - You can group searches and incidents by creating an investigation. Manage who can access the investigation by adding or removing members.  You can also select and mark your favorite investigations. Track and monitor activity within and across investigations using new dashboards. After you complete your investigation, you can close or delete it.</span></span>

- <span data-ttu-id="f5043-p103">**目的の人**を調査対象のユーザーとしてユーザーを追加するときに、自分のメールボックスでは、ビジネス アカウント、およびマイクロソフトのチーム サイトの OneDrive を表示できます。調査コンテンツ検索の範囲を使用できます。目的の人物をさらに調査するには、表示することも Office 365 とその他の Microsoft サービスで、活動に関連するレコードを監査します。</span><span class="sxs-lookup"><span data-stu-id="f5043-p103">**People of interest** – When you add users to investigations as people of interest, you can see their mailbox, OneDrive for Business account, and Microsoft Teams sites. You can use them to scope your investigative content searches. To further investigate a person of interest, you can also view audit records related to their activities in Office 365 and other Microsoft services.</span></span>

- <span data-ttu-id="f5043-p104">**検索**: 作成のさまざまなを使用して組織全体の検索条件を検索します。ユーザーまたはサイトを検索する場合は、これを行う人や、検索の作成ウィザードでサイトの場所を指定するとそれらのユーザーを追加することによって。</span><span class="sxs-lookup"><span data-stu-id="f5043-p104">**Searches** – Create a organization-wide search using various search condition. If you know users or sites that you want to search, you can do so by adding those users as people of interest or specifying site locations in search creation wizard.</span></span> 

- <span data-ttu-id="f5043-p105">**事故**– は、新しいインシデントを作成し、検索結果を確認するを追加します。個々 のドキュメントを確認し、調査のノートに注釈を別の環境に移動する結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="f5043-p105">**Incidents** – Create a new incident and add search results that you want to review. You can review individual documents, annotate to leave investigation notes, and export results to move to a different environment.</span></span> 

- <span data-ttu-id="f5043-p106">**確認**– インシデントに追加のドキュメントを確認するには、ネイティブを使用、テキスト、およびネイティブに近い表示します。重複、電子メールのスレッド、およびインシデントのレビューを支援することができます、テーマによって項目をグループ化するドキュメントを分析機能を適用することも。</span><span class="sxs-lookup"><span data-stu-id="f5043-p106">**Review** – Use a native, text, and near-native view to review the documents added to an incident. You can also apply analytics to documents to group items by duplicates, email threads, and themes, which can help assist your review of the incident.</span></span> 

- <span data-ttu-id="f5043-123">**Redact、タグ、および注釈を付ける**: テキストを墨消し、タグ、およびドキュメントを参照するようにコメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="f5043-123">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="f5043-124">**高度なインデックスの作成**: 部分的にインデックス付きの項目がある場合、されます要求時に再インデックス付けされたすべてのデータを検索に使用できるように。</span><span class="sxs-lookup"><span data-stu-id="f5043-124">**Deep indexing** – If there are any partially indexed items, they will be re-indexed on demand so that all data will be available for searching.</span></span>

- <span data-ttu-id="f5043-p107">**エラーの修復**– Remediate またはダウンロードのエラーを処理します。大規模なファイルの種類の修復のサポートが含まれます、ファイル、およびエラーのインデックス作成に関連するその他の問題、パスワード保護されています。</span><span class="sxs-lookup"><span data-stu-id="f5043-p107">**Error remediation** – Remediate or download processing errors. This includes remediation support for large file types, password protected files, and other issues related to indexing errors.</span></span> 

- <span data-ttu-id="f5043-127">**ジョブ**: 長時間実行されるプロセスの状態を追跡します。</span><span class="sxs-lookup"><span data-stu-id="f5043-127">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="f5043-p108">**ハード削除のメールボックス アイテム**の緊急の状況でする必要があります正しく配置されなかったアイテムを削除します。これを行うには、実行することができます、**新規 ComplianceSearchAction-PurgeType - HardDelete を削除**セキュリティ & のメールボックスからアイテムを完全に削除するのにはコンプライアンス中心の PowerShell のコマンドです。詳細については、[新規 ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5043-p108">**Hard-delete mailbox items** - In urgent situations, you might need to permanently delete misplaced items. To do this, you can run the **New-ComplianceSearchAction -Purge -PurgeType HardDelete** command in Security & Compliance Center PowerShell to permanently remove items from mailboxes. For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction).</span></span>
