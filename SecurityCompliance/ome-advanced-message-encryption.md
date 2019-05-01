---
title: Office 365 の高度なメッセージの暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: office 365 の高度なメッセージ暗号化では、管理者が office 365 web ポータルを使用して暗号化された電子メールにアクセスを期限切れにし、取り消すことができるようになります。
ms.openlocfilehash: a775803a8d2678441f319c0145e96e7d19c26f7e
ms.sourcegitcommit: 8eb3cb4ec45ae0bb75fde249e35c4bc3d263b84f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2019
ms.locfileid: "33506727"
---
# <a name="office-365-advanced-message-encryption"></a><span data-ttu-id="26ae1-103">Office 365 の高度なメッセージの暗号化</span><span class="sxs-lookup"><span data-stu-id="26ae1-103">Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="26ae1-104">office 365 の高度なメッセージの暗号化は、特定のサブスクリプションの office 365 メッセージの暗号化の上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="26ae1-104">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="26ae1-105">高度なメッセージ暗号化は、 [Microsoft 365 Enterprise e5](https://www.microsoft.com/microsoft-365/enterprise/home)、office 365 Enterprise e5、および Office 365 エデュケーション A5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="26ae1-105">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="26ae1-106">office 365 advanced message encryption を含まない office 365 サブスクリプションが組織にある場合は、advanced コンプライアンス SKU の E5 コンプライアンスを使用して、高度なメッセージ暗号化をアドオンとして購入できます。</span><span class="sxs-lookup"><span data-stu-id="26ae1-106">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="26ae1-107">この記事は、 [Office 365 メッセージの暗号化](ome.md)についてのより大きな一連の記事の一部です。</span><span class="sxs-lookup"><span data-stu-id="26ae1-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="26ae1-108">Office 365 の高度なメッセージ暗号化を使用すると、お客様は、外部の受信者により柔軟な制御と暗号化された電子メールへのアクセスを必要とするコンプライアンス義務を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="26ae1-108">Advanced Message Encryption in Office 365 helps customers meet compliance obligations that require more flexible controls over external recipients and their access to encrypted emails.</span></span> <span data-ttu-id="26ae1-109">Office 365 の高度なメッセージ暗号化を使用すると、自動ポリシーにより、組織の外部で共有される機密メールを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="26ae1-109">With Advanced Message Encryption in Office 365, you can control sensitive emails shared outside the organization with automatic policies.</span></span> <span data-ttu-id="26ae1-110">これらのポリシーは、PII、財務、健康 id などの機密情報の種類を識別するために構成したり、保護を強化するためにキーワードを使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="26ae1-110">You configure these policies to identify sensitive information types such as PII, Financial, or Health IDs, or you can use keywords to enhance protection.</span></span> <span data-ttu-id="26ae1-111">ポリシーを構成したら、ポリシーをカスタムのブランド化された電子メールテンプレートとペアにして、ポリシーに適合するメールの追加の制御の有効期限を追加します。</span><span class="sxs-lookup"><span data-stu-id="26ae1-111">Once you've configured the policies, you pair policies with a custom branded email templates and then add an expiration date for additional control for emails that fit the policy.</span></span> <span data-ttu-id="26ae1-112">さらに、管理者は、いつでもメールへのアクセスを取り消すことにより、セキュリティで保護された web ポータルを介して外部からアクセスされる暗号化メールを制御できます。</span><span class="sxs-lookup"><span data-stu-id="26ae1-112">Additionally, admins can further control encrypted emails accessed externally through a secure web portal by revoking access to the mail at any time.</span></span>

<span data-ttu-id="26ae1-113">外部の受信者に送信されたメールの有効期限を設定し、取り消すことはできません。</span><span class="sxs-lookup"><span data-stu-id="26ae1-113">You can only set an expiration for and revoke emails  sent to external recipients.</span></span>

<span data-ttu-id="26ae1-114">office 365 Advanced Message Encryption では、カスタムブランドを適用するたびに、office 365 は、テンプレートを適用するメールフロールールに適合するラッパーを電子メールに適用します。</span><span class="sxs-lookup"><span data-stu-id="26ae1-114">With Office 365 Advanced Message Encryption, any time you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="26ae1-115">また、有効期限は、カスタムブランド化が使用されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="26ae1-115">In addition, expiration can only be used if custom branding is used.</span></span> <span data-ttu-id="26ae1-116">取り消すことができるのは、ポータル経由で受信したメッセージのみです。</span><span class="sxs-lookup"><span data-stu-id="26ae1-116">You can only revoke messages that are received through the portal.</span></span>

## <a name="get-started-with-office-365-advanced-message-encryption"></a><span data-ttu-id="26ae1-117">Office 365 Advanced Message Encryption の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="26ae1-117">Get started with Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="26ae1-118">次のトピックでは、高度なメッセージ暗号化の設定方法と使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="26ae1-118">The following topics describe how you set up and use Advanced Message Encryption.</span></span>

<span data-ttu-id="26ae1-119">組織には、Office 365 Advanced Message Encryption を含むサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="26ae1-119">Your organization must have a subscription that includes Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="26ae1-120">サポートされているサブスクリプションの詳細については、「[メッセージポリシーとコンプライアンスサービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26ae1-120">For detailed information about supported subscriptions, see the [Message policy and compliance service description](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

<span data-ttu-id="26ae1-121">高度なメッセージ暗号化機能を活用するように設定されていない場合は、新しい Office 365 メッセージ暗号化機能をセットアップします。これにより、外部で共有される暗号化されたメッセージの上位に保護が追加されます。</span><span class="sxs-lookup"><span data-stu-id="26ae1-121">Set up the new Office 365 Message Encryption capabilities if they are not already set up to leverage Advanced Message Encryption capabilities which provide added protection on top of encrypted messages shared externally.</span></span> <span data-ttu-id="26ae1-122">office 365 メッセージの暗号化がセットアップされていない場合は、「 [office を新しい office 365 メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26ae1-122">If you do not have Office 365 Message Encryption set up, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>

<span data-ttu-id="26ae1-123">[Office 365 Advanced Message Encryption で暗号化された電子メールの有効期限日を設定](ome-advanced-expiration.md)します。</span><span class="sxs-lookup"><span data-stu-id="26ae1-123">[Set an expiration date for email encrypted by Office 365 Advanced Message Encryption](ome-advanced-expiration.md).</span></span> <span data-ttu-id="26ae1-124">セキュリティで保護された web ポータルから暗号化された電子メールへのアクセスを期限切れにすることによって保護を強化する自動ポリシーを使用して、組織外で共有する機密メールを制御</span><span class="sxs-lookup"><span data-stu-id="26ae1-124">Control sensitive emails shared outside the organization with automatic policies that enhance protection by expiring access through a secure web portal to encrypted emails.</span></span>

<span data-ttu-id="26ae1-125">[Office 365 の高度なメッセージ暗号化によって暗号化された電子メールを取り消し](revoke-ome-encrypted-mail.md)ます。</span><span class="sxs-lookup"><span data-stu-id="26ae1-125">[Revoke email encrypted by Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md).</span></span> <span data-ttu-id="26ae1-126">セキュリティで保護された web ポータルから暗号化された電子メールへのアクセスを取り消すことにより、組織の外部で共有される機密メールを制御し、保護を強化します。</span><span class="sxs-lookup"><span data-stu-id="26ae1-126">Control sensitive emails shared outside the organization and enhance protection by revoking access through a secure web portal to encrypted emails.</span></span>  