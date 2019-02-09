---
title: Office 365 の ATP の安全なリンク機能
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 02/05/2019
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
ms.openlocfilehash: 8c63de9e62e33dbca6dde5a5bb45a7f7875ab71f
ms.sourcegitcommit: c1c41744c2de89c9e172f817c8f73bb0ada81a58
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792242"
---
# <a name="office-365-atp-safe-links"></a>Office 365 の ATP の安全なリンク機能

## <a name="overview-of-office-365-atp-safe-links"></a>ATP の安全なリンクを Office 365 の概要

> [!IMPORTANT]
> この資料は、ビジネスのお客様向けです。ホーム ユーザーが Outlook での安全なリンクに関する情報を検索する場合は、 [Outlook.com の高度なセキュリティ](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)を参照してください。

Office 365 ATP の安全なリンク ([高度な脅威保護](office-365-atp.md)の一部) は、[電子メール メッセージ](#how-atp-safe-links-works-with-email)および[Office ドキュメント](#how-atp-safe-links-works-with-office-documents)内の web アドレス (Url) のクリックの検証を提供することにより、組織を保護するために役立ちます。保護は、Office 365 のセキュリティ チームが設定されている[ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)によって定義されています。 
  
場所、ATP の安全なリンク ポリシーが表示されたら、Office 365 のグローバル管理者、セキュリティ管理者、およびセキュリティのリーダーことができます[脅威保護の詳細に関するレポートを表示](view-reports-for-atp.md)します。それらのレポート内の情報は、セキュリティ チームは、組織を保護するか、セキュリティ インシデントを調査するそれ以上の手順を実行できます。

として[分析ツールに新機能が追加されます](office-365-atp.md#new-features-are-continually-being-added-to-atp)が、Office 365 のセキュリティ チームを追加したり、組織の安全なリンクの ATP のポリシーを編集します。さらに、変更し、新しく変更された[ページの警告](atp-safe-links-warning-pages.md)とネイティブのリンクを Outlook でのレンダリングなどの機能強化がわかります可能性があります。
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>Url を電子メールで ATP の安全なリンクの動作

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
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Url を持つ Office ドキュメントで ATP の安全なリンクの動作

高レベルでは、ここでは Url の Office 365 用リソースのアプリケーション (Word、Excel、および PowerPoint では、Windows や Mac、iOS または Android デバイス、Windows、OneNote オンライン、および Office オンライン上の Visio での Office アプリケーションの現在のバージョン) で ATP の安全なリンクの保護の動作します。
  
1. ユーザーは、コンピューター、スマート フォンやタブレットに Office 365 用リソース インストールされています。(または、使用している Office オンラインのブラウザーで)。
    
2. ユーザーは、Word、Excel、PowerPoint、または Visio を開くし、Office 365 の企業、職場、学校のアカウントを使用してにサインインします。ドキュメントには、Url が含まれています。
    
3. ユーザーは、ドキュメントの URL をクリックすると、ATP の安全なリンク サービスのリンクがチェックされます。
    
  - URL は、ユーザーに適用されるポリシーの[カスタム」を書き換えない」の Url] ボックスの一覧](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)に含まれている web サイトには、web サイトにそのユーザーが取得されます。 
    
  - 組織の[ユーザー設定のブロックされた Url のリスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)に含まれている web サイトへの URL の場合は、[警告ページ](atp-safe-links-warning-pages.md)にユーザーが取得されます。
    
  - 悪意があると判断された web サイトへの URL の場合は、[警告ページ](atp-safe-links-warning-pages.md)にユーザーが取得されます。
    
  - URL がダウンロード可能なファイルに移動し、 [ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)は、このようなダウンロードをスキャンするよう構成する場合は、ダウンロード可能なファイルがチェックされます。 
    
  - URL は、安全と見なされますが、web サイトにユーザーが取得されます。

## <a name="how-to-get-atp-safe-links-protection"></a>ATP の安全なリンクを保護する方法

最初に、お申し込みの[脅威保護の高度な](office-365-atp.md)内容を確認します。ATP は、 [365 企業の Microsoft](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 ビジネス](https://www.microsoft.com/microsoft-365/business)、Office 365 エンタープライズ E5、Office 365 の教育 A5 など、サブスクリプションに含まれます。組織が Office 365 の分析ツールが含まれていない Office 365 のサブスクリプションの場合は、アドオンとして可能性のある ATP を購入できます。詳細については、 [Office 365 の高度な脅威保護の計画と価格設定](https://products.office.com/exchange/advance-threat-protection)と[Office 365 高度な脅威保護サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)を参照してください。 
  
次に、ATP の安全なリンク ポリシーが定義されているを確認します。( [Office 365 の ATP の安全なリンクのポリシーの設定](set-up-atp-safe-links-policies.md)を参照してください)。ATP の安全なリンク機能は、次のような場合アクティブです。
  
- **ATP の安全なリンク ポリシーが設定されて**メールや Word、Excel、PowerPoint、および Visio のドキュメントです。( [Office 365 の ATP の安全なリンク ポリシーの設定](set-up-atp-safe-links-policies.md)を参照してください)。

- **現代の認証を使用する office 365 クライアント アプリケーションが構成されています。**(これは、Office ドキュメント内の ATP の安全なリンクの保護のため)。( [2016 の Office の最新の認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)を参照してください)。 
    
- **ユーザーが Office 365 にサインインして**、職場、学校のアカウントを使用しています。(詳しくは、 [Office または Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)を参照してください)。
    
- **組織の電子メールが Office 365 でホストされている**。 

ATP のポリシーを定義 (または編集) を割り当てる必要があります、次の表に記載されている役割のいずれか。

|役割  |場所と方法が割り当てられています。  |
|---------|---------|
|Office 365 のグローバル管理者 |Office 365 を購入するのに署名した人は、既定でグローバル管理者です。( [Office 365 の管理者の役割](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)の詳細についてを参照してください)。         |
|セキュリティ管理者 |Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange オンライン組織の管理 |Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  PowerShell コマンドレット (を参照してください[Exchange オンライン PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>配置では、ATP の安全なリンクのことを確認して保護する方法です。

グローバル管理者またはセキュリティ管理者は、必ず、 [ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)を確認してください。ATP の安全なリンク ポリシーは、保護に適用するか電子メール メッセージ内のハイパーリンクまたは Url にのみ、Office ドキュメントも同様を決定します。

ATP の安全なリンクのポリシーがあると、組織のセキュリティ チームを確認できます ATP の安全なリンクの保護が動作している組織は[高度な脅威保護のためのレポートの表示](view-reports-for-atp.md)の方法を参照してください。 

## <a name="example-scenarios"></a>シナリオ例
  
次の表では、ATP の安全なリンクの保護の可能性があります、または配置できない場合がありますいくつかのサンプル シナリオについて説明します。(すべてのこれらの場合にと仮定した組織には、Office 365 エンタープライズ E5。)
  
|**シナリオ例**|**ATP の安全なリンクの保護はここで適用しますか。**|
|:-----|:-----|
|Jean は、電子メールや Office ドキュメントの Url に対応する分析ツールの安全なリンク ポリシーのあるグループのメンバーです。ジャンはその他の送信されると、PowerPoint プレゼンテーションを開くし、プレゼンテーションの URL をクリックします。  <br/> |うん。ジャンのグループ、ジャンの電子メール、Jean が開き、Jean がサインインしている限り、Word、Excel、PowerPoint、または Visio のドキュメントと Office 365 用リソースまたはを使用して Windows、iOS、Android のデバイスに定義されている ATP の安全なリンク ポリシーが適用されます。  <br/> |
|ないグローバル組織またはセキュリティ管理者が定義した、ATP の安全なリンク ポリシーまだ。山口さんは、悪意のある web サイトへの URL を含む電子メールを受信します。山口さんには認識されていない URL は、悪意のあるし、リンクをクリックします。  <br/> |違います。適切に保護するために組織内のすべてのユーザーに対して Url をカバーする既定のポリシーを定義する必要があります。  <br/> |
|Pat のないグローバル組織またはセキュリティ管理者が定義されているまたは ATP の安全なリンクのすべてのポリシーの編集が完了します。Pat は Word ドキュメントを開くし、ファイルの URL をクリックすると。  <br/> |Office ドキュメントが含まれます。 ポリシーは、適切に保護するために定義しなければなりません。[Office 365 の ATP の安全なリンクのポリシーの設定](set-up-atp-safe-links-policies.md)を参照してください。<br/> |
|Lee の組織には、ATP の安全なリンクを持つポリシーを`http://tailspintoys.com`ブロックされた web サイトとして表示されます。Lee の URL を含む電子メール メッセージを受信する`http://tailspintoys.com/aboutus/trythispage`。Lee では、URL をクリックします。<br/> |サイト全体とそのサブページがの一覧に含まれるすべての Url をブロックするかどうかによって異なります。[ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定する](set-up-a-custom-blocked-urls-list-wtih-atp.md)を参照してください。<br/> |
|青木さん、ジャンの仕事仲間、電子メールを送信しジャン、電子メールに悪意のある URL が含まれていることもできます。  <br/> |組織内で送信される電子メールの ATP の安全なリンクのポリシーが定義されているかどうかによって異なります。[Office 365 の ATP の安全なリンクのポリシーの設定](set-up-atp-safe-links-policies.md)を参照してください。<br/> |


  

