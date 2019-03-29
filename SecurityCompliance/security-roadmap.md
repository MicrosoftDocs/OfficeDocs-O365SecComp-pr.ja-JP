---
title: Office 365 セキュリティロードマップ-最初の30日間、90日以降の最優先事項
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'Office 365 環境を保護するためのセキュリティ機能を実装するための、Microsoft の cybersecurity チームからの主な推奨事項。 '
ms.openlocfilehash: ba74827c34a869ee11553f02d9085b6f015b2d9d
ms.sourcegitcommit: 54d58da1777eb83adb82826d1bb1adb94903c8e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30955170"
---
# <a name="office-365-security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Office 365 セキュリティロードマップ-最初の30日間、90日以降の最優先事項

この記事では、Office 365 環境を保護するためのセキュリティ機能を実装するために、Microsoft の cybersecurity チームからの推奨事項について説明します。 この記事は、Microsoft Ignite session ( [cybersecurity pro のように、セキュリティで保護された Office 365 のように、最初の30日間、90日以降) に適用](https://www.youtube.com/watch?v=luignzNyR-o)されます。 このセッションは、Mark Simos および Kemelhar, エンタープライズ Cybersecurity アーキテクトによって開発および提供されました。
  
この記事の内容
  
- [ロードマップの結果](security-roadmap.md#Roadmap)
    
- [30日-強力な高速 wins](security-roadmap.md#Thirdaydays)
    
- [90日—保護の強化](security-roadmap.md#Ninetydays)
    
- [超え](security-roadmap.md#Beyond)
    
## <a name="roadmap-outcomes"></a>ロードマップの結果
<a name="Roadmap"> </a>

これらのロードマップの推奨事項は、次の目標を使用して、3つのフェーズに論理的な順序で段階的に展開されています。

|||
|:-----|:-----|
| |結果
|30 日間|高速構成:  <br/> •基本的な管理者による保護  <br/> •ログおよび分析  <br/> •基本的な id の保護  <br/> テナントの構成  <br/>  ステークホルダーの準備  <br/> |
|90 日|高度な保護:  <br/> •管理者アカウント  <br/>  •データ&amp;ユーザーアカウント  <br/>  コンプライアンス、脅威、およびユーザーのニーズの可視性  <br/>  既定のポリシーと保護を調整して実装する  <br/> |
|超え|主要なポリシーとコントロールを調整および調整する  <br/> オンプレミスの依存関係への保護を拡張する  <br/> ビジネスおよびセキュリティプロセス (法務、insider の脅威など) と統合する  <br/> |
  

   
## <a name="30-days--powerful-quick-wins"></a>30日-強力な高速 wins
<a name="Thirdaydays"> </a>

タスクはすぐに実行できますので、ユーザーへの影響は少なくて済みます。
  
|||
|:-----|:-----|
|領域  <br/> |タスク  <br/> |
|セキュリティ管理  <br/> |• [セキュリティで保護されたスコア] を確認[https://securescore.office.com](https://securescore.office.com)し、現在のスコアをメモします ()。  <br/>  • Office 365 の監査ログを有効にします。 「[監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)」を参照してください。  <br/> •[セキュリティを強化するために、Office 365 テナントを構成](tenant-wide-setup-for-increased-security.md)します。  <br/>  • Microsoft 365 セキュリティセンターおよび Cloud App security のダッシュボードとレポートを定期的に確認します。  <br/> |
|脅威保護  <br/> |[Office 365 を Microsoft Cloud App Security に接続](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)して、異常な動作に関する既定の脅威検出ポリシーを使用して監視を開始します。 異常検出のベースラインを構築するには、7日間かかります。  <br><br/>  管理者アカウントの保護を実装します。  <br/> •管理者アクティビティに専用の管理者アカウントを使用します。  <br/>  •管理者アカウントに対して多要素認証 (MFA) を適用します。  <br/>  •管理者アクティビティには、[高度にセキュリティで保護された Windows 10 デバイス](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure)を使用します。  <br/> |
|ID およびアクセス管理  <br/> |• [Azure Active Directory id 保護を有効に](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)します。  <br/> •フェデレーション id 環境の場合は、アカウントセキュリティ (パスワードの長さ、年齢、複雑さなど) を適用します。  <br/> |
|情報保護  <br/> | 情報保護に関する推奨事項の例を確認します。 情報保護には、組織全体にわたる調整が必要です。 次のリソースの使用を開始する:  <br/> • [Office 365 の GDPR の情報保護](http://aka.ms/o365gdpr) <br/> • [SharePoint Online のサイトとファイルをセキュリティで保護](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files)する (共有、分類、データ損失防止、および Azure Information Protection を含む)  <br/> |
   
## <a name="90-days--enhanced-protections"></a>90日—保護の強化
<a name="Ninetydays"> </a>

タスクの計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。 
  
|||
|:-----|:-----|
|領域  <br/> |タスク  <br/> |
|セキュリティ管理  <br/> | •お使いの環境で推奨されるアクションに[https://securescore.office.com](https://securescore.office.com)ついては、「Secure Score」を確認してください ()。  <br/>  •引き続き、Microsoft 365 セキュリティセンター、Cloud App security、および SIEM ツールのダッシュボードとレポートを定期的に確認します。  <br/>  •ソフトウェア更新プログラムを検索して実装します。  <br/>  •[アタックシミュレータ](https://support.office.com/article/attack-simulator-office-365-da5845db-c578-4a41-b2cb-5a09689a551b)を使用して、スピアーフィッシング、パスワードスプレー、ブルートフォースパスワード攻撃に対する攻撃のシミュレーションを行います ( [Office 365 の脅威インテリジェンス](office-365-ti.md)に含まれています)。  <br/>  • Cloud App Security ([調査] タブ) の組み込みレポートを確認して、共有リスクを探します。  <br/>  •[コンプライアンスマネージャー](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md)に対して、組織に適用される規制 (GDPR、NIST 800-171 など) の状態を確認するために確認します。  <br/> |
|脅威保護  <br/> | 管理者アカウントの強化された保護を実装します。  <br/>  •管理者アクティビティ用に[特権アクセスワークステーション](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations)(PAWs) を構成します。  <br/>  • [Azure AD 特権 id 管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)を構成します。  <br/>  •セキュリティ情報およびイベント管理 (SIEM) ツールを構成して、Office 365、Cloud App security、およびその他のサービス (AD FS を含む) からログデータを収集します。 Office 365 監査ログには、90日間のみのデータが格納されます。 このデータを SIEM ツールで取得すると、長期間にデータを格納することができます。  <br/> |
|ID およびアクセス管理  <br/> | •すべてのユーザーに対して MFA を有効にし、適用します。  <br/>  •[条件付きアクセスと関連ポリシー](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations)のセットを実装します。 |
|情報保護  <br/> | 情報保護ポリシーを調整して実装します。 これらのリソースには例があります。  <br/> • [Office 365 の GDPR の情報保護](http://aka.ms/o365gdpr) <br/> • [SharePoint Online のサイトとファイルをセキュリティで保護](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files)する <br/> <br> office 365 に保存されたデータ (Cloud App Security ではなく) に対して、office 365 のデータ損失防止ポリシーおよび監視ツールを使用します。 <br><br>高度な警告機能 (データ損失防止) については、Office 365 で Cloud App Security を使用します。  <br/> |
   
## <a name="beyond"></a>超え
<a name="Beyond"> </a>

これらは、前の作業で構築された重要なセキュリティ対策です。 
  
|||
|:-----|:-----|
|領域  <br/> |タスク  <br/> |
|セキュリティ管理  <br/> |•セキュリティで保護されたスコアを使用[https://securescore.office.com](https://securescore.office.com)して、次のアクションの計画を続行します ()。  <br/>  •引き続き、Microsoft 365 セキュリティセンター、Cloud App security、および SIEM ツールのダッシュボードとレポートを定期的に確認します。  <br/>  •ソフトウェア更新プログラムの検索と実装を続行します。  <br/>  •電子情報開示を法的および脅威対応プロセスに統合します。  <br/> |
|脅威保護  <br/> | •オンプレミス (ad、ad FS) 上の id コンポーネントに対して、[セキュリティで保護された特権アクセス](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)(SPA) を実装します。  <br/>  •内部者の脅威を監視するには、Cloud App Security を使用します。  <br/>  • Cloud App Security を使用して IT SaaS のシャドウ使用状況を検出します。  <br/> |
|ID およびアクセス管理  <br/> | •情報保護ポリシーを調整します。  <br/>  • Azure Information Protection および Office 365 データ損失防止 (DLP)。  <br/>  • Cloud App Security ポリシーとアラート。  <br/> |
|情報保護  <br/> | •ポリシーおよび運用プロセスを調整します。  <br/>  • Azure AD id 保護を使用して、内部の脅威を特定します。  <br/> |
   
また、「 [petya および WannaCrypt などのラピッド cyberattacks を緩和する方法](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)」も参照してください。 
  

