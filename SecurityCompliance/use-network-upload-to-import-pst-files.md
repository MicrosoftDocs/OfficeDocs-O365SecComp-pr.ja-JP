---
title: ネットワークアップロードを使用して組織の PST ファイルを Office 365 にインポートする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: '管理者向け: Office 365 で、ネットワークアップロードを使用して複数の PST ファイルをユーザーのメールボックスに一括インポートする方法について説明します。'
ms.openlocfilehash: 73123d5f36a01b31cfc38e6404bd400bb722fb36
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264242"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a>ネットワークアップロードを使用して組織の PST ファイルを Office 365 にインポートする

> [!NOTE]
> この記事は、管理者を対象としています。 PST ファイルを自分のメールボックスにインポートしようとしていますか? 「 [Outlook .pst ファイルからメール、連絡先、予定表をインポートする](https://go.microsoft.com/fwlink/p/?LinkID=785075)」を参照してください。
  
この記事では、ネットワークアップロードを使用して複数の PST ファイルを Office 365 メールボックスに一括インポートするために必要な手順を説明します。 ネットワークアップロードを使用して pst ファイルを Office 365 メールボックスに一括インポートする方法についてよく寄せられる質問については、「 [faq for network upload to import pst files](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files)」を参照してください。
  
[手順 1: SAS URL をコピーして Azure azcopy をインストールする](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[手順 2: Office 365 に PST ファイルをアップロードする](#step-2-upload-your-pst-files-to-office-365)

[オプション手順 3: Office 365 にアップロードされた PST ファイルの一覧を表示する](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[手順 4: PST インポートのマッピングファイルを作成する](#step-4-create-the-pst-import-mapping-file)

[手順 5: Office 365 で PST インポートジョブを作成する](#step-5-create-a-pst-import-job-in-office-365)

[手順 6: データをフィルター処理し、PST インポートジョブを開始する](#step-6-filter-data-and-start-the-pst-import-job)

Office 365 メールボックスに PST ファイルをインポートするには、手順1を一度だけ実行する必要があることに注意してください。 これらの手順を実行した後、PST ファイルのバッチをアップロードしてインポートするたびに、手順2から手順6に従います。

## <a name="before-you-begin"></a>始める前に
  
- PST ファイルを Office 365 メールボックスにインポートするには、Exchange Online でメールボックスのインポートのエクスポートの役割を割り当てられている必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. 詳細については、「 [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688)」の「役割グループに役割を追加する」または「役割グループを作成する」のセクションを参照してください。
    
    さらに、Security & コンプライアンスセンターでインポートジョブを作成するには、次のいずれかの条件を満たしている必要があります。
    
  - Exchange Online では、メール受信者の役割が割り当てられている必要があります。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    または
    
  - Office 365 組織の全体管理者である必要があります。
    
  > [!TIP]
    > Office 365 に PST ファイルをインポートするための特別な目的である Exchange Online に新しい役割グループを作成することを検討してください。 PST ファイルのインポートに必要な最低限の特権レベルについては、メールボックスのインポートの役割とメール受信者の役割を新しい役割グループに割り当ててから、メンバーを追加します。 
  
- PST ファイルを Office 365 にインポートするためにサポートされている唯一の方法は、このトピックで説明されているように、Azure azcopy ツールを使用することです。 azure ストレージエクスプローラーを使用して、PST ファイルを azure ストレージ領域に直接アップロードすることはできません。
    
- Office 365 にインポートする PST ファイルは、組織内のファイルサーバーまたは共有フォルダーに格納する必要があります。 手順2では、このファイルサーバーまたは共有フォルダーに格納されている PST ファイルを Office 365 にアップロードする Azure azcopy ツールを実行します。
    
- この手順では、アクセスキーを含む URL のコピーのコピーと保存を行います。 この情報は、手順2で pst ファイルをアップロードするために使用され、手順3で Office 365 にアップロードされた pst ファイルの一覧を表示します。 パスワードやその他のセキュリティ関連の情報を保護するのと同じように、この URL を保護するための予防措置を講じるようにしてください。 たとえば、パスワードで保護された Microsoft Word 文書、または暗号化された USB ドライブに保存することができます。 この組み合わせの URL とキーの例については、「 [More information](#more-information) 」セクションを参照してください。 
    
- Office 365 の非アクティブなメールボックスに PST ファイルをインポートすることができます。 これを行うには、PST インポートマッピングファイルの`Mailbox`パラメーターに非アクティブなメールボックスの GUID を指定します。 詳細については**** 、このトピックの「手順4」を参照してください。 
    
- Exchange ハイブリッド展開では、プライマリメールボックスがオンプレミスであるユーザーのクラウドベースのアーカイブメールボックスに PST ファイルをインポートできます。 これを行うには、PST インポートマッピングファイルで以下の手順を実行します。
    
  - `Mailbox`パラメーターに、ユーザーの社内メールボックスの電子メールアドレスを指定します。 
    
  - `IsArchive`パラメーターに**TRUE**の値を指定します。 
    
    詳細については、[手順 4](#step-4-create-the-pst-import-mapping-file)を参照してください。 
    
- PST ファイルが Office 365 メールボックスにインポートされると、メールボックスの保持ホールドの設定は無期限に有効になります。 これは、メールボックスに割り当てられたアイテム保持ポリシーは、保存機能を無効にするか、保留を解除する日付を設定するまで処理されないことを意味します。 なぜこれを行うのでしょうか。 メールボックスにインポートされたメッセージが古くなっている場合は、メールボックスに対して構成されたアイテム保持ポリシーに基づいて保持期間が経過したために、削除 (パージ) される可能性があります。 メールボックスの保存機能を有効にすると、メールボックスの所有者は新しくインポートされたメッセージを管理することができ、メールボックスの保存期間の設定を変更する時間を与えることができます。 保持ホールドの管理に関する提案については、このトピックの「**詳細情報**」タブを参照してください。 
    
- 既定では、Office 365 メールボックスで受信できる最大メッセージサイズは 35 MB です。 これは、メールボックスの*MaxReceiveSize*プロパティの既定値が 35 MB に設定されているためです。 ただし、Office 365 の最大メッセージ受信サイズの制限は 150 MB です。 そのため、35 mb を超えるアイテムを含む PST ファイルをインポートすると、Office 365 インポートサービスによって、ターゲットメールボックスの*MaxReceiveSize*プロパティの値が 150 mb に自動的に変更されます。 これにより、150 MB までのメッセージをユーザーのメールボックスにインポートできます。 
    
    > [!TIP]
    > メールボックスのメッセージ受信サイズを特定するには、Exchange Online PowerShell で次のコマンドを`Get-Mailbox <user mailbox> | FL MaxReceiveSize`実行します。 

## <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a>手順 1: SAS URL をコピーして Azure azcopy をインストールする

最初の手順として、Azure azcopy ツールをダウンロードしてインストールします。このツールは、手順2で実行して PST ファイルを Office 365 にアップロードします。 組織の SAS URL もコピーします。 この url は、組織のための Microsoft クラウド内の Azure ストレージの場所のネットワーク URL と、共有アクセス署名 (SAS) キーの組み合わせです。 このキーは、Azure ストレージの場所に PST ファイルをアップロードするために必要なアクセス許可を提供します。 SAS URL を保護するための予防措置を講じてください。 これは組織に固有であり、手順2で使用されます。

> [!IMPORTANT]
> network upload メソッドを使用して PST ファイルをインポートするには、次の手順の手順6b でダウンロードできるバージョンの Azure azcopy を使用することをお勧めします。
  
1. に[https://protection.office.com](https://protection.office.com)移動し、Office 365 組織の管理者アカウントの資格情報を使用してサインインします。 
    
2. セキュリティ & コンプライアンスセンターの左側のウィンドウで、[**データガバナンス** \>の**インポート**] をクリックします。
    
    > [!NOTE]
    > セキュリティ & コンプライアンスセンターの [**インポート**] ページにアクセスするには、適切なアクセス許可が割り当てられている必要があります。 詳細については、「**はじめに**」セクションを参照してください。 
    
3. [**インポート**] ページで、 ![[追加](media/ITPro-EAC-AddIcon.gif) ] アイコン [**新しいインポートジョブ**] をクリックします。
    
    [ジョブのインポート] ウィザードが表示されます。
    
4. PST インポートジョブの名前を入力し、[**次へ**] をクリックします。 小文字、数字、ハイフン、およびアンダースコアを使用してください。 名前には、大文字を使用したり、スペースを含めたりすることはできません。
    
5. [**データをアップロードまたは出荷しますか?** ] ページで、[**データのアップロード**] をクリックし、[**次へ**] をクリックします。
    
    ![[データをアップロードしてネットワークアップロードのインポートジョブを作成する] をクリックします。](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. [**データのインポート**] ページで、次の2つの操作を行います。 
    
    ![SAS URL をコピーして、[データのインポート] ページに Azure azcopy ツールをダウンロードする](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    a. 手順2で、[**ネットワークアップロード SAS URL を表示する**] をクリックします。 SAS URL が表示されたら、[**クリップボードにコピー** ] をクリックして貼り付け、ファイルに保存し、後でアクセスできるようにします。
    
    b. 手順3で、[ **azure azcopy のダウンロード**] をクリックして、azure azcopy ツールをダウンロードしてインストールします。 ポップアップウィンドウで、[**実行**] をクリックして azcopy をインストールします。 
    
> [!NOTE]
> [**データのインポート**] ページは開いたままにしておくことができます (SAS URL を再度コピーする必要がある場合)。または、[**キャンセル**] をクリックして閉じます。 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>手順 2: Office 365 に PST ファイルをアップロードする

これで、azcopy ツールを使用して PST ファイルを Office 365 にアップロードする準備ができました。 このツールは、Microsoft クラウド内の Azure ストレージの場所にそれらをアップロードして保存します。 前述したように、PST ファイルをアップロードする Azure ストレージの場所は、Office 365 組織が配置されているのと同じ地域の Microsoft データセンターに存在します。 この手順を完了するには、PST ファイルを組織内のファイル共有またはファイル サーバーに配置する必要があります。 これは、次の手順でソース ディレクトリと呼ばれます。 azcopy ツールを実行するたびに、別のソースディレクトリを指定することができます。 
  
1. ローカル コンピューター上でコマンド プロンプトを開く。
    
2. 手順1で azcopy ツールをインストールしたディレクトリに移動します。 ツールを既定の場所にインストールした場合は、 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`に移動します。
    
3. 次のコマンドを実行して、Office 365 に PST ファイルをアップロードします。

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    > [!IMPORTANT] 
    > 前のコマンドのソースの場所としてディレクトリを指定する必要があります。個別の PST ファイルを指定することはできません。 ソースディレクトリ内のすべての PST ファイルがアップロードされます。
 
    次の表では、azcopy .exe パラメーターとその必須値について説明します。 前の手順で取得した情報は、これらのパラメーターの値で使用されます。
    
    |**パラメーター**|**説明**|**例**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |Office 365 にアップロードされる PST ファイルを含む、組織内のソースディレクトリを指定します。  <br/> このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |手順1で取得した SAS URL を指定します。  <br/> このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> **ヒント:** オプションPST ファイルをアップロードするために、Azure ストレージの場所にサブフォルダーを指定することができます。 これを行うには、SAS URL にサブフォルダーの場所 ("ingestiondata" の後) を追加します。 最初の例では、サブフォルダーを指定しません。これは、pst が Azure ストレージの場所のルート ( *ingestiondata*という名前) にアップロードされることを意味します。 2番目の例では、PST ファイルを Azure ストレージの場所のルートにあるサブフォルダー ( *PSTFiles*という名前) にアップロードします。  <br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> または  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |詳細な状態メッセージをログファイルに出力します。 既定では、詳細ログファイルは%LocalAppData%\Microsoft\Azure\AzCopy. の azcopyverbose .log という名前です。 このオプションに既存のファイルの場所を指定すると、そのファイルに詳細ログが追加されます。  <br/> このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |このオプションスイッチでは、 `/Source:`パラメーターで指定されたソースディレクトリ内のサブフォルダーにある pst ファイルが、azcopy ツールによってコピーされるように、再帰モードを指定します。  <br/> **注:** このスイッチを含めると、サブフォルダー内の PST ファイルは、アップロード後に、Azure ストレージの場所に別のファイルパス名を持つことになります。 手順4で作成した CSV ファイルの正確なファイルのパス名を指定する必要があります。  <br/> | `/S` <br/> |
    | `/Y` <br/> |この必須スイッチでは、PST ファイルを Azure ストレージの場所にアップロードするときに、書き込み専用の SAS トークンを使用できます。 手順1で取得した sas url (およびパラメーターで`/Dest:`指定) は書き込み専用の sas url なので、このスイッチを含める必要があります。 書き込み専用の SAS URL を使用しても、azure ストレージの場所にアップロードされた PST ファイルの一覧を表示することはできません。  <br/> | `/Y` <br/> |
   
以下は、各パラメーターに実際の値を使用した azcopy の構文の例です。
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

コマンドを実行すると、PST ファイルのアップロードの進行状況を示す状態メッセージが表示されます。 最終状態メッセージには、正常にアップロードされたファイルの合計数が表示されます。

> [!TIP]
> azcopy コマンドを正常に実行し、すべてのパラメーターが正しいことを確認したら、手順1で取得した情報をコピーしたのと同じ (セキュリティで保護された) ファイルにコマンドライン構文のコピーを保存します。 その後、azcopy ツールを実行して PST ファイルを Office 365 にアップロードするたびに、このコマンドをコマンドプロンプトにコピーして貼り付けることができます。 変更する必要があるのは、 `/Source:`パラメーターの値のみです。 これは、PST ファイルがあるソース ディレクトリによって異なります。

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>オプション手順 3: Office 365 にアップロードされた PST ファイルの一覧を表示する

オプションの手順として、Microsoft azure ストレージエクスプローラー (無償のオープンソースツール) をインストールして使用し、azure blob にアップロードした PST ファイルの一覧を表示することができます。 これを行うには、次の2つの適切な理由があります。
  
- 組織内の共有フォルダーまたはファイルサーバーの PST ファイルが Azure blob に正常にアップロードされたことを確認します。
    
- Azure blob にアップロードされた各 PST ファイルのファイル名 (およびサブフォルダーが含まれている場合はそのパス名) を確認します。 これは、次の手順で pst マッピングファイルを作成している場合に、各 pst ファイルのフォルダーパス名とファイル名の両方を指定する必要があるため、非常に役立ちます。 これらの名前を確認すると、PST マッピングファイルの潜在的なエラーを減らすのに役立ちます。
    
Microsoft Azure ストレージエクスプローラーはプレビュー段階です。
  
> [!IMPORTANT]
> Azure ストレージエクスプローラーを使用して PST ファイルをアップロードまたは変更することはできません。 PST ファイルを Office 365 にインポートするためにサポートされている唯一の方法は、azcopy を使用することです。 また、Azure blob にアップロードした PST ファイルを削除することもできません。 PST ファイルを削除しようとすると、必要なアクセス許可がないというエラーが表示されます。 すべての PST ファイルが Azure ストレージ領域から自動的に削除されることに注意してください。 If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created.
  
azure ストレージエクスプローラーをインストールして azure ストレージ領域に接続するには、次のようにします。
  
1. [Microsoft Azure ストレージエクスプローラーツール](https://go.microsoft.com/fwlink/p/?LinkId=544842)をダウンロードしてインストールします。
    
2. Microsoft Azure ストレージエクスプローラーを起動し、左側のウィンドウで [**ストレージアカウント**] を右クリックして、[ **Azure ストレージに接続] を**クリックします。
    
    ![[ストレージアカウント] を右クリックし、[Azure ストレージへの接続] をクリックします。](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. [**共有アクセス署名 (SAS) URI または接続文字列を使用**する] をクリックし、[**次へ**] をクリックします。
    
4. [ **sas uri を使用**する] をクリックし、手順1で取得した sas URL を [ **uri**] の下のボックスに貼り付け、[**次へ**] をクリックします。
    
5. [**接続の概要**] ページで、接続情報を確認し、[**接続**] をクリックします。
    
    **ingestiondata**コンテナーが開きます。このファイルには、手順2でアップロードした PST ファイルが含まれています。 **ingestiondata**コンテナーは、**ストレージアカウント** \> **(SAS 接続されたサービス)** \> **Blob コンテナー**の下にあります。 
    
    ![Azure ストレージ エクスプローラーには、アップロードした PST ファイルの一覧が表示される](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. Microsoft azure ストレージエクスプローラーの使用が終了したら、[ **ingestiondata**] を右クリックし、 **** [切断] をクリックして azure ストレージ領域から切断します。 そうしないと、次に接続しようとしたときにエラーが表示されます。 
    
    ![ingestion を右クリックして [デタッチ] をクリックし、Azure のストレージ エリアから切断する](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>手順 4: PST インポートのマッピングファイルを作成する

pst ファイルが Office 365 組織の Azure ストレージの場所にアップロードされた後、次の手順では、pst ファイルがインポートされるユーザーメールボックスを指定するコンマ区切り値 (CSV) ファイルを作成します。 PST インポートジョブを作成する場合は、次の手順でこの CSV ファイルを送信します。
  
1. [PST インポートのマッピングファイルのコピーをダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=544717)します。
    
2. CSV ファイルを開くか、またはローカル コンピューターに保存します。次の例は、完了した PST インポートのマッピング ファイル (メモ帳で開いた) を示しています。Microsoft Excel を使用して CSV ファイルを編集するのは、はるかに簡単です。


    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,PSTFiles,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,PSTFiles,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```
    CSV ファイルの先頭行、またはヘッダー行には、PST インポート サービスによって使用され、PST ファイルをユーザー メールボックスにインポートするパラメーターが一覧表示されます。 パラメーター名とパラメーター名の間はコンマで区切られています。 ヘッダー行の下の各行は、特定のメールボックスに PST ファイルをインポートするためのパラメーター値を表します。 ユーザー メールボックスにインポートする PST ファイルごとに行が必要になります。 必ずマッピング ファイル内のプレースホルダーのデータを実際のデータに置き換えてください。

   **注:** SharePoint のパラメーターを含め、見出し行の内容を変更しないでください。PST インポートプロセス中は無視されます。 

 3. 次の表の情報を使用して、必要な情報を含む CSV ファイルを作成します。


    |**パラメーター**|**説明**|**例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |データのインポート先となる Office 365 サービスを指定します。 PST ファイルをユーザーのメールボックスにインポート`Exchange`するには、を使用します。  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |手順2で PST ファイルをアップロードした Azure ストレージの場所でのフォルダーの場所を指定します。  <br/> 手順2の`/Dest:`パラメーターにオプションのサブフォルダー名を SAS URL に含めなかった場合は、CSV ファイルでこのパラメーターを空白のままにしておきます。 サブフォルダー名を含めた場合は、このパラメーターで指定します (2 番目の例を参照してください)。 このパラメーターの値は、大文字と小文字を区別します。  <br/> どちらの方法** でも、 `FilePath`パラメーターの値に "ingestiondata" を含めないでください。  <br/><br/> **重要:** ファイルパス名の大文字と小文字は、手順2の`/Dest:`パラメーターの SAS URL にオプションのサブフォルダー名を含めた場合に使用した場合と同じである必要があります。 たとえば、手順2でサブ`PSTFiles`フォルダー名を使用して、CSV ファイルの`pstfiles` `FilePath`パラメーターでを使用した場合、PST ファイルのインポートは失敗します。 両方のインスタンスで同じケースを使用してください。  <br/> |(空白)  <br/> または  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |ユーザー メールボックスにインポートする PST ファイルの名前を指定します。  このパラメーターの値は、大文字と小文字を区別します。  <br/> <br/>**重要:** CSV ファイルの pst ファイル名の大文字と小文字は、手順2で Azure ストレージの場所にアップロードされた pst ファイルと同じである必要があります。 たとえば、CSV ファイルの`annb.pst` `Name`パラメーターでを使用していて、実際の pst ファイルの名前が`AnnB.pst`である場合、その pst ファイルのインポートは失敗します。 CSV ファイルの pst の名前では、実際の pst ファイルと同じ大文字と小文字が使用されていることを確認してください。  <br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |PST ファイルのインポート先になるメールボックスの電子メール アドレスを指定します。  PST インポート サービスは、PST ファイルのパブリック フォルダーへのインポートをサポートしていないため、パブリック フォルダーの指定はできないことにご注意ください。  <br/> 非アクティブなメールボックスに PST ファイルをインポートするには、このパラメーターのメールボックス GUID を指定する必要があります。 この GUID を取得するには、Exchange Online で次の PowerShell コマンドを実行します。`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**注:** 場合によっては、1つのメールボックスがアクティブなメールボックスであり、もう一方のメールボックスが削除済み (非アクティブ) 状態になっているメールボックスが同じメールアドレスを持つ複数のメールボックスが存在することがあります。 このような状況では、PST ファイルをインポートするメールボックスを一意に識別するために、メールボックスの GUID を指定する必要があります。 この GUID をアクティブなメールボックスに対して取得するには`Get-Mailbox <identity of active mailbox> | FL Guid`、次の PowerShell コマンドを実行します。 回復可能な削除 (または非アクティブ) のメールボックスの GUID を取得`Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`するには、次のコマンドを実行します。  <br/> | `annb@contoso.onmicrosoft.com` <br/> または  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | PST ファイルをユーザーのアーカイブ メールボックスにインポートするかどうかを指定します。 次のような 2 つの選択肢があります。  <br/><br/>**FALSE** -PST ファイルをユーザーのプライマリメールボックスにインポートします。  <br/> **TRUE** -PST ファイルをユーザーのアーカイブメールボックスにインポートします。 This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). <br/><br/>このパラメーターをに`TRUE`設定し、ユーザーのアーカイブメールボックスが有効になっていない場合、そのユーザーのインポートは失敗します。 1人のユーザーに対してインポートが失敗した場合 (アーカイブが有効になっておら`TRUE`ず、このプロパティがに設定されているため)、インポートジョブの他のユーザーに影響が及ぶことに注意してください。  <br/>  If you leave this parameter blank, the PST file is imported to the user's primary mailbox.  <br/> <br/>**注:** プライマリメールボックスがオンプレミスであるユーザーのクラウドベースのアーカイブメールボックスに PST ファイルをインポートするには`TRUE` 、このパラメーターに対してを指定して、 `Mailbox`パラメーターのユーザーの社内メールボックスの電子メールアドレスを指定するだけです。  <br/> | `FALSE` <br/> または  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | PST ファイルのインポート先メールボックスフォルダーを指定します。  <br/>  このパラメーターを空白のままにした場合、PST はメールボックスのルートレベル (受信トレイフォルダーとその他の既定のメールボックスフォルダーと同じレベル) にある**インポート**された新しいフォルダーにインポートされます。  <br/>  を指定`/`した場合、PST ファイル内のアイテムは、ユーザーの受信トレイフォルダーに直接インポートされます。  <br/><br/>  を指定`/<foldername>`した場合、PST ファイルのアイテムは、 * \<foldername\> *という名前のフォルダーにインポートされます。 たとえば、を使用`/ImportedPst`すると、アイテムは**ImportedPst**という名前のフォルダーにインポートされます。 このフォルダーは、受信トレイフォルダーと同じレベルにあるユーザーのメールボックスに配置されます。  <br/><br/> **ヒント:** pst ファイルのインポートに最適なフォルダーの場所を決定できるように、いくつかのテストバッチを実行して、このパラメーターを試してみることをお勧めします。  <br/> |(空白)  <br/> または  <br/>  `/` <br/> または  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |このオプションパラメーターは、ANSI ファイル形式で PST ファイルをインポートするために使用するコードページの数値を指定します。 このパラメーターは、中国語、日本語、および韓国語 (CJK) の組織から PST ファイルをインポートするために使用されます。これらの言語では、通常、文字エンコードに2バイト文字セット (DBCS) を使用します。 メールボックスフォルダー名に DBCS を使用する言語の PST ファイルをインポートするためにこのパラメーターを使用していない場合は、インポート後にフォルダー名が正しくないことがよくあります。  <br/><br/> このパラメーターに使用することがサポートされている値の一覧については、「[コードページ識別子](https://go.microsoft.com/fwlink/p/?LinkId=328514)」を参照してください。  <br/> <br/>**注:** 前述したように、これはオプションのパラメーターであり、CSV ファイルに含める必要はありません。 または、1つまたは複数の行の値を空白のままにしておくこともできます。  <br/> |(空白)  <br/> または  <br/>  `932`(ANSI/OEM 日本語のコードページ識別子)  <br/> |
    | `SPFileContainer` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。   <br/> |該当なし  <br/> |
    | `SPManifestContainer` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。   <br/> |該当なし  <br/> |
    | `SPSiteUrl` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。   <br/> |該当なし  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>手順 5: Office 365 で PST インポートジョブを作成する

次の手順では、Office 365 のインポートサービスで PST インポートジョブを作成します。 前述のとおり、手順4で作成した PST インポートマッピングファイルを送信します。 新しいジョブを作成すると、Office 365 は pst ファイルのデータを分析し、pst インポートマッピングファイルで指定されたメールボックスに実際にインポートされるデータをフィルター処理する機会を提供します ([手順 6](#step-6-filter-data-and-start-the-pst-import-job)を参照)。
  
1. に[https://protection.office.com](https://protection.office.com)移動し、Office 365 組織の管理者アカウントの資格情報を使用してサインインします。 
    
2. セキュリティ & コンプライアンスセンターの左側のウィンドウで、[**データガバナンス**] をクリックし、[**インポート**] をクリックします。
    
3. [**インポート**] ページで、 ![[追加](media/ITPro-EAC-AddIcon.gif) ] アイコン [**新しいインポートジョブ**] をクリックします。
    
    **注:** 新しいインポートジョブを作成するには、セキュリティ & コンプライアンスセンターの [**インポート**] ページにアクセスするための適切なアクセス許可が割り当てられている必要があります。 詳細については、「**はじめに**」セクションを参照してください。 
    
4. PST インポートジョブの名前を入力し、[**次へ**] をクリックします。 小文字、数字、ハイフン、およびアンダースコアを使用してください。 名前には、大文字を使用したり、スペースを含めたりすることはできません。
    
5. [**データをアップロードまたは出荷しますか?** ] ページで、[**データのアップロード**] をクリックし、[**次へ**] をクリックします。
    
    ![[データをアップロードしてネットワークアップロードのインポートジョブを作成する] をクリックします。](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. [**データのインポート**] ページの手順4で、[ファイルの**アップロードが完了**しました] と [**マッピングファイルにアクセス**できます] チェックボックスをオンにして、[**次へ**] をクリックします。
    
    ![手順4で2つのチェックボックスをクリックします。](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. [**マッピングファイルの選択**] ページで、[**マッピングファイルの選択**] をクリックして、手順4で作成した PST インポートマッピングファイルを送信します。 
    
    ![[マッピングファイルの選択] をクリックして、インポートジョブ用に作成した CSV ファイルを送信します。](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. csv ファイルの名前が [**マッピングファイル名**] の下に表示されたら、[**検証**] をクリックして csv ファイルにエラーがないか確認します。 
    
    ![[検証] をクリックして、CSV ファイルのエラーを確認します。](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    PST インポート ジョブを作成するには、CSV ファイルが正常に検証される必要があります。 メモファイル名が正常に検証された後に、緑に変更されます。 検証が失敗した場合は、[ **View log** ] リンクをクリックします。 検証エラーレポートが開き、エラーが発生したファイル内の各行に関するエラーメッセージが表示されます。 
    
9. PST マッピングファイルが正常に検証された後、使用条件ドキュメントを読み、チェックボックスをオンにします。
    
10. [**保存**] をクリックしてジョブを送信し、ジョブが正常に作成されたら [**閉じる**] をクリックします。 
    
    状態のポップアップページが表示され、状態が "**分析中**" で、新しいインポートジョブが [**インポート**] ページの一覧に表示されます。 
    
11. [最新の情報](media/O365-MDM-Policy-RefreshIcon.gif)に更新] アイコンをクリックして、[**状態**] 列に表示される状態情報を更新します。 **** ![ 分析が完了し、データをインポートできる状態になると、状態は [**分析完了**] に変更されます。
    
    インポートジョブをクリックすると、[状態] ポップアップページが表示されます。これには、マッピングファイルに記載されている各 PST ファイルの状態など、インポートジョブに関する詳細情報が表示されます。
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>手順 6: データをフィルター処理し、PST インポートジョブを開始する

手順5でインポートジョブを作成した後、Office 365 は、アイテムの保存期間と pst ファイルに含まれるさまざまなメッセージの種類を識別することによって、pst ファイル (安全で安全な方法) のデータを分析します。 分析が完了し、データをインポートする準備ができたら、PST ファイルに含まれるすべてのデータをインポートするか、インポートするデータを制御するフィルターを設定してインポートしたデータをトリミングすることができます。
  
1. [セキュリティ & コンプライアンスセンター] の [**インポート**] ページで、手順5で作成したインポートジョブについて、[ **Office 365 にインポートする準備ができ**ました] をクリックします。 
    
    ![作成したインポートジョブの横にある [Office 365 にインポートする準備完了] をクリックします。](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    フライアウトページには、PST ファイルおよびインポートジョブに関するその他の情報が表示されます。
    
2. [フライアウト] ページで、[ **Office 365 へのインポート**] をクリックします。
    
    [**データをフィルター**する] ページが表示されます。 このファイルには、データの保存期間に関する情報を含む、Office 365 によって PST ファイルに対して実行された分析の結果として得られるデータ insights が含まれています。 この時点で、インポートされるデータをフィルター処理するか、すべてのデータをそのものとしてインポートするかを選択できます。 
    
    ![PST ファイルのデータをトリミングしたり、すべてのデータをインポートしたりできます。](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. 次のいずれかの操作を行います。
    
    a. インポートするデータをトリミングするには、[**はい、インポートする前にフィルターを適用**します] をクリックします。
    
    pst ファイルのデータをフィルター処理してからインポートジョブを開始する方法の詳細な手順については、「 [pst ファイルを Office 365 にインポートするときにデータをフィルターする](filter-data-when-importing-pst-files.md)」を参照してください。
    
    または
    
    b. PST ファイル内のすべてのデータをインポートするには、[**いいえ、** すべてをインポートします] をクリックし、[**次へ**] をクリックします。
    
4. すべてのデータをインポートすることを選択した場合は、[**データのインポート**] をクリックしてインポートジョブを開始します。 
    
    インポートジョブの状態が [**インポート**] ページに表示されます。 [ ![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif) **** の更新] をクリックして、[**状態**] 列に表示される状態情報を更新します。 インポートジョブをクリックして状態ポップアップページを表示すると、インポートされている各 PST ファイルに関する状態情報が表示されます。 

## <a name="how-the-import-process-works"></a>インポートプロセスのしくみ
  
ネットワークアップロードオプションと Office 365 インポートサービスを使用して、PST ファイルをユーザーのメールボックスに一括インポートすることができます。 ネットワークのアップロードとは、PST ファイルを Microsoft クラウドの一時的なストレージ領域としてアップロードすることを意味します。 その後、Office 365 インポートサービスは、PST ファイルをストレージ領域からターゲットユーザーのメールボックスにコピーします。
  
Office 365 のメールボックスに PST ファイルをインポートするためのネットワークアップロードプロセスの図と説明を以下に示します。
  
![PST ファイルを Office 365 にインポートするためのネットワークアップロードプロセスのワークフロー](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **pst インポートツールとキーをプライベート Azure ストレージの場所にダウンロード**する-最初の手順として、azure azcopy コマンドラインツールと、PST ファイルを Microsoft クラウド内の azure ストレージの場所にアップロードするために使用するアクセスキーをダウンロードします。 これらは、セキュリティ & コンプライアンスセンターの [**インポート**] ページから取得します。 キー (secure access signature (SAS) キーと呼ばれる) によって、PST ファイルをプライベートおよび安全な Azure ストレージの場所にアップロードするために必要なアクセス許可が提供されます。 このアクセスキーは組織に固有のものであり、Microsoft クラウドにアップロードされた後に PST ファイルへの権限のないアクセスを防止するのに役立てることができます。 Office 365 に PST ファイルをインポートする場合は、組織で別の Azure サブスクリプションを使用する必要はありません。 
    
2. **pst ファイルを azure ストレージの場所にアップロード**します。次の手順では、azcopy ツール (手順1でダウンロードしたもの) を使用して、Office 365 の同じ地域の Microsoft データセンターに存在する Azure ストレージの場所に pst ファイルをアップロードして保存します。組織があります。 これらをアップロードするには、Office 365 にインポートする PST ファイルが、組織内のファイル共有またはファイルサーバーに配置されている必要があります。
    
    PST ファイルの一覧を表示するために実行できるオプションの手順は、Azure ストレージの場所にアップロードされています。
    
3. **pst インポートのマッピングファイルを作成**する-pst ファイルが Azure ストレージの場所にアップロードされた後、次の手順では、pst ファイルがインポートされるユーザーメールボックスを指定するコンマ区切り値 (CSV) ファイルを作成します。 ユーザーのプライマリメールボックスまたはアーカイブメールボックスにインポートされます。 Office 365 インポートサービスは、CSV ファイルの情報を使用して PST ファイルをインポートします。
    
4. **pst インポートジョブを作成**する-次の手順では、セキュリティ & コンプライアンスセンターの [**インポート**] ページで pst インポートジョブを作成し、前の手順で作成した pst インポートマッピングファイルを送信します。 インポートジョブを作成した後、Office 365 は pst ファイルのデータを分析し、pst インポートマッピングファイルで指定されたメールボックスに実際にインポートするデータを制御するフィルターを設定する機会を提供します。 
    
5. **メールボックスにインポートする pst データをフィルター処理する**-インポートジョブが作成されて開始されると、Office 365 は pst ファイル内のデータ (安全かつ安全) を分析して、アイテムの保存期間と pst ファイルに含まれるさまざまなメッセージの種類を特定します。. 分析が完了し、データをインポートする準備ができたら、PST ファイルに含まれるすべてのデータをインポートするか、インポートするデータを制御するフィルターを設定してインポートしたデータをトリミングすることができます。
    
6. **pst インポートジョブを開始**する-インポートジョブが開始されると、Office 365 は pst インポートマッピングファイル内の情報を使用して、pst ファイルをユーザーのメールボックスにインポートします。 インポートジョブに関する状態情報 (インポートされる各 PST ファイルに関する情報を含む) は、セキュリティ & コンプライアンスセンターの [**インポート**] ページに表示されます。 インポートジョブが完了すると、ジョブの状態が [**完了**] に設定されます。
  
## <a name="more-information"></a>詳細情報

- PST ファイルを Office 365 にインポートする理由
    
  - 組織のアーカイブメッセージングデータを Office 365 にインポートすることをお勧めします。
    
  - データがクラウドに格納されるので、ユーザーはあらゆるデバイスからデータを利用できます。
    
  - Office 365 のコンプライアンス機能を、インポートした PST ファイルのデータに適用することにより、組織のコンプライアンスニーズに対応できます。 これには以下が含まれます。
    
  - [アーカイブメールボックス](enable-archive-mailboxes.md)および[自動拡張アーカイブ](enable-unlimited-archiving.md)を有効にすることで、ユーザーはインポートしたデータを格納するための追加のメールボックスストレージスペースを提供できます。 
    
  - メールボックスを[訴訟ホールド](https://go.microsoft.com/fwlink/?linkid=856286)の対象にして、インポートしたデータを保持します。 
    
  - Microsoft [eDiscovery ツール](search-for-content.md)を使用して、インポートしたデータを検索します。 
    
  - [Office 365 のアイテム保持ポリシー](retention-policies.md)を使用して、インポートしたデータが保持される期間、および保持期間が経過した後に実行するアクションを制御します。 
    
  - [Office 365 監査ログ](search-the-audit-log-in-security-and-compliance.md)で、インポートしたデータに影響するメールボックス関連イベントを検索します。 
    
  - コンプライアンスの目的でデータをアーカイブするために、[非アクティブなメールボックス](create-and-manage-inactive-mailboxes.md)にデータをインポートします。 
    
  - [データ損失防止ポリシー](data-loss-prevention-policies.md)を使用して、機密データが組織外に漏洩しないようにします。 
  
- 手順1で取得した Shared Access Signature (SAS) URL の例を次に示します。 この例には、azcopy で実行して PST ファイルを Office 365 にアップロードするコマンドの構文も含まれています。 パスワードやその他のセキュリティ関連の情報を保護するのと同じように、SAS URL を保護するための予防措置を講じるようにしてください。

    ```
    SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D

    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y

    EXAMPLES

    This example uploads PST files to the root of the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    
    This example uploads PST files to a subfolder named PSTFiles  in the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
``

- As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RetentionHoldEnabled*  property is set to  **True** so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold: 
    
    - After a certain period of time, you can turn off the retention hold by running the **Set-Mailbox -RetentionHoldEnabled $false** command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
   - You can configure the retention hold so that it's turned off on some date in the future. You do this by running the **Set-Mailbox -EndDateForRetentionHold *date*** command. For example, assuming that today's date is June 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  **Set-Mailbox -EndDateForRetentionHold 7/1/2016**. In this scenario, you would leave the  **RetentionHoldEnabled**  property set to  *True*. For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
   - You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    
