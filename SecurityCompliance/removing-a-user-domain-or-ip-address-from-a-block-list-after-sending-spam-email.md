---
title: ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
description: 'スパムとして分類されている Office 365 からメール メッセージをユーザーが送り続ける場合、メッセージを送信しないようブロックされます。 '
ms.openlocfilehash: 3ffd8b65d6994699093237e9f9a0a3aaa802f5e2
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223086"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する

ユーザーが、スパムとして分類された Office 365 から電子メールメッセージを継続的に送信した場合、それ以上メッセージを送信することはブロックされます。ユーザーは、無効な送信者としてサービスに一覧表示され、次の状態を示す配信不能レポート (NDR) を受信します。

- 有効な送信者として認識されなかったため、メッセージを配信できませんでした。最も一般的な理由は、メールアドレスがスパムを送信している可能性があり、組織外のメッセージを送信することが許可されなくなったためです。詳細については、メール管理者に問い合わせてください。 リモートサーバーが ' 550 5.1.8 アクセスが拒否されましたが、正しくない送信送信者 ' が返されました

また、テナント管理者は、ユーザーがその他の送信メッセージの送信を制限していることを示す警告を受信します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報
<a name="sectionSection0"> </a>

予想所要時間 : 5 分
  
この手順を実行する前に、アクセス許可を割り当てる必要があります。必要なアクセス許可を確認するには、「 [Exchange Online の機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)」トピックの「スパム対策エントリ」を参照してください。

次の手順は、リモート PowerShell を使用して実行することもできます。制限を解除するには、BlockedSenderAddress コマンドレットを使用して、制限されたユーザーの一覧を取得し、BlockedSenderAddress を削除します。Windows PowerShell を使用して exchange online に接続する方法については、「 [exchange online powershell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>ブロックされた Office 365 メールアカウントの制限を削除する

このタスクは、「Office 365 Security & コンプライアンスセンター (SCC) で完了します。SCC の詳細について[は、「Office 365 Security & コンプライアンスセンター」を参照](go-to-the-securitycompliance-center.md)してください。これらの機能を実行するには、**組織の管理**または**セキュリティ管理者**の役割グループに所属している必要があります。SCC の役割グループの詳細について[は、「Office 365 セキュリティ & コンプライアンスセンター」の「アクセス許可」を参照](permissions-in-the-security-and-compliance-center.md)してください。

1. office 365 のグローバル管理者特権を持つ職場または学校のアカウントを使用して、office 365 セキュリティ/コンプライアンスセンターにサインインし、左側の一覧で [**脅威の管理**] を展開し、[**レビュー**] を選択して、[制限あり] を選択します。 **ユーザー**。
    
    > [!TIP]
    > セキュリティ&amp; /コンプライアンスセンターの [制限された**ユーザー** ] ページ (以前のアクションセンター) に直接移動するには、次の URL を使用します。 >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. このページには、組織外へのメールの送信をブロックされているユーザーの一覧が表示されます。 制限を解除するユーザーを見つけ、[**ブロックの解除**] をクリックします。

3. **[はい]** をクリックして変更を確定します。 
    
> [!NOTE]
> テナント管理者がアカウントのブロックを解除できる回数には制限があります。ユーザーの制限を超えている場合は、エラーメッセージが表示されます。その後、サポートに連絡して、ユーザーのブロックを解除する必要があります。<br/><br/> ユーザーがブロック解除されるまで最大で1時間かかる場合があります。
  
## <a name="third-party-block-lists"></a>サード パーティのブロック リスト

Exchange Online Protection では、スパムフィルター処理における意思決定に役立てるために、サードパーティのブロックリストも使用します。ユーザー、web サイト、ドメイン、および IP アドレスを、スパムメッセージに表示するためだけにブロックリストに追加できます。Office 365 管理者は、サードパーティのリストプロバイダーが所有している場合は、それらのオブジェクトを削除する必要があります。

> [!NOTE]
> office 365 の外部のユーザーが office 365 アカウントにメッセージを送信できない場合は、そのアカウントが外部の受信拒否リストに含まれている可能性があります。Office 365 の外部のユーザーは、[セルフサービス](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)の区切りポータルを使用して自分自身を削除しようとすることができます。 

## <a name="for-more-information"></a>関連情報

[侵害された電子メールアカウントへの対応](responding-to-a-compromised-email-account.md)

[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)
  
[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)

[Office 365 Security & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)

  

