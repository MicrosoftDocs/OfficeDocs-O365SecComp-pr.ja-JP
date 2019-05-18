---
title: 保留通知の承認
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: eb29ff34d663cf43af4a9a4b1e966a282d16eaf2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151949"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="dae5b-102">保留通知を確認する</span><span class="sxs-lookup"><span data-stu-id="dae5b-102">Acknowledge a hold notification</span></span> 
<span data-ttu-id="dae5b-103">法的な要求または調査に対応する際には、保管担当者に、電子的に保存された情報 (ESI) を保持するように義務を与える必要があります。また、法律上の法的事項に関連する可能性があるすべてのマテリアルを通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae5b-103">When responding to a regulatory request or investigation, you may be required to  inform custodians of their obligation to preserve electronically stored information (ESI) as well as any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="dae5b-104">送信された法律チームは、各保管担当者が受信、読み取り、理解されており、所定の手順に準拠していることを知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae5b-104">Once sent, legal teams must know that each custodian has received, read, and understood, and agreed to comply with the given instructions.</span></span>

<span data-ttu-id="dae5b-105">高度な電子情報開示では、保管担当者を使用してフォローアップする時間、コスト、労力を削減するために、電子メールで法的情報保留通知を送信してフォローアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="dae5b-105">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow-up on legal hold notifications through email.</span></span> <span data-ttu-id="dae5b-106">電子メール通知に加えて、各保管担当者は個別のコンプライアンスポータルにもアクセスできるようになり、保管担当者に義務の状態に対する変更を通知することができます。</span><span class="sxs-lookup"><span data-stu-id="dae5b-106">In addition to email notices, each custodian will also have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="dae5b-107">電子メール通知</span><span class="sxs-lookup"><span data-stu-id="dae5b-107">Email notifications</span></span>
<span data-ttu-id="dae5b-108">法的情報保留通知が発行されると、各保管担当者は、定義された法的情報保留通知および追加の手順を含む固有でパーソナライズされた電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="dae5b-108">Once a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!Tip] 
> <span data-ttu-id="dae5b-109">組み込みの[コミュニケーションエディター](using-communications-editor.md)を使用して、保管担当者が自分の通知を確認したり、電子メールからコンプライアンスポータルに直接アクセスしたりできるようにする方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dae5b-109">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="dae5b-110">法的情報保留通知の構成に基づいて、保管担当者に次の通知が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="dae5b-110">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="dae5b-111">**発行通知**-これは、保管担当者に送信される最初の通知です。</span><span class="sxs-lookup"><span data-stu-id="dae5b-111">**Issuance notice** - This is the first notice sent to your custodian.</span></span> <span data-ttu-id="dae5b-112">これには、発行手順と、メッセージの最後に保留通知が追加されます。</span><span class="sxs-lookup"><span data-stu-id="dae5b-112">This will contain your issuance instructions as well as the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="dae5b-113">**アラーム通知**-有効になっている場合、指定された頻度と間隔に基づいて、保管担当者に通知通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="dae5b-113">**Reminder notice** - If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="dae5b-114">保管担当者が通知を認知するか、または通知の数が不足するまで、アラームは引き続き送信されます。</span><span class="sxs-lookup"><span data-stu-id="dae5b-114">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="dae5b-115">**エスカレーションの通知**-有効になっている場合は、通知が使用された後に、保管担当者および上司にエスカレーション通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="dae5b-115">**Escalation notice** - If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="dae5b-116">Alloted のエスカレーションが完了するか、保管担当者が保留通知を確認するまで、システムはエスカレーション通知を自動的に送信します。</span><span class="sxs-lookup"><span data-stu-id="dae5b-116">The system will automatically send escalation notices until the alloted escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="dae5b-117">**通知の再発行**-調査の途中で、保留通知の内容が更新されると、更新された通知が自動的に保管担当者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="dae5b-117">**Re-issue notice** - During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="dae5b-118">**リリース通知**-保管担当者がケースからリリースされると、リリース通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="dae5b-118">**Release notice** - When a custodian is released from the case, they will be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="dae5b-119">コンプライアンスポータル</span><span class="sxs-lookup"><span data-stu-id="dae5b-119">Compliance Portal</span></span>
<span data-ttu-id="dae5b-120">電子メール通知に加えて、各保管担当者は固有のコンプライアンスポータルにもアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="dae5b-120">In addition to the email notifications, each custodian will also have access to a unique Compliance Portal.</span></span> <span data-ttu-id="dae5b-121">ポータルを通じて、各保管担当者は、アクティブな保留通知を表示、アクセス、および認識できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dae5b-121">Through the portal, each custodian will be able to view, access, and acknowledge their active hold notifications.</span></span>

![保管担当者のコンプライアンスポータル](../media/CustodianPortal.jpg)
