---
title: Office 365 のセキュリティとコンプライアンスのセンターからのコンテンツの検索結果をエクスポートします。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: 'Office 365 のセキュリティ コンテンツの検索から検索結果をエクスポートする&amp;コンプライアンス センターをローカル コンピューターにします。Emaill メールの結果は、PST ファイルとしてエクスポートされます。ビジネス サイトは、ネイティブの Office ドキュメントとしてエクスポートするには、SharePoint と OneDrive のコンテンツです。 '
ms.openlocfilehash: 35fb0aa8a037fc77020269d1b42d738dd801ea0a
ms.sourcegitcommit: da4aa7335b577148ecd61e09bbb11039b817b287
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26539119"
---
# <a name="export-content-search-results-from-the-office-365-security--compliance-center"></a><span data-ttu-id="82bef-105">Office 365 のセキュリティとコンプライアンスのセンターからのコンテンツの検索結果をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="82bef-105">Export Content Search results from the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="82bef-p102">コンテンツの検索が正常に実行すると、検索結果をローカル コンピューターにエクスポートできます。メールの結果をエクスポートする場合は、PST ファイルとしてコンピューターにダウンロードしています。SharePoint および OneDrive からビジネス サイトのコンテンツをエクスポートする場合は、ネイティブの Office ドキュメントのコピーがエクスポートされます。追加のドキュメントおよびエクスポートした検索結果に含まれているレポートがあります。</span><span class="sxs-lookup"><span data-stu-id="82bef-p102">After a Content Search is successfully run, you can export the search results to a local computer. When you export email results, they're downloaded to your computer as PST files. When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents are exported. There are additional documents and reports that are included with the exported search results.</span></span>
  
<span data-ttu-id="82bef-p103">さらに、コンテンツの検索結果に含まれるすべての RMS で暗号化された電子メール メッセージが復号化としてエクスポートするときに (個々 のメッセージ)。この復号化機能は、電子的証拠開示マネージャーの役割グループのメンバーに対して既定で有効です。復号する RMS 管理の役割がこのロール グループに割り当てられているためにです。検索結果をエクスポートする場合は、RMS の復号化の詳細についての[詳細について](#more-information)はセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p103">Additionally, any RMS-encrypted email messages that are included in the results of a Content Search will be decrypted when you export them (as individual messages). This decryption capability is enabled by default for members of the eDiscovery Manager role group. This is because the RMS Decrypt management role is assigned to this role group. See the [More information](#more-information) section for details about RMS decryption when you export search results.</span></span> 
  
<span data-ttu-id="82bef-114">コンテンツ検索の結果をエクスポートするには、結果を準備して、ローカル コンピューターにダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82bef-114">Exporting the results of a Content Search involves preparing the results, and then downloading them to a local computer.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="82bef-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="82bef-115">Before you begin</span></span>

- <span data-ttu-id="82bef-p104">検索結果をエクスポートするには、Office 365 のセキュリティのエクスポートの管理役割を割り当てる必要がある&amp;コンプライアンス センターです。このロールは、組み込みの電子的証拠開示マネージャーの役割グループに割り当てられます。組織の管理役割グループに既定で割り当てられますことはありません。詳細についてを参照してください[Office 365 のセキュリティ、電子的証拠開示のアクセス許可を割り当てる&amp;コンプライアンス センター](assign-ediscovery-permissions.md)です。</span><span class="sxs-lookup"><span data-stu-id="82bef-p104">To export search results, you have to be assigned the Export management role in the Office 365 Security &amp; Compliance Center. This role is assigned to the built-in eDiscovery Manager role group. It isn't assigned by default to the Organization Management role group. For more information, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="82bef-120">検索結果をエクスポートする際に使用するコンピューターは、次のシステム要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="82bef-120">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="82bef-121">32 ビットおよび 64 ビット バージョンの Windows 7 およびそれ以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="82bef-121">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="82bef-122">Microsoft.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="82bef-122">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="82bef-123">サポートされているブラウザー:</span><span class="sxs-lookup"><span data-stu-id="82bef-123">A supported browser:</span></span>
    
     - <span data-ttu-id="82bef-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="82bef-124">Microsoft Edge</span></span>
    
        <span data-ttu-id="82bef-125">または</span><span class="sxs-lookup"><span data-stu-id="82bef-125">OR</span></span>
    
     - <span data-ttu-id="82bef-126">Microsoft インターネット エクスプ ローラー 10 およびそれ以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="82bef-126">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="82bef-p105">**注:** マイクロソフトではサードパーティ製の拡張機能またはアドオンの ClickOnce アプリケーションを製造します。アドオンまたはサードパーティ製の拡張機能でサポートされていないブラウザーを使用して検索結果のエクスポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="82bef-p105">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications. Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 
    
- <span data-ttu-id="82bef-p106">(手順 2 で説明します) の検索結果をダウンロードするときは、検索結果をエクスポートするのにを使用するコンピューターの Windows レジストリ設定を構成することによってダウンロード速度を強化できます。詳細については、 [Office 365 からの電子的証拠開示検索結果をエクスポートするときのダウンロード速度を向上させる](increase-download-speeds-when-exporting-ediscovery-results.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p106">When you download search results (described in Step 2), you can increase the download speed by configuring a Windows Registry setting on the computer you use to export the search results. For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
    
- <span data-ttu-id="82bef-p107">検索結果をエクスポートする場合、ローカル コンピューターにダウンロードされる前にデータがマイクロソフト クラウドに固有の Microsoft Azure ストレージ場所に一時的に格納されます。組織が、Azure でエンドポイントに接続できるかどうかを必ず**\*です。 blob.core.windows.net** (ワイルドカードは、エクスポートの一意の識別子を表します)。作成後、2 週間、Azure ストレージの場所から検索結果のデータが削除されます。</span><span class="sxs-lookup"><span data-stu-id="82bef-p107">When you export search results, the data is temporarily stored in a unique Microsoft Azure storage location in the Microsoft cloud before it's downloaded to your local computer. Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export). The search results data is deleted from the Azure storage location two weeks after it's created.</span></span> 
    
- <span data-ttu-id="82bef-p108">組織では、インターネットと通信するプロキシ サーバーを使用している場合は、(エクスポート ツールは、プロキシ サーバーによって認証されることができます) ので、検索結果をエクスポートするのにを使用しているコンピューター上のプロキシ サーバーの設定を定義する必要があります。これを行うには、Windows のバージョンに一致する場所に*machine.config*ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="82bef-p108">If your organization uses a proxy server to communicate with the Internet, you need to define the proxy server settings on the computer that you use to export the search results (so the export tool can be authenticated by your proxy server). To do this, open the  *machine.config*  file in the location that matches your version of Windows.</span></span> 
    
  - <span data-ttu-id="82bef-136">**32 ビット** - `%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`</span><span class="sxs-lookup"><span data-stu-id="82bef-136">**32-bit** - `%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`</span></span>
    
  - <span data-ttu-id="82bef-137">**64 ビット** - `%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`</span><span class="sxs-lookup"><span data-stu-id="82bef-137">**64-bit** - `%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`</span></span>
    
    <span data-ttu-id="82bef-p109">間では、 *machine.config*ファイルをどこかに次の行を追加、`<configuration>`と`</configuration>`のタグです。交換してください`ProxyServer`と`Port`、組織に適切な値を持つたとえば、 `proxy01.contoso.com:80` 。</span><span class="sxs-lookup"><span data-stu-id="82bef-p109">Add the following lines to the  *machine.config*  file somewhere between the  `<configuration>` and  `</configuration>` tags. Be sure to replace  `ProxyServer` and  `Port` with the correct values for your organization; for example,  `proxy01.contoso.com:80` .</span></span> 
    
    ```
    <system.net>
       <defaultProxy enabled="true" useDefaultCredentials="true">
         <proxy proxyaddress="http://ProxyServer :Port " 
                usesystemdefault="False" 
                bypassonlocal="True" 
                autoDetect="False" />
       </defaultProxy>
    </system.net>
    ```

- <span data-ttu-id="82bef-140">検索結果をエクスポートするための制限の説明についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-140">See the  section for a description of the limits for exporting search results.</span></span> 
    
- <span data-ttu-id="82bef-p110">エクスポート可能な PST ファイルの最大サイズは、10 GB です。この既定のサイズを変更する場合は、検索結果のエクスポートに使用するコンピューターの Windows レジストリを編集できます。[電子的証拠開示検索結果をエクスポートするときに、PST ファイルのサイズを変更](change-the-size-of-pst-files-when-exporting-results.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p110">The maximum size of a PST file that can be exported is 10 GB. If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results. See [Change the size of PST files when exporting eDiscovery search results](change-the-size-of-pst-files-when-exporting-results.md).</span></span>
    
## <a name="step-1-prepare-search-results-for-export"></a><span data-ttu-id="82bef-144">手順 1: エクスポートする検索結果を準備する</span><span class="sxs-lookup"><span data-stu-id="82bef-144">Step 1: Prepare search results for export</span></span>

<span data-ttu-id="82bef-p111">エクスポートするための検索結果を準備するのには、まずです。結果を準備するときは、マイクロソフトのクラウドでは、Azure ストレージの場所にアップロードされます。メールボックスとサイトからコンテンツことに注意は、1 時間あたり最大 2 GB の速度でアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="82bef-p111">The first step is to prepare the search results for exporting. When you prepare results, they are uploaded to an Azure storage location in the Microsoft cloud. Note that content from mailboxes and sites is uploaded at a maximum rate of 2 GB per hour.</span></span>
  
1. <span data-ttu-id="82bef-148">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="82bef-148">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="82bef-149">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="82bef-149">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="82bef-150">セキュリティ/コンプライアンス センターの左側のウィンドウで、**[検索と調査]** \> **[コンテンツ検索]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="82bef-150">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**.</span></span>
    
4. <span data-ttu-id="82bef-151">**コンテンツの検索**ページで、検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="82bef-151">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="82bef-152">詳細ウィンドウの **[結果をコンピューターにエクスポートする]** で、**[エクスポートの開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82bef-152">In the details pane, under **Export results to a computer**, click **Start export**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="82bef-p112">検索の結果が 7 日よりも前の場合は、検索結果を更新するように求められます。この場合は、エクスポートをキャンセルして、選んだ検索の詳細ウィンドウの **[検索結果の更新]** をクリックして、結果が更新された後で、エクスポートをもう一度開始します。 </span><span class="sxs-lookup"><span data-stu-id="82bef-p112">If the results for a search are older than 7 days, you are prompted to update the search results. If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="82bef-155">**検索結果のエクスポート**] ページの**検索でこれらの項目を含める**には、次のオプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="82bef-155">On the **Export the search results** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="82bef-156">インデックス付きのアイテムのみをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="82bef-156">Export only indexed items</span></span>
    
    - <span data-ttu-id="82bef-157">インデックスを作成し、部分的にインデックス付きのアイテムをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="82bef-157">Export indexed and partially indexed items</span></span>
    
    - <span data-ttu-id="82bef-158">部分的にインデックス付きのアイテムのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="82bef-158">Export only partially indexed items</span></span>
    
    <span data-ttu-id="82bef-p113">部分的にどのようにインデックス付きの項目に関する説明は、エクスポートの[詳細について](#more-information)はセクションを参照してください。部分的にインデックス付きのアイテムの詳細については、[一部のコンテンツの検索項目をインデックス](partially-indexed-items-in-content-search.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p113">See the [More information](#more-information) section for a description about how partially indexed items are exported. For more information about partially indexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="82bef-161">[**エクスポートする Exchange のコンテンツとして**、次のオプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="82bef-161">Under **Export Exchange content as**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="82bef-p114">**メールボックスごとに 1 つの PST ファイル**には、検索結果が含まれる各ユーザーのメールボックスの 1 つの PST ファイルをエクスポートします。同じ PST ファイルには、ユーザーのアーカイブ メールボックスからすべての結果が含まれます。このオプションが移行元のメールボックスからメールボックスのフォルダー構造を再現することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p114">**One PST file for each mailbox** - Exports one PST file for each user mailbox that contains search results. Any results from the user's archive mailbox are included in the same PST file. Note that this option reproduces the mailbox folder structure from the source mailbox.</span></span> 
    
    - <span data-ttu-id="82bef-p115">**1 つの PST ファイルのすべてのメッセージが含まれている**のでは、単一 PST ファイル ( *Exchange.pst*という名前)、検索に含まれるすべてのソース メールボックスから検索結果が含まれるをエクスポートします。このオプションがメッセージごとに、メールボックスのフォルダー構造を再現することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p115">**One PST file containing all messages** - Exports a single PST file (named  *Exchange.pst*  ) that contains the search results from all source mailboxes included in the search. Note that this option reproduces the mailbox folder structure for each message.</span></span> 
    
    - <span data-ttu-id="82bef-p116">**1 つの PST ファイルには、1 つのフォルダー内のすべてのメッセージが含まれている**が、単一の最上位のフォルダーにあるすべてのメッセージ 1 つの PST ファイルを検索結果のエクスポートです。このオプションは、校閲者の各項目の元のメールボックス フォルダーの構造を移動することがなく (アイテムは送信日時で並べ替え) の順に項目を確認できます。</span><span class="sxs-lookup"><span data-stu-id="82bef-p116">**One PST file containing all messages in a single folder** - Exports search results to a single PST file where all messages are located in a single, top-level folder. This option lets reviewers review items in chronological order (items are sorted by sent date) without having to navigate the original mailbox folder structure for each item.</span></span> 
    
    - <span data-ttu-id="82bef-p117">**個々 のメッセージ**のエクスポートの検索結果として、個々 の電子メール メッセージ .msg 形式を使用します。このオプションを選択した場合、ファイル システムのフォルダーにメールの検索結果がエクスポートされます。メッセージを個別のフォルダーのパスは、PST ファイルに結果をエクスポートする場合に使用されるものと同じです。</span><span class="sxs-lookup"><span data-stu-id="82bef-p117">**Individual messages** - Exports search results as individual email messages, using the .msg format. If you select this option, email search results are exported to a folder in the file system. The folder path for individual messages is the same as the one used if you exported the results to PST files.</span></span> 
    
      > [!IMPORTANT]
      > <span data-ttu-id="82bef-p118">それらをエクスポートしている場合は、RMS で暗号化されたメッセージを復号化、個々 のメッセージとして電子メールの検索結果をエクスポートする必要があります。PST ファイルとして検索結果をエクスポートする場合、暗号化されたメッセージは暗号化されたままです。</span><span class="sxs-lookup"><span data-stu-id="82bef-p118">To decrypt RMS-encrypted messages when they're exported, you must export email search results as individual messages. Encrypted messages will remain encrypted if you export the search results as a PST file.</span></span> 
  
8. <span data-ttu-id="82bef-p119">重複メッセージを除外するのには **、重複除外を有効にする**チェック ボックスをクリックします。検索のコンテンツ ソースには、Exchange メールボックスまたはパブリック フォルダーが含まれて 場合にのみ、このオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82bef-p119">Click the **Enable de-duplication** checkbox to exclude duplicate messages. This option appears only if the content sources of the search includes Exchange mailboxes or public folders.</span></span> 
    
    <span data-ttu-id="82bef-p120">このオプションを選択する場合は、検索されたメールボックスに同じメッセージの複数のコピーが含まれている場合でもメッセージのコピーが 1 つだけがエクスポートされます。メールボックス、パブリック フォルダー) を識別できるように、重複したメッセージのコピーがすべての行が含まれます (Results.csv) のレポートのエクスポートの結果、重複したメッセージのコピーが含まれています。について重複し、重複した項目を識別する詳細については、[電子的証拠開示検索結果内の重複](de-duplication-in-ediscovery-search-results.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p120">If you select this option, only one copy of a message will be exported even if multiple copies of the same message are found in the mailboxes that were searched. The export results report (Results.csv) will contain a row for every copy of a duplicate message so that you can identify the mailboxes (or public folders) that contain a copy of the duplicate message. For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>
    
9. <span data-ttu-id="82bef-p121">SharePoint ドキュメントのすべてのバージョンをエクスポートするのには、 **SharePoint ドキュメントのバージョンを含める**] チェック ボックスをクリックします。検索のコンテンツ ソースには、SharePoint または OneDrive ビジネス サイトの場合にのみ、このオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82bef-p121">Click the **Include versions for SharePoint documents** checkbox to export all versions of SharePoint documents. This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span> 
    
10. <span data-ttu-id="82bef-p122">圧縮フォルダーに検索結果をエクスポートするのには [**圧縮 (zip 形式) フォルダー内のファイルをエクスポートする**] チェック ボックスをクリックします。このオプションは、SharePoint または OneDrive のドキュメントが検索結果に含まれている場合、個々 のメッセージとして Exchange アイテムをエクスポートする場合にのみ使用できます。このオプションは、アイテムをエクスポートする際に Windows のファイルのパス名の 260 文字の制限を回避するのには主に使用します。「ファイル名エクスポートされたアイテムの「[詳細](#more-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p122">Click the **Export files in a compressed (zipped) folder** checkbox to export search results to compressed folders. This option is available only when you choose to export Exchange items as individual messages and when the search results include SharePoint or OneDrive documents. This option is primarily used to work around the 260 character limit in Windows file path names when items are exported. See the "Filenames of exported items" in the [More information](#more-information) section.</span></span> 
    
11. <span data-ttu-id="82bef-185">**[エクスポートの開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82bef-185">Click **Start export**.</span></span>
    
    <span data-ttu-id="82bef-p123">検索結果を準備するは、ダウンロードのマイクロソフトのクラウド内の Azure ストレージ場所にアップロードされていることを意味する場合。検索結果では、ダウンロードの準備が整ったらは、詳細ペインで、**コンピューターに結果をエクスポートする**] の下**のダウンロード結果のエクスポート**のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82bef-p123">The search results are prepared for downloading, which means they're being uploaded to the Azure storage location in the Microsoft cloud. When the search results are ready for download, the **Download exported results** link is displayed under **Export results to a computer** in the details pane.</span></span> 
  
## <a name="step-2-download-the-search-results"></a><span data-ttu-id="82bef-188">手順 2:検索結果をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="82bef-188">Step 2: Download the search results</span></span>

<span data-ttu-id="82bef-189">次の手順では、Azure ストレージの場所から検索結果をローカル コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="82bef-189">The next step is to download the search results from the Azure storage location to your local computer.</span></span>
  
<span data-ttu-id="82bef-p124">説明したようには、検索結果をエクスポートするのにを使用するコンピューターの Windows レジストリ設定を構成することによってダウンロード速度を強化できます。詳細については、 [Office 365 からの電子的証拠開示検索結果をエクスポートするときのダウンロード速度を向上させる](increase-download-speeds-when-exporting-ediscovery-results.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p124">As previously explained, you can increase the download speed by configuring a Windows Registry setting on the computer you use to export the search results. For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
  
1. <span data-ttu-id="82bef-192">エクスポートを開始した検索の詳細ウィンドウの **[結果をコンピューターにエクスポートする]** で、**[エクスポートした結果をダウンロードする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82bef-192">In the details pane for the search that you started the export for, under **Export results to a computer**, click **Download exported results**.</span></span>
    
    <span data-ttu-id="82bef-193">**ダウンロード結果のエクスポート**] ウィンドウが表示され、コンピューターにダウンロードされる検索結果に関する次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="82bef-193">The **Download exported results** window is displayed and contains the following information about the search results that will be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="82bef-194">ダウンロードされるアイテムの数。</span><span class="sxs-lookup"><span data-stu-id="82bef-194">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="82bef-195">ダウンロードされるアイテムの推定合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="82bef-195">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="82bef-p125">エクスポートされる内容にインデックスが付いているかどうか。インデックスのないアイテムは、形式が認識されているアイテム、暗号化されているアイテム、他の理由でインデックスが作成されなかったアイテムのいずれかです。詳細については、「[Unindexed items in Content Search](partially-indexed-items-in-content-search.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p125">Whether indexed or unindexed will be exported. Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons. For more information, see [Unindexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
    - <span data-ttu-id="82bef-199">SharePoint ドキュメントのバージョンがダウンロードされるかどうか。</span><span class="sxs-lookup"><span data-stu-id="82bef-199">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="82bef-p126">エクスポートの準備プロセスの状態。データの準備が完了していない場合でも、検索結果のダウンロードを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="82bef-p126">The status of the export preparation process. You can start downloading search results even if the preparation of the data isn't complete.</span></span>
    
2. <span data-ttu-id="82bef-p127">**[エクスポート キー]** で、**[クリップボードにコピー]** をクリックします。このキーは手順 5 で検索結果をダウンロードする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="82bef-p127">Under **Export key**, click **Copy to clipboard**. You will use this key in step 5 to download the search results.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="82bef-204">電子情報開示エクスポート ツールをインストールして開始し、このキーを使用して検索結果をダウンロードすることはだれにでもできるため、このキーは、パスワードやその他のセキュリティ関連の情報を保護する場合と同様の予防策を講じてください。 </span><span class="sxs-lookup"><span data-stu-id="82bef-204">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search results, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="82bef-205">**[結果のダウンロード]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82bef-205">Click **Download results**.</span></span>
    
4. <span data-ttu-id="82bef-206">**MicrosoftOffice 365 電子的証拠開示のエクスポート ツール**をインストールするメッセージが表示されたら、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82bef-206">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="82bef-207">**電子情報開示エクスポート ツール**で、手順 2 でコピーしたエクスポート キーを適切なボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="82bef-207">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="82bef-208">**[参照]** をクリックして、検索結果のファイルをダウンロードする場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="82bef-208">Click **Browse** to specify the location where you want to download the search result files.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="82bef-209">により、大量のディスク ・ アクティビティ (読み取りおよび書き込み)、ローカルのディスク ドライブに検索結果をダウンロードする必要があります。マップされたネットワーク ドライブまたはその他のネットワーク上の場所にそれらをダウンロードしないでください。</span><span class="sxs-lookup"><span data-stu-id="82bef-209">Due to the high amount of disk activity (reads and writes), you should download search results to a local disk drive; don't download them to a mapped network drive or other network location.</span></span> 
  
1. <span data-ttu-id="82bef-210">**[開始]** をクリックして、検索結果をコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="82bef-210">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="82bef-p128">**EDiscovery ツールのエクスポート**には、数 (サイズ) の残りのアイテムをダウンロードする推定値を含む、エクスポート プロセスに関するステータス情報が表示されます。エクスポート処理が完了すると、ダウンロードした場所にファイルをアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="82bef-p128">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    

  
## <a name="more-information"></a><span data-ttu-id="82bef-213">詳細情報</span><span class="sxs-lookup"><span data-stu-id="82bef-213">More information</span></span>

<span data-ttu-id="82bef-214">検索結果のエクスポートの詳細については、ここで。</span><span class="sxs-lookup"><span data-stu-id="82bef-214">Here's more information about exporting search results.</span></span>
  
[<span data-ttu-id="82bef-215">エクスポートの制限</span><span class="sxs-lookup"><span data-stu-id="82bef-215">Export limits</span></span>](#export-limits)
  
[<span data-ttu-id="82bef-216">レポートをエクスポート</span><span class="sxs-lookup"><span data-stu-id="82bef-216">Export reports</span></span>](#export-reports)
  
[<span data-ttu-id="82bef-217">部分的にインデックス付きのアイテムをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="82bef-217">Exporting partially indexed items</span></span>](#exporting-partially-indexed-items)

[<span data-ttu-id="82bef-218">個々 のメッセージまたは PST ファイルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="82bef-218">Exporting individual messages or PST files</span></span>](#exporting-individual-messages-or-pst-files)
  
[<span data-ttu-id="82bef-219">RMS で暗号化されたメッセージを復号化</span><span class="sxs-lookup"><span data-stu-id="82bef-219">Decrypting RMS-encrypted messages</span></span>](#decrypting-rms-encrypted-messages)

[<span data-ttu-id="82bef-220">エクスポートされたアイテムのファイル名</span><span class="sxs-lookup"><span data-stu-id="82bef-220">Filenames of exported items</span></span>](#filenames-of-exported-items)  
  
[<span data-ttu-id="82bef-221">その他</span><span class="sxs-lookup"><span data-stu-id="82bef-221">Miscellaneous</span></span>](#miscellaneous)
  
 ### <a name="export-limits"></a><span data-ttu-id="82bef-222">エクスポートの制限</span><span class="sxs-lookup"><span data-stu-id="82bef-222">Export limits</span></span>
  
- <span data-ttu-id="82bef-223">セキュリティから検索結果をエクスポートする&amp;コンプライアンス センターには次の制限。</span><span class="sxs-lookup"><span data-stu-id="82bef-223">Exporting search results from the Security &amp; Compliance Center has the following limits:</span></span>
    
  - <span data-ttu-id="82bef-p129">最大 2 TB のデータをエクスポートするには 1 つのコンテンツ検索から。検索結果が 2 TB より大きい場合は、日付の範囲またはその他の種類のフィルターを使用して、検索結果の合計サイズを小さくことを検討します。</span><span class="sxs-lookup"><span data-stu-id="82bef-p129">You can export a maximum of 2 TB of data from a single Content Search. If the search results are larger than 2 TB, consider using date ranges or other types of filters to decrease the total size of the search results.</span></span>
    
  - <span data-ttu-id="82bef-226">組織は、1 日の中に、最大 2 TB のデータをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="82bef-226">Your organization can export a maximum of 2 TB of data during a single day.</span></span>
    
  - <span data-ttu-id="82bef-227">組織内で最大 10 のエクスポートを同時に実行することができます。</span><span class="sxs-lookup"><span data-stu-id="82bef-227">You can have a maximum of 10 exports running at the same time within your organization.</span></span>
    
  - <span data-ttu-id="82bef-228">1 人のユーザーは、同時に最大 3 つのエクスポートを実行できます。</span><span class="sxs-lookup"><span data-stu-id="82bef-228">A single user can run a maximum of three exports at the same time.</span></span>
    
  - <span data-ttu-id="82bef-229">コンテンツの検索レポートをエクスポートするエクスポートの制限のいずれかに対しては入りません。</span><span class="sxs-lookup"><span data-stu-id="82bef-229">Exporting Content Search reports doesn't count against any of the export limits.</span></span> 
    
- <span data-ttu-id="82bef-230">述べたように、メールボックス、およびサイトからの検索結果は、Azure ストレージの場所にアップロードされます (で説明するよう[手順 1: 準備の検索結果のエクスポート](#step-1-prepare-search-results-for-export)) 1 時間あたり最大 2 GB の速度で。</span><span class="sxs-lookup"><span data-stu-id="82bef-230">As previously stated, search results from mailboxes and sites are uploaded to the Azure storage location (as described in [Step 1: Prepare search results for export](#step-1-prepare-search-results-for-export)) at a maximum rate of 2 GB per hour.</span></span>
    
- <span data-ttu-id="82bef-p130">エクスポート可能な PST ファイルの最大サイズは、既定で 10 GB です。メールボックスの検索結果を 2 つ (以上) の別の PST ファイルにエクスポートするユーザーのメールボックスの検索結果が 10 GB より大きい場合は、ことを意味します。さらに、1 つの PST ファイル内のすべての検索結果をエクスポートする場合は、PST ファイルがあります spilt 追加の PST ファイルに検索結果の合計サイズが 10 GB より大きい場合。この既定のサイズを変更する場合は、検索結果のエクスポートに使用するコンピューターの Windows レジストリを編集できます。[電子的証拠開示検索結果をエクスポートするときに、PST ファイルのサイズを変更](change-the-size-of-pst-files-when-exporting-results.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p130">The maximum size of a PST file that can be exported is 10 GB by default. That means if the search results from a user's mailbox are larger than 10 GB, the search results for the mailbox will be exported in two (or more) separate PST files. Additionally, if you choose to export all search results in a single PST file, the PST file will be spilt into additional PST files if the total size of the search results is larger than 10 GB. If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results. See [Change the size of PST files when exporting eDiscovery search results](change-the-size-of-pst-files-when-exporting-results.md).</span></span>
    
    <span data-ttu-id="82bef-p131">さらに、特定のメールボックスの検索結果はありませんに分割される複数の PST ファイル 1 つのメールボックスからの内容は、10 GB を超える場合を除き、します。検索結果をエクスポートする場合は 1 つの pst には、そのファイルに 1 つのフォルダー内のすべてのメッセージが含まれていますと検索結果が 10 GB より大きい、ため、これらは、送信済みの d に基づく追加の PST ファイルに spilt は作成順でアイテムの整理も作成 ()。</span><span class="sxs-lookup"><span data-stu-id="82bef-p131">Additionally, the search results from a specific mailbox won't be divided among multiple PST files unless the content from a single mailbox is more than 10 GB. If you chose to export the search results in one PST file for that contains all messages in a single folder and the search results are larger than 10 GB, the items are still organized in chronological order, so they will be spilt into additional PST files based on the sent date.</span></span>
     
 ### <a name="export-reports"></a><span data-ttu-id="82bef-238">レポートをエクスポート</span><span class="sxs-lookup"><span data-stu-id="82bef-238">Export reports</span></span>
  
- <span data-ttu-id="82bef-239">検索結果をエクスポートする場合、次のレポートは、検索結果と共に含まれます。</span><span class="sxs-lookup"><span data-stu-id="82bef-239">When you export search results, the following reports are included in addition to the search results.</span></span>
    
  - <span data-ttu-id="82bef-p132">**エクスポートの概要**Excel ファイルをエクスポートの概要が含まれています。これには、検索されたコンテンツ ソースの数、検索結果、およびエクスポートされたアイテム数の推定とダウンロードしたの推定とダウンロードのサイズなどの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="82bef-p132">**Export Summary** An Excel document that contains a summary of the export. This includes information such as the number of content sources that were searched, the estimated and downloaded sizes of the search results, and the estimated and downloaded number of items that were exported.</span></span> 
    
  - <span data-ttu-id="82bef-242">**マニフェスト**マニフェスト ファイル (XML 形式) で、検索結果に含まれる各アイテムに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="82bef-242">**Manifest** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
  - <span data-ttu-id="82bef-p133">**結果**Excel ファイルを検索結果としては、ダウンロードする各アイテムに関する情報が含まれています。電子メールでは、結果のログに、各メッセージに関する情報が含まれているなど。</span><span class="sxs-lookup"><span data-stu-id="82bef-p133">**Results** An Excel document that contains information about each item that is download as a search result. For email, the result log contains information about each message, including:</span></span> 
    
      - <span data-ttu-id="82bef-245">移行元のメールボックス内のメッセージの場所 (メッセージがプライマリ メールボックスとアーカイブ メールボックスのどちらであるかを含みます)。</span><span class="sxs-lookup"><span data-stu-id="82bef-245">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
        
      - <span data-ttu-id="82bef-246">メッセージが送信または受信された日付。</span><span class="sxs-lookup"><span data-stu-id="82bef-246">The date the message was sent or received.</span></span>
        
      - <span data-ttu-id="82bef-247">メッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="82bef-247">The Subject line from the message.</span></span>
        
      - <span data-ttu-id="82bef-248">メッセージの送信者と受信者。</span><span class="sxs-lookup"><span data-stu-id="82bef-248">The sender and recipients of the message.</span></span>
        
      - <span data-ttu-id="82bef-p134">かどうか、メッセージは、検索結果をエクスポートするときに、重複除外オプションを有効にした場合、重複するメッセージです。重複したメッセージは、重複メッセージを識別する**項目に重複する**列の値があります。**項目に重複する**列の値には、エクスポートされたメッセージの項目 id が含まれています。詳細については、[電子的証拠開示検索結果内の重複](de-duplication-in-ediscovery-search-results.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p134">Whether the message is a duplicate message if you enabled the de-duplication option when exporting the search results. Duplicate messages will have a value in the **Duplicate to Item** column that identifies the message as a duplicate. The value in the **Duplicate to Item** column contains the item identity of the message that was exported. For more information, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>
        
      <span data-ttu-id="82bef-253">各ドキュメントに関する情報が含まれますビジネス サイトのドキュメント SharePoint と OneDrive から、には結果のログには含みます。</span><span class="sxs-lookup"><span data-stu-id="82bef-253">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
        
      - <span data-ttu-id="82bef-254">ドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="82bef-254">The URL for the document.</span></span>
        
      - <span data-ttu-id="82bef-255">ドキュメントがあるサイト コレクションの URL。</span><span class="sxs-lookup"><span data-stu-id="82bef-255">The URL for the site collection where the document is located.</span></span>
        
      - <span data-ttu-id="82bef-256">ドキュメントが最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="82bef-256">The date that the document was last modified.</span></span>
        
      - <span data-ttu-id="82bef-257">ドキュメントの名前 (これは、結果のログの [件名] 列にあります)。</span><span class="sxs-lookup"><span data-stu-id="82bef-257">The name of the document (which is located in the Subject column in the result log).</span></span>
    
  - <span data-ttu-id="82bef-p135">**インデックス付けされない項目**Excel ファイルを検索結果に含まれる、部分的にインデックス付きの項目に関する情報が含まれています。検索結果のレポートを生成すると、部分的にインデックス付きの項目を含まない、このレポートは、ダウンロードされますが、空になります。</span><span class="sxs-lookup"><span data-stu-id="82bef-p135">**Unindexed Items** An Excel document that contains information about any partially indexed items that would be included in the search results. If you don't include partially indexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span> 
    
  - <span data-ttu-id="82bef-p136">**エラーと警告**ファイルのエクスポート中に発生したエラーと警告が含まれています。個々 のエラーまたは警告ごとに固有の情報のエラーの詳細の列を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p136">**Errors and Warnings** Contains errors and warnings for files encountered during export. See the Error Details column for information specific to each individual error or warning.</span></span> 
    
  - <span data-ttu-id="82bef-p137">**スキップした項目**SharePoint および OneDrive からビジネス サイトの検索結果をエクスポートする場合、エクスポートには通常スキップした項目のレポート (SkippedItems.csv) が含まれます。このレポートに示された項目は、通常、フォルダーやドキュメントなど、ダウンロードしないアイテムを設定します。設計ではこの種類のアイテムをエクスポートできません。スキップされたその他の項目の 'エラー '、' エラーの詳細' フィールドをスキップした項目のレポートに理由の項目がスキップされた、ダウンロードとその他の検索結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="82bef-p137">**Skipped Items** When you export search results from SharePoint and OneDrive for Business sites, the export will usually include a skipped items report (SkippedItems.csv). The items cited in this report are typically items that won't be downloaded, such as a folder or a document set. Not exporting this types of items is by design. For other items that were skipped, the 'Error Type' and 'Error Details' field in the skipped items report show the reason the item was skipped and wasn't download with the other search results.</span></span> 
    
  - <span data-ttu-id="82bef-266">**トレース ログ**エクスポート処理についての詳細なログ情報が含まれていて、エクスポート中に問題を明らかにできます。</span><span class="sxs-lookup"><span data-stu-id="82bef-266">**Trace Log** Contains detailed logging information about the export process and can help uncover issues during export.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="82bef-p138">だけで、実際の検索結果をエクスポートすることがなくこれらのドキュメントをエクスポートできます。[コンテンツの検索レポートをエクスポートする](export-a-content-search-report.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p138">You can just export these documents without having to export the actual search results. See [Export a Content Search report](export-a-content-search-report.md).</span></span> 
  
 ### <a name="exporting-partially-indexed-items"></a><span data-ttu-id="82bef-269">部分的にインデックス付きのアイテムをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="82bef-269">Exporting partially indexed items</span></span>
  
- <span data-ttu-id="82bef-p139">メールボックス アイテムを検索結果にすべてのメールボックス アイテムを取得するコンテンツの検索からエクスポートする場合 (のでキーワード検索クエリに含まれている場合)、部分的にインデックス付きのアイテムは、インデックスの項目を格納する PST ファイルにコピーされません。部分的にインデックス付きのアイテムを含むすべてのアイテムが通常の検索結果に自動的に含まれているためにです。つまり、部分的にインデックス付きの項目が含まれている、他のインデックス付きのアイテムを含む PST ファイル (または、個々 のメッセージとして)。</span><span class="sxs-lookup"><span data-stu-id="82bef-p139">If you're exporting mailbox items from a content search that returns all mailbox items in the search results (because no keywords where included in the search query), partially indexed items won't be copied to the PST file that contains the unindexed items. This is because all items, including any partially indexed items, are automatically included in the regular search results. This means that partially indexed items will be included in a PST file (or as individual messages) that contains the other, indexed items.</span></span>
    
    <span data-ttu-id="82bef-p140">さらに、インデックスを作成し、部分的にインデックス付けされたアイテムの両方をエクスポートする場合、またはすべての項目を返すコンテンツの検索からインデックス付けされたアイテムのみをエクスポートする場合は、同じ数のアイテムがダウンロードされます。これは、ような場合でも、予定の検索結果のコンテンツの検索 (セキュリティで検索の統計情報に表示されている&amp;コンプライアンス センター) は部分的にインデックス付きの項目の数の別の見積もりが含まれています。たとえば、(検索クエリにキーワードがない) のすべての項目を含む検索のために見積もりが 1,000 件が検出されたこととも部分的にインデックス付けされたアイテムは 200 個が検出されたことを示しているとします。この例では、1,000 の項目には、検索がすべての項目を返すために部分的にインデックス付きの項目が含まれます。つまり、によって返される検索と 1,200 アイテムではなく (ご想像のとおり)、1,000 の合計の項目があります。この検索の結果をエクスポートするを選んだ場合はエクスポートがインデックスを作成し、部分的に項目 (または単にインデックス付きの項目) のインデックスを作成し、1,000 のアイテムがダウンロードされます。もう一度、部分的にインデックス付きの項目は、空白の検索クエリを使用して、すべてのアイテムを取得するときに通常の (インデックス) の結果に含まれているためにです。この例で、唯一の部分的にインデックス付けされたアイテムをエクスポートする場合は 200 のインデックスを持たないアイテムのみがダウンロード。</span><span class="sxs-lookup"><span data-stu-id="82bef-p140">Additionally, if you export both the indexed and partially indexed items or if you export only the indexed items from a content search that returns all items, the same number of items will be downloaded. This happens even though the estimated search results for the content search (displayed in the search statistics in the Security &amp; Compliance Center) will still include a separate estimate for the number of partially indexed items. For example, let's say that the estimate for a search that includes all items (no keywords in the search query) shows that 1,000 items were found and that 200 partially indexed items were also found. In this case, the 1,000 items include the partially indexed items because the search returns all items. In other words, there are 1,000 total items returned by the search, and not 1,200 items (as you might expect). If you export the results of this search and choose to export indexed and partially indexed items (or just indexed items), then 1,000 items will be downloaded. Again, that's because partially indexed items are included with the regular (indexed) results when you use a blank search query to return all items. In this same example, if you choose to export only partially indexed items, then only the 200 unindexed items would be downloaded.</span></span>
    
    <span data-ttu-id="82bef-281">前の例 (インデックスを作成し、部分的にインデックス付きのアイテムをエクスポートするまたはインデックス付きのアイテムのみをエクスポートする場合) では、**エクスポートの概要**レポートをエクスポートした検索結果に含まれているリストが 1,000 件の見積項目および 1,000 のダウンロードにも注意してください。前述したように同じ理由の項目です。</span><span class="sxs-lookup"><span data-stu-id="82bef-281">Also note that in the previous example (when you export indexed and partially indexed items or you export only indexed items) , the **Export Summary** report included with the exported search results would list 1,000 items estimated items and 1,000 downloaded items for the same reasons as previously described.</span></span> 
    
- <span data-ttu-id="82bef-p141">コンテンツの特定の場所または組織内のすべてのコンテンツの場所の検索、検索から結果をエクスポートする場合は、部分的にからの項目のみ、検索条件に一致する項目が含まれているコンテンツの場所がエクスポートされます。つまり、メールボックス内またはサイト内検索結果が見つからない場合、いずれかの部分的にインデックスを作成するメールボックス内のアイテムまたはサイトは、エクスポートされません。この理由は、組織内の場所の多数の部分的にインデックス付きのアイテムをエクスポートする可能性がありますエクスポート エラーの可能性が高く、エクスポートし、検索結果のダウンロードにかかる時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="82bef-p141">If the search that you're exporting results from was a search of specific content locations or all content locations in your organization, only the partially items from content locations that contain items that match the search criteria will be exported. In other words, if no search results are found in a mailbox or site, then any partially indexed items in that mailbox or site won't be exported. The reason for this is that exporting partially indexed items from lots of locations in the organization might increase the likelihood of export errors and increase the time it takes to export and download the search results.</span></span>
    
    <span data-ttu-id="82bef-285">検索のすべてのコンテンツの場所から部分的にインデックス付きのアイテムをエクスポートするのには (任意のキーワードを削除して、検索クエリから) ですべての項目を返す検索を構成して検索結果をエクスポートすると、部分的にインデックス付きのアイテムのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="82bef-285">To export partially indexed items from all content locations for a search, configure the search to return all items (by removing any keywords from the search query) and then export only partially indexed items when you export the search results.</span></span>
    
    ![Thrid のエクスポート オプションを使用して、インデックスを持たないアイテムのみをエクスポートするのには](media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- <span data-ttu-id="82bef-p142">ビジネス サイトの SharePoint または OneDrive からの検索結果をエクスポートするとき、インデックスを持たないアイテムをエクスポートする機能は、エクスポート オプションを選択して検索対象となったサイトが検索条件に一致するインデックス付きの項目を含むかどうかによっても異なります。などのビジネス サイトの特定の SharePoint または OneDrive を検索する検索結果が見つからない場合は、し、それらのサイトから、インデックスを持たないアイテムがエクスポートされますないインデックスとインデックスの両方のアイテムをエクスポートするのには 2 つ目のエクスポート オプションを選択した場合。サイトからインデックス付けされたアイテムは、検索条件と一致して場合、そのサイトからのすべてのインデックスを持たないアイテムがエクスポートされますインデックスとインデックスの両方のアイテムをエクスポートするとき。次の図では、サイトに検索条件に一致するインデックス付きの項目が含まれているかどうかに基づいて、エクスポート オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="82bef-p142">When exporting search results from SharePoint or OneDrive for Business sites, the ability to export unindexed items also depends on the export option that you select and whether a site that was searched contains an indexed item that matches the search criteria. For example, if you search specific SharePoint or OneDrive for Business sites and no search results are found, then no unindexed items from those sites will be exported if you choose the second export option to export both indexed and unindexed items. If an indexed item from a site does match the search criteria, then all unindexed items from that site will be exported when exporting both indexed and unindexed items. The following illustration describes the export options based on whether or not a site contains an indexed item that matches the search criteria.</span></span>
    
    ![サイトに検索条件に一致するインデックス付きの項目が含まれているかどうかに基づいて、エクスポート オプションを選択します。](media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    
    <span data-ttu-id="82bef-p143">検索条件に一致するインデックス付き項目 a のみがエクスポートされます。部分的にインデックス付きのアイテムはエクスポートされませんでした。</span><span class="sxs-lookup"><span data-stu-id="82bef-p143">A - Only indexed items that matches the search criteria are exported. No partially indexed items are exported.</span></span>
    
    <span data-ttu-id="82bef-p144">B の場合は、サイトのインデックス付きのアイテムが検索条件に一致しないし、その同じサイトから部分的にインデックス付きのアイテムはエクスポートされません。サイトのインデックス付きのアイテムが検索結果に返される場合は、そのサイトから部分的にインデックス付きのアイテムがエクスポートされます。つまり、検索条件に一致する項目が含まれるサイトから部分的にインデックス付きのアイテムのみがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="82bef-p144">B - If no indexed items from a site match the search criteria, then partially indexed items from that same site aren't exported. If indexed items from a site are returned in the search results, then the partially indexed items from that site are exported. In other words, only the partially indexed items from sites that contain items that match the search criteria are exported.</span></span>
    
    <span data-ttu-id="82bef-297">C のサイトに検索条件に一致する項目が含まれているかどうかに関係なく、検索のすべてのサイトから部分的にインデックス付けされたすべてのアイテムがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="82bef-297">C - All partially indexed items from all sites in the search are exported, regardless of whether a site contains items that match the search criteria.</span></span>
    
    <span data-ttu-id="82bef-298">部分的にインデックス付きのアイテムをエクスポートする場合は、部分的にインデックス付けされたメールボックス アイテムは、[**としてエクスポートする Exchange のコンテンツ**を選択するオプションにかかわらず、別の PST ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="82bef-298">If you choose to export partially indexed items, partially indexed mailbox items are exported in a separate PST file regardless of the option that you choose under **Export Exchange content as**.</span></span>

- <span data-ttu-id="82bef-p145">部分的にインデックス付きのアイテムが検索で返された場合の結果 (部分的にインデックス付きのアイテムの他のプロパティには、検索条件が一致する) ため、部分的にインデックスは、通常の検索結果を使用してエクスポートし、します。では、(オプションを選択して、**認識できない形式があるものなど、すべてのアイテムが暗号化されているか他の理由によりインデックスが作成されなかった**エクスポート)、インデックス付きの項目と部分的にインデックス付けされたアイテムの両方をエクスポートする場合は、部分的にインデックス付きの項目をエクスポート通常の結果では、Results.csv のレポートに表示されます。それらはインデックスを持たない items.csv レポートに表示されません。</span><span class="sxs-lookup"><span data-stu-id="82bef-p145">If partially indexed items are returned in the search results (because other properties of an partially indexed items matched the search criteria), then those partially indexed are exported with the regular search results. So, if you choose to export both indexed items and partially indexed items (by selecting the **All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons** export option), the partially indexed items exported with the regular results will be listed in the Results.csv report. They will not be listed in the Unindexed items.csv report.</span></span>
    
 ### <a name="exporting-individual-messages-or-pst-files"></a><span data-ttu-id="82bef-302">個々 のメッセージまたは PST ファイルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="82bef-302">Exporting individual messages or PST files</span></span>
  
- <span data-ttu-id="82bef-p146">メッセージのファイルのパス名では、Windows の最大文字数の制限を超えている場合は、ファイルのパス名が切り捨てられます。マニフェストと ResultsLog の元のファイルのパス名を一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="82bef-p146">If the file path name of a message exceeds the maximum character limit for Windows, the file path name is truncated. But the original file path name will be listed in the Manifest and ResultsLog.</span></span>
    
- <span data-ttu-id="82bef-p147">説明したよう検索の結果がファイル ・ システム内のフォルダーにエクスポートを電子メールで送信します。フォルダーのパスの個々 のメッセージの複製をユーザーのメールボックス内のフォルダーのパスです。などの"ContosoCase101"をという名前の検索のユーザーの受信トレイにメッセージがあるフォルダーのパスに`~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox`。</span><span class="sxs-lookup"><span data-stu-id="82bef-p147">As previously explained, email search results are exported to a folder in the file system. The folder path for individual messages would replicate the folder path in the user's mailbox. For example, for a search named "ContosoCase101" messages in a user's inbox would be located in the folder path  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox`.</span></span> 
    
- <span data-ttu-id="82bef-p148">電子メール メッセージを 1 つのフォルダー内のすべてのメッセージが含まれている 1 つの PST ファイルをエクスポートする場合は、PST フォルダーの最上部に**削除済みアイテム**フォルダーと、[**検索フォルダー** ] フォルダーが含まれます。これらのフォルダーは空になります。</span><span class="sxs-lookup"><span data-stu-id="82bef-p148">If you choose to export email messages in one PST file containing all messages in a single folder, a **Deleted Items** folder and a **Search Folders** folder are included in the top level of the PST folder. These folders will be empty.</span></span> 
  
 ### <a name="decrypting-rms-encrypted-messages"></a><span data-ttu-id="82bef-310">RMS で暗号化されたメッセージを復号化</span><span class="sxs-lookup"><span data-stu-id="82bef-310">Decrypting RMS-encrypted messages</span></span>
  
- <span data-ttu-id="82bef-p149">説明したように、それらをエクスポートする場合は、RMS で暗号化されたメッセージを復号化がある個々 のメッセージと検索結果をエクスポートするのには。PST ファイルに検索結果をエクスポートする場合は、RMS で暗号化されたメッセージは暗号化されたままにします。</span><span class="sxs-lookup"><span data-stu-id="82bef-p149">As previously explained, to decrypt RMS-encrypted messages when you export them, you have to export the search results as individual messages. If you export search results to a PST file, RMS-encrypted messages will remain encrypted.</span></span>
    
- <span data-ttu-id="82bef-p150">RMS の復号化機能でコンテンツの検索は、検索結果をエクスポートする場合は、Office 365 メッセージの暗号化 (ホーム) とを暗号化されたメッセージを復号化しません。ただし、ホームで暗号化されたメッセージは、組織内のユーザーによって送信される、ユーザーの送信済みアイテム フォルダー内のメッセージのコピーは暗号化されていないしにエクスポートした後は表示されません。ただし、ホームで暗号化されたメッセージは、組織内のユーザーが受信した場合にも復号化、エクスポートして後。ホームの詳細については、 [Office 365 のメッセージの暗号化](https://go.microsoft.com/fwlink/p/?linkid=844966)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p150">The RMS decryption feature in Content Search doesn't decrypt messages encrypted with Office 365 Message Encryption (OME) when you export search results. However, if a message encrypted with OME is sent by a user in your organization, the copy of the message in the user's Sent folder isn't encrypted and will be viewable after it's exported. However, if messages encrypted with OME are received by users in your organization, they won't be decrypted after they're exported. For more information about OME, see [Office 365 Message Encryption](https://go.microsoft.com/fwlink/p/?linkid=844966).</span></span>
    
- <span data-ttu-id="82bef-p151">暗号化が解除されているメッセージは、 **ResultsLog**のレポートで識別されます。このレポートには、**デコードの状態**] という名前の列が含まれているし、 **Decoded**のこの列の値は、メッセージを識別しますが解除されました。</span><span class="sxs-lookup"><span data-stu-id="82bef-p151">Messages that are decrypted are identified in the **ResultsLog** report. This report contains a column named **Decode Status**, and a value of **Decoded** in this column identifies the messages the were decrypted.</span></span> 
    
- <span data-ttu-id="82bef-p152">現在、この復号化機能には、ビジネス サイトの SharePoint と OneDrive からの暗号化されたコンテンツが含まれていません。RMS で暗号化された電子メール メッセージだけはそれらをエクスポートすると、復号化します。</span><span class="sxs-lookup"><span data-stu-id="82bef-p152">Currently, this decryption capability doesn't include encrypted content from SharePoint and OneDrive for Business sites. Only RMS-encrypted email messages will be decrypted when you export them.</span></span>
    
- <span data-ttu-id="82bef-321">RMS で暗号化された電子メール メッセージ、添付ファイル (ドキュメント、別の電子メール メッセージなど) も暗号化されている場合は、最上位レベルの電子メール メッセージのみが復号化します。</span><span class="sxs-lookup"><span data-stu-id="82bef-321">If an RMS-encrypted email message has an attachment (such as a document or another email message) that's also encrypted, only the top-level email message will be decrypted.</span></span>
    
- <span data-ttu-id="82bef-p153">RMS で暗号化された電子メール メッセージをプレビューすることはできません。暗号化されたメッセージを表示するには、それをエクスポートするのにはあります。</span><span class="sxs-lookup"><span data-stu-id="82bef-p153">You can't preview an RMS-encrypted email message. To view an encrypted message, you have to export it.</span></span>
    
- <span data-ttu-id="82bef-p154">他のユーザーが RMS で暗号化されたメッセージを復号化を防止する場合は、(組み込みの電子証拠開示マネージャーの役割グループをコピーするには)、カスタムの役割グループを作成し、カスタムの役割グループから復号する RMS 管理の役割を削除する必要があります。カスタム役割グループのメンバーとしてメッセージを復号化したくない人を追加します。</span><span class="sxs-lookup"><span data-stu-id="82bef-p154">If you need to prevent someone from decrypting RMS-encrypted messages, you'll have to create a custom role group (by copying the built-in eDiscovery Manager role group) and then remove the RMS Decrypt management role from the custom role group. Then add the person who you don't want to decrypt messages as a member of the custom role group.</span></span>
  
 ### <a name="filenames-of-exported-items"></a><span data-ttu-id="82bef-326">エクスポートされたアイテムのファイル名</span><span class="sxs-lookup"><span data-stu-id="82bef-326">Filenames of exported items</span></span>
  
- <span data-ttu-id="82bef-p155">電子メール メッセージと、ローカル コンピューターにエクスポートするサイトのドキュメントの完全なパス名には、(オペレーティング システムによって課せられている) 260 文字制限があります。エクスポートされたアイテムの完全なパス名には、アイテムの元の場所とする検索結果をダウンロードする先のローカル コンピューター上のフォルダーの場所が含まれています。検索結果をダウンロードするように指定した場合など、 `C:\Users\Admin\Desktop\SearchResults` 、電子的証拠開示のエクスポート ・ ツール、ダウンロードした電子メール アイテムの完全なパス名になります`C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg`。</span><span class="sxs-lookup"><span data-stu-id="82bef-p155">There is a 260-character limit (imposed by the operating system) for the full path name for email messages and site documents exported to your local computer. The full path name for exported items includes the item's original location and the folder location on the local computer where the search results are downloaded to. For example, if you specify to download the search results to  `C:\Users\Admin\Desktop\SearchResults` in the eDiscovery Export tool, then the full pathname for a downloaded email item would be  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg`.</span></span>
    
    <span data-ttu-id="82bef-330">260 文字の制限を超えた場合、アイテムの完全なパス名は切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="82bef-330">If the 260-character limit is exceeded, the full path name for an item will be truncated.</span></span>
    
  - <span data-ttu-id="82bef-331">ファイル名を取得の制限の下に短縮される完全なパス名が 260 文字より長い場合は、切り捨てられたファイル名 (ファイル拡張子を除く) が 8 文字未満にできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-331">If the full path name is longer than 260 characters, the file name will be shortened to get under the limit; note that the truncated filename (excluding the file extension) won't be less than 8 characters.</span></span>
    
  - <span data-ttu-id="82bef-p156">完全なパス名が長すぎるファイル名を短縮した後、アイテムが親フォルダーに現在の場所から移動します。パス名が長すぎるかどうかは、プロセスが繰り返されます: ファイル名を短く必要は、もう一度親フォルダーに移動する場合とします。まで、完全なパス名が 260 文字の制限下には、このプロセスが繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="82bef-p156">If the full path name is still too long after shortening the file name, the item is moved from its current location to the parent folder. If the pathname is still too long, then the process is repeated: shorten the filename, and if necessary move again to the parent folder. This process is repeated until the full pathname is under the 260-character limit.</span></span>
    
  - <span data-ttu-id="82bef-335">バージョン番号をファイル名の末尾に追加されますが切り捨てられる完全なパス名が既に存在する場合たとえば、 `statusmessage(2).msg`。</span><span class="sxs-lookup"><span data-stu-id="82bef-335">If a truncated full path name already exists, a version number will be added to the end of the filename; for example,  `statusmessage(2).msg`.</span></span>
    
    <span data-ttu-id="82bef-336">この問題を軽減するためには、短いパス名の場所に検索結果のダウンロードを検討してください。検索結果をダウンロードするなどという名前のフォルダーに`C:\Results`という名前のフォルダーにダウンロードするよりもエクスポートした項目のパス名に文字数を追加すると`C:\Users\Admin\Desktop\Results`。</span><span class="sxs-lookup"><span data-stu-id="82bef-336">To help mitigate this issue, consider downloading search results to a location with a short path name; for example, downloading search results to a folder named  `C:\Results` would add fewer characters to the path names of exported items than downloading them to a folder named  `C:\Users\Admin\Desktop\Results`.</span></span>
    
- <span data-ttu-id="82bef-p157">サイトのドキュメントをエクスポートするときにもドキュメントの元のファイル名を変更することが可能です。これは、保留リストに配置されているは、ビジネス サイトの SharePoint または OneDrive から削除されたドキュメントの具体的には発生します。保留中のサイトに配置されているドキュメントが削除されると、削除したドキュメントが自動的に移動ライブラリの保存を保持する (保留中のサイトが置かれたときに作成された) サイトです。保持保持ライブラリを削除したドキュメントを移動すると、ランダムに生成し、一意の ID は、ドキュメントの元のファイル名に追加されます。たとえば、ドキュメントのファイル名は`FY2017Budget.xlsx`後でそのドキュメントが削除され、ライブラリに移動、保存を保持のようなものには、ライブラリに移動、保管を保持するドキュメントのファイル名が変更されると`FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`。保持保持ライブラリ内のドキュメントのコンテンツの検索クエリに一致して、その検索結果をエクスポートする、エクスポートされたファイルが変更されたファイル名です。この例では、エクスポートされた文書のファイル名になります`FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`。</span><span class="sxs-lookup"><span data-stu-id="82bef-p157">When you export site documents, it's also possible that the original file name of a document will be modified. This happens specifically for documents that have been deleted from a SharePoint or OneDrive for Business site that's been placed on hold. After a document that's located on a site that's on hold is deleted, the deleted document is automatically moved to the Preservation Hold library for the site (which was created when the site was placed on hold). When the deleted document is moved to the Preservation Hold library, a randomly-generated and unique ID is appended to the original filename of the document. For example, if the filename for a document is  `FY2017Budget.xlsx` and that document is later deleted and moved to the Preservation Hold library, the filename of the document that is moved to the Preservation Hold library is modified to something like  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`. If a document in the Preservation Hold library matches the query of a Content Search and you export the results of that search, the exported file will have the modified filename; in this example, the filename of the exported document would be  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`.</span></span>
    
    <span data-ttu-id="82bef-p158">さらにと保留中のサイト上にあるドキュメントの変更 (サイトのドキュメント ライブラリのバージョン管理が有効になっている)、、ファイルのコピーがで自動的に作成ライブラリの保存を保持します。この例では、ランダムに生成し、一意の ID がライブラリにコピー、保存を保持するドキュメントのファイル名に追加されます。</span><span class="sxs-lookup"><span data-stu-id="82bef-p158">Additionally, when a document located on a site that's on hold is modified (and versioning for the document library in the site has been enabled), a copy of the file is automatically created in the Preservation Hold library. In this case, a randomly-generated and unique ID is also appended to the filename of the document that's copied to the Preservation Hold library.</span></span>
    
    <span data-ttu-id="82bef-p159">移動やコピーの保持保持ライブラリへのドキュメントのファイル名が競合するファイル名をしないようにするのには理由の理由です。サイトとライブラリの保存を保持保留リストに配置することに関する詳細については、 [SharePoint サーバーの 2016年の埋め込みの概要を保持](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bef-p159">The reason why filenames of documents that are moved or copied to the Preservation Hold library is to prevent conflicting filenames. For more information about placing a hold on sites and the Preservation Hold library, see [Overview of in-place hold in SharePoint Server 2016](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95).</span></span>
    
 ### <a name="miscellaneous"></a><span data-ttu-id="82bef-347">その他</span><span class="sxs-lookup"><span data-stu-id="82bef-347">Miscellaneous</span></span>
  
- <span data-ttu-id="82bef-p160">すべての検索結果とコンテンツの検索と同じ名前を持つフォルダーに含まれて、レポートをエクスポートします。エクスポートされた電子メール メッセージは、 **Exchange**をという名前のフォルダーにあります。**SharePoint**をという名前のフォルダー内にドキュメントがあります。</span><span class="sxs-lookup"><span data-stu-id="82bef-p160">All search results and the export reports are included in a folder that has the same name as the Content Search. The email messages that were exported are located in a folder named **Exchange**. Documents are located in a folder named **SharePoint**.</span></span> 
    
- <span data-ttu-id="82bef-p161">ローカル コンピューターにドキュメントをエクスポートする際は、ビジネス サイトの SharePoint と OneDrive のドキュメントのファイル システム メタデータが維持されます。ドキュメントのプロパティは、次のように作成されたと最後の日付を変更、ドキュメントをエクスポートする場合は変更されません。</span><span class="sxs-lookup"><span data-stu-id="82bef-p161">The file system metadata for documents on SharePoint and OneDrive for Business sites is maintained when documents are exported to your local computer. That means document properties, such as created and last modified dates, aren't changed when documents are exported.</span></span>