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
# <a name="protect-access-to-data-and-services-in-office-365"></a><span data-ttu-id="2cebb-103">Office 365 でデータやサービスへのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="2cebb-103">Protect access to data and services in Office 365</span></span>

<span data-ttu-id="2cebb-p101">Office 365 のデータとサービスへのアクセスを保護することは、サイバー攻撃に対する防御と、データの損失から保護するために重要です。環境内での他の SaaS アプリケーションに同レベルの保護を適用することができ、Azure Active Directory アプリケーション プロキシのオンプレミス アプリケーションにも公開します。</span><span class="sxs-lookup"><span data-stu-id="2cebb-p101">Protecting access to your Office 365 data and services is crucial to defending against cyber-attacks and guarding against data loss. The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="2cebb-106">手順 1: 推奨事項の検討</span><span class="sxs-lookup"><span data-stu-id="2cebb-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="2cebb-107">Office 365、他の SaaS サービス、および Azure AD アプリケーション プロキシで公開したオンプレミス アプリケーションにアクセスする ID とデバイスを保護するために推奨される機能。</span><span class="sxs-lookup"><span data-stu-id="2cebb-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="2cebb-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [その他の言語](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="2cebb-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-configure-mfa"></a><span data-ttu-id="2cebb-109">MFA を構成する手順 2。</span><span class="sxs-lookup"><span data-stu-id="2cebb-109">Step 2: Configure MFA</span></span>

<span data-ttu-id="2cebb-110">MFA の向きを自分で、お客様に適したバージョンを決定するこれらのリソースを使用し、計画および展開 MFA 環境に。</span><span class="sxs-lookup"><span data-stu-id="2cebb-110">Use these resources to orient yourself to MFA, decide which version is right for you, and then plan and deploy MFA for your environment.</span></span>
  
- [<span data-ttu-id="2cebb-111">Azure の多要素認証とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="2cebb-111">What is Azure multi-factor authentication?</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication)
    
- [<span data-ttu-id="2cebb-112">Azure の多要素認証ソリューションを選択してください。</span><span class="sxs-lookup"><span data-stu-id="2cebb-112">Choose the Azure multi-factor authentication solution for you</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="2cebb-113">Azure の多要素認証を取得する方法</span><span class="sxs-lookup"><span data-stu-id="2cebb-113">How to get Azure multi-factor authentication</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-versions-plans)
    
- [<span data-ttu-id="2cebb-114">Office 365 の展開の多要素認証の計画</span><span class="sxs-lookup"><span data-stu-id="2cebb-114">Plan for multi-factor authentication for Office 365 deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [<span data-ttu-id="2cebb-115">Office 365 のユーザーに対して多要素認証を設定します</span><span class="sxs-lookup"><span data-stu-id="2cebb-115">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
- [<span data-ttu-id="2cebb-116">MFA、クラウドまたはオンプレミスの展開を計画します。</span><span class="sxs-lookup"><span data-stu-id="2cebb-116">Plan where to deploy MFA, Cloud or on-premises</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started)
    
- [<span data-ttu-id="2cebb-117">Azure の多元的な認証設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2cebb-117">Configure Azure multi-factor authentication settings</span></span>](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-whats-next)
    
## <a name="step-3-enforce-mfa-with-azure-ad-conditional-access-rules"></a><span data-ttu-id="2cebb-118">手順 3: Azure AD の条件付きのアクセス ルールで MFA を適用します。</span><span class="sxs-lookup"><span data-stu-id="2cebb-118">Step 3: Enforce MFA with Azure AD conditional access rules</span></span>

<span data-ttu-id="2cebb-119">Azure AD の MFA を使用する場合は、Office 365 と、環境内の他の SaaS アプリケーションへのアクセスに MFA を必要とする条件付きのアクセス ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="2cebb-119">If you are using Azure AD MFA, create a conditional access rule to require MFA for access to Office 365 and other SaaS apps in your environment.</span></span>
  
- [<span data-ttu-id="2cebb-120">Azure Active Directory 内の条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="2cebb-120">Conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
    
## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="2cebb-121">ステップ 4: SharePoint のデバイスのアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2cebb-121">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="2cebb-p102">SharePoint Online およびビジネスのための OneDrive のデバイスのアクセス ポリシーは、機密性の高い、分類、および規制対象のデータの保護に適しています。準備中は、デバイスのアクセス ポリシーを個々 のチーム サイトに適用する機能です。</span><span class="sxs-lookup"><span data-stu-id="2cebb-p102">Device access policies for SharePoint Online and OneDrive for Business are recommended for protecting sensitive, classified, and regulated data. Coming soon is the ability to apply device access policies to individual team sites.</span></span>
  
- [<span data-ttu-id="2cebb-124">非管理対象デバイスからのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="2cebb-124">Control access from unmanaged devices</span></span>](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&amp;rs=en-US&amp;ad=US)
    
## <a name="step-5-configure-app-and-data-protection-for-devices"></a><span data-ttu-id="2cebb-125">手順 5: デバイス用のアプリケーションとデータの保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="2cebb-125">Step 5: Configure app and data protection for devices</span></span>

<span data-ttu-id="2cebb-p103">モバイル デバイス管理のためのデバイスを登録するかどうかに関係なく、モバイル デバイス上のアプリケーションを管理することができます。これは、メールやファイルなど、Office 365 内のデータの偶発的な漏えいから保護します。</span><span class="sxs-lookup"><span data-stu-id="2cebb-p103">You can manage applications on mobile devices regardless of whether the devices are enrolled for mobile device management. This protects against accidental leakage of data in Office 365, including mail and files.</span></span>
  
- <span data-ttu-id="2cebb-128">IOS および Android: [Microsoft Intune とアプリケーションの保護ポリシーを使用してアプリケーション データを保護](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="2cebb-128">For iOS and Android: [Protect app data using app protection policies with Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)</span></span>
    
<span data-ttu-id="2cebb-129">Windows 10、偶発的なデータ漏洩を防ぐために Windows の情報の保護 (WIP) を構成します。</span><span class="sxs-lookup"><span data-stu-id="2cebb-129">For Windows 10, configure Windows Information Protection (WIP) to prevent accidental data leaks.</span></span>
  
- <span data-ttu-id="2cebb-130">管理下のデバイス: [Microsoft Intune の Azure ポータルを使用した登録ポリシーを使用して Windows の情報の保護 (WIP) を作成します。](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span><span class="sxs-lookup"><span data-stu-id="2cebb-130">For managed devices: [Create a Windows Information Protection (WIP) with enrollment policy using the Azure portal for Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span></span>
    
- <span data-ttu-id="2cebb-131">管理されていないデバイスの:[作成 Intune の Windows 情報保護 (WIP) アプリケーションの保護ポリシーを展開し、](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span><span class="sxs-lookup"><span data-stu-id="2cebb-131">For un-managed devices: [Create and deploy Windows Information Protection (WIP) app protection policy with Intune](https://docs.microsoft.com/intune/windows-information-protection-policy-create)</span></span>
    
## <a name="step-6-manage-devices-with-intune"></a><span data-ttu-id="2cebb-132">Intune でデバイスを管理する手順 6。</span><span class="sxs-lookup"><span data-stu-id="2cebb-132">Step 6: Manage devices with Intune</span></span>

<span data-ttu-id="2cebb-p104">デバイスを管理することは正常な準拠、環境内のリソースへのアクセスを許可する前にことを確認できます。デバイス ベースの条件付きのアクセス ルールにより、攻撃者にアクセスできません、リソース管理されていないデバイスからことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2cebb-p104">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment. Device based conditional access rules help ensure attackers can't gain access to your resources from unmanaged devices.</span></span>
  
- [<span data-ttu-id="2cebb-135">Intune で管理するためのデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="2cebb-135">Enroll devices for management in Intune</span></span>](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
    
## <a name="step-7-configure-additional-intune-policies-and-conditional-access-rules-for-your-environment"></a><span data-ttu-id="2cebb-136">Intune ポリシーを追加し、環境の条件付きのアクセス ルールを構成する手順 7。</span><span class="sxs-lookup"><span data-stu-id="2cebb-136">Step 7: Configure additional Intune policies and conditional access rules for your environment</span></span>

<span data-ttu-id="2cebb-137">推奨される構成が企業規模や高度なアクセス セキュリティのシナリオの開始点としてこれらを使用します。</span><span class="sxs-lookup"><span data-stu-id="2cebb-137">Use these recommended configurations as a starting point for enterprise scale or sophisticated access security scenarios.</span></span>
  
- [<span data-ttu-id="2cebb-138">セキュリティで保護された電子メール ポリシーと構成</span><span class="sxs-lookup"><span data-stu-id="2cebb-138">Secure email policies and configurations</span></span>](https://docs.microsoft.com/azure/active-directory/secure-email-introduction)
    

