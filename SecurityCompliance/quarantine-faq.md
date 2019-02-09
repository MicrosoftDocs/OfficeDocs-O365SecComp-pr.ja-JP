---
title: 検疫に関する FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
description: このトピックでは、ホストされた検疫についてのよく寄せられる質問 (FAQ) とその回答を紹介します。
ms.openlocfilehash: 1473e682faab0471f5a6356e8d54a65a9baf291a
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792498"
---
# <a name="quarantine-faq"></a>検疫に関する FAQ

このトピックでは、ホストされた検疫についてのよく寄せられる質問 (FAQ) とその回答を紹介します。回答は Microsoft Exchange Online および Exchange Online Protection のお客様を対象としています。
  
 **検査中のマルウェア検疫されたメッセージの管理 (質問)**
  
セキュリティを使用する必要があります&amp;マルウェアが含まれているために、検疫に送信されたメッセージを表示したり操作するためにコンプライアンス センターです。詳細については、 [Office 365 で電子メール メッセージの検疫](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b)を参照してください。
  
 **Q. スパム検疫済みメッセージを検疫に送るには、どのようにサービスを構成しますか?**
  
A. 既定では、コンテンツ フィルターで処理されたメッセージは受信者の迷惑メール フォルダーに送信されます。しかし管理者は、代わりにコンテンツ フィルター ポリシーを構成することで、スパム検疫済みメッセージを検疫に送ることができます。コンテンツ フィルターで処理されたメッセージに対して実行できるさまざまな操作の詳細については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。
  
 **Q. このサービスには、スパム検疫メッセージの管理者およびエンド ユーザー管理はありますか?**
  
A. 管理者は、検疫された電子メール メッセージすべてに関する詳細を Exchange 管理センター (EAC) で検索し、表示することができます。メッセージを検索したら、特定のユーザーに解放し、さらにオプションとして Microsoft スパム分析チームに誤検知 (迷惑メールではない) として報告することもできます。詳細については、「[管理者として検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-an-administrator.md)」を参照してください。
  
エンド ユーザーとして、自分のスパム検疫メッセージを以下を通じて管理することができます。 
  
- スパム検疫ユーザー インターフェース。詳細については、「[Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)」を参照してください。
        
 **Q. エンド ユーザーにスパム検疫へのアクセスを許可するにはどのようにすればよいですか。**
  
A. のため、エンド ・ ユーザーのスパム検疫にアクセスするエンドユーザーは、有効な Office 365 のユーザー ID とパスワードが必要です。EOP お客様のオンプレミスのメールボックスを保護するには、有効な電子メールのユーザー ディレクトリの同期や、EAC を使用して作成された必要があります。ユーザーの管理の詳細については、EOP の管理者は、 [EOP のメール ユーザーの管理](eop/manage-mail-users-in-eop.md)を参照してください。EOP スタンドアロンお客様では、ディレクトリ同期を使用して、ディレクトリ ベースのエッジ ブロックを有効にすることをお勧め詳細については、[使用してディレクトリ ベースのエッジ ブロックの無効な受信者にメッセージを送信を拒否するのに](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)を参照してください。
  
 **Q. スパム以外のものを検疫に送信できますか?**
  
それが構成されたアクションである場合は、トランスポート ルールに一致するメッセージも管理者の検疫に送信することができます。エンド ユーザーの検疫はスパム限定です。
  
 **Q. メッセージが検疫内に保存される期間はどのくらいですか。**
  
A. 既定では、メッセージをスパム検疫は、検疫で 30 日間保存、トランスポート ルールに一致した検疫済みのメッセージ、検疫で 7 日間保存中に。この期間の後、メッセージは削除され、取得することはできません。トランスポート ルールに一致した検疫済みのメッセージの保存期間が設定可能ではありません。ただし、スパム検疫されたメッセージの保存期間は、 **(日単位) を保持するスパム**の設定、コンテンツ フィルター ポリシーを使用して低下することができます。詳細については、[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)を参照してください。
  
 **Q. 一度に複数の検疫メッセージを解放または報告できますか。**
  
A. EAC またはエンド ユーザー スパム検疫で一度に複数のメッセージを解放または報告する機能は現在利用できません。ただし、管理者はリモート Windows PowerShell スクリプトを作成してこのタスクを実行できます。メッセージを検索する場合は [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) コマンドレットを使用し、それらを解放する場合は [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) コマンドレットを使用します。 
  
 **Q. 隔離されたメッセージを検索する場合にワイルドカードはサポートされますか。特定のドメインの隔離されたメッセージを検索できますか。**
  
A. Exchange 管理センターで検索条件を指定する場合、ワイルドカードはサポートされません。たとえば、送信者を検索する場合には、完全な電子メール アドレスを指定する必要があります。
  
リモート Windows PowerShell を使用すれば、管理者は [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) コマンドレットで指定して、特定のドメイン (contoso.com など) の隔離されたメッセージを検索できます。 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

この結果は、[Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) コマンドレットに渡すことができます。メッセージをすべての受信者に解放するために、ReleaseToAll パラメーターを組み込みます。いったんメッセージが解放されると、再び解放することはできません。 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```


