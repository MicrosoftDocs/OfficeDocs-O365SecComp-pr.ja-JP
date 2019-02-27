---
title: Office 365 への PST ファイルのインポートに関するよくあるご質問
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: '管理者にとってよく寄せられる質問。 office 365 インポートサービスを使用して、組織の PST ファイルを office 365 メールボックスにインポートする方法について説明します。 '
ms.openlocfilehash: bef9c9e80f4f4c8261e9c44ba201a978937e2841
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296880"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a><span data-ttu-id="3e29c-103">Office 365 への PST ファイルのインポートに関するよくあるご質問</span><span class="sxs-lookup"><span data-stu-id="3e29c-103">FAQ about importing PST files to Office 365</span></span>

<span data-ttu-id="3e29c-104">**この記事は、管理者を対象としています。PST ファイルを自分のメールボックスにインポートしますか?「 [Outlook .pst ファイルからメール、連絡先、予定表をインポートする](https://go.microsoft.com/fwlink/p/?LinkID=785075)」を参照してください。**|</span><span class="sxs-lookup"><span data-stu-id="3e29c-104">**This article is for administrators. Do you want to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span></span>
   
<span data-ttu-id="3e29c-p101">office 365 インポートサービスを使用して PST ファイルを office 365 メールボックスに一括インポートする方法についてよく寄せられる質問を以下に示します。pst ファイルのインポート方法の詳細については、「 [Office 2010 への pst ファイルのインポートの概要](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p101">Here are some frequently asked questions about using the Office 365 Import Service to bulk-import PST files to Office 365 mailboxes. For more information about how to import PST files, see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).</span></span>
  
## <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="3e29c-107">ネットワークアップロードを使用して PST ファイルをインポートする</span><span class="sxs-lookup"><span data-stu-id="3e29c-107">Using network upload to import PST files</span></span>

<span data-ttu-id="3e29c-108">詳細な手順については、「[ネットワークアップロードを使用して PST ファイルを Office 365 にインポート](use-network-upload-to-import-pst-files.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e29c-108">For step-by-step instructions, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
  
 <span data-ttu-id="3e29c-109">**Office 365 インポートサービスでインポートジョブを作成するには、どのようなアクセス許可が必要ですか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-109">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="3e29c-p102">PST ファイルを Office 365 メールボックスにインポートするには、Exchange Online でメールボックスのインポートのエクスポートの役割を割り当てられている必要があります。既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。[組織の管理] 役割グループに、メールボックスのインポートのエクスポートの役割を追加できます。または、新しい役割グループを作成し、メールボックスのインポートのエクスポート役割を割り当てて、自分または他のユーザーをメンバーとして追加することもできます。詳細については、「 [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)」の「役割グループに役割を追加する」または「役割グループを作成する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p102">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="3e29c-115">さらに、Office 365 セキュリティ&amp;コンプライアンスセンターでインポートジョブを作成するには、次のいずれかの条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e29c-115">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="3e29c-p103">Exchange Online では、メール受信者の役割が割り当てられている必要があります。既定では、この役割は組織の管理役割グループと受信者管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p103">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="3e29c-118">または</span><span class="sxs-lookup"><span data-stu-id="3e29c-118">Or</span></span>
    
- <span data-ttu-id="3e29c-119">Office 365 組織の全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e29c-119">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="3e29c-p104">Office 365 に PST ファイルをインポートするための特別な目的である Exchange Online に新しい役割グループを作成することを検討してください。PST ファイルのインポートに必要な最低限の特権レベルについては、メールボックスのインポートの役割とメール受信者の役割を新しい役割グループに割り当ててから、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p104">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="3e29c-122">**ネットワークアップロードを使用できる場所**</span><span class="sxs-lookup"><span data-stu-id="3e29c-122">**Where is network upload available?**</span></span>
  
<span data-ttu-id="3e29c-p105">ネットワークアップロードは現在、米国、カナダ、ブラジル、英国、フランス、ヨーロッパ、インド、東アジア、東南アジア、日本、韓国、およびオーストラリアで利用できます。ネットワークアップロードは、近日中により多くの地域で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p105">Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, France, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="3e29c-125">**ネットワークアップロードを使用して PST ファイルをインポートする場合の価格設定について**</span><span class="sxs-lookup"><span data-stu-id="3e29c-125">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="3e29c-126">PST ファイルのインポートにネットワークアップロードを使用することは無料です。</span><span class="sxs-lookup"><span data-stu-id="3e29c-126">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="3e29c-p106">これは、PST ファイルが Azure ストレージ領域から削除された後に、Office 365 管理センターでインポートジョブが完了したファイルの一覧に表示されなくなったことも意味します。[ **Office にデータをインポート**します] ページにインポートジョブが表示されている可能性がありますが、古いインポートジョブの詳細を表示すると、PST ファイルの一覧は空の場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p106">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Office 365 admin center. Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="3e29c-129">**Office 365 へのインポートでサポートされている PST ファイル形式のバージョン**</span><span class="sxs-lookup"><span data-stu-id="3e29c-129">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="3e29c-p107">PST ファイル形式には、ANSI と Unicode の2つのバージョンがあります。Unicode PST ファイル形式を使用するファイルをインポートすることをお勧めします。ただし、ANSI PST ファイル形式を使用するファイル (2 バイト文字セット (DBCS) を使用する言語など) は、Office 365 にインポートすることもできます。ANSI pst ファイルのインポートの詳細については、「[ネットワークアップロードを使用して組織の pst ファイルを Office 365 にインポートする](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)」の手順4を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p107">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 4 in [Use network upload to import your organization's PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="3e29c-134">また、Outlook 2007 以降のバージョンの PST ファイルを Office 365 にインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-134">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="3e29c-135">**PST ファイルを azure ストレージ領域にアップロードした後、削除される前に azure で保持されている期間はどのくらいか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-135">**After I upload my PST files to the Azure storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="3e29c-p108">network upload メソッドを使用して PST ファイルをインポートする場合は、 **ingestiondata**という名前の Azure blob コンテナーにアップロードします。セキュリティ&amp;コンプライアンスセンターの [**インポート**] ページで進行中のインポートジョブがない場合、Azure の**ingestiondata**コンテナーにあるすべての PST ファイルは、最新のインポートジョブがセキュリティ&amp;コンプライアンスセンターまた、セキュリティ&amp;コンプライアンスセンター (「ネットワークアップロードの手順」の手順 5) で新しいインポートジョブを作成してから、30日以内に PST ファイルを Azure にアップロードする必要があるということです。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p108">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**. If there are no import jobs in progress on the **Import** page in the Security &amp; Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security &amp; Compliance Center. That also means you have to create a new import job in the Security &amp; Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="3e29c-p109">これは、PST ファイルが Azure ストレージ領域から削除された後に、セキュリティ&amp;コンプライアンスセンターで完了したインポートジョブのファイル一覧に表示されなくなったことも意味します。インポートジョブはセキュリティ&amp;コンプライアンスセンターの [**インポート**] ページに表示されることがありますが、以前のインポートジョブの詳細を表示すると、PST ファイルの一覧は空になることがあります。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p109">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="3e29c-141">**PST ファイルをメールボックスにインポートするのにどのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="3e29c-141">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="3e29c-p110">ネットワークの容量によって異なりますが、通常は、組織の Azure ストレージ領域に各テラバイト (tb) のデータをアップロードするのに数時間かかります。pst ファイルが Azure ストレージ領域にコピーされると、1日あたり 24 GB 以上の速度で pst ファイルが Office 365 メールボックスにインポートされます。このレートがニーズに合わない場合は、電子メールデータを Office 365 に移行する他の方法を検討してください。詳細については、「[複数のメールアカウントを Office 365 に移行する方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p110">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. After the PST files are copied to the Azure storage area, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="3e29c-p111">異なる PST ファイルが別のターゲットメールボックスにインポートされた場合、インポートプロセスは並行して実行されます。つまり、PST/メールボックスの各ペアは同時にインポートされます。同様に、複数の PST ファイルが同じメールボックスにインポートされると、それらのファイルは同時にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p111">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="3e29c-148">**PST ファイルのインポート時にメッセージサイズに制限はありますか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-148">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="3e29c-p112">うん。PST ファイルに 150 MB を超えるメールボックスアイテムが含まれている場合、インポート処理中にそのアイテムはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p112">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="3e29c-151">**は、メッセージが送受信された日時、受信者のリスト、および PST ファイルが Office 365 メールボックスにインポートされるときに保持されるメッセージのプロパティです。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-151">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="3e29c-p113">うん。インポート処理中は、元のメッセージのメタデータは変更されません。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p113">Yes. The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="3e29c-154">**メールボックスにインポートする PST ファイルのフォルダー階層のレベル数には制限がありますか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-154">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="3e29c-p114">うん。300以上のネストされたフォルダーがある PST ファイルをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p114">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="3e29c-157">**ネットワークアップロードを使用して、Office 365 の非アクティブなメールボックスに PST ファイルをインポートできますか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-157">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="3e29c-158">はい、この機能は使用可能になりました。</span><span class="sxs-lookup"><span data-stu-id="3e29c-158">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="3e29c-159">**ネットワークアップロードを使用して、Exchange ハイブリッド展開のオンラインアーカイブメールボックスに PST ファイルをインポートできますか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-159">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="3e29c-160">はい、この機能は使用可能になりました。</span><span class="sxs-lookup"><span data-stu-id="3e29c-160">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="3e29c-161">**ネットワークアップロードを使用して、Exchange Online のパブリックフォルダーに PST ファイルをインポートできますか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-161">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="3e29c-162">いいえ。 PST ファイルをパブリックフォルダーにインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3e29c-162">No, you can't import PST files to public folders.</span></span>
  
## <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="3e29c-163">ドライブ配送を使用して PST ファイルをインポートする</span><span class="sxs-lookup"><span data-stu-id="3e29c-163">Using drive shipping to import PST files</span></span>

<span data-ttu-id="3e29c-164">詳細な手順については、「 [drive 送料を使用して PST ファイルを Office 365 にインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e29c-164">For step-by-step instructions, see [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).</span></span>
  
 <span data-ttu-id="3e29c-165">**Office 365 インポートサービスでインポートジョブを作成するには、どのようなアクセス許可が必要ですか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-165">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="3e29c-p115">PST ファイルを Office 365 メールボックスにインポートするには、メールボックスのインポートのエクスポート役割が割り当てられている必要があります。既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。[組織の管理] 役割グループに、メールボックスのインポートのエクスポートの役割を追加できます。または、新しい役割グループを作成し、メールボックスのインポートのエクスポート役割を割り当てて、自分または他のユーザーをメンバーとして追加することもできます。詳細については、「 [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)」の「役割グループに役割を追加する」または「役割グループを作成する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p115">You have to be assigned the Mailbox Import Export role to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="3e29c-171">さらに、Office 365 セキュリティ&amp;コンプライアンスセンターでインポートジョブを作成するには、次のいずれかの条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e29c-171">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="3e29c-p116">Exchange Online では、メール受信者の役割が割り当てられている必要があります。既定では、この役割は組織の管理役割グループと受信者管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p116">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="3e29c-174">または</span><span class="sxs-lookup"><span data-stu-id="3e29c-174">Or</span></span>
    
- <span data-ttu-id="3e29c-175">Office 365 組織の全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e29c-175">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="3e29c-p117">Office 365 に PST ファイルをインポートするための特別な目的である Exchange Online に新しい役割グループを作成することを検討してください。PST ファイルのインポートに必要な最低限の特権レベルについては、メールボックスのインポートの役割とメール受信者の役割を新しい役割グループに割り当ててから、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p117">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="3e29c-178">**ドライブ出荷の利用可能な場所**</span><span class="sxs-lookup"><span data-stu-id="3e29c-178">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="3e29c-p118">現時点では、ドライブの配送は米国、カナダ、ブラジル、英国、ヨーロッパ、インド、東アジア、東南アジア、日本、韓国共和国、オーストラリアで利用可能です。ドライブの配送は、近日中にさらに多くの地域で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p118">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Drive shipping will be available in more regions soon.</span></span>
  
 <span data-ttu-id="3e29c-181">**どのような商用ライセンス契約がドライブ出荷をサポートしていますか?**</span><span class="sxs-lookup"><span data-stu-id="3e29c-181">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="3e29c-p119">Office 365 に PST ファイルをインポートするためのドライブの送付は、Microsoft Enterprise アグリーメント (EA) を通じて利用できます。ドライブの送付は、Microsoft 製品およびサービス契約 (mpsa) 経由では利用できません。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p119">Drive shipping to import PST files to Office 365 is available through a Microsoft Enterprise Agreement (EA). Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="3e29c-184">**PST ファイルを Office 365 にインポートするためにドライブ出荷を使用する場合の価格設定について**</span><span class="sxs-lookup"><span data-stu-id="3e29c-184">**What is the pricing for using drive shipping to import PST files to Office 365?**</span></span>
  
<span data-ttu-id="3e29c-p120">ドライブの配送を使用して PST ファイルを Office 365 メールボックスにインポートするためのコストは、1 GB あたり $2 USD です。たとえば、1000 GB (1 TB) の PST ファイルを含むハードドライブを出荷した場合、コストは $2000 USD になります。パートナーと協力して、インポート料金を支払うことができます。パートナーの検索の詳細について[は、「Office 365 パートナーまたは販売店を検索](https://go.microsoft.com/fwlink/p/?LinkId=785197)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p120">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="3e29c-189">**ドライブの配送に対してサポートされているハードドライブの種類は何ですか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-189">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="3e29c-p121">Office 365 インポートサービスでの使用には、2.5 インチのソリッドステートドライブ (ssd) または2.5 または3.5 インチの SATA II/III 内部ハードドライブのみがサポートされています。ハードドライブは最大 10 TB まで使用できます。インポートジョブの場合、ハードドライブ上の最初のデータボリュームのみが処理されます。データボリュームは NTFS でフォーマットされている必要があります。データをハードドライブにコピーする場合は、2.5 インチ ssd または2.5 または3.5 インチ sata ii/iii コネクタを使用して直接接続できます。また、外部の2.5 インチ ssd または2.5 または3.5 インチの sata ii/iii USB アダプターを使用して外部に接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p121">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service. You can use hard drives up to 10 TB. For import jobs, only the first data volume on the hard drive will be processed. The data volume must be formatted with NTFS. When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3e29c-p122">組み込みの USB アダプターが付属している外部ハードドライブは、Office 365 インポートサービスではサポートされていません。さらに、外部ハードドライブの大文字と小文字の内部にあるディスクは使用できません。外部ハードドライブを送付しないでください。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p122">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="3e29c-198">**1つのインポートジョブに対して、何個のハードドライブを送付できますか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-198">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="3e29c-199">1つのインポートジョブに対して最大10台のハードドライブを出荷できます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-199">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="3e29c-200">**ハードドライブを出荷した後、Microsoft データセンターにアクセスするのにどのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="3e29c-200">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="3e29c-p123">これは、Microsoft データセンターに近接していることや、ハードドライブの出荷に使用された送付オプションの種類 (翌営業日配信、2日配信、または地上配信) など、いくつかの事柄によって決まります。多くの仕入れ先では、追跡番号を使用して、配信の状態を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p123">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="3e29c-203">**Microsoft データセンターにハードドライブが到着した後、PST ファイルを Azure にアップロードするのにどのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="3e29c-203">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="3e29c-p124">microsoft データセンターでハードドライブを受信した後は、7 ~ 10 営業日かかります。 PST ファイルは、組織の Microsoft Azure ストレージ領域にアップロードされます。PST ファイルは、 **ingestiondata**という名前の Azure blob コンテナーにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p124">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Microsoft Azure storage area for your organization. The PST files will be uploaded to a Azure blob container named **ingestiondata**.</span></span> 
  
 <span data-ttu-id="3e29c-206">**PST ファイルをメールボックスにインポートするのにどのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="3e29c-206">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="3e29c-p125">pst ファイルが Azure ストレージ領域にアップロードされると、Office 365 は pst ファイルのデータ (安全かつ安全な方法) を分析して、アイテムの保存期間と pst ファイルに含まれるさまざまなメッセージの種類を特定します。この分析が完了すると、PST ファイルのすべてのデータをインポートするか、インポートするデータを制御するフィルターを設定するかを選択できます。インポートジョブを開始すると、1日に 24 GB 以上の速度で PST ファイルが Office 365 メールボックスにインポートされます。このレートがニーズに合わない場合は、Office 365 に電子メールデータをインポートするためのその他の方法を検討することができます。詳細については、「[複数のメールアカウントを Office 365 に移行する方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p125">After the PST files are uploaded to the Azure storage area, Office 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files. When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported. After you start the import job, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="3e29c-p126">異なる PST ファイルが別のターゲットメールボックスにインポートされた場合、インポートプロセスは並行して実行されます。つまり、PST/メールボックスの各ペアは同時にインポートされます。同様に、複数の PST ファイルが同じメールボックスにインポートされると、それらのファイルは同時にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p126">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="3e29c-214">**Microsoft は、PST ファイルを azure にアップロードした後、削除される前に azure に保存されている期間はどのくらいか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-214">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="3e29c-215">**ingestiondata**という名前の blob コンテナー内の組織の Azure ストレージの場所にあるすべての PST ファイルは、最新のインポートジョブが、セキュリティ&amp;センターコンプライアンスセンターの [**インポート**] ページで作成されてから30日後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-215">All PST files in the Azure storage location for your organization (in blob container named **ingestiondata** ), are deleted 30 days after the most recent import job was created on the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="3e29c-p127">これは、PST ファイルが Azure ストレージ領域から削除された後に、セキュリティ&amp;コンプライアンスセンターで完了したインポートジョブのファイル一覧に表示されなくなったことも意味します。インポートジョブはセキュリティ&amp;コンプライアンスセンターの [**インポート**] ページに表示されることがありますが、以前のインポートジョブの詳細を表示すると、PST ファイルの一覧は空になることがあります。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p127">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="3e29c-218">**Office 365 へのインポートでサポートされている PST ファイル形式のバージョン**</span><span class="sxs-lookup"><span data-stu-id="3e29c-218">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="3e29c-p128">PST ファイル形式には、ANSI と Unicode の2つのバージョンがあります。Unicode PST ファイル形式を使用するファイルをインポートすることをお勧めします。ただし、ANSI PST ファイル形式を使用するファイル (2 バイト文字セット (DBCS) を使用する言語など) は、Office 365 にインポートすることもできます。ANSI pst ファイルのインポートの詳細については、「 [Use drive 送料 to Office 365 に PST ファイルをインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)」の手順3を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p128">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="3e29c-223">また、Outlook 2007 以降のバージョンの PST ファイルを Office 365 にインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-223">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="3e29c-224">**PST ファイルのインポート時にメッセージサイズに制限はありますか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-224">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="3e29c-p129">うん。PST ファイルに 150 MB を超えるメールボックスアイテムが含まれている場合、インポート処理中にそのアイテムはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p129">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="3e29c-227">**は、メッセージが送受信された日時、受信者のリスト、および PST ファイルが Office 365 メールボックスにインポートされるときに保持されるメッセージのプロパティです。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-227">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="3e29c-p130">うん。インポート処理中に元のメッセージのメタデータが変更されない</span><span class="sxs-lookup"><span data-stu-id="3e29c-p130">Yes. The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="3e29c-230">**メールボックスにインポートする PST ファイルのフォルダー階層のレベル数には制限がありますか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-230">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="3e29c-p131">うん。300以上のネストされたフォルダーがある PST ファイルをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="3e29c-233">**ドライブの配送を使用して、Office 365 の非アクティブなメールボックスに PST ファイルをインポートできますか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-233">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="3e29c-234">はい、この機能は使用可能になりました。</span><span class="sxs-lookup"><span data-stu-id="3e29c-234">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="3e29c-235">**ドライブの配送を使用して、Exchange ハイブリッド展開のオンラインアーカイブメールボックスに PST ファイルをインポートできますか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-235">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="3e29c-236">はい、この機能は使用可能になりました。</span><span class="sxs-lookup"><span data-stu-id="3e29c-236">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="3e29c-237">**ドライブの配送を使用して、Exchange Online のパブリックフォルダーに PST ファイルをインポートできますか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-237">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="3e29c-238">いいえ。 PST ファイルをパブリックフォルダーにインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3e29c-238">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="3e29c-239">**Microsoft は、自分に戻す前にハードドライブをワイプすることができますか?**</span><span class="sxs-lookup"><span data-stu-id="3e29c-239">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="3e29c-p132">いいえ。お客様に出荷する前に、Microsoft はハードドライブをワイプすることはできません。ハードドライブは、Microsoft によって受信されたときと同じ状態で返されます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p132">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="3e29c-242">**Microsoft は、自分のハードドライブを自分に出荷する代わりに、shred することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="3e29c-242">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="3e29c-p133">いいえ、Microsoft はハードドライブを破棄できません。ハードドライブは、Microsoft によって受信されたときと同じ状態で返されます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p133">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="3e29c-245">**返品出荷に対してサポートされている媒体使用サービスについて**</span><span class="sxs-lookup"><span data-stu-id="3e29c-245">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="3e29c-p134">米国またはヨーロッパのお客様の場合、Microsoft は FedEx を使用してハードドライブを返却しています。その他の地域の場合、Microsoft は DHL を使用します。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p134">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="3e29c-248">**返品送料のコストはどの程度ですか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-248">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="3e29c-p135">返品配送費用は、ハードドライブを送付した Microsoft データセンターへの近接度によって異なります。Microsoft は、FedEx または DHL アカウントを請求して、ハードドライブを返します。返品配送のコストは責任を負っています。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p135">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="3e29c-252">**FedEx custom 送料などのカスタムの宅配便サービスを使用して、Microsoft にハードドライブを送付できますか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-252">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="3e29c-253">はい。</span><span class="sxs-lookup"><span data-stu-id="3e29c-253">Yes.</span></span>
  
 <span data-ttu-id="3e29c-254">**別の国にハードドライブを送付する必要がある場合は、何が必要ですか。**</span><span class="sxs-lookup"><span data-stu-id="3e29c-254">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="3e29c-p136">Microsoft に出荷するハードドライブは、国際的な国境を越える必要がある場合があります。その場合は、該当する法律に従ってハードドライブとそれに含まれるデータがインポートまたはエクスポートされていることを確認する責任があります。ハードドライブを出荷する前に、アドバイザーに確認して、指定した Microsoft データセンターに、ドライブとデータが合法的に出荷されることを確認してください。これにより、適切なタイミングで Microsoft に到達していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3e29c-p136">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
