---
title: FCI または他のプロパティが使用されているドキュメントを保護する DLP ポリシーを作成する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 多くの組織では、Windows Server ファイル分類インフラストラクチャ (FCI) の分類プロパティ、SharePoint のドキュメントプロパティ、またはドキュメントプロパティを使用して、機密情報を識別して分類するプロセスが既に存在します。サードパーティ製のシステムによって適用されます。 これが組織を説明している場合は、Office 365 で、Windows Server FCI または他のシステムによってドキュメントに適用されたプロパティを認識する DLP ポリシーを作成して、特定の FCI またはその他の Office ドキュメントに DLP ポリシーを適用できるようにすることができます。プロパティの値。
ms.openlocfilehash: 5f464c2918d7ea91fa5c65b28bc477ee7cc768e3
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230961"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a><span data-ttu-id="47e3f-104">FCI または他のプロパティを使用したドキュメントを保護する DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="47e3f-104">Create a DLP policy to protect documents with FCI or other properties</span></span>

<span data-ttu-id="47e3f-p102">Office 365 でデータ損失防止 (DLP) ポリシーを使用すると、機密情報の識別、監視、保護を行えます。多くの組織には、Windows Server ファイル分類インフラストラクチャ (FCI) の分類プロパティ、SharePoint のドキュメント プロパティ、またはサード パーティによって適用されたドキュメント プロパティを使用して機密情報を識別および分類するプロセスが既に存在します。ご自分の組織でもこの状況が当てはまる場合、Offce 365 で DLP ポリシーを作成できます。このポリシーは、Windows Server FCI または他のシステムによってドキュメントに適用されているプロパティを認識し、特定の FCI 値または他のプロパティ値が含まれる Office ドキュメントに DLP ポリシーを適用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="47e3f-p102">In Office 365, you can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information. Many organizations already have a process to identify and classify sensitive information by using the classification properties in Windows Server File Classification Infrastructure (FCI), the document properties in SharePoint, or the document properties applied by a third-party system. If this describes your organization, you can create a DLP policy in Office 365 that recognizes the properties that have been applied to documents by Windows Server FCI or other system, so that the DLP policy can be enforced on Office documents with specific FCI or other property values.</span></span>
  
![Office 365 と外部の分類システムを示す図](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
<span data-ttu-id="47e3f-109">たとえば、組織において、Windows Server FCI を使用して社会保障番号などの個人情報 (PII) が含まれるドキュメントを識別し、ドキュメント内で検出された個人情報の種類と検出回数に基づいて [**個人情報**] プロパティを [**高**]、[**中**]、[**低**]、[**公開**]、または [**個人情報ではない**] に設定することによってドキュメントの分類を行っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="47e3f-109">For example, your organization might use Windows Server FCI to identify documents with personally identifiable information (PII) such as social security numbers, and then classify the document by setting the **Personally Identifiable Information** property to **High**, **Moderate**, **Low**, **Public**, or **Not PII** based on the type and number of occurrences of PII found in the document.</span></span> <span data-ttu-id="47e3f-110">Office 365 では、それらのプロパティが [**高**] や [**中**] などの特定の値に設定されているドキュメントを識別し、それらのファイルに対するアクセスをブロックするなどのアクションを実行する DLP ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="47e3f-110">In Office 365, you can create a DLP policy that identifies documents that have that property set to specific values, such as **High** and **Medium**, and then takes an action such as blocking access to those files.</span></span> <span data-ttu-id="47e3f-111">プロパティが [**低**] に設定されている場合には (電子メールの通知送信などの) 異なるアクションを実行する別のルールを同じポリシーに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="47e3f-111">The same policy can have another rule that takes a different action if the property is set to **Low**, such as sending an email notification.</span></span> <span data-ttu-id="47e3f-112">このようにして、Office 365 の DLP が Windows Server FCI と統合されており、Windows Server ベースのファイルサーバーから Office 365 にアップロードまたは共有される Office ドキュメントを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="47e3f-112">In this way, DLP in Office 365 integrates with Windows Server FCI and can help protect Office documents uploaded or shared to Office 365 from Windows Server-based file servers.</span></span>
  
<span data-ttu-id="47e3f-p104">DLP ポリシーは、特定のプロパティの名前と値のペアを探すだけです。対象プロパティに SharePoint 検索の対応する管理プロパティが含まれる場合には、任意のドキュメント プロパティを使用できます。たとえば、SharePoint のサイト コレクションが [**旅行レポート**] という名前のコンテンツの種類を使用し、[**顧客**] という必須フィールドが指定されているとします。ユーザーが旅行レポートを作成するたびに、顧客名を入力する必要が生じます。このプロパティの名前と値のペアを DLP ポリシーでも使用できます。たとえば、[**顧客**] フィールドに [**Contoso**] が含まれるときに外部ユーザーによるドキュメントへのアクセスをブロックするルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="47e3f-p104">A DLP policy simply looks for a specific property name/value pair. Any document property can be used, as long as the property has a corresponding managed property for SharePoint search. For example, a SharePoint site collection might use a content type named **Trip Report** with a required field named **Customer**. Whenever a person creates a trip report, they must enter the customer name. This property name/value pair can also be used in a DLP policy — for example, if you want a rule that blocks access to the document for external users when the **Customer** field contains **Contoso**.</span></span>
  
<span data-ttu-id="47e3f-118">特定の Office 365 ラベルを含むコンテンツに DLP ポリシーを適用する場合は、ここに記載されている手順に従ってはいけないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="47e3f-118">Note that if you want to apply your DLP policy to content with specific Office 365 labels, you should not follow the steps here.</span></span> <span data-ttu-id="47e3f-119">代わりに、 [DLP ポリシーの条件としてラベルを使用](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-119">Instead, learn how to [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
  
## <a name="before-you-create-the-dlp-policy"></a><span data-ttu-id="47e3f-120">DLP ポリシーを作成する前に</span><span class="sxs-lookup"><span data-stu-id="47e3f-120">Before you create the DLP policy</span></span>

<span data-ttu-id="47e3f-121">DLP ポリシーで Windows Server FCI プロパティまたは他のプロパティを使用するには、その前に、SharePoint 管理センターで管理プロパティを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47e3f-121">Before you can use a Windows Server FCI property or other property in a DLP policy, you need to create a managed property in the SharePoint admin center.</span></span> <span data-ttu-id="47e3f-122">理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="47e3f-122">Here's why.</span></span>
  
<span data-ttu-id="47e3f-p107">例</span><span class="sxs-lookup"><span data-stu-id="47e3f-p107">In SharePoint Online and OneDrive for Business, the search index is built up by crawling the content on your sites. The crawler picks up content and metadata from the documents in the form of crawled properties. The search schema helps the crawler decide what content and metadata to pick up. Examples of metadata are the author and the title of a document. However, to get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties. Only managed properties are kept in the index. For example, a crawled property related to author is mapped to a managed property related to author.</span></span>
  
<span data-ttu-id="47e3f-p108">このマッピングは重要になります。Office 365 の DLP は検索クローラーを使用して、サイト上の機密情報を識別および分類し、その機密情報を検索インデックスのセキュリティで保護された部分に格納するからです。ドキュメントを Office 365 にアップロードすると、ドキュメント プロパティに基づいて、クロールされたプロパティが SharePoint によって自動作成されます。しかし DLP ポリシーで FCI または他のプロパティを使用するには、クロールされたプロパティを管理プロパティにマッピングし、そのプロパティが含まれるコンテンツをインデックスで保持できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="47e3f-p108">This is important because DLP in Office 365 uses the search crawler to identify and classify sensitive information on your sites, and then store that sensitive information in a secure portion of the search index. When you upload a document to Office 365, SharePoint automatically creates crawled properties based on the document properties. But to use an FCI or other property in a DLP policy, that crawled property needs to be mapped to a managed property so that content with that property is kept in the index.</span></span>
  
<span data-ttu-id="47e3f-133">検索および管理プロパティの詳細については、「 [SharePoint Online で検索スキーマを管理する](http://go.microsoft.com/fwlink/p/?LinkID=627454)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47e3f-133">For more information on search and managed properties, see [Manage the search schema in SharePoint Online](http://go.microsoft.com/fwlink/p/?LinkID=627454).</span></span>
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a><span data-ttu-id="47e3f-134">手順 1: 必要なプロパティが含まれるドキュメントを Office 365 にアップロードする</span><span class="sxs-lookup"><span data-stu-id="47e3f-134">Step 1: Upload a document with the needed property to Office 365</span></span>

<span data-ttu-id="47e3f-135">最初に、DLP ポリシーで参照するプロパティが含まれるドキュメントをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="47e3f-135">You first need to upload a document with the property that you want to reference in your DLP policy.</span></span> <span data-ttu-id="47e3f-136">Office 365 はこのプロパティを検出し、それに基づいて、クロールされたプロパティを自動作成します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-136">Office 365 will detect the property and automatically create a crawled property from it.</span></span> <span data-ttu-id="47e3f-137">次の手順では、管理プロパティを作成し、管理プロパティをこのクロールされたプロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="47e3f-137">In the next step, you'll create a managed property, and then map the managed property to this crawled property.</span></span>
  
### <a name="step-2-create-a-managed-property"></a><span data-ttu-id="47e3f-138">手順 2: 管理プロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="47e3f-138">Step 2: Create a managed property</span></span>

1. <span data-ttu-id="47e3f-139">Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="47e3f-139">Sign in to the Microsoft 365 admin center.</span></span>
    
2. <span data-ttu-id="47e3f-140">左側のナビゲーションで、[**管理センター** \> **SharePoint**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-140">In the left navigation, choose **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="47e3f-141">SharePoint 管理センターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47e3f-141">You're now in the SharePoint admin center.</span></span>
    
3. <span data-ttu-id="47e3f-142">左側のナビゲーションで、[ \*\*\*\* \>検索**管理**] ページ\>の [検索] を選択します。**検索スキーマを管理**します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-142">In the left navigation, choose **search** \> on the **search administration** page \> **Manage Search Schema**.</span></span>
    
    ![SharePoint 管理センターの検索管理ページ](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. <span data-ttu-id="47e3f-144">[**管理プロパティ**] ページ\>で、**新しい管理プロパティを追加**します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-144">On the **Managed Properties** page \> **New Managed Property**.</span></span>
    
    ![[新しい管理プロパティ] ボタンが強調表示されている[プロパティ管理] ページ](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. <span data-ttu-id="47e3f-p111">プロパティの名前と説明を入力します。この名前が、DLP ポリシーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="47e3f-p111">Enter a name and description for the property. This name is what will appear in your DLP policies.</span></span>
    
6. <span data-ttu-id="47e3f-148">[**型**] で [**テキスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-148">For **Type**, choose **Text**.</span></span> 
    
7. <span data-ttu-id="47e3f-149">[**主な特徴**] では [**クエリ可能**] と [**取得可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-149">Under **Main characteristics**, select **Queryable** and **Retrievable**.</span></span>
    
8. <span data-ttu-id="47e3f-150">[**クロール** \>されたプロパティへのマッピング] で**マッピングを追加**します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-150">Under **Mappings to crawled properties** \> **Add a mapping**.</span></span>
    
9. <span data-ttu-id="47e3f-151">[クロールされたプロパティの\> **選択**] ダイアログボックスで、DLP ポリシー \> \*\*\*\* で使用する Windows Server fci プロパティまたはその他のプロパティに対応するクロールされたプロパティを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-151">In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.</span></span>
    
    ![[クロールされたプロパティの選択] ダイアログ ボックス](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. <span data-ttu-id="47e3f-153">ページ\>の下部にある **[OK] をクリック**します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-153">At the bottom of the page \> **OK**.</span></span>
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a><span data-ttu-id="47e3f-154">FCI プロパティまたは他のプロパティを使用する DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="47e3f-154">Create a DLP policy that uses an FCI property or other property</span></span>

<span data-ttu-id="47e3f-155">この例では、組織が Windows Server ベースのファイルサーバー上で FCI を使用しています。具体的には、[**高**]、[中]、[**低**]、[**パブリック**]、 \*\*\*\* および [PII] で**はなく**、可能な値を持つ、"**個人識別情報**" という名前の fci 分類プロパティを使用しています。</span><span class="sxs-lookup"><span data-stu-id="47e3f-155">In this example, an organization is using FCI on its Windows Server-based file servers; specifically, they're using the FCI classification property named **Personally Identifiable Information** with possible values of **High**, **Moderate**, **Low**, **Public**, and **Not PII**.</span></span> <span data-ttu-id="47e3f-156">ここで、Office 365 の DLP ポリシーで既存の FCI 分類を活用することを希望しています。</span><span class="sxs-lookup"><span data-stu-id="47e3f-156">Now they want to leverage their existing FCI classification in their DLP policies in Office 365.</span></span>
  
<span data-ttu-id="47e3f-157">まず、前述の手順に従って SharePoint Online で管理プロパティを作成します。管理プロパティを、FCI に基づいて自動作成された、クロールされたプロパティにマッピングします。</span><span class="sxs-lookup"><span data-stu-id="47e3f-157">First, they follow the steps above to create a managed property in SharePoint Online, which maps to the crawled property created automatically from the FCI property.</span></span>
  
<span data-ttu-id="47e3f-158">次に、2つのルールを使用する DLP ポリシーを作成します。両方のプロパティには、条件**ドキュメントプロパティに次のいずれかの値が含まれ**ています。</span><span class="sxs-lookup"><span data-stu-id="47e3f-158">Next, they create a DLP policy with two rules that both use the condition **Document properties contain any of these values**:</span></span>
  
- <span data-ttu-id="47e3f-159">**Fci PII コンテンツ-高、** 中最初のルールは、FCI 分類プロパティの個人を特定できる**情報**が**高**または**モデレート**で、ドキュメントが組織外のユーザーと共有されている場合に、ドキュメントへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-159">**FCI PII content - High, Moderate** The first rule restricts access to the document if the FCI classification property **Personally Identifiable Information** equals **High** or **Moderate** and the document is shared with people outside the organization.</span></span> 
    
- <span data-ttu-id="47e3f-160">**Fci PII コンテンツ-低**2番目のルールは、FCI 分類プロパティの個人を特定できる**情報**が**少なく**、ドキュメントが組織外のユーザーと共有されている場合に、ドキュメント所有者に通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-160">**FCI PII content - Low** The second rule sends a notification to the document owner if the FCI classification property **Personally Identifiable Information** equals **Low** and the document is shared with people outside the organization.</span></span> 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a><span data-ttu-id="47e3f-161">PowerShell を使用して DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="47e3f-161">Create the DLP policy by using PowerShell</span></span>

<span data-ttu-id="47e3f-162">Condition**ドキュメントプロパティにこれらの値のいずれかが含ま**れていることに注意してください&amp; 。これらの値は、セキュリティコンプライアンスセンターの UI では一時的に使用できませんが、PowerShell を使用してこの条件を引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="47e3f-162">Note that the condition **Document properties contain any of these values** is temporarily not available in the UI of the Security &amp; Compliance Center, but you can still use this condition by using PowerShell.</span></span> <span data-ttu-id="47e3f-163">コマンドレットを使用して DLP ポリシーを操作`ContentPropertyContainsWords`し、パラメーターを指定`New\Set\Get-DlpComplianceRule`したコマンドレットを使用して、条件**ドキュメントプロパティにこれらの値のいずれかを含める**ことができます。 `New\Set\Get-DlpCompliancePolicy`</span><span class="sxs-lookup"><span data-stu-id="47e3f-163">You can use the  `New\Set\Get-DlpCompliancePolicy` cmdlets to work with a DLP policy, and use the  `New\Set\Get-DlpComplianceRule` cmdlets with the  `ContentPropertyContainsWords` parameter to add the condition **Document properties contain any of these values**.</span></span>
  
<span data-ttu-id="47e3f-164">これらのコマンドレットの詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのコマンドレット](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47e3f-164">For more information on these cmdlets, see [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).</span></span>
  
1. [<span data-ttu-id="47e3f-165">リモート PowerShell を使用して Office 365 セキュリティ/コンプライアンス センターに接続する</span><span class="sxs-lookup"><span data-stu-id="47e3f-165">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="47e3f-166">を使用`New-DlpCompliancePolicy`してポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-166">Create the policy by using  `New-DlpCompliancePolicy`.</span></span>
    
    <span data-ttu-id="47e3f-167">すべての場所に適用する DLP ポリシーを作成する PowerShell の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-167">Here is a PowerShell example that creates a DLP policy that applies to all locations.</span></span>
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. <span data-ttu-id="47e3f-168">上記の2つのルールを使用`New-DlpComplianceRule`して、1つのルールを**低**値に、もう1つは**高**および中**程度**のルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-168">Create the two rules described above by using  `New-DlpComplianceRule`, where one rule is for the **Low** value, and another rule is for the **High** and **Moderate** values.</span></span> 
    
    <span data-ttu-id="47e3f-169">これら2つのルールを作成する PowerShell の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-169">Here is a PowerShell example that creates these two rules.</span></span> <span data-ttu-id="47e3f-170">プロパティ名と値のペアは二重引用符で囲まれており、プロパティ名でコンマで区切って複数の値を指定する場合は、次のようにスペースを含めません。`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span><span class="sxs-lookup"><span data-stu-id="47e3f-170">Note that the property name/value pairs are enclosed in quotation marks, and a property name may specify multiple values separated by commas with no spaces, like  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span></span>
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    <span data-ttu-id="47e3f-171">Windows Server FCI には、この例で使用されている**個人を特定できる情報**を含む、多くの組み込みのプロパティが含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="47e3f-171">Note that Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example.</span></span> <span data-ttu-id="47e3f-172">各プロパティに指定できる値は、すべての組織によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="47e3f-172">The possible values for each property can be different for every organization.</span></span> <span data-ttu-id="47e3f-173">ここで使用\*\*\*\* されているのは、次に示すように、**高**、中、**低**の値だけです。</span><span class="sxs-lookup"><span data-stu-id="47e3f-173">The **High**, **Moderate**, and **Low** values used here are only an example.</span></span> <span data-ttu-id="47e3f-174">組織では、windows server FCI 分類プロパティを、Windows Server ベースのファイルサーバー上のファイルサーバーリソースマネージャーで指定可能な値で表示できます。</span><span class="sxs-lookup"><span data-stu-id="47e3f-174">For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server.</span></span> <span data-ttu-id="47e3f-175">詳細については、「[分類プロパティを作成する](http://go.microsoft.com/fwlink/p/?LinkID=627456)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47e3f-175">For more information, see [Create a classification property](http://go.microsoft.com/fwlink/p/?LinkID=627456).</span></span>
    
<span data-ttu-id="47e3f-176">完了したら、ドキュメントプロパティを使用する2つの新しいルールに**これらの値の条件が含まれ**ている必要があります。</span><span class="sxs-lookup"><span data-stu-id="47e3f-176">When you finish, your policy should have two new rules that both use the **Document properties contain any of these values** condition.</span></span> <span data-ttu-id="47e3f-177">この条件は UI には表示されませんが、他の条件、アクション、設定が表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="47e3f-177">Note that this condition won't appear in the UI, though the other conditions, actions, and settings will appear.</span></span> 
  
<span data-ttu-id="47e3f-178">1 つのルールは、[**個人情報**] プロパティが [**高**] または [**中**] の場合にコンテンツへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="47e3f-178">One rule blocks access to content where the **Personally Identifiable Information** property equals **High** or **Moderate**.</span></span> <span data-ttu-id="47e3f-179">2 番目のルールは、[**個人情報**] プロパティが [**低**] の場合にコンテンツについて通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-179">A second rule sends a notification about content where the **Personally Identifiable Information** property equals **Low**.</span></span>
  
![2 つのルールが作成されたことを示す[新しい DLP ポリシー] ダイアログ ボックス](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a><span data-ttu-id="47e3f-181">DLP ポリシーを作成した後に</span><span class="sxs-lookup"><span data-stu-id="47e3f-181">After you create the DLP policy</span></span>

<span data-ttu-id="47e3f-182">前のセクションの手順を実行すると、そのプロパティを使用してコンテンツを迅速に検出する DLP ポリシーが作成されます。ただし、そのコンテンツが新しくアップロードされた場合 (コンテンツのインデックスが作成されます)、またはそのコンテンツが古く、編集された (コンテンツの再インデックスが作成される) 場合のみです。.</span><span class="sxs-lookup"><span data-stu-id="47e3f-182">Doing the steps in the previous sections will create a DLP policy that will quickly detect content with that property, but only if that content is newly uploaded (so that the content's indexed), or if that content is old but just edited (so that the content's re-indexed).</span></span>
  
<span data-ttu-id="47e3f-p118">対象プロパティが含まれるコンテンツを検出するには、ライブラリ、サイト、サイト コレクションの再インデックス付けを手動で要求し、対象プロパティが含まれるコンテンツすべてを DLP ポリシーが認識するようにできます。SharePoint Online では、定義されているクロール スケジュールに基づいてコンテンツは自動的にクロールされます。クローラーは、最後にクロールされて以降に変更が加えられたコンテンツを取得して、インデックスを更新します。スケジュールされたクロールが次に実行される前にコンテンツを保護する DLP ポリシーが必要となる場合には、以下の手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="47e3f-p118">To detect content with that property everywhere, you may want to manually request that your library, site, or site collection be re-indexed, so that the DLP policy is aware of all the content with that property. In SharePoint Online, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index. If you need your DLP policy to protect content before the next scheduled crawl, you can take these steps.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="47e3f-187">サイトを再インデックス付けすると、検索システムで多大な負荷が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="47e3f-187">Re-indexing a site can cause a massive load on the search system.</span></span> <span data-ttu-id="47e3f-188">シナリオで絶対に必要でない限り、サイトを再インデックス化しないでください。</span><span class="sxs-lookup"><span data-stu-id="47e3f-188">Don't re-index your site unless your scenario absolutely requires it.</span></span> 
  
<span data-ttu-id="47e3f-189">詳細については、「[サイト、ライブラリ、またはリストのクロールとインデックス再作成を手動で要求](http://go.microsoft.com/fwlink/p/?LinkID=627457)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47e3f-189">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](http://go.microsoft.com/fwlink/p/?LinkID=627457).</span></span>
  
### <a name="re-index-a-site-optional"></a><span data-ttu-id="47e3f-190">サイトを再インデックス付けする (省略可能)</span><span class="sxs-lookup"><span data-stu-id="47e3f-190">Re-index a site (optional)</span></span>

1. <span data-ttu-id="47e3f-191">サイトで、[**設定**] (右上にある歯車アイコン\> ) [**サイトの設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-191">On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="47e3f-192">[**検索**] で、[**検索とオフライン可用性** \> **インデックス作成サイト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47e3f-192">Under **Search**, choose **Search and offline availability** \> **Reindex site**.</span></span>
    
## <a name="more-information"></a><span data-ttu-id="47e3f-193">詳細情報</span><span class="sxs-lookup"><span data-stu-id="47e3f-193">More information</span></span>

- [<span data-ttu-id="47e3f-194">データ損失防止ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="47e3f-194">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="47e3f-195">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="47e3f-195">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="47e3f-196">通知を送信して、DLP ポリシーのポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="47e3f-196">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="47e3f-197">DLP ポリシー テンプレートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="47e3f-197">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="47e3f-198">機密情報の種類インベントリ</span><span class="sxs-lookup"><span data-stu-id="47e3f-198">Sensitive information types inventory</span></span>](what-the-sensitive-information-types-look-for.md)
    

