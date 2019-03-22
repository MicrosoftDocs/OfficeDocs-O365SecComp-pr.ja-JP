---
title: データ処理中のエラー修復
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: f6db3c178e584c45cf282158c58fb5125dc41f3f
ms.sourcegitcommit: cf9d9b545a7c153d314aa9c08c7fb16fcd785b3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "30737677"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="54d3f-102">データ処理中のエラー修復</span><span class="sxs-lookup"><span data-stu-id="54d3f-102">Error remediation when processing data</span></span>

<span data-ttu-id="54d3f-103">エラー修復を使用すると、電子情報開示管理者がコンテンツを適切に処理できないようなデータの問題を修正することができます。</span><span class="sxs-lookup"><span data-stu-id="54d3f-103">Error remediation allows eDiscovery administrators the ability to rectify data issues which prevent Advanced eDiscovery (Preview) from properly processing the content.</span></span> <span data-ttu-id="54d3f-104">たとえば、ファイルがロックまたは暗号化されているため、パスワードで保護されたファイルを処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="54d3f-104">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="54d3f-105">エラー修復を使用すると、電子情報開示管理者は、このようなエラーが発生したファイルをダウンロードし、パスワード保護を解除して、修復されたファイルをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="54d3f-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection and upload the remediated files.</span></span>

<span data-ttu-id="54d3f-106">次のワークフローを使用して、高度な電子情報開示 (プレビュー) ケースでエラーが発生したファイルを修復します。</span><span class="sxs-lookup"><span data-stu-id="54d3f-106">Use the following workflow to remediate files with errors in Advanced eDiscovery (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="54d3f-107">処理エラーが発生したファイルを修復するためのエラー修復セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="54d3f-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="54d3f-108">次の手順の途中でエラー修復ウィザードが閉じられた場合は、[**表示**] ドロップダウンメニューから [error \*\*\*\* **remediations** ] を選択することにより、エラー修復セッションに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="54d3f-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="54d3f-109">高度な電子情報開示 (プレビュー) ケースの [**処理**] タブで、[**表示**] ドロップダウンメニューから [**エラー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="54d3f-109">On the **Processing** tab in an Advanced eDiscovery (Preview) case, select **Errors** in the **View** drop down menu.</span></span>

2. <span data-ttu-id="54d3f-110">エラーの種類またはファイルの種類の横にあるラジオボタンをクリックして、修復するエラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="54d3f-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="54d3f-111">次の例では、パスワードで保護されたファイルを修復しています。</span><span class="sxs-lookup"><span data-stu-id="54d3f-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="54d3f-112">[ **+ 新しいエラーの修復**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54d3f-112">Click **+ New error remediation**.</span></span>

    ![エラーの修復](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="54d3f-114">エラー修復セッションが開始され、エラーが発生したファイルが、セキュリティで保護された Azure の場所に移動される準備段階から開始されます。</span><span class="sxs-lookup"><span data-stu-id="54d3f-114">The error remediation session will begin, starting with a preparation stage where the files that errored are moved to a secure Azure location to be downloaded.</span></span>

    ![エラー修復の準備](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="54d3f-116">準備が完了したら、[**次へ: ファイルのダウンロード**] をクリックして、ダウンロードを続行します。</span><span class="sxs-lookup"><span data-stu-id="54d3f-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![ファイルをダウンロードする](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="54d3f-118">ファイルをダウンロードするには、**ダウンロード先のパス**を指定します。これは、ファイルをダウンロードするローカルコンピューター上のパスです。</span><span class="sxs-lookup"><span data-stu-id="54d3f-118">To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="54d3f-119">既定のパス%USERPROFILE%\Downloads\errors は、ログインしているユーザーの [ダウンロード] フォルダーを指します。必要に応じて変更できます。</span><span class="sxs-lookup"><span data-stu-id="54d3f-119">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="54d3f-120">最適なパフォーマンスを得るには、リモートネットワークパスの代わりにローカルファイルパスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54d3f-120">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="54d3f-121">azcopy をインストールしていない場合は、ここからインストールできます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="54d3f-121">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="54d3f-122">[**クリップボードにコピー] を**クリックして、定義済みのコマンドをコピーします。</span><span class="sxs-lookup"><span data-stu-id="54d3f-122">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="54d3f-123">windows コマンドプロンプトを起動し、コマンドを貼り付けて、 **enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="54d3f-123">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="54d3f-124">ファイルがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="54d3f-124">The files will be downloaded.</span></span>

    ![エラー修復の準備](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="54d3f-126">指定した azcopy コマンドが失敗した場合は、「 [Advanced eDiscovery での azcopy のトラブルシューティング (プレビュー)](troubleshooting-azcopy.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54d3f-126">If the supplied AzCopy command fails, see to [Troubleshoot AzCopy in Advanced eDiscovery (Preview)](troubleshooting-azcopy.md)</span></span>

7. <span data-ttu-id="54d3f-127">ファイルをダウンロードした後、適切なツールを使用して修復できます。</span><span class="sxs-lookup"><span data-stu-id="54d3f-127">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="54d3f-128">パスワードで保護されたファイルには、いくつかのパスワードクラッキングツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="54d3f-128">For password protected files, there are a number of password cracking tools you can use.</span></span> <span data-ttu-id="54d3f-129">ファイルのパスワードがわかっている場合は、それらを開いてパスワード保護を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="54d3f-129">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="54d3f-130">tact で修復されたファイルのディレクトリ構造とファイル名を保持することが重要です。</span><span class="sxs-lookup"><span data-stu-id="54d3f-130">IT is important that you retain the directory structure and file names of the remediated files in tact.</span></span>  <span data-ttu-id="54d3f-131">ダウンロードしたファイルとフォルダーで使用されているすべての命名規則によって、remdiated ファイルを元のファイルに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="54d3f-131">All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="54d3f-132">「Advanced eDiscovery (プレビュー)」に戻り、[**次へ: ファイルのアップロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54d3f-132">Now, return to Advanced eDiscovery (Preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="54d3f-133">これにより、次の手順に進み、ファイルをアップロードできるようになります。</span><span class="sxs-lookup"><span data-stu-id="54d3f-133">This will move to the next step where you can now upload the files.</span></span>

    ![ファイルをアップロードする](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="54d3f-135">[**ファイルの場所へのパス**] テキストボックスで、修復したファイルの場所を指定してから、[マイ**ボードにコピー] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="54d3f-135">Specifiy the location of the remediated files in the **Path to location of files** text box, then click **Copy to clibpboard**.</span></span>

10. <span data-ttu-id="54d3f-136">コマンドを Windows コマンドプロンプトに貼り付け、 **enter**キーを押してファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="54d3f-136">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="54d3f-138">最後に、[Advanced eDiscovery (プレビュー) に戻る] をクリックし、[**次へ: ファイルの処理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54d3f-138">Finally, return to Advanced eDiscovery (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="54d3f-139">処理が完了したとき。</span><span class="sxs-lookup"><span data-stu-id="54d3f-139">When processing is complete.</span></span>  <span data-ttu-id="54d3f-140">ワーキングセットに戻り、修復されたファイルを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="54d3f-140">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="54d3f-141">ファイルが修復されたときの処理</span><span class="sxs-lookup"><span data-stu-id="54d3f-141">What happens when files are remediated</span></span>

<span data-ttu-id="54d3f-142">修復済みのファイルがアップロードされると、元のメタデータは次のフィールドを除いて保持されます。</span><span class="sxs-lookup"><span data-stu-id="54d3f-142">When remediated files are uploaded, the original metadata is preserved with the exception of the following fields:</span></span> 

- <span data-ttu-id="54d3f-143">DocumentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="54d3f-143">DocumentExtractedUrl</span></span>
- <span data-ttu-id="54d3f-144">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="54d3f-144">ExtractedTextSize</span></span>
- <span data-ttu-id="54d3f-145">HasText</span><span class="sxs-lookup"><span data-stu-id="54d3f-145">HasText</span></span>
- <span data-ttu-id="54d3f-146">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="54d3f-146">IsErrorRemediate</span></span>
- <span data-ttu-id="54d3f-147">IsParentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="54d3f-147">IsParentExtractedUrl</span></span>
- <span data-ttu-id="54d3f-148">ItemExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="54d3f-148">ItemExtractedUrl</span></span>
- <span data-ttu-id="54d3f-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="54d3f-149">LoadId</span></span>
- <span data-ttu-id="54d3f-150">processingerrormessage</span><span class="sxs-lookup"><span data-stu-id="54d3f-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="54d3f-151">processingstatus</span><span class="sxs-lookup"><span data-stu-id="54d3f-151">ProcessingStatus</span></span>
- <span data-ttu-id="54d3f-152">テキスト</span><span class="sxs-lookup"><span data-stu-id="54d3f-152">Text</span></span>
- <span data-ttu-id="54d3f-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="54d3f-153">WordCount</span></span>
- <span data-ttu-id="54d3f-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="54d3f-154">WorkingsetId</span></span>

<span data-ttu-id="54d3f-155">Advanced eDiscovery (プレビュー) 内のすべてのドキュメントメタデータフィールドの定義については、「[ドキュメントメタデータフィールド](document-metadata-fields.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54d3f-155">For a definition of all document metadata fields in Advanced eDiscovery (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>