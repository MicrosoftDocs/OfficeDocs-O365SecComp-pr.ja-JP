---
title: Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/04/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: 高度な脅威保護 office 365 にはには、なりすましのインテリジェンス、安全なリンク、安全な添付ファイル、および高度なフィッシング対策機能が含まれています。脅威の高度な保護も拡張されている SharePoint のオンライン、OneDrive 内のファイルにビジネス、およびマイクロソフトのチームです。
ms.openlocfilehash: 7d60ac9bff108a6746a5e89d05d70bba23d2671d
ms.sourcegitcommit: a64af0ebd0b03e4a5e60a33e9108c44c7d74f356
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2019
ms.locfileid: "29741040"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

## <a name="overview-of-office-365-advanced-threat-protection"></a>Office 365 の高度な脅威保護の概要

Office 365 の高度な脅威保護 (ATP) は、悪意のある攻撃から組織を保護するために役立ちます。
  
- [ATP の安全な添付ファイル](atp-safe-attachments.md)にマルウェアが電子メールの添付ファイルをスキャン
    
- 電子メール メッセージおよび[ATP の安全なリンク](atp-safe-links.md)を含む Office ドキュメントでのスキャンの web アドレス (Url)
    
- 識別して、 [SharePoint、OneDrive、およびマイクロソフトのチームの分析ツール](atp-for-spo-odb-and-teams.md)とライブラリがオンラインでの悪意のあるファイルをブロック
    
- [スプーフィングのインテリジェンス](learn-about-spoof-intelligence.md)によって不正ななりすましの電子メール メッセージの確認
    
- 他のユーザーと[Office 365 の ATP のフィッシング対策機能](atp-anti-phishing.md)を持つ、組織のカスタム ドメインを偽装しようとするときを検出します。
    
**Office 365 の ATP による保護は、安全なリンク、安全な添付ファイル、およびフィッシング詐欺対策のため、組織のセキュリティ チームを定義するポリシーによって決定されます**。ことが重要のポリシーを定義するのには、定期的に確認し、最新の状態にし、サービスに追加される新しい機能の利点をこれらのポリシーを変更します。 

[レポートは、使用](view-reports-for-atp.md)は、組織の分析ツールを使用する方法を表示します。これらのレポートも表示できます領域を確認し、ポリシーを更新する必要があります。.、マルウェアをすべき、またはファイルかを確認するのにはマイクロソフトとマークされているファイルがあれば、[分析のためのマイクロソフトにファイルを送信](#submit-a-suspicious-file-to-microsoft-for-analysis)することができます。

## <a name="new-features-are-continually-being-added-to-atp"></a>ATP に新機能が追加されているが継続的に

Office 365 に新しい機能を追加するのには継続していて、分析ツールが含まれています。ATP のポリシーを確認および更新するための呼び出しのいくつかの新機能の一覧を次に示します。ATP (または一般的な Microsoft 365) に導入された新機能に関する詳細については、[マイクロソフトの 365 のロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)を参照してください。


|機能の更新  |アクション アイテム  |
|---------|---------|
|2018年 10 月年と、今後数か月にロールアウト、ユーザーが Outlook を使用しているまたは Outlook Web アプリケーション (OWA)、ATP の安全なリンク元の Url が表示されない場合は、Url を書き換えます。(このリンクはネイティブのレンダリングを呼び出して) します。<br>ネイティブのリンクのレンダリングが、組織の利用可能な 365 (クイック実行) の Outlook と OWA の機能します。|なし         |
|先頭 2018年 9 月で、[警告のページを Office 365 の分析ツール](atp-safe-links-warning-pages.md)の機能、新しい配色パターン、詳細についてとにもかかわらず、サイトを続行することには、警告と推奨事項が与えられます。 |なし         |
|2018 の後半以降では、ATP の安全なリンクの保護を拡張 (オンラインの Word、Excel のオンライン、PowerPoint オンラインでは、および OneNote オンライン) オンライン Office および Office 365 用リソース mac 上での Url に適用するには   |[確認し、ATP の安全なリンク ポリシーの編集](set-up-atp-safe-links-policies.md)  |
|遅延月 2018、セキュリティの[検査](quarantine-email-messages.md)機能に&amp;コンプライアンス センターは、 [SharePoint Online をビジネス、およびマイクロソフトのチームの OneDrive の分析ツール](atp-for-spo-odb-and-teams.md)を拡張します。 |[確認し、ATP の安全な添付ファイル ポリシーの編集](set-up-atp-safe-attachments-policies.md) |
|2018年 3 月で以降では、ATP の安全なリンクの保護は、組織内のユーザー間で送信される電子メールに適用する拡張されます。 |[確認し、ATP の安全なリンク ポリシーの編集](set-up-atp-safe-links-policies.md) |
|遅延 2017年 10 月以降では、ATP の安全なリンクの保護に適用する Url の Url と同様に電子メールで Word、Excel、PowerPoint、および Visio など、Office 365 用リソースのドキュメントのウィンドウ、および Office に iOS および Android デバイス上のアプリ拡張されます。  |[Office の最新の認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)を使用するかどうかを確認します。 |
  
## <a name="get-office-365-atp"></a>Office 365 の ATP を取得します。

[ [365 企業の Microsoft](https://www.microsoft.com/microsoft-365/enterprise/home)、Microsoft 365 ビジネス](https://www.microsoft.com/microsoft-365/business)、Office 365 のエンタープライズ E5、および Office 365 の教育 A5 などのサブスクリプションでは、office 365 の ATP が含まれます。組織が Office 365 の分析ツールが含まれていない Office 365 のサブスクリプションの場合は、アドオンとして可能性のある ATP を購入できます。詳細については、 [Office 365 高度な脅威保護サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)を参照してください。 

## <a name="define-policies-for-atp"></a>ATP のポリシーを定義します。

ATP のポリシーを定義 (または編集) を割り当てる必要があります、次の表に記載されている役割のいずれか。

|役割  |場所と方法が割り当てられています。  |
|---------|---------|
|Office 365 のグローバル管理者 |Office 365 を購入するのに署名した人は、既定でグローバル管理者です。( [Office 365 の管理者の役割](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)の詳細についてを参照してください)。         |
|Office 365 のセキュリティ管理者 |管理者センター ([https://aka.ms/admincenter](https://aka.ms/admincenter))|
|Exchange オンライン組織の管理 |Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  PowerShell コマンドレット (を参照してください[Exchange オンライン PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

ATP のポリシーを定義し、定期的に確認するのにはいくつかの種類があります。

1. **[Office 365 の ATP のフィッシング詐欺対策ポリシーを設定します](set-up-anti-phishing-policies.md)** 偽装ベースの攻撃を含む電子メール メッセージを送信する攻撃者に対して保護するためには、信頼されたユーザーまたはドメインからのように見えます。 

2. **[Office 365 の ATP の安全なリンクのポリシーを設定](set-up-atp-safe-links-policies.md)** 組織の[ユーザー設定のブロックされた Url のリスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)と[カスタム」を書き換えない」の Url] ボックスの一覧](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を含みます。
    
3. **[Office 365 の ATP の安全な添付ファイル ポリシーを設定](set-up-atp-safe-attachments-policies.md)** し、[動的な配信およびプレビュー](dynamic-delivery-and-previewing.md)などのいくつかのオプションから選択します。
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>レポートを表示する分析ツールを使用する方法を参照してください。

ATP のポリシーがあると後、は、サービスの操作方法を表示するレポートが利用できます。(Office 365 のセキュリティ & コンプライアンス センターでは、[**レポート**] に移動 > **ダッシュ ボード**です)。

[![セキュリティ&amp;コンプライアンス センターのダッシュ ボードを使用して、脅威の高度な保護が作業しているを確認できます](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. 移動すると、Office 365 のグローバル管理者、セキュリティ管理者、またはセキュリティのリーダー、[https://protection.office.com](https://protection.office.com)し、サインインします。
    
2. **レポート**に > **のダッシュ ボード**です。(これらのレポートのヘルプを表示するには、[高度な脅威保護のためのレポートを表示する](view-reports-for-atp.md)を参照してください)。
    
3. 必要な場合、セキュリティ ポリシーを調整します。ヘルプを表示するには、次のリソースを参照してください。
      - [Office 365 の ATP のフィッシング詐欺対策ポリシー](set-up-anti-phishing-policies.md)
      - [Office 365 の ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)
      - [Office 365 の ATP の安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>分析のためのマイクロソフトに不審なファイルを送信します。

- マルウェアである可能性があります疑いがあるファイルを取得する場合は、分析のためにマイクロソフトは、そのファイルを送信できます。[Windows Defender のセキュリティ情報発信のポータル](https://go.microsoft.com/fwlink/?linkid=857185)にアクセスしてください。

- 分析のためにマイクロソフトに送信する電子メール メッセージ (添付ファイルの有無にかかわらず) を取得する場合[レポート メッセージのアドインを](enable-the-report-message-add-in.md)使用します。 
  

