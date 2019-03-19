---
title: ゼロアワー自動消去 - スパムやマルウェアからの保護
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
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
ms.openlocfilehash: b49f7e3b5effec7b67daf6ab8acbf049705a4841
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670582"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>ゼロアワー自動消去 - スパムやマルウェアからの保護

## <a name="overview"></a>概要

ゼロ時間自動削除 (ZAP) は、ユーザーの受信トレイに既に配信されているフィッシング、スパム、またはマルウェアを含むメッセージを検出し、悪意のあるコンテンツを表示する電子メール保護機能です。 これは、検出された悪意のあるコンテンツの種類によってどのような違いがありますか。メールの内容、url、または添付ファイルのため、メールを zapped することができます。
  
ZAP は、exchange online メールボックスを含む Office 365 サブスクリプションに含まれている既定の exchange online Protection で利用できます。

ZAP は既定で有効になっていますが、次の条件を満たしている必要があります。
  
- **迷惑メールフォルダーにメッセージを移動**するように**スパムアクション**が設定されています。 <br/>すべてのメールボックスを ZAP でスクリーニングしないようにする場合は、ユーザーのセットにのみ適用される新しいスパムフィルターポリシーを作成することもできます。

- ユーザーが既定の迷惑メール設定を保持しており、迷惑メールの保護がオフになっていない。 (Outlook のユーザーオプションの詳細については[、「迷惑メールフィルターの保護レベルを変更](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b)する」を参照してください)。 
  
## <a name="how-does-zap-work"></a>ZAP はどのように動作しますか?

Office 365 は、毎日スパム対策エンジンとマルウェア署名をリアルタイムで更新します。 ただし、ユーザーが配信された後にコンテンツが weaponized されている場合を含め、さまざまな理由で、ユーザーは引き続き悪意のあるメッセージを受信トレイに配信する可能性があります。 ZAP は、継続的に Office 365 スパムおよびマルウェア署名の更新を監視することによって解決します。 ZAP は、既にユーザーの受信トレイにある配信済みメッセージを見つけて削除することができます。 

- スパムとして識別されたメールの場合、ZAP は未読のメッセージをユーザーの迷惑メールフォルダーに移動します。 

- フィッシングとして識別されるメールの場合、ZAP は、電子メールが開封されたかどうかに関係なく、ユーザーの迷惑メールフォルダーにメッセージを移動します。

- 新たに検出されたマルウェアの場合、ZAP は電子メールメッセージの添付ファイルを削除します (電子メールが開封されたかどうかは関係ありません)。 
  
ZAP アクションは、メールボックスユーザーにとってシームレスです。電子メールメッセージが移動された場合は通知されません。
  
許可リスト、[メールフロールール](https://go.microsoft.com/fwlink/p/?LinkId=722755)、およびエンドユーザールールまたは追加フィルターは、ZAP より優先されます。
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a>スパムフィルターポリシーを確認または設定するには
  
1. に[https://protection.office.com](https://protection.office.com)移動して、Office 365 の職場または学校のアカウントを使用してサインインします。

2. [**脅威の管理**] で、[**スパム対策**] を選択します。

3. 標準設定を確認します。 

4. 設定をカスタマイズする場合は、[**ユーザー**設定] タブを選択し、[**ユーザー設定**] をオンにします。 設定を編集し、必要に応じて、[ **+ ポリシーを作成**して新しいポリシーを追加する] を選択します。 
    
## <a name="to-see-if-zap-moved-your-message"></a>ZAP がメッセージを移動したかどうかを確認するには

ZAP がメッセージを移動したかどうかを確認するには、[脅威保護状態レポート](view-email-security-reports.md#threat-protection-status-report)(または[脅威エクスプローラー](use-explorer-in-security-and-compliance.md)) を使用できます。
    
## <a name="to-disable-zap"></a>ZAP を無効にするには
  
Office 365 テナントまたはユーザーのセットに対する ZAP を無効にする場合は、 [set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)の EOP コマンドレットの**zapenabled**パラメーターを使用します。
    
次の例では、"Test" という名前のコンテンツフィルターポリシーで ZAP が無効になっています。
    
```Powershell
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a>FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>正当なメッセージが迷惑メールフォルダーに移動された場合はどうなりますか。
  
誤[検知](prevent-email-from-being-marked-as-spam.md)の通常のレポートプロセスに従う必要があります。 メッセージが [受信トレイ] から [迷惑メール] フォルダーに移動されるのは、サービスがスパムまたは悪意のあるメッセージであると判断した場合のみです。
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>迷惑メールフォルダーではなく、Office 365 検疫を使用している場合はどうなりますか?
  
この時点で、ZAP は受信トレイからメッセージを検疫に移動しません。
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>カスタムメールフロールール (ブロック/許可ルール) を持っている場合
  
管理者によって作成されたルール (メールフロールール) またはブロックと許可ルールが優先されます。 このようなメッセージは、機能の条件から除外されるので、メールフローはルールの処理 (ブロック/許可ルール) に従います。
  
## <a name="related-topics"></a>関連項目

[Office 365 の電子メールのスパム対策保護](anti-spam-protection.md)
  
[検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする](reduce-spam-email.md)
  

