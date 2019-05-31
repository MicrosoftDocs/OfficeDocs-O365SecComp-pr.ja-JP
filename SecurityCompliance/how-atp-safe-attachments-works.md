---
title: Office 365 の ATP の安全な添付ファイルの動作
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: '[安全な添付ファイル] 機能を使用すると、電子メールの添付ファイルの確認時間を確認できます。 安全な添付ファイルを使用して、ユーザーが電子メールで送受信する悪意のあるファイルから組織を保護します。'
ms.openlocfilehash: 99d31e327343971f6a7630e2a43ffd3044fbf976
ms.sourcegitcommit: 424a614141c1f19a1c84a67ec2d71dd3d7ef6694
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "34592267"
---
# <a name="how-ffice-365-atp-safe-attachments-works"></a><span data-ttu-id="bd8ca-104">Ffice> office 365 の ATP の安全な添付ファイルの動作方法</span><span class="sxs-lookup"><span data-stu-id="bd8ca-104">How ffice 365 ATP Safe Attachments works</span></span>

## <a name="how-it-works"></a><span data-ttu-id="bd8ca-105">メカニズム</span><span class="sxs-lookup"><span data-stu-id="bd8ca-105">How it works</span></span>

<span data-ttu-id="bd8ca-106">ATP の安全な添付ファイル機能は、組織内のユーザーの電子メールの添付ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-106">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="bd8ca-107">ATP の安全な添付ファイルポリシーが設定されている場合に、そのポリシーの対象となるユーザーが Office 365 で電子メールを表示すると、そのメール添付ファイルがチェックされ、ATP の安全な添付ファイルのポリシーに基づいて適切な操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-107">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="bd8ca-108">ポリシーの定義によっては、悪意のあるファイルが送信されたことを知らなくても、ユーザーは作業を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-108">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="bd8ca-109">次に、作業中の ATP の安全な添付ファイルの2つの例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-109">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="bd8ca-110">**例 1: 電子メールの添付ファイル**Lee が添付ファイル付きの電子メールメッセージを受信するとします。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-110">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="bd8ca-111">Lee のユーザー資格情報を盗もうとするように設計されたマルウェアが安全か実際に添付されているかは、Lee では明白ではありません。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-111">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="bd8ca-112">Lee の組織では、セキュリティ管理者が ATP の安全な添付ファイルポリシーを数日前に定義しています。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-112">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="bd8ca-113">ATP の安全な添付ファイル機能を使用すると、Lee が受信する前に、仮想環境で電子メール添付ファイルが開かれ、テストされます。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-113">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="bd8ca-114">添付ファイルが悪意があると判断された場合は、自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-114">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="bd8ca-115">添付ファイルが安全な場合は、Lee がクリックしたときに正常に開かれます。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-115">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="bd8ca-116">**例 2: SharePoint Online のファイル**田中がファイルを受信し、SharePoint Online のライブラリにアップロードしたとします。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-116">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="bd8ca-117">田中は、ファイルが実際に悪意があることを知らずに、そのファイルへのリンクを他のチームと共有します。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-117">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="bd8ca-118">幸いなことに、 [SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)は、悪意のあるファイルを検出してブロックしています。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-118">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="bd8ca-119">数日後に、Chris はドキュメントを開きます。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-119">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="bd8ca-120">Chris はファイルを見ることはできますが、そのファイルを開いたり共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-120">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="bd8ca-121">ATP の安全な添付ファイルポリシーは、組織内の特定のユーザーやグループ、またはドメイン全体に適用できます。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-121">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="bd8ca-122">また、ATP の安全な添付ファイルのポリシーでは、実際の添付ファイルがスキャンされている間は、プレースホルダーの添付ファイルを使用するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-122">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="bd8ca-123">詳細については、「 **[Office 365 で ATP の安全な添付ファイルのポリシーを設定](set-up-atp-safe-attachments-policies.md)** する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-123">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="bd8ca-124">ATP の安全な添付ファイルのスキャンは、Office 365 データが存在する地域と同じ地域で行われます。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-124">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides.</span></span> <span data-ttu-id="bd8ca-125">データセンター地理の詳細については、「[データの保存場所](https://products.office.com/where-is-your-data-located?geo=All)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8ca-125">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

