---
title: Office 365 での動的配信とプレビュー、ATP の安全な添付ファイル
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
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
ms.openlocfilehash: 1fb221d28a4089db8a4278903107c610d6825f5e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218397"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="3a27e-103">Office 365 での動的配信とプレビュー、ATP の安全な添付ファイル</span><span class="sxs-lookup"><span data-stu-id="3a27e-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="3a27e-p101">**概要**: 動的配信は、 [ATP の安全な添付ファイル](atp-safe-attachments.md)に対して選択可能なオプションです。この記事では、 [Office 365 の ATP の安全な添付ファイル](atp-safe-attachments.md)の動的配信および添付ファイルのプレビュー機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a27e-p101">**Summary**: Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md). Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="3a27e-p102">組織に対して[ATP の安全な添付ファイルポリシーが設定さ](set-up-atp-safe-attachments-policies.md)れている場合は、電子メールの添付ファイルの処理方法に関するいくつかのオプションがあります。これには、**ブロック**、**置換**、および**動的配信**が含まれます。ATP の安全な添付ファイルポリシーの構成によっては、電子メールの受信者が、添付ファイルがスキャンされている間、電子メール配信に多少の遅延が発生する可能性があります。メッセージの遅延を回避するには、[**動的配信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a27e-p102">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled. These include **Block**, **Replace**, and **Dynamic Delivery**. Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned. To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="3a27e-110">動的配信のしくみ</span><span class="sxs-lookup"><span data-stu-id="3a27e-110">How Dynamic Delivery works</span></span>
  
<span data-ttu-id="3a27e-p103">動的配信では、電子メールの添付ファイルごとにプレースホルダーを使用して電子メールメッセージの本文を受信者に送信することによって、メールの遅延を排除します。添付ファイルのコピーがスキャンされ、 [ATP の安全な添付ファイル](atp-safe-attachments.md)によって安全であると判断されるまで、プレースホルダーは残ります。</span><span class="sxs-lookup"><span data-stu-id="3a27e-p103">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment. The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span> 

- <span data-ttu-id="3a27e-113">各添付ファイルが削除されると、その添付ファイルを開いたりダウンロードしたりできます。</span><span class="sxs-lookup"><span data-stu-id="3a27e-113">As each attachment is cleared, it is available to open or download.</span></span> 

- <span data-ttu-id="3a27e-114">添付ファイルが悪意のあるものと判断された場合は、検疫に送信されます。これにより、組織のセキュリティチーム (office 365 のグローバル管理者やセキュリティ管理者など) が[office 365 の検疫済みメッセージを管理](manage-quarantined-messages-and-files.md)できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3a27e-114">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="3a27e-p104">ほとんどの pdf および Office ドキュメントは、ATP のスキャンが進行している間、セーフモードでプレビューできます。添付ファイルが動的配信プレビューアーに対応していない場合、電子メールの受信者には、ATP の安全な添付ファイルのスキャンが完了するまで、添付ファイルプレースホルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a27e-p104">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway. If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="3a27e-117">モバイルデバイスを使用していて、初めて動的配信プレビューで pdf が表示されない場合は、モバイルブラウザーを使用して Office 365 にサインインしてください。</span><span class="sxs-lookup"><span data-stu-id="3a27e-117">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing into Office 365 using your mobile browser.</span></span>

<span data-ttu-id="3a27e-118">動的配信を使用すると、ユーザーはすぐに電子メールメッセージの読み取りと応答を行うことができますが、添付ファイルは分析されます。</span><span class="sxs-lookup"><span data-stu-id="3a27e-118">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span> 

<span data-ttu-id="3a27e-p105">ATP の安全な添付ファイルのスキャンは、Office 365 データが存在する地域と同じ地域で行われます。データセンター地理の詳細については、「[データの保存場所](https://products.office.com/where-is-your-data-located?geo=All)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a27e-p105">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides. For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="3a27e-121">添付ファイルを含む電子メールを他のユーザーが転送した場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="3a27e-121">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="3a27e-p106">組織が[ATP の安全な添付ファイルポリシー](set-up-atp-safe-attachments-policies.md)の動的配信を使用していて、誰かが添付ファイルを含む電子メールを受信したとします。そのユーザーが電子メールメッセージを他のユーザーに転送したとします。どうなりますか?これは、追加の受信者が ATP の安全な添付ファイルポリシーに含まれているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3a27e-p106">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment. Now suppose that person forwards the email message to someone else. What happens? It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="3a27e-126">[動的配信] オプションを使用して、受信者が ATP の安全な添付ファイルポリシーでカバーされている場合、受信者には、互換性のあるファイルをプレビューできるプレースホルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a27e-126">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="3a27e-127">受信者が atp の安全な添付ファイルポリシーでカバーされていない場合、電子メールと添付ファイルは、atp の安全な添付ファイルのスキャンまたは添付ファイルのプレースホルダーを使用せずに実行されます。</span><span class="sxs-lookup"><span data-stu-id="3a27e-127">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="3a27e-128">動的配信が機能するために必要なこと</span><span class="sxs-lookup"><span data-stu-id="3a27e-128">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="3a27e-129">組織が[Office 365 Advanced Threat Protection](office-365-atp.md)を持っている必要がある</span><span class="sxs-lookup"><span data-stu-id="3a27e-129">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="3a27e-130">[動的配信] オプションを使用して、atp の安全な添付ファイルに関するポリシーを定義する必要があります (「 [Office 365 の atp の安全な添付ファイルポリシーの設定](set-up-atp-safe-attachments-policies.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="3a27e-130">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="3a27e-131">組織のメールは Office 365 でホストされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a27e-131">Your organization's email must be hosted in Office 365</span></span>
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a><span data-ttu-id="3a27e-132">動的配信を使用できないシナリオはありますか?</span><span class="sxs-lookup"><span data-stu-id="3a27e-132">Are there scenarios for which Dynamic Delivery is not available?</span></span>

<span data-ttu-id="3a27e-p107">動的配信はサポートされていない特定のシナリオがあります。これらには次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="3a27e-p107">There are certain scenarios in which Dynamic Delivery is not supported. These include the following:</span></span>
  
- <span data-ttu-id="3a27e-135">パブリックフォルダー内の電子メールメッセージ</span><span class="sxs-lookup"><span data-stu-id="3a27e-135">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="3a27e-136">カスタムルールを使用して、ユーザーのメールボックスにルーティングされてから戻る電子メールメッセージ</span><span class="sxs-lookup"><span data-stu-id="3a27e-136">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="3a27e-137">ホストされたメールボックスと、アーカイブフォルダーなどの他の場所に移動した (自動または手動で) 電子メールメッセージ</span><span class="sxs-lookup"><span data-stu-id="3a27e-137">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="3a27e-138">削除された電子メールメッセージ</span><span class="sxs-lookup"><span data-stu-id="3a27e-138">Email messages that are deleted</span></span>
    
- <span data-ttu-id="3a27e-139">エラー状態にあるユーザーのメールボックス検索フォルダー</span><span class="sxs-lookup"><span data-stu-id="3a27e-139">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="3a27e-p108">Exchange Online 管理者が exclaimer を有効にしている環境。この解決方法については、「 [ATP Dynamic Delivery and exclaimer の使用時に添付ファイル付きメッセージが配信されない](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a27e-p108">Environments in which an Exchange Online admin has enabled Exclaimer. To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span></span>

- <span data-ttu-id="3a27e-142">[セキュリティで保護された、または汎用インターネットメール内線 (S/MIME)](s-mime-for-message-signing-and-encryption.md)で暗号化されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="3a27e-142">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span></span>

