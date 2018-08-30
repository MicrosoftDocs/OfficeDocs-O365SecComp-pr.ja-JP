---
title: 電子情報開示センターを使用したすべてのメールボックスとサイトの検索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 56e2978f-71b6-4141-b769-ad856d31bbec
description: Office 365 の電子情報開示センターの 1 つの電子的証拠開示検索を行うビジネス サイトのすべての Exchange Online のメールボックス、SharePoint Online サイト、および OneDrive を検索できます。組織内すべてのコンテンツ ソースを検索するのには、電子的証拠開示マネージャー割り当てる必要がありますコンテンツ ソースごとに電子情報開示の適切なアクセス許可です。
ms.openlocfilehash: b3508d5929ca2b5b7a937eb2dccf677a2968cbbc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531990"
---
# <a name="search-all-mailboxes-and-sites-using-the-ediscovery-center"></a>電子情報開示センターを使用したすべてのメールボックスとサイトの検索

Office 365 の電子情報開示センターの 1 つの電子的証拠開示検索を行うビジネス サイトのすべての Exchange Online のメールボックス、SharePoint Online サイト、および OneDrive を検索できます。組織内すべてのコンテンツ ソースを検索するのには、電子的証拠開示マネージャー割り当てる必要がありますコンテンツ ソースごとに電子情報開示の適切なアクセス許可です。 
  
## <a name="before-you-begin"></a>開始する前に

- 電子情報開示マネージャーには、コンテンツ ソースを検索する適切なアクセス許可が割り当てられている必要があります。メールボックスとサイトに対する電子情報開示のアクセス許可の割り当ての詳細については、以下を参照してください。 
    
  - [Exchange の電子情報開示のアクセス許可を割り当てる](https://go.microsoft.com/fwlink/p/?LinkId=526886)
    
  - [SharePoint Online の電子情報開示のアクセス許可を割り当てる](https://go.microsoft.com/fwlink/p/?LinkId=526885)
    
  - [OneDrive for Business サイトに対する電子情報開示のアクセス許可を割り当てる](assign-permissions-to-onedrive-for-business-sites.md)
    
- 1 つの電子的証拠開示検索クエリでは、最大 10,000 のメールボックスおよびビジネスのサイトの SharePoint Online と OneDrive の無制限の数を検索できます。ただし、検索する特定のサイトを指定すると、制限が 100 サイトです。
    
- すべてのメールボックスとサイトを検索するときに結果を表示するときは、制限の説明の[詳細について](search-all-mailboxes-and-sites-with-ediscovery.md#moreinfo)はセクションを参照してください。 
    
- 電子情報開示センターで検索クエリを作成する方法の詳細については、[作成および実行の電子的証拠開示のクエリ](https://go.microsoft.com/fwlink/p/?LinkID=404032)を参照してください。
    
## <a name="search-all-locations"></a>すべての場所を検索

1. 電子情報開示センターで、検索クエリを実行する電子情報開示ケースを開きます。
    
2. [**検索とエクスポート**、既存のクエリをクリックするか、新しい検索クエリを作成する **[新しい項目**] をクリックします。 
    
3. [検索クエリ] ページの **[ソース]** セクションで、**[クエリ範囲の変更]** をクリックします。
    
4. **[クエリ範囲の変更]** ページで、**[すべてを検索]** をクリックして、検索するコンテンツの場所を選択します。
    
  - すべてのメールボックスを検索するように**Exchange**を選択します。 
    
  - ビジネス サイトのすべての SharePoint Online と OneDrive を検索するように**SharePoint**を選択します。 
    
  - **交換**および**SharePoint**の両方に、組織内のすべてのコンテンツの場所の検索を選択します。 
    
![すべてのメールボックスとサイトの検索](media/e1f919ab-5596-43bb-a3c9-626cd41067b3.gif)
  
5. **[OK]** をクリックして変更を保存します。 
    
6. キーワード クエリ、日付範囲など、[検索クエリ] ページのその他の情報を記入または変更したり、検索対象のコンテンツを特定の種類のコンテンツに絞ったりします。クエリを実行する準備ができたら、**[検索]** をクリックします。 
    
## <a name="more-information"></a>詳細情報
<a name="moreinfo"> </a>

- 上位 500 メールボックス、上位 500 サイトとその他の結果が、**[クエリ]** ページの **[ソース]** の下に一覧表示されます。 
    
- すべてのコンテンツ ソースで見つかったアイテムの合計数とそれらの合計サイズが、**[クエリ]** ページの **[ソース]** の下に表示されます。 
 
    
- ExchangeメールボックスまたはSharePointのサイトにある最新の検索結果の 200 個を **[クエリ]** ページでプレビューできます。 
    
    次のスクリーン ショットは、すべてのメールボックスとサイトを検索したときの **[クエリ]** ページに表示される検索結果の例を示しています。 
    
    ![すべての場所を検索した結果のスクリーン ショット](media/4bf430f6-41ab-4bf6-afa9-33c3f6fd8b16.gif)
  

