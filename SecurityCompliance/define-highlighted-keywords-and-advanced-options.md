---
title: Office 365 の高度な電子情報開示で強調表示されたキーワードと詳細オプションを定義する
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 03cc4387-2c7d-4058-8a44-0deefb58f011
description: 'ユーザー定義のキーワードを関連性に追加して、Office 365 の高度な電子情報開示でのタグ付けとコストパラメータを指定する際に関連ファイルを特定する方法について説明します。  '
ms.openlocfilehash: 4542e80e5324a35df2e7dc8e7e0cf09f37ae1ef4
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153389"
---
# <a name="define-highlighted-keywords-and-advanced-options-in-office-365-advanced-ediscovery"></a><span data-ttu-id="67388-103">Office 365 の高度な電子情報開示で強調表示されたキーワードと詳細オプションを定義する</span><span class="sxs-lookup"><span data-stu-id="67388-103">Define highlighted keywords and advanced options in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="67388-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="67388-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="67388-106">詳細な電子情報開示では、ユーザー定義のキーワードを関連性に追加して、タグ付けの際に関連ファイルを識別するのに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="67388-106">In Advanced eDiscovery, it's possible to add user-defined keywords to Relevance in order to help you identify relevant files while tagging.</span></span> <span data-ttu-id="67388-107">キーワードは、**関連性\>タグ**の指定した色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="67388-107">Keywords will be displayed in the specified colors in **Relevance \> Tag**.</span></span> 
  
<span data-ttu-id="67388-108">以下に示すように、キーワードリストを追加したり、キーワードリストに割り当てられている色や関連する問題を追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="67388-108">As described below, keyword lists can be added, and colors assigned to the Keywords list and the related issues.</span></span> <span data-ttu-id="67388-109">ヒントには、キーワードの説明 (存在する場合) が、二重下線で示されます。</span><span class="sxs-lookup"><span data-stu-id="67388-109">A tooltip displays the keyword's description, if one exists, as indicated by a double underline.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="67388-110">関連性のタグ付け時にドキュメント内の関連性の強調表示とキーワードヒット結果の表示は、日本語、中国語、韓国語の2バイト文字セットでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="67388-110">Hit highlighting in Relevance and viewing keyword hit results within documents during Relevance tagging does not work for the Japanese, Chinese, and Korean double-byte character sets.</span></span> 
  
## <a name="adding-highlighted-keywords"></a><span data-ttu-id="67388-111">強調表示されたキーワードの追加</span><span class="sxs-lookup"><span data-stu-id="67388-111">Adding highlighted keywords</span></span>

1. <span data-ttu-id="67388-112">[**関連性\>の関連性の設定**] タブで、[**強調表示**されたキーワード] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67388-112">In the **Relevance \> Relevance setup** tab, select **Highlighted keywords**.</span></span>
    
2. <span data-ttu-id="67388-113">アイコンを**+** クリックしてキーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="67388-113">Click the **+** icon to add keywords.</span></span> <span data-ttu-id="67388-114">[**新しいキーワードの追加**] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="67388-114">The **Add new keywords** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="67388-115">[**キーワード**] にキーワードリストを入力します。キーワードはコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="67388-115">In **Keywords**, type the keywords list, separating keywords with commas.</span></span> 
    
4. <span data-ttu-id="67388-116">[**色**] ボックスの一覧で色を選択し、[入力したキーワード] ボックスの一覧を強調表示にします。</span><span class="sxs-lookup"><span data-stu-id="67388-116">In the **Color** list, select the color to highlight the entered keywords list.</span></span> 
    
5. <span data-ttu-id="67388-117">**[問題の選択**] リストで、[キーワード] リストを [すべての問題] に適用するか、選択した案件に適用するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="67388-117">In the **Select issue** list, select whether to apply the keywords list to "All issues" or to selected issues.</span></span> 
    
6. <span data-ttu-id="67388-118">[**説明**] に、キーワードリスト (省略可能) を入力します。</span><span class="sxs-lookup"><span data-stu-id="67388-118">In **Description**, type the keywords list (optional).</span></span>
    
    ![新しいキーワードの追加](media/1683a71f-0875-48fc-b4ef-01f3b0e8e8e9.png)
  
7. <span data-ttu-id="67388-120">完了したら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67388-120">Click **OK** when done.</span></span> <span data-ttu-id="67388-121">作成したリストがキーワードリストテーブルに追加され、編集または削除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="67388-121">The created list is added to the keywords list table and can be edited or deleted.</span></span> 
    
    ![関連性の設定のキーワードの一覧](media/a05d5ec0-8bde-470d-97e2-456b169281d6.png)
  
<span data-ttu-id="67388-123">ユーザー定義のキーワードが、[関連性\> ] タグの指定した色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="67388-123">The user-defined keywords will be displayed, in the specified colors in Relevance \> Tag.</span></span> 
  
## <a name="specifying-relevance-setup-advanced-settings"></a><span data-ttu-id="67388-124">関連性セットアップの詳細設定の指定</span><span class="sxs-lookup"><span data-stu-id="67388-124">Specifying Relevance setup advanced settings</span></span>

<span data-ttu-id="67388-125">これらの設定は、関連性のあるトラックと判断グラフに影響します。</span><span class="sxs-lookup"><span data-stu-id="67388-125">These settings affect the Track and Decide graphs in Relevance.</span></span>
  
1. <span data-ttu-id="67388-126">[**関連性\>の関連性の設定**] タブで、[**詳細設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67388-126">In the **Relevance \> Relevance setup** tab, select **Advanced settings**.</span></span>
    
2. <span data-ttu-id="67388-127">[**コストパラメーター** ] ダイアログで、次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="67388-127">In the **Cost parameters** dialog, make the following selections:</span></span> 
    
1. <span data-ttu-id="67388-128">1**時間あたりのコストレビュー ($)** の一覧で、[金額] を選択するか、既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="67388-128">In the **Cost review per hour ($)** list, select the amount in dollars or accept the default.</span></span> 
    
2. <span data-ttu-id="67388-129">[**時間で確認されたファイルの数**] ボックスの一覧で、金額を選択するか、既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="67388-129">In the **Number of files reviewed by hour** list, select the amount or accept the default.</span></span> 
    
    ![関連性の設定のコストのパラメーター](media/bab7b5b7-6297-4e7c-b0a6-ba5aa8b21787.png)
  
3. <span data-ttu-id="67388-131">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67388-131">Click **Save**.</span></span> <span data-ttu-id="67388-132">選択した設定が保存されます。</span><span class="sxs-lookup"><span data-stu-id="67388-132">The selected settings are saved.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="67388-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="67388-133">See also</span></span>

[<span data-ttu-id="67388-134">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="67388-134">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="67388-135">問題の定義とユーザーの割り当て</span><span class="sxs-lookup"><span data-stu-id="67388-135">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="67388-136">インポートしたファイルを追加するためのロードの設定</span><span class="sxs-lookup"><span data-stu-id="67388-136">Setting up loads to add imported files</span></span>](set-up-loads-to-add-imported-files.md)

