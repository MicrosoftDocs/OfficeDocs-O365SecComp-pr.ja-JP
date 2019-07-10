---
title: Exchange Online でエラーコード 5.7.7 xx のメール配信の問題を修正する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/11/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Exchange Online でエラーコード 5.7.7 xx の電子メールの問題を解決する方法について説明します (テナントがメールの送信をブロックされた場合)。
ms.openlocfilehash: d55bc1f8a051a7f9932528a75aac8f1efa18911c
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599333"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a>Exchange Online でエラーコード 5.7.7 xx のメール配信の問題を修正する

このトピックでは、配信不能レポート (NDR、バウンスメッセージ、配信状態通知、または DSN とも呼ばれる) に状態コード 550 5.7.7 xx が表示される場合に実行できる操作について説明します。 この自動通知は、テナントが1つまたは別の方法で電子メールの送信を制限されている場合に表示されます。 これらのエラーコードは通常、705または750として表示されます。

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a>5.7.705: テナントがしきい値制限を超過しました: 知っておくべきこと

内部の送信者は、テナントが侵害された場合に、メールを送信しようとするたびにこの NDR を表示することができます。 これは通常、テナントからのトラフィックの大部分が疑わしいと検出され、テナントの送信機能が禁止されている場合に occus します。 これは、ユーザーが Office 365 から大量のバルクメールを送信した場合にも発生する可能性があります。 サービスの説明に記載されているように、正当なバルク商用電子メール (たとえば、顧客向けのニュースレター) を送信する必要がある Exchange Online のお客様は、これらのサービスに特化したサードパーティのプロバイダーを使用する必要があります。

テナントとしてユーザーが特定の数の疑わしいメールをサービス経由で送信すると、その問題が解決されるまで、すべてのユーザーがメールを送信できなくなります。 ユーザーは、次の状態を示す配信不能レポート (NDR) を受信します。

- 550 5.7.705 アクセスが拒否されました、テナントはしきい値を超えています

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a>5.7.750: 登録が解除されるドメインの電子メール制限: 理解しておくべき情報

Office 365 では、テナントが Exchange Online Protection (EOP) を介して一部のメッセージを中継できます。 サポートされている例の1つは、ユーザーが Office 365 メールボックスを持っていて、誰かが電子メールを送信したが、電子メール転送がユーザーの外部メールボックスに戻るように構成されている場合です。 これは、学生が個人用の電子メールインターフェイスを利用していても、学校に関連するメールを受信したい教育環境で最も一般的です。 もう1つの例として、顧客がハイブリッドシナリオで、EOP からメールを送信するオンプレミスサーバーがある場合があります。

### <a name="problems-with-unregistered-domains"></a>未登録のドメインに関する問題

この問題は、オンプレミスのサーバーが侵害され、EOP の大量のスパムを中継してしまうことにあります。 ほとんどの場合、右コネクタはセットアップされていますが、未登録のドメイン (プロビジョニング解除されたドメインとも呼ばれる) からメールを送信しています。 Office 365 では、登録されていないドメインからのメールの送信を許可していますが、の送信を計画している各ドメインの管理センターで承認済みドメインを構成する必要があります。

いったん侵害されると、テナントは未登録のドメインの送信メールを送信できなくなります。 ユーザーは、次の状態を示す配信不能レポート (NDR) を受信します。

- 550 5.7.750 サービスは利用できません。 クライアントが未登録のドメインからの送信をブロックしました

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a>再送信のためにテナントのブロックを解除する方法

テナントが電子メールの送信をブロックされる場合は、次のようないくつかの作業を行う必要があります。

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
