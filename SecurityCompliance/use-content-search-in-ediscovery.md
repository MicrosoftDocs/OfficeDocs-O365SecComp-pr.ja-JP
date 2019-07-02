---
title: 電子情報開示ワークフローでコンテンツ検索を使用する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: 'セキュリティ & コンプライアンスセンターで作成された検索に基づいて、Exchange Online でインプレース電子情報開示検索を作成するには、PowerShell スクリプトを使用します。 '
ms.openlocfilehash: f3d5eb76dfa91334bccae42e0ddb66a71f739a6f
ms.sourcegitcommit: 044003455eb36071806c9f008ac631d54c64dde6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2019
ms.locfileid: "35199824"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a><span data-ttu-id="82d83-103">電子情報開示ワークフローでコンテンツ検索を使用する</span><span class="sxs-lookup"><span data-stu-id="82d83-103">Use Content Search in your eDiscovery workflow</span></span>

<span data-ttu-id="82d83-104">セキュリティ & コンプライアンスセンターのコンテンツ検索機能を使用すると、組織内のすべてのメールボックスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="82d83-104">The Content Search feature in the Security & Compliance Center allows you to search all mailboxes in your organization.</span></span> <span data-ttu-id="82d83-105">Exchange Online のインプレース電子情報開示とは異なり (1万メールボックスを検索することができます)、単一の検索の対象メールボックスの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="82d83-105">Unlike In-Place eDiscovery in Exchange Online (where you can search up to 10,000 mailboxes), there are no limits for the number of target mailboxes in a single search.</span></span> <span data-ttu-id="82d83-106">組織全体の検索を実行する必要があるシナリオでは、コンテンツ検索を使用してすべてのメールボックスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="82d83-106">For scenarios that require you to perform organization-wide searches, you can use Content Search to search all mailboxes.</span></span> <span data-ttu-id="82d83-107">その後、インプレース電子情報開示のワークフロー機能を使用して、メールボックスを保持に配置したり、検索結果をエクスポートしたりするなど、電子情報開示関連のその他のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="82d83-107">Then you can use the workflow features of In-Place eDiscovery to perform other eDiscovery-related tasks, such as placing mailboxes on hold and exporting search results.</span></span> <span data-ttu-id="82d83-108">たとえば、すべてのメールボックスを検索して、訴訟に応答する特定の保管担当者を識別する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="82d83-108">For example, let's say you have to search all mailboxes to identify specific custodians that are responsive to a legal case.</span></span> <span data-ttu-id="82d83-109">セキュリティ & コンプライアンスセンターでコンテンツ検索を使用して、組織内のすべてのメールボックスを検索し、そのケースに応答するものを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="82d83-109">You can use Content Search in the Security & Compliance Center to search all mailboxes in your organization to identify those that are responsive to the case.</span></span> <span data-ttu-id="82d83-110">その後、保管担当者メールボックスのリストを、Exchange Online のインプレース電子情報開示検索用のソースメールボックスとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="82d83-110">Then you can use that list of custodian mailboxes as the source mailboxes for an In-Place eDiscovery search in Exchange Online.</span></span> <span data-ttu-id="82d83-111">インプレース電子情報開示を使用すると、これらのソースメールボックスを保持でき、検索結果を証拠開示用メールボックスにコピーして、検索結果をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="82d83-111">Using In-Place eDiscovery also allows you to put a hold on those source mailboxes, copy search results to a discovery mailbox, and export the search results.</span></span>
  
<span data-ttu-id="82d83-112">このトピックには、セキュリティ & コンプライアンスセンターで作成された検索からソースメールボックスと検索クエリの一覧を使用して、Exchange Online でインプレース電子情報開示検索を作成するために実行できるスクリプトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="82d83-112">This topic includes a script that you can run to create an In-Place eDiscovery search in Exchange Online by using the list of source mailboxes and search query from a search created in the Security & Compliance Center.</span></span> <span data-ttu-id="82d83-113">プロセスの概要は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82d83-113">Here's an overview of the process:</span></span>
  
[<span data-ttu-id="82d83-114">手順 1: 組織内のすべてのメールボックスを検索するためのコンテンツ検索を作成する</span><span class="sxs-lookup"><span data-stu-id="82d83-114">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[<span data-ttu-id="82d83-115">手順 2: 1 つのリモート\& PowerShell セッションでセキュリティコンプライアンスセンターと Exchange Online に接続する</span><span class="sxs-lookup"><span data-stu-id="82d83-115">Step 2: Connect to the Security \& Compliance Center and Exchange Online in a single remote PowerShell session</span></span>](#step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[<span data-ttu-id="82d83-116">手順 3: コンテンツ検索からインプレースの電子情報開示検索を作成するスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="82d83-116">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[<span data-ttu-id="82d83-117">手順 4: インプレースの電子情報開示検索を開始する</span><span class="sxs-lookup"><span data-stu-id="82d83-117">Step 4: Start the In-Place eDiscovery search</span></span>](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a><span data-ttu-id="82d83-118">手順 1: 組織内のすべてのメールボックスを検索するためのコンテンツ検索を作成する</span><span class="sxs-lookup"><span data-stu-id="82d83-118">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>

<span data-ttu-id="82d83-119">最初の手順として、セキュリティ & コンプライアンスセンター (またはセキュリティ & コンプライアンスセンター PowerShell) を使用して、組織内のすべてのメールボックスを検索するコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="82d83-119">The first step is to use the Security & Compliance Center (or Security & Compliance Center PowerShell) to create a Content Search that searches all mailboxes in your organization.</span></span> <span data-ttu-id="82d83-120">単一のコンテンツ検索のメールボックス数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="82d83-120">There's no limit for the number of mailboxes for a single Content Search.</span></span> <span data-ttu-id="82d83-121">適切なキーワード クエリ (または機密情報の種類に関するクエリ) を指定し、検索によって対象に関連する検索メールボックスだけが返されるようにします。</span><span class="sxs-lookup"><span data-stu-id="82d83-121">Specify an appropriate keyword query (or a query for sensitive information types) so that the search returns only those source mailboxes that are relevant to your investigation.</span></span> <span data-ttu-id="82d83-122">必要に応じて、検索クエリを調整し、返される検索結果とソース メールボックスの範囲を絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="82d83-122">If necessary, refine the search query to narrow the scope of search results and source mailboxes that are returned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="82d83-123">ソースコンテンツ検索で結果が返されない場合は、手順3でスクリプトを実行しても、インプレース電子情報開示は作成されません。</span><span class="sxs-lookup"><span data-stu-id="82d83-123">If the source Content Search doesn't return any results, an In-Place eDiscovery won't be created when you run the script in Step 3.</span></span> <span data-ttu-id="82d83-124">検索クエリを変更してから、検索結果を返すためにコンテンツ検索を再実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="82d83-124">You may have to revise the search query then rerun the Content Search to return search results.</span></span> 
  
### <a name="use-the-security--compliance-center-to-search-all-mailboxes"></a><span data-ttu-id="82d83-125">セキュリティ & コンプライアンスセンターを使用してすべてのメールボックスを検索する</span><span class="sxs-lookup"><span data-stu-id="82d83-125">Use the Security & Compliance Center to search all mailboxes</span></span>

1. <span data-ttu-id="82d83-126">[セキュリティ & コンプライアンスセンターに移動](go-to-the-securitycompliance-center.md)します。</span><span class="sxs-lookup"><span data-stu-id="82d83-126">[Go to the Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span> 
    
2. <span data-ttu-id="82d83-127">[**検索** > **コンテンツ検索**] をクリックし、[**新しい検索** ![の追加] アイコン](media/O365-MDM-CreatePolicy-AddIcon.gif)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82d83-127">Click **Search** > **Content search**, and then click **New search** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
3. <span data-ttu-id="82d83-128">**[新規検索]** ページで、コンテンツ検索の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="82d83-128">On the **New search** page, type a name for the Content Search.</span></span> 
    
4. <span data-ttu-id="82d83-129">[**どこを調べますか?**] で、[**すべてのメールボックスを検索**する] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82d83-129">Under **Where do you want us to look?**, click **Search all mailboxes**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="82d83-130">**[何をお探しですか?]** の下にあるボックスに、検索クエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="82d83-130">In the box under **What do you want us to look for?**, type a search query in the box.</span></span> <span data-ttu-id="82d83-131">キーワード、メッセージ プロパティ (送信日付や受信日付など)、ドキュメント プロパティ (ファイル名や、ドキュメントの最終変更日など) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="82d83-131">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="82d83-132">AND、OR、NOT、NEAR などのブール演算子を使用するより複雑なクエリを使用することも、メッセージで機密情報 (社会保障番号など) を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="82d83-132">You can use a more complex queries that use a Boolean operator, such as AND, OR, NOT or NEAR, or you can also search for sensitive information (such as social security numbers) in messages.</span></span> <span data-ttu-id="82d83-133">検索クエリの作成方法の詳細については、「[コンテンツ検索のキーワードクエリ](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82d83-133">For more information about creating search queries, see [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
6. <span data-ttu-id="82d83-134">**[検索]** をクリックして、検索設定を保存して検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="82d83-134">Click **Search** to save the search settings and start the search.</span></span> 
    
    <span data-ttu-id="82d83-135">しばらくすると、詳細ウィンドウに検索結果の推定値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82d83-135">After a while, an estimate of the search results displayed in the details pane.</span></span> <span data-ttu-id="82d83-136">この推定値には、検索結果の合計サイズと項目数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="82d83-136">The estimate includes the total size and number of items for the search results.</span></span> <span data-ttu-id="82d83-137">検索が完了すると、検索結果をプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="82d83-137">After the search is completed, you can preview the search results.</span></span> <span data-ttu-id="82d83-138">必要に応じて\*\*\*\*![、[最新](media/O365-MDM-Policy-RefreshIcon.gif)の情報に更新] アイコンをクリックして、詳細ウィンドウの情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="82d83-138">If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
7.  <span data-ttu-id="82d83-139">必要に応じて、検索結果の範囲を絞り込むために検索クエリを調整し、検索を再開します。</span><span class="sxs-lookup"><span data-stu-id="82d83-139">If necessary, refine the search query to narrow the scope of search results and then restart the search.</span></span> 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a><span data-ttu-id="82d83-140">セキュリティ & コンプライアンスセンターの PowerShell を使用してすべてのメールボックスを検索する</span><span class="sxs-lookup"><span data-stu-id="82d83-140">Use Security & Compliance Center PowerShell to search all mailboxes</span></span>

<span data-ttu-id="82d83-141">**New-compliancesearch**コマンドレットを使用して、組織内のすべてのメールボックスを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="82d83-141">You can also use the **New-ComplianceSearch** cmdlet to search all mailboxes in your organization.</span></span> <span data-ttu-id="82d83-142">最初の手順として、[セキュリティ & コンプライアンスセンター PowerShell に接続](https://go.microsoft.com/fwlink/p/?LinkID=627084)します。</span><span class="sxs-lookup"><span data-stu-id="82d83-142">The first step is to [Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span></span>
  
<span data-ttu-id="82d83-143">ここでは、PowerShell を使用して組織内のすべてのメールボックスを検索する例を示します。</span><span class="sxs-lookup"><span data-stu-id="82d83-143">Here's an example of using PowerShell to search all mailboxes in your organization.</span></span> <span data-ttu-id="82d83-144">検索クエリは、2015年1月1日から2015年6月30日までの間に送信されたすべてのメッセージを返します。これには件名行に「財務報告」という語句が含まれています。</span><span class="sxs-lookup"><span data-stu-id="82d83-144">The search query returns all messages sent between January 1, 2015 and June 30, 2015 and that contain the phrase "financial report" in the subject line.</span></span> <span data-ttu-id="82d83-145">1 番目のコマンドは検索を作成し、2 番目のコマンドは検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="82d83-145">The first command creates the search, and the second command runs the search.</span></span> 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

<span data-ttu-id="82d83-146">詳細については、「[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82d83-146">For more information, see [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span></span>
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a><span data-ttu-id="82d83-147">コンテンツ検索のソースメールボックスの数を確認する</span><span class="sxs-lookup"><span data-stu-id="82d83-147">Verify the number of source mailboxes in the Content Search</span></span>

<span data-ttu-id="82d83-148">コンテンツ検索では、検索結果を含む最大1000のソースメールボックスが返されます。</span><span class="sxs-lookup"><span data-stu-id="82d83-148">A Content Search returns a maximum of 1,000 source mailboxes that contain search results.</span></span> <span data-ttu-id="82d83-149">検索クエリに一致するコンテンツを含む1000個を超えるメールボックスがある場合、前の手順で作成したコンテンツ検索には、最も検索結果がある上位1000のメールボックスのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="82d83-149">If there are more than 1,000 mailboxes that contain content that matches the search query, only the top 1,000 mailboxes with the most search results are included in the Content Search that you created in the previous step.</span></span> <span data-ttu-id="82d83-150">そのため、1000以上のメールボックスに検索結果が含まれている場合、これらのメールボックスの一部は、手順3で作成した新しいインプレース電子情報開示検索にコピーされたソースメールボックスの一覧には含まれません。</span><span class="sxs-lookup"><span data-stu-id="82d83-150">So if more than 1,000 mailboxes contain search results, some of those mailboxes won't be included in the list of source mailboxes copied to the new In-Place eDiscovery search created in Step 3.</span></span> 
  
<span data-ttu-id="82d83-151">1000を超えるソースメールボックスを持つコンテンツ検索を作成するのに役立つように、次の手順に従って、手順1で作成したコンテンツ検索によって返されるソースメールボックスの数 (検索結果が含まれる) を表示するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="82d83-151">To help you create a Content Search with no more than 1,000 source mailboxes, follow these steps to run a script that displays the number of source mailboxes (that contain search results) returned by the Content Search you created in Step 1.</span></span> 
  
1. <span data-ttu-id="82d83-152">次のテキストを、ファイル名サフィックス. ps1 を使用して PowerShell スクリプトファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="82d83-152">Save the following text to a PowerShell script file by using a filename suffix of .ps1.</span></span> <span data-ttu-id="82d83-153">たとえば、という名前`SourceMailboxes.ps1`のファイルに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="82d83-153">For example, you could save it to a file named `SourceMailboxes.ps1`.</span></span>
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
                  "Please wait until the search finishes.";
                  break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
                  "The Content Search " + $SearchName + " didn't return any useful results.";
                  break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  "Number of mailboxes that have search hits: " + $mailboxes.Count
  ```

2. <span data-ttu-id="82d83-154">[セキュリティ & コンプライアンスセンター] PowerShell で、前の手順で作成したスクリプトが置かれているフォルダーに移動し、スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="82d83-154">In Security & Compliance Center PowerShell, go to the folder where the script you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\SourceMailboxes.ps1
    ```

3. <span data-ttu-id="82d83-155">スクリプトによってメッセージが表示されたら、手順1で作成したコンテンツ検索の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="82d83-155">When prompted by the script, type the name of the Content Search that you created in Step 1.</span></span>
    
    <span data-ttu-id="82d83-156">スクリプトで検索結果が含まれるソース メールボックスの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82d83-156">The script displays the number of source mailboxes that contain search results.</span></span>
    
<span data-ttu-id="82d83-157">1000個を超えるソースメールボックスがある場合は、2つ以上のコンテンツ検索を作成してみてください。</span><span class="sxs-lookup"><span data-stu-id="82d83-157">If there are more than 1,000 source mailboxes, try creating two (or more) Content Searches.</span></span> <span data-ttu-id="82d83-158">たとえば、組織のメールボックスの半分を1つのコンテンツ検索で検索し、別のコンテンツ検索でその残りの部分を検索します。</span><span class="sxs-lookup"><span data-stu-id="82d83-158">For example, search half of your organization's mailboxes in one Content Search and the other half in another Content Search.</span></span> <span data-ttu-id="82d83-159">検索結果が含まれるメールボックスの数が減るように検索条件を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="82d83-159">You could also change the search criteria to reduce the number of mailboxes that contain search results.</span></span> <span data-ttu-id="82d83-160">たとえば、日付範囲を指定したり、キーワードクエリを絞り込んだりすることができます。</span><span class="sxs-lookup"><span data-stu-id="82d83-160">For example, you could include a date range or refine the keyword query.</span></span>
  
## <a name="step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a><span data-ttu-id="82d83-161">手順 2: 1 つのリモート\& PowerShell セッションでセキュリティコンプライアンスセンターと Exchange Online に接続する</span><span class="sxs-lookup"><span data-stu-id="82d83-161">Step 2: Connect to the Security \& Compliance Center and Exchange Online in a single remote PowerShell session</span></span>

<span data-ttu-id="82d83-162">次の手順では、Windows PowerShell をセキュリティ & コンプライアンスセンターおよび Exchange Online 組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="82d83-162">The next step is to connect Windows PowerShell to both the Security & Compliance Center and to your Exchange Online organization.</span></span> <span data-ttu-id="82d83-163">この手順が必要になるのは、手順3で実行するスクリプトで、セキュリティ & コンプライアンスセンターおよび Exchange Online のインプレース電子情報開示のコマンドレットにあるコンテンツ検索コマンドレットにアクセスする必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="82d83-163">This is necessary because the script that you run in Step 3 requires access to the Content Search cmdlets in the Security & Compliance Center and the In-Place eDiscovery cmdlets in Exchange Online.</span></span>
  
1. <span data-ttu-id="82d83-164">ファイル名のサフィックスに .ps1 を使って、次のテキストを Windows PowerShell スクリプト ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="82d83-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1.</span></span> <span data-ttu-id="82d83-165">たとえば、という名前`ConnectEXO-CC.ps1`のファイルに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="82d83-165">For example, you could save it to a file named `ConnectEXO-CC.ps1`.</span></span>
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. <span data-ttu-id="82d83-166">ローカル コンピューター上で、Windows PowerShell を開き、前の手順で作成したスクリプトが配置されているフォルダーに移動し、スクリプトを実行します。例:</span><span class="sxs-lookup"><span data-stu-id="82d83-166">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\ConnectEXO-CC.ps1
    ```

<span data-ttu-id="82d83-167">これが機能したかどうかを知る方法</span><span class="sxs-lookup"><span data-stu-id="82d83-167">How do you know if this worked?</span></span> <span data-ttu-id="82d83-168">スクリプトを実行すると、セキュリティ & コンプライアンスセンターおよび Exchange Online のコマンドレットがローカルの PowerShell セッションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="82d83-168">After you run the script, cmdlets from the Security & Compliance Center and Exchange Online are imported into your local PowerShell session.</span></span> <span data-ttu-id="82d83-169">何もエラーが表示されなければ、正常に接続されています。</span><span class="sxs-lookup"><span data-stu-id="82d83-169">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="82d83-170">簡単に確かめるには、セキュリティ/コンプライアンス センターのコマンドレット (**Install-UnifiedCompliancePrerequisite** など) および Exchange Online のコマンドレット (**Get-Mailbox** など) を実行して結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="82d83-170">A quick test is to run a Security & Compliance Center cmdlet—for example, **Install-UnifiedCompliancePrerequisite** —and an Exchange Online cmdlet, such as **Get-Mailbox**.</span></span> 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a><span data-ttu-id="82d83-171">手順 3: コンテンツ検索からインプレースの電子情報開示検索を作成するスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="82d83-171">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>

<span data-ttu-id="82d83-172">手順2で2つの PowerShell セッションを作成した後、次の手順では、既存のコンテンツ検索をインプレース電子情報開示検索に変換するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="82d83-172">After you create the dual PowerShell session in Step 2, the next step is to run a script that will convert an existing Content Search to an In-Place eDiscovery search.</span></span> <span data-ttu-id="82d83-173">スクリプトは次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="82d83-173">Here's what the script does:</span></span>
  
- <span data-ttu-id="82d83-174">変換するコンテンツ検索の名前を入力するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82d83-174">Prompts you for the name of the Content Search to convert.</span></span>
    
- <span data-ttu-id="82d83-175">コンテンツ検索の実行が完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="82d83-175">Verifies that the Content Search has completed running.</span></span> <span data-ttu-id="82d83-176">コンテンツ検索で結果が返されない場合、インプレース電子情報開示は作成されません。</span><span class="sxs-lookup"><span data-stu-id="82d83-176">If the Content Search doesn't return any results, and In-Place eDiscovery won't be created.</span></span>
    
- <span data-ttu-id="82d83-177">検索結果が含まれるコンテンツ検索からソースメールボックスの一覧を変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="82d83-177">Saves a list of the source mailboxes from the Content Search that contain search results to a variable.</span></span>
    
- <span data-ttu-id="82d83-178">以下のプロパティが設定されたインプレースの電子情報開示検索を新たに作成します。</span><span class="sxs-lookup"><span data-stu-id="82d83-178">Creates a new In-Place eDiscovery search, with the following properties.</span></span> <span data-ttu-id="82d83-179">新しい検索が開始されていないことに注目してください。</span><span class="sxs-lookup"><span data-stu-id="82d83-179">Note that the new search isn't started.</span></span> <span data-ttu-id="82d83-180">手順 4 で開始します。</span><span class="sxs-lookup"><span data-stu-id="82d83-180">You'll start it in step 4.</span></span>
    
  - <span data-ttu-id="82d83-181">**Name** -新しい検索の名前は、次\<の形式を使用します。\>コンテンツ検索 _MBSearch1 の名前です。</span><span class="sxs-lookup"><span data-stu-id="82d83-181">**Name** - The name of the new search uses this format: \<Name of Content Search\>_MBSearch1.</span></span> <span data-ttu-id="82d83-182">スクリプトをもう一度実行して同じソースコンテンツ検索を使用した場合、検索に\<は「Content search\>_MBSearch2」という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="82d83-182">If you run the script again and use the same source Content Search, the search will be named \<Name of Content Search\>_MBSearch2.</span></span>
    
  - <span data-ttu-id="82d83-183">**ソースメールボックス**-検索結果が含まれるコンテンツ検索からのすべてのメールボックス。</span><span class="sxs-lookup"><span data-stu-id="82d83-183">**Source mailboxes** - All mailboxes from the Content Search that contain search results.</span></span> 
    
  - <span data-ttu-id="82d83-184">**検索クエリ**-新しい検索では、コンテンツ検索の検索クエリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="82d83-184">**Search query** - The new search uses the search query from the Content Search.</span></span> <span data-ttu-id="82d83-185">コンテンツ検索にすべてのコンテンツが含まれている場合 (検索クエリが空白の場合)、新しい検索には空の検索クエリがあり、ソースメールボックス内のすべてのコンテンツが含まれます。</span><span class="sxs-lookup"><span data-stu-id="82d83-185">If the Content Search includes all content (where the search query is blank) the new search will also have a blank search query and will include all content found in the source mailboxes.</span></span> 
    
  - <span data-ttu-id="82d83-186">**推定のみ検索**-新しい検索は、推定のみの検索としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="82d83-186">**Estimate only search** - The new search is marked as an estimate-only search.</span></span> <span data-ttu-id="82d83-187">開始した後、検索結果は探索メールボックスにコピーされません。</span><span class="sxs-lookup"><span data-stu-id="82d83-187">It won't copy search results to a discovery mailbox after you start it.</span></span> 
    
1. <span data-ttu-id="82d83-188">ファイル拡張子 ps1 の Windows PowerShell スクリプト ファイルに以下のテキストを保存します。</span><span class="sxs-lookup"><span data-stu-id="82d83-188">Save the following text to a Windows PowerShell script file by using a filename suffix of ps1.</span></span> <span data-ttu-id="82d83-189">たとえば、という名前`CreateMBSearchFromComplianceSearch.ps1`のファイルに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="82d83-189">For example, you could save it to a file named `CreateMBSearchFromComplianceSearch.ps1`.</span></span>
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName,
      [switch]$original,
      [switch]$restoreOriginal
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
    "Please wait until the search finishes";
    break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
    "The Content Search " + $SearchName + " didn't return any useful results";
    "A mailbox search object wasn't created";
    break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  $msPrefix = $SearchName + "_MBSearch";
  $I = 1;
  $mbSearches = Get-MailboxSearch;
  while ($true)
  {
      $found = $false;
      $mbsName = "$msPrefix$I";
      foreach ($mbs in $mbSearches)
      {
          if ($mbs.Name -eq $mbsName)
          {
              $found = $true;
              break;
          }
      }
      if (!$found)
      {
          break;
      }
      $I++;
  }
  $query = $search.KeywordQuery;
  if ([string]::IsNullOrWhiteSpace($query))
  {
      $query = $search.ContentMatchQuery;
  }
  if ([string]::IsNullOrWhiteSpace($query))
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -EstimateOnly;
  }
  else
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -SearchQuery $query -EstimateOnly;
  }
  
  ```

2. <span data-ttu-id="82d83-190">手順2で作成した Windows PowerShell セッションで、前の手順で作成したスクリプトが置かれているフォルダーに移動して、スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="82d83-190">In the Windows PowerShell session that you created in Step 2, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. <span data-ttu-id="82d83-191">スクリプトによってメッセージが表示されたら、インプレース電子情報開示検索に変換するコンテンツ検索の名前を入力し (たとえば、手順1で作成した検索)、enter キーを押し\*\*\*\* ます。</span><span class="sxs-lookup"><span data-stu-id="82d83-191">When prompted by the script, type the name of the Content Search that you want to covert to an In-Place eDiscovery search (for example, the search that you created in Step 1), and then press **Enter**.</span></span>
    
    <span data-ttu-id="82d83-p122">スクリプトが正常に実行されると、新しいインプレースの電子情報開示検索が **NotStarted** というステータスで作成されます。  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` コマンドを実行し、新しい検索のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="82d83-p122">If the script is successful, a new In-Place eDiscovery search is created with a status of **NotStarted**. Run the command  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` to display the properties of the new search.</span></span> 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a><span data-ttu-id="82d83-194">手順 4: インプレースの電子情報開示検索を開始する</span><span class="sxs-lookup"><span data-stu-id="82d83-194">Step 4: Start the In-Place eDiscovery search</span></span>

<span data-ttu-id="82d83-p123">手順 3 で実行したスクリプトでは新しいインプレースの電子情報開示検索が作成されますが、検索は開始しません。この手順では、検索を開始して検索結果の推定値を取得します。</span><span class="sxs-lookup"><span data-stu-id="82d83-p123">The script that you run in Step 3 creates a new In-Place eDiscovery search, but doesn't start it. The next step is to start the search so you can get an estimate of the search results.</span></span>
  
1. <span data-ttu-id="82d83-197">In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="82d83-197">In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="82d83-198">一覧表示から、手順 3 で作成したインプレースの電子情報開示検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="82d83-198">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="82d83-199">![[ \*\*\*\* 検索検索アイコン](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> \*\*\*\* ] をクリックして検索を開始し、検索によって返されるアイテムの合計サイズと件数の推定値を返します。</span><span class="sxs-lookup"><span data-stu-id="82d83-199">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **Estimate search results** to start the search and return an estimate of the total size and number of items returned by the search.</span></span> 
    
    <span data-ttu-id="82d83-200">推定は、詳細ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="82d83-200">The estimates are displayed in the details pane.</span></span> <span data-ttu-id="82d83-201">[最新の情報](media/O365-MDM-Policy-RefreshIcon.gif)に更新] アイコンをクリックして、詳細ウィンドウに表示される情報を更新します。 \*\*\*\* ![</span><span class="sxs-lookup"><span data-stu-id="82d83-201">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information displayed in the details pane.</span></span> 
    
4. <span data-ttu-id="82d83-202">検索が完了した後で結果をプレビューするには、詳細ウィンドウで [ **検索結果のプレビュー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82d83-202">To preview the results after the search is completed, click **Preview search results** in the details pane.</span></span>
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a><span data-ttu-id="82d83-203">インプレースの電子情報開示検索の作成と実行後の手順</span><span class="sxs-lookup"><span data-stu-id="82d83-203">Next steps after creating and running the In-Place eDiscovery search</span></span>

<span data-ttu-id="82d83-204">手順 3 でスクリプトによって作成されたインプレースの電子情報開示検索を開始した後は、通常のインプレースの電子情報開示ワークフローを使用して、検索結果で各種の電子情報開示アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="82d83-204">After you create and start the In-Place eDiscovery search that was created by the script in Step 3, you can use the normal In-Place eDiscovery workflow to perform different eDiscovery actions on the search results.</span></span>
  
### <a name="create-an-in-place-hold"></a><span data-ttu-id="82d83-205">インプレース保持を作成する</span><span class="sxs-lookup"><span data-stu-id="82d83-205">Create an In-Place Hold</span></span>

1. <span data-ttu-id="82d83-206">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="82d83-206">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="82d83-207">リストビューで、手順3で作成したインプレースの電子情報開示検索を選択し、[編集\*\*\*\* ![] 編集アイコン](media/O365-MDM-CreatePolicy-EditIcon.gif)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82d83-207">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Edit** ![Edit icon](media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>
    
3. <span data-ttu-id="82d83-208">[ **インプレース保持**] ページで、[ **選択したメールボックス内の検索クエリに一致したコンテンツを保持する**] チェック ボックスをオンにして、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="82d83-208">On the **In-Place Hold** page, select the **Place content matching the search query in selected mailboxes on hold** check box and then select one of the following options:</span></span> 
    
  - <span data-ttu-id="82d83-209">**無期限に保持**-検索によって返されたアイテムを無期限保持に配置するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="82d83-209">**Hold indefinitely** - Choose this option to place items returned by the search on an indefinite hold.</span></span> <span data-ttu-id="82d83-210">保持されたアイテムは、検索からメールボックスを削除するか、検索を削除するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="82d83-210">Items on hold will be preserved until you remove the mailbox from the search or remove the search.</span></span> 
    
  - <span data-ttu-id="82d83-211">[**受信日を基準としてアイテムを保持する日数を指定**する-特定の期間のアイテムを保持するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="82d83-211">**Specify number of days to hold items relative to their received date** - Choose this option to hold items for a specific period.</span></span> <span data-ttu-id="82d83-212">期間は、メールボックス アイテムが受信または作成された日から計算されます。</span><span class="sxs-lookup"><span data-stu-id="82d83-212">The duration is calculated from the date a mailbox item is received or created.</span></span> 
    
4. <span data-ttu-id="82d83-213">[ **保存**] をクリックしてインプレース保持を作成し、検索を再開します。</span><span class="sxs-lookup"><span data-stu-id="82d83-213">Click **Save** to create the In-Place Hold and restart the search.</span></span> 
    
[<span data-ttu-id="82d83-214">Return to top</span><span class="sxs-lookup"><span data-stu-id="82d83-214">Return to top</span></span>](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a><span data-ttu-id="82d83-215">検索結果をコピーする</span><span class="sxs-lookup"><span data-stu-id="82d83-215">Copy the search results</span></span>

1. <span data-ttu-id="82d83-216">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="82d83-216">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="82d83-217">リスト表示から、手順 3 で作成したインプレースの電子情報開示検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="82d83-217">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="82d83-218">[ \*\*\*\* ![検索検索]](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)アイコンをクリックし、ドロップダウンリストから [**検索結果のコピー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82d83-218">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif), and then click **Copy search results** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="82d83-219">**[検索結果のコピー]** で、次のオプションの中から選択します。</span><span class="sxs-lookup"><span data-stu-id="82d83-219">In **Copy Search Results**, select from the following options:</span></span>
    
    - <span data-ttu-id="82d83-220">[**検索不能アイテムを含める**]: このチェックボックスをオンにすると、検索できなかったメールボックスアイテム (たとえば、Exchange Search によってインデックスが作成されていないファイルの種類の添付ファイルを含むメッセージ) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="82d83-220">**Include unsearchable items** - Select this check box to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search).</span></span> 
    
    - <span data-ttu-id="82d83-221">重複**除外を有効**にする-重複するメッセージを除外するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="82d83-221">**Enable de-duplication** - Select this check box to exclude duplicate messages.</span></span> <span data-ttu-id="82d83-222">探索メールボックスには、メッセージの 1 つのインスタンスだけがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="82d83-222">Only a single instance of a message will be copied to the discovery mailbox.</span></span> 
    
    - <span data-ttu-id="82d83-223">**完全なログ出力を有効**にする-検索結果に完全なログを含めるには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="82d83-223">**Enable full logging** - Select this check box to include a full log in search results.</span></span> 
    
    - <span data-ttu-id="82d83-224">**コピーが完了したらメールを送信**する-検索が完了したときに電子メール通知を受信するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="82d83-224">**Send me mail when the copy is completed** - Select this check box to get an email notification when the search is completed.</span></span> 
    
    - <span data-ttu-id="82d83-225">[**結果をこの探索メールボックスにコピーする**]-[**参照**] をクリックして、検索結果のコピー先の探索メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="82d83-225">**Copy results to this discovery mailbox** - Click **Browse** to select the discovery mailbox where you want the search results copied to.</span></span> 
    
5. <span data-ttu-id="82d83-226">**[コピー]** をクリックして検索結果を指定された探索メールボックスにコピーするプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="82d83-226">Click **Copy** to start the process to copy the search results to the specified discovery mailbox.</span></span> 
    
6. <span data-ttu-id="82d83-227">[最新の情報](media/O365-MDM-Policy-RefreshIcon.gif)に更新] アイコンをクリックして、詳細ウィンドウに表示されるコピー状態に関する情報を更新します。 \*\*\*\* ![</span><span class="sxs-lookup"><span data-stu-id="82d83-227">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information about the copying status that is displayed in the details pane.</span></span> 
    
7. <span data-ttu-id="82d83-228">コピーが完了したら、[**開く**] をクリックして、検索結果を表示する探索メールボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="82d83-228">When copying is complete, click **Open** to open the discovery mailbox to view the search results.</span></span> 
  
### <a name="export-the-search-results"></a><span data-ttu-id="82d83-229">検索結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="82d83-229">Export the search results</span></span>

1. <span data-ttu-id="82d83-230">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="82d83-230">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="82d83-231">一覧表示から、手順 3 で作成したインプレースの電子情報開示検索を選択し、[ **PST ファイルにエクスポートする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82d83-231">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Export to a PST file**.</span></span>
    
3. <span data-ttu-id="82d83-232">[ **Exchange eDiscovery PST エクスポート ツール**] ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="82d83-232">In the **eDiscovery PST Export Tool** window, do the following:</span></span> 
    
    - <span data-ttu-id="82d83-233">[ **参照**] をクリックして、PST ファイルをダウンロードする場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="82d83-233">Click **Browse** to specify the location where you want to download the PST file.</span></span> 
    
    - <span data-ttu-id="82d83-p128">[ **重複除去を有効にする**] ボックスをクリックして重複メッセージを除外します。PST ファイルには、メッセージのインスタンスが 1 つだけ含まれます。</span><span class="sxs-lookup"><span data-stu-id="82d83-p128">Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file.</span></span> 
    
    - <span data-ttu-id="82d83-p129">[ **検索不能アイテムを含める**] チェック ボックスをオンにすると、検索できなかったメールボックス アイテム (たとえば、Exchange 検索でインデックスが作成できなかった種類のファイルが添付されたメッセージ) が含まれます。検索できないアイテムは、別の PST ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="82d83-p129">Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file.</span></span> 
    
4. <span data-ttu-id="82d83-238">[ **開始**] をクリックして、検索結果を PST ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="82d83-238">Click **Start** to export the search results to a PST file.</span></span> 
    
    <span data-ttu-id="82d83-239">エクスポート プロセスに関するステータス情報が含まれているウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82d83-239">A window is displayed that contains status information about the export process.</span></span>
