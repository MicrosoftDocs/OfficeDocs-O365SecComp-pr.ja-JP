---
title: 外部連絡先を Exchange Online に一括インポートする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: 管理者が Exchange Online PowerShell と CSV ファイルを使用して外部連絡先をグローバルアドレス一覧に一括インポートする方法について説明します。
ms.openlocfilehash: 08fe7666f03c7fe60555133292be9e27a9ffa413
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152209"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="e8bcc-103">外部連絡先を Exchange Online に一括インポートする</span><span class="sxs-lookup"><span data-stu-id="e8bcc-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="e8bcc-104">**この記事は、管理者を対象としています。連絡先を自分のメールボックスにインポートしようとしていますか?「 [Outlook に連絡先をインポートする」を](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)参照してください。**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="e8bcc-105">会社は、Exchange Online の共有アドレス帳 (グローバルアドレス一覧とも呼ばれます) に含める必要のある、多数の既存のビジネス用連絡先を所有していますか。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="e8bcc-106">外部の連絡先を、社内のユーザーと同様に、配布グループのメンバーとして追加しますか。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="e8bcc-107">その場合は、Exchange Online の PowerShell と CSV (コンマ区切り値) ファイルを使用して、外部連絡先を Exchange Online に一括インポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-107">If so, you can use Exchange Online PowerShell and a CSV (Comma Separated Value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="e8bcc-108">次の3つの手順からなるプロセスがあります。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="e8bcc-109">手順 1: 外部連絡先に関する情報を含む CSV ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="e8bcc-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="e8bcc-110">手順 2: PowerShell を使用して外部連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="e8bcc-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="e8bcc-111">手順 3: 外部連絡先のプロパティに情報を追加する</span><span class="sxs-lookup"><span data-stu-id="e8bcc-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="e8bcc-112">連絡先をインポートするための手順を完了したら、次の追加のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="e8bcc-113">外部連絡先を追加する</span><span class="sxs-lookup"><span data-stu-id="e8bcc-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="e8bcc-114">共有アドレス帳から外部連絡先を非表示にする</span><span class="sxs-lookup"><span data-stu-id="e8bcc-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="e8bcc-115">手順 1: 外部連絡先に関する情報を含む CSV ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="e8bcc-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="e8bcc-116">最初の手順として、Exchange Online にインポートする各外部連絡先に関する情報を含む CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="e8bcc-117">次のテキストをメモ帳のテキストファイルにコピーして、ファイル名サフィックス .csv を使用して、そのファイルを CSV ファイルとしてデスクトップに保存します。たとえば、ExternalContacts。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-117">Copy the following text to a text file in NotePad, and save it to your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e8bcc-118">言語に特殊文字 ( **å**、 **ä**、 **ö**など) が含まれている場合は、メモ帳でファイルを保存するときに、CSV ファイルを Utf-8 またはその他の Unicode エンコードで保存します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    <span data-ttu-id="e8bcc-119">CSV ファイルの最初の行、つまりヘッダー行には、Exchange Online にインポートするときに使用できる連絡先のプロパティが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="e8bcc-120">各プロパティ名はコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="e8bcc-121">ヘッダー行の下の各行は、1つの外部連絡先をインポートするためのプロパティ値を表します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e8bcc-122">このテキストには、サンプルデータが含まれています。これは削除できます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="e8bcc-123">ただし、最初の (ヘッダー) 行を削除または変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="e8bcc-124">これには、外部連絡先のすべてのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="e8bcc-125">Csv ファイルを編集するには、Excel を使用する方が簡単なため、Microsoft Excel で CSV ファイルを開いて編集してください。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="e8bcc-126">Exchange Online にインポートする連絡先ごとに行を作成します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="e8bcc-127">可能な限り多くのセルにデータを設定します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="e8bcc-128">この情報は、連絡先ごとに共有アドレス帳に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="e8bcc-129">外部連絡先を作成するには、次のプロパティ (見出し行の最初の4つの項目) が必要です。 **ExternalEmailAddress**、 **Name**、 **FIRSTNAME**、 **LastName**という CSV ファイルに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="e8bcc-130">手順2で実行した PowerShell コマンドは、これらのプロパティの値を使用して連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="e8bcc-131">手順 2: PowerShell を使用して外部連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="e8bcc-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="e8bcc-132">次の手順では、手順1および PowerShell で作成した CSV ファイルを使用して、CSV ファイルに記載されている外部連絡先を Exchange Online に一括インポートします。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="e8bcc-133">PowerShell を Exchange Online 組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="e8bcc-134">詳細な手順については、「 [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span> <span data-ttu-id="e8bcc-135">Exchange Online の PowerShell に接続するときは、必ず Office 365 のグローバル管理者アカウントのユーザー名とパスワードを使用してください。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-135">Be sure to use the user name and password for your Office 365 global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="e8bcc-136">PowerShell を Exchange Online に接続したら、手順1で CSV ファイルを保存したデスクトップフォルダーに移動します。例`C:\Users\Administrator\desktop`を示します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="e8bcc-137">外部連絡先を作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-137">Run the following command to create the external contacts:</span></span>

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="e8bcc-138">インポートしているユーザーの数によっては、新しい連絡先を作成するのに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="e8bcc-139">コマンドの実行が終了すると、作成された新しい連絡先の一覧が PowerShell に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="e8bcc-140">新しい外部連絡先を表示するには、Exchange 管理センター (EAC) に移動し、[**受信者** \>の**連絡先**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="e8bcc-141">EAC への接続手順については、「exchange [Online の exchange 管理センター](https://go.microsoft.com/fwlink/p/?LinkId=328197)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="e8bcc-142">必要に応じて\*\*\*\* ![、[最新](media/O365-MDM-Policy-RefreshIcon.gif)の情報に更新] アイコンをクリックしてリストを更新し、インポートされた外部連絡先を表示します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-142">If necessary, click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="e8bcc-143">インポートされた連絡先は、Outlook および web 上の Outlook の共有アドレス帳に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e8bcc-144">[**ユーザー** \>の**連絡先**] にアクセスして、Microsoft 365 管理センターで連絡先を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="e8bcc-145">手順 3: 外部連絡先のプロパティに情報を追加する</span><span class="sxs-lookup"><span data-stu-id="e8bcc-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="e8bcc-146">手順2でコマンドを実行した後、外部連絡先は作成されますが、CSV ファイルの大部分のセルからの情報である連絡先または組織の情報は含まれません。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from the most of the cells in the CSV file.</span></span> <span data-ttu-id="e8bcc-147">これは、新しい外部連絡先を作成したときに、必要なプロパティだけが設定されるためです。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="e8bcc-148">CSV ファイルに情報が入力されていない場合は、心配しないでください。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="e8bcc-149">含まれていない場合は追加されません。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="e8bcc-150">PowerShell を Exchange Online 組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="e8bcc-151">詳細な手順については、「 [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="e8bcc-152">手順1で CSV ファイルを保存したデスクトップフォルダーに移動します。例`C:\Users\Administrator\desktop`を示します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-152">Go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="e8bcc-153">次の2つのコマンドを実行して、CSV ファイルの他のプロパティを手順2で作成した外部連絡先に追加します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="e8bcc-154">_Manager_パラメーターに問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="e8bcc-155">CSV ファイル内のセルが空白の場合は、エラーが発生し、プロパティ情報が連絡先に追加されません。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="e8bcc-156">マネージャーを指定する必要がない場合は、前の` -Manager $_.Manager ` PowerShell コマンドからのみ削除してください。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="e8bcc-157">手順1でインポートした回数に応じて、連絡先を更新するのに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="e8bcc-158">プロパティが連絡先に追加されたことを確認するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="e8bcc-159">EAC で、[**受信者** \>の**連絡先**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="e8bcc-160">連絡先をクリックし、[ \*\*\*\* ![編集] 編集](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)アイコンをクリックして、連絡先のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-160">Click a contact and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="e8bcc-161">するだけです。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-161">That's it!</span></span> <span data-ttu-id="e8bcc-162">ユーザーは、アドレス帳 Outlook および Outlook on the web の連絡先とその他の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="e8bcc-163">外部連絡先を追加する</span><span class="sxs-lookup"><span data-stu-id="e8bcc-163">Add more external contacts</span></span>

<span data-ttu-id="e8bcc-164">手順1から手順3を繰り返して、Exchange Online に新しい外部連絡先を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="e8bcc-165">会社内のユーザーは、新しい連絡先の CSV ファイルに新しい行を追加するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="e8bcc-166">その後、手順2と手順3の PowerShell コマンドを実行して、新しい連絡先に情報を作成して追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e8bcc-167">新しい連絡先を作成するコマンドを実行すると、以前に作成した連絡先が既に存在するというエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="e8bcc-168">ただし、CSV ファイルに追加された新しい連絡先は作成されます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="e8bcc-169">共有アドレスから外部連絡先を非表示にする book></span><span class="sxs-lookup"><span data-stu-id="e8bcc-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="e8bcc-170">一部の企業では、配布グループのメンバーとして追加できるように外部連絡先のみを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="e8bcc-171">このシナリオでは、共有アドレス帳から外部連絡先を非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="e8bcc-172">次の操作を実行してください。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-172">Here's how:</span></span>
  
1.  <span data-ttu-id="e8bcc-173">PowerShell を Exchange Online 組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="e8bcc-174">詳細な手順については、「 [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="e8bcc-175">単一の外部連絡先を非表示にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-175">To hide a single external contact, run the following command.</span></span>
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    <span data-ttu-id="e8bcc-176">たとえば、共有アドレス帳から Pilar Pinilla を非表示にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. <span data-ttu-id="e8bcc-177">共有アドレス帳からすべての外部連絡先を非表示にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="e8bcc-178">非表示にした後も、外部の連絡先は共有アドレス帳に表示されませんが、配布グループのメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="e8bcc-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
