---
title: 暗号化されたメッセージに、組織のブランドを追加します。
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
description: Exchange 管理者は、組織のブランドの組織の暗号化された電子メール メッセージや暗号化のポータルのコンテンツに適用できます。
ms.openlocfilehash: 4b22b72a8b77c2978a7cf25166978759119c272c
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696221"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>組織のブランドを暗号化されたメッセージに追加する

オンライン Exchange または Exchange のオンライン保護管理者は、会社、組織の Office 365 のメッセージの暗号化電子メール メッセージの外観および暗号化のポータルのコンテンツをカスタマイズするのにはブランド化を適用できます。Get OMEConfiguration とセット OMEConfiguration Windows PowerShell コマンドレットを使用すると、暗号化された電子メール メッセージの受信者の表示操作の次の側面をカスタマイズできます。
  
- 暗号化メッセージを含む電子メールの導入部のテキスト
- 暗号化メッセージを含む電子メールの免責事項のテキスト
- ホーム ポータルに表示されるテキスト
- ホーム ポータル、電子メール メッセージに表示されるロゴ
- ホーム ポータル、電子メール メッセージの背景色

いつでも既定のルック アンド フィールに戻すこともできます。

詳細に制御する場合は、組織から発信される、暗号化された電子メールを複数のテンプレートを作成できます。これらのテンプレートを使用すると、制御、電子メール メッセージの外観と動作だけでなくは、エンドユーザーの操作性の部分を制御できます。たとえば、このテンプレートの適用を持ち、Google や Yahoo、Microsoft アカウントを使用しているメールの宛先が Office 365 のメッセージの暗号化のポータルにサインインするのにはこれらのアカウントを使用できるかどうかを指定できます。次のようにいくつかのユース ケースを実行するためにテンプレートを使用する場合があります。

- 財務や営業など、各部門用のテンプレートです。
- 別の製品用のテンプレート
- 異なる地域や国のためのテンプレート

テンプレートを作成した後は Exchange メール フローの規則を使用して暗号化された電子メールに適用にできます。これらのテンプレートを使用して、ブランドは、すべてのメールを失効させることができます。
  
||
|:-----|
|この資料は、Office 365 のメッセージの暗号化についての記事の大規模な一連の一部です。この資料は、管理者および ITPros。だけを行う場合、暗号化されたメッセージを送受信する情報は[Office 365 メッセージの暗号化 (ホーム)](ome.md)内のアーティクルの一覧を参照してくださいし、お客様のニーズに最も適した記事を検索します。 |
||

## <a name="create-branding-templates"></a>ブランド化のテンプレートを作成します。

新規 OMEConfiguration コマンドレットを Windows PowerShell で組織のブランド化のテンプレートを作成するとします。テンプレートを作成した後は、セット OMEConfiguration コマンドレットを使用して、テンプレートの構成要素を定義します。複数のテンプレートを作成することができます。

![電子メールのカスタマイズ可能なパーツ](media/ome-template-breakout.png)
  
1. 大域管理者アクセス許可を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://aka.ms/exopowershell)を参照してください。

2. 新しいテンプレートを作成するのにには、新規 OMEConfiguration コマンドレットを使用します。
     ```powershell
     New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
     ```
     たとえば、次のように使用します。
     ```powershell
     New-OMEConfiguration -Identity <Branding template 1>
     ```
3. [セット OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)で説明したように、セット OMEConfiguration コマンドレットを使用して定義したテンプレートのカスタマイズを定義またはガイダンスについては、次の表を使用します。

|**カスタマイズする暗号化エクスペリエンスの特性**|**これらのコマンドを使用します。**|
|:-----|:-----|
|背景色  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> |
|ロゴ  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> サポートされているファイル形式: .png、.jpg、.bmp、.tiff  <br/> ロゴ ファイルの最適なサイズ:40 KB 未満  <br/> 最適なロゴ画像のサイズ:170x70 ピクセル  <br/> |
|送信者の名前と電子メール アドレスの横にあるテキスト| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|"メッセージの読み取り] ボタンに表示されるテキスト| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|上"のメッセージを開封] ボタンの下に表示されるテキスト| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|暗号化メッセージを含む電子メールの免責文  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|暗号化メールの表示ポータルの最上部に表示されるテキスト<br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."` <br/> |
|有効にするか、このユーザー設定のテンプレートの 1 回限りのパスコードを使用して認証を無効にするには| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **例:** <br/>このカスタム テンプレートのワンタイム ・ パスワードを有効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> このカスタム テンプレートのワンタイム ・ パスワードを無効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|有効にするか、このカスタム テンプレートのマイクロソフトや Google、yahoo の id を使用して認証を無効にするには| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **例:** <br/>このカスタム テンプレートのソーシャル Id を有効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> このカスタム テンプレートのソーシャル Id を無効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a>ホームで暗号化されたホーム ポータル、電子メール メッセージから、ブランドのカスタマイズを削除するのには
  
1. [Exchange Online PowerShell に接続します](https://aka.ms/exopowershell)。

2. [セット OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)で説明したように、セット OMEConfiguration コマンドレットを使用します。組織を削除するのには、DisclaimerText、EmailText からのカスタマイズをブランドし、PortalText の値を空の文字列値を設定する`""`。すべてのイメージ、ロゴなどの値の値を設定、 `"$null"`。

**暗号化のカスタマイズ オプション**

**この暗号化の機能を既定のテキストと画像に戻すには**|**これらのコマンドを使用します。**|
|:-----|:-----|
|暗号化された電子メール メッセージに付けられる既定のテキスト  <br/> 暗号化メッセージの表示手順の上に表示される既定のテキスト| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|暗号化メッセージを含む電子メールの免責文| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|暗号化メールの表示ポータルの最上部に表示されるテキスト| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **既定値に戻すの背面を例:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|ロゴ| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **既定値に戻すの背面を例:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|背景色| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **既定値に戻すの背面を例:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a>Exchange メール フロー ルールが適用されるカスタム ブランドを暗号化された電子メールを作成します。

ブランド化のテンプレートを作成した後、特定の条件に基づいて、そのカスタム ブランド化を適用する Exchange のメール フロー ルールを作成できます。カスタム ブランドの次のシナリオでこのようなルールが適用されます。

- 電子メールが Outlook または OWA クライアントからエンドユーザーが手動で暗号化されたかどうか
- 電子メールが Exchange のメール フローの規則またはポリシーを Office 365 のデータ損失の防止によって自動的に暗号化

暗号化を適用する Exchange メール フローの規則を作成する方法については、 [Office 365 で電子メール メッセージを暗号化するためにメール フロー ルールの定義](define-mail-flow-rules-to-encrypt-email.md)を参照してください。

1. Web ブラウザーで[Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)、グローバル管理者のアクセス許可が与えられている、職場、学校のアカウントを使用します。

2. **管理者**のタイルを選択します。

3. Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。

4. **メール フロー**には、EAC で\>**の規則**と**新規**作成]![新しいアイコン](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しい規則を作成します**。詳細については、EAC を使用して、 [Exchange のオンラインでの Exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)を参照してください。

5. **名**、販売部門のブランドなど、ルールの名前を入力します。

6. **場合にこのルールを適用する**条件を選択、使用可能な条件の一覧から必要なその他の条件と同様に **、送信者が組織内にある**条件を選択します。などの特定のブランドにテンプレートを適用します。

     - 財務部門のメンバーから送信される e メールはすべて暗号化
     - 「外部」または「パートナー」などの特定のキーワードを使用して送信される暗号化された e メール
     - 暗号化された電子メールを特定のドメインに送信されます。

7. **次の操作**をには、**メッセージ セキュリティの変更**] を選択 > **ブランド ホームのメッセージを指定して適用**します。次に、ドロップダウン リストからは、ブランド化のテンプレートから作成したものを選択します。
8. (省略可能)メール フロー ルールもだけでなく、カスタムの暗号化を適用する場合から **、次の操作**をには、ブランド、**メッセージ セキュリティの変更**] を選択し、**適用 Office 365 のメッセージの暗号化と権限保護**します。RMS テンプレートを一覧から選択、**保存**を選択し、[ **ok]** します。
  
     テンプレートの一覧には、すべての既定のテンプレートが含まれていて、オプションと同様に作成したカスタム テンプレートを Office 365 で使用します。リストが空の場合は、設定することが Office 365 のメッセージの暗号化を新しい機能を備えた[新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)の説明に従ってを確認します。既定のテンプレートの詳細については、[構成して Azure の情報保護のためのテンプレートを管理する](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)を参照してください。[**転送不可**] オプションの詳細については、[電子メールの転送不可] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を参照してください。**のみ暗号化**オプションの詳細については、[電子メールの暗号化のみ] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)を参照してください。

     別のアクションを指定する場合は、**アクションを追加する**選択できます。
