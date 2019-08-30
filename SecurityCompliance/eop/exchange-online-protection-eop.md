---
title: 'Exchange Online Protection '
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 70ab4af2-fec4-4886-8e12-27d348649204
description: EOP の操作を開始する前に知っておく必要があるいくつかの点を以下に示します。
ms.openlocfilehash: c3e1df3d0016304a22f8411687118c3b4224a710
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676792"
---
# <a name="exchange-online-protection"></a>Exchange Online Protection

Microsoft Exchange Online Protection (EOP) でホストされる電子メール フィルタリング サービスへようこそ。ここでは、EOP で作業を開始する前に注意すべき点をいくつか取り上げ、以下のコンテンツを使用します。
  
- EOP の詳細については、「[Exchange Online Protection サービスの説明](https://go.microsoft.com/fwlink/p/?LinkId=320619)」を参照してください。その他の有益なリソースとして、「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」、「[EOP の一般的な FAQ](eop-general-faq.md)」、および「[EOP の機能](eop-features.md)」、および「[Exchange Online Protection ホームページ](https://go.microsoft.com/fwlink/?LinkId=279912)」があります。

- EOP を初めて使うお客様は、まず「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照してください。 このトピックには、EOP を使い始める際に役立つ手順が記載されています。

- さらに支援が必要な場合や、アイデアを共有したい場合は、「[EOP のフォーラム](https://go.microsoft.com/fwlink/?LinkId=285351)」からご確認ください。

## <a name="eop-help-for-administrators"></a>管理者向けの EOP ヘルプ

EOP 管理者向けのヘルプ コンテンツは、次の最上位カテゴリで構成されます。
  
- [Exchange Online Protection の概要](exchange-online-protection-overview.md): EOP のしくみについて説明し、追加情報へのリンクを提供します。

- [EOP features](eop-features.md): EOP で使用できる機能の一覧を示します。

- [EOP サービス](set-up-your-eop-service.md)をセットアップする: EOP サービスをセットアップする手順、および追加情報へのリンクを提供します。

- [EOP に Google Postini、Barracuda Spam And Virus Firewall、または Cisco IronPort を切り替え](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)ます。別の電子メール保護製品から EOP に切り替えるプロセスについて説明します。

- [EOP の受信者と管理役割グループを管理](manage-recipients-and-admin-role-groups-in-eop.md)する受信者を管理する方法と、ユーザーを管理役割グループに割り当てる方法について説明します。

- [EOP のメールフロー](mail-flow-in-eop.md): コネクタを使用してカスタムメールフローシナリオを構成する方法、サービスに関連付けられたドメインを管理する方法、およびディレクトリベースのエッジブロック (DBEB) 機能を有効にする方法について説明します。

- [EOP を構成するためのベストプラクティス](best-practices-for-configuring-eop.md): サービスをセットアップしてプロビジョニングした後の推奨される構成設定および考慮事項について説明します。

- [EOP のメッセージングポリシーとコンプライアンス](messaging-policy-and-compliance-in-eop.md): Exchange メールフロールール (トランスポートルールとも呼ばれます) を使用して特定の会社の規制やポリシーを適用する方法、および監査レポートを使用してサービスへの構成の変更を追跡する方法について説明します。

- [Office 365 でのスパム対策およびマルウェア対策の保護](../anti-spam-and-anti-malware-protection.md): スパムフィルター処理とマルウェアフィルター処理について説明し、組織のニーズに合わせてカスタマイズする方法を示します。 また、管理者とエンド ユーザーが検疫済みメッセージに対して実行可能なタスクについても説明しています。

- [Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md): 使用可能なレポートとトラブルシューティングツールについて説明します。

- 「Exchange [Online Protection の exchange 管理センター」 ](../exchange-admin-center-in-exchange-online-protection-eop.md): EOP サービスを管理するために、exchange 管理センター (EAC) 管理インターフェイスを介してアクセスおよびナビゲートする方法について説明します。

- [Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell): リモート PowerShell に関する情報を提供します。これにより、EOP サービスをコマンドラインから管理できます。

- 「[EOP のヘルプとサポート](help-and-support-for-eop.md)」 ヘルプおよびテクニカル サポートの入手方法について説明しています。

## <a name="eop-help-for-end-users"></a>エンド ユーザー向けの EOP ヘルプ

EOP エンド ユーザーによるスパム管理を支援するためのヘルプ コンテンツは、次のトピックで構成されます。
  
- [ユーザーとして検疫済みメッセージを検索して解放](../find-and-release-quarantined-messages-as-a-user.md)する: エンドユーザーがスパム検疫ユーザーインターフェイスで自分のスパム検疫メッセージを見つけてリリースする方法を説明し、オプションで、それらを迷惑メールではないとして Microsoft に報告する方法について説明します。

- [スパム、非スパム、フィッシング詐欺メッセージを分析のために microsoft に送信する](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md): エンドユーザーがスパム (迷惑メール) メッセージと非スパム (迷惑メールではない) メッセージを microsoft に送信するさまざまな方法について説明します。 このトピックには、Microsoft Outlook および web 上の Outlook (旧称 Outlook Web App) で使用可能なレポートツールへのリンクが含まれています。

- [マルウェアおよびマルウェア以外の Microsoft による分析の提出](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md): エンドユーザーがフィルターを通過したマルウェアを送信したり、マルウェアとして誤って識別されたファイルを送信したりする方法について説明します。

- エンドユーザーは、Outlook または web 上の Outlook で迷惑メール設定を構成することで、特定のユーザーまたはドメインを安全な送信者リストまたは受信拒否リストに追加できます。 禁止された送信者から送信されたメッセージは拒否されず、スパムとしてマークされ、迷惑メールフォルダーまたは検疫から取得できることに注意してください (管理者がスパムを送信するように構成されている場所によって異なります)。詳細については、「[レポートメッセージアドインを使用する](https://support.office.com/article/addin-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)」を参照してください。

- 「[EOP のヘルプとサポート](help-and-support-for-eop.md)」 ヘルプおよびテクニカル サポートの入手方法について説明しています。
