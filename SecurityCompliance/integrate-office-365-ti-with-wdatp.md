---
title: Windows Defender Advanced Threat Protection と Office 365 脅威インテリジェンスを統合する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: Windows Defender 高度な脅威保護の脅威の管理の詳細を表示するには、Office 365 の高度な脅威保護を統合します。
ms.openlocfilehash: 48e879c1d41b5aa662f5128e234be91eb8225e7b
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014769"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="b27a2-103">Windows Defender Advanced Threat Protection と Office 365 脅威インテリジェンスを統合する</span><span class="sxs-lookup"><span data-stu-id="b27a2-103">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="b27a2-p101">組織のセキュリティ チームの一部は、の Windows Defender 高度な脅威保護 (ATP) を Office 365 に統合できます。これは、かどうかユーザーのコンピューターは危険に Office 365 の脅威を調査するときに簡単に理解することができます。などの統合を有効にするを参照してください、検出された電子メール メッセージの受信者によって使用されるコンピューターの一覧にも多く最近受信したアラートの分析ツールを Windows Defender でのこれらのマシンがあるどのようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b27a2-p101">If you are part of your organization's security team, you can integrate Office 365 with Windows Defender Advanced Threat Protection (ATP). This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365. For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender ATP.</span></span>
  
<span data-ttu-id="b27a2-107">次の図は、表示される Windows Defender の ATP の統合を有効にする場合、[**デバイス**] タブを示しています。</span><span class="sxs-lookup"><span data-stu-id="b27a2-107">The following image shows the **Devices** tab that you'll see when have Windows Defender ATP integration enabled:</span></span> 
  
![ATP の Windows Defender を有効にすると、アラートがあるコンピューターの一覧を表示できます。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="b27a2-p102">この例では、アラートの分析ツールを Windows Defender では、電子メール メッセージの受信者がある 4 つのマシンを表示できます。コンピューターへのリンクをクリックすると新しいタブで Windows Defender の ATP のマシンのページを開きます。</span><span class="sxs-lookup"><span data-stu-id="b27a2-p102">In this example, you can see that the recipients of the email message have four machines and one has an alert in Windows Defender ATP. Clicking the link to a machine opens the machine page in Windows Defender ATP in a new tab.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="b27a2-111">要件</span><span class="sxs-lookup"><span data-stu-id="b27a2-111">Requirements</span></span>

- <span data-ttu-id="b27a2-112">組織には、Office 365 の脅威インテリジェンスと Windows Defender の分析ツールが必要です。</span><span class="sxs-lookup"><span data-stu-id="b27a2-112">Your organization must have Office 365 Threat Intelligence and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="b27a2-p103">Office 365 のグローバル管理者であるかに割り当てられているセキュリティ管理者の役割を持っている必要があります、[セキュリティ&amp;コンプライアンス センター](https://protection.office.com)です。(を参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="b27a2-p103">You must be an Office 365 global administrator or have a security administrator role assigned in the [Security &amp; Compliance Center](https://protection.office.com). (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="b27a2-115">Office 365 の脅威インテリジェンスと、Windows Defender の ATP ポータルの両方へのアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b27a2-115">You must have access to both Office 365 Threat Intelligence and the Windows Defender ATP portal.</span></span>
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a><span data-ttu-id="b27a2-116">Windows Defender の分析ツールと Office 365 の脅威インテリジェンスを統合するには</span><span class="sxs-lookup"><span data-stu-id="b27a2-116">To integrate Office 365 Threat Intelligence with Windows Defender ATP</span></span>

<span data-ttu-id="b27a2-117">Windows Defender の分析ツールと Office 365 の脅威インテリジェンスを統合することは、Office 365 と、Windows Defender の ATP ポータルの両方を設定します。</span><span class="sxs-lookup"><span data-stu-id="b27a2-117">Integrating Office 365 Threat Intelligence with Windows Defender ATP is set up both in Office 365 and in the Windows Defender ATP portal.</span></span>
  
1. <span data-ttu-id="b27a2-118">移動すると、Office 365 のグローバル セキュリティ管理者は、[https://protection.office.com](https://protection.office.com)と Office 365 は、職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="b27a2-118">As an Office 365 global or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="b27a2-119">**脅威の管理**を選択して\>**脅威のエクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="b27a2-119">Choose **Threat management** \> **Threat explorer**.</span></span>
    
3. <span data-ttu-id="b27a2-120">[**詳細**] メニューには、 **WDATP の設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="b27a2-120">On the **More** menu, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="b27a2-121">**ATP の Windows への接続**を選択します。</span><span class="sxs-lookup"><span data-stu-id="b27a2-121">Select **Connect to Windows ATP**.</span></span>
    
<span data-ttu-id="b27a2-p104">Office 365 内の設定を変更した後は、Windows Defender の ATP からの接続を有効にする必要があります。[Windows Defender の高度な脅威保護のポータルの使用](https://go.microsoft.com/fwlink/?linkid=859690)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b27a2-p104">After you have changed the settings in Office 365, you must enable the connection from Windows Defender ATP. To do that, see [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b27a2-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="b27a2-124">Related topics</span></span>

[<span data-ttu-id="b27a2-125">Office 365 脅威インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="b27a2-125">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="b27a2-126">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b27a2-126">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

