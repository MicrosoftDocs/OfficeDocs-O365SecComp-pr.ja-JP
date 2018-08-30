---
title: Office 365 の MDM のデバイスの登録のトラブルシューティングを行う
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/17/2015
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: c863b2bf-45f3-483a-ba05-29fc7f4d6434
description: Office 365 のデバイスでモバイル デバイス管理 (MDM) を登録しようとするときの問題に実行している場合、は、以下の手順に従って問題を追跡するためをしてください。一般的な手順で問題が解決しない場合、デバイス ・ タイプの特定の手順を実行後のセクションのいずれかを参照してください。
ms.openlocfilehash: 490259fc623b38ab5ad6cf8553c5074c77b77426
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272112"
---
# <a name="troubleshoot-device-enrollment-with-mdm-for-office-365"></a><span data-ttu-id="a28fb-104">Office 365 の MDM のデバイスの登録のトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="a28fb-104">Troubleshoot device enrollment with MDM for Office 365</span></span>

<span data-ttu-id="a28fb-p102">Office 365 のデバイスでモバイル デバイス管理 (MDM) を登録しようとするときの問題に実行している場合、は、以下の手順に従って問題を追跡するためをしてください。一般的な手順で問題が解決しない場合、デバイス ・ タイプの特定の手順を実行後のセクションのいずれかを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a28fb-p102">If you're running into issues when you try to enroll a device in Mobile Device Management (MDM) for Office 365, try the steps listed here to track down the problem. If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>
  
## <a name="steps-to-try-first"></a><span data-ttu-id="a28fb-107">最初に手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a28fb-107">Steps to try first</span></span>

<span data-ttu-id="a28fb-108">開始するには、次の手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="a28fb-108">To start, check the following:</span></span>
  
- <span data-ttu-id="a28fb-109">そのデバイスは既に登録していない Intune など、他のモバイル デバイス管理プロバイダーに確認します。</span><span class="sxs-lookup"><span data-stu-id="a28fb-109">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>
    
- <span data-ttu-id="a28fb-110">デバイスが、正しい日付と時刻に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a28fb-110">Make sure that the device is set to the correct date and time.</span></span>
    
- <span data-ttu-id="a28fb-111">別の Wi-fi または携帯電話のネットワーク デバイス上に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="a28fb-111">Switch to a different Wi-Fi or cellular network on the device.</span></span>
    
- <span data-ttu-id="a28fb-112">Android や iOS デバイスでは、アンインストールし、Intune 会社のポータル アプリケーションを再インストール、デバイスにします。</span><span class="sxs-lookup"><span data-stu-id="a28fb-112">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span>
    
## <a name="ios-phone-or-tablet"></a><span data-ttu-id="a28fb-113">iOS の携帯電話やタブレット</span><span class="sxs-lookup"><span data-stu-id="a28fb-113">iOS phone or tablet</span></span>

- <span data-ttu-id="a28fb-114">[Apn の証明書を設定](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7)したりしたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a28fb-114">Make sure that you've [set up an APNs certificate](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7).</span></span>
    
- <span data-ttu-id="a28fb-p103">**設定**で\>**一般的な** \> **プロファイル**(または**デバイスの管理**) では、**管理プロファイル**が既にインストールされていないことを確認します。場合は、それを削除します。</span><span class="sxs-lookup"><span data-stu-id="a28fb-p103">In **Settings** \> **General** \> **Profile** (or **Device Management**), make sure that a **Management Profile** is not already installed. If it is, remove it.</span></span> 
    
- <span data-ttu-id="a28fb-117">「に登録して、デバイスが失敗しました」エラー メッセージが表示される場合は、Office 365 にサインインし、デバイスにサインインしたユーザーを含む Exchange Online ライセンスが割り当てられているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a28fb-117">If you see the error message, "Device failed to enroll," sign in to Office 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="a28fb-118">「プロファイルをインストールするに失敗しました」エラー メッセージが表示される場合は、次のいずれかを試してください。</span><span class="sxs-lookup"><span data-stu-id="a28fb-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>
    
  - <span data-ttu-id="a28fb-119">Safari が、デバイスの既定のブラウザーであること、および cookie が無効になっていないことを確認ください。</span><span class="sxs-lookup"><span data-stu-id="a28fb-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>
    
  - <span data-ttu-id="a28fb-120">、デバイスを再起動し、portal.manage.microsoft.com に移動、Office 365 のユーザー ID とパスワードでサインイン、プロファイルを手動でインストールしようとしてください。</span><span class="sxs-lookup"><span data-stu-id="a28fb-120">Reboot the device, then navigate to portal.manage.microsoft.com, sign in with your Office 365 user ID and password, and attempt to install the profile manually.</span></span>
    
## <a name="windows-rt-tablet"></a><span data-ttu-id="a28fb-121">Windows RT タブレット</span><span class="sxs-lookup"><span data-stu-id="a28fb-121">Windows RT tablet</span></span>

- <span data-ttu-id="a28fb-122">ドメインには、 [MDM を使用する Office 365 のセットアップ](set-up-mobile-device-management.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="a28fb-122">Make sure that your domain is [set up in Office 365 to work with MDM](set-up-mobile-device-management.md).</span></span>
    
- <span data-ttu-id="a28fb-123">**オンにする**を選択することがなく、ユーザー**への参加**を選択するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="a28fb-123">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>
    
## <a name="windows-phone"></a><span data-ttu-id="a28fb-124">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="a28fb-124">Windows Phone</span></span>

- <span data-ttu-id="a28fb-125">ドメインには、 [MDM を使用する Office 365 のセットアップ](set-up-mobile-device-management.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="a28fb-125">Make sure that your domain is [set up in Office 365 to work with MDM](set-up-mobile-device-management.md).</span></span>
    
- <span data-ttu-id="a28fb-126">デバイスで Windows 8.1 以降を実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a28fb-126">Make sure the device is running Windows 8.1 or later.</span></span>
    
## <a name="android-phone-or-tablet"></a><span data-ttu-id="a28fb-127">Android の携帯電話やタブレット</span><span class="sxs-lookup"><span data-stu-id="a28fb-127">Android phone or tablet</span></span>

- <span data-ttu-id="a28fb-128">4.0 またはそれ以降、デバイスは Android を実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a28fb-128">Make sure the device is running Android 4.0 or later.</span></span>
    
- <span data-ttu-id="a28fb-129">「このデバイスでは、私たち登録できませんでした」エラー メッセージが表示される場合は、Office 365 にサインインし、、デバイスにサインインしたユーザーを含む Exchange Online ライセンスが割り当てられているどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a28fb-129">If you see the error message, "We couldn't enroll this device," sign in to Office 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="a28fb-130">必要なエンドユーザー操作が保留中、かどうかをデバイスに**通知領域**を確認し、場合は、操作を完了します。</span><span class="sxs-lookup"><span data-stu-id="a28fb-130">Check the **Notification Area** on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span> 
    

