---
title: SharePoint、OneDrive、Microsoft Teams で検出された悪意のあるファイルに関する情報を表示する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: SharePoint、OneDrive、Teams で検出された悪意のあるファイルに関する情報を表示する方法と、それらのファイルに対してアクションを実行する方法について説明します。
ms.openlocfilehash: f5304f78ddec884748dd7d1090e2a7895044d045
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259835"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="c8fd2-103">SharePoint、OneDrive、Microsoft Teams で検出された悪意のあるファイルに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="c8fd2-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="c8fd2-104">[Office 365 ATP for SharePoint、OneDrive、Microsoft Teams](atp-for-spo-odb-and-teams.md)では、組織がドキュメントライブラリおよびチームサイト内の悪意のあるファイルから保護されます。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="c8fd2-105">悪意のあるファイルが検出されると、そのファイルはブロックされるようになり、組織のセキュリティチームによって追加の操作が行われるまで、そのファイルを開いたり、コピー、移動、または共有することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="c8fd2-106">この記事では、検出されたファイルと実行するアクションに関する情報を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="c8fd2-107">この記事で説明されているタスクを実行するには、 [Office 365 セキュリティ&amp;コンプライアンスセンターに必要なアクセス許可](permissions-in-the-security-and-compliance-center.md)を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="c8fd2-108">検出されたファイルに関する情報をレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="c8fd2-108">View reports with information about detected files</span></span>

<span data-ttu-id="c8fd2-109">Office 365 ATP によって検出されたファイルの状態と詳細情報を表示するには、脅威保護の状態レポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="c8fd2-110">[Office 365 セキュリティ&amp; /コンプライアンスセンター](https://protection.office.com)で、[**ダッシュボード** \>の**脅威保護の状態**を**報告** \>する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-110">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="c8fd2-111">レポートの右上隅で、[**詳細テーブルの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="c8fd2-112">レポートで検出されたファイルの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="c8fd2-113">リスト内の項目を選択して、実行されたアクション、ファイル名、ファイルパスなどを含む詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="c8fd2-114">[**詳細分析**] タブを選択して、観測された動作や分析の詳細などの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="c8fd2-115">検疫内のファイルを表示し、処理を実行する</span><span class="sxs-lookup"><span data-stu-id="c8fd2-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="c8fd2-116">&amp; Office 365 セキュリティコンプライアンスセンターで、[**脅威管理** \> **レビュー** \>の**検疫**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-116">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span>
    
2. <span data-ttu-id="c8fd2-117">左上隅で、フィルターを [**電子メール**] から [**コンテンツ**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-117">In the upper left corner, change the filter from **Email** to **Content**.</span></span>
    
3. <span data-ttu-id="c8fd2-118">リストで項目を選択すると、ファイルの URL などの詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-118">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="c8fd2-119">使用可能なアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-119">Choose an available action.</span></span>
    
  - <span data-ttu-id="c8fd2-120">ファイルのブロックを解除するには、[\*\*レポートの解放&amp; \*\* ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-120">Choose **Release &amp; report** to unblock the file.</span></span> 
    
    <span data-ttu-id="c8fd2-121">microsoft への誤検知としてファイルを報告するには、[ **microsoft にレポートを送信**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-121">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 
    
  - <span data-ttu-id="c8fd2-122">[**ファイルのダウンロード**] を選択して、ファイルをさらに調査します。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-122">Choose **Download file** to investigate the file further.</span></span> 
    
  - <span data-ttu-id="c8fd2-123">[**削除**] を選択して、検疫されたアイテムのリストからファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-123">Choose **Delete** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="c8fd2-124">このオプションを選択する場合は、SharePoint Online、OneDrive for business、または Microsoft Teams の対応するライブラリからもファイルを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-124">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="c8fd2-125">このオプションでは、ファイルが開かれたり共有されたりすることはブロックされません。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-125">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="c8fd2-126">[**閉じる**] を選択して、選択したアイテムの詳細を閉じます。</span><span class="sxs-lookup"><span data-stu-id="c8fd2-126">Choose **Close** to close the details for a selected item.</span></span> 
  
  

