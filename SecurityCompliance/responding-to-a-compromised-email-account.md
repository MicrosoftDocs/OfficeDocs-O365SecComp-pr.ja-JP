---
title: 侵害された Office 365 電子メール アカウントへの対応
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 06/27/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: 認識し、Office 365 で電子メールのセキュリティを侵害されたアカウントに対応する方法を学習します。
ms.openlocfilehash: d6731b6f1c12a3fa2b30bcbe6e12212629b65f9f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532580"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>侵害された Office 365 電子メール アカウントへの対応

**概要**認識し、Office 365 で電子メールのセキュリティを侵害されたアカウントに対応する方法を説明します。

## <a name="what-is-a-compromised-email-account-in-office-365"></a>Office 365 では、危険にさらされた電子メール アカウントとは何ですか。
Office 365 のメールボックス、データ、およびその他のサービスへのアクセスをユーザー名とパスワードまたは暗証番号 (pin) などの資格情報を使用して制御されます。これらの資格情報を盗み、意図したユーザー以外の誰かに盗まれた資格情報が危険にさらされると見なされます。攻撃者は元のユーザーとしてサインインし、不正な操作を実行できます。盗まれた資格情報を使用すると、ユーザーの Office 365 のメールボックス、SharePoint フォルダー、またはユーザーの OneDrive 内のファイル、攻撃者はアクセスできます。表示される 1 つのアクションは、組織の内外両方の受信者に元のユーザーとしての e メールを送信する攻撃者です。攻撃者は、データを外部の受信者にメール、ときにこのデータ exfiltration と呼びます。

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>危険にさらされた Office 365 の電子メール アカウントの現象
ユーザーに注意してくださいし、Office 365 のメールボックスでの異常な活動を報告する場合があります。いくつかの一般的な現象を以下に示します。
- 存在しないか削除された電子メールなどの不審な活動です。
- 他のユーザーが表示される電子メール セキュリティを侵害されたアカウントから既存の送信者の**送信済みアイテム**フォルダーに対応する電子メールに。
- 目的のユーザーまたは管理者によって作成されていない受信トレイ ルールが存在します。またはこれらの規則が自動的に不明なアドレスに e メールを転送、**メモ**、**迷惑メール**、または**RSS 購読**フォルダーに移動します。
- グローバル アドレス一覧にユーザーの表示名を変更する可能性があります。
- ユーザーのメールボックスは、電子メールを送信するからブロックされています。

ユーザーは、上記の現象のいずれかを報告する場合は、行う必要がありますさらに調査します。Office 365 のセキュリティとコンプライアンスの中心と、Azure ポータルは、侵害される可能性があるユーザー アカウントのアクティビティを調査するためのツールを提供します。
- Office 365 ユニファイド監査ログでセキュリティとコンプライアンス センター - は、日付範囲にわたるから現在の日付に不審なアクティビティが発生した直前の結果をフィルタ リングによって疑いのあるアカウントのすべてのアクティビティを確認します。フィルターを適用しないアクティビティの検索中にします。
- Azure AD のログ、および AD の Azure ポータルで使用可能なその他のリスク ・ レポートを使用します。これらの列内の値を確認します。
    - IP アドレスを確認します。
    - サインインの場所
    - 回サインイン
    - サインインが成功または失敗



## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>Office 365 のアカウントとメールボックスをセキュリティで保護し、疑いがあるに電子メール機能を復元する方法が侵害されました。

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

### <a name="step-1-reset-the-users-password"></a>ステップ 1 は、ユーザーのパスワードをリセット
> [!WARNING]
> 攻撃者がアクセス、メールボックスにこの時点で電子メールを通じて目的のユーザーに新しいパスワードを送りません。

1. 次ビジネス パスワードのリセット、Office 365 の他のユーザーの他のプロシージャの[管理者: ビジネスのパスワードを Office 365 のリセット](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>不審な電子メール転送アドレスの削除は 2 つのステップします。
1. 開く、 **Office 365 管理者センター > ユーザーのアクティブな**です。
2. 対象のユーザー アカウントを検索し、**メールの設定**を展開します。
3. **電子メールの転送**をするには、[**編集**] をクリックします。
4. 不審な転送先アドレスを削除します。

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>ステップ 3 は、不審な受信トレイ ルールを無効にします。
1. Outlook Web App (OWA) を使用してユーザーのメールボックスにサインインします。
2. 歯車のアイコンをクリックし、[**メール**] をクリックします。
3. **スイープし、受信トレイのルール**] をクリックし、ルールを確認します。
4. 無効にするか、不審なルールを削除します。

### <a name="step-4-unblock-the-user-from-sending-mail"></a>手順 4 ブロックを解除するユーザーがメールを送信します。
侵害された疑いがあるメールボックスがスパム メールを送信するのには不正使用された場合は、メールボックスがメールを送信するからブロックされている可能性があります。
1. メールボックスからのメール送信のブロックを解除するには、[ユーザー、ドメイン、またはスパムの電子メールを送信した後のブロック一覧から IP アドレスを削除する](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email )の手順に従います。

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>署名内のユーザー アカウントをブロックするオプションの手順 5。
> [!IMPORTANT]
> 署名でアクセスを再度有効にするは安全と思われるまで危険にさらされた疑いのあるアカウントをブロックすることができます。

1. Office 365 管理センターに移動します。
2. Office 365 管理センターでは、**ユーザー**を選択します。
3. ブロックは、使用する従業員を選択し、[**サインイン状態**の横の**編集**を、[ユーザー] ウィンドウで選択
4. **サインイン状態**ウィンドウで、**サインインをブロック**し、**保存**を選択します。 
5. Office 365 管理センターで、左のナビゲーション ウィンドウでは、**管理センター**を展開し、**交換**] を選択します。
6. Exchange 管理センターで、[に移動**受信者 > メールボックス**。
7. ユーザーを [ユーザーのプロパティ] ページで、[**モバイル デバイス**] をクリックして**Exchange ActivcSync を無効にして****デバイスの OWA を無効にして**両方に**yes**と答えます。
8. [**メール接続****を無効にして**解答を **[はい]** です。 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>手順 6 のオプション: すべての管理者の役割グループからセキュリティを侵害された疑いのあるアカウントを削除します。
> [!NOTE]
> アカウントがセキュリティで保護された後、管理者の役割グループのメンバーシップを復元できます。

1. グローバル管理者アカウントを使用して Office 365 の管理センターにサインインし、**アクティブなユーザー**を開きます。
2. 疑いのあるアカウントが侵害され、手動であるか確認して、アカウントに割り当てられているすべての管理者の役割があるかどうかを検索します。
3. **セキュリティと Compliace センター**を開きます。
4. [**アクセス許可**] をクリックします。
5. アカウントのうちいずれかのメンバーでは、疑いのある危険にさらされた場合に表示する役割グループを手動で確認します。 ある場合: a. がロール グループをクリックし、**ロール グループの編集**] をクリックします。 b. は、役割グループからユーザーを削除する**メンバーの選択**し、**編集**をクリックします。
6. **Exchange 管理センター**を開く
7. [**アクセス許可**] をクリックします。
8. アカウントのうちいずれかのメンバーでは、疑いのある危険にさらされた場合に表示する役割グループを手動で確認します。ある場合: a. がロール グループをクリックし、[**編集**] をクリックします。 b. 役割グループからユーザーを削除するのには、[**メンバー** ] セクションを使用します。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Pro の cybersecurity のように Office 365 をセキュリティで保護します。
Office 365 サブスクリプションのデータとユーザーを保護するために使用できるセキュリティ機能の強力なセットが付属します。 使用、 [Office 365 のセキュリティ ロードマップ: 最初の 30 日、90 日間での内外の優先順位のトップ](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)マイクロソフトが推奨する、Office 365 テナントのセキュリティに関するベスト プラクティスを実装します。
- 最初の 30 日以内に実行するタスクです。 即座に影響があり、影響の少ないのはこれらのユーザーにします。
- 90 日以内に実行するタスクです。これらにより、計画し実装しますが、セキュリティ体制を大幅に改善するに少し時間がかかります。
- 90 日が経過します。これらの拡張機能は、最初の 90 日間の作業でビルドします。

## <a name="see-also"></a>参照してください。
- [Office 365 のセキュリティのベスト プラクティス](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [Office 365 で Outlook のルールと ユーザー設定フォーム インジェクション攻撃の検出と修復を行う](detect-and-remediate-outlook-rules-forms-attack.md)