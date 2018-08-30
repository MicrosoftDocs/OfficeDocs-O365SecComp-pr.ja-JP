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
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a><span data-ttu-id="19261-104">FCI または他のプロパティが使用されているドキュメントを保護する DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="19261-104">Create a DLP policy to protect documents with FCI or other properties</span></span>

<span data-ttu-id="19261-p102">Office 365 でデータ損失防止 (DLP) ポリシーを使用すると、機密情報の識別、監視、保護を行えます。多くの組織には、Windows Server ファイル分類インフラストラクチャ (FCI) の分類プロパティ、SharePoint のドキュメント プロパティ、またはサード パーティによって適用されたドキュメント プロパティを使用して機密情報を識別および分類するプロセスが既に存在します。ご自分の組織でもこの状況が当てはまる場合、Offce 365 で DLP ポリシーを作成できます。このポリシーは、Windows Server FCI または他のシステムによってドキュメントに適用されているプロパティを認識し、特定の FCI 値または他のプロパティ値が含まれる Office ドキュメントに DLP ポリシーを適用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="19261-p102">In Office 365, you can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information. Many organizations already have a process to identify and classify sensitive information by using the classification properties in Windows Server File Classification Infrastructure (FCI), the document properties in SharePoint, or the document properties applied by a third-party system. If this describes your organization, you can create a DLP policy in Office 365 that recognizes the properties that have been applied to documents by Windows Server FCI or other system, so that the DLP policy can be enforced on Office documents with specific FCI or other property values.</span></span>
  
![Office 365 と外部の分類システムを示す図](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
<span data-ttu-id="19261-p103">可能性があります、組織の社会保障番号などの個人を特定できる情報 (PII) を使用してドキュメントを識別する Windows サーバーの FCI を使用して**個人情報**を設定することにより、ドキュメントを分類など種類に基づいて、プロパティを**高**、**中**、**低**、**パブリック**、または**個人情報ではありません**し、個人情報の項目の数がドキュメントで見つかった。、Office 365 では、**高**、**中**、などの特定の値に設定するプロパティを持つドキュメントを識別し、それらのファイルへのアクセスをブロックするなどの動作を受け取る DLP ポリシーを作成できます。同じポリシーでは、プロパティは、電子メール通知を送信するなど**低**] に設定されている場合に別のアクションを実行する別のルールを持つことができます。この方法で Office 365 の DLP は Windows サーバー FCI との統合し、Office ドキュメントのアップロードまたはファイルの Windows Server ベースのサーバーから Office 365 の共有を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="19261-p103">For example, your organization might use Windows Server FCI to identify documents with personally identifiable information (PII) such as social security numbers, and then classify the document by setting the **Personally Identifiable Information** property to **High**, **Moderate**, **Low**, **Public**, or **Not PII** based on the type and number of occurrences of PII found in the document. In Office 365, you can create a DLP policy that identifies documents that have that property set to specific values, such as **High** and **Medium**, and then takes an action such as blocking access to those files. The same policy can have another rule that takes a different action if the property is set to **Low**, such as sending an email notification. In this way, DLP in Office 365 integrates with Windows Server FCI and can help protect Office documents uploaded or shared to Office 365 from Windows Server-based file servers.</span></span>
  
<span data-ttu-id="19261-p104">DLP ポリシーは、特定のプロパティの名前と値のペアを探すだけです。対象プロパティに SharePoint 検索の対応する管理プロパティが含まれる場合には、任意のドキュメント プロパティを使用できます。たとえば、SharePoint のサイト コレクションが [**旅行レポート**] という名前のコンテンツの種類を使用し、[**顧客**] という必須フィールドが指定されているとします。ユーザーが旅行レポートを作成するたびに、顧客名を入力する必要が生じます。このプロパティの名前と値のペアを DLP ポリシーでも使用できます。たとえば、[**顧客**] フィールドに [**Contoso**] が含まれるときに外部ユーザーによるドキュメントへのアクセスをブロックするルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="19261-p104">A DLP policy simply looks for a specific property name/value pair. Any document property can be used, as long as the property has a corresponding managed property for SharePoint search. For example, a SharePoint site collection might use a content type named **Trip Report** with a required field named **Customer**. Whenever a person creates a trip report, they must enter the customer name. This property name/value pair can also be used in a DLP policy — for example, if you want a rule that blocks access to the document for external users when the **Customer** field contains **Contoso**.</span></span>
  
<span data-ttu-id="19261-p105">ある特定の Office 365 のラベルの内容を DLP ポリシーを適用する場合は、従う必要はありません手順をここで注意してください。については、 [DLP ポリシーの条件としてのラベルを使用](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)する方法です。</span><span class="sxs-lookup"><span data-stu-id="19261-p105">Note that if you want to apply your DLP policy to content with specific Office 365 labels, you should not follow the steps here. Instead, learn how to [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
  
## <a name="before-you-create-the-dlp-policy"></a><span data-ttu-id="19261-120">DLP ポリシーを作成する前に</span><span class="sxs-lookup"><span data-stu-id="19261-120">Before you create the DLP policy</span></span>

<span data-ttu-id="19261-p106">Windows Server FCI プロパティまたはその他のプロパティを使用するには、DLP ポリシーで、SharePoint の管理センターの管理プロパティを作成する必要があります。です。</span><span class="sxs-lookup"><span data-stu-id="19261-p106">Before you can use a Windows Server FCI property or other property in a DLP policy, you need to create a managed property in the SharePoint admin center. Here's why.</span></span>
  
<span data-ttu-id="19261-p107">例</span><span class="sxs-lookup"><span data-stu-id="19261-p107">In SharePoint Online and OneDrive for Business, the search index is built up by crawling the content on your sites. The crawler picks up content and metadata from the documents in the form of crawled properties. The search schema helps the crawler decide what content and metadata to pick up. Examples of metadata are the author and the title of a document. However, to get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties. Only managed properties are kept in the index. For example, a crawled property related to author is mapped to a managed property related to author.</span></span>
  
<span data-ttu-id="19261-p108">このマッピングは重要になります。Office 365 の DLP は検索クローラーを使用して、サイト上の機密情報を識別および分類し、その機密情報を検索インデックスのセキュリティで保護された部分に格納するからです。ドキュメントを Office 365 にアップロードすると、ドキュメント プロパティに基づいて、クロールされたプロパティが SharePoint によって自動作成されます。しかし DLP ポリシーで FCI または他のプロパティを使用するには、クロールされたプロパティを管理プロパティにマッピングし、そのプロパティが含まれるコンテンツをインデックスで保持できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19261-p108">This is important because DLP in Office 365 uses the search crawler to identify and classify sensitive information on your sites, and then store that sensitive information in a secure portion of the search index. When you upload a document to Office 365, SharePoint automatically creates crawled properties based on the document properties. But to use an FCI or other property in a DLP policy, that crawled property needs to be mapped to a managed property so that content with that property is kept in the index.</span></span>
  
<span data-ttu-id="19261-133">検索と管理プロパティの詳細については、 [SharePoint Online の検索スキーマの管理](http://go.microsoft.com/fwlink/p/?LinkID=627454)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19261-133">For more information on search and managed properties, see [Manage the search schema in SharePoint Online](http://go.microsoft.com/fwlink/p/?LinkID=627454).</span></span>
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a><span data-ttu-id="19261-134">手順 1: 必要なプロパティが含まれるドキュメントを Office 365 にアップロードする</span><span class="sxs-lookup"><span data-stu-id="19261-134">Step 1: Upload a document with the needed property to Office 365</span></span>

<span data-ttu-id="19261-p109">まず、DLP ポリシーで参照するプロパティを使用してドキュメントをアップロードする必要があります。Office 365 は、プロパティを検出し、そこからクロールされたプロパティを自動的に作成します。次の手順では、管理プロパティを作成し、このクロールされたプロパティを管理プロパティをマップします。</span><span class="sxs-lookup"><span data-stu-id="19261-p109">You first need to upload a document with the property that you want to reference in your DLP policy. Office 365 will detect the property and automatically create a crawled property from it. In the next step, you'll create a managed property, and then map the managed property to this crawled property.</span></span>
  
### <a name="step-2-create-a-managed-property"></a><span data-ttu-id="19261-138">手順 2: 管理プロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="19261-138">Step 2: Create a managed property</span></span>

1. <span data-ttu-id="19261-139">Office 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="19261-139">Sign in to the Office 365 admin center.</span></span>
    
2. <span data-ttu-id="19261-p110">左側のナビゲーションでは、**管理者が中央揃え**」を選択します\> **SharePoint**。SharePoint 管理センターを場合します。</span><span class="sxs-lookup"><span data-stu-id="19261-p110">In the left navigation, choose **Admin centers** \> **SharePoint**. You're now in the SharePoint admin center.</span></span>
    
3. <span data-ttu-id="19261-142">左側のナビゲーションでは、[**検索**] を選択\>[**検索管理**] ページで、 \> **検索スキーマを管理**します。</span><span class="sxs-lookup"><span data-stu-id="19261-142">In the left navigation, choose **search** \> on the **search administration** page \> **Manage Search Schema**.</span></span>
    
    ![SharePoint 管理センターの検索管理ページ](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. <span data-ttu-id="19261-144">**プロパティの管理**ページの [ \> **管理の新しいプロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="19261-144">On the **Managed Properties** page \> **New Managed Property**.</span></span>
    
    ![[新しい管理プロパティ] ボタンが強調表示されている[プロパティ管理] ページ](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. <span data-ttu-id="19261-p111">プロパティの名前と説明を入力します。この名前が、DLP ポリシーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="19261-p111">Enter a name and description for the property. This name is what will appear in your DLP policies.</span></span>
    
6. <span data-ttu-id="19261-148">[**型**] で [**テキスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19261-148">For **Type**, choose **Text**.</span></span> 
    
7. <span data-ttu-id="19261-149">[**主な特徴**] では [**クエリ可能**] と [**取得可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19261-149">Under **Main characteristics**, select **Queryable** and **Retrievable**.</span></span>
    
8. <span data-ttu-id="19261-150">[**クロールされたプロパティのマッピングを** \> **のマッピングを追加**します。</span><span class="sxs-lookup"><span data-stu-id="19261-150">Under **Mappings to crawled properties** \> **Add a mapping**.</span></span>
    
9. <span data-ttu-id="19261-151">**クロール プロパティの選択**] ダイアログ ボックスで\>を検索して、Windows サーバーの FCI プロパティまたは DLP ポリシーで使用する他のプロパティに対応するクロールされたプロパティを選択\> **OK**です。</span><span class="sxs-lookup"><span data-stu-id="19261-151">In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.</span></span>
    
    ![[クロールされたプロパティの選択] ダイアログ ボックス](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. <span data-ttu-id="19261-153">ページの下部にある\> **OK**です。</span><span class="sxs-lookup"><span data-stu-id="19261-153">At the bottom of the page \> **OK**.</span></span>
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a><span data-ttu-id="19261-154">FCI プロパティまたは他のプロパティを使用する DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="19261-154">Create a DLP policy that uses an FCI property or other property</span></span>

<span data-ttu-id="19261-p112">この例では、その Windows サーバー ベースのファイル サーバーで FCI を使っています。具体的には、**高**、**中**、**低**、**公開**、および**PII ではない**ので**個人情報**を指定した FCI 分類プロパティを使用しています。Office 365 の DLP ポリシーの既存の FCI 分類を活用するようになりました。</span><span class="sxs-lookup"><span data-stu-id="19261-p112">In this example, an organization is using FCI on its Windows Server-based file servers; specifically, they're using the FCI classification property named **Personally Identifiable Information** with possible values of **High**, **Moderate**, **Low**, **Public**, and **Not PII**. Now they want to leverage their existing FCI classification in their DLP policies in Office 365.</span></span>
  
<span data-ttu-id="19261-157">まず、前述の手順に従って SharePoint Online で管理プロパティを作成します。管理プロパティを、FCI に基づいて自動作成された、クロールされたプロパティにマッピングします。</span><span class="sxs-lookup"><span data-stu-id="19261-157">First, they follow the steps above to create a managed property in SharePoint Online, which maps to the crawled property created automatically from the FCI property.</span></span>
  
<span data-ttu-id="19261-158">次に、DLP ポリシーを**ドキュメントのプロパティが含まれているこれらの値のいずれかの**条件を両方使用している 2 つのルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="19261-158">Next, they create a DLP policy with two rules that both use the condition **Document properties contain any of these values**:</span></span>
  
- <span data-ttu-id="19261-159">**FCI の個人情報のコンテンツを高、中**FCI 分類プロパティ**を特定できる情報個人**が**高**または**中レベル**に相当し、組織外のユーザーとドキュメントを共有する場合、最初のルールは、ドキュメントにアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="19261-159">**FCI PII content - High, Moderate** The first rule restricts access to the document if the FCI classification property **Personally Identifiable Information** equals **High** or **Moderate** and the document is shared with people outside the organization.</span></span> 
    
- <span data-ttu-id="19261-160">**FCI PII コンテンツ - 低**2 番目のルールでは、FCI 分類プロパティの**個人情報**は、**低**と、ドキュメントと等しい場合、ドキュメントの所有者に通知するが、組織外のユーザーと共有を送信します。</span><span class="sxs-lookup"><span data-stu-id="19261-160">**FCI PII content - Low** The second rule sends a notification to the document owner if the FCI classification property **Personally Identifiable Information** equals **Low** and the document is shared with people outside the organization.</span></span> 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a><span data-ttu-id="19261-161">PowerShell を使用して、DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="19261-161">Create the DLP policy by using PowerShell</span></span>

<span data-ttu-id="19261-p113">**ドキュメント プロパティには、これらの値のいずれかが含まれている**条件が一時的に使用できないこと、セキュリティの UI に注意してください&amp;コンプライアンスの中心ですが、それでも条件を使用してこの PowerShell を使用しています。使用することができます、 `New\Set\Get-DlpCompliancePolicy` 、DLP ポリシーを使用してコマンドレット、`New\Set\Get-DlpComplianceRule`コマンドレットで、 `ContentPropertyContainsWords` **ドキュメントのプロパティが含まれているこれらの値のいずれかの**条件を追加するパラメーター。</span><span class="sxs-lookup"><span data-stu-id="19261-p113">Note that the condition **Document properties contain any of these values** is temporarily not available in the UI of the Security &amp; Compliance Center, but you can still use this condition by using PowerShell. You can use the  `New\Set\Get-DlpCompliancePolicy` cmdlets to work with a DLP policy, and use the  `New\Set\Get-DlpComplianceRule` cmdlets with the  `ContentPropertyContainsWords` parameter to add the condition **Document properties contain any of these values**.</span></span>
  
<span data-ttu-id="19261-164">これらのコマンドレットの詳細についてを参照してください[Office 365 のセキュリティ&amp;コンプライアンス センター コマンドレット](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="19261-164">For more information on these cmdlets, see [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).</span></span>
  
1. [<span data-ttu-id="19261-165">Office 365 のセキュリティへの接続&amp;リモート PowerShell を使用してコンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="19261-165">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="19261-166">使用してポリシーを作成する`New-DlpCompliancePolicy`。</span><span class="sxs-lookup"><span data-stu-id="19261-166">Create the policy by using  `New-DlpCompliancePolicy`.</span></span>
    
    <span data-ttu-id="19261-167">ここでは、すべての場所に適用される DLP ポリシーを作成する PowerShell の使用例です。</span><span class="sxs-lookup"><span data-stu-id="19261-167">Here is a PowerShell example that creates a DLP policy that applies to all locations.</span></span>
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. <span data-ttu-id="19261-168">使用して上記で説明した 2 つの規則を作成する`New-DlpComplianceRule`、**低**値の 1 つのルールでは、**高**または**中レベル**の値は、別のルールです。</span><span class="sxs-lookup"><span data-stu-id="19261-168">Create the two rules described above by using  `New-DlpComplianceRule`, where one rule is for the **Low** value, and another rule is for the **High** and **Moderate** values.</span></span> 
    
    <span data-ttu-id="19261-p114">ここでは、これら 2 つの規則を作成する PowerShell の使用例です。プロパティの名前と値のペアが、引用符で囲まれているし、プロパティ名と同様に、スペースなしでカンマで区切られた複数の値を指定ことがあることに注意してください。`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span><span class="sxs-lookup"><span data-stu-id="19261-p114">Here is a PowerShell example that creates these two rules. Note that the property name/value pairs are enclosed in quotation marks, and a property name may specify multiple values separated by commas with no spaces, like  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span></span>
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    <span data-ttu-id="19261-p115">Windows Server FCI に次の使用例で使用されている**個人情報**を含む、多くの組み込みプロパティが含まれていることに注意してください。各プロパティの値はすべての組織の別にすることはできます。**高**、**中程度**、およびここでは**低**値は、単なる一例です。組織の Windows サーバー ベースのファイル サーバー上のファイル サーバー リソース マネージャーで、使用可能な値を持つ Windows Server FCI 分類のプロパティを表示できます。詳細については、[分類プロパティの作成](http://go.microsoft.com/fwlink/p/?LinkID=627456)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19261-p115">Note that Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example. The possible values for each property can be different for every organization. The **High**, **Moderate**, and **Low** values used here are only an example. For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server. For more information, see [Create a classification property](http://go.microsoft.com/fwlink/p/?LinkID=627456).</span></span>
    
<span data-ttu-id="19261-p116">終了したら、ポリシーに 2 つの新しいルールが**ドキュメントのプロパティが含まれているこれらの値のいずれかの**条件を両方使用している必要があります。メモは、この条件は表示されません UI では、ただし、その他の条件、アクション、および設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19261-p116">When you finish, your policy should have two new rules that both use the **Document properties contain any of these values** condition. Note that this condition won't appear in the UI, though the other conditions, actions, and settings will appear.</span></span> 
  
<span data-ttu-id="19261-p117">ルールは 1 つのブロックは、**個人情報**プロパティが**高**または**中レベル**と同じコンテンツにアクセスします。2 番目のルールは、**個人情報**プロパティが**低**に等しいコンテンツに関する通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="19261-p117">One rule blocks access to content where the **Personally Identifiable Information** property equals **High** or **Moderate**. A second rule sends a notification about content where the **Personally Identifiable Information** property equals **Low**.</span></span>
  
![2 つのルールが作成されたことを示す[新しい DLP ポリシー] ダイアログ ボックス](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a><span data-ttu-id="19261-181">DLP ポリシーを作成した後に</span><span class="sxs-lookup"><span data-stu-id="19261-181">After you create the DLP policy</span></span>

<span data-ttu-id="19261-182">、そのプロパティを持つコンテンツがコンテンツを新しくアップロードされると、コンテンツのインデックスを作成)、DLP ポリシーを迅速に検出されますが作成されます、前のセクションの手順を実行またはコンテンツのある場合は古いですが、編集できるように、コンテンツの再インデックス付けされた).</span><span class="sxs-lookup"><span data-stu-id="19261-182">Doing the steps in the previous sections will create a DLP policy that will quickly detect content with that property, but only if that content is newly uploaded (so that the content's indexed), or if that content is old but just edited (so that the content's re-indexed).</span></span>
  
<span data-ttu-id="19261-p118">対象プロパティが含まれるコンテンツを検出するには、ライブラリ、サイト、サイト コレクションの再インデックス付けを手動で要求し、対象プロパティが含まれるコンテンツすべてを DLP ポリシーが認識するようにできます。SharePoint Online では、定義されているクロール スケジュールに基づいてコンテンツは自動的にクロールされます。クローラーは、最後にクロールされて以降に変更が加えられたコンテンツを取得して、インデックスを更新します。スケジュールされたクロールが次に実行される前にコンテンツを保護する DLP ポリシーが必要となる場合には、以下の手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="19261-p118">To detect content with that property everywhere, you may want to manually request that your library, site, or site collection be re-indexed, so that the DLP policy is aware of all the content with that property. In SharePoint Online, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index. If you need your DLP policy to protect content before the next scheduled crawl, you can take these steps.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="19261-p119">サイトのインデックスを再作成と、検索システムの大規模な負荷が発生する可能性がします。シナリオ絶対に必要としない限り、サイトをインデックス再しません。</span><span class="sxs-lookup"><span data-stu-id="19261-p119">Re-indexing a site can cause a massive load on the search system. Don't re-index your site unless your scenario absolutely requires it.</span></span> 
  
<span data-ttu-id="19261-189">詳細については、[クロールして、サイト、ライブラリまたはリストのインデックスの再作成を手動で要求](http://go.microsoft.com/fwlink/p/?LinkID=627457)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19261-189">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](http://go.microsoft.com/fwlink/p/?LinkID=627457).</span></span>
  
### <a name="re-index-a-site-optional"></a><span data-ttu-id="19261-190">サイトを再インデックス付けする (省略可能)</span><span class="sxs-lookup"><span data-stu-id="19261-190">Re-index a site (optional)</span></span>

1. <span data-ttu-id="19261-191">サイトの**設定**(右上の歯車アイコン) を選択します\>**サイトの設定**。</span><span class="sxs-lookup"><span data-stu-id="19261-191">On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="19261-192">[**検索**]、[**検索とオフラインでの可用性**を選択\>**サイトのインデックスを再作成**します。</span><span class="sxs-lookup"><span data-stu-id="19261-192">Under **Search**, choose **Search and offline availability** \> **Reindex site**.</span></span>
    
## <a name="more-information"></a><span data-ttu-id="19261-193">詳細情報</span><span class="sxs-lookup"><span data-stu-id="19261-193">More information</span></span>

- [<span data-ttu-id="19261-194">データ損失防止ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="19261-194">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="19261-195">テンプレートから DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="19261-195">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="19261-196">DLP ポリシーに関する通知を送信してポリシー ヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="19261-196">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="19261-197">DLP ポリシー テンプレートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="19261-197">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="19261-198">機密情報の種類のインベントリ</span><span class="sxs-lookup"><span data-stu-id="19261-198">Sensitive information types inventory</span></span>](what-the-sensitive-information-types-look-for.md)
    

