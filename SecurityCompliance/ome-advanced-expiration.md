---
title: Office 365 で暗号化された電子メールの有効期限日を設定する高度なメッセージ暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: office 365 の高度なメッセージ暗号化機能が office 365 メッセージ暗号化 (OME) の上にあるため、電子メールのセキュリティを拡張するには、カスタムブランド化されたテンプレートを使用して、メールの有効期限を設定します。
ms.openlocfilehash: c1fb876724bed970095e950906500ff551d93cee
ms.sourcegitcommit: 8eb3cb4ec45ae0bb75fde249e35c4bc3d263b84f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2019
ms.locfileid: "33506726"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="1df76-103">Office 365 で暗号化された電子メールの有効期限日を設定する高度なメッセージ暗号化</span><span class="sxs-lookup"><span data-stu-id="1df76-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="1df76-104">office 365 の高度なメッセージの暗号化は、特定のサブスクリプションの office 365 メッセージの暗号化の上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1df76-104">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="1df76-105">高度なメッセージ暗号化は、 [Microsoft 365 Enterprise e5](https://www.microsoft.com/microsoft-365/enterprise/home)、office 365 Enterprise e5、および Office 365 エデュケーション A5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="1df76-105">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="1df76-106">office 365 advanced message encryption を含まない office 365 サブスクリプションが組織にある場合は、advanced コンプライアンス SKU の E5 コンプライアンスを使用して、高度なメッセージ暗号化をアドオンとして購入できます。</span><span class="sxs-lookup"><span data-stu-id="1df76-106">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="1df76-107">OME ポータルを使用して暗号化された電子メールにアクセスする外部の受信者に送信するユーザーが電子メールでメッセージの有効期限を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1df76-107">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="1df76-108">受信者が OME ポータルを使用して、組織によって送信される暗号化された電子メールを、Windows Powershell で有効期限を指定するカスタムブランド化テンプレートを使用して表示および返信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1df76-108">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="1df76-109">O365 グローバル管理者は、会社のブランドを適用して Office 365 組織の電子メールメッセージの外観をカスタマイズする場合、これらの電子メールメッセージの有効期限を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1df76-109">As an O365 global administrator, when you apply your company branding to customize the look of your Office 365 organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="1df76-110">Office 365 Advanced Message Encryption では、組織から送信される暗号化メール用に複数のテンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1df76-110">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="1df76-111">テンプレートを使用すると、受信者がユーザーによって送信されたメールにアクセスできる期間を制御できます。</span><span class="sxs-lookup"><span data-stu-id="1df76-111">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="1df76-112">エンドユーザーが有効期限が設定されたメールを受信すると、ユーザーにはラッパーの電子メールの有効期限が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1df76-112">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="1df76-113">ユーザーが期限切れメールを開こうとすると、OME ポータルにエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1df76-113">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="1df76-114">外部の受信者へのメールのみが expirable になります。</span><span class="sxs-lookup"><span data-stu-id="1df76-114">Only emails to external recipients are expirable.</span></span>

<span data-ttu-id="1df76-115">office 365 Advanced Message Encryption では、カスタムブランドを適用するたびに、office 365 は、テンプレートを適用するメールフロールールに適合するラッパーを電子メールに適用します。</span><span class="sxs-lookup"><span data-stu-id="1df76-115">With Office 365 Advanced Message Encryption, any time you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="1df76-116">また、有効期限は、カスタムブランド化が使用されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1df76-116">In addition, expiration can only be used if custom branding is used.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="1df76-117">PowerShell を使用してメールの有効期限を強制するカスタムブランド化テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="1df76-117">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="1df76-118">Office 365 テナント内のグローバル管理者のアクセス許可を持つアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="1df76-118">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="1df76-119">omeconfiguration 新しいコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1df76-119">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="1df76-120">詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1df76-120">Where:</span></span>

- <span data-ttu-id="1df76-121">Identity は、カスタムテンプレートの名前です。</span><span class="sxs-lookup"><span data-stu-id="1df76-121">Identity is the name of the custom template.</span></span>

- <span data-ttu-id="1df76-122">ExternalMailExpiryInDays は、受信者が期限切れになる前にメールを保持できる日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1df76-122">ExternalMailExpiryInDays identifies the number of days you want recipients to be able to keep mail before it expires.</span></span> <span data-ttu-id="1df76-123">1から730日までの任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1df76-123">You can use any value between 1 to 730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="1df76-124">Office 365 の詳細なメッセージの暗号化に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="1df76-124">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="1df76-125">Office 365 の高度なメッセージの暗号化</span><span class="sxs-lookup"><span data-stu-id="1df76-125">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="1df76-126">Office 365 で暗号化されたメールの取り消し高度なメッセージ暗号化</span><span class="sxs-lookup"><span data-stu-id="1df76-126">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="1df76-127">メッセージポリシーとコンプライアンスサービスの説明</span><span class="sxs-lookup"><span data-stu-id="1df76-127">Message policy and compliance service description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)