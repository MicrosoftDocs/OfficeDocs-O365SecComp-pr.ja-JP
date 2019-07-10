---
title: 送信スパム ポリシーを構成する
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
description: 送信電子メールの送信にサービスを使用すると、送信スパムフィルターは常に有効になり、それによって、そのサービスと目的の受信者を使用して組織が保護されます。
ms.openlocfilehash: c3eb663d569e717597ff926896ed3daefb48186e
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600063"
---
# <a name="configure-the-outbound-spam-policy"></a>送信スパム ポリシーを設定する

送信電子メールを送信するサービスを使用している場合は、送信スパム フィルターが常時有効になっているため、このフィルターによりこのサービスを利用している組織と対象の受信者は保護されます。送信スパム フィルターは、受信フィルターと同様、接続フィルターとコンテンツ フィルターで構成されていますが、送信フィルターの設定は構成できません。送信メッセージがスパムとして判断されると、より危険度の高い配信プール経由でルーティングされます。これにより、通常の送信 IP プールが禁止リストに追加される可能性が低くなります。ユーザーがこのサービス経由で送信スパムを送信し続けると、ユーザーはメッセージの送信からブロックされます。送信スパム フィルターを無効にしたり変更したりすることはできませんが、既定の送信スパム ポリシーを使用して企業全体の送信スパム設定を構成できます。 
  
次のビデオは、送信スパム ポリシーの構成方法を示しています。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1f20d655-0d3d-4141-9cae-e57f5a6cffe8?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>事前に必要な知識
<a name="sectionSection0"> </a>

予想所要時間 : 5 分
  
この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 必要なアクセス許可を確認するには、「 [Exchange Online の機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)」トピックの「スパム対策エントリ」を参照してください。 
  
このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。
  
以下の手順はリモート PowerShell 経由でも実行することができます。Get-HostedOutboundSpamFilterPolicy コマンドレットを使用して設定を確認し、 Set-HostedOutboundSpamFilterPolicy を使用して送信スパム ポリシー設定を編集します。 [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) コマンドレットを使用して設定を確認し、[Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) を使用して送信スパム ポリシー設定を編集します。 Windows PowerShell を使って Exchange Online Protection に接続する方法については、「[Exchange Online Protection の PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=627290)」を参照してください。 Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。
  
## <a name="use-the-eac-to-edit-the-default-outbound-spam-policy"></a>EAC を使用して既定の送信スパム ポリシーを編集する
<a name="sectionSection1"> </a>

既定の送信スパム ポリシーを編集するには、次の手順を使用します。
  
### <a name="to-configure-the-default-outbound-spam-policy"></a>既定の送信スパム ポリシーを構成する方法

1. Exchange 管理センター (EAC) で、 **[保護]** \> **[送信スパム]** に移動し、既定のポリシーをダブルクリックします。
    
2. **[送信スパム基本設定]** メニュー オプションを選択します。 
    
3. 送信メッセージに関連する以下のチェック ボックスにチェック マークを付けてから、付随して表示される入力ボックスに、関連する電子メール アドレスを指定します (解決結果が有効な SMTP 配信先であるなら、配信先リストも可能)。
    
1. **[すべての疑わしい送信電子メール メッセージのコピーを次の電子メール アドレスに送信します]**。(SCL 評価に関係なく) フィルターによってスパムとしてマークされたメッセージです。フィルターによって拒否されませんが、より危険度の高い配信プールでルーティングされます。複数のアドレスはセミコロンで区切ります。指定された受信者はブラインド カーボン コピー (BCC) アドレスとしてメッセージを受け取ることに注意してください (差出人フィールドと宛先フィールドは元の送信者と受信者です)。
    
2. **[送信者が送信スパムの送信をブロックされているとき、次の電子メール アドレスに通知を送信]**。複数のアドレスはセミコロンで区切ります。
    
    特定のユーザーから膨大な数のスパムが発信されると、そのユーザーによるメール メッセージの送信は無効になります。この設定の使用を指定したドメインの管理者は、このユーザーによるメッセージ送信がブロックされていることを通知されます。この通知がどのように表示されるかを確認するには、「[送信者が送信スパムの送信をブロックされる場合の通知例](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)」をご覧ください。作業を再度有効にする方法については、「[Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx)」をご覧ください。
    
4. **[保存]** をクリックします。既定のポリシー設定の概要が右側のウィンドウに表示されます。
    
## <a name="for-more-information"></a>詳細情報
<a name="sectionSection2"> </a>

[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)
  
[スパム対策保護に関する FAQ](anti-spam-protection-faq.md)
  

