---
title: IOS デバイス用の Apn 証明書を作成します。
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_APNCertMDM
- O365E_APNCertMDM
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 522b43f4-a2ff-46f6-962a-dd4f47e546a7
description: Office 365 の iPad とモバイル デバイス管理の iPhones のように iOS のデバイスを管理するために最初に Apn の証明書を作成するのにはこれら手順を実行します。
ms.openlocfilehash: 28e8888d7dd57c3052cdcb5994725f11a5f0445f
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272052"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="c944b-103">IOS デバイス用の Apn 証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="c944b-103">Create an APNs Certificate for iOS devices</span></span>

 <span data-ttu-id="c944b-104">Office 365 の iPad とモバイル デバイス管理の iPhones のように iOS のデバイスを管理するには、Apn の証明書を作成してください。</span><span class="sxs-lookup"><span data-stu-id="c944b-104">To manage iOS devices like iPad and iPhones in Mobile Device Management for Office 365 you must create an APNs certificate.</span></span> 
  
<span data-ttu-id="c944b-p101">これを行うには、ポータル ページ**設定**リンクの手順に従います。(には、**セキュリティ&amp;コンプライアンス センター** \> **セキュリティ ポリシー** \> **デバイス管理** \> **の設定の管理**)。</span><span class="sxs-lookup"><span data-stu-id="c944b-p101">To do this, follow the steps from the **Set up** link on the portal page. (Go to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings**.)</span></span>
  
![モバイル デバイスの管理に必要な推奨手順を設定します](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. <span data-ttu-id="c944b-108">**IOS デバイス用の Apn 証明書を構成する**] の横にある**設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="c944b-108">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span></span>
    
2. <span data-ttu-id="c944b-109">**CSR ファイルをダウンロード**] を選択し、任意の場所に証明書署名要求を保存する、わかりやすいコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="c944b-109">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span></span> 
    
    ![APN の証明書] ダイアログ ボックスをインストールします。](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. <span data-ttu-id="c944b-111">**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="c944b-111">Select **Next**.</span></span>
    
4. <span data-ttu-id="c944b-112">APN の証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="c944b-112">Create an APN certificate.</span></span>
    
  - <span data-ttu-id="c944b-113">開くには、Apple のプッシュ証明書ポータル**アップル APN のポータル**を選択します。</span><span class="sxs-lookup"><span data-stu-id="c944b-113">Select **Apple APNS Portal** to open the Apple Push Certificates Portal.</span></span> 
    
    ![選択 Apple APN ポータルでの APN 通知証明書] ダイアログをインストールします。](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - <span data-ttu-id="c944b-115">Apple ID でサインイン</span><span class="sxs-lookup"><span data-stu-id="c944b-115">Sign in with an Apple ID.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c944b-p102">Apple ID は、アカウントを管理しているユーザーを離れた場合でも、組織に残る電子メール アカウントに関連付けられている会社を使用します。証明書を更新する時と同じ ID を使用する必要がありますので、この ID を保存します。</span><span class="sxs-lookup"><span data-stu-id="c944b-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span> 
  
  - <span data-ttu-id="c944b-118">**証明書の作成**を選択し、**使用条件**に同意します。</span><span class="sxs-lookup"><span data-stu-id="c944b-118">Select **Create a Certificate** and accept the **Terms of Use**.</span></span>
    
  - <span data-ttu-id="c944b-119">証明書署名要求**をアップロード**を選択し、Office 365 からコンピューターにダウンロードするには、**参照**をします。</span><span class="sxs-lookup"><span data-stu-id="c944b-119">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span></span>
    
  - <span data-ttu-id="c944b-120">**ダウンロード**APN の証明書は、お使いのコンピューターに Apple プッシュ証明書ポータルによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="c944b-120">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="c944b-121">、証明書のダウンロードで問題が発生した場合は、ブラウザーを更新します。</span><span class="sxs-lookup"><span data-stu-id="c944b-121">If you're having trouble downloading the certificate, refresh your browser.</span></span> 
  
5. <span data-ttu-id="c944b-122">Office 365 に戻るし、**次****アップロード APN の証明書**のページを表示するを選択します。</span><span class="sxs-lookup"><span data-stu-id="c944b-122">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span></span> 
    
6. <span data-ttu-id="c944b-123">アップル プッシュ証明書ポータルからダウンロードした APN の証明書を参照します。</span><span class="sxs-lookup"><span data-stu-id="c944b-123">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
    ![アップルからダウンロードした APN の証明書を選択するのには [参照] ボタンをクリックします。](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. <span data-ttu-id="c944b-125">**終了**を選択します。</span><span class="sxs-lookup"><span data-stu-id="c944b-125">Select **Finish**.</span></span>
    
<span data-ttu-id="c944b-126">戻る**セキュリティ&amp;コンプライアンス センター** \> **セキュリティ ポリシー** \> **デバイス管理** \> **設定の管理**セットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="c944b-126">Go back to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings** to complete setup.</span></span> 
  

