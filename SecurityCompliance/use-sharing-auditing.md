---
title: 共有を監査して外部ユーザーと共有されているリソースを見つける
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
ms.audience: Admin
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
ms.openlocfilehash: 08b511acdf74edac5b2d595d1b60bdd84d630918
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263411"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a><span data-ttu-id="3fe46-104">共有を監査して外部ユーザーと共有されているリソースを見つける</span><span class="sxs-lookup"><span data-stu-id="3fe46-104">Use sharing auditing in the Office 365 audit log</span></span>

<span data-ttu-id="3fe46-105">共有は、SharePoint Online と OneDrive for business の主要なアクティビティであり、Office 365 組織で広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="3fe46-105">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in Office 365 organizations.</span></span> <span data-ttu-id="3fe46-106">管理者は、Office 365 監査ログで共有監査を使用して、組織での共有の使用状況を確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3fe46-106">Administrators can now use sharing auditing in the Office 365 audit log to determine how sharing is being used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="3fe46-107">SharePoint 共有スキーマ</span><span class="sxs-lookup"><span data-stu-id="3fe46-107">The SharePoint Sharing schema</span></span>

<span data-ttu-id="3fe46-108">共有イベント (共有ポリシーと共有リンクイベントを除く) は、1つのユーザーが別のユーザーに対して何らかの影響を与えるアクションを実行しているという主な方法で、ファイルとフォルダーに関連するイベントとは異なります。</span><span class="sxs-lookup"><span data-stu-id="3fe46-108">Sharing events (excluding sharing policy and sharing link events) are different from file- and folder-related events in one primary way: one user is taking an action that has some effect on another user.</span></span> <span data-ttu-id="3fe46-109">たとえば、user A はユーザー B にファイルへのアクセス権を与えます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-109">For example, User A gives User B access to a file.</span></span> <span data-ttu-id="3fe46-110">この例では、ユーザー A は、動作している*ユーザー*で、ユーザー B は*対象ユーザー*です。</span><span class="sxs-lookup"><span data-stu-id="3fe46-110">In this example, User A is the  *acting user*  and User B is the  *target user*.</span></span> <span data-ttu-id="3fe46-111">SharePoint ファイルスキーマでは、動作しているユーザーの操作だけがファイル自体に影響します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-111">In the SharePoint File schema, the acting user's action only affects the file itself.</span></span> <span data-ttu-id="3fe46-112">ユーザーがファイルを開くと、 **fileaccessed**イベントに必要な情報は、動作しているユーザーのみになります。</span><span class="sxs-lookup"><span data-stu-id="3fe46-112">When User A opens a file, the only information needed in the **FileAccessed** event is the acting user.</span></span> <span data-ttu-id="3fe46-113">この違いに対処するために、共有イベントに関する詳細情報を収集する、 *SharePoint 共有スキーマ*と呼ばれる別のスキーマがあります。</span><span class="sxs-lookup"><span data-stu-id="3fe46-113">To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events.</span></span> <span data-ttu-id="3fe46-114">これにより、管理者はリソースを共有しているユーザーとリソースを共有していたユーザーについて、より洞察を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-114">This ensures that administrators have more insight into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="3fe46-115">共有スキーマは、イベントの共有に関連する2つの追加フィールドを監査ログに提供します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-115">The Sharing schema provides two additional fields in the audit log related to sharing events:</span></span> 
  
- <span data-ttu-id="3fe46-116">**targetuserorgroupname** -リソースが共有されていたターゲットユーザーまたはグループの UPN または名前を格納します (前の例では user B)。</span><span class="sxs-lookup"><span data-stu-id="3fe46-116">**TargetUserOrGroupName** - Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 
    
- <span data-ttu-id="3fe46-117">**TargetUserOrGroupType** -対象のユーザーまたはグループが、メンバー、ゲスト、グループ、またはパートナーであるかどうかを識別します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-117">**TargetUserOrGroupType** - Identifies whether the target user or group is a Member, Guest, Group, or Partner.</span></span> 
    
<span data-ttu-id="3fe46-118">これら2つのフィールドは、ユーザー、操作、日付などの Office 365 監査ログスキーマの他のプロパティに加えて、*どの*ユーザーがどのリソースを*どのよう*な\*\* *とき*に共有したかについての完全なストーリーを伝えることができます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-118">These two fields, in addition to other properties from the Office 365 audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="3fe46-119">共有ストーリーにとって重要なスキーマプロパティは他にもあります。</span><span class="sxs-lookup"><span data-stu-id="3fe46-119">There's another schema property that's important to the sharing story.</span></span> <span data-ttu-id="3fe46-120">**EventData**プロパティは、共有イベントに関する追加情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-120">The **EventData** property stores additional information about sharing events.</span></span> <span data-ttu-id="3fe46-121">たとえば、ユーザーが別のユーザーとサイトを共有する場合は、ターゲットユーザーを SharePoint グループに追加することによって実現します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-121">For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group.</span></span> <span data-ttu-id="3fe46-122">**EventData**プロパティは、管理者にコンテキストを提供するために、この追加情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="3fe46-122">The **EventData** property captures this additional information to provide context for administrators.</span></span> 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a><span data-ttu-id="3fe46-123">SharePoint 共有モデルと共有イベント</span><span class="sxs-lookup"><span data-stu-id="3fe46-123">The SharePoint Sharing model and sharing events</span></span>

<span data-ttu-id="3fe46-124">共有は、実際には、 **sharingset**、 **SharingInvitationCreated**、および**SharingInvitaitonAccepted**の3つの個別のイベントによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-124">Sharing is actually defined by three separate events: **SharingSet**, **SharingInvitationCreated**, and **SharingInvitaitonAccepted**.</span></span> <span data-ttu-id="3fe46-125">Office 365 監査ログに共有イベントを記録する方法については、次のワークフローを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fe46-125">Here's the work flow for how sharing events are logged in the Office 365 audit log.</span></span> 
  
![共有の監査のしくみを示すフローチャート](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
<span data-ttu-id="3fe46-127">ユーザー (動作しているユーザー) が別のユーザー (ターゲットユーザー) とリソースを共有しようとしている場合、SharePoint (または OneDrive for business) は最初に、対象ユーザーの電子メールアドレスが組織のディレクトリ内のユーザーアカウントに関連付けられているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-127">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory.</span></span> <span data-ttu-id="3fe46-128">ターゲットユーザーが組織のディレクトリにある場合、SharePoint は次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="3fe46-128">If the target user is in the organization's directory, SharePoint does the following:</span></span>
  
-  <span data-ttu-id="3fe46-129">リソースにアクセスするためのターゲットユーザーのアクセス許可を即時に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-129">Immediately assigns the target user permissions to access the resource.</span></span> 
    
- <span data-ttu-id="3fe46-130">ターゲットユーザーの電子メールアドレスに共有通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-130">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="3fe46-131">**sharingset**イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-131">Logs a **SharingSet** event.</span></span> 
    
 <span data-ttu-id="3fe46-132">ターゲットユーザーのユーザーアカウントが組織のディレクトリにない場合、SharePoint は次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="3fe46-132">If a user account for the target user isn't in the organization's directory, SharePoint does the following:</span></span> 
  
- <span data-ttu-id="3fe46-133">共有への招待を作成し、対象ユーザーの電子メールアドレスに送信します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-133">Creates a sharing invitation and sends it to the email address of the target user.</span></span>
    
- <span data-ttu-id="3fe46-134">**SharingInvitationCreated**イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-134">Logs a **SharingInvitationCreated** event.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3fe46-135">**SharingInvitationCreated**イベントは、ターゲットユーザーが共有されているリソースにアクセスできない場合、常に外部またはゲストの共有に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-135">The **SharingInvitationCreated** event is most always associated with external or guest sharing when the target user doesn't have access to the resource that was shared.</span></span> 
  
<span data-ttu-id="3fe46-136">ターゲットユーザーが (招待のリンクをクリックすることによって) 送信された共有の招待を承諾すると、SharePoint は**SharingInvitationAccepted**イベントをログに記録し、リソースにアクセスするためのアクセス許可をターゲットユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-136">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource.</span></span> <span data-ttu-id="3fe46-137">対象ユーザーに関する追加情報も記録されます。たとえば、招待状が送信されたユーザーの id や、招待を実際に受諾したユーザーなどが記録されます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-137">Additional information about the target user is also logged, such as the identity of the user that the invitation was sent to and the user who actually accepted the invitation.</span></span> <span data-ttu-id="3fe46-138">場合によっては、これらのユーザー (またはメールアドレス) が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3fe46-138">In some case, these users (or email addresses) might be different.</span></span> 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="3fe46-139">外部ユーザーと共有されるリソースを特定する方法</span><span class="sxs-lookup"><span data-stu-id="3fe46-139">How to identify resources shared with external users</span></span>

<span data-ttu-id="3fe46-140">管理者にとって一般的な要件は、組織外のユーザーと共有されているすべてのリソースの一覧を作成することです。</span><span class="sxs-lookup"><span data-stu-id="3fe46-140">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization.</span></span> <span data-ttu-id="3fe46-141">Office 365 で共有監査を使用すると、管理者がこのリストを生成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3fe46-141">By using sharing auditing in Office 365, administrators can now generate this list.</span></span> <span data-ttu-id="3fe46-142">ここでは、使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-142">Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="3fe46-143">手順 1: 共有イベントを検索し、結果を CSV ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="3fe46-143">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="3fe46-144">最初の手順として、Office 365 監査ログで共有イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-144">The first step is to search the Office 365 audit log for sharing events.</span></span> <span data-ttu-id="3fe46-145">監査ログの検索に関する詳細 (必要なアクセス許可を含む) については、「 [Security & コンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fe46-145">For more details (including the required permissions) about searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="3fe46-146">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-146">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="3fe46-147">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="3fe46-147">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="3fe46-148">セキュリティ & コンプライアンスセンターの左側のウィンドウで、[**検索**  > **監査ログの検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3fe46-148">In the left pane of the Security & Compliance Center, click **Search**  > **Audit log search**.</span></span>
    
    <span data-ttu-id="3fe46-149">[**監査ログの検索**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-149">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="3fe46-150">[**アクティビティ**] の [**共有アクティビティ**] をクリックして、共有イベントのみを検索します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-150">Under **Activities**, click **Sharing activities** to search only for sharing events.</span></span> 
    
    ![[アクティビティ] で、[共有アクティビティ] を選択します。](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="3fe46-152">日付と時刻の範囲を選択して、その期間内に発生した共有イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-152">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="3fe46-153">[**検索**] をクリックして検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-153">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="3fe46-154">検索の実行が完了し、結果が表示されたら、[**結果** \>のエクスポート] をクリックして**すべての結果をダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-154">When the search is finished running and the results are displayed , click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="3fe46-155">[エクスポート] オプションを選択すると、CSV ファイルを開いたり保存したりするように求めるメッセージがウィンドウの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-155">After you select the export option, a message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="3fe46-156">[名前を付け**て**保存] をクリックし、CSV ファイルをローカルコンピューター上のフォルダーに保存します。 \*\*\*\* \></span><span class="sxs-lookup"><span data-stu-id="3fe46-156">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="3fe46-157">手順 2: 外部ユーザーと共有しているリソースの CSV ファイルをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="3fe46-157">Step 2: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="3fe46-158">次の手順では、 **sharingset**イベントと**SharingInvitationCreated**イベントに対して CSV をフィルター処理し、 **TargetUserOrGroupType**プロパティが**Guest**であるイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-158">The next step is to filter the CSV for the **SharingSet** and **SharingInvitationCreated** events, and to display those events where the **TargetUserOrGroupType** property is **Guest**.</span></span> <span data-ttu-id="3fe46-159">これを行うには、Excel の Power Query 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-159">You'll use the Power Query feature in Excel to do this.</span></span> <span data-ttu-id="3fe46-160">Excel 2016 では、次の手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-160">The following procedure is performed in Excel 2016.</span></span> 
  
1. <span data-ttu-id="3fe46-161">Excel 2016 で、空のブックを開きます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-161">In Excel 2016, open a blank workbook.</span></span>
    
2. <span data-ttu-id="3fe46-162">[**データ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3fe46-162">Click the **Data** tab.</span></span> 
    
3. <span data-ttu-id="3fe46-163">[ \> **ファイルからの\*\*\*\*新しいクエリ** \> ]**を [CSV から] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="3fe46-163">Click **New Query** \> **From file** \> **From CSV**.</span></span>
    
    ![[データ] タブで、[新しいクエリ] を選択し、[ファイルから] を選択してから、[CSV から] を選択します。](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. <span data-ttu-id="3fe46-165">手順1でダウンロードした CSV ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-165">Open the CSV file that you downloaded in Step 1.</span></span>
    
    <span data-ttu-id="3fe46-166">CSV ファイルがクエリエディターで開かれます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-166">The CSV file is opened in the Query Editor.</span></span> <span data-ttu-id="3fe46-167">**Time**、 **User**、 **Action**、 **Detail**という4つの列があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3fe46-167">Note that there are four columns: **Time**, **User**, **Action**, and **Detail**.</span></span> <span data-ttu-id="3fe46-168">**詳細**列は複数のプロパティフィールドです。</span><span class="sxs-lookup"><span data-stu-id="3fe46-168">The **Detail** column is a multi-property field.</span></span> <span data-ttu-id="3fe46-169">次の手順では、**詳細**列の各プロパティに対して新しい列を作成します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-169">The next step is to create a new column for each of the properties in the **Detail** column.</span></span> 
    
5. <span data-ttu-id="3fe46-170">**詳細**列を選択し、[**ホーム**] タブの [**区切り記号で\*\*\*\*列** \>を分割] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3fe46-170">Select the **Detail** column, and then on the **Home** tab, click **Split Column** \> **By Delimiter**.</span></span>
    
    ![[ホーム] タブの [分割列] をクリックし、[区切り記号] をクリックします。](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. <span data-ttu-id="3fe46-172">[**区切り記号で分割**した列] ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3fe46-172">In the **Split Column by Delimiter** window, do the following:</span></span> 
    
      - <span data-ttu-id="3fe46-173">[ **select or enter delimiter**] で、[**コンマ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-173">Under **Select or enter delimiter**, select **Comma**.</span></span>
    
      - <span data-ttu-id="3fe46-174">[**分割**] で、**区切り記号が出現するたびに**[] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-174">Under **Split**, select **At each occurrence of the delimiter**.</span></span>
    
7. <span data-ttu-id="3fe46-175">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3fe46-175">Click **OK**.</span></span>
    
    <span data-ttu-id="3fe46-176">**詳細**列は複数の列に分割されます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-176">The **Detail** column is split into multiple columns.</span></span> <span data-ttu-id="3fe46-177">各新しい列には、詳細について説明します。 **1**、 **2**、 **3**というように指定します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-177">Each new column is named **Detail.1**, **Detail.2**, **Detail.3**, and so on.</span></span> <span data-ttu-id="3fe46-178">詳細については、各セルの値を確認**してください。 n**列の先頭には、プロパティの名前が付きます。たとえば、 **operation: sharingset**、 **operation: SharingInvitationAccepted**、 **operation: SharingInvitationCreated**。</span><span class="sxs-lookup"><span data-stu-id="3fe46-178">You'll notice the values in each cell in the **Detail.n** columns are prefixed with the name of the property; for example, **Operation:SharingSet**, **Operation:SharingInvitationAccepted**, and **Operation:SharingInvitationCreated**.</span></span>
    
    ![詳細列は、プロパティごとに1つずつ、複数の列に分割されます。](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. <span data-ttu-id="3fe46-180">[**ファイル**] タブの [**読み込み&amp;を閉じる**] をクリックして、クエリエディターを閉じ、Excel ブックでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-180">On the **File** tab, click **Close &amp; Load** to close the Query Editor and open the file in an Excel workbook.</span></span> 
    
    <span data-ttu-id="3fe46-181">次の手順では、 **sharingset**および**SharingInvitationCreated**イベントのみを表示するようにファイルをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-181">The next step is to filter the file to only display the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
9. <span data-ttu-id="3fe46-182">[**ホーム**] タブに移動して、[**アクション**] 列を選択します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-182">Go to the **Home** tab, and then select the **Action** column.</span></span> 
    
10. <span data-ttu-id="3fe46-183">[**並べ替え&amp;フィルター** ] ドロップダウンリストで、すべての選択を解除し、[ **sharingset** ] と [ **SharingInvitationCreated**] を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3fe46-183">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **SharingSet** and **SharingInvitationCreated**, and click **OK**.</span></span>
    
    <span data-ttu-id="3fe46-184">**sharingset**および**SharingInvitationCreated**イベントの行が Excel に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-184">Excel displays the rows for the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
11. <span data-ttu-id="3fe46-185">[ **Detail** ] (または [ **TargetUserOrGroupType** ] プロパティを含む列) という名前の列に移動し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-185">Go to the column named **Detail.17** (or whichever column contains the **TargetUserOrGroupType** property) and select it.</span></span> 
    
12. <span data-ttu-id="3fe46-186">[**並べ替え&amp;フィルター** ] ドロップダウンリストで、すべての選択を解除し、[ **TargetUserOrGroupType: Guest**] を選択して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3fe46-186">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **OK**.</span></span>
    
    <span data-ttu-id="3fe46-187">ここでは、外部ユーザーが**TargetUserOrGroupType: Guest**という値で識別されるため、 **SharingInvitationCreated**および**sharingset**イベントの行と、ターゲットユーザーが組織外にある場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3fe46-187">Now Excel displays the rows for **SharingInvitationCreated** and **SharingSet** events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
    
<span data-ttu-id="3fe46-188">次の表に、指定された日付範囲内のゲストユーザーとリソースを共有している、組織内のすべてのユーザーを示します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-188">The following table shows all users in the organization who shared resources with a guest user within a specified date range.</span></span>
  
![Office での共有イベント365監査ログ](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
<span data-ttu-id="3fe46-190">上記の表には含まれていませんが、 **10**列 (または**ObjectId**プロパティを含む列) は、ターゲットユーザーと共有していたリソースを識別します。例`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`を示します。</span><span class="sxs-lookup"><span data-stu-id="3fe46-190">Although it's not included in the previous table, the **Detail.10** column (or whichever column contains the **ObjectId** property) identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
  
> [!TIP]
> <span data-ttu-id="3fe46-191">ゲストユーザーが実際にリソースにアクセスするためのアクセス許可が割り当てられているかどうかを確認するには (リソースと共有しているリソースだけでなく)、手順10、11、12を繰り返し、 **SharingInvitationAccepted**と sharingset でフィルター処理します。 \*\*\*\* 手順10のイベント</span><span class="sxs-lookup"><span data-stu-id="3fe46-191">If you want to identify when a guest user was actually assigned permissions to access a resource (as opposed to just the resources that where shared with them), repeat Steps 10, 11, and 12, and filter on the **SharingInvitationAccepted** and **SharingSet** events in Step 10.</span></span> 
