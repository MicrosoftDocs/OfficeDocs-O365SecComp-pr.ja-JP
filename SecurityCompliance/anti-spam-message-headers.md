---
title: スパム対策メッセージ ヘッダー
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/9/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
description: Exchange Online Protection では、受信電子メール メッセージをスキャンするときに、 **X-Forefront-Antispam-Report** ヘッダーをそれぞれのメッセージに挿入します。
ms.openlocfilehash: 7baa15f4d687c809d45461a135f64f0d18f49a7f
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026504"
---
# <a name="anti-spam-message-headers"></a>スパム対策メッセージ ヘッダー

Exchange Online Protection では、受信電子メール メッセージをスキャンするときに、 **X-Forefront-Antispam-Report** ヘッダーをそれぞれのメッセージに挿入します。このヘッダー内のフィールドは、そのメッセージに関する情報やそれがどのように処理されたかに関する情報を管理者に提供できます。 **X-Microsoft-Antispam** ヘッダー内のフィールドは、バルク メールやフィッシングについての追加情報を提供します。これら 2 つのヘッダーのほかに、Exchange Online Protection も電子メール認証の結果を **Authentication-results** ヘッダーで処理する各メッセージに挿入します。 
  
> [!TIP]
> さまざまな電子メール クライアントで電子メール メッセージ ヘッダーを表示する方法については、「[メッセージ ヘッダー アナライザー](https://go.microsoft.com/fwlink/p/?LinkId=306583)」を参照してください。メッセージ ヘッダーの内容は、コピーして[メッセージ ヘッダー アナライザー](https://testconnectivity.microsoft.com/?tabid=mha) ツールに貼り付けることができます。Exchange 管理センターで検疫内のメッセージを選択した場合は、 **[メッセージ ヘッダーの表示]** リンクを使ってメッセージ ヘッダー テキストをコピーしてツールに貼り付けることもできます。メッセージ ヘッダー アナライザー ツールに貼り付ければ、 **[ヘッダーの分析]** をクリックしてヘッダーに関する情報を取得できます。 
  
## <a name="x-forefront-antispam-report-message-header-fields"></a>X-Forefront-Antispam-Report メッセージ ヘッダー フィールド
<a name="sectionSection0"> </a>

メッセージ ヘッダー情報にアクセスしたら、 **X-Forefront-Antispam-Report** を検索して、次に示すフィールドを確認します。このヘッダー内のその他のフィールドは、Microsoft スパム対策チームが診断のために専用で使用します。 
  
|||
|:-----|:-----|
|**ヘッダー フィールド** <br/> |**説明** <br/> |
|CIP:[IP アドレス]  <br/> |接続 IP アドレス接続フィルターで IP 許可一覧と IP 禁止一覧を作成する際、この IP アドレスを指定することができます。詳細については、「[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)」を参照してください。  <br/> |
|CTRY  <br/> |サービスに接続されたメッセージの発信国。これは、接続先 IP アドレスから特定されます。そのため、発信元の送信先 IP アドレスとは異なる可能性があります。  <br/> |
|LANG  <br/> |メッセージが作成された言語であり、国番号 (たとえば、ロシア語は ru_RU) で指定されます。  <br/> |
|SCL  <br/> |メッセージの Spam Confidence Level (SCL) 値。これらの値の解釈方法については、「[Spam Confidence Level](spam-confidence-levels.md)」を参照してください。  <br/> |
|PCL  <br/> |メッセージの Phishing Confidence Level (PCL) 値。PCL 値の詳細については、「[PCL](anti-spam-message-headers.md#PCL)」を参照してください。  <br/> |
|SRV:BULK  <br/> |メッセージが一括電子メール メッセージとして識別されました。 **[バルクメール メッセージをすべてブロックする]** 詳細スパム フィルター オプションが有効になっている場合、このメッセージがスパムとしてマークされます。このオプションが有効になっていない場合は、残りのフィルター処理ルールでそのメッセージがスパンであると判断された場合にのみスパムとしてマークされます。  <br/> |
|SFV:SFE  <br/> |メッセージが個人の差出人セーフ リスト上のアドレスから送信されているため、フィルター処理が省略され、メッセージはそのまま配信されました。  <br/> |
|SFV:BLK  <br/> |メッセージが個人の受信拒否リスト上のアドレスから送信されているため、フィルター処理が省略され、メッセージはブロックされました。  <br/> **ヒント:** エンド ユーザーが差出人セーフ リストと受信拒否リストを作成する方法については、「 [ブロックまたは許可 (迷惑メール設定)](https://go.microsoft.com/fwlink/p/?LinkId=294862)」 (OWA) と「[迷惑メール フィルターの概要](https://go.microsoft.com/fwlink/p/?LinkId=270065)」 (Outlook) を参照してください。  <br/> |
|IPV:CAL  <br/> |このメッセージの IP アドレスは接続フィルターの IP 許可一覧に指定されているため、スパム フィルターの通過を許可されました。  <br/> |
|IPV:NLI  <br/> |IP アドレスが IP 評価リストに掲載されていませんでした。  <br/> |
|SFV:SPM  <br/> |コンテンツ フィルターによって、メッセージがスパムとしてマークされました。  <br/> |
|SFV:SKS  <br/> |コンテンツ フィルターによって処理される前に、メッセージがスパムとしてマークされました。これには、メッセージを自動的にスパムとしてマークし、他のすべてのフィルター処理を省略するトランスポート ルールに適合したメッセージが含まれます。  <br/> |
|SFV:SKA  <br/> |メッセージは、スパム フィルター ポリシーの許可リスト ( **送信者の許可**リストなど) と一致したため、フィルタリングをスキップして受信トレイに配信されました。  <br/> |
|SFV:SKB  <br/> |メッセージは、スパム フィルター ポリシーの拒否リスト ( **送信者の拒否**リストなど) と一致したため、スパムとしてマークされました。  <br/> |
|SFV:SKN  <br/> |コンテンツ フィルターによって処理される前に、メッセージが非スパムとしてマークされました。これには、メッセージを自動的に非スパムとしてマークし、他のすべてのフィルター処理を省略するトランスポート ルールに適合したメッセージが含まれます。  <br/> |
|SFV:SKI  <br/> |SFV:SKN と同様に、メッセージはテナント内の組織内電子メールであるなどの別の理由でフィルター処理が省略されました。  <br/> |
|SFV:SKQ  <br/> |メッセージは検疫から解放され、目的の受信者に送信されました。  <br/> |
|SFV:NSPM  <br/> |メッセージがスパムではないとしてマークされ、意図された受信者に送信されました。  <br/> |
|H:[helostring]  <br/> |接続元のメール サーバーの HELO または EHLO 文字列。  <br/> |
|PTR:[ReverseDNS]  <br/> |逆引き DNS アドレスとも呼ばれる、送信元の IP アドレスの PTR レコード (またはポインター レコード)。  <br/> |
|SFTY  <br/> | メッセージは、フィッシング詐欺として識別され、も、次の値のいずれかでマークされます。  <br/>  9.1 の既定値です。メッセージは、フィッシング詐欺の URL が含まれています、その他のフィッシング詐欺の内容が含まれている可能性があります。 または可能性がありますとマークされているフィッシング詐欺の設置型バージョンの Exchange Server などの別のメール フィルターにより Office 365 にメッセージを中継する前に。  <br/>  9.11 - は、メッセージがスプーフィング対策の確認に失敗しました。 どこから送信側のドメイン: ヘッダーが同じに合わせて、または受信側のドメインと同じ組織の一部であります。  <br/>  9.21 - スプーフィング対策のチェックと送信側ドメインからのメッセージが失敗しました: ヘッダーの認証は行いません。CompAuth との組み合わせで使用されている (認証の結果を参照してください)。  <br/>  9.22 - ユーザーがオーバーライドされた差出人セーフ リストを持っていることを除いて、9.21 と同じです。  <br/>  9.23 - 組織には、許可された送信者またはドメインがオーバーライドされることを除いて、9.22 と同じです。  <br/>  9.24 - 9.23 と同じユーザーがルールを Exchange メール フローを持っていることを除いてが上書きされました。  <br/> |
|X-CustomSpam:[ASFOption]  <br/> |メッセージには、高度なスパム フィルターのオプションが一致します。たとえば、 **X CustomSpam: イメージをリモート ・ サイトへのリンク****のリモート ・ サイトへの画像リンク**の ASF のオプションが一致したことを示します。X ヘッダー テキストはそれぞれ特定の ASF オプションの追加については、[高度な迷惑メール フィルターのオプション](advanced-spam-filtering-asf-options.md)を参照してください。<br/> |
   
## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft-Antispam メッセージ ヘッダー フィールド
<a name="sectionSection1"> </a>

次の表に、 **X-Microsoft-Antispam** メッセージ ヘッダー内の便利なフィールドを示します。このヘッダー内のその他のフィールドは、Microsoft スパム対策チームが診断のために専用で使用します。 
  
|||
|:-----|:-----|
|**ヘッダー フィールド** <br/> |**説明** <br/> |
|BCL  <br/> |メッセージの Bulk Complaint Level (BCL)。詳細については、「[バルク苦情レベルの値](bulk-complaint-level-values.md)」を参照してください。  <br/> |
|PCL  <br/> | メッセージの Phishing Confidence Level (PCL)。これは、そのメッセージがフィッシング メッセージかどうかを示します。    <br/>  この状態は、次のいずれかの数値として返されます。  <br/> **0-3** は、メッセージの内容がフィッシングである可能性が低いことを示します。  <br/> **4-8** は、メッセージの内容がフィッシングである可能性が高いことを示します。  <br/> **-9990** (Exchange Online Protection のみ) は、メッセージの内容がフィッシングである可能性が低いことを示します。  <br/>  これらの値は、電子メール クライアントがメッセージに対して実行するアクションを決めるために使用されます。たとえば、Microsoft Office Outlook は PCL スタンプを使用して、疑わしいメッセージの内容をブロックします。フィッシングについてと、Outlook がフィッシング メッセージを処理する方法の詳細については、「 [電子メール メッセージ内のリンクを有効または無効にする](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8)」を参照してください。  <br/> |
   
## <a name="authentication-results-message-header"></a>Authentication-results メッセージ ヘッダー
<a name="sectionSection2"> </a>

メール サーバーが電子メール メッセージを受信すると、SPF、DKIM、および DMARC に対するチェックの結果が Office 365 によって、 **Authentication-results** メッセージ ヘッダーに記録またはスタンプされます。 
  
### <a name="check-stamp-syntax-and-examples"></a>check stamp 構文と例
<a name="referenceSPFstamp"> </a>

次に示す構文の例では、Office 365 がメール サーバーでの受信時に電子メールの認証チェックを受ける各メールのメッセージ ヘッダーに適用するテキスト "スタンプ" の一部を示しています。このスタンプは **Authentication-Results** ヘッダーに追加されます。 
  
 **構文:SPF check stamp**
  
SPF の場合は、次の構文を適用します。
  
```
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

 **例:SPF check stamp**
  
```
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com

```

 **構文:DKIM check stamp**
  
DKIM の場合は、次の構文を適用します。
  
```
dkim=<pass|fail (reason)|none> header.d=<domain>
```

 **例:DKIM check stamp**
  
```
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

 **構文:DMARC check stamp**
  
DMARC の場合は、次の構文を適用します。
  
```
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

 **例:DMARC check stamp**
  
```
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Office 365 の電子メールの認証で使用される Authentication-results メッセージ ヘッダー フィールド
<a name="referenceSPFstamp"> </a>

フィールドと各電子メールの認証チェックに使用できる値を次の表に示します。
  
|**ヘッダー フィールド**|**説明**|
|:-----|:-----|
|spf  <br/> | メッセージの SPF チェックの結果についての説明。次の値を指定できます。  <br/> **pass (IP アドレス)** は、メッセージの SPF チェックにパスしたことを示します。送信者の IP アドレスが含まれます。送信の許可、または送信者のドメインに代わっての電子メールを中継する許可がクライアントに与えられます。  <br/> **fail (IP アドレス)** は、メッセージの SPF チェックに失敗したことを示します。送信者の IP アドレスが含まれます。Hard Fail ともいいます。  <br/> **softfail (理由)** は、SPF レコードがホストを、送信が認められたものではなく、切り替えとして指定したことを示します。  <br/> **neutral** は、IP アドレスが許可されているかどうかをアサートしていないことを、 SPF レコードが明示的に宣言したことを示します。  <br/> **none** は、ドメインに SPF レコードがないか、SPF レコードが結果に対して評価されないことを示します。  <br/> **temperror** は、DNS エラーなど、実際には一時的なものの可能性があるエラーが発生したことを示します。 管理者がなんらかのアクションを実行しなくても、後で再試行すれば成功する場合があります。  <br/> **permerror** は、永続的なエラーが発生したことを示します。これは、ドメインに不正な形式の SPF レコードがある場合に発生します。  <br/> |
|smtp.mailfrom  <br/> |メッセージが送信された送信元のドメインを含みます。この電子メール メッセージに関するすべてのエラーは、ポスト マスターまたはドメインを担当するエンティティに送信されます。これは、メッセージ エンベロープの 5321.MailFrom アドレスまたはリバースパス アドレスとも呼ばれます。  <br/> |
|dkim  <br/> | メッセージの DKIM チェックの結果についての説明。次の値を指定できます。  <br/> **pass** は、メッセージの DKIM チェックにパスしたことを示します。  <br/> **fail (理由)** メッセージの DKIM チェックに失敗したことと、その理由を示します。たとえば、メッセージが署名されていなかったり、署名を確認できない場合です。  <br/> **none** メッセージが署名されていないことを示します。これは、ドメインに DKIM レコードがあるかどうかや、DKIM レコードが結果を評価しない (このメッセージが署名されていない点のみ) ことを示しますが、これらを示さない場合もあります。  <br/> |
|header.d  <br/> |DKIM 署名で識別されるドメイン (存在する場合)。 これは、公開キーを照会するドメインです。  <br/> |
|dmarc  <br/> | メッセージの DMARC チェックの結果についての説明。次の値を指定できます。  <br/> **pass** は、メッセージの DMARC チェックにパスしたことを示します。  <br/> **fail** は、メッセージの DMARC チェックに失敗したことを示します。  <br/> **bestguesspass** は、ドメインの DMARC TXT レコードが存在しないことを示します。ただし、レコードが存在していた場合、メッセージの DMARC チェックはパスしていたことになります。これは、5321.MailFrom アドレスのドメインが、5322.From アドレスのドメインと一致するためです。  <br/> **none** は、DNS に送信側ドメインの DKIM TXT レコードが存在していないことを示します。  <br/> |
|action  <br/> | DMARC チェックの結果に基づいて、スパム フィルターが実行するアクションを示します。例:  <br/> **permerror** は、DMARC の評価時に永続的なエラーが発生したことを示します (DNS で正しくない形式の DMARC TXT レコードが見つかった場合など)。このメッセージを再送信しようとしても、結果が異なる可能性はほとんどありません。その代わりに、ドメインの所有者に問い合わせて問題を解決する必要があります。  <br/> **temperror** は、DMARC の評価時に一時的なエラーが発生したことを示します。メールが正しく処理されるように、後でメッセージを再送信するように、送信者に要求することもできます。  <br/> **oreject** または **o.reject** 拒否の上書き (override reject) の略語。この場合、Office 365 は、ポリシーが p=reject に設定されている DMARC TXT レコードを持つドメインからの DMARC チェックに失敗したメッセージを受信したときに、このアクションを使用します。Office 365 はメッセージを削除または拒否する代わりに、スパムとしてメッセージにマークを付けます。このように Office 365 が構成されている理由の詳細については、「 [Office 365 が DMARC に失敗した受信メールを処理する方法](use-dmarc-to-validate-email.md#inbounddmarcfail)」を参照してください。  <br/> **pct.quarantine** は、DMARC をパスできない、パーセンテージが 100% 未満のメッセージが配信されることを示します。これは、メッセージが DMARC に失敗してポリシーが検疫に設定されますが、pct フィールドは 100% に設定されず、システムは指定されたドメインのポリシーに従って、DMARC アクションを適用しないことをランダムに判断しているということです。  <br/> **pct.reject** DMARC をパスできない、パーセンテージが 100% 未満のメッセージが配信されることを示します。これは、メッセージが DMARC に失敗してポリシーが拒否に設定されますが、pct フィールドは 100% に設定されず、システムは指定されたドメインのポリシーに従って、DMARC アクションを適用しないことをランダムに判断しているということです。  <br/> |
|header.from  <br/> |メール メッセージ ヘッダーの From アドレスのドメイン。5322.From アドレス ともいいます。  <br/> |
|compauth  <br/> |複合認証の結果です。認証 SPF、DKIM、DMARC、またはメッセージが認証済みかどうかを確認するメッセージの他の部分などの複数の種類を組み合わせるには、Office 365 で使用されます。From を使用して: 評価の基礎としてのドメインです。  <br/> |
|理由  <br/> | 理由複合認証は、合格または失敗します。理由の値は、3 桁の数字で構成されています。  <br/>  000 - メッセージに明示的に認証に失敗しました。たとえば、メッセージ検疫または拒否のアクションを伴う DMARC の失敗を受信しました。  <br/>  001 - メッセージは認証では、暗黙的に失敗し、送信側のドメインは、認証ポリシーを公開できませんでした。ポリシーなどの DMARC の p = なし。  <br/>  1 xx のメッセージには、認証が渡されます。次の 2 桁は、Office 365 で使用される内部のコードです。  <br/>  2 xx - メッセージ ソフト渡される認証します。次の 2 桁は、Office 365 で使用される内部のコードです。  <br/>  3 xx - メッセージは、複合認証チェックされませんでした。  <br/>  4 xx - メッセージは、複合認証をバイパスします。次の 2 桁は、Office 365 で使用される内部のコードです。  <br/> |
  