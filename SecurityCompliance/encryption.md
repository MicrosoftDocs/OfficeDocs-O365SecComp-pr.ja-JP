---
title: Office 365 での暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/3/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
description: Office 365 では、残りの部分と、最も強力な暗号化、プロトコル、および利用可能なテクノロジを使用して、移動中のコンテンツが暗号化されます。Office 365 の暗号化の概要を取得します。
ms.openlocfilehash: a9f37fddf28461ee4912e0b8a1f5b922c59c009f
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972289"
---
# <a name="encryption-in-office-365"></a>Office 365 での暗号化

暗号化は、ファイルの保護と情報保護の戦略の重要な部分です。Office 365 のすべてのバージョンで使用される暗号化の概要を取得するには、この資料を参照し、Office ドキュメントのパスワード保護に、組織の暗号化の設定から暗号化の操作のヘルプを取得します。
  
- 証明書と TLS のようなテクノロジについての情報を探している場合は、 [Office 365 での暗号化に関するテクニカル リファレンスの詳細](technical-reference-details-about-encryption.md)を参照してください。
    
- 組織の暗号化を設定する方法についての情報を探している場合は、 [Office 365 のエンタープライズでの暗号化の設定](set-up-encryption.md)を参照してください。
    
## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>暗号化とは何ですし、どのように動作する Office 365 のでしょうか。

高レベルは、暗号化、暗号テキストに暗号化、暗号文を復号化しない限り、ユーザーまたはコンピューターで使用できない ("プレーン テキスト"と呼ばれます)、データのエンコーディングのプロセスです。復号化には、承認されたユーザーだけが暗号化キーが必要です。暗号化は、認証された受信者のみが電子メール メッセージやファイルなど、コンテンツを復号化できることを確認することができます。
  
暗号化自体でも、ファイル、電子メール メッセージ、予定表のアイテムなどのコンテンツが悪人の手に渡ることできます。暗号化とは、組織の大規模な情報保護戦略の一部です。暗号化を使用すると、暗号化されたデータを使用できる必要があります人だけができることを確認することができます。
  
場所で同時に暗号化の複数のレイヤーを持つことができます。たとえば、電子メール メッセージおよび電子メールのフローを使用する通信チャネルを暗号化できます。残りの部分といくつかの強力な暗号化プロトコルとトランスポート層セキュリティまたは Secure Sockets Layer (SSL または TLS)、インターネット プロトコル セキュリティ (IPSec)、高度な暗号化などのテクノロジを使用して、転送中に、Office 365 のデータが暗号化します。標準 (AES) です。
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>データおよび転送中のデータの暗号化

 **不使用時のデータの例**には、SharePoint ライブラリ、プロジェクトのオンライン ・ データ、ビジネス会議、電子メール メッセージおよび添付ファイル、Office 365 内のフォルダーに格納されているため、Skype でアップロードされたドキュメントにアップロードされているファイルが含まれてメールボックス、およびビジネスのための OneDrive にアップロードされたファイルです。 
  
 **転送中のデータ**には、メール メッセージが配信される、またはオンライン会議で行われる会話などがあります。Office 365 では、ユーザーのデバイスは、Office 365 をサーバーと通信しているときに、または、Office 365 のサーバーは、別のサーバーと通信しているデータは転送中には。 
  
、Office 365 では、複数のレイヤーと連携してデータを保護する暗号化の種類を持つことができます。次の表には、追加情報へのリンクをいくつかの例が含まれています。
  
|**コンテンツの種類**|**暗号化テクノロジー**|**リソースの詳細**|
|:-----|:-----|:-----|
|デバイス上のファイルです。これには、フォルダー、コンピューター、タブレット、または電話に保存されている Office ドキュメント、またはマイクロソフトのクラウドに保存されたデータに保存されている電子メール メッセージが含まれます。  <br/> |マイクロソフトのデータ センターで BitLocker。BitLocker は、Windows のコンピューターやタブレットなどのクライアント マシンにも使用できます。  <br/> マイクロソフトのデータ センターに分散キー マネージャー (DKM)  <br/> Office 365 の顧客のキー  <br/> |[Windows IT センター: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [マイクロソフト セキュリティ センター: 暗号化](https://www.microsoft.com/en-us/TrustCenter/Security/Encryption) <br/> [コントロールのクラウド セキュリティ: 残りの部分でのデータの暗号化](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online が電子メールの機密情報をセキュリティで保護する方法](exchange-online-secures-email-secrets.md) <br/> [顧客キーを使用して Office 365 でデータを制御する](controlling-your-data-using-customer-key.md) <br/> |
|ユーザー間で転送中のファイルです。これは、Office ドキュメント、またはユーザー間で共有する SharePoint リスト アイテムを含めることができます。  <br/> |TLS 転送中のファイルの  <br/> |[OneDrive for Business および SharePoint Online におけるデータ暗号化](data-encryption-in-odb-and-spo.md) <br/> [オンライン ビジネスの Skype: セキュリティとアーカイブ](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|受信者間で転送中の電子メールを送信します。これには、Exchange のオンラインでホストされている電子メールが含まれます。  <br/> |Azure アクセス権の管理、S/MIME では、電子メールの送信中に TLS と office 365 のメッセージの暗号化  <br/> |[Office 365 Message Encryption (OME)](ome.md) <br/> [Office 365 での電子メールの暗号化](email-encryption.md) <br/> [Exchange Online で電子メール接続をセキュリティで保護するために Office 365 で TLS を使用する方法](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
   
## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>場合に必要な制御の強化セキュリティとコンプライアンスの要件を満たすために暗号化でしょうか。

ボリュームの暗号化、ファイル暗号化、および Office 365 のメールボックスの暗号化に Microsoft 管理ソリューションに加えより厳格なセキュリティおよびコンプライアンスの要件を満たすために顧客管理オプションを使用できます。このようなソリューションは、Office 365 と Azure アクセス権管理 (Azure RMS) を使用します。
  
詳細については、次のリソースを参照してください。
  
- [Azure アクセス権の管理とは何ですか。](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
    
- [Office 365 管理センターで Rights Management をアクティブにする](https://support.office.com/article/5b6d3ac7-b1ac-428e-b03e-50e882f85a6e)
    
- [SharePoint 管理センターでの情報権利管理 (IRM) を設定します。](set-up-irm-in-sp-admin-center.md)
    
## <a name="how-do-i"></a>操作方法.

|**この処理を実行するには**|**これらのリソースを参照してください。**|
|:-----|:-----|
|組織内での暗号化を設定します。  <br/> |[Office 365 Enterprise で暗号化を設定する](set-up-encryption.md) <br/> |
|Office 365 の証明書、技術、および TLS 暗号スイートの詳細を表示します。  <br/> |[Office 365 での暗号化に関する技術的な詳細](technical-reference-details-about-encryption.md) <br/> |
|モバイル デバイス上で暗号化されたメッセージを操作します。  <br/> |[Android デバイスで暗号化されたメッセージを表示します。](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [IPhone または iPad で暗号化されたメッセージを表示します。](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|パスワード保護を使用してドキュメントを暗号化します。  <br/><br/>  現時点では、パスワードによる保護では、Office Online でサポートされていません。パスワード保護のためには、デスクトップ バージョンの Word、Excel、および PowerPoint を使用します。           |[ドキュメント、ブック、またはプレゼンテーションの保護を追加または削除します。](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)(**追加の保護**] セクションを選択して**暗号化パスワードを使用して**参照してください)  <br/> |
|ドキュメントの暗号化を解除します。  <br/> |[ドキュメント、ブック、またはプレゼンテーションの保護を追加または削除します。](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)(**保護を解除する**セクションを選択し、し、[**パスワードの暗号化を解除**を参照してください)  <br/> |
   
## <a name="related-topics"></a>関連項目

[Office 365 のセキュリティ、情報保護の機能の計画します。](https://support.office.com/article/3d4ac4a1-3920-4ff9-918f-011f3ce60408)
  
[セキュリティとビジネスの管理のヘルプを Office 365 でのコンプライアンス](https://support.office.com/article/7fe448f7-49bd-4d3e-919d-0a6d1cf675bb)
  

