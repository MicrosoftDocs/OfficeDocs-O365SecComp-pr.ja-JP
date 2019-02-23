---
title: Windows Defender Advanced Threat Protection と Office 365 脅威インテリジェンスを統合する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Windows Defender advanced threat protection を使用して Office 365 advanced threat protection を統合し、より詳細な脅威管理情報を表示します。
ms.openlocfilehash: 892d04152d6029c48a52d37c6235d45a8ba67b81
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222816"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="ff3c1-103">Windows Defender Advanced Threat Protection と Office 365 脅威インテリジェンスを統合する</span><span class="sxs-lookup"><span data-stu-id="ff3c1-103">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="ff3c1-p101">組織のセキュリティチームに参加している場合は、Windows Defender advanced threat protection を使用して Office 365 advanced threat protection および脅威インテリジェンス機能を統合することができます。これは、Office 365 で脅威を調査しているときに、ユーザーのコンピューターが危険にさらされているかどうかをすばやく理解するのに役立ちます。たとえば、統合が有効になると、検出された電子メールメッセージの受信者によって使用されるコンピューターの一覧と、それらのコンピューターが Windows Defender Advanced Threat Protection で保持している最近の通知の数も表示できます。</span><span class="sxs-lookup"><span data-stu-id="ff3c1-p101">If you are part of your organization's security team, you can integrate Office 365 Advanced Threat Protection and Threat Intelligence features with Windows Defender Advanced Threat Protection. This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365. For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="ff3c1-107">次の図は、Windows Defender Advanced Threat Protection の統合が有効になっている場合に表示される [**デバイス**] タブを示しています。</span><span class="sxs-lookup"><span data-stu-id="ff3c1-107">The following image shows the **Devices** tab that you'll see when have Windows Defender Advanced Threat Protection integration enabled:</span></span> 
  
![Windows Defender ATP が有効になっている場合は、アラートがあるコンピューターの一覧を表示できます。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="ff3c1-p102">この例では、電子メールメッセージの受信者に4つのデバイスがあり、1つに通知があることがわかります。デバイスのリンクをクリックすると、Windows Defender Advanced Threat Protection ポータルのページが開きます。</span><span class="sxs-lookup"><span data-stu-id="ff3c1-p102">In this example, you can see that the recipients of the email message have four devices and one has an alert. Clicking the link for a device opens its page in the Windows Defender Advanced Threat Protection portal.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ff3c1-111">要件</span><span class="sxs-lookup"><span data-stu-id="ff3c1-111">Requirements</span></span>

- <span data-ttu-id="ff3c1-112">組織には、Office 365 の脅威インテリジェンスと Windows Defender ATP が必要です。</span><span class="sxs-lookup"><span data-stu-id="ff3c1-112">Your organization must have Office 365 Threat Intelligence and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="ff3c1-p103">Office 365 グローバル管理者であるか、セキュリティ管理者の役割 (セキュリティ管理者など) が[ &amp;セキュリティコンプライアンスセンター](https://protection.office.com)で割り当てられている必要があります。( [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可を](permissions-in-the-security-and-compliance-center.md)参照してください)</span><span class="sxs-lookup"><span data-stu-id="ff3c1-p103">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com). (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="ff3c1-115">Office 365 の脅威インテリジェンスと Windows Defender Advanced threat Protection ポータルの両方にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff3c1-115">You must have access to both Office 365 Threat Intelligence and the Windows Defender Advanced Threat Protection portal.</span></span>
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a><span data-ttu-id="ff3c1-116">Office 365 脅威インテリジェンスと Windows Defender ATP を統合するには</span><span class="sxs-lookup"><span data-stu-id="ff3c1-116">To integrate Office 365 Threat Intelligence with Windows Defender ATP</span></span>

<span data-ttu-id="ff3c1-117">office 365 の脅威インテリジェンスと windows defender advanced threat protection の統合は、office 365 Security & コンプライアンスセンターと windows defender advanced threat protection ポータルの両方を使用してセットアップされています。</span><span class="sxs-lookup"><span data-stu-id="ff3c1-117">Integrating Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection is set up by using both the Office 365 Security & Compliance Center AND the Windows Defender Advanced Threat Protection portal.</span></span>
  
1. <span data-ttu-id="ff3c1-118">office 365 全体管理者またはセキュリティ管理者として[https://protection.office.com](https://protection.office.com) 、に移動して、office 365 の職場または学校アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="ff3c1-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="ff3c1-119">[**脅威管理** \> **エクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff3c1-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="ff3c1-120">![脅威管理メニューのエクスプローラー](media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="ff3c1-120">![Explorer in Threat Management menu](media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="ff3c1-121">画面の右上にある [ **wdatp 設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff3c1-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="ff3c1-122">[windows Defender atp 接続] ダイアログボックスで、[windows ATP への接続] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="ff3c1-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Windows Defender ATP 接続](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="ff3c1-p104">Windows Defender Advanced Threat Protection で接続を有効にします。「 [Windows Defender Advanced Threat Protection ポータルの使用](https://go.microsoft.com/fwlink/?linkid=859690)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff3c1-p104">Enable the connection in Windows Defender Advanced Threat Protection. See [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="ff3c1-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff3c1-126">Related topics</span></span>

[<span data-ttu-id="ff3c1-127">Office 365 脅威インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="ff3c1-127">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="ff3c1-128">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ff3c1-128">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

