---
title: Microsoft Defender Advanced Threat Protection を使用して Office 365 Advanced Threat Protection を統合する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Microsoft Defender Advanced Threat Protection を使用して Office 365 Advanced Threat Protection を統合し、より詳細な脅威管理情報を表示します。
ms.openlocfilehash: 2d1c88f9911a9940589cdafcc7b12980f2e61a7e
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852561"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="4ce7e-103">Microsoft Defender Advanced Threat Protection を使用して Office 365 Advanced Threat Protection を統合する</span><span class="sxs-lookup"><span data-stu-id="4ce7e-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="4ce7e-104">組織のセキュリティチームに参加している場合は、 [Microsoft Defender Advanced Threat protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)を使用して[Office 365 advanced threat protection](office-365-atp.md)と関連調査および応答機能を統合することができます。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-104">If you are part of your organization's security team, you can integrate [Office 365 Advanced Threat Protection](office-365-atp.md) and related investigation and response features with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span> <span data-ttu-id="4ce7e-105">これは、Office 365 で脅威を調査しているときに、ユーザーのコンピューターが危険にさらされているかどうかをすばやく理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="4ce7e-106">たとえば、統合が有効になると、検出された電子メールメッセージの受信者によって使用されるコンピューターの一覧、およびそれらのコンピューターが Microsoft Defender Advanced Threat Protection で保持している最近の通知の数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Microsoft Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="4ce7e-107">次の図は、Microsoft Defender ATP 統合が有効になっている場合に表示される [**デバイス**] タブを示しています。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-107">The following image shows the **Devices** tab that you'll see when have Microsoft Defender ATP integration enabled:</span></span>
  
![Microsoft Defender ATP が有効になっている場合は、アラートがあるコンピューターの一覧を表示できます。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="4ce7e-109">この例では、電子メールメッセージの受信者に4つのデバイスがあり、1つに通知があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="4ce7e-110">デバイスのリンクをクリックすると、Microsoft Defender セキュリティセンターにそのページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="4ce7e-111">要件</span><span class="sxs-lookup"><span data-stu-id="4ce7e-111">Requirements</span></span>

- <span data-ttu-id="4ce7e-112">組織では、Office 365 ATP Plan 2 (または Office 365 E5) と Microsoft Defender ATP を所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-112">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="4ce7e-113">Office 365 グローバル管理者であるか、セキュリティ管理者の役割 (セキュリティ管理者など) が[ &amp;セキュリティコンプライアンスセンター](https://protection.office.com)で割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-113">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="4ce7e-114">( [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可を](permissions-in-the-security-and-compliance-center.md)参照してください)</span><span class="sxs-lookup"><span data-stu-id="4ce7e-114">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="4ce7e-115">セキュリティ & コンプライアンスセンターと Microsoft Defender セキュリティセンターの両方の[エクスプローラー (またはリアルタイム検出)](threat-explorer.md)にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-115">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="4ce7e-116">Microsoft Defender ATP を使用して Office 365 ATP を統合するには</span><span class="sxs-lookup"><span data-stu-id="4ce7e-116">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="4ce7e-117">Microsoft Defender ATP との Office 365 ATP の統合は、セキュリティ & コンプライアンスセンターと Microsoft Defender セキュリティセンターの両方を使用してセットアップされています。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-117">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="4ce7e-118">Office 365 全体管理者またはセキュリティ管理者として[https://protection.office.com](https://protection.office.com) 、に移動して、office 365 の職場または学校アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span>
    
2. <span data-ttu-id="4ce7e-119">[**脅威管理** \> **エクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="4ce7e-120">![脅威管理メニューのエクスプローラー](media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="4ce7e-120">![Explorer in Threat Management menu](media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="4ce7e-121">画面の右上にある [ **Wdatp 設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="4ce7e-122">[Windows Defender ATP 接続] ダイアログボックスで、[Windows ATP への接続] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Microsoft Defender ATP 接続](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="4ce7e-124">Microsoft Defender セキュリティセンターで接続を有効にします。</span><span class="sxs-lookup"><span data-stu-id="4ce7e-124">Enable the connection in the Microsoft Defender Security Center.</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="4ce7e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ce7e-125">Related topics</span></span>

[<span data-ttu-id="4ce7e-126">Office 365 の脅威の調査と対応</span><span class="sxs-lookup"><span data-stu-id="4ce7e-126">Office 365 Threat Investigation and Response</span></span>](office-365-ti.md)
  
[<span data-ttu-id="4ce7e-127">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4ce7e-127">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

