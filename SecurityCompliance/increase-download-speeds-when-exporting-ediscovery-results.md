---
title: Office 365 から電子情報開示検索の結果をエクスポートするときにダウンロード速度を上げる
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: office 365 セキュリティ&amp;コンプライアンスセンターおよび office 365 Advanced eDiscovery から検索結果をダウンロードするとき、データのスループットを向上させるように Windows レジストリを構成する方法について説明します。
ms.openlocfilehash: bafe9eda98b411472098770e4178748eb84f8afd
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216247"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a><span data-ttu-id="5aaa6-103">Office 365 から電子情報開示検索の結果をエクスポートするときにダウンロード速度を上げる</span><span class="sxs-lookup"><span data-stu-id="5aaa6-103">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>

<span data-ttu-id="5aaa6-p101">office 365 eDiscovery エクスポートツールを使用して office 365 セキュリティ&amp;コンプライアンスセンターでコンテンツ検索の結果をダウンロードするか、office 365 Advanced eDiscovery からデータをダウンロードすると、ツールによって一定数の同時エクスポートが開始されます。データをローカルコンピューターにダウンロードする操作。既定では、同時操作の数は、データのダウンロードに使用しているコンピューターのコア数の8倍に設定されます。たとえば、デュアルコアコンピューター (1 つのチップ上に2台の中央処理装置があることを意味します) では、既定の同時エクスポート操作数は16です。データ転送のスループットとダウンロード処理の速度を向上させるために、検索結果のダウンロードに使用するコンピューターで Windows レジストリ設定を構成することによって、同時操作の数を増やすことができます。ダウンロードプロセスを高速化するには、24回の同時操作の設定から始めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-p101">When you use the Office 365 eDiscovery Export tool to download the results of a Content Search in the Office 365 Security &amp; Compliance Center or download data from Office 365 Advanced eDiscovery, the tool starts a certain number of concurrent export operations to download the data to your local computer. By default, the number of concurrent operations is set to 8 times the number of cores in the computer you're using to download the data. For example, if you have a dual core computer (meaning two central processing units on one chip), the default number of concurrent export operations is 16. To increase the data transfer throughput and speed-up the download process, you can increase the number of concurrent operations by configuring a Windows Registry setting on the computer that you use to download the search results. To speed-up the download process, we recommend that you start with a setting of 24 concurrent operations.</span></span>
  
<span data-ttu-id="5aaa6-p102">低帯域幅ネットワーク経由で検索結果をダウンロードする場合は、この設定値を大きくすると、悪影響を及ぼす可能性があります。または、高帯域幅ネットワーク (同時操作の最大数は 512) で、24を超える同時操作の設定値を増やすことができる場合もあります。このレジストリ設定を構成した後で、環境に最適な同時操作数を見つけるために、この設定を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-p102">If you download search results over a low-bandwidth network, increasing this setting might have a negative impact. Alternatively, you might be able to increase the setting to more than 24 concurrent operations in a high-bandwidth network (the maximum number of concurrent operations is 512). After you configure this registry setting, you might have to change it to find the optimal number of concurrent operations for your environment.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a><span data-ttu-id="5aaa6-112">レジストリ設定を作成してデータをエクスポートするときの同時操作数を変更する</span><span class="sxs-lookup"><span data-stu-id="5aaa6-112">Create a registry setting to change the number of concurrent operations when exporting data</span></span>

<span data-ttu-id="5aaa6-113">セキュリティ&amp;コンプライアンスセンターまたは Advanced eDiscovery からのデータから検索結果をダウンロードするために使用するコンピューターで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-113">Perform the following procedure on the computer that you'll use to download search results from the Security &amp; Compliance Center or data from Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="5aaa6-114">Office 365 eDiscovery エクスポートツールが開いている場合は、これを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-114">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="5aaa6-115">ファイル名サフィックス .reg を使用して、次のテキストをウィンドウのレジストリファイルに保存します。たとえば、ConcurrentOperations のようにします。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-115">Save the following text to a Window registry file by using a filename suffix of .reg; for example, ConcurrentOperations.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    <span data-ttu-id="5aaa6-116">前述のとおり、24回の同時操作から始めて、必要に応じてこの設定を変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-116">As previous explained, we recommend that you start with 24 concurrent operations, and then change this setting as appropriate.</span></span>
    
3. <span data-ttu-id="5aaa6-117">エクスプローラーで、前の手順で作成した .reg ファイルをクリックまたはダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-117">In Windows Explorer, click or double-click the .reg file that you created in the previous step.</span></span>
    
4. <span data-ttu-id="5aaa6-118">[ユーザーアクセス制御] ウィンドウで、[**はい**] をクリックしてレジストリエディターに変更を許可します。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="5aaa6-119">続行するように求めるメッセージが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="5aaa6-120">レジストリエディターに、設定が正常にレジストリに追加されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
6. <span data-ttu-id="5aaa6-121">手順 2-5 を繰り返して、 `DownloadConcurrency`レジストリの設定の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-121">You can repeat steps 2 - 5 to change the value for the  `DownloadConcurrency` registry setting.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="5aaa6-p103">`DownloadConcurrency`レジストリ設定を作成または変更した後は、必ず新しいエクスポートジョブを作成するか、またはダウンロードする検索結果またはデータに対して既存のエクスポートジョブを再起動します。詳細については、「 [more information](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-p103">After you create or change the  `DownloadConcurrency` registry setting, be sure to create a new export job or restart an existing export job for the search results or data that you want to download. See the [More information](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) section for more details.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="5aaa6-124">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5aaa6-124">More information</span></span>

- <span data-ttu-id="5aaa6-p104">この手順で作成した .reg ファイルを初めて実行するときに、新しいレジストリキーが作成されます。その後`DownloadConcurrency` 、.reg の編集ファイルを変更して再実行するたびに、レジストリ設定が編集されます。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-p104">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the  `DownloadConcurrency` registry setting is edited each time you change and re-run the .reg edit file.</span></span> 
    
- <span data-ttu-id="5aaa6-p105">Office 365 eDiscovery エクスポートツールは、 [Azure azcopy ユーティリティ](https://go.microsoft.com/fwlink/?linkid=849949)を使用して、セキュリティ&amp;コンプライアンスセンターまたはアドバンスト eDiscovery から検索データをダウンロードします。レジストリ設定`DownloadConcurrency`の構成は、azcopy ユーティリティを実行するときに、 **/NC**パラメーターを使用するのと似ています。そのため、の`"DownloadConcurrency=24"`レジストリ設定は、azcopy ユーティリティ`/NC:24`でパラメーター値を使用するのと同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-p105">The Office 365 eDiscovery Export tool uses the [Azure AzCopy utility](https://go.microsoft.com/fwlink/?linkid=849949) to download search data from the Security &amp; Compliance Center or from Advanced eDiscovery. Configuring the  `DownloadConcurrency` registry setting is similar to using the **/NC** parameter when running the AzCopy utility. So the registry setting of  `"DownloadConcurrency=24"` would have the same effect as using the parameter value of  `/NC:24` with the AzCopy utility.</span></span> 
    
- <span data-ttu-id="5aaa6-p106">現在進行中のエクスポートのダウンロードを停止してから再起動すると (検索結果を再度ダウンロードしようとした場合)、Office 365 eDiscovery エクスポートツールは同じダウンロードを再開します。そのため、ダウンロードを開始し、停止した後、 `DownloadConcurrency`レジストリ設定を変更すると、再起動するとダウンロードが失敗することがあります ([エクスポートされた結果の**ダウンロード**] をクリックします)。これは、エクスポートツールがレジストリ設定を変更したために有効でない設定を使用して、以前のダウンロードを再開しようとしたためです。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-p106">If you stop an export download that's currently in progress and then restart it (by trying to download the search results again), the Office 365 eDiscovery Export tool will attempt to resume the same download. So, if you start a download, stop it, and then change the  `DownloadConcurrency` registry setting, the download will probably fail if you restart it (by clicking **Download exported results**). This is because the export tool will attempt to resume the previous download using settings that aren't valid because you changed the registry setting.</span></span>
    
    <span data-ttu-id="5aaa6-p107">そのため、レジストリの`DownloadConcurrency`設定を変更した後は、セキュリティ&amp; /コンプライアンスセンターのエクスポートジョブを ([**再起動**] をクリックして) 再起動してください。その後、エクスポートされた結果をダウンロードできます。検索結果とデータのエクスポートの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aaa6-p107">Therefore, after you change the  `DownloadConcurrency` registry setting, be sure to restart the export job (by clicking **Restart export**) in the Security &amp; Compliance Center. Then you can download the exported results. For more information about exporting search results and data, see:</span></span>
    
  - [<span data-ttu-id="5aaa6-136">Office 365 セキュリティ&amp;コンプライアンスセンターからコンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5aaa6-136">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
  - [<span data-ttu-id="5aaa6-137">Office 365 Advanced eDiscovery で結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5aaa6-137">Export results in Office 365 Advanced eDiscovery</span></span>](export-results-in-advanced-ediscovery.md)
    
