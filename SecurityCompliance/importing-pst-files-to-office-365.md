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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: '管理者向け: Office 365 セキュリティ&amp;コンプライアンスセンターのインポートサービスを使用して、電子メールデータ (PST ファイル) を Exchange Online のユーザーメールボックスに一括インポートする方法について説明します。このトピックでは、faq を示し、PST インポート処理のしくみについて説明します。'
ms.openlocfilehash: 89aa1a351d0a9bcc70819f4b2657d04adc7599e2
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296780"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a><span data-ttu-id="73900-104">Overview of importing your organization PST files to Office 365</span><span class="sxs-lookup"><span data-stu-id="73900-104">Overview of importing your organization PST files to Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="73900-p102">この記事は、管理者を対象としています。PST ファイルを自分のメールボックスにインポートしようとしていますか?「 [Outlook .pst ファイルからメール、連絡先、予定表をインポートする](https://go.microsoft.com/fwlink/p/?LinkID=785075)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73900-p102">This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)</span></span>

<span data-ttu-id="73900-p103">office 365 セキュリティ&amp;コンプライアンスセンターのインポートサービスを使用して、office 365 組織の Exchange Online メールボックスに PST ファイルを簡単に一括インポートすることができます。PST ファイルを Office 365 にインポートするには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="73900-p103">You can use the Import service in the Office 365 Security &amp; Compliance Center to quickly bulk-import PST files to Exchange Online mailboxes in your Office 365 organization. There are two ways you can import PST files to Office 365:</span></span>
   
- <span data-ttu-id="73900-p104">**ネットワークアップロード**![クラウドの](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png)アップロード-PST ファイルをネットワーク経由で Microsoft クラウド内の一時的な Azure ストレージの場所にアップロードします。次に、office 365 インポートサービスを使用して、office 365 組織のメールボックスに PST データをインポートします。</span><span class="sxs-lookup"><span data-stu-id="73900-p104">**Network upload** ![Cloud upload](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - Upload the PST files over the network to a temporary Azure storage location in the Microsoft cloud. Then you use the Office 365 Import service to import the PST data to mailboxes in your Office 365 organization.</span></span> 

- <span data-ttu-id="73900-p105">**ドライブの送付**![ハードディスク](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) -PST ファイルを BitLocker で暗号化されたハードドライブにコピーし、ドライブを Microsoft に物理的に送付します。microsoft がハードドライブを受け取ると、データセンターの担当者は、microsoft クラウド内の一時的な Azure ストレージの場所にデータをアップロードします。次に、office 365 インポートサービスを使用して、office 365 組織のメールボックスにデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="73900-p105">**Drive shipping** ![Hard disk](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - Copy the PST files to a BitLocker-encrypted hard drive and then physically ship the drive to Microsoft. When Microsoft receives the hard drive, data center personnel upload the data to a temporary Azure storage location in the Microsoft cloud. Then you use the Office 365 Import service to import the data to mailboxes in your Office 365 organization.</span></span>

## <a name="step-by-step-instructions"></a><span data-ttu-id="73900-115">ステップごとの手順</span><span class="sxs-lookup"><span data-stu-id="73900-115">Step-by-step instructions</span></span>
  
<span data-ttu-id="73900-116">組織の PST ファイルを Office 365 に一括インポートする詳細な手順については、以下のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73900-116">See one of the following topics for detailed, step-by-step instructions for bulk-importing your organization's PST files to Office 365.</span></span> 
   
- [<span data-ttu-id="73900-117">ネットワーク アップロードを使用して PST ファイルを Office 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="73900-117">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
- [<span data-ttu-id="73900-118">ドライブ送付を使用して PST ファイルを Office 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="73900-118">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a><span data-ttu-id="73900-119">PST ファイルのインポートのしくみ</span><span class="sxs-lookup"><span data-stu-id="73900-119">How importing PST files works</span></span>

<span data-ttu-id="73900-p106">以下に、完全な PST インポートプロセスの図と説明を示します。この図はプライマリワークフローを示しており、ネットワークアップロード方法とドライブ送付方法の相違点を強調しています。</span><span class="sxs-lookup"><span data-stu-id="73900-p106">Here's an illustration and description of the complete PST import process. The illustration shows the primary workflow and highlights the differences between the network upload and drive shipping methods.</span></span>
  
![PST インポートプロセスのワークフロー](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. <span data-ttu-id="73900-p107">**pst インポートツールとキーをプライベート Azure ストレージの場所にダウンロード**する-最初の手順として、pst ファイルのアップロードまたはハードドライブへのコピーに使用するツールとアクセスキーをダウンロードします。これらは、Office 365 \*\*\*\* セキュリティ&amp;コンプライアンスセンターの [インポート] ページから取得します。このキーを使用すると、機密およびセキュリティで保護された Azure ストレージの場所に PST ファイルをアップロードするために必要なアクセス許可が付与されたユーザー (または、ドライブを配送する場合は Microsoft データセンターのスタッフ) が提供されます。このアクセスキーは組織に固有のものであり、Microsoft クラウドにアップロードされた後に PST ファイルへの権限のないアクセスを防止するのに役立てることができます。Office 365 に PST ファイルをインポートする場合は、組織で別の Azure サブスクリプションを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="73900-p107">**Download the PST import tools and key to private Azure storage location** - The first step is to download the tool and access key used to upload the PST files or copy them to a hard drive. You obtain these from the **Import** page in the Office 365 Security &amp; Compliance Center. The key provides you (or Microsoft data center personnel in the case of drive shipping) with the necessary permissions to upload PST files to a private and secure Azure storage location. This access key is unique to your organization and helps prevent unauthorized access to your PST files after they're uploaded to the Microsoft cloud. Note that importing PST files to Office 365 doesn't require your organization to have a separate Azure subscription.</span></span> 
    
2. <span data-ttu-id="73900-p108">**pst ファイルのアップロードまたはコピー** -次の手順は、pst ファイルをインポートするためにネットワークアップロードまたはドライブ配送を使用しているかどうかによって異なります。どちらの場合も、前の手順で取得したツールとセキュリティ保護されたストレージキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="73900-p108">**Upload or copy the PST files** - The next step depends on whether you're using network upload or drive shipping to import PST files. In both cases, you'll use the tool and secure storage key that you obtained in the previous step.</span></span>
    
    - <span data-ttu-id="73900-p109">**ネットワークアップロード**(手順1でダウンロードした) azcopy ツールを使用して、PST ファイルをアップロードし、Microsoft クラウド内の Azure ストレージの場所に保存します。PST ファイルをアップロードする Azure ストレージの場所は、Office 365 組織が配置されているのと同じ地域の Microsoft データセンターに存在することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="73900-p109">**Network upload**The AzCopy.exe tool (downloaded in step 1) is used to upload and store your PST files in an Azure storage location in the Microsoft cloud. Note that the Azure storage location that you upload your PST files to resides in the same regional Microsoft datacenter where your Office 365 organization is located.</span></span> 
    
      <span data-ttu-id="73900-132">これらをアップロードするには、Office 365 にインポートする PST ファイルが、組織内のファイル共有またはファイルサーバーに配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="73900-132">To upload them, the PST files that you want to import to Office 365 have to be located in a file share or file server in your organization.</span></span>
    
    - <span data-ttu-id="73900-p110">**ドライブの送付**ユーザーの PST ファイルをハードドライブにコピーするには、手順1でダウンロードした waimportexport .exe ツールを使用します。このツールは、BitLocker を使用してハードドライブを暗号化し、次に pst をハードドライブにコピーします。ネットワークアップロードと同様に、ハードドライブにコピーする PST ファイルは、組織内のファイル共有またはファイルサーバーに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73900-p110">**Drive shipping**The WAImportExport.exe tool (downloaded in step 1) is used to copy your PST files to the hard drive. This tool encrypts the hard drive with BitLocker and then copies the PSTs to the hard drive. Like network upload, the PST files that you want to copy to the hard drive have to be located in a file share or file server in your organization.</span></span>
    
3. <span data-ttu-id="73900-p111">**pst インポートのマッピングファイルを作成**する-pst ファイルが Azure の保存場所にアップロードされた後、またはハードドライブにコピーされた後、次の手順では、pst ファイルをインポートするユーザーメールボックスを指定するコンマ区切り値 (CSV) ファイルを作成します。nd PST ファイルは、ユーザーのプライマリメールボックスまたは自分のアーカイブメールボックスにインポートできます。Office 365 インポートサービスは、この情報を使用して PST ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="73900-p111">**Create a PST import mapping file** - After the PST files have been uploaded to the Azure storage location or copied to a hard drive, the next step is to create a comma separated value (CSV) file that specifies which user mailboxes the PST files will be imported to (and a PST file can be imported to a user's primary mailbox or their archive mailbox). The Office 365 Import service will use the information to import the PST files.</span></span> 
    
4. <span data-ttu-id="73900-p112">**pst インポートジョブを作成**する-次の手順では、セキュリティ&amp;コンプライアンスセンターの [**インポート**] ページで pst インポートジョブを作成し、前の手順で作成した pst インポートマッピングファイルを送信します。ネットワークアップロードの場合 (pst ファイルが Azure にアップロードされているため)、Office 365 は pst ファイルのデータを分析し、pst インポートマッピングファイルで指定されているメールボックスに実際にインポートするデータを制御するフィルターを設定する機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="73900-p112">**Create a PST import job** - The next step is to create a PST import job on the **Import** page in the Security &amp; Compliance Center and submit the PST import mapping file created in the previous step. For network upload (because the PST files have been uploaded to Azure) Office 365 analyzes the data in the PST files and then gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span> 
    
    <span data-ttu-id="73900-140">ドライブの配送に関しては、プロセスのこの時点でいくつかの追加が行われます。</span><span class="sxs-lookup"><span data-stu-id="73900-140">For drive shipping, a few additional things happen at this point in the process.</span></span>
    
    - <span data-ttu-id="73900-141">ハードドライブを microsoft データセンターに物理的に輸送します (インポートジョブの作成時に microsoft データセンターの送付先住所が表示されます)。</span><span class="sxs-lookup"><span data-stu-id="73900-141">You physically ship the hard drive to a Microsoft data center (the shipping address for the Microsoft data center is displayed when the import job is created)</span></span>
    
    - <span data-ttu-id="73900-p113">Microsoft がハードドライブを受け取ると、データセンター担当者は、組織のためにハードドライブ上の pst ファイルを Azure ストレージの場所にアップロードします。前述したように、PST ファイルは、Office 365 組織が配置されているのと同じ地域の Microsoft データセンターに存在する Azure ストレージの場所にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="73900-p113">When Microsoft receives the hard drive, data center personnel will upload the PSTs files on the hard drive to the Azure storage location for your organization. As previously explained, your PST files are uploaded to a Azure storage location that resides in the same regional Microsoft datacenter where your Office 365 organization is located.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="73900-144">ハードドライブ上の PST ファイルは、Microsoft がハードドライブを受け取った後、7 ~ 10 営業日以内に Azure にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="73900-144">The PST files on the hard drive are uploaded to Azure within 7 to 10 business days after Microsoft receives the hard drive.</span></span> 
  
      <span data-ttu-id="73900-145">ネットワークアップロードプロセスと同様に、Office 365 は pst ファイルのデータを分析し、pst インポートマッピングファイルで指定されたメールボックスに実際にインポートするデータを制御するフィルターを設定する機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="73900-145">Like the network upload process, Office 365 then analyzes the data in the PST files and gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span>
    
    - <span data-ttu-id="73900-146">Microsoft は、hdd をお送りします。</span><span class="sxs-lookup"><span data-stu-id="73900-146">Microsoft ships the hard drive back to you.</span></span> 
    
5. <span data-ttu-id="73900-p114">**メールボックスにインポートする pst データのフィルター処理**-インポートジョブが作成された後 (およびドライブ出荷ジョブからの pst ファイルが Azure ストレージの場所にアップロードされた後)、Office 365 は pst ファイルのデータ (安全かつ安全) を分析します。アイテムの保存期間、および PST ファイルに含まれるさまざまなメッセージの種類を識別する。分析が完了し、データをインポートする準備ができたら、PST ファイルに含まれるすべてのデータをインポートするか、インポートするデータを制御するフィルターを設定してインポートしたデータをトリミングすることができます。</span><span class="sxs-lookup"><span data-stu-id="73900-p114">**Filter the PST data that will be imported to mailboxes** - After the import job is created (and after the PST files from a drive shipping job are uploaded to the Azure storage location) Office 365 analyzes the data in the PST files (safely and securely) by identifying the age of the items and the different message types included in the PST files. When the analysis is completed and the data is ready to import, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span> 
    
6. <span data-ttu-id="73900-p115">**pst インポートジョブを開始**する-インポートジョブが開始されると、Office 365 は pst インポートマッピングファイル内の情報を使用して、pst ファイルをユーザーのメールボックスにインポートします。インポートジョブに関する状態情報 (インポートされている各 PST ファイルに関する情報を含む\*\*\*\* ) は、セキュリティ&amp;コンプライアンスセンターの [インポート] ページに表示されます。インポートジョブが完了すると、ジョブの状態が [**完了**] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="73900-p115">**Start the PST import job** - After the import job is started, Office 365 uses the information in the PST import mapping file to import the PSTs files from the he Azure storage location to user mailboxes. Status information about the import job (including information about each PST file being imported) is displayed on the **Import** page in the Security &amp; Compliance Center. When the import job is finished, the status for the job is set to **Complete**.</span></span>
  
## <a name="why-import-email-data-to-office-365"></a><span data-ttu-id="73900-152">メールデータを Office 365 にインポートする理由</span><span class="sxs-lookup"><span data-stu-id="73900-152">Why import email data to Office 365?</span></span>

- <span data-ttu-id="73900-153">PST ファイルのユーザーメールボックスへのインポートは、組織の電子メールを Office 365 に移行する1つの方法です。</span><span class="sxs-lookup"><span data-stu-id="73900-153">Importing PST files to user mailboxes is one way to migrate your organization's email to Office 365.</span></span>
    
- <span data-ttu-id="73900-p116">[インテリジェントインポート](filter-data-when-importing-pst-files.md)機能を使用すると、移動先のメールボックスに実際にインポートされる PST ファイル内のアイテムをフィルター処理できます。これにより、インポートするデータを制御するフィルターを設定することによって、インポートされたデータをトリミングできます。</span><span class="sxs-lookup"><span data-stu-id="73900-p116">You can use the [Intelligent Import](filter-data-when-importing-pst-files.md) feature to filter the items in PST files that actually get imported to the target mailboxes. This lets you trim the data that's imported by setting filters that control what data gets imported.</span></span> 
    
- <span data-ttu-id="73900-156">メールデータを Office 365 にインポートすると、組織のコンプライアンスニーズに対応できます。</span><span class="sxs-lookup"><span data-stu-id="73900-156">Importing email data to Office 365 helps address compliance needs of your organization by letting you:</span></span>
    
  - <span data-ttu-id="73900-157">[アーカイブメールボックス](enable-archive-mailboxes.md)と[無制限のアーカイブ](unlimited-archiving.md)を有効にして、ユーザーに追加のメールボックス記憶領域を付与します。</span><span class="sxs-lookup"><span data-stu-id="73900-157">Enable [archive mailboxes](enable-archive-mailboxes.md) and [unlimited archiving](unlimited-archiving.md) to give users additional mailbox storage space.</span></span> 
    
  - <span data-ttu-id="73900-158">メールボックスを[訴訟ホールド](https://go.microsoft.com/fwlink/?linkid=841243)の対象にして、コンテンツを保持します。</span><span class="sxs-lookup"><span data-stu-id="73900-158">Place mailboxes on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=841243) to retain content.</span></span> 
    
  - <span data-ttu-id="73900-159">[コンテンツ検索ツール](content-search.md)を使用して、メールボックスのコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="73900-159">Use the [Content Search tool](content-search.md) to search for mailbox content.</span></span> 
    
  - <span data-ttu-id="73900-160">[電子情報開示ケース](ediscovery-cases.md)を使用して組織の法的調査を行う</span><span class="sxs-lookup"><span data-stu-id="73900-160">Use [eDiscovery cases](ediscovery-cases.md) to mange your organization's legal investigations</span></span> 
    
  - <span data-ttu-id="73900-161">セキュリティ&amp; /コンプライアンスセンターの[アイテム保持ポリシー](retention-policies.md)を使用して、メールボックスのコンテンツを保持する期間を制御し、保存期間の期限が切れた後にコンテンツを削除します。</span><span class="sxs-lookup"><span data-stu-id="73900-161">Use [retention policies](retention-policies.md) in the Security &amp; Compliance Center to control how long mailbox content is retained, and then delete content after the retention period expires.</span></span> 
    
- <span data-ttu-id="73900-p117">Office 365 にデータをインポートすると、データの損失を防ぐことができます。Office 365 にインポートされた電子メールデータは、Exchange Online の高可用性機能を継承します。</span><span class="sxs-lookup"><span data-stu-id="73900-p117">Importing data to Office 365 helps protect against data loss. Email data that's imported to Office 365 inherits the high availability features of Exchange Online.</span></span>
    
- <span data-ttu-id="73900-164">Office 365 の電子メールデータは、クラウドに格納されているため、すべてのデバイスのユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="73900-164">Email data in Office 365 is available to users from all devices because it's stored in the cloud.</span></span>
    
## <a name="importing-sharepoint-data-to-office-365"></a><span data-ttu-id="73900-165">Office 365 に SharePoint データをインポートする</span><span class="sxs-lookup"><span data-stu-id="73900-165">Importing SharePoint data to Office 365</span></span>

<span data-ttu-id="73900-p118">また、Office 365 組織の SharePoint サイトや OneDrive アカウントにファイルやドキュメントをインポートすることもできます。詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73900-p118">You can also import files and documents to SharePoint sites and OneDrive accounts in your Office 365 organization. For more information, see the following articles:</span></span>

- [<span data-ttu-id="73900-168">SharePoint Online に移行する</span><span class="sxs-lookup"><span data-stu-id="73900-168">Migrate to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [<span data-ttu-id="73900-169">SharePoint 移行ツールの概要</span><span class="sxs-lookup"><span data-stu-id="73900-169">Introducing the SharePoint Migration Tool</span></span>](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [<span data-ttu-id="73900-170">PowerShell を使用して SharePoint Onine に移行する</span><span class="sxs-lookup"><span data-stu-id="73900-170">Migrate to SharePoint Online using PowerShell</span></span>](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- [<span data-ttu-id="73900-171">Azure データボックスを使用してファイル共有コンテンツを SharePoint Online に移行する</span><span class="sxs-lookup"><span data-stu-id="73900-171">Migrate your file share content to SharePoint Online using the Azure Data Box</span></span>](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a><span data-ttu-id="73900-172">Office 365 への PST ファイルのインポートに関してよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="73900-172">Frequently asked questions about importing PST files to Office 365</span></span>
  
<span data-ttu-id="73900-173">office 365 インポートサービスを使用して PST ファイルを office 365 メールボックスに一括インポートする方法についてよく寄せられる質問を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="73900-173">Here are some frequently asked questions about using the Office 365 Import service to bulk-import PST files to Office 365 mailboxes.</span></span> 
  
- [<span data-ttu-id="73900-174">ネットワークアップロードを使用して PST ファイルをインポートする</span><span class="sxs-lookup"><span data-stu-id="73900-174">Using network upload to import PST files</span></span>](#using-network-upload-to-import-pst-files)
  
- [<span data-ttu-id="73900-175">ドライブ配送を使用して PST ファイルをインポートする</span><span class="sxs-lookup"><span data-stu-id="73900-175">Using drive shipping to import PST files</span></span>](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="73900-176">ネットワークアップロードを使用して PST ファイルをインポートする</span><span class="sxs-lookup"><span data-stu-id="73900-176">Using network upload to import PST files</span></span>

 <span data-ttu-id="73900-177">**Office 365 インポートサービスでインポートジョブを作成するには、どのようなアクセス許可が必要ですか。**</span><span class="sxs-lookup"><span data-stu-id="73900-177">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="73900-p119">PST ファイルを Office 365 メールボックスにインポートするには、Exchange Online でメールボックスのインポートのエクスポートの役割を割り当てられている必要があります。既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。[組織の管理] 役割グループに、メールボックスのインポートのエクスポートの役割を追加できます。または、新しい役割グループを作成し、メールボックスのインポートのエクスポート役割を割り当てて、自分または他のユーザーをメンバーとして追加することもできます。詳細については、「 [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)」の「役割グループに役割を追加する」または「役割グループを作成する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73900-p119">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="73900-183">さらに、Office 365 セキュリティ&amp;コンプライアンスセンターでインポートジョブを作成するには、次のいずれかの条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="73900-183">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="73900-p120">Exchange Online では、メール受信者の役割が割り当てられている必要があります。既定では、この役割は組織の管理役割グループと受信者管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="73900-p120">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="73900-186">または</span><span class="sxs-lookup"><span data-stu-id="73900-186">Or</span></span>
    
- <span data-ttu-id="73900-187">Office 365 組織の全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="73900-187">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="73900-p121">Office 365 に PST ファイルをインポートするための特別な目的である Exchange Online に新しい役割グループを作成することを検討してください。PST ファイルのインポートに必要な最低限の特権レベルについては、メールボックスのインポートの役割とメール受信者の役割を新しい役割グループに割り当ててから、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="73900-p121">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="73900-190">**ネットワークアップロードを使用できる場所**</span><span class="sxs-lookup"><span data-stu-id="73900-190">**Where is network upload available?**</span></span>
  
<span data-ttu-id="73900-p122">ネットワークアップロードは現在、米国、カナダ、ブラジル、英国、ヨーロッパ、インド、東アジア、東南アジア、日本、韓国共和国、オーストラリアで利用できます。ネットワークアップロードは、近日中により多くの地域で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="73900-p122">Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="73900-193">**ネットワークアップロードを使用して PST ファイルをインポートする場合の価格設定について**</span><span class="sxs-lookup"><span data-stu-id="73900-193">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="73900-194">PST ファイルのインポートにネットワークアップロードを使用することは無料です。</span><span class="sxs-lookup"><span data-stu-id="73900-194">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="73900-p123">これは、PST ファイルが Azure ストレージ領域から削除された後に、Office 365 管理センターでインポートジョブが完了したファイルの一覧に表示されなくなったことも意味します。[ **Office にデータをインポート**します] ページにインポートジョブが表示されている可能性がありますが、古いインポートジョブの詳細を表示すると、PST ファイルの一覧は空の場合があります。</span><span class="sxs-lookup"><span data-stu-id="73900-p123">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Office 365 admin center. Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="73900-197">**Office 365 へのインポートでサポートされている PST ファイル形式のバージョン**</span><span class="sxs-lookup"><span data-stu-id="73900-197">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="73900-p124">PST ファイル形式には、ANSI と Unicode の2つのバージョンがあります。Unicode PST ファイル形式を使用するファイルをインポートすることをお勧めします。ただし、ANSI PST ファイル形式を使用するファイル (2 バイト文字セット (DBCS) を使用する言語など) は、Office 365 にインポートすることもできます。ANSI pst ファイルのインポートの詳細については、「[ネットワークアップロードを使用して pst ファイルを Office 365 にインポートする](https://go.microsoft.com/fwlink/p/?LinkId=823074)」の手順4を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73900-p124">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 4 in [Use network upload to import PST files to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074).</span></span>
  
<span data-ttu-id="73900-202">また、Outlook 2007 以降のバージョンの PST ファイルを Office 365 にインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="73900-202">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="73900-203">**PST ファイルを azure ストレージ領域にアップロードした後、削除される前に azure で保持されている期間はどのくらいか。**</span><span class="sxs-lookup"><span data-stu-id="73900-203">**After I upload my PST files to the Azure storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="73900-p125">network upload メソッドを使用して PST ファイルをインポートする場合は、 **ingestiondata**という名前の Azure blob コンテナーにアップロードします。セキュリティ&amp;コンプライアンスセンターの [**インポート**] ページで進行中のインポートジョブがない場合、Azure の**ingestiondata**コンテナーにあるすべての PST ファイルは、最新のインポートジョブがセキュリティ&amp;コンプライアンスセンターまた、セキュリティ&amp;コンプライアンスセンター (「ネットワークアップロードの手順」の手順 5) で新しいインポートジョブを作成してから、30日以内に PST ファイルを Azure にアップロードする必要があるということです。</span><span class="sxs-lookup"><span data-stu-id="73900-p125">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**. If there are no import jobs in progress on the **Import** page in the Security &amp; Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security &amp; Compliance Center. That also means you have to create a new import job in the Security &amp; Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="73900-p126">これは、PST ファイルが Azure ストレージ領域から削除された後に、セキュリティ&amp;コンプライアンスセンターで完了したインポートジョブのファイル一覧に表示されなくなったことも意味します。インポートジョブはセキュリティ&amp;コンプライアンスセンターの [**インポート**] ページに表示されることがありますが、以前のインポートジョブの詳細を表示すると、PST ファイルの一覧は空になることがあります。</span><span class="sxs-lookup"><span data-stu-id="73900-p126">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="73900-209">**PST ファイルをメールボックスにインポートするのにどのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="73900-209">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="73900-p127">ネットワークの容量によって異なりますが、通常は、組織の Azure ストレージ領域に各テラバイト (tb) のデータをアップロードするのに数時間かかります。pst ファイルが Azure ストレージ領域にコピーされると、1日あたり 24 GB 以上の速度で pst ファイルが Office 365 メールボックスにインポートされます。このレートがニーズに合わない場合は、電子メールデータを Office 365 に移行する他の方法を検討してください。詳細については、「[複数のメールアカウントを Office 365 に移行する方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73900-p127">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. After the PST files are copied to the Azure storage area, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="73900-p128">異なる PST ファイルが別のターゲットメールボックスにインポートされた場合、インポートプロセスは並行して実行されます。つまり、PST/メールボックスの各ペアは同時にインポートされます。同様に、複数の PST ファイルが同じメールボックスにインポートされると、それらのファイルは同時にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="73900-p128">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="73900-216">**PST ファイルのインポート時にメッセージサイズに制限はありますか。**</span><span class="sxs-lookup"><span data-stu-id="73900-216">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="73900-p129">うん。PST ファイルに 150 MB を超えるメールボックスアイテムが含まれている場合、インポート処理中にそのアイテムはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="73900-p129">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="73900-219">**は、メッセージが送受信された日時、受信者のリスト、および PST ファイルが Office 365 メールボックスにインポートされるときに保持されるメッセージのプロパティです。**</span><span class="sxs-lookup"><span data-stu-id="73900-219">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="73900-p130">うん。インポート処理中は、元のメッセージのメタデータは変更されません。</span><span class="sxs-lookup"><span data-stu-id="73900-p130">Yes. The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="73900-222">**メールボックスにインポートする PST ファイルのフォルダー階層のレベル数には制限がありますか。**</span><span class="sxs-lookup"><span data-stu-id="73900-222">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="73900-p131">うん。300以上のネストされたフォルダーがある PST ファイルをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="73900-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="73900-225">**ネットワークアップロードを使用して、Office 365 の非アクティブなメールボックスに PST ファイルをインポートできますか。**</span><span class="sxs-lookup"><span data-stu-id="73900-225">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="73900-226">はい、この機能は使用可能になりました。</span><span class="sxs-lookup"><span data-stu-id="73900-226">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="73900-227">**ネットワークアップロードを使用して、Exchange ハイブリッド展開のオンラインアーカイブメールボックスに PST ファイルをインポートできますか。**</span><span class="sxs-lookup"><span data-stu-id="73900-227">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="73900-228">はい、この機能は使用可能になりました。</span><span class="sxs-lookup"><span data-stu-id="73900-228">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="73900-229">**ネットワークアップロードを使用して、Exchange Online のパブリックフォルダーに PST ファイルをインポートできますか。**</span><span class="sxs-lookup"><span data-stu-id="73900-229">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="73900-230">いいえ。 PST ファイルをパブリックフォルダーにインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="73900-230">No, you can't import PST files to public folders.</span></span>
  
### <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="73900-231">ドライブ配送を使用して PST ファイルをインポートする</span><span class="sxs-lookup"><span data-stu-id="73900-231">Using drive shipping to import PST files</span></span>

 <span data-ttu-id="73900-232">**Office 365 インポートサービスでインポートジョブを作成するには、どのようなアクセス許可が必要ですか。**</span><span class="sxs-lookup"><span data-stu-id="73900-232">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="73900-p132">PST ファイルを Office 365 メールボックスにインポートするには、メールボックスのインポートのエクスポート役割が割り当てられている必要があります。既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。[組織の管理] 役割グループに、メールボックスのインポートのエクスポートの役割を追加できます。または、新しい役割グループを作成し、メールボックスのインポートのエクスポート役割を割り当てて、自分または他のユーザーをメンバーとして追加することもできます。詳細については、「 [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)」の「役割グループに役割を追加する」または「役割グループを作成する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73900-p132">You have to be assigned the Mailbox Import Export role to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="73900-238">さらに、Office 365 セキュリティ&amp;コンプライアンスセンターでインポートジョブを作成するには、次のいずれかの条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="73900-238">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="73900-p133">Exchange Online では、メール受信者の役割が割り当てられている必要があります。既定では、この役割は組織の管理役割グループと受信者管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="73900-p133">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="73900-241">または</span><span class="sxs-lookup"><span data-stu-id="73900-241">Or</span></span>
    
- <span data-ttu-id="73900-242">Office 365 組織の全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="73900-242">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="73900-p134">Office 365 に PST ファイルをインポートするための特別な目的である Exchange Online に新しい役割グループを作成することを検討してください。PST ファイルのインポートに必要な最低限の特権レベルについては、メールボックスのインポートの役割とメール受信者の役割を新しい役割グループに割り当ててから、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="73900-p134">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="73900-245">**ドライブ出荷の利用可能な場所**</span><span class="sxs-lookup"><span data-stu-id="73900-245">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="73900-p135">現時点では、ドライブの配送は米国、カナダ、ブラジル、英国、ヨーロッパ、インド、東アジア、東南アジア、日本、韓国共和国、オーストラリアで利用可能です。ドライブの配送は、近日中にさらに多くの地域で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="73900-p135">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Drive shipping will be available in more regions soon.</span></span>
  
 <span data-ttu-id="73900-248">**どのような商用ライセンス契約がドライブ出荷をサポートしていますか?**</span><span class="sxs-lookup"><span data-stu-id="73900-248">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="73900-p136">Office 365 に PST ファイルをインポートするためのドライブの送付は、Microsoft Enterprise アグリーメント (EA) を通じて利用できます。ドライブの送付は、Microsoft 製品およびサービス契約 (mpsa) 経由では利用できません。</span><span class="sxs-lookup"><span data-stu-id="73900-p136">Drive shipping to import PST files to Office 365 is available through a Microsoft Enterprise Agreement (EA). Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="73900-251">**PST ファイルを Office 365 にインポートするためにドライブ出荷を使用する場合の価格設定について**</span><span class="sxs-lookup"><span data-stu-id="73900-251">**What is the pricing for using drive shipping to import PST files to Office 365?**</span></span>
  
<span data-ttu-id="73900-p137">ドライブの配送を使用して PST ファイルを Office 365 メールボックスにインポートするためのコストは、1 GB あたり $2 USD です。たとえば、1000 GB (1 TB) の PST ファイルを含むハードドライブを出荷した場合、コストは $2000 USD になります。パートナーと協力して、インポート料金を支払うことができます。パートナーの検索の詳細について[は、「Office 365 パートナーまたは販売店を検索](https://go.microsoft.com/fwlink/p/?LinkId=785197)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73900-p137">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="73900-256">**ドライブの配送に対してサポートされているハードドライブの種類は何ですか。**</span><span class="sxs-lookup"><span data-stu-id="73900-256">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="73900-p138">Office 365 インポートサービスでの使用には、2.5 インチのソリッドステートドライブ (ssd) または2.5 または3.5 インチの SATA II/III 内部ハードドライブのみがサポートされています。ハードドライブは最大 10 TB まで使用できます。インポートジョブの場合、ハードドライブ上の最初のデータボリュームのみが処理されます。データボリュームは NTFS でフォーマットされている必要があります。データをハードドライブにコピーする場合は、2.5 インチ ssd または2.5 または3.5 インチ sata ii/iii コネクタを使用して直接接続できます。また、外部の2.5 インチ ssd または2.5 または3.5 インチの sata ii/iii USB アダプターを使用して外部に接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="73900-p138">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service. You can use hard drives up to 10 TB. For import jobs, only the first data volume on the hard drive will be processed. The data volume must be formatted with NTFS. When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="73900-p139">組み込みの USB アダプターが付属している外部ハードドライブは、Office 365 インポートサービスではサポートされていません。さらに、外部ハードドライブの大文字と小文字の内部にあるディスクは使用できません。外部ハードドライブを送付しないでください。</span><span class="sxs-lookup"><span data-stu-id="73900-p139">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="73900-265">**1つのインポートジョブに対して、何個のハードドライブを送付できますか。**</span><span class="sxs-lookup"><span data-stu-id="73900-265">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="73900-266">1つのインポートジョブに対して最大10台のハードドライブを出荷できます。</span><span class="sxs-lookup"><span data-stu-id="73900-266">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="73900-267">**ハードドライブを出荷した後、Microsoft データセンターにアクセスするのにどのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="73900-267">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="73900-p140">これは、Microsoft データセンターに近接していることや、ハードドライブの出荷に使用された送付オプションの種類 (翌営業日配信、2日配信、または地上配信) など、いくつかの事柄によって決まります。多くの仕入れ先では、追跡番号を使用して、配信の状態を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="73900-p140">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="73900-270">**Microsoft データセンターにハードドライブが到着した後、PST ファイルを Azure にアップロードするのにどのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="73900-270">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="73900-p141">microsoft データセンターでハードドライブを受信した後は、7 ~ 10 営業日かかります。 PST ファイルは、組織の Microsoft Azure ストレージ領域にアップロードされます。PST ファイルは、という名前`ingestiondata`の Azure blob コンテナーにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="73900-p141">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Microsoft Azure storage area for your organization. The PST files will be uploaded to a Azure blob container named `ingestiondata`.</span></span> 
  
 <span data-ttu-id="73900-273">**PST ファイルをメールボックスにインポートするのにどのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="73900-273">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="73900-p142">pst ファイルが Azure ストレージ領域にアップロードされると、Office 365 は pst ファイルのデータ (安全かつ安全な方法) を分析して、アイテムの保存期間と pst ファイルに含まれるさまざまなメッセージの種類を特定します。この分析が完了すると、PST ファイルのすべてのデータをインポートするか、インポートするデータを制御するフィルターを設定するかを選択できます。インポートジョブを開始すると、1日に 24 GB 以上の速度で PST ファイルが Office 365 メールボックスにインポートされます。このレートがニーズに合わない場合は、Office 365 に電子メールデータをインポートするためのその他の方法を検討することができます。詳細については、「[複数のメールアカウントを Office 365 に移行する方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73900-p142">After the PST files are uploaded to the Azure storage area, Office 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files. When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported. After you start the import job, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="73900-p143">異なる PST ファイルが別のターゲットメールボックスにインポートされた場合、インポートプロセスは並行して実行されます。つまり、PST/メールボックスの各ペアは同時にインポートされます。同様に、複数の PST ファイルが同じメールボックスにインポートされると、それらのファイルは同時にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="73900-p143">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="73900-281">**Microsoft は、PST ファイルを azure にアップロードした後、削除される前に azure に保存されている期間はどのくらいか。**</span><span class="sxs-lookup"><span data-stu-id="73900-281">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="73900-282">組織の Azure ストレージの場所 (名前付き`ingestiondata`blob コンテナー内) にあるすべての PST ファイルは、最新のインポートジョブが、セキュリティ&amp;コンプライアンスセンターの [**インポート**] ページで作成されてから30日後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="73900-282">All PST files in the Azure storage location for your organization (in blob container named `ingestiondata`), are deleted 30 days after the most recent import job was created on the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="73900-p144">これは、PST ファイルが Azure ストレージ領域から削除された後に、セキュリティ&amp;コンプライアンスセンターで完了したインポートジョブのファイル一覧に表示されなくなったことも意味します。インポートジョブはセキュリティ&amp;コンプライアンスセンターの [**インポート**] ページに表示されることがありますが、以前のインポートジョブの詳細を表示すると、PST ファイルの一覧は空になることがあります。</span><span class="sxs-lookup"><span data-stu-id="73900-p144">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="73900-285">**Office 365 へのインポートでサポートされている PST ファイル形式のバージョン**</span><span class="sxs-lookup"><span data-stu-id="73900-285">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="73900-p145">PST ファイル形式には、ANSI と Unicode の2つのバージョンがあります。Unicode PST ファイル形式を使用するファイルをインポートすることをお勧めします。ただし、ANSI PST ファイル形式を使用するファイル (2 バイト文字セット (DBCS) を使用する言語など) は、Office 365 にインポートすることもできます。ANSI pst ファイルのインポートの詳細については、「Use drive 送料」の手順3「[組織の pst ファイルを Office 365 にインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73900-p145">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import your organization PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="73900-290">また、Outlook 2007 以降のバージョンの PST ファイルを Office 365 にインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="73900-290">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="73900-291">**PST ファイルのインポート時にメッセージサイズに制限はありますか。**</span><span class="sxs-lookup"><span data-stu-id="73900-291">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="73900-p146">うん。PST ファイルに 150 MB を超えるメールボックスアイテムが含まれている場合、インポート処理中にそのアイテムはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="73900-p146">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="73900-294">**は、メッセージが送受信された日時、受信者のリスト、および PST ファイルが Office 365 メールボックスにインポートされるときに保持されるメッセージのプロパティです。**</span><span class="sxs-lookup"><span data-stu-id="73900-294">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="73900-p147">うん。インポート処理中に元のメッセージのメタデータが変更されない</span><span class="sxs-lookup"><span data-stu-id="73900-p147">Yes. The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="73900-297">**メールボックスにインポートする PST ファイルのフォルダー階層のレベル数には制限がありますか。**</span><span class="sxs-lookup"><span data-stu-id="73900-297">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="73900-p148">うん。300以上のネストされたフォルダーがある PST ファイルをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="73900-p148">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="73900-300">**ドライブの配送を使用して、Office 365 の非アクティブなメールボックスに PST ファイルをインポートできますか。**</span><span class="sxs-lookup"><span data-stu-id="73900-300">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="73900-301">はい、この機能は使用可能になりました。</span><span class="sxs-lookup"><span data-stu-id="73900-301">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="73900-302">**ドライブの配送を使用して、Exchange ハイブリッド展開のオンラインアーカイブメールボックスに PST ファイルをインポートできますか。**</span><span class="sxs-lookup"><span data-stu-id="73900-302">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="73900-303">はい、この機能は使用可能になりました。</span><span class="sxs-lookup"><span data-stu-id="73900-303">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="73900-304">**ドライブの配送を使用して、Exchange Online のパブリックフォルダーに PST ファイルをインポートできますか。**</span><span class="sxs-lookup"><span data-stu-id="73900-304">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="73900-305">いいえ。 PST ファイルをパブリックフォルダーにインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="73900-305">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="73900-306">**Microsoft は、自分に戻す前にハードドライブをワイプすることができますか?**</span><span class="sxs-lookup"><span data-stu-id="73900-306">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="73900-p149">いいえ。お客様に出荷する前に、Microsoft はハードドライブをワイプすることはできません。ハードドライブは、Microsoft によって受信されたときと同じ状態で返されます。</span><span class="sxs-lookup"><span data-stu-id="73900-p149">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="73900-309">**Microsoft は、自分のハードドライブを自分に出荷する代わりに、shred することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="73900-309">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="73900-p150">いいえ、Microsoft はハードドライブを破棄できません。ハードドライブは、Microsoft によって受信されたときと同じ状態で返されます。</span><span class="sxs-lookup"><span data-stu-id="73900-p150">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="73900-312">**返品出荷に対してサポートされている媒体使用サービスについて**</span><span class="sxs-lookup"><span data-stu-id="73900-312">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="73900-p151">米国またはヨーロッパのお客様の場合、Microsoft は FedEx を使用してハードドライブを返却しています。その他の地域の場合、Microsoft は DHL を使用します。</span><span class="sxs-lookup"><span data-stu-id="73900-p151">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="73900-315">**返品送料のコストはどの程度ですか。**</span><span class="sxs-lookup"><span data-stu-id="73900-315">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="73900-p152">返品配送費用は、ハードドライブを送付した Microsoft データセンターへの近接度によって異なります。Microsoft は、FedEx または DHL アカウントを請求して、ハードドライブを返します。返品配送のコストは責任を負っています。</span><span class="sxs-lookup"><span data-stu-id="73900-p152">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="73900-319">**FedEx custom 送料などのカスタムの宅配便サービスを使用して、Microsoft にハードドライブを送付できますか。**</span><span class="sxs-lookup"><span data-stu-id="73900-319">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="73900-320">はい。</span><span class="sxs-lookup"><span data-stu-id="73900-320">Yes.</span></span>
  
 <span data-ttu-id="73900-321">**別の国にハードドライブを送付する必要がある場合は、何が必要ですか。**</span><span class="sxs-lookup"><span data-stu-id="73900-321">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="73900-p153">Microsoft に出荷するハードドライブは、国際的な国境を越える必要がある場合があります。その場合は、該当する法律に従ってハードドライブとそれに含まれるデータがインポートまたはエクスポートされていることを確認する責任があります。ハードドライブを出荷する前に、アドバイザーに確認して、指定した Microsoft データセンターに、ドライブとデータが合法的に出荷されることを確認してください。これにより、適切なタイミングで Microsoft に到達していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="73900-p153">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
