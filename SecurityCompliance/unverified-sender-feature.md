---
title: 未確認の送信者
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/11/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: フィッシングメッセージがメールボックスに到達しないようにするため、Outlook.com および web 上の Outlook では、送信者が本人であることを確認し、疑わしいメッセージを迷惑メールとしてマークします。
ms.openlocfilehash: 233474dbfff430be8dd95d513adeb257bb26c5c7
ms.sourcegitcommit: 9e2df36b05a2c93ce2629a7a5eda8f44159d114d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "35628510"
---
# <a name="unverified-sender"></a>未確認の送信者

> [!NOTE] 
> これらの更新プログラムは現在ロールアウトされており、すべてのユーザーに対してまだ使用できない場合があります。

フィッシングメッセージがメールボックスに到達しないようにするため、Outlook.com および web 上の Outlook では、送信者が本人であることを確認し、疑わしいメッセージを迷惑メールとしてマークします。

> [!IMPORTANT]
> メッセージがフィッシング詐欺としてマークされている場合、Outlook.com および web 上の Outlook では、ページの上部に警告が表示されますが、メッセージ内のすべてのリンクを開くことができます。

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a>受信トレイ内の疑わしいメッセージを特定するには、どうすればよいですか。

Web 上の Outlook.com および Outlook on the メッセージの送信者が識別できない場合、または送信者アドレスに表示されているものとは異なる場合のインジケーターを表示します。

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a>未確認の送信者の処理を受信するメッセージを管理する方法 

Office 365 をご利用のお客様の場合は、セキュリティ & コンプライアンスセンターを使用してこの機能を管理できます。 

- Office 365 セキュリティ & コンプライアンスセンターでは、フィッシングポリシーの下にあるスプーフィング対策保護を使用して、グローバルまたはセキュリティ管理者がこの機能を有効または無効にすることができます。 また、' Get-antiphishpolicy ' コマンドレットを使用して管理することもできます。 詳細については、「 [Office 365 のフィッシング対策保護](anti-phishing-protection.md)」および「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy?view=exchange-ps)」を参照してください。

    ![グラフィックインターフェイスで認証されていない送信者を編集する。](media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- 管理者が誤検知を識別し、送信者が未確認の送信者の処理を受信しないようにする場合は、次のいずれかの操作を実行して、スプーフィングインテリジェンススプーフィング許可リストに送信者を追加することができます。
        
    - スプーフィングインテリジェンスの洞察を通じてドメインペアを追加します。 詳細については、「チュートリアル: スプーフィングインテリジェンスの洞察」を参照してください。
                
    - Get-phishfilterpolicy コマンドレットを使用して、ドメインペアを追加します。 詳細については、「Get-phishfilterpolicy」および「Office のスプーフィング対策保護」を参照してください365

また、電子メールトランスポートルール (Etr)、安全なドメインリスト (スパム対策ポリシー)、安全な送信者リスト、またはユーザーがこのユーザーを自分のドメイン内の "安全な送信者" として設定している場合にも、未検証の送信者の処理は適用されません。ボックス.

### <a name="you-see-a--in-the-sender-image"></a>送信者の画像に '? ' が表示される

Outlook.com と web 上の Outlook が電子メール認証手法を使用して送信者の身元を確認できない場合は、送信者の写真に '? ' が表示されます。 

![メッセージが検証に合格しませんでした](media/message-did-not-pass-verification.jpg)

認証に失敗したすべてのメッセージが悪意のあるものであるとは限りません。 ただし、送信者を認識しない場合は、認証されないメッセージの操作について注意する必要があります。 または、通常は送信者の画像に '? ' が含まれていない送信者を認識したが、突然表示を開始した場合は、送信者がスプーフィングされているという署名になることがあります。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a>Outlook.com と web 上の Outlook で、'? ' および ' via ' プロパティを追加するために使用する条件とは何ですか。

送信者イメージの '? ' の場合: Outlook.com では、メッセージが SPF または DKIM 認証のいずれかを通過する必要があります。 詳細については、「 [Set UP SPF In office 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 」を参照して、スプーフィングを防止し、 [Dkim を使用して office 365 のカスタムドメインから送信される送信電子メールを検証](use-dkim-to-validate-outbound-email.md)します。

Via タグの場合: From アドレスのドメインが DKIM シグネチャまたは SMTP メールのドメインと異なる場合、Outlook.com は、この2つのフィールドのいずれかにドメインを表示します (DKIM シグネチャを優先します)。

### <a name="how-do-i-remove-the-"></a>'? ' を削除する方法

送信者の画像の '? ' の場合は、送信者として、SPF または DKIM のいずれかを使用してメッセージを認証する必要があります。

Via タグ: 送信者としての場合は、DKIM 署名のドメインまたは SMTP メールが、From アドレスのドメインと同じかサブドメインのものであることを確認する必要があります。

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a>Outlook.com と web 上の Outlook は、認証を通過しないすべてのメッセージに対してこのように表示されます。

必ずしもそうではありません。 Outlook.com および web 上の Outlook は、メッセージ内に送信者を認証するためのその他のプロパティがある場合があります。

## <a name="related-topics"></a>関連項目

[Outlook.com メールアカウントを保護する](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[Outlook.com での迷惑行為、フィッシング、またはスプーフィングに対処する](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[Outlook on the web で迷惑メールおよびスパムをフィルター処理する](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
