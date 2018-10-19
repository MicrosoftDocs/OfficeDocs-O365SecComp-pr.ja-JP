---
title: Overview of importing your organization PST files to Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: '管理者: インポート サービスを使用して Office 365 のセキュリティについて&amp;Exchange Online でユーザーのメールボックスに電子メール (PST ファイル) のデータを一括インポートするコンプライアンス センターです。このトピックでは、Faq を提供し、PST のインポート プロセスのしくみについて説明します。'
ms.openlocfilehash: 3a6c3db966513be5c63588dac75643ffc1962323
ms.sourcegitcommit: 8294182d4dd124f035a221de0b90159ef7eec4ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2018
ms.locfileid: "25639676"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a><span data-ttu-id="32db2-104">Overview of importing your organization PST files to Office 365</span><span class="sxs-lookup"><span data-stu-id="32db2-104">Overview of importing your organization PST files to Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="32db2-p102">この資料では、管理者用です。自分のメールボックスを PST ファイルをインポートしようとしていますか。[インポート電子メール、連絡先、および Outlook の .pst ファイルから予定表](https://go.microsoft.com/fwlink/p/?LinkID=785075)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32db2-p102">This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)</span></span>

<span data-ttu-id="32db2-p103">インポート サービスを使用するには Office 365 のセキュリティで&amp;、Office 365 の組織内の Exchange Online のメールボックスにファイルを簡単に一括インポート PST にコンプライアンス センターです。PST ファイルをインポートするには Office 365 に 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="32db2-p103">You can use the Import service in the Office 365 Security &amp; Compliance Center to quickly bulk-import PST files to Exchange Online mailboxes in your Office 365 organization. There are two ways you can import PST files to Office 365:</span></span>
   
- <span data-ttu-id="32db2-p104">**ネットワークのアップロード**![クラウドにアップロード](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png)-マイクロソフトのクラウド内の Azure ストレージの一時的な場所にネットワーク経由で PST ファイルをアップロードします。Office 365 の組織内のメールボックスに PST のデータをインポートするのには Office 365 のインポート サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="32db2-p104">**Network upload** ![Cloud upload](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - Upload the PST files over the network to a temporary Azure storage location in the Microsoft cloud. Then you use the Office 365 Import service to import the PST data to mailboxes in your Office 365 organization.</span></span> 

- <span data-ttu-id="32db2-p105">**ドライブの出荷**![ハード ディスク](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png)- BitLocker で暗号化されたハード ディスクに PST ファイルをコピーし、Microsoft にドライブを物理的に出荷します。マイクロソフトでは、ハード ディスク ドライブを受信すると、データ センターのスタッフは、マイクロソフト クラウド内の Azure ストレージの一時的な場所にデータをアップロードします。Office 365 のインポート サービスを使用するには、Office 365 の組織内のメールボックスにデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="32db2-p105">**Drive shipping** ![Hard disk](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - Copy the PST files to a BitLocker-encrypted hard drive and then physically ship the drive to Microsoft. When Microsoft receives the hard drive, data center personnel upload the data to a temporary Azure storage location in the Microsoft cloud. Then you use the Office 365 Import service to import the data to mailboxes in your Office 365 organization.</span></span>

## <a name="step-by-step-instructions"></a><span data-ttu-id="32db2-115">手順</span><span class="sxs-lookup"><span data-stu-id="32db2-115">Step-by-step instructions</span></span>
  
<span data-ttu-id="32db2-116">Office 365 の組織の PST ファイルを一括インポートの手順については、詳細な手順を次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32db2-116">See one of the following topics for detailed, step-by-step instructions for bulk-importing your organization's PST files to Office 365.</span></span> 
   
- [<span data-ttu-id="32db2-117">ネットワーク アップロードを使用して PST ファイルを Office 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="32db2-117">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
- [<span data-ttu-id="32db2-118">ドライブ送付を使用して PST ファイルを Office 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="32db2-118">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a><span data-ttu-id="32db2-119">PST ファイルのインポートのしくみ</span><span class="sxs-lookup"><span data-stu-id="32db2-119">How importing PST files works</span></span>

<span data-ttu-id="32db2-p106">ここでは、図と包括的な PST のインポート プロセスの説明です。図は、プライマリ ワークフローを示していて、ネットワークのアップロードとドライブの送付方法の違いを強調表示。</span><span class="sxs-lookup"><span data-stu-id="32db2-p106">Here's an illustration and description of the complete PST import process. The illustration shows the primary workflow and highlights the differences between the network upload and drive shipping methods.</span></span>
  
![PST インポート プロセスのワークフロー](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. <span data-ttu-id="32db2-p107">**ダウンロード PST のインポート ツールおよびプライベート キーの Azure ストレージの場所**の最初のステップには、PST ファイルをアップロードまたはハード ドライブにコピーするために使用するツールとアクセス キーをダウンロードします。これらの Office 365 のセキュリティで [**インポート**] ページから取得する&amp;コンプライアンス センターです。キーは、プライベートとセキュリティで保護された Azure のストレージの場所に PST ファイルをアップロードするために必要なアクセス許可を持つ場合に、Microsoft データ センターのスタッフがドライブの出荷の場合) を提供します。このアクセス キーは、組織に固有で、マイクロソフトのクラウドにアップロードしたファイルは、PST ファイルに不正なアクセスを防ぐことがOffice 365 に PST ファイルをインポートするを必要としない独立した Azure サブスクリプションを持つ組織に注意してください。</span><span class="sxs-lookup"><span data-stu-id="32db2-p107">**Download the PST import tools and key to private Azure storage location** - The first step is to download the tool and access key used to upload the PST files or copy them to a hard drive. You obtain these from the **Import** page in the Office 365 Security &amp; Compliance Center. The key provides you (or Microsoft data center personnel in the case of drive shipping) with the necessary permissions to upload PST files to a private and secure Azure storage location. This access key is unique to your organization and helps prevent unauthorized access to your PST files after they're uploaded to the Microsoft cloud. Note that importing PST files to Office 365 doesn't require your organization to have a separate Azure subscription.</span></span> 
    
2. <span data-ttu-id="32db2-p108">**アップロードまたはファイルのコピー pst ファイル**の次の手順は、かどうかを使用してネットワーク アップロードまたはドライブの出荷する PST ファイルをインポートすることに依存します。どちらの場合も、ツールと、前の手順で取得したキーをセキュリティで保護された記憶域を使用します。</span><span class="sxs-lookup"><span data-stu-id="32db2-p108">**Upload or copy the PST files** - The next step depends on whether you're using network upload or drive shipping to import PST files. In both cases, you'll use the tool and secure storage key that you obtained in the previous step.</span></span>
    
    - <span data-ttu-id="32db2-p109">**ネットワークのアップロード**(手順 1 でダウンロードした) AzCopy.exe のツールを使用して、アップロードし、マイクロソフトのクラウドでは、Azure ストレージの場所に PST ファイルを保存します。Azure ストレージの場所に PST ファイルをアップロードすることが同じ地域マイクロソフト データ センターでは、Office 365 の組織に存在する注意してください。</span><span class="sxs-lookup"><span data-stu-id="32db2-p109">**Network upload**The AzCopy.exe tool (downloaded in step 1) is used to upload and store your PST files in an Azure storage location in the Microsoft cloud. Note that the Azure storage location that you upload your PST files to resides in the same regional Microsoft datacenter where your Office 365 organization is located.</span></span> 
    
      <span data-ttu-id="32db2-132">それらをアップロードするには、Office 365 にインポートする PST ファイルをファイル共有またはファイル サーバーを組織内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32db2-132">To upload them, the PST files that you want to import to Office 365 have to be located in a file share or file server in your organization.</span></span>
    
    - <span data-ttu-id="32db2-p110">**ドライブの出荷**(手順 1 でダウンロードした) WAImportExport.exe のツールを使用して、PST ファイルをハード ドライブにコピーします。このツールは、ハード ドライブが BitLocker で暗号化し、pst ファイルをハード ドライブにコピーされます。ネットワークのアップロードと同じようにハード ドライブにコピーする PST ファイルをファイル共有またはファイル サーバーを組織内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32db2-p110">**Drive shipping**The WAImportExport.exe tool (downloaded in step 1) is used to copy your PST files to the hard drive. This tool encrypts the hard drive with BitLocker and then copies the PSTs to the hard drive. Like network upload, the PST files that you want to copy to the hard drive have to be located in a file share or file server in your organization.</span></span>
    
3. <span data-ttu-id="32db2-p111">**PST インポート マッピング ファイルを作成する**- PST ファイルが、Azure ストレージの場所にアップロードまたはハード ドライブにコピーされた後、次の手順はユーザー メールボックス、PST ファイルにインポートされますを指定するコンマ区切り値 (CSV) ファイルを作成する (nd PST ファイルをインポートすると、ユーザーのプライマリ メールボックスまたはアーカイブ メールボックス) です。Office 365 のインポート サービスは、PST ファイルをインポートするのには情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="32db2-p111">**Create a PST import mapping file** - After the PST files have been uploaded to the Azure storage location or copied to a hard drive, the next step is to create a comma separated value (CSV) file that specifies which user mailboxes the PST files will be imported to (and a PST file can be imported to a user's primary mailbox or their archive mailbox). The Office 365 Import service will use the information to import the PST files.</span></span> 
    
4. <span data-ttu-id="32db2-p112">セキュリティの [**インポート**] ページで、PST のインポート ジョブを作成するのには、 **pst ファイルを作成するジョブをインポートする**ために次の手順&amp;コンプライアンス センターおよび前の手順で作成した PST のインポート マッピング ファイルを送信します。ネットワーク アップロード用 (Azure には、PST ファイルをアップロードされている) ため、Office 365 が PST ファイル内のデータを分析しでは、どのようなデータは実際にはマッピング ファイルには、PST のインポートで指定したメールボックスにインポートされた取得を制御するフィルターを設定するのには。</span><span class="sxs-lookup"><span data-stu-id="32db2-p112">**Create a PST import job** - The next step is to create a PST import job on the **Import** page in the Security &amp; Compliance Center and submit the PST import mapping file created in the previous step. For network upload (because the PST files have been uploaded to Azure) Office 365 analyzes the data in the PST files and then gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span> 
    
    <span data-ttu-id="32db2-140">ドライブの出荷、追加の項目はプロセスのこの時点で発生します。</span><span class="sxs-lookup"><span data-stu-id="32db2-140">For drive shipping, a few additional things happen at this point in the process.</span></span>
    
    - <span data-ttu-id="32db2-141">(マイクロソフトのデータ ・ センターの送付先住所は、インポート ジョブが作成されたときに表示されます)、Microsoft のデータ センターにハード ドライブを物理的に出荷します。</span><span class="sxs-lookup"><span data-stu-id="32db2-141">You physically ship the hard drive to a Microsoft data center (the shipping address for the Microsoft data center is displayed when the import job is created)</span></span>
    
    - <span data-ttu-id="32db2-p113">マイクロソフトでは、ハード ディスク ドライブを受信するとデータ センターのスタッフは、組織の Azure ストレージの場所にハード ディスク ドライブ上の Pst ファイルをアップロードします。説明したよう、PST ファイルは、Office 365 の組織が配置されている同じ地域の Microsoft データ センター内に存在する Azure ストレージ場所にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="32db2-p113">When Microsoft receives the hard drive, data center personnel will upload the PSTs files on the hard drive to the Azure storage location for your organization. As previously explained, your PST files are uploaded to a Azure storage location that resides in the same regional Microsoft datacenter where your Office 365 organization is located.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="32db2-144">ハード ドライブ上の PST ファイルは、Microsoft は、ハード ディスク ドライブを受信した後、7 ~ 10 営業日以内に、Azure にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="32db2-144">The PST files on the hard drive are uploaded to Azure within 7 to 10 business days after Microsoft receives the hard drive.</span></span> 
  
      <span data-ttu-id="32db2-145">ネットワーク アップロード処理のように Office 365 PST ファイル内のデータを分析し、どのようなデータは実際には、PST のインポート マッピング ファイルで指定されたメールボックスにインポートされた取得を制御するフィルターを設定する機会が与えられます。</span><span class="sxs-lookup"><span data-stu-id="32db2-145">Like the network upload process, Office 365 then analyzes the data in the PST files and gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span>
    
    - <span data-ttu-id="32db2-146">マイクロソフトでは、ハード ドライブに同梱されています。</span><span class="sxs-lookup"><span data-stu-id="32db2-146">Microsoft ships the hard drive back to you.</span></span> 
    
5. <span data-ttu-id="32db2-p114">**フィルターのメールボックスにインポートされる PST のデータ**のインポート ジョブを作成した後 (および、Azure ストレージの場所にドライブ配布のジョブから PST ファイルをアップロードした後) と Office 365 が (安全かつ確実に) でに PST ファイル内のデータを分析アイテムと PST ファイルに含まれている別のメッセージの種類の保存期間を指定します。分析が完了して、データをインポートする準備が、PST ファイルに含まれるすべてのデータをインポートするオプションがあるか、インポートされたデータを取得するかを制御するフィルターを設定することによってインポートされたデータをトリミングすることができます。</span><span class="sxs-lookup"><span data-stu-id="32db2-p114">**Filter the PST data that will be imported to mailboxes** - After the import job is created (and after the PST files from a drive shipping job are uploaded to the Azure storage location) Office 365 analyzes the data in the PST files (safely and securely) by identifying the age of the items and the different message types included in the PST files. When the analysis is completed and the data is ready to import, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span> 
    
6. <span data-ttu-id="32db2-p115">**PST のインポート ジョブを開始する**-インポート ジョブが開始された後、Office 365 情報を使用して、マッピング ファイルには、PST のインポートで彼は Azure ストレージの場所からユーザーのメールボックスを Pst ファイルをインポートするのには。[**インポート**] ページで、セキュリティなどについては各 PST ファイルをインポートするインポート ジョブの状態に関する情報が表示されます&amp;コンプライアンス センターです。インポート ジョブが完了したら、ジョブのステータスが**完了**に設定します。</span><span class="sxs-lookup"><span data-stu-id="32db2-p115">**Start the PST import job** - After the import job is started, Office 365 uses the information in the PST import mapping file to import the PSTs files from the he Azure storage location to user mailboxes. Status information about the import job (including information about each PST file being imported) is displayed on the **Import** page in the Security &amp; Compliance Center. When the import job is finished, the status for the job is set to **Complete**.</span></span>
  
## <a name="why-import-email-data-to-office-365"></a><span data-ttu-id="32db2-152">なぜ電子メール データを Office 365 にインポートしますか。</span><span class="sxs-lookup"><span data-stu-id="32db2-152">Why import email data to Office 365?</span></span>

- <span data-ttu-id="32db2-153">PST ファイルをインポートするユーザーのメールボックスには、組織の電子メールを Office 365 に移行する方法の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="32db2-153">Importing PST files to user mailboxes is one way to migrate your organization's email to Office 365.</span></span>
    
- <span data-ttu-id="32db2-p116">対象のメールボックスに実際にインポートを取得する PST ファイル内のアイテムをフィルター処理するのに[インテリジェントなインポート](filter-data-when-importing-pst-files.md)機能を使用できます。これにより、トリミングすると、フィルターを設定することによってインポートされるデータは、インポートされたデータを取得を制御します。</span><span class="sxs-lookup"><span data-stu-id="32db2-p116">You can use the [Intelligent Import](filter-data-when-importing-pst-files.md) feature to filter the items in PST files that actually get imported to the target mailboxes. This lets you trim the data that's imported by setting filters that control what data gets imported.</span></span> 
    
- <span data-ttu-id="32db2-156">Office 365 のメール ・ データをインポートすることができるため、組織のコンプライアンスのニーズに対応を支援します。</span><span class="sxs-lookup"><span data-stu-id="32db2-156">Importing email data to Office 365 helps address compliance needs of your organization by letting you:</span></span>
    
  - <span data-ttu-id="32db2-157">[アーカイブ メールボックス](enable-archive-mailboxes.md)とユーザーの追加のメールボックスの記憶域を提供する[無制限のアーカイブ](unlimited-archiving.md)を有効にします。</span><span class="sxs-lookup"><span data-stu-id="32db2-157">Enable [archive mailboxes](enable-archive-mailboxes.md) and [unlimited archiving](unlimited-archiving.md) to give users additional mailbox storage space.</span></span> 
    
  - <span data-ttu-id="32db2-158">[証拠保全](https://go.microsoft.com/fwlink/?linkid=841243)を内容を保持するには、メールボックスを配置します。</span><span class="sxs-lookup"><span data-stu-id="32db2-158">Place mailboxes on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=841243) to retain content.</span></span> 
    
  - <span data-ttu-id="32db2-159">メールボックスの内容を検索するには、[コンテンツの検索ツール](content-search.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="32db2-159">Use the [Content Search tool](content-search.md) to search for mailbox content.</span></span> 
    
  - <span data-ttu-id="32db2-160">管理する[電子的証拠開示の場合](ediscovery-cases.md)組織の法的な調査を使用して、</span><span class="sxs-lookup"><span data-stu-id="32db2-160">Use [eDiscovery cases](ediscovery-cases.md) to mange your organization's legal investigations</span></span> 
    
  - <span data-ttu-id="32db2-161">セキュリティで[保存ポリシー](retention-policies.md)を使用して&amp;、メールボックスの内容を保持する期間を制御するためのコンプライアンス センターとし、削除内容の保存期間が終了した後です。</span><span class="sxs-lookup"><span data-stu-id="32db2-161">Use [retention policies](retention-policies.md) in the Security &amp; Compliance Center to control how long mailbox content is retained, and then delete content after the retention period expires.</span></span> 
    
- <span data-ttu-id="32db2-p117">Office 365 へのデータのインポートは、データの損失から保護するのに役立ちます。Office 365 にインポートするメール データは、オンラインの Exchange の高可用性機能を継承します。</span><span class="sxs-lookup"><span data-stu-id="32db2-p117">Importing data to Office 365 helps protect against data loss. Email data that's imported to Office 365 inherits the high availability features of Exchange Online.</span></span>
    
- <span data-ttu-id="32db2-164">電子メール データを Office 365 でユーザーが利用できるすべてのデバイスからクラウドに格納されているためです。</span><span class="sxs-lookup"><span data-stu-id="32db2-164">Email data in Office 365 is available to users from all devices because it's stored in the cloud.</span></span>
    
## <a name="importing-sharepoint-data-to-office-365"></a><span data-ttu-id="32db2-165">SharePoint データを Office 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="32db2-165">Importing SharePoint data to Office 365</span></span>

<span data-ttu-id="32db2-p118">SharePoint サイトおよび OneDrive のアカウントに、Office 365 の組織で、ファイルやドキュメントをインポートすることも。詳細については、以下の資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32db2-p118">You can also import files and documents to SharePoint sites and OneDrive accounts in your Office 365 organization. For more information, see the following articles:</span></span>

- [<span data-ttu-id="32db2-168">SharePoint Online に移行する</span><span class="sxs-lookup"><span data-stu-id="32db2-168">Migrate to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [<span data-ttu-id="32db2-169">SharePoint 移行ツールの概要</span><span class="sxs-lookup"><span data-stu-id="32db2-169">Introducing the SharePoint Migration Tool</span></span>](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [<span data-ttu-id="32db2-170">PowerShell を使用して SharePoint Onine に移行する</span><span class="sxs-lookup"><span data-stu-id="32db2-170">Migrate to SharePoint Online using PowerShell</span></span>](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- <span data-ttu-id="32db2-171">[Azure データ] ボックスを使用して SharePoint Online に、ファイル共有のコンテンツを移行します。](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)</span><span class="sxs-lookup"><span data-stu-id="32db2-171">[Migrate your file share content to SharePoint Online using the Azure Data Box](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)</span></span>


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a><span data-ttu-id="32db2-172">Office 365 に PST ファイルのインポートについてのよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="32db2-172">Frequently asked questions about importing PST files to Office 365</span></span>
  
<span data-ttu-id="32db2-173">サービスを使用して、Office 365 をインポート Office 365 のメールボックスを PST ファイルを一括インポートするにはいくつかのよく寄せられる質問を次に示します。</span><span class="sxs-lookup"><span data-stu-id="32db2-173">Here are some frequently asked questions about using the Office 365 Import service to bulk-import PST files to Office 365 mailboxes.</span></span> 
  
- [<span data-ttu-id="32db2-174">PST ファイルをインポートするのには、ネットワークのアップロードを使用してください。</span><span class="sxs-lookup"><span data-stu-id="32db2-174">Using network upload to import PST files</span></span>](#using-network-upload-to-import-pst-files)
  
- [<span data-ttu-id="32db2-175">ドライブの出荷を使用して、PST ファイルをインポートするのには</span><span class="sxs-lookup"><span data-stu-id="32db2-175">Using drive shipping to import PST files</span></span>](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="32db2-176">PST ファイルをインポートするのには、ネットワークのアップロードを使用してください。</span><span class="sxs-lookup"><span data-stu-id="32db2-176">Using network upload to import PST files</span></span>

 <span data-ttu-id="32db2-177">**Office 365 にインポート サービスのインポート ジョブを作成するために必要なアクセス許可ですか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-177">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="32db2-p119">メールボックスのエクスポートをインポートの役割を割り当てるには、Exchange オンライン Office 365 のメールボックスを PST ファイルをインポートするのにはする必要があります。既定では、この役割はありませんに割り当てられている役割グループは、Exchange オンライン。組織の管理役割グループに、メールボックスのインポート エクスポートの役割を追加できます。または、新しい役割グループを作成、メールボックスのインポート エクスポートの役割を割り当てるし、自分自身または他のユーザーをメンバーとして追加できます。詳細については、追加するロール グループのロール」を参照してください。 または、"グループを作成する役割」セクションの[管理役割グループの Exchange でオンライン](https://go.microsoft.com/fwlink/p/?LinkId=730688)にします。</span><span class="sxs-lookup"><span data-stu-id="32db2-p119">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="32db2-183">Office 365 のセキュリティのジョブのインポートを作成するのにはさらに、&amp;コンプライアンス センターは、次のいずれかを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="32db2-183">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="32db2-p120">メール受信者の役割を割り当てるには、Exchange オンラインする必要があります。既定では、この役割は組織の管理と受信者の管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="32db2-p120">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="32db2-186">または</span><span class="sxs-lookup"><span data-stu-id="32db2-186">Or</span></span>
    
- <span data-ttu-id="32db2-187">Office 365 の組織のグローバル管理者があります。</span><span class="sxs-lookup"><span data-stu-id="32db2-187">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="32db2-p121">Exchange Online の具体的には、Office 365 に PST ファイルをインポートする新しい役割グループを作成することを検討してください。PST ファイルをインポートするのには必要な特権を最低限のレベルで、新しい役割グループにメールボックスのエクスポートをインポートし、メール受信者の役割を割り当てるし、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="32db2-p121">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="32db2-190">**アップロードのネットワークが利用可能な場所**</span><span class="sxs-lookup"><span data-stu-id="32db2-190">**Where is network upload available?**</span></span>
  
<span data-ttu-id="32db2-p122">ネットワークのアップロードは、アメリカ合衆国、カナダ、ブラジル、英国、ヨーロッパ、インド、東アジア、東南アジア、日本、韓国、およびオーストラリアで現在利用できません。ネットワークのアップロードは近日より多くの地域で。</span><span class="sxs-lookup"><span data-stu-id="32db2-p122">Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="32db2-193">**ネットワークのアップロードを使用して、PST ファイルをインポートするための価格設定とは何ですか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-193">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="32db2-194">ネットワークのアップロードを使用して、PST ファイルをインポートするのには、無料です。</span><span class="sxs-lookup"><span data-stu-id="32db2-194">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="32db2-p123">つまり、PST ファイルが、Azure のストレージ領域から削除されると、不要になった表示 Office 365 の管理ページで、インポートが完了したジョブのファイルの一覧にします。インポート ジョブが一覧に表示される**Office 365 へのデータのインポート**] ページは、古いインポート ジョブの詳細を表示すると、PST ファイルの一覧が空あります。</span><span class="sxs-lookup"><span data-stu-id="32db2-p123">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Office 365 admin center. Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="32db2-197">**PST ファイルの形式のバージョンは、Office 365 にインポートするためにサポートされてでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-197">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="32db2-p124">PST ファイルの形式の 2 つのバージョン: ANSI と Unicode です。Unicode PST ファイルの形式を使用するファイルをインポートすることをお勧めします。ただし、ANSI PST ファイル形式の 2 バイト文字を使用する言語などを使用しているファイルはセット (DBCS)、Office 365 にインポートすることもできます。ANSI PST ファイルをインポートする方法の詳細については、 [Office 365 に PST ファイルをインポートするのにはアップロードの使用のネットワーク](https://go.microsoft.com/fwlink/p/?LinkId=823074)上の手順 4 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32db2-p124">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 4 in [Use network upload to import PST files to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074).</span></span>
  
<span data-ttu-id="32db2-202">さらに、Outlook 2007 およびそれ以降のバージョンの PST ファイルは、Office 365 にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="32db2-202">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="32db2-203">**Azure のストレージ領域に、PST ファイルをアップロードすると後、どのくらいの時間、Azure でまでに保存されては削除ですか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-203">**After I upload my PST files to the Azure storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="32db2-p125">PST ファイルをインポートするのには、ネットワークのアップロード方法を使用するときに**ingestiondata**という名前の Azure blob コンテナーにアップロードします。ジョブはありませんインポート進行中の [**インポート**] ページで、セキュリティの場合&amp;コンプライアンス センター) で、Azure の**ingestiondata**コンテナー内のすべての PST ファイルがセキュリティの&amp;コンプライアンス センターです。つまり、セキュリティに新しいインポート ジョブを作成する必要が&amp;Azure にファイルを PST のアップロードから 30 日以内コンプライアンス センター (ネットワークのアップロード手順の手順 5 で説明します)。</span><span class="sxs-lookup"><span data-stu-id="32db2-p125">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**. If there are no import jobs in progress on the **Import** page in the Security &amp; Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security &amp; Compliance Center. That also means you have to create a new import job in the Security &amp; Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="32db2-p126">つまり、PST ファイルが、Azure のストレージ領域から削除されると、不要になった表示、セキュリティのインポートが完了したジョブのファイルの一覧で、&amp;コンプライアンス センターです。インポート ジョブが一覧に表示されるセキュリティの [**インポート**] ページに&amp;コンプライアンス センターでは、PST ファイルの一覧があります空古いインポート ジョブの詳細を表示するとします。</span><span class="sxs-lookup"><span data-stu-id="32db2-p126">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="32db2-209">**メールボックスを PST ファイルをインポートするのにはどのくらい時間がかかりますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-209">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="32db2-p127">ネットワークの容量によって異なりますが、組織の Azure ストレージ領域にアップロードするデータのテラバイト (TB) のそれぞれのいくつかの時間がかかります。PST ファイルが、Azure のストレージ領域にコピーされると、PST ファイルは、1 日あたり 24 GB 以上の速度で Office 365 のメールボックスにインポートされます。このレートは、お客様のニーズを満たしていない場合、は、Office 365 に移行するメール ・ データの他の方法を検討する可能性があります。詳細については、 [Office 365 に複数の電子メール アカウントを移行する方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32db2-p127">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. After the PST files are copied to the Azure storage area, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="32db2-p128">別の PST ファイルは、別のターゲット メールボックスにインポートする、インポート処理の場合は並列です。つまり、PST またはメールボックスの各ペアが同時にインポートされます。同様に、同じメールボックスに複数の PST ファイルを読み込む場合、同時にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="32db2-p128">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="32db2-216">**メッセージ サイズの制限の PST ファイルをインポートするときでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-216">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="32db2-p129">うん。PST ファイルには 150 MB を超えるメールボックスのアイテムが含まれている場合は、インポート処理中に項目がスキップされます。</span><span class="sxs-lookup"><span data-stu-id="32db2-p129">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="32db2-219">**など、メッセージを送信または受信されると、一連の受信者、およびその他のプロパティは、Office 365 のメールボックスに PST ファイルのインポート時に維持すると、メッセージのプロパティは**</span><span class="sxs-lookup"><span data-stu-id="32db2-219">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="32db2-p130">うん。元のメッセージのメタデータは、インポート処理中に変更されません。</span><span class="sxs-lookup"><span data-stu-id="32db2-p130">Yes. The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="32db2-222">**メールボックスにインポートする PST ファイルのフォルダー階層内のレベルの数に制限はありますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-222">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="32db2-p131">うん。入れ子になったフォルダーの 300 以上のレベルを持つ PST ファイルをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="32db2-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="32db2-225">**ネットワークのアップロードを使用して、Office 365 で、アクティブでないメールボックスを PST ファイルをインポートするのにはできますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-225">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="32db2-226">はい、この機能は、使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="32db2-226">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="32db2-227">**Exchange ハイブリッド展開でのオンライン ・ アーカイブ メールボックスに PST ファイルをインポートするのにはネットワークのアップロードを使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-227">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="32db2-228">はい、この機能は、使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="32db2-228">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="32db2-229">**オンライン Exchange 内のパブリック フォルダーを PST ファイルをインポートするのにはネットワークのアップロードを使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-229">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="32db2-230">残念ですが、パブリック フォルダーを PST ファイルをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="32db2-230">No, you can't import PST files to public folders.</span></span>
  
### <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="32db2-231">ドライブの出荷を使用して、PST ファイルをインポートするのには</span><span class="sxs-lookup"><span data-stu-id="32db2-231">Using drive shipping to import PST files</span></span>

 <span data-ttu-id="32db2-232">**Office 365 にインポート サービスのインポート ジョブを作成するために必要なアクセス許可ですか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-232">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="32db2-p132">Office 365 のメールボックスを PST ファイルをインポートするのには、メールボックスのエクスポートをインポートの役割を割り当てる必要があります。既定では、この役割はありませんに割り当てられている役割グループは、Exchange オンライン。組織の管理役割グループに、メールボックスのインポート エクスポートの役割を追加できます。または、新しい役割グループを作成、メールボックスのインポート エクスポートの役割を割り当てるし、自分自身または他のユーザーをメンバーとして追加できます。詳細については、追加するロール グループのロール」を参照してください。 または、"グループを作成する役割」セクションの[管理役割グループの Exchange でオンライン](https://go.microsoft.com/fwlink/p/?LinkId=730688)にします。</span><span class="sxs-lookup"><span data-stu-id="32db2-p132">You have to be assigned the Mailbox Import Export role to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="32db2-238">Office 365 のセキュリティのジョブのインポートを作成するのにはさらに、&amp;コンプライアンス センターは、次のいずれかを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="32db2-238">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="32db2-p133">メール受信者の役割を割り当てるには、Exchange オンラインする必要があります。既定では、この役割は組織の管理と受信者の管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="32db2-p133">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="32db2-241">または</span><span class="sxs-lookup"><span data-stu-id="32db2-241">Or</span></span>
    
- <span data-ttu-id="32db2-242">Office 365 の組織のグローバル管理者があります。</span><span class="sxs-lookup"><span data-stu-id="32db2-242">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="32db2-p134">Exchange Online の具体的には、Office 365 に PST ファイルをインポートする新しい役割グループを作成することを検討してください。PST ファイルをインポートするのには必要な特権を最低限のレベルで、新しい役割グループにメールボックスのエクスポートをインポートし、メール受信者の役割を割り当てるし、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="32db2-p134">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="32db2-245">**場所はドライブ配布可能ですか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-245">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="32db2-p135">ドライブの出荷は、米国、カナダ、ブラジル、英国、ヨーロッパ、インド、東アジア、東南アジア、日本、韓国、およびオーストラリアで現在利用可能です。ドライブの出荷は近日より多くの地域で。</span><span class="sxs-lookup"><span data-stu-id="32db2-p135">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Drive shipping will be available in more regions soon.</span></span>
  
 <span data-ttu-id="32db2-248">**どのような商用のライセンス契約では、ドライブの出荷をサポートしますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-248">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="32db2-p136">配布の PST ファイルを Office 365 にインポートするのにはドライブは、Microsoft マイクロソフトエンタープライズ契約 (EA) を使用することができます。ドライブの出荷は、マイクロソフトの製品およびサービス契約 (MPSA) を使用できません。</span><span class="sxs-lookup"><span data-stu-id="32db2-p136">Drive shipping to import PST files to Office 365 is available through a Microsoft Enterprise Agreement (EA). Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="32db2-251">**配布の PST ファイルを Office 365 にインポートするのにはドライブを使用するための価格設定とは何ですか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-251">**What is the pricing for using drive shipping to import PST files to Office 365?**</span></span>
  
<span data-ttu-id="32db2-p137">ドライブの出荷を使用して、Office 365 のメールボックスを PST ファイルをインポートするためのコストは、$2 米ドル 1 GB のデータです。1,000 GB (1 TB) を PST ファイルを格納しているハード ドライブを出荷する場合、コストは $2,000 USD です。インポートの手数料をお支払いするパートナーを使用することができます。パートナーを検索する方法の詳細については[、Office 365 のパートナーまたは販売店を検索](https://go.microsoft.com/fwlink/p/?LinkId=785197)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32db2-p137">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="32db2-256">**ドライブの出荷は、どのような種類のハード ドライブがサポートされているでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-256">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="32db2-p138">2.5 インチのみソリッド ・ ステート ・ ドライブを (Ssd) または 2.5 または 3.5 インチ SATA II と III の内部ハード ドライブが Office 365 のインポート サービスで使用するためにサポートされています。ハード ドライブを使用することができます最大 10 TB です。インポート ジョブの場合は、ハード ドライブの最初のデータ量のみが処理されます。データ ボリュームは、NTFS でフォーマットする必要があります。ハード ドライブにデータをコピーするときに 2.5 インチ SSD を使用して直接接続することができます 2.5 または 3.5 インチの SATA II と III のコネクタ、または外部の 2.5 インチ SSD を使用して外部にまたは 2.5 または 3.5 インチの SATA II と III の USB アダプターを接続することができます。</span><span class="sxs-lookup"><span data-stu-id="32db2-p138">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service. You can use hard drives up to 10 TB. For import jobs, only the first data volume on the hard drive will be processed. The data volume must be formatted with NTFS. When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="32db2-p139">組み込みの USB アダプターに付属している外付けのハード ドライブは、Office 365 のインポート サービスでサポートされていません。さらに、大文字と小文字の外付けハード ドライブ内のディスクは使用できません。外付けハード ドライブを出荷しないしてください。</span><span class="sxs-lookup"><span data-stu-id="32db2-p139">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="32db2-265">**1 回のインポート ジョブには、ハード ドライブの数を出荷してでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-265">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="32db2-266">1 回のインポート ジョブの 10 個のハード ドライブの最大を出荷することができます。</span><span class="sxs-lookup"><span data-stu-id="32db2-266">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="32db2-267">**ハード ドライブを出荷した後は時間をマイクロソフトのデータ ・ センターを取得するでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-267">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="32db2-p140">いくつか、マイクロソフトのデータ ・ センターの近くなどに依存して、配送オプションの種類を使用してハード ドライブなど、翌日配送、2 日間の配信、地上配信を出荷します。ほとんどの運送会社では、配信のステータスを追跡するために追跡番号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="32db2-p140">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="32db2-270">**ハード ドライブは、マイクロソフトのデータ ・ センターに到着すた後、所要時間はどれに Azure に PST ファイルをアップロードするか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-270">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="32db2-p141">マイクロソフトのデータ ・ センターで、ハード ディスク ドライブが受信されると、組織の Microsoft Azure のストレージ領域を PST ファイルをアップロードするのには、7 ~ 10 営業日間かかります。PST ファイルのアップロードという名前の Azure blob コンテナーに`ingestiondata`。</span><span class="sxs-lookup"><span data-stu-id="32db2-p141">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Microsoft Azure storage area for your organization. The PST files will be uploaded to a Azure blob container named `ingestiondata`.</span></span> 
  
 <span data-ttu-id="32db2-273">**メールボックスを PST ファイルをインポートするのにはどのくらい時間がかかりますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-273">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="32db2-p142">PST ファイルは、Azure のストレージ領域にアップロードした後 Office 365 は、アイテムと PST ファイルに含まれている別のメッセージの種類の保存期間を識別する (安全性とセキュリティで保護された形で) PST ファイル内のデータを分析します。この分析が完了すると、PST ファイル内のすべてのデータをインポートするオプションがあります。 または、インポートされたデータを取得するフィルターの設定を制御します。インポート ジョブを起動した後、PST ファイルは、1 日あたり 24 GB 以上の速度で Office 365 のメールボックスにインポートされます。このレートは、お客様のニーズを満たしていない場合、は、Office 365 のメール ・ データをインポートするその他の方法を検討する可能性があります。詳細については、 [Office 365 に複数の電子メール アカウントを移行する方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32db2-p142">After the PST files are uploaded to the Azure storage area, Office 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files. When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported. After you start the import job, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="32db2-p143">別の PST ファイルは、別のターゲット メールボックスにインポートする、インポート処理の場合は並列です。つまり、PST またはメールボックスの各ペアが同時にインポートされます。同様に、同じメールボックスに複数の PST ファイルを読み込む場合、同時にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="32db2-p143">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="32db2-281">**マイクロソフトでは、Azure に PST ファイルをアップロード後、どのくらいの時間、Azure でまでに保存されては削除しますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-281">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="32db2-282">Azure ストレージの場所に組織のすべての PST ファイル (という名前の blob コンテナーに`ingestiondata`)、[**インポート**] ページで、セキュリティ、最新のインポート ジョブを作成した後、30 日以内に削除されます&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="32db2-282">All PST files in the Azure storage location for your organization (in blob container named `ingestiondata`), are deleted 30 days after the most recent import job was created on the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="32db2-p144">つまり、PST ファイルが、Azure のストレージ領域から削除されると、不要になった表示、セキュリティのインポートが完了したジョブのファイルの一覧で、&amp;コンプライアンス センターです。インポート ジョブが一覧に表示されるセキュリティの [**インポート**] ページに&amp;コンプライアンス センターでは、PST ファイルの一覧があります空古いインポート ジョブの詳細を表示するとします。</span><span class="sxs-lookup"><span data-stu-id="32db2-p144">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="32db2-285">**PST ファイルの形式のバージョンは、Office 365 にインポートするためにサポートされてでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-285">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="32db2-p145">PST ファイルの形式の 2 つのバージョン: ANSI と Unicode です。Unicode PST ファイルの形式を使用するファイルをインポートすることをお勧めします。ただし、ANSI PST ファイル形式の 2 バイト文字を使用する言語などを使用しているファイルはセット (DBCS)、Office 365 にインポートすることもできます。ANSI PST ファイルをインポートする方法の詳細については、 [Office 365 組織 PST ファイルをインポートするのには配布のドライブを使用して](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)手順 3 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32db2-p145">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import your organization PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="32db2-290">さらに、Outlook 2007 およびそれ以降のバージョンの PST ファイルは、Office 365 にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="32db2-290">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="32db2-291">**メッセージ サイズの制限の PST ファイルをインポートするときでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-291">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="32db2-p146">うん。PST ファイルには 150 MB を超えるメールボックスのアイテムが含まれている場合は、インポート処理中に項目がスキップされます。</span><span class="sxs-lookup"><span data-stu-id="32db2-p146">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="32db2-294">**など、メッセージを送信または受信されると、一連の受信者、およびその他のプロパティは、Office 365 のメールボックスに PST ファイルのインポート時に維持すると、メッセージのプロパティは**</span><span class="sxs-lookup"><span data-stu-id="32db2-294">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="32db2-p147">うん。インポート処理中に元のメッセージのメタデータは変更されません。</span><span class="sxs-lookup"><span data-stu-id="32db2-p147">Yes. The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="32db2-297">**メールボックスにインポートする PST ファイルのフォルダー階層内のレベルの数に制限はありますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-297">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="32db2-p148">うん。入れ子になったフォルダーの 300 以上のレベルを持つ PST ファイルをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="32db2-p148">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="32db2-300">**ドライブの出荷を使用して、Office 365 で、アクティブでないメールボックスを PST ファイルをインポートするのにはできますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-300">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="32db2-301">はい、この機能は、使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="32db2-301">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="32db2-302">**Exchange ハイブリッド展開でのオンライン ・ アーカイブ メールボックスに PST ファイルをインポートするのにはドライブの配布を使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-302">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="32db2-303">はい、この機能は、使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="32db2-303">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="32db2-304">**オンライン Exchange 内のパブリック フォルダーを PST ファイルをインポートするのにはドライブの配布を使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-304">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="32db2-305">残念ですが、パブリック フォルダーを PST ファイルをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="32db2-305">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="32db2-306">**いただくようお願いを出荷する前に、ハード ドライブのワイプを Microsoft できますでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-306">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="32db2-p149">残念ですが、マイクロソフトはそれらを顧客に出荷する前にハード ドライブを消去することはできません。ハード ドライブはマイクロソフトが受信したときと同じ状態にするに返されます。</span><span class="sxs-lookup"><span data-stu-id="32db2-p149">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="32db2-309">**私に出荷するのではなくハード ドライブを Microsoft シュレッダ処理できますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-309">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="32db2-p150">残念ですが、マイクロソフトでは、ハード ディスクを破棄できません。ハード ドライブはマイクロソフトが受信したときと同じ状態にするに返されます。</span><span class="sxs-lookup"><span data-stu-id="32db2-p150">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="32db2-312">**返品の送付先にどのような宅配サービスがサポートされますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-312">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="32db2-p151">米国またはヨーロッパの顧客の場合、マイクロソフトは、ハード ドライブを取得するのには宅配便を使用します。他のすべての地域では、マイクロソフトは、DHL を使用します。</span><span class="sxs-lookup"><span data-stu-id="32db2-p151">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="32db2-315">**戻り値の送料は?**</span><span class="sxs-lookup"><span data-stu-id="32db2-315">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="32db2-p152">ハード ディスクが同梱されているマイクロソフトのデータ ・ センターへの近接によって、送料が異なりますが返されます。ハード ドライブを取得するのには、FedEx、DHL のアカウントに請求させていただきます。返品送料のコストは、ユーザーの責任です。</span><span class="sxs-lookup"><span data-stu-id="32db2-p152">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="32db2-319">**マイクロソフトにハード ドライブを出荷するのに FedEx カスタム送付先住所などのカスタムの宅配便配送サービスを使用できますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-319">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="32db2-320">はい。</span><span class="sxs-lookup"><span data-stu-id="32db2-320">Yes.</span></span>
  
 <span data-ttu-id="32db2-321">**他の国の私のハード ドライブを出荷する必要がある、する場合はありますを行う必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="32db2-321">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="32db2-p153">マイクロソフトに出荷するハード ディスク ドライブは、国境を通過する必要があります。大文字と小文字の場合は、自分が責任をハード ディスク ドライブとそれに含まれるデータはインポートまたはエクスポートされた適用法に準拠を保証するためです。ハード ドライブを出荷する前にこと、ドライブとデータが合法的に出荷する指定した Microsoft のデータ センターを確認するのには、アドバイザーに確認してください。これは適切なタイミングでマイクロソフトに到達することを確認するのには役立ちます。</span><span class="sxs-lookup"><span data-stu-id="32db2-p153">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
