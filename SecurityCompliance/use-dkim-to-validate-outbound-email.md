---
title: DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.custom: TN2DMC
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
description: 概要:この記事では、Office 365 で DomainKeys Identified Mail (DKIM) を使用して、カスタム ドメインから送信されたメッセージを送信先のメール システムが信頼するようにする方法を説明します。
ms.openlocfilehash: 080d873c91c2dfb5910588113f2a6709b3ee9ab4
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696334"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a>DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する

 **概要:** この記事では、Office 365 で DomainKeys Identified Mail (DKIM) を使用して、カスタム ドメインから送信されたメッセージを送信先のメール システムが信頼するようにする方法を説明します。 
  
ドメインから送信されたように見えるメッセージをなりすまし者が送信できないようにするためには、SPF と DMARC に加え、DKIM を使用する必要があります。DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加することができます。複雑そうに思えますが、まったく複雑ではありません。DKIM の構成時に、関連付けるドメインを承認するか、暗号化認証を使用して電子メール メッセージにその名前を署名します。ドメインから電子メールを受信する電子メール システムでは、このデジタル署名を使用して、受け取った受信メールが正当であるかどうかを判断することができます。
  
基本的には、秘密キーを使用してドメインの送信メールのヘッダーを暗号化します。受信側サーバーが署名のデコードに使用できるドメインの DNS レコードに、公開キーを発行します。公開キーを使用することで、そのメッセージが送信者本人からのものであり、ドメイン偽装をしている他人からのものでないことを確認します。
  
Office 365 は初期ドメインに DKIM を自動的にセットアップします。初期ドメインは、ユーザーが contoso.onmicrosoft.com などのサービスにサインアップしたときに、Office 365 が自動的に作成したドメインです。ユーザーは、初期ドメインに対する DKIM のセットアップに関して何も行う必要はありません。ドメインの詳細については、「[ドメインに関する FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)」を参照してください。
  
カスタム ドメインの DKIM に関しても、何も操作しなくて構いません。カスタム ドメインに対して DKIM を設定しない場合、Office 365 が秘密キーと公開キーのペアを作成して、DKIM 署名を有効にし、カスタム ドメインに対して Office 365 の既定ポリシーを構成します。ほとんどの Office 365 ユーザーの場合はこれで十分ですが、次の状況ではカスタム ドメインの DKIM を手動で構成する必要があります。
  
- Office 365 に複数のカスタム ドメインがある場合
    
- DMARC も設定する場合 (推奨)
    
- 秘密キーを制御する場合
    
- CNAME レコードをカスタマイズする場合
    
- たとえば、サード パーティ製の大容量メーラーを使用する場合、サードパーティのドメインから発信される電子メールに DKIM キーを設定することがあります。
    
この記事の内容
  
- [Office 365 での悪意のあるスプーフィング防止の点で DKIM のしくみが SPF 単独よりも優れているといえる理由](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)
    
- [Office 365 で DKIM を手動でセットアップする方法](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)
    
- [Office 365 で DKIM の複数のドメインを構成するには](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)
    
- [Office 365 でカスタム ドメインの DKIM 署名ポリシーを無効にする](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)
    
- [DKIM と Office 365 の既定の動作](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)
    
- [サードパーティのサービスがカスタム ドメインに代わって電子メールを送信つまり偽装できるように DKIM を設定する](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)
    
- [次の手順: Office 365 に SPF をセットアップした後](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)
    
## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a>Office 365 での悪意のあるスプーフィング防止の点で DKIM のしくみが SPF 単独よりも優れているといえる理由
<a name="HowDKIMWorks"> </a>

SPF ではメッセージ エンベロープに情報を追加しますが、DKIM は実際にメッセージ ヘッダー内の署名を暗号化します。メッセージを転送すると、そのメッセージのエンベロープの一部が転送サーバーによって取り除かれる可能性があります。デジタル署名は、電子メール ヘッダーの一部であるため、電子メール メッセージと共に残ります。したがって、DKIM はメッセージが転送された場合にも機能します。次の例で説明します。
  
![SPF チェックが失敗したときに DKIM 認証を通過した転送されたメッセージを示す図](media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)
  
この例で、ドメインに対して SPF TXT レコードしか発行しなかったとしたら、受信者のメール サーバーによってメールがスパムとしてマークされ、誤検知の結果になる可能性があります。このシナリオでは DKIM を追加することによって、誤検知のスパム報告が減少しています。DKIM は、IP アドレスだけではなく、公開キー暗号化を使って認証を行うので、SPF よりもはるかに強力な認証形態といえます。展開では DMARC だけでなく、SPF と DKIM の両方を使うことをお勧めします。
  
基本事項:DKIM では秘密キーを使用して、暗号化された署名をメッセージ ヘッダーに挿入します。署名ドメイン、つまり送信ドメインは、 **d=** フィールドの値としてヘッダーに挿入されます。確認ドメイン、つまり受信者のドメインは、 **d=** フィールドを使用して、DNS から公開キーを検索し、メッセージを認証します。メッセージが確認されれば、DKIM チェックは合格です。 
  
## <a name="what-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a>Office 365 で DKIM を手動でセットアップする方法
<a name="SetUpDKIMO365"> </a>

DKIM を構成するには、次の手順を完了します。
  
- [DNS でカスタム ドメインに対して 2 つの CNAME レコードを発行する](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
    
- [Office 365 でカスタム ドメインに対して DKIM 署名を有効にする](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)
    
### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>DNS でカスタム ドメインに対して 2 つの CNAME レコードを発行する
<a name="Publish2CNAME"> </a>

DNS の DKIM 署名を追加する各ドメインに対して、2 つの CNAME レコードを発行する必要があります。CNAME レコードは、ドメインの 正規名が別のドメイン名のエイリアスであることを指定するために DNS によって使用されます。 
  
 Office 365 は、発行された 2 つのレコードを使用して自動的にキーの交換を実行します。Office 365 の初期ドメインに加えてプロビジョニングされたカスタム ドメインがある場合には、追加の各ドメインに対して 2 つの CNAME レコードを発行する必要があります。したがって、2 つのドメインがある場合は、さらに 2 つの CNAME レコードを発行するなどの操作が必要になります。
  
CNAME レコードの次の形式を使用します。

> [!IMPORTANT]
> GCC の高いお客様のいずれかの場合は、計算_domainGuid_とは異なる。_DomainGuid_を計算するのには、 _initialDomain_の MX レコードを検索すると、代わりに代わりに自動的に計算される、カスタマイズされたドメインから直接。たとえば、カスタマイズされたドメインは、"contoso.com という"、domainGuid"contoso com"になります、任意の期間は、ダッシュに置き換えられます。したがって、どのような MX レコードとは無関係に、initialDomain のポイントには、常を使用します上記の方法で CNAME レコードを使用するのに domainGuid を計算します。

  
```
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600
```

ここで、
  
- Office 365 では、セレクターは常に "selector1" または "selector2" になります。 
    
- _domainGUID_は、ドメインには、mail.protection.outlook.com の前に表示されるカスタマイズされた MX レコードの_domainGUID_と同じです。ドメイン contoso.com の次の MX レコードの_domainGUID_は contoso com です。 
    
    ```
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- _initialDomain_は、Office 365 にサインアップするときに使用しているドメインです。Onmicrosoft.com で最初のドメインが常に終了します。最初のドメインを決定する方法の詳細については、[ドメインに関する FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)を参照してください。
    
たとえば、初期ドメイン (cohovineyardandwinery.onmicrosoft.com) と 2 つのカスタム ドメイン (cohovineyard.com と cohowinery.com) がある場合は、追加のそれぞれのドメインに対して 2 つの CNAME レコードをセットアップして、合計で 4 つの CNAME レコードをセットアップする必要があります。
  
```
Host name:          selector1._domainkey
Points to address or value: **selector1-cohovineyard-com**._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: **selector2-cohovineyard-com**._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: **selector1-cohowinery-com**._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
 
Host name:          selector2._domainkey
Points to address or value: **selector2-cohowinery-com**._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
```

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a>Office 365 でカスタム ドメインに対して DKIM 署名を有効にする
<a name="EnableDKIMinO365"> </a>

DNS に CNAME レコードを発行したら、Office 365 で DKIM 署名を有効にする準備が整ったことになります。これは、Office 365 管理センターか、PowerShell を使用して行うことができます。
  
#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-office-365-admin-center"></a>Office 365 管理センター経由でカスタム ドメインの DKIM 署名を有効にするには

1. [Office 365 へのサインイン](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)、職場または学校のアカウントを使用します。 
    
2. 左上隅にあるアプリ起動ツールのアイコンを選択し、 **[管理]** をクリックします。
    
3. 左下のナビゲーションで、 **[管理者]** を展開し、 **[Exchange]** を選択します。
    
4. **[保護]** \> **[dkim]** の順に移動します。
    
5. DKIM を有効にするドメインを選択してから、 **[このドメインのメッセージに DKIM 署名で署名する]** で **[有効]** を選択します。各カスタム ドメインにこの手順を繰り返します。
    
#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>PowerShell を使用してカスタム ドメインの DKIM 署名を有効にするには

1. [Exchange Online PowerShell に接続します](https://technet.microsoft.com/library/jj984289.aspx)。
    
2. 次のコマンドを実行します。
    
    ```
    New-DkimSigningConfig -DomainName <domain> -Enabled $true
    ```

   _ドメイン_は、DKIM の署名を有効にするカスタムのドメインの名前です。 
    
   たとえば、ドメイン名 contoso.com の場合は次のようになります。
    
    ```
    New-DkimSigningConfig -DomainName contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a>DKIM 署名が Office 365 に対して適切に構成されていることを確認するには

数分待ってから、これらの手順に従って、DKIM が適切に構成されていることを確認してください。待っている間に、ドメインに関する DKIM 情報がネットワーク全体に広まります。
  
- Office 365 の DKIM が有効になっているドメイン内のアカウントから、Outlook.com や Hotmail.com などの別の電子メール アカウントにメッセージを送信します。
    
- テスト目的には .aol.com アカウントは使用しないでください。AOL は SPF チェックに合格すると、DKIM チェックをスキップする場合があります。この場合、テストは成り立ちません。
    
- メッセージを開き、ヘッダーを確認します。メッセージのヘッダーを表示する方法は、メッセージング クライアントによって異なります。Outlook でメッセージ ヘッダーを表示する方法については、「[電子メール メッセージ ヘッダーを表示する](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C)」をご覧ください。

  DKIM 署名されたメッセージには、CNAME エントリの発行時に定義したホスト名とドメインが含まれます。メッセージは、次の例のようになります。 
    
    ```
    From: Example User <example@contoso.com> 
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
        s=selector1; d=contoso.com; t=1429912795; 
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
        bh=<body hash>; 
        b=<signed field>;
    ```

- 認証結果のヘッダーを確認します。各受信側のサービスでは受信メールのスタンプに若干異なる形式が使用されますが、結果には **DKIM=pass** や **DKIM=OK** などが含まれている必要があります。 
    
## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a>Office 365 で DKIM の複数のドメインを構成するには
<a name="DKIMMultiDomain"> </a>

後で別のカスタム ドメインを追加して、その新しいドメインに対して DKIM を有効にする場合は、各ドメインに対してこの記事の手順を完了する必要があります。具体的には、「[Office 365 で DKIM を手動でセットアップする方法](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)」のすべての手順を完了します。
  
## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a>Office 365 でカスタム ドメインの DKIM 署名ポリシーを無効にする
<a name="DisableDKIMSigningPolicy"> </a>

署名ポリシーを無効にしても、DKIM は完全には無効になりません。一定の期間が経過すると、Office 365 はドメインの既定の Office 365 ポリシーを自動的に適用します。詳細については、「[DKIM と Office 365 の既定の動作](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)」を参照してください。
  
### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>Windows PowerShell を使用して DKIM 署名ポリシーを無効にするには

1. [Exchange Online PowerShell に接続します](https://technet.microsoft.com/library/jj984289.aspx)。
    
2. DKIM 署名を無効にする各ドメインに対して次のいずれかのコマンドを実行します。
    
    ```
    $p=Get-DkimSigningConfig -identity <domain>
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   次に例を示します。
    
    ```
    $p=Get-DkimSigningConfig -identity contoso.com
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   または
    
    ```
    Set-DkimSigningConfig -identity $p[<number>].identity -enabled $false
    ```

    ここで、_number_ はポリシーのインデックスです。たとえば、 
    
    ```
    Set-DkimSigningConfig -identity $p[0].identity -enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a>DKIM と Office 365 の既定の動作
<a name="DefaultDKIMbehavior"> </a>

DKIM を有効にしない場合、Office 365 はカスタム ドメインに対して 1024 ビットの DKIM 公開キーと、それに関連する秘密キー (これはデータセンターに内部的に保存されます) を作成します。既定では、Office 365 は、所定のポリシーを持たないドメインに対して既定の署名構成を使用します。これは、ユーザーが DKIM をセットアップしなければ、Office 365 が、その既定のポリシーと、自らが作成するキーを使用して、そのドメインに対して DKIM を有効にすることを意味しています。
  
また、DKIM 署名を有効にしてから無効にした場合にも、一定の期間が過ぎると、Office 365 が自動的にドメインに対して Office 365 の既定のポリシーを適用します。
  
次の例では、fabrikam.com の DKIM が、ドメインの管理者ではなく、Office 365 によって有効にされていることを想定しています。これは、必須の CNAME が DNS に存在しないことを意味します。このドメインからのメールの DKIM 署名は、次のようなものになります。
  
```
From: Second Example <second.example@fabrikam.com> 
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795; 
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
    bh=<body hash>; 
    b=<signed field>;
```

この例のホスト名とドメインには、fabrikam.com の DKIM 署名がドメイン管理者によって有効にされた場合に CNAME が指し示す値が含まれています。最終的には、Office 365 から送信されるすべてのメッセージは DKIM 署名されたメッセージになります。自分で DKIM を有効にしている場合、ドメインは From: アドレス内のドメインと同じになります (この場合は fabrikam.com)。自分で DKIM を有効にしない場合は、ドメインは同じにならず、代わりに組織の初期ドメインが使用されます。初期ドメインを決定する方法の詳細については、「[ドメインに関する FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)」を参照してください。
  
## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>サードパーティのサービスがカスタム ドメインに代わって電子メールを送信つまり偽装できるように DKIM を設定する
<a name="SetUp3rdPartyspoof"> </a>

一部の一括電子メール サービス プロバイダー、または Software-as-a-Service プロバイダーでは、サービスから送信される電子メールに DKIM キーを設定できます。この場合、必要な DNS レコードを設定するために自分とサードパーティの間で調整が必要です。まったく同じ方法を用いる組織は 2 つとありません。それどころか、プロセスは完全に組織に依存します。
  
contoso.com および bulkemailprovider.com 用に適切に構成された DKIM を示すメッセージの例は、次のようになります。
  
```
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

この例では、この結果を達成するために、次を実行しました。
  
1. 一括電子メール プロバイダーは、Contosoc に DKIM の公開キーを付与しました。
    
2. Contoso は、その DNS レコードに DKIM キーを発行しました。
    
3. 電子メールを送信する場合、一括電子メール プロバイダーは対応する秘密キーを使用してキーに署名しました。これにより、一括電子メール プロバイダーはメッセージ ヘッダーに DKIM 署名を添付します。
    
4. 受信側の電子メール システムでは、DKIM-Signature d=\<domain\> 値を以下の宛先のドメインに対して認証することによって、DKIM チェックを実行します。(5322.From) メッセージのアドレス。この例では、次の値が一致します。
    
    メールボックス**ストア**の送信者
    
    d =**contoso.com**
    
## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a>次の手順: Office 365 に SPF をセットアップした後
<a name="DKIMNextSteps"> </a>

DKIM は、スプーフィングを防止するために設計されていますが、DKIM は SPF と DMARC をよりよく動作します。設定した DKIM、SPF を既に設定していない場合は、これを行う必要があります。SPF を迅速に構成するための簡単な説明、[スプーフィングを防止するために Office 365 の SPF を設定](set-up-spf-in-office-365-to-help-prevent-spoofing.md)を参照してください。Office 365 の SPF、使用方法について詳細に説明またはハイブリッド展開などのトラブルシューティング、または標準の導入では、[どの Office 365 を使用して送信者ポリシー フレームワーク (SPF) のスプーフィングを防ぐために](how-office-365-uses-spf-to-prevent-spoofing.md)始まります。次に、 [Office 365 で電子メールを検証するために使用して DMARC](use-dmarc-to-validate-email.md)を参照してください。[スパム メッセージのヘッダー](anti-spam-message-headers.md)には、DKIM チェックには、Office 365 で使用される構文およびヘッダーのフィールドが含まれています。 
  

