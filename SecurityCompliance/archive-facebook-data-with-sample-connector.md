---
title: サンプルコネクタを使用して Office 365 で Facebook データをアーカイブする (プレビュー)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理者は、ネイティブコネクタをセットアップして、Facebook のビジネスページ、Twitter、LinkedIn 会社のページ、インスタント Bloomberg などのデータソースからサードパーティのデータをインポートできます。 これにより、Office 365 でサードパーティのデータソースのデータをアーカイブできるため、組織のサードパーティデータのガバナンスを管理するために、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用できます。
ms.openlocfilehash: 33972d6d3124841a4cd2636c3d7756ec55f5cfa9
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852611"
---
# <a name="use-a-sample-connector-to-archive-facebook-data-in-office-365-preview"></a>サンプルコネクタを使用して Office 365 で Facebook データをアーカイブする (プレビュー)

Office 365 で Facebook データをアーカイブするためのサンプルコネクタ機能は、プレビュー段階にあります。

Office 365 のセキュリティ & コンプライアンスセンターのサンプルコネクタを使用して、Facebook のビジネスページ、LinkedIn、Twitter、Instant Bloomberg などのサードパーティのデータソースのデータをインポートおよびアーカイブします。 サンプルコネクタをセットアップして構成すると、そのコネクタはサードパーティのデータソースに接続し (スケジュールに従って)、アイテムのコンテンツを電子メールメッセージの形式に変換してから、それらのアイテムを Office 365 のメールボックスにインポートします。

サードパーティのデータがインポートされた後、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、監督、Office 365 アイテム保持ポリシーなどの Office 365 コンプライアンス機能をサードパーティのデータに適用することができます。 たとえば、メールボックスが訴訟ホールドの対象となっている場合、またはアイテム保持ポリシーに割り当てられている場合、サードパーティのデータは保持されます。 高度な電子情報開示ケースでは、コンテンツ検索を使用してサードパーティのデータを検索したり、保管担当者に関連付けることができます。 サンプルコネクタを使用して Office 365 でサードパーティのデータをインポートおよびアーカイブすることにより、組織は政府ポリシーおよび規制ポリシーに準拠し続けることができます。

> [!NOTE]
> 現時点では、Facebook のビジネスページと[Twitter](archive-twitter-data-with-sample-connector.md)のサンプルコネクタのみをプレビューに使用できます。 その他のサンプルコネクタは近日中に公開されます。


## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Facebook ビジネスページ用のコネクタを設定するための前提条件

セキュリティ & コンプライアンスセンターでサンプルコネクタを設定および構成するには、次の前提条件を満たしている必要があります。これにより、組織の Facebook ビジネスページからデータをインポートしてアーカイブすることができます。 

- 組織のビジネスページ用の Facebook アカウントが必要です (コネクタを設定するときに、このアカウントにサインインする必要があります)。 現時点では、Facebook のビジネスページのデータのみをアーカイブできます。個別の Facebook プロファイルからデータをアーカイブすることはできません。

- 組織が有効な Azure サブスクリプションを持っている必要があります。 既存の Azure サブスクリプションがない場合は、次のオプションのいずれかにサインアップできます。

    – [1 年間の無料の Azure サブスクリプションにサインアップする](https://azure.microsoft.com/free) 

    –[お客いただく Azure サブスクリプションへのサインアップ](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Office 365 サブスクリプションに含まれている[無料の Azure Active Directory サブスクリプション](use-your-free-azure-ad-subscription-in-office-365.md)は、セキュリティ & コンプライアンスセンターのサンプルコネクタをサポートしていません。

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この要求に同意するには、[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Office 365 グローバル管理者の資格情報でサインインし、要求を承諾します。

- セキュリティ & コンプライアンス (手順 7) でカスタムコネクタをセットアップするユーザーに、Exchange Online のメールボックスのインポートのエクスポート役割を割り当てる必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、新しい役割グループを作成し、メールボックスインポートエクスポートの役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「[役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)」または「[役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)」のセクションを参照してください。

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a>手順 1: Github から事前に作成されたコネクタアプリパッケージをダウンロードする

最初の手順として、facebook API を使用して facebook のビジネスページに接続し、Facebook データを抽出して Office 365 にインポートできるようにする、事前に作成された Facebook コネクタアプリのソースコードをダウンロードします。

1. [この GitHub サイト](https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases)に移動します。 
2. 最新のリリースで、 **SampleConnector**ファイルをクリックします。
3. ZIP ファイルをローカルコンピューターの場所に保存します。 手順4で、この zip ファイルを Azure にアップロードします。

## <a name="step-2-create-an-app-in-azure-active-directory"></a>手順 2: Azure Active Directory でアプリを作成する

次の手順では、Azure Active Directory (AAD) に新しいアプリを登録します。 このアプリは、手順4で Facebook コネクタ用に実装した web app リソースに対応しています。 

詳細な手順については、「 [Azure Active Directory でアプリを作成](deploy-facebook-connector.md#step-2-create-an-app-in-azure-active-directory)する」を参照してください。

この手順が完了すると (手順に従って)、次の情報がテキストファイルに保存されます。 これらの値は、展開プロセスの後の手順で使用します。

- AAD アプリケーション ID
- AAD アプリケーションシークレット
- AAD アプリケーション Uri
- テナント Id

## <a name="step-3-create-an-azure-storage-account"></a>手順 3: Azure storage アカウントを作成する

組織用に展開する Facebook コネクタは、Facebook ビジネスページから、この手順で作成した Azure ストレージの場所にアイテムをアップロードします。 セキュリティ & コンプライアンスセンター (手順 7) でカスタムコネクタを作成した後、Office 365 インポートサービスは、Azure ストレージの場所から Office 365 のメールボックスに Facebook データをコピーします。 前述の「[前提条件](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages)」セクションで説明したように、azure storage アカウントを作成するには、有効な azure サブスクリプションを用意する必要があります。

詳細な手順については、「 [Azure storage アカウントを作成する](deploy-facebook-connector.md#step-3-create-an-azure-storage-account)」を参照してください。

この手順が完了したら (手順に従って)、生成された接続文字列 Uri を保存します。 この文字列は、手順4で Azure で web app リソースを作成するときに使用します。

## <a name="step-4-create-a-web-app-resource-in-azure"></a>手順 4: Azure で web app リソースを作成する

次の手順では、Facebook コネクタ用に Azure で web app リソースを作成します。 

詳細な手順については、「 [Create a new web app resource In Azure](deploy-facebook-connector.md#step-4-create-a-new-web-app-resource-in-azure)」を参照してください。

この手順が完了すると (手順に従って)、次の情報が提供されます (前の手順を完了した後、テキストファイルにコピーしたもの) web app リソースを作成します。

- APISecretKey —この手順の完了時にこのシークレットを作成します。手順7で使用されます。
- StorageAccountConnectionString –手順3で Azure storage アカウントを作成した後にコピーした接続文字列 Uri。
- tenantId –手順2で Azure Active Directory で Facebook connector アプリを作成した後にコピーした Office 365 組織のテナント ID。

さらに、この手順の手順1でダウンロードした SampleConnector ファイルをアップロードして、Facebook connector アプリのソースコードを展開します。

この手順を完了したら、app Service の URL (例:) https://fbconnector.azurewebsites.net)をコピーしてください。 手順5、手順6、手順7を完了するには、これを使用する必要があります。

## <a name="step-5-register-the-web-app-on-facebook"></a>手順 5: Facebook で web アプリを登録する

次の手順では、Facebook で新しいアプリを作成して構成します。 手順7で作成したカスタムコネクタは、facebook web アプリを使用して、組織の Facebook ビジネスページからデータを取得する Facebook API と対話します。

詳細な手順については、「 [Facebook アプリを登録する](deploy-facebook-connector.md#step-5-register-the-facebook-app)」を参照してください。

この手順が完了したら (手順に従って)、次の情報をテキストファイルに保存します。 この値は、手順6で Facebook connector アプリを構成するために使用されます。

- Facebook アプリケーション ID
- Facebook アプリケーションシークレット
- Facebook webhook でトークンを確認する

## <a name="step-6-configure-the-facebook-connector-app"></a>手順 6: Facebook connector アプリを構成する

次の手順では、手順4で Azure web app リソースの作成時にアップロードした Facebook connector アプリに構成設定を追加します。 これを行うには、コネクタアプリのホームページにアクセスして構成します。

詳細な手順については、「 [step 6: Configure the connector web app](deploy-facebook-connector.md#step-6-configure-the-connector-web-app)」を参照してください。

この手順が完了すると (手順に従って)、次の情報が提供されます (前の手順を完了した後、テキストファイルにコピーしたことになります)。

- Facebook アプリケーション ID (手順5で取得)
- Facebook アプリケーションシークレット (手順5で取得)
- Facebook webhook でトークンを確認する (手順5で取得)
- Azure Active Directory アプリケーション ID (手順2で取得した AAD アプリケーション ID)
- Azure Active Directory アプリケーションシークレット (手順2で取得した AAD アプリケーションシークレット)
- Azure Active Directory アプリケーション Uri (手順2で取得した AAD アプリケーション Uri、たとえば、https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>手順 7: セキュリティ & コンプライアンスセンターでカスタムコネクタをセットアップする

最後の手順として、セキュリティ & コンプライアンスセンターでカスタムコネクタを設定して、Facebook ビジネスページから Office 365 の指定したメールボックスにデータをインポートします。 この手順を完了すると、Office 365 インポートサービスは、Facebook のビジネスページから Office 365 にデータをインポートするプロセスを開始します。 

詳細な手順については、「[セキュリティ & コンプライアンスセンターでカスタムコネクタを設定する](deploy-facebook-connector.md#step-7-set-up-a-custom-connector-in-the-security--compliance-center)」を参照してください。 

この手順が完了すると (手順に従って)、次の情報が提供されます (手順を完了した後、テキストファイルにコピーしたことになります)。

- Azure app service の URL (手順4で取得)。たとえば、https://fbconnector.azurewebsites.net)
- APISecretKey (手順4で作成したもの)
