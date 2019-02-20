---
title: office 365 のテナント分離 (office 365 Search)
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '概要: Office 365 検索でのテナントの分離について説明します。'
ms.openlocfilehash: b9faae9f1d61af181807f60243890b5115c0d679
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090809"
---
# <a name="tenant-isolation-in-office-365-search"></a><span data-ttu-id="ae7f7-103">Office 365 の検索でのテナントの分離</span><span class="sxs-lookup"><span data-stu-id="ae7f7-103">Tenant Isolation in Office 365 Search</span></span>
<span data-ttu-id="ae7f7-p101">SharePoint Online の検索では、テナント間の情報リークに対する保護と、共有データ構造の効率のバランスを実現するテナント分離モデルが使用されます。このモデルを使用すると、次のような検索機能を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ae7f7-p101">SharePoint Online search uses a tenant separation model that balances the efficiency of shared data structures with protection against information leaking between tenants. With this model, we prevent the Search features from:</span></span>
- <span data-ttu-id="ae7f7-106">他のテナントからのドキュメントを含むクエリの結果を返す</span><span class="sxs-lookup"><span data-stu-id="ae7f7-106">Returning query results that contain documents from other tenants</span></span>
- <span data-ttu-id="ae7f7-107">熟練ユーザーが他のテナントに関する情報を推測できる、クエリ結果に十分な情報を公開する</span><span class="sxs-lookup"><span data-stu-id="ae7f7-107">Exposing sufficient information in query results that a skilled user could infer information about other tenants</span></span>
- <span data-ttu-id="ae7f7-108">別のテナントのスキーマまたは設定を表示する</span><span class="sxs-lookup"><span data-stu-id="ae7f7-108">Showing schema or settings from another tenant</span></span>
- <span data-ttu-id="ae7f7-109">テナント間での分析処理情報の混在、または正しくないテナントへの結果の保存</span><span class="sxs-lookup"><span data-stu-id="ae7f7-109">Mixing analytics processing information between tenants or store results in the wrong tenant</span></span>
- <span data-ttu-id="ae7f7-110">別のテナントからの辞書エントリを使用する</span><span class="sxs-lookup"><span data-stu-id="ae7f7-110">Using dictionary entries from another tenant</span></span>

<span data-ttu-id="ae7f7-p102">テナントデータの種類ごとに、情報を誤ってリークしないようにするために、1つまたは複数のコードの保護層を使用します。最も重要なデータは、1つの欠陥によって実際または情報漏洩が発生しないことを確認するために、最も多くの保護レイヤーを備えています。</span><span class="sxs-lookup"><span data-stu-id="ae7f7-p102">For each type of tenant data, we use one or more layers of protection in the code to prevent accidental leaking of information. The most critical data has the most layers of protection to make sure that a single defect doesn't result in actual or perceived information leakage.</span></span>

## <a name="tenant-separation-for-the-search-index"></a><span data-ttu-id="ae7f7-113">検索インデックスのテナントの分離</span><span class="sxs-lookup"><span data-stu-id="ae7f7-113">Tenant Separation for the Search Index</span></span>
<span data-ttu-id="ae7f7-p103">検索インデックスは、インデックスコンポーネントをホストしているサーバーのディスクに格納され、テナントはインデックスファイルを共有します。テナントのインデックス付きドキュメントは、そのテナントのクエリに対してのみ表示されます。情報漏洩を防止する3つの独立したメカニズム:</span><span class="sxs-lookup"><span data-stu-id="ae7f7-p103">The search index is stored on disk in the servers hosting the index components and the tenants share the index files. A tenant's indexed documents are visible only for queries for that tenant. Three independent mechanisms prevent information leakage:</span></span>
- <span data-ttu-id="ae7f7-117">テナント ID フィルター</span><span class="sxs-lookup"><span data-stu-id="ae7f7-117">Tenant ID filtering</span></span>
- <span data-ttu-id="ae7f7-118">テナント ID 用語のプレフィックス</span><span class="sxs-lookup"><span data-stu-id="ae7f7-118">Tenant ID term prefixing</span></span>
- <span data-ttu-id="ae7f7-119">ACL チェック</span><span class="sxs-lookup"><span data-stu-id="ae7f7-119">ACL checks</span></span>

<span data-ttu-id="ae7f7-120">検索によって正しくないテナントにドキュメントが返されるようにするには、3つのメカニズムがすべて失敗する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae7f7-120">All three mechanisms would have to fail for Search to return documents to the wrong tenant.</span></span>

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a><span data-ttu-id="ae7f7-121">テナント id フィルターとテナント id 用語のプレフィックス</span><span class="sxs-lookup"><span data-stu-id="ae7f7-121">Tenant ID Filtering and Tenant ID Term Prefixing</span></span>
<span data-ttu-id="ae7f7-p104">検索では、フルテキストインデックスでインデックスが付けられたすべての用語がテナント ID でプレフィックスされます。たとえば、ID が "*123*" のテナントに対して "*foo*" という用語がインデックス付けされている場合、フルテキストインデックス内のエントリは "123foo" になり*ます。*</span><span class="sxs-lookup"><span data-stu-id="ae7f7-p104">Search prefixes every term that is indexed in the full-text index with the tenant ID. For example, when the term "*foo*" is indexed for a tenant with an ID of "*123*", the entry in the full-text index is "*123foo.*"</span></span>

<span data-ttu-id="ae7f7-p105">すべてのクエリは、テナント id フィルターと呼ばれるプロセスを使用して、テナント id を含むように変換されます。たとえば、クエリ "*foo*" は "<*guid*>" に変換されます。*foo*および*tenantID*: <*guid*> "。ここで、<*guid*> は、クエリを実行するテナントを表します。このクエリ変換は各インデックスノード内で行われ、クエリもコンテンツ処理も影響を及ぼすことはありません。テナント ID はすべてのクエリに追加されるため、その他のテナント内の用語の頻度は、1つのテナントで最適な一致ランクを調べることでは推論できません。</span><span class="sxs-lookup"><span data-stu-id="ae7f7-p105">Every query is converted to include the tenant ID using a process called tenant ID filtering. For example, the query "*foo*" is converted to "<*guid*>.*foo* AND *tenantID*:<*guid*>", where <*guid*> represents the tenant performing the query. This query conversion occurs within each index node and neither query nor content processing can influence it. Because the tenant ID is added to every query, the frequency of a term in other tenants can't be inferred by looking at best match ranking in one tenant.</span></span>

<span data-ttu-id="ae7f7-p106">テナント ID 用語のプレフィックスは、フルテキストインデックスでのみ行われます。"*title: foo*" のような検索は、代理検索インデックスに移動します。これには、用語の先頭にテナント ID が付いていません。代わりに、フィールド名の先頭に検索語が付けられます。たとえば、クエリ "*title: foo*" は "*fields. title: foo AND fields.*<*guid*>" に変換されます。用語の頻度は、代理検索インデックス内のヒットのランク付けには影響しないため、用語のプレフィックスによるテナントの分離は必要ありません。「*title: foo*」のような検索を行う場合、テナントのコンテンツの分離は、クエリ変換によるテナント ID フィルターに依存します。</span><span class="sxs-lookup"><span data-stu-id="ae7f7-p106">Tenant ID term prefixing occurs only in the full-text index. Fielded searches, such as "*title:foo*", go to a synthetic search index where terms aren't prefixed by tenant ID. Instead, fielded searches are prefixed with the field name. For example, the query "*title:foo*" is converted to "*fields.title:foo AND fields.tenantID*:<*guid*>." Because the frequency of a term doesn't influence ranking of hits in the synthetic search index, there's no need for tenant separation by term prefixing. For a fielded search like "*title:foo*", tenant content separation depends on tenant ID filtering by query conversion.</span></span>

## <a name="document-access-control-list-checks"></a><span data-ttu-id="ae7f7-134">ドキュメントアクセス制御リストのチェック</span><span class="sxs-lookup"><span data-stu-id="ae7f7-134">Document Access Control List Checks</span></span>
<span data-ttu-id="ae7f7-p107">検索では、検索インデックスに保存されている acl 経由でドキュメントへのアクセスを制御します。各アイテムには、特殊な ACL フィールド内の一連の用語がインデックス化されています。ACL フィールドには、ドキュメントを表示できる1つまたは複数のグループまたはユーザーごとの用語が含まれています。すべてのクエリは、認証されたユーザーが属するグループごとに1つずつ、アクセス制御エントリ (ACE) 用語のリストによって補強されます。</span><span class="sxs-lookup"><span data-stu-id="ae7f7-p107">Search controls access to documents through ACLs that are saved in the search index. Every item is indexed with a set of terms in a special ACL field. The ACL field contains one term per group or user that can view the document. Every query is augmented with a list of access control entry (ACE) terms, one for each group to which the authenticated user belongs.</span></span>

<span data-ttu-id="ae7f7-139">たとえば、"<*guid*>" のようなクエリがあるとします。*foo と tenantID*: <*guid*> "は:" <*guid*> になります。*foo と tenantID*: <*guid*> *と*(*docacl:*<*ace1*> *または docacl*:*< ace2*> *または docacl*: <*ace3*> *...*)"</span><span class="sxs-lookup"><span data-stu-id="ae7f7-139">For example, a query like "<*guid*>.*foo AND tenantID*:<*guid*>" becomes: "<*guid*>.*foo AND tenantID*:<*guid*> *AND* (*docACL:*<*ace1*> *OR docACL*:<*ace2*> *OR docACL*:<*ace3*> *...*)"</span></span>

<span data-ttu-id="ae7f7-p108">ユーザー id とグループ識別子、および ace が一意であるため、一部のユーザーにのみ表示されるドキュメントのテナント間では、これによってセキュリティレベルが強化されます。これは、テナント内の通常のユーザーにアクセスを許可する "外部ユーザー以外のすべてのユーザー" ACE の場合と同じです。しかし、"Everyone" の ace はすべてのテナントで同じであるため、パブリックドキュメントのテナントの分離はテナント ID フィルターに依存します。拒否 ace もサポートされています。クエリの拡張によって、拒否 ACE と一致する場合に結果からドキュメントを削除する句が追加されます。</span><span class="sxs-lookup"><span data-stu-id="ae7f7-p108">Because user and group identifiers and hence ACEs are unique, this provides an extra level of security between tenants for documents that are only visible to some users. The same is the case for the special "Everyone except external users" ACE that grants access to regular users in the tenant. But since ACEs for "Everyone" are the same for all tenants, tenant separation for public documents depends on tenant ID filtering. Deny ACEs are also supported. The query augmentation adds a clause that removes a document from the result when there is a match with a deny ACE.</span></span>

<span data-ttu-id="ae7f7-p109">Exchange online search では、インデックスは SharePoint online と同様に、テナント id (サブスクリプション ID) ではなく、個々のユーザーのメールボックスのメールボックス ID でパーティション分割されます。パーティション分割メカニズムは SharePoint Online と同じですが、ACL フィルターはありません。</span><span class="sxs-lookup"><span data-stu-id="ae7f7-p109">In Exchange Online search, the index is partitioned on mailbox ID for individual user's mailboxes instead of tenant ID (subscription ID) as in SharePoint Online. The partitioning mechanism is the same as SharePoint Online, but there is no ACL filtering.</span></span>
