---
title: メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: Exchange トランスポートルールを作成して、ユーザーが電子メールメッセージを分析のために Microsoft に送信したり、独自のセキュリティプロセスで使用したりできないようにすることができます。
ms.openlocfilehash: 7ee8fb2bca1071ccd4080379485c1670a5e66a73
ms.sourcegitcommit: 06d6e63225f912d0f3c6bb836c61eb11c1dbe97a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "30206410"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="05438-103">メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する</span><span class="sxs-lookup"><span data-stu-id="05438-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="05438-p101">誤検知および false 否定的メッセージを分析のために Microsoft に送信する方法は複数あります。管理者は、メールフロールールを使用して、ユーザーがスパム、非スパム、フィッシング詐欺として Microsoft に報告する内容を確認できます。詳細については、「[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。反対に、Exchange トランスポートルールを作成して、ユーザーが電子メールメッセージを分析のために Microsoft に送信したり、独自のセキュリティプロセスで使用したりするのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="05438-p101">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis. As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams. For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Conversely, you can create an Exchange Transport rule to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="05438-108">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="05438-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="05438-109">予想所要時間 : 5 分</span><span class="sxs-lookup"><span data-stu-id="05438-109">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="05438-p102">この手順を実行する前に、アクセス許可を割り当てる必要があります。必要なアクセス許可を確認するには、「[メッセージングポリシーとコンプライアンスのアクセス許可](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)」トピックの「トランスポートルール」、および「[クライアントとモバイルデバイスのアクセス許可](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx)」の「web メールボックスポリシー」エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="05438-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook on the web mailbox policies" entry in the [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic.</span></span> 
  
<span data-ttu-id="05438-112">このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05438-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="05438-113">EAC を使用して、ユーザーの手動による迷惑メール レポート、フィッシング レポート、非迷惑メール レポートを表示するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="05438-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="05438-114">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="05438-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="05438-115">![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="05438-115">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="05438-116">ルールに名前を付けてから、 **[その他のオプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05438-116">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="05438-117">**[このルールを適用する条件]** の下で **[受信者]** を選択してから、 **[アドレスに次のいずれかの単語が含まれる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="05438-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>
    
5. <span data-ttu-id="05438-118">**[単語または語句の指定]** ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="05438-118">In the **specify words or phrases** box, do the following:</span></span> 
    - <span data-ttu-id="05438-p103">入力`abuse@messaging.microsoft.com`してから![[追加](media/ITPro-EAC-AddIcon.gif)] アイコンをクリック`junk@office365.microsoft.com`し、[ ![追加]](media/ITPro-EAC-AddIcon.gif)アイコンをクリックします。これらの電子メールアドレスは、偽の否定的なメッセージを Microsoft に送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="05438-p103">Type `abuse@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). These email addresses are used to submit false negative messages to Microsoft.</span></span>
    - <span data-ttu-id="05438-p104">入力`phish@office365.microsoft.com`して、 ![[追加](media/ITPro-EAC-AddIcon.gif)] アイコンをクリックします。この電子メールアドレスは、不在時のフィッシングメッセージを Microsoft に送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="05438-p104">Type `phish@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). This email address is used to submit missed phishing messages to Microsoft.</span></span>
    - <span data-ttu-id="05438-p105">入力`false_positive@messaging.microsoft.com`してから![[追加](media/ITPro-EAC-AddIcon.gif)] アイコンをクリック`not_junk@office365.microsoft.com`し、[ ![追加]](media/ITPro-EAC-AddIcon.gif)アイコンをクリックします。これらの電子メールアドレスは、偽陽性のメッセージをマイクロソフトに送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="05438-p105">Type `false_positive@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `not_junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). These email addresses are used to submit false positive messages to Microsoft.</span></span>
    - <span data-ttu-id="05438-125">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05438-125">Click **ok**.</span></span>
    
6. <span data-ttu-id="05438-126">**[次の操作を行います]** で、 **[メッセージを BCC で次へ送信する...]** を選択し、次にメッセージを受信するメールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="05438-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span> 
    
7. <span data-ttu-id="05438-p106">必要に応じて、ルールを監査したり、ルールをテストしたり、特定の期間中にルールをアクティブ化したり、その他の選択を行ったりすることができます。ルールを適用する前に、期間に対してルールをテストすることをお勧めします。「[メールフロールールの手順」を](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)参照してください。</span><span class="sxs-lookup"><span data-stu-id="05438-p106">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period before you enforce it. See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span> 
    
8. <span data-ttu-id="05438-p107">**[保存]** ボタンをクリックしてルールを保存します。保存されたルールはルールの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="05438-p107">Click the **save** button to save the rule. It appears in your list of rules.</span></span> 
    
<span data-ttu-id="05438-132">ルールを作成して試行すると、指定したメール アドレス宛に組織内から送信されるすべてのメッセージが指定されたメールボックスにコピーされるようになります。</span><span class="sxs-lookup"><span data-stu-id="05438-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
  

