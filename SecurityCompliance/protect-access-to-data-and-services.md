---
title: Office 365 でデータやサービスへのアクセスを保護する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: O365 データおよびサービスへのアクセスを保護するためのランディングページ
ms.openlocfilehash: 95933c5a7bc95f9fd70e8f3470055b57193971d4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213537"
---
# <a name="protect-access-to-data-and-services-in-office-365"></a>Office 365 でデータやサービスへのアクセスを保護する

Office 365 のデータおよびサービスへのアクセスを保護することは、サイバー攻撃を防御し、データ損失を防ぐために不可欠です。同じ保護を、環境内の他の SaaS アプリケーション、および Azure Active Directory アプリケーションプロキシで公開されているオンプレミスアプリケーションにも適用できます。
  
## <a name="step-1-review-recommendations"></a>手順 1: 推奨事項を確認する

Office 365、他の SaaS サービス、および Azure AD アプリケーション プロキシで公開したオンプレミス アプリケーションにアクセスする ID とデバイスを保護するために推奨される機能。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [その他の言語](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-configure-mfa"></a>手順 2: MFA を構成する

これらのリソースを使用して、mfa を確認し、適切なバージョンを決定して、環境に対して mfa を計画して展開します。
  
- [Azure 多要素認証とは](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [Azure 多要素認証ソリューションを選択する](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [Azure 多要素認証を取得する方法](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [Office 365 の展開で多要素認証を計画する](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [Office 365 の多要素認証を設定する](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [MFA、クラウド、またはオンプレミスを展開する場所を計画する](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [Azure 多要素認証の設定を構成する](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a>手順 3: Azure AD 条件付きアクセスルールで MFA を適用する

Azure AD MFA を使用している場合は、環境内の Office 365 およびその他の SaaS アプリへのアクセスに MFA を必要とする条件付きアクセスルールを作成します。
  
- [Azure Active Directory での条件付きアクセス](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-privileged-access-management"></a>手順 4: 特権アクセス管理を構成する

特権アクセス管理を使用すると、Office 365 の特権のある管理タスクに対して詳細なアクセス制御を行うことができます。 機密データへの継続的なアクセス、または重要な構成設定へのアクセスを備えた既存の特権のある管理者アカウントを使用する可能性がある侵害から組織を保護するのに役立ちます。

- [特権アクセス管理の概要](privileged-access-management-overview.md)
- [特権アクセス管理を構成する](privileged-access-management-configuration.md)

## <a name="step-5-configure-sharepoint-device-access-policies"></a>手順 5: SharePoint デバイスアクセスポリシーを構成する

機密、分類、および規制されたデータを保護するには、SharePoint Online と OneDrive for business のデバイスアクセスポリシーをお勧めします。近日中に、デバイスアクセスポリシーを個々のチームサイトに適用できるようになります。
  
- [非管理対象デバイスからのアクセスを制御する](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-6-configure-app-and-data-protection-for-devices"></a>手順 6: デバイスのアプリとデータ保護を構成する

モバイルデバイス管理のためにデバイスが登録されているかどうかに関係なく、モバイルデバイス上のアプリケーションを管理できます。これにより、メールやファイルを含む Office 365 のデータの偶発的な漏洩から保護されます。
  
- iOS および Android の場合: [Microsoft Intune でアプリ保護ポリシーを使用してアプリデータを保護する](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
    
windows 10 では、誤ってデータが漏洩しないように windows 情報保護 (WIP) を構成します。
  
- 管理対象デバイスの場合: [Microsoft Intune の Azure portal を使用して登録ポリシーで Windows 情報保護 (WIP) を作成する](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
    
- 管理されていないデバイスの場合: [Intune で Windows 情報保護 (WIP) アプリ保護ポリシーを作成および展開](https://docs.microsoft.com/intune/windows-information-protection-policy-create)する
    
## <a name="step-7-manage-devices-with-intune"></a>手順 7: Intune を使用してデバイスを管理する

デバイスを管理することにより、環境内のリソースへのアクセスを許可する前に、それらを正常かつ準拠していることを確認できます。デバイスベースの条件付きアクセスルールは、攻撃者が管理されていないデバイスからリソースにアクセスできないようにするのに役立ちます。
  
- [Intune で管理するためのデバイスの登録](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-8-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a>手順 8: 環境に対して追加の Intune ポリシーおよび条件付きアクセスルールを構成する

これらの推奨される構成は、エンタープライズ規模または洗練されたアクセスセキュリティシナリオの開始点として使用します。
  
- [セキュリティで保護された電子メールポリシーと構成](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    

