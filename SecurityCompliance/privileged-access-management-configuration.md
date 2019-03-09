---
title: Office 365 での特権アクセス管理の構成
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: Office 365 での特権アクセス管理の構成の詳細については、このトピックを使用してください。
ms.openlocfilehash: 3d186998006dd3cc59877b1571f50314af5bbce8
ms.sourcegitcommit: 5eb664b6ecef94aef4018a75684ee4ae66c486bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "30492826"
---
# <a name="configuring-privileged-access-management-in-office-365"></a>Office 365 での特権アクセス管理の構成

> [!IMPORTANT]
> このトピックでは、Office 365 E5 と Advanced コンプライアンス sku で現在利用可能な機能の展開と構成のガイダンスについて説明します。

このトピックでは、Office 365 組織で特権アクセス管理を有効にして構成する方法について説明します。 Microsoft 365 管理センターまたは Exchange 管理 PowerShell のいずれかを使用して、特権アクセスを管理および使用することができます。 

## <a name="enable-and-configure-privileged-access-management"></a>特権アクセス管理を有効にして構成する

Office 365 組織で特権アクセスをセットアップして使用するには、次の手順を実行します。

- [手順 1: 承認者のグループを作成する](privileged-access-management-configuration.md#step1)

    特権アクセスの使用を開始する前に、昇格されたタスクと特権タスクへのアクセスのための受信要求に対して、誰がだれに承認権限を付与するかを決定します。 承認者グループの一部であるユーザーは、アクセス要求を承認できます。 これは、Office 365 でメールが有効なセキュリティグループを作成することによって有効になります。

- [手順 2: 特権アクセスを有効にする](privileged-access-management-configuration.md#step2)

    既定の承認者グループを使用して Office 365 で特権アクセスを明示的に有効にする必要があります。また、特権アクセス管理アクセス制御から除外する必要があるシステムアカウントのセットを含める必要があります。

- [手順 3: アクセスポリシーを作成する](privileged-access-management-configuration.md#step3)

    承認ポリシーを作成すると、個々のタスクでスコープを設定する特定の承認要件を定義できます。 承認の種類のオプションは**自動**または**手動**です。

- [手順 4: 特権アクセス要求を送信/承認する](privileged-access-management-configuration.md#step4)

    有効にした場合、関連付けられた承認ポリシーが定義されているタスクを実行するには、権限のあるアクセス権が必要です。 承認ポリシーに含まれるタスクを実行する必要があるユーザーは、タスクを実行するために必要なアクセス許可を付与するために、要求してアクセス承認を付与する必要があります。

承認が付与されると、要求元のユーザーは目的のタスクを実行できるようになり、特権アクセスはユーザーの代わりにタスクを承認して実行します。 承認は、要求された期間 (既定の期間は4時間) に対して有効なままとなり、要求者は目的のタスクを複数回実行できます。 このような実行はすべてログに記録され、セキュリティとコンプライアンスの監査に使用できるようになります。 

> [!NOTE]
> exchange 管理 powershell を使用して特権アクセスを有効にし、構成する場合は、「[複数要素認証を使用して exchange online powershell に](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)接続する」の手順に従って、Office 365 を使用して exchange online powershell に接続します。クリデンシャル. Office 365 組織に対して多要素認証を有効にして、Exchange Online PowerShell への接続中に特権アクセスを有効にする手順を使用する必要はありません。 多要素認証を使用して接続すると、要求に署名するために特権アクセスで使用される OAuth トークンが作成されます。

<a name="step1"> </a>

## <a name="step-1---create-an-approvers-group"></a>手順 1-承認者のグループを作成する

1. 組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. 管理センターで、[グループ**** > **の追加]** を選びます。

3. メールが**有効なセキュリティグループ**グループの種類を選択し、新しいグループの**名前**、**グループ電子メールアドレス**、および**説明**フィールドを入力します。

4. グループを保存します。 グループが完全に構成され、Office 365 管理センターに表示されるまでに数分かかる場合があります。

5. 新しい承認者のグループを選択し、[**編集**] を選択してグループにユーザーを追加します。

6. グループを保存します。

<a name="step2"> </a>

## <a name="step-2---enable-privileged-access"></a>手順 2-特権アクセスを有効にする

### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの使用

1. 組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. 管理センターで、[**設定 > セキュリティ & プライバシー** > **特権アクセス**] に移動します。

3. [**特権アクセス制御の承認を必須**にする] を有効にします。

4. 手順1で作成した承認者のグループを**既定の承認者グループ**として割り当てます。

5. **保存**して**閉じ**ます。

### <a name="using-exchange-management-powershell"></a>Exchange 管理 PowerShell の使用

Exchange Online PowerShell で次のコマンドを実行して、特権アクセスを有効にし、承認者のグループを割り当てます。
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
例:
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> システムアカウント機能を使用して、組織内の特定のオートメーションが特権アクセスに依存せずに機能できるようにすることができます。ただし、このような除外は例外的に行うことをお勧めします。普段は。

<a name="step3"> </a>

## <a name="step-3---create-an-access-policy"></a>手順 3-アクセスポリシーを作成する

Office 365 組織に対して最大30の特権アクセスポリシーを作成し、構成することができます。

### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの使用

1. 組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. 管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。

3. [**アクセスポリシーと要求の管理**] を選択します。

4. [**ポリシーの構成**] を選択し、[**ポリシーの追加**] を選択します。

5. ドロップダウンフィールドで、組織に適切な値を選択します。
    
    **ポリシーの種類**: タスク、役割、または役割グループ

    **ポリシースコープ**: Exchange

    **ポリシー名**: 使用可能なポリシーから選択します。

    **承認の種類**: 手動または自動

    **承認グループ**: 手順1で作成した承認者グループを選択します。

6. [**作成**] を選択し、[**閉じる**] をクリックします。 ポリシーが完全に構成され、有効になるまでに数分かかる場合があります。

### <a name="using-exchange-management-powershell"></a>Exchange 管理 PowerShell の使用

Exchange Online PowerShell で次のコマンドを実行して、承認ポリシーを作成および定義します。

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
例:
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>手順 4: 特権アクセス要求を送信/承認する

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>権限タスクを実行するための昇格承認の要求

特権アクセスの要求は、要求が送信されてから最大24時間有効です。 承認または拒否されていない場合、要求は期限切れになり、アクセスは承認されません。

#### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの使用

1. 資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. 管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。

3. [**アクセスポリシーと要求の管理**] を選択します。

4. [**新しい要求**] を選択します。 ドロップダウンフィールドで、組織に適切な値を選択します。

    **要求の種類**: タスク、役割、または役割グループ

    **要求スコープ**: Exchange

    **要求**: 使用可能なポリシーから選択します

    **期間 (時間)**: 要求されたアクセスの時間数。 要求可能な時間数に制限はありません。

    **comments**: アクセス要求に関連するコメントのテキストフィールド

5. [**保存**] を選択し、[**閉じる**] をクリックします。 要求は、電子メールを介して承認者のグループに送信されます。

#### <a name="using-exchange-management-powershell"></a>Exchange 管理 PowerShell の使用

Exchange Online PowerShell で次のコマンドを実行して、承認要求を作成し、承認者のグループに送信します。
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
例:
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a>昇格要求の状態を表示する
承認要求が作成されると、昇格要求の状態は、管理センターまたは Exchange 管理 PowerShell で、関連付けられている要求 ID を使用して確認できます。

#### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの使用

1. 資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. 管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。

3. [**アクセスポリシーと要求の管理**] を選択します。

4. [**表示**] を選択して、送信された要求を**保留**、**承認**、**拒否**、または**顧客のロックボックス**の状態でフィルター処理します。

#### <a name="using-exchange-management-powershell"></a>Exchange 管理 PowerShell の使用

Exchange Online PowerShell で次のコマンドを実行して、特定の要求 ID の承認要求の状態を表示します。
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
例:
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>昇格認証要求を承認する
承認要求が作成されると、関連する承認者グループのメンバーは電子メール通知を受信し、要求 ID に関連付けられている要求を承認できます。 送信者は、電子メールメッセージを使用して、要求の承認または拒否を通知されます。

#### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの使用

1. 資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. 管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。

3. [**アクセスポリシーと要求の管理**] を選択します。

4. 詳細を表示し、要求に対してアクションを実行するには、リストされている要求を選択します。

5. [**承認**] を選択して要求を承認するか、[**拒否**] を選択して要求を拒否します。 以前に承認された要求では、 **Revoke**を選択することによってアクセスを取り消すことができます

#### <a name="using-exchange-management-powershell"></a>Exchange 管理 PowerShell の使用

Exchange Online PowerShell で次のコマンドを実行して、昇格認証要求を承認します。

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
例:
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Exchange Online PowerShell で次のコマンドを実行して、昇格認証要求を拒否します。

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
例:
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Office 365 で特権アクセスポリシーを削除する
組織で不要になった場合は、特権アクセスポリシーを削除することができます。

### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの使用

1. 組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. 管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。

3. [**アクセスポリシーと要求の管理**] を選択します。

4. [**構成ポリシー**] を選択します。

5. 削除するポリシーを選択し、[ポリシーの**削除**] を選択します。

6. **[閉じる]** を選択します。

### <a name="using-exchange-management-powershell"></a>Exchange 管理 PowerShell の使用

Exchange Online Powershell で次のコマンドを実行して、特権アクセスポリシーを削除します。

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Office 365 で特権アクセスを無効にする

必要に応じて、組織の特権アクセス管理を無効にすることができます。 特権アクセスを無効にしても、関連付けられている承認ポリシーまたは承認グループは削除されません。

### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの使用

1. 組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. 管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。

3. [**特権アクセス制御の承認を必須**にする] を有効にします。

### <a name="using-exchange-management-powershell"></a>Exchange 管理 PowerShell の使用

Exchange Online Powershell で次のコマンドを実行して、特権アクセスを無効にします。

```
Disable-ElevatedAccessControl
```