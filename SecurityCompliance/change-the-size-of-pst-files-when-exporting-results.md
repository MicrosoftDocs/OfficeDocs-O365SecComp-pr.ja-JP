---
title: 電子情報開示検索結果をエクスポートするときに PST ファイルのサイズを変更する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 電子情報開示検索結果をエクスポートするときに、コンピューターにダウンロードされる PST ファイルの既定のサイズを変更できます。
ms.openlocfilehash: 8a956091f29ec1b564d3194c7e3ca2680fdeb564
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214627"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="bcf42-103">電子情報開示検索結果をエクスポートするときに PST ファイルのサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="bcf42-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="bcf42-p101">Office 365 ediscovery エクスポートツールを使用して、さまざまな Microsoft ediscovery ツールから電子情報開示検索の結果をエクスポートする場合、エクスポート可能な PST ファイルの既定のサイズは 10 GB です。この既定のサイズを変更する場合は、検索結果のエクスポートに使用するコンピューターで Windows レジストリを編集できます。これを行う理由の1つは、PST ファイルが DVD、コンパクトディスク、または USB ドライブなどのリムーバブルメディアに格納できるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="bcf42-p101">When you use the Office 365 eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB. If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results. One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="bcf42-107">office 365 eDiscovery エクスポートツールは、office 365 セキュリティ&amp;コンプライアンスセンター、Exchange online のインプレース電子情報開示、および SharePoint online の電子情報開示センターでコンテンツ検索を使用している場合に、検索結果をエクスポートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bcf42-107">The Office 365 eDiscovery Export tool is used to export the search results when using Content Search in the Office 365 Security &amp; Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span> 
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="bcf42-108">電子情報開示検索結果をエクスポートするときに PST ファイルのサイズを変更するためのレジストリ設定を作成する</span><span class="sxs-lookup"><span data-stu-id="bcf42-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="bcf42-109">電子情報開示検索の結果をエクスポートするために使用するコンピューターで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bcf42-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="bcf42-110">Office 365 eDiscovery エクスポートツールが開いている場合は、これを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bcf42-110">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="bcf42-111">ファイル名サフィックス .reg を使用して、次のテキストをウィンドウのレジストリファイルに保存します。たとえば、PstExportSize のようにします。</span><span class="sxs-lookup"><span data-stu-id="bcf42-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="bcf42-p102">上記の例では、 `PstSizeLimitInBytes`値は1073741824バイトまたは約 1 GB に設定されます。この`PstSizeLimitInBytes`設定の他のサンプル値を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bcf42-p102">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB. Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="bcf42-114">**サイズ (GB) (約)**</span><span class="sxs-lookup"><span data-stu-id="bcf42-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="bcf42-115">**バイト単位のサイズ**</span><span class="sxs-lookup"><span data-stu-id="bcf42-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="bcf42-116">7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="bcf42-116">.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="bcf42-117">751619277</span><span class="sxs-lookup"><span data-stu-id="bcf42-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="bcf42-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="bcf42-118">2 GB</span></span>  <br/> |<span data-ttu-id="bcf42-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="bcf42-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="bcf42-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="bcf42-120">4 GB</span></span>  <br/> |<span data-ttu-id="bcf42-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="bcf42-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="bcf42-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="bcf42-122">8 GB</span></span>  <br/> |<span data-ttu-id="bcf42-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="bcf42-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="bcf42-124">検索結果`PstSizeLimitInBytes`をエクスポートするときに、必要な PST ファイルの最大サイズに値を変更して、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="bcf42-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="bcf42-125">エクスプローラーで、前の手順で作成した .reg ファイルをクリックまたはダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcf42-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="bcf42-126">[ユーザーアクセス制御] ウィンドウで、[**はい**] をクリックしてレジストリエディターに変更を許可します。</span><span class="sxs-lookup"><span data-stu-id="bcf42-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="bcf42-127">続行するように求めるメッセージが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcf42-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="bcf42-128">レジストリエディターに、設定が正常にレジストリに追加されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcf42-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="bcf42-129">手順 3-6 を繰り返して、 `PstSizeLimitInBytes`レジストリの設定の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="bcf42-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="bcf42-130">電子情報開示検索結果をエクスポートするときの PST ファイルの既定のサイズ変更に関してよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="bcf42-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="bcf42-131">**既定のサイズが 10 GB ののはなぜですか。**</span><span class="sxs-lookup"><span data-stu-id="bcf42-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="bcf42-132">既定のサイズは 10 GB で、お客様のフィードバックに基づいています。10 GB は、1つの PST に含まれるコンテンツの最適な量と、ファイルの破損が最小限になる確率とのバランスが優れています。</span><span class="sxs-lookup"><span data-stu-id="bcf42-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="bcf42-133">**PST ファイルの既定のサイズを増減する必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="bcf42-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="bcf42-p103">お客様は、組織内の他の場所を物理的に出荷できるリムーバブルメディアに検索結果が格納されるように、サイズ制限を小さくする傾向があります。10 GB を超える PST ファイルで破損の問題が発生する可能性があるため、既定のサイズを大きくしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bcf42-p103">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship other locations in their organization. We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="bcf42-136">**この操作を実行する必要があるコンピューター**</span><span class="sxs-lookup"><span data-stu-id="bcf42-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="bcf42-137">Office 365 eDiscovery エクスポートツールを実行するローカルコンピューターのレジストリ設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcf42-137">You need to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="bcf42-138">**この設定を変更した後、コンピューターを再起動する必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="bcf42-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="bcf42-p104">いいえ、コンピューターを再起動する必要はありません。ただし、Office 365 eDiscovery エクスポートツールを実行している場合は、この設定を変更した後に、このツールを閉じて再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcf42-p104">No, you don't have to reboot the computer. But, if the Office 365 eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="bcf42-141">**既存のレジストリキーを編集するか、新しいキーを作成しますか?**</span><span class="sxs-lookup"><span data-stu-id="bcf42-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="bcf42-p105">この手順で作成した .reg ファイルを初めて実行するときに、新しいレジストリキーが作成されます。その後、.reg の編集ファイルを変更して再実行するたびに、この設定が編集されます。</span><span class="sxs-lookup"><span data-stu-id="bcf42-p105">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
