---
title: Office 365 ATP for SharePoint、OneDrive、Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection を SharePoint Online、OneDrive for Business、Microsoft Teams のファイルに拡張して、組織にとってより安全なコラボレーションを可能にします。
ms.openlocfilehash: a73f978ca40571e33864061cfe9538033579b3c7
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408262"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="5df1e-103">Office 365 ATP for SharePoint、OneDrive、Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5df1e-103">Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="5df1e-104">SharePoint、OneDrive、Microsoft Teams の Office 365 ATP の概要</span><span class="sxs-lookup"><span data-stu-id="5df1e-104">Overview of Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="5df1e-105">ユーザーは、SharePoint、OneDrive、Microsoft Teams を使用して、ファイルを定期的に共有し、共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5df1e-105">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="5df1e-106">[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) を使用すると、組織は安全な方法で共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5df1e-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner.</span></span> <span data-ttu-id="5df1e-107">ATP は、チームサイトおよびドキュメントライブラリで悪意のあるものとして識別されたファイルを検出およびブロックするのに便利です。</span><span class="sxs-lookup"><span data-stu-id="5df1e-107">ATP helps detect and block files that are identified as malicious in team sites and document libraries.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="5df1e-108">メカニズム</span><span class="sxs-lookup"><span data-stu-id="5df1e-108">How it works</span></span>

<span data-ttu-id="5df1e-109">SharePoint Online、OneDrive for Business、および Microsoft Teams のファイルが悪意のあるものとして識別されると、そのファイルをロックするために、ATP はファイルストアと直接統合されます。</span><span class="sxs-lookup"><span data-stu-id="5df1e-109">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file.</span></span> <span data-ttu-id="5df1e-110">次の図は、ライブラリ内で検出された悪意のあるファイルの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="5df1e-110">The following image shows an example of a malicious file detected in a library.</span></span>
  
<span data-ttu-id="5df1e-111">[![悪意のあるものとして検出された OneDrive for Business のファイル](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="5df1e-111">[![Files in OneDrive for Business with one detected as malicious](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="5df1e-112">ブロックされたファイルは、ドキュメントライブラリ、web、モバイル、またはデスクトップの各アプリケーションに表示されたままですが、ブロックされたファイルを開く、コピー、移動、または共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="5df1e-112">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared.</span></span> <span data-ttu-id="5df1e-113">ただし、ユーザーはブロックされたファイルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="5df1e-113">People can, however, delete a blocked file.</span></span> <span data-ttu-id="5df1e-114">ユーザーのモバイルデバイスに表示されるものの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5df1e-114">Here's an example of what that looks like on a user's mobile device:</span></span>
  
<span data-ttu-id="5df1e-115">[![Onedrive モバイルアプリから OneDrive for business からブロックされたファイルを削除する](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="5df1e-115">[![Deleting a blocked file from OneDrive for Business from the OneDrive mobile app](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="5df1e-116">Office 365 の構成方法によっては、ブロックされたファイルをダウンロードすることができるかどうかはユーザーによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5df1e-116">Depending on how Office 365 is configured, people might or might not have the ability to download a blocked file.</span></span> <span data-ttu-id="5df1e-117">ブロックされたファイルをダウンロードすると、ユーザーのモバイルデバイスで次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="5df1e-117">Here's what downloading a blocked file looks like on a user's mobile device:</span></span>
  
<span data-ttu-id="5df1e-118">[![OneDrive for Business でブロックされたファイルをダウンロードする](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="5df1e-118">[![Downloading a blocked file in OneDrive for Business](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="5df1e-119">詳細については、「 [Turn On Office 365 ATP For SharePoint, OneDrive, And Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5df1e-119">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
  
## <a name="keep-these-points-in-mind"></a><span data-ttu-id="5df1e-120">これらの点を念頭に置いてください。</span><span class="sxs-lookup"><span data-stu-id="5df1e-120">Keep these points in mind</span></span>

- <span data-ttu-id="5df1e-121">ATP では、SharePoint Online、OneDrive for Business、または Microsoft Teams のすべてのファイルがスキャンされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="5df1e-121">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="5df1e-122">これは仕様どおりです。</span><span class="sxs-lookup"><span data-stu-id="5df1e-122">This is by design.</span></span> <span data-ttu-id="5df1e-123">ファイルは、共有とゲストアクティビティイベントを使用するプロセスによって非同期でスキャンされ、スマートヒューリスティックおよび脅威信号を使用して悪意のあるファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="5df1e-123">Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="5df1e-124">SharePoint サイトが[モダンな環境](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)を使用するように構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5df1e-124">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="5df1e-125">ファイルが悪意のあるものとして認識され、ブロックされると、これがモダンな機能で発生していることがわかりますが、クラシックビューでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="5df1e-125">When a file is identified as malicious and blocked, people can see that this has occurred in the Modern experience, but not the Classic view.</span></span> <span data-ttu-id="5df1e-126">ATP 保護は、モダンな表示とクラシック表示のどちらを使用するかに適用されます。ただし、ファイルがブロックされているという視覚インジケーターは、モダンな環境でのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="5df1e-126">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are present only in the Modern experience.</span></span>
    
- <span data-ttu-id="5df1e-127">SharePoint Online、OneDrive for Business、または Microsoft Teams で悪意のあるものとして識別されたファイルは、 [Office 365 Advanced Threat Protection](view-reports-for-atp.md)および[Explorer (およびリアルタイム検出)](threat-explorer.md)のレポートで表示されます。</span><span class="sxs-lookup"><span data-stu-id="5df1e-127">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>
    
- <span data-ttu-id="5df1e-128">ATP は、組織の全体的な脅威保護戦略の一部であり、スパム対策とマルウェア対策の保護、および安全なリンクと安全な添付ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5df1e-128">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments.</span></span> <span data-ttu-id="5df1e-129">詳細については、「 [Office 365 の脅威から保護](protect-against-threats.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5df1e-129">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="5df1e-130">SharePoint Online 管理者は、悪意のあるものとして検出されたファイルをユーザーがダウンロードできるようにするかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="5df1e-130">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious.</span></span> <span data-ttu-id="5df1e-131">これを行うには、DisallowInfectedFileDownload パラメーターを使用して Set-spotenant PowerShell コマンドレットを実行します (「 [Turn On Office 365 ATP For SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="5df1e-131">This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>
    
## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="5df1e-132">SharePoint Online、OneDrive for Business、Microsoft Teams 用の ATP での検疫</span><span class="sxs-lookup"><span data-stu-id="5df1e-132">Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="5df1e-133">2018年5月の初期[](quarantine-email-messages.md)段階では、セキュリティ&amp; /コンプライアンスセンターの検疫機能が、SharePoint Online、OneDrive For business、MICROSOFT Teams 用の ATP に拡張されています。</span><span class="sxs-lookup"><span data-stu-id="5df1e-133">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
  
<span data-ttu-id="5df1e-134">SharePoint Online、OneDrive for Business、または Microsoft Teams のファイルが悪意のあるものとして識別されると、そのファイルは、検疫されたアイテムの一覧に含まれています。</span><span class="sxs-lookup"><span data-stu-id="5df1e-134">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items.</span></span> <span data-ttu-id="5df1e-135">&amp; (セキュリティコンプライアンスセンターで、[**脅威管理** \> **レビュー** \> ] [**コンテンツ**の**検疫**とフィルター] に移動します。)</span><span class="sxs-lookup"><span data-stu-id="5df1e-135">(In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for **Content**.)</span></span> 
  
<span data-ttu-id="5df1e-136">組織の Office 365 セキュリティチームに属していて、 [office 365 セキュリティ&amp;コンプライアンスセンターで必要なアクセス許可が割り当てら](permissions-in-the-security-and-compliance-center.md)れている場合は、ATP によって悪意があると検出されたファイルをダウンロード、リリース、レポート、および削除することができます。検疫から。</span><span class="sxs-lookup"><span data-stu-id="5df1e-136">If you're part of your organization's Office 365 security team and have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>
  
- <span data-ttu-id="5df1e-137">ファイルを**リリースおよびレポートすると**、SharePoint、OneDrive、Microsoft Teams の各チームサイトまたはドキュメントライブラリにあるファイルの ATP ブロックが削除されます。</span><span class="sxs-lookup"><span data-stu-id="5df1e-137">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams.</span></span> <span data-ttu-id="5df1e-138">その後、ユーザーはファイルを開いて、共有し、ダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="5df1e-138">Users are then able to open, share, and download the file.</span></span> <span data-ttu-id="5df1e-139">そして、[ **microsoft にレポートを送信**] オプションが選択されている場合、ファイルは誤検知として microsoft に報告されます。</span><span class="sxs-lookup"><span data-stu-id="5df1e-139">And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span> 
    
- <span data-ttu-id="5df1e-140">**ファイルを削除する**と、検疫からファイルが削除されます。ただし、ファイルは開いたり共有したりすることはブロックされたままです。</span><span class="sxs-lookup"><span data-stu-id="5df1e-140">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared.</span></span> <span data-ttu-id="5df1e-141">また、ファイルは、対応するドキュメントライブラリまたはチームサイト (SharePoint Online、OneDrive for Business、または Microsoft Teams) で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5df1e-141">The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span> 
    
- <span data-ttu-id="5df1e-142">**ファイルをダウンロード**すると、誤検知のためにファイルをダウンロードして分析することができます。</span><span class="sxs-lookup"><span data-stu-id="5df1e-142">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="5df1e-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="5df1e-143">Next steps</span></span>

1. [<span data-ttu-id="5df1e-144">SharePoint、OneDrive、Microsoft Teams の Office 365 ATP を有効にする</span><span class="sxs-lookup"><span data-stu-id="5df1e-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)
    
2. [<span data-ttu-id="5df1e-145">SharePoint、OneDrive、Microsoft Teams で検出された悪意のあるファイルに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="5df1e-145">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
