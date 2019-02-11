---
title: Office 365 での電子情報開示調査のためにコンプライアンスの境界を設定する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: コンプライアンスの境界を使用して、Office 365 組織内で、電子的証拠開示マネージャーが検索できるユーザー コンテンツの場所を制御する論理的な境界を作成します。コンプライアンスの境界を使用して、検索のアクセス許可がどのようなメールボックス、SharePoint サイトを制御する (も呼び出されたコンプライアンス セキュリティ フィルター) をフィルタ リングし、OneDrive アカウントは、特定のユーザーによって検索できます。
ms.openlocfilehash: 23594673e70be4b960c463ae2344c2f4b0fd0cbe
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29768018"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a>Office 365 での電子情報開示調査のためにコンプライアンスの境界を設定する

コンプライアンスの境界では、Office 365 組織内のユーザー コンテンツの場所 (メールボックス、SharePoint サイトでは、OneDrive アカウントなど) 電子的証拠開示マネージャーが検索できるを制御する論理的な境界を作成します。さらに、コンプライアンスの境界管理、法務、人事管理、または組織内の他の調査を管理するために使用される電子的証拠開示の場合にアクセスできるユーザーです。コンプライアンスの境界の必要性は必要なは、地理的な boarders や規制を尊重する必要がある複数の国の企業および政府機関は、さまざまな政府機関は、多くの場合がよくあります。Office 365 に対応できるコンプライアンスの境界のようにこれらの要件を実行すると、コンテンツの検索と電子的証拠開示のサポート案件の管理の調査。
  
コンプライアンスの境界がどのように動作するかを説明するのに次の図の例を使用します。
  
![コンプライアンスの境界で構成されているアクセス許可の検索フィルターの機関や管理者の役割へのアクセス制御グループの eDisocovery の場合にアクセスを制御すること](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
この例では、Contoso 社は、Fourth Coffee とコーホー ワイナリーの 2 つの子会社で構成される Office 365 組織です。マネージャーの電子的証拠開示および調査官しか検索 Exchange メールボックス、OneDrive のアカウント、および SharePoint サイトの広告代理店のビジネスが必要です。さらに、電子的証拠開示マネージャーおよび調査官のみを確認できます電子的証拠開示の場合、その機関でのみのメンバーがいる場合をアクセスすることができ、。コンプライアンスの境界がこれらの要件に対応する方法を次に示します。
  
- コンテンツの検索コントロールの機能を電子的証拠開示マネージャーと調査官が検索できるコンテンツの場所にフィルタ リング検索のアクセス許可。これは、電子的証拠開示マネージャーと Fourth Coffee の広告代理店の調査官しか検索コンテンツの場所、Fourth Coffee の子会社のことを意味します。コーホー ワイナリーの関連会社に同じ制限が適用されます。
    
    ロールは、Office 365 のセキュリティで電子的証拠開示の場合を見ることができるコントロールをグループ化&amp;コンプライアンス センターです。これは、電子的証拠開示マネージャーおよび調査官だけを見られる、政府機関で電子的証拠開示の場合を意味します。
    
- 役割グループ、ユーザー、電子的証拠開示の場合にメンバーを割り当てることができますを制御します。これは、電子的証拠開示マネージャーおよび調査官のみに割り当てることがメンバーのメンバーは、自身の場合を意味します。
    
コンプライアンスの境界を設定するためのプロセスを以下に示します。
  
[ステップ 1: 政府機関を定義するのにはユーザーの属性を識別します。](#step-1-identify-a-user-attribute-to-define-your-agencies)

[手順 2: ファイルの OneDrive アカウントにユーザーの属性を同期するには、マイクロソフトのサポートと要求](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[手順 3: 各機関の役割グループを作成します。](#step-3-create-a-role-group-for-each-agency)

[手順 4: コンプライアンスの境界を適用する検索のアクセス許可フィルターを作成します。](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[機関内の調査の電子的証拠開示のケースを作成する手順 5。](#step-5-create-an-ediscovery-case-for-an-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>ステップ 1: 政府機関を定義するのにはユーザーの属性を識別します。

最初のステップでは、Azure Active Directory 属性を使用するを選択するのには、政府機関を定義します。電子情報開示を制限する検索のアクセス許可フィルターを作成するには、この属性に特定の値が割り当てられているユーザーのコンテンツの場所のみを検索するにはマネージャーには、この属性が使用されます。たとえば、contoso 社**所属**の属性を使用することを決定したとします。Fourth Coffee の関連会社内のユーザーに対しては、この属性の値になります`FourthCoffee`「コーホーワイナリー」と関連会社でユーザー値なると`CohoWinery`。手順 4 で、これを使用します`attribute:value`ユーザーを制限するための組み合わせ (たとえば、*部門: FourthCoffee* ) コンテンツの電子的証拠開示マネージャーが検索できる場所です。 
  
境界を遵守するために使用できる Azure Active Directory ユーザー属性の一覧を以下に示します。
  
- Company
    
- CustomAttribute1 - CustomAttribute15
    
- 部署
    
- 事業所
    
多くのユーザー属性は、メールボックスで使用できる、特に Exchange が、上記の属性は、OneDrive で現在サポートされているだけのものです。
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>手順 2: ファイルの OneDrive アカウントにユーザーの属性を同期するには、マイクロソフトのサポートと要求

組織の OneDrive のすべてのアカウントに手順 1 で選択した Azure Active Directory 属性を同期するのにはマイクロソフトのサポートの要求をファイルには、次の手順です。この同期が発生した場合、属性とその値) という名前の SharePoint で非表示の管理プロパティにマップする手順 1 で選択した`ComplianceAttribute`。手順 4 で OneDrive の検索のアクセス許可フィルターを作成するのには、この属性を使用します。
  
マイクロソフトのサポート要求を送信する場合については、次のとおりです。
  
- Office 365 組織の既定のドメイン名
    
- (手順 1) から Azure Active Directory 属性の名前
    
- 次のタイトルまたはサポート要求の目的の説明:」を有効にする OneDrive のビジネス同期と Azure アクティブ ディレクトリのコンプライアンス セキュリティ フィルター」です。要求を実装する Office 365 電子的証拠開示エンジニア リング チームに要求をルーティングするのに役立ちます。
    
エンジニア リングの変更が加えられるし、属性が OneDrive に同期されている、マイクロソフトのサポート送信するとビルド番号に変更が加えられたと展開の予定日です。展開プロセスは、サポート リクエストを送信した後、4 ~ 6 週間を通常は注意してください。
  
 **重要な:** 変更を展開する前に、手順 5 から手順 3 を完了できます。変更が配置された後まで検索のアクセス許可のフィルターで指定されている OneDrive のサイトからドキュメントを返すコンテンツの検索を実行しているされません。 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>手順 3: 各機関の役割グループを作成します。

次の手順は、Office 365 のセキュリティの役割グループを作成する&amp;、政府機関の連携はコンプライアンス センターです。コピーして、組み込みの電子的証拠開示マネージャー グループ、メンバーの追加、適切なお客様のニーズに該当することができない可能性があるロールを削除する新しい役割グループを作成することをお勧めします。電子的証拠開示に関連する役割の詳細についてを参照してください[Office 365 のセキュリティ、電子的証拠開示のアクセス許可を割り当てる&amp;コンプライアンス センター](assign-ediscovery-permissions.md)です。
  
役割グループを作成するには、セキュリティの**アクセス許可**] ページに移動&amp;コンプライアンス センター調査を管理するためにコンプライアンスの境界および電子的証拠開示のサポート案件を使用する各省庁の各チームの役割グループを作成します。 
  
Contoso のコンプライアンスの境界を使用すると、4 つの役割グループを作成する必要があるし、それぞれに適切なメンバーを追加します。
  
- 4 番目のコーヒーの電子的証拠開示マネージャー
    
- コーヒー 4 つ目の調査官
    
- Coho Winery 電子的証拠開示マネージャー
    
- Coho Winery 調査官
    

  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>手順 4: コンプライアンスの境界を適用する検索のアクセス許可フィルターを作成します。
<a name="step4"> </a>

各機関の役割グループを作成したら、次の手順はその特定の機関にそれぞれの役割グループに関連付ける検索のアクセス許可フィルターを作成するのには、し、コンプライアンスの境界を定義します。各機関の 1 つの検索のアクセス許可のフィルターを作成する必要があります。セキュリティ アクセス許可のフィルターを作成する方法の詳細については、[アクセス許可を構成するコンテンツの検索のフィルター処理](permissions-filtering-for-content-search.md)を参照してください。
  
ここでは、境界を遵守するために使用される検索のアクセス許可フィルターを作成するために使用される構文です。

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<Compliance attribute from Step 1>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq <AttributeValue>' -or Site_Path -like <SharePointURL> *'" -Action <Action >
```
  
コマンドの各パラメーターの説明を以下に示します。
  
-  `FilterName`-フィルターの名前を指定します。使用について説明またはフィルターを適用する代理店を識別する名前が使用されます。 
    
-  `Users`-ユーザーまたはグループを実行するコンテンツの検索操作に適用されるフィルターを取得するユーザーを指定します。コンプライアンスの境界の代理店のためのフィルターを作成することで、ロール グループ (手順 3 で作成した場合) を指定します。複数値パラメーターは、コンマで区切られた 1 つまたは複数の役割グループを含めることができますので注意してください。 
    
-  `Filters`-フィルターの検索条件を指定します。コンプライアンスの境界は、次のフィルターを定義します。各 1 つは、ユーザーのコンテンツの場所に適用されます。 
    
  -  `Mailbox`-の役割グループが定義されているメールボックスを指定する、`Users`のパラメーターを検索できます。コンプライアンスの境界の*ComplianceAttribute*は、手順 1 で特定したのと同じ属性および*AttributeValue*機関を指定します。このフィルターは特定の政府機関にのみメールボックスを検索するロール グループのメンバーを許可します。たとえば、 `"Mailbox_Department -eq 'FourthCoffee'"` 。 
    
  -  `Site`-の役割グループが定義されている OneDrive のアカウントを指定する、`Users`のパラメーターを検索できます。OneDrive フィルターは、実際の文字列を使用して、 `ComplianceAttribute`。手順 1 で特定した、手順 2 で送信したサポート ・ リクエストの結果として OneDrive のアカウントに同期するのと同じ属性にマッピングします。 *AttributeValue*は、機関を指定します。このフィルターは特定の政府機関でのみ OneDrive のアカウントを検索するロール グループのメンバーを許可します。たとえば、 `"Site_ComplianceAttribute -eq 'FourthCoffee'"`。
    
  -  `Site_Path`-の役割グループが定義されている SharePoint サイトを指定する、`Users`のパラメーターを検索できます。*SharePointURL*では、サイトを指定の機関の役割グループのメンバーを検索できます。例えば`"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`
    
-  `Action`-フィルターを適用するコンプライアンスの検索動作の種類を指定します。たとえば、`-Action Search`だけに適用、フィルターの役割グループのメンバーが定義されている場合、`Users`パラメーターは、コンテンツの検索を実行します。この例では、検索結果をエクスポートするときは、フィルターを適用しません。コンプライアンスの境界を使用して`-Action All`ため、すべてのアクションを検索するフィルターが適用されます。 
    
    コンテンツの検索操作のリストは、[アクセス許可を構成するコンテンツの検索をフィルタ リング](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)で「新規 ComplianceSecurityFilter」セクションを参照してください。
    
Contoso 社のコンプライアンスの境界のシナリオをサポートするために作成される 2 つの検索のアクセス許可のフィルターの例を次に示します。
  
 **コーヒーハウス**

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 **コーホー ワイナリー**

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-an-intra-agency-investigations"></a>機関内の調査の電子的証拠開示のケースを作成する手順 5。

最後の手順は、セキュリティの新しい電子的証拠開示のサポート案件を作成するのには、&amp;コンプライアンス センター、役割グループに追加し、手順 3 で作成した-大文字と小文字のメンバーとして。これは、コンプライアンスの境界を使用する場合の 2 つの重要な特性が得られます。
  
- 表示して、セキュリティの場合にアクセスできる場合に追加の役割グループのメンバーのみ&amp;コンプライアンス センターです。たとえば、4 つ目のコーヒーの調査官の役割グループが、大文字と小文字の唯一のメンバーである場合は、し、Fourth Coffee の電子的証拠開示マネージャー ロールのグループ (または、他の役割グループのメンバー) のメンバーことはできませんを参照するか、大文字と小文字をアクセスします。
    
- サポート案件に割り当てられた役割グループのメンバーは、サポート案件に関連付けられている検索を実行するときにのみできるようになります (で定義されている手順 4 で作成した検索のアクセス許可のフィルターします。)、機関内でのコンテンツの場所を検索


新しいケースを作成し、メンバーを割り当てます。
    
1. セキュリティで**電子的証拠開示**のページに&amp;コンプライアンス センターと新しいケースを作成します。 
    
2. 電子的証拠開示のサポート案件の一覧で、作成した、大文字と小文字の名前をクリックします。
    
3. **管理ここ**フライアウト] ページで、**役割グループの管理**] の下でをクリックして![の追加アイコン](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**追加**します。
    
    ![電子的証拠開示のサポート案件のメンバーとしての役割グループを追加します。](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. 役割グループの一覧で手順 3 で作成した役割グループのいずれかを選択し、[**追加**] をクリックします。
    
5. 変更を保存するのには**このサポート案件の管理**のフライアウトで [**保存**] をクリックします。 

## <a name="compliance-boundary-limitations"></a>境界の制限事項を遵守

場合は電子的証拠開示およびコンプライアンスの境界の調査を使用する管理する場合は、次の制限事項に留意してください。
  
- 作成すると、コンテンツの検索を実行している、政府機関が外部にあるコンテンツの場所を選択できます。ただし、検索のアクセス許可のフィルターがあるためは、これらの場所からコンテンツを検索結果に含まれません。
    
- コンプライアンスの境界は、電子的証拠開示の場合の保留を適用しないでください。1 つの機関で、電子的証拠開示マネージャーは、保留中のさまざまな機関でユーザーを追加できることを意味します。ただし、コンプライアンスの境界は、電子的証拠開示マネージャーが配置された保留中のユーザーのコンテンツの場所を検索する場合に適用されます。つまり、電子的証拠開示マネージャーはユーザーのコンテンツの場所が検索をする、いても、それらのユーザーを配置することを保持はありません。
    
    また、統計情報は、機関内のコンテンツの場所にのみ適用されますを保持します。
    
- Exchange パブリック フォルダーへのアクセス許可の検索フィルターが適用されません。

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>検索や、複数地域の環境でのコンテンツをエクスポートします。

検索のアクセス許可のフィルターでは、エクスポート用のコンテンツがルーティングされ、 [SharePoint の複数の地域の環境](https://go.microsoft.com/fwlink/?linkid=860840)での SharePoint サイトおよび OneDrive のアカウントを検索する場合、どのデータ ・ センターを検索できるを制御することもできます。
  
- 特定のデータ ・ センターから検索結果をエクスポートします。つまり、データ ・ センターの場所から結果をエクスポートする検索を指定することができます。
    
- SharePoint サイトおよび衛星データ ・ センターに OneDrive のアカウントのルートを検索します。つまり、検索を実行可能なデータ センターの場所を指定することができます。
    
**新規 ComplianceSecurityFilter**または**セット ComplianceSecurityFilter**コマンドレットの作成またはエクスポートを経由するデータ ・ センターを変更する**地域**パラメーターを使用します。
  
|**パラメーターの値**|**データ センターの場所**|
|:-----|:-----|
|NAM  <br/> |北アメリカ (実際のデータ ・ センターは、米国では)  <br/> |
|EUR  <br/> |ヨーロッパ  <br/> |
|APC  <br/> |アジア太平洋地域  <br/> |
|CAN <br/> |カナダ
   
同様に、SharePoint と OneDrive の場所を検索するときにコンテンツの検索を実行するどのデータ ・ センターを制御するのに**領域**のパラメーター値を次の値を使用できます。次の表は、エクスポートを経由するデータ ・ センターも表示に注意してください。 
  
|**パラメーターの値**|**データ ・ センターのエクスポート用のルーティングの場所**|
|:-----|:-----|
|NAM  <br/> |US  <br/> |
|EUR  <br/> |ヨーロッパ  <br/> |
|APC  <br/> |アジア太平洋地域  <br/> |
|CAN  <br/> |US  <br/> |
|AUS  <br/> |アジア太平洋地域  <br/> |
|KOR  <br/> |組織の既定のデータ センター  <br/> |
|GBR  <br/> |ヨーロッパ  <br/> |
|JPN  <br/> |アジア太平洋地域  <br/> |
|IND  <br/> |アジア太平洋地域  <br/> |
|LAM  <br/> |US  <br/> |
   
 **注:** 検索のアクセス許可のフィルターの領域のパラメーターを指定しない場合の組織の既定の SharePoint 地域が検索されますし、検索結果は、最も近いデータ ・ センターにエクスポートします。 
  
使用例をここでは、 **-地域**境界を遵守するための検索許可フィルターを作成するときのパラメーターです。これは、Fourth Coffee の関連会社が北アメリカであることと、Coho Winery が、ヨーロッパにあると仮定します。 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
複数地域の環境でコンテンツを検索するときの注意、およびエクスポートするのには、次のことを維持します。
  
- **領域**パラメーターは、Exchange メールボックスの検索を制御しません。メールボックスを検索すると、すべてのデータ ・ センターが検索されます。どの Exchange のメールボックスを検索できる検索範囲を限定するには、**フィルター**パラメーターを作成または検索のアクセス許可のフィルターを変更するときに使用します。 
    
- 代替領域を指定する検索のアクセス許可のフィルターで使用できるマネージャーその証拠開示のための別のユーザー アカウントを作成する必要があります電子的証拠開示マネージャーが複数の SharePoint の領域全体を検索するために必要な場合は、場所、SharePoint サイトまたは OneDrive アカウントは、配置されます。
    
- SharePoint および OneDrive のコンテンツを検索する**領域**のパラメーターを指示したか、メインの検索や、電子的証拠開示マネージャーが電子的証拠開示の調査を実施する場所の場所の衛星。電子的証拠開示マネージャーは、SharePoint サイトと OneDrive サイトの検索のアクセス許可のフィルターで指定されている領域の外を検索する場合は、検索結果は返されません。 
    
- (Exchange、Skype をビジネスでは、SharePoint では、OneDrive のコンテンツの検索ツールを使用して検索できるその他の Office 365 サービスを含む) すべてのコンテンツの場所からコンテンツで Azure ストレージの場所にアップロードする検索結果をエクスポートするとき、**領域**パラメーターで指定されているデータ ・ センターです。これにより、組織内でのコンプライアンスの対象となるコントロールの境界線の間でコンテンツを許可しないことによってです。検索のアクセス許可のフィルターで地域を指定しない場合は、組織の既定の領域にコンテンツがアップロードされます。 
    
- 追加または次のコマンドを実行することによって、地域を変更する既存の検索のアクセス許可フィルターを編集できます。

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a>よく寄せられる質問

 **ユーザーを作成および管理 (新規 ComplianceSecurityFilter とセット ComplianceSecurityFilter コマンドレットを使用して) 検索のアクセス許可のフィルターでしょうか。**
  
作成するに表示し、検索のアクセス許可のフィルターを変更、セキュリティで組織の管理役割グループのメンバーである必要がある&amp;コンプライアンス センターです。
  
 **電子的証拠開示マネージャーが複数の機関にまたがる複数の役割グループに割り当てられている場合、検索する方法を 1 つの機関内のコンテンツやその他のでしょうか。**
  
電子的証拠開示マネージャーは、検索の範囲を特定の機関に制限は、検索クエリにパラメーターを追加できます。たとえば、組織が政府機関を区別するために**CustomAttribute10**プロパティを指定した場合に追加できます次特定機関でメールボックスおよび OneDrive のアカウントを検索するには、その検索クエリ: `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`。
  
 **コンプライアンス属性検索のアクセス許可のフィルターとして使用される属性の値を変更するとどうなりますか。**
  
コンプライアンスの境界を適用するフィルターで使用されている属性の値が変更された場合に検索のアクセス許可のフィルターには、最大で 3 日かかります。たとえば、contoso 社のシナリオと Fourth Coffee の代理店のユーザーが Coho Winery 代行業者に転送されます。その結果、ユーザー オブジェクトに**所属**の属性の値は、 *FourthCoffee*から*CohoWinery*に変更します。このような場合は、Fourth Coffee の電子的証拠開示、投資家検索結果を取得、属性が変更された後、3 日間をそのユーザー用です。同様に、Coho Winery 電子的証拠開示マネージャーの前に最大 3 日かかるし、調査官は、ユーザーの検索結果を取得します。 
  
 **電子的証拠開示マネージャーは 2 つの独立したコンプライアンスの境界からのコンテンツを表示できますか。**
  
うん。これは、両方の機関からの可視性を持っている役割グループにユーザーを追加することによって実行できます。
  
 **電子的証拠開示のサポート ・ リクエストの保留、Office 365 の保持ポリシー、または DLP のフィルター機能のアクセス許可を検索しますか。**
  
いいえ、現時点ではありません。
  
 **コンテンツをエクスポートすると、SharePoint の組織がその地域でないコントロールに領域を指定した場合でも検索する SharePoint でしょうか。**
  
組織の検索のアクセス許可のフィルターで指定された領域が存在しない場合は、既定の領域が検索されます。
  
 **組織で作成することができます検索のアクセス許可のフィルターの最大数とは何ですか。**
  
組織で作成することができます検索のアクセス許可のフィルターの数に制限はありません。ただし、100 以上の検索のアクセス許可のフィルターがある場合に検索のパフォーマンスが低下します。できるだけ小さく、組織内のアクセス許可の検索フィルターの数を保持するには、可能な限り 1 つの検索のアクセス許可のフィルターに交換、SharePoint、および OneDrive の規則を結合するためのフィルターを作成します。
