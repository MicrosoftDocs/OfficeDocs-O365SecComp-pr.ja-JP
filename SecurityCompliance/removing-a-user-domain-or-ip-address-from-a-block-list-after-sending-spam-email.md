---
title: ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/05/2018
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
ms.openlocfilehash: 6665c405c62f75b77e7898419ebcfbc1c8c20f4c
ms.sourcegitcommit: 7b85c22fc85ec19e4b44a07e91bfa9ade768185a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "23998611"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する

ユーザーは、継続的に迷惑メールとして分類されている Office 365 の電子メール メッセージを送信する場合は、そのメッセージの送信がブロックされます。ユーザーが不正な送信の送信元としてサービスに表示され、配信不能レポート (NDR) を示すが表示されます。

- 有効な送信者として認識していなかったために、メッセージを配信できませんでした。このエラーの最も一般的な理由は、あなたの電子メール アドレスがスパムを送信する可能性がある場合、そのことができなく、組織外へメッセージを送信するには。について、メール管理者に問い合わせてください。 550 5.1.8 アクセス拒否、送信者送信リモート サーバーから返されました

送信スパム ポリシー設定を構成するには、電子メールを送信することから、Office 365 ユーザーがブロックされたときに通知を取得するためです。ユーザーのメールボックスで問題が解決された後は、その送信者のブロックを削除できます。
  
## <a name="unblock-a-blocked-office-365-email-account"></a>ブロックされている Office 365 メール アカウントのブロックを解除する

Office 365 のセキュリティとコンプライアンス センター (SCC) では、このタスクを完了するとします。SCC の詳細については、 [Office 365 のセキュリティとコンプライアンスの中心に移動](go-to-the-securitycompliance-center.md)をします。

1. 職場または学校を Office 365 のセキュリティやコンプライアンス センターにサインインし、**脅威の管理**を展開し、左側のボックスの一覧で、**レビュー**をクリックし選択**制限付きの Office 365 グローバル管理者特権を持つアカウントを使用してください。ユーザー**。
    
    > [!TIP]
    > セキュリティで**制限されたユーザー**のページに直接移動するのには&amp;コンプライアンス センターでは、この URL を使用します >。[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. このページから別の組織にメールを送信するブロックされているユーザーの一覧が含まれます。 上の制限を削除し、たいをクリックし、**ブロックを解除する**にユーザーを検索するには。

3. **[はい]** をクリックして変更を確定します。 
    
> [!NOTE]
> テナント管理者がアカウントのブロックを解除できる回数に制限があります。ユーザーの制限を超えた場合は、エラー メッセージが表示されます。ユーザーのブロックを解除するためのサポートに連絡する必要があります。
  
## <a name="third-party-block-lists"></a>サード パーティのブロック リスト

また、Exchange のオンライン保護は、スパム フィルターで決定を下すためにサード パーティのブロック リストを使用します。ブロックのスパム メッセージに表示されるリストには、ユーザー、web サイト、ドメイン、および IP アドレスを追加できます。、Office 365 管理者としては、これらのオブジェクトに属している場合は、サード ・ パーティ製リスト プロバイダーからの削除を取得するください。内のリンクを使用して、各サード パーティに連絡し、指示に従って操作するテーブルの下。

|**リスト名**|**リスト削除ポータル**|**詳細情報**|
|:-----|:-----|:-----|
|URIBL  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[URIBL web サイト](https://uribl.com/) <br/> |
|SURBL  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[SURBL URI の評判のデータの概要](http://www.surbl.org/) <br/> |
|Spamhaus   <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[DNSBL フィルタ リングを理解します。](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|invaluement  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[invaluement スパム対策リスト](http://dnsbl.invaluement.com/) <br/> |
|Phishtank  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[PhishTank のよく寄せられる質問](https://www.phishtank.com/faq.php) <br/> |

> [!NOTE]
> Office 365 アカウントに他のユーザーが Office 365 の外部メッセージを送信できません、ブロックされた外部の送信者の一覧に自分のアカウント可能性があります。Office 365 の外部のユーザーは、自分を[delisting のセルフ サービス ポータル](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)を使用して削除を試行できます。 

## <a name="for-more-information"></a>詳細情報

[感染した電子メール アカウントへの対応](responding-to-a-compromised-email-account.md)

[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)
  
[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)

  

  

