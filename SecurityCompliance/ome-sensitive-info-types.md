---
title: Office 365 の機密情報のメッセージ暗号化ポリシー
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/31/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: Office 365 では、機密情報の種類のメッセージ暗号化ポリシーが利用可能になりました。'
ms.openlocfilehash: e2a72ee85ca65a2fe8ae1543979b51915ff0a88f
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2019
ms.locfileid: "29696201"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a>Office 365 の機密情報のメッセージ暗号化ポリシー

更新プログラム (1/30/19): 2018 年10月に、お客様の小規模なサンプルを使用して、特定の機密情報の種類に基づいて機密メールを自動的に暗号化することによって保護を簡略化できるかどうかを理解しています。このサンプルからの肯定的なフィードバックに基づき、2018年12月に、より多様なテナントのプロファイルに拡張することを決定しました。次のロールアウトを送信してテナントを選択したら、フィードバックを検討して、より複雑な環境を使用しているお客様がルールをより慎重に実装する必要があると判断しました。そのため、計画を調整しています。

2019年1月15日の展開のために組織が選択されている場合、自動ポリシーはロールアウトされません。代わりに、この記事では、ロールアウト yourselves を完了する方法について説明しています。詳細については、「how to」を参照してください。

||
|:-----|
|この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。この記事は、管理者および it 担当者を対象としています。暗号化されたメッセージの送信または受信に関する情報をお探しの場合は、「 [Office 365 message Encryption (OME)](ome.md) 」の記事の一覧を参照し、ニーズに最も適した記事を見つけてください。 |
||

## <a name="how-to-create-the-sensitive-information-type-policy-for-your-tenant"></a>テナントの機密情報の種類のポリシーを作成する方法

Exchange メールフロールールまたは Office 365 データ損失防止 (DLP) のいずれかを使用して、機密情報の種類のポリシーを作成できます。exchange メールフロールールを作成するには、exchange 管理センター (EAC) または PowerShell のどちらかを使用できます。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>EAC でメールフロールールを使用してポリシーを作成するには

Exchange 管理センター (EAC) にサインインし、[**メールフロー** > **ルール**] に移動します。ここで、メッセージまたは添付ファイルに特定のキーワードや機密情報の種類が存在するなどの条件に基づいて、Office 365 メッセージの暗号化を適用するルールを作成します。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>PowerShell でメールフロールールを使用してポリシーを作成するには

Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。TransporRule コマンドレットと新しいコマンドレットを使用して、ポリシーを作成します。

### <a name="example-mail-flow-rule-created-with-powershell"></a>PowerShell を使用して作成されたメールフロールールの例

PowerShell で次のコマンドを実行すると、電子メールまたは添付ファイルに次の機密情報が含まれている場合に、組織外のメールを自動的に*暗号化*する Exchange メールフロールールを作成します。情報の種類:

- ABA ルーティング番号
- クレジットカード番号
- 医薬品執行機関 (dea) 番号
- 米国/英国のパスポート番号
- 米国の銀行口座番号
- 米国の個人納税者識別番号 (ITIN)
- 米国の社会保障番号 (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentsForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

## <a name="how-recipients-access-attachments"></a>受信者が添付ファイルにアクセスする方法

メッセージが暗号化されると、受信者は暗号化された電子メールにアクセスして開くと、添付ファイルに無制限にアクセスできるようになります。

## <a name="to-prepare-for-this-change"></a>この変更を準備するには

この変更に関して組織内のユーザーを準備するために、適用可能なエンドユーザードキュメントおよびトレーニング資料を更新することが必要な場合があります。必要に応じて、これらの Office 365 メッセージ暗号化リソースをユーザーと共有します。

- [Outlook for PC で暗号化されたメッセージを送信、表示、および返信する](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [office 365 Essentials ビデオ: office メッセージの暗号化](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>監査ログでのこれらの変更の表示

このアクティビティは監査され、Office 365 管理者が使用できます。この操作は ' new-transportrule ' であり、Security & コンプライアンスセンターでの監査ログの検索に含まれるサンプルの監査エントリのスニペットは以下のとおりです。

|     |
| --- |
| *{"設定時刻": "2018-28t23:35:01", "Id": "a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c", "Operation": "New-new-transportrule", "": "", "UserKey": "", "RecordType": "", "": "Microsoft Operator", "UserType ": 3"、"バージョン": 1, "ワークロード": "Exchange", "clientip": "123.456.147.68: 17584", "": "", "UserId": "" or ":": "" 組織名 "、" "、" "、" CY4PR13MBXXXX (15.20.1382.008) "," パラメーター ": {" name ":" Organization "、" value ":" 123456-221d-12346 "{" name ":" ApplyRightsProtectionTemplate "、" value ":" Encrypt "}、{" name ":" name "、" Value ":" 送信機密性の高いメールの暗号化 (アウトボックスルール) "}, {" name ":"MessageContainsDataClassificationsいう.* |
| |

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>機密情報の種類のポリシーを無効にする、またはカスタマイズするには

exchange メールフロールールを作成したら、exchange 管理センター (EAC) の**メールフロー** > **ルール**に移動し、[*送信機密メールを暗号化する (すぐ*に使用できるルール)] ルールを無効にして、[ルールを無効に](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)したり、編集したりすることができます。".
