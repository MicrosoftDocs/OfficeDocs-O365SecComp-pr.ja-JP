---
title: 既存の Office 365 テナントにロールアウトされる Azure Information protection の保護機能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
description: 情報を保護するための最初の手順を説明するために、2018年7月に、azure information protection の対象となるすべてのテナントに、azure information protection の保護機能が既定で有効になります。以前は Office 365 では、azure Information protection の保護機能が Rights Management または azure RMS と呼ばれていました。組織に Office E3 service プランまたはより高いサービスプランがある場合は、これらの機能をロールアウトする際に、Azure information Protection を使用して情報の保護を開始することになります。
ms.openlocfilehash: 2484f9b335a6698894046aaf429fdad68d82491e
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223256"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-office-365-tenants"></a>既存の Office 365 テナントにロールアウトされる Azure Information protection の保護機能

情報を保護するための最初の手順を説明するために、2018年7月に、azure information protection の対象となるすべてのテナントに、azure information protection の保護機能が既定で有効になります。以前は Office 365 では、azure Information protection の保護機能が Rights Management または azure RMS と呼ばれていました。組織に Office E3 service プランまたはより高いサービスプランがある場合は、これらの機能をロールアウトする際に、Azure information Protection を使用して情報の保護を開始することになります。
  
## <a name="changes-beginning-july-1-2018"></a>2018年7月1日以降の変更

2018年7月1日以降、次のいずれかのサブスクリプションプランを所有しているすべての Office 365 テナントに対して、Azure Information protection の保護機能が有効になります。
  
- office 365 メッセージの暗号化は、office 365 E3 および e5 の一部として提供されます。 Microsoft E3 and e5、office 365 A1、A3、A5、および office 365 G3 および G5。Azure Information protection によって提供される新しい保護機能を利用するには、追加のライセンスは必要ありません。 
    
- また、次のプランに Azure Information Protection Plan 1 を追加して、新しい Office 365 メッセージの暗号化機能を受け取ることができます。 exchange online プラン1、exchange online プラン2、office 365 F1、office 365 business Essentials、office 365 business Premium、またはOffice 365 Enterprise E1
    
- Office 365 の各ユーザー利点を活用するには、この機能の対象となるライセンスが必要です。
    
- 完全なリストについては、「 [Exchange Online サービスの説明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)」の「Office 365 Message Encryption」を参照してください。 
    
テナント管理者は、Office 365 管理者ポータルで保護の状態を確認できます。 
  
![Office 365 の権限管理がアクティブ化されたことを示すスクリーンショット。](media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)
  
## <a name="why-are-we-making-this-change"></a>この変更を行う理由

Office 365 Message Encryption では、Azure Information protection の保護機能を活用しています。最近の Office 365 メッセージ暗号化の機能強化と、Microsoft 365 における情報保護への幅広い投資に加えて、組織では、以前のように保護機能を有効にして使用することが容易になりました。暗号化テクノロジはセットアップが困難です。Azure Information protection の保護機能を既定で有効にすることにより、機密データの保護をすばやく始めることができます。
  
## <a name="does-this-impact-me"></a>影響はありますか?

office 365 組織が適格な office 365 ライセンスを購入している場合、テナントはこの変更によって影響を受けます。
  
 **重要です。** オンプレミス環境で Active Directory Rights Management サービス (AD RMS) を使用している場合は、この変更をすぐにオプトアウトするか、または Azure Information Protection に移行してから、今後30日間以内にこの変更を展開する必要があります。オプトアウト方法の詳細については、この記事で後述する「AD RMS を使用して、方法を選択する方法 out?」を参照してください。移行を希望する場合は、「 [AD RMS から Azure Information Protection への移行](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)」を参照してください。
  
## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Active Directory Rights Management サービス (AD RMS) で Azure Information Protection を使用できますか?

違います。これは、サポートされている展開シナリオではありません。追加の脱退手順を行わないと、一部のコンピューターでは、Azure Rights Management サービスの使用が自動的に開始され、AD RMS クラスターにも接続される場合があります。このシナリオはサポートされておらず、信頼できない結果があるため、これらの新機能を展開する前に、今後30日以内にこの変更を行わないことが重要です。オプトアウト方法の詳細については、この記事で後述する「AD RMS を使用して、方法を選択する方法 out?」を参照してください。移行を希望する場合は、「 [AD RMS から Azure Information Protection への移行](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)」を参照してください。
  
## <a name="how-do-i-know-if-im-using-ad-rms"></a>AD RMS を使用しているかどうかを確認する方法

[Active Directory rights management サービス (ad rms)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms)を使用して ad rms が展開されているかどうかを確認するときは、次の手順を使用して Azure Rights management の環境を準備します。 
  
1. ほとんどの ad rms 展開はオプションですが、ドメインコンピューターが AD rms クラスターを検出できるように、サービス接続ポイント (SCP) を Active Directory に公開します。 
  
ADSI edit を使用して、Active Directory で発行された SCP があるかどうかを確認します。 cn = Configuration [サーバー名], cn = Services, cn = RightsManagementServices, cn = SCP
    
2. SCP を使用していない場合は、AD RMS クラスターに接続する windows コンピューターを、windows レジストリ: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation または HKEY_ を使用して、クライアント側サービスの検出またはライセンスのリダイレクト用に構成する必要があります。LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation 
  
これらのレジストリ構成の詳細については、「 [Windows レジストリを使用して](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry)[ライセンスサーバーのトラフィックをリダイレクト](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)する」を参照してください。
    
## <a name="i-use-ad-rms-how-do-i-opt-out"></a>AD RMS を使用していますが、どのようにオプトアウトすればよいですか?

今後の変更を中止するには、次の手順を実行します。
  
1. Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、「 [Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)」を参照してください。
    
2. 次の構文を使用して、Set-irmconfiguration コマンドレットを実行します。
    
  ```
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false 
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>この変更を行った後に予想されることは何ですか。

これを有効にしていない場合は、 [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801)で発表された新しいバージョンの Office 365 Message Encryption の使用を開始して、Azure 情報の暗号化および保護機能を活用することができます。保護. 
  
![web 上の Outlook で OME 保護されたメッセージを示すスクリーンショット。](media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)
  
新しい機能の詳細については、「 [Office 365 Message Encryption](ome.md)」を参照してください。
  

