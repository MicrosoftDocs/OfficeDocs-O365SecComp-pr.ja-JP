---
title: Office 365 セキュリティ&amp;コンプライアンスセンターへのアクセス権をユーザーに付与する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: ユーザーは、セキュリティまたはコンプライアンス機能を管理する&amp;前に、Office 365 セキュリティコンプライアンスセンターでアクセス許可を割り当てる必要があります。
ms.openlocfilehash: 08b3781ceb48b9a8d5933a075106d7bd3b9ab17d
ms.sourcegitcommit: 799a958fcac643f62dfac6fa04020f2f4758635c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30997239"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a>Office 365 セキュリティ&amp;コンプライアンスセンターへのアクセス権をユーザーに付与する

ユーザーは、セキュリティまたはコンプライアンス機能を管理する&amp;前に、Office 365 セキュリティコンプライアンスセンターでアクセス許可を割り当てる必要があります。 セキュリティ&amp; /コンプライアンスセンターでは、Office 365 のグローバル管理者または組織の管理役割グループのメンバーとして、これらのアクセス許可をユーザーに与えることができます。 ユーザーが管理できるのは、アクセス権が付与されたセキュリティまたはコンプライアンスの機能のみです。 
  
セキュリティ/コンプライアンスセンターでユーザーに付与できるさまざまなアクセス許可の詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターでアクセス許可](permissions-in-the-security-and-compliance-center.md)を確認する」を参照してください。 &amp;
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- この記事に記載されている手順を完了するには、Office 365 グローバル管理者である&amp;か、または、セキュリティコンプライアンスセンターの組織管理役割グループのメンバーである必要があります。
    
- セキュリティ&amp; /コンプライアンスセンターの役割グループの名前は Exchange Online の役割グループと似ている場合がありますが、同じではありません。 
    
- 役割グループのメンバーシップは、Exchange Online とセキュリティ&amp;センターコンプライアンスセンターとの間で共有されません。
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a>Office 365 管理センターを使用して、別のユーザーにセキュリティ&amp;コンプライアンスセンターへのアクセス権を付与する

1. [Office 365 にサインインし、管理センターに移動し](https://go.microsoft.com/fwlink/p/?LinkId=525275)ます。
    
2. Office 365 管理センターで、**管理センター**を開き、[**セキュリティ&amp;のコンプライアンス**] をクリックします。 
    
3. セキュリティ&amp; /コンプライアンスセンターで、[**アクセス許可**] に移動します。
    
4. リストからユーザーを追加する役割グループを選択し、[編集] [ **** ![編集] アイコン](media/O365_MDM_CreatePolicy_EditIcon.gif)をクリックします。
    
5. 役割グループのプロパティページの [**メンバー**] で、 ****![[追加]](media/ITPro-EAC-AddIcon.gif)アイコンをクリックし、追加するユーザーの名前を選択します。 
    
6. 役割グループに追加するすべてのユーザーを選択したら、[ **\>追加**] をクリックし、[ **OK]** をクリックします。
    
7. **[保存]** をクリックして、役割グループに加えた変更を保存します。 
    
### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

1. セキュリティ&amp; /コンプライアンスセンターで、[**アクセス許可**] に移動します。
    
2. リストから、メンバーを表示する役割グループを選択します。
    
3. 右側の役割グループの詳細では、役割グループのメンバーを表示できます。
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a>PowerShell を使用して、セキュリティ&amp; /コンプライアンスセンターへのアクセス権を別のユーザーに付与する

1. [Office 365 Security & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)します。
    
2. 次の例で示すように、**Add-RoleGroupMember** コマンドを使用して、ユーザーを Organization Management の役割に追加できます。 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 **パラメーター**
  
- _-Identity_ は、メンバーを追加する役割グループです。 
    
- _Member_は、役割グループに追加するメールボックス、ユニバーサルセキュリティグループ (USG)、またはコンピューターです。 一度に 1 メンバーしか指定できません。 
    
構文とパラメーターの詳細については、「 [add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510859)」を参照してください。
  
### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

ユーザーにセキュリティ&amp;コンプライアンスセンターへのアクセス権が与えられたことを確認するには、次の例に示すように、 **add-rolegroupmember**コマンドレットを使用して組織の管理役割グループのメンバーを表示します。 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

構文とパラメーターの詳細については、「 [add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510860)」を参照してください。
  

