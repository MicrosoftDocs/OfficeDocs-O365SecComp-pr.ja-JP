---
title: pst コレクションツールを使用して、組織内の pst ファイルを検索、コピー、および削除する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid: MOE150
ms.assetid: 7a150c84-049c-4a9c-8c91-22355b35f2a7
description: Microsoft pst コレクションツールを使用して、組織のネットワークを検索し、組織全体に散在している PST ファイルのインベントリを取得します。 pst ファイルを検索したら、pst コレクションツールを使用して、それらを Office 365 にインポートできるように、1つの場所にコピーすることができます。
ms.openlocfilehash: 87e13ec8a4c58f848ac2ff7a430a7532942ece74
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255349"
---
# <a name="use-the-pst-collection-tool-to-find-copy-and-delete-pst-files-in-your-organization"></a>pst コレクションツールを使用して、組織内の pst ファイルを検索、コピー、および削除する

> [!IMPORTANT]
> この記事に記載されている PST コレクションツールは、Microsoft の標準サポートプログラムやサービスではサポートされていません。 このツールは、あらゆる種類の保証なしで提供されます。 Microsoft は、商品性の保証および特定目的への適合性の保証を含むいかなる明示もしくは黙示の保証責任を負いません。 ツールやドキュメントの使用やパフォーマンスの問題が発生した場合は、そのリスク全体が維持されます。 いかなる場合でも、マイクロソフトは、このツールの作成、運用、または提供に関与する、何らかの損害 (損失、損失、ビジネスの中断、損失など) に関して責任を負いかねます。そのような損害が発生する可能性が Microsoft から通知されている場合でも、ツールまたはドキュメントの使用または使用できないことによって発生したビジネス情報やその他の pecuniary 損失。

Microsoft pst コレクションツールを使用して、組織のネットワークで pst ファイルを検索することができます。 このツールは、組織全体に散在している PST ファイルのインベントリを取得するのに役に立ちます。 pst ファイルを見つけたら、pst コレクションツールを使用して、それらを1か所にまとめてコピーできます。 次に pst を1か所に配置すると、それらを exchange online メールボックス (または単一の exchange online メールボックス) にインポートできるようになります。これにより、Office 365 で豊富なコンプライアンス機能セットを適用することができます。 これには、ユーザーのアーカイブメールボックスへの pst のインポート、電子情報開示検索ツールを使用してインポートした pst ファイル内の特定のメッセージの検索、電子情報開示の保持と Office 365 のアイテム保持ポリシーを使用したメッセージの保持、およびライフサイクルの管理が含まれます。Exchange Online のメッセージングレコード管理機能を使用したこれらのメッセージのサイクル。 収集した PST ファイルが Office 365 に正常にインポートされたことを確認したら、ツールを使用して、ネットワーク上の元の場所から削除することができます。 
  
pst コレクションツールを使用して、ユーザーが新しい pst ファイルを作成したり、ネットワーク上で見つけた既存の pst ファイルを変更したりできないようにすることができます。 これらの "ブロック" 機能を使用すると、pst ファイルの既知のセットを Office 365 に検索、収集、インポートして、組織内の pst ファイルが将来的に急増しないようにすることができます。 
  
## <a name="how-the-pst-collection-tool-works"></a>PST コレクションツールのしくみ

pst コレクションツールを使用して、組織内の pst ファイルを検索、制御、収集、および削除するプロセスの概要を次に示します。
  
![PST コレクションツールのプロセスの概要](media/67a29f27-f83c-4f0a-9df4-7ed92d3086fe.png)
  
1. **[手順 1: ネットワーク上の pst ファイルを検索](#step-1-find-pst-files-on-your-network)** する-ツールを実行して pst ファイルを検索する場合、クライアントおよびサーバーコンピューターの Active Directory オブジェクトを含む組織単位などの場所を指定します。 特定のコンピューターまたはネットワークファイル共有を検索することもできます。 ツールを実行すると、ターゲットコンピューターに "ライトウェイト" コレクションエージェントがインストールされます。 このエージェントは、送信先のコンピューターで pst ファイルを検索し、見つかった pst ファイルに関する情報を pst コレクションツールに送り返します。 このツールは、指定した場所に見つかった PST ファイルに関する情報を含むログファイルを作成します。 これらのファイルは、後の手順でツールを実行するときに使用されます。 
    
2. **[(省略可能) 手順 2: pst ファイルへのアクセスを制御](#optional-step-2-control-access-to-pst-files)** する-このツールは、ユーザーが pst ファイルを作成または変更できないようにする設定を使用してグループポリシーオブジェクト (GPO) を作成します。 この GPO は、ドメイン内のすべてのユーザーに適用されます。 このオプションの手順により、手順1で検出された pst ファイルを "ロックダウン" して、新しい pst ファイルを作成したり、既存の pst ファイルを変更したりせずに、収集、インポート、および削除できるようにすることができます。 
    
3. **[手順 3: pst ファイルをコレクションの場所にコピー](#step-3-copy-the-pst-files-to-a-collection-location)** します。これにより、1つの場所で pst ファイルを収集することができます。これにより、手順4で Office 365 インポートサービスを使用して Exchange Online メールボックスにインポートできるようになります。 このツールを "収集" モードで実行すると、各コレクションエージェントは、エージェントがインストールされているターゲットマシンから、コレクションの場所に PST ファイルをコピーします。 
    
4. **[手順 4: pst ファイルを Office 365 にインポート](#step-4-import-the-pst-files-to-office-365)** します。 pst ファイルを1つの場所にコピーしたら、それらを Exchange Online メールボックスにインポートする準備ができました。 
    
5. **[手順 5: ネットワーク上の pst ファイルを削除](#step-5-delete-the-pst-files-found-on-your-network)** する-見つかって収集された pst ファイルを Office 365 の Exchange Online メールボックスにインポートした後、pst コレクションツールを使用して、pst ファイルを元の場所から削除することができます。が手順1で見つかりました。 

## <a name="before-you-begin"></a>始める前に

- PST コレクションツールをローカルコンピューターにダウンロードするには、次の手順を実行します。 
    
    1. [PST コレクションツールをダウンロード](https://aka.ms/pstcollectiontool)します。
    
    2. ポップアップウィンドウで、[名前を付け**** \> **て**保存] をクリックして、PSTCollectionTool ファイルをローカルコンピューター上のフォルダーに保存します。 
    
    3. PSTCollectionTool ファイルをローカルコンピューター上のフォルダーに抽出します。既定のフォルダー名は PSTCollectionTool です。
    
- PST コレクションツールを任意のモード (検索、ブロック、コピー、または削除) で実行するには、Active Directory ドメインのドメイン管理者グループのメンバーである必要があります。 

## <a name="step-1-find-pst-files-on-your-network"></a>手順 1: ネットワーク上の PST ファイルを検索する

最初の手順として、pst コレクションツールを実行して、組織内の pst ファイルを検索します。 このツールを使用して、次の種類の場所を検索できます。 
  
- 社内の Active Directory ドメイン内の組織単位 (ou)。 このツールは、指定された OU に含まれるすべてのコンピューターを検索します。 
    
- クライアントおよびサーバーのコンピューター。 ツールは、指定されたコンピューターを検索します。 
    
- ネットワークファイル共有。 ツールは、指定されたネットワークファイル共有を検索します。 
    
これらの各場所の`Locations`種類に使用する構文の例については、次の表の表のパラメーターの説明を参照してください。 
  
> [!IMPORTANT]
> pst ファイルのブロック、収集、削除など、他の操作を実行する前に、pst コレクションツールを検索モードで実行する必要があります。 
  
1. ローカルコンピューターでコマンドプロンプトを開きます (管理者として実行します)。
    
2. PSTCollectionTool フォルダー (または、PSTCollectionTool ファイルを抽出したフォルダー) に移動します。
    
3. DataCollectorMaster ディレクトリに移動します。
    
4. 指定した場所に PST ファイルを検索するには、次のコマンドを実行します。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName <Name> -Locations <Locations to search for PSTs> -LogLocation <Location to store log files> -ConfigurationLocation <Location to store configuration files>
    ```

    次の表では、DataCollectorMaster コマンドを実行して PST ファイルを検索するときのパラメーターとその必須値について説明します。 
    
    |パラメーター * * * *|****説明****|例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |検索するデータの種類を指定します。 現時点では、pst コレクションツールを使用して pst ファイルを検索できます。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |ツールによって実行される操作の種類を指定します。 値`Find`を使用して、指定した場所に PST ファイルを検索します。 このツールは、outlook プロファイルに接続されている outlook ファイルおよび pst ファイルで開いている pst ファイルに関する情報を検索して取得することができることに注意してください。  <br/> | `-Mode Find` <br/> |
    | `JobName` <br/> |PST コレクションジョブの名前を指定します。 この同じジョブ名は、ツールを実行して pst ファイルを検索するときに、pst コレクションツールを実行して検出された pst ファイルをブロック、収集、および削除するときに使用します。 ジョブ名は、ログおよび構成ファイル名にも追加されます。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> | PST ファイルを検索する1つまたは複数の場所を指定します。 複数の場所を指定する場合は、セミコロン (;) を使用します。個別の場所を区切ります。 このパラメーターの個々の値は二重引用符 ("") で囲むようにしてください。  <br/><br/>   以下は、検索できる場所の種類に必要な id 値の形式です。  <br/><br/>        **ou** -識別名 (DN) を使用して ou を識別します。例えば：`"OU=NorthAmerica,OU=NWRegion,OU=ITServices,DC=contoso,DC=com"` <br/> > [!IMPORTANT]> 組み込みのコンピューターコンテナー (たとえば、CN = Computers, dc = contoso, dc = com ") は、組織単位ではないため、指定することはできません。<br/> <br/> [**コンピューター** ]-DN または完全修飾ドメイン名 (FQDN) を使用して、ネットワーク上のクライアントおよびサーバーコンピューターを識別します。例えば：  <br/>  ティ`"CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"` <br/>  または  <br/>  FQDN`"FILESERVER01.contoso.com"` <br/><br/>  **ネットワークファイル共有**: UNC 名を使用してネットワークファイル共有を識別します。例えば`"\\FILESERVER02\Users"` <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `LogLocation` <br/> |ログファイルのコピー先となるフォルダーを指定します。 フォルダーが存在しない場合は、ツールの実行時に作成されます。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ConfigurationLocation` <br/> |.xml 構成ファイルのコピー先となるフォルダーを指定します。 このファイルには、ツールの実行時に見つかった各 PST ファイルに関する情報が含まれています。 このファイルは、手順3でツールを実行して検出された PST ファイルをコピーするときに使用されます。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `ExcludedLocations` <br/> |このオプションパラメーターは、検索操作中にスキップする場所を指定します。 特定の ou、コンピューター、およびネットワークファイル共有を除外することができます。 たとえば、ユーザーがアクセス権を持っていない SQL server (または他の種類のアプリケーションサーバー) などのマシンを除外することができます。 除外する場所を複数指定する場合は、セミコロン (;) を使用します。個別の場所を区切ります。 このパラメーターの個々の値は二重引用符 ("") で囲むようにしてください。  <br/> | `-ExcludedLocations "SQLSERVER01.contoso.com"` <br/> |
    | `ForceRestart` <br/> |このオプションスイッチを使用すると、既存の PST コレクションジョブの検索モードでツールを実行できます。 `ForceRestart`スイッチを使用すると、ジョブの前の検索操作からの結果が破棄され、ツールによって指定された場所が再スキャンされ、新しいログおよび構成ファイルが作成されます。  <br/> | `-ForceRestart` <br/> |
   
    各パラメーターに実際の値を使用して、DataCollectorMaster コマンドの構文の例を次に示します。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -LogLocation "c:\users\admin\desktop\PSTCollection" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"
    ```

    コマンドを実行すると、指定した場所に PST ファイルを検索する処理の進行状況を示す詳細な状態メッセージが表示されます。 しばらくすると、最後の状態メッセージに、見つかった PST ファイルの合計数、ジョブが完了したかどうか、およびエラーがあったかどうかが表示されます。 同じ状態メッセージが .log ファイルにコピーされます。
    
### <a name="results-of-running-datacollectormasterexe-in-the-find-mode"></a>検索モードで DataCollectorMaster を実行した結果

PST コレクションツールを検索モードで正常に実行した後、次のファイルが作成され、 `LogLocation` and `ConfigurationLocation`パラメーターで指定されたフォルダーに格納されます。 
  
- **JobName\>__ datetimestamp\>.log-ログファイルには、表示された状態メッセージが含まれています。\< \<** このファイルは、 `LogLocation`パラメーターで指定されたフォルダー内に作成されます。 
    
- **\>__ JobName Find\<datetimestamp\>.csv-csv ファイルには、検出された各 PST ファイルの行が含まれてい\<** ます。 各 pst の情報には、pst ファイルが検出されたコンピューター、pst ファイルの完全なファイルパスの場所、pst ファイルの所有者、pst ファイルのサイズ (キロバイト、kb 単位) が含まれています。 このファイルは、 `LogLocation`パラメーターで指定されたフォルダー内に作成されます。 
    
    > [!TIP]
    > Excel の [オート sum] ツールを使用して、CSV ファイルに記載されているすべての PST ファイルの合計サイズ (KB 単位) を計算します。 その後、変換ツールを使用して合計サイズをメガバイト (mb) またはギガバイト (gb) に変換できます。 
  
- **JobName\>__ datetimestamp\>xml-xml ファイルには、ツールを検索モードで実行したときに使用されたパラメーター値に関する情報が含まれています。\< \<** このファイルには、検出されたすべての PST ファイルに関する情報も含まれています。 このファイル内のデータは、同じジョブに対してツールを再実行して、見つかった PST ファイルをブロック、収集、または削除するときに使用されます。 このファイルは、 `ConfigurationLocation`パラメーターで指定されたフォルダー内に作成されます。 
    
    > [!IMPORTANT]
    > このファイルの名前を変更、変更、または移動しないでください。 このツールは、同じジョブのブロック、コピー、または削除モードでツールを再実行するときに PST コレクションツールによって使用されます。 

## <a name="optional-step-2-control-access-to-pst-files"></a>オプション手順 2: PST ファイルへのアクセスを制御する

このオプションの手順により、手順1で見つかった pst ファイルを "ロックダウン" して、既知の pst ファイルのセットを収集して Office 365 にインポートできるようにします。 PST コレクションツールをブロックモードで実行すると、次の処理が行われます。 
  
- このツールは、 *PST 使用法コントロール*という名前のグループポリシーオブジェクト (GPO) を作成します。 この GPO はドメインにリンクされており、組織内のすべての認証済みユーザーに適用されます。 
    
- [PST 使用状況] コントロール GPO は、組織内のコンピューターにレジストリ設定を作成します。 使用するパラメーターに応じて、ユーザーが新しい pst ファイルを作成できないようにするレジストリ設定を作成し、ユーザーが既存の pst ファイルを変更できないようにするレジストリ設定を作成することができます。
    
> [!NOTE]
> pst ファイルへのアクセスを管理することが組織にとってより破壊的な場合は、この手順を省略して、手順3を実行して pst ファイルを中央の場所にコピーすることを検討してください。 その後、同じジョブに対して ( `ForceRestart`パラメーターを使用して) 手順1を繰り返し、pst ファイルをコレクションの場所にコピーした後に作成されたその他の pst ファイルを検索できます。 新しい PST ファイルが見つかった場合は、それらをコレクションの場所にコピーできます。 このツールを検索`ForceRestart`モードで再実行するときにパラメーターを使用すると、ジョブに対する以前の検索操作からの結果は破棄され、ツールによって指定された場所が再スキャンされます。 

PST ファイルへのアクセスをブロックするには、次のようにします。

1. ローカルコンピューターでコマンドプロンプトを開きます (管理者として実行します)。
    
2. PST コレクションツールをダウンロードしたディレクトリに移動します。
    
3. 手順1で見つかった PST ファイルへのアクセスをブロックするには、次のコマンドを実行します。

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -BlockChangesToFiles -BlockNewFiles
    ```

    次の表では、DataCollectorMaster コマンドを実行して PST ファイルの作成と変更をブロックする際のパラメーターとその必須値について説明します。 
    
    |パラメーター * * * *|****説明****|例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |検索するデータの種類を指定します。 現時点では、pst コレクションツールを使用して pst ファイルを検索できます。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |ツールによって実行される操作の種類を指定します。 この値`Block`を使用して、ユーザーが新しい pst ファイルを作成したり、既存の pst ファイルに変更を加えたりできないようにします。  <br/> | `-Mode Block` <br/> |
    | `JobName` <br/> |既存の PST コレクションジョブの名前を指定します。 手順1でツールを検索モードで実行したときに使用したものと同じジョブ名を使用する必要があります。 このジョブ名は、ブロックモードでツールを実行するときに作成されるログファイルの名前にも追加されます。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |検索モードでツールを実行したときに作成された .xml 構成ファイルがフォルダーに含まれていることを指定します。 手順1でこのパラメーターに使用したのと同じ値を使用します。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |ブロック操作のログファイルがコピーされるフォルダーを指定します。 このパラメーターは省略可能です。 このファイルを含めない場合、ログファイルは PST コレクションツールをダウンロードしたフォルダーにコピーされます。 手順1の検索モードでツールを実行したときに使用したのと同じログの場所を使用して、すべてのログファイルが同じフォルダーに保存されるようにしてください。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `BlockChangesToFiles` <br/> |ユーザーが PST ファイルを変更できないようにするには、このスイッチを使用します。 このスイッチを使用すると、次のレジストリエントリが作成`HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\PST\PstDisableGrow`され、データ値は1に設定されます。 このレジストリ設定は、ブロックモードで PST コレクションツールを実行するときに作成される GPO によって、組織内のコンピューターに作成されます。  <br/> | `-BlockChangesToFiles` <br/> |
    | `BlockNewFiles` <br/> |このスイッチを使用すると、ユーザーは新しい pst ファイルを作成したり、pst ファイルを outlook にインポートしたり、outlook から pst ファイルをエクスポートしたりすることができなくなります。 このスイッチを使用すると、次のレジストリエントリが作成`HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\DisablePst`され、データ値は1に設定されます。 このレジストリ設定は、ブロックモードで PST コレクションツールを実行するときに作成される GPO によって、組織内のコンピューターに作成されます。  <br/> | `-BlockNewFiles` <br/> |
   
    各パラメーターに実際の値を使用して、DataCollectorMaster コマンドの構文の例を次に示します。

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection" -BlockChangesToFiles -BlockNewFiles
    ```
    
    新しい pst ファイルまたは既存の pst ファイルへの変更をブロックするかどうかを確認するメッセージが表示されます。 続行することを確認し、コマンドが正常に実行されると、"PST Usage Controls" という名前の新しい GPO が作成されたことを示すメッセージが表示されます。
    
## <a name="step-3-copy-the-pst-files-to-a-collection-location"></a>手順 3: PST ファイルをコレクションの場所にコピーする

次の手順では、pst コレクションツールを実行したときに見つかった pst ファイルを検索モードでコピーします。 これにより、後で Office 365 にインポートできるように PST ファイルを1か所で収集できます。 PST ファイルをコレクションの場所にコピーする前に、必要な記憶域の容量の合計を決定することを検討してください。 これは、手順1で作成した CSV ファイルを使用して、すべての PST ファイルの合計サイズを計算することができます。
  
> [!NOTE]
> PST ファイルを Office 365 にインポートして元の場所から削除した後、この手順でコピーしたコレクションの場所から PST ファイルを削除する必要がある場合があります。 
  
1. ローカルコンピューターでコマンドプロンプトを開きます (管理者として実行します)。
    
2. PST コレクションツールをダウンロードしたディレクトリに移動します。
    
3. 次のコマンドを実行して、PST ファイルを指定した場所にコピーします。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName <Name of job from Step 1> -Locations <same locations from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    次の表では、DataCollectorMaster コマンドを実行して PST ファイルをコピーするときのパラメーターとその必須値について説明します。 
    
    |パラメーター * * * *|****説明****|例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |検索するデータの種類を指定します。 現時点では、pst コレクションツールを使用して pst ファイルを検索できます。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |ツールによって実行される操作の種類を指定します。 この値`Collect`を使用して、検索モードでツールを実行したときに検出された PST ファイルをコピーします。 このツールは、outlook で開いている pst ファイルをコピーして、outlook プロファイルに接続された pst ファイルをコピーできることに注意してください。  <br/> | `-Mode Collect` <br/> |
    | `JobName` <br/> |既存の PST コレクションジョブの名前を指定します。 手順1でツールを検索モードで実行したときに使用したものと同じジョブ名を使用する必要があります。 このジョブ名は、収集モードでツールを実行するときに作成されるログファイルの名前にも追加されます。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> |手順1で`Locations`パラメーターに使用したのと同じ値を使用します。 ツールを再実行して、手順5で元の場所から PST ファイルを削除する場合は、このツールを Collect モードで実行するときに、このパラメーターを含めます。  <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"; "CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `ConfigurationLocation` <br/> |検索モードでツールを実行したときに作成された .xml 構成ファイルが格納されているフォルダーを指定します。 手順1でこのパラメーターに使用したのと同じ値を使用します。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop \PSTCollection\Configuration"` <br/> |
    | `CopyLocation` <br/> |PST ファイルのコピー先となるコレクションの場所を指定します。 ファイルをファイルサーバー、ネットワークファイル共有、またはハードドライブにコピーすることができます。 この場所は、収集モードでツールを実行する前に存在している必要があります。 このツールは場所を作成せず、存在しないというエラーが返されます。  <br/> また、このパラメーターで指定されたコレクションの場所にアクセス許可を書き込む必要があります。  <br/> | `-CopyLocation "\\FILESERVER03\PSTs"` <br/> |
    | `LogLocation` <br/> |収集モードのログファイルがコピーされるフォルダーを指定します。 このパラメーターは省略可能です。 このファイルを含めない場合、ログファイルは PST コレクションツールをダウンロードしたフォルダーにコピーされます。 手順1の検索モードでツールを実行したときに使用したのと同じログの場所を使用して、すべてのログファイルが同じフォルダーに保存されるようにしてください。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |このオプションのスイッチを使用すると、既存の PST コレクションジョブのコレクションモードでツールを再実行できます。 以前に Collect モードでツールを実行していて、PST ファイルの場所を再スキャンする`ForceRestart`スイッチを使用して、このツールを検索モードで再び実行した場合は、このスイッチを使用して、コレクションモードでツールを再実行し、場所を再スキャンします。 コレクションモードで`ForceRestart`スイッチを使用する場合、このツールは以前のすべてのコレクション操作を無視し、PST ファイルを最初からコピーしようとします。  <br/> | `-ForceRestart` <br/> |
   
    各パラメーターに実際の値を使用して、DataCollectorMaster ツールの構文の例を次に示します。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -CopyLocation "\\FILESERVER03\PSTs" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    コマンドを実行すると、手順1で見つかった PST ファイルの収集の進行状況を示す詳細な状態メッセージが表示されます。 しばらくすると、最後の状態メッセージにエラーがあるかどうかと、ログのコピー先が表示されます。 同じ状態メッセージが .log ファイルにコピーされます。
    
### <a name="results-of-running-datacollectormasterexe-in-the-collect-mode"></a>収集モードで DataCollectorMaster を実行した結果

DataCollectorMaster を Collect モードで正常に実行した後、次のファイルが作成され、 `LogLocation` and `ConfigurationLocation`パラメーターで指定されたフォルダーに格納されます。 
  
- JobName は、**日付\>を_収集_\<します。ログファイルには、表示された状態メッセージが含まれています。\> \<** このファイルは、 `LogLocation`パラメーターで指定されたフォルダー内に作成されます。 
    
- **JobName の日付\>を_収集_\<する-xml ファイルには、収集モードでツールが実行されたパラメーター値に関する情報のみが含まれます。\> \<** このファイル内のデータは、DataCollectorMaster ツールを再実行して PST ファイルを削除するときに使用されます。[手順 5](#step-5-delete-the-pst-files-found-on-your-network)を参照してください。
    

## <a name="step-4-import-the-pst-files-to-office-365"></a>手順 4: Office 365 に PST ファイルをインポートする

手順1で見つかった PST ファイルを収集した後、次の手順では、それらを Office 365 のメールボックスにインポートします。 一部またはインポートプロセスでは、インポートする各 PST ファイルの行を含む CSV マッピングファイルを作成する必要があります。 各行の情報 pst ファイルの名前、ユーザーの電子メールアドレス、および pst ファイルをユーザーのプライマリメールボックスまたはアーカイブメールボックスにインポートするかどうかを指定します。 csv マッピングファイルを作成するには、手順1で作成した**JobName\>_Find_\<datetimestamp の .csv**ファイルの情報を使用します。 
  
PST ファイルを Office 365 にインポートするための詳細な手順については、以下のいずれかのトピックを参照してください。
  
- [ネットワークアップロードを使用して Office 365 に PST ファイルをインポートする](use-network-upload-to-import-pst-files.md)
    
- [ドライブ送付を使用して PST ファイルを Office 365 にインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md)
    

## <a name="step-5-delete-the-pst-files-found-on-your-network"></a>手順 5: ネットワーク上で見つかった PST ファイルを削除する

見つけて収集した pst ファイルを Office 365 の Exchange Online メールボックスにインポートした後で、pst コレクションツールを使用して、手順1で見つけた元の場所から pst ファイルを削除できます。 
  
1. ローカルコンピューターでコマンドプロンプトを開きます (管理者として実行します)。
    
2. PST コレクションツールをダウンロードしたディレクトリに移動します。
    
3. PST ファイルを削除するには、次のコマンドを実行します。

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    次の表では、DataCollectorMaster コマンドを実行して PST ファイルを削除するときのパラメーターとその必須値について説明します。 
    
    |パラメーター * * * *|****説明****|例 * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |検索するデータの種類を指定します。 現時点では、pst コレクションツールを使用して pst ファイルを検索できます。 ![空ける](media/b078d05c-3aee-4b9f-8805-6a8a9d8970ee.png)           <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |ツールによって実行される操作の種類を指定します。 検索モードで`Delete`ツールを実行したときに検出された PST ファイルを削除するには、値を使用します。  <br/> | `-Mode Delete` <br/> |
    | `JobName` <br/> |既存の PST コレクションジョブの名前を指定します。 この同じジョブ名を使用する必要があります。この名前は、このツールを検索モードで実行したときと、手順1および手順3で使用したものと同じです。 このジョブ名は、ツールを削除モードで実行するときに作成されるログファイルの名前にも追加されます。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |収集モードでツールを実行したときに作成された .xml 構成ファイルが格納されているフォルダーを指定します。 手順3でこのパラメーターに使用したのと同じ値を使用します。  <br/> | `-ConfigurationLocation "c:\users\admin\ desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |削除モードのログファイルがコピーされるフォルダーを指定します。 このパラメーターは省略可能です。 このファイルを含めない場合、ログファイルは PST コレクションツールをダウンロードしたフォルダーにコピーされます。 手順1と手順3でツールを実行したときと同じログの場所を使用して、すべてのログファイルが同じフォルダーに保存されるようにしてください。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |このオプションスイッチを使用すると、既存の PST コレクションジョブの削除モードでツールを再実行できます。 以前に削除モードでツールを実行していて、PST ファイルの場所を再スキャンする`ForceRestart`スイッチを使用して、このツールを検索モードで再び実行した場合は、このスイッチを使用して削除モードでツールを再実行し、再 sca で検出された pst ファイルを削除できます。この場所を代入します。 `ForceRestart`スイッチを削除モードで使用すると、以前の削除操作は無視され、PST ファイルの削除が再試行されます。  <br/> | `-ForceRestart` <br/> 

    各パラメーターに実際の値を使用して、DataCollectorMaster ツールの構文の例を次に示します。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```
   
    コマンドを実行すると、手順1で検出され、手順3で収集された PST ファイルの削除の進行状況を示す詳細な状態メッセージが表示されます。 しばらくすると、最後の状態メッセージにエラーがあるかどうかと、ログのコピー先が表示されます。 同じ状態メッセージが .log ファイルにコピーされます。
    
### <a name="results-of-running-datacollectormasterexe-in-the-delete-mode"></a>削除モードで DataCollectorMaster を実行した結果

DataCollectorMaster を削除モードで正常に実行した後、次のファイルが作成され、 `LogLocation` and `ConfigurationLocation`パラメーターで指定されたフォルダーに格納されます。 
  
- **JobName\>__ datetimestamp\>。ログファイルには、表示された状態メッセージが含まれています。\< \<** このファイルは、 `LogLocation`パラメーターで指定されたフォルダー内に作成されます。 
    
- **JobName\>__ datetimestamp\>xml-xml ファイルには、ツールで使用された場所が削除モードで実行されたパラメーター値に関する情報のみが含まれています。\< \<** また、削除された各 PST ファイルの名前とファイルパスも一覧表示します。 このファイルは、 `ConfigurationLocation`パラメーターで指定されたフォルダー内に作成されます。 
