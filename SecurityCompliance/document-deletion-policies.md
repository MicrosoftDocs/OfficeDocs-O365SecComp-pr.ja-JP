---
title: ドキュメント削除ポリシーの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/12/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- SPO160
ms.assetid: 55e8d858-f278-482b-a198-2e62d6a2e6e5
description: 組織は、法律、コンプライアンスのための時間の期間のドキュメントまたはその他のビジネス要件を維持する必要があります。ただし場合は、組織では、ドキュメントが必要な複数を繰り返し、不要な法的リスクを作成します。ドキュメント削除のポリシーを使用して減らすことができます積極的にリスク特定の期間の後、サイト内のドキュメントを削除することによって、ビジネス ドキュメントが作成された後、5 年間のサイトのユーザーの OneDrive 内のドキュメントを削除するなどです。
ms.openlocfilehash: 495dd781c56e25e884d47f72a7e48410ea340208
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013661"
---
# <a name="overview-of-document-deletion-policies"></a><span data-ttu-id="3c6ad-105">ドキュメント削除ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="3c6ad-105">Overview of document deletion policies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c6ad-p102">リテンション ・ ポリシーまたはセキュリティで作成したラベルを使用することお勧め、&amp;ドキュメント ポリシーの削除ではなくコンプライアンス センターです。ドキュメント削除のポリシーは、保持ポリシーでは、密接に共同作業する続行されますが、リテンション ・ ポリシーを使用することをお勧め保持するか、Office 365 の任意の場所のコンテンツを削除する必要がある場合。詳細については、[これらの機能ではなく保存ポリシーを使用する](retention-policies.md#use-a-retention-policy-instead-of-these-features)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p102">Moving forward, we recommend that you use a retention policy or labels created in the Security &amp; Compliance Center instead of a document deletion policy. Document deletion policies will continue to work side by side with retention policies, but if you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy. For more information, see [Use a retention policy instead of these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span></span>
  
<span data-ttu-id="3c6ad-p103">組織は、法律、コンプライアンスのための時間の期間のドキュメントまたはその他のビジネス要件を維持する必要があります。ただし場合は、組織では、ドキュメントが必要な複数を繰り返し、不要な法的リスクを作成します。ドキュメント削除のポリシーを使用して減らすことができます積極的にリスク特定の期間の後、サイト内のドキュメントを削除することによって、ビジネス ドキュメントが作成された後、5 年間のサイトのユーザーの OneDrive 内のドキュメントを削除するなどです。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p103">Your organization may be required to retain documents for a period of time because of compliance, legal, or other business requirements. However, if your organization keeps documents longer than required, you create unnecessary legal risk. With a document deletion policy, you can proactively reduce risk by deleting documents in a site after a specific period of time—for example, you can delete documents in users' OneDrive for Business sites five years after the documents were created.</span></span>
  
<span data-ttu-id="3c6ad-112">ドキュメント削除のポリシーは強力なまだ柔軟な-などを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-112">Document deletion policies are powerful yet flexible—for example, you can:</span></span>
  
- <span data-ttu-id="3c6ad-p104">サイト所有者が一元的に作成および管理するポリシーから選択できるようにします。また、サイト所有者がコンテンツにポリシーを適用しないと決定した場合に、まとめて拒否できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p104">Allow site owners to choose from policies that you centrally create and manage. You can also allow site owners to opt out altogether if they decide a policy does not apply to their content.</span></span>
    
- <span data-ttu-id="3c6ad-115">1 つの必須のポリシーを、すべての OneDrive for Business サイトなど、サイト コレクションのすべてのサイトに強制するか、チーム サイト テンプレートなど、特定のサイト コレクション テンプレートから作成されたすべてのサイト コレクションのポリシーに適用します。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-115">Enforce a single mandatory policy on all sites in a site collection, such as all OneDrive for Business sites, or even enforce a policy on all site collections created from a specific site collection template, such as the Team Site template.</span></span>
    
- <span data-ttu-id="3c6ad-116">サイト所有者に求められる操作がなくても自動的に適用される、既定のルールを既定のポリシーに指定します。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-116">Provide a default policy with a default rule that will be automatically applied without any action required by site owners.</span></span>
    
- <span data-ttu-id="3c6ad-117">サイト所有者が選択できるいくつかの削除ルールを含むポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-117">Create a policy that includes several deletion rules that a site owner can choose from.</span></span>
    
<span data-ttu-id="3c6ad-p105">作成し、ドキュメントの削除ポリシーを管理センターを使用して、ドキュメントの削除ポリシー、Office 365 のセキュリティ**保持**の下にあります&amp;コンプライアンス センターです。または、[サイト コレクションを作成](https://go.microsoft.com/fwlink/p/?LinkID=404342)し、[**エンタープライズ**] タブで、**コンプライアンス ・ ポリシー ・ センター**を選択することによって手動でポリシー センターを作成します。各テナントは、1 つのドキュメントの削除ポリシー センターを持つことができ、セキュリティを起動する場合に自動的に作成されます&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p105">You create and manage document deletion policies by using the Document Deletion Policy Center, which you can find under **Retention** in the Office 365 Security &amp; Compliance Center. Alternatively, you can create the policy center manually by [creating the site collection](https://go.microsoft.com/fwlink/p/?LinkID=404342) and choosing **Compliance Policy Center** on the **Enterprise** tab. Each tenant can have only one Document Deletion Policy Center, and it'll be created automatically if you start from the Security &amp; Compliance Center.</span></span> 
  
![ドキュメント削除ポリシー センターのホーム ページ](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="when-to-use-document-deletion-policies"></a><span data-ttu-id="3c6ad-121">ドキュメント削除ポリシーを使用する場合</span><span class="sxs-lookup"><span data-stu-id="3c6ad-121">When to use document deletion policies</span></span>

<span data-ttu-id="3c6ad-122">Office 365 ではドキュメント削除ポリシーのほかに、サイト コンテンツに対して次のアイテム保持ポリシーを用意しています。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-122">In addition to document deletion policies, Office 365 provides these retention policies for site content:</span></span>
  
- [<span data-ttu-id="3c6ad-123">レコードの管理</span><span class="sxs-lookup"><span data-stu-id="3c6ad-123">Records management</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404250)
    
- [<span data-ttu-id="3c6ad-124">コンテンツ タイプ、リスト、およびライブラリの情報管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="3c6ad-124">Information management policies for content types, lists, and libraries</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404239)
    
- [<span data-ttu-id="3c6ad-125">サイト ポリシー</span><span class="sxs-lookup"><span data-stu-id="3c6ad-125">Site policies</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404242)
    
<span data-ttu-id="3c6ad-p106">ポリシーの種類はそれぞれ、特定の種類のサイトまたはデータに対して最も適切に機能します。たとえば、契約用の財務サイトや記事の技術情報サイトなど、コンテンツ タイプを使用して高度に構造化されたサイトを組織が持っている場合があります。この場合、コンテンツ タイプ ポリシーを使用できます。また、組織で法務文書を保持する必要があることがありますが、その場合、コンテンツ タイプとレコード センターを使用して、ファイル プランを実装できます。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p106">Each type of policy works best for a specific type of site or data. For example, your organization may have a highly structured site that uses content types, such as a financial site for contracts or a knowledge base for articles. In this case, you can use content type policies. Or your organization may need to retain legal documents, in which case you might use content types and a Records Center to implement a file plan.</span></span>
  
<span data-ttu-id="3c6ad-p107">ドキュメント削除のポリシーには、レコードの管理や情報管理ポリシーは、構造化データとコンテンツの種類で最適に動作しない交換してください。代わりに、幅広くビジネス サイトやチーム サイトの OneDrive などの非構造化データの自動削除を管理するために必要なときに、ドキュメントの削除ポリシーを使用してください。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p107">Document deletion policies don't replace records management or information management policies, which work best with structured data and content types. Instead, you should use document deletion policies when you need to broadly manage the automatic deletion of unstructured data such as OneDrive for Business sites and team sites.</span></span>
  
![サイト コンテンツの保持オプションを示す図](media/IP-Retention-policies-for-site-content.png)
  
<span data-ttu-id="3c6ad-p108">リストまたはライブラリ用に既にコンテンツ タイプ ポリシーまたは情報管理ポリシーを使用しているサイトにドキュメント削除ポリシーを適用した場合、前者のポリシーは無視され、ドキュメント削除ポリシーが有効になります。つまり、1 つのサイトで、構造化されたコンテンツのためのポリシー、または構造化されていないコンテンツのためのポリシーのいずれかを使用し、両方は使用しないように計画する必要があります。ドキュメント削除ポリシーがほかのポリシーを上書きする方法の詳細については、「[Apply or remove a document deletion policy for a site](apply-or-remove-a-document-deletion-policy-for-a-site.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p108">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect. This means you should plan for a site to use only policies meant for structured or unstructured content, not both. For more information on how document deletion policies override other policies, see [Apply or remove a document deletion policy for a site](apply-or-remove-a-document-deletion-policy-for-a-site.md).</span></span>
  
<span data-ttu-id="3c6ad-136">他のポリシーとは異なり、ドキュメント削除ポリシーは、ドキュメント リストではなくドキュメント ライブラリでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-136">Unlike other policies, document deletion policies work only on document libraries, not lists.</span></span>
  
## <a name="deletion-policies-and-rules"></a><span data-ttu-id="3c6ad-137">削除ポリシーとルール</span><span class="sxs-lookup"><span data-stu-id="3c6ad-137">Deletion policies and rules</span></span>

<span data-ttu-id="3c6ad-138">ドキュメント削除ポリシーには、次の項目を指定する削除ルールが 1 つ以上含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-138">A document deletion policy contains one or more delete rules that specify:</span></span>
  
- <span data-ttu-id="3c6ad-139">削除するまでの時間。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-139">The time period until deletion.</span></span>
    
- <span data-ttu-id="3c6ad-140">削除日をドキュメントの作成日から計算するか、最終更新日から計算するか。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-140">Whether to calculate the deletion date from the when the document was created or last modified.</span></span>
    
- <span data-ttu-id="3c6ad-141">ドキュメントを完全に削除するか、またはごみ箱に移動するか。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-141">Whether to delete the document permanently or to the Recycle Bin.</span></span>
    
<span data-ttu-id="3c6ad-142">ポリシーに 1 つ以上のルールが含まれている場合、サイト所有者はコンテンツに最も当てはまるルールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-142">If a policy contains more than one rule, site owners can select the rule that best applies to their content.</span></span>
  
![新しい削除ルール ページ](media/IP-New-deletion-rule.png)
  
## <a name="policies-and-assignments"></a><span data-ttu-id="3c6ad-144">ポリシーと割り当て</span><span class="sxs-lookup"><span data-stu-id="3c6ad-144">Policies and assignments</span></span>

<span data-ttu-id="3c6ad-p109">ドキュメント削除のポリシーを作成した後は、サイト コレクションのテンプレートに割り当てることができます-たとえば、割り当てることができますポリシー ビジネス テンプレートの OneDrive にすべてのユーザーの OneDrive のサイトが含まれるようにします。サイト コレクションのテンプレートにポリシーを割り当てると、この後でそのテンプレートから作成されたサイト コレクションだけでなく、そのテンプレートから作成済みのすべてのサイト コレクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p109">After you create a document deletion policy, you can assign it to a site collection template — for example, you can assign a policy to the OneDrive for Business template so that it includes every user's OneDrive site. When you assign a policy to a site collection template, this applies to all site collections already created from that template, in addition to any site collections created from that template in the future.</span></span>
  
![OneDrive オプションを表示するテンプレート ページの選択](media/IP-Choose-a-template.png)
  
<span data-ttu-id="3c6ad-p110">また、特定のサイト コレクションにポリシーを割り当てることもできます。それにより、そのサイト コレクション テンプレートに割り当てられているポリシーが上書きされます。たとえば、ポリシーをチーム サイト テンプレートに割り当て、そのテンプレートから作成された特定のサイト コレクションに別のポリシーのセットを適用して上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p110">You can also assign a policy to a specific site collection— doing so overrides any policies that have been assigned to that site collection template. For example, you may assign policies to the Team Site template, but then override them by applying a different set of policies to a specific site collection created from that template.</span></span>
  
### <a name="one-mandatory-policy-or-several-policies-to-choose-from"></a><span data-ttu-id="3c6ad-150">1 つの必須ポリシーまたは複数のポリシーから選択する</span><span class="sxs-lookup"><span data-stu-id="3c6ad-150">One mandatory policy or several policies to choose from</span></span>

<span data-ttu-id="3c6ad-p111">ポリシーを割り当てる場合に、そのポリシーを必須にして、そのポリシーだけが割り当て可能で、サイト コレクションのすべてのサイトに適用されるようにすることができます。サイト所有者は、必須のポリシーを拒否できません。つまり、サイトのドキュメントはいかなる場合でも削除ポリシーの対象となります。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p111">When you assign a policy, you can choose to make it mandatory, so that only this policy can be assigned and that it will be applied to all sites in the site collection. Site owners cannot opt out of a mandatory policy, which means documents in the site will be subject to the delete policy no matter what.</span></span>
  
<span data-ttu-id="3c6ad-p112">1 つのポリシーを必須にする代わりに、複数のポリシーをサイト コレクションに割り当てることができます。それにより各サイト所有者は、サイトに適用するポリシーを選択したり、すべて拒否したりできます。たとえば、一般的なビジネス ドキュメントに 1 つのポリシーを作成し、別の保存スケジュールを持つ財務ドキュメントには別のポリシーを作成することができます。多くの場合、サイト所有者はサイトにどのコンテンツが含まれているのかをよく理解しているので、どのドキュメント削除ポリシーを適用すべきかを最も理解しています。各サイトには、適用されるポリシーが 1 つしかないこともあります。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p112">Instead of making a single policy mandatory, you can also assign several policies to a site collection, which allows each site owner to choose which policy to apply to their site, or even to opt out altogether. For example, you can create one policy for general business documents and another policy for financial documents that have a different retention schedule. A site owner often knows best what content their site contains and therefore which document deletion policy to apply. Each site can have only one policy applied to it.</span></span>
  
### <a name="one-rule-or-several-rules-to-choose-from"></a><span data-ttu-id="3c6ad-157">1 つまたは複数のルールを選択する</span><span class="sxs-lookup"><span data-stu-id="3c6ad-157">One rule or several rules to choose from</span></span>

<span data-ttu-id="3c6ad-158">さらに、各ポリシーが多くのルールを含めることができます-たとえば、一般的なビジネス ・ ドキュメントの削除ポリシーが 2 つの規則を必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-158">In turn, each policy can contain many rules—for example, a deletion policy for general business documents may have two rules:</span></span>
  
- <span data-ttu-id="3c6ad-159">法的義務に基づいて、ドキュメントの保存の必要がないか、作成から 1 年以上の継続的なビジネスの必要性は保持されませんする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-159">Documents that don't need retention based on legal obligations or ongoing business need should not be retained for more than one year from creation.</span></span>
    
- <span data-ttu-id="3c6ad-160">1 年以上必要とされる、アクティブで継続中の業務での使用に必要なドキュメントは、作成後 3 年を超えて保持しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-160">Documents necessary for active, ongoing business use that are needed for more than one year, should not be retained for more than three years from creation.</span></span>
    
<span data-ttu-id="3c6ad-p113">サイトの所有者は、サイトにはで全般的な業務が含まれているを判断できますドキュメントがこの削除のポリシーを選択し、ポリシーから適切なルールを選択します。(すべてのポリシー) からではなくサイトに現在適用されているポリシーでルールを選択することができ、サイト内のすべてのドキュメント ライブラリに規則を適用します。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p113">A site owner can determine that their site contains general business documents, select this deletion policy, and then select the appropriate rule from the policy. You can only select a rule from the policy that's currently applied to the site (not from any policy), and the rule applies to all document libraries in the site.</span></span>
  
## <a name="the-relationship-of-site-collections-policies-and-rules"></a><span data-ttu-id="3c6ad-163">サイト コレクション、ポリシー、およびルールの関係</span><span class="sxs-lookup"><span data-stu-id="3c6ad-163">The relationship of site collections, policies, and rules</span></span>

<span data-ttu-id="3c6ad-164">基本的な関係は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-164">The basic relationship is this:</span></span>
  
<span data-ttu-id="3c6ad-p114">サイト コレクションまたはサイト コレクションのテンプレートは、それに割り当てられている 1 つまたは複数のポリシーを持つことができ、それらのポリシーの 1 つまたは複数の規則を持つことができます。ただし、サイトごとにアクティブになっているポリシーは 1 つのみ、サイト内のライブラリには、いつでもアクティブになっている 1 つだけの削除ルールが存在することができます。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p114">A site collection or a site collection template can have one or more policies assigned to it, and each of those policies can have one or more rules. However, there can be only one policy that's active per site, and there can be only one deletion rule that's active at any time for the libraries within the site.</span></span>
  
![ポリシー間の関係を示す図](media/IP-Two-policies-four-rules.png)
  
## <a name="document-deletion-policies-are-inherited"></a><span data-ttu-id="3c6ad-168">ドキュメント削除ポリシーは継承される</span><span class="sxs-lookup"><span data-stu-id="3c6ad-168">Document deletion policies are inherited</span></span>

<span data-ttu-id="3c6ad-p115">権限、ナビゲーション、およびサイトの他の多くの機能のように、ドキュメント削除ポリシーも継承されます。サイト所有者は、サイトのドキュメント削除ポリシーを選択でき、すべてのサブサイトは親からポリシーを継承します。サブサイト所有者は、さまざまなポリシーとルールの組み合わせを選択することで継承を断つことができ、そのポリシーは、継承が再度断たれるまですべてのサブサイトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p115">Like permissions, navigation, and many other site features, document deletion policies are inherited. A site owner can select a document deletion policy for their site, and all subsites inherit the policy from the parent. An owner of a subsite can break inheritance by selecting a different policy and rule combination, and that policy applies to all subsites until inheritance is broken again.</span></span>
  
## <a name="assigning-document-deletion-policies-for-the-first-time"></a><span data-ttu-id="3c6ad-172">初めてドキュメント削除ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3c6ad-172">Assigning document deletion policies for the first time</span></span>

<span data-ttu-id="3c6ad-p116">ドキュメントの指定された期間削除ポリシーということ、時間、ドキュメントが作成または変更されると、時刻ではなく、ポリシーが割り当てられていたためであるために理解する重要です。などのドキュメントを作成した後、2 年間を完全に削除するドキュメント削除ポリシーを作成し、いくつかのサイト コレクションが 4、5 年前が作成されたサイト コレクションのテンプレートにそのポリシーを割り当てる可能性があります。削除ポリシーで指定された 2 年以上経過されている多くのドキュメントには既存のサイト コレクションが含まれている可能性がありますが、ここで、つまり、最初のドキュメントの削除ポリシーの割り当て後すぐに大量のコンテンツが削除されます時間です。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p116">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned. For example, you might create a document deletion policy that permanently deletes documents two years after they were created, and then assign that policy to a site collection template from which several site collections were created four or five years ago. In this case, it's likely that the existing site collections contain many documents that are already older than the two years specified by the deletion policy—this means a lot of content will be deleted soon after assigning the document deletion policy for the first time.</span></span>
  
<span data-ttu-id="3c6ad-p117">ポリシーを初めて割り当てると、サイト内のすべてのドキュメントが評価され、条件を満たしている場合、ドキュメントは削除されます。これは、ポリシーの割り当て以降に新しく作成されたドキュメントだけでなく、すべての既存のドキュメントに適用されます。また、期間はポリシーが初めて適用されたときからの時間ではなく、各ドキュメントの保存期間を指します。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p117">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted. This applies to all existing documents, not just new documents created since the policy was assigned. And remember that the time period is for the age of each document, not the time from when the policy was first assigned.</span></span>
  
<span data-ttu-id="3c6ad-p118">このため、ポリシーを初めてサイトに割り当てる前に、まず既存のコンテンツの期間と、ポリシーがその既存のコンテンツに与える影響を検討する必要があります。また、新しいポリシーを割り当てる前にサイト所有者に伝達し、発生する可能性がある影響を評価する時間を与えます。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p118">Therefore, before you assign a policy to a site for the first time, you should first consider the age of the existing content and how the policy may impact that existing content. You may also want to communicate the new policy to site owners before assigning it, to give them time to assess the possible impact.</span></span>
  
## <a name="time-lag-for-propagating-policies"></a><span data-ttu-id="3c6ad-181">ポリシーの伝達の時間差</span><span class="sxs-lookup"><span data-stu-id="3c6ad-181">Time lag for propagating policies</span></span>

<span data-ttu-id="3c6ad-182">ポリシーをサイト コレクションに割り当てた後で、サイト所有者は **[サイトの設定]** ページの **[ドキュメント削除ポリシー]** リンクを使用して、サイトで利用できるポリシーを表示して適用します。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-182">After you assign policies to a site collection, site owners use the **Document Deletion Policies** link on the **Site Settings** page to view and apply policies available for the site.</span></span> 
  
<span data-ttu-id="3c6ad-p119">サイト コレクションにポリシーが割り当てられていない限り、**ドキュメントの削除ポリシー**のリンクは表示されません。ポリシーは、サイトに割り当てられている後にすぐにリンクが表示されないまた、-にポリシーが割り当てられている**ドキュメントの削除ポリシー**のリンクが表示されたらときから 24 時間がかかることができます。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p119">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection. Also, the link doesn't appear immediately after policies have been assigned to the site—it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="3c6ad-185">権限</span><span class="sxs-lookup"><span data-stu-id="3c6ad-185">Permissions</span></span>

<span data-ttu-id="3c6ad-p120">ドキュメント削除ポリシー センターを使用するコンプライアンス チームのメンバーは、ポリシー センターとポリシーが適用されるサイト コレクションの両方に対する権限を持っている必要があります。次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p120">Members of your compliance team who will use the Document Deletion Policy Center need permissions to both the policy center and site collections to which policies will be applied. We recommend that you:</span></span>
  
1. <span data-ttu-id="3c6ad-p121">ドキュメントの削除ポリシー センターのすべてのユーザーを含むセキュリティ グループを作成、コンプライアンス ・ ポリシーの管理、チーム可能性があります。詳細については、 [Manage Mail-Enabled セキュリティ グループ](https://go.microsoft.com/fwlink/p/?LinkID=404345)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p121">Create a security group that contains all users of the Document Deletion Policy Center—most likely your compliance policy-management team. See [Manage Mail-Enabled Security Groups](https://go.microsoft.com/fwlink/p/?LinkID=404345) for more information.</span></span> 
    
2. <span data-ttu-id="3c6ad-p122">センターではドキュメントの削除ポリシー、サイト コレクションの所有者のアクセス許可グループに割り当てるセキュリティです。詳細については、[サイト コレクションの管理者のアクセス許可](https://go.microsoft.com/fwlink/p/?LinkID=404346)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p122">In the Document Deletion Policy Center, assign site collection owner permissions to the security group. See [Permissions for site collection administrators](https://go.microsoft.com/fwlink/p/?LinkID=404346) for more information.</span></span> 
    
3. <span data-ttu-id="3c6ad-192">ドキュメント削除ポリシーを割り当てる必要がある各サイト コレクションで、サイト コレクション所有者の権限をセキュリティ グループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-192">In each site collection to which you need to assign document deletion policies, assign site collection owner permissions to the security group.</span></span>
    
## <a name="how-document-deletion-policies-work-with-hold-policies"></a><span data-ttu-id="3c6ad-193">ドキュメント削除ポリシーが保留ポリシーと連携する方法</span><span class="sxs-lookup"><span data-stu-id="3c6ad-193">How document deletion policies work with hold policies</span></span>

<span data-ttu-id="3c6ad-194">保留ポリシーではすべてのコンテンツが特定の期間保持され、ドキュメント削除ポリシーではすべてのコンテンツが特定の期間の後で削除されるようにします。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-194">A hold policy ensures that all content is preserved for a specific period of time, while a document deletion policy ensures that all content is deleted after a specific period of time.</span></span>
  
<span data-ttu-id="3c6ad-p123">固定された期間ドキュメントを保持する必要がある場合は、削除ポリシーと組み合わせて保留ポリシーを使用できます。たとえば、ドキュメントは変更後 3 年間保持でき、最後に変更されてから 3 年経過したらこれらのドキュメントを削除する削除ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p123">If you need to retain documents for a fixed period of time, you can use a hold policy in conjunction with a deletion policy. For example, you could hold documents for three years after they are modified, and then set up a deletion policy to delete those documents three years after they were last modified.</span></span>
  
<span data-ttu-id="3c6ad-p124">削除ポリシーが、保留を上書きできないことに注意してください。サイトが保留状態で、ドキュメント削除ポリシーによってドキュメントが削除される場合、そのドキュメントは、手動で削除されるときと同じように、アイテム保管ライブラリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="3c6ad-p124">Note that a deletion policy cannot override a hold. If a site is on hold and a document deletion policy deletes a document, then the document will be preserved in the Preservation Hold library in the same way as if the document had been deleted manually.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3c6ad-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c6ad-199">See also</span></span>

[<span data-ttu-id="3c6ad-200">サイトのドキュメント削除ポリシーを適用または削除する</span><span class="sxs-lookup"><span data-stu-id="3c6ad-200">Apply or remove a document deletion policy for a site</span></span>](apply-or-remove-a-document-deletion-policy-for-a-site.md)

[<span data-ttu-id="3c6ad-201">ドキュメント削除ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3c6ad-201">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)


