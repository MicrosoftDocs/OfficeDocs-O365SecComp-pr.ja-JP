---
title: Office 365 Advanced Message Encryption 機能を使って暗号化されたメールの有効期限を設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: Office 365 の高度なメッセージ暗号化機能が Office 365 メッセージ暗号化 (OME) の上にあるため、電子メールのセキュリティを拡張するには、カスタムブランド化されたテンプレートを使用して、メールの有効期限を設定します。
ms.openlocfilehash: 260e6032d3b7a4c9b81fca73dfbcd57fa01168cb
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157670"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="5f4a2-103">Office 365 Advanced Message Encryption 機能を使って暗号化されたメールの有効期限を設定する</span><span class="sxs-lookup"><span data-stu-id="5f4a2-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="5f4a2-104">Office 365 の高度なメッセージの暗号化は、特定のサブスクリプションの Office 365 メッセージの暗号化の上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-104">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="5f4a2-105">高度なメッセージ暗号化は、 [Microsoft 365 Enterprise e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 Enterprise e5、および Office 365 エデュケーション A5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-105">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="5f4a2-106">Office 365 Advanced Message Encryption を含まない Office 365 サブスクリプションが組織にある場合は、Advanced コンプライアンス SKU の E5 コンプライアンスを使用して、高度なメッセージ暗号化をアドオンとして購入できます。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-106">If your organization has an Office 365 subscription that doesn't include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="5f4a2-107">OME ポータルを使用して暗号化された電子メールにアクセスする外部の受信者に送信するユーザーが電子メールでメッセージの有効期限を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-107">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="5f4a2-108">受信者が OME ポータルを使用して、組織によって送信される暗号化された電子メールを、Windows Powershell で有効期限を指定するカスタムブランド化テンプレートを使用して表示および返信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-108">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="5f4a2-109">O365 グローバル管理者は、会社のブランドを適用して Office 365 組織の電子メールメッセージの外観をカスタマイズする場合、これらの電子メールメッセージの有効期限を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-109">As an O365 global administrator, when you apply your company brand to customize the look of your Office 365 organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="5f4a2-110">Office 365 Advanced Message Encryption を使用すると、組織から発信される暗号化された電子メール用に複数のテンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-110">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="5f4a2-111">テンプレートを使用すると、受信者がユーザーによって送信されたメールにアクセスできる期間を制御できます。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-111">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="5f4a2-112">エンドユーザーが有効期限が設定されたメールを受信すると、ユーザーにはラッパーの電子メールの有効期限が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-112">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="5f4a2-113">ユーザーが期限切れメールを開こうとすると、OME ポータルにエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-113">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="5f4a2-114">電子メールの有効期限は、外部の受信者にのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-114">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="5f4a2-115">Office 365 Advanced Message Encryption では、カスタムブランドを適用するたびに、Office 365 は、テンプレートを適用するメールフロールールに適合するラッパーを電子メールに適用します。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-115">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="5f4a2-116">また、カスタムブランド化を使用する場合にのみ、有効期限を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-116">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="5f4a2-117">PowerShell を使用してメールの有効期限を強制するカスタムブランド化テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="5f4a2-117">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="5f4a2-118">Office 365 組織のグローバル管理者のアクセス許可を持つアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-118">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your Office 365 organization.</span></span>

2. <span data-ttu-id="5f4a2-119">OMEConfiguration 新しいコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-119">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="5f4a2-120">詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-120">Where:</span></span>

- <span data-ttu-id="5f4a2-121">`Identity`は、カスタムテンプレートの名前です。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-121">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="5f4a2-122">`ExternalMailExpiryInDays`受信者が期限切れになる前にメールを保持できる日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-122">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="5f4a2-123">1から730日までの任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f4a2-123">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="5f4a2-124">Office 365 の詳細なメッセージの暗号化に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="5f4a2-124">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="5f4a2-125">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="5f4a2-125">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="5f4a2-126">Office 365 Advanced Message Encryption 機能を使って暗号化されたメールを無効にする</span><span class="sxs-lookup"><span data-stu-id="5f4a2-126">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="5f4a2-127">メッセージポリシーとコンプライアンスサービスの説明</span><span class="sxs-lookup"><span data-stu-id="5f4a2-127">Message policy and compliance service description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)