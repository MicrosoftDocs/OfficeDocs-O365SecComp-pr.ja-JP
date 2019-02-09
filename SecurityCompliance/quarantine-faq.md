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
# <a name="quarantine-faq"></a><span data-ttu-id="f60a2-103">検疫に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="f60a2-103">Quarantine FAQ</span></span>

<span data-ttu-id="f60a2-p101">このトピックでは、ホストされた検疫についてのよく寄せられる質問 (FAQ) とその回答を紹介します。回答は Microsoft Exchange Online および Exchange Online Protection のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="f60a2-p101">This topic provides frequently asked questions and answers about the hosted quarantine. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection customers.</span></span>
  
 <span data-ttu-id="f60a2-106">**検査中のマルウェア検疫されたメッセージの管理 (質問)**</span><span class="sxs-lookup"><span data-stu-id="f60a2-106">**Q. How do I manage malware-quarantined messages in quarantine?**</span></span>
  
<span data-ttu-id="f60a2-p102">セキュリティを使用する必要があります&amp;マルウェアが含まれているために、検疫に送信されたメッセージを表示したり操作するためにコンプライアンス センターです。詳細については、 [Office 365 で電子メール メッセージの検疫](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f60a2-p102">You need to use the Security &amp; Compliance Center in order to view and work with messages that were sent to quarantine because they contain malware. For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).</span></span>
  
 <span data-ttu-id="f60a2-109">**Q. スパム検疫済みメッセージを検疫に送るには、どのようにサービスを構成しますか?**</span><span class="sxs-lookup"><span data-stu-id="f60a2-109">**Q. How do I configure the service to send spam-quarantined messages to the quarantine?**</span></span>
  
<span data-ttu-id="f60a2-p103">A. 既定では、コンテンツ フィルターで処理されたメッセージは受信者の迷惑メール フォルダーに送信されます。しかし管理者は、代わりにコンテンツ フィルター ポリシーを構成することで、スパム検疫済みメッセージを検疫に送ることができます。コンテンツ フィルターで処理されたメッセージに対して実行できるさまざまな操作の詳細については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f60a2-p103">A. By default, content-filtered messages are sent to the recipients Junk Email folder. However, admins can configure content filter policies to send spam-quarantined messages to the quarantine instead. For more information about the different actions that can be performed on content-filtered messages, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
 <span data-ttu-id="f60a2-114">**Q. このサービスには、スパム検疫メッセージの管理者およびエンド ユーザー管理はありますか?**</span><span class="sxs-lookup"><span data-stu-id="f60a2-114">**Q. Does the service have administrator and end user management of spam-quarantined messages?**</span></span>
  
<span data-ttu-id="f60a2-p104">A. 管理者は、検疫された電子メール メッセージすべてに関する詳細を Exchange 管理センター (EAC) で検索し、表示することができます。メッセージを検索したら、特定のユーザーに解放し、さらにオプションとして Microsoft スパム分析チームに誤検知 (迷惑メールではない) として報告することもできます。詳細については、「[管理者として検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-an-administrator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f60a2-p104">A. As an administrator, you can search for and view details about all quarantined email messages in the Exchange admin center (EAC). After locating the message, you can release it to specific users and optionally report it as a false positive (not junk) to the Microsoft Spam Analysis Team. For more information, see [Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>
  
<span data-ttu-id="f60a2-119">エンド ユーザーとして、自分のスパム検疫メッセージを以下を通じて管理することができます。</span><span class="sxs-lookup"><span data-stu-id="f60a2-119">As an end user, you can manage your own spam-quarantined messages via:</span></span> 
  
- <span data-ttu-id="f60a2-p105">スパム検疫ユーザー インターフェース。詳細については、「[Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f60a2-p105">The spam quarantine user interface. For more information, see [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx).</span></span>
        
 <span data-ttu-id="f60a2-122">**Q. エンド ユーザーにスパム検疫へのアクセスを許可するにはどのようにすればよいですか。**</span><span class="sxs-lookup"><span data-stu-id="f60a2-122">**Q. How do I grant access to the spam quarantine for my end users?**</span></span>
  
<span data-ttu-id="f60a2-p106">A. のため、エンド ・ ユーザーのスパム検疫にアクセスするエンドユーザーは、有効な Office 365 のユーザー ID とパスワードが必要です。EOP お客様のオンプレミスのメールボックスを保護するには、有効な電子メールのユーザー ディレクトリの同期や、EAC を使用して作成された必要があります。ユーザーの管理の詳細については、EOP の管理者は、 [EOP のメール ユーザーの管理](eop/manage-mail-users-in-eop.md)を参照してください。EOP スタンドアロンお客様では、ディレクトリ同期を使用して、ディレクトリ ベースのエッジ ブロックを有効にすることをお勧め詳細については、[使用してディレクトリ ベースのエッジ ブロックの無効な受信者にメッセージを送信を拒否するのに](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f60a2-p106">A. In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password. EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC. For more information about managing users, EOP admins can refer to [Manage mail users in EOP](eop/manage-mail-users-in-eop.md). For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span>
  
 <span data-ttu-id="f60a2-128">**Q. スパム以外のものを検疫に送信できますか?**</span><span class="sxs-lookup"><span data-stu-id="f60a2-128">**Q. Can anything other than spam be sent to the quarantine?**</span></span>
  
<span data-ttu-id="f60a2-p107">それが構成されたアクションである場合は、トランスポート ルールに一致するメッセージも管理者の検疫に送信することができます。エンド ユーザーの検疫はスパム限定です。</span><span class="sxs-lookup"><span data-stu-id="f60a2-p107">A. Messages that match a transport rule can also be sent to the administrator quarantine, if that's the configured action. The end user quarantine is for spam only.</span></span>
  
 <span data-ttu-id="f60a2-132">**Q. メッセージが検疫内に保存される期間はどのくらいですか。**</span><span class="sxs-lookup"><span data-stu-id="f60a2-132">**Q. For how long are messages kept in the quarantine?**</span></span>
  
<span data-ttu-id="f60a2-p108">A. 既定では、メッセージをスパム検疫は、検疫で 30 日間保存、トランスポート ルールに一致した検疫済みのメッセージ、検疫で 7 日間保存中に。この期間の後、メッセージは削除され、取得することはできません。トランスポート ルールに一致した検疫済みのメッセージの保存期間が設定可能ではありません。ただし、スパム検疫されたメッセージの保存期間は、 **(日単位) を保持するスパム**の設定、コンテンツ フィルター ポリシーを使用して低下することができます。詳細については、[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f60a2-p108">A. By default, spam-quarantined messages are kept in the quarantine for 30 days, while quarantined messages that matched a transport rule are kept in the quarantine for 7 days. After this period of time the messages are deleted and are not retrievable. The retention period for quarantined messages that matched a transport rule is not configurable. However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
 <span data-ttu-id="f60a2-139">**Q. 一度に複数の検疫メッセージを解放または報告できますか。**</span><span class="sxs-lookup"><span data-stu-id="f60a2-139">**Q. Can I release or report more than one quarantined message at a time?**</span></span>
  
<span data-ttu-id="f60a2-p109">A. EAC またはエンド ユーザー スパム検疫で一度に複数のメッセージを解放または報告する機能は現在利用できません。ただし、管理者はリモート Windows PowerShell スクリプトを作成してこのタスクを実行できます。メッセージを検索する場合は [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) コマンドレットを使用し、それらを解放する場合は [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f60a2-p109">A. The ability to release or report multiple messages at once is not currently available in the EAC or the end user spam quarantine. However, admins can create a remote Windows PowerShell script to accomplish this task. Use the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for messages, and the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet to release them.</span></span> 
  
 <span data-ttu-id="f60a2-144">**Q. 隔離されたメッセージを検索する場合にワイルドカードはサポートされますか。特定のドメインの隔離されたメッセージを検索できますか。**</span><span class="sxs-lookup"><span data-stu-id="f60a2-144">**Q. Are wildcards supported when searching for quarantined messages? Can I search for quarantined messages for a specific domain?**</span></span>
  
<span data-ttu-id="f60a2-p110">A. Exchange 管理センターで検索条件を指定する場合、ワイルドカードはサポートされません。たとえば、送信者を検索する場合には、完全な電子メール アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f60a2-p110">A. Wildcards are not supported when specifying search criteria in the Exchange admin center. For example, when searching for a sender, you must specify the full email address.</span></span>
  
<span data-ttu-id="f60a2-148">リモート Windows PowerShell を使用すれば、管理者は [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) コマンドレットで指定して、特定のドメイン (contoso.com など) の隔離されたメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="f60a2-148">Using remote Windows PowerShell, admins can specify the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for quarantined messages for a specific domain (for example, contoso.com):</span></span> 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

<span data-ttu-id="f60a2-p111">この結果は、[Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) コマンドレットに渡すことができます。メッセージをすべての受信者に解放するために、ReleaseToAll パラメーターを組み込みます。いったんメッセージが解放されると、再び解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="f60a2-p111">The results can be passed to the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet. Include the -ReleaseToAll parameter to release the message to all recipients. Once a message is released, it can't be released again.</span></span> 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```


