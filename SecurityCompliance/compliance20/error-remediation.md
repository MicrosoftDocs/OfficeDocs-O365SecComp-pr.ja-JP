---
title: データの処理中にエラーの修復
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 82e6d44ded64d586611f429f9b3eebe4f47e9898
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608060"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="71a3b-102">データの処理中にエラーの修復</span><span class="sxs-lookup"><span data-stu-id="71a3b-102">Error remediation when processing data</span></span>

<span data-ttu-id="71a3b-p101">エラーの修復は、高度な電子的証拠開示 (プレビュー) がコンテンツを正しく処理することを防止するデータに関する問題を修正する機能を電子的証拠開示の管理者に使用できます。たとえば、ファイルがロックされているか、暗号化されているために、パスワードで保護されているファイルを処理できません。エラーの修復を使用すると、電子的証拠開示管理者ことができますこのようなエラーがあるファイルをダウンロード、パスワード保護を削除および修正されたファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="71a3b-p101">Error remediation allows eDiscovery administrators the ability to rectify data issues which prevent Advanced eDiscovery (Preview) from properly processing the content. For example, files that are password protected cannot be processed since the files are locked or encrypted. Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection and upload the remediated files.</span></span>

<span data-ttu-id="71a3b-106">高度な電子的証拠開示 (プレビュー) の場合にエラーがあるファイルを修正するのにには、次のワークフローを使用します。</span><span class="sxs-lookup"><span data-stu-id="71a3b-106">Use the following workflow to remediate files with errors in Advanced eDiscovery (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="71a3b-107">処理エラーを含むファイルを修正するのには、エラー修復のセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="71a3b-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="71a3b-108">場合、エラーの修復ウィザードを閉じると、次の手順の実行中にいつでもに戻れるエラー修復のセッションは、[**処理**] タブから **「ビュー** 」ドロップ ダウン メニューで**エラーの改善点**を選択するとします。</span><span class="sxs-lookup"><span data-stu-id="71a3b-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="71a3b-109">高度な電子的証拠開示 (プレビュー) 場合は、[**処理**] タブでは、 **「ビュー** 」ドロップ ダウン メニューで**エラー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="71a3b-109">On the **Processing** tab in an Advanced eDiscovery (Preview) case, select **Errors** in the **View** drop down menu.</span></span>

2. <span data-ttu-id="71a3b-p102">エラーの種類またはファイルの種類のいずれかのラジオボタンをクリックして修正するエラーを選択します。 次の例では、パスワード保護されたファイルを得られるようにしていること。</span><span class="sxs-lookup"><span data-stu-id="71a3b-p102">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.  In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="71a3b-112">**+ 新しいエラーの修復**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71a3b-112">Click **+ New error remediation**.</span></span>

    ![エラーの修復](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="71a3b-114">そのエラーになったファイルは、移動先 Azure の安全な場所にダウンロードする準備の段階から始まるエラー修復のセッションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="71a3b-114">The error remediation session will begin, starting with a preparation stage where the files that errored are moved to a secure Azure location to be downloaded.</span></span>

    ![エラー修復の準備をしています。](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="71a3b-116">準備が完了したらをクリックして**次: ファイルをダウンロード**ダウンロードを続行します。</span><span class="sxs-lookup"><span data-stu-id="71a3b-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![ファイルをダウンロードします。](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="71a3b-p103">ファイルをダウンロードするには、**ダウンロード先のパス**を指定しますこれは、ファイルをダウンロードするかローカル コンピューター上のパスです。 %Userprofile%\downloads\errors、既定のパスがログインしているユーザーのダウンロードのフォルダーを指すこれは、必要に応じて変更できます。</span><span class="sxs-lookup"><span data-stu-id="71a3b-p103">To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.  The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="71a3b-120">最適なパフォーマンスのため、リモートのネットワーク パスではなくローカル ファイル パスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="71a3b-120">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="71a3b-121">AzCopy をインストールしていない場合は、ここからインストールできます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="71a3b-121">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="71a3b-p104">定義済みのコマンドをコピーするには、**クリップボードにコピー**] をクリックします。Windows コマンド プロンプトを起動、コマンドを貼り付け、 **Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="71a3b-p104">Copy the predefined command by clicking **Copy to clipboard**. Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="71a3b-124">ファイルがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="71a3b-124">The files will be downloaded.</span></span>

    ![エラー修復の準備をしています。](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > <span data-ttu-id="71a3b-126">このコマンドを実行中に問題があればを参照してくださいhttps://go.microsoft.com/fwlink/?linkid=2038117のトラブルシューティングのヒントします。</span><span class="sxs-lookup"><span data-stu-id="71a3b-126">If you have issues running this command, see https://go.microsoft.com/fwlink/?linkid=2038117 for troubleshooting tips.</span></span>

7. <span data-ttu-id="71a3b-p105">ファイルをダウンロードした後、適切なツールを使用して修正することができます。パスワードで保護されたファイルがいくつかのパスワード クラッキング ツールを使用することができます。ファイルのパスワードがわかっている場合は、開くし、パスワード保護を解除します。</span><span class="sxs-lookup"><span data-stu-id="71a3b-p105">After downloading the files, you can remediate them with an appropriate tool. For password protected files, there are a number of password cracking tools you can use. If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="71a3b-p106">IT の整合性を修正されたファイルのディレクトリ構造とファイル名を保持することが重要です。 ダウンロードしたファイルですべての名前付け規則が使用されているフォルダーを使うと、元の remdiated ファイルを関連付けるには。</span><span class="sxs-lookup"><span data-stu-id="71a3b-p106">IT is important that you retain the directory structure and file names of the remediated files in tact.  All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="71a3b-p107">ここで、高度な電子的証拠開示 (プレビュー) を返し] をクリックして**次: ファイルをアップロードする**です。 ファイルを今すぐアップロードする、次の手順に移動します。</span><span class="sxs-lookup"><span data-stu-id="71a3b-p107">Now, return to Advanced eDiscovery (Preview) and click **Next: Upload files**.  This will move to the next step where you can now upload the files.</span></span>

    ![ファイルをアップロードします。](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="71a3b-135">**ファイルの場所へのパス**のテキスト ボックスで、修正されたファイルの場所を指定してくださいでは、 **clibpboard にコピー**しをクリックします。</span><span class="sxs-lookup"><span data-stu-id="71a3b-135">Specifiy the location of the remediated files in the **Path to location of files** text box, then click **Copy to clibpboard**.</span></span>

10. <span data-ttu-id="71a3b-136">コマンドを Windows コマンド プロンプトに貼り付けるし、ファイルをアップロードするのには**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="71a3b-136">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="71a3b-138">最後に、高度な電子的証拠開示 (プレビュー) を返すをクリックして**次: ファイルを処理する**です。</span><span class="sxs-lookup"><span data-stu-id="71a3b-138">Finally, return to Advanced eDiscovery (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="71a3b-p108">処理が完了します。 ワーキング セットに戻るし、修正されたファイルを参照してくださいことができます。</span><span class="sxs-lookup"><span data-stu-id="71a3b-p108">When processing is complete.  You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="71a3b-141">ファイルを改善するときの動作します。</span><span class="sxs-lookup"><span data-stu-id="71a3b-141">What happens when files are remediated</span></span>

<span data-ttu-id="71a3b-142">修正されたファイルがアップロードされると、次のフィールドを除いて元のメタデータが保持されます。</span><span class="sxs-lookup"><span data-stu-id="71a3b-142">When remediated files are uploaded, the original metadata is preserved with the exception of the following fields:</span></span> 

- <span data-ttu-id="71a3b-143">DocumentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="71a3b-143">DocumentExtractedUrl</span></span>
- <span data-ttu-id="71a3b-144">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="71a3b-144">ExtractedTextSize</span></span>
- <span data-ttu-id="71a3b-145">HasText</span><span class="sxs-lookup"><span data-stu-id="71a3b-145">HasText</span></span>
- <span data-ttu-id="71a3b-146">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="71a3b-146">IsErrorRemediate</span></span>
- <span data-ttu-id="71a3b-147">IsParentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="71a3b-147">IsParentExtractedUrl</span></span>
- <span data-ttu-id="71a3b-148">ItemExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="71a3b-148">ItemExtractedUrl</span></span>
- <span data-ttu-id="71a3b-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="71a3b-149">LoadId</span></span>
- <span data-ttu-id="71a3b-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="71a3b-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="71a3b-151">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="71a3b-151">ProcessingStatus</span></span>
- <span data-ttu-id="71a3b-152">テキスト</span><span class="sxs-lookup"><span data-stu-id="71a3b-152">Text</span></span>
- <span data-ttu-id="71a3b-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="71a3b-153">WordCount</span></span>
- <span data-ttu-id="71a3b-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="71a3b-154">WorkingsetId</span></span>

<span data-ttu-id="71a3b-155">高度な電子的証拠開示 (プレビュー) 内のすべてのドキュメントのメタデータのフィールドの定義、[ドキュメントのメタデータ フィールド](document-metadata-fields.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71a3b-155">For a definition of all document metadata fields in Advanced eDiscovery (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>