---
title: Office 365 のセキュリティのベスト プラクティス
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 以下の推奨されるベストプラクティスに従って、データ違反または侵害されたアカウントの可能性を最小限に抑えます。
ms.openlocfilehash: bd4b911cd5972b7d6dc9b55c17e375d326b1d571
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264639"
---
# <a name="security-best-practices-for-office-365"></a>Office 365 のセキュリティのベスト プラクティス

以下の推奨されるベストプラクティスに従って、データ違反または侵害されたアカウントの可能性を最小限に抑えます。
  
この記事には、ベストプラクティスの簡単な一覧が記載されています。 詳細な分析とセキュリティの設定に関する情報については、「 [Office 365 セキュリティロードマップ: 最初の30日間、90日以降の優先度の高いもの](security-roadmap.md)を参照してください。 この記事では、Microsoft Office 365 cybersecurity のトップの専門家が、リスクを評価し、最も重要なセキュリティ、コンプライアンス、情報を実装する方法について指導する、現実世界の攻撃の調査に基づく情報を提供します。Office 365 テナントを保護するための保護制御。 脅威の優先度を設定し、脅威を技術的戦略に変換した後、機能と制御を実装するための体系的なアプローチを採用する方法について説明します。
  
## <a name="use-office-365-secure-score"></a>Office 365 のセキュリティで保護されたスコアの使用

セキュリティで保護されたスコアは、リスクをさらに軽減するために推奨されるセキュリティ分析ツールです。 セキュリティで保護されたスコアは、Office 365 の設定とアクティビティを調べて、Microsoft によって確立された基準と比較します。 最適なセキュリティプラクティスの調整に基づいて、スコアが得られます。 セキュリティで保護されたスコアを取得し、それを使用して office 365 組織のセキュリティを強化する方法の詳細については、「 [office 365 のセキュリティで保護さ](office-365-secure-score.md)れたスコアを導入する」を参照してください。
  
セキュリティで保護されたスコアを試す場合
  
office 365 について office の[管理者の役割](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)の役割に割り当てられている職場または学校のアカウントを使用して、 [office 365 にサインイン](https://www.office.com/signin)します。
  
セキュリティで保護さ[https://SecureScore.office.com](https://SecureScore.office.com)れたスコアへのアクセス
  
## <a name="use-multi-factor-authentication-mfa"></a>多要素認証 (MFA) を使用する

MFA は、パスワードを正確に入力した後に、スマートフォンでの通話、テキストメッセージ、またはアプリの通知の確認をユーザーに要求することで、強力なパスワード戦略に保護の層を追加します。 MFA が設定されていると、ユーザーのパスワードが侵害された場合でも、Office 365 のユーザーアカウントは承認されていないアクセスから保護されたままです。 アカウントが保護されるのは、追加のチャレンジが満たされるまでアカウントへのアクセスが許可されないためです。 侵害または盗難にあったパスワードが十分ではありません。
  
- [Office 365 の展開で多要素認証を計画する](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)

- [Office 365 の多要素認証を設定する](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)

## <a name="use-office-365-cloud-app-security"></a>Office 365 Cloud App Security の使用

ビジネスニーズに基づいてポリシーを設定し、異常なアクティビティを追跡して、それに対処します。 Office 365 Cloud App Security を使用して通知を設定することで、管理者は大量のデータのダウンロード、サインイン試行の失敗、不明または危険な IP アドレスからのサインインなど、不審で、または危険なユーザーアクティビティを確認できます。 office 365 Enterprise E5 プランを持つ組織では、すぐに office 365 Cloud App Security の使用を開始することができます。 エンタープライズプランが異なる場合は、Office 365 Cloud App Security をアドオンとして購入できます。
  
- [O365 Cloud App Security の概要](office-365-cas-overview.md)

- [Office 365 Cloud App Security を有効にする](turn-on-office-365-cas.md)

## <a name="secure-mail-flow"></a>セキュリティで保護されたメールフロー

Exchange Online Protection の豊富な機能セットを実装し、各電子メールメッセージの送信者の id についての保証を強化し、電子メールによって送信される不明なマルウェア、ウイルス、および悪意のある url から保護します。
  
- 組織の[Office 365 電子メールのスパム対策保護](anti-spam-protection.md)ポリシーを構成します。

- [「安全な添付ファイルと安全なリンク](https://technet.microsoft.com/library/mt148491.aspx)」について説明し、Advanced threat protection を使用します。

- [組織にマルウェア対策保護を追加](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx)します。

- ユーザーのために[Office 365 の電子メールメッセージの安全性](safety-tips-in-office-365.md)に関するヒントについて説明し、有効にします。

- Office 365 で組織のカスタムドメインを使用している場合は、SPF、dkim、DMARC を設定して、組織によって送信されたメールを検証し、スプーフィングを防止するために、次のようにします。

  - [スプーフィングを防止するために、Office 365 で SPF をセットアップ](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)します。

  - [dkim を使用して、Office 365 でカスタムドメインから送信される送信電子メールを検証](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)します。

  - [DMARC を使用して、Office 365 で電子メールを検証](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)します。

## <a name="enable-mailbox-audit-logging"></a>メールボックス監査ログを有効にする

Office 365 では、一部の監査ログが自動的に有効になります。ただし、メールボックス監査ログは既定で有効になっていません。 Office 365 のすべてのユーザーメールボックスの監査ログをオンにするには、Exchange Online PowerShell を使用します。 詳細については、「 [Enable mailbox auditing in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=626109)」を参照してください。
  
監査ログを有効にした後、 [Office 365 セキュリティ&amp;コンプライアンスセンターで監査ログを検索](search-the-audit-log-in-security-and-compliance.md)して、ユーザーのメールボックス、送信済みメッセージ、およびメールボックスの所有者が実行したその他のアクティビティ (委任されたユーザー) によって実行されたユーザーを見つけることができます。または管理者。 既定で Office 365 監査ログに含まれるメールボックスアクティビティの一覧については、「 [Exchange mailbox アクティビティ](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities)」を参照してください。
  
監査ログで実行できるその他のアクションの詳細については、「 [Exchange 2016 のメールボックス監査ログ](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx)」を参照してください。
  
## <a name="configure-data-loss-prevention-dlp"></a>データ損失防止 (DLP) を構成する

DLP を使用すると、機密データを識別し、ポリシーを作成して、ユーザーが偶然または故意にデータを共有するのを防ぐのに役立ちます。 DLP は、Exchange online、SharePoint Online、および OneDrive を含む Office 365 に対して機能するため、ワークフローを中断することなく、ユーザーが準拠し続けることができます。 詳しくは、「[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)」を参照してください。
  
## <a name="use-customer-lockbox"></a>カスタマーロックボックスを使用する

Office 365 管理者はカスタマー ロックボックスを使用して、Microsoft のサポート エンジニアがヘルプ セッション中にデータにアクセスする方法を制御することができます。 問題をトラブルシューティングして解決するために、エンジニアがデータへのアクセスを要求した場合、カスタマー ロックボックスを使用してアクセス権の要求を承認または拒否することができます。 承認すると、エンジニアはデータにアクセスできるようになります。 各要求には有効期限があり、問題が解決されると、要求は閉じられ、アクセスは取り消されます。 お客様のロックボックスは office 365 enterprise E5 プランに含まれています。または、他の office 365 Enterprise プランと別のサブスクリプションを購入することもできます。 詳細については、「 [Office 365 の顧客ロックボックス要求](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2)」を参照してください。
  
## <a name="try-it-yourself"></a>自分で試してみる
<a name="SecureScore"> </a>

これらのセキュリティ機能を運用環境で採用する前に、Office 365 試用版サブスクリプションで作業してください。
  
- [Office 365 試用版サブスクリプションを作成する](https://technet.microsoft.com/library/mt736406.aspx)

- [ユーザーアカウントの MFA を構成およびテストする](https://technet.microsoft.com/library/mt492459.aspx)

- [Office 365 Cloud App Security を構成およびテストして、グローバル管理者のアクティビティを通知する](https://technet.microsoft.com/library/mt757250.aspx)

- [疑わしい電子メールの ATP を構成およびテストする](https://technet.microsoft.com/library/mt490479.aspx)

- 上記の各手順について、試用版サブスクリプションの[Office 365 セキュリティスコア](https://securescore.office.com/)を確認する