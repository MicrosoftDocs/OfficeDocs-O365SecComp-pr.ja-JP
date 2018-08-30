---
title: Office 365 から電子的証拠開示検索結果をエクスポートするときは、ダウンロード速度を上げる
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: 検索結果をダウンロードするとき、データのスループットを向上するのには Windows レジストリを構成する方法について説明し、Office 365 のセキュリティ データを検索する&amp;コンプライアンス センターと Office 365 の詳細の開示。
ms.openlocfilehash: 3f456f5ee0312d4d4d7b95f868520e6756a90fd1
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532808"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a><span data-ttu-id="6f8f4-103">Office 365 から電子的証拠開示検索結果をエクスポートするときは、ダウンロード速度を上げる</span><span class="sxs-lookup"><span data-stu-id="6f8f4-103">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>

<span data-ttu-id="6f8f4-p101">Office 365 のセキュリティ コンテンツの検索結果をダウンロードするのには Office 365 の電子的証拠開示のエクスポート ツールを使用すると&amp;コンプライアンス センターまたはダウンロードのデータを Office 365 の高度な電子的証拠開示、ツールから特定の数の同時実行のエクスポートを開始します。ローカル コンピューターにデータをダウンロードする操作です。既定では、コンカレント ・ オペレーションの数が 8 倍のデータをダウンロードして使用しているコンピューターでのコアの数を設定します。たとえば、デュアル コア コンピューター (つまり、1 つのチップ上の 2 つの中央演算処理装置) がある場合は、同時実行のエクスポート操作の既定数は 16 です。増やすには、データ転送のスループットとをダウンロード処理の高速化、検索結果のダウンロードに使用するコンピューターの Windows レジストリ設定を構成することで同時操作の数を変更できます。ダウンロード処理の高速化に 24 の並行処理の設定を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-p101">When you use the Office 365 eDiscovery Export tool to download the results of a Content Search in the Office 365 Security &amp; Compliance Center or download data from Office 365 Advanced eDiscovery, the tool starts a certain number of concurrent export operations to download the data to your local computer. By default, the number of concurrent operations is set to 8 times the number of cores in the computer you're using to download the data. For example, if you have a dual core computer (meaning two central processing units on one chip), the default number of concurrent export operations is 16. To increase the data transfer throughput and speed-up the download process, you can increase the number of concurrent operations by configuring a Windows Registry setting on the computer that you use to download the search results. To speed-up the download process, we recommend that you start with a setting of 24 concurrent operations.</span></span>
  
<span data-ttu-id="6f8f4-p102">低帯域幅のネットワーク上で検索結果をダウンロードすると、この設定を増やすこと、影響を及ぼすことがあります。または、(並行処理の最大数は 512 です)、高帯域幅ネットワークでの同時オペレーションを 24 個を超えるに設定できる場合があります。このレジストリ設定を構成した後は、環境内のコンカレント ・ オペレーションの最適数を検索するように変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-p102">If you download search results over a low-bandwidth network, increasing this setting might have a negative impact. Alternatively, you might be able to increase the setting to more than 24 concurrent operations in a high-bandwidth network (the maximum number of concurrent operations is 512). After you configure this registry setting, you might have to change it to find the optimal number of concurrent operations for your environment.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a><span data-ttu-id="6f8f4-112">データをエクスポートするときに、コンカレント ・ オペレーションの数を変更するレジストリを設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-112">Create a registry setting to change the number of concurrent operations when exporting data</span></span>

<span data-ttu-id="6f8f4-113">セキュリティからの検索結果のダウンロードを使用しているコンピューターで次の手順を実行&amp;コンプライアンス センターや高度な電子的証拠開示のデータです。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-113">Perform the following procedure on the computer that you'll use to download search results from the Security &amp; Compliance Center or data from Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="6f8f4-114">開いている場合は、Office 365 の電子的証拠開示のエクスポート ツールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-114">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="6f8f4-115">.Reg のファイル名サフィックスを使用して、レジストリ ファイルのウィンドウに次のテキストを保存します。たとえば、ConcurrentOperations.reg です。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-115">Save the following text to a Window registry file by using a filename suffix of .reg; for example, ConcurrentOperations.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    <span data-ttu-id="6f8f4-116">前に説明すると、24 の同時オペレーションを開始し、し、必要に応じてこの設定を変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-116">As previous explained, we recommend that you start with 24 concurrent operations, and then change this setting as appropriate.</span></span>
    
3. <span data-ttu-id="6f8f4-117">Windows エクスプ ローラーで、をクリックしてまたは前の手順で作成した .reg ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-117">In Windows Explorer, click or double-click the .reg file that you created in the previous step.</span></span>
    
4. <span data-ttu-id="6f8f4-118">ユーザー アクセスの制御] ウィンドウで **[はい]** に変更した場合、レジストリ エディターを使用をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="6f8f4-119">続行するメッセージが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="6f8f4-120">レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
6. <span data-ttu-id="6f8f4-121">値を変更する手順 2 ~ 5 を繰り返すことができます、`DownloadConcurrency`のレジストリ設定です。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-121">You can repeat steps 2 - 5 to change the value for the  `DownloadConcurrency` registry setting.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="6f8f4-p103">作成または変更した後、`DownloadConcurrency`レジストリ設定は、必ず新しいエクスポート ジョブを作成または検索結果のデータをダウンロードする既存のエクスポート ジョブを再起動します。詳細については、[詳細について](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo)はを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-p103">After you create or change the  `DownloadConcurrency` registry setting, be sure to create a new export job or restart an existing export job for the search results or data that you want to download. See the [More information](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) section for more details.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="6f8f4-124">詳細情報</span><span class="sxs-lookup"><span data-stu-id="6f8f4-124">More information</span></span>

- <span data-ttu-id="6f8f4-p104">最初にこの手順で作成した .reg ファイルを実行するとき、新しいレジストリ キーが作成されます。`DownloadConcurrency`のレジストリ設定を変更および編集の .reg ファイルを再実行するたびに編集します。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-p104">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the  `DownloadConcurrency` registry setting is edited each time you change and re-run the .reg edit file.</span></span> 
    
- <span data-ttu-id="6f8f4-p105">Office 365 の電子的証拠開示のエクスポート ツールでは、 [Azure AzCopy ユーティリティ](https://go.microsoft.com/fwlink/?linkid=849949)を使用して、セキュリティの検索データをダウンロード&amp;コンプライアンス センターまたは高度な電子的証拠開示します。構成する、`DownloadConcurrency`レジストリ設定は、 **/NC**パラメーターを使用して AzCopy ユーティリティを実行するときに似ています。などのレジストリ設定`"DownloadConcurrency=24"`のパラメーターの値を使用すると同じ効果があります`/NC:24`AzCopy ユーティリティを使用しています。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-p105">The Office 365 eDiscovery Export tool uses the [Azure AzCopy utility](https://go.microsoft.com/fwlink/?linkid=849949) to download search data from the Security &amp; Compliance Center or from Advanced eDiscovery. Configuring the  `DownloadConcurrency` registry setting is similar to using the **/NC** parameter when running the AzCopy utility. So the registry setting of  `"DownloadConcurrency=24"` would have the same effect as using the parameter value of  `/NC:24` with the AzCopy utility.</span></span> 
    
- <span data-ttu-id="6f8f4-p106">(検索結果をもう一度ダウンロードしようとしています) を再起動しますが現在進行中のエクスポート ダウンロードを停止すると、Office 365 の電子的証拠開示のエクスポート ツールは、同じダウンロードを再開しようとします。ダウンロードを開始する場合は停止し、変更、`DownloadConcurrency`レジストリ設定、ダウンロード失敗する可能性が (**ダウンロード結果のエクスポート**] をクリック) で再起動する場合。エクスポート ツールは、前にレジストリ設定を変更したためではない有効な設定を使用してダウンロードを再開しようとして ためにです。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-p106">If you stop an export download that's currently in progress and then restart it (by trying to download the search results again), the Office 365 eDiscovery Export tool will attempt to resume the same download. So, if you start a download, stop it, and then change the  `DownloadConcurrency` registry setting, the download will probably fail if you restart it (by clicking **Download exported results**). This is because the export tool will attempt to resume the previous download using settings that aren't valid because you changed the registry setting.</span></span>
    
    <span data-ttu-id="6f8f4-p107">したがってを変更した後、`DownloadConcurrency`のレジストリ設定を [セキュリティ] をクリックして**エクスポートを再起動**) エクスポート ジョブを再開することを確認して&amp;コンプライアンス センターです。エクスポートされた結果をダウンロードできます。検索結果とデータのエクスポートの詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f8f4-p107">Therefore, after you change the  `DownloadConcurrency` registry setting, be sure to restart the export job (by clicking **Restart export**) in the Security &amp; Compliance Center. Then you can download the exported results. For more information about exporting search results and data, see:</span></span>
    
  - [<span data-ttu-id="6f8f4-136">Office 365 のセキュリティ コンテンツの検索結果をエクスポートする&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="6f8f4-136">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
  - [<span data-ttu-id="6f8f4-137">Office 365 Advanced eDiscovery で結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="6f8f4-137">Export results in Office 365 Advanced eDiscovery</span></span>](export-results-in-advanced-ediscovery.md)
    
