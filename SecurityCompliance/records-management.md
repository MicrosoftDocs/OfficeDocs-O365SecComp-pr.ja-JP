---
title: Microsoft 365 のレコードの管理
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
description: Microsoft 365 のレコード管理を使用すると、組織の特定の保持スケジュールをファイル計画に適用し、コンテンツの完全なライフサイクルをサポートするために、保持、レコード宣言、廃棄を管理することができます。
ms.openlocfilehash: f399fbf29c549c3b0cba47f82bdb3b508a3c5819
ms.sourcegitcommit: 7f00f765e8fa674ce1c8c66f5b89b6bea45e13ac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2019
ms.locfileid: "34379215"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="9c8aa-103">Microsoft 365 のレコードの管理</span><span class="sxs-lookup"><span data-stu-id="9c8aa-103">Records management in Microsoft 365</span></span>

<span data-ttu-id="9c8aa-104">すべての種類の組織では、企業データ全体にわたってビジネス、法務および人事のレコードを管理するためにレコード管理ソリューションが必要です。</span><span class="sxs-lookup"><span data-stu-id="9c8aa-104">Organizations of all types require a records-management solution to manage business, legal, and HR records across their corporate data.</span></span> <span data-ttu-id="9c8aa-105">Microsoft 365 のレコード管理は、組織が法的義務を管理できるようにし、規制の遵守を実証する機能を提供します。これにより、ビジネス上、価値がなくなった、または不要になったアイテムを定期的に処分することができて効率が向上します。</span><span class="sxs-lookup"><span data-stu-id="9c8aa-105">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of  items that are no longer of value or no longer required for business purposes.</span></span>

<span data-ttu-id="9c8aa-106">レコード管理ソリューションは、次の要素をサポートします。</span><span class="sxs-lookup"><span data-stu-id="9c8aa-106">The records-management solution supports the following elements:</span></span> 

-   <span data-ttu-id="9c8aa-107">**レコードとしてラベルを使用する**。</span><span class="sxs-lookup"><span data-stu-id="9c8aa-107">**Label as a record**.</span></span> <span data-ttu-id="9c8aa-108">エンド ユーザーによって適用される[レコード ラベル](labels.md#using-retention-labels-for-records-management)を発行するか、特定の機密情報、キーワード、またはコンテンツ種類を含むアイテムに[レコード ラベルを自動適用](labels.md#applying-a-retention-label-automatically-based-on-conditions)します。</span><span class="sxs-lookup"><span data-stu-id="9c8aa-108">Publish [record labels](labels.md#using-retention-labels-for-records-management) to be applied by end users, or [auto-apply record labels](labels.md#applying-a-retention-label-automatically-based-on-conditions) to items containing specific sensitive information, keywords or content types.</span></span>

-   <span data-ttu-id="9c8aa-109">**レコード ラベル内で保持と削除ポリシーを確立する**。</span><span class="sxs-lookup"><span data-stu-id="9c8aa-109">**Establish retention and deletion policies within the record label**.</span></span> <span data-ttu-id="9c8aa-110">[保持](retention-policies.md#retaining-content-for-a-specific-period-of-time)と[廃棄](retention-policies.md#deleting-content-thats-older-than-a-specific-age)の期間は、最終更新日や作成日などのさまざまな要因に基づいて定義します。</span><span class="sxs-lookup"><span data-stu-id="9c8aa-110">Define [retention](retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on a variety of factors including the date last modified or created.</span></span>

-   <span data-ttu-id="9c8aa-111">[イベント ベースの保持](event-driven-retention.md)を使用して**イベント ベースの保持をトリガーする**。</span><span class="sxs-lookup"><span data-stu-id="9c8aa-111">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

-   <span data-ttu-id="9c8aa-112">**ファイル計画を使用して保持計画を移行および管理**し、[ファイル計画マネージャー](file-plan-manager.md)を使用して既存の保持計画を取り込むか、ファイル記述子と階層を展開して新しい計画を構築します。</span><span class="sxs-lookup"><span data-stu-id="9c8aa-112">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

-   <span data-ttu-id="9c8aa-113">[廃棄確認](disposition-reviews.md)を使用して**廃棄を確認および検証する**。</span><span class="sxs-lookup"><span data-stu-id="9c8aa-113">**Review and validate disposition** with [disposition review](disposition-reviews.md).</span></span>

-   <span data-ttu-id="9c8aa-114">**廃棄されたアイテムを廃棄確認で確認**し、 [廃棄レポートをエクスポート](disposition-reviews.md#export-the-disposition-items)し、さらに詳しく検証および報告します。</span><span class="sxs-lookup"><span data-stu-id="9c8aa-114">**Review disposed items with disposition review** and [export a disposition report](disposition-reviews.md#export-the-disposition-items) for further validation and reporting.</span></span>

-   <span data-ttu-id="9c8aa-115">[適切なアクセス権を取得する](permissions-in-the-security-and-compliance-center.md)ために、組織内のレコード管理機能に**特定のアクセス許可**を設定します。</span><span class="sxs-lookup"><span data-stu-id="9c8aa-115">**Set specific permissions** for records manager functions in your organization to [have the right access](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="9c8aa-116">Microsoft 365 のレコード管理ソリューションを使用すると、組織の保持スケジュールをファイル計画に反映し、コンテンツの完全なライフサイクルをサポートするために、保持、レコード宣言、廃棄を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="9c8aa-116">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition in support of the full content lifecycle.</span></span> 
