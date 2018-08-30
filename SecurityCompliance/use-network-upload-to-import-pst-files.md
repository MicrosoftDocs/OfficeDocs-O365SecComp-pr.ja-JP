---
title: ネットワークのアップロードを使用して、Office 365 の組織の PST ファイルをインポートするのには
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: '管理者: ネットワークのアップロードを使用して、Office 365 でユーザーのメールボックスに複数の PST ファイルを一括インポートする方法について説明します。'
ms.openlocfilehash: c5bcaed9075939d098ac4bf9fbf4d8a94007232c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531901"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a>ネットワークのアップロードを使用して、Office 365 の組織の PST ファイルをインポートするのには

> [!NOTE]
> この資料では、管理者用です。自分のメールボックスを PST ファイルをインポートしようとしていますか。[インポート電子メール、連絡先、および Outlook の .pst ファイルから予定表](https://go.microsoft.com/fwlink/p/?LinkID=785075)を参照してください。
  
ネットワークのアップロードを使用して、Office 365 のメールボックスに複数の PST ファイルを一括インポートするに必要な手順を次に示します。ネットワークのアップロードを使用して、Office 365 のメールボックスを PST ファイルを一括インポートするには、 [PST ファイルをインポートするのにはネットワークのアップロードを使用するための Faq](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files)を参照してくださいについてよく寄せられる質問。
  
[手順 1: SAS の URL をコピーし、Azure の AzCopy をインストール](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[手順 2: Office 365 の PST ファイルをアップロードします。](#step-2-upload-your-pst-files-to-office-365)

[(省略可能)Office 365 にアップロードされたステップ 3: ビューの PST ファイルの一覧](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[PST インポート マッピング ファイルを作成する手順 4。](#step-4-create-the-pst-import-mapping-file)

[手順 5:Office 365 で PST インポート ジョブを作成する](#step-5-create-a-pst-import-job-in-office-365)

[手順 6: データをフィルター処理し、PST のインポート ジョブを開始します。](#step-6-filter-data-and-start-the-pst-import-job)

Office 365 のメールボックスを PST ファイルをインポートするのには手順 1 で 1 回だけを実行する必要がある注意してください。後次の手順を実行すると、次の手順 6 を介して手順 2 をアップロードし、複数の PST ファイルをインポートするたびにします。

## <a name="before-you-begin"></a>はじめに
  
- メールボックスのエクスポートをインポートの役割を割り当てるには、Exchange オンライン Office 365 のメールボックスを PST ファイルをインポートするのにはする必要があります。既定では、この役割はありませんに割り当てられている役割グループは、Exchange オンライン。組織の管理役割グループに、メールボックスのインポート エクスポートの役割を追加できます。または、新しい役割グループを作成、メールボックスのインポート エクスポートの役割を割り当てるし、ユーザー自身をメンバーとして追加します。詳細については、追加するロール グループのロール」を参照してください。 または、「作成」の役割グループの[役割グループの管理](https://go.microsoft.com/fwlink/p/?LinkId=730688)のセクションです。
    
    Office 365 のセキュリティのジョブのインポートを作成するのにはさらに、&amp;コンプライアンス センターは、次のいずれかを満たす必要があります。
    
  - メール受信者の役割を割り当てるには、Exchange オンラインする必要があります。既定では、この役割は組織の管理と受信者の管理役割グループに割り当てられます。
    
    または
    
  - Office 365 の組織のグローバル管理者があります。
    
  > [!TIP]
    > Exchange Online の具体的には、Office 365 に PST ファイルをインポートする新しい役割グループを作成することを検討してください。PST ファイルをインポートするのには必要な特権を最低限のレベルで、新しい役割グループにメールボックスのエクスポートをインポートし、メール受信者の役割を割り当てるし、メンバーを追加します。 
  
- PST ファイルを Office 365 にインポートする方法のみがサポートは、このトピックで説明するよう Azure AzCopy ツールを使用します。Azure ストレージ領域に直接 PST ファイルをアップロードするのには、Azure ストレージ エクスプ ローラーを使うことはできません。
    
- ファイル サーバーまたは共有のフォルダー、組織内で Office 365 にインポートする PST ファイルを保存する必要があります。手順 2 では、このファイル サーバーに格納されるか、Office 365 にフォルダーを共有する PST ファイルをアップロードする Azure AzCopy ツールを実行するでしょう。
    
- この手順ではコピーして、アクセス キーを含む URL のコピーを保存します。この情報が適用されます、PST ファイルをアップロードする手順 2 と手順 3 で、Office 365 にアップロードされた PST ファイルの一覧を表示する場合。パスワードやその他のセキュリティに関連する情報を保護するようにこの URL を保護するために対策を講じていることを確認します。たとえばまたは暗号化された USB ドライブをパスワードで保護された Microsoft Word 文書に保存する可能性があります。URL とキーと組み合わせ、1 つの例の[詳細について](#more-information)はセクションを参照してください。 
    
- PST ファイルをインポートするには Office 365 の非アクティブなメールボックスにします。内の非アクティブなメールボックスの GUID を指定することによってこれを行う、 `Mailbox` PST インポート マッピング ファイル内のパラメーターです。[**命令**] タブの情報は、このトピックでは、手順 4 を参照してください。 
    
- Exchange ハイブリッド展開の場合は、[プライマリ メールボックスは、オンプレミス ユーザーのクラウド ベースのアーカイブ メールボックスに PST ファイルをインポートできます。PST インポート マッピング ファイルで次の操作を行います。
    
  - ユーザーのオンプレミスのメールボックスの電子メール アドレスを指定します`Mailbox`パラメーター。 
    
  - **真**の値を指定します`IsArchive`パラメーター。 
    
    詳細については、[手順 4](#step-4-create-the-pst-import-mapping-file)を参照してください。 
    
- PST ファイルが Office 365 のメールボックスにインポートされると、メールボックスの設定の保存は不定の期間のになっています。つまり、メールボックスに割り当てられているリテンション ・ ポリシーは、の保持を無効にするか、保留リストを無効にする日付を設定するまで処理されません。なぜこのような処理でしょうか。メールボックスにインポートするメッセージが古い場合は、それら可能性が完全に削除 (パージ)、メールボックスに対して構成されている保存期間の設定に基づいて、保存期間が期限切れになった。保存保留中のメールボックスを配置することと、これらの新しくインポートされたメッセージまたはメールボックスの保存期間の設定を変更するのには、時間を提供を管理するためにメールボックス所有者の時間が提供されます。保存保留リストを管理する方法に関する推奨事項については、このトピックの**詳細情報**] タブを参照してください。 
    
- デフォルトで、Office 365 のメールボックスで受信できるメッセージの最大サイズは 35 MB です。メールボックスの*MaxReceiveSize*プロパティの既定値は 35 MB に設定されているためにです。ただし、制限の Office 365 の最大のメッセージの受信サイズは 150 MB です。150 MB に移動先のメールボックス上の*MaxReceiveSize*プロパティの値を自動的に変更するが、Office 365 にインポート サービス、35 MB を超えるアイテムを含む PST ファイルをインポートする場合。メッセージは、このユーザーのメールボックスにインポートするのには最大 150 MB です。 
    
    > [!TIP]
    > サイズを受信するメッセージを識別する、メールボックスの Exchange のオンライン PowerShell でこのコマンドを実行することができます: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。 

### <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a>手順 1: SAS の URL をコピーし、Azure の AzCopy をインストール

最初のステップでは、ダウンロードして、Azure の AzCopy ツールを Office 365 に PST ファイルをアップロードする手順 2 で実行するツールをインストールします。組織の SA の URL をコピーすることもあります。この URL は、組織と共有アクセス署名 (SAS) キーをマイクロソフトのクラウド内の Azure ストレージ場所のネットワークの URL の組み合わせです。このキーは、Azure のストレージ場所に PST ファイルをアップロードする必要なアクセス許可を提供します。SAS URL を保護するために対策を講じていることを確認します。組織に一意でし、手順 2 で使用されます。
  
 **重要な:** Azure AzCopy バージョンのネットワークを使用して、PST ファイルをインポートするのには 7.1.0 のアップロード方法を使用することをお勧めします。バージョン 7.1.0 は次の手順で手順 6 b でダウンロードされます。 
  
1. [https://protection.office.com](https://protection.office.com)し、組織の Office 365 の管理者アカウントの資格情報を使用してサインインします。 
    
2. セキュリティの左側のウィンドウで&amp;コンプライアンス センターでは、**データの管理**をクリックして\>**インポート**します。
    
    **注:** セキュリティの**インポート**] ページにアクセスするための適切なアクセス許可を割り当てる必要がある&amp;コンプライアンス センターです。詳細については、**開始する前に**セクションを参照してください。 
    
3. [**インポート**] ページをクリックして![アイコンの追加](media/ITPro-EAC-AddIcon.gif)**新規ジョブをインポート**します。
    
    インポート ジョブ ・ ウィザードが表示されます。
    
4. PST インポート ジョブの名前を入力し、[**次へ**] をクリックします。小文字の英字、数字、ハイフン、およびアンダー スコアを使用します。大文字を使用して、またはの名前にスペースを追加できません。
    
5. **アップロードしたり、データを送付したいですか?** ページで、**データのアップロード**] をクリックし、[**次へ**] をクリックします。
    
    ![アップロードが、ネットワークのアップロードを作成するデータは、ジョブをインポート] をクリックします。](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. **データのインポート**] ページで、次の 2 つの操作を行います。 
    
    ![SAS の URL をコピーし、データのインポート] ページで、Azure の AzCopy ツールをダウンロード](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    a: ステップ 2 で、**ネットワークのアップロード URL の SA を表示する**をクリックします。SAS の URL が表示されたら、**クリップボードにコピー** ] をクリックし、貼り付けることとファイルに保存して後で使用するため。
    
    b. 手順 3 で、 **Azure AzCopy のダウンロード**をダウンロードして、Azure の AzCopy ツールをインストールする] をクリックします。述べたように、バージョン 7.1.0 がダウンロードされます。ポップアップ ウィンドウで、AzCopy をインストールするのには**実行**をクリックします。 
    
  **注:** できます**データのインポート**] ページを開いておく場合に SAS の URL を再度コピーする必要があります) するかを閉じるには**キャンセル**をクリックします。 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>手順 2: Office 365 の PST ファイルをアップロードします。

AzCopy.exe ツールを使用して、Office 365 に PST ファイルをアップロードする準備が整いました。このツールでは、アップロードし、マイクロソフトのクラウドでは、Azure ストレージの場所に保存します。説明したよう、同じ地域マイクロソフト データ センターで、Office 365 の組織が配置されている Azure ストレージの場所に PST ファイルをアップロードすることが存在します。この手順を完了するには、PST ファイルをファイル共有や、組織内のファイル サーバーに配置する必要があります。これは、次の手順でソース ディレクトリと呼ばれます。AzCopy ツールを実行するたびに別のソース ディレクトリを指定できます。 
  
1. ローカル コンピューター上でコマンド プロンプトを開きます。
    
2. 手順 1 で AzCopy.exe ツールをインストールしたディレクトリに移動します。デフォルトの場所にツールをインストールした場合に、 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`。
    
3. Office 365 に PST ファイルをアップロードするのには次のコマンドを実行します。

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    次の表は、パラメーターと、必要な値について説明します。これらのパラメーターの値を前の手順で取得した情報が使用されることに注意してください。
    
    |**パラメーター**|**説明**|**例**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |Office 365 にアップロードする PST ファイルを含む、組織内には、ソース ディレクトリを指定します。  <br/> このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |手順 1 で取得した SAS の URL を指定します。  <br/> このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> **ヒント:**(省略可能)PST ファイルをアップロードするのには Azure ストレージの場所にサブフォルダーを指定することができます。SAS の url ("ingestiondata") の後にサブフォルダーの場所を追加するこれを行います。最初の例は、サブフォルダーを指定しません。つまり、pst ファイルには、Azure ストレージの場所の ( *ingestiondata*という名前) のルートにアップロードされます。2 番目の例では、Azure のストレージの場所のルートに、PST ファイルのフォルダー ( *PSTFiles* ) をアップロードします。<br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> または  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |詳細なステータス メッセージをログ ファイルに出力します。既定では、詳細なログ ファイルは、%LocalAppData%\Microsoft\Azure\AzCopy 内の AzCopyVerbose.log という名前です。既存のファイルの場所をこのオプションで指定した場合、詳細なログはそのファイルに追加されます。  <br/> このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |このオプション スイッチは、AzCopy ツールがで指定されたソース ディレクトリ内のサブフォルダーにある Pst ファイルをコピーするために再帰的なモードを指定します`/Source:`パラメーター。  <br/> **注:** このスイッチを含める場合は、PST ファイルのサブフォルダーには、アップロードした Azure ストレージの場所に別のファイルのパス名があります。手順 4 で作成した CSV ファイルの正確なファイルのパス名を指定する必要があります。<br/> | `/S` <br/> |
    | `/Y` <br/> |必要なこのスイッチにより、書き込み専用の SAS トークンの Azure ストレージの場所に PST ファイルをアップロードするとします。手順 1 で取得した SAS の URL (で指定された`/Dest:`パラメーター) は、書き込み専用 SAS、URL はこのスイッチを含める必要があります。書き込み専用の SAS URL が禁止されない Azure ストレージ エクスプ ローラーを使用して、Azure のストレージの場所にアップロードされた PST ファイルの一覧を表示するのには注意してください。<br/> | `/Y` <br/> |
   
各パラメーターの実際の値を使う AzCopy.exe ツールの構文の例を以下に示します。
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

コマンドを実行すると、PST ファイルのアップロードの進行状況を示す状態メッセージが表示されます。最終の状態メッセージは、正常にアップロードされたファイルの合計数を示しています。 
    
**ヒント:** 正常に AzCopy.exe コマンドを実行してすべてのパラメーターが正しいことを確認するものと同じ情報をコピーする (セキュリティで保護された) ファイルをコマンド ・ ライン構文のコピーを保存で取得したステップ 1 です。次コピーして、Office 365 に PST ファイルをアップロードする AzCopy.exe ツールを実行するたびに、コマンド プロンプトで次のコマンドを貼り付けることができます。ものは、唯一の値を変更する必要があります、`/Source:`のパラメーターです。これは、PST ファイルがあるソース ディレクトリとは異なります。 

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>(省略可能)Office 365 にアップロードされたステップ 3: ビューの PST ファイルの一覧

オプションの手順としてインストールし、Azure blob にアップロードしている PST ファイルの一覧を表示するのには、Azure ストレージ エクスプ ローラーは、無料のオープン ソースのツール) を使用できます。これを行う 2 つの理由があります。
  
- PST ファイルを共有フォルダーまたは組織内のファイル サーバーからが、Azure blob を正常にアップロードされたことを確認します。
    
- Azure blob にアップロードされた各 PST ファイルのファイル名 (および 1 つ含まれている場合、サブフォルダーのパス名) を確認します。各 PST ファイルのファイル名とフォルダーのパス名を指定する必要があるために、次の手順でファイルをマッピングする pst ファイルを作成するときに非常に便利です。これらの名前を確認すると、PST のマッピング ・ ファイル内の潜在的なエラーを削減できます。
    
プレビューでは、Microsoft Azure ストレージ エクスプ ローラーです。
  
 **重要な:** アップロードまたは PST ファイルを変更するには、Azure ストレージ エクスプ ローラーを使うことはできません。Office 365 に PST ファイルをインポートするための唯一のサポートされている方法では、AzCopy を使用します。また、Azure blob にアップロードしている PST ファイルを削除できません。PST ファイルを削除しようとすると、必要な権限がないというエラー メッセージが表示されます。Azure ストレージ領域からすべての PST ファイルを自動的に削除するに注意してください。進行中のインポート ジョブはありませんし、内のすべての PST ファイルがある場合、* * ingestiondata * * コンテナーは、最新のインポート ジョブを作成した後 30 日を削除します。 
  
Azure ストレージ エクスプ ローラーをインストールし、Azure のストレージ領域への接続します。
  
1. ダウンロードして、 [Microsoft Azure ストレージ エクスプ ローラー ツール](https://go.microsoft.com/fwlink/p/?LinkId=544842)をインストールします。
    
2. Microsoft Azure ストレージ エクスプ ローラーを起動左側のウィンドウで、**ストレージ アカウント**を右クリックし、 **Azure ストレージへの接続**] をクリックします。
    
    ![ストレージ アカウントを右クリックし、Azure ストレージに接続] をクリックし、](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. **共有アクセス署名 (SAS) URI、または接続文字列を使用**] をクリックし、[**次へ**] をクリックします。
    
4. **SAS の URI を使用**] をクリックして、[ **URI**] ボックスに、手順 1 で取得した SAS の URL を貼り付けます、[**次へ**] をクリックします。
    
5. [**接続の概要**] ページで、接続情報を確認し、[**接続**] をクリックできます。
    
    **Ingestiondata**コンテナーを開きます。手順 2 でアップロードしている PST ファイルが含まれています。**Ingestiondata**コンテナーは、**ストレージ アカウント**の下にある\> **(SAS-Attached サービス)** \> **Blob コンテナー**です。 
    
    ![Azure ストレージ エクスプローラーには、アップロードした PST ファイルの一覧が表示される](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. Microsoft Azure ストレージ エクスプ ローラーの使用が終了したら、 **ingestiondata**を右クリックし、Azure のストレージ領域から切断するのには**接続解除**] をクリックします。それ以外の場合、次に接続しようとするとき、エラーが表示されます。 
    
    ![ingestion を右クリックして [デタッチ] をクリックし、Azure のストレージ エリアから切断する](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>PST インポート マッピング ファイルを作成する手順 4。

Azure ストレージの場所、Office 365 の組織には、PST ファイルをアップロードされている後、次に、PST ファイルはインポートできません、ユーザーのメールボックスを指定する値 (CSV) ファイルを区切るコンマを作成します。PST インポート ジョブを作成するときは、次の手順では、この CSV ファイルを送信します。
  
1. [PST インポート マッピング ・ ファイルのコピーをダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=544717)します。
    
2. CSV ファイルを開くか、ローカル コンピューターに保存します。次の例は、完了した PST インポートのマッピング ファイル (メモ帳で開いた) を示しています。Microsoft Excel を使って CSV ファイルを編集するほうが、はるかに簡単です。


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
    最初の行、または CSV ファイルのヘッダー行は、PST ファイルをユーザーのメールボックスにインポートする PST インポート サービスによって使用されるパラメーターを一覧表示します。各パラメーター名は、コンマで区切られます。ヘッダー行の下の各行は、特定のメールボックスを PST ファイルをインポートするためのパラメーター値を表します。行は、各ユーザーのメールボックスにインポートする PST ファイルの必要があります。マッピング ファイル内のプレース ホルダーのデータを実際のデータに置き換えることを確認します。

   **注:** 設定を変更しないヘッダー行で、SharePoint のパラメーターです。PST のインポート処理中に無視されます。 

 3. 次の表の情報を使って、必要な情報を含む CSV ファイルを作成します。


    |**パラメーター**|**説明**|**例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Office 365 サービスにインポートするデータを指定します。PST ファイルをユーザーのメールボックスにインポートするを使用して、 `Exchange`。<br/> | `Exchange` <br/> |
    | `FilePath` <br/> |手順 2 で PST ファイルをアップロードした Azure ストレージの場所にフォルダーの場所を指定します。  <br/> SAS の URL を任意のサブフォルダーの名前が含まれていないかどうか、`/Dest:`ステップ 2 で、パラメーターを空白にこのパラメーター CSV ファイルにします。サブフォルダー名を入力した場合、このパラメーターの指定 (2 番目の例を参照してください)。このパラメーターの値は、大文字小文字を区別します。<br/> *どちらにしてがの値に"ingestiondata"を含まない*、`FilePath`のパラメーターです。  <br/><br/> **重要な:** ファイルのパス名の大文字と小文字に SAS の URL を任意のサブフォルダーの名前が含まれている場合に使用する場合と同じである必要があります、`/Dest:`で、手順 2 のパラメーターです。使用した場合など、 `PSTFiles` 、サブフォルダー名を手順 2 でをクリックして`pstfiles`で、 `FilePath` CSV ファイル内のパラメーター、PST ファイルのインポートは失敗します。両方のインスタンスで、同じ大文字と小文字を使用することを確認します。<br/> |(空白)  <br/> または  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |ユーザーのメールボックスにインポートする PST ファイルの名前を指定します。このパラメーターの値は、大文字小文字を区別します。<br/> <br/>**重要な:** CSV ファイル内の PST ファイル名の大文字と小文字は、手順 2 で Azure ストレージの場所にアップロードされた PST ファイルと同じである必要があります。使用する場合など、`annb.pst`で、 `Name` 、CSV ファイルが実際の PST ファイルの名前のパラメーターは、 `AnnB.pst`、その PST ファイルのインポートは失敗します。CSV ファイルに pst ファイルの名前が実際の PST ファイルと同じ大文字と小文字を使用することを確認します。<br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |PST ファイルをインポートするメールボックスの電子メール アドレスを指定します。PST インポート サービスがパブリック フォルダーを PST ファイルのインポートをサポートしていないために、パブリック フォルダーを指定できないことに注意してください。<br/> 非アクティブなメールボックスに PST ファイルをインポートするのにはこのパラメーターにメールボックスの GUID を指定する必要です。この GUID を取得するには、Exchange Online で次の PowerShell コマンドを実行します: ' Get メールボックス<identity of inactive mailbox>- InactiveMailboxOnly。 | FL Guid` <br/> <br/>**Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get メールボックス<identity of active mailbox> | FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get メールボックス<identity of soft-deleted or inactive mailbox>- SoftDeletedMailbox | FL Guid' です。  <br/> | `annb@contoso.onmicrosoft.com` <br/> または  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | PST ファイルをユーザーのアーカイブ メールボックスにインポートするかどうかを指定します。次のような 2 つの選択肢があります。<br/><br/>**FALSE**は、ユーザーのプライマリ メールボックスを PST ファイルをインポートします。  <br/> **TRUE**は、ユーザーのアーカイブ メールボックスに PST ファイルをインポートします。これを対象とする[ユーザーのアーカイブ メールボックスを有効に](enable-archive-mailboxes.md)するします。<br/><br/>このパラメーターを設定する場合は、`TRUE`とは、ユーザーのアーカイブ メールボックスが有効になっていない、そのユーザーのインポートは失敗します。1 人のユーザーのインポートに失敗した場合に注意してください (そのアーカイブが有効になっていないし、このプロパティに設定されているため`TRUE`)、インポート ジョブ内の他のユーザーが影響を受けることはありません。<br/>  このパラメーターを空白のままにすると、PST ファイルは、ユーザーのプライマリ メールボックスにインポートされます。  <br/> <br/>**注:** クラウド ベースのアーカイブ メールボックスがプライマリ メールボックスは、オンプレミス ユーザーの PST ファイルをインポートするを指定するだけ`TRUE`このパラメーターのユーザーのオンプレミスのメールボックスの電子メール アドレスを指定し、`Mailbox`パラメーター。  <br/> | `FALSE` <br/> または  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | PST ファイルをインポートするメールボックス フォルダーを指定します。  <br/>  このパラメーターを空白のままにする場合は、**インポート済み**の名前付きの ([受信トレイ] フォルダーおよびその他の既定のメールボックス フォルダーと同じレベル) のメールボックスのルート レベルに新しいフォルダーを pst ファイルがインポートされます。  <br/>  指定する場合は、 `/`、PST ファイル内の項目をユーザーの受信トレイ フォルダーに直接インポートされます。  <br/><br/>  指定する場合は、 `/<foldername>`、という名前のフォルダーにインポートされるアイテムの PST ファイルの*\<フォルダー名\>*。使用する場合など、 `/ImportedPst`、 **ImportedPst**をという名前のフォルダーにアイテムをインポートするとします。このフォルダーは、受信トレイ フォルダーと同じレベルでユーザーのメールボックスに配置されます。<br/><br/> **ヒント:** Pst ファイルをインポートするのには最適なフォルダーの場所を特定できるように、このパラメーターを実験するのには、いくつかのテスト バッチを実行することを検討してください。  <br/> |(空白)  <br/> または  <br/>  `/` <br/> または  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |この省略可能なパラメーターでは、ANSI のファイル形式の PST ファイルのインポートに使用するコード ページの数値を指定します。これらの言語が文字をエンコードするための 2 バイト文字セット (DBCS) を通常使用されるため、中国語、日本語、韓国語 (CJK) の組織から PST ファイルをインポートするため、このパラメーターが使用されます。メールボックス フォルダーの名前に DBCS を使用する言語の PST ファイルをインポートするのにはこのパラメーターを使用していない場合は、フォルダー名を多くの場合文字化けする、インポートした後。<br/><br/> このパラメーターを使用するのにはサポートされている値のリストは、[コード ページの識別子](https://go.microsoft.com/fwlink/p/?LinkId=328514)を参照してください。  <br/> <br/>**注:** 前に述べたように、これは、オプションのパラメーターと、CSV ファイルに含めるようにする必要はありません。または追加して値を 1 つまたは複数の行の空白のままにします。<br/> |(空白)  <br/> または  <br/>  `932`(日本語版 ANSI と OEM のコード ページの id です)  <br/> |
    | `SPFileContainer` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。   <br/> |該当なし  <br/> |
    | `SPManifestContainer` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。   <br/> |該当なし  <br/> |
    | `SPSiteUrl` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。   <br/> |該当なし  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>手順 5:Office 365 で PST インポート ジョブを作成する

次の手順では、Office 365 のサービスのインポートの PST のインポート ジョブを作成します。手順 4 で作成した PST インポート マッピング ファイルを提出する前に説明したようです。新しいジョブを作成したら、Office 365 PST ファイル内のデータを分析し、PST のインポート マッピング ファイルで指定されたメールボックスに実際にインポートを取得するデータをフィルター処理すること ([手順 6](#step-6-filter-data-and-start-the-pst-import-job)を参照してください)。
  
1. [https://protection.office.com](https://protection.office.com)し、組織の Office 365 の管理者アカウントの資格情報を使用してサインインします。 
    
2. セキュリティの左側のウィンドウで&amp;コンプライアンス センターでは、**データの管理**] をクリックし、し、[**インポート**] をクリックします。
    
3. [**インポート**] ページをクリックして![アイコンの追加](media/ITPro-EAC-AddIcon.gif)**新規ジョブをインポート**します。
    
    **注:** セキュリティの [**インポート**] ページにアクセスするための適切なアクセス許可を割り当てる必要がある&amp;新しいインポート ジョブを作成するコンプライアンス センターです。詳細については、**開始する前に**セクションを参照してください。 
    
4. PST インポート ジョブの名前を入力し、[**次へ**] をクリックします。小文字の英字、数字、ハイフン、およびアンダー スコアを使用します。大文字を使用して、またはの名前にスペースを追加できません。
    
5. **アップロードしたり、データを送付したいですか?** ページで、**データのアップロード**] をクリックし、[**次へ**] をクリックします。
    
    ![アップロードが、ネットワークのアップロードを作成するデータは、ジョブをインポート] をクリックします。](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. [**データのインポート**] ページで、手順 4 でをクリックして、**作業は自分のファイルをアップロードする****マッピング ファイルへのアクセス権がある**がチェック ボックスと、[**次へ**] をクリックします。
    
    ![手順 4 では、2 つのチェック ボックスをクリックします。](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. **マッピング ファイルの選択**] ページで、手順 4 で作成した PST インポート マッピング ファイルを送信するため**のマッピング ファイルを選択**ををクリックします。 
    
    ![インポート ジョブの作成した CSV ファイルを送信するのには [マップ ファイル] をクリックします。](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. **マップ ファイル名の**下にある CSV の名の後にファイルが表示されます、CSV ファイルのエラーをチェックする**検証する**] をクリックします。 
    
    ![CSV ファイルにエラーをチェックする検証] をクリックします。](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    CSV ファイルは、PST のインポート ジョブを作成するのには正常に検証するのには。ファイル名が緑に変化が正常に検証された後に注意してください。検証が失敗した場合は、**ログの表示**のリンクをクリックします。失敗したファイル内の各行についてエラー メッセージと、検証エラーのレポートが開かれます。 
    
9. PST のマッピング ファイルが正常に検証されると、条項および条件のドキュメントを参照し、チェック ボックスをクリックし、します。
    
10. **保存**ジョブを送信する] をクリックし、ジョブが正常に作成された後 [**閉じる**] をクリックします。 
    
    フライアウトはステータス ・ ページが表示され、**分析**の状態と、新しいインポート ジョブが [**インポート**] ページで、一覧に表示されます。 
    
11. [**更新**] をクリックして![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif)[**状態**] 列に表示されるステータス情報を更新します。分析が完了し、データをインポートする準備ができて、**分析を完了**するのには、ステータスが変更されます。
    
    マッピング ファイルに記載されている各 PST ファイルのインポート ジョブの状態についてのより詳細な情報が含まれている状態のポップアップ ページを表示するインポート ジョブをクリックすることができます。
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>手順 6: データをフィルター処理し、PST のインポート ジョブを開始します。

ステップ 5 では、インポート ジョブを作成したら、Office 365 は、アイテムと PST ファイルに含まれている別のメッセージの種類の保存期間を識別することによって (安全性とセキュリティで保護された形で) PST ファイル内のデータを分析します。分析が完了して、データをインポートする準備が、PST ファイルに含まれるすべてのデータをインポートするオプションがあるか、インポートされたデータを取得するかを制御するフィルターを設定することによってインポートされたデータをトリミングすることができます。
  
1. [**インポート**] ページで、セキュリティ&amp;コンプライアンス センターでは、手順 5 で作成したインポート ジョブの [ **Office 365 にインポートする準備ができました**] をクリックします。 
    
    ![作成したインポート ジョブの横にある Office 365 にインポートする準備ができました] をクリックします。](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    ページをその場は、PST ファイルの情報とインポート ジョブに関する他の情報が表示されます。
    
2. フライアウト] ページで、 **Office 365 にインポート**] をクリックします。
    
    **データにフィルターをかける**] ページが表示されます。PST ファイルのデータの保存期間に関する情報を含め、Office 365 による分析の結果データの分析が含まれています。この時点で、インポートするかが格納されるすべてのデータをインポートするデータをフィルター処理するためのオプションがあります。 
    
    ![PST ファイル内のデータをトリミングしたり、すべてのインポート](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. 次のいずれかを実行します。
    
    a. トリムするのにはインポートしたデータを**インポートする前にフィルター処理する**をクリックします。
    
    PST ファイル内のデータをフィルター処理とインポート ジョブを開始し、ステップ バイ ステップの詳細については、 [Office 365 に PST ファイルをインポートするときにデータをフィルター処理](filter-data-when-importing-pst-files.md)を参照してください。
    
    または
    
    b. PST ファイル内のすべてのデータをインポートするに**なしで、すべてをインポートする**] をクリックし、[**次へ**] をクリックします。
    
4. すべてのデータをインポートする] を選択した場合は、**データをインポートする**インポート ジョブを開始するをクリックします。 
    
    インポート ジョブのステータスは、[**インポート**] ページの表示です。クリックして![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif)[**状態**] 列に表示されるステータス情報を更新する**更新**をします。インポートする各 PST ファイルのステータス情報を表示するステータス フライアウトのページを表示するインポート ジョブをクリックします。 

## <a name="how-the-import-process-works"></a>インポート プロセスのしくみ
  
ネットワークのアップロード] オプションと、Office 365 のインポート サービスを使用するには、ユーザーのメールボックスを PST ファイルを一括インポートします。ネットワークのアップロードでは、マイクロソフトのクラウド内の一時記憶領域、PST ファイルをアップロードすることを意味します。Office 365 のインポート サービスは、ターゲット ユーザーのメールボックスにストレージ領域から PST ファイルをコピーします。
  
ここでは、図と Office 365 のメールボックスを PST ファイルをインポートするのにはネットワークのアップロード処理の説明です。
  
![ネットワークのワークフローは、Office 365 に PST ファイルをインポートするプロセスをアップロードします。](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **ダウンロード PST のインポート ツールおよびプライベート キーの Azure ストレージの場所**の最初のステップには、Azure AzCopy コマンド ライン ツールとマイクロソフトのクラウドでは、Azure ストレージの場所に PST ファイルをアップロードするために使用するアクセス キーをダウンロードします。これらの Office 365 のセキュリティで [**インポート**] ページから取得する&amp;コンプライアンス センターです。キー (セキュリティで保護されたアクセス (SA) の署名のキーと呼ばれるは、PST ファイルをアップロードするために必要なアクセス許可を持つプライベートと Azure ストレージの場所をセキュリティで保護します。このアクセス キーは、組織に固有で、マイクロソフトのクラウドにアップロードしたファイルは、PST ファイルに不正なアクセスを防ぐことがOffice 365 に PST ファイルをインポートするを必要としない独立した Azure サブスクリプションを持つ組織に注意してください。 
    
2. (手順 1 でダウンロード) AzCopy.exe ツールを使用してアップロードし、同じ地域の Microsoft データ センター内に存在する Azure ストレージの場所に PST ファイルを保存するには、 **Azure ストレージの場所に PST ファイルをアップロード**- 次のステップで、Office 365組織があります。それらをアップロードするには、Office 365 にインポートする PST ファイルをファイル共有またはファイル サーバーを組織内に存在する必要があります。
    
    Azure ストレージの場所にアップロードした後、PST ファイルの一覧を表示するときに実行するオプションの手順があることに注意してください。
    
3. **PST インポート マッピング ファイルを作成する**- Azure ストレージの場所に PST ファイルがアップロードした後、次の手順はユーザーのメールボックスを PST ファイル インポートされます PST ファイルができることに注意することを指定するコンマ区切り値 (CSV) ファイルを作成するには ユーザーのプライマリ メールボックスまたはアーカイブ メールボックスにインポートされます。PST ファイルをインポートするのに CSV ファイルで、Office 365 にインポート サービスは情報を使用します。
    
4. セキュリティの [**インポート**] ページで、PST のインポート ジョブを作成するのには、 **pst ファイルを作成するジョブをインポートする**ために次の手順&amp;コンプライアンス センターおよび前の手順で作成した PST のインポート マッピング ファイルを送信します。インポート ジョブを作成したら、Office 365 PST ファイル内のデータを分析し、どのようなデータは実際にはマッピング ファイルには、PST のインポートで指定したメールボックスにインポートされた取得を制御するフィルターを設定すること。 
    
5. **フィルターのメールボックスにインポートされる PST のデータ**のインポート ジョブが作成され、開始した後、Office 365 を分析し、PST ファイル内のデータ (安全かつ確実に) 項目と PST ファイルに含まれている別のメッセージの種類の保存期間を識別することによって.分析が完了して、データをインポートする準備が、PST ファイルに含まれるすべてのデータをインポートするオプションがあるか、インポートされたデータを取得するかを制御するフィルターを設定することによってインポートされたデータをトリミングすることができます。
    
6. **PST のインポート ジョブを開始する**-インポート ジョブが開始された後、Office 365 情報を使用して、マッピング ファイルには、PST のインポートで彼は Azure ストレージの場所からユーザーのメールボックスを Pst ファイルをインポートするのには。[**インポート**] ページで、セキュリティなどについては各 PST ファイルをインポートするインポート ジョブの状態に関する情報が表示されます&amp;コンプライアンス センターです。インポート ジョブが完了したら、ジョブのステータスが**完了**に設定します。
  
## <a name="more-information"></a>詳細情報

- 理由 PST ファイルを Office 365 にインポートしますか。
    
  - Office 365 組織のメッセージング データのアーカイブをインポートする場合に便利です。
    
  - データがクラウドに格納されるので、ユーザーはあらゆるデバイスからデータを利用できます。
    
  - により、インポートする PST ファイルからデータを Office 365 のコンプライアンス機能を適用することで、組織のコンプライアンスのニーズに対応ができます。これが含まれています。
    
  - [アーカイブ メールボックス](enable-archive-mailboxes.md)とユーザーにインポートしたデータを格納する追加のメールボックスの記憶域を提供する[アーカイブの自動拡張](enable-unlimited-archiving.md)を有効にします。 
    
  - [証拠保全](https://go.microsoft.com/fwlink/?linkid=856286)をインポートしたデータを保持するには、メールボックスを配置することです。 
    
  - マイクロソフトの[電子的証拠開示のツール](search-for-content.md)を使用して、インポートしたデータを検索します。 
    
  - [Office 365 の保存ポリシー](retention-policies.md)を使用して、インポートしたデータの保存期間、および保存期間が終了した後に実行するには、どのようなアクションを制御します。 
    
  - [Office 365 の監査ログ](search-the-audit-log-in-security-and-compliance.md)をインポートしたデータに影響を及ぼすメールボックスに関連するイベントを検索します。 
    
  - コンプライアンスのためのデータをアーカイブするのには[アクティブでないメールボックス](create-and-manage-inactive-mailboxes.md)にデータをインポートしています。 
    
  - [データ損失防止ポリシー](data-loss-prevention-policies.md)を使用して、機密性の高いデータが組織の外部にリークが発生するを防ぐためです。 
  
- ここでは、手順 1 で取得した共有アクセス署名 (SA) の URL の例です。この例では、Office 365 に PST ファイルをアップロードする AzCopy.exe ツールを実行するコマンドの構文も含まれています。パスワードやその他のセキュリティに関連する情報を保護するように、SAS の URL を保護するために対策を講じていることを確認します。

    ```
    SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D

    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y

    EXAMPLES

    This example uploads PST files to the root of the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    
    This example uploads PST files to a subfolder named PSTFiles  in the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
``

- As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RetentionHoldEnabled*  property is set to  `True` so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold: 
    
    - After a certain period of time, you can turn off the retention hold by running the  `Set-Mailbox -RetentionHoldEnabled $false` command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
   - You can configure the retention hold so that it's turned off on some date in the future. You do this by running the  `Set-Mailbox -EndDateForRetentionHold <date>` command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. In this scenario, you would leave the  *RetentionHoldEnabled*  property set to  *True*  . For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
   - You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    
