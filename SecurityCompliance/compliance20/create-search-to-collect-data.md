---
title: Create a search
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
ms.openlocfilehash: 1aa4ce6e406e4b3a3b72b9d93f651416b1fc65f9
ms.sourcegitcommit: 803baca9f99a6691fb41a3308e799752e4d8f20c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222251"
---
# <a name="create-a-search"></a><span data-ttu-id="16eb2-102">Create a search</span><span class="sxs-lookup"><span data-stu-id="16eb2-102">Create a search</span></span>

<span data-ttu-id="16eb2-103">ケースの [**検索**] タブで、[**新規検索**] をクリックしてウィザードに従って、新しい検索を作成できます。</span><span class="sxs-lookup"><span data-stu-id="16eb2-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

## <a name="name-your-search-and-give-it-a-description"></a><span data-ttu-id="16eb2-104">検索の名前を指定して説明を付ける</span><span class="sxs-lookup"><span data-stu-id="16eb2-104">Name your search and give it a description</span></span>

<span data-ttu-id="16eb2-105">ケースを含む各検索には、一意の名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="16eb2-105">Each search with a case should have a unique name.</span></span> <span data-ttu-id="16eb2-106">必要に応じて、検索の説明を指定できます。</span><span class="sxs-lookup"><span data-stu-id="16eb2-106">You can optionally provide a description for your search.</span></span> 

## <a name="define-your-search-query-and-conditions"></a><span data-ttu-id="16eb2-107">検索クエリと条件を定義する</span><span class="sxs-lookup"><span data-stu-id="16eb2-107">Define your search query and conditions</span></span>

<span data-ttu-id="16eb2-108">作成済みの条件カードを使用するか、またはキーワードクエリ言語 (KQL) を使用して、キーワードクエリと検索条件を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="16eb2-108">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="16eb2-109">詳細については、「 [Build search queries](building-search-queries.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16eb2-109">For more information, see [Build search queries](building-search-queries.md).</span></span>

## <a name="choose-the-custodians-to-search-from"></a><span data-ttu-id="16eb2-110">検索する保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="16eb2-110">Choose the custodians to search from</span></span>

<span data-ttu-id="16eb2-111">条件を定義したら、検索する場所を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16eb2-111">Once you have defined your conditions, you need to choose which locations you want to search.</span></span> <span data-ttu-id="16eb2-112">1つの方法として、検索するケースに既に追加した保管担当者を指定します。</span><span class="sxs-lookup"><span data-stu-id="16eb2-112">One way to do it is by specifying which custodians you have already added to the case you want to search.</span></span> <span data-ttu-id="16eb2-113">保管担当者を選択すると、保管担当者にマップされているすべてのデータソースに対して検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="16eb2-113">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="16eb2-114">ケースに保管担当者を追加し、データソースを管理する方法の詳細については、「 [Work with 保管担当者](managing-custodians.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16eb2-114">See [Work with custodians](managing-custodians.md) for more information on how to add custodians to your case and manage their data sources.</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="16eb2-115">Custodial のダイヤル場所を選択する</span><span class="sxs-lookup"><span data-stu-id="16eb2-115">Choose non-custodial locations</span></span>

<span data-ttu-id="16eb2-116">場合によっては、保管担当者にマップされていないデータソースを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16eb2-116">In some cases, you may wish to search data sources that are not mapped to a custodian.</span></span> <span data-ttu-id="16eb2-117">この場合、検索する場所を指定するか、特定の Office 365 サービスのすべてのコンテンツの場所を検索する (すべての Exchange メールボックスまたはすべての SharePoint および OneDrive for business サイトを検索するなど) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="16eb2-117">In this case, you can specify the locations you would like to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint and OneDrive for Business sites).</span></span>