---
title: ユーザーに Office 365 セキュリティ センターとコンプライアンス センターへのアクセス権を付与する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
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
description: ユーザーがセキュリティまたはコンプライアンス機能を管理する前に、Office 365 セキュリティ & コンプライアンスセンターでアクセス許可を割り当てる必要があります。
ms.openlocfilehash: 7963a8c3db64e83566960abe9298b9a2d636ae53
ms.sourcegitcommit: 6302a43d947a908dd10a8e40550b806f491692fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2019
ms.locfileid: "35645122"
---
# <a name="give-users-access-to-the-office-365-security--compliance-center"></a>ユーザーに Office 365 セキュリティ センターとコンプライアンス センターへのアクセス権を付与する

ユーザーがセキュリティまたはコンプライアンス機能を管理する前に、Office 365 セキュリティ & コンプライアンスセンターでアクセス許可を割り当てる必要があります。 セキュリティ & コンプライアンスセンターで、Office 365 グローバル管理者または組織の組織の管理役割グループのメンバーとして、これらのアクセス許可をユーザーに与えることができます。 ユーザーが管理できるのは、アクセス権が付与されたセキュリティまたはコンプライアンスの機能のみです。 
  
セキュリティ & コンプライアンスセンターでユーザーに付与できるさまざまなアクセス許可の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>事前に必要な知識

- この記事に記載されている手順を完了するには、Office 365 グローバル管理者であるか、またはセキュリティ & コンプライアンスセンターの組織の組織の管理役割グループのメンバーである必要があります。

- セキュリティ & コンプライアンスセンターの役割グループには、Exchange Online の役割グループと同じような名前が付いている場合がありますが、これらは同じではありません。

- 役割グループのメンバーシップは、Exchange Online とセキュリティ & コンプライアンスセンターとの間で共有されません。

- (AOBO) 権限を持つ代理アクセス許可 (DAP) パートナーは、セキュリティ & コンプライアンスセンターにアクセスできません。

## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>Office 365 管理センターを使用して、別のユーザーにセキュリティ & コンプライアンスセンターへのアクセス権を付与する

1. [Office 365 にサインインし、管理センターに移動し](https://go.microsoft.com/fwlink/p/?LinkId=525275)ます。

2. Office 365 管理センターで、**管理センター**を開き、[**セキュリティ & コンプライアンス**] をクリックします。

3. [セキュリティ & コンプライアンスセンター] で、[**アクセス許可**] に移動します。

4. リストからユーザーを追加する役割グループを選択し、[編集] [ **** ![編集] アイコン](media/O365-MDM-CreatePolicy-EditIcon.gif)をクリックします。

5. 役割グループのプロパティページの [**メンバー**] で、 ****![[追加]](media/ITPro-EAC-AddIcon.gif)アイコンをクリックし、追加するユーザーの名前を選択します。

6. 役割グループに追加するすべてのユーザーを選択したら、[ **\>追加**] をクリックし、[ **OK]** をクリックします。

7. **[保存]** をクリックして、役割グループに加えた変更を保存します。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

1. [セキュリティ & コンプライアンスセンター] で、[**アクセス許可**] に移動します。

2. リストから、メンバーを表示する役割グループを選択します。

3. 右側の役割グループの詳細では、役割グループのメンバーを表示できます。

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>PowerShell を使用して、別のユーザーにセキュリティ & コンプライアンスセンターへのアクセス権を付与する

1. [Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)します。

2. 次の例で示すように、**Add-RoleGroupMember** コマンドを使用して、ユーザーを Organization Management の役割に追加できます。

   ```
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **パラメーター**:
  
   - _Identity_は、メンバーを追加する役割グループです。

   - _Member_は、役割グループに追加するメールボックス、ユニバーサルセキュリティグループ (USG)、またはコンピューターです。 一度に 1 メンバーしか指定できません。

構文とパラメーターの詳細については、「 [add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510859)」を参照してください。
  
### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

ユーザーにセキュリティ & コンプライアンスセンターへのアクセス権が与えられたことを確認するには、次の例に示すように、 **add-rolegroupmember**コマンドレットを使用して組織の管理役割グループのメンバーを表示します。
  
```
Get-RoleGroupMember -Identity "Organization Management"
```

構文とパラメーターの詳細については、「 [add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510860)」を参照してください。
