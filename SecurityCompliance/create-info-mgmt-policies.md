---
title: 情報管理ポリシーを作成して適用する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/16/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
ms.collection:
- M365-security-compliance
description: 情報管理ポリシーを使用すると、コンテンツの保持期間を制御したり、コンテンツについてユーザーの作業を監査したり、バーコードやラベルをドキュメントに追加したりできます。 ポリシーを使用すると、法律上および行政上の規制や内部のビジネスプロセスに準拠することができます。 管理者は、ドキュメントの追跡方法やドキュメントを保持する期間を制御するポリシーをセットアップできます。
ms.openlocfilehash: 1d17dd8cadb721478831ab8fe77413c08f959f29
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862569"
---
# <a name="create-and-apply-information-management-policies"></a><span data-ttu-id="14977-105">情報管理ポリシーを作成して適用する</span><span class="sxs-lookup"><span data-stu-id="14977-105">Create and apply information management policies</span></span>

<span data-ttu-id="14977-106">情報管理ポリシーを使用すると、コンテンツの保持期間を制御したり、コンテンツについてユーザーの作業を監査したり、バーコードやラベルをドキュメントに追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="14977-106">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="14977-107">ポリシーを使用すると、法律上および行政上の規制や内部のビジネスプロセスに準拠することができます。</span><span class="sxs-lookup"><span data-stu-id="14977-107">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="14977-108">管理者は、ドキュメントの追跡方法やドキュメントを保持する期間を制御するポリシーをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="14977-108">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>
  
<span data-ttu-id="14977-109">情報管理ポリシーは、サイト階層内の3つの異なる場所 (最も広いものから最も狭いものまで) に作成できます。</span><span class="sxs-lookup"><span data-stu-id="14977-109">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
  
- <span data-ttu-id="14977-110">サイトコレクション内の複数のコンテンツタイプで使用するポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="14977-110">Create a policy to use on multiple content types within a site collection.</span></span>
    
- <span data-ttu-id="14977-111">サイトコンテンツタイプのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="14977-111">Create a policy for a site content type.</span></span>
    
- <span data-ttu-id="14977-112">リストまたはライブラリのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="14977-112">Create a policy for a list or library.</span></span>
    
<span data-ttu-id="14977-113">詳細については、「[情報管理ポリシーの概要](intro-to-info-mgmt-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14977-113">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a><span data-ttu-id="14977-114">サイトコレクション内の複数のコンテンツタイプのポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="14977-114">Create a policy for multiple content types within a site collection</span></span>
<span data-ttu-id="14977-115"><a name="__toc261001590"> </a></span><span class="sxs-lookup"><span data-stu-id="14977-115"></span></span>

<span data-ttu-id="14977-116">サイトコレクション内の特定の種類のすべてのドキュメントに情報ポリシーが適用されるようにするには、サイトコレクションレベルでポリシーを作成してから、そのポリシーをコンテンツタイプに適用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="14977-116">To ensure that an information policy is applied to all documents of a certain type within a site collection, consider creating the policy at the site collection level and then later apply the policy to content types.</span></span> <span data-ttu-id="14977-117">これらは、サイトコレクションポリシーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="14977-117">These are referred to as site collection policies.</span></span> 
  
1. <span data-ttu-id="14977-118">サイトコレクションのホームページ\> **設定**![SharePoint 2016 設定] ボタン (タイトルバー)。](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="14977-118">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="14977-119">\> **[サイトの設定]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="14977-119">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="14977-120">SharePoint グループに接続されたサイトで、[**設定**] をクリックし、[**サイトコンテンツ**]、[**サイトの設定**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="14977-120">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="14977-121">[サイトの設定] ページの [**サイトコレクションの管理** \> **コンテンツタイプポリシーテンプレート**] を指定します。</span><span class="sxs-lookup"><span data-stu-id="14977-121">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![[サイトの設定] ページの [コンテンツ タイプ ポリシーのテンプレート] リンク](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="14977-123">[ポリシー] ページ\>で、[**作成**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="14977-123">On the Policies page \> **Create**.</span></span> 
    
4. <span data-ttu-id="14977-124">ポリシーの名前と説明を入力し、ユーザーに対してポリシーがどのようなものかを説明する簡単なポリシーステートメントを記述します。</span><span class="sxs-lookup"><span data-stu-id="14977-124">Enter a name and description for the policy, and then write a brief policy statement that explains to users what the policy is for.</span></span>
    
5. <span data-ttu-id="14977-125">ポリシーに関連付ける機能をセットアップする方法については、「サイトコンテンツタイプのポリシーの作成」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14977-125">See the next section on creating policies for a site content type to learn how to set up the features you want to associate with the policy.</span></span> 
    
6. <span data-ttu-id="14977-126">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-126">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-site-content-type"></a><span data-ttu-id="14977-127">サイトコンテンツタイプのポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="14977-127">Create a policy for a site content type</span></span>
<span data-ttu-id="14977-128"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="14977-128"></span></span>

<span data-ttu-id="14977-129">コンテンツタイプに情報管理ポリシーを追加すると、ポリシー機能と複数のリストまたはライブラリとの関連付けが容易になります。</span><span class="sxs-lookup"><span data-stu-id="14977-129">Adding an information management policy to a content type makes it easy to associate policy features with multiple lists or libraries.</span></span> <span data-ttu-id="14977-130">既存の情報管理ポリシーをコンテンツタイプに追加するか、個別のコンテンツタイプに固有の一意のポリシーを作成するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="14977-130">You can choose to add an existing information management policy to a content type or create a unique policy specific to an individual content type.</span></span>
  
 <span data-ttu-id="14977-131">リストに固有のコンテンツタイプに情報管理ポリシーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="14977-131">You can also add an information management policy to a content type that is specific to lists.</span></span> <span data-ttu-id="14977-132">これには、コンテンツタイプを使用しているリスト内のアイテムにのみポリシーを適用する効果があります。</span><span class="sxs-lookup"><span data-stu-id="14977-132">This has the effect of applying the policy only to items in that list that are using the content type.</span></span> 
  
1. <span data-ttu-id="14977-133">サイトコレクションのホームページ\> **設定**![SharePoint 2016 設定] ボタン (タイトルバー)。](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="14977-133">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="14977-134">\> **[サイトの設定]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="14977-134">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="14977-135">SharePoint グループに接続されたサイトで、[**設定**] をクリックし、[**サイトコンテンツ**]、[**サイトの設定**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="14977-135">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="14977-136">[サイトの設定] ページの [ **Web デザイナーギャラリー** \> **サイトコンテンツタイプ**] の下。</span><span class="sxs-lookup"><span data-stu-id="14977-136">On the Site Settings page, under **Web Designer Galleries** \> **Site content types**.</span></span>
  
![[サイトの設定] ページの [サイト コンテンツ タイプ] リンク](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. <span data-ttu-id="14977-138">[サイトコンテンツタイプの設定] ページで、ポリシーを追加するコンテンツタイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-138">On the Site Content Type Settings page, select the content type that you want to add a policy to.</span></span>
    
4. <span data-ttu-id="14977-139">[サイトコンテンツタイプ] ページの [**設定** \> **情報管理ポリシーの設定**] で。</span><span class="sxs-lookup"><span data-stu-id="14977-139">On the Site Content Type page, under **Settings** \> **Information management policy settings**.</span></span>
    
5. <span data-ttu-id="14977-140">[ポリシーの編集] ページで、ポリシーの名前と説明を入力し、ユーザーに対してポリシーの内容を説明する簡単な説明を記入します。</span><span class="sxs-lookup"><span data-stu-id="14977-140">On the Edit Policy page, enter a name and description for the policy, and then write a brief description that explains to users what the policy is for.</span></span>
    
6. <span data-ttu-id="14977-141">次のセクションでは、情報管理ポリシーに追加する個々のポリシー機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-141">In the next sections, select the individual policy features that you want to add to your information management policy.</span></span> 
  
![コンテンツ ポリシーの種類](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. <span data-ttu-id="14977-143">このポリシーの対象となるドキュメントとアイテムの保持期間を指定するには、[**保持を有効**にする] を選択し、アイテムの有効期限が切れたときに実行する保持期間とアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="14977-143">To specify a retention period for documents and items that are subject to this policy, choose **Enable Retention**, and then specify the retention period and the actions that you want to occur when the items expire.</span></span>
    
    <span data-ttu-id="14977-144">保持期間を指定するには</span><span class="sxs-lookup"><span data-stu-id="14977-144">To specify a retention period</span></span>
    
||||||<span data-ttu-id="14977-145">**1.**</span><span class="sxs-lookup"><span data-stu-id="14977-145">**1.**</span></span>|<span data-ttu-id="14977-146">\* \* Choose \* \* レコードの保持ステージを追加する... \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="14977-146">\*\*Choose \*\*Add a retention stage for records…\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="14977-147">2.</span><span class="sxs-lookup"><span data-stu-id="14977-147">2.</span></span>  <br/> | <span data-ttu-id="14977-148">ドキュメントまたはアイテムを期限切れにするタイミングを指定するには、[保持期間] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-148">Select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="14977-149">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="14977-149">Do one of the following:</span></span>  <br/>  <span data-ttu-id="14977-150">日付プロパティに基づいて有効期限を設定するには、[**イベント** \> ] の [**このステージはアイテムの日付プロパティに基づいてい**ます] の下にある [ドキュメントまたはアイテム] アクション (たとえば、[作成日時] または [変更日時]) を選択し、このアクションの後の時間の増分を選択します (たとえば、アイテムを期限切れにする場合は、日数、月数、または年数を指定します。</span><span class="sxs-lookup"><span data-stu-id="14977-150">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span>  <br/>  <span data-ttu-id="14977-151">カスタム保持期間の計算式を使用して有効期限を決定するには、[**このサーバーにインストールされているカスタム保持期間の数式で設定**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-151">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span>  <br/> <span data-ttu-id="14977-152">> [!NOTE]> このオプションは、管理者によってカスタム式が設定されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="14977-152">> [!NOTE]>  This option is only available if a custom formula has been set up by your administrator.</span></span>           |
||||||<span data-ttu-id="14977-153">3.</span><span class="sxs-lookup"><span data-stu-id="14977-153">3.</span></span>  <br/> |<span data-ttu-id="14977-154">[**ワークフローの開始**] オプションは、既にワークフローが関連付けられているリスト、ライブラリ、またはコンテンツタイプのポリシーを定義している場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="14977-154">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="14977-155">その後、選択するワークフローが選択されます。</span><span class="sxs-lookup"><span data-stu-id="14977-155">You will then be given a choice of workflows to choose from.</span></span>  <br/> |
||||||<span data-ttu-id="14977-156">4.</span><span class="sxs-lookup"><span data-stu-id="14977-156">4.</span></span>  <br/> |<span data-ttu-id="14977-157">[**定期的なパターン**] セクションで、[**このステージのアクションを繰り返す...** ] を選択します。を選択し、アクションを実行する頻度を入力します。</span><span class="sxs-lookup"><span data-stu-id="14977-157">In the **Recurrence** section, select **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span>  <br/> <span data-ttu-id="14977-158">> [!NOTE]> このオプションは、選択したアクションを繰り返すことができる場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="14977-158">> [!NOTE]>  This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="14977-159">たとえば、アクションが**完全に削除**されると、定期的なアイテムを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="14977-159">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span>           |
||||||<span data-ttu-id="14977-160">5.</span><span class="sxs-lookup"><span data-stu-id="14977-160">5.</span></span>  <br/> |<span data-ttu-id="14977-161">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-161">Chose **OK**.</span></span>  <br/> |
   
1. <span data-ttu-id="14977-162">このポリシーの対象となるドキュメントとアイテムの監査を有効にするには、[**監査を有効**にする] を選択し、監査するイベントを指定します。</span><span class="sxs-lookup"><span data-stu-id="14977-162">To enable auditing for the documents and items that are subject to this policy, choose **Enable Auditing**, and then specify the events you want to audit.</span></span>
    
    <span data-ttu-id="14977-163">監査を有効にするには</span><span class="sxs-lookup"><span data-stu-id="14977-163">To enable auditing</span></span>
    
||||||<span data-ttu-id="14977-164">1. \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="14977-164">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="14977-165">[ポリシーの編集] ページで、\* \* [監査\*\*\*\* **\>** **を有効**にする **] の下**の [監査を有効にする] チェックボックスをオンにして、監査記録を保持するイベントの横にあるチェックボックスをオンにします。 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="14977-165">\*\*\*\*On the Edit Policy page,\*\* **under** **Auditing** **\>** **Enable auditing** \*\*, and then select the check boxes next to the events you want to keep an audit trail for.\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="14977-166">**2.**</span><span class="sxs-lookup"><span data-stu-id="14977-166">**2.**</span></span> <br/> |<span data-ttu-id="14977-167">**ユーザーにこれらのバーコードをドキュメントに挿入するように求めるには、\*\*\*\*[\*\*\*\*保存または印刷前にバーコードを挿入するかどうかを確認するメッセージをユーザーに表示する\*\*\*\*.**</span><span class="sxs-lookup"><span data-stu-id="14977-167">**To prompt users to insert these barcodes into documents,** **choose** **Prompt users to insert a barcode before saving or printing** **.**</span></span> <br/> |
||||||<span data-ttu-id="14977-168">**3.**</span><span class="sxs-lookup"><span data-stu-id="14977-168">**3.**</span></span> <br/> |<span data-ttu-id="14977-169">**[\*\*\*\*[OK] をクリック**して、ポリシーに監査機能を適用します。</span><span class="sxs-lookup"><span data-stu-id="14977-169">**Choose** **OK** \*\* to apply the auditing feature to the policy.</span></span> ** <br/> |
|||||||<span data-ttu-id="14977-170">監査ポリシー機能を使用すると、組織でドキュメントの監査証跡を作成して分析したり、タスクリスト、案件リスト、ディスカッショングループ、予定表などのリストアイテムを作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="14977-170">The Auditing Policy feature enables organizations to create and analyze audit trails for documents and to list items such as task lists, issues lists, discussion groups, and calendars.</span></span> <span data-ttu-id="14977-171">このポリシー機能は、コンテンツの表示、編集、削除など、イベントを記録する監査ログを提供します。</span><span class="sxs-lookup"><span data-stu-id="14977-171">This policy feature provides an audit log that records events, such as when content is viewed, edited, or deleted.</span></span>  <br/> |
|||||||<span data-ttu-id="14977-172">情報管理ポリシーの一部として監査が有効になっている場合、管理者は、Microsoft Excel に基づくポリシー利用状況レポートで監査データを表示し、現在の使用状況を要約することができます。</span><span class="sxs-lookup"><span data-stu-id="14977-172">When auditing is enabled as part of an information management policy, administrators can view the audit data in policy usage reports that are based in Microsoft Excel and that summarize current usage.</span></span> <span data-ttu-id="14977-173">管理者は、これらのレポートを使用して、組織内でどのように情報が使用されているかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="14977-173">Administrators can use these reports to determine how information is being used within the organization.</span></span> <span data-ttu-id="14977-174">これらのレポートは、組織が法令遵守を確認して文書化したり、潜在的な懸念事項を調査する際にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="14977-174">These reports can also help organizations to verify and document their regulatory compliance or to investigate potential concerns.</span></span>  <br/> |
|||||||<span data-ttu-id="14977-175">監査ログには次の情報が記録されます。イベント名、イベントの日付と時刻、およびアクションを実行したユーザーのシステム名です。</span><span class="sxs-lookup"><span data-stu-id="14977-175">The audit log records the following information: event name, date and time of the event, and system name of the user who performed the action.</span></span>  <br/> |
   
1. <span data-ttu-id="14977-176">ポリシーの一部としてバーコードが有効になっている場合、バーコードはドキュメントプロパティに追加され、バーコードが適用される文書のヘッダー領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="14977-176">When barcodes are enabled as part of a policy, they are added to document properties and displayed in the header area of the document to which the barcode is applied.</span></span> <span data-ttu-id="14977-177">ラベルと同様に、バーコードをドキュメントから手動で削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="14977-177">Like labels, barcodes can also be manually removed from a document.</span></span> <span data-ttu-id="14977-178">ユーザーがアイテムを印刷または保存するときにバーコードを含めるかどうかを確認するメッセージを表示するか、または2010の Office リリースプログラムの [**挿入**] タブを使用してバーコードを手動で挿入するかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="14977-178">You can specify whether users should be prompted to include the barcode when printing or saving an item or if the barcode should be inserted manually using the **Insert** tab in 2010 Office release programs.</span></span> 
    
    <span data-ttu-id="14977-179">バーコードを有効にするには</span><span class="sxs-lookup"><span data-stu-id="14977-179">To enable barcodes</span></span>
    
||||||<span data-ttu-id="14977-180">1. \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="14977-180">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="14977-181">**[ポリシーの編集] ページの [**バーコード**\> ] の下で、**バーコードを有効**にします。**</span><span class="sxs-lookup"><span data-stu-id="14977-181">**On the Edit Policy page, under **Barcodes**\> **Enable Barcodes**.**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="14977-182">**2.**</span><span class="sxs-lookup"><span data-stu-id="14977-182">**2.**</span></span> <br/> |<span data-ttu-id="14977-183">ユーザーにドキュメントにバーコードを挿入するように求めるには、[**保存または印刷する前に、ユーザーにバーコードを挿入するかどうかを確認**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-183">To prompt users to insert these barcodes into documents, choose **Prompt users to insert a barcode before saving or printing**.</span></span>  <br/> |
||||||<span data-ttu-id="14977-184">**3.**</span><span class="sxs-lookup"><span data-stu-id="14977-184">**3.**</span></span> <br/> |<span data-ttu-id="14977-185">**[OK]** を選択して、ポリシーにバーコード機能を適用します。</span><span class="sxs-lookup"><span data-stu-id="14977-185">Choose **OK** to apply the barcode feature to the policy.</span></span>  <br/> |
|||||||
 <span data-ttu-id="14977-186">バーコードポリシーは、コード39の標準バーコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="14977-186">The barcode policy generates Code 39 standard barcodes.</span></span> <span data-ttu-id="14977-187">各バーコードイメージには、バーコード値を表すバーコードの下にテキストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="14977-187">Each barcode image includes text below the barcode symbol that represents the barcode value.</span></span> <span data-ttu-id="14977-188">これにより、スキャンハードウェアが使用できない場合でも、バーコードデータを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="14977-188">This enables the barcode data to be used even when scanning hardware is not available.</span></span> <span data-ttu-id="14977-189">ユーザーは、サイト上のアイテムを検索するために、検索ボックスにバーコード番号を手動で入力することができます。</span><span class="sxs-lookup"><span data-stu-id="14977-189">Users can manually type the barcode number into the search box to locate the item on a site.</span></span>  <br/> |
   
1. <span data-ttu-id="14977-190">このポリシーの対象となるドキュメントにラベルがあることを要求するには、[**ラベルを有効**にする] を選択して、ラベルに必要な設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="14977-190">To require that documents that are subject to this policy have labels, choose **Enable Labels**, and then specify the settings that you want for the labels.</span></span>
    
    <span data-ttu-id="14977-191">ラベルを有効にするには</span><span class="sxs-lookup"><span data-stu-id="14977-191">To enable labels</span></span>
    
||||||<span data-ttu-id="14977-192">**1.**</span><span class="sxs-lookup"><span data-stu-id="14977-192">**1.**</span></span>|<span data-ttu-id="14977-193">\* \* ドキュメントにラベルを追加することをユーザーに要求するには、[**保存または印刷前にラベルを挿入するかどうかをユーザーに確認**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-193">\*\*To require users to add a label to a document, choose **Prompt users to insert a label before saving or printing**.</span></span>  <br/> <span data-ttu-id="14977-194">> [!NOTE]> ラベルを省略可能にする場合は、このチェックボックスをオンにしないでください。</span><span class="sxs-lookup"><span data-stu-id="14977-194">> [!NOTE]>  If you want labels to be optional, do not select this check box.</span></span>        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="14977-195">2.</span><span class="sxs-lookup"><span data-stu-id="14977-195">2.</span></span>  <br/> |<span data-ttu-id="14977-196">挿入した後で変更できないようにラベルをロックするには、[**ラベルを追加した後にラベルを変更できないよう**にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-196">To lock a label so that it cannot be changed after it has been inserted, choose **Prevent changes to labels after they are added**.</span></span>  <br/>  <span data-ttu-id="14977-197">この設定では、Word、Excel、PowerPoint などのクライアントアプリケーション内のアイテムにラベルが挿入されると、ラベルテキストは更新されません。</span><span class="sxs-lookup"><span data-stu-id="14977-197">This setting prevents the label text from updating once the label has been inserted into an item within a client application such as Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="14977-198">このドキュメントまたはアイテムのプロパティが更新されたときにラベルを更新する場合は、このチェックボックスをオンにしないでください。</span><span class="sxs-lookup"><span data-stu-id="14977-198">If you want the label to be updated when the properties for this document or item are updated, do not select this check box.</span></span>  <br/> |
||||||<span data-ttu-id="14977-199">3.</span><span class="sxs-lookup"><span data-stu-id="14977-199">3.</span></span>  <br/> |<span data-ttu-id="14977-200">[ラベルの書式] ボックスに、表示するラベルのテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="14977-200">In the Label format box, enter the text for the label as you want it to be displayed.</span></span> <span data-ttu-id="14977-201">ラベルには最大10個の列参照を含めることができます。それぞれの値は最大255文字まで指定できます。</span><span class="sxs-lookup"><span data-stu-id="14977-201">Labels can contain up to 10 column references, each of which can be up to 255 characters long.</span></span> <span data-ttu-id="14977-202">ラベルの書式を作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="14977-202">To create the format for your label, do the following:</span></span>  <br/> <span data-ttu-id="14977-203">ラベルに含める列の名前を、表示する順序に従って入力します (この名前を付ける場合)。</span><span class="sxs-lookup"><span data-stu-id="14977-203">Type the names of the columns that you want to include in the label in the order in which you want them to appear.</span></span> <span data-ttu-id="14977-204">[ポリシーの編集] ページの例{}に示すように、列名を中かっこ () で囲みます。</span><span class="sxs-lookup"><span data-stu-id="14977-204">Enclose the column names in curly brackets ({}), as shown in the example on the Edit Policy page.</span></span>  <br/> <span data-ttu-id="14977-205">[ポリシーの編集] ページの例に示されているように、角かっこの外側にある列を識別する単語を入力します。</span><span class="sxs-lookup"><span data-stu-id="14977-205">Type words to identify the columns outside the brackets, as shown in the example on the Edit Policy page.</span></span>  <br/> |
||||||<span data-ttu-id="14977-206">4.</span><span class="sxs-lookup"><span data-stu-id="14977-206">4.</span></span>  <br/> |<span data-ttu-id="14977-207">改行を追加するには、改行を表示する場所に「 **\n** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="14977-207">To add a line break, enter **\n** where you want the line break to appear.</span></span>  <br/> |
||||||<span data-ttu-id="14977-208">5.</span><span class="sxs-lookup"><span data-stu-id="14977-208">5.</span></span>  <br/> |<span data-ttu-id="14977-209">目的のフォントサイズとスタイルを選択し、文書内でラベルを左揃え、中央揃え、右揃えのどちらに配置するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="14977-209">Select the font size and style that you want, and specify whether you want the label positioned left, center, or right within the document.</span></span>  <br/>  <span data-ttu-id="14977-210">ユーザーのコンピューターで使用可能なフォントとスタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-210">Select a font and style that are available on the users' computers.</span></span> <span data-ttu-id="14977-211">フォントのサイズは、ラベルに表示できるテキストの量に影響します。</span><span class="sxs-lookup"><span data-stu-id="14977-211">The size of the font affects how much text can be displayed on the label.</span></span>  <br/> |
||||||<span data-ttu-id="14977-212">6.</span><span class="sxs-lookup"><span data-stu-id="14977-212">6.</span></span>  <br/> |<span data-ttu-id="14977-213">ラベルの高さと幅を入力します。</span><span class="sxs-lookup"><span data-stu-id="14977-213">Enter the height and width of the label.</span></span> <span data-ttu-id="14977-214">ラベルの高さは0.25 インチから20インチで、ラベルの幅は0.25 インチから20インチの範囲にすることができます。</span><span class="sxs-lookup"><span data-stu-id="14977-214">Label height can range from .25 inches to 20 inches, and label width can range from .25 inches to 20 inches.</span></span> <span data-ttu-id="14977-215">ラベルの文字列は、常にラベルのイメージ内で垂直方向に中央揃えされます。</span><span class="sxs-lookup"><span data-stu-id="14977-215">Label text is always vertically centered within the label image.</span></span>  <br/> |
||||||<span data-ttu-id="14977-216">7.</span><span class="sxs-lookup"><span data-stu-id="14977-216">7.</span></span>  <br/> |<span data-ttu-id="14977-217">[**更新**] を選択して、ラベルの内容をプレビューします。</span><span class="sxs-lookup"><span data-stu-id="14977-217">Choose **Refresh** to preview the label content.</span></span>  <br/> |
   
1. <span data-ttu-id="14977-218">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-218">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a><span data-ttu-id="14977-219">リスト、ライブラリ、またはフォルダーに対するポリシーを作成する (場所に応じた保持ポリシー)</span><span class="sxs-lookup"><span data-stu-id="14977-219">Create a policy for a list, library or folder (location-based retention policy)</span></span>
<span data-ttu-id="14977-220"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="14977-220"></span></span>

<span data-ttu-id="14977-221">特定のリスト、ライブラリ、またはフォルダーにのみ適用されるアイテム保持ポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="14977-221">You can define a retention policy that applies only to a specific list, library or folder.</span></span> <span data-ttu-id="14977-222">ただし、この方法でアイテム保持ポリシーを作成した場合、他のリスト、ライブラリ、フォルダー、またはサイトでこのポリシーを再利用することはできません。また、サイトコレクションポリシーを場所に基づいたポリシーに適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="14977-222">However, if you create a retention policy this way, you cannot reuse this policy on other lists, libraries, folders or sites, and you cannot apply a site collection policy to a location based policy.</span></span>
  
<span data-ttu-id="14977-223">単一の場所にあるすべての種類のコンテンツに対して単一のアイテム保持ポリシーを適用する場合は、ほとんどの場合、場所に基づく保持を使用することをお考えください。</span><span class="sxs-lookup"><span data-stu-id="14977-223">If you want to apply a single retention policy to all types of content in a single location, you will most likely want to use location-based retention.</span></span> <span data-ttu-id="14977-224">その他のほとんどの場合は、すべてのコンテンツタイプに対してアイテム保持ポリシーが指定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14977-224">In most other cases, you will want to verify that a retention policy is specified for all content types.</span></span>
  
 <span data-ttu-id="14977-225">継承を解除して新しいアイテム保持ポリシーを子レベルで定義しない限り、各サブフォルダーはその親のアイテム保持ポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="14977-225">Each subfolder inherits the retention policy of its parent, unless you choose to break inheritance and define a new retention policy at the child level.</span></span> 
  
<span data-ttu-id="14977-226">リストまたはライブラリに保持以外の情報管理ポリシーを定義する場合は、そのリストまたはライブラリに関連付けられている個々のリストコンテンツタイプごとに情報管理ポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14977-226">If you want to define an information management policy other than retention to a list or library, you need to define an information management policy for each individual list content type associated with that list or library.</span></span>
  
 <span data-ttu-id="14977-227">コンテンツタイプからリストまたはライブラリの場所に基づくポリシーに切り替えることを決定した場合、そのアイテム保持ポリシーのみが場所ベースのポリシーとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="14977-227">If at any point you decide to switch from content type to location-based policies for a list or library, only the retention policy will be used as the location-based policy.</span></span> <span data-ttu-id="14977-228">他のすべての管理ポリシー (監査、バーコード、およびバーコード) は、関連付けられたコンテンツタイプから継承されます。</span><span class="sxs-lookup"><span data-stu-id="14977-228">All other management policies (audits, barcodes, and barcodes) will be inherited from the associated content types.</span></span> 
  
 <span data-ttu-id="14977-229">サイトコレクションでは、ライブラリおよびフォルダーベースの保持機能を非アクティブ化することによって、場所に基づくポリシーを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="14977-229">Location based policies can be disabled for a site collection by deactivating the Library and Folder Based Retention feature.</span></span> <span data-ttu-id="14977-230">これにより、サイトコレクション管理者は、そのコンテンツタイプポリシーがリスト管理者の場所に基づいたポリシーによって上書きされないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="14977-230">This enables site collection administrators to ensure that their content type policies are not overridden by a list administrator's location based policies.</span></span> 
  
<span data-ttu-id="14977-231">リストまたはライブラリの情報管理ポリシーの設定を変更するには、少なくともリストの管理権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="14977-231">You need at least the Manage Lists permission to change the information management policy settings for a list or library.</span></span>
  
1. <span data-ttu-id="14977-232">情報管理ポリシーを指定するリストまたはライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="14977-232">Navigate to the list or library for which you want to specify an information management policy.</span></span> 
    
2. <span data-ttu-id="14977-233">リボンで、**ライブラリ**または**リスト**タブ\> **ライブラリの設定**または**リスト設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-233">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="14977-234">SharePoint Online で、[**設定**] をクリックし、[**リストの設定**] または [**ライブラリの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14977-234">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="14977-235">[**権限と管理**\> **情報管理ポリシーの設定**] の下。</span><span class="sxs-lookup"><span data-stu-id="14977-235">Under **Permissions and Management**\> **Information management policy settings**.</span></span>
  
![ドキュメント ライブラリの設定ページ上の情報管理ポリシーのリンク](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="14977-237">[情報管理ポリシーの設定] ページで、リストまたはライブラリの保持のソースが [ライブラリとフォルダー] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="14977-237">On the Information Management Policy Settings page, make sure that the source of retention for the list or library is set to Library and Folders.</span></span> 
  
<span data-ttu-id="14977-238">**コンテンツタイプ**がソースとして表示されている場合は、[**ソースの変更**] をクリックし、[**ライブラリとフォルダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14977-238">If **Content Type** appears as the source, click **Change Source**, and then click **Library and Folders**.</span></span> <span data-ttu-id="14977-239">コンテンツタイプのアイテム保持ポリシーが無視されるという警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="14977-239">You are alerted that content type retention policies will be ignored.</span></span> <span data-ttu-id="14977-240">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-240">Choose **OK**.</span></span> 
    
5. <span data-ttu-id="14977-241">[ポリシーの編集] ページの [**ライブラリベースの保持スケジュール**] で、作成するポリシーの簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="14977-241">On the Edit Policy page, under **Library Based Retention Schedule**, enter a brief description for the policy you are creating.</span></span> 
    
6. <span data-ttu-id="14977-242">[**保持ステージの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-242">Choose **Add a retention stage…**</span></span>
    
     <span data-ttu-id="14977-243">[レコード] の下で、[レコードに対してさまざまな保持ステージを定義する] オプションを選択することによって、レコードに異なるアイテム保持ポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="14977-243">Note that under Records, you can choose to define different retention policies for records by selecting the Define different retention stages for records option.</span></span> 
    
7. <span data-ttu-id="14977-244">[ステージのプロパティ] ダイアログで、[保持期間] オプションを選択して、ドキュメントまたはアイテムの有効期限を設定します。</span><span class="sxs-lookup"><span data-stu-id="14977-244">In the Stage properties dialog, select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="14977-245">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="14977-245">Do one of the following:</span></span>
    
  - <span data-ttu-id="14977-246">日付プロパティに基づいて有効期限を設定するには、[**イベント** \> ] の [**このステージはアイテムの日付プロパティに基づいてい**ます] の下にある [ドキュメントまたはアイテム] アクション (たとえば、[作成日時] または [変更日時]) を選択し、このアクションの後の時間の増分を選択します (たとえば、アイテムを期限切れにする場合は、日数、月数、または年数を指定します。</span><span class="sxs-lookup"><span data-stu-id="14977-246">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span> 
    
  - <span data-ttu-id="14977-247">カスタム保持期間の計算式を使用して有効期限を決定するには、[**このサーバーにインストールされているカスタム保持期間の数式で設定**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-247">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="14977-248">このオプションは、管理者によってカスタム式が設定されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="14977-248">This option is only available if a custom formula has been set up by your administrator.</span></span> 
  
  - <span data-ttu-id="14977-249">[**アクション**] で、ドキュメントまたはアイテムの有効期限が切れたときに行う処理を指定します。</span><span class="sxs-lookup"><span data-stu-id="14977-249">Under **Action**, specify what you want to happen when the document or item expires.</span></span> <span data-ttu-id="14977-250">ドキュメントまたはアイテムに対する特定のアクション (削除など) を有効にするには、リストからアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-250">To enable a specific action to happen to the document or item (such as deletion), select an action from the list.</span></span> 
    
8. <span data-ttu-id="14977-251">[**ワークフローの開始**] オプションは、既にワークフローが関連付けられているリスト、ライブラリ、またはコンテンツタイプのポリシーを定義している場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="14977-251">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="14977-252">その後、選択するワークフローが選択されます。</span><span class="sxs-lookup"><span data-stu-id="14977-252">You will then be given a choice of workflows to choose from.</span></span> 
    
9. <span data-ttu-id="14977-253">[**定期的なアイテム**] で、[**このステージの動作を繰り返す**] を選択します。を選択し、アクションを実行する頻度を入力します。</span><span class="sxs-lookup"><span data-stu-id="14977-253">Under **Recurrence**, choose **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="14977-254">このオプションは、選択したアクションを繰り返すことができる場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="14977-254">This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="14977-255">たとえば、アクションが**完全に削除**されると、定期的なアイテムを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="14977-255">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span> 
  
10. <span data-ttu-id="14977-256">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-256">Choose **OK**.</span></span>
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a><span data-ttu-id="14977-257">サイトコレクションポリシーをコンテンツタイプに適用する</span><span class="sxs-lookup"><span data-stu-id="14977-257">Apply a site collection policy to a content type</span></span>
<span data-ttu-id="14977-258"><a name="__apply_a_site"> </a></span><span class="sxs-lookup"><span data-stu-id="14977-258"></span></span>

<span data-ttu-id="14977-259">サイトコレクションポリシーとしてサイトに情報管理ポリシーが既に作成されている場合は、1つのポリシーをコンテンツタイプに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="14977-259">If information management policies have already been created for your site as site collection policies, you can apply one of the policies to a content type.</span></span> <span data-ttu-id="14977-260">これにより、同じ親コンテンツタイプを共有しないサイトコレクション内の複数のコンテンツタイプに同じポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="14977-260">By doing this, you can apply the same policy to multiple content types in a site collection that do not share the same parent content type.</span></span>
  
 <span data-ttu-id="14977-261">ポリシーをサイトコレクション内の複数のコンテンツタイプに適用し、Managed Metadata Service を構成している場合は、コンテンツタイプの発行を使用して、情報管理ポリシーを複数のサイトコレクションに公開できます。</span><span class="sxs-lookup"><span data-stu-id="14977-261">If you want to apply policies to multiple content types in a site collection, and you have a Managed Metadata Service configured, you can use Content Type Publishing to publish out information management polices to multiple site collections.</span></span> <span data-ttu-id="14977-262">詳細については、「[サイトコレクション全体にポリシーを適用](#apply-a-policy-across-site-collections)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14977-262">See the section [Apply a policy across site collections](#apply-a-policy-across-site-collections) for more information.</span></span> 
  
1. <span data-ttu-id="14977-263">ポリシーを適用するコンテンツタイプを含むリストまたはライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="14977-263">Navigate to the list or library that contains the content type to which you want to apply a policy.</span></span>
    
2. <span data-ttu-id="14977-264">リボンで、**ライブラリ**または**リスト**タブ\> **ライブラリの設定**または**リスト設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-264">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="14977-265">SharePoint Online で、[**設定**] をクリックし、[**リストの設定**] または [**ライブラリの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14977-265">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="14977-266">[**権限と管理** \> **情報管理ポリシーの設定**] の下。</span><span class="sxs-lookup"><span data-stu-id="14977-266">Under **Permissions and Management** \> **Information management policy settings**.</span></span>
  
![ドキュメント ライブラリの設定ページ上の情報管理ポリシーのリンク](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="14977-268">ポリシーソースが [**コンテンツタイプ**] に設定されていることを確認し、[**コンテンツタイプポリシー** ] で、ポリシーを適用するコンテンツタイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-268">Verify that the policy source is set to **Content Types**, and under **Content Type Policies** select the content type you want to apply the policy to.</span></span> 
    
5. <span data-ttu-id="14977-269">[**ポリシー** \>を指定して**サイトコレクションポリシーを使用**する] で、適用するポリシーをリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-269">Under **Specify the Policy** \> **Use a site collection policy**, and then select the policy that you want to apply from the list.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="14977-270">[**サイトコレクションポリシーを使用**する] オプションが使用できない場合は、サイトコレクションに対してサイトコレクションポリシーが定義されていません。</span><span class="sxs-lookup"><span data-stu-id="14977-270">If the **Use a site collection policy** option is not available, no site collection policies have been defined for the site collection.</span></span> 
  
6. <span data-ttu-id="14977-271">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-271">Choose **OK**.</span></span>
    
     <span data-ttu-id="14977-272">作業しているリストまたはライブラリが複数のコンテンツタイプの管理をサポートしている場合は、[**コンテンツタイプ**] で情報管理ポリシーを指定するコンテンツタイプを選択できます。</span><span class="sxs-lookup"><span data-stu-id="14977-272">If the list or library you are working with supports the management of multiple content types, under **Content Types** you can choose the content type for which you want to specify an information management policy.</span></span> <span data-ttu-id="14977-273">この操作を行うと、上記の手順5に進みます。</span><span class="sxs-lookup"><span data-stu-id="14977-273">This will take you directly to Step 5 above.</span></span> 
    
## <a name="apply-a-policy-across-site-collections"></a><span data-ttu-id="14977-274">サイトコレクション間でポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="14977-274">Apply a policy across site collections</span></span>
<span data-ttu-id="14977-275"><a name="__toc260646789"> </a></span><span class="sxs-lookup"><span data-stu-id="14977-275"></span></span>

<span data-ttu-id="14977-276">コンテンツタイプの発行をセットアップするために Managed Metadata service アプリケーションを使用して、サイトコレクション間でコンテンツタイプを共有します。</span><span class="sxs-lookup"><span data-stu-id="14977-276">Share content types across site collections by using a Managed Metadata service application to set up content type publishing.</span></span> <span data-ttu-id="14977-277">コンテンツタイプの発行は、コンテンツタイプを一元的に作成および更新できるため、また複数のサブスクライブ元サイトコレクションまたは Web アプリケーションに更新を発行できるため、コンテンツとメタデータをサイト全体で一貫して管理するのに便利です。</span><span class="sxs-lookup"><span data-stu-id="14977-277">Content type publishing helps you manage content and metadata consistently across your sites because content types can be created and updated centrally, and updates can be published out to multiple subscribing site collections or Web applications.</span></span>
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a><span data-ttu-id="14977-278">サイトコレクション全体で使用するテンプレートを既存のポリシーから作成する</span><span class="sxs-lookup"><span data-stu-id="14977-278">Create a template from an existing policy to use across site collections</span></span>
<span data-ttu-id="14977-279"><a name="__toc262125409"> </a></span><span class="sxs-lookup"><span data-stu-id="14977-279"></span></span>

<span data-ttu-id="14977-280">情報管理ポリシーを定義し、そこからテンプレートを作成して、複数のサイトコレクション間で必要に応じて使用することができます。</span><span class="sxs-lookup"><span data-stu-id="14977-280">You can define an information management policy and then create a template from it to use as needed across multiple site collections.</span></span> <span data-ttu-id="14977-281">この方法は、情報ポリシーのバックアップが必要な場合、またはサイトコレクション間で1つのポリシーを適用するためにコンテンツタイプの発行を使用する代替手段としても使用できます。</span><span class="sxs-lookup"><span data-stu-id="14977-281">This method can be used if you want to have a backup of your information policies, or it can also be used as an alternate method to using content type publishing for applying one policy across site collections.</span></span> <span data-ttu-id="14977-282">ポリシーのテンプレートまたはバックアップを作成するには、ポリシーを1つのサイトコレクションからエクスポートしてから、保存した場所または別のサイトコレクションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="14977-282">You create a template or backup of the policy by exporting the policy from one site collection and then importing it to a saved location or to another site collection.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="14977-283">ポリシーテンプレートのセットを作成する方法としてエクスポート/インポート機能を使用している場合は、ポリシーの .xml ファイルに一意の識別子が存在することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="14977-283">If you using the export/import feature as a way to make a set of policy templates, keep in mind that a unique identifier exists in the policy .xml file.</span></span> <span data-ttu-id="14977-284">そのため、この一意識別子を変更せずに、そのポリシーをサイトに複数回インポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="14977-284">Because of this, you cannot import that policy into a site more than once without changing this unique identifier.</span></span> 
  
### <a name="export-a-policy"></a><span data-ttu-id="14977-285">ポリシーをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="14977-285">Export a policy</span></span>
<span data-ttu-id="14977-286"><a name="__toc260646790"> </a></span><span class="sxs-lookup"><span data-stu-id="14977-286"></span></span>

1. <span data-ttu-id="14977-287">サイトコレクションのホームページで、[**設定**![] [サイトの設定] の代わりに [設定] を選択します。](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)**設定。** \></span><span class="sxs-lookup"><span data-stu-id="14977-287">On the site collection home page, choose **Settings**![Small Settings gear that took the place of Site Settings.](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="14977-288">SharePoint グループに接続されたサイトで、[**設定**] をクリックし、[**サイトコンテンツ**]、[**サイトの設定**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="14977-288">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="14977-289">[サイトの設定] ページの [**サイトコレクションの管理** \> **コンテンツタイプポリシーテンプレート**] を指定します。</span><span class="sxs-lookup"><span data-stu-id="14977-289">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![[サイトの設定] ページの [コンテンツ タイプ ポリシーのテンプレート] リンク](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="14977-291">[エクスポート\>するポリシー] を選択して、下\>の**エクスポート**にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="14977-291">Choose the policy you want to export \> scroll to the bottom \> **Export**.</span></span>
    
4. <span data-ttu-id="14977-292">ファイルを保存するか開くかを確認するメッセージが表示されたら、[**保存**] を選択して、ファイルを保存する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-292">At the prompt to save or open the file, choose **Save**, and then select a location to save the file to.</span></span> <span data-ttu-id="14977-293">ポリシーをインポートするサイトコレクションで使用可能な場所を選択してください。</span><span class="sxs-lookup"><span data-stu-id="14977-293">Be sure to select a location that is available to the site collections that are importing the policy.</span></span>
    
5. <span data-ttu-id="14977-294">[ダウンロードの完了] ダイアログが表示されたら、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-294">When the Download Complete dialog is displayed, choose **Close**.</span></span>
    
### <a name="import-a-policy-to-a-different-site-collection"></a><span data-ttu-id="14977-295">ポリシーを別のサイトコレクションにインポートする</span><span class="sxs-lookup"><span data-stu-id="14977-295">Import a policy to a different site collection</span></span>
<span data-ttu-id="14977-296"><a name="__toc260646791"> </a></span><span class="sxs-lookup"><span data-stu-id="14977-296"></span></span>

<span data-ttu-id="14977-297">情報管理ポリシーをインポートすると、特定のサイトコレクション内のサイトレベルまたはリストレベルで複数のコンテンツタイプに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="14977-297">Importing an information management policy enables you to apply it to multiple content types at the site or list level within any given site collection.</span></span> <span data-ttu-id="14977-298">これを行うと、次の2つの利点があります。各コンテンツタイプにポリシーを再定義して適用する必要はありません。また、ポリシーに変更を加えることによって、ポリシーの変更を1か所で容易に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="14977-298">The benefits of doing this are twofold: you don't have to re-define and apply the policy on each content type, and you can more easily manage policy modifications by making changes to the policy in just one place.</span></span>
  
1. <span data-ttu-id="14977-299">ポリシーを適用するサイトコレクションのホームページで、[設定] [サイトの設定] の代わりに [**設定**![] [小規模設定歯車] を選択します。](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)**設定。** \></span><span class="sxs-lookup"><span data-stu-id="14977-299">On the home page of the site collection to which you want to apply the policy, choose **Settings**![Small Settings gear that took the place of Site Settings.](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="14977-300">SharePoint グループに接続されたサイトで、[**設定**] をクリックし、[**サイトコンテンツ**]、[**サイトの設定**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="14977-300">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="14977-301">[サイトの設定] ページの [**サイトコレクションの管理** \> **コンテンツタイプポリシーテンプレート**] を指定します。</span><span class="sxs-lookup"><span data-stu-id="14977-301">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span>
    
3. <span data-ttu-id="14977-302">[ポリシー] ページ\>の [**インポート** \> ] を**選択**して、ポリシーの XML ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="14977-302">On the Policies page \> **Import** \> **Browse** to find the XML file for the policy.</span></span> 
    
4. <span data-ttu-id="14977-303">ポリシーが保存\> \*\*\*\* されている XML ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="14977-303">Select the XML file in which the policy has been saved \> **Open**.</span></span> 
    
5. <span data-ttu-id="14977-304">[サイトコレクションポリシーのインポート] ページ\> \*\*\*\* で、このポリシーをサイトコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="14977-304">On the Import a Site Collection Policy page \> **Import** to add the policy to the site collection.</span></span> 
    
<span data-ttu-id="14977-305">インポートされたポリシーは、サイトレベルまたはリストレベルで、1つまたは複数のコンテンツタイプに適用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="14977-305">Your imported policy can now be applied to one or many content types at the site or list level.</span></span> 
  
<span data-ttu-id="14977-306">情報管理ポリシーを使用すると、コンテンツの保持期間を制御したり、コンテンツについてユーザーの作業を監査したり、バーコードやラベルをドキュメントに追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="14977-306">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="14977-307">ポリシーを使用すると、法律上および行政上の規制や内部のビジネスプロセスに準拠することができます。</span><span class="sxs-lookup"><span data-stu-id="14977-307">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="14977-308">管理者は、ドキュメントの追跡方法やドキュメントを保持する期間を制御するポリシーをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="14977-308">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>

<span data-ttu-id="14977-309">情報管理ポリシーは、サイト階層内の3つの異なる場所 (最も広いものから最も狭いものまで) に作成できます。</span><span class="sxs-lookup"><span data-stu-id="14977-309">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
- <span data-ttu-id="14977-310">サイトコレクション内の複数のコンテンツタイプで使用するポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="14977-310">Create a policy to use on multiple content types within a site collection.</span></span>
- <span data-ttu-id="14977-311">サイトコンテンツタイプのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="14977-311">Create a policy for a site content type.</span></span>
- <span data-ttu-id="14977-312">リストまたはライブラリのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="14977-312">Create a policy for a list or library.</span></span>

<span data-ttu-id="14977-313">詳細については、「[情報管理ポリシーの概要](intro-to-info-mgmt-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14977-313">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  

