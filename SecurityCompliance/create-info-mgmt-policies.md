---
title: 作成し、情報管理ポリシーを適用します。
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
description: 情報管理ポリシーは、組織にどのような人か、コンテンツを監査し、バーコードを追加するのには、コンテンツの保存期間の制御、またはドキュメントにラベルを有効にします。ポリシーは、法的および政府の規制や社内の業務プロセスへの準拠を強制できます。ドキュメントを追跡する方法を制御する管理者は、ポリシーを設定でき、ドキュメントの保存期間です。
ms.openlocfilehash: cc15b7d830e6c13e00045f7e4b672ac4a755a70e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531835"
---
# <a name="create-and-apply-information-management-policies"></a><span data-ttu-id="abfba-105">作成し、情報管理ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="abfba-105">Create and apply information management policies</span></span>

<span data-ttu-id="abfba-p102">情報管理ポリシーは、組織にどのような人か、コンテンツを監査し、バーコードを追加するのには、コンテンツの保存期間の制御、またはドキュメントにラベルを有効にします。ポリシーは、法的および政府の規制や社内の業務プロセスへの準拠を強制できます。ドキュメントを追跡する方法を制御する管理者は、ポリシーを設定でき、ドキュメントの保存期間です。</span><span class="sxs-lookup"><span data-stu-id="abfba-p102">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents. A policy can help enforce compliance with legal and governmental regulations or internal business processes. As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>
  
<span data-ttu-id="abfba-109">情報管理ポリシーのことを作成するには広範かつからサイト階層で、3 つの異なる場所で、狭い。</span><span class="sxs-lookup"><span data-stu-id="abfba-109">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
  
- <span data-ttu-id="abfba-110">サイト コレクション内の複数のコンテンツ タイプで使用するポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="abfba-110">Create a policy to use on multiple content types within a site collection.</span></span>
    
- <span data-ttu-id="abfba-111">サイト コンテンツ タイプのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="abfba-111">Create a policy for a site content type.</span></span>
    
- <span data-ttu-id="abfba-112">リストまたはライブラリのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="abfba-112">Create a policy for a list or library.</span></span>
    
<span data-ttu-id="abfba-113">詳細については、[情報管理ポリシーの概要](intro-to-info-mgmt-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abfba-113">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a><span data-ttu-id="abfba-114">サイト コレクション内の複数のコンテンツ タイプのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="abfba-114">Create a policy for multiple content types within a site collection</span></span>
<span data-ttu-id="abfba-115"><a name="__toc261001590"> </a></span><span class="sxs-lookup"><span data-stu-id="abfba-115"></span></span>

<span data-ttu-id="abfba-p103">サイト コレクション内の特定の種類のすべてのドキュメントに情報ポリシーが適用されていることを確認するには、サイト コレクション レベルでポリシーの作成を検討してくださいし、コンテンツ タイプにポリシーを適用し、後で。サイト コレクション ポリシーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="abfba-p103">To ensure that an information policy is applied to all documents of a certain type within a site collection, consider creating the policy at the site collection level and then later apply the policy to content types. These are referred to as site collection policies.</span></span> 
  
1. <span data-ttu-id="abfba-p104">サイト コレクションのホーム ページに\>**の設定**![のタイトル バーに [SharePoint 2016 の設定] ボタン。](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **サイトの設定**。</span><span class="sxs-lookup"><span data-stu-id="abfba-p104">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Site Settings**.</span></span>
    
    <span data-ttu-id="abfba-120">SharePoint グループに接続されたサイトの**設定**] をクリックして**サイトの内容**を**サイトの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abfba-120">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="abfba-121">サイトの設定ページで、[**サイト コレクションの管理** \> **コンテンツ タイプ ポリシーのテンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="abfba-121">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![[サイトの設定] ページの [コンテンツ タイプ ポリシーのテンプレート] リンク](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="abfba-123">[ポリシー] ページで、 \> **を作成**します。</span><span class="sxs-lookup"><span data-stu-id="abfba-123">On the Policies page \> **Create**.</span></span> 
    
4. <span data-ttu-id="abfba-124">名と、ポリシーの説明を入力し、ユーザーのポリシーの目的を説明する簡単なポリシー ステートメントを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="abfba-124">Enter a name and description for the policy, and then write a brief policy statement that explains to users what the policy is for.</span></span>
    
5. <span data-ttu-id="abfba-125">ポリシーに関連付ける機能を設定する方法については、サイト コンテンツ タイプのポリシーを作成するのには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="abfba-125">See the next section on creating policies for a site content type to learn how to set up the features you want to associate with the policy.</span></span> 
    
6. <span data-ttu-id="abfba-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abfba-126">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-site-content-type"></a><span data-ttu-id="abfba-127">サイト コンテンツ タイプのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="abfba-127">Create a policy for a site content type</span></span>
<span data-ttu-id="abfba-128"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="abfba-128"></span></span>

<span data-ttu-id="abfba-p105">コンテンツ タイプに情報管理ポリシーに追加すると、ポリシーの機能を複数のリストまたはライブラリに関連付けるに簡単。コンテンツ タイプに既存の情報管理ポリシーを追加または個々 のコンテンツ タイプに固有の一意なポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="abfba-p105">Adding an information management policy to a content type makes it easy to associate policy features with multiple lists or libraries. You can choose to add an existing information management policy to a content type or create a unique policy specific to an individual content type.</span></span>
  
 <span data-ttu-id="abfba-p106">リストに固有のコンテンツ タイプに情報管理ポリシーを追加することもできます。ポリシーを適用するコンテンツ タイプを使用しているリスト内のアイテムにのみ効果があります。</span><span class="sxs-lookup"><span data-stu-id="abfba-p106">You can also add an information management policy to a content type that is specific to lists. This has the effect of applying the policy only to items in that list that are using the content type.</span></span> 
  
1. <span data-ttu-id="abfba-p107">サイト コレクションのホーム ページに\>**の設定**![のタイトル バーに [SharePoint 2016 の設定] ボタン。](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **サイトの設定**。</span><span class="sxs-lookup"><span data-stu-id="abfba-p107">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Site Settings**.</span></span>
    
    <span data-ttu-id="abfba-135">SharePoint グループに接続されたサイトの**設定**] をクリックして**サイトの内容**を**サイトの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abfba-135">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="abfba-136">サイトの設定ページで、 **Web デザイナーのギャラリー**の下にある\>**サイトのコンテンツ タイプ**。</span><span class="sxs-lookup"><span data-stu-id="abfba-136">On the Site Settings page, under **Web Designer Galleries** \> **Site content types**.</span></span>
  
![[サイトの設定] ページの [サイト コンテンツ タイプ] リンク](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. <span data-ttu-id="abfba-138">[サイト コンテンツ タイプの設定] ページで、ポリシーを追加するコンテンツ タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-138">On the Site Content Type Settings page, select the content type that you want to add a policy to.</span></span>
    
4. <span data-ttu-id="abfba-139">サイト コンテンツ タイプ] ページの [**設定**] の下に\>**の情報管理ポリシーの設定**。</span><span class="sxs-lookup"><span data-stu-id="abfba-139">On the Site Content Type page, under **Settings** \> **Information management policy settings**.</span></span>
    
5. <span data-ttu-id="abfba-140">[ポリシーの編集] ページで、名と、ポリシーの説明を入力し、ユーザーのポリシーの目的を説明する簡単な説明を記述し。</span><span class="sxs-lookup"><span data-stu-id="abfba-140">On the Edit Policy page, enter a name and description for the policy, and then write a brief description that explains to users what the policy is for.</span></span>
    
6. <span data-ttu-id="abfba-141">次のセクションで、情報管理ポリシーに追加する各ポリシー機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-141">In the next sections, select the individual policy features that you want to add to your information management policy.</span></span> 
  
![コンテンツ ポリシーの種類](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. <span data-ttu-id="abfba-143">ドキュメントおよびこのポリシーが適用されているアイテムの保存期間を指定するには、**保存管理機能を有効にする**を選択し、保持期間をおよびアイテムの有効期限が切れるときに発生するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="abfba-143">To specify a retention period for documents and items that are subject to this policy, choose **Enable Retention**, and then specify the retention period and the actions that you want to occur when the items expire.</span></span>
    
    <span data-ttu-id="abfba-144">保存期間を指定するのには</span><span class="sxs-lookup"><span data-stu-id="abfba-144">To specify a retention period</span></span>
    
||||||<span data-ttu-id="abfba-145">**1。**</span><span class="sxs-lookup"><span data-stu-id="abfba-145">**1.**</span></span>|<span data-ttu-id="abfba-146">* * [* *] レコードの保持ステージを追加。</span><span class="sxs-lookup"><span data-stu-id="abfba-146">**Choose **Add a retention stage for records…****</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="abfba-147">2.</span><span class="sxs-lookup"><span data-stu-id="abfba-147">2.</span></span>  <br/> | <span data-ttu-id="abfba-p108">ドキュメントまたはアイテムが期限切れに設定するときを指定する保持期間オプションを選択します。次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="abfba-p108">Select a retention period option to specify when documents or items are set to expire. Do one of the following:  </span></span><br/>  <span data-ttu-id="abfba-150">**イベント**] の下の日付プロパティに基づいて有効期限の日付を設定するのには\>**アイテムの日付プロパティに基づくこの段階では**、ドキュメントまたはアイテムのアクション (たとえば、作成または変更) を選択し、このアクション (後の時間の単位たとえば、日数、月数、または年の数)、アイテムを期限切れにする場合します。</span><span class="sxs-lookup"><span data-stu-id="abfba-150">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span>  <br/>  <span data-ttu-id="abfba-151">カスタム保持期間の数式を使用して、有効期限を設定するのには、**このサーバーにインストールされているカスタム保持期間の数式で設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-151">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span>  <br/> <span data-ttu-id="abfba-152">> [!NOTE]> このオプションには、管理者がユーザー設定の数式が設定されている場合にできるだけです。</span><span class="sxs-lookup"><span data-stu-id="abfba-152">> [!NOTE]>  This option is only available if a custom formula has been set up by your administrator.</span></span>           |
||||||<span data-ttu-id="abfba-153">3.</span><span class="sxs-lookup"><span data-stu-id="abfba-153">3.</span></span>  <br/> |<span data-ttu-id="abfba-p109">**ワークフローを開始する**] オプションでは、リスト、ライブラリ、または既に関連付けられているワークフローをコンテンツ タイプのポリシーを定義している場合にのみがあります。あるから選択するワークフローを選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-p109">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it. You will then be given a choice of workflows to choose from.  </span></span><br/> |
||||||<span data-ttu-id="abfba-156">4.</span><span class="sxs-lookup"><span data-stu-id="abfba-156">4.</span></span>  <br/> |<span data-ttu-id="abfba-157">[**定期的なアイテム**] セクションでの選択 **] にこの段階の操作を繰り返します。** 再発を操作する頻度を入力してください。</span><span class="sxs-lookup"><span data-stu-id="abfba-157">In the **Recurrence** section, select **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span>  <br/> <span data-ttu-id="abfba-p110">> [!NOTE]> このオプションには、選択したアクションを繰り返すことができる場合だけです。など**を完全に削除**アクションの繰り返しを設定できません。</span><span class="sxs-lookup"><span data-stu-id="abfba-p110">> [!NOTE]>  This option is only available if the action you selected can be repeated. For example, you cannot set recurrence for the action **Permanently Delete**.</span></span>           |
||||||<span data-ttu-id="abfba-160">5.</span><span class="sxs-lookup"><span data-stu-id="abfba-160">5.</span></span>  <br/> |<span data-ttu-id="abfba-161">**[Ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-161">Chose **OK**.</span></span>  <br/> |
   
1. <span data-ttu-id="abfba-162">ドキュメントおよびこのポリシーが適用されているアイテムに対して監査を有効にするには、**監査を有効にする**] を選択し、監査するイベントを指定します。</span><span class="sxs-lookup"><span data-stu-id="abfba-162">To enable auditing for the documents and items that are subject to this policy, choose **Enable Auditing**, and then specify the events you want to audit.</span></span>
    
    <span data-ttu-id="abfba-163">監査を有効にするのには</span><span class="sxs-lookup"><span data-stu-id="abfba-163">To enable auditing</span></span>
    
||||||<span data-ttu-id="abfba-164">1.\* \* \*</span><span class="sxs-lookup"><span data-stu-id="abfba-164">****1.****</span></span>|<span data-ttu-id="abfba-165">[ポリシーの編集] ページで、\* \* の **[** **監査** **\>** **の監査を有効にする**\* *、] を選択して、監査イベントのチェック ボックスの記録 \* for.* \* と</span><span class="sxs-lookup"><span data-stu-id="abfba-165">****On the Edit Policy page,** **under** **Auditing** **\>** **Enable auditing** **, and then select the check boxes next to the events you want to keep an audit trail for.****</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="abfba-166">**2。**</span><span class="sxs-lookup"><span data-stu-id="abfba-166">**2.**</span></span> <br/> |<span data-ttu-id="abfba-167">**ドキュメントにバーコードを挿入するのにはユーザーの入力を求める****選択****保存および印刷前にバーコードを挿入します。****.**</span><span class="sxs-lookup"><span data-stu-id="abfba-167">**To prompt users to insert these barcodes into documents,** **choose** **Prompt users to insert a barcode before saving or printing** **.**</span></span> <br/> |
||||||<span data-ttu-id="abfba-168">**3。**</span><span class="sxs-lookup"><span data-stu-id="abfba-168">**3.**</span></span> <br/> |<span data-ttu-id="abfba-169">**選択****OK** * * 監査機能をポリシーに適用します。</span><span class="sxs-lookup"><span data-stu-id="abfba-169">**Choose** **OK** ** to apply the auditing feature to the policy.</span></span> ** <br/> |
|||||||<span data-ttu-id="abfba-p111">監査ポリシー機能を作成し、ドキュメントとリスト アイテムをタスク リスト、案件リスト、ディスカッション グループ、および予定表のように、監査記録の分析を使用します。このポリシー機能は、コンテンツを表示、編集、または削除する場合など、イベントを記録する監査ログを提供します。</span><span class="sxs-lookup"><span data-stu-id="abfba-p111">The Auditing Policy feature enables organizations to create and analyze audit trails for documents and to list items such as task lists, issues lists, discussion groups, and calendars. This policy feature provides an audit log that records events, such as when content is viewed, edited, or deleted.</span></span>  <br/> |
|||||||<span data-ttu-id="abfba-p112">情報管理ポリシーの一部としての監査を有効にすると、管理者は、[ポリシー利用状況のレポートを Microsoft Excel では、現在の利用状況が要約する監査データを表示できます。管理者は、組織内の情報の使用方法を決定するのには、これらのレポートを使用できます。これらのレポートには、組織または潜在的な懸念事項を調査することを確認し、規制へのコンプライアンスを文書化することができます。</span><span class="sxs-lookup"><span data-stu-id="abfba-p112">When auditing is enabled as part of an information management policy, administrators can view the audit data in policy usage reports that are based in Microsoft Excel and that summarize current usage. Administrators can use these reports to determine how information is being used within the organization. These reports can also help organizations to verify and document their regulatory compliance or to investigate potential concerns.</span></span>  <br/> |
|||||||<span data-ttu-id="abfba-175">監査ログには、イベント名、イベントの発生日時、アクションを実行したユーザーのシステム名などの情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="abfba-175">The audit log records the following information: event name, date and time of the event, and system name of the user who performed the action.</span></span>  <br/> |
   
1. <span data-ttu-id="abfba-p113">バーコードをポリシーの一部として有効にすると、ドキュメントのプロパティを追加、バーコードを適用する文書のヘッダー領域に表示されます。ラベルのようなバーコードも手動で削除ドキュメントから。バーコードを印刷または、アイテムを保存するときは、ユーザーが求められますかどうか、またはバーコードを手動で挿入する場合は、2010 年に、[**挿入**] タブを使用して Office リリース プログラムを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="abfba-p113">When barcodes are enabled as part of a policy, they are added to document properties and displayed in the header area of the document to which the barcode is applied. Like labels, barcodes can also be manually removed from a document. You can specify whether users should be prompted to include the barcode when printing or saving an item or if the barcode should be inserted manually using the **Insert** tab in 2010 Office release programs.</span></span> 
    
    <span data-ttu-id="abfba-179">バーコードを有効にするには</span><span class="sxs-lookup"><span data-stu-id="abfba-179">To enable barcodes</span></span>
    
||||||<span data-ttu-id="abfba-180">1.\* \* \*</span><span class="sxs-lookup"><span data-stu-id="abfba-180">****1.****</span></span>|<span data-ttu-id="abfba-181">**ポリシーの編集] ページの [**バーコード**] の下に\> **[バーコード**を有効にします。**</span><span class="sxs-lookup"><span data-stu-id="abfba-181">**On the Edit Policy page, under **Barcodes**\> **Enable Barcodes**.**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="abfba-182">**2。**</span><span class="sxs-lookup"><span data-stu-id="abfba-182">**2.**</span></span> <br/> |<span data-ttu-id="abfba-183">ドキュメントにバーコードを挿入するユーザーを表示するには、**保存および印刷前にバーコードを挿入する**を選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-183">To prompt users to insert these barcodes into documents, choose **Prompt users to insert a barcode before saving or printing**.</span></span>  <br/> |
||||||<span data-ttu-id="abfba-184">**3。**</span><span class="sxs-lookup"><span data-stu-id="abfba-184">**3.**</span></span> <br/> |<span data-ttu-id="abfba-185">バーコード機能をポリシーに適用するのには **[ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-185">Choose **OK** to apply the barcode feature to the policy.</span></span>  <br/> |
|||||||
 <span data-ttu-id="abfba-p114">バーコードのポリシーでは、コード 39 標準のバーコードを生成します。それぞれのバーコード イメージには、バーコード値を表す記号の下にテキストが含まれています。これにより、バーコードのデータがハードウェアのスキャンが使用できないときでも使用できます。ユーザーは、サイト上のアイテムを検索する検索ボックスにバーコード番号を手動で入力できます。</span><span class="sxs-lookup"><span data-stu-id="abfba-p114">The barcode policy generates Code 39 standard barcodes. Each barcode image includes text below the barcode symbol that represents the barcode value. This enables the barcode data to be used even when scanning hardware is not available. Users can manually type the barcode number into the search box to locate the item on a site.</span></span>  <br/> |
   
1. <span data-ttu-id="abfba-190">このポリシーが適用されているドキュメントにラベルがあることを必要とするには、は、**ラベルを有効にする**を選択し、ラベルに使用する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="abfba-190">To require that documents that are subject to this policy have labels, choose **Enable Labels**, and then specify the settings that you want for the labels.</span></span>
    
    <span data-ttu-id="abfba-191">ラベルを有効にするには</span><span class="sxs-lookup"><span data-stu-id="abfba-191">To enable labels</span></span>
    
||||||<span data-ttu-id="abfba-192">**1。**</span><span class="sxs-lookup"><span data-stu-id="abfba-192">**1.**</span></span>|<span data-ttu-id="abfba-193">* * ドキュメントにラベルを追加するユーザーを必要とするには、**保存および印刷前にラベルを挿入する**を選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-193">**To require users to add a label to a document, choose **Prompt users to insert a label before saving or printing**.</span></span>  <br/> <span data-ttu-id="abfba-194">> [!NOTE]> ラベルを省略できる、する場合はこのチェック ボックスをオンできません。</span><span class="sxs-lookup"><span data-stu-id="abfba-194">> [!NOTE]>  If you want labels to be optional, do not select this check box.</span></span>        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="abfba-195">2.</span><span class="sxs-lookup"><span data-stu-id="abfba-195">2.</span></span>  <br/> |<span data-ttu-id="abfba-196">ラベルをロックし、挿入された後は変更できませんので、**ラベルを追加した後に変更をできないようにする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-196">To lock a label so that it cannot be changed after it has been inserted, choose **Prevent changes to labels after they are added**.</span></span>  <br/>  <span data-ttu-id="abfba-p115">この設定では、ラベルのテキストが Word、Excel、PowerPoint などのクライアント アプリケーション内の項目にラベルが挿入された後に更新できなくなります。このドキュメントまたはアイテムのプロパティが更新されたときに更新するラベルを設定する場合はこのチェック ボックスをオンしません。</span><span class="sxs-lookup"><span data-stu-id="abfba-p115">This setting prevents the label text from updating once the label has been inserted into an item within a client application such as Word, Excel, or PowerPoint. If you want the label to be updated when the properties for this document or item are updated, do not select this check box.  </span></span><br/> |
||||||<span data-ttu-id="abfba-199">3.</span><span class="sxs-lookup"><span data-stu-id="abfba-199">3.</span></span>  <br/> |<span data-ttu-id="abfba-p116">ラベルの形式] ボックスでは、必要な表示するラベルのテキストを入力します。ラベルには、それぞれ最大 255 文字を入力でき、最大 10 個の列参照を含めることができます。ラベルの書式を作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="abfba-p116">In the Label format box, enter the text for the label as you want it to be displayed. Labels can contain up to 10 column references, each of which can be up to 255 characters long. To create the format for your label, do the following:</span></span>  <br/> <span data-ttu-id="abfba-p117">ラベルに表示される順序で追加する列の名前を入力します。列名を中かっこで囲みます ({}) [ポリシーの編集] ページで、この例のように、です。</span><span class="sxs-lookup"><span data-stu-id="abfba-p117">Type the names of the columns that you want to include in the label in the order in which you want them to appear. Enclose the column names in curly brackets ({}), as shown in the example on the Edit Policy page.</span></span>  <br/> <span data-ttu-id="abfba-205">[ポリシーの編集] ページで、この例のように、角かっこの外側の列を識別する語句を入力します。</span><span class="sxs-lookup"><span data-stu-id="abfba-205">Type words to identify the columns outside the brackets, as shown in the example on the Edit Policy page.</span></span>  <br/> |
||||||<span data-ttu-id="abfba-206">4.</span><span class="sxs-lookup"><span data-stu-id="abfba-206">4.</span></span>  <br/> |<span data-ttu-id="abfba-207">改行を追加するのには、改行を表示する**\n**を入力します。</span><span class="sxs-lookup"><span data-stu-id="abfba-207">To add a line break, enter **\n** where you want the line break to appear.</span></span>  <br/> |
||||||<span data-ttu-id="abfba-208">5.</span><span class="sxs-lookup"><span data-stu-id="abfba-208">5.</span></span>  <br/> |<span data-ttu-id="abfba-209">フォントのサイズとし、左、中央、またはドキュメント内の右にラベルが配置されるかどうかを指定するスタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-209">Select the font size and style that you want, and specify whether you want the label positioned left, center, or right within the document.</span></span>  <br/>  <span data-ttu-id="abfba-p118">フォントおよびユーザーのコンピューターで利用可能なスタイルを選択します。フォントのサイズは、ラベルに表示されるテキストの量に影響します。</span><span class="sxs-lookup"><span data-stu-id="abfba-p118">Select a font and style that are available on the users' computers. The size of the font affects how much text can be displayed on the label.</span></span>  <br/> |
||||||<span data-ttu-id="abfba-212">6.</span><span class="sxs-lookup"><span data-stu-id="abfba-212">6.</span></span>  <br/> |<span data-ttu-id="abfba-p119">ラベルの幅と高さを入力します。ラベルの高さの 25 インチから 20 インチの場合、範囲は、25 インチから 20 インチのラベルの幅が範囲は.ラベルのテキストは、ラベル イメージの中心は常に垂直方向にです。</span><span class="sxs-lookup"><span data-stu-id="abfba-p119">Enter the height and width of the label. Label height can range from .25 inches to 20 inches, and label width can range from .25 inches to 20 inches. Label text is always vertically centered within the label image.</span></span>  <br/> |
||||||<span data-ttu-id="abfba-216">7.</span><span class="sxs-lookup"><span data-stu-id="abfba-216">7.</span></span>  <br/> |<span data-ttu-id="abfba-217">ラベルの内容をプレビューするのには**更新**を選択してください。</span><span class="sxs-lookup"><span data-stu-id="abfba-217">Choose **Refresh** to preview the label content.</span></span>  <br/> |
   
1. <span data-ttu-id="abfba-218">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abfba-218">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a><span data-ttu-id="abfba-219">リスト、ライブラリ、またはフォルダーに対するポリシーを作成する (場所に応じた保持ポリシー)</span><span class="sxs-lookup"><span data-stu-id="abfba-219">Create a policy for a list, library or folder (location-based retention policy)</span></span>
<span data-ttu-id="abfba-220"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="abfba-220"></span></span>

<span data-ttu-id="abfba-p120">特定のリスト、ライブラリまたはフォルダーにのみ適用される保持ポリシーを定義することができます。場合はこの方法で保存ポリシーを作成する他のリスト、ライブラリ、フォルダー、または、サイトでこのポリシーを再利用することはできませんし、場所に基づいてポリシーをサイト コレクション ポリシーを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="abfba-p120">You can define a retention policy that applies only to a specific list, library or folder. However, if you create a retention policy this way, you cannot reuse this policy on other lists, libraries, folders or sites, and you cannot apply a site collection policy to a location based policy.</span></span>
  
<span data-ttu-id="abfba-p121">すべての種類の 1 つの場所でコンテンツを 1 つの保持ポリシーを適用する場合は、場所ベースの保存を使用するが可能性があります。他のほとんどの場合では、すべてのコンテンツ タイプの保持ポリシーが指定されていることを確認するができます。</span><span class="sxs-lookup"><span data-stu-id="abfba-p121">If you want to apply a single retention policy to all types of content in a single location, you will most likely want to use location-based retention. In most other cases, you will want to verify that a retention policy is specified for all content types.</span></span>
  
 <span data-ttu-id="abfba-225">各サブフォルダーは、継承を停止し、子レベルで、新しい保持ポリシーを定義する場合を除き、親のリテンション ・ ポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="abfba-225">Each subfolder inherits the retention policy of its parent, unless you choose to break inheritance and define a new retention policy at the child level.</span></span> 
  
<span data-ttu-id="abfba-226">リストまたはライブラリに保存期間以外の情報管理ポリシーを定義する場合は、そのリストまたはライブラリに関連付けられている各リスト コンテンツ タイプに対する情報管理ポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abfba-226">If you want to define an information management policy other than retention to a list or library, you need to define an information management policy for each individual list content type associated with that list or library.</span></span>
  
 <span data-ttu-id="abfba-p122">場合は任意の時点でリストまたはライブラリの場所ベースのポリシーをコンテンツ タイプを切り替えるには、場所ベースのポリシーとリテンション ・ ポリシーのみが使用します。他の管理ポリシー (監査、バーコード、およびバーコード) は、関連付けられたコンテンツ タイプから継承されます。</span><span class="sxs-lookup"><span data-stu-id="abfba-p122">If at any point you decide to switch from content type to location-based policies for a list or library, only the retention policy will be used as the location-based policy. All other management policies (audits, barcodes, and barcodes) will be inherited from the associated content types.</span></span> 
  
 <span data-ttu-id="abfba-p123">ベースの場所のポリシーを無効にサイト コレクションのライブラリおよびフォルダー ベースの保存の機能を非アクティブ化します。これにより、サイト コレクションの管理者リスト管理者の場所に基づくポリシーによって、そのコンテンツ タイプのポリシーがオーバーライドされないようにします。</span><span class="sxs-lookup"><span data-stu-id="abfba-p123">Location based policies can be disabled for a site collection by deactivating the Library and Folder Based Retention feature. This enables site collection administrators to ensure that their content type policies are not overridden by a list administrator's location based policies.</span></span> 
  
<span data-ttu-id="abfba-231">少なくともリストまたはライブラリの情報管理ポリシーの設定を変更するのにはリストの管理権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="abfba-231">You need at least the Manage Lists permission to change the information management policy settings for a list or library.</span></span>
  
1. <span data-ttu-id="abfba-232">情報管理ポリシーを指定するリストまたはライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="abfba-232">Navigate to the list or library for which you want to specify an information management policy.</span></span> 
    
2. <span data-ttu-id="abfba-233">**ライブラリ**または**リスト**] タブを選択して、リボンの\>**ライブラリの設定**] または [**リストの設定**。</span><span class="sxs-lookup"><span data-stu-id="abfba-233">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="abfba-234">SharePoint Online では、[**設定**] をクリックしてで [**リストの設定**] または [**ライブラリの設定**。</span><span class="sxs-lookup"><span data-stu-id="abfba-234">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="abfba-235">[**権限と管理**\> **情報管理ポリシーの設定**。</span><span class="sxs-lookup"><span data-stu-id="abfba-235">Under **Permissions and Management**\> **Information management policy settings**.</span></span>
  
![ドキュメント ライブラリの設定ページ上の情報管理ポリシーのリンク](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="abfba-237">情報管理ポリシーの設定] ページで、[ライブラリとフォルダーをリストまたはライブラリのアイテム保持ポリシーのソースが設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="abfba-237">On the Information Management Policy Settings page, make sure that the source of retention for the list or library is set to Library and Folders.</span></span> 
  
<span data-ttu-id="abfba-p124">**コンテンツ タイプ**は、ソースとして表示されている場合**ソースの変更**] をクリックし、**ライブラリとフォルダー**] をクリックします。コンテンツ タイプの保持ポリシーを無視することを確認するメッセージが表示されたら。**[Ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-p124">If **Content Type** appears as the source, click **Change Source**, and then click **Library and Folders**. You are alerted that content type retention policies will be ignored. Choose **OK**.</span></span> 
    
5. <span data-ttu-id="abfba-241">**ライブラリ ベースの保持スケジュール**では、[ポリシーの編集] ページで、作成するポリシーの簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="abfba-241">On the Edit Policy page, under **Library Based Retention Schedule**, enter a brief description for the policy you are creating.</span></span> 
    
6. <span data-ttu-id="abfba-242">**追加保持ステージ...** 」を選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-242">Choose **Add a retention stage…**</span></span>
    
     <span data-ttu-id="abfba-243">[レコード] で、設定できることのレコード数] オプションを定義する別の保存段階を選択することによってレコードの別の保存ポリシーを定義するのには注意してください。</span><span class="sxs-lookup"><span data-stu-id="abfba-243">Note that under Records, you can choose to define different retention policies for records by selecting the Define different retention stages for records option.</span></span> 
    
7. <span data-ttu-id="abfba-p125">ステージのプロパティ ダイアログ ボックスで、ドキュメントまたはアイテムが期限切れに設定すると指定する保持期間オプションを選択します。次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="abfba-p125">In the Stage properties dialog, select a retention period option to specify when documents or items are set to expire. Do one of the following:</span></span>
    
  - <span data-ttu-id="abfba-246">**イベント**] の下の日付プロパティに基づいて有効期限の日付を設定するのには\>**アイテムの日付プロパティに基づくこの段階では**、ドキュメントまたはアイテムのアクション (たとえば、作成または変更) を選択し、このアクション (後の時間の単位たとえば、日数、月数、または年の数)、アイテムを期限切れにする場合します。</span><span class="sxs-lookup"><span data-stu-id="abfba-246">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span> 
    
  - <span data-ttu-id="abfba-247">カスタム保持期間の数式を使用して、有効期限を設定するのには、**このサーバーにインストールされているカスタム保持期間の数式で設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-247">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="abfba-248">このオプションは、使用できるは、管理者がユーザー設定の数式が設定されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="abfba-248">This option is only available if a custom formula has been set up by your administrator.</span></span> 
  
  - <span data-ttu-id="abfba-p126">**アクション**] の下には、ドキュメントまたはアイテムの有効期限が切れたときに発生する内容を指定します。ドキュメントまたはアイテムを削除するなど) 場合に発生する特定のアクションを有効にするには、リストからアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-p126">Under **Action**, specify what you want to happen when the document or item expires. To enable a specific action to happen to the document or item (such as deletion), select an action from the list.</span></span> 
    
8. <span data-ttu-id="abfba-p127">**ワークフローを開始する**] オプションでは、リスト、ライブラリ、または既に関連付けられているワークフローをコンテンツ タイプのポリシーを定義している場合にのみがあります。あるから選択するワークフローを選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-p127">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it. You will then be given a choice of workflows to choose from.</span></span> 
    
9. <span data-ttu-id="abfba-253">**定期的なアイテム**、[ **...] この段階の操作を繰り返す**」を選択します再発を操作する頻度を入力してください。</span><span class="sxs-lookup"><span data-stu-id="abfba-253">Under **Recurrence**, choose **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="abfba-p128">このオプションは、選択したアクションを繰り返すことができる場合のみです。など**を完全に削除**アクションの繰り返しを設定できません。</span><span class="sxs-lookup"><span data-stu-id="abfba-p128">This option is only available if the action you selected can be repeated. For example, you cannot set recurrence for the action **Permanently Delete**.</span></span> 
  
10. <span data-ttu-id="abfba-256">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abfba-256">Choose **OK**.</span></span>
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a><span data-ttu-id="abfba-257">サイト コレクション ポリシーをコンテンツ タイプに適用します。</span><span class="sxs-lookup"><span data-stu-id="abfba-257">Apply a site collection policy to a content type</span></span>
<span data-ttu-id="abfba-258"><a name="__apply_a_site"> </a></span><span class="sxs-lookup"><span data-stu-id="abfba-258"></span></span>

<span data-ttu-id="abfba-p129">情報管理ポリシーは、サイト コレクション ポリシーとして、サイトに既に作成されている場合、は、コンテンツ タイプにポリシーのいずれかを適用できます。これを行うには、同じ親コンテンツ タイプを共有していないサイト コレクション内の複数のコンテンツ タイプに同じポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="abfba-p129">If information management policies have already been created for your site as site collection policies, you can apply one of the policies to a content type. By doing this, you can apply the same policy to multiple content types in a site collection that do not share the same parent content type.</span></span>
  
 <span data-ttu-id="abfba-p130">複数のサイト コレクション情報管理ポリシーの場合は、サイト コレクション内の複数のコンテンツ タイプにポリシーを適用して構成の管理されたメタデータ サービスがある場合、発行するコンテンツ タイプの発行を使用することができます。詳細については[サイト コレクション間でのコンテンツ タイプにポリシーを適用](create-info-mgmt-policies.md#__apply_a_policy)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abfba-p130">If you want to apply policies to multiple content types in a site collection, and you have a Managed Metadata Service configured, you can use Content Type Publishing to publish out information management polices to multiple site collections. See the section [Apply a policy to content types across site collections](create-info-mgmt-policies.md#__apply_a_policy) for more information.</span></span> 
  
1. <span data-ttu-id="abfba-263">一覧またはポリシーを適用するコンテンツ タイプが含まれているライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="abfba-263">Navigate to the list or library that contains the content type to which you want to apply a policy.</span></span>
    
2. <span data-ttu-id="abfba-264">**ライブラリ**または**リスト**] タブを選択して、リボンの\>**ライブラリの設定**] または [**リストの設定**。</span><span class="sxs-lookup"><span data-stu-id="abfba-264">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="abfba-265">SharePoint Online では、[**設定**] をクリックしてで [**リストの設定**] または [**ライブラリの設定**。</span><span class="sxs-lookup"><span data-stu-id="abfba-265">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="abfba-266">[**権限と管理** \> **情報管理ポリシーの設定**。</span><span class="sxs-lookup"><span data-stu-id="abfba-266">Under **Permissions and Management** \> **Information management policy settings**.</span></span>
  
![ドキュメント ライブラリの設定ページ上の情報管理ポリシーのリンク](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="abfba-268">ポリシー ソース設定されている**コンテンツ タイプ**、および**コンテンツ タイプのポリシー**の選択] の [コンテンツ タイプにポリシーを適用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="abfba-268">Verify that the policy source is set to **Content Types**, and under **Content Type Policies** select the content type you want to apply the policy to.</span></span> 
    
5. <span data-ttu-id="abfba-269">**ポリシーの指定**] の下\>、**サイト コレクション ポリシーを使用して**、リストから、適用するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-269">Under **Specify the Policy** \> **Use a site collection policy**, and then select the policy that you want to apply from the list.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="abfba-270">**サイト コレクション ポリシーを使用する**オプションが使用できない場合は、サイト コレクション ポリシーが定義されていないサイト コレクションのです。</span><span class="sxs-lookup"><span data-stu-id="abfba-270">If the **Use a site collection policy** option is not available, no site collection policies have been defined for the site collection.</span></span> 
  
6. <span data-ttu-id="abfba-271">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abfba-271">Choose **OK**.</span></span>
    
     <span data-ttu-id="abfba-p131">リストまたはライブラリを使用して複数のコンテンツ タイプの管理をサポートする場合は、[**コンテンツ タイプ]** ことができます情報管理ポリシーを指定するコンテンツ タイプ。これを実行する前の手順 5。</span><span class="sxs-lookup"><span data-stu-id="abfba-p131">If the list or library you are working with supports the management of multiple content types, under **Content Types** you can choose the content type for which you want to specify an information management policy. This will take you directly to Step 5 above.</span></span> 
    
## <a name="apply-a-policy-across-site-collections"></a><span data-ttu-id="abfba-274">サイト コレクション間でポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="abfba-274">Apply a policy across site collections</span></span>
<span data-ttu-id="abfba-275"><a name="__toc260646789"> </a></span><span class="sxs-lookup"><span data-stu-id="abfba-275"></span></span>

<span data-ttu-id="abfba-p132">サイト コレクション間でコンテンツ タイプを共有するには、管理されたメタデータ サービス アプリケーションを使用して発行するコンテンツ タイプを設定します。コンテンツ タイプの発行では、管理コンテンツとメタデータの一貫性のある、サイト間で、コンテンツ タイプを作成および更新を一元的に更新を複数のサブスクリプションのサイト コレクションまたは Web アプリケーションに公開できます。</span><span class="sxs-lookup"><span data-stu-id="abfba-p132">Share content types across site collections by using a Managed Metadata service application to set up content type publishing. Content type publishing helps you manage content and metadata consistently across your sites because content types can be created and updated centrally, and updates can be published out to multiple subscribing site collections or Web applications.</span></span>
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a><span data-ttu-id="abfba-278">サイト コレクション全体で使用する既存のポリシーからテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="abfba-278">Create a template from an existing policy to use across site collections</span></span>
<span data-ttu-id="abfba-279"><a name="__toc262125409"> </a></span><span class="sxs-lookup"><span data-stu-id="abfba-279"></span></span>

<span data-ttu-id="abfba-p133">情報管理ポリシーを定義してから複数のサイト コレクション間で必要に応じて、使用するテンプレートを作成できます。情報ポリシーのバックアップを保持する、またはサイト コレクション全体で 1 つのポリシーを適用するコンテンツ タイプの発行に使用する代替手段として使用することも、このメソッドを使用できます。別のサイト コレクションに 1 つのサイト コレクションからポリシーをエクスポートおよびインポートすることや保存されている場所には、テンプレートまたはポリシーのバックアップを作成します。</span><span class="sxs-lookup"><span data-stu-id="abfba-p133">You can define an information management policy and then create a template from it to use as needed across multiple site collections. This method can be used if you want to have a backup of your information policies, or it can also be used as an alternate method to using content type publishing for applying one policy across site collections. You create a template or backup of the policy by exporting the policy from one site collection and then importing it to a saved location or to another site collection.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="abfba-p134">ポリシー テンプレートのセットを作成する方法として機能をエクスポート/インポートを使用している場合は、ポリシーの .xml ファイルに一意の識別子が存在することに留意してください。このため、インポートできませんそのポリシーのサイトに 2 回以上この一意の識別子を変更することがなく。</span><span class="sxs-lookup"><span data-stu-id="abfba-p134">If you using the export/import feature as a way to make a set of policy templates, keep in mind that a unique identifier exists in the policy .xml file. Because of this, you cannot import that policy into a site more than once without changing this unique identifier.</span></span> 
  
### <a name="export-a-policy"></a><span data-ttu-id="abfba-285">ポリシーをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="abfba-285">Export a policy</span></span>
<span data-ttu-id="abfba-286"><a name="__toc260646790"> </a></span><span class="sxs-lookup"><span data-stu-id="abfba-286"></span></span>

1. <span data-ttu-id="abfba-287">サイト コレクションのホーム ページの**設定**を選択します![、サイトの設定が行われた小さな設定装置。](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **サイトの設定**。</span><span class="sxs-lookup"><span data-stu-id="abfba-287">On the site collection home page, choose **Settings**![Small Settings gear that took the place of Site Settings.](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="abfba-288">SharePoint グループに接続されたサイトの**設定**] をクリックして**サイトの内容**を**サイトの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abfba-288">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="abfba-289">サイトの設定ページで、[**サイト コレクションの管理** \> **コンテンツ タイプ ポリシーのテンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="abfba-289">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![[サイトの設定] ページの [コンテンツ タイプ ポリシーのテンプレート] リンク](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="abfba-291">エクスポートするポリシーを選択する\>の一番下までスクロール\>**をエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="abfba-291">Choose the policy you want to export \> scroll to the bottom \> **Export**.</span></span>
    
4. <span data-ttu-id="abfba-p135">保存、ファイルを開くまたは**保存**を選択して、ファイルを保存する場所を選択し、プロンプトにします。ポリシーをインポートするサイト コレクションに使用可能な場所を選択することを確認します。</span><span class="sxs-lookup"><span data-stu-id="abfba-p135">At the prompt to save or open the file, choose **Save**, and then select a location to save the file to. Be sure to select a location that is available to the site collections that are importing the policy.</span></span>
    
5. <span data-ttu-id="abfba-294">[ダウンロードの完了ダイアログ ボックスが表示されたら、**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="abfba-294">When the Download Complete dialog is displayed, choose **Close**.</span></span>
    
### <a name="import-a-policy-to-a-different-site-collection"></a><span data-ttu-id="abfba-295">別のサイト コレクションにポリシーをインポートします。</span><span class="sxs-lookup"><span data-stu-id="abfba-295">Import a policy to a different site collection</span></span>
<span data-ttu-id="abfba-296"><a name="__toc260646791"> </a></span><span class="sxs-lookup"><span data-stu-id="abfba-296"></span></span>

<span data-ttu-id="abfba-p136">情報管理ポリシーのインポートを使用すると、任意の特定のサイト コレクション内のサイトまたはリスト レベルで複数のコンテンツ タイプに適用します。この方法の利点は、2 つあります: 再定義し、それぞれのコンテンツ タイプにポリシーを適用する必要はありませんし、1 か所だけで、ポリシーを変更することでポリシーの変更をより簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="abfba-p136">Importing an information management policy enables you to apply it to multiple content types at the site or list level within any given site collection. The benefits of doing this are twofold: you don't have to re-define and apply the policy on each content type, and you can more easily manage policy modifications by making changes to the policy in just one place.</span></span>
  
1. <span data-ttu-id="abfba-299">ポリシーを適用するサイト コレクションのホーム ページの**設定**を選択します![、サイトの設定が行われた小さな設定装置。](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **サイトの設定**。</span><span class="sxs-lookup"><span data-stu-id="abfba-299">On the home page of the site collection to which you want to apply the policy, choose **Settings**![Small Settings gear that took the place of Site Settings.](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="abfba-300">SharePoint グループに接続されたサイトの**設定**] をクリックして**サイトの内容**を**サイトの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abfba-300">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="abfba-301">サイトの設定ページで、[**サイト コレクションの管理** \> **コンテンツ タイプ ポリシーのテンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="abfba-301">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span>
    
3. <span data-ttu-id="abfba-302">[ポリシー] ページで、 \> **インポート**\>ポリシーの XML ファイルを検索する**参照**をします。</span><span class="sxs-lookup"><span data-stu-id="abfba-302">On the Policies page \> **Import** \> **Browse** to find the XML file for the policy.</span></span> 
    
4. <span data-ttu-id="abfba-303">ポリシーが保存されている XML ファイルを選択して\>**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="abfba-303">Select the XML file in which the policy has been saved \> **Open**.</span></span> 
    
5. <span data-ttu-id="abfba-304">[サイト コレクション ポリシーのインポート] ページで\>のサイト コレクションにポリシーを追加するのには**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="abfba-304">On the Import a Site Collection Policy page \> **Import** to add the policy to the site collection.</span></span> 
    
<span data-ttu-id="abfba-305">インポートしたポリシーは、サイトまたはリスト レベルで 1 つまたは複数のコンテンツ タイプを今すぐ適用できます。</span><span class="sxs-lookup"><span data-stu-id="abfba-305">Your imported policy can now be applied to one or many content types at the site or list level.</span></span> 
  
[<span data-ttu-id="abfba-306">情報管理ポリシーは、組織にどのような人か、コンテンツを監査し、バーコードを追加するのには、コンテンツの保存期間の制御、またはドキュメントにラベルを有効にします。ポリシーは、法的および政府の規制や社内の業務プロセスへの準拠を強制できます。ドキュメントを追跡する方法を制御する管理者は、ポリシーを設定でき、ドキュメントの保存期間です。情報管理ポリシーのことを作成するには広範かつからサイト階層で、3 つの異なる場所で、狭い: サイト コレクション内の複数のコンテンツ タイプで使用するポリシーを作成します。サイト コンテンツ タイプのポリシーを作成します。リストまたはライブラリのポリシーを作成します。詳細については、情報管理ポリシーの概要を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abfba-306">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents. A policy can help enforce compliance with legal and governmental regulations or internal business processes. As an administrator, you can set up a policy to control how to track documents and how long to retain documents.You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:Create a policy to use on multiple content types within a site collection.Create a policy for a site content type.Create a policy for a list or library.For more information, see Introduction to information management policies.</span></span>](create-info-mgmt-policies.md#__top)
  

