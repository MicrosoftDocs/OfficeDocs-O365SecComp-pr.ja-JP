---
title: キーワード ディクショナリを作成する
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/11/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 機密情報を識別する際、特に汎用コンテンツ (医療関連のコミュニケーションなど) や不適切または露骨な言語を識別するのに、キーワードの検索が必要になることがあります。機密情報の種類でもキーワード リストを作成できますが、キーワード リストにはサイズ制限があり、作成や編集のためには XML を変更する必要があります。キーワード ディクショナリでは、よりシンプルかつより大規模にキーワードを管理することができます。ディクショナリあたり最大 100,000 語をサポートします。
ms.openlocfilehash: 5e99cad328115ad6b49982ea4c5749cdea6e43ed
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230791"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="d5672-105">キーワード ディクショナリを作成する</span><span class="sxs-lookup"><span data-stu-id="d5672-105">Create a keyword dictionary</span></span>

<span data-ttu-id="d5672-106">Office 365 のデータ損失防止 (DLP) は、機密情報を識別、監視、保護することができます。</span><span class="sxs-lookup"><span data-stu-id="d5672-106">Data loss prevention (DLP) in Office 365 can identify, monitor, and protect your sensitive information.</span></span> <span data-ttu-id="d5672-107">機密情報を特定するには、特に、一般的なコンテンツ (医療関連の通信など) や不適切または明示的な言語を特定するときにキーワードの検索が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="d5672-107">Identifying sensitive information sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="d5672-108">キーワードリストは機密情報の種類に作成できますが、キーワードリストのサイズは制限されており、作成または編集するには XML を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5672-108">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="d5672-109">キーワード辞書を使用すると、キーワードを簡単に管理でき、より大きなスケールで、1つの辞書に最大10万用語をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d5672-109">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100,000 terms per dictionary.</span></span>
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="d5672-110">キーワード ディクショナリを作成する基本的な手順</span><span class="sxs-lookup"><span data-stu-id="d5672-110">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="d5672-p103">ディクショナリのキーワードを、さまざまなソースから作成することができます。一般的な例として、サービスにインポートされたファイルや PowerShell コマンドレットでインポートされたファイル (.csv または .txt リストなど)、PowerShell コマンドレットで直接入力するリスト、または既存のディクショナリなどがあります。キーワード ディクショナリを作成するときには、次の同じ基本手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d5672-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="d5672-113">**セキュリティ & コンプライアンスセンター** ([https://protection.office.com](https://protection.office.com)) を使用するか、 **Office 365 セキュリティ&amp;コンプライアンスセンターの PowerShell**に接続します。</span><span class="sxs-lookup"><span data-stu-id="d5672-113">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Office 365 Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="d5672-114">**目的のソースからキーワードを定義または読み込み**ます。</span><span class="sxs-lookup"><span data-stu-id="d5672-114">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="d5672-115">ウィザードとコマンドレットはどちらも、ユーザー設定のキーワード辞書を作成するためのキーワードのコンマ区切りのリストを受け入れます。この手順は、キーワードの取得元に応じて若干異なります。</span><span class="sxs-lookup"><span data-stu-id="d5672-115">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="d5672-116">いったん読み込まれたキーワードは、インポートされる前にエンコードされてバイト配列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="d5672-116">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="d5672-117">**辞書を作成**します。</span><span class="sxs-lookup"><span data-stu-id="d5672-117">**Create your dictionary**.</span></span> <span data-ttu-id="d5672-118">名前と説明を選択し、辞書を作成します。</span><span class="sxs-lookup"><span data-stu-id="d5672-118">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="d5672-119">セキュリティ & コンプライアンスセンターを使用してキーワードディクショナリを作成する</span><span class="sxs-lookup"><span data-stu-id="d5672-119">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="d5672-120">ユーザー辞書のキーワードを作成してインポートするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5672-120">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="d5672-121">セキュリティ & コンプライアンスセンター ([https://protection.office.com](https://protection.office.com)) に接続します。</span><span class="sxs-lookup"><span data-stu-id="d5672-121">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="d5672-122">**[分類] > [機密情報の種類]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d5672-122">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="d5672-123">**[作成]** を選択し、機密情報の**名前**と**説明**を入力してから、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5672-123">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="d5672-124">**[要素を追加する]** を選択し、**[次を含むコンテンツを検出する]** ドロップダウン リストの中から **[辞書 (大規模なキーワード)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5672-124">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="d5672-125">**[辞書を追加する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5672-125">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="d5672-126">検索コントロールで、**[ここで新しいキーワード ディクショナリを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5672-126">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="d5672-127">ユーザー辞書の**名前**を入力します。</span><span class="sxs-lookup"><span data-stu-id="d5672-127">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="d5672-128">**[インポート]** を選択し、キーワード ファイルの種類に応じて **[テキストから]** か **[csv から]** のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="d5672-128">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="d5672-129">ファイル ダイアログで、ローカル PC またはネットワーク ファイル共有からキーワード ファイルを選択し、**[開く]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5672-129">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="d5672-130">**[保存]** を選択し、**[キーワード ディクショナリ]** リストから該当するユーザー辞書を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5672-130">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="d5672-131">**[追加]** を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5672-131">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="d5672-132">機密情報の種類の選択を最終的に確認し、**[終了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5672-132">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="d5672-133">PowerShell を使用してファイルからキーワード ディクショナリを作成する</span><span class="sxs-lookup"><span data-stu-id="d5672-133">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="d5672-134">多くの場合、大きい辞書を作成する必要がある場合は、ファイルまたは他のソースからエクスポートされたリストのキーワードを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d5672-134">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="d5672-135">この例では、外部電子メールで画面に表示するのに適していない言語のリストを含むキーワードディクショナリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5672-135">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="d5672-136">最初[に Office 365 セキュリティ&amp;コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5672-136">You must first [connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="d5672-137">キーワードをテキスト ファイルにコピーし、各キーワードが別個の行にあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d5672-137">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="d5672-p107">テキスト ファイルを、Unicode エンコードで、メモ帳 \> **名前を付けて保存** \> **エンコード** \> **Unicode** に保存します。</span><span class="sxs-lookup"><span data-stu-id="d5672-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="d5672-140">このコマンドレットを実行して、ファイルを変数として読み取ります。</span><span class="sxs-lookup"><span data-stu-id="d5672-140">Read the file into a variable by running this cmdlet:</span></span>
    
    ```
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="d5672-141">このコマンドレットを実行して、ディクショナリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5672-141">Create the dictionary by running this cmdlet:</span></span>
    
    ```
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="d5672-142">既存のキーワード ディクショナリを変更する</span><span class="sxs-lookup"><span data-stu-id="d5672-142">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="d5672-143">キーワード ディクショナリのいずれかでキーワードを変更したり、組み込みのディクショナリのいずれかを変更したりする必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="d5672-143">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="d5672-144">現在のところ、PowerShell を使用してのみ、カスタム キーワード ディクショナリを更新できます。</span><span class="sxs-lookup"><span data-stu-id="d5672-144">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="d5672-145">たとえば、いくつかの用語を PowerShell で変更し、それらをエディターで変更できるようにローカルに保存してから、以前の用語をインプレースで更新します。</span><span class="sxs-lookup"><span data-stu-id="d5672-145">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="d5672-146">最初に、ディクショナリ オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d5672-146">First, retrieve the dictionary object:</span></span>
  
```
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="d5672-147">印刷`$dict`にはさまざまな変数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5672-147">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="d5672-148">キーワード自体はバックエンドのオブジェクトに格納されますが`$dict.KeywordDictionary` 、辞書を変更するために使用する文字列表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d5672-148">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="d5672-149">辞書を変更する前に、 `.split(',')`メソッドを使用して用語の文字列を配列に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5672-149">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="d5672-150">その後、 `.trim()`メソッドを使用してキーワード間の不要なスペースをクリーンアップし、操作するキーワードだけを残します。</span><span class="sxs-lookup"><span data-stu-id="d5672-150">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="d5672-p111">ここでは、ディクショナリから一部の用語を削除します。例のディクショナリには少しのキーワードしかないので、ディクショナリのエクスポートとノートパッドでの編集に簡単にスキップすることができますが、通常、ディクショナリには大量のテキストが含まれているので PowerShell で簡単に編集を行うこの方法をまず確認しておいてください。</span><span class="sxs-lookup"><span data-stu-id="d5672-p111">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="d5672-p112">最後の手順で、キーワードを配列に保存しました。[配列から項目を削除する](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))にはいくつか方法がありますが、簡単なのは、ディクショナリから削除する用語の配列を作成して、削除する用語のリストには含まれないディクショナリの用語だけをそこにコピーする方法です。</span><span class="sxs-lookup"><span data-stu-id="d5672-p112">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="d5672-p113">コマンド `$terms` を実行して、現在の用語のリストを表示します。コマンドの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d5672-p113">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
```
aarskog's syndrome
abandonment
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipoproteinemia
abiotrophy
ablatio
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

<span data-ttu-id="d5672-157">このコマンドを実行して、削除する用語を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5672-157">Run this command to specify the terms that you want to remove:</span></span>
  
```
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="d5672-158">リストから用語を実際に削除するには、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5672-158">Run this command to actually remove the terms from the list:</span></span>
  
```
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="d5672-p114">コマンド `$updatedTerms` を実行して、更新された用語のリストを表示します。コマンドの出力は次のようになります (指定した用語は削除されています)。</span><span class="sxs-lookup"><span data-stu-id="d5672-p114">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
```
aarskog's syndrome
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipo proteinemia
abiotrophy
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

<span data-ttu-id="d5672-p115">ここでは、ディクショナリをローカルに保存して、用語をいくつか追加します。PowerShell で直接用語を追加できますが、確実に Unicode エンコードで保存し BOM が含まれるようにするために、ファイルをローカルでエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5672-p115">Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.</span></span>
  
<span data-ttu-id="d5672-163">次のように実行してディクショナリをローカルに保存します。</span><span class="sxs-lookup"><span data-stu-id="d5672-163">Save the dictionary locally by running the following:</span></span>
  
```
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="d5672-p116">次にファイルを開いて、補足する用語を追加し、Unicode エンコード (UTF-16) で保存します。それから更新した用語をアップロードして、ディクショナリを所定の場所で更新します。</span><span class="sxs-lookup"><span data-stu-id="d5672-p116">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="d5672-p117">これでディクショナリが、所定の場所で更新されました。`Identity` フィールドは、ディクショナリの名前になります。`set-` コマンドレットを使ってディクショナリの名前を変更したい場合は、`-Name` パラメーターを新しいディクショナリの名前と合わせて上記に追加します。</span><span class="sxs-lookup"><span data-stu-id="d5672-p117">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="d5672-169">カスタムの機密情報の種類と DLP ポリシーでキーワード ディクショナリを使う</span><span class="sxs-lookup"><span data-stu-id="d5672-169">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="d5672-170">キーワード辞書は、カスタムの機密情報の種類の一致要件の一部として、または機密情報の種類自体として使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5672-170">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="d5672-171">どちらの場合も、[カスタムの機密情報の種類](create-a-custom-sensitive-information-type-in-scc-powershell.md)を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5672-171">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="d5672-172">リンクされた記事の手順に従って、機密情報の種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="d5672-172">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="d5672-173">XML を取得したら、それを使用するには、ディクショナリの GUID 識別子が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d5672-173">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="d5672-174">ディクショナリの ID を取得するには、このコマンドを実行して **ID** のプロパティ値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="d5672-174">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="d5672-175">コマンドの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d5672-175">The output of the command looks like this:</span></span>
  
```
RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255
Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f
Name              : Diseases
Description       : Names of diseases and injuries from ICD-10-CM lexicon
KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo
                    proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,
                    abrami's disease, abramo
IsValid           : True
ObjectState       : Unchanged
```

<span data-ttu-id="d5672-p119">カスタムの機密情報の種類の XML に ID を貼り付けて、アップロードします。これで、ディクショナリは機密情報の種類のリストに表示され、それをポリシーで使用して、一致するキーワードがいくつ必要かを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="d5672-p119">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
```
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```


