---
title: Office 365 での電子メールの暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
description: Office メッセージ365の暗号化 (OME)、S/MIME、Information Rights Management (IRM)、トランスポート層セキュリティ (TLS) について説明します。
ms.openlocfilehash: 4a39bee76346bb46a53ab752d2fac31316c0258f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154789"
---
# <a name="email-encryption-in-office-365"></a>Office 365 の電子メールの暗号化

この記事では、office メッセージ365の暗号化 (OME)、S/MIME、Information Rights Management (IRM)、トランスポート層セキュリティ (TLS) について説明します。
  
Office 365 には、電子メール セキュリティのビジネス ニーズを満たすために役立つ複数の暗号化オプションが用意されています。 この記事では、Office 365 で電子メールを暗号化する3つの方法を示します。 Office 365 のすべてのセキュリティ機能の詳細については、「 [office 365 セキュリティセンター](http://go.microsoft.com/fwlink/p/?LinkID=282470)」を参照してください。 この記事では、office 365 で電子メールをセキュリティで保護するために Office 365 管理者が使用できる3種類の暗号化について説明します。
  
- Office Message Encryption (OME)。
    
- Secure/Multipurpose Internet Mail Extensions (S/MIME)。
    
- Information Rights Management (IRM)。
    
## <a name="what-is-email-encryption-and-how-does-office-365-use-it"></a>電子メールの暗号化とはどのようなもので、Office 365 ではどのように使用しますか?

暗号化とは、認証された受信者のみが情報をデコードして利用できるように情報をエンコードするプロセスのことです。 Office 365 では、2つの方法で暗号化を使用しています。サービスでは、カスタマーコントロールとして使用されます。 サービスでは、既定では、Office 365 で暗号化が使用されます。何も構成する必要はありません。 たとえば、Office 365 はトランスポート層セキュリティ (TLS) を使用して、2台のサーバー間の接続 (セッション) を暗号化します。 
  
通常、電子メールの暗号化のしくみは次のとおりです。
  
- メッセージが暗号化されているか、メッセージの送信中に、送信者のコンピューターまたは中央のサーバーのいずれかで、プレーンテキストから読み取り不能な暗号テキストに変換された。
    
- メッセージが傍受された場合にそのメッセージが読み取られないようにするために、送信中のメッセージは暗号化テキストのままです。
    
- 受信者がメッセージを受信すると、メッセージは次の 2 つの方法で読み取り可能なプレーンテキストに変換し直されます。
    
  - 受信者のコンピューターは、キーを使用してメッセージを復号化します。
    
  - 中央サーバーは、受信者の id を検証した後、受信者に代わってメッセージを復号化します。
    
Office 365 365 内365の組織間、office 365 と、office の外部の信頼されたビジネスパートナーの間など、office がサーバー間の通信をセキュリティで保護する方法の詳細については、「Exchange Online で TLS を使用して電子メールを保護する方法」を参照してください。Office 365 の接続。
  
[Office 365 での暗号化](https://www.youtube.com/watch?v=KmfxCd5ublI)の概要については、このビデオをご覧ください。
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Office 365 で使用可能な電子メール暗号化オプションの比較

||![OME を説明する概念アートワーク](media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![IRM を説明する概念アートワーク](media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![SMIME を説明する概念アートワーク](media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|暗号化オプションの説明|Office 365 Message Encryption (OME) は、Azure Rights Management (Azure RMS) で構築され、宛先のメール アドレス (Gmail、Yahoo! Mail、Outlook.com など) に関係なく、暗号化された電子メールを組織内外の宛先に送信できるようにするサービスです。  <br/> 管理者は、暗号化の条件を定義するトランスポート ルールを設定できます。ユーザーがルールに一致するメッセージを送信する場合、自動的に暗号化が適用されます。  <br/> 受信者は、ワンタイム パスコードを取得するか、Microsoft アカウントまたは Office 365 と関連付けられている職場または学校のアカウントを使用してサインインして、暗号化されたメッセージを表示できます。 受信者は、暗号化された返信を送信することもできます。 暗号化されたメッセージを表示したり、暗号化された返信を送信したりするために Office 365 サブスクリプションは必要ありません。|IRM は、電子メール メッセージに使用制限の適用も行える暗号化ソリューションです。機密情報が権限のないユーザーによって印刷、転送、またはコピーされるのを防止します。  <br/> Office 365 の IRM 機能には Azure Rights Management (Azure RMS) が使用されます。|S/MIME は、メッセージを暗号化およびデジタル署名するための証明書ベースの暗号化ソリューションです。 メッセージの暗号化により、指定された受信者だけがメッセージを開き読むことができます。 デジタル署名により、受信者は送信者の身元を確認できます。  <br/> デジタル署名とメッセージの暗号化は、デジタル署名を検証し、メッセージを暗号化または解読するためのキーを含む一意のデジタル証明書を使用することによって可能になります。  <br/> S/MIME を使用するには、各受信者のファイルに公開キーが必要です。 受信者は独自の秘密キーを維持し、保護する必要があります。 受信者の秘密キーが侵害された場合、受信者は新しい秘密キーを取得し、公開キーをすべての潜在的な送信者に再配布する必要があります。|
|暗号化オプションの機能|OME  <br/>  内部または外部の受信者に送信されたメッセージを暗号化します。  <br/>  ユーザーは Outlook.com、Yahoo! Mail、および Gmail を含むすべての電子メール アドレスに暗号化されたメッセージを送信できます。  <br/>  管理者は、組織のブランドを反映するように電子メール表示ポータルをカスタマイズできます。  <br/>  Microsoft は、キーを安全に管理し、保存する必要はありません。  <br/>  暗号化されたメッセージ (HTML 添付ファイルとして送信済み) をブラウザーで開くことができる場合は、クライアント側の特別なソフトウェアは必要ありません。|IRM  <br/>  電子メール メッセージおよび添付ファイルに対するオンラインおよびオフラインの保護を提供するために、暗号化および利用制限を使用します。  <br/>  管理者には、自動的に IRM を適用してメッセージを選択するためのトランスポート ルールまたは Outlook 保護ルールを設定する権限が付与されます。  <br/>  ユーザーが Outlook または web 上の Outlook (旧称 Outlook Web App) でテンプレートを手動で適用できるようにします。|S/MIME は、デジタル署名による送信者の認証および暗号化によるメッセージの機密性を処理します。|
|暗号化オプションの限界|OME では、メッセージに使用制限を適用することはできません。 たとえば、受信者が暗号化されたメッセージを転送または印刷するのを停止するために使用することはできません。|一部のアプリケーションでは、すべてのデバイスで IRM 電子メールをサポートするわけではないかもしれません。 IRM 電子メールをサポートするその他の製品の詳細については、「[クライアントデバイスの機能](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities)」を参照してください。|S/MIME では、マルウェア、スパム、またはポリシーの暗号化されたメッセージのスキャンを許可しません。|
|推奨事項とシナリオ例|組織外のユーザーに機密業務情報を送信する場合は、OME を使用することをお勧めします。 例:  <br/>  顧客にクレジット カード請求書を送信する銀行員  <br/>  患者に医療記録を送信する医師の事務所  <br/>  他の弁護士に法的な機密情報を送信する弁護士|使用制限と暗号化の両方を適用する場合は、IRM を使用することをお勧めします。例:  <br/>  新しい製品に関する機密情報をチームに送信するマネージャーには、"転送不可" オプションが適用されます。  <br/>  エグゼクティブが、Office 365 を使用しているパートナーからの添付ファイルを含む重要な提案書を別の会社と共有しなければならず、電子メールと添付ファイルの両方を保護する必要がある場合。|組織または受信者の組織が true ピアツーピア暗号化を必要とする場合は、S/MIME を使用することをお勧めします。  <br/>  S/MIME は、次のシナリオで最もよく使用されます。  <br/>  他の政府機関と通信する政府機関  <br/>  政府機関と通信する会社|
   
## <a name="what-encryption-options-are-available-for-my-office-365-subscription"></a>使用中の Office 365 サブスクリプションでは、どの暗号化オプションを利用できますか?

Office 365 サブスクリプションの電子メール暗号化オプションの詳細については、「 [Exchange Online サービスの説明](https://technet.microsoft.com/en-us/library/exchange-online-service-description.aspx)」を参照してください。 ここでは、次の暗号化の機能に関する情報を確認できます。
  
- IRM 機能と OME の両方を含む Azure RMS
    
- S/MIME
    
- TLS
    
- 保存中のデータの暗号化 (BitLocker を使用)
    
## <a name="what-about-encryption-for-data-at-rest"></a>保存中のデータの暗号化について

"Rest のデータ" とは、伝送中のデータを意味します。 Office 365 では、保存電子メール データは BitLocker ドライブ暗号化を使用して暗号化されます。 BitLocker は、Office 365 データセンター内のハード ドライブを暗号化し、権限のないアクセスに対する保護を強化します。 詳細については、「 [BitLocker の概要](https://go.microsoft.com/fwlink/p/?LinkId=394737)」を参照してください。
  
## <a name="more-information-about-email-encryption-options-in-office-365"></a>Office 365 の電子メール暗号化オプションの詳細

この記事および TLS の電子メール暗号化オプションの詳細については、次の記事を参照してください。
  
 **OME**
  
[Office 365 Message Encryption (OME)](ome.md)
  
 **IRM**
  
[Exchange Online での Information Rights Management](https://technet.microsoft.com/en-us/library/jj983436%28v=exchg.150%29.aspx)
  
[Azure Rights Management とは](https://technet.microsoft.com/library/jj585026)
  
 **S/MIME**
  
[S/MIME によるメッセージの署名と暗号化](https://technet.microsoft.com/library/dn626158)
  
[S/MIME について](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[公開キー暗号化について](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
 **TLS**
  
[Office 365 でコネクタを使用してカスタムメールフローを構成する](https://technet.microsoft.com/en-us/library/jj723138%28v=exchg.150%29.aspx)
  

