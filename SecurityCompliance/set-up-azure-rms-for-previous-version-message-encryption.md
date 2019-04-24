---
title: Office 365 Message Encryption の旧バージョン用に Microsoft Azure AD Rights Management を設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 以前のバージョンの Office 365 メッセージの暗号化は、Microsoft azure Rights management (旧称 Windows azure Active Directory rights management) に依存します。
ms.openlocfilehash: 89b86035f57699457c86fefb49888b8428f4e01c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266889"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a>Office 365 Message Encryption の旧バージョン用に Microsoft Azure AD Rights Management を設定する

このトピックでは、以前のバージョンの Office 365 Message Encryption (OME) を使用するために、azure Information Protection の一部である azure Rights Management (RMS) をアクティブ化してからセットアップするために従う必要のある手順について説明します。

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>この記事は、以前のバージョンの OME にのみ適用されます。
Office 365 組織を新しい OME 機能に移行していない場合でも、既に OME を展開している場合は、この記事の情報が組織に適用されます。 Microsoft は、組織にとって適切であることをすぐに、新しい OME 機能に移行するための計画を立てることを推奨します。 手順については、「 [Office の新しい365メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」を参照してください。 新しい機能が最初にどのように機能するかについて詳しくは、「 [Office 365 Message Encryption](ome.md)」を参照してください。 この記事の残りの部分では、新しい OME 機能のリリース前の OME の動作を示します。

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>以前のバージョンの Office 365 メッセージ暗号化を使用するための前提条件
<a name="warmprereqs"> </a>

Office 365 Message Encryption (OME) は、IRM を含め、azure Rights Management (azure RMS) に依存しています。 azure RMS は、azure Information protection で使用される保護テクノロジです。 OME を使用するには、Office 365 組織に exchange online または exchange online Protection のサブスクリプションを含める必要があります。これには、Azure Rights Management サブスクリプションが含まれています。
  
- サブスクリプションに含まれる内容がわからない場合は、「Exchange Online サービスの[メッセージポリシー、回復、および準拠](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)」の説明を参照してください。

- Azure RMS サブスクリプションが exchange online または exchange online Protection にない場合は、最初にサブスクリプションを購入してライセンス認証を行う必要があります。

    azure rights management へのサブスクリプションの購入については、「 [azure rights management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT)」を参照してください。 次のセクションでは、Azure Rights Management のアクティブ化に関する情報を提供します。

- azure rights management を使用していても、exchange online または exchange online Protection 用にセットアップされていない場合は、この記事で azure rights management をアクティブ化する方法について説明します。次に、azure rights management と連携するように OME をセットアップするための最適な方法について説明します。

- exchange online または exchange online Protection の Azure Rights Management で作業するための OME を既にセットアップしている場合は、設定方法によっては、OME とその新機能をすぐに使用する準備ができている場合があります。 この記事では、OME が正しく設定されているかどうかを判断する方法、設定を変更する必要がある場合の対処方法、および設定を変更しない場合の対処方法について説明します。 たとえば、新しい機能を使用するためには、Azure RMS を OME と共に使用する必要があります。 オンプレミスの Active Directory RMS で新しい機能を使用することはできません。

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Office 365 の以前のバージョンの OME の Azure Rights Management をアクティブ化する

組織内のユーザーが情報保護を送信するメッセージに適用できるように、azure rights management サービスで保護されたメッセージやファイルを開くには、azure rights management をアクティブ化する必要があります。 手順については、「 [Azure Rights Management をアクティブ化](https://go.microsoft.com/fwlink/p/?LinkId=525775)する」を参照してください。 ライセンス認証を完了したら、ここに戻り、この記事のタスクを続行します。
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>信頼された発行ドメインをインポートすることによって Azure RMS を使用するように以前のバージョンの OME をセットアップする (tpds)

TPD は、組織の権限管理設定に関する情報を含む XML ファイルです。 たとえば、TPD には、証明書とライセンスの署名と暗号化、ライセンスと発行に使用される url などに使用されるサーバーライセンサー証明書 (SLC) に関する情報が含まれています。 Windows PowerShell を使用して、TPD を Office 365 組織にインポートします。
  
> [!IMPORTANT]
> 以前は、Active Directory Rights Management サービス (AD RMS) から Office 365 組織に tpds をインポートすることを選択できました。 ただし、これを行うと、新しい OME 機能を使用できなくなり、推奨されません。 現在 Office 365 組織がこの方法で構成されている場合は、オンプレミスの Active Directory RMS からクラウドベースの Azure Information Protection に移行する計画を作成することをお勧めします。 詳細については、「 [AD RMS から Azure information Protection への移行](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)」を参照してください。 Azure Information Protection への移行が完了するまで、新しい OME 機能を使用することはできません。
  
 **Azure RMS から tpds をインポートするには**
  
1. [リモート PowerShell を使用して Exchange Online に接続](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。

2. Office 365 組織の地理的な場所に対応するキー共有 URL を選択します。

|**場所**|**キー共有場所の URL**|
|:-----|:-----|
|北アメリカ  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|欧州連合  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|地域  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|南アメリカ  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|行政機関向け Office 365 (行政機関のコミュニティ クラウド)  <br/> この RMS キー共有場所は、Office 365 を Government sku 用に購入したお客様向けに予約されています。  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. 次のように、 [Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx)コマンドレットを実行して、キー共有の場所を構成します。 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    たとえば、組織が北米に配置されている場合に、主な共有場所を構成するには、次のように入力します。
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. -RMSOnline スイッチを使用して[import-rmstrustedpublishingdomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx)コマンドレットを実行し、Azure Rights Management から TPD をインポートします。 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    ここで、 *tpdname*は、TPD に対して使用する名前です。 たとえば、「Contoso 社の北米 TPD」とします。 
    
5. Azure Rights Management サービスを使用するように Office 365 組織が正常に構成されたことを確認するには、次のように、-RMSOnline スイッチを使用して[Test-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx)コマンドレットを実行します。 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    特に、このコマンドレットでは、Azure Rights Management サービスとの接続を確認し、TPD をダウンロードして、有効性をチェックします。
    
6. 次のように、 [Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)コマンドレットを実行して、outlook on the web および outlook で Azure Rights Management テンプレートを使用できないようにします。 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. 次のように、 [Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)コマンドレットを実行して、クラウドベースの電子メール組織の azure rights management を有効にし、Office 365 メッセージの暗号化に azure rights management を使用するように構成します。 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. TPD および有効にされた azure rights management が正常にインポートされたことを確認するには、test-irmconfiguration コマンドレットを使用して azure rights management 機能をテストします。 詳細については、「 [Test-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)」の「例1」を参照してください。
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>以前のバージョンの OME が Azure Information Protection ではなく、Active Directory Rights Management を使用して設定されている場合は、どうすればよいですか。
<a name="importTPDs"> </a>

Active Directory Rights Management で既存の Office 365 メッセージ暗号化のメールフロールールを引き続き使用することはできますが、新しい OME 機能を構成したり使用したりすることはできません。 代わりに、Azure Information Protection に移行する必要があります。 移行の詳細と、組織にとっての意味については、「 [AD RMS から Azure information Protection への移行](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)」を参照してください。
  
## <a name="next-steps"></a>次の手順
<a name="importTPDs"> </a>

azure Rights Management のセットアップを完了した後、新しい OME 機能を有効にする場合は、「 [azure Information Protection の上に構築された新しい Office 365 メッセージ暗号化機能のセットアップ](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)」を参照してください。
  
新しい OME 機能を使用するように組織を設定した後、[メールフロールールを定義して、新しい OME 機能で電子メールメッセージを保護](define-mail-flow-rules-to-encrypt-email.md)することができます。
  
## <a name="related-topics"></a>関連項目
<a name="importTPDs"> </a>

[Office 365 での暗号化](encryption.md)
  
[Office 365 の暗号化についてのテクニカル リファレンスの詳細](technical-reference-details-about-encryption.md)
  
[Azure Rights Management とは](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  

