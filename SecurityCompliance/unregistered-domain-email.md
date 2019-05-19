---
title: 未登録のドメインメール
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/17/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 登録されていないドメインの電子メールを大量に送信する場合は、メールがブロックされる危険を実行します。 詳細については、この記事をお読みください。
ms.openlocfilehash: 207b71ab7e144af9709e7485d61c936e07271a11
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156299"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a>未登録のドメインメール: 知っておくべき情報

Office 365 では、テナントが Exchange Online Protection (EOP) を介して一部のメッセージを中継できます。 サポートされている例の1つは、ユーザーが Office 365 メールボックスを持っていて、誰かが電子メールを送信したが、電子メール転送がユーザーの外部メールボックスに戻るように構成されている場合です。 これは、学生が個人用の電子メールインターフェイスを利用していても、学校に関連するメールを受信したい教育環境で最も一般的です。 もう1つの例として、顧客がハイブリッドシナリオで、EOP からメールを送信するオンプレミスサーバーがある場合があります。

## <a name="problems-with-unregistered-domains"></a>未登録のドメインに関する問題

この問題は、オンプレミスのサーバーが侵害され、EOP の大量のスパムを中継してしまうことにあります。 ほとんどの場合、右コネクタはセットアップされていますが、未登録のドメイン (プロビジョニング解除されたドメインとも呼ばれる) からメールを送信しています。 Office 365 では、登録されていないドメインからのメールの送信を許可していますが、の送信を計画している各ドメインの管理センターで承認済みドメインを構成する必要があります。

いったん侵害されると、テナントは未登録のドメインの送信メールを送信できなくなります。 ユーザーは、次の状態を示す配信不能レポート (NDR) を受信します。

- 550 5.7.750 サービスは利用できません。 クライアントが未登録のドメインからの送信をブロックしました

## <a name="unblocking-tenant-in-order-to-send-again"></a>再送信するためにテナントのブロックを解除する

未登録のドメインからの送信がブロックされた場合は、いくつかの作業を行う必要があります。

1. Microsoft 365 管理センターですべてのドメインを登録していることを確認してください。 詳細については、[こちら](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)を参照してください。

2. 異常なコネクタを探します。 悪意のある俳優は、多くの場合、スパムを送信するために Office 365 テナントに新しい受信コネクタを作成します。 コネクタの確認の詳細については、[こちら](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)を参照してください。 

3. オンプレミスのサーバーをロックし、侵害されないようにします。

> [!TIP]
> ここでは、特にサードパーティ製のサーバーの場合に、多くの要因が関係しています。 いずれにしても、サーバーから発信されたすべてのメールが正当であることを確認できるようにする必要があります。

4. 完了したら、Microsoft サポートに連絡して、登録されていないドメインから送信されないようにテナントのブロック解除を取得するように依頼する必要があります。  エラーコードを提供することは役に立ちますが、環境がセキュリティで保護されており、スパムが再送信されないことを証明する必要があります。 サポートケースを開く方法については、[こちら](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)を参照してください。
  
## <a name="for-more-information"></a>関連情報

[Office 365 メールのスパム対策保護](anti-spam-protection.md)

[Office 365 でのメール配信不能レポート](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[メールボックスへの電子メールの転送を構成する](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Office 365 を使用してメールを送信するように多機能デバイスまたはアプリケーションをセット アップする方法](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[Exchange Online で承認済みドメインを管理](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)します。
