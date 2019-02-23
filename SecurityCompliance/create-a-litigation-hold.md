---
title: Office 365 で訴訟ホールドを作成する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: f2d3793eac84e8f80158842c833c30986b0549c5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218657"
---
# <a name="create-a-litigation-hold-in-office-365"></a><span data-ttu-id="98a57-102">Office 365 で訴訟ホールドを作成する</span><span class="sxs-lookup"><span data-stu-id="98a57-102">Create a Litigation Hold in Office 365</span></span>

<span data-ttu-id="98a57-p101">メールボックスを訴訟ホールドの対象にして、削除済みアイテムや変更されたアイテムの元のバージョンを含む、すべてのメールボックスのコンテンツを保持することができます。ユーザーメールボックスを訴訟ホールドの対象にすると、ユーザーのアーカイブメールボックス内のコンテンツ (有効になっている場合) も保持されます。保持を作成するときに、削除および変更されたアイテムが指定した期間保持され、メールボックスから完全に削除されるように、保持期間 (*時間ベースの保持*とも呼ばれます) を指定できます。または、コンテンツを無期限に (*無限保持*と呼ばれます)、または訴訟ホールドが解除されるまで保持することができます。保持期間を指定する場合は、メッセージが受信された日付、またはメールボックスアイテムが作成された日付から計算されます。</span><span class="sxs-lookup"><span data-stu-id="98a57-p101">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items. When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained. When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox. Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed. If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="98a57-108">訴訟ホールドを作成すると、次のような結果になります。</span><span class="sxs-lookup"><span data-stu-id="98a57-108">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="98a57-109">ユーザーによって完全に削除されたアイテムは、保留中のユーザーのメールボックス内の [回復可能なアイテム] フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="98a57-109">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="98a57-110">ユーザーが [回復可能なアイテム] フォルダーから削除されたアイテムは、保持期間中は保持されます。</span><span class="sxs-lookup"><span data-stu-id="98a57-110">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="98a57-111">回復可能なアイテムフォルダーの記憶域のクォータは、30 gb から 110 gb に増加しました。</span><span class="sxs-lookup"><span data-stu-id="98a57-111">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="98a57-112">ユーザーのプライマリおよびアーカイブメールボックスのアイテムは保持されます。</span><span class="sxs-lookup"><span data-stu-id="98a57-112">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="before-you-begin"></a><span data-ttu-id="98a57-113">始める前に</span><span class="sxs-lookup"><span data-stu-id="98a57-113">Before you begin</span></span>

- <span data-ttu-id="98a57-p102">exchange online メールボックスを訴訟ホールドの対象にするには、exchange online プラン2ライセンスが割り当てられている必要があります。メールボックスに exchange online プラン1ライセンスが割り当てられている場合は、それを保持するために別の exchange online アーカイブライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="98a57-p102">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license. If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a><span data-ttu-id="98a57-116">Office 365 管理センターでメールボックスを訴訟ホールドの対象にする</span><span class="sxs-lookup"><span data-stu-id="98a57-116">Place a mailbox on Litigation Hold in the Office 365 admin center</span></span>

<span data-ttu-id="98a57-117">Office 365 管理センターを使用して、訴訟ホールドに maibox を配置する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="98a57-117">Here are the steps to place a maibox on Litigation Hold using the Office 365 admin center.</span></span>

1. <span data-ttu-id="98a57-118">にhttps://portal.office.com/adminportal/home移動し、全体管理者アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="98a57-118">Go to https://portal.office.com/adminportal/home and sign in using your global administrator account.</span></span>
2. <span data-ttu-id="98a57-119">左側のナビゲーションウィンドウで [**ユーザー** > の**アクティブなユーザー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98a57-119">Click **Users** > **Active users** in the left navigation pane.</span></span>
3. <span data-ttu-id="98a57-120">訴訟ホールドの対象とするメールボックスを持つユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="98a57-120">Select the user whose mailbox you want to place on Litigation Hold.</span></span>
4. <span data-ttu-id="98a57-121">[フライアウト] ページで、[**メールの設定**] をクリックし、[**訴訟ホールド**] の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98a57-121">On the fly-out page, click **Mail settings**, and then click **Edit** next to **Litigation hold**.</span></span>
5. <span data-ttu-id="98a57-122">[**訴訟ホールド**] ページで、オンにして訴訟ホールドを有効にし、表示されている次のオプション設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="98a57-122">On the **Litigation hold** page, click the toggle to turn on Litigation Hold and complete the following optional settings that are displayed:</span></span>
 
    ![O365_LitigationHold1](media/O365-LitigationHold1.png)

    <span data-ttu-id="98a57-p103">[**保持期間 (日)** ]-このボックスを使用して、時間ベースの保持を作成し、メールボックスが訴訟ホールドの対象になったときのメールボックスアイテムの保持期間を指定します。期間は、メールボックスアイテムが受信または作成された日付から計算されます。このボックスを空白のままにすると、アイテムは無期限に、または保持が解除されるまで保持されます。期間を指定するには、[日] を使用します。</span><span class="sxs-lookup"><span data-stu-id="98a57-p103">a. **Hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold. The duration is calculated from the date a mailbox item is received or created. If you leave this box blank, items are held indefinitely or until the hold is removed. Use days to specify the duration.</span></span>
    
    <span data-ttu-id="98a57-p104">b. 注: このボックスを使用して、メールボックスが訴訟ホールドの対象である**こと**をユーザーに通知します。メモは、Outlook 2010 以降を使用している場合は、ユーザーのメールボックスの [アカウント情報] ページに表示されます。このページにアクセスするには、ユーザーが Outlook で [**ファイル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98a57-p104">b. **Note** - Use this box to inform the user their mailbox is on Litigation Hold. The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
     
    <span data-ttu-id="98a57-p105">c. **web ページ**-訴訟ホールドの詳細については、このボックスを使用してユーザーに web サイトを送信します。この URL は、Outlook 2010 以降を使用している場合に、ユーザーのメールボックスの [アカウント情報] ページに表示されます。このページにアクセスするには、ユーザーが Outlook で [**ファイル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98a57-p105">c. **Web page** - Use this box to direct the user to a website for more information about Litigation Hold. This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
 
6. <span data-ttu-id="98a57-137">[**保存**] をクリックして訴訟ホールドを作成します。</span><span class="sxs-lookup"><span data-stu-id="98a57-137">Click **Save** to create the Litigation Hold.</span></span>

<span data-ttu-id="98a57-138">ホールドを作成した後、フライアウトページのメール設定は、選択したユーザーに対して訴訟ホールドが有効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="98a57-138">After you create the hold, the mail settings on the fly-out page shows that Litigation Hold is turned on for the selected user.</span></span>

![O365_LitigationHold2](media/O365-LitigationHold2.png)

<span data-ttu-id="98a57-140">訴訟ホールドを作成および管理し、Exchange Online PowerShell を使用して訴訟ホールドを一括作成する方法の詳細については、「[メールボックスを訴訟ホールドの](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold)対象にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98a57-140">For more information about creating and managing Litigation Holds and using Exchange Online PowerShell to bulk-create Litigation Holds, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).</span></span>
