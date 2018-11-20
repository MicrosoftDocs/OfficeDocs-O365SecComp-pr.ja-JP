---
title: 動的な配信および Office 365 ATP の安全な添付ファイルをプレビューします。
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/08/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
description: ATP の安全な添付ファイル ポリシーを設定するときに、メッセージの遅延を回避し、スキャンされている添付ファイルをプレビューするのにはユーザーを有効にする動的な配信を選択します。
ms.openlocfilehash: a272253594dda7ea720bb1e8b59e38e870f2f036
ms.sourcegitcommit: 147768bbe44c8c98c02fa29ae9d882cee4ec2d6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238429"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="7811c-103">動的な配信および Office 365 ATP の安全な添付ファイルをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="7811c-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="7811c-p101">**概要**: 動的な配信は、 [ATP の安全な添付ファイル](atp-safe-attachments.md)を選択できるオプションです。動的な配信および[Office 365 の ATP の安全な添付ファイル](atp-safe-attachments.md)の添付ファイルのプレビュー機能の詳細については、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7811c-p101">**Summary**: Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md). Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="7811c-106">動的配信のしくみ</span><span class="sxs-lookup"><span data-stu-id="7811c-106">How Dynamic Delivery works</span></span>

<span data-ttu-id="7811c-p102">[ATP の安全な添付ファイル ポリシーの設定](set-up-atp-safe-attachments-policies.md)組織には電子メールの添付ファイルを処理する方法のいくつかのオプションがあります。**ブロック**、**交換**、および**動的な配信**が含まれます。ATP の安全な添付ファイル ポリシーの構成方法によって、添付ファイルをスキャン中に、電子メールの受信者によってマイナー電子メールの配信に遅延が発生することができます。メッセージの遅延を避けるためには、**動的な配信**を選択します。</span><span class="sxs-lookup"><span data-stu-id="7811c-p102">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled. These include **Block**, **Replace**, and **Dynamic Delivery**. Depending on how ATP Safe Attachments policies are configured, email recipients can experience a minor delay in email delivery while their attachments are scanned. To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
<span data-ttu-id="7811c-p103">動的配信では、各電子メールの添付ファイルのプレース ホルダーを持つ受信者に、電子メール メッセージの本文を送信することによりメールの遅延を排除します。プレース ホルダーは、添付ファイルのコピーがスキャンされ、 [ATP の安全な添付ファイル](atp-safe-attachments.md)が安全であると判断されるまで残ります。ほとんどの Pdf や Office が進行中で ATP のスキャン中に、セーフ モードでドキュメントをプレビューできます。添付ファイルに動的な配信プレビュー用のプログラムと互換性がない場合電子メールの受信者は、ATP の安全な添付ファイルのスキャンが完了するまでに、添付ファイルのプレース ホルダーが参照してください。</span><span class="sxs-lookup"><span data-stu-id="7811c-p103">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment. The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md). Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway. If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

- <span data-ttu-id="7811c-115">各添付ファイルをオフにすると、開くか、ダウンロードに使用可能です。</span><span class="sxs-lookup"><span data-stu-id="7811c-115">As each attachment is cleared, it is available to open or download.</span></span> 

- <span data-ttu-id="7811c-116">悪意のある添付ファイルが確認された場合、検疫に送信されます、 [Office 365 で検疫されたメッセージを管理する](manage-quarantined-messages-and-files.md)ことができます (Office 365 のグローバル管理者またはセキュリティ管理者の場合) などの組織のセキュリティ チームの他の場所。</span><span class="sxs-lookup"><span data-stu-id="7811c-116">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="7811c-117">動的な配信は、電子メールの受信者は、読み取りおよび応答の電子メール メッセージをすぐにその添付ファイルを分析していることを知ることです。</span><span class="sxs-lookup"><span data-stu-id="7811c-117">With Dynamic Delivery, email recipients can read and respond to their email messages right away, knowing that their attachments are being analyzed.</span></span> 

<span data-ttu-id="7811c-p104">スキャンでは、ATP 安全な添付ファイルを Office 365 のデータが格納されている同じ地域に配置します。データ センターの地理的条件の詳細についてを参照してください[にあるデータがあるか?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="7811c-p104">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides. For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="7811c-120">添付ファイルを含む電子メールを転送他のときの動作ですか。</span><span class="sxs-lookup"><span data-stu-id="7811c-120">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="7811c-p105">組織が、 [ATP の安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)の動的な配信を使用して添付ファイルを含む電子メールを受け取る他のユーザーとします。今すぐその人が他のユーザーに電子メール メッセージを転送しようとしていますがいると仮定します。どうなりますか。ATP の安全な添付ファイル ポリシーに追加の受信者が含まれているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7811c-p105">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment. Now suppose that person is about to forward the email message to someone else. What happens? It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="7811c-125">場合は受信者が動的な配信オプションを使用して、ATP の安全な添付ファイル ポリシーの対象でし、受信者が表示されるプレース ホルダーは、互換性のあるファイルをプレビューする機能を持つ。</span><span class="sxs-lookup"><span data-stu-id="7811c-125">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="7811c-126">場合は、受信者は、ATP の安全な添付ファイル ポリシーの影響を受けません、電子メールと添付ファイルは進み、ATP スキャン安全な添付ファイルや添付ファイルのプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="7811c-126">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="7811c-127">動作する動的な配信に必要となるものですか。</span><span class="sxs-lookup"><span data-stu-id="7811c-127">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="7811c-128">組織が[Office 365 の高度な脅威保護](office-365-atp.md)を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="7811c-128">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="7811c-129">ATP (を参照してください[Office 365 の ATP の安全な添付ファイル ポリシーの設定](set-up-atp-safe-attachments-policies.md)) の動的な配信オプションを使用して安全な添付ファイルのポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7811c-129">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="7811c-130">Office 365 で、組織の電子メールをホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7811c-130">Your organization's email must be hosted in Office 365</span></span>
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a><span data-ttu-id="7811c-131">動的な配信が利用可能ないないシナリオはありますか。</span><span class="sxs-lookup"><span data-stu-id="7811c-131">Are there scenarios for which Dynamic Delivery is not available?</span></span>

<span data-ttu-id="7811c-p106">動的な配信がサポートされていない特定のシナリオがあります。これらを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="7811c-p106">There are certain scenarios in which Dynamic Delivery is not supported. These include the following:</span></span>
  
- <span data-ttu-id="7811c-134">電子メール メッセージをパブリック フォルダーに含まれる</span><span class="sxs-lookup"><span data-stu-id="7811c-134">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="7811c-135">電子メールをルーティングし、カスタム規則を使用してユーザーのメールボックスには、</span><span class="sxs-lookup"><span data-stu-id="7811c-135">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="7811c-136">ホストされているメールボックスとアーカイブのフォルダーを含む、他の場所に (自動または手動で) 移動されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="7811c-136">Messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="7811c-137">削除されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="7811c-137">Messages that are deleted</span></span>
    
- <span data-ttu-id="7811c-138">エラー状態では、ユーザーのメールボックスの検索フォルダー</span><span class="sxs-lookup"><span data-stu-id="7811c-138">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="7811c-p107">Exclaimer Exchange Online 管理者が有効にする環境。( [ATP の動的な配信および Exclaimer を使用すると、添付ファイル付きのメッセージが配信されない](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)を参照してください)</span><span class="sxs-lookup"><span data-stu-id="7811c-p107">Environments in which an Exchange Online admin has enabled Exclaimer. (See [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery))</span></span>

- <span data-ttu-id="7811c-141">/Multipurpose をセキュリティで保護されたインターネット メール拡張 ([S/MIME](s-mime-for-message-signing-and-encryption.md)) で暗号化されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="7811c-141">Messages encrypted with Secure/Multipurpose Internet Mail Extensions ([S/MIME](s-mime-for-message-signing-and-encryption.md))</span></span>
    
