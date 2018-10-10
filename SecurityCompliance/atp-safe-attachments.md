---
title: Office 365 の ATP の安全な添付ファイル
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
description: 安全な添付ファイル機能は、電子メールの添付ファイルのクリックの検証を提供します。ファイルを悪意のあるユーザーから組織を保護するために使用の安全な添付ファイルで送信または受信電子メールです。
ms.openlocfilehash: 44a7aa56db6b19ac948184988c930841fc7ffb89
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454314"
---
# <a name="office-365-atp-safe-attachments"></a><span data-ttu-id="08bc3-104">Office 365 の ATP の安全な添付ファイル</span><span class="sxs-lookup"><span data-stu-id="08bc3-104">Office 365 ATP Safe Attachments</span></span>

## <a name="overview-of-office-365-atp-safe-attachments"></a><span data-ttu-id="08bc3-105">Office 365 の ATP の安全な添付ファイルの概要</span><span class="sxs-lookup"><span data-stu-id="08bc3-105">Overview of Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="08bc3-p102">分析ツール ( [ATP の安全なリンク](atp-safe-links.md)) との安全な添付ファイルは、 [Office 365 の高度な脅威保護](office-365-atp.md)(ATP) の一部です。ATP の安全な添付ファイル機能では、電子メールの添付ファイルは、悪意のあるかどうかを確認し、組織を保護するために操作を行います。ATP の安全な添付ファイル機能は、Office 365 のグローバルまたはセキュリティ管理者によって設定されている[安全な添付ファイルの分析ツールのポリシー](set-up-atp-safe-attachments-policies.md)に従って、組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p102">ATP Safe Attachments (along with [ATP Safe Links](atp-safe-links.md)) is part of [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP). The ATP Safe Attachments feature checks to see if email attachments are malicious, and then takes action to protect your organization. The ATP Safe Attachments feature protects your organization according to [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) that are set by your Office 365 global or security administrators.</span></span> 
  
<span data-ttu-id="08bc3-p103">最近では、ATP の保護が、SharePoint Online の OneDrive 内のファイルにビジネス、およびマイクロソフトのチームに拡張されました。詳細については、 [Office 365 高度な脅威保護](atp-for-spo-odb-and-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p103">Recently, ATP protection has been extended to files in SharePoint Online, OneDrive for Business, and Microsoft Teams. To learn more, see [Office 365 Advanced Threat Protection for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>
       
### <a name="how-it-works"></a><span data-ttu-id="08bc3-111">しくみ</span><span class="sxs-lookup"><span data-stu-id="08bc3-111">How it works</span></span>

<span data-ttu-id="08bc3-p104">ATP の安全な添付ファイル機能は、組織内のユーザーの電子メールの添付ファイルをチェックします。ATP の安全な添付ファイル ポリシーが適用されて、他の対象となるポリシーが Office 365 に自分の電子メールを表示する、その電子メールの添付ファイルがチェックされ、ATP の安全な添付ファイル ポリシーに基づいて、適切な動作が実行します。ポリシーの定義方法によって、人は悪意のあるファイルを送信した順序を今まで知らなくても作業を続行できます。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p104">The ATP Safe Attachments feature checks email attachments for people in your organization. When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies. Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="08bc3-115">作業で、ATP の安全な添付ファイルの 2 つの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="08bc3-115">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="08bc3-p105">**の例 1: 電子メールの添付ファイル**Lee がファイルの添付された電子メール メッセージを受信すると仮定します。Lee にわかりやすいかどうか添付ファイルが安全ではまたは、実際には Lee のユーザーの資格情報を盗み出す目的のマルウェアが含まれています。Lee の組織では、セキュリティ管理者は、数日前、ATP の安全な添付ファイル ポリシーを定義します。ATP の安全な添付ファイル機能を使用して電子メールの添付ファイルが開かれ、Lee では、それを受け取る前に、仮想環境でテストします。悪意のある添付ファイルが確認された場合に自動的に削除されます。添付ファイルが安全な場合に Lee をクリックしたときに期待どおりに開きます。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p105">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment. It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal the Lee's user credentials. In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago. With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it. If the attachment is determined to be malicious, it will be removed automatically. If the attachment is safe, it will open as expected when Lee clicks on it.</span></span> 
    
- <span data-ttu-id="08bc3-p106">**例 2: SharePoint のオンラインでのファイル**Jean がファイルを受信して、SharePoint Online 内のライブラリにアップロードすることがあるとします。Jean は、ファイルが実際には悪意のあるであることも、チームの残りの部分とファイルへのリンクを共有します。幸いなことに、 [SharePoint、OneDrive、およびマイクロソフトのチームの分析ツール](atp-for-spo-odb-and-teams.md)は、悪意のあるファイルを検出し、それをブロックします。数日後で、山口さんは、ドキュメントを開くに移動します。山口さんは、ファイルがあるを確認できます、松田さんは開けないか、悪意のあるファイルからのコンピューターと他のユーザーを防止するように、共有できません。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p106">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online. Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious. Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it. A few days later, Chris goes to open the document. Although Chris can see the file is there, Chris cannot open or share it, which prevents Chris's computer and others from the malicious file.</span></span> 
    
<span data-ttu-id="08bc3-p107">ATP の安全な添付ファイルのポリシーは、特定の人または組織内のグループまたはドメイン全体に適用できます。詳細については、 **[Office 365 の ATP の安全な添付ファイル ポリシーの設定](set-up-atp-safe-attachments-policies.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p107">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain. To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span> 
  
## <a name="how-to-get-atp-safe-attachments"></a><span data-ttu-id="08bc3-129">ATP の安全な添付ファイルを取得する方法</span><span class="sxs-lookup"><span data-stu-id="08bc3-129">How to get ATP Safe Attachments</span></span>

<span data-ttu-id="08bc3-p108">ATP の安全な添付ファイル機能は、高度な脅威保護の Microsoft 365 エンタープライズ、Office 365 のエンタープライズ E5、および Microsoft 365 業務に含まれている部分です。組織は、別の Office 365 エンタープライズ サブスクリプションで使用されている場合は、アドオンとして脅威の高度な保護を購入できます。(グローバル管理者は、Office 365 管理センターを選択して**請求** \> **サブスクリプションを追加**します)。詳細についてを参照してください[Office 365 のプラットフォーム サービスの説明: Office 365 のセキュリティ&amp;コンプライアンス センター](https://technet.microsoft.com/en-us/library/dn933793.aspx) [購入またはビジネスのための Office 365 のアドオンを編集](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)するとします。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p108">The ATP Safe Attachments feature is part of Advanced Threat Protection, which is included in Microsoft 365 Enterprise, Office 365 Enterprise E5, and Microsoft 365 Business. If your organization is using another Office 365 Enterprise subscription, Advanced Threat Protection can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span>
  
<span data-ttu-id="08bc3-133">場合、安全な添付ファイルの分析ツールの機能に適用されます。</span><span class="sxs-lookup"><span data-stu-id="08bc3-133">The ATP Safe Attachments feature applies when:</span></span>
  
- <span data-ttu-id="08bc3-p109">ATP の安全な添付ファイル ポリシーが設定されています。( [Office 365 の ATP の安全な添付ファイル ポリシーの設定](set-up-atp-safe-attachments-policies.md)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p109">ATP Safe Attachments policies are set up. (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md).)</span></span>
    
- <span data-ttu-id="08bc3-p110">職場、学校のアカウントを使用して Office 365 にユーザーに署名します。(詳しくは、 [Office または Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p110">Users have signed into Office 365 using their work or school account. (See [Sign in to Office or Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)</span></span>
    
### <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a><span data-ttu-id="08bc3-138">ATP の安全な添付ファイルの保護を確認する方法</span><span class="sxs-lookup"><span data-stu-id="08bc3-138">How to know if ATP Safe Attachments protection is in place</span></span>

 <span data-ttu-id="08bc3-139">ATP の安全な添付ファイルの保護を配置するためには、 [ATP の安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)を定義しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="08bc3-139">[ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) must be defined in order for ATP Safe Attachments protection to be in place.</span></span> 
  
<span data-ttu-id="08bc3-140">[脅威の高度な保護のためのレポートを表示する](view-reports-for-atp.md)ことでは、サービスの操作方法を表示する方法の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="08bc3-140">One good way to see how the service is working is by [viewing reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span>
  
<span data-ttu-id="08bc3-p111">さらに、次の表では、いくつかのサンプル シナリオについて説明します。すべてのこれらの場合に、組織には、脅威の高度な保護が含まれています Office 365 エンタープライズ E5 と仮定します。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p111">In addition, the following table describes some example scenarios. In all of these cases, we assume the organization has Office 365 Enterprise E5, which includes Advanced Threat Protection.</span></span>
  
|<span data-ttu-id="08bc3-143">**シナリオ例**</span><span class="sxs-lookup"><span data-stu-id="08bc3-143">**Example scenario**</span></span>|<span data-ttu-id="08bc3-144">**ATP の安全な添付ファイルの保護はここで適用しますか。**</span><span class="sxs-lookup"><span data-stu-id="08bc3-144">**Does ATP Safe Attachments protection apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="08bc3-145">Pat の組織の Office 365 のエンタープライズ E5 ですが、ATP の安全な添付ファイルのすべてのポリシーをまだ定義誰が。</span><span class="sxs-lookup"><span data-stu-id="08bc3-145">Pat's organization has Office 365 Enterprise E5, but no one has defined any policies for ATP Safe Attachments yet.</span></span>  <br/> |<span data-ttu-id="08bc3-p112">違います。機能が利用可能ですが、ATP の安全な添付ファイルの保護を配置するために少なくとも 1 つの ATP の安全な添付ファイル ポリシーを定義しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p112">No. Although the feature is available, at least one ATP Safe Attachments policy must be defined in order for ATP Safe Attachments protection to be in place.</span></span>  <br/> |
|<span data-ttu-id="08bc3-p113">Contoso の営業部門の従業員です。Lee の組織では、財務部門の従業員のみに適用されるように、ATP の安全な添付ファイル ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p113">Lee is an employee in the sales department at Contoso. Lee's organization has an ATP Safe Attachments policy in place that applies to finance employees only.</span></span>  <br/> |<span data-ttu-id="08bc3-p114">違います。この例では、財務部門の従業員には、ATP の安全な添付ファイルの保護、販売部門を含め、他の従業員は、それらのグループを含むポリシーを定義しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p114">No. In this case, finance employees would have ATP Safe Attachments protection, but other employees, including the sales department, would not until policies that include those groups are defined.</span></span>  <br/> |
|<span data-ttu-id="08bc3-p115">昨日、ジャンの組織で Office 365 管理者は、すべての従業員に適用される分析ツールの安全な添付ファイル ポリシーを設定します。今日以前のバージョンでは、Jean は、添付ファイルを含む電子メール メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p115">Yesterday, an Office 365 administrator at Jean's organization set up an ATP Safe Attachments policy that applies to all employees. Earlier today, Jean received an email message that includes an attachment.</span></span>  <br/> |<span data-ttu-id="08bc3-p116">うん。この例では、ジャンが高度な脅威を保護するためのライセンスを持つし、ジャンが含まれている ATP の安全な添付ファイル ポリシーが定義されています。新しいポリシーを有効にするデータ センターの間を約 30 分がかかります1 日はここで渡される、ため、ポリシーが有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p116">Yes. In this example, Jean has a license for Advanced Threat Protection, and an ATP Safe Attachments policy that includes Jean has been defined. It typically takes about 30 minutes for a new policy to take effect across datacenters; since a day has passed in this case, the policy should be in effect.</span></span>  <br/> |
|<span data-ttu-id="08bc3-p117">組織では、組織内のすべてのユーザーのために ATP の安全な添付ファイル ポリシーを使用して Office 365 エンタープライズ E5 があります。山口さんは、添付ファイル、および他の組織の外部ユーザーにメッセージを転送する電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p117">Chris's organization has Office 365 Enterprise E5 with ATP Safe Attachments policies in place for everyone in the organization. Chris receives an email that has an attachment, and forwards the message to others who are outside the organization.</span></span>  <br/> |<span data-ttu-id="08bc3-p118">ATP の安全な添付ファイルの保護は、山口さんが受信したメッセージのためには。場合は、受信者の組織 ATP の安全な添付ファイル ポリシーの場所で、し、山口さんに転送するメッセージを対象になるこれらのポリシー転送メッセージが到着するとします。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p118">ATP Safe Attachments protection is in place for messages that Chris receives. If the recipients' organizations also have ATP Safe Attachments policies in place, then the message that Chris forwards would be subject to those policies when the forwarded message arrives.</span></span>  <br/> |
|<span data-ttu-id="08bc3-p119">森さんの組織 ATP の安全な添付ファイル ポリシーの場所であり、 [SharePoint、OneDrive、およびマイクロソフトのチームの分析ツール](atp-for-spo-odb-and-teams.md)は有効にします。青木さんには、SharePoint Online のすべてのファイルをスキャンし、開くか、ダウンロードしても安全ですが想定しています。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p119">Jamie's organization has ATP Safe Attachments policies in place, and [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) has been turned on. Jamie assumes that every file in SharePoint Online has been scanned and is safe to open or download.  </span></span><br/> |<span data-ttu-id="08bc3-p120">は定義されているポリシーに従って配置では、ATP の安全な添付ファイルの保護ただし、これとは限りません、ビジネス、またはマイクロソフトのチームの OneDrive の SharePoint Online では、すべてのファイルをスキャンすることです。(詳細については、 [SharePoint、OneDrive、およびマイクロソフトのチームの分析ツール](atp-for-spo-odb-and-teams.md)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="08bc3-p120">ATP Safe Attachments protection is in place according to the policies that are defined; however, this does not mean that every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams is scanned. (To learn more, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).)  </span></span><br/> |
   
## <a name="submitting-files-for-malware-analysis"></a><span data-ttu-id="08bc3-165">マルウェアの分析のためのファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="08bc3-165">Submitting files for malware analysis</span></span>

- <span data-ttu-id="08bc3-166">分析するためのマイクロソフトを要求するファイルを受信する場合は、[マルウェアの解析用のファイルの送信](https://aka.ms/wdsi/submit)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08bc3-166">If you receive a file that you want to ask Microsoft to analyze, visit [Submit a file for malware analysis](https://aka.ms/wdsi/submit).</span></span>

- <span data-ttu-id="08bc3-167">分析のためにマイクロソフトに送信する電子メール メッセージ (添付ファイルの有無にかかわらず) を受信する場合、[レポート メッセージのアドインを](enable-the-report-message-add-in.md)使用します。</span><span class="sxs-lookup"><span data-stu-id="08bc3-167">If you receive an email message (with or without an attachment) that you want to submit to Microsoft for analysis, use the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="08bc3-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="08bc3-168">Related topics</span></span>

[<span data-ttu-id="08bc3-169">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="08bc3-169">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="08bc3-170">Office 365 の ATP の安全な添付ファイル ポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="08bc3-170">Set up ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
  
[<span data-ttu-id="08bc3-171">SharePoint、OneDrive、およびマイクロソフトのチームの分析ツール</span><span class="sxs-lookup"><span data-stu-id="08bc3-171">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)
  
[<span data-ttu-id="08bc3-172">Office 365 で ATP の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="08bc3-172">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="08bc3-173">Office 365 の ATP のフィッシング詐欺対策機能</span><span class="sxs-lookup"><span data-stu-id="08bc3-173">ATP anti-phishing capabilities in Office 365</span></span>](atp-anti-phishing.md)
  
[<span data-ttu-id="08bc3-174">脅威の高度な保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="08bc3-174">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

