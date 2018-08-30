---
title: Office 365 の監査ログに監査を共有を使用します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: '共有は、SharePoint Online およびビジネスのための OneDrive でのキー操作です。管理者を使用できます Office 365 の監査ログに監査を共有する方法の共有で使用されている自分の組織を決定します。 '
ms.openlocfilehash: 511f8b0e61d450659d78177d5b87fac9ee636cd4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532259"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a><span data-ttu-id="3eb2e-104">Office 365 の監査ログに監査を共有を使用します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-104">Use sharing auditing in the Office 365 audit log</span></span>

<span data-ttu-id="3eb2e-p102">SharePoint Online とのビジネス、OneDrive でのキー操作は、共有し、Office 365 の組織で広く使用されています。管理者を使用できます Office 365 の監査ログに監査を共有する方法の共有で使用されている自分の組織を決定します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-p102">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in Office 365 organizations. Administrators can now use sharing auditing in the Office 365 audit log to determine how sharing is being used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="3eb2e-107">SharePoint 共有スキーマ</span><span class="sxs-lookup"><span data-stu-id="3eb2e-107">The SharePoint Sharing schema</span></span>

<span data-ttu-id="3eb2e-p103">(除外ポリシーを共有および共有リンク イベント) 共有のイベントとは異なるファイルとフォルダー関連のイベントで 1 つの主な方法: 別のユーザーにいくつかの効果のあるアクションを 1 つのユーザーが実行します。たとえば、ユーザー A では、ファイルにユーザー B のアクセスが与えられます。この例では、ユーザー A は、*ユーザーが機能している*とユーザー B は、*移動先のユーザー*です。SharePoint ファイルのスキーマで機能しているユーザーのアクションは、ファイル自体をのみ影響します。**FileAccessed**のイベントで必要な情報だけのファイルをユーザー A が表示は、機能しているユーザーです。この違いに対処するため、*スキーマの SharePoint の共有*、共有イベントの詳細をキャプチャすると呼ばれる、別のスキーマがあります。これにより、管理者があるユーザーがリソースを共有することにより多くの洞察と、リソースのユーザーが共有されました。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-p103">Sharing events (excluding sharing policy and sharing link events) are different from file- and folder-related events in one primary way: one user is taking an action that has some effect on another user. For example, User A gives User B access to a file. In this example, User A is the  *acting user*  and User B is the  *target user*. In the SharePoint File schema, the acting user's action only affects the file itself. When User A opens a file, the only information needed in the **FileAccessed** event is the acting user. To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events. This ensures that administrators have more insight into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="3eb2e-115">共有スキーマには、共有イベントに関連する監査ログ内の 2 つのフィールドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-115">The Sharing schema provides two additional fields in the audit log related to sharing events:</span></span> 
  
- <span data-ttu-id="3eb2e-116">**TargetUserOrGroupName**では、UPN または移動先のユーザーまたは (前の例では、ユーザー B) を持つリソースが共有されているグループの名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-116">**TargetUserOrGroupName** - Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 
    
- <span data-ttu-id="3eb2e-117">**TargetUserOrGroupType**では、ターゲットのユーザーまたはグループは、メンバー、ゲスト、グループ、またはパートナーかどうかを識別します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-117">**TargetUserOrGroupType** - Identifies whether the target user or group is a Member, Guest, Group, or Partner.</span></span> 
    
<span data-ttu-id="3eb2e-118">Office 365 の他のプロパティに加えて、これらの 2 つのフィールドは、ユーザー、操作、および日付がについて完全に理解し、**どの*ユーザーが共有リソースを*対象*と*すると** ログのスキーマを監査します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-118">These two fields, in addition to other properties from the Office 365 audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="3eb2e-p104">ストーリーを共有する必要がある別のスキーマ プロパティがあります。**EventData**プロパティは、共有イベントに関する追加情報を格納します。たとえば、ユーザーは、他のユーザーとサイトを共有する場合これは、ターゲット ユーザーを SharePoint グループに追加します。**EventData**プロパティは、管理者のコンテキストを提供する追加情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-p104">There's another schema property that's important to the sharing story. The **EventData** property stores additional information about sharing events. For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group. The **EventData** property captures this additional information to provide context for administrators.</span></span> 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a><span data-ttu-id="3eb2e-123">SharePoint のモデルとイベントを共有</span><span class="sxs-lookup"><span data-stu-id="3eb2e-123">The SharePoint Sharing model and sharing events</span></span>

<span data-ttu-id="3eb2e-p105">3 つの別々 のイベントで実際に定義されて共有: **SharingSet**、 **SharingInvitationCreated**、および**SharingInvitaitonAccepted**。次のイベントを共有する方法の作業の流れは、Office 365 の監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-p105">Sharing is actually defined by three separate events: **SharingSet**, **SharingInvitationCreated**, and **SharingInvitaitonAccepted**. Here's the work flow for how sharing events are logged in the Office 365 audit log.</span></span> 
  
![監査を共有のしくみのフロー チャート](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
<span data-ttu-id="3eb2e-p106">(ターゲット ユーザー) の他のユーザーとリソースを共有するユーザー (機能しているユーザー) 場合、SharePoint (またはビジネスのための OneDrive) はまず移動先のユーザーの電子メール アドレスが既に組織のディレクトリ内のユーザー アカウントに関連付けられています。ターゲット ユーザーが組織のディレクトリにある場合は、SharePoint は、次を行います。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-p106">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory. If the target user is in the organization's directory, SharePoint does the following:</span></span>
  
-  <span data-ttu-id="3eb2e-129">すぐにリソースにアクセスするターゲット ・ ユーザーのアクセス許可が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-129">Immediately assigns the target user permissions to access the resource.</span></span> 
    
- <span data-ttu-id="3eb2e-130">ターゲット ユーザーの電子メール アドレスを共有の通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-130">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="3eb2e-131">**SharingSet**イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-131">Logs a **SharingSet** event.</span></span> 
    
 <span data-ttu-id="3eb2e-132">ターゲット ユーザーのユーザー アカウントは、組織のディレクトリにない場合は、SharePoint は、次が。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-132">If a user account for the target user isn't in the organization's directory, SharePoint does the following:</span></span> 
  
- <span data-ttu-id="3eb2e-133">共有への招待を作成し、ターゲット ユーザーの電子メール アドレスに送信します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-133">Creates a sharing invitation and sends it to the email address of the target user.</span></span>
    
- <span data-ttu-id="3eb2e-134">**SharingInvitationCreated**イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-134">Logs a **SharingInvitationCreated** event.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3eb2e-135">**SharingInvitationCreated**イベントは、外部またはゲストの共有ターゲット ユーザーが共有されているリソースへのアクセスを持っていない場合、ほとんど常に。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-135">The **SharingInvitationCreated** event is most always associated with external or guest sharing when the target user doesn't have access to the resource that was shared.</span></span> 
  
<span data-ttu-id="3eb2e-p107">ターゲット ユーザーが送信すること (リンクをクリックして招待状に)、SharePoint 共有への招待を受け入れると**SharingInvitationAccepted**のイベントをログに記録し、リソースにアクセスするターゲット ・ ユーザーのアクセス許可が割り当てられます。ターゲット ユーザーに関する追加情報も記録、招待状が送られてきたユーザーと実際には、出席依頼を承諾したユーザーの id などです。これらのユーザー (または電子メール アドレス) がいくつかのケースでは、異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-p107">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource. Additional information about the target user is also logged, such as the identity of the user that the invitation was sent to and the user who actually accepted the invitation. In some case, these users (or email addresses) might be different.</span></span> 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="3eb2e-139">外部ユーザーと共有されているリソースを識別する方法</span><span class="sxs-lookup"><span data-stu-id="3eb2e-139">How to identify resources shared with external users</span></span>

<span data-ttu-id="3eb2e-p108">管理者の一般的な要件は、組織外のユーザーと共有されているすべてのリソースの一覧を作成しています。監査では、Office 365 の共有を使用して、管理者は今すぐこのリストを生成できます。ここではどのようにします。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-p108">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization. By using sharing auditing in Office 365, administrators can now generate this list. Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="3eb2e-143">イベントを共有するための手順 1: 検索し、結果を CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-143">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="3eb2e-p109">最初のステップでは、イベントを共有するための Office 365 の監査ログを検索します。詳細 (必要なアクセス許可を含む) に関する監査ログの検索、参照してください[では、Office 365 のセキュリティ監査ログを検索する&amp;コンプライアンス センター](search-the-audit-log-in-security-and-compliance.md)です。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-p109">The first step is to search the Office 365 audit log for sharing events. For more details (including the required permissions) about searching the audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="3eb2e-146">[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-146">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="3eb2e-147">職場、学校のアカウントを使用して Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-147">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="3eb2e-148">セキュリティの左側のウィンドウで&amp;コンプライアンス センター] をクリックして**検索&amp;調査**、**監査ログの検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-148">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation**, and then click **Audit log search**.</span></span>
    
    <span data-ttu-id="3eb2e-149">**監査ログの検索**ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-149">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="3eb2e-150">**アクティビティ**で [共有イベントだけを検索するのには、**共有アクティビティ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-150">Under **Activities**, click **Sharing activities** to search only for sharing events.</span></span> 
    
    ![アクティビティで [共有するアクティビティを選択します](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="3eb2e-152">その期間内に発生した共有のイベントを検索する日付と時刻の範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-152">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="3eb2e-153">検索を実行する**検索**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-153">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="3eb2e-154">実行と結果が表示される検索が完了すると、**結果のエクスポート**] をクリックして\>**すべての結果をダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-154">When the search is finished running and the results are displayed , click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="3eb2e-155">エクスポート オプションを選択すると、開く、または CSV ファイルを保存するように要求するウィンドウの下部にあるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-155">After you select the export option, a message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="3eb2e-156">**保存**] をクリックして\>**として保存**し、ローカル コンピューター上のフォルダーに CSV ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-156">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="3eb2e-157">ステップ 2: CSV ファイルの外部ユーザーと共有されているリソースをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-157">Step 2: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="3eb2e-p110">次に、 **SharingSet**と**SharingInvitationCreated**のイベントで CSV にフィルターを適用して、それらのイベントを表示するのには、 **TargetUserOrGroupType**プロパティでは、**ゲスト**です。Excel でこれを行う電源クエリ機能を使用します。2016 の Excel では、次の手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-p110">The next step is to filter the CSV for the **SharingSet** and **SharingInvitationCreated** events, and to display those events where the **TargetUserOrGroupType** property is **Guest**. You'll use the Power Query feature in Excel to do this. The following procedure is performed in Excel 2016.</span></span> 
  
1. <span data-ttu-id="3eb2e-161">Excel の 2016年には、空白のブックを開きます。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-161">In Excel 2016, open a blank workbook.</span></span>
    
2. <span data-ttu-id="3eb2e-162">[**データ** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-162">Click the **Data** tab.</span></span> 
    
3. <span data-ttu-id="3eb2e-163">**新しいクエリ**をクリックして\>**ファイルから** \> **から CSV**です。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-163">Click **New Query** \> **From file** \> **From CSV**.</span></span>
    
    ![[データ] タブで、新しいクエリを選択して、ファイルから選択し、CSV から](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. <span data-ttu-id="3eb2e-165">手順 1 でダウンロードした CSV ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-165">Open the CSV file that you downloaded in Step 1.</span></span>
    
    <span data-ttu-id="3eb2e-p111">CSV ファイルはクエリ ・ エディターで開かれます。4 つの列があることに注意してください:**時間**、**ユーザー**、**アクション**、および**詳細**。**詳細**列は、複数のプロパティのフィールドです。次の手順では、各プロパティの [**詳細**] 列に新しい列を作成します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-p111">The CSV file is opened in the Query Editor. Note that there are four columns: **Time**, **User**, **Action**, and **Detail**. The **Detail** column is a multi-property field. The next step is to create a new column for each of the properties in the **Detail** column.</span></span> 
    
5. <span data-ttu-id="3eb2e-170">**詳細**列を選択し、[**ホーム**] タブで、**列を分割する** \> **での区切り記号**。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-170">Select the **Detail** column, and then on the **Home** tab, click **Split Column** \> **By Delimiter**.</span></span>
    
    ![[ホーム] タブで、分割列] をクリックし、区切り記号](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. <span data-ttu-id="3eb2e-172">ウィンドウで、**区切り文字で列を分割する**には、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-172">In the **Split Column by Delimiter** window, do the following:</span></span> 
    
      - <span data-ttu-id="3eb2e-173">**選択するか区切り記号を入力して**、**コンマ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-173">Under **Select or enter delimiter**, select **Comma**.</span></span>
    
      - <span data-ttu-id="3eb2e-174">**分割**では、[**区切り記号の各アイテム**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-174">Under **Split**, select **At each occurrence of the delimiter**.</span></span>
    
7. <span data-ttu-id="3eb2e-175">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-175">Click **OK**.</span></span>
    
    <span data-ttu-id="3eb2e-p112">**詳細**列は、複数の列に分割されます。新しい列のそれぞれは、 **Detail.1**、 **Detail.2**、 **Detail.3**というように呼びます。**Detail.n**列の各セルの値のプロパティの名前が付きますがわかりますたとえば、**操作: SharingSet**、**操作: SharingInvitationAccepted**、および**操作: SharingInvitationCreated**にします。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-p112">The **Detail** column is split into multiple columns. Each new column is named **Detail.1**, **Detail.2**, **Detail.3**, and so on. You'll notice the values in each cell in the **Detail.n** columns are prefixed with the name of the property; for example, **Operation:SharingSet**, **Operation:SharingInvitationAccepted**, and **Operation:SharingInvitationCreated**.</span></span>
    
    ![詳細列は、プロパティごとに 1 つ、複数の列に分割します。](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. <span data-ttu-id="3eb2e-180">[**ファイル**] タブをクリックして**を閉じる&amp;ロード**クエリ ・ エディターを終了し、Excel ブックのファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-180">On the **File** tab, click **Close &amp; Load** to close the Query Editor and open the file in an Excel workbook.</span></span> 
    
    <span data-ttu-id="3eb2e-181">次の手順では、のみイベントを表示する、 **SharingSet**および**SharingInvitationCreated**ファイルをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-181">The next step is to filter the file to only display the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
9. <span data-ttu-id="3eb2e-182">**[ホーム**] タブに移動し、[**アクション**] 列を選択します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-182">Go to the **Home** tab, and then select the **Action** column.</span></span> 
    
10. <span data-ttu-id="3eb2e-183">**ソート&amp;フィルター** 」ドロップ ダウン リスト、すべての選択: **SharingSet**と**SharingInvitationCreated**を選択し、 **[ok]** をクリックしてクリアします。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-183">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **SharingSet** and **SharingInvitationCreated**, and click **OK**.</span></span>
    
    <span data-ttu-id="3eb2e-184">Excel では**SharingSet**と**SharingInvitationCreated**のイベントの行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-184">Excel displays the rows for the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
11. <span data-ttu-id="3eb2e-185">**Detail.17** (またはいずれかの列には、 **TargetUserOrGroupType**プロパティが含まれています) という名前の列に移動し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-185">Go to the column named **Detail.17** (or whichever column contains the **TargetUserOrGroupType** property) and select it.</span></span> 
    
12. <span data-ttu-id="3eb2e-186">**ソート&amp;フィルター** 」ドロップ ダウン リスト、すべての選択: **TargetUserOrGroupType:Guest**を選択し、 **[ok]** をクリックしてクリアします。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-186">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **OK**.</span></span>
    
    <span data-ttu-id="3eb2e-187">ここで Excel は、外部ユーザーが**TargetUserOrGroupType:Guest**の値によって識別されるため、 **SharingInvitationCreated**と**SharingSet**のイベントは、ターゲットである別の組織では、行を表示します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-187">Now Excel displays the rows for **SharingInvitationCreated** and **SharingSet** events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
    
<span data-ttu-id="3eb2e-188">次の表は、指定した日付の範囲内でのゲスト ユーザーとリソースを共有する組織のすべてのユーザーを示します。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-188">The following table shows all users in the organization who shared resources with a guest user within a specified date range.</span></span>
  
![Office 365 の共有のイベントの監査ログ](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
<span data-ttu-id="3eb2e-190">**Detail.10**列 (または、**オブジェクト Id**のプロパティを含んでいる列) がターゲット ・ ユーザーと共有されていたリソースを識別するには上記の表には含まれていません、たとえば`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-190">Although it's not included in the previous table, the **Detail.10** column (or whichever column contains the **ObjectId** property) identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
  
> [!TIP]
> <span data-ttu-id="3eb2e-191">識別する場合は、ゲスト ユーザーが実際に割り当てるとリソースにアクセスするアクセス許可 (リソースだけではなくその場所に共有)、手順 10、11、12、および、 **SharingInvitationAccepted**と**SharingSet にフィルターを適用**手順 10 でのイベントです。</span><span class="sxs-lookup"><span data-stu-id="3eb2e-191">If you want to identify when a guest user was actually assigned permissions to access a resource (as opposed to just the resources that where shared with them), repeat Steps 10, 11, and 12, and filter on the **SharingInvitationAccepted** and **SharingSet** events in Step 10.</span></span> 
