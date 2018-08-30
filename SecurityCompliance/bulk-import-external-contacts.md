---
title: Exchange Online に一括インポートの外部の連絡先
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: End User
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: 管理者は、Exchange のオンライン PowerShell を使用でき、一括して CSV ファイルは、グローバル アドレス一覧に外部の連絡先をインポートする方法について説明します。
ms.openlocfilehash: 4bde56d49ccf94dc91993df90e1ae693e25c961a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531637"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="074e6-103">Exchange Online に一括インポートの外部の連絡先</span><span class="sxs-lookup"><span data-stu-id="074e6-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="074e6-104">**この資料では、管理者用です。連絡先を自分のメールボックスにインポートしようとしていますか。[Outlook に連絡先をインポート](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="074e6-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="074e6-p101">会社は Exchange Online で共有のアドレス帳 (グローバル アドレス一覧とも呼ばれます) に追加する既存のビジネス用連絡先の多くをあるか。場合と同様のユーザーと、社内の配布グループのメンバーとして外部の連絡先を追加しますか。Exchange オンライン PowerShell と一括して CSV (コンマ区切り値) ファイルを使用するため場合、は、Exchange Online に外部の連絡先をインポートします。3 つの手順です。</span><span class="sxs-lookup"><span data-stu-id="074e6-p101">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online? Do you want to add external contacts as members of distribution groups, just like you can with users inside your company? If so, you can use Exchange Online PowerShell and a CSV (Comma Separated Value) file to bulk import external contacts into Exchange Online. It's a three-step process:</span></span>
  
[<span data-ttu-id="074e6-109">手順 1: 外部の連絡先に関する情報を含む CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="074e6-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="074e6-110">手順 2: PowerShell での外部の連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="074e6-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="074e6-111">手順 3: 外部の連絡先のプロパティに情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="074e6-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="074e6-112">連絡先をインポートするのには次の手順を完了したら、これらの追加タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="074e6-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="074e6-113">その他の外部の連絡先を追加します。</span><span class="sxs-lookup"><span data-stu-id="074e6-113">Add more external contacts</span></span>](bulk-import-external-contacts.md#AddMore)
  
- [<span data-ttu-id="074e6-114">共有のアドレス帳からの外部の連絡先を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="074e6-114">Hide external contacts from the shared address book</span></span>](bulk-import-external-contacts.md#Hide)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="074e6-115">手順 1: 外部の連絡先に関する情報を含む CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="074e6-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="074e6-116">最初のステップでは、オンラインの Exchange にインポートする各外部連絡先に関する情報を含む CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="074e6-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="074e6-117">メモ帳でテキスト ファイルに次のテキストをコピーし、デスクトップに保存して、CSV ファイルとして .csv のファイル名のサフィックスを使用して、たとえば、ExternalContacts.csv です。</span><span class="sxs-lookup"><span data-stu-id="074e6-117">Copy the following text to a text file in NotePad, and save it to your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="074e6-118">場合は、言語には、UTF-8、またはその他のエンコード方法はメモ帳でファイルを保存するときに CSV ファイルを保存 ( **å** **ä**、およびスウェーデン語の**ö** ) などの特殊文字が含まれています。</span><span class="sxs-lookup"><span data-stu-id="074e6-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    <span data-ttu-id="074e6-p102">最初の行、または CSV ファイルのヘッダー行は、オンラインの Exchange にインポートするときに使用できる連絡先のプロパティを一覧表示します。各プロパティ名は、コンマで区切られます。ヘッダー行の下の各行は、1 つの外部連絡先をインポートするためのプロパティの値を表します。</span><span class="sxs-lookup"><span data-stu-id="074e6-p102">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online. Each property name is separated by a comma. Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="074e6-p103">このテキストには、サンプル データ削除することにはが含まれています。削除したり、(ヘッダー) の最初の行を変更しないでください。すべての外部の連絡先のプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="074e6-p103">This text includes sample data, which you can delete. But don't delete or change the first (header) row. It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="074e6-125">CSV ファイルを編集するのには Excel を使用する方が簡単であるために、CSV ファイルを編集するのには Microsoft Excel で CSV ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="074e6-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="074e6-p104">オンラインの Exchange にインポートする連絡先ごとに行を作成します。多くの可能なセルとして設定します。この情報は、各連絡先の共有アドレス帳に表示されます。</span><span class="sxs-lookup"><span data-stu-id="074e6-p104">Create a row for each contact that you want to import to Exchange Online. Populate as many of the cells as possible. This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="074e6-p105">(見出し行の最初の 4 つの項目は、) 次のプロパティは、外部の連絡先を作成する必要があり、CSV ファイルに入力する必要があります: **ExternalEmailAddress**、**名**、**姓**、**姓**です。手順 2 で実行するための PowerShell コマンドは、連絡先を作成するのにこれらのプロパティの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="074e6-p105">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="074e6-131">手順 2: PowerShell での外部の連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="074e6-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="074e6-132">次の手順は、手順 1 で作成した CSV ファイルを使用して、一括に PowerShell が Exchange Online を CSV ファイルに記載されている外部の連絡先をインポートします。</span><span class="sxs-lookup"><span data-stu-id="074e6-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="074e6-p106">PowerShell は、オンラインの Exchange 組織に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)を参照してください。オンライン PowerShell を Exchange に接続するときに、Office 365 のグローバル管理者アカウントのユーザー名とパスワードを使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="074e6-p106">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Be sure to use the user name and password for your Office 365 global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="074e6-136">PowerShell を Exchange Online に接続した後は、手順 1 で保存した CSV ファイルのデスクトップ フォルダーに移動します。たとえば`C:\Users\Administrator\desktop`。</span><span class="sxs-lookup"><span data-stu-id="074e6-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="074e6-137">外部の連絡先を作成するのには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="074e6-137">Run the following command to create the external contacts:</span></span>

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="074e6-p107">インポートする多くの方法によって、新しい連絡先を作成するのにはしばらく時間がかかる場合があります。コマンドが完了するとこれを実行すると、PowerShell が表示されます作成された新しい連絡先の一覧です。</span><span class="sxs-lookup"><span data-stu-id="074e6-p107">It might take a while to create the new contacts, depending on how many you're importing. When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="074e6-140">新しい外部の連絡先を表示するには、Exchange 管理センター (EAC) に移動し、**受信者**をクリックし、 \> **の連絡先**です。</span><span class="sxs-lookup"><span data-stu-id="074e6-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="074e6-141">EAC に接続する方法の詳細については、 [Exchange 管理センター オンラインの Exchange](https://go.microsoft.com/fwlink/p/?LinkId=328197)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="074e6-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="074e6-142">**更新**] をクリックして、必要に応じて![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif)リストを更新し、インポートされた外部の連絡先を参照してください。</span><span class="sxs-lookup"><span data-stu-id="074e6-142">If necessary, click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="074e6-143">インポートされた連絡先は、Outlook と Outlook web 上で共有のアドレス帳に表示されます。</span><span class="sxs-lookup"><span data-stu-id="074e6-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="074e6-144">**ユーザー**に Office 365 の管理ページで、連絡先を表示することも\>**連絡先**です。</span><span class="sxs-lookup"><span data-stu-id="074e6-144">You can also view the contacts in the Office 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="074e6-145">手順 3: 外部の連絡先のプロパティに情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="074e6-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="074e6-p108">手順 2 でコマンドを実行した後、外部の連絡先が作成されるが、CSV ファイル内のセルのほとんどの情報は、取引先担当者や組織情報が含まれています。必要なプロパティのみを設定する新しい外部の連絡先を作成する場合があるためにです。気にしないですべての情報を CSV ファイルに入力する必要はありません。存在しない、する場合は追加されません。</span><span class="sxs-lookup"><span data-stu-id="074e6-p108">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from the most of the cells in the CSV file. This is because when you create new external contacts, only the required properties are populated. Don't worry if you don't have all the information populated in the CSV file. If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="074e6-p109">PowerShell は、オンラインの Exchange 組織に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="074e6-p109">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="074e6-152">CSV ファイルを手順 1 で保存したデスクトップのフォルダーに移動します。たとえば`C:\Users\Administrator\desktop`。</span><span class="sxs-lookup"><span data-stu-id="074e6-152">Go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="074e6-153">手順 2 で作成した外部の連絡先を CSV ファイルから他のプロパティを追加するのには次の 2 つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="074e6-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="074e6-p110">_マネージャー_のパラメーターは、問題が発生する可能性があります。CSV ファイル内のセルが空白の場合は、エラー メッセージが表示され、プロパティ情報は、連絡先に追加されます。マネージャーを指定する必要はありません場合、だけを削除して` -Manager $_.Manager `以前の PowerShell コマンドからです。</span><span class="sxs-lookup"><span data-stu-id="074e6-p110">The  _Manager_ parameter might be problematic. If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact. If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="074e6-157">もう一度、手順 1 でインポートした数に応じて、連絡先を更新するのにはしばらくかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="074e6-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="074e6-158">プロパティは、連絡先に追加されたことを確認するには。</span><span class="sxs-lookup"><span data-stu-id="074e6-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="074e6-159">**受信者**には、EAC で\>**の連絡先**です。</span><span class="sxs-lookup"><span data-stu-id="074e6-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="074e6-160">[連絡先] をクリックし、[**編集**] をクリックして![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)連絡先のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="074e6-160">Click a contact and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="074e6-p111">それです！ユーザーは、連絡先と Outlook のアドレス帳に追加の情報および web 上で Outlook に表示されます。</span><span class="sxs-lookup"><span data-stu-id="074e6-p111">That's it! Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="074e6-163">その他の外部の連絡先を追加します。</span><span class="sxs-lookup"><span data-stu-id="074e6-163">Add more external contacts</span></span>

<span data-ttu-id="074e6-p112">オンライン Exchange で新しい外部の連絡先を追加するのには手順 3 から手順 1 を繰り返します。や社内のユーザーでは、新しい連絡先を CSV ファイルに新しい行を追加できるだけです。作成し、新しい連絡先に情報を追加するには、手順 2 と手順 3 の PowerShell コマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="074e6-p112">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online. You or users in your company can just add a new row in the CSV file for the new contact. Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="074e6-p113">新しい連絡先を作成するコマンドを実行するときは、既に以前のバージョンで作成された連絡先が存在していることを示すエラーが出るでしょう。ですが、CSV ファイルに追加された新しい連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="074e6-p113">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist. But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="074e6-169">共有のアドレス帳からの外部の連絡先を非表示にする ></span><span class="sxs-lookup"><span data-stu-id="074e6-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="074e6-p114">一部の企業は、配布グループのメンバーとして追加できるようにだけ、外部の連絡先を使用できます。このシナリオでは、共有アドレス帳からの外部の連絡先を非表示にする場合があります。ここではどのようにします。</span><span class="sxs-lookup"><span data-stu-id="074e6-p114">Some companies may use external contacts only so they can be added as members of distribution groups. In this scenario, they may want to hide external contacts from the shared address book. Here's how:</span></span>
  
1.  <span data-ttu-id="074e6-p115">PowerShell は、オンラインの Exchange 組織に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="074e6-p115">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="074e6-175">1 つの外部連絡先を非表示にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="074e6-175">To hide a single external contact, run the following command.</span></span>
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    <span data-ttu-id="074e6-176">たとえば、Pilar Pinilla 共有アドレス帳から非表示にするには、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="074e6-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. <span data-ttu-id="074e6-177">共有のアドレス帳からのすべての外部の連絡先を非表示にするには、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="074e6-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="074e6-178">非表示にする、外部の連絡先は、共有アドレス帳に表示されていないが、配布グループのメンバーとして追加することができます。</span><span class="sxs-lookup"><span data-stu-id="074e6-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
