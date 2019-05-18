---
title: Office 365 のフィッシング対策保護
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.custom: TopSMBIssues
ms.collection:
- M365-security-compliance
description: Office 365 は、既定では、フィッシング対策のような追加のサービスを通じて、フィッシング攻撃に対するさまざまな保護を提供しています。 このトピックでは、Office 365 でのフィッシング対策のオプションと戦略について学習し、実装するために使用できるオンラインリソースについて説明します。
ms.openlocfilehash: a002002967e3e529cada587f9b0bd29fa867e06e
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155669"
---
# <a name="anti-phishing-protection-in-office-365"></a><span data-ttu-id="6988f-104">Office 365 のフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="6988f-104">Anti-phishing protection in Office 365</span></span>

<span data-ttu-id="6988f-105">Office 365 は、既定では、フィッシング対策のような追加のサービスを通じて、フィッシング攻撃に対するさまざまな保護を提供しています。</span><span class="sxs-lookup"><span data-stu-id="6988f-105">Office 365 offers a variety of protection against phishing attacks by default and also through additional offerings such as ATP anti-phishing.</span></span> <span data-ttu-id="6988f-106">このトピックでは、Office 365 でのフィッシング対策のオプションと戦略について学習し、実装するために使用できるオンラインリソースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6988f-106">This topic introduces the online resources you can use to learn about and implement anti-phishing options and strategies in Office 365.</span></span>
  
## <a name="protect-your-organization-against-phishing-attacks-in-office-365"></a><span data-ttu-id="6988f-107">Office 365 のフィッシング攻撃から組織を保護する</span><span class="sxs-lookup"><span data-stu-id="6988f-107">Protect your organization against phishing attacks in Office 365</span></span>

<span data-ttu-id="6988f-108">Office 365 管理者として、これらのリソースを使用して、Office 365 を使用して偽装ベースのフィッシング攻撃から保護し、悪意のあるフィッシング攻撃に prey れないようにエンドユーザーを教育する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6988f-108">As an Office 365 administrator, use these resources to learn how to use Office 365 to protect against impersonation-based phishing attacks and to help you educate your end users so that they don't fall prey to malicious phishing attacks.</span></span>
  
<span data-ttu-id="6988f-109">Office 365 の構成を変更する前に、Office 365 で提供されている最新の最新のをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="6988f-109">Before you make any changes to your Office 365 configuration, ensure that you're up to date on the latest that Office 365 has to offer.</span></span> <span data-ttu-id="6988f-110">「 [Microsoft セーフティ&amp;セキュリティセンター」を参照して](https://www.microsoft.com/security/default.aspx)ください。</span><span class="sxs-lookup"><span data-stu-id="6988f-110">[Visit the Microsoft Safety &amp; Security Center](https://www.microsoft.com/security/default.aspx).</span></span>
  
<span data-ttu-id="6988f-111">環境をセキュリティで保護するための最も重要なことは、フィッシング攻撃の危険性と警告の兆候についてユーザーを教育することです。</span><span class="sxs-lookup"><span data-stu-id="6988f-111">The most important thing you can do to secure your environment is to educate your users about the dangers and the warning signs of phishing attacks.</span></span> <span data-ttu-id="6988f-112">開始するには、[フィッシングスキームやその他の形式のオンライン詐欺から保護](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546)されている情報をユーザーに理解してください。</span><span class="sxs-lookup"><span data-stu-id="6988f-112">To get started, familiarize your users with the information in [Protect yourself from phishing schemes and other forms of online fraud](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546).</span></span>
  
<span data-ttu-id="6988f-113">Office Enterprise E5 を使用している Office 365 組織の場合は、セキュリティ&amp;コンプライアンスセンターで ATP のフィッシング対策を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6988f-113">For Office 365 organizations with Office Enterprise E5, you can use ATP anti-phishing in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="6988f-114">ATP のフィッシング対策は、一連の機械学習モデルを受信メッセージに適用して、市販およびスピアーフィッシング攻撃に対する保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="6988f-114">ATP anti-phishing applies a set of machine learning models together with impersonation detection algorithms to incoming messages to provide protection for commodity and spear phishing attacks.</span></span> <span data-ttu-id="6988f-115">ATP のフィッシング対策は、Office 365 グローバルまたはセキュリティ管理者によって設定されたポリシーに従って組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="6988f-115">ATP anti-phishing protects your organization according to policies that are set by your Office 365 global or security administrators.</span></span> <span data-ttu-id="6988f-116">詳細については、「 [office 365 の ATP のフィッシング対策機能](atp-anti-phishing.md)」および「 [office 365 でフィッシング対策ポリシーを設定](set-up-anti-phishing-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6988f-116">To learn more, see [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md) and [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
<span data-ttu-id="6988f-117">フィッシング攻撃から保護するために既定で Office 365 が構成される方法の詳細については、「Office 365 が差出人を検証する方法」を参照してください。[フィッシングを防ぐ方法に](how-office-365-validates-the-from-address.md)ついて説明します。</span><span class="sxs-lookup"><span data-stu-id="6988f-117">For more details about how Office 365 is configured by default to protect you from phishing attacks, see [How Office 365 validates the From: address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6988f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6988f-118">Related topics</span></span>

[<span data-ttu-id="6988f-119">Office 365 がフィッシング詐欺を防ぐために差出人アドレスを検証する方法</span><span class="sxs-lookup"><span data-stu-id="6988f-119">How Office 365 validates the From: address to prevent phishing</span></span>](how-office-365-validates-the-from-address.md)
  
[<span data-ttu-id="6988f-120">フィッシング詐欺やその他の形式のオンライン詐欺から保護する</span><span class="sxs-lookup"><span data-stu-id="6988f-120">Protect yourself from phishing schemes and other forms of online fraud</span></span>](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546)
  
[<span data-ttu-id="6988f-121">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6988f-121">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="6988f-122">Office 365 の ATP のフィッシング詐欺対策機能</span><span class="sxs-lookup"><span data-stu-id="6988f-122">ATP anti-phishing capabilities in Office 365</span></span>](atp-anti-phishing.md)
  

