---
title: Advanced eDiscovery で保管担当者を操作する (プレビュー)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 933dfafb0f103f072966cb7ae455ba3a977ae03f
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218187"
---
# <a name="work-with-custodians-in-advanced-ediscovery-preview"></a><span data-ttu-id="bbf17-102">Advanced eDiscovery で保管担当者を操作する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="bbf17-102">Work with custodians in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="bbf17-p101">組織が法的調査に応答している場合は、組織内のユーザーまたはデータ保管担当者に基づいて、潜在的な関連コンテンツを特定、保存、および収集するワークフローが、多くの場合、組織内の人物またはデータのに基づいています。電子情報開示では、これらの個人は data 保管担当者と呼ばれ、"ドキュメントまたは電子ファイルの管理制御を持つユーザー" として定義されています。たとえば、電子メールのデータ保管担当者は、関連するメッセージが含まれるメールボックスの所有者である場合があります。</span><span class="sxs-lookup"><span data-stu-id="bbf17-p101">Often, when an organization is responding to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based off people or data custodians within their organization. In eDiscovery, these individuals are called data custodians and are defined as “persons having administrative control of a document or electronic file”. For example, the data custodian of an email could be the owner of the mailbox which contains the relevant message.</span></span>  

<span data-ttu-id="bbf17-p102">調査の開始時に、電子情報開示チームは、ケースに関連するすべての関連保管担当者とデータソースを迅速に特定する必要があります。時間の経過とともに、保管担当者のリストとそのデータソースが拡張または契約する可能性があります。その結果、組織は、ケースのライフサイクルを通じて、custodial コンテンツを識別、保持、収集するための制御されたプロセスを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbf17-p102">When an investigation begins, the eDiscovery team must quickly identify all the relevant custodians and data sources related to the case. Over time, the lists of custodians and their data sources may expand or contract. As a result, organizations must maintain a controlled process around identifying, preserving, and collecting custodial content throughout the lifecycle of a case.</span></span>

<span data-ttu-id="bbf17-p103">高度な電子情報開示 (プレビュー) ケースでは、法務部門が組織内の個人をデータ保管担当者として追加し、Exchange、OneDrive、SharePoint、teams サイトなどの custodial ソースを自動的に識別して保存することができます。組み込みの保管担当者管理ツールを使用することにより、組織は電子的に保存された情報 (ESI) を不注意による削除から保護することができます。また、手動、時間がかかる、エラーが発生する可能性のある法的な保留プロセスを中止することができます。</span><span class="sxs-lookup"><span data-stu-id="bbf17-p103">Within an Advanced eDiscovery (Preview) case, legal teams can add individuals within their organization as data custodians and automatically identify and preserve custodial sources such as Exchange, OneDrive, SharePoint, and Teams sites. By using the built-in and in-place Custodian Management tool, organizations can secure electronically stored information (ESI) from inadvertent deletion and say goodbye to manual, time consuming, and error-prone legal hold processes.</span></span> 

<span data-ttu-id="bbf17-111">保管担当者の使用の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbf17-111">For more information about working with custodians, see the following articles:</span></span> 

- [<span data-ttu-id="bbf17-112">ケースにカストディアンを追加する</span><span class="sxs-lookup"><span data-stu-id="bbf17-112">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="bbf17-113">ケースで保管担当者を管理する</span><span class="sxs-lookup"><span data-stu-id="bbf17-113">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="bbf17-114">カストディアンのアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="bbf17-114">View custodian activity</span></span>](view-custodian-activity.md)

## <a name="roles-and-permissions"></a><span data-ttu-id="bbf17-115">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="bbf17-115">Roles and permissions</span></span>

<span data-ttu-id="bbf17-116">advanced ediscovery (プレビュー) では、組み込みの電子情報開示マネージャーの役割グループを使用して、ユーザーが高度な電子情報開示 (プレビュー) でエンドツーエンドのワークフローを管理できるように、必要なアクセス許可をユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bbf17-116">In Advanced eDiscovery (Preview), you can use the built-in eDiscovery Manager role group to assign the necessary permissions to users so they can manage the end-to-end workflow in Advanced eDiscovery (Preview).</span></span>
