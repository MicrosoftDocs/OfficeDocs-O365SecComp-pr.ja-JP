---
title: Office 365 でモバイル デバイスをワイプします。
ms.author: dianef
author: dianef77
manager: scotv
ms.date: 6/11/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_WipeDevice
- O365E_WipeDevice
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 9d727c7d-8b47-4499-bf24-d046b449214c
description: 組織の情報のみを削除するのに選択的なワイプ、またはモバイル デバイスからすべての情報を削除し、工場出荷時設定に戻すことを完全にクリーン インストールを行うには、Office 365 の組み込みのモバイル デバイス管理を使用できます。
ms.openlocfilehash: d3eb28575924ca3bb4a647ae9af2f96b55116a53
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272502"
---
# <a name="wipe-a-mobile-device-in-office-365"></a><span data-ttu-id="9ab6e-103">Office 365 でモバイル デバイスをワイプします。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-103">Wipe a mobile device in Office 365</span></span>
  
<span data-ttu-id="9ab6e-104">組織の情報のみを削除するのに選択的なワイプ、またはモバイル デバイスからすべての情報を削除し、工場出荷時設定に戻すことを完全にクリーン インストールを行うには、Office 365 の組み込みのモバイル デバイス管理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-104">You can use built-in mobile device management for Office 365 to do a selective wipe to remove only organizational information, or a full wipe to delete all information from a mobile device and restore it to its factory settings.</span></span>
  
## <a name="what-to-know-before-you-begin"></a><span data-ttu-id="9ab6e-105">開始する前に必要な知識</span><span class="sxs-lookup"><span data-stu-id="9ab6e-105">What to know before you begin</span></span>

- <span data-ttu-id="9ab6e-p101">モバイル デバイスでは、組織の機密情報を格納でき、組織の Office 365 リソースへのアクセスを提供することができます。組織の情報を保護するため、全体のクリーン インストールまたは選択のクリーン インストールを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-p101">Mobile devices can store sensitive organizational information and provide access to your organization's Office 365 resources. To help protect your organization's information, you can do a full wipe or a selective wipe:</span></span>
    
  - <span data-ttu-id="9ab6e-p102">**完全なクリーン インストール**: インストール済みのアプリケーション、写真、個人情報など、ユーザーのモバイル デバイス上のすべてのデータを削除します。ワイプが完了すると、デバイスが工場出荷時設定に復元されます。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-p102">**Full wipe**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information. When the wipe is complete, the device is restored to its factory settings.</span></span> 
    
  - <span data-ttu-id="9ab6e-110">**セレクティブ ワイプ**: 組織のデータと葉がインストールされているアプリケーション、写真、およびユーザーのモバイル デバイス上で個人情報のみを削除します。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-110">**Selective wipe**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span> 
    
- <span data-ttu-id="9ab6e-111">デバイスを消去して、完全なクリーン インストール (クリーン インストールのオプションを選択)、デバイスが管理対象デバイスの一覧から削除されます。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-111">When a device is wiped (full wipe or selective wipe), the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="9ab6e-p103">設定できます (完全消去) を自動的に消去するモバイル デバイス管理ポリシーをデバイス デバイスのパスワードを入力すると失敗した後、特定の回数。手順に従って、[を作成するデバイスのセキュリティ ポリシーを展開し、](create-device-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-p103">You can set up a mobile device management policy that automatically wipes (full wipe) a device after the user unsuccessfully tries to enter the device's password a specific number of times. Follow the steps in [Create and deploy device security policies](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="9ab6e-114">ユーザーがそのデバイスを無効にするときに発生を確認する場合を参照してください[ユーザーとデバイスへの影響とは何ですか?](wipe-a-mobile-device.md#BKMK_Impact)です。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-114">If you want to know what a user will experience when you wipe their device, see [What's the user and device impact?](wipe-a-mobile-device.md#BKMK_Impact).</span></span>
    
## <a name="wipe-a-mobile-device"></a><span data-ttu-id="9ab6e-115">モバイル デバイスをワイプします。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="9ab6e-116">[![ここをクリックすると、Office 365 の管理ページに移動します。](media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home)。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-116">Go to the [![Click here to go to the Office 365 admin center.](media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="9ab6e-117">[には、Office 365 のセキュリティ&amp;コンプライアンス センター](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) \> **データ損失の防止** \> **デバイスの管理**です。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-117">Go to [Go to the Office 365 Security &amp; Compliance Center](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)\> **Data loss prevention** \> **Device management**.</span></span>
    
3. <span data-ttu-id="9ab6e-118">消去するデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-118">Select the device you want to wipe.</span></span>
    
4. <span data-ttu-id="9ab6e-119">リモート ワイプを実行するの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-119">Select the type of remote wipe you want to do.</span></span>
    
  - <span data-ttu-id="9ab6e-120">選択のクリーン インストールを行うし、Office 365 組織の情報のみ、右側のペインを削除するには、**選択を消去**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-120">To do a selective wipe and delete only Office 365 organization information, in the right pane, select **Selective wipe**.</span></span>
    
  - <span data-ttu-id="9ab6e-121">全体のクリーン インストールを行うし、工場出荷時の設定、右側のウィンドウでデバイスを復元するには、**完全なクリーン インストール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-121">To do a full wipe and restore the device to its factory settings, in the right pane, select **Full wipe**.</span></span>
    
![デバイスを選択し、クリーン インストールの種類を選択しています。](media/ac940abe-0c4a-404e-a842-a1ad2af13ce3.png)
  
5. <span data-ttu-id="9ab6e-123">**[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-123">Select **Yes** to confirm.</span></span> 
    
<span data-ttu-id="9ab6e-124">ワイプが完了するまで、**デバイスの状態**は、 **RetirePending**または**RetireIssued**として表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-124">Until the wipe finishes, the **Device status** will show as **RetirePending** or **RetireIssued**.</span></span>
  
### <a name="how-do-i-know-it-worked"></a><span data-ttu-id="9ab6e-125">動作方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-125">How do I know it worked?</span></span>

<span data-ttu-id="9ab6e-126">不要になったモバイル デバイスの管理下のデバイスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-126">You'll no longer see the mobile device in the list of managed devices.</span></span>
  
## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="9ab6e-127">なぜ、デバイスをワイプする必要があるのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-127">Why would you want to wipe a device?</span></span>

<span data-ttu-id="9ab6e-128">デバイスをワイプする理由はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-128">There are several reasons for wiping devices:</span></span>
  
- <span data-ttu-id="9ab6e-p104">スマート フォンやタブレットなどのモバイル デバイスになって本格的にします。つまり、ユーザー (個人識別情報や社外秘の通信) などの重要な企業情報を格納し、外出先でアクセスするが簡単です。これらのモバイル デバイスのいずれかが紛失または盗難に遭った、デバイスをすぐに消去を防ぐのに役立ちますが悪人の手で終了することから、組織の情報です。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-p104">Mobile devices like smartphones and tablets are becoming more full-featured all the time. This means it's easier for your users to store sensitive corporate information (such as personal identification or confidential communications) and access it on the go. If one of these mobile devices is lost or stolen, wiping the device immediately can help prevent your organization's information from ending up in the wrong hands.</span></span>
    
- <span data-ttu-id="9ab6e-132">Office 365 の MDM が登録されている個人所有のデバイスで、ユーザーが組織を離れると、選択的なワイプを実行してそのユーザーにすることを組織の情報を防止できます。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-132">When a user leaves the organization with a personal device that is enrolled in MDM for Office 365, you can help prevent organizational information from going with that user by doing a selective wipe.</span></span>
    
- <span data-ttu-id="9ab6e-p105">組織では、ユーザーにモバイル デバイスを提供する場合にデバイスを再割り当てする必要があります。新規ユーザー支援に割り当てる前に、デバイスの完全ワイプを実行により、以前の所有者からのすべての機密情報が削除されます。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-p105">If your organization provides mobile devices to users, you might need to reassign devices from time to time. Doing a full wipe on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>
    
## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="9ab6e-135">ユーザーおよびデバイスへの影響は何か</span><span class="sxs-lookup"><span data-stu-id="9ab6e-135">What's the user and device impact?</span></span>

<span data-ttu-id="9ab6e-p106">ワイプは、モバイル デバイスに直ちに送信されます。デバイスは、AAD に準拠していないにもマークされます。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-p106">The wipe is sent immediately to the mobile device. The device is also marked as not compliant in AAD.</span></span>
  
<span data-ttu-id="9ab6e-138">次の表は、どのような内容は各デバイス タイプのデバイスが選択的に消去されている場合について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-138">The following table describes what content is removed for each device type when a device is selectively wiped.</span></span>
  
|<span data-ttu-id="9ab6e-139">**コンテンツへの影響**</span><span class="sxs-lookup"><span data-stu-id="9ab6e-139">**Content impact**</span></span>|<span data-ttu-id="9ab6e-140">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="9ab6e-140">**Windows Phone 8.1**</span></span>|<span data-ttu-id="9ab6e-141">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="9ab6e-141">**iOS 7.1+**</span></span>|<span data-ttu-id="9ab6e-142">**Android 4 以降**</span><span class="sxs-lookup"><span data-stu-id="9ab6e-142">**Android 4+**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9ab6e-143">企業ポータル アプリケーション\*をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-143">Company Portal app\* is uninstalled.</span></span>  <br/> |<span data-ttu-id="9ab6e-144">該当なし</span><span class="sxs-lookup"><span data-stu-id="9ab6e-144">N/A</span></span>  <br/> |<span data-ttu-id="9ab6e-145">✔</span><span class="sxs-lookup"><span data-stu-id="9ab6e-145">✔</span></span>  <br/> |<span data-ttu-id="9ab6e-146">該当なし</span><span class="sxs-lookup"><span data-stu-id="9ab6e-146">N/A</span></span>  <br/> |
|<span data-ttu-id="9ab6e-p107">MDM で Office 365 にアクセス制御がサポートされるアプリケーションによってホストされるアプリのデータを office 365 は、削除された (現在の Outlook とビジネスの OneDrive) です。アプリケーションは削除されません。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-p107">Office 365 app data hosted by apps where access control is supported by MDM for Office 365 is removed (currently Outlook and OneDrive for Business). The apps are not removed.</span></span>  <br/> <span data-ttu-id="9ab6e-149">Android は、outlook では、キャッシュされたメールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-149">Outlook for Android does not remove cached emails.</span></span>  <br/> |<span data-ttu-id="9ab6e-150">✔</span><span class="sxs-lookup"><span data-stu-id="9ab6e-150">✔</span></span>  <br/> |<span data-ttu-id="9ab6e-151">✔</span><span class="sxs-lookup"><span data-stu-id="9ab6e-151">✔</span></span>  <br/> |<span data-ttu-id="9ab6e-152">✔</span><span class="sxs-lookup"><span data-stu-id="9ab6e-152">✔</span></span>  <br/> |
|<span data-ttu-id="9ab6e-153">デバイスにデバイスを Office 365 の MDM によって適用されたポリシー設定が適用されて不要になったと、ユーザーが設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-153">Policy settings that were applied by MDM for Office 365 to devices are no longer enforced on the device and users can change the settings.</span></span>  <br/> |<span data-ttu-id="9ab6e-154">✔</span><span class="sxs-lookup"><span data-stu-id="9ab6e-154">✔</span></span>  <br/> |<span data-ttu-id="9ab6e-155">✔</span><span class="sxs-lookup"><span data-stu-id="9ab6e-155">✔</span></span>  <br/> |<span data-ttu-id="9ab6e-156">✔</span><span class="sxs-lookup"><span data-stu-id="9ab6e-156">✔</span></span>  <br/> |
|<span data-ttu-id="9ab6e-157">Office 365 の MDM によって作成された電子メール プロファイルが削除され、デバイス上のキャッシュされた電子メールが削除されます。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-157">Email profiles created by MDM for Office 365 are removed and cached email on the device is deleted.</span></span>  <br/> |<span data-ttu-id="9ab6e-158">該当なし</span><span class="sxs-lookup"><span data-stu-id="9ab6e-158">N/A</span></span>  <br/> |<span data-ttu-id="9ab6e-159">✔</span><span class="sxs-lookup"><span data-stu-id="9ab6e-159">✔</span></span>  <br/> |<span data-ttu-id="9ab6e-160">該当なし</span><span class="sxs-lookup"><span data-stu-id="9ab6e-160">N/A</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="9ab6e-161">\*企業ポータル アプリケーションは、iOS のアプリケーション ストアと Android デバイスの再生ストアであります。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-161">\* Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="9ab6e-162">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="9ab6e-162">Related content</span></span>

[<span data-ttu-id="9ab6e-163">Office 365 でモバイル デバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="9ab6e-163">Manage mobile devices in Office 365</span></span>](set-up-mobile-device-management.md)
  

