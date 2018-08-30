---
title: PST コレクション ツールを使用して、検索、コピー、および組織内の PST ファイルを削除するには
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 7a150c84-049c-4a9c-8c91-22355b35f2a7
description: Microsoft PST コレクション ツールを使用して、組織全体にわたって散在している PST ファイルのインベントリを取得するのには、組織のネットワークを検索します。PST ファイルを検索した後は、Office 365 にインポートするために中央の場所にコピーするのに PST コレクション ツールを使用することができます。
ms.openlocfilehash: 183ab968b894c824f2b23c08e98e671ef85316cc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532095"
---
# <a name="use-the-pst-collection-tool-to-find-copy-and-delete-pst-files-in-your-organization"></a>PST コレクション ツールを使用して、検索、コピー、および組織内の PST ファイルを削除するには

PST ファイルは、組織のネットワークを検索するのには Microsoft PST コレクション ツールを使用できます。ツールを使用して、組織全体にわたって散在している PST ファイルのインベントリを取得できます。PST ファイルを検索した後は、中央の場所にコピーするのに PST コレクション ツールを使用できます。Pst ファイルを 1 か所でもし、Office 365 のコンプライアンス機能の豊富なセットを適用できる Exchange Online のメールボックス (または 1 つの Exchange Online メールボックス) をインポートすることを許可します。これは pst ファイルにインポートするユーザーのアーカイブが電子的証拠開示を使用してメッセージを保持する電子的証拠開示検索ツールを使用してインポートする PST ファイル内の特定のメッセージを検索して、メールボックスを保持して、Office 365 の保存ポリシーとライフ サイクルの管理も含まれます。サイクルは、メッセージングを使用してこれらのメッセージのレコード管理機能では、Exchange オンライン。収集した PST ファイルが Office 365 に正常にインポートされたことが確実に把握して後、は、ネットワーク上の元の場所から削除するのにはツールを使用することができます。 
  
PST コレクション ツールを使用して行うことができます、もう 1 つは、新しい PST ファイルを作成して、ネットワーク上にある既存の PST ファイルを変更することからユーザーを防ぐためです。これらの「ブロック」機能を使用すると、収集するには、Office 365 に既知の一連の PST ファイルをインポートし、、組織内の PST ファイルの将来の増加を防ぐためです。 
  
## <a name="how-the-pst-collection-tool-works"></a>PST コレクション ツールの動作

PST コレクション ツールを使用して、検索、管理、収集、組織内の PST ファイルを削除するプロセスの概要を次に示します。
  
![ツールの PST の収集プロセスの概要](media/67a29f27-f83c-4f0a-9df4-7ed92d3086fe.png)
  
1. **[ステップ 1: ネットワーク上の PST ファイルを検索する](#step-1-find-pst-files-on-your-network)** クライアントとサーバー コンピューターの Active Directory オブジェクトを含む組織単位など、場所を指定する PST ファイルを検索するツールを実行したときです。特定のコンピューターまたはネットワーク ファイル共有を検索することもできます。ツールを実行するときは、ターゲット コンピューターに「軽量な」コレクション エージェントがインストールされています。このエージェントでは、PST ファイルのターゲット コンピューターを検索し、PST ファイルのすべての PST コレクション ツールに情報を送信します。ツールは、指定された場所で検出された PST ファイルに関する情報を含むログ ファイルを作成します。これらのファイルは、後の手順でツールを実行するときに使用されます。 
    
2. **[(省略可能) 手順 2: PST ファイルへのアクセスを制御する](#optional-step-2-control-access-to-pst-files)**-ツールは、ユーザーが作成または PST ファイルを変更することを防ぐ設定で、グループ ポリシー オブジェクト (GPO) を作成します。この GPO は、ドメイン内のすべてのユーザーに適用されます。この省略可能な手順では、「ロック ダウン」を収集、インポート、およびそれらを削除せずに、新しい PST ファイルを作成するために手順 1 で、検出された PST ファイルまたは既存の PST ファイルを変更できます。 
    
3. **[手順 3: コレクションの場所に PST ファイルをコピー](#step-3-copy-the-pst-files-to-a-collection-location)** をインポートできます、Exchange Online のメールボックスにサービスを使用して、Office 365 のインポート手順 4 で 1 つの場所に PST ファイルを収集できます。収集」モードでツールを実行すると、各コレクションのエージェントは、コレクションの場所に、エージェントがインストールされているターゲット ・ マシンから PST ファイルをコピーします。 
    
4. **[ステップ 4: Office 365 に PST ファイルをインポートする](#step-4-import-the-pst-files-to-office-365)** の Exchange Online のメールボックスにインポートする準備が整ったら、PST ファイルを 1 つの場所にコピーした後。 
    
5. **[手順 5: PST ファイルがネットワーク上にある削除](#step-5-delete-the-pst-files-found-on-your-network)**、PST ファイルを PST コレクション ツールを使用するには元の場所から PST ファイルを削除すること、検出し、収集されたことが Office 365 のオンラインの Exchange メールボックスにインポートした後で、手順 1 で見つかりました。 

## <a name="before-you-begin"></a>はじめに

- PST コレクション ツールをローカル コンピューターにダウンロードするこれらの手順に従います。 
    
    1. [PST コレクション ツールをダウンロード](https://aka.ms/pstcollectiontool)します。
    
    2. ポップアップ ウィンドウで、[**保存**] をクリックします\>**として保存する**に PSTCollectionTool.zip ファイルをローカル コンピューター上のフォルダーに保存します。 
    
    3. ローカル コンピューター上のフォルダーに PSTCollectionTool.zip ファイルを抽出します。既定のフォルダー名は、PSTCollectionTool です。
    
- (検索、ブロック、コピー、または削除) のいずれかのモードでは、PST コレクション ツールを実行するには、Active Directory ドメインのドメイン管理者グループのメンバーであるがあります。 

## <a name="step-1-find-pst-files-on-your-network"></a>ステップ 1: ネットワーク上の PST ファイルを検索します。

最初のステップでは、PST ファイルを検索する、組織内の PST コレクション ツールを実行します。次の種類の場所を検索するのにツールを使用することができます。 
  
- オンプレミスの Active Directory ドメイン内の組織単位 (Ou)。ツールは、指定した OU に含まれているすべてのコンピューターを検索します。 
    
- クライアント コンピューターとサーバー コンピューターです。ツールは、指定したコンピューターを検索します。 
    
- ネットワーク ファイル共有にします。ツールは、指定したネットワーク ファイル共有を検索します。 
    
説明を参照してください、`Locations`のこれらの場所の種類ごとに使用する構文の例については次の手順でテーブル内のパラメーターです。 
  
> [!IMPORTANT]
> ツールがある、実行するように、PST コレクション検索モードでブロックを収集する、PST ファイルの削除などの他のアクションを実行する前にします。 
  
1. ローカル コンピューターに (管理者として実行) コマンド プロンプトを開きます。
    
2. PSTCollectionTool フォルダー (または、PSTCollectionTool.zip ファイルを抽出したフォルダー) に移動します。
    
3. DataCollectorMaster ディレクトリに変更します。
    
4. 指定の場所に PST ファイルを検索するのには次のコマンドを実行します。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName <Name> -Locations <Locations to search for PSTs> -LogLocation <Location to store log files> -ConfigurationLocation <Location to store configuration files>
    ```

    次の表では、PST ファイルを検索する DataCollectorMaster.exe コマンドを実行すると、パラメーターと、必要な値をについて説明します。 
    
    |パラメーター。|****説明****|例。|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |検索するデータの種類を指定します。現時点では、PST ファイルを検索する PST コレクション ツールを使用することができます。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |ツールを実行する操作の種類を指定します。値を使用して`Find`を指定された場所に PST ファイルを検索します。ツールが検索し、PST ファイルを Outlook プロファイルに接続されている Outlook と PST ファイルを開いているに関する情報を得ることができますに注意してください。<br/> | `-Mode Find` <br/> |
    | `JobName` <br/> |PST コレクション ジョブの名前を指定します。ブロックおよび収集し、PST ファイルを検索するツールの実行時に検出された PST ファイルを削除するコレクションの PST のツールを実行するときは、これと同じジョブ名を使用します。ジョブ名は、ログと構成ファイルの名前にも追加されます。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> | PST ファイルを検索する 1 つまたは複数の場所を指定します。複数の場所を指定する場合は、セミコロン (;) を使用して、個々 の場所を区切ります。このパラメーターを二重引用符での個々 の値を囲むことを確認する ("")。<br/><br/>   ここで、検索できる場所の種類に必要な id 値の形式です。  <br/><br/>        **Ou**の識別名 (DN) を使用して Ou を特定するのには例えば：`"OU=NorthAmerica,OU=NWRegion,OU=ITServices,DC=contoso,DC=com"` <br/> > [!IMPORTANT]> ビルトイン コンピューター コンテナーを指定できません (たとえば、CN = DC のコンピューター = contoso 社、DC = com") 組織単位ではありませんので。<br/> <br/> **マシン**で、ネットワーク上のクライアントとサーバーのマシンを識別するには、DN を使用してまたは完全修飾ドメイン名 (FQDN)例えば：  <br/>  DN:`"CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"` <br/>  または  <br/>  FQDN。`"FILESERVER01.contoso.com"` <br/><br/>  **ネットワーク ファイル共有**の UNC 名を使用して、ネットワーク ファイル共有を識別します。例えば`"\\FILESERVER02\Users"` <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `LogLocation` <br/> |ログ ファイルをコピーするフォルダーを指定します。フォルダーが存在しない場合は、ツールを実行するときに作成されます。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ConfigurationLocation` <br/> |.Xml 構成ファイルにコピーするフォルダーを指定します。このファイルには、ツールを実行するときに見られる各 PST ファイルに関する情報が含まれています。このファイルは、手順 3 である、PST ファイルのファイルをコピーするのには、ツールを実行するときに使用されます。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `ExcludedLocations` <br/> |この省略可能なパラメーターは、検索操作の実行中にスキップする場所を指定します。特定の Ou、マシン、およびネットワーク共有のファイルを除外することができます。たとえば、SQL server (またはその他のアプリケーション サーバー) として構成されているコンピューターなどのコンピューターを除外することが、ユーザーへのアクセス権を持っていないことです。除外する 1 つ以上の場所を指定する場合は、セミコロン (;) を使用して、個々 の場所を区切ります。このパラメーターを二重引用符での個々 の値を囲むことを確認する ("")。  <br/> | `-ExcludedLocations "SQLSERVER01.contoso.com"` <br/> |
    | `ForceRestart` <br/> |この省略可能なスイッチでは、既存の PST コレクション ジョブの検索モードでツールを実行することができます。使用する場合、`ForceRestart`スイッチの場合は、ジョブが破棄され、ツールは指定された場所を再スキャンし、新しいログ ファイルと構成ファイルを作成するため、以前の検索操作の結果。<br/> | `-ForceRestart` <br/> |
   
    各パラメーターの実際の値を使用して、DataCollectorMaster.exe コマンドの構文の例を以下に示します。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -LogLocation "c:\users\admin\desktop\PSTCollection" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"
    ```

    コマンドを実行した後、指定された場所に PST ファイルの検索の進行状況を示す詳細なステータス メッセージが表示されます。最終ステータス メッセージはしばらくして、検出された PST ファイルの合計数、ジョブが完了するかどうか、およびすべてのエラーが発生したかどうかを示しています。同じステータス メッセージは、.log ファイルにコピーされます。
    
### <a name="results-of-running-datacollectormasterexe-in-the-find-mode"></a>検索モードで DataCollectorMaster.exe の実行結果

次のファイルが作成されで指定されたフォルダーに格納されている正常にツールの実行後、PST コレクション検索モードを`LogLocation`と`ConfigurationLocation`のパラメーターです。 
  
- **\<態\>_検索_\<DateTimeStamp\>.log** -ログ ファイルに表示されているステータス メッセージが含まれています。指定したフォルダーにこのファイルが作成、`LogLocation`のパラメーターです。 
    
- **\<態\>_検索_\<DateTimeStamp\>.csv** -「CSV ファイルには、検出された PST ファイルごと行が含まれています。各 pst ファイルの情報には、PST ファイルが見つかった、PST ファイルの完全なファイル パスの場所、所有者、PST ファイルと PST ファイルのサイズ (キロバイト単位、kb 単位) のコンピューターが含まれています。指定したフォルダーにこのファイルが作成、`LogLocation`のパラメーターです。 
    
    > [!TIP]
    > Excel で、[オート Sum] ツールを使用すると、CSV ファイルに記載されているすべての PST ファイルの合計サイズ (kb 単位で) を計算できます。合計サイズをメガバイト (MB) またはギガバイト (GB) に変換するのに変換電卓を使用することができます。 
  
- **\<態\>_検索_\<DateTimeStamp\>.xml** ・に関する情報が XML ファイルに含まれているパラメーターの値を検索モードでツールを実行したときに使用されている場合。このファイルには、検出されたすべての PST ファイルに関する情報も含まれています。ブロックをジョブの収集、同じツールを再実行または PST ファイルの削除が検出されましたを実行すると、このファイル内のデータが使用されます。指定したフォルダーにこのファイルが作成、`ConfigurationLocation`のパラメーターです。 
    
    > [!IMPORTANT]
    > しない名前を変更、変更、またはこのファイルを移動します。PST 収集ツールによっては、ブロック内でのコピー ツールを再実行するか、同じジョブのモードを削除するときに使用されます。 

## <a name="optional-step-2-control-access-to-pst-files"></a>(省略可能)PST ファイルへのアクセスを制御する手順 2。

この省略可能な手順では、ロックダウンして、PST ファイルを収集することができるように、手順 1 で見つかった、既知の一連の PST ファイルを Office 365 にインポートすることができます。PST コレクション ツールを実行するにはブロック モードでは、次の処理が発生します。 
  
- ツールは、グループ ポリシー オブジェクト (GPO) という名前の*PST の使用状況のコントロール*を作成します。この GPO は、ドメインにリンクされているし、組織内のすべての認証されたユーザーに適用されます。 
    
- PST の使用状況のコントロールの GPO では、組織内のコンピューターのレジストリ設定が作成されます。パラメーターを使用することによって、ユーザーが新しい PST ファイルを作成することを防ぐためのレジストリ設定と既存の PST ファイルを変更できないようにするレジストリ設定を作成できます。
    
> [!NOTE]
> PST ファイルへのアクセスを制御するが、組織の混乱を生じさせ場合、この手順をスキップしていて、中央の場所に PST ファイルをコピーするのには手順 3 を実行するを検討する可能性があります。同じジョブのステップ 1 を繰り返すことができますし、(を使用して、`ForceRestart`パラメーター) コレクションの場所に Pst ファイルをコピーした後に作成された追加の Pst ファイルを検索します。新しい PST ファイルが見つかった場合は、コレクションの場所にコピーできます。使用する場合、`ForceRestart`パラメーターと検索モードでツールを再実行、ジョブの前回の検索操作の結果は破棄されますが、このツールは指定された場所を再スキャンします。 

PST ファイルへのアクセスをブロックするには。

1. ローカル コンピューターに (管理者として実行) コマンド プロンプトを開きます。
    
2. PST コレクション ツールをダウンロードしたディレクトリに移動します。
    
3. 手順 1 での PST ファイルへのアクセスを禁止するのには次のコマンドを実行します。

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -BlockChangesToFiles -BlockNewFiles
    ```

    次の表では、作成し、PST ファイルの変更を禁止するのには DataCollectorMaster.exe コマンドを実行すると、パラメーターと、必要な値をについて説明します。 
    
    |パラメーター。|****説明****|例。|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |検索するデータの種類を指定します。現時点では、PST ファイルを検索する PST コレクション ツールを使用することができます。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |ツールを実行する操作の種類を指定します。値を使用して`Block`を新しい PST ファイルを作成して、既存の PST ファイルに変更を加えるようにします。<br/> | `-Mode Block` <br/> |
    | `JobName` <br/> |既存の PST コレクション ジョブの名前を指定します。手順 1 で検索モードでツールを実行したときに使用しているこれと同じジョブ名を使用する必要があります。このジョブの名前は、ブロック モードでツールを実行するときに作成されるログ ファイルの名前に追加されます。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |検索モードでツールを実行したときに作成された .xml 構成ファイルを格納するフォルダーを指定します。手順 1 でこのパラメーターを使用した同じ値を使用します。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |ブロック操作のログ ファイルをコピーするフォルダーを指定します。これは、省略可能なパラメーターです。それを含めない場合は、PST コレクション ツールをダウンロードしたフォルダーにログ ファイルがコピーされます。すべてのログ ファイルが同じフォルダーに保存するために手順 1 で検索モードでツールを実行したときに使用したログの場所を検討してください。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `BlockChangesToFiles` <br/> |PST ファイルを変更できないようにするのにには、このスイッチを使用します。次のレジストリ エントリが作成されるとき、このスイッチを使用する: `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\PST\PstDisableGrow` 、データ値が 1 に設定します。ブロック モードでは、PST のコレクション ツールを実行するときに作成される GPO が組織内のコンピューターでこのレジストリ設定が作成されます。<br/> | `-BlockChangesToFiles` <br/> |
    | `BlockNewFiles` <br/> |新しい PST ファイルを作成する、開く、Outlook に PST ファイルをインポートして Outlook から PST ファイルをエクスポートするようにするのにには、このスイッチを使用します。次のレジストリ エントリが作成されるとき、このスイッチを使用する: `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\DisablePst` 、データ値が 1 に設定します。ブロック モードでは、PST のコレクション ツールを実行するときに作成される GPO が組織内のコンピューターでこのレジストリ設定が作成されます。<br/> | `-BlockNewFiles` <br/> |
   
    各パラメーターの実際の値を使用して、DataCollectorMaster.exe コマンドの構文の例を以下に示します。

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection" -BlockChangesToFiles -BlockNewFiles
    ```
    
    新しい PST ファイルまたは既存の PST ファイルへの変更をブロックすることを確認するように求められます。続行して、コマンドが正常に実行されることを確認した後、PST の使用「コントロール」、という名前の新しい GPO が作成されたことを示すメッセージが表示されます。
    
## <a name="step-3-copy-the-pst-files-to-a-collection-location"></a>手順 3: コレクションの場所に PST ファイルをコピーします。

コピーするのには次の手順では、PST ファイルの検索モードで、PST のコレクション ツールを実行したときがあること。Office 365 にインポートすることが後で 1 つの場所に PST ファイルを収集できます。コレクションの場所に PST ファイルをコピーする前に、必要なストレージ領域の合計量を決定することを検討します。これを行うすべての PST ファイルの合計サイズを計算するのには手順 1 で作成した CSV ファイルを使用します。
  
> [!NOTE]
> Office 365 に PST ファイルをインポートし、それらを元の場所から削除、したらここにコピーしたコレクションの場所からそれらを削除する可能性があります。 
  
1. ローカル コンピューターに (管理者として実行) コマンド プロンプトを開きます。
    
2. PST コレクション ツールをダウンロードしたディレクトリに移動します。
    
3. 指定した場所に PST ファイルをコピーするのには次のコマンドを実行します。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName <Name of job from Step 1> -Locations <same locations from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    次の表では、PST ファイルをコピーするのには DataCollectorMaster.exe コマンドを実行すると、パラメーターと、必要な値をについて説明します。 
    
    |パラメーター。|****説明****|例。|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |検索するデータの種類を指定します。現時点では、PST ファイルを検索する PST コレクション ツールを使用することができます。  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |ツールを実行する操作の種類を指定します。値を使用して`Collect`PST ファイルをコピーするのには検出された検索モードでツールを実行したときです。このツールは、Outlook で開いているし、Outlook プロファイルに接続されている PST ファイルをコピーする PST ファイルのコピーができないことに注意してください。<br/> | `-Mode Collect` <br/> |
    | `JobName` <br/> |既存の PST コレクション ジョブの名前を指定します。手順 1 で検索モードでツールを実行したときに使用しているこれと同じジョブ名を使用する必要があります。このジョブの名前は、収集モードでツールを実行するときに作成されるログ ファイルの名前に追加されます。  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> |使用した同じ値を使用して、`Locations`ステップ 1 のパラメーターです。手順 5 で、元の場所から PST ファイルを削除するのにはこのツールを再実行する場合は、収集モードでツールを実行するときは、このパラメーターを指定しました。<br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"; "CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `ConfigurationLocation` <br/> |検索モードでツールを実行したときに作成された .xml 構成ファイルを含むフォルダーを指定します。手順 1 でこのパラメーターを使用した同じ値を使用します。  <br/> | `-ConfigurationLocation "c:\users\admin\desktop \PSTCollection\Configuration"` <br/> |
    | `CopyLocation` <br/> |PST ファイルのコピー先コレクションの場所を指定します。ファイル サーバー、ネットワーク ファイル共有、またはハード ドライブにファイルをコピーすることができます。収集モードでツールを実行する前に、場所が存在する必要があります。このツールでは、場所を作成しないし、それが存在しないことを示すエラーが返されます。  <br/> また、このパラメーターで指定されたコレクションの場所に書き込みアクセス許可があります。  <br/> | `-CopyLocation "\\FILESERVER03\PSTs"` <br/> |
    | `LogLocation` <br/> |収集モードのログ ファイルをコピーするフォルダーを指定します。これは、省略可能なパラメーターです。それを含めない場合は、PST コレクション ツールをダウンロードしたフォルダーにログ ファイルがコピーされます。すべてのログ ファイルが同じフォルダーに保存するために手順 1 で検索モードでツールを実行したときに使用したログの場所を検討してください。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |この省略可能なスイッチでは、既存の PST コレクション ジョブのコレクション モードでツールを再実行することができます。収集モードでツールを実行していたかどうかは、検索モードでツールを再度実行します`ForceRestart`PST ファイルの場所を再スキャンに切り替えると、このスイッチを使用するにはコレクション モードでツールを再実行し、再度コピーする PST ファイルを検出する場合がありました、場所を再スキャンします。使用する場合、`ForceRestart`コレクション モードでは、ツール内のスイッチは、前のコレクションの操作を無視し、最初から PST ファイルをコピーしようとしています。<br/> | `-ForceRestart` <br/> |
   
    各パラメーターの実際の値を使用する DataCollectorMaster.exe ツールの構文の例を以下に示します。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -CopyLocation "\\FILESERVER03\PSTs" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    コマンドを実行した後、手順 1 で検出された PST ファイルの収集の進行状況を示す詳細なステータス メッセージが表示するされます。しばらくして、最終的なステータス メッセージは、エラーと、ログがコピーされる場所はないかを示します。同じステータス メッセージは、.log ファイルにコピーされます。
    
### <a name="results-of-running-datacollectormasterexe-in-the-collect-mode"></a>収集モードで DataCollectorMaster.exe の実行結果

次のファイルが作成されで指定されたフォルダーに格納されている収集モードで DataCollectorMaster.exe を正常に実行した後、`LogLocation`と`ConfigurationLocation`のパラメーターです。 
  
- **\<態\>_収集_\<DateTimeStamp\>.log** -ログ ファイルに表示されているステータス メッセージが含まれています。指定したフォルダーにこのファイルが作成、`LogLocation`のパラメーターです。 
    
- **\<態\>_収集_\<DateTimeStamp\>.xml** -XML ファイルにのみで使用されているツールが収集モードで実行されたパラメーターの値に関する情報が含まれています。実行すると、このファイル内のデータが使用される PST ファイルを削除するのには DataCollectorMaster.exe ツールを再実行します。[手順 5](#step-5-delete-the-pst-files-found-on-your-network)を参照してください。
    

## <a name="step-4-import-the-pst-files-to-office-365"></a>手順 4: Office 365 に PST ファイルをインポートします。

PST ファイルを手順 1 で収集した後は、Office 365 のメールボックスにインポートします。部品またはインポート プロセスでは、インポートする PST ファイルの行が含まれる CSV マッピング ファイルを作成する必要があります。各行の情報、ユーザーの電子メール アドレスでは、PST ファイルの名前を指定し、プライマリ ・ ユーザーの PST ファイルをインポートするかどうか、またはメールボックスをアーカイブします。内の情報を使用して、**態\>_検索_\<DateTimeStamp.csv**ファイル (手順) CSV マッピング ファイルを作成するための 1 です。 
  
PST ファイルを Office 365 にインポートする手順については、次のトピックを参照してください。
  
- [ネットワーク アップロードを使用して PST ファイルを Office 365 にインポートする](use-network-upload-to-import-pst-files.md)
    
- [ドライブ送付を使用して PST ファイルを Office 365 にインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md)
    

## <a name="step-5-delete-the-pst-files-found-on-your-network"></a>ステップ 5: ネットワーク上にある PST ファイルを削除します。

検出および収集する PST ファイルを Office 365 のオンラインの Exchange メールボックスにインポートすると後、は、PST ファイルを手順 1 で置かれていた元のソースの場所から削除するのには PST コレクション ツールを使用することができます。 
  
1. ローカル コンピューターに (管理者として実行) コマンド プロンプトを開きます。
    
2. PST コレクション ツールをダウンロードしたディレクトリに移動します。
    
3. PST ファイルを削除するのには次のコマンドを実行します。

    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    次の表では、PST ファイルを削除するのには DataCollectorMaster.exe コマンドを実行すると、パラメーターと、必要な値をについて説明します。 
    
    |パラメーター。|****説明****|例。|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |検索するデータの種類を指定します。現時点では、PST ファイルを検索する PST コレクション ツールを使用することができます。 ![スペーサー](media/b078d05c-3aee-4b9f-8805-6a8a9d8970ee.png)           <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |ツールを実行する操作の種類を指定します。値を使用して`Delete`PST ファイルを削除するのには検出された検索モードでツールを実行したときです。<br/> | `-Mode Delete` <br/> |
    | `JobName` <br/> |既存の PST コレクション ジョブの名前を指定します。検索モードと、手順 1 と手順 3 で収集モードでツールを実行したときに使用しているこれと同じジョブ名を使用する必要があります。このジョブの名前は、削除モードでツールを実行するときに作成されるログ ファイルの名前に追加されます。  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |収集モードでツールを実行したときに作成された .xml 構成ファイルを含むフォルダーを指定します。手順 3 でこのパラメーターを使用した同じ値を使用します。  <br/> | `-ConfigurationLocation "c:\users\admin\ desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |削除モードでのログ ファイルをコピーするフォルダーを指定します。これは、省略可能なパラメーターです。それを含めない場合は、PST コレクション ツールをダウンロードしたフォルダーにログ ファイルがコピーされます。すべてのログ ファイルが同じフォルダーに保存されるように検索し、手順 1 と手順 3 での収集モードでツールを実行したときに使用したログの場所を検討してください。  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |この省略可能なスイッチでは、既存の PST コレクション ジョブの削除モードでツールを再実行することができます。削除モードでツールを実行していたかどうかは、検索モードでツールを再度実行します`ForceRestart`PST ファイルの場所を再スキャンに切り替えると、削除モードでツールを再実行し、見つかった場合がありました PST ファイルを削除するのにはこのスイッチを使用することができます、re scanned 場所です。使用する場合、`ForceRestart`削除モードでは、ツール内のスイッチは、以前の削除の操作を無視し、PST ファイルをもう一度削除しようとしています。<br/> | `-ForceRestart` <br/> 

    各パラメーターの実際の値を使用する DataCollectorMaster.exe ツールの構文の例を以下に示します。
    
    ```
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```
   
    コマンドを実行した後、手順 1 し、手順 3 で収集された PST ファイルを削除するの進行状況を示す詳細なステータス メッセージが表示するされます。しばらくして、最終的なステータス メッセージは、エラーと、ログがコピーされる場所はないかを示します。同じステータス メッセージは、.log ファイルにコピーされます。
    
### <a name="results-of-running-datacollectormasterexe-in-the-delete-mode"></a>削除モードで DataCollectorMaster.exe の実行結果

次のファイルが作成されで指定したフォルダーに格納されている削除モードで DataCollectorMaster.exe を正常に実行した後、`LogLocation`と`ConfigurationLocation`のパラメーターです。 
  
- **\<態\>_削除_\<DateTimeStamp\>.log** -ログ ファイルに表示されているステータス メッセージが含まれています。指定したフォルダーにこのファイルが作成、`LogLocation`のパラメーターです。 
    
- **\<態\>_削除_\<DateTimeStamp\>.xml** -XML ファイルにのみで使用されているツールが、削除モードで実行されたパラメーターの値に関する情報が含まれています。削除された PST ファイルの名前とファイルのパスも表示されます。指定したフォルダーにこのファイルが作成、`ConfigurationLocation`のパラメーターです。 
