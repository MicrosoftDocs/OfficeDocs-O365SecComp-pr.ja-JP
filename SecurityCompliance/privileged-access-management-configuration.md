---
title: Office 365 にアクセス権限の管理を構成します。
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.custom: Ent_Solutions
ms.assetid: ''
description: このトピックを使用して、Office 365 にアクセス権限の管理を構成する方法の詳細については、
ms.openlocfilehash: b2b6ab18687617c0da3425f4ee60cf81074f6f69
ms.sourcegitcommit: 15dfa0c83aa88816c18e30a44a49e36e733d952c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "24021405"
---
# <a name="configuring-privileged-access-management-in-office-365"></a>Office 365 にアクセス権限の管理を構成します。

> [!IMPORTANT]
> このトピックでは、Office 365 の E5 と高度なコンプライアンスの Sku でのみ現在利用できる機能の展開と構成のガイダンスについて説明します。

このトピックでは有効にし、Office 365 の組織内のアクセス権限の管理について説明します。いずれかの方法を使用することができます、管理者アクセス権を管理および使用するには、365 の管理窓口または Exchange 管理 PowerShell。 

## <a name="enable-and-configure-privileged-access-management"></a>有効にして、アクセス権限の管理を構成します。

設定し、Office 365 の組織内のアクセス権限を使用してこれらの手順に従います。

- [手順 1: 承認者のグループを作成します。](privileged-access-management-configuration.md#step1)

    特権アクセスの使用を開始する前に、管理者特権、特権を持つタスクにアクセスするための着信方向の要求の承認権限を持ってことを確認します。承認者グループの一部になっているユーザーはアクセス権の要求を承認することになります。これは、Office 365 のメールが有効なセキュリティ グループを作成することによって有効になります。

- [手順 2: アクセス権限を有効にします。](privileged-access-management-configuration.md#step2)

    アクセス権限を明示的にオンにする Office 365 の既定の承認者グループとアクセス権限の管理アクセスの制御から除外することがシステム アカウントのセットを含む必要があります。

- [アクセス ポリシーを作成する手順 3。](privileged-access-management-configuration.md#step3)

    承認ポリシーを作成すると、個々 のタスクのスコープの特定の承認要件を定義できます。承認の種類のオプションは、**自動**または**手動**です。

- [ステップ 4: 送信とアクセス権限の要求を承認します。](privileged-access-management-configuration.md#step4)

    いったん有効に、特権を持つアクセスでは、定義されている関連する承認ポリシーを持つ任意のタスクを実行するための承認が必要です。含まれているタスクを実行するために必要とするユーザーの承認ポリシーが要求する必要があり、タスクを実行するために必要なアクセス許可を持つために、アクセスの承認を付与します。

承認を付与すると、要求元のユーザーは、目的のタスクを実行できるとアクセス権限は承認され、ユーザーの代わりにタスクを実行します。承認は、要求の有効期間 (既定の期間は、4 時間) 中に、依頼者が目的のタスクを複数回実行します。このようなすべての実行はログに記録したり、セキュリティとコンプライアンスの監査に使用可能です。 

> [!NOTE]
> Exchange 管理 PowerShell を使用して、有効にしてアクセス権限を構成する場合は、以下の[Exchange オンライン PowerShell への接続は、多要素認証を使用して](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)Office 365 のオンライン PowerShell を Exchange に接続するための手順資格情報です。オンライン PowerShell を Exchange に接続中にアクセス権限を有効にする手順を使用する Office 365 の組織の多要素認証を有効にする必要はありません。多要素認証で接続する、要求に署名するためのアクセス権限で使用される、OAuth トークンを作成します。

<a name="step1"> </a>

## <a name="step-1---create-an-approvers-group"></a>手順 1 - 承認者のグループを作成します。

1. 組織の管理者アカウントの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. **グループ**には、管理センターで、 > **グループを追加**します。

3. **メールが有効なセキュリティ グループ**のグループの種類を選択し、し、新しいグループの**名前**、**グループの電子メール アドレス**、および**説明**のフィールドを完了します。

4. グループを保存します。グループを完全に構成して、Office 365 の管理ページに表示するのに数分かかる場合があります。

5. 新しい承認者のグループを選択し、グループにユーザーを追加するのには**編集**を選択します。

6. グループを保存します。

<a name="step2"> </a>

## <a name="step-2---enable-privileged-access"></a>手順 2 - アクセス権限を有効にします。

### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用してください。

1. 組織の管理者アカウントの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. 移動、管理センターで、**の設定 > セキュリティとプライバシー** > **のアクセス権限**。

3. **アクセス権限の承認を必要とする**コントロールを有効にします。

4. の**既定の承認者グループ**に手順 1 で作成した承認者のグループに割り当てます。

5. **保存**して**閉じます**。

### <a name="using-exchange-management-powershell"></a>Exchange 管理 PowerShell を使用します。

アクセス権限を有効にして、承認者のグループを割り当てるには、Exchange オンライン PowerShell で次のコマンドを実行します。
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
例:
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> システム アカウントの機能は、組織内の特定の自動化を確実に使用可能になりますが、アクセス権限の依存関係を持たない作業できますを推奨するこのような除外される例外的な許可承認および監査する必要があります。普段は。

<a name="step3"> </a>

## <a name="step-3---create-an-access-policy"></a>手順 3 - アクセス ポリシーを作成します。

### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用してください。

1. 組織の管理者アカウントの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. **設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。

3. **アクセス ポリシーを管理し要求**を選択します。

4. **ポリシーを構成する**を選択し、[**ポリシーの追加**] を選択します。

5. ドロップ ダウン フィールドから、組織の適切な値を選択します。
    
    **ポリシーの種類**: タスク、ロール、またはロールのグループ

    **ポリシーのスコープ**: Exchange または Office 365

    **ポリシー名**: 使用可能なポリシーから選択

    **承認タイプ**: 手動または自動

    **承認グループ**: ステップ 1 で作成した承認者のグループを選択します。

6. **作成**し、[**閉じる**を選択します。ポリシーを完全に構成し、有効にするのには数分かかる場合があります。

### <a name="using-exchange-management-powershell"></a>Exchange 管理 PowerShell を使用します。

次のコマンドを実行 Exchange オンライン PowerShell を作成し、承認ポリシーを定義します。

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
例:
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>ステップ 4: 送信とアクセス権限の要求を承認します。

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>特権付きタスクを実行する昇格の承認を要求します。

#### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用してください。

1. ユーザーの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. **設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。

3. **アクセス ポリシーを管理し要求**を選択します。

4. **新しい要求**を選択します。ドロップ ダウン フィールドから、組織の適切な値を選択します。

    **要求の種類**: タスク、ロール、またはロールのグループ

    **要求スコープ**: Exchange

    **要求**: 使用可能なポリシーから選択

    **期間 (時間)**: 要求されたアクセスの時間数

    **コメント**: コメントのテキスト フィールドは、アクセス権の要求に関連します。

5. **保存**し、**閉じる**を選択します。要求は、電子メールでの承認者のグループに送信されます。

#### <a name="using-exchange-management-powershell"></a>Exchange 管理 PowerShell を使用します。

次のコマンドを実行 Exchange オンライン PowerShell を作成し、承認者のグループに承認依頼を送信します。
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
例:
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a>昇格の要求のステータスを表示
承認要求が作成されると、管理センターには、昇格の要求の状態を確認できますか、Exchange 管理の PowerShell で使用する、関連付けられている要求の id。

#### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用してください。

1. ユーザーの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. **設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。

3. **アクセス ポリシーを管理し要求**を選択します。

4. **保留中**の、**承認**、**拒否**、または**お客様のロック ボックス**の状態で送信された要求をフィルター処理する**ビュー**を選択します。

#### <a name="using-exchange-management-powershell"></a>Exchange 管理 PowerShell を使用します。

次のコマンドを実行 Exchange オンライン PowerShell は、特定の要求 ID の承認の要求の状態を表示するのには。
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
例:
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>昇格の承認要求を承認します。
承認要求が作成されると、関連する承認者グループのメンバーは電子メール通知が表示され、要求 ID に関連付けられている要求を承認することができます。

#### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用してください。

1. ユーザーの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. **設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。

3. **アクセス ポリシーを管理し要求**を選択します。

4. 一覧表示されている要求の詳細を表示するのには、要求の操作を実行するを選択します。

5. 要求を承認するか要求を拒否する**拒否**を選択するのには、**承認**を選択します。以前承認された要求は、失効**を取り消す**かを選択してアクセスを持つことができます。

#### <a name="using-exchange-management-powershell"></a>Exchange 管理 PowerShell を使用します。

次のコマンドを実行 Exchange オンラインの昇格の承認要求を承認する PowerShell:

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
例:
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

次のコマンドを実行 Exchange オンラインの昇格の承認要求を拒否する PowerShell:

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
例:
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="disable-privileged-access-in-office-365"></a>Office 365 の管理者のアクセスを無効にします。

必要な場合、組織のアクセス権限の管理を無効にできます。特権を無効にするとアクセスは削除されません、関連付けられている承認ポリシーや承認者のグループです。

### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用してください。

1. 組織の管理者アカウントの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. **設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。

3. **アクセス権限の承認を必要とする**コントロールを有効にします。

### <a name="using-exchange-management-powershell"></a>Exchange 管理 PowerShell を使用します。

次のコマンドを実行 Exchange オンライン Powershell へのアクセス権限を無効にします。

```
Disable-ElevatedAccessControl
```