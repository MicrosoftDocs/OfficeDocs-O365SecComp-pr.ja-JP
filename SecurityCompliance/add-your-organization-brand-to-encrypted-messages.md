---
title: 暗号化されたメッセージに、組織のブランドを追加します。
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/2/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
description: 'Exchange 管理者は、組織のブランドの組織の暗号化された電子メール メッセージや暗号化のポータルのコンテンツに適用できます。 '
ms.openlocfilehash: 2f34b5cea3155f587fd7787f1f69270d1373400b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532167"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a><span data-ttu-id="0bdfc-103">組織のブランドを暗号化されたメッセージに追加する</span><span class="sxs-lookup"><span data-stu-id="0bdfc-103">Add your organization's brand to your encrypted messages</span></span>

<span data-ttu-id="0bdfc-p101">オンライン Exchange または Exchange のオンライン保護管理者は、会社、組織の Office 365 のメッセージの暗号化電子メール メッセージの外観および暗号化のポータルのコンテンツをカスタマイズするのにはブランド化を適用できます。Get OMEConfiguration とセット OMEConfiguration Windows PowerShell コマンドレットを使用すると、暗号化された電子メール メッセージの受信者の表示操作の次の側面をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="0bdfc-p101">As an Exchange Online or Exchange Online Protection administrator, you can apply your company branding to customize the look of your organization's Office 365 Message Encryption email messages and the contents of the encryption portal. Using the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets, you can customize the following aspects of the viewing experience for recipients of encrypted email messages:</span></span>
  
- <span data-ttu-id="0bdfc-106">暗号化メッセージを含む電子メールの導入部のテキスト</span><span class="sxs-lookup"><span data-stu-id="0bdfc-106">Introductory text of the email that contains the encrypted message</span></span>
    
- <span data-ttu-id="0bdfc-107">暗号化メッセージを含む電子メールの免責事項のテキスト</span><span class="sxs-lookup"><span data-stu-id="0bdfc-107">Disclaimer text of the email that contains the encrypted message</span></span>
    
- <span data-ttu-id="0bdfc-108">ホーム ポータルに表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="0bdfc-108">Text that appears in the OME portal</span></span>
    
- <span data-ttu-id="0bdfc-109">ホーム ポータル、電子メール メッセージに表示されるロゴ</span><span class="sxs-lookup"><span data-stu-id="0bdfc-109">Logo that appears in the email message and OME portal</span></span>
    
- <span data-ttu-id="0bdfc-110">ホーム ポータル、電子メール メッセージの背景色</span><span class="sxs-lookup"><span data-stu-id="0bdfc-110">Background color in the email message and OME portal</span></span>
    
<span data-ttu-id="0bdfc-111">いつでも既定のルック アンド フィールに戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="0bdfc-111">You can also revert back to the default look and feel at any time.</span></span>
  
||
|:-----|
|<span data-ttu-id="0bdfc-p102">この資料は、Office 365 のメッセージの暗号化についての記事の大規模な一連の一部です。この資料は、管理者および ITPros。だけを行う場合、暗号化されたメッセージを送受信する情報は[Office 365 メッセージの暗号化 (ホーム)](ome.md)内のアーティクルの一覧を参照してくださいし、お客様のニーズに最も適した記事を検索します。</span><span class="sxs-lookup"><span data-stu-id="0bdfc-p102">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||
   
<span data-ttu-id="0bdfc-115">**組織のブランドを使用してホームで暗号化のホーム ポータルや電子メール メッセージの外観をカスタマイズする**</span><span class="sxs-lookup"><span data-stu-id="0bdfc-115">**To customize the look of the OME portal and email messages encrypted by OME with your organization's brand**</span></span>
  
1. <span data-ttu-id="0bdfc-116">[Exchange オンラインを使用してリモート PowerShell への接続](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)で説明するようリモート PowerShell を使用して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="0bdfc-116">Connect to Exchange Online using Remote PowerShell, as described in [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="0bdfc-117">[セット OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)で説明したように、セット OMEConfiguration コマンドレットを使用してまたはガイダンスについては、次の表を使用します。</span><span class="sxs-lookup"><span data-stu-id="0bdfc-117">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b) or use the following table for guidance.</span></span> 
    
<span data-ttu-id="0bdfc-118">**暗号化のカスタマイズ オプション**</span><span class="sxs-lookup"><span data-stu-id="0bdfc-118">**Encryption customization options**</span></span>

|<span data-ttu-id="0bdfc-119">**カスタマイズする暗号化エクスペリエンスの特性**</span><span class="sxs-lookup"><span data-stu-id="0bdfc-119">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="0bdfc-120">**これらのコマンドを使用します。**</span><span class="sxs-lookup"><span data-stu-id="0bdfc-120">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0bdfc-p103">暗号化された電子メール メッセージに付属する既定のテキスト。暗号化されたメッセージを表示するための指示の上に既定のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bdfc-p103">Default text that accompanies encrypted email messages. The default text appears above the instructions for viewing encrypted messages</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="0bdfc-123">**例:** </span><span class="sxs-lookup"><span data-stu-id="0bdfc-123">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="0bdfc-124">暗号化メッセージを含む電子メールの免責文</span><span class="sxs-lookup"><span data-stu-id="0bdfc-124">Disclaimer statement in the email that contains the encrypted message</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="0bdfc-125">**例:** </span><span class="sxs-lookup"><span data-stu-id="0bdfc-125">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only."` <br/> |
|<span data-ttu-id="0bdfc-126">暗号化メールの表示ポータルの最上部に表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="0bdfc-126">Text that appears at the top of the encrypted mail viewing portal</span></span><br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="0bdfc-127">**例:** </span><span class="sxs-lookup"><span data-stu-id="0bdfc-127">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."` <br/> |
|<span data-ttu-id="0bdfc-128">ロゴ</span><span class="sxs-lookup"><span data-stu-id="0bdfc-128">Logo</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> <span data-ttu-id="0bdfc-129">**例:** </span><span class="sxs-lookup"><span data-stu-id="0bdfc-129">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="0bdfc-130">サポートされているファイル形式: .png、.jpg、.bmp、.tiff</span><span class="sxs-lookup"><span data-stu-id="0bdfc-130">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="0bdfc-131">ロゴ ファイルの最適なサイズ:40 KB 未満</span><span class="sxs-lookup"><span data-stu-id="0bdfc-131">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="0bdfc-132">最適なロゴ画像のサイズ:170x70 ピクセル</span><span class="sxs-lookup"><span data-stu-id="0bdfc-132">Optimal size of logo image: 170x70 pixels</span></span>  <br/> |
|<span data-ttu-id="0bdfc-133">背景色</span><span class="sxs-lookup"><span data-stu-id="0bdfc-133">Background color</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> <span data-ttu-id="0bdfc-134">**例:** </span><span class="sxs-lookup"><span data-stu-id="0bdfc-134">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -BackgroundColor "#ffffff"` <br/> |
   
<span data-ttu-id="0bdfc-135">**ホームで暗号化されたホーム ポータル、電子メール メッセージから、ブランドのカスタマイズを削除するのには**</span><span class="sxs-lookup"><span data-stu-id="0bdfc-135">**To remove brand customizations from the OME portal and email messages encrypted by OME**</span></span>
  
1. <span data-ttu-id="0bdfc-136">[Exchange オンラインを使用してリモート PowerShell への接続](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)で説明するようリモート PowerShell を使用して Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="0bdfc-136">Connect to Exchange Online using Remote PowerShell, as described in [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="0bdfc-p104">[セット OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)で説明したように、セット OMEConfiguration コマンドレットを使用します。組織を削除するのには、DisclaimerText、EmailText からのカスタマイズをブランドし、PortalText の値を空の文字列値を設定する`""`。すべてのイメージ、ロゴなどの値の値を設定、 `"$null"`。</span><span class="sxs-lookup"><span data-stu-id="0bdfc-p104">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b). To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string,  `""`. For all image values, such as Logo, set the value to  `"$null"`.</span></span>
    
<span data-ttu-id="0bdfc-140">**暗号化のカスタマイズ オプション**</span><span class="sxs-lookup"><span data-stu-id="0bdfc-140">**Encryption customization options**</span></span>

<span data-ttu-id="0bdfc-141">**この暗号化の機能を既定のテキストと画像に戻すには**</span><span class="sxs-lookup"><span data-stu-id="0bdfc-141">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="0bdfc-142">**これらのコマンドを使用します。**</span><span class="sxs-lookup"><span data-stu-id="0bdfc-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0bdfc-143">暗号化された電子メール メッセージに付けられる既定のテキスト</span><span class="sxs-lookup"><span data-stu-id="0bdfc-143">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="0bdfc-144">暗号化メッセージの表示手順の上に表示される既定のテキスト</span><span class="sxs-lookup"><span data-stu-id="0bdfc-144">The default text appears above the instructions for viewing encrypted messages</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> <span data-ttu-id="0bdfc-145">**例:** </span><span class="sxs-lookup"><span data-stu-id="0bdfc-145">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|<span data-ttu-id="0bdfc-146">暗号化メッセージを含む電子メールの免責文</span><span class="sxs-lookup"><span data-stu-id="0bdfc-146">Disclaimer statement in the email that contains the encrypted message</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> <span data-ttu-id="0bdfc-147">**例:** </span><span class="sxs-lookup"><span data-stu-id="0bdfc-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|<span data-ttu-id="0bdfc-148">暗号化メールの表示ポータルの最上部に表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="0bdfc-148">Text that appears at the top of the encrypted mail viewing portal</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> <span data-ttu-id="0bdfc-149">**既定値に戻すの背面を例:**</span><span class="sxs-lookup"><span data-stu-id="0bdfc-149">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|<span data-ttu-id="0bdfc-150">ロゴ</span><span class="sxs-lookup"><span data-stu-id="0bdfc-150">Logo</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> <span data-ttu-id="0bdfc-151">**既定値に戻すの背面を例:**</span><span class="sxs-lookup"><span data-stu-id="0bdfc-151">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
|<span data-ttu-id="0bdfc-152">背景色</span><span class="sxs-lookup"><span data-stu-id="0bdfc-152">Background color</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> <span data-ttu-id="0bdfc-153">**既定値に戻すの背面を例:**</span><span class="sxs-lookup"><span data-stu-id="0bdfc-153">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null` <br/> |
   

