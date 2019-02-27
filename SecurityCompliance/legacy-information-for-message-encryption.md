---
title: Office 365 Message Encryption の旧来の情報
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/4/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
description: Office 365 組織を新しい OME 機能に移行していない場合でも、既に OME を展開している場合は、この記事の情報が組織に適用されます。Microsoft は、組織にとって適切であることをすぐに、新しい OME 機能に移行するための計画を立てることを推奨します。手順については、「Azure Information Protection の上に構築された新しい Office 365 メッセージ暗号化機能のセットアップ」を参照してください。新しい機能が最初にどのように機能するかについて詳しくは、「Office 365 Message Encryption」を参照してください。この記事の残りの部分では、新しい OME 機能のリリース前の OME の動作を示します。
ms.openlocfilehash: f6e407208735a53b98033e58a6f7b36fe9a37f62
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276067"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Office 365 Message Encryption の旧来の情報

Office 365 組織を新しい OME 機能に移行していない場合でも、既に OME を展開している場合は、この記事の情報が組織に適用されます。Microsoft は、組織にとって適切であることをすぐに、新しい OME 機能に移行するための計画を立てることを推奨します。手順については、「 [Azure Information Protection の上に構築された新しい Office 365 メッセージ暗号化機能のセットアップ](set-up-new-message-encryption-capabilities.md)」を参照してください。新しい機能が最初にどのように機能するかについて詳しくは、「 [Office 365 Message Encryption](ome.md)」を参照してください。この記事の残りの部分では、新しい OME 機能のリリース前の OME の動作を示します。
  
Office 365 メッセージの暗号化では、組織内のユーザーと外部のユーザーとの間で暗号化された電子メールメッセージの送受信を行うことができます。Office 365 メッセージの暗号化は、Outlook.com、Yahoo、Gmail、その他の電子メールサービスで機能します。電子メールメッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。
  
次に、いくつかの例を示します。
  
- 銀行の従業員がクレジットカードの明細書を顧客に送信する
    
- 保険会社の担当者は、顧客にポリシーの詳細を提供します。
    
- 抵当ブローカーは、顧客からローン申請の財務情報を要求します。
    
- 医療保険会社が患者に医療保険情報を送信する
    
- 弁護士が顧客または別の弁護士に機密情報を送信する
    
## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>新機能なしで Office 365 メッセージの暗号化がどのように機能するか

Office 365 Message Encryption は、Microsoft azure Rights Management (azure RMS) に基づいて構築されたオンラインサービスです。Azure RMS では、管理者はメールフロールールを定義して、暗号化の条件を決めることができます。たとえば、特定の受信者に宛てたすべてのメッセージの暗号化を必要とするルールがあります。
  
この短いビデオを見て、Office 365 メッセージの暗号化が新機能なしでどのように動作するかを確認します。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
ユーザーが暗号化ルールに一致する電子メールメッセージを Exchange Online で送信すると、メッセージは HTML 添付ファイルと共に送信されます。受信者は、HTML 添付ファイルを開き、Office 365 メッセージ暗号化ポータルで暗号化されたメッセージを表示する指示に従います。受信者は、office 365 に関連付けられた Microsoft アカウントまたは職場または学校でサインインするか、またはワンタイムパスコードを使用して、メッセージを表示するかを選択できます。どちらのオプションでも、目的の受信者のみが暗号化されたメッセージを表示できるようにすることができます。このプロセスは、新しい OME 機能とは大きく異なります。
  
下の図は、暗号化と復号化のプロセスにおける電子メール メッセージの流れをまとめたものです。
  
![暗号化された電子メールのパスを示す図](media/O365-Office365MessageEncryption-Concept.png)
  
詳細については、[新しい OME 機能のリリース前に、「従来の Office 365 Message Encryption のサービス情報](legacy-information-for-message-encryption.md#LegacyServiceInfo)」を参照してください。
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>新しい OME 機能を使用しない Office 365 メッセージ暗号化のメールフロールールを定義する

新しい機能を使用せずに Office 365 メッセージの暗号化を有効にするには、exchange online および exchange online Protection 管理者が exchange メールフロールールを定義します。これらのルールは、電子メールメッセージを暗号化する条件、およびメッセージの暗号化を削除する条件を決定します。ルールに対して暗号化アクションが設定されている場合、ルールの条件に一致するメッセージは、送信される前に暗号化されます。
  
メールフロールールは柔軟性に富んでおり、条件を組み合わせて1つのルール内の特定のセキュリティ要件を満たすことができます。たとえば、指定したキーワードを含むすべてのメッセージを暗号化するルールを作成し、外部の受信者に送信することができます。Office 365 Message Encryption は、暗号化された電子メールの受信者からの返信を暗号化することもできます。また、電子メールユーザーにとって便利なように、これらの返信を復号化するルールを作成することができます。このようにすると、組織内のユーザーは、返信を表示するために暗号化ポータルにサインインする必要がなくなります。
  
Exchange メールフロールールの作成方法の詳細については、「 [Define rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>暗号化された電子メール メッセージの送信、表示、および返信

Office 365 メッセージの暗号化では、管理者が定義したルールに基づいて電子メールメッセージが自動的に暗号化されます。暗号化されたメッセージを含む電子メールが、添付の HTML ファイルと共に受信者の受信トレイに到着します。
  
受信者は、メッセージ内の指示に従って添付ファイルを開き、Office 365 に関連付けられた Microsoft アカウントまたは職場または学校を使用して認証を行います。受信者がどちらのアカウントも持っていない場合、暗号化されたメッセージを表示するためにユーザーがサインインするための Microsoft アカウントを作成することができます。または、受信者はメッセージを表示するための1回限りのパスコードを取得することもできます。サインインまたはワンタイムパスコードを使用すると、受信者は復号化されたメッセージを表示し、暗号化された応答を送信できます。
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>Office 365 メッセージの暗号化を使用して暗号化されたメッセージをカスタマイズする

exchange online および exchange online Protection 管理者は、暗号化されたメッセージをカスタマイズできます。たとえば、会社のブランドとロゴを追加したり、概要を指定したり、暗号化されたメッセージや、受信者が暗号化されたメッセージを表示するポータルで、免責事項のテキストを追加したりすることができます。Windows PowerShell コマンドレットを使用すると、暗号化された電子メールメッセージの受信者向けに、次のような表示環境をカスタマイズできます。
  
- 暗号化メッセージを含む電子メールの導入部のテキスト
    
- 暗号化メッセージを含む電子メールの免責事項のテキスト
    
- メッセージ表示ポータルに表示されるポータルのテキスト
    
- 電子メール メッセージおよび表示ポータルに表示されるロゴ
    
いつでも既定のルック アンド フィールに戻すこともできます。
  
以下の例は、電子メールの添付ファイルに表示される ContosoPharma のカスタム ロゴです。
  
![暗号化メッセージ ページの表示例](media/TA-OME-3attachment2.jpg)
  
 **暗号化の電子メールメッセージと暗号化ポータルを組織のブランドでカスタマイズするには**
  
1. 「リモート[powershell を使用して exchange online に接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated)」の説明に従って、リモート powershell を使用して exchange online に接続します。
    
2. 次の説明に従って、omeconfiguration 設定コマンド[](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)レットを使用します。この場合、ガイダンスについては、次の表を参照してください。 
    
   **暗号化のカスタマイズ オプション**

|**カスタマイズする暗号化エクスペリエンスの特性**|**使用する Windows PowerShell コマンド**|
|:-----|:-----|
|暗号化された電子メール メッセージに付けられる既定のテキスト  <br/> 暗号化メッセージの表示手順の上に表示される既定のテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"`  <br/> |
|暗号化メッセージを含む電子メールの免責文  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"`  <br/> |
|暗号化メールの表示ポータルの最上部に表示されるテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"`  <br/> |
|ロゴ  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **例:** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)`  <br/> サポートされているファイル形式: .png、.jpg、.bmp、.tiff  <br/> ロゴ ファイルの最適なサイズ:40 KB 未満  <br/> 最適なロゴ画像のサイズ:170x70 ピクセル  <br/> |
   
 **暗号化の電子メールメッセージおよび暗号化ポータルからブランドのカスタマイズを削除するには**
  
1. 「リモート[powershell を使用して exchange online に接続する](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)」の説明に従って、リモート powershell を使用して exchange online に接続します。
    
2. 次の説明に従って、omeconfiguration 設定コマンド[](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)レットを使用します。組織のブランド化されたカスタマイズを DisclaimerText、emailtext、および PortalText の値から削除するには、値を`""`空の文字列に設定します。ロゴなどのすべてのイメージ値について、値を`"$null"`に設定します。
    
   **暗号化のカスタマイズ オプション**

|**この暗号化の機能を既定のテキストと画像に戻すには**|**使用する Windows PowerShell コマンド**|
|:-----|:-----|
|暗号化された電子メール メッセージに付けられる既定のテキスト  <br/> 暗号化メッセージの表示手順の上に表示される既定のテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`  <br/> |
|暗号化メッセージを含む電子メールの免責文  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`  <br/> |
|暗号化メールの表示ポータルの最上部に表示されるテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **既定値に戻す例:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|ロゴ  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **既定値に戻す例:**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
   
## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>新しい OME 機能のリリース前の従来の Office 365 メッセージ暗号化のサービス情報
<a name="LegacyServiceInfo"> </a>

次の表では、新しい OME 機能のリリース前の Office 365 Message Encryption サービスに関する技術情報を提供します。
  
|**サービスの詳細情報**|**説明**|
|:-----|:-----|
|クライアント デバイスの要件  <br/> |暗号化されたメッセージは、Form Post をサポートする最新のブラウザーで HTML 添付ファイルを開くことができれば、任意のクライアント デバイスで表示できます。  <br/> |
|暗号化アルゴリズムと連邦情報処理規格 (FIPS) への準拠  <br/> |Office 365 Message encryption は、Windows Azure Information Rights Management (IRM) と同じ暗号化キーを使用し、暗号化モード 2 (RSA の場合は2k キー、sha-1 システムの場合は256ビットキー) をサポートします。基礎となる IRM 暗号化モードの詳細については、「 [AD RMS 暗号化モード](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx)」を参照してください。<br/> |
|サポートされているメッセージの種類  <br/> |Office 365 メッセージの暗号化は、メッセージクラス ID が IPM であるアイテムに対してのみサポートされ**ます。メモ**。詳細については、「 [Item types and message classes](https://msdn.microsoft.com/library/office/ff861573.aspx)」を参照してください。<br/> |
|メッセージ サイズの制限  <br/> |Office 365 Message Encryption は、最大25メガバイトのメッセージを暗号化できます。メッセージサイズの制限の詳細については、「 [Exchange Online の制限](http://technet.microsoft.com/library/exchange-online-limits.aspx)」を参照してください。<br/> |
|Exchange Online の電子メールアイテム保持ポリシー  <br/> |Exchange Online は、暗号化されたメッセージを保存しません。  <br/> |
|Office 365 Message Encryption の言語サポート  <br/> | Office 365 Message Encryption は、以下のように Office 365 の言語をサポートします。  <br/>  受信メールメッセージと添付 HTML ファイルは、送信者の言語設定に基づいてローカライズされます。  <br/>  表示するためのポータルは、受信者のブラウザーの設定に基づいてローカライズされます。  <br/>  暗号化されたメッセージの本文 (コンテンツ) は、ローカライズされません。  <br/> |
|OME ポータルと OME Viewer アプリの個人情報  <br/> |[Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md) には、お客様の個人情報を使用して Microsoft が行うことと行わないことについて詳しく記されています。  <br/> |
   
## <a name="frequently-asked-questions-about-legacy-ome"></a>従来の OME についてよく寄せられる質問
<a name="LegacyServiceInfo"> </a>

Office 365 メッセージの暗号化についての質問いくつかの答えを次に示します。必要な情報が見つからない場合は、「office 365 コミュニティフォーラム ( [office 365 community](http://community.office365.com/en-us/forums/default.aspx))」を確認してください。
  
 **Q: ユーザーが暗号化された電子メールメッセージを組織外の受信者に送信します。Office 365 メッセージの暗号化で暗号化された電子メールメッセージの読み取りと返信を行うために、外部の受信者が行う必要があることはありますか。**
  
Office 365 で暗号化されたメッセージを受信する組織外部の受信者は、以下の 2 つの方法のいずれかでそのメッセージを表示できます。
  
- office 365 に関連付けられた Microsoft アカウントまたは職場または学校のアカウントを使用してサインインします。
    
- ワンタイムパスコードを使用します。
    
 **Q. Office 365 の暗号化されたメッセージはクラウドまたは Microsoft サーバーに保存されますか。**
  
いいえ、暗号化されたメッセージは受信者の電子メールシステムに保持され、受信者がメッセージを開いたときに、Office 365 サーバーに表示するために一時的に投稿されます。メッセージはそこに格納されません。
  
 **Q. 暗号化された電子メール メッセージを独自のブランドでカスタマイズすることはできますか。**
  
はい。Windows PowerShell コマンドレットを使用して、暗号化された電子メール メッセージの上に表示する既定のテキスト、免責事項テキスト、および電子メール メッセージや暗号化ポータルに使用するロゴをカスタマイズできます。詳細については、「[Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md)」を参照してください。
  
 **Q. このサービスは組織内のすべてのユーザーに対して 1 つのライセンスが必要ですか。**
  
暗号化された電子メールを送信する組織内のすべてのユーザーに対して 1 つのライセンスが必要です。
  
 **Q. 外部の受信者はサブスクリプションが必要ですか。**
  
いいえ。外部の受信者は、暗号化されたメッセージを読んで返信するためにサブスクリプションを必要としません。 
  
 **Q: Office 365 メッセージの暗号化は、Rights Management Services (RMS) とはどのような違いがありますか?**
  
RMS は、次のような組み込みのテンプレートを提供することによって、組織の内部電子メールに関する情報権限保護機能を提供します。「転送不可」および「会社の機密」Office 365 Message encryption は、外部の受信者や内部の受信者に送信されるメッセージの電子メールメッセージの暗号化をサポートしています。
  
 **Q: Office 365 メッセージの暗号化は S/MIME とはどのような違いがありますか?**
  
S/MIME は、基本的に、クライアント側の暗号化テクノロジであり、複雑な証明書管理と発行インフラストラクチャが必要です。Office 365 Message Encryption は、トランスポート ルールを使用するため、証明書の発行に依存しません。
  
 **Q. モバイル デバイスで暗号化されたメッセージを読むことはできますか。**
  
はい、 [Google Play ストア](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409)および[Apple App store](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409)から OME Viewer アプリをダウンロードすることによって、Android および iOS のメッセージを表示することができます。OME ビューアアプリで HTML 添付ファイルを開き、指示に従って暗号化されたメッセージを開きます。他のモバイルデバイスでは、メールクライアントがフォームの Post をサポートしている限り、HTML 添付ファイルを開くことができます。
  
 **Q. 返信や転送されたメッセージは暗号化されますか。**
  
はい。返信はスレッド期間の間、暗号化されます。
  
 **Q. Office 365 Message Encryption にはローカライズ機能がありますか。**
  
受信電子メールと HTML コンテンツは、送信者の電子メール設定に基づいてローカライズされます。表示ポータルは、受信者のブラウザー設定に基づいてローカライズされます。ただし、暗号化されたメッセージの本文 (コンテンツ) はローカライズされません。
  
 **Q. Office 365 Message Encryption ではどのような暗号化方式が使用されますか。**
  
Office 365 Message Encryption では、Rights Management サービス (RMS) が暗号化インフラストラクチャとして使用されます。使用される暗号化方式は、メッセージの暗号化と復号化に使用する RMS キーを取得する場所によって異なります。
  
- Microsoft Azure RMS を使用してキーを取得する場合、暗号化モード2が使用されます。暗号化モード2は、更新され、拡張された AD RMS 暗号化実装です。このメソッドは、署名と暗号化に RSA 2048 をサポートし、署名に sha-1-256 をサポートします。
    
- Active Directory (AD) RMS を使用してキーを取得する場合は、暗号化モード 1 または暗号化モード 2 が使用されます。使用される方法は、社内 AD RMS 展開によって異なります。暗号化モード 1 は、元来の AD RMS 暗号実装です。この方式は署名と暗号化に RSA 1024 をサポートし、署名に関しては SHA-1 もサポートします。このモードは、引き続き RMS の現在のすべてのバージョンでサポートされています。
    
詳細については、「 [AD RMS 暗号化モード](http://go.microsoft.com/fwlink/p/?LinkId=398616)」を参照してください。
  
 **Q. 一部の暗号化メッセージには Office365@messaging.microsoft.com から送られていると表示されているのはなぜですか?**
  
暗号化された返信が暗号ポータルから、または OME ビューアー アプリを介して送信されるとき、送信元電子メール アドレスは Office365@messaging.microsoft.com に設定されます。暗号化メッセージは Microsoft エンドポイントを介して送信されるためです。これにより、暗号化されたメッセージがスパムとしてマークされるのを回避できます。このラベルがあるため、暗号化ポータル内の電子メールとアドレスの表示名が変更されることはありません。また、このラベルが適用されるのは、ポータルを介して送信されるメッセージだけで、他の電子メール クライアントを介して送信されるメッセージには適用されません。
  
 **Q: Exchange Hosted Encryption (EHE) サブスクライバーです。Office 365 メッセージの暗号化へのアップグレードの詳細については、どこから入手できますか。**
  
すべての EHE お客様は、Office 365 Message Encryption にアップグレードされました。詳細については、「 [Exchange Hosted Encryption Upgrade Center」](http://go.microsoft.com/fwlink/p/?LinkID=511077)を参照してください。
  
 **Q: Office 365 メッセージの暗号化をサポートするために、組織のファイアウォール内の url、IP アドレス、またはポートを開く必要がありますか。**
  
はい。Office 365 Message Encryption によって暗号化されたメッセージの認証を有効にするには、ご自分の組織の許可リストに Exchange Online の URL を追加する必要があります。Exchange Online の URL リストについては、「[Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx)」を参照してください。
  
 **Q. Office 365 の暗号化されたメッセージは、何人まで送信できますか。**
  
暗号化されたメッセージの受信者の制限は、メッセージの "**宛先**" フィールドの文字数に基づいています。結合された場合 (配布リストの展開後)、 **** 宛先フィールドの受信者のアドレスは11980文字を超えないようにする必要があります。電子メールアドレスは文字の長さによって異なる可能性があるため、1つの暗号化されたメッセージに対して標準の受信者の制限はありません。 
  
 **Q. 特定の受信者に送信されたメッセージを取り消すことは可能ですか。**
  
違います。送信されたメッセージを特定のユーザーに対して取り消すことはできません。
  
 **Q. 受信されて既読になった暗号化メッセージのレポートを表示することはできますか。**
  
暗号化されたメッセージが表示されているかどうかを示すレポートはありませんが、特定のトランスポートルールに一致したメッセージの数を特定するために利用できる Office 365 レポートがあります (たとえば、)。
  
 **Q. OME ポータルと OME Viewer アプリで提供した情報を Microsoft はどのように使用しますか。**
  
[Office 365 Messaging Encryption ポータルのプライバシー](protected-message-viewer-portal-privacy-statement.md)に関する声明では、Microsoft が個人情報に対して実行する操作と行わないことについての詳細情報が提供されています。 
  

