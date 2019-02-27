---
title: 情報管理ポリシー入門
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/16/2014
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
ms.collection:
- M365-security-compliance
description: 情報管理ポリシーとは、コンテンツ タイプに関する一連のルールです。 情報管理ポリシーにより、組織はコンテンツの保持期間やユーザーがそのコンテンツで実行できる操作などを制御し、管理することができます。 情報管理ポリシーは、組織が法律上または行政上の規制を遵守したり、内部のビジネス プロセスを徹底するのに役立ちます。
ms.openlocfilehash: 23662c555dfc19b2fc83b0364d93724e922c7c97
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275757"
---
# <a name="introduction-to-information-management-policies"></a><span data-ttu-id="8613d-105">情報管理ポリシー入門</span><span class="sxs-lookup"><span data-stu-id="8613d-105">Introduction to information management policies</span></span>

<span data-ttu-id="8613d-p102">情報管理ポリシーとは、コンテンツ タイプに関する一連のルールです。 情報管理ポリシーにより、組織はコンテンツの保持期間やユーザーがそのコンテンツで実行できる操作などを制御し、管理することができます。 情報管理ポリシーは、組織が法律上または行政上の規制を遵守したり、内部のビジネス プロセスを徹底するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8613d-p102">An information management policy is a set of rules for a type of content. Information management policies enable organizations to control and track things like how long content is retained or what actions users can take with that content. Information management policies can help organizations comply with legal or governmental regulations, or they can simply enforce internal business processes.</span></span> 
  
<span data-ttu-id="8613d-109">たとえば、組織は、財務諸表の "十分な管理" を示すことを求める行政上の規制に従う必要があり、1 つ以上の情報管理ポリシーを作成する場合があります。このポリシーでは、財務報告に関連したすべてのドキュメントの作成と承認プロセスにおける特定の作業を監査します。</span><span class="sxs-lookup"><span data-stu-id="8613d-109">For example, an organization that must follow government regulations requiring that they demonstrate "adequate controls" of their financial statements might create one or more information management policies that audit specific actions in the authoring and approval process for all documents related to financial filings.</span></span>
  
<span data-ttu-id="8613d-110">使用方法については、「[情報管理ポリシーを作成して適用する](create-info-mgmt-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8613d-110">For how-to information, see [Create and apply information management policies](create-info-mgmt-policies.md).</span></span>
  
## <a name="features-of-information-management-policies"></a><span data-ttu-id="8613d-111">情報管理ポリシーの機能</span><span class="sxs-lookup"><span data-stu-id="8613d-111">Features of information management policies</span></span>
<span data-ttu-id="8613d-112"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="8613d-112"></span></span>

<span data-ttu-id="8613d-113">定義済みのポリシー機能には、4 つの基本的なカテゴリがあります。これには、コンテンツやプロセスを管理するために、組織が単独または組み合わせて使用できる機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8613d-113">There are four basic categories of predefined policy features that organizations can use individually or in combination to manage content and processes.</span></span> 
  
![コンテンツ ポリシーの種類](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
<span data-ttu-id="8613d-p103">監査ポリシー機能では、ドキュメントやリスト アイテムに対して実行されたイベントと操作をログに記録して、コンテンツ管理システムがどのように使用されているかを組織で分析できます。ドキュメントまたはアイテムを編集、表示、チェックイン、チェックアウト、削除、またはその権限を変更するときなど、イベントをログに記録する監査ポリシー機能を構成することができます。すべての監査情報はサーバー上の単一の監査ログに格納され、サイト管理者がそれについてのレポートを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8613d-p103">The Auditing policy feature helps organizations analyze how their content management systems are used by logging events and operations that are performed on documents and list items. You can configure the Auditing policy feature to log events such as when a document or item is edited, viewed, checked in, checked out, deleted, or has its permissions changed. All of the audit information is stored in a single audit log on the server, and site administrators can run reports on it.</span></span> 
  
<span data-ttu-id="8613d-p104">有効期限ポリシー機能では、一貫性のある追跡可能な方法で、期限切れのコンテンツを組織がサイトから削除できます。これは、期限切れのコンテンツを保持することに起因するコストとリスクの両方を管理するのに役立ちます。有効期限ポリシーを構成して、特定の種類のコンテンツが特定の日付に有効期限が切れるように、またはドキュメントの作成または変更後、特定の時間内に有効期限が切れるように、指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8613d-p104">The Expiration policy feature helps organizations delete or remove out-of-date content from their sites in a consistent, trackable way. This helps you manage both the cost and risk associated with retaining out-of-date content. You can configure an Expiration policy to specify that certain types of content expire on a particular date or within a period of time after the document was created or last modified.</span></span>
  
<span data-ttu-id="8613d-p105">また、組織固有のニーズを満たすように、独自のポリシー機能を作成して展開することもできます。たとえば、製造業などの組織では、すべての製品設計仕様のドキュメントの下書きに対する情報管理ポリシーを定義する場合があります。このポリシーにより、ユーザーはこれらのドキュメントのコピーをセキュリティで保護されないプリンターで印刷することが禁止されます。この種類の情報管理ポリシーを定義するために、印刷制限ポリシー機能を作成して展開できます。このポリシーは、関連する製品設計仕様コンテンツ タイプ用の情報管理ポリシーに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8613d-p105">Organizations can also create and deploy custom policy features to meet specific needs. For example, a manufacturing organization might want to define an information management policy for all draft product-design specification documents that prohibits users from printing copies of these documents on nonsecure printers. To define this kind of information management policy, you can create and deploy a Printing Restriction policy feature that can be added to the relevant information management policy for the product design specification content type.</span></span>
  
## <a name="locations-to-use-an-information-management-policy"></a><span data-ttu-id="8613d-124">情報管理ポリシーを使用する場所</span><span class="sxs-lookup"><span data-stu-id="8613d-124">Locations to use an information management policy</span></span>
<span data-ttu-id="8613d-125"><a name="__toc340213528"> </a></span><span class="sxs-lookup"><span data-stu-id="8613d-125"></span></span>

<span data-ttu-id="8613d-p106">情報管理ポリシーを実装するには、サイト上のリスト、ライブラリ、またはコンテンツ タイプに追加する必要があります。情報管理ポリシーを作成または追加する場所は、ポリシーが適用される範囲または使用できる範囲に影響を及ぼします。以下を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8613d-p106">To implement an information management policy, you must add it to a list, library, or content type in a site. The location where you create or add an information management policy affects how broadly the policy applies or how broadly it can be used. You can:</span></span>
  
 <span data-ttu-id="8613d-p107">**サイト コレクション ポリシーを作成し、このポリシーをコンテンツ タイプ、リスト、またはライブラリに追加する**: サイト コレクションのトップ レベル サイトのポリシー リストに、サイト コレクション ポリシーを作成することができます。サイト コレクション ポリシーを作成した後、エクスポートできるので、他のサイト コレクションのサイト管理者が自身のポリシー リストにインポートできます。エクスポート可能なサイト コレクション ポリシーを作成すると、組織内のすべてのサイトで情報管理ポリシーを統一できます。</span><span class="sxs-lookup"><span data-stu-id="8613d-p107">**Create a site collection policy and then add this policy to a content type, list, or library** You can create a site collection policy in the Policies list in the top-level site of a site collection. After you create a site collection policy, you can export it so that administrators of other site collections can import it into their Policies list. Creating an exportable site collection policy enables you to standardize the information management policies across the sites in your organization.</span></span> 
  
<span data-ttu-id="8613d-p108">サイト コレクション ポリシーをサイト コンテンツ タイプに追加し、サイト コンテンツ タイプのインスタンスをリストまたはライブラリに追加する場合、そのリストまたはライブラリの所有者は、リストまたはライブラリのサイト コレクション ポリシーを変更することができません。 サイト コレクション ポリシーをサイト コンテンツ タイプに追加することは、サイト コレクション ポリシーをサイト階層の各レベルに適用するには良い方法です。</span><span class="sxs-lookup"><span data-stu-id="8613d-p108">When you add a site collection policy to a site content type, and an instance of that site content type is added to a list or library, the owner of that list or library cannot modify the site collection policy for the list or library. Adding a site collection policy to a site content type is a good way to ensure that site collection policies are enforced at each level of your site hierarchy.</span></span>
  
![[サイトの設定] ページの [コンテンツ タイプ ポリシーのテンプレート] リンク](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 <span data-ttu-id="8613d-p109">**トップ レベル サイトのサイト コンテンツ タイプ ギャラリーで、サイト コンテンツ タイプに対する情報管理ポリシーを作成し、1 つ以上のリストまたはライブラリにそのコンテンツ タイプを追加する**: サイト コンテンツ タイプの情報管理ポリシーを直接作成してから、そのサイト コンテンツ タイプのインスタンスを複数のリストまたはライブラリと関連付けることもできます。この方法で情報管理ポリシーを作成した場合は、そのコンテンツ タイプのサイト コレクション内のすべてのアイテムに、またはそのコンテンツ タイプから継承するコンテンツ タイプにポリシーがあります。ただし、直接サイト コンテンツ タイプの情報管理ポリシーを作成した場合、このようにして作成したポリシーはエクスポートできないため、他のサイト コレクションでこの情報管理ポリシーを再利用するのが困難です。</span><span class="sxs-lookup"><span data-stu-id="8613d-p109">**Create an information management policy for a site content type in the top-level site's Site Content Type Gallery, and then add that content type to one or more lists or libraries** You can also create an information management policy directly for a site content type and then associate an instance of that site content type with multiple lists or libraries. If you create an information management policy this way, every item in the site collection of that content type or a content type that inherits from that content type has the policy. However, if you create an information management policy directly for a site content type, it is more difficult to reuse this information management policy in other site collections, because policies that are created this way cannot be exported.</span></span> 
  
![[サイトの設定] ページの [サイト コンテンツ タイプ] リンク](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![サイト コンテンツ タイプの設定ページにある情報管理ポリシー リンク](media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
<span data-ttu-id="8613d-p110">注: サイト コレクションで使用されるポリシーを制御するため、サイト コレクションの管理者は、ポリシー機能をコンテンツ タイプに直接設定する機能を無効にすることができます。 この制限が有効であるとき、コンテンツ タイプを作成するユーザーは、サイト コレクション ポリシー リストからポリシーを選択することしかできません。</span><span class="sxs-lookup"><span data-stu-id="8613d-p110">Note To control which policies are used in a site collection, site collection administrators can disable the ability to set policy features directly on a content type. When this restriction is in effect, users who create content types are limited to selecting policies from the site collection Policies list.</span></span>
  
 <span data-ttu-id="8613d-p111">**リストまたはライブラリの情報管理ポリシーを作成する**: 組織で、非常に限られたコンテンツ セットに特定の情報管理ポリシーを適用する必要がある場合、個々のリストまたはライブラリにのみ適用される情報管理ポリシーを作成することができます。この情報管理ポリシーの作成方法は、最も柔軟性に欠ける方法です。ポリシーが 1 か所にのみ適用され、ポリシーをエクスポートできず、他の場所に再利用できないからです。ただし、場合によっては、特定の状況を処理するために、適用性が制限された固有の情報管理ポリシーを作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8613d-p111">**Create an information management policy for a list or library** If your organization needs to apply a specific information management policy to a very limited set of content, you can create an information management policy that applies only to an individual list or library. This method of creating an information management policy is the least flexible, because the policy applies only to one location, and it cannot be exported or reused for other locations. However, sometimes you may need to create unique information management policies with limited applicability to address specific situations.</span></span> 
  
![ドキュメント ライブラリの設定ページ上の情報管理ポリシーのリンク](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
<span data-ttu-id="8613d-146">注</span><span class="sxs-lookup"><span data-stu-id="8613d-146">Notes</span></span> 
  
<span data-ttu-id="8613d-p112">リストまたはライブラリが複数のコンテンツ タイプをサポートしていない場合のみ、リストまたはライブラリに対する情報管理ポリシーを作成することができます。 リストまたはライブラリが複数のコンテンツ タイプをサポートしている場合は、そのリストまたはライブラリに関連付けられている個別のリスト コンテンツ タイプに情報管理ポリシーを定義する必要があります (特定のリストまたはライブラリに関連付けられているサイト コンテンツ タイプのインスタンスは、リスト コンテンツ タイプと呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="8613d-p112">You can create an information management policy for a list or library only if that list or library does not support multiple content types. If a list or library supports multiple content types, you need to define an information management policy for each individual list content type that is associated with that list or library. (Instances of a site content type that are associated with a specific list or library are known as list content types.)</span></span>
  
<span data-ttu-id="8613d-p113">サイト コレクションで使用されるポリシーを制御するため、サイト コレクションの管理者は、ポリシー機能をリストまたはライブラリに直接設定する機能を無効にすることができます。 この制限が有効であるとき、リストまたはライブラリを管理するユーザーは、サイト コレクション ポリシー リストからポリシーを選択することしかできません。</span><span class="sxs-lookup"><span data-stu-id="8613d-p113">To control which policies are used in a site collection, site collection administrators can disable the ability to set policy features directly on a list or library. When this restriction is in effect, users who manage lists or libraries are limited to selecting policies from the site collection Policies list.</span></span>
  
[<span data-ttu-id="8613d-152">情報管理ポリシーとは、コンテンツ タイプに関する一連のルールです。 情報管理ポリシーにより、組織はコンテンツの保持期間やユーザーがそのコンテンツで実行できる操作などを制御し、管理することができます。 情報管理ポリシーは、組織が法律上または行政上の規制を遵守したり、内部のビジネス プロセスを徹底するのに役立ちます。 たとえば、組織は、財務諸表の "十分な管理" を示すことを求める行政上の規制に従う必要があり、1 つ以上の情報管理ポリシーを作成する場合があります。このポリシーでは、財務報告に関連したすべてのドキュメントの作成と承認プロセスにおける特定の作業を監査します。使用方法については、「情報管理ポリシーを作成して適用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8613d-152">An information management policy is a set of rules for a type of content. Information management policies enable organizations to control and track things like how long content is retained or what actions users can take with that content. Information management policies can help organizations comply with legal or governmental regulations, or they can simply enforce internal business processes. For example, an organization that must follow government regulations requiring that they demonstrate "adequate controls" of their financial statements might create one or more information management policies that audit specific actions in the authoring and approval process for all documents related to financial filings.For how-to information, see Create and apply information management policies.</span></span>](intro-to-info-mgmt-policies.md#__top)
  

