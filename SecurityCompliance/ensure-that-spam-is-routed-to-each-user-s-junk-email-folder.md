---
title: スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 7/16/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection でスパムをユーザーの迷惑メールフォルダーにルーティングする方法について説明します。
ms.openlocfilehash: 80c3e3cab1bdaf85e815ab1acc790cc907ebbb91
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341378"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="f9958-103">スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする</span><span class="sxs-lookup"><span data-stu-id="f9958-103">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9958-p101">このトピックは、ハイブリッド展開でオンプレミスのメールボックスをホストしている Exchange Online Protection (EOP) のお客様にのみ当てはまります。Office 365 でメールボックスが完全にホストされている Exchange Online のお客様は、ここに示すコマンドを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f9958-p101">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment. Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span> 
  
<span data-ttu-id="f9958-p102">EOP のユーザーの既定のスパム対策アクションでは、スパムメッセージを受信者の迷惑メールフォルダーに移動します。このアクションをオンプレミスのメールボックスで使用するには、オンプレミスのエッジサーバーまたはハブサーバーで Exchange メールフロールール (トランスポートルールとも呼ばれます) を構成して、EOP によって追加されたスパムヘッダーを検出する必要があります。これらのメールフロールールは、SclJunkThreshold コマンドレットのプロパティで使用されるスパム信頼レベル (SCL) を設定し、スパムを各メールボックスの迷惑メールフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="f9958-p102">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder. In order for this action to work with on-premises mailboxes, you must configure Exchange mail flow rules (also known as transport rules) on your on-premises Edge or Hub servers to detect spam headers added by EOP. These mail flow rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span> 
  
### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="f9958-109">Windows PowerShell を使用してスパムが迷惑メールフォルダーに移動されるようにメールフロールールを追加するには</span><span class="sxs-lookup"><span data-stu-id="f9958-109">To add mail flow rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="f9958-p103">オンプレミス Exchange サーバーの Exchange 管理シェル にアクセスします。オンプレミスの Exchange 組織で Exchange 管理シェル を開く方法については、「 **Open the Shell**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9958-p103">Access the Exchange Management Shell for your on-premises Exchange server. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>
    
2. <span data-ttu-id="f9958-112">コンテンツでフィルターされたスパム メッセージを [迷惑メール] フォルダーにルーティングするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9958-112">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    <span data-ttu-id="f9958-113">_NameForRule_ は、新しいルールの名前です (例: JunkContentFilteredMail)。</span><span class="sxs-lookup"><span data-stu-id="f9958-113">Where  _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span> 
    
3. <span data-ttu-id="f9958-114">コンテンツ フィルターに到達する前にスパムとしてマークされたメッセージを [迷惑メール] フォルダーにルーティングするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9958-114">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    <span data-ttu-id="f9958-115">_NameForRule_ は新しいルールの名前です (例: JunkMailBeforeReachingContentFilter)。</span><span class="sxs-lookup"><span data-stu-id="f9958-115">Where  _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span> 
    
4. <span data-ttu-id="f9958-116">次に示すコマンドを実行して、スパム フィルター ポリシーのブロック リスト ( **受信拒否送信者**一覧など) に登録されている送信者からのメッセージが [迷惑メール] フォルダーにルーティングされるようにします。</span><span class="sxs-lookup"><span data-stu-id="f9958-116">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span> 
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    <span data-ttu-id="f9958-117">_NameForRule_ は新しいルールの名前です (例: JunkMailInSenderBlockList)。</span><span class="sxs-lookup"><span data-stu-id="f9958-117">Where  _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span> 
    
<span data-ttu-id="f9958-p104">**[迷惑メール フォルダーにメッセージを移動する]** アクションを使用しない場合は、Exchange 管理センター のコンテンツ フィルター ポリシーで別のアクションを選択してください。詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。メッセージ ヘッダー内で該当するフィールドの詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9958-p104">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f9958-121">See also</span><span class="sxs-lookup"><span data-stu-id="f9958-121">See also</span></span>

[<span data-ttu-id="f9958-122">New-TransportRule コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f9958-122">New-TransportRule cmdlet</span></span>](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

