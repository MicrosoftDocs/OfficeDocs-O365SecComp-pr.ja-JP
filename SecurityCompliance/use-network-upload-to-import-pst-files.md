---
title: ネットワーク アップロードを使用して、組織の PST ファイルを Office 365 にインポートする
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: '管理者向け: ネットワーク アップロードを使用して、複数の PST ファイルを Office 365 のユーザー メールボックスに一括インポートする方法について説明します。'
ms.openlocfilehash: bd15216df69e003a5aaddb2ec21ede4da5c5c312
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854821"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a>ネットワーク アップロードを使用して、組織の PST ファイルを Office 365 にインポートする

> [!NOTE]
> この記事は管理者向けです。 自分のメールボックスに PST ファイルをインポートしようとしていますか? 「[Outlook .pst ファイルからメール、連絡先、予定表をインポートする](https://go.microsoft.com/fwlink/p/?LinkID=785075)」を参照してください。
  
ネットワーク アップロードを使用して、複数の PST ファイルを Office 365 のメールボックスに一括インポートするために必要なステップ バイ ステップによる手順を以下に示します。 ネットワーク アップロードを使用した Office 365 メールボックスへの PST ファイルの一括インポートについてよく寄せられる質問については、「[FAQs for using network upload to import PST files](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files)」 (ネットワーク アップロードを使用して PST ファイルをインポートすることついてよく寄せられる質問) を参照してください。
  
[手順 1: SAS URL をコピーして、Azure AzCopy をインストールする](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[手順 2: Office 365 に PST ファイルをアップロードする](#step-2-upload-your-pst-files-to-office-365)

[(省略可能) 手順 3: Office 365 にアップロードされた PST ファイルのリストを表示する](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[手順 4: PST インポート マッピング ファイルを作成する](#step-4-create-the-pst-import-mapping-file)

[手順 5:Office 365 で PST インポート ジョブを作成する](#step-5-create-a-pst-import-job-in-office-365)

[手順 6:データをフィルター処理して、PST インポート ジョブを開始する](#step-6-filter-data-and-start-the-pst-import-job)

手順 1 は、PST ファイルを Office 365 メールボックスにインポートするために、1 回のみ実行する必要があることに注意してください。 これらの手順を実行した後、 PST ファイルのバッチのアップロードとインポートを行うたびに、手順 2 から手順 6 を実行します。

## <a name="before-you-begin"></a>始める前に
  
- PST ファイルを Office 365 メールボックスにインポートするには、Exchange Online で Mailbox Import Export の役割が割り当てられている必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は "Organization Management/組織の管理" 役割グループに追加できます。 または、新しい役割グループを作成し、"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割を割り当て、ユーザー自身をメンバーとして追加することができます。 詳細については、「[役割グループの管理](https://go.microsoft.com/fwlink/p/?LinkId=730688)」の「役割グループに役割を追加する」または「役割グループを作成します」のセクションを参照してください。
    
    さらに、セキュリティ/コンプライアンス センターでインポート ジョブを作成するには、次のいずれかを満たす必要があります。
    
  - Exchange Online で Mail Recipients の役割が割り当てられている必要があります。 既定では、この役割は Organization Management 役割グループと Recipient Management 役割グループに割り当てられます。
    
    または
    
  - Office 365 組織の全体の管理者である必要があります。
    
  > [!TIP]
    > PST ファイルを Office 365 にインポートするための新しい役割グループを Exchange Online で作成することを検討します。 PST ファイルをインポートするのに必要な最小レベルの権限では、新しい役割グループに [メールボックス インポート エクスポート] 役割および [メール受信者] 役割を割り当て、メンバーを追加します。 
  
- PST ファイルを Office 365 にインポートするためにサポートされている方法は、このトピックで説明されているように、Azure AzCopy ツールを使用することのみです。 Azure Storage Explorer を使用して、PST ファイルを Azure ストレージ領域に直接アップロードすることはできません。
    
- Office 365 にインポートする PST ファイルは、組織内のファイル サーバーまたは共有フォルダーに保存する必要があります。 手順 2 では、Azure AzCopy ツールを実行して、このファイル サーバーや共有フォルダーに保存されている PST ファイルを Office 365 にアップロードします。
    
- この手順では、アクセス キーを含む URL をコピーして保存します。 この情報は、PST ファイルをアップロードするために手順 2 で、Office 365 にアップロードされた PST ファイルのリストを表示する場合に手順 3 で使用されます。 パスワードや他のセキュリティ関連の情報を保護するのと同じように、この URL を保護する予防措置を講じる必要があります。 たとえば、この URL をパスワードで保護された Microsoft Word 文書に保存したり、暗号化された USB ドライブに保存したりします。 この URL とキーの組み合わせの例については、「[詳細情報](#more-information)」セクションを参照してください。 
    
- PST ファイルを Office 365 の非アクティブなメールボックスにインポートできます。 PST インポート マッピング ファイルの `Mailbox` パラメーターで非アクティブなメールボックスの GUID を指定して、この操作を行います。 詳細については、このトピックの「**手順**」タブの手順 4 を参照してください。 
    
- Exchange ハイブリッド展開では、オンプレミスのプライマリ メールボックスを持つユーザーのために、PST ファイルをクラウド ベースのアーカイブ メールボックスにインポートすることができます。 PST インポート マッピング ファイルに次を指定して、この操作を行います。
    
  - `Mailbox` パラメーターに、ユーザーのオンプレミス メールボックス用のメール アドレスを指定します。 
    
  - `IsArchive` パラメーターに、**TRUE** 値を指定します。 
    
    詳細については、[手順 4](#step-4-create-the-pst-import-mapping-file) を参照してください。 
    
- PST ファイルが Office 365 メールボックスにインポートされると、メールボックスのアイテム保持ホールド設定が無期限でオンになります。 つまり、メールボックスに割り当てられたアイテム保持ポリシーは、アイテム保持ホールドをオフにするか、またはホールドをオフにする日付を設定するまで処理されません。 このようにした理由は次のとおりです。 メールボックスにインポートされたメッセージは、古くなると完全に削除 (パージ) される可能性があります。これは、メッセージの保持期限がメールボックスに対して構成されたアイテム保持設定に基づいて決められるためです。 メールボックスに対してアイテム保持ホールドが設定されると、メールボックスの所有者は、新たにインポートされたメッセージを管理する時間、またはメールボックスのアイテム保持設定を変更する時間を確保できます。 アイテム保持ホールドの管理に関する推奨事項については、このトピックの「**詳細情報**」セクションを参照してください。 
    
- 既定では、Office 365 メールボックスで受信できるメッセージの最大サイズは、35 MB です。 これは、メールボックスの *MaxReceiveSize* プロパティの既定値が 35 MB に設定されているためです。 ただし、Office 365 のメッセージ受信最大サイズの上限は 150 MB です。 そのため、35 MB より大きいアイテムを含む PST ファイルをインポートすると、Office 365 インポート サービスにより、対象メールボックスの *MaxReceiveSize* プロパティの値が 150 MB に自動的に変更されます。 これにより、最大 150 MB のメッセージをユーザーのメールボックスにインポートできます。 
    
    > [!TIP]
    > メッセージ受信サイズを識別するには、Exchange Online PowerShell で次のコマンドを実行します: `Get-Mailbox <user mailbox> | FL MaxReceiveSize` 

## <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a>手順 1: SAS URL をコピーして、Azure AzCopy をインストールする

最初の手順では、Azure AzCopy ツールをダウンロードしてインストールします。これは、手順 2 で PST ファイルを Office 365 にアップロードするために実行するツールです。 また、組織の SAS URL もコピーします。 この URL は、組織の Microsoft クラウドにある Azure ストレージの場所のネットワーク URL と、Shared Access Signature (SAS) キーの組み合わせです。 このキーでは、Azure ストレージの場所に PST ファイルをアップロードするために必要な権限が与えられます。 必ず SAS URL を保護するための予防措置を講じてください。 これらは組織に固有で、手順 2 で使用されます。

> [!IMPORTANT]
> ネットワーク アップロードの方法を使用して PST ファイルをインポートするには、次の手順 6b でダウンロードできる Azure AzCopy のバージョンを使用することをお勧めします。
  
1. [ https://protection.office.com ](https://protection.office.com) に移動し、Office 365 組織の管理者アカウントの資格情報を使用してサインインします。 
    
2. セキュリティ/コンプライアンス センターの左のウィンドウで、[**データ ガバナンス**] \> [**インポート**] の順にクリックします。
    
    > [!NOTE]
    > セキュリティ/コンプライアンス センターの [**インポート**] ページにアクセスするには、適切なアクセス許可の割り当てが必要です。 詳細については、「**はじめに**」セクションを参照してください。 
    
3. [**インポート**] ページで、[![追加](media/ITPro-EAC-AddIcon.gif)] アイコン > [**新規インポート ジョブ**] を順にクリックします。
    
    ジョブのインポート ウィザードが表示されます。
    
4. PST インポート ジョブの名前を入力し、[**次へ**] をクリックします。 小文字の英字、数字、ハイフン、およびアンダー スコアを使用します。 大文字を使用したり、名前にスペースを含めたりすることはできません。
    
5. [**データをアップロードまたは配送しますか?**] ページで、[**データをアップロードする**] をクリックし、[**次へ**] をクリックします。
    
    ![[データをアップロードする] をクリックして、ネットワーク アップロードのインポート ジョブを作成する](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. [**データのインポート**] ページで、次の 2 つの操作を行います。 
    
    ![SAS URL をコピーし、[データのインポート] ページで Azure AzCopy ツールをダウンロードする](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    a.  手順 2 で、[**ネットワーク アップロード SAS URL を表示する**] をクリックします。 SAS URL が表示されたら、[**クリップボードにコピー**] をクリックしてから、ファイルに貼り付けて保存し、後でアクセスできるようにします。
    
    b.  手順 3 で、[**Azure AzCopy のダウンロード**] をクリックし、Azure AzCopy ツールをダウンロードしてインストールします。 ポップアップ ウィンドウで、[**実行**] をクリックして、AzCopy をインストールします。 
    
> [!NOTE]
> [**データのインポート**] ページを開いたままにしておくか (もう一度 SAS URL をコピーする必要がある場合)、[**キャンセル**] をクリックして閉じることができます。 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>手順 2: Office 365 に PST ファイルをアップロードする

これで、AzCopy.exe ツールを使って Office 365 に PST ファイルをアップロードする準備が整いました。 このツールで、PST ファイルを Microsoft クラウド内の Azure ストレージの場所にアップロードして保存します。 前述したように、PST ファイルをアップロードする Azure ストレージの場所は、Office 365 組織があるのと同じ地域の Microsoft データ センターにあります。 この手順を完了するには、PST ファイルを組織内のファイル共有やファイル サーバーに配置する必要があります。 これは、次の手順でソース ディレクトリと呼ばれます。 AzCopy ツールを実行するたびに、別のソース ディレクトリを指定することができます。 
  
1. ローカル コンピューターでコマンド プロンプトを開きます。
    
2. 手順 1 で AzCopy.exe ツールをインストールしたディレクトリに移動します。 既定の場所にツールをインストールした場合は、`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy` に移動します。
    
3. 次のコマンドを実行して、PST ファイルを Office 365 にアップロードします。

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    > [!IMPORTANT] 
    > 前のコマンドでは、ソースの場所としてディレクトリを指定する必要があります。個々の PST ファイルを指定することはできません。 ソース ディレクトリにあるすべての PST ファイルがアップロードされます。
 
    次の表は、AzCopy.exe のパラメーターとそれに必要な値を説明したものです。 前の手順で取得した情報は、これらのパラメーターの値に使用されます。
    
    |**パラメーター**|**Description**|**例**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |Office 365 にアップロードする PST ファイルを含む組織内のソース ディレクトリを指定します。  <br/> このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |手順 1 で取得した SAS URL を指定します。  <br/> このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> **ヒント:** (省略可能) PST ファイルをアップロードする Azure ストレージの場所にサブフォルダーを指定できます。 SAS URL で ("ingestiondata" の後に) サブフォルダーの場所を追加して、この操作を行います。 最初の例では、サブフォルダーを指定しません。つまり、PST ファイルは、Azure ストレージの場所のルート (*ingestiondata* という名前) にアップロードされます。 2 つ目の例では、PST ファイルを Azure ストレージの場所のルートにあるサブフォルダー (*PSTFiles* という名前) にアップロードします。  <br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> または  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |ログ ファイルに詳細な状態メッセージを出力します。 既定では、詳細ログ ファイルは AzCopyVerbose.log という名前が付けられ、%localappdata%\microsoft\azure\azcopy に作成されます。 このオプションで既存のファイルの場所を指定する場合、詳細ログがそのファイルに追加されます。  <br/> このパラメーターの値は必ず二重引用符 (" ") で囲むようにしてください。  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |この省略可能なスイッチによって再帰モードが指定され、AzCopy ツールが `/Source:` パラメーターで指定されるソース ディレクトリのサブフォルダーにある PST ファイルをコピーするようになります。  <br/> **注: **このスイッチを含めると、サブフォルダー内の PST ファイルには、アップロード後、Azure ストレージの場所に別のファイルのパス名が指定されます。 手順 4 で作成した CSV ファイルの正確なファイルのパス名を指定する必要があります。  <br/> | `/S` <br/> |
    | `/Y` <br/> |この必須スイッチにより、Azure ストレージの場所に PST ファイルをアップロードするときに、書き込み専用の SAS トークンを使用できます。 手順 1 で取得 (および `/Dest:` パラメーターで指定) した SAS URL は書き込み専用の SAS URL であるため、このスイッチを含める必要があります。 書き込み専用の SAS URL を使用しても、Azure Storage Explorer を使用して Azure ストレージの場所にアップロードされた PST ファイルのリストを表示できなくなることはありません。  <br/> | `/Y` <br/> |
   
各パラメーターの実際の値を使う AzCopy.exe ツールの構文の例を以下に示します。
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

コマンドを実行すると、PST ファイルのアップロードの進行状況を示す状態メッセージが表示されます。 最終的なステータス メッセージには、正常にアップロードされたファイルの合計数が表示されます。

> [!TIP]
> AzCopy.exe コマンドを実行し、すべてのパラメーターが正しいことを確認したら、手順 1 で取得した情報をコピーしたのと同じ (セキュリティで保護された) ファイルにコマンド ライン構文のコピーを保存します。 これで、AzCopy.exe ツールを実行して、PST ファイルを Office 365 にアップロードするたびに、コマンド プロンプトにこのコマンドをコピーして貼り付けることができます。 変更する必要のある値は、`/Source:` パラメーターの値のみです。 これは、PST ファイルがあるソース ディレクトリによって異なります。

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>(省略可能) 手順 3: Office 365 にアップロードされた PST ファイルのリストを表示する

オプションの手順として、Azure Storage Explorer (無料のオープン ソース ツール) をインストールして使用し、Azure BLOB にアップロードした PST ファイルのリストを表示できます。 これを行う 2 つの理由があります。
  
- 共有フォルダーまたは組織内のファイル サーバーから PST ファイルが Azure BLOB に正常にアップロードされたことを確認します。
    
- 各 PST ファイルのファイル名 (および含めている場合はサブフォルダーのパス名) が Azure BLOB にアップロードされたことを確認するためです。 次の手順で PST マッピング ファイルを作成する際、各 PST ファイルに対しファイル名とフォルダーのパス名の両方を指定する必要があるため、この機能は非常に便利です。 これらの名前を確認すると、PST マッピング ファイル内の潜在的なエラーを削減できます。
    
Microsoft Azure Storage Explorer はプレビュー中です。 
  
> [!IMPORTANT]
> Azure Storage Explorer で PST ファイルをアップロードまたは変更することはできません。 PST ファイルを Office 365 にインポートするには、AzCopy を使用する方法のみがサポートされています。 また、Azure BLOB にアップロードした PST ファイルを削除することはできません。 PST ファイルを削除しようとすると、必要なアクセス許可がないというエラーが表示されます。 なお、すべての PST ファイルは Azure 記憶域から自動的に削除されます。 進捗中のインポート ジョブがない場合、一番新しいインポート ジョブの作成から 30 日後に **ingestiondata** コンテナーのすべての PST ファイルが削除されます。
  
Azure Storage Explorer をインストールし、Azure 記憶域に接続する方法は以下のとおりです。
  
1. [Microsoft Azure Storage Explorer ツール](https://go.microsoft.com/fwlink/p/?LinkId=544842)をダウンロードしてインストールします。
    
2. Microsoft Azure Storage Explorer を起動し、左側のウィンドウで [**ストレージ アカウント**] を右クリックして、[**Azure ストレージに接続する**] をクリックします。
    
    ![[ストレージ アカウント] を右クリックし、[Azure Storage への接続] をクリックする](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. [**共有アクセス署名 (SAS) URI または接続文字列を使用**] をクリックし、[**次へ**] をクリックします。
    
4. [**SAS URI の使用**] をクリックし、[**URI**] の下にあるボックスに、手順 1 で取得した SAS URI を貼り付けて、[**次へ**] をクリックします。
    
5. [**接続の概要**] ページで、接続情報を確認して、[**接続**] をクリックします。
    
    **ingestiondata** コンテナーが開き、手順 2 でアップロードした PST ファイルが含まれています。 **ingestiondata** コンテナーは、[**ストレージ アカウント**] \> **(SAS 接続サービス)** \> [**BLOB コンテナー**] の下にあります。 
    
    ![Azure Storage Explorer には、アップロードした PST ファイルのリストが表示される](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. Microsoft Azure Storage Explorer の使用が完了したら、**ingestiondata** を右クリックし、[**デタッチ**] をクリックすると Azure 記憶域から切断されます。 そうしないと、次に接続しようとするときにエラーが表示されます。 
    
    ![ingestiondata を右クリックして [デタッチ] をクリックし、Azure 記憶域から切断する](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>手順 4: PST インポート マッピング ファイルを作成する

PST ファイルを Office 365 組織の Azure ストレージの場所にアップロードしたら、次は、コンマ区切り値 (CSV) のファイルを作成して、PST ファイルのインポート先のユーザー メールボックスを指定します。 PST インポート ジョブを作成する場合は、次の手順でこの CSV ファイルを送信します。
  
1. [PST インポート マッピング ファイルのコピーをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=544717)。
    
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
    CSV ファイルの先頭行やヘッダー行には、PST ファイルをユーザー メールボックスにインポートするために PST インポート サービスで使うパラメーターが一覧表示されます。 各パラメーター名はコンマで区切られています。 ヘッダー行の下の各行は、特定のメールボックスに PST ファイルをインポートするためのパラメーター値を表します。 ユーザー メールボックスにインポートする PST ファイルごとに行が必要になります。 必ずマッピング ファイル内のプレースホルダーのデータを実際のデータに置き換えてください。

   **注: **SharePoint パラメーターなど、ヘッダー行は何も変更しないでください。これらは PST インポートの処理中、無視されます。 

 3. 次の表の情報を使って、必要な情報を含む CSV ファイルを作成します。


    |**パラメーター**|**Description**|**例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |データのインポート先の Office 365 サービスを指定します。 ユーザー メールボックスに PST ファイルをインポートするには、`Exchange` を使います。  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |手順 2 で PST ファイルをアップロードした Azure ストレージの場所でフォルダーの場所を指定します。   <br/> 手順 2 の `/Dest:` パラメーターの SAS URL に省略可能なサブフォルダー名を含めなかった場合は、CSV ファイルのこのパラメーターを空白のままにしておきます。 サブフォルダー名を含めている場合は、このパラメーターでそれを指定します (2 番目の例を参照)。 このパラメーターの値には、大文字と小文字の区別があります。  <br/> どちらの場合でも、`FilePath` パラメーターの値に "ingestiondata" を含め*ない*でください。  <br/><br/> **重要: **手順 2 で `/Dest:` パラメーターに SAS URL の省略可能なサブフォルダー名を含めた場合、ファイル パス名の大文字小文字はそのとき使用したものと同じである必要があります。 たとえば、手順 2 でサブフォルダー名として `PSTFiles` を使用した場合、CSV ファイル内の `FilePath` パラメーターに `pstfiles` を使用すると、PST ファイルのインポートは失敗します。 必ず、両方のインスタンスの大文字と小文字を同じにしてください。  <br/> |(空白のまま)  <br/> または  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |ユーザー メールボックスにインポートする PST ファイルの名前を指定します。 このパラメーターの値には、大文字と小文字の区別があります。  <br/> <br/>**重要: **CSV ファイル内の PST ファイル名の大文字と小文字は、手順 2 で Azure ストレージの場所にアップロードした PST ファイルの場合と同じである必要があります。 たとえば、CSV ファイル内の `Name` パラメーターでは `annb.pst` を使用しているが、実際の PST ファイルの名前は `AnnB.pst` である場合、その PST ファイルのインポートは失敗します。 CSV ファイル内の PST の名前の大文字小文字は、実際の PST ファイルの場合と同じである必要があります。  <br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |PST ファイルのインポート先になるメールボックスのメール アドレスを指定します。 PST インポート サービスは、PST ファイルのパブリック フォルダーへのインポートをサポートしていないため、パブリック フォルダーの指定はできないことにご注意ください。  <br/> PST ファイルを非アクティブなメールボックスにインポートするには、このパラメーターにメールボックスの GUID を指定する必要があります。 この GUID を取得するには、Exchange Online で次の PowerShell コマンドを実行します: `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**注: **場合によっては、1 つのメール アドレスに対して複数のメールボックスが存在することがあります。この場合、1 つのメールボックスがアクティブ状態となり、他のメールボックスは論理的に削除された (非アクティブな) 状態となります。 このような状況で、PST ファイルのインポート先のメールボックスを一意に識別するには、メールボックスの GUID を指定する必要があります。 アクティブなメールボックスの GUID を取得するには、次の PowerShell コマンドを実行します: `Get-Mailbox <identity of active mailbox> | FL Guid` 論理的に削除された (非アクティブな) メールボックスの GUID を取得するには、次のコマンドを実行します: `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`  <br/> | `annb@contoso.onmicrosoft.com` <br/> または  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | PST ファイルをユーザーのアーカイブ メールボックスにインポートするかどうかを指定します。 次のような 2 つの選択肢があります。  <br/><br/>**FALSE** - PST ファイルをユーザーのプライマリ メールボックスにインポートします。  <br/> **TRUE** - PST ファイルをユーザーのアーカイブ メールボックスにインポートします。 これは、[ユーザーのアーカイブ メールボックスが有効化されている](enable-archive-mailboxes.md)ことが前提です。 <br/><br/>このパラメーターが `TRUE` に設定されているときに、ユーザーのアーカイブ メールボックスが有効化されていない場合は、そのユーザーのインポートが失敗します。 アーカイブが有効化されていないにもかかわらずこのプロパティが `TRUE` に設定されたことが原因で、あるユーザーのインポートが失敗しても、そのインポート ジョブ内の他のユーザーが影響を受けることはありません。  <br/>  このパラメーターを空白のままにすると、PST ファイルはユーザーのプライマリ メールボックスにインポートされます。  <br/> <br/>**注:** PST ファイルをクラウド ベースのアーカイブ メールボックスにインポートするときに、そのユーザーのプライマリ メールボックスがオンプレミスの場合は、このパラメーターに対して `TRUE` を指定し、そのユーザーのオンプレミスのメールボックスのメール アドレスを `Mailbox` パラメーターで指定してください。  <br/> | `FALSE` <br/> または  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | PST ファイルをインポートするメールボックス フォルダーを指定します。  <br/>  このパラメーターを空白のままにすると、PST ファイルはメールボックスのルート レベル (受信トレイ フォルダーや他の既定のメールボックス フォルダーと同じレベル) に配置される**インポート済み**という新しいフォルダーにインポートされます。  <br/>  `/` を指定すると、PST ファイルのアイテムはユーザーの受信トレイ フォルダーに直接インポートされます。  <br/><br/>  `/<foldername>` を指定すると、PST ファイルのアイテムは * \<foldername\> * というフォルダーにインポートされます。 たとえば、`/ImportedPst` を使用した場合、アイテムは **ImportedPst** というフォルダーにインポートされます。 このフォルダーは、ユーザーのメールボックスの受信トレイ フォルダーと同じレベルにあります。  <br/><br/> **ヒント: **PST ファイルのインポート先に最適なフォルダーの場所を決定できるよう、このパラメーターを試すテスト バッチをいくつか実行することを検討してください。   <br/> |(空白)  <br/> または  <br/>  `/` <br/> または  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |この省略可能なパラメーターでは、PST ファイルを ANSI ファイル形式でインポートする場合に使用するコード ページの数値を指定します。 このパラメーターは、中国語、日本語、韓国語 (CJK) を使用する組織から PST ファイルをインポートする場合に使用します。通常、これらの言語は、文字エンコードのために 2 バイト文字セット (DBCS) を使用するからです。 メールボックス フォルダー名に DBCS が使用されている言語については、PST ファイルのインポートの際にこのパラメーターを使用しないと、多くの場合、インポート後にフォルダー名の文字化けが発生します。  <br/><br/> このパラメーターに使用できる値のリストについては、「[Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514)」 (コード ページ識別子) を参照してください。  <br/> <br/>**注: **前述したように、これは省略可能なパラメーターであり、CSV ファイルに含めなくてもかまいません。 または、このパラメーターを含め、1 つまたは複数の行について値を空白のままにしておくこともできます。  <br/> |(空白のまま)  <br/> または  <br/>  `932` (ANSI/OEM 日本語のコード ページ ID)  <br/> |
    | `SPFileContainer` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。  <br/> |該当なし  <br/> |
    | `SPManifestContainer` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。  <br/> |該当なし  <br/> |
    | `SPSiteUrl` <br/> |PST インポートの場合は、このパラメーターを空白のままにします。  <br/> |該当なし  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>手順 5: Office 365 で PST インポート ジョブを作成する

次の手順では、Office 365 のインポート サービスで PST インポート ジョブを作成します。 前述したように、手順 4 で作成した PST インポートのマッピング ファイルを送信します。 新しいジョブを作成した後に、Office 365 は PST ファイル内のデータを分析し、実際に PST インポート マッピング ファイル ([手順 6](#step-6-filter-data-and-start-the-pst-import-job) を参照) で指定したメールボックスにインポートするデータをフィルター処理する機会を提供します。
  
1. [ https://protection.office.com ](https://protection.office.com) に移動し、Office 365 組織の管理者アカウントの資格情報を使用してサインインします。 
    
2. セキュリティ/コンプライアンス センターの左のウィンドウで、[**データ ガバナンス**] をクリックしてから、[**インポート**] をクリックします。
    
3. [**インポート**] ページで、[![追加](media/ITPro-EAC-AddIcon.gif)] アイコン > [**新規インポート ジョブ**] を順にクリックします。
    
    **注: **セキュリティ/コンプライアンス センターの [**インポート**] ページにアクセスして新しいインポート ジョブを作成するには、適切なアクセス許可の割り当てが必要です。 詳細については、「**はじめに**」セクションを参照してください。 
    
4. PST インポート ジョブの名前を入力し、[**次へ**] をクリックします。 小文字の英字、数字、ハイフン、およびアンダー スコアを使用します。 大文字を使用したり、名前にスペースを含めたりすることはできません。
    
5. [**データをアップロードまたは配送しますか?**] ページで、[**データをアップロードする**] をクリックし、[**次へ**] をクリックします。
    
    ![[データをアップロードする] をクリックして、ネットワーク アップロードのインポート ジョブを作成する](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. 手順 4 の [**データのインポート**] ページで、[**ファイルをアップロードしました**] と [**マッピング ファイルにアクセスできます**] チェック ボックスを選択して、[**次へ**] をクリックします。
    
    ![手順 4 で 2 つのチェック ボックスをクリックする](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. [**マッピング ファイルの選択**] ページで、[**マッピング ファイルの選択**] をクリックし、手順 4 で作成した PST インポート マッピング ファイルを送信します。 
    
    ![[マッピング ファイルの選択] をクリックして、インポート ジョブのために作成した CSV ファイルを送信する](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. CSV ファイルの名前が [**マッピング ファイル名**] に表示されたら、[**検証**] をクリックし、CSV ファイルでエラーを確認します。 
    
    ![[検証] をクリックして CSV ファイルでエラーを確認する](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    PST インポート ジョブを作成するには、CSV ファイルが正常に検証される必要があります。 正常に検証された後にファイル名が緑色に変更されます。 検証が失敗した場合は、[**ログの表示**] リンクをクリックします。 検証エラー レポート開き、失敗したファイルの各行にエラー メッセージが表示されています。 
    
9. PST マッピング ファイルが正常に検証された後に、利用条件を読み、チェック ボックスをクリックします。
    
10. [**保存**] をクリックしてジョブを送信し、ジョブが正常に作成されたら [**閉じる**] をクリックします。 
    
    [**分析の進行中**] のステータスを示すステータス フライアウト ページが表示され、新しいインポート ジョブが [**インポート**] ページのリストに表示されます。 
    
11. [**更新**] ![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif) をクリックして、[**ステータス**] 列に表示されるステータス情報を更新します。 分析が完了し、データをインポートする準備ができると、ステータスが [**分析完了**] に変わります。
    
    インポート ジョブをクリックしてステータス フライアウト ページを表示することができます。このページにはマッピング ファイルにリストされている各 PST ファイルのステータスなどのインポート ジョブに関する詳細が表示されます。
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>手順 6: データをフィルター処理して、PST インポート ジョブを開始する

手順 5 でインポート ジョブを作成した後、Office 365 は、セキュリティで保護された安全な方法で PST ファイル内のデータを分析します。具体的には、アイテムの経過時間と、PST ファイルに含まれるさまざまなメッセージの種類を識別します。 分析が完了し、データをインポートする準備ができたら、PST ファイルに含まれるすべてのデータをインポートするか、インポートするデータをトリミングするかを選ぶことができます。データをトリミングする場合は、インポートするデータを制御するフィルターを設定します。
  
1. セキュリティ/コンプライアンス センターの [**インポート**] ページで、手順 5 で作成したインポート ジョブの [**Office 365 へのインポートの準備完了**] をクリックします。 
    
    ![作成したインポート ジョブの横にある [Office 365 にインポートする準備ができました] をクリックする](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    PST ファイルに関する情報とインポート ジョブに関するその他の情報を示すポップアップ ページが表示されます。
    
2. ポップアップ ページで、[**Office 365 へのインポート**] をクリックします。
    
    [**データのフィルター処理**] ページが表示されます。 ここには、データの使用期間に関する情報など、Office 365 によって実行された PST ファイルの分析の結果のデータ情報が含まれます。 この時点で、インポートされるデータにフィルター処理を適用するか、すべてのデータをそのままインポートするかを選択できます。 
    
    ![PST ファイルのデータをトリミングしたり、そのすべてをインポートしたりすることができる](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. 次のいずれかの操作を行います。
    
    a.  インポートするデータをトリミングする場合は [**はい、インポートする前にフィルター処理します**] をクリックします。
    
    PST ファイル内のデータをフィルター処理してインポート ジョブを開始する手順の詳細については、「[Office 365 に PST ファイルをインポートするときにデータをフィルター処理する](filter-data-when-importing-pst-files.md)」を参照してください。
    
    または
    
    b.  PST ファイル内のすべてのデータをインポートするには、[**いいえ、すべてのアイテムをインポートします**] をクリックして、[**次へ**] をクリックします。
    
4. すべてのデータをインポートする場合は、[**データのインポート**] をクリックしてインポート ジョブを開始します。 
    
    インポート ジョブのステータスが [**インポート**] ページに表示されます。 ![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif) [**更新**] をクリックして、[**ステータス**] 列に表示されるステータス情報を更新します。 インポート ジョブをクリックするとステータス フライアウト ページが表示され、インポートされている各 PST ファイルに関するステータス情報が表示されます。 

## <a name="how-the-import-process-works"></a>インポート プロセスの流れ
  
ネットワークのアップロード オプションおよび Office 365 のインポート サービスを使用して、ユーザーのメールボックスに PST ファイルを一括インポートすることができます。 ネットワーク アップロードとは、Microsoft クラウドの一時的な記憶域に PST ファイルをアップロードすることを意味します。 その後、Office 365 インポート サービスが記憶域からユーザーのメールボックスに PST ファイルをコピーします。
  
ここでは、PST ファイルを Office 365 のメールボックスにインポートするためのネットワーク アップロード処理の図と説明を示します。
  
![PST ファイルを Office 365 にインポートするためのネットワーク アップロード処理のワークフロー](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **PST インポート ツールとキーをプライベート Azure ストレージの場所にダウンロードする** - 最初の手順は、PST ファイルを Microsoft クラウドの Azure ストレージの場所にアップロードするために使用される Azure AzCopy コマンドライン ツールとアクセス キーをダウンロードすることです。 これらは、セキュリティ/コンプライアンス センター の [**インポート**] ページで取得します。 このキー (Secure Access Signature (SAS) キーと呼ばれます) は、ユーザーに、PST ファイルをプライベートのセキュリティで保護された Azure ストレージの場所にアップロードするために必要なアクセス許可を提供します。 このアクセス キーは組織に固有のもので、PST ファイルを Microsoft クラウドにアップロードした後に、PST ファイルへの不正アクセスから保護するのに役立ちます。 Office 365 への PST ファイルのインポートには、組織で別の Azure サブスクリプションを持つ必要はないことに注意してください。 
    
2. **Azure ストレージの場所に PST ファイルをアップロードする** - 次の手順は、AzCopy.exe ツール (手順 1 でダウンロード) を使用して、Office 365 組織がある場所と同じ地域の Microsoft データ センターに置かれている Azure ストレージの場所に PST ファイルをアップロードして保存することです。 PST ファイルをアップロードするには、Office 365 にインポートするファイルが組織のファイル共有またはファイル サーバー上にある必要があります。
    
    Azure ストレージの場所にアップロードした後に PST ファイルのリストを表示するときに実行できるオプションの手順があることに注意してください。
    
3. **PST インポート マッピング ファイルを作成する** - PST ファイルを Azure ストレージの場所にアップロードしたら、次は PST ファイルのインポート先となるユーザーのメールボックスを指定する、コンマ区切り値 (CSV) ファイルを作成します。PST ファイルはユーザーのプライマリ メールボックスまたはアーカイブ メールボックスにインポートできます。 Office 365 インポート サービスは、CSV ファイルの情報を使用して PST ファイルをインポートします。
    
4. **PST インポート ジョブを作成する** - 次の手順では、セキュリティ/コンプライアンス センターの [**インポート**] ページで PST インポート ジョブを作成し、前の手順で作成した PST インポート マッピング ファイルを送信します。 インポート ジョブを作成した後に、Office 365 は PST ファイル内のデータを分析し、実際に PST インポート マッピング ファイルで指定したメールボックスにインポートするデータを制御するフィルターを設定する機会を提供します。 
    
5. **メールボックスにインポートされる PST データをフィルター処理する** - インポート ジョブを作成すると、Office 365 は PST ファイルに含まれているアイテムの経過時間とさまざまなメッセージの種類を識別することで、PST ファイル内のデータを (安全に) 分析します。 分析が完了し、データをインポートする準備ができたら、PST ファイルに含まれるすべてのデータをインポートするか、インポートするデータをトリミングするかを選ぶことができます。データをトリミングする場合は、インポートするデータを制御するフィルターを設定します。
    
6. **PST インポート ジョブを開始する** - インポート ジョブを開始すると、Office 365 は PST インポート マッピング ファイルの情報を使用して、PST ファイルを Azure Storage の場所からユーザーのメールボックスにインポートします。 インポート ジョブの進捗情報 (インポート中の各 PST ファイルに関する情報を含む) が セキュリティ/コンプライアンス センターの [**インポート**] ページに表示されます。 インポート ジョブが完了すると、ジョブの状態が [**完了**] に設定されます。
  
## <a name="more-information"></a>詳細情報

- なぜ PST ファイルを Office 365 にインポートするのか?
    
  - 組織のアーカイブ メッセージング データを Office 365 にインポートする場合に役立ちます。
    
  - データがクラウドに格納されるので、ユーザーはあらゆるデバイスからデータを利用できます。
    
  - この機能は、インポートした PST ファイルのデータに Office 365 のコンプライアンス機能を適用することで、組織のコンプライアンスのニーズに対応するのに役立ちます。 これには、次の内容が含まれます。
    
  - [アーカイブ メールボックス](enable-archive-mailboxes.md)と[自動拡張アーカイブ](enable-unlimited-archiving.md)を有効にして、インポートしたデータを保存するための追加のメールボックス記憶域をユーザーに与える。 
    
  - メールボックスを[訴訟ホールド](https://go.microsoft.com/fwlink/?linkid=856286)に配置して、インポートしたデータを保持する。 
    
  - Microsoft [電子情報開示ツール](search-for-content.md)を使用して、インポートしたデータを検索する。 
    
  - [Office 365 アイテム保持ポリシー](retention-policies.md)を使用して、インポートしたデータの保持期間、および保持期間の経過後に実行するアクションを制御する。 
    
  - インポートしたデータに影響を与えるメールボックス関連イベントを、[Office 365 監査ログ](search-the-audit-log-in-security-and-compliance.md)で検索する。 
    
  - データを[非アクティブなメールボックス](create-and-manage-inactive-mailboxes.md)にインポートして、コンプライアンスのためにデータをアーカイブする。 
    
  - [データ損失防止ポリシー](data-loss-prevention-policies.md)を使用して、機密データが組織外に漏洩するのを防ぐ。 
  
- 手順 1 で取得する Shared Access Signature (SAS) URL の例を示します。 この例には、PST ファイルを Office 365 にアップロードするために AzCopy.exe ツールで実行するコマンドの構文も含まれています。 パスワードや他のセキュリティ関連の情報を保護するのと同じように、SAS URL を保護する予防措置を講じる必要があります。

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
    
