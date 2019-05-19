---
title: メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Exchange メールフロールールを作成して、ユーザーが電子メールメッセージを分析のために Microsoft に送信したり、独自のセキュリティプロセスで使用したりできないようにすることができます。
ms.openlocfilehash: 0086cf048dcffa912085f23b328ab1d51780f0df
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156139"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="ace94-103">メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する</span><span class="sxs-lookup"><span data-stu-id="ace94-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="ace94-104">分析のために、偽陽性と偽陰性のメッセージを Microsoft に送信する方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="ace94-104">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis.</span></span> <span data-ttu-id="ace94-105">管理者は、メール フロー ルールを使用して、ユーザーが Microsoft にスパム、スパム以外、およびフィッシング詐欺として報告しているものを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="ace94-105">As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams.</span></span> <span data-ttu-id="ace94-106">詳細については、「[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ace94-106">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> <span data-ttu-id="ace94-107">反対に、Exchange メールフロールール (トランスポートルールとも呼ばれます) を作成して、ユーザーが電子メールメッセージを分析のために Microsoft に送信したり、独自のセキュリティプロセスで使用したりするのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="ace94-107">Conversely, you can create an Exchange mail flow rule (also known as a transport rule) to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ace94-108">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="ace94-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="ace94-109">予想所要時間 : 5 分</span><span class="sxs-lookup"><span data-stu-id="ace94-109">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="ace94-110">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ace94-110">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="ace94-111">必要なアクセス許可を確認するには、「[メッセージングポリシーとコンプライアンスのアクセス許可](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)」トピックの「メールフロールール」、および「[クライアントとモバイルデバイスのアクセス許可](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx)」の「web メールボックスポリシー」エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ace94-111">To see what permissions you need, see the "Mail flow rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook on the web mailbox policies" entry in the [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic.</span></span> 
  
<span data-ttu-id="ace94-112">このトピックの手順で使用可能なキーボード ショートカットについては、「**Exchange 管理センターのキーボード ショートカット**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ace94-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="ace94-113">EAC を使用して、ユーザーの手動による迷惑メール レポート、フィッシング レポート、非迷惑メール レポートを表示するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="ace94-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="ace94-114">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="ace94-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="ace94-115">![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ace94-115">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="ace94-116">ルールに名前を付けてから、 **[その他のオプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ace94-116">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="ace94-117">**[このルールを適用する条件]** の下で **[受信者]** を選択してから、 **[アドレスに次のいずれかの単語が含まれる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ace94-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>
    
5. <span data-ttu-id="ace94-118">**[単語または語句の指定]** ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ace94-118">In the **specify words or phrases** box, do the following:</span></span> 
    - <span data-ttu-id="ace94-119">入力`abuse@messaging.microsoft.com`してから![[追加](media/ITPro-EAC-AddIcon.gif)] アイコンをクリック`junk@office365.microsoft.com`し、[ ![追加]](media/ITPro-EAC-AddIcon.gif)アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ace94-119">Type `abuse@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="ace94-120">これらの電子メール アドレスは、偽陰性のメッセージをマイクロソフトに送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ace94-120">These email addresses are used to submit false negative messages to Microsoft.</span></span>
    - <span data-ttu-id="ace94-121">入力`phish@office365.microsoft.com`して、 ![[追加](media/ITPro-EAC-AddIcon.gif)] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ace94-121">Type `phish@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="ace94-122">この電子メール アドレスは、フィッシングとして処理されなかったフィッシング メッセージを Microsoft に送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ace94-122">This email address is used to submit missed phishing messages to Microsoft.</span></span>
    - <span data-ttu-id="ace94-123">入力`false_positive@messaging.microsoft.com`してから![[追加](media/ITPro-EAC-AddIcon.gif)] アイコンをクリック`not_junk@office365.microsoft.com`し、[ ![追加]](media/ITPro-EAC-AddIcon.gif)アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ace94-123">Type `false_positive@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `not_junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="ace94-124">これらの電子メール アドレスは、偽陽性のメッセージをマイクロソフトに送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ace94-124">These email addresses are used to submit false positive messages to Microsoft.</span></span>
    - <span data-ttu-id="ace94-125">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ace94-125">Click **ok**.</span></span>
    
6. <span data-ttu-id="ace94-126">**[次の操作を行います]** で、 **[メッセージを BCC で次へ送信する...]** を選択し、次にメッセージを受信するメールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="ace94-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span> 
    
7. <span data-ttu-id="ace94-127">これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。</span><span class="sxs-lookup"><span data-stu-id="ace94-127">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="ace94-128">ルールを施行する前に一定期間ルールをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ace94-128">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="ace94-129">「[メールフロールールの手順」を](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)参照してください。</span><span class="sxs-lookup"><span data-stu-id="ace94-129">See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span> 
    
8. <span data-ttu-id="ace94-p107">**[保存]** ボタンをクリックしてルールを保存します。保存されたルールはルールの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ace94-p107">Click the **save** button to save the rule. It appears in your list of rules.</span></span> 
    
<span data-ttu-id="ace94-132">ルールを作成して試行すると、指定したメール アドレス宛に組織内から送信されるすべてのメッセージが指定されたメールボックスにコピーされるようになります。</span><span class="sxs-lookup"><span data-stu-id="ace94-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
  

