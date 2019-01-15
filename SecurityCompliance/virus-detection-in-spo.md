---
title: SharePoint Online のウイルス検出
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 01/14/2019
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
description: Office 365 では、ユーザーが SharePoint Online にアップロードするファイルのウイルスが検出されるため、お客様の環境をマルウェアから保護できます。ファイルをアップロードすると、そのファイルがスキャンされてウイルスが検出されます。ファイルで感染が見つかると、プロパティが設定されて、そのファイルをダウンロードしたり、同期したりできなくなります。
ms.openlocfilehash: ab02d2d4e82e9427ec6b512490f94ccc9c14b54e
ms.sourcegitcommit: 5ccc3dd0d1c087bffd3a8fc807d5d1750f046eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2019
ms.locfileid: "28009593"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="1695a-105">SharePoint Online のウイルス検出</span><span class="sxs-lookup"><span data-stu-id="1695a-105">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="1695a-p102">Office 365 では、ユーザーが SharePoint Online にアップロードするファイルのウイルスが検出されるため、お客様の環境をマルウェアから保護できます。ファイルをアップロードすると、そのファイルがスキャンされてウイルスが検出されます。ファイルで感染が見つかると、プロパティが設定されて、そのファイルをダウンロードしたり、同期したりできなくなります。</span><span class="sxs-lookup"><span data-stu-id="1695a-p102">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online. Files are scanned for viruses after they are uploaded. If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1695a-p103">SharePoint Online のウイルス対策機能は、ウイルスを封じ込める 1 つの方法にすぎません。これだけで、お客様の環境がマルウェアから保護されるわけではありません。すべてのお客様が、マルウェア対策保護を評価してさまざまなレイヤーに実装し、ベスト プラクティスを適用してエンタープライズ インフラストラクチャを保護することをお勧めします。戦略とベスト プラクティスの詳細については、「[Security best practices for Office 365](security-best-practices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1695a-p103">These antivirus capabilities in SharePoint Online are a way to contain viruses. They aren't intended as a single point of defense against malware for your environment. We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure. For more information about strategies and best practices, see [Security best practices for Office 365](security-best-practices.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="1695a-113">感染したファイルが SharePoint Online にアップロードされたとき</span><span class="sxs-lookup"><span data-stu-id="1695a-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="1695a-p104">Office 365 は、一般的なウイルス検出エンジンを使用します。エンジンでは、SharePoint Online では、内で非同期的に実行し、アップロードしたファイルをスキャンします。ウイルスを含むファイルが見つかった場合フラグ設定できるように、もう一度ダウンロードすることはできません。2018 年 4 月では、スキャンしたファイルの 25 MB の制限を削除しました。</span><span class="sxs-lookup"><span data-stu-id="1695a-p104">Office 365 uses a common virus detection engine. The engine runs asynchronously within SharePoint Online, and scans files after they're uploaded. When a file is found to contain a virus, it's flagged so that it can't be downloaded again. In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="1695a-118">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1695a-118">Here's what happens:</span></span>
  
1. <span data-ttu-id="1695a-119">ユーザーがファイルを SharePoint Online にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="1695a-119">A user uploads a file to SharePoint Online.</span></span>
    
2. <span data-ttu-id="1695a-120">ウイルス検出エンジンによってファイルがスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="1695a-120">The virus detection engine scans the file.</span></span>
    
3. <span data-ttu-id="1695a-121">ウイルスが見つかると、ウイルス エンジンによって、感染していることを示すプロパティがファイルに設定されます。</span><span class="sxs-lookup"><span data-stu-id="1695a-121">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="1695a-122">ブラウザーを使って感染したファイルをダウンロードしようとしても、</span><span class="sxs-lookup"><span data-stu-id="1695a-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="1695a-123">SharePoint Online からファイルをダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1695a-123">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="1695a-124">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1695a-124">Here's what happens:</span></span>
  
1. <span data-ttu-id="1695a-125">Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、</span><span class="sxs-lookup"><span data-stu-id="1695a-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="1695a-p105">ユーザーには、ウイルスが検出されたことの警告が与えられます。ユーザーには、ファイルをダウンロードし、独自のウイルス ソフトウェアを使用してクリーニングするためのオプションが与えられます。</span><span class="sxs-lookup"><span data-stu-id="1695a-p105">The user is given a warning that a virus has been detected. The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="1695a-p106">**DisallowInfectedFileDownload**パラメーターを使用してセット SPOTenant コマンドレットを使用するにはウイルス対策の警告] ウィンドウであっても、検出されたファイルをダウンロードするのにユーザーを許可しないようにします。[DisallowInfectedFileDownload] を参照してください (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="1695a-p106">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window. See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="1695a-130">感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="1695a-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="1695a-p107">ファイルの同期を 新しい OneDrive の同期クライアント (OneDrive.exe) と前の OneDrive for Business 同期クライアント (Groove.exe) のどちらを使用して行っても、そのファイルにウイルスが含まれている場合には同期クライアントでダウンロードができません。ファイルを同期できないという通知が同期クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1695a-p107">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it. The sync client will display a notification that the file can't be synced.</span></span>
  

