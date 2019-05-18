---
title: Office 365 に PST ファイルをインポートするときにデータをフィルター処理する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
description: 'Office 365 インポートサービスの新しいインテリジェントインポート機能を使用して、実際にターゲットメールボックスにインポートされるアイテムをフィルター処理します。 インテリジェントインポートを使用すると、どのデータをインポートするか、またどのデータを残しておくかを事前に決定できます。 インテリジェントインポートでは、Office 365 にインポートしているデータについての洞察も提供されます。 '
ms.openlocfilehash: 2e012159f7f278dc10db14b07531686b5d130fd9
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154599"
---
# <a name="filter-data-when-importing-pst-files-to-office-365"></a><span data-ttu-id="5afd9-105">Office 365 に PST ファイルをインポートするときにデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="5afd9-105">Filter data when importing PST files to Office 365</span></span>

<span data-ttu-id="5afd9-106">Office 365 インポートサービスの新しいインテリジェントインポート機能を使用して、実際にターゲットメールボックスにインポートされる PST ファイル内のアイテムをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5afd9-106">Use the new Intelligent Import feature in the Office 365 Import service to filter the items in PST files that actually get imported to the target mailboxes.</span></span> <span data-ttu-id="5afd9-107">次に、動作のしくみを示します。</span><span class="sxs-lookup"><span data-stu-id="5afd9-107">Here's how it works:</span></span>
  
- <span data-ttu-id="5afd9-108">PST インポートジョブを作成して送信すると、PST ファイルが Microsoft クラウドの Azure ストレージ領域にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-108">After you create and submit a PST import job, PST files are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="5afd9-109">Office 365 は、メールボックスアイテムの保存期間と PST ファイルに含まれるさまざまなメッセージの種類を識別することによって、PST ファイル内のデータを安全かつ安全な方法で分析します。</span><span class="sxs-lookup"><span data-stu-id="5afd9-109">Office 365 analyzes the data in the PST files, in a safe and secure manner, by identifying the age of the mailbox items and the different message types included in the PST files.</span></span>
    
- <span data-ttu-id="5afd9-110">分析が完了し、データをインポートする準備ができたら、すべてのデータをその PST ファイルにインポートするか、またはインポートするデータを制御するフィルターを設定することによってインポートされたデータをトリミングするかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-110">When the analysis is complete and the data is ready to import, you have the option to import all data in the PST files as is or trim the data that's imported by setting filters that control what data gets imported.</span></span> <span data-ttu-id="5afd9-111">たとえば、次のことを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-111">For example, you can choose to:</span></span>
    
  - <span data-ttu-id="5afd9-112">特定の期間のアイテムのみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="5afd9-112">Import only items of a certain age.</span></span>
    
  - <span data-ttu-id="5afd9-113">選択したメッセージの種類をインポートします。</span><span class="sxs-lookup"><span data-stu-id="5afd9-113">Import selected message types.</span></span>
    
  - <span data-ttu-id="5afd9-114">特定のユーザーによって送受信されたメッセージを除外します。</span><span class="sxs-lookup"><span data-stu-id="5afd9-114">Exclude messages sent or received by specific people.</span></span>
    
- <span data-ttu-id="5afd9-115">フィルター設定を構成した後、Office 365 は、インポートジョブで指定されたターゲットメールボックスにフィルター条件を満たすデータのみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="5afd9-115">After you configure the filter settings, Office 365 imports only the data that meets the filtering criteria to the target mailboxes specified in the import job.</span></span>
    
<span data-ttu-id="5afd9-116">次の図は、インテリジェントなインポート処理を示しており、実行するタスクと Office 365 によって実行されるタスクを強調表示しています。</span><span class="sxs-lookup"><span data-stu-id="5afd9-116">The following graphic shows the Intelligent Import process, and highlights the tasks you perform and the tasks performed by Office 365.</span></span>
  
![Office 365 のインテリジェントなインポートプロセス](media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="before-you-begin"></a><span data-ttu-id="5afd9-118">始める前に</span><span class="sxs-lookup"><span data-stu-id="5afd9-118">Before you begin</span></span>

- <span data-ttu-id="5afd9-119">このトピックの手順では、ネットワークアップロードまたはドライブ出荷を使用して、Office 365 インポートサービスに PST インポートジョブを作成したことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="5afd9-119">The steps in this topic assume that you've created a PST import job in the Office 365 Import service by using network upload or drive shipping.</span></span> <span data-ttu-id="5afd9-120">詳細な手順については、以下のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5afd9-120">For step-by-step instructions, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="5afd9-121">ネットワークアップロードを使用して Office 365 に PST ファイルをインポートする</span><span class="sxs-lookup"><span data-stu-id="5afd9-121">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
    
  - [<span data-ttu-id="5afd9-122">ドライブ送付を使用して PST ファイルを Office 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="5afd9-122">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- <span data-ttu-id="5afd9-123">ネットワークアップロードを使用してインポートジョブを作成した後、Security & コンプライアンスセンターの [インポート] ページのインポートジョブの状態が [**進行中**] に設定されていることを示します。これは、Office 365 がアップロードした PST ファイルのデータを分析していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5afd9-123">After you create an import job by using network upload, the status for the import job on the Import page in the Security & Compliance Center is set to **Analysis in progress**, which means that Office 365 is analyzing the data in the PST files that you uploaded.</span></span> <span data-ttu-id="5afd9-124">[更新の](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)更新] をクリックして、インポートジョブの状態を更新します。 \*\*\*\*![</span><span class="sxs-lookup"><span data-stu-id="5afd9-124">Click **Refresh**![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the status for the import job.</span></span> 
    
- <span data-ttu-id="5afd9-125">ドライブを送付するインポートジョブの場合、Microsoft データセンターの担当者がハードドライブを受け取って、PST ファイルを組織の Azure ストレージ領域にアップロードした後に、Office 365 によってデータが分析されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-125">For drive shipping import jobs, the data will be analyzed by Office 365 after Microsoft data center personnel receive your hard drive and upload the PST files to the Azure storage area for your organization.</span></span>
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a><span data-ttu-id="5afd9-126">メールボックスにインポートされるデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="5afd9-126">Filter data that gets imported to mailboxes</span></span>

<span data-ttu-id="5afd9-127">PST インポートジョブを作成したら、次の手順に従って、Office 365 にインポートする前にデータをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5afd9-127">After you've created a PST import job, follow these steps to filter the data before you import it to Office 365.</span></span>
  
1. <span data-ttu-id="5afd9-128">に[https://protection.office.com/](https://protection.office.com/)移動し、Office 365 組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="5afd9-128">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="5afd9-129">[**データガバナンス** \>の**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5afd9-129">Click **Data governance** \> **Import**.</span></span>
    
    <span data-ttu-id="5afd9-130">組織のインポートジョブが [**インポート**] ページに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-130">The import jobs for your organization are listed on the **Import** page.</span></span> <span data-ttu-id="5afd9-131">[**状態**] 列の [**分析完了**] の値は、Office 365 によって分析され、インポートの準備が整っているインポートジョブを示していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5afd9-131">Note that the **Analysis completed** value in the **Status** column indicates the import jobs that have been analyzed by Office 365 and are ready for you to import.</span></span> 
    
    ![分析の完了状態 Office 365 が PST ファイルのデータを分析したことを示します。](media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. <span data-ttu-id="5afd9-133">完了するインポートジョブについては、[準備完了] をクリックして**Office 365 にインポート**します。</span><span class="sxs-lookup"><span data-stu-id="5afd9-133">Click **Ready to import to Office 365** for the import job that you want to complete.</span></span> 
    
    <span data-ttu-id="5afd9-134">フライアウトページには、PST ファイルおよびインポートジョブに関するその他の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-134">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="5afd9-135">[ **Office 365 へのインポート] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="5afd9-135">Click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="5afd9-136">[**データをフィルター**する] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-136">The **Filter your data** page is displayed.</span></span> <span data-ttu-id="5afd9-137">このサイトには、データの保存期間に関する情報を含む、インポートジョブの PST ファイル内のデータに関するデータの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5afd9-137">It contains data insights about the data in the PST files for the import job, including information about the age of the data.</span></span> 
    
    ![[データをフィルターする] ページに、インポートジョブの PST ファイルのデータ分析情報が表示されます。](media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. <span data-ttu-id="5afd9-139">Office 365 にインポートされたデータをトリミングするかどうかに基づいて、[**データにフィルターを適用しますか?**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5afd9-139">Based on whether or not you want to trim the data that's imported to Office 365, under **Do you want to filter your data?**, do one of the following:</span></span>
    
    <span data-ttu-id="5afd9-140">a.</span><span class="sxs-lookup"><span data-stu-id="5afd9-140">a.</span></span> <span data-ttu-id="5afd9-141">[**はい、インポートする前にフィルターを適用**して、インポートしたデータをトリミングします] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5afd9-141">Click **Yes, I want to filter it before importing** to trim the data that you import, and then click **Next**.</span></span>
    
    <span data-ttu-id="5afd9-142">Office **365 へのデータのインポート**ページページに、office 365 が実行した分析からの詳細なデータ洞察が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-142">The **Import data to Office 365 page** page is displayed with detailed data insights from the analysis that Office 365 performed.</span></span> 
    
    ![Office 365 には、PST ファイルの分析から詳細なデータの洞察が表示されます。](media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    <span data-ttu-id="5afd9-144">このページのグラフには、インポートされるデータの量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-144">The graph on this page shows the amount of data that will be imported.</span></span> <span data-ttu-id="5afd9-145">PST ファイルに含まれる各メッセージの種類に関する情報が、グラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-145">Information about each message type found in the PST files is displayed in the graph.</span></span> <span data-ttu-id="5afd9-146">各バーの上にカーソルを置くと、そのメッセージの種類に関する特定の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-146">You can hover the cursor over each bar to display specific information about that message type.</span></span> <span data-ttu-id="5afd9-147">また、PST ファイルの分析に基づいて、保存期間の値が異なるドロップダウンリストもあります。</span><span class="sxs-lookup"><span data-stu-id="5afd9-147">There is also a drop-down list with different age values based on the analysis of the PST files.</span></span> <span data-ttu-id="5afd9-148">ドロップダウンリストで年齢を選択すると、グラフが更新されて、選択した期間にインポートされるデータの量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-148">When you select an age in the drop-down list, the graph is updated to show how much data will be imported for the selected age.</span></span> 
    
    <span data-ttu-id="5afd9-149">b.</span><span class="sxs-lookup"><span data-stu-id="5afd9-149">b.</span></span> <span data-ttu-id="5afd9-150">追加フィルターを構成して、インポートされるデータの量を減らすには、[**その他のフィルターオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5afd9-150">To configure addition filters to reduce the amount of data that's imported, click **More filtering options**.</span></span>
    
    ![[その他のオプション] ページでフィルターを構成して、インポートされたデータをトリミングします。](media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    <span data-ttu-id="5afd9-152">これらのフィルターは、次のように構成できます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-152">You can configure these filters:</span></span>
    
      - <span data-ttu-id="5afd9-153">**Age** -年齢を選択すると、指定した期間より新しいアイテムのみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-153">**Age** - Select an age so only items that are newer than the specified age will be imported.</span></span> <span data-ttu-id="5afd9-154">Office 365 が**年齢**フィルターの年齢バケットを決定する方法については、「 [More information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5afd9-154">See the [More information](#more-information) section for a description about how Office 365 determines the age buckets for the **Age** filter.</span></span> 
    
      - <span data-ttu-id="5afd9-155">**種類**-このセクションには、インポートジョブの PST ファイルにあるすべてのメッセージの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-155">**Type** - This section shows all the message types that were found in the PST files for the import job.</span></span> <span data-ttu-id="5afd9-156">除外するメッセージの種類の横にあるチェックボックスをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-156">You can uncheck a box next to a message type that you want to exclude.</span></span> <span data-ttu-id="5afd9-157">他の種類のメッセージは除外できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5afd9-157">Note that you can't exclude the Other message type.</span></span> <span data-ttu-id="5afd9-158">他のカテゴリに含まれるメールボックスアイテムの一覧については、「 [More information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5afd9-158">See the [More information](#more-information) section for a list of mailbox items that are included in the Other category.</span></span> 
    
      - <span data-ttu-id="5afd9-159">**ユーザー** -特定のユーザーが送信または受信したメッセージを除外することができます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-159">**Users** - You can exclude messages that are sent or received by specific people.</span></span> <span data-ttu-id="5afd9-160">メッセージの [差出人:] フィールド、[宛先] フィールド、または [Cc:] フィールドに表示されるユーザーを除外するには、その受信者の種類の横にある [**ユーザーを除外**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5afd9-160">To exclude people who appear in the From: field, To: field, or the Cc: field of messages, click **Exclude users** next to that recipient type.</span></span> <span data-ttu-id="5afd9-161">ユーザーの電子メールアドレス (SMTP アドレス) を入力し、 \*\*\*\*![[新しいアイコン](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)の追加] をクリックして、その受信者の種類の除外対象ユーザーの一覧に追加します。次に、[**保存**] をクリックして、除外されるユーザーの一覧を保存します。</span><span class="sxs-lookup"><span data-stu-id="5afd9-161">Type the email address (SMTP address) of the person, click **Add**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) to add them to the list of excluded users for that recipient type, and then click **Save** to save the list of excluded users.</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="5afd9-162">Office 365 は、**ユーザー**フィルターを設定することによって得られるデータ洞察を示していません。</span><span class="sxs-lookup"><span data-stu-id="5afd9-162">Office 365 doesn't show data insights that result from setting the **People** filter.</span></span> <span data-ttu-id="5afd9-163">ただし、特定のユーザーが送信または受信したメッセージを除外するようにこのフィルターを設定すると、実際のインポート処理中にこれらのメッセージは除外されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-163">However, if you set this filter to exclude messages sent or received by specific people, those messages will be excluded during the actual import process.</span></span> 
  
    <span data-ttu-id="5afd9-164">c.</span><span class="sxs-lookup"><span data-stu-id="5afd9-164">c.</span></span> <span data-ttu-id="5afd9-165">フィルターの設定を保存するには、[**その他のフィルターオプション**] ページの [**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5afd9-165">Click **Apply** in the **More filtering options** fly out page to save your filter settings.</span></span> 
    
    <span data-ttu-id="5afd9-166">[ **Office へのデータのインポート 365** ] ページのデータ分析は、フィルター設定に基づいてインポートされるデータの総量など、フィルター設定に基づいて更新されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-166">The data insights on the **Import data to Office 365** page are updated based on your filter settings, including the total amount of data that will be imported based on the filter settings.</span></span> <span data-ttu-id="5afd9-167">フィルター設定の概要も表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5afd9-167">Note that a summary of the filter settings is also shown.</span></span> <span data-ttu-id="5afd9-168">必要に応じて、フィルターの横にある [**編集**] をクリックして設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-168">You can click **Edit** next to a filter to change the setting if necessary.</span></span> 
    
    ![データ分析情報は、フィルター設定に基づいて更新されます。](media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    <span data-ttu-id="5afd9-170">d.</span><span class="sxs-lookup"><span data-stu-id="5afd9-170">d.</span></span> <span data-ttu-id="5afd9-171">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5afd9-171">Click **Next**.</span></span>
    
    <span data-ttu-id="5afd9-172">フィルター設定を示す状態ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-172">A status page is displayed showing your filter settings.</span></span> <span data-ttu-id="5afd9-173">この場合も、任意のフィルター設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-173">Again, you can edit any of the filter settings.</span></span>
    
    <span data-ttu-id="5afd9-174">e.</span><span class="sxs-lookup"><span data-stu-id="5afd9-174">e.</span></span> <span data-ttu-id="5afd9-175">[**データのインポート**] をクリックしてインポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="5afd9-175">Click **Import data** to start the import .</span></span> <span data-ttu-id="5afd9-176">インポートされるデータの合計量が表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5afd9-176">Note that the total amount of data that will be imported is displayed.</span></span> 
    
    <span data-ttu-id="5afd9-177">または</span><span class="sxs-lookup"><span data-stu-id="5afd9-177">Or</span></span>
    
    <span data-ttu-id="5afd9-178">a.</span><span class="sxs-lookup"><span data-stu-id="5afd9-178">a.</span></span> <span data-ttu-id="5afd9-179">[**いいえ、** PST ファイルのすべてのデータを Office 365 にインポートするためにすべてインポートします] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5afd9-179">Click **No, I want to import everything** to import all data in the PST files to Office 365, and then click **Next**.</span></span>
    
    <span data-ttu-id="5afd9-180">b.</span><span class="sxs-lookup"><span data-stu-id="5afd9-180">b.</span></span> <span data-ttu-id="5afd9-181">[ **Office へのデータのインポート 365** ] ページで、[**データのインポート**] をクリックしてインポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="5afd9-181">On the **Import data to Office 365** page, click **Import data** to start the import.</span></span> <span data-ttu-id="5afd9-182">インポートされるデータの合計量が表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5afd9-182">Note that the total amount of data that will be imported is displayed.</span></span> 
    
6. <span data-ttu-id="5afd9-183">[**インポート**] ページで、 \*\*\*\* ![[最新](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)の情報に更新] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5afd9-183">On the **Import** page, click **Refresh** ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png).</span></span> <span data-ttu-id="5afd9-184">インポートジョブの状態は、[**状態**] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-184">The status for the import job is displayed in the **Status** column.</span></span> 
    
7. <span data-ttu-id="5afd9-185">[ジョブのインポート] をクリックして、各 PST ファイルの状態、構成したフィルター設定などの詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="5afd9-185">Click the import the job to display more detailed information, such as the status for each PST file and the filter settings that you configured.</span></span>

  
## <a name="more-information"></a><span data-ttu-id="5afd9-186">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5afd9-186">More information</span></span>

- <span data-ttu-id="5afd9-187">Office 365 で年齢フィルターの増分を決定する方法</span><span class="sxs-lookup"><span data-stu-id="5afd9-187">How does Office 365 determine the increments for the age filter?</span></span> <span data-ttu-id="5afd9-188">Office 365 は、PST ファイルを分析するときに、各アイテムの送受信タイムスタンプを確認します (アイテムに送信および受信したタイムスタンプの両方がある場合は、最も古い日付が選択されます)。</span><span class="sxs-lookup"><span data-stu-id="5afd9-188">When Office 365 analyzes a PST file, it looks at the sent or received time stamp of each item (if an item has both a sent and received timestamp, the oldest date is selected).</span></span> <span data-ttu-id="5afd9-189">次に、Office 365 は、そのタイムスタンプの年の値を調べ、それを現在の日付と比較して、アイテムの保存期間を判断します。</span><span class="sxs-lookup"><span data-stu-id="5afd9-189">Then Office 365 looks at the year value for that timestamp and compares it to the current date to determine the age of the item.</span></span> <span data-ttu-id="5afd9-190">これらの年齢は、**年齢**フィルターのドロップダウンリストの値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="5afd9-190">These ages are then used as the values in the drop-down list for the **Age** filter.</span></span> <span data-ttu-id="5afd9-191">たとえば、PST ファイルに2016、2015、および2014のメッセージが含まれている場合、 **Age**フィルターの値は**1 年**、 **2 年**、 **3 年**になります。</span><span class="sxs-lookup"><span data-stu-id="5afd9-191">For example, if a PST file has messages from 2016, 2015, and 2014, then values in the **Age** filter would be **1 year**, **2 years**, and **3 years**.</span></span>
    
- <span data-ttu-id="5afd9-192">次の表に、[その他の**オプション**] フライアウトページの [フィルターの**種類**] で、**他の**カテゴリに含まれるメッセージの種類を示します (前の手順の手順5b を参照)。</span><span class="sxs-lookup"><span data-stu-id="5afd9-192">The following table lists the message types that are included in the **Other** category in the **Type** filter on the **More options** fly out page (see Step 5b in the previous procedure).</span></span> <span data-ttu-id="5afd9-193">現時点では、Pst を Office 365 にインポートするときに、"その他の" カテゴリのアイテムを除外することはできません。</span><span class="sxs-lookup"><span data-stu-id="5afd9-193">Currently, you can't exclude items in the "Other" category when you import PSTs to Office 365.</span></span> 
    
    |<span data-ttu-id="5afd9-194">**メッセージ クラス ID**</span><span class="sxs-lookup"><span data-stu-id="5afd9-194">**Message class ID**</span></span>|<span data-ttu-id="5afd9-195">**このメッセージクラスを使用するメールボックスアイテム**</span><span class="sxs-lookup"><span data-stu-id="5afd9-195">**Mailbox items that use this message class**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5afd9-196">IPM.運用</span><span class="sxs-lookup"><span data-stu-id="5afd9-196">IPM.Activity</span></span>  <br/> |<span data-ttu-id="5afd9-197">履歴項目</span><span class="sxs-lookup"><span data-stu-id="5afd9-197">Journal entries</span></span>  <br/> |
    |<span data-ttu-id="5afd9-198">IPM.化</span><span class="sxs-lookup"><span data-stu-id="5afd9-198">IPM.Document</span></span>  <br/> |<span data-ttu-id="5afd9-199">ドキュメントとファイル (電子メールメッセージに添付されていない)</span><span class="sxs-lookup"><span data-stu-id="5afd9-199">Documents and files (not attached to an email message)</span></span>  <br/> |
    |<span data-ttu-id="5afd9-200">IPM.拡張子</span><span class="sxs-lookup"><span data-stu-id="5afd9-200">IPM.File</span></span>  <br/> |<span data-ttu-id="5afd9-201">(IPM と同じです。化</span><span class="sxs-lookup"><span data-stu-id="5afd9-201">(same as IPM.Document)</span></span>  <br/> |
    |<span data-ttu-id="5afd9-202">IPM.メモ: 通知</span><span class="sxs-lookup"><span data-stu-id="5afd9-202">IPM.Note.IMC.Notification</span></span>  <br/> |<span data-ttu-id="5afd9-203">インターネットメール接続によって送信されるレポート。インターネットへの Exchange サーバーゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="5afd9-203">Reports sent by Internet Mail Connect, which is the Exchange Server gateway to the Internet</span></span>  <br/> |
    |<span data-ttu-id="5afd9-204">IPM.注: Microsoft Fax</span><span class="sxs-lookup"><span data-stu-id="5afd9-204">IPM.Note.Microsoft.Fax</span></span>  <br/> |<span data-ttu-id="5afd9-205">Fax メッセージ</span><span class="sxs-lookup"><span data-stu-id="5afd9-205">Fax messages</span></span>  <br/> |
    |<span data-ttu-id="5afd9-206">IPM.注: Microsoft では、</span><span class="sxs-lookup"><span data-stu-id="5afd9-206">IPM.Note.Rules.Oof.Template.Microsoft</span></span>  <br/> |<span data-ttu-id="5afd9-207">不在時の自動応答メッセージ</span><span class="sxs-lookup"><span data-stu-id="5afd9-207">Out-of-office auto-reply messages</span></span>  <br/> |
    |<span data-ttu-id="5afd9-208">IPM.注 ReplyTemplate。</span><span class="sxs-lookup"><span data-stu-id="5afd9-208">IPM.Note.Rules.ReplyTemplate.Microsoft</span></span>  <br/> |<span data-ttu-id="5afd9-209">受信トレイルールによって送信された返信</span><span class="sxs-lookup"><span data-stu-id="5afd9-209">Replies sent by an inbox rule</span></span>  <br/> |
    |<span data-ttu-id="5afd9-210">IPM.OLE.クラス</span><span class="sxs-lookup"><span data-stu-id="5afd9-210">IPM.OLE.Class</span></span>  <br/> |<span data-ttu-id="5afd9-211">定期的なアイテムの例外</span><span class="sxs-lookup"><span data-stu-id="5afd9-211">Exceptions for a recurring series</span></span>  <br/> |
    |<span data-ttu-id="5afd9-212">IPM.取り消し。レポート</span><span class="sxs-lookup"><span data-stu-id="5afd9-212">IPM.Recall.Report</span></span>  <br/> |<span data-ttu-id="5afd9-213">メッセージ取り消しレポート</span><span class="sxs-lookup"><span data-stu-id="5afd9-213">Message recall reports</span></span>  <br/> |
    |<span data-ttu-id="5afd9-214">IPM.リモート</span><span class="sxs-lookup"><span data-stu-id="5afd9-214">IPM.Remote</span></span>  <br/> |<span data-ttu-id="5afd9-215">リモートメールメッセージ</span><span class="sxs-lookup"><span data-stu-id="5afd9-215">Remote mail messages</span></span>  <br/> |
    |<span data-ttu-id="5afd9-216">IPM.レポート</span><span class="sxs-lookup"><span data-stu-id="5afd9-216">IPM.Report</span></span>  <br/> |<span data-ttu-id="5afd9-217">アイテムの進捗レポート</span><span class="sxs-lookup"><span data-stu-id="5afd9-217">Item status reports</span></span>  <br/> |
