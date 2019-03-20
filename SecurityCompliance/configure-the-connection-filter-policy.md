---
title: 接続フィルター ポリシーを構成する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
description: 信頼できるユーザーからの電子メールがブロックされないようにするには、接続フィルターポリシーを使用して、信頼する IP アドレスの許可リスト (安全な差出人のリストとも呼ばれます) を作成します。 受信拒否リストを作成することもできます。
ms.openlocfilehash: 5ca6ad6721ac03e5ae62b40dda219671bde3e1c1
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693546"
---
# <a name="configure-the-connection-filter-policy"></a><span data-ttu-id="96da4-104">接続フィルター ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="96da4-104">Configure the connection filter policy</span></span>
 
<span data-ttu-id="96da4-p102">ほとんどの人は友人やビジネス パートナーを信頼しています。信頼する人からの電子メールが迷惑メール フォルダーに入っていたり、スパム フィルターによって完全にブロックされたりすると、もどかしさを感じます。そのようなメールがブロックされないようにするには、接続フィルター ポリシーを利用して許可リスト (「差出人セーフ リスト」ともいう) を作成し、信頼する IP アドレスを登録することができます。また、受信拒否リストを作成して既知のスパム メール送信者の IP アドレスを登録し、そのような送信者からの電子メール メッセージを受信しないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="96da4-p102">Most of us have friends and business partners we trust. It can be frustrating to find email from them in your junk email folder, or even blocked entirely by a spam filter. If you want to make sure that email sent from people you trust isn't blocked, you can use the connection filter policy to create an Allow list, also known as a safe sender list, of IP addresses that you trust. You can also create a blocked senders list, which is a list of IP addresses, typically from known spammers, that you don't ever want to receive email messages from.</span></span>
  
 <span data-ttu-id="96da4-p103">組織全体に適用されるスパム設定の詳細については、「 [EOP と Office 365 でメールが迷惑メールとして検出されないようにする](https://go.microsoft.com/fwlink/p/?LinkId=534224)」または「[Office 365 のスパム フィルターでスパムや迷惑メールをブロックして、検出漏れ問題を防止する](https://go.microsoft.com/fwlink/p/?LinkId=534225)」を参照してください。これらは、管理者レベルの制御権限を持っている場合にスパムの誤検知や検出漏れを防ぐ上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96da4-p103">For more spam settings that apply to the whole organization, take a look at [How to help ensure that a message isn't marked as spam](https://go.microsoft.com/fwlink/p/?LinkId=534224) or [Block email spam with the Office 365 spam filter to prevent false negative issues](https://go.microsoft.com/fwlink/p/?LinkId=534225). These are helpful if you have administrator-level control and you want to prevent false positives or false negatives.</span></span>
  
<span data-ttu-id="96da4-111">次のビデオでは、接続フィルター ポリシーの構成手順を示します。</span><span class="sxs-lookup"><span data-stu-id="96da4-111">The following video shows the configuration steps for the connection filter policy:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="96da4-112">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="96da4-112">What do you need to know before you begin?</span></span>
<span data-ttu-id="96da4-113"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="96da4-113"></span></span>

- <span data-ttu-id="96da4-114">予想所要時間 : 15 分</span><span class="sxs-lookup"><span data-stu-id="96da4-114">Estimated time to complete: 15 minutes</span></span>
    
- <span data-ttu-id="96da4-115">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="96da4-115">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="96da4-116">必要なアクセス許可を確認するには、「 [Exchange Online の機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)」トピックの「スパム対策」のエントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96da4-116">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
    
- <span data-ttu-id="96da4-117">許可またはブロックする送信者の IP アドレスを取得するには、メッセージのインターネット ヘッダーを確認するという方法があります。</span><span class="sxs-lookup"><span data-stu-id="96da4-117">To obtain the IP address of the sender whose messages you want to allow or block, you can check the Internet header of the message.</span></span> <span data-ttu-id="96da4-118">「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」で説明されているように、CIP ヘッダーを調べます。</span><span class="sxs-lookup"><span data-stu-id="96da4-118">Look for the CIP header as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="96da4-119">さまざまな電子メールクライアントでメッセージヘッダーを表示する方法については、「[メッセージヘッダーアナライザー](https://go.microsoft.com/fwlink/p/?LinkId=306583)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96da4-119">For information about how to view a message header in various email clients, see [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583).</span></span> 
    
- <span data-ttu-id="96da4-120">IP ブロック一覧の IP アドレスから送信された電子メール メッセージは拒否され、スパムとしてマークされず、追加のフィルター処理は行われません。</span><span class="sxs-lookup"><span data-stu-id="96da4-120">Email messages sent from an IP address on the IP Block list are rejected, not marked as spam, and no additional filtering occurs.</span></span>
    
- <span data-ttu-id="96da4-121">以下の接続フィルター手順はリモート PowerShell 経由でも実行することができます。Get-HostedConnectionFilterPolicy コマンドレットを使用して設定を確認し、 Set-HostedConnectionFilterPolicy を使用して接続フィルター ポリシー設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="96da4-121">The following connection filter procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="96da4-122">[Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) コマンドレットを使用して設定を確認し、[Set-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) を使用して接続フィルター ポリシー設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="96da4-122">Use the [Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) cmdlet to review your settings, and the [Set-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) to edit your connection filter policy settings.</span></span> <span data-ttu-id="96da4-123">Windows PowerShell を使って Exchange Online Protection に接続する方法については、「[Exchange Online Protection の PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=627290)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96da4-123">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span> <span data-ttu-id="96da4-124">Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96da4-124">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a><span data-ttu-id="96da4-125">EAC を使用して既定の接続フィルター ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="96da4-125">Use the EAC to edit the default connection filter policy</span></span>
<span data-ttu-id="96da4-126"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="96da4-126"></span></span>

<span data-ttu-id="96da4-p107">IP 許可リストまたは IP 禁止リストを作成するには、Exchange 管理センター (EAC) で接続フィルター ポリシーを編集します。接続フィルター ポリシーの設定は、受信メッセージのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="96da4-p107">You create an IP Allow list or IP Block list by editing the connection filter policy in the Exchange admin center (EAC). The connection filter policy settings are applied to inbound messages only.</span></span>
  
1. <span data-ttu-id="96da4-129">Exchange 管理センター (EAC) で、 **[保護]** \> **[接続フィルター]** に移動し、既定のポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="96da4-129">In the Exchange admin center (EAC), navigate to **Protection** \> **Connection filter**, and then double-click the default policy.</span></span>
    
2. <span data-ttu-id="96da4-130">**[接続フィルター]** メニュー項目をクリックし、IP 許可一覧、IP 禁止一覧、あるいはその両方のうち、必要な一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="96da4-130">Click the **Connection filtering** menu item and then create the lists you want: an IP Allow list, an IP Block list, or both.</span></span> 
    
    <span data-ttu-id="96da4-p108">この一覧を作成するには、![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックします。後続のダイアログ ボックスでは、IP アドレスまたはアドレス範囲を指定して **[OK]** をクリックします。さらにアドレスを追加するには、このプロセスを繰り返します。(IP アドレスは、追加後に編集または削除できます。)</span><span class="sxs-lookup"><span data-stu-id="96da4-p108">To create these lists, click ![Add Icon](media/ITPro-EAC-AddIcon.gif). In the subsequent dialog box, specify the IP address or address range, and then click **ok**. Repeat this process to add additional addresses. (You can also edit or remove IP addresses after they have been added.)</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="96da4-135">両方のリストに ip アドレスを追加すると、その ip アドレスから送信された電子メールが許可されます。</span><span class="sxs-lookup"><span data-stu-id="96da4-135">If you add an IP address to both lists, email sent from that IP address is allowed.</span></span> 

    <span data-ttu-id="96da4-136">形式を nnn. nnn にする場合は、IPV4 IP アドレスを指定します。 nnn には0から255の数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="96da4-136">Specify IPV4 IP addresses in the format nnn.nnn.nnn.nnn where nnn is a number from 0 to 255.</span></span> <span data-ttu-id="96da4-137">クラスレス ドメイン間ルーティング (CIDR) の範囲を nnn.nnn.nnn.nnn/rr (rr は 24 から 32 までの数値) の形式で指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="96da4-137">You can also specify Classless Inter-Domain Routing (CIDR) ranges in the format nnn.nnn.nnn.nnn/rr where rr is a number from 24 to 32.</span></span> <span data-ttu-id="96da4-138">24 ~ 32 の範囲外の範囲を指定するには、 [IP 許可一覧を構成するときの追加の考慮事項](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96da4-138">To specify ranges outside of the 24 to 32 range, see [Additional considerations when configuring IP Allow lists](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists).</span></span> 

    <span data-ttu-id="96da4-139">最大 1273 のエントリを指定できます。各エントリは、単一の IP アドレス、または IP アドレスの CIDR 範囲 (/24 から /32 まで) にすることができます。</span><span class="sxs-lookup"><span data-stu-id="96da4-139">You can specify a maximum of 1273 entries, where an entry is either a single IP address or a CIDR range of IP addresses from /24 to /32.</span></span> <span data-ttu-id="96da4-140">> TLS で暗号化されたメッセージを送信している場合、IPv6 アドレスとアドレス範囲はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="96da4-140">>  If you're sending TLS-encrypted messages, IPv6 addresses and address ranges are not supported.</span></span> 
  
3. <span data-ttu-id="96da4-141">必要に応じて、[**セーフリストを有効**にする] チェックボックスをオンにして、特定の既知の送信者からの電子メールが失われないようにします。</span><span class="sxs-lookup"><span data-stu-id="96da4-141">Optionally, select the **Enable safe list** check box to prevent missing email from certain well-known senders.</span></span> <span data-ttu-id="96da4-142">どう。</span><span class="sxs-lookup"><span data-stu-id="96da4-142">How?</span></span> <span data-ttu-id="96da4-143">Microsoft は、信頼できる送信者のサードパーティソースにサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="96da4-143">Microsoft subscribes to third-party sources of trusted senders.</span></span> <span data-ttu-id="96da4-144">このセーフリストを使用することは、これらの信頼できる差出人が誤ってスパムとしてマークされていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="96da4-144">Using this safe list means that these trusted senders aren't mistakenly marked as spam.</span></span> <span data-ttu-id="96da4-145">受信する誤検知 (良好なメールに分類されているメール) の数を減らす必要があるため、このオプションを選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="96da4-145">We recommend selecting this option because it should reduce the number of false positives (good mail that's classified as spam) that you receive.</span></span> 
    
4. <span data-ttu-id="96da4-p112">**[保存]** をクリックします。既定のポリシー設定の概要が右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="96da4-p112">Click **save**. A summary of your default policy settings appears in the right pane.</span></span>
    
## <a name="additional-considerations-when-configuring-ip-allow-lists"></a><span data-ttu-id="96da4-148">IP 許可一覧を構成する場合のその他の留意点</span><span class="sxs-lookup"><span data-stu-id="96da4-148">Additional considerations when configuring IP Allow lists</span></span>
<span data-ttu-id="96da4-149"><a name="bkmk_addtionalconsiderationswhenconfiguringipallowlists"> </a></span><span class="sxs-lookup"><span data-stu-id="96da4-149"></span></span>

<span data-ttu-id="96da4-150">IP 許可一覧を構成する場合に考慮するまたは認識すべきその他の留意点を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="96da4-150">The following are additional considerations you may want to consider or that you should be aware of when configuring an IP Allow list.</span></span>
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a><span data-ttu-id="96da4-151">推奨範囲外の CIDR 範囲の指定</span><span class="sxs-lookup"><span data-stu-id="96da4-151">Specifying a CIDR range that falls outside of the recommended range</span></span>

<span data-ttu-id="96da4-152">/1 から/23 の CIDR ip アドレス範囲を指定するには、スパムの信頼レベル (SCL) を設定するメールフロールールを作成する必要があります。これは、スパムの**フィルター処理をバイパス**する (つまり、この ip アドレス範囲内で受信するすべてのメッセージが[迷惑メールではない] に設定し、サービスによって追加のフィルター処理は実行されません)。</span><span class="sxs-lookup"><span data-stu-id="96da4-152">To specify a CIDR IP address range from /1 to /23, you must create a mail flow rule that operates on the IP address range that sets the spam confidence level (SCL) to **Bypass spam filtering** (meaning that all messages received from within this IP address range are set to "not spam") and no additional filtering is performed by the service).</span></span> <span data-ttu-id="96da4-153">ただし、これらの IP アドレスのいずれかが Microsoft の独自のブロックリストまたはサードパーティのブロックリストのいずれかに表示される場合でも、これらのメッセージはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="96da4-153">However, if any of these IP addresses appear on any of Microsoft's proprietary block lists or on any of our third-party block lists, these messages will still be blocked.</span></span> <span data-ttu-id="96da4-154">そのため、/24 ~ 32 IP アドレス範囲を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="96da4-154">It is therefore strongly recommended that you use the /24 to /32 IP address range.</span></span> 
  
<span data-ttu-id="96da4-155">このメールフロールールを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="96da4-155">To create this mail flow rule, perform the following steps.</span></span>
  
1. <span data-ttu-id="96da4-156">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="96da4-156">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="96da4-157">![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96da4-157">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="96da4-158">ルールに名前を付けてから、 **[その他のオプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96da4-158">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="96da4-159">**[このルールを適用する条件]** で、 **[差出人]** を選択してから、 **[IP アドレスがこれらの範囲内か完全に一致している]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96da4-159">Under **Apply this rule if**, select **The sender** and then choose **IP address is in any of these ranges or exactly matches**.</span></span>
    
5. <span data-ttu-id="96da4-160">[ **ip アドレスの指定**] で、ip アドレスの範囲を\*\*\*\* ![指定し、](media/ITPro-EAC-AddIcon.gif)[追加] アイコンをクリックして、[ **ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96da4-160">In the **specify IP addresses**, specify the IP address range, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then click **ok**.</span></span>
    
6. <span data-ttu-id="96da4-p114">**[実行する処理]** ボックスで、 **[メッセージのプロパティを変更する]** の次に **[SCL (Spam Confidence Level) の設定]** を選択することによって、処理を設定します。 **[SCL の指定]** ボックスで、 **[スパム対策フィルターをバイパスする]** を選択してから、 **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96da4-p114">Under **Do the following** box, set the action by choosing **Modify the message properties** and then **set the spam confidence level (SCL)**. In the **specify SCL** box, select **Bypass spam filtering**, and click **ok**.</span></span>
    
7. <span data-ttu-id="96da4-163">これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。</span><span class="sxs-lookup"><span data-stu-id="96da4-163">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="96da4-164">ルールを施行する前に一定期間ルールをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="96da4-164">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="96da4-165">[Exchange Server のメールフロールールの手順には](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)、これらの選択についての詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="96da4-165">[Procedures for mail flow rules in Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) contains more information about these selections.</span></span> 
    
8. <span data-ttu-id="96da4-166">[**保存**] をクリックしてルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="96da4-166">Click **save** to save the rule.</span></span> <span data-ttu-id="96da4-167">ルールがルールの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="96da4-167">The rule appears in your list of rules.</span></span> 
    
<span data-ttu-id="96da4-168">ルールを作成して適用すると、サービスは指定した IP アドレス範囲のスパムフィルター処理をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="96da4-168">After you create and enforce the rule, the service bypasses spam filtering for the IP address range you specified.</span></span>
  
### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a><span data-ttu-id="96da4-169">特定のドメインに関する IP 許可一覧例外の範囲指定</span><span class="sxs-lookup"><span data-stu-id="96da4-169">Scoping an IP Allow list exception for a specific domain</span></span>

<span data-ttu-id="96da4-170">一般に、安全だと思われるドメインの IP アドレス (または IP アドレス範囲) をすべて IP 許可一覧に追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="96da4-170">In general, we recommend that you add the IP addresses (or IP address ranges) for all your domains that you consider safe to the IP Allow list.</span></span> <span data-ttu-id="96da4-171">ただし、IP 許可一覧のエントリをすべてのドメインに適用しない場合は、特定のドメインを除外するメールフロールール (トランスポートルールとも呼ばれます) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="96da4-171">However, if you don't want your IP Allow List entry to apply to all your domains, you can create a mail flow rule (also known as a transport rule) that excepts specific domains.</span></span> 
  
<span data-ttu-id="96da4-172">たとえば、ContosoA.com、ContosoB.com、および ContosoC.com という 3 つのドメインがあり、IP アドレス (簡単にするために、1.2.3.4 を使用する) を追加して、ContosoB.com ドメインのフィルター処理だけを省略することにしましょう。</span><span class="sxs-lookup"><span data-stu-id="96da4-172">For example, let's say you have three domains: ContosoA.com, ContosoB.com, and ContosoC.com, and you want to add the IP address (for simplicity's sake, let's use 1.2.3.4) and skip filtering only for domain ContosoB.com.</span></span> <span data-ttu-id="96da4-173">すべてのドメインの Spam Confidence Level (SCL) を -1 に設定する (非スパムに分類されることを意味する) 1.2.3.4 用の IP 許可一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="96da4-173">You would create an IP Allow list for 1.2.3.4, which sets the spam confidence level (SCL) to -1 (meaning it is classified as non-spam) for all domains.</span></span> <span data-ttu-id="96da4-174">その後、ContosoB.com 以外のすべてのドメインの SCL を0に設定するメールフロールールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="96da4-174">You can then create a mail flow rule that sets the SCL for all domains except ContosoB.com to 0.</span></span> <span data-ttu-id="96da4-175">これにより、ルールの適用外のドメインに指定されている ContosoB.com を除く IP アドレスに対応するすべてのドメインについてメッセージが再スキャンされます。</span><span class="sxs-lookup"><span data-stu-id="96da4-175">This results in the message being rescanned for all domains associated with the IP address except for ContosoB.com which is the domain listed as the exception in the rule.</span></span> <span data-ttu-id="96da4-176">ContosoB.com の SCL はフィルター処理をスキップする -1 のままであるのに対して、ContosoA.com と ContosoC.com の SCL はコンテンツ フィルターによって再スキャンされる 0 です。</span><span class="sxs-lookup"><span data-stu-id="96da4-176">ContosoB.com still has an SCL of -1 which means skip filtering, whereas ContosoA.com and ContosoC.com have SCLs of 0, meaning they will be rescanned by the content filter.</span></span>
  
<span data-ttu-id="96da4-177">これを実現するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="96da4-177">To do this, perform the following steps:</span></span>
  
1. <span data-ttu-id="96da4-178">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="96da4-178">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="96da4-179">![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96da4-179">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="96da4-180">ルールに名前を付けてから、 **[その他のオプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96da4-180">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="96da4-181">**[このルールを適用する条件]** で、 **[差出人]** を選択してから、 **[IP アドレスがこれらの範囲内か完全に一致している]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96da4-181">Under **Apply this rule if**, select **The sender** and then choose **IP address is in any of these ranges or exactly matches**.</span></span>
    
5. <span data-ttu-id="96da4-182">[ip**アドレスの指定**] ボックスで、ip 許可一覧\*\*\*\* ![に入力した ip アドレスまたは ip アドレスの範囲を指定し](media/ITPro-EAC-AddIcon.gif)、[追加] アイコンをクリックし、[ **ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96da4-182">In the **specify IP addresses** box, specify the IP address or IP address range you entered in the IP Allow list, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then click **ok**.</span></span>
    
6. <span data-ttu-id="96da4-p119">**[実行する処理]** で、 **[メッセージのプロパティを変更する]** の次に **[SCL (Spam Confidence Level) の設定]** を選択することによって、処理を設定します。 **[SCL の指定]** ボックスで、 **[0]** を選択してから、 **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96da4-p119">Under **Do the following**, set the action by choosing **Modify the message properties** and then **set the spam confidence level (SCL)**. In the **specify SCL** box, select **0**, and click **ok**.</span></span>
    
7. <span data-ttu-id="96da4-185">**[例外の追加]** をクリックして、 **[ただし次の場合を除く]** で、 **[差出人]** を選択し、 **[ドメイン名]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96da4-185">Click **add exception**, and under **Except if**, select **The sender** and choose **domain is**.</span></span> 
    
8. <span data-ttu-id="96da4-186">**[ドメインの指定]** ボックスで、 **contoso.com** のように、スパム フィルター処理を省略するドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="96da4-186">In the **specify domain** box, enter the domain for which you want to bypass spam filtering, such as **contosob.com**.</span></span> <span data-ttu-id="96da4-187">[追加] アイコン](media/ITPro-EAC-AddIcon.gif)をクリックして、それを語句の一覧に移動します。 \*\*\*\* ![</span><span class="sxs-lookup"><span data-stu-id="96da4-187">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) to move it to the list of phrases.</span></span> <span data-ttu-id="96da4-188">その他のドメインを例外として追加する場合はこの手順を繰り返し、完了したら、 **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96da4-188">Repeat this step if you want to add additional domains as exceptions, and click **ok** when you are finished.</span></span> 
    
9. <span data-ttu-id="96da4-189">これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。</span><span class="sxs-lookup"><span data-stu-id="96da4-189">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="96da4-190">ルールを施行する前に一定期間ルールをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="96da4-190">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="96da4-191">[Exchange Server のメールフロールールの手順には](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)、これらの選択についての詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="96da4-191">[Procedures for mail flow rules in Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) contains more information about these selections.</span></span> 
    
10. <span data-ttu-id="96da4-192">[**保存**] をクリックしてルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="96da4-192">Click **save** to save the rule.</span></span> <span data-ttu-id="96da4-193">ルールがルールの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="96da4-193">The rule appears in your list of rules.</span></span> 
    
<span data-ttu-id="96da4-194">ルールを作成して適用すると、指定した IP アドレスまたは IP アドレス範囲に対するスパム フィルター処理が入力したドメイン例外の場合にのみ省略されます。</span><span class="sxs-lookup"><span data-stu-id="96da4-194">After you create and enforce the rule, spam filtering for the IP address or IP address range you specified is bypassed only for the domain exception you entered.</span></span>
  
## <a name="new-to-office-365"></a><span data-ttu-id="96da4-195">Office 365 を初めて使用する場合</span><span class="sxs-lookup"><span data-stu-id="96da4-195">New to Office 365?</span></span>
<span data-ttu-id="96da4-196"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="96da4-196"></span></span>

||
|:-----|
|<span data-ttu-id="96da4-p123">![LinkedIn Learning の小さいアイコン](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Office 365 を初めて使用する場合は、**         LinkedIn Learning が提供する **Office 365 admins and IT pros** のための無料のビデオ コースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="96da4-p123">![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span> |
   
## <a name="for-more-information"></a><span data-ttu-id="96da4-199">関連情報</span><span class="sxs-lookup"><span data-stu-id="96da4-199">For more information</span></span>
<span data-ttu-id="96da4-200"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="96da4-200"></span></span>

[<span data-ttu-id="96da4-201">Exchange Online の差出人セーフ リストと受信拒否リスト</span><span class="sxs-lookup"><span data-stu-id="96da4-201">Safe sender and blocked sender lists in Exchange Online</span></span>](safe-sender-and-blocked-sender-lists-faq.md)
  
[<span data-ttu-id="96da4-202">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="96da4-202">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="96da4-203">送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="96da4-203">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="96da4-204">メッセージがスパムとしてマークされないようにする方法</span><span class="sxs-lookup"><span data-stu-id="96da4-204">How to help ensure that a message isn't marked as spam</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[<span data-ttu-id="96da4-205">検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする</span><span class="sxs-lookup"><span data-stu-id="96da4-205">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

