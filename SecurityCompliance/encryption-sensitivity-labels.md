---
title: 機密ラベルの暗号化を使用してコンテンツへのアクセスを制限する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 10/22/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 機密ラベルを作成するときに、そのラベルが適用されるコンテンツへのアクセスを制限できます。機密ラベルでは、コンテンツの保護のために暗号化を使用できます。
ms.openlocfilehash: 04de1b1efaa26694bcad2274d2ff9e9b3b2c637e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220317"
---
# <a name="restrict-access-to-content-by-using-encryption-in-sensitivity-labels"></a><span data-ttu-id="69aa4-104">機密ラベルの暗号化を使用してコンテンツへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="69aa4-104">Restrict access to content by using encryption in sensitivity labels</span></span>

<span data-ttu-id="69aa4-p102">機密ラベルを作成するときに、そのラベルが適用されるコンテンツへのアクセスを制限できます。たとえば、機密ラベルに対応する暗号化の設定によって、次のようにコンテンツを保護できます。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p102">When you create a sensitivity label, you can restrict access to content that the label will be applied to. For example, with the encryption settings for a sensitivity label, you can protect content so that:</span></span>

- <span data-ttu-id="69aa4-107">組織内のユーザーのみが機密ドキュメントや電子メールを開けるようにする。</span><span class="sxs-lookup"><span data-stu-id="69aa4-107">Only users within your organization can open a confidential document or email.</span></span>
- <span data-ttu-id="69aa4-108">宣伝広告用のドキュメントや電子メールは、マーケティング部門のユーザーのみが編集および印刷できるようにして、その他の組織内のユーザーは閲覧のみできるようにする。</span><span class="sxs-lookup"><span data-stu-id="69aa4-108">Only users in the marketing department can edit and print the promotion announcement document or email, while all other users in your organization can only read it.</span></span>
- <span data-ttu-id="69aa4-109">内部の再編成に関するニュースが含まれている電子メールは、ユーザーが転送や情報のコピーをできないようにする。</span><span class="sxs-lookup"><span data-stu-id="69aa4-109">Users cannot forward an email or copy information from it that contains news about an internal reorganization.</span></span>
- <span data-ttu-id="69aa4-110">ビジネス パートナーに送信する現行の価格リストは、指定した日付以降は開けないようにする。</span><span class="sxs-lookup"><span data-stu-id="69aa4-110">The current price list that is sent to business partners cannot be opened after a specified date.</span></span>

<span data-ttu-id="69aa4-111">ドキュメントや電子メールを暗号化するときには、次のようにしてコンテンツへのアクセスが制限されます。</span><span class="sxs-lookup"><span data-stu-id="69aa4-111">When a document or email is encrypted, access to the content is restricted, so that it:</span></span>

- <span data-ttu-id="69aa4-112">暗号化の解除は、ラベルの暗号化設定で許可されているユーザーのみが可能です。</span><span class="sxs-lookup"><span data-stu-id="69aa4-112">Can be decrypted only by users authorized by the label’s encryption settings.</span></span>
- <span data-ttu-id="69aa4-113">暗号化は、ファイルの場所 (組織内外) を問わず、ファイル名が変更されていても維持されます。</span><span class="sxs-lookup"><span data-stu-id="69aa4-113">Remains encrypted no matter where it resides, inside or outside your organization, even if the file’s renamed.</span></span>
- <span data-ttu-id="69aa4-114">保存中 (OneDrive アカウントなど) と転送中 (送信中の電子メールなど) の両方で暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="69aa4-114">Is encrypted both at rest (for example, in a OneDrive account) and in transit (for example, a sent email).</span></span>

<span data-ttu-id="69aa4-115">暗号化設定は、Office 365 セキュリティ/コンプライアンス センターの **[ラベル]** ページにある **[秘密度]** タブの **[ラベルの作成]** で使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="69aa4-115">The encryption settings are available in the Office 365 Security & Compliance Center > **Labels** page > **Sensitivity** tab > **Create a label**.</span></span>

## <a name="how-encryption-works"></a><span data-ttu-id="69aa4-116">暗号化のしくみ</span><span class="sxs-lookup"><span data-stu-id="69aa4-116">How encryption works</span></span>

<span data-ttu-id="69aa4-p103">暗号化には、Azure Rights Management (Azure RMS) を使用します。Azure RMS は、暗号化ポリシー、ID ポリシー、および認証ポリシーを使用します。詳細については、「[Azure Rights Management とは](https://docs.microsoft.com/ja-JP/azure/information-protection/what-is-azure-rms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p103">Encryption uses Azure Rights Management (Azure RMS). Azure RMS uses encryption, identity, and authorization policies. To learn more, see [What is Azure Rights Management?](https://docs.microsoft.com/ja-JP/azure/information-protection/what-is-azure-rms)</span></span>

## <a name="how-to-turn-on-encryption-for-a-sensitivity-label"></a><span data-ttu-id="69aa4-120">機密ラベルに対する暗号化を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="69aa4-120">How to turn on encryption for a sensitivity label</span></span>

<span data-ttu-id="69aa4-p104">最初に **[暗号化]** を **[オン]** に切り替えて、その下側にあるオプションを使用して、このラベルが適用される電子メールやドキュメントにアクセスできるユーザーを制御します。次のことが可能です。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p104">To begin, simply toggle **Encryption** to **On**, and then use the options below to control who can access email or documents to which this label is applied. You can:</span></span>

1. <span data-ttu-id="69aa4-p105">**電子メールとドキュメントの両方、または電子メールにのみ暗号化を適用します。** 電子メールのみを選択すると、このラベルが付いたメッセージは Outlook で暗号化されますが、このラベルが付いたドキュメントは他のアプリ (Word や PowerPoint など) では暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p105">**Apply encryption to both email and documents, or just email.** If you choose just email, messages with this label will be encrypted in Outlook, but documents with this label won't be encrypted in other apps, such as Word or PowerPoint.</span></span> 
2. <span data-ttu-id="69aa4-p106">**ラベル付けされたコンテンツへのアクセスに有効期限を設定します。** 指定の日付または指定の日数 (ラベル適用後の経過日数) で有効期限が切れます。この期限が切れると、ユーザーはラベル付きのアイテムを開けなくなります。日付を指定すると、その日付の午前 0 時まで有効になります (現在のタイム ゾーン)。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p106">**Allow access to labeled content to expire**, either on a specific date or after a specific number of days after the label is applied. After this time, users won’t be able to open the labeled item. If you specify a date, it is effective midnight on that date in your current time zone.</span></span> 
3. <span data-ttu-id="69aa4-p107">**オフライン アクセス**を禁止、常に許可、または指定の日数 (ラベル適用後の経過日数) で許可します。オフライン アクセスを禁止または日数で制限すると、そのしきい値に達したときに、ユーザーは再認証される必要があり、ユーザーのアクセスがログに記録されます。詳細については、Rights Management 使用ライセンスに関する次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p107">**Allow offline access** never, always, or for a specific number of days after the label is applied. If you restrict offline access to never or a number of days, when that threshold is reached, users must be reauthenticated and their access is logged. For more information, see the next section on the Rights Management use license.</span></span>

![機密ラベルに対する暗号化の設定](media/Sensitivity_Encryption_settings_for_sensitivity_label.png)

### <a name="rights-management-use-license-for-offline-access"></a><span data-ttu-id="69aa4-132">オフライン アクセスのための Rights Management 使用ライセンス</span><span class="sxs-lookup"><span data-stu-id="69aa4-132">Rights Management use license for offline access</span></span>

<span data-ttu-id="69aa4-p108">ユーザーが機密ラベルで保護されているドキュメントや電子メールをオフラインで開くと、そのコンテンツの Azure Rights Management 使用ライセンスがユーザーに付与されます。この使用ライセンスは、ドキュメントまたは電子メールに対するユーザーの使用権とコンテンツの暗号化に使用された暗号化キーが含まれている証明書です。この使用ライセンスには、有効期限日 (設定されている場合) と使用ライセンスの有効期間も含まれています。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p108">When a user opens a document or email offline that’s been protected by a sensitivity label, an Azure Rights Management use license for that content is granted to the user. This use license is a certificate that contains the user's usage rights for the document or email, and the encryption key that was used to encrypt the content. The use license also contains an expiration date if this has been set, and how long the use license is valid.</span></span>

<span data-ttu-id="69aa4-p109">有効期限日が設定されていない場合、テナントに対する使用ライセンスの既定の有効期間は 30 日間です。使用ライセンスの有効期間中は、そのコンテンツに対してユーザーが再認証または再承認されることはありません。これにより、ユーザーは保護されたドキュメントまたは電子メールをインターネット接続なしで継続して開くことができます。使用ライセンスの有効期間が切れると、保護されたドキュメントまたは電子メールの次回のユーザー アクセス時に、ユーザーの再認証または再承認が必要になります。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p109">If no expiration date has been set, the default use license validity period for a tenant is 30 days. For the duration of the use license, the user is not reauthenticated or reauthorized for the content. This lets the user continue to open the protected document or email without an Internet connection. When the use license validity period expires, the next time the user accesses the protected document or email, the user must be reauthenticated and reauthorized.</span></span>

<span data-ttu-id="69aa4-p110">再認証だけでなく、ポリシーとユーザー グループ メンバーシップの再評価も実行されます。そのため、ユーザーが最後にコンテンツにアクセスした後でポリシーやグループ メンバーシップに変更が加えられていると、同じドキュメントや電子メールに対して異なるアクセス結果がユーザーに示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p110">In addition to reauthentication, the policy and user group membership is reevaluated. This means that users could experience different access results for the same document or email if there are changes in the policy or group membership from when they last accessed the content.</span></span>

<span data-ttu-id="69aa4-142">既定の 30 日の設定を変更する方法については、「[Rights Management 使用ライセンス](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-usage-rights#rights-management-use-license)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69aa4-142">To learn how to change the default 30-day setting, see [Rights Management use license](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-usage-rights#rights-management-use-license).</span></span>

## <a name="assign-permissions-to-specific-users-or-groups"></a><span data-ttu-id="69aa4-143">特定のユーザーまたはグループにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="69aa4-143">Assign permissions to specific users or groups</span></span>

<span data-ttu-id="69aa4-144">特定のユーザーにアクセス許可を付与することで、ラベル付きコンテンツの操作を特定のユーザーにのみ許可することができます。</span><span class="sxs-lookup"><span data-stu-id="69aa4-144">You can grant permissions to specific people so that only they can interact with the labeled content.</span></span>

<span data-ttu-id="69aa4-145">そのようにするには、次の簡単な 2 段階の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="69aa4-145">Doing so is a straightforward two-step process:</span></span>

1. <span data-ttu-id="69aa4-146">まず、ラベル付きコンテンツへのアクセス許可を割り当てるユーザーまたはグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="69aa4-146">First you add users or groups that will be assigned permissions to the labeled content.</span></span>
2. <span data-ttu-id="69aa4-147">次に、該当するユーザーに付与するラベル付きコンテンツへのアクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="69aa4-147">Then you choose which permissions those users have for the labeled content.</span></span>

![ユーザーにアクセス許可を割り当てる際のオプション](media/Sensitivity_Assign_permissions_settings.png)

### <a name="add-users-or-groups"></a><span data-ttu-id="69aa4-149">ユーザーまたはグループの追加</span><span class="sxs-lookup"><span data-stu-id="69aa4-149">Add users or groups</span></span>

<span data-ttu-id="69aa4-150">アクセス許可を割り当てるときには、次の選択が可能です。</span><span class="sxs-lookup"><span data-stu-id="69aa4-150">When you assign permissions, you can choose:</span></span>

- <span data-ttu-id="69aa4-p111">組織内のすべてのユーザー (すべてのテナント メンバー)。この設定ではゲスト アカウントが除外されます。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p111">Everyone in your organization (all tenant members). This setting excludes guest accounts.</span></span>
- <span data-ttu-id="69aa4-153">特定のユーザーまたは電子メールが有効なセキュリティ グループ、配布グループ、Office 365 グループ、または動的配布グループ。</span><span class="sxs-lookup"><span data-stu-id="69aa4-153">Any specific user or email-enabled security group, distribution group, Office 365 group, or dynamic distribution group.</span></span> 
- <span data-ttu-id="69aa4-154">組織外の電子メール アドレスまたはドメイン (gmail.com、hotmail.com、outlook.com など)。</span><span class="sxs-lookup"><span data-stu-id="69aa4-154">Any email address or domain outside your organization, such as gmail.com, hotmail.com, or outlook.com.</span></span>

<span data-ttu-id="69aa4-155">すべてのテナント メンバーを選択する場合やディレクトリを参照する場合は、ユーザーまたはグループに電子メール アドレスが必要になります。</span><span class="sxs-lookup"><span data-stu-id="69aa4-155">When you choose all tenant members or browse the directory, the users or groups must have an email address.</span></span>

<span data-ttu-id="69aa4-p112">ベスト プラクティスとして、ユーザーではなくグループを使用します。この方針により、シンプルな構成を維持できます。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p112">As a best practice, use groups rather than users. This strategy keeps your configuration simpler.</span></span>

### <a name="choose-permissions"></a><span data-ttu-id="69aa4-158">アクセス許可の選択</span><span class="sxs-lookup"><span data-stu-id="69aa4-158">Choose permissions</span></span>

<span data-ttu-id="69aa4-159">該当するユーザーまたはグループに付与するアクセス許可を選択するときには、次のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="69aa4-159">When you choose which permissions to allow for those users or groups, you can select either:</span></span>

- <span data-ttu-id="69aa4-160">既定の権限のグループ (「共同制作者」や「レビュー担当者」など) で[事前定義されたアクセス許可レベル](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels)。</span><span class="sxs-lookup"><span data-stu-id="69aa4-160">A [predefined permissions level](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) with a preset group of rights, such as Co-Author or Reviewer.</span></span>
- <span data-ttu-id="69aa4-161">カスタムの権限のグループ。この場合は任意のアクセス許可を選択できます。</span><span class="sxs-lookup"><span data-stu-id="69aa4-161">A Custom group of rights, where you choose whichever permissions you want.</span></span>

<span data-ttu-id="69aa4-162">それぞれの具体的なアクセス許可に関する詳細については、「[使用権限と説明](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69aa4-162">For more information on each specific permission, see [Usage rights and descriptions](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).</span></span>  

![既定またはカスタムのアクセス許可を選択する際のオプション](media/Sensitivity_Choose_permissions_settings.png)

<span data-ttu-id="69aa4-p113">同じラベルで異なるユーザーに異なるアクセス許可を付与できます。たとえば、次に示すように、単一のラベルで一部のユーザーを「レビュー担当者」として割り当てて、別のユーザーを「共同作成者」として割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p113">Note that the same label can grant different permissions to different users. For example, a single label can assign some users as Reviewer and a different user as Co-author, as shown below.</span></span>

<span data-ttu-id="69aa4-p114">このようにするには、ユーザーまたはグループを追加し、それらにアクセス許可を割り当てて、その設定を保存します。その後で、この手順 (ユーザーの追加とアクセス許可の割り当て) を繰り返して、そのたびに保存します。この手順は、異なるユーザーに異なるアクセス許可を定義することが必要になるたびに実行できます。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p114">To do this, add users or groups, assign them permissions, and save those settings. Then repeat these steps, adding users and assigning them permissions, saving the settings each time. You can do this as often as necessary, to define different permissions for different users.</span></span>

![異なるアクセス許可を持つ異なるユーザー](media/Sensitivity_Multiple_users_permissions.png)

### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a><span data-ttu-id="69aa4-170">常にフル コントロールを持つ Rights Management 発行者 (機密ラベルを適用するユーザー)</span><span class="sxs-lookup"><span data-stu-id="69aa4-170">Rights Management issuer (user applying the sensitivity label) always has Full Control</span></span>

<span data-ttu-id="69aa4-p115">機密ラベルに対する暗号化には Azure RMS が使用されます。ユーザーがドキュメントや電子メールを保護するために Azure RMS を使用して機密ラベルを適用すると、そのユーザーはそのコンテンツに対する Rights Management 発行者になります。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p115">Encryption for a sensitivity label uses Azure RMS. When a user applies a sensitivity label to protect a document or email by using Azure RMS, that user becomes the Rights Management issuers for that content.</span></span>

<span data-ttu-id="69aa4-173">Rights Management 発行者には、常に、ドキュメントや電子メールに対するフル コントロールのアクセス許可が付与されます。さらに、次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="69aa4-173">The Rights Management issuer is always granted Full Control permissions for the document or email, and in addition:</span></span>

- <span data-ttu-id="69aa4-174">保護設定に有効期限日が含まれている場合、Rights Management 発行者は、その期日が過ぎていてもドキュメントや電子メールを開いて編集できます。</span><span class="sxs-lookup"><span data-stu-id="69aa4-174">If the protection settings include an expiration date, the Rights Management issuer can still open and edit the document or email after that date.</span></span>
- <span data-ttu-id="69aa4-175">Rights Management 発行者は、常に、オフラインでドキュメントや電子メールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="69aa4-175">The Rights Management issuer can always access the document or email offline.</span></span>
- <span data-ttu-id="69aa4-176">Rights Management 発行者は、失効後のドキュメントも開くことができます。</span><span class="sxs-lookup"><span data-stu-id="69aa4-176">The Rights Management issuer can still open a document after it is revoked.</span></span>

<span data-ttu-id="69aa4-177">詳細については、「[Rights Management 発行者と Rights Management 所有者](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69aa4-177">For more information, see [Rights Management issuer and Rights Management owner](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).</span></span>

## <a name="storing-encrypted-content-in-onedrive-and-sharepoint"></a><span data-ttu-id="69aa4-178">OneDrive および SharePoint に暗号化されたコンテンツを保存する</span><span class="sxs-lookup"><span data-stu-id="69aa4-178">Storing encrypted content in OneDrive and SharePoint</span></span>

<span data-ttu-id="69aa4-p116">OneDrive および SharePoint に保存されているファイルに暗号化を適用すると、サービスは該当するファイルのコンテンツを処理できなくなります。そのため、共同編集、電子情報開示、検索、Delve などの共同作業機能が動作しなくなります。さらに、データ損失防止 (DLP) ポリシーはメタデータ (Office 365 のラベルを含む) にのみ作用し、暗号化されたファイルのコンテンツ (ファイル内のクレジット カード番号など) には作用しなくなります。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p116">Be aware that when encryption is applied to files stored in OneDrive and SharePoint, the service cannot process the contents of these files. This means that features such as co-authoring, eDiscovery, search, Delve, and other collaborative features do not work. Also, data loss prevention (DLP) policies can work only with the metadata (including Office 365 labels) but not the contents of encrypted files (such as credit card numbers within files).</span></span>

<span data-ttu-id="69aa4-p117">これは、OneDrive および SharePoint に保存されているコンテンツにのみ当てはまります。Exchange Online では、トランスポート ルールで[スーパー ユーザー アカウント](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-super-users)が使用されるため、暗号化されたコンテンツのスキャンと DLP ポリシーの強制適用が可能です。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p117">This applies only to content stored in OneDrive and SharePoint. In Exchange Online, transport rules use the [super user account](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-super-users) so that they can scan encrypted content and enforce DLP policies.</span></span>

## <a name="important-prerequisites"></a><span data-ttu-id="69aa4-184">重要な前提条件</span><span class="sxs-lookup"><span data-stu-id="69aa4-184">Important prerequisites</span></span>

<span data-ttu-id="69aa4-185">暗号化を使用する前に、次のタスクの実行が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="69aa4-185">Before you can use encryption, you might need to perform these tasks.</span></span>

### <a name="activating-azure-rights-management"></a><span data-ttu-id="69aa4-186">Azure Rights Management を有効化する</span><span class="sxs-lookup"><span data-stu-id="69aa4-186">Activating Azure Rights Management</span></span>

<span data-ttu-id="69aa4-p118">機密ラベルでの暗号化を使用する場合は、Azure Rights Management サービスがテナントで有効化されている必要があります。新しいテナントでは、このサービスが既定でオンになっていますが、手動で有効化することが必要になる場合もあります。詳細については、「[Rights Management をアクティブにする](https://docs.microsoft.com/ja-JP/azure/information-protection/activate-service)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p118">To use encryption in sensitivity labels, the Azure Rights Management service needs to be activated in your tenant. In newer tenants, the service is on by default, but you might need to manually activate the service. For more information, see [Activating Azure Rights Management](https://docs.microsoft.com/ja-JP/azure/information-protection/activate-service).</span></span>

### <a name="configure-exchange-for-azure-information-protection"></a><span data-ttu-id="69aa4-190">Azure Information Protection 用に Exchange を構成する</span><span class="sxs-lookup"><span data-stu-id="69aa4-190">Configure Exchange for Azure Information Protection</span></span>

<span data-ttu-id="69aa4-p119">ユーザーが Outlook で電子メールの保護のためにラベルを適用するまでは、Azure Information Protection 用に Exchange を構成する必要はありません。ただし、Exchange が Azure Information Protection 用に構成されるまで、Exchange には Azure Rights Management 保護の使用よる完全な機能が備わりません。</span><span class="sxs-lookup"><span data-stu-id="69aa4-p119">Exchange does not have to be configured for Azure Information Protection before users can apply labels in Outlook to protect their emails. However, until Exchange is configured for Azure Information Protection, you do not get the full functionality of using Azure Rights Management protection with Exchange.</span></span>
 
<span data-ttu-id="69aa4-193">たとえば、ユーザーは保護された電子メールを携帯電話や Outlook on the web で表示できません。また、保護された電子メールは検索用のインデックスを作成できません。さらに、Rights Management 保護用に Exchange Online DLP を構成することもできません。</span><span class="sxs-lookup"><span data-stu-id="69aa4-193">For example, users cannot view protected emails on mobile phones or with Outlook on the web, protected emails cannot be indexed for search, and you cannot configure Exchange Online DLP for Rights Management protection.</span></span> 

<span data-ttu-id="69aa4-194">このような追加のシナリオを Exchange でサポートする場合は、次の項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69aa4-194">To ensure that Exchange can support these additional scenarios, see the following:</span></span>

- <span data-ttu-id="69aa4-195">Exchange Online の場合は、「[Exchange Online: IRM 構成](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-office365#exchange-online-irm-configuration)」の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69aa4-195">For Exchange Online, see the instructions for [Exchange Online: IRM Configuration](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-office365#exchange-online-irm-configuration).</span></span>
- <span data-ttu-id="69aa4-196">Exchange On-Premises の場合は、[RMS コネクタを展開して Exchange サーバーを構成する](https://docs.microsoft.com/ja-JP/azure/information-protection/deploy-rms-connector)必要があります。</span><span class="sxs-lookup"><span data-stu-id="69aa4-196">For Exchange on-premises, you must deploy the [RMS connector and configure your Exchange servers](https://docs.microsoft.com/ja-JP/azure/information-protection/deploy-rms-connector).</span></span> 
