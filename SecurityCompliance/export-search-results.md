---
title: Office 365 Security & コンプライアンスセンターからコンテンツ検索の結果をエクスポートする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: 'Office 365 Security & コンプライアンスセンターのコンテンツ検索からローカルコンピューターに検索結果をエクスポートします。電子メールの結果は PST ファイルとしてエクスポートされます。SharePoint と OneDrive for business サイトのコンテンツは、ネイティブの Office ドキュメントとしてエクスポートされます。 '
ms.openlocfilehash: 5ec1456c7d1a787a1ede70c15b109e7f0358f60a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219947"
---
# <a name="export-content-search-results-from-the-office-365-security--compliance-center"></a><span data-ttu-id="46934-105">Office 365 Security & コンプライアンスセンターからコンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="46934-105">Export Content Search results from the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="46934-p102">コンテンツ検索が正常に実行されたら、検索結果をローカルコンピューターにエクスポートできます。電子メールの結果をエクスポートすると、その結果は PST ファイルとしてコンピューターにダウンロードされます。SharePoint と OneDrive for business サイトからコンテンツをエクスポートすると、ネイティブな Office ドキュメントのコピーがエクスポートされます。エクスポートされた検索結果には、追加のドキュメントとレポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="46934-p102">After a Content Search is successfully run, you can export the search results to a local computer. When you export email results, they're downloaded to your computer as PST files. When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents are exported. There are additional documents and reports that are included with the exported search results.</span></span>
  
<span data-ttu-id="46934-p103">さらに、コンテンツ検索の結果に含まれる rm で暗号化された電子メールメッセージは、個別のメッセージとしてエクスポートするときに復号化されます。この暗号化解除機能は、電子情報開示マネージャーの役割グループのメンバーに対して既定で有効になっています。これは、RMS の解読管理役割がこの役割グループに割り当てられるためです。検索結果をエクスポートするときの RMS 復号化の詳細については、「 [More information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p103">Additionally, any RMS-encrypted email messages that are included in the results of a Content Search will be decrypted when you export them (as individual messages). This decryption capability is enabled by default for members of the eDiscovery Manager role group. This is because the RMS Decrypt management role is assigned to this role group. See the [More information](#more-information) section for details about RMS decryption when you export search results.</span></span> 
  
<span data-ttu-id="46934-114">コンテンツ検索の結果をエクスポートするには、結果を準備してからローカルコンピューターにダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="46934-114">Exporting the results of a Content Search involves preparing the results, and then downloading them to a local computer.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="46934-115">始める前に</span><span class="sxs-lookup"><span data-stu-id="46934-115">Before you begin</span></span>

- <span data-ttu-id="46934-p104">検索結果をエクスポートするには、Office 365 セキュリティ&amp;コンプライアンスセンターで、export 管理役割が割り当てられている必要があります。この役割は、組み込みの電子情報開示マネージャーの役割グループに割り当てられます。既定では、組織の管理役割グループに割り当てられません。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p104">To export search results, you have to be assigned the Export management role in the Office 365 Security &amp; Compliance Center. This role is assigned to the built-in eDiscovery Manager role group. It isn't assigned by default to the Organization Management role group. For more information, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="46934-120">検索結果をエクスポートする際に使用するコンピューターは、次のシステム要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="46934-120">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="46934-121">32 ビットおよび 64 ビット バージョンの Windows 7 およびそれ以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="46934-121">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="46934-122">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="46934-122">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="46934-123">サポートされているブラウザー:</span><span class="sxs-lookup"><span data-stu-id="46934-123">A supported browser:</span></span>
    
     - <span data-ttu-id="46934-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="46934-124">Microsoft Edge</span></span>
    
        <span data-ttu-id="46934-125">または</span><span class="sxs-lookup"><span data-stu-id="46934-125">OR</span></span>
    
     - <span data-ttu-id="46934-126">Microsoft Internet Explorer 10 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="46934-126">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="46934-p105">**注:** Microsoft は、ClickOnce アプリケーションのサードパーティの拡張機能またはアドオンを製造していません。サポートされていないブラウザーを使用して、サードパーティの内線番号またはアドオンを使用して検索結果をエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="46934-p105">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications. Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 
    
- <span data-ttu-id="46934-p106">検索結果 (手順2で説明) をダウンロードする場合は、検索結果のエクスポートに使用するコンピューターで Windows レジストリ設定を構成することで、ダウンロードの速度を向上させることができます。詳細については、「 [Office の電子情報開示検索結果をエクスポートするときにダウンロード速度を上げる 365](increase-download-speeds-when-exporting-ediscovery-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p106">When you download search results (described in Step 2), you can increase the download speed by configuring a Windows Registry setting on the computer you use to export the search results. For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
    
- <span data-ttu-id="46934-p107">検索結果をエクスポートすると、データがローカルコンピューターにダウンロードされる前に、microsoft クラウド内の一意の microsoft Azure ストレージの場所に一時的に格納されます。組織が Azure のエンドポイントに接続できることを確認し\*\* \*ます。 blob.core.windows.net\*\* (ワイルドカードは、エクスポートの一意識別子を表します)。検索結果データは、作成後2週間後に Azure ストレージの場所から削除されます。</span><span class="sxs-lookup"><span data-stu-id="46934-p107">When you export search results, the data is temporarily stored in a unique Microsoft Azure storage location in the Microsoft cloud before it's downloaded to your local computer. Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export). The search results data is deleted from the Azure storage location two weeks after it's created.</span></span> 
    
- <span data-ttu-id="46934-p108">組織がプロキシサーバーを使用してインターネットと通信する場合は、検索結果のエクスポートに使用するコンピューターでプロキシサーバーの設定を定義する必要があります (エクスポートツールをプロキシサーバーで認証できるようにするため)。これを行うには、使用している Windows のバージョンと一致する場所にある*machine.config*ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="46934-p108">If your organization uses a proxy server to communicate with the Internet, you need to define the proxy server settings on the computer that you use to export the search results (so the export tool can be authenticated by your proxy server). To do this, open the  *machine.config*  file in the location that matches your version of Windows.</span></span> 
    
  - <span data-ttu-id="46934-136">**32ビット** - `%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`</span><span class="sxs-lookup"><span data-stu-id="46934-136">**32-bit** - `%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`</span></span>
    
  - <span data-ttu-id="46934-137">**64ビット** - `%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`</span><span class="sxs-lookup"><span data-stu-id="46934-137">**64-bit** - `%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`</span></span>
    
    <span data-ttu-id="46934-p109">次の行を、 `<configuration>`および`</configuration>`タグの間の*machine.config*ファイルに追加します。を`Port`使用して`ProxyServer` 、組織の正しい値をに置き換えてください。たとえば、 `proxy01.contoso.com:80`のようになります。</span><span class="sxs-lookup"><span data-stu-id="46934-p109">Add the following lines to the  *machine.config*  file somewhere between the  `<configuration>` and  `</configuration>` tags. Be sure to replace  `ProxyServer` and  `Port` with the correct values for your organization; for example,  `proxy01.contoso.com:80` .</span></span> 
    
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
    
## <a name="step-1-prepare-search-results-for-export"></a><span data-ttu-id="46934-140">手順 1: エクスポートする検索結果を準備する</span><span class="sxs-lookup"><span data-stu-id="46934-140">Step 1: Prepare search results for export</span></span>

<span data-ttu-id="46934-p110">最初の手順として、エクスポート用の検索結果を準備します。結果を準備すると、Microsoft クラウド内の Azure ストレージの場所にアップロードされます。メールボックスとサイトのコンテンツは、最大で1時間あたり 2 GB にアップロードされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p110">The first step is to prepare the search results for exporting. When you prepare results, they are uploaded to an Azure storage location in the Microsoft cloud. Note that content from mailboxes and sites is uploaded at a maximum rate of 2 GB per hour.</span></span>
  
1. <span data-ttu-id="46934-144">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="46934-144">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="46934-145">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="46934-145">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="46934-146">セキュリティ/コンプライアンス センターの左側のウィンドウで、**[検索と調査]** \> **[コンテンツ検索]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="46934-146">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**.</span></span>
    
4. <span data-ttu-id="46934-147">[**コンテンツ検索**] ページで、検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="46934-147">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="46934-148">詳細ウィンドウの **[結果をコンピューターにエクスポートする]** で、**[エクスポートの開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46934-148">In the details pane, under **Export results to a computer**, click **Start export**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="46934-p111">検索の結果が 7 日よりも前の場合は、検索結果を更新するように求められます。この場合は、エクスポートをキャンセルして、選んだ検索の詳細ウィンドウの **[検索結果の更新]** をクリックして、結果が更新された後で、エクスポートをもう一度開始します。 </span><span class="sxs-lookup"><span data-stu-id="46934-p111">If the results for a search are older than 7 days, you are prompted to update the search results. If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="46934-151">[**検索結果のエクスポート**] ページの [**出力オプション**] で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="46934-151">On the **Export the search results** page, under **Output options**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="46934-152">すべてのアイテム (認識できない形式のアイテムを除く)、暗号化されている、またはその他の理由でインデックスが作成されていないもの</span><span class="sxs-lookup"><span data-stu-id="46934-152">All items, excluding ones that have unrecognized format, are encrypted, or weren't indexed for other reasons</span></span>
    
    - <span data-ttu-id="46934-153">他の理由により、認識されない形式のアイテム、暗号化されているアイテム、またはインデックス付けされていないアイテムを含むすべてのアイテム</span><span class="sxs-lookup"><span data-stu-id="46934-153">All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons</span></span>
    
    - <span data-ttu-id="46934-154">他の理由により、認識されていない形式、またはインデックス付けされていないアイテムのみ</span><span class="sxs-lookup"><span data-stu-id="46934-154">Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons</span></span>
    
    <span data-ttu-id="46934-p112">部分的にインデックスが作成されたアイテムがエクスポートされる方法の詳細については、「 [More information](#more-information) 」セクションを参照してください。部分的にインデックスが作成されたアイテムの詳細については、「[コンテンツ検索でのインデックスのあるアイテムの一部](partially-indexed-items-in-content-search.md)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="46934-p112">See the [More information](#more-information) section for a description about how partially indexed items are exported. For more information about partially indexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="46934-157">[ **Exchange コンテンツのエクスポート**] で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="46934-157">Under **Export Exchange content as**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="46934-p113">**メールボックスごとに1つの pst ファイル**-検索結果が含まれるユーザーメールボックスごとに1つの pst ファイルをエクスポートします。ユーザーのアーカイブメールボックスからの結果はすべて、同じ PST ファイルに含まれています。このオプションを選択すると、移動元メールボックスからメールボックスフォルダー構造が再現されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p113">**One PST file for each mailbox** - Exports one PST file for each user mailbox that contains search results. Any results from the user's archive mailbox are included in the same PST file. Note that this option reproduces the mailbox folder structure from the source mailbox.</span></span> 
    
    - <span data-ttu-id="46934-p114">**すべてのメッセージを含む1つの pst ファイル**-検索に含ま\*\* れるすべてのソースメールボックスからの検索結果を含む1つの pst ファイル (名前付き) をエクスポートします。このオプションでは、各メッセージのメールボックスフォルダーの構造が再現されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p114">**One PST file containing all messages** - Exports a single PST file (named  *Exchange.pst*  ) that contains the search results from all source mailboxes included in the search. Note that this option reproduces the mailbox folder structure for each message.</span></span> 
    
    - <span data-ttu-id="46934-p115">**単一のフォルダー内のすべてのメッセージを含む1つの pst ファイル**-すべてのメッセージが1つの最上位フォルダーに格納されている1つの pst ファイルに検索結果をエクスポートします。このオプションを使用すると、各アイテムの元のメールボックスフォルダー構造を移動しなくても、レビューアーはアイテムを時系列順 (送信日で並べ替え) で確認できます。</span><span class="sxs-lookup"><span data-stu-id="46934-p115">**One PST file containing all messages in a single folder** - Exports search results to a single PST file where all messages are located in a single, top-level folder. This option lets reviewers review items in chronological order (items are sorted by sent date) without having to navigate the original mailbox folder structure for each item.</span></span> 
    
    - <span data-ttu-id="46934-p116">**個々のメッセージ**-.msg 形式を使用して、個々の電子メールメッセージとして検索結果をエクスポートします。このオプションを選択すると、電子メール検索の結果はファイルシステムのフォルダーにエクスポートされます。個々のメッセージのフォルダーパスは、その結果を PST ファイルにエクスポートした場合に使用したものと同じです。</span><span class="sxs-lookup"><span data-stu-id="46934-p116">**Individual messages** - Exports search results as individual email messages, using the .msg format. If you select this option, email search results are exported to a folder in the file system. The folder path for individual messages is the same as the one used if you exported the results to PST files.</span></span> 
    
      > [!IMPORTANT]
      > <span data-ttu-id="46934-p117">RMS で暗号化されたメッセージをエクスポートするときに暗号化を解除するには、電子メール検索結果を個々のメッセージとしてエクスポートする必要があります。検索結果を PST ファイルとしてエクスポートする場合、暗号化されたメッセージは暗号化されたままになります。</span><span class="sxs-lookup"><span data-stu-id="46934-p117">To decrypt RMS-encrypted messages when they're exported, you must export email search results as individual messages. Encrypted messages will remain encrypted if you export the search results as a PST file.</span></span> 
  
8. <span data-ttu-id="46934-p118">重複するメッセージを除外するには、[重複**除外を有効**にする] チェックボックスをオンにします。このオプションは、検索のコンテンツソースに Exchange メールボックスまたはパブリックフォルダーが含まれている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="46934-p118">Click the **Enable de-duplication** checkbox to exclude duplicate messages. This option appears only if the content sources of the search includes Exchange mailboxes or public folders.</span></span> 
    
    <span data-ttu-id="46934-p119">このオプションを選択すると、同じメッセージのコピーが検索されたメールボックスに複数存在する場合でも、メッセージのコピーが1つだけエクスポートされます。[結果のエクスポート] レポート (結果 .csv) には、重複するメッセージのコピーごとに1つの行が含まれているので、重複するメッセージのコピーを含むメールボックス (またはパブリックフォルダー) を識別できます。重複除外と重複するアイテムの識別方法の詳細については、「[電子情報開示検索結果の重複除外](de-duplication-in-ediscovery-search-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p119">If you select this option, only one copy of a message will be exported even if multiple copies of the same message are found in the mailboxes that were searched. The export results report (Results.csv) will contain a row for every copy of a duplicate message so that you can identify the mailboxes (or public folders) that contain a copy of the duplicate message. For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>
    
9. <span data-ttu-id="46934-p120">[ **sharepoint ドキュメントにバージョンを含める**] チェックボックスをオンにして、sharepoint ドキュメントのすべてのバージョンをエクスポートします。このオプションは、検索のコンテンツソースに SharePoint または OneDrive for business サイトが含まれている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="46934-p120">Click the **Include versions for SharePoint documents** checkbox to export all versions of SharePoint documents. This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span> 
    
10. <span data-ttu-id="46934-p121">[**圧縮 (zip 形式) フォルダー内のファイルをエクスポート**する] チェックボックスをオンにして、検索結果を圧縮フォルダーにエクスポートします。このオプションは、Exchange アイテムを個別のメッセージとしてエクスポートすることを選択した場合、検索結果に SharePoint または OneDrive ドキュメントが含まれる場合にのみ使用できます。このオプションは、アイテムをエクスポートするときに、Windows ファイルパス名の260文字制限を回避するために主に使用されます。「[詳細情報](#more-information)」セクションの「エクスポートされたアイテムのファイル名」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p121">Click the **Export files in a compressed (zipped) folder** checkbox to export search results to compressed folders. This option is available only when you choose to export Exchange items as individual messages and when the search results include SharePoint or OneDrive documents. This option is primarily used to work around the 260 character limit in Windows file path names when items are exported. See the "Filenames of exported items" in the [More information](#more-information) section.</span></span> 
    
11. <span data-ttu-id="46934-181">**[エクスポートの開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46934-181">Click **Start export**.</span></span>
    
    <span data-ttu-id="46934-p122">検索結果はダウンロードのために準備されています。つまり、Microsoft クラウド内の Azure ストレージの場所にアップロードされています。検索結果がダウンロードできる状態になると、[**結果をコンピューターにエクスポートする**] の下に [エクスポートされた**結果のダウンロード**] リンクが [詳細] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="46934-p122">The search results are prepared for downloading, which means they're being uploaded to the Azure storage location in the Microsoft cloud. When the search results are ready for download, the **Download exported results** link is displayed under **Export results to a computer** in the details pane.</span></span> 
  
## <a name="step-2-download-the-search-results"></a><span data-ttu-id="46934-184">手順 2:検索結果をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="46934-184">Step 2: Download the search results</span></span>

<span data-ttu-id="46934-185">次の手順では、Azure のストレージの場所からローカルコンピューターに検索結果をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="46934-185">The next step is to download the search results from the Azure storage location to your local computer.</span></span>
  
<span data-ttu-id="46934-p123">前述のように、検索結果のエクスポートに使用するコンピューターで Windows レジストリ設定を構成することで、ダウンロード速度を向上させることができます。詳細については、「 [Office の電子情報開示検索結果をエクスポートするときにダウンロード速度を上げる 365](increase-download-speeds-when-exporting-ediscovery-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p123">As previously explained, you can increase the download speed by configuring a Windows Registry setting on the computer you use to export the search results. For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
  
1. <span data-ttu-id="46934-188">エクスポートを開始した検索の詳細ウィンドウの **[結果をコンピューターにエクスポートする]** で、**[エクスポートした結果をダウンロードする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46934-188">In the details pane for the search that you started the export for, under **Export results to a computer**, click **Download exported results**.</span></span>
    
    <span data-ttu-id="46934-189">[**エクスポート**した結果のダウンロード] ウィンドウが表示され、コンピューターにダウンロードされる検索結果に関する次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="46934-189">The **Download exported results** window is displayed and contains the following information about the search results that will be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="46934-190">ダウンロードされるアイテムの数。</span><span class="sxs-lookup"><span data-stu-id="46934-190">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="46934-191">ダウンロードされるアイテムの推定合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="46934-191">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="46934-p124">エクスポートされる内容にインデックスが付いているかどうか。インデックスのないアイテムは、形式が認識されているアイテム、暗号化されているアイテム、他の理由でインデックスが作成されなかったアイテムのいずれかです。詳細については、「[Unindexed items in Content Search](partially-indexed-items-in-content-search.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="46934-p124">Whether indexed or unindexed will be exported. Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons. For more information, see [Unindexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
    - <span data-ttu-id="46934-195">SharePoint ドキュメントのバージョンがダウンロードされるかどうか。</span><span class="sxs-lookup"><span data-stu-id="46934-195">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="46934-p125">エクスポートの準備プロセスの状態。データの準備が完了していない場合でも、検索結果のダウンロードを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="46934-p125">The status of the export preparation process. You can start downloading search results even if the preparation of the data isn't complete.</span></span>
    
2. <span data-ttu-id="46934-p126">**[エクスポート キー]** で、**[クリップボードにコピー]** をクリックします。このキーは手順 5 で検索結果をダウンロードする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="46934-p126">Under **Export key**, click **Copy to clipboard**. You will use this key in step 5 to download the search results.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="46934-200">電子情報開示エクスポート ツールをインストールして開始し、このキーを使用して検索結果をダウンロードすることはだれにでもできるため、このキーは、パスワードやその他のセキュリティ関連の情報を保護する場合と同様の予防策を講じてください。 </span><span class="sxs-lookup"><span data-stu-id="46934-200">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search results, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="46934-201">**[結果のダウンロード]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46934-201">Click **Download results**.</span></span>
    
4. <span data-ttu-id="46934-202">**MicrosoftOffice 365 電子情報開示エクスポートツール**をインストールするように求めるメッセージが表示されたら、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46934-202">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="46934-203">**電子情報開示エクスポート ツール**で、手順 2 でコピーしたエクスポート キーを適切なボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="46934-203">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="46934-204">**[参照]** をクリックして、検索結果のファイルをダウンロードする場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="46934-204">Click **Browse** to specify the location where you want to download the search result files.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="46934-205">ディスクアクティビティが大量に (読み取りおよび書き込み) あるため、検索結果をローカルディスクドライブにダウンロードする必要があります。マップされたネットワークドライブまたは他のネットワークの場所にはダウンロードしないでください。</span><span class="sxs-lookup"><span data-stu-id="46934-205">Due to the high amount of disk activity (reads and writes), you should download search results to a local disk drive; don't download them to a mapped network drive or other network location.</span></span> 
  
1. <span data-ttu-id="46934-206">**[開始]** をクリックして、検索結果をコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="46934-206">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="46934-p127">**電子情報開示エクスポートツール**は、エクスポート処理に関する状態情報を表示します。これには、ダウンロードする残りのアイテムの数 (およびサイズ) の推定値が含まれます。エクスポートプロセスが完了すると、ダウンロードされた場所にあるファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="46934-p127">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    

  
## <a name="more-information"></a><span data-ttu-id="46934-209">詳細情報</span><span class="sxs-lookup"><span data-stu-id="46934-209">More information</span></span>

<span data-ttu-id="46934-210">検索結果のエクスポートの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46934-210">Here's more information about exporting search results.</span></span>
  
[<span data-ttu-id="46934-211">エクスポートの制限</span><span class="sxs-lookup"><span data-stu-id="46934-211">Export limits</span></span>](#export-limits)
  
[<span data-ttu-id="46934-212">レポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="46934-212">Export reports</span></span>](#export-reports)
  
[<span data-ttu-id="46934-213">部分的にインデックスが作成されたアイテムをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="46934-213">Exporting partially indexed items</span></span>](#exporting-partially-indexed-items)

[<span data-ttu-id="46934-214">個々のメッセージまたは PST ファイルのエクスポート</span><span class="sxs-lookup"><span data-stu-id="46934-214">Exporting individual messages or PST files</span></span>](#exporting-individual-messages-or-pst-files)
  
[<span data-ttu-id="46934-215">RMS で暗号化されたメッセージの復号化</span><span class="sxs-lookup"><span data-stu-id="46934-215">Decrypting RMS-encrypted messages</span></span>](#decrypting-rms-encrypted-messages)

[<span data-ttu-id="46934-216">エクスポートされたアイテムのファイル名</span><span class="sxs-lookup"><span data-stu-id="46934-216">Filenames of exported items</span></span>](#filenames-of-exported-items)  
  
[<span data-ttu-id="46934-217">その他</span><span class="sxs-lookup"><span data-stu-id="46934-217">Miscellaneous</span></span>](#miscellaneous)
  
 ### <a name="export-limits"></a><span data-ttu-id="46934-218">エクスポートの制限</span><span class="sxs-lookup"><span data-stu-id="46934-218">Export limits</span></span>
  
- <span data-ttu-id="46934-219">セキュリティ&amp;コンプライアンスセンターからの検索結果のエクスポートには、次のような制限があります。</span><span class="sxs-lookup"><span data-stu-id="46934-219">Exporting search results from the Security &amp; Compliance Center has the following limits:</span></span>
    
  - <span data-ttu-id="46934-p128">1つのコンテンツ検索から最大 2 TB のデータをエクスポートできます。検索結果が 2 TB より大きい場合は、日付の範囲やその他の種類のフィルターを使用して、検索結果の合計サイズを小さくすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p128">You can export a maximum of 2 TB of data from a single Content Search. If the search results are larger than 2 TB, consider using date ranges or other types of filters to decrease the total size of the search results.</span></span>
    
  - <span data-ttu-id="46934-222">組織は1日に最大 2 TB のデータをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="46934-222">Your organization can export a maximum of 2 TB of data during a single day.</span></span>
    
  - <span data-ttu-id="46934-223">組織内で最大 10 のエクスポートを同時に実行することができます。</span><span class="sxs-lookup"><span data-stu-id="46934-223">You can have a maximum of 10 exports running at the same time within your organization.</span></span>
    
  - <span data-ttu-id="46934-224">1人のユーザーは、一度に最大で3つのエクスポートを実行できます。</span><span class="sxs-lookup"><span data-stu-id="46934-224">A single user can run a maximum of three exports at the same time.</span></span>

  > [!NOTE]
  > <span data-ttu-id="46934-225">コンテンツ検索からのレポートのみをエクスポートすると、同時に実行しているエクスポートの数と、1人のユーザーが実行できるエクスポートの数についてもカウントされます。</span><span class="sxs-lookup"><span data-stu-id="46934-225">Exporting only the reports from a Content Search also counts against the number of exports running at the same time and the number of exports that a single user can run.</span></span>
    
- <span data-ttu-id="46934-226">前述したように、メールボックスとサイトの検索結果は、最大速度が1時間あたり 2 GB の Azure ストレージの場所にアップロードされます (「[手順 1: エクスポートの検索結果を準備](#step-1-prepare-search-results-for-export)する」を参照)。</span><span class="sxs-lookup"><span data-stu-id="46934-226">As previously stated, search results from mailboxes and sites are uploaded to the Azure storage location (as described in [Step 1: Prepare search results for export](#step-1-prepare-search-results-for-export)) at a maximum rate of 2 GB per hour.</span></span>
    
- <span data-ttu-id="46934-p129">エクスポート可能な PST ファイルの最大サイズは、既定では 10 GB です。つまり、ユーザーのメールボックスからの検索結果が 10 GB より大きい場合、メールボックスの検索結果は2つ (またはそれ以上) の個別の PST ファイルにエクスポートされます。また、すべての検索結果を1つの pst ファイルにエクスポートする場合、検索結果の合計サイズが 10 GB より大きい場合は、pst ファイルが追加の pst ファイルに組み込まれます。この既定のサイズを変更する場合は、検索結果のエクスポートに使用するコンピューターで Windows レジストリを編集できます。[電子情報開示検索結果をエクスポートする場合は、「PST ファイルのサイズを変更する](change-the-size-of-pst-files-when-exporting-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p129">The maximum size of a PST file that can be exported is 10 GB by default. That means if the search results from a user's mailbox are larger than 10 GB, the search results for the mailbox will be exported in two (or more) separate PST files. Additionally, if you choose to export all search results in a single PST file, the PST file will be spilt into additional PST files if the total size of the search results is larger than 10 GB. If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results. See [Change the size of PST files when exporting eDiscovery search results](change-the-size-of-pst-files-when-exporting-results.md).</span></span>
    
    <span data-ttu-id="46934-p130">また、特定のメールボックスからの検索結果は、1つのメールボックスのコンテンツが 10 GB を超えていない限り、複数の PST ファイルに分割されることはありません。1つのフォルダーにすべてのメッセージが含まれていて、検索結果が 10 GB より大きい場合、検索結果を1つの pst ファイルにエクスポートすることを選択すると、アイテムは時系列順に整理されたままとなり、送信された d に基づいて追加の PST ファイルが作成されます。ate.</span><span class="sxs-lookup"><span data-stu-id="46934-p130">Additionally, the search results from a specific mailbox won't be divided among multiple PST files unless the content from a single mailbox is more than 10 GB. If you chose to export the search results in one PST file for that contains all messages in a single folder and the search results are larger than 10 GB, the items are still organized in chronological order, so they will be spilt into additional PST files based on the sent date.</span></span>
     
 ### <a name="export-reports"></a><span data-ttu-id="46934-234">レポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="46934-234">Export reports</span></span>
  
- <span data-ttu-id="46934-235">検索結果をエクスポートすると、検索結果に加えて次のレポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="46934-235">When you export search results, the following reports are included in addition to the search results.</span></span>
    
  - <span data-ttu-id="46934-p131">**エクスポートの概要**エクスポートの概要を含む Excel ドキュメント。これには、検索されたコンテンツソースの数、検索結果の推定サイズとダウンロードサイズ、およびエクスポートされたアイテム数の予想およびダウンロード数などの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="46934-p131">**Export Summary** An Excel document that contains a summary of the export. This includes information such as the number of content sources that were searched, the estimated and downloaded sizes of the search results, and the estimated and downloaded number of items that were exported.</span></span> 
    
  - <span data-ttu-id="46934-238">**マニフェスト**検索結果に含まれる各アイテムに関する情報を含むマニフェストファイル (XML 形式)。</span><span class="sxs-lookup"><span data-stu-id="46934-238">**Manifest** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
  - <span data-ttu-id="46934-p132">**結果**検索結果としてダウンロードされる各アイテムに関する情報を含む Excel ドキュメント。メールの場合、結果ログには、各メッセージに関する次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="46934-p132">**Results** An Excel document that contains information about each item that is download as a search result. For email, the result log contains information about each message, including:</span></span> 
    
      - <span data-ttu-id="46934-241">移行元のメールボックス内のメッセージの場所 (メッセージがプライマリ メールボックスとアーカイブ メールボックスのどちらであるかを含みます)。</span><span class="sxs-lookup"><span data-stu-id="46934-241">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
        
      - <span data-ttu-id="46934-242">メッセージが送信または受信された日付。</span><span class="sxs-lookup"><span data-stu-id="46934-242">The date the message was sent or received.</span></span>
        
      - <span data-ttu-id="46934-243">メッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="46934-243">The Subject line from the message.</span></span>
        
      - <span data-ttu-id="46934-244">メッセージの送信者と受信者。</span><span class="sxs-lookup"><span data-stu-id="46934-244">The sender and recipients of the message.</span></span>
        
      - <span data-ttu-id="46934-p133">検索結果をエクスポートするときに重複除去オプションを有効にした場合、メッセージが重複メッセージであるかどうか。重複するメッセージは、重複しているとしてメッセージを識別する [重複した**アイテム**] 列に値が表示されます。[**重複したアイテム**] 列の値には、エクスポートされたメッセージのアイテム id が含まれています。詳細については、「[電子情報開示検索結果の重複除外](de-duplication-in-ediscovery-search-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p133">Whether the message is a duplicate message if you enabled the de-duplication option when exporting the search results. Duplicate messages will have a value in the **Duplicate to Item** column that identifies the message as a duplicate. The value in the **Duplicate to Item** column contains the item identity of the message that was exported. For more information, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>
        
      <span data-ttu-id="46934-249">SharePoint と OneDrive for business サイトのドキュメントの場合、結果ログには、各ドキュメントに関する以下の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="46934-249">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
        
      - <span data-ttu-id="46934-250">ドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="46934-250">The URL for the document.</span></span>
        
      - <span data-ttu-id="46934-251">ドキュメントがあるサイト コレクションの URL。</span><span class="sxs-lookup"><span data-stu-id="46934-251">The URL for the site collection where the document is located.</span></span>
        
      - <span data-ttu-id="46934-252">ドキュメントが最後に変更された日付。</span><span class="sxs-lookup"><span data-stu-id="46934-252">The date that the document was last modified.</span></span>
        
      - <span data-ttu-id="46934-253">ドキュメントの名前 (これは、結果のログの [件名] 列にあります)。</span><span class="sxs-lookup"><span data-stu-id="46934-253">The name of the document (which is located in the Subject column in the result log).</span></span>
    
  - <span data-ttu-id="46934-p134">**インデックス**のないアイテム検索結果に含まれる、部分的にインデックスが作成されたアイテムに関する情報を含む Excel ドキュメント。検索結果レポートを生成するときに、部分的にインデックス付けされたアイテムを含めない場合、このレポートは引き続きダウンロードされますが、空になります。</span><span class="sxs-lookup"><span data-stu-id="46934-p134">**Unindexed Items** An Excel document that contains information about any partially indexed items that would be included in the search results. If you don't include partially indexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span> 
    
  - <span data-ttu-id="46934-p135">**エラーと警告**エクスポート中に発生したファイルのエラーと警告を含みます。各エラーまたは警告に固有の情報については、[エラーの詳細] 列を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p135">**Errors and Warnings** Contains errors and warnings for files encountered during export. See the Error Details column for information specific to each individual error or warning.</span></span> 
    
  - <span data-ttu-id="46934-p136">**スキップ**されたアイテムSharePoint および OneDrive for business サイトから検索結果をエクスポートする場合、通常、スキップされたアイテムのレポート (skippeditems) がエクスポートに含まれます。このレポートで言及されているアイテムは、通常、フォルダーやドキュメントセットなど、ダウンロードされないアイテムです。この種類のアイテムをエクスポートすることは、設計によるものではありません。スキップされたその他のアイテムについては、スキップされたアイテムレポートの [エラーの種類] および [エラーの詳細] フィールドに、アイテムがスキップされ、他の検索結果でダウンロードされなかった理由が表示されます。</span><span class="sxs-lookup"><span data-stu-id="46934-p136">**Skipped Items** When you export search results from SharePoint and OneDrive for Business sites, the export will usually include a skipped items report (SkippedItems.csv). The items cited in this report are typically items that won't be downloaded, such as a folder or a document set. Not exporting this types of items is by design. For other items that were skipped, the 'Error Type' and 'Error Details' field in the skipped items report show the reason the item was skipped and wasn't download with the other search results.</span></span> 
    
  - <span data-ttu-id="46934-262">**トレースログ**エクスポートプロセスに関する詳細なログ情報が含まれており、エクスポート中の問題を明らかにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="46934-262">**Trace Log** Contains detailed logging information about the export process and can help uncover issues during export.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="46934-p137">これらのドキュメントは、実際の検索結果をエクスポートせずにエクスポートするだけでかまいません。「[コンテンツ検索レポートをエクスポートする」を](export-a-content-search-report.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p137">You can just export these documents without having to export the actual search results. See [Export a Content Search report](export-a-content-search-report.md).</span></span> 
  
 ### <a name="exporting-partially-indexed-items"></a><span data-ttu-id="46934-265">部分的にインデックスが作成されたアイテムをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="46934-265">Exporting partially indexed items</span></span>
  
- <span data-ttu-id="46934-p138">検索結果のすべてのメールボックスアイテムを返すコンテンツ検索からメールボックスアイテムをエクスポートしている場合 (検索クエリに含まれているキーワードがないため)、部分的にインデックスが作成されたアイテムは、インデックスのないアイテムを含む PST ファイルにコピーされません。これは、部分的にインデックスが作成されたアイテムを含むすべてのアイテムが自動的に通常の検索結果に含まれるためです。これは、部分的にインデックスが作成されたアイテムが、他のインデックス付きアイテムを含む PST ファイル (または個別のメッセージ) に含まれることを意味します。</span><span class="sxs-lookup"><span data-stu-id="46934-p138">If you're exporting mailbox items from a content search that returns all mailbox items in the search results (because no keywords where included in the search query), partially indexed items won't be copied to the PST file that contains the unindexed items. This is because all items, including any partially indexed items, are automatically included in the regular search results. This means that partially indexed items will be included in a PST file (or as individual messages) that contains the other, indexed items.</span></span>
    
    <span data-ttu-id="46934-p139">また、インデックスが作成されたアイテムと部分的にインデックス付けされたアイテムの両方をエクスポートする場合、またはすべてのアイテムを返すコンテンツ検索からインデックス付きアイテムのみをエクスポートする場合は、同じ数のアイテムがダウンロードされます。これは、コンテンツ検索の予想される検索結果 (セキュリティ&amp;コンプライアンスセンターの検索統計に表示される) にも、部分的にインデックスが作成されたアイテムの数について別の推定結果が含まれる場合でも発生します。たとえば、すべてのアイテムを含む検索の推定値 (検索クエリにキーワードがありません) は、1000のアイテムが検出され、200の部分的なインデックスが作成されたアイテムも検出されたことを示しているとします。この例では、検索によってすべてのアイテムが返されるため、1000アイテムには部分的にインデックス付けされたアイテムが含まれます。つまり、検索によって返されるアイテムの合計は1000であり、1200アイテムではありません (期待したとおり)。この検索の結果をエクスポートし、インデックスが作成されたアイテムをエクスポートする (またはインデックス付きのアイテムのみ) ように選択すると、1000のアイテムがダウンロードされます。これは、空の検索クエリを使用してすべてのアイテムを返す場合に、部分的にインデックスが作成されたアイテムが通常の (インデックス付きの) 結果に含まれるためです。この同じ例では、部分的にインデックスが付けられたアイテムのみをエクスポートするように選択すると、200のインデックスのないアイテムのみがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="46934-p139">Additionally, if you export both the indexed and partially indexed items or if you export only the indexed items from a content search that returns all items, the same number of items will be downloaded. This happens even though the estimated search results for the content search (displayed in the search statistics in the Security &amp; Compliance Center) will still include a separate estimate for the number of partially indexed items. For example, let's say that the estimate for a search that includes all items (no keywords in the search query) shows that 1,000 items were found and that 200 partially indexed items were also found. In this case, the 1,000 items include the partially indexed items because the search returns all items. In other words, there are 1,000 total items returned by the search, and not 1,200 items (as you might expect). If you export the results of this search and choose to export indexed and partially indexed items (or just indexed items), then 1,000 items will be downloaded. Again, that's because partially indexed items are included with the regular (indexed) results when you use a blank search query to return all items. In this same example, if you choose to export only partially indexed items, then only the 200 unindexed items would be downloaded.</span></span>
    
    <span data-ttu-id="46934-277">また、前の例では、エクスポートされた検索結果に含まれているエクスポートの概要レポートでは、エクスポートされた検索結果に含まれる**エクスポートの概要**レポートに、1000アイテムの推定アイテムと1000がダウンロードされたことに注意してください。前に説明したものと同じ理由のアイテム。</span><span class="sxs-lookup"><span data-stu-id="46934-277">Also note that in the previous example (when you export indexed and partially indexed items or you export only indexed items) , the **Export Summary** report included with the exported search results would list 1,000 items estimated items and 1,000 downloaded items for the same reasons as previously described.</span></span> 
    
- <span data-ttu-id="46934-p140">結果のエクスポート元の検索が、特定のコンテンツの場所または組織内のすべてのコンテンツの場所の検索であった場合、検索条件に一致するアイテムを含むコンテンツの場所からの部分的なアイテムのみがエクスポートされます。言い換えると、メールボックスまたはサイトで検索結果が見つからない場合、そのメールボックスまたはサイト内の一部のインデックスアイテムはエクスポートされません。これは、組織内の多くの場所から、部分的にインデックスが作成されたアイテムをエクスポートすると、エクスポートエラーが発生する可能性が高くなり、検索結果のエクスポートとダウンロードにかかる時間が長くなる可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="46934-p140">If the search that you're exporting results from was a search of specific content locations or all content locations in your organization, only the partially items from content locations that contain items that match the search criteria will be exported. In other words, if no search results are found in a mailbox or site, then any partially indexed items in that mailbox or site won't be exported. The reason for this is that exporting partially indexed items from lots of locations in the organization might increase the likelihood of export errors and increase the time it takes to export and download the search results.</span></span>
    
    <span data-ttu-id="46934-281">検索用のすべてのコンテンツの場所から、部分的にインデックスが作成されたアイテムをエクスポートするには、検索結果をエクスポートするときに、すべてのアイテムを返すように検索を構成し (検索クエリからすべてのキーワードを削除する)、インデックスが作成されたアイテムのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="46934-281">To export partially indexed items from all content locations for a search, configure the search to return all items (by removing any keywords from the search query) and then export only partially indexed items when you export the search results.</span></span>
    
    ![インデックスのないアイテムのみをエクスポートするには、thrid エクスポートオプションを使用します。](media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- <span data-ttu-id="46934-p141">SharePoint または OneDrive for business サイトから検索結果をエクスポートする場合、インデックスが作成されていないアイテムをエクスポートできるかどうかは、選択したエクスポートオプションと検索条件に一致するインデックスアイテムが検索されたサイトであるかどうかによって決まります。たとえば、特定の SharePoint または OneDrive for business サイトを検索し、検索結果が見つからない場合は、2番目のエクスポートオプションを選択してインデックス付きアイテムとインデックスなしアイテムの両方をエクスポートすると、これらのサイトのインデックスが作成されていないアイテムはエクスポートされません。サイトからのインデックス付けされたアイテムが検索条件に一致した場合は、インデックスアイテムとインデックスのないアイテムの両方をエクスポートするときに、そのサイトのすべてのインデックスのないアイテムがエクスポートされます。次の図では、検索条件に一致するインデックス付きアイテムがサイトに含まれているかどうかに基づいたエクスポートオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="46934-p141">When exporting search results from SharePoint or OneDrive for Business sites, the ability to export unindexed items also depends on the export option that you select and whether a site that was searched contains an indexed item that matches the search criteria. For example, if you search specific SharePoint or OneDrive for Business sites and no search results are found, then no unindexed items from those sites will be exported if you choose the second export option to export both indexed and unindexed items. If an indexed item from a site does match the search criteria, then all unindexed items from that site will be exported when exporting both indexed and unindexed items. The following illustration describes the export options based on whether or not a site contains an indexed item that matches the search criteria.</span></span>
    
    ![検索条件に一致するインデックス付きアイテムがサイトに含まれているかどうかに基づいて、[エクスポート] オプションを選択します。](media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    
    <span data-ttu-id="46934-p142">検索条件に一致するインデックス付きのアイテムのみがエクスポートされます。部分的にインデックスが作成されたアイテムはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="46934-p142">A - Only indexed items that matches the search criteria are exported. No partially indexed items are exported.</span></span>
    
    <span data-ttu-id="46934-p143">B-インデックス付けされたアイテムが検索条件に一致しない場合、そのサイトからのインデックスが作成されたアイテムはエクスポートされません。サイトからインデックス付けされたアイテムが検索結果で返された場合、そのサイトの部分的なインデックスアイテムがエクスポートされます。つまり、検索条件に一致するアイテムを含むサイトから、部分的にインデックスが作成されたアイテムのみがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="46934-p143">B - If no indexed items from a site match the search criteria, then partially indexed items from that same site aren't exported. If indexed items from a site are returned in the search results, then the partially indexed items from that site are exported. In other words, only the partially indexed items from sites that contain items that match the search criteria are exported.</span></span>
    
    <span data-ttu-id="46934-293">C-検索条件に一致するアイテムがサイトに含まれているかどうかにかかわらず、検索内のすべてのサイトのすべてのインデックスアイテムがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="46934-293">C - All partially indexed items from all sites in the search are exported, regardless of whether a site contains items that match the search criteria.</span></span>
    
    <span data-ttu-id="46934-294">部分的にインデックスが作成されたアイテムをエクスポートすることを選択すると、[ **Exchange コンテンツのエクスポート**] で選択したオプションに関係なく、部分的にインデックスが作成されたメールボックスアイテムが別の PST ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="46934-294">If you choose to export partially indexed items, partially indexed mailbox items are exported in a separate PST file regardless of the option that you choose under **Export Exchange content as**.</span></span>

- <span data-ttu-id="46934-p144">部分的にインデックスが作成されたアイテムの他のプロパティが検索条件に一致したために、部分的にインデックスが作成されたアイテムが検索結果で返される場合、その部分的なインデックスは、通常の検索結果でエクスポートされます。そのため、インデックス付きアイテムと部分的にインデックスが作成されたアイテムの両方をエクスポートすることを選択した場合 ([**すべてのアイテム (認識できない形式のアイテムを含む、暗号化されているかどうか、その他の理由エクスポートオプションのインデックスがなかっ**た場合を含む)] を選択すると、エクスポートされます。が正規の結果である場合は、結果が .csv レポートに表示されます。インデックスなしの csv レポートには表示されません。</span><span class="sxs-lookup"><span data-stu-id="46934-p144">If partially indexed items are returned in the search results (because other properties of an partially indexed items matched the search criteria), then those partially indexed are exported with the regular search results. So, if you choose to export both indexed items and partially indexed items (by selecting the **All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons** export option), the partially indexed items exported with the regular results will be listed in the Results.csv report. They will not be listed in the Unindexed items.csv report.</span></span>
    
 ### <a name="exporting-individual-messages-or-pst-files"></a><span data-ttu-id="46934-298">個々のメッセージまたは PST ファイルのエクスポート</span><span class="sxs-lookup"><span data-stu-id="46934-298">Exporting individual messages or PST files</span></span>
  
- <span data-ttu-id="46934-p145">メッセージのファイルパス名が Windows の最大文字数制限を超えている場合、ファイルパス名は切り捨てられます。ただし、元のファイルパス名は、マニフェストと [記録ログ] に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="46934-p145">If the file path name of a message exceeds the maximum character limit for Windows, the file path name is truncated. But the original file path name will be listed in the Manifest and ResultsLog.</span></span>
    
- <span data-ttu-id="46934-p146">前述のように、電子メール検索結果はファイルシステム内のフォルダーにエクスポートされます。個々のメッセージのフォルダーパスは、ユーザーのメールボックス内のフォルダーのパスをレプリケートします。たとえば、"ContosoCase101" という名前の検索では、ユーザーの受信トレイ内のメッセージはフォルダーの`~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox`パスに配置されます。</span><span class="sxs-lookup"><span data-stu-id="46934-p146">As previously explained, email search results are exported to a folder in the file system. The folder path for individual messages would replicate the folder path in the user's mailbox. For example, for a search named "ContosoCase101" messages in a user's inbox would be located in the folder path  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox`.</span></span> 
    
- <span data-ttu-id="46934-p147">1つのフォルダー内のすべてのメッセージを含む1つの pst ファイルに電子メールメッセージをエクスポートする場合、[**削除済みアイテム**] フォルダーと [**検索フォルダー** ] フォルダーは pst フォルダーの最上位レベルに含まれます。これらのフォルダーは空になります。</span><span class="sxs-lookup"><span data-stu-id="46934-p147">If you choose to export email messages in one PST file containing all messages in a single folder, a **Deleted Items** folder and a **Search Folders** folder are included in the top level of the PST folder. These folders will be empty.</span></span> 
  
 ### <a name="decrypting-rms-encrypted-messages"></a><span data-ttu-id="46934-306">RMS で暗号化されたメッセージの復号化</span><span class="sxs-lookup"><span data-stu-id="46934-306">Decrypting RMS-encrypted messages</span></span>
  
- <span data-ttu-id="46934-p148">前述したように、RMS で暗号化されたメッセージをエクスポートするときに復号化するには、個々のメッセージとして検索結果をエクスポートする必要があります。検索結果を PST ファイルにエクスポートすると、RMS で暗号化されたメッセージは暗号化されたままになります。</span><span class="sxs-lookup"><span data-stu-id="46934-p148">As previously explained, to decrypt RMS-encrypted messages when you export them, you have to export the search results as individual messages. If you export search results to a PST file, RMS-encrypted messages will remain encrypted.</span></span>
    
- <span data-ttu-id="46934-p149">検索結果をエクスポートするときに、コンテンツ検索の RMS 復号化機能が Office 365 Message Encryption (OME) で暗号化されたメッセージを解読することはありません。ただし、OME で暗号化されたメッセージが組織内のユーザーによって送信された場合、ユーザーの送信フォルダー内のメッセージのコピーは暗号化されず、エクスポート後に表示できるようになります。ただし、OME で暗号化されたメッセージが組織内のユーザーによって受信されると、エクスポート後に暗号化が解除されることはありません。OME の詳細については、「 [Office 365 Message Encryption](https://go.microsoft.com/fwlink/p/?linkid=844966)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p149">The RMS decryption feature in Content Search doesn't decrypt messages encrypted with Office 365 Message Encryption (OME) when you export search results. However, if a message encrypted with OME is sent by a user in your organization, the copy of the message in the user's Sent folder isn't encrypted and will be viewable after it's exported. However, if messages encrypted with OME are received by users in your organization, they won't be decrypted after they're exported. For more information about OME, see [Office 365 Message Encryption](https://go.microsoft.com/fwlink/p/?linkid=844966).</span></span>
    
- <span data-ttu-id="46934-p150">復号化されたメッセージは、"**出力ログ**" レポートで識別されます。このレポートには、**デコード状態**という名前の列が含まれており、この列で**デコード**された値は、が復号化されたメッセージを識別します。</span><span class="sxs-lookup"><span data-stu-id="46934-p150">Messages that are decrypted are identified in the **ResultsLog** report. This report contains a column named **Decode Status**, and a value of **Decoded** in this column identifies the messages the were decrypted.</span></span> 
    
- <span data-ttu-id="46934-p151">現時点では、この復号化機能には、SharePoint および OneDrive for business サイトの暗号化されたコンテンツは含まれていません。RMS で暗号化された電子メールメッセージのみが、エクスポート時に復号化されます。</span><span class="sxs-lookup"><span data-stu-id="46934-p151">Currently, this decryption capability doesn't include encrypted content from SharePoint and OneDrive for Business sites. Only RMS-encrypted email messages will be decrypted when you export them.</span></span>
    
- <span data-ttu-id="46934-317">RMS で暗号化された電子メールメッセージに、添付ファイル (ドキュメントや別の電子メールメッセージなど) が含まれている場合は、最上位の電子メールメッセージのみが復号化されます。</span><span class="sxs-lookup"><span data-stu-id="46934-317">If an RMS-encrypted email message has an attachment (such as a document or another email message) that's also encrypted, only the top-level email message will be decrypted.</span></span>
    
- <span data-ttu-id="46934-p152">RMS で暗号化された電子メールメッセージをプレビューすることはできません。暗号化されたメッセージを表示するには、それをエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="46934-p152">You can't preview an RMS-encrypted email message. To view an encrypted message, you have to export it.</span></span>
    
- <span data-ttu-id="46934-p153">ユーザーが rms で暗号化されたメッセージの暗号化を解除できないようにする必要がある場合は、(組み込みの電子情報開示マネージャーの役割グループをコピーして) カスタムの役割グループを作成し、そのカスタム役割グループから RMS の解読管理役割を削除する必要があります。その後、メッセージの暗号化を解除しないユーザーを、カスタム役割グループのメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="46934-p153">If you need to prevent someone from decrypting RMS-encrypted messages, you'll have to create a custom role group (by copying the built-in eDiscovery Manager role group) and then remove the RMS Decrypt management role from the custom role group. Then add the person who you don't want to decrypt messages as a member of the custom role group.</span></span>
  
 ### <a name="filenames-of-exported-items"></a><span data-ttu-id="46934-322">エクスポートされたアイテムのファイル名</span><span class="sxs-lookup"><span data-stu-id="46934-322">Filenames of exported items</span></span>
  
- <span data-ttu-id="46934-p154">ローカルコンピューターにエクスポートされた電子メールメッセージとサイトドキュメントの完全パス名には、オペレーティングシステムによって適用される260文字の制限があります。エクスポートされたアイテムの完全なパス名には、検索結果がダウンロードされるローカルコンピューター上のアイテムの元の場所とフォルダーの場所が含まれます。たとえば、電子情報開示エクスポートツール`C:\Users\Admin\Desktop\SearchResults`で検索結果をダウンロードするように指定すると、ダウンロードした電子メールアイテムの完全パス名`C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg`はになります。</span><span class="sxs-lookup"><span data-stu-id="46934-p154">There is a 260-character limit (imposed by the operating system) for the full path name for email messages and site documents exported to your local computer. The full path name for exported items includes the item's original location and the folder location on the local computer where the search results are downloaded to. For example, if you specify to download the search results to  `C:\Users\Admin\Desktop\SearchResults` in the eDiscovery Export tool, then the full pathname for a downloaded email item would be  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg`.</span></span>
    
    <span data-ttu-id="46934-326">260文字の制限を超えている場合は、アイテムの完全なパス名が切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="46934-326">If the 260-character limit is exceeded, the full path name for an item will be truncated.</span></span>
    
  - <span data-ttu-id="46934-327">完全なパス名が260文字より長い場合は、ファイル名が短くなり、制限を超えてしまいます。切り捨てられたファイル名 (ファイル拡張子を除く) は、8文字未満にならないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="46934-327">If the full path name is longer than 260 characters, the file name will be shortened to get under the limit; note that the truncated filename (excluding the file extension) won't be less than 8 characters.</span></span>
    
  - <span data-ttu-id="46934-p155">ファイル名を短くしても完全なパス名が長い場合は、アイテムは現在の場所から親フォルダーに移動されます。パス名が長すぎる場合は、次の処理が繰り返されます。ファイル名を短くし、必要に応じて親フォルダーに再度移動します。この処理は、完全なパス名が260文字の制限を超えない限り繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="46934-p155">If the full path name is still too long after shortening the file name, the item is moved from its current location to the parent folder. If the pathname is still too long, then the process is repeated: shorten the filename, and if necessary move again to the parent folder. This process is repeated until the full pathname is under the 260-character limit.</span></span>
    
  - <span data-ttu-id="46934-331">省略された完全なパス名が既に存在する場合は、ファイル名の末尾にバージョン番号が追加されます。たとえば、 `statusmessage(2).msg`のようになります。</span><span class="sxs-lookup"><span data-stu-id="46934-331">If a truncated full path name already exists, a version number will be added to the end of the filename; for example,  `statusmessage(2).msg`.</span></span>
    
    <span data-ttu-id="46934-332">この問題を軽減するために、短いパス名の場所に検索結果をダウンロードすることを検討してください。たとえば、という名前`C:\Results`のフォルダーに検索結果をダウンロードすると、という名前`C:\Users\Admin\Desktop\Results`のフォルダーにダウンロードするよりも、エクスポートされたアイテムのパス名の文字数が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="46934-332">To help mitigate this issue, consider downloading search results to a location with a short path name; for example, downloading search results to a folder named  `C:\Results` would add fewer characters to the path names of exported items than downloading them to a folder named  `C:\Users\Admin\Desktop\Results`.</span></span>
    
- <span data-ttu-id="46934-p156">サイトドキュメントをエクスポートする場合も、ドキュメントの元のファイル名が変更される可能性があります。これは特に、保留になっている SharePoint または OneDrive for business サイトから削除されたドキュメントに対して発生します。保留中のサイトに配置されたドキュメントが削除されると、削除されたドキュメントは、サイト (サイトが保留状態になっているときに作成されたもの) の保持保持ライブラリに自動的に移動します。削除されたドキュメントを保存保持ライブラリに移動すると、ランダムに生成された一意の ID がドキュメントの元のファイル名に追加されます。たとえば、ドキュメントのファイル名が`FY2017Budget.xlsx`後に削除されて、保存保持ライブラリに移動された場合、そのドキュメントのファイル名は、保存保持ライブラリに移動されたときのよう`FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`に変更されます。保持保持ライブラリ内のドキュメントがコンテンツ検索のクエリと一致し、その検索の結果をエクスポートすると、エクスポートされたファイルには変更されたファイル名が含まれます。この例では、エクスポートさ`FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`れたドキュメントのファイル名はになります。</span><span class="sxs-lookup"><span data-stu-id="46934-p156">When you export site documents, it's also possible that the original file name of a document will be modified. This happens specifically for documents that have been deleted from a SharePoint or OneDrive for Business site that's been placed on hold. After a document that's located on a site that's on hold is deleted, the deleted document is automatically moved to the Preservation Hold library for the site (which was created when the site was placed on hold). When the deleted document is moved to the Preservation Hold library, a randomly-generated and unique ID is appended to the original filename of the document. For example, if the filename for a document is  `FY2017Budget.xlsx` and that document is later deleted and moved to the Preservation Hold library, the filename of the document that is moved to the Preservation Hold library is modified to something like  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`. If a document in the Preservation Hold library matches the query of a Content Search and you export the results of that search, the exported file will have the modified filename; in this example, the filename of the exported document would be  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`.</span></span>
    
    <span data-ttu-id="46934-p157">また、保留中のサイトにあるドキュメントが変更されたときに (サイト内のドキュメントライブラリのバージョン管理が有効になっている場合)、ファイルのコピーが自動的に保存保持ライブラリに作成されます。この場合、ランダムに生成された一意の ID が、保持保持ライブラリにコピーされるドキュメントのファイル名にも追加されます。</span><span class="sxs-lookup"><span data-stu-id="46934-p157">Additionally, when a document located on a site that's on hold is modified (and versioning for the document library in the site has been enabled), a copy of the file is automatically created in the Preservation Hold library. In this case, a randomly-generated and unique ID is also appended to the filename of the document that's copied to the Preservation Hold library.</span></span>
    
    <span data-ttu-id="46934-p158">保存保持ライブラリに移動またはコピーされたドキュメントのファイル名が競合しないようにする理由は、競合しているファイル名を防ぐためです。サイトおよび保持保持ライブラリに保持を配置することの詳細については、「 [SharePoint Server 2016 のインプレースホールドの概要](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p158">The reason why filenames of documents that are moved or copied to the Preservation Hold library is to prevent conflicting filenames. For more information about placing a hold on sites and the Preservation Hold library, see [Overview of in-place hold in SharePoint Server 2016](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95).</span></span>
    
 ### <a name="miscellaneous"></a><span data-ttu-id="46934-343">その他</span><span class="sxs-lookup"><span data-stu-id="46934-343">Miscellaneous</span></span>
  
- <span data-ttu-id="46934-p159">すべての検索結果とエクスポートレポートは、コンテンツ検索と同じ名前のフォルダーに含まれています。エクスポートされた電子メールメッセージは、 **Exchange**という名前のフォルダーにあります。ドキュメントは、 **SharePoint**という名前のフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="46934-p159">All search results and the export reports are included in a folder that has the same name as the Content Search. The email messages that were exported are located in a folder named **Exchange**. Documents are located in a folder named **SharePoint**.</span></span> 
    
- <span data-ttu-id="46934-p160">SharePoint および OneDrive for business サイトのドキュメントのファイルシステムメタデータは、ドキュメントをローカルコンピューターにエクスポートするときに維持されます。これは、ドキュメントがエクスポートされるときに、作成日時、最終変更日などのドキュメントプロパティが変更されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="46934-p160">The file system metadata for documents on SharePoint and OneDrive for Business sites is maintained when documents are exported to your local computer. That means document properties, such as created and last modified dates, aren't changed when documents are exported.</span></span>

- <span data-ttu-id="46934-p161">検索クエリに一致する SharePoint のリストアイテムが検索結果に含まれている場合は、検索クエリと一致するアイテムに加えて、リスト内のすべての行がエクスポートされます。これには、リスト内のすべての添付ファイルが含まれます。これは、検索結果で返されるリストアイテムのコンテキストを提供するためのものです。また、追加のリストアイテムと添付ファイルを使用すると、エクスポートされたアイテムのカウントが検索結果の元の推定値と異なる場合があることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="46934-p161">If your search results include a list item from SharePoint that matches the search query, all rows in the list will be exported in addition to the item that matches the search query. This includes any attachments in the list. The reason for this is to provide a context for list items that are returned in the search results. Also note that the additional list items and attachments may cause the count of exported items to be different than the original estimate of search results.</span></span>
