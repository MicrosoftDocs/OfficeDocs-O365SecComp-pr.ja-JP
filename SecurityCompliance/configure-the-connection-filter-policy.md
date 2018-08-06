---
title: 接続フィルター ポリシーを構成する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
description: 信頼できる人から送信された電子メールがブロックされていないことを確認するには、信頼できる IP アドレスの安全な送信者リストとも呼ばれ、許可リストを作成するのには、接続フィルター ポリシーを使用することができます。受信拒否リストを作成することもできます。
ms.openlocfilehash: d106e55779c6246b77018fef3ab9d58fa759d99e
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027604"
---
# <a name="configure-the-connection-filter-policy"></a><span data-ttu-id="0d7b2-104">接続フィルター ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="0d7b2-104">Configure the connection filter policy</span></span>
 
<span data-ttu-id="0d7b2-p102">ほとんどの人は友人やビジネス パートナーを信頼しています。信頼する人からの電子メールが迷惑メール フォルダーに入っていたり、スパム フィルターによって完全にブロックされたりすると、もどかしさを感じます。そのようなメールがブロックされないようにするには、接続フィルター ポリシーを利用して許可リスト (「差出人セーフ リスト」ともいう) を作成し、信頼する IP アドレスを登録することができます。また、受信拒否リストを作成して既知のスパム メール送信者の IP アドレスを登録し、そのような送信者からの電子メール メッセージを受信しないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p102">Most of us have friends and business partners we trust. It can be frustrating to find email from them in your junk email folder, or even blocked entirely by a spam filter. If you want to make sure that email sent from people you trust isn't blocked, you can use the connection filter policy to create an Allow list, also known as a safe sender list, of IP addresses that you trust. You can also create a blocked senders list, which is a list of IP addresses, typically from known spammers, that you don't ever want to receive email messages from.</span></span>
  
 <span data-ttu-id="0d7b2-p103">組織全体に適用されるスパム設定の詳細については、「 [EOP と Office 365 でメールが迷惑メールとして検出されないようにする](https://go.microsoft.com/fwlink/p/?LinkId=534224)」または「[Office 365 のスパム フィルターでスパムや迷惑メールをブロックして、検出漏れ問題を防止する](https://go.microsoft.com/fwlink/p/?LinkId=534225)」を参照してください。これらは、管理者レベルの制御権限を持っている場合にスパムの誤検知や検出漏れを防ぐ上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p103">For more spam settings that apply to the whole organization, take a look at [How to help ensure that a message isn't marked as spam](https://go.microsoft.com/fwlink/p/?LinkId=534224) or [Block email spam with the Office 365 spam filter to prevent false negative issues](https://go.microsoft.com/fwlink/p/?LinkId=534225). These are helpful if you have administrator-level control and you want to prevent false positives or false negatives.</span></span>
  
<span data-ttu-id="0d7b2-111">次のビデオでは、接続フィルター ポリシーの構成手順を示します。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-111">The following video shows the configuration steps for the connection filter policy:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0d7b2-112">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="0d7b2-112">What do you need to know before you begin?</span></span>
<span data-ttu-id="0d7b2-113"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="0d7b2-113"></span></span>

- <span data-ttu-id="0d7b2-114">予想所要時間 : 15 分</span><span class="sxs-lookup"><span data-stu-id="0d7b2-114">Estimated time to complete: 15 minutes</span></span>
    
- <span data-ttu-id="0d7b2-p104">このプロシージャまたはプロシージャを実行する前にアクセス許可を割り当てる必要があります。必要なアクセス許可については、 [Exchange のオンラインでの機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)トピックの「スパム対策」エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
    
- <span data-ttu-id="0d7b2-p105">許可またはブロックする送信者の IP アドレスを取得するには、メッセージのインターネット ヘッダーを確認するという方法があります。「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」で説明されているように、CIP ヘッダーを調べます。メール クライアントでメッセージ ヘッダーを表示する方法については、「[メッセージ ヘッダー アナライザー](https://go.microsoft.com/fwlink/p/?LinkId=306583)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p105">To obtain the IP address of the sender whose messages you want to allow or block, you can check the Internet header of the message. Look for the CIP header as described in [Anti-spam message headers](anti-spam-message-headers.md). For information about how to view a message header in various email clients, see the [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583) topic.</span></span> 
    
- <span data-ttu-id="0d7b2-120">IP ブロック一覧の IP アドレスから送信された電子メール メッセージは拒否され、スパムとしてマークされず、追加のフィルター処理は行われません。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-120">Email messages sent from an IP address on the IP Block list are rejected, not marked as spam, and no additional filtering occurs.</span></span>
    
- <span data-ttu-id="0d7b2-p106">リモート PowerShell を使用しても、次の接続フィルターの手順を実行できます。設定と、接続フィルター ポリシーの設定を編集するのには[一連の HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx)を確認するのには、 [Get HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx)コマンドレットを使用します。Exchange のオンライン保護への接続に Windows PowerShell を使用する方法については、 [Exchange のオンライン保護 PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=627290)を参照してください。Exchange Online に接続する Windows PowerShell を使用する方法については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p106">The following connection filter procedure can also be performed via remote PowerShell. Use the [Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) cmdlet to review your settings, and the [Set-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) to edit your connection filter policy settings. To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290). To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="0d7b2-125">このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-125">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a><span data-ttu-id="0d7b2-126">EAC を使用して既定の接続フィルター ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="0d7b2-126">Use the EAC to edit the default connection filter policy</span></span>
<span data-ttu-id="0d7b2-127"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="0d7b2-127"></span></span>

<span data-ttu-id="0d7b2-p107">IP 許可リストまたは IP 禁止リストを作成するには、Exchange 管理センター (EAC) で接続フィルター ポリシーを編集します。接続フィルター ポリシーの設定は、受信メッセージのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p107">You create an IP Allow list or IP Block list by editing the connection filter policy in the Exchange admin center (EAC). The connection filter policy settings are applied to inbound messages only.</span></span>
  
1. <span data-ttu-id="0d7b2-130">Exchange 管理センター (EAC) で、 **[保護]** \> **[接続フィルター]** に移動し、既定のポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-130">In the Exchange admin center (EAC), navigate to **Protection** \> **Connection filter**, and then double-click the default policy.</span></span>
    
2. <span data-ttu-id="0d7b2-131">**[接続フィルター]** メニュー項目をクリックし、IP 許可一覧、IP 禁止一覧、あるいはその両方のうち、必要な一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-131">Click the **Connection filtering** menu item and then create the lists you want: an IP Allow list, an IP Block list, or both.</span></span> 
    
    <span data-ttu-id="0d7b2-p108">この一覧を作成するには、![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックします。後続のダイアログ ボックスでは、IP アドレスまたはアドレス範囲を指定して **[OK]** をクリックします。さらにアドレスを追加するには、このプロセスを繰り返します。(IP アドレスは、追加後に編集または削除できます。)</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p108">To create these lists, click ![Add Icon](media/ITPro-EAC-AddIcon.png). In the subsequent dialog box, specify the IP address or address range, and then click **ok**. Repeat this process to add additional addresses. (You can also edit or remove IP addresses after they have been added.)</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="0d7b2-p109">両方の一覧に IP アドレスを追加した場合、その IP アドレスから送信される電子メールは許可されます。 >  IPV4 の IP アドレスは nnn.nnn.nnn.nnn (nnn は 0 から 255 までの数値) の形式で指定する必要があります。クラスレス ドメイン間ルーティング (CIDR) の範囲を nnn.nnn.nnn.nnn/rr (rr は 24 から 32 までの数値) の形式で指定することもできます。24 から 32 以外の範囲を指定するには、「 [IP 許可一覧を構成する場合のその他の留意点](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists)」を参照してください。 >  最大 1273 のエントリを指定できます。各エントリは、単一の IP アドレス、または IP アドレスの CIDR 範囲 (/24 から /32 まで) にすることができます。 >  TLS 暗号化メッセージを送信している場合は、IPv6 のアドレスとアドレス範囲はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p109">If you add an IP address to both lists, email sent from it is allowed. >  IPV4 IP addresses must be specified in the format nnn.nnn.nnn.nnn where nnn is a number from 0 to 255. You can also specify Classless Inter-Domain Routing (CIDR) ranges in the format nnn.nnn.nnn.nnn/rr where rr is a number from 24 to 32. To specify ranges outside of the 24 to 32 range, see [Additional considerations when configuring IP Allow lists](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists). >  You can specify a maximum of 1273 entries, where an entry is either a single IP address or a CIDR range of IP addresses from /24 to /32. >  If you're sending TLS-encrypted messages, IPv6 addresses and address ranges are not supported.</span></span> 
  
3. <span data-ttu-id="0d7b2-p110">オプションとして、 **[セーフ リストを有効にする]** チェック ボックスを選択していくつかの既知の送信者からの電子メールをブロックしないようにできます。そのために、Microsoft は、信頼できる送信者のサード パーティ ソースにサブスクライブしています。このセーフ リストを使用すれば、信頼できる送信者に誤ってスパムのマークを付けないようにできます。このオプションを選択すると、誤検知 (スパムとして分類される正常なメール) の受信数が減少するため、選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p110">Optionally, select the **Enable safe list** check box to prevent missing email from certain well-known senders. How? Microsoft subscribes to third-party sources of trusted senders. Using this safe list means that these trusted senders aren't mistakenly marked as spam. We recommend selecting this option because it should reduce the number of false positives (good mail that's classified as spam) you receive.</span></span> 
    
4. <span data-ttu-id="0d7b2-p111">**[保存]** をクリックします。既定のポリシー設定の概要が右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p111">Click **save**. A summary of your default policy settings appears in the right pane.</span></span>
    
## <a name="additional-considerations-when-configuring-ip-allow-lists"></a><span data-ttu-id="0d7b2-149">IP 許可一覧を構成する場合のその他の留意点</span><span class="sxs-lookup"><span data-stu-id="0d7b2-149">Additional considerations when configuring IP Allow lists</span></span>
<span data-ttu-id="0d7b2-150"><a name="bkmk_addtionalconsiderationswhenconfiguringipallowlists"> </a></span><span class="sxs-lookup"><span data-stu-id="0d7b2-150"></span></span>

<span data-ttu-id="0d7b2-151">IP 許可一覧を構成する場合に考慮するまたは認識すべきその他の留意点を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-151">The following are additional considerations you may want to consider or that you should be aware of when configuring an IP Allow list.</span></span>
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a><span data-ttu-id="0d7b2-152">推奨範囲外の CIDR 範囲の指定</span><span class="sxs-lookup"><span data-stu-id="0d7b2-152">Specifying a CIDR range that falls outside of the recommended range</span></span>

<span data-ttu-id="0d7b2-p112">/1 ～ /23 の CIDR IP アドレス範囲を指定するには、Spam Confidence Level (SCL) を **[スパム フィルターをバイパスする]** に設定した、この IP アドレス範囲に対して動作するトランスポート ルールを作成する必要があります (この IP アドレス範囲から受信されたすべてのメッセージが "非スパム" に設定され、サービスによるフィルタリングがこれ以上行われないことを意味します)。ただし、これらの IP アドレスのいずれかが Microsoft 独自のブロック リストのいずれか、または、サード・パーティ・ブロック・リストのいずれかに含まれている場合は、これらのメッセージもブロックされます。そのため、/32 ～ /24 の IP アドレス範囲の使用を強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p112">To specify a CIDR IP address range from /1 to /23, you must create a Transport rule that operates on the IP address range that sets the spam confidence level (SCL) to **Bypass spam filtering** (meaning that all messages received from within this IP address range are set to "not spam�? and no additional filtering is performed by the service). However, if any of these IP addresses appear on any of Microsoft's proprietary block lists or on any of our third-party block lists, these messages will still be blocked. It is therefore strongly recommended that you use the /32 to /24 IP address range.</span></span> 
  
<span data-ttu-id="0d7b2-157">トランスポート ルールを作成するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-157">To create this Transport rule, perform the following steps.</span></span>
  
1. <span data-ttu-id="0d7b2-158">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-158">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="0d7b2-159">![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックしてから、 **[新しいルールを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-159">Click ![Add Icon](media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="0d7b2-160">ルールに名前を付けてから、 **[その他のオプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-160">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="0d7b2-161">**[このルールを適用する条件]** で、 **[差出人]** を選択してから、 **[IP アドレスがこれらの範囲内か完全に一致している]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-161">Under **Apply this rule if**, select **The sender** and then choose **IP address is in any of these ranges or exactly matches**.</span></span>
    
5. <span data-ttu-id="0d7b2-162">**[IP アドレスを指定する]** で、IP アドレス範囲を指定して、 **[追加]**![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックしてから、 **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-162">In the **specify IP addresses**, specify the IP address range, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then click **ok**.</span></span>
    
6. <span data-ttu-id="0d7b2-p113">**[実行する処理]** ボックスで、 **[メッセージのプロパティを変更する]** の次に **[SCL (Spam Confidence Level) の設定]** を選択することによって、処理を設定します。 **[SCL の指定]** ボックスで、 **[スパム対策フィルターをバイパスする]** を選択してから、 **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p113">Under **Do the following** box, set the action by choosing **Modify the message properties** and then **set the spam confidence level (SCL)**. In the **specify SCL** box, select **Bypass spam filtering**, and click **ok**.</span></span>
    
7. <span data-ttu-id="0d7b2-p114">これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。ルールを施行する前に一定期間ルールをテストすることをお勧めします。[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) にこれらの選択肢に関する詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p114">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period before you enforce it. [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) contains more information about these selections.</span></span> 
    
8. <span data-ttu-id="0d7b2-p115">**[保存]** ボタンをクリックしてルールを保存します。保存されたルールはルールの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p115">Click the **save** button to save the rule. It appears in your list of rules.</span></span> 
    
<span data-ttu-id="0d7b2-170">ルールを作成して適用したら、指定した IP アドレス範囲に対してスパム フィルター処理が省略されます。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-170">After you create and enforce the rule, spam filtering is bypassed for the IP address range you specified.</span></span>
  
### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a><span data-ttu-id="0d7b2-171">特定のドメインに関する IP 許可一覧例外の範囲指定</span><span class="sxs-lookup"><span data-stu-id="0d7b2-171">Scoping an IP Allow list exception for a specific domain</span></span>

<span data-ttu-id="0d7b2-p116">一般に、安全だと思われるドメインの IP アドレス (または IP アドレス範囲) をすべて IP 許可一覧に追加することをお勧めします。ただし、IP 許可一覧のエントリをすべてのドメインに適用しない場合は、特定のドメインを除外するトランスポート ルールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p116">In general, we recommend that you add the IP addresses (or IP address ranges) for all your domains that you consider safe to the IP Allow list. However, if you don't want your IP Allow List entry to apply to all your domains, you can create a Transport rule that excepts specific domains.</span></span> 
  
<span data-ttu-id="0d7b2-p117">たとえば、ContosoA.com、ContosoB.com、および ContosoC.com という 3 つのドメインがあり、IP アドレス (簡単にするために、1.2.3.4 を使用する) を追加して、ContosoB.com ドメインのフィルター処理だけを省略することにしましょう。すべてのドメインの Spam Confidence Level (SCL) を -1 に設定する (非スパムに分類されることを意味する) 1.2.3.4 用の IP 許可一覧を作成します。その後、ContosoB.com 以外のすべてのドメインについて SCL を 0 に設定するトランスポート ルールを作成できます。これにより、ルールの適用外のドメインに指定されている ContosoB.com を除く IP アドレスに対応するすべてのドメインについてメッセージが再スキャンされます。ContosoB.com の SCL はフィルター処理をスキップする -1 のままであるのに対して、ContosoA.com と ContosoC.com の SCL はコンテンツ フィルターによって再スキャンされる 0 です。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p117">For example, let's say you have three domains: ContosoA.com, ContosoB.com, and ContosoC.com, and you want to add the IP address (for simplicity's sake, let's use 1.2.3.4) and skip filtering only for domain ContosoB.com. You would create an IP Allow list for 1.2.3.4, which sets the spam confidence level (SCL) to -1 (meaning it is classified as non-spam) for all domains. You can then create a Transport rule that sets the SCL for all domains except ContosoB.com to 0. This results in the message being rescanned for all domains associated with the IP address except for ContosoB.com which is the domain listed as the exception in the rule. ContosoB.com still has an SCL of -1 which means skip filtering, whereas ContosoA.com and ContosoC.com have SCLs of 0, meaning they will be rescanned by the content filter.</span></span>
  
<span data-ttu-id="0d7b2-179">これを実現するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-179">To do this, perform the following steps:</span></span>
  
1. <span data-ttu-id="0d7b2-180">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-180">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="0d7b2-181">![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックしてから、 **[新しいルールを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-181">Click ![Add Icon](media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="0d7b2-182">ルールに名前を付けてから、 **[その他のオプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-182">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="0d7b2-183">**[このルールを適用する条件]** で、 **[差出人]** を選択してから、 **[IP アドレスがこれらの範囲内か完全に一致している]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-183">Under **Apply this rule if**, select **The sender** and then choose **IP address is in any of these ranges or exactly matches**.</span></span>
    
5. <span data-ttu-id="0d7b2-184">**[IP アドレスを指定する]** ボックスで、IP 許可一覧に入力した IP アドレスまたは IP アドレス範囲を指定して、 **[追加]**![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックしてから、 **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-184">In the **specify IP addresses** box, specify the IP address or IP address range you entered in the IP Allow list, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then click **ok**.</span></span>
    
6. <span data-ttu-id="0d7b2-p118">**[実行する処理]** で、 **[メッセージのプロパティを変更する]** の次に **[SCL (Spam Confidence Level) の設定]** を選択することによって、処理を設定します。 **[SCL の指定]** ボックスで、 **[0]** を選択してから、 **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p118">Under **Do the following**, set the action by choosing **Modify the message properties** and then **set the spam confidence level (SCL)**. In the **specify SCL** box, select **0**, and click **ok**.</span></span>
    
7. <span data-ttu-id="0d7b2-187">**[例外の追加]** をクリックして、 **[ただし次の場合を除く]** で、 **[差出人]** を選択し、 **[ドメイン名]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-187">Click **add exception**, and under **Except if**, select **The sender** and choose **domain is**.</span></span> 
    
8. <span data-ttu-id="0d7b2-p119">**[ドメインの指定]** ボックスで、 **contoso.com** のように、スパム フィルター処理を省略するドメインを入力します。 **[追加]**![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックして、そのドメインを語句の一覧に移動します。その他のドメインを例外として追加する場合はこの手順を繰り返し、完了したら、 **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p119">In the **specify domain** box, enter the domain for which you want to bypass spam filtering, such as **contosob.com**. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png) to move it to the list of phrases. Repeat this step if you want to add additional domains as exceptions, and click **ok** when you are finished.</span></span> 
    
9. <span data-ttu-id="0d7b2-p120">これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。ルールを施行する前に一定期間ルールをテストすることをお勧めします。[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) にこれらの選択肢に関する詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p120">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period before you enforce it. [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) contains more information about these selections.</span></span> 
    
10. <span data-ttu-id="0d7b2-p121">**[保存]** ボタンをクリックしてルールを保存します。保存されたルールはルールの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p121">Click the **save** button to save the rule. It appears in your list of rules.</span></span> 
    
<span data-ttu-id="0d7b2-196">ルールを作成して適用すると、指定した IP アドレスまたは IP アドレス範囲に対するスパム フィルター処理が入力したドメイン例外の場合にのみ省略されます。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-196">After you create and enforce the rule, spam filtering for the IP address or IP address range you specified is bypassed only for the domain exception you entered.</span></span>
  
## <a name="new-to-office-365"></a><span data-ttu-id="0d7b2-197">Office 365 を初めて使用する場合</span><span class="sxs-lookup"><span data-stu-id="0d7b2-197">New to Office 365?</span></span>
<span data-ttu-id="0d7b2-198"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="0d7b2-198"></span></span>

||
|:-----|
|<span data-ttu-id="0d7b2-p122">![LinkedIn Learning の小さいアイコン](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Office 365 を初めて使用する場合は、**         LinkedIn Learning が提供する **Office 365 admins and IT pros** のための無料のビデオ コースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0d7b2-p122">![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span> |
   
## <a name="for-more-information"></a><span data-ttu-id="0d7b2-201">詳細情報</span><span class="sxs-lookup"><span data-stu-id="0d7b2-201">For more information</span></span>
<span data-ttu-id="0d7b2-202"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="0d7b2-202"></span></span>

[<span data-ttu-id="0d7b2-203">Exchange Online の差出人セーフ リストと受信拒否リスト</span><span class="sxs-lookup"><span data-stu-id="0d7b2-203">Safe sender and blocked sender lists in Exchange Online</span></span>](safe-sender-and-blocked-sender-lists-faq.md)
  
[<span data-ttu-id="0d7b2-204">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="0d7b2-204">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="0d7b2-205">送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="0d7b2-205">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="0d7b2-206">メッセージがスパムとしてマークされないようにする方法</span><span class="sxs-lookup"><span data-stu-id="0d7b2-206">How to help ensure that a message isn't marked as spam</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[<span data-ttu-id="0d7b2-207">検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする</span><span class="sxs-lookup"><span data-stu-id="0d7b2-207">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

