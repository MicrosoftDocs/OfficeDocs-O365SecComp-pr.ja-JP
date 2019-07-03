---
title: アイテム保持ポリシーの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: アイテム保持ポリシーでは、コンテンツを保持するか、コンテンツを削除するか、またはコンテンツを保持した後で削除するかを事前に決定できます。さらに、1 つのポリシーを組織全体に適用するか、特定の場所やユーザーにのみ適用するか、すべてのコンテンツにポリシーを適用するか、特定の条件を満たしているコンテンツにのみポリシーを適用するかも事前に決定できます。
ms.openlocfilehash: 84470098cdbe1893a0e85dd52857bee428e58cbb
ms.sourcegitcommit: b262d40f6daf06be26e7586f37b736e09f8a4511
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35435257"
---
# <a name="overview-of-retention-policies"></a><span data-ttu-id="39caf-103">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="39caf-103">Overview of retention policies</span></span>

<span data-ttu-id="39caf-p101">ほとんどの組織では、電子メール、ドキュメント、インスタント メッセージなどのデータの量と複雑さが日々増しています。この情報の効果的な管理が重要になる理由は、次の事項が必要になるためです。</span><span class="sxs-lookup"><span data-stu-id="39caf-p101">For most organizations, the volume and complexity of their data is increasing daily - email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="39caf-106">**業界の規制や内部ポリシーを遵守する**: このために、コンテンツは最小限の期間保持する必要があります。たとえば、米国企業改革法では、特定の種類のコンテンツを 7 年間保持するように定められています。</span><span class="sxs-lookup"><span data-stu-id="39caf-106">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time - for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 
    
- <span data-ttu-id="39caf-107">**訴訟やセキュリティ違反が発生した場合にリスクを軽減する**: このために、保持する必要がなくなった古いコンテンツは完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="39caf-107">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="39caf-108">**組織内での効率的な知識の共有と迅速な対応に役立てる**: このために、ユーザーは現時点で関連性のあるコンテンツのみを対象に作業するようにします。</span><span class="sxs-lookup"><span data-stu-id="39caf-108">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="39caf-p102">アイテム保持ポリシーは、これらすべての目標の達成に役立ちます。一般に、コンテンツの管理に求められる操作は次の 2 つです。</span><span class="sxs-lookup"><span data-stu-id="39caf-p102">A retention policy can help you achieve all of these goals. Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="39caf-111">**コンテンツの保持**: 保持期間が満了するまではコンテンツの完全な削除ができないようにします。</span><span class="sxs-lookup"><span data-stu-id="39caf-111">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="39caf-112">**コンテンツの削除**: 保持期間の満了時点でコンテンツを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="39caf-112">**Deleting** content permanently at the end of the retention period.</span></span> 
    
<span data-ttu-id="39caf-113">アイテム保持ポリシーにより、次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="39caf-113">With a retention policy, you can:</span></span>
  
- <span data-ttu-id="39caf-114">コンテンツを保持するか、コンテンツを削除するか、コンテンツを保持した後に削除するかを事前に決定する。</span><span class="sxs-lookup"><span data-stu-id="39caf-114">Decide proactively whether to retain content, delete content, or both - retain and then delete the content.</span></span>
    
- <span data-ttu-id="39caf-115">1 つのポリシーを組織全体または特定の場所やユーザーにのみ適用する。</span><span class="sxs-lookup"><span data-stu-id="39caf-115">Apply a single policy to the entire organization or just specific locations or users.</span></span>
    
- <span data-ttu-id="39caf-116">すべてのコンテンツにポリシーを適用する。または、特定の条件を満たしているコンテンツ (たとえば、特定のキーワードや[特定の種類の機密情報](what-the-sensitive-information-types-look-for.md)を含むコンテンツ) にのみポリシーを適用する。</span><span class="sxs-lookup"><span data-stu-id="39caf-116">Apply a policy to all content or just content meeting certain conditions, such as content containing specific keywords or [specific types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span>
    
<span data-ttu-id="39caf-p103">コンテンツがアイテム保持ポリシーの対象になったときに、そのコンテンツは所定の場所に維持されるため、ユーザーは何も変更されなかったかのように元の場所でコンテンツに対する編集や作業を続行できます。ただし、ポリシーの対象になっているコンテンツを編集または削除すると、コピーが安全な場所に保存され、ポリシーが有効な間はその場所で保持されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p103">When content is subject to a retention policy, people can continue to edit and work with the content as if nothing's changed because the content is retained in place, in its original location. But if someone edits or deletes content that's subject to the policy, a copy is saved to a secure location where it's retained while the policy is in effect.</span></span>
  
<span data-ttu-id="39caf-p104">最後に、一部の組織は、米国証券取引委員会 (SEC) 規則 17a-4 のような規制に準拠する必要があります。この規則では、アイテム保持ポリシーをオンにした後で、そのポリシーをオフにすることや制限を緩和することが禁止されています。この要件を満たすために、保持ロックを使用できます。ポリシーがロックされていると、そのポリシーは誰も (管理者でも) オフにすることや制限を緩和することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="39caf-p104">Finally, some organizations might need to comply with regulations such as Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a retention policy is turned on, it cannot be turned off or made less restrictive. To meet this requirement, you can use Preservation Lock. After a policy's been locked, no one—including the administrator—can turn off the policy or make it less restrictive.</span></span>
  
<span data-ttu-id="39caf-122">アイテム保持ポリシーの作成と管理は、次の場所で実行します</span><span class="sxs-lookup"><span data-stu-id="39caf-122">You create and manage retention policies on the:</span></span>

- <span data-ttu-id="39caf-123">Microsoft 365 コンプライアンス センターの **[ポリシー]** ページ。</span><span class="sxs-lookup"><span data-stu-id="39caf-123">**Policies** page in the Microsoft 365 compliance center.</span></span>
- <span data-ttu-id="39caf-124">Office 365 セキュリティ/コンプライアンス センターの **[データ ガバナンス]** にある **[保持]** ページ。</span><span class="sxs-lookup"><span data-stu-id="39caf-124">**Retention** page under **Data governance** in the Office 365 Security &amp; Compliance Center.</span></span>
  
## <a name="how-a-retention-policy-works-with-content-in-place"></a><span data-ttu-id="39caf-125">アイテム保持ポリシーは所定の場所にあるコンテンツに対してどのように作用するか</span><span class="sxs-lookup"><span data-stu-id="39caf-125">How a retention policy works with content in place</span></span>

<span data-ttu-id="39caf-p105">サイトやメールボックスなどの場所をアイテム保持ポリシーに含めたときにも、コンテンツは元の場所に引き続き保持されます。そのため、ユーザーは何事もなかったかのように、自分のドキュメントやメールに対する作業を継続できます。ただし、ポリシーに含まれるコンテンツを編集したり削除したりした場合、ポリシーを適用したときの状態でコンテンツのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p105">When you include a location such as a site or mailbox in a retention policy, the content remains in its original location. People can continue to work with their documents or mail as if nothing's changed. But if they edit or delete content that's included in the policy, a copy of the content as it existed when you applied the policy is retained.</span></span>
  
<span data-ttu-id="39caf-p106">SharePoint サイト コレクションの場合、ユーザーがコンテンツを編集または削除すると、元のコンテンツのコピーが [アイテム保管ライブラリ] に保持されます。メールやパブリック フォルダーの場合、コピーは [回復可能なアイテム] フォルダーに保持されます。これらの安全な場所と保持されたコンテンツは、ほとんどのユーザーに表示されません。アイテム保持ポリシーでは、ユーザーは自分のコンテンツがポリシーの対象になっていることを知る必要もありません。</span><span class="sxs-lookup"><span data-stu-id="39caf-p106">For Sharepoint site collections, a copy of the original content is retained in the Preservation Hold library when users edit or delete it; for email and public folders, the copy is retained in the Recoverable Items folder. These secure locations and the retained content are not visible to most people. With a retention policy, people do not even need to know that their content is subject to the policy.</span></span>
  
<span data-ttu-id="39caf-132">注:</span><span class="sxs-lookup"><span data-stu-id="39caf-132">Notes:</span></span>
  
- <span data-ttu-id="39caf-133">Skype のコンテンツは Exchange に格納されます。ここでは、メッセージの種類 (メールまたは会話) に応じてポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-133">Skype content is stored in Exchange, where the policy is applied based on message type (email or conversation).</span></span>
    
- <span data-ttu-id="39caf-134">Office 365 のグループに適用されるアイテム保持ポリシーには、グループのメールボックスとサイトが両方とも含まれます。</span><span class="sxs-lookup"><span data-stu-id="39caf-134">A retention policy applied to an Office 365 group includes both the group mailbox and site.</span></span>
    
### <a name="content-in-onedrive-accounts-and-sharepoint-sites"></a><span data-ttu-id="39caf-135">OneDrive アカウントと SharePoint サイトのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="39caf-135">Content in OneDrive accounts and SharePoint sites</span></span>

<span data-ttu-id="39caf-p107">アイテム保持ポリシーは、サイト コレクション レベルで適用されます。アイテム保持ポリシーに SharePoint サイトや OneDrive アカウントを含めると、[アイテム保管ライブラリ] が作成されます (このライブラリが存在しない場合)。このライブラリは、サイト コレクションのトップレベル サイトの [**サイト コンテンツ**] に表示されます。[アイテム保管ライブラリ] はサイト コレクションの管理者のみに表示されるため、ほとんどのユーザーは参照できません。</span><span class="sxs-lookup"><span data-stu-id="39caf-p107">A retention policy is applied at the level of a site collection. When you include a SharePoint site collection or OneDrive account in a retention policy, a Preservation Hold library will be created, if one doesn't already exist. You can view this library on the **Site contents** page in the top-level site of the site collection. Most users can't view the Preservation Hold library because it's visible only to site collection administrators.</span></span>
  
<span data-ttu-id="39caf-p108">ユーザーがアイテム保持ポリシーの対象になっているサイトのコンテンツを変更または削除しようとすると、ポリシーによって、まず、そのコンテンツがポリシーの適用以降に変更されているかどうかが確認されます。アイテム保持ポリシーが適用されてから初めての変更である場合は、ポリシーによって、そのコンテンツがアイテム保管ライブラリにコピーされます。その後で、ユーザーは元のコンテンツを変更または削除できるようになります。アイテム保持ポリシーで使用しているクエリとコンテンツが一致しない場合でも、サイト コレクションのあらゆるコンテンツがアイテム保管ライブラリにコピーされることがあります。</span><span class="sxs-lookup"><span data-stu-id="39caf-p108">If a person attempts to change or delete content in a site that's subject to a retention policy, first the policy checks whether the content's been changed since the policy was applied. If this is the first change since the policy was applied, the retention policy copies the content to the Preservation Hold library, and then allows the person to change or delete the original content. Note that any content in the site collection can be copied to the Preservation Hold library, even if the content does not match the query used by the retention policy.</span></span>
  
<span data-ttu-id="39caf-p109">その次に、タイマー ジョブにより、アイテム保管ライブラリがクリーンアップされます。タイマー ジョブは定期的に実行され、アイテム保管ライブラリ内のすべてのコンテンツが、サイトのアイテム保持ポリシーで使用されているすべてのクエリと比較されます。コンテンツは、少なくとも 1 つのクエリと一致する場合を除いて、タイマー ジョブによってアイテム保持ライブラリから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p109">Then a timer job cleans up the Preservation Hold library. The timer job runs periodically and compares all content in the Preservation Hold library to all of the queries used by the retention policies on the site. Unless content matches at least one of the queries, the timer job permanently deletes the content from the Preservation Hold library.</span></span>
  
<span data-ttu-id="39caf-p110">これは、アイテム保持ポリシーが適用されたときに存在していたコンテンツに当てはまります。これに加えて、サイト コレクションがポリシーの対象になった後で作成または追加された新しいコンテンツは、削除後も保持されます。ただし、新しいコンテンツは、削除された場合にのみアイテム保管ライブラリにコピーされ、最初の編集時にはコピーされません。すべてのファイルのバージョンを保持するには、バージョン管理を有効にする必要があります。バージョン管理については、後述のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="39caf-p110">The previous applies to content that exists when the retention policy is applied. In addition, any new content that's created or added to the site collection after it was included in the policy will be retained after deletion. However, new content isn't copied to the Preservation Hold library the first time it's edited, only when it's deleted. To retain all versions of a file, you need to turn on versioning — see the below section on versioning.</span></span>
  
<span data-ttu-id="39caf-p111">ユーザーがライブラリ、リスト、フォルダー、またはアイテム保持ポリシーの対象になっているサイトを削除しようとするとエラーが発生することに注意してください。ユーザーはフォルダーを削除できますが、最初にポリシーの対象になっているファイルをすべてフォルダーから移動または削除する必要があります。[アイテム保管ライブラリ] が作成されるのは、アイテム保持ポリシーが作成されたときではなく、このライブラリにコピーする必要がある最初のアイテムが出現したときであることに注意してください。そのため、ポリシーをテストするには、最初にポリシーの対象になっているサイトでドキュメントを編集または削除し、それから [アイテム保管ライブラリ] を参照して保持されたコピーの確認を行うようにします。</span><span class="sxs-lookup"><span data-stu-id="39caf-p111">Note that a user will receive an error if they try to delete a library, list, folder, or site that's subject to a retention policy. A user can delete a folder if they first move or delete any files in the folder that are subject to the policy. Also note that the Preservation Hold library is created only when the first item needs to be copied to the library - not when you create the retention policy. Therefore, to test your policy, you first need to edit or delete a document in a site subject to the policy, and then browse to the Preservation Hold library to view the retained copy.</span></span>
  
![SharePoint および OneDrive のコンテンツのライフサイクルの図](Retention_Diagram_of_retention_flow_in_sites.png)
  
<span data-ttu-id="39caf-155">OneDrive アカウントまたは SharePoint サイトにアイテム保持ポリシーが割り当てられていると、コンテンツは次の 2 つの経路のどちらかで処理されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-155">After a retention policy is assigned to a OneDrive account or SharePoint site, content can follow one of two paths:</span></span>
  
1. <span data-ttu-id="39caf-156">保持期間中、**コンテンツが変更または削除された場合**、元のコンテンツがアイテム保持ポリシーが割り当てられたときの状態でコピーされたものは、[アイテム保管ライブラリ] で作成されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-156">**If the content is modified or deleted** during the retention period, a copy of the original content as it existed when the retention policy was assigned is created in the Preservation Hold library. There, a timer job runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within seven days of the end of the retention period.</span></span> <span data-ttu-id="39caf-157">ここで、タイマー ジョブが定期的に実行され、アイテム保持ポリシーの有効期間が過ぎたアイテムを特定します。このようなアイテムは、 第 2 段階の [ごみ箱] に移動され、移動から 93 日目に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-157">There, a timer job runs periodically and identifies items whose retention period has expired, and those items are moved to the second-stage Recycle Bin, where they're permanently deleted at the end of 93 days.</span></span> <span data-ttu-id="39caf-158">第 2 段階のごみ箱はエンドユーザーには表示されないことに注意してください (第1 段階のごみ箱のみ表示)。サイトコレクション管理者はそこにあるコンテンツを表示および復元できます。</span><span class="sxs-lookup"><span data-stu-id="39caf-158">Note that the second-stage Recycle Bin is not visible to end users (only the first-stage Recycle Bin is), but site collection admins can view and restore content from there.</span></span>

    > [!NOTE]
    > <span data-ttu-id="39caf-159">アイテム保管ライブラリからコンテンツを削除する方法が変更されました。</span><span class="sxs-lookup"><span data-stu-id="39caf-159">We've recently changed how content is deleted from the Preservation Hold library.</span></span> <span data-ttu-id="39caf-160">不注意によるデータの損失を防ぐために、アイテム保管ライブラリからコンテンツを完全に削除しないようになりました。</span><span class="sxs-lookup"><span data-stu-id="39caf-160">To help prevent inadvertent data loss, we no longer permanently delete content from the Preservation Hold library.</span></span> <span data-ttu-id="39caf-161">代わりに、ごみ箱のコンテンツのみを完全に削除するようになるため、保持アイテムライブラリのすべてのコンテンツは、第 2 段階のごみ箱を通過するようになります。</span><span class="sxs-lookup"><span data-stu-id="39caf-161">Instead, we permanently delete content only from the Recycle Bin, so all content from the Preservation Hold library now goes through the second-stage Recycle Bin.</span></span>
    
2. <span data-ttu-id="39caf-p114">保持期間中に**コンテンツが変更または削除されていない場合**。保持期間の満了日に、コンテンツは [第 1 段階のごみ箱] に移動されます。ユーザーが [第 1 段階のごみ箱] からコンテンツを削除した場合や、このごみ箱を空にした場合、ドキュメントは [第 2 段階のごみ箱] に移動されます。第 1 段階と第 2 段階の両方のごみ箱で保持期間は 93 日間です。93 日目に、ドキュメントは第 1 段階と第 2 段階のどちらにあっても完全に削除されます。[ごみ箱] にはインデックスが作成されないため、検索機能でコンテンツを見つけることができない点に注意してください。そのため、電子情報開示の保留リストでは、コンテンツの保留ために [ごみ箱] 内を検索できません。</span><span class="sxs-lookup"><span data-stu-id="39caf-p114">**If the content is not modified or deleted** during the retention period, it's moved to the first-stage Recycle Bin at the end of the retention period. If a user deletes the content from there or empties this Recycle Bin (also known as purging), the document is moved to the second-stage Recycle Bin. A 93-day retention period spans both the first- and second-stage recycle bins. At the end of 93 days, the document is permanently deleted from wherever it resides, in either the first- or second-stage Recycle Bin. Note that the Recycle Bin is not indexed and therefore searches do not find content there. This means that an eDiscovery hold can't locate any content in the Recycle Bin in order to hold it.</span></span> 
    
### <a name="content-in-mailboxes-and-public-folders"></a><span data-ttu-id="39caf-167">メールボックス内およびパブリック フォルダー内にあるコンテンツ</span><span class="sxs-lookup"><span data-stu-id="39caf-167">Content in mailboxes and public folders</span></span>

<span data-ttu-id="39caf-p115">ユーザーのメールや予定表などのアイテムには、メールボックス レベルでアイテム保持ポリシーが適用されます。パブリック フォルダーには、メールボックス レベルではなく、フォルダー レベルでアイテム保持ポリシーが適用されます。メールボックスとパブリック フォルダーの両方で、アイテム保持のために [回復可能なアイテム] フォルダーが使用されます。別のユーザーの [回復可能なアイテム] フォルダーに含まれるアイテムは、電子情報開示のアクセス許可が割り当てられているユーザーのみが閲覧できます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p115">For a user's mail, calendar, and other items, a retention policy is applied at the level of a mailbox. For a public folder, a retention policy is applied at the folder level, not the mailbox level. Both a mailbox and a public folder use the Recoverable Items folder to retain items. Only people whom have been assigned eDiscovery permissions can view items in another user's Recoverable Items folder.</span></span>
  
<span data-ttu-id="39caf-p116">既定では、ユーザーが [削除済みアイテム] フォルダー以外のフォルダー内のメッセージを削除すると、そのメッセージは [削除済みアイテム] フォルダーに移動されます。ユーザーが [削除済みアイテム] フォルダー内のアイテムを削除すると、そのメッセージは [回復可能なアイテム] フォルダーに移動されます。また、ユーザーは任意のフォルダー内のアイテムを論理的に削除できます (Shift キーと Delete キーを同時に押します)。この操作により、アイテムは [削除済みアイテム] フォルダーをバイパスして、[回復可能なアイテム] フォルダーに直接移動されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p116">By default, when a person deletes a message in a folder other than the Deleted Items folder, the message is moved to the Deleted Items folder. When a person deletes an item in the Deleted Items folder, the message is moved to the Recoverable Items folder. In addition, a person can soft delete an item (SHIFT+DELETE) in any folder, which bypasses the Deleted Items folder and moves the item directly to the Recoverable Items folder.</span></span>
  
<span data-ttu-id="39caf-p117">[回復可能なアイテム] フォルダー内のアイテムは、プロセスによって定期的に評価されます。どのアイテム保持ポリシーとも一致しないアイテムは、[回復可能なアイテム] フォルダーから完全に削除されます (この削除は物理的な削除とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="39caf-p117">A process periodically evaluates items in the Recoverable Items folder. If an item doesn't match the rules of at least one retention policy, the item is permanently deleted (also called hard deleted) from the Recoverable Items folder.</span></span>
  
<span data-ttu-id="39caf-p118">ユーザーがメールボックス アイテムの特定のプロパティ (件名、本文、添付ファイル、送信者と受信者、メッセージの送信日や受信日など) を変更しようとすると、変更の確定前に、元のアイテムのコピーが [回復可能なアイテム] フォルダーに保存されます。それ以降、この処理は変更があるたびに実行されます。[回復可能なアイテム] フォルダー内のコピーは、保持期間の満了日に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p118">When a person attempts to change certain properties of a mailbox item — such as the subject, body, attachments, senders and recipients, or date sent or received for a message — a copy of the original item is saved to the Recoverable Items folder before the change is committed. This happens for each subsequent change. At the end of the retention period, copies in the Recoverable Items folder are permanently deleted.</span></span>
  
<span data-ttu-id="39caf-p119">組織を退職するユーザーのメールボックスがアイテム保持ポリシーに含まれている場合は、そのユーザーの Office 365 アカウントが削除されたときに、メールボックスが非アクティブなメールボックスになります。非アクティブなメールボックスのコンテンツは、引き続きメールボックスが非アクティブになる前に実施されたアイテム保持ポリシーの適用対象であり、電子情報開示の検索に表示されます。詳細については、「[Exchange Online の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39caf-p119">If a user leaves your organization, and their mailbox is included in a retention policy, the mailbox becomes an inactive mailbox when the user's Office 365 account is deleted. The contents of an inactive mailbox are still subject to any retention policy that was placed on the mailbox before it was made inactive, and the contents are available to an eDiscovery search. For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span>
  
![メールおよびパブリック フォルダーの保持フローについての図](media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)
  
<span data-ttu-id="39caf-184">メールボックスまたはパブリック フォルダーにアイテム保持ポリシーが割り当てられていると、コンテンツは次の 2 つの経路のどちらかで処理されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-184">After a retention policy is assigned to a mailbox or public folder, content can follow one of two paths:</span></span>
  
1. <span data-ttu-id="39caf-p120">保持期間中に**ユーザーがアイテムを変更または完全に削除した場合**。ユーザーが Shift キーと Delete キーを同時に押すか、[削除済みアイテム] から削除を実行すると、アイテムは [回復可能なアイテム] フォルダーに移動されます (編集の場合はコピーされます)。ここでは、プロセスが定期的に実行され、アイテム保持ポリシーの有効期間を経過したアイテムが識別されます。これに該当するアイテムは、保持期間の満了日から 14 日以内に完全に削除されます。既定の設定は 14 日間ですが、最長 30 日間にまで変更できます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p120">**If the item is modified or permanently deleted** by the user (either SHIFT+DELETE or deleted from Deleted Items) during the retention period, the item is moved (or copied, in the case of edit) to the Recoverable Items folder. There, a process runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period. Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span>
    
2. <span data-ttu-id="39caf-p121">保持期間中に**アイテムが変更または削除されていない場合**。同じプロセスがメールボックス内のすべてのフォルダーに対して定期的に実行され、アイテム保持ポリシーの有効期間を経過したアイテムが識別されます。これに該当するアイテムは、保持期間の満了日から 14 日以内に完全に削除されます。既定の設定では 14 日間ですが、最長 30 日間にまで変更できます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p121">**If the item is not modified or deleted** during the retention period, the same process runs periodically on all folders in the mailbox and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period. Note that 14 days is the default setting but it can be configured up to 30 days.</span></span> 
    
## <a name="how-a-retention-policy-works-with-document-versions-in-a-site-collection"></a><span data-ttu-id="39caf-190">アイテム保持ポリシーはサイト コレクションのドキュメントのバージョンにどのように作用するか</span><span class="sxs-lookup"><span data-stu-id="39caf-190">How a retention policy works with document versions in a site collection</span></span>

<span data-ttu-id="39caf-p122">バージョン管理は、SharePoint Online と OneDrive for Business のすべてのドキュメント ライブラリの機能です。既定では、少なくとも 500 件のメジャー バージョンが保持されます (この制限は増やすことができます)。詳細については、「[リストまたはライブラリのバージョン管理を有効にして構成する](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39caf-p122">Versioning is a feature of all document libraries in SharePoint Online and OneDrive for Business. By default, versioning retains a minimum of five hundred major versions, though you can increase this limit. For more information, see [Enable and configure versioning for a list or library](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37).</span></span>
  
<span data-ttu-id="39caf-p123">アイテム保持ポリシーにより、SharePoint サイト コレクションまたは OneDrive アカウントのドキュメントのすべてのバージョンが保持されます。アイテム保持ポリシーの対象になっているドキュメントが編集または削除されるたびに、アイテム保管ライブラリにバージョンがコピーされます。アイテム保管ライブラリ内のドキュメントの各バージョンは、独自の保持期間が設定された個別のアイテムとして存在します。</span><span class="sxs-lookup"><span data-stu-id="39caf-p123">A retention policy retains all versions of a document in a SharePoint site collection or OneDrive account. Each time a document subject to a retention policy is edited or deleted, a version is copied to the Preservation Hold library. Each version of a document in the Preservation Hold library exists as a separate item with its own retention period:</span></span>
  
- <span data-ttu-id="39caf-p124">アイテム保持ポリシーがコンテンツの作成日時に基づいている場合、それぞれのバージョンには、元のドキュメントと同じ有効期限日が設定されます。元のドキュメントとそのバージョンは、すべて同時に期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p124">If the retention policy is based on when the content was created, each version has the same expiration date as the original document. The original document and its versions all expire at the same time.</span></span>
    
- <span data-ttu-id="39caf-p125">アイテム保持ポリシーがコンテンツの最終更新日時に基づいている場合、それぞれのバージョンには、そのバージョンを作成するために元のドキュメントを変更した日時に基づいた独自の有効期限日が設定されます。元のドキュメントとそのバージョンは、個別に期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p125">If the retention policy is based on when the content was last modified, each version has its own expiration date based on when the original document was modified to create that version. The original documents and its versions expire independently of each other.</span></span>
    
## <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="39caf-201">コンテンツを特定の期間保持する</span><span class="sxs-lookup"><span data-stu-id="39caf-201">Retaining content for a specific period of time</span></span>

<span data-ttu-id="39caf-p126">アイテム保持ポリシーでは、コンテンツを無期限に保持することも、指定した日数、月数、または年数で保持することもできます。コンテンツの保持期間は、アイテム保持ポリシーの適用時点からではなく、コンテンツの経過時間で計算されます。コンテンツの経過時間は、コンテンツが作成された日時、または最後に更新された日時 (OneDrive や SharePoint の場合) のどちらかを基準に計算するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p126">With a retention policy, you can retain content indefinitely or for a specific number of days, months, or years. Note that the duration for how long content is retained is calculated from the age of the content, not from when the retention policy is applied. You can choose whether the age is based on when the content was created or (for OneDrive and SharePoint) when it was last modified.</span></span>
  
<span data-ttu-id="39caf-p127">たとえば、サイト コレクションのコンテンツを最終変更日から 7 年間保持するとします。そのサイト コレクションのドキュメントが過去 6 年間変更されていない場合、そのドキュメントは、もう 1 年間のみ保持されます。そのドキュメントが再度編集された場合、ドキュメントの経過時間は新しい最終変更日から計算され、その時点から 7 年間保持されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p127">For example, if you want to retain content in a site collection for seven years since it was last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified. If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>
  
<span data-ttu-id="39caf-p128">同様に、メールボックスのコンテンツを 7 年間保持するとします。メッセージが 6 年前に送信されていた場合、そのメッセージは、もう 1 年間のみ保持されます。Exchange のコンテンツの経過時間は、常に、受信日または送信日に基づいて計算されます。最終更新日に基づいてコンテンツを保持するポリシーは、OneDrive および SharePoint のサイト コンテンツにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p128">Similarly, if you want to retain content in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year. For Exchange content, the age is always based on the date received or sent (they are the same). Retaining content based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>
  
<span data-ttu-id="39caf-p129">保持期間の満了日にコンテンツを完全に削除するかどうかは選択できます。アイテム保持ポリシーでは、古いコンテンツを保持しないで削除することもできます。次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39caf-p129">You can choose whether you want the content to be permanently deleted at the end of the retention period. A retention policy can also simply delete old content without retaining it - see the next section.</span></span>
  
![[アイテム保持設定] ページ](media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
## <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="39caf-213">特定の経過時間を超えた古いコンテンツを削除する</span><span class="sxs-lookup"><span data-stu-id="39caf-213">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="39caf-214">アイテム保持ポリシーでは、コンテンツを保持してから削除することも、古いコンテンツを保持しないで削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="39caf-214">A retention policy can both retain and then delete content, or simply delete old content without retaining it.</span></span>
  
<span data-ttu-id="39caf-215">アイテム保持ポリシーによってコンテンツを削除する場合、アイテム保持ポリシーに指定した期間は、ポリシーが割り当てられた時点からではなく、コンテンツが作成または変更された時点から計算されることを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="39caf-215">If your retention policy deletes content, it's important to understand that the time period specified for a retention policy is calculated from the time when the content was created or modified, not the time since the policy was assigned.</span></span>
  
![[削除の設定]](media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
<span data-ttu-id="39caf-p130">たとえば、3 年間経過後のコンテンツを削除するアイテム保持ポリシーを作成して、そのポリシーをすべての OneDrive アカウントに割り当てるとします。また、該当するアカウントには 4 年から 5 年前に作成されたコンテンツが数多く含まれているとします。この場合、そのアイテム保持ポリシーを初めて割り当てたときに、多数のコンテンツがすぐに削除されます。こうした理由から、**コンテンツを削除するアイテム保持ポリシーは、コンテンツに大きな影響を与えることになります**。</span><span class="sxs-lookup"><span data-stu-id="39caf-p130">For example, suppose that you create a retention policy that deletes content after three years, and then assign that policy to all OneDrive accounts, which contain a lot of content that was created four or five years ago. In this case, a lot of content will be deleted soon after assigning the retention policy for the first time. For this reason, **a retention policy that deletes content can have a considerable impact on your content**.</span></span> 
  
<span data-ttu-id="39caf-p131">そのため、サイト コレクションに初めてポリシーを割り当てるときには、その前に、既存のコンテンツの経過時間と、そのコンテンツにポリシーが及ぼす影響について考慮する必要があります。また、新しいポリシーを割り当てる前に、サイト所有者に連絡して、発生する可能性のある影響について評価するための時間を与えるようにしてください。アイテム保持ポリシーの作成前に設定を確認すると、この警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p131">Therefore, before you assign a retention policy to a site collection for the first time, you should first consider the age of the existing content and how the policy may impact that content. You may also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact. Note this warning that appears when you review the settings for your retention policy just before creating it.</span></span>
  
![コンテンツの削除に関する警告](media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-that-apply-a-policy-only-to-content-that-meets-certain-conditions"></a><span data-ttu-id="39caf-224">特定の条件を満たすコンテンツにのみポリシーを適用するための高度な設定</span><span class="sxs-lookup"><span data-stu-id="39caf-224">Advanced settings that apply a policy only to content that meets certain conditions</span></span>

<span data-ttu-id="39caf-225">アイテム保持ポリシーは、その場所に含まれるすべてのコンテンツに適用することも、特定のキーワードや[特定の種類の機密情報](what-the-sensitive-information-types-look-for.md)を含むコンテンツにのみ適用するように選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="39caf-225">A retention policy can apply to all content in the locations that it includes, or you can choose to apply a retention policy only to content that contains specific keywords or [specific types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span>
  
![高度なアイテム保持のオプション](media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="retain-content-that-contains-specific-keywords"></a><span data-ttu-id="39caf-227">特定のキーワードを含むコンテンツを保持する</span><span class="sxs-lookup"><span data-stu-id="39caf-227">Retain content that contains specific keywords</span></span>

<span data-ttu-id="39caf-p132">特定の条件を満たすコンテンツにのみアイテム保持ポリシーを適用して、そのコンテンツのみを保持できます。現時点で利用可能な条件では、特定の単語や語句を含むコンテンツにアイテム保持ポリシーを適用することがサポートされています。AND、OR、NOT などの検索演算子を使用すると、クエリの範囲を絞り込むことができます。これらの演算子の詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39caf-p132">You can apply a retention policy only to content that satisfies certain conditions, and then take retention actions on just that content. The conditions available now support applying a retention policy to content that contains specific words or phrases. You can refine your query by using search operators like AND, OR, and NOT. For more information on these operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="39caf-232">検索可能なプロパティ (**件名:** など) の追加については間もなくサポートされます。</span><span class="sxs-lookup"><span data-stu-id="39caf-232">Support for adding searchable properties (for example, **subject:**) is coming soon.</span></span>
  
<span data-ttu-id="39caf-233">クエリ ベースのアイテム保持では、コンテンツの識別に検索インデックスが使用される点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="39caf-233">Note that query-based retention uses the search index to identify content.</span></span>
  
![クエリ エディター](media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="retain-content-that-contains-sensitive-information"></a><span data-ttu-id="39caf-235">機密情報が含まれているコンテンツを保持する</span><span class="sxs-lookup"><span data-stu-id="39caf-235">Retain content that contains sensitive information</span></span>

<span data-ttu-id="39caf-p133">アイテム保持ポリシーは、[特定の種類の機密情報](what-the-sensitive-information-types-look-for.md)が含まれているコンテンツにのみ適用できます。たとえば、納税者番号、社会保障番号、パスポート番号などの個人を特定できる情報 (PII) が含まれているコンテンツにのみ固有の保持要件を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p133">You can also apply a retention policy only to content that contains [specific types of sensitive information](what-the-sensitive-information-types-look-for.md). For example, you can choose to apply unique retention requirements only to content that contains personally identifiable information (PII) such as taxpayer identification numbers, social security numbers, or passport numbers.</span></span>
  
![機密情報の種類のページ](media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
<span data-ttu-id="39caf-239">注:</span><span class="sxs-lookup"><span data-stu-id="39caf-239">Notes:</span></span>
  
- <span data-ttu-id="39caf-240">機密情報に対応する高度な保持は、Exchange のパブリック フォルダーや Skype for Business には適用されません (これらの場所が機密情報の種類をサポートしていないため)。</span><span class="sxs-lookup"><span data-stu-id="39caf-240">Advanced retention for sensitive information doesn't apply to Exchange public folders or Skype for Business because those locations don't support sensitive information types.</span></span>
    
- <span data-ttu-id="39caf-p134">Exchange Online では、機密情報の識別にメール フロー ルール (トランスポート ルールとも呼ばれる) が使用されていることを理解している必要があります。このルールは、転送中のメッセージには有効ですが、既にメールボックスに保存されているアイテムには作用しません。つまり、Exchange Online の場合、アイテム保持ポリシーでは、そのポリシーがメールボックスに適用された**後**に受信したメッセージに対してのみ機密情報の識別と保持が可能になります (前のセクションで説明したクエリ ベースの保持では、コンテンツを識別する際に検索インデックスが使用されるため、このような制限はありません)。</span><span class="sxs-lookup"><span data-stu-id="39caf-p134">You should understand that Exchange Online uses mail flow rules (also known as transport rules) to identify sensitive information, so this works only on messages in transit — not on all items already stored in a mailbox. For Exchange Online, this means that a retention policy can identify sensitive information and take retention actions only on messages that are received **after** the policy is applied to the mailbox. (Note that query-based retention described in the previous section doesn't have this limitation because it uses the search index to identify content.)</span></span> 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a><span data-ttu-id="39caf-244">アイテム保持ポリシーを組織全体または特定の場所に適用する</span><span class="sxs-lookup"><span data-stu-id="39caf-244">Applying a retention policy to an entire organization or specific locations</span></span>

<span data-ttu-id="39caf-245">アイテム保持ポリシーは、組織全体、場所全体、または特定の場所やユーザーのみに簡単に適用できます。</span><span class="sxs-lookup"><span data-stu-id="39caf-245">You can easily apply a retention policy to an entire organization, entire locations, or only to specific locations or users.</span></span>
  
### <a name="org-wide-policy"></a><span data-ttu-id="39caf-246">組織全体のポリシー</span><span class="sxs-lookup"><span data-stu-id="39caf-246">Org-wide policy</span></span>

<span data-ttu-id="39caf-247">アイテム保持ポリシーの強力な機能の 1 つとして、既定ではポリシーが Office 365 全体の場所に適用されます。これには、次の場所が含まれます。</span><span class="sxs-lookup"><span data-stu-id="39caf-247">One of the most powerful features of a retention policy is that by default it applies to locations across Office 365, including:</span></span>
  
- <span data-ttu-id="39caf-248">Exchange 電子メール</span><span class="sxs-lookup"><span data-stu-id="39caf-248">Exchange email</span></span>
    
- <span data-ttu-id="39caf-249">SharePoint サイト コレクション</span><span class="sxs-lookup"><span data-stu-id="39caf-249">SharePoint site collections</span></span>
    
- <span data-ttu-id="39caf-250">OneDrive アカウント</span><span class="sxs-lookup"><span data-stu-id="39caf-250">OneDrive accounts</span></span>
    
- <span data-ttu-id="39caf-p135">Office 365 のグループ (グループのメールボックスとサイトのコンテンツ、およびドキュメントに適用されます。Planner、Yammer、および CRM のコンテンツについては間もなくサポートされます)。</span><span class="sxs-lookup"><span data-stu-id="39caf-p135">Office 365 groups (applies to content in the group's mailbox, site, and documents. Support for content in Planner, Yammer, and CRM is coming soon.)</span></span>
    
- <span data-ttu-id="39caf-253">Exchange パブリック フォルダー</span><span class="sxs-lookup"><span data-stu-id="39caf-253">Exchange public folders</span></span>
    
![すべての場所のオプション](media/c343bd8e-42ac-4f17-a338-36f3c9598a86.png)
  
<span data-ttu-id="39caf-255">その他の組織全体のアイテム保持ポリシーに関する重要な機能は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="39caf-255">Other important features of an org-wide retention policy include:</span></span>
  
- <span data-ttu-id="39caf-256">ポリシーに含めることができるメールボックスまたはサイトの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="39caf-256">There is no limit to the number of mailboxes or sites the policy can include.</span></span>
    
- <span data-ttu-id="39caf-257">Exchange の場合、ポリシーの適用後に作成された新しいメールボックスには、そのポリシーが自動的に継承されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-257">For Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>
  
### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="39caf-258">場所全体に適用されるポリシー</span><span class="sxs-lookup"><span data-stu-id="39caf-258">A policy that applies to entire locations</span></span>

<span data-ttu-id="39caf-p136">場所を選択するときには、Exchange 電子メールや OneDrive アカウントなどの場所全体を簡単に含めたり除外したりできます。この操作は、該当する場所の **[状態]** をオンまたはオフに切り替えるだけです。</span><span class="sxs-lookup"><span data-stu-id="39caf-p136">When you choose locations, you can easily include or exclude an entire location, such as Exchange email or OneDrive accounts. To do so, simply toggle the **Status** of that location on or off.</span></span> 
  
<span data-ttu-id="39caf-p137">組織全体のポリシーと同様に、場所全体の任意の組み合わせにポリシーを適用する場合は、ポリシーに含めることができるメールボックスまたはサイトの数に制限はありません。たとえば、ポリシーにすべての Exchange 電子メールとすべての SharePoint サイトを含めると、数に関係なくすべてのサイトとメールボックスが含まれるようになります。また、Exchange の場合、ポリシーの適用後に作成された新しいメールボックスには、そのポリシーが自動的に継承されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p137">Like an org-wide policy, if a policy applies to any combination of entire locations, there is no limit to the number of mailboxes or sites the policy can include. For example, if a policy includes all Exchange email and all SharePoint sites, all sites and mailboxes will be included, no matter how many. And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>
 
![[場所の選択] ページ](media/6ac0c2d6-1abf-4690-b3f6-9ca506887ba3.png)
  
### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="39caf-265">特定の追加または除外を含むポリシー</span><span class="sxs-lookup"><span data-stu-id="39caf-265">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="39caf-p138">アイテム保持ポリシーは、特定のユーザーに適用することもできます。そのためには、目的の場所の **[状態]** をオンに切り替えてから、リンクを使用して特定のユーザー、Office 365 グループ、または場所を含めたり除外したりします。</span><span class="sxs-lookup"><span data-stu-id="39caf-p138">You can also apply a retention policy to specific users. To do so, toggle the **Status** of that location on, and then use the links to include or exclude specific users, Office 365 groups, or locations.</span></span> 
  
<span data-ttu-id="39caf-268">ただし、1,000 人を超える特定ユーザーを含めたり除外したりするアイテム保持ポリシーには、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="39caf-268">However, note that the following limits exist for a retention policy that includes or excludes over 1,000 specific users:</span></span>
  
- <span data-ttu-id="39caf-269">これに該当する保持ポリシーに含めることができるメールボックスは 1,000 個以下、サイト コレクションは 100 個以下です。</span><span class="sxs-lookup"><span data-stu-id="39caf-269">Such a retention policy can contain no more than 1,000 mailboxes and 100 site collections.</span></span>
    
- <span data-ttu-id="39caf-270">1 つのテナントに含めることができる、アイテム保持ポリシーは 10,000 個以下です。</span><span class="sxs-lookup"><span data-stu-id="39caf-270">A tenant can contain no more than 10,000 retention policies.</span></span>
    
<span data-ttu-id="39caf-271">こうした制限はありますが、組織全体のポリシーまたは場所全体に適用されるポリシーを適用することで、この制限を取り除くことができます。</span><span class="sxs-lookup"><span data-stu-id="39caf-271">Although these limits exist, understand that you can get over these limits by applying either an org-wide policy or a policy that applies to entire locations.</span></span>
  
### <a name="skype-locations"></a><span data-ttu-id="39caf-272">Skype の場所</span><span class="sxs-lookup"><span data-stu-id="39caf-272">Skype locations</span></span>

<span data-ttu-id="39caf-273">Exchange 電子メールとは異なり、Skype の場所の状態を切り替えるだけでは、すべてのユーザーを含めることができません。ただし、その場所をオンにしてから、会話を保持するユーザーを手動で選択することはできます。</span><span class="sxs-lookup"><span data-stu-id="39caf-273">Unlike Exchange email, you can't simply toggle the status of the Skype location on to include all users, but you can turn on that location and then manually choose the users whose conversations you want to retain.</span></span>
  
<span data-ttu-id="39caf-p139">Skype for Business のユーザーを選択するときには、列のヘッダーの **[名前]** ボックスを選択すると、簡単にすべてのユーザーを含めることができます。ただし、それぞれのユーザーが、このポリシーに個別に含まれるものとしてカウントされる点に注意してください。そのため、1,000 人以上のユーザーを含めると、前のセクションで説明した制限が適用されるようになります。すべての Skype ユーザーをここで選択することは、組織全体のポリシーに既定ですべての Skype ユーザーが含まれることと同じではありません。</span><span class="sxs-lookup"><span data-stu-id="39caf-p139">When you choose Skype for Business users, you can quickly include all users by selecting the **Name** box in the column header - however, it's important to understand that each user counts as a specific inclusion in the policy. Therefore, if you include over 1,000 users, the limits noted in the previous section apply. Selecting all Skype users here is not the same as if an org-wide policy were able to include all Skype users by default.</span></span> 
  
![Skype ユーザーの選択ページ](media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
<span data-ttu-id="39caf-p140">Outlook のフォルダー **[会話履歴]** は、Skype のアーカイブには作用しない機能です。**[会話履歴]** はエンド ユーザーが無効にできますが、Skype のアーカイブの場合はユーザーがアクセスできない (電子情報開示には使用できる) 非表示フォルダーに Skype の会話のコピーが保存されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p140">Note that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving. **Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>

### <a name="office-365-groups-locations"></a><span data-ttu-id="39caf-280">Office 365 グループの場所</span><span class="sxs-lookup"><span data-stu-id="39caf-280">Office 365 groups locations</span></span>

<span data-ttu-id="39caf-p141">Office 365 グループのコンテンツを保持するには、Office 365 グループの場所を使用する必要があります。Office 365 グループには Exchange メールボックスがありますが、Exchange の場所全体が含まれるアイテム保持ポリシーには、Office 365 グループのメールボックスのコンテンツは含まれません。Office 365 グループに適用されるアイテム保持ポリシーには、グループのメールボックスとサイトが両方とも含まれます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p141">To retain content for an Office 365 group, you need to use the Office 365 groups location. Even though an Office 365 group has an Exchange mailbox, a retention policy that includes the entire Exchange location won't include content in Office 365 group mailboxes. A retention policy applied to an Office 365 group includes both the group mailbox and site.</span></span>

<span data-ttu-id="39caf-p142">また、Exchange の場所を使用して、特定のグループのメールボックスを含めたり除外したりすることはできません。最初は Exchange の場所でグループのメールボックスを選択できますが、アイテム保持ポリシーを保存しようとすると、Exchange の場所では "RemoteGroupMailbox" を選択できないことを示すエラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="39caf-p142">In addition, it's not possible to use the Exchange location to include or exclude a specific group mailbox. Although the Exchange location initially allows a group mailbox to be selected, when you try to save the retention policy, you'll receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span> 
  
### <a name="teams-locations"></a><span data-ttu-id="39caf-286">Teams の場所</span><span class="sxs-lookup"><span data-stu-id="39caf-286">Teams locations</span></span>

<span data-ttu-id="39caf-p143">アイテム保持ポリシーは、Teams のチャットとチャネル メッセージの保持に使用できます。Teams のチャットは、チャットに参加していた各ユーザーのメールボックス内の隠しフォルダーに保存されます。また、Teams のチャネル メッセージは、チーム用のグループ メールボックス内の同様の隠しフォルダーに保存されます。ただし、Teams は Azure が提供するチャット サービスを使用し、そのサービスでも、このデータが保存されることを理解しておくことが重要です。また、このサービスは、既定でデータを無期限に保存します。このため、Teams のデータの保持および削除する場合は、Teams の場所を使用することを強くお勧めします。Teams の場所を使用すると、Exchange メールボックスと基になる Azure が提供するチャット サービスの両方から完全にデータが削除されます。詳細については、「[Microsoft Teams のセキュリティとコンプライアンスの概要](https://go.microsoft.com/fwlink/?linkid=871258)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39caf-p143">You can use a retention policy to retain chats and channel messages in Teams. Teams chats are stored in a hidden folder in the mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team. However, it's important to understand that Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data forever. For this reason, we strongly recommend that you use the Teams location to retain and delete Teams data. Using the Teams location will permanently delete data from both the Exchange mailboxes and the underlying Azure-powered chat service. For more information, see [Overview of security and compliance in Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258).</span></span>
  
<span data-ttu-id="39caf-p144">Teams のチャットとチャネル メッセージは、Exchange または Office 365 グループの場所にあるユーザーまたはグループのメールボックスに適用されているアイテム保持ポリシーの影響を受けない点に注意してください。Teams のチャットとチャネル メッセージは Exchange に保存されていても、Teams の場所に適用されるアイテム保持ポリシーのみの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p144">Note that Teams chats and channel messages are not affected by retention policies applied to user or group mailboxes in the Exchange or Office 365 groups locations. Even though Teams chats and channel messages are stored in Exchange, they're affected only by a retention policy that's applied to the Teams location.</span></span>
  
<span data-ttu-id="39caf-p145">Microsoft では、Teams のアイテム保持に関する作業を継続していて、近日中に追加機能が公開される予定です。それまでの間は、注意が必要な制限がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="39caf-p145">We're still working on retention in Teams, and additional features are coming. In the meantime, here are a few limitations to be aware of:</span></span>
  
- <span data-ttu-id="39caf-p146">**Teams には個別のアイテム保持ポリシーが必要**: アイテム保持ポリシーを作成して、Teams の場所をオンに切り替えると、その他のすべての場所がオフに切り替わります。Teams を含むアイテム保持ポリシーには、Teams のみを含めることが可能です (その他の場所は含めることができません)。</span><span class="sxs-lookup"><span data-stu-id="39caf-p146">**Teams require a separate retention policy** When you create a retention policy and toggle on the Teams location, all other locations toggle off. A retention policy that includes Teams can include only Teams and no other locations.</span></span> 
    
- <span data-ttu-id="39caf-299">**Teams は組織全体のポリシーには含まれない**: 組織全体のポリシーを作成する場合、Teams は含まれません。Teams には個別のアイテム保持ポリシーが必要になるためです。</span><span class="sxs-lookup"><span data-stu-id="39caf-299">**Teams are not included in an org-wide policy** If you create an org-wide policy, Teams are not included because they require a separate retention policy.</span></span> 
    
- <span data-ttu-id="39caf-p147">**Teams は高度なアイテム保持をサポートしていない**: アイテム保持ポリシーを作成するときに、[特定の条件を満たすコンテンツにのみポリシーを適用する高度な設定](#advanced-settings-that-apply-a-policy-only-to-content-that-meets-certain-conditions)を選択すると、Teams の場所は利用できなくなります。現時点では、Teams のアイテム保持はすべてのチャットおよびチャネル メッセージのコンテンツに適用されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p147">**Teams doesn't support advanced retention** When you create a retention policy, if you choose the [Advanced settings that apply a policy only to content that meets certain conditions](#advanced-settings-that-apply-a-policy-only-to-content-that-meets-certain-conditions), the Teams location is not available. At this time, retention in Teams applies to all of the chat and channel message content.</span></span>
    
- <span data-ttu-id="39caf-p148">**Teams コンテンツは削除されるまでに少なくとも 30 日間かかる**: 現時点では、経過時間が 30 日未満の Teams コンテンツを削除するポリシーの作成はサポートされていません。このポリシーを Teams コンテンツに適用する必要がある場合は、30 日以上のアイテム保持期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="39caf-p148">**Teams content must be at least 30 days old to be deleted** At this time, creating a policy to delete Teams content that's less than 30 days old is not supported. If you want this policy to apply to Teams content, specify a retention period that's equal to or greater than 30 days.</span></span> 
    
- <span data-ttu-id="39caf-p149">**Teams では保持されたコンテンツをクリーンアップするまでに最大 30 日間かかる可能性がある**: Teams に適用されているアイテム保持ポリシーでは、すべての関連するストレージの場所からコンテンツが削除されます。ただし、Teams クライアントが、アイテム保持ポリシーを基にコンテンツをクリーンアップするまでに、起動直後から最大 30 日間かかる可能性があります。コンテンツが Teams クライアントに引き続き表示される場合であっても、そのコンテンツはアイテム保持期間の終了後にコンテンツの検索や電子情報開示には表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="39caf-p149">**Teams may take up to 30 days to clean up retained content** A retention policy applied to Teams will delete the content from all relevant storage locations. However, immediately after launch, it may take up to 30 days for Teams clients to clean up content based on the retention policy. But even though content still appears in the Teams clients, that content will not appear in content search or eDiscovery after the end of the retention period.</span></span> 
    
<span data-ttu-id="39caf-p150">チームでは、チャットで共有されるファイルが、ファイルを共有したユーザーの OneDrive アカウントに保存されます。チャネルにアップロードされたファイルは、チームの SharePoint 内に保存されます。そのため、チーム内のファイルを保持または削除するには、SharePoint の場所と OneDrive の場所に適用されるアイテム保持ポリシーを作成する必要があります。特定のチームのみのファイルにポリシーを適用する場合は、チーム用の SharePoint サイトおよびチーム内のユーザーの OneDrive アカウントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p150">In a Team, files that are shared in chat are stored in the OneDrive account of the user who shared the file. Files that are uploaded into channels are stored in the SharePoint site for the Team. Therefore, to retain or delete files in a Team, you need to create a retention policy that applies to the SharePoint and OneDrive locations. If you want to apply a policy to the files of just a specific team, you can choose the SharePoint site for the Team and the OneDrive accounts of users in the Team.</span></span>
  
<span data-ttu-id="39caf-311">Teams に適用するアイテム保持ポリシーには、[保持ロック](#locking-a-retention-policy)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="39caf-311">A retention policy that applies to Teams can use [Preservation Lock](#locking-a-retention-policy).</span></span>
  
![チャットおよびチャネル メッセージに対応する Teams の場所](media/127345da-e802-4b3a-afc7-6e354dc3f409.png)
  
## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a><span data-ttu-id="39caf-313">アイテム保持ポリシーから特定の種類の Exchange アイテムを除外する</span><span class="sxs-lookup"><span data-stu-id="39caf-313">Excluding specific types of Exchange items from a retention policy</span></span>
<span data-ttu-id="39caf-p151">PowerShell を使用すると、アイテム保持ポリシーから特定の種類の Exchange アイテムを除外できます。たとえば、メールボックス内のボイスメール メッセージや IM 会話などの Skype for Business Online のコンテンツを除外できます。さらに、予定表、メモ、タスク アイテムを除外することもできます。この機能は、PowerShell を使用してのみ利用できます。アイテム保持ポリシーを作成するときの UI では、この機能を利用できません。</span><span class="sxs-lookup"><span data-stu-id="39caf-p151">By using PowerShell, you can exclude specific types of Exchange items from a retention policy. For example, you can exclude voicemail messages, IM conversations, and other Skype for Business Online content in mailboxes. You can also exclude calendar, note, and task items. This capability is available only by using PowerShell; it's not available in the UI when you create a retention policy.</span></span>
  
<span data-ttu-id="39caf-p152">この操作を行うには、`New-RetentionComplianceRule` および `Set-RetentionComplianceRule` コマンドレットの `ExcludedItemClasses` パラメーターを使用します。PowerShell の詳細については、後述のセクション「[アイテム保持ポリシーの PowerShell コマンドレットを検索する](#find-the-powershell-cmdlets-for-retention-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39caf-p152">To do this, use the  `ExcludedItemClasses` parameter of the  `New-RetentionComplianceRule` and  `Set-RetentionComplianceRule` cmdlets. For more information about PowerShell, see the below section [Find the PowerShell cmdlets for retention policies](#find-the-powershell-cmdlets-for-retention-policies).</span></span>


## <a name="locking-a-retention-policy"></a><span data-ttu-id="39caf-320">アイテム保持ポリシーをロックする</span><span class="sxs-lookup"><span data-stu-id="39caf-320">Locking a retention policy</span></span>
<span data-ttu-id="39caf-p153">一部の組織は、米国証券取引委員会 (SEC) 規則 17a-4 のような規制機関によって定義された規則に準拠する必要があります。その規則には、アイテム保持ポリシーをオンにした後で、そのポリシーをオフにすることや、制限を緩和したりすることが禁止されています。保持ロックを使用すると、管理者を含めて誰もポリシーをオフにしたり、制限を緩和したりできなくなるようにポリシーをロックできます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p153">Some organizations may need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a retention policy is turned on, it cannot be turned off or made less restrictive. With Preservation Lock, you can lock the policy so that no one — including the administrator — can turn off the policy or make it less restrictive.</span></span>
  
<span data-ttu-id="39caf-p154">ポリシーがロックされると、そのポリシーは誰もオフにしたり、無効にしたりできなくなります。また、ポリシーが適用されているコンテンツを保持期間中に変更したり削除したりすることもできません。ポリシーがロックされると、アイテム保持ポリシーには、場所を追加する変更または保持期間を延長する変更のみが可能になります。ロックされたポリシーは増強することができますが、縮小したりオフにしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="39caf-p154">After a policy's been locked, no one can turn it off or remove locations from the policy. And it's not possible to modify or delete content that's subject to the policy during the retention period. After the policy's been locked, the only ways you can modify the retention policy are by adding locations to it or extending its duration. A locked policy can be increased or extended, but it can't be reduced or turned off.</span></span>
  
<span data-ttu-id="39caf-327">そのため、アイテム保持ポリシーをロックする前に、組織のコンプライアンス要件を理解しておくことと、ポリシーのロックが必要であると確信するまでは**ポリシーをロックしない**ことが**非常に重要**になります。</span><span class="sxs-lookup"><span data-stu-id="39caf-327">Therefore, before you lock a retention policy, it's **critical** that you understand your organization's compliance requirements, and that **you do not lock a policy** until you're certain that's what you need.</span></span>

### <a name="lock-a-retention-policy-by-using-powershell"></a><span data-ttu-id="39caf-328">PowerShell を使用してアイテム保持ポリシーをロックする</span><span class="sxs-lookup"><span data-stu-id="39caf-328">Lock a retention policy by using PowerShell</span></span>
  
<span data-ttu-id="39caf-329">アイテム保持ポリシーは、PowerShell を使用してのみロックできます。</span><span class="sxs-lookup"><span data-stu-id="39caf-329">You can lock a retention policy only by using PowerShell.</span></span>

<span data-ttu-id="39caf-330">まず、[Office 365 セキュリティ/コンプライアンス センター PowerShell へ接続します](http://go.microsoft.com/fwlink/p/?LinkID=799771)。</span><span class="sxs-lookup"><span data-stu-id="39caf-330">First, [connect to Office 365 Security & Compliance Center PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=799771).</span></span>

<span data-ttu-id="39caf-331">次に、アイテム保持ポリシーの一覧を表示し、ロックするポリシーの名前を検索し、`Get-RetentionCompliancePolicy` を実行します。</span><span class="sxs-lookup"><span data-stu-id="39caf-331">Second, to view a list of your retention policies and find the name of the policy that you want to lock, run `Get-RetentionCompliancePolicy`.</span></span>

![PowerShell のアイテム保持ポリシーの一覧](media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

<span data-ttu-id="39caf-333">3 番目に、アイテム保持ポリシーの保持ロックを配置するために、`Set-RetentionCompliancePolicy` を実行し、`RestrictiveRetention` パラメーターを true に設定します。たとえば、</span><span class="sxs-lookup"><span data-stu-id="39caf-333">Third, to place a Preservation Lock on the retention policy, run `Set-RetentionCompliancePolicy` with the `RestrictiveRetention` parameter set to true -- for example:</span></span>

`Set-RetentionCompliancePolicy -Identity “<Name of Policy>” – RestrictiveRetention $true`

![PowerShell の RestrictiveRetention パラメーター](media/retention-policy-preservation-lock-restrictiveretention.PNG)

<span data-ttu-id="39caf-p155">そのコマンドレットを実行すると、確認メッセージが表示されます。**[すべてにはい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39caf-p155">After you run that cmdlet, you see a confirmation prompt. Choose **Yes to All**.</span></span>

![PowerShell のアイテム保持ポリシーをロックするかを確認するダイアログ](media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="39caf-p156">アイテム保持ポリシーの保持ロックをが配置されました。`Get-RetentionCompliancePolicy` を実行すると、`RestrictiveRetention` パラメーターは true に設定されます。たとえば、</span><span class="sxs-lookup"><span data-stu-id="39caf-p156">A Preservation Lock is now placed on the retention policy. If you run `Get-RetentionCompliancePolicy`, the `RestrictiveRetention` parameter is set to true -- for example:</span></span>

`Get-RetentionCompliancePolicy -Identity “<Name of Policy>” |Fl`

![PowerShell に表示されるすべてのパラメーターでロックされたポリシー](media/retention-policy-preservation-lock-locked-policy.PNG)
  
## <a name="releasing-a-retention-policy"></a><span data-ttu-id="39caf-341">アイテム保持ポリシーを解除する</span><span class="sxs-lookup"><span data-stu-id="39caf-341">Locking a retention policy</span></span>

<span data-ttu-id="39caf-342">アイテム保持ポリシーはいつでもオフまたは削除できます。</span><span class="sxs-lookup"><span data-stu-id="39caf-342">You can turn off a DLP policy at any time.</span></span> <span data-ttu-id="39caf-343">この操作を行うと、保持されている SharePoint や OneDrive のコンテンツは、すぐには完全に削除されません。</span><span class="sxs-lookup"><span data-stu-id="39caf-343">When you do so, any SharePoint or OneDrive content that's being retained is not immediately and permanently deleted.</span></span> <span data-ttu-id="39caf-344">代わりに、不注意によるデータの損失を防ぐために、30日間の猶予期間があります。そのポリシーのコンテンツの有効期限は、[アイテム保管ライブラリ] には表示されず、必要に応じてコンテンツを復元できます。</span><span class="sxs-lookup"><span data-stu-id="39caf-344">Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed.</span></span> <span data-ttu-id="39caf-345">猶予期間中はアイテム保持ポリシーをもう一度有効にすることもできます。そのポリシーのコンテンツは削除されません。</span><span class="sxs-lookup"><span data-stu-id="39caf-345">You can also turn on the retention policy again during the grace period, and no content will be deleted for that policy.</span></span> <span data-ttu-id="39caf-346">PowerShell を使用して、猶予期間の設定は変更できます。</span><span class="sxs-lookup"><span data-stu-id="39caf-346">This grace period is configurable by using PowerShell.</span></span>

<span data-ttu-id="39caf-347">まず、[Office 365 セキュリティ/コンプライアンス センター PowerShell へ接続](http://go.microsoft.com/fwlink/p/?LinkID=799771) します。</span><span class="sxs-lookup"><span data-stu-id="39caf-347">First, [connect to Office 365 Security & Compliance Center PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=799771).</span></span>

<span data-ttu-id="39caf-348">その後、PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="39caf-348">Then run this PowerShell script.</span></span> <span data-ttu-id="39caf-349">テナントのサブスクリプション設定で、0 から 100 日までの間で`ip_tenantGracePeriodInDays` プロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="39caf-349">You can set `ip_tenantGracePeriodInDays` property in the tenant subscription settings to any value between 0-100 days.</span></span> <span data-ttu-id="39caf-350">これを 0 に設定すると、猶予期間はありません。アイテム保持ポリシーは直ちに解除されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-350">If you set this to 0, there is no grace period, and any retention policy will be released immediately.</span></span> 

`
$siteSubscription = Get-SPSiteSubscription -Identity 
$siteSubScriptionId 
$siteSubSettingsMgr = [Microsoft.SharePoint.SPSiteSubscriptionSettingsManager]::Local
$properties = $siteSubSettingsMgr.GetProperties($siteSubscription)
$properties.SetValue("ip_tenantGracePeriodInDays",  30)
`

<span data-ttu-id="39caf-351">この SharePoint と OneDrive の 30 日の猶予期間は、Exchange の 30 日の保留期間に対応しています。</span><span class="sxs-lookup"><span data-stu-id="39caf-351">This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange.</span></span> <span data-ttu-id="39caf-352">詳しくは、[メールボックスの管理についての詳細](https://docs.microsoft.com/ja-JP/office365/securitycompliance/identify-a-hold-on-an-exchange-online-mailbox#managing-mailboxes-on-delay-hold) をご覧ください。。</span><span class="sxs-lookup"><span data-stu-id="39caf-352">For more information, see [Place all mailboxes on hold](https://docs.microsoft.com/en-us/office365/securitycompliance/identify-a-hold-on-an-exchange-online-mailbox#managing-mailboxes-on-delay-hold).</span></span>

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="39caf-353">保持の原則、すなわち優先順位について</span><span class="sxs-lookup"><span data-stu-id="39caf-353">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="39caf-p160">コンテンツには複数のアイテム保持ポリシーが適用され、各ポリシーに異なるアクション (保持または削除、あるいはその両方) と保持期間が設定されている場合が多くあります。どれが優先されるのでしょうか? 概ね、あるポリシーで保持されているコンテンツを別のポリシーで完全に削除することはできないので、ご安心ください。</span><span class="sxs-lookup"><span data-stu-id="39caf-p160">It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or both) and retention period. What takes precedence? At the highest level, rest assured that content being retained by one policy can't be permanently deleted by another policy.</span></span>
  
![保持の原則の図](media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="39caf-358">さまざまなアイテム保持ポリシーが、どのようにコンテンツに適用されるかを理解するために、次に示す保持の原則を覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="39caf-358">To understand how different retention policies are applied to content, keep these principles of retention in mind:</span></span>
  
1. <span data-ttu-id="39caf-p161">**保持は削除よりも優先されます。** たとえば、Exchange 電子メールを 3 年後に削除するアイテム保持ポリシーと、Exchange 電子メールを 5 年間保持した後に削除するアイテム保持ポリシーがあるとします。この場合、3 年を経過したコンテンツはすべて削除されてユーザーには表示されなくなりますが、[回復可能なアイテム] フォルダーに保持され、5 年経過したときに完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p161">**Retention wins over deletion.** Suppose that one retention policy says to delete Exchange email after three years, but another retention policy says to retain Exchange email for five years and then delete it. Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it will be permanently deleted.</span></span> 
    
2. <span data-ttu-id="39caf-p162">**最長の保持期間が優先されます。** コンテンツを保持する複数のポリシーの対象となるコンテンツは、最長の保持期間が終了するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p162">**The longest retention period wins.** If content's subject to multiple policies that retain content, it will be retained until the end of the longest retention period.</span></span> 
    
3. <span data-ttu-id="39caf-p163">**明示的な包含は暗黙的な包含に優先します。** これは次を意味します。</span><span class="sxs-lookup"><span data-stu-id="39caf-p163">**Explicit inclusion wins over implicit inclusion.** This means:</span></span> 
    
    1. <span data-ttu-id="39caf-p164">保持設定を持つラベルをユーザーが Exchange メールや OneDrive ドキュメントなどのアイテムに手動で割り当てると、そのラベルはサイト レベルまたはメールボックス レベルで割り当てられたポリシー、およびドキュメント ライブラリによって割り当てられた既定のラベルよりも優先されます。たとえば、明示的なラベルで 10 年間保持するように設定されているときに、サイトに割り当てられたポリシーでは 5 年間のみ保持するように設定されている場合は、ラベルが優先されます。自動適用ラベルは、Office 365 によって自動的に適用されるため、明示的ではなく暗黙的に指定されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p164">If a label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that label takes precedence over both a policy assigned at the site or mailbox level and a default label assigned by the document library. For example, if the explicit label says to retain for ten years, but the policy assigned to the site says to retain for only five years, the label takes precedence. Note that auto-apply labels are considered implicit, not explicit, because they're applied automatically by Office 365.</span></span>
    
    2. <span data-ttu-id="39caf-369">アイテム保持ポリシーに特定のユーザーのメールボックスまたは OneDrive for Business のアカウントなどの特定の場所が含まれている場合、そのポリシーは、すべてのユーザーのメールボックスまたは OneDrive for Business のアカウントに適用されるが、そのユーザーのメールボックスを特に含まない別の保持ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-369">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive for Business account, that policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive for Business accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="39caf-p165">**最短の削除期間が優先されます。** 同様に、コンテンツを削除する複数のポリシー (保持なし) の対象となるコンテンツは、最短保持期間の終了時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="39caf-p165">**The shortest deletion period wins.** Similarly, if content's subject to multiple policies that delete content (with no retention), it will be deleted at the end of the shortest retention period.</span></span> 
    
<span data-ttu-id="39caf-372">保持の原則は上位から下位のタイブレーク フローとして機能することを理解します。すべてのポリシーまたはラベルによって適用された複数のルールがあるレベルで同じ場合、フローは次の下位レベルに移動し、ルールが適用される優先順位を決定します。</span><span class="sxs-lookup"><span data-stu-id="39caf-372">Understand that the principles of retention work as a tie-breaking flow from top to bottom: If the rules applied by all policies or labels are the same at one level, the flow moves down to the next level to determine precedence for which rule is applied.</span></span>
  
<span data-ttu-id="39caf-p166">最後に、アイテム保持ポリシーまたはラベルでは、電子情報開示のために保留中のコンテンツを完全に削除することはできません。保留が解除されると、コンテンツは再び上記に記載されたクリーンアップ プロセスの対象となります。</span><span class="sxs-lookup"><span data-stu-id="39caf-p166">Finally, a retention policy or label cannot permanently delete any content that's on hold for eDiscovery. When the hold is released, the content again becomes eligible for the cleanup process described above.</span></span>
  
## <a name="use-a-retention-policy-instead-of-these-features"></a><span data-ttu-id="39caf-375">別の機能の代わりにアイテム保持ポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="39caf-375">Use a retention policy instead of these features</span></span>

<span data-ttu-id="39caf-p167">1 つのアイテム保持ポリシーは、組織全体や Office 365 のすべての場所 (Exchange Online、SharePoint Online、OneDrive for Business、Office 365 グループなど) に簡単に適用できます。Office 365 のいずれかの場所にあるコンテンツを保持または削除する必要がある場合は、アイテム保持ポリシーの使用をお勧めします (保持設定付きのラベルを使用することもできます。詳細については、「[ラベルの概要](labels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="39caf-p167">A single retention policy can easily apply to an entire organization and locations across Office 365, including Exchange Online, SharePoint Online, OneDrive for Business, and Office 365 groups. If you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy. (You can also use labels with retention settings - for more information, see [Overview of labels](labels.md).)</span></span>
  
<span data-ttu-id="39caf-379">Office 365 のコンテンツを保持または削除するために以前使用されていた別の機能がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="39caf-379">There are several other features that have previously been used to retain or delete content in Office 365.</span></span> <span data-ttu-id="39caf-380">その一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="39caf-380">These are listed below.</span></span> <span data-ttu-id="39caf-381">これらの機能は、保持ポリシーおよび保持ラベルと共存して引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="39caf-381">These features will continue to work side by side with retention policies and retention labels.</span></span> <span data-ttu-id="39caf-382">ただし、データ ガバナンスについては、今後、これらの機能ではなく、アイテム保持ポリシーまたはラベルの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39caf-382">But moving forward, for data governance, we recommend that you use a retention policy or labels instead of all of these features.</span></span> <span data-ttu-id="39caf-383">アイテム保持ポリシーのみ、Office 365 全体でコンテンツの保持と削除の両方を行えます。</span><span class="sxs-lookup"><span data-stu-id="39caf-383">A retention policy is the only feature that can both retain and delete content across Office 365.</span></span>
  
### <a name="exchange-online"></a><span data-ttu-id="39caf-384">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="39caf-384">Exchange Online</span></span>

- <span data-ttu-id="39caf-385">[Office 365 のセキュリティ センター/コンプライアンス センターでの電子情報開示のケースの管理](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) (電子情報開示の保留リスト)</span><span class="sxs-lookup"><span data-stu-id="39caf-385">[Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) (eDiscovery hold)</span></span> 
    
- <span data-ttu-id="39caf-386">[インプレース ホールドと訴訟ホールド](https://go.microsoft.com/fwlink/?linkid=846124) (電子情報開示の保留リスト)</span><span class="sxs-lookup"><span data-stu-id="39caf-386">[In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/?linkid=846124) (eDiscovery hold)</span></span> 
    
- <span data-ttu-id="39caf-387">[保持タグおよびアイテム保持ポリシー](https://go.microsoft.com/fwlink/?linkid=846125)。[メッセージング レコード管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) とも呼ばれます (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="39caf-387">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (Deletion only)</span></span> 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="39caf-388">Sharepoint Online と OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="39caf-388">SharePoint Online and OneDrive for Business</span></span>

- <span data-ttu-id="39caf-389">[Office 365 のセキュリティ センター/コンプライアンス センターでの電子情報開示のケースの管理](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) (電子情報開示の保留リスト)</span><span class="sxs-lookup"><span data-stu-id="39caf-389">[Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) (eDiscovery hold)</span></span> 
    
- <span data-ttu-id="39caf-390">[電子情報開示センターでのコンテンツのケースへの追加とソースの保留リストへの配置](https://support.office.com/article/54d70de9-1ec2-4325-84f3-aeb588554479) (電子情報開示の保留リスト)</span><span class="sxs-lookup"><span data-stu-id="39caf-390">[Add content to a case and place sources on hold in the eDiscovery Center](https://support.office.com/article/54d70de9-1ec2-4325-84f3-aeb588554479) (eDiscovery hold)</span></span> 
    
- <span data-ttu-id="39caf-391">[ドキュメント削除ポリシーの概要](https://support.office.com/article/55e8d858-f278-482b-a198-2e62d6a2e6e5) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="39caf-391">[Overview of document deletion policies](https://support.office.com/article/55e8d858-f278-482b-a198-2e62d6a2e6e5) (Deletion only)</span></span> 
    
- <span data-ttu-id="39caf-392">[インプレース レコード管理の構成](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保持)</span><span class="sxs-lookup"><span data-stu-id="39caf-392">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (Retention)</span></span> 
    
- <span data-ttu-id="39caf-393">[サイトのクローズと削除のポリシーを使用する](https://support.office.com/article/a8280d82-27fd-48c5-9adf-8a5431208ba5) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="39caf-393">[Use policies for site closure and deletion](https://support.office.com/article/a8280d82-27fd-48c5-9adf-8a5431208ba5) (Deletion only)</span></span> 
    
- <span data-ttu-id="39caf-394">[情報管理ポリシー](intro-to-info-mgmt-policies.md) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="39caf-394">[Information management policies](intro-to-info-mgmt-policies.md) (Deletion only)</span></span> 
    
<span data-ttu-id="39caf-395">これまでにデータ ガバナンスの目的で電子情報開示の保留のいずれかを使用していた場合は、将来に向けて法令を遵守するためにアイテム保持ポリシーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39caf-395">Note that if you've previously used any of the eDiscovery holds for the purpose of data governance, you should instead use a retention policy for proactive compliance.</span></span> <span data-ttu-id="39caf-396">保留は電子情報開示にのみ使用するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="39caf-396">You should use a hold only for eDiscovery.</span></span>
  
### <a name="retention-policies-override-information-management-policies"></a><span data-ttu-id="39caf-397">アイテム保護ポリシーによる情報管理ポリシーの上書き</span><span class="sxs-lookup"><span data-stu-id="39caf-397">Retention policies override information management policies</span></span>

<span data-ttu-id="39caf-398">SharePoint のサイトでは、[情報管理ポリシー](intro-to-info-mgmt-policies.md)を使用してコンテンツを保持している場合があります。</span><span class="sxs-lookup"><span data-stu-id="39caf-398">In SharePoint sites, you may be using [information management policies](intro-to-info-mgmt-policies.md) to retain content.</span></span> <span data-ttu-id="39caf-399">リストまたはライブラリに対してコンテンツ タイプ ポリシーまたは情報管理ポリシーを既に使用しているサイトに、保持ポリシーを適用すると、前者のポリシーは無視され、保持ポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="39caf-399">If you apply a retention policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the retention policy is in effect.</span></span> 
  
## <a name="what-happened-to-preservation-policies"></a><span data-ttu-id="39caf-400">保持ポリシーの変更点</span><span class="sxs-lookup"><span data-stu-id="39caf-400">What happened to preservation policies?</span></span>

<span data-ttu-id="39caf-401">保持ポリシーを使用していた場合、そのポリシーは自動的にアイテム保持ポリシーに変換されます。このポリシーは保持操作にのみ使用され、コンテンツを削除することはありません。</span><span class="sxs-lookup"><span data-stu-id="39caf-401">If you were using a preservation policy, that policy has been automatically converted to a retention policy that uses only the retain action - the policy won't delete content.</span></span> <span data-ttu-id="39caf-402">保持ポリシーは、引き続き機能してコンテンツを保持します。ユーザーが変更を加える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="39caf-402">The preservation policy will continue to work and preserve your content without requiring any changes from you.</span></span> <span data-ttu-id="39caf-403">こうしたポリシーは、Microsoft 365 コンプライアンス センターの **[ポリシー]** ページか、セキュリティ/コンプライアンス センターの **[データ ガバナンス]** にある **[保持]** ページで検索できます。</span><span class="sxs-lookup"><span data-stu-id="39caf-403">You can find these policies on the **Policies** page in the Microsoft 365 compliance center, or on the **Retention** page under **Data governance** in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="39caf-404">保持ポリシーを編集して保持期間を変更することはできますが、それ以外の変更 (場所の追加や削除など) はできません。</span><span class="sxs-lookup"><span data-stu-id="39caf-404">You can edit a preservation policy to change the retention period, but you can't make other changes, such as adding or removing locations.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="39caf-405">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="39caf-405">Permissions</span></span>

<span data-ttu-id="39caf-p172">アイテム保持ポリシーを作成するコンプライアンス チームのメンバーには、セキュリティ/コンプライアンス センターへのアクセス許可が必要です。既定では、テナント管理者はこの場所へのアクセス許可を持っています。そのため、法令遵守責任者や他のユーザーに対し、テナント管理者のすべてのアクセス許可を付与せずに、セキュリティ/コンプライアンス センターへのアクセスを許可できます。これを行うには、セキュリティ/コンプライアンス センターの **[アクセス許可]** ページに移動して、**[コンプライアンス管理者]** 役割グループを編集し、メンバーをその役割グループに追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39caf-p172">Members of your compliance team who will create retention policies need permissions to the Security &amp; Compliance Center. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="39caf-408">詳細については、「[ユーザーに Office 365 セキュリティ センター/コンプライアンス センターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39caf-408">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="39caf-p173">これらのアクセス許可は、アイテム保持ポリシーを作成して適用するためにのみ必要です。ポリシーを適用するために、コンテンツへのアクセスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="39caf-p173">These permissions are required only to create and apply a retention policy. Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-powershell-cmdlets-for-retention-policies"></a><span data-ttu-id="39caf-411">アイテム保持ポリシーの PowerShell コマンドレットを検索する</span><span class="sxs-lookup"><span data-stu-id="39caf-411">Find the PowerShell cmdlets for retention policies</span></span>

<span data-ttu-id="39caf-412">アイテム保持ポリシーのコマンドレットを使用するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="39caf-412">To use the retention policy cmdlets, you need to:</span></span>
  
1. [<span data-ttu-id="39caf-413">リモート PowerShell を使用して Office 365 セキュリティ/コンプライアンス センターに接続する</span><span class="sxs-lookup"><span data-stu-id="39caf-413">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="39caf-414">[Office 365 セキュリティ/コンプライアンス センターのコマンドレット](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)を使用する</span><span class="sxs-lookup"><span data-stu-id="39caf-414">Use these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
## <a name="more-information"></a><span data-ttu-id="39caf-415">詳細情報</span><span class="sxs-lookup"><span data-stu-id="39caf-415">More information</span></span>

- [<span data-ttu-id="39caf-416">ラベルの概要</span><span class="sxs-lookup"><span data-stu-id="39caf-416">Overview of labels</span></span>](labels.md)
    

