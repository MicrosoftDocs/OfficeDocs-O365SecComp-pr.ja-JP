---
title: Office 365 でアーカイブ Twitter データにコネクタを展開する
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
description: 管理者は、Office 365 に Twitter データをインポートしてアーカイブするためのネイティブコネクタをセットアップできます。 このデータを Office 365 にインポートした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織の Twitter データのガバナンスを管理できます。
ms.openlocfilehash: c3c5af0fc42057d9fc2e8b8e67423398d6ed0ddf
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014776"
---
# <a name="deploy-a-connector-to-archive-twitter-data-in-office-365"></a>Office 365 でアーカイブ Twitter データにコネクタを展開する

この記事では、Office 365 インポートサービスを使用して組織の Twitter アカウントから Office 365 にデータをインポートするコネクタを展開するための段階的なプロセスについて説明します。 このプロセスの概要と、Twitter コネクタを展開するために必要な前提条件の一覧については、「[サンプルコネクタを使用して Office 365 の Twitter データをアーカイブする (プレビュー)](archive-twitter-data-with-sample-connector.md)」を参照してください。 

## <a name="step-1-download-the-package"></a>手順 1: パッケージをダウンロードする

の GitHub リポジトリのリリースセクションから、構築済みパッケージをダウンロード[https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)します。 最新リリースの下で、 **SampleConnector**という名前の zip ファイルをダウンロードします。 この zip ファイルを手順4で Azure にアップロードします。

## <a name="step-2-create-an-app-in-azure-active-directory"></a>手順 2: Azure Active Directory でアプリを作成する

1. に<https://portal.azure.com>移動し、Office 365 グローバル管理者アカウントの資格情報を使用してサインインします。

   ![](media/TCimage01.png)

2. 左側のナビゲーションウィンドウで、[ **Azure Active Directory**] をクリックします。

   ![](media/TCimage02.png)

3. 左側のナビゲーションウィンドウで、[**アプリの登録 (プレビュー)** ] をクリックし、[**新しい登録**] をクリックします。

   ![](media/TCimage03.png)

4. アプリケーションを登録します。 [**リダイレクト URI (オプション)**] で、[アプリケーションの種類] ドロップダウンリストから<https://portal.azure.com> [Web] を選択し、URI のボックスに入力します。

   ![](media/TCimage04.png)

5. **アプリケーション (クライアント) id**と**ディレクトリ (テナント) id**をコピーし、それをテキストファイルまたは他の安全な場所に保存します。 これらの Id は、後の手順で使用します。

    ![](media/TCimage05.png)

6. [**証明書 & 新しいアプリのシークレット**] および [**クライアントシークレット**] の下で、[**新しいクライアントシークレット**] をクリックします。

   ![](media/TCimage06.png)

7. 新しいシークレットを作成します。 [説明] ボックスに、シークレットを入力し、有効期限を選択します。 

   ![](media/TCimage08.png)

8. シークレットの値をコピーして、テキストファイルまたは他の保存場所に保存します。 これは、後の手順で使用する AAD アプリケーションシークレットです。

   ![](media/TCimage09.png)

9. **マニフェスト**に移動し、次のスクリーンショットで強調表示されているように、identifieruris (AAD アプリケーション Uri とも呼ばれる) をコピーします。 AAD アプリケーション Uri をテキストファイルまたは他の保存場所にコピーします。 手順6で使用します。

    ![](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a>手順 3: Azure storage アカウントを作成する

1.  組織の Azure ホームページに移動します。

    ![](media/TCimage11.png)

2. [**リソースの作成**] をクリックし、検索ボックスに「**ストレージアカウント**」と入力します。

   ![](media/TCimage12.png)

3. [**記憶域**] をクリックし、[**ストレージアカウント**] をクリックします。

   ![](media/TCimage13.png)

4. [**ストレージアカウントの作成**] ページの [サブスクリプション] ボックスで、使用している Azure サブスクリプションの種類に応じて、[**購入時に支払う**] または [**無料試用版**] を選択します。 

   ![](media/TCimage14.png)

5. リソースグループを選択または作成します。

   ![](media/TCimage15.png)

6. ストレージアカウントの名前を入力します。

   ![](media/TCimage16.png)

7. 確認してから [**作成**] をクリックして、ストレージアカウントを作成します。

   ![](media/TCimage17.png)

8. しばらくしてから、[**更新**] をクリックし、[**リソースに移動**] をクリックして、ストレージアカウントに移動します。

   ![](media/TCimage18.png)

9. 左側のナビゲーションウィンドウで [**アクセスキー** ] をクリックします。

   ![](media/TCimage19.png)

10. **接続文字列**をコピーし、テキストファイルまたは他の保存場所に保存します。 この操作は、手順4で web app リソースを作成するときに使用します。

    ![](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a>手順 4: Azure で新しい web app リソースを作成する

1. Azure portal の**ホーム**ページで、[**リソース\>すべて\>の Web アプリの作成**] をクリックします。 [ **Web アプリ**] ページで、[**作成**] をクリックします。

   ![](media/TCimage21.png)

2. 詳細を入力し (次の図を参照)、Web アプリを作成します。 [**アプリケーション名**] ボックスに入力した名前は、Azure app SERVICE の URL を作成するために使用されます。たとえば、twitterconnector.azurewebsites.net のようになります。

   ![](media/TCimage22.png)

3. 新しく作成した web app リソースに移動し、左側のナビゲーションウィンドウで [**アプリケーションの設定**] をクリックします。 [**アプリケーションの設定**] で、[**新しい設定の追加**] をクリックし、次の3つの設定を追加します。 前の手順で入力したテキストファイルにコピーした値を使用します。 

    – * * APISecretKey-任意の値をシークレットとして入力できます。 これは、手順7でコネクタ web アプリにアクセスするために使用されます。

    – **Storageaccountconnectionstring** –手順3で Azure storage アカウントを作成した後にコピーした接続文字列 Uri。

    – **tenantId** –手順2で、Azure Active Directory で Twitter connector アプリを作成した後にコピーした Office 365 組織のテナント ID。

    ![](media/TCimage23.png)

4. [**全般設定**] で、[**常にオン**] の横にある [**オン**] をクリックします。 ページの上部にある [**保存**] をクリックして、アプリケーションの設定を保存します。

   ![](media/TCimage24.png)

5. 最後の手順では、手順1でダウンロードしたコネクタアプリソースコードを Azure にアップロードします。 Web ブラウザーで、https://<AzureAppResourceName>に移動します。 たとえば、このセクションの手順2で指定した Azure app リソースの名前が**twitterconnector**の場合は、にhttps://twitterconnector.scm.azurewebsites.net/ZipDeployUi移動します。

6. 手順1でダウンロードした SampleConnector をドラッグアンドドロップして、このページに移動します。 ファイルがアップロードされ、展開が正常に完了すると、ページは次のスクリーンショットのようになります。

   ![](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a>手順 5: Twitter アプリを作成する

1. にhttps://developer.twitter.com移動して、組織の開発者アカウントの資格情報を使用してログインし、[**アプリ**] をクリックします。

   ![TCimage25-5](media/TCimage25-5.png)
2. [**アプリの作成**] をクリックします。
   
   ![](media/TCimage26.png)

3. [**アプリの詳細**] で、アプリケーションに関する情報を追加します。

   ![](media/TCimage27.png)

4. Twitter 開発者ダッシュボードで、作成したばかりのアプリを選択し、表示されたアプリ ID をコピーして、テキストファイルまたはその他の保存場所に保存します。 [**詳細**] をクリックします。
   
   ![](media/TCimage28.png)

5. [**キーとトークン**] タブの [**コンシューマー api キー** ] で、api シークレットキーをコピーして、テキストファイルまたは他の保存場所に保存します。 次に、[**作成**] をクリックしてアクセストークンとアクセストークンシークレットを生成し、それをテキストファイルまたは他の保存場所にコピーします。
   
   ![](media/TCimage29.png)

   次に、[**作成**] をクリックしてアクセストークンとアクセストークンシークレットを生成し、それをテキストファイルまたは他の保存場所にコピーします。

6. [**アクセス許可**] タブをクリックし、次のスクリーンショットに示されているようにアクセス許可を構成します。

   ![](media/TCimage30.png)

7. アクセス許可の設定を保存した後、[**アプリの詳細**] タブをクリックし、[編集] をクリックして [**詳細の編集 >** します。

   ![](media/TCimage31.png)

8. 次のタスクを実行します。

   –コネクタアプリが Twitter にサインインできるようにするには、チェックボックスをオンにします。
   
   –次の形式を使用して OAuth リダイレクト Uri を追加します: ** \<コネクタ>/views/twitteroauth**。この場合は、*コネクタサービス uri*の値が組織の Azure app service URL になります。たとえば、 https://twitterconnector.azurewebsites.net/Views/TwitterOAuthのようになります。

   ![](media/TCimage32.png)

Twitter 開発者アプリを使用する準備ができました。

## <a name="step-6-configure-the-connector-web-app"></a>手順 6: コネクタ web アプリを構成する 

1. Https://\<AzureAppResourceName> に移動します (ここで、 **AzureAppResourceName**は、手順4で名前を付けた Azure app リソースの名前です)。 たとえば、名前が**twitterconnector**の場合は、にhttps://twitterconnector.azurewebsites.net移動します。 アプリのホームページは、次のスクリーンショットのようになります。

   ![](media/FBCimage41.png)

2. [**構成**] をクリックして、サインインページを表示します。

   ![](media/FBCimage42.png)

3. [テナント Id] ボックスに、テナント Id を入力するか貼り付けます (手順2で取得したもの)。 [パスワード] ボックスに、APISecretKey (手順2で取得した) を入力するか貼り付け、[**構成設定の設定**] をクリックして**構成の詳細**ページを表示します。

   ![](media/TCimage35.png)

4. [**構成の詳細**] で、次の構成設定を入力します。 

   - **Twitter Api キー** –手順5で作成した twitter アプリケーションのアプリ ID。
   - **Twitter Api シークレットキー** –手順5で作成した twitter アプリケーションの api シークレットキー。
   – **Twitter アクセストークン**–手順5で作成したアクセストークン。
   – **Twitter アクセストークンシークレット**–手順5で作成したアクセストークンシークレット。
   – **Aad APPLICATION id** –「手順2– **aad application Secret** 」で作成した Azure Active DIRECTORY アプリのアプリケーション id –手順4で作成した APISecretKey シークレットの値。
   – **Aad アプリケーション uri** –手順2で取得した Aad アプリケーション uri。たとえば、 https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213のようになります。
   – **App Insights Instrumentation キー** –このボックスは空白のままにします。

5. [**保存**] をクリックしてコネクタの設定を保存します。

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a>手順 7: セキュリティ/コンプライアンスセンターでカスタムコネクタをセットアップする

1.  に移動<https://protection.office.com>して、[**データ\>ガバナンス\> ] [サードパーティデータのインポート**] をクリックします。

    ![](media/TCimage36.png)

2. [**コネクタの追加**] をクリックし、[ **Twitter**] をクリックします。

   ![](media/TCimage37.png)

3. [**コネクタアプリの追加**] ページで、次の情報を入力し、[**コネクタの検証**] をクリックします。

    -最初のボックスに、 **Twitter**などのコネクタの名前を入力します。
    -2 番目のボックスに、手順4で追加した APISecretKey の値を入力するか貼り付けます。
    –3番目のボックスに、Azure app service の URL を入力するか、貼り付けます。たとえば、 **https://twitterconnector.azurewebsites.net**のようになります。

   コネクタの検証が正常に完了したら、[**次へ**] をクリックします。

   ![](media/TCimage38.png)

4. [**コネクタアプリを使用してログイン] を**クリックします。

   ![](media/TCimage39.png)

5. APISecretKey をもう一度入力するか貼り付け、[**コネクタサービスにログイン] を**クリックします。

   ![](media/TCimage40.png)


6. [ **Twitter で続行] を**クリックします。

7. [Twitter サインイン] ページで、組織の Twitter アカウントのアカウントの資格情報を使用してサインインします。

   ![](media/TCimage42.png)

   サインインした後、Twitter ページに次のメッセージが表示されます。 "Twitter Connector ジョブは正常にセットアップされました。"

8. [**完了**] をクリックして、Twitter connector の設定を完了します。

9. [**フィルターの設定**] ページでは、特定の年齢のアイテムをインポート (およびアーカイブ) するためのフィルターを適用できます。 **[次へ]** をクリックします。

   ![](media/TCimage44.png)

10. [**ストレージアカウントの設定**] ページで、Twitter アイテムがインポートされる Office 365 メールボックスの電子メールアドレスを入力します。

    ![](media/TCimage45.png)

11. 設定を確認し、[**完了**] をクリックして、セキュリティ & コンプライアンスセンターでコネクタの設定を完了します。

    ![](media/TCimage46.png)

    ![](media/TCimage47.png)

12. [**サードパーティのデータをアーカイブ**する] ページに移動して、インポートプロセスの進行状況を表示します。

    ![](media/TCimage48.png)
