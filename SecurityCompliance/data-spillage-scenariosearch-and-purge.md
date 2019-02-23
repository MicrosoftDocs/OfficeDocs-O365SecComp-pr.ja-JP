---
title: 電子情報開示ソリューションシリーズデータ流出シナリオ-検索と削除
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: Office 365 の電子情報開示および検索ツールを使用して、組織内のデータ流出インシデントを管理および応答します。
ms.openlocfilehash: 0da49dfbe8104d89a1abf4a14adce51ec0ef25f1
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219427"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a><span data-ttu-id="10dcb-103">電子情報開示ソリューションシリーズ: Data 流出 scenario-検索と削除</span><span class="sxs-lookup"><span data-stu-id="10dcb-103">eDiscovery solution series: Data spillage scenario - Search and purge</span></span>

 <span data-ttu-id="10dcb-p101">**データ流出とは何ですか。なぜ注意する必要があるのですか。** データ流出は、信頼できない環境に機密ドキュメントがリリースされるときに発生します。データ流出インシデントが検出された場合、流出のサイズと場所をすばやく評価し、その周囲のユーザーアクティビティを調べて、システムから完全に削除されたデータを完全に削除することが重要です。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p101">**What is data spillage and why should you care?** Data spillage is when a confidential document is released into an untrusted environment. When a data spillage incident is detected, it's important to quickly assess the size and locations of the spillage, examine user activities around it,  and then permanently purge the spilled data from the system.</span></span> 
  
## <a name="data-spillage-scenario"></a><span data-ttu-id="10dcb-107">データ流出シナリオ</span><span class="sxs-lookup"><span data-stu-id="10dcb-107">Data spillage scenario</span></span>

<span data-ttu-id="10dcb-p102">Contoso 社のリード情報セキュリティ責任者であること。従業員が知らずに大量の機密文書を電子メールで共有しているというデータ流出状況について通知されています。このドキュメントを内部および外部で受信したユーザーをすばやく評価する必要がある。識別された場合は、他の調査担当者とのケース調査結果を共有して、Office 365 からデータを完全に削除してください。調査が完了したら、永続的な削除と、今後の参照に関するその他の大文字と小文字の詳細情報を含むレポートを生成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p102">You’re a lead information security officer at Contoso. You are informed of a data spillage situation where an employee unknowingly shared a highly confidential document with multiple people through email. You want to quickly assess who received this document internally and externally. Once identified, you would like to share case findings with other investigators to review, and then permanently remove the data from Office 365. After the investigation is complete, you want to generate a report with the evidence of permanent removal and other case details for any future reference.</span></span>
  
### <a name="scope-of-this-article"></a><span data-ttu-id="10dcb-113">この記事の対象範囲</span><span class="sxs-lookup"><span data-stu-id="10dcb-113">Scope of this article</span></span>

<span data-ttu-id="10dcb-p103">このドキュメントでは、Office 365 からメッセージを完全に削除して、アクセスまたは復元できないようにする手順の一覧を示します。削除済みアイテムの保存期間が経過するまでメッセージを削除して回復可能にするには、「 [Office 365 組織で電子メールメッセージを検索して削除](search-for-and-delete-messages-in-your-organization.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p103">This document provides a list of instructions on how to permanently remove a message from Office 365 so that it's not accessible or recoverable. To delete a message and make it recoverable until the deleted item retention period expires, see [Search for and delete email messages in your Office 365 organization](search-for-and-delete-messages-in-your-organization.md).</span></span>
  
## <a name="workflow-for-managing-data-spillage-incidents"></a><span data-ttu-id="10dcb-116">データ流出インシデントを管理するためのワークフロー</span><span class="sxs-lookup"><span data-stu-id="10dcb-116">Workflow for managing data spillage incidents</span></span>

<span data-ttu-id="10dcb-117">データ流出インシデントを管理する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="10dcb-117">Here's a how to manage a data spillage incident:</span></span>

![データ流出インシデントを管理するための8段階のワークフロー](media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[<span data-ttu-id="10dcb-119">オプション手順 1: ケースにアクセスできるユーザーを管理し、コンプライアンスの境界を設定する</span><span class="sxs-lookup"><span data-stu-id="10dcb-119">(Optional) Step 1: Manage who can access the case and set compliance boundaries</span></span>](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[<span data-ttu-id="10dcb-120">手順 2: 電子情報開示ケースを作成する</span><span class="sxs-lookup"><span data-stu-id="10dcb-120">Step 2: Create an eDiscovery case</span></span>](#step-2-create-an-ediscovery-case)<br/>
[<span data-ttu-id="10dcb-121">手順 3: こぼれたデータを検索する</span><span class="sxs-lookup"><span data-stu-id="10dcb-121">Step 3: Search for the spilled data</span></span>](#step-3-search-for-the-spilled-data)<br/>
[<span data-ttu-id="10dcb-122">手順 4: ケースの調査結果を確認して検証する</span><span class="sxs-lookup"><span data-stu-id="10dcb-122">Step 4: Review and validate case findings</span></span>](#step-4-review-and-validate-case-findings)<br/>
[<span data-ttu-id="10dcb-123">手順 5: メッセージ追跡ログを使用して、こぼれたデータがどのように共有されているかを確認する</span><span class="sxs-lookup"><span data-stu-id="10dcb-123">Step 5: Use message trace log to check how spilled data was shared</span></span>](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[<span data-ttu-id="10dcb-124">手順 6: メールボックスを準備する</span><span class="sxs-lookup"><span data-stu-id="10dcb-124">Step 6: Prepare the mailboxes</span></span>](#step-6-prepare-the-mailboxes)<br/>
[<span data-ttu-id="10dcb-125">手順 7: こぼれたデータを完全に削除する</span><span class="sxs-lookup"><span data-stu-id="10dcb-125">Step 7: Permanently delete the spilled data</span></span>](#step-7-permanently-delete-the-spilled-data)<br/>
[<span data-ttu-id="10dcb-126">手順 8: 確認し、削除の証明を提供し、監査を行う</span><span class="sxs-lookup"><span data-stu-id="10dcb-126">Step 8: Verify, provide a proof of deletion, and audit</span></span>](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a><span data-ttu-id="10dcb-127">開始する前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="10dcb-127">Things to know before you start</span></span>

- <span data-ttu-id="10dcb-p104">メールボックスが保持されている場合、削除されたメッセージは保持期間が経過するか、保留が解除されるまで、[回復可能なアイテム] フォルダーに残ります。[手順 6](#step-6-prepare-the-mailboxes)メールボックスからホールドを削除する方法について説明します。保留リストを削除する前に、レコード管理または法務部門に確認してください。組織には、保留中のメールボックスとデータ流出インシデントのどちらを優先するかを定義するポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p104">When a mailbox is on hold, a deleted message remains in the Recoverable Items folder until the retention period expires or the hold is released. [Step 6](#step-6-prepare-the-mailboxes) describes how to remove hold from the mailboxes. Check with your records management or legal departments before removing the hold. Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
    
- <span data-ttu-id="10dcb-p105">データ流出調査担当者がどのユーザーメールボックスを検索し、そのケースにアクセスできるかを制御するには、コンプライアンスの境界を設定して、[手順 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)で説明されているカスタム役割グループを作成します。これを行うには、組織の管理役割グループのメンバーであるか、役割管理の役割が割り当てられている必要があります。組織内の管理者が既に法令遵守の境界を設定している場合は、手順1を省略できます。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p105">To control which user mailboxes an data spillage investigator can search and manage who can access the case, you can set up compliance boundaries and create a custom role group, which is described in [Step 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries). To do this, you have to be a member of the Organization Management role group or be assigned the role management role. If you or in administrator in your organization has already set compliance boundaries, you can skip Step 1.</span></span>
    
- <span data-ttu-id="10dcb-p106">ケースを作成するには、電子情報開示マネージャーの役割グループのメンバーであるか、またはケース管理役割が割り当てられているカスタム役割グループのメンバーである必要があります。メンバーではない場合は、Office 365 管理者に[電子情報開示マネージャーの役割グループへの追加](assign-ediscovery-permissions.md)を依頼してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p106">To create a case, you must be a member of the eDiscovery Manager role group or be a member of a custom role group that's assigned the Case Management role. If you're not a member, ask an Office 365 administrator to [add you to the eDiscovery manager role group](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="10dcb-p107">組織に挿入されたデータを削除するには、Exchange Online PowerShell で[DeleteContent](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps)コマンドを使用する必要があります。さらに、 *DeleteContent*パラメーターを使用するには、メールボックスのインポートのエクスポート役割が割り当てられている Exchange Online の役割グループのメンバーでもある必要があります。「 [Manage role groups](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx)」の「役割グループに役割を追加する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p107">To delete data that's spilled into your organization, you need to use the [Search-Mailbox -DeleteContent](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps) command in Exchange Online PowerShell. Additionally, to use the  *DeleteContent* parameter, you also have to be a member of a role group in Exchange Online that's assigned the Mailbox Import Export role. See the "Add a role to a role group" section in [Manage role groups](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx).</span></span>
    
- <span data-ttu-id="10dcb-p108">手順8で Office 365 監査ログ電子情報開示アクティビティを検索するには、組織に対して監査を有効にする必要があります。過去90日以内に実行されたアクティビティを検索できます。監査を有効にして使用する方法の詳細については、手順8の「[データ流出調査プロセスの監査](#auditing-the-data-spillage-investigation-process)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p108">To search the Office 365 audit log eDiscovery activities in Step 8, auditing must be turned on for your organization. You can search for activities that were performed within the last 90 days. To learn more about how to enable and use auditing, see the [Auditing the data spillage investigation process](#auditing-the-data-spillage-investigation-process) section in Step 8.</span></span> 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a><span data-ttu-id="10dcb-143">オプション手順 1: ケースにアクセスできるユーザーを管理し、コンプライアンスの境界を設定する</span><span class="sxs-lookup"><span data-stu-id="10dcb-143">(Optional) Step 1: Manage who can access the case and set compliance boundaries</span></span>

<span data-ttu-id="10dcb-p109">組織の慣行によっては、データ流出のインシデントを調査し、コンプライアンスの境界を設定するために使用する電子情報開示ケースにアクセスできるユーザーを制御する必要があります。これを行う最も簡単な方法は、「Office 365 Security & コンプライアンスセンターで既存の役割グループのメンバーとして調査担当者を追加し、その役割グループを電子情報開示ケースのメンバーとして追加することです。組み込みの電子情報開示の役割グループと、電子情報開示ケースにメンバーを追加する方法については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターでの電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p109">Depending on your organizational practice, you need to control who can access the eDiscovery case used to investigate a data spillage incident and set up compliance boundaries. The easiest way to do this is to add investigators as members of an existing role group in the Office 365 Security & Compliance Center and then add the role group as a member of the eDiscovery case. For information about the built-in eDiscovery role groups and how to add members to an eDiscovery case, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
<span data-ttu-id="10dcb-p110">また、組織のニーズに合わせて新しい役割グループを作成することもできます。たとえば、組織内のデータ流出捜査官のグループが、すべてのデータ流出ケースにアクセスして共同作業する必要があるとします。これを行うには、"Data 流出捜査" 役割グループを作成し、適切な役割 (エクスポート、RMS の解読、レビュー、プレビュー、コンプライアンス検索、ケース管理) を割り当て、データ流出捜査を役割グループに追加して、データ流出電子情報開示ケースのメンバーとしての役割グループ。これを行う方法の詳細については、「 [Office 365 で電子情報開示の調査のためのコンプライアンス境界を設定](set-up-compliance-boundaries.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p110">You can also create a new role group that aligns with your organizational needs. For example, you might want a group of data spillage investigators in the organization to access and collaborate on all data spillage cases. You can do this by creating a "Data Spillage Investigator" role group, assigning the appropriate roles (Export, RMS Decrypt, Review, Preview, Compliance Search, and Case Management), adding the data spillage investigators to the role group, and then adding the role group as a member of the data spillage eDiscovery case. See [Set up compliance boundaries for eDiscovery investigations in Office 365](set-up-compliance-boundaries.md) for detailed instructions on how to do this.</span></span> 
  
## <a name="step-2-create-an-ediscovery-case"></a><span data-ttu-id="10dcb-151">手順 2: 電子情報開示ケースを作成する</span><span class="sxs-lookup"><span data-stu-id="10dcb-151">Step 2: Create an eDiscovery case</span></span>

<span data-ttu-id="10dcb-p111">電子情報開示ケースは、データ流出調査を効率的に管理する方法を提供します。手順1で作成した役割グループにメンバーを追加したり、新しい電子情報開示ケースのメンバーとして役割グループを追加したり、反復検索を実行してこぼれたデータを検索したり、共有するレポートをエクスポートしたり、ケースの状態を追跡したり、c の詳細を参照したりすることができます。必要に応じて、ase を行います。データ流出のインシデントに使用される電子情報開示ケースの命名規則を確立し、必要に応じて後で検索して参照できるように、ケースの名前と説明にできるだけ多くの情報を提供することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p111">An eDiscovery case provides an effective way to manage your data spillage investigation. You can add members to the role group that you created in Step 1, add the role group as a member of new a eDiscovery case, perform iterative searches to find the spilled data, export a report to share, track the status of the case, and then refer back to the details of the case if needed. Consider establishing a naming convention for eDiscovery cases used for data spillage incidents, and provide as much information as you can in the case name and description so you can locate and refer to in the future if necessary.</span></span>
  
<span data-ttu-id="10dcb-p112">新しいケースを作成するには、セキュリティ&amp;コンプライアンスセンターで電子情報開示を使用できます。「 [Office 365 Security & コンプライアンスセンターの電子情報開示ケース](ediscovery-cases.md#step-2-create-a-new-case)」の「新しいケースを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p112">To create a new case, you can use eDiscovery in the Security &amp; Compliance Center. See "Create a new case" in [eDiscovery Cases in the Office 365 Security & Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
  
## <a name="step-3-search-for-the-spilled-data"></a><span data-ttu-id="10dcb-157">手順 3: こぼれたデータを検索する</span><span class="sxs-lookup"><span data-stu-id="10dcb-157">Step 3: Search for the spilled data</span></span>

<span data-ttu-id="10dcb-p113">ケースおよび管理アクセスを作成したので、ケースを繰り返し検索して、こぼれたデータを見つけて、そのデータを含むメールボックスを特定することができます。[手順 7](#step-7-permanently-delete-the-spilled-data)で同じメッセージを削除するには、電子メールメッセージの検索に使用したものと同じ検索クエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p113">Now that you've created a case and managed access, you can use the case to iteratively search to find the spilled data and identify the mailboxes that contain the spilled data. You will use the same search query that you used to find the email messages to delete those same messages in [Step 7](#step-7-permanently-delete-the-spilled-data).</span></span>
  
<span data-ttu-id="10dcb-160">電子情報開示ケースに関連付けられたコンテンツ検索を作成するには、「 [Office 365 セキュリティ & コンプライアンスセンターの電子情報開示ケース](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case)」の「ケースに関連付けられたコンテンツ検索を作成して実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-160">To create a content searches associated with an eDiscovery case, see "Create and run a Content Search associated with a case" in [eDiscovery Cases in the Office 365 Security & Compliance Center](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case).</span></span>
  
 <span data-ttu-id="10dcb-p114">**重要:** 検索クエリで使用するキーワードには、検索している実際のこぼれたデータが含まれている場合があります。たとえば、社会保障番号を含むドキュメントを検索し、それを検索キーワードとして使用する場合は、さらに流出を回避するために、後でクエリを削除する必要があります。手順8の「[検索クエリを削除する](#deleting-the-search-query)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p114">**Important:** The keywords that you use in the search query may contain the actual spilled data that you're searching for. For example, if you searching for documents containing a social security number and you use the it as search keyword, you must delete the query afterwards to avoid further spillage. See [Deleting the search query](#deleting-the-search-query) in Step 8.</span></span> 
  
## <a name="step-4-review-and-validate-case-findings"></a><span data-ttu-id="10dcb-164">手順 4: ケースの調査結果を確認して検証する</span><span class="sxs-lookup"><span data-stu-id="10dcb-164">Step 4: Review and validate case findings</span></span>

<span data-ttu-id="10dcb-p115">コンテンツ検索を作成した後、検索結果を確認して検証し、削除する必要がある電子メールメッセージのみが含まれていることを確認する必要があります。コンテンツ検索では、その他のデータ流出を回避するために、検索結果をエクスポートせずに、1000メールメッセージのランダムなサンプリングをプレビューできます。コンテンツ検索の制限の詳細については[、「Office 365 セキュリティ&amp; /コンプライアンスセンター」](limits-for-content-search.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p115">After you create a content search, you need to review and validate that the search results and verify that they consist only of the email messages that must be deleted. In a content search, you can preview a random sampling of 1,000 email messages without exporting the search results to avoid further data spillage. You can read more about the preview limitations at [Limits for Content Search in the Office 365 Security &amp; Compliance Center](limits-for-content-search.md).</span></span>
  
<span data-ttu-id="10dcb-p116">メールボックスごとに1000個を超えるメールボックスを使用している場合や、確認するメールボックスごとの電子メールメッセージ数が100を超える場合は、日付範囲や送信者/受信者などの追加のキーワードや条件を使用して、最初の検索を複数の検索に分割し、各検索の結果を確認することができます。1.[手順 7](#step-7-permanently-delete-the-spilled-data)でメッセージを削除するときに使用するすべての検索クエリを書き留めておいてください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p116">If you have more than 1,000 mailboxes or more than 100 email messages per mailbox to review, you can divide the initial search into multiple searches by using additional keywords or conditions such as date range or sender/recipient and review the results of each search individually. Make sure to note down all search queries to use when you delete messages in [Step 7](#step-7-permanently-delete-the-spilled-data).</span></span>

<span data-ttu-id="10dcb-p117">保管担当者またはエンドユーザーに office 36 E5 ライセンスが割り当てられている場合は、office 365 Advanced eDiscovery を使用して、最大1万の検索結果を一度に調べることができます。レビュー対象の電子メールメッセージが1万を超える場合は、検索結果が日付で並べ替えられるように、検索クエリを日付範囲で分割し、各結果を個別に確認できます。高度な電子情報開示では、プレビューパネルの [**ラベル**] 機能を使用して検索結果にタグを付け、ラベルの付いたタグで検索結果をフィルター処理することができます。これは、第2のレビュー担当者と共同で作業する場合に役立ちます。高度な電子情報開示の追加分析ツール (光学式文字認識、電子メールスレッド、予測コーディングなど) を使用すると、数千のメッセージをすばやく処理して確認し、さらにレビューすることができます。「 [Office 365 Advanced eDiscovery のクイックセットアップ」を](quick-setup-for-advanced-ediscovery.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p117">If a custodian or end user is assigned an Office 36 E5 license, you can examine up to 10,000 search results at once using Office 365 Advanced eDiscovery. If there are more than 10,000 email messages to review, you can divide the search query by date range and review each result individually as search results are sorted by date. In Advanced eDiscovery, you can tag search results using the **Label as** feature in the preview panel and filter the search result by the tag you labeled. This is helpful when you collaborate with a secondary reviewer. By using additional analytics tools in Advanced eDiscovery, such as optical character recognition, email threading, and predictive coding, you can quickly process and review thousands of messages and tag them for further review. See [Quick setup for Office 365 Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md).</span></span>

<span data-ttu-id="10dcb-p118">こぼれたデータが含まれている電子メールメッセージが見つかったら、メッセージの受信者に対して、外部で共有されているかどうかを確認します。さらにメッセージを追跡するには、メッセージのトレースログを使用できるように、送信者情報と日付範囲を収集することができます。これについては、[手順 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)で説明します。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p118">When you find an email message that contains spilled data, check the recipients of the message to determine if it was shared externally. To further trace an message, you can collect sender information and date range so you can use the message trace logs, which is described in [Step 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared).</span></span>

<span data-ttu-id="10dcb-p119">afer 検索結果を確認した後、他のユーザーと検索結果を共有して、第2のレビューを行うことができます。手順1でケースに割り当てたユーザーは、電子情報開示と高度な電子情報開示の両方でケースの内容を確認し、ケースの調査結果を承認することができます。実際のコンテンツをエクスポートせずにレポートを生成することもできます。このレポートを削除の証明として使用することもできます。これについては、[手順 8](#step-8-verify-provide-a-proof-of-deletion-and-audit)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p119">Afer you verified the search results, you may want to share your findings with others for a secondary review. People who you assigned to the case in Step 1 can review the case content in both eDiscovery and Advanced eDiscovery and approve case findings. You can also generate a report without exporting the actual content. You can also use this same report as a proof of deletion, which is described in [Step 8](#step-8-verify-provide-a-proof-of-deletion-and-audit).</span></span>
  
 <span data-ttu-id="10dcb-182">**統計レポートを生成するには、次のようにします。**</span><span class="sxs-lookup"><span data-stu-id="10dcb-182">**To generate a statistical report:**</span></span>
  
1. <span data-ttu-id="10dcb-183">電子情報開示ケースの [**検索**] ページに移動し、レポートを生成する検索をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10dcb-183">Go to the **Search** page in the eDiscovery case, and click the search that you want to generate a report for.</span></span> 
    
2. <span data-ttu-id="10dcb-184">フライアウトページで、[**その他の > エクスポートレポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10dcb-184">On the flyout page, click **More > Export report**.</span></span>
 
      <span data-ttu-id="10dcb-185">[レポートのエクスポート] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10dcb-185">The Export report page is displayed.</span></span>

    ![検索を選択し、[その他の > エクスポートレポート] をポップアップページでクリックします。](media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. <span data-ttu-id="10dcb-187">**認識できない形式のアイテムを含む、暗号化されている、またはその他の理由でインデックスが付けられ**ていないすべてのアイテムを選択して、[**レポートの生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10dcb-187">Select **All items, including ones that have unrecognized format, are encrypted, or weren’t indexed for other reasons** and then click **Generate report**.</span></span>

4. <span data-ttu-id="10dcb-p120">電子情報開示ケースで、[**エクスポート**] をクリックして、エクスポートジョブの一覧を表示します。作成したエクスポートジョブを表示するには、[**更新**] をクリックしてリストを更新する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p120">In the eDiscovery case, click **Export** to display the list of export jobs. You may have to click **Refresh** to update the list to display the export job you just created.</span></span>

5. <span data-ttu-id="10dcb-190">エクスポートジョブをクリックし、ポップアップページの [レポートの**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10dcb-190">Click the export job, and then click **Download** report on the flyout page.</span></span>
 
    ![[エクスポート] ページで、エクスポートをクリックしてから、[レポートのダウンロード] をクリックします。](media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

<span data-ttu-id="10dcb-p121">**エクスポートの概要**レポートには、結果がある場所の数と検索結果のサイズが含まれています。これを使用して、削除後に生成されたレポートと比較し、削除の証明として提供することができます。**結果**レポートには、件名、送信者、受信者、電子メールが開封された場合、各メッセージのサイズなど、検索結果の詳細な要約が表示されます。このレポートの詳細に実際にこぼれたデータが含まれている場合は、調査の完了時に結果の .csv ファイルを完全に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p121">The **Export Summary** report contains the number of locations found with results and the size of the search results. You can use this to compare with the report generated after deletion and provide as a proof of deletion. The **Results** report contains a more detailed summary of the search results, including the subject, sender, recipients, if the email was read, dates, and size of each message. If any of the details in this report contains that actual spilled data, be sure to permanently delete the Results.csv file when the investigation is complete.</span></span>

<span data-ttu-id="10dcb-196">レポートのエクスポートの詳細については、「[コンテンツ検索レポートをエクスポートする](export-a-content-search-report.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-196">For more information about exporting reports, see [Export a Content Search report](export-a-content-search-report.md).</span></span>
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a><span data-ttu-id="10dcb-197">手順 5: メッセージ追跡ログを使用して、こぼれたデータがどのように共有されているかを確認する</span><span class="sxs-lookup"><span data-stu-id="10dcb-197">Step 5: Use message trace log to check how spilled data was shared</span></span>

<span data-ttu-id="10dcb-p122">こぼれたデータを含む電子メールが共有されたかどうかをさらに詳しく調べるには、必要に応じて、手順4で収集した送信者情報および日付範囲情報を使用してメッセージ追跡ログを照会します。メッセージ追跡の保持期間は、リアルタイムデータの場合は30日、履歴データの場合は90日になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p122">To further investigate if email with spilled data was shared, you can optionally query the message trace logs with the sender information and the date range information that you gathered in Step 4. Note that the retention period for message trace is 30 days for real time data and 90 days for historical data.</span></span>
  
<span data-ttu-id="10dcb-p123">セキュリティ & コンプライアンスセンターでメッセージ追跡を使用するか、Exchange Online PowerShell で対応するコマンドレットを使用することができます。メッセージ追跡では、返されるデータの完全性について完全な保証が提供されない点に注意してください。メッセージ追跡の使用の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p123">You can use Message trace in the Security & Compliance Center or use the corresponding cmdlets in Exchange Online PowerShell. It's important to note that message tracing doesn't offer full guarantees on the completeness of data returned. For more information about using Message trace, see:</span></span> 
  
- [<span data-ttu-id="10dcb-203">Office 365 セキュリティ&amp;コンプライアンスセンターのメッセージ追跡</span><span class="sxs-lookup"><span data-stu-id="10dcb-203">Message trace in the Office 365 Security &amp; Compliance Center</span></span>](https://support.office.com/article/3e64f99d-ac33-4aba-91c5-9cb4ca476803.aspx)
    
- [<span data-ttu-id="10dcb-204">Office の新しいメッセージの追跡 365 &amp;セキュリティコンプライアンスセンター</span><span class="sxs-lookup"><span data-stu-id="10dcb-204">New Message Trace in Office 365 Security &amp; Compliance Center</span></span>](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a><span data-ttu-id="10dcb-205">手順 6: メールボックスを準備する</span><span class="sxs-lookup"><span data-stu-id="10dcb-205">Step 6: Prepare the mailboxes</span></span>

<span data-ttu-id="10dcb-p124">削除が必要なメッセージのみが検索結果に含まれることを確認して検証した後、 **DeleteContent**コマンドを実行するときに、手順7で使用する影響を受けるメールボックスの電子メールアドレスの一覧を収集する必要があります。また、永続的なデータを含むメールボックスで単一アイテムの回復が有効になっているかどうか、またはこれらのメールボックスが保留中であるかどうかによって、メールボックスを完全に削除する前にメールボックスを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p124">After you review and validate that the search results contains only the messages that must be deleted, you need to collect a list of the email addresses of the impacted mailboxes to use in Step 7 when you run the **Search-Mailbox -DeleteContent** command. You may also have to prepare the mailboxes before you can permanently delete email messages depending on whether single item recovery is enabled on the mailboxes that contain the spilled data or if any of those mailboxes are on hold.</span></span>
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a><span data-ttu-id="10dcb-208">データがこぼれているメールボックスのアドレスの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="10dcb-208">Get a list of addresses of mailboxes with spilled data</span></span>

<span data-ttu-id="10dcb-209">こぼれたデータを含むメールボックスの電子メールアドレスの一覧を収集する方法は2つあります。</span><span class="sxs-lookup"><span data-stu-id="10dcb-209">There are two ways to collect a list of email addresses of mailboxes with spilled data.</span></span>

<span data-ttu-id="10dcb-210">**オプション 1: データがこぼれているメールボックスのアドレスの一覧を取得する**</span><span class="sxs-lookup"><span data-stu-id="10dcb-210">**Option 1: Get a list of addresses of mailboxes with spilled data**</span></span>

1. <span data-ttu-id="10dcb-211">電子情報開示ケースを開き、[**検索**] ページに移動して、適切なコンテンツ検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="10dcb-211">Open the eDiscovery case, go to the **Search** page and select the appropriate content search.</span></span> 
    
2. <span data-ttu-id="10dcb-212">[フライアウト] ページで、[**結果の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10dcb-212">On the flyout page, click **View results**.</span></span>
    
3. <span data-ttu-id="10dcb-213">[**個々の結果**] ドロップダウンリストで、[**検索統計**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10dcb-213">In the **Individual results** drop down list, click **Search statistics**.</span></span>
    
4. <span data-ttu-id="10dcb-214">[**種類**] ドロップダウンリストで、[**上の場所**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10dcb-214">In the **Type** drop down list, click **Top locations**.</span></span>
    
    ![検索統計の [上位の場所] ページに検索結果が含まれているメールボックスの一覧を取得する](media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    <span data-ttu-id="10dcb-p125">検索結果が含まれるメールボックスの一覧が表示されます。検索クエリに一致する各メールボックス内のアイテムの数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p125">A list of mailboxes that contain search results is displayed. The number of items in each mailbox that match the search query is also displayed.</span></span>
    
5. <span data-ttu-id="10dcb-218">一覧の情報をコピーしてファイルに保存するか、[**ダウンロード**] をクリックして情報を CSV ファイルにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="10dcb-218">Copy the information in the list and save it to a file or click **Download** to download the information to a CSV file.</span></span> 
    
<span data-ttu-id="10dcb-219">**オプション 2: エクスポートレポートからメールボックスの場所を取得する**</span><span class="sxs-lookup"><span data-stu-id="10dcb-219">**Option 2: Get mailbox locations from the export report**</span></span>

<span data-ttu-id="10dcb-p126">[手順 4](#step-4-review-and-validate-case-findings)でダウンロードしたエクスポート概要レポートを開きます。レポートの最初の列に、各メールボックスの電子メールアドレスが [**場所**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p126">Open the Export Summary report that you downloaded in [Step 4](#step-4-review-and-validate-case-findings). In the first column in the report, the email address of each mailbox is listed under **Locations**.</span></span>
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a><span data-ttu-id="10dcb-222">メールボックスを準備して、こぼれたデータを削除できるようにする</span><span class="sxs-lookup"><span data-stu-id="10dcb-222">Prepare the mailboxes so you can delete the spilled data</span></span>

<span data-ttu-id="10dcb-p127">単一アイテムの回復が有効になっている場合、またはメールボックスが保持されている場合、完全に削除された (パージされた) メッセージは、回復可能なアイテムフォルダーに保持されます。こぼれたデータを削除する前に、既存のメールボックスの構成を確認し、単一アイテムの回復を無効にして、ホールドまたは Office 365 アイテム保持ポリシーを削除する必要があります。一度に1つのメールボックスを準備してから、別のメールボックスで同じコマンドを実行することも、複数のメールボックスを同時に準備するための PowerShell スクリプトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p127">If single item recovery is enabled or if a mailbox is placed on hold, a permanently deleted (purged) message will be retained in Recoverable Items folder. So before you can purge spilled data, you need to check the existing mailbox configurations and disable single item recovery and remove any hold or Office 365 retention policy. Keep in mind that you can prepare one mailbox at a time, and then run the same command on different mailboxes or create a PowerShell script to prepare multiple mailboxes at the same time.</span></span>

- <span data-ttu-id="10dcb-226">単一アイテムの回復が有効になっているかどう[](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox)か、またはメールボックスが保留になっているかどうかを確認する方法、またはメールボックスが保持されているかどうかを確認する方法については、「手順 1: メールボックスに関する情報を収集する」を参照してください。アイテム保持ポリシー。</span><span class="sxs-lookup"><span data-stu-id="10dcb-226">See "Step 1: Collect information about the mailbox" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) for instructions about how to check if single item recovery is enabled or if the mailbox is placed on hold or it's assigned to a retention policy.</span></span> 
    
- <span data-ttu-id="10dcb-227">単一アイテムの回復を無効にする手順については[、「クラウドベースのメールボックスの回復可能なアイテムフォルダーのアイテムを削除する](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox)」の「手順 2: メールボックスを準備する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-227">See "Step 2: Prepare the mailbox" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) for instructions about disabling single item recovery.</span></span> 
    
- <span data-ttu-id="10dcb-228">メールボックスから保留またはアイテム保持ポリシーを削除する方法については、「手順 3:[クラウドベースのメールボックスの回復可能なアイテムフォルダーのアイテムを削除](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox)する」の「メールボックスからすべての保留リストを削除する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-228">See "Step 3: Remove all holds from the mailbox" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) for instructions about how to remove a hold or retention policy from a mailbox.</span></span> 

- <span data-ttu-id="10dcb-229">任意の種類の保留を解除した後にメールボックスに設定されている遅延ホールドを削除する手順については、「手順 4:[クラウドベースのメールボックスの回復可能なアイテムフォルダーのアイテム](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox)を削除する」の「メールボックスから遅延ホールドを削除する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-229">See "Step 4: Remove the delay hold from the mailbox" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox) for instructions about removing the delay hold that is placed on the mailbox after any type of hold is removed.</span></span>
    
 <span data-ttu-id="10dcb-p128">**重要:** 保留またはアイテム保持ポリシーを削除する前に、レコード管理または法務部門に確認してください。組織には、保留中のメールボックスとデータ流出インシデントのどちらを優先するかを定義するポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p128">**Important:** Check with your records management or legal departments before removing a hold or retention policy. Your organization may have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
<span data-ttu-id="10dcb-p129">こぼれたデータが完全に削除されたことを確認したら、必ずメールボックスを以前の構成に戻します。詳細については、[手順 7](#step-7-permanently-delete-the-spilled-data)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p129">Be sure to revert the mailbox to previous configurations after you verify that the spilled data has been permanently deleted. See the details in [Step 7](#step-7-permanently-delete-the-spilled-data).</span></span>

## <a name="step-7-permanently-delete-the-spilled-data"></a><span data-ttu-id="10dcb-234">手順 7: こぼれたデータを完全に削除する</span><span class="sxs-lookup"><span data-stu-id="10dcb-234">Step 7: Permanently delete the spilled data</span></span>

<span data-ttu-id="10dcb-p130">手順6で収集して準備したメールボックスの場所と、手順3で作成して調整した検索クエリを使用して、こぼれたデータが含まれている電子メールメッセージを検索することで、そのデータを完全に削除できます。前述したように、次の手順を使用してメッセージを削除するには、Exchange Online のメールボックスのインポートの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p130">Using the mailbox locations that you collected and prepared in Step 6 and the search query that was created and refined in Step 3 to find email messages that contain the spilled data, you can now permanently delete the spilled data. As previously explained, you have to be assigned the Mailbox Import Export role in Exchange Online to delete messages using the following procedure.</span></span>
  
1. <span data-ttu-id="10dcb-237">[Exchange Online PowerShell に接続します](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="10dcb-237">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>
    
2. <span data-ttu-id="10dcb-238">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="10dcb-238">Run the following command:</span></span>
    
    ```
    Search-Mailbox -Identity <mailbox identity> -SearchDumpster -DeleteContent $true -SearchQuery <search query>
    ```
  
3. <span data-ttu-id="10dcb-239">id パラメーターの値を置換して、こぼれたデータを含む各メールボックスに対して前のコマンドを再度実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="10dcb-239">Re-run the previous command for each mailbox that contains the spilled data, by replacing the value for the Identity parameter; for example:</span></span>

    ```
    Search-Mailbox -Identity sarad@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

    ```
    Search-Mailbox -Identity janets@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

   ```
   Search-Mailbox -Identity pilarp@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
   ```
  
<span data-ttu-id="10dcb-240">前述したように、 [powershell スクリプト](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6)を作成し、メールボックスの一覧に対して実行することで、スクリプトによって各メールボックス内のこぼれたデータが削除されるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="10dcb-240">As previously stated, you can also create a [powershell script](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6) and run it against a list of mailboxes so that the script deletes the spilled data in each mailbox.</span></span>
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a><span data-ttu-id="10dcb-241">手順 8: 確認し、削除の証明を提供し、監査を行う</span><span class="sxs-lookup"><span data-stu-id="10dcb-241">Step 8: Verify, provide a proof of deletion, and audit</span></span>

<span data-ttu-id="10dcb-p131">データ流出インシデントを管理するワークフローの最後の手順は、電子情報開示ケースに移動し、そのデータを削除するために使用したものと同じ検索クエリを再実行して、結果が得られなかったことを確認することです。e が返されます。こぼれたデータが完全に削除されたことを確認した後、レポートをエクスポートして、削除の証明として (元のレポートと共に) レポートを含めることができます。その場合は、その[ケースを閉じる](ediscovery-cases.md#optional-step-9-close-a-case)ことができます。これにより、後で参照した場合に再び開くことができます。さらに、メールボックスを以前の状態に戻したり、こぼれたデータを検索するために使用される検索クエリを削除したり、データ流出インシデントを管理するときに実行されるタスクの監査記録を検索したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p131">The final step in the workflow to manage a data spillage incident is to verify that the spilled data was permanently removed from the mailbox by going to the eDiscovery case and re-running the same search query that was used to delete that data to confirm that no results are returned. After you confirm the spilled data has been permanently removed, you can export a report and include it (along with the original report) as a proof of deletion. Then you can [close the case](ediscovery-cases.md#optional-step-9-close-a-case), which will allow you to re-open it if you have refer to it in the future. Additionally, you can also revert mailboxes to their previous state, delete the search query used to find the spilled data, and search for auditing records of tasks performed when managing the data spillage incident.</span></span> 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a><span data-ttu-id="10dcb-246">メールボックスを以前の状態に戻す</span><span class="sxs-lookup"><span data-stu-id="10dcb-246">Reverting the mailboxes to their previous state</span></span>

<span data-ttu-id="10dcb-p132">作業中のデータが削除される前にメールボックスを準備するために、手順6でメールボックス構成を変更した場合は、それらを以前の状態に戻す必要があります。「[保持中のクラウドベースのメールボックスの回復可能なアイテムフォルダーの削除アイテム](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state)」の「手順 6: メールボックスを以前の状態に戻す」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p132">If you changed any mailbox configuration in Step 6 to prepare the mailboxes before the spilled data was deleted, you will need to revert them to their previous state. See "Step 6: Revert the mailbox to its previous state" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state).</span></span>
  
### <a name="deleting-the-search-query"></a><span data-ttu-id="10dcb-249">検索クエリを削除する</span><span class="sxs-lookup"><span data-stu-id="10dcb-249">Deleting the search query</span></span>

<span data-ttu-id="10dcb-250">手順3で作成して使用した検索クエリのキーワードに、実際にこぼれたすべてのデータが含まれている場合は、検索クエリを削除して、さらにデータを流出しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-250">If the keywords in the search query that you created and used in Step 3 contains some of all of the actual spilled data, you should delete the search query to prevent further data spillage.</span></span>
  
1. <span data-ttu-id="10dcb-251">セキュリティ & コンプライアンスセンターで、電子情報開示ケースを開き、[**検索**] ページに移動して、適切なコンテンツ検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="10dcb-251">In the Security & Compliance Center, open the eDiscovery case, go to the **Search** page, and select the appropriate content search.</span></span>
    
2. <span data-ttu-id="10dcb-252">フライアウトページで、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10dcb-252">On the flyout page, click **Delete**.</span></span>

    ![検索を選択し、フライアウトページで [削除] をクリックします。](media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a><span data-ttu-id="10dcb-254">データ流出調査プロセスの監査</span><span class="sxs-lookup"><span data-stu-id="10dcb-254">Auditing the data spillage investigation process</span></span>

<span data-ttu-id="10dcb-p133">調査中に実行された電子情報開示アクティビティについては、Office 365 監査ログを検索することができます。また、監査ログを検索して、 **DeleteContent**コマンドを実行して、こぼれたデータを削除したときに作成された監査レコードを取得することもできます。詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-p133">You can search the Office 365 audit log for the eDiscovery activities that were performed during the investigation. You can also search the audit log to return the audit records that were created when you ran the **Search-Mailbox -DeleteContent** command to delete the spilled data. For more information, see:</span></span>

- <span data-ttu-id="10dcb-258">&amp;</span><span class="sxs-lookup"><span data-stu-id="10dcb-258">[Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md)</span></span>

- [<span data-ttu-id="10dcb-259">Office 365 監査ログで電子情報開示アクティビティを検索する</span><span class="sxs-lookup"><span data-stu-id="10dcb-259">Search for eDiscovery activities in the Office 365 audit log</span></span>](search-for-ediscovery-activities-in-the-audit-log.md)

- <span data-ttu-id="10dcb-260">Exchange Online のコマンドレットの実行に関連する監査レコードを検索する方法については、「 [Office 365 セキュリティ & コンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md#audited-activities)」の「監査対象のアクティビティ-Exchange 管理者監査ログ」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dcb-260">See the "Audited activities - Exchange admin audit log " section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities) for guidance about how to search for audit records related to running cmdlets in Exchange Online.</span></span>
  

