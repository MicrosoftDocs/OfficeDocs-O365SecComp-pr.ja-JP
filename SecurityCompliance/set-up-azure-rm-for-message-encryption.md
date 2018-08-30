---
title: Office 365 Message Encryption 用に Azure Rights Management を設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/3/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 'Office 365 のメッセージの暗号化は、Microsoft Azure アクセス権の管理 (以前は Windows Azure Active Directory の権限の管理と呼ばれます) によって異なります。 '
ms.openlocfilehash: 99c8de49330cf99545d28d81e0c99c2138797356
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532199"
---
# <a name="set-up-azure-rights-management-for-office-365-message-encryption"></a>Office 365 Message Encryption 用に Azure Rights Management を設定する

アクティブにしを Azure の権限の管理 (RMS)、Office 365 メッセージの暗号化 (ホーム) を使用して、Azure の情報保護の部分を設定するために以下の必要な手順について説明します。
  
## <a name="prerequisites-for-using-office-365-message-encryption"></a>Office 365 Message Encryption を使用するための前提条件
<a name="warmprereqs"> </a>

Office 365 メッセージの暗号化 (ホーム)、IRM を含むは、Azure アクセス権管理 (Azure RMS) によって異なります。Azure の RMS は、情報保護の Azure で使用される保護技術です。ホームを使用するには、Office 365 の組織は、著作権管理の Azure サブスクリプションが含まれますが、オンライン Exchange または Exchange のオンライン保護のサブスクリプションを含める必要があります。
  
- お申し込みの内容のことを確認していない場合は、[メッセージのポリシー、リカバリ、コンプライアンス](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)に関する Exchange Online のサービスの説明を参照してください。
    
- RMS の Azure サブスクリプションのオンラインの Exchange または Exchange のオンライン保護をお持ちでない場合は、サブスクリプションを購入および最初に有効にする必要があります。
    
    Azure アクセス権の管理へのサブスクリプションの購入方法の詳細については、 [Azure アクセス権の管理](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT)を参照してください。次のセクションでは、Azure の権限管理のアクティブ化についての情報を示します。
    
- Azure アクセス権の管理を有効にする方法について説明 Azure アクセス権の管理がある場合は、Exchange Online または Exchange のオンライン保護設定されていないし、Azure アクセス権の管理に使用するホームを設定する最善の方法を説明します。
    
- 既に設定したホームで使用する Azure アクセス権管理オンライン Exchange または Exchange のオンライン保護を設定する方法によって場合は、ホームおよびその新機能をすぐに使用を開始する準備が完了する必要があります。この資料では、かどうかしたホームを正しくセットアップすることを確認する方法、設定を変更する必要がある場合の対処方法と、設定を変更しないように選択する場合の対処について説明します。などの新機能を使用するためには、ホームで Azure RMS を使用する必要があります。オンプレミス Active ディレクトリ RMS では、新しい機能を使用できません。
    
## <a name="activate-azure-rights-management-for-ome-in-office-365"></a>Office 365 でホームの Azure の著作権管理を有効化します。
<a name="activatewarm"> </a>

Azure アクセス権の管理を有効に、組織内のユーザーがメッセージを送信すると、情報の保護を適用し、メッセージと Azure の権利管理サービスによって保護されているファイルを開くようにする必要があります。手順については、 [Azure アクセス権の管理をアクティブにする](https://go.microsoft.com/fwlink/p/?LinkId=525775)を参照してください。ライセンス認証の手続きが完了したら、ここを返し、この資料内のタスクを続行します。
  
## <a name="set-up-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>信頼された発行ドメイン (TPDs) をインポートすると、Azure の RMS を使用するホームを設定します。
<a name="importTPDs"> </a>

TPD は、組織の権限の管理の設定に関する情報を含む XML ファイルです。など、TPD には、署名と証明書とライセンスの暗号化に使用されるサーバー ライセンサー証明書 (SLC) に関する情報が含まれている、Url のライセンスおよび発行を使用しています。Office 365 の組織に、TPD をインポートするには、Windows PowerShell を使用します。
  
> [!IMPORTANT]
> 以前は、Active Directory の権限管理サービス (AD RMS) から TPDs を Office 365 の組織にインポートすることもできます。ただし、これを行う新しいホーム機能を使用するを防止する、お勧めできません。組織は、現在、Office 365 では、このような方法を構成する場合は、オンプレミスの Active ディレクトリ RMS から Azure クラウド ・ ベース情報の保護に移行する計画を作成することをお勧めします。詳細については、 [Azure の情報保護に AD RMS からの移行](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)を参照してください。Azure の情報保護への移行が完了するまでは、ホームの新機能を使用することはできません。 
  
 **TPDs を Azure の RMS からインポートするのには**
  
1. [オンライン リモート PowerShell を使用して Exchange に接続](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。
    
2. Office 365 組織の地理的な場所に対応するキーの共有 URL を選択します。
    
|**場所**|**キーの場所の URL を共有します。**|
|:-----|:-----|
|北アメリカ  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|欧州連合  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|アジア  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|南アメリカ  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|行政機関向け Office 365 (行政機関のコミュニティ クラウド)  <br/> この RMS キーを共有の場所は、政府の Sku の Office 365 が購入されたお客様に予約されています。  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. 次のように[セット IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx)コマンドレットを実行してキーを共有の場所を構成します。 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    たとえば、北米では、組織がある場合、場所を共有キーを構成するとします。
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. Azure アクセス権の管理から、TPD をインポートするのには-RMSOnline スイッチを使用して[インポート RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx)コマンドレットを実行します。 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    *TPDName*は、名前、TPD を使用します。たとえば、「Contoso 北米 TPD」。 
    
5. Azure の権限の管理サービスを使用する Office 365 の組織が正常に構成されていることを確認するには、次のように-RMSOnline スイッチを使用して[テスト IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx)コマンドレットを実行します。 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    などでは、このコマンドレット Azure の権限の管理サービスとの接続を確認、TPD をダウンロード、その有効性を確認します。
    
6. Outlook と web 上の Outlook で使用できなくなっている Azure アクセス権の管理テンプレートを無効にするには、次のように[セット IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)コマンドレットを実行します。 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. クラウド ベースの電子メール組織の Azure アクセス権の管理を有効にして、Azure のアクセス権の管理を使用して、Office 365 のメッセージの暗号化を構成する次のように[セット IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)コマンドレットを実行します。 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. 正常に、TPD をインポートしている Azure アクセス権の管理を有効になっていることを確認するには、Azure の著作権管理の機能をテストするのには、テスト IRMConfiguration コマンドレットを使用します。詳細については、[テスト ・ IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)の「例 1」を参照してください。
    
## <a name="i-have-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>ホームが Active Directory の権限管理 Azure の情報保護しないと設定があると、行うことは何ですか?
<a name="importTPDs"> </a>

Active Directory の権限管理で、既存の Office 365 のメッセージの暗号化メール フロー ルールを使用する続行することができますが、構成またはホームの新機能を使用することはできません。代わりに、情報の保護を Azure に移行する必要があります。移行し、これにより、組織の詳細については、 [Azure の情報保護に AD RMS からの移行](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)を参照してください。
  
## <a name="next-steps"></a>次の手順
<a name="importTPDs"> </a>

ホームの新機能を有効にするを参照してくださいする場合は Azure アクセス権の管理のセットアップが完了したら[情報の保護を Azure 上に構築された、新しい Office 365 のメッセージの暗号化機能を設定します](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)。
  
ホームの新機能を使用する組織を設定したら後、は、[ホームの新機能を持つ電子メール メッセージを保護するためにメール フロー ルールを定義](define-mail-flow-rules-to-encrypt-email.md)する準備が整ったら。
  
## <a name="related-topics"></a>関連項目
<a name="importTPDs"> </a>

[Office 365 での暗号化](encryption.md)
  
[Office 365 の暗号化についてのテクニカル リファレンスの詳細](technical-reference-details-about-encryption.md)
  
[Azure アクセス権の管理とは何ですか。](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  

