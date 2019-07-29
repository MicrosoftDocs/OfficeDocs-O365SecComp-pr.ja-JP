---
title: Office 365 の電子メールの暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
description: Office Message Encryption (OME)、S/MIME、Information Rights Management (IRM) など、Office 365 での暗号化のオプションを比較し、トランスポート層セキュリティ (TLS) について紹介します。
ms.openlocfilehash: dba0c0d890a7018f9ca5daab2c1e88c4d234c5c3
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854681"
---
# <a name="email-encryption-in-office-365"></a>Office 365 の電子メールの暗号化

この記事では、Office Message Encryption (OME)、S/MIME、Information Rights Management (IRM) など、Office 365 での暗号化のオプションを比較し、トランスポート層セキュリティ (TLS) について紹介します。
  
Office 365 では、電子メールのセキュリティのビジネス ニーズを満たすために複数の暗号化オプションが提供されています。 この記事では、Office 365 でメールを暗号化する 3 つの方法を紹介します。 Office 365 のすべてのセキュリティ機能については、[Office 365 トラスト センター](http://go.microsoft.com/fwlink/p/?LinkID=282470)にアクセスしてください。 この記事では、Office 365 管理者が Office 365 で電子メールを保護する上で役立つ次の 3 つの種類の暗号化を紹介します。
  
- Office Message Encryption (OME)。
    
- Secure/Multipurpose Internet Mail Extensions (S/MIME)。
    
- Information Rights Management (IRM)。
    
## <a name="what-is-email-encryption-and-how-does-office-365-use-it"></a>電子メールの暗号化とはどのようなもので、Office 365 ではどのように使用しますか?

暗号化とは、認証された受信者だけが特定の情報をデコードおよび利用できるようにその情報をエンコードするプロセスのことです。 Office 365 では、サービスでの使用とカスタマー コントロールとしての使用の 2 つの方法で暗号化を使用します。 サービスでは、暗号化は Office 365 で既定で使用されるため、ユーザーによる設定は特に必要ありません。 たとえば、Office 365 はトランスポート層セキュリティ (TLS) を使用して、2 つのサーバー間の接続またはセッションを暗号化します。 
  
一般的な電子メールの暗号化のしくみは次のとおりです。
  
- メッセージの送信中に送信者のコンピューターまたは中央サーバーによって、メッセージがプレーンテキストから読み取り不可能な暗号テキストに暗号化または変換されます。
    
- メッセージが途中で読み取られることを防ぐため、送信中のメッセージは暗号テキストのままです。
    
- 受信者がメッセージを受信すると、メッセージは次の 2 つの方法で読み取り可能なプレーンテキストに変換し直されます。
    
  - 受信者のコンピューターでキーを使用してメッセージを解読するか、
    
  - 受信者の身元を確認した後に、受信者の代わりに中央サーバーでメッセージを解読します。
    
Office 365 内の組織間、または Office 365 と Office 365 外部の信頼できるビジネス パートナー間など、Office 365 でサーバー間の通信をセキュリティで保護する方法については、「[Exchange Online が TLS を使って Office 365 のメール接続をセキュリティで保護する方法](exchange-online-uses-tls-to-secure-email-connections.md)」を参照してください。
  
[Office 365 の暗号化](https://www.youtube.com/watch?v=KmfxCd5ublI)の概要はこの動画でご覧いただけます。
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Office 365 で使用可能な電子メール暗号化オプションの比較

||![OME を説明する概念アートワーク](media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![IRM を説明する概念アートワーク](media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![SMIME を説明する概念アートワーク](media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|暗号化オプションの説明|Office 365 Message Encryption (OME) は、Azure Rights Management (Azure RMS) で構築され、宛先のメール アドレス (Gmail、Yahoo! Mail、Outlook.com など) に関係なく、暗号化された電子メールを組織内外の宛先に送信できるようにするサービスです。  <br/> 管理者は、暗号化の条件を定義するトランスポート ルールを設定できます。ユーザーがルールに一致するメッセージを送信する場合、自動的に暗号化が適用されます。  <br/> 暗号化メッセージを表示するために、受信者は 1 回限りのパスコードを取得するか、Microsoft アカウントでサインインするか、Office 365 に関連付けられている職場または学校のアカウントでサインインできます。 受信者は暗号化された返事を送信することもできます。 暗号化されたメッセージを表示したり、暗号化された返信を送信するのに、受信者は Office 365 サブスクリプションを必要としません。|IRM は、電子メール メッセージに使用制限の適用も行える暗号化ソリューションです。機密情報が権限のないユーザーによって印刷、転送、またはコピーされるのを防止します。  <br/> Office 365 の IRM 機能には Azure Rights Management (Azure RMS) が使用されます。|S/MIME は証明書基盤の暗号化ソリューションであり、メッセージを暗号化し、デジタル署名できます。 メッセージを暗号化することで、本来の受信者だけがメッセージを開き、閲覧できます。 デジタル署名は、受信者が送信者の身元を確認するのに役立ちます。  <br/> デジタル署名と暗号化メッセージのいずれも、独自のデジタル証明書の利用により可能となります。この証明書には、デジタル署名を検証し、メッセージを暗号化し、復号化するための鍵が含まれています。  <br/> S/MIME を使用するには、受信者ごとにファイルに公開鍵を付ける必要があります。 受信者は独自の秘密キーを維持し、保護する必要があります。 受信者の秘密キーが危険にさらされた場合、受信者は新しい秘密キーを取得し、すべての潜在的な送信者に公開キーを再配布する必要があります。|
|この機能について|OME:  <br/>  内部または外部の受信者に送信されたメッセージを暗号化します。  <br/>  ユーザーは Outlook.com、Yahoo! Mail、および Gmail を含むすべての電子メール アドレスに暗号化されたメッセージを送信できます。  <br/>  管理者であれば、組織のブランドを反映するように電子メール表示ポータルをカスタマイズできます。  <br/>  Microsoft がキーを安全に管理および格納するため、ユーザーがそうする必要はありません。  <br/>  暗号化されたメッセージ (HTML 添付ファイルとして送信済み) をブラウザーで開くことができる場合は、クライアント側の特別なソフトウェアは必要ありません。|IRM:  <br/>  暗号化と使用制限を利用し、電子メールのメッセージと添付ファイルをオンラインとオフラインで保護します。  <br/>  管理者には、自動的に IRM を適用してメッセージを選択するためのトランスポート ルールまたは Outlook 保護ルールを設定する権限が付与されます。  <br/>  ユーザーは Outlook または Outlook on the web (旧称: Outlook Web App) で手動でテンプレートを適用できます。|S/MIME は、デジタル署名による送信者の認証および暗号化によるメッセージの機密性を処理します。|
|暗号化オプションの限界|OME では、メッセージに利用制限を適用できません。 たとえば、受信者が暗号化メッセージを転送したり印刷したりするのを制限することはできません。|一部のアプリケーションでは、すべてのデバイスで IRM 電子メールをサポートするわけではないかもしれません。 以上の製品と IRM メールに対応しているその他の製品に関する詳細については、「[クライアント デバイスの機能](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities)」を参照してください。|S/MIME では、マルウェア、スパム、およびポリシーについて、暗号化されたメッセージをスキャンできません。|
|推奨事項とシナリオ例|顧客であろうと他の会社であろうと、組織外のユーザーに機密のビジネス情報を送信する場合は、OME を使用することをお勧めします。 例:  <br/>  顧客にクレジット カード請求書を送信する銀行員  <br/>  患者に医療記録を送信する診療所  <br/>  他の弁護士に法的な機密情報を送信する弁護士|使用制限と暗号化の両方を適用する場合は、IRM を使用することをお勧めします。例:  <br/>  新しい製品に関する機密情報の詳細をチームに送信するマネージャーが [転送不可] オプションを適用する場合。  <br/>  エグゼクティブが、Office 365 を使用しているパートナーからの添付ファイルを含む重要な提案書を別の会社と共有しなければならず、電子メールと添付ファイルの両方を保護する必要がある場合。|ユーザーの組織または受信者の組織のいずれかが、適切なピアツーピア暗号化を必要とする場合は、S/MIME を使用することをお勧めします。  <br/>  S/MIME は、次のシナリオで最もよく使用されます。  <br/>  他の政府機関と通信する政府機関  <br/>  政府機関と通信する会社|
   
## <a name="what-encryption-options-are-available-for-my-office-365-subscription"></a>使用中の Office 365 サブスクリプションでは、どの暗号化オプションを利用できますか?

Office 365 サブスクリプションの電子メール暗号化オプションについては、「[Exchange Online サービスの説明](https://technet.microsoft.com/en-us/library/exchange-online-service-description.aspx)」を参照してください。 ここでは、次の暗号化の機能に関する情報を確認できます。
  
- Azure RMS、IRM 機能と OME の両方を含む
    
- S/MIME
    
- TLS
    
- 保存中のデータの暗号化 (BitLocker を使用)
    
## <a name="what-about-encryption-for-data-at-rest"></a>保存中のデータの暗号化について

"保存データ" とは、アクティブに送信されている過程にはないデータです。 Office 365 では、保存中の電子メール データは BitLocker ドライブ暗号化を使用して暗号化されます。 BitLocker は、Office 365 データセンター内のハード ドライブを暗号化し、権限のないアクセスに対する保護を強化します。 詳細については、「[BitLocker の概要](https://go.microsoft.com/fwlink/p/?LinkId=394737)」を参照してください。
  
## <a name="more-information-about-email-encryption-options-in-office-365"></a>Office 365 の電子メール暗号化オプションの詳細

この記事の電子メール暗号化オプションと TLS の詳細については、次の記事を参照してください。
  
 **OME**
  
[Office 365 Message Encryption (OME)](ome.md)
  
 **IRM**
  
[Exchange Online での Information Rights Management](https://technet.microsoft.com/en-us/library/jj983436%28v=exchg.150%29.aspx)
  
[Azure Active Directory Rights Management の概要](https://technet.microsoft.com/library/jj585026)
  
 **S/MIME**
  
[S/MIME によるメッセージの署名と暗号化](https://technet.microsoft.com/library/dn626158)
  
[S/MIME について](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[公開キー暗号について](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
 **TLS**
  
[Office 365 でコネクタを使用してメール フローを構成する](https://technet.microsoft.com/en-us/library/jj723138%28v=exchg.150%29.aspx)
  

