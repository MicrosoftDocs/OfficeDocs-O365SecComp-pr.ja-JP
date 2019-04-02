---
title: 調査のためにデータを処理するときのエラー修復
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
ms.openlocfilehash: b78a8e45ffb0833dec5116ff637cd0930387ebfe
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030278"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a><span data-ttu-id="f7c2c-102">調査のためにデータを処理するときのエラー修復</span><span class="sxs-lookup"><span data-stu-id="f7c2c-102">Error remediation when processing data for an investigation</span></span>

<span data-ttu-id="f7c2c-103">エラー修復を使用すると、調査担当はデータ調査 (プレビュー) がコンテンツを適切に処理できなくなるデータの問題を修正することができます。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-103">Error remediation allows investigators the ability to rectify data issues which prevent Data Investigations (Preview) from properly processing the content.</span></span> <span data-ttu-id="f7c2c-104">たとえば、ファイルがロックまたは暗号化されているため、パスワードで保護されたファイルを処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-104">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="f7c2c-105">エラー修復を使用する調査官は、このようなエラーのあるファイルをダウンロードし、パスワード保護を解除して、修復されたファイルをアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-105">Using error remediation, investigators can download files with such errors, remove the password protection and upload the remediated files.</span></span>

<span data-ttu-id="f7c2c-106">データ調査 (プレビュー) ケースでエラーが発生したファイルを修復するには、次のワークフローを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-106">Use the following workflow to remediate files with errors in Data Investigations (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="f7c2c-107">処理エラーが発生したファイルを修復するためのエラー修復セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="f7c2c-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="f7c2c-108">次の手順の途中でエラー修復ウィザードが閉じられた場合は、[**表示**] ドロップダウンメニューから [error \*\*\*\* **remediations** ] を選択することにより、エラー修復セッションに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="f7c2c-109">データ調査 (プレビュー) ケースの [**処理**] タブで、[**表示**] ドロップダウンメニューから [**エラー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-109">On the **Processing** tab in an Data Investigations (Preview) case, select **Errors** in the **View** drop down menu.</span></span>

2. <span data-ttu-id="f7c2c-110">エラーの種類またはファイルの種類の横にあるラジオボタンをクリックして、修復するエラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="f7c2c-111">次の例では、パスワードで保護されたファイルを修復しています。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="f7c2c-112">[ **+ 新しいエラーの修復**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-112">Click **+ New error remediation**.</span></span>

    ![エラーの修復](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="f7c2c-114">エラー修復セッションが開始され、エラーが発生したファイルが、セキュリティで保護された Azure の場所に移動される準備段階から開始されます。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-114">The error remediation session will begin, starting with a preparation stage where the files that errored are moved to a secure Azure location to be downloaded.</span></span>

    ![エラー修復の準備](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="f7c2c-116">準備が完了したら、[**次へ: ファイルのダウンロード**] をクリックして、ダウンロードを続行します。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![ファイルをダウンロードする](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="f7c2c-118">ファイルをダウンロードするには、**ダウンロード先のパス**を指定します。これは、ファイルをダウンロードするローカルコンピューター上のパスです。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-118">To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="f7c2c-119">既定のパス%USERPROFILE%\Downloads\errors は、ログインしているユーザーの [ダウンロード] フォルダーを指します。必要に応じて変更できます。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-119">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="f7c2c-120">最適なパフォーマンスを得るには、リモートネットワークパスの代わりにローカルファイルパスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-120">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f7c2c-121">azcopy をインストールしていない場合は、ここからインストールできます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="f7c2c-121">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="f7c2c-122">[**クリップボードにコピー] を**クリックして、定義済みのコマンドをコピーします。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-122">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="f7c2c-123">windows コマンドプロンプトを起動し、コマンドを貼り付けて、 **enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-123">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="f7c2c-124">ファイルがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-124">The files will be downloaded.</span></span>

    ![エラー修復の準備](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > <span data-ttu-id="f7c2c-126">このコマンドの実行に関する問題があるhttps://go.microsoft.com/fwlink/?linkid=2038117場合は、トラブルシューティングのヒントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-126">If you have issues running this command, see https://go.microsoft.com/fwlink/?linkid=2038117 for troubleshooting tips.</span></span>

7. <span data-ttu-id="f7c2c-127">ファイルをダウンロードした後、適切なツールを使用して修復できます。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-127">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="f7c2c-128">パスワードで保護されたファイルには、いくつかのパスワードクラッキングツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-128">For password protected files, there are a number of password cracking tools you can use.</span></span> <span data-ttu-id="f7c2c-129">ファイルのパスワードがわかっている場合は、それらを開いてパスワード保護を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-129">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="f7c2c-130">tact で修復されたファイルのディレクトリ構造とファイル名を保持することが重要です。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-130">IT is important that you retain the directory structure and file names of the remediated files in tact.</span></span>  <span data-ttu-id="f7c2c-131">ダウンロードしたファイルとフォルダーで使用されているすべての命名規則によって、remdiated ファイルを元のファイルに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-131">All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="f7c2c-132">データの調査 (プレビュー) に戻り、[**次へ: ファイルのアップロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-132">Now, return to Data Investigations (Preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="f7c2c-133">これにより、次の手順に進み、ファイルをアップロードできるようになります。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-133">This will move to the next step where you can now upload the files.</span></span>

    ![ファイルをアップロードする](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="f7c2c-135">[**ファイルの場所へのパス**] テキストボックスで、修復したファイルの場所を指定してから、[マイ**ボードにコピー] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-135">Specifiy the location of the remediated files in the **Path to location of files** text box, then click **Copy to clibpboard**.</span></span>

10. <span data-ttu-id="f7c2c-136">コマンドを Windows コマンドプロンプトに貼り付け、 **enter**キーを押してファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-136">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="f7c2c-138">最後に、データ調査 (プレビュー) に戻り、[**次へ: プロセスファイル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-138">Finally, return to Data Investigations (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="f7c2c-139">処理が完了したとき。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-139">When processing is complete.</span></span>  <span data-ttu-id="f7c2c-140">ワーキングセットに戻り、修復されたファイルを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-140">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="f7c2c-141">ファイルが修復されたときの処理</span><span class="sxs-lookup"><span data-stu-id="f7c2c-141">What happens when files are remediated</span></span>

<span data-ttu-id="f7c2c-142">修復済みのファイルがアップロードされると、元のメタデータは次のフィールドを除いて保持されます。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-142">When remediated files are uploaded, the original metadata is preserved with the exception of the following fields:</span></span> 

- <span data-ttu-id="f7c2c-143">DocumentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="f7c2c-143">DocumentExtractedUrl</span></span>
- <span data-ttu-id="f7c2c-144">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="f7c2c-144">ExtractedTextSize</span></span>
- <span data-ttu-id="f7c2c-145">HasText</span><span class="sxs-lookup"><span data-stu-id="f7c2c-145">HasText</span></span>
- <span data-ttu-id="f7c2c-146">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="f7c2c-146">IsErrorRemediate</span></span>
- <span data-ttu-id="f7c2c-147">IsParentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="f7c2c-147">IsParentExtractedUrl</span></span>
- <span data-ttu-id="f7c2c-148">ItemExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="f7c2c-148">ItemExtractedUrl</span></span>
- <span data-ttu-id="f7c2c-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="f7c2c-149">LoadId</span></span>
- <span data-ttu-id="f7c2c-150">processingerrormessage</span><span class="sxs-lookup"><span data-stu-id="f7c2c-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="f7c2c-151">processingstatus</span><span class="sxs-lookup"><span data-stu-id="f7c2c-151">ProcessingStatus</span></span>
- <span data-ttu-id="f7c2c-152">テキスト</span><span class="sxs-lookup"><span data-stu-id="f7c2c-152">Text</span></span>
- <span data-ttu-id="f7c2c-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="f7c2c-153">WordCount</span></span>
- <span data-ttu-id="f7c2c-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="f7c2c-154">WorkingsetId</span></span>

<span data-ttu-id="f7c2c-155">データ調査 (プレビュー) 内のすべてのドキュメントメタデータフィールドの定義については、「[ドキュメントメタデータフィールド](document-metadata-fields.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7c2c-155">For a definition of all document metadata fields in Data Investigations (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>