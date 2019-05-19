---
title: Office 365 での暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/3/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Office 365 では、使用可能な最強の暗号化、プロトコル、およびテクノロジを使用して、コンテンツが保存中で転送中に暗号化されます。 Office 365 の暗号化の概要について説明します。
ms.openlocfilehash: 3cd72b3caf26c18ca6836490bc3cd48c2977863b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154719"
---
# <a name="encryption-in-office-365"></a>Office 365 の暗号化

暗号化は、ファイル保護と情報保護戦略の重要な部分です。 この記事では、Office 365 のすべてのバージョンで使用されている暗号化の概要を説明し、暗号化タスクに関するヘルプを取得するために、「組織の暗号化を設定する」から「Office ドキュメントをパスワードで保護する」までを参照してください。
  
- TLS などの証明書とテクノロジに関する情報をお探しの場合は、「 [Office 365 の暗号化に関するテクニカルリファレンスの詳細](technical-reference-details-about-encryption.md)」を参照してください。

- 組織のために暗号化を構成または設定する方法については、「 [Office 365 Enterprise で暗号化を設定](set-up-encryption.md)する」を参照してください。

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>暗号化とは何ですか。 Office 365 ではどのように動作しますか?

高レベルでは、暗号化とは、データ (プレーンテキストと呼ばれます) を、ユーザーまたはコンピューターで使用できない暗号化テキストにエンコードするプロセスです。 復号化には、承認されたユーザーのみが所有する暗号化キーが必要です。 暗号化を使用すると、承認された受信者のみが、電子メールメッセージやファイルなどのコンテンツを解読できるようになります。
  
暗号化だけでは、ファイル、電子メールメッセージ、予定表のエントリなどのコンテンツを不適切な手で保護することはできません。 暗号化は、組織にとってより大きな情報保護戦略の一部となります。 暗号化を使用することで、暗号化されたデータを使用できるユーザーのみがサポートできるようになります。
  
一度に複数の暗号化レイヤーを設定することができます。 たとえば、電子メールメッセージと、電子メールがフローする通信チャネルも暗号化できます。 Office 365 では、データは保存時に暗号化され、複数の強力な暗号化プロトコル、およびトランスポート層セキュリティ/Secure Sockets Layer (TLS/SSL)、インターネットプロトコルセキュリティ (IPSec)、および高度な暗号化を含むテクノロジが使用されます。標準 (AES)。
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>保存中のデータと転送中のデータの暗号化

 **Rest のデータの例**としては、SharePoint ライブラリにアップロードされたファイル、Project Online のデータ、Skype for business の会議にアップロードされたドキュメント、電子メールメッセージ、および 365 Office のフォルダーに保存されている添付ファイルなどがあります。メールボックスおよび OneDrive for business にアップロードされたファイル。 
  
 **転送中のデータの例**には、配信処理中のメールメッセージ、またはオンライン会議で行われている会話が含まれます。 Office 365 では、ユーザーのデバイスが Office 365 サーバーと通信している場合、または Office 365 サーバーが別のサーバーと通信している場合、データは転送されます。 
  
Office 365 では、複数のレイヤーと種類の暗号化を共同作業してデータをセキュリティで保護することができます。 次の表に、いくつかの例を示し、追加情報へのリンクを掲載しています。
  
|**コンテンツの種類**|**暗号化テクノロジ**|**詳細については、リソースを参照してください**|
|:-----|:-----|:-----|
|デバイス上のファイル。 これには、フォルダーに保存された電子メールメッセージ、コンピューター、タブレット、電話に保存された Office ドキュメント、または Microsoft クラウドに保存されたデータが含まれます。  <br/> |Microsoft データセンター内の BitLocker。 BitLocker は、Windows コンピューターやタブレットなどのクライアントマシンでも使用できます。  <br/> Microsoft データセンターでの Distributed Key Manager (DKM)  <br/> Office 365 の顧客キー  <br/> |[Windows IT センター: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft セキュリティセンター: 暗号化](https://www.microsoft.com/en-us/TrustCenter/Security/Encryption) <br/> [Cloud security controls series: 休息中のデータを暗号化する](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online が電子メールの機密情報をセキュリティで保護する方法](exchange-online-secures-email-secrets.md) <br/> [顧客キーを使用して Office 365 でデータを制御する](controlling-your-data-using-customer-key.md) <br/> |
|ユーザー間で転送中のファイル。 これには、ユーザー間で共有する Office ドキュメントまたは SharePoint リストアイテムを含めることができます。  <br/> |送信中のファイルの TLS  <br/> |[OneDrive for Business および SharePoint Online におけるデータ暗号化](data-encryption-in-odb-and-spo.md) <br/> [Skype for Business Online: セキュリティとアーカイブ](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|受信者間で送信中の電子メール。 これには、Exchange Online でホストされる電子メールが含まれます。  <br/> |送信中の電子メールのための Azure Rights Management、S/MIME、TLS を使用した Office 365 メッセージの暗号化  <br/> |[Office 365 Message Encryption (OME)](ome.md) <br/> [Office 365 での電子メールの暗号化](email-encryption.md) <br/> [Exchange Online が TLS を使って Office 365 のメール接続をセキュリティで保護する方法](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>セキュリティとコンプライアンスの要件を満たすために、暗号化についてより詳細に制御する必要がある場合はどうすればよいですか?

Office 365 でのボリューム暗号化、ファイル暗号化、メールボックス暗号化の Microsoft 管理ソリューションに加えて、顧客管理オプションを使用して、より厳しいセキュリティおよびコンプライアンスの要件を満たすことができます。 このようなソリューションでは、Office 365 と組み合わせて Azure Rights Management (Azure RMS) を使用します。
  
詳細については、以下のリソースを参照してください。
  
- [Azure Rights Management とは](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [Office 365 管理センターで Rights Management をアクティブにする](https://support.office.com/article/5b6d3ac7-b1ac-428e-b03e-50e882f85a6e)

- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)

## <a name="how-do-i"></a>方法

|**このタスクを実行するには**|**次のリソースを参照**|
|:-----|:-----|
|組織の暗号化の設定  <br/> |[Office 365 Enterprise で暗号化を設定する](set-up-encryption.md) <br/> |
|Office 365 の証明書、テクノロジ、TLS 暗号スイートに関する詳細を表示する  <br/> |[Office 365 での暗号化に関する技術的な詳細](technical-reference-details-about-encryption.md) <br/> |
|モバイルデバイスで暗号化されたメッセージを操作する  <br/> |[Android デバイスで暗号化されたメッセージを表示する](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [IPhone または iPad で暗号化されたメッセージを表示する](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|パスワード保護を使用してドキュメントを暗号化する  <br/><br/>  現時点では、Office Online ではパスワード保護はサポートされていません。 デスクトップ版の Word、Excel、および PowerPoint をパスワード保護に使用します。           |[文書、ブック、またはプレゼンテーションの保護を追加または削除する](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)([**保護の追加**] セクションを選択し、[**パスワードで暗号化**する] をクリックします)。  <br/> |
|文書から暗号化を削除する  <br/> |[文書、ブック、またはプレゼンテーションの保護を追加または削除する](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)([**保護の解除**] セクションを選択し、[**パスワード暗号化の解除**] をクリックします)。  <br/> |

## <a name="related-topics"></a>関連項目

[Office 365 のセキュリティおよび情報保護機能を計画する](https://support.office.com/article/3d4ac4a1-3920-4ff9-918f-011f3ce60408)
  
[一般法人向け Office 365 のセキュリティとコンプライアンス-管理者向けヘルプ](https://support.office.com/article/7fe448f7-49bd-4d3e-919d-0a6d1cf675bb)