---
title: SharePoint、OneDrive、Microsoft Teams 用の Microsoft Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/18/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
description: SharePoint Online で、組織の安全なコラボレーションを有効にするには、ビジネス、およびマイクロソフトのチームの OneDrive 内のファイルには、Office 365 の高度な脅威保護を拡張します。
ms.openlocfilehash: ea1c77273be70ce27f60bfaeae3544d605553a32
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532572"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="a57cd-103">SharePoint、OneDrive、Microsoft Teams 用の Microsoft Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="a57cd-103">Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="a57cd-p101">人が定期的にファイルを共有し、SharePoint、OneDrive、およびマイクロソフトのチームを使用して共同作業を行います。[Office 365 の高度な脅威保護](office-365-atp.md)(ATP) のより安全な方法で共同作業を行う組織です。分析ツールは、検出し、チーム サイトおよびドキュメント ライブラリで悪意あるコードとして指定されているファイルをブロックすることができます。SharePoint のオンライン、OneDrive のビジネス、およびマイクロソフトのチームの分析ツールの概要を取得するには、この記事を読むし、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a57cd-p101">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams. With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner. ATP helps detect and block files that are identified as malicious in team sites and document libraries. Read this article to get an overview of ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams, and then take your next steps.</span></span> 
  
> [!TIP]
> <span data-ttu-id="a57cd-p102">この資料で説明するタスクを実行するために Office 365 のグローバル管理者またはセキュリティ管理者でなければなりません。参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="a57cd-p102">In order to perform the tasks described in this article, you must be an Office 365 global administrator or a security administrator. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="how-it-works"></a><span data-ttu-id="a57cd-110">しくみ</span><span class="sxs-lookup"><span data-stu-id="a57cd-110">How it works</span></span>

<span data-ttu-id="a57cd-p103">SharePoint Online でのファイル、ビジネス、およびマイクロソフトのチームの OneDrive 確認された、悪意のある、分析ツールは、そのファイルをロックするのにはファイル ストアに直接統合されます。次の図は、ライブラリで検出された悪意のあるファイルの例を示します。</span><span class="sxs-lookup"><span data-stu-id="a57cd-p103">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file. The following image shows an example of a malicious file detected in a library.</span></span>
  
<span data-ttu-id="a57cd-113">[![悪意のあるものとして検出された 1 つのビジネスの OneDrive 内のファイルのスクリーン ショット](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="a57cd-113">[![Screenshot of files in OneDrive for Business with one detected as malicious](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="a57cd-p104">ブロックされたファイルはドキュメント ライブラリと web、モバイル、またはデスクトップのアプリケーションにも示されています。 ブロックされたファイルを開けなかったり、コピー、移動、共有。人、ただし、ファイルを削除ブロックします。ここでどのようなことの一例が、ユーザーのモバイル デバイス上のようになります。</span><span class="sxs-lookup"><span data-stu-id="a57cd-p104">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared. People can, however, delete a blocked file. Here's an example of what that looks like on a user's mobile device:</span></span>
  
<span data-ttu-id="a57cd-117">[![ビジネスの OneDrive から OneDrive のモバイル アプリケーションからブロックされたファイルを削除するのスクリーン ショット](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="a57cd-117">[![Screenshot of deleting a blocked file from OneDrive for Business from the OneDrive mobile app](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="a57cd-p105">Office 365 の構成方法によってユーザーには、ブロックされたファイルをダウンロードする機能がない可能性があります。ブロックされたファイルのダウンロードがどのようにユーザーのモバイル デバイスを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a57cd-p105">Depending on how Office 365 is configured, people might or might not have the ability to download a blocked file. Here's what downloading a blocked file looks like on a user's mobile device:</span></span>
  
<span data-ttu-id="a57cd-120">[![ビジネスの OneDrive でブロックされたファイルのダウンロードのスクリーン ショット](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="a57cd-120">[![Screenshot of downloading a blocked file in OneDrive for Business](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="a57cd-121">詳細については、 [SharePoint、OneDrive、およびマイクロソフトのチームの Office 365 の分析ツールを有効にする](turn-on-atp-for-spo-odb-and-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a57cd-121">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
  
### <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="a57cd-122">次の点に留意します。</span><span class="sxs-lookup"><span data-stu-id="a57cd-122">Keep the following points in mind</span></span>

- <span data-ttu-id="a57cd-p106">分析ツールでは、ビジネス、またはマイクロソフトのチームの SharePoint のオンライン、OneDrive では、すべてのファイルはスキャンしません。これは仕様です。スマート ヒューリスティックおよび脅威の信号と共有し、ゲストのアクティビティのイベントを使用して、悪意のあるファイルを特定するプロセスを非同期的にファイルがスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="a57cd-p106">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams. This is by design. Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>
    
- <span data-ttu-id="a57cd-126">SharePoint Online で悪意のあるものとして指定されているファイルの場合は、ビジネス、またはマイクロソフトのチームの OneDrive が表示されます[Office 365 の高度な脅威保護のためのレポート](view-reports-for-atp.md)と脅威のエクスプ ローラー ( [Office 365 の脅威インテリジェンス](office-365-ti.md)の一部)。</span><span class="sxs-lookup"><span data-stu-id="a57cd-126">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in Threat Explorer (part of [Office 365 Threat Intelligence](office-365-ti.md)).</span></span>
    
- <span data-ttu-id="a57cd-p107">分析ツールは、組織の全体的な脅威保護戦略、スパム対策とマルウェア対策の保護と安全なリンクと安全な添付ファイルを含む部分です。詳細については、 [Office 365 の脅威から保護する](protect-against-threats.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a57cd-p107">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments. To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="a57cd-p108">SharePoint Online 管理者は、悪意あるコードとして検出されたファイルをダウンロードするユーザーを有効にするかどうかを判断できます。DisallowInfectedFileDownload パラメーターを使用してセット SPOTenant PowerShell コマンドレットを実行して、これは ( [SharePoint、OneDrive、およびマイクロソフトのチームの Office 365 の分析ツールを有効にする](turn-on-atp-for-spo-odb-and-teams.md)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a57cd-p108">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious. This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>
    
## <a name="new-quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="a57cd-131">(New!)オンラインでは、SharePoint の ATP 検査、ビジネス、およびマイクロソフトのチームの OneDrive</span><span class="sxs-lookup"><span data-stu-id="a57cd-131">(New!) Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="a57cd-132">* * 遅延月 2018、セキュリティの[検査](quarantine-email-messages.md)機能で始まる&amp;コンプライアンス センターが拡張される ATP を SharePoint のオンラインでのビジネス、およびマイクロソフトのチームの OneDrive。</span><span class="sxs-lookup"><span data-stu-id="a57cd-132">**Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> **
  
<span data-ttu-id="a57cd-p109">SharePoint Online でのファイル、ビジネス、またはマイクロソフトのチームの OneDrive は ATP を開けない状態、または共有からファイルをブロックするだけでなく、悪意のある、検疫済みのアイテムの一覧でそのファイルが含まれています。(セキュリティ&amp;コンプライアンス センターでは、**脅威の管理**に移動\>**レビュー** \> **検査**し、コンテンツのフィルターします)。</span><span class="sxs-lookup"><span data-stu-id="a57cd-p109">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items. (In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for Content.)</span></span> 
  
<span data-ttu-id="a57cd-135">組織の Office 365 のセキュリティ チームの一部になっている必要がある場合[Office 365 のセキュリティに割り当てられたアクセス権&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)、ダウンロード、リリース、レポート、および分析ツールで悪意あるコードとして検出されたファイルを削除隔離します。</span><span class="sxs-lookup"><span data-stu-id="a57cd-135">If you're part of your organization's Office 365 security team and have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>
  
- <span data-ttu-id="a57cd-p110">**解放してレポート**ファイルは、SharePoint、OneDrive、またはマイクロソフトのチームのそれぞれのチーム サイトまたはドキュメント ライブラリで、ATP のブロック、ファイルを削除します。開き、共有、およびファイルをダウンロードすることもできます。**マイクロソフトにレポートを送信**する] オプションを選択すると、ファイルがマイクロソフトに報告として誤検知します。</span><span class="sxs-lookup"><span data-stu-id="a57cd-p110">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams. Users are then able to open, share, and download the file. And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span> 
    
- <span data-ttu-id="a57cd-p111">検疫; からファイルを削除する**ファイルを削除します。** ただし、ファイルはまだされるを禁止を開く、または共有します。ファイルは、それぞれのドキュメント ライブラリ、またはチーム サイト (SharePoint のオンライン ・ ビジネス、またはマイクロソフトのチームの OneDrive) でも削除しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a57cd-p111">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared. The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span> 
    
- <span data-ttu-id="a57cd-141">**ファイルのダウンロード**を使用すると、ダウンロードし、任意の偽陽性のファイルを分析します。</span><span class="sxs-lookup"><span data-stu-id="a57cd-141">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="a57cd-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="a57cd-142">Next steps</span></span>

- [<span data-ttu-id="a57cd-143">SharePoint、OneDrive、およびマイクロソフトのチームに対して Office 365 の分析ツールを有効に</span><span class="sxs-lookup"><span data-stu-id="a57cd-143">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)
    
- [<span data-ttu-id="a57cd-144">SharePoint、OneDrive、またはマイクロソフトのチームで検出された、悪意のあるファイルに関する情報を表示</span><span class="sxs-lookup"><span data-stu-id="a57cd-144">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
## <a name="related-topics"></a><span data-ttu-id="a57cd-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="a57cd-145">Related topics</span></span>

[<span data-ttu-id="a57cd-146">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a57cd-146">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="a57cd-147">Office 365 の高度な脅威保護のレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="a57cd-147">View the reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  
[<span data-ttu-id="a57cd-148">Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="a57cd-148">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

