---
title: Office 365 に PST ファイルをインポートするときにデータをフィルター処理します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
description: '対象のメールボックスに実際にインポートを取得するアイテムをフィルターするのには Office 365 のインポート サービスの新しいインテリジェントなインポート機能を使用します。インテリジェント ・ インポートでは、事前にインポートし、何を残すには、どのようなデータを決定することができます。インテリジェント ・ インポートでは、Office 365 にインポートするデータの情報も提供します。 '
ms.openlocfilehash: c90d9df62c7d8c411196b283acec37959fc95e57
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038200"
---
# <a name="filter-data-when-importing-pst-files-to-office-365"></a><span data-ttu-id="d9cdd-105">Office 365 に PST ファイルをインポートするときにデータをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-105">Filter data when importing PST files to Office 365</span></span>

<span data-ttu-id="d9cdd-p102">対象のメールボックスに実際にインポートを取得する PST ファイル内のアイテムにフィルターを適用するのには、Office 365 のインポート サービスの新しいインテリジェントなインポート機能を使用します。その動作を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p102">Use the new Intelligent Import feature in the Office 365 Import service to filter the items in PST files that actually get imported to the target mailboxes. Here's how it works:</span></span>
  
- <span data-ttu-id="d9cdd-108">作成し、PST のインポート ジョブを送信した後、PST ファイルは、マイクロソフトのクラウド内の Azure ストレージ領域にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-108">After you create and submit a PST import job, PST files are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="d9cdd-109">Office 365 は、メールボックスのアイテムと PST ファイルに含まれている別のメッセージの種類の保存期間を識別することによって、安全性とセキュリティで保護された方法で、PST ファイル内のデータを分析します。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-109">Office 365 analyzes the data in the PST files, in a safe and secure manner, by identifying the age of the mailbox items and the different message types included in the PST files.</span></span>
    
- <span data-ttu-id="d9cdd-p103">分析が完了すると、データをインポートする準備ができました、またはインポートされたデータを取得するかを制御するフィルターを設定することによってインポートされたデータをトリミングすると、PST ファイルのすべてのデータをインポートするオプションがあります。たとえば、することもできます。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p103">When the analysis is complete and the data is ready to import, you have the option to import all data in the PST files as is or trim the data that's imported by setting filters that control what data gets imported. For example, you can choose to:</span></span>
    
  - <span data-ttu-id="d9cdd-112">特定の年齢の項目のみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-112">Import only items of a certain age.</span></span>
    
  - <span data-ttu-id="d9cdd-113">選択したメッセージの種類をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-113">Import selected message types.</span></span>
    
  - <span data-ttu-id="d9cdd-114">特定のユーザーによって送信または受信のメッセージを除外します。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-114">Exclude messages sent or received by specific people.</span></span>
    
- <span data-ttu-id="d9cdd-115">フィルターの設定を構成した後、Office 365 は、インポート ジョブで指定されたターゲット メールボックスにフィルター条件に一致するデータのみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-115">After you configure the filter settings, Office 365 imports only the data that meets the filtering criteria to the target mailboxes specified in the import job.</span></span>
    
<span data-ttu-id="d9cdd-116">次の図はインテリジェントなインポート プロセスを示していて、タスクを実行し、Office 365 によって実行されるタスクを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-116">The following graphic shows the Intelligent Import process, and highlights the tasks you perform and the tasks performed by Office 365.</span></span>
  
![Office 365 のインテリジェントなインポート処理](media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="before-you-begin"></a><span data-ttu-id="d9cdd-118">はじめに</span><span class="sxs-lookup"><span data-stu-id="d9cdd-118">Before you begin</span></span>

- <span data-ttu-id="d9cdd-p104">このトピックの手順では、PST のインポート ジョブ ネットワーク アップロードまたは送付先のドライブを使用して Office 365 のインポート サービスに作成したと仮定します。手順については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p104">The steps in this topic assume that you've created a PST import job in the Office 365 Import service by using network upload or drive shipping. For step-by-step instructions, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="d9cdd-121">ネットワーク アップロードを使用して PST ファイルを Office 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="d9cdd-121">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
  - [<span data-ttu-id="d9cdd-122">ドライブ送付を使用して PST ファイルを Office 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="d9cdd-122">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- <span data-ttu-id="d9cdd-p105">インポートでインポート ジョブのステータスが Office 365 のセキュリティ ページ ネットワークのアップロードを使用して、インポート ジョブを作成したら、&amp;コンプライアンス センターに設定**を解析して**、Office 365 が PST ファイルのデータを分析していることを意味することアップロードします。[**更新**] をクリックして![更新](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)インポート ジョブの状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p105">After you create an import job by using network upload, the status for the import job on the Import page in Office 365 Security &amp; Compliance Center is set to **Analysis in progress**, which means that Office 365 is analyzing the data in the PST files that you uploaded. Click **Refresh**![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the status for the import job.</span></span> 
    
- <span data-ttu-id="d9cdd-125">インポート ジョブを配布するドライブは、Microsoft データ センターのスタッフは、ハード ディスク ドライブが表示され、組織、Azure のストレージ領域を PST ファイルをアップロードした後、Office 365 でデータを分析してがします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-125">For drive shipping import jobs, the data will be analyzed by Office 365 after Microsoft data center personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span></span>
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a><span data-ttu-id="d9cdd-126">メールボックスにインポートを取得するデータをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-126">Filter data that gets imported to mailboxes</span></span>

<span data-ttu-id="d9cdd-127">作成した後、PST ジョブのインポートは、Office 365 にインポートする前にデータをフィルター処理するのには次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-127">After you've created a PST import job, follow these steps to filter the data before you import it to Office 365.</span></span>
  
1. <span data-ttu-id="d9cdd-128">[https://protection.office.com/](https://protection.office.com/)し、組織の Office 365 の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-128">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="d9cdd-129">Office 365 のセキュリティの左側のウィンドウで&amp;コンプライアンス センターでは、**データの管理**をクリックして\>**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-129">In the left pane of the Office 365 Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
    <span data-ttu-id="d9cdd-p106">組織のインポート ジョブは、[**インポート**] ページに一覧表示されます。**分析は完了\*\*\*\*状態**] 列に値が、インポート ジョブは Office 365 によって分析されているし、インポートする準備ができているを示しているに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p106">The import jobs for your organization are listed on the **Import** page. Note that the **Analysis completed** value in the **Status** column indicates the import jobs that have been analyzed by Office 365 and are ready for you to import.</span></span> 
    
    ![分析の完全な状態では、Office 365 は、PST ファイル内のデータを分析ことを示します](media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. <span data-ttu-id="d9cdd-133">インポート ジョブを完了するのには、 **Office 365 にインポートする準備**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-133">Click **Ready to import to Office 365** for the import job that you want to complete.</span></span> 
    
    <span data-ttu-id="d9cdd-134">ページをその場は、PST ファイルの情報とインポート ジョブに関する他の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-134">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="d9cdd-135">**Office 365 にインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-135">Click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="d9cdd-p107">**データにフィルターをかける**] ページが表示されます。データの保存期間に関する情報を含む、インポート ジョブは、PST ファイルのデータに関するデータの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p107">The **Filter your data** page is displayed. It contains data insights about the data in the PST files for the import job, including information about the age of the data.</span></span> 
    
    ![フィルター、データ ページは、インポート ジョブの PST ファイルのデータの分析を示しています。](media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. <span data-ttu-id="d9cdd-139">で、Office 365 にインポートされるデータをトリミングするかどうかに基づいて**にデータをフィルターする?**、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-139">Based on whether or not you want to trim the data that's imported to Office 365, under **Do you want to filter your data?**, do one of the following:</span></span>
    
    <span data-ttu-id="d9cdd-p108">a. では、**インポートする前にフィルター処理する**、インポートしたデータをトリムするのにはをクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p108">a. Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.</span></span>
    
    <span data-ttu-id="d9cdd-142">**Office 365 のページへのデータのインポート**] ページには、Office 365 を実行する解析の詳細なデータ分析が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-142">The **Import data to Office 365 page** page is displayed with detailed data insights from the analysis that Office 365 performed.</span></span> 
    
    ![Office 365 には、PST ファイルの分析からデータの詳細な情報が表示されます。](media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    <span data-ttu-id="d9cdd-p109">このページ上のグラフでは、インポートされるデータの量を示します。PST ファイルで検出された各メッセージの種類に関する情報は、グラフに表示されます。そのメッセージの種類に関する特定の情報を表示するには、各バーの上にカーソルを合わせたことができます。PST ファイルの解析に基づくさまざまな年齢の値を持つドロップ ダウン リストもあります。ドロップ ダウン リストで、有効期間を選択すると、データの量は、選択した期間のインポートを表示するグラフが更新されます。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p109">The graph on this page shows the amount of data that will be imported. Information about each message type found in the PST files is displayed in the graph. You can hover the cursor over each bar to display specific information about that message type. There is also a drop-down list with different age values based on the analysis of the PST files. When you select an age in the drop-down list, the graph is updated to show how much data will be imported for the selected age.</span></span> 
    
    <span data-ttu-id="d9cdd-p110">b. インポートされるデータの量を減らすために追加のフィルターを構成するには、**他のフィルター オプション**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p110">b. To configure addition filters to reduce the amount of data that's imported, click **More filtering options**.</span></span>
    
    ![インポートするデータをトリムするのには [詳細オプション] ページで、フィルターを構成します。](media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    <span data-ttu-id="d9cdd-152">これらのフィルターを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-152">You can configure these filters:</span></span>
    
      - <span data-ttu-id="d9cdd-p111">**時代**のアイテムのみが指定された期間よりも新しいため、経過時間をインポートする] を選択します。Office 365 で**年齢**フィルターの有効期間のバケットを決定する方法についての説明の[詳細について](filter-data-when-importing-pst-files.md#moreinfo)はを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p111">**Age** - Select an age so only items that are newer than the specified age will be imported. See the [More information](filter-data-when-importing-pst-files.md#moreinfo) section for a description about how Office 365 determines the age buckets for the **Age** filter.</span></span> 
    
      - <span data-ttu-id="d9cdd-p112">**タイプ**- このセクションでは、インポート ジョブの PST ファイル内で見つかったすべてのメッセージの種類を示しています。除外するメッセージの種類の横のボックスをオフにすることができます。その他のメッセージの種類を除外することはできませんに注意してください。メールボックス アイテムを他のカテゴリに含まれているリストの[詳細について](filter-data-when-importing-pst-files.md#moreinfo)はセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p112">**Type** - This section shows all the message types that were found in the PST files for the import job. You can uncheck a box next to a message type that you want to exclude. Note that you can't exclude the Other message type. See the [More information](filter-data-when-importing-pst-files.md#moreinfo) section for a list of mailbox items that are included in the Other category.</span></span> 
    
      - <span data-ttu-id="d9cdd-p113">**ユーザー**にメッセージを送信または受信した特定の人を除外することができます。From に表示するユーザーを除外する: フィールドに、: フィールド、または [Cc: メッセージのフィールドをクリックして**ユーザーを除外**する受信者の種類です。相手の電子メール アドレス (SMTP アドレス) を入力、[**追加**] をクリックして![新しいアイコン](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)、その受信者の種類を除外するユーザーのリストに追加し、**保存**を除外するユーザーの一覧を保存する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p113">**Users** - You can exclude messages that are sent or received by specific people. To exclude people who appear in the From: field, To: field, or the Cc: field of messages, click **Exclude users** next to that recipient type. Type the email address (SMTP address) of the person, click **Add**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) to add them to the list of excluded users for that recipient type, and then click **Save** to save the list of excluded users.</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="d9cdd-p114">Office 365**ユーザー**フィルターの設定に起因するデータの情報が表示されません。ただし、特定のユーザーによって送信または受信のメッセージを除外するには、このフィルターを設定する場合、実際のインポート プロセス中にこれらのメッセージが除外されます。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p114">Office 365 doesn't show data insights that result from setting the **People** filter. However, if you set this filter to exclude messages sent or received by specific people, those messages will be excluded during the actual import process.</span></span> 
  
    <span data-ttu-id="d9cdd-p115">c. では、フィルター設定を保存するページを**複数のフィルター オプション**その場で**適用**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p115">c. Click **Apply** in the **More filtering options** fly out page to save your filter settings.</span></span> 
    
    <span data-ttu-id="d9cdd-p116">**Office 365 へのデータのインポート**] ページに関する情報を提供は、フィルターの設定に基づいてください。、更新データは、インポートするデータ量の合計を含むフィルターの設定に基づいてください。フィルター設定の概要が表示されてもいることを注意してください。必要に応じて設定を変更するフィルターの横には、**編集**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p116">The data insights on the **Import data to Office 365** page are updated based on your filter settings, including the total amount of data that will be imported based on the filter settings. Note that a summary of the filter settings is also shown. You can click **Edit** next to a filter to change the setting if necessary.</span></span> 
    
    ![データ情報が更新され、フィルターの設定](media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    <span data-ttu-id="d9cdd-p117">d. [**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p117">d. Click **Next**.</span></span>
    
    <span data-ttu-id="d9cdd-p118">状態ページに、フィルターの設定が表示されます。もう一度、フィルターの設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p118">A status page is displayed showing your filter settings. Again, you can edit any of the filter settings.</span></span>
    
    <span data-ttu-id="d9cdd-p119">e. では、**データをインポートする**インポートを開始します] をクリックします。インポートされるデータ量の合計が表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p119">e. Click **Import data** to start the import . Note that the total amount of data that will be imported is displayed.</span></span> 
    
    <span data-ttu-id="d9cdd-177">または</span><span class="sxs-lookup"><span data-stu-id="d9cdd-177">Or</span></span>
    
    <span data-ttu-id="d9cdd-p120">a.**いいえ、すべてのものをインポートする**を Office 365 では、PST ファイル内のすべてのデータをインポートする] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p120">a. Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.</span></span>
    
    <span data-ttu-id="d9cdd-p121">b. **Office 365 へのデータのインポート**] ページで、[**データをインポート**インポートを開始するをクリックします。インポートされるデータ量の合計が表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p121">b. On the **Import data to Office 365** page, click **Import data** to start the import. Note that the total amount of data that will be imported is displayed.</span></span> 
    
6. <span data-ttu-id="d9cdd-p122">[**インポート**] ページで [**更新**] をクリックします![更新](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)。インポート ジョブのステータスは、[**状態**] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p122">On the **Import** page, click **Refresh** ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png). The status for the import job is displayed in the **Status** column.</span></span> 
    
7. <span data-ttu-id="d9cdd-185">インポートの詳細については、各 PST ファイルと設定したフィルターの設定の状態などを表示するジョブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-185">Click the import the job to display more detailed information, such as the status for each PST file and the filter settings that you configured.</span></span>

  
## <a name="more-information"></a><span data-ttu-id="d9cdd-186">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d9cdd-186">More information</span></span>

- <span data-ttu-id="d9cdd-p123">Office 365 は、フィルターの有効期間の単位をどのように決定するのでしょうか。各項目の送信または受信した時刻のタイムスタンプにするときに Office 365 は、PST ファイルを分析し、検索 (最も古い日付を選択する場合は、品目には、送信および受信したタイムスタンプの両方が割り当てられている)。Office 365 を使用して、そのタイムスタンプの年の値を調べ、アイテムの期間を確認する現在の日付を比較します。これらの年齢は、**年齢**フィルターのドロップダウン リスト内の値として使用されます。たとえば、PST ファイルは、2016、2015 年と 2014 年からメッセージを受信し、**年齢**フィルターに値をなります**1 年間** **2 年間**、および**3 年間**。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p123">How does Office 365 determine the increments for the age filter? When Office 365 analyzes a PST file, it looks at the sent or received time stamp of each item (if an item has both a sent and received timestamp, the oldest date is selected). Then Office 365 looks at the year value for that timestamp and compares it to the current date to determine the age of the item. These ages are then used as the values in the drop-down list for the **Age** filter. For example, if a PST file has messages from 2016, 2015, and 2014, then values in the **Age** filter would be **1 year**, **2 years**, and **3 years**.</span></span>
    
- <span data-ttu-id="d9cdd-p124">次の表に、ページを**他のオプション**の実行時に**型**のフィルターで**その他の**カテゴリに含まれるメッセージの種類 (前の手順の手順 5 b を参照してください)。現時点では、Office 365 に pst ファイルをインポートするときは、「その他」カテゴリ内の項目を除外できません。 します</span><span class="sxs-lookup"><span data-stu-id="d9cdd-p124">The following table lists the message types that are included in the **Other** category in the **Type** filter on the **More options** fly out page (see Step 5b in the previous procedure). Currently, you can't exclude items in the "Other" category when you import PSTs to Office 365.</span></span> 
    
    |<span data-ttu-id="d9cdd-194">**メッセージ クラス ID**</span><span class="sxs-lookup"><span data-stu-id="d9cdd-194">**Message class ID**</span></span>|<span data-ttu-id="d9cdd-195">**このメッセージ クラスを使用して、メールボックスのアイテム**</span><span class="sxs-lookup"><span data-stu-id="d9cdd-195">**Mailbox items that use this message class**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d9cdd-196">IPM.活動</span><span class="sxs-lookup"><span data-stu-id="d9cdd-196">IPM.Activity</span></span>  <br/> |<span data-ttu-id="d9cdd-197">仕訳帳のエントリ</span><span class="sxs-lookup"><span data-stu-id="d9cdd-197">Journal entries</span></span>  <br/> |
    |<span data-ttu-id="d9cdd-198">IPM.ドキュメント</span><span class="sxs-lookup"><span data-stu-id="d9cdd-198">IPM.Document</span></span>  <br/> |<span data-ttu-id="d9cdd-199">ドキュメントやファイルを (電子メール メッセージに添付されません)</span><span class="sxs-lookup"><span data-stu-id="d9cdd-199">Documents and files (not attached to an email message)</span></span>  <br/> |
    |<span data-ttu-id="d9cdd-200">IPM.ファイル</span><span class="sxs-lookup"><span data-stu-id="d9cdd-200">IPM.File</span></span>  <br/> |<span data-ttu-id="d9cdd-201">(IPM と同じです。ドキュメント)</span><span class="sxs-lookup"><span data-stu-id="d9cdd-201">(same as IPM.Document)</span></span>  <br/> |
    |<span data-ttu-id="d9cdd-202">IPM.Note.IMC.Notification</span><span class="sxs-lookup"><span data-stu-id="d9cdd-202">IPM.Note.IMC.Notification</span></span>  <br/> |<span data-ttu-id="d9cdd-203">レポートを送信して、インターネット メールの接続、インターネットへの Exchange Server のゲートウェイであります。</span><span class="sxs-lookup"><span data-stu-id="d9cdd-203">Reports sent by Internet Mail Connect, which is the Exchange Server gateway to the Internet</span></span>  <br/> |
    |<span data-ttu-id="d9cdd-204">IPM.Note.Microsoft.Fax</span><span class="sxs-lookup"><span data-stu-id="d9cdd-204">IPM.Note.Microsoft.Fax</span></span>  <br/> |<span data-ttu-id="d9cdd-205">Fax メッセージ</span><span class="sxs-lookup"><span data-stu-id="d9cdd-205">Fax messages</span></span>  <br/> |
    |<span data-ttu-id="d9cdd-206">IPM.Note.Rules.Oof.Template.Microsoft</span><span class="sxs-lookup"><span data-stu-id="d9cdd-206">IPM.Note.Rules.Oof.Template.Microsoft</span></span>  <br/> |<span data-ttu-id="d9cdd-207">不在時の自動応答メッセージ</span><span class="sxs-lookup"><span data-stu-id="d9cdd-207">Out-of-office auto-reply messages</span></span>  <br/> |
    |<span data-ttu-id="d9cdd-208">IPM.Note.Rules.ReplyTemplate.Microsoft</span><span class="sxs-lookup"><span data-stu-id="d9cdd-208">IPM.Note.Rules.ReplyTemplate.Microsoft</span></span>  <br/> |<span data-ttu-id="d9cdd-209">受信トレイ ルールによってメッセージの返信</span><span class="sxs-lookup"><span data-stu-id="d9cdd-209">Replies sent by an inbox rule</span></span>  <br/> |
    |<span data-ttu-id="d9cdd-210">IPM.OLE です。クラス</span><span class="sxs-lookup"><span data-stu-id="d9cdd-210">IPM.OLE.Class</span></span>  <br/> |<span data-ttu-id="d9cdd-211">定期的な一連の例外</span><span class="sxs-lookup"><span data-stu-id="d9cdd-211">Exceptions for a recurring series</span></span>  <br/> |
    |<span data-ttu-id="d9cdd-212">IPM.Recall.Report</span><span class="sxs-lookup"><span data-stu-id="d9cdd-212">IPM.Recall.Report</span></span>  <br/> |<span data-ttu-id="d9cdd-213">メッセージの取り消し状況レポート</span><span class="sxs-lookup"><span data-stu-id="d9cdd-213">Message recall reports</span></span>  <br/> |
    |<span data-ttu-id="d9cdd-214">IPM.リモート</span><span class="sxs-lookup"><span data-stu-id="d9cdd-214">IPM.Remote</span></span>  <br/> |<span data-ttu-id="d9cdd-215">リモート メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="d9cdd-215">Remote mail messages</span></span>  <br/> |
    |<span data-ttu-id="d9cdd-216">IPM.レポート</span><span class="sxs-lookup"><span data-stu-id="d9cdd-216">IPM.Report</span></span>  <br/> |<span data-ttu-id="d9cdd-217">項目ステータス レポート</span><span class="sxs-lookup"><span data-stu-id="d9cdd-217">Item status reports</span></span>  <br/> |
