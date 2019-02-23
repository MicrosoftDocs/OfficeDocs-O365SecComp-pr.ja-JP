---
title: ドキュメント削除ポリシーの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/12/2017
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 55e8d858-f278-482b-a198-2e62d6a2e6e5
description: 組織では、コンプライアンス、法律、またはその他のビジネス要件のために長期間ドキュメントを保持する必要がある場合があります。ただし、組織でドキュメントを必要以上に長期に保持している場合は、不要な法的リスクを作成します。ドキュメント削除ポリシーを使用すると、特定の期間が経過した後にサイト内のドキュメントを削除することによって、積極的にリスクを軽減できます。たとえば、ドキュメントが作成された後に、ユーザーの OneDrive for business サイトのドキュメントを5年後に削除することができます。
ms.openlocfilehash: 9f1355e8a522900aa47ef20ef580918ab5584b99
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218437"
---
# <a name="overview-of-document-deletion-policies"></a><span data-ttu-id="13ac7-105">ドキュメント削除ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="13ac7-105">Overview of document deletion policies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13ac7-p102">転送前に、ドキュメント削除ポリシーではなく、セキュリティ&amp; /コンプライアンスセンターで作成されたアイテム保持ポリシーまたはラベルを使用することをお勧めします。ドキュメント削除ポリシーは、保持ポリシーを使用して引き続き並行して機能しますが、Office 365 でコンテンツを保持または削除する必要がある場合は、アイテム保持ポリシーを使用することをお勧めします。詳細については、「[これらの機能の代わりにアイテム保持ポリシーを使用](retention-policies.md#use-a-retention-policy-instead-of-these-features)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p102">Moving forward, we recommend that you use a retention policy or labels created in the Security &amp; Compliance Center instead of a document deletion policy. Document deletion policies will continue to work side by side with retention policies, but if you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy. For more information, see [Use a retention policy instead of these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span></span>
  
<span data-ttu-id="13ac7-p103">組織では、コンプライアンス、法律、またはその他のビジネス要件のために長期間ドキュメントを保持する必要がある場合があります。ただし、組織でドキュメントを必要以上に長期に保持している場合は、不要な法的リスクを作成します。ドキュメント削除ポリシーを使用すると、特定の期間が経過した後にサイト内のドキュメントを削除することによって、積極的にリスクを軽減できます。たとえば、ドキュメントが作成された後に、ユーザーの OneDrive for business サイトのドキュメントを5年後に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p103">Your organization may be required to retain documents for a period of time because of compliance, legal, or other business requirements. However, if your organization keeps documents longer than required, you create unnecessary legal risk. With a document deletion policy, you can proactively reduce risk by deleting documents in a site after a specific period of time—for example, you can delete documents in users' OneDrive for Business sites five years after the documents were created.</span></span>
  
<span data-ttu-id="13ac7-112">ドキュメント削除ポリシーは、次のような強力な柔軟性を備えています。</span><span class="sxs-lookup"><span data-stu-id="13ac7-112">Document deletion policies are powerful yet flexible—for example, you can:</span></span>
  
- <span data-ttu-id="13ac7-p104">サイト所有者が一元的に作成および管理するポリシーから選択できるようにします。また、サイト所有者がコンテンツにポリシーを適用しないと決定した場合に、まとめて拒否できるようにします。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p104">Allow site owners to choose from policies that you centrally create and manage. You can also allow site owners to opt out altogether if they decide a policy does not apply to their content.</span></span>
    
- <span data-ttu-id="13ac7-115">1 つの必須のポリシーを、すべての OneDrive for Business サイトなど、サイト コレクションのすべてのサイトに強制するか、チーム サイト テンプレートなど、特定のサイト コレクション テンプレートから作成されたすべてのサイト コレクションのポリシーに適用します。</span><span class="sxs-lookup"><span data-stu-id="13ac7-115">Enforce a single mandatory policy on all sites in a site collection, such as all OneDrive for Business sites, or even enforce a policy on all site collections created from a specific site collection template, such as the Team Site template.</span></span>
    
- <span data-ttu-id="13ac7-116">サイト所有者に求められる操作がなくても自動的に適用される、既定のルールを既定のポリシーに指定します。</span><span class="sxs-lookup"><span data-stu-id="13ac7-116">Provide a default policy with a default rule that will be automatically applied without any action required by site owners.</span></span>
    
- <span data-ttu-id="13ac7-117">サイト所有者が選択できるいくつかの削除ルールを含むポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="13ac7-117">Create a policy that includes several deletion rules that a site owner can choose from.</span></span>
    
<span data-ttu-id="13ac7-p105">ドキュメント削除ポリシーセンターを使用してドキュメント削除ポリシーを作成および管理します。これは\*\*\*\* 、Office 365 セキュリティ&amp;コンプライアンスセンターの [保持] で確認できます。または、[サイトコレクションを作成](https://go.microsoft.com/fwlink/p/?LinkID=404342)し、[**エンタープライズ**] タブの [**コンプライアンスポリシーセンター** ] を選択して、ポリシーセンターを手動で作成することもできます。各テナントは、1つのドキュメント削除ポリシーセンターのみを持つことができ、セキュリティ&amp;コンプライアンスセンターから開始した場合は自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p105">You create and manage document deletion policies by using the Document Deletion Policy Center, which you can find under **Retention** in the Office 365 Security &amp; Compliance Center. Alternatively, you can create the policy center manually by [creating the site collection](https://go.microsoft.com/fwlink/p/?LinkID=404342) and choosing **Compliance Policy Center** on the **Enterprise** tab. Each tenant can have only one Document Deletion Policy Center, and it'll be created automatically if you start from the Security &amp; Compliance Center.</span></span> 
  
![ドキュメント削除ポリシー センターのホーム ページ](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="when-to-use-document-deletion-policies"></a><span data-ttu-id="13ac7-121">ドキュメント削除ポリシーを使用する場合</span><span class="sxs-lookup"><span data-stu-id="13ac7-121">When to use document deletion policies</span></span>

<span data-ttu-id="13ac7-122">Office 365 ではドキュメント削除ポリシーのほかに、サイト コンテンツに対して次のアイテム保持ポリシーを用意しています。</span><span class="sxs-lookup"><span data-stu-id="13ac7-122">In addition to document deletion policies, Office 365 provides these retention policies for site content:</span></span>
  
- [<span data-ttu-id="13ac7-123">レコードの管理</span><span class="sxs-lookup"><span data-stu-id="13ac7-123">Records management</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404250)
    
- [<span data-ttu-id="13ac7-124">コンテンツタイプ、リスト、およびライブラリの情報管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="13ac7-124">Information management policies for content types, lists, and libraries</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404239)
    
- [<span data-ttu-id="13ac7-125">サイト ポリシー</span><span class="sxs-lookup"><span data-stu-id="13ac7-125">Site policies</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404242)
    
<span data-ttu-id="13ac7-p106">ポリシーの種類はそれぞれ、特定の種類のサイトまたはデータに対して最も適切に機能します。たとえば、契約用の財務サイトや記事の技術情報サイトなど、コンテンツ タイプを使用して高度に構造化されたサイトを組織が持っている場合があります。この場合、コンテンツ タイプ ポリシーを使用できます。また、組織で法務文書を保持する必要があることがありますが、その場合、コンテンツ タイプとレコード センターを使用して、ファイル プランを実装できます。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p106">Each type of policy works best for a specific type of site or data. For example, your organization may have a highly structured site that uses content types, such as a financial site for contracts or a knowledge base for articles. In this case, you can use content type policies. Or your organization may need to retain legal documents, in which case you might use content types and a Records Center to implement a file plan.</span></span>
  
<span data-ttu-id="13ac7-p107">ドキュメント削除ポリシーは、構造化データとコンテンツタイプに最適に機能するレコード管理ポリシーまたは情報管理ポリシーを置き換えません。OneDrive for business サイトやチームサイトなどの非構造化データの自動削除を幅広く管理する必要がある場合は、ドキュメント削除ポリシーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p107">Document deletion policies don't replace records management or information management policies, which work best with structured data and content types. Instead, you should use document deletion policies when you need to broadly manage the automatic deletion of unstructured data such as OneDrive for Business sites and team sites.</span></span>
  
![サイト コンテンツの保持オプションを示す図](media/IP-Retention-policies-for-site-content.png)
  
<span data-ttu-id="13ac7-p108">リストまたはライブラリ用に既にコンテンツ タイプ ポリシーまたは情報管理ポリシーを使用しているサイトにドキュメント削除ポリシーを適用した場合、前者のポリシーは無視され、ドキュメント削除ポリシーが有効になります。つまり、1 つのサイトで、構造化されたコンテンツのためのポリシー、または構造化されていないコンテンツのためのポリシーのいずれかを使用し、両方は使用しないように計画する必要があります。ドキュメント削除ポリシーがほかのポリシーを上書きする方法の詳細については、「[Apply or remove a document deletion policy for a site](apply-or-remove-a-document-deletion-policy-for-a-site.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p108">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect. This means you should plan for a site to use only policies meant for structured or unstructured content, not both. For more information on how document deletion policies override other policies, see [Apply or remove a document deletion policy for a site](apply-or-remove-a-document-deletion-policy-for-a-site.md).</span></span>
  
<span data-ttu-id="13ac7-136">他のポリシーとは異なり、ドキュメント削除ポリシーは、ドキュメント リストではなくドキュメント ライブラリでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="13ac7-136">Unlike other policies, document deletion policies work only on document libraries, not lists.</span></span>
  
## <a name="deletion-policies-and-rules"></a><span data-ttu-id="13ac7-137">削除ポリシーとルール</span><span class="sxs-lookup"><span data-stu-id="13ac7-137">Deletion policies and rules</span></span>

<span data-ttu-id="13ac7-138">ドキュメント削除ポリシーには、次の項目を指定する削除ルールが 1 つ以上含まれています。</span><span class="sxs-lookup"><span data-stu-id="13ac7-138">A document deletion policy contains one or more delete rules that specify:</span></span>
  
- <span data-ttu-id="13ac7-139">削除するまでの時間。</span><span class="sxs-lookup"><span data-stu-id="13ac7-139">The time period until deletion.</span></span>
    
- <span data-ttu-id="13ac7-140">削除日をドキュメントの作成日から計算するか、最終更新日から計算するか。</span><span class="sxs-lookup"><span data-stu-id="13ac7-140">Whether to calculate the deletion date from the when the document was created or last modified.</span></span>
    
- <span data-ttu-id="13ac7-141">ドキュメントを完全に削除するか、またはごみ箱に移動するか。</span><span class="sxs-lookup"><span data-stu-id="13ac7-141">Whether to delete the document permanently or to the Recycle Bin.</span></span>
    
<span data-ttu-id="13ac7-142">ポリシーに 1 つ以上のルールが含まれている場合、サイト所有者はコンテンツに最も当てはまるルールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="13ac7-142">If a policy contains more than one rule, site owners can select the rule that best applies to their content.</span></span>
  
![新しい削除ルール ページ](media/IP-New-deletion-rule.png)
  
## <a name="policies-and-assignments"></a><span data-ttu-id="13ac7-144">ポリシーと割り当て</span><span class="sxs-lookup"><span data-stu-id="13ac7-144">Policies and assignments</span></span>

<span data-ttu-id="13ac7-p109">ドキュメント削除ポリシーを作成したら、それをサイトコレクションテンプレートに割り当てることができます。たとえば、ポリシーを onedrive for business テンプレートに割り当てることによって、すべてのユーザーの onedrive サイトが含まれるようにすることができます。ポリシーをサイトコレクションテンプレートに割り当てると、そのテンプレートから作成されたすべてのサイトコレクションに加えて、そのテンプレートから作成されたすべてのサイトコレクションにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p109">After you create a document deletion policy, you can assign it to a site collection template — for example, you can assign a policy to the OneDrive for Business template so that it includes every user's OneDrive site. When you assign a policy to a site collection template, this applies to all site collections already created from that template, in addition to any site collections created from that template in the future.</span></span>
  
![OneDrive オプションを表示するテンプレート ページの選択](media/IP-Choose-a-template.png)
  
<span data-ttu-id="13ac7-p110">また、特定のサイト コレクションにポリシーを割り当てることもできます。それにより、そのサイト コレクション テンプレートに割り当てられているポリシーが上書きされます。たとえば、ポリシーをチーム サイト テンプレートに割り当て、そのテンプレートから作成された特定のサイト コレクションに別のポリシーのセットを適用して上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p110">You can also assign a policy to a specific site collection— doing so overrides any policies that have been assigned to that site collection template. For example, you may assign policies to the Team Site template, but then override them by applying a different set of policies to a specific site collection created from that template.</span></span>
  
### <a name="one-mandatory-policy-or-several-policies-to-choose-from"></a><span data-ttu-id="13ac7-150">1 つの必須ポリシーまたは複数のポリシーから選択する</span><span class="sxs-lookup"><span data-stu-id="13ac7-150">One mandatory policy or several policies to choose from</span></span>

<span data-ttu-id="13ac7-p111">ポリシーを割り当てる場合に、そのポリシーを必須にして、そのポリシーだけが割り当て可能で、サイト コレクションのすべてのサイトに適用されるようにすることができます。サイト所有者は、必須のポリシーを拒否できません。つまり、サイトのドキュメントはいかなる場合でも削除ポリシーの対象となります。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p111">When you assign a policy, you can choose to make it mandatory, so that only this policy can be assigned and that it will be applied to all sites in the site collection. Site owners cannot opt out of a mandatory policy, which means documents in the site will be subject to the delete policy no matter what.</span></span>
  
<span data-ttu-id="13ac7-p112">1 つのポリシーを必須にする代わりに、複数のポリシーをサイト コレクションに割り当てることができます。それにより各サイト所有者は、サイトに適用するポリシーを選択したり、すべて拒否したりできます。たとえば、一般的なビジネス ドキュメントに 1 つのポリシーを作成し、別の保存スケジュールを持つ財務ドキュメントには別のポリシーを作成することができます。多くの場合、サイト所有者はサイトにどのコンテンツが含まれているのかをよく理解しているので、どのドキュメント削除ポリシーを適用すべきかを最も理解しています。各サイトには、適用されるポリシーが 1 つしかないこともあります。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p112">Instead of making a single policy mandatory, you can also assign several policies to a site collection, which allows each site owner to choose which policy to apply to their site, or even to opt out altogether. For example, you can create one policy for general business documents and another policy for financial documents that have a different retention schedule. A site owner often knows best what content their site contains and therefore which document deletion policy to apply. Each site can have only one policy applied to it.</span></span>
  
### <a name="one-rule-or-several-rules-to-choose-from"></a><span data-ttu-id="13ac7-157">1 つまたは複数のルールを選択する</span><span class="sxs-lookup"><span data-stu-id="13ac7-157">One rule or several rules to choose from</span></span>

<span data-ttu-id="13ac7-158">さらに、各ポリシーには多くのルールを含めることができます。たとえば、一般的なビジネスドキュメントの削除ポリシーには、次の2つのルールがあります。</span><span class="sxs-lookup"><span data-stu-id="13ac7-158">In turn, each policy can contain many rules—for example, a deletion policy for general business documents may have two rules:</span></span>
  
- <span data-ttu-id="13ac7-159">法的義務や継続的なビジネスニーズに基づいて保持を必要としないドキュメントは、作成から1年を超えて保持してはなりません。</span><span class="sxs-lookup"><span data-stu-id="13ac7-159">Documents that don't need retention based on legal obligations or ongoing business need should not be retained for more than one year from creation.</span></span>
    
- <span data-ttu-id="13ac7-160">1 年以上必要とされる、アクティブで継続中の業務での使用に必要なドキュメントは、作成後 3 年を超えて保持しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13ac7-160">Documents necessary for active, ongoing business use that are needed for more than one year, should not be retained for more than three years from creation.</span></span>
    
<span data-ttu-id="13ac7-p113">サイトの所有者は、サイトに一般的なビジネスドキュメントが含まれていることを確認し、この削除ポリシーを選択してから、ポリシーから適切なルールを選択します。ルールは、現在サイトに適用されているポリシー (どのポリシーからではない) からのみ選択でき、ルールはサイト内のすべてのドキュメントライブラリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p113">A site owner can determine that their site contains general business documents, select this deletion policy, and then select the appropriate rule from the policy. You can only select a rule from the policy that's currently applied to the site (not from any policy), and the rule applies to all document libraries in the site.</span></span>
  
## <a name="the-relationship-of-site-collections-policies-and-rules"></a><span data-ttu-id="13ac7-163">サイト コレクション、ポリシー、およびルールの関係</span><span class="sxs-lookup"><span data-stu-id="13ac7-163">The relationship of site collections, policies, and rules</span></span>

<span data-ttu-id="13ac7-164">基本的な関係は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="13ac7-164">The basic relationship is this:</span></span>
  
<span data-ttu-id="13ac7-p114">サイトコレクションまたはサイトコレクションテンプレートには、1つまたは複数のポリシーを割り当てることができます。また、各ポリシーには1つ以上のルールを含めることができます。ただし、サイトごとにアクティブなポリシーは1つだけであり、サイト内のライブラリに対していつでもアクティブな削除ルールは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p114">A site collection or a site collection template can have one or more policies assigned to it, and each of those policies can have one or more rules. However, there can be only one policy that's active per site, and there can be only one deletion rule that's active at any time for the libraries within the site.</span></span>
  
![ポリシー間の関係を示す図](media/IP-Two-policies-four-rules.png)
  
## <a name="document-deletion-policies-are-inherited"></a><span data-ttu-id="13ac7-168">ドキュメント削除ポリシーは継承される</span><span class="sxs-lookup"><span data-stu-id="13ac7-168">Document deletion policies are inherited</span></span>

<span data-ttu-id="13ac7-p115">権限、ナビゲーション、およびサイトの他の多くの機能のように、ドキュメント削除ポリシーも継承されます。サイト所有者は、サイトのドキュメント削除ポリシーを選択でき、すべてのサブサイトは親からポリシーを継承します。サブサイト所有者は、さまざまなポリシーとルールの組み合わせを選択することで継承を断つことができ、そのポリシーは、継承が再度断たれるまですべてのサブサイトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p115">Like permissions, navigation, and many other site features, document deletion policies are inherited. A site owner can select a document deletion policy for their site, and all subsites inherit the policy from the parent. An owner of a subsite can break inheritance by selecting a different policy and rule combination, and that policy applies to all subsites until inheritance is broken again.</span></span>
  
## <a name="assigning-document-deletion-policies-for-the-first-time"></a><span data-ttu-id="13ac7-172">初めてドキュメント削除ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="13ac7-172">Assigning document deletion policies for the first time</span></span>

<span data-ttu-id="13ac7-p116">ドキュメント削除ポリシーに指定された期間は、ポリシーが割り当てられた後の時間ではなく、ドキュメントが作成または変更されてからの経過時間を意味することを理解しておくことが重要です。たとえば、作成された2年後にドキュメントを完全に削除するドキュメント削除ポリシーを作成し、そのポリシーを、複数のサイトコレクションを作成したサイトコレクションテンプレート (4 または5年前) に割り当てることができます。この場合、既存のサイトコレクションには、削除ポリシーで指定された2年より前のバージョンよりも多くのドキュメントが含まれている可能性があります。これは、最初にドキュメント削除ポリシーを割り当てた後に、多くのコンテンツが削除されることを意味します。同時.</span><span class="sxs-lookup"><span data-stu-id="13ac7-p116">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned. For example, you might create a document deletion policy that permanently deletes documents two years after they were created, and then assign that policy to a site collection template from which several site collections were created four or five years ago. In this case, it's likely that the existing site collections contain many documents that are already older than the two years specified by the deletion policy—this means a lot of content will be deleted soon after assigning the document deletion policy for the first time.</span></span>
  
<span data-ttu-id="13ac7-p117">ポリシーを初めて割り当てると、サイト内のすべてのドキュメントが評価され、条件を満たしている場合、ドキュメントは削除されます。これは、ポリシーの割り当て以降に新しく作成されたドキュメントだけでなく、すべての既存のドキュメントに適用されます。また、期間はポリシーが初めて適用されたときからの時間ではなく、各ドキュメントの保存期間を指します。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p117">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted. This applies to all existing documents, not just new documents created since the policy was assigned. And remember that the time period is for the age of each document, not the time from when the policy was first assigned.</span></span>
  
<span data-ttu-id="13ac7-p118">このため、ポリシーを初めてサイトに割り当てる前に、まず既存のコンテンツの期間と、ポリシーがその既存のコンテンツに与える影響を検討する必要があります。また、新しいポリシーを割り当てる前にサイト所有者に伝達し、発生する可能性がある影響を評価する時間を与えます。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p118">Therefore, before you assign a policy to a site for the first time, you should first consider the age of the existing content and how the policy may impact that existing content. You may also want to communicate the new policy to site owners before assigning it, to give them time to assess the possible impact.</span></span>
  
## <a name="time-lag-for-propagating-policies"></a><span data-ttu-id="13ac7-181">ポリシーの伝達の時間差</span><span class="sxs-lookup"><span data-stu-id="13ac7-181">Time lag for propagating policies</span></span>

<span data-ttu-id="13ac7-182">ポリシーをサイト コレクションに割り当てた後で、サイト所有者は **[サイトの設定]** ページの **[ドキュメント削除ポリシー]** リンクを使用して、サイトで利用できるポリシーを表示して適用します。</span><span class="sxs-lookup"><span data-stu-id="13ac7-182">After you assign policies to a site collection, site owners use the **Document Deletion Policies** link on the **Site Settings** page to view and apply policies available for the site.</span></span> 
  
<span data-ttu-id="13ac7-p119">サイトコレクションにポリシーが割り当てられていない場合、[**ドキュメント削除ポリシー**のリンクは表示されません。また、リンクは、ポリシーがサイトに割り当てられた直後には表示されず、[**ドキュメント削除ポリシー** ] リンクが表示されるときにポリシーが割り当てられると、最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p119">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection. Also, the link doesn't appear immediately after policies have been assigned to the site—it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="13ac7-185">権限</span><span class="sxs-lookup"><span data-stu-id="13ac7-185">Permissions</span></span>

<span data-ttu-id="13ac7-p120">ドキュメント削除ポリシー センターを使用するコンプライアンス チームのメンバーは、ポリシー センターとポリシーが適用されるサイト コレクションの両方に対する権限を持っている必要があります。次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p120">Members of your compliance team who will use the Document Deletion Policy Center need permissions to both the policy center and site collections to which policies will be applied. We recommend that you:</span></span>
  
1. <span data-ttu-id="13ac7-p121">ドキュメント削除ポリシーセンターのすべてのユーザーを含むセキュリティグループを作成します。これは、コンプライアンスポリシー管理チームである可能性が高いと考えられます。詳細については[、「メールが有効なセキュリティグループの管理](https://go.microsoft.com/fwlink/p/?LinkID=404345)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p121">Create a security group that contains all users of the Document Deletion Policy Center—most likely your compliance policy-management team. See [Manage Mail-Enabled Security Groups](https://go.microsoft.com/fwlink/p/?LinkID=404345) for more information.</span></span> 
    
2. <span data-ttu-id="13ac7-p122">[ドキュメント削除ポリシーセンター] で、[サイトコレクションの所有者] のアクセス許可をセキュリティグループに割り当てます。詳細については、「[サイトコレクション管理者のアクセス許可](https://go.microsoft.com/fwlink/p/?LinkID=404346)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p122">In the Document Deletion Policy Center, assign site collection owner permissions to the security group. See [Permissions for site collection administrators](https://go.microsoft.com/fwlink/p/?LinkID=404346) for more information.</span></span> 
    
3. <span data-ttu-id="13ac7-192">ドキュメント削除ポリシーを割り当てる必要がある各サイト コレクションで、サイト コレクション所有者の権限をセキュリティ グループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="13ac7-192">In each site collection to which you need to assign document deletion policies, assign site collection owner permissions to the security group.</span></span>
    
## <a name="how-document-deletion-policies-work-with-hold-policies"></a><span data-ttu-id="13ac7-193">ドキュメント削除ポリシーが保留ポリシーと連携する方法</span><span class="sxs-lookup"><span data-stu-id="13ac7-193">How document deletion policies work with hold policies</span></span>

<span data-ttu-id="13ac7-194">保留ポリシーではすべてのコンテンツが特定の期間保持され、ドキュメント削除ポリシーではすべてのコンテンツが特定の期間の後で削除されるようにします。</span><span class="sxs-lookup"><span data-stu-id="13ac7-194">A hold policy ensures that all content is preserved for a specific period of time, while a document deletion policy ensures that all content is deleted after a specific period of time.</span></span>
  
<span data-ttu-id="13ac7-p123">固定された期間ドキュメントを保持する必要がある場合は、削除ポリシーと組み合わせて保留ポリシーを使用できます。たとえば、ドキュメントは変更後 3 年間保持でき、最後に変更されてから 3 年経過したらこれらのドキュメントを削除する削除ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p123">If you need to retain documents for a fixed period of time, you can use a hold policy in conjunction with a deletion policy. For example, you could hold documents for three years after they are modified, and then set up a deletion policy to delete those documents three years after they were last modified.</span></span>
  
<span data-ttu-id="13ac7-p124">削除ポリシーが、保留を上書きできないことに注意してください。サイトが保留状態で、ドキュメント削除ポリシーによってドキュメントが削除される場合、そのドキュメントは、手動で削除されるときと同じように、アイテム保管ライブラリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="13ac7-p124">Note that a deletion policy cannot override a hold. If a site is on hold and a document deletion policy deletes a document, then the document will be preserved in the Preservation Hold library in the same way as if the document had been deleted manually.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="13ac7-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="13ac7-199">See also</span></span>

[<span data-ttu-id="13ac7-200">サイトのドキュメント削除ポリシーを適用または削除する</span><span class="sxs-lookup"><span data-stu-id="13ac7-200">Apply or remove a document deletion policy for a site</span></span>](apply-or-remove-a-document-deletion-policy-for-a-site.md)

[<span data-ttu-id="13ac7-201">ドキュメント削除ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="13ac7-201">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)


