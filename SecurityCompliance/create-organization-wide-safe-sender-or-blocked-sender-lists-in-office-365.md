---
title: Office 365 で組織全体の信頼できる差出人またはブロックする差出人のリストを作成する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/8/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: 特定の送信者からのメールを確実に受信できるようにする場合は、Exchange 管理センターでスパムフィルターポリシーの許可リストを調整できます。このようなメッセージを受信します。
ms.openlocfilehash: 765660ba8c0c9ab384368a0f0c4cd194e4ff2bc6
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258175"
---
# <a name="create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365"></a><span data-ttu-id="f7435-103">Office 365 で組織全体の信頼できる差出人またはブロックする差出人のリストを作成する</span><span class="sxs-lookup"><span data-stu-id="f7435-103">Create organization-wide safe sender or blocked sender lists in Office 365</span></span>
  
<span data-ttu-id="f7435-104">特定の送信者とそのメッセージを信頼しているため、その送信者からのメールを確実に受信したい場合は、Exchange 管理センター (EAC) の **[保護]** \> **[スパム フィルター]** で開くスパム フィルター ポリシーで許可リストを調整できます。</span><span class="sxs-lookup"><span data-stu-id="f7435-104">If you want to be sure that you receive mail from a particular sender, because you trust them and their messages, you can adjust your allow list in a spam filter policy in the Exchange admin center (EAC) at **Protection** \> **Spam filter**.</span></span> <span data-ttu-id="f7435-105">この内容の詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7435-105">Learn more about this at [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="f7435-106">別のオプションとして、Exchange メールフロールール (トランスポートルールとも呼ばれます) を作成します。これは、スパムフィルターのドメインまたはユーザーベースの許可一覧のように機能します。</span><span class="sxs-lookup"><span data-stu-id="f7435-106">Another option would be create an Exchange mail flow rule (also known as a transport rule) that works like the domain or user-based allow list in the spam filter.</span></span> <span data-ttu-id="f7435-107">同様の方法でも、特定のドメインまたはユーザーからの送信メッセージをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="f7435-107">You can block messages sent from a particular domain or user in a similar manner too.</span></span>
  
<span data-ttu-id="f7435-108">このような状況では、メッセージヘッダーや添付ファイルの名前のチェックなどの複雑な抽出条件にフィルターを適用する必要がある場合や、メッセージに免責事項を追加したり、メッセージに期間を適用したりするなど、複雑なアクションを追加する場合に、メールフロールールが役に立ちます。e はアクティブです。</span><span class="sxs-lookup"><span data-stu-id="f7435-108">A mail flow rule would be useful in this situation if you need to filter for complex criteria such as checking message headers or the names of attachments or if you want to add complex actions such as adding a disclaimer to the message or applying a time period where the rule is active.</span></span> <span data-ttu-id="f7435-109">ただし、特定の送信者またはドメインからの電子メールを確実にスパム フィルターからバイパスさせる方法としては、スパム フィルター ポリシーにその電子メールを追加する方法が優先されます。</span><span class="sxs-lookup"><span data-stu-id="f7435-109">However, the preferred method to make sure emails from a specific sender or domain bypass your spam filter is to add them to your spam filter policy.</span></span> <span data-ttu-id="f7435-110">**[保護]** \> **[スパム フィルター]** に移動して、EAC でこの作業をやってみましょう。</span><span class="sxs-lookup"><span data-stu-id="f7435-110">Get started with this in the EAC by going to **Protection** \> **Spam filter**.</span></span> <span data-ttu-id="f7435-111">詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7435-111">Learn more at [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="f7435-112">ドメインはスプーフィングできるため、メールフロールールのドメインベースのリストは、IP アドレスベースのリストほど安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="f7435-112">A domain-based list in a mail flow rule isn't as secure as an IP address-based list, because domains can be spoofed.</span></span> <span data-ttu-id="f7435-113">また、送信 IP アドレスが禁止一覧に含まれる場合、ドメインまたはユーザーのフィルター処理がバイパスされても、そのアドレスはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f7435-113">Also, if the sending IP address is on a Block list, it will still be blocked even if filtering for the domain or user is being bypassed.</span></span> <span data-ttu-id="f7435-114">これは、ドメインまたはユーザーのメールフロールールがグローバル IP 禁止一覧を上書きしないためです。</span><span class="sxs-lookup"><span data-stu-id="f7435-114">This is because a mail flow rule on a domain or user does not override the global IP Block list.</span></span> <span data-ttu-id="f7435-115">通常は、IP アドレスベースのリストを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f7435-115">We recommend using an IP address-based list in most cases.</span></span> <span data-ttu-id="f7435-116">IP アドレスベースのリストを作成するには、接続フィルター内で IP 許可一覧または IP 禁止一覧を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7435-116">To create an IP address-based list, you can use the IP Allow list or IP Block list in the connection filter.</span></span> <span data-ttu-id="f7435-117">これらの IP アドレスから送信されたメッセージはコンテンツ フィルターによってチェックされません。</span><span class="sxs-lookup"><span data-stu-id="f7435-117">Any messages sent from these IP addresses aren't checked by the content filter.</span></span> <span data-ttu-id="f7435-118">IP アドレスを IP 許可一覧または IP 禁止一覧に追加することによる接続フィルター ポリシーの構成方法の手順については、「[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7435-118">For instructions on how to configure the connection filter policy by adding IP addresses to the IP Allow list or IP Block list, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> 
  
<span data-ttu-id="f7435-119">メールフロールールに関連する追加の管理タスクについては、「 [Exchange Online のメールフロールール (トランスポートルール)](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7435-119">For additional management tasks related to mail flow rules, see [Mail flow rules (transport rules) in Exchange Online](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).</span></span>
  
## <a name="use-the-eac-to-customize-a-block-or-allow-list-to-prevent-or-receive-email-from-a-domain-or-user"></a><span data-ttu-id="f7435-120">EAC で禁止または許可リストをカスタマイズして、ドメインまたはユーザーからの電子メールを拒否または受信する</span><span class="sxs-lookup"><span data-stu-id="f7435-120">Use the EAC to customize a block or allow list to prevent or receive email from a domain or user</span></span>

1. <span data-ttu-id="f7435-121">EAC の **[保護]** \> **[スパム フィルター]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7435-121">In the EAC, go to **Protection** \> **Spam filter**.</span></span> 
    
2. <span data-ttu-id="f7435-122">**[全般]** ページで次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7435-122">On the **general** page, do one of the following:</span></span> 
    
  - <span data-ttu-id="f7435-123">編集を開始するため、既定のポリシーまたは既存のポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7435-123">Double-click the default policy or an existing policy in order to start editing it.</span></span>
    
  - <span data-ttu-id="f7435-124">**[新規作成]** をクリックして、組織内のユーザー、グループ、およびドメインに適用可能な新しいカスタム スパム フィルター ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7435-124">Click **New** in order to create a new custom spam-filter policy that can be applied to users, groups, and domains in your organization.</span></span> 
    
3. <span data-ttu-id="f7435-p104">[ **受信許可一覧**] ページで、送信者やドメインなどのエントリを指定すると、それらのエントリからのメールが常に受信トレイに配信されます。これらのエントリからのメールは、迷惑メール フィルターによって処理されません。次の操作を実行してください。</span><span class="sxs-lookup"><span data-stu-id="f7435-p104">On the **Allow Lists** page, you can specify entries, such as senders or domains, that will always be delivered to the inbox. Email from these entries is not processed by the spam filter. Do the following:</span></span> 
    
  - <span data-ttu-id="f7435-p105">信頼できる送信者を [受信許可送信者一覧] に追加します。 **[追加]** をクリックし、選択ダイアログ ボックスで、許可する送信者のアドレスを追加します。複数のエントリを区切るには、セミコロンまたは改行を使用します。[OK] をクリックして **[受信許可一覧]** ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="f7435-p105">Add trusted senders to the Sender allow list. Click **Add**, and then in the selection dialog box, add the sender addresses you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page.</span></span> 
    
  - <span data-ttu-id="f7435-p106">信頼できるドメインを [受信許可ドメイン一覧] に追加します。 **[追加]** をクリックし、選択ダイアログ ボックスで、許可するドメインを追加します。複数のエントリを区切るには、セミコロンまたは改行を使用します。[OK] をクリックして **[受信許可一覧]** ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="f7435-p106">Add trusted domains to the Domain allow list. Click **Add**, and then in the selection dialog box, add the domains you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="f7435-136">トップレベル ドメインを許可した場合、不要な電子メールが受信トレイに配信される可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="f7435-136">If you allow top-level domains, it's likely that email you don't want will be delivered to an inbox.</span></span> 
  
4. <span data-ttu-id="f7435-p107">[ **受信拒否一覧**] ページで、送信者やドメインなどのエントリを指定すると、それらのエントリからのメールが常にスパムとしてマークされます。サービスにより、これらのエントリに一致する電子メールに対して、構成された精度の高いスパム処理が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f7435-p107">On the **Block Lists** page, you can specify entries, such as senders or domains, that will always be marked as spam. The service will apply the configured high confidence spam action on email that matches these entries.</span></span> 
    
  - <span data-ttu-id="f7435-p108">不要な送信者を [受信拒否送信者一覧] に追加します。[ **追加**] ![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックし、選択ダイアログ ボックスで、禁止する送信者のアドレスを追加します。複数のエントリを区切るには、セミコロンまたは改行を使用します。[ **OK**] をクリックして [ **受信拒否一覧**] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="f7435-p108">Add unwanted senders to the Sender block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then in the selection dialog box, add the sender addresses you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page.</span></span> 
    
  - <span data-ttu-id="f7435-p109">不要なドメインを [受信拒否ドメイン一覧] に追加します。[ **追加**] ![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックし、選択ダイアログ ボックスで、禁止するドメインを追加します。複数のエントリを区切るには、セミコロンまたは改行を使用します。[ **OK**] をクリックして [ **受信拒否一覧**] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="f7435-p109">Add unwanted domains to the Domain block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then in the selection dialog box, add the domains you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="f7435-147">トップレベル ドメインを禁止した場合、必要なメールが迷惑メールとしてマークされる可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="f7435-147">If you block top-level domains, it's likely that email you want will be marked as spam.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin-creating-a-mail-flow-rule"></a><span data-ttu-id="f7435-148">メールフロールールの作成を開始する前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="f7435-148">What do you need to know before you begin creating a mail flow rule?</span></span>
    
- <span data-ttu-id="f7435-149">メールフロールールを作成してスパムフィルターをバイパスしたり、送信者またはドメインに対して電子メールをスパムとしてマークしたりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f7435-149">You don't need to create a mail flow rule to bypass spam filtering or mark email as spam for a sender or domain.</span></span> <span data-ttu-id="f7435-150">特定の送信者またはドメインを禁止または許可し、その他の条件を添付しない場合は、このメールフロールールの代わりに、Exchange Online Protection ブロックと許可リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7435-150">Use the Exchange Online Protection block and allow lists in a spam policy instead of this mail flow rule if you simply want to block or allow a specific sender or domain and not attach any extra conditions.</span></span> <span data-ttu-id="f7435-151">この内容の詳細については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7435-151">Learn more about this at [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
- <span data-ttu-id="f7435-152">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7435-152">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="f7435-153">必要なアクセス許可については、「[メッセージングポリシーとコンプライアンスのアクセス許可](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)」の「メールフロールール」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7435-153">To see what permissions you need, see the "Mail flow rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="f7435-154">このトピックの手順で使用可能なキーボード ショートカットについては、「**Exchange 管理センターのキーボード ショートカット**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7435-154">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="f7435-p112">問題がある場合は、Exchange のフォーラムで質問してください。次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="f7435-p112">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612), [Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-bypass-spam-filtering-for-a-domain-or-user"></a><span data-ttu-id="f7435-158">EAC を使用して、ドメインまたはユーザーのスパムフィルタリングをバイパスするメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="f7435-158">Use the EAC to create a mail flow rule to bypass spam filtering for a domain or user</span></span>

1. <span data-ttu-id="f7435-159">EAC で、 **[メール フロー]** \> **[ルール]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7435-159">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span> <span data-ttu-id="f7435-160">[**追加** ![] [](media/ITPro-EAC-AddIcon.gif)追加] アイコンを選択し、[**スパムフィルタリングをバイパス**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7435-160">Choose **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then choose **Bypass spam filtering**.</span></span>
    
2. <span data-ttu-id="f7435-161">ルールに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="f7435-161">Give the rule a name.</span></span> <span data-ttu-id="f7435-162">**[このルールを適用します]** で、 **[送信者]** を選択してから、以下の条件のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7435-162">Under **Apply this rule if**, choose **The sender** and then select one of the following conditions:</span></span> 
    
  - <span data-ttu-id="f7435-163">ドメインを指定する場合は、[ **domain is**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7435-163">If you want to specify a domain, choose **domain is**.</span></span> <span data-ttu-id="f7435-164">[**ドメインの指定**] ダイアログボックスで、安全として指定する送信者のドメイン (contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="f7435-164">In the **Specify domain** dialog box, enter the domain of the sender you want to designate as safe, such as contoso.com.</span></span> <span data-ttu-id="f7435-165">**追加**![[追加](media/ITPro-EAC-AddIcon.gif) ] アイコンを語句の一覧に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7435-165">**Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) to move it to the list of phrases.</span></span> <span data-ttu-id="f7435-166">他のドメインを追加する場合は、この手順を繰り返し、完了したら [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7435-166">Repeat this step if you want to add additional domains, and click **OK** when you are finished.</span></span> 
    
  - <span data-ttu-id="f7435-p116">ユーザーを指定する場合は、 **[この人物である]** を選択します。 **[メンバーの選択]** ダイアログ ボックスで、リストからユーザーを追加するか、あるいはユーザーを入力し、 **[名前の確認]** をクリックします。ユーザーをさらに追加する場合は、この手順を繰り返します。終了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7435-p116">If you want to specify a user, choose **is this person**. In the **Select members** dialog box, add the user from the list or type the user and click **Check names**. Repeat this step if you want to add additional users, and click **OK** when you are finished.</span></span> 
    
3. <span data-ttu-id="f7435-170">他のルールによってバイパス操作が元に戻されないようにするために、 **[これ以上の処理を中止する]** チェックボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7435-170">Select the **Stop processing more rules** check box to ensure that no other rule can reverse the bypass action</span></span> 
    
4. <span data-ttu-id="f7435-171">**[メッセージの送信者アドレスに一致する]** オプションで、 **[ヘッダーまたはエンベロープ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7435-171">For the **Match sender address in message** option, select **Header or envelope**.</span></span>
    
5. <span data-ttu-id="f7435-172">これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。</span><span class="sxs-lookup"><span data-stu-id="f7435-172">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span>
    
6. <span data-ttu-id="f7435-173">**[保存]** をクリックして、ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="f7435-173">Choose **Save** to save the rule.</span></span> 
    
<span data-ttu-id="f7435-174">ルールを作成して適用すると、指定したドメインまたはユーザーはスパム フィルターをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="f7435-174">After you create and enforce the rule, spam filtering is bypassed for the domain or user you specified.</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-that-blocks-messages-sent-from-a-domain-or-user"></a><span data-ttu-id="f7435-175">EAC を使用して、ドメインまたはユーザーから送信されたメッセージをブロックするメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="f7435-175">Use the EAC to create a mail flow rule that blocks messages sent from a domain or user</span></span>

1. <span data-ttu-id="f7435-176">EAC で、 **[メール フロー]** \> **[ルール]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f7435-176">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span> <span data-ttu-id="f7435-177">[**追加** ![] [](media/ITPro-EAC-AddIcon.gif)追加] アイコンを選択し、[**新しいルールの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7435-177">Choose **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then choose **Create a new rule**.</span></span>
    
2. <span data-ttu-id="f7435-178">ルールに名前を付けてから、 **[その他のオプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7435-178">Give the rule a name and then click **More options**.</span></span> 
    
3. <span data-ttu-id="f7435-179">**[このルールを適用します]** で、 **[送信者]** を選択してから、以下の条件のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7435-179">Under **Apply this rule if**, choose **The sender** and then select one of the following conditions:</span></span> 
    
  - <span data-ttu-id="f7435-180">ドメインを指定する場合は、[ **domain is**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7435-180">If you want to specify a domain, choose **domain is**.</span></span> <span data-ttu-id="f7435-181">[ドメインの指定] ダイアログボックスで、メッセージをブロックする送信者ドメイン (contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="f7435-181">In the Specify domain dialog box, enter the sender domain from which you want to block messages, such as contoso.com.</span></span> <span data-ttu-id="f7435-182">[追加] アイコン](media/ITPro-EAC-AddIcon.gif)をクリックして、それを語句の一覧に移動します。 \*\*\*\* ![</span><span class="sxs-lookup"><span data-stu-id="f7435-182">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) to move it to the list of phrases.</span></span> <span data-ttu-id="f7435-183">他のドメインを追加する場合は、この手順を繰り返し、完了したら [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7435-183">Repeat this step if you want to add additional domains, and click **OK** when you are finished.</span></span> 
    
  - <span data-ttu-id="f7435-p119">ユーザーを指定する場合は、 **[この人物である]** を選択します。 **[メンバーの選択]** ダイアログ ボックスで、リストからユーザーを追加するか、あるいはユーザーを入力し、 **[名前の確認]** をクリックします。ユーザーをさらに追加する場合は、この手順を繰り返します。終了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7435-p119">If you want to specify a user, choose **is this person**. In the **Select members** dialog box, add the user from the list or type the user and click **Check names**. Repeat this step if you want to add additional users, and click **OK** when you are finished.</span></span> 
    
4. <span data-ttu-id="f7435-187">**[実行する処理]** で、 **[メッセージをブロックする]** を選択してから、 **[だれにも通知せずにメッセージを削除する]** などのその他のオプションのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7435-187">Under **Do the following**, choose **Block the message** and then click one of the other options such as **Delete the message without notifying anyone**.</span></span>
    
5. <span data-ttu-id="f7435-188">**[その他のオプション]** をクリックしてから、 **[メッセージの送信者アドレスに一致する]** オプションで、 **[ヘッダーまたはエンベロープ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7435-188">Click **More options**, and then for the **Match sender address in message** option, select **Header or envelope**.</span></span>
    
6. <span data-ttu-id="f7435-189">これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。</span><span class="sxs-lookup"><span data-stu-id="f7435-189">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="f7435-190">組織でルールを施行する前に、一定期間そのルールをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f7435-190">We recommend testing the rule for a period of time before enforcing it in your organization.</span></span>
    
7. <span data-ttu-id="f7435-191">**[保存]** をクリックして、ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="f7435-191">Choose **Save** to save the rule.</span></span> 
    
<span data-ttu-id="f7435-192">ルールを作成して適用すると、指定したドメインまたはユーザーから送信されたすべてのメッセージがブロックされるようになります。</span><span class="sxs-lookup"><span data-stu-id="f7435-192">After you create and enforce the rule, any messages sent from the domain or user you specify will be blocked.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f7435-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7435-193">See also</span></span>

[<span data-ttu-id="f7435-194">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="f7435-194">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="f7435-195">メール フロー ルールを使用してバルク メールのフィルター処理を構成する</span><span class="sxs-lookup"><span data-stu-id="f7435-195">Use mail flow rules to configure bulk email filtering</span></span>](use-transport-rules-to-configure-bulk-email-filtering.md)

