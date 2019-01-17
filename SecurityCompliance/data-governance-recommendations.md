---
title: データ ガバナンスの推奨事項のためのコンテンツの識別方法
ms.author: brendonb
author: stephow-MSFT
manager: laurawi
ms.date: 1/15/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Office 365 セキュリティ/コンプライアンス センターは、組織の現在の設定に基づきデータ ガバナンスのための推奨事項を提供し、ユーザーによる設定作業を簡略化します。これらの推奨事項の一部は組織で特定のコンテンツを検出し、そのコンテンツを管理するための推奨手順を提供します。たとえば、重要な業務コンテンツ (弁護士依頼人間の秘匿特権や秘密保持契約書に関わる情報など) を含むアイテムが推奨事項によって検出された際に、ユーザーは保持ラベルを自動適用し、必要に応じてアイテムを機密扱いにして保持することができます。このトピックでは、ユーザーに表示される可能性があるデータ ガバナンスの推奨事項を一覧表示し、それぞれの推奨事項をトリガーするコンテンツについて説明します。
ms.openlocfilehash: a3f803105ea5c2626c8c2a26ad898df5f45af2f0
ms.sourcegitcommit: c7737903ff2e1d047682ee61f7ac21b0bdd1c6fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "28263946"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="886d1-106">データ ガバナンスの推奨事項のためのコンテンツの識別方法</span><span class="sxs-lookup"><span data-stu-id="886d1-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="886d1-p102">Office 365 セキュリティ/コンプライアンス センターは、組織の現在の設定に基づきデータ ガバナンスのための推奨事項を提供し、ユーザーによる設定作業を簡略化します。これらの推奨事項の一部は組織で特定のコンテンツを検出し、そのコンテンツを管理するための推奨手順を提供します。たとえば、重要な業務コンテンツ (弁護士依頼人間の秘匿特権や秘密保持契約書に関わる情報など) を含むアイテムが推奨事項によって検出された際に、ユーザーは保持ラベルを自動適用し、必要に応じてアイテムを機密扱いにして保持することができます。</span><span class="sxs-lookup"><span data-stu-id="886d1-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="886d1-110">このトピックでは、ユーザーに表示される可能性があるデータ ガバナンスの推奨事項を一覧表示し、それぞれの推奨事項をトリガーするコンテンツについて説明します。</span><span class="sxs-lookup"><span data-stu-id="886d1-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="886d1-111">ボイスメールのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="886d1-111">Clean up voicemail</span></span>

<span data-ttu-id="886d1-p103">この推奨事項は、メッセージの種類が “ボイスメール” と識別されるメール メッセージがユーザーのメールボックスで検出されたときに表示されます。詳細については、「[Exchange でのメッセージのプロパティ](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="886d1-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="886d1-114">弁護士/依頼人特権関連コンテンツのラベル付け</span><span class="sxs-lookup"><span data-stu-id="886d1-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="886d1-115">この推奨事項は、次のいずれかの条件が満たされた場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="886d1-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="886d1-116">メール メッセージの本文で、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="886d1-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="886d1-117">ACP</span><span class="sxs-lookup"><span data-stu-id="886d1-117">ACP</span></span>
    - <span data-ttu-id="886d1-118">弁護士依頼人特権</span><span class="sxs-lookup"><span data-stu-id="886d1-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="886d1-119">弁護士/依頼人特権</span><span class="sxs-lookup"><span data-stu-id="886d1-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="886d1-120">弁護士/依頼人特権がある</span><span class="sxs-lookup"><span data-stu-id="886d1-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="886d1-121">SharePoint ファイルまたは OneDrive ファイルで、これらのキーワードのいずれの組み合わせも検出されます</span><span class="sxs-lookup"><span data-stu-id="886d1-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="886d1-122">ACP</span><span class="sxs-lookup"><span data-stu-id="886d1-122">ACP</span></span>
    - <span data-ttu-id="886d1-123">弁護士依頼人特権\*</span><span class="sxs-lookup"><span data-stu-id="886d1-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="886d1-124">AC 特権</span><span class="sxs-lookup"><span data-stu-id="886d1-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="886d1-125">オーディオ ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="886d1-125">Retain audio files</span></span>

<span data-ttu-id="886d1-126">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="886d1-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="886d1-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="886d1-127">MP3 (default)</span></span>
- <span data-ttu-id="886d1-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="886d1-128">WMA</span></span>
- <span data-ttu-id="886d1-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="886d1-129">WAV</span></span>
- <span data-ttu-id="886d1-130">.RA</span><span class="sxs-lookup"><span data-stu-id="886d1-130">.RA</span></span>
- <span data-ttu-id="886d1-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="886d1-131">RAM</span></span>
- <span data-ttu-id="886d1-132">.RM</span><span class="sxs-lookup"><span data-stu-id="886d1-132">rm</span></span>
- <span data-ttu-id="886d1-133">.MID</span><span class="sxs-lookup"><span data-stu-id="886d1-133">.MID</span></span>
- <span data-ttu-id="886d1-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="886d1-134">.OGG</span></span>
- <span data-ttu-id="886d1-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="886d1-135">.AIFF</span></span>
- <span data-ttu-id="886d1-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="886d1-136">.PCM</span></span>
- <span data-ttu-id="886d1-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="886d1-137">.AAC</span></span>
- <span data-ttu-id="886d1-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="886d1-138">.FLAC</span></span>
- <span data-ttu-id="886d1-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="886d1-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="886d1-140">CAD ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="886d1-140">Retain CAD files</span></span>

<span data-ttu-id="886d1-141">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="886d1-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="886d1-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="886d1-142">.3DXML</span></span>
- <span data-ttu-id="886d1-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="886d1-143">.ACIS</span></span>
- <span data-ttu-id="886d1-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="886d1-144">ARC
</span></span>
- <span data-ttu-id="886d1-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="886d1-145">asm</span></span>
- <span data-ttu-id="886d1-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="886d1-146">cat</span></span>
- <span data-ttu-id="886d1-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="886d1-147">.CGR</span></span>
- <span data-ttu-id="886d1-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="886d1-148">DW</span></span>
- <span data-ttu-id="886d1-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="886d1-149">Dx</span></span>
- <span data-ttu-id="886d1-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="886d1-150">.EDRW</span></span>
- <span data-ttu-id="886d1-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="886d1-151">.IAM</span></span>
- <span data-ttu-id="886d1-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="886d1-152">.IGES</span></span>
- <span data-ttu-id="886d1-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="886d1-153">.IGS</span></span>
- <span data-ttu-id="886d1-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="886d1-154">.IPT</span></span>
- <span data-ttu-id="886d1-155">.JT</span><span class="sxs-lookup"><span data-stu-id="886d1-155">.JT</span></span>
- <span data-ttu-id="886d1-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="886d1-156">.MF1</span></span>
- <span data-ttu-id="886d1-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="886d1-157">.NEU</span></span>
- <span data-ttu-id="886d1-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="886d1-158">.PAR</span></span>
- <span data-ttu-id="886d1-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="886d1-159">.PKG</span></span>
- <span data-ttu-id="886d1-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="886d1-160">PRC
</span></span>
- <span data-ttu-id="886d1-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="886d1-161">.PRT</span></span>
- <span data-ttu-id="886d1-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="886d1-162">.PSM</span></span>
- <span data-ttu-id="886d1-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="886d1-163">.PWD</span></span>
- <span data-ttu-id="886d1-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="886d1-164">.SLD\*</span></span>
- <span data-ttu-id="886d1-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="886d1-165">Step</span></span>
- <span data-ttu-id="886d1-166">.STL</span><span class="sxs-lookup"><span data-stu-id="886d1-166">.STL</span></span>
- <span data-ttu-id="886d1-167">.STP</span><span class="sxs-lookup"><span data-stu-id="886d1-167">.STP</span></span>
- <span data-ttu-id="886d1-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="886d1-168">.U3D</span></span>
- <span data-ttu-id="886d1-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="886d1-169">.UNV</span></span>
- <span data-ttu-id="886d1-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="886d1-170">.VRML</span></span>
- <span data-ttu-id="886d1-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="886d1-171">.WRL</span></span>
- <span data-ttu-id="886d1-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="886d1-172">X</span></span>
- <span data-ttu-id="886d1-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="886d1-173">.XAS</span></span>
- <span data-ttu-id="886d1-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="886d1-174">.XMT\*</span></span>
- <span data-ttu-id="886d1-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="886d1-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="886d1-176">画像ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="886d1-176">Retain image files</span></span>

<span data-ttu-id="886d1-177">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="886d1-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="886d1-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="886d1-178">JPEG</span></span>
- <span data-ttu-id="886d1-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="886d1-179">GIF</span></span>
- <span data-ttu-id="886d1-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="886d1-180">tif</span></span>
- <span data-ttu-id="886d1-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="886d1-181">.bmp</span></span>
- <span data-ttu-id="886d1-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="886d1-182">PNG</span></span>
- <span data-ttu-id="886d1-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="886d1-183">.RAW</span></span>
- <span data-ttu-id="886d1-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="886d1-184">.PSD</span></span>
- <span data-ttu-id="886d1-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="886d1-185">PSP
</span></span>
- <span data-ttu-id="886d1-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="886d1-186">.jpg</span></span>
- <span data-ttu-id="886d1-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="886d1-187">.EXIF</span></span>
- <span data-ttu-id="886d1-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="886d1-188">PPM capabilities</span></span>
- <span data-ttu-id="886d1-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="886d1-189">.PGM</span></span>
- <span data-ttu-id="886d1-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="886d1-190">.PBM</span></span>
- <span data-ttu-id="886d1-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="886d1-191">.PNM</span></span>
- <span data-ttu-id="886d1-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="886d1-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="886d1-193">NDA 関連コンテンツの保持</span><span class="sxs-lookup"><span data-stu-id="886d1-193">Retain NDA content</span></span> 

<span data-ttu-id="886d1-194">この推奨事項は、次のいずれかの条件が満たされた場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="886d1-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="886d1-195">メール メッセージの本文で、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="886d1-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="886d1-196">NDA</span><span class="sxs-lookup"><span data-stu-id="886d1-196">NDA</span></span>
    - <span data-ttu-id="886d1-197">“秘密保持契約”</span><span class="sxs-lookup"><span data-stu-id="886d1-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="886d1-198">“秘密保持契約”</span><span class="sxs-lookup"><span data-stu-id="886d1-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="886d1-199">SharePoint または OneDrive の .PDF または .DOC ファイルで、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="886d1-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="886d1-200">NDA</span><span class="sxs-lookup"><span data-stu-id="886d1-200">NDA</span></span>
    - <span data-ttu-id="886d1-201">“秘密保持契約”</span><span class="sxs-lookup"><span data-stu-id="886d1-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="886d1-202">ソフトウェア開発ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="886d1-202">Retain software development files</span></span>

<span data-ttu-id="886d1-203">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="886d1-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="886d1-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="886d1-204">.ASAX</span></span>
- <span data-ttu-id="886d1-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="886d1-205">asm</span></span>
- <span data-ttu-id="886d1-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="886d1-206">asp</span></span>
- <span data-ttu-id="886d1-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="886d1-207">bat</span></span>
- <span data-ttu-id="886d1-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="886d1-208">.config</span></span>
- <span data-ttu-id="886d1-209">.CS</span><span class="sxs-lookup"><span data-stu-id="886d1-209">cs</span></span>
- <span data-ttu-id="886d1-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="886d1-210">CSS</span></span>
- <span data-ttu-id="886d1-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="886d1-211">.DISCO</span></span>
- <span data-ttu-id="886d1-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="886d1-212">htm</span></span>
- <span data-ttu-id="886d1-213">.INC</span><span class="sxs-lookup"><span data-stu-id="886d1-213">.INC</span></span>
- <span data-ttu-id="886d1-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="886d1-214">.JAD</span></span>
- <span data-ttu-id="886d1-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="886d1-215">Java</span></span>
- <span data-ttu-id="886d1-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="886d1-216">.js</span></span>
- <span data-ttu-id="886d1-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="886d1-217">\lib</span></span>
- <span data-ttu-id="886d1-218">.O</span><span class="sxs-lookup"><span data-stu-id="886d1-218">O</span></span>
- <span data-ttu-id="886d1-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="886d1-219">PHP</span></span>
- <span data-ttu-id="886d1-220">.RC</span><span class="sxs-lookup"><span data-stu-id="886d1-220">.RC</span></span>
- <span data-ttu-id="886d1-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="886d1-221">\*.resx</span></span>
- <span data-ttu-id="886d1-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="886d1-222">.RPT</span></span>
- <span data-ttu-id="886d1-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="886d1-223">RSS</span></span>
- <span data-ttu-id="886d1-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="886d1-224">.SCPT</span></span>
- <span data-ttu-id="886d1-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="886d1-225">.SRC</span></span>
- <span data-ttu-id="886d1-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="886d1-226">.vb</span></span>
- <span data-ttu-id="886d1-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="886d1-227">.wsf</span></span>
- <span data-ttu-id="886d1-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="886d1-228">.XCODEPROJ</span></span>
- <span data-ttu-id="886d1-229">.XML</span><span class="sxs-lookup"><span data-stu-id="886d1-229">XML</span></span>
- <span data-ttu-id="886d1-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="886d1-230">.XSD</span></span>
- <span data-ttu-id="886d1-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="886d1-231">XSL</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="886d1-232">ビデオ ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="886d1-232">Retain video files</span></span>

<span data-ttu-id="886d1-233">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="886d1-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="886d1-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="886d1-234">.AVCHD</span></span>
- <span data-ttu-id="886d1-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="886d1-235">avi</span></span>
- <span data-ttu-id="886d1-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="886d1-236">.FLV</span></span>
- <span data-ttu-id="886d1-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="886d1-237">.MOV</span></span>
- <span data-ttu-id="886d1-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="886d1-238">.MP2V</span></span>
- <span data-ttu-id="886d1-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="886d1-239">.MP4</span></span>
- <span data-ttu-id="886d1-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="886d1-240">.MP4V</span></span>
- <span data-ttu-id="886d1-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="886d1-241">.MPE</span></span>
- <span data-ttu-id="886d1-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="886d1-242">MPEG</span></span>
- <span data-ttu-id="886d1-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="886d1-243">.MPEG1</span></span>
- <span data-ttu-id="886d1-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="886d1-244">.MPEG2</span></span>
- <span data-ttu-id="886d1-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="886d1-245">.MPEG4</span></span>
- <span data-ttu-id="886d1-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="886d1-246">.MPG</span></span>
- <span data-ttu-id="886d1-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="886d1-247">.MPG2</span></span>
- <span data-ttu-id="886d1-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="886d1-248">.MPG4</span></span>
- <span data-ttu-id="886d1-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="886d1-249">.WMV</span></span>
- <span data-ttu-id="886d1-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="886d1-250">.XMV</span></span>
