---
title: Office 365 でフィッシング対策保護を調整する
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 管理者は、フィッシングメッセージがどのように使用されたのかや、今後のフィッシング対策メッセージを回避するために何を行う必要があるかを特定する方法について説明します。
ms.openlocfilehash: b17cdc6ec6cfc07642a6a40657009b46b83f1559
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156349"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a>Office 365 でフィッシング対策保護を調整する

Office 365 には、既定で有効になっているさまざまなフィッシング対策機能が用意されていますが、一部のフィッシングメッセージが依然としてメールボックスに届く可能性があります。 このトピックでは、フィッシングメッセージが通過した理由を検出するために実行できることと、誤って事態を発生さ_せず_に、Exchange Online 組織のフィッシング対策設定を調整する方法について説明します。

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>最初に、侵害されたアカウントを処理して、より多くのフィッシングメッセージを取得することを禁止していることを確認してください。

フィッシングメッセージの結果として受信者のアカウントが侵害された場合は、「 [Office 365 で侵害された電子メールアカウントに応答する](responding-to-a-compromised-email-account.md)」の手順を実行します。

サブスクリプションに Advanced Threat Protection (ATP) が含まれている場合は、 [Office 365 脅威インテリジェンス](office-365-ti.md)を使用して、フィッシングメッセージを受信した他のユーザーを識別できます。 フィッシングメッセージをブロックするための追加のオプションがあります。

- [ATP の安全なリンク](set-up-atp-safe-links-policies.md)

- [ATP の安全な添付ファイル機能](set-up-atp-safe-attachments-policies.md)

- [ATP のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)。 ポリシーの**高度なフィッシングしきい値**は、**標準**から**アグレッシブ**、アグレッシブ、または**最も積極的**なものに一時的に増やすことができます。 ****

これらの ATP 機能が有効になっていることを確認します。

## <a name="report-the-phishing-message-to-microsoft"></a>フィッシングメッセージを Microsoft に報告する

フィッシングメッセージの報告は、Office 365 のすべてのお客様を保護するために使用されるフィルターを調整するのに役立ちます。

フィッシングメッセージを新しい、それ以外の空のメッセージの_添付ファイルとして_ **phish@office365.microsoft.com**に送信します。 元のメッセージを転送するだけではありません。それ以外の場合は、元のメッセージヘッダーを調べることはできません。 または、Outlook または web 上の Outlook (旧称 Outlook Web App) で[レポートメッセージ](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in)アドインを使用することもできます。

詳細については、「[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。

## <a name="inspect-the-message-headers"></a>メッセージヘッダーを検査する

フィッシングメッセージのヘッダーを調べて、より多くのフィッシングメッセージが送られないようにすることができるかどうかを確認できます。 言い換えると、メッセージヘッダーを調べると、でフィッシングメッセージを許可する責任がある、組織内のすべての設定を識別するのに役立ちます。

具体的には、メッセージヘッダーの**スパム対策**ヘッダーフィールドを調べて、スパムフィルター Verdict (sfv) の値で、スキップされたスパムまたはフィッシングのフィルター処理が表示されることを確認する必要があります。 フィルター処理をスキップするメッセージには、 `SCL:-1`のエントリがあります。これは、サービスによって決定されたスパムまたはフィッシング verdicts を上書きすることによって、このメッセージが許可される設定の1つになります。 メッセージヘッダーと、使用可能なすべてのスパム対策およびフィッシングメッセージヘッダーの完全な一覧を取得する方法の詳細については、「[スパム対策メッセージヘッダー](https://docs.microsoft.com/office365/SecurityCompliance/anti-spam-message-headers)」を参照してください。

## <a name="best-practices-to-stay-protected"></a>保護を維持するためのベストプラクティス

- Office 365 組織のセキュリティ設定を評価するために、月単位で、[セキュリティで保護されたスコア](microsoft-secure-score.md)を実行します。

- [スプーフィングインテリジェンスレポート](learn-about-spoof-intelligence.md)を定期的に確認し、[フィッシング対策ポリシーのスプーフィング対策保護を有効](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy)にして、疑わしいメッセージをユーザーの迷惑メールフォルダーに配信する代わりに、そのメッセージを**検疫**します。

- [脅威保護状態レポート](view-reports-for-atp.md#threat-protection-status-report)を定期的に確認します。

- ユーザーによっては、スパム対策ポリシーの [送信者を許可する] または [ドメインを許可する] の一覧に独自のドメインを設定することで、フィッシングメッセージを誤って許可することがあります。 これを行う場合は、細心の注意を払う必要があります。 この構成では、一部の正当なメッセージが許可されますが、通常は Office 365 スパムまたはフィッシングフィルターによってブロックされる悪意のあるメッセージも許可されます。

  ドメイン内の送信者によっ365て禁止されている正当なメッセージ (誤検知) を処理する最善の方法は、office 365 のすべての電子メールドメインについて、DNS の SPF、dkim、および DMARC レコードを完全に完全に構成することです。

  - SPF レコードが、ドメイン内の送信者の電子メールの_すべて_のソースを識別していることを確認します (サードパーティのサービスを忘れないでください)。

  - ハード fail (\-) を使用して、承認されていない送信者が電子メールシステムによって拒否されるようにします。 [スプーフィングインテリジェンス](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence)を使用すると、ドメインを使用している送信者を特定し、SPF レコードに承認されたサードパーティの送信者を含めることができます。

  構成手順については、以下を参照してください。
  
  - [スプーフィングを防止するために Office 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)

  - [DMARC を使用して Office で電子メールを検証する365](use-dmarc-to-validate-email.md)

- 可能な限り、自分のドメインのメールを Office 365 に直接配信することをお勧めします。 言い換えると、Office 365 ドメインの MX レコードを Office 365 にポイントします。 Exchange Online Protection (EOP) は、メールが Office 365 に直接配信される場合に、クラウドユーザーに最高の保護を提供することができます。 EOP の前にサードパーティの電子メールの検疫システムを使用する必要がある場合は、[ここに記載](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)されているガイダンスに従っていることを確認してください。

- 複数要素認証 (MFA) は、侵害されたアカウントを防止するための最適な方法です。 すべてのユーザーに対して MFA を有効にすることを強くお勧めします。 段階的なアプローチの場合は、すべてのユーザーに対して MFA を有効にする前に、最も機密性の高いユーザー (管理者、役員など) に対して MFA を有効にすることから始めます。 手順については、「[多要素認証をセットアップ](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)する」を参照してください。

- 外部の受信者へのルールの転送は、多くの場合、攻撃者がデータを抽出するために使用します。 「 [Microsoft セキュリティスコア](microsoft-secure-score.md)」の「**メールボックス転送ルールを確認**する」を使用して、外部の受信者に対する転送ルールを見つけて、それを防止します。 詳細については、「[セキュリティで保護されたスコアでクライアントの外部転送ルールを軽減](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)する」を参照してください。
