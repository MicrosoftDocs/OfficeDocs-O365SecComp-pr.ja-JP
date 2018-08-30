---
title: Office 365 のセキュリティ ロードマップの最初の 30 日、90 日間での内外の最優先事項
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'Office 365 環境を保護するセキュリティ機能を実装するためのマイクロソフトの cybersecurity のチームからの推奨事項です。 '
ms.openlocfilehash: 714f2a9c8c2883ee954f6d74eb20db01114c62a7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013731"
---
# <a name="office-365-security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Office 365 のセキュリティ ロードマップの最初の 30 日、90 日間での内外の最優先事項

この資料には、Office 365 環境を保護するセキュリティ機能を実装するためのマイクロソフトの cybersecurity のチームからの推奨事項が含まれています。出典: マイクロソフトの Ignite セッションから- [pro の cybersecurity のように Office 365 のセキュリティで保護された: 最初の 30 日、90 日間での内外の優先順位のトップ](https://www.youtube.com/watch?v=luignzNyR-o)。このセッションが開発され、マーク Simos と Matt Kemelhar、企業の Cybersecurity の設計者によって提示されます。
  
この記事の内容
  
- [ロードマップの結果](security-roadmap.md#Roadmap)
    
- [30 日-強力な短期](security-roadmap.md#Thirdaydays)
    
- [90 日間、保護を強化](security-roadmap.md#Ninetydays)
    
- [を超えて](security-roadmap.md#Beyond)
    
## <a name="roadmap-outcomes"></a>ロードマップの結果
<a name="Roadmap"> </a>

これらのロードマップの推奨事項は、次の要件を論理的な順序で 3 つのフェーズにわたってがステージングされます。

|||
|:-----|:-----|
| |成果
|30 日|迅速に構成します。  <br/> • 管理の基本的な保護  <br/> • ログの記録および分析  <br/> • 基本的な id の保護  <br/> テナント構成  <br/>  利害関係者を準備します。  <br/> |
|90 日|高度な保護。  <br/> • 管理者アカウント  <br/>  • データ&amp;ユーザー アカウント  <br/>  コンプライアンス、脅威、およびユーザーのニーズの把握  <br/>  適応し、既定のポリシーおよび保護機能を実装します。  <br/> |
|を超えて|調整し、キーのポリシーおよび制御を調整します。  <br/> 設置型の依存関係への保護機能を拡張します。  <br/> (法務、内部からの脅威など) は、ビジネスおよびセキュリティのプロセスとの統合します。  <br/> |
  

   
## <a name="30-days--powerful-quick-wins"></a>30 日-強力な短期
<a name="Thirdaydays"> </a>

これらのタスクは、迅速に行うことができ、ユーザーに影響が少ない。
  
|||
|:-----|:-----|
|領域  <br/> |タスク  <br/> |
|セキュリティの管理  <br/> |• は、セキュリティで保護されたスコアを確認し、注意してください、現在のスコアの ( [https://securescore.office.com](https://securescore.office.com))。  <br/>  • は、Office 365 の監査ログを有効にします。参照してください[では、Office 365 のセキュリティ監査ログを検索する&amp;コンプライアンス センター](search-the-audit-log-in-security-and-compliance.md)です。<br/> •[セキュリティ強化のため、Office 365 のテナントを構成](tenant-wide-setup-for-increased-security.md)します。  <br/>  • は、ダッシュ ボードおよびレポートでは、Office 365 のセキュリティとコンプライアンス センターおよびクラウド アプリケーションのセキュリティを定期的に確認します。  <br/> |
|脅威保護  <br/> |脅威の検出の既定のポリシーを使用して、異常な動作の監視を開始するのには[マイクロソフトのクラウド アプリケーションのセキュリティに Office 365 を接続](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)をします。異常検出の基準計画を作成するのには 7 日間がかかります。<br><br/>  管理者アカウントの保護を実装します。  <br/> • 専用の使用の管理では、管理アクティビティが占めています。  <br/>  • は、管理者アカウント用の多要素認証 (MFA) を適用します。  <br/>  [安全性の高い Windows 10 デバイス](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure)を使用して管理活動の •。  <br/> |
|ID およびアクセス管理  <br/> |• は[Azure Active Directory Id の保護を有効に](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)します。  <br/> • フェデレートされた識別情報の環境では、アカウントのセキュリティ (パスワードの長さ、年齢、複雑さなど) を適用します。  <br/> |
|情報 proteciton  <br/> | 例については保護の推奨事項を確認します。情報の保護には、組織全体にわたって調整が必要です。これらのリソースを開始します。<br/> • [GDPR の office 365 の情報の保護](http://aka.ms/o365gdpr) <br/> • [SharePoint Online のセキュリティで保護されたサイトおよびファイル](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files)(共有、クラス分け、データ損失の防止、Azure の情報の保護が含まれています)  <br/> |
   
## <a name="90-days--enhanced-protections"></a>90 日間、保護を強化
<a name="Ninetydays"> </a>

これらのタスクには、計画し実装しますが、セキュリティの状態が大幅に増加するに少し時間がかかります。 
  
|||
|:-----|:-----|
|領域  <br/> |タスク  <br/> |
|セキュリティの管理  <br/> | • 環境に推奨される操作をセキュリティで保護されたスコアを確認する ( [https://securescore.office.com](https://securescore.office.com))。  <br/>  • は、ダッシュ ボードおよびレポートでは、Office 365 のセキュリティとコンプライアンスの中心、クラウド アプリケーションのセキュリティ、および SIEM ツールを定期的に確認」に進みます。  <br/>  • は、検索し、ソフトウェア更新プログラムを実装します。  <br/>  スピアー フィッシング、スプレーのパスワード、および[攻撃のシミュレータ](https://support.office.com/article/attack-simulator-office-365-da5845db-c578-4a41-b2cb-5a09689a551b)に付属している[Office 365 の脅威インテリジェンス](office-365-ti.md)) を使用して、ブルート フォース パスワード攻撃の • 倫理規定の攻撃のシミュレーション。  <br/>  • ファイルの場所 ([調査] タブ) のクラウド アプリケーションのセキュリティの組み込みのレポートを確認することによってリスクを共有するためです。  <br/>  • は、(GDPR、NIST 800-171) などの組織に適用される規制の状態を確認するのには、[コンプライアンス マネージャー](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md)を確認します。  <br/> |
|脅威保護  <br/> | 管理者アカウントの拡張保護機能を実装します。  <br/>  • 管理アクティビティに[アクセスの権限を持つワークステーション](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations)(前足) を構成します。  <br/>  • は、 [Azure AD 特権 Id の管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)を構成します。  <br/>  • は、Office 365、クラウド アプリケーションのセキュリティ、および AD FS を含むその他のサービスからログ データを収集するためにセキュリティ情報およびイベント管理 (SIEM) ツールを構成します。Office 365 の監査ログでは、90 日間のみのデータを格納します。SIEM のツールでは、このデータのキャプチャを使用するより長い期間のデータを格納します。<br/> |
|ID およびアクセス管理  <br/> | • を有効にし、すべてのユーザーの MFA を適用します。  <br/>  • は、一連の[条件付きアクセスおよび関連するポリシー](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations)を実装します。 |
|情報 proteciton  <br/> | 適応し、情報保護のポリシーを実装します。これらのリソースには、例が含まれます。<br/> • [GDPR の office 365 の情報の保護](http://aka.ms/o365gdpr) <br/> • [SharePoint Online のセキュリティで保護されたサイトおよびファイル](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) <br/> <br> (クラウド アプリケーションのセキュリティ) の代わりに Office 365 に格納されている Office 365 のデータ損失防止のポリシーと監視ツールを使用します。 <br><br>詳細なアラート機能 (データ損失の防止) を除く、Office 365 でクラウド アプリケーションのセキュリティを使用します。  <br/> |
   
## <a name="beyond"></a>を超えて
<a name="Beyond"> </a>

これらは、前の作業を構築する重要なセキュリティ対策です。 
  
|||
|:-----|:-----|
|領域  <br/> |タスク  <br/> |
|セキュリティの管理  <br/> |• 引き続き、セキュリティで保護されたスコアを使用して、次のアクションを計画 ( [https://securescore.office.com](https://securescore.office.com))。  <br/>  • は、ダッシュ ボードおよびレポートでは、Office 365 のセキュリティとコンプライアンスの中心、クラウド アプリケーションのセキュリティ、および SIEM ツールを定期的に確認」に進みます。  <br/>  • を検索し、ソフトウェア更新プログラムを実装する」に進みます。  <br/>  •、法的には、電子的証拠開示と脅威の応答のプロセスを統合します。  <br/> |
|脅威保護  <br/> | • (AD、AD FS) は、社内設置型のコンポーネントをユーザーの[アクセス権限をセキュリティで保護された](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)(SPA) を実装します。  <br/>  • 内部からの脅威を監視するためのクラウド アプリケーションのセキュリティを使用します。  <br/>  • クラウド アプリケーションのセキュリティを使用してシャドウ IT SaaS の利用状況を検出します。  <br/> |
|ID およびアクセス管理  <br/> | • 絞り込み情報保護ポリシー:  <br/>  • Azure の情報の保護と Office 365 のデータ損失防止 (DLP)。  <br/>  • クラウド アプリケーションのセキュリティ ポリシーと通知します。  <br/> |
|情報 proteciton  <br/> | • 絞り込みのポリシーと運用プロセスです。  <br/>  • は、内部からの脅威を識別するのには、Azure AD Id の保護を使用します。  <br/> |
   
参照してください: [Petya や WannaCrypt などの高速 cyberattacks を軽減する方法](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)です。 
  

