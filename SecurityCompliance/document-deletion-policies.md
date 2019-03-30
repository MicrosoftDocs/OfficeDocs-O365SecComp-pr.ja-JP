---
title: ドキュメント削除ポリシーの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 55e8d858-f278-482b-a198-2e62d6a2e6e5
description: 組織では、コンプライアンス、法律、またはその他のビジネス要件のために長期間ドキュメントを保持する必要がある場合があります。 ただし、組織でドキュメントを必要以上に長期に保持している場合は、不要な法的リスクを作成します。 ドキュメント削除ポリシーを使用すると、特定の期間が経過した後にサイト内のドキュメントを削除することによって、積極的にリスクを軽減できます。たとえば、ドキュメントが作成された後に、ユーザーの OneDrive for business サイトのドキュメントを5年後に削除することができます。
ms.openlocfilehash: 2a6b1c29986020ebd63f6ddb960f0d28ba348b3e
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30998700"
---
# <a name="overview-of-document-deletion-policies"></a><span data-ttu-id="1a492-105">ドキュメント削除ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="1a492-105">Overview of document deletion policies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a492-106">今後は、ドキュメント削除ポリシーの代わりに、microsoft 365 コンプライアンスセンター、microsoft 365 セキュリティセンター、または Office 365 セキュリティ&amp;コンプライアンスセンターで作成されたアイテム保持ポリシーまたはラベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1a492-106">Moving forward, we recommend that you use a retention policy or labels created in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security &amp; Compliance Center instead of a document deletion policy.</span></span> <span data-ttu-id="1a492-107">ドキュメント削除ポリシーは、保持ポリシーを使用して引き続き並行して機能しますが、Office 365 でコンテンツを保持または削除する必要がある場合は、アイテム保持ポリシーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1a492-107">Document deletion policies will continue to work side by side with retention policies, but if you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy.</span></span> <span data-ttu-id="1a492-108">詳細については、「[これらの機能の代わりにアイテム保持ポリシーを使用](retention-policies.md#use-a-retention-policy-instead-of-these-features)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a492-108">For more information, see [Use a retention policy instead of these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span></span>
  
<span data-ttu-id="1a492-109">組織では、コンプライアンス、法律、またはその他のビジネス要件のために長期間ドキュメントを保持する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a492-109">Your organization may be required to retain documents for a period of time because of compliance, legal, or other business requirements.</span></span> <span data-ttu-id="1a492-110">ただし、組織でドキュメントを必要以上に長期に保持している場合は、不要な法的リスクを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a492-110">However, if your organization keeps documents longer than required, you create unnecessary legal risk.</span></span> <span data-ttu-id="1a492-111">ドキュメント削除ポリシーを使用すると、特定の期間が経過した後にサイト内のドキュメントを削除することによって、積極的にリスクを軽減できます。たとえば、ドキュメントが作成された後に、ユーザーの OneDrive for business サイトのドキュメントを5年後に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="1a492-111">With a document deletion policy, you can proactively reduce risk by deleting documents in a site after a specific period of time—for example, you can delete documents in users' OneDrive for Business sites five years after the documents were created.</span></span>
  
<span data-ttu-id="1a492-112">ドキュメント削除ポリシーは、次のような強力な柔軟性を備えています。</span><span class="sxs-lookup"><span data-stu-id="1a492-112">Document deletion policies are powerful yet flexible—for example, you can:</span></span>
  
- <span data-ttu-id="1a492-113">サイトの所有者が、一元的に作成および管理するポリシーから選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1a492-113">Allow site owners to choose from policies that you centrally create and manage.</span></span> <span data-ttu-id="1a492-114">また、ポリシーがコンテンツに適用されないことを決定した場合に、サイトの所有者に対して完全な脱退を許可することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a492-114">You can also allow site owners to opt out altogether if they decide a policy does not apply to their content.</span></span>
    
- <span data-ttu-id="1a492-115">サイトコレクション内のすべてのサイト (すべての OneDrive for business サイトなど) に対して1つの必須ポリシーを適用するか、またはチームサイトテンプレートなど、特定のサイトコレクションテンプレートから作成されたすべてのサイトコレクションに対してポリシーを強制することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a492-115">Enforce a single mandatory policy on all sites in a site collection, such as all OneDrive for Business sites, or even enforce a policy on all site collections created from a specific site collection template, such as the Team Site template.</span></span>
    
- <span data-ttu-id="1a492-116">サイトの所有者に必要な操作を行わずに、自動的に適用される既定のルールを既定のポリシーとして指定します。</span><span class="sxs-lookup"><span data-stu-id="1a492-116">Provide a default policy with a default rule that will be automatically applied without any action required by site owners.</span></span>
    
- <span data-ttu-id="1a492-117">サイト所有者が選択できるいくつかの削除ルールを含むポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a492-117">Create a policy that includes several deletion rules that a site owner can choose from.</span></span>
    
<span data-ttu-id="1a492-118">ドキュメント削除ポリシーセンターを使用して、ドキュメント削除ポリシーを作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="1a492-118">You create and manage document deletion policies by using the Document Deletion Policy Center.</span></span> <span data-ttu-id="1a492-119">または、[サイトコレクションを作成](https://go.microsoft.com/fwlink/p/?LinkID=404342)し、[**エンタープライズ**] タブの [**コンプライアンスポリシーセンター** ] を選択して、ポリシーセンターを手動で作成することもできます。各テナントには、ドキュメント削除ポリシーセンターを1つだけ含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1a492-119">Alternatively, you can create the policy center manually by [creating the site collection](https://go.microsoft.com/fwlink/p/?LinkID=404342) and choosing **Compliance Policy Center** on the **Enterprise** tab. Each tenant can have only one Document Deletion Policy Center.</span></span> 
  
![ドキュメント削除ポリシー センターのホーム ページ](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="when-to-use-document-deletion-policies"></a><span data-ttu-id="1a492-121">ドキュメント削除ポリシーを使用する場合</span><span class="sxs-lookup"><span data-stu-id="1a492-121">When to use document deletion policies</span></span>

<span data-ttu-id="1a492-122">Office 365 には、ドキュメント削除ポリシーに加えて、サイトコンテンツに対する以下のアイテム保持ポリシーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1a492-122">In addition to document deletion policies, Office 365 provides these retention policies for site content:</span></span>
  
- [<span data-ttu-id="1a492-123">レコードの管理</span><span class="sxs-lookup"><span data-stu-id="1a492-123">Records management</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404250)
    
- [<span data-ttu-id="1a492-124">コンテンツタイプ、リスト、およびライブラリの情報管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="1a492-124">Information management policies for content types, lists, and libraries</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404239)
    
- [<span data-ttu-id="1a492-125">サイト ポリシー</span><span class="sxs-lookup"><span data-stu-id="1a492-125">Site policies</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404242)
    
<span data-ttu-id="1a492-126">各種類のポリシーは、特定の種類のサイトまたはデータに最適に機能します。</span><span class="sxs-lookup"><span data-stu-id="1a492-126">Each type of policy works best for a specific type of site or data.</span></span> <span data-ttu-id="1a492-127">たとえば、組織には、契約のための財務サイトや記事のサポート技術情報など、コンテンツタイプを使用する高度な構造化サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="1a492-127">For example, your organization may have a highly structured site that uses content types, such as a financial site for contracts or a knowledge base for articles.</span></span> <span data-ttu-id="1a492-128">この場合は、コンテンツタイプのポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a492-128">In this case, you can use content type policies.</span></span> <span data-ttu-id="1a492-129">または、組織で法的ドキュメントを保持する必要がある場合があります。その場合は、コンテンツタイプとレコードセンターを使用してファイルプランを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="1a492-129">Or your organization may need to retain legal documents, in which case you might use content types and a Records Center to implement a file plan.</span></span>
  
<span data-ttu-id="1a492-130">ドキュメント削除ポリシーは、構造化データとコンテンツタイプに最適に機能するレコード管理ポリシーまたは情報管理ポリシーを置き換えません。</span><span class="sxs-lookup"><span data-stu-id="1a492-130">Document deletion policies don't replace records management or information management policies, which work best with structured data and content types.</span></span> <span data-ttu-id="1a492-131">OneDrive for business サイトやチームサイトなどの非構造化データの自動削除を幅広く管理する必要がある場合は、ドキュメント削除ポリシーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a492-131">Instead, you should use document deletion policies when you need to broadly manage the automatic deletion of unstructured data such as OneDrive for Business sites and team sites.</span></span>
  
![サイト コンテンツの保持オプションを示す図](media/IP-Retention-policies-for-site-content.png)
  
<span data-ttu-id="1a492-133">リストまたはライブラリ用に既にコンテンツ タイプ ポリシーまたは情報管理ポリシーを使用しているサイトにドキュメント削除ポリシーを適用した場合、前者のポリシーは無視され、ドキュメント削除ポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="1a492-133">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect.</span></span> <span data-ttu-id="1a492-134">つまり、構造化または非構造化コンテンツ (両方ではない) に対して指定されたポリシーのみを使用するようにサイトを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a492-134">This means you should plan for a site to use only policies meant for structured or unstructured content, not both.</span></span> <span data-ttu-id="1a492-135">ドキュメント削除ポリシーが他のポリシーを上書きする方法の詳細については、「[サイトのドキュメント削除ポリシーを適用または削除する](apply-or-remove-a-document-deletion-policy-for-a-site.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a492-135">For more information on how document deletion policies override other policies, see [Apply or remove a document deletion policy for a site](apply-or-remove-a-document-deletion-policy-for-a-site.md).</span></span>
  
<span data-ttu-id="1a492-136">他のポリシーとは異なり、ドキュメント削除ポリシーは、リストではなく、ドキュメントライブラリでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="1a492-136">Unlike other policies, document deletion policies work only on document libraries, not lists.</span></span>
  
## <a name="deletion-policies-and-rules"></a><span data-ttu-id="1a492-137">削除ポリシーとルール</span><span class="sxs-lookup"><span data-stu-id="1a492-137">Deletion policies and rules</span></span>

<span data-ttu-id="1a492-138">ドキュメント削除ポリシーには、以下を指定する1つまたは複数の削除ルールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a492-138">A document deletion policy contains one or more delete rules that specify:</span></span>
  
- <span data-ttu-id="1a492-139">削除されるまでの期間です。</span><span class="sxs-lookup"><span data-stu-id="1a492-139">The time period until deletion.</span></span>
    
- <span data-ttu-id="1a492-140">ドキュメントの作成日または最終更新日時から削除日を計算するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a492-140">Whether to calculate the deletion date from the when the document was created or last modified.</span></span>
    
- <span data-ttu-id="1a492-141">ドキュメントを完全に削除するか、ゴミ箱に削除するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a492-141">Whether to delete the document permanently or to the Recycle Bin.</span></span>
    
<span data-ttu-id="1a492-142">ポリシーに複数のルールが含まれている場合、サイト所有者は、そのコンテンツに最も適したルールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1a492-142">If a policy contains more than one rule, site owners can select the rule that best applies to their content.</span></span>
  
![新しい削除ルール ページ](media/IP-New-deletion-rule.png)
  
## <a name="policies-and-assignments"></a><span data-ttu-id="1a492-144">ポリシーと割り当て</span><span class="sxs-lookup"><span data-stu-id="1a492-144">Policies and assignments</span></span>

<span data-ttu-id="1a492-145">ドキュメント削除ポリシーを作成したら、それをサイトコレクションテンプレートに割り当てることができます。たとえば、ポリシーを onedrive for business テンプレートに割り当てることによって、すべてのユーザーの onedrive サイトが含まれるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1a492-145">After you create a document deletion policy, you can assign it to a site collection template — for example, you can assign a policy to the OneDrive for Business template so that it includes every user's OneDrive site.</span></span> <span data-ttu-id="1a492-146">ポリシーをサイトコレクションテンプレートに割り当てると、そのテンプレートから作成されたすべてのサイトコレクションに加えて、そのテンプレートから作成されたすべてのサイトコレクションにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="1a492-146">When you assign a policy to a site collection template, this applies to all site collections already created from that template, in addition to any site collections created from that template in the future.</span></span>
  
![OneDrive オプションを表示するテンプレート ページの選択](media/IP-Choose-a-template.png)
  
<span data-ttu-id="1a492-148">ポリシーを特定のサイトコレクションに割り当てることもできます。これにより、そのサイトコレクションテンプレートに割り当てられているすべてのポリシーが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="1a492-148">You can also assign a policy to a specific site collection— doing so overrides any policies that have been assigned to that site collection template.</span></span> <span data-ttu-id="1a492-149">たとえば、ポリシーをチームサイトテンプレートに割り当てることができますが、そのテンプレートから作成された特定のサイトコレクションに対して、異なる一連のポリシーを適用することによって上書きします。</span><span class="sxs-lookup"><span data-stu-id="1a492-149">For example, you may assign policies to the Team Site template, but then override them by applying a different set of policies to a specific site collection created from that template.</span></span>
  
### <a name="one-mandatory-policy-or-several-policies-to-choose-from"></a><span data-ttu-id="1a492-150">1つの必須ポリシーまたは複数のポリシーから選択する</span><span class="sxs-lookup"><span data-stu-id="1a492-150">One mandatory policy or several policies to choose from</span></span>

<span data-ttu-id="1a492-151">ポリシーを割り当てるときに、ポリシーを必須にするように選択して、このポリシーを割り当てることができ、サイトコレクション内のすべてのサイトに適用されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1a492-151">When you assign a policy, you can choose to make it mandatory, so that only this policy can be assigned and that it will be applied to all sites in the site collection.</span></span> <span data-ttu-id="1a492-152">サイト所有者は必須ポリシーから除外することはできません。つまり、サイト内のドキュメントは、何に関係なく削除ポリシーの対象になります。</span><span class="sxs-lookup"><span data-stu-id="1a492-152">Site owners cannot opt out of a mandatory policy, which means documents in the site will be subject to the delete policy no matter what.</span></span>
  
<span data-ttu-id="1a492-153">1つのポリシーを必須にする代わりに、複数のポリシーをサイトコレクションに割り当てることもできます。これにより、各サイト所有者が自分のサイトに適用するポリシーを選択できるようになります。または、完全にオプトアウトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1a492-153">Instead of making a single policy mandatory, you can also assign several policies to a site collection, which allows each site owner to choose which policy to apply to their site, or even to opt out altogether.</span></span> <span data-ttu-id="1a492-154">たとえば、一般的なビジネスドキュメント用に1つのポリシーを作成し、別の保持スケジュールが設定されている財務ドキュメントに対して別のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1a492-154">For example, you can create one policy for general business documents and another policy for financial documents that have a different retention schedule.</span></span> <span data-ttu-id="1a492-155">サイトの所有者は、サイトに含まれるコンテンツと、適用するドキュメント削除ポリシーをよく知っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a492-155">A site owner often knows best what content their site contains and therefore which document deletion policy to apply.</span></span> <span data-ttu-id="1a492-156">各サイトに適用できるポリシーは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="1a492-156">Each site can have only one policy applied to it.</span></span>
  
### <a name="one-rule-or-several-rules-to-choose-from"></a><span data-ttu-id="1a492-157">1つまたは複数のルールを選択する</span><span class="sxs-lookup"><span data-stu-id="1a492-157">One rule or several rules to choose from</span></span>

<span data-ttu-id="1a492-158">さらに、各ポリシーには多くのルールを含めることができます。たとえば、一般的なビジネスドキュメントの削除ポリシーには、次の2つのルールがあります。</span><span class="sxs-lookup"><span data-stu-id="1a492-158">In turn, each policy can contain many rules—for example, a deletion policy for general business documents may have two rules:</span></span>
  
- <span data-ttu-id="1a492-159">法的義務や継続的なビジネスニーズに基づいて保持を必要としないドキュメントは、作成から1年を超えて保持してはなりません。</span><span class="sxs-lookup"><span data-stu-id="1a492-159">Documents that don't need retention based on legal obligations or ongoing business need should not be retained for more than one year from creation.</span></span>
    
- <span data-ttu-id="1a492-160">複数年の間に必要なアクティブなビジネスの使用に必要なドキュメントは、作成から3年以上保持しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a492-160">Documents necessary for active, ongoing business use that are needed for more than one year, should not be retained for more than three years from creation.</span></span>
    
<span data-ttu-id="1a492-161">サイトの所有者は、サイトに一般的なビジネスドキュメントが含まれていることを確認し、この削除ポリシーを選択してから、ポリシーから適切なルールを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a492-161">A site owner can determine that their site contains general business documents, select this deletion policy, and then select the appropriate rule from the policy.</span></span> <span data-ttu-id="1a492-162">ルールは、現在サイトに適用されているポリシー (どのポリシーからではない) からのみ選択でき、ルールはサイト内のすべてのドキュメントライブラリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1a492-162">You can only select a rule from the policy that's currently applied to the site (not from any policy), and the rule applies to all document libraries in the site.</span></span>
  
## <a name="the-relationship-of-site-collections-policies-and-rules"></a><span data-ttu-id="1a492-163">サイトコレクション、ポリシー、およびルールの関係</span><span class="sxs-lookup"><span data-stu-id="1a492-163">The relationship of site collections, policies, and rules</span></span>

<span data-ttu-id="1a492-164">基本的な関係は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a492-164">The basic relationship is this:</span></span>
  
<span data-ttu-id="1a492-165">サイトコレクションまたはサイトコレクションテンプレートには、1つまたは複数のポリシーを割り当てることができます。また、各ポリシーには1つ以上のルールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1a492-165">A site collection or a site collection template can have one or more policies assigned to it, and each of those policies can have one or more rules.</span></span> <span data-ttu-id="1a492-166">ただし、サイトごとにアクティブなポリシーは1つだけであり、サイト内のライブラリに対していつでもアクティブな削除ルールは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="1a492-166">However, there can be only one policy that's active per site, and there can be only one deletion rule that's active at any time for the libraries within the site.</span></span>
  
![ポリシー間の関係を示す図](media/IP-Two-policies-four-rules.png)
  
## <a name="document-deletion-policies-are-inherited"></a><span data-ttu-id="1a492-168">ドキュメント削除ポリシーが継承される</span><span class="sxs-lookup"><span data-stu-id="1a492-168">Document deletion policies are inherited</span></span>

<span data-ttu-id="1a492-169">アクセス許可、ナビゲーションなど、他の多くのサイト機能と同様に、ドキュメント削除ポリシーが継承されます。</span><span class="sxs-lookup"><span data-stu-id="1a492-169">Like permissions, navigation, and many other site features, document deletion policies are inherited.</span></span> <span data-ttu-id="1a492-170">サイト所有者は、サイトのドキュメント削除ポリシーを選択でき、すべてのサブサイトは親からポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="1a492-170">A site owner can select a document deletion policy for their site, and all subsites inherit the policy from the parent.</span></span> <span data-ttu-id="1a492-171">サブサイトの所有者は、別のポリシーとルールの組み合わせを選択することによって継承を解除でき、継承が再度切断されるまで、そのポリシーはすべてのサブサイトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1a492-171">An owner of a subsite can break inheritance by selecting a different policy and rule combination, and that policy applies to all subsites until inheritance is broken again.</span></span>
  
## <a name="assigning-document-deletion-policies-for-the-first-time"></a><span data-ttu-id="1a492-172">初めてドキュメント削除ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1a492-172">Assigning document deletion policies for the first time</span></span>

<span data-ttu-id="1a492-173">ドキュメント削除ポリシーに指定された期間は、ポリシーが割り当てられた後の時間ではなく、ドキュメントが作成または変更されてからの経過時間を意味することを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="1a492-173">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned.</span></span> <span data-ttu-id="1a492-174">たとえば、作成された2年後にドキュメントを完全に削除するドキュメント削除ポリシーを作成し、そのポリシーを、複数のサイトコレクションを作成したサイトコレクションテンプレート (4 または5年前) に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1a492-174">For example, you might create a document deletion policy that permanently deletes documents two years after they were created, and then assign that policy to a site collection template from which several site collections were created four or five years ago.</span></span> <span data-ttu-id="1a492-175">この場合、既存のサイトコレクションには、削除ポリシーで指定された2年より前のバージョンよりも多くのドキュメントが含まれている可能性があります。これは、最初にドキュメント削除ポリシーを割り当てた後に、多くのコンテンツが削除されることを意味します。同時.</span><span class="sxs-lookup"><span data-stu-id="1a492-175">In this case, it's likely that the existing site collections contain many documents that are already older than the two years specified by the deletion policy—this means a lot of content will be deleted soon after assigning the document deletion policy for the first time.</span></span>
  
<span data-ttu-id="1a492-176">ポリシーを初めて割り当てると、サイト内のすべてのドキュメントが評価され、条件を満たしている場合、ドキュメントは削除されます。</span><span class="sxs-lookup"><span data-stu-id="1a492-176">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted.</span></span> <span data-ttu-id="1a492-177">これは、ポリシーの割り当て以降に新しく作成されたドキュメントだけでなく、すべての既存のドキュメントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1a492-177">This applies to all existing documents, not just new documents created since the policy was assigned.</span></span> <span data-ttu-id="1a492-178">また、期間は、ポリシーが最初に割り当てられた時間ではなく、各ドキュメントの保存期間を対象としていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1a492-178">And remember that the time period is for the age of each document, not the time from when the policy was first assigned.</span></span>
  
<span data-ttu-id="1a492-179">そのため、最初にポリシーをサイトに割り当てる前に、既存のコンテンツの保存期間と、ポリシーが既存のコンテンツに与える影響について考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a492-179">Therefore, before you assign a policy to a site for the first time, you should first consider the age of the existing content and how the policy may impact that existing content.</span></span> <span data-ttu-id="1a492-180">また、新しいポリシーを割り当てる前にサイト所有者に連絡して、考えられる影響を評価するための時間を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a492-180">You may also want to communicate the new policy to site owners before assigning it, to give them time to assess the possible impact.</span></span>
  
## <a name="time-lag-for-propagating-policies"></a><span data-ttu-id="1a492-181">ポリシーの伝達のタイムラグ</span><span class="sxs-lookup"><span data-stu-id="1a492-181">Time lag for propagating policies</span></span>

<span data-ttu-id="1a492-182">ポリシーをサイトコレクションに割り当てると、サイト所有者は [**サイトの設定**] ページの [**ドキュメント削除ポリシー** ] リンクを使用して、サイトで利用可能なポリシーを表示および適用します。</span><span class="sxs-lookup"><span data-stu-id="1a492-182">After you assign policies to a site collection, site owners use the **Document Deletion Policies** link on the **Site Settings** page to view and apply policies available for the site.</span></span> 
  
<span data-ttu-id="1a492-183">サイトコレクションにポリシーが割り当てられていない場合、[**ドキュメント削除ポリシー**のリンクは表示されません。</span><span class="sxs-lookup"><span data-stu-id="1a492-183">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="1a492-184">また、リンクは、ポリシーがサイトに割り当てられた直後には表示されず、[**ドキュメント削除ポリシー** ] リンクが表示されるときにポリシーが割り当てられると、最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="1a492-184">Also, the link doesn't appear immediately after policies have been assigned to the site—it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="1a492-185">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="1a492-185">Permissions</span></span>

<span data-ttu-id="1a492-186">ドキュメント削除ポリシーセンターを使用するコンプライアンスチームのメンバーは、ポリシーセンターとポリシーを適用するサイトコレクションの両方に対するアクセス許可を必要とします。</span><span class="sxs-lookup"><span data-stu-id="1a492-186">Members of your compliance team who will use the Document Deletion Policy Center need permissions to both the policy center and site collections to which policies will be applied.</span></span> <span data-ttu-id="1a492-187">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1a492-187">We recommend that you:</span></span>
  
1. <span data-ttu-id="1a492-188">ドキュメント削除ポリシーセンターのすべてのユーザーを含むセキュリティグループを作成します。これは、コンプライアンスポリシー管理チームである可能性が高いと考えられます。</span><span class="sxs-lookup"><span data-stu-id="1a492-188">Create a security group that contains all users of the Document Deletion Policy Center—most likely your compliance policy-management team.</span></span> <span data-ttu-id="1a492-189">詳細については[、「メールが有効なセキュリティグループの管理](https://go.microsoft.com/fwlink/p/?LinkID=404345)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a492-189">See [Manage Mail-Enabled Security Groups](https://go.microsoft.com/fwlink/p/?LinkID=404345) for more information.</span></span> 
    
2. <span data-ttu-id="1a492-190">[ドキュメント削除ポリシーセンター] で、[サイトコレクションの所有者] のアクセス許可をセキュリティグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1a492-190">In the Document Deletion Policy Center, assign site collection owner permissions to the security group.</span></span> <span data-ttu-id="1a492-191">詳細については、「[サイトコレクション管理者のアクセス許可](https://go.microsoft.com/fwlink/p/?LinkID=404346)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a492-191">See [Permissions for site collection administrators](https://go.microsoft.com/fwlink/p/?LinkID=404346) for more information.</span></span> 
    
3. <span data-ttu-id="1a492-192">ドキュメント削除ポリシーを割り当てる必要がある各サイトコレクションで、サイトコレクション所有者のアクセス許可をセキュリティグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1a492-192">In each site collection to which you need to assign document deletion policies, assign site collection owner permissions to the security group.</span></span>
    
## <a name="how-document-deletion-policies-work-with-hold-policies"></a><span data-ttu-id="1a492-193">ドキュメント削除ポリシーで保持ポリシーを使用する方法</span><span class="sxs-lookup"><span data-stu-id="1a492-193">How document deletion policies work with hold policies</span></span>

<span data-ttu-id="1a492-194">保持ポリシーでは、すべてのコンテンツが一定の期間保持されるようにします。また、ドキュメント削除ポリシーを使用すると、特定の期間が経過した後にすべてのコンテンツが削除されるようになります。</span><span class="sxs-lookup"><span data-stu-id="1a492-194">A hold policy ensures that all content is preserved for a specific period of time, while a document deletion policy ensures that all content is deleted after a specific period of time.</span></span>
  
<span data-ttu-id="1a492-195">一定期間ドキュメントを保持する必要がある場合は、削除ポリシーと組み合わせて保持ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a492-195">If you need to retain documents for a fixed period of time, you can use a hold policy in conjunction with a deletion policy.</span></span> <span data-ttu-id="1a492-196">たとえば、変更後3年間、ドキュメントを保持した後、削除ポリシーを設定して、最終変更後3年間そのドキュメントを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="1a492-196">For example, you could hold documents for three years after they are modified, and then set up a deletion policy to delete those documents three years after they were last modified.</span></span>
  
<span data-ttu-id="1a492-197">削除ポリシーは、ホールドを上書きできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1a492-197">Note that a deletion policy cannot override a hold.</span></span> <span data-ttu-id="1a492-198">サイトが保留中で、ドキュメント削除ポリシーによってドキュメントが削除されると、ドキュメントが手動で削除された場合と同じように、ドキュメントが保持保持ライブラリに保持されます。</span><span class="sxs-lookup"><span data-stu-id="1a492-198">If a site is on hold and a document deletion policy deletes a document, then the document will be preserved in the Preservation Hold library in the same way as if the document had been deleted manually.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1a492-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a492-199">See also</span></span>

[<span data-ttu-id="1a492-200">サイトのドキュメント削除ポリシーを適用または削除する</span><span class="sxs-lookup"><span data-stu-id="1a492-200">Apply or remove a document deletion policy for a site</span></span>](apply-or-remove-a-document-deletion-policy-for-a-site.md)

[<span data-ttu-id="1a492-201">ドキュメント削除ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1a492-201">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)


