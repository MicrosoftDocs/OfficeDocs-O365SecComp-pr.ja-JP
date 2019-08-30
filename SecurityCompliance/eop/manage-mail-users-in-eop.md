---
title: EOP でメール ユーザーを管理する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: メール ユーザーの定義は、Exchange Online Protection (EOP) サービスを管理する上で重要な部分です。
ms.openlocfilehash: 48d530be17a7e75f6e179a50067b1b9526606cb0
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676717"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="a3575-103">EOP でメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="a3575-103">Manage mail users in EOP</span></span>

<span data-ttu-id="a3575-p101">メール ユーザーの定義は、Exchange Online Protection (EOP) サービスを管理する上で重要な部分です。EOP でユーザーを管理するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="a3575-p101">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service. There are several ways that you can manage users in EOP:</span></span>
  
- <span data-ttu-id="a3575-106">ディレクトリ同期を使用してメールユーザーを管理する: 社内の Active Directory 環境に既存のユーザーアカウントがある場合は、それらのアカウントを Azure Active Directory (AD) と同期することができます。これにより、アカウントのコピーがクラウドに保存されます。</span><span class="sxs-lookup"><span data-stu-id="a3575-106">Use directory synchronization to manage mail users: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud.</span></span> <span data-ttu-id="a3575-107">既存のユーザーアカウントを Azure Active Directory と同期する場合は、Exchange 管理センター (EAC) の [**受信者**] ウィンドウで、それらのユーザーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a3575-107">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC).</span></span> <span data-ttu-id="a3575-108">ディレクトリ同期の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3575-108">Using directory synchronization is recommended.</span></span> 

- <span data-ttu-id="a3575-109">EAC を使用してメール ユーザーを管理する: EAC で直接メール ユーザーを追加して管理します。</span><span class="sxs-lookup"><span data-stu-id="a3575-109">Use the EAC to manage mail users: Add and manage mail users directly in the EAC.</span></span> <span data-ttu-id="a3575-110">これは、メール ユーザーを追加する最も簡単な方法で、一度に 1 ユーザーを追加する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a3575-110">This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>

- <span data-ttu-id="a3575-111">リモートの Windows PowerShell を使用してメール ユーザーを管理するには: リモートの Windows PowerShell を実行してメール ユーザーを追加し、管理します。</span><span class="sxs-lookup"><span data-stu-id="a3575-111">Use remote Windows PowerShell to manage mail users: Add and manage mail users by running remote Windows PowerShell.</span></span> <span data-ttu-id="a3575-112">このメソッドは、複数のレコードの追加およびスクリプトの作成に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a3575-112">This method is useful for adding multiple records and creating scripts.</span></span>

> [!NOTE]
> <span data-ttu-id="a3575-113">Microsoft 365 管理センターでユーザーを追加することはできますが、これらのユーザーをメール受信者として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a3575-113">You can add users in the Microsoft 365 admin center, however these users can't be used as mail recipients.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="a3575-114">始める前に</span><span class="sxs-lookup"><span data-stu-id="a3575-114">Before you begin</span></span>

- <span data-ttu-id="a3575-115">Exchange 管理センターを開くには、「exchange [Online Protection の exchange 管理センター](../exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3575-115">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="a3575-p105">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「ユーザー、連絡先、および役割グループ」。</span><span class="sxs-lookup"><span data-stu-id="a3575-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>

- <span data-ttu-id="a3575-118">Exchange Online Protection の PowerShell コマンドレットを使用してメールユーザーを作成する場合、調整が発生する可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a3575-118">Be aware that when creating mail users by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="a3575-119">このトピックの PowerShell コマンドでは、コマンドの結果が表示されるまでに数分の遅延が発生するバッチ処理方式を使用しています。</span><span class="sxs-lookup"><span data-stu-id="a3575-119">The PowerShell commands in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="a3575-120">Windows PowerShell を使って Exchange Online Protection に接続する方法については、「[Exchange Online Protection の PowerShell への接続](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3575-120">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span></span>

- <span data-ttu-id="a3575-121">このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3575-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="a3575-122">問題がある場合は、</span><span class="sxs-lookup"><span data-stu-id="a3575-122">Having problems?</span></span> <span data-ttu-id="a3575-123">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラムでヘルプを要求します。</span><span class="sxs-lookup"><span data-stu-id="a3575-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="a3575-124">ディレクトリ同期を使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="a3575-124">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="a3575-125">このセクションでは、ディレクトリ同期を使用して電子メール ユーザーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3575-125">This section provides information about managing email users by using directory synchronization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a3575-126">ディレクトリ同期を使用して受信者を管理している場合でも、Microsoft 365 管理センターでユーザーを追加および管理することはできますが、オンプレミスの Active Directory と同期されることはありません。</span><span class="sxs-lookup"><span data-stu-id="a3575-126">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="a3575-127">これは、ディレクトリ同期では社内 Active Directory からクラウドへの受信者の同期だけが実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="a3575-127">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span> <br/><br/> <span data-ttu-id="a3575-128">ディレクトリ同期は、次の機能を使用する場合にお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3575-128">Directory synchronization is recommended for use with the following features:</span></span> <br/><br/><span data-ttu-id="a3575-129">• **Outlook の差出人セーフリストと受信拒否リスト**: サービスに同期すると、これらのリストはサービスのスパムフィルタリングよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a3575-129">• **Outlook safe sender and blocked sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="a3575-130">これにより、ユーザーは独自の差出人セーフ リストとブロックする差出人リストをユーザー単位またはドメイン単位で管理できます。</span><span class="sxs-lookup"><span data-stu-id="a3575-130">This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis.</span></span> <br/><br/><span data-ttu-id="a3575-131">•**ディレクトリベースのエッジブロック (dbeb)**: DBEB の詳細については、「 [Use Directory based Edge Blocking To Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3575-131">• **Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span> <br/><br/><span data-ttu-id="a3575-132">•**エンドユーザーのスパム検疫**: エンドユーザーのスパム検疫にアクセスするには、エンドユーザーが有効な Office 365 ユーザー ID とパスワードを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3575-132">• **End user spam quarantine**: In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="a3575-133">社内のメールボックスを保護している EOP のお客様は、有効な電子メール ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3575-133">EOP customers protecting on-premises mailboxes must be valid email users.</span></span> <br/><br/><span data-ttu-id="a3575-134">•**メールフロールール**: ディレクトリ同期を使用すると、既存の Active directory ユーザーとグループがクラウドに自動的にアップロードされ、特定のユーザーを対象とするメールフロールール (トランスポートルールとも呼ばれる) を作成できます。または、EAC または Exchange Online Protection の PowerShell を使用して手動で追加する必要のないグループ。</span><span class="sxs-lookup"><span data-stu-id="a3575-134">• **Mail flow rules**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules (also known as transport rules) that target specific users and/or groups without having to manually add them via the the EAC or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="a3575-135">[動的配布グループ](https://go.microsoft.com/fwlink/?LinkId=507569)はディレクトリ同期を使用して同期できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a3575-135">Note that [dynamic distribution groups](https://go.microsoft.com/fwlink/?LinkId=507569) can't be synchronized via directory synchronization.</span></span>
  
<span data-ttu-id="a3575-136">「[ディレクトリ同期を準備する](https://go.microsoft.com/fwlink/p/?LinkId=308908)」で説明されている手順に従って、必要な許可を取得し、ディレクトリ同期を準備します。</span><span class="sxs-lookup"><span data-stu-id="a3575-136">Get the necessary permissions and prepare for directory synchronization, as described in [Prepare for directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span></span>
  
### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="a3575-137">ユーザーディレクトリを Azure Active Directory Connect (AAD Connect) と同期するには</span><span class="sxs-lookup"><span data-stu-id="a3575-137">To synchronize user directories with Azure Active Directory Connect (AAD Connect)</span></span>

<span data-ttu-id="a3575-138">Azure Active Directory (AAD) にユーザーを同期するには、「 [active directory 同期をアクティブ](https://go.microsoft.com/fwlink/p/?LinkId=308909)化する」の説明に従って、**ディレクトリ同期をアクティブ化**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3575-138">To synchronize users to Azure Active Directory (AAD) you first have to **activate directory synchronization**, as described in [Activate directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span></span>

<span data-ttu-id="a3575-139">次に、AAD Connect を実行するためのオンプレミスのコンピューターのインストールと構成を行います (時間の前に確認する必要があるものがまだない場合)。</span><span class="sxs-lookup"><span data-stu-id="a3575-139">Next is the installation and configuration of an on-premises computer to run AAD Connect (if you don't already have one -- something worth checking ahead of time).</span></span> <span data-ttu-id="a3575-140">[Aad connect を設定](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)すると、このトピックでは、社内のアカウントを aad 接続を使用して Azure AD にセットアップし、同期する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3575-140">The [Setting up AAD Connect, the express way](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) topic tells you how to setup and synchronize your accounts from on-premises to Azure AD with AAD Connect.</span></span>

<span data-ttu-id="a3575-141">この作業を行う前に、[前提条件を満たし](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)ていることを確認し、[インストールの種類を選択](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)してください。</span><span class="sxs-lookup"><span data-stu-id="a3575-141">But before you do that work, make certain [you meet prerequisites](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites), and [choose your installation type](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span></span> <span data-ttu-id="a3575-142">以前のリンクは、高速インストールに関する短い記事を対象としています。</span><span class="sxs-lookup"><span data-stu-id="a3575-142">The earlier link is to a short article for express installs.</span></span> <span data-ttu-id="a3575-143">[カスタムインストール](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)の記事や、必要に応じ[て認証をパススルー](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3575-143">You can also find articles on [custom installations](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom), or [pass-through authentication](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) if they're needed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3575-p114">Azure Active Directory 同期ツール構成ウィザードを終了すると、Active Directory フォレストに **MSOL_AD_SYNC** アカウントが作成されます。このアカウントは、社内 Active Directory 情報の読み取りと同期に使われます。ディレクトリ同期が正しく行われるように、ローカル ディレクトリ同期サーバー上の TCP 443 が開いていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a3575-p114">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="a3575-147">同期を構成した後、EOP が正しく同期されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a3575-147">After configuring your sync, be sure to verify that EOP is synchronizing correctly.</span></span> <span data-ttu-id="a3575-148">EAC で、 **[受信者]** \> **[連絡先]** に移動し、ユーザーの一覧が社内環境から同期されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3575-148">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>

## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="a3575-149">EAC を使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="a3575-149">Use the EAC to manage mail users</span></span>

<span data-ttu-id="a3575-150">ここでは、EAC で直接電子メール ユーザーを追加し管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3575-150">This section provides information about adding and managing email users directly in the EAC.</span></span>
  
### <a name="use-the-eac-to-add-a-mail-user"></a><span data-ttu-id="a3575-151">EAC を使用してメールユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="a3575-151">Use the EAC to add a mail user</span></span>

1. <span data-ttu-id="a3575-152">電子メール ユーザーを作成するために、EAC で **[受信者]** \> **[連絡先]** に移動し、 **[新規 +]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3575-152">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>

2. <span data-ttu-id="a3575-153">**[メール ユーザーの新規作成]** ページで、以下を含むユーザー情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3575-153">On the **New mail user** page, enter the user's information, including the following:</span></span> 

   ****

   |<span data-ttu-id="a3575-154">**メール ユーザーのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="a3575-154">**Mail user property**</span></span>|<span data-ttu-id="a3575-155">**説明**</span><span class="sxs-lookup"><span data-stu-id="a3575-155">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="a3575-156">**[名]**、 **[イニシャル]**、 **[姓]**</span><span class="sxs-lookup"><span data-stu-id="a3575-156">**First name**, **Initials**, and **Last name**</span></span>|<span data-ttu-id="a3575-157">該当するボックスに、ユーザーの氏名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3575-157">Type the user's full name in the appropriate boxes.</span></span>|
   |<span data-ttu-id="a3575-158">**表示名**</span><span class="sxs-lookup"><span data-stu-id="a3575-158">**Display name**</span></span>|<span data-ttu-id="a3575-p116">名前を入力します (最大 64 文字)。既定では、このボックスには **[名]**、 **[イニシャル]**、 **[姓]** ボックスに入力した名前が表示されます。表示名は必須です。  </span><span class="sxs-lookup"><span data-stu-id="a3575-p116">Type a name, using up to 64 characters. By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any. The display name is required.</span></span>|
   |<span data-ttu-id="a3575-162">**エイリアス**</span><span class="sxs-lookup"><span data-stu-id="a3575-162">**Alias**</span></span>|<span data-ttu-id="a3575-p117">ユーザーのエイリアスを入力します (最大 64 文字)。エイリアスは必須です。</span><span class="sxs-lookup"><span data-stu-id="a3575-p117">Type a unique alias, using up to 64 characters, for the user. The alias is required.</span></span>|
   |<span data-ttu-id="a3575-165">**外部電子メール アドレス**</span><span class="sxs-lookup"><span data-stu-id="a3575-165">**External email address**</span></span>|<span data-ttu-id="a3575-166">ユーザーの外部電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3575-166">Type the external email address of the user.</span></span>|
   |<span data-ttu-id="a3575-167">**ユーザー ID**</span><span class="sxs-lookup"><span data-stu-id="a3575-167">**User id**</span></span>|<span data-ttu-id="a3575-p118">メール ユーザーがサービスにサインインするときに使用する名前を入力します。ユーザー サインイン名は、アットマーク記号 (@) の左側のユーザー名と右側のサフィックスで構成されます。一般的にサフィックスは、ユーザー アカウントが存在するドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="a3575-p118">Type the name that the mail user will use to sign in to the service. The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side. Typically, the suffix is the domain name in which the user account resides.</span></span>|
   |<span data-ttu-id="a3575-171">**新しいパスワード**</span><span class="sxs-lookup"><span data-stu-id="a3575-171">**New password**</span></span>|<span data-ttu-id="a3575-p119">メール ユーザーがサービスにサインインするときに使用するパスワードを入力します。作成するユーザー アカウントが属するドメインでのパスワードの長さ、複雑さ、および履歴に関する要件を満たすパスワードを指定してください。</span><span class="sxs-lookup"><span data-stu-id="a3575-p119">Type the password that the mail user will use to sign in to the service. Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>|
   |<span data-ttu-id="a3575-174">**パスワードの確認入力**</span><span class="sxs-lookup"><span data-stu-id="a3575-174">**Confirm password**</span></span>|<span data-ttu-id="a3575-175">確認のためのパスワードを再入力します。</span><span class="sxs-lookup"><span data-stu-id="a3575-175">Retype the password to confirm it.</span></span>|

3. <span data-ttu-id="a3575-p120">**[保存]** をクリックして新しい電子メール ユーザーを作成します。ユーザーの一覧に、新規ユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3575-p120">Click **Save** to create the new email user. The new user should appear in the list of users.</span></span>

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a><span data-ttu-id="a3575-178">EAC を使用してメールユーザーを編集または削除する</span><span class="sxs-lookup"><span data-stu-id="a3575-178">Use the EAC to edit or remove a mail user</span></span>

- <span data-ttu-id="a3575-179">EAC で、[**受信者** \>の**連絡先**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a3575-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="a3575-180">ユーザーの一覧で、表示または変更するユーザーをクリックし、[編集] \*\*\*\* ![編集アイコン](../media/ITPro-EAC-EditIcon.gif)を選択して、必要に応じてユーザーの設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="a3575-180">In the list of users, click the user that you want to view or change, and then select **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif) to update the user settings as needed.</span></span> <span data-ttu-id="a3575-181">ユーザーの名前、エイリアス、または連絡先情報を変更したり、組織内のユーザーの役割に関する詳細情報を記録したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a3575-181">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span></span> <span data-ttu-id="a3575-182">ユーザーを選択し、[削除] [ \*\*\*\* ![削除] アイコン](../media/ITPro-EAC-RemoveIcon.gif)を選択して削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3575-182">You can also select a user and then choose **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span></span> 

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a><span data-ttu-id="a3575-183">Exchange Online Protection PowerShell を使用してメールユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="a3575-183">Use Exchange Online Protection PowerShell to manage mail users</span></span>

<span data-ttu-id="a3575-184">このセクションでは、リモートの Windows PowerShell を使用してメール ユーザーを追加し、管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3575-184">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>
  
### <a name="use-eop-powershell-to-add-a-mail-user"></a><span data-ttu-id="a3575-185">EOP PowerShell を使用してメールユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="a3575-185">Use EOP PowerShell to add a mail user</span></span>
  
<span data-ttu-id="a3575-186">この例では、コマンドレット [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) を使用して、以下の情報を基に、EOP で Jeffrey Zeng に対してメールが有効なユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a3575-186">This example uses the [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span>
  
- <span data-ttu-id="a3575-187">名は Jeffrey で、姓は Zeng です。</span><span class="sxs-lookup"><span data-stu-id="a3575-187">The first name is Jeffrey and the last name is Zeng.</span></span>

- <span data-ttu-id="a3575-188">名前は Jeffrey で、表示名は Jeffrey Zeng です。</span><span class="sxs-lookup"><span data-stu-id="a3575-188">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>

- <span data-ttu-id="a3575-189">エイリアスは jeffreyz です。</span><span class="sxs-lookup"><span data-stu-id="a3575-189">The alias is jeffreyz.</span></span>

- <span data-ttu-id="a3575-190">外部の電子メール アドレスは jzeng@tailspintoys.com です。</span><span class="sxs-lookup"><span data-stu-id="a3575-190">The external email address is jzeng@tailspintoys.com.</span></span>

- <span data-ttu-id="a3575-191">Office 365 のサインイン名は jeffreyz@contoso.onmicrosoft.com です。</span><span class="sxs-lookup"><span data-stu-id="a3575-191">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>

- <span data-ttu-id="a3575-192">パスワードは Pa$$word1 です。</span><span class="sxs-lookup"><span data-stu-id="a3575-192">The password is Pa$$word1.</span></span>

```Powershell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

<span data-ttu-id="a3575-193">これが正常に動作することを確認するには、次のコマンドを実行して、新しいメールユーザー Jeffrey Zeng に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a3575-193">To verify that this worked, run the following command to display information about new mail user Jeffrey Zeng:</span></span>
  
```Powershell
Get-User -Identity "Jeffrey Zeng"
```

<span data-ttu-id="a3575-194">構文およびパラメーターの詳細については、「[取得-ユーザー](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3575-194">For detailed syntax and parameter information, see [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span></span>

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a><span data-ttu-id="a3575-195">EOP PowerShell を使用してメールユーザーのプロパティを編集する</span><span class="sxs-lookup"><span data-stu-id="a3575-195">Use EOP PowerShell to edit the properties of a mail user</span></span>
  
<span data-ttu-id="a3575-196">コマンドレット [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) および [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) を使用して、メール ユーザーのプロパティを表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="a3575-196">Use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) cmdlets to view or change properties for mail users.</span></span>
  
<span data-ttu-id="a3575-197">この例では、Pilar Pinilla の外部電子メール アドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="a3575-197">This example sets the external email address for Pilar Pinilla.</span></span>
  
```Powershell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="a3575-198">この例では、すべてのメール ユーザーの [会社] プロパティを Contoso に設定します。</span><span class="sxs-lookup"><span data-stu-id="a3575-198">This example sets the Company property for all mail users to Contoso.</span></span>
  
```Powershell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```
  
<span data-ttu-id="a3575-199">これが正常に動作することを[](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)確認するには、次のコマンドレットを使用して変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="a3575-199">To verify that this worked, use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify the changes.</span></span> <span data-ttu-id="a3575-200">(複数のメール連絡先に対して複数のプロパティが表示されることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="a3575-200">(Note that you can view multiple properties for multiple mail contacts.)</span></span>
  
```Powershell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

<span data-ttu-id="a3575-201">前にすべてのメール ユーザーの ［会社］ プロパティを Contoso に設定した例で、次のコマンドを実行して変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="a3575-201">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>
  
```Powershell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="a3575-202">このコマンドレットはバッチ処理方法を使用しており、コマンドレットの結果が表示されるまで数分の送信遅延が生じます。</span><span class="sxs-lookup"><span data-stu-id="a3575-202">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
  
### <a name="use-eop-powershell-to-remove-a-mail-user"></a><span data-ttu-id="a3575-203">EOP PowerShell を使用してメールユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="a3575-203">Use EOP PowerShell to remove a mail user</span></span>
  
<span data-ttu-id="a3575-204">この例では、コマンドレット [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) を使用してユーザー Jeffrey Zeng を削除します。</span><span class="sxs-lookup"><span data-stu-id="a3575-204">This example uses the [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) cmdlet to delete user Jeffrey Zeng:</span></span>
  
```Powershell
Remove-EOPMailUser -Identity Jeffrey
```

 <span data-ttu-id="a3575-205">**これが機能することを確認するには**</span><span class="sxs-lookup"><span data-stu-id="a3575-205">**To verify that this worked**</span></span>
  
<span data-ttu-id="a3575-206">これが正常に動作することを確認するには、 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)コマンドレットを実行して、メールユーザーが存在しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3575-206">To verify that this worked, run the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify that the mail user no longer exists.</span></span>
  
```Powershell
Get-Recipient Jeffrey | Format-List
```
