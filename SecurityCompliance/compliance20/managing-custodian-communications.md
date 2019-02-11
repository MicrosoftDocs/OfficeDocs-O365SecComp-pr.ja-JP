---
title: 通信の高度な電子的証拠開示 (プレビュー) を使用します。
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
description: ''
ms.openlocfilehash: 962bd13f66ec8fe4f3385656f1241dd5fb5c4dcf
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695043"
---
# <a name="work-with-communications-in-advanced-ediscovery-preview"></a><span data-ttu-id="4b2ba-102">通信の高度な電子的証拠開示 (プレビュー) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-102">Work with communications in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="4b2ba-p101">高度な電子的証拠開示 (プレビュー) には、追跡し、法的保持義務通告の配布のプロセスを簡略化するのには法務部門が使用できます。保管担当者の通信機能では、法律の部門を管理し、通知、アラーム、およびエスカレーション - すべて 1 つの場所にから--の全体の法的保持義務プロセスを自動化するを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-p101">Advanced eDiscovery (Preview) allows legal departments to simplify their processes around tracking and distributing legal hold notifications. The custodian communications feature enables legal departments to manage and automate their entire legal hold processes--from notifications, reminders, and escalations--all in one place.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="4b2ba-105">法的保存要件の通知とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-105">What is a legal hold notification?</span></span>

<span data-ttu-id="4b2ba-p102">法的保持義務 (とも呼ばれます*を保持する訴訟*) には、従業員、臨時社員、またはその他のデータの通告を組織の法務部門から送信される通知です。これらの通知は、アクティブなまたは緊急の法的事項に関連する可能性のあるすべての材料と同様に電子的に保存されている情報 (ESI) を保持するために通告を指示します。法務部門は、各管理者が受信、読み取りと理解し、同意与えられた指示を遵守する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-p102">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or other data custodians. These notifications instruct custodians to preserve electronically stored information (ESI) as well as any material that may be relevant to an active or imminent legal matter. Legal teams must know that each custodian has received, read, and understood, and agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="4b2ba-109">法的通知の処理を保持します。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-109">The legal hold notification process</span></span>

<span data-ttu-id="4b2ba-p103">組織には、差し迫った訴訟や規制の調査について学習することと、関連する情報を保持する義務があります。保持要件を遵守するために組織は潜在的な通告をに関する関連情報を保持するために、関税すぐに知らせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-p103">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation. In order to comply with its preservation requirements, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span> 

<span data-ttu-id="4b2ba-p104">高度な電子的証拠開示 (プレビュー) を持つ法務部門が作成し、法的保存要件の通知ワークフローをカスタマイズできます。保管担当者の通信機能には、以下の通知およびワークフローを構成するのには法務部門ができます。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-p104">With Advanced eDiscovery (Preview), legal teams can create and customize their legal hold notification workflow. The Custodian Communications feature allows legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="4b2ba-p105">**発行に注意してください**: 法的保持義務通告が発行された (または開始) ケースの問題の関連情報がある通告する法務部門からの通知をします。この通知は、証拠開示のために必要となるすべての情報を保持するためにそれらの通告を指示します。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-p105">**Issuance notice**: A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who might have relevant information about the case matter. This notice instructs those custodians to preserve any information that might be needed for discovery.</span></span> 
   
2.  <span data-ttu-id="4b2ba-p106">**再発行に注意してください**: 場合は、中に通告を追加を保持する必要がありますかよりも情報量が以前に指示します。このシナリオでは、既存の保留中の通知を更新し、通告することを再実行できます。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-p106">**Re-Issuance notice**: During a case, custodians may be required to preserve additional or less information than was previously instructed. For this scenario, you can update the existing hold notice and re-issue it to your custodians.</span></span>

3.  <span data-ttu-id="4b2ba-p107">**リリースに注意してください**: 書を解放できるように、情報が不要になった保存不要な場合問題が解決され、書は、不要になった情報保持義務。さらに、管理者に通知されますが不要になった保護関税の下とその活動を再開する方法については未解決であります。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-p107">**Release notice**: Once a matter is resolved and the custodian is no longer subject to a preservation duty, the custodian can be released so that information is no longer retained if not needed. In addition, your custodian will be notified that they are no longer under preservation duty and with outstanding instructions on how to resume their activity.</span></span>

4. <span data-ttu-id="4b2ba-p108">**アラームとエスカレーション**: 場合によっては、通知を発行した十分ではありません法的証拠開示の要件を満たすためにします。各通知は、法務部門は一連の応答を停止の通告をフォロー アップのために自動的にアラームとエスカレーションのワークフローをスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-p108">**Reminders and escalations**: In some instances, just issuing a notice is not enough to satisfy legal discovery requirements. With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow-up with unresponsive custodians.</span></span>

    - <span data-ttu-id="4b2ba-122">**アラーム**: 組織は、応答を停止の通告を通知するアラームを設定可能性があります法的保持義務通告を発行または一連の通告を再発行すると、します。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-122">**Reminders**:  After a legal hold notice has been issued or re-issued to a set of custodians, an organization may set up reminders to alert unresponsive custodians.</span></span> 

    - <span data-ttu-id="4b2ba-123">**エスカレーション**: 場合によっては、アラームをセットした後でも、管理者が応答しない場合法務チーム ワークフローを設定、エスカレーション、保管担当者とその管理者に通知します。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-123">**Escalations**: In some cases, if a custodian remains unresponsive even after a set of reminders, the legal team can set up an escalation workflow to notify the custodian and his/her manager.</span></span>

## <a name="role-groups-and-permissions"></a><span data-ttu-id="4b2ba-124">役割グループおよびアクセス許可</span><span class="sxs-lookup"><span data-stu-id="4b2ba-124">Role groups and permissions</span></span> 

<span data-ttu-id="4b2ba-125">法務部門では、制御でき、セキュリティ & コンプライアンス センターでの役割を電子的証拠開示に関連するグループとアクセス許可を使用して、サポート ・ リクエストの活動をセグメント化することができます。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-125">Legal teams can control and segment their case activity using eDiscovery-related role groups and permissions in the Security & Compliance Center.</span></span> 

<span data-ttu-id="4b2ba-126">作成し、法的保持義務通告の管理、ユーザーは次のような役割グループの一部をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-126">To create and manage legal hold notifications, a user must be part of the following role groups:</span></span>

- <span data-ttu-id="4b2ba-p109">**電子的証拠開示マネージャー**がこの役割グループのメンバーでは、作成でき、電子的証拠開示のサポート案件を管理することができます。追加および削除するメンバー、通告を配置し、上のコンテンツの場所を保持、法的保持義務通告を管理、作成しサポート案件に関連付けられているコンテンツの検索を編集、コンテンツ検索の結果をエクスポート、および検索結果の詳細に分析の準備(プレビュー) を電子的証拠開示します。このロール グループに 2 つのサブグループがあります。次の内容の違いは、スコープに基づきます。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-p109">**eDiscovery Manager** - Members of this role group can create and manage eDiscovery cases. They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit Content Searches associated with a case, export the results of a Content Search, and prepare search results for analysis in Advanced eDiscovery (Preview). There are two sub-groups in this role group. The difference between these subgroups is based on scope.</span></span>

  - <span data-ttu-id="4b2ba-p110">**電子的証拠開示マネージャー**には、表示し、それらを作成またはのメンバーは、電子的証拠開示のサポート案件を管理できます。別の電子的証拠開示マネージャー サポート案件を作成する場合のメンバーとして、2 つ目電子的証拠開示マネージャーが追加されない場合は、2 つ目の電子証拠開示マネージャーを表示またはセキュリティ & コンプライアンス センターで電子的証拠開示のページで、大文字と小文字を開くことはできません。電子的証拠開示マネージャーは、高度な電子的証拠開示分析タスクを実行するには、(プレビュー) で、大文字と小文字にもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-p110">**eDiscovery Manager** - Can view and manage the eDiscovery cases they create or are a member of. If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the eDiscovery page in the Security & Compliance Center. eDiscovery Managers can also access their cases in Advanced eDiscovery (Preview) to perform analysis tasks.</span></span>

  - <span data-ttu-id="4b2ba-p111">**管理者の電子的証拠開示**では、電子的証拠開示マネージャーが実行できるすべてのサポート案件の管理タスクを実行できます。さらに、電子的証拠開示管理者では次のことができます。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-p111">**eDiscovery Administrator** - Can perform all case management tasks that an eDiscovery Manager can do. Additionally, an eDiscovery Administrator can:</span></span>
    
    - <span data-ttu-id="4b2ba-136">[電子情報開示] ページに一覧表示されたすべてのケースの表示。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-136">View all cases that are listed on the eDiscovery page.</span></span>
    - <span data-ttu-id="4b2ba-137">大文字と小文字のメンバーとして自分自身を追加した後は、いかなる場合においても、組織内を管理します。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-137">Manage any case in the organization after they add themselves as a member of the case.</span></span>
    - <span data-ttu-id="4b2ba-138">高度な電子的証拠開示 (プレビュー)、組織内のすべてのケースでのケース ・ データにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-138">Access case data in Advanced eDiscovery (Preview) for any case in the organization.</span></span>

<span data-ttu-id="4b2ba-139">詳細については、 [Office 365 のセキュリティ & コンプライアンス センターでの電子的証拠開示のアクセス許可を割り当てる](../assign-ediscovery-permissions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b2ba-139">For more information, see [Assign eDiscovery permissions in the Office 365 Security & Compliance Center](../assign-ediscovery-permissions.md).</span></span>