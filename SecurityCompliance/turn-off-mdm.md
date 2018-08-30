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
# <a name="how-to-turn-off-mobile-device-management-in-office-365"></a>Office 365 でモバイル デバイスの管理を無効にする方法

Office 365 には、MDM を無効に効果的に、(セキュリティ グループによって定義されている) ユーザーのグループ ポリシーから削除、デバイス管理、または、ポリシー自体を削除します。 
  
- デバイス ポリシーを作成したユーザー セキュリティ グループを削除することによってユーザーのグループを削除します。 
    
- MDM デバイスのすべてのポリシーを削除することによって、すべての MDM を無効にします。 
    
これらのオプションは、組織のデバイスの MDM の強制を削除します。残念ながら、ことはできません単に"提供を解除する「MDM Office 365 の設定した後です。
  
> [!IMPORTANT]
> ポリシーからユーザーのセキュリティ グループを削除または、ポリシー自体を削除する場合は、ユーザーのデバイスへの影響の認識をします。たとえば、プロファイルを電子メールで送信し、デバイスに応じて、キャッシュされた e メールを削除する場合があります。参照してください:[種類の異なるデバイス上のセキュリティ ポリシーの影響とは何ですか?](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)
  
## <a name="remove-user-security-groups-from-mdm-device-policies"></a>MDM のデバイス ポリシーからユーザーのセキュリティ グループを削除します。

1. 移動**セキュリティ&amp;コンプライアンス センター** \> **データの損失防止** \> **デバイスのセキュリティ ポリシー**です。
    
2. デバイス ポリシーを選択しをクリックして![[編集] アイコン](media/O365-MDM-CreatePolicy-EditIcon.gif)**のポリシーを編集**します。
    
3. **展開**では、[ **- 削除**をクリックします。
    
    **グループ**] の下には、セキュリティ グループを選択します。
    
4.  **[削除]** をクリックします。
    
5. **[保存]** をクリックします。
    
## <a name="remove-mdm-device-policies"></a>MDM のデバイス ポリシーを削除します。

1. 移動**セキュリティ&amp;コンプライアンス センター** \> **セキュリティ ポリシー** \> **デバイスのセキュリティ ポリシー**です。
    
2. デバイス ポリシーを選択しをクリックし、 ![、ゴミ箱のイメージのアイコンをことができます。](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **ポリシーを削除**します。
    
3. **警告**ダイアログ ボックスで、[**はい**] をクリックします。 
    

