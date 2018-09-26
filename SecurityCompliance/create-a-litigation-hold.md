---
title: 証拠保全を Office 365 で作成します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: aa78d12046108aa1f1b974f01c02ff923b99b97b
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25037960"
---
# <a name="create-a-litigation-hold-in-office-365"></a><span data-ttu-id="581ee-102">証拠保全を Office 365 で作成します。</span><span class="sxs-lookup"><span data-stu-id="581ee-102">Create a Litigation Hold in Office 365</span></span>

<span data-ttu-id="581ee-p101">削除された項目と変更されたアイテムの元のバージョンを含む、すべてのメールボックスの内容を保持するのには証拠の保全には、メールボックスを配置できます。証拠保全でユーザーのメールボックスを配置すると、ユーザーのアーカイブ メールボックス内のコンテンツ (それが有効な場合) も保持されます。保留リストを作成するとき、(*保留中の時間をベース*とも呼ばれます) の保持期間を指定するには、削除するためを実行し、変更された項目が指定された期間保持し、メールボックスから完全に削除を実行します。コンテンツを無期限に保持することができますだけ、または (、*無限のホールド*と呼ばれる) か、証拠保全が解除されるまで。保留期間を指定する場合は、メッセージを受け取るか、メールボックスのアイテムが作成された日付から計算されます。</span><span class="sxs-lookup"><span data-stu-id="581ee-p101">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items. When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained. When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox. Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed. If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="581ee-108">証拠の保全を作成するときの動作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="581ee-108">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="581ee-109">ユーザーが完全に削除されたアイテムは、保留中のユーザーのメールボックスの回復可能なアイテム] フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="581ee-109">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="581ee-110">ユーザーが回復可能なアイテム] フォルダーから削除されたアイテムは、保留リストの中に保持されます。</span><span class="sxs-lookup"><span data-stu-id="581ee-110">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="581ee-111">110 GB を 30 GB から、回復可能なアイテム] フォルダーの記憶域のクォータが向上します。</span><span class="sxs-lookup"><span data-stu-id="581ee-111">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="581ee-112">ユーザーのプライマリおよびアーカイブ メールボックス内のアイテムが保持されます。</span><span class="sxs-lookup"><span data-stu-id="581ee-112">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="before-you-begin"></a><span data-ttu-id="581ee-113">はじめに</span><span class="sxs-lookup"><span data-stu-id="581ee-113">Before you begin</span></span>

- <span data-ttu-id="581ee-p102">Exchange Online のメールボックスを配置すると、証拠保全に割り当てる必要があります Exchange オンライン計画 2 ライセンスです。メールボックスが Exchange オンライン計画 1 のライセンスを割り当てられている場合は、上に配置するのには別の Exchange Online Archiving のライセンスを保持してそれを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="581ee-p102">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license. If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a><span data-ttu-id="581ee-116">Office 365 の管理センターでの証拠保全上のメールボックスの場所</span><span class="sxs-lookup"><span data-stu-id="581ee-116">Place a mailbox on Litigation Hold in the Office 365 admin center</span></span>

<span data-ttu-id="581ee-117">証拠保全が Office 365 の管理センターを使用して、メールボックスに配置する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="581ee-117">Here are the steps to place a maibox on Litigation Hold using the Office 365 admin center.</span></span>

1. <span data-ttu-id="581ee-118">https://portal.office.com/adminportal/homeのグローバル管理者アカウントを使ってサインインしています。</span><span class="sxs-lookup"><span data-stu-id="581ee-118">Go to https://portal.office.com/adminportal/home and sign in using your global administrator account.</span></span>
2. <span data-ttu-id="581ee-119">**ユーザー**をクリックして > の左側のナビゲーション ウィンドウで**アクティブなユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="581ee-119">Click **Users** > **Active users** in the left navigation pane.</span></span>
3. <span data-ttu-id="581ee-120">証拠保全に配置するメールボックスを持つユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="581ee-120">Select the user whose mailbox you want to place on Litigation Hold.</span></span>
4. <span data-ttu-id="581ee-121">フライアウトのページで、**メールの設定**] をクリックし、**証拠保全**の横の**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="581ee-121">On the fly-out page, click **Mail settings**, and then click **Edit** next to **Litigation hold**.</span></span>
5. <span data-ttu-id="581ee-122">**証拠保全**] ページで、証拠保全を有効にし、表示される次のオプション設定を完了するのには表示/非表示をクリックします。</span><span class="sxs-lookup"><span data-stu-id="581ee-122">On the **Litigation hold** page, click the toggle to turn on Litigation Hold and complete the following optional settings that are displayed:</span></span>
 
    ![O365_LitigationHold1.png](media/O365-LitigationHold1.png)

    <span data-ttu-id="581ee-p103">a.**ホールドの継続時間 (日)** -このボックスを使用して、時間ベースの保留リストを作成し、証拠保全に格納されると、メールボックスのメールボックス アイテムの保持期間を指定します。期間は、メールボックス アイテムの受信または作成した日付から計算されます。場合はこのボックスを空白のままにすると、アイテムは保留が解除されるまで、または無期限に保持されます。日を使用すると、期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="581ee-p103">a. **Hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold. The duration is calculated from the date a mailbox item is received or created. If you leave this box blank, items are held indefinitely or until the hold is removed. Use days to specify the duration.</span></span>
    
    <span data-ttu-id="581ee-p104">b.**注**- は、証拠保全に自分のメールボックスは、ユーザーに通知するために、このボックスを使用します。メモは、Outlook 2010 またはそれ以降を使用している場合、ユーザーのメールボックスの [アカウント情報] ページに表示されます。このページにアクセスするには、ユーザーが Outlook で**ファイル**をクリックできます。</span><span class="sxs-lookup"><span data-stu-id="581ee-p104">b. **Note** - Use this box to inform the user their mailbox is on Litigation Hold. The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
     
    <span data-ttu-id="581ee-p105">c. **Web ページ**には、証拠保全の詳細については web サイトにアクセスするため、このボックスを使用します。Outlook 2010 以降を使用している場合は、ユーザーのメールボックスの [アカウント情報] ページでこの URL が表示されます。このページにアクセスするには、ユーザーが Outlook で**ファイル**をクリックできます。</span><span class="sxs-lookup"><span data-stu-id="581ee-p105">c. **Web page** - Use this box to direct the user to a website for more information about Litigation Hold. This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
 
6. <span data-ttu-id="581ee-137">証拠保全を作成して**保存**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="581ee-137">Click **Save** to create the Litigation Hold.</span></span>

<span data-ttu-id="581ee-138">保留リストを作成したら、証拠保全が有効である選択したユーザーの [スライド アウト] ページで、メールの設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="581ee-138">After you create the hold, the mail settings on the fly-out page shows that Litigation Hold is turned on for the selected user.</span></span>

![O365_LitigationHold2.png](media/O365-LitigationHold2.png)

<span data-ttu-id="581ee-140">証拠保全の管理と証拠保全の一括作成する Exchange のオンライン PowerShell を使用して作成する方法の詳細については、[証拠保全上のメールボックスの場所](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="581ee-140">For more information about creating and managing Litigation Holds and using Exchange Online PowerShell to bulk-create Litigation Holds, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).</span></span>
