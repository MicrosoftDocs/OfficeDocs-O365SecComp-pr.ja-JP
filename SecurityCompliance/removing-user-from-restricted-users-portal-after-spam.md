---
title: 迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 03/12/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: ユーザーが、スパムとして分類された Office 365 から電子メールを継続的に送信した場合、それ以上メッセージを送信することはできません。
ms.openlocfilehash: 3e05b250d5a3cdca79c7cf494b84be02ce3ecdc9
ms.sourcegitcommit: 5a93c2f3df35d06a59a7fbaff5c91f7afde11781
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857627"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する

ユーザーが Office 365 からスパムとして分類された電子メールを継続的に送信すると、メールの送信が制限されますが、受信は可能になります。 ユーザーは、無効な送信者としてサービスに一覧表示され、次の状態を示す配信不能レポート (NDR) を受信します。

> "有効な送信者として認識されなかったため、メッセージを配信できませんでした。 最も一般的な理由は、電子メールアドレスがスパム送信の疑いがあり、電子メールの送信が許可されていないためです。  詳細については、メール管理者に問い合わせてください。 リモートサーバーが ' 550 5.1.8 アクセス拒否、正しくない送信送信者を返しました。 "

## <a name="what-do-you-need-to-know-before-you-begin"></a>事前に必要な知識
<a name="sectionSection0"> </a>

予想所要時間 : 5 分
  
この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 必要なアクセス許可を確認するには、「 [Exchange Online の機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)」トピックの「スパム対策エントリ」を参照してください。

以下の手順はリモート PowerShell 経由でも実行することができます。Get-HostedOutboundSpamFilterPolicy コマンドレットを使用して設定を確認し、 Set-HostedOutboundSpamFilterPolicy を使用して送信スパム ポリシー設定を編集します。 制限を解除するには、BlockedSenderAddress コマンドレットを使用して、制限されたユーザーの一覧を取得し、BlockedSenderAddress を削除します。 Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>ブロックされた Office 365 メールアカウントの制限を削除する

セキュリティ & コンプライアンスセンター (SCC) でこのタスクを完了します。 SCC の詳細について[は、「Security & コンプライアンスセンター」を参照](go-to-the-securitycompliance-center.md)してください。 これらの機能を実行するには、**組織の管理**または**セキュリティ管理者**の役割グループに所属している必要があります。 SCC 役割グループの詳細について[は、「セキュリティ & コンプライアンスセンター」の「アクセス許可」を参照](permissions-in-the-security-and-compliance-center.md)してください。

1. Office 365 のグローバル管理者特権を持つ職場または学校のアカウントを使用して、Office 365 セキュリティ/コンプライアンスセンターにサインインし、左側の一覧で [**脅威の管理**] を展開し、[**レビュー**] を選択して、[制限あり] を選択します。 **ユーザー**。
    
    > [!TIP]
    > セキュリティ&amp; /コンプライアンスセンターの [制限された**ユーザー** ] ページ (以前のアクションセンター) に直接移動するには、次の URL を使用します。 >[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. このページには、電子メールの送信をブロックされているユーザーの一覧が表示されます。  制限を削除するユーザーを検索し、[**ブロック解除**] を選択します。

3. フライアウトは、送信が制限されているアカウントの詳細に進みます。 アカウントが実際に侵害された場合に備えて、適切な操作を実行していることを確認するために、推奨事項を実行する必要があります。 完了したら、[**次へ**] をクリックします。

4. 次の画面には、今後の侵害を防止するための推奨事項があります。 多要素認証 (MFA) を有効にし、パスワードを変更することは、優れた防衛策となります。 完了したら、[**ユーザーのブロック解除**] をクリックします。

5. **[はい]** をクリックして変更を確定します。

    > [!NOTE]
    > 制限が削除されるまでに30分以上かかる場合があります。 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>この問題が発生した場合に管理者に警告を出す

[ユーザーによる電子メール送信からの制限] 通知は、Office 365 セキュリティ & コンプライアンスのアラートポリシーのページの下にあるポリシーとして使用できます。 これは以前の送信スパムポリシーでしたが、Office 365 通知プラットフォームにネイティブになっています。 警告の詳細について[は、「セキュリティ & コンプライアンスセンター」のアラートポリシー](alert-policies.md)にアクセスしてください。

> [!IMPORTANT]
> 警告が機能するには、監査ログの検索を有効にする必要があります。 詳細については、「 [Office 365 監査ログの検索をオンまたはオフ](turn-audit-log-search-on-or-off.md)にする方法」を参照してください。

この通知のポリシーは既定のものであり、すべての Office 365 テナントに付属しており、設定する必要はありません。 ユーザーがメールの送信を制限されている場合に常に警告が発生すると、これは重要度の高いアラートとして扱われ、構成された TenantAdmins グループが電子メールで送信されます。 管理者は、SCC ポータルの下にあるアラートにアクセスすることで、この警告が発生したときに通知されるグループを更新することができます。ユーザーがメールの送信を制限されて > ユーザーに通知 > アラートポリシー > ます。

通知を編集して、次の操作を行うことができます。
- メール通知をオン/オフにする
- 必要な受信者を電子メールで送信する
- 1日に受信する通知を制限する

## <a name="for-more-information"></a>関連情報

[侵害された電子メールアカウントへの対応](responding-to-a-compromised-email-account.md)

[ユーザーがメール通知の送信を制限していることを理解する](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)

[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)

[セキュリティ & コンプライアンスセンターのアラートポリシー](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)
