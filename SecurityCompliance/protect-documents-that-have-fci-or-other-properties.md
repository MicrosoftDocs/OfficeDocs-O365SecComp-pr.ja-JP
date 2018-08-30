---
title: FCI または他のプロパティが使用されているドキュメントを保護する DLP ポリシーを作成する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.assetid: 1b9e3c6c-4308-4a20-b11e-c37b8013e177
description: 多くの組織があるプロセスを識別し、Windows サーバーのファイル分類インフラストラクチャ (FCI)、SharePoint で、ドキュメントのプロパティまたはドキュメントのプロパティで分類プロパティを使用して機密情報を分類するにはサード ・ パーティ製システムによって適用されます。DLP ポリシーは、FCI の特定またはその他の Office ドキュメントに適用できるように、Windows Server FCI やその他のシステムでは、ドキュメントに適用されているプロパティを認識する Office 365 の DLP ポリシーを作成することができますこれは、組織を記述する場合プロパティの値です。
ms.openlocfilehash: 057cdad981249e39d6f39f231d8d60ab977e717a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013691"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>FCI または他のプロパティが使用されているドキュメントを保護する DLP ポリシーを作成する

Office 365 でデータ損失防止 (DLP) ポリシーを使用すると、機密情報の識別、監視、保護を行えます。多くの組織には、Windows Server ファイル分類インフラストラクチャ (FCI) の分類プロパティ、SharePoint のドキュメント プロパティ、またはサード パーティによって適用されたドキュメント プロパティを使用して機密情報を識別および分類するプロセスが既に存在します。ご自分の組織でもこの状況が当てはまる場合、Offce 365 で DLP ポリシーを作成できます。このポリシーは、Windows Server FCI または他のシステムによってドキュメントに適用されているプロパティを認識し、特定の FCI 値または他のプロパティ値が含まれる Office ドキュメントに DLP ポリシーを適用できるようにします。
  
![Office 365 と外部の分類システムを示す図](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
可能性があります、組織の社会保障番号などの個人を特定できる情報 (PII) を使用してドキュメントを識別する Windows サーバーの FCI を使用して**個人情報**を設定することにより、ドキュメントを分類など種類に基づいて、プロパティを**高**、**中**、**低**、**パブリック**、または**個人情報ではありません**し、個人情報の項目の数がドキュメントで見つかった。、Office 365 では、**高**、**中**、などの特定の値に設定するプロパティを持つドキュメントを識別し、それらのファイルへのアクセスをブロックするなどの動作を受け取る DLP ポリシーを作成できます。同じポリシーでは、プロパティは、電子メール通知を送信するなど**低**] に設定されている場合に別のアクションを実行する別のルールを持つことができます。この方法で Office 365 の DLP は Windows サーバー FCI との統合し、Office ドキュメントのアップロードまたはファイルの Windows Server ベースのサーバーから Office 365 の共有を保護することができます。
  
DLP ポリシーは、特定のプロパティの名前と値のペアを探すだけです。対象プロパティに SharePoint 検索の対応する管理プロパティが含まれる場合には、任意のドキュメント プロパティを使用できます。たとえば、SharePoint のサイト コレクションが [**旅行レポート**] という名前のコンテンツの種類を使用し、[**顧客**] という必須フィールドが指定されているとします。ユーザーが旅行レポートを作成するたびに、顧客名を入力する必要が生じます。このプロパティの名前と値のペアを DLP ポリシーでも使用できます。たとえば、[**顧客**] フィールドに [**Contoso**] が含まれるときに外部ユーザーによるドキュメントへのアクセスをブロックするルールを作成できます。
  
ある特定の Office 365 のラベルの内容を DLP ポリシーを適用する場合は、従う必要はありません手順をここで注意してください。については、 [DLP ポリシーの条件としてのラベルを使用](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)する方法です。
  
## <a name="before-you-create-the-dlp-policy"></a>DLP ポリシーを作成する前に

Windows Server FCI プロパティまたはその他のプロパティを使用するには、DLP ポリシーで、SharePoint の管理センターの管理プロパティを作成する必要があります。です。
  
例
  
このマッピングは重要になります。Office 365 の DLP は検索クローラーを使用して、サイト上の機密情報を識別および分類し、その機密情報を検索インデックスのセキュリティで保護された部分に格納するからです。ドキュメントを Office 365 にアップロードすると、ドキュメント プロパティに基づいて、クロールされたプロパティが SharePoint によって自動作成されます。しかし DLP ポリシーで FCI または他のプロパティを使用するには、クロールされたプロパティを管理プロパティにマッピングし、そのプロパティが含まれるコンテンツをインデックスで保持できるようにする必要があります。
  
検索と管理プロパティの詳細については、 [SharePoint Online の検索スキーマの管理](http://go.microsoft.com/fwlink/p/?LinkID=627454)を参照してください。
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>手順 1: 必要なプロパティが含まれるドキュメントを Office 365 にアップロードする

まず、DLP ポリシーで参照するプロパティを使用してドキュメントをアップロードする必要があります。Office 365 は、プロパティを検出し、そこからクロールされたプロパティを自動的に作成します。次の手順では、管理プロパティを作成し、このクロールされたプロパティを管理プロパティをマップします。
  
### <a name="step-2-create-a-managed-property"></a>手順 2: 管理プロパティを作成する

1. Office 365 管理センターにサインインします。
    
2. 左側のナビゲーションでは、**管理者が中央揃え**」を選択します\> **SharePoint**。SharePoint 管理センターを場合します。
    
3. 左側のナビゲーションでは、[**検索**] を選択\>[**検索管理**] ページで、 \> **検索スキーマを管理**します。
    
    ![SharePoint 管理センターの検索管理ページ](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. **プロパティの管理**ページの [ \> **管理の新しいプロパティ**です。
    
    ![[新しい管理プロパティ] ボタンが強調表示されている[プロパティ管理] ページ](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. プロパティの名前と説明を入力します。この名前が、DLP ポリシーに表示されます。
    
6. [**型**] で [**テキスト**] を選択します。 
    
7. [**主な特徴**] では [**クエリ可能**] と [**取得可能**] を選択します。
    
8. [**クロールされたプロパティのマッピングを** \> **のマッピングを追加**します。
    
9. **クロール プロパティの選択**] ダイアログ ボックスで\>を検索して、Windows サーバーの FCI プロパティまたは DLP ポリシーで使用する他のプロパティに対応するクロールされたプロパティを選択\> **OK**です。
    
    ![[クロールされたプロパティの選択] ダイアログ ボックス](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. ページの下部にある\> **OK**です。
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>FCI プロパティまたは他のプロパティを使用する DLP ポリシーを作成する

この例では、その Windows サーバー ベースのファイル サーバーで FCI を使っています。具体的には、**高**、**中**、**低**、**公開**、および**PII ではない**ので**個人情報**を指定した FCI 分類プロパティを使用しています。Office 365 の DLP ポリシーの既存の FCI 分類を活用するようになりました。
  
まず、前述の手順に従って SharePoint Online で管理プロパティを作成します。管理プロパティを、FCI に基づいて自動作成された、クロールされたプロパティにマッピングします。
  
次に、DLP ポリシーを**ドキュメントのプロパティが含まれているこれらの値のいずれかの**条件を両方使用している 2 つのルールを作成します。
  
- **FCI の個人情報のコンテンツを高、中**FCI 分類プロパティ**を特定できる情報個人**が**高**または**中レベル**に相当し、組織外のユーザーとドキュメントを共有する場合、最初のルールは、ドキュメントにアクセスを制限します。 
    
- **FCI PII コンテンツ - 低**2 番目のルールでは、FCI 分類プロパティの**個人情報**は、**低**と、ドキュメントと等しい場合、ドキュメントの所有者に通知するが、組織外のユーザーと共有を送信します。 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a>PowerShell を使用して、DLP ポリシーを作成します。

**ドキュメント プロパティには、これらの値のいずれかが含まれている**条件が一時的に使用できないこと、セキュリティの UI に注意してください&amp;コンプライアンスの中心ですが、それでも条件を使用してこの PowerShell を使用しています。使用することができます、 `New\Set\Get-DlpCompliancePolicy` 、DLP ポリシーを使用してコマンドレット、`New\Set\Get-DlpComplianceRule`コマンドレットで、 `ContentPropertyContainsWords` **ドキュメントのプロパティが含まれているこれらの値のいずれかの**条件を追加するパラメーター。
  
これらのコマンドレットの詳細についてを参照してください[Office 365 のセキュリティ&amp;コンプライアンス センター コマンドレット](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)。
  
1. [Office 365 のセキュリティへの接続&amp;リモート PowerShell を使用してコンプライアンス センター](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. 使用してポリシーを作成する`New-DlpCompliancePolicy`。
    
    ここでは、すべての場所に適用される DLP ポリシーを作成する PowerShell の使用例です。
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. 使用して上記で説明した 2 つの規則を作成する`New-DlpComplianceRule`、**低**値の 1 つのルールでは、**高**または**中レベル**の値は、別のルールです。 
    
    ここでは、これら 2 つの規則を作成する PowerShell の使用例です。プロパティの名前と値のペアが、引用符で囲まれているし、プロパティ名と同様に、スペースなしでカンマで区切られた複数の値を指定ことがあることに注意してください。`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    Windows Server FCI に次の使用例で使用されている**個人情報**を含む、多くの組み込みプロパティが含まれていることに注意してください。各プロパティの値はすべての組織の別にすることはできます。**高**、**中程度**、およびここでは**低**値は、単なる一例です。組織の Windows サーバー ベースのファイル サーバー上のファイル サーバー リソース マネージャーで、使用可能な値を持つ Windows Server FCI 分類のプロパティを表示できます。詳細については、[分類プロパティの作成](http://go.microsoft.com/fwlink/p/?LinkID=627456)を参照してください。
    
終了したら、ポリシーに 2 つの新しいルールが**ドキュメントのプロパティが含まれているこれらの値のいずれかの**条件を両方使用している必要があります。メモは、この条件は表示されません UI では、ただし、その他の条件、アクション、および設定が表示されます。 
  
ルールは 1 つのブロックは、**個人情報**プロパティが**高**または**中レベル**と同じコンテンツにアクセスします。2 番目のルールは、**個人情報**プロパティが**低**に等しいコンテンツに関する通知を送信します。
  
![2 つのルールが作成されたことを示す[新しい DLP ポリシー] ダイアログ ボックス](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a>DLP ポリシーを作成した後に

、そのプロパティを持つコンテンツがコンテンツを新しくアップロードされると、コンテンツのインデックスを作成)、DLP ポリシーを迅速に検出されますが作成されます、前のセクションの手順を実行またはコンテンツのある場合は古いですが、編集できるように、コンテンツの再インデックス付けされた).
  
対象プロパティが含まれるコンテンツを検出するには、ライブラリ、サイト、サイト コレクションの再インデックス付けを手動で要求し、対象プロパティが含まれるコンテンツすべてを DLP ポリシーが認識するようにできます。SharePoint Online では、定義されているクロール スケジュールに基づいてコンテンツは自動的にクロールされます。クローラーは、最後にクロールされて以降に変更が加えられたコンテンツを取得して、インデックスを更新します。スケジュールされたクロールが次に実行される前にコンテンツを保護する DLP ポリシーが必要となる場合には、以下の手順を実行できます。
  
> [!CAUTION]
> サイトのインデックスを再作成と、検索システムの大規模な負荷が発生する可能性がします。シナリオ絶対に必要としない限り、サイトをインデックス再しません。 
  
詳細については、[クロールして、サイト、ライブラリまたはリストのインデックスの再作成を手動で要求](http://go.microsoft.com/fwlink/p/?LinkID=627457)を参照してください。
  
### <a name="re-index-a-site-optional"></a>サイトを再インデックス付けする (省略可能)

1. サイトの**設定**(右上の歯車アイコン) を選択します\>**サイトの設定**。
    
2. [**検索**]、[**検索とオフラインでの可用性**を選択\>**サイトのインデックスを再作成**します。
    
## <a name="more-information"></a>詳細情報

- [データ損失防止ポリシーの概要](data-loss-prevention-policies.md)
    
- [テンプレートから DLP ポリシーを作成する](create-a-dlp-policy-from-a-template.md)
    
- [DLP ポリシーに関する通知を送信してポリシー ヒントを表示する](use-notifications-and-policy-tips.md)
    
- [DLP ポリシー テンプレートに含まれるもの](what-the-dlp-policy-templates-include.md)
    
- [機密情報の種類のインベントリ](what-the-sensitive-information-types-look-for.md)
    

