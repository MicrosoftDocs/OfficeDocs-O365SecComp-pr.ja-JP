---
title: SharePoint、OneDrive、またはマイクロソフトのチームで検出された、悪意のあるファイルに関する情報を表示
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
description: SharePoint、OneDrive、またはチームで検出された、悪意のあるファイルに関する情報を表示する場所とそれらのファイルに対してアクションを実行する方法について説明します。
ms.openlocfilehash: 37cd721c9ec2608ddcd74f9ae1ed6991b5f0cea7
ms.sourcegitcommit: e0c6f99d5514d8da8a70d9bd3616d1a1c0851254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2018
ms.locfileid: "25552385"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="ecb77-103">SharePoint、OneDrive、またはマイクロソフトのチームで検出された、悪意のあるファイルに関する情報を表示</span><span class="sxs-lookup"><span data-stu-id="ecb77-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="ecb77-p101">[SharePoint、OneDrive、およびマイクロソフトのチームの office 365 の分析ツール](atp-for-spo-odb-and-teams.md)は、ドキュメント ライブラリ、およびチーム サイト内の悪意のあるファイルから組織を保護します。悪意のあるファイルが検出されると、そのファイルを開く、コピー、移動、またはそれ以降の操作は、組織のセキュリティ チームによって実行されるまで、共有できる誰にするためにブロックされます。によって検出されたファイルに関する情報を表示する方法とどのような措置を説明するには、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecb77-p101">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites. When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team. Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="ecb77-107">この資料で説明するタスクを実行するために、必要なを設定する必要があります[Office 365 のセキュリティに割り当てられたアクセス権&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="ecb77-107">In order to perform the tasks described in this article, you must have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="ecb77-108">によって検出されたファイルに関する情報をレポートの表示</span><span class="sxs-lookup"><span data-stu-id="ecb77-108">View reports with information about detected files</span></span>

<span data-ttu-id="ecb77-109">状態と Office 365 の分析ツールによって検出されたファイルに関する詳細情報を表示するには、脅威の保護の状態レポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ecb77-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="ecb77-110">Office 365 のセキュリティで&amp;コンプライアンス センターでは、**レポート**を選択して\>**ダッシュ ボード** \> **脅威保護の状態**です。</span><span class="sxs-lookup"><span data-stu-id="ecb77-110">In the Office 365 Security &amp; Compliance Center, choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="ecb77-111">レポートの右上隅の**ビューの詳細テーブル**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ecb77-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="ecb77-112">レポート内で検出されたファイルの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="ecb77-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="ecb77-113">詳細については、実行されたアクションを含む、ファイル名、ファイルのパスなどを表示するのには、ボックスの一覧で項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="ecb77-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="ecb77-114">観察された現象と分析の詳細などの情報を表示するのには、**高度な分析**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecb77-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="ecb77-115">表示し、検査中のファイルに対してアクションを実行</span><span class="sxs-lookup"><span data-stu-id="ecb77-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="ecb77-116">Office 365 のセキュリティで&amp;コンプライアンス センターでは、**脅威の管理**を選択して\>**レビュー** \> **検査**します。</span><span class="sxs-lookup"><span data-stu-id="ecb77-116">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span>
    
2. <span data-ttu-id="ecb77-117">左上隅で、**メール**から**コンテンツ**にフィルターを変更します。</span><span class="sxs-lookup"><span data-stu-id="ecb77-117">In the upper left corner, change the filter from **Email** to **Content**.</span></span>
    
3. <span data-ttu-id="ecb77-118">ファイルの URL を含む、詳細情報を表示するのには、ボックスの一覧で項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="ecb77-118">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="ecb77-119">使用可能なアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecb77-119">Choose an available action.</span></span>
    
  - <span data-ttu-id="ecb77-120">選択**リリース&amp;レポート**ファイルのブロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="ecb77-120">Choose **Release &amp; report** to unblock the file.</span></span> 
    
    <span data-ttu-id="ecb77-121">誤認としてファイルをマイクロソフトに報告を**マイクロソフトにレポートを送信する**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ecb77-121">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 
    
  - <span data-ttu-id="ecb77-122">さらにファイルを調査する**ファイルのダウンロード**を選択してください。</span><span class="sxs-lookup"><span data-stu-id="ecb77-122">Choose **Download file** to investigate the file further.</span></span> 
    
  - <span data-ttu-id="ecb77-p102">検疫済みのアイテムの一覧からファイルを削除する**削除**をクリックします。このオプションを選択する場合は、ビジネス、またはマイクロソフトのチームの SharePoint のオンライン、OneDrive で、それぞれのライブラリからファイルを削除する必要がありますもします。このオプションがないブロックを解除されてからファイルを共有を開くか。</span><span class="sxs-lookup"><span data-stu-id="ecb77-p102">Choose **Delete** to remove the file from the list of quarantined items. If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams. This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="ecb77-126">選択したアイテムの詳細を閉じるに**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ecb77-126">Choose **Close** to close the details for a selected item.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="ecb77-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="ecb77-127">Related topics</span></span>

[<span data-ttu-id="ecb77-128">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ecb77-128">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="ecb77-129">Office 365 の高度な脅威保護のレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="ecb77-129">View the reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  
[<span data-ttu-id="ecb77-130">Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="ecb77-130">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

[<span data-ttu-id="ecb77-131">Office 365 の管理者として検疫されたメッセージやファイルを管理します。</span><span class="sxs-lookup"><span data-stu-id="ecb77-131">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
  

