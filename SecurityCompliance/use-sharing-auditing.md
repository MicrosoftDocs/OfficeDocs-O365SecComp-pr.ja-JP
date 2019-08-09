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
ms.collection: M365-security-compliance
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: '共有は、SharePoint Online と OneDrive for business の主要なアクティビティです。 管理者は、Office 365 監査ログで共有監査を使用して、組織外のユーザーと共有しているリソースを識別できるようになりました。 '
ms.openlocfilehash: 54fa32ec9ed16a65354eb845421c56f6d58559e4
ms.sourcegitcommit: c8ea7c0900e69e69bd5c735960df70aae27690a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "36258570"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a><span data-ttu-id="622e7-104">共有を監査して外部ユーザーと共有されているリソースを見つける</span><span class="sxs-lookup"><span data-stu-id="622e7-104">Use sharing auditing in the Office 365 audit log</span></span>

<span data-ttu-id="622e7-105">共有は、SharePoint Online と OneDrive for business の主要なアクティビティであり、Office 365 組織で広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="622e7-105">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in Office 365 organizations.</span></span> <span data-ttu-id="622e7-106">管理者は、Office 365 監査ログで共有監査を使用して、組織での共有の使用方法を決定できます。</span><span class="sxs-lookup"><span data-stu-id="622e7-106">Administrators can use sharing auditing in the Office 365 audit log to determine how sharing is used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="622e7-107">SharePoint 共有スキーマ</span><span class="sxs-lookup"><span data-stu-id="622e7-107">The SharePoint Sharing schema</span></span>

<span data-ttu-id="622e7-108">共有イベント (共有ポリシーと共有リンクに関連するイベントは含まれません) は、1人のユーザーが別のユーザーに影響を与えるアクションを実行しているという主な方法で、ファイルとフォルダーに関連するイベントとは異なります。</span><span class="sxs-lookup"><span data-stu-id="622e7-108">Sharing events (not including events related to sharing policy and sharing links) are different from file- and folder-related events in one primary way: one user is performing an action that has an effect on another user.</span></span> <span data-ttu-id="622e7-109">たとえば、リソースユーザー A がファイルへのアクセス権をユーザー B に付与したとします。</span><span class="sxs-lookup"><span data-stu-id="622e7-109">For example, when a resource User A gives User B access to a file.</span></span> <span data-ttu-id="622e7-110">この例では、ユーザー A は、動作している*ユーザー*で、ユーザー B は*対象ユーザー*です。</span><span class="sxs-lookup"><span data-stu-id="622e7-110">In this example, User A is the  *acting user*  and User B is the  *target user*.</span></span> <span data-ttu-id="622e7-111">SharePoint ファイルスキーマでは、動作しているユーザーの操作だけがファイル自体に影響します。</span><span class="sxs-lookup"><span data-stu-id="622e7-111">In the SharePoint File schema, the acting user's action only affects the file itself.</span></span> <span data-ttu-id="622e7-112">ユーザーがファイルを開くと、 **Fileaccessed**イベントに必要な情報は、動作しているユーザーのみになります。</span><span class="sxs-lookup"><span data-stu-id="622e7-112">When User A opens a file, the only information needed in the **FileAccessed** event is the acting user.</span></span> <span data-ttu-id="622e7-113">この違いに対処するために、共有イベントに関する詳細情報を収集する、 *SharePoint 共有スキーマ*と呼ばれる別のスキーマがあります。</span><span class="sxs-lookup"><span data-stu-id="622e7-113">To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events.</span></span> <span data-ttu-id="622e7-114">これにより、管理者がリソースを共有しているユーザーや、リソースが共有されていたユーザーを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="622e7-114">This ensures that administrators have visibility into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="622e7-115">共有スキーマは、イベントの共有に関連する監査レコードに2つの追加フィールドを提供します。</span><span class="sxs-lookup"><span data-stu-id="622e7-115">The Sharing schema provides two additional fields in an audit record related to sharing events:</span></span> 
  
- <span data-ttu-id="622e7-116">**TargetUserOrGroupType:** 対象のユーザーまたはグループが、Member、Guest、SharePointGroup、Microsoft.rtc.management.writableconfig.settings.centralizedlogging.securitygroup、または Partner であるかどうかを識別します。</span><span class="sxs-lookup"><span data-stu-id="622e7-116">**TargetUserOrGroupType:** Identifies whether the target user or group is a Member, Guest, SharePointGroup, SecurityGroup, or Partner.</span></span>

- <span data-ttu-id="622e7-117">**Targetuserorgroupname:** リソースが共有されていたターゲットユーザーまたはグループの UPN または名前を格納します (前の例では User B)。</span><span class="sxs-lookup"><span data-stu-id="622e7-117">**TargetUserOrGroupName:** Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 

<span data-ttu-id="622e7-118">これら2つのフィールドは、ユーザー、操作、日付などの Office 365 監査ログスキーマの他のプロパティに加えて、*どの*ユーザーがどのリソースを*どのよう*な\*\* *とき*に共有したかについての完全なストーリーを伝えることができます。</span><span class="sxs-lookup"><span data-stu-id="622e7-118">These two fields, in addition to other properties from the Office 365 audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="622e7-119">共有ストーリーにとって重要なスキーマプロパティは他にもあります。</span><span class="sxs-lookup"><span data-stu-id="622e7-119">There's another schema property that's important to the sharing story.</span></span> <span data-ttu-id="622e7-120">監査ログの検索結果をエクスポートすると、エクスポートされた CSV ファイルの**Auditdata**列に、共有イベントに関する情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="622e7-120">When you export audit log search results, the **AuditData** column in the exported CSV file stores information about sharing events.</span></span> <span data-ttu-id="622e7-121">たとえば、ユーザーが別のユーザーとサイトを共有する場合は、ターゲットユーザーを SharePoint グループに追加することによって実現します。</span><span class="sxs-lookup"><span data-stu-id="622e7-121">For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group.</span></span> <span data-ttu-id="622e7-122">**Auditdata**列は、管理者向けにコンテキストを提供するために、この情報を取り込みます。</span><span class="sxs-lookup"><span data-stu-id="622e7-122">The **AuditData** column captures this information to provide context for administrators.</span></span> <span data-ttu-id="622e7-123">**Auditdata**列の情報を解析する手順については、[手順 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="622e7-123">See [Step 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) for instructions on how to parse the information in the **AuditData** column.</span></span>

## <a name="sharepoint-sharing-events"></a><span data-ttu-id="622e7-124">SharePoint 共有イベント</span><span class="sxs-lookup"><span data-stu-id="622e7-124">SharePoint sharing events</span></span>

<span data-ttu-id="622e7-125">共有は、ユーザー (*動作*しているユーザー) が別のユーザー (*ターゲット*ユーザー) とリソースを共有しようとしたときに定義されます。</span><span class="sxs-lookup"><span data-stu-id="622e7-125">Sharing is defined by when a user (the *acting* user) wants to share a resource with another user (the *target* user).</span></span> <span data-ttu-id="622e7-126">外部ユーザーとのリソースの共有に関連する監査レコード (組織外のユーザーが組織の Azure Active Directory にゲストアカウントを持っていない場合) は、Office 365 に記録されている次のイベントによって識別されます。監査ログ:</span><span class="sxs-lookup"><span data-stu-id="622e7-126">Audit records related to sharing a resource with an external user (a user who is outside of your organization and doesn't have a guest account in your organization's Azure Active Directory) are identified by the following events, which are logged in the Office 365 audit log:</span></span>

- <span data-ttu-id="622e7-127">**SharingInvitationCreated:** 組織内のユーザーが外部ユーザーとリソース (通常はサイト) を共有しようとしました。</span><span class="sxs-lookup"><span data-stu-id="622e7-127">**SharingInvitationCreated:** A user in your organization tried to share a resource (likely a site) with an external user.</span></span> <span data-ttu-id="622e7-128">この結果、外部共有への招待がターゲットユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="622e7-128">This results in an external sharing invitation sent to the target user.</span></span> <span data-ttu-id="622e7-129">この時点では、リソースへのアクセスは許可されません。</span><span class="sxs-lookup"><span data-stu-id="622e7-129">No access to the resource is granted at this point.</span></span>

- <span data-ttu-id="622e7-130">**SharingInvitationAccepted:** 外部ユーザーが、動作しているユーザーによって送信された共有の招待を承諾し、リソースにアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="622e7-130">**SharingInvitationAccepted:** The external user has accepted the sharing invitation sent by the acting user and now has access to the resource.</span></span>

- <span data-ttu-id="622e7-131">**AnonymousLinkCreated:** 匿名リンク ([すべてのユーザー] リンクとも呼ばれます) は、リソースに対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="622e7-131">**AnonymousLinkCreated:** An anonymous link (also called an "Anyone" link) is created for a resource.</span></span> <span data-ttu-id="622e7-132">匿名リンクを作成してコピーすることができるので、匿名リンクが設定されているドキュメントは、ターゲットユーザーと共有していることを前提としては十分です。</span><span class="sxs-lookup"><span data-stu-id="622e7-132">Because an anonymous link can be created and then copied, it's reasonable to assume that any document that has an anonymous link has been shared with a target user.</span></span>

- <span data-ttu-id="622e7-133">**AnonymousLinkUsed:** その名前が示すように、このイベントは、匿名リンクを使用してリソースにアクセスしたときに記録されます。</span><span class="sxs-lookup"><span data-stu-id="622e7-133">**AnonymousLinkUsed:** As the name implies, this event is logged when an anonymous link is used to access a resource.</span></span> 

- <span data-ttu-id="622e7-134">**Securelinkcreated:** ユーザーが、特定のユーザーとリソースを共有するための "特定のユーザーリンク" を作成しました。</span><span class="sxs-lookup"><span data-stu-id="622e7-134">**SecureLinkCreated:** A user has created a "specific people link" to share a resource with a specific person.</span></span> <span data-ttu-id="622e7-135">このターゲットユーザーには、組織の外部にいる人がいる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="622e7-135">This target user may be someone who is external to your organization.</span></span>

- <span data-ttu-id="622e7-136">**Addedtosecurelink:** ユーザーが特定の人物リンクに追加されました。</span><span class="sxs-lookup"><span data-stu-id="622e7-136">**AddedToSecureLink:** A user was added to a specific people link.</span></span> <span data-ttu-id="622e7-137">このターゲットユーザーには、組織の外部にいる人がいる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="622e7-137">This target user may be someone who is external to your organization.</span></span>

## <a name="sharing-auditing-work-flow"></a><span data-ttu-id="622e7-138">共有監査ワークフロー</span><span class="sxs-lookup"><span data-stu-id="622e7-138">Sharing auditing work flow</span></span>
  
<span data-ttu-id="622e7-139">ユーザー (動作しているユーザー) が別のユーザー (ターゲットユーザー) とリソースを共有しようとしている場合、SharePoint (または OneDrive for Business) は最初に、対象ユーザーの電子メールアドレスが組織のディレクトリ内のユーザーアカウントに関連付けられているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="622e7-139">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory.</span></span> <span data-ttu-id="622e7-140">ターゲットユーザーがディレクトリ内にあり、対応するゲストユーザーアカウントを持っている場合、SharePoint は次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="622e7-140">If the target user is in the directory (and has a corresponding guest user account), SharePoint does the following things:</span></span>
  
-  <span data-ttu-id="622e7-141">ターゲットユーザーを適切な SharePoint グループに追加して、リソースにアクセスするためのターゲットユーザーのアクセス許可を即時に割り当て、 **Addedtogroup**イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="622e7-141">Immediately assigns the target user permissions to access the resource by adding the target user to the appropriate SharePoint group, and logs an **AddedToGroup** event.</span></span> 
    
- <span data-ttu-id="622e7-142">ターゲットユーザーの電子メールアドレスに共有通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="622e7-142">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="622e7-143">**Sharingset**イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="622e7-143">Logs a **SharingSet** event.</span></span> <span data-ttu-id="622e7-144">このイベントには、監査ログ検索ツールの [アクティビティの選択] の [**共有とアクセスの要求のアクティビティ**] の [共有ファイル、フォルダー、またはサイト] のフレンドリ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="622e7-144">This event has a friendly name of "Shared file, folder, or site" under **Sharing and access request activities** in the activities picker of the audit log search tool.</span></span> <span data-ttu-id="622e7-145">[手順 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file)のスクリーンショットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="622e7-145">See the screenshot in [Step 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file).</span></span> 
    
<span data-ttu-id="622e7-146">ターゲットユーザーのユーザーアカウントがディレクトリにない場合、SharePoint は次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="622e7-146">If a user account for the target user isn't in the directory, SharePoint does the following:</span></span> 
    
   - <span data-ttu-id="622e7-147">リソースがどのように共有されているかに基づいて、次のいずれかのイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="622e7-147">Logs one of the following events, based on how the resource is shared:</span></span>
   
      - <span data-ttu-id="622e7-148">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="622e7-148">**AnonymousLinkCreated**</span></span>
   
      - <span data-ttu-id="622e7-149">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="622e7-149">**SecureLinkCreated**</span></span>
   
      - <span data-ttu-id="622e7-150">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="622e7-150">**AddedToSecureLink**</span></span> 

      - <span data-ttu-id="622e7-151">**SharingInvitationCreated**(このイベントは、共有リソースがサイトである場合にのみ記録されます)</span><span class="sxs-lookup"><span data-stu-id="622e7-151">**SharingInvitationCreated** (this event is logged only when the shared resource is a site)</span></span>
    
   - <span data-ttu-id="622e7-152">ターゲットユーザーが (招待のリンクをクリックすることによって) 送信された共有の招待を承諾すると、SharePoint は**SharingInvitationAccepted**イベントをログに記録し、リソースにアクセスするためのアクセス許可をターゲットユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="622e7-152">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource.</span></span> <span data-ttu-id="622e7-153">ターゲットユーザーが匿名リンクを送信している場合、ターゲットユーザーがリンクを使用してリソースにアクセスした後、 **AnonymousLinkUsed**イベントがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="622e7-153">If the target user is sent an anonymous link, the **AnonymousLinkUsed** event is logged after the target user uses the link to access the resource.</span></span> <span data-ttu-id="622e7-154">セキュリティで保護され\*\*\*\* たリンクの場合、外部ユーザーがリンクを使用してリソースにアクセスするときに、fileaccessed イベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="622e7-154">For secure links, a **FileAccessed** event is logged when an external user uses the link to access the resource.</span></span>

<span data-ttu-id="622e7-155">対象ユーザーに関する追加情報もログに記録されます。たとえば、招待が行われるユーザーの id や、実際に招待を承諾したユーザーなどが記録されます。</span><span class="sxs-lookup"><span data-stu-id="622e7-155">Additional information about the target user is also logged, such as the identity of the user that the invitation is to and the user who actually accepts the invitation.</span></span> <span data-ttu-id="622e7-156">場合によっては、これらのユーザー (またはメールアドレス) が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="622e7-156">In some case, these users (or email addresses) can be different.</span></span> 

## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="622e7-157">外部ユーザーと共有されるリソースを特定する方法</span><span class="sxs-lookup"><span data-stu-id="622e7-157">How to identify resources shared with external users</span></span>

<span data-ttu-id="622e7-158">管理者にとって一般的な要件は、組織外のユーザーと共有されているすべてのリソースの一覧を作成することです。</span><span class="sxs-lookup"><span data-stu-id="622e7-158">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization.</span></span> <span data-ttu-id="622e7-159">Office 365 で共有監査を使用すると、管理者はこの一覧を生成できます。</span><span class="sxs-lookup"><span data-stu-id="622e7-159">By using sharing auditing in Office 365, administrators can generate this list.</span></span> <span data-ttu-id="622e7-160">ここでは、使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="622e7-160">Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="622e7-161">手順 1: 共有イベントを検索し、結果を CSV ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="622e7-161">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="622e7-162">最初の手順として、Office 365 監査ログで共有イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="622e7-162">The first step is to search the Office 365 audit log for sharing events.</span></span> <span data-ttu-id="622e7-163">監査ログの検索に関する詳細 (必要なアクセス許可を含む) については、「[セキュリティ & のコンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="622e7-163">For more information (including the required permissions) about searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="622e7-164">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="622e7-164">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="622e7-165">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="622e7-165">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="622e7-166">セキュリティ & コンプライアンスセンターの左側のウィンドウで、[**検索**  > **監査ログの検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="622e7-166">In the left pane of the Security & Compliance Center, click **Search**  > **Audit log search**.</span></span>
    
    <span data-ttu-id="622e7-167">[**監査ログの検索**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="622e7-167">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="622e7-168">[**アクティビティ**] の下の [**共有とアクセス要求アクティビティ**] をクリックして、共有関連イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="622e7-168">Under **Activities**, click **Sharing and access request activities** to search for sharing-related events.</span></span> 
    
    ![[アクティビティ] の下で、[共有とアクセスの要求のアクティビティ] を選択します。](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="622e7-170">日付と時刻の範囲を選択して、その期間内に発生した共有イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="622e7-170">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="622e7-171">[**検索**] をクリックして検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="622e7-171">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="622e7-172">検索の実行が完了し、結果が表示されたら、[**結果** \>のエクスポート] をクリックして**すべての結果をダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="622e7-172">When the search is finished running and the results are displayed, click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="622e7-173">[エクスポート] オプションを選択すると、CSV ファイルを開いたり保存したりするように求めるメッセージがウィンドウの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="622e7-173">After you select the export option, a message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="622e7-174">[名前を付け**て**保存] をクリックし、CSV ファイルをローカルコンピューター上のフォルダーに保存します。 \*\*\*\* \></span><span class="sxs-lookup"><span data-stu-id="622e7-174">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a><span data-ttu-id="622e7-175">手順 2: PowerQuery Editor を使用して、エクスポートされた監査ログを書式設定する</span><span class="sxs-lookup"><span data-stu-id="622e7-175">Step 2: Use the PowerQuery Editor to format the exported audit log</span></span>

<span data-ttu-id="622e7-176">次の手順では、Excel の Power Query エディターで JSON 変換機能を使用して、 **Auditdata**列 (複数のプロパティを持つ JSON オブジェクトから構成される) の各プロパティをそれぞれの列に分割します。</span><span class="sxs-lookup"><span data-stu-id="622e7-176">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the **AuditData** column (which consists of a multi-property JSON object) into its own column.</span></span> <span data-ttu-id="622e7-177">これにより、共有に関連するレコードを表示するための列をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="622e7-177">This lets you filter columns to view records related to sharing</span></span>

<span data-ttu-id="622e7-178">詳細な手順については、「[エクスポート、構成、および監査ログレコードの表示](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)」の「手順 2: エクスポートされた監査ログを Power Query エディターを使用して書式設定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="622e7-178">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="622e7-179">手順 3: 外部ユーザーと共有しているリソースの CSV ファイルをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="622e7-179">Step 3: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="622e7-180">次の手順では、 [SharePoint 共有イベント](#sharepoint-sharing-events)セクションに記載されている、さまざまな共有関連イベントに対して CSV をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="622e7-180">The next step is to filter the CSV for the different sharing-related events that were previously described in the [SharePoint sharing events](#sharepoint-sharing-events) section.</span></span> <span data-ttu-id="622e7-181">または、 **TargetUserOrGroupType**列をフィルター処理して、このプロパティの値が**Guest**になっているすべてのレコードを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="622e7-181">Alternatively, you can filter the **TargetUserOrGroupType** column to display all records where the value of this property is **Guest**.</span></span> 

<span data-ttu-id="622e7-182">前の手順の手順に従って、PowerQuery エディターを使用して CSV ファイルを準備した後、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="622e7-182">After you've followed the instructions in the previous step to prepare the CSV file by using the PowerQuery editor, do the following:</span></span>
    
1. <span data-ttu-id="622e7-183">手順2で作成した Excel ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="622e7-183">Open the Excel file that you created in Step 2.</span></span> 

2. <span data-ttu-id="622e7-184">[**ホーム**] タブで、[**並べ替え & フィルター**] をクリックし、[**フィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="622e7-184">On the **Home** tab, click **Sort & Filter**, and then click **Filter**.</span></span>
    
3. <span data-ttu-id="622e7-185">[**操作**] 列の [**並べ替え & フィルター** ] ボックスの一覧で、すべての選択をオフにし、次に共有関連のイベントを1つ以上選択して、[ **Ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="622e7-185">In the **Sort & Filter** dropdown list on the **Operations** column, clear all selections, then select one or more the following sharing-related events and then click **Ok**.</span></span>
 
   - <span data-ttu-id="622e7-186">**SharingInvitationCreated**</span><span class="sxs-lookup"><span data-stu-id="622e7-186">**SharingInvitationCreated**</span></span>
   
   - <span data-ttu-id="622e7-187">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="622e7-187">**AnonymousLinkCreated**</span></span>
   
   - <span data-ttu-id="622e7-188">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="622e7-188">**SecureLinkCreated**</span></span>
   
   - <span data-ttu-id="622e7-189">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="622e7-189">**AddedToSecureLink**</span></span> 
    
    <span data-ttu-id="622e7-190">Excel には、選択したイベントの行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="622e7-190">Excel displays the rows for the events you selected.</span></span>
    
4. <span data-ttu-id="622e7-191">**TargetUserOrGroupType**という名前の列に移動し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="622e7-191">Go to the column named **TargetUserOrGroupType** and select it.</span></span> 
    
5. <span data-ttu-id="622e7-192">[**並べ替え & フィルター** ] ドロップダウンリストで、すべての選択をオフにし、[ **TargetUserOrGroupType: Guest**] を選択して、[ **Ok**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="622e7-192">In the **Sort & Filter** dropdown list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **Ok**.</span></span>
    
    <span data-ttu-id="622e7-193">ここでは、外部ユーザーは**TargetUserOrGroupType: GUEST**という値で識別されるため、共有イベントの行と、対象ユーザーが組織外にある場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="622e7-193">Now Excel displays the rows for sharing events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
  
> [!TIP]
> <span data-ttu-id="622e7-194">表示されている監査レコードについては、 **ObjectId**列に、ターゲットユーザーと共有されているリソースが示されます。例`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`を示します。</span><span class="sxs-lookup"><span data-stu-id="622e7-194">For the audit records that are displayed, the **ObjectId** column identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
