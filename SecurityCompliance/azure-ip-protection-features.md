---
title: 既存の Office 365 テナントにロールアウト Azure の情報保護の保護機能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
description: 2018年 7 月 Azure 情報の保護対象となるテナントのすべての開始、お客様の情報保護における最初のステップを支援するには、は Azure の情報保護の保護機能オンにして既定では。Azure の情報保護の保護機能はされた権限管理や Azure RMS として Office 365 で呼ばれていました。Office E3 のサービス プランやサービスの向上の計画がある場合は、これらの機能を展開すると、Azure の情報保護を使用して情報を保護することを簡単に開始を今すぐ表示されます。
ms.openlocfilehash: be0200da3032dccbcf54e67f3bdfbac800b65526
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531879"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-office-365-tenants"></a>既存の Office 365 テナントにロールアウト Azure の情報保護の保護機能

2018年 7 月 Azure 情報の保護対象となるテナントのすべての開始、お客様の情報保護における最初のステップを支援するには、は Azure の情報保護の保護機能オンにして既定では。Azure の情報保護の保護機能はされた権限管理や Azure RMS として Office 365 で呼ばれていました。Office E3 のサービス プランやサービスの向上の計画がある場合は、これらの機能を展開すると、Azure の情報保護を使用して情報を保護することを簡単に開始を今すぐ表示されます。
  
## <a name="changes-beginning-july-1-2018"></a>開始、2018 年 7 月 1 日の変更

開始 2018 年 7 月 1日マイクロソフトで有効に Azure の情報保護の保護機能購入プランを次のいずれかを持っているすべての Office 365 テナント。
  
- Office 365 Office 365 の E3 と E5、マイクロソフト E3 と E5、Office 365 の A1、A3、A5、および Office 365 の第 3 世代との G5 の一部としてメッセージの暗号化が提供されます。Azure 情報保護により、新しい保護機能を表示するのには追加のライセンスを使用する必要はありません。 
    
- Azure 情報保護計画する場合は 1 次が新しい Office 365 のメッセージの暗号化機能を受信する計画を追加することも: Exchange オンライン計画 1、Exchange オンライン計画 2、Office 365 の F1、Office 365 の業務に関する重要事項、Office 365 のビジネス プレミアム、またはOffice 365 エンタープライズ E1。
    
- 各ユーザーが Office 365 のメッセージの暗号化のメリットは、この機能によってカバーされるライセンスを取得する必要があります。
    
- 完全なリストについては、Office 365 のメッセージの暗号化の[Exchange Online のサービスの説明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)を参照してください。 
    
テナント管理者は、Office 365 管理者ポータルでは、保護のステータスを確認できます。 
  
![Office 365 にアクセス権の管理を有効にするかを示すスクリーン ショットです。](media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)
  
## <a name="why-are-we-making-this-change"></a>この変更はなぜどうしているのでしょうか。

Office 365 のメッセージの暗号化では、Azure の情報保護の保護機能を活用します。Office 365 のメッセージの暗号化に最新の機能強化およびマイクロソフトの 365 の情報保護をより広範な投資の中核となる、私たちは容易にすることをオンにし、従来、暗号化と私たちの保護機能を使用して組織のテクノロジを設定することが困難にされています。既定では、Azure の情報保護の保護機能をオンを迅速に開始、機密データを保護するために。
  
## <a name="does-this-impact-me"></a>影響は私ですか。

Office 365 の組織が対象となる Office 365 のライセンスを購入した場合、テナントはこの変更によって影響を受けるが。
  
 **重要!** オンプレミス環境で Active Directory Rights Management サービス (AD RMS) を使用する場合を無効にこの変更の直後にか 30 日以内には、この変更を展開する前に、Azure の情報保護への移行です。脱退には、この資料の後半の「AD RMS を使用して、out? を選択する方法」を参照してください方法の詳細について。移行する場合を参照してください[AD RMS から Azure 情報保護への移行します](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。
  
## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Active Directory Rights Management サービス (AD RMS) と Azure の情報保護を使用できますか。

違います。サポートされている展開シナリオではありません。脱退の追加手順を行わなくては、一部のコンピューターは Azure の権限の管理サービスを使用するを自動的に開始および AD RMS クラスターに接続しても可能性があります。このシナリオでは、サポートされていないし、これらの新機能を展開する前に、次の 30 日以内には、この変更のオプションを選択することが重要ですので、信頼性の低い結果を持ちます。脱退には、この資料の後半の「AD RMS を使用して、out? を選択する方法」を参照してください方法の詳細について。移行する場合を参照してください[AD RMS から Azure 情報保護への移行します](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。
  
## <a name="how-do-i-know-if-im-using-ad-rms"></a>かどうかは、AD RMS を使用して方法を教えてください。

AD RMS を展開しているかどうかを確認するのにには、 [Azure アクセス権の管理と、Active Directory Rights Management サービス (AD RMS) のための環境を準備しています](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms)から、次の手順を使用します。 
  
1. オプションですが、ほとんどの AD RMS の展開はドメイン コンピューターが AD RMS クラスターを検出できるように、Active Directory にサービス接続ポイント (SCP) を発行します。 
  
ADSI Edit を使用して、SCP が Active Directory で公開されているがあるかどうかを参照してください: CN = 構成の [サーバー名] で、CN = サービス、CN = RightsManagementServices、CN = SCP
    
2. Windows レジストリを使用してクライアント側のサービスの検出またはライセンスのリダイレクトの AD RMS クラスターに接続している Windows コンピューターを構成する必要があります、SCP を使用していない場合: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation または HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation 
  
これらのレジストリの構成の詳細については、 [Windows レジストリを使用してクライアント側のサービス検出を有効にして](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry)、[リダイレクトのライセンス サーバーのトラフィック](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)を参照してください。
    
## <a name="i-use-ad-rms-how-do-i-opt-out"></a>使用して AD RMS では、どのように操作を行いますか脱退か。

今後の変更を無効にするには、これらの操作を行います。
  
1. 大域管理者アクセス許可を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)を参照してください。
    
2. 次の構文を使用してセット IRMConfiguration コマンドレットを実行します。
    
  ```
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false 
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>どのようなことができますこの変更が行われた後に期待どおりですか。

新しいバージョンの[Microsoft の Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801)で発表されました、Azure の情報の暗号化と保護機能を活用して Office 365 のメッセージの暗号化の使用を開始するにはこれが有効にすると、削除していない限り、保護します。 
  
![ホームのスクリーン ショットには、web 上の Outlook でメッセージが保護されています。](media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)
  
新しい拡張機能の詳細については、 [Office 365 のメッセージの暗号化](ome.md)を参照してください。
  

