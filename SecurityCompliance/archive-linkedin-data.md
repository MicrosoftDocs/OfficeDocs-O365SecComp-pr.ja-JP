---
title: Office 365 で LinkedIn データをアーカイブするためのコネクタの設定 (プレビュー)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理者は、標準コネクタをセットアップして、LinkedIn Company ページから Office 365 にデータをインポートすることができます。 これにより、Office 365 でサードパーティのデータソースからデータをアーカイブできるため、法的情報保留、コンテンツ検索、およびアイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータのコンプライアンスを管理することができます。
ms.openlocfilehash: 2b89f990f18ae13ad15015f240ea4c4b0ec434b0
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2019
ms.locfileid: "35017948"
---
# <a name="set-up-a-connector-to-archive-linkedin-data-in-office-365-preview"></a><span data-ttu-id="b652a-104">Office 365 で LinkedIn データをアーカイブするためのコネクタの設定 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="b652a-104">Set up a connector to archive LinkedIn data in Office 365 (Preview)</span></span>

<span data-ttu-id="b652a-105">Office 365 の LinkedIn Company ページからデータをアーカイブするためのコネクタ機能は、プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="b652a-105">The connector feature to archive data from LinkedIn Company pages in Office 365 is in Preview.</span></span>

<span data-ttu-id="b652a-106">Office 365 のセキュリティ & コンプライアンスセンターのネイティブコネクタを使用して、LinkedIn の会社のページからデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="b652a-106">Use a native connector in the Security & Compliance Center in Office 365 to import and archive data from LinkedIn Company pages.</span></span> <span data-ttu-id="b652a-107">コネクタを設定して構成すると、24時間ごとに、特定の LinkedIn 会社のページのアカウントに接続されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-107">After you set up and configure a connector, it connects to the account for the specific LinkedIn Company page once every 24 hours.</span></span> <span data-ttu-id="b652a-108">コネクタは、会社のページに投稿されたメッセージを電子メールメッセージに変換し、そのアイテムを Office 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="b652a-108">The connector converts the messages posted to the Company page to an email message, and then imports those items to a mailbox in Office 365.</span></span>

<span data-ttu-id="b652a-109">LinkedIn 会社のページデータがメールボックスに保存された後、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、Office 365 アイテム保持ポリシーなどの Office 365 コンプライアンス機能を LinkedIn データに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="b652a-109">After the LinkedIn Company page data is stored in a mailbox, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies to LinkedIn data.</span></span> <span data-ttu-id="b652a-110">たとえば、コンテンツ検索を使用してこれらのアイテムを検索したり、高度な電子情報開示ケースの保管担当者にストレージメールボックスを関連付けたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b652a-110">For example, you can search for these items using Content Search or associate the storage mailbox with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="b652a-111">Office 365 で LinkedIn データをインポートおよびアーカイブするためのコネクタを作成することで、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="b652a-111">Creating a connector to import and archive LinkedIn data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="before-you--begin"></a><span data-ttu-id="b652a-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="b652a-112">Before you  begin</span></span>

- <span data-ttu-id="b652a-113">アーカイブする LinkedIn の会社のページの管理者である LinkedIn ユーザーアカウントのサインイン資格情報 (電子メールアドレスまたは電話番号とパスワード) を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b652a-113">You must have the sign-in credentials (email address or phone number and password) of a LinkedIn user account that is an admin for the LinkedIn Company Page that you want to archive.</span></span> <span data-ttu-id="b652a-114">これらの資格情報を使用して、コネクタを設定するときに LinkedIn にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b652a-114">You use these credentials to sign in to LinkedIn when setting up the connector.</span></span>

- <span data-ttu-id="b652a-115">LinkedIn Company Page コネクタを作成したユーザーには、Exchange Online のメールボックスのインポートのエクスポート役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b652a-115">The user who creates an LinkedIn Company Page connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="b652a-116">これは、セキュリティ & コンプライアンスセンターの [**サードパーティのデータをアーカイブ**する] ページにアクセスするために必要です。</span><span class="sxs-lookup"><span data-stu-id="b652a-116">This is required to access the **Archive third-party data** page in the Security & Compliance Center.</span></span> <span data-ttu-id="b652a-117">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="b652a-117">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="b652a-118">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="b652a-118">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="b652a-119">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="b652a-119">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="b652a-120">詳細については、記事「Manage role groups in Exchange Online」の「[役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)」または「[役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b652a-120">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-a-linkedin-connector"></a><span data-ttu-id="b652a-121">LinkedIn コネクタを作成する</span><span class="sxs-lookup"><span data-stu-id="b652a-121">Create a LinkedIn connector</span></span>

1. <span data-ttu-id="b652a-122">に移動<https://protection.office.com>して、[**データ\>ガバナンスのインポート**] をクリックし、[**サードパーティのデータをアーカイブ**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b652a-122">Go to <https://protection.office.com> and then click **Data governance \> Import** and then click **Archive third-party data**.</span></span>

2. <span data-ttu-id="b652a-123">[**サードパーティのデータをアーカイブ**する] ページで、[**コネクタの追加**] をクリックし、[ **LinkedIn**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b652a-123">On the **Archive third-party data** page, click **Add a connector**, and then click **LinkedIn**.</span></span>

3. <span data-ttu-id="b652a-124">[**サービス利用規約**] ページで、[**同意**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b652a-124">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="b652a-125">[ **Linkedin を使用**してサインインする] ページで、[ **linkedin でサインイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b652a-125">On the **Sign in with LinkedIn** page, click **Sign in with LinkedIn**.</span></span>

   <span data-ttu-id="b652a-126">LinkedIn の [サインイン] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-126">The LinkedIn sign in page is displayed.</span></span>

   ![LinkedIn サインインページ](media/LinkedInSigninPage.png)

5. <span data-ttu-id="b652a-128">LinkedIn の [サインイン] ページで、アーカイブする会社のページに関連付けられている LinkedIn アカウントの電子メールアドレス (または電話番号) とパスワードを入力し、[**サインイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b652a-128">On the LinkedIn sign in page, enter the email address (or phone number) and password for the LinkedIn account that associated with the company page that you want to archive, and then click **Sign in**.</span></span>

   <span data-ttu-id="b652a-129">ウィザードページが、サインインしたアカウントに関連付けられているすべての LinkedIn 会社のページの一覧と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-129">A wizard page is displayed with a list of all LinkedIn Company Pages associated with the account that you signed in to.</span></span> <span data-ttu-id="b652a-130">コネクタは、1つの会社のページに対してのみ構成できます。</span><span class="sxs-lookup"><span data-stu-id="b652a-130">A connector can only be configured for one company page.</span></span> <span data-ttu-id="b652a-131">組織に複数の LinkedIn Company ページがある場合は、それぞれに対してコネクタを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b652a-131">If your organization has multiple LinkedIn Company Pages, you have to create a connector for each one.</span></span>

   ![LinkedIn 会社のページの一覧を含むページが表示されます。](media/LinkedInSelectCompanyPage.png)


6. <span data-ttu-id="b652a-133">アイテムをアーカイブする会社のページを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b652a-133">Select the company page that you want to archive items from, and then click **Next**.</span></span>

7. <span data-ttu-id="b652a-134">[**フィルターの設定**] ページでは、特定の年齢のアイテムを最初にインポートするためのフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="b652a-134">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="b652a-135">年齢を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b652a-135">Select an age, and then click **Next**.</span></span>

8. <span data-ttu-id="b652a-136">[**ストレージアカウントの設定**] ページで、LinkedIn アイテムがインポートされる Office 365 メールボックスの電子メールアドレスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b652a-136">On the **Set storage account** page, type the email address of an Office 365 mailbox that the LinkedIn items will be imported to, and then click **Next**.</span></span> <span data-ttu-id="b652a-137">アイテムは、このメールボックスの受信トレイフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="b652a-137">Items are imported to the Inbox folder in this mailbox.</span></span>

9. <span data-ttu-id="b652a-138">コネクタの設定を確認し、[**保存**] をクリックしてコネクタのセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="b652a-138">Review the connector settings and then click **Save** to complete the connector setup.</span></span>

<span data-ttu-id="b652a-139">コネクタを作成した後、[**サードパーティのデータをアーカイブ**する] ページに戻ることができます (コネクタの一覧を更新するには、[**更新**] をクリックします)。新しいコネクタを表示します。</span><span class="sxs-lookup"><span data-stu-id="b652a-139">After you create the connector, you can go back to the **Archive third-party data** page (click **Refresh** if necessary to update the list of connectors) a view the new connector.</span></span> <span data-ttu-id="b652a-140">[**状態**] 列の値は、**開始を待機**しています。</span><span class="sxs-lookup"><span data-stu-id="b652a-140">The value in the **Status** column is **Waiting to start**.</span></span> <span data-ttu-id="b652a-141">最初のインポート処理が開始されるまでに最大で24時間かかります。</span><span class="sxs-lookup"><span data-stu-id="b652a-141">It takes up to 24 hours for the initial import process to be started.</span></span> <span data-ttu-id="b652a-142">コネクタが初めて実行され、LinkedIn アイテムがインポートされると、コネクタは24時間ごとに1回実行され、過去24時間に LinkedIn Company ページに作成された新しいアイテムをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b652a-142">After the first time the connector runs and imports the LinkedIn items, the connector will run once every 24 hours and import any new items that are created on the LinkedIn Company Page in the previous 24 hours.</span></span>

<span data-ttu-id="b652a-143">詳細を表示するには、[**サードパーティデータをアーカイブ**する] ページの一覧でコネクタをクリックして、フライアウトページを表示します。</span><span class="sxs-lookup"><span data-stu-id="b652a-143">To view more details, click the connector in the list on the **Archive third-party data** page to display the flyout page.</span></span> <span data-ttu-id="b652a-144">[**状態**] の下に表示される日付の範囲は、コネクタの作成時に選択された年齢フィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="b652a-144">Under **Status**, the date range that's displayed indicates the age filter that was selected when the connector was created.</span></span> 

## <a name="more-information"></a><span data-ttu-id="b652a-145">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b652a-145">More information</span></span>

- <span data-ttu-id="b652a-146">LinkedIn アイテムは、Office 365 のストレージメールボックスの受信トレイフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="b652a-146">LinkedIn items are imported to the Inbox folder in the storage mailbox in Office 365.</span></span> <span data-ttu-id="b652a-147">電子メールメッセージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-147">They appear as email messages.</span></span> <span data-ttu-id="b652a-148">メッセージの送信者の表示名は、LinkedIn Company ページの名前です。</span><span class="sxs-lookup"><span data-stu-id="b652a-148">The display name of the sender of the message is the name of the LinkedIn Company Page.</span></span> <span data-ttu-id="b652a-149">送信者の実際の電子メールアドレスは、ストレージメールボックスの電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="b652a-149">The actual email address of the sender is the email address of the storage mailbox.</span></span> <span data-ttu-id="b652a-150">会社のページの名前も件名行の前に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-150">The name of the company page is also pre-appended to the subject line.</span></span> 

- <span data-ttu-id="b652a-151">以前の動作により、Microsoft eDiscovery ツールを`from`使用`subject`して Office 365 にアーカイブされている LinkedIn アイテムを検索するときに、またはメールのプロパティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="b652a-151">Because of the previous behavior, you can search the `from` or `subject` email properties when using a Microsoft eDiscovery tool to search LinkedIn items that are archived in Office 365.</span></span> <span data-ttu-id="b652a-152">たとえば、会社のページの名前が "Contoso Company Page" の場合は、次のいずれかのプロパティを使用でき*ます。値*のペアは、キーワード検索クエリで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b652a-152">For example if the name of the company page is "Contoso Company Page", then you can use one of the following *property:value* pairs in the keyword search query:</span></span>
   
   ```
   from:"Contoso Company Page"
   ```

    <span data-ttu-id="b652a-153">または</span><span class="sxs-lookup"><span data-stu-id="b652a-153">Or</span></span>

   ```
   subject:"Contoso Company Page"
   ```

- <span data-ttu-id="b652a-154">Office 365 にインポートされた LinkedIn アイテムを簡単に検索または管理できるようにするために、ストレージメールボックスの所有者 (または FullAccess アクセス許可を割り当てられているユーザー) は、特定の LinkedIn Company ページから特定のフォルダーにアイテムを移動する受信トレイルールを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="b652a-154">To make it easier to locate or manage LinkedIn items imported to Office 365, the owner of the storage mailbox (or anyone assigned the FullAccess permission) can set up an inbox rule to move the items from a specific LinkedIn Company page to a specific folder.</span></span> <span data-ttu-id="b652a-155">これは、ストレージメールボックスを使用して、さまざまなサードパーティのデータソースからインポートされたアイテムをアーカイブする場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b652a-155">This is helpful if the storage mailbox is used to archive items that are imported from different third-party data sources.</span></span> <span data-ttu-id="b652a-156">たとえば、[件名] フィールドに特定の LinkedIn Company ページの名前を含むすべてのアイテムを特定のフォルダーに移動する受信トレイルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b652a-156">For example, you can create an inbox rule that moves all items that contain the name of a specific LinkedIn Company page in the subject field to a specific folder.</span></span>