---
title: Set up Information Rights Management (IRM) in SharePoint admin center
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Microsoft Azure Active Directory Rights Management Services (RMS) を使用して sharepoint Online IRM を使用して sharepoint リストとドキュメントライブラリを保護する方法について説明します。
ms.openlocfilehash: a5ac2cf5f33f3957e4cf17660461ad2d719d7c83
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217707"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a><span data-ttu-id="70dba-103">Set up Information Rights Management (IRM) in SharePoint admin center</span><span class="sxs-lookup"><span data-stu-id="70dba-103">Set up Information Rights Management (IRM) in SharePoint admin center</span></span>

<span data-ttu-id="70dba-p101">SharePoint Online では、IRM 保護はリストおよびライブラリレベルでファイルに適用されます。組織で IRM 保護を使用するには、最初に Rights Management を設定する必要があります。IRM は azure Information Protection からの azure Rights Management サービスに依存して、使用制限を暗号化して割り当てます。一部の Office 365 プランには、Azure Rights Management は含まれていますが、すべてではありません。詳細については、「 [Office アプリケーションとサービスが Azure Rights Management をサポートする方法](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70dba-p101">Within SharePoint Online, IRM protection is applied to files at the list and library level. Before your organization can use IRM protection, you must first set up Rights Management. IRM relies on the Azure Rights Management service from Azure Information Protection to encrypt and assign usage restrictions. Some Office 365 plans include Azure Rights Management, but not all. To learn more, read [How Office applications and services support Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support).</span></span>
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a><span data-ttu-id="70dba-109">SharePoint 管理センターを使用して IRM サービスを有効にする</span><span class="sxs-lookup"><span data-stu-id="70dba-109">Turn on IRM service using SharePoint admin center</span></span>

<span data-ttu-id="70dba-p102">組織で SharePoint リストとライブラリを IRM で保護するには、まず、組織の Rights Management サービスをアクティブ化する必要があります。[Azure Rights Management をアクティブ化](https://docs.microsoft.com/information-protection/deploy-use/activate-service)する方法については、「」を参照してください。Office 365 グローバル管理者特権を持つ職場または学校のアカウントを使用して、Rights Management サービスを有効にする必要があります。そうしないと、SharePoint Online で IRM 機能を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="70dba-p102">Before your organization can IRM-protect SharePoint lists and libraries, you must first activate the Rights Management service for your organization. To learn how see [Activating Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service). You must use a work or school account that has Office 365 global administrator privileges to enable the Rights Management service. Otherwise, you won't be able to use IRM features with SharePoint Online.</span></span>
  
<span data-ttu-id="70dba-114">Rights Management サービスをアクティブ化した後、SharePoint 管理センターにサインインして IRM を有効にします。</span><span class="sxs-lookup"><span data-stu-id="70dba-114">After activating the Rights Management service, sign in to the SharePoint admin center to turn on IRM.</span></span>
  
1. <span data-ttu-id="70dba-115">グローバル管理者または SharePoint 管理者として Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="70dba-115">Sign in to Office 365 as a global admin or SharePoint admin.</span></span>
    
2. <span data-ttu-id="70dba-p103">左上のアプリ起動ツール アイコン ![Office 365 のアプリ起動ツール アイコン](media/e5aee650-c566-4100-aaad-4cc2355d909f.png)を選択し、**[管理者]** を選択して、Office 365 管理センターを開きます。([管理] タイルが表示されない場合は、組織内で Office 365 管理者権限を持っていません。)</span><span class="sxs-lookup"><span data-stu-id="70dba-p103">Select the app launcher icon ![The app launcher icon in Office 365](media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in the upper-left and choose **Admin** to open the Office 365 admin center. (If you don't see the Admin tile, you don't have Office 365 administrator permissions in your organization.)</span></span> 
    
3. <span data-ttu-id="70dba-118">左側のウィンドウで、**[管理センター]** \> **[SharePoint]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="70dba-118">In the left pane, choose **Admin centers** \> **SharePoint**.</span></span>
    
4. <span data-ttu-id="70dba-119">左側のウィンドウで、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="70dba-119">In the left pane, choose **settings**.</span></span>
    
5. <span data-ttu-id="70dba-p104">[ **Information Rights Management (irm)** ] セクションで、[**構成で指定された irm サービスを使用する**] を選択し、[ **irm 設定の更新**] を選択します。irm 設定を更新した後、組織内のユーザーは、SharePoint リストとドキュメントライブラリで irm を使用することができます。ただし、[ライブラリの設定] および [リストの設定] に表示されるまでに最大1時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="70dba-p104">In the **Information Rights Management (IRM)** section, choose **Use the IRM service specified in your configuration**, and then choose **Refresh IRM Settings**. After you refresh IRM settings, people in your organization can begin using IRM in their SharePoint lists and document libraries. However, the options to do so may take up to an hour to appear in Library Settings and List Settings.</span></span>
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a><span data-ttu-id="70dba-123">IRM-SharePoint ドキュメントライブラリとリストを有効にする</span><span class="sxs-lookup"><span data-stu-id="70dba-123">IRM-enable SharePoint document libraries and lists</span></span>
<span data-ttu-id="70dba-124"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="70dba-124"></span></span>

<span data-ttu-id="70dba-p105">irm 設定を更新すると、サイト所有者は SharePoint リストとドキュメントライブラリを irm で保護できます。詳細については、「[リストまたはライブラリに information Rights Management を適用する](apply-irm-to-a-list-or-library.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70dba-p105">After refreshing IRM settings, site owners can IRM-protect their SharePoint lists and document libraries. For more information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="70dba-p106">サイト所有者は、リストまたはライブラリで IRM を有効にすると、そのリストまたはライブラリでサポートされているファイルの種類を保護できます。ライブラリで IRM が有効になっている場合、rights management はそのライブラリ内のすべてのファイルに適用されます。リストに対して IRM を有効にする場合、rights management は、実際のリストアイテムではなく、リストアイテムに添付されているファイルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="70dba-p106">When site owners enable IRM for a list or library, they can protect any supported file types in that list or library. When IRM is enabled for a library, rights management applies to all of the files in that library. When you enable IRM for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="70dba-p107">ユーザーが IRM 対応リストまたはライブラリにファイルをダウンロードすると、承認されたユーザーのみがファイルを表示できるように、ファイルが暗号化されます。また、各権限管理ファイルには、ファイルを表示するユーザーに制限を課す発行ライセンスが含まれています。一般的な制限としては、ファイルを読み取り専用にし、テキストのコピーを無効にして、ユーザーがローカルコピーを保存しないようにしたり、ファイルを印刷できないようにしたりすることがあります。IRM がサポートするファイルの種類を読み取ることができるクライアントプログラムは、権限が管理されたファイル内の発行ライセンスを使用して、これらの制限を適用します。これは、権限が管理されたファイルがダウンロードされた後も保護を保持する方法です。リストまたはライブラリで IRM を有効にするには、「[リストまたはライブラリへの Information Rights Management の適用](apply-irm-to-a-list-or-library.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70dba-p107">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them. Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file. Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file. Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions. This is how a rights-managed file retains its protection even after it is downloaded. To enable IRM on a list or library, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="70dba-p108">Office Online を使用して IRM 対応ライブラリでドキュメントを作成または編集することはできません。代わりに、一度に1人のユーザーが IRM で暗号化されたファイルをダウンロードして編集することができます。チェックインとチェックアウトを使用して、複数のユーザーにまたがる*共同編集*または作成を管理します。</span><span class="sxs-lookup"><span data-stu-id="70dba-p108">You cannot create or edit documents in an IRM-enabled library using Office Online. Instead, one person at a time can download and edit IRM-encrypted files. Use check-in and check-out to manage  *co-authoring*  , or authoring across multiple users.</span></span> 
  
<span data-ttu-id="70dba-p109">IRM で保護されたライブラリから pdf ファイルをダウンロードすると、Office 365 は保護された pdf ファイルを作成します。ファイルの拡張子は変わりませんが、ファイルは保護されます。このファイルを表示するには、azure information protection viewer、完全な azure information protection クライアント、または保護された PDF ファイルの表示をサポートする別のアプリケーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="70dba-p109">When you download a PDF file from an IRM-protected library, Office 365 creates a protected PDF file. The file's extension won't change, but the file is protected. To view this file you'll need the Azure Information Protection viewer, the full Azure Information Protection client, or another application that supports viewing protected PDF files.</span></span> 
  
<span data-ttu-id="70dba-142">SharePoint Online では、次の種類のファイルの暗号化がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="70dba-142">SharePoint Online supports encryption of the following file types:</span></span>
  
- <span data-ttu-id="70dba-143">PDF</span><span class="sxs-lookup"><span data-stu-id="70dba-143">PDF</span></span>
    
- <span data-ttu-id="70dba-144">次の Microsoft Office プログラムの97-2003 ファイル形式: Word、Excel、および PowerPoint</span><span class="sxs-lookup"><span data-stu-id="70dba-144">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="70dba-145">office Open XML 形式の次の Microsoft Office プログラム: Word、Excel、および PowerPoint</span><span class="sxs-lookup"><span data-stu-id="70dba-145">The Office Open XML formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="70dba-146">XML Paper Specification (XPS) 形式</span><span class="sxs-lookup"><span data-stu-id="70dba-146">The XML Paper Specification (XPS) format</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="70dba-147">次の手順</span><span class="sxs-lookup"><span data-stu-id="70dba-147">Next steps</span></span>
<span data-ttu-id="70dba-148"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="70dba-148"></span></span>

<span data-ttu-id="70dba-p110">SharePoint Online の IRM を有効にしたら、[リストとライブラリへの rights management の適用] を開始できます。詳細については、「[リストまたはライブラリに information Rights Management を適用する](apply-irm-to-a-list-or-library.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70dba-p110">Once you've enabled IRM for SharePoint Online, you can start applying rights management to lists and libraries. For information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="70dba-p111">SharePoint 用の新しい onedrive 同期クライアントでは、irm で保護された SharePoint ドキュメントライブラリと onedrive の場所の同期がサポートされるようになりました (ライブラリの irm 設定でドキュメントアクセス権の有効期限が設定されていない場合)。詳細については、または新しい同期クライアントの展開を開始するには、「 [Windows 用の新しい OneDrive 同期クライアントを展開](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70dba-p111">The new OneDrive sync client for Windows now supports synchronizing IRM-protected SharePoint document libraries and OneDrive locations (as long as the IRM setting for the library isn't set to expire document access rights). For more information, or to get started deploying the new sync client, see [Deploy the new OneDrive sync client for Windows](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668).</span></span>
  
[<span data-ttu-id="70dba-153">ページの先頭へ</span><span class="sxs-lookup"><span data-stu-id="70dba-153">Top of Page</span></span>](set-up-irm-in-sp-admin-center.md#__top)
  

