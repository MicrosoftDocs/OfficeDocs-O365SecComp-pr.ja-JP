---
title: Office 365 で送信スパムポリシー通知を構成する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/10/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 管理者は、Office 365 で送信スパム検出の通知設定を変更する方法について説明します。
ms.openlocfilehash: c48b6cd634417a00040fb5479313782b44f6aa8d
ms.sourcegitcommit: 81b3bff27bc60235a38004c5b0297ac454331b25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "36822517"
---
# <a name="configure-outbound-spam-policy-notifications-in-office-365"></a>Office 365 で送信スパムポリシー通知を構成する

送信電子メールの送信にサービスを使用すると、送信スパムフィルターは常に有効になり、それによって、そのサービスと目的の受信者を使用して組織が保護されます。 受信フィルターと同様に、送信スパムフィルターは、接続フィルターとコンテンツフィルターで構成されますが、送信フィルター設定は構成できません。 送信メッセージがスパムであると判断された場合は、より危険度の高い配信プールを経由してルーティングされます。これにより、通常の送信 IP プールがブロックリストに追加される確率が低くなります。 お客様がサービス経由で送信スパムを引き続き送信する場合、メッセージの送信はブロックされます。

送信スパムフィルター処理を無効にしたり、変更したりすることはできませんが、次の送信スパム通知設定を構成できます。

- **疑わしいメッセージのコピーを送信**する: これらのメッセージは、SCL レベルに関係なく、スパムとしてマークされ、フィルターによって拒否されることはありませんが、より危険度の高い配信プールを経由してルーティングされます。 Exchange 管理センター (EAC) また** \*は HostedOutboundSpamFilterPolicy**コマンドレットを使用して、exchange online powershell または exchange online Protection powershell で、これらの検出されたメッセージの受信者を追加することができます。 受信者は**Bcc**受信者として追加されることに注意してください **(差出人フィールド**と宛先フィールドは元の**送信者と受信**者です)。

- **送信者がブロックされたときに通知を送信**する: 特定のユーザーが大量のスパムを受信した場合、そのユーザーは電子メールメッセージの送信を無効にします。 管理者には既定で通知されますが、Office 365 セキュリティ & コンプライアンスセンターで [**ユーザーによるメール通知の送信を制限** [](alert-policies.md)する] を使用して、追加の通知受信者を構成することができます。

  この通知がどのように表示されるかを確認するには、「[送信者が送信スパムの送信をブロックされる場合の通知例](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)」をご覧ください。 作業を再度有効にする方法については、「[Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx)」をご覧ください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- 予想所要時間 : 5 分

- セキュリティ/コンプライアンス センターを開くには、「[Office 365 のセキュリティ センターとコンプライアンス センターに移動する](go-to-the-securitycompliance-center.md)」を参照してください。

- EAC を開くには、「exchange [online の exchange 管理センター](https://docs.microsoft.com/Exchange/exchange-admin-center) 」または「exchange [Admin Center In exchange online Protection](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。

- Exchange Online PowerShell を開くには、「 [Exchange Online powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。 Exchange Online Protection PowerShell を開くには、「 [Exchange Online protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)」を参照してください。

- この手順を実行する前に、アカウントにアクセス許可を割り当てる必要があります。 必要なアクセス許可については、「 [Office 365 セキュリティ & コンプライアンスセンター](permissions-in-the-security-and-compliance-center.md)」の「アクセス許可」の「通知を管理する」の役割エントリを参照してください。

## <a name="use-the-eac-to-configure-additional-recipients-for-outbound-spam-messages"></a>EAC を使用して、送信スパムメッセージの追加の受信者を構成する

1. EAC で、[**保護** \> **送信スパム**] に移動します。

2. **Default**という名前のポリシーを選択し、[編集](media/ITPro-EAC-EditIcon.png)] ![編集アイコン**をクリックし**ます。

3. 開いたプロパティページで、[**送信スパムの設定**] タブが選択されていることを確認し、次の設定を構成します。

   **疑わしい送信電子メールメッセージすべてのコピーを次の電子メールアドレスまたはアドレスに送信**する: チェックボックスをオンにして、検出されたメッセージの**Bcc**フィールドに追加する1人以上の管理者の電子メールアドレスを入力します。 複数の電子メールアドレスは、セミコロン (;) で区切ります。

   完了したら、**[保存]** をクリックします。

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-additional-recipients-for-outbound-spam-messages"></a>Exchange Online PowerShell または Exchange Online Protection PowerShell を使用して、送信スパムメッセージの追加の受信者を構成する

送信スパムメッセージの追加の受信者を有効にして構成するには、次の構文を使用します。

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients <recipients>
```

- 既存のすべての値を上書きする受信者を指定する`emailaddress1,emailaddress2,...emailaddressN`には、構文を使用します。

- 他のエントリに影響を与えずに、受信者を追加また`@{Add="\<emailaddress1\>","\<emailaddress2\>"...; Remove="\<emailaddress1\>","\<emailaddress2\>"...}`は削除するには、構文を使用します。

この例では、chris@contoso.com、laura@contoso.com、および julia@contoso.com を送信スパムメッセージの Bcc 受信者として構成します。

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients chris@contoso.com,laura@contoso.com,julia@contoso.com
```

この例では、追加の Bcc 受信者として michelle@contoso.com を追加します。

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Add=michelle@contoso.com}
```

この例では、Bcc 受信者のリストから chris@contoso.com および julia@contoso.com を削除します。

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Remove='chris@contoso.com','julia@contoso.com'}
```

構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy)」を参照してください。

**注**: コマンド`Get-HostedOutboundSpamFilterPolicy | Format-List`を実行して、 *BccSuspiciousOutboundMail*プロパティと*BccSuspiciousOutboundAdditionalRecipients*プロパティの現在の値を確認します。

## <a name="use-the-security--compliance-center-to-configure-notifications-when-a-sender-is-blocked"></a>セキュリティ & コンプライアンスセンターを使用して、送信者がブロックされたときの通知を構成する

1. [セキュリティ & コンプライアンスセンター] で、[**アラート** \> **ポリシー**] に移動します。

2. [**ユーザーによるメール送信からの制限**] という名前のポリシーを検索して選択します。

3. スライドが開いたら、[ポリシーの**編集**] をクリックします。

4. 表示される [**受信者の編集**] ページで、次の設定を構成します。

   - **電子メール通知****の**送信: が選択されていることを確認します。

   - **電子メール受信者**: 既定では、 **tenantadmins**のみがこの値になります。 その他の受信者を追加するには、このボックスの空の場所をクリックし、受信者の入力を開始して、名前が解決される受信者を選択します。 受信者を削除するには、名前の横にある [ **X** ] をクリックします。

   - [**毎日の通知制限**]: 既定値は**制限なし**ですが、1 ~ 200 のさまざまな制限を構成できます。

   完了したら、**[保存]** をクリックします。

## <a name="for-more-information"></a>関連情報

[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)

[スパム対策保護に関する FAQ](anti-spam-protection-faq.md)
