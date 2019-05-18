---
title: Office 365 Advanced Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Office 365 の高度なメッセージ暗号化では、管理者が Office 365 web ポータルを使用して暗号化された電子メールにアクセスを期限切れにし、取り消すことができるようになります。
ms.openlocfilehash: dcef5f861711acffb8359063373cd90d4b122d88
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157651"
---
# <a name="office-365-advanced-message-encryption"></a><span data-ttu-id="cc81a-103">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="cc81a-103">Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="cc81a-104">Office 365 の高度なメッセージの暗号化は、特定のサブスクリプションの Office 365 メッセージの暗号化の上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc81a-104">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="cc81a-105">高度なメッセージ暗号化は、 [Microsoft 365 Enterprise e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 Enterprise e5、および Office 365 エデュケーション A5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc81a-105">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="cc81a-106">Office 365 Advanced Message Encryption を含まない Office 365 サブスクリプションが組織にある場合は、Advanced コンプライアンス SKU の E5 コンプライアンスを使用して、高度なメッセージ暗号化をアドオンとして購入できます。</span><span class="sxs-lookup"><span data-stu-id="cc81a-106">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="cc81a-107">Office 365 の高度なメッセージ暗号化を使用すると、お客様は、外部の受信者により柔軟な制御と暗号化された電子メールへのアクセスを必要とするコンプライアンス義務を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="cc81a-107">Advanced Message Encryption in Office 365 helps customers meet compliance obligations that require more flexible controls over external recipients and their access to encrypted emails.</span></span> <span data-ttu-id="cc81a-108">Office 365 の高度なメッセージ暗号化を使用すると、自動ポリシーにより、組織の外部で共有される機密メールを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="cc81a-108">With Advanced Message Encryption in Office 365, you can control sensitive emails shared outside the organization with automatic policies.</span></span> <span data-ttu-id="cc81a-109">これらのポリシーは、PII、財務、健康 Id などの機密情報の種類を識別するために構成したり、保護を強化するためにキーワードを使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="cc81a-109">You configure these policies to identify sensitive information types such as PII, Financial, or Health IDs, or you can use keywords to enhance protection.</span></span> <span data-ttu-id="cc81a-110">ポリシーを構成したら、ポリシーをカスタムのブランド化された電子メールテンプレートとペアにして、ポリシーに適合する電子メールの追加の制御の有効期限を追加します。</span><span class="sxs-lookup"><span data-stu-id="cc81a-110">Once you've configured the policies, you pair policies with custom branded email templates and then add an expiration date for extra control of emails that fit the policy.</span></span> <span data-ttu-id="cc81a-111">また、管理者は、メールへのアクセスをいつでも取り消すことにより、セキュリティで保護された web ポータルを介して外部からアクセスされる暗号化メールを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="cc81a-111">Also, admins can further control encrypted emails accessed externally through a secure web portal by revoking access to the mail at any time.</span></span>

<span data-ttu-id="cc81a-112">外部の受信者に送信される電子メールの有効期限は、失効日と設定のみを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cc81a-112">You can only revoke and set an expiration date for emails sent to external recipients.</span></span>

<span data-ttu-id="cc81a-113">Office 365 の高度なメッセージ暗号化では、カスタムブランド設定テンプレートを適用するたびに、Office 365 は、テンプレートを適用するメールフロールールに適合するラッパーを電子メールに適用します。</span><span class="sxs-lookup"><span data-stu-id="cc81a-113">With Office 365 Advanced Message Encryption, anytime you apply a custom branding template, Office 365 applies a wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="cc81a-114">メッセージを失効させることができます。また、ユーザーがポータル経由で受信するメッセージに有効期限日を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="cc81a-114">You can only revoke messages and apply expiration dates to messages that users receive through the portal.</span></span> <span data-ttu-id="cc81a-115">つまり、カスタムブランド化テンプレートが適用されている電子メール。</span><span class="sxs-lookup"><span data-stu-id="cc81a-115">In other words, email that has a custom branding template applied.</span></span>

## <a name="get-started-with-office-365-advanced-message-encryption"></a><span data-ttu-id="cc81a-116">Office 365 Advanced Message Encryption の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="cc81a-116">Get started with Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="cc81a-117">次のトピックでは、高度なメッセージ暗号化の設定方法と使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc81a-117">The following topics describe how you set up and use Advanced Message Encryption.</span></span>

<span data-ttu-id="cc81a-118">組織には、Office 365 Advanced Message Encryption を含むサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="cc81a-118">Your organization must have a subscription that includes Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="cc81a-119">サポートされているサブスクリプションの詳細については、「[メッセージポリシーとコンプライアンスサービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc81a-119">For detailed information about supported subscriptions, see the [Message policy and compliance service description](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

<span data-ttu-id="cc81a-120">Office 365 メッセージの暗号化が既にセットアップされていない場合は、「365 office の新しいメッセージの暗号化機能をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc81a-120">If you do not have Office 365 Message Encryption set up already, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>

<span data-ttu-id="cc81a-121">[Office 365 Advanced Message Encryption で暗号化された電子メールの有効期限日を設定](ome-advanced-expiration.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc81a-121">[Set an expiration date for email encrypted by Office 365 Advanced Message Encryption](ome-advanced-expiration.md).</span></span> <span data-ttu-id="cc81a-122">セキュリティで保護された web ポータルから暗号化された電子メールへのアクセスを期限切れにすることによって保護を強化する自動ポリシーを使用して、組織外で共有する機密メールを制御</span><span class="sxs-lookup"><span data-stu-id="cc81a-122">Control sensitive emails shared outside the organization with automatic policies that enhance protection by expiring access through a secure web portal to encrypted emails.</span></span>

<span data-ttu-id="cc81a-123">[Office 365 の高度なメッセージ暗号化によって暗号化された電子メールを取り消し](revoke-ome-encrypted-mail.md)ます。</span><span class="sxs-lookup"><span data-stu-id="cc81a-123">[Revoke email encrypted by Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md).</span></span> <span data-ttu-id="cc81a-124">セキュリティで保護された web ポータルから暗号化された電子メールへのアクセスを取り消すことにより、組織の外部で共有される機密メールを制御し、保護を強化します。</span><span class="sxs-lookup"><span data-stu-id="cc81a-124">Control sensitive emails shared outside the organization and enhance protection by revoking access through a secure web portal to encrypted emails.</span></span>  