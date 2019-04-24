---
title: ネットワーク アップロードを使用して、RMS で暗号化された PST ファイルを Office 365 にインポートする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: ネットワークアップロードを使用して、RMS で暗号化された PST ファイルを Office 365 のユーザーメールボックスにインポートする方法について説明します。
ms.openlocfilehash: 46f77f3fe173da23e08284884bb85c69ab53f710
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263701"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a>ネットワーク アップロードを使用して、RMS で暗号化された PST ファイルを Office 365 にインポートする

**この記事は、管理者を対象としています。PST ファイルを自分のメールボックスにインポートしようとしていますか?「 [Outlook .pst ファイルからメール、連絡先、予定表をインポートする](https://go.microsoft.com/fwlink/p/?LinkID=785075)」を参照してください。**
   
ユーザーのメールボックスに PST ファイルをインポートするには、ネットワークアップロードオプションと Office 365 インポートサービスを使用します。 ネットワークのアップロードとは、PST ファイルを Microsoft クラウドの一時的なストレージ領域としてアップロードすることを意味します。 その後、Office 365 インポートサービスは、PST ファイルをストレージ領域からターゲットユーザーのメールボックスにコピーします。 インポートサービスの新機能により、PST ファイルを暗号化して Microsoft クラウドに保存することができます。 これらのファイルは、ユーザー メールボックスへのインポート時には暗号化されません。 
  
PST ファイルを暗号化して Office 365 メールボックスにインポートするために必要な手順は次のとおりです。
  
[手順 1: PST インポートの Azure Rights Management をセットアップする](#step-1-set-up-azure-rights-management-for-pst-import)

[手順 2:PST インポートの暗号化キーを生成する](#step-2-generate-an-encryption-key-for-pst-import)

[手順 3: RMS テナント ID とライセンス URL を取得する](#step-3-obtain-rms-tenant-id-and-licensing-url)

[手順 4: PST インポートツールをダウンロードして、SAS URL をコピーする](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[手順 5: PST ファイルを暗号化して Office 365 にアップロードする](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[オプション手順 6: Office 365 にアップロードされた PST ファイルの一覧を表示する](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[手順 7: PST インポートのマッピングファイルを作成する](#step-7-create-the-pst-import-mapping-file)

[手順 8:Office 365 で PST インポート ジョブを作成する](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> PST ファイルを暗号化して Office 365 メールボックスにインポートするように組織を設定および構成するには、手順 1 ~ 4 を一度だけ実行する必要があります。 これらの手順を実行した後、PST ファイルのバッチを暗号化、アップロード、およびインポートするたびに、手順5から手順8に従います。 
  
office 365 へのデータのインポートの詳細については、「[組織の PST ファイルを office 365 にインポートする」の概要](importing-pst-files-to-office-365.md)を参照してください。
  
## <a name="before-you-begin"></a>始める前に

- PST ファイルを Office 365 メールボックスにインポートするには、Exchange Online でメールボックスのインポートのエクスポートの役割を割り当てられている必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. 詳細については、「 [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688)」の「役割グループに役割を追加する」または「役割グループを作成する」のセクションを参照してください。
    
    さらに、Security & コンプライアンスセンターでインポートジョブを作成するには、次のいずれかの条件を満たしている必要があります。
    
  - Exchange Online では、メール受信者の役割が割り当てられている必要があります。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    または
    
  - Office 365 組織の全体管理者である必要があります。
    
  > [!TIP]
  > Office 365 に PST ファイルをインポートするための特別な目的である Exchange Online に新しい役割グループを作成することを検討してください。 PST ファイルのインポートに必要な最低限の特権レベルについては、メールボックスのインポートの役割とメール受信者の役割を新しい役割グループに割り当ててから、メンバーを追加します。 
  
- Office 365 にインポートする PST ファイルは、組織内のファイルサーバーまたは共有フォルダーに格納する必要があります。 手順5では、office 365 importtool を実行して、このファイルサーバーまたは共有フォルダーに保存されている PST ファイルを office 365 に暗号化してアップロードします。
    
- この手順では、暗号化キー、ストレージ キー、および多数の識別キーと URL のコピーをコピーして保存します。 この情報は、手順5で PST ファイルを暗号化してアップロードするために使用されます。 パスワードやその他のセキュリティ関連情報を保護するのと同じように、これらのファイルを保護するための予防策を必ず講じてください。 たとえば、パスワードで保護された Microsoft Word 文書に保存する、または暗号化された USB ドライブに保存することができます。 これらのキー、ID、および URL の例については、「[詳細情報](#more-information)」セクションを参照してください。 
    
- Office 365 の非アクティブなメールボックスに PST ファイルをインポートすることができます。 これを行うには、PST インポートマッピングファイルの`Mailbox`パラメーターに非アクティブなメールボックスの GUID を指定します。 詳細については、[手順 7](#step-7-create-the-pst-import-mapping-file)を参照してください。 
    
- Exchange ハイブリッド展開では、プライマリメールボックスがオンプレミスであるユーザーのクラウドベースのアーカイブメールボックスに PST ファイルをインポートできます。 これを行うには、PST インポートマッピングファイルで以下の手順を実行します。
    
  - `Mailbox`パラメーターに、ユーザーの社内メールボックスの電子メールアドレスを指定します。 
    
  - `IsArchive`パラメーターに**TRUE**の値を指定します。 
    
    詳細については、[手順 7](#step-7-create-the-pst-import-mapping-file)を参照してください。 
    
- PST ファイルが Office 365 メールボックスにインポートされると、メールボックスの保持ホールドの設定は無期限に有効になります。 これは、メールボックスに割り当てられたアイテム保持ポリシーは、保存機能を無効にするか、保留を解除する日付を設定するまで処理されないことを意味します。 なぜこれを行うのでしょうか。 メールボックスにインポートされたメッセージが古くなっている場合は、メールボックスに対して構成されたアイテム保持ポリシーに基づいて保持期間が経過したために、削除 (パージ) される可能性があります。 メールボックスの保存機能を有効にすると、メールボックスの所有者は新しくインポートされたメッセージを管理することができ、メールボックスの保存期間の設定を変更する時間を与えることができます。 保持ホールドの管理に関する提案については、「 [More information](#more-information) 」セクションを参照してください。 
    
- office 365 にアップロードする前に pst ファイルを暗号化する必要がない場合は、「[ネットワークアップロードを使用して pst ファイルを office 365 にインポート](use-network-upload-to-import-pst-files.md)する」を参照してください。
    
- ネットワークアップロードを使用して pst ファイルを office 365 にインポートする方法についてよく寄せられる質問については、「 [office 365 への pst ファイルのインポートに関する FAQ](faqimporting-pst-files-to-office-365.md)」を参照してください。
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a>手順 1:PST インポートの Azure Rights Management をセットアップする 

PST インポートでは、Office 365 の azure Rights Management (azure RMS) サービスが提供する暗号化機能を使用します。 これにより、Office 365 にアップロードする前に PST ファイルを暗号化することができます。 
  
PST インポート用に Azure RMS を構成するには、3つの手順から構成されます。
  
- [Azure RMS をアクティブ化する](#activating-azure-rms)
    
- [Exchange Online で RMS を構成する](#configuring-rms-in-exchange-online)
    
- [Active Directory RMS クライアントのインストール](#installing-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a>Azure RMS をアクティブ化する

Azure RMS は既定で無効になっていますが、組織内の別の管理者がライセンス認証を行った可能性があります。 [azure Rights Management をアクティブ化](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)して azure DRM をインストールしてアクティブ化する手順に従います。
  
### <a name="configuring-rms-in-exchange-online"></a>Exchange Online で RMS を構成する

Rights management サービスをアクティブ化した後、次の手順では、Azure RMS を使用するために Exchange Online で Information Rights Management (IRM) をセットアップします。 詳細については、「 [Azure Rights Management を使用するように IRM を構成する](https://go.microsoft.com/fwlink/p/?LinkId=394816)」を参照してください。
  
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
    |地域  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |南アメリカ  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |行政機関向け Office 365 (行政機関のコミュニティ クラウド)  <br/> | `https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1-d</sup> <br/> |
   
    > [!NOTE]
    > <sup>1</sup> Office 365 for government sku (government Community Cloud) を購入したお客様のみ、この RMS キー共有場所を使用する必要があります。 
  
    たとえば、次のコマンドを実行すると、北米に配置されている顧客に対して Exchange online の RMS online キー共有場所が構成されます。
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. 次のコマンドを実行して、信頼された発行ドメイン (TPD) を RMS Online から Office 365 組織にインポートします。 
    
    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    TPD には、PST ファイルの暗号化など、組織で RMS 機能を使用するために必要な設定が含まれています。  
    
4. 次のコマンドを実行して、Office 365 組織の IRM を有効にします。
    
    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a>Active Directory RMS クライアントのインストール

このセクションの最後の手順で、Rights Management サービス (RMS) クライアント 2.1 をダウンロードします。 このソフトウェアは、azure rms へのアクセスを保護し、azure rms を使用するアプリケーションを経由する情報を保護するのに役に立ちます。 手順5で PST ファイルの暗号化とアップロードに使用するのと同じコンピューターに RMS クライアントをインストールします。 
  
1. [Rights Management サービスクライアント 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396)をダウンロードします。
    
2. Active Directory Rights Management サービス クライアント 2.1 ウィザードを実行して、クライアントをインストールする。

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a>手順 2:PST インポートの暗号化キーを生成する

Azure RMS をセットアップしたら、次の手順として、Office 365 にアップロードする PST ファイルを暗号化するために使用される暗号化キー (対称キーと呼ばれる) を生成します。 これを行うには、Azure Active Directory のサービスプリンシパルとして PST インポートサービスを追加します。 このアプリケーションをサービスプリンシパルとして追加すると、手順5で pst ファイルを暗号化して azure ストレージの場所にアップロードするときに、pst インポートサービスが azure Active Directory を直接認証できるようになります。
  
1. Windows PowerShell の Azure Active Directory モジュールを開始します。
    
2. 次のコマンドを実行して、Microsoft Online サービスに接続する。
    
    ```
    Connect-MsolService
    ```

3. Office 365 組織の管理者アカウントの資格情報を入力し、[ **OK]** をクリックします。
    
4. 次のコマンドを実行して、暗号化キー (対称キーと呼ばれる) を生成する。 これを行うには、新しい PST 暗号化プリンシパルを作成します。
    
    ```
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    システムには、新しい PST 暗号化プリンシパルの対称キーとプロパティが表示されます。
    
    ![表示されている対称キーをコピーして保存する](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. 対称キーをテキスト ファイルまたは Word ファイルにコピーする。前述したように、必ずこのファイルを保護する予防策を講じてください。対称キーが表示されるのはこの時だけであるため、このウィンドウのスクリーンショットを撮り、同じファイルに保存することも検討してください。  
    
    > [!IMPORTANT]
    > PST 暗号化プリンシパルの作成後は、**Get-MsolServicePrincipal** コマンドレットを使用して対称キーを取得することはできなくなります。 このためキーを保存することが重要になります。 
  
Windows PowerShell 用 Azure Active Directory モジュールを開いたままにして、Microsoft Online サービスに接続します。 次の手順では、このウィンドウでコマンドを実行します。

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a>手順 3: RMS テナント ID とライセンス URL を取得する

次の手順では、組織の Azure RMS サービスのテナント ID とライセンスの場所の URL を取得します。 手順 2 の対称キーが保存されている同じファイルに、この情報をコピーして保存します。 ID と URL は、手順5で PST ファイルを暗号化するために使用されます。
  
1. (Microsoft Online service に接続されている) Windows PowerShell 用 azure Active Directory モジュールで、次のコマンドを実行して Office 365 組織の azure RMS サービスに接続します。
    
    ```
    Connect-AadrmService 
    ```

2. Office 365 組織の管理者アカウントの資格情報を入力し、[ **OK]** をクリックします。
    
3. Office 365 組織の Azure RMS サービスのテナント ID を表示するには、次のコマンドを実行します。
    
    ```
    Get-AadrmConfiguration | FL BPOSId
    ```

    `BPOSId`プロパティの値をコピーして保存します。 
    
4. Azure RMS サービスのライセンスの場所を表示するには、次のコマンドを実行します。
    
    ```
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    `LicensingIntranetDistributionPointUrl`プロパティの値をコピーして保存します。 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a>手順 4: PST インポートツールをダウンロードして、SAS URL をコピーする

Azure RMS を構成し、pst ファイルを暗号化するために必要な id を取得したので、次の手順では、手順5で実行するツールをダウンロードしてインストールし、pst ファイルを暗号化して Office 365 にアップロードします。 これらのツールは、Azure azcopy ツールおよび Office 365 データ暗号化ツールです。 組織の SAS URL もコピーします。 この url は、組織のための Microsoft クラウド内の Azure ストレージの場所のネットワーク URL と、共有アクセス署名 (SAS) キーの組み合わせです。 このキーは、Azure ストレージの場所に PST ファイルをアップロードするために必要なアクセス許可を提供します。 手順2と手順3で、他の情報をコピーしたのと同じファイルに保存します。 前述したように、SAS URL を保護するための予防措置を講じます。 
  
> [!IMPORTANT]
> azure のストレージの場所に PST ファイルを正常にアップロードするには、azure azcopy バージョン5.0 を使用する必要があります。 新しいバージョンの azcopy ツールは、Office 365 に PST ファイルをインポートするためにサポートされていません。 この手順の手順に従って、[**ネットワーク経由でファイルをアップロード**する] ページから azcopy ツールをダウンロードしてください。 
  
1. [https://protection.office.com](https://protection.office.com) に移動します。
    
2. office 365 組織の管理者アカウントの資格情報を使用して、office 365 にサインインします。
    
3. 左側のウィンドウで、[**データガバナンス**] をクリックし、[**インポート**] をクリックします。
    
4. **[インポート]** ページで、**[インポート サービスに移動します]** をクリックする。
    
5. [ **Office へのデータのインポート 365** ] ページで、[**新しいジョブ** ![の追加] アイコン](media/ITPro-EAC-AddIcon.gif)をクリックし、[**電子メールメッセージ (PST ファイル) のアップロード**] をクリックします。
    
6. [**ネットワーク経由でファイルをアップロード**する] ページの手順2で、[**ネットワークアップロード SAS URL を表示する**] をクリックします。
    
7. URL が表示されたら、それをコピーして、他のキーを保存したファイルに保存します。 必ず URL 全体をコピーする。 
    
8. 手順3で、[ **azure azcopy ツールのダウンロード**] をクリックして、azure azcopy ツールをダウンロードしてインストールします。 
    
9. ポップアップ ウィンドウで、**[実行]** をクリックして、Azure AzCopy ツールをインストールする。 
    
    > [!IMPORTANT]
    > 必ず、64ビットの Windows を実行しているコンピューター `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`上の、既定の場所に Azure azcopy ツールをインストールしてください。 これは、手順5で o365importtool.zip を実行したときに、この場所で azcopy ツールを検索するためです。 
  
10. Azure azcopy ツールをインストールした後、[ **Office 365 データ暗号化およびインポートツールをダウンロード**する] をクリックします。
    
11. ポップアップウィンドウで、[名前を付け**** \> **て**保存] をクリックして、o365importtool.zip ファイルをローカルコンピューター上のフォルダーに保存します。 
    
12. O365ImportTool.zip ファイルを抽出する。
    
13. [**キャンセル**] をクリックして、[**ネットワーク経由でファイルをアップロード**する] ページを閉じます。 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a>手順 5: PST ファイルを暗号化して Office 365 にアップロードする

手順 1 ~ 手順4を完了したら、o365importtool.zip ツールを使用して、PST ファイルを暗号化して Office 365 にアップロードすることができます。 このツールは、PST ファイルを暗号化してから、Microsoft クラウド内の Azure ストレージの場所にアップロードして保存します。 この手順を完了するには、PST ファイルを組織内のファイル共有またはファイル サーバーに配置する必要があります。 これは、次の手順でソース ディレクトリと呼ばれます。 O365ImportTool.exe ツールを実行するたびに、異なるソース ディレクトリを指定することができます。 
  
1. ローカル コンピューター上でコマンド プロンプトを開く。
    
2. 手順 4 で O365ImportTool.exe ツールをインストールしたディレクトリに移動する。
    
3. 次のコマンドを実行して、PST ファイルを暗号化して Office 365 にアップロードします。
    
    ```
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    次の表は、パラメーターとそれに必要な値を説明したものです。前の手順で取得した情報は、これらのパラメーターの値で使用されることに注意してください。
    
    |**パラメーター**|**説明**|**例**|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |Office 365 にアップロードされる PST ファイルを含む、組織内のソースディレクトリを指定します。  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |Azure RMS サービスのライセンスの場所を指定します。 手順3で取得し`LicensingIntranetDistributionPointUrl`たプロパティの値を使用します。 このパラメーターの値は二重引用符 ("") で囲むようにしてください。  <br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |Azure RMS 組織の id を指定します。 手順3で取得し`BPOSId`たプロパティの値を使用します。  <br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |手順 2 で取得した対称キーを指定します。 このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |PST ファイルをネットワーク経由でアップロードするか、またはハード ドライブで送付するかを指定します。 この値`upload`は、ネットワーク経由でファイルをアップロードしていることを示します。 この値`drive`は、ハードドライブに pst を配布することを示します。  <br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |PST ファイルのアップロード先となる Office 365 の送信先を指定します。これは、組織の Azure ストレージの場所です。 このパラメーターの値は、手順4でコピーした SAS url からのネットワークアップロード URL で構成されます。 このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/><br/> **ヒント:** オプション暗号化された PST ファイルをアップロードするために、Azure ストレージの場所にサブフォルダーを指定することができます。 これを行うには、ネットワークアップロード URL にサブフォルダーの場所 ("ingestiondata" の後) を追加します。 最初の例では、サブフォルダーを指定しません。これは、pst が Azure ストレージの場所のルート ( *ingestiondata*という名前) にアップロードされることを意味します。 2番目の例では、PST ファイルを Azure ストレージの場所のサブフォルダー ( *encryptedpsts*という名前) にアップロードします。           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> または  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |組織の SAS キーを指定します。 このパラメーターの値は、手順4でコピーした sas URL の sas キーで構成されます。 SAS キーの最初の文字が疑問符 ("?") であることに注意してください。 このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |このオプションスイッチは、o365importtool.zip ツールが、 `/srcdir:`パラメーターで指定されたソースディレクトリ内のサブフォルダーにある pst ファイルをコピーするように、再帰モードを指定します。  <br/><br/> **注:** このスイッチを含めると、サブフォルダー内の PST ファイルは、アップロード後に、Azure ストレージの場所に別のファイルパス名を持つことになります。 手順 7 で作成した CSV ファイルの正確なファイルのパス名を指定する必要があります。           | `/recurse` <br/> |
   
    各パラメーターの実際の値を使用する O365ImportTool.exe ツールの構文の例を以下に示します。
    
    ```
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    コマンドを実行すると、PST ファイルの暗号化とアップロードの進行状況を示す状態メッセージが表示されます。最終の状態メッセージは、暗号化とアップロードが正常に完了したファイルの合計数を示しています。  
    
    > [!TIP]
    > O365ImportTool コマンドを正常に実行して、すべてのパラメーターが正しいことを確認した後、コマンド ライン構文のコピーを、前の手順で取得した情報をコピーしたファイルと同じ (セキュリティで保護された) ファイルに保存します。 次に、o365importtool.zip ツールを実行して PST ファイルを暗号化して Office 365 にアップロードするたびに、このコマンドをコマンドプロンプトにコピーして貼り付けることができます。 変更する必要があるのは、パラメーター `/srcdir:`と`/upload-dest:`パラメーターの値だけです。 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>オプション手順 6: Office 365 にアップロードされた PST ファイルの一覧を表示する

オプションの手順として、Microsoft azure ストレージエクスプローラー (無償のオープンソースツール) をインストールして使用し、azure blob にアップロードした PST ファイルの一覧を表示することができます。 これを行うには、次の3つの適切な理由があります。
  
- 組織内の共有フォルダーまたはファイルサーバーの PST ファイルが Azure blob に正常にアップロードされたことを確認します。

- PST ファイルが暗号化されていることを確認します。 暗号化された pst `.pfile`ファイルには、pst ファイル名に拡張子が付いています。たとえば、 `pilarp.pst.pfile`のようになります。
    
- Azure blob にアップロードされた各 PST ファイルのファイル名 (およびサブフォルダーが含まれている場合はそのパス名) を確認します。 これは、次の手順で pst マッピングファイルを作成している場合に、各 pst ファイルのフォルダーパス名とファイル名の両方を指定する必要があるため、非常に役立ちます。 これらの名前を確認すると、PST マッピングファイルの潜在的なエラーを減らすのに役立ちます。
    
Microsoft Azure ストレージエクスプローラーはプレビュー段階です。 
  
 > [!IMPORTANT]
>  Azure ストレージエクスプローラーを使用して PST ファイルをアップロードまたは変更することはできません。 PST ファイルを Office 365 にインポートするためにサポートされている唯一の方法は、azcopy を使用することです。 また、Azure blob にアップロードした PST ファイルを削除することもできません。 PST ファイルを削除しようとすると、必要なアクセス許可がないというエラーが表示されます。 すべての PST ファイルが Azure ストレージ領域から自動的に削除されることに注意してください。 If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created. 
  
azure ストレージエクスプローラーをインストールして azure ストレージ領域に接続するには、次のようにします。
  
1. [Microsoft Azure ストレージエクスプローラーツール](https://go.microsoft.com/fwlink/p/?LinkId=544842)をダウンロードしてインストールします。
    
2. Microsoft Azure ストレージエクスプローラーを起動し、左側のウィンドウで [**ストレージアカウント**] を右クリックして、[ **Azure ストレージに接続] を**クリックします。 
    
    ![[ストレージアカウント] を右クリックし、[Azure ストレージへの接続] をクリックします。](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. [ **Azure ストレージへの接続**] のボックスで、手順4で取得した SAS URL を貼り付けて、[**次へ**] をクリックします。 
    
    ![[Azure Storage への接続] ページのボックスに、SAS URL を貼り付けます。](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. [**接続の概要**] ページで、接続情報を確認し、[**接続**] をクリックします。 
    
5. [**ストレージアカウント**] の下にある **(サービス SAS)** ノードを展開し、[ **Blob コンテナー** ] ノードを展開します。 
    
6. [ **ingestiondata**] を右クリックし、[ **Blob コンテナーエディターを開く**] をクリックします。
    
    ![ingestiondata を右クリックし、[Blob コンテナー エディターを開く] をクリックする](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    手順5でアップロードした PST ファイルの一覧を含む Azure ストレージ領域が表示されます。
    
    ![Azure ストレージ エクスプローラーには、アップロードした PST ファイルの一覧が表示される](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. Microsoft azure ストレージエクスプローラーの使用が終了したら、[ **ingestiondata**] を右クリックし、 **** [切断] をクリックして azure ストレージ領域から切断します。 そうしないと、次に接続しようとしたときにエラーが表示されます。 
    
    ![ingestion を右クリックして [デタッチ] をクリックし、Azure のストレージ エリアから切断する](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a>手順 7: PST インポートのマッピングファイルを作成する

pst ファイルが暗号化され、Office 365 組織の Azure ストレージの場所にアップロードされたら、次の手順では、pst ファイルをインポートするユーザーのメールボックスを指定するコンマ区切り値 (CSV) ファイルを作成します。 PST インポート ジョブを作成する場合は、次の手順でこの CSV ファイルを送信します。
  
1. [PST インポートのマッピングファイルのコピーをダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=544717)します。 
    
2. CSV ファイルを開くか、またはローカル コンピューターに保存します。次の例は、完了した PST インポートのマッピング ファイル (メモ帳で開いた) を示しています。Microsoft Excel を使用して CSV ファイルを編集するのは、はるかに簡単です。
    
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

    CSV ファイルの先頭行、またはヘッダー行には、PST インポート サービスによって使用され、PST ファイルをユーザー メールボックスにインポートするパラメーターが一覧表示されます。 パラメーター名とパラメーター名の間はコンマで区切られています。 ヘッダー行の下の各行は、特定のメールボックスに PST ファイルをインポートするためのパラメーター値を表します。 ユーザー メールボックスにインポートする PST ファイルごとに行が必要になります。 必ずマッピング ファイル内のプレースホルダーのデータを実際のデータに置き換えてください。
    
    > [!NOTE]
    > SharePoint パラメーターなど、ヘッダー行は何も変更しないでください。これらは PST インポートの処理中、無視されます。 
  
3. 次の表の情報を使用して、必要な情報を含む CSV ファイルを作成します。
    
    |**パラメーター**|**説明**|**例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |データのインポート先となる Office 365 サービスを指定します。 PST ファイルをユーザーのメールボックスにインポート`Exchange`するには、を使用します。  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |手順5で PST ファイルをアップロードした Azure ストレージの場所でのフォルダーの場所を指定します。  <br/>  手順5の`/upload-dest:`パラメーターに、ネットワーク URL にオプションのサブフォルダー名を含めなかった場合は、CSV ファイルでこのパラメーターを空白のままにしておきます。 サブフォルダー名を含める場合は、このパラメーターで指定します。 このパラメーターの値は、大文字と小文字を区別します。 どちらの方法** でも、 `FilePath`パラメーターの値に "ingestiondata" を含めないでください。  <br/> <br/>**重要:** ファイルパス名の大文字と小文字は、手順5で`/upload-dest:`パラメーターの SAS URL にオプションのサブフォルダ名を含めた場合に使用したものと同じである必要があります。 たとえば、手順5でサブ`EncryptedPSTs`フォルダー名を使用し、CSV ファイルの`encryptedpsts` `FilePath`パラメーターでを使用した場合、PST ファイルのインポートは失敗します。 両方のインスタンスで同じケースを使用してください。           |(空白)  <br/> または  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |ユーザー メールボックスにインポートする PST ファイルの名前を指定します。  このパラメーターの値は、大文字と小文字を区別します。 Azure ストレージの場所にアップロードされる pst ファイルは暗号化されるため、 `.pfile` pst ファイル名に拡張子が追加されます。 CSV ファイルの PST `.pfile`ファイルの名前に拡張機能を追加する必要があります。  <br/><br/> **重要:** CSV ファイルの pst ファイル名の大文字と小文字は、手順5で Azure ストレージの場所にアップロードされた pst ファイルと同じである必要があります。 たとえば、CSV ファイルの`annb.pst.pfile` `Name`パラメーターでを使用していて、実際の pst ファイルの名前が`AnnB.pst`である場合、その pst ファイルのインポートは失敗します。 CSV ファイルの pst の名前では、実際の pst ファイルと同じ大文字と小文字が使用されていることを確認してください。           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |PST ファイルのインポート先になるメールボックスの電子メール アドレスを指定します。   <br/> 非アクティブなメールボックスに PST ファイルをインポートするには、このパラメーターのメールボックス GUID を指定する必要があります。 この GUID を取得するには、Exchange Online で次の PowerShell コマンドを実行します。`Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL Guid` <br/><br/> **注:** 場合によっては、1つのメールボックスがアクティブなメールボックスであり、もう一方のメールボックスが削除済み (非アクティブ) 状態になっているメールボックスが同じメールアドレスを持つ複数のメールボックスが存在することがあります。 このような状況では、PST ファイルをインポートするメールボックスを一意に識別するメールボックス GUID を指定します。 この GUID をアクティブなメールボックスに対して取得するには`Get-Mailbox - <identity of active mailbox> | FL Guid`、次の PowerShell コマンドを実行します。 回復可能な削除 (または非アクティブ) のメールボックスの GUID を取得するには、次のコマンドを実行します。`Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`           | `annb@contoso.onmicrosoft.com` <br/> または  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | PST ファイルをユーザーのアーカイブ メールボックスにインポートするかどうかを指定します。 次のような 2 つの選択肢があります。  <br/> **FALSE**PST ファイルをユーザーのプライマリメールボックスにインポートします。  <br/> **TRUE**PST ファイルをユーザーのアーカイブメールボックスにインポートします。  <br/>  If you leave this parameter blank, the PST file is imported to the user's primary mailbox.  <br/><br/> **注:** プライマリメールボックスがオンプレミスであるユーザーのクラウドベースのアーカイブメールボックスに PST ファイルをインポートするには、このパラメーターに**TRUE**を指定し、 `Mailbox`パラメーターのユーザーの社内メールボックスの電子メールアドレスを指定するだけです。           | `FALSE` <br/> または  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | PST ファイルのインポート先メールボックスフォルダーを指定します。  <br/>  このパラメーターを空白のままにした場合、PST はメールボックスのルートレベル (受信トレイフォルダーとその他の既定のメールボックスフォルダーと同じレベル) にある**インポート**された新しいフォルダーにインポートされます。  <br/>  を指定`/`した場合、PST ファイル内のアイテムは、ユーザーの受信トレイフォルダーに直接インポートされます。  <br/>  を指定`/<foldername>`した場合、PST ファイルのアイテムは、 * \<foldername\> *という名前のサブフォルダーにインポートされます。 たとえば、を使用`/ImportedPst`した場合、アイテムは**ImportedPst**という名前のサブフォルダーにインポートされます。 このサブフォルダーは、ユーザーの受信トレイフォルダーに配置されます。  <br/><br/> **ヒント:** pst ファイルのインポートに最適なフォルダーの場所を決定できるように、いくつかのテストバッチを実行して、このパラメーターを試してみることをお勧めします。           |(空白)  <br/> または  <br/>  `/` <br/> または  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |このオプションパラメーターは、ANSI ファイル形式で PST ファイルをインポートするために使用するコードページの数値を指定します。 このパラメーターは、中国語、日本語、および韓国語 (CJK) の組織から PST ファイルをインポートするために使用されます。これらの言語では、通常、文字エンコードに2バイト文字セット (DBCS) を使用します。 メールボックスフォルダー名に DBCS を使用する言語の PST ファイルをインポートするためにこのパラメーターを使用していない場合は、インポート後にフォルダー名が正しくないことがよくあります。 このパラメーターに使用することがサポートされている値の一覧については、「[コードページ識別子](https://go.microsoft.com/fwlink/p/?LinkId=328514)」を参照してください。  <br/><br/> **注:** 前述したように、これはオプションのパラメーターであり、CSV ファイルに含める必要はありません。 または、1つまたは複数の行の値を空白のままにしておくこともできます。           |(空白)  <br/> または  <br/>  `932`(ANSI/OEM 日本語のコードページ識別子)  <br/> |
    | `SPFileContainer` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。   <br/> |該当なし  <br/> |
    | `SPManifestContainer` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。   <br/> |該当なし  <br/> |
    | `SPSiteUrl` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。   <br/> |該当なし  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a>手順 8:Office 365 で PST インポート ジョブを作成する

最後の手順では、Office 365 のインポートサービスで PST インポートジョブを作成します。 前述したように、手順 7 で作成した PST インポートのマッピング ファイルを送信します。 新しいジョブを作成した後、インポートサービスはマッピングファイル内の情報を使用して、(手順5で Office 365 にアップロードした) PST ファイルを暗号化解除してインポートし、指定されたユーザーメールボックスにインポートします。 
  
1. [https://protection.office.com](https://protection.office.com) に移動します。
    
2. office 365 組織の管理者アカウントの資格情報を使用して、office 365 にサインインします。
    
3. 左側のウィンドウで、[**データガバナンス**] をクリックし、[**インポート**] をクリックします。
    
4. **[インポート]** ページで、**[インポート サービスに移動します]** をクリックする。
    
5. [ **Office へのデータのインポート 365** ] ページで、[**新しいジョブ**![の追加] アイコン](media/ITPro-EAC-AddIcon.gif)をクリックし、[**電子メールメッセージ (PST ファイル) のアップロード**] をクリックします。
    
6. **[ネットワーク経由でファイルをアップロードする]** ページで、**[ファイルのアップロードが完了しました]** と **[マッピング ファイルにアクセスできます]** の各チェック ボックスを選択して、**[次へ]** をクリックします。  
    
7. PST インポート ジョブの名前を入力し、**[次へ]** をクリックする。
    
8. [追加] アイコン](media/ITPro-EAC-AddIcon.gif)をクリックして、手順7で作成した PST マッピングファイルを選択します。 **** ![ 
    
9. CSV ファイルの名前が一覧に表示されたら、**[検証]** をクリックして、CSV ファイルにエラーがないか確認する。  
    
    > [!NOTE]
    > 前述したように、pst ファイルが暗号化され`.pfile`ている場合は、pst ファイル名に拡張子が追加されます。 CSV ファイルの PST `.pfile`ファイルの名前に拡張機能を追加する必要があります。 追加しないと、CSV ファイルの検証が失敗します。 
  
    PST インポート ジョブを作成するには、CSV ファイルが正常に検証される必要があります。検証が失敗した場合は、**[状態]** 列の **[無効]** リンクをクリックします。PST インポートのマッピング ファイルのコピーが開き、失敗したファイル内の各行ごとにエラー メッセージが表示されます。 
    
10. PST のマッピング ファイルが正常に検証されたら、ご契約条件を読み、チェック ボックスをオンにします。
    
11. **[完了]** をクリックして、ジョブを送信します。 
    
    ジョブは、[**データを Office 365 にインポートする**] ページの PST インポートジョブの一覧に表示されます。 
    
12. ジョブを選択し、 ****![[更新の](media/O365-MDM-Policy-RefreshIcon.gif)更新] アイコンをクリックして、詳細ウィンドウに表示される状態情報を更新します。 
    
13. 詳細ウィンドウで、**[詳細の表示]** をクリックして、選択したジョブの最新の状態を取得します。 
 
## <a name="more-information"></a>詳細情報

- PST ファイルを Office 365 にインポートする理由
    
  - 組織の電子メールを Office 365 に移行することをお勧めします。
    
  - 次のことが可能になるので、組織のコンプライアンスのニーズに対応するのに役立ちます。
    
  - アーカイブ メールボックスを有効にして、追加のメールボックス容量をユーザーに提供する。
    
  - メールボックスを保持状態にして、コンテンツを保持する。
    
  - Microsoft 電子情報開示ツールを使って、メールボックスのコンテンツを検索する。
    
  - アイテム保持ポリシーを使って、メールボックスのコンテンツの保持期間を制御する。
    
  - メールボックス関連イベントに対して Office 365 監査ログを検索します。
    
  - データ損失を防止するのに役立ちます。 Office 365 メールボックスにインポートされる PST ファイルは、データをユーザーのコンピューターに保存するのではなく、Exchange Online の高可用性機能を継承します。
    
  - データがクラウドに格納されるので、ユーザーはあらゆるデバイスからデータを利用できます。
    
- 手順2、3、および4で取得したキー、id、および url の例を次に示します。 この例には、o365importtool.zip ツールで実行して、PST ファイルを暗号化して Office 365 にアップロードするためのコマンドの構文も含まれています。 パスワードやその他のセキュリティ関連情報を保護するのと同じように、これらのファイルを保護するための予防策を必ず講じてください。
    
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

- 前述したように、Office 365 インポートサービスは、PST ファイルがメールボックスにインポートされた後、保持ホールドの設定 (無期限) を有効にします。 つまり、 *RentionHoldEnabled*プロパティはに`True`設定されているため、メールボックスに割り当てられたアイテム保持ポリシーは処理されません。 これにより、メールボックスの所有者は、削除またはアーカイブポリシーによる古いメッセージの削除またはアーカイブを禁止することにより、新しくインポートされたメッセージを管理できます。 この保持ホールドを管理するために実行できるいくつかの手順を次に示します。 
    
  - 一定の期間が経過した後、 `Set-Mailbox -RetentionHoldEnabled $false`コマンドを実行して保存機能を無効にすることができます。 手順については、「[メールボックスを保持ホールドの状態にする](https://go.microsoft.com/fwlink/p/?LinkId=544749)」を参照してください。
    
  - 今後、ある日付に無効になるように、保存機能を構成することができます。 そのためには、 `Set-Mailbox -EndDateForRetentionHold <date>`コマンドを実行します。 たとえば、今日の日付が2016年6月1日で、保存機能を30日以内に無効にする場合は、次のコマンド`Set-Mailbox -EndDateForRetentionHold 7/1/2016`を実行します。 このシナリオでは、 *RentionHoldEnabled*プロパティをに`True`設定したままにします。 詳細については、「[メールボックスの設定](https://go.microsoft.com/fwlink/p/?LinkId=150317)」を参照してください。
    
  - メールボックスに割り当てられているアイテム保持ポリシーの設定を変更して、インポートした古いアイテムがすぐに削除されるか、ユーザーのアーカイブメールボックスに移動されないようにすることができます。 たとえば、メールボックスに割り当てられている削除ポリシーまたはアーカイブポリシーの保存期間を長くすることができます。 このシナリオでは、アイテム保持ポリシーの設定を変更した後、メールボックスの保存機能をオフにします。 詳細については、「 [Office 365 組織のメールボックスのアーカイブおよび削除ポリシーをセットアップする](set-up-an-archive-and-deletion-policy-for-mailboxes.md)」を参照してください。
