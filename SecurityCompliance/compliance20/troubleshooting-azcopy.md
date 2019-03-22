---
title: Advanced eDiscovery での azcopy のトラブルシューティング (プレビュー)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 9711bee4ec9a61510b47568df37dfd3135e1e00c
ms.sourcegitcommit: cf9d9b545a7c153d314aa9c08c7fb16fcd785b3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "30742509"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery-preview"></a><span data-ttu-id="4313d-102">Advanced eDiscovery での azcopy のトラブルシューティング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="4313d-102">Troubleshoot AzCopy in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="4313d-103">高度な電子情報開示 (プレビュー) でエラーを修復するために Office 以外の365データまたはドキュメントを読み込む場合、ユーザーインターフェイスは、アップロードするファイルが保存されている場所と azure にパラメーターを含む azure azcopy コマンドを提供します。ファイルがアップロードされる保存場所。</span><span class="sxs-lookup"><span data-stu-id="4313d-103">When loading non-Office 365 data or documents for error remediation in Advanced eDiscovery (Preview), the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="4313d-104">ドキュメントをアップロードするには、このコマンドをコピーして、ローカルコンピューターのコマンドプロンプトで実行します。</span><span class="sxs-lookup"><span data-stu-id="4313d-104">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="4313d-105">次のスクリーンショットは、azcopy コマンドの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="4313d-105">The follow screenshot shows an example of an AzCopy command:</span></span>

![Office 365 以外のファイルをアップロードする](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="4313d-107">ほとんどの場合、提供されているコマンドは、実行時に機能します。</span><span class="sxs-lookup"><span data-stu-id="4313d-107">In most cases, the command that's provided will work when you run it.</span></span> <span data-ttu-id="4313d-108">ただし、表示されるコマンドが正常に実行されない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="4313d-108">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="4313d-109">考えられるいくつかの理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4313d-109">Here's a few possible reasons.</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="4313d-110">azcopy がローカルコンピューターにインストールされていないか、既定の場所にインストールされていません</span><span class="sxs-lookup"><span data-stu-id="4313d-110">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="4313d-111">azcopy がインストールされていない場合や、既定のインストール先 (つまり`%ProgramFiles(x86)%`) 以外の場所にインストールされている場合、azcopy コマンドを実行すると、次のエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="4313d-111">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

    The system cannot find the path specified.

<span data-ttu-id="4313d-112">azcopy がローカルコンピューターにインストールされていない場合は、ここからインストールできます (既定の場所にインストールする[https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)必要があります)。</span><span class="sxs-lookup"><span data-stu-id="4313d-112">If AzCopy isn't install on the local computer, you can install from here (being sure to install it in the default location): [https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span>


<span data-ttu-id="4313d-113">azcopy がインストールされていても、既定の場所とは別の場所にインストールされている場合は、コマンドをコピーしてテキストファイルに貼り付け、次に、azcopy が実際にインストールされている場所へのパスを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4313d-113">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is actually installed.</span></span> <span data-ttu-id="4313d-114">たとえば、azcopy がに`%ProgramFiles%`ある場合は、コマンドの最初の部分をから`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe`に`%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`変更できます。</span><span class="sxs-lookup"><span data-stu-id="4313d-114">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="4313d-115">この変更を行った後、テキストファイルからコピーし、コマンドプロンプトで実行します。</span><span class="sxs-lookup"><span data-stu-id="4313d-115">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="4313d-116">azcopy が既定のインストール先以外の場所にインストールされている場合は、それをアンインストールしてから、既定の場所に再インストールすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4313d-116">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="4313d-117">これにより、今後この問題を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="4313d-117">This will help prevent this issue in the future.</span></span>