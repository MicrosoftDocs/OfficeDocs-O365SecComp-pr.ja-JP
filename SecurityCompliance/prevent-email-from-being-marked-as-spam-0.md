---
title: 電子メールが Office 365 と Exchange のオンライン保護で迷惑メールとして扱われることを防ぐ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 74aaade0-efc0-46ac-b949-f2d1d59256fa
description: 適切な電子メールを防ぐために、Office 365 管理者のためのヒントは、偽陽性として検疫に送信されてからの迷惑メールとしてマークされます。セーフリストと適切な電子メールがスパムとしてマークされているを防ぐために他のオプションをカスタマイズします。
ms.openlocfilehash: 42b27d237592e95e6d175ab335959bc82269c0f7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531635"
---
# <a name="prevent-email-from-being-marked-as-spam-in-office-365-and-exchange-online-protection"></a><span data-ttu-id="8be55-104">電子メールが Office 365 と Exchange のオンライン保護で迷惑メールとして扱われることを防ぐ</span><span class="sxs-lookup"><span data-stu-id="8be55-104">Prevent email from being marked as spam in Office 365 and Exchange Online Protection</span></span>

<span data-ttu-id="8be55-105">適切なアクセス資格情報を持つ Exchange Online または Exchange オンライン保護 (EOP) の管理者は、出張サービスから電子メール メッセージがスパムとしてマークされたされていないことを確実に次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8be55-105">Exchange Online or Exchange Online Protection (EOP) administrators with the appropriate access credentials can use these steps to help ensure that an email message traveling through the service isn't marked as spam.</span></span>
  
<span data-ttu-id="8be55-p102">隔離または検疫用フォルダーでの着陸にスパムをブロックを正当なメールにイライラができます。スパム フィルターをバイパスして、適切な電子メール メッセージが迷惑メールとしてマークするを防ぐには、[差出人セーフ リスト] ボックスの一覧またはメール フロー ルールを使用できます。メッセージが正しくないスパムとしてマークされた迷惑メール フィルターによって、誤検知が呼び出されます。Office 365 の迷惑メール フィルターでは、エンド ・ ユーザーは、誤検出を防止するためにカスタマイズが可能ないくつかのオプションも提供します。</span><span class="sxs-lookup"><span data-stu-id="8be55-p102">It can be frustrating to have legitimate, good email quarantined or blocked as spam and landing in a quarantine folder. You can use a safe sender list or a mail flow rule to bypass spam filtering and prevent good email messages from getting marked as junk mail. When a message is incorrectly marked as spam by the spam filter, it's called a false positive. The Office 365 spam filter also provides some options that end users can customize in order to help prevent false positives.</span></span>
  
<span data-ttu-id="8be55-110">メールでは false 負の値、ヘルプを探している場合は、スパム メッセージを取得べきではない、[偽の負の問題を防ぐために Office 365 のスパム フィルターを使用してスパム電子メールのブロック](block-email-spam-to-prevent-false-negatives.md)内のヒントをチェックすることとします。</span><span class="sxs-lookup"><span data-stu-id="8be55-110">If you're looking for help with false negative mail, that is, a spam message that gets through when it shouldn't, check out the tips in [Block email spam with the Office 365 spam filter to prevent false negative issues](block-email-spam-to-prevent-false-negatives.md).</span></span>
  
## <a name="eop-only-customers-use-directory-synchronization"></a><span data-ttu-id="8be55-111">EOP 専用のお客様: ディレクトリ同期を使用します。</span><span class="sxs-lookup"><span data-stu-id="8be55-111">EOP-only customers: use directory synchronization</span></span>

<span data-ttu-id="8be55-p103">EOP は、スパムやマルウェアから組織を保護するのに役立つサービスをフィルタ リングするクラウド ベースの電子メールです。Office 365 のメールボックスがある場合に自動的にによって保護されている EOP サービスの一部であるためです。</span><span class="sxs-lookup"><span data-stu-id="8be55-p103">EOP is a cloud-based email filtering service that helps protect your organization against spam and malware. If you have mailboxes in Office 365, they are automatically protected by EOP since it is part of the service.</span></span> 
  
<span data-ttu-id="8be55-p104">EOP 専用の顧客の場合、つまり、オンプレミスの Exchange Server で使用の EOP サービスに登録する、ディレクトリ同期を使用するサービスとユーザー設定を同期する必要があります。これにより、差出人セーフ リストが EOP を尊重します。詳細については、 [EOP のメール ユーザーの管理](https://go.microsoft.com/fwlink/?LinkId=534098)で「メール ユーザーを管理するためにディレクトリ同期を使用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8be55-p104">If you're an EOP-only customer, that is, you subscribe to the EOP service for use with your on-premises Exchange Server, you should sync user settings with the service by using directory synchronization. Doing this ensures that your safe senders lists are respected by EOP. For more information, see "Use directory synchronization to manage mail users" in [Manage Mail Users in EOP](https://go.microsoft.com/fwlink/?LinkId=534098).</span></span>
  
## <a name="prevent-false-positive-email-by-using-the-connection-filters-ip-allow-list"></a><span data-ttu-id="8be55-117">正偽の電子メールを防ぐフィルターの IP 接続を使用してリストを許可します。</span><span class="sxs-lookup"><span data-stu-id="8be55-117">Prevent false positive email by using the connection filter's IP allow list</span></span>

<span data-ttu-id="8be55-p105">送信者の電子メールは常に、組織内の迷惑メール フォルダーに移動、メールの送信者の IP アドレスを追加するには、接続フィルターの ip を検索する場合は、リストを使用できます。通常、この送信者を組織内のすべての受信者に偽の肯定応答をできないようにします。ユーザー オプションを有効にする場合は例外です"セーフ リスト] のみ: ユーザーまたはドメインを [差出人セーフ リストまたは宛先セーフ リストからのメールのみを受信トレイに配信されます「Outlook でし、その送信者を差出人セーフ リストに追加されません。このオプションを上書きする方法についてを参照してください[トラブルシューティング: EOP 非スパムとしてメッセージをマークする場合でも [迷惑メール] フォルダー メッセージ終了](prevent-email-from-being-marked-as-spam-0.md#TroubleshootingJunkEOPNonSpam)。</span><span class="sxs-lookup"><span data-stu-id="8be55-p105">If you find that a sender's email is always moved to the Junk folders in your organization, you can add the email sender's IP address to your connection filter's IP allow list. Normally, this prevents false positive responses for this sender for all recipients within your organization. The exception is when a user enables the option "Safe Lists Only: Only mail from people or domains on your Safe Senders list or Safe Recipients List will be delivered to your Inbox" in Outlook and does not add that sender to the Safe Sender List. For information on overriding that option, see [Troubleshooting: A message ends up in the Junk folder even though EOP marked the message as non-spam](prevent-email-from-being-marked-as-spam-0.md#TroubleshootingJunkEOPNonSpam).</span></span>
  
 <span data-ttu-id="8be55-122">**フィルターの IP 許可一覧を接続する IP アドレスを追加するのには**</span><span class="sxs-lookup"><span data-stu-id="8be55-122">**To add an IP address to your connection filter's IP allow list**</span></span>
  
1. <span data-ttu-id="8be55-p106">許可する送信者によって送信されたメッセージからヘッダーを取得します。[メッセージ ヘッダーの分析](https://go.microsoft.com/fwlink/p/?LinkId=306583)で説明するよう、Outlook など、Web 上の Outlook のユーザーのメール クライアントからこれを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8be55-p106">Obtain the header from a message sent by the sender that you want to allow. You can do this from your mail client such as Outlook or Outlook on the Web, as described in [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583).</span></span>
    
2. <span data-ttu-id="8be55-125">CIP タグ X Forefront スパム対策レポートのヘッダーまたは[リモート接続アナライザー](https://testconnectivity.microsoft.com/?tabid=mha)の [**メッセージの分析**] タブを使用して、次の IP アドレスを手動で検索します。</span><span class="sxs-lookup"><span data-stu-id="8be55-125">Manually search for the IP address following the CIP tag in the X-Forefront-Antispam-Report header or by using the **Message Analyzer** tab of the [Remote Connectivity Analyzer](https://testconnectivity.microsoft.com/?tabid=mha).</span></span>
    
3. <span data-ttu-id="8be55-126">追加の ip アドレスに IP アドレス「既定の接続フィルター ポリシーを編集するのには EAC を使用する」の手順に従って、[接続フィルター ポリシー構成](https://go.microsoft.com/fwlink/?LinkId=534132)リストを許可します。</span><span class="sxs-lookup"><span data-stu-id="8be55-126">Add the IP address to the IP allow list by following the steps in "Use the EAC to edit the default connection filter policy" in [Configure the connection filter policy](https://go.microsoft.com/fwlink/?LinkId=534132).</span></span>
    
## <a name="prevent-false-positive-email-by-configuring-spam-filter-policies"></a><span data-ttu-id="8be55-127">正偽の電子メールを防ぐため、スパム フィルター ポリシーを構成することによって</span><span class="sxs-lookup"><span data-stu-id="8be55-127">Prevent false positive email by configuring spam filter policies</span></span>

<span data-ttu-id="8be55-128">[スパム フィルター ポリシーの構成](https://go.microsoft.com/fwlink/?LinkID=534136)の手順を実行して、許可リストにドメインまたは個々 の電子メール アドレスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8be55-128">You can add domains or individual email addresses to an allow list by following the steps in [Configure your spam filter policies](https://go.microsoft.com/fwlink/?LinkID=534136).</span></span>
  
## <a name="review-your-advanced-spam-filter-policies"></a><span data-ttu-id="8be55-129">高度な迷惑メール フィルターのポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="8be55-129">Review your advanced spam filter policies</span></span>

<span data-ttu-id="8be55-p107">ドメイン全体をブロックした場合、スパム フィルター ポリシーで、たとえば、特別な制限があるかどうか、それらが原因で誤検知を確認することを確認します。[スパム フィルター ポリシーを構成](https://go.microsoft.com/fwlink/?LinkId=534136)するにはを参照してくださいし、その他[高度な迷惑メール フィルターのオプション](https://go.microsoft.com/fwlink/?LinkId=534137)が迷惑メールとしてマークするメッセージが発生する可能性がありますを無効にします。</span><span class="sxs-lookup"><span data-stu-id="8be55-p107">If you have special restrictions set up in a spam filter policy, for example, if you have blocked an entire domain, you should review them to check if they may be causing false positives. See [Configure your spam filter policies](https://go.microsoft.com/fwlink/?LinkId=534136), and turn off additional [Advanced spam filtering options](https://go.microsoft.com/fwlink/?LinkId=534137) that might cause messages to be marked as spam.</span></span> 
  
## <a name="help-your-end-users-create-a-safe-sender-list-to-prevent-good-email-from-being-marked-as-spam"></a><span data-ttu-id="8be55-132">な電子メールがスパムとしてマークされていることを防ぐための安全な送信者リストを作成する、エンド ・ ユーザーを支援します。</span><span class="sxs-lookup"><span data-stu-id="8be55-132">Help your end users create a safe sender list to prevent good email from being marked as spam</span></span>
<span data-ttu-id="8be55-133"><a name="BKMK_email-user-help-safelist"> </a></span><span class="sxs-lookup"><span data-stu-id="8be55-133"></span></span>

<span data-ttu-id="8be55-p108">[Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065)または[Outlook Web 上](https://go.microsoft.com/fwlink/p/?LinkId=294862)で安全な送信者リストに信頼できる差出人アドレスを追加するのには、ユーザーに指示します。開始するには、Web 上の Outlook で**の設定**を選択します![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **オプション** \> **ブロックまたは許可する**です。次の図は、何か、[差出人セーフ リスト] ボックスの一覧に追加する例を示します。</span><span class="sxs-lookup"><span data-stu-id="8be55-p108">Tell your users to add addresses from senders that they trust to their safe sender list in [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) or [Outlook on the Web](https://go.microsoft.com/fwlink/p/?LinkId=294862). To get started in Outlook on the Web, choose **Settings**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **Options** \> **Block or allow**. The following diagram shows an example of adding something to a safe sender list.</span></span>
  
![Outlook Web App の [差出人セーフ リストを追加します。](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
<span data-ttu-id="8be55-p109">EOP は、ユーザーの [差出人セーフ リストと受信者がいない安全なドメインを優先します。これは、ドメインを Web 上で Outlook を使用して追加または Outlook に追加するかどうかは関係ありませんし、ディレクトリ同期を使用して同期します。</span><span class="sxs-lookup"><span data-stu-id="8be55-p109">EOP will honor your users' Safe Senders and Recipients, but not Safe Domains. This is true regardless of whether the domain is added through the Outlook on the Web, or added in Outlook and synchronized using Directory Sync.</span></span>
  
## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a><span data-ttu-id="8be55-140">トラブルシューティング: メッセージ最終的に迷惑メール フォルダーに EOP 非スパムとしてメッセージをマークする場合でも</span><span class="sxs-lookup"><span data-stu-id="8be55-140">Troubleshooting: A message ends up in the Junk folder even though EOP marked the message as non-spam</span></span>
<span data-ttu-id="8be55-141"><a name="TroubleshootingJunkEOPNonSpam"> </a></span><span class="sxs-lookup"><span data-stu-id="8be55-141"></span></span>

<span data-ttu-id="8be55-p110">ユーザーに対して有効にする Outlook のオプションがあるかどうかは"セーフ リスト] のみ: ユーザーまたはドメインを [差出人セーフ リストまたは宛先セーフ リストからのメールのみを受信トレイに配信されます」をクリックしすべての電子メールが迷惑メール フォルダーに送信者の送信者、reci に含まれていない限り、pient の差出人セーフ リスト] ボックスの一覧です。これは、EOP 非スパムとしてメッセージをマークするかどうか、またはメッセージを非スパムとしてマークする EOP でルールを設定した場合に関係なく行われます。</span><span class="sxs-lookup"><span data-stu-id="8be55-p110">If your users have the option in Outlook enabled for "Safe Lists Only: Only mail from people or domains on your Safe Senders list or Safe Recipients List will be delivered to your Inbox", then all email will go to the junk folder for a sender unless the sender is on the recipient's Safe Sender list. This will happen regardless of whether EOP marks a message as non-spam, or if you have set up a rule in EOP to mark a message as non-spam.</span></span>
  
<span data-ttu-id="8be55-144">指示に従って、Outlook ユーザーのセーフ リスト] のみのオプションを無効にすることができます[Outlook: 迷惑メールの UI を無効にするポリシー設定とフィルター機能](https://support.microsoft.com/en-us/kb/2180568)です。</span><span class="sxs-lookup"><span data-stu-id="8be55-144">You can disable the Safe Lists Only option for your Outlook users by following the instructions in [Outlook: Policy setting to disable the Junk E-mail UI and filtering mechanism](https://support.microsoft.com/en-us/kb/2180568).</span></span>
  
<span data-ttu-id="8be55-145">Web 上の Outlook でメッセージを表示する場合、メッセージが迷惑メール フォルダーに、送信者が受信者の [差出人セーフ リストにはないためであることを示す黄色の安全性のヒントがあります。</span><span class="sxs-lookup"><span data-stu-id="8be55-145">If you view the message in Outlook on the Web, there will be a yellow safety tip that indicates that the message is in the Junk folder because the sender is not on the recipient's Safe Senders list.</span></span>
  
<span data-ttu-id="8be55-p111">メッセージのヘッダーを見ると、スタンプの SFV:SKN (IP を許可するか、ETR を許可する) または SFV:NSPM (スパム以外) が含まれますが、メッセージがユーザーの迷惑メール フォルダーに配置されます。ありませんメッセージ ヘッダーには、ユーザーが [セーフ リスト] のみ] が有効になっていることを示します。これは、[セーフ リストのみ] オプションを Outlook でユーザーが設定した EOP 設定をオーバーライドするために発生します。</span><span class="sxs-lookup"><span data-stu-id="8be55-p111">If you look at the header of a message, it may include the stamp SFV:SKN (IP Allow or ETR Allow) or SFV:NSPM (non-spam), but the message is still placed in the user's junk folder. There is nothing in the message header that indicates that the user has "Safe Lists Only" enabled. This happens because the "Safe Lists Only" option set by users in Outlook overrides the EOP setting.</span></span> 
  
 <span data-ttu-id="8be55-149">**確認するのにはなぜ安全な送信者からのメッセージがスパムとしてマークされた以外のメッセージのヘッダーがまだ終了ユーザーの迷惑メール フォルダーに**</span><span class="sxs-lookup"><span data-stu-id="8be55-149">**To verify why a message from a safe sender is marked as non-spam in the message header, but still ends up in the user's Junk folder**</span></span>
  
1. <span data-ttu-id="8be55-150">オンライン PowerShell を Exchange に接続する方法については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8be55-150">To learn how to connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span> 
    
2. <span data-ttu-id="8be55-151">ユーザーの迷惑メール構成の設定を表示するのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8be55-151">Run the following command to view the user's junk email configuration settings:</span></span>
    
  ```
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

    <span data-ttu-id="8be55-p112">TrustedListsOnly が True に設定されている場合は、この設定が有効になっていることを意味します。ContactsTrusted を True に設定すると、[差出人セーフ リストと連絡先の両方をユーザーが信頼されるためです。TrustedSendersAndDomains は、ユーザーの [差出人セーフ リストの内容を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8be55-p112">If TrustedListsOnly is set to True, it means that this setting is enabled. If ContactsTrusted is set to True, it means that the user trusts both Contacts and Safe Senders. The TrustedSendersAndDomains lists the contents of the user's Safe Senders list.</span></span>
    
## <a name="still-need-help"></a><span data-ttu-id="8be55-155">ヘルプが必要ですか。</span><span class="sxs-lookup"><span data-stu-id="8be55-155">Still need help?</span></span>
<span data-ttu-id="8be55-156"><a name="TroubleshootingJunkEOPNonSpam"> </a></span><span class="sxs-lookup"><span data-stu-id="8be55-156"></span></span>

<span data-ttu-id="8be55-157">[![Office 365 コミュニティ フォーラムからヘルプを取得する](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)</span><span class="sxs-lookup"><span data-stu-id="8be55-157">[![Get help from the Office 365 community forums](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)</span></span>
  
<span data-ttu-id="8be55-158">[![管理者:サインインしてサービス リクエストを作成する](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)</span><span class="sxs-lookup"><span data-stu-id="8be55-158">[![Admins: Sign in and create a service request](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)</span></span>
  
<span data-ttu-id="8be55-159">[![管理者:サポートの依頼](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)</span><span class="sxs-lookup"><span data-stu-id="8be55-159">[![Admins: Call Support](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8be55-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="8be55-160">See also</span></span>
<span data-ttu-id="8be55-161"><a name="TroubleshootingJunkEOPNonSpam"> </a></span><span class="sxs-lookup"><span data-stu-id="8be55-161"></span></span>

[<span data-ttu-id="8be55-162">迷惑メール フィルターの概要</span><span class="sxs-lookup"><span data-stu-id="8be55-162">Overview of the Junk Email Filter</span></span>](https://support.office.com/article/5AE3EA8E-CF41-4FA0-B02A-3B96E21DE089)
  
[<span data-ttu-id="8be55-163">ブロックまたは許可 (迷惑メールの設定)</span><span class="sxs-lookup"><span data-stu-id="8be55-163">Block or allow (junk email settings)</span></span>](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)
  
[<span data-ttu-id="8be55-164">検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする</span><span class="sxs-lookup"><span data-stu-id="8be55-164">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](block-email-spam-to-prevent-false-negatives.md)

