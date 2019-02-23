---
title: スパム対策メッセージ ヘッダー
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Exchange Online Protection では、受信電子メール メッセージをスキャンするときに、 **X-Forefront-Antispam-Report** ヘッダーをそれぞれのメッセージに挿入します。
ms.openlocfilehash: 4851c05f4db8d120eb54b9c22025fe2972e1e515
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223586"
---
# <a name="anti-spam-message-headers"></a>スパム対策メッセージ ヘッダー

Exchange Online Protection では、受信電子メール メッセージをスキャンするときに、 **X-Forefront-Antispam-Report** ヘッダーをそれぞれのメッセージに挿入します。このヘッダー内のフィールドは、そのメッセージに関する情報やそれがどのように処理されたかに関する情報を管理者に提供できます。 **X-Microsoft-Antispam** ヘッダー内のフィールドは、バルク メールやフィッシングについての追加情報を提供します。これら 2 つのヘッダーのほかに、Exchange Online Protection も電子メール認証の結果を **Authentication-results** ヘッダーで処理する各メッセージに挿入します。
  
> [!TIP]
> さまざまな電子メール クライアントで電子メール メッセージ ヘッダーを表示する方法については、「[メッセージ ヘッダー アナライザー](https://go.microsoft.com/fwlink/p/?LinkId=306583)」を参照してください。メッセージ ヘッダーの内容は、コピーして[メッセージ ヘッダー アナライザー](https://testconnectivity.microsoft.com/?tabid=mha) ツールに貼り付けることができます。Exchange 管理センターで検疫内のメッセージを選択した場合は、 **[メッセージ ヘッダーの表示]** リンクを使ってメッセージ ヘッダー テキストをコピーしてツールに貼り付けることもできます。メッセージ ヘッダー アナライザー ツールに貼り付ければ、 **[ヘッダーの分析]** をクリックしてヘッダーに関する情報を取得できます。
  
## <a name="x-forefront-antispam-report-message-header-fields"></a>X-Forefront-Antispam-Report メッセージ ヘッダー フィールド
<a name="sectionSection0"> </a>

メッセージ ヘッダー情報にアクセスしたら、 **X-Forefront-Antispam-Report** を検索して、次に示すフィールドを確認します。このヘッダー内のその他のフィールドは、Microsoft スパム対策チームが診断のために専用で使用します。

|**ヘッダー フィールド**|**説明**|
|:-----|:-----|
|CIP:[IP アドレス]|接続 IP アドレス接続フィルターで IP 許可一覧と IP 禁止一覧を作成する際、この IP アドレスを指定することができます。詳細については、「[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)」を参照してください。  |
|CTRY|サービスに接続されたメッセージの発信国。これは、接続先 IP アドレスから特定されます。そのため、発信元の送信先 IP アドレスとは異なる可能性があります。|
|LANG|メッセージが作成された言語であり、国番号 (たとえば、ロシア語は ru_RU) で指定されます。|
|SCL|メッセージの Spam Confidence Level (SCL) 値。これらの値の解釈方法については、「[Spam Confidence Level](spam-confidence-levels.md)」を参照してください。  |
|PCL|メッセージの Phishing Confidence Level (PCL) 値。 |
|SRV:BULK|メッセージが一括電子メール メッセージとして識別されました。 **[バルクメール メッセージをすべてブロックする]** 詳細スパム フィルター オプションが有効になっている場合、このメッセージがスパムとしてマークされます。このオプションが有効になっていない場合は、残りのフィルター処理ルールでそのメッセージがスパンであると判断された場合にのみスパムとしてマークされます。  |
|SFV:SFE|メッセージが個人の差出人セーフ リスト上のアドレスから送信されているため、フィルター処理が省略され、メッセージはそのまま配信されました。|
|SFV:BLK|メッセージが個人の受信拒否リスト上のアドレスから送信されているため、フィルター処理が省略され、メッセージはブロックされました。  <br/> **ヒント**: エンドユーザーがセーフリストと受信拒否リストを作成する方法の詳細については、「 [Block or allow (迷惑メール設定)](https://go.microsoft.com/fwlink/p/?LinkId=294862) 」 (web 上の outlook) および「[迷惑メールフィルター](https://go.microsoft.com/fwlink/p/?LinkId=270065) (outlook) の概要」を参照してください。|
|IPV:CAL|このメッセージの IP アドレスは接続フィルターの IP 許可一覧に指定されているため、スパム フィルターの通過を許可されました。|
|IPV:NLI|IP アドレスが IP 評価リストに掲載されていませんでした。|
|SFV:SPM|コンテンツ フィルターによって、メッセージがスパムとしてマークされました。|
|SFV:SKS|コンテンツ フィルターによって処理される前に、メッセージがスパムとしてマークされました。これには、メッセージを自動的にスパムとしてマークし、他のすべてのフィルター処理を省略するトランスポート ルールに適合したメッセージが含まれます。|
|SFV:SKA|メッセージは、スパム フィルター ポリシーの許可リスト ( **送信者の許可**リストなど) と一致したため、フィルタリングをスキップして受信トレイに配信されました。|
|SFV:SKB|メッセージは、スパム フィルター ポリシーの拒否リスト ( **送信者の拒否**リストなど) と一致したため、スパムとしてマークされました。|
|SFV:SKN|コンテンツ フィルターによって処理される前に、メッセージが非スパムとしてマークされました。これには、メッセージを自動的に非スパムとしてマークし、他のすべてのフィルター処理を省略するトランスポート ルールに適合したメッセージが含まれます。|
|SFV:SKI|SFV:SKN と同様に、メッセージはテナント内の組織内電子メールであるなどの別の理由でフィルター処理が省略されました。|
|SFV:SKQ|メッセージは検疫から解放され、目的の受信者に送信されました。|
|SFV:NSPM|メッセージがスパムではないとしてマークされ、意図された受信者に送信されました。|
|H:[helostring]|接続元のメール サーバーの HELO または EHLO 文字列。|
|PTR:[ReverseDNS]|逆引き DNS アドレスとも呼ばれる、送信元の IP アドレスの PTR レコード (またはポインター レコード)。|
|SFTY|メッセージはフィッシングとして識別され、次の値のいずれかでマークされます。 <br/>• 9.1: 既定値。メッセージには、フィッシングの URL が含まれているか、他のフィッシングコンテンツが含まれている可能性があります。または、Office 365 にメッセージを中継する前に、Exchange Server の社内バージョンなどの他のメールフィルターによってフィッシングとしてマークされている場合があります。 <br/>• 9.11: メッセージで失敗したスプーフィング防止チェックに失敗しました。 From: ヘッダー内の送信側ドメインが、受信側ドメインと同じ組織またはその一部と同じであるか、その一部であるか。これは、組織内のスプーフィングの安全性のヒントがメッセージに追加されることを示します。 <br/>• 9.19: メッセージの失敗したドメイン偽装チェックによって、送信ドメインが受信者によって所有されているドメインを偽装しようとしたか、またはフィッシング対策ポリシーによって保護されているカスタムドメインの偽装を試みます。これは、Phishig ポリシーによって有効にされた場合に、偽装の安全ヒントがメッセージに追加されることを示します。 <br/>• 9.20: 送信ユーザーが受信者の組織内でユーザーを偽装しようとした、またはフィッシング対策ポリシーによって保護されているカスタムユーザーのユーザー偽装チェックに失敗したメッセージ。これは、Phishig ポリシーによって有効にされた場合に、偽装の安全ヒントがメッセージに追加されることを示します。 <br/>• 9.21: メッセージが失敗したスプーフィング防止チェックを行い、From: ヘッダーの送信ドメインは認証されず、外部ドメインからのものです。compauth と組み合わせて使用されます (「Authentication-Results」を参照してください)。 <br/>• 9.22: ユーザーが、上書きされた差出人セーフリストを持っている場合を除き、9.21 と同じです。 <br/>• 9.23: 9.22 と同じです。ただし、組織には、上書きされた許可された送信者またはドメインがあります。 <br/>• 9.24: ユーザーには、上書きされた Exchange メールフロールールがあることを除き、9.23 と同じです。|
|X-CustomSpam:[ASFOption]|メッセージは、高度なスパムフィルターオプションと一致しました。たとえば、 **X-customspam: リモートサイトへの画像リンク**は、**リモートサイト ASF オプションへの画像リンク**が一致したことを示しています。特定の ASF オプションに対してどの X ヘッダーテキストが追加されているかを確認するには、「 [Advanced spam filtering options](advanced-spam-filtering-asf-options.md)」を参照してください。|
   
## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft-Antispam メッセージ ヘッダー フィールド
<a name="sectionSection1"> </a>

次の表に、 **X-Microsoft-Antispam** メッセージ ヘッダー内の便利なフィールドを示します。このヘッダー内のその他のフィールドは、Microsoft スパム対策チームが診断のために専用で使用します。
  
|**ヘッダー フィールド**|**説明**|
|:-----|:-----|
|BCL|メッセージの Bulk Complaint Level (BCL)。詳細については、「[バルク苦情レベルの値](bulk-complaint-level-values.md)」を参照してください。  |
|PCL|メッセージのフィッシング信頼レベル (PCL)。これは、フィッシングメッセージであるかどうかを示します。この状態は、次のいずれかの数値として返されます。<br/>• **0-3**: メッセージの内容がフィッシングではない可能性があります。 <br/>• **4-8**: メッセージの内容がフィッシングである可能性が高いことを示します。 <br/>• **-9990**: (Exchange Online Protection のみ) メッセージの内容がフィッシングである可能性が高いことを示します。  <br/>  これらの値は、電子メールクライアントがメッセージに対して実行するアクションを決定するために使用されます。たとえば、Outlook は PCL スタンプを使用して、疑わしいメッセージの内容をブロックします。フィッシングの詳細と、Outlook がフィッシングメッセージを処理する方法については、「[電子メールメッセージ内のリンクを有効または無効](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8)にする」を参照してください。|
   
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
|spf|メッセージの SPF チェックの結果についての説明。次の値を指定できます。  <br/>• **pass (IP アドレス)**: メッセージの SPF チェックが渡され、送信者の IP アドレスが含まれていることを示します。クライアントは、送信者のドメインに代わって電子メールを送信または中継することを承認されています。<br/>• **fail (IP アドレス)**: メッセージの SPF チェックでエラーが発生し、送信者の IP アドレスが含まれていることを示します。これは、" _hard fail_" と呼ばれることがあります。<br/>• **softfail (理由)**: SPF レコードがホストを送信が許可されていないものとして指定したが、移行中であることを示します。 <br/>•**ニュートラル**: SPF レコードが、IP アドレスが承認されているかどうかがアサートされていないことを明示的に明記していることを示します。 <br/>• **none**: ドメインに spf レコードがないか、spf レコードが結果として評価されないことを示します。 <br/>• **temperror**: DNS エラーなど、自然に一時的なエラーが発生したことを示します。後で再試行することは、管理者の操作なしで成功する可能性があります。<br/>• **permerror**: 永続的なエラーが発生したことを示します。これは、たとえば、ドメインの SPF レコードが正しくフォーマットされていない場合に発生します。|
|mailfrom|メッセージが送信された送信元のドメインを含みます。この電子メール メッセージに関するすべてのエラーは、ポスト マスターまたはドメインを担当するエンティティに送信されます。これは、メッセージ エンベロープの 5321.MailFrom アドレスまたはリバースパス アドレスとも呼ばれます。|
|dkim|メッセージの DKIM チェックの結果についての説明。次の値を指定できます。  <br/>• **pass**: メッセージの dkim チェックに合格したことを示します。 <br/>• **fail (理由)**: メッセージの dkim チェックに失敗したことと、その理由を示します。たとえば、メッセージが署名されていない、または署名が検証されていない場合です。<br/>• **none**: メッセージが署名されていなかったことを示します。これは、ドメインに dkim レコードがあること、または dkim レコードが結果を評価せず、このメッセージが署名されていないことのみを示している可能性があります。|
|ヘッダー d|DKIM 署名で識別されるドメイン (存在する場合)。 これは、公開キーを照会するドメインです。|
|dmarc|メッセージの DMARC チェックの結果についての説明。次の値を指定できます。  <br/>• **pass**: メッセージの DMARC チェックが渡されたことを示します。 <br/>• **fail**: メッセージの DMARC チェックに失敗したことを示します。 <br/>• **bestguesspass**: ドメインの DMARC TXT レコードが存在しないことを示しますが、存在していた場合は、メッセージの DMARC チェックに合格したことになります。これは、5321.mailfrom アドレスのドメインが5322.from アドレスのドメインと一致するからです。<br/>• **none**: DNS に送信側ドメインの dkim TXT レコードが存在しないことを示します。|
|action|DMARC チェックの結果に基づいて、スパム フィルターが実行するアクションを示します。例:  <br/>• **permerror**: DMARC 評価中に永続的なエラーが発生しました。たとえば、DNS で間違った形式の DMARC TXT レコードが発生した場合などです。このメッセージを再送信しようとしても、結果が異なる可能性があります。代わりに、問題を解決するために、ドメインの所有者に連絡しなければならない場合があります。<br/>• **temperror**: DMARC 評価中に一時的なエラーが発生しました。メールを適切に処理するために、後で送信者がメッセージを再送信するように要求することができます。<br/>• **oreject**または**reject**: 上書き拒否を表します。この場合、Office 365 は、DMARC TXT レコードのポリシーが p = reject であるドメインから DMARC チェックに失敗したメッセージを受信すると、このアクションを使用します。Office 365 は、メッセージを削除または拒否する代わりに、メッセージをスパムとしてマークします。この方法で office 365 を構成する理由の詳細については、「 [office 365 が受信電子メールを処理する方法 DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail)」を参照してください。<br/>• **quarantine**: DMARC を通過しないメッセージの 100% 未満の割合が配信されることを示します。これは、メッセージが DMARC に失敗し、ポリシーが検疫に設定されたが、pct フィールドが 100% に設定されておらず、指定されたドメインのポリシーに従って DMARC アクションが適用されないことをランダムに決定したことを意味します。<br/>• **pct**: DMARC を通過しないメッセージの 100% 未満の割合が配信されることを示します。これは、メッセージが DMARC に失敗し、ポリシーが reject に設定されていたが、pct フィールドが 100% に設定されておらず、指定されたドメインのポリシーに従って DMARC アクションが適用されないことをランダムに決定したことを意味します。|
|ヘッダー|電子メールメッセージヘッダーの From アドレスのドメイン。これは、 _5322.from_アドレスと呼ばれることがあります。|
|compauth|複合認証の結果。Office 365 によって使用され、SPF、dkim、DMARC などのさまざまな種類の認証を組み合わせて、メッセージが認証されているかどうかを判断します。評価の基準として、From: ドメインを使用します。|
|したがっ|コンポジット認証が合格または失敗した理由。理由の値は3桁の数字で構成されます。<br/>• **000**: メッセージは明示的に認証に失敗しました。たとえば、メッセージは、検疫または拒否のアクションを使用して、DMARC fail を受信しました。<br/>• **001**: メッセージは暗黙的に認証に失敗し、送信側ドメインは認証ポリシーを公開しませんでした。たとえば、p = none の DMARC ポリシーがあります。<br/>• **1xx**: 認証に合格したメッセージ。2番目の2桁の数字は、Office 365 で使用される内部コードです。<br/>• **2xx**: メッセージがソフトで渡される認証。2番目の2桁の数字は、Office 365 で使用される内部コードです。<br/>• **3xx**: メッセージは、コンポジット認証のためにチェックされませんでした。 <br/>• **4xx**: メッセージは複合認証をバイパスします。2番目の2桁の数字は、Office 365 で使用される内部コードです。|
