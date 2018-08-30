---
title: ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/20/2018
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
ms.openlocfilehash: 87b7083fe1345a15ea582f12a5b0d417bbe6b568
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002603"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>ユーザー、ドメイン、または IP アドレスをスパム電子メール送信後のブロック一覧から削除する

スパムとして分類されている Office 365 からメール メッセージをユーザーが送り続ける場合、メッセージを送信しないようブロックされます。  
  

送信者がメール メッセージを送信しないようブロックされると、配信不能レポート (NDR つまりメールはメッセージの送信に失敗した) を受信します。このレポートは、ブロックを解除するために取る必要がある手順に関する特定の情報を提供します。
  
サービスが特定の web サイト、ドメイン、個々 のユーザーがブロックされ、だけでなく、IP アドレスをブロックすることもできます。場合によっては、ドメインまたは web サイト追加できますブロック リストに迷惑メール メッセージに表示されているからといって。として Office 365 の管理者、ユーザー、web サイト、ドメイン、およびサード パーティのブロック リストから削除する IP アドレスを取得しようことができます。このトピックの下部にあるテーブルのリンクを使用して、各サード パーティに連絡し、指示に従って操作します。場合は、Office 365 アカウントに他のユーザーが Office 365 の外部メッセージを送信できません、自分のアカウント可能性がありますが、最終的に外部の受信拒否リストに。Office 365 の外部のユーザーは、自分を[delisting のセルフ サービス ポータル](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx)を使用して受信拒否リストから削除を試行できます。
  
スパムとして分類されているメールを送信しないよう Office 365 ユーザーがブロックされたときに、通知を受け取るよう送信スパム設定を構成できます。ユーザーのメールボックスの問題が解決されると、その送信者のブロックを解除できるようになります。
  
## <a name="unblock-a-blocked-office-365-email-account"></a>ブロックされている Office 365 メール アカウントのブロックを解除する

Exchange 管理センター (EAC) では、このタスクを完了するとします。EAC の詳細については、 [Exchange 管理センターでは、Exchange オンライン保護](exchange-admin-center-in-exchange-online-protection-eop.md)を確認します。 
  
> [!NOTE]
> Exchange Online の EAC 以外では、アクション センターは表示されません。 
  
1. EAC で**の保護**に移動\>**アクション センター**です。
    
    ![Exchange 管理センターのアクション センターに移動します。](media/9bbf0844-7b34-4a86-a2b7-8c7e9c8519a3.png)
  
2. **[検索]** アイコンを選択し、ブロックされているユーザーの SMTP アドレスを入力します。 
    
    ![アクション センターでブロックされているユーザーを検索する](media/f931b5a0-7115-4d95-9f6f-b403436031ba.png)
  
3. 説明ウィンドウの **[アカウントのブロック解除]** をクリックします。 
    
    ![アクション センターでユーザーのブロックを解除する](media/c5d5b1b9-8416-45aa-9631-881e94d1d056.png)
  
4. **[はい]** をクリックして変更を確定します。 
    
> [!NOTE]
> テナント管理者がアカウントのブロックを解除できる回数には制限があります。ユーザーに関して制限を超えると、エラー メッセージが表示されます。ユーザーのブロックを解除するには、サポートにお問い合わせください。 
  
## <a name="third-party-block-lists"></a>サード パーティのブロック リスト

|**リスト名**|**リスト削除ポータル**|**詳細情報**|
|:-----|:-----|:-----|
|URIBL  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[URIBL web サイト](https://uribl.com/) <br/> |
|SURBL  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[SURBL URI の評判のデータの概要](http://www.surbl.org/) <br/> |
|Spamhaus   <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[DNSBL フィルタ リングを理解します。](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|invaluement  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[invaluement スパム対策リスト](http://dnsbl.invaluement.com/) <br/> |
|Phishtank  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[PhishTank のよく寄せられる質問](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> また、Exchange のオンライン保護は、スパムのフィルタ リングのサード パーティのブロック リストを使用します。 
   
## <a name="for-more-information"></a>詳細情報

[送信スパム ポリシーを構成する](configure-the-outbound-spam-policy.md)
  
[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)

[リストから除外のポータルを使って Office 365 の受信拒否リストから自分自身を削除する](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  

