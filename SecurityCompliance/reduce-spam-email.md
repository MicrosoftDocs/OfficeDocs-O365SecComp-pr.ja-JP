---
title: Office 365 で迷惑メールを減らす方法
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/07/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: Office 365 でスパム メールや迷惑メールを減らすための最も一般的な方法について説明します。
ms.openlocfilehash: d99b5e1452c60be713f0f4cfbab965d30eeeb8ef
ms.sourcegitcommit: bc25ea19c0b6d318751eadc4f27902b0054d5e2b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "36054709"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a>Office 365 で迷惑メールを減らす方法

 **Office 365 で大量のスパムを受信している方は、次のようにしてください。**
  
フィルターを改善できるように「[迷惑メール報告アドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)」から偽陰性メッセージを報告するよう強くお勧めします。 さらに、[報告エクスプローラー](admin-submission.md)を使用して提出することもできます。

> [!TIP]
> 迷惑メールと思われるメッセージが迷惑メール フォルダーにある場合、問題にはなりません。メールボックス内に一切表示しないようにするには、スパム対策ポリシーを変更して、メッセージを検疫する必要があります。メッセージ検疫の詳細については「[Office 365 でメール メッセージを検疫する](quarantine-email-messages.md)」を参照してください。

## <a name="fixing-allowed-spam"></a>許可されている迷惑メールを解決する

多くの場合、構成が正しくないために迷惑メールがお客様の受信トレイに入ってしまっているようです。最も一般的なのは、フィルターをバイパスするようにメール フロー ルール (別名: トランスポート ルール) でドメインを構成すること、または許可/安全送信者リストにドメインを一覧表示することです。この方法では、本来検出されるはずのこれらのメッセージが迷惑メール フィルターをスキップしてしまうため、正しくありません。  

## <a name="solutions-to-other-common-causes-of-getting-too-much-spam"></a>大量の迷惑メールを受け取る他の一般的な原因の解決方法

大量のスパムを受信しないようにするには、Exchange Online Protection (EOP) で管理者がいくつかのタスクを実行する必要があります。Office 365 テナントの管理者でなく、大量の迷惑メールを受け取っているユーザーは、これらのタスクを管理者と一緒に行うこともできます。そうしない場合は、ユーザーのセクションにスキップしてください。
  
### <a name="for-admins"></a>管理者向け

- **DNS レコードを Office 365 用にする**: EOP で最大の保護を提供するには、すべてのドメインのメール エクスチェンジャー (MX) の DNS レコードを Office 365 専用にする必要があります。「[任意の DNS ホスティング プロバイダーで Office 365 用の DNS レコードを作成する](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)」を参照してください。
    
- 
  **すべてのメールボックスで迷惑メール ルールを有効にする**: 既定では、迷惑メールのフィルタリング アクションは**メッセージを迷惑メール フォルダーに移動する**ように設定されています。この設定が優先される現在のスパム ポリシー アクションである場合、各メールボックスで[迷惑メール ルールが有効になっている必要があります](https://support.office.com/ja-JP/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。設定を確認するには、1 つ以上のメールボックスに対して Get-MailboxJunkEmailConfiguration コマンドレットを実行します。たとえば、コマンド「Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}」を実行すると、すべてのメールボックスに対して設定をチェックすることができます。
    
    出力を表示するときは、Enable プロパティを True に設定する必要があります。False に設定されている場合は、Set-MailboxJunkEmailConfiguration を実行して次のように True に変更できます: Set-MailboxJunkEmailConfiguration -Identity $values.UserPrincipalName -Enabled $true。
    
- **オンプレミス Exchange Server でメール フロー ルールを作成する**: Exchange Online Protection を使用していても、メールボックスがオンプレミス Exchange Server にある場合は、Exchange Server でいくつかのメール フロー ルールを作成する必要があります。「[EOP 専用の命令](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150))」を参照してください。
    
- 
  **バルク メールをスパムとしてマークする**: バルク メールとは、ユーザーはサインアップした可能性があるとしても望ましくないと思われるメールのことです。メッセージ ヘッダーで、X-Microsoft-Antispam ヘッダーの中の BCL (Bulk Confidence Level) プロパティを見つけます。迷惑メール フィルターに設定されたしきい値よりも BCL 値の方が小さければ、これらのタイプのバルク メッセージを迷惑メールとしてマークするようにしきい値を調整することが必要になる場合があります。[バルク メールの処理](https://docs.microsoft.com/ja-JP/office365/SecurityCompliance/bulk-complaint-level-values)に関する許容度とユーザー設定はユーザーによって異なります。ユーザー設定ごとに異なるポリシーやルールを作成できます。 
    
- **すぐに送信者をブロックする**: すぐに送信者をブロックする必要がある場合は、メール アドレス、ドメイ ン、または IP アドレスでブロックすることができます。「[Office 365 でブロックする差出人のリストを作成する](create-block-sender-lists-in-office-365.md)」を参照してください。エンド ユーザー許可リスト内のエントリで、管理者によるブロック設定をオーバーライドできます。
    
- **ユーザーの迷惑メール報告アドインを有効にする**: [ユーザーの迷惑メール報告アドインを有効にする](enable-the-report-message-add-in.md)ことを強くお勧めします。

- **[報告エクスプローラー](admin-submission.md)を使用する**: 管理者は、Office 365 の Microsoft でスキャンするファイルまたはネットワークのメッセージ ID、URL、ファイルを使用してメールを送信できるようになりました。 管理者は、ユーザーが送信したフィードバックを表示し、問題の原因である可能性のある設定を任意のパターンで調整することができる場合もあります。

- **[DKIM](use-dkim-to-validate-outbound-email.md)を有効にする**: これにより、すべての送信メッセージに署名して、ドメインとテナントのセキュリティを強化します。
 > [!TIP]
> DKIM を有効化したら、[DMARC](use-dkim-to-validate-outbound-email.md) も有効にする必要があります。このレコードにより、DKIM と SPF が正しく動作していることを確認するためです。また、秘密キーと公開対称キーは O365 によって管理されるため、ほとんどのスプーフィング電子メールには署名がありません。
    
### <a name="for-users"></a>ユーザー向け

- **迷惑メール ルールを有効にして許可リストを確認する**: 迷惑メール対策ルールが有効で、送信者または送信者のドメインが個人の許可リストでバイパスするように設定されていないことを確認します。これらの設定にアクセスする最適な方法は、[禁止または許可 (迷惑メール設定)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) の使用です。その際に、送信者のメール アドレスまたはドメインをブロックするように選択することもできます。
    
- **Microsoft に迷惑メールを報告する**: 「[迷惑メール報告アドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)」を使用して、Microsoft にスパム メッセージを報告します。
       
- **バルク メールの受信を停止する**: サインアップしたメッセージ (ニュースレター、製品アナウンスなど) に、信頼できる送信元からの登録解除リンクが含まれている場合は、簡単に登録を解除することができます。Office 365 では通常、こうしたメッセージをスパムとして扱いません。また、送信者をブロックしたり、すべてのバルク メールをスパムとして扱うように管理者に設定変更を依頼したりすることもできます。
