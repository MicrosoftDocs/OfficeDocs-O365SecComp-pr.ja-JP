---
title: EOP でメール ユーザーを管理する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: メール ユーザーの定義は、Exchange Online Protection (EOP) サービスを管理する上で重要な部分です。
ms.openlocfilehash: e985adf5659b50cf567ea798a092f809d77ca470
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027394"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="c8f1a-103">EOP でメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="c8f1a-103">Manage mail users in EOP</span></span>

<span data-ttu-id="c8f1a-p101">メール ユーザーの定義は、Exchange Online Protection (EOP) サービスを管理する上で重要な部分です。EOP でユーザーを管理するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p101">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service. There are several ways that you can manage users in EOP:</span></span>
  
- <span data-ttu-id="c8f1a-p102">メール ユーザーを管理するためにディレクトリ同期を使用して: に Azure Active ディレクトリ (AD)、コードのコピーをクラウドに格納する場所は、それらのアカウントを同期するには、オンプレミスの Active Directory 環境で既存のユーザー アカウントがある企業、です。Azure Active Directory への既存のユーザー アカウントを同期するときは、Exchange 管理センター (EAC) の [**受信者**] ウィンドウでこれらのユーザーを表示できます。ディレクトリ同期を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p102">Use directory synchronization to manage mail users: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud. When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC). Using directory synchronization is recommended.</span></span> 
    
- <span data-ttu-id="c8f1a-p103">EAC を使用してメール ユーザーを管理する: EAC で直接メール ユーザーを追加して管理します。これは、メール ユーザーを追加する最も簡単な方法で、一度に 1 ユーザーを追加する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p103">Use the EAC to manage mail users: Add and manage mail users directly in the EAC. This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>
    
- <span data-ttu-id="c8f1a-p104">リモートの Windows PowerShell を使用してメール ユーザーを管理するには: リモートの Windows PowerShell を実行してメール ユーザーを追加し、管理します。このメソッドは、複数のレコードの追加およびスクリプトの作成に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p104">Use remote Windows PowerShell to manage mail users: Add and manage mail users by running remote Windows PowerShell. This method is useful for adding multiple records and creating scripts.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c8f1a-113">Office 365 管理センターにユーザーを追加できますが、このユーザーはメールの受信者には使用できません。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-113">You can add users in the Office 365 admin center, however these users can't be used as mail recipients.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="c8f1a-114">開始する前に</span><span class="sxs-lookup"><span data-stu-id="c8f1a-114">Before you begin</span></span>

- <span data-ttu-id="c8f1a-p105">このトピックの手順には、特定のアクセス許可が必要です。アクセス許可情報については、各手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p105">Procedures in this topic require specific permissions. See each procedure for its permissions information.</span></span>
    
- <span data-ttu-id="c8f1a-117">このトピックの手順で使用可能なキーボード ショートカットについては、「**Exchange 管理センターのキーボード ショートカット**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="c8f1a-p106">問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p106">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="c8f1a-121">ディレクトリ同期を使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="c8f1a-121">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="c8f1a-122">このセクションでは、ディレクトリ同期を使用して電子メール ユーザーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-122">This section provides information about managing email users by using directory synchronization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c8f1a-p107">ディレクトリ同期を使って受信者を管理する場合でも、Office 365 管理センター でユーザーの追加と管理は可能ですが、これらのユーザーは社内 Active Directory を使った同期の対象になりません。これは、ディレクトリ同期では社内 Active Directory からクラウドへの受信者の同期だけが実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p107">If you use directory synchronization to manage your recipients, you can still add and manage users in the Office 365 admin center, but they will not be synchronized with your on-premises Active Directory. This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span> 
  
> [!TIP]
>  <span data-ttu-id="c8f1a-p108">次の機能によるディレクトリ同期の使用をお勧めします。 > **Outlook の差出人セーフ リストとブロックする差出人リスト** - サービスに同期すると、これらのリストはサービスのスパム フィルターより優先されます。これにより、ユーザーは独自の差出人セーフ リストとブロックする差出人リストをユーザー単位またはドメイン単位で管理できます。 > **ディレクトリ ベースのエッジ ブロック (DBEB)** - DBEB についての詳細は、「 [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)」を参照してください。 > **エンド ユーザーのスパム検疫**  エンド ユーザーのスパム検疫にアクセスするためには、エンド ユーザーは有効な Office 365 のユーザー ID とパスワードを保有している必要があります。社内のメールボックスを保護している EOP のお客様は、有効な電子メール ユーザーである必要があります。 > **トランスポート ルール** - ディレクトリ同期を使用すると、既存の Active Directory ユーザーおよびグループが自動的にクラウドにアップロードされます。特定のユーザーやグループを対象とするトランスポート ルールを作成するために、EAC または リモート Windows PowerShell を使ってユーザーやグループを手動で追加する必要はありません。ただし、 [動的配布グループ](https://go.microsoft.com/fwlink/?LinkId=507569)は、ディレクトリ同期を介して同期できません。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p108">Using directory synchronization is recommended for use with the following features: > **Outlook safe sender and blocked sender lists** - When synchronized to the service, these lists will take precedence over spam filtering in the service. This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis. > **Directory Based Edge Blocking (DBEB)** - For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx). > **End user spam quarantine** - In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password. EOP customers protecting on-premises mailboxes must be valid email users. > **Transport rules** - When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create Transport rules that target specific users and/or groups without having to manually add them via the EAC or remote Windows PowerShell. Note that [dynamic distribution groups](https://go.microsoft.com/fwlink/?LinkId=507569) can't be synchronized via directory synchronization.</span></span> 
  
 <span data-ttu-id="c8f1a-132">**開始する前に**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-132">**Before you begin**</span></span>
  
<span data-ttu-id="c8f1a-133">「[ディレクトリ同期を準備する](https://go.microsoft.com/fwlink/p/?LinkId=308908)」で説明されている手順に従って、必要な許可を取得し、ディレクトリ同期を準備します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-133">Get the necessary permissions and prepare for directory synchronization, as described in [Prepare for directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span></span>
  
### <a name="to-synchronize-user-directories"></a><span data-ttu-id="c8f1a-134">ユーザー ディレクトリを同期するには</span><span class="sxs-lookup"><span data-stu-id="c8f1a-134">To synchronize user directories</span></span>

1. <span data-ttu-id="c8f1a-135">「[ディレクトリ同期をアクティブにする](https://go.microsoft.com/fwlink/p/?LinkId=308909)」で説明されている手順に従って、ディレクトリ同期をアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-135">Activate directory synchronization, as described in [Activate directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span></span>
    
2. <span data-ttu-id="c8f1a-136">「[ディレクトリ同期用コンピューターをセットアップする](http://go.microsoft.com/fwlink/p/?LinkId=308911)」で説明されている手順に従って、ディレクトリ同期コンピュータをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-136">Set up your directory synchronization computer, as described in [Set up your directory sync computer](http://go.microsoft.com/fwlink/p/?LinkId=308911).</span></span>
    
3. <span data-ttu-id="c8f1a-137">「[構成ウィザードを使ってディレクトリを同期する](http://go.microsoft.com/fwlink/?LinkId=308912)」で説明されている手順に従って、ディレクトリを同期します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-137">Synchronize your directories, as described in [Use the Configuration Wizard to sync your directories](http://go.microsoft.com/fwlink/?LinkId=308912).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c8f1a-p109">Azure Active Directory 同期ツール構成ウィザードを終了すると、Active Directory フォレストに **MSOL_AD_SYNC** アカウントが作成されます。このアカウントは、社内 Active Directory 情報の読み取りと同期に使われます。ディレクトリ同期が正しく行われるように、ローカル ディレクトリ同期サーバー上の TCP 443 が開いていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p109">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span> 
  
4. <span data-ttu-id="c8f1a-141">「[同期ユーザーのアクティブ化](http://go.microsoft.com/fwlink/p/?LinkId=308913)」で説明されている手順に従って、同期ユーザーをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-141">Activate synced users, as described in [Activate synced users](http://go.microsoft.com/fwlink/p/?LinkId=308913).</span></span>
    
5. <span data-ttu-id="c8f1a-142">「[ディレクトリ同期を管理する](http://go.microsoft.com/fwlink/p/?LinkId=308915)」で説明されている手順に従って、ディレクトリ同期を管理します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-142">Manage directory synchronization, as described in [Manage directory synchronization](http://go.microsoft.com/fwlink/p/?LinkId=308915).</span></span>
    
6. <span data-ttu-id="c8f1a-p110">EOP が正しく同期されていることを確認します。EAC で、 **[受信者]** \> **[連絡先]** に移動し、ユーザーの一覧が社内環境から同期されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p110">Verify that EOP is synchronizing correctly. In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span> 
    
## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="c8f1a-145">EAC を使用してメール ユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="c8f1a-145">Use the EAC to manage mail users</span></span>

<span data-ttu-id="c8f1a-146">ここでは、EAC で直接電子メール ユーザーを追加し管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-146">This section provides information about adding and managing email users directly in the EAC.</span></span>
  
 <span data-ttu-id="c8f1a-147">**開始する前に**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-147">**Before you begin**</span></span>
  
<span data-ttu-id="c8f1a-p111">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「ユーザー、連絡先、および役割グループ」。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p111">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>
  
### <a name="to-add-a-mail-user-in-the-eac"></a><span data-ttu-id="c8f1a-150">EAC でメール ユーザーを追加するには</span><span class="sxs-lookup"><span data-stu-id="c8f1a-150">To add a mail user in the EAC</span></span>

1. <span data-ttu-id="c8f1a-151">電子メール ユーザーを作成するために、EAC で **[受信者]** \> **[連絡先]** に移動し、 **[新規 +]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-151">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>
    
2. <span data-ttu-id="c8f1a-152">**[メール ユーザーの新規作成]** ページで、以下を含むユーザー情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-152">On the **New mail user** page, enter the user's information, including the following:</span></span> 
    
   ****

|<span data-ttu-id="c8f1a-153">**メール ユーザーのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-153">**Mail user property**</span></span>|<span data-ttu-id="c8f1a-154">**説明**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c8f1a-155">**[名]**、 **[イニシャル]**、 **[姓]**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-155">**First name**, **Initials**, and **Last name**</span></span> <br/> |<span data-ttu-id="c8f1a-156">該当するボックスに、ユーザーの氏名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-156">Type the user's full name in the appropriate boxes.</span></span>  <br/> |
|<span data-ttu-id="c8f1a-157">**表示名**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-157">**Display name**</span></span> <br/> |<span data-ttu-id="c8f1a-p112">名前を入力します (最大 64 文字)。既定では、このボックスには **[名]**、 **[イニシャル]**、 **[姓]** ボックスに入力した名前が表示されます。表示名は必須です。  </span><span class="sxs-lookup"><span data-stu-id="c8f1a-p112">Type a name, using up to 64 characters. By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any. The display name is required.  </span></span><br/> |
|<span data-ttu-id="c8f1a-161">**エイリアス**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-161">**Alias**</span></span> <br/> |<span data-ttu-id="c8f1a-p113">ユーザーのエイリアスを入力します (最大 64 文字)。エイリアスは必須です。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p113">Type a unique alias, using up to 64 characters, for the user. The alias is required.</span></span>  <br/> |
|<span data-ttu-id="c8f1a-164">**外部電子メール アドレス**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-164">**External email address**</span></span> <br/> |<span data-ttu-id="c8f1a-165">ユーザーの外部電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-165">Type the external email address of the user.</span></span>  <br/> |
|<span data-ttu-id="c8f1a-166">**ユーザー ID**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-166">**User id**</span></span> <br/> |<span data-ttu-id="c8f1a-p114">メール ユーザーがサービスにサインインするときに使用する名前を入力します。ユーザー サインイン名は、アットマーク記号 (@) の左側のユーザー名と右側のサフィックスで構成されます。一般的にサフィックスは、ユーザー アカウントが存在するドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p114">Type the name that the mail user will use to sign in to the service. The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side. Typically, the suffix is the domain name in which the user account resides.</span></span>  <br/> |
|<span data-ttu-id="c8f1a-170">**新しいパスワード**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-170">**New password**</span></span> <br/> |<span data-ttu-id="c8f1a-p115">メール ユーザーがサービスにサインインするときに使用するパスワードを入力します。作成するユーザー アカウントが属するドメインでのパスワードの長さ、複雑さ、および履歴に関する要件を満たすパスワードを指定してください。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p115">Type the password that the mail user will use to sign in to the service. Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>  <br/> |
|<span data-ttu-id="c8f1a-173">**パスワードの確認入力**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-173">**Confirm password**</span></span> <br/> |<span data-ttu-id="c8f1a-174">確認のためのパスワードを再入力します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-174">Retype the password to confirm it.</span></span>  <br/> |
   
3. <span data-ttu-id="c8f1a-p116">**[保存]** をクリックして新しい電子メール ユーザーを作成します。ユーザーの一覧に、新規ユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p116">Click **Save** to create the new email user. The new user should appear in the list of users.</span></span> 
    
### <a name="to-edit-or-remove-a-mail-user-in-the-eac"></a><span data-ttu-id="c8f1a-177">EAC でメール ユーザーを編集または削除するには</span><span class="sxs-lookup"><span data-stu-id="c8f1a-177">To edit or remove a mail user in the EAC</span></span>

- <span data-ttu-id="c8f1a-p117">EAC で、 **[受信者]** \> **[連絡先]** に移動します。ユーザーの一覧で、表示または変更対象のユーザーをクリックしてから **[編集]**![編集アイコン](../media/ITPro-EAC-EditIcon.png) を選択し、必要に応じてユーザー設定を更新します。ユーザーの名前、エイリアス、連絡先情報を変更できます。また、組織内でのユーザーの役割に関する詳細情報を記録できます。ユーザーを削除するには、ユーザーを選択してから **[削除]**![[削除] アイコン](../media/ITPro-EAC-RemoveIcon.png) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p117">In the EAC, go to **Recipients** \> **Contacts**. In the list of users, click the user that you want to view or change, and then select **Edit**![Edit icon](../media/ITPro-EAC-EditIcon.png) to update the user settings as needed. You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization. You can also select a user and then choose **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.png) to delete it.</span></span> 
    
## <a name="use-remote-windows-powershell-to-manage-mail-users"></a><span data-ttu-id="c8f1a-182">リモートの Windows PowerShell を使用してメール ユーザーを管理するには</span><span class="sxs-lookup"><span data-stu-id="c8f1a-182">Use remote Windows PowerShell to manage mail users</span></span>

<span data-ttu-id="c8f1a-183">このセクションでは、リモートの Windows PowerShell を使用してメール ユーザーを追加し、管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-183">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>
  
 <span data-ttu-id="c8f1a-184">**開始する前に**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-184">**Before you begin**</span></span>
  
- <span data-ttu-id="c8f1a-p118">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「ユーザー、連絡先、および役割グループ」。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p118">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>
    
- <span data-ttu-id="c8f1a-187">リモートの PowerShell コマンドレットを使用してメール ユーザーを作成する際、調整が発生することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-187">Be aware that when creating mail users by using remote PowerShell cmdlets, you may encounter throttling.</span></span>
    
- <span data-ttu-id="c8f1a-188">このコマンドレットはバッチ処理方法を使用しており、コマンドレットの結果が表示されるまで数分の送信遅延が生じます。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-188">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
    
- <span data-ttu-id="c8f1a-189">Windows PowerShell を使用して Exchange Online Protection に接続する方法については、「[リモート PowerShell を使用して Exchange Online Protection に接続する](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-189">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection Using Remote PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span></span>
    
 <span data-ttu-id="c8f1a-190">**リモートの PowerShell を使用してメール ユーザーを追加するには**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-190">**To add a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="c8f1a-191">この例では、コマンドレット [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) を使用して、以下の情報を基に、EOP で Jeffrey Zeng に対してメールが有効なユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-191">This example uses the [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span> 
  
- <span data-ttu-id="c8f1a-192">名は Jeffrey で、姓は Zeng です。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-192">The first name is Jeffrey and the last name is Zeng.</span></span>
    
- <span data-ttu-id="c8f1a-193">名前は Jeffrey で、表示名は Jeffrey Zeng です。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-193">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>
    
- <span data-ttu-id="c8f1a-194">エイリアスは jeffreyz です。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-194">The alias is jeffreyz.</span></span>
    
- <span data-ttu-id="c8f1a-195">外部の電子メール アドレスは jzeng@tailspintoys.com です。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-195">The external email address is jzeng@tailspintoys.com.</span></span>
    
- <span data-ttu-id="c8f1a-196">Office 365 のサインイン名は jeffreyz@contoso.onmicrosoft.com です。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-196">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>
    
- <span data-ttu-id="c8f1a-197">パスワードは Pa$$word1 です。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-197">The password is Pa$$word1.</span></span>
    
```
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

 <span data-ttu-id="c8f1a-198">**これが機能することを確認するには**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-198">**To verify that this worked**</span></span>
  
<span data-ttu-id="c8f1a-199">新しいメール ユーザー Jeffrey Zeng に関する情報を表示するには、次のようにコマンドレット [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) を実行します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-199">Run the [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) cmdlet as follows to display information about new mail user Jeffrey Zeng:</span></span> 
  
```
Get-User "Jeffrey Zeng"

```

 <span data-ttu-id="c8f1a-200">**リモートの PowerShell を使用してメール ユーザーのプロパティを編集するには**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-200">**To edit the properties of a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="c8f1a-201">コマンドレット [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) および [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) を使用して、メール ユーザーのプロパティを表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-201">Use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) and [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) cmdlets to view or change properties for mail users.</span></span> 
  
<span data-ttu-id="c8f1a-202">この例では、Pilar Pinilla の外部電子メール アドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-202">This example sets the external email address for Pilar Pinilla.</span></span>
  
```
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="c8f1a-203">この例では、すべてのメール ユーザーの [会社] プロパティを Contoso に設定します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-203">This example sets the Company property for all mail users to Contoso.</span></span>
  
```
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}

```

 <span data-ttu-id="c8f1a-204">**これが機能することを確認するには**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-204">**To verify that this worked**</span></span>
  
<span data-ttu-id="c8f1a-p119">前にメール ユーザー Pilar Pinella のプロパティを変更した例で、コマンドレット [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) を使用して変更を確認します。(複数のメール連絡先に対して複数のプロパティが表示されることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p119">In the previous example where we changed the properties for mail user Pilar Pinella, use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to verify the changes. (Note that you can view multiple properties for multiple mail contacts.)</span></span> 
  
```
Get-Recipient -Identity "Pilar Pinilla" | Format-List 

```

<span data-ttu-id="c8f1a-207">前にすべてのメール ユーザーの ［会社］ プロパティを Contoso に設定した例で、次のコマンドを実行して変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-207">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>
  
```
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="c8f1a-208">このコマンドレットはバッチ処理方法を使用しており、コマンドレットの結果が表示されるまで数分の送信遅延が生じます。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-208">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span> 
  
 <span data-ttu-id="c8f1a-209">**リモートの PowerShell を使用してメール ユーザーを削除するには**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-209">**To remove a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="c8f1a-210">この例では、コマンドレット [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) を使用してユーザー Jeffrey Zeng を削除します。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-210">This example uses the [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) cmdlet to delete user Jeffrey Zeng:</span></span> 
  
```
Remove-EOPMailUser -Identity Jeffrey
```

 <span data-ttu-id="c8f1a-211">**これが機能することを確認するには**</span><span class="sxs-lookup"><span data-stu-id="c8f1a-211">**To verify that this worked**</span></span>
  
<span data-ttu-id="c8f1a-p120">次のようにコマンドレット [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) を実行します。ユーザーが存在しないため、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8f1a-p120">Run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows. You should get an error message since the user no longer exists.</span></span> 
  
```
Get-Recipient Jeffrey | fl
```


