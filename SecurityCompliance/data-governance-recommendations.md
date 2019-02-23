---
title: データ ガバナンスの推奨事項のためのコンテンツの識別方法
ms.author: brendonb
author: stephow-MSFT
manager: laurawi
ms.date: 1/15/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Office 365 セキュリティ/コンプライアンス センターは、組織の現在の設定に基づきデータ ガバナンスのための推奨事項を提供し、ユーザーによる設定作業を簡略化します。これらの推奨事項の一部は組織で特定のコンテンツを検出し、そのコンテンツを管理するための推奨手順を提供します。たとえば、重要な業務コンテンツ (弁護士依頼人間の秘匿特権や秘密保持契約書に関わる情報など) を含むアイテムが推奨事項によって検出された際に、ユーザーは保持ラベルを自動適用し、必要に応じてアイテムを機密扱いにして保持することができます。このトピックでは、ユーザーに表示される可能性があるデータ ガバナンスの推奨事項を一覧表示し、それぞれの推奨事項をトリガーするコンテンツについて説明します。
ms.openlocfilehash: 24e41501ed11d54e60f8b3d9f27a2e96f3cde112
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220437"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="bff85-106">データ ガバナンスの推奨事項のためのコンテンツの識別方法</span><span class="sxs-lookup"><span data-stu-id="bff85-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="bff85-p102">Office 365 セキュリティ/コンプライアンス センターは、組織の現在の設定に基づきデータ ガバナンスのための推奨事項を提供し、ユーザーによる設定作業を簡略化します。これらの推奨事項の一部は組織で特定のコンテンツを検出し、そのコンテンツを管理するための推奨手順を提供します。たとえば、重要な業務コンテンツ (弁護士依頼人間の秘匿特権や秘密保持契約書に関わる情報など) を含むアイテムが推奨事項によって検出された際に、ユーザーは保持ラベルを自動適用し、必要に応じてアイテムを機密扱いにして保持することができます。</span><span class="sxs-lookup"><span data-stu-id="bff85-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="bff85-110">このトピックでは、ユーザーに表示される可能性があるデータ ガバナンスの推奨事項を一覧表示し、それぞれの推奨事項をトリガーするコンテンツについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bff85-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="bff85-111">ボイスメールのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="bff85-111">Clean up voicemail</span></span>

<span data-ttu-id="bff85-p103">この推奨事項は、メッセージの種類が “ボイスメール” と識別されるメール メッセージがユーザーのメールボックスで検出されたときに表示されます。詳細については、「[Exchange でのメッセージのプロパティ](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bff85-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="bff85-114">弁護士/依頼人特権関連コンテンツのラベル付け</span><span class="sxs-lookup"><span data-stu-id="bff85-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="bff85-115">この推奨事項は、次のいずれかの条件が満たされた場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bff85-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="bff85-116">メール メッセージの本文で、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="bff85-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="bff85-117">ACP</span><span class="sxs-lookup"><span data-stu-id="bff85-117">ACP</span></span>
    - <span data-ttu-id="bff85-118">弁護士依頼人特権</span><span class="sxs-lookup"><span data-stu-id="bff85-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="bff85-119">弁護士/依頼人特権</span><span class="sxs-lookup"><span data-stu-id="bff85-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="bff85-120">弁護士/依頼人特権がある</span><span class="sxs-lookup"><span data-stu-id="bff85-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="bff85-121">SharePoint ファイルまたは OneDrive ファイルで、これらのキーワードのいずれの組み合わせも検出されます</span><span class="sxs-lookup"><span data-stu-id="bff85-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="bff85-122">ACP</span><span class="sxs-lookup"><span data-stu-id="bff85-122">ACP</span></span>
    - <span data-ttu-id="bff85-123">弁護士依頼人特権\*</span><span class="sxs-lookup"><span data-stu-id="bff85-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="bff85-124">AC 特権</span><span class="sxs-lookup"><span data-stu-id="bff85-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="bff85-125">オーディオ ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="bff85-125">Retain audio files</span></span>

<span data-ttu-id="bff85-126">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bff85-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="bff85-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="bff85-127">.MP3</span></span>
- <span data-ttu-id="bff85-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="bff85-128">.WMA</span></span>
- <span data-ttu-id="bff85-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="bff85-129">.WAV</span></span>
- <span data-ttu-id="bff85-130">.RA</span><span class="sxs-lookup"><span data-stu-id="bff85-130">.RA</span></span>
- <span data-ttu-id="bff85-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="bff85-131">.RAM</span></span>
- <span data-ttu-id="bff85-132">.RM</span><span class="sxs-lookup"><span data-stu-id="bff85-132">.RM</span></span>
- <span data-ttu-id="bff85-133">.MID</span><span class="sxs-lookup"><span data-stu-id="bff85-133">.MID</span></span>
- <span data-ttu-id="bff85-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="bff85-134">.OGG</span></span>
- <span data-ttu-id="bff85-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="bff85-135">.AIFF</span></span>
- <span data-ttu-id="bff85-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="bff85-136">.PCM</span></span>
- <span data-ttu-id="bff85-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="bff85-137">.AAC</span></span>
- <span data-ttu-id="bff85-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="bff85-138">.FLAC</span></span>
- <span data-ttu-id="bff85-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="bff85-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="bff85-140">CAD ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="bff85-140">Retain CAD files</span></span>

<span data-ttu-id="bff85-141">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bff85-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="bff85-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="bff85-142">.3DXML</span></span>
- <span data-ttu-id="bff85-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="bff85-143">.ACIS</span></span>
- <span data-ttu-id="bff85-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="bff85-144">.ARC</span></span>
- <span data-ttu-id="bff85-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="bff85-145">.ASM</span></span>
- <span data-ttu-id="bff85-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="bff85-146">.CAT\*</span></span>
- <span data-ttu-id="bff85-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="bff85-147">.CGR</span></span>
- <span data-ttu-id="bff85-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="bff85-148">.DW\*</span></span>
- <span data-ttu-id="bff85-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="bff85-149">.DX\*</span></span>
- <span data-ttu-id="bff85-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="bff85-150">.EDRW</span></span>
- <span data-ttu-id="bff85-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="bff85-151">.IAM</span></span>
- <span data-ttu-id="bff85-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="bff85-152">.IGES</span></span>
- <span data-ttu-id="bff85-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="bff85-153">.IGS</span></span>
- <span data-ttu-id="bff85-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="bff85-154">.IPT</span></span>
- <span data-ttu-id="bff85-155">.JT</span><span class="sxs-lookup"><span data-stu-id="bff85-155">.JT</span></span>
- <span data-ttu-id="bff85-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="bff85-156">.MF1</span></span>
- <span data-ttu-id="bff85-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="bff85-157">.NEU</span></span>
- <span data-ttu-id="bff85-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="bff85-158">.PAR</span></span>
- <span data-ttu-id="bff85-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="bff85-159">.PKG</span></span>
- <span data-ttu-id="bff85-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="bff85-160">.PRC</span></span>
- <span data-ttu-id="bff85-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="bff85-161">.PRT</span></span>
- <span data-ttu-id="bff85-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="bff85-162">.PSM</span></span>
- <span data-ttu-id="bff85-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="bff85-163">.PWD</span></span>
- <span data-ttu-id="bff85-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="bff85-164">.SLD\*</span></span>
- <span data-ttu-id="bff85-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="bff85-165">.STEP</span></span>
- <span data-ttu-id="bff85-166">.STL</span><span class="sxs-lookup"><span data-stu-id="bff85-166">.STL</span></span>
- <span data-ttu-id="bff85-167">.STP</span><span class="sxs-lookup"><span data-stu-id="bff85-167">.STP</span></span>
- <span data-ttu-id="bff85-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="bff85-168">.U3D</span></span>
- <span data-ttu-id="bff85-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="bff85-169">.UNV</span></span>
- <span data-ttu-id="bff85-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="bff85-170">.VRML</span></span>
- <span data-ttu-id="bff85-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="bff85-171">.WRL</span></span>
- <span data-ttu-id="bff85-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="bff85-172">.X_\*</span></span>
- <span data-ttu-id="bff85-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="bff85-173">.XAS</span></span>
- <span data-ttu-id="bff85-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="bff85-174">.XMT\*</span></span>
- <span data-ttu-id="bff85-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="bff85-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="bff85-176">画像ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="bff85-176">Retain image files</span></span>

<span data-ttu-id="bff85-177">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bff85-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="bff85-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="bff85-178">.JPEG</span></span>
- <span data-ttu-id="bff85-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="bff85-179">.GIF</span></span>
- <span data-ttu-id="bff85-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="bff85-180">.TIF\*</span></span>
- <span data-ttu-id="bff85-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="bff85-181">.BMP</span></span>
- <span data-ttu-id="bff85-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="bff85-182">.PNG</span></span>
- <span data-ttu-id="bff85-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="bff85-183">.RAW</span></span>
- <span data-ttu-id="bff85-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="bff85-184">.PSD</span></span>
- <span data-ttu-id="bff85-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="bff85-185">.PSP</span></span>
- <span data-ttu-id="bff85-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="bff85-186">.JPG</span></span>
- <span data-ttu-id="bff85-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="bff85-187">.EXIF</span></span>
- <span data-ttu-id="bff85-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="bff85-188">.PPM</span></span>
- <span data-ttu-id="bff85-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="bff85-189">.PGM</span></span>
- <span data-ttu-id="bff85-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="bff85-190">.PBM</span></span>
- <span data-ttu-id="bff85-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="bff85-191">.PNM</span></span>
- <span data-ttu-id="bff85-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="bff85-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="bff85-193">NDA 関連コンテンツの保持</span><span class="sxs-lookup"><span data-stu-id="bff85-193">Retain NDA content</span></span> 

<span data-ttu-id="bff85-194">この推奨事項は、次のいずれかの条件が満たされた場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bff85-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="bff85-195">メール メッセージの本文で、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="bff85-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="bff85-196">NDA</span><span class="sxs-lookup"><span data-stu-id="bff85-196">NDA</span></span>
    - <span data-ttu-id="bff85-197">“秘密保持契約”</span><span class="sxs-lookup"><span data-stu-id="bff85-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="bff85-198">“秘密保持契約”</span><span class="sxs-lookup"><span data-stu-id="bff85-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="bff85-199">SharePoint または OneDrive の .PDF または .DOC ファイルで、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="bff85-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="bff85-200">NDA</span><span class="sxs-lookup"><span data-stu-id="bff85-200">NDA</span></span>
    - <span data-ttu-id="bff85-201">“秘密保持契約”</span><span class="sxs-lookup"><span data-stu-id="bff85-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="bff85-202">ソフトウェア開発ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="bff85-202">Retain software development files</span></span>

<span data-ttu-id="bff85-203">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bff85-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="bff85-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="bff85-204">.ASAX</span></span>
- <span data-ttu-id="bff85-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="bff85-205">.ASM</span></span>
- <span data-ttu-id="bff85-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="bff85-206">.ASP\*</span></span>
- <span data-ttu-id="bff85-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="bff85-207">.BAT</span></span>
- <span data-ttu-id="bff85-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="bff85-208">.CONFIG</span></span>
- <span data-ttu-id="bff85-209">.CS</span><span class="sxs-lookup"><span data-stu-id="bff85-209">.CS</span></span>
- <span data-ttu-id="bff85-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="bff85-210">.CSS</span></span>
- <span data-ttu-id="bff85-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="bff85-211">.DISCO</span></span>
- <span data-ttu-id="bff85-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="bff85-212">.HTM\*</span></span>
- <span data-ttu-id="bff85-213">.INC</span><span class="sxs-lookup"><span data-stu-id="bff85-213">.INC</span></span>
- <span data-ttu-id="bff85-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="bff85-214">.JAD</span></span>
- <span data-ttu-id="bff85-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="bff85-215">.JAVA</span></span>
- <span data-ttu-id="bff85-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="bff85-216">.JS\*</span></span>
- <span data-ttu-id="bff85-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="bff85-217">.LIB</span></span>
- <span data-ttu-id="bff85-218">.O</span><span class="sxs-lookup"><span data-stu-id="bff85-218">.O</span></span>
- <span data-ttu-id="bff85-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="bff85-219">.PHP</span></span>
- <span data-ttu-id="bff85-220">.RC</span><span class="sxs-lookup"><span data-stu-id="bff85-220">.RC</span></span>
- <span data-ttu-id="bff85-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="bff85-221">.RESX</span></span>
- <span data-ttu-id="bff85-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="bff85-222">.RPT</span></span>
- <span data-ttu-id="bff85-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="bff85-223">.RSS</span></span>
- <span data-ttu-id="bff85-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="bff85-224">.SCPT</span></span>
- <span data-ttu-id="bff85-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="bff85-225">.SRC</span></span>
- <span data-ttu-id="bff85-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="bff85-226">.VB\*</span></span>
- <span data-ttu-id="bff85-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="bff85-227">.WSF</span></span>
- <span data-ttu-id="bff85-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="bff85-228">.XCODEPROJ</span></span>
- <span data-ttu-id="bff85-229">.XML</span><span class="sxs-lookup"><span data-stu-id="bff85-229">.XML</span></span>
- <span data-ttu-id="bff85-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="bff85-230">.XSD</span></span>
- <span data-ttu-id="bff85-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="bff85-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="bff85-232">ビデオ ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="bff85-232">Retain video files</span></span>

<span data-ttu-id="bff85-233">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bff85-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="bff85-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="bff85-234">.AVCHD</span></span>
- <span data-ttu-id="bff85-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="bff85-235">.AVI</span></span>
- <span data-ttu-id="bff85-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="bff85-236">.FLV</span></span>
- <span data-ttu-id="bff85-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="bff85-237">.MOV</span></span>
- <span data-ttu-id="bff85-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="bff85-238">.MP2V</span></span>
- <span data-ttu-id="bff85-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="bff85-239">.MP4</span></span>
- <span data-ttu-id="bff85-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="bff85-240">.MP4V</span></span>
- <span data-ttu-id="bff85-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="bff85-241">.MPE</span></span>
- <span data-ttu-id="bff85-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="bff85-242">.MPEG</span></span>
- <span data-ttu-id="bff85-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="bff85-243">.MPEG1</span></span>
- <span data-ttu-id="bff85-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="bff85-244">.MPEG2</span></span>
- <span data-ttu-id="bff85-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="bff85-245">.MPEG4</span></span>
- <span data-ttu-id="bff85-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="bff85-246">.MPG</span></span>
- <span data-ttu-id="bff85-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="bff85-247">.MPG2</span></span>
- <span data-ttu-id="bff85-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="bff85-248">.MPG4</span></span>
- <span data-ttu-id="bff85-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="bff85-249">.WMV</span></span>
- <span data-ttu-id="bff85-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="bff85-250">.XMV</span></span>
