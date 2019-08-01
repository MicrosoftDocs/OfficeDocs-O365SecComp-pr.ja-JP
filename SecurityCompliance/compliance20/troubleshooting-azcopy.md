---
title: Advanced eDiscovery での AzCopy のトラブルシューティング
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: eb8c84d696a05f86246a512f1867d8efc98881a0
ms.sourcegitcommit: 73dcdafb15b462223d1a670c781db260eb73c2f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "36048095"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="f5e90-102">Advanced eDiscovery での AzCopy のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f5e90-102">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="f5e90-103">高度な電子情報開示でエラーを修復するために Office ではない365データまたはドキュメントを読み込む場合、ユーザーインターフェイスは、アップロードするファイルが保存されている場所と Azure ストレージの場所を含む、Azure AzCopy コマンドを提供します。ファイルがアップロードされる場所。</span><span class="sxs-lookup"><span data-stu-id="f5e90-103">When loading non-Office 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="f5e90-104">ドキュメントをアップロードするには、このコマンドをコピーして、ローカルコンピューターのコマンドプロンプトで実行します。</span><span class="sxs-lookup"><span data-stu-id="f5e90-104">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="f5e90-105">次のスクリーンショットは、AzCopy コマンドの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="f5e90-105">The follow screenshot shows an example of an AzCopy command:</span></span>

![Office 365 以外のファイルをアップロードする](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="f5e90-107">通常、提供されるコマンドは、実行時に機能します。</span><span class="sxs-lookup"><span data-stu-id="f5e90-107">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="f5e90-108">ただし、表示されるコマンドが正常に実行されない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f5e90-108">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="f5e90-109">考えられるいくつかの理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f5e90-109">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="f5e90-110">サポートされているバージョンの AzCopy がローカルコンピューターにインストールされていません</span><span class="sxs-lookup"><span data-stu-id="f5e90-110">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="f5e90-111">現時点では、Advanced 電子情報開示で Office 以外の365データを読み込むには AzCopy v1.1 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5e90-111">At this time, you must use AzCopy v8.1 to load non-Office 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="f5e90-112">AzCopy v2.0 を使用していない場合、前のスクリーンショットに表示されている [**ファイルのアップロード**] ページに表示される azcopy コマンドはエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="f5e90-112">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="f5e90-113">このバージョンをインストールするには、「 [Windows で AzCopy](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)v2.0 でデータを転送する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5e90-113">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="f5e90-114">AzCopy がローカルコンピューターにインストールされていないか、既定の場所にインストールされていません</span><span class="sxs-lookup"><span data-stu-id="f5e90-114">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="f5e90-115">AzCopy がインストールされていない場合や、既定のインストール先 (つまり`%ProgramFiles(x86)%`) 以外の場所にインストールされている場合、azcopy コマンドを実行すると、次のエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f5e90-115">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

    The system cannot find the path specified.

<span data-ttu-id="f5e90-116">AzCopy がローカルコンピューターにインストールされていない場合は、[ここ](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)からインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f5e90-116">If AzCopy isn't installed on the local computer, you can install from [here](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="f5e90-117">必ず既定の場所にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="f5e90-117">Be sure to install it in the default location.</span></span>

<span data-ttu-id="f5e90-118">AzCopy がインストールされていても、既定の場所とは異なる場所にインストールされている場合は、コマンドをコピーしてテキストファイルに貼り付け、次に、AzCopy がインストールされている場所へのパスを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f5e90-118">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="f5e90-119">たとえば、Azcopy がに`%ProgramFiles%`ある場合は、コマンドの最初の部分をから`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe`に`%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`変更できます。</span><span class="sxs-lookup"><span data-stu-id="f5e90-119">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="f5e90-120">この変更を行った後、テキストファイルからコピーし、コマンドプロンプトで実行します。</span><span class="sxs-lookup"><span data-stu-id="f5e90-120">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="f5e90-121">AzCopy が既定のインストール先以外の場所にインストールされている場合は、それをアンインストールしてから、既定の場所に再インストールすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f5e90-121">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="f5e90-122">これにより、今後この問題を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="f5e90-122">This will help prevent this issue in the future.</span></span>
