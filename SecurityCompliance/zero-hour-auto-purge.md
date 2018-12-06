---
title: ゼロアワー自動消去 - 迷惑メールやマルウェアからの保護
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: ゼロの自動パージ (ZAP) は既にユーザーの受信トレイに配信されたメッセージをスパムやマルウェアを検出する電子メールの保護機能で、害のない、悪意のあるコンテンツをレンダリングZAP はこれは、検出された、悪意のあるコンテンツの種類によって異なります。
ms.openlocfilehash: 1cf14051e91801a74a0d739c69900bb3f825b318
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180847"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>ゼロアワー自動消去 - 迷惑メールやマルウェアからの保護

## <a name="overview"></a>概要

ゼロの自動パージ (ZAP) 電子メール保護機能があり、フィッシング、スパムやマルウェアに既にユーザーの受信トレイに配信されたメッセージを検出は、害のない、悪意のあるコンテンツをレンダリングします。ZAP はこれは、悪意のあるコンテンツが検出されたの種類によって異なりますメールは、メールのコンテンツ、Url、または添付ファイルのためれたことができます。
  
ZAP は、既定の Exchange Online のメールボックスを含むすべての Office 365 サブスクリプションに含まれている Exchange のオンライン保護に使用できます。

ZAP が既定でオンですが、以下の条件を満たす必要があります。
  
- **スパム アクション**は、 **[迷惑メール フォルダーにメッセージを移動**するのには設定されています。 <br/>すべてのメールボックスを ZAP でスクリーニングする必要がある場合に、一連のユーザーにのみ適用する新しい迷惑メール フィルター ポリシーを作成することもできます。

- ユーザーは、迷惑メールの設定をその既定値を保管してあるし、迷惑メールの保護をオフになっていません。(Outlook ユーザー オプションの詳細について[の迷惑メール フィルターの保護レベルの変更](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b)を参照してください)。 
  
## <a name="how-does-zap-work"></a>ZAP の動作方法

Office 365 のスパム対策エンジンおよびマルウェアのシグネチャを更新する毎日のようにリアルタイムです。ただし、ユーザーは悪意のあるメッセージをさまざまな理由から、ユーザーに配布された後の内容が後で場合を含む受信トレイに配信をする可能性が残っています。ZAP は、Office 365 のスパムやマルウェアのシグネチャの更新を継続的に監視することによってこれを説明します。ZAP では、検索でき、ユーザーの受信トレイに配信されるメッセージを削除することができます。 

- スパムとして識別されるメールでは、ZAP は未読メ ッ セージをユーザーの迷惑メール フォルダーに移動します。 

- スパムとして識別されるメールでは、ZAP は、電子メールが読み取られたかどうかに関係なく、ユーザーの迷惑メール フォルダーにメッセージを移動します。

- 新たに検出されたマルウェアが、ZAP は、電子メールが読み取られたかどうかに関係なく、電子メール メッセージから添付ファイルを削除します。 
  
ZAP アクションが、メールボックスのユーザーのシームレスです電子メール メッセージが移動された場合に通知されません。
  
リスト、[メール フローの規則](https://go.microsoft.com/fwlink/p/?LinkId=722755)、およびエンド ・ ユーザーの規則を許可するか、追加フィルター ZAP よりも優先します。
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a>迷惑メール フィルターのポリシー設定を確認または
  
1. [https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用して Office 365 にサインインします。

2. **脅威の管理**の下で、**迷惑メール対策**を選択します。

3. 標準の設定を確認します。 

4. 設定をカスタマイズする場合は、**ユーザー設定**] タブを選択し、**カスタム設定**を有効にします。設定を編集し、 **+ ポリシーを作成する**新しいポリシーを追加するを選択する場合は、します。 
    
## <a name="to-see-if-zap-moved-your-message"></a>ZAP がメッセージを移動するかどうかを参照してください。

ZAP がメッセージを移動するかどうかを参照してくださいしたい場合、またはいずれかの[脅威保護の状態のレポート](view-email-security-reports.md#threat-protection-status-report-new)([脅威のエクスプ ローラー](use-explorer-in-security-and-compliance.md)) を使用できます。
    
## <a name="to-disable-zap"></a>ZAP を無効にするには
  
無効にするか、Office 365 のテナントの ZAP[セット HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)EOP、コマンドレットの**ZapEnabled**パラメーターを使用するユーザーのセットです。
    
次の例では、ZAP は「テスト」という名前のコンテンツ フィルター ポリシー無効になります。
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a>FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>正当なメッセージが [迷惑メール] フォルダーに移動するとどうなりますか。
  
誤の通常のレポート作成プロセスに従う必要があります。[迷惑メール] フォルダーにメッセージを受信トレイから移動が唯一の理由の場合は、サービスが、メッセージが迷惑メールをしたことを確認するためまたは悪意のあります。
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>場合、[迷惑メール] フォルダーではなく Office 365 の検査を使用しますか。
  
ZAP 移動しないメッセージ検疫場所に受信トレイからこの時点で。
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>ユーザー設定のメール フロー ルールがある場合 (禁止/許可の規則)。
  
管理者 (メール フロー ルール) またはブロックし、許可する規則が作成した規則が優先されます。このようなメッセージは、機能の基準から除外されます。
  
## <a name="related-topics"></a>関連項目

[Office 365 の電子メールのスパム対策保護](anti-spam-protection.md)
  
[検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする](block-email-spam-to-prevent-false-negatives.md)
  

