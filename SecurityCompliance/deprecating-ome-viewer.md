---
title: 廃止 Office 365 Message Encryption Viewer アプリ
ms.author: krowley
author: kccross
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
description: 2018年8月15日には、Office 365 Message Encryption (OME) Viewer モバイルアプリを Android および Apple ストアから削除します。 以前のバージョンの OME で Apple と Android の電話機で暗号化された電子メールメッセージと添付ファイルを読み取るには、Office 365 Message Encryption Viewer モバイルアプリが必要でした。 OME Viewer アプリの削除とは別に、以前のバージョンの OME には他の変更は加えていません。
ms.openlocfilehash: 82f28249e6b9911faea866f5a3574b635e45156c
ms.sourcegitcommit: d3e3ce391130f209f4d63c2528e1da8342cd732f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901935"
---
# <a name="deprecating-office-365-message-encryption-viewer-app"></a><span data-ttu-id="f73f2-105">廃止 Office 365 Message Encryption Viewer アプリ</span><span class="sxs-lookup"><span data-stu-id="f73f2-105">Deprecating Office 365 Message Encryption Viewer App</span></span>

<span data-ttu-id="f73f2-106">2018年8月15日に、Office 365 Message Encryption (OME) Viewer モバイルアプリが Android および Apple ストアから削除されました。</span><span class="sxs-lookup"><span data-stu-id="f73f2-106">On August 15, 2018, we removed the Office 365 Message Encryption (OME) Viewer mobile app from Android and Apple stores.</span></span> <span data-ttu-id="f73f2-107">以前のバージョンの OME で Apple と Android の電話機で暗号化された電子メールメッセージと添付ファイルを読み取るには、Office 365 Message Encryption Viewer モバイルアプリが必要でした。</span><span class="sxs-lookup"><span data-stu-id="f73f2-107">The Office 365 Message Encryption Viewer mobile app was required to read email messages and attachments that were encrypted with the previous version of OME on Apple and Android phones.</span></span> <span data-ttu-id="f73f2-108">OME Viewer アプリの削除とは別に、以前のバージョンの OME には他の変更は加えていません。</span><span class="sxs-lookup"><span data-stu-id="f73f2-108">Apart from removing the OME Viewer app, we are not making any other changes to the previous version of OME.</span></span>
  
## <a name="changes-from-august-2018"></a><span data-ttu-id="f73f2-109">2018年8月の変更</span><span class="sxs-lookup"><span data-stu-id="f73f2-109">Changes from August 2018</span></span>

<span data-ttu-id="f73f2-110">2017年9月に発表されたように、microsoft は新しいバージョンの[Office 365 Message Encryption](https://aka.ms/ome2017)をリリースしました。これにより、ユーザーは、暗号化されたメッセージと保護されたメッセージを、モバイルアプリの要件なしに、組織内外のユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="f73f2-110">As announced September 2017, we have released a new version of [Office 365 Message Encryption](https://aka.ms/ome2017) so that users can send encrypted and protected messages to anyone inside or outside the organization without the requirement of the mobile app.</span></span> <span data-ttu-id="f73f2-111">その後、追加機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="f73f2-111">Since then, we've added additional capabilities:</span></span>
  
- [<span data-ttu-id="f73f2-112">暗号化専用テンプレート</span><span class="sxs-lookup"><span data-stu-id="f73f2-112">Encrypt-only template</span></span>](https://aka.ms/encryptonly)

- [<span data-ttu-id="f73f2-113">添付ファイルの暗号化を解除するコントロール</span><span class="sxs-lookup"><span data-stu-id="f73f2-113">Control to decrypt attachments</span></span>](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
<span data-ttu-id="f73f2-114">この変更により、ユーザーは8月1日までに Office 365 Message Encryption Viewer モバイルアプリをダウンロードできなくなります。</span><span class="sxs-lookup"><span data-stu-id="f73f2-114">With this change, users will no longer be able to download the Office 365 Message Encryption Viewer mobile app beginning August 1.</span></span> <span data-ttu-id="f73f2-115">その結果、メールの受信者は、一部の Android および Apple モバイルデバイスで、以前のバージョンの OME で暗号化されたメッセージを読むことができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f73f2-115">As a result, mail recipients may not be able to read messages encrypted with the previous version of OME on some Android and Apple mobile devices.</span></span> <span data-ttu-id="f73f2-116">ただし、これらのメッセージをパーソナルコンピューター (デスクトップブラウザー経由) で読み取ることはできます。</span><span class="sxs-lookup"><span data-stu-id="f73f2-116">However, they will still be able to read these messages on personal computers (via desktop browsers).</span></span> <span data-ttu-id="f73f2-117">既にアプリをダウンロードしているユーザーは、引き続きそのアプリを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f73f2-117">Users who have already downloaded the app will continue to be able to use it.</span></span>
  
## <a name="why-this-change-was-made"></a><span data-ttu-id="f73f2-118">この変更が行われた理由</span><span class="sxs-lookup"><span data-stu-id="f73f2-118">Why this change was made</span></span>

<span data-ttu-id="f73f2-119">新しいバージョンの OME では、モバイルアプリで保護された電子メールメッセージと添付ファイルを読み取る必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f73f2-119">The new version of OME no longer requires a mobile app to read protected email messages and attachments.</span></span> <span data-ttu-id="f73f2-120">office 365 新しい OME 機能を使用しているお客様は、保護されたメッセージを Outlook mobile および非 Office 365 で表示できます。ユーザーは、保護されたメッセージをブラウザーで表示できます。</span><span class="sxs-lookup"><span data-stu-id="f73f2-120">Office 365 customers using the new OME capabilities can view the protected message in Outlook mobile and non-Office 365 customers can view protected messages in a browser.</span></span>
  
<span data-ttu-id="f73f2-121">ユーザーが保護されたメッセージを表示できるようにするために、ユーザーにモバイルアプリのダウンロードを要求する hurdle があります。</span><span class="sxs-lookup"><span data-stu-id="f73f2-121">Requiring users to download a mobile app is another hurdle for customers to view protected messages.</span></span> <span data-ttu-id="f73f2-122">新しい Office 365 メッセージの暗号化機能は、より優れたモバイル環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="f73f2-122">The new Office 365 Message Encryption capabilities provide a better mobile experience.</span></span>
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="f73f2-123">以前のバージョンの Office 365 メッセージの暗号化を引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f73f2-123">Can I still use the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="f73f2-124">以前のバージョンの office 365 メッセージの暗号化は、現時点では推奨されていません。ただし、新しいバージョンの office 365 message encryption には大幅な機能強化が加えられているため、機密データを暗号化して他のユーザーに保護することが容易になります。および任意のデバイス (Office 365 ユーザーが保護されたメッセージを Outlook (デスクトップ、モバイル、および web) で直接読み取る機能を含む)。</span><span class="sxs-lookup"><span data-stu-id="f73f2-124">The previous version of Office 365 Message Encryption will not be deprecated at this time, however, we have made significant enhancements to the new version of Office 365 Message Encryption, which make it easier to encrypt and rights protect sensitive data to anyone and on any device - including the ability for Office 365 users to read protected messages directly in Outlook (desktop, mobile, and web).</span></span> 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="f73f2-125">この変更を準備するために必要な作業</span><span class="sxs-lookup"><span data-stu-id="f73f2-125">What do I need to do to prepare for this change</span></span>

<span data-ttu-id="f73f2-126">組織が暗号化された添付ファイルを OME Viewer アプリを必要とする受信者に現在送信している場合は、ドキュメントとトレーニングリソースを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f73f2-126">If your organization currently sends encrypted attachments to recipients that require the OME Viewer app, you should update your documentation and training resources.</span></span>
  
<span data-ttu-id="f73f2-127">既存の Exchange メールフロールールを更新して現在のバージョンの OME を使用することをお勧めします。これにより、組織は新機能と強化された機能を活用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f73f2-127">We recommend updating existing Exchange mail flow rules to use the current version of OME so that your organization can take advantage of the new and improved capabilities.</span></span> <span data-ttu-id="f73f2-128">OME の新しい機能を設定すると、受信者はモバイルデバイスで暗号化されたメッセージを読み取るために OME ビューアアプリを必要としなくなります。</span><span class="sxs-lookup"><span data-stu-id="f73f2-128">Once you have set up the new OME capabilities, recipients won't need the OME Viewer app to read encrypted messages on mobile devices.</span></span>
  
<span data-ttu-id="f73f2-129">Microsoft は、組織にとって適切であることをすぐに、新しい OME 機能に移行するための計画を立てることを推奨します。</span><span class="sxs-lookup"><span data-stu-id="f73f2-129">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="f73f2-130">手順については、「 [Office の新しい365メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f73f2-130">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="f73f2-131">新しい機能が最初にどのように機能するかについて詳しくは、「 [Office 365 Message Encryption](ome.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f73f2-131">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span>
  

