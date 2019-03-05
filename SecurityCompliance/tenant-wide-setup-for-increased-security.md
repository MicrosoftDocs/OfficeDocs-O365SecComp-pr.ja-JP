---
title: セキュリティ強化のために、Office 365 テナントを構成する
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
description: Office 365 環境のセキュリティに影響を与えるテナント全体の設定に推奨される構成について説明します。セキュリティのニーズによっては、より多くのセキュリティを必要とする場合があります。これらの推奨事項を出発点として使用します。
ms.openlocfilehash: 249ccda6bdd474c853dc5e1941d49ea182e2dad1
ms.sourcegitcommit: 15983a08a4ae9c2050344172c7e957830ce3867e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "30373928"
---
# <a name="configure-your-office-365-tenant-for-increased-security"></a>セキュリティ強化のために、Office 365 テナントを構成する

このトピックでは、Office 365 環境のセキュリティに影響を与えるテナント全体の設定に推奨される構成について説明します。セキュリティのニーズによっては、より多くのセキュリティを必要とする場合があります。これらの推奨事項を出発点として使用します。
  
## <a name="check-office-365-secure-score"></a>Office 365 のセキュリティで保護されたスコアを確認する

office 365 のセキュリティで保護されたスコアは、通常のアクティビティとセキュリティ設定に基づいて office 365 組織のセキュリティを分析し、スコアを割り当てます。最初に、現在のスコアをメモしておきます。テナント全体の設定を調整すると、スコアが増加します。目標は最大スコアを達成することではなく、ユーザーの生産性に悪影響を及ぼすことがない環境を保護する機会に注意してください。「 [Office 365 のセキュリティスコアの紹介」を](office-365-secure-score.md)参照してください。
  
## <a name="tune-threat-management-policies-in-the-office-365-security-amp-compliance-center"></a>Office 365 セキュリティ&amp;コンプライアンスセンターで脅威管理ポリシーを調整する

Office 365 セキュリティ&amp;コンプライアンスセンターには、環境を保護する機能が含まれています。また、レポートとダッシュボードを使用して、監視してアクションを実行することもできます。既定のポリシー構成には、いくつかの領域があります。一部の領域には、既定のポリシーやルールは含まれません。脅威管理の設定を調整して、より安全な環境を構成するには、次のポリシーにアクセスしてください。 
  
|Area * * * *|既定のポリシーが含まれています * * * * *|推奨事項 * * * *|
|:-----|:-----|:-----|
|**フィッシング対策** <br/> |はい  <br/> | カスタムドメインがある場合は、CEO などの最も重要なユーザーの電子メールアカウントを保護し、ドメインを保護するために、フィッシング対策ポリシーを作成します。「[フィッシング対策ポリシーを設定](set-up-anti-phishing-policies.md)する」および「例: ユーザーとドメインを保護するためのフィッシング対策ポリシー」の例を使用してポリシーを作成します。|
|**マルウェア対策エンジン** <br/> |はい  <br/> | 既定のポリシーを編集します。  <br/> &ensp;&ensp;•一般的な添付ファイルの種類のフィルター— [オン]  <br/><br>  また、カスタムマルウェアフィルターポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することもできます。  <br/> <br> 詳しくは、以下の資料を参照してください。  <br/> &ensp;&ensp;•[マルウェア対策保護](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx) <br/> &ensp;&ensp;•[マルウェア対策ポリシーを構成する](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |
|**ATP の安全な添付ファイル機能** <br/> |なし  <br/> | 「安全な添付ファイル」のメインページで、このボックスをオンにして、SharePoint、OneDrive、Microsoft Teams のファイルを保護します。  <br/>  &ensp;&ensp;• SharePoint、OneDrive、Microsoft Teams の ATP を有効にします。  <br/> <br> 次の設定を使用して、新しい安全な添付ファイルポリシーを追加します。  <br/>  &ensp;&ensp;•ブロック: 検出されたマルウェアを使用して、現在の電子メールと添付ファイルをブロックする (このオプションを選択する)  <br/>  &ensp;&ensp;•リダイレクトの有効化— (このボックスをオンにして、管理者や検疫アカウントなどの電子メールアドレスを入力してください)  <br/>  &ensp;&ensp;•添付ファイルのマルウェアスキャンがタイムアウトまたはエラーが発生した場合は、上記の選択を適用します (このチェックボックスをオンにします)。  <br/>  &ensp;&ensp;•適用先-受信者ドメイン is (ドメインを選択してください)  <br/>  <br>詳細情報: [Office 365 の ATP の安全な添付ファイルのポリシーを設定](set-up-atp-safe-attachments-policies.md)する <br/> |
|**ATP の安全なリンク** <br/> |はい  <br/> | この設定を組織全体の既定のポリシーに追加します。  <br/> &ensp;&ensp;•安全なリンクの使用: office 365 ProPlus、office for iOS および Android (このオプションを選択します)。  <br/> <br>特定の受信者に推奨されるポリシー:  <br/>  &ensp;&ensp;•ユーザーがリンクをクリックしたときに、既知の悪意のあるリンクの一覧に対して url が書き換えられ、チェックされます (このオプションを選択します)。  <br/>  &ensp;&ensp;•安全な添付ファイルを使用して、ダウンロード可能なコンテンツをスキャンします (このチェックボックスをオンにします)。  <br/>  &ensp;&ensp;•適用先-受信者ドメイン is (ドメインを選択してください)。  <br/> <br> 詳細については、「 [Office 365 の ATP の安全なリンク](atp-safe-links.md)」を参照してください。  <br/> |
|**スパム対策 (メールフィルター)** <br/> |はい  <br/> | 監視対象:  <br/>  &ensp;&ensp;•スパム数が多すぎます。カスタム設定を選択し、既定のスパムフィルターポリシーを編集します。  <br/>  &ensp;&ensp;•スプーフィングインテリジェンス—ドメインをスプーフィングしている送信者を確認します。これらの送信者を禁止または許可します。<br/>  <br>詳細については[、「Office 365 電子メールのスパム対策保護](anti-spam-protection.md)」を参照してください。  <br/> |
|***電子メール認証*** <br/> |はい  <br/> |電子メール認証は、ドメインネームシステム (DNS) を使用して、電子メールの送信者に関する検証可能な情報を電子メールメッセージに追加します。office 365 は、既定のドメイン (onmicrosoft.com) に対して電子メール認証を設定しますが、office 365 管理者はカスタムドメインに対して電子メール認証を使用することもできます。3つの認証方法が使用されます。<br/> <br> &ensp;&ensp;• Sender Policy Framework (または SPF)。<br/>&ensp;&ensp;&ensp;&ensp;-セットアップの場合は、「 [Set up SPF in Office 365」を参照してスプーフィングを防止](set-up-spf-in-office-365-to-help-prevent-spoofing.md)してください。 <br/> &ensp;&ensp;• domainkeys で識別されたメール (dkim)。 <br/> &ensp;&ensp;&ensp;&ensp;-「 [Office 365 でカスタムドメインのメールに dkim を使用する](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)」を参照してください。 <br>&ensp;&ensp;&ensp;&ensp;-dkim の構成が完了したら、セキュリティ&amp;コンプライアンスセンターでそれを有効にします。<br/> &ensp;&ensp;•ドメインベースのメッセージ認証、レポート、および準拠 (DMARC)。 <br/> &ensp;&ensp;&ensp;&ensp;-DMARC セットアップの場合は、 [DMARC を使用して Office 365 で電子メールを検証](use-dmarc-to-validate-email.md)します。<br/>  <br/>
|

> [!NOTE]
> spf、ハイブリッド展開、およびトラブルシューティングの標準的でない展開の場合: [Office 365 では、スプーフィングを防止するために Sender Policy Framework (SPF) を使用する方法に](how-office-365-uses-spf-to-prevent-spoofing.md)ついて説明します。

## <a name="view-dashboards-and-reports-in-the-security-amp-compliance-center"></a>セキュリティ&amp; /コンプライアンスセンターのダッシュボードとレポートを表示する

環境の正常性の詳細については、以下のレポートとダッシュボードを参照してください。これらのレポートのデータは、組織が Office 365 サービスを使用しているほど充実したものになります。ここでは、監視してアクションを実行できるものについて理解しておきます。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのレポート](reports-in-security-and-compliance.md)」を参照してください。
  
|ダッシュボード * * * *|****説明****|
|:-----|:-----|
|脅威管理ダッシュボード  <br/> |セキュリティ&amp; /コンプライアンスセンターの [脅威の管理] セクションで、このダッシュボードを使用して、既に処理されている脅威を確認し、ビジネス上の意思決定者に対して、セキュリティを確保するために既に実行されている脅威を報告する便利なツールとして使用します。出張.  <br/> |
|脅威エクスプローラー  <br/> |これは、セキュリティ&amp; /コンプライアンスセンターの [脅威の管理] セクションにもあります。Office 365 テナントに対する攻撃を調査している、または攻撃を受けている場合は、脅威エクスプローラーを使用して脅威を分析します。脅威エクスプローラーは、時間の経過と共に攻撃の量を示します。また、脅威ファミリ、攻撃インフラストラクチャなどによって、このデータを分析することができます。インシデントリストに対して疑わしい電子メールをマークすることもできます。  <br/> |
|レポート—ダッシュボード  <br/> |セキュリティ&amp; /コンプライアンスセンターの [レポート] セクションで、SharePoint online および Exchange Online 組織の監査レポートを表示します。[レポートの表示] ページから、azure Active Directory (AD) ユーザーのサインインレポート、ユーザーアクティビティレポート、および azure AD 監査ログにアクセスすることもできます。  <br/> |
   
![セキュリティ&amp;コンプライアンスセンターダッシュボード](media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)
  
## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>その他の Exchange Online テナント全体の設定を構成する

Exchange 管理センターでのセキュリティと保護の多くの制御は、セキュリティ/コンプライアンスセンターにも含まれています。両方の場所にこれらを構成する必要はありません。推奨されるその他のいくつかの設定を以下に示します。 
  
|Area * * * *|既定のポリシーが含まれています * * * * *|推奨事項 * * * *|
|:-----|:-----|:-----|
|**メールフロー**(メールフロールール (トランスポートルールとも呼ばれる)|なし|ランサムウェアから保護できるように、メールフロールールを追加します。「ランサムウェア対策に[対処する方法](https://blogs.technet.microsoft.com/office365security/how-to-deal-with-ransomware/)」の記事「Exchange トランスポートルールを使用して、ランサムウェアによって使用されているファイル拡張子を使用してメールを追跡またはブロックする方法」を参照してください。<br><br/> メールフロールールを作成して、外部ドメインに電子メールを自動的に転送できないようにします。詳細については、「[セキュリティで保護されたスコアでクライアントの外部転送ルールを軽減](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)する」を参照してください。<br/><br/> 詳細情報: [Exchange Online のメールフロールール (トランスポートルール)](https://technet.microsoft.com/en-us/library/jj919238%28v=exchg.150%29.aspx)|
|**モダン認証を有効にする**|なし|Office 365 の先進認証は、多要素認証 (MFA) を使用するための前提条件です。メールを含むクラウドリソースへのアクセスを保護するために、MFA が推奨されています。<br/><br/> 次のトピックを参照してください。  <br/>• [Exchange Online で先進認証を有効または無効](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662)にする <br/>• [Skype for business Online: 最新認証のためにテナントを有効にする](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/><br/> モダン認証は、Office 2016 クライアント、SharePoint Online、および OneDrive for business では既定で有効になっています。 <br/><br/> 詳細情報: office [365 のモダン認証を office クライアントで使用する](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a)|
   
## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>SharePoint 管理センターでテナント全体の共有ポリシーを構成する

SharePoint チームサイトを保護レベルを高くして構成する場合は、ベースライン保護から始めることをお勧めします。詳細については、「 [Secure SharePoint Online sites and files](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files) 」を参照してください。
  
ベースラインレベルで構成された SharePoint チームサイトでは、匿名アクセスリンクを使用して外部ユーザーとファイルを共有できます。この方法は、電子メールでファイルを送信する代わりに推奨されます。 
  
ベースライン保護の目的をサポートするには、ここで推奨されているように、テナント全体の共有ポリシーを構成します。個々のサイトの共有設定は、このテナント全体のポリシーよりも制限がありますが、制限はありません。 
  
|Area * * * *|既定のポリシーが含まれています * * * * *|推奨事項 * * * *|
|:-----|:-----|:-----|
|**共有**(SharePoint Online と OneDrive for business)|はい|既定では、外部共有が有効になっています。これらの設定をお勧めします。<br/>•認証済み外部ユーザーへの共有と匿名アクセスリンクの使用を許可します (既定の設定)。 <br/>  •匿名アクセスリンクの有効期限がこの日数を過ぎています。必要に応じて、30日などの数値を入力します。<br/>•既定のリンクの種類— [内部] (組織内のユーザーのみ) を選択します。匿名リンクを使用して共有を希望するユーザーは、[共有] メニューからこのオプションを選択する必要があります。<br/><br/> 詳細情報:[外部共有の概要](https://support.office.com/article/c8a462eb-0723-4b0b-8d0a-70feafe4be85)|
   
SharePoint 管理センターと OneDrive for business 管理センターには、同じ設定が含まれています。どちらの管理センターの設定も、両方に適用されます。
  
## <a name="configure-settings-in-azure-active-directory"></a>Azure Active Directory で設定を構成する

セキュリティで保護された環境でのテナント全体のセットアップを完了するには、Azure Active Directory のこれら2つの領域を参照してください。
  
### <a name="configure-named-locations-under-conditional-access"></a>名前付きの場所を構成する (条件付きアクセスの場合)

セキュリティで保護されたネットワークアクセスを備えたオフィスが組織に含まれている場合は、名前付きの場所として、信頼できる IP アドレス範囲を Azure Active Directory に追加します。この機能により、サインインリスクイベントに対して報告される誤検知の数を減らすことができます。 
  
参照: [Azure Active Directory の名前付きの場所](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)
  
### <a name="block-apps-that-dont-support-modern-authentication"></a>モダン認証をサポートしていないアプリをブロックする

多要素認証では、先進認証をサポートするアプリが必要です。モダン認証をサポートしていないアプリは、条件付きアクセスルールを使用してブロックすることはできません。
  
セキュリティで保護された環境では、先進認証をサポートしていないアプリの認証を無効にしてください。Azure Active Directory でこれを行うには、近日中にコントロールを使用します。
  
その間、次のいずれかの方法を使用して、SharePoint Online と OneDrive for business でこれを実行します。
  
- PowerShell を使用する場合は、「[モダン認証を使用していないアプリをブロックする](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication)」を参照してください。
    
- これを SharePoint 管理センターの [デバイスアクセス] ページ ("モダン認証を使用していないアプリからアクセスを制御する") で構成します。[ブロック] を選択します。 
    
## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>cloud app security または Office 365 cloud app security の使用を開始する

Office 365 Cloud App Security を使用して、リスクを評価し、疑わしいアクティビティについての警告を行い、自動的にアクションを実行します。Office 365 E5 プランが必要です。
  
または、Microsoft cloud App Security を使用して、アクセスが許可された後でも、Office 365 を含むすべてのクラウドアプリケーションに対する包括的な制御と、保護を強化した後でも、より深い可視性を得ることができます。 
  
このソリューションでは EMS E5 プランが推奨されるため、これを環境内の他の SaaS アプリケーションで使用できるように、Cloud App Security から始めることをお勧めします。既定のポリシーと設定を使用して開始します。
  
詳しくは、以下の資料を参照してください。
  
- [Cloud App Security を展開する](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
    
- [Microsoft Cloud App Security の詳細情報](https://www.microsoft.com/en-us/cloud-platform/cloud-app-security)
    
- [Office 365 Cloud App Security の概要](office-365-cas-overview.md)
    
![Cloud App Security ダッシュボード](media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)
  
## <a name="additional-resources"></a>その他の技術情報

これらの記事およびガイドでは、Office 365 環境を保護するためのその他の規範となる情報を提供します。
  
- [政治キャンペーン、非営利組織、およびその他のアジャイル組織のための Microsoft security ガイダンス](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance)(特にクラウドのみの環境では、これらの推奨事項を使用できます) 
    
- [id とデバイスに推奨されるセキュリティポリシーと構成](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations)(これらの推奨事項は、AD FS 環境のヘルプを含みます) 
    

