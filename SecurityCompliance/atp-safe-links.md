---
title: Office 365 の ATP の安全なリンク機能
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: 安全なリンク機能は、Office ドキュメントや電子メール メッセージのハイパーリンクのクリックの検証を提供します。フィッシング詐欺やその他の攻撃から組織を保護するために安全なリンクを使用します。
ms.openlocfilehash: 34e32038cd5718ca3399fc65aae11adfeb0f4ee0
ms.sourcegitcommit: f8cc2c7bad31d04c99a8eca5e0f8fad72494087a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "23848077"
---
# <a name="office-365-atp-safe-links"></a>Office 365 の ATP の安全なリンク機能

Office 365 ATP 安全なリンク (ATP の安全なリンク) ( [Office 365 ATP の安全な添付ファイル](atp-safe-attachments.md)) とは、企業向けの[Office 365 の高度な脅威保護](office-365-atp.md)の一部として提供されるセキュリティ機能のセットです。ATP の安全なリンクは、電子メール メッセージ、および Office ドキュメントの web アドレス (Url) のクリックの検証を提供することにより、組織を保護するために役立ちます。保護は、Office 365 のセキュリティ チームが設定されている[ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)によって定義されています。 
  
場所、ATP の安全なリンク ポリシーが表示されたら、Office 365 のグローバル管理者、セキュリティ管理者、およびセキュリティのリーダーことができます[脅威保護の詳細に関するレポートを表示](view-reports-for-atp.md)します。それらのレポート内の情報は、セキュリティ チームは、組織を保護するか、セキュリティ インシデントを調査するそれ以上の手順を実行できます。
  
新機能は、ATP の安全なリンクに追加されている継続的にします。
  
- 遅延 2017年 10 月以降では、ATP の安全なリンクの保護に適用する Url の Url と同様に電子メールで Word、Excel、PowerPoint、および Visio など、Office 365 用リソースのドキュメントのウィンドウ、および Office に iOS および Android デバイス上のアプリ拡張されます。
    
- 2018年 3 月で以降では、ATP の安全なリンクの保護は、組織内のユーザー間で送信される電子メールに適用する拡張されます。
    
- 2018 の後半以降では、ATP の安全なリンクの保護を拡張 (オンラインの Word、Excel のオンライン、PowerPoint オンラインでは、および OneNote オンライン) オンライン Office および Office 365 用リソース mac 上での Url に適用するには
    
- 先頭 2018年 9 月で、[警告のページを Office 365 の分析ツール](atp-safe-links-warning-pages.md)の機能、新しい配色パターン、詳細についてとにもかかわらず、サイトを続行することには、警告と推奨事項が与えられます。 
         
## <a name="how-atp-safe-links-in-email-works"></a>ATP 安全な電子メールのリンクが機能するしくみ

高レベルでは、ここでは ATP の安全なリンク保護のしくみの url (Office 365 でないオンプレミスでホストされている) 電子メール。
  
1. ユーザーには、Url が含まれているいくつかの電子メール メッセージが表示されます。
    
2. すべての電子メールを通過、インターネット プロトコル (IP) とエンベロープ、フィルター処理、Exchange のオンライン保護シグネチャ ・ ベースのマルウェアからの保護、スパム対策とマルウェア対策のフィルターが適用されます。 
    
3. 電子メールは、他のユーザーの受信トレイに到着します。
    
4. ユーザーが、Office 365 にサインインし、電子メールの受信トレイに移動します。
    
5. ユーザーは、電子メール メッセージを開くと、電子メール メッセージ内の URL をクリックします。
    
6. ATP の安全なリンク機能は、すぐに web サイトを開く前に URL をチェックします。ブロックされると、悪意のある、または安全では、URL が識別されます。
    
    - URL がユーザーに適用されるポリシーの[カスタム」を書き換えない」の Url] ボックスの一覧](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)に含まれている web サイトにある場合は、web サイトを開きます。 
    
    - 組織の[ユーザー設定のブロックされた Url のリスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)に含まれている web サイトへの URL の場合は、[警告のページ](atp-safe-links-warning-pages.md)が開きます。 
    
    - URL は、悪意があると判断された web サイトには、[警告ページ](atp-safe-links-warning-pages.md)が表示されます。 
    
    - URL がダウンロード可能なファイルに移動し、このようなコンテンツをスキャンするのには、組織の[安全なリンクの ATP のポリシー](set-up-atp-safe-links-policies.md)が構成されて、ダウンロード可能なファイルがチェックされます。 
    
    - 安全のための URL が確認された場合、web サイトを開きます。
    
## <a name="how-atp-safe-links-in-office-documents-works"></a>Office ドキュメント内の安全なリンクの ATP のしくみ

高レベルでは、ここでは ATP の安全なリンク保護のしくみの url (現在のバージョンの OneNote、Word、Excel、および PowerPoint では、Windows や Mac、iOS または Android デバイス、ウィンドウ、および Office オンライン上の Visio での Office アプリケーション) の Office 365 用リソースのアプリケーションで。
  
1. ユーザーは、コンピューター、スマート フォンやタブレットに Office 365 用リソース インストールされています。
    
2. ユーザーは、Word、Excel、PowerPoint、または Visio を開くし、Office 365 の企業、職場、学校のアカウントを使用してにサインインします。ドキュメントには、Url が含まれています。
    
3. ユーザーは、ドキュメントの URL をクリックすると、ATP の安全なリンク サービスのリンクがチェックされます。
    
  - URL は、ユーザーに適用されるポリシーの[カスタム」を書き換えない」の Url] ボックスの一覧](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)に含まれている web サイトには、web サイトにそのユーザーが取得されます。 
    
  - 組織の[ユーザー設定のブロックされた Url のリスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)に含まれている web サイトへの URL の場合は、[警告ページ](atp-safe-links-warning-pages.md)にユーザーが取得されます。
    
  - 悪意があると判断された web サイトへの URL の場合は、[警告ページ](atp-safe-links-warning-pages.md)にユーザーが取得されます。
    
  - URL がダウンロード可能なファイルに移動し、 [ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)は、このようなダウンロードをスキャンするよう構成する場合は、ダウンロード可能なファイルがチェックされます。 
    
  - URL は、安全と見なされますが、web サイトにユーザーが取得されます。
    
## <a name="how-to-get-atp-safe-links-protection"></a>ATP の安全なリンクを保護する方法

ATP の安全なリンク機能は、[脅威の高度な保護](office-365-atp.md)、Office 365 エンタープライズ E5 に含まれているの一部です。組織は、別の Office 365 エンタープライズ サブスクリプションで使用されている場合は、アドオンとして脅威の高度な保護を購入できます。詳細についてを参照してください[Office 365 のプラットフォーム サービスの説明: Office 365 のセキュリティ&amp;コンプライアンス センター](https://technet.microsoft.com/en-us/library/dn933793.aspx) [購入またはビジネスのための Office 365 のアドオンを編集](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)するとします。
  
ATP の安全なリンク機能は、次のような場合アクティブです。
  
- **ATP の安全なリンク ポリシーが設定されて**メールや Word、Excel、PowerPoint、および Visio のドキュメントです。( [Office 365 の ATP の安全なリンク ポリシーの設定](set-up-atp-safe-links-policies.md)を参照してください)。

- **現代の認証を使用する office 365 クライアント アプリケーションを構成**します。詳細については、 [Office の 2016年の最新の認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)を参照してください。 
    
- **ユーザーが Office 365 にサインインして**、職場、学校のアカウントを使用しています。(詳しくは、 [Office または Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)を参照してください)。
    
- **組織の電子メールが Office 365 でホストされている**、オンプレミスのサーバーではなく。 
    
## <a name="make-sure-atp-safe-links-protection-is-in-place"></a>ATP の安全なリンクの保護が設定されていることを確認します。

[脅威の高度な保護のためのレポートを表示する](view-reports-for-atp.md)ことでは、組織の安全なリンクの ATP の保護を使用する方法を表示する方法の 1 つ。さらに、グローバルまたはセキュリティ管理者は、 [ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)を確認することを確認します。ATP の安全なリンク ポリシーは、保護に適用するか電子メール メッセージ内のハイパーリンクまたは Url にのみ、Office ドキュメントも同様を決定します。
  
次の表では、ATP の安全なリンクの保護の可能性があります、または配置できない場合がありますいくつかのサンプル シナリオについて説明します。すべてのこれらの場合に、組織には、Office 365 エンタープライズ E5 と仮定します。
  
|**シナリオ例**|**ATP の安全なリンクの保護はここで適用しますか。**|
|:-----|:-----|
|Jean は、電子メールや Office ドキュメントの Url に対応する分析ツールの安全なリンク ポリシーのあるグループのメンバーです。ジャンはその他の PowerPoint の 2016年に送信されたプレゼンテーションを開くし、プレゼンテーションの URL をクリックします。  <br/> |うん。ジャンのグループ、ジャンの電子メール、Jean が開き、Jean がサインインしている限り、Word、Excel、PowerPoint、または Visio のドキュメントと Office 365 用リソースまたはを使用して Windows、iOS、Android のデバイスに定義されている ATP の安全なリンク ポリシーが適用されます。  <br/> |
|ないグローバル組織またはセキュリティ管理者が定義した、ATP の安全なリンク ポリシーまだ。山口さんは、悪意のある web サイトへの URL を含む電子メールを受信します。山口さんには認識されていない URL は、悪意のあるし、リンクをクリックします。  <br/> |違います。適切に保護するために組織内のすべてのユーザーに対して Url をカバーする既定のポリシーを定義する必要があります。  <br/> |
|Pat のないグローバル組織またはセキュリティ管理者が定義されているまたは ATP の安全なリンクのすべてのポリシーの編集が完了します。Pat は Word ドキュメントを開くし、ファイルの URL をクリックすると。  <br/> |Office ドキュメントが含まれます。 ポリシーは、適切に保護するために定義しなければなりません。[Office 365 の ATP の安全なリンクのポリシーの設定](set-up-atp-safe-links-policies.md)を参照してください。<br/> |
|Lee の組織には、ATP の安全なリンクを持つポリシーを`http://tailspintoys.com`ブロックされた web サイトとして表示されます。Lee の URL を含む電子メール メッセージを受信する`http://tailspintoys.com/aboutus/trythispage`。Lee では、URL をクリックします。<br/> |サイト全体とそのサブページがの一覧に含まれるすべての Url をブロックするかどうかによって異なります。[ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定する](set-up-a-custom-blocked-urls-list-wtih-atp.md)を参照してください。<br/> |
|青木さん、ジャンの仕事仲間、電子メールを送信しジャン、電子メールに悪意のある URL が含まれていることもできます。  <br/> |組織内で送信される電子メールの ATP の安全なリンクのポリシーが定義されているかどうかによって異なります。[Office 365 の ATP の安全なリンクのポリシーの設定](set-up-atp-safe-links-policies.md)を参照してください。<br/> |
   
## <a name="related-topics"></a>関連項目

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Office 365 の ATP の安全なリンクのポリシーを設定します](set-up-atp-safe-links-policies.md)
  
[ATP の安全な添付ファイルを Office 365 で](atp-safe-attachments.md)
  
[Office 365 の ATP のフィッシング詐欺対策機能](atp-anti-phishing.md)
  
[脅威の高度な保護のためのレポートを表示します。](view-reports-for-atp.md)
  

