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
ms.openlocfilehash: 2763ca35456bb40b5b11e38eb2e7497934115d5f
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599643"
---
# <a name="manage-groups-in-eop"></a>EOP でグループを管理する

 Exchange Online Protection (EOP) を使用すれば、Exchange 組織のメールが有効なグループを作成できます。また、EOP を使用してメンバーシップ、電子メール アドレス、グループのその他の側面を指定するグループのプロパティを定義または更新することもできます。必要に応じて配布グループとセキュリティ グループを作成できます。これらのグループは、Exchange 管理センター (EAC) を使用するか、リモートの Windows PowerShell を介して作成できます。 
  
## <a name="types-of-mail-enabled-groups"></a>メールが有効なグループの種類

Exchange 組織では、2 種類のグループを作成できます。
  
- [EAC でグループを作成する](manage-groups-in-eop.md) ( 配布グループとも言う) は、共通の関心領域に関する電子メールを送受信する必要のあるチームやその他の専門グループなどの電子メール ユーザーの集まりです。配布グループは電子メール メッセージの配布専用です。EOP では、配布グループは、セキュリティに関連するかどうかにかかわらず、すべてのメールが有効なグループを意味します。
    
- [EAC でグループを編集または削除する](manage-groups-in-eop.md) ( セキュリティ グループとも言う) は、管理者役割のアクセス許可が必要な電子メール ユーザーの集まりです。たとえば、特定のユーザー グループに管理者役割アクセス許可を付与して、スパム対策設定とマルウェア対策設定を構成できるようにする場合があります。
    
    > [!NOTE]
    > 既定では、メールが有効なすべての新しいセキュリティ グループで、すべての送信者を認証する必要があります。これにより、外部の送信者はメールが有効なセキュリティ グループに対してメッセージを送信できなくなります。 
  
## <a name="before-you-begin"></a>開始する前に

- この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「配布グループとセキュリティ グループ」。 
    
- リモートの PowerShell コマンドレットを使用してグループの作成および管理を行う際、調整が発生することに注意してください。
    
- このコマンドレットはバッチ処理方法を使用しており、コマンドレットの結果が表示されるまで数分の送信遅延が生じます。
    
- Windows PowerShell を使用して Exchange Online Protection に接続する方法については、「[リモート PowerShell を使用して Exchange Online Protection に接続する](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)」を参照してください。
    
- このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。
    
> [!TIP]
> 問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="create-a-group-in-the-eac"></a>EAC でグループを作成する

1. Exchange 管理センター (EAC) で、 **[受信者]** \> **[グループ]** に移動します。
    
2. **[新規]**![[追加] アイコン](../media/ITPro-EAC-AddIcon.gif) をクリックしてから、必要に応じて、 **[配布グループ]** または **[セキュリティ グループ]** をクリックします。違いについては、「 [メールが有効なグループの種類](manage-groups-in-eop.md)」を参照してください。 
    
3. **[配布グループの新規作成]** ページまたは **[新しいセキュリティ グループ]** ページで、次のフィールドにデータを入力します。 
    
  - **[表示名]** 組織に固有で、EOP ユーザーにとって意味のある表示名を入力します。表示名は必須です。 
    
  - **[エイリアス]** 組織に固有で、最大 64 文字のグループのエイリアスを入力します。EOP ユーザーが電子メール メッセージの宛先行にエイリアスを入力すると、グループの表示名に解読されます。エイリアスを変更すると、グループのプライマリ SMTP アドレスも変更され、新しいエイリアスが追加されます。エイリアスは必須です。 
    
  - **[説明]** グループの目的がわかるようにグループの説明を入力します。 
    
  - **[所有者]** 既定では、グループを作成したユーザーがその所有者です。所有者を追加するには、 **[追加]**![[追加] アイコン](../media/ITPro-EAC-AddIcon.gif) を選択します。グループには、最低 1 人の所有者が必要です。
    
    > [!NOTE]
    > 所有者はグループのメンバーである必要はありません。 
  
  - **[メンバー]** このセクションは、グループ メンバーを追加したり、ユーザーがグループに参加または脱退するときに承認が必要かどうかを指定したりするために使用します。グループにメンバーを追加するには、 **[追加]**![[追加] アイコン](../media/ITPro-EAC-AddIcon.gif) をクリックします。
    
4. **[OK]** をクリックして元のページに戻ります。 
    
5. 完了したら、 **[保存]** をクリックしてグループを作成します。新しいグループがグループの一覧に表示されます。 
    
## <a name="edit-or-remove-a-group-in-the-eac"></a>EAC でグループを編集または削除する

1. EAC で、 **[受信者]** \> **[グループ]** に移動します。
    
2. 次のいずれかを実行します。
    
  - グループを編集するには、グループの一覧で、表示または変更する配布グループまたはセキュリティグループをクリックし、[ **** ![編集] 編集](../media/ITPro-EAC-EditIcon.gif)アイコンをクリックします。 必要に応じて、全般設定を更新したり、グループ所有者を追加または削除したり、グループメンバーを追加または削除したりできます。
    
  - グループを削除するには、次の手順を実行します。グループを選択して、 **[削除]**![[削除] アイコン](../media/ITPro-EAC-RemoveIcon.gif) をクリックします。
    
3. 変更が完了したら、 **[保存]** をクリックします。
    
## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>リモートの Windows PowerShell を使用してグループを作成、編集、または削除する

このセクションでは、リモートの Windows PowerShell を使用してグループを作成し、そのプロパティを変更する方法について説明します。また、既存のグループを削除する方法も説明します。 
  
 **リモートの Windows PowerShell を使用してグループを作成するには**
  
この例では、コマンドレット [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) を使用して、エイリアスが「itadmin」、名前が「IT Administrators」の配布グループを作成します。また、ユーザーをグループのメンバーとして追加します。 
  
```Powershell
New-EOPDistributionGroup -Type "Distribution" -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy "Member1"

```

配布グループではなくセキュリティ グループを作成するには、代わりに  `-Type "Security"` を指定します。 
  
正常に IT Administrators グループを作成したことを確認するには、コマンドレット [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) を実行して新しいグループの情報を表示します。 
  
```Powershell
Get-Recipient "IT Administrators" | Format-List

```

グループ内のメンバーの一覧を取得するには、次のようにコマンドレット [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) を実行します。 
  
```Powershell
Get-DistributionGroupMember "IT Administrators"

```

すべてのグループの完全な一覧を取得するには、次のように [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) コマンドレットを実行します。 
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | FT | more

```

 **リモートの Windows PowerShell を使用してグループのプロパティを変更するには**
  
コマンドレット [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) および [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) を使用して、グループのプロパティを表示し、変更します。EAC ではなくリモートの PowerShell を使用する利点は、複数のグループのプロパティを変更できることです。 
  
リモートの Windows PowerShell を使用してグループのプロパティを変更する例を次に示します。
  
この例では、コマンドレット [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) を使用して、シアトルの従業員グループのプライマリ SMTP アドレス (返信アドレスともいう) を sea.employees@contoso.com に変更します。 
  
```Powershell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"

```

グループのプロパティが正常に変更されたことを確認するには、コマンドレット [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) を使用して変更を確認します。リモートの PowerShell を使用する利点の 1 つは、複数のグループの複数のプロパティを参照できる点です。前にプライマリ SMTP アドレス グループが変更された例で、次のコマンドを実行して新しい値を確認します。 
  
```Powershell
Get-Recipient "Seattle Employees" | FL "PrimarySmtpAddress"

```

この例では、コマンドレット [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) を使用して、シアトルの従業員グループの全メンバーを更新します。全メンバーをコンマを使用して区切ります。 
  
```Powershell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")

```

シアトルの従業員グループの全メンバーの一覧を取得するには、次のようにコマンドレット [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) を使用します。 
  
```Powershell
Get-DistributionGroupMember "Seattle Employees"

```

 **リモートの Windows PowerShell を使用してグループを削除するには**
  
この例では、コマンドレット [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) を使用して、IT Administrators という名前の配布グループを削除します。 
  
```Powershell
Remove-EOPDistributionGroup -Identity "IT Administrators" 

```

グループが削除されたことを確認するには、次のようにコマンドレット [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) を実行し、グループ (この場合は「IT Administrators」) が削除されたことを確認します。 
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"

```


