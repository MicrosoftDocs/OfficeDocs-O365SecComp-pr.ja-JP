---
title: Office 365 Message Encryption に関する FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/9/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: Office 365 で新しいメッセージの保護機能のしくみについて質問があるでしょうか。ここで回答を確認します。
ms.openlocfilehash: e35495106b44ccb566f4da743264def8c7d4f96f
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696271"
---
# <a name="office-365-message-encryption-faq"></a>Office 365 Message Encryption に関する FAQ

Office 365 で新しいメッセージの保護機能のしくみについて質問があるでしょうか。ここで回答を確認します。またを見て[Azure の情報保護のデータの保護についてご質問がよく寄せられる](https://docs.microsoft.com/information-protection/get-started/faqs-rms)Azure の著作権管理、データ保護サービスに関する質問への回答の Azure の情報保護の。

||
|:-----|
|この資料は、Office 365 のメッセージの暗号化についての記事の大規模な一連の一部です。この資料は、管理者および ITPros。だけを行う場合、暗号化されたメッセージを送受信する情報は[Office 365 メッセージの暗号化 (ホーム)](ome.md)内のアーティクルの一覧を参照してくださいし、お客様のニーズに最も適した記事を検索します。 |
||
  
## <a name="what-is-office-365-message-encryption-ome"></a>Office 365 メッセージの暗号化 (ホーム) とは何ですか。

ホームでは、電子メールの暗号化と権限管理の機能を結合します。権限管理機能は、Azure の情報保護が導入されています。
  
## <a name="who-can-use-ome"></a>ホームを使用していることができますか。

ホームの新機能を使用するには次の条件。
  
- 場合は Office 365 の Exchange Online のホームまたは IRM を設定することことはありませんが。
    
- ホームと IRM のように設定した場合は、Azure の情報保護と Azure の権限の管理サービスを使用している場合にこの手順を使用できます。
    
- 使用する場合 Exchange Online では、Active Directory の権限管理サービス (AD RMS)、これらの新機能を直ちに有効にできません。代わりに、する必要があります[Azure の情報保護に AD RMS を移行](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)する最初にします。移行が終了したら、ホーム正常に設定することができます。 
    
    引き続き使用する場合は、オンプレミス AD RMS Exchange 情報の保護を Azure に移行するのではなく、オンラインにすることはできませんこれらの新機能を使用します。
    
## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>新しいホーム機能を使用する必要があるどのようなサブスクリプションをしますか。

ホームの新機能を使用するには、次のプランのいずれかが必要です。
  
- Office 365 Office 365 の E3 と E5、マイクロソフト E3 と E5、Office 365 の A1、A3、A5、および Office 365 の第 3 世代との G5 の一部としてメッセージの暗号化が提供されます。お客様では、Azure 情報保護により、新しい保護機能を表示するのには追加のライセンスは必要ありません。 
    
- Azure 情報保護計画する場合は 1 次が新しい Office 365 のメッセージの暗号化機能を受信する計画を追加することも: Exchange オンライン計画 1、Exchange オンライン計画 2、Office 365 の F1、Office 365 の業務に関する重要事項、Office 365 のビジネス プレミアム、またはOffice 365 エンタープライズ E1。
    
- 各ユーザーが Office 365 のメッセージの暗号化のメリットは、この機能によってカバーされるライセンスを取得する必要があります。
    
- 完全なリストについては、Office 365 のメッセージの暗号化の[Exchange Online のサービスの説明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)を参照してください。 
    
## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>使用できる Exchange Online で、Azure の情報保護の独自のキー (BYOK) を表示しますか?

うん！ホームを設定する前に BYOK を設定する手順を完了することをお勧めします。
  
BYOK の詳細については、[計画と Azure の情報保護のテナントのキーを実装する](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)を参照してください。
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>ホームと Azure の情報保護と BYOK を変更するマイクロソフトのアプローチ令状などのサード パーティのデータ要求にでしょうか。

違います。提供し、Azure の情報の保護からの BYOK と呼ばれる独自の暗号化キーを制御するには、ホームおよびオプションは、法律の執行令状への応答には設計されていません。Azure の情報を保護するための BYOK で、ホームは、お客様のコンプライアンスを重視した設計されています。非常に真剣に、マイクロソフトでは顧客データの要求をサード ・ パーティ製です。クラウド ・ サービス ・ プロバイダーとして、私たちが顧客データのプライバシー保護のため推奨常になりました。令状を取得して、イベントには常にターゲットを変更しようサード ・ パーティ情報の取得をお客様に。(Brad Smith のブログを参照してください:[政府のスヌーピング (のぞき見) から顧客データの保護](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。受信要求の詳細な情報を定期的に公開します。サード ・ パーティ製のデータ要求の詳細については、マイクロソフトのセキュリティ センターで[政府や顧客データにアクセスするための法律執行の要求への応答](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data)を参照してください。また、漏えいのお客様で「データ」[オンライン サービス条件 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)を参照してください。
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>従来の Office 365 メッセージの暗号化 (ホーム) および情報権利管理 (IRM) 機能にこの機能が関連するはどのようにでしょうか。

Office 365 のメッセージの暗号化のための新しい機能は、既存の IRM と従来のホーム ソリューションの発展させたものです。次の表は、詳細情報を提供します。
  
**従来のホーム、IRM では、ホームの新機能の比較**

|**機能**|**ホームの以前のバージョン**|**IRM**|**ホームの新機能**|
|:-----|:-----|:-----|:-----|
|**暗号化された電子メールを送信します。**|Exchange メール フロー ルールによってのみ|エンドユーザーが Outlook の PC、Mac 用の Outlook または Outlook は web 上から行うまたは Exchange からのメール フロー ルール|エンドユーザーが Outlook の PC、Mac 用の Outlook または Outlook は web 上から行うまたはメール フロー ルールを使用|
|**アクセス権管理**|-|転送不可のオプションとカスタム テンプレートの操作を行います|転送不可のオプション、暗号化のみのオプション、既定値、およびカスタム テンプレートの操作を行います|
|**受信者の種類をサポート**|外部受信者のみ|内部の受信者のみ|内部および外部の受信者|
|**受信者の経験**|外部の受信者は、ダウンロードし、ブラウザーで開かれているにモバイル アプリケーションをダウンロード、html 形式のメッセージを受信しました。|のみ、内部の受信者は、PC の Outlook、Outlook for Mac、および web 上の Outlook で暗号化された電子メールを受け取りました。|、IOS 用または web ポータルでは、同じ Office 365 組織または任意の Office 365 にするかどうかにかかわらず、内部および外部の受信者が PC の Outlook、Outlook for Mac、web 上で Outlook、Android では、Outlook と Outlook で電子メールを受信します。組織です。ホーム ポータルには、個別のダウンロードは不要です。|
|**独自のキーのサポートを提供します。**|使用不可|使用不可| BYOK のサポート|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>自分の所属組織のホームの新機能を有効する方法

[新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)を参照してください。
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>ホームの以前のバージョンは推奨されていませんか。

ホームの以前のバージョンを使用することができますが、この時点でない推奨されません。ただし、強くお勧め、新規あるいは強化されたホーム ソリューションを使用する組織です。ホームを配置していないお客様は、ホームの以前のバージョンの新しい展開を設定できません。
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>組織が Active Directory の権限の管理を使用して、この機能を使用できますか。

違います。使用する場合 Exchange Online では、Active Directory の権限管理サービス (AD RMS)、これらの新機能を直ちに有効にできません。代わりに、する必要があります[Azure の情報保護に AD RMS を移行](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)する最初にします。 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>自組織は、Exchange ハイブリッド展開をします。この機能を使用することができますか。

オンプレミス ユーザーがオンラインの Exchange のメール フロー ルールを使用して、暗号化されたメールを送信できます。これを行うには、Exchange のオンラインを介して電子メールをルーティングする必要があります。詳細についてを参照してください[第 2 部: メールをメール サーバーから Office 365 へのフローを構成する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)です。
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>ホームの暗号化されたメッセージを作成するために使用する必要があるどのような電子メール クライアントをしますか。保護されたメッセージを送信するためにどのようなアプリケーションがサポートされてでしょうか。

Outlook の 2016年と PC と Mac 用の Outlook 2013 および web 上の Outlook からは、保護されたメッセージを作成できます。
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>読み取りおよび保護された電子メールに返信するのには、どのような電子メール クライアントがサポートされているでしょうか。

Office 365 ユーザーの場合は、Outlook の PC と Mac (2013 および 2016)、web 上の Outlook および Outlook モバイル (Android と iOS) からの応答を読み書きできます。組織で許可される場合にも、iOS のネイティブのメール クライアントを使用できます。以外の Office 365 ユーザーの場合は、読み取りし、web ブラウザーを通じて web 上で暗号化されたメッセージに返信できます。
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>保護された電子メールの添付ファイルとしては、どのようなファイルの種類がサポートされているでしょうか。添付ファイルは保護された電子メールに関連付けられている保護ポリシーを継承しますか。

上でのみ、ファイルの形式で述べた[ここで](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)保護ポリシーが適用されますが、保護されたメールの場合は、あらゆる種類のファイルを添付できます。 
  
Word、Excel、または PowerPoint ファイルなど、ファイル形式がサポートされている場合、ファイルは常に保護、受信者が添付ファイルのダウンロードが完了した後でも。たとえば、添付ファイルは転送不可で保護されていると、元の受信者がダウンロードされ、新しい受信者に添付ファイルを転送、新しい受信者されません保護されたファイルを開くことができません。
  
## <a name="are-pdf-file-attachments-supported"></a>PDF ファイルの添付ファイルはサポートされますか。

保護されたメッセージには、PDF ファイルを添付する場合、メッセージ自体は保護されているが、追加の保護は適用されません、PDF ファイルを受信者が受信した後。つまりに限って使用するように名前を付けて保存、転送、コピー、および PDF ファイルを印刷します。
  
## <a name="are-onedrive-for-business-attachments-supported"></a>OneDrive をビジネスの添付ファイルがサポートされているのでしょうか。

まだです。ビジネスの添付ファイルの OneDrive はサポートされていませんし、エンド ・ ユーザーは、ビジネスの添付ファイルのためのクラウド OneDrive を含むメールを暗号化できません。
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>できますに自動的にメッセージの暗号化のポリシーを設定することによってでしょうか。

うん。使用してメール フロー ルール Exchange オンライン特定の条件に基づいてメッセージを自動的に暗号化します。受信者に基づくポリシーを作成することができますたとえば、ID、受信者のドメイン、またはメッセージの件名、本文の内容にします。参照してください[Office 365 で電子メール メッセージを暗号化するためにメール フローの規則を定義します](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>自動的に暗号化メッセージでデータ損失防止 (DLP)、セキュリティ ・ ポリシーを設定することによって&amp;コンプライアンス センターでしょうか。

うん！DLP を使用して、セキュリティで、Exchange のオンラインでのメール フロー ルールを設定することができます&amp;コンプライアンス センターです。
  
## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>共有メールボックスに送信された暗号化メッセージを開くことができますか。

現在の暗号化されたメッセージは、共有メールボックスではサポートされていません。

## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>暗号化されたメッセージを自分の会社ブランド設定をカスタマイズできますか。

うん！電子メール メッセージおよびホーム ポータルをカスタマイズする方法の詳細についてを参照してください暗号化されたメッセージに、組織のブランドを追加します。参照してください[、暗号化されたメッセージを組織のブランドを追加します](add-your-organization-brand-to-encrypted-messages.md)。
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>レポート作成機能や暗号化された電子メールの情報はありますか。

ではなくこの時間が準備中です。
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>電子的証拠開示などのコンプライアンス機能とメッセージの暗号化を使用できますか。

うん。すべての暗号化された電子メール メッセージは、Office 365 のコンプライアンス機能により検出可能です。
  

