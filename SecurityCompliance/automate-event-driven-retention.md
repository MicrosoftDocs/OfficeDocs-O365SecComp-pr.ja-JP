---
title: イベント ベースの保持を自動化する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: このトピックでは、Microsoft 365 REST API を使用して、イベントによってビジネス プロセス フローの自動化の保持をセットアップする方法について説明します。
ms.openlocfilehash: bfd33550eea447fb787ef981f9b0d7a36274b2cc
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410862"
---
# <a name="automate-event-based-retention"></a>イベント ベースの保持を自動化する

組織内のコンテンツの急増や、コンテンツが ROT (冗長、古い、無駄) になる可能性はビジネスにとって重大です。法、ビジネス、規制に関するコンプライアンスの課題に継続的に対応するには、企業は重要な情報を保持して保護し、関連性をすばやく見い出す必要があります。ビジネスを成功させるには、重要かつ適切な情報のみを保持することが鍵となります。

そのため、組織は Office 365 セキュリティ/コンプライアンス センターの保持ソリューションを活用できます。保持は、[保持ラベル](labels.md)を使用してトリガーできます。保持ラベルには、[特定のイベントに基づいて保持期間を設定する](event-driven-retention.md)オプションがあります。通常、保持期間は、コンテンツの作成日や最終変更日など既知の日付に基づきます。ただし、組織で、ある従業員が組織から離れてから 7 年後などの特定のイベントに基づいてコンテンツを破棄するという要件が生じることもあります。

コンテンツの破棄に対応するには、イベントが生じた時期を把握することが不可欠です。コンテンツ量が急激に増えると、適切なタイミングで準拠した方法でコンテンツを保持したり破棄したりすることが課題となります。

イベント ベースの保持はこの問題を解決できます。このトピックでは、Microsoft 365 REST API を使用して、イベントによりビジネス プロセス フローの保持の自動化をセットアップする方法について説明します。

## <a name="about-event-based-retention"></a>イベント ベースの保持について

組織の規模は小、中、大とさまざまです。日常的に作成および管理されるビジネス文書、法的文書、従業員のファイル、契約、製品文書は劇的に増えていきます。

たとえば、数十、数百単位の従業員が入社したり退社したりします。人事部はビジネス要件に基づいて従業員関連の文書を継続的に作成、更新、削除します。このプロセスは、会社で規定されている各種保持ポリシーの対象となります。

- **コンテンツの保持期間は既知の日付にすることことが可能です**。たとえば、コンテンツの作成日、最終変更日または最終ラベル設定日などです。文書を作成後 7 年間保持し、その後処分するなどが可能です。

- **またコンテンツの保持期間を不明な日付にすることもできます**。たとえば、保持ラベルを使用すると、従業員が組織を離れるなどの特定のイベントが生じる時点に基づいて保持期間を設定できます。

イベントによって保持時間が開始され、対象種類のイベントに適用されるラベルが付いたすべてのコンテンツに、そのラベルの保持アクションが実行されます。これを、イベント ベースの保持と呼びます。詳しくは、[イベント ベースの保持の概要](event-driven-retention.md)をご覧ください。

## <a name="set-up-event-based-retention"></a>イベント ベースの保持をセットアップする

このセクションでは、コンテンツを保持する前に実行する必要がある事柄について取り上げます。

### <a name="identify-roles"></a>役割を特定する

ビジネス文書の有効かつ効率的な保持に関して責任を担うレコード管理タスクを実行する、組織内の各種役割を特定します。

  | **ユーザー**| **役割**|
  | - | - |
  | セキュリティ/コンプライアンス センター管理者 | 保持イベントの種類、保持ラベル、レコード リポジトリを SharePoint で作成します |
  | レコード管理者                                  | 保持ポリシー、保持スケジュール ガイダンス、コンプライアンスの詳細を提供します   |
  | システム管理者 (会社)                          | Microsoft 365 を扱う外部システムをセットアップして管理します                       |
  | インフォメーション ワーカー                               | (人事、財務、IT など) ビジネス プロセスのライフ サイクルを管理します                 |

### <a name="set-up-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターをセットアップする
  
1. コンプライアンス管理者は、従業員が組織のメンバーでなくなる、契約の期限切れ、製品の有効期間などのイベントの種類を作成します ([イベント保持に関する記事](https://docs.microsoft.com/ja-JP/office365/securitycompliance/event-driven-retention)でステップごとのプロセスを参照してください)
    
1. コンプライアンス管理者は、イベントに基づいて保持ラベルを作成し、そのラベルをイベントの種類に関連付けます
    
1. 保持ラベルをトリガーするには以下の 4 種類があります。
            
    1. 作成日
                
    1. 最終更新日時
                
    1. ラベル日付 (コンテンツがラベル付けされた日)
                
    1. イベント ベース
    
1. コンプライアンス管理者がラベルを公開します

### <a name="set-up-sharepoint"></a>SharePoint をセットアップする
   
レコード リポジトリを作成するには、コンプライアンス管理者は次の操作を行います。

1. SharePoint サイトを作成します。

1. 次のいずれかを実行します。
        
    - SharePoint ライブラリを作成します。ライブラリ レベルでイベント ベースのラベルを設定します。詳しくは、[SharePoint ライブラリ、フォルダー、またはドキュメント セット内のすべてのコンテンツへの既定の保持ラベルの適用](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)をご覧ください。
          
    - SharePoint でドキュメント セットをセットアップします。詳しくは、[ドキュメント セットの概要](https://support.office.com/ja-JP/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234)をご覧ください。
      
1. 各従業員ドキュメント セットにアセット ID (アセット ID は組織が使用する製品名またはコードです。たとえば、従業員番号はアセット ID となります) を割り当てます。そのため、フォルダーにアセット ID を割り当て、そのフォルダー内のすべての項目が同じアセット ID を自動的に継承します。つまり、すべての項目に、同じイベントによってトリガーされた保持期間を設定できます。

## <a name="ways-to-trigger-event-based-retention"></a>イベント ベースの保持をトリガーする方法

イベント ベースの保持をトリガーするには 2 つの方法があります。

- **セキュリティ/コンプライアンス センター UI を使用する** このプロセスは、1 度に少量のコンテンツを保持したり、月または年単位など保持のトリガー頻度が多くない場合に使用できます。この方法について詳しくは、[イベント ベースの保持の概要](event-driven-retention.md)をご覧ください。ただし、この方法で保持をトリガーすると時間がかかり、エラーが発生し、スケーラビリティが阻害される可能性があります。そのため、保持をトリガーするための自動化されたシームレスなソリューションによって、データのセキュリティとコンプライアンスを強化できます。

- **M365 REST API を使用する** このプロセスは、1 度に大量のコンテンツを保持したり、保持をトリガーする頻度が毎日や週ごとなど多い場合に使用できます。このフローによって基幹業務システムでイベントが生じたタイミングが検出され、セキュリティ/コンプライアンス センターで関連するイベントが自動的に作成されます。該当するイベントが生じるたびに UI でイベントを手動で作成する必要はありません。

REST API の使用に関して次の 2 つのオプションがあります。

- **Microsoft Flow または同様のアプリケーション**を使用して、イベントを自動的にトリガーできます。Microsoft Flow は他のシステムとの接続のオーケストレーターです。Microsoft Flow の使用に際して、カスタム ソリューションは必要ありません。

- **PowerShell または HTTP クライアントを使用して REST API を呼び出す** PowerShell (バージョン 6 以降) を使用して Microsoft 365 REST API を呼び出してイベントを作成します。 

Rest API は一連の HTTP 操作 (メソッド) をサポートするサービス エンドポイントで、サービスのリソースに対する作成/取得/更新/削除のアクセス権を提供します。詳しくは、[REST API 要求/応答のコンポーネント](https://docs.microsoft.com/ja-JP/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)をご覧ください。この場合、Microsoft 365 REST API を使用することにより、POST および GET 操作 (メソッド) を使用してイベントを作成および取得できます。

## <a name="example-scenarios"></a>シナリオ例

次のシナリオについて考えます。

### <a name="scenario-1-employees-leaving-the-organization"></a>シナリオ 1: 従業員が組織のメンバーでなくなる 

ある組織は、従業員ごとに多数の従業員関連文書を作成し、保管しています。これらの文書は、各従業員の雇用期間中、管理および保持されます。ただし、従業員が組織のメンバーでなくなったり、従業員が退職したりすると、法的および会社の要件に基づいて、規定された期間、その従業員の文書を保持する義務が組織にはあります。

ここで、複数の従業員が毎日組織のメンバーでなくなるとすると、数千ではないものの数百もの文書の保持期間を毎日トリガーしなくてはなりません。

また、各従業員に関して保持期間を計算する必要もあります。従業員の退社日に、従業員レコードの種類に応じて、日、月、年数を加算します。たとえば、従業員の報酬に関する文書と同じ従業員の福利厚生申請書類では保持期間が異なる可能性があります。

次の図には、1 つのイベントに複数のラベルを関連付けられることを示しています。「従業員の報酬 (Worker’s compensation)」の下のすべてのファイルと、「従業員の福利厚生 (Employee benefits)」ラベルのすべてのファイルがどちらも、従業員が組織のメンバーでなくなるときの単一のイベントに関連付けられています。これら別々のファイルの保持期間は異なります。そのため、従業員が組織のメンバーでなくなると、各ラベルのファイルには異なる保持期間が適用されます。異なる種類のラベルまたは各従業員のラベルに対して異なる保持期間すべてをトリガーするのは、たいへん難しい作業となります。しかも複数の従業員に対してそうしなければなりません。

![イベントの種類、イベント、およびラベルの図](media/automate-event-driven-retention-event-diagram-employee-leaving.png)

そのため、複数の従業員に対して異なる保持期間をトリガーするプロセスを自動化すると、時間の節約になり、エラーがなくなり、非常に効率的となります。

**このシナリオに関する自動化されたイベント ベースの保持を構成する:**

![従業員が組織のメンバーでなくなるシナリオに関する役割とアクションの図](media/automate-event-driven-retention-employee-termination-diagram.png)

  - 管理者は Jane Doe、John Smith などの文書セットに従業員フォルダーを作成します。

  - 管理者は、福利厚生、給与、従業員報酬などの従業員ファイルを各従業員フォルダーに追加します

  - 管理者は、各従業員フォルダーにアセット ID を割り当てます。 

  - SCC 管理者は

  - セキュリティ/コンプライアンス センターにログインします

  - SCC 管理者は、「従業員の退職」、「従業員の雇用」イベントなどの従業員関連イベントの種類をセキュリティ/コンプライアンス センターで作成します。

  - SCC 管理者は、セキュリティとコンプライアンス センターで「従業員の保持」ラベルを作成します。

  - この「従業員の保持」ラベルを SharePoint で公開し、従業員ファイルに手動または自動で適用します。

  - Workday などの人事管理システムを Microsoft Flow と連携させ、従業員ファイルの管理を定期的に実行できます

  - 従業員が組織のメンバーではなくなると、Flow によって M365 イベント ベースの保持 REST API がトリガーされ、特定の従業員ファイルの保持期間が開始されます。

#### <a name="using-microsoft-flow"></a>Microsoft Flow の使用

手順 1 - Microsoft 365 REST API を使用してイベントを作成するフローを作成します

![Flow を使用してイベントを作成する](media/automate-event-driven-retention-flow-1.png)

![Flow を使用して REST API を呼び出す](media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a>イベントを作成する

REST API を呼び出すサンプル コード

<table>
<thead>
<tr class="header">
<th>メソッド</th>
<th>POST</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>URL</td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent)</td>
<td></td>
</tr>
<tr class="even">
<td>ヘッダー</td>
<td>Content-Type</td>
<td>application/atom+xml</td>
</tr>
<tr class="odd">
<td>本文</td>
<td><p>&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</p>
<p>&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</p>
<p>xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</p>
<p>xmlns='http://www.w3.org/2005/Atom'&gt;</p>
<p>&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</p>
<p>&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</p>
<p>&lt;content type='application/xml'&gt;</p>
<p>&lt;m:properties&gt;</p>
<p>&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</p>
<p>&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</p>
<p>&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</p>
<p>&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</p>
<p>&lt;/m:properties&gt;</p>
<p>&lt;/content&gt;</p>
<p>&lt;/entry&gt;</p></td>
<td></td>
</tr>
<tr class="even">
<td>認証</td>
<td>基本</td>
<td></td>
</tr>
<tr class="odd">
<td>ユーザー名</td>
<td>“Complianceuser”</td>
<td></td>
</tr>
<tr class="even">
<td>パスワード</td>
<td>“Compliancepassword”</td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a>利用可能なパラメーター

<table>
<thead>
<tr class="header">
<th><strong>パラメーター</strong></th>
<th><strong>説明</strong></th>
<th><strong>メモ</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>&lt;d:Name&gt;&lt;/d:Name&gt;</td>
<td>イベントの一意の名前を入力します。</td>
<td>末尾にスペースおよび以下の文字を含めることはできません: % * \ &amp; &lt; &gt; | # ? , : ;</td>
</tr>
<tr class="even">
<td>&lt;d:EventType&gt;&lt;/d:EventType&gt;</td>
<td>イベントの種類の名前 (または GUID) を入力します。</td>
<td>例: 「従業員の退職」というイベントの種類を保持ラベルに関連付ける必要があります。</td>
</tr>
<tr class="odd">
<td>&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</td>
<td>“ComplianceAssetId:” と従業員 ID を入力します</td>
<td>例: &quot;ComplianceAssetId:12345&quot;</td>
</tr>
<tr class="even">
<td>&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</td>
<td>イベントの日時</td>
<td><p>形式: yyyy-MM-ddTHH:mm:ssZ。例:</p>
<p>2018-12-01T00:00:00Z</p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a>応答コード

| **応答コード** | **説明**       |
| ----------------- | --------------------- |
| 302               | リダイレクト              |
| 201               | 作成済み               |
| 403               | 承認に失敗しました  |
| 401               | 認証に失敗しました |

##### <a name="get-events-based-on-time-range"></a>時間範囲に基づいてイベントを取得する

<table>
<thead>
<tr class="header">
<th>メソッド</th>
<th>GET</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>URL</td>
<td><ol start="4" type="1">
<li><p>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td>ヘッダー</td>
<td>Content-Type</td>
<td>application/atom+xml</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>認証</td>
<td>基本</td>
<td></td>
</tr>
<tr class="odd">
<td>ユーザー名</td>
<td>“Complianceuser”</td>
<td></td>
</tr>
<tr class="even">
<td>パスワード</td>
<td>“Compliancepassword”</td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a>応答コード

| **応答コード** | **説明**                   |
| ----------------- | --------------------------------- |
| 200               | 問題ありません。イベントの一覧は atom+ xml 形式です |
| 404               | 見つかりません                         |
| 302               | リダイレクト                          |
| 401               | 承認に失敗しました              |
| 403               | 認証に失敗しました             |

##### <a name="get-an-event-by-id"></a>ID でイベントを取得する

| メソッド         | GET   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| URL            | [https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\)) |                      |
| ヘッダー         | Content-Type                                                                                                                                                                                                                                                       | application/atom+xml |
| 認証 | 基本                                                                                                                                                                                                                                                              |                      |
| ユーザー名       | “Complianceuser”                                                                                                                                                                                                                                                   |                      |
| パスワード       | “Compliancepassword”                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a>応答コード

| **応答コード** | **説明**                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | 問題ありません。応答本体に atom+xml 形式のイベントが含まれています |
| 404               | 見つかりません                                            |
| 302               | リダイレクト                                             |
| 401               | 承認に失敗しました                                 |
| 403               | 認証に失敗しました                                |

##### <a name="get-an-event-by-name"></a>名前でイベントを取得する

| メソッド         | GET       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| URL            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| ヘッダー        | Content-Type                                                                                                                                 | application/atom+xml |
| 認証 | 基本                                                                                                                                        |                      |
| ユーザー名       | “Complianceuser”                                                                                                                             |                      |
| パスワード       | “Compliancepassword”                                                                                                                         |                      |

##### <a name="response-codes"></a>応答コード

| **応答コード** | **説明**                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | 問題ありません。応答本体に atom+xml 形式のイベントが含まれています |
| 404               | 見つかりません                                            |
| 302               | リダイレクト                                             |
| 401               | 承認に失敗しました                                 |
| 403               | 認証に失敗しました                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a>PowerShell (ver.6 以降) または任意の HTTP クライアントの使用

手順 1: PowerShell に接続します。

手順 2: 次のスクリプトを実行します。

<table>
<tbody>
<tr class="odd">
<td><p>param([string]$baseUri)</p>
<p>$userName = &quot;UserName&quot;</p>
<p>$password = &quot;Password&quot;</p>
<p>$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</p>
<p>$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</p>
<p>$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</p>
<p>Write-Host &quot;Start to create an event with name: $EventName&quot;</p>
<p>$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</p>
<p>&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</p>
<p>xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</p>
<p>xmlns='http://www.w3.org/2005/Atom'&gt;</p>
<p>&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</p>
<p>&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</p>
<p>&lt;content type='application/xml'&gt;</p>
<p>&lt;m:properties&gt;</p>
<p>&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</p>
<p>&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</p>
<p>&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</p>
<p>&lt;/m:properties&gt;</p>
<p>&lt;/content&gt;</p>
<p>&lt;/entry&gt;&quot;</p>
<p>$event = $null</p>
<p>try</p>
<p>{</p>
<p>$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</p>
<p>}</p>
<p>catch</p>
<p>{</p>
<p>$response = $_.Exception.Response</p>
<p>if($response.StatusCode -eq &quot;Redirect&quot;)</p>
<p>{</p>
<p>$url = $response.Headers.Location</p>
<p>Write-Host &quot;redirected to $url&quot;</p>
<p>$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</p>
<p>}</p>
<p>}</p>
<p>$event | fl *</p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a>両方のオプションの結果を確認する

手順 1: セキュリティ/コンプライアンス センターに移動します

手順 2: [データ ガバナンス] の [イベント] をクリックします

手順 3: イベントが作成されていることを確認します。

同様に、イベント ベースの保持を自動化する上記のオプションを以下のシナリオに使用することもできます。

### <a name="scenario-2-contracts-expiring"></a>シナリオ 2: 契約の期限切れ

組織には、顧客、ベンダー、パートナーとの単一の契約向けの複数のレコードが存在することがあります。こうした文書は、SharePoint などの文書ライブラリに格納できます。契約の終了は、対象の契約に関連付けられている文書の保持期間の開始時期に基づいて判別されます。たとえば、契約に関連するすべてのレコードは契約の有効期限後、5 年間は保持する必要があります。契約の期限切れは、5 年間の保持期間をトリガーするイベントとなります。

顧客関係管理 (CRM) システムを Microsoft 365 と連携させ、契約文書の保持をトリガーできます。

**このシナリオに関する自動化されたイベント ベースの保持を構成する:**

![契約の有効期限シナリオの役割とタスクの図](media/automate-event-driven-retention-contract-expiration.png)

  - 管理者は、契約の種類ごとにさまざまなフォルダーを含む SharePoint ライブラリを作成します。

  - 管理者は、ライセンス契約書、開発契約などの契約ファイル意を各契約フォルダーに追加します

  - 管理者は、各契約フォルダーにアセット ID を割り当てます

  - SCC 管理者がセキュリティ/コンプライアンス センターにログインします

  - SCC 管理者は、「契約作成」、「契約の有効期限」イベントなどの契約関連イベントの種類をセキュリティ/コンプライアンス センターで作成します。

  - SCC 管理者は、セキュリティとコンプライアンス センターで「契約の有効期限」ラベルを作成します。

  - この「契約の有効期限」ラベルを SharePoint で公開し、契約ファイルに手動または自動で適用します

  - 契約管理システムを Microsoft Flow または同様のアプリケーションと連携させ、契約ファイルの管理を定期的に実行できます

  - 契約の期限が切れると、Microsoft Flow によって M365 イベント ベースの保持 REST API がトリガーされ、特定の契約ファイルの保持期間が開始されます。

### <a name="scenario-3-end-of-product-manufacturing"></a>シナリオ 3: 製品製造の終了

さまざまな製品群を生み出す製造企業は、多数の製造仕様と価格に関する文書を作成します。製品が製造されなくなると、その製品にリンクされているすべての仕様と文書は、製品のライフサイクル後、特定に期間にわたり保持する必要があります。

エンタープライズ リソース プランニング (ERP) システムを Microsoft 365 および Microsoft Flow と連携させ、保持をトリガーできます。

**このシナリオに関する自動化されたイベント ベースの保持を構成する:**

![製品のライフサイクル シナリオの役割とタスクの図](media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - 管理者は、製品 1、製品 2 などの製品フォルダーを文書セットに作成します。

  - 管理者は、「製造仕様」、「製品価格」、「製品ライセンス」などの製品ファイルを各製品フォルダーに追加します

  - 管理者は、各製品フォルダーにアセット ID を割り当てます。

  - SCC 管理者がセキュリティ/コンプライアンス センターにログインします

  - SCC 管理者は、「製品製造の開始」、「製品製造の終了」イベントなどの製品関連イベントをセキュリティ/コンプライアンス センターで作成します。

  - SCC 管理者は、セキュリティとコンプライアンス センターで「製品製造の終了」ラベルを作成します。

  - この「製品製造の終了」ラベルを SharePoint で公開し、製品ファイルに手動または自動で適用します

  - ERP システムを Microsoft Flow または同様のアプリケーションと連携させ、製品ファイルの管理を定期的に実行できます

  - 製品製造が終了すると、Microsoft Flow によって M365 イベント ベースの保持 REST API がトリガーされ、特定の製品ファイルの保持期間が開始されます。

## <a name="appendix"></a>付録

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a>リダイレクト 302 応答結果を使用して REST API を呼び出す

1.  REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> を使用して、POST 保持イベント呼び出しを実行します (全体管理者のアクセス許可が必要です)

2.  応答コードを確認し、302 の場合、応答ヘッダーの場所プロパティから、リダイレクトされた URL を取得します

3.  リダイレクトされた URL を使用して、もう一度 POST 保持イベント呼び出しを実行します。

## <a name="credits"></a>開発者情報

このトピックの校閲者をご紹介します。

Antonio Maio<br/>Microsoft Office アプリとサービスの MVP<br/> Antonio.Maio@Protiviti.com
