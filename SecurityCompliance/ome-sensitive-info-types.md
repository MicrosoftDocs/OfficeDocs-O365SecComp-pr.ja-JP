---
title: Office 365 Message Encryption 機能を使用して、機密情報の種類のポリシーを作成する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: '概要: 機密情報の種類に関する Office 365 メッセージの暗号化ポリシー。'
ms.openlocfilehash: d74712798ba9d46614b5fc916e4b1ce111582304
ms.sourcegitcommit: 73f1db241c0686020167d43442e7b07a2199ea3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "36658123"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-office-365-message-encryption"></a>Office 365 Message Encryption 機能を使用して、機密情報の種類のポリシーを作成する

Exchange メールフロールールまたは Office 365 データ損失防止 (DLP) のいずれかを使用して、Office 365 メッセージの暗号化を使用して機密情報の種類ポリシーを作成できます。 Exchange メールフロールールを作成するには、Exchange 管理センター (EAC) または PowerShell のどちらかを使用できます。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>EAC でメールフロールールを使用してポリシーを作成するには

Exchange 管理センター (EAC) にサインインし、[**メールフロー** > ] [**ルール**] に移動します。 [ルール] ページで、Office 365 メッセージの暗号化を適用するルールを作成します。 特定のキーワードの存在や、メッセージまたは添付ファイル内の機密情報の種類などの条件に基づいてルールを作成することができます。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>PowerShell でメールフロールールを使用してポリシーを作成するには

Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。 手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。 New-transportrule コマンドレットと新しいコマンドレットを使用して、ポリシーを作成します。

### <a name="example-mail-flow-rule-created-with-powershell"></a>PowerShell を使用して作成されたメールフロールールの例

メールまたは添付ファイルに次の機密情報が含まれている場合に、組織外の電子メールを自動的に*暗号化*する Exchange メールフロールールを作成するには、PowerShell で次のコマンドを実行します。各種

- ABA ルーティング番号
- クレジットカード番号
- 医薬品執行機関 (DEA) 番号
- 米国/英国 passport number
- 米国の銀行口座番号
- 米国の個人納税者識別番号 (ITIN)
- 米国の社会保障番号 (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

詳細については[](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps) 、「 [new-transportrule](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps)」を参照してください。

## <a name="how-recipients-access-attachments"></a>受信者が添付ファイルにアクセスする方法

Office 365 がメッセージを暗号化した後は、受信者が暗号化された電子メールにアクセスして開くときに、添付ファイルへのアクセス権を無制限にすることができます。

## <a name="to-prepare-for-this-change"></a>この変更を準備するには

この変更に関して組織内のユーザーを準備するために、適用可能なエンドユーザードキュメントおよびトレーニング資料を更新することが必要な場合があります。 必要に応じて、これらの Office 365 メッセージ暗号化リソースをユーザーと共有します。

- [Outlook for PC で暗号化されたメッセージを送信、表示、および返信する](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Office 365 Essentials ビデオ: Office メッセージの暗号化](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>監査ログでのこれらの変更の表示

Office 365 は、このアクティビティを監査して、Office 365 管理者が使用できるようにします。 この操作は ' New-transportrule ' であり、セキュリティ & コンプライアンスセンターでの監査ログの検索からのサンプルの監査エントリのスニペットは以下のとおりです。

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>機密情報の種類のポリシーを無効にする、またはカスタマイズするには

Exchange メールフロールールを作成したら、exchange 管理センター (EAC) の**メールフロー** > **ルール**に移動し、[*送信機密メールを暗号化する (すぐ*に使用できるルール)] ルールを無効にして、[ルールを無効に](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)したり、編集したりすることができます。".
