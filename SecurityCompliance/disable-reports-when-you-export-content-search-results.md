---
title: Office 365 のセキュリティ コンテンツの検索結果をエクスポートするときに、レポートを無効にする&amp;コンプライアンス センター
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: Office 365 のセキュリティ コンテンツの検索結果をエクスポートするときにレポートを無効にするローカル コンピューターの Windows レジストリを編集する&amp;Comliance センター。これらのレポートを無効にすると、ダウンロード時間を短縮し、ディスク領域を節約できます。
ms.openlocfilehash: 3c09e0563ddd4469f21950dc3a698ce08b0014df
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532675"
---
# <a name="disable-reports-when-you-export-content-search-results-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="55cf3-104">Office 365 のセキュリティ コンテンツの検索結果をエクスポートするときに、レポートを無効にする&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="55cf3-104">Disable reports when you export Content Search results in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="55cf3-p102">セキュリティ コンテンツの検索結果をエクスポートするのには Office 365 の電子的証拠開示のエクスポート ツールを使用すると&amp;コンプライアンス センター、ツール自動的に作成し、エクスポートされたコンテンツに関する追加情報が含まれている 2 つのレポートをエクスポートします。これらのレポートは、Results.csv ファイル Manifest.xml ファイル (これらのレポートの詳細な説明については、このトピックの[よく寄せられる質問に関するレポートをエクスポートを無効にする](#frequently-asked-questions-about-disabling-export-reports)セクションを参照してください)。これらのファイルであるため非常に大きく、ダウンロード時間を短縮し、これらのファイルがエクスポートされるようにすることでディスク領域を節約できます。検索結果のエクスポートに使用するコンピューターの Windows レジストリを変更することによってこれを行うことができます。後で、レポートを含める場合は、レジストリ設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="55cf3-p102">When you use the Office 365 eDiscovery Export tool to export the results of a Content Search in the Security &amp; Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content. These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports). Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported. You can do this by changing the Windows Registry on the computer that you use to export the search results. If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="55cf3-110">エクスポート レポートを無効にするレジストリ設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="55cf3-110">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="55cf3-111">コンテンツの検索結果をエクスポートするのには使用するコンピューターで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="55cf3-111">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="55cf3-112">開いている場合は、Office 365 の電子的証拠開示のエクスポート ツールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="55cf3-112">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="55cf3-113">いずれかまたは両方を無効にするレポートのエクスポートによって、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="55cf3-113">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="55cf3-114">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="55cf3-114">**Results.csv**</span></span>
    
      <span data-ttu-id="55cf3-115">次のテキストを .reg のファイル名サフィックスを使用して Windows レジストリ ファイルを保存します。たとえば、DisableResultsCsv.reg です。</span><span class="sxs-lookup"><span data-stu-id="55cf3-115">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="55cf3-116">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="55cf3-116">**Manifest.xml**</span></span>
    
      <span data-ttu-id="55cf3-117">次のテキストを .reg のファイル名サフィックスを使用して Windows レジストリ ファイルを保存します。たとえば、DisableManifestXml.reg です。</span><span class="sxs-lookup"><span data-stu-id="55cf3-117">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="55cf3-118">Windows エクスプ ローラーで、をクリックしてまたは前の手順で作成した .reg ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="55cf3-118">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="55cf3-119">ユーザー アクセスの制御] ウィンドウで **[はい]** に変更した場合、レジストリ エディターを使用をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55cf3-119">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="55cf3-120">続行するメッセージが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55cf3-120">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="55cf3-121">レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55cf3-121">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="55cf3-122">エクスポート レポートを再度有効にするレジストリ設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="55cf3-122">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="55cf3-p103">前の手順で .reg ファイルを作成することによって、Results.csv と Manifest.xml レポートを無効にした場合は、レポートを再度有効にするには、検索結果と共にエクスポートするためにそれらのファイルを編集できます。もう一度、コンテンツの検索結果をエクスポートするのには使用するコンピューターで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="55cf3-p103">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results. Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="55cf3-125">開いている場合は、Office 365 の電子的証拠開示のエクスポート ツールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="55cf3-125">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="55cf3-126">1 つまたは 2 つの .reg ファイルの編集前の手順で作成したを編集します。</span><span class="sxs-lookup"><span data-stu-id="55cf3-126">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="55cf3-127">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="55cf3-127">**Results.csv**</span></span>
    
        <span data-ttu-id="55cf3-p104">開いているメモ帳で DisableResultsCsv.reg ファイルの値を変更`False`を`True`、し、ファイルを保存します。などのファイルを編集した後に次のようになります。</span><span class="sxs-lookup"><span data-stu-id="55cf3-p104">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file. For example, after you edit the file, it looks like this:</span></span>
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="55cf3-130">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="55cf3-130">**Manifest.xml**</span></span>
    
        <span data-ttu-id="55cf3-p105">開いているメモ帳で DisableManifestXml.reg ファイルの値を変更`False`を`True`、し、ファイルを保存します。などのファイルを編集した後に次のようになります。</span><span class="sxs-lookup"><span data-stu-id="55cf3-p105">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file. For example, after you edit the file, it looks like this:</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="55cf3-133">Windows エクスプ ローラーでをクリックしてまたは前の手順で編集した内容の .reg ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="55cf3-133">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="55cf3-134">ユーザー アクセスの制御] ウィンドウで **[はい]** に変更した場合、レジストリ エディターを使用をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55cf3-134">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="55cf3-135">続行するメッセージが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55cf3-135">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="55cf3-136">レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55cf3-136">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="55cf3-137">エクスポート レポートの無効化についてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="55cf3-137">Frequently asked questions about disabling export reports</span></span>
<span data-ttu-id="55cf3-138"><a name="faqs"> </a></span><span class="sxs-lookup"><span data-stu-id="55cf3-138"></span></span>

 <span data-ttu-id="55cf3-139">**Results.csv と Manifest.xml レポートとは**</span><span class="sxs-lookup"><span data-stu-id="55cf3-139">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="55cf3-140">Results.csv、Manifest.xml ファイルには、エクスポートされたコンテンツに関する追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="55cf3-140">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="55cf3-p106">**Results.csv**する Excel ドキュメントを検索結果としては、ダウンロードする各アイテムに関する情報が含まれています。電子メールでは、結果のログに、各メッセージに関する情報が含まれているなど。</span><span class="sxs-lookup"><span data-stu-id="55cf3-p106">**Results.csv** An Excel document that contains information about each item that is download as a search result. For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="55cf3-143">移行元のメールボックス内のメッセージの場所 (メッセージがプライマリ メールボックスとアーカイブ メールボックスのどちらであるかを含みます)。</span><span class="sxs-lookup"><span data-stu-id="55cf3-143">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="55cf3-144">メッセージが送信または受信された日付。</span><span class="sxs-lookup"><span data-stu-id="55cf3-144">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="55cf3-145">メッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="55cf3-145">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="55cf3-146">メッセージの送信者と受信者。</span><span class="sxs-lookup"><span data-stu-id="55cf3-146">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="55cf3-p107">かどうか、メッセージは、検索結果をエクスポートするときに重複除外を有効にした場合、重複するメッセージです。重複したメッセージは、**親アイテムの Id**列を重複メッセージを識別する値があります。**親アイテムの Id**列の値は、エクスポートされたメッセージの**項目 DocumentId**列の値と同じです。</span><span class="sxs-lookup"><span data-stu-id="55cf3-p107">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results. Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate. The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="55cf3-150">各ドキュメントに関する情報が含まれますビジネス サイトのドキュメント SharePoint と OneDrive から、には結果のログには含みます。</span><span class="sxs-lookup"><span data-stu-id="55cf3-150">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="55cf3-151">ドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="55cf3-151">The URL for the document.</span></span>
    
  - <span data-ttu-id="55cf3-152">ドキュメントがあるサイト コレクションの URL。</span><span class="sxs-lookup"><span data-stu-id="55cf3-152">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="55cf3-153">ドキュメントが最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="55cf3-153">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="55cf3-154">ドキュメントの名前 (これは、結果のログの [件名] 列にあります)。</span><span class="sxs-lookup"><span data-stu-id="55cf3-154">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="55cf3-p108">**Manifest.xml**内のマニフェスト ファイル (XML 形式) を検索結果に含まれる各アイテムに関する情報が含まれています。このレポートの情報は、Results.csv レポートと同じですが、指定されている形式の電子証拠開示の参照モデル (優れた) で。優れたについての詳細についてを参照して[https://www.edrm.net](https://www.edrm.net)。</span><span class="sxs-lookup"><span data-stu-id="55cf3-p108">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results. The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM). For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="55cf3-158">**無効にすべきこれらのレポートをエクスポートしますか。**</span><span class="sxs-lookup"><span data-stu-id="55cf3-158">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="55cf3-p109">お客様固有のニーズによって異なります。多くの組織では、検索結果に関する追加情報を必要としないし、これらのレポートは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="55cf3-p109">It depends on your specific needs. Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="55cf3-161">**どのようなコンピューターでこれを行うにあるでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="55cf3-161">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="55cf3-162">Office 365 の電子的証拠開示のエクスポート ツールを実行する任意のローカル コンピューターのレジストリ設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55cf3-162">You have to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="55cf3-163">**この設定を変更した後コンピューターを再起動する必要ですか。**</span><span class="sxs-lookup"><span data-stu-id="55cf3-163">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="55cf3-p110">いいえ、コンピューターを再起動する必要はありません。閉じ、レジストリ設定を変更した後に再起動する必要がある Office 365 の電子的証拠開示のエクスポート ツールを実行する場合。</span><span class="sxs-lookup"><span data-stu-id="55cf3-p110">No, you don't have to restart the computer. But if the Office 365 eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="55cf3-166">**既存のレジストリ キーを編集を取得して新しいキーを作成を取得してか。**</span><span class="sxs-lookup"><span data-stu-id="55cf3-166">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="55cf3-p111">最初にこのトピックの手順で作成した .reg ファイルを実行するとき、新しいレジストリ キーが作成されます。設定を変更および編集の .reg ファイルを再実行するたびに編集します。</span><span class="sxs-lookup"><span data-stu-id="55cf3-p111">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic. Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
