---
title: Office 365 に PST ファイルのインポートについてよく寄せられる質問
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: 'Office 365 のメールボックスに、organizaiton の PST ファイルをインポートするのには Office 365 にインポート サービスの使用についてよく寄せられる質問管理者向けです。 '
ms.openlocfilehash: 35080106f92b38e944ba31f74d5564e65ba1f752
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532827"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a><span data-ttu-id="50362-103">Office 365 に PST ファイルのインポートについてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="50362-103">FAQ about importing PST files to Office 365</span></span>

<span data-ttu-id="50362-104">**この資料では、管理者用です。PST ファイルを自分のメールボックスにインポートしますか。[インポート電子メール、連絡先、および Outlook の .pst ファイルから予定表](https://go.microsoft.com/fwlink/p/?LinkID=785075)を参照してください。**|</span><span class="sxs-lookup"><span data-stu-id="50362-104">**This article is for administrators. Do you want to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span></span>
   
<span data-ttu-id="50362-p101">ここでは、Office 365 にインポート サービスを使用して Office 365 のメールボックスを PST ファイルを一括インポートする方法のいくつかのよく寄せられる質問をします。PST ファイルをインポートする方法の詳細については、 [Office 365 に PST ファイルのインポートの概要](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50362-p101">Here are some frequently asked questions about using the Office 365 Import Service to bulk-import PST files to Office 365 mailboxes. For more information about how to import PST files, see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).</span></span>
  
## <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="50362-107">PST ファイルをインポートするのには、ネットワークのアップロードを使用してください。</span><span class="sxs-lookup"><span data-stu-id="50362-107">Using network upload to import PST files</span></span>

<span data-ttu-id="50362-108">手順については、 [Office 365 に PST ファイルをインポートするのにはアップロードの使用のネットワーク](use-network-upload-to-import-pst-files.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50362-108">For step-by-step instructions, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
  
 <span data-ttu-id="50362-109">**Office 365 にインポート サービスのインポート ジョブを作成するために必要なアクセス許可ですか。**</span><span class="sxs-lookup"><span data-stu-id="50362-109">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="50362-p102">メールボックスのエクスポートをインポートの役割を割り当てるには、Exchange オンライン Office 365 のメールボックスを PST ファイルをインポートするのにはする必要があります。既定では、この役割はありませんに割り当てられている役割グループは、Exchange オンライン。組織の管理役割グループに、メールボックスのインポート エクスポートの役割を追加できます。または、新しい役割グループを作成、メールボックスのインポート エクスポートの役割を割り当てるし、自分自身または他のユーザーをメンバーとして追加できます。詳細については、追加するロール グループのロール」を参照してください。 または、"グループを作成する役割」セクションの[管理役割グループの Exchange でオンライン](https://go.microsoft.com/fwlink/p/?LinkId=730688)にします。</span><span class="sxs-lookup"><span data-stu-id="50362-p102">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="50362-115">Office 365 のセキュリティのジョブのインポートを作成するのにはさらに、&amp;コンプライアンス センターは、次のいずれかを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="50362-115">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="50362-p103">メール受信者の役割を割り当てるには、Exchange オンラインする必要があります。既定では、この役割は組織の管理と受信者の管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="50362-p103">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="50362-118">または</span><span class="sxs-lookup"><span data-stu-id="50362-118">Or</span></span>
    
- <span data-ttu-id="50362-119">Office 365 の組織のグローバル管理者があります。</span><span class="sxs-lookup"><span data-stu-id="50362-119">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="50362-p104">Exchange Online の具体的には、Office 365 に PST ファイルをインポートする新しい役割グループを作成することを検討してください。PST ファイルをインポートするのには必要な特権を最低限のレベルで、新しい役割グループにメールボックスのエクスポートをインポートし、メール受信者の役割を割り当てるし、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="50362-p104">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="50362-122">**アップロードのネットワークが利用可能な場所**</span><span class="sxs-lookup"><span data-stu-id="50362-122">**Where is network upload available?**</span></span>
  
<span data-ttu-id="50362-p105">ネットワークのアップロードは、アメリカ合衆国、カナダ、ブラジル、英国、ヨーロッパ、インド、東アジア、東南アジア、日本、韓国、およびオーストラリアで現在利用できません。ネットワークのアップロードは近日より多くの地域で。</span><span class="sxs-lookup"><span data-stu-id="50362-p105">Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="50362-125">**ネットワークのアップロードを使用して、PST ファイルをインポートするための価格設定とは何ですか。**</span><span class="sxs-lookup"><span data-stu-id="50362-125">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="50362-126">ネットワークのアップロードを使用して、PST ファイルをインポートするのには、無料です。</span><span class="sxs-lookup"><span data-stu-id="50362-126">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="50362-p106">つまり、PST ファイルが、Azure のストレージ領域から削除されると、不要になった表示 Office 365 の管理ページで、インポートが完了したジョブのファイルの一覧にします。インポート ジョブが一覧に表示される**Office 365 へのデータのインポート**] ページは、古いインポート ジョブの詳細を表示すると、PST ファイルの一覧が空あります。</span><span class="sxs-lookup"><span data-stu-id="50362-p106">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Office 365 admin center. Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="50362-129">**PST ファイルの形式のバージョンは、Office 365 にインポートするためにサポートされてでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="50362-129">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="50362-p107">PST ファイルの形式の 2 つのバージョン: ANSI と Unicode です。Unicode PST ファイルの形式を使用するファイルをインポートすることをお勧めします。ただし、ANSI PST ファイル形式の 2 バイト文字を使用する言語などを使用しているファイルはセット (DBCS)、Office 365 にインポートすることもできます。ANSI PST ファイルをインポートする方法の詳細については、 [Office 365 の組織の PST ファイルをインポートするのにはアップロードの使用のネットワーク](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)上の手順 4 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50362-p107">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 4 in [Use network upload to import your organization's PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="50362-134">さらに、Outlook 2007 およびそれ以降のバージョンの PST ファイルは、Office 365 にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="50362-134">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="50362-135">**Azure のストレージ領域に、PST ファイルをアップロードすると後、どのくらいの時間、Azure でまでに保存されては削除ですか。**</span><span class="sxs-lookup"><span data-stu-id="50362-135">**After I upload my PST files to the Azure storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="50362-p108">PST ファイルをインポートするのには、ネットワークのアップロード方法を使用するときに**ingestiondata**という名前の Azure blob コンテナーにアップロードします。ジョブはありませんインポート進行中の [**インポート**] ページで、セキュリティの場合&amp;コンプライアンス センター) で、Azure の**ingestiondata**コンテナー内のすべての PST ファイルがセキュリティの&amp;コンプライアンス センターです。つまり、セキュリティに新しいインポート ジョブを作成する必要が&amp;Azure にファイルを PST のアップロードから 30 日以内コンプライアンス センター (ネットワークのアップロード手順の手順 5 で説明します)。</span><span class="sxs-lookup"><span data-stu-id="50362-p108">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**. If there are no import jobs in progress on the **Import** page in the Security &amp; Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security &amp; Compliance Center. That also means you have to create a new import job in the Security &amp; Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="50362-p109">つまり、PST ファイルが、Azure のストレージ領域から削除されると、不要になった表示、セキュリティのインポートが完了したジョブのファイルの一覧で、&amp;コンプライアンス センターです。インポート ジョブが一覧に表示されるセキュリティの [**インポート**] ページに&amp;コンプライアンス センターでは、PST ファイルの一覧があります空古いインポート ジョブの詳細を表示するとします。</span><span class="sxs-lookup"><span data-stu-id="50362-p109">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="50362-141">**メールボックスを PST ファイルをインポートするのにはどのくらい時間がかかりますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-141">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="50362-p110">ネットワークの容量によって異なりますが、組織の Azure ストレージ領域にアップロードするデータのテラバイト (TB) のそれぞれのいくつかの時間がかかります。PST ファイルが、Azure のストレージ領域にコピーされると、PST ファイルは、1 日あたり 24 GB 以上の速度で Office 365 のメールボックスにインポートされます。このレートは、お客様のニーズを満たしていない場合、は、Office 365 に移行するメール ・ データの他の方法を検討する可能性があります。詳細については、 [Office 365 に複数の電子メール アカウントを移行する方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50362-p110">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. After the PST files are copied to the Azure storage area, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="50362-p111">別の PST ファイルは、別のターゲット メールボックスにインポートする、インポート処理の場合は並列です。つまり、PST またはメールボックスの各ペアが同時にインポートされます。同様に、同じメールボックスに複数の PST ファイルを読み込む場合、同時にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="50362-p111">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="50362-148">**メッセージ サイズの制限の PST ファイルをインポートするときでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="50362-148">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="50362-p112">うん。PST ファイルには 150 MB を超えるメールボックスのアイテムが含まれている場合は、インポート処理中に項目がスキップされます。</span><span class="sxs-lookup"><span data-stu-id="50362-p112">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="50362-151">**など、メッセージを送信または受信されると、一連の受信者、およびその他のプロパティは、Office 365 のメールボックスに PST ファイルのインポート時に維持すると、メッセージのプロパティは**</span><span class="sxs-lookup"><span data-stu-id="50362-151">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="50362-p113">うん。元のメッセージのメタデータは、インポート処理中に変更されません。</span><span class="sxs-lookup"><span data-stu-id="50362-p113">Yes. The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="50362-154">**メールボックスにインポートする PST ファイルのフォルダー階層内のレベルの数に制限はありますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-154">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="50362-p114">うん。入れ子になったフォルダーの 300 以上のレベルを持つ PST ファイルをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="50362-p114">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="50362-157">**ネットワークのアップロードを使用して、Office 365 で、アクティブでないメールボックスを PST ファイルをインポートするのにはできますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-157">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="50362-158">はい、この機能は、使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="50362-158">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="50362-159">**Exchange ハイブリッド展開でのオンライン ・ アーカイブ メールボックスに PST ファイルをインポートするのにはネットワークのアップロードを使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-159">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="50362-160">はい、この機能は、使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="50362-160">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="50362-161">**オンライン Exchange 内のパブリック フォルダーを PST ファイルをインポートするのにはネットワークのアップロードを使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-161">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="50362-162">残念ですが、パブリック フォルダーを PST ファイルをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="50362-162">No, you can't import PST files to public folders.</span></span>
  
## <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="50362-163">ドライブの出荷を使用して、PST ファイルをインポートするのには</span><span class="sxs-lookup"><span data-stu-id="50362-163">Using drive shipping to import PST files</span></span>

<span data-ttu-id="50362-164">手順については、 [Office 365 に PST ファイルをインポートするのには配布のドライブを使用して](use-drive-shipping-to-import-pst-files-to-office-365.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="50362-164">For step-by-step instructions, see [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).</span></span>
  
 <span data-ttu-id="50362-165">**Office 365 にインポート サービスのインポート ジョブを作成するために必要なアクセス許可ですか。**</span><span class="sxs-lookup"><span data-stu-id="50362-165">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="50362-p115">Office 365 のメールボックスを PST ファイルをインポートするのには、メールボックスのエクスポートをインポートの役割を割り当てる必要があります。既定では、この役割はありませんに割り当てられている役割グループは、Exchange オンライン。組織の管理役割グループに、メールボックスのインポート エクスポートの役割を追加できます。または、新しい役割グループを作成、メールボックスのインポート エクスポートの役割を割り当てるし、自分自身または他のユーザーをメンバーとして追加できます。詳細については、追加するロール グループのロール」を参照してください。 または、"グループを作成する役割」セクションの[管理役割グループの Exchange でオンライン](https://go.microsoft.com/fwlink/p/?LinkId=730688)にします。</span><span class="sxs-lookup"><span data-stu-id="50362-p115">You have to be assigned the Mailbox Import Export role to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="50362-171">Office 365 のセキュリティのジョブのインポートを作成するのにはさらに、&amp;コンプライアンス センターは、次のいずれかを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="50362-171">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="50362-p116">メール受信者の役割を割り当てるには、Exchange オンラインする必要があります。既定では、この役割は組織の管理と受信者の管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="50362-p116">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="50362-174">または</span><span class="sxs-lookup"><span data-stu-id="50362-174">Or</span></span>
    
- <span data-ttu-id="50362-175">Office 365 の組織のグローバル管理者があります。</span><span class="sxs-lookup"><span data-stu-id="50362-175">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="50362-p117">Exchange Online の具体的には、Office 365 に PST ファイルをインポートする新しい役割グループを作成することを検討してください。PST ファイルをインポートするのには必要な特権を最低限のレベルで、新しい役割グループにメールボックスのエクスポートをインポートし、メール受信者の役割を割り当てるし、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="50362-p117">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="50362-178">**場所はドライブ配布可能ですか。**</span><span class="sxs-lookup"><span data-stu-id="50362-178">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="50362-p118">ドライブの出荷は、米国、カナダ、ブラジル、英国、ヨーロッパ、インド、東アジア、東南アジア、日本、韓国、およびオーストラリアで現在利用可能です。ドライブの出荷は近日より多くの地域で。</span><span class="sxs-lookup"><span data-stu-id="50362-p118">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Drive shipping will be available in more regions soon.</span></span>
  
 <span data-ttu-id="50362-181">**どのような商用のライセンス契約では、ドライブの出荷をサポートしますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-181">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="50362-p119">配布の PST ファイルを Office 365 にインポートするのにはドライブは、Microsoft マイクロソフトエンタープライズ契約 (EA) を使用することができます。ドライブの出荷は、マイクロソフトの製品およびサービス契約 (MPSA) を使用できません。</span><span class="sxs-lookup"><span data-stu-id="50362-p119">Drive shipping to import PST files to Office 365 is available through a Microsoft Enterprise Agreement (EA). Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="50362-184">**配布の PST ファイルを Office 365 にインポートするのにはドライブを使用するための価格設定とは何ですか。**</span><span class="sxs-lookup"><span data-stu-id="50362-184">**What is the pricing for using drive shipping to import PST files to Office 365?**</span></span>
  
<span data-ttu-id="50362-p120">ドライブの出荷を使用して、Office 365 のメールボックスを PST ファイルをインポートするためのコストは、$2 米ドル 1 GB のデータです。1,000 GB (1 TB) を PST ファイルを格納しているハード ドライブを出荷する場合、コストは $2,000 USD です。インポートの手数料をお支払いするパートナーを使用することができます。パートナーを検索する方法の詳細については[、Office 365 のパートナーまたは販売店を検索](https://go.microsoft.com/fwlink/p/?LinkId=785197)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50362-p120">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="50362-189">**ドライブの出荷は、どのような種類のハード ドライブがサポートされているでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="50362-189">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="50362-p121">2.5 インチのみソリッド ・ ステート ・ ドライブを (Ssd) または 2.5 または 3.5 インチ SATA II と III の内部ハード ドライブが Office 365 のインポート サービスで使用するためにサポートされています。ハード ドライブを使用することができます最大 10 TB です。インポート ジョブの場合は、ハード ドライブの最初のデータ量のみが処理されます。データ ボリュームは、NTFS でフォーマットする必要があります。ハード ドライブにデータをコピーするときに 2.5 インチ SSD を使用して直接接続することができます 2.5 または 3.5 インチの SATA II と III のコネクタ、または外部の 2.5 インチ SSD を使用して外部にまたは 2.5 または 3.5 インチの SATA II と III の USB アダプターを接続することができます。</span><span class="sxs-lookup"><span data-stu-id="50362-p121">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service. You can use hard drives up to 10 TB. For import jobs, only the first data volume on the hard drive will be processed. The data volume must be formatted with NTFS. When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="50362-p122">組み込みの USB アダプターに付属している外付けのハード ドライブは、Office 365 のインポート サービスでサポートされていません。さらに、大文字と小文字の外付けハード ドライブ内のディスクは使用できません。外付けハード ドライブを出荷しないしてください。</span><span class="sxs-lookup"><span data-stu-id="50362-p122">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="50362-198">**1 回のインポート ジョブには、ハード ドライブの数を出荷してでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="50362-198">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="50362-199">1 回のインポート ジョブの 10 個のハード ドライブの最大を出荷することができます。</span><span class="sxs-lookup"><span data-stu-id="50362-199">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="50362-200">**ハード ドライブを出荷した後は時間をマイクロソフトのデータ ・ センターを取得するでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="50362-200">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="50362-p123">いくつか、マイクロソフトのデータ ・ センターの近くなどに依存して、配送オプションの種類を使用してハード ドライブなど、翌日配送、2 日間の配信、地上配信を出荷します。ほとんどの運送会社では、配信のステータスを追跡するために追跡番号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="50362-p123">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="50362-203">**ハード ドライブは、マイクロソフトのデータ ・ センターに到着すた後、所要時間はどれに Azure に PST ファイルをアップロードするか。**</span><span class="sxs-lookup"><span data-stu-id="50362-203">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="50362-p124">マイクロソフトのデータ ・ センターで、ハード ディスク ドライブが受信されると、組織の Microsoft Azure のストレージ領域を PST ファイルをアップロードするのには、7 ~ 10 営業日間かかります。PST ファイルは、 **ingestiondata**という名前の Azure blob コンテナーにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="50362-p124">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Microsoft Azure storage area for your organization. The PST files will be uploaded to a Azure blob container named **ingestiondata**.</span></span> 
  
 <span data-ttu-id="50362-206">**メールボックスを PST ファイルをインポートするのにはどのくらい時間がかかりますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-206">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="50362-p125">PST ファイルは、Azure のストレージ領域にアップロードした後 Office 365 は、アイテムと PST ファイルに含まれている別のメッセージの種類の保存期間を識別する (安全性とセキュリティで保護された形で) PST ファイル内のデータを分析します。この分析が完了すると、PST ファイル内のすべてのデータをインポートするオプションがあります。 または、インポートされたデータを取得するフィルターの設定を制御します。インポート ジョブを起動した後、PST ファイルは、1 日あたり 24 GB 以上の速度で Office 365 のメールボックスにインポートされます。このレートは、お客様のニーズを満たしていない場合、は、Office 365 のメール ・ データをインポートするその他の方法を検討する可能性があります。詳細については、 [Office 365 に複数の電子メール アカウントを移行する方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50362-p125">After the PST files are uploaded to the Azure storage area, Office 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files. When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported. After you start the import job, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="50362-p126">別の PST ファイルは、別のターゲット メールボックスにインポートする、インポート処理の場合は並列です。つまり、PST またはメールボックスの各ペアが同時にインポートされます。同様に、同じメールボックスに複数の PST ファイルを読み込む場合、同時にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="50362-p126">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="50362-214">**マイクロソフトでは、Azure に PST ファイルをアップロード後、どのくらいの時間、Azure でまでに保存されては削除しますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-214">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="50362-215">Azure ストレージの場所内のすべての PST ファイル (blob コンテナーに**ingestiondata**という名前の)、組織のセキュリティの [**インポート**] ページで、最新のインポート ジョブを作成した後、30 日間削除&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="50362-215">All PST files in the Azure storage location for your organization (in blob container named **ingestiondata** ), are deleted 30 days after the most recent import job was created on the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="50362-p127">つまり、PST ファイルが、Azure のストレージ領域から削除されると、不要になった表示、セキュリティのインポートが完了したジョブのファイルの一覧で、&amp;コンプライアンス センターです。インポート ジョブが一覧に表示されるセキュリティの [**インポート**] ページに&amp;コンプライアンス センターでは、PST ファイルの一覧があります空古いインポート ジョブの詳細を表示するとします。</span><span class="sxs-lookup"><span data-stu-id="50362-p127">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="50362-218">**PST ファイルの形式のバージョンは、Office 365 にインポートするためにサポートされてでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="50362-218">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="50362-p128">PST ファイルの形式の 2 つのバージョン: ANSI と Unicode です。Unicode PST ファイルの形式を使用するファイルをインポートすることをお勧めします。ただし、ANSI PST ファイル形式の 2 バイト文字を使用する言語などを使用しているファイルはセット (DBCS)、Office 365 にインポートすることもできます。ANSI PST ファイルをインポートする方法の詳細については、 [Office 365 に PST ファイルをインポートするのには配布のドライブを使用して](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)手順 3 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50362-p128">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="50362-223">さらに、Outlook 2007 およびそれ以降のバージョンの PST ファイルは、Office 365 にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="50362-223">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="50362-224">**メッセージ サイズの制限の PST ファイルをインポートするときでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="50362-224">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="50362-p129">うん。PST ファイルには 150 MB を超えるメールボックスのアイテムが含まれている場合は、インポート処理中に項目がスキップされます。</span><span class="sxs-lookup"><span data-stu-id="50362-p129">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="50362-227">**など、メッセージを送信または受信されると、一連の受信者、およびその他のプロパティは、Office 365 のメールボックスに PST ファイルのインポート時に維持すると、メッセージのプロパティは**</span><span class="sxs-lookup"><span data-stu-id="50362-227">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="50362-p130">うん。インポート処理中に元のメッセージのメタデータは変更されません。</span><span class="sxs-lookup"><span data-stu-id="50362-p130">Yes. The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="50362-230">**メールボックスにインポートする PST ファイルのフォルダー階層内のレベルの数に制限はありますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-230">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="50362-p131">うん。入れ子になったフォルダーの 300 以上のレベルを持つ PST ファイルをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="50362-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="50362-233">**ドライブの出荷を使用して、Office 365 で、アクティブでないメールボックスを PST ファイルをインポートするのにはできますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-233">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="50362-234">はい、この機能は、使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="50362-234">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="50362-235">**Exchange ハイブリッド展開でのオンライン ・ アーカイブ メールボックスに PST ファイルをインポートするのにはドライブの配布を使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-235">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="50362-236">はい、この機能は、使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="50362-236">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="50362-237">**オンライン Exchange 内のパブリック フォルダーを PST ファイルをインポートするのにはドライブの配布を使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-237">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="50362-238">残念ですが、パブリック フォルダーを PST ファイルをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="50362-238">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="50362-239">**いただくようお願いを出荷する前に、ハード ドライブのワイプを Microsoft できますでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="50362-239">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="50362-p132">残念ですが、マイクロソフトはそれらを顧客に出荷する前にハード ドライブを消去することはできません。ハード ドライブはマイクロソフトが受信したときと同じ状態にするに返されます。</span><span class="sxs-lookup"><span data-stu-id="50362-p132">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="50362-242">**私に出荷するのではなくハード ドライブを Microsoft シュレッダ処理できますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-242">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="50362-p133">残念ですが、マイクロソフトでは、ハード ディスクを破棄できません。ハード ドライブはマイクロソフトが受信したときと同じ状態にするに返されます。</span><span class="sxs-lookup"><span data-stu-id="50362-p133">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="50362-245">**返品の送付先にどのような宅配サービスがサポートされますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-245">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="50362-p134">米国またはヨーロッパの顧客の場合、マイクロソフトは、ハード ドライブを取得するのには宅配便を使用します。他のすべての地域では、マイクロソフトは、DHL を使用します。</span><span class="sxs-lookup"><span data-stu-id="50362-p134">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="50362-248">**戻り値の送料は?**</span><span class="sxs-lookup"><span data-stu-id="50362-248">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="50362-p135">ハード ディスクが同梱されているマイクロソフトのデータ ・ センターへの近接によって、送料が異なりますが返されます。ハード ドライブを取得するのには、FedEx、DHL のアカウントに請求させていただきます。返品送料のコストは、ユーザーの責任です。</span><span class="sxs-lookup"><span data-stu-id="50362-p135">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="50362-252">**マイクロソフトにハード ドライブを出荷するのに FedEx カスタム送付先住所などのカスタムの宅配便配送サービスを使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-252">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="50362-253">はい。</span><span class="sxs-lookup"><span data-stu-id="50362-253">Yes.</span></span>
  
 <span data-ttu-id="50362-254">**他の国の私のハード ドライブを出荷する必要がある、する場合はありますを行う必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="50362-254">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="50362-p136">マイクロソフトに出荷するハード ディスク ドライブは、国境を通過する必要があります。大文字と小文字の場合は、自分が責任をハード ディスク ドライブとそれに含まれるデータはインポートまたはエクスポートされた適用法に準拠を保証するためです。ハード ドライブを出荷する前にこと、ドライブとデータが合法的に出荷する指定した Microsoft のデータ センターを確認するのには、アドバイザーに確認してください。これは適切なタイミングでマイクロソフトに到達することを確認するのには役立ちます。</span><span class="sxs-lookup"><span data-stu-id="50362-p136">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
