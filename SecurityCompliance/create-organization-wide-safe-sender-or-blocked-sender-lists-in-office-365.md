---
title: Office 365 で組織全体の信頼できる差出人またはブロックする差出人の一覧を作成する
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/8/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: 調整でき、自分のメッセージを信頼するために、特定の送信者からのメールを受信したことを確認する場合、Exchange 管理センターでの迷惑メール フィルター ポリシーのリストを許可します。
ms.openlocfilehash: 1086a4a710432eb412ae9f08f204beda52aa5390
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027544"
---
# <a name="create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365"></a><span data-ttu-id="e5205-103">Office 365 で組織全体の信頼できる差出人またはブロックする差出人の一覧を作成する</span><span class="sxs-lookup"><span data-stu-id="e5205-103">Create organization-wide safe sender or blocked sender lists in Office 365</span></span>
  
<span data-ttu-id="e5205-p101">特定の送信者とそのメッセージを信頼しているため、その送信者からのメールを確実に受信したい場合は、Exchange 管理センター (EAC) の **[保護]** \> **[スパム フィルター]** で開くスパム フィルター ポリシーで許可リストを調整できます。この内容の詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。別の選択肢としては、スパム フィルターのドメインまたはユーザーによる許可リストのように機能する Exchange トランスポート ルールを作成することです。同様の方法でも、特定のドメインまたはユーザーからの送信メッセージをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5205-p101">If you want to be sure that you receive mail from a particular sender, because you trust them and their messages, you can adjust your allow list in a spam filter policy in the Exchange admin center (EAC) at **Protection** \> **Spam filter**. Learn more about this at [Configure your spam filter policies](configure-your-spam-filter-policies.md). Another option would be create an Exchange transport rule that works like the domain or user-based allow list in the spam filter. You can block messages sent from a particular domain or user in a similar manner too.</span></span>
  
<span data-ttu-id="e5205-p102">メッセージ ヘッダーや添付ファイルの名前のチェックなどの複雑な条件をフィルタリングする必要がある場合や、メッセージに免責条項を追加する、またはルールの有効期間を適用するなどの複雑な処理を追加する場合、この状況ではトランスポート ルールが便利です。ただし、特定の送信者またはドメインからの電子メールを確実にスパム フィルターからバイパスさせる方法としては、スパム フィルター ポリシーにその電子メールを追加する方法が優先されます。 **[保護]** \> **[スパム フィルター]** に移動して、EAC でこの作業をやってみましょう。詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5205-p102">A transport rule would be useful in this situation if you need to filter for complex criteria such as checking message headers or the names of attachments or if you want to add complex actions such as adding a disclaimer to the message or applying a time period where the rule is active. However, the preferred method to make sure emails from a specific sender or domain bypass your spam filter is to add them to your spam filter policy. Get started with this in the EAC by going to **Protection** \> **Spam filter**. Learn more at [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="e5205-p103">ドメインはスプーフィング (なりすまし) が可能なため、トランスポート ルールのドメイン ベースのリストは、IP アドレス ベースのリストほど安全ではありません。また、送信 IP アドレスが禁止一覧に含まれる場合、ドメインまたはユーザーのフィルター処理がバイパスされても、そのアドレスはブロックされます。グローバル IP 禁止一覧による指定のほうが、ドメインまたはユーザーによるトランスポート ルールより優先されるからです。通常は、IP アドレスベースのリストを使用することをお勧めします。IP アドレスベースのリストを作成するには、接続フィルター内で IP 許可一覧または IP 禁止一覧を使用します。これらの IP アドレスから送信されたメッセージはコンテンツ フィルターによってチェックされません。IP アドレスを IP 許可一覧または IP 禁止一覧に追加することによる接続フィルター ポリシーの構成方法の手順については、「[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5205-p103">A domain-based list in a transport rule isn't as secure as an IP address-based list, because domains can be spoofed. Also, if the sending IP address is on a Block list, it will still be blocked even if filtering for the domain or user is being bypassed. This is because a transport rule on a domain or user does not override the global IP Block list. We recommend using an IP address-based list in most cases. To create an IP address-based list, you can use the IP Allow list or IP Block list in the connection filter. Any messages sent from these IP addresses aren't checked by the content filter. For instructions on how to configure the connection filter policy by adding IP addresses to the IP Allow list or IP Block list, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> 
  
<span data-ttu-id="e5205-119">トランスポート ルールに関連する追加の管理タスクについては、「[Transport Rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5205-119">For additional management tasks related to transport rules, see [Transport Rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).</span></span>
  
## <a name="use-the-eac-to-customize-a-block-or-allow-list-to-prevent-or-receive-email-from-a-domain-or-user"></a><span data-ttu-id="e5205-120">EAC で禁止または許可リストをカスタマイズして、ドメインまたはユーザーからの電子メールを拒否または受信する</span><span class="sxs-lookup"><span data-stu-id="e5205-120">Use the EAC to customize a block or allow list to prevent or receive email from a domain or user</span></span>
<span data-ttu-id="e5205-121"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="e5205-121"></span></span>

1. <span data-ttu-id="e5205-122">EAC の **[保護]** \> **[スパム フィルター]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e5205-122">In the EAC, go to **Protection** \> **Spam filter**.</span></span> 
    
2. <span data-ttu-id="e5205-123">**[全般]** ページで次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e5205-123">On the **general** page, do one of the following:</span></span> 
    
  - <span data-ttu-id="e5205-124">編集を開始するため、既定のポリシーまたは既存のポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5205-124">Double-click the default policy or an existing policy in order to start editing it.</span></span>
    
  - <span data-ttu-id="e5205-125">**[新規作成]** をクリックして、組織内のユーザー、グループ、およびドメインに適用可能な新しいカスタム スパム フィルター ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5205-125">Click **New** in order to create a new custom spam-filter policy that can be applied to users, groups, and domains in your organization.</span></span> 
    
3. <span data-ttu-id="e5205-p104">[ **受信許可一覧**] ページで、送信者やドメインなどのエントリを指定すると、それらのエントリからのメールが常に受信トレイに配信されます。これらのエントリからのメールは、迷惑メール フィルターによって処理されません。次の操作を実行してください。</span><span class="sxs-lookup"><span data-stu-id="e5205-p104">On the **Allow Lists** page, you can specify entries, such as senders or domains, that will always be delivered to the inbox. Email from these entries is not processed by the spam filter. Do the following:</span></span> 
    
  - <span data-ttu-id="e5205-p105">信頼できる送信者を [受信許可送信者一覧] に追加します。 **[追加]** をクリックし、選択ダイアログ ボックスで、許可する送信者のアドレスを追加します。複数のエントリを区切るには、セミコロンまたは改行を使用します。[OK] をクリックして **[受信許可一覧]** ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="e5205-p105">Add trusted senders to the Sender allow list. Click **Add**, and then in the selection dialog box, add the sender addresses you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page.</span></span> 
    
  - <span data-ttu-id="e5205-p106">信頼できるドメインを [受信許可ドメイン一覧] に追加します。 **[追加]** をクリックし、選択ダイアログ ボックスで、許可するドメインを追加します。複数のエントリを区切るには、セミコロンまたは改行を使用します。[OK] をクリックして **[受信許可一覧]** ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="e5205-p106">Add trusted domains to the Domain allow list. Click **Add**, and then in the selection dialog box, add the domains you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="e5205-137">トップレベル ドメインを許可した場合、不要な電子メールが受信トレイに配信される可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="e5205-137">If you allow top-level domains, it's likely that email you don't want will be delivered to an inbox.</span></span> 
  
4. <span data-ttu-id="e5205-p107">[ **受信拒否一覧**] ページで、送信者やドメインなどのエントリを指定すると、それらのエントリからのメールが常にスパムとしてマークされます。サービスにより、これらのエントリに一致する電子メールに対して、構成された精度の高いスパム処理が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e5205-p107">On the **Block Lists** page, you can specify entries, such as senders or domains, that will always be marked as spam. The service will apply the configured high confidence spam action on email that matches these entries.</span></span> 
    
  - <span data-ttu-id="e5205-p108">不要な送信者を [受信拒否送信者一覧] に追加します。[ **追加**] ![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックし、選択ダイアログ ボックスで、禁止する送信者のアドレスを追加します。複数のエントリを区切るには、セミコロンまたは改行を使用します。[ **OK**] をクリックして [ **受信拒否一覧**] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="e5205-p108">Add unwanted senders to the Sender block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the sender addresses you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page.</span></span> 
    
  - <span data-ttu-id="e5205-p109">不要なドメインを [受信拒否ドメイン一覧] に追加します。[ **追加**] ![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックし、選択ダイアログ ボックスで、禁止するドメインを追加します。複数のエントリを区切るには、セミコロンまたは改行を使用します。[ **OK**] をクリックして [ **受信拒否一覧**] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="e5205-p109">Add unwanted domains to the Domain block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the domains you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="e5205-148">トップレベル ドメインを禁止した場合、必要なメールが迷惑メールとしてマークされる可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="e5205-148">If you block top-level domains, it's likely that email you want will be marked as spam.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin-creating-a-transport-rule"></a><span data-ttu-id="e5205-149">トランスポート ルールの作成を始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="e5205-149">What do you need to know before you begin creating a transport rule?</span></span>
<span data-ttu-id="e5205-150"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="e5205-150"></span></span>

- <span data-ttu-id="e5205-151">予想所要時間 : 15 分</span><span class="sxs-lookup"><span data-stu-id="e5205-151">Estimated time to complete: 15 minutes</span></span>
    
- <span data-ttu-id="e5205-p110">スパム フィルタリングをバイパスするか、送信者またはドメインによって電子メールをスパムとしてマークするようなトランスポート ルールを作成する必要はありません。単に特定の送信者またはドメインを禁止または許可し、特別な条件を付加しない場合は、トランスポート ルールではなく、スパム ポリシーの Exchange Online Protection 禁止リストおよび許可リストを使用します。この内容の詳細については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5205-p110">You don't need to create a transport rule to bypass spam filtering or mark email as spam for a sender or domain. Use the Exchange Online Protection block and allow lists in a spam policy instead of this transport rule if you simply want to block or allow a specific sender or domain and not attach any extra conditions. Learn more about this at [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
- <span data-ttu-id="e5205-p111">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)」の「トランスポート ルール」。</span><span class="sxs-lookup"><span data-stu-id="e5205-p111">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="e5205-157">このトピックの手順で使用可能なキーボード ショートカットについては、「**Exchange 管理センターのキーボード ショートカット**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5205-157">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="e5205-p112">問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="e5205-p112">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-the-eac-to-create-a-transport-rule-to-bypass-spam-filtering-for-a-domain-or-user"></a><span data-ttu-id="e5205-161">EAC でトランスポート ルールを作成し、ドメインまたはユーザーのスパム フィルタリングをバイパスする</span><span class="sxs-lookup"><span data-stu-id="e5205-161">Use the EAC to create a transport rule to bypass spam filtering for a domain or user</span></span>
<span data-ttu-id="e5205-162"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="e5205-162"></span></span>

1. <span data-ttu-id="e5205-p113">EAC で、 **[メール フロー]** \> **[ルール]** の順に移動します。 **[追加]**![[追加] アイコン](media/ITPro-EAC-AddIcon.png)、 **[スパム フィルターをバイパスする]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e5205-p113">In the EAC, navigate to **Mail flow** \> **Rules**. Choose **Add**![Add Icon](media/ITPro-EAC-AddIcon.png) and then choose **Bypass spam filtering**.</span></span>
    
2. <span data-ttu-id="e5205-p114">ルールに名前を付けます。 **[このルールを適用します]** で、 **[送信者]** を選択してから、以下の条件のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5205-p114">Give the rule a name. Under **Apply this rule if**, choose **The sender** and then select one of the following conditions:</span></span> 
    
  - <span data-ttu-id="e5205-p115">ドメインを指定する場合は、 **[ドメインが次の値である]** を選択します。 **[ドメインの指定]** ダイアログ ボックスに、安全であると指定する差出人のドメインを入力します (例: contoso.com)。 **[追加]**![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックして、そのドメインを語句の一覧に移動します。ドメインを更に追加する場合は、この手順を繰りかえします。終了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5205-p115">If you want to specify a domain, choose **domain is**. In the **Specify domain** dialog box, enter the domain of the sender you want to designate as safe, such as contoso.com. **Add**![Add Icon](media/ITPro-EAC-AddIcon.png) to move it to the list of phrases. Repeat this step if you want to add additional domains, and click **OK** when you are finished.</span></span> 
    
  - <span data-ttu-id="e5205-p116">ユーザーを指定する場合は、 **[この人物である]** を選択します。 **[メンバーの選択]** ダイアログ ボックスで、リストからユーザーを追加するか、あるいはユーザーを入力し、 **[名前の確認]** をクリックします。ユーザーをさらに追加する場合は、この手順を繰り返します。終了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5205-p116">If you want to specify a user, choose **is this person**. In the **Select members** dialog box, add the user from the list or type the user and click **Check names**. Repeat this step if you want to add additional users, and click **OK** when you are finished.</span></span> 
    
3. <span data-ttu-id="e5205-174">他のルールによってバイパス操作が元に戻されないようにするために、 **[これ以上の処理を中止する]** チェックボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5205-174">Select the **Stop processing more rules** check box to ensure that no other rule can reverse the bypass action</span></span> 
    
4. <span data-ttu-id="e5205-175">**[メッセージの送信者アドレスに一致する]** オプションで、 **[ヘッダーまたはエンベロープ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5205-175">For the **Match sender address in message** option, select **Header or envelope**.</span></span>
    
5. <span data-ttu-id="e5205-p117">これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。組織でルールを施行する前に、一定期間そのルールをテストすることをお勧めします。これらの選択項目の詳細については、「[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5205-p117">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period of time before enforcing it in your organization. For more information about these selections, see [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx).</span></span>
    
6. <span data-ttu-id="e5205-179">**[保存]** をクリックして、ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="e5205-179">Choose **Save** to save the rule.</span></span> 
    
<span data-ttu-id="e5205-180">ルールを作成して適用すると、指定したドメインまたはユーザーはスパム フィルターをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="e5205-180">After you create and enforce the rule, spam filtering is bypassed for the domain or user you specified.</span></span>
  
## <a name="use-the-eac-to-create-a-transport-rule-that-blocks-messages-sent-from-a-domain-or-user"></a><span data-ttu-id="e5205-181">ドメインまたはユーザーからの送信メッセージをブロックするトランスポート ルールを EAC で作成する</span><span class="sxs-lookup"><span data-stu-id="e5205-181">Use the EAC to create a transport rule that blocks messages sent from a domain or user</span></span>
<span data-ttu-id="e5205-182"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="e5205-182"></span></span>

1. <span data-ttu-id="e5205-p118">EAC で、 **[メール フロー]** \> **[ルール]** の順に移動します。 **[追加]**![[追加] アイコン](media/ITPro-EAC-AddIcon.png) を選択してから、 **[新しいルールの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5205-p118">In the EAC, navigate to **Mail flow** \> **Rules**. Choose **Add**![Add Icon](media/ITPro-EAC-AddIcon.png) and then choose **Create a new rule**.</span></span>
    
2. <span data-ttu-id="e5205-185">ルールに名前を付けてから、 **[その他のオプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5205-185">Give the rule a name and then click **More options**.</span></span> 
    
3. <span data-ttu-id="e5205-186">**[このルールを適用します]** で、 **[送信者]** を選択してから、以下の条件のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5205-186">Under **Apply this rule if**, choose **The sender** and then select one of the following conditions:</span></span> 
    
  - <span data-ttu-id="e5205-p119">ドメインを指定する場合は、 **[ドメインが次の値である]** を選択します。[ドメインの指定] ダイアログ ボックスに、メッセージをブロックする差出し元の差出人ドメイン (contoso.com など) を入力します。 **[追加]**![[追加] アイコン](media/ITPro-EAC-AddIcon.png)をクリックして、そのドメインを語句の一覧に移動します。ドメインを更に追加する場合は、この手順を繰り返します。終了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5205-p119">If you want to specify a domain, choose **domain is**. In the Specify domain dialog box, enter the sender domain from which you want to block messages, such as contoso.com. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png) to move it to the list of phrases. Repeat this step if you want to add additional domains, and click **OK** when you are finished.</span></span> 
    
  - <span data-ttu-id="e5205-p120">ユーザーを指定する場合は、 **[この人物である]** を選択します。 **[メンバーの選択]** ダイアログ ボックスで、リストからユーザーを追加するか、あるいはユーザーを入力し、 **[名前の確認]** をクリックします。ユーザーをさらに追加する場合は、この手順を繰り返します。終了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5205-p120">If you want to specify a user, choose **is this person**. In the **Select members** dialog box, add the user from the list or type the user and click **Check names**. Repeat this step if you want to add additional users, and click **OK** when you are finished.</span></span> 
    
4. <span data-ttu-id="e5205-194">**[実行する処理]** で、 **[メッセージをブロックする]** を選択してから、 **[だれにも通知せずにメッセージを削除する]** などのその他のオプションのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5205-194">Under **Do the following**, choose **Block the message** and then click one of the other options such as **Delete the message without notifying anyone**.</span></span>
    
5. <span data-ttu-id="e5205-195">**[その他のオプション]** をクリックしてから、 **[メッセージの送信者アドレスに一致する]** オプションで、 **[ヘッダーまたはエンベロープ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5205-195">Click **More options**, and then for the **Match sender address in message** option, select **Header or envelope**.</span></span>
    
6. <span data-ttu-id="e5205-p121">これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。組織でルールを施行する前に、一定期間そのルールをテストすることをお勧めします。これらの選択項目の詳細については、「[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5205-p121">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period of time before enforcing it in your organization. For more information about these selections, see [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx).</span></span>
    
7. <span data-ttu-id="e5205-199">**[保存]** をクリックして、ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="e5205-199">Choose **Save** to save the rule.</span></span> 
    
<span data-ttu-id="e5205-200">ルールを作成して適用すると、指定したドメインまたはユーザーから送信されたすべてのメッセージがブロックされるようになります。</span><span class="sxs-lookup"><span data-stu-id="e5205-200">After you create and enforce the rule, any messages sent from the domain or user you specify will be blocked.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e5205-201">See also</span><span class="sxs-lookup"><span data-stu-id="e5205-201">See also</span></span>
<span data-ttu-id="e5205-202"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="e5205-202"></span></span>

[<span data-ttu-id="e5205-203">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="e5205-203">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="e5205-204">トランスポート ルールを使用して、一括メールのフィルタ リングを構成するのには</span><span class="sxs-lookup"><span data-stu-id="e5205-204">Use transport rules to configure bulk email filtering</span></span>](use-transport-rules-to-configure-bulk-email-filtering.md)

