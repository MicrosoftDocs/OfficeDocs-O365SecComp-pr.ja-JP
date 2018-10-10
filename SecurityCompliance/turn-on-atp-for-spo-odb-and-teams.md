---
title: SharePoint、OneDrive、およびマイクロソフトのチームに対して Office 365 の分析ツールを有効に
ms.author: derng
author: derng
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
description: SharePoint、OneDrive、および検出されたファイルについての警告を設定する方法など、チーム分析ツールを有効にする方法を説明します。
ms.openlocfilehash: eb3687f6afd2e7f9a3698944019bcdb8dcbff5ae
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454294"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="86d1e-103">SharePoint、OneDrive、およびマイクロソフトのチームに対して Office 365 の分析ツールを有効に</span><span class="sxs-lookup"><span data-stu-id="86d1e-103">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="86d1e-p101">[SharePoint、OneDrive、およびマイクロソフトのチームの office 365 の分析ツール](atp-for-spo-odb-and-teams.md)は、悪意のあるファイルを誤って共有から組織を保護します。悪意のあるファイルが検出されると、そのファイルを開く、コピー、移動、またはそれ以降の操作は、組織のセキュリティ チームによって実行されるまで、共有できる誰にするためにブロックされます。SharePoint の分析ツールを有効にするには、この資料を参照するには、OneDrive、チーム、検出されたファイルを通知する警告を設定し、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="86d1e-p101">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files. When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team. Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span> 
  
<span data-ttu-id="86d1e-107">この資料で説明するタスクを実行するために Office 365 では、セキュリティでの割り当てに必要なアクセス許可が必要&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="86d1e-107">In order to perform the tasks described in this article, you must have the necessary permissions assigned in Office 365 and in the Security &amp; Compliance Center.</span></span>
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="86d1e-108">ATP を SharePoint、OneDrive、Microsoft Teams で有効にする</span><span class="sxs-lookup"><span data-stu-id="86d1e-108">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

 <span data-ttu-id="86d1e-p102">**この手順を開始する前に、監査ログが有効になって、Office 365 環境の確認**をします。これは通常、Exchange のオンラインを割り当てられている監査ログのロールを持つユーザーによって行います。詳細については、[オンまたはオフ、Office 365 を有効にする監査ログの検索](turn-audit-log-search-on-or-off.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86d1e-p102">**Before you begin this procedure, make sure that audit logging is already turned on for your Office 365 environment**. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>
  
1. <span data-ttu-id="86d1e-112">グローバル管理者またはセキュリティ管理者には、 [https://protection.office.com](https://protection.office.com)、および、職場、学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="86d1e-112">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="86d1e-113">Office 365 のセキュリティで&amp;コンプライアンス センターでは、**脅威の管理**の下で、左側のナビゲーション ペインで**ポリシー**を選択する\>**安全な添付ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="86d1e-113">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>
    
    ![セキュリティ&amp;コンプライアンス センターでは、脅威の管理を選択して\>ポリシー](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)
  
3. <span data-ttu-id="86d1e-115">**SharePoint、OneDrive、およびマイクロソフトのチームの分析ツールを有効にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="86d1e-115">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>
    
    ![オンライン、ビジネス、およびマイクロソフトのチームの OneDrive の SharePoint の高度な脅威保護を有効に](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)
  
4. <span data-ttu-id="86d1e-117">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="86d1e-117">Click **Save**.</span></span>
    
5. <span data-ttu-id="86d1e-118">確認 (および、必要に応じて編集)、組織の[安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)と[ポリシーの安全なリンク](set-up-atp-safe-links-policies.md)です。</span><span class="sxs-lookup"><span data-stu-id="86d1e-118">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>
    
6. <span data-ttu-id="86d1e-119">(推奨)グローバル管理者または SharePoint Online 管理者は、 **DisallowInfectedFileDownload**パラメーターが*true*に設定を使用して**[セット SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="86d1e-119">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true*  .</span></span> <br/><span data-ttu-id="86d1e-p103">*真*のブロックのパラメーター (削除) を除くすべてのアクションを設定すると、ファイルが検出されました。人ことはできませんを開く、移動、コピー、または検出されたファイルを共有します。</span><span class="sxs-lookup"><span data-stu-id="86d1e-p103">Setting the parameter to *true* blocks all actions (except Delete) for detected files. People cannot open, move, copy, or share detected files. </span></span><br/><span data-ttu-id="86d1e-p104">パラメーターを*false*に設定すると、削除し、ダウンロードを除くすべてのアクションがブロックされます。リスクを受け入れるし、検出されたファイルをダウンロードするユーザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="86d1e-p104">Setting the parameter to *false* blocks all actions except Delete and Download. People can choose to accept the risk and download a detected file. </span></span><br/><span data-ttu-id="86d1e-124">パラメーターを*true*に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="86d1e-124">We recommend setting the parameter to *true*.</span></span> 
   
7. <span data-ttu-id="86d1e-125">最大 30 分間のすべての Office 365 のデータ センターに展開するのには、変更を許可します。</span><span class="sxs-lookup"><span data-stu-id="86d1e-125">Allow up to 30 minutes for your changes to spread to all Office 365 datacenters.</span></span>
    
8. <span data-ttu-id="86d1e-126">(推奨)によって検出されたファイルの通知の設定に進みます。</span><span class="sxs-lookup"><span data-stu-id="86d1e-126">(Recommended) Proceed to set up alerts for detected files.</span></span>
    
<span data-ttu-id="86d1e-p105">Office 365 で、PowerShell を使用する方法の詳細については、 [PowerShell での Office 365 の管理](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)を参照してください。> として、悪意のあるファイルが検出されたときのユーザー エクスペリエンスの詳細についてを参照してください[SharePoint のオンライン、OneDrive、またはマイクロソフトのチームで悪意のあるファイルが見つかった場合の対処方法](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)です。</span><span class="sxs-lookup"><span data-stu-id="86d1e-p105">To learn more about using PowerShell with Office 365, see [Manage Office 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell). > To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span> 
  
## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="86d1e-129">によって検出されたファイルの通知を設定します。</span><span class="sxs-lookup"><span data-stu-id="86d1e-129">Set up alerts for detected files</span></span>

<span data-ttu-id="86d1e-130">ビジネス、またはマイクロソフトのチームの SharePoint のオンライン、OneDrive のファイルが悪意のあるものとして確認されたときに通知を受信するには、アラートを設定できます。</span><span class="sxs-lookup"><span data-stu-id="86d1e-130">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>
  
1. <span data-ttu-id="86d1e-131">Office 365 のセキュリティで&amp;コンプライアンス センターでは、**アラート**を選択して\>**通知の管理**。</span><span class="sxs-lookup"><span data-stu-id="86d1e-131">In the Office 365 Security &amp; Compliance Center, choose **Alerts** \> **Manage alerts**.</span></span>
    
2. <span data-ttu-id="86d1e-132">**新しいアラート ・ ポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="86d1e-132">Choose **New alert policy**.</span></span>
    
3. <span data-ttu-id="86d1e-p106">警告の名前を指定します。たとえば、ライブラリで悪意のあるファイルを入力します。</span><span class="sxs-lookup"><span data-stu-id="86d1e-p106">Specify a name for the alert. For example, you could type Malicious Files in Libraries.</span></span>
    
4. <span data-ttu-id="86d1e-p107">アラートの説明を入力します。たとえば、SharePoint のオンライン、OneDrive、またはマイクロソフトのチームで悪意のあるファイルが検出された場合は通知の管理者を入力します。</span><span class="sxs-lookup"><span data-stu-id="86d1e-p107">Type a description for the alert. For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
    
5. <span data-ttu-id="86d1e-137">**. のときは、このアラートを送信**] セクションでは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="86d1e-137">In the **Send this alert when...** section, do the following:</span></span> 
    
  - <span data-ttu-id="86d1e-138">**活動**] ボックスの一覧で、**ファイルにマルウェアを検出しました**を選択します。</span><span class="sxs-lookup"><span data-stu-id="86d1e-138">In the **Activities** list, choose **Detected malware in file**.</span></span>
    
  - <span data-ttu-id="86d1e-139">**ユーザー**のフィールドは空のままにします。</span><span class="sxs-lookup"><span data-stu-id="86d1e-139">Leave the **Users** field empty.</span></span> 
    
6. <span data-ttu-id="86d1e-140">**. このアラートを送信**] セクションで、グローバル管理者、セキュリティ管理者、または悪意のあるファイルが検出されたときに通知を受信する必要がありますセキュリティの読者の 1 つまたは複数を選択します。</span><span class="sxs-lookup"><span data-stu-id="86d1e-140">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span> 
    
7. <span data-ttu-id="86d1e-141">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="86d1e-141">Click **Save**.</span></span>
    
<span data-ttu-id="86d1e-142">警告に関する詳細についてを参照してください[では、Office 365 のセキュリティ アクティビティのアラートを作成&amp;コンプライアンス センター](create-activity-alerts.md)です。</span><span class="sxs-lookup"><span data-stu-id="86d1e-142">To learn more about alerts, see [Create activity alerts in the Office 365 Security &amp; Compliance Center](create-activity-alerts.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="86d1e-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="86d1e-143">Next steps</span></span>

- [<span data-ttu-id="86d1e-144">SharePoint、OneDrive、またはマイクロソフトのチームで検出された、悪意のあるファイルに関する情報を表示</span><span class="sxs-lookup"><span data-stu-id="86d1e-144">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
- [<span data-ttu-id="86d1e-145">Office 365 の管理者として検疫されたメッセージやファイルを管理します。</span><span class="sxs-lookup"><span data-stu-id="86d1e-145">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
    
## <a name="related-topics"></a><span data-ttu-id="86d1e-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="86d1e-146">Related topics</span></span>

[<span data-ttu-id="86d1e-147">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="86d1e-147">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="86d1e-148">Office 365 の高度な脅威保護のレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="86d1e-148">View the reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  
[<span data-ttu-id="86d1e-149">Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="86d1e-149">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

