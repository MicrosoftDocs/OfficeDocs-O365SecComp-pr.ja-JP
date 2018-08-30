---
title: Office 365 でモバイル デバイスの管理を無効にする方法
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- GPA150
- MET150
ms.assetid: 2709cafb-0a8b-44bc-8494-7e2fccfa2b19
description: MDM、Office 365 の組織でのモバイル デバイスに適用されているポリシーを停止するこれらの手順に従います。
ms.openlocfilehash: 6b8f0036ed999b10263f5cc074df27175769e604
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272222"
---
# <a name="how-to-turn-off-mobile-device-management-in-office-365"></a><span data-ttu-id="70b2f-103">Office 365 でモバイル デバイスの管理を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="70b2f-103">How to turn off Mobile Device Management in Office 365</span></span>

<span data-ttu-id="70b2f-104">Office 365 には、MDM を無効に効果的に、(セキュリティ グループによって定義されている) ユーザーのグループ ポリシーから削除、デバイス管理、または、ポリシー自体を削除します。</span><span class="sxs-lookup"><span data-stu-id="70b2f-104">To effectively turn off MDM for Office 365, you remove groups of people (defined by security groups) from the device management policies, or remove the policies themselves.</span></span> 
  
- <span data-ttu-id="70b2f-105">デバイス ポリシーを作成したユーザー セキュリティ グループを削除することによってユーザーのグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="70b2f-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span> 
    
- <span data-ttu-id="70b2f-106">MDM デバイスのすべてのポリシーを削除することによって、すべての MDM を無効にします。</span><span class="sxs-lookup"><span data-stu-id="70b2f-106">Disable MDM for everyone by removing all MDM device policies.</span></span> 
    
<span data-ttu-id="70b2f-p101">これらのオプションは、組織のデバイスの MDM の強制を削除します。残念ながら、ことはできません単に"提供を解除する「MDM Office 365 の設定した後です。</span><span class="sxs-lookup"><span data-stu-id="70b2f-p101">These options will remove MDM enforcement for devices in your organization. Unfortunately, you can't simply "unprovision" MDM for Office 365 after you've set it up.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="70b2f-p102">ポリシーからユーザーのセキュリティ グループを削除または、ポリシー自体を削除する場合は、ユーザーのデバイスへの影響の認識をします。たとえば、プロファイルを電子メールで送信し、デバイスに応じて、キャッシュされた e メールを削除する場合があります。参照してください:[種類の異なるデバイス上のセキュリティ ポリシーの影響とは何ですか?](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)</span><span class="sxs-lookup"><span data-stu-id="70b2f-p102">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves. For example, email profiles and cached emails may be removed, depending on the device. See: [What is the impact of security policies on different device types?](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)</span></span>
  
## <a name="remove-user-security-groups-from-mdm-device-policies"></a><span data-ttu-id="70b2f-112">MDM のデバイス ポリシーからユーザーのセキュリティ グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="70b2f-112">Remove user security groups from MDM device policies</span></span>

1. <span data-ttu-id="70b2f-113">移動**セキュリティ&amp;コンプライアンス センター** \> **データの損失防止** \> **デバイスのセキュリティ ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="70b2f-113">Go to **Security &amp; Compliance Center**\> **Data loss prevention** \> **Device security polices**.</span></span>
    
2. <span data-ttu-id="70b2f-114">デバイス ポリシーを選択しをクリックして![[編集] アイコン](media/O365-MDM-CreatePolicy-EditIcon.gif)**のポリシーを編集**します。</span><span class="sxs-lookup"><span data-stu-id="70b2f-114">Select a device policy, and click ![Edit icon](media/O365-MDM-CreatePolicy-EditIcon.gif) **Edit policy**.</span></span>
    
3. <span data-ttu-id="70b2f-115">**展開**では、[ **- 削除**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70b2f-115">Under **Deployment**, click **- Remove**.</span></span>
    
    <span data-ttu-id="70b2f-116">**グループ**] の下には、セキュリティ グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="70b2f-116">Under **Groups**, select a security group.</span></span>
    
4.  <span data-ttu-id="70b2f-117">**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70b2f-117">Click **Remove**.</span></span>
    
5. <span data-ttu-id="70b2f-118">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70b2f-118">Click **Save**.</span></span>
    
## <a name="remove-mdm-device-policies"></a><span data-ttu-id="70b2f-119">MDM のデバイス ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="70b2f-119">Remove MDM device policies</span></span>

1. <span data-ttu-id="70b2f-120">移動**セキュリティ&amp;コンプライアンス センター** \> **セキュリティ ポリシー** \> **デバイスのセキュリティ ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="70b2f-120">Go to **Security &amp; Compliance Center**\> **Security policies** \> **Device security policies**.</span></span>
    
2. <span data-ttu-id="70b2f-p103">デバイス ポリシーを選択しをクリックし、 ![、ゴミ箱のイメージのアイコンをことができます。](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **ポリシーを削除**します。</span><span class="sxs-lookup"><span data-stu-id="70b2f-p103">Select a device policy, and then click ![Image of the trash can icon.](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **Delete policy**.</span></span>
    
3. <span data-ttu-id="70b2f-123">**警告**ダイアログ ボックスで、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70b2f-123">In the **Warning** dialog, click **Yes**.</span></span> 
    

