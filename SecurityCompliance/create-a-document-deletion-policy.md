---
title: ドキュメント削除ポリシーを作成する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 41b2ed73-eb8d-4429-945e-a8197894585a
description: 組織は多くの場合、コンプライアンス、法律、その他の規制により、ドキュメントを一定期間保持する必要があります。しかし、必要以上にドキュメントを長く保持すると、組織が法的なリスクにさらされる場合があります。
ms.openlocfilehash: 7fb0c546fb65bf2cc2e67fe7e047593892cea58d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259766"
---
# <a name="create-a-document-deletion-policy"></a><span data-ttu-id="e3c4b-104">ドキュメント削除ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="e3c4b-104">Create a document deletion policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3c4b-105">今後は、ドキュメント削除ポリシーの代わりに、microsoft 365 コンプライアンスセンター、microsoft 365 セキュリティセンター、または Office 365 セキュリティ&amp;コンプライアンスセンターで作成されたアイテム保持ポリシーまたはアイテム保持ラベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-105">Moving forward, we recommend that you use a retention policy or retention labels created in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security &amp; Compliance Center instead of a document deletion policy.</span></span> <span data-ttu-id="e3c4b-106">ドキュメント削除ポリシーは、保持ポリシーを使用して引き続き並行して機能しますが、Office 365 でコンテンツを保持または削除する必要がある場合は、アイテム保持ポリシーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-106">Document deletion policies will continue to work side by side with retention policies, but if you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy.</span></span> <span data-ttu-id="e3c4b-107">詳細については、「[これらの機能の代わりにアイテム保持ポリシーを使用](retention-policies.md#use-a-retention-policy-instead-of-these-features)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-107">For more information, see [Use a retention policy instead of these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span></span> 
  
<span data-ttu-id="e3c4b-p103">組織は多くの場合、コンプライアンス、法律、その他の規制により、ドキュメントを一定期間保持する必要があります。しかし、必要以上にドキュメントを長く保持すると、組織が法的なリスクにさらされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p103">Organizations are often required to retain documents for a certain period of time due to compliance, legal, or other regulations. However, retaining documents for longer than required can expose the organization to legal risk.</span></span>
  
<span data-ttu-id="e3c4b-110">ドキュメント削除ポリシーを使用すると、特定の期間が経過した後にサイト内のドキュメントを削除することによって、積極的にリスクを軽減できます。たとえば、ドキュメントが作成された後に、ユーザーの OneDrive for business サイトのドキュメントを5年後に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-110">With a document deletion policy, you can proactively reduce risk by deleting documents in a site after a specific period of time—for example, you can delete documents in users' OneDrive for Business sites five years after the documents were created.</span></span> 
  
<span data-ttu-id="e3c4b-p104">ドキュメント削除ポリシーを作成した後、それをサイト コレクション テンプレートに割り当てると、そのテンプレートから作成されたすべてのサイト コレクションでポリシーを利用できます。さらに、特定のサイト コレクションにポリシーを割り当て、そのサイト コレクションのテンプレートに割り当てられているポリシーを上書きすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p104">After you create a document deletion policy, you can assign it to a site collection template, so that the policy is available to all site collections created from that template. You can also assign a policy to a specific a site collection, which overrides any policies that may have been assigned to the template for that site collection.</span></span>
  
![ドキュメント削除ポリシー センターのホーム ページ](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="policy-templates"></a><span data-ttu-id="e3c4b-114">ポリシー テンプレート</span><span class="sxs-lookup"><span data-stu-id="e3c4b-114">Policy templates</span></span>

<span data-ttu-id="e3c4b-p105">ドキュメント削除ポリシーは、最初から作成することも、サンプル ポリシーのいずれかを使用して作成することもできます。コンプライアンス ポリシー センターには、そのまま使用できるサンプル ポリシー、または名前や内容の変更ができる基礎となるサンプル ポリシーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p105">You can create a document deletion policy from scratch, or you can use one of the sample policies. The Compliance Policy Center includes sample policies that you can use as is, or you can use them as a starting point and then rename or modify them.</span></span>
  
![サンプル ドキュメント削除ポリシー](media/IP-Sample-deletion-policies.png)
  
## <a name="examples-of-how-to-use-document-deletion-policies"></a><span data-ttu-id="e3c4b-118">ドキュメント削除ポリシーの使い方の例</span><span class="sxs-lookup"><span data-stu-id="e3c4b-118">Examples of how to use document deletion policies</span></span>

<span data-ttu-id="e3c4b-119">サイト コレクションまたはサイト コレクション テンプレートに 1 つ以上のポリシーを割り当てることができ、各ポリシーに 1 つ以上のルールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-119">A site collection or a site collection template can have one more policies assigned to it, and each of those policies can have one or more rules.</span></span> <span data-ttu-id="e3c4b-120">ただし、サイトごとにアクティブなポリシーは1つだけであり、サイト内のライブラリに対していつでもアクティブな削除ルールは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-120">However, there can be only one policy that's active per site, and there can be only one deletion rule that's active at any time for the libraries within the site.</span></span>
  
![ポリシー間の関係を示す図](media/IP-Two-policies-four-rules.png)
  
<span data-ttu-id="e3c4b-122">さらに、必須または既定のポリシーを選択でき、削除ルールを既定のルールとして選択できます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-122">In addition, you can select a policy as mandatory or default, and you can select a deletion rule as a default rule:</span></span> 
  
- <span data-ttu-id="e3c4b-123">**必須のポリシー**ポリシーが必須としてマークされている場合、サイトコレクションまたはテンプレートに割り当てることができるポリシーは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-123">**Mandatory policy**When a policy is marked as mandatory, only one policy can be assigned to the site collection or template.</span></span> <span data-ttu-id="e3c4b-124">ポリシーは、既定としてマークされ、すべてのサイトに適用される必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-124">The policy must be marked as default and will be applied to all sites.</span></span> <span data-ttu-id="e3c4b-125">サイトの所有者はポリシーから脱退できません。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-125">Site owners cannot opt out of the policy.</span></span>
    
- <span data-ttu-id="e3c4b-126">**既定のポリシー**ポリシーが既定として設定されている場合、そのポリシーは、そのポリシーが割り当てられているすべてのサイトで自動的にアクティブ化され、サイト所有者が必要とするアクションはありません。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-126">**Default policy**When a policy is set as default, the policy is automatically active in all sites that it's assigned to with no action required by site owner.</span></span>
    
- <span data-ttu-id="e3c4b-127">**既定のルール**削除ルールが既定として設定されている場合、そのルールは、そのポリシーを使用するサイト内のすべてのライブラリに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-127">**Default rule**When a deletion rule is set as default, it is automatically applied to all libraries in the sites that use the policy.</span></span>
    
<span data-ttu-id="e3c4b-128">次の例では、必須のポリシー、既定のポリシー、既定のルールの使い方を説明します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-128">The following examples explain when you might want to use a mandatory policy or default policies and rules.</span></span>
  
### <a name="example-1-apply-a-single-policy-with-a-single-rule-to-a-site-collection-template"></a><span data-ttu-id="e3c4b-129">例 1: 単一のルールを持つ単一のポリシーをサイト コレクション テンプレートに適用する</span><span class="sxs-lookup"><span data-stu-id="e3c4b-129">Example 1: Apply a single policy with a single rule to a site collection template</span></span>

<span data-ttu-id="e3c4b-p108">ドキュメント削除ポリシーを、すべての OneDrive for Business サイトまたはすべてのチーム サイトなど、広範囲にわたる構造化されていないコンテンツに適用する場合があります。特定のサイト コレクション テンプレートから作成されたすべてのサイトで、単一のドキュメント削除ポリシーをアクティブにするには、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p108">You may want to enforce a document deletion policy across a broad range of unstructured content, such as all OneDrive for Business sites or all team sites. If you want to ensure that a single document deletion policy is active in all sites created from a site collection template, you can:</span></span>
  
1. <span data-ttu-id="e3c4b-132">単一の既定の削除ルールを持つ単一のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-132">Create a single policy with a single default deletion rule.</span></span>
    
2. <span data-ttu-id="e3c4b-133">ポリシーを必須および既定として設定します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-133">Set the policy as mandatory and default.</span></span>
    
3. <span data-ttu-id="e3c4b-134">ポリシーをサイト コレクション テンプレートに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-134">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="e3c4b-p109">この例では、特定のテンプレートから作成されたすべてのサイト コレクション内のすべてのライブラリに既定の削除ルールが適用され、サイトの所有者はポリシーを拒否できません。これは、ドキュメント削除ポリシーを広範囲にわたって厳格に適用するための最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p109">In this example, the default deletion rule will be applied to all libraries in all site collections created from the template, and site owners cannot opt out of the policy. This is the simplest way to broadly and rigidly enforce a document deletion policy.</span></span>
  
![単一の必須ポリシーを示す図](media/IP-Example-1-doc-deletion-policies.png)
  
### <a name="example-2-apply-a-single-policy-with-several-rules-to-a-site-collection-template"></a><span data-ttu-id="e3c4b-138">例 2: 複数のルールを持つ単一のポリシーをサイトコレクションテンプレートに適用する</span><span class="sxs-lookup"><span data-stu-id="e3c4b-138">Example 2: Apply a single policy with several rules to a site collection template</span></span>

<span data-ttu-id="e3c4b-p110">通常、サイトに含まれるコンテンツの種類を最もよく知っているのはサイト所有者です。したがって、サイトの所有者は、各サイトに最適な削除ルールを選択できます。また、サイトの所有者は、ポリシーを完全に拒否することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p110">Site owners often know best what type of content their site contains, so you may choose to allow site owners to select the deletion rule that best applies to their site. You may also want to allow site owners to opt out of a policy entirely.</span></span>
  
<span data-ttu-id="e3c4b-p111">これと並行して、ポリシーを一元的に作成して管理することもできます。さらに、1 つのポリシーとルールを既定として選択して、サイトの所有者が別のポリシーを選択するか拒否した場合以外は、特定のポリシーを常に有効にすることもできます。サイトの所有者にこのような柔軟性を提供する場合は、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p111">At the same time, you can still centrally create and manage the policies. You can also select one policy and rule as the default, so that a policy is always in effect until the site owner chooses a different one or opts out. If you want to provide such flexibility to site owners, you can:</span></span>
  
1. <span data-ttu-id="e3c4b-143">複数の削除ルールを持つ単一のポリシーを作成し、既定のルールを 1 つ設定します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-143">Create a single policy with several deletion rules, and set one rule as the default.</span></span>
    
2. <span data-ttu-id="e3c4b-144">ポリシーを既定のポリシーとして設定します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-144">Set the policy as the default policy.</span></span>
    
3. <span data-ttu-id="e3c4b-145">ポリシーをサイト コレクション テンプレートに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-145">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="e3c4b-146">サイトの所有者は、代替削除ルールを 1 つ選択する、ポリシーを拒否する、あるいはそのまま既定のポリシーとルールに従うこともできます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-146">Site owners can select one of the alternate deletion rules, opt out of the policy, or do nothing and be subject to the default policy and rule.</span></span>
  
![多数のルールを含む 1 つのポリシーを示す図](media/IP-Example-2-doc-deletion-policies.png)
  
### <a name="example-3-apply-several-policies-with-one-or-more-rules-to-a-site-collection"></a><span data-ttu-id="e3c4b-148">例 3: 1 つ以上のルールを持つ複数のポリシーをサイト コレクションに適用する</span><span class="sxs-lookup"><span data-stu-id="e3c4b-148">Example 3: Apply several policies with one or more rules to a site collection</span></span>

<span data-ttu-id="e3c4b-p112">この例では、サイトの所有者は複数のポリシーから選択でき、多くの場合はポリシーを選択した後に複数のルールから選択できるため、サイト所有者に最大限の柔軟性が与えられます。1 つのポリシーとルールを既定として設定すると、サイトの所有者が別のポリシーを選択するか拒否する場合以外は、特定のポリシーが常に有効になります。ただし、既定のポリシーとルールを設定しない場合は、サイトの所有者がポリシーやルールを選択して適用しない限り、サイト内のドキュメント ライブラリにはアクティブなポリシーとルールが存在しません。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p112">This example provides the maximum flexibility to site owners because they can choose from several policies, and after selecting a policy they can often choose from several rules. One policy and rule are set as default, so that a policy is always in effect until the site owner chooses a different one or opts out. Note that if you do not set a policy and rule as the default, then no policies or rules will be active for the document libraries in the site until the site owner takes action to select and apply them.</span></span>
  
<span data-ttu-id="e3c4b-p113">前の 2 つの例とは異なり、これらのポリシーの割り当て先は、サイト コレクション テンプレートではなく、特定のサイト コレクションです。つまり、特定のサイト コレクションのコンテンツに合わせてカスタマイズが可能なポリシーです。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p113">Unlike the previous two examples, these policies are assigned to a specific site collection — not the site collection template. This means the policies can be more specifically tailored for the content in a specific site collection.</span></span>
  
<span data-ttu-id="e3c4b-p114">ポリシーとルールは継承されます。サイトの所有者がサイト用のポリシーとルールを選択すると、すべてのサブサイトが親からポリシーを継承します。ただし、サブサイトの所有者が別のポリシーとルールを選択した場合は継承が断たれ、すべてのサブサイトでは、継承が再び断たれるまで、新たに選択されたポリシーとルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p114">Policies and rules are inherited. Site owners can select a policy and rule for their site, and all subsites inherit the policy from the parent. However, an owner of a subsite can break inheritance by selecting a different policy and rule, which in turn applies to all subsites until inheritance is broken again.</span></span>
  
<span data-ttu-id="e3c4b-156">このシナリオを設定するには、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-156">To set up this scenario, you can:</span></span>
  
1. <span data-ttu-id="e3c4b-157">複数のポリシーを作成し、各ポリシーに 1 つ以上のルールを含めます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-157">Create several policies that each contains one or more rules.</span></span>
    
2. <span data-ttu-id="e3c4b-158">既定のポリシーとルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-158">Set a policy and rule as the default.</span></span>
    
3. <span data-ttu-id="e3c4b-159">ポリシーを特定のサイト コレクションに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-159">Assign the policies to a specific site collection.</span></span>
    
<span data-ttu-id="e3c4b-160">さらに、特定のサイト コレクションに合わせてポリシーとルールをカスタマイズし、サイトの所有者は各サイトに最も適したポリシーとルールを選択して、継承を断つことができます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-160">In addition, the policies and rules are tailored to a specific site collection, where site owners can break inheritance by selecting the policy and rule that best applies to their site.</span></span>
  
![多数のポリシーとルールを示す図](media/IP-Example-3-doc-deletion-policies.png)
  
## <a name="create-a-document-deletion-policy"></a><span data-ttu-id="e3c4b-162">ドキュメント削除ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="e3c4b-162">Create a document deletion policy</span></span>

1. <span data-ttu-id="e3c4b-163">Office 365security &amp;コンプライアンスセンターで、[**データ管理** \>の**保持**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-163">In the Office 365Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="e3c4b-164">[**削除**] の [ **SharePoint Online および OneDrive for business のドキュメント削除ポリシーの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-164">Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="e3c4b-165">ドキュメント削除ポリシー センターが新しいブラウザー タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-165">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
    <span data-ttu-id="e3c4b-166">セキュリティ&amp;コンプライアンスセンターからドキュメント削除ポリシーセンターへの最初の移動では、ポリシーセンターが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-166">The first time you navigate from the Security &amp; Compliance Center to the Document Deletion Policy Center, the policy center is automatically created for you.</span></span> <span data-ttu-id="e3c4b-167">または、[サイトコレクションを作成](http://go.microsoft.com/fwlink/p/?LinkID=404342)し、[**エンタープライズ**] タブの [**コンプライアンスポリシーセンター** ] を選択して、ポリシーセンターを手動で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-167">Alternatively, you can manually create the policy center by [creating the site collection](http://go.microsoft.com/fwlink/p/?LinkID=404342) and choosing **Compliance Policy Center** on the **Enterprise** tab.</span></span> 
    
2. <span data-ttu-id="e3c4b-168">[**削除ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-168">Choose **Deletion Policies**.</span></span>
    
    ![削除ポリシー オプション](media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="e3c4b-170">**[新しいアイテム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-170">Choose **new item**.</span></span>
    
4. <span data-ttu-id="e3c4b-p117">ポリシーの名前と説明を入力します。サイトの所有者はこの名前と説明を基にサイトのポリシーを選択する可能性があるので、サイトの所有者が適切なポリシーを選択できるように十分な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p117">Enter a policy name and description. Site owners may be selecting a policy for their site based on this name and description, so include enough information for them to choose the correct policy.</span></span>
    
5. <span data-ttu-id="e3c4b-173">ルールを作成するには、**[新規]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-173">To create a rule, choose **New**.</span></span>
    
6. <span data-ttu-id="e3c4b-174">名前を入力し、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-174">Enter a name and choose the following options:</span></span>
    
  - <span data-ttu-id="e3c4b-175">ルールによってドキュメントを完全に削除するのか、ごみ箱にそれらを移動するのかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-175">Choose whether the rule will permanently delete documents or delete them to the Recycle Bin.</span></span> <span data-ttu-id="e3c4b-176">ごみ箱は、アイテムをサイトから完全に削除する前の、第 2 段階のセーフティ ネットを提供します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-176">The Recycle Bin provides a second-stage safety net before an item is permanently deleted from a site.</span></span> <span data-ttu-id="e3c4b-177">ゴミ箱の詳細については、「[ごみ箱を空にする」または「ファイルを復元](http://go.microsoft.com/fwlink/p/?LinkID=404348)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-177">For more information about the Recycle Bin, see [Empty the Recycle Bin or restore your files](http://go.microsoft.com/fwlink/p/?LinkID=404348).</span></span>
    
  - <span data-ttu-id="e3c4b-178">削除の基準となる日付を、ドキュメントの作成日にするか、最終更新日にするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-178">Choose whether the deletion date is calculated from the date when a document was created or last modified.</span></span>
    
  - <span data-ttu-id="e3c4b-179">ドキュメントが削除されるまでの期間として、日数、月数、年数を入力します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-179">Enter a number of days, months, or years as the time period after which a document will be deleted.</span></span>
    
  - <span data-ttu-id="e3c4b-p119">ルールが既定のルールであるかどうかを選択します。最初に作成したルールは、自動的に既定のルールとして設定されます。既定のルールは、ポリシーを使用するサイト内のすべてのライブラリに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p119">Choose whether the rule is a default rule. The first rule that you create is automatically set as the default rule. A default rule is automatically applied to all libraries in the sites that use the policy.</span></span>
    
![新しい削除ルール ページ](media/IP-New-deletion-rule.png)
  
7. <span data-ttu-id="e3c4b-184">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-184">Click **Save**.</span></span>
    
8. <span data-ttu-id="e3c4b-p120">サイトの所有者が各サイトに適用する別のルールを選択できるようにしたい場合は、追加のルールを作成します。サイト所有者が措置を取らなければ、既定のルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p120">Create additional rules if you want site owners to be able to choose different rules to apply to their site. The default rule, if any, will be applied if the site owner takes no action.</span></span>
    
9. <span data-ttu-id="e3c4b-187">ポリシーからルールを削除するには、ルールを選択し、[**削除**] をクリックして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-187">To remove a rule from a policy, select the rule, click **Delete**, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e3c4b-188">ルールを削除したときに、そのポリシーに既定のルールが含まれていない場合は、そのポリシーに対して適用されるルールはありません。つまり、ドキュメントが削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-188">If you delete a rule, and the policy does not contain a default rule, then no rule will be in effect for that policy—in other words, no documents will be deleted.</span></span> 
  
![ポリシーからのルール削除の確認メッセージ](media/IP-Remove-rule-from-policy-message.png)
  
## <a name="assign-the-document-deletion-policy-to-a-site-collection-template"></a><span data-ttu-id="e3c4b-190">ドキュメント削除ポリシーをサイト コレクション テンプレートに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e3c4b-190">Assign the document deletion policy to a site collection template</span></span>

<span data-ttu-id="e3c4b-191">ポリシーをサイト コレクション テンプレートに割り当てると、既存のサイト コレクションと今後作成されるサイト コレクションを含め、そのテンプレートから作成されるすべてのサイト コレクションでポリシーを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-191">By assigning a policy to a site collection template, you make the policy available to all site collections created from that template, including both existing site collections and site collections created in the future.</span></span>
  
<span data-ttu-id="e3c4b-192">ドキュメント削除ポリシーに指定された期間は、ポリシーが割り当てられた後の時間ではなく、ドキュメントが作成または変更されてからの経過時間を意味することを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-192">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned.</span></span> <span data-ttu-id="e3c4b-193">ポリシーを初めて割り当てると、サイト内のすべてのドキュメントが評価され、条件を満たしている場合、ドキュメントは削除されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-193">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted.</span></span> <span data-ttu-id="e3c4b-194">これは、ポリシーの割り当て以降に新しく作成されたドキュメントだけでなく、すべての既存のドキュメントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-194">This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="e3c4b-195">セキュリティ&amp; /コンプライアンスセンターで、[**データ管理** \>の**保持**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-195">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="e3c4b-196">[**削除**] の [ **SharePoint Online および OneDrive for business のドキュメント削除ポリシーの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-196">Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="e3c4b-197">ドキュメント削除ポリシー センターが新しいブラウザー タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-197">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="e3c4b-198">**[テンプレートのポリシーの割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-198">Choose **Policy Assignments for Templates**.</span></span>
    
    ![[テンプレートのポリシーの割り当て] オプション](media/IP-Policy-Assignments-for-Templates-option.png)
  
3. <span data-ttu-id="e3c4b-200">**[新しいアイテム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-200">Choose **new item**.</span></span>
    
4. <span data-ttu-id="e3c4b-201">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-201">Do one of the following:</span></span>
    
  - <span data-ttu-id="e3c4b-202">ポリシーをチーム サイト テンプレートなどのサイト コレクション テンプレートに割り当てるには、**[サイト コレクション テンプレートに割り当てる]** を選択し、サイト コレクション テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-202">To assign the policy to a site collection template such as the Team Site template, select **Assign to site collection template**, and then select the site collection template.</span></span>
    
  - <span data-ttu-id="e3c4b-203">ポリシーをユーザーの1台のドライブに割り当てるには、下の強調表示されている [ **OneDrive for business テンプレートに割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-203">To assign the policy to users' One Drive for Business, choose **Assign to OneDrive for Business Template**, highlighted below.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e3c4b-204">サイト コレクション テンプレートにポリシーを割り当てると、そのポリシーは、そのテンプレートから作成された既存のサイト コレクションと今後作成されるサイト コレクションの両方で利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-204">When you assign a policy to a site collection template, that policy will be available both to existing site collections created from that template and to site collections created in the future.</span></span> 
  
![OneDrive オプションを表示するテンプレート ページの選択](media/IP-Choose-a-template.png)
  
5. <span data-ttu-id="e3c4b-206">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-206">Click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e3c4b-207">各テンプレートには、1つのポリシーセットのみを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-207">Each template can have only one set of policies assigned to it.</span></span> <span data-ttu-id="e3c4b-208">このテンプレートに既にポリシーが割り当てられていることを示すエラーが表示された場合は、左側の\>ナビゲーションで [**サイトコレクションへの割り当て**の**取り消し** \> ] を選択します。サイトコレクションを選択して、既にポリシーのセットを表示および管理するら.</span><span class="sxs-lookup"><span data-stu-id="e3c4b-208">If you see an error saying that this template already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** in the left navigation \> select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
6. <span data-ttu-id="e3c4b-209">**[割り当て済みのポリシーの管理]** を選択し、割り当てたいポリシーを選択し、いずれかのポリシーを既定のポリシーにするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-209">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy.</span></span> <span data-ttu-id="e3c4b-210">既定のポリシーを設定すると、そのポリシーに割り当てられているすべてのサイトでポリシーが自動的に (サイト所有者の操作なしに) アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-210">When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![ポリシー ページの追加および管理](media/IP-Add-and-manage-policies-page.png)
  
7. <span data-ttu-id="e3c4b-212">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-212">Click **Save**.</span></span>
    
8. <span data-ttu-id="e3c4b-p125">サイト所有者が拒否できないようにポリシーをすべてのサイトに適用するには、**[必須のポリシーに指定する]** を選択します。ポリシーを必須にすると、サイト コレクション テンプレートにはその 1 つのポリシーのみを割り当てることができます。そのポリシーは、既定のポリシーとしても指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p125">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection template. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="e3c4b-216">このオプションが灰色表示になっている場合は、**[割り当て済みのポリシーの管理]** を選択し、少なくとも 1 つのポリシーが割り当て済みであり、既定として設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-216">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
9. <span data-ttu-id="e3c4b-217">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-217">Click **Save**.</span></span>
    
## <a name="assign-the-document-deletion-policy-to-a-site-collection"></a><span data-ttu-id="e3c4b-218">ドキュメント削除ポリシーをサイト コレクションに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e3c4b-218">Assign the document deletion policy to a site collection</span></span>

<span data-ttu-id="e3c4b-p126">ポリシーを特定のサイト コレクションに割り当てると、ポリシーはその特定のサイト コレクションでのみ使用可能になります。つまり、サイト コレクション内のコンテンツに合わせてポリシーをさらにカスタマイズできます。また、特定のサイト コレクションに割り当てられたポリシーは、そのサイト コレクションのテンプレートに割り当てられたポリシーを上書きします。たとえば、営業部のサイト コレクション (チーム サイト テンプレートから作成) に割り当てられたポリシーは、チーム サイト テンプレートに割り当てられたポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p126">By assigning a policy to a specific site collection, you make the policy available only to that specific site collection. This means you can tailor policies more closely to the content in the site collection. Also, policies assigned to a specific site collection will override any policies that are assigned to the template for that site collection. For example, a policy assigned to the Sales Department site collection (created from the Team Site template) will override any policies assigned to the Team Site template.</span></span>
  
<span data-ttu-id="e3c4b-223">ドキュメント削除ポリシーに指定された期間は、ポリシーが割り当てられた後の時間ではなく、ドキュメントが作成または変更されてからの経過時間を意味することを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-223">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned.</span></span> <span data-ttu-id="e3c4b-224">ポリシーを初めて割り当てると、サイト内のすべてのドキュメントが評価され、条件を満たしている場合、ドキュメントは削除されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-224">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted.</span></span> <span data-ttu-id="e3c4b-225">これは、ポリシーの割り当て以降に新しく作成されたドキュメントだけでなく、すべての既存のドキュメントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-225">This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="e3c4b-226">セキュリティ&amp; /コンプライアンスセンターで、[**データ管理** \>の**保持**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-226">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="e3c4b-227">[**削除**] の下で、[ **SharePoint Online および OneDrive for business のドキュメント削除ポリシーの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-227">Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="e3c4b-228">ドキュメント削除ポリシー センターが新しいブラウザー タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-228">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="e3c4b-229">**[サイト コレクションのポリシーの割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-229">Choose **Policy Assignments for Site Collections**.</span></span>
    
    ![[サイト コレクションのポリシーの割り当て] オプション](media/IP-Policy-Assignments-for-Site-Collections-option.png)
  
3. <span data-ttu-id="e3c4b-231">**[新しいアイテム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-231">Choose **new item**.</span></span>
    
4. <span data-ttu-id="e3c4b-232">[**サイトコレクションの選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-232">Choose **Choose a site collection**.</span></span> <span data-ttu-id="e3c4b-233">名前または URL でサイトコレクションを検索し、サイトコレクションを選択して [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-233">Search for the site collection by name or URL, select the site collection and click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e3c4b-234">各サイトコレクションには、1つのポリシーセットのみを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-234">Each site collection can have only one set of policies assigned to it.</span></span> <span data-ttu-id="e3c4b-235">このサイトコレクションに既にポリシーが割り当てられていることを示すエラーが表示された場合は、[**サイトコレクションへの割り当て**を**キャンセル** \>する] を選択し、既に割り当てられているポリシーのセットを表示および管理するためのサイトコレクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-235">If you see an error saying that this site collection already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** and select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
![サイト コレクション ページの選択](media/IP-Choose-a-site-collection-page.png)
  
5. <span data-ttu-id="e3c4b-237">**[割り当て済みのポリシーの管理]** を選択し、割り当てたいポリシーを選択し、いずれかのポリシーを既定のポリシーにするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-237">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy.</span></span> <span data-ttu-id="e3c4b-238">既定のポリシーを設定すると、そのポリシーに割り当てられているすべてのサイトでポリシーが自動的に (サイト所有者の操作なしに) アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-238">When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![ポリシー ページの追加および管理](media/IP-Add-and-manage-policies-page.png)
  
6. <span data-ttu-id="e3c4b-240">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-240">Click **Save**.</span></span>
    
7. <span data-ttu-id="e3c4b-p132">サイト所有者が拒否できないようにポリシーをすべてのサイトに適用するには、**[必須のポリシーに指定する]** を選択します。ポリシーを必須にすると、サイト コレクションにその 1 つのポリシーのみを割り当てることができます。そのポリシーは、既定のポリシーとしても指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-p132">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="e3c4b-244">このオプションが灰色表示になっている場合は、**[割り当て済みのポリシーの管理]** を選択し、少なくとも 1 つのポリシーが割り当て済みであり、既定として設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-244">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
8. <span data-ttu-id="e3c4b-245">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-245">Click **Save**.</span></span>
    
## <a name="delete-a-policy-assignment"></a><span data-ttu-id="e3c4b-246">ポリシーの割り当てを削除する</span><span class="sxs-lookup"><span data-stu-id="e3c4b-246">Delete a policy assignment</span></span>

<span data-ttu-id="e3c4b-247">割り当てを削除すると、割り当てられていたポリシーは、サイト コレクションまたはサイト コレクション テンプレートのどのサイトにも適用されなくなります。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-247">When you delete an assignment, the assigned policies will no longer apply to any sites in the site collection or site collection template.</span></span>
  
1. <span data-ttu-id="e3c4b-248">セキュリティ&amp; /コンプライアンスセンターで、[**データ管理** \>の**保持**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-248">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="e3c4b-249">[**削除**] の下で、[ **SharePoint Online および OneDrive for business のドキュメント削除ポリシーの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-249">Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="e3c4b-250">ドキュメント削除ポリシー センターが新しいブラウザー タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-250">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="e3c4b-251">**[テンプレートのポリシーの割り当て]** または **[サイト コレクションのポリシーの割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-251">Choose either **Policy Assignments for Templates** or **Policy Assignments for Site Collections**.</span></span>
    
3. <span data-ttu-id="e3c4b-252">割り当てアイテムを選択し、[**アイテムの削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-252">Select the assignment item and click **Delete Item**.</span></span>
    
    ![ポリシー割り当てのアイテム コマンドの削除](media/IP-Delete-policy-assignment.png)
  
## <a name="delete-a-policy"></a><span data-ttu-id="e3c4b-254">ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="e3c4b-254">Delete a policy</span></span>

<span data-ttu-id="e3c4b-255">使用中のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-255">You can't delete a policy that's in use.</span></span> <span data-ttu-id="e3c4b-256">ポリシーを削除する前に、まず、そのポリシーを含むサイトコレクションおよびサイトコレクションテンプレートへのすべての割り当てを削除する必要があります。前のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-256">Before you can delete a policy, you first need to delete all assignments to site collections and site collection templates that include that policy—see the previous section.</span></span>
  
1. <span data-ttu-id="e3c4b-257">セキュリティ&amp; /コンプライアンス\>センターで、[**削除** \> ] の下にある左側のナビゲーション\>で [**データ管理** \>の**保持**] を選択します。 **SharePoint Online および OneDrive のドキュメント削除ポリシーを管理するfor Business**。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-257">In the Security &amp; Compliance Center \> choose **Data management** \> **Retention** in the left navigation \> under **Delete** \> **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="e3c4b-258">ドキュメント削除ポリシー センターが新しいブラウザー タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-258">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="e3c4b-259">[\* \* 削除ポリシー] \* \* を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-259">Choose \*\* Deletion Policies \*\*.</span></span>
    
    ![削除ポリシー オプション](media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="e3c4b-261">ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-261">Select the policy.</span></span>
    
4. <span data-ttu-id="e3c4b-262">[リボン\> **アイテム**] タブ\>で [**ポリシーの削除**] を削除します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-262">On the Ribbon \> **Items** tab \> **Remove Policy**.</span></span>
    
    ![リボンの [ポリシーの削除] ボタン](media/IP-Remove-Policy-button-on-Ribbon.png)
  
5. <span data-ttu-id="e3c4b-264">ポリシーが使用されている場合、そのポリシーを使用しているすべてのサイトコレクションから削除するかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-264">If the policy is in use, you'll be asked if you want to remove the policy from all of the site collections where it's being used.</span></span> <span data-ttu-id="e3c4b-265">確認したら、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c4b-265">If you're sure, choose **OK**.</span></span>
    
    ![ポリシー確認メッセージの削除](media/IP-Delete-policy-confirmation.png)
  
## <a name="see-also"></a><span data-ttu-id="e3c4b-267">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3c4b-267">See also</span></span>

<span data-ttu-id="e3c4b-268">
  [ドキュメント削除ポリシーの概要](document-deletion-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e3c4b-268">[Overview of document deletion policies](document-deletion-policies.md)</span></span>

[<span data-ttu-id="e3c4b-269">サイトのドキュメント削除ポリシーを適用または削除する</span><span class="sxs-lookup"><span data-stu-id="e3c4b-269">Apply or remove a document deletion policy for a site</span></span>](apply-or-remove-a-document-deletion-policy-for-a-site.md)
 

