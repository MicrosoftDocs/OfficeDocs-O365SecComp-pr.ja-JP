---
title: メールボックスを訴訟ホールドの対象にする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2016
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: adee4621-3626-4aec-aa53-00b35ff0d0b0
description: 'メールボックスを訴訟ホールドの対象にすると、削除済みアイテムと変更されたアイテムの元のバージョンを含む、すべてのメールボックスのコンテンツが保持されます。 '
ms.openlocfilehash: 8f440f5fc0bc7dafd639bdf8136808aa2f3bd35f
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026444"
---
# <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="79ba4-103">メールボックスを訴訟ホールドの対象にする</span><span class="sxs-lookup"><span data-stu-id="79ba4-103">Place a mailbox on Litigation Hold</span></span>
 
<span data-ttu-id="79ba4-p101">メールボックスを訴訟ホールドの対象にすると、削除済みアイテムと変更されたアイテムの元のバージョンを含む、すべてのメールボックスのコンテンツが保持されます。ユーザーのメールボックスを訴訟ホールドの対象にすると、ユーザーのアーカイブ メールボックス (有効である場合) もホールドの対象になります。削除済みアイテムと変更されたアイテムは、指定した期間またはメールボックスを訴訟ホールドの対象から外すまで、保持されます。[In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx) 検索で、このようなメールボックスのすべてのアイテムが返されます。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p101">Place a mailbox on Litigation Hold to preserve all mailbox content, including deleted items and original versions of modified items. When you place a user' mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also placed on hold. Deleted and modified items are preserved for a specified period, or until you remove the mailbox from Litigation Hold. All such mailbox items are returned in an [In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx) search.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="79ba4-p102">証拠保全は、ユーザーのメールボックスの回復可能なアイテム フォルダー内のアイテムを保持します。番号を削除または変更した項目のサイズによっては、メールボックスの回復可能なアイテム] フォルダーのサイズが簡単に向上します。[回復可能なアイテム] フォルダーは、既定で高いクォータが構成されます。Exchange online では、証拠保全のメールボックスを配置すると、このクォータが自動的に大きくなります。Exchange Server 2013 では、お勧めは、証拠保全、回復可能なアイテムのクォータの制限に到達しないことを確認するのには週単位でのメールボックスを監視すること。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p102">Litigation Hold preserves items in the Recoverable Items folder in the user's mailbox. Depending on number and size of items deleted or modified, the size of the Recoverable Items folder of the mailbox may increase quickly. The Recoverable Items folder is configured with a high quota by default. In Exchange Online, this quota is automatically increased when you place a mailbox on Litigation Hold. In Exchange Server 2013, we recommend that you monitor mailboxes that are placed on Litigation Hold on a weekly basis to ensure they don't reach the limits of the Recoverable Items quotas.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="79ba4-113">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="79ba4-113">What do you need to know before you begin?</span></span>
<span data-ttu-id="79ba4-114"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="79ba4-114"></span></span>

- <span data-ttu-id="79ba4-115">予想所要時間: 5 分</span><span class="sxs-lookup"><span data-stu-id="79ba4-115">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="79ba4-116">訴訟ホールド設定が有効になるまでに、最長で 60 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="79ba4-116">The Litigation Hold setting may take up to 60 minutes to take effect.</span></span>
    
- <span data-ttu-id="79ba4-p103">[メッセージング ポリシーとコンプライアンスのアクセス許可](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) トピック内の この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。 の「インプレース保持」エントリ。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "In-Place Hold" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="79ba4-p104">Exchange Online のメールボックスを配置すると、証拠保全に割り当てる必要があります Exchange Online (プラン 2) ライセンスです。メールボックスが Exchange Online (プラン 1) のライセンスを割り当てられている場合は、上に配置するのには別の Exchange Online Archiving のライセンスを保持してそれを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p104">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online (Plan 2) license. If a mailbox is assigned an Exchange Online (Plan 1) license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    
- <span data-ttu-id="79ba4-p105">説明したよう、ユーザーのメールボックスに、証拠保全を配置すると、ユーザーのアーカイブ メールボックス内のコンテンツも配置保留状態にされます。Exchange ハイブリッド展開での設置型のプライマリ メールボックスで、証拠保全を配置する場合、クラウド ・ ベースのアーカイブ メールボックスが有効な場合) も保留状態に配置されます。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p105">As previously explained, when you place a Litigation Hold on a user's mailbox, content in the user's archive mailbox is also placed on hold. If you place a Litigation Hold on an on-premises primary mailbox in an Exchange hybrid deployment, the cloud-based archive mailbox (if enabled) is also placed on hold.</span></span>
    
- <span data-ttu-id="79ba4-p106">Exchange online では、回復可能なアイテム フォルダーのクォータが自動的に増加 100 GB に証拠保全のメールボックスを配置すると。このフォルダーの既定のサイズは、30 GB です。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p106">In Exchange Online, the quota for the Recoverable Items folder is automatically increased to 100 GB when you place a mailbox on Litigation Hold. The default size of this folder is 30 GB.</span></span>
    
- <span data-ttu-id="79ba4-p107">証拠保全は、削除済みアイテムが保持され、保留が解除されるまで、変更されたアイテムの元のバージョンも保持されます。保持期間] は、指定した期間のメールボックス アイテムが保持されますを指定することができます。保留期間を指定する場合は、メッセージを受け取るか、メールボックスのアイテムが作成された日付から計算されます。指定した条件を満たすアイテムを保持するには、クエリ ベースの保留リストを作成するのには、埋め込みの保持を使用します。詳細については、[作成または埋め込みの保持を削除する](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p107">Litigation Hold preserves deleted items and also preserves original versions of modified items until the hold is removed. You can optionally specify a hold duration, which preserves a mailbox item for the specified duration period. If you specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created. To preserve items that meet your specified criteria, use an In-Place Hold to create a query-based hold. For details, see [Create or Remove an In-Place Hold](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx).</span></span>
    
- <span data-ttu-id="79ba4-p108">保留中の Exchange Online のメールボックスを配置するのにはシェルを使用するには、Exchange のオンライン PowerShell を使用する必要です。詳細については、 [Exchange オンラインを使用してリモート PowerShell への接続](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p108">To use the Shell to place an Exchange Online mailbox on hold, you have to use Exchange Online PowerShell. For more information, see [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span></span>
    
- <span data-ttu-id="79ba4-p109">パブリック フォルダー メールボックスを訴訟ホールドの対象にすることはサポートされていません。パブリック フォルダーを保持の対象にするには、インプレース ホールドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p109">Placing a Litigation Hold on a public folder mailbox isn't supported. You have to use In-Place Hold to place a hold on public folders.</span></span>
    
## <a name="use-the-eac-to-place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="79ba4-134">EAC を使用してメールボックスを訴訟ホールドの対象にする</span><span class="sxs-lookup"><span data-stu-id="79ba4-134">Use the EAC to place a mailbox on Litigation Hold</span></span>
<span data-ttu-id="79ba4-135"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="79ba4-135"></span></span>

1. <span data-ttu-id="79ba4-136">**[受信者]** \> **[メールボックス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="79ba4-136">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="79ba4-137">ユーザーのメールボックスのリストで、訴訟ホールドの対象とするメールボックスを選択し、 **[編集]**![編集アイコン](media/ITPro-EAC-EditIcon.png) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79ba4-137">In the list of user mailboxes, click the mailbox that you want to place on Litigation Hold, and then click **Edit**![Edit icon](media/ITPro-EAC-EditIcon.png).</span></span>
    
3. <span data-ttu-id="79ba4-138">[メールボックスのプロパティ] ページをクリックして **[メールボックスの機能です**。</span><span class="sxs-lookup"><span data-stu-id="79ba4-138">On the mailbox properties page, click **Mailbox features.**</span></span>
    
4. <span data-ttu-id="79ba4-139">**[訴訟ホールド:無効]** で、 **[有効]** をクリックすると、メールボックスが訴訟ホールドの対象になります。</span><span class="sxs-lookup"><span data-stu-id="79ba4-139">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span> 
    
5. <span data-ttu-id="79ba4-140">**[訴訟ホールド]** ページで、以下のオプション情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="79ba4-140">On the **Litigation Hold** page, enter the following optional information:</span></span> 
    
  - <span data-ttu-id="79ba4-p110">**訴訟ホールド期間 (日)** このボックスを使用して、メールボックスを訴訟ホールドの対象にするときに、メールボックス アイテムを保持する期間を指定します。期間は、メールボックス アイテムが受信または作成された日から計算されます。このボックスが空白の場合は、アイテムは無期限に、またはその保留が解除されるまで保持されます。日数で期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p110">**Litigation hold duration (days)** Use this box to specify how long mailbox items are held when the mailbox is placed on Litigation Hold. The duration is calculated from the date a mailbox item is received or created. If you leave this box blank, items are held indefinitely or until the hold is removed. Use days to specify the duration.</span></span> 
    
  - <span data-ttu-id="79ba4-p111">**メモ**証拠保全に自分のメールボックスは、ユーザーに通知するのにには、このボックスを使用します。メモは、Outlook 2010 またはそれ以降を使用している場合、ユーザーのメールボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p111">**Note** Use this box to inform the user their mailbox is on Litigation Hold. The note will appear in the user's mailbox if they're using Outlook 2010 or later.</span></span> 
    
  - <span data-ttu-id="79ba4-p112">**URL**証拠保全の詳細については web サイトをユーザーに指示するのにには、このボックスを使用します。Outlook 2010 以降を使用している場合は、ユーザーのメールボックスにこの URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p112">**URL** Use this box to direct the user to a website for more information about Litigation Hold. This URL appears in the user's mailbox if they are using Outlook 2010 or later.</span></span> 
    
6. <span data-ttu-id="79ba4-149">**[訴訟ホールド]** ページの **[保存]** をクリックして、メールボックスのプロパティ ページにある **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79ba4-149">Click **Save** on the **Litigation Hold** page, and then click **Save** on the mailbox properties page.</span></span> 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-indefinitely"></a><span data-ttu-id="79ba4-150">シェルを使用して無期限にメールボックスを訴訟ホールドの対象にする</span><span class="sxs-lookup"><span data-stu-id="79ba4-150">Use the Shell to place a mailbox on Litigation Hold indefinitely</span></span>
<span data-ttu-id="79ba4-151"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="79ba4-151"></span></span>

<span data-ttu-id="79ba4-p113">この例では、メールボックス bsuneja@contoso.com を訴訟ホールドの対象にします。メールボックス内のアイテムは、無期限にまたは保留が解除されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p113">This example places the mailbox bsuneja@contoso.com on Litigation Hold. Items in the mailbox are held indefinitely or until the hold is removed.</span></span>
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true
```

> [!NOTE]
> <span data-ttu-id="79ba4-154">メールボックスを無期限に訴訟ホールドの対象にする (期間を指定しない) 場合、メールボックスの  _LitigationHoldDuration_ プロパティの値は  `Unlimited` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="79ba4-154">When you place a mailbox on Litigation Hold indefinitely (by not specifying a duration period), the value for the  _LitigationHoldDuration_ property mailbox is set to  `Unlimited`.</span></span> 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-and-preserve-items-for-a-specified-duration"></a><span data-ttu-id="79ba4-155">シェルを使用してメールボックスを訴訟ホールドの対象にし、指定した期間アイテムを保持する</span><span class="sxs-lookup"><span data-stu-id="79ba4-155">Use the Shell to place a mailbox on Litigation Hold and preserve items for a specified duration</span></span>
<span data-ttu-id="79ba4-156"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="79ba4-156"></span></span>

<span data-ttu-id="79ba4-157">この例では、メールボックス bsuneja@contoso.com を訴訟ホールドの対象とし、2555 日間 (約 7 年間) アイテムを保持します。</span><span class="sxs-lookup"><span data-stu-id="79ba4-157">This example places the mailbox bsuneja@contoso.com on Litigation Hold and preserves items for 2555 days (approximately 7 years).</span></span> 
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true -LitigationHoldDuration 2555
```

## <a name="use-the-shell-to-place-all-mailboxes-on-litigation-hold-for-a-specified-duration"></a><span data-ttu-id="79ba4-158">シェルを使用してすべてのメールボックスを指定した期間訴訟ホールドの対象にする</span><span class="sxs-lookup"><span data-stu-id="79ba4-158">Use the Shell to place all mailboxes on Litigation Hold for a specified duration</span></span>
<span data-ttu-id="79ba4-159"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="79ba4-159"></span></span>

<span data-ttu-id="79ba4-p114">組織では、すべてのメールボックス データを特定の期間保持しなければならない場合があります。組織内のすべてのメールボックスを訴訟ホールドの対象にする前に、以下の点を考慮します。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p114">Your organization may require that all mailbox data be preserved for a specific period of time. Before you place all mailboxes in an organization on Litigation Hold, consider the following:</span></span>
  
<span data-ttu-id="79ba4-162">次の例では、組織内のすべてのユーザー メールボックスを 1 年間 (365 日間) 訴訟ホールドの対象にします。</span><span class="sxs-lookup"><span data-stu-id="79ba4-162">This example places all user mailboxes in the organization on Litigation Hold for one year (365 days).</span></span>
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -LitigationHoldEnabled $true -LitigationHoldDuration 365
```

<span data-ttu-id="79ba4-163">この例では、[Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) コマンドレットを使用して組織内のすべてのユーザー メールボックスを取得し、受信者フィルターを使用してすべてのユーザーのメールボックスを含めます。それから、メールボックスの一覧を [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) コマンドレットにパイプ処理して訴訟ホールドを有効にし、保持期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="79ba4-163">The example uses the [Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) cmdlet to retrieve all mailboxes in the organization, specifies a recipient filter to include all user mailboxes, and then pipes the list of mailboxes to the [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) cmdlet to enable the Litigation Hold and hold duration.</span></span> 
  
<span data-ttu-id="79ba4-164">すべてのユーザー メールボックスを無期限の保持の対象にするには、上記のコマンドを実行しますが、 _LitigationHoldDuration_ パラメーターは含めません。</span><span class="sxs-lookup"><span data-stu-id="79ba4-164">To place all user mailboxes on an indefinite hold, run the previous command but don't include the  _LitigationHoldDuration_ parameter.</span></span> 
  
<span data-ttu-id="79ba4-165">1 つ以上のメールボックスを含めるまたは除外するフィルターで他の受信者のプロパティを使用する例については、「[詳細情報](#moreinfo.md)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79ba4-165">See the [More information](#moreinfo.md) section for examples of using other recipient properties in a filter to include or exclude one or more mailboxes.</span></span> 
  
## <a name="use-the-shell-to-remove-a-mailbox-from-litigation-hold"></a><span data-ttu-id="79ba4-166">シェルを使用してメールボックスを訴訟ホールドから削除する</span><span class="sxs-lookup"><span data-stu-id="79ba4-166">Use the Shell to remove a mailbox from Litigation Hold</span></span>
<span data-ttu-id="79ba4-167"><a name="sectionSection5"> </a></span><span class="sxs-lookup"><span data-stu-id="79ba4-167"></span></span>

<span data-ttu-id="79ba4-168">この例では、メールボックス bsuneja@contoso.com を訴訟ホールドから削除します。</span><span class="sxs-lookup"><span data-stu-id="79ba4-168">This example removes the mailbox bsuneja@contoso.com from Litigation Hold.</span></span>
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $false
```

<span data-ttu-id="79ba4-169">P</span><span class="sxs-lookup"><span data-stu-id="79ba4-169">P</span></span>
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="79ba4-170">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="79ba4-170">How do you know this worked?</span></span>
<span data-ttu-id="79ba4-171"><a name="sectionSection6"> </a></span><span class="sxs-lookup"><span data-stu-id="79ba4-171"></span></span>

<span data-ttu-id="79ba4-172">メールボックスが正常に訴訟ホールドの対象となったことを確認するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="79ba4-172">To verify that you have successfully placed a mailbox on Litigation Hold, do the one of the following:</span></span>
  
- <span data-ttu-id="79ba4-173">EAC で以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="79ba4-173">In the EAC:</span></span>
    
1. <span data-ttu-id="79ba4-174">**[受信者]** \> **[メールボックス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="79ba4-174">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="79ba4-175">ユーザーのメールボックスのリストで、訴訟ホールドの設定を確認するメールボックスをクリックし、 **[編集]**![編集アイコン](media/ITPro-EAC-EditIcon.png) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79ba4-175">In the list of user mailboxes, click the mailbox that you want to verify Litigation Hold settings for, and then click **Edit**![Edit icon](media/ITPro-EAC-EditIcon.png).</span></span>
    
3. <span data-ttu-id="79ba4-176">[メールボックスのプロパティ] ページをクリックして **[メールボックスの機能です**。</span><span class="sxs-lookup"><span data-stu-id="79ba4-176">On the mailbox properties page, click **Mailbox features.**</span></span>
    
4. <span data-ttu-id="79ba4-177">**[訴訟ホールド]** の下でそのホールドが有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79ba4-177">Under **Litigation hold**, verify that hold is enabled.</span></span>
    
5. <span data-ttu-id="79ba4-p115">**[詳細表示]** をクリックして、いつまただれによってメールボックスが訴訟ホールドの対象とされたかを確認します。オプションの **[訴訟ホールド期間 (日)]**、 **[メモ]**、および **[URL]** ボックスの値を確認したり、変更したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p115">Click **View details** to verify when the mailbox was placed on Litigation Hold and by whom. You can also verify or change the values in the optional **Litigation hold duration (days)**, **Note**, and **URL** boxes.</span></span> 
    
- <span data-ttu-id="79ba4-180">シェルで、次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="79ba4-180">In the Shell, run one of the following commands:</span></span>
    
  ```
  Get-Mailbox <name of mailbox> | FL LitigationHold*
  ```

    <span data-ttu-id="79ba4-181">または</span><span class="sxs-lookup"><span data-stu-id="79ba4-181">or</span></span>
    
  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,LitigationHold*
  ```

    <span data-ttu-id="79ba4-182">メールボックスが無期限に訴訟ホールドの対象とされた場合、メールボックスの  _LitigationHoldDuration_ プロパティの値は  `Unlimited` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="79ba4-182">If a mailbox is placed on Litigation Hold indefinitely, the value for the  _LitigationHoldDuration_ property mailbox is set to  `Unlimited`.</span></span>
    
## <a name="more-information"></a><span data-ttu-id="79ba4-183">詳細情報</span><span class="sxs-lookup"><span data-stu-id="79ba4-183">More information</span></span>
<span data-ttu-id="79ba4-184"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="79ba4-184"></span></span>

- <span data-ttu-id="79ba4-185">組織においてすべてのメールボックス データを特定の期間保持する必要がある場合、組織内のすべてのメールボックスを訴訟ホールドの対象にする前に、以下を考慮します。</span><span class="sxs-lookup"><span data-stu-id="79ba4-185">If your organization requires that all mailbox data has to preserved for a specific period of time, consider the following before you place all mailboxes in an organization on Litigation Hold.</span></span>
    
  - <span data-ttu-id="79ba4-p116">上記のコマンドを使用して、組織内のすべてのメールボックス (または指定した受信者フィルターに一致するメールボックスのサブセット) を保持の対象にすると、コマンドを実行した時点で存在するメールボックスのみが保持の対象になります。後でメールボックスを新規作成する場合は、再度コマンドを実行して、その新しいメールボックスを保持の対象にする必要があります。頻繁にメールボックスを新規作成する場合は、必要な頻度にスケジュールしたタスクとしてコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p116">When you use the previous command to place a hold on all mailboxes in an organization (or a subset of mailboxes matching a specified recipient filter) only mailboxes that exist at the time that you run the command are placed on hold. If you create new mailboxes later, you have to run the command again to place the new mailboxes on hold. If you create new mailboxes often, you can run the command as a scheduled task as frequently as required.</span></span>
    
  - <span data-ttu-id="79ba4-p117">証拠保全上のすべてのメールボックスを配置すると、メールボックスのサイズが大幅に可能性があります。2013 の Exchange Server 組織で、組織の維持の要件を満たすために十分な記憶域を計画します。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p117">Placing all mailboxes on Litigation Hold can significantly impact mailbox sizes. In an Exchange Server 2013 organization, plan for adequate storage to meet your organization's preservation requirements.</span></span>
    
  - <span data-ttu-id="79ba4-p118">[回復可能なアイテム] フォルダーでは、フォルダー内のアイテムは、メールボックス格納域の制限をカウントしないように、独自の格納域の制限があります。説明したよう時間の長い期間のメールボックスのデータを保持するがユーザーのメールボックスの回復可能なアイテム] フォルダーの増加が発生し、保存します。対応するための増加 Exchange オンライン、回復可能なアイテム] フォルダーのクォータが自動的に増加 30 GB から 100 GB に証拠保全のメールボックスを配置すると。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p118">The Recoverable Items folder has its own storage limit, so items in the folder don't count towards the mailbox storage limit. As previously explained, preserving mailbox data for a long period of time will result in growth of the Recoverable Items folder in a user's mailbox and archive. To accommodate for this increase in Exchange Online, the quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when you place a mailbox on Litigation Hold.</span></span> 
    
    <span data-ttu-id="79ba4-p119">Exchange Server 2013 年、回復可能なアイテム] フォルダーの既定の記憶域の制限は、30 GB でもあります。上限に達したことがないことを確認するには、このフォルダーのサイズを定期的に監視することをお勧めします。詳細については、[回復可能なアイテム] フォルダー](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p119">In Exchange Server 2013, the default storage limit for the Recoverable Items folder is also 30 GB. We recommend that you periodically monitor the size of this folder to ensure it doesn't reach the limit. For more information, see [Recoverable Items Folder](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx).</span></span>
    
- <span data-ttu-id="79ba4-p120">すべてのメールボックスを保持の対象にする上記のコマンドでは、すべてのユーザーのメールボックスを返す受信者フィルターが使用されます。特定のメールボックスを訴訟ホールドの対象とするために、その他の受信者プロパティを使用して、 **Set-Mailbox** コマンドレットにパイプ処理できるそれらのメールボックスの一覧を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p120">The previous command to place a hold on all mailboxes uses a recipient filter that returns all user mailboxes. You can use other recipient properties to return a list of specific mailboxes that you can then pipe to the **Set-Mailbox** cmdlet to place a Litigation Hold on those mailboxes.</span></span> 
    
    <span data-ttu-id="79ba4-p121">以下に、 **Get-Mailbox** コマンドレットと **Get-Recipient** コマンドレットを使用して、共通のユーザー属性またはメールボックス属性に基づいてメールボックスのサブセットを返す例を示します。これらの例では、関連するメールボックスのプロパティ (  _CustomAttributeN_ や  _Department_ など) が入力されていることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p121">Here are some examples of using the **Get-Mailbox** and **Get-Recipient** cmdlets to return a subset of mailboxes based on common user or mailbox properties. These examples assume that relevant mailbox properties (such as  _CustomAttributeN_ or  _Department_) have been populated.</span></span>
    
  ```
  Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'CustomAttribute15 -eq "OneYearLitigationHold"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'Department -eq "HR"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'PostalCode -eq "98052"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'StateOrProvince -eq "WA"'
  ```

  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -ne "DiscoveryMailbox"}
  ```

    <span data-ttu-id="79ba4-p122">フィルターで他のユーザーのメールボックス プロパティを使用して、メールボックスを含めたり、除外したりすることができます。詳細については、「[Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79ba4-p122">You can use other user mailbox properties in a filter to include or exclude mailboxes. For details, see [Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx).</span></span>
    

