---
title: EOP スタンドアロンで迷惑メールをブロックする
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: laurawi
ms.date: 2/25/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: da21c0b6-e8f0-4cc8-af2e-5029a9433d59
ms.collection:
- M365-security-compliance
description: 迷惑メールの検出漏れを防ぐための EOP スタンドアロンの管理者向けドキュメント
ms.openlocfilehash: c9b17704c514fd83f8c00a51fad76cddb26e378c
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30306546"
---
## <a name="customize-the-office-365-anti-spam-filter-with-these-settings"></a><span data-ttu-id="62237-103">以下の設定により Office 365 のスパム対策フィルターをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="62237-103">Customize the Office 365 anti-spam filter with these settings</span></span>

<span data-ttu-id="62237-p101">管理者は、いくつかの Office 365 スパム フィルターの設定を利用して、迷惑メールがユーザーの受信トレイに送信されないようにすることができます。この一覧のオプションを使用すると、Office 365 のスパム フィルターは、より適切に迷惑メールをブロックし、検出漏れのメッセージを防ぐことができるようになります。このコンテキストでは、検出漏れとは、ユーザーの受信トレイに送信されてしまうスパム メールや迷惑メッセージのことです。</span><span class="sxs-lookup"><span data-stu-id="62237-p101">An Admin can use several Office 365 spam filter settings to help prevent email spam from being sent to a user inbox. The Office 365 spam filter will become better able to block email spam and prevent false negative messages if you use the options listed here. In this context, a false negative refers to email spam or junk messages that are getting sent to a user inbox.</span></span>
  
### <a name="block-ip-addresses-with-a-connection-filter"></a><span data-ttu-id="62237-107">接続フィルターで IP アドレスをブロックする</span><span class="sxs-lookup"><span data-stu-id="62237-107">Block IP addresses with a connection filter</span></span>

<span data-ttu-id="62237-108">接続フィルター IP 禁止一覧に送信者の IP アドレスを追加して、Office 365 のスパム フィルターをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="62237-108">Customize your Office 365 spam filter by adding the sender IP address to the connection filter IP block list:</span></span>
  
1. <span data-ttu-id="62237-109">「[メッセージ ヘッダー アナライザー](https://go.microsoft.com/fwlink/p/?LinkId=306583)」で説明されているように、Outlook や Outlook on the web (以前の Outlook Web App) などのメール クライアントでブロックするメッセージのヘッダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="62237-109">Obtain the headers for the message you want to block in your mail client such as Outlook or Outlook on the web (formerly known as Outlook Web App), as described in [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583).</span></span>
    
2. <span data-ttu-id="62237-110">[メッセージ ヘッダー アナライザー](https://testconnectivity.microsoft.com/?tabid=mha)を使用するか、または手動で、X-Forefront-Antispam-Report ヘッダー内の CIP タグの後に続く IP アドレスを検索します。</span><span class="sxs-lookup"><span data-stu-id="62237-110">Search for the IP address following the CIP tag in the X-Forefront-Antispam-Report header using the [message header analyzer](https://testconnectivity.microsoft.com/?tabid=mha) or manually.</span></span> 
    
3. <span data-ttu-id="62237-111">「[接続フィルター ポリシーを構成する](https://technet.microsoft.com/ja-JP/library/jj200718%28v=exchg.150%29.aspx)」の「EAC を使用して既定の接続フィルター ポリシーを編集する」に示された手順に従って、その IP アドレスを IP 禁止一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="62237-111">Add the IP address to the IP Block list by following the steps in "Use the EAC to edit the default connection filter policy" in [Configure the Connection Filter Policy](https://technet.microsoft.com/ja-JP/library/jj200718%28v=exchg.150%29.aspx).</span></span>
    
### <a name="block-bulk-mail-with-transport-rules-or-the-spam-filter"></a><span data-ttu-id="62237-112">トランスポート ルールまたはスパム フィルターでバルク メールをブロックする</span><span class="sxs-lookup"><span data-stu-id="62237-112">Block bulk mail with transport rules or the spam filter</span></span>

<span data-ttu-id="62237-p102">スパムは主に、ニュースレターやプロモーションなどのバルク メールでしょうか。[トランスポート ルールを使用してバルク メール メッセージを積極的にフィルタリングする](https://technet.microsoft.com/ja-JP/library/dn720438%28v=exchg.150%29.aspx)か、スパム フィルターの[高度なスパム フィルター処理オプション](https://technet.microsoft.com/ja-JP/library/jj200750%28v=exchg.150%29.aspx)で**バルク メール**設定をオンにすると、Office 365 でスパム フィルターをカスタマイズできます。Exchange 管理センターで、**[保護]** \> **[コンテンツ フィルター]** をクリックし、調整するフィルター ポリシーをダブルクリックして作業を開始します。ここで示すとおり、**[Spam and bulk mail actions (スパムおよびバルク メール操作)]** をクリックして設定を調整します。</span><span class="sxs-lookup"><span data-stu-id="62237-p102">Is the spam primarily bulk mail, for example, newsletters or promotions? You can customize the spam filter in Office 365 if you [Use transport rules to aggressively filter bulk email messages](https://technet.microsoft.com/ja-JP/library/dn720438%28v=exchg.150%29.aspx) or turn on the **Bulk mail** setting in your spam filter's [Advanced Spam Filtering Options](https://technet.microsoft.com/ja-JP/library/jj200750%28v=exchg.150%29.aspx). In the Exchange Admin center, get started by clicking **Protection** \> **Content filter** and then double click the filter policy you want to adjust. Click **Spam and bulk mail actions** to adjust the settings, as shown here.</span></span> 
  
![Exchange Online でバルク メール フィルターを設定する](media/a45095c2-269d-45b8-a76c-999b5e78da68.png)
  
### <a name="block-email-spam-using-spam-filter-block-lists"></a><span data-ttu-id="62237-118">スパム フィルター禁止一覧を使用して迷惑メールをブロックする</span><span class="sxs-lookup"><span data-stu-id="62237-118">Block email spam using spam filter block lists</span></span>

<span data-ttu-id="62237-p103">[スパム フィルター ポリシーを構成](https://technet.microsoft.com/ja-JP/library/jj200684%28v=exchg.150%29.aspx)して、スパム フィルターの送信者禁止一覧に送信者アドレスを追加するか、ドメイン禁止一覧にドメインを追加します。スパム フィルター禁止一覧に記載の送信者やドメインからのメールはスパムとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="62237-p103">[Configure your spam filter policies](https://technet.microsoft.com/ja-JP/library/jj200684%28v=exchg.150%29.aspx) to add the sender address to the sender block list or domain to the domain block list in the spam filter. Emails from a sender or domain on a spam filter block list will marked as spam.</span></span> 
  
## <a name="email-users-can-also-help-ensure-that-false-negative-and-email-spam-is-blocked-with-office-365-spam-filter"></a><span data-ttu-id="62237-121">メール ユーザーは、Office 365 のスパム フィルターを使用して、確実に検出漏れや迷惑メールをブロックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="62237-121">Email users can also help ensure that false negative and email spam is blocked with Office 365 spam filter</span></span>

<span data-ttu-id="62237-p104">Office 365 のスパム対策を活用すれば、[Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) または [Outlook on the web](https://go.microsoft.com/fwlink/p/?LinkId=294862) のスパム送信者一覧にスパム送信者アドレスを追加するようユーザーに指示した場合に、検出漏れや迷惑メールを防止することができます。Outlook on the web では、ここで示すとおり、**[設定]** \> **[オプション]** \> **[ブロックまたは許可]** をクリックし、**[ブロックする差出人]** 一覧にアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="62237-p104">It will help your Office 365 anti-spam efforts to prevent false negatives and junk mail if you tell your users to add the spam sender address to their blocked sender list in [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) or [Outlook on the web](https://go.microsoft.com/fwlink/p/?LinkId=294862). In Outlook on the web, get started by clicking **Settings** \> **Options** \> **Block or allow**, and then adding the address to the **Blocked senders** list, as shown here.</span></span> 
  
![Outlook on the web で送信者をブロックする](media/fdf51381-2527-4819-ac2a-5dff84d2a36d.png)
  
> [!NOTE]
> <span data-ttu-id="62237-125">差出人セーフ リストについて詳しくは、「[差出人セーフ リストと受信拒否リストの FAQ](https://technet.microsoft.com/ja-JP/library/dn133608%28v=exchg.150%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62237-125">For more detailed information about safe sender lists, see [Safe Sender and Blocked Sender Lists FAQ](https://technet.microsoft.com/ja-JP/library/dn133608%28v=exchg.150%29.aspx).</span></span> 
  
## <a name="eop-only-customers-set-up-directory-synchronization"></a><span data-ttu-id="62237-126">EOP のみのユーザー: ディレクトリ同期のセットアップ</span><span class="sxs-lookup"><span data-stu-id="62237-126">EOP-only customers: Set up directory synchronization</span></span>

<span data-ttu-id="62237-p105">ディレクトリ同期を使用してユーザー設定をサービスと同期させ、ブロックする差出人が考慮されるようにすると、検出漏れの迷惑メールを回避するのに役立ちます。詳細については、EOP のメール ユーザー管理で「ディレクトリ同期を使用してメール ユーザーを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62237-p105">It will help you to avoid false negative email spam if you sync user settings with the service via directory synchronization to ensure that your blocked senders are respected. For more information, see "Use directory synchronization to manage mail users" in Manage mail users in EOP.</span></span>
  
## <a name="eop-only-customers-who-are-not-using-directory-synchronization"></a><span data-ttu-id="62237-129">ディレクトリ同期を使用していない EOP のみのお客様</span><span class="sxs-lookup"><span data-stu-id="62237-129">EOP-only customers who are not using directory synchronization</span></span>

<span data-ttu-id="62237-p106">EOP サービスは、情報がサービスと共有されている場合、ユーザーの安全な差出人とブロックする差出人を尊重するように設計されています。Outlook を使用している EOP のお客様で、ユーザーを Office 365 に同期させるようにディレクトリ同期を構成していない場合でも、ブロックする差出人を使用してユーザーの受信トレイにメッセージが配信されないようにできます。ただし、次の状況ではいくつかの Exchange メール フロー ルールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62237-p106">The EOP service is designed to honor the user's safe and blocked senders, if the information has been shared with the service. If you are an EOP customer using Outlook, but do not have Directory Synchronization configured to sync your users to Office 365, you can still stop messages from being delivered to your users' inbox using blocked senders. However, you may have to set up some Exchange mail flow rules in the following situations:</span></span>
  
- <span data-ttu-id="62237-133">メッセージが EOP による通常のスパム フィルター処理を経てローカルのオンプレミス Exchange サーバーに配信され、EOP が SCL 1 から 4 (非スパム) のスパム判定を割り当てた場合、ユーザーのローカルの受信拒否リストが EOP スパム フィルターの判定をオーバーライドし、メッセージは迷惑メール フォルダーに配信されます。</span><span class="sxs-lookup"><span data-stu-id="62237-133">If a message goes through regular spam filtering through EOP and then is delivered to a local on-premises Exchange server, and EOP assigns a spam verdict of SCL 1-4 (non-spam), then your users' local blocked senders list will override the EOP spam filter verdict and deliver it to their junk email folder.</span></span>
    
- <span data-ttu-id="62237-p107">Exchange メール フロー ルールによって、または IP アドレスやドメインが許可一覧に含まれていることで、EOP のメッセージに SCL -1 が割り当てられている場合、SCL はコネクタを使用してオンプレミス Exchange サーバーに伝達されます。この場合、ユーザーの受信拒否リストは適用されません。この動作を変更するには、SCL を 0 に設定するローカルのメール フロー ルールを作成します。これにより、Outlook はユーザーのローカルの受信拒否リストを適用します。</span><span class="sxs-lookup"><span data-stu-id="62237-p107">If a message in EOP is assigned SCL -1 by an Exchange mail flow rule or because the IP address or domain is in your allow list, the SCL is propagated to the on-premises Exchange server using connectors. In this case, your user's blocked senders list will not be enforced. To change this, you can create a local mail flow rule that sets the SCL to 0. This will cause Outlook to enforce your user's local blocked senders list.</span></span>
    
<span data-ttu-id="62237-138">**受信拒否リストを使用してメッセージがユーザーの受信トレイに配信されないようにメール フロー ルールを設定するには**</span><span class="sxs-lookup"><span data-stu-id="62237-138">**To set up a mail flow rule to stop messages from being delivered to your users' inbox by using the blocked senders list**</span></span>
  
1. <span data-ttu-id="62237-p108">オンプレミス サーバーで Exchange 管理シェルを開きます。オンプレミスの Exchange 組織でシェルを開く方法については、「[Exchange 管理シェルを開く](https://technet.microsoft.com/library/dd638134%28v=exchg.160%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62237-p108">Open the Exchange Management Shell on your on-premises server. To learn how to open the Shell in your on-premises Exchange organization, see [Open the Exchange Management Shell](https://technet.microsoft.com/library/dd638134%28v=exchg.160%29.aspx).</span></span>
    
2. <span data-ttu-id="62237-141">SCL -1 とマークされたすべてのメッセージで SCL を更新するには、次のコマンドを実行してコンテンツでフィルタリングされたスパム メッセージを迷惑メール フォルダーにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="62237-141">Run the following command to route content-filtered spam messages to the Junk Email folder in order to update the SCL on every message that was marked with SCL -1:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SCL:-1" -SetSCL 0
  ```

    <span data-ttu-id="62237-p109">SCL はオンプレミス Exchange サーバーでは 0 なので、非スパムはユーザーの受信トレイに配信されますが、ユーザーのローカルの受信拒否リストによって迷惑メール フォルダーに送信されことも可能です。EOP でスパム検疫を使用している場合も、ユーザーのセーフ リストに記載されている送信者がスパムとして識別され、検疫に送られる可能性があります。ただし、ローカルのメールボックスで迷惑メール フォルダーを使用している場合、この操作で、安全な送信者用の受信トレイへの配信が可能になります。</span><span class="sxs-lookup"><span data-stu-id="62237-p109">Because the SCL is 0 in your on-premises Exchange server, non-spam will be delivered to your users' inboxes but still allow for users' local blocked senders list to send them to junk email. If you are using spam quarantine in EOP, it is still possible that senders who are on your user's safe list will be identified as spam and sent to quarantine. If you are using the Junk Mail Folder in your local mailbox, however, this will allow delivery to the Inbox for safe senders.</span></span>

> [!WARNING]
> <span data-ttu-id="62237-p110">メール フロー ルールを使用して SCL 値を 0 (または -1 以外の値) に変更すると、すべての Outlook の迷惑メール オプションがメッセージに適用されます。これは、ブロック リストおよびセーフ リストが尊重されるようになることを意味しますが、ブロック リストやセーフ リストにアドレスが記載されていないメッセージは、クライアント側の迷惑メール フィルター処理によって迷惑メールとしてマークされる可能性があるということも意味します。Outlook にブロック リストとセーフ リストを処理させる必要があるものの、クライアント側の迷惑メール フィルターは使用したくない場合は、Outlook の迷惑メール オプションでオプションを「自動フィルター処理なし」に設定する必要があります。最新バージョンの Outlook では、「自動フィルター処理なし」が既定のオプションですが、クライアント側の迷惑メール フィルターがメッセージに適用されないようにするために、この設定になっていることを確認する必要があります。管理者は、「[Outlook: 迷惑メールの UI とフィルター処理機構を無効にするポリシー設定](https://support.microsoft.com/ja-JP/kb/2180568)」の手順に従って、Outlook の迷惑メール フィルター処理を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="62237-p110">If you use a mail flow rule to change the SCL value to 0 (or any value other than -1), then all of the Outlook junk mail options will apply to the message. This means that blocked and safe lists will be honored, but also means that messages that do not have addresses from the blocked or safe lists will potentially be marked as junk by the client side junk mail filter processing. If you want to have Outlook process the blocked and safe lists, but not use the client side junk mail filter, you must set the option to "No Automatic Filtering" in Outlook Junk Mail Options. "No Automatic Filtering" is the default option in the latest versions of Outlook, but you should confirm that the this setting is in place to ensure the client side junk mail filter is not applied to the messages. As an administrator, you can enforce disabling the Outlook Junk Email filtering by following the instructions in [Outlook: Policy setting to disable the Junk E-mail UI and filtering mechanism](https://support.microsoft.com/ja-JP/kb/2180568).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="62237-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="62237-150">See Also</span></span>

[<span data-ttu-id="62237-151">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="62237-151">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="62237-152">セーフリストまたはその他の手法で誤検知の電子メールがスパムとしてマークされないようにする</span><span class="sxs-lookup"><span data-stu-id="62237-152">Prevent false positive email marked as spam with a safelist or other techniques</span></span>](prevent-email-from-being-marked-as-spam.md)
