---
title: 機密情報の新しい Office 365 のメッセージの暗号化のポリシー
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 12/13/2018
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: 新しい Office 365 のメッセージの暗号化用のポリシーの機密情報。'
ms.openlocfilehash: 180050d1bf9303f6d29bc126e66ac53211c2fb34
ms.sourcegitcommit: 3aae959ea1ac5ef61a9942c681d334831e6b6038
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "27271093"
---
# <a name="new-office-365-message-encryption-policy-for-sensitive-information"></a>機密情報の新しい Office 365 のメッセージの暗号化のポリシー

機密情報が含まれていると、組織外に送信されているすべての電子メールを Office 365 のメッセージの暗号化を適用する Office 365 テナントに新しい自動ポリシーを作成しています。この新規の Exchange メール フロー ルールは自動的に作成、Office 365 テナントに組織は、既定で保護されるようにします。

## <a name="how-will-this-work"></a>この作業をどのようにでしょうか。

組織で Office 365 のメッセージ ・ センター、テナントのこの自動ポリシーを作成するのには、日付を通知する通知が表示されます。少なくとも 30 日間の通知を指定して、オプションを無効にする必要があります。可能性があることをすることがありますシナリオでは、既に、機密性の高い型をスキャンするサード パーティ製データ損失防止ソリューションがあるかどうか、します。

## <a name="new-policy-details"></a>新しいポリシーの詳細

使用して組織外の電子メールを自動的に暗号化される組織で新しい Exchange メール フロー ルールを作成するは、*暗号化専用*ポリシーは次の種類機密情報にはが含まれている場合。

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

更新または新しい変更する前に既存の Office 365 の構成設定を変更する必要はありません。ただし、この変更を組織内のユーザーを準備するのには、トレーニング資料、マニュアルの該当する場合のエンド ・ ユーザーを更新することがあります。

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a>この変更表されるか、監査ログにしますか。

このアクティビティでは、監査され、お客様が利用します。 操作は、' 新しい TransportRule' は、監査ログの検索でセキュリティとコンプライアンスの中心から監査エントリの例のスニペットの下にある.

|     |
| --- |
| *{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345"、「RecordType」: 1 の場合、"ResultStatus":"True"、"ユーザーのキー":"Microsoft オペレーター」、「UserType」: 3、[バージョン]: 1、「ワークロード」:「交換」、"ClientIP":「123.456.147.68:17584」、"オブジェクト Id":"「、」ユーザー Id":"マイクロソフトの Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters」: {[名]:「組織」、「値」:"123456 221 d-12346"{[名]:"ApplyRightsProtectionTemplate"、「値」:「暗号化」}、{[名]:「名」、「値」:「(ルール) から機密性の高い電子メールを送信を暗号化する」}、{[名]:"MessageContainsDataClassifications」などです。*
 |

## <a name="how-do-i-opt-out"></a>方法の操作を行いますか脱退か。

この変更を中止する場合は、次の手順に従ってください。

1. [Exchange オンライン PowerShell](https://aka.ms/exopowershell)グローバル管理者ロールを持つユーザーとして接続します。
2.  認証した後、次のコードを実行します。

    ```
    Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
    ```

## <a name="how-do-i-disable-the-automatic-policy"></a>自動ポリシーを無効にする方法は?

でしたを無効にこの変更は、Exchange のメール ルールは既に作成されている場合することができます[、ルールを無効にするの](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)には、**メールの流れ** > Exchange 管理ツールでは、**ルール**のセンター (EAC) と「*送信暗号化ルール無効にします。(ルール) から機密性の高い電子メール*」です。
