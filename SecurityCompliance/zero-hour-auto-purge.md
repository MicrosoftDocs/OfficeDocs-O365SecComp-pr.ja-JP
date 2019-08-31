---
title: ゼロアワー自動消去 - スパムまたはマルウェアからの保護
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/11/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: ゼロ時間自動削除 (ZAP) は、ユーザーの受信トレイに既に配信されているスパムまたはマルウェアを含むメッセージを検出し、その悪意のあるコンテンツを無害にする電子メール保護機能です。 これは、検出された悪意のあるコンテンツの種類によってどのような違いがありますか。
ms.openlocfilehash: 91bb167c988e49a40895f851a518ee255abdbf08
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "36698969"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>ゼロアワー自動消去 - スパムまたはマルウェアからの保護

## <a name="overview"></a>概要

ゼロ時間自動削除 (ZAP) は、ユーザーの受信トレイに既に配信されているフィッシング、スパム、またはマルウェアを含むメッセージを検出し、悪意のあるコンテンツを表示する電子メール保護機能です。 これは、検出された悪意のあるコンテンツの種類によってどのような違いがありますか。メールの内容、Url、または添付ファイルのため、メールを zapped することができます。
  
ZAP は、Exchange Online メールボックスを含む Office 365 サブスクリプションに含まれている既定の Exchange Online Protection で利用できます。

ZAP は既定で有効になっていますが、次の条件を満たしている必要があります。
  
- **迷惑メールフォルダーにメッセージを移動**するように**スパムアクション**が設定されています。 すべてのメールボックスを ZAP でスクリーニングしないようにする場合は、ユーザーのセットにのみ適用される新しいスパムフィルターポリシーを作成することもできます。

- ユーザーが既定の迷惑メール設定を保持しており、迷惑メールの保護がオフになっていない。 (Outlook のユーザーオプションの詳細については[、「迷惑メールフィルターの保護レベルを変更](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)する」を参照してください)。
  
## <a name="how-zap-works"></a>ZAP のしくみ

Office 365 は、毎日スパム対策エンジンとマルウェア署名をリアルタイムで更新します。 ただし、ユーザーが配信された後にコンテンツが weaponized されている場合を含め、さまざまな理由で、ユーザーは引き続き悪意のあるメッセージを受信トレイに配信する可能性があります。 ZAP は、継続的に Office 365 スパムおよびマルウェア署名の更新を監視することによって解決します。 ZAP は、既にユーザーの受信トレイにある配信済みメッセージを見つけて削除することができます。

ZAP アクションは、メールボックスユーザーにとってシームレスです。電子メールメッセージが移動された場合は通知されません。 メッセージを2日より前にすることはできません。
  
許可リスト、[メールフロールール](https://go.microsoft.com/fwlink/p/?LinkId=722755)(トランスポートルールとも呼ばれます)、およびエンドユーザールールまたは追加フィルターは、ZAP より優先されます。

### <a name="malware-zap"></a>マルウェアの ZAP

新たに検出されたマルウェアの場合、ZAP は電子メールメッセージから添付ファイルを削除し、ユーザーのメールボックスにメッセージの本文を残します。 添付ファイルは、メールの開封状況に関係なく削除されます。

マルウェアの ZAP は、マルウェアポリシーで既定で有効になっています。 Exchange Online PowerShell または Exchange Online Protection PowerShell で[new-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)コマンドレットの*zapenabled*パラメーターを使用して、マルウェアの ZAP を無効にすることができます。

### <a name="phish-zap"></a>フィッシング ZAP

配信後にフィッシングとして識別されるメールの場合、ZAP はユーザーが対象とするスパムポリシーに従って処理を行います。 [Policy フィッシング] アクションがメールに対してアクションを実行するように設定されている場合 (リダイレクト、削除、検疫、迷惑メールへの移動)、ZAP により、メールの開封状況に関係なく、ユーザーの受信トレイの迷惑メールフォルダーにメッセージが移動されます。 [ポリシーのフィッシング] アクションが [アクションを実行する] に設定されていない ([X-ヘッダーの追加]、[件名の変更]、[アクションなし]) 場合、ZAP はメールに対してアクションを実行しません。 ここでは[、スパムフィルターポリシーを構成](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies)する方法について説明します。

スパムポリシーでは、フィッシング ZAP が既定で有効になっています。 フィッシング ZAP を無効にするには、Exchange Online PowerShell または Exchange Online Protection PowerShell の[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)コマンドレットで*zapenabled*パラメーターを使用します。

### <a name="spam-zap"></a>スパム ZAP

配信後にスパムとして識別されるメールの場合、ZAP はユーザーが対象とするスパムポリシーに従って処理を行います。 メールに対してアクションを実行するようにポリシーのスパムアクションが設定されている場合 (リダイレクト、削除、検疫、迷惑メールへの移動)、ZAP により、メッセージが未読の場合は、ユーザーの受信トレイの迷惑メールフォルダーにメッセージが移動されます。 [Policy Spam] アクションがアクションを実行するように設定されていない ([X-ヘッダーの追加]、[件名の変更]、[アクションなし]) 場合、ZAP はメールに対してアクションを実行しません。 ここでは[、スパムフィルターポリシーを構成](configure-your-spam-filter-policies.md)する方法について説明します。

スパム ZAP は、スパムポリシーでは既定で有効になっています。 Exchange Online PowerShell または Exchange Online Protection PowerShell で[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)コマンドレットの*zapenabled*パラメーターを使用して、スパム ZAP を無効にすることができます。

> [!NOTE]
> **Set-hostedcontentfilterpolicy**コマンドレットの*zapenabled*パラメーターは、ポリシーに対してフィッシング ZAP とスパム zap の両方を無効または有効にします。 同じポリシー内でフィッシング ZAP とスパム ZAP を独立して有効または無効にすることはできません。

## <a name="how-to-see-if-zap-moved-your-message"></a>ZAP がメッセージを移動したかどうかを確認する方法

ZAP がメッセージを移動したかどうかを確認するには、[脅威保護状態レポート](view-email-security-reports.md#threat-protection-status-report)または[脅威エクスプローラー (およびリアルタイム検出)](threat-explorer.md)のいずれかを使用できます。

## <a name="disable-zap"></a>ZAP を無効にする

Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。 Exchange Online Protection PowerShell に接続するには、「 [Exchange Online protection の powershell への接続](https://go.microsoft.com/fwlink/p/?linkid=627290)」を参照してください。

### <a name="disable-malware-zap"></a>マルウェアの無効化 * *

この例では、"Test" という名前のマルウェアフィルターポリシーの ZAP を無効にします。

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

構文とパラメーターの詳細については、「[Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)」を参照してください。

### <a name="disable-phish-zap-and-spam-zap"></a>フィッシング ZAP とスパム ZAP を無効にする

この例では、"Test" という名前のコンテンツフィルターポリシーでフィッシング ZAP とスパム ZAP を無効にします。

```Powershell
Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

構文およびパラメーターの詳細については、「 [set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)」を参照してください。

## <a name="faq"></a>FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>正当なメッセージが迷惑メールフォルダーに移動された場合はどうなりますか。
  
誤[検知](prevent-email-from-being-marked-as-spam.md)の通常のレポートプロセスに従う必要があります。 メッセージが [受信トレイ] から [迷惑メール] フォルダーに移動されるのは、サービスがスパムまたは悪意のあるメッセージであると判断した場合のみです。
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>迷惑メールフォルダーではなく、Office 365 検疫を使用している場合はどうなりますか?
  
この時点で、ZAP は受信トレイからメッセージを検疫に移動しません。
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>カスタムメールフロールール (ブロック/許可ルール) を持っている場合
  
管理者によって作成されたルール (メールフロールール) またはブロックと許可ルールが優先されます。 このようなメッセージは、機能の条件から除外されるので、メールフローはルールの処理 (ブロック/許可ルール) に従います。

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a>メッセージが別のフォルダー (たとえば、受信トレイルールなど) に移動した場合はどうなりますか。

この場合、ZAP は、メッセージが削除されているか、迷惑メールにある場合を除き、この場合でも動作します。

## <a name="related-topics"></a>関連項目

[Office 365 の電子メールのスパム対策保護](anti-spam-protection.md)
  
[検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする](reduce-spam-email.md)
