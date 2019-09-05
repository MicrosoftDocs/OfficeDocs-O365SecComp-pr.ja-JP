---
title: ユーザーとデバイス アクセスの保護
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: O365 データおよびサービスへのアクセスを保護するためのランディングページ
ms.openlocfilehash: 9fc1691e7e36f994b5d0b8a6a9735fe8ccd8735a
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761613"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="b171d-103">ユーザーとデバイス アクセスの保護</span><span class="sxs-lookup"><span data-stu-id="b171d-103">Protect user and device access</span></span>

<span data-ttu-id="b171d-104">Office 365 データおよびサービスへのアクセスを保護することは、cyberattacks を防御し、データ損失を防ぐために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="b171d-104">Protecting access to your Office 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="b171d-105">同じ保護を、環境内の他の SaaS アプリケーション、および Azure Active Directory アプリケーションプロキシで公開されているオンプレミスアプリケーションにも適用できます。</span><span class="sxs-lookup"><span data-stu-id="b171d-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="b171d-106">手順 1: 推奨事項を確認する</span><span class="sxs-lookup"><span data-stu-id="b171d-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="b171d-107">Office 365、他の SaaS サービス、および Azure AD アプリケーション プロキシで公開したオンプレミス アプリケーションにアクセスする ID とデバイスを保護するために推奨される機能。</span><span class="sxs-lookup"><span data-stu-id="b171d-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="b171d-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [その他の言語](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="b171d-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="b171d-109">手順 2: 管理者アカウントとアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="b171d-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="b171d-110">Office 365 環境を管理するために使用する管理アカウントには、昇格された特権が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b171d-110">The administrative accounts you use to administer your Office 365 environment include elevated privileges.</span></span> <span data-ttu-id="b171d-111">これらはハッカーおよび cyberattackers の重要な目標です。</span><span class="sxs-lookup"><span data-stu-id="b171d-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="b171d-112">管理者アカウントのみを使用して開始します。</span><span class="sxs-lookup"><span data-stu-id="b171d-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="b171d-113">管理者は、管理者ではない通常の使用に対して個別のユーザーアカウントを持っている必要があります。ジョブ機能に関連付けられたタスクを完了するために必要な場合にのみ、管理アカウントを使用してください。</span><span class="sxs-lookup"><span data-stu-id="b171d-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="b171d-114">多要素認証および条件付きアクセスを使用して管理者アカウントを保護します。</span><span class="sxs-lookup"><span data-stu-id="b171d-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="b171d-115">詳細については、「[管理者アカウントを保護](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b171d-115">For more information, see [Protecting administrator accounts](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="b171d-116">次に、Office 365 で特権アクセス管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="b171d-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="b171d-117">特権アクセス管理を使用すると、Office 365 の特権のある管理タスクに対して詳細なアクセス制御を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b171d-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="b171d-118">機密データへの継続的なアクセス、または重要な構成設定へのアクセスを備えた既存の特権のある管理者アカウントを使用する可能性がある侵害から組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b171d-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="b171d-119">特権アクセス管理の概要</span><span class="sxs-lookup"><span data-stu-id="b171d-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="b171d-120">特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="b171d-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="b171d-121">もう1つの主要な推奨事項は、管理作業用に構成されたワークステーションを使用することです。</span><span class="sxs-lookup"><span data-stu-id="b171d-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="b171d-122">これらは、管理タスクのみに使用される専用デバイスです。</span><span class="sxs-lookup"><span data-stu-id="b171d-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="b171d-123">「[権限](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)のあるアクセスの保護」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b171d-123">See [Securing privileged access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="b171d-124">最後に、テナント内に2つ以上の緊急アクセスアカウントを作成することによって、不注意による管理アクセスが行われない影響を軽減できます。</span><span class="sxs-lookup"><span data-stu-id="b171d-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="b171d-125">「 [AZURE AD でエマージェンシーアクセスアカウントを管理](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b171d-125">See [Manage emergency access accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="b171d-126">手順 3: 推奨される id とデバイスアクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="b171d-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="b171d-127">多要素認証 (MFA) と条件付きアクセスポリシーは、侵害されたアカウントおよび権限のないアクセスを軽減するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="b171d-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="b171d-128">一緒にテストされたポリシーのセットを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b171d-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="b171d-129">展開の手順を含む詳細については、「 [id とデバイスのアクセス構成](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b171d-129">For more information, including deployment steps, see [Identity and device access configurations](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations).</span></span>

 <span data-ttu-id="b171d-130">これらのポリシーは、次の機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="b171d-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="b171d-131">Mult 認証</span><span class="sxs-lookup"><span data-stu-id="b171d-131">Mult-factor authentication</span></span>
- <span data-ttu-id="b171d-132">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="b171d-132">Conditional access</span></span>
- <span data-ttu-id="b171d-133">Intune アプリの保護 (デバイス用のアプリとデータの保護)</span><span class="sxs-lookup"><span data-stu-id="b171d-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="b171d-134">Intune デバイスのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="b171d-134">Intune device compliance</span></span>
- <span data-ttu-id="b171d-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="b171d-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="b171d-136">Intune デバイスコンプライアンスを実装するには、デバイスの登録が必要です。</span><span class="sxs-lookup"><span data-stu-id="b171d-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="b171d-137">デバイスを管理することにより、環境内のリソースへのアクセスを許可する前に、それらを正常かつ準拠していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b171d-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="b171d-138">「 [Intune で管理用のデバイスを登録する](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b171d-138">See [Enroll devices for management in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="b171d-139">手順 4: SharePoint デバイスアクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="b171d-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="b171d-140">Microsoft では、デバイスアクセス制御を使用して、機密および規制の厳しいコンテンツを持つ SharePoint サイトのコンテンツを保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b171d-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="b171d-141">詳細については、「 [SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b171d-141">For more information, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>



    

