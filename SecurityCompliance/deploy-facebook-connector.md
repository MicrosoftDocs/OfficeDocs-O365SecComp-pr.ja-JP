---
title: Office 365 で Facebook データをアーカイブするためのコネクタの展開
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理者は、Facebook のビジネスページをインポートおよびアーカイブするためのネイティブコネクタを Office 365 にセットアップすることができます。 このデータを Office 365 にインポートした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織の Facebook データのガバナンスを管理できます。
ms.openlocfilehash: 1f5b0f241616cc95e79e80d054a8782f97c5887b
ms.sourcegitcommit: 3699da2cad6e6a2002083e2884e32393dacab0ca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "34694739"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a><span data-ttu-id="9d206-104">Office 365 で Facebook データをアーカイブするためのコネクタの展開</span><span class="sxs-lookup"><span data-stu-id="9d206-104">Deploy a connector to archive Facebook data in Office 365</span></span>

<span data-ttu-id="9d206-105">この記事では、Office 365 インポートサービスを使用して Facebook のビジネスページから Office 365 にデータをインポートするコネクタを展開するための段階的なプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9d206-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Office 365.</span></span> <span data-ttu-id="9d206-106">このプロセスの概要と、Facebook コネクタを展開するために必要な前提条件の一覧については、「[サンプルコネクタを使用して Office 365 で facebook データをアーカイブする (プレビュー)](archive-facebook-data-with-sample-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d206-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Use a sample connector to archive Facebook data in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="9d206-107">手順 1: パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="9d206-107">Step 1: Download the package</span></span>

<span data-ttu-id="9d206-108">の GitHub リポジトリのリリースセクションから、構築済みパッケージをダウンロード<https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>します。</span><span class="sxs-lookup"><span data-stu-id="9d206-108">Download the prebuilt package from the Release section in the GitHub repository at <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span></span> <span data-ttu-id="9d206-109">最新リリースの下で、 **SampleConnector**という名前の zip ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9d206-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="9d206-110">この zip ファイルを手順4で Azure にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="9d206-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="9d206-111">手順 2: Azure Active Directory でアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="9d206-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="9d206-112">に<https://portal.azure.com>移動し、Office 365 グローバル管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="9d206-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![AAD でアプリを作成する](media/FBCimage1.png)

2. <span data-ttu-id="9d206-114">左側のナビゲーションウィンドウで、[ **Azure Active Directory**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![](media/FBCimage2.png)

3. <span data-ttu-id="9d206-115">左側のナビゲーションウィンドウで、[**アプリの登録 (プレビュー)** ] をクリックし、[**新しい登録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-115">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![](media/FBCimage3.png)

4. <span data-ttu-id="9d206-116">アプリケーションを登録します。</span><span class="sxs-lookup"><span data-stu-id="9d206-116">Register the application.</span></span> <span data-ttu-id="9d206-117">[リダイレクト URI] で、[アプリケーションの種類] ドロップダウンリストから<https://portal.azure.com> [Web] を選択し、URI のボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="9d206-117">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![](media/FBCimage4.png)

5. <span data-ttu-id="9d206-118">**アプリケーション (クライアント) id**と**ディレクトリ (テナント) id**をコピーし、それをテキストファイルまたは他の安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="9d206-118">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="9d206-119">これらの Id は、後の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="9d206-119">You use these IDs in later steps.</span></span>

   ![](media/FBCimage5.png)

6. <span data-ttu-id="9d206-120">[証明書] に移動して **、新しいアプリのシークレット & します。**</span><span class="sxs-lookup"><span data-stu-id="9d206-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![](media/FBCimage6.png)

7. <span data-ttu-id="9d206-121">[**新しいクライアントシークレット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-121">Click **New client secret**</span></span>

   ![](media/FBCimage7.png)

8. <span data-ttu-id="9d206-122">新しいシークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="9d206-122">Create a new secret.</span></span> <span data-ttu-id="9d206-123">[説明] ボックスに、シークレットを入力し、有効期限を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d206-123">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![](media/FBCimage8.png)

9. <span data-ttu-id="9d206-124">シークレットの値をコピーして、テキストファイルまたは他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="9d206-124">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="9d206-125">これは、後の手順で使用する AAD アプリケーションシークレットです。</span><span class="sxs-lookup"><span data-stu-id="9d206-125">This is the AAD application secret that you use in later steps.</span></span>

   ![](media/FBCimage9.png)

10. <span data-ttu-id="9d206-126">**マニフェスト**に移動し、次のスクリーンショットで強調表示されているように、identifieruris (AAD アプリケーション Uri とも呼ばれる) をコピーします。</span><span class="sxs-lookup"><span data-stu-id="9d206-126">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="9d206-127">AAD アプリケーション Uri をテキストファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9d206-127">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="9d206-128">手順6で使用します。</span><span class="sxs-lookup"><span data-stu-id="9d206-128">You use it in Step 6.</span></span>

   ![](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="9d206-129">手順 3: Azure storage アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="9d206-129">Step 3: Create an Azure storage account</span></span>

1. <span data-ttu-id="9d206-130">組織の Azure ホームページに移動します。</span><span class="sxs-lookup"><span data-stu-id="9d206-130">Go to the Azure home page for your organization.</span></span>

    ![](media/FBCimage11.png)

2. <span data-ttu-id="9d206-131">[**リソースの作成**] をクリックし、検索ボックスに「**ストレージアカウント**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9d206-131">Click **Create a resource** and they type **storage account** in the search box.</span></span>

    ![](media/FBCimage12.png)

3. <span data-ttu-id="9d206-132">[**記憶域**] をクリックし、[**ストレージアカウント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-132">Click **Storage**, and then click **Storage account**.</span></span>

    ![](media/FBCimage13.png)

4. <span data-ttu-id="9d206-133">[**ストレージアカウントの作成**] ページの [サブスクリプション] ボックスで、使用している Azure サブスクリプションの種類に応じて、[**購入時に支払う**] または [**無料試用版**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d206-133">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> <span data-ttu-id="9d206-134">次に、リソースグループを選択または作成します。</span><span class="sxs-lookup"><span data-stu-id="9d206-134">Then select or create a resource group.</span></span>

    ![](media/FBCimage14.png)

5. <span data-ttu-id="9d206-135">ストレージアカウントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9d206-135">Type a name for the storage account.</span></span>

    ![](media/FBCimage15.png)

6. <span data-ttu-id="9d206-136">確認してから [**作成**] をクリックして、ストレージアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="9d206-136">Review and then click **Create** to create the storage account.</span></span>

    ![](media/FBCimage16.png)

7. <span data-ttu-id="9d206-137">しばらくしてから、[**更新**] をクリックし、[**リソースに移動**] をクリックして、ストレージアカウントに移動します。</span><span class="sxs-lookup"><span data-stu-id="9d206-137">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

    ![](media/FBCimage17.png)

8. <span data-ttu-id="9d206-138">左側のナビゲーションウィンドウで [**アクセスキー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-138">Click **Access keys** in the left navigation pane.</span></span>

    ![](media/FBCimage18.png)

9. <span data-ttu-id="9d206-139">**接続文字列**をコピーし、テキストファイルまたは他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="9d206-139">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="9d206-140">これは、web アプリケーションリソースを作成するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="9d206-140">You use this when creating a web app resource.</span></span>

    ![](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="9d206-141">手順 4: Azure で新しい web app リソースを作成する</span><span class="sxs-lookup"><span data-stu-id="9d206-141">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="9d206-142">Azure portal の**ホーム**ページで、[**リソース\>すべて\>の Web アプリの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-142">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="9d206-143">[ **Web アプリ**] ページで、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-143">On the **Web app** page, click **Create**.</span></span> 

   ![](media/FBCimage20.png)

2. <span data-ttu-id="9d206-144">詳細を入力し (次の図を参照)、Web アプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="9d206-144">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="9d206-145">[**アプリケーション名**] ボックスに入力した名前が Azure App SERVICE の URL を作成するために使用されることに注意してください。たとえば、fbconnector.azurewebsites.net のようになります。</span><span class="sxs-lookup"><span data-stu-id="9d206-145">Note that the name that you enter in the **App name** box is used to create the Azure app service URL; for example, fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage21.png)

3. <span data-ttu-id="9d206-146">新しく作成した web app リソースに移動し、左側のナビゲーションウィンドウで [**アプリケーション設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-146">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="9d206-147">[アプリケーションの設定] で、[新しい設定の追加] をクリックし、次の3つの設定を追加します。値 (前の手順で入力したテキストファイルにコピーした値) を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d206-147">Under Application settings, click Add new setting and add the following three settings: Use the values (that you copied to the text file from the previous steps):</span></span> 

    <span data-ttu-id="9d206-148">– **APISecretKey** –任意の値をシークレットとして入力できます。</span><span class="sxs-lookup"><span data-stu-id="9d206-148">– **APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="9d206-149">これは、手順7でコネクタ web アプリにアクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9d206-149">This is used to access the connector web app in Step 7.</span></span>

    <span data-ttu-id="9d206-150">– \* \* StorageAccountConnectionString —手順3で Azure storage アカウントを作成した後にコピーした接続文字列 Uri。</span><span class="sxs-lookup"><span data-stu-id="9d206-150">– \*\*StorageAccountConnectionString — The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    <span data-ttu-id="9d206-151">– **tenantId** –手順2で Azure Active Directory で Facebook connector アプリを作成した後にコピーした Office 365 組織のテナント ID。</span><span class="sxs-lookup"><span data-stu-id="9d206-151">– **tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

    ![](media/FBCimage22.png)

4. <span data-ttu-id="9d206-152">[**全般設定**] で、[**常にオン**] の横にある [**オン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-152">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="9d206-153">ページの上部にある [**保存**] をクリックして、アプリケーションの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="9d206-153">Click **Save** at the top of the page to save application settings.</span></span>

   ![](media/FBCimage23.png)

5. <span data-ttu-id="9d206-154">最後の手順では、手順1でダウンロードしたコネクタアプリソースコードを Azure にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="9d206-154">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="9d206-155">Web ブラウザーで、https://<AzureAppResourceName>に移動します。</span><span class="sxs-lookup"><span data-stu-id="9d206-155">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="9d206-156">たとえば、Azure app リソース (このセクションの手順2で名前を付けた) の名前が**fbconnector**の場合は、にhttps://fbconnector.scm.azurewebsites.net/ZipDeployUi移動します。</span><span class="sxs-lookup"><span data-stu-id="9d206-156">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **fbconnector**, then you would go to https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span></span> 

6. <span data-ttu-id="9d206-157">手順1でダウンロードした SampleConnector をドラッグアンドドロップして、このページに移動します。</span><span class="sxs-lookup"><span data-stu-id="9d206-157">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="9d206-158">ファイルがアップロードされ、展開が正常に完了すると、ページは次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="9d206-158">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a><span data-ttu-id="9d206-159">手順 5: Facebook アプリを登録する</span><span class="sxs-lookup"><span data-stu-id="9d206-159">Step 5: Register the Facebook app</span></span>

1. <span data-ttu-id="9d206-160">に<https://developers.facebook.com>移動して、組織の Facebook ビジネスページのアカウントの資格情報を使用してログインし、[**新しいアプリの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-160">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![](media/FBCimage25.png)

2. <span data-ttu-id="9d206-161">新しいアプリ ID を作成します。</span><span class="sxs-lookup"><span data-stu-id="9d206-161">Create a new app ID.</span></span>

   ![](media/FBCimage26.png)

3. <span data-ttu-id="9d206-162">左側のナビゲーションウィンドウで、[**製品の追加**] をクリックし、 **Facebook ログイン**タイルで [**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-162">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![](media/FBCimage27.png)

4. <span data-ttu-id="9d206-163">[Facebook ログインの統合] ページで、[ **Web**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-163">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![](media/FBCimage28.png)

5. <span data-ttu-id="9d206-164">Azure app service の URL を追加します。例https://fbconnector.azurewebsites.netを示します。</span><span class="sxs-lookup"><span data-stu-id="9d206-164">Add the Azure app service URL; for example https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage29.png)

6. <span data-ttu-id="9d206-165">Facebook ログインセットアップのクイックスタートセクションを完了します。</span><span class="sxs-lookup"><span data-stu-id="9d206-165">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![](media/FBCimage30.png)

7. <span data-ttu-id="9d206-166">[ **Facebook ログイン**] の左側のナビゲーションウィンドウで、[**設定**] をクリックし、[**有効な oauth リダイレクト**URI] ボックスに oauth リダイレクト uri を追加します。</span><span class="sxs-lookup"><span data-stu-id="9d206-166">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="9d206-167">\*\* \</Views/facebookoauth の>\*\* 形式を使用します。この場合は、を使用します。この場合、コネクタサービス uri の値は組織の Azure app service URL になります。たとえば、 https://fbconnector.azurewebsites.netのようになります。</span><span class="sxs-lookup"><span data-stu-id="9d206-167">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage31.png)

8. <span data-ttu-id="9d206-168">左側のナビゲーションウィンドウで、[**製品の追加**] をクリックし、[webhooks] をクリックし**ます。**</span><span class="sxs-lookup"><span data-stu-id="9d206-168">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="9d206-169">**ページ**のプルダウンメニューで、[**ページ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-169">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![](media/FBCimage32.png)

9. <span data-ttu-id="9d206-170">Webhooks コールバック URL を追加し、検証トークンを追加します。</span><span class="sxs-lookup"><span data-stu-id="9d206-170">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="9d206-171">コールバック URL の形式。 \*\* <connectorserviceuri>/api/fbpagewebhook\*\*の形式を使用します。ここで、コネクタサービス uri の値は、組織の Azure app service URL になります。例https://fbconnector.azurewebsites.netを示します。</span><span class="sxs-lookup"><span data-stu-id="9d206-171">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example https://fbconnector.azurewebsites.net.</span></span> 

    <span data-ttu-id="9d206-172">Verify トークンは、強力なパスワードと類似している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d206-172">The verify token should similar to a strong password.</span></span> <span data-ttu-id="9d206-173">検証トークンをテキストファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9d206-173">Copy the verify token to a text file or other storage location.</span></span>

     ![](media/FBCimage33.png)

10. <span data-ttu-id="9d206-174">フィードのエンドポイントをテストし、サブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="9d206-174">Test and subscribe to the endpoint for feed.</span></span>

    ![](media/FBCimage34.png)

11. <span data-ttu-id="9d206-175">プライバシー URL、アプリアイコン、およびビジネス用途を追加します。</span><span class="sxs-lookup"><span data-stu-id="9d206-175">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="9d206-176">また、アプリケーション ID とアプリシークレットをテキストファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9d206-176">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![](media/FBCimage35.png)

12. <span data-ttu-id="9d206-177">アプリを公開します。</span><span class="sxs-lookup"><span data-stu-id="9d206-177">Make the app public.</span></span>

    ![](media/FBCimage36.png)

13. <span data-ttu-id="9d206-178">管理者またはテスト担当者の役割にユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="9d206-178">Add user to the admin or tester role.</span></span>

    ![](media/FBCimage37.png)

14. <span data-ttu-id="9d206-179">ページの**パブリックコンテンツのアクセス**許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="9d206-179">Add the **Page Public Content Access** permission.</span></span>

    ![](media/FBCimage38.png)

15. <span data-ttu-id="9d206-180">[ページの管理] アクセス許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="9d206-180">Add Manage Pages permission.</span></span>

    ![](media/FBCimage39.png)

16. <span data-ttu-id="9d206-181">Facebook によって確認されたアプリケーションを取得します。</span><span class="sxs-lookup"><span data-stu-id="9d206-181">Get the application reviewed by Facebook.</span></span>

    ![](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="9d206-182">手順 6: コネクタ web アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="9d206-182">Step 6: Configure the connector web app</span></span>

1. <span data-ttu-id="9d206-183">Https://\<AzureAppResourceName> に移動します (ここで、AzureAppResourceName は、手順4で名前を付けた Azure app リソースの名前です)。たとえば、名前が**fbconnector**の場合https://fbconnector.azurewebsites.netは、に移動します。</span><span class="sxs-lookup"><span data-stu-id="9d206-183">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to https://fbconnector.azurewebsites.net.</span></span> <span data-ttu-id="9d206-184">アプリのホームページは、次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="9d206-184">The home page of the app will look like the following screenshot:</span></span>


   ![](media/FBCimage41.png)

2. <span data-ttu-id="9d206-185">[**構成**] をクリックして、サインインページを表示します。</span><span class="sxs-lookup"><span data-stu-id="9d206-185">Click **Configure** to display a sign in page.</span></span>
 
   ![](media/FBCimage42.png)

3. <span data-ttu-id="9d206-186">[テナント Id] ボックスに、テナント Id を入力するか貼り付けます (手順2で取得したもの)。</span><span class="sxs-lookup"><span data-stu-id="9d206-186">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="9d206-187">[パスワード] ボックスに、APISecretKey (手順2で取得した) を入力するか貼り付け、[**構成設定の設定**] をクリックして**構成の詳細**ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="9d206-187">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

    ![](media/FBCimage43.png)


4. <span data-ttu-id="9d206-188">[**構成の詳細**] で、次の構成設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="9d206-188">Under **Configuration Details**, enter the following configuration settings</span></span> 

   <span data-ttu-id="9d206-189">– **Facebook アプリケーション id** –手順5で取得した facebook アプリケーションのアプリ id。</span><span class="sxs-lookup"><span data-stu-id="9d206-189">– **Facebook application ID** – The app ID for the Facebook application that you obtained in Step 5.</span></span>
   <span data-ttu-id="9d206-190">– **Facebook アプリケーションシークレット**–手順5で取得した facebook アプリケーションのアプリシークレット。</span><span class="sxs-lookup"><span data-stu-id="9d206-190">– **Facebook application secret** – The app secret for the Facebook application that you obtained in Step 5.</span></span>
   <span data-ttu-id="9d206-191">– **Facebook webhook verify token** –手順5で作成した verify トークン。</span><span class="sxs-lookup"><span data-stu-id="9d206-191">– **Facebook webhooks verify token** – The verify token that you created in Step 5.</span></span>
   <span data-ttu-id="9d206-192">– **AAD APPLICATION id** –手順2で作成した Azure Active Directory アプリのアプリケーション id。</span><span class="sxs-lookup"><span data-stu-id="9d206-192">– **AAD application ID** – The application ID for the Azure Active Directory app that you created in Step 2.</span></span>
   <span data-ttu-id="9d206-193">– **AAD application secret** –手順4で作成した APISecretKey シークレットの値。</span><span class="sxs-lookup"><span data-stu-id="9d206-193">– **AAD application secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   <span data-ttu-id="9d206-194">– **Aad アプリケーション uri** –手順2で取得した Aad アプリケーション uri。たとえば、 https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213のようになります。</span><span class="sxs-lookup"><span data-stu-id="9d206-194">– **AAD application Uri** – The AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span></span>
   <span data-ttu-id="9d206-195">– **App insights instrumentation キー** –このボックスは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="9d206-195">– **App insights instrumentation key** – Leave this box blank.</span></span>

5. <span data-ttu-id="9d206-196">[**保存**] をクリックしてコネクタの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="9d206-196">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="9d206-197">手順 7: セキュリティ & コンプライアンスセンターでカスタムコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="9d206-197">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

1. <span data-ttu-id="9d206-198">に移動<https://protection.office.com>して、[**データ\>ガバナンス\> ] [サードパーティデータのインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-198">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

   ![](media/FBCimage44.png)

2.  <span data-ttu-id="9d206-199">[**コネクタの追加**] をクリックし、[ **Facebook のページ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-199">Click **Add a connector** and then click **Facebook pages**.</span></span>

    ![](media/FBCimage46.png)

3.  <span data-ttu-id="9d206-200">[**コネクタアプリの追加**] ページで、次の情報を入力し、[**コネクタの検証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-200">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    <span data-ttu-id="9d206-201">-最初のボックスに、 **Facebook**などのコネクタの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9d206-201">– In the first box, type a name for the connector, such as **Facebook**.</span></span>
    <span data-ttu-id="9d206-202">-2 番目のボックスに、手順4で追加した APISecretKey の値を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9d206-202">– In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    <span data-ttu-id="9d206-203">–3番目のボックスに、Azure app service の URL を入力するか、貼り付けます。例**https://fbconnector.azurewebsites.net**を示します。</span><span class="sxs-lookup"><span data-stu-id="9d206-203">– In the third box, type or paste the Azure app service URL; for example **https://fbconnector.azurewebsites.net**.</span></span>
 
    <span data-ttu-id="9d206-204">コネクタの検証が正常に完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-204">After the connector is successfully validated, click **Next**.</span></span>
    
    ![](media/FBCimage47.png)

4.  <span data-ttu-id="9d206-205">[**コネクタアプリを使用してログイン] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-205">Click **Login with Connector App**.</span></span>

    ![](media/FBCimage45.png)

5. <span data-ttu-id="9d206-206">APISecretKey をもう一度入力するか貼り付け、[**コネクタサービスにログイン] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-206">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![](media/FBCimage48.png)


6. <span data-ttu-id="9d206-207">[ **Facebook でログイン] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="9d206-207">Click **Login with Facebook.**</span></span>

   ![](media/FBCimage49.png)

7. <span data-ttu-id="9d206-208">[ **Facebook へのログイン**] ページで、組織の facebook ビジネスページのアカウントの資格情報を使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="9d206-208">On the **Log in to Facebook** page, log in using the credentials for the account for your organization’s Facebook Business pages.</span></span> <span data-ttu-id="9d206-209">ログインした Facebook アカウントに、組織の Facebook ビジネスページの管理者の役割が割り当てられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9d206-209">Make sure the Facebook account that you logged in to is assigned the admin role for your organization’s Facebook Business pages</span></span>

   ![](media/FBCimage50.png)

8. <span data-ttu-id="9d206-210">[**ページの選択**] をクリックして、Office 365 でアーカイブする組織のビジネスページを選択します。</span><span class="sxs-lookup"><span data-stu-id="9d206-210">Click **Select Pages** to choose your organization’s business pages that you want to archive in Office 365.</span></span>

   ![](media/FBCimage51.png)

9. <span data-ttu-id="9d206-211">ログインした Facebook アカウントによって管理されるビジネスページの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d206-211">A list of the Business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="9d206-212">アーカイブするページを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-212">Select the page to archive and then click **Save**.</span></span>

    ![](media/FBCimage52.png)

10. <span data-ttu-id="9d206-213">[**準備**] をクリックして、connector service アプリのセットアップを終了します。</span><span class="sxs-lookup"><span data-stu-id="9d206-213">Click **prepare** to exit the setup of the connector service app.</span></span>

    ![](media/FBCimage53.png)

11. <span data-ttu-id="9d206-214">[**フィルターの設定**] ページでは、特定の年齢のアイテムをインポート (およびアーカイブ) するためのフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="9d206-214">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="9d206-215">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d206-215">Click **Next**.</span></span>

    ![](media/FBCimage54.png)

12. <span data-ttu-id="9d206-216">[**ストレージアカウントの設定**] ページで、以前に選択した Facebook ビジネスページのアイテムがインポートされる Office 365 メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="9d206-216">On the **Set Storage Account** page, select the Office 365 mailbox that the items from the Facebook Business pages that you previously selected will be imported to.</span></span>

    ![](media/FBCimage55.png)

13. <span data-ttu-id="9d206-217">設定を確認し、[**完了**] をクリックして、セキュリティ & コンプライアンスセンターでコネクタの設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="9d206-217">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![](media/FBCimage56.png)

14. <span data-ttu-id="9d206-218">[**サードパーティのデータをアーカイブ**する] ページに移動して、インポートプロセスの進行状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="9d206-218">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![](media/FBCimage58.png)
