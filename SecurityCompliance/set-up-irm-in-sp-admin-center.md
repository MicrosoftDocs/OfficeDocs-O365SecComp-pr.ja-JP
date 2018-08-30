---
title: SharePoint 管理センターでの情報権利管理 (IRM) を設定します。
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: SharePoint オンライン IRM を通じて Microsoft Azure Active Directory Rights Management サービス (RMS) を使用して SharePoint リストおよびドキュメント ライブラリを保護する方法について説明します。
ms.openlocfilehash: dea8c71ce67207b3c40a1f934f90e63740f70f29
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532151"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a><span data-ttu-id="34d66-103">SharePoint 管理センターでの情報権利管理 (IRM) を設定します。</span><span class="sxs-lookup"><span data-stu-id="34d66-103">Set up Information Rights Management (IRM) in SharePoint admin center</span></span>

<span data-ttu-id="34d66-p101">SharePoint Online では、内のリストやライブラリ レベルでファイルに IRM 保護が適用されます。組織が IRM 保護を使用する前に権限の管理を設定する必要があります。IRM では、Azure の情報保護を暗号化し、使用率の制限を割り当てるから Azure の権限の管理サービスに依存しています。Azure アクセス権の管理がすべてではなく、一部の Office 365 のプランが含まれます。詳細についてを参照して[どのように Office アプリケーションおよびサービスは、Azure の権利管理をサポート](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)します。</span><span class="sxs-lookup"><span data-stu-id="34d66-p101">Within SharePoint Online, IRM protection is applied to files at the list and library level. Before your organization can use IRM protection, you must first set up Rights Management. IRM relies on the Azure Rights Management service from Azure Information Protection to encrypt and assign usage restrictions. Some Office 365 plans include Azure Rights Management, but not all. To learn more, read [How Office applications and services support Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support).</span></span>
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a><span data-ttu-id="34d66-109">SharePoint 管理センターを使用して IRM サービスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="34d66-109">Turn on IRM service using SharePoint admin center</span></span>

<span data-ttu-id="34d66-p102">組織には、IRM で保護する SharePoint リストおよびライブラリことができます、前にまず、組織の権限の管理サービスを有効にする必要があります。については、どのように[Azure アクセス権の管理をアクティブにする](https://docs.microsoft.com/information-protection/deploy-use/activate-service)を参照してください。権限管理サービスを有効にするのには Office 365 のグローバル管理者権限のある職場、学校のアカウントを使用する必要があります。それ以外の場合、SharePoint Online で IRM 機能を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="34d66-p102">Before your organization can IRM-protect SharePoint lists and libraries, you must first activate the Rights Management service for your organization. To learn how see [Activating Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service). You must use a work or school account that has Office 365 global administrator privileges to enable the Rights Management service. Otherwise, you won't be able to use IRM features with SharePoint Online.</span></span>
  
<span data-ttu-id="34d66-114">権限管理サービスをアクティブにした後、IRM を有効にするのには SharePoint の管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="34d66-114">After activating the Rights Management service, sign in to the SharePoint admin center to turn on IRM.</span></span>
  
1. <span data-ttu-id="34d66-115">グローバル管理者または SharePoint 管理者として Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="34d66-115">Sign in to Office 365 as a global admin or SharePoint admin.</span></span>
    
2. <span data-ttu-id="34d66-p103">左上のアプリ起動ツール アイコン ![Office 365 のアプリ起動ツール アイコン](media/e5aee650-c566-4100-aaad-4cc2355d909f.png)を選択し、**[管理者]** を選択して、Office 365 管理センターを開きます。([管理] タイルが表示されない場合は、組織内で Office 365 管理者権限を持っていません。)</span><span class="sxs-lookup"><span data-stu-id="34d66-p103">Select the app launcher icon ![The app launcher icon in Office 365](media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in the upper-left and choose **Admin** to open the Office 365 admin center. (If you don't see the Admin tile, you don't have Office 365 administrator permissions in your organization.)</span></span> 
    
3. <span data-ttu-id="34d66-118">左側のウィンドウで [**管理者の中央に配置**」を選択します\> **SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="34d66-118">In the left pane, choose **Admin centers** \> **SharePoint**.</span></span>
    
4. <span data-ttu-id="34d66-119">左側のウィンドウで**設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="34d66-119">In the left pane, choose **settings**.</span></span>
    
5. <span data-ttu-id="34d66-p104">**情報権利管理 (IRM)** セクションで、**構成では、指定された IRM サービスを使用して**、選択し、 **IRM の設定を更新**します。IRM の設定を更新すると、組織内のユーザー、SharePoint リストおよびドキュメント ライブラリで IRM を使用して開始できます。ただし、オプションこれを行うにかかる場合があります 1 時間ライブラリの設定と設定の一覧に表示します。</span><span class="sxs-lookup"><span data-stu-id="34d66-p104">In the **Information Rights Management (IRM)** section, choose **Use the IRM service specified in your configuration**, and then choose **Refresh IRM Settings**. After you refresh IRM settings, people in your organization can begin using IRM in their SharePoint lists and document libraries. However, the options to do so may take up to an hour to appear in Library Settings and List Settings.</span></span>
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a><span data-ttu-id="34d66-123">IRM を有効にする SharePoint ドキュメント ライブラリとリスト</span><span class="sxs-lookup"><span data-stu-id="34d66-123">IRM-enable SharePoint document libraries and lists</span></span>
<span data-ttu-id="34d66-124"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="34d66-124"></span></span>

<span data-ttu-id="34d66-p105">IRM の設定を更新すると、サイトの所有者は、SharePoint リストに [IRM で保護することができ、ドキュメント ライブラリです。詳細については、[リストまたはライブラリの情報権利管理の適用](apply-irm-to-a-list-or-library.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34d66-p105">After refreshing IRM settings, site owners can IRM-protect their SharePoint lists and document libraries. For more information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="34d66-p106">サイトの所有者は、リストまたはライブラリの IRM を有効にすると、は、そのリストまたはライブラリでサポートされているファイルの種類を保護することができます。ライブラリに対して IRM を有効に、権限の管理は、そのライブラリ内のファイルのすべてに適用されます。リストに対して IRM を有効にすると、実際のリスト アイテムではなくリスト アイテムに関連付けられているファイルにのみアクセス権管理が適用されます。</span><span class="sxs-lookup"><span data-stu-id="34d66-p106">When site owners enable IRM for a list or library, they can protect any supported file types in that list or library. When IRM is enabled for a library, rights management applies to all of the files in that library. When you enable IRM for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="34d66-p107">ユーザーは、IRM が有効なリストやライブラリ内のファイルをダウンロードするとき、ファイルが暗号化されるため、承認されたユーザーのみが表示ことができます。各権限が管理されたファイルには、ファイルを表示できるユーザーの制限を課する発行ライセンスも含まれています。典型的な制限、ファイルを読み取り専用にする、ローカル コピーを保存し、ファイルの印刷を禁止するから人を防止する、テキストのコピーを無効にします。IRM 対応のファイル タイプを読み取ることができるクライアント プログラムは、権限が管理されたファイル内でこれらの制限を適用するのに発行ライセンスを使用します。ダウンロードされた後にもに権限が管理されたファイルが、保護を保持する方法です。をリストまたはライブラリに IRM を有効にするのには、[リストまたはライブラリの情報権利管理の適用](apply-irm-to-a-list-or-library.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34d66-p107">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them. Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file. Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file. Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions. This is how a rights-managed file retains its protection even after it is downloaded. To enable IRM on a list or library, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="34d66-p108">作成または Office オンラインを使用して、IRM が有効なライブラリのドキュメントを編集することはできません。代わりに、一度に 1 人のユーザーは、ダウンロードして、IRM で暗号化されたファイルを編集します。複数のユーザー間でチェックインし、*共同編集*を管理するためにチェック アウトまたはオーサリングを使用します。</span><span class="sxs-lookup"><span data-stu-id="34d66-p108">You cannot create or edit documents in an IRM-enabled library using Office Online. Instead, one person at a time can download and edit IRM-encrypted files. Use check-in and check-out to manage  *co-authoring*  , or authoring across multiple users.</span></span> 
  
<span data-ttu-id="34d66-p109">IRM で保護されたライブラリから PDF ファイルをダウンロードすると、Office 365 は、保護された PDF ファイルを作成します。ファイルの拡張子は変更されませんが、ファイルが保護されています。このファイルを表示する必要があります Azure の情報保護のビューアー、Azure の情報保護、完全なクライアント、または保護された PDF ファイルの表示をサポートしている別のアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="34d66-p109">When you download a PDF file from an IRM-protected library, Office 365 creates a protected PDF file. The file's extension won't change, but the file is protected. To view this file you'll need the Azure Information Protection viewer, the full Azure Information Protection client, or another application that supports viewing protected PDF files.</span></span> 
  
<span data-ttu-id="34d66-142">SharePoint Online には、次のファイルの種類の暗号化がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="34d66-142">SharePoint Online supports encryption of the following file types:</span></span>
  
- <span data-ttu-id="34d66-143">PDF</span><span class="sxs-lookup"><span data-stu-id="34d66-143">PDF</span></span>
    
- <span data-ttu-id="34d66-144">次の Microsoft Office プログラムの 97-2003 ファイル形式: Word、Excel、および PowerPoint</span><span class="sxs-lookup"><span data-stu-id="34d66-144">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="34d66-145">次の Microsoft Office プログラムの Office オープン XML の書式を設定します Word、Excel、および PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="34d66-145">The Office Open XML formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="34d66-146">XML 用紙仕様 (XPS) 形式</span><span class="sxs-lookup"><span data-stu-id="34d66-146">The XML Paper Specification (XPS) format</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="34d66-147">次の手順</span><span class="sxs-lookup"><span data-stu-id="34d66-147">Next steps</span></span>
<span data-ttu-id="34d66-148"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="34d66-148"></span></span>

<span data-ttu-id="34d66-p110">SharePoint Online の IRM を有効にして、リストやライブラリにアクセス権管理を適用することを開始できます。については、[リストまたはライブラリの情報権利管理の適用](apply-irm-to-a-list-or-library.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34d66-p110">Once you've enabled IRM for SharePoint Online, you can start applying rights management to lists and libraries. For information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="34d66-p111">Windows 用の新しい OneDrive 同期クライアントでは、IRM で保護された SharePoint ドキュメント ライブラリおよび OneDrive の場所である限り、ライブラリの IRM 設定は、ドキュメントのアクセス権を期限切れに設定されていない) の同期をサポートしています。詳細については、または、新しい同期クライアントの展開を開始するには、 [Windows 用の新しい OneDrive 同期クライアントの展開](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34d66-p111">The new OneDrive sync client for Windows now supports synchronizing IRM-protected SharePoint document libraries and OneDrive locations (as long as the IRM setting for the library isn't set to expire document access rights). For more information, or to get started deploying the new sync client, see [Deploy the new OneDrive sync client for Windows](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668).</span></span>
  
[<span data-ttu-id="34d66-153">ページの一番上</span><span class="sxs-lookup"><span data-stu-id="34d66-153">Top of Page</span></span>](set-up-irm-in-sp-admin-center.md#__top)
  

