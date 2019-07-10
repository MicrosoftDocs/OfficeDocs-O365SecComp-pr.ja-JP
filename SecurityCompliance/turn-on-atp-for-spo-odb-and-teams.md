---
title: SharePoint、OneDrive、Microsoft Teams の Office 365 ATP を有効にする
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
description: 検出されたファイルに対して通知を設定する方法など、SharePoint、OneDrive、Teams の ATP を有効にする方法について説明します。
ms.openlocfilehash: c4146ce97f09723a8da543b84dc57bc522581001
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600283"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="0227d-103">SharePoint、OneDrive、Microsoft Teams の Office 365 ATP を有効にする</span><span class="sxs-lookup"><span data-stu-id="0227d-103">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0227d-104">この記事は、 [Office 365 Advanced Threat Protection](office-365-atp.md)を使用しているビジネスのお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="0227d-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="0227d-105">Outlook の安全なリンクに関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0227d-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="0227d-106">[Office 365 ATP For SharePoint、OneDrive、Microsoft Teams では](atp-for-spo-odb-and-teams.md)、組織が悪意のあるファイルを誤って共有することを防止します。</span><span class="sxs-lookup"><span data-stu-id="0227d-106">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="0227d-107">悪意のあるファイルが検出されると、そのファイルはブロックされるようになり、組織のセキュリティチームによって追加の操作が行われるまで、そのファイルを開いたり、コピー、移動、または共有することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="0227d-107">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="0227d-108">この記事では、SharePoint、OneDrive、Teams の ATP を有効にし、検出されたファイルについて通知する通知を設定し、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0227d-108">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span> 
  
<span data-ttu-id="0227d-109">ATP ポリシーを定義 (または編集) するには、適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0227d-109">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="0227d-110">次の表では、いくつかの例について説明します。</span><span class="sxs-lookup"><span data-stu-id="0227d-110">Some examples are described in the following table:</span></span>

|<span data-ttu-id="0227d-111">役割</span><span class="sxs-lookup"><span data-stu-id="0227d-111">Role</span></span>  |<span data-ttu-id="0227d-112">参照先/割り当て方法</span><span class="sxs-lookup"><span data-stu-id="0227d-112">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="0227d-113">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="0227d-113">Office 365 Global Administrator</span></span> |<span data-ttu-id="0227d-p104">Office 365 の購入へのサインアップをする場合、既定ではグローバル管理者になります。詳細については、「[Office 365 の管理者の役割について](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0227d-p104">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="0227d-116">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="0227d-116">Security Administrator</span></span> |<span data-ttu-id="0227d-117">Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="0227d-117">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="0227d-118">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="0227d-118">Exchange Online Organization Management</span></span> |<span data-ttu-id="0227d-119">Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="0227d-119">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="0227d-120">または</span><span class="sxs-lookup"><span data-stu-id="0227d-120">or</span></span> <br>  <span data-ttu-id="0227d-121">PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="0227d-121">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="0227d-122">SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする</span><span class="sxs-lookup"><span data-stu-id="0227d-122">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="0227d-123">**この手順を開始する前に、Office 365 環境の監査ログが既に有効になっていることを確認して**ください。</span><span class="sxs-lookup"><span data-stu-id="0227d-123">**Before you begin this procedure, make sure that audit logging is already turned on for your Office 365 environment**.</span></span> <span data-ttu-id="0227d-124">これは、通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="0227d-124">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="0227d-125">詳細については、「 [Office 365 監査ログ検索をオンまたはオフにする](turn-audit-log-search-on-or-off.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0227d-125">For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>
  
1. <span data-ttu-id="0227d-126">に[https://protection.office.com](https://protection.office.com)移動し、職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="0227d-126">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="0227d-127">Office 365 &amp;セキュリティ/コンプライアンスセンターの左側のナビゲーションウィンドウで、[**脅威の管理**] の下にある [**ポリシー** \>の**安全な添付ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0227d-127">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span> <br/><span data-ttu-id="0227d-128">![セキュリティ&amp; /コンプライアンスセンターで、[脅威管理\>ポリシー] を選択します。](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span><span class="sxs-lookup"><span data-stu-id="0227d-128">![In the Security &amp; Compliance Center, choose Threat management \> Policy](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span></span>
  
3. <span data-ttu-id="0227d-129">[ **SharePoint、OneDrive、Microsoft Teams に対して ATP を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0227d-129">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span><br/><span data-ttu-id="0227d-130">![SharePoint Online、OneDrive for Business、Microsoft Teams の Advanced Threat Protection を有効にします。](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span><span class="sxs-lookup"><span data-stu-id="0227d-130">![Turn on Advanced Threat Protection for SharePoint Online, OneDrive for Business, and Microsoft Teams](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span></span>
  
4. <span data-ttu-id="0227d-131">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0227d-131">Click **Save**.</span></span>
    
5. <span data-ttu-id="0227d-132">組織の[安全な添付ファイルポリシー](set-up-atp-safe-attachments-policies.md)と[安全なリンクのポリシー](set-up-atp-safe-links-policies.md)を確認し、必要に応じて編集します。</span><span class="sxs-lookup"><span data-stu-id="0227d-132">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>
    
6. <span data-ttu-id="0227d-133">勧めグローバル管理者または SharePoint Online 管理者として、 **DisallowInfectedFileDownload**パラメーターを*true*に設定して**[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="0227d-133">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true*.</span></span> <br/>
      - <span data-ttu-id="0227d-134">このパラメーターを*true*に設定すると、検出されたファイルのすべてのアクション (削除を除く) がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="0227d-134">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="0227d-135">ユーザーは、検出されたファイルを開いたり、移動、コピー、または共有したりできません。</span><span class="sxs-lookup"><span data-stu-id="0227d-135">People cannot open, move, copy, or share detected files.</span></span>
      - <span data-ttu-id="0227d-136">パラメーターを*false*に設定すると、削除とダウンロード以外のすべてのアクションがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="0227d-136">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="0227d-137">ユーザーは、リスクを容認し、検出されたファイルをダウンロードすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0227d-137">People can choose to accept the risk and download a detected file.</span></span>  
   
7. <span data-ttu-id="0227d-138">変更がすべての Office 365 データセンターに蔓延するまで最大30分かかります。</span><span class="sxs-lookup"><span data-stu-id="0227d-138">Allow up to 30 minutes for your changes to spread to all Office 365 datacenters.</span></span>
    
8. <span data-ttu-id="0227d-139">勧め検出されたファイルの通知の設定に進みます。</span><span class="sxs-lookup"><span data-stu-id="0227d-139">(Recommended) Proceed to set up alerts for detected files.</span></span>
    
<span data-ttu-id="0227d-140">Office 365 での PowerShell の使用の詳細については、「 [Manage office 365 With powershell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0227d-140">To learn more about using PowerShell with Office 365, see [Manage Office 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span> 

<span data-ttu-id="0227d-141">ファイルが悪意のあるものとして検出された場合のユーザーの操作の詳細については、「 [SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが検出された場合の対処](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0227d-141">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span> 
  
## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="0227d-142">検出されたファイルの通知を設定する</span><span class="sxs-lookup"><span data-stu-id="0227d-142">Set up alerts for detected files</span></span>

<span data-ttu-id="0227d-143">SharePoint Online、OneDrive for Business、または Microsoft Teams のファイルが悪意のあるものとして識別された場合に通知を受け取るには、警告を設定します。</span><span class="sxs-lookup"><span data-stu-id="0227d-143">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>
  
1. <span data-ttu-id="0227d-144">[Office 365 セキュリティ&amp; /コンプライアンスセンター](https://protection.office.com)で、[ \*\*\*\* \>警告の**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0227d-144">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>
    
2. <span data-ttu-id="0227d-145">[**新しい通知ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0227d-145">Choose **New alert policy**.</span></span>
    
3. <span data-ttu-id="0227d-146">通知の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0227d-146">Specify a name for the alert.</span></span> <span data-ttu-id="0227d-147">たとえば、ライブラリに悪意のあるファイルを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="0227d-147">For example, you could type Malicious Files in Libraries.</span></span>
    
4. <span data-ttu-id="0227d-148">通知の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="0227d-148">Type a description for the alert.</span></span> <span data-ttu-id="0227d-149">たとえば、SharePoint Online、OneDrive、Microsoft Teams で悪意のあるファイルが検出されたときに管理者に通知を入力できます。</span><span class="sxs-lookup"><span data-stu-id="0227d-149">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
    
5. <span data-ttu-id="0227d-150">[**この通知を送信するタイミング**] セクションで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0227d-150">In the **Send this alert when...** section, do the following:</span></span> 
    
    <span data-ttu-id="0227d-151">a.</span><span class="sxs-lookup"><span data-stu-id="0227d-151">a.</span></span> <span data-ttu-id="0227d-152">[**アクティビティ**] リストで、[**検出されたマルウェア (ファイル内**)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0227d-152">In the **Activities** list, choose **Detected malware in file**.</span></span>
    
    <span data-ttu-id="0227d-153">b.</span><span class="sxs-lookup"><span data-stu-id="0227d-153">b.</span></span> <span data-ttu-id="0227d-154">[**ユーザー** ] フィールドは空のままにします。</span><span class="sxs-lookup"><span data-stu-id="0227d-154">Leave the **Users** field empty.</span></span> 
    
6. <span data-ttu-id="0227d-155">[**この通知を送信する**ユーザー...] セクションで、悪意のあるファイルが検出されたときに通知を受信する必要がある1つ以上のグローバル管理者、セキュリティ管理者、またはセキュリティ閲覧者を選択します。</span><span class="sxs-lookup"><span data-stu-id="0227d-155">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span> 
    
7. <span data-ttu-id="0227d-156">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0227d-156">Click **Save**.</span></span>
    
<span data-ttu-id="0227d-157">通知の詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターでアクティビティ通知を作成](create-activity-alerts.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0227d-157">To learn more about alerts, see [Create activity alerts in the Office 365 Security &amp; Compliance Center](create-activity-alerts.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="0227d-158">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0227d-158">Next steps</span></span>

1. [<span data-ttu-id="0227d-159">SharePoint、OneDrive、Microsoft Teams で検出された悪意のあるファイルに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="0227d-159">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [<span data-ttu-id="0227d-160">Office 365 の管理者として検疫済みメッセージおよびファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="0227d-160">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
    

  

