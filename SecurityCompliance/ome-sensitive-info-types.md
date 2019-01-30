---
title: 機密情報の新しい Office 365 のメッセージの暗号化のポリシー
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/16/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: は、すべてのテナントにロールアウトの機密情報の種類の Office 365 のメッセージの暗号化ポリシーを自動的に適用します。'
ms.openlocfilehash: f83bf0fe572586b3becf2dd53395e611bdaaea24
ms.sourcegitcommit: 03b9221d9885bcde1cdb5df2c2dc5d835802d299
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29614381"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a>機密情報を office 365 のメッセージの暗号化ポリシー

グループ、組織の規模と複雑さ、メールの流れに基づき、テナントの機密性の高い特定の種類を含む電子メールを Office 365 のメッセージの暗号化を適用する Office 365 テナントに新しい自動ポリシーの低速ロール アウトを行って、情報です。テナントの小規模なグループではテストされます。このポリシーはありませんにロールアウトされるすべての組織と組織のサイズに関する考慮事項と、メールの流れの複雑さを使用して、このロールアウトのための適格性を決定します。このロールアウトのため、組織が選択されている場合、ことを通知する日付をこの自動ポリシーを作成するには、少なくとも 30 日間の通知とを無効にするオプションが与えられます Office 365 のメッセージ センターに通知を受け取ります。マイクロソフトがこのポリシーを作成するを待つ必要があるようにしたい場合、自分自身で作成できるポリシーを作成するこの自動 Exchange メール フローの規則を使用しています。

## <a name="when-to-expect-the-update-for-your-tenant"></a>テナント用の更新プログラムが予想される時期

組織で Office 365 のメッセージ ・ センター、テナントのこの自動ポリシーを作成するのには、日付を通知する通知が表示されます。少なくとも 30 日間の通知を指定して、オプションを無効にする必要があります。可能性があることをすることがありますシナリオでは、既に、機密性の高い型をスキャンするサード パーティ製データ損失防止ソリューションがあるかどうか、します。無効にする方法の詳細については、この資料で後で使用できます。

## <a name="sensitive-information-type-policy-details"></a>機密性の高い情報の種類のポリシーの詳細

使用して組織外の電子メールを自動的に暗号化される組織で Exchange メール フロー ルールを作成するは、*暗号化専用*ポリシーは、電子メールまたは添付ファイルに次の種類の機密情報が含まれている場合。

- ABA ルーティング番号
- クレジット カード番号
- 薬品執行局 (DEA) の数
- 米国と英国のパスポート番号
- 米国の銀行口座番号
- 米国の個人納税者識別番号 (ITIN)
- 米国の社会保障番号 (SSN)

> [!Note]
> 正確な機密性の高いタイプは、組織のロケールによって異なる場合があり、メッセージ センターからの通知で伝達されます。

## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>この変更の準備を行うには何が必要でしょうか。

更新または新しい変更する前に既存の Office 365 の構成設定を変更する必要はありません。ただし、この変更を組織内のユーザーを準備するのには、トレーニング資料、マニュアルの該当する場合のエンド ・ ユーザーを更新することがあります。必要に応じてユーザーと Office 365 のメッセージの暗号化リソースを共有します。

- [送信、表示、および PC の Outlook で暗号化されたメッセージに返信します。](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Office 365 に関する重要事項のビデオ: Office のメッセージの暗号化](https://youtu.be/CQR0cG_iEUc)

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a>この変更表されるか、監査ログにしますか。

このアクティビティでは、監査され、お客様が利用します。 操作は、' 新しい TransportRule' と & コンプライアンス センターのセキュリティの監査ログの検索から監査エントリの例のスニペットの下にあります。

|     |
| --- |
| *{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345"、「RecordType」: 1 の場合、"ResultStatus":"True"、"ユーザーのキー":"Microsoft オペレーター」、「UserType」: 3、[バージョン]: 1、「ワークロード」:「交換」、"ClientIP":「123.456.147.68:17584」、"オブジェクト Id":"「、」ユーザー Id":"マイクロソフトの Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters」: {[名]:「組織」、「値」:"123456 221 d-12346"{[名]:"ApplyRightsProtectionTemplate"、「値」:「暗号化」}、{[名]:「名」、「値」:「(ルール) から機密性の高い電子メールを送信を暗号化する」}、{[名]:"MessageContainsDataClassifications」などです。*
 |

## <a name="how-do-i-opt-out"></a>方法の操作を行いますか脱退か。

この変更を中止する場合は、次の手順に従ってください。

1. 大域管理者アクセス許可を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://aka.ms/exopowershell)を参照してください。
2. とおりセット IRMConfiguration コマンドレットを実行します。

   ```
   Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
   ```

## <a name="how-do-i-disable-or-customize-the-automatic-policy"></a>方法を無効にする、または自動のポリシーをカスタマイズしますか。

でしたを無効にこの変更は、Exchange のメール フロー ルールは既に作成されている場合することができます[を無効にするかルールを編集して](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)**メールの流れ**に移動して > Exchange 管理ツールでは、**ルール**(EAC) を中心し、"*暗号化の規則を無効にします。(ルール) から機密性の高い電子メールを送信*」です。
