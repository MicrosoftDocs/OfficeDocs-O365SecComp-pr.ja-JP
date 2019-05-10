---
title: 未確認の送信者
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: フィッシングメッセージがメールボックスに到達しないようにするため、Outlook.com および web 上の Outlook では、送信者が本人であることを確認し、疑わしいメッセージを迷惑メールとしてマークします。
ms.openlocfilehash: 5d4315afb33964e7c466384366b7315287cf6298
ms.sourcegitcommit: d24f50347c671cf5d2d8afec2f80d37d18af8b5d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "33867847"
---
# <a name="unverified-sender"></a>未確認の送信者

フィッシングメッセージがメールボックスに到達しないようにするため、Outlook.com および web 上の Outlook では、送信者が本人であることを確認し、疑わしいメッセージを迷惑メールとしてマークします。

> [!IMPORTANT]
> メッセージがフィッシング詐欺としてマークされている場合、Outlook.com および web 上の Outlook では、ページの上部に警告が表示されますが、メッセージ内のすべてのリンクを開くことができます。

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a>受信トレイ内の疑わしいメッセージを特定するには、どうすればよいですか。

Web 上の Outlook.com および Outlook on the メッセージの送信者が識別できない場合、または送信者アドレスに表示されているものとは異なる場合のインジケーターを表示します。

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a>未確認の送信者の処理を受信するメッセージを管理する方法 

Office 365 をご利用のお客様の場合は、セキュリティ & コンプライアンスセンターを使用してこの機能を管理できます。 

- Office 365 Security & コンプライアンスセンターでは、テナント管理者は、フィッシングポリシーの下にあるスプーフィング対策保護を使用して、この機能をオンまたはオフにすることができます。 また、' Get-antiphishpolicy ' コマンドレットを使用して管理することもできます。 詳細については、「Office 365 のフィッシング対策保護」および「Get-antiphishpolicy」を参照してください。

    ![グラフィックインターフェイスで認証されていない送信者を編集する。](media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- 管理者が誤検知を識別し、送信者が未確認の送信者の処理を受信しないようにする場合は、次のいずれかの操作を実行して、スプーフィングインテリジェンススプーフィング許可リストに送信者を追加することができます。
        
    - スプーフィングインテリジェンスの洞察を通じてドメインペアを追加します。 詳細については、「チュートリアル: スプーフィングインテリジェンスの洞察」を参照してください。
                
    - Get-phishfilterpolicy コマンドレットを使用して、ドメインペアを追加します。 詳細については、「Get-phishfilterpolicy」および「Office のスプーフィング対策保護」を参照してください365

また、電子メールトランスポートルール (Etr)、安全なドメインリスト (スパム対策ポリシー)、安全な送信者リスト、またはユーザーがこのユーザーを自分のドメイン内の "安全な送信者" として設定している場合にも、未検証の送信者の処理は適用されません。ボックス.

### <a name="you-see-a--in-the-sender-image"></a>送信者の画像に '? ' が表示される

Outlook.com と web 上の Outlook が電子メール認証手法を使用して送信者の身元を確認できない場合は、送信者の写真に '? ' が表示されます。 

![メッセージが検証に合格しませんでした](media/message-did-not-pass-verification.jpg)

認証に失敗したすべてのメッセージが悪意のあるものであるとは限りません。 ただし、送信者を認識しない場合は、認証されないメッセージの操作について注意する必要があります。 または、通常は送信者の画像に '? ' が含まれていない送信者を認識したが、突然表示を開始した場合は、送信者がスプーフィングされているという署名になることがあります。

### <a name="the-senders-address-is-different-than-what-appears-in-the-from-address"></a>送信者のアドレスが差出人アドレスに表示されているものと異なる

多くの場合、メッセージに表示される電子メールアドレスは、差出人アドレスに表示されているものとは異なります。 場合によっては、送信者が実際のユーザーではない人物であることを phishers してみることをお勧めします。

Outlook.com と、web 上の Outlook で、送信者の実際のアドレスと差出人のアドレスのアドレスが異なることを検出すると、[経由] タグを使用して実際の送信者が表示されます。これには下線が付きます。

![未確認の送信者代替テキスト](media/unverified-sender-feature1.png)

この例では、送信側`suspicious.com`ドメインは認証されますが`unknown@contoso.com` 、送信者は差出人アドレスに入力します。

Via タグを持つすべてのメッセージが疑わしいとは限りません。 ただし、via タグが付いているメッセージを認識しない場合は、それとの対話に注意する必要があります。

Outlook.com と新しい Outlook on the web では、メッセージを開く必要なしに、メッセージ一覧の送信者の名前またはアドレスの上にカーソルを置くと、その電子メールアドレスを確認できます。

![OneDrive の使用を開始する](media/get-started-with-onedrive-message.png)

新しい Outlook on the web を使用しているかどうかを確認するには、どうすればよいですか。 次の例を参照してください。

![Outlook vs Office 365](media/outlook-vs-outlook365.png)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a>Outlook.com と web 上の Outlook で、'? ' および ' via ' プロパティを追加するために使用する条件とは何ですか。

送信者イメージの '? ' の場合: Outlook.com では、メッセージが SPF または DKIM 認証のいずれかを通過する必要があります。 詳細については、「 [Set UP SPF In office 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 」を参照して、スプーフィングを防止し、 [Dkim を使用して office 365 のカスタムドメインから送信される送信電子メールを検証](use-dkim-to-validate-outbound-email.md)します。

Via タグの場合: From アドレスのドメインが DKIM シグネチャまたは SMTP メールのドメインと異なる場合、Outlook.com は、この2つのフィールドのいずれかにドメインを表示します (DKIM シグネチャを優先します)。

### <a name="can-i-override-these-properties-with-ip-allows-exchange-transport-rule-allows-or-safe-senders"></a>これらのプロパティを IP で使用できる、Exchange トランスポートルールの許可、または安全な送信者に上書きすることはできますか。

これらのプロパティを無効にすることはできません。

### <a name="how-do-i-remove-these-properties"></a>これらのプロパティを削除するにはどうすればよいですか?

送信者の画像の '? ' の場合は、送信者として、SPF または DKIM のいずれかを使用してメッセージを認証する必要があります。

Via タグ: 送信者としての場合は、DKIM 署名のドメインまたは SMTP メールが、From アドレスのドメインと同じかサブドメインのものであることを確認する必要があります。

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a>Outlook.com と web 上の Outlook は、認証を通過しないすべてのメッセージに対してこのように表示されます。

必ずしもそうではありません。 Outlook.com および web 上の Outlook は、メッセージ内に送信者を認証するためのその他のプロパティがある場合があります。

## <a name="related-topics"></a>関連トピック

[Outlook.com メールアカウントを保護する](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[Outlook.com での迷惑行為、フィッシング、またはスプーフィングに対処する](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[Outlook on the web で迷惑メールおよびスパムをフィルター処理する](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
