---
title: Office 365 での動的配信とプレビュー、ATP の安全な添付ファイル
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: ATP の安全な添付ファイルのポリシーを設定する場合は、[動的配信] を選択してメッセージの遅延を回避し、スキャンされた添付ファイルをプレビューできるようにします。
ms.openlocfilehash: 203f5082701f1f3eeea36b385918328cb85deb81
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230651"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="6d298-103">Office 365 での動的配信とプレビュー、ATP の安全な添付ファイル</span><span class="sxs-lookup"><span data-stu-id="6d298-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

## <a name="overview"></a><span data-ttu-id="6d298-104">概要</span><span class="sxs-lookup"><span data-stu-id="6d298-104">Overview</span></span>

<span data-ttu-id="6d298-105">動的配信は、 [ATP の安全な添付ファイル](atp-safe-attachments.md)に対して選択可能なオプションです。</span><span class="sxs-lookup"><span data-stu-id="6d298-105">Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="6d298-106">この記事では、 [Office 365 の ATP の安全な添付ファイル](atp-safe-attachments.md)の動的配信および添付ファイルのプレビュー機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d298-106">Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="6d298-107">組織に対して[ATP の安全な添付ファイルポリシーが設定さ](set-up-atp-safe-attachments-policies.md)れている場合は、電子メールの添付ファイルの処理方法に関するいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="6d298-107">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled.</span></span> <span data-ttu-id="6d298-108">これには、**ブロック**、**置換**、および**動的配信**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d298-108">These include **Block**, **Replace**, and **Dynamic Delivery**.</span></span> <span data-ttu-id="6d298-109">ATP の安全な添付ファイルポリシーの構成によっては、電子メールの受信者が、添付ファイルがスキャンされている間、電子メール配信に多少の遅延が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6d298-109">Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned.</span></span> <span data-ttu-id="6d298-110">メッセージの遅延を回避するには、[**動的配信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d298-110">To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="6d298-111">動的配信のしくみ</span><span class="sxs-lookup"><span data-stu-id="6d298-111">How Dynamic Delivery works</span></span>
  
<span data-ttu-id="6d298-112">動的配信では、電子メールの添付ファイルごとにプレースホルダーを使用して電子メールメッセージの本文を受信者に送信することによって、メールの遅延を排除します。</span><span class="sxs-lookup"><span data-stu-id="6d298-112">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment.</span></span> <span data-ttu-id="6d298-113">添付ファイルのコピーがスキャンされ、 [ATP の安全な添付ファイル](atp-safe-attachments.md)によって安全であると判断されるまで、プレースホルダーは残ります。</span><span class="sxs-lookup"><span data-stu-id="6d298-113">The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span> 

- <span data-ttu-id="6d298-114">各添付ファイルが削除されると、その添付ファイルを開いたりダウンロードしたりできます。</span><span class="sxs-lookup"><span data-stu-id="6d298-114">As each attachment is cleared, it is available to open or download.</span></span> 

- <span data-ttu-id="6d298-115">添付ファイルが悪意のあるものと判断された場合は、検疫に送信されます。これにより、組織のセキュリティチーム (Office 365 のグローバル管理者やセキュリティ管理者など) が[office 365 の検疫済みメッセージを管理](manage-quarantined-messages-and-files.md)できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6d298-115">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="6d298-116">ほとんどの Pdf および Office ドキュメントは、ATP のスキャンが進行している間、セーフモードでプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="6d298-116">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway.</span></span> <span data-ttu-id="6d298-117">添付ファイルが動的配信プレビューアーに対応していない場合、電子メールの受信者には、ATP の安全な添付ファイルのスキャンが完了するまで、添付ファイルプレースホルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d298-117">If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="6d298-118">モバイルデバイスを使用していて、初めて動的配信プレビューで Pdf が表示されない場合は、モバイルブラウザーを使用して Office 365 にサインインしてください。</span><span class="sxs-lookup"><span data-stu-id="6d298-118">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing into Office 365 using your mobile browser.</span></span>

<span data-ttu-id="6d298-119">動的配信を使用すると、ユーザーはすぐに電子メールメッセージの読み取りと応答を行うことができますが、添付ファイルは分析されます。</span><span class="sxs-lookup"><span data-stu-id="6d298-119">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span> 

<span data-ttu-id="6d298-120">ATP の安全な添付ファイルのスキャンは、Office 365 データが存在する地域と同じ地域で行われます。</span><span class="sxs-lookup"><span data-stu-id="6d298-120">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides.</span></span> <span data-ttu-id="6d298-121">データセンター地理の詳細については、「[データの保存場所](https://products.office.com/where-is-your-data-located?geo=All)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d298-121">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="6d298-122">添付ファイルを含む電子メールを他のユーザーが転送した場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="6d298-122">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="6d298-123">組織が[ATP の安全な添付ファイルポリシー](set-up-atp-safe-attachments-policies.md)の動的配信を使用していて、誰かが添付ファイルを含む電子メールを受信したとします。</span><span class="sxs-lookup"><span data-stu-id="6d298-123">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment.</span></span> <span data-ttu-id="6d298-124">そのユーザーが電子メールメッセージを他のユーザーに転送したとします。</span><span class="sxs-lookup"><span data-stu-id="6d298-124">Now suppose that person forwards the email message to someone else.</span></span> <span data-ttu-id="6d298-125">どうなりますか?</span><span class="sxs-lookup"><span data-stu-id="6d298-125">What happens?</span></span> <span data-ttu-id="6d298-126">これは、追加の受信者が ATP の安全な添付ファイルポリシーに含まれているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6d298-126">It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="6d298-127">[動的配信] オプションを使用して、受信者が ATP の安全な添付ファイルポリシーでカバーされている場合、受信者には、互換性のあるファイルをプレビューできるプレースホルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d298-127">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="6d298-128">受信者が ATP の安全な添付ファイルポリシーでカバーされていない場合、電子メールと添付ファイルは、ATP の安全な添付ファイルのスキャンまたは添付ファイルのプレースホルダーを使用せずに実行されます。</span><span class="sxs-lookup"><span data-stu-id="6d298-128">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without any ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="6d298-129">動的配信が機能するために必要なこと</span><span class="sxs-lookup"><span data-stu-id="6d298-129">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="6d298-130">組織が[Office 365 Advanced Threat Protection](office-365-atp.md)を持っている必要がある</span><span class="sxs-lookup"><span data-stu-id="6d298-130">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="6d298-131">[動的配信] オプションを使用して、ATP の安全な添付ファイルに関するポリシーを定義する必要があります (「 [Office 365 の atp の安全な添付ファイルポリシーの設定](set-up-atp-safe-attachments-policies.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="6d298-131">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="6d298-132">組織の電子メールは、Office 365 でホストされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d298-132">Your organization's email must be hosted in Office 365.</span></span> <span data-ttu-id="6d298-133">[どの SMTP メール転送エージェント (Exchange Server など) でも Office 365 Advanced Threat Protection を使用でき](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp)ますが、ATP の安全な添付ファイルの動的配信オプションでは、組織の電子メールが Office 365 でホストされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d298-133">Although [Office 365 Advanced Threat Protection can be used with any SMTP mail transfer agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (such as Exchange Server), the Dynamic Delivery option for ATP Safe Attachments requires that your organization's email be hosted in Office 365.</span></span> <span data-ttu-id="6d298-134">メールが Office 365 でホストされていない場合は、[**ブロック**] などの別の[ATP の安全な添付ファイルポリシーオプション](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options)を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d298-134">If your email is not hosted in Office 365, choose a different [ATP Safe Attachments policy option](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), such as **Block**.</span></span>
    
## <a name="additional-considerations"></a><span data-ttu-id="6d298-135">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="6d298-135">Additional considerations</span></span>

<span data-ttu-id="6d298-136">動的配信はサポートされていない特定のシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="6d298-136">There are certain scenarios in which Dynamic Delivery is not supported.</span></span> <span data-ttu-id="6d298-137">これらには次のコマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="6d298-137">These include the following:</span></span>
  
- <span data-ttu-id="6d298-138">パブリックフォルダー内の電子メールメッセージ</span><span class="sxs-lookup"><span data-stu-id="6d298-138">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="6d298-139">カスタムルールを使用して、ユーザーのメールボックスにルーティングされてから戻る電子メールメッセージ</span><span class="sxs-lookup"><span data-stu-id="6d298-139">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="6d298-140">ホストされたメールボックスと、アーカイブフォルダーなどの他の場所に移動した (自動または手動で) 電子メールメッセージ</span><span class="sxs-lookup"><span data-stu-id="6d298-140">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="6d298-141">削除された電子メールメッセージ</span><span class="sxs-lookup"><span data-stu-id="6d298-141">Email messages that are deleted</span></span>
    
- <span data-ttu-id="6d298-142">エラー状態にあるユーザーのメールボックス検索フォルダー</span><span class="sxs-lookup"><span data-stu-id="6d298-142">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="6d298-143">Exchange Online 管理者が Exclaimer を有効にしている環境。</span><span class="sxs-lookup"><span data-stu-id="6d298-143">Environments in which an Exchange Online admin has enabled Exclaimer.</span></span> <span data-ttu-id="6d298-144">この解決方法については、「 [ATP Dynamic Delivery And Exclaimer の使用時に添付ファイル付きメッセージが配信されない](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d298-144">To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span></span>

- <span data-ttu-id="6d298-145">[セキュリティで保護された、または汎用インターネットメール内線 (S/MIME)](s-mime-for-message-signing-and-encryption.md)で暗号化されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="6d298-145">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span></span>

- <span data-ttu-id="6d298-146">動的配信がサポートされていない場合、ATP の安全な添付ファイルは電子メールメッセージをスキャンしません。</span><span class="sxs-lookup"><span data-stu-id="6d298-146">In cases where Dynamic Delivery is not supported, ATP Safe Attachments will not scan email messages.</span></span> <span data-ttu-id="6d298-147">ただし、 [ATP の安全なリンクポリシー](set-up-atp-safe-links-policies.md)がどのように構成されているかに応じて、url を含む添付ファイル付きの電子メールメッセージを配信することが確認されます。</span><span class="sxs-lookup"><span data-stu-id="6d298-147">However, delivering email messages with attachments that contain URLs will be checked, depending on how your [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured.</span></span> <span data-ttu-id="6d298-148">このような場合、電子メールメッセージと Office ファイルの Url がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="6d298-148">In these cases, URLs in email messages and Office files are checked.</span></span>
