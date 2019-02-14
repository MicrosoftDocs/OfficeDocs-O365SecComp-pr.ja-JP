---
title: Office 365 での電子メールの暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
description: Office 365 の Office のメッセージの暗号化 (ホーム)、S/MIME、情報権利管理 (IRM) などの暗号化のオプションを比較し、トランスポート層セキュリティ (TLS) の詳細を説明します。
ms.openlocfilehash: a6db6c9cf6af180fe84e955613fb6b1175ee0747
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995358"
---
# <a name="email-encryption-in-office-365"></a>Office 365 での電子メールの暗号化

この資料では、Office 365 の Office のメッセージの暗号化 (ホーム)、S/MIME、情報権利管理 (IRM) などの暗号化のオプションを比較し、トランスポート層セキュリティ (TLS) を紹介します。
  
Office 365 は、電子メール セキュリティのビジネス ニーズを満たすために複数の暗号化オプションを提供します。この資料では、Office 365 で電子メールを暗号化するために 3 つの方法について説明します。Office 365 内のすべてのセキュリティ機能の詳細についてはする場合は、 [Office 365 の信頼のセンター](http://go.microsoft.com/fwlink/p/?LinkID=282470)を参照してください。この資料には、Office 365 管理者は、Office 365 のセキュリティで保護された電子メールのために使用できる暗号化の 3 つのタイプが導入されています。
  
- Office Message Encryption (OME)。
    
- Secure/Multipurpose Internet Mail Extensions (S/MIME)。
    
- Information Rights Management (IRM)。
    
## <a name="what-is-email-encryption-and-how-does-office-365-use-it"></a>電子メールの暗号化とはどのようなもので、Office 365 ではどのように使用しますか?

暗号化は、承認された受信者のみがデコードし、その情報を利用するために情報をエンコードするプロセスです。Office 365 は、2 つの方法で暗号化を使用して: サービス、およびカスタム コントロールとして。サービスでは、Office 365 で暗号化を使用、デフォルトでは何も構成する必要はありません。たとえば、Office 365 は、接続、または 2 つのサーバー間のセッションを暗号化するためにトランスポート層セキュリティ (TLS) を使用します。 
  
通常電子メールの暗号化の動作方法を以下に示します。
  
- メッセージの暗号化、またはメッセージが転送中には、送信者のコンピューターで、または中央サーバーのいずれか、読み取り不可能な暗号文をテキスト形式から変換します。
    
- メッセージは、転送中に、メッセージが傍受された場合に読み込まれているを防ぐためには、暗号文に残ります。
    
- 受信者がメッセージを受信すると、メッセージは次の 2 つの方法で読み取り可能なプレーンテキストに変換し直されます。
    
  - 受信者のコンピューターに、メッセージを復号化キーを使用するか、
    
  - 中央のサーバーでは、受信者の身元を確認した後、受信者がメッセージを復号化します。
    
Office 365 がサーバー間の通信をセキュリティで保護する方法の詳細についてなど、Office 365 内で、または Office 365 および Office 365 では、外部で信頼できるビジネス パートナーとの間の組織間で[をどのように Exchange Online を参照を使用して TLS セキュリティで保護された電子メールOffice 365 での接続の](exchange-online-uses-tls-to-secure-email-connections.md)です。
  
このビデオでは、 [Office 365 での暗号化](https://www.youtube.com/watch?v=KmfxCd5ublI)の概要について。
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Office 365 で使用可能な電子メール暗号化オプションの比較

||        ![OME を説明する概念アートワーク](media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)                 |        ![IRM を説明する概念アートワーク](media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)                 |        ![SMIME を説明する概念アートワーク](media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)                |
|:-----|:-----|:-----|:-----|
|暗号化オプションの説明  <br/> |Office 365 Message Encryption (OME) は、Azure Rights Management (Azure RMS) で構築され、宛先のメール アドレス (Gmail、Yahoo! Mail、Outlook.com など) に関係なく、暗号化された電子メールを組織内外の宛先に送信できるようにするサービスです。  <br/> 管理者は、暗号化の条件を定義するトランスポート ルールを設定できます。ユーザーがルールに一致するメッセージを送信する場合、自動的に暗号化が適用されます。  <br/> 暗号化されたメッセージを表示するのには受信者ワンタイム パスワード、Microsoft アカウントでサインインまたは著作物を使用して記号を取得するか、Office 365 に関連付けられているアカウントを学校します。受信者は、暗号化された返信を送信することもできます。Office 365 のサブスクリプションには、暗号化されたメッセージを表示するか、暗号化された応答を送信する必要はありません。  <br/> |IRM は、電子メール メッセージに使用制限の適用も行える暗号化ソリューションです。機密情報が権限のないユーザーによって印刷、転送、またはコピーされるのを防止します。  <br/> Office 365 の IRM 機能には Azure Rights Management (Azure RMS) が使用されます。 
  <br/> |S/MIME は、証明書ベースの暗号化ソリューションを使用すると、両方の暗号化し、メッセージにデジタル署名をします。メッセージの暗号化により、目的の受信者だけが開くし、メッセージを読むことができます。デジタル署名は、受信者が送信者の id を確認することができます。  <br/> デジタル署名とメッセージの暗号化は、デジタル署名を検証し、メッセージを暗号化または解読するためのキーを含む一意のデジタル証明書を使用することによって可能になります。  <br/> 秒/MIME を使用するには、公開キーを受信者ごとにファイルが必要です。受信者は、セキュリティで保護されたままにする必要がありますが自分の秘密キーを維持するためにあります。受信者の秘密キーが侵害された場合、受信者は、新しい秘密キーを取得し、すべての潜在的な送信者の公開キーを再配布する必要があります。  <br/> |
|暗号化オプションの機能  <br/> | OME:  <br/>  内部または外部の受信者に送信されたメッセージを暗号化します。  <br/>  ユーザーは Outlook.com、Yahoo! Mail、および Gmail を含むすべての電子メール アドレスに暗号化されたメッセージを送信できます。  <br/>  管理者として、組織のブランドを反映するようにポータルを表示する電子メールをカスタマイズできます。  <br/>  マイクロソフトは安全に管理し、必要はありませんので、キーを格納します。  <br/>  暗号化されたメッセージ (HTML 添付ファイルとして送信済み) をブラウザーで開くことができる場合は、クライアント側の特別なソフトウェアは必要ありません。  <br/> | IRM:  <br/>  電子メール メッセージおよび添付ファイルに対するオンラインおよびオフラインの保護を提供するために、暗号化および利用制限を使用します。  <br/>  管理者には、自動的に IRM を適用してメッセージを選択するためのトランスポート ルールまたは Outlook 保護ルールを設定する権限が付与されます。  <br/>  ユーザーは Outlook または Outlook Web App で手動でテンプレートを適用できます。  <br/> |S/MIME は、デジタル署名による送信者の認証および暗号化によるメッセージの機密性を処理します。  <br/> |
|暗号化オプションの限界  <br/> |ホームでは利用上の制限をメッセージに適用できます。たとえば、受信者が転送または暗号化されたメッセージを印刷を停止するのには使用できません。  <br/> |一部のアプリケーションが、すべてのデバイスで IRM 電子メールをサポートしていません。IRM 電子メールをサポートするその他の製品の詳細については、[クライアント デバイスの能力](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities)を参照してください。<br/> |秒/MIME では、マルウェア、スパム、またはポリシーのスキャン対象の暗号化されたメッセージを許可されていません。  <br/> |
|推奨事項とシナリオ例  <br/> | 消費者またはその他の企業があるかどうかは、組織外のユーザーにビジネス上の機密情報を送信するときにホームを使用することをお勧めします。例えば：  <br/>  顧客にクレジット カード請求書を送信する銀行員  <br/>  医師、患者の医療記録を送信します。  <br/>  他の弁護士に法的な機密情報を送信する弁護士  <br/> | 使用制限と暗号化の両方を適用する場合は、IRM を使用することをお勧めします。例:  <br/>  新製品についての彼女のチームに機密情報の詳細を送信するマネージャーには、「転送不可」のオプションが適用されます。  <br/>  エグゼクティブが、Office 365 を使用しているパートナーからの添付ファイルを含む重要な提案書を別の会社と共有しなければならず、電子メールと添付ファイルの両方を保護する必要がある場合。  <br/> | 組織または受信者の組織のいずれかが真のピア ツー ピアの暗号化を必要とする場合は、S/MIME を使用することをお勧めします。  <br/>  S/MIME は、次のシナリオで最もよく使用されます。  <br/>  他の政府機関と通信する政府機関  <br/>  政府機関と通信する会社  <br/> |
   
## <a name="what-encryption-options-are-available-for-my-office-365-subscription"></a>使用中の Office 365 サブスクリプションでは、どの暗号化オプションを利用できますか?

Office 365 サブスクリプションの電子メールの暗号化のオプションの詳細については、 [Exchange のオンライン サービスの説明](https://technet.microsoft.com/en-us/library/exchange-online-service-description.aspx)を参照してください。ここでは、次の暗号化機能についての情報をご覧ください。
  
- IRM 機能と OME の両方を含む Azure RMS
    
- S/MIME
    
- TLS
    
- 保存中のデータの暗号化 (BitLocker を使用)
    
## <a name="what-about-encryption-for-data-at-rest"></a>保存中のデータの暗号化について

「データ」は、データ転送中にアクティブにされていないことを指します。、Office 365 で、BitLocker ドライブ暗号化を使用してメール データが暗号化されます。BitLocker では、承認されていないアクセスに対する保護を強化するには Office 365 のデータ センターでのハード ドライブを暗号化します。詳細については、 [BitLocker の概要](https://go.microsoft.com/fwlink/p/?LinkId=394737)を参照してください。
  
## <a name="more-information-about-email-encryption-options-in-office-365"></a>Office 365 の電子メール暗号化オプションの詳細

この記事および TLS の電子メール暗号化オプションの詳細については、次の記事を参照してください。
  
 **OME**
  
[Office 365 Message Encryption (OME)](ome.md)
  
 **IRM**
  
[Exchange Online での Information Rights Management](https://technet.microsoft.com/en-us/library/jj983436%28v=exchg.150%29.aspx)
  
[Azure アクセス権の管理とは何ですか。](https://technet.microsoft.com/library/jj585026)
  
 **S/MIME**
  
[S/MIME によるメッセージの署名と暗号化](https://technet.microsoft.com/library/dn626158)
  
[理解 S-MIME](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[公開キー暗号をについてください。](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
 **TLS**
  
[Office 365 のコネクタを使用してユーザー設定のメール フローを構成します。](https://technet.microsoft.com/en-us/library/jj723138%28v=exchg.150%29.aspx)
  

