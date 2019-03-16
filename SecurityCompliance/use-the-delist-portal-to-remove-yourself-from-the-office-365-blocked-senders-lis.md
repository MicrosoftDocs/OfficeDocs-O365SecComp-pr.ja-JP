---
title: リストから除外のポータルを使って、Office 365 の受信拒否リストから自分自身を削除する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 4/18/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
description: Office 365 にメール アドレスがある受信者にメールを送信しようとするときに、エラー メッセージが返される場合があります。エラー メッセージを受信しないようにするには、リストから除外のポータルを使って、Office 365 の受信拒否リストから自分自身を削除します。
ms.openlocfilehash: 2d01d1637ddf1a4666d580b09e59fc6baa12784e
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "30647307"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a>リストから除外のポータルを使って、Office 365 の受信拒否リストから自分自身を削除する

Office 365 にメール アドレスがある受信者にメールを送信しようとするときに、エラー メッセージが返される場合があります。エラー メッセージを受信しないようにするには、リストから除外のポータルを使って、Office 365 の受信拒否リストから自分自身を削除します。
  
## <a name="what-is-the-office-365-blocked-senders-list"></a>Office 365 の 受信拒否リストとは何か

Microsoft は、受信拒否リストを使って、スパム、スプーフィング、フィッシング攻撃からお客様を保護しています。お客様のメール サーバーの IP アドレス、つまりお客様のメール サーバーがインターネット上でそれ自身を識別するために使うアドレスが、さまざまな理由によって Office 365 への潜在的な脅威としてタグ付けされる場合があります。Office 365 がその IP アドレスを受信拒否リストに追加すると、それ以降、データセンターを介してその IP アドレスと他のユーザーはまったく通信できなくなります。
  
メール メッセージに対して、次のようなエラーが含まれた応答を受信する場合、お客様は受信拒否リストに追加されています。
  
> 550 5.7.606-649 アクセス拒否、禁止された送信 ip [_ip address_]、このリストからの削除を要求するhttps://sender.office.com/には、にアクセスして、指示に従ってください。 詳細については、「 [Office 365 で配信不能レポートを送信](http://go.microsoft.com/fwlink/?LinkID=526653)する」を参照してください。
  
ここで、 _IP address_ は、メール サーバーを稼働しているコンピューターの IP アドレスです。 
  
### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Office 365 のリストから除外のポータルを使って、受信拒否リストから自分自身を除外するには

1. Web ブラウザーで、[https://sender.office.com](https://sender.office.com) に移動します。
    
2. ページ上の指示に従います。エラー メッセージを受信したメール アドレス、エラー メッセージで特定されている IP アドレスを使っていることを確認してください。1 回のアクセスにつき、1 つのメール アドレス、1 つの IP アドレスのみ入力できます。
    
3. [ **保存**] をクリックします。
    
    ポータルは、指定したメール アドレスにメールを送信します。 電子メールは次のようになります![。リストから除外ポータルを通じて要求を送信したときに受信された電子メールのスクリーンショット](media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)
  
4. リストから除外のポータルから受信したメールの中にある確認のリンクをクリックします。
    
    これで、リストから除外のポータルに戻ります。
    
5. リストから除外のポータルで **[IP をリストから除外]** をクリックします。
    
    IP アドレスが受信拒否リストから削除されると、その IP アドレスからのメール メッセージが、Office 365 を使用する受信者に配信されるようになります。その IP アドレスから送信されるメールに不正や悪意のある内容が含まれていないことを確認してください。そのような内容が含まれていると、IP アドレスが再びブロックされる可能性があります。
    
    > [!NOTE]
    > 制限が削除されるまでに最大で1時間かかる場合があります。
