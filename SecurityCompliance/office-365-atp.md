---
title: Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/08/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: 高度な脅威保護 office 365 にはには、なりすましのインテリジェンス、安全なリンク、安全な添付ファイル、および高度なフィッシング対策機能が含まれています。脅威の高度な保護も拡張されている SharePoint のオンライン、OneDrive 内のファイルにビジネス、およびマイクロソフトのチームです。
ms.openlocfilehash: 1e6a2dc16bf5fb8dbf1b242a3495d8fb87cfda1c
ms.sourcegitcommit: 147768bbe44c8c98c02fa29ae9d882cee4ec2d6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238479"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

## <a name="overview"></a>概要

Office 365 の高度な脅威保護 (ATP) は、悪意のある攻撃から組織を保護するために役立ちます。
  
- [ATP の安全な添付ファイル](atp-safe-attachments.md)にマルウェアが電子メールの添付ファイルをスキャン
    
- 電子メール メッセージおよび[ATP の安全なリンク](atp-safe-links.md)を含む Office ドキュメントでのスキャンの web アドレス (Url)
    
- 識別して、 [SharePoint、OneDrive、およびマイクロソフトのチームの分析ツール](atp-for-spo-odb-and-teams.md)とライブラリがオンラインでの悪意のあるファイルをブロック
    
- [スプーフィングのインテリジェンス](learn-about-spoof-intelligence.md)によって不正ななりすましの電子メール メッセージの確認
    
- 他のユーザーと[Office 365 の ATP のフィッシング対策機能](atp-anti-phishing.md)を持つ、組織のカスタム ドメインを偽装しようとするときを検出します。
    
**Office 365 の ATP による保護は、安全なリンク、安全な添付ファイル、およびフィッシング詐欺対策のため、組織のセキュリティ チームを定義するポリシーによって決定されます**。定期的に確認し、最新の状態にし、サービスに追加される新しい機能の利点を利用規約を修正するに重要です。[レポートは、使用](view-reports-for-atp.md)は、組織の分析ツールを使用する方法を表示します。これらのレポートも表示できます領域を確認し、ポリシーを更新する必要があります。.、マルウェアをすべき、またはファイルかを確認するのにはマイクロソフトとマークされているファイルがあれば、[分析のためのマイクロソフトにファイルを送信](#submit-a-suspicious-file-to-microsoft-for-analysis)することができます。

## <a name="new-features-are-continually-being-added-to-atp"></a>ATP に新機能が追加されているが継続的に

Office 365 に新しい機能を追加するのには継続していて、分析ツールが含まれています。ATP のポリシーを確認および更新するための呼び出しのいくつかの新機能の一覧を次に示します。ATP (または一般的な Microsoft 365) に導入された新機能に関する詳細については、[マイクロソフトの 365 のロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)を参照してください。
  
- 遅延 2017年 10 月以降では、ATP の安全なリンクの保護に適用する Url の Url と同様に電子メールで Word、Excel、PowerPoint、および Visio など、Office 365 用リソースのドキュメントのウィンドウ、および Office に iOS および Android デバイス上のアプリ拡張されます。( [Office の最新の認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)を使用することを確認してください。)
    
- 2018年 3 月で以降では、ATP の安全なリンクの保護は、組織内のユーザー間で送信される電子メールに適用する拡張されます。(を必ず[確認](set-up-atp-safe-links-policies.md)し、ATP の安全なリンク ポリシーを編集します。

- 遅延月 2018、セキュリティの[検査](quarantine-email-messages.md)機能に&amp;コンプライアンス センターは、 [SharePoint Online をビジネス、およびマイクロソフトのチームの OneDrive の分析ツール](atp-for-spo-odb-and-teams.md)を拡張します。
 
- 2018 の後半以降では、ATP の安全なリンクの保護を拡張 (オンラインの Word、Excel のオンライン、PowerPoint オンラインでは、および OneNote オンライン) オンライン Office および Office 365 用リソース mac 上での Url に適用するには(を必ず[確認](set-up-atp-safe-links-policies.md)し、ATP の安全なリンク ポリシーを編集します。

- 先頭 2018年 9 月で、[警告のページを Office 365 の分析ツール](atp-safe-links-warning-pages.md)の機能、新しい配色パターン、詳細についてとにもかかわらず、サイトを続行することには、警告と推奨事項が与えられます。 
 
- 2018年 10 月年と、今後数か月にロールアウト、Outlook Web アプリケーション (OWA) を使用している人または、次の ATP の安全なリンク元の Url が表示されない場合は、Url を書き換えます。(このネイティブのリンクの表示/非表示を呼び出して) します。

      
## <a name="get-office-365-atp"></a>Office 365 の ATP を取得します。

> [!IMPORTANT]
> Office 365 の分析ツールは、Microsoft 365 エンタープライズ、Office 365 エンタープライズ E5、Office 365 の教育 A5、および[Microsoft 365 ビジネス](https://docs.microsoft.com/en-us/microsoft-365/business/security-features)など、サブスクリプションに含まれます。組織が Office 365 の分析ツールが含まれていない Office 365 のサブスクリプションの場合は、アドオンとして可能性のある ATP を購入できます。詳細については、 [Office 365 高度な脅威保護サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)を参照してください。 

1. グローバルまたはセキュリティ管理者には、[https://portal.office.com](https://portal.office.com)と Office 365 は、職場または学校のアカウントでサインインします。 
    
2. **Admin**を選択して\>**請求**をして、現在のサブスクリプションが含まれています。 <br/>![管理者にして、グローバル管理者としてサインイン portal.office.com\>請求](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)
  
3. **Office 365 エンタープライズ E5**、 **Office 365 の教育 A5**、または**Microsoft 365 ビジネス**を表示する場合、組織は ATP をいます。 <br/>**Office 365 エンタープライズ E3**や**Office 365 エンタープライズ E1**など、別のサブスクリプションを参照する場合は、分析ツールを追加することを検討してください。そのためには、 **+ 追加のサブスクリプション**を選択します。
    
ATP を作成したら、次に、セキュリティ チーム用にポリシーを定義します。 
  
## <a name="define-policies-for-atp"></a>ATP のポリシーを定義します。

- 信頼されたユーザーまたはドメインからのように見える**[Office 365 の ATP のフィッシング詐欺対策ポリシーを設定します](set-up-anti-phishing-policies.md)** 偽装ベースの攻撃を含む電子メール メッセージを送信する攻撃者から保護するため 

- **[Office 365 の ATP の安全なリンクのポリシーを設定](set-up-atp-safe-links-policies.md)** 組織の[ユーザー設定のブロックされた Url のリスト](set-up-a-custom-blocked-urls-list-wtih-atp.md)と[カスタム」を書き換えない」の Url] ボックスの一覧](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を含む
    
- **[Office 365 の ATP の安全な添付ファイル ポリシーを設定](set-up-atp-safe-attachments-policies.md)** する[動的な配信およびプレビュー](dynamic-delivery-and-previewing.md)を含めることができます。
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>レポートを表示する分析ツールを使用する方法を参照してください。

ATP のポリシーがあると後、は、サービスの操作方法を表示するレポートが利用できます。

[![セキュリティ&amp;コンプライアンス センターのダッシュ ボードを使用して、脅威の高度な保護が作業しているを確認できます](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. Office 365 グローバル管理者、セキュリティ管理者、またはセキュリティのリーダーをしていることを確認します。(を参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md).)
    
2. [脅威の高度な保護に関するレポートを表示](view-reports-for-atp.md)します。
    
3. 必要な場合、セキュリティ ポリシーを調整します。次のリソースを参照してください。

  - [Office 365 の ATP のフィッシング詐欺対策ポリシー](set-up-anti-phishing-policies.md)
    
  - [Office 365 の ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)
    
  - [Office 365 の ATP の安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>分析のためのマイクロソフトに不審なファイルを送信します。

- マルウェアである可能性があります疑いがあるファイルを取得する場合は、分析のためにマイクロソフトは、そのファイルを送信できます。[Windows Defender のセキュリティ情報発信のポータル](https://go.microsoft.com/fwlink/?linkid=857185)にアクセスしてください。

- 分析のためにマイクロソフトに送信する電子メール メッセージ (添付ファイルの有無にかかわらず) を取得する場合[レポート メッセージのアドインを](enable-the-report-message-add-in.md)使用します。 
  

