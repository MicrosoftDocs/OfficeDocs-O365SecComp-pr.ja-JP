---
title: ドライブの出荷を使用して、Office 365 の組織の PST ファイルをインポートするのには
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
description: '管理者: PST ファイルをハード ドライブにコピーし、マイクロソフトに出荷し、Office 365 のメールボックスに、組織の PST ファイルを一括インポートする方法について説明します。 '
ms.openlocfilehash: ebe88918b6c25e18562db7817d22fbf71f05e4c7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532064"
---
# <a name="use-drive-shipping-to-import-your-organization-pst-files-to-office-365"></a><span data-ttu-id="95660-103">ドライブの出荷を使用して、Office 365 の組織の PST ファイルをインポートするのには</span><span class="sxs-lookup"><span data-stu-id="95660-103">Use drive shipping to import your organization PST files to Office 365</span></span>

<span data-ttu-id="95660-104">**この資料では、管理者用です。自分のメールボックスを PST ファイルをインポートしようとしていますか。[インポート電子メール、連絡先、および Outlook の .pst ファイルから予定表](https://go.microsoft.com/fwlink/p/?LinkID=785075)を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="95660-104">**This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span></span>
   
<span data-ttu-id="95660-p101">サービスを Office 365 にインポートし、ドライブがユーザーのメールボックスを PST ファイルを一括インポートする配布を使用します。ドライブの出荷は、PST ファイルをハード ディスク ドライブにコピーし、Microsoft にドライブを物理的に出荷するを意味します。マイクロソフトでは、ハード ドライブを受信するとデータ センターの担当者はデータをマイクロソフトのクラウド内のストレージ領域をハード ディスク ドライブからコピーします。インポートされたデータを取得するかを制御するフィルターを設定することによって実際に対象のメールボックスにインポートする PST のデータをトリミングすることがあります。インポート ジョブを開始すると、サービスのインポートは、ユーザーのメールボックスにストレージ領域から PST のデータをインポートします。PST ファイルをユーザーのメールボックスにインポートするのにはドライブの出荷を使用して、組織の電子メールを Office 365 に移行する方法の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="95660-p101">Use the Office 365 Import service and drive shipping to bulk-import PST files to user mailboxes. Drive shipping means that you copy the PST files to a hard disk drive and then physically ship the drive to Microsoft. When Microsoft receives your hard drive, data center personnel will copy the data from the hard drive to a storage area in the Microsoft cloud. Then you have the opportunity to trim the PST data that's actually imported to the target mailboxes by setting filters that control what data gets imported. After you start the import job, the Import service imports the PST data from the storage area to user mailboxes. Using drive shipping to import PST files to user mailboxes is one way to migrate your organization's email to Office 365.</span></span>
  
<span data-ttu-id="95660-111">ドライブの出荷を使用して Office 365 のメールボックスを PST ファイルをインポートするための手順を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="95660-111">Here are the steps required to use drive shipping to import PST files to Office 365 mailboxes:</span></span>
  
[<span data-ttu-id="95660-112">手順 1: セキュリティで保護されたストレージ キーと PST インポート ツールをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="95660-112">Step 1: Download the secure storage key and PST Import tool</span></span>](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[<span data-ttu-id="95660-113">手順 2: PST ファイルをハード ドライブにコピーします。</span><span class="sxs-lookup"><span data-stu-id="95660-113">Step 2: Copy the PST files to the hard drive</span></span>](#step-2-copy-the-pst-files-to-the-hard-drive)

[<span data-ttu-id="95660-114">PST インポート マッピング ファイルを作成する手順 3。</span><span class="sxs-lookup"><span data-stu-id="95660-114">Step 3: Create the PST Import mapping file</span></span>](#step-3-create-the-pst-import-mapping-file)

[<span data-ttu-id="95660-115">手順 4:Office 365 で PST インポート ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="95660-115">Step 4: Create a PST Import job in Office 365</span></span>](#step-4-create-a-pst-import-job-in-office-365)

[<span data-ttu-id="95660-116">手順 5:Microsoft にハード ドライブを送付する</span><span class="sxs-lookup"><span data-stu-id="95660-116">Step 5: Ship the hard drive to Microsoft</span></span>](#step-5-ship-the-hard-drive-to-microsoft)

[<span data-ttu-id="95660-117">手順 6: データをフィルター処理し、PST のインポート ジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="95660-117">Step 6: Filter data and start the PST Import job</span></span>](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> <span data-ttu-id="95660-p102">セキュリティで保護されたストレージ キーおよびインポート ツールをロードする手順の 1 回のみを実行する必要があります。次の手順を実行した後、次の手順 6 を介して手順 2、マイクロソフトのハード ドライブを出荷するたびに。</span><span class="sxs-lookup"><span data-stu-id="95660-p102">You have to perform Step 1 once to down load the secure storage key and the import tool. After you perform these steps, follow Step 2 through Step 6 each time you want to ship a hard drive to Microsoft.</span></span> 
  
<span data-ttu-id="95660-120">頻繁に質問配布の[配布の PST ファイルをインポートするのにはドライブを使用するための Faq](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files)を参照してください PST ファイルを Office 365 にインポートするドライブを使用しています。</span><span class="sxs-lookup"><span data-stu-id="95660-120">For frequently asked questions about using drive shipping to import PST files to Office 365, see [FAQs for using drive shipping to import PST files](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="95660-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="95660-121">Before you begin</span></span>

- <span data-ttu-id="95660-p103">メールボックスのエクスポートをインポートの役割を割り当てるには、Exchange オンライン Office 365 のメールボックスを PST ファイルをインポートするのにはする必要があります。既定では、この役割はありませんに割り当てられている役割グループは、Exchange オンライン。組織の管理役割グループに、メールボックスのインポート エクスポートの役割を追加できます。または、新しい役割グループを作成、メールボックスのインポート エクスポートの役割を割り当てるし、ユーザー自身をメンバーとして追加します。詳細については、追加するロール グループのロール」を参照してください。 または、「作成」の役割グループの[役割グループの管理](https://go.microsoft.com/fwlink/p/?LinkId=730688)のセクションです。</span><span class="sxs-lookup"><span data-stu-id="95660-p103">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
    
    <span data-ttu-id="95660-127">Office 365 のセキュリティのジョブのインポートを作成するのにはさらに、&amp;コンプライアンス センターは、次のいずれかを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="95660-127">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
    
  - <span data-ttu-id="95660-p104">メール受信者の役割を割り当てるには、Exchange オンラインする必要があります。既定では、この役割は組織の管理と受信者の管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="95660-p104">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="95660-130">または</span><span class="sxs-lookup"><span data-stu-id="95660-130">Or</span></span>
    
  - <span data-ttu-id="95660-131">Office 365 の組織のグローバル管理者があります。</span><span class="sxs-lookup"><span data-stu-id="95660-131">You have to be a global administrator in your Office 365 organization.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="95660-p105">Exchange Online の具体的には、Office 365 に PST ファイルをインポートする新しい役割グループを作成することを検討してください。PST ファイルをインポートするのには必要な特権を最低限のレベルで、新しい役割グループにメールボックスのエクスポートをインポートし、メール受信者の役割を割り当てるし、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="95660-p105">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
- <span data-ttu-id="95660-p106">ファイル サーバーまたは組織内の共有フォルダー上のハード ドライブにコピーする PST ファイルを保存する必要があります。手順 2 で、Azure インポート エクスポート ツール (WAImportExport.exe)、このファイル サーバーに保存またはハード ドライブにフォルダーを共有する PST ファイルをコピーするを実行するでしょう。</span><span class="sxs-lookup"><span data-stu-id="95660-p106">You need to store the PST files that you want to copy to a hard drive on a file server or shared folder in your organization. In Step 2, you'll run the Azure Import Export tool (WAImportExport.exe) that will copy the PST files that are stored on this file server or shared folder to the hard drive.</span></span>
    
- <span data-ttu-id="95660-p107">2.5 インチのみソリッド ・ ステート ・ ドライブを (Ssd) または 2.5 または 3.5 インチ SATA II と III の内部ハード ドライブが Office 365 のインポート サービスで使用するためにサポートされています。ハード ドライブを使用することができます最大 10 TB です。インポート ジョブの場合は、ハード ドライブの最初のデータ量のみが処理されます。データ ボリュームは、NTFS でフォーマットする必要があります。ハード ドライブにデータをコピーするときに 2.5 インチ SSD を使用して直接接続することができます 2.5 または 3.5 インチの SATA II と III のコネクタ、または外部の 2.5 インチ SSD を使用して外部にまたは 2.5 または 3.5 インチの SATA II と III の USB アダプターを接続することができます。</span><span class="sxs-lookup"><span data-stu-id="95660-p107">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service. You can use hard drives up to 10 TB. For import jobs, only the first data volume on the hard drive will be processed. The data volume must be formatted with NTFS. When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="95660-p108">組み込みの USB アダプターに付属している外付けのハード ドライブは、Office 365 のインポート サービスでサポートされていません。さらに、大文字と小文字の外付けハード ドライブ内のディスクは使用できません。外付けハード ドライブを出荷しないしてください。</span><span class="sxs-lookup"><span data-stu-id="95660-p108">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives.</span></span> 
  
- <span data-ttu-id="95660-p109">PST ファイルをコピーするハード ドライブは、BitLocker によって暗号化する必要があります。手順 2 を実行する WAImportExport.exe ツールを BitLocker を設定できます。生成されます BitLocker 暗号化キーをマイクロソフトのデータ センターのスタッフを使用して PST ファイルをマイクロソフトのクラウド内の Azure ストレージ領域にアップロードするのにはドライブへのアクセスします。</span><span class="sxs-lookup"><span data-stu-id="95660-p109">The hard drive that you copy the PST files to must be encrypted with BitLocker. The WAImportExport.exe tool that you run in Step 2 will help you set up BitLocker. It also generates a BitLocker encryption key that Microsoft data center personnel will use to access the drive to upload the PST files to the Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="95660-p110">ドライブの出荷は、Microsoft マイクロソフトエンタープライズ契約 (EA) を使用することが可能です。ドライブの出荷は、マイクロソフトの製品およびサービス契約 (MPSA) を使用できません。</span><span class="sxs-lookup"><span data-stu-id="95660-p110">Drive shipping is available through a Microsoft Enterprise Agreement (EA). Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
    
- <span data-ttu-id="95660-p111">ドライブの出荷を使用して Office 365 のメールボックスを PST ファイルをインポートするためのコストは、$2 米ドル 1 GB のデータです。1,000 GB (1 TB) を PST ファイルを格納しているハード ドライブを出荷する場合、コストは $2,000 USD です。インポートの手数料をお支払いするパートナーを使用することができます。パートナーを検索する方法の詳細については[、Office 365 のパートナーまたは販売店を検索](https://go.microsoft.com/fwlink/p/?LinkId=785197)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95660-p111">The cost to import PST files to Office 365 mailboxes using drive shipping is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
    
- <span data-ttu-id="95660-153">お客様またはお客様の組織は、FedEx または DHL のアカウントを持っている必要があります。 </span><span class="sxs-lookup"><span data-stu-id="95660-153">You or your organization must have an account with FedEx or DHL.</span></span>
    
  - <span data-ttu-id="95660-154">米国、ブラジル、およびヨーロッパ内の組織には、FedEx のアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="95660-154">Organizations in the United States, Brazil, and Europe must have FedEx accounts.</span></span>
    
  - <span data-ttu-id="95660-155">東アジア、東南アジア、日本、韓国、オーストラリア内の組織には、DHL のアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="95660-155">Organizations in East Asia, Southeast Asia, Japan, Republic of Korea, and Australia must have DHL accounts.</span></span>
    
    <span data-ttu-id="95660-156">Microsoft はこのアカウントを使用 (または課金) して、ハード ドライブをお客様に返却します。 </span><span class="sxs-lookup"><span data-stu-id="95660-156">Microsoft will use (and charge) this account to return the hard drive back to you.</span></span>
    
- <span data-ttu-id="95660-p112">Microsoft に送付するハード ドライブは、国境を超えて送付される場合があります。この場合は、お客様にはハード ドライブとそれに含まれるデータが適用法に従って輸入または輸出されることを保証する責任があります。ハード ドライブを送付する前に、指定された Microsoft データ センターにハード ドライブとデータを合法的に送付できるか法律顧問と一緒に確認してください。こうすることで、適切なタイミングで確実に Microsoft に届きます。</span><span class="sxs-lookup"><span data-stu-id="95660-p112">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the identified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
    
- <span data-ttu-id="95660-p113">この手順ではコピーして、セキュリティで保護されたストレージ キーと、BitLocker 暗号化キーを保存します。パスワードやその他のセキュリティに関連する情報を保護するようにこれらのキーを保護するために対策を講じていることを確認します。たとえば、パスワードで保護された Microsoft Word 文書に保存したり、暗号化された USB ドライブに保存します。これらのキーの例については、[詳細について](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo)はを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95660-p113">This procedure involves copying and saving a secure storage key and a BitLocker encryption key. Be sure to take precautions to protect these keys like you would protect passwords or other security-related information. For example, you might save them to a password-protected Microsoft Word document or save them to an encrypted USB drive. See the [More information](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) section for an example of these keys.</span></span> 
    
- <span data-ttu-id="95660-p114">PST ファイルが Office 365 のメールボックスにインポートされると、メールボックスの設定の保存は不定の期間のになっています。つまり、メールボックスに割り当てられているリテンション ・ ポリシーは、の保持を無効にするか、保留リストを無効にする日付を設定するまで処理されません。なぜこのような処理でしょうか。メールボックスにインポートするメッセージが古い場合は、それら可能性が完全に削除 (パージ)、メールボックスに対して構成されている保存期間の設定に基づいて、保存期間が期限切れになった。保存保留中のメールボックスを配置することと、これらの新しくインポートされたメッセージまたはメールボックスの保存期間の設定を変更するのには、時間を提供を管理するためにメールボックス所有者の時間が提供されます。保存保留リストの管理に関する推奨事項の[詳細について](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo)はを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95660-p114">After PST files are imported to an Office 365 mailbox, the retention hold setting for the mailbox is turned on for an indefinite duration. This means that the retention policy assigned to the mailbox won't be processed until you turn off the retention hold or set a date to turn off the hold. Why do we do this? If messages imported to a mailbox are old, they might be permanently deleted (purged) because their retention period has expired based on the retention settings configured for the mailbox. Placing the mailbox on retention hold will give the mailbox owner time to manage these newly-imported messages or give you time to change the retention settings for the mailbox. See the [More information](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) section for suggestions about managing the retention hold.</span></span> 
    
- <span data-ttu-id="95660-p115">デフォルトで、Office 365 のメールボックスで受信できるメッセージの最大サイズは 35 MB です。メールボックスの*MaxReceiveSize*プロパティの既定値は 35 MB に設定されているためにです。ただし、制限の Office 365 の最大のメッセージの受信サイズは 150 MB です。150 MB に移動先のメールボックス上の*MaxReceiveSize*プロパティの値を自動的に変更するが、Office 365 にインポート サービス、35 MB を超えるアイテムを含む PST ファイルをインポートする場合。メッセージは、このユーザーのメールボックスにインポートするのには最大 150 MB です。</span><span class="sxs-lookup"><span data-stu-id="95660-p115">By default, the maximum message size that can be received by an Office 365 mailbox is 35 MB. That's because the default value for the  *MaxReceiveSize*  property for a mailbox is set to 35 MB. However, the limit for the maximum message receive size in Office 365 is 150 MB. So if you import a PST file that contains an item larger than 35 MB, the Office 365 Import service we will automatically change the value of the  *MaxReceiveSize*  property on the target mailbox to 150 MB. This allows messages up to 150 MB to be imported to user mailboxes.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="95660-176">サイズを受信するメッセージを識別する、メールボックスの Exchange のオンライン PowerShell でこのコマンドを実行することができます: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。</span><span class="sxs-lookup"><span data-stu-id="95660-176">To identify the message receive size for a mailbox, you can run this command in Exchange Online PowerShell:  `Get-Mailbox <user mailbox> | FL MaxReceiveSize`.</span></span> 
  
- <span data-ttu-id="95660-p116">PST ファイルをインポートするには Office 365 の非アクティブなメールボックスにします。内の非アクティブなメールボックスの GUID を指定することによってこれを行う、 `Mailbox` PST インポート マッピング ファイル内のパラメーターです。参照してください[手順 3: PST インポート マッピング ファイルを作成する](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)の詳細について。</span><span class="sxs-lookup"><span data-stu-id="95660-p116">You can import PST files to an inactive mailbox in Office 365. You do this by specifying the GUID of the inactive mailbox in the  `Mailbox` parameter in the PST Import mapping file. See [Step 3: Create the PST Import mapping file](use-drive-shipping-to-import-pst-files-to-office-365.md#step3) for more information.</span></span> 
    
- <span data-ttu-id="95660-p117">Exchange ハイブリッド展開の場合は、[プライマリ メールボックスは、オンプレミス ユーザーのクラウド ベースのアーカイブ メールボックスに PST ファイルをインポートできます。PST インポート マッピング ファイルで次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="95660-p117">In an Exchange hybrid deployment, you can import PST files to a cloud-based archive mailbox for a user whose primary mailbox is on-premises. You do this by doing the following in the PST Import mapping file:</span></span>
    
  - <span data-ttu-id="95660-182">ユーザーのオンプレミスのメールボックスの電子メール アドレスを指定します`Mailbox`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="95660-182">Specify the email address for the user's on-premises mailbox in the  `Mailbox` parameter.</span></span> 
    
  - <span data-ttu-id="95660-183">**真**の値を指定します`IsArchive`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="95660-183">Specify the **TRUE** value in the  `IsArchive` parameter.</span></span> 
    
    <span data-ttu-id="95660-184">参照してください[手順 3: PST インポート マッピング ファイルを作成する](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)の詳細について。</span><span class="sxs-lookup"><span data-stu-id="95660-184">See [Step 3: Create the PST Import mapping file](use-drive-shipping-to-import-pst-files-to-office-365.md#step3) for more information.</span></span> 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a><span data-ttu-id="95660-185">手順 1: セキュリティで保護されたストレージ キーと PST インポート ツールをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="95660-185">Step 1: Download the secure storage key and PST Import tool</span></span>

<span data-ttu-id="95660-186">最初の手順は、セキュリティで保護されたストレージ キーをダウンロードして、ツールとその使用手順 2 でハード ディスクに PST ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="95660-186">The first step is to download the secure storage key and the tool and that you will use in Step 2 to copy PST files to the hard drive.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="95660-p118">正常にドライブの送付方法を使用して、PST ファイルをインポートするのには、Azure のインポート/エクスポート ツール バージョン 1 (WAimportExportV1) を使用する必要があります。Azure のインポート/エクスポート ツールのバージョン 2 がサポートされていないし、それを使用してハード ディスクのインポート ジョブの準備になります。Azure のインポート/エクスポート ツールは、セキュリティからダウンロードしてください&amp;によって、この手順の手順に従ってコンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="95660-p118">You have to use Azure Import/Export tool version 1 (WAimportExportV1) to successfully import PST files by using the drive shipping method. Version 2 of the Azure Import/Export tool isn't supported and using it will result in incorrectly preparing the hard drive for the import job. Be sure to download the Azure Import/Export tool from the Security &amp; Compliance Center by following the procedures in this step.</span></span> 
  
1. <span data-ttu-id="95660-190">[https://protection.office.com/](https://protection.office.com/)し、組織の Office 365 の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="95660-190">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="95660-191">セキュリティの左側のウィンドウで&amp;コンプライアンス センターでは、**データの管理**をクリックして\>**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="95660-191">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="95660-192">述べたように、セキュリティの**インポート**] ページにアクセスするための適切なアクセス許可を割り当てる必要がある&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="95660-192">As previously stated, you have to be assigned the appropriate permissions to access the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
3. <span data-ttu-id="95660-193">[**インポート**] ページをクリックして![アイコンの追加](media/ITPro-EAC-AddIcon.gif)**新規ジョブをインポート**します。</span><span class="sxs-lookup"><span data-stu-id="95660-193">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
4. <span data-ttu-id="95660-p119">インポート ・ ジョブ ・ ウィザードの PST インポート ジョブの名前を入力し、[**次へ**] をクリックします。小文字の英字、数字、ハイフン、およびアンダー スコアを使用します。大文字を使用して、またはの名前にスペースを追加できません。</span><span class="sxs-lookup"><span data-stu-id="95660-p119">In the import job wizard, type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="95660-197">[**ジョブの種類をインポートするを選択してください**] ページで、**船のハード ドライブの物理的な場所のいずれか**をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-197">On the **Choose import job type** page, click **Ship hard drives to one of our physical locations** and then click **Next**.</span></span>
    
    ![インポート ジョブを配布するドライブを作成する当社の物理的な場所のいずれかに船のハード ドライブをクリックします。](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. <span data-ttu-id="95660-199">**データのインポート**] ページで、次の 2 つの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="95660-199">On the **Import data** page, do the following two things:</span></span> 
    
    ![セキュリティで保護されたストレージ キーをコピーし、データのインポート] ページで、Azure インポート エクスポート ツールをダウンロード](media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    <span data-ttu-id="95660-p120">a: ステップ 2 で、**セキュリティで保護されたストレージ キーのコピー**] をクリックします。ストレージ キーが表示されたら、**クリップボードにコピー** ] をクリックし、貼り付けることとファイルに保存して後で使用するため。</span><span class="sxs-lookup"><span data-stu-id="95660-p120">a. In step 2, click **Copy the secure storage key**. After the storage key is displayed, click **Copy to clipboard** and then paste it and save it to a file so you can access it later.</span></span>
    
    <span data-ttu-id="95660-p121">b. 手順 3、 **Azure のインポート/エクスポート ツールをダウンロード**をダウンロードして、Azure のインポート/エクスポート (バージョン 1) ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="95660-p121">b. In step 3, **Download the Azure Import/Export tool** to download and install the Azure Import/Export (version 1) tool.</span></span>
    
    - <span data-ttu-id="95660-206">ポップアップ ウィンドウで、[**保存**] をクリックします\>**として保存する**に WaImportExportV1.zip ファイルをローカル コンピューター上のフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="95660-206">In the pop-up window, click **Save** \> **Save as** to save the WaImportExportV1.zip file to a folder on your local computer.</span></span> 
    
    - <span data-ttu-id="95660-207">WaImportExportV1.zip ファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="95660-207">Extract the WaImportExportV1.zip file.</span></span>
    
7. <span data-ttu-id="95660-208">ウィザードを閉じるに**キャンセル**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-208">Click **Cancel** to close the wizard.</span></span> 
    
    <span data-ttu-id="95660-209">セキュリティの [**インポート**] ページに戻ること&amp;手順 4 でインポート ジョブを作成するとき、コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="95660-209">You'll come back to the **Import** page in the Security &amp; Compliance Center when you create the import job in Step 4.</span></span> 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a><span data-ttu-id="95660-210">手順 2: PST ファイルをハード ドライブにコピーします。</span><span class="sxs-lookup"><span data-stu-id="95660-210">Step 2: Copy the PST files to the hard drive</span></span>

<span data-ttu-id="95660-p122">次の手順は、WAImportExport.exe ツールを使用して、PST ファイルをハード ドライブにコピーするには。このツールは、ハード ドライブが BitLocker で暗号化、ハード ドライブに、pst ファイルをコピーし、コピー ・ プロセスに関する情報を保存するジャーナル ファイルを作成します。この手順を完了するには、PST ファイルをファイル共有や、組織内のファイル サーバーに配置する必要があります。これは、次の手順でソース ディレクトリと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="95660-p122">The next step is to use the WAImportExport.exe tool to copy PST files to the hard drive. This tool encrypts the hard drive with BitLocker, copies the PSTs to the hard drive, and creates a journal file that stores information about the copy process. To complete this step, the PST files have to be located in a file share or file server in your organization. This is known as the source directory in the following procedure.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="95660-p123">異なる構文を使用する必要がハード ドライブが最初に、WAImportExport.exe ツールを実行して、その後時間。この構文は、PST ファイルをハード ドライブにコピーするには、この手順の手順 4 で説明されています。</span><span class="sxs-lookup"><span data-stu-id="95660-p123">After you run the WAImportExport.exe tool the first time for a hard drive, you have to use a different syntax each time after that. This syntax is explained in step 4 of this procedure to copy PST files to the hard drive.</span></span> 
  
1. <span data-ttu-id="95660-217">ローカル コンピューター上でコマンド プロンプトを開く。</span><span class="sxs-lookup"><span data-stu-id="95660-217">Open a Command Prompt on your local computer.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="95660-p124">管理者としてコマンド プロンプトを実行する場合 (コマンド プロンプトを開く際に [管理者として実行] を選択する)、コマンド プロンプト ウィンドウにエラー メッセージが表示されます。これにより、WAImportExport.exe ツールの実行に関する問題のトラブルシューティングが行えます。</span><span class="sxs-lookup"><span data-stu-id="95660-p124">If you run the command prompt as an administrator (by selecting "Run as administrator" when you open it) error messages will be displayed in the command prompt window. This can help you troubleshoot problems running the WAImportExport.exe tool.</span></span> 
  
2. <span data-ttu-id="95660-220">手順 1 で WAImportExport ツールをインストールしたディレクトリに移動する。</span><span class="sxs-lookup"><span data-stu-id="95660-220">Go to the directory where you installed the WAImportExport.exe tool in Step 1.</span></span>
    
3. <span data-ttu-id="95660-221">初めて WAImportExport.exe を使用してハード ドライブに PST ファイルをコピーする場合は、次のコマンドを実行する。</span><span class="sxs-lookup"><span data-stu-id="95660-221">Run the following command the first time that you use the WAImportExport.exe to copy PST files to a hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>
    ```

    <span data-ttu-id="95660-222">次の表は、パラメーターとそれに必要な値を説明したものです。</span><span class="sxs-lookup"><span data-stu-id="95660-222">The following table describes the parameters and their required values.</span></span>
    
    |<span data-ttu-id="95660-223">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="95660-223">**Parameter**</span></span>|<span data-ttu-id="95660-224">**説明**</span><span class="sxs-lookup"><span data-stu-id="95660-224">**Description**</span></span>|<span data-ttu-id="95660-225">**例**</span><span class="sxs-lookup"><span data-stu-id="95660-225">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `/j:` <br/> |<span data-ttu-id="95660-p125">ジャーナル ファイルの名前を指定します。このファイルは、WAImportExport.exe ツールがあるフォルダーと同じフォルダーに保存されます。Microsoft に送付するハード ドライブごとに 1 つのジャーナル ファイルが必要です。WAImportTool.exe を実行して PST ファイルをハード ドライブにコピーするたびに、そのドライブのジャーナル ファイルに情報が追加されます。 
</span><span class="sxs-lookup"><span data-stu-id="95660-p125">Specifies the name of the journal file. This file is saved to the same folder where the WAImportExport.exe tool is located. Each hard drive you ship to Microsoft must have one journal file. Every time you run the WAImportTool.exe to copy PST files to a hard drive, information will be appended to the journal file for that drive.</span></span>  <br/> <span data-ttu-id="95660-230">Microsoft データ センターのスタッフは、ハード ドライブを手順 4 で作成したインポート ジョブに関連付けると、PST ファイルをマイクロソフトのクラウド内の Azure ストレージ領域にアップロードするのには、ジャーナル ・ ファイルで情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="95660-230">Microsoft data center personnel will use the information in the journal file to associate the hard drive with the import job that you create in Step 4, and to upload the PST files to the Azure storage area in the Microsoft cloud.</span></span>  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |<span data-ttu-id="95660-231">ローカル コンピューターに接続されている場合は、ハード ドライブのドライブ文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="95660-231">Specifies the drive letter of the hard drive when it's connected to your local computer.</span></span>  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |<span data-ttu-id="95660-p126">コピー セッションの名前を指定します。WAImportExport.exe ツールを実行してファイルをハード ドライブにコピーするたびに、セッションが定義されます。PST ファイルは、このパラメーターで指定されたセッション名の名前が付けられたフォルダーにコピーされます。 </span><span class="sxs-lookup"><span data-stu-id="95660-p126">Specifies the name of the copy session. A session is defined as each time you run the WAImportExport.exe tool to copy files to the hard drive. The PST files are copied to a folder named with the session name specified by this parameter.</span></span>  <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |<span data-ttu-id="95660-p127">セッション中にコピーする PST ファイルを含む、組織内には、ソース ディレクトリを指定します。二重引用符では、このパラメーターの値を囲むことを確認する ("")。</span><span class="sxs-lookup"><span data-stu-id="95660-p127">Specifies the source directory in your organization that contains the PST files that will be copied during the session. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |<span data-ttu-id="95660-p128">Pst ファイルがアップロードされるマイクロソフトのクラウド内の Azure ストレージ領域の保存先のディレクトリを指定します。値を使用する必要があります`ingestiondata/`。二重引用符では、このパラメーターの値を囲むことを確認する ("")。</span><span class="sxs-lookup"><span data-stu-id="95660-p128">Specifies the destination directory in the Azure storage area in the Microsoft cloud where the PSTs will be uploaded. You must use the value  `ingestiondata/`. Be sure to surround the value of this parameter with double-quotation marks (" ").  </span></span><br/> <span data-ttu-id="95660-p129">必要に応じて、このパラメーターの値に、追加のファイル パスを追加することも。指定されている (URL の形式に変換) ハード ドライブにソース ディレクトリのファイル パスを使用するなど、`/srcdir:`のパラメーターです。たとえば、`\\FILESERVER01\PSTs`は`FILESERVER01/PSTs`です。この場合、するまだ必要があります`ingestiondata`ファイルのパスにします。この例では、値は、`/dstdir:`パラメーターになります`"ingestiondata/FILESERVER01/PSTs"`。</span><span class="sxs-lookup"><span data-stu-id="95660-p129">Optionally, you can also add an additional file path to the value of this parameter. For example, you can use the file path of the source directory on the hard drive (converted to a URL format) , which is specified in the  `/srcdir:` parameter. For example,  `\\FILESERVER01\PSTs` is changed to  `FILESERVER01/PSTs`. In this case, you still must include  `ingestiondata` in the file path. So in this example, the value for the  `/dstdir:` parameter would be  `"ingestiondata/FILESERVER01/PSTs"`.  </span></span><br/> <span data-ttu-id="95660-245">追加のファイルのパスを追加するのには理由の 1 つは、同じファイル名を Pst ファイルがあるかどうか。</span><span class="sxs-lookup"><span data-stu-id="95660-245">One reason to add the additional file path is if you have PSTs files with the same filename.</span></span>  <br/> <span data-ttu-id="95660-p130">> [!NOTE]> パス名と、PST ファイルの名前場合、省略可能なパス名を含めると、Azure のストレージ領域へのアップロード後に、PST ファイルの名前空間に含まれますたとえば、 `FILESERVER01/PSTs/annb.pst`。パス名を含まない名前空間が、PST ファイル名のみです。たとえば`annb.pst`。</span><span class="sxs-lookup"><span data-stu-id="95660-p130">> [!NOTE]> If you include the optional pathname, the namespace for a PST file after it's uploaded to the Azure storage area will include the pathname and the name of the PST file; for example,  `FILESERVER01/PSTs/annb.pst`. If you don't include a pathname, the namespace is only the PST filename; for example  `annb.pst`.</span></span>           | `/dstdir:"ingestiondata/"` <br/> <span data-ttu-id="95660-248">または</span><span class="sxs-lookup"><span data-stu-id="95660-248">Or</span></span>  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |<span data-ttu-id="95660-p131">手順 1 で取得したストレージ アカウント キーを指定します。二重引用符では、このパラメーターの値を囲むことを確認する ("")。</span><span class="sxs-lookup"><span data-stu-id="95660-p131">Specifies the storage account key that you obtained in Step 1. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/encrypt` <br/> |このスイッチは、ハード ドライブの BitLocker を有効にします。このパラメーターは、WAImportExport.exe ツールを初めて実行する際に必要です。  <br/> <span data-ttu-id="95660-p133">BitLocker 暗号化キーがジャーナル ・ ファイルとログ ファイルを使用する場合に作成されるコピーは、`/logfile:`のパラメーターです。説明したようは、ジャーナル ・ ファイルは、WAImportExport.exe ツールが配置されている同じフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="95660-p133">The BitLocker encryption key is copied to the journal file and the log file that is created if you use the  `/logfile:` parameter. As previously explained, the journal file is saved to the same folder where the WAImportExport.exe tool is located.  </span></span><br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |<span data-ttu-id="95660-p134">この省略可能なパラメーターは、ログ ファイルを保存するフォルダーを指定します。指定しない場合、ログ ファイルは、WAImportExport.exe ツールが配置されている同じフォルダーに保存は。二重引用符では、このパラメーターの値を囲むことを確認する ("")。</span><span class="sxs-lookup"><span data-stu-id="95660-p134">This optional parameter specifies a folder to save log files to. If not specified, the log files are save to the same folder where the WAImportExport.exe tool is located. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    <span data-ttu-id="95660-258">各パラメーターの実際の値を使用する WAImportExport.exe ツールの構文の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="95660-258">Here's an example of the syntax for the WAImportExport.exe tool using actual values for each parameter:</span></span>
    
    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    <span data-ttu-id="95660-p135">コマンドを実行すると、ハード ドライブへの PST ファイルのコピーの進行状況を示す状態メッセージが表示されます。最終の状態メッセージは、正常にコピーされたファイルの合計数を示しています。 </span><span class="sxs-lookup"><span data-stu-id="95660-p135">After you run the command, status messages are displayed that show the progress of copying the PST files to the hard drive. A final status message shows the total number of files that were successfully copied.</span></span>
    
4. <span data-ttu-id="95660-261">このコマンドを、WAImportExport.ext ツールを 2 回目以降に実行するたびに実行して、PST ファイルを同じハード ドライブにコピーする。</span><span class="sxs-lookup"><span data-stu-id="95660-261">Run this command each subsequent time you run the WAImportExport.ext tool to copy PST files to the same hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 
    ```

    <span data-ttu-id="95660-262">以降のセッションを実行して PST ファイルを同じハード ドライブにコピーするための構文の例は、以下の通りです。  </span><span class="sxs-lookup"><span data-stu-id="95660-262">Here's an example of the syntax for running subsequent sessions to copy PST files to the same hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a><span data-ttu-id="95660-263">PST インポート マッピング ファイルを作成する手順 3。</span><span class="sxs-lookup"><span data-stu-id="95660-263">Step 3: Create the PST Import mapping file</span></span>

<span data-ttu-id="95660-p136">インポート サービスが、pst ファイルをユーザーのメールボックスを指定するコンマ区切り値 (CSV) ファイルは、PST のインポート マッピング ・ ファイル内の情報を使用 Microsoft データ センターの担当者は、Azure のストレージ領域には、ハード ドライブから PST ファイルをアップロードした後ファイルにインポートされます。PST インポート ジョブを作成するときは、次の手順では、この CSV ファイルが送信されます。</span><span class="sxs-lookup"><span data-stu-id="95660-p136">After Microsoft data center personnel upload the PST files from the hard drive to the Azure storage area, the Import service will use the information in the PST Import mapping file, which is a comma separated value (CSV) file, that specifies which user mailboxes the PST files will be imported to. You will submit this CSV file in the next step when you create a PST Import job.</span></span>
  
1. <span data-ttu-id="95660-266">[PST インポート マッピング ・ ファイルのコピーをダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=544717)します。</span><span class="sxs-lookup"><span data-stu-id="95660-266">[Download a copy of the PST Import mapping file](https://go.microsoft.com/fwlink/p/?LinkId=544717).</span></span>
    
2. <span data-ttu-id="95660-p137">CSV ファイルを開くか、ローカル コンピューターに保存します。次の例は、完了した PST インポートのマッピング ファイル (メモ帳で開いた) を示しています。Microsoft Excel を使って CSV ファイルを編集するほうが、はるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="95660-p137">Open or save the CSV file to your local computer. The following example shows a completed PST Import mapping file (opened in NotePad). It's much easier to use Microsoft Excel to edit the CSV file.</span></span>

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

    <span data-ttu-id="95660-p138">最初の行、または CSV ファイルのヘッダー行は、PST ファイルをユーザーのメールボックスにインポートする PST インポート サービスによって使用されるパラメーターを一覧表示します。各パラメーター名は、コンマで区切られます。ヘッダー行の下の各行は、特定のメールボックスを PST ファイルをインポートするためのパラメーター値を表します。行は、各ハード ドライブにコピーされた PST ファイルの必要があります。マッピング ファイル内のプレース ホルダーのデータを実際のデータに置き換えることを確認します。</span><span class="sxs-lookup"><span data-stu-id="95660-p138">The first row, or header row, of the CSV file lists the parameters that will be used by the PST Import service to import the PST files to user mailboxes. Each parameter name is separated by a comma. Each row under the header row represents the parameter values for importing a PST file to a specific mailbox. You will need a row for each PST file that was copied to the hard drive. Be sure to replace the placeholder data in the mapping file with your actual data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="95660-275">SharePoint パラメーターなど、ヘッダー行は何も変更しないでください。これらは PST インポートの処理中、無視されます。</span><span class="sxs-lookup"><span data-stu-id="95660-275">Don't change anything in the header row, including the SharePoint parameters; they will be ignored during the PST Import process.</span></span> 
  
3. <span data-ttu-id="95660-276">次の表の情報を使って、必要な情報を含む CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="95660-276">Use the information in the following table to populate the CSV file with the required information.</span></span>
    
    |<span data-ttu-id="95660-277">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="95660-277">**Parameter**</span></span>|<span data-ttu-id="95660-278">**説明**</span><span class="sxs-lookup"><span data-stu-id="95660-278">**Description**</span></span>|<span data-ttu-id="95660-279">**例**</span><span class="sxs-lookup"><span data-stu-id="95660-279">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `Workload` <br/> |<span data-ttu-id="95660-p139">Office 365 サービスにインポートするデータを指定します。PST ファイルをユーザーのメールボックスにインポートするを使用して、 `Exchange`。</span><span class="sxs-lookup"><span data-stu-id="95660-p139">Specifies the Office 365 service that data will be imported to. To import PST files to user mailboxes, use  `Exchange`.  </span></span><br/> | `Exchange` <br/> |
    | `FilePath` <br/> | <span data-ttu-id="95660-282">PST ファイルにコピーされますハード ドライブを出荷時にマイクロソフトが、Azure のストレージ領域にフォルダーの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="95660-282">Specifies the folder location in the Azure storage area that PST files will be copied to when the hard drive is shipped to Microsoft.</span></span>  <br/>  <span data-ttu-id="95660-283">指定では、CSV ファイル内のこの列に追加する、 `/dstdir:` 、前の手順のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="95660-283">What you add in this column in the CSV file depends on what you specified in for the  `/dstdir:` parameter in the previous step.</span></span>  <br/>  <span data-ttu-id="95660-284">使用した場合`/dstdir:"ingestiondata/"`、し、空白のままにこのパラメーターでは、CSV ファイルです。</span><span class="sxs-lookup"><span data-stu-id="95660-284">If you used  `/dstdir:"ingestiondata/"`, then leave this parameter blank in the CSV file.</span></span>  <br/>  <span data-ttu-id="95660-p140">値の任意のパス名が含まれているかどうか、`/dstdir:`パラメーター (たとえば、 `/dstdir:"ingestiondata/FILESERVER01/PSTs"`、("ingestiondata"を除く)、そのパス名を使用して CSV ファイルでこのパラメーターを。このパラメーターの値は、大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="95660-p140">If you included an optional pathname for the value of the  `/dstdir:` parameter (for example,  `/dstdir:"ingestiondata/FILESERVER01/PSTs"`, then use that pathname (not including "ingestiondata") for this parameter in the CSV file. The value for this parameter is case sensitive.  </span></span><br/>  <span data-ttu-id="95660-p141">*どちらにしてがの値に"ingestiondata"を含まない*、`FilePath`のパラメーターです。このパラメーターを空白のままにしておくか、省略可能なパス名のみを指定します。</span><span class="sxs-lookup"><span data-stu-id="95660-p141">Either way,  *don't*  include "ingestiondata" in the value for the  `FilePath` parameter. Leave this parameter blank or specify only the optional pathname.  </span></span><br/> <span data-ttu-id="95660-p142">> [!IMPORTANT]>、ファイルのパス名の大文字と小文字で、同じ大文字と小文字で指定する必要があります、 `/dstdir:` 、前の手順のパラメーターです。使用した場合など、`"ingestiondata/FILESERVER01/PSTs"`で前の手順では、サブフォルダー名を使用していますが、`fileserver01/psts`で、 `FilePath` CSV ファイル内のパラメーター、PST ファイルのインポートは失敗します。両方のインスタンスで、同じ大文字と小文字を使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="95660-p142">> [!IMPORTANT]>  The case for the file path name must be the same case that you specified in the  `/dstdir:` parameter in the previous step . For example, if you used  `"ingestiondata/FILESERVER01/PSTs"` for the subfolder name in the previous step, but then used  `fileserver01/psts` in the  `FilePath` parameter in CSV file, the import for the PST file will fail. Be sure to use the same case in both instances.</span></span>           |<span data-ttu-id="95660-292">(空白)</span><span class="sxs-lookup"><span data-stu-id="95660-292">(leave blank)</span></span>  <br/> <span data-ttu-id="95660-293">または</span><span class="sxs-lookup"><span data-stu-id="95660-293">Or</span></span>  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |<span data-ttu-id="95660-p143">ユーザーのメールボックスにインポートする PST ファイルの名前を指定します。このパラメーターの値は、大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="95660-p143">Specifies the name of the PST file that will be imported to the user mailbox. The value for this parameter is case sensitive.  </span></span><br/> <span data-ttu-id="95660-p144">> [!IMPORTANT]> CSV ファイル内の PST ファイル名の場合は、手順 2 で Azure ストレージの場所にアップロードされた PST ファイルと同じである必要があります。使用する場合など、`annb.pst`で、 `Name` 、CSV ファイルが実際の PST ファイルの名前のパラメーターは、 `AnnB.pst`、その PST ファイルのインポートは失敗します。CSV ファイルに pst ファイルの名前が実際の PST ファイルと同じ大文字と小文字を使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="95660-p144">> [!IMPORTANT]> The case for the PST file name in the CSV file must be the same as the PST file that was uploaded to the Azure storage location in Step 2. For example, if you use  `annb.pst` in the  `Name` parameter in the CSV file, but the name of the actual PST file is  `AnnB.pst`, the import for that PST file will fail. Be sure that the name of the PST in the CSV file uses the same case as the actual PST file.</span></span>           | `annb.pst` <br/> |
    | `Mailbox` <br/> |<span data-ttu-id="95660-p145">PST ファイルをインポートするメールボックスの電子メール アドレスを指定します。PST インポート サービスがパブリック フォルダーを PST ファイルのインポートをサポートしていないために、パブリック フォルダーを指定できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="95660-p145">Specifies the email address of the mailbox that the PST file will be imported to. Note that you can't specify a public folder because the PST Import Service doesn't support importing PST files to public folders.  </span></span><br/> <span data-ttu-id="95660-p146">非アクティブなメールボックスに PST ファイルをインポートするのにはこのパラメーターにメールボックスの GUID を指定する必要です。この GUID を取得するには、Exchange Online で次の PowerShell コマンドを実行します: ' Get メールボックス<identity of inactive mailbox>- InactiveMailboxOnly。</span><span class="sxs-lookup"><span data-stu-id="95660-p146">To import a PST file to an inactive mailbox, you have to specify the mailbox GUID for this parameter. To obtain this GUID, run the following PowerShell command in Exchange Online:  \`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly</span></span> | <span data-ttu-id="95660-303">FL Guid` <br/> > [!NOTE]> In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get メールボックス<identity of active mailbox></span><span class="sxs-lookup"><span data-stu-id="95660-303">FL Guid` <br/> > [!NOTE]> In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox <identity of active mailbox></span></span> | <span data-ttu-id="95660-304">FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command:  `Get メールボックス<identity of soft-deleted or inactive mailbox>- SoftDeletedMailbox</span><span class="sxs-lookup"><span data-stu-id="95660-304">FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command:  `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox</span></span> | <span data-ttu-id="95660-305">FL Guid' です。</span><span class="sxs-lookup"><span data-stu-id="95660-305">FL Guid\`.</span></span>           | `annb@contoso.onmicrosoft.com` <br/> <span data-ttu-id="95660-306">または</span><span class="sxs-lookup"><span data-stu-id="95660-306">Or</span></span>  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | <span data-ttu-id="95660-p147">PST ファイルをユーザーのアーカイブ メールボックスにインポートするかどうかを指定します。次のような 2 つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="95660-p147">Specifies whether or not to import the PST file to the user's archive mailbox. There are two options:  </span></span><br/> <span data-ttu-id="95660-309">**FALSE**PST ファイルをユーザーのプライマリ メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="95660-309">**FALSE** Imports the PST file to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="95660-p148">**場合は TRUE。** PST ファイルをユーザーのアーカイブ メールボックスにインポートします。これを対象とする[ユーザーのアーカイブ メールボックスを有効に](enable-archive-mailboxes.md)するします。このパラメーターを設定する場合は、`TRUE`とは、ユーザーのアーカイブ メールボックスが有効になっていない、そのユーザーのインポートは失敗します。1 人のユーザーのインポートに失敗した場合に注意してください (そのアーカイブが有効になっていないし、このプロパティに設定されているため`TRUE`)、インポート ジョブ内の他のユーザーが影響を受けることはありません。</span><span class="sxs-lookup"><span data-stu-id="95660-p148">**TRUE** Imports the PST file to the user's archive mailbox. This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). If you set this parameter to  `TRUE` and the user's archive mailbox isn't enabled, the import for that user will fail. Note that if an import fails for one user (because their archive isn't enabled and this property is set to  `TRUE`), the other users in the import job won't be affected.  </span></span><br/>  <span data-ttu-id="95660-314">このパラメーターを空白のままにすると、PST ファイルは、ユーザーのプライマリ メールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="95660-314">If you leave this parameter blank, the PST file is imported to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="95660-315">**注:** クラウド ベースのアーカイブ メールボックスがプライマリ メールボックスは、オンプレミス ユーザーの PST ファイルをインポートするを指定するだけ`TRUE`このパラメーターのユーザーのオンプレミスのメールボックスの電子メール アドレスを指定し、`Mailbox`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="95660-315">**Note:** To import a PST file to a cloud-based archive mailbox for a user whose primary mailbox is on-premises, just specify  `TRUE` for this parameter and specify the email address for the user's on-premises mailbox for the  `Mailbox` parameter.</span></span>  <br/> | `FALSE` <br/> <span data-ttu-id="95660-316">または</span><span class="sxs-lookup"><span data-stu-id="95660-316">Or</span></span>  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | <span data-ttu-id="95660-317">PST ファイルをインポートするメールボックス フォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="95660-317">Specifies the mailbox folder that the PST file is imported to.</span></span>  <br/>  <span data-ttu-id="95660-318">このパラメーターを空白のままにする場合は、**インポート済み**の名前付きの ([受信トレイ] フォルダーおよびその他の既定のメールボックス フォルダーと同じレベル) のメールボックスのルート レベルに新しいフォルダーを pst ファイルがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="95660-318">If you leave this parameter blank, the PST will be imported to a new folder named **Imported** located at the root level of the mailbox (the same level as the Inbox folder and the other default mailbox folders).</span></span>  <br/>  <span data-ttu-id="95660-319">指定する場合は、 `/`、PST ファイル内の項目をユーザーの受信トレイ フォルダーに直接インポートされます。</span><span class="sxs-lookup"><span data-stu-id="95660-319">If you specify  `/`, items in the PST file will be imported directly in to the user's Inbox folder.</span></span>  <br/>  <span data-ttu-id="95660-p149">指定する場合は、 `/<foldername>`、という名前のフォルダーにインポートされるアイテムの PST ファイルの*\<フォルダー名\>*。使用する場合など、 `/ImportedPst`、 **ImportedPst**をという名前のフォルダーにアイテムをインポートするとします。このフォルダーは、受信トレイ フォルダーと同じレベルでユーザーのメールボックスに配置されます。</span><span class="sxs-lookup"><span data-stu-id="95660-p149">If you specify  `/<foldername>`, items in the PST file will be imported to a folder named  *\<foldername\>*  . For example, if you use  `/ImportedPst`, items would be imported to a folder named **ImportedPst**. This folder will be located in the user's mailbox at the same level as the Inbox folder.  </span></span><br/> |<span data-ttu-id="95660-323">(空白)</span><span class="sxs-lookup"><span data-stu-id="95660-323">(leave blank)</span></span>  <br/> <span data-ttu-id="95660-324">または</span><span class="sxs-lookup"><span data-stu-id="95660-324">Or</span></span>  <br/>  `/` <br/> <span data-ttu-id="95660-325">または</span><span class="sxs-lookup"><span data-stu-id="95660-325">Or</span></span>  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |<span data-ttu-id="95660-p150">この省略可能なパラメーターでは、ANSI のファイル形式の PST ファイルのインポートに使用するコード ページの数値を指定します。これらの言語が文字をエンコードするための 2 バイト文字セット (DBCS) を通常使用されるため、中国語、日本語、韓国語 (CJK) の組織から PST ファイルをインポートするため、このパラメーターが使用されます。メールボックス フォルダーの名前に DBCS を使用する言語の PST ファイルをインポートするのにはこのパラメーターを使用していない場合は、フォルダー名を多くの場合文字化けする、インポートした後。</span><span class="sxs-lookup"><span data-stu-id="95660-p150">This optional parameter specifies a numeric value for the code page to use for importing PST files in the ANSI file format. This parameter is used for importing PST files from Chinese, Japanese, and Korean (CJK) organizations because these languages typically use a double byte character set (DBCS) for character encoding. If this parameter isn't used to import PST files for languages that use DBCS for mailbox folder names, the folder names are often garbled after they're imported.  </span></span><br/> <span data-ttu-id="95660-329">このパラメーターを使用するのにはサポートされている値のリストは、[コード ページの識別子](https://go.microsoft.com/fwlink/p/?LinkId=328514)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95660-329">For a list of supported values to use for this parameter, see [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).</span></span>  <br/> <span data-ttu-id="95660-p151">> [!NOTE]> 前述したように、これは、オプションのパラメーターと、CSV ファイルに含めるようにする必要はありません。または追加して値を 1 つまたは複数の行の空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="95660-p151">> [!NOTE]> As previously stated, this is an optional parameter and you don't have to include it in the CSV file. Or you can include it and leave the value blank for one or more rows.</span></span>           |<span data-ttu-id="95660-332">(空白)</span><span class="sxs-lookup"><span data-stu-id="95660-332">(leave blank)</span></span>  <br/> <span data-ttu-id="95660-333">または</span><span class="sxs-lookup"><span data-stu-id="95660-333">Or</span></span>  <br/>  <span data-ttu-id="95660-334">`932`(日本語版 ANSI と OEM のコード ページの id です)</span><span class="sxs-lookup"><span data-stu-id="95660-334">`932` (which is the code page identifier for ANSI/OEM Japanese)</span></span>  <br/> |
    | `SPFileContainer` <br/> |<span data-ttu-id="95660-335">PST インポートの場合は、このパラメーターを空白のままにします。 </span><span class="sxs-lookup"><span data-stu-id="95660-335">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="95660-336">該当なし</span><span class="sxs-lookup"><span data-stu-id="95660-336">Not applicable</span></span>  <br/> |
    | `SPManifestContainer` <br/> |<span data-ttu-id="95660-337">PST インポートの場合は、このパラメーターを空白のままにします。 </span><span class="sxs-lookup"><span data-stu-id="95660-337">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="95660-338">該当なし</span><span class="sxs-lookup"><span data-stu-id="95660-338">Not applicable</span></span>  <br/> |
    | `SPSiteUrl` <br/> |<span data-ttu-id="95660-339">PST インポートの場合は、このパラメーターを空白のままにします。 </span><span class="sxs-lookup"><span data-stu-id="95660-339">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="95660-340">該当なし</span><span class="sxs-lookup"><span data-stu-id="95660-340">Not applicable</span></span>  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a><span data-ttu-id="95660-341">手順 4:Office 365 で PST インポート ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="95660-341">Step 4: Create a PST Import job in Office 365</span></span>

<span data-ttu-id="95660-p152">次の手順では、Office 365 のサービスのインポートの PST のインポート ジョブを作成します。手順 3 で作成した PST インポート マッピング ファイルを提出する前に説明したようです。新しいジョブを作成したら、インポート サービス情報を使用して、マッピング ファイルの PST ファイルは、ハード ドライブから、Azure のストレージ領域にコピーされ、作成、インポート ジョブを開始した後、指定したユーザーのメールボックスを PST ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="95660-p152">The next step is to create the PST Import job in the Import service in Office 365. As previously explained, you will submit the PST Import mapping file that you created in Step 3. After you create the new job, the Import service will use the information in the mapping file to import the PST files to the specified user mailbox after the PST files are copied from the hard drive to the Azure storage area and you create and start the import job.</span></span>
  
1. <span data-ttu-id="95660-345">[https://protection.office.com](https://protection.office.com)し、組織の Office 365 の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="95660-345">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="95660-346">セキュリティの左側のウィンドウで&amp;コンプライアンス センターでは、**データの管理**] をクリックし、し、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-346">In the left pane of the Security &amp; Compliance Center, click **Data governance** and then click **Import**.</span></span>
    
3. <span data-ttu-id="95660-347">[**インポート**] ページをクリックして![アイコンの追加](media/ITPro-EAC-AddIcon.gif)**新規ジョブをインポート**します。</span><span class="sxs-lookup"><span data-stu-id="95660-347">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="95660-348">述べたように、セキュリティの**インポート**] ページにアクセスするための適切なアクセス許可を割り当てる必要がある&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="95660-348">As previously stated, you have to be assigned the appropriate permissions to access the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
4. <span data-ttu-id="95660-p153">PST インポート ジョブの名前を入力し、[**次へ**] をクリックします。小文字の英字、数字、ハイフン、およびアンダー スコアを使用します。大文字を使用して、またはの名前にスペースを追加できません。</span><span class="sxs-lookup"><span data-stu-id="95660-p153">Type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="95660-352">[**ジョブの種類をインポートするを選択してください**] ページで、**船のハード ドライブの物理的な場所のいずれか**をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-352">On the **Choose import job type** page, click **Ship hard drives to one of our physical locations** and then click **Next**.</span></span>
    
    ![インポート ジョブを配布するドライブを作成する当社の物理的な場所のいずれかに船のハード ドライブをクリックします。](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. <span data-ttu-id="95660-354">手順 6 では、**マッピング ファイルへのアクセス権がある**と**自分のハード ドライブを準備した、ドライブのために必要なジャーナル ・ ファイルにアクセスして**チェック ボックスをクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-354">In step 6, click the **I've prepared my hard drives and have access to the necessary drive journal files** and **I have access to the mapping file** check boxes, and then click **Next**.</span></span>
    
    ![手順 6 では、2 つのチェック ボックスをクリックします。](media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. <span data-ttu-id="95660-p154">**ドライブのファイルを選択**] ページで、**ドライブのファイルを選択**する] をクリックし、WAImportExport.exe ツールが配置されている同じフォルダーに移動します。手順 2 で作成した仕訳帳ファイルは、このフォルダーにコピーされました。</span><span class="sxs-lookup"><span data-stu-id="95660-p154">On the **Select the drive file** page, click **Select drive file**, and then go to the same folder where the WAImportExport.exe tool is located. The journal file that was created in Step 2 was copied to this folder.</span></span>
    
    ![WAImportExport.exe ツールを実行したときに作成されたジャーナル ・ ファイルを送信する選択ドライブのファイルをクリックします。](media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. <span data-ttu-id="95660-359">ジャーナル ・ ファイルを選択します。たとえば、 `PSTHDD1.jrn`。</span><span class="sxs-lookup"><span data-stu-id="95660-359">Select the journal file; for example, `PSTHDD1.jrn`.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="95660-360">ジャーナル ・ ファイルの名前がで指定された手順 2 で WAImportExport.exe ツールを実行したときに、`/j:`のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="95660-360">When you ran the WAImportExport.exe tool in Step 2, the name of the journal file was specified by the  `/j:` parameter.</span></span> 
  
9. <span data-ttu-id="95660-361">ドライブのファイルの名前は、**ドライブのファイル**名が表示されたら、ドライブ、ファイルにエラーをチェックする**検証**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-361">After the name of the drive file appears under **Drive file name**, click **Validate** to check your drive file for errors.</span></span> 
    
    ![選択したドライブのファイルを検証するために確認] をクリックします。](media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    <span data-ttu-id="95660-p155">ドライブのファイルは、PST インポート ジョブを作成するのには正常に検証するのには。ファイル名が緑に変化が正常に検証された後に注意してください。検証が失敗した場合は、**ログの表示**のリンクをクリックします。ファイルが失敗した理由に関する情報を含むエラー メッセージと、検証エラーのレポートが開かれます。</span><span class="sxs-lookup"><span data-stu-id="95660-p155">The drive file has to be successfully validated to create a PST Import job. Note the file name is changed to green after it's successfully validated. If the validation fails, click the **View log** link. A validation error report is opened, with a error message with information about why the file failed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="95660-367">追加し、各ハード ドライブを Microsoft に送付するためのジャーナル ・ ファイルを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95660-367">You must add and validate a journal file for each hard drive you ship to Microsoft.</span></span> 
  
10. <span data-ttu-id="95660-368">マイクロソフトに出荷することを各ハード ドライブのジャーナル ・ ファイルを検証して後、は、**次**のようにクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-368">After adding and validating a journal file for each hard drive that you'll ship to Microsoft, click **Next**.</span></span>
    
11. <span data-ttu-id="95660-369">クリックして![アイコンの追加](media/ITPro-EAC-AddIcon.gif)**マッピング ファイルを選択して**手順 3 で作成した PST インポート マッピング ファイルを送信する。</span><span class="sxs-lookup"><span data-stu-id="95660-369">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Select mapping file** to submit the PST Import mapping file that you created in Step 3.</span></span> 
    
    ![インポート ジョブの作成した CSV ファイルを送信するのには [マップ ファイル] をクリックします。](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. <span data-ttu-id="95660-371">**マップ ファイル名の**下にある CSV の名の後にファイルが表示されます、CSV ファイルのエラーをチェックする**検証する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-371">After the name of the CSV file appears under **Mapping file name**, click **Validate** to check your CSV file for errors.</span></span> 
    
    ![CSV ファイルにエラーをチェックする検証] をクリックします。](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    <span data-ttu-id="95660-p156">CSV ファイルは、PST のインポート ジョブを作成するのには正常に検証するのには。ファイル名が緑に変化が正常に検証された後に注意してください。検証が失敗した場合は、**ログの表示**のリンクをクリックします。失敗したファイル内の各行についてエラー メッセージと、検証エラーのレポートが開かれます。</span><span class="sxs-lookup"><span data-stu-id="95660-p156">The CSV file has to be successfully validated to create a PST Import job. Note the file name is changed to green after it's successfully validated. If the validation fails, click the **View log** link. A validation error report is opened, with a error message for each row in the file that failed.</span></span> 
    
13. <span data-ttu-id="95660-377">PST のマッピング ファイルが正常に検証されると、**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-377">After the PST mapping file is successfully validated, click **Next**.</span></span>
    
14. <span data-ttu-id="95660-378">**連絡先情報の指定**] ページで、該当するボックスに、連絡先情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="95660-378">On the **Provide contact information** page, type your contact information in the applicable boxes.</span></span> 
    
    <span data-ttu-id="95660-p157">ハード ・ ドライブを出荷するマイクロソフトの場所のアドレスが表示されることに注意してください。このアドレスでは、Office 365 のデータ センターの場所に基づいて自動的に生成されます。このアドレスをファイルにコピーするか、スクリーン ショットします。</span><span class="sxs-lookup"><span data-stu-id="95660-p157">Note that the address for the Microsoft location that you will ship your hard drives to is displayed. This address is auto-generated based on your Office 365 data center location. Copy this address to a file or take a screenshot.</span></span>
    
15. <span data-ttu-id="95660-382">条項および条件のドキュメントを読み取り、チェック ボックス、**保存**インポート ジョブを送信する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-382">Read the terms and conditions document, click the checkbox, and then click **Save** to submit the import job.</span></span> 
    
    <span data-ttu-id="95660-383">インポート ジョブが正常に作成されると、ドライブの出荷プロセスの次の手順を説明するステータス ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95660-383">When the import job is successfully created, a status page is displayed that explains the next steps of the drive shipping process.</span></span>
    
16. <span data-ttu-id="95660-p158">[**インポート**] ページをクリックして![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif)インポート ジョブの一覧で、インポート ジョブを配布する新しいドライブを表示する**更新**をします。**追跡番号の待機**に設定されている注意してください。インポート ジョブに関する詳細な情報が含まれている状態のポップアップ ページを表示するインポート ジョブをクリックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="95660-p158">On the **Import** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to displayed the new drive shipping import job in the list of import jobs. Note that the status is set to **Waiting for tracking number**. You can also click the import job to display the status flyout page, which contains more detailed information about the import job.</span></span>
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a><span data-ttu-id="95660-387">手順 5:Microsoft にハード ドライブを送付する</span><span class="sxs-lookup"><span data-stu-id="95660-387">Step 5: Ship the hard drive to Microsoft</span></span>

<span data-ttu-id="95660-p159">次の手順は、マイクロソフトでは、ハード ドライブを出荷し、出荷の追跡番号を提供し、ドライブ配布ジョブの出荷情報を返すには。ドライブがマイクロソフトによって受信されると、かかるデータの 7 から 10 営業日以内のセンターのスタッフが、組織の Azure ストレージ領域に、PST ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="95660-p159">The next step is to ship the hard drive to Microsoft, and then provide the tracking number for the shipment and return shipment information for the drive shipping job. After the drive is received by Microsoft, it will take between 7 and 10 business days for data center personnel to upload your PST files to the Azure storage area for your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="95660-p160">場合は、追跡番号と、インポート ジョブの作成後 14 日以内の返品荷物の情報を提供しない、インポート ジョブが期限切れにします。インポート ジョブを配布する新しいドライブを作成する必要がありますこのような場合は、(を参照してください[手順 4: Office 365 の PST のインポート ジョブを作成する](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)) とドライブのファイルとマッピング ファイルには、PST のインポートを再送信します。</span><span class="sxs-lookup"><span data-stu-id="95660-p160">If you don't provide the tracking number and return shipment information within 14 days of creating the import job, the import job will be expired. If this happens, you'll have to create a new drive shipping import job (see [Step 4: Create a PST Import job in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)) and re-submit the drive file and the PST import mapping file.</span></span> 
  
### <a name="ship-the-hard-drive"></a><span data-ttu-id="95660-392">ハード ドライブを送付する</span><span class="sxs-lookup"><span data-stu-id="95660-392">Ship the hard drive</span></span>

<span data-ttu-id="95660-393">Microsoft にハード ドライブを送付する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95660-393">Keep the following things in mind when you ship hard drives to Microsoft:</span></span>
  
- <span data-ttu-id="95660-394">USB-シリアル ATA へのアダプターを出荷しません。ハード ディスク ドライブを出荷する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="95660-394">Don't ship the SATA-to-USB adapter; you only have to ship the hard drive.</span></span>
    
- <span data-ttu-id="95660-395">ハード ドライブを適切に梱包する。たとえば、静電気防止バッグやクッション材など使用する。</span><span class="sxs-lookup"><span data-stu-id="95660-395">Package the hard drive properly; for example, use an anti-static bag or bubble wrap.</span></span>
    
- <span data-ttu-id="95660-396">任意の配送業者を使用して、Microsoft にハード ドライブを送付する。</span><span class="sxs-lookup"><span data-stu-id="95660-396">Use a delivery carrier of your choice to ship the hard drive to Microsoft.</span></span>
    
- <span data-ttu-id="95660-p161">手順 4 でインポート ジョブを作成したときに表示されていたマイクロソフトの場所のアドレスをハード ディスク ドライブを出荷してください。配送先のアドレスに「Office 365 サービスのインポート」を含めることを確認します。</span><span class="sxs-lookup"><span data-stu-id="95660-p161">Ship the hard drive to the address for the Microsoft location that was displayed when you created the import job in Step 4. Be sure to include "Office 365 Import Service" in the ship-to address.</span></span>
    
- <span data-ttu-id="95660-p162">ハード ドライブの送付後、配送業者の名前と追跡番号を必ず書き留めてください。これらは次の手順で必要になります。</span><span class="sxs-lookup"><span data-stu-id="95660-p162">After you ship the hard drive, be sure to write down the name of the delivery carrier and the tracking number. You'll provide these in the next step.</span></span>
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a><span data-ttu-id="95660-401">追跡番号と他の配送情報を入力する</span><span class="sxs-lookup"><span data-stu-id="95660-401">Enter the tracking number and other shipping information</span></span>

<span data-ttu-id="95660-402">Microsoft にハード ドライブを送付した後、インポート サービスのページで次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="95660-402">After you've shipped the hard drive to Microsoft, complete the following procedure on the Import service page.</span></span>
  
1. <span data-ttu-id="95660-403">[https://protection.office.com](https://protection.office.com)し、組織の Office 365 の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="95660-403">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="95660-404">左側のウィンドウでは、**データ ・ ガバナンス**をクリックし、し、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-404">In the left pane, click **Data governance** and then click **Import**.</span></span>
    
3. <span data-ttu-id="95660-405">[**インポート**] ページで、ドライブの出荷の追跡番号を入力するジョブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-405">On the **Import** page, click the job for the drive shipment that you want to enter the tracking number for.</span></span> 
    
4. <span data-ttu-id="95660-406">フライアウトの状態] ページで、[**追跡番号の入力**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-406">On the status flyout page, click **Enter tracking number**.</span></span>
    
5. <span data-ttu-id="95660-407">以下の送付情報を入力する。</span><span class="sxs-lookup"><span data-stu-id="95660-407">Provide the following shipping information:</span></span>
    
1. <span data-ttu-id="95660-408">**配信キャリア**マイクロソフトにハード ドライブを出荷するために使用する配信キャリアの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="95660-408">**Delivery carrier** Type the name of the delivery carrier that you used to ship the hard drive to Microsoft.</span></span> 
    
2. <span data-ttu-id="95660-409">**追跡番号**ハード ディスク ドライブの出荷の追跡番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="95660-409">**Tracking number** Type the tracking number for the hard drive shipment.</span></span> 
    
3. <span data-ttu-id="95660-p163">**戻り配送業者アカウント番号****キャリアの取得**の下に表示される通信事業者の組織のアカウント番号を入力します。マイクロソフトを使用して、充電返信して、ハード ディスク ドライブを出荷するには、このアカウント。アメリカ合衆国およびヨーロッパ内の組織が宅配便を持つアカウントを持つ必要がある注意してください。アジアと、世界の残りの部分の組織は、DHL アカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="95660-p163">**Return carrier account number** Type your organization's account number for the carrier that listed under **Return carrier**. Microsoft will use (and charge) this account to ship your hard drive back to you. Note that organizations in the USA and Europe, must have an account with FedEx. Organizations in Asia and the rest of the world, must have an account with DHL.</span></span>
    
6. <span data-ttu-id="95660-414">**[保存]** をクリックして、インポート ジョブのこの情報を保存する。</span><span class="sxs-lookup"><span data-stu-id="95660-414">Click **Save** to save this information for the import job.</span></span> 
    
    <span data-ttu-id="95660-p164">[**インポート**] ページをクリックして![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif)インポート ジョブを配布する、ドライブの情報を更新する**更新**をします。状態は、**輸送中のドライブ**に設定されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="95660-p164">On the **Import** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the information for your drive shipping import job. Notice that status is now set to **Drives in transit**.</span></span>

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a><span data-ttu-id="95660-417">手順 6: データをフィルター処理し、PST のインポート ジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="95660-417">Step 6: Filter data and start the PST Import job</span></span>

<span data-ttu-id="95660-p165">マイクロソフトが、ハード ディスク ドライブが受信されると、**受信したドライブ**に [**インポート**] ページで、インポート ジョブのステータスが変更されます。データ センターのスタッフが情報を使用して、ジャーナル ・ ファイルに、組織、Azure ストレージ領域に、PST ファイルをアップロードします。この時点では、**インポート中**に、ステータスが変更されます。前述したように、PST ファイルをアップロードするのにはハード ディスク ドライブを受信した後、7 ~ 10 営業日間かかります。</span><span class="sxs-lookup"><span data-stu-id="95660-p165">After your hard drive is received by Microsoft, the status for the import job on the **Import** page will change to **Drives received**. Data center personnel will use the information in the journal file to upload your PST files to the Azure storage area for your organization. At this point, the status will change to **Import in-progress**. As previously stated, it will take between 7 to 10 business days after receiving your hard drive to upload the PST files.</span></span>
  
<span data-ttu-id="95660-p166">PST ファイルは、Azure にアップロードした後、**分析**にステータスが変更されます。これは、Office 365 は、PST ファイル内のデータ (方法での分析安全かつセキュリティで保護された) 項目と PST ファイルに含まれている別のメッセージの種類の保存期間を識別することを示します。分析が完了して、データをインポートする準備が、**分析を完了**するのにはインポート ジョブのステータスが変更されます。この時点では、PST ファイルに含まれるすべてのデータをインポートするオプションがあるか、インポートされたデータを取得するかを制御するフィルターを設定することによってインポートされたデータをトリミングすることができます。</span><span class="sxs-lookup"><span data-stu-id="95660-p166">After PST files are uploaded to Azure, the status is changed to **Analysis in progress**. This indicates that Office 365 is analyzing the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files. When the analysis is completed and the data is ready to import, the status for the import job is changed to **Analysis completed**. At this point, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span>
  
1. <span data-ttu-id="95660-426">[https://protection.office.com](https://protection.office.com)し、組織の Office 365 の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="95660-426">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="95660-427">左側のウィンドウで [**データ管理**] をクリックします > **インポート**します。</span><span class="sxs-lookup"><span data-stu-id="95660-427">In the left pane, click **Data governance** > **Import**.</span></span>
    
3. <span data-ttu-id="95660-428">[**インポート**] ページで、手順 4 で作成したインポート ジョブの**Office 365 にインポートする準備ができました**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-428">On the **Import** page, click **Ready to import to Office 365** for the import job that you created in Step 4.</span></span> 
    
    ![作成したインポート ジョブの横にある Office 365 にインポートする準備ができました] をクリックします。](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    <span data-ttu-id="95660-430">ページをその場は、PST ファイルの情報とインポート ジョブに関する他の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="95660-430">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="95660-431">**Office 365 にインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-431">Click **Import to Office 365**.</span></span>
    
5. <span data-ttu-id="95660-p167">**データにフィルターをかける**] ページが表示されます。PST ファイルのデータの保存期間に関する情報を含め、Office 365 による分析の結果データの分析が含まれています。この時点で、インポートするかが格納されるすべてのデータをインポートするデータをフィルター処理するためのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="95660-p167">The **Filter your data** page is displayed. It contains the data insights resulting from the analysis performed on the PST files by Office 365, including information about the age of the data. At this point, you have the option to filter the data that will be imported or import all the data as is.</span></span> 
    
    ![PST ファイル内のデータをトリミングしたり、すべてのインポート](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. <span data-ttu-id="95660-436">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="95660-436">Do one of the following:</span></span>
    
    <span data-ttu-id="95660-p168">a. トリムするのにはインポートしたデータを**インポートする前にフィルター処理する**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-p168">a. To trim the data that you import, click **Yes, I want to filter it before importing**.</span></span>
    
    <span data-ttu-id="95660-439">PST ファイル内のデータをフィルター処理とインポート ジョブを開始し、ステップ バイ ステップの詳細については、 [Office 365 に PST ファイルをインポートするときにデータをフィルター処理](filter-data-when-importing-pst-files.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95660-439">For detailed step-by-step instructions about filtering the data in the PST files and then starting the import job, see [Filter data when importing PST files to Office 365](filter-data-when-importing-pst-files.md).</span></span>
    
    <span data-ttu-id="95660-440">または</span><span class="sxs-lookup"><span data-stu-id="95660-440">Or</span></span>
    
    <span data-ttu-id="95660-p169">b. PST ファイル内のすべてのデータをインポートするに**なしで、すべてをインポートする**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-p169">b. To import all data in the PST files, click **No, I want to import everything,** and click **Next**.</span></span>
    
7. <span data-ttu-id="95660-443">すべてのデータをインポートする] を選択した場合は、**データをインポートする**インポート ジョブを開始するをクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-443">If you chose to import all the data, click **Import data** to start the import job.</span></span> 
    
    <span data-ttu-id="95660-p170">[**インポート**] ページで、インポート ジョブのステータスが表示されます。クリックして![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif)[**状態**] 列に表示されるステータス情報を更新する**更新**をします。インポートする各 PST ファイルのステータス情報を表示するステータス フライアウトのページを表示するインポート ジョブをクリックします。インポートが完了し、PST ファイルをユーザーのメールボックスにインポートしたときにステータスが**完了済**] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="95660-p170">The status of the import job is displayed on the **Import** page. Click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the status information that's displayed in the **Status** column. Click the import job to display the status flyout page, which displays status information about each PST file being imported. When the import is complete and PST files have been imported to user mailboxes, the status will be changed to **Completed**.</span></span>

## <a name="view-a-list-of-the-pst-files-uploaded-to-office-365"></a><span data-ttu-id="95660-448">Office 365 にアップロードされた PST ファイルの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="95660-448">View a list of the PST files uploaded to Office 365</span></span>

<span data-ttu-id="95660-p171">インストールし、組織の Azure ストレージ領域に (マイクロソフトのデータ センターのスタッフ) をアップロードしたしていること PST ファイルの一覧を表示するのには、Azure ストレージ エクスプ ローラーは、無料のオープン ソースのツール) を使用できます。PST ファイルをマイクロソフトに送信したハード ドライブからが、Azure のストレージ領域を正常にアップロードされたことを確認するのにはこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="95660-p171">You can install and use the Microsoft Azure Storage Explorer (which is a free, open source tool) to view the list of the PST files that we're uploaded (by Microsoft data center personnel) to the Azure storage area for your organization. You can do this to verify that PST files from the hard drives that you sent to Microsoft were successfully uploaded to the Azure storage area.</span></span>
  
<span data-ttu-id="95660-451">プレビューでは、Microsoft Azure ストレージ エクスプ ローラーです。</span><span class="sxs-lookup"><span data-stu-id="95660-451">The Microsoft Azure Storage Explorer is in Preview.</span></span>
  
 <span data-ttu-id="95660-p172">**重要な:** アップロードまたは PST ファイルを変更するには、Azure ストレージ エクスプ ローラーを使うことはできません。Office 365 に PST ファイルをインポートするための唯一のサポートされている方法では、AzCopy を使用します。また、Azure blob にアップロードしている PST ファイルを削除できません。PST ファイルを削除しようとすると、必要な権限がないというエラー メッセージが表示されます。Azure ストレージ領域からすべての PST ファイルを自動的に削除するに注意してください。進行中のインポート ジョブはありませんし、内のすべての PST ファイルがある場合、* * ingestiondata * * コンテナーは、最新のインポート ジョブを作成した後 30 日を削除します。</span><span class="sxs-lookup"><span data-stu-id="95660-p172">**Important:** You can't use the Azure Storage Explorer to upload or modify PST files. The only supported method for importing PST files to Office 365 is to use AzCopy. Also, you can't delete PST files that you've uploaded to the Azure blob. If you try to delete a PST file, you'll receive an error about not having the required permissions. Note that all PST files are automatically deleted from your Azure storage area. If there are no import jobs in progress, then all PST files in the ** ingestiondata ** container are deleted 30 days after the most recent import job was created.</span></span> 
  
<span data-ttu-id="95660-458">Azure ストレージ エクスプ ローラーをインストールし、Azure のストレージ領域への接続します。</span><span class="sxs-lookup"><span data-stu-id="95660-458">To install the Azure Storage Explorer and connect to your Azure storage area:</span></span>
  
1. <span data-ttu-id="95660-p173">組織の共有アクセス署名 (SAS) URL を取得するのには次の手順を実行します。この URL は、組織と、SA のキーをマイクロソフトのクラウド内の Azure ストレージ場所のネットワークの URL の組み合わせです。このキーは、組織の Azure ストレージの場所にアクセスするために必要なアクセス許可を提供します。</span><span class="sxs-lookup"><span data-stu-id="95660-p173">Perform the following steps to get the Shared Access Signature (SAS) URL for your organization. This URL is a combination of the network URL for the Azure storage location in the Microsoft cloud for your organization and an SAS key. This key provides you with the necessary permissions to access your organization's Azure storage location.</span></span>
    
1. <span data-ttu-id="95660-462">[https://protection.office.com/](https://protection.office.com/)し、組織の Office 365 の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="95660-462">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="95660-463">セキュリティの左側のウィンドウで&amp;コンプライアンス センターでは、**データの管理**をクリックして\>**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="95660-463">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
3. <span data-ttu-id="95660-464">[**インポート**] ページをクリックして![アイコンの追加](media/ITPro-EAC-AddIcon.gif)**新規ジョブをインポート**します。</span><span class="sxs-lookup"><span data-stu-id="95660-464">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
4. <span data-ttu-id="95660-p174">インポート ・ ジョブ ・ ウィザードの PST インポート ジョブの名前を入力し、[**次へ**] をクリックします。小文字の英字、数字、ハイフン、およびアンダー スコアを使用します。大文字を使用して、またはの名前にスペースを追加できません。</span><span class="sxs-lookup"><span data-stu-id="95660-p174">In the import job wizard, type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="95660-468">**ジョブの種類をインポートするを選択してください**] ページで、**データのアップロード**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-468">On the **Choose import job type** page, click **Upload your data** and then click **Next**.</span></span>
    
6. <span data-ttu-id="95660-469">ステップ 2 で、**ネットワークのアップロード URL の SA を表示する**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-469">In step 2, click **Show network upload SAS URL**.</span></span>
    
7. <span data-ttu-id="95660-p175">URL が表示されたら、コピーし、ファイルに保存します。URL 全体をコピーすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="95660-p175">After the URL is displayed, copy it and save it to a file. Be sure to copy the entire URL.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="95660-p176">SAS URL を保護するために対策を講じていることを確認します。これは、組織、Azure のストレージ領域にアクセスするすべてのユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="95660-p176">Be sure to take precautions to protect the SAS URL. This can be used by anyone to access the Azure storage area for your organization.</span></span> 
  
8. <span data-ttu-id="95660-474">インポート ジョブ ・ ウィザードを閉じるに**キャンセル**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-474">Click **Cancel** to close the import job wizard.</span></span> 
    
2. <span data-ttu-id="95660-475">ダウンロードして、 [Microsoft Azure ストレージ エクスプ ローラー ツール](https://go.microsoft.com/fwlink/p/?LinkId=544842)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="95660-475">Download and install the [Microsoft Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span>
    
3. <span data-ttu-id="95660-476">Microsoft Azure ストレージ エクスプ ローラーを起動左側のウィンドウで、**ストレージ アカウント**を右クリックし、 **Azure ストレージへの接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-476">Start the Microsoft Azure Storage Explorer, right-click **Storage Accounts** in the left pane, and then click **Connect to Azure storage**.</span></span>
    
    ![ストレージ アカウントを右クリックし、Azure ストレージに接続] をクリックし、](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. <span data-ttu-id="95660-478">**共有アクセス署名 (SAS) URI、または接続文字列を使用**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-478">Click **Use a shared access signature (SAS) URI or connection string** and click **Next**.</span></span>
    
5. <span data-ttu-id="95660-479">**SAS の URI を使用**] をクリックして、手順 1 で [ **URI**] ボックスで取得した SAS の URL を貼り付けるし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95660-479">Click **Use a SAS URI**, paste the SAS URL that you obtained in step 1 in to in the box under **URI**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="95660-480">[**接続の概要**] ページで、接続情報を確認し、[**接続**] をクリックできます。</span><span class="sxs-lookup"><span data-stu-id="95660-480">On the **Connection summary** page, you can review the connection information, and then click **Connect**.</span></span>
    
    <span data-ttu-id="95660-p177">**Ingestiondata**コンテナーを開きます。ハード ドライブから PST ファイルが含まれています。**Ingestiondata**コンテナーは、**ストレージ アカウント**の下にある\> **(SAS-Attached サービス)** \> **Blob コンテナー**です。</span><span class="sxs-lookup"><span data-stu-id="95660-p177">The **ingestiondata** container is opened; it contains the PST files from your hard drive. The **ingestiondata** container is located under **Storage Accounts** \> **(SAS-Attached Services)** \> **Blob Containers**.</span></span>
    
    ![Azure ストレージ エクスプローラーには、アップロードした PST ファイルの一覧が表示される](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. <span data-ttu-id="95660-p178">Microsoft Azure ストレージ エクスプ ローラーの使用が終了したら、 **ingestiondata**を右クリックし、Azure のストレージ領域から切断するのには**接続解除**] をクリックします。それ以外の場合、次に接続しようとするとき、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95660-p178">When you're finished using the Microsoft Azure Storage Explorer, right-click **ingestiondata**, and then click **Detach** to disconnect from your Azure storage area. Otherwise, you'll receive an error the next time you try to attach.</span></span> 
    
    ![ingestion を右クリックして [デタッチ] をクリックし、Azure のストレージ エリアから切断する](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  

  
## <a name="troubleshooting-tips"></a><span data-ttu-id="95660-487">トラブルシューティングのヒント</span><span class="sxs-lookup"><span data-stu-id="95660-487">Troubleshooting tips</span></span>
<span data-ttu-id="95660-488"><a name="troubleshootingtips"> </a></span><span class="sxs-lookup"><span data-stu-id="95660-488"></span></span>

- <span data-ttu-id="95660-p179">**PST インポート CSV マッピング ファイル内のエラーが発生したためインポート ジョブが失敗した場合はどうなるか?** インポート ジョブでは、マッピング ・ ファイル内のエラーにより失敗した場合、再インポート ジョブを新規作成するためにマイクロソフトにハード ドライブを出荷する必要はありません。組織、Azure のストレージ領域に既に送信したハード ドライブからのドライブ出荷インポート ジョブの PST ファイルがアップロードされているためにです。この場合、だけ、PST インポート CSV マッピング ・ ファイルのエラーを修正し新しい「ネットワーク アップロード」インポート ジョブを作成し、改訂された CSV マッピング ファイルを送信する必要があります。作成し、新しいネットワークのアップロードのインポート ジョブを開始するを参照してください[手順 5: Office 365 の PST のインポート ジョブを作成する](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365)と[手順 6: データをフィルター処理し、PST のインポート ジョブを開始](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job)」使用ネットワークへのアップロードを Office 365 に PST ファイルをインポートします」のトピックで。</span><span class="sxs-lookup"><span data-stu-id="95660-p179">**What happens if the import job fails because of errors in the PST Import CSV mapping file?** If an import job fails because of errors in the mapping file, you don't have to re-ship the hard drive to Microsoft in order to create a new import job. That's because the PST files from the hard drive that you submitted for the drive shipping import job have already been uploaded to the Azure storage area for your organization. In this case, you just have to fix the errors in the PST Import CSV mapping file, and then create a new "network upload" import job and submit the revised CSV mapping file. To create and start a new network upload import job, see [Step 5: Create a PST Import job in Office 365](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365) and [Step 6: Filter data and start the PST Import job](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job) in the topic "Use network upload to import PST files to Office 365."</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="95660-p180">PST インポート CSV マッピング ファイルをトラブルシューティングするために、Azure のストレージ領域にアップロードされたハード ドライブからの PST ファイルの**ingestiondata**コンテナー内のフォルダー構造を表示するのには、 [Azure ストレージ エクスプ ローラー](#view-a-list-of-the-pst-files-uploaded-to-office-365)ツールを使用します。マッピング ファイルのエラーは、通常、FilePath パラメーターの値が正しくないによって発生します。このパラメーターは、Azure のストレージ領域に、PST ファイルの場所を指定します。[手順 3](#step-3-create-the-pst-import-mapping-file)の表でファイルのパスのパラメーターの説明を参照してください。指定されたが、Azure のストレージ領域に PST ファイルの場所に説明したよう、 `/dstdir:` [手順 2](#step-2-copy-the-pst-files-to-the-hard-drive)で WAImportExport.exe ツールを実行したときのパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="95660-p180">To help you troubleshoot the PST Import CSV mapping file, use the [Azure Storage Explorer](#view-a-list-of-the-pst-files-uploaded-to-office-365) tool to view the folder structure in the **ingestiondata** container for the PST files from your hard drive that were uploaded to the Azure storage area. Mapping file errors are typically caused by an incorrect value in the FilePath parameter. This parameter specifies the location of a PST file in the Azure storage area. See the description of the FilePath parameter in table in [Step 3](#step-3-create-the-pst-import-mapping-file). As previously explained, the location of PST files in the Azure storage area was specified by the  `/dstdir:` parameter when you ran the WAImportExport.exe tool in [Step 2](#step-2-copy-the-pst-files-to-the-hard-drive).</span></span> 
  

  
## <a name="more-information"></a><span data-ttu-id="95660-499">詳細情報</span><span class="sxs-lookup"><span data-stu-id="95660-499">More information</span></span>

- <span data-ttu-id="95660-p181">ドライブの出荷は、大量のメッセージング データのアーカイブを組織に利用可能なコンプライアンス機能を活用するのには Office 365 にインポートするのには効果的な方法です。アーカイブ ・ データがユーザーのメールボックスにインポートされると、以下の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="95660-p181">Drive shipping is an effective way to import large amounts of archival messaging data to Office 365 to take advantage of the compliance features that are available to your organization. After archival data is imported to user mailboxes, you can:</span></span>
    
  - <span data-ttu-id="95660-502">[メールボックスのアーカイブ](enable-archive-mailboxes.md)およびデータの記憶域の追加のメールボックスをユーザーに付与する[アーカイブの自動拡張](enable-unlimited-archiving.md)を有効にします。</span><span class="sxs-lookup"><span data-stu-id="95660-502">Enable [archive mailboxes](enable-archive-mailboxes.md) and [auto-expanding archiving](enable-unlimited-archiving.md) to give users additional mailbox storage space for the data.</span></span> 
    
  - <span data-ttu-id="95660-503">[証拠保全](https://go.microsoft.com/fwlink/?linkid=856286)データを保持するには、メールボックスを配置します。</span><span class="sxs-lookup"><span data-stu-id="95660-503">Place mailboxes on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) to retain the data.</span></span> 
    
  - <span data-ttu-id="95660-504">データを検索するのにには、マイクロソフトの[電子的証拠開示のツール](search-for-content.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="95660-504">Use Microsoft [eDiscovery tools](search-for-content.md) to search the data.</span></span> 
    
  - <span data-ttu-id="95660-505">データの保存期間と保存期間が終了した後に実行するには、どのようなアクションを制御するのには[Office 365 の保存ポリシー](retention-policies.md)を適用します。</span><span class="sxs-lookup"><span data-stu-id="95660-505">Apply [Office 365 retention policies](retention-policies.md) to control how long the data is retained, and what action to take after the retention period expires.</span></span> 
    
  - <span data-ttu-id="95660-506">このデータに関連するイベントの[Office 365 の監査ログ](search-the-audit-log-in-security-and-compliance.md)を検索します。</span><span class="sxs-lookup"><span data-stu-id="95660-506">Search the [Office 365 audit log](search-the-audit-log-in-security-and-compliance.md) for events related to this data.</span></span> 
    
  - <span data-ttu-id="95660-507">コンプライアンスのためのデータをアーカイブするのには[アクティブでないメールボックス](create-and-manage-inactive-mailboxes.md)にデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="95660-507">Import data to [inactive mailboxes](create-and-manage-inactive-mailboxes.md) to archive data for compliance purposes.</span></span> 
    
  - <span data-ttu-id="95660-508">組織[データの損失](data-loss-prevention-policies.md)からの機密情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="95660-508">Protect your organization against [data loss](data-loss-prevention-policies.md) of sensitive information.</span></span> 
    
- <span data-ttu-id="95660-p182">セキュリティで保護されたストレージ アカウント キーと BitLocker 暗号化キーの例を、次に示します。この例には、ハード ディスクに PST ファイルをコピーするために実行する WAImportExport.exe コマンドの構文も含まれています。パスワードやその他のセキュリティ関連情報を保護するのと同じように、これらのファイルを保護するための予防策を必ず講じてください。</span><span class="sxs-lookup"><span data-stu-id="95660-p182">Here's an example of the secure storage account key and a BitLocker encryption key. This example also contains the syntax for the WAImportExport.exe command that you run to copy PST files to a hard drive. Be sure to take precautions to protect these just like you would protect passwords or other security-related information.</span></span>
    

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
   
- <span data-ttu-id="95660-p183">説明したよう Office 365 のインポート サービスをオンに設定 (不定の期間) のメールボックスを PST ファイルをインポートした後に保持します。つまり、 *RentionHoldEnabled*プロパティに設定されて`True`メールボックスに割り当てられているリテンション ・ ポリシーを処理しないようにします。これには、削除したり、古いメッセージをアーカイブするアーカイブ ポリシーの削除を防止することで、新しくインポートされたメッセージを管理するためにメールボックス所有者の時間が与えられます。この保持を管理するためのいくつかの手順を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="95660-p183">As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RentionHoldEnabled*  property is set to  `True` so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold:</span></span> 
    
  - <span data-ttu-id="95660-p184">後、一定時間、オフにできます、保存を実行して、`Set-Mailbox -RetentionHoldEnabled $false`コマンドです。手順については、[保存上のメールボックスの場所を保持](https://go.microsoft.com/fwlink/p/?LinkId=544749)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95660-p184">After a certain period of time, you can turn off the retention hold by running the  `Set-Mailbox -RetentionHoldEnabled $false` command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).</span></span>
    
  - <span data-ttu-id="95660-p185">無効になって、将来的にいくつかの日付にするため、保持を構成できます。これを実行するのには、`Set-Mailbox -EndDateForRetentionHold <date>`コマンドです。たとえば、今日の日付は 2016 年 7 月 1 日、30 日以内にオフに保持する、ことを前提としては、次のコマンドを実行、: `Set-Mailbox -EndDateForRetentionHold 8/1/2016`。このシナリオでは、 *RentionHoldEnabled*プロパティを*True*に設定のままにします。詳細については、[一連のメールボックス](https://go.microsoft.com/fwlink/p/?LinkId=150317)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95660-p185">You can configure the retention hold so that it's turned off on some date in the future. You do this by running the  `Set-Mailbox -EndDateForRetentionHold <date>` command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. In this scenario, you would leave the  *RentionHoldEnabled*  property set to  *True*  . For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).</span></span>
    
  - <span data-ttu-id="95660-p186">できるように、すぐに削除またはユーザーのアーカイブ メールボックスに移動しないインポートされた古いアイテムは、メールボックスに割り当てられているリテンション ・ ポリシーの設定を変更することができます。たとえば、削除またはアーカイブ メールボックスに割り当てられているポリシーの保有期間を長く可能性があります。このシナリオでは無効にするメールボックスに保持リテンション ・ ポリシーの設定を変更した後。詳細については、 [Office 365 の組織内のメールボックスのアーカイブと削除ポリシーの設定](set-up-an-archive-and-deletion-policy-for-mailboxes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95660-p186">You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>
    

  

