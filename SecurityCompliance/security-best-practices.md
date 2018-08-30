---
title: Office 365 のセキュリティのベスト プラクティス
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
description: これらの推奨されるベスト プラクティスに従って、データ漏洩やセキュリティを侵害されたアカウントの可能性を最小限に抑えます。
ms.openlocfilehash: 245302af0b08a4ee8183345fc386fe47985c93dd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532711"
---
# <a name="security-best-practices-for-office-365"></a>Office 365 のセキュリティのベスト プラクティス

これらの推奨されるベスト プラクティスに従って、データ漏洩やセキュリティを侵害されたアカウントの可能性を最小限に抑えます。
  
この資料には、ベスト ・ プラクティスの簡単な一覧が含まれています。詳細な詳細な分析とセキュリティの設定の詳細についてを参照してください[Office 365 のセキュリティ ロードマップ: 最初の 30 日、90 日間での内外の優先順位のトップ](security-roadmap.md)。その記事で情報を入手できます、実際の攻撃の調査に基づいて、上の Microsoft Office 365 cybersecurity エキスパートがリスクを評価し、最も重要なセキュリティ、コンプライアンス、および情報を実装する方法についての指導を提供Office 365 テナントを保護するためのコントロールを保護します。脅威の優先順位を付ける、技術戦略は、脅威に変換し、体系的なアプローチの機能とコントロールを実装する方法を学習します。
  
## <a name="use-office-365-secure-score"></a>Office 365 のセキュリティで保護されたスコアを使用します。

セキュリティで保護されたスコアは、さらにリスクの軽減を行うことができることをお勧めするセキュリティ分析ツールです。セキュリティで保護されたスコアを使用して、Office 365 の設定と活動を調べ、マイクロソフトによって確立されたベースラインを比較します。調整方法に問題が、セキュリティのベスト プラクティスに基づくスコアが表示されます。セキュリティで保護されたスコアを取得し、Office 365 の組織のセキュリティを強化するために使用する方法の詳細については、 [Office 365 のセキュリティで保護されたスコアを導入すること](office-365-secure-score.md)を参照してください。
  
セキュリティで保護されたスコアを試したいですか。
  
[Office 365 にサインイン](https://www.office.com/signin)、Office 365 の[Office 365 の管理者の役割](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)の役割が割り当てられている、職場、学校のアカウントを使用しています。
  
アクセス時に得点をセキュリティで保護された[https://SecureScore.office.com](https://SecureScore.office.com)。
  
## <a name="use-multi-factor-authentication-mfa"></a>多要素認証を使用する (MFA)

MFA では、電話、テキスト メッセージ、または自分のパスワードを正しく入力した後、スマート フォン上のアプリ通知を確認するユーザーを要求することによって強力なパスワード方式に追加の保護レイヤーを追加します。MFA は、ユーザーのパスワードが危険にさらされた場合でも、Office 365 ユーザー アカウントがまだ不正アクセスから保護します。追加の課題が満たされた後までのアカウントにアクセスを許可しないために、アカウントが保護されています。危険にさらされた、または盗まれたパスワードは、十分ではありません。
  
- [Office 365 の展開の多要素認証の計画](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [Office 365 のユーザーに対して多要素認証を設定します](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
## <a name="use-office-365-cloud-app-security"></a>Office 365 のクラウド アプリケーションのセキュリティを使用します。

異常なアクティビティを追跡し、それに基づいて行動する、ビジネス ・ ニーズに基づいてポリシーを設定します。管理者が大量のデータのダウンロードなど、異常なまたは危険なユーザー アクティビティを確認するよう Office 365 のクラウド アプリケーションのセキュリティの警告を設定複数サインインの試行、または不明なまたは危険な IP アドレスからのサインインができませんでした。組織で Office 365 エンタープライズ E5 計画には、Office 365 のクラウド アプリケーションのセキュリティをすぐに使用を開始できます。企業のさまざまな計画があれば、Office 365 のクラウド アプリケーションのセキュリティのアドオンとして購入できます。
  
- [O365 クラウド アプリケーションのセキュリティの概要](office-365-cas-overview.md)
    
- [Office 365 Cloud App Security を有効にする](turn-on-office-365-cas.md)
    
## <a name="secure-mail-flow"></a>セキュリティで保護されたメールの流れ

リッチでは、Exchange のオンライン保護機能、各電子メール メッセージの送信者の身元についてより確実な保証を得るし、不明なマルウェア、ウイルス、および悪意のある Url を電子メール経由で送信される保護を実装します。
  
- 組織の[Office 365 の電子メール スパム対策の保護](anti-spam-protection.md)ポリシーを構成します。 
    
- について説明し、[安全な添付ファイルと安全なリンクの高度な脅威保護](https://technet.microsoft.com/library/mt148491.aspx)します。
    
- [組織に対するマルウェア対策保護を追加](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx)します。
    
- について学習し、ユーザーの[Office 365 の電子メール メッセージでの安全性のヒント](safety-tips-in-office-365.md)を有効にします。 
    
- Office 365 の組織のカスタム ドメインを使用する場合は、組織から送信されたメールを検証し、なりすましを防ぐには SPF、DKIM、および DMARC を設定します。
    
  - [スプーフィングを防止するために Office 365 の SPF を設定](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx)します。
    
  - [カスタム ドメインを Office 365 から送信された送信の電子メールを検証するために DKIM を使用](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx)します。
    
  - [Office 365 で電子メールを検証するために DMARC を使用](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)します。
    
## <a name="enable-mailbox-audit-logging"></a>メールボックス監査ログを有効にする

Office 365; でのいくつかの監査ログが自動的に有効にただし、メールボックスの監査ログ収集既定で有効にできません。Office 365 のすべてのユーザーのメールボックスの監査ログにするには、Exchange オンライン PowerShell を使用します。については、[メールボックスを Office 365 で監査を有効にする](https://go.microsoft.com/fwlink/p/?LinkID=626109)を参照してください。
  
監査ログを収集することができますを有効にした後[では、Office 365 のセキュリティ監査ログを検索する&amp;コンプライアンス センター](search-the-audit-log-in-security-and-compliance.md)メッセージ、および委任されたユーザー、メールボックスの所有者によって実行されるその他の活動を送信する、ユーザーのメールボックスにログオンしたことを確認するにはまたは管理者を選択します。Office 365 に含まれるメールボックス アクティビティの一覧については、監査ログを既定では、 [Exchange メールボックスの動作](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities)を参照してください。
  
監査ログ、監査ログにエントリを保存するのには時間の変更などで実行できるその他のアクションについては、[メールボックスが Exchange 2016 のログを監査](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx)を参照してください。
  
## <a name="configure-data-loss-prevention-dlp"></a>データ損失防止 (DLP) を構成します。

DLP では、機密性の高いデータを識別し、ユーザーが誤ってまたは意図的にデータを共有することを防ぐためのポリシーを作成できます。DLP は、ユーザーは、ワークフローを中断することがなく準拠で維持できるようにするため Exchange Online、SharePoint Online では、および OneDrive を含む Office 365 の間で動作します。詳細については、[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)を参照してください。
  
## <a name="use-customer-lockbox"></a>お客様のロック ボックスを使用します。

Office 365 管理者の場合は、マイクロソフトのサポート エンジニアがヘルプ セッション中に、データにアクセスする方法を制御するのに顧客のロック ボックスを使用できます。エンジニアがトラブルシューティングし、問題を修正するのには、データへのアクセスを必要とする場合、お客様のロック ボックスを使用すると、承認またはアクセス権の要求を拒否できます。それを承認すると、エンジニアがデータにアクセスできます。各要求には、有効期限、および問題が解決されると、要求は閉じられ、アクセスが無効にします。お客様のロック ボックスは、計画に含まれる、Office 365 エンタープライズ 5、またはその他の Office 365 エンタープライズ プランに個別のサブスクリプションを購入することができます。については、 [Office 365 ユーザーのロック ボックス要求](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2)を参照してください。
  
## <a name="try-it-yourself"></a>試してみよう
<a name="SecureScore"> </a>

これらのセキュリティ機能を運用環境に導入する前に、Office 365 の試用版サブスクリプションでの作業を参照してください。
  
- [Office 365 の試用版サブスクリプションを作成します。](https://technet.microsoft.com/library/mt736406.aspx)
    
- [構成およびユーザー アカウントの MFA をテストします。](https://technet.microsoft.com/library/mt492459.aspx)
    
- [構成およびグローバル管理者のアクティビティを通知するのには Office 365 のクラウド アプリケーションのセキュリティをテストします。](https://technet.microsoft.com/library/mt757250.aspx)
    
- [構成および不審な電子メールの分析ツールをテストします。](https://technet.microsoft.com/library/mt490479.aspx)
    
- 上記の手順のそれぞれの試用版サブスクリプションの[Office 365 のセキュリティで保護されたスコア](https://securescore.office.com/)を確認します。 
    

