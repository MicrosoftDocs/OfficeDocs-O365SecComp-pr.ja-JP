---
title: IOS デバイス用の APNs 証明書を作成する
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
audience: Admin
ms.topic: article
f1_keywords:
- O365M_APNCertMDM
- O365E_APNCertMDM
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 522b43f4-a2ff-46f6-962a-dd4f47e546a7
description: Office 365 のモバイルデバイス管理で iPad や iPhones などの iOS デバイスを管理するには、最初に APNs 証明書を作成するために、次の手順を実行します。
ms.openlocfilehash: 17dae3e02520cdac2b1381039844d1657b12c4eb
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153759"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="623b6-103">IOS デバイス用の APNs 証明書を作成する</span><span class="sxs-lookup"><span data-stu-id="623b6-103">Create an APNs Certificate for iOS devices</span></span>

 <span data-ttu-id="623b6-104">Office 365 のモバイルデバイス管理で iPad や iPhones などの iOS デバイスを管理するには、APNs 証明書を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="623b6-104">To manage iOS devices like iPad and iPhones in Mobile Device Management for Office 365 you must create an APNs certificate.</span></span> 
  
<span data-ttu-id="623b6-105">これを行うには、ポータルページの [**設定**] リンクからの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="623b6-105">To do this, follow the steps from the **Set up** link on the portal page.</span></span> <span data-ttu-id="623b6-106">( \*\* &amp;セキュリティコンプライアンスセンター\*\* \>の**セキュリティポリシー** \>に移動し、**デバイス管理** \>の**設定を管理**します。)</span><span class="sxs-lookup"><span data-stu-id="623b6-106">(Go to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings**.)</span></span>
  
![モバイルデバイス管理をセットアップする必要があり、推奨される手順](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. <span data-ttu-id="623b6-108">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span><span class="sxs-lookup"><span data-stu-id="623b6-108">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span></span>
    
2. <span data-ttu-id="623b6-109">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span><span class="sxs-lookup"><span data-stu-id="623b6-109">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span></span> 
    
    ![[APN 証明書のインストール] ダイアログボックス](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. <span data-ttu-id="623b6-111"> Select *\*Next*\*. </span><span class="sxs-lookup"><span data-stu-id="623b6-111">Select **Next**.</span></span>
    
4. <span data-ttu-id="623b6-112"> Create an APN certificate.</span><span class="sxs-lookup"><span data-stu-id="623b6-112">Create an APN certificate.</span></span>
    
  - <span data-ttu-id="623b6-113">Select **Apple APNS Portal** to open the Apple Push Certificates Portal. </span><span class="sxs-lookup"><span data-stu-id="623b6-113">Select **Apple APNS Portal** to open the Apple Push Certificates Portal.</span></span> 
    
    ![Apple APNS ポータルが選択されている状態で APN 通知証明書ダイアログをインストールする](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - <span data-ttu-id="623b6-115">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="623b6-115">Sign in with an Apple ID.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="623b6-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="623b6-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span> 
  
  - <span data-ttu-id="623b6-118">Select **Create a Certificate** and accept the **Terms of Use**.</span><span class="sxs-lookup"><span data-stu-id="623b6-118">Select **Create a Certificate** and accept the **Terms of Use**.</span></span>
    
  - <span data-ttu-id="623b6-119">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span><span class="sxs-lookup"><span data-stu-id="623b6-119">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span></span>
    
  - <span data-ttu-id="623b6-120">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span><span class="sxs-lookup"><span data-stu-id="623b6-120">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="623b6-121">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="623b6-121">If you're having trouble downloading the certificate, refresh your browser.</span></span> 
  
5. <span data-ttu-id="623b6-122">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span><span class="sxs-lookup"><span data-stu-id="623b6-122">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span></span> 
    
6. <span data-ttu-id="623b6-123"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="623b6-123">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
    ![[参照] ボタンをクリックして Apple からダウンロードした APNS 証明書を選択します。](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. <span data-ttu-id="623b6-125">**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="623b6-125">Select **Finish**.</span></span>
    
<span data-ttu-id="623b6-126">**セキュリティ&amp; /コンプライアンスセンター** \> **のセキュリティポリシー** \>に戻る**デバイス管理** \> **設定を管理**してセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="623b6-126">Go back to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings** to complete setup.</span></span> 
  

