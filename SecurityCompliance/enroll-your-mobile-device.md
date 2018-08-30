---
title: Office 365 でモバイル デバイスを登録します。
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/25/2018
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: c8ac722d-dcaf-4135-8345-3e6327f5d3c5
description: Office 365 サービスを使用するには、デバイスに、前に、Office 365 (MDM) のモバイル デバイスの管理で登録する手順に従う必要があります。作業内容を追加するか、デバイスに最初に電子メール アカウントを学校の場合に実行します。
ms.openlocfilehash: 63e4052d42007d97928f158a704beb9721758a44
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272302"
---
# <a name="enroll-your-mobile-device-in-office-365"></a><span data-ttu-id="cccad-104">Office 365 でモバイル デバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="cccad-104">Enroll your mobile device in Office 365</span></span>

<span data-ttu-id="cccad-p102">維持するための優れた方法が必要な情報し、オフィスから離れているときに、ビジネス プロジェクトを操作するには作業を自分の携帯電話、タブレット、およびその他のモバイル デバイスを使用しています。Office 365 サービスを使用するには、デバイスに、前に、最初に登録する、モバイル デバイス管理の Office 365 (MDM) Microsoft Intune 企業ポータルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cccad-p102">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you're away from the office. Before you can use Office 365 services with your device, you may need to first enroll it in Mobile Device Management for Office 365 (MDM) using Microsoft Intune Company Portal.</span></span>
  
<span data-ttu-id="cccad-p103">組織は、ビジネスが重要なデータをセキュリティで保護し、コンプライアンス要件を満たしているときに、仕事の電子メール、予定表、およびドキュメントを安全にアクセスする従業員が自分のモバイル デバイスを使用できるように、MDM を選択します。[MDM では、Office 365 について学習](https://go.microsoft.com/fwlink/?LinkId=615142)します。</span><span class="sxs-lookup"><span data-stu-id="cccad-p103">Organizations choose MDM so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements. [Learn about MDM in Office 365](https://go.microsoft.com/fwlink/?LinkId=615142).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cccad-p104">MDM のデバイスを Office 365 に登録するときにデバイスをワイプするには、社内のオプションを許可すると、パスワードを設定する必要可能性があります。デバイス ワイプを実行できます (Office 365 の管理者センター) から、たとえば、パスワードの入力を間違えた回数が多すぎる場合、または使用条件が破損している場合、デバイスからすべてのデータを削除するのには。</span><span class="sxs-lookup"><span data-stu-id="cccad-p104">When you enroll your device in MDM for Office 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device. A device wipe can be performed (from the Office 365 admin center), for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span> 
  
 <span data-ttu-id="cccad-111">**サポート対象のデバイス**</span><span class="sxs-lookup"><span data-stu-id="cccad-111">**Supported devices**</span></span>
  
<span data-ttu-id="cccad-p105">MDM と InTune は、すべてではなく、ほとんどのモバイル デバイスで動作します。次は MDM を Office 365 の。</span><span class="sxs-lookup"><span data-stu-id="cccad-p105">MDM and InTune works with most, but not all, mobile devices. The following are supported with MDM for Office 365.</span></span>
  
- <span data-ttu-id="cccad-114">iOS 7.1 以降</span><span class="sxs-lookup"><span data-stu-id="cccad-114">iOS 7.1 or later</span></span>
    
- <span data-ttu-id="cccad-115">4 またはそれ以降のアプリ</span><span class="sxs-lookup"><span data-stu-id="cccad-115">Android 4 or later</span></span>
    
- <span data-ttu-id="cccad-116">Windows 8.1 の (電話と PC) し、Windows の 10 を追加するには、後で</span><span class="sxs-lookup"><span data-stu-id="cccad-116">Windows 8.1 (Phone and PC) and later to include Windows 10</span></span>
    
- <span data-ttu-id="cccad-117">Windows 10</span><span class="sxs-lookup"><span data-stu-id="cccad-117">Windows 10</span></span>
    
<span data-ttu-id="cccad-118">デバイスが表示されていないと、MDM と Intune を使用する必要があります、職場または学校管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="cccad-118">If your device is not listed above, and you need to use it with MDM and Intune, contact your work or school administrator.</span></span>
  
> [!TIP]
> <span data-ttu-id="cccad-119">、デバイスの登録に問題が発生した場合を参照してください: [Office 365 の MDM のデバイス登録をトラブルシューティング](troubleshoot-mdm.md)します。</span><span class="sxs-lookup"><span data-stu-id="cccad-119">If you're having trouble enrolling your device, see: [Troubleshoot device enrollment with MDM for Office 365](troubleshoot-mdm.md).</span></span> 
  
## <a name="set-up-your-mobile-device-with-intune-and-mdm-for-office-365"></a><span data-ttu-id="cccad-120">Office 365 の Intune MDM とモバイル デバイスのセットアップします。</span><span class="sxs-lookup"><span data-stu-id="cccad-120">Set up your mobile device with Intune and MDM for Office 365</span></span>

<span data-ttu-id="cccad-121">Intune 企業ポータルにより、Office 365 と MDM. によって管理されるデバイス</span><span class="sxs-lookup"><span data-stu-id="cccad-121">The Intune Company Portal enables a device to be managed by Office 365 and MDM.</span></span>
  
### <a name="iphone-or-ipad"></a><span data-ttu-id="cccad-122">iPhone または iPad</span><span class="sxs-lookup"><span data-stu-id="cccad-122">iPhone or iPad</span></span>

> [!TIP]
> <span data-ttu-id="cccad-123">この手順を完了するまで、電子メールを送受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="cccad-123">You won't be able to send and receive email until you complete this step.</span></span> 
  
> <span data-ttu-id="cccad-124">Apple のアプリケーション ストアにダウンロードおよび Intune 会社のポータルのインストールを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cccad-124">Go to the Apple App Store, download and install Intune Company Portal.</span></span>
    
> <span data-ttu-id="cccad-125">の[構成および接続する次の手順に従って](https://go.microsoft.com/fwlink/?linkid=875316)iOS の携帯電話または会社 Office 365 ポータルでのタブレット。</span><span class="sxs-lookup"><span data-stu-id="cccad-125">[Follow these steps to configure and connect](https://go.microsoft.com/fwlink/?linkid=875316) your iOS phone or tablet with the Company portal to Office 365.</span></span> 
    
### <a name="android-phone-or-tablet"></a><span data-ttu-id="cccad-126">Android の携帯電話やタブレット</span><span class="sxs-lookup"><span data-stu-id="cccad-126">Android phone or tablet</span></span>

> [!TIP]
> <span data-ttu-id="cccad-127">この手順を完了するまで、電子メールを送受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="cccad-127">You won't be able to send and receive email until you complete this step.</span></span> 
  
> <span data-ttu-id="cccad-128">Google プレイ ストアにダウンロードし、Intune 会社のポータルのインストールを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cccad-128">Go to the Google Play store, download and install Intune Company Portal.</span></span>
    
> <span data-ttu-id="cccad-129">Android の電話は、[以下の手順を構成し、接続](https://go.microsoft.com/fwlink/?linkid=875317)または Office 365 に企業ポータルとタブレット。</span><span class="sxs-lookup"><span data-stu-id="cccad-129">[Follow these steps to configure and connect](https://go.microsoft.com/fwlink/?linkid=875317) your Android phone or tablet with the Company portal to Office 365.</span></span> 
    
## <a name="whats-next"></a><span data-ttu-id="cccad-130">次は何</span><span class="sxs-lookup"><span data-stu-id="cccad-130">What's next</span></span>

<span data-ttu-id="cccad-131">デバイスを Office 365 の MDM に登録すると、電子メール、予定表、連絡先、およびドキュメントを操作するデバイス上の Office アプリケーションを使用してを開始できます。</span><span class="sxs-lookup"><span data-stu-id="cccad-131">After your device is enrolled in MDM for Office 365, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
  

