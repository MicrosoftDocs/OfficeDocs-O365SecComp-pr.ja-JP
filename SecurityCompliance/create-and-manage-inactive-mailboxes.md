---
title: 作成し、Office 365 の非アクティブなメールボックスの管理
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
description: 保留または Office 365 のリテンション ・ ポリシーをメールボックスに適用して、対応する Office 365 ユーザー アカウントを削除し、Office 365 で、非アクティブなメールボックスを作成できます。適用されて非アクティブにされる前に、保留中または保存ポリシーの期間中、非アクティブなメールボックス内のアイテムが保持されます。非アクティブなメールボックスを完全に削除するには、だけで、保留中または保持ポリシーを削除します。
ms.openlocfilehash: de67068ded30f63e46a8a94c1030d45a12b56a2e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29740839"
---
# <a name="create-and-manage-inactive-mailboxes-in-office-365"></a><span data-ttu-id="c5dd4-105">作成し、Office 365 の非アクティブなメールボックスの管理</span><span class="sxs-lookup"><span data-stu-id="c5dd4-105">Create and manage inactive mailboxes in Office 365</span></span>

<span data-ttu-id="c5dd4-p102">Office 365 では、削除済みメールボックスの内容を保持できます。この機能は、[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)と呼ばれます。非アクティブなメールボックスを使用すると、組織を離れた後に退職した従業員の電子メールを保持できます。証拠の保全または Office 365 のリテンション ・ ポリシーとメールボックスを非アクティブになります (Office 365 のセキュリティで作成された&amp;コンプライアンス センター) は、対応する Office 365 ユーザー アカウントが削除される前に、メールボックスに適用します。非アクティブにされる前に、メールボックスに格納された保留リストの中に、非アクティブなメールボックスの内容が保持されます。これにより、レコードの管理者、およびコンプライアンス責任者、マネージャー、セキュリティでのコンテンツの検索を使用する&amp;コンプライアンス ・ センターを検索し、非アクティブなメールボックスの内容をエクスポートします。非アクティブなメールボックスはメールを受信できないし、組織の共有アドレス帳またはその他のリストに表示されていません。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p102">Office 365 makes it possible for you to retain the contents of deleted mailboxes. This feature is called [inactive mailboxes](inactive-mailboxes-in-office-365.md). Inactive mailboxes allow you to retain former employees' email after they leave your organization. A mailbox becomes inactive when a Litigation Hold or an Office 365 retention policy (created in the Office 365 Security &amp; Compliance Center) is applied to the mailbox before the corresponding Office 365 user account is deleted. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. This allows administrators, compliance officers, and records managers to use Content Search in the Security &amp; Compliance Center to search and export the contents of an inactive mailbox. Inactive mailboxes can't receive email and aren't displayed in your organization's shared address book or other lists.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c5dd4-p103">2017 年 7 月 1 日に終了する予定だった、メールボックスを非アクティブにするために新しいインプレース ホールドを作成できる期間を延長しました。しかし、今年の終わりごろまたは来年の初めごろには、新しいインプレース ホールドを Exchange Online 内で作成することはできなくなります。その時点で、非アクティブのメールボックスを作成するために使用できるのは、訴訟ホールドと Office 365 アイテム保持ポリシーだけになります。ただし、インプレース ホールドにある既存の非アクティブなメールボックスは引き続きサポートされます。また、引き続き非アクティブなメールボックスのインプレース ホールドを管理することができます。これには、インプレース ホールドの期間を変更すること、およびそのインプレース ホールドを削除することによって非アクティブなメールボックスを完全に削除することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="c5dd4-118">始める前に</span><span class="sxs-lookup"><span data-stu-id="c5dd4-118">Before you begin</span></span>

- <span data-ttu-id="c5dd4-p104">メールボックスを非アクティブにするに割り当てる必要があります Exchange オンライン計画 2 ライセンス、証拠保全、または Office 365 のリテンション ・ ポリシーに適用する、メールボックスが削除される前にできるようにします。Exchange オンライン計画 2 ライセンスは、Office 365 エンタープライズ E3、E5 のサブスクリプションの一部です。メールボックスが、Exchange のオンライン計画 1 ライセンス (Office 365 のエンタープライズ E1 サブスクリプションの一部である) を割り当てられている場合は、割り当てる Exchange Online Archiving の個別のライセンスが削除される前に、メールボックスに保留を適用できるようにする必要があります。詳細については、 [Exchange Online Archiving](https://go.microsoft.com/fwlink/p/?LinkId=286153)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p104">To make a mailbox inactive, it must be assigned an Exchange Online Plan 2 license so that a Litigation Hold or an Office 365 retention policy can be applied to the mailbox before it's deleted. Exchange Online Plan 2 licenses are part of an Office 365 Enterprise E3 and E5 subscriptions. If a mailbox is assigned an Exchange Online Plan 1 license (which is part of an Office 365 Enterprise E1 subscription), you would have to assign it a separate Exchange Online Archiving license so that a hold can be applied to the mailbox before it's deleted. For more information, see [Exchange Online Archiving](https://go.microsoft.com/fwlink/p/?LinkId=286153).</span></span>
    
- <span data-ttu-id="c5dd4-p105">対応する Office 365 ユーザー アカウントを削除した後、削除された Exchange Online メールボックスに関連付けられているライセンスが提供されます。できますし、[ビジネス向けの Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)別のユーザーにします。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p105">The license associated with the deleted Exchange Online mailbox will be available after you delete the corresponding Office 365 user account. You can then [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) to another user.</span></span> 
    
- <span data-ttu-id="c5dd4-p106">メールボックスを削除する前に訴訟ホールドまたは Office 365 アイテム保持ポリシーを適用しなかった場合は、メールボックスの内容が保持されず、検索もできません。なお、削除されたメールボックスは、削除後 30 日以内であれば回復できますが、回復されない場合、メールボックスとその内容は 30 日後に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p106">If a Litigation Hold or an Office 365 retention policy isn't applied to a mailbox before it's deleted, the contents of the mailbox won't be retained or discoverable. However, the deleted mailbox can be recovered within 30 days of deletion, but the mailbox and its contents will be permanently deleted after 30 days if it isn't recovered.</span></span>
    
- <span data-ttu-id="c5dd4-p107">証拠保全に関する詳細については、[インプレース保持、訴訟](https://go.microsoft.com/fwlink/p/?LinkId=846124)を参照してください。セキュリティで保存ポリシーを Office 365 の詳細については&amp;コンプライアンス センターでは、 [Office 365 のリテンション ・ ポリシーの概要](retention-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p107">For more information about Litigation Hold, see [In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=846124). For more information about Office 365 retention policies in the Security &amp; Compliance Center, see [Overview of retention policies in Office 365](retention-policies.md).</span></span>
  
## <a name="create-an-inactive-mailbox"></a><span data-ttu-id="c5dd4-129">非アクティブなメールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-129">Create an inactive mailbox</span></span>

<span data-ttu-id="c5dd4-p108">2 つの手順では、メールボックスを非アクティブにする: 1) メールボックスを配置すること証拠保全または Office 365 のリテンション ・ ポリシーを適用して 2)、メールボックスを削除するのにまたは対応する Office 365 ユーザー アカウントです。後、メールボックスがアクティブではありません、保持、または保持ポリシーが削除されるまでその内容が保持されます。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p108">Making a mailbox inactive involves two steps: 1) placing the mailbox on Litigation Hold or applying an Office 365 retention policy to it, and 2) deleting the mailbox or corresponding Office 365 user account. After the mailbox is inactive, its contents are retained until the hold or retention policy is removed.</span></span>
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-an-office-365-retention-policy"></a><span data-ttu-id="c5dd4-132">手順 1:メールボックスを訴訟ホールドの対象にするか、Office 365 アイテム保持ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="c5dd4-132">Step 1: Place a mailbox on Litigation Hold or apply an Office 365 retention policy</span></span>

<span data-ttu-id="c5dd4-p109">メールボックスを訴訟ホールドの対象にするか、Office 365 アイテム保持ポリシーを適用すると、メールボックスが削除される前に、その中のすべての内容が保持されます。どちらの種類の保持も、削除済みアイテムや変更されたアイテムの元のバージョンなど、すべてのメールボックスのコンテンツを保持します。削除または変更されたアイテムは、指定された期間、または非アクティブなメールボックスに適用されているホールドまたは保持ポリシーを除去することによって完全に非アクティブなメールボックスを削除するまで、非アクティブなメールボックスに保持されます。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p109">Placing a mailbox on Litigation Hold or applying an Office 365 retention policy retains the contents in the mailbox before it's deleted. Both types of holds will retain all mailbox content, including deleted items and original versions of modified items. Deleted and modified items are retained in the inactive mailbox for a specified period, or until you permanently delete the inactive mailbox by removing the hold or retention policy that's applied to the inactive mailbox.</span></span>
  
<span data-ttu-id="c5dd4-136">メールボックスが既にホールドの対象になっている場合や、Office 365 アイテム保持ポリシーがメールボックスに既に適用されている場合に行う必要があるのは、手順 2 で説明されているように、対応する Office 365 ユーザー アカウントを削除することだけです。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-136">If a hold is already placed on a mailbox, or if an Office 365 retention policy is already applied to a mailbox, then all you have to do is delete the corresponding Office 365 user account as explained in Step 2.</span></span>
  
<span data-ttu-id="c5dd4-137">メールボックスを訴訟ホールドの対象にするため、または Office 365 アイテム保持ポリシーを適用するためのステップごとの手順については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-137">For step-by-step procedures for placing a mailbox on Litigation Hold or applying an Office 365 retention policy, see:</span></span>
  
- [<span data-ttu-id="c5dd4-138">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="c5dd4-138">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [<span data-ttu-id="c5dd4-139">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="c5dd4-139">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
> [!NOTE]
> <span data-ttu-id="c5dd4-p110">訴訟ホールドと Office 365 アイテム保持ポリシーでは、無期限のホールドまたは時間ベースのホールドを作成できます。無期限のホールドでは、非アクティブなメールボックスの内容が永久に保持されるか、またはそのホールドが除去されるかホールド期間が変更されるまで保持されます。ホールドまたはアイテム保持ポリシーを解除すると、非アクティブなメールボックスは完全な削除対象としてマークされ、メールボックスの内容は保持されなくなり、検索もできなくなります (メールボックスは 30 日より前に削除されていることを前提とします)。時間ベースのホールドまたは Office 365 アイテム保持ポリシーでは、ホールド期間を指定します。この期間は、アイテム ベースで、メールボックス アイテムが受信または作成された日から計算されます。メールボックス アイテムのホールド期間が切れると、そのアイテムが非アクティブなメールボックスの [回復可能なアイテム] フォルダーにあるかそこに移動された場合、そのアイテムは削除済みアイテム保持期間が切れた後に非アクティブなメールボックスから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p110">For Litigation Holds and Office 365 retention policies, you can create an indefinite hold or on a time-based hold. In an indefinite hold, the contents of the inactive mailbox will be retained forever, or until the hold is removed or until the hold duration is changed. After the hold or retention policy is removed (assuming that the mailbox was deleted more than 30 days ago), the inactive mailbox will be marked for permanent deletion and the contents of the mailbox will no longer be retained or discoverable. In a time-based hold or Office 365 retention policy, you specify the duration of the hold. This duration is on a per-item basis and is calculated from the date a mailbox item was received or created. After the hold expires for a mailbox item, and that item moved to or is located in the Recoverable Items folder in the inactive mailbox, the item is permanently deleted (purged) from the inactive mailbox after the deleted item retention period expires.</span></span> 
  
### <a name="step-2-delete-the-mailbox"></a><span data-ttu-id="c5dd4-146">手順 2:メールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="c5dd4-146">Step 2: Delete the mailbox</span></span>

<span data-ttu-id="c5dd4-p111">保留中のメールボックスが配置された、または Office 365 のリテンション ・ ポリシーが適用されること、次の手順、メールボックスを削除します。メールボックスを削除する最善の方法は、Office 365 の管理センターでの対応する Office 365 ユーザー アカウントを削除するのには。Office 365 ユーザー アカウントを削除する方法の詳細については、[組織からユーザーを削除する](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p111">After the mailbox is placed on hold or an Office 365 retention policy is applied to it, the next step is to delete the mailbox. The best way to delete a mailbox is to delete the corresponding Office 365 user account in the Office 365 admin center. For information about deleting Office 365 user accounts, see [Delete a user from your organization](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c5dd4-p112">Exchange オンライン PowerShell の**削除メールボックス**コマンドレットを使用してメールボックスを削除することもできます。詳細については、[削除するかオンライン Exchange ユーザーのメールボックスの復元](https://go.microsoft.com/fwlink/?linkid=856287)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p112">You can also delete the mailbox by using the **Remove-Mailbox** cmdlet in Exchange Online PowerShell. For more information, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287).</span></span> 
  

## <a name="view-a-list-of-inactive-mailboxes"></a><span data-ttu-id="c5dd4-152">非アクティブなメールボックスの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-152">View a list of inactive mailboxes</span></span>


<span data-ttu-id="c5dd4-153">組織内の非アクティブなメールボックスの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-153">To view a list of the inactive mailboxes in your organization:</span></span>
  
1. <span data-ttu-id="c5dd4-154">[https://protection.office.com/](https://protection.office.com/)し、組織の Office 365 の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-154">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="c5dd4-155">セキュリティの左側のウィンドウで&amp;コンプライアンス センターでは、**データの管理**をクリックして\>\* \* 保存 \* \*。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-155">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> \*\* Retention \*\*.</span></span>
    
3. <span data-ttu-id="c5dd4-156">[**保存**] ページで [**詳細**] をクリックして![・ ナビゲーション ・ バーの省略記号](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)、し、[**非アクティブなメールボックス**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-156">On the **Retention** page, click **More**![Navigation Bar ellipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif), and then click **Inactive mailboxes**.</span></span>
    
    ![保存期間] ページで、[詳細] をクリックし、非アクティブなメールボックスの一覧を表示する非アクティブなメールボックスをクリックし、](media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    <span data-ttu-id="c5dd4-p113">**メールボックスがアクティブでない**ページが表示されます。注組織内の非アクティブなメールボックスの合計数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p113">The **Inactive mailboxes** page is displayed. Note the total number of inactive mailboxes in your organization is displayed.</span></span> 
    
    ![組織内のすべての非アクティブなメールボックスの一覧が表示されます。](media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
<span data-ttu-id="c5dd4-161">または、オンラインで実行できる次のコマンドで Exchange PowerShell を非アクティブなメールボックスの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-161">Alternatively, you can run the following command in Exchange Online PowerShell to display the list of inactive mailboxes.</span></span>

```
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

<span data-ttu-id="c5dd4-162">をクリックすることができます![エクスポートの検索結果のアイコン](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)に**エクスポート**を表示または組織内の非アクティブなメールボックスに関する追加情報を含む CSV ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-162">You can click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Export** to view or download a CSV file that contains additional information about the inactive mailboxes in your organization.</span></span> 
  
<span data-ttu-id="c5dd4-p114">非アクティブなメールボックスの一覧およびその他の情報を CSV ファイルにエクスポートするのには次のコマンドを実行することもできます。この例では、CSV ファイルが現在のディレクトリに作成されます。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p114">You can also run the following command to export the list of inactive mailboxes and other information to a CSV file. In this example, the CSV file is created in the current directory.</span></span>

```
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```
   
> [!NOTE]
> <span data-ttu-id="c5dd4-p115">非アクティブなメールボックスがアクティブなユーザーのメールボックスと同じ SMTP アドレスをいる可能性があることができます。この例では、非アクティブなメールボックスを一意に識別する**識別名**または**ExchangeGuid**プロパティの値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p115">It's possible that an inactive mailbox may have the same SMTP address as an active user mailbox. In this case, the value of the **DistinguishedName** or **ExchangeGuid** property can be used to uniquely identify an inactive mailbox.</span></span> 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a><span data-ttu-id="c5dd4-167">非アクティブなメールボックスのコンテンツを検索し、エクスポートする</span><span class="sxs-lookup"><span data-stu-id="c5dd4-167">Search and export the contents of an inactive mailbox</span></span>

<span data-ttu-id="c5dd4-p116">セキュリティ コンテンツの検索ツールを使用して非アクティブなメールボックスの内容にアクセスすることができます&amp;コンプライアンス センターです。アクティブでないメールボックスを検索すると、特定の項目を検索するキーワードの検索クエリを作成することができます。 または非アクティブなメールボックスの内容全体を返すことができます。検索結果をプレビューするか、個々 の電子メール メッセージ、Outlook のデータ (PST) ファイルには、検索結果をエクスポートできます。メールボックスを検索し、検索結果のエクスポートの詳細な手順は、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p116">You can access the contents of the inactive mailbox by using the Content Search tool in the Security &amp; Compliance Center. When you search an inactive mailbox, you can create a keyword search query to search for specific items or you can return the entire contents of the inactive mailbox. You can preview the search results or export the search results to an Outlook Data (PST) file or as individual email messages. For step-by-step procedures for searching mailboxes and exporting search results, see the following topics:</span></span>
  
- [<span data-ttu-id="c5dd4-172">Office 365 でのコンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="c5dd4-172">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="c5dd4-173">Office 365 のセキュリティ コンテンツの検索結果をエクスポートする&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="c5dd4-173">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
<span data-ttu-id="c5dd4-174">非アクティブなメールボックスを検索するときに留意する点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-174">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>
  
- <span data-ttu-id="c5dd4-175">コンテンツの検索には、ユーザーのメールボックスが含まれていて、そのメールボックスが無効になりましたが、コンテンツの検索が引き続き非アクティブにした後再度検索を実行すると、アクティブでないメールボックスを検索します。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-175">If a content search includes a user mailbox and that mailbox is then made inactive, the content search will continue to search the inactive mailbox when you re-run the search after it becomes inactive.</span></span>
    
- <span data-ttu-id="c5dd4-p117">いくつかの場合、ユーザーは、アクティブなメールボックスと同じ SMTP アドレスを持つ、非アクティブなメールボックスがあります。この例では、コンテンツの検索場所として選択した特定のメールボックスのみが検索されます。つまり、検索するには、ユーザーのメールボックスを追加する場合があると、ことは、両方のアクティブおよび非アクティブなメールボックスが検索されます。検索を明示的に追加するメールボックスのみが検索されます。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p117">In some cases, a user may have an active mailbox and an inactive mailbox that have the same SMTP address. In this case, only the specific mailbox that you select as a location for a content search will be searched. In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes will be searched; only the mailbox that you explicitly add to the search will be searched.</span></span>
    
- <span data-ttu-id="c5dd4-p118">アクティブなメールボックスと同じ SMTP アドレスを持つメールボックスを非アクティブすることを避けることを強くお勧めします。非アクティブなメールボックスに現在割り当てられている SMTP アドレスを再利用する場合をお勧めアクティブでないメールボックスを回復またはアクティブなメールボックス (またはアクティブなメールボックスのアーカイブ) では、非アクティブなメールボックスの内容を復元しているし、削除します非アクティブなメールボックスです。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p118">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address. If you need to reuse the SMTP address that is currently assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox.</span></span>
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="c5dd4-181">非アクティブなメールボックスの保持期間を変更する</span><span class="sxs-lookup"><span data-stu-id="c5dd4-181">Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="c5dd4-p119">メールボックスを無効になりましたが後、は、保留、または非アクティブなメールボックスに適用される Office 365 の保持ポリシーの期間を変更できます。手順は、 [Office 365 での非アクティブなメールボックスの保持期間の変更](change-the-hold-duration-for-an-inactive-mailbox.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p119">After a mailbox is made inactive, you can change the duration of the hold or the Office 365 retention policy applied to the inactive mailbox. For step-by-step procedures, see [Change the hold duration for an inactive mailbox in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).</span></span>
  
## <a name="recover-an-inactive-mailbox"></a><span data-ttu-id="c5dd4-184">非アクティブなメールボックスを回復する</span><span class="sxs-lookup"><span data-stu-id="c5dd4-184">Recover an inactive mailbox</span></span>

<span data-ttu-id="c5dd4-p120">組織では、元従業員が返された場合、またはゲーム終了者の従業員の業務上の責任で実行する新しい従業員が採用された場合は、非アクティブなメールボックスの内容を回復できます。アクティブでないメールボックスをリカバリする場合は、メールボックスを新しいメールボックスに変換され、内容と非アクティブなメールボックスのフォルダー構造は保持されますが、メールボックスを新しいユーザー アカウントにリンクします。を修復した後、非アクティブなメールボックスは存在しません。詳細な手順と詳細については、非アクティブなメールボックスを回復するときの動作、 [Office 365 で、非アクティブなメールボックスのリカバリ](recover-an-inactive-mailbox.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p120">If a former employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox. When you recover an inactive mailbox, the mailbox is converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists. For step-by-step procedures and more information about happens when you recover an inactive mailbox, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a><span data-ttu-id="c5dd4-189">非アクティブなメールボックスのコンテンツを別のメールボックスに復元する</span><span class="sxs-lookup"><span data-stu-id="c5dd4-189">Restore the contents of an inactive mailbox to another mailbox</span></span>

<span data-ttu-id="c5dd4-p121">別の従業員には、以前の社員の職務内容や、他のユーザーが非アクティブなメールボックスの内容へのアクセスを必要とする場合、することができます復元 (またはマージ) 使用頻度の低い既存のメールボックスにメールボックスの内容。アクティブでないメールボックスを復元する場合は、内容が別のメールボックスにコピーされます。非アクティブなメールボックスが保持され、非アクティブなメールボックスのままです。非アクティブなメールボックスは電子的証拠開示検索することができます、別のメールボックスにその内容を復元することができます、またはリカバリまたは後で削除できます。手順は、 [Office 365 で、非アクティブなメールボックスの復元](restore-an-inactive-mailbox.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p121">If another employee takes on the job responsibilities of a former employee, or if another person needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. When you restore an inactive mailbox, the contents are copied to another mailbox. The inactive mailbox is retained and remains an inactive mailbox. The inactive mailbox can still be searched using eDiscovery, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date. For step-by-step procedures, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
  
## <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="c5dd4-195">非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="c5dd4-195">Delete an inactive mailbox</span></span>

<span data-ttu-id="c5dd4-p122">不要になった非アクティブなメールボックスの内容を保持する必要がある場合は、保留リストを削除または非アクティブなメールボックスに適用される Office 365 の保持ポリシーを削除することによって非アクティブなメールボックスを完全に削除できます。メールボックスが 30 日以上前に削除された場合、保留を解除すると、メールボックスが不可能になる、メールボックスは完全に削除のマークされます。過去 30 日以内のメールボックスが削除された場合、保留中または保持ポリシーを削除した後、メールボックスを回復できます。保留または恒久的に、非アクティブなメールボックスを削除するのには Office 365 の保持ポリシーを削除する手順は、 [Office 365 で、非アクティブなメールボックスの削除](delete-an-inactive-mailbox.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5dd4-p122">If you no longer need to retain the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold or removing the Office 365 retention policy applied to the inactive mailbox. If the mailbox was deleted more than 30 days ago, the mailbox will be marked for permanent deletion after you remove the hold, and the mailbox will become non-recoverable. If the mailbox was deleted within the last 30 days, you can still recover the mailbox after removing the hold or retention policy. For step-by-step procedures for removing a hold or a Office 365 retention policy to permanently delete an inactive mailbox, see [Delete an inactive mailbox in Office 365](delete-an-inactive-mailbox.md).</span></span>