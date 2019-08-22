---
title: データ処理中のエラー修復
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c9c2660929037430535c9b612218563c51b1f056
ms.sourcegitcommit: 3f3f3ecb28ef65d023f3573f9a4e09a0586d8f53
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "36490794"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="3e54e-102">データ処理中のエラー修復</span><span class="sxs-lookup"><span data-stu-id="3e54e-102">Error remediation when processing data</span></span>

<span data-ttu-id="3e54e-103">エラー修復により、電子情報開示管理者は、コンテンツを適切に処理できなくなるデータの問題を修正することができます。</span><span class="sxs-lookup"><span data-stu-id="3e54e-103">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="3e54e-104">たとえば、ファイルがロックまたは暗号化されているため、パスワードで保護されたファイルを処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="3e54e-104">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="3e54e-105">エラー修復を使用すると、電子情報開示管理者は、このようなエラーのあるファイルをダウンロードし、パスワード保護を解除して、修復したファイルをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="3e54e-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="3e54e-106">次のワークフローを使用して、高度な電子情報開示ケースでエラーが発生したファイルを修復します。</span><span class="sxs-lookup"><span data-stu-id="3e54e-106">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="3e54e-107">エラー修復セッションを作成して処理エラーが発生したファイルを修復する</span><span class="sxs-lookup"><span data-stu-id="3e54e-107">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="3e54e-108">次の手順の途中でエラー修復ウィザードが閉じられた場合は、[**表示**] ドロップダウンメニューから [error \*\*\*\* **remediations** ] を選択することにより、エラー修復セッションに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="3e54e-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="3e54e-109">高度な電子情報開示ケースの [**処理**] タブで、[**表示**] ドロップダウンメニューから [**エラー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e54e-109">On the **Processing** tab in an Advanced eDiscovery case, select **Errors** in the **View** drop-down menu.</span></span>

2. <span data-ttu-id="3e54e-110">エラーの種類またはファイルの種類の横にあるラジオボタンをクリックして、修復するエラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e54e-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="3e54e-111">次の例では、パスワードで保護されたファイルを修復しています。</span><span class="sxs-lookup"><span data-stu-id="3e54e-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="3e54e-112">[**新しいエラーの修復**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e54e-112">Click **New error remediation**.</span></span>

    ![エラーの修復](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="3e54e-114">エラー修復セッションは、エラーが発生したファイルを Microsoft 提供の Azure ストレージの場所にコピーして、それをローカルコンピューターにダウンロードして修復できるようにする準備段階で開始します。</span><span class="sxs-lookup"><span data-stu-id="3e54e-114">The error remediation session starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![エラー修復の準備](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="3e54e-116">準備が完了したら、[**次へ: ファイルのダウンロード**] をクリックして、ダウンロードを続行します。</span><span class="sxs-lookup"><span data-stu-id="3e54e-116">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![ファイルをダウンロードする](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="3e54e-118">ファイルをダウンロードするには、**ダウンロード先のパス**を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e54e-118">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="3e54e-119">これは、ファイルがダウンロードされるローカルコンピューター上のパスです。</span><span class="sxs-lookup"><span data-stu-id="3e54e-119">This is a path on your local computer where the file is downloaded.</span></span>  <span data-ttu-id="3e54e-120">既定のパス%USERPROFILE%\Downloads\errors は、ログインしているユーザーの [ダウンロード] フォルダーを指します。</span><span class="sxs-lookup"><span data-stu-id="3e54e-120">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="3e54e-121">このパスは必要に応じて変更できます。</span><span class="sxs-lookup"><span data-stu-id="3e54e-121">You can change this path if necessary.</span></span> <span data-ttu-id="3e54e-122">これを変更する場合は、最適なパフォーマンスを得るためにローカルファイルパスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3e54e-122">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="3e54e-123">リモートネットワークパスは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="3e54e-123">Don't use a remote network path.</span></span>

6. <span data-ttu-id="3e54e-124">[**クリップボードにコピー] を**クリックして、定義済みのコマンドをコピーします。</span><span class="sxs-lookup"><span data-stu-id="3e54e-124">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="3e54e-125">Windows コマンドプロンプトを起動し、コマンドを貼り付けて、 **enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3e54e-125">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="3e54e-126">ファイルがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="3e54e-126">The files are downloaded.</span></span>

    ![エラー修復の準備](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="3e54e-128">[**ファイルのダウンロード**] ページで提供されているコマンドを正常に使用するには、azcopy v1.1 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e54e-128">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="3e54e-129">また、AzCopy v1.1 を使用して、以下の手順10でファイルをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e54e-129">You also must use AzCopy v8.1 to upload the files in step 10 below.</span></span> <span data-ttu-id="3e54e-130">このバージョンの AzCopy をインストールするには、「 [Transfer data With AzCopy v2.0 On Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e54e-130">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="3e54e-131">指定した AzCopy コマンドが失敗した場合は、「 [Advanced eDiscovery での AzCopy のトラブルシューティング](troubleshooting-azcopy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e54e-131">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="3e54e-132">ファイルをダウンロードした後、適切なツールを使用して修復できます。</span><span class="sxs-lookup"><span data-stu-id="3e54e-132">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="3e54e-133">パスワードで保護されたファイルでは、いくつかのパスワードクラッキングツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e54e-133">For password-protected files, there several password cracking tools you can use.</span></span> <span data-ttu-id="3e54e-134">ファイルのパスワードがわかっている場合は、それらを開いてパスワード保護を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="3e54e-134">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="3e54e-135">修復されたファイルのディレクトリ構造とファイル名を保持することが重要です。</span><span class="sxs-lookup"><span data-stu-id="3e54e-135">It's important that you retain the directory structure and file names of the remediated files.</span></span> <span data-ttu-id="3e54e-136">ダウンロードしたファイルとフォルダーのパス名によって、修復済みのファイルを元のファイルに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="3e54e-136">The path names of the downloaded files and folders make it possible to associate the remediated files with the original files.</span></span>  <span data-ttu-id="3e54e-137">ディレクトリ構造またはファイル名が変更されると、次のエラーが表示`Cannot apply Error Remediation to the current Workingset`されます。</span><span class="sxs-lookup"><span data-stu-id="3e54e-137">If the directory structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span>

8. <span data-ttu-id="3e54e-138">[Advanced eDiscovery] に戻り、[**次へ: ファイルのアップロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e54e-138">Now, return to Advanced eDiscovery and click **Next: Upload files**.</span></span>  <span data-ttu-id="3e54e-139">これにより、次の手順に進み、ファイルをアップロードできるようになります。</span><span class="sxs-lookup"><span data-stu-id="3e54e-139">This will move to the next step where you can now upload the files.</span></span>

    ![ファイルをアップロードする](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="3e54e-141">[**ファイルの場所へのパス**] テキストボックスに修復したファイルの場所を指定し、[**クリップボードにコピー] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="3e54e-141">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="3e54e-142">コマンドを Windows コマンドプロンプトに貼り付け、 **enter**キーを押してファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="3e54e-142">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="3e54e-144">[Advanced eDiscovery] に戻り、[**次へ: ファイルの処理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e54e-144">Return to Advanced eDiscovery and click **Next: Process files**.</span></span>

12. <span data-ttu-id="3e54e-145">処理が完了したとき。</span><span class="sxs-lookup"><span data-stu-id="3e54e-145">When processing is complete.</span></span> <span data-ttu-id="3e54e-146">レビューセットに戻り、修復されたファイルを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="3e54e-146">You can return to the review set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="3e54e-147">ファイルが修復されたときの処理</span><span class="sxs-lookup"><span data-stu-id="3e54e-147">What happens when files are remediated</span></span>

<span data-ttu-id="3e54e-148">修復済みのファイルがアップロードされると、元のメタデータは次のフィールドを除いて保持されます。</span><span class="sxs-lookup"><span data-stu-id="3e54e-148">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="3e54e-149">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="3e54e-149">ExtractedTextSize</span></span>
- <span data-ttu-id="3e54e-150">HasText</span><span class="sxs-lookup"><span data-stu-id="3e54e-150">HasText</span></span>
- <span data-ttu-id="3e54e-151">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="3e54e-151">IsErrorRemediate</span></span>
- <span data-ttu-id="3e54e-152">LoadId</span><span class="sxs-lookup"><span data-stu-id="3e54e-152">LoadId</span></span>
- <span data-ttu-id="3e54e-153">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="3e54e-153">ProcessingErrorMessage</span></span>
- <span data-ttu-id="3e54e-154">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="3e54e-154">ProcessingStatus</span></span>
- <span data-ttu-id="3e54e-155">テキスト</span><span class="sxs-lookup"><span data-stu-id="3e54e-155">Text</span></span>
- <span data-ttu-id="3e54e-156">WordCount</span><span class="sxs-lookup"><span data-stu-id="3e54e-156">WordCount</span></span>
- <span data-ttu-id="3e54e-157">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="3e54e-157">WorkingsetId</span></span>

<span data-ttu-id="3e54e-158">Advanced eDiscovery のすべてのメタデータフィールドの定義については、「[ドキュメントメタデータフィールド](document-metadata-fields.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e54e-158">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>
