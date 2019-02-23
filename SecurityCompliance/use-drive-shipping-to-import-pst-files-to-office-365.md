---
title: ドライブの送付を使用して組織の PST ファイルを Office 365 にインポートする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
description: '管理者向け: pst ファイルをハードドライブにコピーしてから Microsoft に配布することによって、組織の pst ファイルを Office 365 メールボックスに一括インポートする方法について説明します。 '
ms.openlocfilehash: 44ca6e58d9273c73a807ba0b186c47721949c6f6
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223686"
---
# <a name="use-drive-shipping-to-import-your-organization-pst-files-to-office-365"></a><span data-ttu-id="c262d-103">ドライブの送付を使用して組織の PST ファイルを Office 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="c262d-103">Use drive shipping to import your organization PST files to Office 365</span></span>

<span data-ttu-id="c262d-104">**この記事は、管理者を対象としています。PST ファイルを自分のメールボックスにインポートしようとしていますか?「 [Outlook .pst ファイルからメール、連絡先、予定表をインポートする](https://go.microsoft.com/fwlink/p/?LinkID=785075)」を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="c262d-104">**This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span></span>
   
<span data-ttu-id="c262d-p101">Office 365 インポートサービスとドライブ配送を使用して、PST ファイルをユーザーのメールボックスに一括インポートします。ドライブの出荷とは、PST ファイルをハードディスクドライブにコピーし、ドライブを Microsoft に物理的に輸送することを意味します。microsoft がハードドライブを受け取ると、データセンターの担当者は、そのデータをハードドライブから microsoft クラウドのストレージ領域にコピーします。次に、インポートするデータを制御するフィルターを設定することにより、実際にターゲットメールボックスにインポートされた PST データをトリミングする機会があります。インポートジョブを開始すると、インポートサービスはストレージ領域の PST データをユーザーのメールボックスにインポートします。ドライブの送付を使用して PST ファイルをユーザーのメールボックスにインポートする方法は、組織の電子メールを Office 365 に移行する方法の1つです。</span><span class="sxs-lookup"><span data-stu-id="c262d-p101">Use the Office 365 Import service and drive shipping to bulk-import PST files to user mailboxes. Drive shipping means that you copy the PST files to a hard disk drive and then physically ship the drive to Microsoft. When Microsoft receives your hard drive, data center personnel will copy the data from the hard drive to a storage area in the Microsoft cloud. Then you have the opportunity to trim the PST data that's actually imported to the target mailboxes by setting filters that control what data gets imported. After you start the import job, the Import service imports the PST data from the storage area to user mailboxes. Using drive shipping to import PST files to user mailboxes is one way to migrate your organization's email to Office 365.</span></span>
  
<span data-ttu-id="c262d-111">ドライブの配送を使用して、Office 365 メールボックスに PST ファイルをインポートするために必要な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c262d-111">Here are the steps required to use drive shipping to import PST files to Office 365 mailboxes:</span></span>
  
[<span data-ttu-id="c262d-112">手順 1: セキュリティで保護されたストレージキーおよび PST インポートツールをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="c262d-112">Step 1: Download the secure storage key and PST Import tool</span></span>](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[<span data-ttu-id="c262d-113">手順 2: PST ファイルをハードドライブにコピーする</span><span class="sxs-lookup"><span data-stu-id="c262d-113">Step 2: Copy the PST files to the hard drive</span></span>](#step-2-copy-the-pst-files-to-the-hard-drive)

[<span data-ttu-id="c262d-114">手順 3: PST インポートのマッピングファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="c262d-114">Step 3: Create the PST Import mapping file</span></span>](#step-3-create-the-pst-import-mapping-file)

[<span data-ttu-id="c262d-115">手順 4:Office 365 で PST インポート ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="c262d-115">Step 4: Create a PST Import job in Office 365</span></span>](#step-4-create-a-pst-import-job-in-office-365)

[<span data-ttu-id="c262d-116">手順 5:Microsoft にハード ドライブを送付する</span><span class="sxs-lookup"><span data-stu-id="c262d-116">Step 5: Ship the hard drive to Microsoft</span></span>](#step-5-ship-the-hard-drive-to-microsoft)

[<span data-ttu-id="c262d-117">手順 6: データをフィルター処理し、PST インポートジョブを開始する</span><span class="sxs-lookup"><span data-stu-id="c262d-117">Step 6: Filter data and start the PST Import job</span></span>](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> <span data-ttu-id="c262d-p102">セキュリティで保護されたストレージキーとインポートツールを読み込むには、手順1を実行する必要があります。これらの手順を実行した後、ハードドライブを Microsoft に出荷するたびに、手順 2 ~ 手順6に従います。</span><span class="sxs-lookup"><span data-stu-id="c262d-p102">You have to perform Step 1 once to down load the secure storage key and the import tool. After you perform these steps, follow Step 2 through Step 6 each time you want to ship a hard drive to Microsoft.</span></span> 
  
<span data-ttu-id="c262d-120">ドライブの送付を使用して pst ファイルを Office 365 にインポートする方法についてよく寄せられる質問については、「[ドライブ出荷を使用して pst ファイルをインポートする](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-120">For frequently asked questions about using drive shipping to import PST files to Office 365, see [FAQs for using drive shipping to import PST files](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="c262d-121">始める前に</span><span class="sxs-lookup"><span data-stu-id="c262d-121">Before you begin</span></span>

- <span data-ttu-id="c262d-p103">PST ファイルを Office 365 メールボックスにインポートするには、Exchange Online でメールボックスのインポートのエクスポートの役割を割り当てられている必要があります。既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。[組織の管理] 役割グループに、メールボックスのインポートのエクスポートの役割を追加できます。または、新しい役割グループを作成し、メールボックスのインポートのエクスポート役割を割り当てて、自分をメンバーとして追加することもできます。詳細については、「 [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688)」の「役割グループに役割を追加する」または「役割グループを作成する」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p103">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
    
    <span data-ttu-id="c262d-127">さらに、Office 365 セキュリティ&amp;コンプライアンスセンターでインポートジョブを作成するには、次のいずれかの条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c262d-127">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
    
  - <span data-ttu-id="c262d-p104">Exchange Online では、メール受信者の役割が割り当てられている必要があります。既定では、この役割は組織の管理役割グループと受信者管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p104">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="c262d-130">または</span><span class="sxs-lookup"><span data-stu-id="c262d-130">Or</span></span>
    
  - <span data-ttu-id="c262d-131">Office 365 組織の全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c262d-131">You have to be a global administrator in your Office 365 organization.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c262d-p105">Office 365 に PST ファイルをインポートするための特別な目的である Exchange Online に新しい役割グループを作成することを検討してください。PST ファイルのインポートに必要な最低限の特権レベルについては、メールボックスのインポートの役割とメール受信者の役割を新しい役割グループに割り当ててから、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p105">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
- <span data-ttu-id="c262d-p106">コピーする PST ファイルは、組織内のファイルサーバーまたは共有フォルダーのハードドライブに格納する必要があります。手順2では、このファイルサーバーまたは共有フォルダーに格納されている PST ファイルをハードドライブにコピーする Azure インポートエクスポートツール (waimportexport) を実行します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p106">You need to store the PST files that you want to copy to a hard drive on a file server or shared folder in your organization. In Step 2, you'll run the Azure Import Export tool (WAImportExport.exe) that will copy the PST files that are stored on this file server or shared folder to the hard drive.</span></span>
    
- <span data-ttu-id="c262d-p107">Office 365 インポートサービスでの使用には、2.5 インチのソリッドステートドライブ (ssd) または2.5 または3.5 インチの SATA II/III 内部ハードドライブのみがサポートされています。ハードドライブは最大 10 TB まで使用できます。インポートジョブの場合、ハードドライブ上の最初のデータボリュームのみが処理されます。データボリュームは NTFS でフォーマットされている必要があります。データをハードドライブにコピーする場合は、2.5 インチ ssd または2.5 または3.5 インチ sata ii/iii コネクタを使用して直接接続できます。また、外部の2.5 インチ ssd または2.5 または3.5 インチの sata ii/iii USB アダプターを使用して外部に接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p107">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service. You can use hard drives up to 10 TB. For import jobs, only the first data volume on the hard drive will be processed. The data volume must be formatted with NTFS. When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c262d-p108">組み込みの USB アダプターが付属している外部ハードドライブは、Office 365 インポートサービスではサポートされていません。さらに、外部ハードドライブの大文字と小文字の内部にあるディスクは使用できません。外部ハードドライブを送付しないでください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p108">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives.</span></span> 
  
- <span data-ttu-id="c262d-p109">PST ファイルのコピー先のハードドライブは、BitLocker で暗号化する必要があります。手順2で実行した waimportexport .exe ツールは、BitLocker のセットアップに役立ちます。また、microsoft データセンターの担当者が、PST ファイルを microsoft クラウドの Azure ストレージ領域にアップロードするために使用する BitLocker 暗号化キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p109">The hard drive that you copy the PST files to must be encrypted with BitLocker. The WAImportExport.exe tool that you run in Step 2 will help you set up BitLocker. It also generates a BitLocker encryption key that Microsoft data center personnel will use to access the drive to upload the PST files to the Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="c262d-p110">ドライブの配送は、Microsoft エンタープライズアグリーメント (EA) を通じて利用できます。ドライブの送付は、Microsoft 製品およびサービス契約 (mpsa) 経由では利用できません。</span><span class="sxs-lookup"><span data-stu-id="c262d-p110">Drive shipping is available through a Microsoft Enterprise Agreement (EA). Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
    
- <span data-ttu-id="c262d-p111">ドライブの配送を使用して PST ファイルを Office 365 メールボックスにインポートするためのコストは、1 GB あたり $2 米ドルです。たとえば、PST ファイルの 1000 GB (1tb) を含むハードドライブを出荷した場合、コストは $2000 USD になります。パートナーと協力して、インポート料金を支払うことができます。パートナーの検索の詳細について[は、「Office 365 パートナーまたは販売店を検索](https://go.microsoft.com/fwlink/p/?LinkId=785197)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p111">The cost to import PST files to Office 365 mailboxes using drive shipping is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
    
- <span data-ttu-id="c262d-153">お客様またはお客様の組織は、FedEx または DHL のアカウントを持っている必要があります。 </span><span class="sxs-lookup"><span data-stu-id="c262d-153">You or your organization must have an account with FedEx or DHL.</span></span>
    
  - <span data-ttu-id="c262d-154">米国、ブラジル、ヨーロッパの組織には、FedEx アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="c262d-154">Organizations in the United States, Brazil, and Europe must have FedEx accounts.</span></span>
    
  - <span data-ttu-id="c262d-155">東アジア、東南アジア、日本、韓国共和国、オーストラリアの組織には、DHL アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="c262d-155">Organizations in East Asia, Southeast Asia, Japan, Republic of Korea, and Australia must have DHL accounts.</span></span>
    
    <span data-ttu-id="c262d-156">Microsoft はこのアカウントを使用 (または課金) して、ハード ドライブをお客様に返却します。 </span><span class="sxs-lookup"><span data-stu-id="c262d-156">Microsoft will use (and charge) this account to return the hard drive back to you.</span></span>
    
- <span data-ttu-id="c262d-p112">Microsoft に送付するハード ドライブは、国境を超えて送付される場合があります。この場合は、お客様にはハード ドライブとそれに含まれるデータが適用法に従って輸入または輸出されることを保証する責任があります。ハード ドライブを送付する前に、指定された Microsoft データ センターにハード ドライブとデータを合法的に送付できるか法律顧問と一緒に確認してください。こうすることで、適切なタイミングで確実に Microsoft に届きます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p112">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the identified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
    
- <span data-ttu-id="c262d-p113">この手順では、セキュリティで保護されたストレージキーと BitLocker 暗号化キーのコピーと保存を行います。パスワードやその他のセキュリティ関連の情報を保護するように、これらのキーを保護するための注意事項を必ず実行してください。たとえば、パスワードで保護された Microsoft Word 文書に保存するか、暗号化された USB ドライブに保存することができます。これらのキーの例については、「 [More information](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p113">This procedure involves copying and saving a secure storage key and a BitLocker encryption key. Be sure to take precautions to protect these keys like you would protect passwords or other security-related information. For example, you might save them to a password-protected Microsoft Word document or save them to an encrypted USB drive. See the [More information](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) section for an example of these keys.</span></span> 
    
- <span data-ttu-id="c262d-p114">PST ファイルが Office 365 メールボックスにインポートされると、メールボックスの保持ホールドの設定は無期限に有効になります。これは、メールボックスに割り当てられたアイテム保持ポリシーは、保存機能を無効にするか、保留を解除する日付を設定するまで処理されないことを意味します。なぜこれを行うのでしょうか。メールボックスにインポートされたメッセージが古くなっている場合は、メールボックスに対して構成されたアイテム保持ポリシーに基づいて保持期間が経過したために、削除 (パージ) される可能性があります。メールボックスの保存機能を有効にすると、メールボックスの所有者は新しくインポートされたメッセージを管理することができ、メールボックスの保存期間の設定を変更する時間を与えることができます。保持ホールドの管理に関する提案については、「 [More information](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p114">After PST files are imported to an Office 365 mailbox, the retention hold setting for the mailbox is turned on for an indefinite duration. This means that the retention policy assigned to the mailbox won't be processed until you turn off the retention hold or set a date to turn off the hold. Why do we do this? If messages imported to a mailbox are old, they might be permanently deleted (purged) because their retention period has expired based on the retention settings configured for the mailbox. Placing the mailbox on retention hold will give the mailbox owner time to manage these newly-imported messages or give you time to change the retention settings for the mailbox. See the [More information](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) section for suggestions about managing the retention hold.</span></span> 
    
- <span data-ttu-id="c262d-p115">既定では、Office 365 メールボックスで受信できる最大メッセージサイズは 35 MB です。これは、メールボックスの*MaxReceiveSize*プロパティの既定値が 35 MB に設定されているためです。ただし、Office 365 の最大メッセージ受信サイズの制限は 150 MB です。そのため、35 mb を超えるアイテムを含む PST ファイルをインポートすると、Office 365 インポートサービスによって、ターゲットメールボックスの*MaxReceiveSize*プロパティの値が 150 mb に自動的に変更されます。これにより、150 MB までのメッセージをユーザーのメールボックスにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p115">By default, the maximum message size that can be received by an Office 365 mailbox is 35 MB. That's because the default value for the  *MaxReceiveSize*  property for a mailbox is set to 35 MB. However, the limit for the maximum message receive size in Office 365 is 150 MB. So if you import a PST file that contains an item larger than 35 MB, the Office 365 Import service we will automatically change the value of the  *MaxReceiveSize*  property on the target mailbox to 150 MB. This allows messages up to 150 MB to be imported to user mailboxes.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="c262d-176">メールボックスのメッセージ受信サイズを特定するには、Exchange Online PowerShell で次のコマンドを`Get-Mailbox <user mailbox> | FL MaxReceiveSize`実行します。</span><span class="sxs-lookup"><span data-stu-id="c262d-176">To identify the message receive size for a mailbox, you can run this command in Exchange Online PowerShell:  `Get-Mailbox <user mailbox> | FL MaxReceiveSize`.</span></span> 
  
- <span data-ttu-id="c262d-p116">Office 365 の非アクティブなメールボックスに PST ファイルをインポートすることができます。これを行うには、PST インポートマッピングファイルの`Mailbox`パラメーターに非アクティブなメールボックスの GUID を指定します。詳細については[、「ステップ 3: PST インポートのマッピングファイルを作成](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p116">You can import PST files to an inactive mailbox in Office 365. You do this by specifying the GUID of the inactive mailbox in the  `Mailbox` parameter in the PST Import mapping file. See [Step 3: Create the PST Import mapping file](use-drive-shipping-to-import-pst-files-to-office-365.md#step3) for more information.</span></span> 
    
- <span data-ttu-id="c262d-p117">Exchange ハイブリッド展開では、プライマリメールボックスがオンプレミスであるユーザーのクラウドベースのアーカイブメールボックスに PST ファイルをインポートできます。これを行うには、PST インポートマッピングファイルで以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p117">In an Exchange hybrid deployment, you can import PST files to a cloud-based archive mailbox for a user whose primary mailbox is on-premises. You do this by doing the following in the PST Import mapping file:</span></span>
    
  - <span data-ttu-id="c262d-182">`Mailbox`パラメーターに、ユーザーの社内メールボックスの電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c262d-182">Specify the email address for the user's on-premises mailbox in the  `Mailbox` parameter.</span></span> 
    
  - <span data-ttu-id="c262d-183">`IsArchive`パラメーターに**TRUE**の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c262d-183">Specify the **TRUE** value in the  `IsArchive` parameter.</span></span> 
    
    <span data-ttu-id="c262d-184">詳細については[、「ステップ 3: PST インポートのマッピングファイルを作成](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-184">See [Step 3: Create the PST Import mapping file](use-drive-shipping-to-import-pst-files-to-office-365.md#step3) for more information.</span></span> 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a><span data-ttu-id="c262d-185">手順 1: セキュリティで保護されたストレージキーおよび PST インポートツールをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="c262d-185">Step 1: Download the secure storage key and PST Import tool</span></span>

<span data-ttu-id="c262d-186">最初の手順は、セキュリティで保護されたストレージキーとツールをダウンロードすることで、手順2で使用して PST ファイルをハードドライブにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c262d-186">The first step is to download the secure storage key and the tool and that you will use in Step 2 to copy PST files to the hard drive.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c262d-p118">drive 送付方法を使用して PST ファイルを正常にインポートするには、Azure インポート/エクスポートツールのバージョン 1 (WAimportExportV1) を使用する必要があります。Azure インポート/エクスポートツールのバージョン2はサポートされていません。これを使用すると、インポートジョブのハードドライブが正しく準備されない可能性があります。必ず、この手順の手順に従って、セキュリティ&amp;コンプライアンスセンターから Azure インポート/エクスポートツールをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p118">You have to use Azure Import/Export tool version 1 (WAimportExportV1) to successfully import PST files by using the drive shipping method. Version 2 of the Azure Import/Export tool isn't supported and using it will result in incorrectly preparing the hard drive for the import job. Be sure to download the Azure Import/Export tool from the Security &amp; Compliance Center by following the procedures in this step.</span></span> 
  
1. <span data-ttu-id="c262d-190">に[https://protection.office.com/](https://protection.office.com/)移動し、Office 365 組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="c262d-190">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="c262d-191">セキュリティ&amp; /コンプライアンスセンターの左側のウィンドウで、[**データガバナンス** \>の**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-191">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c262d-192">前述したように、セキュリティ&amp;コンプライアンスセンターの [**インポート**] ページにアクセスするには、適切なアクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c262d-192">As previously stated, you have to be assigned the appropriate permissions to access the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
3. <span data-ttu-id="c262d-193">[**インポート**] ページで、 ![[追加](media/ITPro-EAC-AddIcon.gif) ] アイコン [**新しいインポートジョブ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-193">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
4. <span data-ttu-id="c262d-p119">[ジョブのインポート] ウィザードで、PST インポートジョブの名前を入力し、[**次へ**] をクリックします。小文字、数字、ハイフン、およびアンダースコアを使用してください。名前には、大文字を使用したり、スペースを含めたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c262d-p119">In the import job wizard, type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="c262d-197">[**インポートジョブの種類の選択**] ページで、[**ハードドライブを物理的な場所の1つに出荷する**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-197">On the **Choose import job type** page, click **Ship hard drives to one of our physical locations** and then click **Next**.</span></span>
    
    ![ドライブ送付インポートジョブを作成するには、[ハードドライブを物理的な場所の1つに出荷] をクリックします。](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. <span data-ttu-id="c262d-199">[**データのインポート**] ページで、次の2つの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c262d-199">On the **Import data** page, do the following two things:</span></span> 
    
    ![セキュリティで保護されたストレージキーをコピーして、[データのインポート] ページに Azure インポートエクスポートツールをダウンロードする](media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    <span data-ttu-id="c262d-p120">a 手順2で、[**セキュリティで保護されたストレージキーをコピー**] をクリックします。ストレージキーが表示されたら、[**クリップボードにコピー** ] をクリックして貼り付け、ファイルに保存し、後でアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="c262d-p120">a. In step 2, click **Copy the secure storage key**. After the storage key is displayed, click **Copy to clipboard** and then paste it and save it to a file so you can access it later.</span></span>
    
    <span data-ttu-id="c262d-p121">b. 手順3で、azure インポート/エクスポート**ツール**をダウンロードしてインストールし、azure インポート/エクスポート (バージョン 1) ツールをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c262d-p121">b. In step 3, **Download the Azure Import/Export tool** to download and install the Azure Import/Export (version 1) tool.</span></span>
    
    - <span data-ttu-id="c262d-206">ポップアップウィンドウで、[名前を付け\*\*\*\* \> **て**保存] をクリックして、WaImportExportV1 ファイルをローカルコンピューター上のフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="c262d-206">In the pop-up window, click **Save** \> **Save as** to save the WaImportExportV1.zip file to a folder on your local computer.</span></span> 
    
    - <span data-ttu-id="c262d-207">WaImportExportV1 ファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="c262d-207">Extract the WaImportExportV1.zip file.</span></span>
    
7. <span data-ttu-id="c262d-208">ウィザードを閉じるには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-208">Click **Cancel** to close the wizard.</span></span> 
    
    <span data-ttu-id="c262d-209">手順4でインポートジョブを\*\*\*\* 作成するときに、 &amp;セキュリティコンプライアンスセンターの [インポート] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="c262d-209">You'll come back to the **Import** page in the Security &amp; Compliance Center when you create the import job in Step 4.</span></span> 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a><span data-ttu-id="c262d-210">手順 2: PST ファイルをハードドライブにコピーする</span><span class="sxs-lookup"><span data-stu-id="c262d-210">Step 2: Copy the PST files to the hard drive</span></span>

<span data-ttu-id="c262d-p122">次の手順では、waimportexport .exe ツールを使用して PST ファイルをハードドライブにコピーします。このツールは、BitLocker を使用してハードドライブを暗号化し、pst をハードドライブにコピーし、コピープロセスに関する情報を格納するジャーナルファイルを作成します。この手順を完了するには、組織内のファイル共有またはファイルサーバーに PST ファイルを配置する必要があります。これは、次の手順でソースディレクトリと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p122">The next step is to use the WAImportExport.exe tool to copy PST files to the hard drive. This tool encrypts the hard drive with BitLocker, copies the PSTs to the hard drive, and creates a journal file that stores information about the copy process. To complete this step, the PST files have to be located in a file share or file server in your organization. This is known as the source directory in the following procedure.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c262d-p123">最初にハードドライブに対して waimportexport .exe ツールを実行した後は、その後毎回別の構文を使用する必要があります。この構文については、この手順のステップ4で、PST ファイルをハードドライブにコピーする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p123">After you run the WAImportExport.exe tool the first time for a hard drive, you have to use a different syntax each time after that. This syntax is explained in step 4 of this procedure to copy PST files to the hard drive.</span></span> 
  
1. <span data-ttu-id="c262d-217">ローカル コンピューター上でコマンド プロンプトを開く。</span><span class="sxs-lookup"><span data-stu-id="c262d-217">Open a Command Prompt on your local computer.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c262d-p124">管理者としてコマンド プロンプトを実行する場合 (コマンド プロンプトを開く際に [管理者として実行] を選択する)、コマンド プロンプト ウィンドウにエラー メッセージが表示されます。これにより、WAImportExport.exe ツールの実行に関する問題のトラブルシューティングが行えます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p124">If you run the command prompt as an administrator (by selecting "Run as administrator" when you open it) error messages will be displayed in the command prompt window. This can help you troubleshoot problems running the WAImportExport.exe tool.</span></span> 
  
2. <span data-ttu-id="c262d-220">手順 1 で WAImportExport ツールをインストールしたディレクトリに移動する。</span><span class="sxs-lookup"><span data-stu-id="c262d-220">Go to the directory where you installed the WAImportExport.exe tool in Step 1.</span></span>
    
3. <span data-ttu-id="c262d-221">初めて WAImportExport.exe を使用してハード ドライブに PST ファイルをコピーする場合は、次のコマンドを実行する。</span><span class="sxs-lookup"><span data-stu-id="c262d-221">Run the following command the first time that you use the WAImportExport.exe to copy PST files to a hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>
    ```

    <span data-ttu-id="c262d-222">次の表は、パラメーターとそれに必要な値を説明したものです。</span><span class="sxs-lookup"><span data-stu-id="c262d-222">The following table describes the parameters and their required values.</span></span>
    
    |<span data-ttu-id="c262d-223">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c262d-223">**Parameter**</span></span>|<span data-ttu-id="c262d-224">**説明**</span><span class="sxs-lookup"><span data-stu-id="c262d-224">**Description**</span></span>|<span data-ttu-id="c262d-225">**例**</span><span class="sxs-lookup"><span data-stu-id="c262d-225">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `/j:` <br/> |<span data-ttu-id="c262d-p125">ジャーナル ファイルの名前を指定します。このファイルは、WAImportExport.exe ツールがあるフォルダーと同じフォルダーに保存されます。Microsoft に送付するハード ドライブごとに 1 つのジャーナル ファイルが必要です。WAImportTool.exe を実行して PST ファイルをハード ドライブにコピーするたびに、そのドライブのジャーナル ファイルに情報が追加されます。 
</span><span class="sxs-lookup"><span data-stu-id="c262d-p125">Specifies the name of the journal file. This file is saved to the same folder where the WAImportExport.exe tool is located. Each hard drive you ship to Microsoft must have one journal file. Every time you run the WAImportTool.exe to copy PST files to a hard drive, information will be appended to the journal file for that drive.</span></span>  <br/> <span data-ttu-id="c262d-230">microsoft データセンター担当者は、ジャーナルファイルの情報を使用して、手順4で作成したインポートジョブにハードドライブを関連付け、PST ファイルを Microsoft クラウドの Azure ストレージ領域にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c262d-230">Microsoft data center personnel will use the information in the journal file to associate the hard drive with the import job that you create in Step 4, and to upload the PST files to the Azure storage area in the Microsoft cloud.</span></span>  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |<span data-ttu-id="c262d-231">ローカル コンピューターに接続されている場合は、ハード ドライブのドライブ文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="c262d-231">Specifies the drive letter of the hard drive when it's connected to your local computer.</span></span>  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |<span data-ttu-id="c262d-p126">コピー セッションの名前を指定します。WAImportExport.exe ツールを実行してファイルをハード ドライブにコピーするたびに、セッションが定義されます。PST ファイルは、このパラメーターで指定されたセッション名の名前が付けられたフォルダーにコピーされます。 </span><span class="sxs-lookup"><span data-stu-id="c262d-p126">Specifies the name of the copy session. A session is defined as each time you run the WAImportExport.exe tool to copy files to the hard drive. The PST files are copied to a folder named with the session name specified by this parameter.</span></span>  <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |<span data-ttu-id="c262d-p127">セッション中にコピーされる PST ファイルを含む組織内のソースディレクトリを指定します。このパラメーターの値は二重引用符 ("") で囲むようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p127">Specifies the source directory in your organization that contains the PST files that will be copied during the session. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |<span data-ttu-id="c262d-p128">pst がアップロードされる Microsoft クラウドの Azure ストレージ領域で、宛先ディレクトリを指定します。値`ingestiondata/`を使用する必要があります。このパラメーターの値は二重引用符 ("") で囲むようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p128">Specifies the destination directory in the Azure storage area in the Microsoft cloud where the PSTs will be uploaded. You must use the value  `ingestiondata/`. Be sure to surround the value of this parameter with double-quotation marks (" ").  </span></span><br/> <span data-ttu-id="c262d-p129">必要に応じて、このパラメーターの値に追加のファイルパスを追加することもできます。たとえば、ハードドライブ上のソースディレクトリのファイルパス (URL 形式に変換される) を使用できます。これは、 `/srcdir:`パラメーターで指定されています。たとえば、 `\\FILESERVER01\PSTs`はに`FILESERVER01/PSTs`変更されます。この場合も、ファイルパスに含める`ingestiondata`必要があります。そのため、この例では、 `/dstdir:`パラメーターの値は`"ingestiondata/FILESERVER01/PSTs"`になります。</span><span class="sxs-lookup"><span data-stu-id="c262d-p129">Optionally, you can also add an additional file path to the value of this parameter. For example, you can use the file path of the source directory on the hard drive (converted to a URL format) , which is specified in the  `/srcdir:` parameter. For example,  `\\FILESERVER01\PSTs` is changed to  `FILESERVER01/PSTs`. In this case, you still must include  `ingestiondata` in the file path. So in this example, the value for the  `/dstdir:` parameter would be  `"ingestiondata/FILESERVER01/PSTs"`.  </span></span><br/> <span data-ttu-id="c262d-245">同じファイル名を持つ pst ファイルがある場合は、追加のファイルパスを追加する理由の1つとして挙げられます。</span><span class="sxs-lookup"><span data-stu-id="c262d-245">One reason to add the additional file path is if you have PSTs files with the same filename.</span></span>  <br/> <span data-ttu-id="c262d-p130">> [!NOTE]> オプションのパス名を指定した場合、pst ファイルの名前空間には、[Azure storage] 領域にアップロードされた後に、pst ファイルのパス名と名前が含まれます。たとえば、 `FILESERVER01/PSTs/annb.pst`のようになります。pathname を指定しない場合、名前空間は PST ファイル名のみになります。例`annb.pst`を示します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p130">> [!NOTE]> If you include the optional pathname, the namespace for a PST file after it's uploaded to the Azure storage area will include the pathname and the name of the PST file; for example,  `FILESERVER01/PSTs/annb.pst`. If you don't include a pathname, the namespace is only the PST filename; for example  `annb.pst`.</span></span>           | `/dstdir:"ingestiondata/"` <br/> <span data-ttu-id="c262d-248">または</span><span class="sxs-lookup"><span data-stu-id="c262d-248">Or</span></span>  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |<span data-ttu-id="c262d-p131">手順1で取得したストレージアカウントキーを指定します。このパラメーターの値は二重引用符 ("") で囲むようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p131">Specifies the storage account key that you obtained in Step 1. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/encrypt` <br/> |このスイッチは、ハード ドライブの BitLocker を有効にします。このパラメーターは、WAImportExport.exe ツールを初めて実行する際に必要です。  <br/> <span data-ttu-id="c262d-p133">BitLocker 暗号化キーは、ジャーナルファイルと、 `/logfile:`パラメーターを使用した場合に作成されるログファイルにコピーされます。前述のように、ジャーナルファイルは、waimportexport .exe ツールが配置されているのと同じフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p133">The BitLocker encryption key is copied to the journal file and the log file that is created if you use the  `/logfile:` parameter. As previously explained, the journal file is saved to the same folder where the WAImportExport.exe tool is located.  </span></span><br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |<span data-ttu-id="c262d-p134">このオプションパラメーターは、ログファイルを保存するフォルダーを指定します。指定しない場合、ログファイルは、waimportexport .exe ツールが配置されているのと同じフォルダーに保存されます。このパラメーターの値は二重引用符 ("") で囲むようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p134">This optional parameter specifies a folder to save log files to. If not specified, the log files are save to the same folder where the WAImportExport.exe tool is located. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    <span data-ttu-id="c262d-258">各パラメーターの実際の値を使用する WAImportExport.exe ツールの構文の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c262d-258">Here's an example of the syntax for the WAImportExport.exe tool using actual values for each parameter:</span></span>
    
    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    <span data-ttu-id="c262d-p135">コマンドを実行すると、ハード ドライブへの PST ファイルのコピーの進行状況を示す状態メッセージが表示されます。最終の状態メッセージは、正常にコピーされたファイルの合計数を示しています。 </span><span class="sxs-lookup"><span data-stu-id="c262d-p135">After you run the command, status messages are displayed that show the progress of copying the PST files to the hard drive. A final status message shows the total number of files that were successfully copied.</span></span>
    
4. <span data-ttu-id="c262d-261">このコマンドを、WAImportExport.ext ツールを 2 回目以降に実行するたびに実行して、PST ファイルを同じハード ドライブにコピーする。</span><span class="sxs-lookup"><span data-stu-id="c262d-261">Run this command each subsequent time you run the WAImportExport.ext tool to copy PST files to the same hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 
    ```

    <span data-ttu-id="c262d-262">以降のセッションを実行して PST ファイルを同じハード ドライブにコピーするための構文の例は、以下の通りです。  </span><span class="sxs-lookup"><span data-stu-id="c262d-262">Here's an example of the syntax for running subsequent sessions to copy PST files to the same hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a><span data-ttu-id="c262d-263">手順 3: PST インポートのマッピングファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="c262d-263">Step 3: Create the PST Import mapping file</span></span>

<span data-ttu-id="c262d-p136">Microsoft データセンターの担当者がハードドライブから Azure ストレージ領域に pst ファイルをアップロードした後、インポートサービスは、pst インポートマッピングファイル (csv) ファイル内の情報を使用して、pst をメールボックスを特定するユーザーを指定します。ファイルはにインポートされます。PST インポートジョブを作成する場合は、次の手順でこの CSV ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p136">After Microsoft data center personnel upload the PST files from the hard drive to the Azure storage area, the Import service will use the information in the PST Import mapping file, which is a comma separated value (CSV) file, that specifies which user mailboxes the PST files will be imported to. You will submit this CSV file in the next step when you create a PST Import job.</span></span>
  
1. <span data-ttu-id="c262d-266">[PST インポートのマッピングファイルのコピーをダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=544717)します。</span><span class="sxs-lookup"><span data-stu-id="c262d-266">[Download a copy of the PST Import mapping file](https://go.microsoft.com/fwlink/p/?LinkId=544717).</span></span>
    
2. <span data-ttu-id="c262d-p137">CSV ファイルを開くか、ローカル コンピューターに保存します。次の例は、完了した PST インポートのマッピング ファイル (メモ帳で開いた) を示しています。Microsoft Excel を使って CSV ファイルを編集するほうが、はるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="c262d-p137">Open or save the CSV file to your local computer. The following example shows a completed PST Import mapping file (opened in NotePad). It's much easier to use Microsoft Excel to edit the CSV file.</span></span>

    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,FILESERVER01/PSTs,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,,,,,
    ```

    <span data-ttu-id="c262d-p138">CSV ファイルの最初の行、つまりヘッダー行には、pst ファイルをユーザーメールボックスにインポートするために pst インポートサービスによって使用されるパラメーターが一覧表示されます。各パラメーター名はコンマで区切ります。ヘッダー行の下の各行は、特定のメールボックスに PST ファイルをインポートするためのパラメーター値を表します。ハードドライブにコピーされた PST ファイルごとに1行が必要です。マッピングファイルのプレースホルダーデータを実際のデータに置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p138">The first row, or header row, of the CSV file lists the parameters that will be used by the PST Import service to import the PST files to user mailboxes. Each parameter name is separated by a comma. Each row under the header row represents the parameter values for importing a PST file to a specific mailbox. You will need a row for each PST file that was copied to the hard drive. Be sure to replace the placeholder data in the mapping file with your actual data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c262d-275">SharePoint パラメーターなど、ヘッダー行は何も変更しないでください。これらは PST インポートの処理中、無視されます。</span><span class="sxs-lookup"><span data-stu-id="c262d-275">Don't change anything in the header row, including the SharePoint parameters; they will be ignored during the PST Import process.</span></span> 
  
3. <span data-ttu-id="c262d-276">次の表の情報を使って、必要な情報を含む CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c262d-276">Use the information in the following table to populate the CSV file with the required information.</span></span>
    
    |<span data-ttu-id="c262d-277">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c262d-277">**Parameter**</span></span>|<span data-ttu-id="c262d-278">**説明**</span><span class="sxs-lookup"><span data-stu-id="c262d-278">**Description**</span></span>|<span data-ttu-id="c262d-279">**例**</span><span class="sxs-lookup"><span data-stu-id="c262d-279">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `Workload` <br/> |<span data-ttu-id="c262d-p139">データのインポート先となる Office 365 サービスを指定します。PST ファイルをユーザーのメールボックスにインポート`Exchange`するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p139">Specifies the Office 365 service that data will be imported to. To import PST files to user mailboxes, use  `Exchange`.  </span></span><br/> | `Exchange` <br/> |
    | `FilePath` <br/> | <span data-ttu-id="c262d-282">ハードドライブが Microsoft に出荷されたときに PST ファイルがコピーされる Azure ストレージ領域内のフォルダーの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c262d-282">Specifies the folder location in the Azure storage area that PST files will be copied to when the hard drive is shipped to Microsoft.</span></span>  <br/>  <span data-ttu-id="c262d-283">CSV ファイルのこの列に追加する内容は、前の手順で`/dstdir:`パラメーターに指定した内容によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c262d-283">What you add in this column in the CSV file depends on what you specified in for the  `/dstdir:` parameter in the previous step.</span></span>  <br/>  <span data-ttu-id="c262d-284">を使用`/dstdir:"ingestiondata/"`した場合は、CSV ファイルでこのパラメーターを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="c262d-284">If you used  `/dstdir:"ingestiondata/"`, then leave this parameter blank in the CSV file.</span></span>  <br/>  <span data-ttu-id="c262d-p140">`/dstdir:`パラメーターの値の省略可能なパス名 (たとえば`/dstdir:"ingestiondata/FILESERVER01/PSTs"`、) を指定した場合、CSV ファイルのこのパラメーターにはその pathname ("ingestiondata" を含まない) を使用します。このパラメーターの値は、大文字と小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p140">If you included an optional pathname for the value of the  `/dstdir:` parameter (for example,  `/dstdir:"ingestiondata/FILESERVER01/PSTs"`, then use that pathname (not including "ingestiondata") for this parameter in the CSV file. The value for this parameter is case sensitive.  </span></span><br/>  <span data-ttu-id="c262d-p141">どちらの方法\*\* でも、 `FilePath`パラメーターの値に "ingestiondata" を含めないでください。このパラメーターを空白のままにしておくか、省略可能なパス名のみを指定します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p141">Either way,  *don't*  include "ingestiondata" in the value for the  `FilePath` parameter. Leave this parameter blank or specify only the optional pathname.  </span></span><br/> <span data-ttu-id="c262d-p142">> [!IMPORTANT]> ファイルパス名の大文字と小文字は、前の手順で`/dstdir:`パラメーターで指定したものと同じである必要があります。たとえば、前の手順で`"ingestiondata/FILESERVER01/PSTs"`サブフォルダー名を使用していて、CSV ファイル`fileserver01/psts`の`FilePath`パラメーターで使用した場合、PST ファイルのインポートは失敗します。両方のインスタンスで同じケースを使用してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p142">> [!IMPORTANT]>  The case for the file path name must be the same case that you specified in the  `/dstdir:` parameter in the previous step . For example, if you used  `"ingestiondata/FILESERVER01/PSTs"` for the subfolder name in the previous step, but then used  `fileserver01/psts` in the  `FilePath` parameter in CSV file, the import for the PST file will fail. Be sure to use the same case in both instances.</span></span>           |<span data-ttu-id="c262d-292">(空白)</span><span class="sxs-lookup"><span data-stu-id="c262d-292">(leave blank)</span></span>  <br/> <span data-ttu-id="c262d-293">または</span><span class="sxs-lookup"><span data-stu-id="c262d-293">Or</span></span>  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |<span data-ttu-id="c262d-p143">ユーザーメールボックスにインポートされる PST ファイルの名前を指定します。このパラメーターの値は、大文字と小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p143">Specifies the name of the PST file that will be imported to the user mailbox. The value for this parameter is case sensitive.  </span></span><br/> <span data-ttu-id="c262d-p144">> [!IMPORTANT]> CSV ファイルの pst ファイル名の大文字と小文字は、手順2で Azure ストレージの場所にアップロードされた pst ファイルと同じである必要があります。たとえば、CSV ファイルの`annb.pst` `Name`パラメーターでを使用していて、実際の pst ファイルの名前が`AnnB.pst`である場合、その pst ファイルのインポートは失敗します。CSV ファイルの pst の名前では、実際の pst ファイルと同じ大文字と小文字が使用されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p144">> [!IMPORTANT]> The case for the PST file name in the CSV file must be the same as the PST file that was uploaded to the Azure storage location in Step 2. For example, if you use  `annb.pst` in the  `Name` parameter in the CSV file, but the name of the actual PST file is  `AnnB.pst`, the import for that PST file will fail. Be sure that the name of the PST in the CSV file uses the same case as the actual PST file.</span></span>           | `annb.pst` <br/> |
    | `Mailbox` <br/> |<span data-ttu-id="c262d-p145">PST ファイルのインポート先となるメールボックスの電子メールアドレスを指定します。pst インポートサービスは、pst ファイルのパブリックフォルダーへのインポートをサポートしていないため、パブリックフォルダーを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c262d-p145">Specifies the email address of the mailbox that the PST file will be imported to. Note that you can't specify a public folder because the PST Import Service doesn't support importing PST files to public folders.  </span></span><br/> <span data-ttu-id="c262d-p146">非アクティブなメールボックスに PST ファイルをインポートするには、このパラメーターのメールボックス GUID を指定する必要があります。この GUID を取得するには、Exchange Online で次の PowerShell コマンドを実行します。`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid`</span><span class="sxs-lookup"><span data-stu-id="c262d-p146">To import a PST file to an inactive mailbox, you have to specify the mailbox GUID for this parameter. To obtain this GUID, run the following PowerShell command in Exchange Online:  `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid`</span></span> <br/> <span data-ttu-id="c262d-p147">> [!NOTE]> 場合によっては、1つのメールボックスがアクティブなメールボックスで、もう一方のメールボックスが削除済み (または非アクティブ) 状態になっているメールボックスが同じメールアドレスを持つ複数のメールボックスが存在することがあります。このような状況では、PST ファイルをインポートするメールボックスを一意に識別するために、メールボックスの GUID を指定する必要があります。この GUID をアクティブなメールボックスに対して取得するには`Get-Mailbox <identity of active mailbox> | FL Guid`、次の PowerShell コマンドを実行します。回復可能な削除 (または非アクティブ) のメールボックスの GUID を取得する`Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`には、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p147">> [!NOTE]> In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox <identity of active mailbox> | FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command:  `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`.</span></span>           | `annb@contoso.onmicrosoft.com` <br/> <span data-ttu-id="c262d-307">または</span><span class="sxs-lookup"><span data-stu-id="c262d-307">Or</span></span>  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | <span data-ttu-id="c262d-p148">PST ファイルをユーザーのアーカイブ メールボックスにインポートするかどうかを指定します。次のような 2 つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="c262d-p148">Specifies whether or not to import the PST file to the user's archive mailbox. There are two options:  </span></span><br/> <span data-ttu-id="c262d-310">**FALSE**PST ファイルをユーザーのプライマリメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="c262d-310">**FALSE** Imports the PST file to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="c262d-p149">**TRUE**PST ファイルをユーザーのアーカイブメールボックスにインポートします。これ[は、ユーザーのアーカイブメールボックスが有効になっ](enable-archive-mailboxes.md)ていることを前提としています。このパラメーターをに`TRUE`設定し、ユーザーのアーカイブメールボックスが有効になっていない場合、そのユーザーのインポートは失敗します。1人のユーザーに対してインポートが失敗した場合 (アーカイブが有効になっておら`TRUE`ず、このプロパティがに設定されているため)、インポートジョブの他のユーザーに影響が及ぶことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p149">**TRUE** Imports the PST file to the user's archive mailbox. This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). If you set this parameter to  `TRUE` and the user's archive mailbox isn't enabled, the import for that user will fail. Note that if an import fails for one user (because their archive isn't enabled and this property is set to  `TRUE`), the other users in the import job won't be affected.  </span></span><br/>  <span data-ttu-id="c262d-315">このパラメーターを空白のままにすると、PST ファイルがユーザーのプライマリメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="c262d-315">If you leave this parameter blank, the PST file is imported to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="c262d-316">**注:** プライマリメールボックスがオンプレミスであるユーザーのクラウドベースのアーカイブメールボックスに PST ファイルをインポートするには`TRUE` 、このパラメーターに対してを指定して、 `Mailbox`パラメーターのユーザーの社内メールボックスの電子メールアドレスを指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="c262d-316">**Note:** To import a PST file to a cloud-based archive mailbox for a user whose primary mailbox is on-premises, just specify  `TRUE` for this parameter and specify the email address for the user's on-premises mailbox for the  `Mailbox` parameter.</span></span>  <br/> | `FALSE` <br/> <span data-ttu-id="c262d-317">または</span><span class="sxs-lookup"><span data-stu-id="c262d-317">Or</span></span>  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | <span data-ttu-id="c262d-318">PST ファイルのインポート先メールボックスフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c262d-318">Specifies the mailbox folder that the PST file is imported to.</span></span>  <br/>  <span data-ttu-id="c262d-319">このパラメーターを空白のままにした場合、PST はメールボックスのルートレベル (受信トレイフォルダーとその他の既定のメールボックスフォルダーと同じレベル) にある**インポート**された新しいフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="c262d-319">If you leave this parameter blank, the PST will be imported to a new folder named **Imported** located at the root level of the mailbox (the same level as the Inbox folder and the other default mailbox folders).</span></span>  <br/>  <span data-ttu-id="c262d-320">を指定`/`した場合、PST ファイル内のアイテムは、ユーザーの受信トレイフォルダーに直接インポートされます。</span><span class="sxs-lookup"><span data-stu-id="c262d-320">If you specify  `/`, items in the PST file will be imported directly in to the user's Inbox folder.</span></span>  <br/>  <span data-ttu-id="c262d-p150">を指定`/<foldername>`した場合、PST ファイルのアイテムは、 \* \<foldername\> \*という名前のフォルダーにインポートされます。たとえば、を使用`/ImportedPst`すると、アイテムは**ImportedPst**という名前のフォルダーにインポートされます。このフォルダーは、受信トレイフォルダーと同じレベルにあるユーザーのメールボックスに配置されます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p150">If you specify  `/<foldername>`, items in the PST file will be imported to a folder named  *\<foldername\>*  . For example, if you use  `/ImportedPst`, items would be imported to a folder named **ImportedPst**. This folder will be located in the user's mailbox at the same level as the Inbox folder.  </span></span><br/> |<span data-ttu-id="c262d-324">(空白)</span><span class="sxs-lookup"><span data-stu-id="c262d-324">(leave blank)</span></span>  <br/> <span data-ttu-id="c262d-325">または</span><span class="sxs-lookup"><span data-stu-id="c262d-325">Or</span></span>  <br/>  `/` <br/> <span data-ttu-id="c262d-326">または</span><span class="sxs-lookup"><span data-stu-id="c262d-326">Or</span></span>  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |<span data-ttu-id="c262d-p151">このオプションパラメーターは、ANSI ファイル形式で PST ファイルをインポートするために使用するコードページの数値を指定します。このパラメーターは、中国語、日本語、および韓国語 (CJK) の組織から PST ファイルをインポートするために使用されます。これらの言語では、通常、文字エンコードに2バイト文字セット (DBCS) を使用します。メールボックスフォルダー名に DBCS を使用する言語の PST ファイルをインポートするためにこのパラメーターを使用していない場合は、インポート後にフォルダー名が正しくないことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="c262d-p151">This optional parameter specifies a numeric value for the code page to use for importing PST files in the ANSI file format. This parameter is used for importing PST files from Chinese, Japanese, and Korean (CJK) organizations because these languages typically use a double byte character set (DBCS) for character encoding. If this parameter isn't used to import PST files for languages that use DBCS for mailbox folder names, the folder names are often garbled after they're imported.  </span></span><br/> <span data-ttu-id="c262d-330">このパラメーターに使用することがサポートされている値の一覧については、「[コードページ識別子](https://go.microsoft.com/fwlink/p/?LinkId=328514)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-330">For a list of supported values to use for this parameter, see [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).</span></span>  <br/> <span data-ttu-id="c262d-p152">> [!NOTE]> 前述のとおり、これはオプションのパラメーターであり、CSV ファイルに含める必要はありません。または、1つまたは複数の行の値を空白のままにしておくこともできます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p152">> [!NOTE]> As previously stated, this is an optional parameter and you don't have to include it in the CSV file. Or you can include it and leave the value blank for one or more rows.</span></span>           |<span data-ttu-id="c262d-333">(空白)</span><span class="sxs-lookup"><span data-stu-id="c262d-333">(leave blank)</span></span>  <br/> <span data-ttu-id="c262d-334">または</span><span class="sxs-lookup"><span data-stu-id="c262d-334">Or</span></span>  <br/>  <span data-ttu-id="c262d-335">`932`(ANSI/OEM 日本語のコードページ識別子)</span><span class="sxs-lookup"><span data-stu-id="c262d-335">`932` (which is the code page identifier for ANSI/OEM Japanese)</span></span>  <br/> |
    | `SPFileContainer` <br/> |<span data-ttu-id="c262d-336">PST インポートの場合は、このパラメーターを空白のままにします。 </span><span class="sxs-lookup"><span data-stu-id="c262d-336">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="c262d-337">該当なし</span><span class="sxs-lookup"><span data-stu-id="c262d-337">Not applicable</span></span>  <br/> |
    | `SPManifestContainer` <br/> |<span data-ttu-id="c262d-338">PST インポートの場合は、このパラメーターを空白のままにします。 </span><span class="sxs-lookup"><span data-stu-id="c262d-338">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="c262d-339">該当なし</span><span class="sxs-lookup"><span data-stu-id="c262d-339">Not applicable</span></span>  <br/> |
    | `SPSiteUrl` <br/> |<span data-ttu-id="c262d-340">PST インポートの場合は、このパラメーターを空白のままにします。 </span><span class="sxs-lookup"><span data-stu-id="c262d-340">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="c262d-341">該当なし</span><span class="sxs-lookup"><span data-stu-id="c262d-341">Not applicable</span></span>  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a><span data-ttu-id="c262d-342">手順 4:Office 365 で PST インポート ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="c262d-342">Step 4: Create a PST Import job in Office 365</span></span>

<span data-ttu-id="c262d-p153">次の手順では、Office 365 のインポートサービスで PST インポートジョブを作成します。前述のように、手順3で作成した PST インポートマッピングファイルを送信します。新しいジョブを作成した後、インポートサービスはマッピングファイルの情報を使用して、pst ファイルがハードドライブから Azure ストレージ領域にコピーされた後に、指定されたユーザーメールボックスに pst ファイルをインポートします。その後、インポートジョブを作成して開始します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p153">The next step is to create the PST Import job in the Import service in Office 365. As previously explained, you will submit the PST Import mapping file that you created in Step 3. After you create the new job, the Import service will use the information in the mapping file to import the PST files to the specified user mailbox after the PST files are copied from the hard drive to the Azure storage area and you create and start the import job.</span></span>
  
1. <span data-ttu-id="c262d-346">に[https://protection.office.com](https://protection.office.com)移動し、Office 365 組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="c262d-346">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="c262d-347">セキュリティ&amp; /コンプライアンスセンターの左側のウィンドウで、[**データガバナンス**] をクリックし、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-347">In the left pane of the Security &amp; Compliance Center, click **Data governance** and then click **Import**.</span></span>
    
3. <span data-ttu-id="c262d-348">[**インポート**] ページで、 ![[追加](media/ITPro-EAC-AddIcon.gif) ] アイコン [**新しいインポートジョブ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-348">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c262d-349">前述したように、セキュリティ&amp;コンプライアンスセンターの [**インポート**] ページにアクセスするには、適切なアクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c262d-349">As previously stated, you have to be assigned the appropriate permissions to access the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
4. <span data-ttu-id="c262d-p154">PST インポートジョブの名前を入力し、[**次へ**] をクリックします。小文字、数字、ハイフン、およびアンダースコアを使用してください。名前には、大文字を使用したり、スペースを含めたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c262d-p154">Type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="c262d-353">[**インポートジョブの種類の選択**] ページで、[**ハードドライブを物理的な場所の1つに出荷する**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-353">On the **Choose import job type** page, click **Ship hard drives to one of our physical locations** and then click **Next**.</span></span>
    
    ![ドライブ送付インポートジョブを作成するには、[ハードドライブを物理的な場所の1つに出荷] をクリックします。](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. <span data-ttu-id="c262d-355">手順6で、[自分のハードドライブの準備ができました] をクリックし、**必要なドライブジャーナルファイルにアクセス**して、[**マッピングファイルにアクセス**できる] チェックボックスをオンにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-355">In step 6, click the **I've prepared my hard drives and have access to the necessary drive journal files** and **I have access to the mapping file** check boxes, and then click **Next**.</span></span>
    
    ![手順6で2つのチェックボックスをクリックします。](media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. <span data-ttu-id="c262d-p155">[**ドライブファイルの選択**] ページで、[**ドライブファイルの選択**] をクリックして、waimportexport .exe ツールが配置されているのと同じフォルダーに移動します。手順2で作成したジャーナルファイルは、このフォルダーにコピーされました。</span><span class="sxs-lookup"><span data-stu-id="c262d-p155">On the **Select the drive file** page, click **Select drive file**, and then go to the same folder where the WAImportExport.exe tool is located. The journal file that was created in Step 2 was copied to this folder.</span></span>
    
    ![waimportexport .exe ツールを実行したときに作成されたジャーナルファイルを送信するには、[ドライブファイルの選択] をクリックします。](media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. <span data-ttu-id="c262d-360">ジャーナルファイルを選択します。たとえば、 `PSTHDD1.jrn`のようになります。</span><span class="sxs-lookup"><span data-stu-id="c262d-360">Select the journal file; for example, `PSTHDD1.jrn`.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c262d-361">手順2で waimportexport .exe ツールを実行したときに、ジャーナルファイルの名前が`/j:`パラメーターによって指定されています。</span><span class="sxs-lookup"><span data-stu-id="c262d-361">When you ran the WAImportExport.exe tool in Step 2, the name of the journal file was specified by the  `/j:` parameter.</span></span> 
  
9. <span data-ttu-id="c262d-362">ドライブファイルの名前が [**ドライブファイル名**] の下に表示されたら、[**検証**] をクリックして、ドライブファイルにエラーがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c262d-362">After the name of the drive file appears under **Drive file name**, click **Validate** to check your drive file for errors.</span></span> 
    
    ![[検証] をクリックして、選択したドライブファイルを検証します。](media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    <span data-ttu-id="c262d-p156">PST インポートジョブを作成するには、ドライブファイルが正常に検証されている必要があります。メモファイル名が正常に検証された後に、緑に変更されます。検証が失敗した場合は、[ **View log** ] リンクをクリックします。検証エラーレポートが開き、ファイルが失敗した理由に関する情報が含まれたエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p156">The drive file has to be successfully validated to create a PST Import job. Note the file name is changed to green after it's successfully validated. If the validation fails, click the **View log** link. A validation error report is opened, with a error message with information about why the file failed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c262d-368">Microsoft に出荷する各ハードドライブに対して、ジャーナルファイルを追加して検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c262d-368">You must add and validate a journal file for each hard drive you ship to Microsoft.</span></span> 
  
10. <span data-ttu-id="c262d-369">Microsoft に出荷する各ハードドライブのジャーナルファイルを追加して検証した後、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-369">After adding and validating a journal file for each hard drive that you'll ship to Microsoft, click **Next**.</span></span>
    
11. <span data-ttu-id="c262d-370">[ ![追加]](media/ITPro-EAC-AddIcon.gif)アイコン [**マッピングファイルの選択**] をクリックして、手順3で作成した PST インポートマッピングファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="c262d-370">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Select mapping file** to submit the PST Import mapping file that you created in Step 3.</span></span> 
    
    ![[マッピングファイルの選択] をクリックして、インポートジョブ用に作成した CSV ファイルを送信します。](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. <span data-ttu-id="c262d-372">csv ファイルの名前が [**マッピングファイル名**] の下に表示されたら、[**検証**] をクリックして csv ファイルにエラーがないか確認します。</span><span class="sxs-lookup"><span data-stu-id="c262d-372">After the name of the CSV file appears under **Mapping file name**, click **Validate** to check your CSV file for errors.</span></span> 
    
    ![[検証] をクリックして、CSV ファイルのエラーを確認します。](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    <span data-ttu-id="c262d-p157">PST インポートジョブを作成するには、CSV ファイルが正常に検証されている必要があります。メモファイル名が正常に検証された後に、緑に変更されます。検証が失敗した場合は、[ **View log** ] リンクをクリックします。検証エラーレポートが開き、エラーが発生したファイル内の各行に関するエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p157">The CSV file has to be successfully validated to create a PST Import job. Note the file name is changed to green after it's successfully validated. If the validation fails, click the **View log** link. A validation error report is opened, with a error message for each row in the file that failed.</span></span> 
    
13. <span data-ttu-id="c262d-378">PST マッピングファイルが正常に検証されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-378">After the PST mapping file is successfully validated, click **Next**.</span></span>
    
14. <span data-ttu-id="c262d-379">[**連絡先情報の入力**] ページで、該当するボックスに連絡先情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c262d-379">On the **Provide contact information** page, type your contact information in the applicable boxes.</span></span> 
    
    <span data-ttu-id="c262d-p158">ハードドライブを送付する Microsoft の場所のアドレスが表示されていることに注意してください。このアドレスは、Office 365 データセンターの場所に基づいて自動生成されます。このアドレスをファイルにコピーするか、スクリーンショットを取ります。</span><span class="sxs-lookup"><span data-stu-id="c262d-p158">Note that the address for the Microsoft location that you will ship your hard drives to is displayed. This address is auto-generated based on your Office 365 data center location. Copy this address to a file or take a screenshot.</span></span>
    
15. <span data-ttu-id="c262d-383">使用条件ドキュメントを読んで、チェックボックスをクリックし、[**保存**] をクリックしてインポートジョブを送信します。</span><span class="sxs-lookup"><span data-stu-id="c262d-383">Read the terms and conditions document, click the checkbox, and then click **Save** to submit the import job.</span></span> 
    
    <span data-ttu-id="c262d-384">インポートジョブが正常に作成されると、ドライブ出荷プロセスの次の手順を説明する状態ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c262d-384">When the import job is successfully created, a status page is displayed that explains the next steps of the drive shipping process.</span></span>
    
16. <span data-ttu-id="c262d-p159">[**インポート**] ページで、 ![[更新](media/O365-MDM-Policy-RefreshIcon.gif)アイコンの**更新**] をクリックして、インポートジョブの一覧に新しいドライブ配送インポートジョブを表示します。状態は、**追跡番号を待機**するように設定されていることに注意してください。インポートジョブをクリックして、インポートジョブに関する詳細情報を含む状態ポップアップページを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p159">On the **Import** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to displayed the new drive shipping import job in the list of import jobs. Note that the status is set to **Waiting for tracking number**. You can also click the import job to display the status flyout page, which contains more detailed information about the import job.</span></span>
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a><span data-ttu-id="c262d-388">手順 5:Microsoft にハード ドライブを送付する</span><span class="sxs-lookup"><span data-stu-id="c262d-388">Step 5: Ship the hard drive to Microsoft</span></span>

<span data-ttu-id="c262d-p160">次の手順では、Microsoft にハードドライブを送付してから、ドライブ出荷ジョブの発送番号と返送情報を提供します。ドライブは、Microsoft によって受信された後、データセンターの担当者が組織の Azure ストレージ領域に PST ファイルをアップロードするのに 7 ~ 10 営業日かかります。</span><span class="sxs-lookup"><span data-stu-id="c262d-p160">The next step is to ship the hard drive to Microsoft, and then provide the tracking number for the shipment and return shipment information for the drive shipping job. After the drive is received by Microsoft, it will take between 7 and 10 business days for data center personnel to upload your PST files to the Azure storage area for your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c262d-p161">インポートジョブの作成から14日以内に追跡番号を指定せずに出荷情報を取得した場合、インポートジョブは期限切れになります。このような状況が発生した場合は、新しいドライブ送付インポートジョブを作成する必要があります (「[手順 4: Office 365 で pst インポートジョブを作成](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)する」を参照し、ドライブファイルと pst インポートマッピングファイルを再送信します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p161">If you don't provide the tracking number and return shipment information within 14 days of creating the import job, the import job will be expired. If this happens, you'll have to create a new drive shipping import job (see [Step 4: Create a PST Import job in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)) and re-submit the drive file and the PST import mapping file.</span></span> 
  
### <a name="ship-the-hard-drive"></a><span data-ttu-id="c262d-393">ハード ドライブを送付する</span><span class="sxs-lookup"><span data-stu-id="c262d-393">Ship the hard drive</span></span>

<span data-ttu-id="c262d-394">Microsoft にハード ドライブを送付する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-394">Keep the following things in mind when you ship hard drives to Microsoft:</span></span>
  
- <span data-ttu-id="c262d-395">シリアルから USB へのアダプターは送付しないでください。ハードドライブを送付するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="c262d-395">Don't ship the SATA-to-USB adapter; you only have to ship the hard drive.</span></span>
    
- <span data-ttu-id="c262d-396">ハード ドライブを適切に梱包する。たとえば、静電気防止バッグやクッション材など使用する。</span><span class="sxs-lookup"><span data-stu-id="c262d-396">Package the hard drive properly; for example, use an anti-static bag or bubble wrap.</span></span>
    
- <span data-ttu-id="c262d-397">任意の配送業者を使用して、Microsoft にハード ドライブを送付する。</span><span class="sxs-lookup"><span data-stu-id="c262d-397">Use a delivery carrier of your choice to ship the hard drive to Microsoft.</span></span>
    
- <span data-ttu-id="c262d-p162">手順4でインポートジョブを作成したときに表示された Microsoft の場所のアドレスにハードドライブを送付します。出荷先住所に「Office 365 Import Service」を含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p162">Ship the hard drive to the address for the Microsoft location that was displayed when you created the import job in Step 4. Be sure to include "Office 365 Import Service" in the ship-to address.</span></span>
    
- <span data-ttu-id="c262d-p163">ハード ドライブの送付後、配送業者の名前と追跡番号を必ず書き留めてください。これらは次の手順で必要になります。</span><span class="sxs-lookup"><span data-stu-id="c262d-p163">After you ship the hard drive, be sure to write down the name of the delivery carrier and the tracking number. You'll provide these in the next step.</span></span>
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a><span data-ttu-id="c262d-402">追跡番号と他の配送情報を入力する</span><span class="sxs-lookup"><span data-stu-id="c262d-402">Enter the tracking number and other shipping information</span></span>

<span data-ttu-id="c262d-403">Microsoft にハード ドライブを送付した後、インポート サービスのページで次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="c262d-403">After you've shipped the hard drive to Microsoft, complete the following procedure on the Import service page.</span></span>
  
1. <span data-ttu-id="c262d-404">に[https://protection.office.com](https://protection.office.com)移動し、Office 365 組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="c262d-404">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="c262d-405">左側のウィンドウで、[**データガバナンス**] をクリックし、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-405">In the left pane, click **Data governance** and then click **Import**.</span></span>
    
3. <span data-ttu-id="c262d-406">[**インポート**] ページで、追跡番号を入力するドライブの出荷のジョブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-406">On the **Import** page, click the job for the drive shipment that you want to enter the tracking number for.</span></span> 
    
4. <span data-ttu-id="c262d-407">[状態のポップアップ] ページで、[**追跡番号の入力**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-407">On the status flyout page, click **Enter tracking number**.</span></span>
    
5. <span data-ttu-id="c262d-408">以下の送付情報を入力する。</span><span class="sxs-lookup"><span data-stu-id="c262d-408">Provide the following shipping information:</span></span>
    
1. <span data-ttu-id="c262d-409">**配送業者**ハードドライブを Microsoft に出荷する際に使用した配送業者の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c262d-409">**Delivery carrier** Type the name of the delivery carrier that you used to ship the hard drive to Microsoft.</span></span> 
    
2. <span data-ttu-id="c262d-410">**追跡番号**ハードドライブの出荷の追跡番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="c262d-410">**Tracking number** Type the tracking number for the hard drive shipment.</span></span> 
    
3. <span data-ttu-id="c262d-p164">**返品業者のアカウント番号**[**返品業者**] にリストされている通信業者の組織のアカウント番号を入力します。Microsoft は、このアカウントを使用して、お客様にハードドライブを送付します。米国およびヨーロッパの組織には、FedEx のアカウントが必要であることに注意してください。アジアおよび世界の他の組織は、DHL のアカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c262d-p164">**Return carrier account number** Type your organization's account number for the carrier that listed under **Return carrier**. Microsoft will use (and charge) this account to ship your hard drive back to you. Note that organizations in the USA and Europe, must have an account with FedEx. Organizations in Asia and the rest of the world, must have an account with DHL.</span></span>
    
6. <span data-ttu-id="c262d-415">**[保存]** をクリックして、インポート ジョブのこの情報を保存する。</span><span class="sxs-lookup"><span data-stu-id="c262d-415">Click **Save** to save this information for the import job.</span></span> 
    
    <span data-ttu-id="c262d-p165">[**インポート**] ページで、 ![[更新](media/O365-MDM-Policy-RefreshIcon.gif) \*\*\*\* アイコンの更新] をクリックして、ドライブの配送インポートジョブの情報を更新します。状態が **[転送中のドライブ**に設定されました。</span><span class="sxs-lookup"><span data-stu-id="c262d-p165">On the **Import** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the information for your drive shipping import job. Notice that status is now set to **Drives in transit**.</span></span>

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a><span data-ttu-id="c262d-418">手順 6: データをフィルター処理し、PST インポートジョブを開始する</span><span class="sxs-lookup"><span data-stu-id="c262d-418">Step 6: Filter data and start the PST Import job</span></span>

<span data-ttu-id="c262d-p166">Microsoft がハードドライブを受信すると、[**インポート**] ページのインポートジョブの状態が [受信した**ドライブ**] に変わります。データセンターの担当者は、ジャーナルファイルの情報を使用して、組織の Azure ストレージ領域に PST ファイルをアップロードします。この時点で、状態は [**インポート中**] に変わります。前述したように、ハードドライブを受け取った後、PST ファイルをアップロードするには、7 ~ 10 営業日かかります。</span><span class="sxs-lookup"><span data-stu-id="c262d-p166">After your hard drive is received by Microsoft, the status for the import job on the **Import** page will change to **Drives received**. Data center personnel will use the information in the journal file to upload your PST files to the Azure storage area for your organization. At this point, the status will change to **Import in-progress**. As previously stated, it will take between 7 to 10 business days after receiving your hard drive to upload the PST files.</span></span>
  
<span data-ttu-id="c262d-p167">PST ファイルが Azure にアップロードされると、進行中の**分析**に状態が変更されます。これは、Office 365 が pst ファイルのデータ (安全かつ安全な方法) を分析して、アイテムの保存期間と pst ファイルに含まれるさまざまなメッセージの種類を識別することを示しています。分析が完了し、データをインポートする準備が整ったら、インポートジョブの状態が [**分析完了**] に変更されます。この時点で、PST ファイルに含まれるすべてのデータをインポートするか、インポートするデータを制御するフィルターを設定することによってインポートされたデータをトリミングするかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p167">After PST files are uploaded to Azure, the status is changed to **Analysis in progress**. This indicates that Office 365 is analyzing the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files. When the analysis is completed and the data is ready to import, the status for the import job is changed to **Analysis completed**. At this point, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span>
  
1. <span data-ttu-id="c262d-427">に[https://protection.office.com](https://protection.office.com)移動し、Office 365 組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="c262d-427">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="c262d-428">左側のウィンドウで、[**データガバナンス** > の**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-428">In the left pane, click **Data governance** > **Import**.</span></span>
    
3. <span data-ttu-id="c262d-429">[**インポート**] ページで、手順4で作成したインポートジョブについて、[ **Office 365 にインポートする準備ができ**ました] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-429">On the **Import** page, click **Ready to import to Office 365** for the import job that you created in Step 4.</span></span> 
    
    ![作成したインポートジョブの横にある [Office 365 にインポートする準備完了] をクリックします。](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    <span data-ttu-id="c262d-431">フライアウトページには、PST ファイルおよびインポートジョブに関するその他の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c262d-431">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="c262d-432">[ **Office 365 へのインポート] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-432">Click **Import to Office 365**.</span></span>
    
5. <span data-ttu-id="c262d-p168">[**データをフィルター**する] ページが表示されます。このファイルには、データの保存期間に関する情報を含む、Office 365 によって PST ファイルに対して実行された分析の結果として得られるデータ insights が含まれています。この時点で、インポートされるデータをフィルター処理するか、すべてのデータをそのものとしてインポートするかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p168">The **Filter your data** page is displayed. It contains the data insights resulting from the analysis performed on the PST files by Office 365, including information about the age of the data. At this point, you have the option to filter the data that will be imported or import all the data as is.</span></span> 
    
    ![PST ファイルのデータをトリミングしたり、すべてのデータをインポートしたりできます。](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. <span data-ttu-id="c262d-437">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c262d-437">Do one of the following:</span></span>
    
    <span data-ttu-id="c262d-p169">。インポートするデータをトリミングするには、[**はい、インポートする前にフィルターを適用**します] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-p169">a. To trim the data that you import, click **Yes, I want to filter it before importing**.</span></span>
    
    <span data-ttu-id="c262d-440">pst ファイルのデータをフィルター処理してからインポートジョブを開始する方法の詳細な手順については、「 [pst ファイルを Office 365 にインポートするときにデータをフィルターする](filter-data-when-importing-pst-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-440">For detailed step-by-step instructions about filtering the data in the PST files and then starting the import job, see [Filter data when importing PST files to Office 365](filter-data-when-importing-pst-files.md).</span></span>
    
    <span data-ttu-id="c262d-441">または</span><span class="sxs-lookup"><span data-stu-id="c262d-441">Or</span></span>
    
    <span data-ttu-id="c262d-p170">b. PST ファイルのすべてのデータをインポートするには、[**いいえ、** すべてをインポートします] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-p170">b. To import all data in the PST files, click **No, I want to import everything,** and click **Next**.</span></span>
    
7. <span data-ttu-id="c262d-444">すべてのデータをインポートすることを選択した場合は、[**データのインポート**] をクリックしてインポートジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="c262d-444">If you chose to import all the data, click **Import data** to start the import job.</span></span> 
    
    <span data-ttu-id="c262d-p171">インポートジョブの状態が [**インポート**] ページに表示されます。[ ![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif) \*\*\*\* の更新] をクリックして、[**状態**] 列に表示される状態情報を更新します。インポートジョブをクリックして状態ポップアップページを表示すると、インポートされている各 PST ファイルに関する状態情報が表示されます。インポートが完了し、PST ファイルがユーザーのメールボックスにインポートされると、状態は [**完了**] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p171">The status of the import job is displayed on the **Import** page. Click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the status information that's displayed in the **Status** column. Click the import job to display the status flyout page, which displays status information about each PST file being imported. When the import is complete and PST files have been imported to user mailboxes, the status will be changed to **Completed**.</span></span>

## <a name="view-a-list-of-the-pst-files-uploaded-to-office-365"></a><span data-ttu-id="c262d-449">Office 365 にアップロードされた PST ファイルの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="c262d-449">View a list of the PST files uploaded to Office 365</span></span>

<span data-ttu-id="c262d-p172">microsoft azure ストレージエクスプローラー (無償のオープンソースツール) をインストールして使用すると、組織の Azure ストレージ領域に (microsoft データセンター担当者が) アップロードした PST ファイルの一覧を表示することができます。これにより、Microsoft に送信したハードドライブの PST ファイルが Azure ストレージ領域に正常にアップロードされたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p172">You can install and use the Microsoft Azure Storage Explorer (which is a free, open source tool) to view the list of the PST files that we're uploaded (by Microsoft data center personnel) to the Azure storage area for your organization. You can do this to verify that PST files from the hard drives that you sent to Microsoft were successfully uploaded to the Azure storage area.</span></span>
  
<span data-ttu-id="c262d-452">Microsoft Azure ストレージエクスプローラーはプレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="c262d-452">The Microsoft Azure Storage Explorer is in Preview.</span></span>
  
 <span data-ttu-id="c262d-p173">**重要:** Azure ストレージエクスプローラーを使用して PST ファイルをアップロードまたは変更することはできません。PST ファイルを Office 365 にインポートするためにサポートされている唯一の方法は、azcopy を使用することです。また、Azure blob にアップロードした PST ファイルを削除することもできません。PST ファイルを削除しようとすると、必要なアクセス許可がないというエラーが表示されます。すべての PST ファイルが Azure ストレージ領域から自動的に削除されることに注意してください。進行中のインポートジョブがない場合、[\* \* ingestiondata \* \*] コンテナー内のすべての PST ファイルは、最新のインポートジョブが作成されてから30日後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p173">**Important:** You can't use the Azure Storage Explorer to upload or modify PST files. The only supported method for importing PST files to Office 365 is to use AzCopy. Also, you can't delete PST files that you've uploaded to the Azure blob. If you try to delete a PST file, you'll receive an error about not having the required permissions. Note that all PST files are automatically deleted from your Azure storage area. If there are no import jobs in progress, then all PST files in the \*\* ingestiondata \*\* container are deleted 30 days after the most recent import job was created.</span></span> 
  
<span data-ttu-id="c262d-459">azure ストレージエクスプローラーをインストールして azure ストレージ領域に接続するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c262d-459">To install the Azure Storage Explorer and connect to your Azure storage area:</span></span>
  
1. <span data-ttu-id="c262d-p174">組織の Shared Access Signature (SAS) URL を取得するには、次の手順を実行します。この url は、組織および SAS キーで使用される Microsoft クラウド内の Azure ストレージの場所のネットワーク URL の組み合わせです。このキーは、組織の Azure ストレージの場所にアクセスするために必要なアクセス許可を提供します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p174">Perform the following steps to get the Shared Access Signature (SAS) URL for your organization. This URL is a combination of the network URL for the Azure storage location in the Microsoft cloud for your organization and an SAS key. This key provides you with the necessary permissions to access your organization's Azure storage location.</span></span>
    
1. <span data-ttu-id="c262d-463">に[https://protection.office.com/](https://protection.office.com/)移動し、Office 365 組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="c262d-463">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="c262d-464">セキュリティ&amp; /コンプライアンスセンターの左側のウィンドウで、[**データガバナンス** \>の**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-464">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
3. <span data-ttu-id="c262d-465">[**インポート**] ページで、 ![[追加](media/ITPro-EAC-AddIcon.gif) ] アイコン [**新しいインポートジョブ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-465">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
4. <span data-ttu-id="c262d-p175">[ジョブのインポート] ウィザードで、PST インポートジョブの名前を入力し、[**次へ**] をクリックします。小文字、数字、ハイフン、およびアンダースコアを使用してください。名前には、大文字を使用したり、スペースを含めたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c262d-p175">In the import job wizard, type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="c262d-469">[**インポートジョブの種類の選択**] ページで、[**データのアップロード**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-469">On the **Choose import job type** page, click **Upload your data** and then click **Next**.</span></span>
    
6. <span data-ttu-id="c262d-470">手順2で、[**ネットワークアップロード SAS URL を表示する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-470">In step 2, click **Show network upload SAS URL**.</span></span>
    
7. <span data-ttu-id="c262d-p176">URL が表示されたら、それをコピーしてファイルに保存します。必ず URL 全体をコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p176">After the URL is displayed, copy it and save it to a file. Be sure to copy the entire URL.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c262d-p177">SAS URL を保護するための予防措置を講じてください。これは、組織の Azure ストレージ領域にアクセスするすべてのユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p177">Be sure to take precautions to protect the SAS URL. This can be used by anyone to access the Azure storage area for your organization.</span></span> 
  
8. <span data-ttu-id="c262d-475">[**キャンセル**] をクリックして、ジョブのインポートウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="c262d-475">Click **Cancel** to close the import job wizard.</span></span> 
    
2. <span data-ttu-id="c262d-476">[Microsoft Azure ストレージエクスプローラーツール](https://go.microsoft.com/fwlink/p/?LinkId=544842)をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="c262d-476">Download and install the [Microsoft Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span>
    
3. <span data-ttu-id="c262d-477">Microsoft Azure ストレージエクスプローラーを起動し、左側のウィンドウで [**ストレージアカウント**] を右クリックして、[ **Azure ストレージに接続] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-477">Start the Microsoft Azure Storage Explorer, right-click **Storage Accounts** in the left pane, and then click **Connect to Azure storage**.</span></span>
    
    ![[ストレージアカウント] を右クリックし、[Azure ストレージへの接続] をクリックします。](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. <span data-ttu-id="c262d-479">[**共有アクセス署名 (SAS) URI または接続文字列を使用**する] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-479">Click **Use a shared access signature (SAS) URI or connection string** and click **Next**.</span></span>
    
5. <span data-ttu-id="c262d-480">[ **sas uri を使用**する] をクリックして、手順1で取得した sas URL を [ **uri**] の下のボックスに貼り付け、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-480">Click **Use a SAS URI**, paste the SAS URL that you obtained in step 1 in to in the box under **URI**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c262d-481">[**接続の概要**] ページで、接続情報を確認し、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c262d-481">On the **Connection summary** page, you can review the connection information, and then click **Connect**.</span></span>
    
    <span data-ttu-id="c262d-p178">**ingestiondata**コンテナーが開きます。ハードドライブの PST ファイルが含まれています。**ingestiondata**コンテナーは、**ストレージアカウント** \> **(SAS 接続されたサービス)** \> **Blob コンテナー**の下にあります。</span><span class="sxs-lookup"><span data-stu-id="c262d-p178">The **ingestiondata** container is opened; it contains the PST files from your hard drive. The **ingestiondata** container is located under **Storage Accounts** \> **(SAS-Attached Services)** \> **Blob Containers**.</span></span>
    
    ![Azure ストレージ エクスプローラーには、アップロードした PST ファイルの一覧が表示される](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. <span data-ttu-id="c262d-p179">Microsoft azure ストレージエクスプローラーの使用が終了したら、[ **ingestiondata**] を右クリックし、 \*\*\*\* [切断] をクリックして azure ストレージ領域から切断します。そうしないと、次に接続しようとしたときにエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p179">When you're finished using the Microsoft Azure Storage Explorer, right-click **ingestiondata**, and then click **Detach** to disconnect from your Azure storage area. Otherwise, you'll receive an error the next time you try to attach.</span></span> 
    
    ![ingestion を右クリックして [デタッチ] をクリックし、Azure のストレージ エリアから切断する](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  

  
## <a name="troubleshooting-tips"></a><span data-ttu-id="c262d-488">トラブルシューティングのヒント</span><span class="sxs-lookup"><span data-stu-id="c262d-488">Troubleshooting tips</span></span>
<span data-ttu-id="c262d-489"><a name="troubleshootingtips"> </a></span><span class="sxs-lookup"><span data-stu-id="c262d-489"></span></span>

- <span data-ttu-id="c262d-p180">**PST インポートの CSV マッピングファイルにエラーがあるためにインポートジョブが失敗した場合はどうなりますか。** マッピングファイルのエラーによってインポートジョブが失敗した場合は、新しいインポートジョブを作成するために、ハードドライブを Microsoft に再出荷する必要はありません。これは、ドライブ送付インポートジョブ用に送信したハードドライブからの PST ファイルが、組織の Azure ストレージ領域に既にアップロードされているためです。この場合は、PST インポート CSV マッピングファイルのエラーを修正してから、新しい "network upload" インポートジョブを作成し、改訂された CSV マッピングファイルを送信するだけで済みます。新しいネットワークアップロードインポートジョブを作成して開始するには、「[手順 5: office 365 で pst インポートジョブを作成](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365)する」および「[手順 6: データをフィルター処理](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job)するために、ネットワークアップロードを使用して pst ファイルを Office 365 にインポートする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p180">**What happens if the import job fails because of errors in the PST Import CSV mapping file?** If an import job fails because of errors in the mapping file, you don't have to re-ship the hard drive to Microsoft in order to create a new import job. That's because the PST files from the hard drive that you submitted for the drive shipping import job have already been uploaded to the Azure storage area for your organization. In this case, you just have to fix the errors in the PST Import CSV mapping file, and then create a new "network upload" import job and submit the revised CSV mapping file. To create and start a new network upload import job, see [Step 5: Create a PST Import job in Office 365](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365) and [Step 6: Filter data and start the PST Import job](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job) in the topic "Use network upload to import PST files to Office 365."</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c262d-p181">pst インポートの CSV マッピングファイルのトラブルシューティングに役立てるために、 [azure ストレージエクスプローラー](#view-a-list-of-the-pst-files-uploaded-to-office-365)ツールを使用して、azure ストレージ領域にアップロードされたハードディスクドライブからの pst ファイルの**ingestiondata**コンテナーにあるフォルダー構造を表示します。通常、ファイルのマッピングエラーは FilePath パラメーターの値が正しくないことが原因で発生します。このパラメーターには、Azure ストレージ領域内の PST ファイルの場所を指定します。[手順 3](#step-3-create-the-pst-import-mapping-file)の表の FilePath パラメーターの説明を参照してください。前述のように、[手順 2](#step-2-copy-the-pst-files-to-the-hard-drive)で waimportexport .exe ツールを実行したとき`/dstdir:`に、パラメーターによって、Azure ストレージ領域内の PST ファイルの場所が指定されました。</span><span class="sxs-lookup"><span data-stu-id="c262d-p181">To help you troubleshoot the PST Import CSV mapping file, use the [Azure Storage Explorer](#view-a-list-of-the-pst-files-uploaded-to-office-365) tool to view the folder structure in the **ingestiondata** container for the PST files from your hard drive that were uploaded to the Azure storage area. Mapping file errors are typically caused by an incorrect value in the FilePath parameter. This parameter specifies the location of a PST file in the Azure storage area. See the description of the FilePath parameter in table in [Step 3](#step-3-create-the-pst-import-mapping-file). As previously explained, the location of PST files in the Azure storage area was specified by the  `/dstdir:` parameter when you ran the WAImportExport.exe tool in [Step 2](#step-2-copy-the-pst-files-to-the-hard-drive).</span></span> 
  

  
## <a name="more-information"></a><span data-ttu-id="c262d-500">詳細情報</span><span class="sxs-lookup"><span data-stu-id="c262d-500">More information</span></span>

- <span data-ttu-id="c262d-p182">ドライブの配送は、組織で使用できるコンプライアンス機能を活用するために、大量のアーカイブメッセージングデータを Office 365 にインポートする効果的な方法です。アーカイブデータをユーザーのメールボックスにインポートした後、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c262d-p182">Drive shipping is an effective way to import large amounts of archival messaging data to Office 365 to take advantage of the compliance features that are available to your organization. After archival data is imported to user mailboxes, you can:</span></span>
    
  - <span data-ttu-id="c262d-503">[アーカイブメールボックス](enable-archive-mailboxes.md)および[自動拡張アーカイブ](enable-unlimited-archiving.md)を有効にして、ユーザーにデータの追加のメールボックス記憶領域を付与します。</span><span class="sxs-lookup"><span data-stu-id="c262d-503">Enable [archive mailboxes](enable-archive-mailboxes.md) and [auto-expanding archiving](enable-unlimited-archiving.md) to give users additional mailbox storage space for the data.</span></span> 
    
  - <span data-ttu-id="c262d-504">メールボックスを[訴訟ホールド](https://go.microsoft.com/fwlink/?linkid=856286)の対象にしてデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="c262d-504">Place mailboxes on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) to retain the data.</span></span> 
    
  - <span data-ttu-id="c262d-505">Microsoft[電子情報開示ツール](search-for-content.md)を使用して、データを検索します。</span><span class="sxs-lookup"><span data-stu-id="c262d-505">Use Microsoft [eDiscovery tools](search-for-content.md) to search the data.</span></span> 
    
  - <span data-ttu-id="c262d-506">[Office 365 アイテム保持ポリシー](retention-policies.md)を適用して、データの保持期間を制御します。また、保持期間が経過した後に実行するアクションを制御します。</span><span class="sxs-lookup"><span data-stu-id="c262d-506">Apply [Office 365 retention policies](retention-policies.md) to control how long the data is retained, and what action to take after the retention period expires.</span></span> 
    
  - <span data-ttu-id="c262d-507">このデータに関連するイベントについては、 [Office 365 監査ログ](search-the-audit-log-in-security-and-compliance.md)を検索します。</span><span class="sxs-lookup"><span data-stu-id="c262d-507">Search the [Office 365 audit log](search-the-audit-log-in-security-and-compliance.md) for events related to this data.</span></span> 
    
  - <span data-ttu-id="c262d-508">コンプライアンスを目的として、[非アクティブなメールボックス](create-and-manage-inactive-mailboxes.md)にデータをアーカイブするためのデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="c262d-508">Import data to [inactive mailboxes](create-and-manage-inactive-mailboxes.md) to archive data for compliance purposes.</span></span> 
    
  - <span data-ttu-id="c262d-509">機密情報の[データ損失](data-loss-prevention-policies.md)から組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="c262d-509">Protect your organization against [data loss](data-loss-prevention-policies.md) of sensitive information.</span></span> 
    
- <span data-ttu-id="c262d-p183">セキュリティで保護されたストレージ アカウント キーと BitLocker 暗号化キーの例を、次に示します。この例には、ハード ディスクに PST ファイルをコピーするために実行する WAImportExport.exe コマンドの構文も含まれています。パスワードやその他のセキュリティ関連情報を保護するのと同じように、これらのファイルを保護するための予防策を必ず講じてください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p183">Here's an example of the secure storage account key and a BitLocker encryption key. This example also contains the syntax for the WAImportExport.exe command that you run to copy PST files to a hard drive. Be sure to take precautions to protect these just like you would protect passwords or other security-related information.</span></span>
    

    ```
    Secure storage account key: 

    yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==

    BitLocker encryption key:

    397386-221353-718905-535249-156728-127017-683716-083391

  COMMAND SYNTAX

  First time:

  WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>

  Subsequent times:

  WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 

  EXAMPLES

  First time:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER1\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"

  Subsequent times:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER1\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```
   
- <span data-ttu-id="c262d-p184">前述したように、Office 365 インポートサービスは、PST ファイルがメールボックスにインポートされた後、保持ホールドの設定 (無期限) を有効にします。つまり、 *RentionHoldEnabled*プロパティはに`True`設定されているため、メールボックスに割り当てられたアイテム保持ポリシーは処理されません。これにより、メールボックスの所有者は、削除またはアーカイブポリシーによる古いメッセージの削除またはアーカイブを禁止することにより、新しくインポートされたメッセージを管理できます。この保持ホールドを管理するために実行できるいくつかの手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c262d-p184">As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RentionHoldEnabled*  property is set to  `True` so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold:</span></span> 
    
  - <span data-ttu-id="c262d-p185">一定の期間が経過した後、 `Set-Mailbox -RetentionHoldEnabled $false`コマンドを実行して保存機能を無効にすることができます。手順については、「[メールボックスを保持ホールドの状態にする](https://go.microsoft.com/fwlink/p/?LinkId=544749)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p185">After a certain period of time, you can turn off the retention hold by running the  `Set-Mailbox -RetentionHoldEnabled $false` command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).</span></span>
    
  - <span data-ttu-id="c262d-p186">今後、ある日付に無効になるように、保存機能を構成することができます。そのためには、 `Set-Mailbox -EndDateForRetentionHold <date>`コマンドを実行します。たとえば、今日の日付が2016年7月1日で、保持ホールドを30日以内に無効にする場合は、次のコマンド`Set-Mailbox -EndDateForRetentionHold 8/1/2016`を実行します。このシナリオでは、 *RentionHoldEnabled*プロパティを*True*に設定したままにします。詳細については、「[メールボックスの設定](https://go.microsoft.com/fwlink/p/?LinkId=150317)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p186">You can configure the retention hold so that it's turned off on some date in the future. You do this by running the  `Set-Mailbox -EndDateForRetentionHold <date>` command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. In this scenario, you would leave the  *RentionHoldEnabled*  property set to  *True*  . For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).</span></span>
    
  - <span data-ttu-id="c262d-p187">メールボックスに割り当てられているアイテム保持ポリシーの設定を変更して、インポートした古いアイテムがすぐに削除されるか、ユーザーのアーカイブメールボックスに移動されないようにすることができます。たとえば、メールボックスに割り当てられている削除ポリシーまたはアーカイブポリシーの保存期間を長くすることができます。このシナリオでは、アイテム保持ポリシーの設定を変更した後、メールボックスの保存機能をオフにします。詳細については、「 [Office 365 組織のメールボックスのアーカイブおよび削除ポリシーをセットアップする](set-up-an-archive-and-deletion-policy-for-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-p187">You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>
    

  

