---
title: 検索を作成してデータを収集する
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
ms.openlocfilehash: 14f90b29cbff9c1a588b816563178039c7af7da6
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295960"
---
# <a name="create-a-search-to-collect-data"></a><span data-ttu-id="27148-102">検索を作成してデータを収集する</span><span class="sxs-lookup"><span data-stu-id="27148-102">Create a search to collect data</span></span>

<span data-ttu-id="27148-103">ケースの [**検索**] タブで、[**新規検索**] をクリックしてウィザードに従って、新しい検索を作成できます。</span><span class="sxs-lookup"><span data-stu-id="27148-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

## <a name="name-your-search-and-give-description"></a><span data-ttu-id="27148-104">検索の名前と説明を指定する</span><span class="sxs-lookup"><span data-stu-id="27148-104">Name your search and give description</span></span>

<span data-ttu-id="27148-p101">ケースを含む各検索には、一意の名前を付ける必要があります。必要に応じて、検索の説明を指定できます。</span><span class="sxs-lookup"><span data-stu-id="27148-p101">Each search with a case should have a unique name. You can optionally provide a description for your search.</span></span> 

## <a name="define-your-conditions"></a><span data-ttu-id="27148-107">条件を定義する</span><span class="sxs-lookup"><span data-stu-id="27148-107">Define your conditions</span></span>

<span data-ttu-id="27148-p102">事前に作成された条件カードを使用して、またはキーワードクエリ言語 (kql) を使用して、検索条件を定義することができます。詳細については、「 [Build search queries](building-search-queries.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27148-p102">You can define the conditions for your search using the pre-built condition cards or using Keyword Query Language (KQL). For more information, see [Build search queries](building-search-queries.md).</span></span>

## <a name="choose-the-custodians-to-search-from"></a><span data-ttu-id="27148-110">検索する保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="27148-110">Choose the custodians to search from</span></span>

<span data-ttu-id="27148-p103">条件を定義したら、検索する場所を選択する必要があります。1つの方法として、検索するケースに既に追加した保管担当者を指定します。保管担当者を選択すると、保管担当者にマップされているすべてのデータソースに対して検索を実行します。ケースに保管担当者を追加し、データソースを管理する方法の詳細については、「 [Work with 保管担当者](managing-custodians.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27148-p103">Once you have defined your conditions, you need to choose which locations you want to search. One way to do it is by specifying which custodians you have already added to the case you want to search. By selecting a custodian, you will run the search against all data sources mapped to the custodian. See [Work with custodians](managing-custodians.md) for more information on how to add custodians to your case and manage their data sources.</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="27148-115">custodial のダイヤル場所を選択する</span><span class="sxs-lookup"><span data-stu-id="27148-115">Choose non-custodial locations</span></span>

<span data-ttu-id="27148-p104">場合によっては、保管担当者にマップされていないデータソースを検索する必要があります。この場合、検索する場所を指定するか、特定の Office 365 サービスのすべてのコンテンツの場所を検索する (すべての Exchange メールボックスまたはすべての SharePoint および OneDrive for business サイトを検索するなど) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="27148-p104">In some cases, you may wish to search data sources that are not mapped to a custodian. In this case, you can specify the locations you would like to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint and OneDrive for Business sites).</span></span>