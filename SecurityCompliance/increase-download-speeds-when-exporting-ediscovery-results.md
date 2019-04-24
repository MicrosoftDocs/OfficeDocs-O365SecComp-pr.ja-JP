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
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: Office 365 のセキュリティ & コンプライアンスセンターおよび Advanced eDiscovery から検索結果をダウンロードし、データを検索するときに、データのスループットを向上させるように Windows レジストリを構成する方法について説明します。
ms.openlocfilehash: 10eff929d6b668d5e2bc22d8ee7f223da4943326
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256515"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a><span data-ttu-id="c0d4b-103">Office 365 から電子情報開示検索の結果をエクスポートするときにダウンロード速度を上げる</span><span class="sxs-lookup"><span data-stu-id="c0d4b-103">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>

<span data-ttu-id="c0d4b-104">office 365 eDiscovery エクスポートツールを使用して、Security & コンプライアンスセンターでコンテンツ検索の結果をダウンロードするか、office 365 Advanced eDiscovery からのデータをダウンロードすると、ツールによって、ダウンロードするための一定数の同時エクスポート操作が開始されます。ローカルコンピューターにデータを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-104">When you use the Office 365 eDiscovery Export tool to download the results of a Content Search in the Security & Compliance Center or download data from Office 365 Advanced eDiscovery, the tool starts a certain number of concurrent export operations to download the data to your local computer.</span></span> <span data-ttu-id="c0d4b-105">既定では、同時操作の数は、データのダウンロードに使用しているコンピューターのコア数の8倍に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-105">By default, the number of concurrent operations is set to 8 times the number of cores in the computer you're using to download the data.</span></span> <span data-ttu-id="c0d4b-106">たとえば、デュアルコアコンピューター (1 つのチップ上に2台の中央処理装置があることを意味します) では、既定の同時エクスポート操作数は16です。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-106">For example, if you have a dual core computer (meaning two central processing units on one chip), the default number of concurrent export operations is 16.</span></span> <span data-ttu-id="c0d4b-107">データ転送のスループットとダウンロード処理の速度を向上させるために、検索結果のダウンロードに使用するコンピューターで Windows レジストリ設定を構成することによって、同時操作の数を増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-107">To increase the data transfer throughput and speed-up the download process, you can increase the number of concurrent operations by configuring a Windows Registry setting on the computer that you use to download the search results.</span></span> <span data-ttu-id="c0d4b-108">ダウンロードプロセスを高速化するには、24回の同時操作の設定から始めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-108">To speed-up the download process, we recommend that you start with a setting of 24 concurrent operations.</span></span>
  
<span data-ttu-id="c0d4b-109">低帯域幅ネットワーク経由で検索結果をダウンロードする場合は、この設定値を大きくすると、悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-109">If you download search results over a low-bandwidth network, increasing this setting might have a negative impact.</span></span> <span data-ttu-id="c0d4b-110">または、高帯域幅ネットワーク (同時操作の最大数は 48) で、24を超える同時操作の設定値を増やすことができる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-110">Alternatively, you might be able to increase the setting to more than 24 concurrent operations in a high-bandwidth network (the maximum number of concurrent operations is 48).</span></span> <span data-ttu-id="c0d4b-111">このレジストリ設定を構成した後で、環境に最適な同時操作数を見つけるために、この設定を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-111">After you configure this registry setting, you might have to change it to find the optimal number of concurrent operations for your environment.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a><span data-ttu-id="c0d4b-112">レジストリ設定を作成してデータをエクスポートするときの同時操作数を変更する</span><span class="sxs-lookup"><span data-stu-id="c0d4b-112">Create a registry setting to change the number of concurrent operations when exporting data</span></span>

<span data-ttu-id="c0d4b-113">セキュリティ & コンプライアンスセンターまたは Advanced eDiscovery からのデータからの検索結果をダウンロードするために使用するコンピューターで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-113">Perform the following procedure on the computer that you'll use to download search results from the Security & Compliance Center or data from Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="c0d4b-114">Office 365 eDiscovery エクスポートツールが開いている場合は、これを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-114">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="c0d4b-115">ファイル名サフィックス .reg を使用して、次のテキストをウィンドウのレジストリファイルに保存します。たとえば、ConcurrentOperations のようにします。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-115">Save the following text to a Window registry file by using a filename suffix of .reg; for example, ConcurrentOperations.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    <span data-ttu-id="c0d4b-116">前述のとおり、24回の同時操作から始めて、必要に応じてこの設定を変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-116">As previous explained, we recommend that you start with 24 concurrent operations, and then change this setting as appropriate.</span></span>
    
3. <span data-ttu-id="c0d4b-117">エクスプローラーで、前の手順で作成した .reg ファイルをクリックまたはダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-117">In Windows Explorer, click or double-click the .reg file that you created in the previous step.</span></span>
    
4. <span data-ttu-id="c0d4b-118">[ユーザーアクセス制御] ウィンドウで、[**はい**] をクリックしてレジストリエディターに変更を許可します。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="c0d4b-119">続行するように求めるメッセージが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="c0d4b-120">レジストリエディターに、設定が正常にレジストリに追加されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
6. <span data-ttu-id="c0d4b-121">手順 2-5 を繰り返して、 `DownloadConcurrency`レジストリの設定の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-121">You can repeat steps 2 - 5 to change the value for the  `DownloadConcurrency` registry setting.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="c0d4b-122">`DownloadConcurrency`レジストリ設定を作成または変更した後は、必ず新しいエクスポートジョブを作成するか、またはダウンロードする検索結果またはデータに対して既存のエクスポートジョブを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-122">After you create or change the  `DownloadConcurrency` registry setting, be sure to create a new export job or restart an existing export job for the search results or data that you want to download.</span></span> <span data-ttu-id="c0d4b-123">詳細については、「[詳細情報](#more-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-123">See the [More information](#more-information) section for more details.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="c0d4b-124">詳細情報</span><span class="sxs-lookup"><span data-stu-id="c0d4b-124">More information</span></span>

- <span data-ttu-id="c0d4b-125">この手順で作成した .reg ファイルを初めて実行するときに、新しいレジストリキーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-125">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="c0d4b-126">その後`DownloadConcurrency` 、.reg の編集ファイルを変更して再実行するたびに、レジストリ設定が編集されます。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-126">Then the  `DownloadConcurrency` registry setting is edited each time you change and re-run the .reg edit file.</span></span> 
    
- <span data-ttu-id="c0d4b-127">Office 365 eDiscovery エクスポートツールは、 [Azure azcopy ユーティリティ](https://go.microsoft.com/fwlink/?linkid=849949)を使用して、Security & コンプライアンスセンターまたは Advanced eDiscovery から検索データをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-127">The Office 365 eDiscovery Export tool uses the [Azure AzCopy utility](https://go.microsoft.com/fwlink/?linkid=849949) to download search data from the Security & Compliance Center or from Advanced eDiscovery.</span></span> <span data-ttu-id="c0d4b-128">レジストリ設定`DownloadConcurrency`の構成は、azcopy ユーティリティを実行するときに、 **/NC**パラメーターを使用するのと似ています。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-128">Configuring the  `DownloadConcurrency` registry setting is similar to using the **/NC** parameter when running the AzCopy utility.</span></span> <span data-ttu-id="c0d4b-129">そのため、の`"DownloadConcurrency=24"`レジストリ設定は、azcopy ユーティリティ`/NC:24`でパラメーター値を使用するのと同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-129">So the registry setting of  `"DownloadConcurrency=24"` would have the same effect as using the parameter value of  `/NC:24` with the AzCopy utility.</span></span> 
    
- <span data-ttu-id="c0d4b-130">現在進行中のエクスポートのダウンロードを停止してから再起動すると (検索結果を再度ダウンロードしようとした場合)、Office 365 eDiscovery エクスポートツールは同じダウンロードを再開します。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-130">If you stop an export download that's currently in progress and then restart it (by trying to download the search results again), the Office 365 eDiscovery Export tool will attempt to resume the same download.</span></span> <span data-ttu-id="c0d4b-131">そのため、ダウンロードを開始し、停止した後、 `DownloadConcurrency`レジストリ設定を変更すると、再起動するとダウンロードが失敗することがあります ([エクスポートされた結果の**ダウンロード**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-131">So, if you start a download, stop it, and then change the  `DownloadConcurrency` registry setting, the download will probably fail if you restart it (by clicking **Download exported results**).</span></span> <span data-ttu-id="c0d4b-132">これは、エクスポートツールがレジストリ設定を変更したために有効でない設定を使用して、以前のダウンロードを再開しようとしたためです。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-132">This is because the export tool will attempt to resume the previous download using settings that aren't valid because you changed the registry setting.</span></span>
    
    <span data-ttu-id="c0d4b-133">そのため、 `DownloadConcurrency`レジストリ設定を変更した後、Security & コンプライアンスセンターで、必ずエクスポートジョブを再起動します ([**再起動**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-133">Therefore, after you change the  `DownloadConcurrency` registry setting, be sure to restart the export job (by clicking **Restart export**) in the Security & Compliance Center.</span></span> <span data-ttu-id="c0d4b-134">その後、エクスポートされた結果をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-134">Then you can download the exported results.</span></span> <span data-ttu-id="c0d4b-135">検索結果とデータのエクスポートの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0d4b-135">For more information about exporting search results and data, see:</span></span>
    
  - [<span data-ttu-id="c0d4b-136">コンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="c0d4b-136">Export Content Search results</span></span>](export-search-results.md)
    
  - [<span data-ttu-id="c0d4b-137">Office の結果をエクスポートする 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c0d4b-137">Export results in Office 365 Advanced eDiscovery</span></span>](export-results-in-advanced-ediscovery.md)
    
