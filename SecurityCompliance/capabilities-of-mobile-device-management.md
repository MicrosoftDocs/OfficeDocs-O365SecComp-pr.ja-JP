---
title: Office 365 用の組み込みモバイル デバイス管理の機能
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/11/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.DevicePolicySupportedDevice
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: a1da44e5-7475-4992-be91-9ccec25905b0
description: Office 365 でモバイル デバイスの管理は、セキュリティで保護し、iPhones、台もの Ipad、Androids、および組織で使用されている Windows の電話のようにモバイル デバイスを管理するのに役立ちます。コントロールは、組織の Office 365 の電子メールおよびサポートされているモバイル デバイスとアプリケーションについてのドキュメントへのアクセスし、盗まれた場合、デバイスをリモートでワイプすることができる設定を使用してモバイル デバイス管理ポリシーを作成します。
ms.openlocfilehash: b7200eee3b50c2fc6d3e0ea0920236d71837a88b
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272602"
---
# <a name="capabilities-of-built-in-mobile-device-management-for-office-365"></a>Office 365 用の組み込みモバイル デバイス管理の機能

Office 365 でモバイル デバイスの管理は、セキュリティで保護し、iPhones、台もの Ipad、Androids、およびライセンスの Office 365 ユーザーが組織内で使用されている Windows の電話のようにモバイル デバイスを管理するのに役立ちます。組織の Office 365 の電子メールおよびサポートされているモバイル デバイスやアプリケーションのドキュメントにアクセスを制御するのに役立つ設定を使用して、モバイル デバイス管理ポリシーを作成できます。デバイスが紛失または盗難に遭った場合は、組織の機密情報を削除するのにはデバイスをリモートでワイプできます。
    
Office 365 の MDM に含まれているよりもより多くの機能が必要ですか。マイクロソフト Intune には必要なかどうかを参照してください: [MDM Intune の Microsoft Office 365 の間で選択](choose-between-mdm-and-intune.md)します。
  
## <a name="supported-devices"></a>サポート対象のデバイス

Office 365 の MDM を使用するにはセキュリティで保護し、次の種類のデバイスを管理します。
  
- Windows Phone 8.1 +
    
- iOS 7.1 以降のバージョン
    
- Android 4 以降のバージョン
    
- Windows 8.1\*
    
- Windows 8.1 RT\*
    
- Windows 10\*\*
    
- Windows 10 Mobile\*\*
    
\*Windows 8.1 および Windows 8.1 RT デバイスのアクセス制御は、Exchange ActiveSync に制限されます。
  
\*\*Azure Active Directory に参加し、組織のモバイル デバイス管理サービスに登録するデバイスが必要です。
  
組織内のユーザーには、Office 365 でモバイル デバイスの管理がサポートされていないモバイル デバイスが使用する場合は、組織のデータのセキュリティを強化するのには、それらのデバイスを Office 365 の電子メールを Exchange ActiveSync アプリケーションのアクセスをブロックします。Exchange ActiveSync をブロックするための手順:[デバイスのアクセス設定の管理](manage-device-access-settings.md)を参照してください。
  
## <a name="access-control-for-office-365-email-and-documents"></a>Office 365 の電子メールとドキュメントのアクセス制御

次の表に、モバイル デバイスのさまざまな種類のサポートされているアプリケーションは、ユーザーに登録しているユーザーのデバイスに適用する新しいモバイル デバイス管理ポリシーがあるし、ユーザーがデバイスを登録していない以前の Office 365 の MDM を求められます。ユーザーのデバイスは、ポリシーに準拠しないをポリシーを設定する方法によって、ユーザーがブロックされているこれらのアプリケーションで Office 365 のリソースにアクセスするまたはアクセスする必要がありますが Office 365 では、ポリシー違反を報告します。
  
||**Windows Phone 8.1 +**|**iOS 7.1 以降**|**Android 4 以降**|
|:-----|:-----|:-----|:-----|
|**Exchange** <br/> Exchange ActiveSync には、組み込みの電子メールおよび 14.1 またはそれ以降の Exchange ActiveSync のバージョンを使用する、接地時のようなのサード ・ パーティ製アプリケーションが含まれています。  <br/> |![[Exchange ActiveSync] アイコン](media/b36e36ba-88a5-4b2e-bd1d-7432b751a60c.png)Exchange ActiveSync  <br/> ![[Exchange Mail mobile] アイコン](media/5b5312b4-3bfb-4fc7-84ff-d7ab21227c10.png)Exchange Mail  <br/> |![[Exchange ActiveSync] アイコン](media/b36e36ba-88a5-4b2e-bd1d-7432b751a60c.png)Exchange ActiveSync  <br/> ![iPhone の [Mail mobile] アイコン](media/888bdc7a-8354-4013-a0b2-0d4432a9a92e.png)Mail  <br/> |![[Exchange ActiveSync] アイコン](media/b36e36ba-88a5-4b2e-bd1d-7432b751a60c.png)Exchange ActiveSync  <br/> ![Android の [電子メール] アイコン](media/20b48492-4adc-40ce-99cf-1b47bd2b389d.png)電子メール  <br/> |
|**Office** および **OneDrive for Business** <br/> |アプリのサポートなし  <br/> |![iPhone の [Outlook mobile] アイコン](media/6c63112d-c10c-4040-85cc-feeccc3dd424.png)Outlook  <br/> ![iPhone の [OneDrive mobile] アイコン](media/560ec187-82d9-4793-b72f-7ba595972bdc.png)OneDrive  <br/> ![iPhone の [Word mobile] アイコン](media/63a3a749-1f98-402f-b211-e46b9224b655.png)Word  <br/> ![iPhone の [Excel mobile] アイコン](media/5b8f62c0-96aa-4602-9ed8-f837bbf5fa9e.png)Excel  <br/> ![iPhone の [PowerPoint mobile] アイコン](media/17c02dca-f60a-4d13-a610-00d576a40943.png)PowerPoint  <br/> |**携帯電話とタブレットで:** <br/> ![電話とタブレットの android Outlook のモバイル アイコン](media/ed2a813d-f481-46e0-acc9-6422f0d16072.png)Outlook  <br/> ![Android の電話 OneDrive モバイル アイコン](media/64855d02-1684-4795-b4c5-863860f18722.png)OneDrive  <br/> ![Android の Word のモバイル アイコン](media/f618fe83-b163-4680-b924-fcedc06ab4ba.png)ワード  <br/> ![Android の Excel のモバイル アイコン](media/659c7a5f-5797-4b47-a776-4a0c8f784c89.png)Excel  <br/> ![PowerPoint の android モバイル アイコン](media/35b98bce-d7cb-40ce-87e3-07b9764207b1.png)PowerPoint  <br/> **電話のみ:** <br/> ![Office のモバイル モバイル アイコン](media/1aa9e978-6eb2-40aa-82da-62fb79cee313.png)Office のモバイル  <br/> |
   
> [!NOTE]
>  IOS 7.1 およびそれ以降のバージョンのサポートには、iPhone と iPad のデバイスが含まれています。> BlackBerry デバイスの管理は、Office 365 のモバイル デバイスの管理がサポートされていません。BlackBerry から BlackBerry ビジネス クラウド サービス (BBCS) を使用すると、BlackBerry デバイスを管理できます。> ユーザーは、登録しはありませんがブロックされたり、Office online では、ドキュメントまたは電子メールを Outlook Web App で、Office 365 の SharePoint サイトにアクセスするモバイル ブラウザーを使用する場合、ポリシー違反を報告する求められるはありません。 
  
サポートが Office 365 の MDM を持つコントロールをアクセスするアプリケーションを新しいデバイスにユーザーがサインインするときの動作を次の図に示します。ユーザーがデバイスを登録するまでアプリケーションでは、Office 365 リソースへのアクセスがブロックされます。
  
![新しいデバイスの登録処理を示します。](media/O365-MDM-Capabilities-EnrollmentExample.png)
  
> [!NOTE]
> ポリシーおよび Office 365 の MDM で作成したアクセス ルールは、Exchange ActiveSync モバイル デバイス メールボックス ポリシーと Exchange 管理センターで作成されたデバイス アクセスのルールをオーバーライドします。デバイスが Exchange ActiveSync モバイル デバイス メールボックス ポリシーを使用すると、Office 365 の MDM に登録されているか、デバイスに適用するデバイス アクセス ルールは無視されます。Exchange ActiveSync の詳細については、 [Exchange のオンラインでの Exchange ActiveSync](https://go.microsoft.com/fwlink/p/?LinkId=524380)を参照してください。 
  
## <a name="policy-settings-for-mobile-devices"></a>モバイル デバイス用のポリシー設定

有効になっている特定の設定を使用してアクセスをブロックするポリシーを作成する場合は、 [Office 365 の電子メールとドキュメントのアクセス制御](#access-control-for-office-365-email-and-documents)に記載されているサポートされているアプリケーションを使用すると、Office 365 のリソースにアクセスするユーザーがブロックされます。これらのセクションには、設定をユーザーが Office 365 リソースへのアクセスをブロックすることができます。
  
- セキュリティ
    
- 暗号化
    
- 脱獄
    
- 管理された電子メール プロファイル
    
たとえば、次の図では、場合がありますが登録されているデバイスを持つユーザーがデバイスに適用されるモバイル デバイス管理ポリシー内のセキュリティ設定に準拠して動作を示しています。サポートが Office 365 の MDM を持つコントロールをアクセスするアプリケーション、ユーザーに署名します。デバイスは、セキュリティの設定に準拠するまで、アプリケーションで Office 365 のリソースへのアクセスをブロックされています。
  
![デバイスが適合していない場合にユーザーがブロックされることを示します。](media/O365-MDM-Capabilities-ComplianceExample.png)
  
次のセクションでは、ポリシー設定をセキュリティ保護し、組織の Office 365 のリソースに接続するモバイル デバイスを管理するに使用することができますを一覧表示します。 
  
### <a name="security-settings"></a>セキュリティ設定

|**設定名**|**Windows Phone 8.1 +**|**iOS 7.1 以降**|**Android 4 以降**|**Samsung 連盟ノックス ・**|
|:-----|:-----|:-----|:-----|:-----|
|パスワードを要求  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|シンプルなパスワードを禁止  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|英数字のパスワードを要求  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|パスワードの最小文字数  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|デバイスがワイプされるまでのサインイン失敗回数  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|デバイスがロックされるまでのアイドル時間 (分)  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|パスワードの有効期限 (日)  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|パスワードの履歴を記憶して再利用を防止  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
   
### <a name="encryption-settings"></a>暗号化の設定

|**設定名**|**Windows Phone 8.1 +**|**iOS 7.1 以降**|**Android 4 以降**|**Samsung 連盟ノックス ・**|
|:-----|:-----|:-----|:-----|:-----|
|デバイス上のデータの暗号化を要求  <br/> |Windows Phone 8.1 は既に暗号化されており、非暗号化することはできません。  <br/> |✖  <br/> |✔  <br/> |✔\*  <br/> |
   
\*Samsung 連盟ノックス ・でストレージ カードの暗号化を要求することもできます。
  
### <a name="jail-broken-setting"></a>脱獄の設定

|**設定名**|**Windows Phone 8.1 +**|**iOS 7.1 以降**|**Android 4 以降**|**Samsung 連盟ノックス ・**|
|:-----|:-----|:-----|:-----|:-----|
|デバイスの脱獄またはルート化はできません  <br/> |✖  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
   
### <a name="managed-email-profile-option"></a>管理された電子メール プロファイルのオプション

次のオプションは、ユーザーが手動で作成したメール プロファイルを使用している場合、Office 365 の電子メールへのアクセスをブロックできます。自分の電子メールにアクセスする前に、iOS デバイス上のユーザーは、手動で作成したメール プロファイルを削除する必要があります。プロファイルを削除した後、デバイスに新しいプロファイルを自動的に作成されます。
  
|**設定名**|**Windows Phone 8.1 +**|**iOS 7.1 以降**|**Android 4 以降**|**Samsung 連盟ノックス ・**|
|:-----|:-----|:-----|:-----|:-----|
|電子メール プロファイルを管理  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
   
### <a name="cloud-settings"></a>クラウドの設定

|**設定名**|**Windows Phone 8.1 +**|**iOS 7.1 以降**|**Android 4 以降**|**Samsung 連盟ノックス ・**|
|:-----|:-----|:-----|:-----|:-----|
|暗号化されたバックアップが必要  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|クラウド バックアップの禁止  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|ドキュメントの同期の禁止  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|写真の同期の禁止  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|Google のバックアップを許可します。  <br/> |該当なし  <br/> |該当なし  <br/> |✖  <br/> |✔  <br/> |
|Google アカウントの自動同期を許可します。  <br/> |該当なし  <br/> |該当なし  <br/> |✖  <br/> |✔  <br/> |
   
### <a name="system-settings"></a>システムの設定

|**設定名**|**Windows Phone 8.1 +**|**iOS 7.1 以降**|**Android 4 以降**|**Samsung 連盟ノックス ・**|
|:-----|:-----|:-----|:-----|:-----|
|画面キャプチャの禁止  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✔  <br/> |
|デバイスからの診断データ送信の禁止  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✔  <br/> |
   
### <a name="application-settings"></a>アプリケーションの設定

|**設定名**|**Windows Phone 8.1 +**|**iOS 7.1 以降**|**Android 4 以降**|**Samsung 連盟ノックス ・**|
|:-----|:-----|:-----|:-----|:-----|
|デバイスでのビデオ会議をブロックする  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|アプリケーション ストアへのアクセスをブロックする  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✔  <br/> |
|アプリケーション ストアにアクセスするときにパスワードを要求  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
   
### <a name="device-capabilities-settings"></a>デバイスの機能の設定

|**設定名**|**Windows Phone 8.1 +**|**iOS 7.1 以降**|**Android 4 以降**|**Samsung 連盟ノックス ・**|
|:-----|:-----|:-----|:-----|:-----|
|リムーバブル ストレージとの接続の禁止  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |
|Bluetooth 接続の禁止  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |
   
### <a name="additional-settings"></a>その他の設定

PowerShell コマンドレットを使用して、次の追加のポリシー設定を設定できます。詳細についてを参照してください[Office 365 のセキュリティ&amp;コンプライアンス センター コマンドレット](https://go.microsoft.com/fwlink/p/?LinkId=827804)。
  
|**設定名**|**Windows Phone 8.1 +**|**iOS 7.1 以降**|**Android 4 + (Samsung 連盟ノックス ・を含む)**|
|:-----|:-----|:-----|:-----|
|CameraEnabled  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|RegionRatings  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|MoviesRatings  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|TVShowsRating  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AppsRatings  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowVoiceDialing  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowVoiceAssistant  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowAssistantWhileLocked  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowPassbookWhileLocked  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|MaxPasswordGracePeriod  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|PasswordQuality  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |
|SystemSecurityTLS  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|WLANEnabled  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
   
### <a name="settings-supported-by-windows"></a>Windows でサポートされている設定

Windows 8.1 および 10 の Windows のデバイスを管理するには、モバイル デバイスとして登録すること。適用可能なポリシーが配置されると、Windows 8.1 の RT と 10 RT の Windows のデバイスを持つユーザーを Office 365 の組み込みの電子メール アプリケーションを使用して、Office 365 の電子メールにアクセスするのには、最初に MDM に登録する必要があります。 
  
モバイル デバイスとして登録されている Windows 8.1 および Windows の 10 のデバイスは、次の設定がサポートされています。ユーザーが Office 365 リソースへのアクセスをブロック、これらの設定はありません。
  
 **セキュリティの設定**
  
- 英数字のパスワードを要求
    
- パスワードの最小文字数
    
- デバイスがワイプされるまでのサインイン失敗回数
    
- デバイスがロックされるまでのアイドル時間 (分)
    
- パスワードの有効期限 (日)
    
- パスワードの履歴を記憶して再利用を防止
    
 **システムの設定**
  
デバイスからの診断データ送信の禁止
  
 **その他の設定**
  
PowerShell コマンドレットを使用して、次のようなポリシー設定もできます。
  
- AllowConvenienceLogon
    
- UserAccountControlStatus
    
- FirewallStatus
    
- AutoUpdateStatus
    
- AntiVirusStatus
    
- AntiVirusSignatureStatus
    
- SmartScreenEnabled
    
- WorkFoldersSyncUrl
    
## <a name="remotely-wipe-a-mobile-device"></a>モバイル デバイスをリモートからワイプする

 デバイスが紛失または盗難に遭った場合は、組織の機密データを削除し、**セキュリティから、クリーン インストールの手順に従って、組織の Office 365 のリソースにアクセスを防ぐため&amp;コンプライアンス センター\>データの損失防止\>デバイス管理**です。組織のデータのみを削除するのには選択的なワイプ、またはデバイスからすべての情報を削除し、工場出荷時設定に戻すことを完全にクリーン インストールを行うことができます。
  
詳細については、 [Office 365 でモバイル デバイスをワイプする](https://go.microsoft.com/fwlink/p/?LinkId=518157)を参照してください。
  
## <a name="see-also"></a>関連項目

[Office 365 用のモバイル デバイス管理の概要](overview-of-mdm.md)
  
[デバイス セキュリティ ポリシーを作成して展開する](create-device-security-policies.md)

