---
title: セキュリティ強化のために、Office 365 テナントを構成する
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
description: テナント全体の設定を Office 365 環境内のセキュリティに影響を与えるための推奨される構成について説明します。セキュリティ ニーズは、セキュリティまたは短い必要があります。これらの推奨事項は、開始点として使用します。
ms.openlocfilehash: 5c989b5a8abace686df50b6847a0a182393927d5
ms.sourcegitcommit: a36d2692396786f49c8765c65145e5093578e9a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498103"
---
# <a name="configure-your-office-365-tenant-for-increased-security"></a>セキュリティ強化のために、Office 365 テナントを構成する

このトピックでは、テナント全体の設定を Office 365 環境内のセキュリティに影響を与えるための推奨される構成について説明します。セキュリティ ニーズは、セキュリティまたは短い必要があります。これらの推奨事項は、開始点として使用します。
  
## <a name="check-office-365-secure-score"></a>Office 365 のセキュリティで保護されたスコアを確認します。

Office 365 セキュリティで保護されたスコアは、通常の動作とセキュリティの設定に基づいて、Office 365 の組織のセキュリティを分析し、スコアが割り当てられます。現在のスコアを記録することから始めます。テナント全体のいくつかの設定を調整すると、あなたのスコアが増加します。目標は、最大のスコアを達成するが、ユーザーの生産性に悪影響を及ぼす影響しない、環境を保護するために営業案件の注意すべきです。[Office 365 のセキュリティで保護されたスコアを導入すること](office-365-secure-score.md)を参照してください。
  
## <a name="tune-threat-management-policies-in-the-office-365-security-amp-compliance-center"></a>Office 365 のセキュリティの脅威の管理ポリシーを調整する&amp;コンプライアンス センター

Office 365 のセキュリティ&amp;コンプライアンス センターには、環境を保護する機能が含まれています。レポートとダッシュ ボードを監視して、処理に使用することができますが含まれます。一部の領域は、既定のポリシーの構成が付いてきます。一部の領域は、既定のポリシーまたはルールには含まれません。安全な環境の脅威の管理の設定を調整するのには脅威の管理の下でこれらのポリシーを参照してください。 
  
|領域。|既定のポリシー。|推奨。|
|:-----|:-----|:-----|
|**フィッシング詐欺対策** <br/> |はい  <br/> | カスタム ドメインがある場合、最高経営責任者など、最も価値のあるユーザーの電子メール アカウントを保護して、ドメインを保護するためには、フィッシング詐欺対策ポリシーを作成します。[フィッシング詐欺対策ポリシーを設定する](set-up-anti-phishing-policies.md)かを確認し、ガイドとしてこの例を使用してポリシーを作成する:」の使用例: ドメインとユーザーを保護するためにフィッシング詐欺対策ポリシー」。|
|**マルウェア対策エンジン** <br/> |はい  <br/> | 既定のポリシーを編集します。  <br/> • 一般的な添付ファイル フィルターの種類などを選択  <br/><br>  カスタムのマルウェア フィルター ポリシーを作成し、組織内の指定したユーザー、グループ、またはドメインに適用できます。  <br/> <br> 詳しくは、以下の資料を参照してください。  <br/> •[マルウェア対策保護](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx) <br/> •[マルウェア対策ポリシーを構成します。](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |
|**ATP の安全な添付ファイル機能** <br/> |いいえ  <br/> | 安全な添付ファイルのメイン ページで、SharePoint、OneDrive、およびマイクロソフトのチーム内のファイルを保護このチェック ボックス。  <br/>  • および有効にする分析ツールで SharePoint、OneDrive、マイクロソフトのチーム  <br/> <br> これらの設定では、新しい安全な添付ファイル ポリシーを追加します。  <br/>  • ブロック-現在および将来の e メールおよび検出されたマルウェアの添付ファイルをブロックする (このオプションを選択します)  <br/>  • 有効にする」にリダイレクト: (チェック ボックスをオンし、管理や検査など、電子メール アドレスを入力してください)  <br/>  • は、マルウェアの添付ファイルのスキャンがタイムアウトになるか、エラーが発生した場合に上記の選択を適用します (チェック ボックスをオン)  <br/>  • に適用される、受信者のドメインにドメインを (選択)  <br/>  <br>詳細: [Office 365 の ATP の安全な添付ファイル ポリシーを設定します](set-up-atp-safe-attachments-policies.md) <br/> |
|**ATP の安全なリンク** <br/> |はい  <br/> | この設定を組織全体の既定のポリシーに追加します。  <br/> • 内の安全なリンクを使用します。 Office 365 用リソース、オフィスの iOS と Android (このオプションを選択します)。  <br/> <br>特定の受信者に対するポリシーを推奨。  <br/>  • Url 書き換えし、するユーザーがリンクをクリックすると、既知の悪意のあるリンクの一覧に照らし合わせて確認 (このオプションを選択します)。  <br/>  • ダウンロード可能なコンテンツをスキャンするのには安全な添付ファイルを使用して (チェック ボックスをオン)。  <br/>  • に適用される、受信者のドメインにドメインを (選択) します。  <br/> <br> 詳細: [Office 365 の ATP の安全なリンク](atp-safe-links.md)です。  <br/> |
|**スパム対策 (メール フィルター)** <br/> |はい  <br/> | 何を監視するには。  <br/>  • はスパムが多すぎる、カスタム設定を選択し、迷惑メール フィルターの既定のポリシーを編集します。  <br/>  • なりすましインテリジェンス-自分のドメインのスプーフィングは、送信者を確認します。ブロックまたは、これらの送信者を許可します。<br/>  <br>詳細: [Office 365 の電子メール スパム対策の保護](anti-spam-protection.md)。  <br/> |
|**DKIM (DomainKeys は、メールを識別)** <br/> |はい  <br/> |DKIM 認証プロセスを保護する送信者と受信者の両方を偽造 (偽) では、フィッシング詐欺メールです。テナントには、ドメインの既定の署名が含まれています。テナントにカスタム ドメインを追加する場合は、追加の DKIM 署名を作成します。<br/> <br>詳細:[カスタム ドメインを Office 365 から送信された送信の電子メールを検証するために DKIM を使用](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email) <br/> |
   
## <a name="view-dashboards-and-reports-in-the-security-amp-compliance-center"></a>セキュリティ ダッシュ ボードおよびレポートを表示する&amp;コンプライアンス センター

これらのレポートとダッシュ ボードをお客様の環境の稼働状態の詳細についてを参照してください。これらのレポート内のデータは豊富なは、組織が Office 365 サービスを使用しているようになります。ここでは、何を監視してアクションを実行を理解します。詳細についてを参照してください:[では、Office 365 のセキュリティ レポート&amp;コンプライアンス センター](reports-in-security-and-compliance.md)です。
  
|ダッシュ ボード。|****説明****|
|:-----|:-----|
|脅威管理ダッシュ ボード  <br/> |セキュリティの脅威の管理] セクションで&amp;コンプライアンス センターへの報告ビジネスの意思決定者にどのような脅威のインテリジェンスは、まだ、既に処理されているを参照してくださいの脅威と便利なツールとしては、このダッシュ ボードを使用して、セキュリティで保護する、ビジネスです。  <br/> |
|脅威のエクスプ ローラー  <br/> |セキュリティの脅威の管理] セクションでは、この&amp;コンプライアンス センターです。調査中であるか、Office 365 テナントに対して攻撃が発生している場合、は、脅威を分析する脅威のエクスプ ローラーを使用します。脅威エクスプ ローラーに表示する攻撃の量、時間の経過と、脅威の種類や、攻撃者のインフラストラクチャでは、このデータを分析することができます。インシデントの一覧については、電子メールで疑わしいをマークすることもできます。  <br/> |
|レポート、ダッシュ ボード  <br/> |セキュリティの [レポート] セクションに&amp;、SharePoint Online 組織と Exchange Online 組織のコンプライアンス部門、監査の表示を報告します。アクセスすることも Azure Active Directory (AD) ユーザー サインインのレポートの場合、ユーザーの利用状況を報告して、Azure AD 監査ログ レポート] ページで表示します。  <br/> |
   
![セキュリティ&amp;コンプライアンス センターのダッシュ ボード](media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)
  
## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>追加の Exchange Online テナント全体の設定を構成します。

セキュリティとコンプライアンス センターでのセキュリティと Exchange 管理センターで保護するためのコントロールの多くも含まれます。両方の場所でこれらを構成する必要はありません。推奨されるその他の設定のいくつかを次に示します。 
  
|領域。|既定のポリシー。|推奨。|
|:-----|:-----|:-----|
|**メールの流れ**(トランスポート ルール)  <br/> |いいえ  <br/> | Ransomware から保護するためにメール フロー ルールを追加します。このブログ記事の「Exchange のトランスポート ルールを使用して追跡または ransomware によって使用されるファイル拡張子を持つ電子メールをブロックする方法」を参照してください: [ransomware を処理する方法](https://blogs.technet.microsoft.com/office365security/how-to-deal-with-ransomware/)です。<br><br/> 外部ドメインへのメールの自動転送を防止するトランスポート ルールを作成します。詳細については、[問題を緩和するクライアント外部転送規則セキュリティで保護されたスコア](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)を参照してください。<br/> <br>詳細:[メール フロー ルール (トランスポート ルール) では、Exchange オンライン](https://technet.microsoft.com/en-us/library/jj919238%28v=exchg.150%29.aspx) <br/> |
|**現代の認証を有効にします。** <br/> |いいえ  <br/> | Office 365 の最新の認証とは、多要素認証 (MFA) を使用するための前提条件です。メールを含む、クラウド リソースへのアクセスをセキュリティで保護するのには、MFA をお勧めします。<br/>  <br>これらのトピックを参照してください。  <br/> •[を有効または無効にする最新の認証では、Exchange オンライン](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) <br/> •[ビジネス オンラインの Skype: 最新の認証のため、テナントを有効にする](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/>  <br>Office 2016 クライアント、SharePoint Online では、およびビジネスのための OneDrive の最新の認証がデフォルトで有効です。  <br/>  <br>詳細: [Office クライアントと Office 365 を使用して最新の認証](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a) <br/> |
   
## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>SharePoint 管理センターのテナントの共有ポリシーを構成します。

基準計画の保護を開始して、保護レベルを増やすことでチームの SharePoint サイトを構成するためのマイクロソフトの推奨事項です。詳細については、「 [SharePoint のオンラインのセキュリティで保護されたサイトおよびファイル](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files)の使用」を参照していますください。
  
ベースライン レベルで構成されている SharePoint のチーム サイトでは、外部ユーザーと匿名アクセスのリンクを使用してファイルの共有を使用できます。電子メールでファイルを送信する代わりには、この方法をお勧めします。 
  
基準計画の保護の目標をサポートするには、ここで推奨されているテナントの共有ポリシーを構成します。個々 のサイトの設定を共有すると、ないより寛容なのですが、このテナント全体のポリシーよりも厳しいことができます。 
  
|領域。|既定のポリシー。|推奨。|
|:-----|:-----|:-----|
|**共有**(SharePoint のオンラインおよびビジネスのための OneDrive)  <br/> |はい  <br/> | 外部の共有は既定で有効にします。これらの設定を推奨します。<br/>  • は、外部ユーザーを認証するように共有し、リンク (デフォルト設定) に匿名アクセスを使用するを使用できます。  <br/>  • リンクに匿名アクセスは、この何日間で期限が切れます。30 日間など、必要な場合は、番号を入力します。<br/>  • 既定のリンクの種類: 内部 (のみ、組織内のユーザー)] を選択します。匿名のリンクを使用して共有したいユーザーは、[共有] メニューからこのオプションを選択する必要があります。<br/>  <br>詳細:[外部の共有の概要](https://support.office.com/article/c8a462eb-0723-4b0b-8d0a-70feafe4be85) <br/> |
   
SharePoint 管理者センターとビジネス管理センターの OneDrive には、同じ設定が含まれます。いずれかの管理センターの設定は、両方に適用されます。
  
## <a name="configure-settings-in-azure-active-directory"></a>Azure Active Directory 内の設定を構成します。

安全な環境のテナントのセットアップを完了する、Azure Active Directory でこれら 2 つの領域にアクセスすることを確認します。
  
### <a name="configure-named-locations-under-conditional-access"></a>(条件付きアクセス)] の下の名前付きの場所を構成します。

組織には、セキュリティで保護されたネットワーク アクセスのオフィスが含まれている場合は、名前付きの場所として Azure Active Directory に信頼される側の IP アドレスの範囲を追加します。この機能では、サインインのリスク イベントの偽陽性の報告されたの数を減らすのに役立ちます。 
  
[Azure Active Directory 内の名前付きの場所](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)を参照してください。
  
### <a name="block-apps-that-dont-support-modern-authentication"></a>現代の認証をサポートしていないアプリケーションをブロック

多要素認証では、最新の認証をサポートするアプリケーションが必要です。条件付きのアクセス ルールを使用して、最新の認証をサポートしていないアプリケーションをブロックできません。
  
セキュリティで保護された環境では、必ず最新の認証をサポートしていないアプリケーションの認証を無効にします。この設定がまもなくリリースされる、コントロールに Azure Active Directory で行うことができます。
  
間、SharePoint Online およびビジネスのための OneDrive のためには、次の方法のいずれかを使用します。
  
- PowerShell を使用して、[最新の認証を使用しないブロックのアプリケーション](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication)を参照してください。
    
- この構成は、SharePoint の管理センターで、「デバイスへアクセスのページ、「最新の認証を使用していないアプリケーションからのアクセスを制御する」ブロックを選択します。 
    
## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>クラウド アプリケーションのセキュリティ、または Office 365 のクラウド アプリケーションのセキュリティを開始します。

不審な動作は、[アラートのリスクを評価して自動的にアクションを実行するのには、Office 365 のクラウド アプリケーションのセキュリティを使用します。Office 365 の E5 の計画が必要です。
  
または、マイクロソフトのクラウド アプリケーションのセキュリティを使用して、詳細表示のアクセスを許可した後でも、包括的なコントロール、およびすべてのクラウド アプリケーション、Office 365 をなどの保護の強化を取得します。 
  
このソリューションでは、EMS の E5 のプランをお勧め、ためにを開始するクラウド アプリケーションのセキュリティを使用できるようにこの他の SaaS アプリケーションと、環境内をお勧めします。既定のポリシーと設定を開始します。
  
詳しくは、以下の資料を参照してください。
  
- [Cloud App Security を展開する](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
    
- [Microsoft Cloud App Security の詳細情報](https://www.microsoft.com/en-us/cloud-platform/cloud-app-security)
    
- [Office 365 Cloud App Security の概要](office-365-cas-overview.md)
    
![Cloud App Security ダッシュボード](media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)
  
## <a name="additional-resources"></a>その他のリソース

これらの記事とガイドは、Office 365 環境内のセキュリティ保護に関する規範的な追加の情報を提供します。
  
- [政治運動、慈善団体、およびその他のアジャイルな組織での Microsoft セキュリティ ガイダンス](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance)(特にクラウド専用環境ではどのような環境でこれらの推奨設定を使用できます) 
    
- [推奨セキュリティ ポリシーとユーザーとデバイスの構成](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations)(これらの推奨事項は、AD FS の環境に対するヘルプを含む) 
    

