---
title: ネットワーク アップロードを使用して、RMS で暗号化された PST ファイルを Office 365 にインポートする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: ネットワークアップロードを使用して、RMS で暗号化された PST ファイルを Office 365 のユーザーメールボックスにインポートする方法について説明します。
ms.openlocfilehash: 8f08b17b5b975316afaf9545d5ba42057f35deca
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296580"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a><span data-ttu-id="409eb-103">ネットワーク アップロードを使用して、RMS で暗号化された PST ファイルを Office 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="409eb-103">Use network upload to import RMS-encrypted PST files to Office 365</span></span>

<span data-ttu-id="409eb-104">**この記事は、管理者を対象としています。PST ファイルを自分のメールボックスにインポートしようとしていますか?「 [Outlook .pst ファイルからメール、連絡先、予定表をインポートする](https://go.microsoft.com/fwlink/p/?LinkID=785075)」を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="409eb-104">**This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span></span>
   
<span data-ttu-id="409eb-p101">ユーザーのメールボックスに PST ファイルをインポートするには、ネットワークアップロードオプションと Office 365 インポートサービスを使用します。ネットワークのアップロードとは、PST ファイルを Microsoft クラウドの一時的なストレージ領域としてアップロードすることを意味します。その後、Office 365 インポートサービスは、PST ファイルをストレージ領域からターゲットユーザーのメールボックスにコピーします。インポートサービスの新機能により、PST ファイルを暗号化して Microsoft クラウドに保存することができます。これらのファイルは、ユーザーのメールボックスにインポートするときに暗号化が解除されます。</span><span class="sxs-lookup"><span data-stu-id="409eb-p101">Use the network upload option and the Office 365 Import service to import PST files to user mailboxes. Network upload means that you upload the PST files a temporary storage area in the Microsoft cloud. Then the Office 365 Import service copies the PST files from the storage area to the target user mailboxes. A new feature of the Import service lets you encrypt your PST files before they are uploaded and stored on the Microsoft cloud. These files will be un-encrypted when they're imported to user mailboxes.</span></span> 
  
<span data-ttu-id="409eb-110">PST ファイルを暗号化して Office 365 メールボックスにインポートするために必要な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="409eb-110">Here are the steps required to encrypt and import PST files to Office 365 mailboxes:</span></span>
  
[<span data-ttu-id="409eb-111">手順 1:PST インポートの Azure Rights Management をセットアップする </span><span class="sxs-lookup"><span data-stu-id="409eb-111">Step 1: Set up Azure Rights Management for PST Import</span></span>](#step-1-set-up-azure-rights-management-for-pst-import)

[<span data-ttu-id="409eb-112">手順 2:PST インポートの暗号化キーを生成する</span><span class="sxs-lookup"><span data-stu-id="409eb-112">Step 2: Generate an encryption key for PST Import</span></span>](#step-2-generate-an-encryption-key-for-pst-import)

[<span data-ttu-id="409eb-113">手順 3: RMS テナント ID とライセンス URL を取得する</span><span class="sxs-lookup"><span data-stu-id="409eb-113">Step 3: Obtain RMS tenant ID and licensing URL</span></span>](#step-3-obtain-rms-tenant-id-and-licensing-url)

[<span data-ttu-id="409eb-114">手順 4: PST インポートツールをダウンロードして、SAS URL をコピーする</span><span class="sxs-lookup"><span data-stu-id="409eb-114">Step 4: Download the PST Import tools and copy the SAS URL</span></span>](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[<span data-ttu-id="409eb-115">手順 5: PST ファイルを暗号化して Office 365 にアップロードする</span><span class="sxs-lookup"><span data-stu-id="409eb-115">Step 5: Encrypt and upload your PST files to Office 365</span></span>](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[<span data-ttu-id="409eb-116">オプション手順 6: Office 365 にアップロードされた PST ファイルの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="409eb-116">(Optional) Step 6: View a list of the PST files uploaded to Office 365</span></span>](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[<span data-ttu-id="409eb-117">手順 7: PST インポートのマッピングファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="409eb-117">Step 7: Create the PST Import mapping file</span></span>](#step-7-create-the-pst-import-mapping-file)

[<span data-ttu-id="409eb-118">手順 8:Office 365 で PST インポート ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="409eb-118">Step 8: Create a PST Import job in Office 365</span></span>](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> <span data-ttu-id="409eb-p102">PST ファイルを暗号化して Office 365 メールボックスにインポートするように組織を設定および構成するには、手順 1 ~ 4 を一度だけ実行する必要があります。これらの手順を実行した後、PST ファイルのバッチを暗号化、アップロード、およびインポートするたびに、手順5から手順8に従います。</span><span class="sxs-lookup"><span data-stu-id="409eb-p102">You have to perform Step 1 through Step 4 only once to set up and configure your organization to encrypt and import PST files to Office 365 mailboxes. After you perform these steps, follow Step 5 through Step 8 each time you want to encrypt, upload, and import a batch of PST files.</span></span> 
  
<span data-ttu-id="409eb-121">office 365 へのデータのインポートの詳細については、「[組織の PST ファイルを office 365 にインポートする」の概要](importing-pst-files-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-121">For more information about importing data to Office 365, see [Overview of importing your organization PST files to Office 365](importing-pst-files-to-office-365.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="409eb-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="409eb-122">Before you begin</span></span>

- <span data-ttu-id="409eb-p103">PST ファイルを Office 365 メールボックスにインポートするには、Exchange Online でメールボックスのインポートのエクスポートの役割を割り当てられている必要があります。既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。[組織の管理] 役割グループに、メールボックスのインポートのエクスポートの役割を追加できます。または、新しい役割グループを作成し、メールボックスのインポートのエクスポート役割を割り当てて、自分をメンバーとして追加することもできます。詳細については、「 [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688)」の「役割グループに役割を追加する」または「役割グループを作成する」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p103">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
    
    <span data-ttu-id="409eb-128">さらに、Office 365 セキュリティ&amp;コンプライアンスセンターでインポートジョブを作成するには、次のいずれかの条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="409eb-128">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
    
  - <span data-ttu-id="409eb-p104">Exchange Online では、メール受信者の役割が割り当てられている必要があります。既定では、この役割は組織の管理役割グループと受信者管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="409eb-p104">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="409eb-131">または</span><span class="sxs-lookup"><span data-stu-id="409eb-131">Or</span></span>
    
  - <span data-ttu-id="409eb-132">Office 365 組織の全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="409eb-132">You have to be a global administrator in your Office 365 organization.</span></span>
    
  > [!TIP]
  > <span data-ttu-id="409eb-p105">Office 365 に PST ファイルをインポートするための特別な目的である Exchange Online に新しい役割グループを作成することを検討してください。PST ファイルのインポートに必要な最低限の特権レベルについては、メールボックスのインポートの役割とメール受信者の役割を新しい役割グループに割り当ててから、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="409eb-p105">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
- <span data-ttu-id="409eb-p106">Office 365 にインポートする PST ファイルは、組織内のファイルサーバーまたは共有フォルダーに格納する必要があります。手順5では、office 365 importtool を実行して、このファイルサーバーまたは共有フォルダーに保存されている PST ファイルを office 365 に暗号化してアップロードします。</span><span class="sxs-lookup"><span data-stu-id="409eb-p106">You need to store the PST files that you want to import to Office 365 on a file server or shared folder in your organization. In Step 5, you'll run the Office 365 ImportTool, which will encrypt and upload the PST files that are stored on this file server or shared folder to Office 365.</span></span>
    
- <span data-ttu-id="409eb-p107">この手順では、暗号化キー、ストレージキー、およびいくつかの識別キーと url のコピーをコピーして保存します。この情報は、手順5で PST ファイルを暗号化してアップロードするために使用されます。パスワードやその他のセキュリティ関連の情報を保護するのと同じように、これらを保護するための予防措置を講じるようにしてください。たとえば、パスワードで保護された Microsoft Word 文書に保存するか、暗号化された USB ドライブに保存することができます。これらのキー、id、および url の例については、「 [More information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p107">This procedure involves copying and saving a copy of an encryption key, a storage key, and a number of identification keys and URLs. This information will be used in Step 5 to encrypt and upload your PST files. Be sure to take precautions to protect these just like you would protect passwords or other security-related information. For example you might save them to a password-protected Microsoft Word document or save them to an encrypted USB drive. See the [More information](#more-information) section for an example of these keys, IDs, and URLs.</span></span> 
    
- <span data-ttu-id="409eb-p108">Office 365 の非アクティブなメールボックスに PST ファイルをインポートすることができます。これを行うには、PST インポートマッピングファイルの`Mailbox`パラメーターに非アクティブなメールボックスの GUID を指定します。詳細については、[手順 7](#step-7-create-the-pst-import-mapping-file)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p108">You can import PST files to an inactive mailbox in Office 365. You do this by specifying the GUID of the inactive mailbox in the  `Mailbox` parameter in the PST Import mapping file. See [Step 7](#step-7-create-the-pst-import-mapping-file) for more information.</span></span> 
    
- <span data-ttu-id="409eb-p109">Exchange ハイブリッド展開では、プライマリメールボックスがオンプレミスであるユーザーのクラウドベースのアーカイブメールボックスに PST ファイルをインポートできます。これを行うには、PST インポートマッピングファイルで以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="409eb-p109">In an Exchange hybrid deployment, you can import PST files to a cloud-based archive mailbox for a user whose primary mailbox is on-premises. You do this by doing the following in the PST Import mapping file:</span></span>
    
  - <span data-ttu-id="409eb-147">`Mailbox`パラメーターに、ユーザーの社内メールボックスの電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="409eb-147">Specify the email address for the user's on-premises mailbox in the  `Mailbox` parameter.</span></span> 
    
  - <span data-ttu-id="409eb-148">`IsArchive`パラメーターに**TRUE**の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="409eb-148">Specify the **TRUE** value in the  `IsArchive` parameter.</span></span> 
    
    <span data-ttu-id="409eb-149">詳細については、[手順 7](#step-7-create-the-pst-import-mapping-file)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-149">See [Step 7](#step-7-create-the-pst-import-mapping-file) for more information.</span></span> 
    
- <span data-ttu-id="409eb-p110">PST ファイルが Office 365 メールボックスにインポートされると、メールボックスの保持ホールドの設定は無期限に有効になります。これは、メールボックスに割り当てられたアイテム保持ポリシーは、保存機能を無効にするか、保留を解除する日付を設定するまで処理されないことを意味します。なぜこれを行うのでしょうか。メールボックスにインポートされたメッセージが古くなっている場合は、メールボックスに対して構成されたアイテム保持ポリシーに基づいて保持期間が経過したために、削除 (パージ) される可能性があります。メールボックスの保存機能を有効にすると、メールボックスの所有者は新しくインポートされたメッセージを管理することができ、メールボックスの保存期間の設定を変更する時間を与えることができます。保持ホールドの管理に関する提案については、「 [More information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p110">After PST files are imported to an Office 365 mailbox, the retention hold setting for the mailbox is turned on for an indefinite duration. This means that the retention policy assigned to the mailbox won't be processed until you turn off the retention hold or set a date to turn off the hold. Why do we do this? If messages imported to a mailbox are old, they might be permanently deleted (purged) because their retention period has expired based on the retention settings configured for the mailbox. Placing the mailbox on retention hold will give the mailbox owner time to manage these newly-imported messages or give you time to change the retention settings for the mailbox. See the [More information](#more-information) section for suggestions about managing the retention hold.</span></span> 
    
- <span data-ttu-id="409eb-156">office 365 にアップロードする前に pst ファイルを暗号化する必要がない場合は、「[ネットワークアップロードを使用して pst ファイルを office 365 にインポート](use-network-upload-to-import-pst-files.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-156">If you don't need to encrypt your PST files before you upload them to Office 365, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
    
- <span data-ttu-id="409eb-157">ネットワークアップロードを使用して pst ファイルを office 365 にインポートする方法についてよく寄せられる質問については、「 [office 365 への pst ファイルのインポートに関する FAQ](faqimporting-pst-files-to-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-157">For frequently asked questions about using network upload to import PST files to Office 365, see [FAQ about importing PST files to Office 365](faqimporting-pst-files-to-office-365.md).</span></span>
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a><span data-ttu-id="409eb-158">手順 1:PST インポートの Azure Rights Management をセットアップする </span><span class="sxs-lookup"><span data-stu-id="409eb-158">Step 1: Set up Azure Rights Management for PST Import</span></span>

<span data-ttu-id="409eb-p111">PST インポートでは、Office 365 の azure Rights Management (azure RMS) サービスが提供する暗号化機能を使用します。これにより、Office 365 にアップロードする前に PST ファイルを暗号化することができます。</span><span class="sxs-lookup"><span data-stu-id="409eb-p111">PST Import uses the encryption functionality provided by the Azure Rights Management (Azure RMS) service in Office 365. This lets you to encrypt PST files before uploading them to Office 365.</span></span> 
  
<span data-ttu-id="409eb-161">PST インポート用に Azure RMS を構成するには、3つの手順から構成されます。</span><span class="sxs-lookup"><span data-stu-id="409eb-161">Configuring Azure RMS for PST Import consists of three steps:</span></span>
  
- [<span data-ttu-id="409eb-162">Azure RMS をアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="409eb-162">Activating Azure RMS</span></span>](#activate-azure-rms)
    
- [<span data-ttu-id="409eb-163">Exchange Online で RMS を構成する</span><span class="sxs-lookup"><span data-stu-id="409eb-163">Configuring RMS in Exchange Online</span></span>](#configure-rms-in-exchange-online)
    
- [<span data-ttu-id="409eb-164">Active Directory RMS クライアントのインストール</span><span class="sxs-lookup"><span data-stu-id="409eb-164">Installing the Active Directory RMS Client</span></span>](#install-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a><span data-ttu-id="409eb-165">Azure RMS をアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="409eb-165">Activating Azure RMS</span></span>

<span data-ttu-id="409eb-p112">Azure RMS は既定で無効になっていますが、組織内の別の管理者がライセンス認証を行った可能性があります。[azure Rights Management をアクティブ化](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)して azure DRM をインストールしてアクティブ化する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="409eb-p112">Azure RMS is disabled by default, but you or another administrator in your organization might have activated it. Follow instructions on [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service) to install and activate Azure DRM.</span></span>
  
### <a name="configuring-rms-in-exchange-online"></a><span data-ttu-id="409eb-168">Exchange Online で RMS を構成する</span><span class="sxs-lookup"><span data-stu-id="409eb-168">Configuring RMS in Exchange Online</span></span>

<span data-ttu-id="409eb-p113">Rights management サービスをアクティブ化した後、次の手順では、Azure RMS を使用するために Exchange Online で Information Rights Management (IRM) をセットアップします。詳細については、「 [Azure Rights Management を使用するように IRM を構成する](https://go.microsoft.com/fwlink/p/?LinkId=394816)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p113">After you've activated the Rights Management service, the next step is to set up Information Rights Management (IRM) in Exchange Online to use Azure RMS. For more information, see [Configure IRM to use Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=394816).</span></span>
  
1. <span data-ttu-id="409eb-171">[リモート PowerShell を使用して Exchange Online に接続](https://go.microsoft.com/fwlink/p/?LinkId=396554 )します。</span><span class="sxs-lookup"><span data-stu-id="409eb-171">[Connect to Exchange Online using Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554 ).</span></span>
    
2. <span data-ttu-id="409eb-172">次のコマンドを実行して、RMS キー共有 URL を設定する。</span><span class="sxs-lookup"><span data-stu-id="409eb-172">Run the following command to set the RMS key sharing URL.</span></span>
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    <span data-ttu-id="409eb-173">組織の場所の正しい RMS キー共有場所を決定するには、次の表を使用します。</span><span class="sxs-lookup"><span data-stu-id="409eb-173">Use the following table to determine the correct RMS key sharing location for the location of your organization.</span></span>
    
    |<span data-ttu-id="409eb-174">**場所**</span><span class="sxs-lookup"><span data-stu-id="409eb-174">**Location**</span></span>|<span data-ttu-id="409eb-175">**RMS キー共有場所**</span><span class="sxs-lookup"><span data-stu-id="409eb-175">**RMS key sharing location**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="409eb-176">North America</span><span class="sxs-lookup"><span data-stu-id="409eb-176">North America</span></span>  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="409eb-177">欧州連合</span><span class="sxs-lookup"><span data-stu-id="409eb-177">European Union</span></span>  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="409eb-178">アジア</span><span class="sxs-lookup"><span data-stu-id="409eb-178">Asia</span></span>  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="409eb-179">南アメリカ</span><span class="sxs-lookup"><span data-stu-id="409eb-179">South America</span></span>  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="409eb-180">行政機関向け Office 365 (行政機関のコミュニティ クラウド)</span><span class="sxs-lookup"><span data-stu-id="409eb-180">Office 365 for Government (Government Community Cloud)</span></span>  <br/> | <span data-ttu-id="409eb-181">`https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1-d</sup></span><span class="sxs-lookup"><span data-stu-id="409eb-181">`https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup></span></span> <br/> |
   
    > [!NOTE]
    > <span data-ttu-id="409eb-182"><sup>1</sup> Office 365 for government sku (government Community Cloud) を購入したお客様のみ、この RMS キー共有場所を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="409eb-182"><sup>1</sup> Only customers who have purchased Office 365 for Government SKUs (Government Community Cloud) should use this RMS key sharing location.</span></span> 
  
    <span data-ttu-id="409eb-183">たとえば、次のコマンドを実行すると、北米に配置されている顧客に対して Exchange online の RMS online キー共有場所が構成されます。</span><span class="sxs-lookup"><span data-stu-id="409eb-183">For example, this command configures the RMS Online key sharing location in Exchange Online for a customer located in North America.</span></span>
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. <span data-ttu-id="409eb-184">次のコマンドを実行して、信頼された発行ドメイン (TPD) を RMS Online から Office 365 組織にインポートします。</span><span class="sxs-lookup"><span data-stu-id="409eb-184">Run the following command to import a Trusted Publishing Domain (TPD) from RMS Online to your Office 365 organization.</span></span> 
    
    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    <span data-ttu-id="409eb-185">TPD には、PST ファイルの暗号化など、組織で RMS 機能を使用するために必要な設定が含まれています。 </span><span class="sxs-lookup"><span data-stu-id="409eb-185">A TPD contains the settings needed to use RMS features in your organization, including encrypting PST files.</span></span> 
    
4. <span data-ttu-id="409eb-186">次のコマンドを実行して、Office 365 組織の IRM を有効にします。</span><span class="sxs-lookup"><span data-stu-id="409eb-186">Run the following command to enable IRM for your Office 365 organization.</span></span>
    
    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a><span data-ttu-id="409eb-187">Active Directory RMS クライアントのインストール</span><span class="sxs-lookup"><span data-stu-id="409eb-187">Installing the Active Directory RMS Client</span></span>

<span data-ttu-id="409eb-p114">このセクションの最後の手順では、Rights Management Services (RMS) クライアント2.1 をダウンロードします。このソフトウェアは、azure rms へのアクセスを保護し、azure rms を使用するアプリケーションを介して流れる情報を保護します。 rms クライアントは、手順5で PST ファイルを暗号化してアップロードする際に使用するのと同じコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="409eb-p114">The last step in this section is to download the Rights Management Services (RMS) Client 2.1. This software helps protect access to Azure RMS and protects information flowing through applications that use Azure RMS. Install the RMS client on the same computer that you'll use to encrypt and upload PST files in Step 5.</span></span> 
  
1. <span data-ttu-id="409eb-191">[Rights Management サービスクライアント 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="409eb-191">Download [Rights Management Service Client 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396).</span></span>
    
2. <span data-ttu-id="409eb-192">Active Directory Rights Management サービス クライアント 2.1 ウィザードを実行して、クライアントをインストールする。</span><span class="sxs-lookup"><span data-stu-id="409eb-192">Run the Active Directory Rights Management Service Client 2.1 wizard to install the client.</span></span>

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a><span data-ttu-id="409eb-193">手順 2:PST インポートの暗号化キーを生成する</span><span class="sxs-lookup"><span data-stu-id="409eb-193">Step 2: Generate an encryption key for PST Import</span></span>

<span data-ttu-id="409eb-p115">Azure RMS をセットアップしたら、次の手順として、Office 365 にアップロードする PST ファイルを暗号化するために使用される暗号化キー (対称キーと呼ばれる) を生成します。これを行うには、Azure Active Directory のサービスプリンシパルとして PST インポートサービスを追加します。このアプリケーションをサービスプリンシパルとして追加すると、手順5で pst ファイルを暗号化して azure ストレージの場所にアップロードするときに、pst インポートサービスが azure Active Directory を直接認証できるようになります。</span><span class="sxs-lookup"><span data-stu-id="409eb-p115">After you've set up Azure RMS, the next step is to generate an encryption key (called a symmetric key) that will be used to encrypt the PST files that you upload to Office 365. You'll do this by adding the PST Import service as a service principal in Azure Active Directory. Adding this application as a service principal will allow the PST Import service to authenticate directly with Azure Active Directory when you upload encrypted the PST files to the Azure storage location in Step 5.</span></span>
  
1. <span data-ttu-id="409eb-197">Windows PowerShell の Azure Active Directory モジュールを開始します。</span><span class="sxs-lookup"><span data-stu-id="409eb-197">Start the Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="409eb-198">次のコマンドを実行して、Microsoft Online サービスに接続する。</span><span class="sxs-lookup"><span data-stu-id="409eb-198">Run the following command to connect to the Microsoft Online service.</span></span>
    
    ```
    Connect-MsolService
    ```

3. <span data-ttu-id="409eb-199">Office 365 組織の管理者アカウントの資格情報を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-199">Enter the credentials for an administrator account in your Office 365 organization, and then click **OK**.</span></span>
    
4. <span data-ttu-id="409eb-p116">次のコマンドを実行して、暗号化キー (対称キーと呼ばれる) を生成する。これを行うには、新しい PST 暗号化プリンシパルを作成します。</span><span class="sxs-lookup"><span data-stu-id="409eb-p116">Run the following command to generate an encryption key (call a symmetric key). You'll do this by creating a new PST Encryption Principal.</span></span>
    
    ```
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    <span data-ttu-id="409eb-202">システムには、新しい PST 暗号化プリンシパルの対称キーとプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="409eb-202">The system displays the symmetric key and the properties for the new PST Encryption Principal.</span></span>
    
    ![表示されている対称キーをコピーして保存する](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. <span data-ttu-id="409eb-p117">対称キーをテキスト ファイルまたは Word ファイルにコピーする。前述したように、必ずこのファイルを保護する予防策を講じてください。対称キーが表示されるのはこの時だけであるため、このウィンドウのスクリーンショットを撮り、同じファイルに保存することも検討してください。 </span><span class="sxs-lookup"><span data-stu-id="409eb-p117">Copy the symmetric key to a text or Word file. As previously stated, be sure to take precautions to protect this file. Because this is the only time that the symmetric key is displayed, you might also consider taking a screenshot of this window and saving it to the same file.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="409eb-p118">PST 暗号化プリンシパルの作成後は、**Get-MsolServicePrincipal** コマンドレットを使用して対称キーを取得することはできなくなります。このためキーを保存することが重要になります。</span><span class="sxs-lookup"><span data-stu-id="409eb-p118">After you create the PST Encryption Principal, you won't be able to retrieve the symmetric key by using the **Get-MsolServicePrincipal** cmdlet. That's why it's important to save the key.</span></span> 
  
<span data-ttu-id="409eb-p119">Windows PowerShell 用 Azure Active Directory モジュールを開いたままにして、Microsoft Online サービスに接続します。このウィンドウでは、次の手順でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="409eb-p119">Keep the Azure Active Directory Module for Windows PowerShell open and connected to the Microsoft Online service. You'll run a command in this window in the next step.</span></span>

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a><span data-ttu-id="409eb-211">手順 3: RMS テナント ID とライセンス URL を取得する</span><span class="sxs-lookup"><span data-stu-id="409eb-211">Step 3: Obtain RMS tenant ID and licensing URL</span></span>

<span data-ttu-id="409eb-p120">次の手順では、組織の Azure RMS サービスのテナント ID とライセンスの場所の URL を取得します。この情報をコピーして、手順2の対称キーを含む同じファイルに保存します。ID と URL は、手順5で PST ファイルを暗号化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="409eb-p120">The next step is to obtain the tenant ID and licensing location URL for the Azure RMS service for your organization. Copy and save this information to the same file that contains the symmetric key from Step 2. The ID and URL will be used in Step 5 to encrypt your PST files.</span></span>
  
1. <span data-ttu-id="409eb-215">(Microsoft Online service に接続されている) Windows PowerShell 用 azure Active Directory モジュールで、次のコマンドを実行して Office 365 組織の azure RMS サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="409eb-215">In the Azure Active Directory Module for Windows PowerShell (which is connected to the Microsoft Online service), run the following command to connect to the Azure RMS service in your Office 365 organization.</span></span>
    
    ```
    Connect-AadrmService 
    ```

2. <span data-ttu-id="409eb-216">Office 365 組織の管理者アカウントの資格情報を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-216">Enter the credentials for an administrator account in your Office 365 organization and then click **OK**.</span></span>
    
3. <span data-ttu-id="409eb-217">Office 365 組織の Azure RMS サービスのテナント ID を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="409eb-217">Run the following command to display the tenant ID for the Azure RMS service in your Office 365 organization.</span></span>
    
    ```
    Get-AadrmConfiguration | FL BPOSId
    ```

    <span data-ttu-id="409eb-218">`BPOSId`プロパティの値をコピーして保存します。</span><span class="sxs-lookup"><span data-stu-id="409eb-218">Copy and save the value for the  `BPOSId` property.</span></span> 
    
4. <span data-ttu-id="409eb-219">Azure RMS サービスのライセンスの場所を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="409eb-219">Run the following command to display the licensing location for your Azure RMS service.</span></span>
    
    ```
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    <span data-ttu-id="409eb-220">`LicensingIntranetDistributionPointUrl`プロパティの値をコピーして保存します。</span><span class="sxs-lookup"><span data-stu-id="409eb-220">Copy and save the value for the  `LicensingIntranetDistributionPointUrl` property.</span></span> 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a><span data-ttu-id="409eb-221">手順 4: PST インポートツールをダウンロードして、SAS URL をコピーする</span><span class="sxs-lookup"><span data-stu-id="409eb-221">Step 4: Download the PST Import tools and copy the SAS URL</span></span>

<span data-ttu-id="409eb-p121">Azure RMS を構成し、pst ファイルを暗号化するために必要な id を取得したので、次の手順では、手順5で実行するツールをダウンロードしてインストールし、pst ファイルを暗号化して Office 365 にアップロードします。これらのツールは、Azure azcopy ツールおよび Office 365 データ暗号化ツールです。組織の SAS URL もコピーします。この url は、組織のための Microsoft クラウド内の Azure ストレージの場所のネットワーク URL と、共有アクセス署名 (SAS) キーの組み合わせです。このキーは、Azure ストレージの場所に PST ファイルをアップロードするために必要なアクセス許可を提供します。手順2と手順3で、他の情報をコピーしたのと同じファイルに保存します。前述したように、SAS URL を保護するための予防措置を講じます。</span><span class="sxs-lookup"><span data-stu-id="409eb-p121">Now that you've configured Azure RMS and obtained the IDs necessary to encrypt PST files, the next step is to download and install the tools that you will run in Step 5 to encrypt and upload PST files to Office 365. These tools are the Azure AzCopy tool and the Office 365 Data Encryption tool. You'll also copy the SAS URL for your organization. This URL is a combination of the network URL for the Azure storage location in the Microsoft cloud for your organization and a Shared Access Signature (SAS) key. This key provides you with the necessary permissions to upload PST files to your Azure storage location. Save it to the same file that you've copied the other information to in Step 2 and Step 3. As previously stated, take precautions to protect the SAS URL.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="409eb-p122">azure のストレージの場所に PST ファイルを正常にアップロードするには、azure azcopy バージョン5.0 を使用する必要があります。新しいバージョンの azcopy ツールは、Office 365 に PST ファイルをインポートするためにサポートされていません。この手順の手順に従って、[**ネットワーク経由でファイルをアップロード**する] ページから azcopy ツールをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p122">You have to use Azure AzCopy version 5.0 to successfully upload PST files to the Azure storage location. Newer versions of the AzCopy tool aren't supported for importing PST files to Office 365. Be sure to download the AzCopy tool from the **Upload files over the network** page by following the procedures in this step.</span></span> 
  
1. <span data-ttu-id="409eb-232">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="409eb-232">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="409eb-233">office 365 組織の管理者アカウントの資格情報を使用して、office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="409eb-233">Sign in to Office 365 using the credentials for an administrator account in your Office 365 organization.</span></span>
    
3. <span data-ttu-id="409eb-234">左側のウィンドウで、[**データガバナンス**] をクリックし、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-234">In the left pane, click **Data governance** and then click **Import**.</span></span>
    
4. <span data-ttu-id="409eb-235">**[インポート]** ページで、**[インポート サービスに移動する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-235">On the **Import** page, click **Go to the Import service**.</span></span>
    
5. <span data-ttu-id="409eb-236">[ **Office へのデータのインポート 365** ] ページで、[**新しいジョブ** ![の追加] アイコン](media/ITPro-EAC-AddIcon.gif)をクリックし、[**電子メールメッセージ (PST ファイル) のアップロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-236">On the **Import data to Office 365** page, click **New job** ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then click **Upload email messages (PST files)**.</span></span>
    
6. <span data-ttu-id="409eb-237">[**ネットワーク経由でファイルをアップロード**する] ページの手順2で、[**ネットワークアップロード SAS URL を表示する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-237">On the **Upload files over the network** page, in step 2, click **Show network upload SAS URL**.</span></span>
    
7. <span data-ttu-id="409eb-p123">URL が表示されたら、それをコピーして、他のキーを保存したファイルに保存します。必ず URL 全体をコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p123">After the URL is displayed, copy it and save it in the file where you saved the other keys. Be sure to copy the entire URL.</span></span> 
    
8. <span data-ttu-id="409eb-240">手順3で、[ **azure azcopy ツールのダウンロード**] をクリックして、azure azcopy ツールをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="409eb-240">In step 3, click **Download the Azure AzCopy tool** to download and install the Azure AzCopy tool.</span></span> 
    
9. <span data-ttu-id="409eb-241">ポップアップ ウィンドウで、**[実行]** をクリックして、Azure AzCopy ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="409eb-241">In the pop-up window, click **Run** to install the Azure AzCopy tool.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="409eb-p124">必ず、64ビットの Windows を実行しているコンピューター `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`上の、既定の場所に Azure azcopy ツールをインストールしてください。これは、手順5で o365importtool.zip を実行したときに、この場所で azcopy ツールを検索するためです。</span><span class="sxs-lookup"><span data-stu-id="409eb-p124">Be sure to install the Azure AzCopy tool in the default location, which is `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy` on a computer running 64-bit Windows. That's because when you run the O365ImportTool.exe in Step 5, it looks for the AzCopy tool in this location.</span></span> 
  
10. <span data-ttu-id="409eb-244">Azure azcopy ツールをインストールした後、[ **Office 365 データ暗号化およびインポートツールをダウンロード**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-244">After you've installed the Azure AzCopy tool, click **Download the Office 365 Data Encryption and Import tool**.</span></span>
    
11. <span data-ttu-id="409eb-245">ポップアップウィンドウで、[名前を付け\*\*\*\* \> **て**保存] をクリックして、o365importtool.zip ファイルをローカルコンピューター上のフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="409eb-245">In the pop-up window, click **Save** \> **Save as** to save the O365ImportTool.zip file to a folder on your local computer.</span></span> 
    
12. <span data-ttu-id="409eb-246">O365ImportTool.zip ファイルを抽出する。</span><span class="sxs-lookup"><span data-stu-id="409eb-246">Extract the O365ImportTool.zip file.</span></span>
    
13. <span data-ttu-id="409eb-247">[**キャンセル**] をクリックして、[**ネットワーク経由でファイルをアップロード**する] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="409eb-247">Click **Cancel** to close the **Upload files over the network** page.</span></span> 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a><span data-ttu-id="409eb-248">手順 5: PST ファイルを暗号化して Office 365 にアップロードする</span><span class="sxs-lookup"><span data-stu-id="409eb-248">Step 5: Encrypt and upload your PST files to Office 365</span></span>

<span data-ttu-id="409eb-p125">手順 1 ~ 手順4を完了したら、o365importtool.zip ツールを使用して、PST ファイルを暗号化して Office 365 にアップロードすることができます。このツールは、PST ファイルを暗号化してから、Microsoft クラウド内の Azure ストレージの場所にアップロードして保存します。この手順を完了するには、組織内のファイル共有またはファイルサーバーに PST ファイルを配置する必要があります。これは、次の手順でソースディレクトリと呼ばれます。o365importtool.zip ツールを実行するたびに、別のソースディレクトリを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="409eb-p125">After you have completed Step 1 through Step 4, you're ready to use the O365ImportTool.exe tool to encrypt and upload PST files to Office 365. This tool encrypts your PST files and then uploads and stores them in an Azure storage location in the Microsoft cloud. To complete this step, the PST files have to be located in a file share or file server in your organization. This is known as the source directory in the following procedure. Each time you run the O365ImportTool.exe tool, you'll can specify a different source directory.</span></span> 
  
1. <span data-ttu-id="409eb-254">ローカル コンピューター上でコマンド プロンプトを開く。</span><span class="sxs-lookup"><span data-stu-id="409eb-254">Open a Command Prompt on your local computer.</span></span>
    
2. <span data-ttu-id="409eb-255">手順 4 で O365ImportTool.exe ツールをインストールしたディレクトリに移動する。</span><span class="sxs-lookup"><span data-stu-id="409eb-255">Go to the directory where you installed the O365ImportTool.exe tool in Step 4.</span></span>
    
3. <span data-ttu-id="409eb-256">次のコマンドを実行して、PST ファイルを暗号化して Office 365 にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="409eb-256">Run the following command to encrypt and upload PST files to Office 365.</span></span>
    
    ```
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    <span data-ttu-id="409eb-p126">次の表は、パラメーターとそれに必要な値を説明したものです。前の手順で取得した情報は、これらのパラメーターの値で使うことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p126">The following table describes the parameters and their required values. Note that the information you obtained in the previous steps is used in the values for these parameters.</span></span>
    
    |<span data-ttu-id="409eb-259">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="409eb-259">**Parameter**</span></span>|<span data-ttu-id="409eb-260">**説明**</span><span class="sxs-lookup"><span data-stu-id="409eb-260">**Description**</span></span>|<span data-ttu-id="409eb-261">**例**</span><span class="sxs-lookup"><span data-stu-id="409eb-261">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |<span data-ttu-id="409eb-262">Office 365 にアップロードされる PST ファイルを含む、組織内のソースディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="409eb-262">Specifies the source directory in your organization that contains the PST files that will be uploaded to Office 365.</span></span>  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |<span data-ttu-id="409eb-p127">Azure RMS サービスのライセンスの場所を指定します。手順3で取得し`LicensingIntranetDistributionPointUrl`たプロパティの値を使用します。このパラメーターの値は二重引用符 ("") で囲むようにしてください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p127">Specifies the licensing location for your Azure RMS service. Use the value of the  `LicensingIntranetDistributionPointUrl` property that you obtained in Step 3. Be sure to surround the value of this parameter with double-quotation marks (" ")  </span></span><br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |<span data-ttu-id="409eb-p128">Azure RMS 組織の id を指定します。手順3で取得し`BPOSId`たプロパティの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="409eb-p128">Specifies the identity of your Azure RMS organization. Use the value of the  `BPOSId` property that you obtained in Step 3.  </span></span><br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |<span data-ttu-id="409eb-p129">手順2で取得した対称キーを指定します。このパラメーターの値は二重引用符 ("") で囲むようにしてください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p129">Specifies the symmetric key that you obtained in Step 2. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |<span data-ttu-id="409eb-p130">PST ファイルをネットワーク経由でアップロードするか、ハードディスク上に送付するかを指定します。この値`upload`は、ネットワーク経由でファイルをアップロードしていることを示します。この値`drive`は、ハードドライブに pst を配布することを示します。</span><span class="sxs-lookup"><span data-stu-id="409eb-p130">Specifies whether you upload PST files over the network or ship them on a hard drive. The value  `upload` indicates that you are uploading the files over the network. The value  `drive` indicates that you are shipping the PSTs on a hard drive.  </span></span><br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |<span data-ttu-id="409eb-p131">PST ファイルのアップロード先となる Office 365 の送信先を指定します。これは、組織の Azure ストレージの場所です。このパラメーターの値は、手順4でコピーした SAS url からのネットワークアップロード URL で構成されます。このパラメーターの値は二重引用符 ("") で囲むようにしてください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p131">Specifies the destination in Office 365 where your PST files will be uploaded to; this is the Azure storage location for your organization. The value for this parameter consists of the network upload URL from the SAS URL that you copied in Step 4. Be sure to surround the value of this parameter with double-quotation marks (" ").  </span></span><br/><br/> <span data-ttu-id="409eb-p132">**ヒント:** オプション暗号化された PST ファイルをアップロードするために、Azure ストレージの場所にサブフォルダーを指定することができます。これを行うには、ネットワークアップロード URL にサブフォルダーの場所 ("ingestiondata" の後) を追加します。最初の例では、サブフォルダーを指定しません。これは、pst が Azure ストレージの場所のルート ( *ingestiondata*という名前) にアップロードされることを意味します。2番目の例では、PST ファイルを Azure ストレージの場所のサブフォルダー ( *encryptedpsts*という名前) にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="409eb-p132">**Tip:** (Optional) You can specify a subfolder in the Azure storage location to upload the encrypted PST files to. You do this by adding a subfolder location (after "ingestiondata") in the network upload URL. The first example doesn't specify a subfolder; that means the PSTs will be uploaded to the root (named  *ingestiondata*  ) of the Azure storage location. The second example uploads the PST files to a subfolder (named  *EncryptedPSTs*  ) in the Azure storage location.</span></span>           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> <span data-ttu-id="409eb-280">または</span><span class="sxs-lookup"><span data-stu-id="409eb-280">Or</span></span>  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |<span data-ttu-id="409eb-p133">組織の SAS キーを指定します。このパラメーターの値は、手順4でコピーした sas URL の sas キーで構成されます。SAS キーの最初の文字が疑問符 ("?") であることに注意してください。このパラメーターの値は二重引用符 ("") で囲むようにしてください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p133">Specifies the SAS key for you organization. The value for this parameter consists of the SAS key from the SAS URL that you copied in Step 4. Note that first character in the SAS key is a question mark ("?"). Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |<span data-ttu-id="409eb-285">このオプションスイッチは、o365importtool.zip ツールが、 `/srcdir:`パラメーターで指定されたソースディレクトリ内のサブフォルダーにある pst ファイルをコピーするように、再帰モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="409eb-285">This optional switch specifies the recursive mode so that the O365ImportTool.exe tool will copy PSTs files that are located in subfolders in the source directory that is specified by the  `/srcdir:` parameter.</span></span>  <br/><br/> <span data-ttu-id="409eb-p134">**注:** このスイッチを含めると、サブフォルダー内の PST ファイルは、アップロード後に、Azure ストレージの場所に別のファイルパス名を持つことになります。手順7で作成した CSV ファイルで、ファイルのパス名を正確に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="409eb-p134">**Note:** If you include this switch, PST files in subfolders will have a different file pathname in the Azure storage location after they're uploaded. You'll have to specify the exact file pathname in the CSV file that you create in Step 7.</span></span>           | `/recurse` <br/> |
   
    <span data-ttu-id="409eb-288">各パラメーターの実際の値を使用する O365ImportTool.exe ツールの構文の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="409eb-288">Here's an example of the syntax for the O365ImportTool.exe tool using actual values for each parameter:</span></span>
    
    ```
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    <span data-ttu-id="409eb-p135">コマンドを実行すると、PST ファイルの暗号化とアップロードの進行状況を示す状態メッセージが表示されます。最終の状態メッセージは、暗号化とアップロードが正常に完了したファイルの合計数を示しています。 </span><span class="sxs-lookup"><span data-stu-id="409eb-p135">After you run the command, status messages are displayed that show the progress of encrypting and uploading the PST files. A final status message shows the total number of files that were successfully encrypted and uploaded.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="409eb-p136">o365importtool.zip コマンドを正常に実行し、すべてのパラメーターが正しいことを確認した後、前の手順で取得した情報をコピーしたものと同じ (セキュリティで保護された) ファイルにコマンドライン構文のコピーを保存します。次に、o365importtool.zip ツールを実行して PST ファイルを暗号化して Office 365 にアップロードするたびに、このコマンドをコマンドプロンプトにコピーして貼り付けることができます。変更する必要があるのは、パラメーター `/srcdir:`と`/upload-dest:`パラメーターの値だけです。</span><span class="sxs-lookup"><span data-stu-id="409eb-p136">After you successfully run the O365ImportTool.exe command and verify that all the parameters are correct, save a copy of the command line syntax to the same (secured) file where you copied the information you obtained in the previous steps. Then you can copy and paste this command in a Command Prompt each time that you want to run the O365ImportTool.exe tool to encrypt and upload PST files to Office 365. The only values you might have to change are the ones for the  `/srcdir:` and  `/upload-dest:` parameters.</span></span> 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a><span data-ttu-id="409eb-294">オプション手順 6: Office 365 にアップロードされた PST ファイルの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="409eb-294">(Optional) Step 6: View a list of the PST files uploaded to Office 365</span></span>

<span data-ttu-id="409eb-p137">オプションの手順として、Microsoft azure ストレージエクスプローラー (無償のオープンソースツール) をインストールして使用し、azure blob にアップロードした PST ファイルの一覧を表示することができます。これを行うには、次の3つの適切な理由があります。</span><span class="sxs-lookup"><span data-stu-id="409eb-p137">As an optional step, you can install and use the Microsoft Azure Storage Explorer (which is a free, open source tool) to view the list of the PST files that you've uploaded to the Azure blob. There are three good reasons to do this:</span></span>
  
- <span data-ttu-id="409eb-297">組織内の共有フォルダーまたはファイルサーバーの PST ファイルが Azure blob に正常にアップロードされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="409eb-297">Verify that PST files from the shared folder or file server in your organization were successfully uploaded to the Azure blob.</span></span>

- <span data-ttu-id="409eb-p138">PST ファイルが暗号化されていることを確認します。暗号化された pst `.pfile`ファイルには、pst ファイル名に拡張子が付いています。たとえば、 `pilarp.pst.pfile`のようになります。</span><span class="sxs-lookup"><span data-stu-id="409eb-p138">Verify that the PST files are encrypted. Encrypted PST files have a  `.pfile` extension appended to the PST filename; for example,  `pilarp.pst.pfile`.</span></span>
    
- <span data-ttu-id="409eb-p139">Azure blob にアップロードされた各 PST ファイルのファイル名 (およびサブフォルダーが含まれている場合はそのパス名) を確認します。これは、次の手順で pst マッピングファイルを作成している場合に、各 pst ファイルのフォルダーパス名とファイル名の両方を指定する必要があるため、非常に役立ちます。これらの名前を確認すると、PST マッピングファイルの潜在的なエラーを減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="409eb-p139">Verify the filename (and the subfolder pathname if you included one) for each PST file uploaded to the Azure blob. This is really helpful when you're creating the PST mapping file in the next step because you have to specify both the folder pathname and filename for each PST file. Verifying these names can help reduce potential errors in your PST mapping file.</span></span>
    
<span data-ttu-id="409eb-303">Microsoft Azure ストレージエクスプローラーはプレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="409eb-303">The Microsoft Azure Storage Explorer is in Preview.</span></span> 
  
 > [!IMPORTANT]
>  <span data-ttu-id="409eb-p140">Azure ストレージエクスプローラーを使用して PST ファイルをアップロードまたは変更することはできません。PST ファイルを Office 365 にインポートするためにサポートされている唯一の方法は、azcopy を使用することです。また、Azure blob にアップロードした PST ファイルを削除することもできません。PST ファイルを削除しようとすると、必要なアクセス許可がないというエラーが表示されます。すべての PST ファイルが Azure ストレージ領域から自動的に削除されることに注意してください。進行中のインポートジョブがない場合は、最新のインポートジョブが作成されてから30日後に**ingestiondata**コンテナー内のすべての PST ファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="409eb-p140">You can't use the Azure Storage Explorer to upload or modify PST files. The only supported method for importing PST files to Office 365 is to use AzCopy. Also, you can't delete PST files that you've uploaded to the Azure blob. If you try to delete a PST file, you'll receive an error about not having the required permissions. Note that all PST files are automatically deleted from your Azure storage area. If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created.</span></span> 
  
<span data-ttu-id="409eb-310">azure ストレージエクスプローラーをインストールして azure ストレージ領域に接続するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="409eb-310">To install the Azure Storage Explorer and connect to your Azure storage area:</span></span>
  
1. <span data-ttu-id="409eb-311">[Microsoft Azure ストレージエクスプローラーツール](https://go.microsoft.com/fwlink/p/?LinkId=544842)をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="409eb-311">Download and install the [Microsoft Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span>
    
2. <span data-ttu-id="409eb-312">Microsoft Azure ストレージエクスプローラーを起動し、左側のウィンドウで [**ストレージアカウント**] を右クリックして、[ **Azure ストレージに接続] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-312">Start the Microsoft Azure Storage Explorer, right-click **Storage Accounts** in the left pane, and then click **Connect to Azure storage**.</span></span> 
    
    ![[ストレージアカウント] を右クリックし、[Azure ストレージへの接続] をクリックします。](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. <span data-ttu-id="409eb-314">[ **Azure ストレージへの接続**] のボックスで、手順4で取得した SAS URL を貼り付けて、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-314">In the box under **Connect to Azure storage**, paste the SAS URL that you obtained in Step 4, and then click **Next**.</span></span> 
    
    ![[Azure Storage への接続] ページのボックスに、SAS URL を貼り付けます。](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. <span data-ttu-id="409eb-316">[**接続の概要**] ページで、接続情報を確認し、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-316">On the **Connection summary** page, you can review the connection information, and then click **Connect**.</span></span> 
    
5. <span data-ttu-id="409eb-317">[**ストレージアカウント**] の下にある **(サービス SAS)** ノードを展開し、[ **Blob コンテナー** ] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="409eb-317">Under **Storage Accounts**, expand the **(Service SAS)** node, and then expand the **Blob Containers** node.</span></span> 
    
6. <span data-ttu-id="409eb-318">[ **ingestiondata**] を右クリックし、[ **Blob コンテナーエディターを開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-318">Right-click **ingestiondata**, and then click **Open Blob Container Editor**.</span></span>
    
    ![ingestiondata を右クリックし、[Blob コンテナー エディターを開く] をクリックする](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    <span data-ttu-id="409eb-320">手順5でアップロードした PST ファイルの一覧を含む Azure ストレージ領域が表示されます。</span><span class="sxs-lookup"><span data-stu-id="409eb-320">The Azure storage area, with a list of the PST files that you uploaded in Step 5 is displayed.</span></span>
    
    ![Azure ストレージ エクスプローラーには、アップロードした PST ファイルの一覧が表示される](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. <span data-ttu-id="409eb-p141">Microsoft azure ストレージエクスプローラーの使用が終了したら、[ **ingestiondata**] を右クリックし、 \*\*\*\* [切断] をクリックして azure ストレージ領域から切断します。そうしないと、次に接続しようとしたときにエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="409eb-p141">When you're finished using the Microsoft Azure Storage Explorer, right-click **ingestiondata**, and then click **Detach** to disconnect from your Azure storage area. Otherwise, you'll receive an error the next time you try to attach.</span></span> 
    
    ![ingestion を右クリックして [デタッチ] をクリックし、Azure のストレージ エリアから切断する](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a><span data-ttu-id="409eb-325">手順 7: PST インポートのマッピングファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="409eb-325">Step 7: Create the PST Import mapping file</span></span>

<span data-ttu-id="409eb-p142">pst ファイルが暗号化され、Office 365 組織の Azure ストレージの場所にアップロードされたら、次の手順では、pst ファイルをインポートするユーザーのメールボックスを指定するコンマ区切り値 (CSV) ファイルを作成します。PST インポートジョブを作成する場合は、次の手順でこの CSV ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="409eb-p142">After the PST files have been encrypted and uploaded to the Azure storage location for your Office 365 organization, the next step is to create a comma separated value (CSV) file that specifies which user mailboxes the PST files will be imported to. You will submit this CSV file in the next step when you create a PST Import job.</span></span>
  
1. <span data-ttu-id="409eb-328">[PST インポートのマッピングファイルのコピーをダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=544717)します。</span><span class="sxs-lookup"><span data-stu-id="409eb-328">[Download a copy of the PST Import mapping file](https://go.microsoft.com/fwlink/p/?LinkId=544717).</span></span> 
    
2. <span data-ttu-id="409eb-p143">CSV ファイルを開くか、ローカル コンピューターに保存します。次の例は、完了した PST インポートのマッピング ファイル (メモ帳で開いた) を示しています。Microsoft Excel を使って CSV ファイルを編集するほうが、はるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="409eb-p143">Open or save the CSV file to your local computer. The following example shows a completed PST Import mapping file (opened in NotePad). It's much easier to use Microsoft Excel to edit the CSV file.</span></span>
    
    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst.pfile,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst.pfile,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,donh.pst.pfile,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst.pfile,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,pilarp.pst.pfile,pilarp@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,pilarp_archive.pst.pfile,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,tonyk.pst.pfile,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,tonyk_archive.pst.pfile,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,zrinkam.pst.pfile,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,zrinkam_archive.pst.pfile,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```

    <span data-ttu-id="409eb-p144">CSV ファイルの最初の行、つまりヘッダー行には、pst ファイルをユーザーメールボックスにインポートするために pst インポートサービスによって使用されるパラメーターが一覧表示されます。各パラメーター名はコンマで区切ります。ヘッダー行の下の各行は、特定のメールボックスに PST ファイルをインポートするためのパラメーター値を表します。ユーザーのメールボックスにインポートする PST ファイルごとに1つの行が必要になります。マッピングファイルのプレースホルダーデータを実際のデータに置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p144">The first row, or header row, of the CSV file lists the parameters that will be used by the PST Import service to import the PST files to user mailboxes. Each parameter name is separated by a comma. Each row under the header row represents the parameter values for importing a PST file to a specific mailbox. You will need a row for each PST file that you want to import to a user mailbox. Be sure to replace the placeholder data in the mapping file with your actual data.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="409eb-337">SharePoint パラメーターなど、ヘッダー行は何も変更しないでください。これらは PST インポートの処理中、無視されます。</span><span class="sxs-lookup"><span data-stu-id="409eb-337">Don't change anything in the header row, including the SharePoint parameters; they will be ignored during the PST Import process.</span></span> 
  
3. <span data-ttu-id="409eb-338">次の表の情報を使って、必要な情報を含む CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="409eb-338">Use the information in the following table to populate the CSV file with the required information.</span></span>
    
    |<span data-ttu-id="409eb-339">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="409eb-339">**Parameter**</span></span>|<span data-ttu-id="409eb-340">**説明**</span><span class="sxs-lookup"><span data-stu-id="409eb-340">**Description**</span></span>|<span data-ttu-id="409eb-341">**例**</span><span class="sxs-lookup"><span data-stu-id="409eb-341">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `Workload` <br/> |<span data-ttu-id="409eb-p145">データのインポート先となる Office 365 サービスを指定します。PST ファイルをユーザーのメールボックスにインポート`Exchange`するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="409eb-p145">Specifies the Office 365 service that data will be imported to. To import PST files to user mailboxes, use  `Exchange`.  </span></span><br/> | `Exchange` <br/> |
    | `FilePath` <br/> |<span data-ttu-id="409eb-344">手順5で PST ファイルをアップロードした Azure ストレージの場所でのフォルダーの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="409eb-344">Specifies the folder location in the Azure storage location that you uploaded the PST files to in Step 5.</span></span>  <br/>  <span data-ttu-id="409eb-p146">手順5の`/upload-dest:`パラメーターに、ネットワーク URL にオプションのサブフォルダー名を含めなかった場合は、CSV ファイルでこのパラメーターを空白のままにしておきます。サブフォルダー名を含める場合は、このパラメーターで指定します。このパラメーターの値は、大文字と小文字を区別します。どちらの方法\*\* でも、 `FilePath`パラメーターの値に "ingestiondata" を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p146">If you didn't include an optional subfolder name in the network URL in the  `/upload-dest:` parameter in Step 5, leave this parameter blank in the CSV file. If you included a subfolder name, specify it in this parameter. The value for this parameter is case sensitive. Either way,  *don't*  include "ingestiondata" in the value for the  `FilePath` parameter.  </span></span><br/> <br/><span data-ttu-id="409eb-p147">**重要:** ファイルパス名の大文字と小文字は、手順5で`/upload-dest:`パラメーターの SAS URL にオプションのサブフォルダ名を含めた場合に使用したものと同じである必要があります。たとえば、手順5でサブ`EncryptedPSTs`フォルダー名を使用し、CSV ファイルの`encryptedpsts` `FilePath`パラメーターでを使用した場合、PST ファイルのインポートは失敗します。両方のインスタンスで同じケースを使用してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p147">**Important:** The case for the file path name must be the same case that you used if you included an optional subfolder name in the SAS URL in the  `/upload-dest:` parameter in Step 5. For example, if you used  `EncryptedPSTs` for the subfolder name in Step 5 and then use  `encryptedpsts` in the  `FilePath` parameter in CSV file, the import for the PST file will fail. Be sure to use the same case in both instances.</span></span>           |<span data-ttu-id="409eb-352">(空白)</span><span class="sxs-lookup"><span data-stu-id="409eb-352">(leave blank)</span></span>  <br/> <span data-ttu-id="409eb-353">または</span><span class="sxs-lookup"><span data-stu-id="409eb-353">Or</span></span>  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |<span data-ttu-id="409eb-p148">ユーザーメールボックスにインポートされる PST ファイルの名前を指定します。このパラメーターの値は、大文字と小文字を区別します。Azure ストレージの場所にアップロードされる pst ファイルは暗号化されるため、 `.pfile` pst ファイル名に拡張子が追加されます。CSV ファイルの PST `.pfile`ファイルの名前に拡張機能を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="409eb-p148">Specifies the name of the PST file that will be imported to the user mailbox. The value for this parameter is case sensitive. Because the PST files that are uploaded to the Azure storage location are encrypted, a  `.pfile` extension is added to the PST filename. You must add the  `.pfile` extension to the name of the PST files in the CSV file.  </span></span><br/><br/> <span data-ttu-id="409eb-p149">**重要:** CSV ファイルの pst ファイル名の大文字と小文字は、手順5で Azure ストレージの場所にアップロードされた pst ファイルと同じである必要があります。たとえば、CSV ファイルの`annb.pst.pfile` `Name`パラメーターでを使用していて、実際の pst ファイルの名前が`AnnB.pst`である場合、その pst ファイルのインポートは失敗します。CSV ファイルの pst の名前では、実際の pst ファイルと同じ大文字と小文字が使用されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p149">**Important:** The case for the PST file name in the CSV file must be the same as the PST file that was uploaded to the Azure storage location in Step 5. For example, if you use  `annb.pst.pfile` in the  `Name` parameter in the CSV file, but the name of the actual PST file is  `AnnB.pst`, the import for that PST file will fail. Be sure that the name of the PST in the CSV file uses the same case as the actual PST file.</span></span>           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |<span data-ttu-id="409eb-361">PST ファイルのインポート先になるメールボックスのメール アドレスを指定します。 </span><span class="sxs-lookup"><span data-stu-id="409eb-361">Specifies the email address of the mailbox that the PST file will be imported to.</span></span>  <br/> <span data-ttu-id="409eb-p150">非アクティブなメールボックスに PST ファイルをインポートするには、このパラメーターのメールボックス GUID を指定する必要があります。この GUID を取得するには、Exchange Online で次の PowerShell コマンドを実行します。`Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL Guid`</span><span class="sxs-lookup"><span data-stu-id="409eb-p150">To import a PST file to an inactive mailbox, you have to specify the mailbox GUID for this parameter. To obtain this GUID, run the following PowerShell command in Exchange Online:  `Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL Guid`</span></span> <br/><br/> <span data-ttu-id="409eb-p151">**注:** 場合によっては、1つのメールボックスがアクティブなメールボックスであり、もう一方のメールボックスが削除済み (非アクティブ) 状態になっているメールボックスが同じメールアドレスを持つ複数のメールボックスが存在することがあります。このような状況では、PST ファイルをインポートするメールボックスを一意に識別するメールボックス GUID を指定します。この GUID をアクティブなメールボックスに対して取得するには`Get-Mailbox - <identity of active mailbox> | FL Guid`、次の PowerShell コマンドを実行します。回復可能な削除 (または非アクティブ) のメールボックスの GUID を取得するには、次のコマンドを実行します。`Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`</span><span class="sxs-lookup"><span data-stu-id="409eb-p151">**Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox - <identity of active mailbox> | FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`</span></span>           | `annb@contoso.onmicrosoft.com` <br/> <span data-ttu-id="409eb-368">または</span><span class="sxs-lookup"><span data-stu-id="409eb-368">Or</span></span>  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | <span data-ttu-id="409eb-p152">PST ファイルをユーザーのアーカイブ メールボックスにインポートするかどうかを指定します。次のような 2 つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="409eb-p152">Specifies whether or not to import the PST file to the user's archive mailbox. There are two options:  </span></span><br/> <span data-ttu-id="409eb-371">**FALSE**PST ファイルをユーザーのプライマリメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="409eb-371">**FALSE** Imports the PST file to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="409eb-372">**TRUE**PST ファイルをユーザーのアーカイブメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="409eb-372">**TRUE** Imports the PST file to the user's archive mailbox.</span></span>  <br/>  <span data-ttu-id="409eb-373">このパラメーターを空白のままにすると、PST ファイルがユーザーのプライマリメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="409eb-373">If you leave this parameter blank, the PST file is imported to the user's primary mailbox.</span></span>  <br/><br/> <span data-ttu-id="409eb-374">**注:** プライマリメールボックスがオンプレミスであるユーザーのクラウドベースのアーカイブメールボックスに PST ファイルをインポートするには、このパラメーターに**TRUE**を指定し、 `Mailbox`パラメーターのユーザーの社内メールボックスの電子メールアドレスを指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="409eb-374">**Note:** To import a PST file to a cloud-based archive mailbox for a user whose primary mailbox is on-premises, just specify **TRUE** for this parameter and specify the email address for the user's on-premises mailbox for the  `Mailbox` parameter.</span></span>           | `FALSE` <br/> <span data-ttu-id="409eb-375">または</span><span class="sxs-lookup"><span data-stu-id="409eb-375">Or</span></span>  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | <span data-ttu-id="409eb-376">PST ファイルのインポート先メールボックスフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="409eb-376">Specifies the mailbox folder that the PST file is imported to.</span></span>  <br/>  <span data-ttu-id="409eb-377">このパラメーターを空白のままにした場合、PST はメールボックスのルートレベル (受信トレイフォルダーとその他の既定のメールボックスフォルダーと同じレベル) にある**インポート**された新しいフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="409eb-377">If you leave this parameter blank, the PST will be imported to a new folder named **Imported** located at the root level of the mailbox (the same level as the Inbox folder and the other default mailbox folders).</span></span>  <br/>  <span data-ttu-id="409eb-378">を指定`/`した場合、PST ファイル内のアイテムは、ユーザーの受信トレイフォルダーに直接インポートされます。</span><span class="sxs-lookup"><span data-stu-id="409eb-378">If you specify  `/`, items in the PST file will be imported directly in to the user's Inbox folder.</span></span>  <br/>  <span data-ttu-id="409eb-p153">を指定`/<foldername>`した場合、PST ファイルのアイテムは、 \* \<foldername\> \*という名前のサブフォルダーにインポートされます。たとえば、を使用`/ImportedPst`した場合、アイテムは**ImportedPst**という名前のサブフォルダーにインポートされます。このサブフォルダーは、ユーザーの受信トレイフォルダーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="409eb-p153">If you specify  `/<foldername>`, items in the PST file will be imported to a subfolder named  *\<foldername\>*  . For example, if you used  `/ImportedPst`, items would be imported to a subfolder named **ImportedPst**. This subfolder will be located in the user's Inbox folder.  </span></span><br/><br/> <span data-ttu-id="409eb-382">**ヒント:** pst ファイルのインポートに最適なフォルダーの場所を決定できるように、いくつかのテストバッチを実行して、このパラメーターを試してみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="409eb-382">**Tip:** Consider running a few test batches to experiment with this parameter so you can determine the best folder location to import PSTs files to.</span></span>           |<span data-ttu-id="409eb-383">(空白)</span><span class="sxs-lookup"><span data-stu-id="409eb-383">(leave blank)</span></span>  <br/> <span data-ttu-id="409eb-384">または</span><span class="sxs-lookup"><span data-stu-id="409eb-384">Or</span></span>  <br/>  `/` <br/> <span data-ttu-id="409eb-385">または</span><span class="sxs-lookup"><span data-stu-id="409eb-385">Or</span></span>  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |<span data-ttu-id="409eb-p154">このオプションパラメーターは、ANSI ファイル形式で PST ファイルをインポートするために使用するコードページの数値を指定します。このパラメーターは、中国語、日本語、および韓国語 (CJK) の組織から PST ファイルをインポートするために使用されます。これらの言語では、通常、文字エンコードに2バイト文字セット (DBCS) を使用します。メールボックスフォルダー名に DBCS を使用する言語の PST ファイルをインポートするためにこのパラメーターを使用していない場合は、インポート後にフォルダー名が正しくないことがよくあります。このパラメーターに使用することがサポートされている値の一覧については、「[コードページ識別子](https://go.microsoft.com/fwlink/p/?LinkId=328514)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p154">This optional parameter specifies a numeric value for the code page to use for importing PST files in the ANSI file format. This parameter is used for importing PST files from Chinese, Japanese, and Korean (CJK) organizations because these languages typically use a double byte character set (DBCS) for character encoding. If this parameter isn't used to import PST files for languages that use DBCS for mailbox folder names, the folder names are often garbled after they're imported. For a list of supported values to use for this parameter, see [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).  </span></span><br/><br/> <span data-ttu-id="409eb-p155">**注:** 前述したように、これはオプションのパラメーターであり、CSV ファイルに含める必要はありません。または、1つまたは複数の行の値を空白のままにしておくこともできます。</span><span class="sxs-lookup"><span data-stu-id="409eb-p155">**Note:** As previously stated, this is an optional parameter and you don't have to include it in the CSV file. Or you can include it and leave the value blank for one or more rows.</span></span>           |<span data-ttu-id="409eb-392">(空白)</span><span class="sxs-lookup"><span data-stu-id="409eb-392">(leave blank)</span></span>  <br/> <span data-ttu-id="409eb-393">または</span><span class="sxs-lookup"><span data-stu-id="409eb-393">Or</span></span>  <br/>  <span data-ttu-id="409eb-394">`932`(ANSI/OEM 日本語のコードページ識別子)</span><span class="sxs-lookup"><span data-stu-id="409eb-394">`932` (which is the code page identifier for ANSI/OEM Japanese)</span></span>  <br/> |
    | `SPFileContainer` <br/> |<span data-ttu-id="409eb-395">PST インポートの場合は、このパラメーターを空白のままにします。 </span><span class="sxs-lookup"><span data-stu-id="409eb-395">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="409eb-396">該当なし</span><span class="sxs-lookup"><span data-stu-id="409eb-396">Not applicable</span></span>  <br/> |
    | `SPManifestContainer` <br/> |<span data-ttu-id="409eb-397">PST インポートの場合は、このパラメーターを空白のままにします。 </span><span class="sxs-lookup"><span data-stu-id="409eb-397">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="409eb-398">該当なし</span><span class="sxs-lookup"><span data-stu-id="409eb-398">Not applicable</span></span>  <br/> |
    | `SPSiteUrl` <br/> |<span data-ttu-id="409eb-399">PST インポートの場合は、このパラメーターを空白のままにします。 </span><span class="sxs-lookup"><span data-stu-id="409eb-399">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="409eb-400">該当なし</span><span class="sxs-lookup"><span data-stu-id="409eb-400">Not applicable</span></span>  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a><span data-ttu-id="409eb-401">手順 8:Office 365 で PST インポート ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="409eb-401">Step 8: Create a PST Import job in Office 365</span></span>

<span data-ttu-id="409eb-p156">最後の手順では、Office 365 のインポートサービスで PST インポートジョブを作成します。前述のように、手順7で作成した PST インポートマッピングファイルを送信します。新しいジョブを作成した後、インポートサービスはマッピングファイル内の情報を使用して、(手順5で Office 365 にアップロードした) PST ファイルを暗号化解除してインポートし、指定されたユーザーメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="409eb-p156">The last step is to create the PST Import job in the Import service in Office 365. As previously explained, you will submit the PST Import mapping file that you created in Step 7. After you create the new job, the Import service will use the information in the mapping file to un-encrypt and import the PST files (that you uploaded to Office 365 in Step 5) to the specified user mailbox.</span></span> 
  
1. <span data-ttu-id="409eb-405">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="409eb-405">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="409eb-406">office 365 組織の管理者アカウントの資格情報を使用して、office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="409eb-406">Sign in to Office 365 using the credentials for an administrator account in your Office 365 organization.</span></span>
    
3. <span data-ttu-id="409eb-407">左側のウィンドウで、[**データガバナンス**] をクリックし、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-407">In the left pane, click **Data governance** and then click **Import**.</span></span>
    
4. <span data-ttu-id="409eb-408">**[インポート]** ページで、**[インポート サービスに移動する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-408">On the **Import** page, click **Go to the Import service**.</span></span>
    
5. <span data-ttu-id="409eb-409">[ **Office へのデータのインポート 365** ] ページで、[**新しいジョブ**![の追加] アイコン](media/ITPro-EAC-AddIcon.gif)をクリックし、[**電子メールメッセージ (PST ファイル) のアップロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-409">On the **Import data to Office 365** page, click **New job**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then click **Upload email messages (PST files)**.</span></span>
    
6. <span data-ttu-id="409eb-410">**[ネットワーク経由でファイルをアップロードする]** ページで、**[ファイルのアップロードが完了しました]** と **[マッピング ファイルにアクセスできます]** の各チェック ボックスを選択して、**[次へ]** をクリックします。 </span><span class="sxs-lookup"><span data-stu-id="409eb-410">On the **Upload files over the network** page, click the **I'm done uploading my files** and **I have access to the mapping file** check boxes, and then click **Next**.</span></span> 
    
7. <span data-ttu-id="409eb-411">PST インポート ジョブの名前を入力し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="409eb-411">Type a name for the PST Import job, and then click **Next**.</span></span>
    
8. <span data-ttu-id="409eb-412">[追加] アイコン](media/ITPro-EAC-AddIcon.gif)をクリックして、手順7で作成した PST マッピングファイルを選択します。 \*\*\*\* ![</span><span class="sxs-lookup"><span data-stu-id="409eb-412">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) to select the PST Mapping file that you created in Step 7.</span></span> 
    
9. <span data-ttu-id="409eb-413">CSV ファイルの名前が一覧に表示されたら、CSV ファイルを選択して **[検証]** をクリックし、CSV ファイルにエラーがないか確認します。 </span><span class="sxs-lookup"><span data-stu-id="409eb-413">After the name of the CSV file appears in the list, select it and then click **Validate** to check your CSV file for errors.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="409eb-p157">前述したように、pst ファイルが暗号化され`.pfile`ている場合は、pst ファイル名に拡張子が追加されます。CSV ファイルの PST `.pfile`ファイルの名前に拡張機能を追加する必要があります。省略すると、CSV ファイルの検証は失敗します。</span><span class="sxs-lookup"><span data-stu-id="409eb-p157">As previous explained, when the PST files are encrypted, a  `.pfile` extension is appended to the PST filename. You must add the  `.pfile` extension to the name of the PST files in the CSV file. If you don't, the validation of the CSV file will fail.</span></span> 
  
    <span data-ttu-id="409eb-p158">PST インポート ジョブを作成するには、CSV ファイルが正常に検証される必要があります。検証が失敗した場合は、**[状態]** 列の **[無効]** リンクをクリックします。PST インポートのマッピング ファイルのコピーが開き、失敗したファイル内の各行ごとにエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="409eb-p158">The CSV file has to be successfully validated to create a PST Import job. If the validation fails, click the **Invalid** link in the **Status** column. A copy of your PST Import mapping file is opened, with a error message for each row in the file that failed.</span></span> 
    
10. <span data-ttu-id="409eb-420">PST のマッピング ファイルが正常に検証されたら、ご契約条件を読み、チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="409eb-420">When the PST mapping file is successfully validated, read the terms and conditions document, and then click the checkbox.</span></span>
    
11. <span data-ttu-id="409eb-421">**[完了]** をクリックして、ジョブを送信します。</span><span class="sxs-lookup"><span data-stu-id="409eb-421">Click **Finish** to submit the job.</span></span> 
    
    <span data-ttu-id="409eb-422">ジョブは、[**データを Office 365 にインポートする**] ページの PST インポートジョブの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="409eb-422">The job is displayed in the list of PST Import jobs on the **Import data to Office 365** page.</span></span> 
    
12. <span data-ttu-id="409eb-423">ジョブを選択し、 \*\*\*\*![[更新の](media/O365-MDM-Policy-RefreshIcon.gif)更新] アイコンをクリックして、詳細ウィンドウに表示される状態情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="409eb-423">Select the job and click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the status information that's displayed in the details pane.</span></span> 
    
13. <span data-ttu-id="409eb-424">詳細ウィンドウで、**[詳細の表示]** をクリックして、選択したジョブの最新の状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="409eb-424">In the details pane, click **View details** to get the latest status for the selected job.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="409eb-425">詳細情報</span><span class="sxs-lookup"><span data-stu-id="409eb-425">More information</span></span>

- <span data-ttu-id="409eb-426">PST ファイルを Office 365 にインポートする理由</span><span class="sxs-lookup"><span data-stu-id="409eb-426">Why import PST files to Office 365?</span></span>
    
  - <span data-ttu-id="409eb-427">組織の電子メールを Office 365 に移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="409eb-427">It's a good way to migrate your organization's email to Office 365.</span></span>
    
  - <span data-ttu-id="409eb-428">次のことが可能になるので、組織のコンプライアンスのニーズに対応するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="409eb-428">It helps address compliance needs of your organization by letting you:</span></span>
    
  - <span data-ttu-id="409eb-429">アーカイブ メールボックスを有効にして、追加のメールボックス容量をユーザーに提供する。</span><span class="sxs-lookup"><span data-stu-id="409eb-429">Enable archive mailboxes to give users additional mailbox storage space.</span></span>
    
  - <span data-ttu-id="409eb-430">メールボックスを保持状態にして、コンテンツを保持する。</span><span class="sxs-lookup"><span data-stu-id="409eb-430">Place mailboxes on hold to preserve content.</span></span>
    
  - <span data-ttu-id="409eb-431">Microsoft 電子情報開示ツールを使って、メールボックスのコンテンツを検索する。</span><span class="sxs-lookup"><span data-stu-id="409eb-431">Use Microsoft eDiscovery tools to search for content in mailboxes.</span></span>
    
  - <span data-ttu-id="409eb-432">アイテム保持ポリシーを使って、メールボックスのコンテンツの保持期間を制御する。</span><span class="sxs-lookup"><span data-stu-id="409eb-432">Use retention policies to control how long mailbox content is retained.</span></span>
    
  - <span data-ttu-id="409eb-433">メールボックス関連イベントに対して Office 365 監査ログを検索します。</span><span class="sxs-lookup"><span data-stu-id="409eb-433">Search the Office 365 audit log for mailbox-related events.</span></span>
    
  - <span data-ttu-id="409eb-p159">データ損失からの保護に役立てることができます。Office 365 メールボックスにインポートされる PST ファイルは、データをユーザーのコンピューターに保存するのではなく、Exchange Online の高可用性機能を継承します。</span><span class="sxs-lookup"><span data-stu-id="409eb-p159">It helps protect against data loss. PST files that are imported to Office 365 mailboxes inherit the high availability features of Exchange Online, as opposed to storing the data on a user's computer.</span></span>
    
  - <span data-ttu-id="409eb-436">データがクラウドに格納されるので、ユーザーはあらゆるデバイスからデータを利用できます。</span><span class="sxs-lookup"><span data-stu-id="409eb-436">The data is available to the user from all devices because it's stored in the cloud.</span></span>
    
- <span data-ttu-id="409eb-p160">手順2、3、および4で取得したキー、id、および url の例を次に示します。この例には、o365importtool.zip ツールで実行して、PST ファイルを暗号化して Office 365 にアップロードするためのコマンドの構文も含まれています。パスワードやその他のセキュリティ関連の情報を保護するのと同じように、これらを保護するための予防措置を講じるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p160">Here's an example of the keys, IDs, and URLs that are obtained in Steps 2, 3, and 4. This example also contains the syntax for the command that you run in the O365ImportTool.exe tool to encrypt and upload PST files to Office 365. Be sure to take precautions to protect these just like you would protect passwords or other security-related information.</span></span>
    
  ```
  Symmetric key: l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=

  BPOSId: 42745b33-2a5c-4726-8a2a-ca43caa0f74b

  LicensingIntranetDistributionPointUrl (RMS licensing location): https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing
  
  SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D
  
  O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL from the SAS URL> /upload-destSAS:<SAS key from the SAS URL>
  
  EXAMPLES
  
  This example uploads PST files to the root of the Azure storage location:

  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  
  This example uploads PST files to a subfolder named EncryptedPSTs  in the Azure storage location:
  
  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  ```

- <span data-ttu-id="409eb-p161">前述したように、Office 365 インポートサービスは、PST ファイルがメールボックスにインポートされた後、保持ホールドの設定 (無期限) を有効にします。つまり、 *RentionHoldEnabled*プロパティはに`True`設定されているため、メールボックスに割り当てられたアイテム保持ポリシーは処理されません。これにより、メールボックスの所有者は、削除またはアーカイブポリシーによる古いメッセージの削除またはアーカイブを禁止することにより、新しくインポートされたメッセージを管理できます。この保持ホールドを管理するために実行できるいくつかの手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="409eb-p161">As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RentionHoldEnabled*  property is set to  `True` so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold:</span></span> 
    
  - <span data-ttu-id="409eb-p162">一定の期間が経過した後、 `Set-Mailbox -RetentionHoldEnabled $false`コマンドを実行して保存機能を無効にすることができます。手順については、「[メールボックスを保持ホールドの状態にする](https://go.microsoft.com/fwlink/p/?LinkId=544749)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p162">After a certain period of time, you can turn off the retention hold by running the  `Set-Mailbox -RetentionHoldEnabled $false` command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).</span></span>
    
  - <span data-ttu-id="409eb-p163">今後、ある日付に無効になるように、保存機能を構成することができます。そのためには、 `Set-Mailbox -EndDateForRetentionHold <date>`コマンドを実行します。たとえば、今日の日付が2016年7月1日で、保持ホールドを30日以内に無効にする場合は、次のコマンド`Set-Mailbox -EndDateForRetentionHold 8/1/2016`を実行します。このシナリオでは、 *RentionHoldEnabled*プロパティをに`True`設定したままにします。詳細については、「[メールボックスの設定](https://go.microsoft.com/fwlink/p/?LinkId=150317)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p163">You can configure the retention hold so that it's turned off on some date in the future. You do this by running the  `Set-Mailbox -EndDateForRetentionHold <date>` command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. In this scenario, you would leave the  *RentionHoldEnabled*  property set to `True`. For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).</span></span>
    
  - <span data-ttu-id="409eb-p164">メールボックスに割り当てられているアイテム保持ポリシーの設定を変更して、インポートした古いアイテムがすぐに削除されるか、ユーザーのアーカイブメールボックスに移動されないようにすることができます。たとえば、メールボックスに割り当てられている削除ポリシーまたはアーカイブポリシーの保存期間を長くすることができます。このシナリオでは、アイテム保持ポリシーの設定を変更した後、メールボックスの保存機能をオフにします。詳細については、「 [Office 365 組織のメールボックスのアーカイブおよび削除ポリシーをセットアップする](set-up-an-archive-and-deletion-policy-for-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409eb-p164">You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>
