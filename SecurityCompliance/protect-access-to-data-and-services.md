---
title: Office 365 でデータやサービスへのアクセスを保護する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: O365 データおよびサービスへのアクセスを保護するためのランディング ・ ページ
ms.openlocfilehash: e6e2d8d3ba6482d4b80593bd9e09d49d6120af80
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532409"
---
# <a name="protect-access-to-data-and-services-in-office-365"></a>Office 365 でデータやサービスへのアクセスを保護する

Office 365 のデータとサービスへのアクセスを保護することは、サイバー攻撃に対する防御と、データの損失から保護するために重要です。環境内での他の SaaS アプリケーションに同レベルの保護を適用することができ、Azure Active Directory アプリケーション プロキシのオンプレミス アプリケーションにも公開します。
  
## <a name="step-1-review-recommendations"></a>手順 1: 推奨事項の検討

Office 365、他の SaaS サービス、および Azure AD アプリケーション プロキシで公開したオンプレミス アプリケーションにアクセスする ID とデバイスを保護するために推奨される機能。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [その他の言語](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-configure-mfa"></a>MFA を構成する手順 2。

MFA の向きを自分で、お客様に適したバージョンを決定するこれらのリソースを使用し、計画および展開 MFA 環境に。
  
- [Azure の多要素認証とは何ですか。](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [Azure の多要素認証ソリューションを選択してください。](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [Azure の多要素認証を取得する方法](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [Office 365 の展開の多要素認証の計画](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [Office 365 のユーザーに対して多要素認証を設定します](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [MFA、クラウドまたはオンプレミスの展開を計画します。](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [Azure の多元的な認証設定を構成します。](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a>手順 3: Azure AD の条件付きのアクセス ルールで MFA を適用します。

Azure AD の MFA を使用する場合は、Office 365 と、環境内の他の SaaS アプリケーションへのアクセスに MFA を必要とする条件付きのアクセス ルールを作成します。
  
- [Azure Active Directory 内の条件付きアクセス](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-sharepoint-device-access-policies"></a>ステップ 4: SharePoint のデバイスのアクセス ポリシーを構成します。

SharePoint Online およびビジネスのための OneDrive のデバイスのアクセス ポリシーは、機密性の高い、分類、および規制対象のデータの保護に適しています。準備中は、デバイスのアクセス ポリシーを個々 のチーム サイトに適用する機能です。
  
- [非管理対象デバイスからのアクセスを制御する](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-5-configure-app-and-data-protection-for-devices"></a>手順 5: デバイス用のアプリケーションとデータの保護を構成します。

モバイル デバイス管理のためのデバイスを登録するかどうかに関係なく、モバイル デバイス上のアプリケーションを管理することができます。これは、メールやファイルなど、Office 365 内のデータの偶発的な漏えいから保護します。
  
- IOS および Android: [Microsoft Intune とアプリケーションの保護ポリシーを使用してアプリケーション データを保護](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
    
Windows 10、偶発的なデータ漏洩を防ぐために Windows の情報の保護 (WIP) を構成します。
  
- 管理下のデバイス: [Microsoft Intune の Azure ポータルを使用した登録ポリシーを使用して Windows の情報の保護 (WIP) を作成します。](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
    
- 管理されていないデバイスの:[作成 Intune の Windows 情報保護 (WIP) アプリケーションの保護ポリシーを展開し、](https://docs.microsoft.com/intune/windows-information-protection-policy-create)
    
## <a name="step-6-manage-devices-with-intune"></a>Intune でデバイスを管理する手順 6。

デバイスを管理することは正常な準拠、環境内のリソースへのアクセスを許可する前にことを確認できます。デバイス ベースの条件付きのアクセス ルールにより、攻撃者にアクセスできません、リソース管理されていないデバイスからことを確認します。
  
- [Intune で管理するためのデバイスを登録します。](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-7-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a>Intune ポリシーを追加し、環境の条件付きのアクセス ルールを構成する手順 7。

推奨される構成が企業規模や高度なアクセス セキュリティのシナリオの開始点としてこれらを使用します。
  
- [セキュリティで保護された電子メール ポリシーと構成](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    

