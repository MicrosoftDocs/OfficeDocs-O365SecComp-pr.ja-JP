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
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>組織のブランドを暗号化されたメッセージに追加する

オンライン Exchange または Exchange のオンライン保護管理者は、会社、組織の Office 365 のメッセージの暗号化電子メール メッセージの外観および暗号化のポータルのコンテンツをカスタマイズするのにはブランド化を適用できます。Get OMEConfiguration とセット OMEConfiguration Windows PowerShell コマンドレットを使用すると、暗号化された電子メール メッセージの受信者の表示操作の次の側面をカスタマイズできます。
  
- 暗号化メッセージを含む電子メールの導入部のテキスト
    
- 暗号化メッセージを含む電子メールの免責事項のテキスト
    
- ホーム ポータルに表示されるテキスト
    
- ホーム ポータル、電子メール メッセージに表示されるロゴ
    
- ホーム ポータル、電子メール メッセージの背景色
    
いつでも既定のルック アンド フィールに戻すこともできます。
  
||
|:-----|
|この資料は、Office 365 のメッセージの暗号化についての記事の大規模な一連の一部です。この資料は、管理者および ITPros。だけを行う場合、暗号化されたメッセージを送受信する情報は[Office 365 メッセージの暗号化 (ホーム)](ome.md)内のアーティクルの一覧を参照してくださいし、お客様のニーズに最も適した記事を検索します。 |
||
   
**組織のブランドを使用してホームで暗号化のホーム ポータルや電子メール メッセージの外観をカスタマイズする**
  
1. [Exchange オンラインを使用してリモート PowerShell への接続](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)で説明するようリモート PowerShell を使用して Exchange Online に接続します。
    
2. [セット OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)で説明したように、セット OMEConfiguration コマンドレットを使用してまたはガイダンスについては、次の表を使用します。 
    
**暗号化のカスタマイズ オプション**

|**カスタマイズする暗号化エクスペリエンスの特性**|**これらのコマンドを使用します。**|
|:-----|:-----|
|暗号化された電子メール メッセージに付属する既定のテキスト。暗号化されたメッセージを表示するための指示の上に既定のテキストが表示されます。  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|暗号化メッセージを含む電子メールの免責文  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only."` <br/> |
|暗号化メールの表示ポータルの最上部に表示されるテキスト<br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."` <br/> |
|ロゴ  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> サポートされているファイル形式: .png、.jpg、.bmp、.tiff  <br/> ロゴ ファイルの最適なサイズ:40 KB 未満  <br/> 最適なロゴ画像のサイズ:170x70 ピクセル  <br/> |
|背景色  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -BackgroundColor "#ffffff"` <br/> |
   
**ホームで暗号化されたホーム ポータル、電子メール メッセージから、ブランドのカスタマイズを削除するのには**
  
1. [Exchange オンラインを使用してリモート PowerShell への接続](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)で説明するようリモート PowerShell を使用して Exchange Online に接続します。
    
2. [セット OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)で説明したように、セット OMEConfiguration コマンドレットを使用します。組織を削除するのには、DisclaimerText、EmailText からのカスタマイズをブランドし、PortalText の値を空の文字列値を設定する`""`。すべてのイメージ、ロゴなどの値の値を設定、 `"$null"`。
    
**暗号化のカスタマイズ オプション**

**この暗号化の機能を既定のテキストと画像に戻すには**|**これらのコマンドを使用します。**|
|:-----|:-----|
|暗号化された電子メール メッセージに付けられる既定のテキスト  <br/> 暗号化メッセージの表示手順の上に表示される既定のテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|暗号化メッセージを含む電子メールの免責文  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|暗号化メールの表示ポータルの最上部に表示されるテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **既定値に戻すの背面を例:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|ロゴ  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **既定値に戻すの背面を例:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
|背景色  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **既定値に戻すの背面を例:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null` <br/> |
   

