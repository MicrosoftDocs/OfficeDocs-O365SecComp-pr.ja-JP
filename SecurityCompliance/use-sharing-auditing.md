---
title: 共有を監査して外部ユーザーと共有されているリソースを見つける
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: '共有は、SharePoint Online と OneDrive for business の主要なアクティビティです。 管理者は、Office 365 監査ログで共有監査を使用して、組織での共有の使用状況を確認できるようになりました。 '
ms.openlocfilehash: e2865d35e988d8c0e42a6c51f78507db8b170d4c
ms.sourcegitcommit: b262d40f6daf06be26e7586f37b736e09f8a4511
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35435243"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a><span data-ttu-id="30f8b-104">共有を監査して外部ユーザーと共有されているリソースを見つける</span><span class="sxs-lookup"><span data-stu-id="30f8b-104">Use sharing auditing in the Office 365 audit log</span></span>

<span data-ttu-id="30f8b-105">共有は、SharePoint Online と OneDrive for business の主要なアクティビティであり、Office 365 組織で広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="30f8b-105">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in Office 365 organizations.</span></span> <span data-ttu-id="30f8b-106">管理者は、Office 365 監査ログで共有監査を使用して、組織での共有の使用状況を確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="30f8b-106">Administrators can now use sharing auditing in the Office 365 audit log to determine how sharing is being used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="30f8b-107">SharePoint 共有スキーマ</span><span class="sxs-lookup"><span data-stu-id="30f8b-107">The SharePoint Sharing schema</span></span>

<span data-ttu-id="30f8b-108">共有イベント (共有ポリシーと共有リンクイベントを除く) は、1つのユーザーが別のユーザーに対して何らかの影響を与えるアクションを実行しているという主な方法で、ファイルとフォルダーに関連するイベントとは異なります。</span><span class="sxs-lookup"><span data-stu-id="30f8b-108">Sharing events (excluding sharing policy and sharing link events) are different from file- and folder-related events in one primary way: one user is taking an action that has some effect on another user.</span></span> <span data-ttu-id="30f8b-109">たとえば、User A はユーザー B にファイルへのアクセス権を与えます。</span><span class="sxs-lookup"><span data-stu-id="30f8b-109">For example, User A gives User B access to a file.</span></span> <span data-ttu-id="30f8b-110">この例では、ユーザー A は、動作している*ユーザー*で、ユーザー B は*対象ユーザー*です。</span><span class="sxs-lookup"><span data-stu-id="30f8b-110">In this example, User A is the  *acting user*  and User B is the  *target user*.</span></span> <span data-ttu-id="30f8b-111">SharePoint ファイルスキーマでは、動作しているユーザーの操作だけがファイル自体に影響します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-111">In the SharePoint File schema, the acting user's action only affects the file itself.</span></span> <span data-ttu-id="30f8b-112">ユーザーがファイルを開くと、 **Fileaccessed**イベントに必要な情報は、動作しているユーザーのみになります。</span><span class="sxs-lookup"><span data-stu-id="30f8b-112">When User A opens a file, the only information needed in the **FileAccessed** event is the acting user.</span></span> <span data-ttu-id="30f8b-113">この違いに対処するために、共有イベントに関する詳細情報を収集する、 *SharePoint 共有スキーマ*と呼ばれる別のスキーマがあります。</span><span class="sxs-lookup"><span data-stu-id="30f8b-113">To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events.</span></span> <span data-ttu-id="30f8b-114">これにより、管理者はリソースを共有しているユーザーとリソースを共有していたユーザーについて、より洞察を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="30f8b-114">This ensures that administrators have more insight into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="30f8b-115">共有スキーマは、イベントの共有に関連する2つの追加フィールドを監査ログに提供します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-115">The Sharing schema provides two additional fields in the audit log related to sharing events:</span></span> 
  
- <span data-ttu-id="30f8b-116">**Targetuserorgroupname** –リソースが共有されていた対象ユーザーまたはグループの UPN または名前を格納します (前の例では、ユーザー B)。</span><span class="sxs-lookup"><span data-stu-id="30f8b-116">**TargetUserOrGroupName** – Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 
    
- <span data-ttu-id="30f8b-117">**TargetUserOrGroupType** –対象のユーザーまたはグループが、メンバー、ゲスト、グループ、またはパートナーであるかどうかを識別します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-117">**TargetUserOrGroupType** – Identifies whether the target user or group is a Member, Guest, Group, or Partner.</span></span> 
    
<span data-ttu-id="30f8b-118">これら2つのフィールドは、ユーザー、操作、日付などの Office 365 監査ログスキーマの他のプロパティに加えて、*どの*ユーザーがどのリソースを*どのよう*な\*\* *とき*に共有したかについての完全なストーリーを伝えることができます。</span><span class="sxs-lookup"><span data-stu-id="30f8b-118">These two fields, in addition to other properties from the Office 365 audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="30f8b-119">共有ストーリーにとって重要なスキーマプロパティは他にもあります。</span><span class="sxs-lookup"><span data-stu-id="30f8b-119">There's another schema property that's important to the sharing story.</span></span> <span data-ttu-id="30f8b-120">**EventData**プロパティは、共有イベントに関する追加情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-120">The **EventData** property stores additional information about sharing events.</span></span> <span data-ttu-id="30f8b-121">たとえば、ユーザーが別のユーザーとサイトを共有する場合は、ターゲットユーザーを SharePoint グループに追加することによって実現します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-121">For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group.</span></span> <span data-ttu-id="30f8b-122">**EventData**プロパティは、管理者にコンテキストを提供するために、この追加情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="30f8b-122">The **EventData** property captures this additional information to provide context for administrators.</span></span> 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a><span data-ttu-id="30f8b-123">SharePoint 共有モデルと共有イベント</span><span class="sxs-lookup"><span data-stu-id="30f8b-123">The SharePoint Sharing model and sharing events</span></span>

<span data-ttu-id="30f8b-124">共有は、 **Sharingset**、 **SharingInvitationCreated**、および**SharingInvitaitonAccepted**の3つの個別のイベントによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="30f8b-124">Sharing is defined by three separate events: **SharingSet**, **SharingInvitationCreated**, and **SharingInvitaitonAccepted**.</span></span> <span data-ttu-id="30f8b-125">Office 365 監査ログに共有イベントを記録する方法については、次のワークフローを参照してください。</span><span class="sxs-lookup"><span data-stu-id="30f8b-125">Here's the work flow for how sharing events are logged in the Office 365 audit log.</span></span> 
  
![共有の監査のしくみを示すフローチャート](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
<span data-ttu-id="30f8b-127">ユーザー (動作しているユーザー) が別のユーザー (ターゲットユーザー) とリソースを共有しようとしている場合、SharePoint (または OneDrive for Business) は最初に、対象ユーザーの電子メールアドレスが組織のディレクトリ内のユーザーアカウントに関連付けられているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-127">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory.</span></span> <span data-ttu-id="30f8b-128">ターゲットユーザーが組織のディレクトリにある場合、SharePoint は次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="30f8b-128">If the target user is in the organization's directory, SharePoint does the following:</span></span>
  
-  <span data-ttu-id="30f8b-129">リソースにアクセスするためのターゲットユーザーのアクセス許可を即時に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="30f8b-129">Immediately assigns the target user permissions to access the resource.</span></span> 
    
- <span data-ttu-id="30f8b-130">ターゲットユーザーの電子メールアドレスに共有通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-130">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="30f8b-131">**Sharingset**イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-131">Logs a **SharingSet** event.</span></span> 
    
 <span data-ttu-id="30f8b-132">ターゲットユーザーのユーザーアカウントが組織のディレクトリにない場合、SharePoint は次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="30f8b-132">If a user account for the target user isn't in the organization's directory, SharePoint does the following:</span></span> 
  
- <span data-ttu-id="30f8b-133">共有への招待を作成し、対象ユーザーの電子メールアドレスに送信します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-133">Creates a sharing invitation and sends it to the email address of the target user.</span></span>
    
- <span data-ttu-id="30f8b-134">**SharingInvitationCreated**イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-134">Logs a **SharingInvitationCreated** event.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="30f8b-135">**SharingInvitationCreated**イベントは、ターゲットユーザーが共有されているリソースにアクセスできない場合、常に外部またはゲストの共有に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="30f8b-135">The **SharingInvitationCreated** event is most always associated with external or guest sharing when the target user doesn't have access to the resource that was shared.</span></span> 
  
<span data-ttu-id="30f8b-136">ターゲットユーザーが (招待のリンクをクリックすることによって) 送信された共有の招待を承諾すると、SharePoint は**SharingInvitationAccepted**イベントをログに記録し、リソースにアクセスするためのアクセス許可をターゲットユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="30f8b-136">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource.</span></span> <span data-ttu-id="30f8b-137">対象ユーザーに関する追加情報も記録されます。たとえば、招待状が送信されたユーザーの id や、招待を実際に受諾したユーザーなどが記録されます。</span><span class="sxs-lookup"><span data-stu-id="30f8b-137">Additional information about the target user is also logged, such as the identity of the user that the invitation was sent to and the user who actually accepted the invitation.</span></span> <span data-ttu-id="30f8b-138">場合によっては、これらのユーザー (またはメールアドレス) が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="30f8b-138">In some case, these users (or email addresses) might be different.</span></span> 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="30f8b-139">外部ユーザーと共有されるリソースを特定する方法</span><span class="sxs-lookup"><span data-stu-id="30f8b-139">How to identify resources shared with external users</span></span>

<span data-ttu-id="30f8b-140">管理者にとって一般的な要件は、組織外のユーザーと共有されているすべてのリソースの一覧を作成することです。</span><span class="sxs-lookup"><span data-stu-id="30f8b-140">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization.</span></span> <span data-ttu-id="30f8b-141">Office 365 で共有監査を使用すると、管理者がこのリストを生成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="30f8b-141">By using sharing auditing in Office 365, administrators can now generate this list.</span></span> <span data-ttu-id="30f8b-142">ここでは、使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-142">Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="30f8b-143">手順 1: 共有イベントを検索し、結果を CSV ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="30f8b-143">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="30f8b-144">最初の手順として、Office 365 監査ログで共有イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-144">The first step is to search the Office 365 audit log for sharing events.</span></span> <span data-ttu-id="30f8b-145">監査ログの検索に関する詳細 (必要なアクセス許可を含む) については、「[セキュリティ & のコンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30f8b-145">For more information (including the required permissions) about searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="30f8b-146">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-146">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="30f8b-147">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="30f8b-147">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="30f8b-148">セキュリティ & コンプライアンスセンターの左側のウィンドウで、[**検索**  > **監査ログの検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30f8b-148">In the left pane of the Security & Compliance Center, click **Search**  > **Audit log search**.</span></span>
    
    <span data-ttu-id="30f8b-149">[**監査ログの検索**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30f8b-149">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="30f8b-150">[**アクティビティ**] の下の [**共有とアクセス要求アクティビティ**] をクリックして、共有関連イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-150">Under **Activities**, click **Sharing and access request activities** to search for sharing-related events.</span></span> 
    
    ![[アクティビティ] の下で、[共有とアクセスの要求のアクティビティ] を選択します。](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="30f8b-152">日付と時刻の範囲を選択して、その期間内に発生した共有イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-152">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="30f8b-153">[**検索**] をクリックして検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-153">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="30f8b-154">検索の実行が完了し、結果が表示されたら、[**結果** \>のエクスポート] をクリックして**すべての結果をダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-154">When the search is finished running and the results are displayed, click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="30f8b-155">[エクスポート] オプションを選択すると、CSV ファイルを開いたり保存したりするように求めるメッセージがウィンドウの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="30f8b-155">After you select the export option, a message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="30f8b-156">[名前を付け**て**保存] をクリックし、CSV ファイルをローカルコンピューター上のフォルダーに保存します。 \*\*\*\* \></span><span class="sxs-lookup"><span data-stu-id="30f8b-156">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 

### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="30f8b-157">手順 2: 外部ユーザーと共有しているリソースの CSV ファイルをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="30f8b-157">Step 2: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="30f8b-158">次の手順では、 **Sharingset**イベントと**SharingInvitationCreated**イベントに対して CSV をフィルター処理し、 **TargetUserOrGroupType**プロパティが**Guest**であるイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-158">The next step is to filter the CSV for the **SharingSet** and **SharingInvitationCreated** events, and to display those events where the **TargetUserOrGroupType** property is **Guest**.</span></span> <span data-ttu-id="30f8b-159">これを行うには、Excel の Power Query Editor ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-159">You use the Power Query Editor tool in Excel to do this.</span></span> <span data-ttu-id="30f8b-160">詳細な手順については、「 [Export, configure, and view audit log records](export-view-audit-log-records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30f8b-160">For step-by-step instructions, see [Export, configure, and view audit log records](export-view-audit-log-records.md).</span></span> 

<span data-ttu-id="30f8b-161">前のトピックの手順に従って CSV ファイルを準備した後、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="30f8b-161">After you've followed the instructions in the previous topic to prepare the CSV file, do the following:</span></span>
    
1. <span data-ttu-id="30f8b-162">Power Query Editor で準備した CSV ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="30f8b-162">Open the CSV file that you prepared with the Power Query Editor.</span></span> 

2. <span data-ttu-id="30f8b-163">[**ホーム**] タブで、[**並べ替え & フィルター**] をクリックし、[**フィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30f8b-163">On the **Home** tab, click **Sort & Filter**, and then click **Filter**.</span></span>
    
3. <span data-ttu-id="30f8b-164">[**操作**] 列の [ **& フィルターの並べ替え**] ドロップダウンリストで、すべての選択を解除し、[ **Sharingset** ] と [ **SharingInvitationCreated**] を選択して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30f8b-164">In the **Sort & Filter** dropdown list on the **Operations** column, clear all selections, then select **SharingSet** and **SharingInvitationCreated**, and click **OK**.</span></span>
    
    <span data-ttu-id="30f8b-165">**Sharingset**および**SharingInvitationCreated**イベントの行が Excel に表示されます。</span><span class="sxs-lookup"><span data-stu-id="30f8b-165">Excel displays the rows for the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
4. <span data-ttu-id="30f8b-166">**TargetUserOrGroupType**という名前の列に移動し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-166">Go to the column named **TargetUserOrGroupType** and select it.</span></span> 
    
5. <span data-ttu-id="30f8b-167">[**並べ替え & フィルター** ] ドロップダウンリストで、すべての選択をオフにし、[ **TargetUserOrGroupType: Guest**] を選択して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30f8b-167">In the **Sort & Filter** dropdown list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **OK**.</span></span>
    
    <span data-ttu-id="30f8b-168">ここでは、外部ユーザーが**TargetUserOrGroupType: Guest**という値で識別されるため、 **SharingInvitationCreated**および**SHARINGSET**イベントの行と、ターゲットユーザーが組織外にある場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="30f8b-168">Now Excel displays the rows for **SharingInvitationCreated** and **SharingSet** events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
    
<span data-ttu-id="30f8b-169">次の表に、指定された日付範囲内のゲストユーザーとリソースを共有している、組織内のすべてのユーザーを示します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-169">The following table shows all users in the organization who shared resources with a guest user within a specified date range.</span></span>
  
![Office での共有イベント365監査ログ](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
<span data-ttu-id="30f8b-171">**ObjectId**プロパティは、前の表には含まれていませんが、ターゲットユーザーと共有されたリソースを識別します。例`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`を示します。</span><span class="sxs-lookup"><span data-stu-id="30f8b-171">Although it's not included in the previous table, the **ObjectId** property identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
  
> [!TIP]
> <span data-ttu-id="30f8b-172">ゲストユーザーが実際にリソースにアクセスするためのアクセス許可が割り当てられているかどうかを確認するには (リソースと共有しているリソースだけでなく)、手順2、3、4を繰り返し、 **SharingInvitationAccepted**と**sharingset**でフィルター処理します。手順5のイベント</span><span class="sxs-lookup"><span data-stu-id="30f8b-172">If you want to identify when a guest user was actually assigned permissions to access a resource (as opposed to just the resources that where shared with them), repeat Steps 2, 3, and 4, and filter on the **SharingInvitationAccepted** and **SharingSet** events in Step 5.</span></span> 
