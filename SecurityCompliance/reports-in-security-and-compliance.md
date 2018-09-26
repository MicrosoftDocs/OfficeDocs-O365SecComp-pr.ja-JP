---
title: Office 365 のセキュリティ レポート&amp;コンプライアンス センター
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/1/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: 'Office 365 のセキュリティを使用して、 &amp; 、SharePoint Online および Exchange オンライン組織のさまざまなレポートを取得するのにはコンプライアンスの中心と Azure Active Directory を報告します。  '
ms.openlocfilehash: 019ccc49352db1aaf392287f62fa63f66913e293
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038340"
---
# <a name="reports-in-the-office-365-security-amp-compliance-center"></a>Office 365 のセキュリティ レポート&amp;コンプライアンス センター

Office 365 のセキュリティ**レポートを表示する**ページを使用することができます&amp;、SharePoint Online 組織と Exchange Online 組織の監査レポートを簡単にアクセスするコンプライアンス センターです。レポートにアクセスできます Azure Active Directory (AD) ユーザー サインインが、ユーザーの利用状況を報告して、Azure AD の監査**レポートを表示する**ページからログに記録します。これは、Office 365 サブスクリプションを購入には、Microsoft Azure への無料サブスクリプションが含まれているためにです。Azure のこれらのレポートにアクセスするときに最初に 1 回限りの登録プロセスを完了する必要があります。 
  
> [!TIP]
> Office 365 の組織内の利用状況に関するレポートを表示するには、 [Office 365 の管理センターでの活動レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)を参照してください。 
  
 **開始する前に**
  
セキュリティ レポートを表示するのには次のアクセスを許可する必要があります&amp;コンプライアンス センターです。
  
- Exchange 管理センター (EAC) が、セキュリティ レポートを表示するのにはセキュリティのリーダーの役割を割り当てる必要がある&amp;コンプライアンス センターです。既定では、このロールは、EAC で組織の管理とセキュリティのリーダーの役割グループに割り当てられます。
    
- セキュリティの DLP コンプライアンス管理の役割を割り当てる必要がある&amp;、セキュリティの DLP レポート (および DLP ポリシー) を表示するのにはコンプライアンス センター&amp;コンプライアンス センター。セキュリティ コンプライアンス管理者、組織の管理、およびセキュリティ管理者の役割グループに既定では、このロールが割り当てられている&amp;コンプライアンス センターです。
    
さらに、EAC で DLP レポート (および DLP ポリシー) を表示するのには EAC のデータ損失の防止の役割を割り当てられる必要があります。既定では、このロールは、EAC でコンプライアンスの管理と組織管理の役割グループに割り当てられます。
  
 **セキュリティ レポート] ページでビューを開くに&amp;コンプライアンス センター。**
  
1. [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports) に移動します。
    
2. Office 365 組織内のユーザー アカウントの資格情報を使用して Office 365 にサインインします。
    
[**レポートの表示**] ページで、次の種類のレポートを表示できます。 
  
- [EOP の監査レポート](#auditing-reports)
- [監督機関による監査レポート](#supervisory-review-report)
- [データ損失防止レポート](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>監査レポート

次の表に、セキュリティ**レポートを表示する**ページで **[監査**] セクションのレポート&amp;コンプライアンス センターです。 
  
|**レポート**|**説明**|
|:-----|:-----|
|**Office 365 の監査ログ レポート** <br/> |Office 365 の組織では、Office 365 の監査ログのユーザーと管理者のアクティビティを検索できます。レポートには、ビジネス、および Office 365 のディレクトリ サービスは、Azure Active Directory の Exchange Online、SharePoint Online の OneDrive のエントリのユーザーと管理者の活動が含まれています。詳細についてを参照してください[では、Office 365 のセキュリティ監査ログを検索する&amp;コンプライアンス センター](search-the-audit-log-in-security-and-compliance.md)です。<br/> |
|**Azure AD レポート** <br/> |サインインし、アクティビティを使用する、異常なまたは不審なサインインの活動、Office 365 の組織内を検索するのには Microsoft Azure でレポートします。Azure AD の監査ログにイベントを表示することもできます。Azure でレポートを表示するには、だけで**Azure AD] ビューに表示**をクリックします。詳細についてを参照してください。<br/><br/>[Office 365 の無料、Azure Active Directory のサブスクリプションを使用](use-your-free-azure-ad-subscription-in-office-365.md)します。 <br/> [アクセスと使用状況レポートを表示](http://go.microsoft.com/fwlink/p/?LinkId=506902)します。  <br/> |
|**Exchange 監査レポート** <br/> | Office 365 の監査機能を使用するには、組織の管理者が、Exchange のオンラインでの構成に加えた変更を追跡します。Microsoft データ センターの管理者、または委任された管理者が、Exchange Online 組織に加えられた変更が記録されます。Exchange オンライン、管理者の監査を有効にするには何も実行する必要はありませんので、デフォルトでログを有効にします。Exchange Online は、メールボックスの監査を使用すると、メールボックスの所有者以外のユーザーがメールボックスへのアクセスを追跡するログを提供します。各メールボックスの所有者以外のアクセスを追跡するログ出力のメールボックスの監査を有効にする必要があります。<br/>  管理者とメールボックスの両方の監査ログ、監査ログ ・ エントリーを表示するのには、監査レポートを実行することができます。メッセージを電子メールに添付されている XML ファイルに 24 時間以内に送信する、メールボックス、管理者の監査ログをエクスポートすることもできます。<br/><br/>監査ログをエクスポートする方法の詳細についてを参照してください。  <br/><br/> [メールボックス監査ログのエクスポート](http://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [表示し、データ センター管理者の監査ログのエクスポート](http://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [役割グループの変更を検索するか、管理者の監査ログ](http://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Exchange 監査レポート](http://go.microsoft.com/fwlink/p/?LinkID=395232)をします。  <br/> |
   
## <a name="supervisory-review-report"></a>監督機関による監査レポート

監督機関による監査レポートを使用するには、組織のすべての監督機関による監査ポリシーのステータスを表示できます。詳細については、[監督者の構成、組織のポリシーを確認する](configure-supervision-policies.md)を参照してください。
  
## <a name="data-loss-prevention-reports"></a>データ損失防止レポート

データ損失防止 (DLP) は、DLP ポリシーに関する情報が含まれているし、コンテンツに適用されているルールには、Office 365 の組織内の機密データが含まれているを報告します。DLP ポリシーとルールをベースとする DLP のアクションに関する情報を表示するレポートを構成することもできます。詳細については、[データ損失の防止についてのレポートのビュー](view-the-dlp-reports.md)を参照してください。
