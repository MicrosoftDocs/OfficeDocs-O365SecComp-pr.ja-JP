---
title: Office 365 で受信拒否リストを作成する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/6/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: 受信拒否リストのオプションには、Outlook のブロックされた送信者、スパム対策送信者/ドメイン禁止リスト、IP 禁止一覧、および Exchange トランスポートルール (Etr) がメールフロールールとも呼ばれます。
ms.openlocfilehash: dae5ffb7d4f2a8f8f3b675719e4f61f5c970dcaf
ms.sourcegitcommit: e834d4168f584f2efb22479aec108497eea267f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "34709125"
---
# <a name="create-block-sender-lists-in-office-365"></a>Office 365 で受信拒否リストを作成する

送信者から不要な電子メールをブロックする必要がある場合があります。 複数の方法から選択できます。 これらのオプションには、Outlook のブロックされた送信者、スパム対策送信者/ドメイン禁止一覧、IP 禁止一覧、および Exchange トランスポートルール (Etr はメールフロールールとも呼ばれます) が含まれます。

> [!NOTE]
> 組織のブロックリストは誤検知 (不在着信) に対処するために使用できますが、これらの候補を分析のために Microsoft に送信する必要があります。 ブロックリストを使用して誤検知を管理すると、管理オーバーヘッドが大幅に向上します。 この目的でブロックリストを使用する場合は、「ready」に記載されているように、[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信](https://docs.microsoft.com/en-us/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)する記事も残しておく必要があります。

受信拒否リストを構成する適切な方法は、影響の範囲によって異なります。 単一のユーザーに影響を与える場合、適切なソリューションは、Outlook のブロックされた送信者を使用することもできますが、複数のユーザーまたはすべてのユーザーが影響を受ける場合は、他のいずれかのオプションの方が適しています。

## <a name="options-from-least-to-broadest-scope"></a>少なくとも最も広範なスコープからのオプション

ブロックリストを作成する際には、影響の範囲 (影響を受けるユーザーの数) に基づいて適切な方法を選択することが重要です。これにより、ブロックメソッドの幅広さに一致するようになります。 次に示すオプションは、範囲と幅の両方でランク付けされます。 リストは狭い範囲から広くなりますが、詳細については、 *「詳細*」を参照してください。

- Outlook のブロックされた送信者
- スパム対策ポリシー: 送信者/ドメインブロックリスト
- Exchange トランスポートルール (Etr はメールフロールールとも呼ばれる)
- スパム対策ポリシー: IP 禁止一覧

## <a name="use-outlook-blocked-senders"></a>Outlook の受信拒否リストを使用する

影響を受けるユーザーの数が少ない場合、Outlook がブロックされた送信者が使用されるのは、送信されたメールにのみ影響するからです。

> [!IMPORTANT]
> 不要なメッセージがよく知られ認識可能なソースからのニュースレターである場合は、電子メールからの登録を中止して、ユーザーが今後メールを受信できないようにすることもできます。

この設定手順は、 [Outlook Web App](https://support.office.com/en-us/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46)と[outlook クライアント](https://support.office.com/en-us/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)で異なります。 受信拒否が原因でメッセージが正常にブロックされると、メッセージがブロックされていることを示す " **fv: BLK" というメッセージがスパム対策に表示され**ます。

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a>スパム対策ポリシーの送信者/ドメインブロックリストを使用する

複数のユーザーが影響を受けている場合、範囲は広くなり、会社全体の送信者/ドメインブロックリストのスパム対策ポリシーを使用する必要があります。 詳細な手順については、「[スパムフィルターポリシーの構成](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies)」のドキュメントを参照してください。 このメソッドによってブロックされるメッセージはすべて、ポリシーに構成されたスパムアクションに従います。

## <a name="use-exchange-transport-rules-etrs-to-block-specific-senders"></a>Exchange トランスポートルール (Etr) を使用して特定の送信者をブロックする

特定のユーザーまたは組織全体で送信されるメッセージをブロックする必要がある場合は、Etr (メールフロールールとも呼ばれます) を使用できます。 Etr では、メッセージの送信者の電子メールアドレスやドメインだけでなく、重要な単語やその他のプロパティもトリガーできるため、柔軟性が向上しています。 この柔軟性により、部分的なブロックを作成することができます。 [ETR (メールフロールールとも呼ばれる) を作成する手順をクリックしてください](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages)。

> [!IMPORTANT]
> 非常にアグレッシブなルールを作成する** のは簡単です。その結果、使用されている条件が可能な限り固有であることが重要です。 また、作成したルールの監査を有効にし、テストを行って、すべてが期待どおりに動作することを確認してください。

## <a name="use-anti-spam-policy-ip-block-lists"></a>スパム対策ポリシーの IP 禁止一覧を使用する

他のオプションのいずれかを使用して送信者をブロックすることが** できない場合は、スパム対策ポリシー IP 禁止一覧を使用できます。 [詳細な手順については、記事「接続フィルターポリシーを構成する」を参照して](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-the-connection-filter-policy)ください。 ここでは、ブロックされた ip の一覧を*最小*にして、IP アドレスの範囲を使用することはお勧めし*ません*。

*特*に、コンシューマーサービスまたは共有インフラストラクチャに属する ip アドレス範囲の追加を避ける必要があります。また、通常のメンテナンスの一環として、許可された ip アドレスの一覧を確認してください。 **が許可されているため、エントリは攻撃のためにルートを開くことができるので、このリストを詳細に管理して、不要になった許可エントリを定期的に削除する必要があります。** また、差出人セーフリストを許可する場合は、「 *[Office 365 で安全な送信者のリストを作成](create-safe-sender-lists-in-office-365.md)* する」のリスクと注意事項を必ず読んで理解してください。