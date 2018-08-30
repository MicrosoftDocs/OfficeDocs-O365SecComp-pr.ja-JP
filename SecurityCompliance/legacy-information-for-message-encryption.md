---
title: Office 365 Message Encryption の旧来の情報
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/4/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
description: ホームを既に展開しているホームの新機能を組織の Office 365 にまだ移動していない場合は、この資料の情報は、組織に適用されます。ホームの新機能、組織の適切なことがすぐに移動するための計画を作成することをお勧めします。セットを参照してください手順については、情報の保護を Azure 上に構築された、新しい Office 365 のメッセージの暗号化機能を設定します。最初の新機能の動作についての詳細を確認する場合は、Office 365 のメッセージの暗号化を参照してください。この資料の残りの部分は、ホームの新機能のリリースの前にホームの動作を意味します。
ms.openlocfilehash: d5b21cbe0004ca7bda38085bd5d8ef5f2a22b04e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532235"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Office 365 Message Encryption の旧来の情報

ホームを既に展開しているホームの新機能を組織の Office 365 にまだ移動していない場合は、この資料の情報は、組織に適用されます。ホームの新機能、組織の適切なことがすぐに移動するための計画を作成することをお勧めします。手順については、[情報の保護を Azure 上に構築された、新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)を参照してください。最初の新機能の動作についての詳細を確認する場合は、 [Office 365 のメッセージの暗号化](ome.md)を参照してください。この資料の残りの部分は、ホームの新機能のリリースの前にホームの動作を意味します。
  
Office 365 のメッセージの暗号化と、組織はことができます、組織内外のユーザーとの間で暗号化された電子メール メッセージを送受信します。Office 365 メッセージの暗号化は、Outlook.com、yahoo!、Gmail、およびその他の電子メール サービスで動作します。電子メール メッセージの暗号化の実現を促進するだけの目的の受信者は、メッセージの内容を表示できます。
  
ここで、いくつかの例を示します。
  
- 銀行従業員が顧客にクレジット カードの明細書を送信します。
    
- 保険会社の代表者のポリシーの詳細をお客様に提供します。
    
- 住宅ローン ブローカーは、ローン申し込み書の顧客から財務情報を要求します。
    
- 医療機関が患者に医療情報を送信します。
    
- 弁護士は、顧客または他の弁護士に機密情報を送信します。
    
## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Office 365 のメッセージの暗号化のしくみは、新しい機能がないです。

Office 365 のメッセージの暗号化とは、Microsoft Azure アクセス権管理 (Azure RMS) に組み込まれているオンライン サービスです。Azure の RMS の管理者は、暗号化するための条件を決定するのには、メール フロー ルールを定義できます。たとえば、ルールでは、特定の受信者宛てのすべてのメッセージの暗号化を要求できます。
  
このビデオで簡単に新しい機能がない Office 365 のメッセージの暗号化のしくみを参照してください。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
他のユーザーから電子メール メッセージが Exchange オンラインする暗号化の規則に一致すると、HTML ファイルが添付されたメッセージを送信します。受信者が HTML 添付ファイルを開くし、ポータルの Office 365 のメッセージの暗号化で暗号化されたメッセージを表示する手順に従います。Microsoft アカウントまたは作業や、Office 365 に関連付けられている学校を使用して署名することによって、または 1 回限りのパスコードを使用してメッセージを表示するのには受信者が選択できます。両方のオプションを確実に目的の受信者だけが暗号化されたメッセージを表示できます。このプロセスは、新しいホーム機能の非常に異なる。
  
下の図は、暗号化と復号化のプロセスにおける電子メール メッセージの流れをまとめたものです。
  
![暗号化された電子メールのパスを示す図](media/O365-Office365MessageEncryption-Concept.png)
  
詳細については、[ホームの新機能のリリースの前に従来の Office 365 のメッセージ暗号化のサービス情報](legacy-information-for-message-encryption.md#LegacyServiceInfo)を参照してください。
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>Office 365 のメッセージの暗号化には、ホームの新機能を使用しないメール フロー ルールを定義します。

Office 365 のメッセージの暗号化を有効に、新しい機能がないには、オンラインの Exchange および Exchange のオンライン保護管理者は、Exchange メール フロー ルールを定義します。これらのルールは、どのような条件の e メールでメッセージを暗号化するか、メッセージの暗号化を削除するための条件とを確認します。暗号化アクションをルールに設定すると、ルールの条件に一致するすべてのメッセージは、送信することをする前に暗号化されます。
  
メール フロー ルールは、柔軟性があり、1 つの規則で特定のセキュリティ要件を満たすことができますので、条件を結合すること。たとえば、指定されたキーワードが含まれているし、外部の受信者にアドレス指定されるすべてのメッセージを暗号化するためにルールを作成できます。Office 365 のメッセージの暗号化は、暗号化された電子メールの受信者からの返信も暗号化して、電子メール ユーザーの便宜のため、返信を復号化するルールを作成することができます。これにより、組織内のユーザーは、返信を表示するのには暗号化のポータルにサインインする必要はありません。
  
Exchange メール フロー ルールを作成する方法の詳細については、 [Office 365 のメッセージの暗号化のための規則の定義](define-mail-flow-rules-to-encrypt-email.md)を参照してください。
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>暗号化された電子メール メッセージの送信、表示、および返信

Office 365 のメッセージの暗号化、電子メール メッセージを自動的に暗号化されます、管理者が定義したルールに基づきます。電子メールに対する暗号化されたメッセージは、添付の HTML ファイルを使用して受信者の受信トレイに到着します。
  
受信者は、添付ファイルを開くと、Microsoft アカウントまたは作業、Office 365 に関連付けられている学校を使用して認証、メッセージの指示に従います。受信者には、いずれかのアカウントを持っていない場合、は、Microsoft 暗号化されたメッセージを表示するのにはサインインするためのアカウントを作成するのには送信しています。または、受信者はメッセージを表示するのには 1 回限りのパスコードを取得する選択できます。サインインまたは、1 回限りのパスコードを使用して後、は、受信者は復号化されたメッセージを表示し、暗号化された返信を送信します。
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>Office 365 のメッセージの暗号化と暗号化されたメッセージをカスタマイズします。

オンラインの Exchange および Exchange のオンライン保護管理者は、暗号化されたメッセージをカスタマイズできます。などの概要についてを指定し、暗号化されたメッセージと受信者が暗号化されたメッセージを表示するポータルでは、免責事項のテキストを追加、会社のブランドとロゴを追加できます。Windows PowerShell コマンドレットを使用すると、暗号化された電子メール メッセージの受信者の表示操作の次の側面をカスタマイズできます。
  
- 暗号化メッセージを含む電子メールの導入部のテキスト
    
- 暗号化メッセージを含む電子メールの免責事項のテキスト
    
- メッセージ表示ポータルに表示されるポータルのテキスト
    
- 電子メール メッセージおよび表示ポータルに表示されるロゴ
    
いつでも既定のルック アンド フィールに戻すこともできます。
  
以下の例は、電子メールの添付ファイルに表示される ContosoPharma のカスタム ロゴです。
  
![暗号化メッセージ ページの表示例](media/TA-OME-3attachment2.jpg)
  
 **電子メール メッセージを暗号化し、組織のブランドを使用して、暗号化ポータルをカスタマイズするのには**
  
1. [Exchange オンラインを使用してリモート PowerShell への接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated)で説明するようリモート PowerShell を使用して Exchange Online に接続します。
    
2. コマンドレットを使用してセット OMEConfiguration に従ってここ:[セット OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)またはガイダンスについては、次の表に使用します。 
    
   **暗号化のカスタマイズ オプション**

|**カスタマイズする暗号化エクスペリエンスの特性**|**使用する Windows PowerShell コマンド**|
|:-----|:-----|
|暗号化された電子メール メッセージに付けられる既定のテキスト  <br/> 暗号化メッセージの表示手順の上に表示される既定のテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **の使用例:**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
|暗号化メッセージを含む電子メールの免責文  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **の使用例:**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
|暗号化メールの表示ポータルの最上部に表示されるテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **の使用例:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
|ロゴ  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **の使用例:**`Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> サポートされているファイル形式: .png、.jpg、.bmp、.tiff  <br/> ロゴ ファイルの最適なサイズ:40 KB 未満  <br/> 最適なロゴ画像のサイズ:170x70 ピクセル  <br/> |
   
 **電子メール メッセージを暗号化および暗号化のポータルからブランドのカスタマイズを削除するのには**
  
1. [Exchange オンラインを使用してリモート PowerShell への接続](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)で説明するようリモート PowerShell を使用して Exchange Online に接続します。
    
2. コマンドレットを使用してセット OMEConfiguration に従ってここ:[セット OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)。組織を削除するのには、DisclaimerText、EmailText からのカスタマイズをブランドし、PortalText の値を空の文字列値を設定する`""`。すべてのイメージ、ロゴなどの値の値を設定、 `"$null"`。
    
   **暗号化のカスタマイズ オプション**

|**この暗号化の機能を既定のテキストと画像に戻すには**|**使用する Windows PowerShell コマンド**|
|:-----|:-----|
|暗号化された電子メール メッセージに付けられる既定のテキスト  <br/> 暗号化メッセージの表示手順の上に表示される既定のテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **の使用例:**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|暗号化メッセージを含む電子メールの免責文  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **の使用例:**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|暗号化メールの表示ポータルの最上部に表示されるテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **デフォルトに戻すことの使用例:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|ロゴ  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **デフォルトに戻すことの使用例:**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
   
## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>ホームの新機能のリリースの前に従来の Office 365 メッセージ暗号化のサービスの情報
<a name="LegacyServiceInfo"> </a>

次の表は、ホームの新機能のリリースの前に Office 365 のメッセージの暗号化サービスの技術的な詳細を提供します。
  
|**サービスの詳細情報**|**説明**|
|:-----|:-----|
|クライアント デバイスの要件  <br/> |暗号化されたメッセージは、Form Post をサポートする最新のブラウザーで HTML 添付ファイルを開くことができれば、任意のクライアント デバイスで表示できます。  <br/> |
|暗号化アルゴリズムと連邦情報処理規格 (FIPS) への準拠  <br/> |Office 365 のメッセージの暗号化では、Windows Azure の情報権利管理 (IRM) と同じ暗号化キーを使用して、システムの sha-1 (2 K キーを RSA) と 256 ビット キーの暗号化モード 2 をサポートしています。IRM の基になる、暗号化モードの詳細については、 [AD RMS の暗号化モード](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx)を参照してください。<br/> |
|サポートされているメッセージの種類  <br/> |Office 365 のメッセージの暗号化の**IPM メッセージ クラス ID を持つアイテムについてのみサポートされます。注**。詳細については、[項目の種類とメッセージ クラス](https://msdn.microsoft.com/library/office/ff861573.aspx)を参照してください。<br/> |
|メッセージ サイズの制限  <br/> |Office 365 のメッセージの暗号化には、25 メガバイトまでのメッセージを暗号化できます。メッセージ サイズの制限の詳細については、 [Exchange オンラインの制限](http://technet.microsoft.com/library/exchange-online-limits.aspx)を参照してください。<br/> |
|Exchange Online の電子メール保存ポリシー  <br/> |Exchange Online は、暗号化されたメッセージを格納します。  <br/> |
|Office 365 Message Encryption の言語サポート  <br/> | Office 365 Message Encryption は、以下のように Office 365 の言語をサポートします。  <br/>  受信電子メール メッセージと添付の HTML ファイルは、送信者の言語設定に基づいてローカライズされます。  <br/>  表示するためのポータルは、受信者のブラウザーの設定に基づいてローカライズされます。  <br/>  暗号化されたメッセージの本文 (コンテンツ) は、ローカライズされません。  <br/> |
|OME ポータルと OME Viewer アプリの個人情報  <br/> |[Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md) には、お客様の個人情報を使用して Microsoft が行うことと行わないことについて詳しく記されています。  <br/> |
   
## <a name="frequently-asked-questions-about-legacy-ome"></a>よく寄せられる質問については、従来のホーム
<a name="LegacyServiceInfo"> </a>

Office 365 のメッセージの暗号化についての質問ですか。ここでは、いくつかの回答をします。必要な情報が見つからない場合は、 [Office 365 コミュニティ](http://community.office365.com/en-us/forums/default.aspx)で、Office 365 コミュニティ フォーラムを確認してください。
  
 **Q: 自分のユーザーは、組織外の受信者に暗号化された電子メール メッセージを送信します。外部の受信者は、Office 365 のメッセージの暗号化と暗号化された電子メール メッセージを読み、返信するために行う必要があることはありますか。**
  
Office 365 で暗号化されたメッセージを受信する組織外部の受信者は、以下の 2 つの方法のいずれかでそのメッセージを表示できます。
  
- Microsoft アカウントまたは Office 365 に関連する仕事や学校のアカウントを使用して署名します。
    
- 1 回だけを使用してコードを渡します。
    
 **Q. Office 365 の暗号化されたメッセージはクラウドまたは Microsoft サーバーに保存されますか。**
  
残念ですが、受信者の電子メール システムでは、暗号化されたメッセージを保持し、Office 365 のサーバー上で表示するため一時的に転記される、受信者がメッセージを開いたとき。メッセージに格納されますできません。
  
 **Q. 暗号化された電子メール メッセージを独自のブランドでカスタマイズすることはできますか。**
  
はい。Windows PowerShell コマンドレットを使用して、暗号化された電子メール メッセージの上に表示する既定のテキスト、免責事項テキスト、および電子メール メッセージや暗号化ポータルに使用するロゴをカスタマイズできます。詳細については、「[Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md)」を参照してください。
  
 **Q. このサービスは組織内のすべてのユーザーに対して 1 つのライセンスが必要ですか。**
  
暗号化された電子メールを送信する組織内のすべてのユーザーに対して 1 つのライセンスが必要です。
  
 **Q. 外部の受信者はサブスクリプションが必要ですか。**
  
いいえ。外部の受信者は、暗号化されたメッセージを読んで返信するためにサブスクリプションを必要としません。 
  
 **(問) 方法は、権限管理サービス (RMS) から別の Office 365 メッセージ暗号化ですか。**
  
RMS では、次のように、組み込みのテンプレートを提供することで組織の内部メールの情報の権利の保護機能が用意されています: 転送の操作を行いますし、社外秘。Office 365 メッセージの暗号化をサポートしています電子メール メッセージの暗号化を内部受信者と外部受信者に送信されるメッセージです。
  
 **(問) 方法は、Office 365 メッセージの暗号化が有効とは異なるでしょうか。**
  
S/MIME は、基本的に、クライアント側の暗号化テクノロジであり、複雑な証明書管理と発行インフラストラクチャが必要です。Office 365 Message Encryption は、トランスポート ルールを使用するため、証明書の発行に依存しません。
  
 **Q. モバイル デバイスで暗号化されたメッセージを読むことはできますか。**
  
はい、 [Google のプレイを保存](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409)するし、 [Apple の App ストア](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409)からホームのビューアーのアプリケーションをダウンロードすることにより、Android と iOS のメッセージを表示できます。ホーム ビューアーのアプリケーションで HTML 添付ファイルを開くし、指示に従って、暗号化されたメッセージを開きます。他のモバイル デバイスには、ユーザーのメール クライアントは、ポストされたフォームをサポートしている限り、HTML 添付ファイルを開くことができます。
  
 **Q. 返信や転送されたメッセージは暗号化されますか。**
  
はい。返信はスレッド期間の間、暗号化されます。
  
 **Q. Office 365 Message Encryption にはローカライズ機能がありますか。**
  
受信電子メールと HTML コンテンツは、送信者の電子メール設定に基づいてローカライズされます。表示ポータルは、受信者のブラウザー設定に基づいてローカライズされます。ただし、暗号化されたメッセージの本文 (コンテンツ) はローカライズされません。
  
 **Q. Office 365 Message Encryption ではどのような暗号化方式が使用されますか。**
  
Office 365 Message Encryption では、Rights Management サービス (RMS) が暗号化インフラストラクチャとして使用されます。使用される暗号化方式は、メッセージの暗号化と復号化に使用する RMS キーを取得する場所によって異なります。
  
- Microsoft Azure の RMS を使用するにはキーを取得するのには、モード 2 の暗号化が使用されます。暗号化モード 2 は、更新および強化された AD RMS 暗号化実装です。署名と暗号化、RSA 2048 をサポートし、署名に sha-256 をサポートしています。
    
- Active Directory (AD) RMS を使用してキーを取得する場合は、暗号化モード 1 または暗号化モード 2 が使用されます。使用される方法は、社内 AD RMS 展開によって異なります。暗号化モード 1 は、元来の AD RMS 暗号実装です。この方式は署名と暗号化に RSA 1024 をサポートし、署名に関しては SHA-1 もサポートします。このモードは、引き続き RMS の現在のすべてのバージョンでサポートされています。
    
詳細については、 [AD RMS の暗号化モード](http://go.microsoft.com/fwlink/p/?LinkId=398616)を参照してください。
  
 **Q. 一部の暗号化メッセージには Office365@messaging.microsoft.com から送られていると表示されているのはなぜですか?**
  
暗号化された返信が暗号ポータルから、または OME ビューアー アプリを介して送信されるとき、送信元電子メール アドレスは Office365@messaging.microsoft.com に設定されます。暗号化メッセージは Microsoft エンドポイントを介して送信されるためです。これにより、暗号化されたメッセージがスパムとしてマークされるのを回避できます。このラベルがあるため、暗号化ポータル内の電子メールとアドレスの表示名が変更されることはありません。また、このラベルが適用されるのは、ポータルを介して送信されるメッセージだけで、他の電子メール クライアントを介して送信されるメッセージには適用されません。
  
 **Q: 私は、Exchange ホストされている暗号化 (的を射た) サブスクライバーです。知るにはの詳細については、Office 365 のメッセージの暗号化にアップグレードしますか。**
  
すべての的を射たユーザーを Office 365 のメッセージの暗号化にアップグレードするとします。詳細については、 [Exchange ホスト暗号化アップグレード センター](http://go.microsoft.com/fwlink/p/?LinkID=511077)を参照してください。
  
 **Office 365 のメッセージの暗号化をサポートする任意の Url、IP アドレスを開く] または [自分の所属組織のファイアウォール内でポートを必要 (問) でしょうか。**
  
はい。Office 365 Message Encryption によって暗号化されたメッセージの認証を有効にするには、ご自分の組織の許可リストに Exchange Online の URL を追加する必要があります。Exchange Online の URL リストについては、「[Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx)」を参照してください。
  
 **Q. Office 365 の暗号化されたメッセージは、何人まで送信できますか。**
  
暗号化されたメッセージの受信者数の制限は、メッセージの [**宛先**] フィールド内の文字の数に基づいています。(配布リストの展開) の後に組み合わせると、受信者のアドレス フィールド**に**文字を超えてはいけません 11,980。電子メール アドレスは、文字の長さで異なりますので 1 つの暗号化されたメッセージの標準的な受信者の制限はありません。 
  
 **Q. 特定の受信者に送信されたメッセージを取り消すことは可能ですか。**
  
違います。送信された後は、特定の人物にメッセージを取り消すことができません。
  
 **Q. 受信されて既読になった暗号化メッセージのレポートを表示することはできますか。**
  
暗号化されたメッセージを表示すると、たとえば、特定のトランスポート ルールに一致するメッセージの数を決定するを活用することができます、利用可能な Office 365 のレポートを表示するレポートが用意されていません。
  
 **Q. OME ポータルと OME Viewer アプリで提供した情報を Microsoft はどのように使用しますか。**
  
[Office 365 の暗号化メッセージングのポータルのプライバシーに関する声明](protected-message-viewer-portal-privacy-statement.md)について、どのような Microsoft はないし、個人情報の詳細な情報を提供します。 
  

