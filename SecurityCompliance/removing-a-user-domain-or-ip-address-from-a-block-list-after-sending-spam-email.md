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
ms.openlocfilehash: 6f6f4504a9c79463aadc21f2eaeadcd769e8b151
ms.sourcegitcommit: 03b9221d9885bcde1cdb5df2c2dc5d835802d299
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29614401"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する

ユーザーは、継続的に迷惑メールとして分類されている Office 365 の電子メール メッセージを送信する場合は、そのメッセージの送信がブロックされます。ユーザーが不正な送信の送信元としてサービスに表示され、配信不能レポート (NDR) を示すが表示されます。

- 有効な送信者として認識していなかったために、メッセージを配信できませんでした。このエラーの最も一般的な理由は、あなたの電子メール アドレスがスパムを送信する可能性がある場合、そのことができなく、組織外へメッセージを送信するには。について、メール管理者に問い合わせてください。 550 5.1.8 アクセス拒否、送信者送信リモート サーバーから返されました

テナント管理者以上の送信メッセージを送信することからユーザーを制限されていることを示す警告を受け取ります。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報
<a name="sectionSection0"> </a>

予想所要時間 : 5 分
  
このプロシージャまたはプロシージャを実行する前にアクセス許可を割り当てる必要があります。必要なアクセス許可を表示するには、エントリを参照"スパム対策[機能のアクセス許可を Exchange Online で](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)トピックです。

リモート PowerShell を使用して次の手順を実行できます。Get BlockedSenderAddress コマンドレットを使用して、制限されたユーザーとの制限を削除する削除-BlockedSenderAddress のリストを取得します。Exchange Online に接続する Windows PowerShell を使用する方法については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)を参照してください。

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>ブロックされている Office 365 の電子メール アカウントの制限を削除します。

Office 365 のセキュリティ & コンプライアンス センター (SCC) では、このタスクを完了するとします。SCC の詳細については、 [Office 365 のセキュリティ & コンプライアンス センターに移動](go-to-the-securitycompliance-center.md)をします。これらの関数を実行するために**組織の管理**または**セキュリティ管理者**の役割グループにする必要があります。ソース コード管理の役割グループの詳細については[Office 365 のセキュリティ & コンプライアンス センターでのアクセス許可に移動](permissions-in-the-security-and-compliance-center.md)をしてください。

1. 職場または学校を Office 365 のセキュリティやコンプライアンス センターにサインインし、**脅威の管理**を展開し、左側のボックスの一覧で、**レビュー**をクリックし選択**制限付きの Office 365 グローバル管理者特権を持つアカウントを使用してください。ユーザー**。
    
    > [!TIP]
    > 直接ページに移動する、**制限付きユーザー** (アクション センターと呼ばれていました)、セキュリティで&amp;コンプライアンス センターでは、この URL を使用して: _gt[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. このページから別の組織にメールを送信するブロックされているユーザーの一覧が含まれます。 上の制限を削除し、たいをクリックし、**ブロックを解除する**にユーザーを検索するには。

3. **[はい]** をクリックして変更を確定します。 
    
> [!NOTE]
> テナント管理者がアカウントのブロックを解除できる回数に制限があります。ユーザーの制限を超えた場合は、エラー メッセージが表示されます。ユーザーのブロックを解除するためのサポートに連絡する必要があります。</br></br> ユーザーがブロックされる前に、最大 1 時間かかる場合があります。
  
## <a name="third-party-block-lists"></a>サード パーティのブロック リスト

また、Exchange のオンライン保護は、スパム フィルターで決定を下すためにサード パーティのブロック リストを使用します。ブロックのスパム メッセージに表示されるリストには、ユーザー、web サイト、ドメイン、および IP アドレスを追加できます。、Office 365 管理者としては、これらのオブジェクトに属している場合は、サード ・ パーティ製リスト プロバイダーからの削除を取得するください。

> [!NOTE]
> Office 365 アカウントに他のユーザーが Office 365 の外部メッセージを送信できません、ブロックされた外部の送信者の一覧に自分のアカウント可能性があります。Office 365 の外部のユーザーは、自分を[delisting のセルフ サービス ポータル](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)を使用して削除を試行できます。 

## <a name="for-more-information"></a>詳細情報

[感染した電子メール アカウントへの対応](responding-to-a-compromised-email-account.md)

[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)
  
[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)

[Office 365 のセキュリティ & コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)

  

