---
title: Office 365 のFAQための、顧客キーによるサービスの暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 41ae293a-bd5c-4083-acd8-e1a2b4329da6
description: BitLocker および Distributed Key Manager (DKM) によって有効になるベースライン、ボリュームレベルの暗号化に加えて、office 365 では、Exchange からのデータを含む、office 365 の顧客コンテンツのための暗号化のレイヤーが追加されています。Online、Skype for business、SharePoint Online、OneDrive for business。 これをサービス暗号化と呼びます。
ms.openlocfilehash: 8515354d716df22fa124c03e18c36914d27102f4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266946"
---
# <a name="service-encryption-with-customer-key-for-office-365-faq"></a>Office 365 のFAQための、顧客キーによるサービスの暗号化

BitLocker および Distributed Key Manager (DKM) によって有効になるベースライン、ボリュームレベルの暗号化に加えて、office 365 では、Exchange からのデータを含む、office 365 の顧客コンテンツのための暗号化のレイヤーが追加されています。Online、Skype for business、SharePoint Online、OneDrive for business。 これをサービス暗号化と呼びます。
  
顧客キーはサービス暗号化に基づいて構築されており、[オンラインサービス利用規約 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)で説明されているように、Office 365 でデータを暗号化するために使用されるキーを提供および制御することができます。 カスタマー キーを使用すれば、Office 365 がデータの暗号化解除に使用する暗号化キーを制御できるので、法令遵守の義務を満たすことができます。
  
ドキュメントなど、顧客キーに関するフィードバックを提供するために、アイデア、提案、および展望を customerkeyfeedback@microsoft.com に送信します。
  
## <a name="what-is-service-encryption-with-customer-key"></a>顧客キーによるサービスの暗号化とは

顧客キーは、クラウドサービスプロバイダーとの主要な手配を指定するコンプライアンス要件を満たすための組織の能力を向上させます。 Customer キーを使用すると、Office 365 データを保存するための暗号化キーをアプリケーションレベルで提供し、それを制御できます。 そのため、サービスを終了するかどうかを決定して、組織のキーを制御し、取り消すことができます。 キーを無効にすると、データはサービスに対して読み取ることができなくなります。 キーの取り消しは、データ削除へのパスの最初のステップです。

## <a name="what-office-365-data-at-rest-is-covered-by-customer-key"></a>お客様キーでカバーされている Office 365 データ
<a name="WhatDataIsCoveredbyCustomerKey"> </a>

SharePoint Online サイトのコンテンツと、そのサイトに保存されているファイル、および OneDrive for business にアップロードされたファイルについて説明します。 Exchange Online メールボックスのコンテンツ (電子メール本文、予定表のエントリ、電子メールの添付ファイルの内容) について説明します。 skype for business からのテキスト会話については説明していますが、skype 会議ブロードキャストのレコーディングおよび skype 会議コンテンツのアップロードについては説明しません。 skype 会議ブロードキャストと skype 会議コンテンツのアップロードは、Office 365 の他のすべてのコンテンツと共に暗号化されますが、現在、暗号化キーをカスタマーコントロールには提供していません。
  
## <a name="what-is-the-difference-between-customer-key-and-bring-your-own-key-byok-with-azure-information-protection-for-exchange-online"></a>Exchange Online の Azure Information Protection では、顧客キーと独自のキー (byok) の違いは何ですか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

両方のオプションを使用すると、独自の暗号化キーを指定して制御できます。ただし、カスタマーキーを使用したサービス暗号化は、保存されたままの状態で Office 365 サーバーに存在するデータを保存します。ただし、Exchange Online の Azure Information Protection を使用すると、データを暗号化し、オンラインおよびオフラインの状態を維持することが可能です。Office 365 の電子メールメッセージと添付ファイルを保護します。 Exchange Online の Azure Information Protection による顧客キーと byok は補完的なものであり、Microsoft のサービス管理キーと独自のキーのどちらを使用するかを選択することにより、データを保存したり、送信したりすることができます。悪意のある攻撃。
  
byok Exchange Online の Azure Information Protection は、Office 365 メッセージ暗号化機能で提供されています。
  
## <a name="does-office-365-message-encryption-and-bring-your-own-key-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>Office 365 Message Encryption および Azure Information Protection を使用して独自のキーを取り込む subpoenas などのサードパーティのデータ要求に対する Microsoft のアプローチを変更する
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

いいえ。 Office 365 メッセージの暗号化、および Azure Information Protection 用の独自のキー (byok) を使用して独自の暗号化キーを提供および制御するオプションは、法的執行 subpoenas への対応を目的としたものではありませんでした。 Office 365 AIP の byok によるメッセージの暗号化は、内部または外部のコンプライアンス義務を満たす必要があるコンプライアンスに重点を置いたお客様向けに設計されています。 Microsoft は、お客様のデータに関するサードパーティの要求を非常に真剣に行います。 クラウドサービスプロバイダーとして、お客様のデータのプライバシーを常に支持しています。 召喚を受け取った場合は、常にお客様にサードパーティをリダイレクトして、情報を入手してください。 (官庁のブログ: 「[お客様のデータを政府から保護](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)する」を参照してください)。 [ここで](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)受信する要求の詳細情報を定期的に公開しています。
  
詳細については、[オンラインサービス利用規約 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)にあるサードパーティのデータ要求と "顧客データの開示" に関する[Microsoft のセキュリティセンター](https://www.microsoft.com/en-us/trustcenter/default.aspx)を参照してください。
  
## <a name="does-service-encryption-with-customer-key-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>顧客キーによるサービスの暗号化 Microsoft の subpoenas などのサードパーティのデータ要求に対するアプローチを変更しますか?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

いいえ。 顧客キーは、法的執行 subpoenas に対応するように設計されていません。 これは、規制を利用しているお客様が、内部または外部のコンプライアンス義務に対応するように設計されました。 Microsoft は、お客様のデータに関するサードパーティの要求を非常に真剣に行います。 クラウドサービスプロバイダーとして、お客様のデータのプライバシーを常に支持しています。 召喚を受け取った場合は、常にお客様にサードパーティをリダイレクトして、情報を入手してください。 (官庁のブログ: 「[お客様のデータを政府から保護](http://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)する」を参照してください)。 [ここで](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)受信する要求の詳細情報を定期的に公開しています。
  
詳細については、[オンラインサービス利用規約 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)にあるサードパーティのデータ要求と "顧客データの開示" に関する[Microsoft のセキュリティセンター](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)を参照してください。 
  
## <a name="is-fasttrack-support-available-for-implementing-customer-key"></a>カスタマーキーを実装するために fasttrack サポートは利用できますか?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

いいえ。 fasttrack は、顧客キーの登録に必要なテナントおよびサービス構成情報を収集するためにのみ使用されます。 カスタマーキー提供は fasttrack で公開されているため、顧客やパートナーが同じ方法でこの必要な情報を提出したり、顧客が提供するデータのアーカイブを容易にしたりするのに便利です。
  
ドキュメント以外のサポートが必要な場合は、microsoft コンサルティングサービス (MCS)、プレミアフィールドエンジニアリング (pfe)、または microsoft パートナーにお問い合わせください。
  
## <a name="if-my-keys-are-destroyed-how-can-i-recover"></a>キーが破壊された場合、どのような方法で回復できますか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性キーは、管理している予期しないルートキーから回復する機能を提供します。 ルートキーを紛失した場合は、microsoft サポートにお問い合わせください。また、microsoft は可用性キーを有効にするプロセスを支援します。 可用性キーを使用して、新しいキーをプロビジョニングした新しいデータ暗号化ポリシーに移行します。 
  
## <a name="what-is-the-availability-key"></a>可用性キーとは
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性キーは、データ暗号化ポリシーの作成時に準備されるルートキーです。 可用性キーは Office 365 内に格納され、保護されており、カスタマーキーを使用してサービス暗号化を使用するために提供される2つのルートキーと同じように機能します。 Azure key Vault で提供および管理するキーとは異なり、可用性キーに直接アクセスすることはできません。 可用性キーのストレージと制御は、次の3つの理由から、azure key Vault キーとは意図的に異なります。最初に、可用性キーは、Office 365 サービスが azure キーでホストされているキーに到達できない場合の高可用性機能を提供します。コンテナー2番目に、可用性キーは、両方の Azure key Vault キーが失われたときに、"ブレイクガラス" 機能を提供します。3番目に、論理コントロールの分離により、多層防御が提供され、単一の攻撃または障害点からすべてのキーが失われないように保護されます。 キーを保護する責任を共有し、キー管理のためのさまざまな保護とプロセスを使用して、最終的にすべてのキー (つまりデータ) が失われたり、破壊されたりするリスクを軽減します。 Microsoft では、可用性キーの破棄に関して、唯一の権限を提供しています。 設計上、Microsoft では可用性キーにアクセスできません。 Office 365 サービスコードによってのみアクセスできます。
  
## <a name="how-many-data-encryption-policies-deps-can-i-create"></a>作成できるデータ暗号化ポリシーの数 (deps)
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online と Skype for business:** 最大 50 deps を作成できます。 
  
 **SharePoint Online と OneDrive for business:** DEP は、1つの地理的位置 (geo とも呼ばれる) のデータに適用されます。 Office 365 の複数地域機能を使用する場合は、geo ごとに1つの DEP を作成できます。 複数地域を使用していない場合は、1つの DEP を作成できます。
  
## <a name="can-i-assign-a-data-encryption-policy-before-migrating-a-mailbox-to-the-cloud"></a>メールボックスをクラウドに移行する前に、データ暗号化ポリシーを割り当てることはできますか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

はい。 Windows PowerShell コマンドレットの Set-mailuser を使用して、メールボックスを Office 365 に移行する前に、ユーザーにデータ暗号化ポリシー (DEP) を割り当てることができます。 この操作を行うと、コンテンツの移行時に、割り当てられた DEP を使用してメールボックスの内容が暗号化されます。 これは、メールボックスが既に移行された後、暗号化が行われるのを待ってから、数時間または数日かかる可能性があるため、DEP を割り当てるよりも効率的です。 
  
## <a name="how-do-i-verify-that-encryption-with-customer-key-is-activated-and-office-365-has-finished-encrypting-with-customer-key"></a>顧客キーによる暗号化がライセンス認証されており、Office 365 が顧客キーでの暗号化を完了したことを確認するには、どうすればよいですか?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online と Skype for business:**[リモート PowerShell を使用して Exchange Online に接続](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)してから、確認する各メールボックスに対して **[get-mailboxstatistics]** コマンドレットを使用することができます。 get-mailboxstatistics コマンドレットの出力では、メールボックスが暗号化されている場合は、 _IsEncrypted_プロパティは**true**の値を返し、そうでない場合は**false**に値を返します。 メールボックスが暗号化されている場合、 _dataencryptionpolicyid_プロパティに対して返される値は、メールボックスが暗号化されている DEP の GUID です。 このコマンドレットの実行の詳細については、「 [get-mailboxstatistics](https://technet.microsoft.com/en-us/library/bb124612%28v=exchg.160%29.aspx) 」および「using PowerShell with Exchange Online」を参照してください。 
  
DEP を割り当てた時点から72時間が経過した後にメールボックスが暗号化されていない場合は、メールボックスの移動を開始します。 これを行うには、[リモート PowerShell を使用して Exchange Online に接続](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)してから、new-moverequest コマンドレットを使用して、次のようにメールボックスのエイリアスを指定します。 
  
```
New-MoveRequest <alias>
```

 **SharePoint Online と OneDrive for business:**[SharePoint Online PowerShell に接続](https://technet.microsoft.com/en-us/library/fp161372.aspx)してから、 **[get-spodataencryptionpolicy]** コマンドレットを使用してテナントの状態を確認できます。 顧客キーの暗号化が有効になっており、すべてのサイトのすべてのファイルが暗号化されている場合、* * _State_* * プロパティは**登録さ**れた値を返します。 暗号化がまだ実行中の場合、このコマンドレットは、完了したサイトの割合に関する情報を提供します。 
  
## <a name="if-i-want-to-switch-to-a-different-set-of-keys-how-long-does-it-take-for-the-new-set-of-keys-to-protect-my-data"></a>別のキーセットに切り替える場合、新しいキーセットがデータを保護するのにどのくらいの時間がかかりますか?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online と Skype for business:** 新しい dep がメールボックスに割り当てられるまでの間に、新しいデータ暗号化ポリシー (DEP) に従ってメールボックスを保護するには、最大72時間かかることがあります。 
  
 **SharePoint Online と OneDrive for business:** 新しいキーが割り当てられたら、テナント全体を再暗号化するには最大4時間かかることがあります。 
  
## <a name="is-my-existing-data-stored-without-encryption-at-any-time-while-it-is-decrypted-or-encrypted-with-customer-key"></a>暗号化されているか顧客キーで暗号化されている間は、いつでも既存のデータは暗号化されていませんか?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

いいえ。 データは常に、BitLocker および DKM を使用して Office 365 サービスで保存されます。 詳細については、「Office のセキュリティ、プライバシー、コンプライアンスに関する情報」、および「 [Exchange Online が電子メールの機密情報を保護する方法](https://support.office.com/article/989BA10C-F73F-4EFB-AD1B-AF3322E5F376)」を参照してください。
  
## <a name="if-i-no-longer-want-to-use-customer-managed-encryption-keys-can-i-switch-to-microsoft-managed-keys"></a>お客様が管理する暗号化キーを使用する必要がなくなった場合、Microsoft が管理するキーに切り替えることはできますか?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online と Skype for business:** まだです。 これは、Microsoft が管理するキーを使用して Office 365 でサービス暗号化を展開するとサポートされます。 お客様のキーを使用してサービスの暗号化を解除した後、サービスでのロールアウトを期待しています。 
  
 **SharePoint Online と OneDrive for business:** うん。 Microsoft による管理キーの使用を、各 geo に対して個別に (複数地域機能を使用する場合)、またはすべてのデータに対して1つの地域内にある場合には、別の方法を選択できます。 
  
## <a name="if-i-lose-my-keys-how-long-does-it-take-to-recover-service-availability-using-the-recovery-key"></a>キーを紛失した場合、回復キーを使用してサービスの可用性を回復するのにどのくらいの時間がかかりますか?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online と Skype for business:** を呼び出して可用性キーを使用すると、数分以内にメールボックスにアクセスできるようになります。 
  
 **SharePoint Online と OneDrive for business:** この操作は、所有しているサイトの数に比例します。 Microsoft に連絡して可用性キーを使用すると、約4時間以内に完全にオンラインになります。 
  
## <a name="how-is-the-availability-key-used-with-exchange-online"></a>可用性キーは Exchange Online でどのように使用されますか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Exchange Online で可用性キーを使用するには、次の3つの方法があります。
  
- サービスの可用性-Azure キーヴォールトキーに到達できない場合。
    
- Office 365 サービスコードによって開始されたアクション (検索インデックスの作成やメールボックスの移動など)。
    
- 単一の DEP に関連付けられている Azure キーヴォールトキーの両方が失われたなど、重要な損失からの回復。
    
 **[可用性キーを使用してサービスを利用できるようにするのには、Azure キーコンテナーキーは到達できません。**
  
Office 365 では、Exchange Online の問題のある顧客のキー状態からサービスの可用性と回復を行うために、可用性キーを使用しています。 顧客キーによって使用されるキーの階層があります。 この階層を次の図に示します。
  
![](media/a760156b-737f-469a-80ab-c28b7a8b9160.png)
  
単一のデータ暗号化ポリシー (DEP) の両方の Azure キーヴォールトキーが使用できない場合、Office 365 は可用性キーを使用して新しい DEP に変更することができます。 Office 365 は、ユーザーが開始したアクティビティ (ユーザーが Outlook クライアントに電子メールをダウンロードした場合など)、またはインデックス処理のようなシステムで開始されたアクティビティであるかどうかによって、サービスの可用性に可用性キーを使用するかどうかを決定します。メールボックスの内容、または電子情報開示検索の場合は、プロセスがトリガーされます。
  
Office 365 は、ユーザーが開始する操作に応答して、ユーザーメールボックスに対して可用性キーを使用するかどうかを判断するために、このプロセスに従います。
  
1. Office 365 は、Azure Key Vault で2つの顧客キーの場所を決定するために、メールボックスが割り当てられている DEP を読み取ります。
    
2. Office 365 は、dep から2つの顧客キーのいずれかをランダムに選択し、顧客キーを使用して dep キーの折り返しを解除するために、Azure key Vault に要求を送信します。
    
3. 顧客キーを使用して DEP キーの折り返しを要求し、エラーが返された場合、Office 365 は2番目の要求を Azure key Vault に送信します。このとき、代替 (2 番目の) 顧客キーを使用するように指示します。
    
4. 顧客キーを使用して DEP キーの折り返しを解除する2番目の要求が失敗し、エラーが返された場合、Office 365 は両方の要求の結果を調べます。
    
  - エラーが顧客 id による明示的なアクションを反映していないことが検証で判断された場合、Office 365 は可用性キーを使用して DEP キーを復号化します。 次に、DEP キーを使用して、メールボックスキーを復号化し、ユーザー要求を完了します。
    
    この場合、Azure Key Vault は何らかの理由で応答できないか、到達不能になります。 Office 365 には、お客様がキーへのアクセスを意図的に取り消さたかどうかを判断する手段はありません。
    
  - お客様のキーが利用できないことを表示するために意図的に処理されたことを調査で示した場合は、可用性キーは使用されず、ユーザー要求は失敗し、ログイン失敗などのエラーメッセージが表示されます。
    
    このような状況が発生すると、お客様はサービスが影響を受け、顧客キーが正常でないということを認識できるようになります。 たとえば、お客様が組織内のすべてのメールボックスに対して単一の DEP を使用している場合、ユーザーが自分のメールボックスにアクセスできないという、広範囲なエラーが発生する可能性があります。 これにより、両方の顧客キーが正常に機能していない場合に、状況を修正してサービスを正常な状態に復元する必要があることをお客様が認識できるようになります。
    
 **Office 365 サービスコードによって開始されたアクションに対して可用性キーを使用する。**
  
Office 365 サービスコードには常に有効なログイントークンがあり、ブロックすることはできません。 そのため、可用性キーが削除されるまでは、検索インデックスの作成またはメールボックスの移動などの Office 365 サービスコードによって開始されるアクションまたは内部からのアクションに使用できます。
  
 **可用性キーを使用してキー損失から回復する。**
  
可用性キーを使用すると、よく寄せられる質問の記事「キーが破損している場合は、どのような方法で回復できますか?」で説明されているように、同じ DEP に関連付けられている両方の Azure キーヴォールトキーが失われないように復旧できます。
  
## <a name="how-is-the-availability-key-used-with-sharepoint-online-and-onedrive-for-business"></a>可用性キーは、SharePoint Online と OneDrive for business でどのように使用されますか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

SharePoint online および OneDrive for business のアーキテクチャと、顧客キーと可用性キーの実装は、Exchange Online と Skype for business とは異なります。
  
顧客が管理するキーに移動すると、Office 365 はテナント固有の中間キー (tik) を作成します。 Office 365 は、各顧客キーを使用して、tik を2回暗号化し、tik の2つの暗号化されたバージョンを格納します。 tik の暗号化バージョンのみが保存され、tik は顧客キーでのみ復号化できます。 次に、tik を使用してサイトキーを暗号化します。これは、blob キーを暗号化するために使用されます。 blob 自体は暗号化され、Microsoft Azure Blob storage サービスに格納されます。
  
Office 365 は、顧客ファイルデータがある blob にアクセスするために、このプロセスに従います。
  
1. 顧客キーを使用して、tik を復号化します。
    
2. 復号化された tik を使用して、サイトキーを復号化します。
    
3. 復号化されたサイトキーを使用して、blob キーを復号化します。
    
4. 復号化された blob キーを使用して、blob の暗号化を解除します。
    
tik の暗号化を解除すると、Office 365 は、2つの復号化要求をわずかなオフセットで Azure Key Vault に発行します。 最初の furnishes が完了し、その他の要求を取り消します。
  
お客様が顧客キーにアクセスできなくなった場合は、Office 365 は、使用可能キーを使用して tik を暗号化し、これを各顧客キーで暗号化された tik と共に格納します。 可用性キーで暗号化された tik は、お客様が Microsoft を呼び出して、キーにアクセスできなくなったときに、故意または誤って回復パスを登録する場合にのみ使用されます。
  
可用性とスケールの理由から、復号化された tiks は時間限定メモリキャッシュにキャッシュされます。 tik キャッシュを期限切れに設定する2時間前に、Office 365 は各 tik の暗号化を解除しようとします。 tiks を復号化すると、キャッシュの有効期間が延長されます。 tik 復号化が長時間に失敗すると、Office 365 はキャッシュの有効期限が切れる前にエンジニアリングに通知する警告を生成します。 お客様が microsoft を呼び出している場合にのみ、Office 365 が回復操作を開始します。これには、microsoft のシークレットストアに格納されている可用性キーを使用して tik の暗号化を解除し、暗号化された tik と新しいセットのセットを使用して、もう一度テナントをオンにします。ユーザーが指定した Azure Key Vault キー。
  
現時点では、顧客キーは Azure blob ストアに保存されている sharepoint online ファイルデータの暗号化と復号化チェーンに関係していますが、SQL データベースに格納されている sharepoint online のリストアイテムまたはメタデータは含まれていません。 Office 365 では、SharePoint Online または OneDrive for business の可用性キーを使用しません。これは、お客様が開始したケースとは異なります。 お客様のデータへのアクセスは、顧客のロックボックスで保護されています。
  
## <a name="how-is-customer-key-licensed"></a>顧客キーライセンスの方法
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

顧客キーは、Office 365 Enterprise Suite、"E5"、および Advanced コンプライアンス SKU で提供されます。 また、お客様は、Azure Key Vault を使用するための適切なライセンスも購入する必要があります。
  
顧客キーでカバーされるようにするには、顧客キーによる各ユーザーの利点がライセンス供与されている必要があります。
  
SharePoint Online では、顧客キーを構成する Office 365 管理者がライセンスを供与する必要があり、セットアップ手順を実行することも必要です。 さらに、この機能を利用できるようにするユーザーは、ライセンスを付与する必要があります。これには、サイトの所有者と、顧客キーを使用して暗号化された1つ以上のサイト上のファイルにアクセスするすべてのユーザーが含まれます。 顧客キーを使用して暗号化された1つ以上のサイトのファイルにアクセスするために、外部ユーザーにライセンスを付与する必要はありません。
  
Exchange Online の場合、"ユーザー" メールボックスおよび "メールユーザー" メールボックスがライセンスである必要があります。 共有メールボックスなど、他のすべてのユーザーが顧客キーのライセンスを持っている必要はありません。 Exchange Online メールボックスのライセンスが適切に付与されているかどうかを確認するには、次のコマンドレットを実行します。
  
```
(Get-Mailbox <alias >).PersistedCapabilities
```

文字列 BPOS_S_EquivioAnalytics が存在する場合、メールボックスは適切にライセンスされています。 それ以外の場合は、このメールボックスの顧客キー機能を使用するために、適切なライセンスを適用する必要があります。
  
## <a name="can-i-enable-customer-key-for-a-trial-subscription"></a>試用版サブスクリプションのカスタマーキーを有効にすることはできますか?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

いいえ。 定義では、試用版サブスクリプションの有効期間は限られています。 試用版サブスクリプションでホストされている暗号化キーは、試用期間の終了時に失われる可能性があります。 Microsoft は、お客様が試用版サブスクリプションに重要な顧客データを配置することを防ぐことはできません。試用版サブスクリプションでの顧客キーの使用は禁止されています。
  
## <a name="how-much-will-using-customer-key-cost"></a>顧客キーのコストをどの程度使用するか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

顧客キーに必要なライセンスに加えて、お客様は重要な資格情報を使用するためのコストを発生させることができます。 [Azure Key Vault の価格の詳細](https://azure.microsoft.com/en-us/pricing/details/key-vault/)は、コストモデルを説明し、見積もりを支援します。 利用状況のパターンは変化するため、顧客が受ける正確なコストを予測する方法はありません。 コストが非常に低く、一般に、月ごとに $0.002 ~ $0.005 の範囲で、HSM によってバックアップされたキーのコストがあることが示されています。 コストは、お客様が選択したログ構成や、azure Key Vault ログに使用される azure ストレージの量によっても異なります。 
  
## <a name="for-more-information"></a>関連情報
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

顧客キーを使用して作業を開始するには、「 [Office のキーを使用して Office 365 でデータを管理](controlling-your-data-using-customer-key.md)する」を参照してください。
  

