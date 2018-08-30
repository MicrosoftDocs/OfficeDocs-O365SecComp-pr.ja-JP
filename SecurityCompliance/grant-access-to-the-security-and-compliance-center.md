---
title: ユーザーに Office 365 のセキュリティのアクセス権を与える&amp;コンプライアンス センター
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/18/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: ユーザーが Office 365 のセキュリティのアクセス許可を割り当てる必要があります&amp;コンプライアンス ・ センターのセキュリティやコンプライアンスの機能のいずれかを管理することができます。
ms.openlocfilehash: c612c99f7d72b19d072d728eb4851532d4012414
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013801"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a>ユーザーに Office 365 のセキュリティのアクセス権を与える&amp;コンプライアンス センター

ユーザーが Office 365 のセキュリティのアクセス許可を割り当てる必要があります&amp;コンプライアンス ・ センターのセキュリティやコンプライアンスの機能のいずれかを管理することができます。Office 365 のグローバル管理者またはセキュリティの OrganizationManagement の役割グループのメンバーとして&amp;コンプライアンス センターでは、ユーザーにこれらのアクセス許可を与えることができます。ユーザーのみへのアクセスを許可するセキュリティやコンプライアンスの機能を管理できるようになります。 
  
セキュリティでユーザーに与えることができます別のアクセス許可の詳細については&amp;コンプライアンス センターでは、チェック アウト[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- Office 365 のグローバル管理者、またはセキュリティの OrganizationManagement の役割グループのメンバーである必要があります&amp;コンプライアンス センターは、この資料の手順を完了します。
    
- セキュリティの役割のグループ&amp;コンプライアンス センターでは、Exchange online では、役割グループに似た名前がありますが、同じあります。 
    
- 役割グループのメンバーシップが Exchange Online とセキュリティの間で共有されていない&amp;コンプライアンス センターです。
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a>Office 365 管理センターを使用して、セキュリティを保護する別のユーザーのアクセス権を与える&amp;コンプライアンス センター

1. [管理ページに移動し、Office 365 にサインイン](https://go.microsoft.com/fwlink/p/?LinkId=525275)します。
    
<<<<<<< 見出し
2. Office 365 管理センターをクリックし、[**管理センター**を開く] をクリックし、**セキュリティ&amp;準拠**。 
=======
2. Office 365 管理センターをクリックし、[**管理センター**を開く] をクリックし、**セキュリティ&amp;準拠**。 
>>>>>>> master
    
3. セキュリティ&amp;コンプライアンス センターでは、**アクセス許可**に移動します。
    
4. 役割グループにユーザーを追加し、[**編集**] をクリックするを選択します] ボックスの一覧から![の編集アイコン](media/O365_MDM_CreatePolicy_EditIcon.gif)。
    
5. [**メンバー]** の役割グループのプロパティ ページで [**追加**] をクリックします![アイコンの追加](media/ITPro-EAC-AddIcon.gif)名を選択してユーザー (またはユーザー) を追加したいです。 
    
6. すべての役割グループに追加] をクリックしユーザーを選択した**を追加-\>** し、 **[ok]** をクリックします。
    
7. **[保存]** をクリックして、役割グループに加えた変更を保存します。 
    
### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

1. セキュリティ&amp;コンプライアンス センターでは、**アクセス許可**に移動します。
    
2. リストからメンバーを表示するロール グループを選択します。
    
3. 役割グループの詳細] で、右側の役割グループのメンバーを表示できます。
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a>PowerShell を使用してセキュリティを保護する別のユーザーのアクセス権を与える&amp;コンプライアンス センター

1. [Office 365 のセキュリティへの接続&amp;リモート PowerShell を使用してコンプライアンス センター](https://go.microsoft.com/fwlink/p/?LinkID=627084)です。
    
2. 次の例で示すように、**Add-RoleGroupMember** コマンドを使用して、ユーザーを Organization Management の役割に追加できます。 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 **パラメーター**
  
-  _-Identity_ は、メンバーを追加する役割グループです。 
    
- - _メンバー_は、役割グループに追加するには、メールボックス、ユニバーサル セキュリティ グループ (USG)、またはコンピューターです。一度に 1 つだけメンバーを指定できます。 
    
構文とパラメーターの詳細については、[追加 RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859)を参照してください。
  
### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

与えたユーザーのアクセス セキュリティを保護することを確認するのには&amp;コンプライアンス センターでは、次の例のように、組織の管理役割グループのメンバーを表示するのには**Get RoleGroupMember**コマンドレットを使用します。 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

構文とパラメーターの詳細については、 [Get RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860)を参照してください。
  

