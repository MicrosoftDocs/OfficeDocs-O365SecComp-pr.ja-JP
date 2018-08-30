---
title: ネットワーク アップロードを使用して、RMS で暗号化された PST ファイルを Office 365 にインポートする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: RMS で暗号化された PST ファイルを Office 365 でユーザーのメールボックスにインポートするのには、ネットワークのアップロードを使用する方法について説明します。
ms.openlocfilehash: 6460512e2d6085df684841248dc286d39dbd9d87
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532765"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a><span data-ttu-id="0906c-103">ネットワーク アップロードを使用して、RMS で暗号化された PST ファイルを Office 365 にインポートする</span><span class="sxs-lookup"><span data-stu-id="0906c-103">Use network upload to import RMS-encrypted PST files to Office 365</span></span>

<span data-ttu-id="0906c-104">**この資料では、管理者用です。自分のメールボックスを PST ファイルをインポートしようとしていますか。[インポート電子メール、連絡先、および Outlook の .pst ファイルから予定表](https://go.microsoft.com/fwlink/p/?LinkID=785075)を参照してください。**</span><span class="sxs-lookup"><span data-stu-id="0906c-104">**This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span></span>
   
<span data-ttu-id="0906c-p101">ネットワークの使用は、PST ファイルをユーザーのメールボックスにインポートするには、オプションと Office 365 のインポート サービスにアップロードします。ネットワークのアップロードでは、マイクロソフトのクラウド内の一時記憶領域、PST ファイルをアップロードすることを意味します。Office 365 のインポート サービスは、ターゲット ユーザーのメールボックスにストレージ領域から PST ファイルをコピーします。インポート サービスの新機能では、アップロード、およびマイクロソフトのクラウドに格納されている前に、PST ファイルを暗号化することができます。ユーザーのメールボックスにインポートすると、これらのファイルは暗号化を解除できません。</span><span class="sxs-lookup"><span data-stu-id="0906c-p101">Use the network upload option and the Office 365 Import service to import PST files to user mailboxes. Network upload means that you upload the PST files a temporary storage area in the Microsoft cloud. Then the Office 365 Import service copies the PST files from the storage area to the target user mailboxes. A new feature of the Import service lets you encrypt your PST files before they are uploaded and stored on the Microsoft cloud. These files will be un-encrypted when they're imported to user mailboxes.</span></span> 
  
<span data-ttu-id="0906c-110">暗号化し、Office 365 のメールボックスを PST ファイルをインポートするための手順を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="0906c-110">Here are the steps required to encrypt and import PST files to Office 365 mailboxes:</span></span>
  
[<span data-ttu-id="0906c-111">手順 1:PST インポートの Azure Rights Management をセットアップする </span><span class="sxs-lookup"><span data-stu-id="0906c-111">Step 1: Set up Azure Rights Management for PST Import</span></span>](#step-1-set-up-azure-rights-management-for-pst-import)

[<span data-ttu-id="0906c-112">手順 2:PST インポートの暗号化キーを生成する</span><span class="sxs-lookup"><span data-stu-id="0906c-112">Step 2: Generate an encryption key for PST Import</span></span>](#step-2-generate-an-encryption-key-for-pst-import)

[<span data-ttu-id="0906c-113">手順 3: RMS のテナント ID とライセンスの URL を取得します。</span><span class="sxs-lookup"><span data-stu-id="0906c-113">Step 3: Obtain RMS tenant ID and licensing URL</span></span>](#step-3-obtain-rms-tenant-id-and-licensing-url)

[<span data-ttu-id="0906c-114">手順 4: PST インポート ツールをダウンロードして、SAS の URL をコピー</span><span class="sxs-lookup"><span data-stu-id="0906c-114">Step 4: Download the PST Import tools and copy the SAS URL</span></span>](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[<span data-ttu-id="0906c-115">手順 5: の暗号化し、PST ファイルを Office 365 にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0906c-115">Step 5: Encrypt and upload your PST files to Office 365</span></span>](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[<span data-ttu-id="0906c-116">(省略可能)手順 6: Office 365 のビュー PST ファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="0906c-116">(Optional) Step 6: View a list of the PST files uploaded to Office 365</span></span>](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[<span data-ttu-id="0906c-117">PST インポート マッピング ファイルを作成する手順 7。</span><span class="sxs-lookup"><span data-stu-id="0906c-117">Step 7: Create the PST Import mapping file</span></span>](#step-7-create-the-pst-import-mapping-file)

[<span data-ttu-id="0906c-118">手順 8:Office 365 で PST インポート ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="0906c-118">Step 8: Create a PST Import job in Office 365</span></span>](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> <span data-ttu-id="0906c-p102">設定し、組織を構成する手順 4 を 1 回だけを暗号化し、Office 365 のメールボックスを PST ファイルをインポートする手順 1 を実行する必要があります。次の手順を実行した後は、暗号化、アップロード、および複数の PST ファイルをインポートするたびを手順 8 から手順 5 に従います。</span><span class="sxs-lookup"><span data-stu-id="0906c-p102">You have to perform Step 1 through Step 4 only once to set up and configure your organization to encrypt and import PST files to Office 365 mailboxes. After you perform these steps, follow Step 5 through Step 8 each time you want to encrypt, upload, and import a batch of PST files.</span></span> 
  
<span data-ttu-id="0906c-121">Office 365 へのデータのインポートの詳細については、 [Office 365 の組織の PST ファイルのインポートの概要](importing-pst-files-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-121">For more information about importing data to Office 365, see [Overview of importing your organization PST files to Office 365](importing-pst-files-to-office-365.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="0906c-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="0906c-122">Before you begin</span></span>

- <span data-ttu-id="0906c-p103">メールボックスのエクスポートをインポートの役割を割り当てるには、Exchange オンライン Office 365 のメールボックスを PST ファイルをインポートするのにはする必要があります。既定では、この役割はありませんに割り当てられている役割グループは、Exchange オンライン。組織の管理役割グループに、メールボックスのインポート エクスポートの役割を追加できます。または、新しい役割グループを作成、メールボックスのインポート エクスポートの役割を割り当てるし、ユーザー自身をメンバーとして追加します。詳細については、追加するロール グループのロール」を参照してください。 または、「作成」の役割グループの[役割グループの管理](https://go.microsoft.com/fwlink/p/?LinkId=730688)のセクションです。</span><span class="sxs-lookup"><span data-stu-id="0906c-p103">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
    
    <span data-ttu-id="0906c-128">Office 365 のセキュリティのジョブのインポートを作成するのにはさらに、&amp;コンプライアンス センターは、次のいずれかを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="0906c-128">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
    
  - <span data-ttu-id="0906c-p104">メール受信者の役割を割り当てるには、Exchange オンラインする必要があります。既定では、この役割は組織の管理と受信者の管理役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0906c-p104">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="0906c-131">または</span><span class="sxs-lookup"><span data-stu-id="0906c-131">Or</span></span>
    
  - <span data-ttu-id="0906c-132">Office 365 の組織のグローバル管理者があります。</span><span class="sxs-lookup"><span data-stu-id="0906c-132">You have to be a global administrator in your Office 365 organization.</span></span>
    
  > [!TIP]
  > <span data-ttu-id="0906c-p105">Exchange Online の具体的には、Office 365 に PST ファイルをインポートする新しい役割グループを作成することを検討してください。PST ファイルをインポートするのには必要な特権を最低限のレベルで、新しい役割グループにメールボックスのエクスポートをインポートし、メール受信者の役割を割り当てるし、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p105">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
- <span data-ttu-id="0906c-p106">ファイル サーバーまたは共有のフォルダー、組織内で Office 365 にインポートする PST ファイルを保存する必要があります。ステップ 5 で、暗号化され、このファイル サーバーに格納されるか、Office 365 にフォルダーを共有する PST ファイルをアップロード、Office 365 の ImportTool を実行します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p106">You need to store the PST files that you want to import to Office 365 on a file server or shared folder in your organization. In Step 5, you'll run the Office 365 ImportTool, which will encrypt and upload the PST files that are stored on this file server or shared folder to Office 365.</span></span>
    
- <span data-ttu-id="0906c-p107">この手順ではコピーして、暗号化キー、ストレージ ・ キー、および多数の識別キーと Url のコピーを保存します。この情報は、暗号化し、PST ファイルをアップロードする手順 5 で使用されます。パスワードやその他のセキュリティに関連する情報を保護するようにこれらだけを保護する対策を講じていることを確認します。たとえば、パスワードで保護された Microsoft Word 文書に保存または暗号化された USB ドライブに保存します。これらのキー、Id、および Url の例の[詳細について](#more-information)はを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-p107">This procedure involves copying and saving a copy of an encryption key, a storage key, and a number of identification keys and URLs. This information will be used in Step 5 to encrypt and upload your PST files. Be sure to take precautions to protect these just like you would protect passwords or other security-related information. For example you might save them to a password-protected Microsoft Word document or save them to an encrypted USB drive. See the [More information](#more-information) section for an example of these keys, IDs, and URLs.</span></span> 
    
- <span data-ttu-id="0906c-p108">PST ファイルをインポートするには Office 365 の非アクティブなメールボックスにします。内の非アクティブなメールボックスの GUID を指定することによってこれを行う、 `Mailbox` PST インポート マッピング ファイル内のパラメーターです。詳細については、[手順 7](#step-7-create-the-pst-import-mapping-file)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-p108">You can import PST files to an inactive mailbox in Office 365. You do this by specifying the GUID of the inactive mailbox in the  `Mailbox` parameter in the PST Import mapping file. See [Step 7](#step-7-create-the-pst-import-mapping-file) for more information.</span></span> 
    
- <span data-ttu-id="0906c-p109">Exchange ハイブリッド展開の場合は、[プライマリ メールボックスは、オンプレミス ユーザーのクラウド ベースのアーカイブ メールボックスに PST ファイルをインポートできます。PST インポート マッピング ファイルで次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0906c-p109">In an Exchange hybrid deployment, you can import PST files to a cloud-based archive mailbox for a user whose primary mailbox is on-premises. You do this by doing the following in the PST Import mapping file:</span></span>
    
  - <span data-ttu-id="0906c-147">ユーザーのオンプレミスのメールボックスの電子メール アドレスを指定します`Mailbox`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="0906c-147">Specify the email address for the user's on-premises mailbox in the  `Mailbox` parameter.</span></span> 
    
  - <span data-ttu-id="0906c-148">**真**の値を指定します`IsArchive`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="0906c-148">Specify the **TRUE** value in the  `IsArchive` parameter.</span></span> 
    
    <span data-ttu-id="0906c-149">詳細については、[手順 7](#step-7-create-the-pst-import-mapping-file)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-149">See [Step 7](#step-7-create-the-pst-import-mapping-file) for more information.</span></span> 
    
- <span data-ttu-id="0906c-p110">PST ファイルが Office 365 のメールボックスにインポートされると、メールボックスの設定の保存は不定の期間のになっています。つまり、メールボックスに割り当てられているリテンション ・ ポリシーは、の保持を無効にするか、保留リストを無効にする日付を設定するまで処理されません。なぜこのような処理でしょうか。メールボックスにインポートするメッセージが古い場合は、それら可能性が完全に削除 (パージ)、メールボックスに対して構成されている保存期間の設定に基づいて、保存期間が期限切れになった。保存保留中のメールボックスを配置することと、これらの新しくインポートされたメッセージまたはメールボックスの保存期間の設定を変更するのには、時間を提供を管理するためにメールボックス所有者の時間が提供されます。保存保留リストの管理に関する推奨事項の[詳細について](#more-information)はを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-p110">After PST files are imported to an Office 365 mailbox, the retention hold setting for the mailbox is turned on for an indefinite duration. This means that the retention policy assigned to the mailbox won't be processed until you turn off the retention hold or set a date to turn off the hold. Why do we do this? If messages imported to a mailbox are old, they might be permanently deleted (purged) because their retention period has expired based on the retention settings configured for the mailbox. Placing the mailbox on retention hold will give the mailbox owner time to manage these newly-imported messages or give you time to change the retention settings for the mailbox. See the [More information](#more-information) section for suggestions about managing the retention hold.</span></span> 
    
- <span data-ttu-id="0906c-156">Office 365 にアップロードする前に、PST ファイルを暗号化する必要はない場合、は、 [Office 365 に PST ファイルをインポートするのにはアップロードの使用のネットワーク](use-network-upload-to-import-pst-files.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-156">If you don't need to encrypt your PST files before you upload them to Office 365, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
    
- <span data-ttu-id="0906c-157">Office 365 に PST ファイルをインポートするのには、ネットワークのアップロードを使用してについてよく寄せられる質問は、 [Office 365 に PST ファイルのインポートについての FAQ](faqimporting-pst-files-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-157">For frequently asked questions about using network upload to import PST files to Office 365, see [FAQ about importing PST files to Office 365](faqimporting-pst-files-to-office-365.md).</span></span>
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a><span data-ttu-id="0906c-158">手順 1:PST インポートの Azure Rights Management をセットアップする </span><span class="sxs-lookup"><span data-stu-id="0906c-158">Step 1: Set up Azure Rights Management for PST Import</span></span>

<span data-ttu-id="0906c-p111">PST インポートでは、Office 365 の Azure アクセス権管理 (Azure RMS) サービスによって提供される暗号化機能を使用します。これにより、Office 365 にアップロードする前に PST ファイルを暗号化することができます。</span><span class="sxs-lookup"><span data-stu-id="0906c-p111">PST Import uses the encryption functionality provided by the Azure Rights Management (Azure RMS) service in Office 365. This lets you to encrypt PST files before uploading them to Office 365.</span></span> 
  
<span data-ttu-id="0906c-161">PST インポートの Azure の RMS の構成は、3 つの手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="0906c-161">Configuring Azure RMS for PST Import consists of three steps:</span></span>
  
- [<span data-ttu-id="0906c-162">Azure の RMS をアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="0906c-162">Activating Azure RMS</span></span>](#activate-azure-rms)
    
- [<span data-ttu-id="0906c-163">RMS を構成する Exchange オンライン</span><span class="sxs-lookup"><span data-stu-id="0906c-163">Configuring RMS in Exchange Online</span></span>](#configure-rms-in-exchange-online)
    
- [<span data-ttu-id="0906c-164">Active Directory の RMS クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0906c-164">Installing the Active Directory RMS Client</span></span>](#install-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a><span data-ttu-id="0906c-165">Azure の RMS をアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="0906c-165">Activating Azure RMS</span></span>

<span data-ttu-id="0906c-p112">Azure の RMS は、既定で無効にしますが、するか、組織内の別の管理者がありますがアクティブになって。インストールし、Azure の DRM を有効にする[Azure アクセス権の管理をアクティブにする](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)の指示に従って操作します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p112">Azure RMS is disabled by default, but you or another administrator in your organization might have activated it. Follow instructions on [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service) to install and activate Azure DRM.</span></span>
  
### <a name="configuring-rms-in-exchange-online"></a><span data-ttu-id="0906c-168">RMS を構成する Exchange オンライン</span><span class="sxs-lookup"><span data-stu-id="0906c-168">Configuring RMS in Exchange Online</span></span>

<span data-ttu-id="0906c-p113">権限管理サービスをアクティブにした後、次に、Exchange Azure の RMS を使用するオンラインでの情報権利管理 (IRM) を設定するのには。詳細については、 [Azure の権利管理を使用する IRM を構成する](https://go.microsoft.com/fwlink/p/?LinkId=394816)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-p113">After you've activated the Rights Management service, the next step is to set up Information Rights Management (IRM) in Exchange Online to use Azure RMS. For more information, see [Configure IRM to use Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=394816).</span></span>
  
1. <span data-ttu-id="0906c-171">[リモート PowerShell を使用して Exchange Online に接続](https://go.microsoft.com/fwlink/p/?LinkId=396554 )します。</span><span class="sxs-lookup"><span data-stu-id="0906c-171">[Connect to Exchange Online using Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554 ).</span></span>
    
2. <span data-ttu-id="0906c-172">次のコマンドを実行して、RMS キー共有 URL を設定する。</span><span class="sxs-lookup"><span data-stu-id="0906c-172">Run the following command to set the RMS key sharing URL.</span></span>
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    <span data-ttu-id="0906c-173">組織の場所の正しい RMS キー共有場所を決定するには、次の表を使用します。</span><span class="sxs-lookup"><span data-stu-id="0906c-173">Use the following table to determine the correct RMS key sharing location for the location of your organization.</span></span>
    
    |<span data-ttu-id="0906c-174">**場所**</span><span class="sxs-lookup"><span data-stu-id="0906c-174">**Location**</span></span>|<span data-ttu-id="0906c-175">**RMS キー共有場所**</span><span class="sxs-lookup"><span data-stu-id="0906c-175">**RMS key sharing location**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="0906c-176">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="0906c-176">North America</span></span>  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="0906c-177">欧州連合</span><span class="sxs-lookup"><span data-stu-id="0906c-177">European Union</span></span>  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="0906c-178">アジア</span><span class="sxs-lookup"><span data-stu-id="0906c-178">Asia</span></span>  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="0906c-179">南アメリカ</span><span class="sxs-lookup"><span data-stu-id="0906c-179">South America</span></span>  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="0906c-180">行政機関向け Office 365 (行政機関のコミュニティ クラウド)</span><span class="sxs-lookup"><span data-stu-id="0906c-180">Office 365 for Government (Government Community Cloud)</span></span>  <br/> | <span data-ttu-id="0906c-181">`https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0906c-181">`https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup></span></span> <br/> |
   
    > [!NOTE]
    > <span data-ttu-id="0906c-182"><sup>1</sup>政府の Sku (政府コミュニティ クラウド) に Office 365 が購入されたお客様のみがこの RMS キーの場所の共有を使用してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-182"><sup>1</sup> Only customers who have purchased Office 365 for Government SKUs (Government Community Cloud) should use this RMS key sharing location.</span></span> 
  
    <span data-ttu-id="0906c-183">たとえば、このコマンドは、共有の場所に Exchange オンライン北アメリカにある顧客の RMS のオンライン キーを構成します。</span><span class="sxs-lookup"><span data-stu-id="0906c-183">For example, this command configures the RMS Online key sharing location in Exchange Online for a customer located in North America.</span></span>
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. <span data-ttu-id="0906c-184">RMS オンラインから Office 365 の組織に、信頼された発行ドメイン (TPD) をインポートするのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0906c-184">Run the following command to import a Trusted Publishing Domain (TPD) from RMS Online to your Office 365 organization.</span></span> 
    
    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    <span data-ttu-id="0906c-185">TPD には、PST ファイルの暗号化など、組織で RMS 機能を使用するために必要な設定が含まれています。 </span><span class="sxs-lookup"><span data-stu-id="0906c-185">A TPD contains the settings needed to use RMS features in your organization, including encrypting PST files.</span></span> 
    
4. <span data-ttu-id="0906c-186">Office 365 組織で IRM を有効にするのには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0906c-186">Run the following command to enable IRM for your Office 365 organization.</span></span>
    
    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a><span data-ttu-id="0906c-187">Active Directory の RMS クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0906c-187">Installing the Active Directory RMS Client</span></span>

<span data-ttu-id="0906c-p114">このセクションの最後のステップでは、権限管理サービス (RMS) クライアント 2.1 をダウンロードします。このソフトウェアでは、Azure の RMS へのアクセスを保護するのに役立ち、情報を暗号化し、手順 5 で PST ファイルをアップロードするに使用する同じコンピューターに RM クライアントを Azure 利用のインストールを使用するアプリケーションからフローを保護します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p114">The last step in this section is to download the Rights Management Services (RMS) Client 2.1. This software helps protect access to Azure RMS and protects information flowing through applications that use Azure RMS. Install the RMS client on the same computer that you'll use to encrypt and upload PST files in Step 5.</span></span> 
  
1. <span data-ttu-id="0906c-191">[権限管理サービス クライアント 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396)をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="0906c-191">Download [Rights Management Service Client 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396).</span></span>
    
2. <span data-ttu-id="0906c-192">Active Directory Rights Management サービス クライアント 2.1 ウィザードを実行して、クライアントをインストールする。</span><span class="sxs-lookup"><span data-stu-id="0906c-192">Run the Active Directory Rights Management Service Client 2.1 wizard to install the client.</span></span>

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a><span data-ttu-id="0906c-193">手順 2:PST インポートの暗号化キーを生成する</span><span class="sxs-lookup"><span data-stu-id="0906c-193">Step 2: Generate an encryption key for PST Import</span></span>

<span data-ttu-id="0906c-p115">Azure の RMS を設定した後、次の手順では、Office 365 にアップロードする PST ファイルを暗号化するために使用される暗号化キー (対称キーと呼ばれます) を生成します。Azure Active Directory の主要サービスとして PST インポート サービスを追加することによってこれを行うでしょう。サービス主体が PST インポート サービスにアップロードすると、Azure Active Directory と直接認証を許可するようにこのアプリケーションを追加すると、手順 5 で Azure ストレージの場所に PST ファイルが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="0906c-p115">After you've set up Azure RMS, the next step is to generate an encryption key (called a symmetric key) that will be used to encrypt the PST files that you upload to Office 365. You'll do this by adding the PST Import service as a service principal in Azure Active Directory. Adding this application as a service principal will allow the PST Import service to authenticate directly with Azure Active Directory when you upload encrypted the PST files to the Azure storage location in Step 5.</span></span>
  
1. <span data-ttu-id="0906c-197">Windows PowerShell の Azure Active Directory のモジュールを起動します。</span><span class="sxs-lookup"><span data-stu-id="0906c-197">Start the Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="0906c-198">次のコマンドを実行して、Microsoft Online サービスに接続する。</span><span class="sxs-lookup"><span data-stu-id="0906c-198">Run the following command to connect to the Microsoft Online service.</span></span>
    
    ```
    Connect-MsolService
    ```

3. <span data-ttu-id="0906c-199">Office 365 組織の管理者アカウントの資格情報を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-199">Enter the credentials for an administrator account in your Office 365 organization, and then click **OK**.</span></span>
    
4. <span data-ttu-id="0906c-p116">次のコマンドを実行して、暗号化キー (対称キーと呼ばれる) を生成する。これを行うには、新しい PST 暗号化プリンシパルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p116">Run the following command to generate an encryption key (call a symmetric key). You'll do this by creating a new PST Encryption Principal.</span></span>
    
    ```
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    <span data-ttu-id="0906c-202">システムには、新しい PST 暗号化プリンシパルの対称キーとプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0906c-202">The system displays the symmetric key and the properties for the new PST Encryption Principal.</span></span>
    
    ![表示されている対称キーをコピーして保存する](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. <span data-ttu-id="0906c-p117">対称キーをテキスト ファイルまたは Word ファイルにコピーする。前述したように、必ずこのファイルを保護する予防策を講じてください。対称キーが表示されるのはこの時だけであるため、このウィンドウのスクリーンショットを撮り、同じファイルに保存することも検討してください。 </span><span class="sxs-lookup"><span data-stu-id="0906c-p117">Copy the symmetric key to a text or Word file. As previously stated, be sure to take precautions to protect this file. Because this is the only time that the symmetric key is displayed, you might also consider taking a screenshot of this window and saving it to the same file.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="0906c-p118">PST 暗号化プリンシパルの作成後は、**Get-MsolServicePrincipal** コマンドレットを使用して対称キーを取得することはできなくなります。このためキーを保存することが重要になります。</span><span class="sxs-lookup"><span data-stu-id="0906c-p118">After you create the PST Encryption Principal, you won't be able to retrieve the symmetric key by using the **Get-MsolServicePrincipal** cmdlet. That's why it's important to save the key.</span></span> 
  
<span data-ttu-id="0906c-p119">開いたままで、Azure Active Directory モジュールを Windows PowerShell の Microsoft オンライン サービスに接続されています。次の手順では、このウィンドウでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p119">Keep the Azure Active Directory Module for Windows PowerShell open and connected to the Microsoft Online service. You'll run a command in this window in the next step.</span></span>

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a><span data-ttu-id="0906c-211">手順 3: RMS のテナント ID とライセンスの URL を取得します。</span><span class="sxs-lookup"><span data-stu-id="0906c-211">Step 3: Obtain RMS tenant ID and licensing URL</span></span>

<span data-ttu-id="0906c-p120">次の手順では、ID と、組織の RMS の Azure サービスのライセンスの場所の URL は、テナントを取得します。コピーし、手順 2 から対称キーが格納されている同じファイルにこの情報を保存します。ID と URL は、PST ファイルを暗号化する手順 5 で使用されます。</span><span class="sxs-lookup"><span data-stu-id="0906c-p120">The next step is to obtain the tenant ID and licensing location URL for the Azure RMS service for your organization. Copy and save this information to the same file that contains the symmetric key from Step 2. The ID and URL will be used in Step 5 to encrypt your PST files.</span></span>
  
1. <span data-ttu-id="0906c-215">モジュールでは、Azure Active ディレクトリ (Microsoft オンライン サービスに接続されている)、Windows PowerShell の組織の Office 365 の Azure の RMS サービスに接続する次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0906c-215">In the Azure Active Directory Module for Windows PowerShell (which is connected to the Microsoft Online service), run the following command to connect to the Azure RMS service in your Office 365 organization.</span></span>
    
    ```
    Connect-AadrmService 
    ```

2. <span data-ttu-id="0906c-216">組織の Office 365 の管理者アカウントの資格情報を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-216">Enter the credentials for an administrator account in your Office 365 organization and then click **OK**.</span></span>
    
3. <span data-ttu-id="0906c-217">Office 365 の組織で、Azure の RMS サービスのテナント ID を表示する次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0906c-217">Run the following command to display the tenant ID for the Azure RMS service in your Office 365 organization.</span></span>
    
    ```
    Get-AadrmConfiguration | FL BPOSId
    ```

    <span data-ttu-id="0906c-218">値をコピーして、`BPOSId`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0906c-218">Copy and save the value for the  `BPOSId` property.</span></span> 
    
4. <span data-ttu-id="0906c-219">Azure の RMS サービスのライセンスの場所を表示するのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0906c-219">Run the following command to display the licensing location for your Azure RMS service.</span></span>
    
    ```
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    <span data-ttu-id="0906c-220">値をコピーして、`LicensingIntranetDistributionPointUrl`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0906c-220">Copy and save the value for the  `LicensingIntranetDistributionPointUrl` property.</span></span> 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a><span data-ttu-id="0906c-221">手順 4: PST インポート ツールをダウンロードして、SAS の URL をコピー</span><span class="sxs-lookup"><span data-stu-id="0906c-221">Step 4: Download the PST Import tools and copy the SAS URL</span></span>

<span data-ttu-id="0906c-p121">Azure の RMS を構成し、PST ファイルを暗号化するために必要な Id を取得した、次に、ダウンロードして Office 365 を暗号化する手順 5 で実行して、ファイルのアップロードの PST のツールをインストールします。これらのツールは、Azure AzCopy ツールと Office 365 のデータの暗号化ツールです。組織の SA の URL をコピーすることもあります。この URL は、組織と共有アクセス署名 (SAS) キーをマイクロソフトのクラウド内の Azure ストレージ場所のネットワークの URL の組み合わせです。このキーは、Azure のストレージ場所に PST ファイルをアップロードする必要なアクセス許可を提供します。ファイルに保存、同じステップ 2 とステップ 3 で、その他の情報をコピーしたことです。述べたように、SAS の URL を保護するために予防措置を講じます。</span><span class="sxs-lookup"><span data-stu-id="0906c-p121">Now that you've configured Azure RMS and obtained the IDs necessary to encrypt PST files, the next step is to download and install the tools that you will run in Step 5 to encrypt and upload PST files to Office 365. These tools are the Azure AzCopy tool and the Office 365 Data Encryption tool. You'll also copy the SAS URL for your organization. This URL is a combination of the network URL for the Azure storage location in the Microsoft cloud for your organization and a Shared Access Signature (SAS) key. This key provides you with the necessary permissions to upload PST files to your Azure storage location. Save it to the same file that you've copied the other information to in Step 2 and Step 3. As previously stated, take precautions to protect the SAS URL.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0906c-p122">Azure ストレージの場所に PST ファイルを正常にアップロードするのには Azure AzCopy バージョン 5.0 を使用する必要があります。AzCopy ツールの新しいバージョンは、Office 365 に PST ファイルをインポートするためにサポートされていません。この手順の手順に従って、**ネットワーク経由でファイルのアップロード**ページから AzCopy ツールをダウンロードすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p122">You have to use Azure AzCopy version 5.0 to successfully upload PST files to the Azure storage location. Newer versions of the AzCopy tool aren't supported for importing PST files to Office 365. Be sure to download the AzCopy tool from the **Upload files over the network** page by following the procedures in this step.</span></span> 
  
1. <span data-ttu-id="0906c-232">[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="0906c-232">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="0906c-233">組織の Office 365 の管理者アカウントの資格情報を使用して Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0906c-233">Sign in to Office 365 using the credentials for an administrator account in your Office 365 organization.</span></span>
    
3. <span data-ttu-id="0906c-234">左側のウィンドウでは、**データ ・ ガバナンス**をクリックし、し、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-234">In the left pane, click **Data governance** and then click **Import**.</span></span>
    
4. <span data-ttu-id="0906c-235">**[インポート]** ページで、**[インポート サービスに移動する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-235">On the **Import** page, click **Go to the Import service**.</span></span>
    
5. <span data-ttu-id="0906c-236">**Office 365 へのデータのインポート**] ページで、[**新しいジョブ**] をクリックします![アイコンの追加](media/ITPro-EAC-AddIcon.gif)、**電子メール メッセージをアップロードする (PST ファイル)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-236">On the **Import data to Office 365** page, click **New job** ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then click **Upload email messages (PST files)**.</span></span>
    
6. <span data-ttu-id="0906c-237">**ネットワーク経由でファイルのアップロード**ページで、手順 2 では、**ネットワーク アップロード SAS の URL を表示する**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-237">On the **Upload files over the network** page, in step 2, click **Show network upload SAS URL**.</span></span>
    
7. <span data-ttu-id="0906c-p123">URL が表示されたら、コピーし、他のキーを保存したファイルに保存します。URL 全体をコピーすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p123">After the URL is displayed, copy it and save it in the file where you saved the other keys. Be sure to copy the entire URL.</span></span> 
    
8. <span data-ttu-id="0906c-240">手順 3 で、 **Azure の AzCopy ツールをダウンロード**をダウンロードして、Azure の AzCopy ツールをインストールする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-240">In step 3, click **Download the Azure AzCopy tool** to download and install the Azure AzCopy tool.</span></span> 
    
9. <span data-ttu-id="0906c-241">ポップアップ ウィンドウで、**[実行]** をクリックして、Azure AzCopy ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0906c-241">In the pop-up window, click **Run** to install the Azure AzCopy tool.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="0906c-p124">既定の場所に、Azure の AzCopy ツールをインストールしてください`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`のコンピューターで 64 ビットの Windows を実行しています。この場所で AzCopy ツールを探す手順 5 で、O365ImportTool.exe を実行するとためにです。</span><span class="sxs-lookup"><span data-stu-id="0906c-p124">Be sure to install the Azure AzCopy tool in the default location, which is `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy` on a computer running 64-bit Windows. That's because when you run the O365ImportTool.exe in Step 5, it looks for the AzCopy tool in this location.</span></span> 
  
10. <span data-ttu-id="0906c-244">Azure AzCopy ツールをインストールした後、 **Office 365 のデータの暗号化およびインポート ツールのダウンロード**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-244">After you've installed the Azure AzCopy tool, click **Download the Office 365 Data Encryption and Import tool**.</span></span>
    
11. <span data-ttu-id="0906c-245">ポップアップ ウィンドウで、[**保存**] をクリックします\>**として保存する**に O365ImportTool.zip ファイルをローカル コンピューター上のフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="0906c-245">In the pop-up window, click **Save** \> **Save as** to save the O365ImportTool.zip file to a folder on your local computer.</span></span> 
    
12. <span data-ttu-id="0906c-246">O365ImportTool.zip ファイルを抽出する。</span><span class="sxs-lookup"><span data-stu-id="0906c-246">Extract the O365ImportTool.zip file.</span></span>
    
13. <span data-ttu-id="0906c-247">**ネットワーク経由でファイルのアップロード**] ページを閉じます**キャンセル**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-247">Click **Cancel** to close the **Upload files over the network** page.</span></span> 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a><span data-ttu-id="0906c-248">手順 5: の暗号化し、PST ファイルを Office 365 にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0906c-248">Step 5: Encrypt and upload your PST files to Office 365</span></span>

<span data-ttu-id="0906c-p125">手順 4 から手順 1 が完了したら後、は、O365ImportTool.exe ツールを使用して暗号化して、Office 365 に PST ファイルをアップロードする準備が整ったら。このツールは、PST ファイルを暗号化しアップロードし、マイクロソフトのクラウドでは、Azure ストレージの場所に保存します。この手順を完了するには、PST ファイルをファイル共有や、組織内のファイル サーバーに配置する必要があります。これは、次の手順でソース ディレクトリと呼ばれます。O365ImportTool.exe ツールを実行するたびができるディレクトリを指定する別のソース。</span><span class="sxs-lookup"><span data-stu-id="0906c-p125">After you have completed Step 1 through Step 4, you're ready to use the O365ImportTool.exe tool to encrypt and upload PST files to Office 365. This tool encrypts your PST files and then uploads and stores them in an Azure storage location in the Microsoft cloud. To complete this step, the PST files have to be located in a file share or file server in your organization. This is known as the source directory in the following procedure. Each time you run the O365ImportTool.exe tool, you'll can specify a different source directory.</span></span> 
  
1. <span data-ttu-id="0906c-254">ローカル コンピューター上でコマンド プロンプトを開く。</span><span class="sxs-lookup"><span data-stu-id="0906c-254">Open a Command Prompt on your local computer.</span></span>
    
2. <span data-ttu-id="0906c-255">手順 4 で O365ImportTool.exe ツールをインストールしたディレクトリに移動する。</span><span class="sxs-lookup"><span data-stu-id="0906c-255">Go to the directory where you installed the O365ImportTool.exe tool in Step 4.</span></span>
    
3. <span data-ttu-id="0906c-256">暗号化し、Office 365 に PST ファイルをアップロードするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0906c-256">Run the following command to encrypt and upload PST files to Office 365.</span></span>
    
    ```
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    <span data-ttu-id="0906c-p126">次の表は、パラメーターとそれに必要な値を説明したものです。前の手順で取得した情報は、これらのパラメーターの値で使うことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-p126">The following table describes the parameters and their required values. Note that the information you obtained in the previous steps is used in the values for these parameters.</span></span>
    
    |<span data-ttu-id="0906c-259">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="0906c-259">**Parameter**</span></span>|<span data-ttu-id="0906c-260">**説明**</span><span class="sxs-lookup"><span data-stu-id="0906c-260">**Description**</span></span>|<span data-ttu-id="0906c-261">**例**</span><span class="sxs-lookup"><span data-stu-id="0906c-261">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |<span data-ttu-id="0906c-262">Office 365 にアップロードする PST ファイルを含む、組織内には、ソース ディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="0906c-262">Specifies the source directory in your organization that contains the PST files that will be uploaded to Office 365.</span></span>  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |<span data-ttu-id="0906c-p127">Azure の RMS サービスのライセンスの場所を指定します。値を使用して、`LicensingIntranetDistributionPointUrl`の手順 3 で取得したプロパティです。二重引用符では、このパラメーターの値を囲むことを確認する ("")</span><span class="sxs-lookup"><span data-stu-id="0906c-p127">Specifies the licensing location for your Azure RMS service. Use the value of the  `LicensingIntranetDistributionPointUrl` property that you obtained in Step 3. Be sure to surround the value of this parameter with double-quotation marks (" ")  </span></span><br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |<span data-ttu-id="0906c-p128">Azure の RMS の組織の id を指定します。値を使用して、`BPOSId`の手順 3 で取得したプロパティです。</span><span class="sxs-lookup"><span data-stu-id="0906c-p128">Specifies the identity of your Azure RMS organization. Use the value of the  `BPOSId` property that you obtained in Step 3.  </span></span><br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |<span data-ttu-id="0906c-p129">手順 2 で取得した対称キーを指定します。二重引用符では、このパラメーターの値を囲むことを確認する ("")。</span><span class="sxs-lookup"><span data-stu-id="0906c-p129">Specifies the symmetric key that you obtained in Step 2. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |<span data-ttu-id="0906c-p130">PST ファイルをネットワーク経由でアップロードまたは、ハード ドライブに付属しているかどうかを指定します。値`upload`、ネットワーク経由でファイルをアップロードすることを示します。値`drive`ハード ドライブ上の pst ファイルを配布することを示します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p130">Specifies whether you upload PST files over the network or ship them on a hard drive. The value  `upload` indicates that you are uploading the files over the network. The value  `drive` indicates that you are shipping the PSTs on a hard drive.  </span></span><br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |<span data-ttu-id="0906c-p131">PST ファイルのアップロードをするには Office 365 の宛先を指定します。これは、組織の Azure ストレージの場所です。このパラメーターの値は、手順 4 でコピーした SAS の URL から、ネットワークのアップロード URL で構成されています。二重引用符では、このパラメーターの値を囲むことを確認する ("")。</span><span class="sxs-lookup"><span data-stu-id="0906c-p131">Specifies the destination in Office 365 where your PST files will be uploaded to; this is the Azure storage location for your organization. The value for this parameter consists of the network upload URL from the SAS URL that you copied in Step 4. Be sure to surround the value of this parameter with double-quotation marks (" ").  </span></span><br/><br/> <span data-ttu-id="0906c-p132">**ヒント:**(省略可能)暗号化された PST ファイルをアップロードするのには Azure ストレージの場所にサブフォルダーを指定することができます。("Ingestiondata") の後にサブフォルダーの場所を追加するネットワークのアップロード URL でこれを行います。最初の例は、サブフォルダーを指定しません。つまり、pst ファイルには、Azure ストレージの場所の ( *ingestiondata*という名前) のルートにアップロードされます。2 番目の例では、Azure ストレージの場所に PST ファイルのフォルダー ( *EncryptedPSTs* ) をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0906c-p132">**Tip:** (Optional) You can specify a subfolder in the Azure storage location to upload the encrypted PST files to. You do this by adding a subfolder location (after "ingestiondata") in the network upload URL. The first example doesn't specify a subfolder; that means the PSTs will be uploaded to the root (named  *ingestiondata*  ) of the Azure storage location. The second example uploads the PST files to a subfolder (named  *EncryptedPSTs*  ) in the Azure storage location.</span></span>           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> <span data-ttu-id="0906c-280">または</span><span class="sxs-lookup"><span data-stu-id="0906c-280">Or</span></span>  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |<span data-ttu-id="0906c-p133">組織の SA のキーを指定します。このパラメーターの値は、手順 4 でコピーした SAS の URL から SA のキーで構成されます。SA のキーの最初の文字が疑問符 () であることを確認 ("?")。二重引用符では、このパラメーターの値を囲むことを確認する ("")。</span><span class="sxs-lookup"><span data-stu-id="0906c-p133">Specifies the SAS key for you organization. The value for this parameter consists of the SAS key from the SAS URL that you copied in Step 4. Note that first character in the SAS key is a question mark ("?"). Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |<span data-ttu-id="0906c-285">このオプション スイッチは、O365ImportTool.exe ツールがで指定されたソース ディレクトリ内のサブフォルダーにある Pst ファイルをコピーするために再帰的なモードを指定します`/srcdir:`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="0906c-285">This optional switch specifies the recursive mode so that the O365ImportTool.exe tool will copy PSTs files that are located in subfolders in the source directory that is specified by the  `/srcdir:` parameter.</span></span>  <br/><br/> <span data-ttu-id="0906c-p134">**注:** このスイッチを含める場合は、PST ファイルのサブフォルダーには、アップロードした Azure ストレージの場所に別のファイルのパス名があります。手順 7 で作成した CSV ファイルの正確なファイルのパス名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0906c-p134">**Note:** If you include this switch, PST files in subfolders will have a different file pathname in the Azure storage location after they're uploaded. You'll have to specify the exact file pathname in the CSV file that you create in Step 7.</span></span>           | `/recurse` <br/> |
   
    <span data-ttu-id="0906c-288">各パラメーターの実際の値を使用する O365ImportTool.exe ツールの構文の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="0906c-288">Here's an example of the syntax for the O365ImportTool.exe tool using actual values for each parameter:</span></span>
    
    ```
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    <span data-ttu-id="0906c-p135">コマンドを実行すると、PST ファイルの暗号化とアップロードの進行状況を示す状態メッセージが表示されます。最終の状態メッセージは、暗号化とアップロードが正常に完了したファイルの合計数を示しています。 </span><span class="sxs-lookup"><span data-stu-id="0906c-p135">After you run the command, status messages are displayed that show the progress of encrypting and uploading the PST files. A final status message shows the total number of files that were successfully encrypted and uploaded.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="0906c-p136">正常に O365ImportTool.exe コマンドを実行してすべてのパラメーターが正しいことを確認するものと同じ情報をコピーする (セキュリティで保護された) ファイルをコマンド ・ ライン構文のコピーを保存で取得した前の手順を実行します。できますをコピーし、貼り付けコマンド プロンプトでこのコマンドを暗号化し、Office 365 に PST ファイルをアップロードするには、O365ImportTool.exe ツールを実行するたびにします。ものは、値のみを変更する必要があります、`/srcdir:`と`/upload-dest:`のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="0906c-p136">After you successfully run the O365ImportTool.exe command and verify that all the parameters are correct, save a copy of the command line syntax to the same (secured) file where you copied the information you obtained in the previous steps. Then you can copy and paste this command in a Command Prompt each time that you want to run the O365ImportTool.exe tool to encrypt and upload PST files to Office 365. The only values you might have to change are the ones for the  `/srcdir:` and  `/upload-dest:` parameters.</span></span> 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a><span data-ttu-id="0906c-294">(省略可能)手順 6: Office 365 のビュー PST ファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="0906c-294">(Optional) Step 6: View a list of the PST files uploaded to Office 365</span></span>

<span data-ttu-id="0906c-p137">オプションの手順としてインストールし、Azure blob にアップロードしている PST ファイルの一覧を表示するのには、Azure ストレージ エクスプ ローラーは、無料のオープン ソースのツール) を使用できます。これを行う 3 つの理由があります。</span><span class="sxs-lookup"><span data-stu-id="0906c-p137">As an optional step, you can install and use the Microsoft Azure Storage Explorer (which is a free, open source tool) to view the list of the PST files that you've uploaded to the Azure blob. There are three good reasons to do this:</span></span>
  
- <span data-ttu-id="0906c-297">PST ファイルを共有フォルダーまたは組織内のファイル サーバーからが、Azure blob を正常にアップロードされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0906c-297">Verify that PST files from the shared folder or file server in your organization were successfully uploaded to the Azure blob.</span></span>

- <span data-ttu-id="0906c-p138">PST ファイルが暗号化されていることを確認します。暗号化された PST ファイルが、 `.pfile` 、PST ファイル名に追加した拡張子たとえば、 `pilarp.pst.pfile`。</span><span class="sxs-lookup"><span data-stu-id="0906c-p138">Verify that the PST files are encrypted. Encrypted PST files have a  `.pfile` extension appended to the PST filename; for example,  `pilarp.pst.pfile`.</span></span>
    
- <span data-ttu-id="0906c-p139">Azure blob にアップロードされた各 PST ファイルのファイル名 (および 1 つ含まれている場合、サブフォルダーのパス名) を確認します。各 PST ファイルのファイル名とフォルダーのパス名を指定する必要があるために、次の手順でファイルをマッピングする pst ファイルを作成するときに非常に便利です。これらの名前を確認すると、PST のマッピング ・ ファイル内の潜在的なエラーを削減できます。</span><span class="sxs-lookup"><span data-stu-id="0906c-p139">Verify the filename (and the subfolder pathname if you included one) for each PST file uploaded to the Azure blob. This is really helpful when you're creating the PST mapping file in the next step because you have to specify both the folder pathname and filename for each PST file. Verifying these names can help reduce potential errors in your PST mapping file.</span></span>
    
<span data-ttu-id="0906c-303">プレビューでは、Microsoft Azure ストレージ エクスプ ローラーです。</span><span class="sxs-lookup"><span data-stu-id="0906c-303">The Microsoft Azure Storage Explorer is in Preview.</span></span> 
  
 > [!IMPORTANT]
>  <span data-ttu-id="0906c-p140">アップロードまたは PST ファイルを変更するには、Azure ストレージ エクスプ ローラーを使うことはできません。Office 365 に PST ファイルをインポートするための唯一のサポートされている方法では、AzCopy を使用します。また、Azure blob にアップロードしている PST ファイルを削除できません。PST ファイルを削除しようとすると、必要な権限がないというエラー メッセージが表示されます。Azure ストレージ領域からすべての PST ファイルを自動的に削除するに注意してください。ある場合、すべて PST ファイルの**ingestiondata**コンテナーには、進行中のインポート ジョブは削除されません、最新のインポート ジョブを作成した後 30 日間。</span><span class="sxs-lookup"><span data-stu-id="0906c-p140">You can't use the Azure Storage Explorer to upload or modify PST files. The only supported method for importing PST files to Office 365 is to use AzCopy. Also, you can't delete PST files that you've uploaded to the Azure blob. If you try to delete a PST file, you'll receive an error about not having the required permissions. Note that all PST files are automatically deleted from your Azure storage area. If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created.</span></span> 
  
<span data-ttu-id="0906c-310">Azure ストレージ エクスプ ローラーをインストールし、Azure のストレージ領域への接続します。</span><span class="sxs-lookup"><span data-stu-id="0906c-310">To install the Azure Storage Explorer and connect to your Azure storage area:</span></span>
  
1. <span data-ttu-id="0906c-311">ダウンロードして、 [Microsoft Azure ストレージ エクスプ ローラー ツール](https://go.microsoft.com/fwlink/p/?LinkId=544842)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0906c-311">Download and install the [Microsoft Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span>
    
2. <span data-ttu-id="0906c-312">Microsoft Azure ストレージ エクスプ ローラーを起動左側のウィンドウで、**ストレージ アカウント**を右クリックし、 **Azure ストレージへの接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-312">Start the Microsoft Azure Storage Explorer, right-click **Storage Accounts** in the left pane, and then click **Connect to Azure storage**.</span></span> 
    
    ![ストレージ アカウントを右クリックし、Azure ストレージに接続] をクリックし、](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. <span data-ttu-id="0906c-314">[ **Azure ストレージに接続する]** ボックスで、手順 4 で取得した SAS の URL を貼り付けるし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-314">In the box under **Connect to Azure storage**, paste the SAS URL that you obtained in Step 4, and then click **Next**.</span></span> 
    
    ![Azure ストレージのページへの接続] ボックスに、SAS の URL を貼り付ける](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. <span data-ttu-id="0906c-316">[**接続の概要**] ページで、接続情報を確認し、[**接続**] をクリックできます。</span><span class="sxs-lookup"><span data-stu-id="0906c-316">On the **Connection summary** page, you can review the connection information, and then click **Connect**.</span></span> 
    
5. <span data-ttu-id="0906c-317">[**ストレージ アカウント**] でノードを展開します **(サービスの SAS)** と**Blob コンテナー**ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="0906c-317">Under **Storage Accounts**, expand the **(Service SAS)** node, and then expand the **Blob Containers** node.</span></span> 
    
6. <span data-ttu-id="0906c-318">**Ingestiondata**を右クリックし、 **Blob コンテナー エディターを開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-318">Right-click **ingestiondata**, and then click **Open Blob Container Editor**.</span></span>
    
    ![ingestiondata を右クリックし、[Blob コンテナー エディターを開く] をクリックする](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    <span data-ttu-id="0906c-320">Azure ストレージ領域、手順 5 でアップロードしている PST ファイルの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0906c-320">The Azure storage area, with a list of the PST files that you uploaded in Step 5 is displayed.</span></span>
    
    ![Azure ストレージ エクスプローラーには、アップロードした PST ファイルの一覧が表示される](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. <span data-ttu-id="0906c-p141">Microsoft Azure ストレージ エクスプ ローラーの使用が終了したら、 **ingestiondata**を右クリックし、Azure のストレージ領域から切断するのには**接続解除**] をクリックします。それ以外の場合、次に接続しようとするとき、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0906c-p141">When you're finished using the Microsoft Azure Storage Explorer, right-click **ingestiondata**, and then click **Detach** to disconnect from your Azure storage area. Otherwise, you'll receive an error the next time you try to attach.</span></span> 
    
    ![ingestion を右クリックして [デタッチ] をクリックし、Azure のストレージ エリアから切断する](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a><span data-ttu-id="0906c-325">PST インポート マッピング ファイルを作成する手順 7。</span><span class="sxs-lookup"><span data-stu-id="0906c-325">Step 7: Create the PST Import mapping file</span></span>

<span data-ttu-id="0906c-p142">PST ファイルは、暗号化され、組織の Office 365 の Azure ストレージの場所にアップロードされたが後、次に、PST ファイルはインポートできません、ユーザーのメールボックスを指定する値 (CSV) ファイルを区切るコンマを作成します。PST インポート ジョブを作成するときは、次の手順では、この CSV ファイルが送信されます。</span><span class="sxs-lookup"><span data-stu-id="0906c-p142">After the PST files have been encrypted and uploaded to the Azure storage location for your Office 365 organization, the next step is to create a comma separated value (CSV) file that specifies which user mailboxes the PST files will be imported to. You will submit this CSV file in the next step when you create a PST Import job.</span></span>
  
1. <span data-ttu-id="0906c-328">[PST インポート マッピング ・ ファイルのコピーをダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=544717)します。</span><span class="sxs-lookup"><span data-stu-id="0906c-328">[Download a copy of the PST Import mapping file](https://go.microsoft.com/fwlink/p/?LinkId=544717).</span></span> 
    
2. <span data-ttu-id="0906c-p143">CSV ファイルを開くか、ローカル コンピューターに保存します。次の例は、完了した PST インポートのマッピング ファイル (メモ帳で開いた) を示しています。Microsoft Excel を使って CSV ファイルを編集するほうが、はるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="0906c-p143">Open or save the CSV file to your local computer. The following example shows a completed PST Import mapping file (opened in NotePad). It's much easier to use Microsoft Excel to edit the CSV file.</span></span>
    
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

    <span data-ttu-id="0906c-p144">最初の行、または CSV ファイルのヘッダー行は、PST ファイルをユーザーのメールボックスにインポートする PST インポート サービスによって使用されるパラメーターを一覧表示します。各パラメーター名は、コンマで区切られます。ヘッダー行の下の各行は、特定のメールボックスを PST ファイルをインポートするためのパラメーター値を表します。行は、各ユーザーのメールボックスにインポートする PST ファイルの必要があります。マッピング ファイル内のプレース ホルダーのデータを実際のデータに置き換えることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p144">The first row, or header row, of the CSV file lists the parameters that will be used by the PST Import service to import the PST files to user mailboxes. Each parameter name is separated by a comma. Each row under the header row represents the parameter values for importing a PST file to a specific mailbox. You will need a row for each PST file that you want to import to a user mailbox. Be sure to replace the placeholder data in the mapping file with your actual data.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0906c-337">SharePoint パラメーターなど、ヘッダー行は何も変更しないでください。これらは PST インポートの処理中、無視されます。</span><span class="sxs-lookup"><span data-stu-id="0906c-337">Don't change anything in the header row, including the SharePoint parameters; they will be ignored during the PST Import process.</span></span> 
  
3. <span data-ttu-id="0906c-338">次の表の情報を使って、必要な情報を含む CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0906c-338">Use the information in the following table to populate the CSV file with the required information.</span></span>
    
    |<span data-ttu-id="0906c-339">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="0906c-339">**Parameter**</span></span>|<span data-ttu-id="0906c-340">**説明**</span><span class="sxs-lookup"><span data-stu-id="0906c-340">**Description**</span></span>|<span data-ttu-id="0906c-341">**例**</span><span class="sxs-lookup"><span data-stu-id="0906c-341">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `Workload` <br/> |<span data-ttu-id="0906c-p145">Office 365 サービスにインポートするデータを指定します。PST ファイルをユーザーのメールボックスにインポートするを使用して、 `Exchange`。</span><span class="sxs-lookup"><span data-stu-id="0906c-p145">Specifies the Office 365 service that data will be imported to. To import PST files to user mailboxes, use  `Exchange`.  </span></span><br/> | `Exchange` <br/> |
    | `FilePath` <br/> |<span data-ttu-id="0906c-344">手順 5 で PST ファイルをアップロードした Azure ストレージの場所にフォルダーの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="0906c-344">Specifies the folder location in the Azure storage location that you uploaded the PST files to in Step 5.</span></span>  <br/>  <span data-ttu-id="0906c-p146">ネットワークの URL を任意のサブフォルダーの名前が含まれていないかどうか、`/upload-dest:`パラメーターでは、手順 5 では、空白のままにこのパラメーターで CSV ファイルです。サブフォルダー名を入力した場合、このパラメーターに値を指定します。このパラメーターの値は、大文字小文字を区別します。*どちらにしてがの値に"ingestiondata"を含まない*、`FilePath`のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="0906c-p146">If you didn't include an optional subfolder name in the network URL in the  `/upload-dest:` parameter in Step 5, leave this parameter blank in the CSV file. If you included a subfolder name, specify it in this parameter. The value for this parameter is case sensitive. Either way,  *don't*  include "ingestiondata" in the value for the  `FilePath` parameter.  </span></span><br/> <br/><span data-ttu-id="0906c-p147">**重要な:** ファイルのパス名の大文字と小文字に SAS の URL を任意のサブフォルダーの名前が含まれている場合に使用した同じ大文字と小文字にする必要があります、`/upload-dest:`手順 5 でのパラメーターです。使用した場合など、 `EncryptedPSTs` 、サブフォルダー名を手順 5 で、使用して`encryptedpsts`で、 `FilePath` CSV ファイル内のパラメーター、PST ファイルのインポートは失敗します。両方のインスタンスで、同じ大文字と小文字を使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p147">**Important:** The case for the file path name must be the same case that you used if you included an optional subfolder name in the SAS URL in the  `/upload-dest:` parameter in Step 5. For example, if you used  `EncryptedPSTs` for the subfolder name in Step 5 and then use  `encryptedpsts` in the  `FilePath` parameter in CSV file, the import for the PST file will fail. Be sure to use the same case in both instances.</span></span>           |<span data-ttu-id="0906c-352">(空白)</span><span class="sxs-lookup"><span data-stu-id="0906c-352">(leave blank)</span></span>  <br/> <span data-ttu-id="0906c-353">または</span><span class="sxs-lookup"><span data-stu-id="0906c-353">Or</span></span>  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |<span data-ttu-id="0906c-p148">ユーザーのメールボックスにインポートする PST ファイルの名前を指定します。このパラメーターの値は、大文字小文字を区別します。Azure ストレージの場所にアップロードされた PST ファイルが暗号化されているため、 `.pfile` PST ファイル名に拡張子が追加されます。追加する必要があります、 `.pfile` pst ファイルの名前に拡張子のファイルを CSV ファイルにします。</span><span class="sxs-lookup"><span data-stu-id="0906c-p148">Specifies the name of the PST file that will be imported to the user mailbox. The value for this parameter is case sensitive. Because the PST files that are uploaded to the Azure storage location are encrypted, a  `.pfile` extension is added to the PST filename. You must add the  `.pfile` extension to the name of the PST files in the CSV file.  </span></span><br/><br/> <span data-ttu-id="0906c-p149">**重要な:** CSV ファイル内の PST ファイル名の大文字と小文字は、手順 5 で Azure ストレージの場所にアップロードされた PST ファイルと同じである必要があります。使用する場合など、`annb.pst.pfile`で、 `Name` 、CSV ファイルが実際の PST ファイルの名前のパラメーターは、 `AnnB.pst`、その PST ファイルのインポートは失敗します。CSV ファイルに pst ファイルの名前が実際の PST ファイルと同じ大文字と小文字を使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p149">**Important:** The case for the PST file name in the CSV file must be the same as the PST file that was uploaded to the Azure storage location in Step 5. For example, if you use  `annb.pst.pfile` in the  `Name` parameter in the CSV file, but the name of the actual PST file is  `AnnB.pst`, the import for that PST file will fail. Be sure that the name of the PST in the CSV file uses the same case as the actual PST file.</span></span>           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |<span data-ttu-id="0906c-361">PST ファイルのインポート先になるメールボックスのメール アドレスを指定します。 </span><span class="sxs-lookup"><span data-stu-id="0906c-361">Specifies the email address of the mailbox that the PST file will be imported to.</span></span>  <br/> <span data-ttu-id="0906c-p150">非アクティブなメールボックスに PST ファイルをインポートするのにはこのパラメーターにメールボックスの GUID を指定する必要です。この GUID を取得するには、Exchange Online で次の PowerShell コマンドを実行します: ' Get メールボックス InactiveMailboxOnly。<identity of inactive mailbox></span><span class="sxs-lookup"><span data-stu-id="0906c-p150">To import a PST file to an inactive mailbox, you have to specify the mailbox GUID for this parameter. To obtain this GUID, run the following PowerShell command in Exchange Online:  \`Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox></span></span> | <span data-ttu-id="0906c-364">FL Guid` <br/><br/> **Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-メールボックス -<identity of active mailbox></span><span class="sxs-lookup"><span data-stu-id="0906c-364">FL Guid` <br/><br/> **Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox - <identity of active mailbox></span></span> | <span data-ttu-id="0906c-365">FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get ・ メールボックス ・ <identity of soft-deleted or inactive mailbox> ・ SoftDeletedMailbox</span><span class="sxs-lookup"><span data-stu-id="0906c-365">FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox</span></span> | <span data-ttu-id="0906c-366">FL Guid'</span><span class="sxs-lookup"><span data-stu-id="0906c-366">FL Guid\`</span></span>           | `annb@contoso.onmicrosoft.com` <br/> <span data-ttu-id="0906c-367">または</span><span class="sxs-lookup"><span data-stu-id="0906c-367">Or</span></span>  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | <span data-ttu-id="0906c-p151">PST ファイルをユーザーのアーカイブ メールボックスにインポートするかどうかを指定します。次のような 2 つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="0906c-p151">Specifies whether or not to import the PST file to the user's archive mailbox. There are two options:  </span></span><br/> <span data-ttu-id="0906c-370">**FALSE**PST ファイルをユーザーのプライマリ メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="0906c-370">**FALSE** Imports the PST file to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="0906c-371">**場合は TRUE。** PST ファイルをユーザーのアーカイブ メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="0906c-371">**TRUE** Imports the PST file to the user's archive mailbox.</span></span>  <br/>  <span data-ttu-id="0906c-372">このパラメーターを空白のままにすると、PST ファイルは、ユーザーのプライマリ メールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="0906c-372">If you leave this parameter blank, the PST file is imported to the user's primary mailbox.</span></span>  <br/><br/> <span data-ttu-id="0906c-373">**注:** クラウド ベースのアーカイブ メールボックスがプライマリ メールボックスは、オンプレミス ユーザーの PST ファイルをインポートするにだけこのパラメーターに**TRUE**を指定しのユーザーのオンプレミスのメールボックスの電子メール アドレスを指定します`Mailbox`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="0906c-373">**Note:** To import a PST file to a cloud-based archive mailbox for a user whose primary mailbox is on-premises, just specify **TRUE** for this parameter and specify the email address for the user's on-premises mailbox for the  `Mailbox` parameter.</span></span>           | `FALSE` <br/> <span data-ttu-id="0906c-374">または</span><span class="sxs-lookup"><span data-stu-id="0906c-374">Or</span></span>  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | <span data-ttu-id="0906c-375">PST ファイルをインポートするメールボックス フォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="0906c-375">Specifies the mailbox folder that the PST file is imported to.</span></span>  <br/>  <span data-ttu-id="0906c-376">このパラメーターを空白のままにする場合は、**インポート済み**の名前付きの ([受信トレイ] フォルダーおよびその他の既定のメールボックス フォルダーと同じレベル) のメールボックスのルート レベルに新しいフォルダーを pst ファイルがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="0906c-376">If you leave this parameter blank, the PST will be imported to a new folder named **Imported** located at the root level of the mailbox (the same level as the Inbox folder and the other default mailbox folders).</span></span>  <br/>  <span data-ttu-id="0906c-377">指定する場合は、 `/`、PST ファイル内の項目をユーザーの受信トレイ フォルダーに直接インポートされます。</span><span class="sxs-lookup"><span data-stu-id="0906c-377">If you specify  `/`, items in the PST file will be imported directly in to the user's Inbox folder.</span></span>  <br/>  <span data-ttu-id="0906c-p152">指定する場合は、 `/<foldername>`、という名前のサブフォルダーをインポートする PST ファイルのアイテム*\<フォルダー名\>*。使用した場合など、 `/ImportedPst`、 **ImportedPst**をという名前のサブフォルダーにアイテムをインポートするとします。このサブフォルダーは、ユーザーの受信トレイ フォルダーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="0906c-p152">If you specify  `/<foldername>`, items in the PST file will be imported to a subfolder named  *\<foldername\>*  . For example, if you used  `/ImportedPst`, items would be imported to a subfolder named **ImportedPst**. This subfolder will be located in the user's Inbox folder.  </span></span><br/><br/> <span data-ttu-id="0906c-381">**ヒント:** Pst ファイルをインポートするのには最適なフォルダーの場所を特定できるように、このパラメーターを実験するのには、いくつかのテスト バッチを実行することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-381">**Tip:** Consider running a few test batches to experiment with this parameter so you can determine the best folder location to import PSTs files to.</span></span>           |<span data-ttu-id="0906c-382">(空白)</span><span class="sxs-lookup"><span data-stu-id="0906c-382">(leave blank)</span></span>  <br/> <span data-ttu-id="0906c-383">または</span><span class="sxs-lookup"><span data-stu-id="0906c-383">Or</span></span>  <br/>  `/` <br/> <span data-ttu-id="0906c-384">または</span><span class="sxs-lookup"><span data-stu-id="0906c-384">Or</span></span>  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |<span data-ttu-id="0906c-p153">この省略可能なパラメーターでは、ANSI のファイル形式の PST ファイルのインポートに使用するコード ページの数値を指定します。これらの言語が文字をエンコードするための 2 バイト文字セット (DBCS) を通常使用されるため、中国語、日本語、韓国語 (CJK) の組織から PST ファイルをインポートするため、このパラメーターが使用されます。メールボックス フォルダーの名前に DBCS を使用する言語の PST ファイルをインポートするのにはこのパラメーターを使用していない場合は、フォルダー名を多くの場合文字化けする、インポートした後。このパラメーターを使用するのにはサポートされている値のリストは、[コード ページの識別子](https://go.microsoft.com/fwlink/p/?LinkId=328514)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-p153">This optional parameter specifies a numeric value for the code page to use for importing PST files in the ANSI file format. This parameter is used for importing PST files from Chinese, Japanese, and Korean (CJK) organizations because these languages typically use a double byte character set (DBCS) for character encoding. If this parameter isn't used to import PST files for languages that use DBCS for mailbox folder names, the folder names are often garbled after they're imported. For a list of supported values to use for this parameter, see [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).  </span></span><br/><br/> <span data-ttu-id="0906c-p154">**注:** 前に述べたように、これは、オプションのパラメーターと、CSV ファイルに含めるようにする必要はありません。または追加して値を 1 つまたは複数の行の空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="0906c-p154">**Note:** As previously stated, this is an optional parameter and you don't have to include it in the CSV file. Or you can include it and leave the value blank for one or more rows.</span></span>           |<span data-ttu-id="0906c-391">(空白)</span><span class="sxs-lookup"><span data-stu-id="0906c-391">(leave blank)</span></span>  <br/> <span data-ttu-id="0906c-392">または</span><span class="sxs-lookup"><span data-stu-id="0906c-392">Or</span></span>  <br/>  <span data-ttu-id="0906c-393">`932`(日本語版 ANSI と OEM のコード ページの id です)</span><span class="sxs-lookup"><span data-stu-id="0906c-393">`932` (which is the code page identifier for ANSI/OEM Japanese)</span></span>  <br/> |
    | `SPFileContainer` <br/> |<span data-ttu-id="0906c-394">PST インポートの場合は、このパラメーターを空白のままにします。 </span><span class="sxs-lookup"><span data-stu-id="0906c-394">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="0906c-395">該当なし</span><span class="sxs-lookup"><span data-stu-id="0906c-395">Not applicable</span></span>  <br/> |
    | `SPManifestContainer` <br/> |<span data-ttu-id="0906c-396">PST インポートの場合は、このパラメーターを空白のままにします。 </span><span class="sxs-lookup"><span data-stu-id="0906c-396">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="0906c-397">該当なし</span><span class="sxs-lookup"><span data-stu-id="0906c-397">Not applicable</span></span>  <br/> |
    | `SPSiteUrl` <br/> |<span data-ttu-id="0906c-398">PST インポートの場合は、このパラメーターを空白のままにします。 </span><span class="sxs-lookup"><span data-stu-id="0906c-398">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="0906c-399">該当なし</span><span class="sxs-lookup"><span data-stu-id="0906c-399">Not applicable</span></span>  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a><span data-ttu-id="0906c-400">手順 8:Office 365 で PST インポート ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="0906c-400">Step 8: Create a PST Import job in Office 365</span></span>

<span data-ttu-id="0906c-p155">最後のステップでは、Office 365 のサービスのインポートの PST のインポート ジョブを作成します。手順 7 で作成した PST インポート マッピング ファイルを提出する前に説明したようです。インポート サービスが、解除するようマッピング ファイルの情報を使用して新しいジョブを作成した後に暗号化し、PST ファイル (手順 5 で Office 365 にアップロードした場合) を指定したユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="0906c-p155">The last step is to create the PST Import job in the Import service in Office 365. As previously explained, you will submit the PST Import mapping file that you created in Step 7. After you create the new job, the Import service will use the information in the mapping file to un-encrypt and import the PST files (that you uploaded to Office 365 in Step 5) to the specified user mailbox.</span></span> 
  
1. <span data-ttu-id="0906c-404">[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="0906c-404">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="0906c-405">組織の Office 365 の管理者アカウントの資格情報を使用して Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0906c-405">Sign in to Office 365 using the credentials for an administrator account in your Office 365 organization.</span></span>
    
3. <span data-ttu-id="0906c-406">左側のウィンドウでは、**データ ・ ガバナンス**をクリックし、し、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-406">In the left pane, click **Data governance** and then click **Import**.</span></span>
    
4. <span data-ttu-id="0906c-407">**[インポート]** ページで、**[インポート サービスに移動する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-407">On the **Import** page, click **Go to the Import service**.</span></span>
    
5. <span data-ttu-id="0906c-408">**Office 365 へのデータのインポート**] ページで、[**新しいジョブ**] をクリックします![アイコンの追加](media/ITPro-EAC-AddIcon.gif)、**電子メール メッセージをアップロードする (PST ファイル)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-408">On the **Import data to Office 365** page, click **New job**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then click **Upload email messages (PST files)**.</span></span>
    
6. <span data-ttu-id="0906c-409">**[ネットワーク経由でファイルをアップロードする]** ページで、**[ファイルのアップロードが完了しました]** と **[マッピング ファイルにアクセスできます]** の各チェック ボックスを選択して、**[次へ]** をクリックします。 </span><span class="sxs-lookup"><span data-stu-id="0906c-409">On the **Upload files over the network** page, click the **I'm done uploading my files** and **I have access to the mapping file** check boxes, and then click **Next**.</span></span> 
    
7. <span data-ttu-id="0906c-410">PST インポート ジョブの名前を入力し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0906c-410">Type a name for the PST Import job, and then click **Next**.</span></span>
    
8. <span data-ttu-id="0906c-411">[**追加**] をクリックして![アイコンの追加](media/ITPro-EAC-AddIcon.gif)手順 7 で作成したマッピングの PST ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="0906c-411">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) to select the PST Mapping file that you created in Step 7.</span></span> 
    
9. <span data-ttu-id="0906c-412">CSV ファイルの名前が一覧に表示されたら、CSV ファイルを選択して **[検証]** をクリックし、CSV ファイルにエラーがないか確認します。 </span><span class="sxs-lookup"><span data-stu-id="0906c-412">After the name of the CSV file appears in the list, select it and then click **Validate** to check your CSV file for errors.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0906c-p156">前に説明すると、PST ファイルが暗号化されている場合、 `.pfile` PST ファイル名に拡張子が追加されます。追加する必要があります、 `.pfile` pst ファイルの名前に拡張子のファイルを CSV ファイルにします。ない場合は、CSV ファイルの検証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p156">As previous explained, when the PST files are encrypted, a  `.pfile` extension is appended to the PST filename. You must add the  `.pfile` extension to the name of the PST files in the CSV file. If you don't, the validation of the CSV file will fail.</span></span> 
  
    <span data-ttu-id="0906c-p157">PST インポート ジョブを作成するには、CSV ファイルが正常に検証される必要があります。検証が失敗した場合は、**[状態]** 列の **[無効]** リンクをクリックします。PST インポートのマッピング ファイルのコピーが開き、失敗したファイル内の各行ごとにエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0906c-p157">The CSV file has to be successfully validated to create a PST Import job. If the validation fails, click the **Invalid** link in the **Status** column. A copy of your PST Import mapping file is opened, with a error message for each row in the file that failed.</span></span> 
    
10. <span data-ttu-id="0906c-419">PST のマッピング ファイルが正常に検証されたら、ご契約条件を読み、チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0906c-419">When the PST mapping file is successfully validated, read the terms and conditions document, and then click the checkbox.</span></span>
    
11. <span data-ttu-id="0906c-420">**[完了]** をクリックして、ジョブを送信します。</span><span class="sxs-lookup"><span data-stu-id="0906c-420">Click **Finish** to submit the job.</span></span> 
    
    <span data-ttu-id="0906c-421">ジョブは、 **Office 365 へのデータのインポート**] ページで、PST のインポート ジョブの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0906c-421">The job is displayed in the list of PST Import jobs on the **Import data to Office 365** page.</span></span> 
    
12. <span data-ttu-id="0906c-422">ジョブを選択し、[**更新**] をクリックして![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif)詳細ペインに表示されるステータス情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="0906c-422">Select the job and click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the status information that's displayed in the details pane.</span></span> 
    
13. <span data-ttu-id="0906c-423">詳細ウィンドウで、**[詳細の表示]** をクリックして、選択したジョブの最新の状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="0906c-423">In the details pane, click **View details** to get the latest status for the selected job.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="0906c-424">詳細情報</span><span class="sxs-lookup"><span data-stu-id="0906c-424">More information</span></span>

- <span data-ttu-id="0906c-425">理由 PST ファイルを Office 365 にインポートしますか。</span><span class="sxs-lookup"><span data-stu-id="0906c-425">Why import PST files to Office 365?</span></span>
    
  - <span data-ttu-id="0906c-426">組織の電子メールを Office 365 に移行する良い方法です。</span><span class="sxs-lookup"><span data-stu-id="0906c-426">It's a good way to migrate your organization's email to Office 365.</span></span>
    
  - <span data-ttu-id="0906c-427">次のことが可能になるので、組織のコンプライアンスのニーズに対応するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0906c-427">It helps address compliance needs of your organization by letting you:</span></span>
    
  - <span data-ttu-id="0906c-428">アーカイブ メールボックスを有効にして、追加のメールボックス容量をユーザーに提供する。</span><span class="sxs-lookup"><span data-stu-id="0906c-428">Enable archive mailboxes to give users additional mailbox storage space.</span></span>
    
  - <span data-ttu-id="0906c-429">メールボックスを保持状態にして、コンテンツを保持する。</span><span class="sxs-lookup"><span data-stu-id="0906c-429">Place mailboxes on hold to preserve content.</span></span>
    
  - <span data-ttu-id="0906c-430">Microsoft 電子情報開示ツールを使って、メールボックスのコンテンツを検索する。</span><span class="sxs-lookup"><span data-stu-id="0906c-430">Use Microsoft eDiscovery tools to search for content in mailboxes.</span></span>
    
  - <span data-ttu-id="0906c-431">アイテム保持ポリシーを使って、メールボックスのコンテンツの保持期間を制御する。</span><span class="sxs-lookup"><span data-stu-id="0906c-431">Use retention policies to control how long mailbox content is retained.</span></span>
    
  - <span data-ttu-id="0906c-432">Office 365 の監査ログ メールボックスに関連するイベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="0906c-432">Search the Office 365 audit log for mailbox-related events.</span></span>
    
  - <span data-ttu-id="0906c-p158">データの損失に対する保護に役立ちます。Office 365 のメールボックスにインポートする PST ファイルは、ユーザーのコンピューターにデータを格納するのではなく、オンラインの Exchange の高可用性機能を継承します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p158">It helps protect against data loss. PST files that are imported to Office 365 mailboxes inherit the high availability features of Exchange Online, as opposed to storing the data on a user's computer.</span></span>
    
  - <span data-ttu-id="0906c-435">データがクラウドに格納されるので、ユーザーはあらゆるデバイスからデータを利用できます。</span><span class="sxs-lookup"><span data-stu-id="0906c-435">The data is available to the user from all devices because it's stored in the cloud.</span></span>
    
- <span data-ttu-id="0906c-p159">ここでは、キー、Id、および 2、3、および 4 の手順で取得した Url の例です。この例では、暗号化するために O365ImportTool.exe ツールを実行して、アップロードの PST ファイルを Office 365 にするコマンドの構文も含まれています。パスワードやその他のセキュリティに関連する情報を保護するようにこれらだけを保護する対策を講じていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p159">Here's an example of the keys, IDs, and URLs that are obtained in Steps 2, 3, and 4. This example also contains the syntax for the command that you run in the O365ImportTool.exe tool to encrypt and upload PST files to Office 365. Be sure to take precautions to protect these just like you would protect passwords or other security-related information.</span></span>
    
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

- <span data-ttu-id="0906c-p160">説明したよう Office 365 のインポート サービスをオンに設定 (不定の期間) のメールボックスを PST ファイルをインポートした後に保持します。つまり、 *RentionHoldEnabled*プロパティに設定されて`True`メールボックスに割り当てられているリテンション ・ ポリシーを処理しないようにします。これには、削除したり、古いメッセージをアーカイブするアーカイブ ポリシーの削除を防止することで、新しくインポートされたメッセージを管理するためにメールボックス所有者の時間が与えられます。この保持を管理するためのいくつかの手順を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="0906c-p160">As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RentionHoldEnabled*  property is set to  `True` so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold:</span></span> 
    
  - <span data-ttu-id="0906c-p161">後、一定時間、オフにできます、保存を実行して、`Set-Mailbox -RetentionHoldEnabled $false`コマンドです。手順については、[保存上のメールボックスの場所を保持](https://go.microsoft.com/fwlink/p/?LinkId=544749)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-p161">After a certain period of time, you can turn off the retention hold by running the  `Set-Mailbox -RetentionHoldEnabled $false` command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).</span></span>
    
  - <span data-ttu-id="0906c-p162">無効になって、将来的にいくつかの日付にするため、保持を構成できます。これを実行するのには、`Set-Mailbox -EndDateForRetentionHold <date>`コマンドです。たとえば、今日の日付は 2016 年 7 月 1 日、30 日以内にオフに保持する、ことを前提としては、次のコマンドを実行、: `Set-Mailbox -EndDateForRetentionHold 8/1/2016`。このシナリオでは、 *RentionHoldEnabled*プロパティに設定のままに`True`。詳細については、[一連のメールボックス](https://go.microsoft.com/fwlink/p/?LinkId=150317)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-p162">You can configure the retention hold so that it's turned off on some date in the future. You do this by running the  `Set-Mailbox -EndDateForRetentionHold <date>` command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. In this scenario, you would leave the  *RentionHoldEnabled*  property set to `True`. For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).</span></span>
    
  - <span data-ttu-id="0906c-p163">できるように、すぐに削除またはユーザーのアーカイブ メールボックスに移動しないインポートされた古いアイテムは、メールボックスに割り当てられているリテンション ・ ポリシーの設定を変更することができます。たとえば、削除またはアーカイブ メールボックスに割り当てられているポリシーの保有期間を長く可能性があります。このシナリオでは無効にするメールボックスに保持リテンション ・ ポリシーの設定を変更した後。詳細については、 [Office 365 の組織内のメールボックスのアーカイブと削除ポリシーの設定](set-up-an-archive-and-deletion-policy-for-mailboxes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0906c-p163">You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>
