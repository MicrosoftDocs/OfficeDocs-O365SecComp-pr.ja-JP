---
title: 動的な配信および Office 365 ATP の安全な添付ファイルをプレビューします。
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: ATP の安全な添付ファイル ポリシーを設定するときに、メッセージの遅延を回避し、スキャンされている添付ファイルをプレビューするのにはユーザーを有効にする動的な配信を選択します。
ms.openlocfilehash: ae027986cf5114bd024c679a59975d1e4be52d32
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995148"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="03e80-103">動的な配信および Office 365 ATP の安全な添付ファイルをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="03e80-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="03e80-p101">**概要**: 動的な配信は、 [ATP の安全な添付ファイル](atp-safe-attachments.md)を選択できるオプションです。動的な配信および[Office 365 の ATP の安全な添付ファイル](atp-safe-attachments.md)の添付ファイルのプレビュー機能の詳細については、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03e80-p101">**Summary**: Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md). Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="03e80-p102">[ATP の安全な添付ファイル ポリシーの設定](set-up-atp-safe-attachments-policies.md)組織には電子メールの添付ファイルを処理する方法のいくつかのオプションがあります。**ブロック**、**交換**、および**動的な配信**が含まれます。ATP の安全な添付ファイル ポリシーの構成方法によって、添付ファイルをスキャン中に、電子メールの受信者によってマイナー電子メールの配信に遅延が発生する可能性があります。メッセージの遅延を避けるためには、**動的な配信**を選択します。</span><span class="sxs-lookup"><span data-stu-id="03e80-p102">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled. These include **Block**, **Replace**, and **Dynamic Delivery**. Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned. To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="03e80-110">動的配信のしくみ</span><span class="sxs-lookup"><span data-stu-id="03e80-110">How Dynamic Delivery works</span></span>
  
<span data-ttu-id="03e80-p103">動的配信では、各電子メールの添付ファイルのプレース ホルダーを持つ受信者に、電子メール メッセージの本文を送信することによりメールの遅延を排除します。プレース ホルダーは、添付ファイルのコピーがスキャンされ、 [ATP の安全な添付ファイル](atp-safe-attachments.md)が安全であると判断されるまで残ります。</span><span class="sxs-lookup"><span data-stu-id="03e80-p103">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment. The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span> 

- <span data-ttu-id="03e80-113">各添付ファイルをオフにすると、開くか、ダウンロードに使用可能です。</span><span class="sxs-lookup"><span data-stu-id="03e80-113">As each attachment is cleared, it is available to open or download.</span></span> 

- <span data-ttu-id="03e80-114">悪意のある添付ファイルが確認された場合、検疫に送信されます、 [Office 365 で検疫されたメッセージを管理する](manage-quarantined-messages-and-files.md)ことができます (Office 365 のグローバル管理者またはセキュリティ管理者の場合) などの組織のセキュリティ チームの他の場所。</span><span class="sxs-lookup"><span data-stu-id="03e80-114">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="03e80-p104">ほとんどの Pdf や Office が進行中で ATP のスキャン中に、セーフ モードでドキュメントをプレビューできます。添付ファイルに動的な配信プレビュー用のプログラムと互換性がない場合電子メールの受信者は、ATP の安全な添付ファイルのスキャンが完了するまでに、添付ファイルのプレース ホルダーが参照してください。</span><span class="sxs-lookup"><span data-stu-id="03e80-p104">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway. If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="03e80-117">モバイル デバイスを使用している場合は、最初の動的な配信プレビューアーで Pdf が動作しない、モバイル ブラウザーを使用して Office 365 にサインインしてみてください。</span><span class="sxs-lookup"><span data-stu-id="03e80-117">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing into Office 365 using your mobile browser.</span></span>

<span data-ttu-id="03e80-118">動的配信では、読み取り、および、添付ファイルを分析しているときに、電子メール メッセージにすぐに応答します。</span><span class="sxs-lookup"><span data-stu-id="03e80-118">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span> 

<span data-ttu-id="03e80-p105">スキャンでは、ATP 安全な添付ファイルを Office 365 のデータが格納されている同じ地域に配置します。データ センターの地理的条件の詳細についてを参照してください[にあるデータがあるか?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="03e80-p105">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides. For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="03e80-121">添付ファイルを含む電子メールを転送他のときの動作ですか。</span><span class="sxs-lookup"><span data-stu-id="03e80-121">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="03e80-p106">組織が、 [ATP の安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)の動的な配信を使用して添付ファイルを含む電子メールを受け取る他のユーザーとします。今すぐその人が他のユーザーに電子メール メッセージを転送します。どうなりますか。ATP の安全な添付ファイル ポリシーに追加の受信者が含まれているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="03e80-p106">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment. Now suppose that person forwards the email message to someone else. What happens? It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="03e80-126">場合は受信者が動的な配信オプションを使用して、ATP の安全な添付ファイル ポリシーの対象でし、受信者が表示されるプレース ホルダーは、互換性のあるファイルをプレビューする機能を持つ。</span><span class="sxs-lookup"><span data-stu-id="03e80-126">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="03e80-127">場合は、受信者は、ATP の安全な添付ファイル ポリシーの影響を受けません、電子メールと添付ファイルは進み、ATP スキャン安全な添付ファイルや添付ファイルのプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="03e80-127">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="03e80-128">動作する動的な配信に必要となるものですか。</span><span class="sxs-lookup"><span data-stu-id="03e80-128">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="03e80-129">組織が[Office 365 の高度な脅威保護](office-365-atp.md)を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e80-129">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="03e80-130">ATP (を参照してください[Office 365 の ATP の安全な添付ファイル ポリシーの設定](set-up-atp-safe-attachments-policies.md)) の動的な配信オプションを使用して安全な添付ファイルのポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e80-130">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="03e80-131">Office 365 で、組織の電子メールをホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e80-131">Your organization's email must be hosted in Office 365</span></span>
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a><span data-ttu-id="03e80-132">動的な配信が利用可能ないないシナリオはありますか。</span><span class="sxs-lookup"><span data-stu-id="03e80-132">Are there scenarios for which Dynamic Delivery is not available?</span></span>

<span data-ttu-id="03e80-p107">動的な配信がサポートされていない特定のシナリオがあります。これらを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="03e80-p107">There are certain scenarios in which Dynamic Delivery is not supported. These include the following:</span></span>
  
- <span data-ttu-id="03e80-135">電子メール メッセージをパブリック フォルダーに含まれる</span><span class="sxs-lookup"><span data-stu-id="03e80-135">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="03e80-136">電子メールをルーティングし、カスタム規則を使用してユーザーのメールボックスには、</span><span class="sxs-lookup"><span data-stu-id="03e80-136">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="03e80-137">電子メール メッセージは、(自動または手動) をホストされているメールボックスとアーカイブのフォルダーを含む、他の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="03e80-137">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="03e80-138">電子メール メッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="03e80-138">Email messages that are deleted</span></span>
    
- <span data-ttu-id="03e80-139">エラー状態では、ユーザーのメールボックスの検索フォルダー</span><span class="sxs-lookup"><span data-stu-id="03e80-139">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="03e80-p108">Exclaimer Exchange Online 管理者が有効にする環境。この問題を解決するには、 [ATP の動的な配信および Exclaimer を使用すると、添付ファイル付きのメッセージが配信されない](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)を参照してください.</span><span class="sxs-lookup"><span data-stu-id="03e80-p108">Environments in which an Exchange Online admin has enabled Exclaimer. To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span></span>

- <span data-ttu-id="03e80-142">[/Multipurpose をセキュリティで保護されたインターネット メール拡張 (S/MIME)](s-mime-for-message-signing-and-encryption.md)で暗号化されたメッセージ)</span><span class="sxs-lookup"><span data-stu-id="03e80-142">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span></span>

