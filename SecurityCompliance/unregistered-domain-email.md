---
title: 登録されていないドメインの電子メール
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: 大量のドメインが登録されていない電子メールを送信する場合は、ブロックを取得する電子メールのリスクを実行します。詳細については、この資料を参照してください。
ms.openlocfilehash: f2b60f492197bf0dadb702a1c3f184c2d7e56bf1
ms.sourcegitcommit: 7b85c22fc85ec19e4b44a07e91bfa9ade768185a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "23998601"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a>登録されていないドメインのメール: に必要なものを知る

Office 365 は、Exchange オンライン保護 (EOP) では、いくつかのメッセージを中継するテナントのことができます。サポートされている 1 つの例としては、ユーザーが Office 365 メールボックスを持って、電子メールを送信して外部の人がされるようにバックアップを外部メールボックスのユーザーの電子メールの転送が構成されているときになります。これは、受講者が自分の個人的な電子メールのインタ フェースを活用して、、まだ学校に関連する電子メールを取得する必要な教育環境で最も一般的です。別の例お客様ハイブリッド シナリオでは、EOP から電子メールを送信する、オンプレミスのサーバーがある場合です。

## <a name="problems-with-unregistered-domains"></a>登録されていないドメインの問題

オンプレミスのサーバーが侵害され、大量の EOP をスパムの中継を終了するときに問題があります。ほとんどすべての場合、右側のコネクタに設定されてですが、登録されていないとも呼ばれる準備が解除された、ドメインから送信される電子メール。Office 365 は適度な未登録のドメインからのメールを許可するを送信するように計画する各ドメインの管理センターで、承認済みドメインを構成する必要があります。

危険にさらされた後のテナントされなくなります登録されていないドメインからの送信メールを送信します。ユーザーは配信不能レポート (NDR) を示すが表示されます。

- 550 5.7.750 サービスを利用できません。クライアントが登録されていないドメインからの送信は禁止

## <a name="unblocking-tenant-in-order-to-send-again"></a>再送信するためにブロック解除のテナント

登録されていないドメインから送信するためにブロックされる場合に実行する必要があるいくつかの方法があります。

1. すべてのドメインを Office 365 の管理センターで登録することを確認します。詳細についてを参照して[ここで](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。

2. オンプレミスのサーバーをロックダウンし、侵害がないことを確認します。多くの要因関係するここでは、これらは、サード パーティのサーバーがそのサーバーをそのまますべてのメールが正当なことを確認できるようにする必要が場合に特に。

終わったら、マイクロソフト サポートに連絡し、登録されていないドメインから再送信をブロック解除、テナントを取得するよう要求する必要があります。 エラー コードを提供することをお勧め、ですが、お客様の環境がセキュリティで保護されていると、迷惑メールは再送信されないことを証明する必要があります。詳細についてを参照して[ここで](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)。
  
## <a name="for-more-information"></a>詳細情報

[Office 365 の電子メールのスパム対策保護](anti-spam-protection.md)

[Office 365 の電子メールの配信不能レポート](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[メールボックスへの電子メールの転送を構成する](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Office 365 を使用してメールを送信するように多機能デバイスまたはアプリケーションをセット アップする方法](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[管理許可ドメイン Exchange オンライン](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
