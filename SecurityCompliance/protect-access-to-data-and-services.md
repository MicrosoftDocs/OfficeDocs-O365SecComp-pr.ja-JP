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
# <a name="protect-access-to-data-and-services-in-office-365"></a><span data-ttu-id="0ca7a-103">Office 365 でデータやサービスへのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-103">Protect access to data and services in Office 365</span></span>

<span data-ttu-id="0ca7a-p101">Office 365 のデータおよびサービスへのアクセスを保護することは、サイバー攻撃を防御し、データ損失を防ぐために不可欠です。同じ保護を、環境内の他の SaaS アプリケーション、および Azure Active Directory アプリケーションプロキシで公開されているオンプレミスアプリケーションにも適用できます。</span><span class="sxs-lookup"><span data-stu-id="0ca7a-p101">Protecting access to your Office 365 data and services is crucial to defending against cyber-attacks and guarding against data loss. The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="0ca7a-106">手順 1: 推奨事項を確認する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="0ca7a-107">Office 365、他の SaaS サービス、および Azure AD アプリケーション プロキシで公開したオンプレミス アプリケーションにアクセスする ID とデバイスを保護するために推奨される機能。</span><span class="sxs-lookup"><span data-stu-id="0ca7a-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="0ca7a-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [その他の言語](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="0ca7a-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-configure-mfa"></a><span data-ttu-id="0ca7a-109">手順 2: MFA を構成する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-109">Step 2: Configure MFA</span></span>

<span data-ttu-id="0ca7a-110">これらのリソースを使用して、mfa を確認し、適切なバージョンを決定して、環境に対して mfa を計画して展開します。</span><span class="sxs-lookup"><span data-stu-id="0ca7a-110">Use these resources to orient yourself to MFA, decide which version is right for you, and then plan and deploy MFA for your environment.</span></span>
  
- [<span data-ttu-id="0ca7a-111">Azure 多要素認証とは</span><span class="sxs-lookup"><span data-stu-id="0ca7a-111">What is Azure multi-factor authentication?</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [<span data-ttu-id="0ca7a-112">Azure 多要素認証ソリューションを選択する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-112">Choose the Azure multi-factor authentication solution for you</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="0ca7a-113">Azure 多要素認証を取得する方法</span><span class="sxs-lookup"><span data-stu-id="0ca7a-113">How to get Azure multi-factor authentication</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [<span data-ttu-id="0ca7a-114">Office 365 の展開で多要素認証を計画する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-114">Plan for multi-factor authentication for Office 365 deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [<span data-ttu-id="0ca7a-115">Office 365 の多要素認証を設定する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-115">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [<span data-ttu-id="0ca7a-116">MFA、クラウド、またはオンプレミスを展開する場所を計画する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-116">Plan where to deploy MFA, Cloud or on-premises</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="0ca7a-117">Azure 多要素認証の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-117">Configure Azure multi-factor authentication settings</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a><span data-ttu-id="0ca7a-118">手順 3: Azure AD 条件付きアクセスルールで MFA を適用する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-118">Step 3: Enforce MFA with Azure AD conditional access rules</span></span>

<span data-ttu-id="0ca7a-119">Azure AD MFA を使用している場合は、環境内の Office 365 およびその他の SaaS アプリへのアクセスに MFA を必要とする条件付きアクセスルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="0ca7a-119">If you are using Azure AD MFA, create a conditional access rule to require MFA for access to Office 365 and other SaaS apps in your environment.</span></span>
  
- [<span data-ttu-id="0ca7a-120">Azure Active Directory での条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="0ca7a-120">Conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-privileged-access-management"></a><span data-ttu-id="0ca7a-121">手順 4: 特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-121">Step 4: Configure privileged access management</span></span>

<span data-ttu-id="0ca7a-p102">特権アクセス管理を使用すると、Office 365 の特権のある管理タスクに対して詳細なアクセス制御を行うことができます。 機密データへの継続的なアクセス、または重要な構成設定へのアクセスを備えた既存の特権のある管理者アカウントを使用する可能性がある侵害から組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0ca7a-p102">Privileged access management allows granular access control over privileged admin tasks in Office 365.  It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="0ca7a-124">特権アクセス管理の概要</span><span class="sxs-lookup"><span data-stu-id="0ca7a-124">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="0ca7a-125">特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-125">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

## <a name="step-5-configure-sharepoint-device-access-policies"></a><span data-ttu-id="0ca7a-126">手順 5: SharePoint デバイスアクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-126">Step 5: Configure SharePoint device access policies</span></span>

<span data-ttu-id="0ca7a-p103">機密、分類、および規制されたデータを保護するには、SharePoint Online と OneDrive for business のデバイスアクセスポリシーをお勧めします。近日中に、デバイスアクセスポリシーを個々のチームサイトに適用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0ca7a-p103">Device access policies for SharePoint Online and OneDrive for Business are recommended for protecting sensitive, classified, and regulated data. Coming soon is the ability to apply device access policies to individual team sites.</span></span>
  
- [<span data-ttu-id="0ca7a-129">非管理対象デバイスからのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-129">Control access from unmanaged devices</span></span>](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-6-configure-app-and-data-protection-for-devices"></a><span data-ttu-id="0ca7a-130">手順 6: デバイスのアプリとデータ保護を構成する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-130">Step 6: Configure app and data protection for devices</span></span>

<span data-ttu-id="0ca7a-p104">モバイルデバイス管理のためにデバイスが登録されているかどうかに関係なく、モバイルデバイス上のアプリケーションを管理できます。これにより、メールやファイルを含む Office 365 のデータの偶発的な漏洩から保護されます。</span><span class="sxs-lookup"><span data-stu-id="0ca7a-p104">You can manage applications on mobile devices regardless of whether the devices are enrolled for mobile device management. This protects against accidental leakage of data in Office 365, including mail and files.</span></span>
  
- <span data-ttu-id="0ca7a-133">iOS および Android の場合: [Microsoft Intune でアプリ保護ポリシーを使用してアプリデータを保護する](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="0ca7a-133">For iOS and Android: [Protect app data using app protection policies with Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span></span>
    
<span data-ttu-id="0ca7a-134">windows 10 では、誤ってデータが漏洩しないように windows 情報保護 (WIP) を構成します。</span><span class="sxs-lookup"><span data-stu-id="0ca7a-134">For Windows 10, configure Windows Information Protection (WIP) to prevent accidental data leaks.</span></span>
  
- <span data-ttu-id="0ca7a-135">管理対象デバイスの場合: [Microsoft Intune の Azure portal を使用して登録ポリシーで Windows 情報保護 (WIP) を作成する](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span><span class="sxs-lookup"><span data-stu-id="0ca7a-135">For managed devices: [Create a Windows Information Protection (WIP) with enrollment policy using the Azure portal for Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span></span>
    
- <span data-ttu-id="0ca7a-136">管理されていないデバイスの場合: [Intune で Windows 情報保護 (WIP) アプリ保護ポリシーを作成および展開](https://docs.microsoft.com/intune/windows-information-protection-policy-create)する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-136">For un-managed devices: [Create and deploy Windows Information Protection (WIP) app protection policy with Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span></span>
    
## <a name="step-7-manage-devices-with-intune"></a><span data-ttu-id="0ca7a-137">手順 7: Intune を使用してデバイスを管理する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-137">Step 7: Manage devices with Intune</span></span>

<span data-ttu-id="0ca7a-p105">デバイスを管理することにより、環境内のリソースへのアクセスを許可する前に、それらを正常かつ準拠していることを確認できます。デバイスベースの条件付きアクセスルールは、攻撃者が管理されていないデバイスからリソースにアクセスできないようにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0ca7a-p105">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment. Device based conditional access rules help ensure attackers can't gain access to your resources from unmanaged devices.</span></span>
  
- [<span data-ttu-id="0ca7a-140">Intune で管理するためのデバイスの登録</span><span class="sxs-lookup"><span data-stu-id="0ca7a-140">Enroll devices for management in Intune</span></span>](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-8-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a><span data-ttu-id="0ca7a-141">手順 8: 環境に対して追加の Intune ポリシーおよび条件付きアクセスルールを構成する</span><span class="sxs-lookup"><span data-stu-id="0ca7a-141">Step 8: Configure additional Intune policies and conditional access rules for your environment</span></span>

<span data-ttu-id="0ca7a-142">これらの推奨される構成は、エンタープライズ規模または洗練されたアクセスセキュリティシナリオの開始点として使用します。</span><span class="sxs-lookup"><span data-stu-id="0ca7a-142">Use these recommended configurations as a starting point for enterprise scale or sophisticated access security scenarios.</span></span>
  
- [<span data-ttu-id="0ca7a-143">セキュリティで保護された電子メールポリシーと構成</span><span class="sxs-lookup"><span data-stu-id="0ca7a-143">Secure email policies and configurations</span></span>](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    

