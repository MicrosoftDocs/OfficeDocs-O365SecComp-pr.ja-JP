---
title: Office 365 の検索での office 365 テナントの分離
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
ms.collection: Strat_O365_Enterprise
description: '概要: Office 365 の検索で、テナントの分離の説明。'
ms.openlocfilehash: cc73f3c157ffd20b3891a6b7c58e7d0b2adf4e55
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531547"
---
# <a name="tenant-isolation-in-office-365-search"></a><span data-ttu-id="b5268-103">Office 365 の検索でのテナントの分離</span><span class="sxs-lookup"><span data-stu-id="b5268-103">Tenant Isolation in Office 365 Search</span></span>
<span data-ttu-id="b5268-p101">SharePoint Online の検索では、テナントとの間をリークしている情報に対する保護の共有データ構造の効率性のバランスがとれたテナント分離モデルを使用します。このモデルでは、検索機能を防ぐこと。</span><span class="sxs-lookup"><span data-stu-id="b5268-p101">SharePoint Online search uses a tenant separation model that balances the efficiency of shared data structures with protection against information leaking between tenants. With this model, we prevent the Search features from:</span></span>
- <span data-ttu-id="b5268-106">他のテナントからのドキュメントを含むクエリ結果を返す</span><span class="sxs-lookup"><span data-stu-id="b5268-106">Returning query results that contain documents from other tenants</span></span>
- <span data-ttu-id="b5268-107">スキルを持つユーザーが他のテナントについての情報を推測可能性がありますクエリの実行結果のための十分な情報を公開します。</span><span class="sxs-lookup"><span data-stu-id="b5268-107">Exposing sufficient information in query results that a skilled user could infer information about other tenants</span></span>
- <span data-ttu-id="b5268-108">他のテナントのスキーマまたは設定を表示</span><span class="sxs-lookup"><span data-stu-id="b5268-108">Showing schema or settings from another tenant</span></span>
- <span data-ttu-id="b5268-109">テナントや不適切なテナントでストアの結果の間で情報を処理する分析機能を混在させる</span><span class="sxs-lookup"><span data-stu-id="b5268-109">Mixing analytics processing information between tenants or store results in the wrong tenant</span></span>
- <span data-ttu-id="b5268-110">他のテナントから辞書のエントリを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5268-110">Using dictionary entries from another tenant</span></span>

<span data-ttu-id="b5268-p102">テナント データの種類、使用保護のレイヤーを 1 つまたは複数のコードに情報の偶発的なリークを防ぐためにします。最も重要なデータには、1 つの欠陥のことは実際や感覚的な情報漏洩のないことを確認する保護のほとんどのレイヤーがあります。</span><span class="sxs-lookup"><span data-stu-id="b5268-p102">For each type of tenant data, we use one or more layers of protection in the code to prevent accidental leaking of information. The most critical data has the most layers of protection to make sure that a single defect doesn't result in actual or perceived information leakage.</span></span>

## <a name="tenant-separation-for-the-search-index"></a><span data-ttu-id="b5268-113">検索インデックスのテナントの分離</span><span class="sxs-lookup"><span data-stu-id="b5268-113">Tenant Separation for the Search Index</span></span>
<span data-ttu-id="b5268-p103">検索インデックスがインデックスのコンポーネントをホストするサーバーのディスクに格納されているし、テナントは、インデックス ・ ファイルを共有します。テナントのインデックス付けされたドキュメントは、そのテナントのクエリに対してのみ表示されます。3 つの独立したメカニズムでは、情報の漏洩を防ぐ。</span><span class="sxs-lookup"><span data-stu-id="b5268-p103">The search index is stored on disk in the servers hosting the index components and the tenants share the index files. A tenant's indexed documents are visible only for queries for that tenant. Three independent mechanisms prevent information leakage:</span></span>
- <span data-ttu-id="b5268-117">テナント ID フィルター</span><span class="sxs-lookup"><span data-stu-id="b5268-117">Tenant ID filtering</span></span>
- <span data-ttu-id="b5268-118">テナント ID 用語の先頭に付けます</span><span class="sxs-lookup"><span data-stu-id="b5268-118">Tenant ID term prefixing</span></span>
- <span data-ttu-id="b5268-119">ACL チェック</span><span class="sxs-lookup"><span data-stu-id="b5268-119">ACL checks</span></span>

<span data-ttu-id="b5268-120">すべての 3 つのメカニズムでは、ドキュメントが正しくないテナントの検索が失敗する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5268-120">All three mechanisms would have to fail for Search to return documents to the wrong tenant.</span></span>

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a><span data-ttu-id="b5268-121">テナント ID フィルターおよびテナント ID の用語の先頭に付けます</span><span class="sxs-lookup"><span data-stu-id="b5268-121">Tenant ID Filtering and Tenant ID Term Prefixing</span></span>
<span data-ttu-id="b5268-p104">プレフィックスのテナント ID を使用して、フルテキスト インデックスでインデックスが設定されたすべての単語の検索たとえば、"*foo*"という用語は、「*123*」の ID を使用してテナントのインデックスが、フルテキスト インデックス内エントリは"*123foo です。*」</span><span class="sxs-lookup"><span data-stu-id="b5268-p104">Search prefixes every term that is indexed in the full-text index with the tenant ID. For example, when the term "*foo*" is indexed for a tenant with an ID of "*123*", the entry in the full-text index is "*123foo.*"</span></span>

<span data-ttu-id="b5268-p105">テナント ID のフィルタ リングと呼ばれるプロセスを使用してテナント ID を含めるには、すべてのクエリが変換されます。"< 使用する*guid*> に"*foo*"のクエリを変換するなど。*foo**TenantID*: <*guid*>"は、<*guid*> がテナントのクエリを実行することを表します。各インデックス ノード内で、このクエリの変換が発生して、クエリも、コンテンツの処理に影響を与えることです。すべてのクエリには、テナント ID を追加するために最適なテナントの 1 つのランクの一致を調べることによって他のテナントの用語の頻度を推論できません。</span><span class="sxs-lookup"><span data-stu-id="b5268-p105">Every query is converted to include the tenant ID using a process called tenant ID filtering. For example, the query "*foo*" is converted to "<*guid*>.*foo* AND *tenantID*:<*guid*>", where <*guid*> represents the tenant performing the query. This query conversion occurs within each index node and neither query nor content processing can influence it. Because the tenant ID is added to every query, the frequency of a term in other tenants can't be inferred by looking at best match ranking in one tenant.</span></span>

<span data-ttu-id="b5268-p106">テナント ID の用語のプレフィックスは、フル テキスト インデックスでのみ発生します。処理された検索は、"*タイトル: foo*"などには、合成検索インデックス用語をテナント ID で始まるは、代わりに、処理された検索は、フィールド名の接頭辞です。"*タイトル: foo*"のクエリを変換するなど、"*fields.title:foo と fields.tenantID*: <*guid*>.」用語の頻度は、合成検索インデックス内のヒットのランキングに影響しません、ために、用語の先頭に付けます、テナントの分離の必要性はありません。「*タイトルは以下となります*」と同様に処理された検索では、テナントのコンテンツの分離はテナント ID のクエリの変換、フィルタ リングとは異なります。</span><span class="sxs-lookup"><span data-stu-id="b5268-p106">Tenant ID term prefixing occurs only in the full-text index. Fielded searches, such as "*title:foo*", go to a synthetic search index where terms aren't prefixed by tenant ID. Instead, fielded searches are prefixed with the field name. For example, the query "*title:foo*" is converted to "*fields.title:foo AND fields.tenantID*:<*guid*>." Because the frequency of a term doesn't influence ranking of hits in the synthetic search index, there's no need for tenant separation by term prefixing. For a fielded search like "*title:foo*", tenant content separation depends on tenant ID filtering by query conversion.</span></span>

## <a name="document-access-control-list-checks"></a><span data-ttu-id="b5268-134">ドキュメントのアクセス制御リストのチェック</span><span class="sxs-lookup"><span data-stu-id="b5268-134">Document Access Control List Checks</span></span>
<span data-ttu-id="b5268-p107">検索検索インデックスに保存されている Acl を通じてドキュメントにアクセスを制御します。すべての項目には、[ACL] のフィールドに特殊な用語のセットを使用してインデックスが付けられます。ACL のフィールドには、グループ、またはドキュメントを表示できるユーザーごとの 1 つの用語が含まれています。すべてのクエリが認証されたユーザーが属するグループごとに 1 つのアクセス制御エントリ (ACE) 用語のリストが大きくなります。</span><span class="sxs-lookup"><span data-stu-id="b5268-p107">Search controls access to documents through ACLs that are saved in the search index. Every item is indexed with a set of terms in a special ACL field. The ACL field contains one term per group or user that can view the document. Every query is augmented with a list of access control entry (ACE) terms, one for each group to which the authenticated user belongs.</span></span>

<span data-ttu-id="b5268-139">"< 使用する*guid*> のようなクエリでは。*foo と tenantID*: <*guid*>"になります。"<*guid*>。*foo と tenantID*: <*guid*> *、* (*docACL:*<*ace1*> *または docACL*: <*ace2*> *または docACL*: <*ace3*> *.*)"</span><span class="sxs-lookup"><span data-stu-id="b5268-139">For example, a query like "<*guid*>.*foo AND tenantID*:<*guid*>" becomes: "<*guid*>.*foo AND tenantID*:<*guid*> *AND* (*docACL:*<*ace1*> *OR docACL*:<*ace2*> *OR docACL*:<*ace3*> *...*)"</span></span>

<span data-ttu-id="b5268-p108">ユーザー id とグループ id とので Ace が一意では、これにより、一部のユーザーに表示されているドキュメントのテナント間でのセキュリティのレベルです。特別な"すべての外部ユーザーを除く」の場合は、同じテナント内の正規のユーザーにアクセスを許可する ACE。パブリックのドキュメントでのテナントの分離によってテナント ID フィルターでは「Everyone」に対して Ace がすべてのテナントに対して同じであるため。Ace もサポートを拒否します。クエリの補強では、拒否 ACE との一致がある場合に、結果からドキュメントを削除する句を追加します。</span><span class="sxs-lookup"><span data-stu-id="b5268-p108">Because user and group identifiers and hence ACEs are unique, this provides an extra level of security between tenants for documents that are only visible to some users. The same is the case for the special "Everyone except external users" ACE that grants access to regular users in the tenant. But since ACEs for "Everyone" are the same for all tenants, tenant separation for public documents depends on tenant ID filtering. Deny ACEs are also supported. The query augmentation adds a clause that removes a document from the result when there is a match with a deny ACE.</span></span>

<span data-ttu-id="b5268-p109">Exchange のオンライン検索は、インデックスが SharePoint Online のようにテナント ID (サブスクリプション ID) ではなく個々 のユーザーのメールボックスに対するメールボックスの ID で分割されます。パーティション分割メカニズムでは、SharePoint Online と同じですが、ACL はフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="b5268-p109">In Exchange Online search, the index is partitioned on mailbox ID for individual user's mailboxes instead of tenant ID (subscription ID) as in SharePoint Online. The partitioning mechanism is the same as SharePoint Online, but there is no ACL filtering.</span></span>
