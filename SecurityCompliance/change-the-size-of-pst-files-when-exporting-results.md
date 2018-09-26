---
title: 電子的証拠開示検索結果をエクスポートするときは、PST ファイルのサイズを変更します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 変更するには、電子的証拠開示検索結果をエクスポートすると、コンピューターへのダウンロードは、PST ファイルの既定のサイズ。
ms.openlocfilehash: 1479db72117729d2e5cfa6feec1d9a0d9a60ffb5
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25037990"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="f31a8-103">電子的証拠開示検索結果をエクスポートするときは、PST ファイルのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="f31a8-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="f31a8-p101">マイクロソフトのさまざまな電子的証拠開示ツールから、電子メールの結果、電子的証拠開示検索をエクスポートするのには Office 365 の電子的証拠開示のエクスポート ツールを使用すると、エクスポート可能な PST ファイルの既定のサイズは、10 GB です。この既定のサイズを変更する場合は、検索結果のエクスポートに使用するコンピューターの Windows レジストリを編集できます。これを行う理由の 1 つは、PST ファイルがリムーバブル メディア、このような DVD、コンパクト ディスク、または USB ドライブに収まるようにします。</span><span class="sxs-lookup"><span data-stu-id="f31a8-p101">When you use the Office 365 eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB. If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results. One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="f31a8-107">Office 365 の電子的証拠開示のエクスポート ツールを使用して Office 365 のセキュリティでコンテンツの検索を使用する場合は、検索結果をエクスポートするのには&amp;コンプライアンス センター、Exchange online では、埋め込み先での電子的証拠開示と電子情報開示センター SharePoint Online にします。</span><span class="sxs-lookup"><span data-stu-id="f31a8-107">The Office 365 eDiscovery Export tool is used to export the search results when using Content Search in the Office 365 Security &amp; Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span> 
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="f31a8-108">電子的証拠開示検索結果をエクスポートする場合は、PST ファイルのサイズを変更するのにはレジストリの設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="f31a8-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="f31a8-109">電子的証拠開示検索結果のエクスポートを使用しているコンピューター上には、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f31a8-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="f31a8-110">開いている場合は、Office 365 の電子的証拠開示のエクスポート ツールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f31a8-110">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="f31a8-111">.Reg のファイル名サフィックスを使用して、レジストリ ファイルのウィンドウに次のテキストを保存します。たとえば、PstExportSize.reg です。</span><span class="sxs-lookup"><span data-stu-id="f31a8-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="f31a8-p102">上記の例で、`PstSizeLimitInBytes`値は 1,073, 741,824 バイトまたは約 1 GB に設定します。他のいくつかのサンプル値をここでは、`PstSizeLimitInBytes`の設定です。</span><span class="sxs-lookup"><span data-stu-id="f31a8-p102">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB. Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="f31a8-114">**GB 単位のサイズ (約)**</span><span class="sxs-lookup"><span data-stu-id="f31a8-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="f31a8-115">**サイズ (バイト単位)**</span><span class="sxs-lookup"><span data-stu-id="f31a8-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="f31a8-116">.7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="f31a8-116">.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="f31a8-117">751619277</span><span class="sxs-lookup"><span data-stu-id="f31a8-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="f31a8-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="f31a8-118">2 GB</span></span>  <br/> |<span data-ttu-id="f31a8-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="f31a8-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="f31a8-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="f31a8-120">4 GB</span></span>  <br/> |<span data-ttu-id="f31a8-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="f31a8-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="f31a8-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="f31a8-122">8 GB</span></span>  <br/> |<span data-ttu-id="f31a8-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="f31a8-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="f31a8-124">変更、 `PstSizeLimitInBytes` 、ファイルを保存して、検索結果をエクスポートするときは、PST ファイルの最大サイズの値です。</span><span class="sxs-lookup"><span data-stu-id="f31a8-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="f31a8-125">Windows エクスプ ローラーで、をクリックしてまたは前の手順で作成した .reg ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f31a8-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="f31a8-126">ユーザー アクセスの制御] ウィンドウで **[はい]** に変更した場合、レジストリ エディターを使用をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f31a8-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="f31a8-127">続行するメッセージが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f31a8-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="f31a8-128">レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f31a8-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="f31a8-129">手順 3 ~ 6 の値を変更するを繰り返すことができます、`PstSizeLimitInBytes`のレジストリ設定です。</span><span class="sxs-lookup"><span data-stu-id="f31a8-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="f31a8-130">電子的証拠開示検索結果をエクスポートする場合は、PST ファイルの既定のサイズを変更することに関するよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="f31a8-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="f31a8-131">**理由は、既定のサイズは 10 GB ですか。**</span><span class="sxs-lookup"><span data-stu-id="f31a8-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="f31a8-132">10 GB の既定のサイズは、顧客からのフィードバックはに基づいてでした。10 GB は、単一の pst ファイルの破損の可能性が最小のコンテンツの最適な量のバランスです。</span><span class="sxs-lookup"><span data-stu-id="f31a8-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="f31a8-133">**増加または PST ファイルの既定のサイズを小さく必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="f31a8-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="f31a8-p103">お客様は、検索結果は、組織内の他の場所に物理的にことができます出荷をリムーバブル ・ メディアに合うようにサイズの制限値を小さく傾向があります。PST ファイル 10 GB の破損の問題があるよりも大きいために、既定サイズを大きくことはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="f31a8-p103">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship other locations in their organization. We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="f31a8-136">**どのようなコンピューターでこれを行うにあるでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="f31a8-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="f31a8-137">Office 365 の電子的証拠開示のエクスポート ツールを実行する任意のローカル コンピューターのレジストリ設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f31a8-137">You need to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="f31a8-138">**この設定を変更後する必要があります、コンピューターを再起動しますか。**</span><span class="sxs-lookup"><span data-stu-id="f31a8-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="f31a8-p104">いいえ、コンピューターを再起動する必要はありません。Office 365 の電子的証拠開示のエクスポート ツールを実行する場合と再起動を終了する必要がありますが、この設定を変更した後ことです。</span><span class="sxs-lookup"><span data-stu-id="f31a8-p104">No, you don't have to reboot the computer. But, if the Office 365 eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="f31a8-141">**既存のレジストリ キーを編集を取得して新しいキーを作成を取得してか。**</span><span class="sxs-lookup"><span data-stu-id="f31a8-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="f31a8-p105">最初にこの手順で作成した .reg ファイルを実行するとき、新しいレジストリ キーが作成されます。設定を変更および編集の .reg ファイルを再実行するたびに編集します。</span><span class="sxs-lookup"><span data-stu-id="f31a8-p105">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
