---
title: Office 365 でアーカイブ Twitter データにコネクタを展開する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理者は、Office 365 に Twitter データをインポートしてアーカイブするためのネイティブコネクタをセットアップできます。 このデータを Office 365 にインポートした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織の Twitter データのガバナンスを管理できます。
ms.openlocfilehash: 2f9d4842a834858b40e1d788f34f4fb8b2d5b9fd
ms.sourcegitcommit: 5bd7a97aeab1c89e0a3660ba7bdb3200224107a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2019
ms.locfileid: "34104013"
---
# <a name="deploy-a-connector-to-archive-twitter-data-in-office-365"></a><span data-ttu-id="b954d-104">Office 365 でアーカイブ Twitter データにコネクタを展開する</span><span class="sxs-lookup"><span data-stu-id="b954d-104">Deploy a connector to archive Twitter data in Office 365</span></span>

<span data-ttu-id="b954d-105">この記事では、Office 365 インポートサービスを使用して組織の Twitter アカウントから Office 365 にデータをインポートするコネクタを展開するための段階的なプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b954d-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Office 365.</span></span> <span data-ttu-id="b954d-106">このプロセスの概要と、Twitter コネクタを展開するために必要な前提条件の一覧については、「[サンプルコネクタを使用して Office 365 の Twitter データをアーカイブする (プレビュー)](archive-twitter-data-with-sample-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b954d-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Use a sample connector to archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="b954d-107">手順 1: パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="b954d-107">Step 1: Download the package</span></span>

<span data-ttu-id="b954d-108">の GitHub リポジトリのリリースセクションから、構築済みパッケージをダウンロード[https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)します。</span><span class="sxs-lookup"><span data-stu-id="b954d-108">Download the prebuilt package from the Release section in the GitHub repository at [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> <span data-ttu-id="b954d-109">最新リリースの下で、 **SampleConnector**という名前の zip ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b954d-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="b954d-110">この zip ファイルは、手順4で Azure にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="b954d-110">You will upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="b954d-111">手順 2: Azure Active Directory でアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="b954d-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="b954d-112">に<https://portal.azure.com>移動し、Office 365 グローバル管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="b954d-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![](media/TCimage01.png)

2. <span data-ttu-id="b954d-113">左側のナビゲーションウィンドウで、[ **Azure Active Directory**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-113">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![](media/TCimage02.png)

3. <span data-ttu-id="b954d-114">左側のナビゲーションウィンドウで、[**アプリの登録 (プレビュー)** ] をクリックし、[**新しい登録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-114">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![](media/TCimage03.png)

4. <span data-ttu-id="b954d-115">アプリケーションを登録します。</span><span class="sxs-lookup"><span data-stu-id="b954d-115">Register the application.</span></span> <span data-ttu-id="b954d-116">[**リダイレクト URI (オプション)**] で、[アプリケーションの種類] ドロップダウンリストから<https://portal.azure.com> [Web] を選択し、URI のボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="b954d-116">Under **Redirect URI (optional)**, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![](media/TCimage04.png)

5. <span data-ttu-id="b954d-117">**アプリケーション (クライアント) id**と**ディレクトリ (テナント) id**をコピーし、それをテキストファイルまたは他の安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="b954d-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="b954d-118">これらの Id は、後の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="b954d-118">You’ll use these IDs in later steps.</span></span>

    ![](media/TCimage05.png)

6. <span data-ttu-id="b954d-119">[**証明書 &] [新しいアプリ**] および [**クライアントシークレット**] の下で、[**新しいクライアントシークレット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-119">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![](media/TCimage06.png)

7. <span data-ttu-id="b954d-120">新しいシークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="b954d-120">Create a new secret.</span></span> <span data-ttu-id="b954d-121">[説明] ボックスに、シークレットを入力し、有効期限を選択します。</span><span class="sxs-lookup"><span data-stu-id="b954d-121">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![](media/TCimage08.png)

8. <span data-ttu-id="b954d-122">シークレットの値をコピーして、テキストファイルまたは他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="b954d-122">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="b954d-123">これは、後の手順で使用する AAD アプリケーションシークレットです。</span><span class="sxs-lookup"><span data-stu-id="b954d-123">This is the AAD application secret that you will use in later steps.</span></span>

   ![](media/TCimage09.png)

9. <span data-ttu-id="b954d-124">**マニフェスト**に移動し、次のスクリーンショットで強調表示されているように、identifieruris (AAD アプリケーション Uri とも呼ばれる) をコピーします。</span><span class="sxs-lookup"><span data-stu-id="b954d-124">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="b954d-125">AAD アプリケーション Uri をテキストファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="b954d-125">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="b954d-126">手順6で使用します。</span><span class="sxs-lookup"><span data-stu-id="b954d-126">You’ll use it in Step 6.</span></span>

    ![](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="b954d-127">手順 3: Azure storage アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b954d-127">Step 3: Create an Azure storage account</span></span>

1.  <span data-ttu-id="b954d-128">組織の Azure ホームページに移動します。</span><span class="sxs-lookup"><span data-stu-id="b954d-128">Go to the Azure home page for your organization.</span></span>

    ![](media/TCimage11.png)

2. <span data-ttu-id="b954d-129">[**リソースの作成**] をクリックし、検索ボックスに「**ストレージアカウント**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b954d-129">Click **Create a resource** and they type **storage account** in the search box.</span></span>

   ![](media/TCimage12.png)

3. <span data-ttu-id="b954d-130">[**記憶域**] をクリックし、[**ストレージアカウント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-130">Click **Storage**, and then click **Storage account**.</span></span>

   ![](media/TCimage13.png)

4. <span data-ttu-id="b954d-131">[**ストレージアカウントの作成**] ページの [サブスクリプション] ボックスで、使用している Azure サブスクリプションの種類に応じて、[**購入時に支払う**] または [**無料試用版**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b954d-131">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> 

   ![](media/TCimage14.png)

5. <span data-ttu-id="b954d-132">リソースグループを選択または作成します。</span><span class="sxs-lookup"><span data-stu-id="b954d-132">Select or create a resource group.</span></span>

   ![](media/TCimage15.png)

6. <span data-ttu-id="b954d-133">ストレージアカウントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b954d-133">Type a name for the storage account.</span></span>

   ![](media/TCimage16.png)

7. <span data-ttu-id="b954d-134">確認してから [**作成**] をクリックして、ストレージアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b954d-134">Review and then click **Create** to create the storage account.</span></span>

   ![](media/TCimage17.png)

8. <span data-ttu-id="b954d-135">しばらくしてから、[**更新**] をクリックし、[**リソースに移動**] をクリックして、ストレージアカウントに移動します。</span><span class="sxs-lookup"><span data-stu-id="b954d-135">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

   ![](media/TCimage18.png)

9. <span data-ttu-id="b954d-136">左側のナビゲーションウィンドウで [**アクセスキー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-136">Click **Access keys** in the left navigation pane.</span></span>

   ![](media/TCimage19.png)

10. <span data-ttu-id="b954d-137">**接続文字列**をコピーし、テキストファイルまたは他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="b954d-137">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="b954d-138">この操作は、手順4で web app リソースを作成するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="b954d-138">You’ll use this when creating a web app resource in Step 4.</span></span>

    ![](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="b954d-139">手順 4: Azure で新しい web app リソースを作成する</span><span class="sxs-lookup"><span data-stu-id="b954d-139">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="b954d-140">Azure portal の**ホーム**ページで、[**リソース\>すべて\>の Web アプリの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-140">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="b954d-141">[ **Web アプリ**] ページで、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-141">On the **Web app** page, click **Create**.</span></span>

   ![](media/TCimage21.png)

2. <span data-ttu-id="b954d-142">詳細を入力し (次の図を参照)、Web アプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="b954d-142">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="b954d-143">[**アプリ名**] ボックスに入力した名前が Azure APP service URL の作成に使用されることに注意してください。たとえば、twitterconnector.azurewebsites.net のようになります。</span><span class="sxs-lookup"><span data-stu-id="b954d-143">Note that the name that you enter in the **App name** box will be used to create the Azure app service URL; for example twitterconnector.azurewebsites.net.</span></span>

   ![](media/TCimage22.png)

3. <span data-ttu-id="b954d-144">新しく作成した web app リソースに移動し、左側のナビゲーションウィンドウで [**アプリケーション設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-144">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="b954d-145">[**アプリケーションの設定**] で、[**新しい設定の追加**] をクリックし、次の3つの設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="b954d-145">Under **Application settings**, click **Add new setting** and add the following three settings.</span></span> <span data-ttu-id="b954d-146">前の手順で入力したテキストファイルにコピーした値を使用します。</span><span class="sxs-lookup"><span data-stu-id="b954d-146">Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="b954d-147">**APISecretKey** –任意の値をシークレットとして入力できます。</span><span class="sxs-lookup"><span data-stu-id="b954d-147">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="b954d-148">これは、手順7でコネクタ web アプリにアクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b954d-148">This will be used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="b954d-149">**Storageaccountconnectionstring** –手順3で Azure storage アカウントを作成した後にコピーした接続文字列 Uri。</span><span class="sxs-lookup"><span data-stu-id="b954d-149">**StorageAccountConnectionString** – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="b954d-150">**tenantId** –手順2で、Azure Active Directory で Twitter connector アプリを作成した後にコピーした Office 365 組織のテナント ID。</span><span class="sxs-lookup"><span data-stu-id="b954d-150">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

    ![](media/TCimage23.png)

4. <span data-ttu-id="b954d-151">[**全般設定**] で、[**常にオン**] の横にある [**オン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-151">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="b954d-152">ページの上部にある [**保存**] をクリックして、アプリケーションの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="b954d-152">Click **Save** at the top of the page to save the application settings.</span></span>

   ![](media/TCimage24.png)

5. <span data-ttu-id="b954d-153">最後の手順では、手順1でダウンロードしたコネクタアプリソースコードを Azure にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="b954d-153">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="b954d-154">Web ブラウザーで、https://<AzureAppResourceName>に移動します。</span><span class="sxs-lookup"><span data-stu-id="b954d-154">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="b954d-155">たとえば、このセクションの手順2で指定した Azure app リソースの名前が**twitterconnector**の場合は、にhttps://twitterconnector.scm.azurewebsites.net/ZipDeployUi移動します。</span><span class="sxs-lookup"><span data-stu-id="b954d-155">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **twitterconnector**, then you would go to https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span></span>

6. <span data-ttu-id="b954d-156">手順1でダウンロードした SampleConnector をドラッグアンドドロップして、このページに移動します。</span><span class="sxs-lookup"><span data-stu-id="b954d-156">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="b954d-157">ファイルがアップロードされ、展開が正常に完了すると、次のスクリーンショットのようなページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b954d-157">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot.</span></span>

   ![](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a><span data-ttu-id="b954d-158">手順 5: Twitter アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="b954d-158">Step 5: Create the Twitter app</span></span>

1. <span data-ttu-id="b954d-159">にhttps://developer.twitter.com移動して、組織の開発者アカウントの資格情報を使用してログインし、[**アプリ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-159">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![TCimage25-5](media/TCimage25-5.png)
2. <span data-ttu-id="b954d-161">[**アプリの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-161">Click **Create an app**.</span></span>
   
   ![](media/TCimage26.png)

3. <span data-ttu-id="b954d-162">[**アプリの詳細**] で、アプリケーションに関する情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="b954d-162">Under **App details**, add information about the application.</span></span>

   ![](media/TCimage27.png)

4. <span data-ttu-id="b954d-163">Twitter 開発者ダッシュボードで、作成したばかりのアプリを選択し、表示されたアプリ ID をコピーして、テキストファイルまたはその他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="b954d-163">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="b954d-164">[**詳細**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-164">Then click **Details**.</span></span>
   
   ![](media/TCimage28.png)

5. <span data-ttu-id="b954d-165">[**キーとトークン**] タブの [**コンシューマー api キー** ] で、api シークレットキーをコピーして、テキストファイルまたは他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="b954d-165">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="b954d-166">次に、[**作成**] をクリックしてアクセストークンとアクセストークンシークレットを生成し、それをテキストファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="b954d-166">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![](media/TCimage29.png)

   <span data-ttu-id="b954d-167">次に、[**作成**] をクリックしてアクセストークンとアクセストークンシークレットを生成し、それをテキストファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="b954d-167">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="b954d-168">[**アクセス許可**] タブをクリックし、次のスクリーンショットに示されているようにアクセス許可を構成します。</span><span class="sxs-lookup"><span data-stu-id="b954d-168">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![](media/TCimage30.png)

7. <span data-ttu-id="b954d-169">アクセス許可の設定を保存した後、[**アプリの詳細**] タブをクリックし、[**編集 > 編集の詳細**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-169">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![](media/TCimage31.png)

8. <span data-ttu-id="b954d-170">次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="b954d-170">Do the following tasks:</span></span>

   - <span data-ttu-id="b954d-171">チェックボックスをオンにして、コネクタアプリが Twitter にサインインできるようにします。</span><span class="sxs-lookup"><span data-stu-id="b954d-171">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="b954d-172">次の形式を使用して OAuth リダイレクト Uri を追加します: \*\* \<connectorserviceuri>/Views/TwitterOAuth\**。この場合は、*コネクタサービス Uri\*の値が組織の Azure app service URL になります。例https://twitterconnector.azurewebsites.net/Views/TwitterOAuthを示します。</span><span class="sxs-lookup"><span data-stu-id="b954d-172">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

   ![](media/TCimage32.png)

<span data-ttu-id="b954d-173">Twitter 開発者アプリを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="b954d-173">The Twitter developer app is now ready to use.</span></span>

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="b954d-174">手順 6: コネクタ web アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="b954d-174">Step 6: Configure the connector web app</span></span> 

1. <span data-ttu-id="b954d-175">Https://\<AzureAppResourceName> に移動します (ここで、 **AzureAppResourceName**は手順4で名前を付けた Azure app リソースの名前です)。たとえば、名前が**twitterconnector**の場合は、にhttps://twitterconnector.azurewebsites.net移動します。</span><span class="sxs-lookup"><span data-stu-id="b954d-175">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4) For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="b954d-176">アプリのホームページは、次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="b954d-176">The home page of the app will look like the following screenshot.</span></span>

   ![](media/FBCimage41.png)

2. <span data-ttu-id="b954d-177">[**構成**] をクリックして、サインインページを表示します。</span><span class="sxs-lookup"><span data-stu-id="b954d-177">Click **Configure** to display a sign in page.</span></span>

   ![](media/FBCimage42.png)

3. <span data-ttu-id="b954d-178">[テナント Id] ボックスに、テナント Id を入力するか貼り付けます (手順2で取得したもの)。</span><span class="sxs-lookup"><span data-stu-id="b954d-178">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="b954d-179">[パスワード] ボックスに、APISecretKey (手順2で取得した) を入力するか貼り付け、[**構成設定の設定**] をクリックして**構成の詳細**ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="b954d-179">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

   ![](media/TCimage35.png)

4. <span data-ttu-id="b954d-180">[**構成の詳細**] で、次の構成設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="b954d-180">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="b954d-181">**Twitter アプリケーション id** -手順5で作成した twitter アプリケーションのアプリ id。</span><span class="sxs-lookup"><span data-stu-id="b954d-181">**Twitter application ID** - The app ID for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="b954d-182">**Twitter アプリケーションシークレット**-手順5で作成した twitter アプリケーションの API シークレットキー。</span><span class="sxs-lookup"><span data-stu-id="b954d-182">**Twitter application secret** - The API secret key for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="b954d-183">**Twitter クライアントトークン**-手順5で作成したアクセストークン。</span><span class="sxs-lookup"><span data-stu-id="b954d-183">**Twitter client token** - The access token that you created in Step 5.</span></span>
   - <span data-ttu-id="b954d-184">**Twitter クライアントトークンシークレット**-手順5で作成したアクセストークンシークレット。</span><span class="sxs-lookup"><span data-stu-id="b954d-184">**Twitter client token secret** - The access token secret that you created in Step 5.</span></span>
   - <span data-ttu-id="b954d-185">**AAD アプリケーション id** -手順2で作成した Azure Active Directory アプリのアプリケーション id</span><span class="sxs-lookup"><span data-stu-id="b954d-185">**AAD application ID** - The application ID for the Azure Active Directory app that you created in Step 2</span></span>
   - <span data-ttu-id="b954d-186">**AAD アプリケーションシークレット**-手順4で作成した APISecretKey シークレットの値。</span><span class="sxs-lookup"><span data-stu-id="b954d-186">**AAD application secret** - The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="b954d-187">**Aad アプリケーション uri** -手順2で取得した Aad アプリケーション uri。たとえば、 https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213のようになります。</span><span class="sxs-lookup"><span data-stu-id="b954d-187">**AAD application Uri** - The AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span></span>
   - <span data-ttu-id="b954d-188">**App insights インストルメンテーションキー** -このボックスは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="b954d-188">**App insights instrumentation key** - Leave this box blank.</span></span>

5. <span data-ttu-id="b954d-189">[**保存**] をクリックしてコネクタの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="b954d-189">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a><span data-ttu-id="b954d-190">手順 7: セキュリティ/コンプライアンスセンターでカスタムコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="b954d-190">Step 7: Set up a custom connector in the security and compliance center</span></span>

1.  <span data-ttu-id="b954d-191">に移動<https://protection.office.com>して、[**データ\>ガバナンス\> ] [サードパーティデータのインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-191">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

    ![](media/TCimage36.png)

2. <span data-ttu-id="b954d-192">[**コネクタの追加**] をクリックし、[ **Twitter**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-192">Click **Add a connector** and then click **Twitter**.</span></span>

   ![](media/TCimage37.png)

3. <span data-ttu-id="b954d-193">[**コネクタアプリの追加**] ページで、次の情報を入力し、[**コネクタの検証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-193">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    - <span data-ttu-id="b954d-194">最初のボックスに、 **Twitter**などのコネクタの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b954d-194">In the first box, type a name for the connector, such as **Twitter**.</span></span>
    - <span data-ttu-id="b954d-195">2番目のボックスに、手順4で追加した APISecretKey の値を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b954d-195">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="b954d-196">3番目のボックスに、Azure app service の URL を入力するか、貼り付けます。例**https://twitterconnector.azurewebsites.net**を示します。</span><span class="sxs-lookup"><span data-stu-id="b954d-196">In the third box, type or paste the Azure app service URL; for example **https://twitterconnector.azurewebsites.net**.</span></span>

   <span data-ttu-id="b954d-197">コネクタの検証が正常に完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-197">After the connector is successfully validated, click **Next**.</span></span>

   ![](media/TCimage38.png)

4. <span data-ttu-id="b954d-198">[**コネクタアプリを使用してログイン] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-198">Click **Login with Connector App**.</span></span>

   ![](media/TCimage39.png)

5. <span data-ttu-id="b954d-199">APISecretKey をもう一度入力するか貼り付け、[**コネクタサービスにログイン] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-199">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![](media/TCimage40.png)


6. <span data-ttu-id="b954d-200">[ **Twitter で続行] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-200">Click **Continue with Twitter**.</span></span>

7. <span data-ttu-id="b954d-201">[Twitter サインイン] ページで、組織の Twitter アカウントのアカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="b954d-201">On the Twitter sign in page, sign in using the credentials for the account for your organization’s Twitter account.</span></span>

   ![](media/TCimage42.png)

   <span data-ttu-id="b954d-202">サインインした後、Twitter ページに次のメッセージが表示されます。 "Twitter Connector ジョブは正常にセットアップされました。"</span><span class="sxs-lookup"><span data-stu-id="b954d-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

8. <span data-ttu-id="b954d-203">[**完了**] をクリックして、Twitter connector の設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="b954d-203">Click **Finish** to complete setting up the Twitter connector.</span></span>

9. <span data-ttu-id="b954d-204">[**フィルターの設定**] ページでは、特定の年齢のアイテムをインポート (およびアーカイブ) するためのフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="b954d-204">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="b954d-205">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b954d-205">Click **Next**.</span></span>

   ![](media/TCimage44.png)

10. <span data-ttu-id="b954d-206">[**ストレージアカウントの設定**] ページで、Twitter アイテムがインポートされる Office 365 メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="b954d-206">On the **Set Storage Account** page, select the Office 365 mailbox that the Twitter items will be imported to.</span></span>

    ![](media/TCimage45.png)

11. <span data-ttu-id="b954d-207">設定を確認し、[**完了**] をクリックして、セキュリティ _AMP_ コンプライアンスセンターでコネクタの設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="b954d-207">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![](media/TCimage46.png)

    ![](media/TCimage47.png)

12. <span data-ttu-id="b954d-208">[**サードパーティのデータをアーカイブ**する] ページに移動して、インポートプロセスの進行状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="b954d-208">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![](media/TCimage48.png)
