---
title: データ損失防止のレポートの表示
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Office 365 の DLP レポートを使用すると、DLP ポリシーの一致、オーバーライド、誤検知の数をすばやく表示できます。時間の経過と共に、傾向の上下が変化するかどうかを確認します。レポートをさまざまな方法でフィルター処理します。そして、グラフ上の線上の点を選択して詳細を表示します。
ms.openlocfilehash: edca8ad8ae970453e6baf9c1910e17cc62568af5
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077303"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="1bac6-103">データ損失防止のレポートの表示</span><span class="sxs-lookup"><span data-stu-id="1bac6-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="1bac6-104">データ損失防止 (DLP) ポリシーを作成したら、意図したとおりに動作していることを確認し、準拠を維持するための支援を求めることができます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="1bac6-105">Office 365 セキュリティ&amp;コンプライアンスセンターの DLP レポートを使用すると、次のものをすばやく表示できます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-105">With the DLP reports in the Office 365 Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="1bac6-106">**DLP ポリシーの一致**このレポートには、長期間の DLP ポリシーの一致数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="1bac6-107">レポートは、日付、場所、ポリシー、またはアクションによってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="1bac6-108">このレポートを使用して、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="1bac6-109">テストモードで実行するときに、DLP ポリシーを調整または微調整します。</span><span class="sxs-lookup"><span data-stu-id="1bac6-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="1bac6-110">コンテンツに一致する特定のルールを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="1bac6-111">特定の期間に絞り込み、スパイクや傾向の理由を理解します。</span><span class="sxs-lookup"><span data-stu-id="1bac6-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="1bac6-112">組織の DLP ポリシーに違反するビジネスプロセスを検出します。</span><span class="sxs-lookup"><span data-stu-id="1bac6-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="1bac6-113">コンテンツに適用されているアクションを確認することにより、DLP ポリシーのビジネスへの影響を理解します。</span><span class="sxs-lookup"><span data-stu-id="1bac6-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="1bac6-114">特定の DLP ポリシーに関する一致箇所を表示することによって、そのポリシーのコンプライアンス遵守を確認します。</span><span class="sxs-lookup"><span data-stu-id="1bac6-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="1bac6-115">上位ユーザーの一覧を表示し、組織内のインシデントに貢献しているユーザーを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1bac6-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="1bac6-116">組織内の機密情報のトップタイプの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="1bac6-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="1bac6-117">**DLP インシデント**このレポートでは、ポリシーが一致したレポートのように、時間の経過と共に一致するポリシーも表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="1bac6-118">ただし、ポリシーが一致するレポートは、ルールレベルで一致するものを示します。たとえば、電子メールが3つの異なるルールに一致した場合、[ポリシーの一致] レポートに3つの異なる行アイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="1bac6-119">これに対して、インシデントレポートではアイテムレベルで一致が表示されます。たとえば、電子メールが3つの異なるルールに一致した場合、インシデントレポートにはそのコンテンツの1行のアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="1bac6-120">レポート数は異なる方法で集約されるので、特定のルールに一致するものを識別し、DLP ポリシーを微調整するには、ポリシーが一致するレポートが適しています。</span><span class="sxs-lookup"><span data-stu-id="1bac6-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="1bac6-121">インシデントレポートは、DLP ポリシーに問題がある特定のコンテンツを識別するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="1bac6-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="1bac6-122">**DLP 誤検知とオーバーライド**DLP ポリシーでユーザーによる上書きまたは誤検知の報告が許可されている場合、このレポートには、そのようなインスタンスの数が時間の経過とともに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="1bac6-123">レポートは、日付、場所、ポリシーによってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="1bac6-124">このレポートを使用して、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="1bac6-125">多数の誤検知が発生するポリシーを確認して、DLP ポリシーを調整または調整します。</span><span class="sxs-lookup"><span data-stu-id="1bac6-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="1bac6-126">ポリシーを上書きすることで、ユーザーがポリシーヒントを解決したときに送信された妥当性を表示します。</span><span class="sxs-lookup"><span data-stu-id="1bac6-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="1bac6-127">ユーザーオーバーライドの数が多い場合に、DLP ポリシーが有効なビジネスプロセスと競合することを検出します。</span><span class="sxs-lookup"><span data-stu-id="1bac6-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="1bac6-128">すべての DLP レポートでは、過去4か月の期間のデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="1bac6-129">最新のデータは、レポートに表示されるまでに最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="1bac6-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="1bac6-130">これらのレポートは、セキュリティ&amp;コンプライアンスセンター \>の**レポート** \> **ダッシュボード**で見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![DLP ポリシーがレポートに一致する](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="1bac6-132">上書きのためにユーザーによって送信された妥当性を表示する</span><span class="sxs-lookup"><span data-stu-id="1bac6-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="1bac6-133">DLP ポリシーでユーザーによる上書きを許可する場合は、誤検知と上書きレポートを使用して、[ポリシー] ヒントにユーザーが送信したテキストを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![DLP false 正とオーバーライドレポートの詳細にある妥当性フィールド](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="1bac6-135">洞察と推奨事項についてのアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="1bac6-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="1bac6-136">レポートでは、赤の警告アイコンをクリックして潜在的な問題に関する詳細を表示し、問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![インサイトアイコンをクリックすると、詳細と実行されるアクションが表示されます。](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="1bac6-138">DLP レポートのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="1bac6-138">Permissions for DLP reports</span></span>

<span data-ttu-id="1bac6-139">セキュリティ & コンプライアンスセンターで DLP レポートを表示するには、次のものを割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bac6-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="1bac6-140">Exchange 管理センターでの**セキュリティリーダー**の役割。</span><span class="sxs-lookup"><span data-stu-id="1bac6-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="1bac6-141">既定では、この役割は Exchange 管理センターの [組織の管理] および [セキュリティリーダー] 役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="1bac6-142">セキュリティ & コンプライアンスセンターでの**表示のみの DLP コンプライアンス管理**役割。</span><span class="sxs-lookup"><span data-stu-id="1bac6-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="1bac6-143">既定では、この役割は、セキュリティ & コンプライアンスセンターの [コンプライアンス管理者]、[組織の管理]、[セキュリティ管理者]、および [セキュリティリーダー] 役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="1bac6-144">Exchange 管理センターの [**表示のみの受信者**の役割。</span><span class="sxs-lookup"><span data-stu-id="1bac6-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="1bac6-145">既定では、この役割は、Exchange 管理センターの [コンプライアンス管理]、[組織の管理]、および [表示のみ] 組織の管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="1bac6-146">DLP レポートのコマンドレットを検索する</span><span class="sxs-lookup"><span data-stu-id="1bac6-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="1bac6-147">セキュリティ&amp; /コンプライアンスセンターのほとんどのコマンドレットを使用するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bac6-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="1bac6-148">リモート PowerShell を使用して Office 365 セキュリティ/コンプライアンス センターに接続する</span><span class="sxs-lookup"><span data-stu-id="1bac6-148">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="1bac6-149">次のいずれかの[Office 365 &amp;セキュリティコンプライアンスセンターコマンドレット](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)を使用する</span><span class="sxs-lookup"><span data-stu-id="1bac6-149">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="1bac6-150">ただし、DLP レポートには、Exchange Online などの Office 365 間でデータをプルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bac6-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="1bac6-151">このため、DLP レポートのコマンドレットは、セキュリティ&amp;コンプライアンスセンターの powershell ではなく、Exchange Online の powershell で利用できます。</span><span class="sxs-lookup"><span data-stu-id="1bac6-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="1bac6-152">そのため、DLP レポートのコマンドレットを使用するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bac6-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="1bac6-153">Connect to Exchange Online using remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bac6-153">Connect to Exchange Online using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="1bac6-154">次のいずれかのコマンドレットを DLP レポートに使用します。</span><span class="sxs-lookup"><span data-stu-id="1bac6-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="1bac6-155">Get-dlpdetectionsreport</span><span class="sxs-lookup"><span data-stu-id="1bac6-155">Get-DlpDetectionsReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [<span data-ttu-id="1bac6-156">取得-Dlpのレポート</span><span class="sxs-lookup"><span data-stu-id="1bac6-156">Get-DlpDetailReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

