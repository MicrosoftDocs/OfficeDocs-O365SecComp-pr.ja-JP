---
title: データ損失防止のレポートの表示
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 41eb4324-c513-4fa5-91c8-8fbd8aaba83b
description: Office 365 の DLP レポートには、DLP ポリシーと一致する、オーバーライド、または誤検知の数をすばやく表示できます。かどうかにして上下に一定期間の傾向; を参照してください。レポートをフィルター処理の方法は異なります。グラフの線の点を選択して詳細情報を表示します。
ms.openlocfilehash: 379e66fc3f2611cf338739d030c2b1d48e7416d8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013911"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="fc917-103">データ損失防止のレポートの表示</span><span class="sxs-lookup"><span data-stu-id="fc917-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="fc917-p101">データ損失防止 (DLP) ポリシーを作成したら、準拠を維持することを目的とするとして機能していることを確認します。Office 365 のセキュリティ、DLP でのレポート&amp;コンプライアンス センターでは、すばやく表示できます。</span><span class="sxs-lookup"><span data-stu-id="fc917-p101">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant. With the DLP reports in the Office 365 Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="fc917-p102">**DLP ポリシーに一致します。** このレポートでは、時間の経過と共に DLP ポリシーの一致の数を示します。日付、場所、ポリシー、またはアクションによって、レポートをフィルター処理できます。このレポートを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fc917-p102">**DLP policy matches** This report shows the count of DLP policy matches over time. You can filter the report by date, location, policy, or action. You can use this report to:</span></span> 
    
  - <span data-ttu-id="fc917-p103">調整またはテスト モードで実行すると、DLP ポリシーを調整します。コンテンツに一致する特定のルールを表示します。</span><span class="sxs-lookup"><span data-stu-id="fc917-p103">Tune or refine your DLP policies as you run them in test mode. You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="fc917-111">特定の期間に絞り込み、スパイクや傾向の理由を理解します。</span><span class="sxs-lookup"><span data-stu-id="fc917-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="fc917-112">組織の DLP ポリシーに違反するビジネス ・ プロセスを検出します。</span><span class="sxs-lookup"><span data-stu-id="fc917-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="fc917-113">DLP ポリシーのビジネスへの影響を理解するには、どのようなアクションは、コンテンツに適用されているかを確認します。</span><span class="sxs-lookup"><span data-stu-id="fc917-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="fc917-114">特定の DLP ポリシーに関する一致箇所を表示することによって、そのポリシーのコンプライアンス遵守を確認します。</span><span class="sxs-lookup"><span data-stu-id="fc917-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="fc917-115">最上位ユーザーの一覧を表示し、組織内の問題に影響を与えているユーザーを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="fc917-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="fc917-116">組織内の機密情報の最上位の型の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="fc917-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="fc917-p104">**DLP インシデント**このレポートは、レポートがポリシーに一致するようにもポリシーと一致すると時間の経過と共に示します。ただし、ポリシーは、ルール レベルでのレポート表示の一致に一致します。などの電子メールには、次の 3 つの異なる規則が一致すると、ポリシーは、レポートに示す 3 つ別の品目を検索します。インシデント レポートが一致するものを示していますこれに対し、項目レベルでは。たとえば、電子メールには、次の 3 つの異なる規則が一致すると、インシデント レポートは、コンテンツの部分の 1 つの行項目を示します。</span><span class="sxs-lookup"><span data-stu-id="fc917-p104">**DLP incidents** This report also shows policy matches over time, like the policy matches report. However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items. By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="fc917-p105">レポート数の集計方法が異なる、ためポリシーと一致するレポートをお勧めの特定の規則と一致するものを識別して、DLP ポリシーを調整します。インシデント レポートは、DLP ポリシーの問題のあるコンテンツの特定の要素を識別するため勧めします。</span><span class="sxs-lookup"><span data-stu-id="fc917-p105">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies. The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="fc917-p106">**DLP 誤とオーバーライド**DLP ポリシーは、このメソッドをオーバーライドまたは誤検出を報告するユーザーを許可している場合、このレポートは、時間の経過と共にこのようなインスタンスの数を示します。日付、場所、またはポリシーによって、レポートをフィルター処理できます。このレポートを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fc917-p106">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time. You can filter the report by date, location, or policy. You can use this report to:</span></span> 
    
  - <span data-ttu-id="fc917-125">DLP ポリシーを調整するには、多数の誤検知が発生するポリシーを表示を調整します。</span><span class="sxs-lookup"><span data-stu-id="fc917-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="fc917-126">ポリシーをオーバーライドすることによってポリシーのヒントを解決するときにユーザーによって送信された妥当性を表示します。</span><span class="sxs-lookup"><span data-stu-id="fc917-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="fc917-127">ユーザーの数が多いを負うことによって有効なビジネス プロセスと DLP ポリシーの競合をオーバーライドを検出します。</span><span class="sxs-lookup"><span data-stu-id="fc917-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="fc917-p107">DLP のすべてのレポートには、4 か月までの時間は、最新のデータを表示できます。最新のデータは、レポートに表示するのには最大 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="fc917-p107">All DLP reports can show data from the most recent four-month time period. The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="fc917-130">セキュリティのこれらのレポートを見つけることができます&amp;コンプライアンス センター \> **レポート** \> **ダッシュ ボード**です。</span><span class="sxs-lookup"><span data-stu-id="fc917-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![DLP ポリシーに一致するレポート](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="fc917-132">オーバーライドするためのユーザから送信された理由を表示します。</span><span class="sxs-lookup"><span data-stu-id="fc917-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="fc917-133">DLP ポリシーは、ユーザーが上書きすることを許可している場合誤検出を使用してポリシーのヒント内のユーザーによって送信されたテキストを表示するレポートを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="fc917-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![妥当性は、DLP の誤検知の詳細のフィールドし、レポートを上書き](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="fc917-135">情報と推奨事項に対処します。</span><span class="sxs-lookup"><span data-stu-id="fc917-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="fc917-136">レポートは、情報および推奨事項潜在的な問題に関する詳細情報を参照してください、可能な救済措置に赤色の警告アイコンをクリックする場所を表示できます。</span><span class="sxs-lookup"><span data-stu-id="fc917-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![詳細と実行するアクションを表示するのには情報アイコンをクリックします。](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="fc917-138">レポートが DLP コマンドレットを検索します。</span><span class="sxs-lookup"><span data-stu-id="fc917-138">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="fc917-139">セキュリティのほとんどのコマンドレットを使用する&amp;コンプライアンス センターでは、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc917-139">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="fc917-140">Office 365 のセキュリティへの接続&amp;リモート PowerShell を使用してコンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="fc917-140">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="fc917-141">次のいずれかを使用して、 [Office 365 のセキュリティ&amp;コマンドレットのコンプライアンス センター](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="fc917-141">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="fc917-p108">ただし、DLP のレポートでは、Exchange Online を含め、Office 365 の間でからデータをプルする必要があります。このため、レポートが DLP コマンドレットは、Exchange オンライン Powershell で使用可能なセキュリティではなく&amp;コンプライアンス センター Powershell。したがって、コマンドレットを使用して、DLP のレポートをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc917-p108">However, DLP reports need pull data from across Office 365, including Exchange Online. For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell. Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="fc917-145">Connect to Exchange Online using remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc917-145">Connect to Exchange Online using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="fc917-146">DLP のレポートには、これらのコマンドレットのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc917-146">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="fc917-147">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="fc917-147">Get-DlpDetectionsReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [<span data-ttu-id="fc917-148">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="fc917-148">Get-DlpDetailReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

