---
title: 保持ラベルの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/22/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: Office 365 の保持ラベルは、適切なコンテンツで適切な操作を実行するために役立ちます。保持ラベルを使用すると、ガバナンス用に組織全体のデータを分類し、その分類に基づいて保持ルールを強制できます。保持ラベルは、Office 365 全体のレコード管理の実装に使用することもできます。
ms.openlocfilehash: 444d3ad676514781152ef2eb23f175f94d723e67
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219067"
---
# <a name="overview-of-retention-labels"></a><span data-ttu-id="d7c27-105">保持ラベルの概要</span><span class="sxs-lookup"><span data-stu-id="d7c27-105">Overview of retention labels</span></span>

<span data-ttu-id="d7c27-p102">おそらく、組織全体では、業界の規制や社内のポリシーを遵守するためにさまざまアクションを実行する必要のある、多様な種類のコンテンツがあります。たとえば、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p102">Across your organization, you probably have different types of content that require different actions taken on them in order to comply with industry regulations and internal policies. For example, you might have:</span></span>
  
- <span data-ttu-id="d7c27-108">最小限の期間、**保持する**必要のある税フォーム。</span><span class="sxs-lookup"><span data-stu-id="d7c27-108">Tax forms that need to be **retained** for a minimum period of time.</span></span> 
    
- <span data-ttu-id="d7c27-109">一定の期間に到達した場合、**完全に削除する**必要があるプレス資料。</span><span class="sxs-lookup"><span data-stu-id="d7c27-109">Press materials that need to be **permanently deleted** when they reach a certain age.</span></span> 
    
- <span data-ttu-id="d7c27-110">**保持**と**完全な削除**の両方が必要な競合他社のリサーチ。</span><span class="sxs-lookup"><span data-stu-id="d7c27-110">Competitive research that needs to be both **retained** and then **permanently deleted**.</span></span> 
    
- <span data-ttu-id="d7c27-111">編集も削除もできないように、**レコードとしてマーク**する必要のある就労ビザ。</span><span class="sxs-lookup"><span data-stu-id="d7c27-111">Work visas that must be **marked as a record** so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="d7c27-p103">これらのすべてのケースにおいて、Office 365 の保持ラベルは、適切なコンテンツで適切な操作を実行するために役立ちます。保持ラベルを使用すると、ガバナンス用に組織全体のデータを分類し、その分類に基づいて保持ルールを強制できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p103">In all of these cases, retention labels in Office 365 can help you take the right actions on the right content. With retention labels, you can classify data across your organization for governance, and enforce retention rules based on that classification.</span></span>
  
<span data-ttu-id="d7c27-114">保持ラベルを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-114">With retention labels, you can:</span></span>
  
- <span data-ttu-id="d7c27-p104">Outlook on the web、Outlook 2010 以降、OneDrive、SharePoint、Office 365 グループのコンテンツに、**組織内のユーザーが保持ラベルを手動で適用**できるようにします。多くの場合、コンテンツの種類を最も良く理解しているのはそれを扱っているユーザーです。そこでユーザーにコンテンツを分類し、適切なポリシーを適用してもらいます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p104">**Enable people in your organization to apply a retention label manually** to content in Outlook on the web, Outlook 2010 and later, OneDrive, SharePoint, and Office 365 groups. Users often know best what type of content they're working with, so they can classify it and have the appropriate policy applied.</span></span> 
    
- <span data-ttu-id="d7c27-117">コンテンツに次のものが含まれている場合など、特定の条件に一致するときには、**保持ラベルをコンテンツに自動的に適用**できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-117">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    
  - <span data-ttu-id="d7c27-118">特定の種類の機密情報。</span><span class="sxs-lookup"><span data-stu-id="d7c27-118">Specific types of sensitive information.</span></span>
    
  - <span data-ttu-id="d7c27-119">作成したクエリに一致する特定のキーワード。</span><span class="sxs-lookup"><span data-stu-id="d7c27-119">Specific keywords that match a query you create.</span></span>
    
    <span data-ttu-id="d7c27-120">保持ラベルを自動的にコンテンツに適用する機能が重要である理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d7c27-120">The ability to apply retention labels to content automatically is important because:</span></span>
    
  - <span data-ttu-id="d7c27-121">ユーザーのトレーニングは、一部の分類方法についてのみ必要。</span><span class="sxs-lookup"><span data-stu-id="d7c27-121">You don't need to train your users on all of your classifications.</span></span>
    
  - <span data-ttu-id="d7c27-122">ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="d7c27-122">You don't need to rely on users to classify all content correctly.</span></span>
    
  - <span data-ttu-id="d7c27-123">ユーザーはデータ ガバナンス ポリシーについて把握する必要がなくなり、仕事に集中できる。</span><span class="sxs-lookup"><span data-stu-id="d7c27-123">Users no longer need to know about data governance policies - they can instead focus on their work.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d7c27-p105">ラベルを自動的に適用する機能では、サイトまたはメールボックスで自動的にラベルが付けられたコンテンツを編集するアクセス許可を持つユーザーごとに Office 365 Enterprise E5 ライセンスが必要になります。読み取り専用アクセス許可だけを持つユーザーにはライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p105">The capability to apply labels automatically requires an Office 365 Enterprise E5 license for each user who has permissions to edit content that's been automatically labeled in a site or mailbox. Users who simply have read-only access do not require a license.</span></span>
      
- <span data-ttu-id="d7c27-126">SharePoint と Office 365 グループのサイトの **ドキュメント ライブラリに既定の保持ラベルを適用**することにより、それらのライブラリ内のすべてのドキュメントに既定の保持ラベルを適用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-126">**Apply a default retention label to a document library** in SharePoint and Office 365 group sites, so that all documents in that library get the default retention label.</span></span> 
    
- <span data-ttu-id="d7c27-p106">メールとドキュメントの両方を含む、**Office 365 全体でレコード管理を実装**できます。保持ラベルを使用して、コンテンツをレコードとして分類できます。この場合、ラベルの変更と削除、およびコンテンツの編集と削除はできません。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p106">**Implement records management across Office 365**, including both email and documents. You can use a retention label to classify content as a record. When this happens, the label can't be changed or removed, and the content can't be edited or deleted.</span></span> 
    
<span data-ttu-id="d7c27-130">保持ラベルは、Office 365 セキュリティ/コンプライアンス センターの **[ラベル]** ページにある **[保持]** タブで作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="d7c27-130">You create and manage retention labels on the **Retention** tab on the **Labels** page in the Office 365 Security &amp; Compliance Center.</span></span> 
  
![[ラベル] ページの [保持] タブ](media/Retention_tab_on_Labels_page.png)
 
## <a name="how-retention-labels-work-with-label-policies"></a><span data-ttu-id="d7c27-132">ラベル ポリシーでの保持ラベルのしくみ</span><span class="sxs-lookup"><span data-stu-id="d7c27-132">How retention labels work with label policies</span></span>

<span data-ttu-id="d7c27-p107">2 段階のプロセスを実行することにより、組織内のユーザーが保持ラベルを使用してコンテンツを分類できるようになります。まず、ラベルを作成し、次に選択した場所にそのラベルを発行します。保持ラベルを発行すると、ラベル ポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p107">Making retention labels available to people in your organization so that they can classify content is a two-step process: first you create the labels, and then you publish them to the locations you choose. When you publish retention labels, a label policy gets created.</span></span>
  
![ラベルの役割とタスクの図](media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)
  
<span data-ttu-id="d7c27-p108">保持ラベルは独立した再利用可能な文書パーツであり、ラベル ポリシーに含まれ、さまざまな場所に発行されます。保持ラベルは多くのポリシー間で再利用できます。ラベル ポリシーの主な目的は、保持ラベルのセットをグループ化し、それらのラベルを表示する場所を指定することです。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p108">Retention labels are independent, reusable building blocks that are included in a label policy and published to different locations. Retention labels can be reused across many policies. The primary purpose of the label policy is to group a set of retention labels and specify the locations where you want those labels to appear.</span></span>
  
![ラベル、ラベル ポリシー、および場所の図](media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. <span data-ttu-id="d7c27-p109">保持ラベルを発行すると、それらはラベル ポリシーに含まれます。単一の保持ラベルは複数のポリシーに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p109">When you publish retention labels, they're included in a label policy. A single retention label can be included in many policies.</span></span>
    
2. <span data-ttu-id="d7c27-142">ラベル ポリシーは保持ラベルを発行する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="d7c27-142">Label policies specify the locations to publish the retention labels.</span></span>
    
## <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="d7c27-143">一度に 1 つの保持ラベルのみ</span><span class="sxs-lookup"><span data-stu-id="d7c27-143">Only one retention label at a time</span></span>

<span data-ttu-id="d7c27-144">メールやドキュメントなどのコンテンツに一度に割り当てられる保持ラベルは 1 つのみです。これを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="d7c27-144">It's important to know that content like an email or document can have only a single retention label assigned to it at a time:</span></span>
  
- <span data-ttu-id="d7c27-145">エンド ユーザーが手動で割り当てた保持ラベルの場合、ユーザーは割り当てられたラベルを削除または変更できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-145">For labels assigned manually by end users, people can remove or change the retention label that's assigned.</span></span>
    
- <span data-ttu-id="d7c27-146">コンテンツに自動適用ラベルが割り当てられている場合は、自動適用ラベルをエンド ユーザーが手動で割り当てた保持ラベルに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-146">If content has an auto-apply label assigned, an auto-apply label can be replaced by a retention label assigned manually by an end user.</span></span>
    
- <span data-ttu-id="d7c27-147">コンテンツにエンド ユーザーが手動で割り当てた保持ラベルがある場合は、自動適用ラベルと手動で割り当てられた保持ラベルを置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="d7c27-147">If content has a retention label assigned manually by an end user, an auto-apply label cannot replace the manually assigned retention label.</span></span>
    
- <span data-ttu-id="d7c27-148">自動適用ラベルを割り当てるルールが複数あり、コンテンツが複数のルールの条件を満たしている場合、最も古いルールの保持ラベルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-148">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the retention label for the oldest rule is assigned.</span></span>
    
<span data-ttu-id="d7c27-p110">手動で割り当てたラベルは明示的に割り当てられ、自動適用のラベルは暗黙的に割り当てられます。明示的な保持ラベルは暗黙的なラベルよりも優先されます。詳細については、後続の「[保持の原則、すなわち優先順位について](labels.md#principles)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p110">Manually assigned labels are explicitly assigned; auto-apply labels are implicitly assigned; an explicit retention label takes precedence over an implicit label. For more information, see the below section on [The principles of retention, or what takes precedence?](labels.md#principles).</span></span>

<span data-ttu-id="d7c27-p111">このセクションのすべての情報は、保持ラベルにのみ適用されます。コンテンツのアイテムには、1 つの保持ラベルの他に 1 つの機密ラベルを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p111">All of the information in this section applies only to retention labels. Note that an item of content can also have one sensitivity label applied to it, in addition to one retention label.</span></span>
  
## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="d7c27-153">保持ラベルが有効になるまでの所要時間</span><span class="sxs-lookup"><span data-stu-id="d7c27-153">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="d7c27-154">保持ラベルを発行または自動適用しても、すぐには有効になりません。</span><span class="sxs-lookup"><span data-stu-id="d7c27-154">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="d7c27-155">まず、ラベル ポリシーをセキュリティ/コンプライアンス センターからポリシー内の場所に同期させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-155">First the label policy needs to be synced from the Security &amp; Compliance Center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="d7c27-p112">その後、エンド ユーザーが手動ラベルを利用できるようにする、またはラベルをコンテンツに自動適用するには、時間がかかることがあります。この所要時間はラベルの場所と種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p112">Then the location may require time to make manual labels available to end users or auto-apply labels to content. How long this takes depends on the location and type of label.</span></span>
    
### <a name="manual-retention-labels"></a><span data-ttu-id="d7c27-158">手動の保持ラベル</span><span class="sxs-lookup"><span data-stu-id="d7c27-158">Manual retention labels</span></span>

<span data-ttu-id="d7c27-p113">SharePoint または OneDrive に保持ラベルを発行する場合、保持ラベルがエンド ユーザーに表示されるまでに 1 日かかる場合があります。また、Exchange に保持ラベルを発行する場合は、保持ラベルがエンド ユーザーに表示するまでに 7 日間かかる場合があり、さらにメールボックスには少なくとも 10 MB のデータが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p113">If you publish retention labels to SharePoint or OneDrive, it can take one day for those retention labels to appear for end users. In addition, if you publish retention labels to Exchange, it can take 7 days for those retention labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.</span></span>
  
![手動ラベルが有効になるタイミングの図](media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="d7c27-162">自動適用の保持ラベル</span><span class="sxs-lookup"><span data-stu-id="d7c27-162">Auto-apply retention labels</span></span>

<span data-ttu-id="d7c27-163">特定の条件に一致するコンテンツに保持ラベルを自動適用する場合、ラベルが条件に一致するすべてのコンテンツに保持ラベルが適用されるまでに 7 日間かかります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-163">If you auto-apply retention labels to content matching specific conditions, it can take seven days for the retention labels to be applied to all content that matches the conditions.</span></span>
  
![自動適用ラベルが有効になるタイミングの図](media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-exchange-labels"></a><span data-ttu-id="d7c27-165">Exchange ラベルの状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="d7c27-165">How to check on the status of Exchange labels</span></span>

<span data-ttu-id="d7c27-p114">Exchange Online では、7 日ごとに実行されるプロセスによってエンド ユーザーが保持ラベルを利用できるようになります。Powershell を使用することで、このプロセスが最後に実行された日時を確認できるため、次に実行される日時を判断できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p114">In Exchange Online, retention labels are made available to end users by a process that runs every seven days. By using Powershell, you can see when this process last ran and thus determine when it will run again.</span></span>
  
1. <span data-ttu-id="d7c27-168">[Exchange Online PowerShell に接続します](https://go.microsoft.com/fwlink/?linkid=799773)。</span><span class="sxs-lookup"><span data-stu-id="d7c27-168">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="d7c27-169">これらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d7c27-169">Run these commands.</span></span>
    
  ```
  $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
  ```

  ```
  $xmlprops = [xml]($logProps.MailboxLog)
  ```

  ```
  $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
  ```

<span data-ttu-id="d7c27-p115">結果では、`ELCLastSuccessTimeStamp` (UTC) プロパティは、システムがメールボックスを最後に処理した日時を示します。ポリシーの作成時点からこの処理が発生していない場合、ラベルは表示されません。処理を強制するには、`Start-ManagedFolderAssistant -Identity <user>` を実行します。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p115">In the results, the  `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox. If it has not happened since the time you created the policy, the labels are not going to appear. To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="d7c27-173">Outlook on the web にラベルが表示されると思われるにもかかわらず、ラベルが表示されない場合は、ブラウザーのキャッシュを必ず消去してください (CTRL + F5)。</span><span class="sxs-lookup"><span data-stu-id="d7c27-173">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    
## <a name="label-policies-and-locations"></a><span data-ttu-id="d7c27-174">ラベルのポリシーと場所</span><span class="sxs-lookup"><span data-stu-id="d7c27-174">Label policies and locations</span></span>

<span data-ttu-id="d7c27-175">保持ラベルの内容に応じて、多様な種類の保持ラベルをさまざまな場所に発行できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-175">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
|<span data-ttu-id="d7c27-176">**保持ラベルの種類**</span><span class="sxs-lookup"><span data-stu-id="d7c27-176">**If the retention label is…**</span></span>|<span data-ttu-id="d7c27-177">**ラベル ポリシーの適用先**</span><span class="sxs-lookup"><span data-stu-id="d7c27-177">**Then the label policy can be applied to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d7c27-178">エンド ユーザーに発行されたラベル</span><span class="sxs-lookup"><span data-stu-id="d7c27-178">Published to end users</span></span>  <br/> |<span data-ttu-id="d7c27-179">Exchange、SharePoint、OneDrive、Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="d7c27-179">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
|<span data-ttu-id="d7c27-180">機密情報の種類に基づいて自動適用されたラベル</span><span class="sxs-lookup"><span data-stu-id="d7c27-180">Auto-applied based on sensitive information types</span></span>  <br/> |<span data-ttu-id="d7c27-181">Exchange (すべてのメールボックスのみ)、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="d7c27-181">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="d7c27-182">クエリに基づいて自動適用されたラベル</span><span class="sxs-lookup"><span data-stu-id="d7c27-182">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="d7c27-183">Exchange、SharePoint、OneDrive、Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="d7c27-183">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
   
<span data-ttu-id="d7c27-p116">Exchange では、自動適用の保持ラベル (情報の種類はクエリと機密の両方) は、新しく送信されたメッセージ (送信中のデータ) にのみ適用され、現在メールボックスにあるすべてのアイテム (保存データ) には適用されません。また、機密情報の種類向けの自動適用の保持ラベルは、すべてのメールボックスにのみ適用できます。ただし、特定のメールボックスを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p116">Note that in Exchange, auto-apply retention labels (for both queries and sensitive information types) are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest). Also, auto-apply retention labels for sensitive information types can apply only to all mailboxes; you can't select the specific mailboxes.</span></span>
  
<span data-ttu-id="d7c27-186">Exchange パブリック フォルダーと Skype ではラベルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d7c27-186">Note that Exchange public folders and Skype do not support labels.</span></span>
  
## <a name="how-retention-labels-enforce-retention"></a><span data-ttu-id="d7c27-187">保持ラベルによる強制保持のしくみ</span><span class="sxs-lookup"><span data-stu-id="d7c27-187">How retention labels enforce retention</span></span>

<span data-ttu-id="d7c27-p117">保持ラベルは、アイテム保持ポリシーが強制できる保持アクションとまったく同じ保持アクションを強制することができます。保持ラベルを使用すると、高度なコンテンツ プラン (またはファイル プラン) を実装できます。保持のしくみに関する詳細については、「[アイテム保持ポリシーの概要](retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p117">Retention labels can enforce exactly the same retention actions that a retention policy can. You can use retention labels to implement a sophisticated content plan (or file plan). For more information on how retention works, see [Overview of retention policies](retention-policies.md).</span></span>
  
<span data-ttu-id="d7c27-p118">さらに、保持ラベルには 2 つの保持オプションがあります。これらのオプションは保持ラベルでのみ使用でき、アイテム保持ポリシーでは使用できません。保持ラベルを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p118">In addition, a retention label has two retention options that are available only in a retention label and not in a retention policy. With a retention label, you can:</span></span>
  
- <span data-ttu-id="d7c27-p119">保持期間の終了時に廃棄レビューをトリガーし、SharePoint と OneDrive のドキュメントを確認してから削除するようにできます。詳細については、「[廃棄レビューの概要](disposition-reviews.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p119">Trigger a disposition review at the end of the retention period, so that SharePoint and OneDrive documents must be reviewed before they can be deleted. For more information, see [Overview of disposition reviews](disposition-reviews.md).</span></span>
    
- <span data-ttu-id="d7c27-195">コンテンツの作成日または最終変更日時ではなく、コンテンツがラベル付けされた時点から保持期間を開始できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-195">Start the retention period from when the content was labeled, instead of the age of the content or when it was last modified.</span></span>
    
![ラベル固有のオプションによる保持設定](media/c49118c9-6279-4661-94db-deffa76e27ac.png)
  
## <a name="where-published-retention-labels-can-appear-to-end-users"></a><span data-ttu-id="d7c27-197">発行済みラベルをエンド ユーザー向けに表示できる場所</span><span class="sxs-lookup"><span data-stu-id="d7c27-197">Where published retention labels can appear to end users</span></span>

<span data-ttu-id="d7c27-198">保持ラベルがエンド ユーザーによってコンテンツに割り当てられる場合、保持ラベルは次の場所に発行できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-198">If your retention label will be assigned to content by end users, you can publish it to:</span></span>
  
- <span data-ttu-id="d7c27-199">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="d7c27-199">Outlook on the web</span></span>
    
- <span data-ttu-id="d7c27-200">Outlook 2010 以降</span><span class="sxs-lookup"><span data-stu-id="d7c27-200">Outlook 2010 and later</span></span>
    
- <span data-ttu-id="d7c27-201">OneDrive</span><span class="sxs-lookup"><span data-stu-id="d7c27-201">OneDrive</span></span>
    
- <span data-ttu-id="d7c27-202">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d7c27-202">SharePoint</span></span>
    
- <span data-ttu-id="d7c27-203">Office 365 グループ (Outlook on the web のグループ サイトとグループ メールボックスの両方)</span><span class="sxs-lookup"><span data-stu-id="d7c27-203">Office 365 groups (both the group site and group mailbox in Outlook on the web)</span></span>
    
<span data-ttu-id="d7c27-204">以下のセクションでは、さまざまなアプリで組織内のユーザーに対してラベルがどのように表示されるかを説明します。</span><span class="sxs-lookup"><span data-stu-id="d7c27-204">The sections below show how labels will appear in different apps to people in your organization.</span></span>
  
### <a name="outlook-on-the-web"></a><span data-ttu-id="d7c27-205">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="d7c27-205">Outlook on the web</span></span>

<span data-ttu-id="d7c27-206">Outlook on the web でアイテムにラベルを付けるには、アイテム \>**[ポリシーの割り当て]**\> の順に右クリックして、保持ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d7c27-206">To label an item in Outlook on the web, right-click the item \> **Assign policy** \> choose the retention label.</span></span> 
  
![Outlook on the web の [ポリシーの割り当て] メニュー](media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
<span data-ttu-id="d7c27-p120">保持ラベルが適用されると、アイテムの上部にその保持ラベルとラベルが実行するアクションが表示されます。メールが分類され、保持期間が関連付けられている場合、メールの有効期限が一目でわかります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p120">After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.</span></span>
  
![メールに割り当てられたラベル (Outlook on the web)](media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
<span data-ttu-id="d7c27-211">保持ラベルはフォルダーに適用することもできます。その場合は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-211">You can also apply retention labels to folders, in which case:</span></span>
  
- <span data-ttu-id="d7c27-p121">明示的に保持ラベルが適用されているアイテムを**除き**、フォルダー内のすべてのアイテムに同じ保持ラベルが自動的に設定されます。明示的にラベル付けされたアイテムは、既存の保持ラベルを維持します。詳細については、保持の原則に関する後続のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p121">All items in the folder automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them. Explicitly labeled items keep their existing retention label. For more information, see the below section on the principles of retention.</span></span> 
    
- <span data-ttu-id="d7c27-215">フォルダーの既定の保持ラベルを変更または削除すると、明示的な保持ラベルを持つアイテムを**除き**、フォルダー内にあるすべてのアイテムの保持ラベルも変更または削除されます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-215">If you change or remove the default retention label for a folder, the retention label's also changed or removed for all items in the folder, **except** items with explicit retention labels.</span></span> 
    
- <span data-ttu-id="d7c27-216">既定の保持ラベルを持つアイテムをあるフォルダーから異なる既定の保持ラベルを持つ別のフォルダーに移動すると、そのアイテムには新しい既定の保持ラベルが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-216">If you move an item with a default retention label from one folder to another folder with a different default retention label, the item will get the new default retention label.</span></span>
    
- <span data-ttu-id="d7c27-217">既定の保持ラベルを持つアイテムをあるフォルダーから既定の保持ラベルがない別のフォルダーに移動すると、以前の既定の保持ラベルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-217">If you move an item with a default retention label from one folder to another folder with no default retention label, the old default retention label is removed.</span></span>
    
### <a name="outlook-2010-and-later"></a><span data-ttu-id="d7c27-218">Outlook 2010 以降</span><span class="sxs-lookup"><span data-stu-id="d7c27-218">Outlook 2010 and later</span></span>

<span data-ttu-id="d7c27-219">Outlook on the web でアイテムにラベルを付けるには、アイテム\>**[リボン]**\>**[ポリシーの割り当て]**\> の順に右クリックして、保持ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d7c27-219">To label an item in Outlook on the web, right-click the item \> on the **Ribbon** \> **Assign Policy** \> choose the retention label.</span></span> 
  
![[ポリシーの割り当て] ボタン](media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
<span data-ttu-id="d7c27-p122">保持ラベルが適用されると、アイテムの上部にその保持ラベルとラベルが実行するアクションが表示されます。メールが分類され、保持期間が関連付けられている場合、メールの有効期限が一目でわかります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p122">After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.</span></span>
  
<span data-ttu-id="d7c27-p123">フォルダーに保持ラベルを適用することもできます。これは、Outlook on the web での機能と同様に Outlook 2010 以降でも機能します。詳細については、前出のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p123">You can also apply retention labels to folders. This works the same in Outlook 2010 and later as it does in Outlook on the web -- see the previous section for more info.</span></span>
  
### <a name="onedrive-and-sharepoint"></a><span data-ttu-id="d7c27-225">OneDrive と SharePoint</span><span class="sxs-lookup"><span data-stu-id="d7c27-225">OneDrive and SharePoint</span></span>

<span data-ttu-id="d7c27-226">OneDrive または SharePoint でドキュメント (OneNote ファイルを含む) にラベルを付けるには、アイテム \> 右上隅にある **[詳細ウィンドウを開く]**![情報ウィンドウ アイコン](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png)\>**[ラベルの適用]**\> の順に選択し、保持ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d7c27-226">To label a document (including OneNote files) in OneDrive or SharePoint, select the item \> in the upper-right corner, choose **Open the details pane**![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Apply label** \> choose the retention label.</span></span> 
  
<span data-ttu-id="d7c27-227">フォルダーまたはドキュメントのセットに保持ラベルを適用することもできます。また、ドキュメント ライブラリに対して既定の保持ラベルを設定できます。詳細については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-227">Note that you can also apply a retention label to a folder or document set, and you can set a default retention label for a document library - see the section below for more information.</span></span>
  
![SharePoint のアイテムに対するラベル リストの適用](media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
<span data-ttu-id="d7c27-229">アイテムに保持ラベルが適用されると、そのアイテムの選択時に、詳細ウィンドウにラベルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-229">After a retention label is applied to an item, you can view it in the details pane when that item's selected.</span></span>
  
![詳細ウィンドウに表示される適用されたラベル](media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
<span data-ttu-id="d7c27-p124">**[ラベル]** 列または **[アイテムがレコード]** 列を含むライブラリのビューを作成して、すべてのアイテムに割り当てられた保持ラベルとレコードであるアイテムを一目で確認できるようにすることも可能です。ただし、**[アイテムがレコード]** 列を使用してビューをフィルターすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p124">You can also create a view of the library that contains the **Labels** column or **Item is a Record** column, so that you can see at a glance the retention labels assigned to all items and which items are records. Note, however, that you can't filter the view by the **Item is a Record** column.</span></span> 
  
![カスタム ビューで表示されるラベルのライブラリの列](media/e3392627-c0a3-405e-bb57-55f27c34cfdd.png)
  
### <a name="office-365-groups"></a><span data-ttu-id="d7c27-234">Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="d7c27-234">Office 365 groups</span></span>

<span data-ttu-id="d7c27-p125">Office 365 グループに保持ラベルを発行すると、保持ラベルは Outlook on the web のグループ サイトとグループ メールボックスの両方に表示されます。コンテンツに保持ラベルを適用する場合のエクスペリエンスは、上記のメールとドキュメントの場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p125">When you publish retention labels to an Office 365 group, the retention labels appear in both the group site and group mailbox in Outlook on the web. The experience of applying a retention label to content is identical to that shown above for email and documents.</span></span>

<span data-ttu-id="d7c27-p126">Office 365 グループのコンテンツを保持するには、Office 365 グループの場所を使用する必要があります。Office 365 グループには Exchange メールボックスがありますが、Exchange の場所全体が含まれるアイテム保持ポリシーには、Office 365 グループのメールボックスのコンテンツは含まれません。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p126">To retain content for an Office 365 group, you need to use the Office 365 groups location. Even though an Office 365 group has an Exchange mailbox, a retention policy that includes the entire Exchange location won't include content in Office 365 group mailboxes.</span></span>

<span data-ttu-id="d7c27-p127">また、Exchange の場所を使用して、特定のグループのメールボックスを含めたり除外したりすることはできません。最初は Exchange の場所でグループのメールボックスを選択できますが、アイテム保持ポリシーを保存しようとすると、Exchange の場所では "RemoteGroupMailbox" を選択できないことを示すエラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p127">In addition, it's not possible to use the Exchange location to include or exclude a specific group mailbox. Although the Exchange location initially allows a group mailbox to be selected, when you try to save the retention policy, you'll receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>
  
## <a name="applying-a-retention-label-automatically-based-on-conditions"></a><span data-ttu-id="d7c27-241">条件に基づいた保持ラベルの自動適用</span><span class="sxs-lookup"><span data-stu-id="d7c27-241">Applying a retention label automatically based on conditions</span></span>

<span data-ttu-id="d7c27-p128">保持ラベルの最も強力な機能の 1 つは、特定の条件に一致したコンテンツにラベルを自動的に適用する機能です。この場合、保持ラベルは Office 365 によって適用されるため、組織内のユーザーがラベルを適用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p128">One of the most powerful features of retention labels is the ability to apply them automatically to content that matches certain conditions. In this case, people in your organization don't need to apply the retention labels - Office 365 does the work for them.</span></span>
  
![自動適用ラベルの役割とタスクの図](media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)
  
<span data-ttu-id="d7c27-245">自動適用の保持ラベルが強力な機能である理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d7c27-245">Auto-apply retention labels are powerful because:</span></span>
  
- <span data-ttu-id="d7c27-246">ユーザーのトレーニングは、一部の分類方法についてのみ必要。</span><span class="sxs-lookup"><span data-stu-id="d7c27-246">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="d7c27-247">ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="d7c27-247">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="d7c27-248">ユーザーはデータ ガバナンス ポリシーについて把握する必要がなくなるので、仕事に集中できる。</span><span class="sxs-lookup"><span data-stu-id="d7c27-248">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="d7c27-249">コンテンツに次の内容が含まれている場合は、保持ラベルを自動的にコンテンツに適用するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-249">You can choose to apply retention labels to content automatically when that content contains:</span></span>
  
- <span data-ttu-id="d7c27-250">特定の種類の機密情報。</span><span class="sxs-lookup"><span data-stu-id="d7c27-250">Specific types of sensitive information.</span></span>
    
- <span data-ttu-id="d7c27-251">作成したクエリに一致する特定のキーワード。</span><span class="sxs-lookup"><span data-stu-id="d7c27-251">Specific keywords that match a query you create.</span></span>
    
![自動適用ラベルの [条件選択] ページ](media/c0b7a3ef-bda0-494c-941d-f1f93753ecdd.png)
  
<span data-ttu-id="d7c27-253">自動適用の保持ラベルには Office 365 Enterprise E5 サブスクリプションが必要であす。また、前述したように、条件に一致するすべてのコンテンツに自動適用の保持ラベルが適用されるまでに最大 7 日間かかります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-253">Note that auto-apply retention labels require an Office 365 Enterprise E5 subscription, and that it can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions, as described above.</span></span>
  
### <a name="auto-apply-retention-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="d7c27-254">特定の種類の機密情報によるコンテンツへの保持ラベルの自動適用</span><span class="sxs-lookup"><span data-stu-id="d7c27-254">Auto-apply retention labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="d7c27-p129">機密情報の自動適用の保持ラベルを作成すると、データ損失防止 (DLP) ポリシーを作成する場合と同じポリシー テンプレートの一覧が表示されます。各ポリシーテンプレートは、特定の種類の機密情報を検索するように事前設定されています。たとえば、ここに表示されているテンプレートでは、米国の ITIN、SSN、およびパスポート番号が検索されます。DLP の詳細については、「[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p129">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy. Each policy template is preconfigured to look for specific types of sensitive information - for example, the template shown here looks for U.S. ITIN, SSN, and passport numbers. To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![機密情報の種類によるポリシー テンプレート](media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="d7c27-p130">ポリシー テンプレートを選択すると、すべての種類の機密情報を追加または削除したり、インスタンス数と一致精度を変更したりできます。ここに示す例では、保持ラベルは次の場合にのみ自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p130">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="d7c27-p131">コンテンツに、次の 3 種類の機密情報のいずれかに 1 から 9 個のインスタンスが含まれる場合。**最大** 値を削除して、**任意** の値に変更できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p131">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="d7c27-p132">検出された機密情報の種類は、一致精度 (または信頼レベル) が少なくとも 75 に設定されています。多くの機密情報の種類は複数のパターンで定義されています。一致精度の高いパターンでは、より多くの証拠 (キーワード、日付、アドレスなど) が検索される必要がありますが、一致精度の低いパターンでは必要な証拠は少なくなります。簡単に言えば、一致精度の **最小** 値が低いほど、コンテンツは条件に一致しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p132">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="d7c27-266">これらのオプションの詳細については、「[一致の難易度を設定するためのルールの調整](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-266">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![機密情報の種類を識別するためのオプション](media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="d7c27-268">キーワードまたは検索可能なプロパティによるコンテンツへの自動適用ラベル</span><span class="sxs-lookup"><span data-stu-id="d7c27-268">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="d7c27-p133">特定の条件を満たすコンテンツにラベルを自動的に適用できます。現在利用可能な条件では、特定の単語、フレーズ、または検索可能なプロパティの値を含むコンテンツへのラベルの適用がサポートされています。AND、OR、NOT などの検索演算子を使用してクエリを絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p133">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="d7c27-272">クエリ構文の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-272">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="d7c27-273">キーワード クエリ言語 (KQL) 構文のリファレンス</span><span class="sxs-lookup"><span data-stu-id="d7c27-273">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/ja-JP/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="d7c27-p134">クエリ ベースのラベルは検索インデックスを使用してコンテンツを特定します。有効な検索可能なプロパティの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p134">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="d7c27-276">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="d7c27-276">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="d7c27-277">クロールされたプロパティと管理プロパティの概要 (SharePoint Server)</span><span class="sxs-lookup"><span data-stu-id="d7c27-277">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/ja-JP/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="d7c27-278">クエリの例:</span><span class="sxs-lookup"><span data-stu-id="d7c27-278">Examples queries:</span></span>

- <span data-ttu-id="d7c27-279">Exchange</span><span class="sxs-lookup"><span data-stu-id="d7c27-279">Exchange</span></span>
    - <span data-ttu-id="d7c27-280">subject:"Quarterly Financials"</span><span class="sxs-lookup"><span data-stu-id="d7c27-280">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="d7c27-281">recipients:garthf<!--nolink-->@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d7c27-281">recipients:garthf<!--nolink-->@contoso.com</span></span>
- <span data-ttu-id="d7c27-282">SharePoint および OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d7c27-282">SharePoint and OneDrive for Business</span></span>
    - <span data-ttu-id="d7c27-283">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="d7c27-283">contenttype:contract</span></span>
    - <span data-ttu-id="d7c27-284">site:https<!--nolink-->://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="d7c27-284">site:https<!--nolink-->://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![クエリ エディター](media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)

## <a name="applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set"></a><span data-ttu-id="d7c27-286">SharePoint ライブラリ、フォルダー、またはドキュメント セット内のすべてのコンテンツへの既定の保持ラベルの適用</span><span class="sxs-lookup"><span data-stu-id="d7c27-286">Applying a default retention label to all content in a SharePoint library, folder, or document set</span></span>

<span data-ttu-id="d7c27-287">個々のドキュメントにユーザーが保持ラベルを適用できるようにするだけでなく、既定の保持ラベルを SharePoint ライブラリ、フォルダー、またはドキュメント セットに適用して、その場所にあるすべてのドキュメントに既定の保持ラベルを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-287">In addition to enabling people to apply a retention label to individual documents, you can also apply a default retention label to a SharePoint library, folder, or document set, so that all documents in that location get the default retention label.</span></span>
  
<span data-ttu-id="d7c27-p135">ドキュメント ライブラリの場合、これはドキュメント ライブラリの **[ライブラリの設定]** ページで実行できます。既定の保持ラベルを選択すると、ライブラリにある任意の既存のアイテムに対して適用するように選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p135">For a document library, this is done on the **Library settings** page for a document library. When you choose the default retention label, you can also choose to apply it to any existing items in the library.</span></span> 
  
<span data-ttu-id="d7c27-290">たとえば、マーケティング資料用のタグがあり、特定のドキュメント ライブラリにその種類のコンテンツだけが含まれていることがわかっている場合は、[マーケティング資料] タグをそのライブラリ内にあるすべてのドキュメントの既定にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-290">For example, if you have a tag for marketing materials, and you know a specific document library will contain only that type of content, you can make the Marketing Materials tag the default for all documents in that library.</span></span>
  
![ライブラリの設定ページでのラベル オプションの適用](media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
<span data-ttu-id="d7c27-292">ライブラリ、フォルダー、またはドキュメント セット内にある既存のアイテムに既定の保持ラベルを適用すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-292">If you apply a default retention label to existing items in the library, folder, or document set:</span></span>
  
- <span data-ttu-id="d7c27-p136">明示的にラベルが適用されているアイテムを**除き**、ライブラリ、フォルダー、またはドキュメント セット内にあるすべてのアイテムに同じ保持ラベルが自動的に設定されます。明示的に保持ラベルが付けられたアイテムは、既存のラベルを維持します。詳細については、以下の「[保持の原則、すなわち優先順位について](#the-principles-of-retention-or-what-takes-precedence)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p136">All items in the library, folder, or document set automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them. Explicitly labeled items keep their existing label. For more information, see the below section on [The principles of retention, or what takes precedence?](#the-principles-of-retention-or-what-takes-precedence).</span></span>
    
- <span data-ttu-id="d7c27-296">ライブラリ、フォルダー、またはドキュメント セットの既定の保持ラベルを変更または削除すると、明示的な保持ラベルを持つアイテムを**除き**、ライブラリ、フォルダー、またはドキュメント セット内にあるすべてのアイテムの保持ラベルも変更または削除されます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-296">If you change or remove the default retention label for a library, folder, or document set, the retention label's also changed or removed for all items in the library, folder, or document set, **except** items with explicit retention labels.</span></span> 
    
- <span data-ttu-id="d7c27-297">既定の保持ラベルを持つアイテムをあるライブラリ、フォルダー、またはドキュメント セットから別のライブラリ、フォルダー、またはドキュメント セットに移動すると、新しい場所に別の既定の保持ラベルが設定されていても、アイテムは既存の既定の保持ラベルを維持します。</span><span class="sxs-lookup"><span data-stu-id="d7c27-297">If you move an item with a default retention label from one library, folder, or document set to another library, folder, or document set, the item keeps its existing default retention label, even if the new location has a different default retention label.</span></span>
    
## <a name="applying-a-retention-label-to-email-by-using-rules"></a><span data-ttu-id="d7c27-298">ルールを使用したメールへの保持ラベルの適用</span><span class="sxs-lookup"><span data-stu-id="d7c27-298">Applying a retention label to email by using rules</span></span>

<span data-ttu-id="d7c27-299">Outlook 2010 以降では、保持ラベルまたはアイテム保持ポリシーを適用するためのルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-299">In Outlook 2010 or later, you can create rules to apply a retention label or retention policy.</span></span>
  
<span data-ttu-id="d7c27-300">たとえば、特定の配布グループとの間で送受信されるすべてのメッセージに対して特定の保持ラベルを適用するルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-300">For example, you can create a rule that applies a specific retention label to all messages sent to or from a specific distribution group.</span></span>
  
<span data-ttu-id="d7c27-301">ルールを作成するには、アイテム \>**[ルール]**\>**[ルールの作成]**\>**[高度なオプション]**\>**[ルール ウィザード]**\>**[アイテム保持ポリシーの適用]** の順に右クリックします。</span><span class="sxs-lookup"><span data-stu-id="d7c27-301">To create a rule, right-click an item \> **Rules** \> **Create Rule** \> **Advanced Options** \> **Rules Wizard** \> **apply retention policy**.</span></span>
  
![アイテム保持ポリシーを適用するオプションを含むルール ウィザード](media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  
## <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="d7c27-303">アクションを適用しないコンテンツの分類</span><span class="sxs-lookup"><span data-stu-id="d7c27-303">Classifying content without applying any actions</span></span>

<span data-ttu-id="d7c27-p137">保持ラベルを作成する場合、以下に示すように、保持やその他の操作を有効にすることなくラベルを作成できます。この場合、アクションを強制せずに、保持ラベルを単にテキスト ラベルとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p137">When you create a retention label, you can do so without turning on any retention or other actions, as shown below. In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="d7c27-306">たとえば、アクションを適用せずに「後で確認」という名前の保持ラベルを作成して、機密情報の種類を持つコンテンツまたはクエリの対象となるコンテンツにその保持ラベルを自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-306">For example, you can create a retention label named "Review later" with no actions, and then auto-apply that retention label to content with sensitive information types or queried content.</span></span>
  
![保持がオフになっているラベルの設定ページ](media/17ce863b-a823-426e-aaad-83718465f762.png)
  
## <a name="using-retention-labels-for-records-management"></a><span data-ttu-id="d7c27-308">レコード管理用の保持ラベルの使用</span><span class="sxs-lookup"><span data-stu-id="d7c27-308">Using retention labels for records management</span></span>

<span data-ttu-id="d7c27-309">概ね、レコード管理とは次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d7c27-309">At a high level, records management means that:</span></span>
  
- <span data-ttu-id="d7c27-310">ユーザーによって重要なコンテンツがレコードとして分類されている。</span><span class="sxs-lookup"><span data-stu-id="d7c27-310">Important content is classified as a record by users.</span></span>
    
- <span data-ttu-id="d7c27-311">レコードは変更も削除もできない。</span><span class="sxs-lookup"><span data-stu-id="d7c27-311">A record can't be modified or deleted.</span></span>
    
- <span data-ttu-id="d7c27-312">レコードは指定された有効期限が過ぎた後、最終的に破棄される。</span><span class="sxs-lookup"><span data-stu-id="d7c27-312">Records are finally disposed of after their stated lifetime is past.</span></span>
    
<span data-ttu-id="d7c27-p138">保持ラベルを使用して Office 365 全体にわたって一貫したレコード管理戦略を実装できます。一方、レコード センターなどの他のレコード管理機能は SharePoint コンテンツにのみ適用されます。また、レコードの保持アクションを強制して、ライフサイクルの終了時にレコードを自動的に破棄することができます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p138">You can use retention labels to implement a single, consistent records-management strategy across Office 365, whereas other records-management features such as the Record Center apply only to SharePoint content. And you can enforce retention actions on records, so that they're disposed of automatically at the end of their lifecycle.</span></span>
  
<span data-ttu-id="d7c27-315">保持ラベルを作成する場合、保持ラベルを使用してコンテンツをレコードとして分類するオプションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-315">When you create a retention label, you have the option to use the retention label to classify the content as a record.</span></span>
  
![[レコードとしてコンテンツを分類する] チェック ボックス](media/9c300739-d5d0-41d2-88dd-137f1cfc9cb6.png)
  
<span data-ttu-id="d7c27-317">アイテムがレコードとしてラベル付けされると、次の 4 つの処理ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-317">When an item is labeled as a record, four things happen:</span></span>
  
- <span data-ttu-id="d7c27-318">アイテムの完全な削除。</span><span class="sxs-lookup"><span data-stu-id="d7c27-318">The item can't be permanently deleted.</span></span>
    
- <span data-ttu-id="d7c27-319">アイテムの編集。</span><span class="sxs-lookup"><span data-stu-id="d7c27-319">The item can't be edited.</span></span>
    
- <span data-ttu-id="d7c27-320">ラベルの変更。</span><span class="sxs-lookup"><span data-stu-id="d7c27-320">The label can't be changed.</span></span>
    
- <span data-ttu-id="d7c27-321">ラベルの削除。</span><span class="sxs-lookup"><span data-stu-id="d7c27-321">The label can't be removed.</span></span>
    
### <a name="who-can-classify-content-as-a-record"></a><span data-ttu-id="d7c27-322">コンテンツをレコードとして分類できるユーザー</span><span class="sxs-lookup"><span data-stu-id="d7c27-322">Who can classify content as a record</span></span>

<span data-ttu-id="d7c27-p139">SharePoint コンテンツの場合、既定のメンバー グループ (投稿アクセス許可レベル) のユーザーは、コンテンツにレコード ラベルを適用できます。適用後、サイト コレクション管理者のみがその保持ラベルを削除または変更できます。さらに、コンテンツをレコードとして分類する保持ラベルは、[自動でコンテンツに適用](#auto-apply-retention-labels)できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p139">For SharePoint content, any user in the default Members group (the Contribute permission level) can apply a record label to content. Only the site collection administrator can remove or change that retention label after it's been applied. In addition, a retention label that classifies content as a record can be [auto-applied to content](#auto-apply-retention-labels).</span></span>
  
### <a name="records-and-folders"></a><span data-ttu-id="d7c27-326">レコードとフォルダー</span><span class="sxs-lookup"><span data-stu-id="d7c27-326">Records and folders</span></span>

<span data-ttu-id="d7c27-p140">保持ラベルは、Exchange、SharePoint、または OneDrive 内のフォルダーに適用できます。フォルダーがレコードとしてラベル付けされている場合にフォルダーにアイテムを移動すると、アイテムはレコードとしてラベル付けされます。フォルダーからアイテムを移動しても、アイテムは引き続きレコードとしてラベル付けされます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p140">You can apply a retention label to a folder in Exchange, SharePoint, or OneDrive. If a folder is labeled as a record, and you move an item into the folder, the item is labeled as a record. When you move the item out of the folder, the item will continue to be labeled as a record.</span></span>
  
### <a name="records-cant-be-deleted"></a><span data-ttu-id="d7c27-330">レコードの削除不可</span><span class="sxs-lookup"><span data-stu-id="d7c27-330">Records can't be deleted</span></span>

<span data-ttu-id="d7c27-331">Exchange でレコードを削除しようとすると、「[アイテム保持ポリシーは所定の場所にあるコンテンツに対してどのように機能するか](retention-policies.md#how-a-retention-policy-works-with-content-in-place)」で説明されているように、アイテムは [回復可能なアイテム] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-331">If you attempt to delete a record in Exchange, the item is moved to the Recoverable Items folder as described in [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>
  
<span data-ttu-id="d7c27-332">SharePoint でレコードを削除しようとすると、「アイテムが削除されませんでした」というエラーが表示され、そのアイテムはライブラリに残ります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-332">If you attempt to delete a record in a SharePoint, you see an error that the item wasn't deleted, and the item remains in the library.</span></span>
  
![Sharepoint の「アイテムが削除されませんでした」というメッセージ](media/d0020726-1593-4a96-b07c-89b275e75c49.png)
  
<span data-ttu-id="d7c27-334">OneDrive でレコードを削除しようとすると、「[アイテム保持ポリシーは所定の場所にあるコンテンツに対してどのように機能するか](retention-policies.md#how-a-retention-policy-works-with-content-in-place)」で説明されているように、アイテムは [アイテム保管] ライブラリに移動されます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-334">If you attempt to delete a record in OneDrive, the item is moved to the Preservation Hold library as described in [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>
  
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="d7c27-335">DLP ポリシーでの条件としての保持ラベルの使用</span><span class="sxs-lookup"><span data-stu-id="d7c27-335">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="d7c27-p141">保持ラベルはコンテンツに対して保持アクションを強制できます。また、保持ラベルをデータ損失防止 (DLP) ポリシーで条件として使用できます。DLP ポリシーは特定のラベルを含むコンテンツに対して、アクセスを制限するなどの他のアクションを強制できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p141">A retention label can enforce retention actions on content. In addition, you can use a retention label as a condition in a data loss prevention (DLP) policy, and the DLP policy can enforce other actions, such as restricting access, on content that contains a specific label.</span></span> 
  
<span data-ttu-id="d7c27-338">詳細については、「[DLP ポリシーにおける条件としてのラベルの使用](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-338">For more information, see [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
  
## <a name="using-the-label-activity-explorer-and-the-data-governance-reports"></a><span data-ttu-id="d7c27-339">ラベル アクティビティ エクスプローラーとデータ ガバナンス レポートの使用。</span><span class="sxs-lookup"><span data-stu-id="d7c27-339">Using the Label Activity Explorer and the data governance reports</span></span>

<span data-ttu-id="d7c27-p142">保持ラベルを発行または自動適用した後、意図したとおりにラベルがコンテンツに適用されていることを確認する必要があります。保持ラベルを監視するには、次のものを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p142">After you publish or auto-apply your retention labels, you'll want to verify that they're being applied to content as you intended. To monitor your retention labels, you can use the:</span></span>
  
- <span data-ttu-id="d7c27-p143">**ラベル アクティビティ エクスプローラー**。エクスプローラー (下記参照) を使用すると、過去 30 日間の SharePoint および OneDrive for Business 全体のすべてのコンテンツの保持ラベルのアクティビティをすばやく検索して表示できます。詳細については、「[ドキュメントのラベルのアクティビティを表示する](view-label-activity-for-documents.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p143">**Label Activity Explorer**. With the explorer (shown below), you can quickly search and view retention label activity for all content across SharePoint and OneDrive for Business over the past 30 days. For more information, see [View label activity for documents](view-label-activity-for-documents.md).</span></span>
    
- <span data-ttu-id="d7c27-p144">**データ ガバナンス レポート**。これらのレポートでは、過去 90 日間の Exchange、SharePoint および OneDrive for Business 全体のすべてのコンテンツの保持ラベルの傾向とアクティビティをすばやく表示できます。詳細については、「[データ ガバナンス レポートを表示する](view-the-data-governance-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p144">**Data governance reports**. With these reports, you can quickly view retention label trends and activity for all content across Exchange, SharePoint, and OneDrive for Business over the past 90 days. For more information, see [View the data governance reports](view-the-data-governance-reports.md).</span></span>
    
![ラベル アクティビティ エクスプローラー](media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it"></a><span data-ttu-id="d7c27-349">コンテンツ検索を使用した特定の保持ラベルが適用されたすべてのコンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="d7c27-349">Using Content Search to find all content with a specific retention label applied to it</span></span>

<span data-ttu-id="d7c27-350">ユーザーまたは自動適用によって保持ラベルがコンテンツに割り当てられた後、セキュリティ/コンプライアンス センターでコンテンツ検索を使用して、特定の保持ラベルで分類されているすべてのコンテンツを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-350">After retention labels are assigned to content, either by users or auto-applied, you can use content search in the Security &amp; Compliance Center to find all content that's classified with a specific retention label.</span></span>
  
![コンテンツ検索ページ](media/564d5dfe-285a-4a7e-800e-907b12a1b273.png)
  
<span data-ttu-id="d7c27-p145">コンテンツ検索を作成する場合は、**[コンプライアンス タグ]** 条件を選択し、完全なラベル名またはラベル名の一部を入力し、ワイルドカードを使用します。詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p145">When you create a content search, choose the **Compliance Tag** condition, and then enter the complete label name or part of the label name and use a wildcard. For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![[コンプライアンス タグ] 条件](media/82d6af16-59f8-462f-babb-c894b2917018.png)
  
## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="d7c27-355">保持の原則、すなわち優先順位について</span><span class="sxs-lookup"><span data-stu-id="d7c27-355">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="d7c27-p146">コンテンツには複数のアイテム保持ポリシーが適用され、各ポリシーに異なるアクション (保持または削除、あるいはその両方) と保持期間が設定されている場合が多くあります。どれが優先されるのでしょうか? 概ね、あるポリシーで保持されているコンテンツを別のポリシーで完全に削除することはできないので、ご安心ください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p146">It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or both) and retention period. What takes precedence? At the highest level, rest assured that content being retained by one policy can't be permanently deleted by another policy.</span></span>
  
![保持の原則の図](media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="d7c27-360">保持アクションが設定されたさまざまなラベルがコンテンツにどのように適用されているかを理解するには、次の保持の原則に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-360">To understand how different labels with retention actions are applied to content, keep these principles of retention in mind:</span></span>
  
1. <span data-ttu-id="d7c27-p147">**保持の削除が優先されます。** あるアイテム保持ポリシーで 3 年後に Exchange メールを削除するように設定され、別のアイテム保持ポリシーでは Exchange メールを 5 年間保持してから削除するように設定されているとします。この場合、3 年を経過したコンテンツはすべて削除され、ユーザーには表示されなくなりますが、コンテンツは完全に削除される 5 年を経過するまで、回復可能なアイテム フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p147">**Retention wins over deletion.** Suppose that one retention policy says to delete Exchange email after three years, but another retention policy says to retain Exchange email for five years and then delete it. Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it will be permanently deleted.</span></span> 
    
2. <span data-ttu-id="d7c27-p148">**最長の保持期間が優先されます。** コンテンツを保持する複数のポリシーの対象となるコンテンツは、最長の保持期間が終了するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p148">**The longest retention period wins.** If content's subject to multiple policies that retain content, it will be retained until the end of the longest retention period.</span></span> 
    
3. <span data-ttu-id="d7c27-p149">**明示的な包含は暗黙的な包含に優先します。** これは次を意味します。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p149">**Explicit inclusion wins over implicit inclusion.** This means:</span></span> 
    
    1. <span data-ttu-id="d7c27-p150">保持設定を持つ保持ラベルをユーザーが Exchange メールや OneDrive ドキュメントなどのアイテムに手動で割り当てると、その保持ラベルはサイト レベルまたはメールボックス レベルで割り当てられたポリシー、およびドキュメント ライブラリによって割り当てられた既定の保持ラベルよりも優先されます。たとえば、明示的な保持ラベルで 10 年間保持するように設定されているときに、サイトに割り当てられた保持ポリシーでは 5 年間のみ保持するように設定されている場合は、保持ラベルが優先されます。自動適用の保持ラベルは、Office 365 によって自動的に適用されるため、明示的ではなく暗黙的に指定されます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p150">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a policy assigned at the site or mailbox level and a default retention label assigned by the document library. For example, if the explicit retention label says to retain for ten years, but the retention policy assigned to the site says to retain for only five years, the retention label takes precedence. Note that auto-apply retention labels are considered implicit, not explicit, because they're applied automatically by Office 365.</span></span>
    
    2. <span data-ttu-id="d7c27-371">アイテム保持ポリシーに特定のユーザーのメールボックスまたは OneDrive for Business のアカウントなどの特定の場所が含まれている場合、そのポリシーは、すべてのユーザーのメールボックスまたは OneDrive for Business のアカウントに適用されるが、そのユーザーのメールボックスを特に含まない別の保持ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-371">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive for Business account, that policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive for Business accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="d7c27-p151">**最短の削除期間が優先されます。** 同様に、コンテンツを削除する複数のポリシー (保持なし) の対象となるコンテンツは、最短保持期間の終了時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p151">**The shortest deletion period wins.** Similarly, if content's subject to multiple policies that delete content (with no retention), it will be deleted at the end of the shortest retention period.</span></span> 
    
<span data-ttu-id="d7c27-374">保持の原則は上位から下位のタイブレーク フローとして機能することを理解します。すべてのポリシーまたはラベルによって適用された複数のルールがあるレベルで同じ場合、フローは次の下位レベルに移動し、ルールが適用される優先順位を決定します。</span><span class="sxs-lookup"><span data-stu-id="d7c27-374">Understand that the principles of retention work as a tie-breaking flow from top to bottom: If the rules applied by all policies or labels are the same at one level, the flow moves down to the next level to determine precedence for which rule is applied.</span></span>
  
<span data-ttu-id="d7c27-p152">最終的には、アイテム保持ポリシーまたはラベルでは、電子情報開示のために保留中のコンテンツを完全に削除することはできません。保留が解除されると、コンテンツは再び上記に記載されたクリーンアップ プロセスの対象となります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p152">Finally, a retention policy or label cannot permanently delete any content that's on hold for eDiscovery. When the hold is released, the content again becomes eligible for the cleanup process described above.</span></span>
  
## <a name="use-retention-labels-instead-of-these-features"></a><span data-ttu-id="d7c27-377">次の機能の代わりとしての保持ラベルの使用</span><span class="sxs-lookup"><span data-stu-id="d7c27-377">Use retention labels instead of these features</span></span>

<span data-ttu-id="d7c27-p153">保持ラベルは、組織全体および Exchange、SharePoint、OneDrive、Office 365 グループなど Office 365 全体にわたる組織のコンテンツで簡単に使用できます。Office 365 の任意の場所でコンテンツを分類したり、レコードを管理したり必要がある場合は、保持ラベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p153">Retention labels can easily be made available to an entire organization and its content across Office 365, including Exchange, SharePoint, OneDrive, and Office 365 groups. If you need to classify content or manage records anywhere in Office 365, we recommend that you use retention labels.</span></span>
  
<span data-ttu-id="d7c27-p154">Office 365 で以前にコンテンツの分類やレコードの管理に使用されていた機能は他に複数あります。それらの機能を次に示します。機能は引き続き、セキュリティ/コンプライアンス センターで作成された保持ラベルと並行して機能します。保持ラベルの実装は以前の機能とは異なる場合がありますが、保持ラベルの進化は Office 365 全体にわたるレコード管理を今後も向上させる原動力となります。そのため、この先、データ ガバナンスには、次に示す機能の代わりに保持ラベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p154">There are several other features that have previously been used to classify content or manage records in Office 365. These are listed below. These features will continue to work side by side with retention labels created in the Security &amp; Compliance Center. Note that while there are instances where the implementation of retention labels differs from previous features, the evolution of retention labels will drive the future of records management across Office 365. Therefore, moving forward, for data governance, we recommend that you use retention labels instead of these features.</span></span>
  
### <a name="exchange-online"></a><span data-ttu-id="d7c27-385">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d7c27-385">Exchange Online</span></span>

- <span data-ttu-id="d7c27-386">[メッセージング レコード管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) とも呼ばれる、[保持タグおよびアイテム保持ポリシー](https://go.microsoft.com/fwlink/?linkid=846125) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="d7c27-386">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (Deletion only)</span></span> 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="d7c27-387">SharePoint Online と OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d7c27-387">SharePoint Online and OneDrive for Business</span></span>

- <span data-ttu-id="d7c27-388">[インプレース レコード管理の構成](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保持)</span><span class="sxs-lookup"><span data-stu-id="d7c27-388">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (Retention)</span></span> 
    
- <span data-ttu-id="d7c27-389">[レコード センターの概要](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (保持)</span><span class="sxs-lookup"><span data-stu-id="d7c27-389">[Introduction to the Records Center](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (Retention)</span></span> 
    
- <span data-ttu-id="d7c27-390">[情報管理ポリシー](intro-to-info-mgmt-policies.md) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="d7c27-390">[Information management policies](intro-to-info-mgmt-policies.md) (Deletion only)</span></span> 
    
## <a name="permissions"></a><span data-ttu-id="d7c27-391">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="d7c27-391">Permissions</span></span>

<span data-ttu-id="d7c27-p155">アイテム保持ラベルを作成するコンプライアンス チームのメンバーには、セキュリティ/コンプライアンス センターへのアクセス許可が必要です。既定では、テナント管理者はこの場所へのアクセス許可を持っています。そのため、法令遵守責任者や他のユーザーに対し、テナント管理者のすべてのアクセス許可を付与せずに、セキュリティ/コンプライアンス センターへのアクセスを許可できます。これを行うには、セキュリティ/コンプライアンス センターの **[アクセス許可]** ページに移動して、**[コンプライアンス管理者]** 役割グループを編集し、メンバーをその役割グループに追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p155">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="d7c27-394">詳細については、「[ユーザーに Office 365 セキュリティ センター/コンプライアンス センターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7c27-394">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="d7c27-p156">これらのアクセス許可は、保持ラベルとラベル ポリシーを作成して適用するときにのみ必要になります。ポリシーを適用する場合に、コンテンツへのアクセスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d7c27-p156">These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-powershell-cmdlets-for-labels"></a><span data-ttu-id="d7c27-397">ラベルの PowerShell コマンドレットの検索</span><span class="sxs-lookup"><span data-stu-id="d7c27-397">Find the PowerShell cmdlets for labels</span></span>

<span data-ttu-id="d7c27-398">ラベル コマンドレットを使用するには、次を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7c27-398">To use the label cmdlets, you need to:</span></span>
  
1. [<span data-ttu-id="d7c27-399">Office 365 セキュリティ センターとコンプライアンス センターの PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="d7c27-399">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="d7c27-400">以下の Office 365 セキュリティ センターとコンプライアンス センターのコマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="d7c27-400">Use these Office 365 Security & Compliance Center cmdlets:</span></span>

  - [<span data-ttu-id="d7c27-401">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="d7c27-401">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetag)

  - [<span data-ttu-id="d7c27-402">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="d7c27-402">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-compliancetag)

  - [<span data-ttu-id="d7c27-403">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="d7c27-403">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-compliancetag)

  - [<span data-ttu-id="d7c27-404">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="d7c27-404">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-compliancetag)

  - [<span data-ttu-id="d7c27-405">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="d7c27-405">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/enable-compliancetagstorage)

  - [<span data-ttu-id="d7c27-406">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="d7c27-406">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetagstorage)

  - [<span data-ttu-id="d7c27-407">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="d7c27-407">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy)

  - [<span data-ttu-id="d7c27-408">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="d7c27-408">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)

  - [<span data-ttu-id="d7c27-409">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="d7c27-409">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy)

  - [<span data-ttu-id="d7c27-410">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="d7c27-410">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy)

  - [<span data-ttu-id="d7c27-411">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="d7c27-411">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule)

  - [<span data-ttu-id="d7c27-412">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="d7c27-412">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)

  - [<span data-ttu-id="d7c27-413">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="d7c27-413">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule)

  - [<span data-ttu-id="d7c27-414">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="d7c27-414">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule)

## <a name="more-information"></a><span data-ttu-id="d7c27-415">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d7c27-415">More information</span></span>

[<span data-ttu-id="d7c27-416">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="d7c27-416">Overview of retention policies</span></span>](retention-policies.md)
