---
title: サイトのドキュメント削除ポリシーを適用または削除する
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: 多くの場合、組織は一定期間、ドキュメントの保持が要求されるコンプライアンス、法的要件、その他の規制を受けます。しかし、必要以上にドキュメントを長く保持すると、組織が法的なリスクにさらされる場合があります。このため、組織は、例えば一般的なビジネス文書は作成の 5 年後に削除する必要があるといった、ドキュメント削除ポリシーをサイトに作成する場合があります。
ms.openlocfilehash: abee0da7adfba6f653743d503f8b30770ee93c40
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532560"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="afa32-105">サイトのドキュメント削除ポリシーを適用または削除する</span><span class="sxs-lookup"><span data-stu-id="afa32-105">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="afa32-p102">多くの場合、組織は一定期間、ドキュメントの保持が要求されるコンプライアンス、法的要件、その他の規制を受けます。しかし、必要以上にドキュメントを長く保持すると、組織が法的なリスクにさらされる場合があります。このため、組織は、例えば一般的なビジネス文書は作成の 5 年後に削除する必要があるといった、ドキュメント削除ポリシーをサイトに作成する場合があります。</span><span class="sxs-lookup"><span data-stu-id="afa32-p102">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time. However, retaining documents for longer than required can expose the organization to legal risk. For this reason, your organization may have created a document deletion policy for your site — for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="afa32-109">組織に応じて、ドキュメント削除ポリシーには次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="afa32-109">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="afa32-110">**必須**サイトの所有者は、お客様が、必須なポリシーは、サイトに自動的に適用されてからです。</span><span class="sxs-lookup"><span data-stu-id="afa32-110">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="afa32-111">**既定** 既定のポリシーがサイトに自動的に適用されますが、サイトの所有者には次の選択肢がある。</span><span class="sxs-lookup"><span data-stu-id="afa32-111">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="afa32-112">利用可能な場合は、別のポリシーを選択する。</span><span class="sxs-lookup"><span data-stu-id="afa32-112">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="afa32-113">そのポリシーがサイト内のコンテンツに関連していない場合は、全く適用しない。</span><span class="sxs-lookup"><span data-stu-id="afa32-113">Opt out of the policy entirely if it is not relevant to the content in the site.</span></span>
    
- <span data-ttu-id="afa32-114">**必須でも既定でもない** この場合、サイトにはどのポリシーも自動的に適用されず、サイトの所有者はポリシーを適用するためにアクションが必要。</span><span class="sxs-lookup"><span data-stu-id="afa32-114">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="afa32-p103">ドキュメント削除ポリシーには複数のルールが含まれる場合があります。例えば、あるルールはドキュメントを作成の 1 年後に削除し、別のルールはドキュメントが最後に変更されてから 1 年後に削除する、というようにです。ポリシーに複数のルールが含まれている場合は、サイトへの適用が最適になるルールを選択できます。削除ルールは、サイト内のすべてのライブラリに適用されます。1 つのサイトに一度に有効にできるのは、1 つのポリシーおよび 1 つのルールのみです。ポリシー同様、ルールを既定として設定し、ポリシーが適用されたときに自動的に適用されるようにできます。</span><span class="sxs-lookup"><span data-stu-id="afa32-p103">A document deletion policy may contain more than one rule — for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified. If a policy contains more than one rule, you can select the rule that best applies to your site. The delete rule will be applied to all libraries within the site. Only one policy and one rule can be active in a site at one time. Like a policy, a rule can be set as default, so that it is applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="afa32-p104">最後に、ドキュメント削除ポリシーは継承されます。サイトにポリシーやルールを選択すると、その選択はすべてのサブサイトに継承されますが、サブサイトの所有者は別のポリシーやルールを選択することにより、継承を止めることができます。ポリシーやルールを選択する際には、サイトの下位にあるすべてのサブサイトのコンテンツを検討してください。</span><span class="sxs-lookup"><span data-stu-id="afa32-p104">Finally, document deletion policies are inherited. When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule. When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="afa32-123">サイト コレクションで使用できるドキュメント削除ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="afa32-123">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="afa32-p105">組織は、異なるサイト コレクションに異なるポリシーを割り当てる場合があります。サイト コレクション レベルでは、サイト コレクションの所有者は、そのサイト コレクションで使用可能なすべてのドキュメント削除ポリシーを表示できます。ポリシーはサイト コレクション テンプレート (そしてそのテンプレートから作成されたすべてのサイト コレクション) で使用できるようになっている場合も、その特定のサイト コレクションで使用できるようになっている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="afa32-p105">Your organization may assign different policies to different site collections. At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection. The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="afa32-127">**設定**ダイアログ ボックスの [歯車アイコン] を選択して右上隅で、[サイト コレクションのトップレベル サイトで\>**サイトの設定**。</span><span class="sxs-lookup"><span data-stu-id="afa32-127">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="afa32-128">**サイト コレクションの管理**下にある\>**ドキュメント削除のポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="afa32-128">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="afa32-p106">サイト コレクションにポリシーが割り当てられていない限り、**ドキュメントの削除ポリシー**のリンクは表示されません。ポリシーは、サイトに割り当てられている後にすぐにリンクが表示されないまた、-にポリシーが割り当てられている**ドキュメントの削除ポリシー**のリンクが表示されたらときから 24 時間がかかることができます。</span><span class="sxs-lookup"><span data-stu-id="afa32-p106">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection. Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="afa32-131">このページでは次のものが確認できます。</span><span class="sxs-lookup"><span data-stu-id="afa32-131">On this page you can view:</span></span>
    
  - <span data-ttu-id="afa32-p107">現在割り当てられているポリシーおよび関連するルール。右側のウィンドウで、ルールを表示するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="afa32-p107">The currently assigned policies and the associated rules. Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="afa32-134">既定のポリシーがある場合、[**既定**] 列に [**はい**] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa32-134">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="afa32-135">ポリシーが [**必須**] として割り当てられている場合は、リストの下にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa32-135">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="afa32-p108">このリストは表示専用であり、サイト コレクションの所有者に、使用可能なすべてのポリシーとルールが表示されます。ポリシーを適用するには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="afa32-p108">This list is view only, for the site collection owner to see all of the available policies and rules. To apply a policy, see the next section.</span></span>
  
![サイト コレクションに割り当てられているドキュメント削除ポリシーの表示](media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="afa32-139">サイトのドキュメント削除ポリシーを適用または削除する</span><span class="sxs-lookup"><span data-stu-id="afa32-139">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="afa32-140">サイト所有者またはサイト コレクション所有者が自分のサイトに適用するか、まったく適用しないかを選択できるポリシーを組織が作成してある場合があります。</span><span class="sxs-lookup"><span data-stu-id="afa32-140">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="afa32-141">右下隅の**設定**ダイアログ ボックスの [歯車アイコン] を選択します\>**サイトの設定**。</span><span class="sxs-lookup"><span data-stu-id="afa32-141">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="afa32-142">**サイトの管理**下にある\>**ドキュメント削除のポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="afa32-142">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="afa32-p109">サイト コレクションにポリシーが割り当てられていない限り、**ドキュメントの削除ポリシー**のリンクは表示されません。ポリシーは、サイトに割り当てられている後にすぐにリンクが表示されないまた、-にポリシーが割り当てられている**ドキュメントの削除ポリシー**のリンクが表示されたらときから 24 時間がかかることができます。</span><span class="sxs-lookup"><span data-stu-id="afa32-p109">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection. Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="afa32-145">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="afa32-145">Do one of the following:</span></span>
    
  - <span data-ttu-id="afa32-146">**ポリシーを適用するには**ポリシーを選択して\>でそのポリシー ルールを選択\>**を保存**します。</span><span class="sxs-lookup"><span data-stu-id="afa32-146">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="afa32-p110">1 つのサイトに一度に有効にできるのは、1 つのポリシーおよび 1 つのルールのみです。組織は複数のポリシーとルールを用意して選択できるようにする場合も、ポリシーやルールを 1 つだけ用意する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="afa32-p110">Only one policy and one rule can be active in a site at one time. Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![ポリシー オプションを選択します。](media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="afa32-150">**ポリシーを無効にする**選択**脱退: 削除に注意してください** \> **を保存**します。</span><span class="sxs-lookup"><span data-stu-id="afa32-150">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="afa32-p111">サイト所有者が、ドキュメント削除ポリシーがサイトのコンテンツに適用可能ではないと判断した場合は、そのポリシーを除外できます。ただし、[**必須**] としてマークされたポリシーは除外できません。</span><span class="sxs-lookup"><span data-stu-id="afa32-p111">As a site owner, you can opt out of a document deletion policy if you determine that the policy is not applicable to the content in your site. However, you cannot opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![Opt Out オプション](media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="afa32-154">ドキュメント削除ポリシーによる、他のポリシーの上書き</span><span class="sxs-lookup"><span data-stu-id="afa32-154">Document deletion policies override other policies</span></span>

<span data-ttu-id="afa32-155">コンテンツの保持と削除のために、サイトでは別のポリシーを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="afa32-155">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="afa32-156">サイト コレクションのコンテンツ タイプ ポリシー。</span><span class="sxs-lookup"><span data-stu-id="afa32-156">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="afa32-157">リストまたはライブラリの情報管理ポリシー。</span><span class="sxs-lookup"><span data-stu-id="afa32-157">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="afa32-p112">ドキュメント削除のポリシーをリストまたはライブラリのコンテンツ タイプのポリシーや情報管理ポリシーを既に使用しているサイトに適用すると、ドキュメントの削除ポリシーが有効なときにこれらのポリシーが無視されます。他のポリシーは無視する場合は、「このサイトのコンテンツは、ドキュメントの削除ポリシーを使用」をメッセージに表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa32-p112">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect. If other policies are ignored, you will see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="afa32-p113">つまり、構造化コンテンツ (情報管理ポリシーとコンテンツ タイプ ポリシー) 用か、非構造化コンテンツ (ドキュメント削除ポリシー) 用のいずれかのポリシーのみを使用するサイトを計画する必要があり、両方を使用することはできません。ドキュメント削除ポリシーを除外した場合、警告は表示されず、他のタイプのポリシーが引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="afa32-p113">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both. If you opt out of a document deletion policy, the warning will not be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="afa32-162">サイト ポリシーはドキュメント削除ポリシーの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="afa32-162">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="afa32-163">コンテンツ タイプ ポリシーが無視されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="afa32-163">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="afa32-p114">サイトを使用していた場合は、コンテンツ タイプのポリシーとしてこのメッセージが表示、これらのポリシーが有効では不要になった。コンテンツ タイプのポリシーを復元するには、前述のとおり、脱退のオプションが利用できる場合、サイトからドキュメントの削除ポリシーを削除できます。選択するオプションがない場合は、ドキュメントのポリシーの削除は必須であり、組織の法令遵守責任者に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afa32-p114">If your site was using content type policies and you now see this message, those policies are no longer in effect. To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available. If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="afa32-167">右下隅の**設定**ダイアログ ボックスの [歯車アイコン] を選択します\>**サイトの設定**。</span><span class="sxs-lookup"><span data-stu-id="afa32-167">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="afa32-168">**サイトの管理**下にある\>**ポリシー テンプレートのコンテンツ タイプ**。</span><span class="sxs-lookup"><span data-stu-id="afa32-168">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![ドキュメントの削除ポリシーが使用されているサイト上の警告](media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="afa32-170">情報管理ポリシーが無視されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="afa32-170">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="afa32-p115">サイトは、情報管理ポリシーを使用するいたし、このメッセージが表示、これらのポリシーは不要になった有効にします。情報管理ポリシーを復元するには、前述のとおり、脱退のオプションが利用できる場合、サイトからドキュメントの削除ポリシーを削除できます。選択するオプションがない場合は、ドキュメントのポリシーの削除は必須であり、組織の法令遵守責任者に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afa32-p115">If your site was using information management policies and you now see this message, those policies are no longer in effect. To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available. If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="afa32-174">リストまたはライブラリで、リボン上の\>[**ライブラリ**] タブ\>**ライブラリの設定** \> [**権限と管理** \> **情報管理ポリシーの設定**。</span><span class="sxs-lookup"><span data-stu-id="afa32-174">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![ドキュメントの削除ポリシーが使用されているサイト上の警告](media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="afa32-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="afa32-176">See also</span></span>

[<span data-ttu-id="afa32-177">ドキュメント削除ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="afa32-177">Overview of document deletion policies</span></span>](document-deletion-policies.md)
  
[<span data-ttu-id="afa32-178">ドキュメント削除ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="afa32-178">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

