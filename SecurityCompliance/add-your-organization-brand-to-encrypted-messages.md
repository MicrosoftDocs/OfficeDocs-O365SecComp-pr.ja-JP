---
title: 暗号化されたメッセージに組織ブランドを追加する
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Office 365 のグローバル管理者は、組織の暗号化された電子メールメッセージと暗号化ポータルの内容に組織のブランド化を適用することができます。
ms.openlocfilehash: 19f227971c522f9d92aec343f1865ab7f23c13aa
ms.sourcegitcommit: b0ea2d66bc4c7f2fc0a8abab28d2ae652b1c4b73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2019
ms.locfileid: "34721374"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>暗号化されたメッセージに組織のブランドを追加する

Exchange Online または Exchange Online Protection 管理者は、企業ブランドを適用して、組織の Office 365 メッセージ暗号化の電子メールメッセージと暗号化ポータルの内容の外観をカスタマイズできます。 取得した、暗号化された電子メールメッセージの受信者については、次のように、Windows PowerShell コマンドレットを使用して、以下の点をカスタマイズできます。
  
- 暗号化メッセージを含む電子メールの導入部のテキスト

- 暗号化メッセージを含む電子メールの免責事項のテキスト

- OME ポータルに表示されるテキスト

- 電子メールメッセージと OME ポータルに表示されるロゴ

- 電子メールメッセージと OME ポータルの背景色

いつでも既定のルック アンド フィールに戻すこともできます。

 より詳細な制御を希望する場合は、Office 365 Advanced Message Encryption を使用して、組織から送信される暗号化電子メール用に複数のテンプレートを作成することができます。 これらのテンプレートを使用すると、電子メールメッセージの外観だけでなく、エンドユーザーの操作性の部分を制御することもできます。 たとえば、このテンプレートが適用されたメールの受信者と、Google、Yahoo、および Microsoft アカウントを使用して、Office 365 メッセージ暗号化ポータルにサインインできるようにするユーザーを指定することができます。 テンプレートを使用して、次のようないくつかのユースケースを満たすことができます。

- 各部門のテンプレート (Finance、Sales など)

- さまざまな製品のテンプレート

- さまざまな地域または国のテンプレート

- 電子メールの失効を許可するかどうか

- 指定した日数が経過した後に、外部の受信者に送信される電子メールの有効期限を指定するかどうか。

テンプレートを作成したら、Exchange メールフロールールを使用して暗号化された電子メールにそれらを適用することができます。 Office 365 の高度なメッセージ暗号化を使用している場合は、これらのテンプレートを使用して、ブランド化されたすべての電子メールを取り消すことができます。
  
||
|:-----|
|この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。 この記事は、管理者および It 担当者を対象としています。 暗号化されたメッセージの送信または受信に関する情報をお探しの場合は、「 [Office 365 Message Encryption (OME)](ome.md) 」の記事の一覧を参照し、ニーズに最も適した記事を見つけてください。|
||

## <a name="create-branding-templates"></a>ブランド設定テンプレートを作成する

Windows PowerShell で組織のブランド化テンプレートを作成するには、新しい/OMEConfiguration コマンドレットを使用します。 テンプレートを作成したら、そのテンプレートの部分を定義します。このためには、コマンドレットを使用します。 複数のテンプレートを作成できます。

![カスタマイズ可能な電子メールパーツ](media/ome-template-breakout.png)
  
1. Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。 手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。

2. 新しいテンプレートを作成するには、新しい-OMEConfiguration コマンドレットを使用します。

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```

   For example,

   ```powershell
   New-OMEConfiguration -Identity "Branding template 1"
   ```

3. 定義したテンプレートのカスタマイズを定義するには、「OMEConfiguration 設定」で説明さ[](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)れているように、このコマンドレットを使用するか、または次の表を参考にしてください。

|**カスタマイズする暗号化エクスペリエンスの特性**|**使用するコマンド**|
|:-----|:-----|
|背景色|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|ロゴ|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> サポートされているファイル形式: .png、.jpg、.bmp、.tiff  <br/> ロゴ ファイルの最適なサイズ:40 KB 未満  <br/> 最適なロゴ画像のサイズ:170x70 ピクセル|
|送信者の名前と電子メールアドレスの横のテキスト|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|[メッセージの読み取り] ボタンに表示されるテキスト|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|[メッセージの読み取り] ボタンの下に表示されるテキスト|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|暗号化メッセージを含む電子メールの免責文|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|暗号化メールの表示ポータルの最上部に表示されるテキスト|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|このカスタムテンプレートのワンタイムパスコードで認証を有効または無効にするには|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **例:** <br/>このカスタムテンプレートで1回限りのパスコードを有効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> このカスタムテンプレートで1回限りのパスコードを無効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|このカスタムテンプレートの Microsoft、Google、または Yahoo の id による認証を有効または無効にするには|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **例:** <br/>このカスタムテンプレートのソーシャル Id を有効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> このカスタムテンプレートのソーシャル Id を無効にするには <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a>OME ポータルおよび OME で暗号化された電子メールメッセージからブランド化のカスタマイズを削除するには
  
1. [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)。

2. Set- **** omeconfiguration コマンドレットを使用します[](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)。 組織のブランド化されたカスタマイズを DisclaimerText、EmailText、および PortalText の値から削除するには、値を`""`空の文字列に設定します。 ロゴなどのすべてのイメージ値について、値を`"$null"`に設定します。

**暗号化のカスタマイズ オプション**

**この暗号化の機能を既定のテキストと画像に戻すには**|**使用するコマンド**|
|:-----|:-----|
|暗号化された電子メール メッセージに付けられる既定のテキスト  <br/> 暗号化メッセージの表示手順の上に表示される既定のテキスト|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|暗号化メッセージを含む電子メールの免責文|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **例:**  <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|暗号化メールの表示ポータルの最上部に表示されるテキスト|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **既定値に戻す例:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
|ロゴ|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **既定値に戻す例:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|背景色|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **既定値に戻す例:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a>暗号化された電子メールにカスタムブランド化を適用する Exchange メールフロールールを作成する

ブランド設定テンプレートを作成したら、Exchange メールフロールールを作成して、特定の条件に基づいてそのカスタムブランド化を適用できます。 このようなルールは、次のシナリオでカスタムブランド化を適用します。

- 電子メールが、Outlook または web 上の outlook (旧称 Outlook Web App) クライアントからエンドユーザーによって手動で暗号化されている場合

- 電子メールが Exchange メールフロールールまたは Office 365 データ損失防止ポリシーによって自動的に暗号化された場合

暗号化を適用する Exchange メールフロールールを作成する方法については、「 [Office 365 で電子メールメッセージを暗号化するためのメールフロールールの定義](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。

2. [**管理**] タイルを選択します。

3. Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。

4. EAC で、[**メールフロー** \> ] [**ルール**] に**** ![移動し、](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> [新しい新規作成] アイコンを選択して**新しいルールを作成**します。 EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。

5. [**名前**] に、[営業部門のブランド化] など、ルールの名前を入力します。

6. [条件を選択する**場合、このルールを適用**する] で、**送信者が組織内に配置さ**れている条件と、使用可能な条件の一覧からその他の条件を選択します。 たとえば、特定のブランド化テンプレートを次のように適用することができます。

     - 財務部門のメンバーから送信されるすべての暗号化された電子メール
     - 「外部」や「パートナー」などの特定のキーワードで暗号化された電子メール
     - 特定のドメインに送信される暗号化された電子メール

7. [**実行する処理] 次**に、[**メッセージセキュリティ** > を変更します] を選択して、**OME メッセージにカスタムブランドを適用**します。 次に、ドロップダウンから、作成したブランド化テンプレートを選択します。

8. オプションカスタムブランド化に加えて、メールフロールールが暗号化も適用するようにするには、**次の操作を行い**ます。次に、[**メッセージのセキュリティを変更**する] を選択し、[ **Office 365 メッセージの暗号化と権限保護を適用**する] を選択します。 一覧から RMS テンプレートを選択し、[**保存**] を選択して、[ **OK]** を選択します。
  
     テンプレートの一覧には、既定のテンプレートとオプションのすべてに加えて、Office 365 で使用するために作成したカスタムテンプレートがすべて含まれています。 リストが空の場合は、「office の[365 新しいメッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」の説明に従って、Office 365 メッセージの暗号化を新しい機能で設定していることを確認してください。 既定のテンプレートの詳細については、「 [Azure Information Protection 用のテンプレートを構成および管理](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)する」を参照してください。 [**転送**しない] オプションの詳細については、「[メールの転送オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を送信しない」を参照してください。 [**暗号化のみ**] オプションの詳細については、「[電子メールの暗号化のみオプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)」を参照してください。

     別のアクションを指定する場合は、[**アクションの追加**] を選択できます。
