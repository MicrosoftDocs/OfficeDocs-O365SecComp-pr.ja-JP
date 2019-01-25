---
title: Office 365 で迷惑メールを減らす方法
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
description: Office 365 でスパム メールや迷惑メールを減らすための最も一般的な方法について説明します。
ms.openlocfilehash: 59778f992ebc232ae31ebc9aaae4ca5333080698
ms.sourcegitcommit: 7023fd3c4d6088f82a5cd2fda241897a3a1c7f5c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2019
ms.locfileid: "29453693"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a>Office 365 で迷惑メールを減らす方法

 **Office 365 で大量のスパムを受信している方は、次のようにしてください。**
  
Office 365 での迷惑メールに関する多くの問題は、[メールのメッセージ ヘッダーを調べ](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)、そうなった理由を判断することによって解決できます。文字列 SFV:NSPM を含む X-Forefront-Antispam-Report というメッセージ ヘッダーがある場合、Exchange Online Protection (EOP) はメッセージをスキャンしてそれを迷惑メールと見なさなかったことを意味します。この場合は、[メッセージ報告アドインを使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)してフィルターが改善されるようにすることを強くお勧めします。この値がヘッダーにない場合は、メールが迷惑メール スキャンをパススルーしなかったか、構成の問題があったためにメッセージが無視されたことが考えられます。この場合は、以下の情報を参照してください。 
  
[迷惑メール対策メッセージ ヘッダー](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)に関する詳しい説明があります。
  
## <a name="solutions-to-common-causes-of-getting-too-much-spam"></a>大量のスパムの一般的な原因に対する解決策

大量のスパムを受信しないようにするには、Exchange Online Protection (EOP) で管理者がいくつかのタスクを実行する必要があります。Office 365 テナントの管理者でなく、大量の迷惑メールを受け取っているユーザーは、これらのタスクを管理者と一緒に行うこともできます。そうしない場合は、ユーザーのセクションにスキップしてください。
  
### <a name="for-admins"></a>管理者向け

- **DNS レコードを Office 365 用にする**: EOP で保護を提供するには、すべてのドメインのメール エクスチェンジャー (MX) の DNS レコードを Office 365 専用にする必要があります。[MX が Office 365 用になっていない](https://blogs.msdn.microsoft.com/tzink/2017/12/28/if-you-use-office-365-but-your-mx-record-doesnt-point-to-office-you-may-want-to-close-down-your-security-settings/)場合、ユーザーは EOP で迷惑メール フィルタリングを行うことはできません。「[DNS レコードの管理時に Office 365 用の DNS レコードを作成する](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)」を参照してください。
    
- **すべてのメールボックスで迷惑メール ルールを有効にする**: 既定では、迷惑メールのフィルタリング アクションは**メッセージを迷惑メール フォルダーに移動する**ように設定されています。この設定が優先される現在のスパム ポリシー アクションである場合、各メールボックスで[迷惑メール ルールが有効になっている必要があります](https://blogs.msdn.microsoft.com/tzink/2017/12/14/making-sure-your-junk-email-filtering-is-enabled-in-office-365/)。設定を確認するには、1 つ以上のメールボックスに対して Get-MailboxJunkEmailConfiguration コマンドレットを実行します。たとえば、コマンド「Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}」を実行すると、すべてのメールボックスに対して設定をチェックすることができます。
    
    出力を表示するときは、Enable プロパティを True に設定する必要があります。False に設定されている場合は、Set-MailboxJunkEmailConfiguration を実行して True に変更できます。
    
- **メール フロー ルールとセーフ リストを確認する**: メッセージ ヘッダーに、スパムとしてマークされているはずのメッセージがないか確認します。X-Forefront-Antispam-Report ヘッダーで SCL プロパティを探します。SCL 値が -1 の場合、これはメッセージがセーフ リストに載り、EOP のスパム対策フィルターをバイパスしたことを示します。メール フロー ルール、許可リスト、受信者の許可送信者リストを調査します。[Office 365 for Business の管理者としてメール配信の問題を探索および修正する](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6)ことは、メッセージが -1 の SCL を受信した理由についての詳細情報を提供するのにも役立ちます。 
    
- **オンプレミス Exchange Server でメール フロー ルールを作成する**: Exchange Online Protection を使用していても、メールボックスがオンプレミス Exchange Server にある場合は、Exchange Server でいくつかのメール フロー ルールを作成する必要があります。「[EOP 専用の命令](https://technet.microsoft.com/library/ms.exch.eac.EditAntispamPolicy_SpamAction%28EXCHG.150%29.aspx?v=15.20.548.14&amp;l=1&amp;s=BPOS_S_E15_0)」を参照してください。
    
- **バルク メールをスパムとしてマークする**: バルク メールとは、ユーザーはサインアップした可能性があるとしても望ましくないと思われるメールのことです。メッセージ ヘッダーで、X-Microsoft-Antispam ヘッダーの中の BCL (Bulk Confidence Level) プロパティを見つけます。迷惑メール フィルターに設定されたしきい値よりも BCL 値の方が小さければ、これらのタイプのバルク メッセージを迷惑メールとしてマークするようにしきい値を調整することが必要になる場合があります。[バルク メールの処理](https://blogs.msdn.microsoft.com/tzink/2014/08/25/different-levels-of-bulk-mail-filtering-in-office-365/)に関する許容度とユーザー設定はユーザーによって異なります。ユーザー設定ごとに異なるポリシーやルールを作成できます。 
    
- **すぐに送信者をブロックする**: すぐに送信者をブロックする必要がある場合は、メール アドレス、ドメイン、または IP アドレスでブロックすることができます。「[検出漏れの問題を防止するために Office 365 のスパム フィルターを使用して迷惑メールをブロックする](block-email-spam-to-prevent-false-negatives.md)」を参照してください。エンド ユーザー許可リスト内のエントリは、管理者によるブロック設定をオーバーライドできます。
    
- **ユーザーのメッセージ報告アドインをオンにする**: [ユーザーのメッセージ報告アドインを有効にする](enable-the-report-message-add-in.md)ことを強くお勧めします。管理者は、ユーザーが送信しているフィードバックを調べ、何らかのパターンを使用して、問題の原因となっている可能性がある設定を調整することもできます。
    
### <a name="for-users"></a>ユーザー向け

- **迷惑メール ルールを有効にして許可リストを確認する**: 迷惑メール対策ルールが有効で、送信者または送信者のドメインが個人の許可リストでバイパスするように設定されていないことを確認します。これらの設定にアクセスする最適な方法は、[禁止または許可 (迷惑メール設定)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) の使用です。その際に、送信者のメール アドレスまたはドメインをブロックするように選択することもできます。
    
- **Microsoft に迷惑メールを報告する**: [メッセージ報告アドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) を使用して、Microsoft に迷惑メール メッセージを報告します。また、junk@office365.microsoft.com にメッセージを送信し、1 つ以上のメッセージをレポートに添付することができます。
    
    **重要**: メッセージを添付ファイルとして転送しなければ、[ヘッダーがないために Office 365 の迷惑メール フィルターの改善ができなくなります](https://blogs.msdn.microsoft.com/tzink/2017/11/30/when-creating-support-tickets-about-spam-be-sure-to-include-message-headers/)。 
    
- **バルク メールの受信を停止する**: サインアップしたメッセージ (ニュースレター、製品アナウンスなど) に、信頼できる送信元からの登録解除リンクが含まれている場合は、簡単に登録を解除することができます。Office 365 では通常、こうしたメッセージをスパムとして扱いません。また、送信者をブロックしたり、すべてのバルク メールをスパムとして扱うように管理者に設定変更を依頼したりすることもできます。 
    

