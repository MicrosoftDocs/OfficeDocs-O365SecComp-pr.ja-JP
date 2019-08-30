---
title: EOP でグループを管理する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: Exchange Online Protection (EOP) を使用すれば、Exchange 組織のメールが有効なグループを作成できます。 また、EOP を使用してメンバーシップ、電子メール アドレス、グループのその他の側面を指定するグループのプロパティを定義または更新することもできます。
ms.openlocfilehash: 9ce501c5d51561a7be86963ae98b62046995e46f
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676737"
---
# <a name="manage-groups-in-eop"></a>EOP でグループを管理する

 Exchange Online Protection (EOP) を使用すれば、Exchange 組織のメールが有効なグループを作成できます。また、EOP を使用してメンバーシップ、電子メール アドレス、グループのその他の側面を指定するグループのプロパティを定義または更新することもできます。必要に応じて配布グループとセキュリティ グループを作成できます。これらのグループは、Exchange 管理センター (EAC) を使用するか、リモートの Windows PowerShell を介して作成できます。
  
## <a name="types-of-mail-enabled-groups"></a>メールが有効なグループの種類

Exchange 組織では、2 種類のグループを作成できます。
  
- 配布グループは、チームやその他の臨時のグループなど、一般的な興味分野に関するメールを受信または送信する必要がある電子メールユーザーのコレクションです。 配布グループは電子メール メッセージの配布専用です。 EOP では、配布グループは、セキュリティに関連するかどうかにかかわらず、すべてのメールが有効なグループを意味します。

- セキュリティグループは、管理者ロールのアクセス許可を必要とする電子メールユーザーのコレクションです。 たとえば、特定のユーザー グループに管理者役割アクセス許可を付与して、スパム対策設定とマルウェア対策設定を構成できるようにする場合があります。

    > [!NOTE]
    > 既定では、メールが有効なすべての新しいセキュリティ グループで、すべての送信者を認証する必要があります。これにより、外部の送信者はメールが有効なセキュリティ グループに対してメッセージを送信できなくなります。
  
## <a name="before-you-begin"></a>開始する前に

- この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「配布グループとセキュリティ グループ」。

- Exchange 管理センターを開くには、「exchange [Online Protection の exchange 管理センター](../exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。

- Exchange Online Protection の PowerShell コマンドレットを使用してグループを作成および管理する場合は、調整が発生する可能性があることに注意してください。

- このトピックの PowerShell の手順では、コマンドの結果が表示されるまでに数分の遅延が発生するバッチ処理方式を使用しています。

- Windows PowerShell を使って Exchange Online Protection に接続する方法については、「[Exchange Online Protection の PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)」を参照してください。

- このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。

> [!TIP]
> 問題がある場合は、 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラムでヘルプを要求します。 
  
## <a name="create-a-group-in-the-eac"></a>EAC でグループを作成する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。

2. 必要**** ![に応じて](../media/ITPro-EAC-AddIcon.gif)、[新規追加] アイコンをクリックし、[**配布グループ**] または [**セキュリティグループ**] をクリックします。

3. [**新しい配布グループ**] ページまたは [**新しいセキュリティグループ**] ページで、次の設定を構成します。

   - [**表示名**]: 組織に固有で、EOP ユーザーにとって意味のある表示名を入力します。 表示名は必須です。

   - **エイリアス**: 組織に固有の最大64文字のグループエイリアスを入力します。 EOP ユーザーが電子メール メッセージの宛先行にエイリアスを入力すると、グループの表示名に解読されます。 エイリアスを変更すると、グループのプライマリ SMTP アドレスも変更され、新しいエイリアスが追加されます。 エイリアスは必須です。 

   - [**説明**]: グループの説明を入力します。これにより、ユーザーはグループの目的を知ることができます。 

   - **所有者**: 既定では、グループを作成したユーザーが所有者になります。 所有者を追加するには、 **** ![[追加]](../media/ITPro-EAC-AddIcon.gif)[追加] アイコンを選択します。 グループには、最低 1 人の所有者が必要です。

     > [!NOTE]
     > 所有者はグループのメンバーである必要はありません。
  
   - **メンバー**: グループメンバーを追加し、グループに参加または脱退するために承認が必要かどうかを指定するには、このセクションを使用します。 グループにメンバーを追加するには**** ![、[追加](../media/ITPro-EAC-AddIcon.gif)] アイコンをクリックします。

4. **[OK]** をクリックして元のページに戻ります。

5. 完了したら、 **[保存]** をクリックしてグループを作成します。新しいグループがグループの一覧に表示されます。

## <a name="edit-or-remove-a-group-in-the-eac"></a>EAC でグループを編集または削除する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。

2. 次のいずれかの手順を実行します。

   - グループを編集するには、グループの一覧で、表示または変更するグループをクリックし、[編集アイコン**** ![](../media/ITPro-EAC-EditIcon.gif)の編集] をクリックします。 全般設定の更新、グループの所有者の追加または削除、および必要に応じてグループメンバーの追加または削除を行うことができます。

   - グループを削除するには、グループを選択**** ![し、[](../media/ITPro-EAC-RemoveIcon.gif)削除] [削除] アイコンをクリックします。

3. 変更が完了したら、 **[保存]** をクリックします。

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>リモートの Windows PowerShell を使用してグループを作成、編集、または削除する

このセクションでは、グループを作成し、Exchange Online Protection の PowerShell でそのプロパティを変更する方法について説明します。 また、既存のグループを削除する方法も説明します。
  
### <a name="create-a-group-using-remote-windows-powershell"></a>リモートの Windows PowerShell を使用してグループを作成する
  
この例では、コマンドレット [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) を使用して、エイリアスが「itadmin」、名前が「IT Administrators」の配布グループを作成します。また、ユーザーをグループのメンバーとして追加します。
  
```Powershell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

**注**: 配布グループではなくセキュリティグループを作成するには、 `Security` *Type*パラメーターの値を使用します。
  
IT 管理者グループが正常に作成されたことを確認するには、次のコマンドを実行して、新しいグループに関する情報を表示します。
  
```Powershell
Get-Recipient "IT Administrators" | Format-List
```

構文およびパラメーターの詳細については、「 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient)」を参照してください。

グループ内のメンバーの一覧を取得するには、次のコマンドを実行します。
  
```Powershell
Get-DistributionGroupMember "IT Administrators"
```

構文およびパラメーターの詳細については、「 [get-distributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember)」を参照してください。

すべてのグループの完全な一覧を取得するには、次のコマンドを実行します。
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a>リモート Windows PowerShell を使用してグループのプロパティを変更する
  
EAC の代わりに PowerShell を使用する利点は、複数のグループのプロパティを変更できることです。
  
Exchange Online Protection PowerShell を使用してグループのプロパティを変更する例を次に示します。
  
この例では、シアトルの従業員グループのプライマリ SMTP アドレス (返信アドレスとも呼ばれます) を sea.employees@contoso.com に変更します。
  
```Powershell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

構文およびパラメーターの詳細については、「 [Set-Eop/グループ](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup)」を参照してください。

グループのプロパティが正常に変更されたことを確認するには、次のコマンドを実行して新しい値を確認します。
  
```Powershell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

この例では、シアトルの従業員グループのすべてのメンバーを更新します。 全メンバーをコンマを使用して区切ります。
  
```Powershell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

構文およびパラメーターの詳細については、「 [update-eopdistributiongroupmember](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember)」を参照してください。

シアトルの従業員グループのすべてのメンバーの一覧を取得するには、次のコマンドを実行します。 
  
```Powershell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a>リモートの Windows PowerShell を使用してグループを削除する
  
この例では、IT 管理者という名前の配布グループを削除します。
  
```Powershell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

構文およびパラメーターの詳細については、「[削除-Eop/グループ](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup)」を参照してください。

グループが削除されたことを確認するには、次のコマンドを実行し、グループ (この場合は「It Administrators」) が削除されたことを確認します。
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
