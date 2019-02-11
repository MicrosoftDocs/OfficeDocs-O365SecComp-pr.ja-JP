---
title: 検索を作成してデータを収集する
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
ms.openlocfilehash: 773137cbfc73d449766e04bf7eccc77f8bdd0cca
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706138"
---
# <a name="create-a-search-to-collect-data"></a><span data-ttu-id="9d56b-102">検索を作成してデータを収集する</span><span class="sxs-lookup"><span data-stu-id="9d56b-102">Create a search to collect data</span></span>

<span data-ttu-id="9d56b-103">場合、[**検索**] タブに**新しい検索**をクリックしてウィザードを次に新しい検索を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9d56b-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

## <a name="name-your-search-and-give-description"></a><span data-ttu-id="9d56b-104">検索の名前し、説明を付ける</span><span class="sxs-lookup"><span data-stu-id="9d56b-104">Name your search and give description</span></span>

<span data-ttu-id="9d56b-p101">ケースと検索には、一意の名前が必要です。検索の説明を入力することができます (オプション)。</span><span class="sxs-lookup"><span data-stu-id="9d56b-p101">Each search with a case should have a unique name. You can optionally provide a description for your search.</span></span> 

## <a name="define-your-conditions"></a><span data-ttu-id="9d56b-107">条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="9d56b-107">Define your conditions</span></span>

<span data-ttu-id="9d56b-p102">検索条件があらかじめ用意されているカードを使用するか、キーワード クエリ言語 (KQL) を使用するための条件を定義できます。詳細については、[検索クエリのビルド](building-search-queries.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d56b-p102">You can define the conditions for your search using the pre-built condition cards or using Keyword Query Language (KQL). For more information, see [Build search queries](building-search-queries.md).</span></span>

## <a name="choose-the-custodians-to-search-from"></a><span data-ttu-id="9d56b-110">通告から検索する」を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d56b-110">Choose the custodians to search from</span></span>

<span data-ttu-id="9d56b-p103">条件を定義すると、検索する場所を選択する必要があります。検索を行う場合に既に追加したどの通告を指定することでは、これを行う方法の 1 つ。保管担当者を選択すると、書にマップされているすべてのデータ ソースに対して検索を実行します。通告をケースに追加し、そのデータ ソースを管理する方法の詳細については、[通告の作業](managing-custodians.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d56b-p103">Once you have defined your conditions, you need to choose which locations you want to search. One way to do it is by specifying which custodians you have already added to the case you want to search. By selecting a custodian, you will run the search against all data sources mapped to the custodian. See [Work with custodians](managing-custodians.md) for more information on how to add custodians to your case and manage their data sources.</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="9d56b-115">非信託の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d56b-115">Choose non-custodial locations</span></span>

<span data-ttu-id="9d56b-p104">いくつかの場合、管理者に割り当てられていないデータ ソースを検索することができます。この例では、検索、またはビジネスのサイトのすべての Exchange メールボックスまたはすべての SharePoint と OneDrive を検索する) など、特定の Office 365 サービスのすべてのコンテンツの場所を検索する」を選択したい場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9d56b-p104">In some cases, you may wish to search data sources that are not mapped to a custodian. In this case, you can specify the locations you would like to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint and OneDrive for Business sites).</span></span>