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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 538fd7e67456bc669b9f5cf140c995a716239fc2
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240989"
---
# <a name="work-with-custodians-in-advanced-ediscovery-preview"></a><span data-ttu-id="fd7ba-102">Advanced eDiscovery で保管担当者を操作する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="fd7ba-102">Work with custodians in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="fd7ba-103">組織が法的調査に応答している場合、関連性のある可能性のあるコンテンツを特定、保存、および収集するワークフローは、組織内のユーザーやデータ保管担当者に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="fd7ba-103">When an organization is responding to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based off people or data custodians within their organization.</span></span> <span data-ttu-id="fd7ba-104">電子情報開示では、これらの個人は*data 保管担当者*(または*保管担当者*と呼ばれます) と呼ばれ、"ドキュメントまたは電子ファイルの管理者制御を持つ人" として定義されています。</span><span class="sxs-lookup"><span data-stu-id="fd7ba-104">In eDiscovery, these individuals are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file.</span></span> <span data-ttu-id="fd7ba-105">たとえば、電子メールメッセージの保管担当者は、関連するメッセージが含まれるメールボックスの所有者である場合があります。</span><span class="sxs-lookup"><span data-stu-id="fd7ba-105">For example, the custodian of an email message could be the owner of the mailbox which contains the relevant message.</span></span>  

<span data-ttu-id="fd7ba-106">調査の開始時に、電子情報開示チームは、ケースに関連するすべての関連保管担当者とデータソースを迅速に特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd7ba-106">When an investigation begins, the eDiscovery team must quickly identify all the relevant custodians and data sources related to the case.</span></span> <span data-ttu-id="fd7ba-107">時間の経過と共に、保管担当者のリストとそのデータソースが増加または decreasse ことがあります。</span><span class="sxs-lookup"><span data-stu-id="fd7ba-107">Over time, the list of custodians and their data sources may increase or decreasse.</span></span> <span data-ttu-id="fd7ba-108">その結果、組織は、ケースのライフサイクルを通じて、custodial コンテンツを識別、保持、および収集するための制御されたプロセスを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd7ba-108">As a result, organizations must maintain a controlled process around identifying, preserving, and collecting custodial content throughout the life cycle of a case.</span></span>

<span data-ttu-id="fd7ba-109">高度な電子情報開示 (プレビュー) ケースでは、法務部門が組織内の個人を保管担当者として追加し、Exchange メールボックス、OneDrive アカウント、SharePoint、teams サイトなどの custodial データソースを自動的に識別して保存することができます。</span><span class="sxs-lookup"><span data-stu-id="fd7ba-109">Within an Advanced eDiscovery (Preview) case, legal teams can add individuals in their organization as custodians and automatically identify and preserve custodial data sources such as Exchange mailboxes, OneDrive accounts, and SharePoint and Teams sites.</span></span> <span data-ttu-id="fd7ba-110">高度な電子情報開示 (プレビュー) の組み込みの保管担当者管理ツールを使用することにより、組織は不注意 (または故意に) 削除から電子的に保存された情報をセキュリティで保護することができます。工程.</span><span class="sxs-lookup"><span data-stu-id="fd7ba-110">By using the built-in custodian management tool in Advanced eDiscovery (Preview), organizations can secure electronically stored information from inadvertent (or intentional) deletion and say goodbye to manual, time consuming, and error-prone legal hold processes.</span></span> 

<span data-ttu-id="fd7ba-111">保管担当者の使用の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd7ba-111">For more information about working with custodians, see the following articles:</span></span> 

- [<span data-ttu-id="fd7ba-112">ケースにカストディアンを追加する</span><span class="sxs-lookup"><span data-stu-id="fd7ba-112">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="fd7ba-113">ケースで保管担当者を管理する</span><span class="sxs-lookup"><span data-stu-id="fd7ba-113">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="fd7ba-114">カストディアンのアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="fd7ba-114">View custodian activity</span></span>](view-custodian-activity.md)

## <a name="roles-and-permissions"></a><span data-ttu-id="fd7ba-115">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="fd7ba-115">Roles and permissions</span></span>

<span data-ttu-id="fd7ba-116">advanced ediscovery (プレビュー) では、組み込みの電子情報開示マネージャーの役割グループを使用して、ユーザーが高度な電子情報開示 (プレビュー) でエンドツーエンドのワークフローを管理できるように、必要なアクセス許可をユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fd7ba-116">In Advanced eDiscovery (Preview), you can use the built-in eDiscovery Manager role group to assign the necessary permissions to users so they can manage the end-to-end workflow in Advanced eDiscovery (Preview).</span></span>
