---
title: iOS デバイス用の APNs 証明書を作成する
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
ms.audience: Admin
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
description: Office 365 のモバイルデバイス管理で iPad や iphones などの iOS デバイスを管理するには、最初に APNs 証明書を作成するために、次の手順を実行します。
ms.openlocfilehash: 5f82690f0add5f1aae95a089d9cdfc0b320ae596
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220457"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="7479c-103">iOS デバイス用の APNs 証明書を作成する</span><span class="sxs-lookup"><span data-stu-id="7479c-103">Create an APNs Certificate for iOS devices</span></span>

 <span data-ttu-id="7479c-104">Office 365 のモバイルデバイス管理で iPad や iphones などの iOS デバイスを管理するには、APNs 証明書を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7479c-104">To manage iOS devices like iPad and iPhones in Mobile Device Management for Office 365 you must create an APNs certificate.</span></span> 
  
<span data-ttu-id="7479c-p101">これを行うには、ポータルページの [**設定**] リンクからの手順を実行します。( \*\* &amp;セキュリティコンプライアンスセンター\*\* \>の**セキュリティポリシー** \>に移動し、**デバイス管理** \>の**設定を管理**します。)</span><span class="sxs-lookup"><span data-stu-id="7479c-p101">To do this, follow the steps from the **Set up** link on the portal page. (Go to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings**.)</span></span>
  
![モバイルデバイス管理をセットアップする必要があり、推奨される手順](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. <span data-ttu-id="7479c-108">[ **iOS デバイス用の APNs 証明書の構成**] の横にある [**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7479c-108">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span></span>
    
2. <span data-ttu-id="7479c-109">[ **CSR ファイルをダウンロード**し、証明書の署名要求をコンピューター上のどこかに保存します] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7479c-109">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span></span> 
    
    ![[APN 証明書のインストール] ダイアログボックス](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. <span data-ttu-id="7479c-111">[ **次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7479c-111">Select **Next**.</span></span>
    
4. <span data-ttu-id="7479c-112">APN 証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="7479c-112">Create an APN certificate.</span></span>
    
  - <span data-ttu-id="7479c-113">apple **APNS portal**を選択して、apple プッシュ証明書ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7479c-113">Select **Apple APNS Portal** to open the Apple Push Certificates Portal.</span></span> 
    
    ![Apple APNS ポータルが選択されている状態で APN 通知証明書ダイアログをインストールする](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - <span data-ttu-id="7479c-115">Apple ID でサインインします。</span><span class="sxs-lookup"><span data-stu-id="7479c-115">Sign in with an Apple ID.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7479c-p102">アカウントを管理するユーザーが残っている場合でも、組織との間で使用される電子メールアカウントに関連付けられている会社の Apple ID を使用します。この id は、証明書の更新時に同じ id を使用する必要があるため、保存します。</span><span class="sxs-lookup"><span data-stu-id="7479c-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span> 
  
  - <span data-ttu-id="7479c-118">[**証明書を作成**し、**使用条件**に同意します] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7479c-118">Select **Create a Certificate** and accept the **Terms of Use**.</span></span>
    
  - <span data-ttu-id="7479c-119">Office 365 からコンピューターにダウンロードした証明書の署名要求を**参照**し、[**アップロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7479c-119">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span></span>
    
  - <span data-ttu-id="7479c-120">Apple プッシュ証明書ポータルによって作成された APN 証明書をコンピューターに**ダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="7479c-120">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="7479c-121">証明書のダウンロードで問題が発生した場合は、ブラウザーを更新します。</span><span class="sxs-lookup"><span data-stu-id="7479c-121">If you're having trouble downloading the certificate, refresh your browser.</span></span> 
  
5. <span data-ttu-id="7479c-122">Office 365 に戻り、[**次**へ] を選択して、[ **APNS 証明書のアップロード**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7479c-122">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span></span> 
    
6. <span data-ttu-id="7479c-123">Apple プッシュ証明書ポータルからダウンロードした APN 証明書に移動します。</span><span class="sxs-lookup"><span data-stu-id="7479c-123">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
    ![[参照] ボタンをクリックして Apple からダウンロードした APNS 証明書を選択します。](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. <span data-ttu-id="7479c-125">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7479c-125">Select **Finish**.</span></span>
    
<span data-ttu-id="7479c-126">**セキュリティ&amp; /コンプライアンスセンター** \> **のセキュリティポリシー** \>に戻る**デバイス管理** \> **設定を管理**してセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="7479c-126">Go back to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings** to complete setup.</span></span> 
  

