---
title: メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/23/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: ユーザー分析のためのマイクロソフトに電子メール メッセージを送信するを防止し、独自のセキュリティ プロセスで使用する Exchange のトランスポート ルールを作成することができます。
ms.openlocfilehash: f2376668e2a1a16eba9913178a100fc31763b227
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026774"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="683ee-103">メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する</span><span class="sxs-lookup"><span data-stu-id="683ee-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="683ee-p101">正と負の値の false メッセージを Microsoft に送信するには分析のための複数の方法があります。管理者は、どのようなユーザーは、マイクロソフトに報告する迷惑メール、スパム以外の場合、フィッシング詐欺とを参照してくださいにメール フロー ルールを使用できます。詳細については、[迷惑メールの送信、スパム以外の場合、および分析のためのマイクロソフトのフィッシング詐欺メッセージ](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)を参照してください。逆に、ユーザー分析のためのマイクロソフトに電子メール メッセージを送信するを防止し、独自のセキュリティ プロセスで使用する Exchange トランスポート ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="683ee-p101">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis. As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams. For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Conversely, you can create an Exchange Transport rule to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="683ee-108">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="683ee-108">What do you need to know before you begin?</span></span>
<span data-ttu-id="683ee-109"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="683ee-109"></span></span>

<span data-ttu-id="683ee-110">予想所要時間 : 5 分</span><span class="sxs-lookup"><span data-stu-id="683ee-110">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="683ee-p102">[Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) トピックの この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「トランスポート ルール」のエントリと、 [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) トピックの「Outlook Web App メールボックス ポリシー」のエントリです。</span><span class="sxs-lookup"><span data-stu-id="683ee-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook Web App mailbox policies" entry in the [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic.</span></span> 
  
<span data-ttu-id="683ee-113">このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="683ee-113">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="683ee-114">EAC を使用して、ユーザーの手動による迷惑メール レポート、フィッシング レポート、非迷惑メール レポートを表示するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="683ee-114">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>
<span data-ttu-id="683ee-115"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="683ee-115"></span></span>

1. <span data-ttu-id="683ee-116">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="683ee-116">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="683ee-117">![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックしてから、 **[新しいルールを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="683ee-117">Click ![Add Icon](media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="683ee-118">ルールに名前を付けてから、 **[その他のオプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="683ee-118">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="683ee-119">**[このルールを適用する条件]** の下で **[受信者]** を選択してから、 **[アドレスに次のいずれかの単語が含まれる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="683ee-119">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>
    
5. <span data-ttu-id="683ee-120">**[単語または語句の指定]** ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="683ee-120">In the **specify words or phrases** box, do the following:</span></span> 
    - <span data-ttu-id="683ee-p103">**abuse@messaging.microsoft.com** と入力してから ![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックし、次に **junk@office365.microsoft.com** と入力してから ![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックします。これらの電子メール アドレスは、偽陰性のメッセージをマイクロソフトに送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="683ee-p103">Type **abuse@messaging.microsoft.com** and then click ![Add Icon](media/ITPro-EAC-AddIcon.png), and then type **junk@office365.microsoft.com** and then click ![Add Icon](media/ITPro-EAC-AddIcon.png). These email addresses are used to submit false negative messages to Microsoft.</span></span>
    - <span data-ttu-id="683ee-p104">**phish@office365.microsoft.com** と入力し、次に ![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックします。この電子メール アドレスは、フィッシングとして処理されなかったフィッシング メッセージを Microsoft に送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="683ee-p104">Type **phish@office365.microsoft.com** and then click ![Add Icon](media/ITPro-EAC-AddIcon.png). This email address is used to submit missed phishing messages to Microsoft.</span></span>
    - <span data-ttu-id="683ee-p105">**false_positive@messaging.microsoft.com** と入力してから ![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックし、次に **not_junk@office365.microsoft.com** と入力してから ![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックします。これらの電子メール アドレスは、偽陽性のメッセージをマイクロソフトに送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="683ee-p105">Type **false_positive@messaging.microsoft.com** and then click ![Add Icon](media/ITPro-EAC-AddIcon.png), and then type **not_junk@office365.microsoft.com** and then click ![Add Icon](media/ITPro-EAC-AddIcon.png). These email addresses are used to submit false positive messages to Microsoft.</span></span>
    - <span data-ttu-id="683ee-127">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="683ee-127">Click **ok**.</span></span>
    
6. <span data-ttu-id="683ee-128">**[次の操作を行います]** で、 **[メッセージを BCC で次へ送信する...]** を選択し、次にメッセージを受信するメールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="683ee-128">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span> 
    
7. <span data-ttu-id="683ee-p106">これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。ルールを施行する前に一定期間ルールをテストすることをお勧めします。[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) にこれらの選択肢に関する詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="683ee-p106">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period before you enforce it. [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) contains more information about these selections.</span></span> 
    
8. <span data-ttu-id="683ee-p107">**[保存]** ボタンをクリックしてルールを保存します。保存されたルールはルールの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="683ee-p107">Click the **save** button to save the rule. It appears in your list of rules.</span></span> 
    
<span data-ttu-id="683ee-134">ルールを作成して試行すると、指定したメール アドレス宛に組織内から送信されるすべてのメッセージが指定されたメールボックスにコピーされるようになります。</span><span class="sxs-lookup"><span data-stu-id="683ee-134">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
  

