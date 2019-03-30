---
title: Office 365 での電子情報開示調査のためにコンプライアンスの境界を設定する
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
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: コンプライアンスの境界を使用して、電子情報開示マネージャーが検索できるユーザーコンテンツの場所を制御する、Office 365 組織内の論理的な境界を作成します。 コンプライアンス境界では、検索アクセス許可フィルター (コンプライアンスセキュリティフィルターとも呼ばれます) を使用して、特定のユーザーが検索できるメールボックス、SharePoint サイト、および OneDrive アカウントを制御します。
ms.openlocfilehash: dc1cf770ab015ece5212d5257f1807596e0e36c7
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001090"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a>Office 365 での電子情報開示調査のためにコンプライアンスの境界を設定する

コンプライアンス境界は、電子情報開示マネージャーが検索できるユーザーコンテンツの場所 (メールボックス、SharePoint サイト、OneDrive アカウントなど) を制御する、Office 365 組織内の論理的な境界を作成します。 また、コンプライアンスの境界は、組織内の法律、人的リソース、またはその他の調査を管理するために使用される電子情報開示ケースにアクセスできるユーザーを制御します。 多くの場合、地理的な boarders および規制を遵守する必要がある多民族企業や、多くの場合、さまざまな機関に分けられる政府機関に対して、コンプライアンスの境界が必要になります。 Office 365 では、コンテンツ検索を実行し、電子情報開示ケースを使用して調査を管理する際に、これらの要件を満たすためにコンプライアンスの境界が役立ちます。
  
次の図の例を使用して、コンプライアンスの境界がどのように機能するかを説明します。
  
![コンプライアンス境界は、政府機関へのアクセスを制御する検索アクセス許可フィルターと、edisococo極端なケースへのアクセスを制御する管理役割グループで構成されます。](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
この例では、Contoso ltd. は、2つの子会社、4番目のコーヒー、Coho (コーホーワイナリー) で構成される Office 365 組織です。 ビジネスでは、電子情報開示 mangers と調査担当者が、エージェンシー内の Exchange メールボックス、OneDrive アカウント、および SharePoint サイトのみを検索できるようにする必要があります。 また、電子情報開示の管理者と調査担当者は、エージェンシーの電子情報開示ケースのみを表示でき、メンバーとなっているケースのみにアクセスできます。 以下に、コンプライアンスの境界がこれらの要件を満たす方法を示します。
  
- コンテンツ検索の検索アクセス許可フィルター機能は、電子情報開示の管理者および捜査担当者が検索できるコンテンツの場所を制御します。 これは、4番目のコーヒーエージェンシーの電子情報開示マネージャーと調査担当者のみが、第4のコーヒー子会社のコンテンツの場所を検索できることを意味します。 同じ制限は、Coho の "子会社" にも適用されます。
    
    役割グループは、セキュリティ & コンプライアンスセンターで電子情報開示ケースを表示できるユーザーを制御します。 つまり、電子情報開示の管理者と調査担当者は、エージェンシーの電子情報開示ケースのみを表示できます。
    
- 役割グループは、電子情報開示ケースにメンバーを割り当てることができるユーザーも制御します。 つまり、電子情報開示マネージャーおよび調査担当者は、自分が自分のメンバーであるケースにのみメンバーを割り当てることができます。
    
コンプライアンスの境界を設定するプロセスは次のとおりです。
  
[手順 1: ユーザー属性を識別して、機関を定義する](#step-1-identify-a-user-attribute-to-define-your-agencies)

[手順 2: Microsoft サポートによる要求をファイル化して、ユーザー属性を OneDrive アカウントに同期させる](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[手順 3: 各エージェンシーの役割グループを作成する](#step-3-create-a-role-group-for-each-agency)

[手順 4: コンプライアンスの境界を適用するための検索アクセス許可フィルターを作成する](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[手順 5: エージェンシー内の調査用に電子情報開示ケースを作成する](#step-5-create-an-ediscovery-case-for-an-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>手順 1: ユーザー属性を識別して、機関を定義する

最初の手順として、を使用する Azure Active Directory 属性を選択して、その機関を定義します。 この属性は、この属性に特定の値が割り当てられているユーザーのコンテンツの場所のみを検索するように電子情報開示マネージャーを制限する検索アクセス許可フィルターを作成するために使用されます。 たとえば、Contoso 社が**Department**属性の使用を決定したとします。 4番目のコーヒー子会社のユーザーのこの属性の値は`FourthCoffee`となり、Coho のユーザーの値はとなり`CohoWinery`ます。 ステップ4では、この`attribute:value`ペア (たとえば、 *Department: 4 thコーヒー* ) を使用して、電子情報開示マネージャーが検索できるユーザーのコンテンツの場所を制限します。 
  
以下は、コンプライアンスの境界に使用できる Azure Active Directory ユーザー属性の一覧です。
  
- Company
    
- CustomAttribute1-CustomAttribute15
    
- 部署
    
- 事業所
    
他のユーザー属性も使用できますが (特に Exchange メールボックスの場合)、上記の属性は OneDrive で現在サポートされているものだけです。
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>手順 2: Microsoft サポートによる要求をファイル化して、ユーザー属性を OneDrive アカウントに同期させる

次の手順では、Microsoft サポートに要求をファイルして、手順1で選択した Azure Active Directory 属性と組織内のすべての OneDrive アカウントを同期させます。 この同期が行われると、手順1で選択した属性 (およびその値) は、SharePoint の非表示の管理プロパティに`ComplianceAttribute`マップされます。 この属性を使用して、手順4で OneDrive の検索アクセス許可フィルターを作成します。
  
Microsoft サポートに要求を送信するときに、次の情報を含めます。
  
- Office 365 組織の既定のドメイン名
    
- Azure Active Directory 属性の名前 (手順1から)
    
- サポート要求の目的に関する次のタイトルまたは説明: "コンプライアンスセキュリティフィルターのために Azure Active Directory との OneDrive for business の同期を有効にする"。 これは、要求を実装する Office 365 eDiscovery エンジニアリングチームに要求をルーティングするのに役立ちます。
    
エンジニアリングの変更が行われ、属性が OneDrive に同期されると、Microsoft Support は変更が行われたビルド番号と推定展開日を送信します。 通常、サポート要求を送信した後、展開プロセスは4-6 週間かかることに注意してください。
  
 **重要:** 変更を展開する前に、手順3から手順5までを完了できます。 ただし、コンテンツ検索を実行しても、検索アクセス許可フィルターで指定された OneDrive サイトからのドキュメントは、変更が展開されるまで返されません。 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>手順 3: 各エージェンシーの役割グループを作成する

次の手順では、組織の機関と連携するセキュリティ & コンプライアンスセンターで役割グループを作成します。 組み込みの電子情報開示マネージャーグループをコピーし、適切なメンバーを追加して、ニーズに該当しない可能性がある役割を削除することによって、新しい役割グループを作成することをお勧めします。 電子情報開示関連のロールの詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。
  
役割グループを作成するには、Security & コンプライアンスセンターの [**アクセス許可**] ページに移動し、コンプライアンスの境界と電子情報開示ケースを使用して調査を管理する各エージェンシーの各チームの役割グループを作成します。 
  
Contoso 社のコンプライアンス境界シナリオを使用して、4つの役割グループを作成し、それぞれに適切なメンバーを追加する必要があります。
  
- 4番目のコーヒー eDiscovery マネージャー
    
- 4番目のコーヒー捜査官
    
- Coho の電子情報開示マネージャー
    
- Coho の捜査官
    

  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>手順 4: コンプライアンスの境界を適用するための検索アクセス許可フィルターを作成する

各エージェンシーの役割グループを作成したら、次の手順として、各役割グループを特定のエージェンシーに関連付け、コンプライアンス境界自体を定義する検索アクセス許可フィルターを作成します。 各エージェンシーに対して1つの検索アクセス許可フィルターを作成する必要があります。 セキュリティアクセス許可フィルターの作成の詳細については、「 [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md)」を参照してください。
  
以下は、コンプライアンスの境界に使用される検索アクセス許可フィルターを作成するために使用される構文です。

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<Compliance attribute from Step 1>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq <AttributeValue>' -or Site_Path -like <SharePointURL> *'" -Action <Action >
```
  
コマンドの各パラメーターの説明を次に示します。
  
-  `FilterName`-フィルターの名前を指定します。 フィルターが使用されるエージェンシーを説明または特定する名前を使用します。 
    
-  `Users`-このフィルターを実行するコンテンツ検索アクションに適用される、このフィルターを取得するユーザーまたはグループを指定します。 このパラメーターは、コンプライアンスの境界に対して、フィルターを作成しているエージェンシーの役割グループ (手順3で作成したもの) を指定します。 メモこれは複数値パラメーターであるため、1つまたは複数の役割グループをコンマで区切って含めることができます。 
    
-  `Filters`-フィルターの検索条件を指定します。 コンプライアンスの境界については、次のフィルターを定義します。 それぞれは、ユーザーのコンテンツの場所に適用されます。 
    
  -  `Mailbox`- `Users`パラメーターで定義されている役割グループが検索できるメールボックスを指定します。 コンプライアンスの境界の場合、 *ComplianceAttribute*は、手順1と属性*値*で指定したものと同じであり、エージェンシーを指定します。 このフィルターを使用すると、役割グループのメンバーは特定のエージェンシーのメールボックスのみを検索できます。たとえば、 `"Mailbox_Department -eq 'FourthCoffee'"`のようになります。 
    
  -  `Site`- `Users`パラメーターで定義されている役割グループが検索できる OneDrive アカウントを指定します。 OneDrive フィルターの場合は、実際の文字列`ComplianceAttribute`を使用します。これは、手順2で送信したサポート要求の結果として、手順1で識別し、OneDrive アカウントに同期されている属性にマッピングされます。 *attributevalue*はエージェンシーを指定します。 このフィルターを使用すると、役割グループのメンバーは特定のエージェンシーの OneDrive アカウントのみを検索できます。たとえば、 `"Site_ComplianceAttribute -eq 'FourthCoffee'"`のようになります。
    
  -  `Site_Path`- `Users`パラメーターで定義されている役割グループが検索できる SharePoint サイトを指定します。 *SharePointURL*は、役割グループのメンバーが検索できる機関内のサイトを指定します。例えば`"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`
    
-  `Action`-フィルターが適用されるコンプライアンス検索アクションの種類を指定します。 たとえば、は`-Action Search` 、 `Users`パラメーターで定義された役割グループのメンバーがコンテンツ検索を実行するときにのみフィルターを適用します。 この場合、検索結果をエクスポートするときに、フィルターは適用されません。 コンプライアンスの境界の場合`-Action All`は、を使用して、すべての検索操作にフィルターが適用されるようにします。 
    
    コンテンツ検索アクションの一覧については、「 [Configure permissions filtering for content search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)」の「new-compliancesecurityfilter」セクションを参照してください。
    
Contoso 社のコンプライアンス境界シナリオをサポートするために作成される2つの検索アクセス許可フィルターの例を次に示します。
  
 **4番目のコーヒー**

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 **コーホーワイナリー**

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-an-intra-agency-investigations"></a>手順 5: エージェンシー内の調査用に電子情報開示ケースを作成する

最後の手順として、セキュリティ & コンプライアンスセンターで新しい電子情報開示ケースを作成し、次に、手順3で作成した役割グループをケースのメンバーとして追加します。 これにより、コンプライアンスの境界を使用する2つの重要な特徴が得られるようになります。
  
- セキュリティ & コンプライアンスセンターでは、ケースに追加された役割グループのメンバーのみが、ケースを参照およびアクセスできるようになります。 たとえば、4番目のコーヒーの捜査官の役割グループがケースの唯一のメンバーである場合、その4番目のコーヒー eDiscovery Managers 役割グループ (または他の任意の役割グループのメンバー) のメンバーは、ケースを表示またはアクセスできません。
    
- ケースに割り当てられた役割グループのメンバーが、そのケースに関連付けられている検索を実行すると、それらは、手順4で作成した検索アクセス許可フィルターによって定義された、エージェンシー内のコンテンツの場所のみを検索できます。


新しいケースを作成し、メンバーを割り当てるには、次のようにします。
    
1. セキュリティ & コンプライアンスセンターの [**電子情報開示**] ページに移動し、新しいケースを作成します。 
    
2. 電子情報開示ケースの一覧で、作成したケースの名前をクリックします。
    
3. [**このケースの管理**] ページの [**役割グループ**の管理] ![で、](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) ****[追加] アイコン [追加] をクリックします。
    
    ![電子情報開示ケースのメンバーとして役割グループを追加する](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. 役割グループの一覧で、手順3で作成した役割グループの1つを選択し、[**追加**] をクリックします。
    
5. [**このケースの管理**] ポップアップで [**保存**] をクリックして変更を保存します。 

## <a name="compliance-boundary-limitations"></a>コンプライアンス境界の制限

電子情報開示ケースを管理する場合、およびコンプライアンスの境界を使用する調査を行う場合は、次の制限事項に注意してください。
  
- コンテンツ検索を作成して実行するときは、エージェンシーの外部にあるコンテンツの場所を選択できます。 ただし、検索アクセス許可フィルターのため、これらの場所からのコンテンツは検索結果に含まれません。
    
- コンプライアンスの境界は、電子情報開示ケースの保留リストには適用されません。 つまり、あるエージェンシーの電子情報開示管理者は、ユーザーを保留中の異なるエージェンシーに配置することができます。 ただし、電子情報開示マネージャーが保留中のユーザーのコンテンツの場所を検索する場合は、コンプライアンスの境界が適用されます。 つまり、電子情報開示マネージャーは、ユーザーを保留にすることができた場合でも、ユーザーのコンテンツの場所を検索することはできません。
    
    また、保留の統計情報はエージェンシーのコンテンツの場所にのみ適用されます。
    
- 検索アクセス許可のフィルターは、Exchange のパブリックフォルダーには適用されません。

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>複数地域環境でのコンテンツの検索とエクスポート

また、検索アクセス許可フィルターを使用すると、エクスポート用にコンテンツをルーティングする場所を制御したり、 [SharePoint 複数地域環境](https://go.microsoft.com/fwlink/?linkid=860840)でコンテンツの場所を検索するときに検索できるデータセンターを制御したりすることもできます。
  
- **検索結果をエクスポート**する-特定のデータセンターから Exchange メールボックス、SharePoint サイト、および OneDrive アカウントから検索結果をエクスポートできます。 これは、検索結果のエクスポート元となるデータセンターの場所を指定できることを意味します。

    **new-compliancesecurityfilter**または**new-compliancesecurityfilter**コマンドレットに**Region**パラメーターを使用して、エクスポートがルーティングされるデータセンターを作成または変更します。
  
    |**パラメーターの値**|**データセンターの場所**|
    |:-----|:-----|
    |NAM  <br/> |北アメリカ (実際のデータセンターは米国にあります)  <br/> |
    |EUR  <br/> |地区  <br/> |
    |APC  <br/> |アジア太平洋地域  <br/> |
    |CAN <br/> |カナダ
    
- **コンテンツ検索をルーティング**する-SharePoint サイトと OneDrive アカウントのコンテンツ検索をサテライトデータセンターにルーティングできます。 これは、検索を実行するデータセンターの場所を指定できることを意味します。
    
    次の値を**Region**パラメーター値として使用して、SharePoint サイトと OneDrive の場所を検索するときにコンテンツ検索が実行するデータセンターを制御します。 また、次の表に、によってルーティングされるデータセンターのエクスポートも表示されることに注意してください。 
  
    |**パラメーターの値**|**エクスポート用のデータセンタールーティング場所**|
    |:-----|:-----|
    |NAM  <br/> |電源  <br/> |
    |EUR  <br/> |地区  <br/> |
    |APC  <br/> |アジア太平洋地域  <br/> |
    |CAN  <br/> |電源  <br/> |
    |AUS  <br/> |アジア太平洋地域  <br/> |
    |KOR  <br/> |組織の既定のデータセンター  <br/> |
    |GBR  <br/> |地区  <br/> |
    |JPN  <br/> |アジア太平洋地域  <br/> |
    |IND  <br/> |アジア太平洋地域  <br/> |
    |語頭  <br/> |電源  <br/> |
   
> [!NOTE]
> 検索アクセス許可フィルターに**Region**パラメーターを指定しない場合、組織の既定の SharePoint 地域が検索され、検索結果が最も近いデータセンターにエクスポートされます。 
  
ここでは、コンプライアンスの境界に対して検索アクセス許可のフィルターを作成するときに**Region**パラメーターを使用する例を示します。 この場合は、4つ目のコーヒー子会社が北米に配置されており、Coho がヨーロッパにあることを前提としています。 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
複数地域環境でコンテンツを検索してエクスポートする場合は、次の点に注意してください。
  
- **Region**パラメーターは、Exchange メールボックスの検索を制御しません。メールボックスを検索すると、すべてのデータセンターが検索されます。 検索アクセス許可フィルターを作成または変更するときに、検索できる Exchange メールボックスの範囲を制限するには、 **Filters**パラメーターを使用します。 
    
- 電子情報開示管理者が複数の SharePoint 地域を検索する必要がある場合は、その電子情報開示マネージャーに対して別のユーザーアカウントを作成する必要があります。これを検索権限フィルターで使用して、SharePoint サイトまたは OneDrive アカウントが配置されている。
    
- SharePoint および OneDrive でコンテンツを検索する場合、 **Region**パラメーターは、電子情報開示マネージャーが電子情報開示の調査を行うメインまたはサテライトの場所を検索します。 電子情報開示マネージャーが、検索アクセス許可フィルターで指定されている地域外の SharePoint および OneDrive サイトを検索すると、検索結果は返されません。 
    
- 検索結果をエクスポートすると、すべてのコンテンツの場所 (Exchange、Skype for business、SharePoint、OneDrive、およびコンテンツ検索ツールを使用して検索できる他の Office 365 サービスを含む) からのコンテンツが、**Region**パラメーターで指定されたデータセンター。 これにより、管理された境界を越えてコンテンツをエクスポートすることを許可しないことで、組織のコンプライアンスを実現できます。 検索アクセス許可フィルターで地域が指定されていない場合、コンテンツは組織の既定の地域にアップロードされます。 
    
- 既存の検索アクセス許可フィルターを編集して、次のコマンドを実行し、地域を追加または変更することができます。

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a>よく寄せられる質問

 **検索アクセス許可フィルターを作成および管理できるユーザー (new-compliancesecurityfilter および new-compliancesecurityfilter コマンドレットを使用)**
  
検索アクセス許可のフィルターを作成、表示、および変更するには、Security & コンプライアンスセンターで、組織の管理役割グループのメンバーである必要があります。
  
 **電子情報開示マネージャーが複数の機関にまたがる複数の役割グループに割り当てられている場合、どのようにして1つのエージェンシーでコンテンツを検索しますか?**
  
電子情報開示マネージャーは、検索を特定のエージェンシーに制限するパラメーターを検索クエリに追加できます。 たとえば、組織で**CustomAttribute10**プロパティを指定してエージェンシーを区別する場合、次のものを検索クエリに追加して、特定のエージェンシーのメールボックスと OneDrive `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`アカウントを検索することができます。
  
 **検索アクセス許可フィルターでコンプライアンス属性として使用されている属性の値が変更された場合はどうなりますか。**
  
検索アクセス許可フィルターで使用される属性の値が変更された場合に、コンプライアンスの境界を適用するには最大3日間かかります。 たとえば、Contoso 社のシナリオでは、第4のコーヒーエージェンシーのユーザーが Coho (コーホーワイナリー) エージェンシーに転送されるとします。 その結果、ユーザーオブジェクトの**Department**属性の値が、"4 *thコーヒー* " から " *cohowinery* " に変更されます。 このような状況では、4番目のコーヒー eDiscovery および投資家が、属性が変更されてから3日後にそのユーザーの検索結果を取得します。 同様に、Coho の電子情報開示マネージャーおよび調査担当者がユーザーの検索結果を取得するまで最大3日間かかります。 
  
 **電子情報開示マネージャーは、2つの異なるコンプライアンス境界からのコンテンツを表示できますか。**
  
はい。 この操作を行うには、両方のエージェンシーに対して可視性を持つ役割グループにユーザーを追加します。
  
 **検索アクセス許可フィルターは、電子情報開示のケースホールド、Office 365 アイテム保持ポリシー、DLP のいずれかに対して機能しますか?**
  
いいえ (現時点では不可)
  
 **コンテンツのエクスポート先を制御する地域を指定したが、その地域に sharepoint 組織が存在しない場合、sharepoint を検索することはできますか?**
  
検索アクセス許可フィルターで指定されている地域が組織内に存在しない場合は、既定の地域が検索されます。
  
 **組織内で作成できる検索アクセス許可のフィルターの最大数はいくつですか。**
  
組織内で作成できる検索アクセス許可フィルターの数に制限はありません。 ただし、100を超える検索アクセス許可フィルターがある場合は、検索のパフォーマンスが影響を受けます。 組織内の検索アクセス許可フィルターの数を可能な限り小さくするには、Exchange、SharePoint、および OneDrive のルールを可能な限り1つの検索アクセス許可フィルターにまとめるフィルターを作成します。
