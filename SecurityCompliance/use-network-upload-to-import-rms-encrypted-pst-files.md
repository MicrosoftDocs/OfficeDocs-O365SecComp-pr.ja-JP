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
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a>ネットワーク アップロードを使用して、RMS で暗号化された PST ファイルを Office 365 にインポートする

**この資料では、管理者用です。自分のメールボックスを PST ファイルをインポートしようとしていますか。[インポート電子メール、連絡先、および Outlook の .pst ファイルから予定表](https://go.microsoft.com/fwlink/p/?LinkID=785075)を参照してください。**
   
ネットワークの使用は、PST ファイルをユーザーのメールボックスにインポートするには、オプションと Office 365 のインポート サービスにアップロードします。ネットワークのアップロードでは、マイクロソフトのクラウド内の一時記憶領域、PST ファイルをアップロードすることを意味します。Office 365 のインポート サービスは、ターゲット ユーザーのメールボックスにストレージ領域から PST ファイルをコピーします。インポート サービスの新機能では、アップロード、およびマイクロソフトのクラウドに格納されている前に、PST ファイルを暗号化することができます。ユーザーのメールボックスにインポートすると、これらのファイルは暗号化を解除できません。 
  
暗号化し、Office 365 のメールボックスを PST ファイルをインポートするための手順を以下に示します。
  
[手順 1:PST インポートの Azure Rights Management をセットアップする ](#step-1-set-up-azure-rights-management-for-pst-import)

[手順 2:PST インポートの暗号化キーを生成する](#step-2-generate-an-encryption-key-for-pst-import)

[手順 3: RMS のテナント ID とライセンスの URL を取得します。](#step-3-obtain-rms-tenant-id-and-licensing-url)

[手順 4: PST インポート ツールをダウンロードして、SAS の URL をコピー](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[手順 5: の暗号化し、PST ファイルを Office 365 にアップロードします。](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[(省略可能)手順 6: Office 365 のビュー PST ファイルのアップロード](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[PST インポート マッピング ファイルを作成する手順 7。](#step-7-create-the-pst-import-mapping-file)

[手順 8:Office 365 で PST インポート ジョブを作成する](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> 設定し、組織を構成する手順 4 を 1 回だけを暗号化し、Office 365 のメールボックスを PST ファイルをインポートする手順 1 を実行する必要があります。次の手順を実行した後は、暗号化、アップロード、および複数の PST ファイルをインポートするたびを手順 8 から手順 5 に従います。 
  
Office 365 へのデータのインポートの詳細については、 [Office 365 の組織の PST ファイルのインポートの概要](importing-pst-files-to-office-365.md)を参照してください。
  
## <a name="before-you-begin"></a>はじめに

- メールボックスのエクスポートをインポートの役割を割り当てるには、Exchange オンライン Office 365 のメールボックスを PST ファイルをインポートするのにはする必要があります。既定では、この役割はありませんに割り当てられている役割グループは、Exchange オンライン。組織の管理役割グループに、メールボックスのインポート エクスポートの役割を追加できます。または、新しい役割グループを作成、メールボックスのインポート エクスポートの役割を割り当てるし、ユーザー自身をメンバーとして追加します。詳細については、追加するロール グループのロール」を参照してください。 または、「作成」の役割グループの[役割グループの管理](https://go.microsoft.com/fwlink/p/?LinkId=730688)のセクションです。
    
    Office 365 のセキュリティのジョブのインポートを作成するのにはさらに、&amp;コンプライアンス センターは、次のいずれかを満たす必要があります。
    
  - メール受信者の役割を割り当てるには、Exchange オンラインする必要があります。既定では、この役割は組織の管理と受信者の管理役割グループに割り当てられます。
    
    または
    
  - Office 365 の組織のグローバル管理者があります。
    
  > [!TIP]
  > Exchange Online の具体的には、Office 365 に PST ファイルをインポートする新しい役割グループを作成することを検討してください。PST ファイルをインポートするのには必要な特権を最低限のレベルで、新しい役割グループにメールボックスのエクスポートをインポートし、メール受信者の役割を割り当てるし、メンバーを追加します。 
  
- ファイル サーバーまたは共有のフォルダー、組織内で Office 365 にインポートする PST ファイルを保存する必要があります。ステップ 5 で、暗号化され、このファイル サーバーに格納されるか、Office 365 にフォルダーを共有する PST ファイルをアップロード、Office 365 の ImportTool を実行します。
    
- この手順ではコピーして、暗号化キー、ストレージ ・ キー、および多数の識別キーと Url のコピーを保存します。この情報は、暗号化し、PST ファイルをアップロードする手順 5 で使用されます。パスワードやその他のセキュリティに関連する情報を保護するようにこれらだけを保護する対策を講じていることを確認します。たとえば、パスワードで保護された Microsoft Word 文書に保存または暗号化された USB ドライブに保存します。これらのキー、Id、および Url の例の[詳細について](#more-information)はを参照してください。 
    
- PST ファイルをインポートするには Office 365 の非アクティブなメールボックスにします。内の非アクティブなメールボックスの GUID を指定することによってこれを行う、 `Mailbox` PST インポート マッピング ファイル内のパラメーターです。詳細については、[手順 7](#step-7-create-the-pst-import-mapping-file)を参照してください。 
    
- Exchange ハイブリッド展開の場合は、[プライマリ メールボックスは、オンプレミス ユーザーのクラウド ベースのアーカイブ メールボックスに PST ファイルをインポートできます。PST インポート マッピング ファイルで次の操作を行います。
    
  - ユーザーのオンプレミスのメールボックスの電子メール アドレスを指定します`Mailbox`パラメーター。 
    
  - **真**の値を指定します`IsArchive`パラメーター。 
    
    詳細については、[手順 7](#step-7-create-the-pst-import-mapping-file)を参照してください。 
    
- PST ファイルが Office 365 のメールボックスにインポートされると、メールボックスの設定の保存は不定の期間のになっています。つまり、メールボックスに割り当てられているリテンション ・ ポリシーは、の保持を無効にするか、保留リストを無効にする日付を設定するまで処理されません。なぜこのような処理でしょうか。メールボックスにインポートするメッセージが古い場合は、それら可能性が完全に削除 (パージ)、メールボックスに対して構成されている保存期間の設定に基づいて、保存期間が期限切れになった。保存保留中のメールボックスを配置することと、これらの新しくインポートされたメッセージまたはメールボックスの保存期間の設定を変更するのには、時間を提供を管理するためにメールボックス所有者の時間が提供されます。保存保留リストの管理に関する推奨事項の[詳細について](#more-information)はを参照してください。 
    
- Office 365 にアップロードする前に、PST ファイルを暗号化する必要はない場合、は、 [Office 365 に PST ファイルをインポートするのにはアップロードの使用のネットワーク](use-network-upload-to-import-pst-files.md)を参照してください。
    
- Office 365 に PST ファイルをインポートするのには、ネットワークのアップロードを使用してについてよく寄せられる質問は、 [Office 365 に PST ファイルのインポートについての FAQ](faqimporting-pst-files-to-office-365.md)を参照してください。
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a>手順 1:PST インポートの Azure Rights Management をセットアップする 

PST インポートでは、Office 365 の Azure アクセス権管理 (Azure RMS) サービスによって提供される暗号化機能を使用します。これにより、Office 365 にアップロードする前に PST ファイルを暗号化することができます。 
  
PST インポートの Azure の RMS の構成は、3 つの手順で構成されます。
  
- [Azure の RMS をアクティブにします。](#activate-azure-rms)
    
- [RMS を構成する Exchange オンライン](#configure-rms-in-exchange-online)
    
- [Active Directory の RMS クライアントをインストールします。](#install-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a>Azure の RMS をアクティブにします。

Azure の RMS は、既定で無効にしますが、するか、組織内の別の管理者がありますがアクティブになって。インストールし、Azure の DRM を有効にする[Azure アクセス権の管理をアクティブにする](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)の指示に従って操作します。
  
### <a name="configuring-rms-in-exchange-online"></a>RMS を構成する Exchange オンライン

権限管理サービスをアクティブにした後、次に、Exchange Azure の RMS を使用するオンラインでの情報権利管理 (IRM) を設定するのには。詳細については、 [Azure の権利管理を使用する IRM を構成する](https://go.microsoft.com/fwlink/p/?LinkId=394816)を参照してください。
  
1. [リモート PowerShell を使用して Exchange Online に接続](https://go.microsoft.com/fwlink/p/?LinkId=396554 )します。
    
2. 次のコマンドを実行して、RMS キー共有 URL を設定する。
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    組織の場所の正しい RMS キー共有場所を決定するには、次の表を使用します。
    
    |**場所**|**RMS キー共有場所**|
    |:-----|:-----|
    |北アメリカ  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |欧州連合  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |アジア  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |南アメリカ  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |行政機関向け Office 365 (行政機関のコミュニティ クラウド)  <br/> | `https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup> <br/> |
   
    > [!NOTE]
    > <sup>1</sup>政府の Sku (政府コミュニティ クラウド) に Office 365 が購入されたお客様のみがこの RMS キーの場所の共有を使用してください。 
  
    たとえば、このコマンドは、共有の場所に Exchange オンライン北アメリカにある顧客の RMS のオンライン キーを構成します。
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. RMS オンラインから Office 365 の組織に、信頼された発行ドメイン (TPD) をインポートするのには次のコマンドを実行します。 
    
    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    TPD には、PST ファイルの暗号化など、組織で RMS 機能を使用するために必要な設定が含まれています。  
    
4. Office 365 組織で IRM を有効にするのには、次のコマンドを実行します。
    
    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a>Active Directory の RMS クライアントをインストールします。

このセクションの最後のステップでは、権限管理サービス (RMS) クライアント 2.1 をダウンロードします。このソフトウェアでは、Azure の RMS へのアクセスを保護するのに役立ち、情報を暗号化し、手順 5 で PST ファイルをアップロードするに使用する同じコンピューターに RM クライアントを Azure 利用のインストールを使用するアプリケーションからフローを保護します。 
  
1. [権限管理サービス クライアント 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396)をダウンロードしてください。
    
2. Active Directory Rights Management サービス クライアント 2.1 ウィザードを実行して、クライアントをインストールする。

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a>手順 2:PST インポートの暗号化キーを生成する

Azure の RMS を設定した後、次の手順では、Office 365 にアップロードする PST ファイルを暗号化するために使用される暗号化キー (対称キーと呼ばれます) を生成します。Azure Active Directory の主要サービスとして PST インポート サービスを追加することによってこれを行うでしょう。サービス主体が PST インポート サービスにアップロードすると、Azure Active Directory と直接認証を許可するようにこのアプリケーションを追加すると、手順 5 で Azure ストレージの場所に PST ファイルが暗号化されます。
  
1. Windows PowerShell の Azure Active Directory のモジュールを起動します。
    
2. 次のコマンドを実行して、Microsoft Online サービスに接続する。
    
    ```
    Connect-MsolService
    ```

3. Office 365 組織の管理者アカウントの資格情報を入力し、し、[ **OK**] をクリックします。
    
4. 次のコマンドを実行して、暗号化キー (対称キーと呼ばれる) を生成する。これを行うには、新しい PST 暗号化プリンシパルを作成します。
    
    ```
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    システムには、新しい PST 暗号化プリンシパルの対称キーとプロパティが表示されます。
    
    ![表示されている対称キーをコピーして保存する](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. 対称キーをテキスト ファイルまたは Word ファイルにコピーする。前述したように、必ずこのファイルを保護する予防策を講じてください。対称キーが表示されるのはこの時だけであるため、このウィンドウのスクリーンショットを撮り、同じファイルに保存することも検討してください。  
    
    > [!IMPORTANT]
    > PST 暗号化プリンシパルの作成後は、**Get-MsolServicePrincipal** コマンドレットを使用して対称キーを取得することはできなくなります。このためキーを保存することが重要になります。 
  
開いたままで、Azure Active Directory モジュールを Windows PowerShell の Microsoft オンライン サービスに接続されています。次の手順では、このウィンドウでコマンドを実行します。

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a>手順 3: RMS のテナント ID とライセンスの URL を取得します。

次の手順では、ID と、組織の RMS の Azure サービスのライセンスの場所の URL は、テナントを取得します。コピーし、手順 2 から対称キーが格納されている同じファイルにこの情報を保存します。ID と URL は、PST ファイルを暗号化する手順 5 で使用されます。
  
1. モジュールでは、Azure Active ディレクトリ (Microsoft オンライン サービスに接続されている)、Windows PowerShell の組織の Office 365 の Azure の RMS サービスに接続する次のコマンドを実行します。
    
    ```
    Connect-AadrmService 
    ```

2. 組織の Office 365 の管理者アカウントの資格情報を入力し、し、[ **OK**] をクリックします。
    
3. Office 365 の組織で、Azure の RMS サービスのテナント ID を表示する次のコマンドを実行します。
    
    ```
    Get-AadrmConfiguration | FL BPOSId
    ```

    値をコピーして、`BPOSId`プロパティ。 
    
4. Azure の RMS サービスのライセンスの場所を表示するのには次のコマンドを実行します。
    
    ```
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    値をコピーして、`LicensingIntranetDistributionPointUrl`プロパティ。 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a>手順 4: PST インポート ツールをダウンロードして、SAS の URL をコピー

Azure の RMS を構成し、PST ファイルを暗号化するために必要な Id を取得した、次に、ダウンロードして Office 365 を暗号化する手順 5 で実行して、ファイルのアップロードの PST のツールをインストールします。これらのツールは、Azure AzCopy ツールと Office 365 のデータの暗号化ツールです。組織の SA の URL をコピーすることもあります。この URL は、組織と共有アクセス署名 (SAS) キーをマイクロソフトのクラウド内の Azure ストレージ場所のネットワークの URL の組み合わせです。このキーは、Azure のストレージ場所に PST ファイルをアップロードする必要なアクセス許可を提供します。ファイルに保存、同じステップ 2 とステップ 3 で、その他の情報をコピーしたことです。述べたように、SAS の URL を保護するために予防措置を講じます。 
  
> [!IMPORTANT]
> Azure ストレージの場所に PST ファイルを正常にアップロードするのには Azure AzCopy バージョン 5.0 を使用する必要があります。AzCopy ツールの新しいバージョンは、Office 365 に PST ファイルをインポートするためにサポートされていません。この手順の手順に従って、**ネットワーク経由でファイルのアップロード**ページから AzCopy ツールをダウンロードすることを確認します。 
  
1. [https://protection.office.com](https://protection.office.com)。
    
2. 組織の Office 365 の管理者アカウントの資格情報を使用して Office 365 にサインインします。
    
3. 左側のウィンドウでは、**データ ・ ガバナンス**をクリックし、し、[**インポート**] をクリックします。
    
4. **[インポート]** ページで、**[インポート サービスに移動する]** をクリックします。
    
5. **Office 365 へのデータのインポート**] ページで、[**新しいジョブ**] をクリックします![アイコンの追加](media/ITPro-EAC-AddIcon.gif)、**電子メール メッセージをアップロードする (PST ファイル)** をクリックします。
    
6. **ネットワーク経由でファイルのアップロード**ページで、手順 2 では、**ネットワーク アップロード SAS の URL を表示する**をクリックします。
    
7. URL が表示されたら、コピーし、他のキーを保存したファイルに保存します。URL 全体をコピーすることを確認します。 
    
8. 手順 3 で、 **Azure の AzCopy ツールをダウンロード**をダウンロードして、Azure の AzCopy ツールをインストールする] をクリックします。 
    
9. ポップアップ ウィンドウで、**[実行]** をクリックして、Azure AzCopy ツールをインストールします。 
    
    > [!IMPORTANT]
    > 既定の場所に、Azure の AzCopy ツールをインストールしてください`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`のコンピューターで 64 ビットの Windows を実行しています。この場所で AzCopy ツールを探す手順 5 で、O365ImportTool.exe を実行するとためにです。 
  
10. Azure AzCopy ツールをインストールした後、 **Office 365 のデータの暗号化およびインポート ツールのダウンロード**をクリックします。
    
11. ポップアップ ウィンドウで、[**保存**] をクリックします\>**として保存する**に O365ImportTool.zip ファイルをローカル コンピューター上のフォルダーに保存します。 
    
12. O365ImportTool.zip ファイルを抽出する。
    
13. **ネットワーク経由でファイルのアップロード**] ページを閉じます**キャンセル**をクリックします。 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a>手順 5: の暗号化し、PST ファイルを Office 365 にアップロードします。

手順 4 から手順 1 が完了したら後、は、O365ImportTool.exe ツールを使用して暗号化して、Office 365 に PST ファイルをアップロードする準備が整ったら。このツールは、PST ファイルを暗号化しアップロードし、マイクロソフトのクラウドでは、Azure ストレージの場所に保存します。この手順を完了するには、PST ファイルをファイル共有や、組織内のファイル サーバーに配置する必要があります。これは、次の手順でソース ディレクトリと呼ばれます。O365ImportTool.exe ツールを実行するたびができるディレクトリを指定する別のソース。 
  
1. ローカル コンピューター上でコマンド プロンプトを開く。
    
2. 手順 4 で O365ImportTool.exe ツールをインストールしたディレクトリに移動する。
    
3. 暗号化し、Office 365 に PST ファイルをアップロードするには、次のコマンドを実行します。
    
    ```
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    次の表は、パラメーターとそれに必要な値を説明したものです。前の手順で取得した情報は、これらのパラメーターの値で使うことに注意してください。
    
    |**パラメーター**|**説明**|**例**|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |Office 365 にアップロードする PST ファイルを含む、組織内には、ソース ディレクトリを指定します。  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |Azure の RMS サービスのライセンスの場所を指定します。値を使用して、`LicensingIntranetDistributionPointUrl`の手順 3 で取得したプロパティです。二重引用符では、このパラメーターの値を囲むことを確認する ("")<br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |Azure の RMS の組織の id を指定します。値を使用して、`BPOSId`の手順 3 で取得したプロパティです。<br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |手順 2 で取得した対称キーを指定します。二重引用符では、このパラメーターの値を囲むことを確認する ("")。  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |PST ファイルをネットワーク経由でアップロードまたは、ハード ドライブに付属しているかどうかを指定します。値`upload`、ネットワーク経由でファイルをアップロードすることを示します。値`drive`ハード ドライブ上の pst ファイルを配布することを示します。<br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |PST ファイルのアップロードをするには Office 365 の宛先を指定します。これは、組織の Azure ストレージの場所です。このパラメーターの値は、手順 4 でコピーした SAS の URL から、ネットワークのアップロード URL で構成されています。二重引用符では、このパラメーターの値を囲むことを確認する ("")。<br/><br/> **ヒント:**(省略可能)暗号化された PST ファイルをアップロードするのには Azure ストレージの場所にサブフォルダーを指定することができます。("Ingestiondata") の後にサブフォルダーの場所を追加するネットワークのアップロード URL でこれを行います。最初の例は、サブフォルダーを指定しません。つまり、pst ファイルには、Azure ストレージの場所の ( *ingestiondata*という名前) のルートにアップロードされます。2 番目の例では、Azure ストレージの場所に PST ファイルのフォルダー ( *EncryptedPSTs* ) をアップロードします。           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> または  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |組織の SA のキーを指定します。このパラメーターの値は、手順 4 でコピーした SAS の URL から SA のキーで構成されます。SA のキーの最初の文字が疑問符 () であることを確認 ("?")。二重引用符では、このパラメーターの値を囲むことを確認する ("")。  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |このオプション スイッチは、O365ImportTool.exe ツールがで指定されたソース ディレクトリ内のサブフォルダーにある Pst ファイルをコピーするために再帰的なモードを指定します`/srcdir:`パラメーター。  <br/><br/> **注:** このスイッチを含める場合は、PST ファイルのサブフォルダーには、アップロードした Azure ストレージの場所に別のファイルのパス名があります。手順 7 で作成した CSV ファイルの正確なファイルのパス名を指定する必要があります。           | `/recurse` <br/> |
   
    各パラメーターの実際の値を使用する O365ImportTool.exe ツールの構文の例を以下に示します。
    
    ```
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    コマンドを実行すると、PST ファイルの暗号化とアップロードの進行状況を示す状態メッセージが表示されます。最終の状態メッセージは、暗号化とアップロードが正常に完了したファイルの合計数を示しています。  
    
    > [!TIP]
    > 正常に O365ImportTool.exe コマンドを実行してすべてのパラメーターが正しいことを確認するものと同じ情報をコピーする (セキュリティで保護された) ファイルをコマンド ・ ライン構文のコピーを保存で取得した前の手順を実行します。できますをコピーし、貼り付けコマンド プロンプトでこのコマンドを暗号化し、Office 365 に PST ファイルをアップロードするには、O365ImportTool.exe ツールを実行するたびにします。ものは、値のみを変更する必要があります、`/srcdir:`と`/upload-dest:`のパラメーターです。 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>(省略可能)手順 6: Office 365 のビュー PST ファイルのアップロード

オプションの手順としてインストールし、Azure blob にアップロードしている PST ファイルの一覧を表示するのには、Azure ストレージ エクスプ ローラーは、無料のオープン ソースのツール) を使用できます。これを行う 3 つの理由があります。
  
- PST ファイルを共有フォルダーまたは組織内のファイル サーバーからが、Azure blob を正常にアップロードされたことを確認します。

- PST ファイルが暗号化されていることを確認します。暗号化された PST ファイルが、 `.pfile` 、PST ファイル名に追加した拡張子たとえば、 `pilarp.pst.pfile`。
    
- Azure blob にアップロードされた各 PST ファイルのファイル名 (および 1 つ含まれている場合、サブフォルダーのパス名) を確認します。各 PST ファイルのファイル名とフォルダーのパス名を指定する必要があるために、次の手順でファイルをマッピングする pst ファイルを作成するときに非常に便利です。これらの名前を確認すると、PST のマッピング ・ ファイル内の潜在的なエラーを削減できます。
    
プレビューでは、Microsoft Azure ストレージ エクスプ ローラーです。 
  
 > [!IMPORTANT]
>  アップロードまたは PST ファイルを変更するには、Azure ストレージ エクスプ ローラーを使うことはできません。Office 365 に PST ファイルをインポートするための唯一のサポートされている方法では、AzCopy を使用します。また、Azure blob にアップロードしている PST ファイルを削除できません。PST ファイルを削除しようとすると、必要な権限がないというエラー メッセージが表示されます。Azure ストレージ領域からすべての PST ファイルを自動的に削除するに注意してください。ある場合、すべて PST ファイルの**ingestiondata**コンテナーには、進行中のインポート ジョブは削除されません、最新のインポート ジョブを作成した後 30 日間。 
  
Azure ストレージ エクスプ ローラーをインストールし、Azure のストレージ領域への接続します。
  
1. ダウンロードして、 [Microsoft Azure ストレージ エクスプ ローラー ツール](https://go.microsoft.com/fwlink/p/?LinkId=544842)をインストールします。
    
2. Microsoft Azure ストレージ エクスプ ローラーを起動左側のウィンドウで、**ストレージ アカウント**を右クリックし、 **Azure ストレージへの接続**] をクリックします。 
    
    ![ストレージ アカウントを右クリックし、Azure ストレージに接続] をクリックし、](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. [ **Azure ストレージに接続する]** ボックスで、手順 4 で取得した SAS の URL を貼り付けるし、[**次へ**] をクリックします。 
    
    ![Azure ストレージのページへの接続] ボックスに、SAS の URL を貼り付ける](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. [**接続の概要**] ページで、接続情報を確認し、[**接続**] をクリックできます。 
    
5. [**ストレージ アカウント**] でノードを展開します **(サービスの SAS)** と**Blob コンテナー**ノードを展開します。 
    
6. **Ingestiondata**を右クリックし、 **Blob コンテナー エディターを開く**] をクリックします。
    
    ![ingestiondata を右クリックし、[Blob コンテナー エディターを開く] をクリックする](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    Azure ストレージ領域、手順 5 でアップロードしている PST ファイルの一覧が表示されます。
    
    ![Azure ストレージ エクスプローラーには、アップロードした PST ファイルの一覧が表示される](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. Microsoft Azure ストレージ エクスプ ローラーの使用が終了したら、 **ingestiondata**を右クリックし、Azure のストレージ領域から切断するのには**接続解除**] をクリックします。それ以外の場合、次に接続しようとするとき、エラーが表示されます。 
    
    ![ingestion を右クリックして [デタッチ] をクリックし、Azure のストレージ エリアから切断する](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a>PST インポート マッピング ファイルを作成する手順 7。

PST ファイルは、暗号化され、組織の Office 365 の Azure ストレージの場所にアップロードされたが後、次に、PST ファイルはインポートできません、ユーザーのメールボックスを指定する値 (CSV) ファイルを区切るコンマを作成します。PST インポート ジョブを作成するときは、次の手順では、この CSV ファイルが送信されます。
  
1. [PST インポート マッピング ・ ファイルのコピーをダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=544717)します。 
    
2. CSV ファイルを開くか、ローカル コンピューターに保存します。次の例は、完了した PST インポートのマッピング ファイル (メモ帳で開いた) を示しています。Microsoft Excel を使って CSV ファイルを編集するほうが、はるかに簡単です。
    
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

    最初の行、または CSV ファイルのヘッダー行は、PST ファイルをユーザーのメールボックスにインポートする PST インポート サービスによって使用されるパラメーターを一覧表示します。各パラメーター名は、コンマで区切られます。ヘッダー行の下の各行は、特定のメールボックスを PST ファイルをインポートするためのパラメーター値を表します。行は、各ユーザーのメールボックスにインポートする PST ファイルの必要があります。マッピング ファイル内のプレース ホルダーのデータを実際のデータに置き換えることを確認します。
    
    > [!NOTE]
    > SharePoint パラメーターなど、ヘッダー行は何も変更しないでください。これらは PST インポートの処理中、無視されます。 
  
3. 次の表の情報を使って、必要な情報を含む CSV ファイルを作成します。
    
    |**パラメーター**|**説明**|**例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Office 365 サービスにインポートするデータを指定します。PST ファイルをユーザーのメールボックスにインポートするを使用して、 `Exchange`。<br/> | `Exchange` <br/> |
    | `FilePath` <br/> |手順 5 で PST ファイルをアップロードした Azure ストレージの場所にフォルダーの場所を指定します。  <br/>  ネットワークの URL を任意のサブフォルダーの名前が含まれていないかどうか、`/upload-dest:`パラメーターでは、手順 5 では、空白のままにこのパラメーターで CSV ファイルです。サブフォルダー名を入力した場合、このパラメーターに値を指定します。このパラメーターの値は、大文字小文字を区別します。*どちらにしてがの値に"ingestiondata"を含まない*、`FilePath`のパラメーターです。<br/> <br/>**重要な:** ファイルのパス名の大文字と小文字に SAS の URL を任意のサブフォルダーの名前が含まれている場合に使用した同じ大文字と小文字にする必要があります、`/upload-dest:`手順 5 でのパラメーターです。使用した場合など、 `EncryptedPSTs` 、サブフォルダー名を手順 5 で、使用して`encryptedpsts`で、 `FilePath` CSV ファイル内のパラメーター、PST ファイルのインポートは失敗します。両方のインスタンスで、同じ大文字と小文字を使用することを確認します。           |(空白)  <br/> または  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |ユーザーのメールボックスにインポートする PST ファイルの名前を指定します。このパラメーターの値は、大文字小文字を区別します。Azure ストレージの場所にアップロードされた PST ファイルが暗号化されているため、 `.pfile` PST ファイル名に拡張子が追加されます。追加する必要があります、 `.pfile` pst ファイルの名前に拡張子のファイルを CSV ファイルにします。<br/><br/> **重要な:** CSV ファイル内の PST ファイル名の大文字と小文字は、手順 5 で Azure ストレージの場所にアップロードされた PST ファイルと同じである必要があります。使用する場合など、`annb.pst.pfile`で、 `Name` 、CSV ファイルが実際の PST ファイルの名前のパラメーターは、 `AnnB.pst`、その PST ファイルのインポートは失敗します。CSV ファイルに pst ファイルの名前が実際の PST ファイルと同じ大文字と小文字を使用することを確認します。           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |PST ファイルのインポート先になるメールボックスのメール アドレスを指定します。   <br/> 非アクティブなメールボックスに PST ファイルをインポートするのにはこのパラメーターにメールボックスの GUID を指定する必要です。この GUID を取得するには、Exchange Online で次の PowerShell コマンドを実行します: ' Get メールボックス InactiveMailboxOnly。<identity of inactive mailbox> | FL Guid` <br/><br/> **Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-メールボックス -<identity of active mailbox> | FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get ・ メールボックス ・ <identity of soft-deleted or inactive mailbox> ・ SoftDeletedMailbox | FL Guid'           | `annb@contoso.onmicrosoft.com` <br/> または  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | PST ファイルをユーザーのアーカイブ メールボックスにインポートするかどうかを指定します。次のような 2 つの選択肢があります。<br/> **FALSE**PST ファイルをユーザーのプライマリ メールボックスにインポートします。  <br/> **場合は TRUE。** PST ファイルをユーザーのアーカイブ メールボックスにインポートします。  <br/>  このパラメーターを空白のままにすると、PST ファイルは、ユーザーのプライマリ メールボックスにインポートされます。  <br/><br/> **注:** クラウド ベースのアーカイブ メールボックスがプライマリ メールボックスは、オンプレミス ユーザーの PST ファイルをインポートするにだけこのパラメーターに**TRUE**を指定しのユーザーのオンプレミスのメールボックスの電子メール アドレスを指定します`Mailbox`パラメーター。           | `FALSE` <br/> または  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | PST ファイルをインポートするメールボックス フォルダーを指定します。  <br/>  このパラメーターを空白のままにする場合は、**インポート済み**の名前付きの ([受信トレイ] フォルダーおよびその他の既定のメールボックス フォルダーと同じレベル) のメールボックスのルート レベルに新しいフォルダーを pst ファイルがインポートされます。  <br/>  指定する場合は、 `/`、PST ファイル内の項目をユーザーの受信トレイ フォルダーに直接インポートされます。  <br/>  指定する場合は、 `/<foldername>`、という名前のサブフォルダーをインポートする PST ファイルのアイテム*\<フォルダー名\>*。使用した場合など、 `/ImportedPst`、 **ImportedPst**をという名前のサブフォルダーにアイテムをインポートするとします。このサブフォルダーは、ユーザーの受信トレイ フォルダーに配置されます。<br/><br/> **ヒント:** Pst ファイルをインポートするのには最適なフォルダーの場所を特定できるように、このパラメーターを実験するのには、いくつかのテスト バッチを実行することを検討してください。           |(空白)  <br/> または  <br/>  `/` <br/> または  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |この省略可能なパラメーターでは、ANSI のファイル形式の PST ファイルのインポートに使用するコード ページの数値を指定します。これらの言語が文字をエンコードするための 2 バイト文字セット (DBCS) を通常使用されるため、中国語、日本語、韓国語 (CJK) の組織から PST ファイルをインポートするため、このパラメーターが使用されます。メールボックス フォルダーの名前に DBCS を使用する言語の PST ファイルをインポートするのにはこのパラメーターを使用していない場合は、フォルダー名を多くの場合文字化けする、インポートした後。このパラメーターを使用するのにはサポートされている値のリストは、[コード ページの識別子](https://go.microsoft.com/fwlink/p/?LinkId=328514)を参照してください。<br/><br/> **注:** 前に述べたように、これは、オプションのパラメーターと、CSV ファイルに含めるようにする必要はありません。または追加して値を 1 つまたは複数の行の空白のままにします。           |(空白)  <br/> または  <br/>  `932`(日本語版 ANSI と OEM のコード ページの id です)  <br/> |
    | `SPFileContainer` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。   <br/> |該当なし  <br/> |
    | `SPManifestContainer` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。   <br/> |該当なし  <br/> |
    | `SPSiteUrl` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。   <br/> |該当なし  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a>手順 8:Office 365 で PST インポート ジョブを作成する

最後のステップでは、Office 365 のサービスのインポートの PST のインポート ジョブを作成します。手順 7 で作成した PST インポート マッピング ファイルを提出する前に説明したようです。インポート サービスが、解除するようマッピング ファイルの情報を使用して新しいジョブを作成した後に暗号化し、PST ファイル (手順 5 で Office 365 にアップロードした場合) を指定したユーザーのメールボックスにインポートします。 
  
1. [https://protection.office.com](https://protection.office.com)。
    
2. 組織の Office 365 の管理者アカウントの資格情報を使用して Office 365 にサインインします。
    
3. 左側のウィンドウでは、**データ ・ ガバナンス**をクリックし、し、[**インポート**] をクリックします。
    
4. **[インポート]** ページで、**[インポート サービスに移動する]** をクリックします。
    
5. **Office 365 へのデータのインポート**] ページで、[**新しいジョブ**] をクリックします![アイコンの追加](media/ITPro-EAC-AddIcon.gif)、**電子メール メッセージをアップロードする (PST ファイル)** をクリックします。
    
6. **[ネットワーク経由でファイルをアップロードする]** ページで、**[ファイルのアップロードが完了しました]** と **[マッピング ファイルにアクセスできます]** の各チェック ボックスを選択して、**[次へ]** をクリックします。  
    
7. PST インポート ジョブの名前を入力し、**[次へ]** をクリックします。
    
8. [**追加**] をクリックして![アイコンの追加](media/ITPro-EAC-AddIcon.gif)手順 7 で作成したマッピングの PST ファイルを選択します。 
    
9. CSV ファイルの名前が一覧に表示されたら、CSV ファイルを選択して **[検証]** をクリックし、CSV ファイルにエラーがないか確認します。  
    
    > [!NOTE]
    > 前に説明すると、PST ファイルが暗号化されている場合、 `.pfile` PST ファイル名に拡張子が追加されます。追加する必要があります、 `.pfile` pst ファイルの名前に拡張子のファイルを CSV ファイルにします。ない場合は、CSV ファイルの検証に失敗します。 
  
    PST インポート ジョブを作成するには、CSV ファイルが正常に検証される必要があります。検証が失敗した場合は、**[状態]** 列の **[無効]** リンクをクリックします。PST インポートのマッピング ファイルのコピーが開き、失敗したファイル内の各行ごとにエラー メッセージが表示されます。 
    
10. PST のマッピング ファイルが正常に検証されたら、ご契約条件を読み、チェック ボックスをオンにします。
    
11. **[完了]** をクリックして、ジョブを送信します。 
    
    ジョブは、 **Office 365 へのデータのインポート**] ページで、PST のインポート ジョブの一覧に表示されます。 
    
12. ジョブを選択し、[**更新**] をクリックして![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif)詳細ペインに表示されるステータス情報を更新します。 
    
13. 詳細ウィンドウで、**[詳細の表示]** をクリックして、選択したジョブの最新の状態を取得します。 
 
## <a name="more-information"></a>詳細情報

- 理由 PST ファイルを Office 365 にインポートしますか。
    
  - 組織の電子メールを Office 365 に移行する良い方法です。
    
  - 次のことが可能になるので、組織のコンプライアンスのニーズに対応するのに役立ちます。
    
  - アーカイブ メールボックスを有効にして、追加のメールボックス容量をユーザーに提供する。
    
  - メールボックスを保持状態にして、コンテンツを保持する。
    
  - Microsoft 電子情報開示ツールを使って、メールボックスのコンテンツを検索する。
    
  - アイテム保持ポリシーを使って、メールボックスのコンテンツの保持期間を制御する。
    
  - Office 365 の監査ログ メールボックスに関連するイベントを検索します。
    
  - データの損失に対する保護に役立ちます。Office 365 のメールボックスにインポートする PST ファイルは、ユーザーのコンピューターにデータを格納するのではなく、オンラインの Exchange の高可用性機能を継承します。
    
  - データがクラウドに格納されるので、ユーザーはあらゆるデバイスからデータを利用できます。
    
- ここでは、キー、Id、および 2、3、および 4 の手順で取得した Url の例です。この例では、暗号化するために O365ImportTool.exe ツールを実行して、アップロードの PST ファイルを Office 365 にするコマンドの構文も含まれています。パスワードやその他のセキュリティに関連する情報を保護するようにこれらだけを保護する対策を講じていることを確認します。
    
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

- 説明したよう Office 365 のインポート サービスをオンに設定 (不定の期間) のメールボックスを PST ファイルをインポートした後に保持します。つまり、 *RentionHoldEnabled*プロパティに設定されて`True`メールボックスに割り当てられているリテンション ・ ポリシーを処理しないようにします。これには、削除したり、古いメッセージをアーカイブするアーカイブ ポリシーの削除を防止することで、新しくインポートされたメッセージを管理するためにメールボックス所有者の時間が与えられます。この保持を管理するためのいくつかの手順を以下に示します。 
    
  - 後、一定時間、オフにできます、保存を実行して、`Set-Mailbox -RetentionHoldEnabled $false`コマンドです。手順については、[保存上のメールボックスの場所を保持](https://go.microsoft.com/fwlink/p/?LinkId=544749)を参照してください。
    
  - 無効になって、将来的にいくつかの日付にするため、保持を構成できます。これを実行するのには、`Set-Mailbox -EndDateForRetentionHold <date>`コマンドです。たとえば、今日の日付は 2016 年 7 月 1 日、30 日以内にオフに保持する、ことを前提としては、次のコマンドを実行、: `Set-Mailbox -EndDateForRetentionHold 8/1/2016`。このシナリオでは、 *RentionHoldEnabled*プロパティに設定のままに`True`。詳細については、[一連のメールボックス](https://go.microsoft.com/fwlink/p/?LinkId=150317)を参照してください。
    
  - できるように、すぐに削除またはユーザーのアーカイブ メールボックスに移動しないインポートされた古いアイテムは、メールボックスに割り当てられているリテンション ・ ポリシーの設定を変更することができます。たとえば、削除またはアーカイブ メールボックスに割り当てられているポリシーの保有期間を長く可能性があります。このシナリオでは無効にするメールボックスに保持リテンション ・ ポリシーの設定を変更した後。詳細については、 [Office 365 の組織内のメールボックスのアーカイブと削除ポリシーの設定](set-up-an-archive-and-deletion-policy-for-mailboxes.md)を参照してください。
