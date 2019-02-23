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
description: EOP のお客様のための既定のスパム対策アクションでは、スパム メッセージは受信者の [迷惑メール] フォルダーに移動されます。このアクションをオンプレミスのメールボックスで使用するには、EOP によって追加されたスパム ヘッダーを検出するように、オンプレミスのエッジ サーバーまたはハブ サーバーで Exchange トランスポート ルールを構成する必要があります。これらのトランスポート ルールにより、Set-OrganizationConfig コマンドレットの SclJunkThreshold プロパティで使用する Spam Confidence Level (SCL) が設定されます。
ms.openlocfilehash: f712e66934956bcf46215e4016501003ce9b1725
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222886"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="c994a-105">スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする</span><span class="sxs-lookup"><span data-stu-id="c994a-105">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c994a-p102">このトピックは、ハイブリッド展開でオンプレミスのメールボックスをホストしている Exchange Online Protection (EOP) のお客様にのみ当てはまります。Office 365 でメールボックスが完全にホストされている Exchange Online のお客様は、ここに示すコマンドを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c994a-p102">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment. Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span> 
  
<span data-ttu-id="c994a-p103">EOP のお客様のための既定のスパム対策アクションでは、スパム メッセージは受信者の [迷惑メール] フォルダーに移動されます。このアクションをオンプレミスのメールボックスで使用するには、EOP によって追加されたスパム ヘッダーを検出するように、オンプレミスのエッジ サーバーまたはハブ サーバーで Exchange トランスポート ルールを構成する必要があります。これらのトランスポート ルールにより、Set-OrganizationConfig コマンドレットの SclJunkThreshold プロパティで使用する Spam Confidence Level (SCL) が設定されます。</span><span class="sxs-lookup"><span data-stu-id="c994a-p103">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder. In order for this action to work with on-premises mailboxes, you must configure Exchange Transport rules on your on-premises Edge or Hub servers to detect spam headers added by EOP. These Transport rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span> 
  
### <a name="to-add-transport-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="c994a-111">Windows PowerShell を使用して、スパムが [迷惑メール] フォルダーに移動されるようにするトランスポート ルールを追加するには</span><span class="sxs-lookup"><span data-stu-id="c994a-111">To add transport rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="c994a-p104">オンプレミス Exchange サーバーの Exchange 管理シェル にアクセスします。オンプレミスの Exchange 組織で Exchange 管理シェル を開く方法については、「 **Open the Shell**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c994a-p104">Access the Exchange Management Shell for your on-premises Exchange server. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>
    
2. <span data-ttu-id="c994a-114">コンテンツでフィルターされたスパム メッセージを [迷惑メール] フォルダーにルーティングするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c994a-114">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    <span data-ttu-id="c994a-115">_NameForRule_ は、新しいルールの名前です (例: JunkContentFilteredMail)。</span><span class="sxs-lookup"><span data-stu-id="c994a-115">Where  _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span> 
    
3. <span data-ttu-id="c994a-116">コンテンツ フィルターに到達する前にスパムとしてマークされたメッセージを [迷惑メール] フォルダーにルーティングするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c994a-116">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    <span data-ttu-id="c994a-117">_NameForRule_ は新しいルールの名前です (例: JunkMailBeforeReachingContentFilter)。</span><span class="sxs-lookup"><span data-stu-id="c994a-117">Where  _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span> 
    
4. <span data-ttu-id="c994a-118">次に示すコマンドを実行して、スパム フィルター ポリシーのブロック リスト ( **受信拒否送信者**一覧など) に登録されている送信者からのメッセージが [迷惑メール] フォルダーにルーティングされるようにします。</span><span class="sxs-lookup"><span data-stu-id="c994a-118">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span> 
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    <span data-ttu-id="c994a-119">_NameForRule_ は新しいルールの名前です (例: JunkMailInSenderBlockList)。</span><span class="sxs-lookup"><span data-stu-id="c994a-119">Where  _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span> 
    
<span data-ttu-id="c994a-p105">**[迷惑メール フォルダーにメッセージを移動する]** アクションを使用しない場合は、Exchange 管理センター のコンテンツ フィルター ポリシーで別のアクションを選択してください。詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。メッセージ ヘッダー内で該当するフィールドの詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c994a-p105">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c994a-123">See also</span><span class="sxs-lookup"><span data-stu-id="c994a-123">See also</span></span>

[<span data-ttu-id="c994a-124">New-TransportRule コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c994a-124">New-TransportRule cmdlet</span></span>](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

