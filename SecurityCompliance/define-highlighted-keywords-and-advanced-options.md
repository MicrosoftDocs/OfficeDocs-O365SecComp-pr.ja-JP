---
title: Office 365 Advanced eDiscovery で強調表示されたキーワードと高度なオプションを定義する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 03cc4387-2c7d-4058-8a44-0deefb58f011
description: 'コスト パラメーターを指定して Office 365 の高度な電子的証拠の開示にタグ付けしているときに関連するファイルを識別するために関連するユーザー定義のキーワードを追加する方法について説明します。  '
ms.openlocfilehash: c7e16fc18ba724d5b778b42e3782e04df10c50ec
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531983"
---
# <a name="define-highlighted-keywords-and-advanced-options-in-office-365-advanced-ediscovery"></a><span data-ttu-id="0377a-103">Office 365 Advanced eDiscovery で強調表示されたキーワードと高度なオプションを定義する</span><span class="sxs-lookup"><span data-stu-id="0377a-103">Define highlighted keywords and advanced options in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="0377a-p101">高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="0377a-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="0377a-p102">高度な電子的証拠開示は、タグ付けしているときに関連するファイルを識別するために関連するユーザー定義のキーワードを追加します。キーワードで指定した色で表示されます**関連\>タグ**。</span><span class="sxs-lookup"><span data-stu-id="0377a-p102">In Advanced eDiscovery, it's possible to add user-defined keywords to Relevance in order to help you identify relevant files while tagging. Keywords will be displayed in the specified colors in **Relevance \> Tag**.</span></span> 
  
<span data-ttu-id="0377a-p103">後述のように、キーワード リストを追加することができますと、キーワードのリストと関連する問題に色が割り当てられています。ツールヒントに表示されますキーワードの説明では、いずれかが存在する場合は、二重下線で示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="0377a-p103">As described below, keyword lists can be added, and colors assigned to the Keywords list and the related issues. A tooltip displays the keyword's description, if one exists, as indicated by a double underline.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0377a-110">ヒット結果のヒットの関連性の強調表示とキーワードを表示する関連性の中にドキュメント内でタグ付けが行われない日本語、中国語、韓国語の 2 バイト文字セットです。</span><span class="sxs-lookup"><span data-stu-id="0377a-110">Hit highlighting in Relevance and viewing keyword hit results within documents during Relevance tagging does not work for the Japanese, Chinese, and Korean double-byte character sets.</span></span> 
  
## <a name="adding-highlighted-keywords"></a><span data-ttu-id="0377a-111">強調表示されているキーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0377a-111">Adding highlighted keywords</span></span>

1. <span data-ttu-id="0377a-112">**の関連性\>関連性の高いセットアップ**] タブで、 **[強調表示のキーワード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0377a-112">In the **Relevance \> Relevance setup** tab, select **Highlighted keywords**.</span></span>
    
2. <span data-ttu-id="0377a-p104">クリックして、**+** のキーワードを追加するアイコン。**新しいキーワードを追加**] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0377a-p104">Click the **+** icon to add keywords. The **Add new keywords** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="0377a-115">**キーワード**キーワードをコンマで区切ります、キーワードのリストを入力します。</span><span class="sxs-lookup"><span data-stu-id="0377a-115">In **Keywords**, type the keywords list, separating keywords with commas.</span></span> 
    
4. <span data-ttu-id="0377a-116">[**色**] 一覧で、入力したキーワードのリストを強調表示する色を選択します。</span><span class="sxs-lookup"><span data-stu-id="0377a-116">In the **Color** list, select the color to highlight the entered keywords list.</span></span> 
    
5. <span data-ttu-id="0377a-117">**問題の選択**] ボックスの一覧で選択した懸案事項をすべての問題」に、[キーワード] ボックスの一覧を適用するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="0377a-117">In the **Select issue** list, select whether to apply the keywords list to "All issues" or to selected issues.</span></span> 
    
6. <span data-ttu-id="0377a-118">**説明**キーワードのリスト (省略可能) を入力します。</span><span class="sxs-lookup"><span data-stu-id="0377a-118">In **Description**, type the keywords list (optional).</span></span>
    
    ![新しいキーワードの追加](media/1683a71f-0875-48fc-b4ef-01f3b0e8e8e9.png)
  
7. <span data-ttu-id="0377a-p105">設定が終わったら **[ok]** をクリックします。作成するリストがテーブルに追加のキーワード] ボックスの一覧とことができます編集または削除します。</span><span class="sxs-lookup"><span data-stu-id="0377a-p105">Click **OK** when done. The created list is added to the keywords list table and can be edited or deleted.</span></span> 
    
    ![関連性の設定のキーワードの一覧](media/a05d5ec0-8bde-470d-97e2-456b169281d6.png)
  
<span data-ttu-id="0377a-123">関連性で、指定した色に、ユーザー定義のキーワードが表示されます\>タグです。</span><span class="sxs-lookup"><span data-stu-id="0377a-123">The user-defined keywords will be displayed, in the specified colors in Relevance \> Tag.</span></span> 
  
## <a name="specifying-relevance-setup-advanced-settings"></a><span data-ttu-id="0377a-124">詳細設定の関連性設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="0377a-124">Specifying Relevance setup advanced settings</span></span>

<span data-ttu-id="0377a-125">これらの設定は、関連性のトラックおよび決定のグラフを反映します。</span><span class="sxs-lookup"><span data-stu-id="0377a-125">These settings affect the Track and Decide graphs in Relevance.</span></span>
  
1. <span data-ttu-id="0377a-126">**の関連性\>関連性の高いセットアップ**] タブで、**詳細設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0377a-126">In the **Relevance \> Relevance setup** tab, select **Advanced settings**.</span></span>
    
2. <span data-ttu-id="0377a-127">**コスト パラメーター**ダイアログ ボックスで、次の選択を行います。</span><span class="sxs-lookup"><span data-stu-id="0377a-127">In the **Cost parameters** dialog, make the following selections:</span></span> 
    
1. <span data-ttu-id="0377a-128">**コスト ($) を 1 時間あたりの確認**] ボックスの一覧でドルで、金額を選択して、デフォルトを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="0377a-128">In the **Cost review per hour ($)** list, select the amount in dollars or accept the default.</span></span> 
    
2. <span data-ttu-id="0377a-129">**時間を確認するファイルの数**] ボックスの一覧で金額を選択して、デフォルトを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="0377a-129">In the **Number of files reviewed by hour** list, select the amount or accept the default.</span></span> 
    
    ![関連性の設定のコストのパラメーター](media/bab7b5b7-6297-4e7c-b0a6-ba5aa8b21787.png)
  
3. <span data-ttu-id="0377a-p106">[**保存**] をクリックします。選択した設定が保存されます。</span><span class="sxs-lookup"><span data-stu-id="0377a-p106">Click **Save**. The selected settings are saved.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0377a-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="0377a-133">See also</span></span>

[<span data-ttu-id="0377a-134">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0377a-134">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="0377a-135">問題を定義し、ユーザーの割り当て</span><span class="sxs-lookup"><span data-stu-id="0377a-135">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="0377a-136">インポートしたファイルを追加するのには、荷重を設定</span><span class="sxs-lookup"><span data-stu-id="0377a-136">Setting up loads to add imported files</span></span>](set-up-loads-to-add-imported-files.md)

