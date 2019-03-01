---
title: Office 365 で組織全体の信頼できる差出人またはブロックする差出人の一覧を作成する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/8/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: 特定の送信者からのメールを確実に受信できるようにする場合は、Exchange 管理センターでスパムフィルターポリシーの許可リストを調整できます。このようなメッセージを受信します。
ms.openlocfilehash: 0759d054f270cae03b98d9da7e2e2dcfe442d68f
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341598"
---
# <a name="create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365"></a><span data-ttu-id="269a2-103">Office 365 で組織全体の信頼できる差出人またはブロックする差出人の一覧を作成する</span><span class="sxs-lookup"><span data-stu-id="269a2-103">Create organization-wide safe sender or blocked sender lists in Office 365</span></span>
  
<span data-ttu-id="269a2-p101">特定の送信者からのメールを確実に受信できるようにする場合は、Exchange 管理センター (EAC) の [**保護** \> ] [**スパム**フィルター] で、スパムフィルターポリシーの許可リストを調整できます。詳細については[、「スパムフィルターポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。別のオプションとして、Exchange メールフロールール (トランスポートルールとも呼ばれます) を作成します。これは、スパムフィルターのドメインまたはユーザーベースの許可一覧のように機能します。同様の方法で、特定のドメインまたはユーザーから送信されたメッセージをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="269a2-p101">If you want to be sure that you receive mail from a particular sender, because you trust them and their messages, you can adjust your allow list in a spam filter policy in the Exchange admin center (EAC) at **Protection** \> **Spam filter**. Learn more about this at [Configure your spam filter policies](configure-your-spam-filter-policies.md). Another option would be create an Exchange mail flow rule (also known as a transport rule) that works like the domain or user-based allow list in the spam filter. You can block messages sent from a particular domain or user in a similar manner too.</span></span>
  
<span data-ttu-id="269a2-p102">このような状況では、メッセージヘッダーや添付ファイルの名前のチェックなどの複雑な抽出条件にフィルターを適用する必要がある場合や、メッセージに免責事項を追加したり、メッセージに期間を適用したりするなど、複雑なアクションを追加する場合に、メールフロールールが役に立ちます。e はアクティブです。ただし、特定の送信者またはドメインからの電子メールがスパムフィルターをバイパスするようにするために推奨される方法は、スパムフィルターポリシーに追加することです。これを EAC で使用するために、「 **Protection** \> **フィルター**」に進みます。詳細につい[ては、「スパムフィルターポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="269a2-p102">A mail flow rule would be useful in this situation if you need to filter for complex criteria such as checking message headers or the names of attachments or if you want to add complex actions such as adding a disclaimer to the message or applying a time period where the rule is active. However, the preferred method to make sure emails from a specific sender or domain bypass your spam filter is to add them to your spam filter policy. Get started with this in the EAC by going to **Protection** \> **Spam filter**. Learn more at [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="269a2-p103">ドメインはスプーフィングできるため、メールフロールールのドメインベースのリストは、IP アドレスベースのリストほど安全ではありません。また、送信 IP アドレスが禁止一覧に含まれている場合でも、ドメインまたはユーザーのフィルター処理がバイパスされてもブロックされます。これは、ドメインまたはユーザーのメールフロールールがグローバル IP 禁止一覧を上書きしないためです。ほとんどの場合、IP アドレスベースのリストを使用することをお勧めします。ip アドレスベースのリストを作成するには、接続フィルターで ip 許可一覧または ip 禁止一覧を使用できます。これらの IP アドレスから送信されたメッセージは、コンテンツフィルターによってチェックされません。ip アドレスを ip 許可一覧または ip 禁止一覧に追加することによって接続フィルターポリシーを構成する方法については、「 [configure the connection filter policy](configure-the-connection-filter-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="269a2-p103">A domain-based list in a mail flow rule isn't as secure as an IP address-based list, because domains can be spoofed. Also, if the sending IP address is on a Block list, it will still be blocked even if filtering for the domain or user is being bypassed. This is because a mail flow rule on a domain or user does not override the global IP Block list. We recommend using an IP address-based list in most cases. To create an IP address-based list, you can use the IP Allow list or IP Block list in the connection filter. Any messages sent from these IP addresses aren't checked by the content filter. For instructions on how to configure the connection filter policy by adding IP addresses to the IP Allow list or IP Block list, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> 
  
<span data-ttu-id="269a2-119">メールフロールールに関連する追加の管理タスクについては、「 [Exchange Online のメールフロールール (トランスポートルール)](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="269a2-119">For additional management tasks related to mail flow rules, see [Mail flow rules (transport rules) in Exchange Online](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).</span></span>
  
## <a name="use-the-eac-to-customize-a-block-or-allow-list-to-prevent-or-receive-email-from-a-domain-or-user"></a><span data-ttu-id="269a2-120">EAC で禁止または許可リストをカスタマイズして、ドメインまたはユーザーからの電子メールを拒否または受信する</span><span class="sxs-lookup"><span data-stu-id="269a2-120">Use the EAC to customize a block or allow list to prevent or receive email from a domain or user</span></span>

1. <span data-ttu-id="269a2-121">EAC の **[保護]** \> **[スパム フィルター]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="269a2-121">In the EAC, go to **Protection** \> **Spam filter**.</span></span> 
    
2. <span data-ttu-id="269a2-122">**[全般]** ページで次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="269a2-122">On the **general** page, do one of the following:</span></span> 
    
  - <span data-ttu-id="269a2-123">編集を開始するため、既定のポリシーまたは既存のポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="269a2-123">Double-click the default policy or an existing policy in order to start editing it.</span></span>
    
  - <span data-ttu-id="269a2-124">**[新規作成]** をクリックして、組織内のユーザー、グループ、およびドメインに適用可能な新しいカスタム スパム フィルター ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="269a2-124">Click **New** in order to create a new custom spam-filter policy that can be applied to users, groups, and domains in your organization.</span></span> 
    
3. <span data-ttu-id="269a2-p104">[ **受信許可一覧**] ページで、送信者やドメインなどのエントリを指定すると、それらのエントリからのメールが常に受信トレイに配信されます。これらのエントリからのメールは、迷惑メール フィルターによって処理されません。次の操作を実行してください。</span><span class="sxs-lookup"><span data-stu-id="269a2-p104">On the **Allow Lists** page, you can specify entries, such as senders or domains, that will always be delivered to the inbox. Email from these entries is not processed by the spam filter. Do the following:</span></span> 
    
  - <span data-ttu-id="269a2-p105">信頼できる送信者を [受信許可送信者一覧] に追加します。 **[追加]** をクリックし、選択ダイアログ ボックスで、許可する送信者のアドレスを追加します。複数のエントリを区切るには、セミコロンまたは改行を使用します。[OK] をクリックして **[受信許可一覧]** ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="269a2-p105">Add trusted senders to the Sender allow list. Click **Add**, and then in the selection dialog box, add the sender addresses you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page.</span></span> 
    
  - <span data-ttu-id="269a2-p106">信頼できるドメインを [受信許可ドメイン一覧] に追加します。 **[追加]** をクリックし、選択ダイアログ ボックスで、許可するドメインを追加します。複数のエントリを区切るには、セミコロンまたは改行を使用します。[OK] をクリックして **[受信許可一覧]** ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="269a2-p106">Add trusted domains to the Domain allow list. Click **Add**, and then in the selection dialog box, add the domains you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="269a2-136">トップレベル ドメインを許可した場合、不要な電子メールが受信トレイに配信される可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="269a2-136">If you allow top-level domains, it's likely that email you don't want will be delivered to an inbox.</span></span> 
  
4. <span data-ttu-id="269a2-p107">[ **受信拒否一覧**] ページで、送信者やドメインなどのエントリを指定すると、それらのエントリからのメールが常にスパムとしてマークされます。サービスにより、これらのエントリに一致する電子メールに対して、構成された精度の高いスパム処理が適用されます。</span><span class="sxs-lookup"><span data-stu-id="269a2-p107">On the **Block Lists** page, you can specify entries, such as senders or domains, that will always be marked as spam. The service will apply the configured high confidence spam action on email that matches these entries.</span></span> 
    
  - <span data-ttu-id="269a2-p108">不要な送信者を [受信拒否送信者一覧] に追加します。[ **追加**] ![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックし、選択ダイアログ ボックスで、禁止する送信者のアドレスを追加します。複数のエントリを区切るには、セミコロンまたは改行を使用します。[ **OK**] をクリックして [ **受信拒否一覧**] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="269a2-p108">Add unwanted senders to the Sender block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then in the selection dialog box, add the sender addresses you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page.</span></span> 
    
  - <span data-ttu-id="269a2-p109">不要なドメインを [受信拒否ドメイン一覧] に追加します。[ **追加**] ![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックし、選択ダイアログ ボックスで、禁止するドメインを追加します。複数のエントリを区切るには、セミコロンまたは改行を使用します。[ **OK**] をクリックして [ **受信拒否一覧**] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="269a2-p109">Add unwanted domains to the Domain block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then in the selection dialog box, add the domains you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="269a2-147">トップレベル ドメインを禁止した場合、必要なメールが迷惑メールとしてマークされる可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="269a2-147">If you block top-level domains, it's likely that email you want will be marked as spam.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin-creating-a-mail-flow-rule"></a><span data-ttu-id="269a2-148">メールフロールールの作成を開始する前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="269a2-148">What do you need to know before you begin creating a mail flow rule?</span></span>
    
- <span data-ttu-id="269a2-p110">メールフロールールを作成してスパムフィルターをバイパスしたり、送信者またはドメインに対して電子メールをスパムとしてマークしたりする必要はありません。特定の送信者またはドメインを禁止または許可し、その他の条件を添付しない場合は、このメールフロールールの代わりに、Exchange Online Protection ブロックと許可リストを使用します。詳細については[、「スパムフィルターポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="269a2-p110">You don't need to create a mail flow rule to bypass spam filtering or mark email as spam for a sender or domain. Use the Exchange Online Protection block and allow lists in a spam policy instead of this mail flow rule if you simply want to block or allow a specific sender or domain and not attach any extra conditions. Learn more about this at [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
- <span data-ttu-id="269a2-p111">この手順を実行する前に、アクセス許可を割り当てる必要があります。必要なアクセス許可については、「[メッセージングポリシーとコンプライアンスのアクセス許可](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)」の「メールフロールール」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="269a2-p111">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Mail flow rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="269a2-154">このトピックの手順で使用可能なキーボード ショートカットについては、「**Exchange 管理センターのキーボード ショートカット**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="269a2-154">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="269a2-p112">問題がある場合は、Exchange のフォーラムで質問してください。次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="269a2-p112">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612), [Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-bypass-spam-filtering-for-a-domain-or-user"></a><span data-ttu-id="269a2-158">EAC を使用して、ドメインまたはユーザーのスパムフィルタリングをバイパスするメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="269a2-158">Use the EAC to create a mail flow rule to bypass spam filtering for a domain or user</span></span>

1. <span data-ttu-id="269a2-p113">EAC で、[**メールフロー** \> **ルール**] に移動します。[**追加** ![] [](media/ITPro-EAC-AddIcon.gif)追加] アイコンを選択し、[**スパムフィルタリングをバイパス**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="269a2-p113">In the EAC, navigate to **Mail flow** \> **Rules**. Choose **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then choose **Bypass spam filtering**.</span></span>
    
2. <span data-ttu-id="269a2-p114">ルールに名前を付けます。 **[このルールを適用します]** で、 **[送信者]** を選択してから、以下の条件のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="269a2-p114">Give the rule a name. Under **Apply this rule if**, choose **The sender** and then select one of the following conditions:</span></span> 
    
  - <span data-ttu-id="269a2-p115">ドメインを指定する場合は、[ **domain is**] を選択します。[**ドメインの指定**] ダイアログボックスで、安全として指定する送信者のドメイン (contoso.com など) を入力します。**追加**![[追加](media/ITPro-EAC-AddIcon.gif) ] アイコンを語句の一覧に移動します。他のドメインを追加する場合は、この手順を繰り返し、完了したら [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="269a2-p115">If you want to specify a domain, choose **domain is**. In the **Specify domain** dialog box, enter the domain of the sender you want to designate as safe, such as contoso.com. **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) to move it to the list of phrases. Repeat this step if you want to add additional domains, and click **OK** when you are finished.</span></span> 
    
  - <span data-ttu-id="269a2-p116">ユーザーを指定する場合は、 **[この人物である]** を選択します。 **[メンバーの選択]** ダイアログ ボックスで、リストからユーザーを追加するか、あるいはユーザーを入力し、 **[名前の確認]** をクリックします。ユーザーをさらに追加する場合は、この手順を繰り返します。終了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="269a2-p116">If you want to specify a user, choose **is this person**. In the **Select members** dialog box, add the user from the list or type the user and click **Check names**. Repeat this step if you want to add additional users, and click **OK** when you are finished.</span></span> 
    
3. <span data-ttu-id="269a2-170">他のルールによってバイパス操作が元に戻されないようにするために、 **[これ以上の処理を中止する]** チェックボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="269a2-170">Select the **Stop processing more rules** check box to ensure that no other rule can reverse the bypass action</span></span> 
    
4. <span data-ttu-id="269a2-171">**[メッセージの送信者アドレスに一致する]** オプションで、 **[ヘッダーまたはエンベロープ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="269a2-171">For the **Match sender address in message** option, select **Header or envelope**.</span></span>
    
5. <span data-ttu-id="269a2-172">これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。</span><span class="sxs-lookup"><span data-stu-id="269a2-172">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span>
    
6. <span data-ttu-id="269a2-173">**[保存]** をクリックして、ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="269a2-173">Choose **Save** to save the rule.</span></span> 
    
<span data-ttu-id="269a2-174">ルールを作成して適用すると、指定したドメインまたはユーザーはスパム フィルターをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="269a2-174">After you create and enforce the rule, spam filtering is bypassed for the domain or user you specified.</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-that-blocks-messages-sent-from-a-domain-or-user"></a><span data-ttu-id="269a2-175">EAC を使用して、ドメインまたはユーザーから送信されたメッセージをブロックするメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="269a2-175">Use the EAC to create a mail flow rule that blocks messages sent from a domain or user</span></span>

1. <span data-ttu-id="269a2-p117">EAC で、[**メールフロー** \> **ルール**] に移動します。[**追加** ![] [](media/ITPro-EAC-AddIcon.gif)追加] アイコンを選択し、[**新しいルールの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="269a2-p117">In the EAC, navigate to **Mail flow** \> **Rules**. Choose **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then choose **Create a new rule**.</span></span>
    
2. <span data-ttu-id="269a2-178">ルールに名前を付けてから、 **[その他のオプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="269a2-178">Give the rule a name and then click **More options**.</span></span> 
    
3. <span data-ttu-id="269a2-179">**[このルールを適用します]** で、 **[送信者]** を選択してから、以下の条件のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="269a2-179">Under **Apply this rule if**, choose **The sender** and then select one of the following conditions:</span></span> 
    
  - <span data-ttu-id="269a2-p118">ドメインを指定する場合は、[ **domain is**] を選択します。[ドメインの指定] ダイアログボックスで、メッセージをブロックする送信者ドメイン (contoso.com など) を入力します。[追加] アイコン](media/ITPro-EAC-AddIcon.gif)をクリックして、それを語句の一覧に移動します。 \*\*\*\* ![他のドメインを追加する場合は、この手順を繰り返し、完了したら [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="269a2-p118">If you want to specify a domain, choose **domain is**. In the Specify domain dialog box, enter the sender domain from which you want to block messages, such as contoso.com. Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) to move it to the list of phrases. Repeat this step if you want to add additional domains, and click **OK** when you are finished.</span></span> 
    
  - <span data-ttu-id="269a2-p119">ユーザーを指定する場合は、 **[この人物である]** を選択します。 **[メンバーの選択]** ダイアログ ボックスで、リストからユーザーを追加するか、あるいはユーザーを入力し、 **[名前の確認]** をクリックします。ユーザーをさらに追加する場合は、この手順を繰り返します。終了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="269a2-p119">If you want to specify a user, choose **is this person**. In the **Select members** dialog box, add the user from the list or type the user and click **Check names**. Repeat this step if you want to add additional users, and click **OK** when you are finished.</span></span> 
    
4. <span data-ttu-id="269a2-187">**[実行する処理]** で、 **[メッセージをブロックする]** を選択してから、 **[だれにも通知せずにメッセージを削除する]** などのその他のオプションのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="269a2-187">Under **Do the following**, choose **Block the message** and then click one of the other options such as **Delete the message without notifying anyone**.</span></span>
    
5. <span data-ttu-id="269a2-188">**[その他のオプション]** をクリックしてから、 **[メッセージの送信者アドレスに一致する]** オプションで、 **[ヘッダーまたはエンベロープ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="269a2-188">Click **More options**, and then for the **Match sender address in message** option, select **Header or envelope**.</span></span>
    
6. <span data-ttu-id="269a2-p120">必要に応じて、ルールを監査したり、ルールをテストしたり、特定の期間中にルールをアクティブ化したり、その他の選択を行ったりすることができます。組織内でルールを適用する前に、一定の期間、ルールをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="269a2-p120">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period of time before enforcing it in your organization.</span></span>
    
7. <span data-ttu-id="269a2-191">**[保存]** をクリックして、ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="269a2-191">Choose **Save** to save the rule.</span></span> 
    
<span data-ttu-id="269a2-192">ルールを作成して適用すると、指定したドメインまたはユーザーから送信されたすべてのメッセージがブロックされるようになります。</span><span class="sxs-lookup"><span data-stu-id="269a2-192">After you create and enforce the rule, any messages sent from the domain or user you specify will be blocked.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="269a2-193">See also</span><span class="sxs-lookup"><span data-stu-id="269a2-193">See also</span></span>

[<span data-ttu-id="269a2-194">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="269a2-194">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="269a2-195">メールフロールールを使用して一括メールフィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="269a2-195">Use mail flow rules to configure bulk email filtering</span></span>](use-transport-rules-to-configure-bulk-email-filtering.md)

