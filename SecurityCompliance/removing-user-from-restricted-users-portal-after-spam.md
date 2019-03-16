---
title: スパムメールの送信後に制限付きユーザーポータルからユーザーを削除する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 03/12/2019
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: ユーザーが、スパムとして分類された Office 365 から電子メールを継続的に送信した場合、それ以上メッセージを送信することはできません。
ms.openlocfilehash: 61d52ad1f25dc3767ad51da5b3a217ace59303ce
ms.sourcegitcommit: 9918411c01e962d5c67d53dd30a8a9c28c547397
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "30654554"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>スパムメールの送信後に制限付きユーザーポータルからユーザーを削除する

ユーザーが、スパムとして分類された Office 365 からの電子メールを継続的に送信する場合、送信中のメッセージの送信が制限されます。 ユーザーは、無効な送信者としてサービスに一覧表示され、次の状態を示す配信不能レポート (NDR) を受信します。

- 有効な送信者として認識されなかったため、メッセージを配信できませんでした。 最も一般的な理由は、メールアドレスがスパムを送信している可能性があり、組織外のメッセージを送信することが許可されなくなったためです。 詳細については、メール管理者に問い合わせてください。 リモートサーバーが ' 550 5.1.8 アクセスが拒否されましたが、正しくない送信送信者 ' が返されました

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報
<a name="sectionSection0"> </a>

予想所要時間 : 5 分
  
この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 必要なアクセス許可を確認するには、「 [Exchange Online の機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)」トピックの「スパム対策エントリ」を参照してください。

以下の手順はリモート PowerShell 経由でも実行することができます。Get-HostedOutboundSpamFilterPolicy コマンドレットを使用して設定を確認し、 Set-HostedOutboundSpamFilterPolicy を使用して送信スパム ポリシー設定を編集します。 制限を解除するには、BlockedSenderAddress コマンドレットを使用して、制限されたユーザーの一覧を取得し、BlockedSenderAddress を削除します。 Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>ブロックされた Office 365 メールアカウントの制限を削除する

このタスクは、「Office 365 Security & コンプライアンスセンター (SCC) で完了します。 SCC の詳細について[は、「Office 365 Security & コンプライアンスセンター」を参照](go-to-the-securitycompliance-center.md)してください。 これらの機能を実行するには、**組織の管理**または**セキュリティ管理者**の役割グループに所属している必要があります。 SCC の役割グループの詳細について[は、「Office 365 セキュリティ & コンプライアンスセンター」の「アクセス許可」を参照](permissions-in-the-security-and-compliance-center.md)してください。

1. office 365 のグローバル管理者特権を持つ職場または学校のアカウントを使用して、office 365 セキュリティ/コンプライアンスセンターにサインインし、左側の一覧で [**脅威の管理**] を展開し、[**レビュー**] を選択して、[制限あり] を選択します。 **ユーザー**。
    
    > [!TIP]
    > セキュリティ&amp; /コンプライアンスセンターの [制限された**ユーザー** ] ページ (以前のアクションセンター) に直接移動するには、次の URL を使用します。 >[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. このページには、組織外へのメールの送信をブロックされているユーザーの一覧が表示されます。  制限を解除するユーザーを見つけ、[**ブロックの解除**] をクリックします。

3. フライアウトは、送信が制限されているアカウントの詳細に進みます。 アカウントが実際に侵害された場合に備えて、適切な操作を実行していることを確認するために、推奨事項を実行する必要があります。 完了したら、[**次へ**] をクリックします。

4. 次の画面には、今後の侵害を防止するための推奨事項があります。 多要素認証 (MFA) を有効にし、パスワードを変更することは、優れた防衛策となります。 完了したら、[**ユーザーのブロック解除**] をクリックします。

5. **[はい]** をクリックして変更を確定します。

    > [!NOTE]
    > 制限が削除されるまでに最大30分かかる場合があります。 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>この問題が発生した場合に管理者に警告を出す

また、テナント管理者は、ユーザーがその他の送信メッセージの送信を制限していることを示す警告を受信します。 これは、すべてのテナントに対して提供され、[SCC alert policies] ページに一覧表示されます (「ユーザーがメールを送信して制限」というタイトルが付いています)。 警告の詳細について[は、「Office 365 Security & コンプライアンスセンターのアラートポリシー」](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)を参照してください。

## <a name="for-more-information"></a>関連情報

[侵害された電子メールアカウントへの対応](responding-to-a-compromised-email-account.md)

[ユーザーがメール通知の送信を制限していることを理解する](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)

[Office 365 Security & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)
