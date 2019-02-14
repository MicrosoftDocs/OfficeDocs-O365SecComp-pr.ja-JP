---
title: Windows Defender Advanced Threat Protection と Office 365 脅威インテリジェンスを統合する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection: M365-security-compliance
description: Windows Defender 高度な脅威保護の脅威の管理の詳細を表示するには、Office 365 の高度な脅威保護を統合します。
ms.openlocfilehash: f8f5f50af10fb668aa67b68604e95e8dd19c9e69
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995208"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="4129e-103">Windows Defender Advanced Threat Protection と Office 365 脅威インテリジェンスを統合する</span><span class="sxs-lookup"><span data-stu-id="4129e-103">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="4129e-p101">組織のセキュリティ チームの一部の場合は、Windows Defender の高度な脅威保護と Office 365 の高度な脅威保護し、脅威のインテリジェンス機能を統合できます。これは、かどうかユーザーのコンピューターは危険に Office 365 の脅威を調査するときに簡単に理解することができます。たとえば、統合を有効にするは、方法として、これらのマシンがある Windows Defender の高度な脅威保護の新しいアラートの数も、検出された電子メール メッセージの受信者によって使用されるコンピューターの一覧を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4129e-p101">If you are part of your organization's security team, you can integrate Office 365 Advanced Threat Protection and Threat Intelligence features with Windows Defender Advanced Threat Protection. This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365. For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="4129e-107">次の図は、表示される Windows Defender の高度な脅威保護の統合を有効にする場合、[**デバイス**] タブを示しています。</span><span class="sxs-lookup"><span data-stu-id="4129e-107">The following image shows the **Devices** tab that you'll see when have Windows Defender Advanced Threat Protection integration enabled:</span></span> 
  
![ATP の Windows Defender を有効にすると、アラートがあるコンピューターの一覧を表示できます。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="4129e-p102">この例では、警告が、電子メール メッセージの受信者がある 4 つのデバイスを表示できます。デバイスへのリンクをクリックすると Windows Defender の高度な脅威保護のポータルでそのページを開きます。</span><span class="sxs-lookup"><span data-stu-id="4129e-p102">In this example, you can see that the recipients of the email message have four devices and one has an alert. Clicking the link for a device opens its page in the Windows Defender Advanced Threat Protection portal.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="4129e-111">要件</span><span class="sxs-lookup"><span data-stu-id="4129e-111">Requirements</span></span>

- <span data-ttu-id="4129e-112">組織には、Office 365 の脅威インテリジェンスと Windows Defender の分析ツールが必要です。</span><span class="sxs-lookup"><span data-stu-id="4129e-112">Your organization must have Office 365 Threat Intelligence and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="4129e-p103">Office 365 のグローバル管理者であるかに割り当てられているセキュリティ管理者ロール (セキュリティ管理者など) を持っている必要があります、[セキュリティ&amp;コンプライアンス センター](https://protection.office.com)です。(を参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="4129e-p103">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com). (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="4129e-115">Office 365 の脅威インテリジェンスと高度な脅威保護の Windows Defender のポータルの両方へのアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4129e-115">You must have access to both Office 365 Threat Intelligence and the Windows Defender Advanced Threat Protection portal.</span></span>
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a><span data-ttu-id="4129e-116">Windows Defender の分析ツールと Office 365 の脅威インテリジェンスを統合するには</span><span class="sxs-lookup"><span data-stu-id="4129e-116">To integrate Office 365 Threat Intelligence with Windows Defender ATP</span></span>

<span data-ttu-id="4129e-117">Windows Defender の高度な脅威保護と Office 365 の脅威インテリジェンスを統合することについては、両方の Office 365 のセキュリティ & コンプライアンス センターとの高度な脅威保護の Windows Defender のポータルを使用して、設定します。</span><span class="sxs-lookup"><span data-stu-id="4129e-117">Integrating Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection is set up by using both the Office 365 Security & Compliance Center AND the Windows Defender Advanced Threat Protection portal.</span></span>
  
1. <span data-ttu-id="4129e-118">移動すると、Office 365 のグローバル管理者またはセキュリティ管理者は、[https://protection.office.com](https://protection.office.com)と Office 365 は、職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="4129e-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="4129e-119">**脅威の管理**を選択して\>**エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="4129e-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="4129e-120">![脅威の管理] メニューのエクスプ ローラー](media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="4129e-120">![Explorer in Threat Management menu](media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="4129e-121">画面の右上隅では、 **WDATP の設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4129e-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="4129e-122">Windows Defender の ATP の接続] ダイアログ ボックスで、ATP の Windows への接続をオンにします。</span><span class="sxs-lookup"><span data-stu-id="4129e-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Windows Defender の ATP の接続](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="4129e-p104">Windows Defender の高度な脅威保護の接続を有効にします。[Windows Defender の高度な脅威保護のポータルの使用](https://go.microsoft.com/fwlink/?linkid=859690)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4129e-p104">Enable the connection in Windows Defender Advanced Threat Protection. See [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="4129e-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="4129e-126">Related topics</span></span>

[<span data-ttu-id="4129e-127">Office 365 脅威インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="4129e-127">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="4129e-128">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4129e-128">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

