---
title: Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 10/09/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: 高度な脅威保護 office 365 にはには、なりすましのインテリジェンス、安全なリンク、安全な添付ファイル、および高度なフィッシング対策機能が含まれています。脅威の高度な保護も拡張されている SharePoint のオンライン、OneDrive 内のファイルにビジネス、およびマイクロソフトのチームです。
ms.openlocfilehash: def22368f8bc219ebceda797dd04b234bc3c4435
ms.sourcegitcommit: cda46434094bc2837dba90256d044ba77552df12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2018
ms.locfileid: "25850831"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

Office 365 の高度な脅威保護 (ATP) は、悪意のある攻撃から組織を保護するために役立ちます。
  
- [ATP の安全な添付ファイル](atp-safe-attachments.md)にマルウェアが電子メールの添付ファイルをスキャン
    
- 電子メール メッセージおよび[ATP の安全なリンク](atp-safe-links.md)を含む Office ドキュメントでのスキャンの web アドレス (Url)
    
- 識別して、 [SharePoint、OneDrive、およびマイクロソフトのチームの分析ツール](atp-for-spo-odb-and-teams.md)とライブラリがオンラインでの悪意のあるファイルをブロック
    
- [スプーフィングのインテリジェンス](learn-about-spoof-intelligence.md)によって不正ななりすましの電子メール メッセージの確認
    
- 他のユーザーと[Office 365 の ATP のフィッシング対策機能](atp-anti-phishing.md)を持つ、組織のカスタム ドメインを偽装しようとするときを検出します。
    
**Office 365 の ATP による保護は、安全なリンク、安全な添付ファイル、およびフィッシング詐欺対策のため、組織のセキュリティ チームを定義するポリシーによって決定されます**。定期的に確認し、最新の状態にし、サービスに追加される新しい機能の利点を利用規約を修正するに重要です。[レポートは、使用](view-reports-for-atp.md)は、組織の分析ツールを使用する方法を表示します。これらのレポートも表示できます領域を確認し、ポリシーを更新する必要があります。.、マルウェアをすべき、またはファイルかを確認するのにはマイクロソフトとマークされているファイルがあれば、[分析のためのマイクロソフトにファイルを送信](#submit-a-suspicious-file-to-microsoft-for-analysis)することができます。
      
## <a name="get-office-365-atp"></a>Office 365 の ATP を取得します。

> [!IMPORTANT]
> Office 365 の分析ツールは、Microsoft 365 エンタープライズ、Office 365 エンタープライズ E5、Office 365 の教育 A5、および[Microsoft 365 ビジネス](https://support.office.com/article/c123694a-1efb-459e-a8d5-2187975373dc)など、サブスクリプションに含まれます。組織が Office 365 の分析ツールが含まれていない Office 365 のサブスクリプションの場合は、アドオンとして可能性のある ATP を購入できます。詳細については、 [Office 365 高度な脅威保護サービスの説明](https://technet.microsoft.com/library/exchange-online-advanced-threat-protection-service-description.aspx)を参照してください。 

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
  
## <a name="related-topics"></a>関連項目

[脅威の高度な保護のためのレポートを表示します。](view-reports-for-atp.md)
  
[Threat management in the Office 365 Security &amp; Compliance Center](threat-management.md)
  

