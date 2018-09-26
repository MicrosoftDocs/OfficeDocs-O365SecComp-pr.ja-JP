---
title: 電子情報開示ワークフローにおけるコンテンツ検索の使用
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: 'PowerShell スクリプトを使用して、Office 365 のセキュリティで作成した検索に基づいて Exchange Online の埋め込みの電子的証拠開示検索を作成する&amp;コンプライアンス センターです。 '
ms.openlocfilehash: 42af94ce850736dede52e619c240bb9e0a6f7031
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038070"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a>電子情報開示ワークフローにおけるコンテンツ検索の使用

コンテンツの検索機能は、Office 365 のセキュリティ&amp;コンプライアンス センターでは、組織内のすべてのメールボックスを検索することができます。(、最大 10,000 のメールボックスを検索することができます) し、Exchange オンラインの場で電子的証拠開示とは異なり 1 回の検索の対象メールボックスの数に制限はありません。組織全体の検索を実行する必要がある場合、すべてのメールボックスを検索するコンテンツの検索を使用できます。上に配置するメールボックスを保持し、エクスポートする検索結果などの他の電子的証拠開示に関連するタスクを実行するのには、インプレース電子証拠開示のワークフロー機能を使用することができます。たとえば、訴訟事件に応答性の高い特定の通告を識別するすべてのメールボックスを検索する必要があるとします。セキュリティ コンテンツの検索を使用することができます&amp;ケースに応答性の高いものを識別するのには、組織内のすべてのメールボックスを検索するコンプライアンス センターです。移行元のメールボックスとして Exchange Online の埋め込みの電子的証拠開示検索の管理者のメールボックスの一覧を使用できます。使用して、インプレース電子証拠開示では、それらのソース メールボックスに対して設定、検出メールボックスに検索結果をコピーし、検索結果をエクスポートすることもできます。
  
このトピックには、ソース メールボックスと、セキュリティで作成した検索の検索クエリの一覧を使用して、Exchange Online の埋め込みの電子的証拠開示検索を作成する場合に実行するスクリプトが含まれています&amp;コンプライアンス センターです。プロセスの概要を以下に示します。
  
[手順 1: 組織内のすべてのメールボックスを検索するためのコンテンツ検索を作成する](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[手順 2: セキュリティを保護する接続を使用する&amp;コンプライアンス センターおよびリモート PowerShell セッションを 1 つで Exchange のオンライン](#step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[手順 3: コンテンツ検索に基づいてインプレースの電子情報開示検索を作成するスクリプトを実行する](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[手順 4: インプレースの電子情報開示検索を開始する](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a>手順 1: 組織内のすべてのメールボックスを検索するためのコンテンツ検索を作成する

最初の手順は、セキュリティを使用する&amp;コンプライアンス センター (またはセキュリティとコンプライアンス センター PowerShell)、組織内のすべてのメールボックスを検索するコンテンツの検索を作成します。コンテンツの検索を 1 つのメールボックスの数に制限はありません。検索には、調査に関連する元のメールボックスのみが返されるように、適切なキーワード クエリ (または機密性の高い情報の種類のクエリ) を指定します。必要に応じて、検索結果および返された元のメールボックスの範囲を絞り込むには検索クエリを絞り込みます。
  
> [!NOTE]
> コンテンツ検索のソースから結果が何も返らない場合には、手順 3 でこのスクリプトを実行してもインプレースの電子情報開示が作成されません。検索クエリに変更を加えてからコンテンツ検索を再実行し、検索結果が返るようにする必要があります。 
  
### <a name="use-the-security-amp-compliance-center-to-search-all-mailboxes"></a>セキュリティを使用して、&amp;のすべてのメールボックスを検索するコンプライアンス センター

1. [には、Office 365 のセキュリティ&amp;コンプライアンス センター](go-to-the-securitycompliance-center.md)です。 
    
2. クリックして**検索&amp;調査**、**コンテンツの検索**] をクリックし、**新規**![追加アイコン](media/O365-MDM-CreatePolicy-AddIcon.gif)。
    
3. **[新規検索]** ページで、コンテンツ検索の名前を入力します。 
    
4. **[どこを調べますか?]** にある **[すべてのメールボックスを検索する]** をクリックし、**[次へ]** をクリックします。
    
5. の下のボックスで**たい項目を検索することですか?**、ボックスに検索クエリを入力します。キーワード、プロパティは次のように送信し、日付、またはファイル名などのドキュメント プロパティ、またはドキュメントが最後に変更された日付を受信したメッセージを指定できます。ブール演算子の AND、OR などを使用していない、または近くより複雑なクエリを使用することができますかなどの機密情報 (社会保障番号) でメッセージを検索することもできます。検索クエリを作成する方法の詳細については、[コンテンツ検索用のキーワード クエリ](keyword-queries-and-search-conditions.md)を参照してください。
    
6. **[検索]** をクリックして、検索設定を保存して検索を開始します。 
    
    詳細ペインで、しばらくして、検索結果の推定値が表示されます。見積には、検索結果の項目数と合計サイズが含まれます。検索が完了したら、検索結果をプレビューできます。**更新**] をクリックして、必要に応じて![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif)の詳細ウィンドウの情報を更新します。 
    
7.  また必要であれば、検索クエリを調整し、検索結果の範囲を絞り込んでから、検索を再開します。 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a>セキュリティとコンプライアンス センター PowerShell を使用して、すべてのメールボックスを検索するには

組織内のすべてのメールボックスを検索するのには**新規 ComplianceSearch**コマンドレットを使用することもできます。まず[Office 365 のセキュリティへの接続&amp;コンプライアンス センター PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084)。
  
ここでは、PowerShell を使用して、組織内のすべてのメールボックスを検索する例です。検索クエリでは、2015 年 1 月 1 日、2015 年 6 月 30 日間で送信されるすべてのメッセージとは、[財務レポートの件名欄に語句を含むを返します。最初のコマンドは、検索を作成し、2 番目のコマンドは、検索を実行します。 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

詳細については、「[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935)」を参照してください。
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a>コンテンツ検索におけるソース メールボックスの数を確認する

コンテンツの検索には、最大 1,000 個のソース メールボックスを含む検索結果が返されます。検索クエリに一致するコンテンツを含む複数の 1,000 個のメールボックスがある場合は、前の手順で作成したコンテンツの検索に多くの検索結果を上位 1,000 名のメールボックスのみが含まれます。1,000 を超えるメールボックスに検索結果が含まれている場合は、手順 3 で作成した新しい場所に電子的証拠開示検索をコピーするソース メールボックスの一覧で、これらのメールボックスのいくつか含まれません。 
  
以上 1,000 のソース メールボックスのコンテンツの検索を作成するために、手順 1 で作成したコンテンツの検索によって返されたソース メールボックスを検索結果を含む) の数を表示するスクリプトを実行するのにはこの手順を実行します。 
  
1. .Ps1 のファイル名のサフィックスを使用して、PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、という名前のファイルに保存することが`SourceMailboxes.ps1`。
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
                  "Please wait until the search finishes.";
                  break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
                  "The Content Search " + $SearchName + " didn't return any useful results.";
                  break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  "Number of mailboxes that have search hits: " + $mailboxes.Count
  ```

2. セキュリティ/コンプライアンス センター PowerShell で、前の手順で作成したスクリプトがある場所のフォルダーに移動し、実行スクリプトです。例えば：
    
    ```
    .\SourceMailboxes.ps1
    ```

3. スクリプトによってプロンプトが表示されたら、手順 1 で作成したコンテンツ検索の名前を入力します。
    
    スクリプトによって、検索結果が含まれるソース メールボックスの数が示されます。
    
ソースの 1,000 を超えるメールボックスが存在する場合は、コンテンツの検索を 2 つ (以上) を作成してください。たとえば、1 つのコンテンツの検索とコンテンツの検索を別の残りの半分で、組織のメールボックスの半分を検索します。検索結果が含まれているメールボックスの数を減らすために検索条件を変更することもできます。たとえば、日付の範囲が含まれます。 またはキーワード クエリを変更できます。
  
## <a name="step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>手順 2: セキュリティを保護する接続を使用する&amp;コンプライアンス センターおよびリモート PowerShell セッションを 1 つで Exchange のオンライン

次の手順は、両方のセキュリティを保護する Windows PowerShell を接続する&amp;コンプライアンス センターおよび Exchange Online 組織にします。これは、手順 3 で実行するスクリプトが、セキュリティでコンテンツの検索のコマンドレットへのアクセスを必要とするために必要な&amp;コンプライアンス センターおよび Exchange Online の埋め込み電子的証拠開示のコマンドレットです。
  
1. .Ps1 のファイル名のサフィックスを使用して、Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、という名前のファイルに保存することが`ConnectEXO-CC.ps1`。
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. ローカル コンピューターに Windows PowerShell を開く前の手順で作成したスクリプトがある場所のフォルダーに移動し、スクリプトを実行し、例えば：
    
    ```
    .\ConnectEXO-CC.ps1
    ```

知るかどうかは次のとおりですか。セキュリティのコマンドレット、スクリプトを実行した後に&amp;コンプライアンス センターおよび Exchange Online は、ローカル PowerShell セッションにインポートされます。エラーを受信しない場合、接続に成功しました。簡単なテストは、セキュリティを実行する&amp;コンプライアンス センター コマンドレット:**インストール UnifiedCompliancePrerequisite**などの — と**Get メールボックス**などの Exchange Online のコマンドレット。 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a>手順 3: コンテンツ検索に基づいてインプレースの電子情報開示検索を作成するスクリプトを実行する

デュアルの PowerShell セッションを作成するには手順 2 で後、は、埋め込みの電子的証拠開示検索に、既存のコンテンツの検索を変換するスクリプトを実行します。スクリプトを以下に示します。
  
- 変換するコンテンツ検索の名前を求めるプロンプトを表示します。
    
- コンテンツ検索の実行が完了したことを確認します。コンテンツ検索が何も結果を返さず、インプレースの電子情報開示検索が作成されない場合には、
    
- 検索結果を含むコンテンツ検索に基づくソース メールボックスの一覧を変数に保存します。
    
- 以下のプロパティが設定されたインプレースの電子情報開示検索を新たに作成します。新しい検索が開始されていないことに注目してください。手順 4 で開始します。
    
  - **名前**- 新しい検索の名前がこの形式を使用:\<コンテンツの検索の名前を\>_MBSearch1。検索は名前を付ける場合は、スクリプトを再度実行して同じソース コンテンツの検索を使用して、\<コンテンツの検索の名前を\>_MBSearch2。
    
  - **ソース メールボックス**のコンテンツの検索から検索結果を含むすべてのメールボックス。 
    
  - **検索クエリ**の検索では、コンテンツの検索から検索クエリを使用します。コンテンツの検索には、すべてのコンテンツ (検索クエリは空白) が含まれている場合、新たに検索では空の [検索クエリされ移行元のメールボックス内のすべてのコンテンツが含まれます。 
    
  - **推定のみの検索**に新しい検索は、見積もり専用のサーチとマークされます。コピーすることの検索結果探索メールボックスにそれを起動した後。 
    
1. Ps1 のファイル名のサフィックスを使用して、Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、という名前のファイルに保存することが`CreateMBSearchFromComplianceSearch.ps1`。
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName,
      [switch]$original,
      [switch]$restoreOriginal
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
    "Please wait until the search finishes";
    break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
    "The Content Search " + $SearchName + " didn't return any useful results";
    "A mailbox search object wasn't created";
    break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  $msPrefix = $SearchName + "_MBSearch";
  $I = 1;
  $mbSearches = Get-MailboxSearch;
  while ($true)
  {
      $found = $false;
      $mbsName = "$msPrefix$I";
      foreach ($mbs in $mbSearches)
      {
          if ($mbs.Name -eq $mbsName)
          {
              $found = $true;
              break;
          }
      }
      if (!$found)
      {
          break;
      }
      $I++;
  }
  $query = $search.KeywordQuery;
  if ([string]::IsNullOrWhiteSpace($query))
  {
      $query = $search.ContentMatchQuery;
  }
  if ([string]::IsNullOrWhiteSpace($query))
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -EstimateOnly;
  }
  else
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -SearchQuery $query -EstimateOnly;
  }
  
  ```

2. 手順 2 で作成した Windows PowerShell セッションで前の手順で作成したスクリプトがある場所のフォルダーに移動し、スクリプトを実行し、例えば：
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. スクリプトによってメッセージが表示されたら、埋め込みの電子的証拠開示検索 (たとえば、検索手順 1 で作成した) に変換するコンテンツの検索の名前を入力し、 **Enter**キーを押します。
    
    スクリプトが正常に実行されると、新しいインプレースの電子情報開示検索が **NotStarted** というステータスで作成されます。  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` コマンドを実行し、新しい検索のプロパティを表示します。 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a>手順 4: インプレースの電子情報開示検索を開始する

手順 3 で実行したスクリプトでは新しいインプレースの電子情報開示検索が作成されますが、検索は開始しません。この手順では、検索を開始して検索結果の推定値を取得します。
  
1. Exchange 管理センター (EAC) では、**コンプライアンスの管理**に移動\>**インプレース電子情報開示&amp;を保持**。
    
2. 一覧表示から、手順 3 で作成したインプレースの電子情報開示検索を選択します。
    
3. [**検索**] をクリックして![検索アイコン](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)\>検索を開始し、検索によって返される項目数と合計サイズの推定値を返す**検索結果の推定値**です。 
    
    見積もりは、詳細ペインに表示されます。[**更新**] をクリックして![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif)詳細ペインに表示される情報を更新します。 
    
4. 検索が完了した後で結果をプレビューするには、詳細ウィンドウで [ **検索結果のプレビュー**] をクリックします。
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a>インプレースの電子情報開示検索の作成と実行後の手順

手順 3 でスクリプトによって作成されたインプレースの電子情報開示検索を開始した後は、通常のインプレースの電子情報開示ワークフローを使用して、検索結果で各種の電子情報開示アクションを実行できます。
  
### <a name="create-an-in-place-hold"></a>インプレース保持を作成する

1. **コンプライアンス管理**には、EAC で\>**インプレース電子情報開示&amp;を保持**。
    
2. リスト ビューで、手順 3 で作成した埋め込み電子的証拠開示検索を選択し、[**編集**] をクリックして![[編集] アイコン](media/O365_MDM_CreatePolicy_EditIcon.gif)。
    
3. [ **インプレース保持**] ページで、[ **選択したメールボックス内の検索クエリに一致したコンテンツを保持する**] チェック ボックスをオンにして、次のいずれかのオプションを選択します。 
    
  - **無期限に保持**無限の保留中の検索で返される項目を配置するには、このオプションを選択します。保留中のアイテムは、検索対象からメールボックスを削除するか、または検索を削除するまで保持されます。 
    
  - **、受信した日を基準にして項目を保持する日数を指定する**- 特定の期間の項目を保持するには、このオプションを選択します。期間は、メールボックス アイテムの受信または作成した日付から計算されます。 
    
4. [ **保存**] をクリックしてインプレース保持を作成し、検索を再開します。 
    
[Return to top](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a>検索結果をコピーする

1. **コンプライアンス管理**には、EAC で\>**インプレース電子情報開示&amp;を保持**。
    
2. リスト表示から、手順 3 で作成したインプレースの電子情報開示検索を選択します。
    
3. [**検索**] をクリックして![検索アイコン](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)、ドロップ ダウン リストから**検索結果のコピー** ] をクリックします。 
    
4. **[検索結果のコピー]** で、次のオプションの中から選択します。
    
    - **検索できないアイテムを含む**、メールボックス アイテム (たとえば、Exchange の検索でインデックスを作成することができませんでした、ファイルの種類の添付ファイル付きメッセージ) は、検索できませんでしたを含めるには、このチェック ボックスを選択します。 
    
    - **重複除外を有効にする**- メッセージの重複を除外するには、このチェック ボックスをオンします。メッセージの単一のインスタンスのみが探索メールボックスにコピーされます。 
    
    - **完全にログ記録を有効にする**- このチェック ボックスをオンにすべてのログを検索結果に含めます。 
    
    - **コピーが完了したときにメールを送って**の検索が完了したときに電子メール通知を取得するには、このチェック ボックスをオンします。 
    
    - **この検出メールボックスに結果をコピー** - をクリックして探索メールボックスを検索する場所を選択する**参照**をコピーします。 
    
5. **[コピー]** をクリックして検索結果を指定された探索メールボックスにコピーするプロセスを開始します。 
    
6. [**更新**] をクリックして![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif)詳細ペインに表示されているコピーの状態に関する情報を更新します。 
    
7. コピーが完了したら、[ **開く**] をクリックして、検索結果を表示する探索メールボックスを開きます。 
  
### <a name="export-the-search-results"></a>検索結果をエクスポートする

1. **コンプライアンス管理**には、EAC で\>**インプレース電子情報開示&amp;を保持**。
    
2. 一覧表示から、手順 3 で作成したインプレースの電子情報開示検索を選択し、[ **PST ファイルにエクスポートする**] をクリックします。
    
3. **[電子情報開示の PST エクスポート ツール]** ウィンドウで、次の操作を行います。 
    
    - **[参照]** をクリックして、PST ファイルをダウンロードする場所を指定します。 
    
    - **[重複除外を有効にする]** チェックボックスをクリックして重複メッセージを除外します。PST ファイルにメッセージの単一インスタンスのみを含めるには。 
    
    - **[検索不能アイテムを含める]** チェック ボックスをオンにすると、検索できなかったメールボックス アイテム (たとえば、Exchange 検索でインデックスが作成できなかった種類のファイルが添付されたメッセージ) が含まれます。検索できないアイテムは、別の PST ファイルにエクスポートされます。 
    
4. **[開始]** をクリックして、検索結果を PST ファイルにエクスポートします。 
    
    エクスポート プロセスに関するステータス情報が含まれているウィンドウが表示されます。
