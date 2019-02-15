---
title: Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/08/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection には、スプーフィング知性、安全なリンク、安全な添付ファイル、高度なフィッシング対策機能、および脅威インテリジェンスが含まれています。
ms.openlocfilehash: d78b37ca048187a298b6e083b54ad68b949638ef
ms.sourcegitcommit: 2af6c3e8a74995294a67429530af8f085e6ca136
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051178"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

## <a name="overview-of-office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection の概要

> [!IMPORTANT]
> この記事は、ビジネスのお客様を対象としています。Outlook の安全なリンクに関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

Office 365 Advanced Threat Protection (ATP) は、次のことにより、組織を悪意のある攻撃から保護するのに役に立ちます。
  
- [ATP の安全な添付ファイル](atp-safe-attachments.md)を使用したマルウェアの電子メール添付ファイルのスキャン
    
- [ATP の安全なリンク](atp-safe-links.md)による電子メールメッセージと Office ドキュメント内の web アドレス (url) のスキャン
    
- [SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)を使用してオンラインライブラリ内の悪意のあるファイルを識別してブロックする
    
- [スプーフィングインテリジェンス](learn-about-spoof-intelligence.md)による不正なスプーフィングの電子メールメッセージの確認
    
- [Office 365 で ATP のフィッシング対策機能](atp-anti-phishing.md)を使用してユーザーおよび組織のカスタムドメインを偽装しようとした場合の検出
    
**Office 365 による保護は、組織のセキュリティチームが安全なリンク、安全な添付ファイル、およびフィッシング対策として定義するポリシーによって判断され**ます。ポリシーを定義し、それらのポリシーを定期的に見直し、改訂して、最新の状態に保ち、サービスに追加された新機能のメリットを得ることが重要です。 

レポートを使用すると、組織の ATP がどのように機能しているかを示すこと[ができ](view-reports-for-atp.md)ます。これらのレポートには、ポリシーを確認して更新する必要がある領域も表示されます。また、マルウェアとしてマークされたファイルがない場合や、microsoft が確認する必要があるファイルがある場合は、 [microsoft にファイルを送信して分析](#submit-a-suspicious-file-to-microsoft-for-analysis)を行うことができます。

## <a name="new-features-are-continually-being-added-to-atp"></a>新機能が ATP に継続的に追加されている

引き続き Office 365 に新機能を追加しています。これには ATP が含まれています。次に示すいくつかの新機能の一覧を示します。これは、ATP ポリシーを確認して更新するための呼び出しの一部です。ATP (または microsoft 365 全般) に出てくる新機能の詳細については、 [microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)を参照してください。


|機能の更新  |アクションアイテム  |
|---------|---------|
|2019年2月から、今後数か月にわたってロールアウトされるようになったため、脅威インテリジェンス機能が ATP に追加されています。また、組織に現在 atp が存在しない場合は、atp プラン1や atp plan 2 を含む新しいオプションを考慮する必要があります。詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。 |組織のサブスクリプションを確認し、必要に応じて[アドオンを購入または編集](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)します。  |
|2018年10月から、ユーザーが outlook または outlook Web アプリケーション (OWA) を使用している場合、ATP の安全なリンクは元の url をレンダリングし、書き換えられた url は表示しません。(このネイティブリンクレンダリングを呼び出しています)。<br>組織でネイティブリンクレンダリングが使用可能な場合、この機能は Outlook 365 (クイック実行) および OWA で機能します。|なし         |
|2018年9月以降、 [Office 365 ATP の警告ページ](atp-safe-links-warning-pages.md)機能には、新しい配色、詳細、および警告と推奨事項があるにもかかわらずサイトを継続する機能があります。 |なし         |
|2018年後半から、office Online (Word online、Excel online、PowerPoint online、OneNote online) および office 365 ProPlus on Mac の url に適用されるように、ATP の安全なリンク保護が拡張されます。   |[ATP の安全なリンクポリシーを確認および編集する](set-up-atp-safe-links-policies.md)  |
|2018年5月の初期[](quarantine-email-messages.md)段階では、セキュリティ&amp; /コンプライアンスセンターの検疫機能が、 [SharePoint Online、OneDrive for business、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)に拡張されています。 |[ATP の安全な添付ファイルポリシーの確認と編集](set-up-atp-safe-attachments-policies.md) |
|2018年3月から、組織内のユーザー間で送信される電子メールに適用されるように、ATP の安全なリンク保護が拡張されました。 |[ATP の安全なリンクポリシーを確認および編集する](set-up-atp-safe-links-policies.md) |
|2017年10月以降、ATP の安全なリンク保護は、電子メールの url、Word、Excel、PowerPoint、Visio on Windows などの office 365 ProPlus ドキュメント、iOS および Android デバイス上の office アプリに適用されるように拡張されています。  |[Office の先進認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)を使用していることを確認する |

## <a name="get-office-365-atp"></a>Office 365 ATP を取得する

office 365 ATP は、サブスクリプションに含まれています。たとえば、 [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、office 365 Enterprise E5、office 365 教育 A5 などです。office 365 atp を含まない office 365 サブスクリプションが組織にある場合は、atp をアドオンとして購入する可能性があります。詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。 

## <a name="define-policies-for-atp"></a>ATP のポリシーを定義する

ATP ポリシーを定義 (または編集) するには、次の表に示すいずれかの役割を割り当てられている必要があります。

|役割  |場所/割り当て方法  |
|---------|---------|
|Office 365 グローバル管理者 |Office 365 の購入にサインアップするユーザーは、既定ではグローバル管理者です。(詳細については、「 [Office 365 管理者の役割につい](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)て」を参照してください)。         |
|セキュリティ管理者 |Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織の管理 |Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  powershell コマンドレット (「 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照) |

> [!TIP]
> 役割とアクセス許可の詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

さまざまな種類の ATP ポリシーを定義し、定期的に確認します。

1. 信頼されたユーザーまたはドメインからの電子メールメッセージを送信する攻撃者から保護するために、 **[Office 365 で ATP のフィッシング対策ポリシーを設定](set-up-anti-phishing-policies.md)** します。 

2. **[Office 365 で ATP の安全なリンクのポリシーを設定](set-up-atp-safe-links-policies.md)** します。これには、組織の[カスタムブロック](set-up-a-custom-blocked-urls-list-wtih-atp.md)された url の一覧や、[ユーザー設定の "url をリライトしない" url リスト](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)が含まれます。
    
3. **[Office 365 で ATP の安全な添付ファイルのポリシーを設定](set-up-atp-safe-attachments-policies.md)** し、[動的配信やプレビュー](dynamic-delivery-and-previewing.md)など、いくつかのオプションから選択します。
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>レポートを表示して ATP の動作を確認する

ATP ポリシーが設定された後、サービスがどのように機能しているかを示すレポートを使用できます。(Office 365 Security & コンプライアンスセンターで、[ **Reports** > **Dashboard**] に移動します。)

[![セキュリティ&amp;コンプライアンスセンターのダッシュボードは、高度な脅威保護が機能している場所を確認するのに役立ちます。](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. Office 365 の全体管理者、セキュリティ管理者、またはセキュリティリーダーとして[https://protection.office.com](https://protection.office.com) 、に移動して、サインインします。
    
2. [**レポート** > ]**ダッシュボード**に移動します。(これらのレポートに関する詳細については、「 [View reports for Advanced Threat Protection](view-reports-for-atp.md)」を参照してください)。
    
3. 必要に応じて、セキュリティポリシーに調整を加えます。これに関するヘルプを表示するには、次のリソースを参照してください。
    - [ATP のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)
    - [ATP の安全なリンクポリシー](set-up-atp-safe-links-policies.md)
    - [ATP の安全な添付ファイルポリシー](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>疑わしいファイルを分析のために Microsoft に提出する

- マルウェアの疑いがあると思われるファイルを取得した場合は、そのファイルを分析のために Microsoft に提出することができます。[Windows Defender セキュリティインテリジェンス送信ポータル](https://go.microsoft.com/fwlink/?linkid=857185)にアクセスします。

- Microsoft に送信する電子メールメッセージ (添付ファイルの有無にかかわらず) を取得する場合は、[レポートメッセージアドイン](enable-the-report-message-add-in.md)を使用します。 
  

