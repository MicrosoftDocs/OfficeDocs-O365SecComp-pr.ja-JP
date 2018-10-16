---
title: Office 365 のよく寄せられる質問のための、顧客キーによるサービスの暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 41ae293a-bd5c-4083-acd8-e1a2b4329da6
description: だけでなく、ベースラインでは、BitLocker と分散キー マネージャー (DKM) の使用を有効にするボリューム ・ レベルの暗号化は、Office 365 は、Exchange のデータを含む、Office 365 でお客様のコンテンツをアプリケーション レベルでの暗号化の層を追加を提供しています。オンラインで Skype のビジネス、オンラインでの SharePoint およびビジネスのための OneDrive です。これは、サービスの暗号化と呼ばれます。
ms.openlocfilehash: ceba35233872bb65b7706ed4e11a263057adc6c1
ms.sourcegitcommit: 659b5f5b38ef7e838cdb44eaa38c18e48d922768
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2018
ms.locfileid: "25575331"
---
# <a name="service-encryption-with-customer-key-for-office-365-faq"></a>Office 365 のよく寄せられる質問のための、顧客キーによるサービスの暗号化

だけでなく、ベースラインでは、BitLocker と分散キー マネージャー (DKM) の使用を有効にするボリューム ・ レベルの暗号化は、Office 365 は、Exchange のデータを含む、Office 365 でお客様のコンテンツをアプリケーション レベルでの暗号化の層を追加を提供しています。オンラインで Skype のビジネス、オンラインでの SharePoint およびビジネスのための OneDrive です。これは、サービスの暗号化と呼ばれます。
  
顧客キーは、サービスの暗号化が適用されを提供し、[オンライン サービスの用語 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)の説明に従って、Office 365 の残りの部分でデータの暗号化に使用されるコントロールのキーを有効にします。顧客キーは、Office 365 を使用してデータを復号化する暗号化キーを制御するための遵守義務を達成することができます。
  
顧客キーを文書などに関するフィードバックを提供するには、customerkeyfeedback@microsoft.com に、アイデア、提案、および視点を送信します。
  
## <a name="what-is-service-encryption-with-customer-key"></a>顧客キーを使用してサービスの暗号化とは何ですか。

顧客キーには、クラウド サービス プロバイダーとキーの配置を指定するためのコンプライアンス要件に対応する組織の機能が強化されます。顧客のキーを使用して提供して、Office 365 で保存データ、アプリケーション レベルの暗号化キーを制御します。その結果、コントロールを練習して、組織のキーを無効するには、サービスを終了する必要があります。キーを取り消すと、データはサービスに読み取り可能ではありません。キーの失効は、データ削除の方向にパス上の最初のステップです。

## <a name="what-office-365-data-at-rest-is-covered-by-customer-key"></a>残りの部分にどのような Office 365 のデータは、お客様のキーで覆われていますか。
<a name="WhatDataIsCoveredbyCustomerKey"> </a>

SharePoint Online サイトのコンテンツ、そのサイトに保存されているファイル、およびビジネスのための OneDrive にアップロードされたファイルは、説明します。Exchange Online のメールボックスの内容 (電子メールの本文、予定表エントリ、および電子メールの添付ファイルのコンテンツ) が記載されています。ビジネス用の Skype からテキスト会話網羅されますが、Skype 会議のブロードキャストの記録と Skype ミーティング コンテンツのアップロードは説明しません。Skype 会議をブロードキャストし、Skype の会議のコンテンツのアップロードは、Office 365 でその他のすべてのコンテンツと共に暗号化されますは現時点では暗号化キーのユーザー コントロールです。
  
## <a name="what-is-the-difference-between-customer-key-and-bring-your-own-key-byok-with-azure-information-protection-for-exchange-online"></a>顧客キーと表示の独自キー (BYOK) Exchange Online の Azure 情報の保護との違いは何ですか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

両方のオプションを提供し、独自の暗号化キーを制御することを有効にします。顧客キーを使用してサービスの暗号化が、Exchange Online の情報保護を Azure に BYOK、データの転送中に暗号化を示し、永続的なオンラインとオフラインのときに、Office 365 のサーバーの両方に存在する残りの部分で、データを暗号化する、電子メール メッセージおよび添付ファイルには、Office 365 を保護します。顧客キーおよび Exchange Online の情報保護を Azure に BYOK は、補完的でき、Microsoft のサービス管理のキーと、独自のキーを使用することを選択するかどうか、データの保存と転送中に暗号化の保護を追加悪意のある攻撃です。
  
Exchange Online の情報保護を Azure に BYOK は、Office 365 のメッセージの暗号化機能で提供されています。
  
## <a name="does-office-365-message-encryption-and-bring-your-own-key-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>Office 365 のメッセージの暗号化と表示、独自のキー Azure の情報保護のアプローチに変更令状などのサード パーティのデータ要求でしょうか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

違います。提供し、Azure の情報の保護 (AIP) の独自の暗号化キーを表示、固有キー (BYOK) を制御するには、office 365 のメッセージの暗号化と、オプションが、法執行令状への応答には設計されていません。AIP の BYOK と office 365 のメッセージの暗号化は、内部または外部の遵守の義務を満たすために必要なコンプライアンスに重点を置いてお客様に設計されています。非常に真剣に、マイクロソフトでは顧客データの要求をサード ・ パーティ製です。クラウド ・ サービス ・ プロバイダーとして、私たちが顧客データのプライバシー保護のため推奨常になりました。令状を取得して、イベントには常にターゲットを変更しようサード ・ パーティ情報の取得をお客様に。(Brad Smith のブログを参照してください:[政府のスヌーピング (のぞき見) から顧客データの保護](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。受信要求の詳細な情報を定期的に公開して[ここで](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)。
  
サード ・ パーティ製データ要求に関する[マイクロソフトのセキュリティ センター](https://www.microsoft.com/en-us/trustcenter/default.aspx)と暴露の顧客の詳細については、[オンライン サービスの用語 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)を参照してください。
  
## <a name="does-service-encryption-with-customer-key-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>顧客キーを使用してサービスの暗号化は、令状などのサード ・ パーティ製データ要求に対するマイクロソフトのアプローチを変更しますか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

違います。顧客キーが、法執行令状への応答には設計されていません。これは、内部または外部の遵守の義務を満たすために規制対象のお客様向けに設計されました。非常に真剣に、マイクロソフトでは顧客データの要求をサード ・ パーティ製です。クラウド ・ サービス ・ プロバイダーとして、私たちが顧客データのプライバシー保護のため推奨常になりました。令状を取得して、イベントには常にターゲットを変更しようサード ・ パーティ情報の取得をお客様に。(Brad Smith のブログを参照してください:[政府のスヌーピング (のぞき見) から顧客データの保護](http://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。受信要求の詳細な情報を定期的に公開して[ここで](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)。
  
サード ・ パーティ製データ要求に関する[マイクロソフトのセキュリティ センター](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)と暴露の顧客の詳細については、[オンライン サービスの用語 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)を参照してください。 
  
## <a name="is-fasttrack-support-available-for-implementing-customer-key"></a>FastTrack サポートを顧客キーを実装するために利用可能ですか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

違います。FastTrack は顧客のキーの登録に必要なテナントとサービスの構成情報を収集するためにのみ使用されます。同じメソッドを使用して必要な情報を送信するには、顧客やパートナーとお客様は、提供サービスの提供するデータをアーカイブするの容易にするために便利になるよう、FastTrack 経由で顧客のキーは発行されます。
  
マニュアル以外の追加のサポートが必要な場合についてマイクロソフト コンサルティング サービス (MCS)、プレミア フィールド エンジニア リング (PFE)、またはマイクロソフト パートナーに問い合わせてください。
  
## <a name="if-my-keys-are-destroyed-how-can-i-recover"></a>場合は、キーが破棄され、復元方法でしょうか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性のキーは、管理しているルート キーの予想外の損失から回復する機能を提供します。ルート キーを紛失した場合は、マイクロソフトのサポートと Microsoft の連絡先ができます可用性キーを有効にする手順。準備して、新しいキーを使用して新しいデータの暗号化ポリシーを移行するのには、可用性のキーを使用します。 
  
## <a name="what-is-the-availability-key"></a>可用性のキーとは何ですか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性のキーは、データの暗号化ポリシーを作成するときに準備されているルート キーです。可用性のキーが格納され、Office 365 の保護が提供するサービスの暗号化で使用する顧客のキーを使用している 2 つのルート キーに機能的に似ています。キーを提供し、Azure のキーの保管場所に管理するのとは異なり、可用性のキーに直接アクセスできません。ストレージと可用性のキーのコントロールでは、Azure キー ヴォールトのキーの 3 つの理由から意図的に異なる: 最初に、可用性のキーでは Office 365 のサービスは、キーの Azure でホストされているキーにアクセスできないこと、高可用性機能が用意されていますボルトです。次に、可用性のキー機能が備わっている「ガラスの破壊」イベントで両方の Azure キー ヴォールト ・ キーは失われます。3 番目に、論理コントロールの分離は多層防御を提供し、1 つの攻撃からのすべてのキーの損失または障害が発生した時点から保護します。されるすべてのキー (およびそのためのデータ) が失われたり破棄されるリスクを軽減することが最終的にキー管理は、さまざまな保護機能とプロセスを使用しているときに、キーを保護する責任を共有します。マイクロソフトに、唯一の権限を持つする可用性のキーの破壊の上に提供します。仕様では、マイクロソフトでは、可用性のキーへのアクセス - は Office 365 サービスのコードによってアクセスできるようにします。
  
## <a name="how-many-data-encryption-policies-deps-can-i-create"></a>データ暗号化ポリシー (DEPs) の数を作成できますか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **オンラインの Exchange およびビジネス用の Skype:** DEPs を 50 個まで作成できます。 
  
 **オンラインの SharePoint とビジネスの OneDrive:** DEP は、地域とも呼ばれる 1 つの地理的位置のデータに適用されます。Office 365 の複数の地域の機能を使用する場合は、地域ごとの 1 つの DEP を作成できます。DEP. の 1 つを作成するには複数の地域を使用していない場合
  
## <a name="can-i-assign-a-data-encryption-policy-before-migrating-a-mailbox-to-the-cloud"></a>メールボックスをクラウドに移行する前にデータの暗号化ポリシーを割り当てるには?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

うん。(DEP) のデータ暗号化のポリシーを割り当てるには、Windows PowerShell コマンドレット セット ユーザを使用するには Office 365 にメールボックスを移行する前にユーザーにします。これを行うと、コンテンツの移行に割り当てられている DEP を使用してメールボックスの内容が暗号化されます。これは、メールボックスが既に移行された後に、DEP を割り当てると、暗号化を実行、かかる時間または日数を待機しているよりも効率的です。 
  
## <a name="how-do-i-verify-that-encryption-with-customer-key-is-activated-and-office-365-has-finished-encrypting-with-customer-key"></a>顧客キーで暗号化がアクティブになり、Office 365 にユーザー キーで暗号化が完了したことを確認する方法は?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **オンラインの Exchange およびビジネス用の Skype:**[リモート PowerShell を使用して Exchange Online に接続](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)することができ、チェックする各メールボックスの **[Get MailboxStatistics]** コマンドレットを使用します。Get MailboxStatistics コマンドレットの出力は、_暗号化されたチャレンジ_を返しますの場合**は true**メールボックスが暗号化されている場合と**false**の値がない場合。メールボックスが暗号化されている場合、 _DataEncryptionPolicyID_プロパティで返される値が、メールボックスが暗号化されている DEP の GUID です。このコマンドレットを実行する方法の詳細については、 [Get MailboxStatistics](https://technet.microsoft.com/en-us/library/bb124612%28v=exchg.160%29.aspx) PowerShell を使用して Exchange online を参照してください。 
  
DEP が割り当てられた時間から 72 時間の待機後、メールボックスが暗号化されない場合、メールボックスの移動を開始します。[リモート PowerShell を使用して Exchange Online に接続](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)し新規 MoveRequest コマンドレットを使用して次のように、メールボックスのエイリアスを指定します。 
  
```
New-MoveRequest <alias>
```

 **オンラインの SharePoint とビジネスの OneDrive:**[オンライン PowerShell を SharePoint に接続](https://technet.microsoft.com/en-us/library/fp161372.aspx)することができ、 **[Get SPODataEncryptionPolicy]** コマンドレットを使用して、テナントの状態を確認します。* *_状態_* * 顧客キーの暗号化を有効にし、すべてのサイト内のすべてのファイルが暗号化されている場合、プロパティが**登録されている**の値を返します。暗号化が進行中である場合は、このコマンドレットは、サイトの何パーセントが完全に情報を提供します。 
  
## <a name="if-i-want-to-switch-to-a-different-set-of-keys-how-long-does-it-take-for-the-new-set-of-keys-to-protect-my-data"></a>異なるキーのセットに切り替える場合は、所要時間はどれに新しいキーのセットのデータを保護するでしょうか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **オンラインの Exchange およびビジネス用の Skype:** 新しい DEP がメールボックスに割り当てられている時間によって、新しいデータの暗号化ポリシー (DEP) のメールボックスを保護するために、最大 72 時間かかることができます。 
  
 **オンラインの SharePoint とビジネスの OneDrive:** 新しいキーが割り当てられると、全体のテナントを再暗号化するのには、最大 4 時間がかかることができます。 
  
## <a name="is-my-existing-data-stored-without-encryption-at-any-time-while-it-is-decrypted-or-encrypted-with-customer-key"></a>既存のデータはいつでも暗号化されていないが中の暗号化を解除または顧客のキーで暗号化されたでしょうか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

違います。データが常に BitLocker と DKM と Office 365 サービスの残りの部分で暗号化します。詳細についてを参照してください、「セキュリティ、プライバシー、および Office 365 の対応情報」を[どのように Exchange Online に、電子メールの機密情報をセキュリティで保護](https://support.office.com/article/989BA10C-F73F-4EFB-AD1B-AF3322E5F376)し、。
  
## <a name="if-i-no-longer-want-to-use-customer-managed-encryption-keys-can-i-switch-to-microsoft-managed-keys"></a>場合不要になったお客様が管理する暗号化キーを使用するのには、私に切り替えることが Microsoft で管理されるキーですか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **オンラインの Exchange およびビジネス用の Skype:** まだです。これは、Microsoft 管理キーを使用して Office 365 のサービスの暗号化が広範囲にわたってロールアウト後にサポートされます。展開サービスで顧客のキーで暗号化のサービスをリリースした後と考えています。 
  
 **オンラインの SharePoint とビジネスの OneDrive:** うん。キーを使用して Microsoft 管理とは別に (複数地域の機能を使用する) 場合は、各地域のまたはすべてのデータの 1 つの地域内にある場合に元に戻すことができます。 
  
## <a name="if-i-lose-my-keys-how-long-does-it-take-to-recover-service-availability-using-the-recovery-key"></a>キーを紛失した場合は時間の回復キーを使用してサービスの可用性を回復するでしょうか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **オンラインの Exchange およびビジネス用の Skype:** 可用性のキーを使用する呼び出すと後のメールボックスは分以内にアクセスできません。 
  
 **オンラインの SharePoint とビジネスの OneDrive:** この操作は、サイトの数に比例します。可用性のキーを使用する Microsoft を呼び出すと、約 4 時間以内で完全にオンラインなります。 
  
## <a name="how-is-the-availability-key-used-with-exchange-online"></a>Exchange のオンラインでの可用性のキーの使用方法
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性のキーを使用する 3 つの方法で Exchange のオンライン。
  
- Azure キー ヴォールト ・ キーに到達できない場合は、サービス可用性
    
- Office 365 サービスのコードによって - 検索インデックスの作成など、操作が開始されるか、メールボックスを移動します。
    
- Azure キー ヴォールト ・ キーが 1 つの dep が原因で関連付けられている両方の損失などのキーの損失からの回復します。
    
 **Azure キー ヴォールト ・ キーには到達できず、イベント、サービスの可用性の可用性のキーを使用します。**
  
Office 365 は、Exchange Online のサービスの可用性と問題がある顧客のキー状態からの回復の両方の可用性のキーを使用します。顧客キーに使用するキーの階層構造があります。この階層は、次の図に示しています。
  
![](media/a760156b-737f-469a-80ab-c28b7a8b9160.png)
  
Azure キー ヴォールトの両方のキーの 1 つのデータの暗号化ポリシー (DEP) が使用できない場合は、Office 365 が利用可能時間を使用できるかどうかに応じて異なる方法でサービスの可用性の可用性のキーを使用するかどうかを決定する新しい DEP. Office 365 に変更するのにはキーをユーザーによって開始されたアクティビティでは、たとえば、ユーザーが Outlook クライアントで、または、システムが開始した活動に、メールボックスの内容のインデックス作成などの電子的証拠開示検索、電子メールをダウンロードするとトリガー プロセスです。
  
Office 365 は、ユーザーのメールボックスの可用性のキーを使用するかどうかを判断するのには、ユーザーによる操作への応答では、このプロセスを次に示します。
  
1. Office 365 は、Azure のキーの保管場所に 2 つのユーザーのキーの場所を決定するためにメールボックスが割り当てられている DEP を読み取ります。
    
2. Office 365 はランダムに、DEP からの 2 つのユーザーのキーのいずれかを選択し、顧客のキーを使用して、DEP のキーのラップを解除するキー ヴォールトを Azure に要求を送信します。
    
3. Office 365 2 番目に要求を送信 Azure キー ヴォールトでは、この時間の代替を使用するように指示する場合は、DEP のラップを解除する要求のキーを使用して、顧客のキーが失敗し、エラーが返されます (2 番目) の顧客のキーです。
    
4. 2 番目の顧客キーが失敗した場合を使用して DEP のキーのラップを解除する要求エラーが返される場合は、Office 365 には、両方の要求の結果が確認されます。
    
  - 調査では、エラーはありませんが、顧客 id で明示的なアクションを反映することを判断した場合、Office 365 は DEP キーを復号化する可用性のキーを使用しています。DEP のキーは、メールボックス キーを復号化し、ユーザーの要求を完了するに使用されます。
    
    この例では、Azure キー ヴォールトに応答しないか、または到達不能何らかの理由です。Office 365 には、お客様が意図的にキーへのアクセスを失効させた場合を判断する方法がありません。
    
  - 調査が示している場合顧客のキーを使用できない場合は、レンダリングするのにはその意図的なものの操作が行われた可用性キーは使用されません、ユーザーの要求が失敗した場合、ユーザーがログインの失敗など、エラー メッセージを受信します。
    
    このような場合、お客様はサービスへの影響は、その顧客のキーの状態が正常な状態ではありませんを認識しました。などの顧客は、組織内のすべてのメールボックスの 1 つの DEP を使用しているお客様ではユーザーがメールボックスにアクセスできない広範囲にわたる障害が発生します。こうこと両方の顧客のキーは、正常な状態が、お客様を認識した状況を修正し、サービスを正常な状態に復元する必要があります。
    
 **Office 365 サービスのコードによって開始されるアクションの可用性のキーを使用しています。**
  
Office 365 サービスのコードは常に有効なログイン トークンには、ブロックすることはできません。したがって、可用性のキーが削除されているまで、または、内部には、検索インデックスの作成など、Office 365 サービスのコード実行またはメールボックスの移動の操作を使用できます。
  
 **可用性のキーを使用して、キーの損失から回復します。**
  
可用性のキーを使用するには両方の Azure キー ヴォールト ・ キーに関連付けられている同じの DEP では、説明に従って faq に対する回答の中「場合は、キーが破棄され、復元方法ですか?」の損失から回復します。
  
## <a name="how-is-the-availability-key-used-with-sharepoint-online-and-onedrive-for-business"></a>可用性のキーの使用方法と、SharePoint Online OneDrive ビジネスのでしょうか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

SharePoint Online とビジネス アーキテクチャの OneDrive と顧客のキーと可用性のキーの実装が Exchange Online とビジネス用の Skype とは異なります。
  
顧客は、お客様が管理キーに移動したとき、Office 365 は、テナントごとに固有の中間キー (TIK) を作成します。Office 365 では、暗号化、TIK 2 回、1 回の各顧客のキー、し、TIK の 2 つの暗号化されたバージョンを格納します。TIK の暗号化されたバージョンのみが格納されていると、TIK は顧客のキーでのみ解読できます。TIK は、キーの blob の暗号化を使用して、サイトのキーの暗号化に使用されます。ブロブ自体は暗号化され、Microsoft Azure Blob ストレージ サービスに格納されています。
  
Office 365 は、お客様のファイルのデータが含まれている blob にアクセスするには、このプロセスを次に示します。
  
1. 顧客キーを使用して TIK を復号化します。
    
2. サイト キーを復号化するのにには、復号化された TIK を使用します。
    
3. キー blob の暗号化を解除するのにには、復号化されたサイトのキーを使用します。
    
4. Blob の暗号化を解除するのにには、blob の暗号化を解除したキーを使用します。
    
TIK を解読するには、Office 365 は、わずかなオフセットで Azure キーのボルトに復号化の 2 つの要求を発行します。終了する 1 つ目は、他の要求をキャンセルする、結果を提供します。
  
顧客は、顧客キーへのアクセスを失った、場合に、Office 365 も可用性キーを使用して、TIK を暗号化し、これとは、各顧客のキーで暗号化された TIKs に格納します。可用性のキーで暗号化された TIK は、お客様が故意にまたは誤って、自分のキーにアクセスを紛失した場合は、リカバリ ・ パスを登録するのには Microsoft を呼び出すときにのみに使用されます。
  
可用性とスケール上の理由からでは、復号化された TIKs は、期間限定のメモリ キャッシュにキャッシュされます。TIK キャッシュは有効期限を設定する前に、2 時間 Office 365 は、各 TIK を復号化を試行します。キャッシュの有効期間を拡張する、TIKs を復号化します。TIK の復号化は、かなりの時間に失敗した場合、Office 365 には、キャッシュの有効期限の前にエンジニア リングを通知する警告が生成されます。お客様がマイクロソフトを呼び出す場合にのみ、Office 365 を開始 TIK と一連の新しいマイクロソフトの秘密のストアと、復号化を使用してテナントを契約時に格納されている可用性のキーを持つ TIK 復号化するには、リカバリ ・ オペレーションAzure キー ヴォールト ・ キーをお客様が提供されます。
  
、今日の時点では、顧客キーは、Azure blob ストアがオンラインの SharePoint リスト アイテムではなくまたは SQL データベースに格納されているメタデータに格納されている SharePoint のオンラインのファイル ・ データの暗号化と復号化のチェーンに関与します。Office 365 では、可用性のキー SharePoint Online またはビジネスのための OneDrive 以外の場合、上記で説明したが開始されたお客様は使用しません。お客様のロック ボックスに、顧客データへのアクセスを人間が保護されています。
  
## <a name="how-is-customer-key-licensed"></a>顧客キー ライセンスの取得方法でしょうか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

顧客キーは、Office 365 のエンタープライズ スイート、「E5」および、高度なコンプライアンス SKU で提供されていますいます。さらに、お客様は、Azure キー ヴォールトを使用するための適切なライセンスを購入もする必要があります。
  
顧客キーからメリットを享受する各ユーザーは、お客様のキーで対応する場合はライセンスを取得する必要があります。
  
SharePoint online では、お客様のキーを設定する Office 365 管理者は、セットアップの手順を実行するのには、ライセンスを取得するも必要です。さらに、機能のメリットは、ユーザーがライセンスを取得する必要があります -、サイトの所有者および顧客のキーを使用して暗号化された 1 つまたは複数のサイト上のファイルにアクセスするすべてのユーザーが含まれます。外部ユーザーは、顧客のキーを使用して暗号化された 1 つまたは複数のサイトのファイルにアクセスするのにはライセンスを取得する必要はありません。
  
Exchange online では、ユーザーのメールボックスおよびメール ユーザーのメールボックスが許可されていなければなりません。顧客キーのライセンスを所有する他のすべて、共有メールボックスなど必要はありません。オンラインの Exchange メールボックスが正しくライセンスされていることを確認するには、次のコマンドレットを実行します。
  
```
(Get-Mailbox <alias >).PersistedCapabilities
```

文字列 BPOS_S_EquivioAnalytics が存在する場合、メールボックスはライセンスが適切です。それ以外の場合は、このメールボックスのユーザーのキーの機能を使用するために適切なライセンスを適用する必要があります。
  
## <a name="can-i-enable-customer-key-for-a-trial-subscription"></a>試用版サブスクリプションの顧客のキーを有効にできますか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

違います。試用版サブスクリプションの定義では、限られた有効期間があります。試用版サブスクリプションでホストされている暗号化キーが試用版の有効期間の終了時失われます。Microsoft できません、試用版サブスクリプションに重要な顧客データを配置することからお客様ができないために、試用版サブスクリプションを持つ顧客のキーの使用は禁止されています。
  
## <a name="how-much-will-using-customer-key-cost"></a>顧客キーのコストを使用するにはどのくらいですか。
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

顧客キーに必要なライセンス、だけでなく顧客キー ヴォールトを使用するためのコストが発生します。[Azure キー ヴォールトの価格の詳細](https://azure.microsoft.com/en-us/pricing/details/key-vault/)は、コスト ・ モデルを説明し、見積もりをお手伝い。使用パターンが異なるため、お客様にかかる原価を正確に予測する方法はありません。経験によれば、コストが非常に低くなり、範囲の 0.002 ドルに $0.005 1 ユーザーあたり月額とキーの HSM ・ バックアップのコスト内で一般的になったことです。コストは、顧客と Azure キー ヴォールト ・ ログに使用される Azure のストレージの容量によって選択されたログの構成によって異なります。 
  
## <a name="for-more-information"></a>関連情報
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

顧客キーを使用して開始するには、[お客様のキーを使用して Office 365 のデータを制御する](controlling-your-data-using-customer-key.md)を参照してください。
  

