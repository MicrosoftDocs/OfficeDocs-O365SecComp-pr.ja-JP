---
title: 電子的証拠開示ソリューション シリーズ データこぼしたシナリオの検索と削除
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: 管理し、組織内のデータこぼしたインシデントに対応するには、Office 365 の電子的証拠開示と検索ツールを使用します。
ms.openlocfilehash: 2bf17923408bd5cf8325d27a38595331d169906f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531657"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a><span data-ttu-id="c531c-103">電子的証拠開示ソリューション シリーズ: データこぼしたシナリオの検索と削除</span><span class="sxs-lookup"><span data-stu-id="c531c-103">eDiscovery solution series: Data spillage scenario - Search and purge</span></span>

 <span data-ttu-id="c531c-p101">**データこぼしたとはなぜ重要なのですか?** こぼしたのデータは、機密性の高いドキュメントが信頼されていない環境にリリースされたときです。データこぼしたのインシデントが検出されると、することが重要、こぼしたの場所とサイズを迅速に評価、囲み、ユーザー アクティビティを確認してシステムからこぼれたデータを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="c531c-p101">**What is data spillage and why should you care?** Data spillage is when a confidential document is released into an untrusted environment. When a data spillage incident is detected, it's important to quickly assess the size and locations of the spillage, examine user activities around it,  and then permanently purge the spilled data from the system.</span></span> 
  
## <a name="data-spillage-scenario"></a><span data-ttu-id="c531c-107">こぼしたシナリオのデータ</span><span class="sxs-lookup"><span data-stu-id="c531c-107">Data spillage scenario</span></span>

<span data-ttu-id="c531c-p102">Contoso の潜在顧客の情報セキュリティ責任者がいます。従業員知らずに共有されている機密性の高いドキュメント電子メールを通じて複数のユーザーとデータのこぼした状況が通知されます。このドキュメントの内部と外部の受信者を迅速に評価する必要があります。識別されると、その他の調査官の確認、および Office 365 のデータを完全に削除するとケースの結果を共有したいと思います。調査が完了した後の将来の参照を完全に削除し、他のケースの詳細の証拠を使用してレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="c531c-p102">You’re a lead information security officer at Contoso. You are informed of a data spillage situation where an employee unknowingly shared a highly confidential document with multiple people through email. You want to quickly assess who received this document internally and externally. Once identified, you would like to share case findings with other investigators to review, and then permanently remove the data from Office 365. After the investigation is complete, you want to generate a report with the evidence of permanent removal and other case details for any future reference.</span></span>
  
### <a name="scope-of-this-article"></a><span data-ttu-id="c531c-113">この資料の範囲</span><span class="sxs-lookup"><span data-stu-id="c531c-113">Scope of this article</span></span>

<span data-ttu-id="c531c-p103">このドキュメントでは、アクセスまたは回復可能ではないように、Office 365 からメッセージを完全に削除する方法の手順の一覧を提供します。メッセージを削除する、それを回復可能な削除済みアイテムの保存期間が終了するまで、[検索して Office 365 の組織内の電子メール メッセージを削除](search-for-and-delete-messages-in-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p103">This document provides a list of instructions on how to permanently remove a message from Office 365 so that it's not accessible or recoverable. To delete a message and make it recoverable until the deleted item retention period expires, see [Search for and delete email messages in your Office 365 organization](search-for-and-delete-messages-in-your-organization.md).</span></span>
  
## <a name="workflow-for-managing-data-spillage-incidents"></a><span data-ttu-id="c531c-116">こぼしたインシデントのデータを管理するためのワークフロー</span><span class="sxs-lookup"><span data-stu-id="c531c-116">Workflow for managing data spillage incidents</span></span>

<span data-ttu-id="c531c-117">データのこぼしたインシデントを管理します。</span><span class="sxs-lookup"><span data-stu-id="c531c-117">Here's a how to manage a data spillage incident:</span></span>

![こぼしたインシデントのデータを管理するための 8 ステップのワークフロー](media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[<span data-ttu-id="c531c-119">(省略可能)手順 1: 大文字と小文字をアクセスし、コンプライアンスの境界を設定したを管理します。</span><span class="sxs-lookup"><span data-stu-id="c531c-119">(Optional) Step 1: Manage who can access the case and set compliance boundaries</span></span>](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[<span data-ttu-id="c531c-120">電子的証拠開示のサポート案件を作成する手順 2。</span><span class="sxs-lookup"><span data-stu-id="c531c-120">Step 2: Create an eDiscovery case</span></span>](#step-2-create-an-ediscovery-case)<br/>
[<span data-ttu-id="c531c-121">こぼれたデータの手順 3: 検索</span><span class="sxs-lookup"><span data-stu-id="c531c-121">Step 3: Search for the spilled data</span></span>](#step-3-search-for-the-spilled-data)<br/>
[<span data-ttu-id="c531c-122">手順 4: を確認し、ケースの調査結果を検証します。</span><span class="sxs-lookup"><span data-stu-id="c531c-122">Step 4: Review and validate case findings</span></span>](#step-4-review-and-validate-case-findings)<br/>
[<span data-ttu-id="c531c-123">こぼれたがどのようにデータを確認するトレース ログの共有メッセージを使用して、手順 5。</span><span class="sxs-lookup"><span data-stu-id="c531c-123">Step 5: Use message trace log to check how spilled data was shared</span></span>](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[<span data-ttu-id="c531c-124">手順 6: メールボックスを準備します。</span><span class="sxs-lookup"><span data-stu-id="c531c-124">Step 6: Prepare the mailboxes</span></span>](#step-6-prepare-the-mailboxes)<br/>
[<span data-ttu-id="c531c-125">こぼれたデータを完全に削除する手順 7。</span><span class="sxs-lookup"><span data-stu-id="c531c-125">Step 7: Permanently delete the spilled data</span></span>](#step-7-permanently-delete-the-spilled-data)<br/>
[<span data-ttu-id="c531c-126">手順 8: ことを確認、削除、テストを行うし、監査</span><span class="sxs-lookup"><span data-stu-id="c531c-126">Step 8: Verify, provide a proof of deletion, and audit</span></span>](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a><span data-ttu-id="c531c-127">開始する前に知っておく</span><span class="sxs-lookup"><span data-stu-id="c531c-127">Things to know before you start</span></span>

- <span data-ttu-id="c531c-p104">保留中のメールボックスがある場合、削除済みのメッセージは、保存期間の期限が切れるか、保留を解除するまで、回復可能なアイテム] フォルダーに残ります。[手順 6](#step-6-prepare-the-mailboxes)では、メールボックスから保持を削除する方法について説明します。保留リストを削除する前に、レコード管理または法務部門に確認してください。上にメールボックスを保持するかどうかを定義するポリシーを持つ組織もあります。 またはデータのこぼしたインシデントが優先します。</span><span class="sxs-lookup"><span data-stu-id="c531c-p104">When a mailbox is on hold, a deleted message remains in the Recoverable Items folder until the retention period expires or the hold is released. [Step 6](#step-6-prepare-the-mailboxes) describes how to remove hold from the mailboxes. Check with your records management or legal departments before removing the hold. Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
    
- <span data-ttu-id="c531c-p105">どのユーザーのメールボックスを管理するには、データのこぼした調査官で検索し、大文字と小文字にアクセスできるユーザーを管理、コンプライアンスの境界を設定し、[手順 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)で説明するカスタムの役割グループを作成できます。これを行うには、組織の管理役割グループのメンバーであるか、役割の管理役割を割り当てる必要があります。場合、または、コンプライアンスの境界のセットが既に組織内の管理者に、手順 1 を省略することができます。</span><span class="sxs-lookup"><span data-stu-id="c531c-p105">To control which user mailboxes an data spillage investigator can search and manage who can access the case, you can set up compliance boundaries and create a custom role group, which is described in [Step 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries). To do this, you have to be a member of the Organization Management role group or be assigned the role management role. If you or in administrator in your organization has already set compliance boundaries, you can skip Step 1.</span></span>
    
- <span data-ttu-id="c531c-p106">サポート案件を作成するには、電子的証拠開示マネージャーの役割グループのメンバーであるか、ケース管理の役割が割り当てられているカスタムの役割グループのメンバーであるください。メンバーでない場合は[、電子的証拠開示マネージャーのロール グループを追加](assign-ediscovery-permissions.md)するのには、Office 365 の管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p106">To create a case, you must be a member of the eDiscovery Manager role group or be a member of a custom role group that's assigned the Case Management role. If you're not a member, ask an Office 365 administrator to [add you to the eDiscovery manager role group](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="c531c-p107">組織にコピーされているデータを削除するには、Exchange オンライン PowerShell で[検索メールボックス DeleteContent](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps)コマンドを使用する必要があります。また、 *DeleteContent*パラメーターを使用するをもする必要がある Exchange Online のメールボックスのインポート エクスポートの役割が割り当てられている役割グループのメンバーであります。[役割グループの管理](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx)の「ロール グループにロールを追加する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p107">To delete data that's spilled into your organization, you need to use the [Search-Mailbox -DeleteContent](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps) command in Exchange Online PowerShell. Additionally, to use the  *DeleteContent* parameter, you also have to be a member of a role group in Exchange Online that's assigned the Mailbox Import Export role. See the "Add a role to a role group" section in [Manage role groups](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx).</span></span>
    
- <span data-ttu-id="c531c-p108">Office 365 の監査ログの電子的証拠開示活動を検索するには手順 8 で、監査する必要がありますオンにする組織。過去 90 日以内に実行された活動を検索できます。有効にして、監査を使用する方法の詳細については、手順 8[データこぼした調査プロセスを監査](#auditing-the-data-spillage-investigation-process)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p108">To search the Office 365 audit log eDiscovery activities in Step 8, auditing must be turned on for your organization. You can search for activities that were performed within the last 90 days. To learn more about how to enable and use auditing, see the [Auditing the data spillage investigation process](#auditing-the-data-spillage-investigation-process) section in Step 8.</span></span> 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a><span data-ttu-id="c531c-143">(省略可能)手順 1: 大文字と小文字をアクセスし、コンプライアンスの境界を設定したを管理します。</span><span class="sxs-lookup"><span data-stu-id="c531c-143">(Optional) Step 1: Manage who can access the case and set compliance boundaries</span></span>

<span data-ttu-id="c531c-p109">実習、組織によっては、データこぼしたのインシデントを調査し、コンプライアンスの境界を設定するために使用する電子的証拠開示の場合にアクセスできるユーザーを制御する必要があります。これを行う最も簡単な方法では、調査官を Office 365 のセキュリティとコンプライアンス センター内の既存の役割グループのメンバーとして追加し、電子的証拠開示の場合のメンバーとしての役割グループに追加します。組み込みの電子的証拠開示の役割グループと、電子的証拠開示の場合にメンバーを追加する方法についてを参照してください[Office 365 のセキュリティ、電子的証拠開示のアクセス許可を割り当てる&amp;コンプライアンス センター](assign-ediscovery-permissions.md)です。</span><span class="sxs-lookup"><span data-stu-id="c531c-p109">Depending on your organizational practice, you need to control who can access the eDiscovery case used to investigate a data spillage incident and set up compliance boundaries. The easiest way to do this is to add investigators as members of an existing role group in the Office 365 Security & Compliance Center and then add the role group as a member of the eDiscovery case. For information about the built-in eDiscovery role groups and how to add members to an eDiscovery case, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
<span data-ttu-id="c531c-p110">組織のニーズに合わせて新しい役割グループを作成することもできます。などのデータにアクセスし、共同作業を行うすべてのデータのこぼした場合に組織内のこぼした調査官のグループをする可能性があります。「データこぼした調査官」の役割グループを作成する、(エクスポート RMS の復号化レビュー プレビュー、コンプライアンス検索、およびサポート案件の管理) は、適切なロールを割り当て、グループに追加するデータのこぼした調査官、ロール、追加し、でこれを行う、データこぼした電子的証拠開示のサポート案件のメンバーとしての役割のグループです。これを行う方法についての詳細な[電子的証拠開示の調査では、Office 365 のコンプライアンスの境界の設定](set-up-compliance-boundaries.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p110">You can also create a new role group that aligns with your organizational needs. For example, you might want a group of data spillage investigators in the organization to access and collaborate on all data spillage cases. You can do this by creating a "Data Spillage Investigator" role group, assigning the appropriate roles (Export, RMS Decrypt, Review, Preview, Compliance Search, and Case Management), adding the data spillage investigators to the role group, and then adding the role group as a member of the data spillage eDiscovery case. See [Set up compliance boundaries for eDiscovery investigations in Office 365](set-up-compliance-boundaries.md) for detailed instructions on how to do this.</span></span> 
  
## <a name="step-2-create-an-ediscovery-case"></a><span data-ttu-id="c531c-151">電子的証拠開示のサポート案件を作成する手順 2。</span><span class="sxs-lookup"><span data-stu-id="c531c-151">Step 2: Create an eDiscovery case</span></span>

<span data-ttu-id="c531c-p111">電子的証拠開示のサポート案件には、こぼした調査データを管理する効果的な方法が用意されています。手順 1 で作成した役割グループにメンバーを追加、新しい電子的証拠開示の場合のメンバーとしての役割グループを追加するこぼれたデータを検索、共有、ケースの状態を追跡するレポートをエクスポートするのには反復的な検索を実行して、c の詳細を参照ase が必要な場合です。データこぼしたのインシデントを使用する電子的証拠開示の場合に名前付け規則を確立することを検討し、場合に大文字の名前と説明を検索しを参照してください、将来的に必要な場合は、できるだけ多くの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c531c-p111">An eDiscovery case provides an effective way to manage your data spillage investigation. You can add members to the role group that you created in Step 1, add the role group as a member of new a eDiscovery case, perform iterative searches to find the spilled data, export a report to share, track the status of the case, and then refer back to the details of the case if needed. Consider establishing a naming convention for eDiscovery cases used for data spillage incidents, and provide as much information as you can in the case name and description so you can locate and refer to in the future if necessary.</span></span>
  
<span data-ttu-id="c531c-p112">新しいサポート案件を作成するに、セキュリティで電子的証拠開示を使用することができます&amp;コンプライアンス センターです。[電子的証拠開示の場合](ediscovery-cases.md#step-2-create-a-new-case)で「新しいケースを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p112">To create a new case, you can use eDiscovery in the Security &amp; Compliance Center. See "Create a new case" in [eDiscovery Cases in the Office 365 Security & Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
  
## <a name="step-3-search-for-the-spilled-data"></a><span data-ttu-id="c531c-157">こぼれたデータの手順 3: 検索</span><span class="sxs-lookup"><span data-stu-id="c531c-157">Step 3: Search for the spilled data</span></span>

<span data-ttu-id="c531c-p113">ケースと管理アクセスを作成したら、これでこぼれたデータを検索し、こぼれたデータが含まれているメールボックスを識別する繰り返しを検索する、大文字と小文字を使用できます。[手順 7](#step-7-permanently-delete-the-spilled-data)で同じメッセージを削除するのには電子メール メッセージを検索するために使用するのと同じ検索クエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="c531c-p113">Now that you've created a case and managed access, you can use the case to iteratively search to find the spilled data and identify the mailboxes that contain the spilled data. You will use the same search query that you used to find the email messages to delete those same messages in [Step 7](#step-7-permanently-delete-the-spilled-data).</span></span>
  
<span data-ttu-id="c531c-160">検索をコンテンツを作成するのには、電子的証拠開示のサポート案件に関連付けられている、[電子的証拠開示の場合](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case)の「の作成とコンテンツの検索サポート案件に関連付けられている実行」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-160">To create a content searches associated with an eDiscovery case, see "Create and run a Content Search associated with a case" in [eDiscovery Cases in the Office 365 Security & Compliance Center](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case).</span></span>
  
 <span data-ttu-id="c531c-p114">**重要な:** 検索クエリで使用するキーワードの検索を実行している実際のこぼれたデータがあります。などのキーワードを検索すると、it を使用し、社会保障番号を含むドキュメントを検索する場合は、さらにこぼしたを回避するには、後でクエリを削除してください。手順 8 で[検索クエリを削除する](#deleting-the-search-query)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p114">**Important:** The keywords that you use in the search query may contain the actual spilled data that you're searching for. For example, if you searching for documents containing a social security number and you use the it as search keyword, you must delete the query afterwards to avoid further spillage. See [Deleting the search query](#deleting-the-search-query) in Step 8.</span></span> 
  
## <a name="step-4-review-and-validate-case-findings"></a><span data-ttu-id="c531c-164">手順 4: を確認し、ケースの調査結果を検証します。</span><span class="sxs-lookup"><span data-stu-id="c531c-164">Step 4: Review and validate case findings</span></span>

<span data-ttu-id="c531c-p115">コンテンツの検索を作成した後は、確認し、検索が結果を削除する必要がある電子メール メッセージのだけで構成されることを確認であることを検証する必要があります。コンテンツの検索、データこぼしたを防ぐために検索結果をエクスポートすることがなく 1,000 個の電子メール メッセージのランダムなサンプリングをプレビューできます。詳細を参照することでプレビュー制限の[コンテンツの検索では、Office 365 のセキュリティの制限&amp;コンプライアンス センター](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="c531c-p115">After you create a content search, you need to review and validate that the search results and verify that they consist only of the email messages that must be deleted. In a content search, you can preview a random sampling of 1,000 email messages without exporting the search results to avoid further data spillage. You can read more about the preview limitations at [Limits for Content Search in the Office 365 Security &amp; Compliance Center](limits-for-content-search.md).</span></span>
  
<span data-ttu-id="c531c-p116">あれば 1,000 を超えるメールボックスまたは電子メール メッセージを 100 個を超えるメールボックスを確認するのにあたり、複数の検索キーワードを追加または日付の範囲または送信者と受信者などの条件を使用して最初の検索に分割して各検索の結果を確認個別にします。[手順 7](#step-7-permanently-delete-the-spilled-data)でメッセージを削除するときに使用するすべての検索クエリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p116">If you have more than 1,000 mailboxes or more than 100 email messages per mailbox to review, you can divide the initial search into multiple searches by using additional keywords or conditions such as date range or sender/recipient and review the results of each search individually. Make sure to note down all search queries to use when you delete messages in [Step 7](#step-7-permanently-delete-the-spilled-data).</span></span>

<span data-ttu-id="c531c-p117">管理者やエンドユーザーが Office 36 E5 のライセンスを割り当てられている場合は、電子的証拠開示の Office 365 の詳細設定を使用して、一度に最大 10000 個までの検索結果を調べることができます。確認するのには、1万人以上の電子メール メッセージがある場合は、日付の範囲で検索クエリを分割し、検索の結果は日付順に並べ替えられます。 として個別にそれぞれの結果を確認できます。高度な電子的証拠開示は、プレビュー パネルで**ラベルとして**の機能を使用して検索結果にタグ付けし、ラベルをタグで検索結果をフィルター処理できます。セカンダリの校閲者と共同作業をする場合に便利です。高度な電子的証拠開示、光学式文字認識、電子メールのスレッド、および予測のコーディングなどの他の分析ツールを使用して、迅速に処理し、何千ものメッセージを確認してさらなるレビューのタグを付ける。[Office 365 の高度な証拠開示のためのクイック セットアップ](quick-setup-for-advanced-ediscovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p117">If a custodian or end user is assigned an Office 36 E5 license, you can examine up to 10,000 search results at once using Office 365 Advanced eDiscovery. If there are more than 10,000 email messages to review, you can divide the search query by date range and review each result individually as search results are sorted by date. In Advanced eDiscovery, you can tag search results using the **Label as** feature in the preview panel and filter the search result by the tag you labeled. This is helpful when you collaborate with a secondary reviewer. By using additional analytics tools in Advanced eDiscovery, such as optical character recognition, email threading, and predictive coding, you can quickly process and review thousands of messages and tag them for further review. See [Quick setup for Office 365 Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md).</span></span>

<span data-ttu-id="c531c-p118">こぼれたデータを含む電子メール メッセージを検索するときは、外部で共有したかどうかを確認するメッセージの受信者を確認してください。さらにトレースをメッセージを収集できます送信者情報と日付の範囲[手順 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)で説明しますが、メッセージのトレース ログを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c531c-p118">When you find an email message that contains spilled data, check the recipients of the message to determine if it was shared externally. To further trace an message, you can collect sender information and date range so you can use the message trace logs, which is described in [Step 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared).</span></span>

<span data-ttu-id="c531c-p119">検索結果を確認するが、第 2 のレビューのため、他のユーザーと、結果を共有する場合します。手順 1 で大文字と小文字を割り当てられているユーザーでは、電子的証拠開示と高度な電子的証拠開示の両方でサポート ・ リクエストの内容を確認でき、サポート ・ リクエストの結果を承認することができます。実際のコンテンツをエクスポートすることがなくレポートを生成することもできます。この同じレポートは、[手順 8](#step-8-verify-provide-a-proof-of-deletion-and-audit)で説明しますが、削除の証明としても使えます。</span><span class="sxs-lookup"><span data-stu-id="c531c-p119">Afer you verified the search results, you may want to share your findings with others for a secondary review. People who you assigned to the case in Step 1 can review the case content in both eDiscovery and Advanced eDiscovery and approve case findings. You can also generate a report without exporting the actual content. You can also use this same report as a proof of deletion, which is described in [Step 8](#step-8-verify-provide-a-proof-of-deletion-and-audit).</span></span>
  
 <span data-ttu-id="c531c-182">**統計レポートを生成します。**</span><span class="sxs-lookup"><span data-stu-id="c531c-182">**To generate a statistical report:**</span></span>
  
1. <span data-ttu-id="c531c-183">電子的証拠開示の場合、[**検索**] ページに移動し、レポートを生成する検索] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c531c-183">Go to the **Search** page in the eDiscovery case, and click the search that you want to generate a report for.</span></span> 
    
2. <span data-ttu-id="c531c-184">[ポップアップ] ページをクリックして**より > レポートをエクスポートする**です。</span><span class="sxs-lookup"><span data-stu-id="c531c-184">On the flyout page, click **More > Export report**.</span></span>
 
      <span data-ttu-id="c531c-185">レポートのエクスポート] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c531c-185">The Export report page is displayed.</span></span>

    ![検索を選択し、[詳細] をクリックして > [ポップアップ] ページで、レポートをエクスポートします。](media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. <span data-ttu-id="c531c-187">**認識できない形式があるものなど、すべてのアイテムが暗号化されているか他の理由によりインデックスが作成されませんでした**を選択し、**レポートの生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c531c-187">Select **All items, including ones that have unrecognized format, are encrypted, or weren’t indexed for other reasons** and then click **Generate report**.</span></span>

4. <span data-ttu-id="c531c-p120">電子的証拠開示の場合、**エクスポート**するエクスポート ジョブの一覧を表示をクリックします。**更新**を作成したエクスポート ジョブを表示するリストを更新する] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c531c-p120">In the eDiscovery case, click **Export** to display the list of export jobs. You may have to click **Refresh** to update the list to display the export job you just created.</span></span>

5. <span data-ttu-id="c531c-190">エクスポート ジョブをクリックし、[ポップアップ] ページで、レポートの**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c531c-190">Click the export job, and then click **Download** report on the flyout page.</span></span>
 
    ![[エクスポート] ページで [エクスポート] をクリックし、[レポートのダウンロード] をクリックし、](media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

<span data-ttu-id="c531c-p121">**エクスポートの概要**レポートには、見つかった結果および検索結果のサイズと位置の数が含まれています。削除後に生成されたレポートと比較し、削除の証拠として提供するには、これを使用します。**結果**レポートには、件名、送信者、受信者の電子メールが読み取られた場合、日付、および各メッセージのサイズを含む、検索結果の詳細な概要が含まれています。こぼれたデータを実際にこのレポートの詳細のいずれかの場合は、必ず調査が完了したときに、Results.csv ファイルを完全に削除してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p121">The **Export Summary** report contains the number of locations found with results and the size of the search results. You can use this to compare with the report generated after deletion and provide as a proof of deletion. The **Results** report contains a more detailed summary of the search results, including the subject, sender, recipients, if the email was read, dates, and size of each message. If any of the details in this report contains that actual spilled data, be sure to permanently delete the Results.csv file when the investigation is complete.</span></span>

<span data-ttu-id="c531c-196">レポートをエクスポートする方法の詳細については、[コンテンツの検索レポートをエクスポートする](export-a-content-search-report.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-196">For more information about exporting reports, see [Export a Content Search report](export-a-content-search-report.md).</span></span>
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a><span data-ttu-id="c531c-197">こぼれたがどのようにデータを確認するトレース ログの共有メッセージを使用して、手順 5。</span><span class="sxs-lookup"><span data-stu-id="c531c-197">Step 5: Use message trace log to check how spilled data was shared</span></span>

<span data-ttu-id="c531c-p122">さらに調査するにはこぼれたデータを電子メールで共有されていた場合は、必要に応じて送信者情報と手順 4 で収集した日付の範囲の情報を持つメッセージのトレース ログを照会できます。メッセージ トレースの保存期間はリアルタイム データと履歴データの 90 日の 30 日間であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p122">To further investigate if email with spilled data was shared, you can optionally query the message trace logs with the sender information and the date range information that you gathered in Step 4. Note that the retention period for message trace is 30 days for real time data and 90 days for historical data.</span></span>
  
<span data-ttu-id="c531c-p123">コマンドレットを使用して、対応する Exchange オンライン PowerShell またはメッセージのトレースを使用して、セキュリティとコンプライアンスの中心にできます。メッセージ トレースは返されるデータの完全性を完全に保証を提供していることに注意する必要があります。メッセージ トレースの使用に関する詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p123">You can use Message trace in the Security & Compliance Center or use the corresponding cmdlets in Exchange Online PowerShell. It's important to note that message tracing doesn't offer full guarantees on the completeness of data returned. For more information about using Message trace, see:</span></span> 
  
- [<span data-ttu-id="c531c-203">メッセージ トレースには、Office 365 のセキュリティ&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="c531c-203">Message trace in the Office 365 Security &amp; Compliance Center</span></span>](https://support.office.com/article/3e64f99d-ac33-4aba-91c5-9cb4ca476803.aspx)
    
- [<span data-ttu-id="c531c-204">Office 365 のセキュリティでは、新しいメッセージ トレース&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="c531c-204">New Message Trace in Office 365 Security &amp; Compliance Center</span></span>](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a><span data-ttu-id="c531c-205">手順 6: メールボックスを準備します。</span><span class="sxs-lookup"><span data-stu-id="c531c-205">Step 6: Prepare the mailboxes</span></span>

<span data-ttu-id="c531c-p124">確認し、メッセージだけを削除する必要がありますが、検索結果に含まれていることを検証した後は、**検索メールボックス DeleteContent**コマンドを実行すると、手順 7 で使用するのには影響を受けるメールボックスの電子メール アドレスの一覧を収集する必要があります。こぼれたデータが含まれているかの場合はこれらのメールボックスのいずれかのメールボックスで単一アイテムの回復を有効にするかどうかによって、電子メール メッセージを完全に削除する前にメールボックスを準備することもあります。</span><span class="sxs-lookup"><span data-stu-id="c531c-p124">After you review and validate that the search results contains only the messages that must be deleted, you need to collect a list of the email addresses of the impacted mailboxes to use in Step 7 when you run the **Search-Mailbox -DeleteContent** command. You may also have to prepare the mailboxes before you can permanently delete email messages depending on whether single item recovery is enabled on the mailboxes that contain the spilled data or if any of those mailboxes are on hold.</span></span>
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a><span data-ttu-id="c531c-208">こぼれたデータを持つメールボックスのアドレスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c531c-208">Get a list of addresses of mailboxes with spilled data</span></span>

<span data-ttu-id="c531c-209">こぼれたデータを持つメールボックスの電子メール アドレスの一覧を収集するための 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c531c-209">There are two ways to collect a list of email addresses of mailboxes with spilled data.</span></span>

<span data-ttu-id="c531c-210">**オプション 1: こぼれたデータを持つメールボックスのアドレスの一覧を取得します。**</span><span class="sxs-lookup"><span data-stu-id="c531c-210">**Option 1: Get a list of addresses of mailboxes with spilled data**</span></span>

1. <span data-ttu-id="c531c-211">電子的証拠開示のサポート案件を開く、**検索**ページに移動し、適切なコンテンツの検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="c531c-211">Open the eDiscovery case, go to the **Search** page and select the appropriate content search.</span></span> 
    
2. <span data-ttu-id="c531c-212">フライアウト] ページで、[**結果の表示**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c531c-212">On the flyout page, click **View results**.</span></span>
    
3. <span data-ttu-id="c531c-213">**個々 の結果**」ドロップ ダウン リストで、**検索の統計情報**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c531c-213">In the **Individual results** drop down list, click **Search statistics**.</span></span>
    
4. <span data-ttu-id="c531c-214">**種類**ドロップダウン リストの**一番上の場所**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c531c-214">In the **Type** drop down list, click **Top locations**.</span></span>
    
    ![上の場所] ページで、検索の統計情報の検索結果が含まれているメールボックスの一覧を取得します。](media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    <span data-ttu-id="c531c-p125">検索結果が含まれているメールボックスの一覧が表示されます。検索クエリに一致する各メールボックス内のアイテムの数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="c531c-p125">A list of mailboxes that contain search results is displayed. The number of items in each mailbox that match the search query is also displayed.</span></span>
    
5. <span data-ttu-id="c531c-218">リストに情報をコピーして、ファイルに保存または**ダウンロード**情報を CSV ファイルにダウンロードする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c531c-218">Copy the information in the list and save it to a file or click **Download** to download the information to a CSV file.</span></span> 
    
<span data-ttu-id="c531c-219">**オプション 2: レポートをエクスポートからメールボックスの場所を取得します。**</span><span class="sxs-lookup"><span data-stu-id="c531c-219">**Option 2: Get mailbox locations from the export report**</span></span>

<span data-ttu-id="c531c-p126">[手順 4](#step-4-review-and-validate-case-findings)でダウンロードしたエクスポートの概要レポートを開きます。レポートの最初の列で、[**所在地**] で各メールボックスの電子メール アドレスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c531c-p126">Open the Export Summary report that you downloaded in [Step 4](#step-4-review-and-validate-case-findings). In the first column in the report, the email address of each mailbox is listed under **Locations**.</span></span>
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a><span data-ttu-id="c531c-222">こぼれたデータを削除することができますので、メールボックスを準備します。</span><span class="sxs-lookup"><span data-stu-id="c531c-222">Prepare the mailboxes so you can delete the spilled data</span></span>

<span data-ttu-id="c531c-p127">単一アイテムの回復が有効になっている場合、または保留中のメールボックスが配置されている場合は、完全に削除 (パージ) メッセージは回復可能なアイテム] フォルダーに保持されます。こぼれたデータを削除することができます、前に、既存のメールボックスの構成を確認して 1 つのアイテムの復元を無効にして、保留中または Office 365 の保持ポリシーを削除する必要があります。一度に 1 つのメールボックスを準備して、別のメールボックスに同じコマンドを実行したり、同時に複数のメールボックスを準備する PowerShell スクリプトを作成するに留意してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p127">If single item recovery is enabled or if a mailbox is placed on hold, a permanently deleted (purged) message will be retained in Recoverable Items folder. So before you can purge spilled data, you need to check the existing mailbox configurations and disable single item recovery and remove any hold or Office 365 retention policy. Keep in mind that you can prepare one mailbox at a time, and then run the same command on different mailboxes or create a PowerShell script to prepare multiple mailboxes at the same time.</span></span>

- <span data-ttu-id="c531c-226">参照してください"ステップ 1: メールボックスに関する情報を収集」で[クラウド ベースのメールボックスのフォルダーを保持する回復可能な項目で項目の削除](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox)を単一アイテムの回復が有効になっているに、メールボックスを配置するかどうかやかに割り当てられるを確認する方法については、リテンション ・ ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="c531c-226">See "Step 1: Collect information about the mailbox" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) for instructions about how to check if single item recovery is enabled or if the mailbox is placed on hold or it's assigned to a retention policy.</span></span> 
    
- <span data-ttu-id="c531c-227">参照してください"ステップ 2: メールボックスを準備する」で[クラウド ベースのメールボックスのフォルダーを保持する回復可能な項目で項目を削除](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox)を 1 つのアイテムの復元を無効にする方法について。</span><span class="sxs-lookup"><span data-stu-id="c531c-227">See "Step 2: Prepare the mailbox" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) for instructions about disabling single item recovery.</span></span> 
    
- <span data-ttu-id="c531c-228">参照してください"ステップ 3: メールボックスからすべての保留を削除」で[クラウド ベースのメールボックスのフォルダーを保持する回復可能な項目で項目を削除](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox)を保持または保持ポリシーをメールボックスから削除する方法について。</span><span class="sxs-lookup"><span data-stu-id="c531c-228">See "Step 3: Remove all holds from the mailbox" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) for instructions about how to remove a hold or retention policy from a mailbox.</span></span> 
    
 <span data-ttu-id="c531c-p128">**重要な:** 保持または保持ポリシーを削除する前に、レコード管理または法務部門に確認してください。組織にメールボックスを保持するかどうかを定義するポリシーがありますか、データのこぼしたインシデントの優先します。</span><span class="sxs-lookup"><span data-stu-id="c531c-p128">**Important:** Check with your records management or legal departments before removing a hold or retention policy. Your organization may have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
<span data-ttu-id="c531c-p129">こぼれたデータが完全に削除されたことを確認した後、以前の構成のためのメールボックスを元に戻すことを確認します。詳細については、[手順 7](#step-7-permanently-delete-the-spilled-data)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p129">Be sure to revert the mailbox to previous configurations after you verify that the spilled data has been permanently deleted. See the details in [Step 7](#step-7-permanently-delete-the-spilled-data).</span></span>

## <a name="step-7-permanently-delete-the-spilled-data"></a><span data-ttu-id="c531c-233">こぼれたデータを完全に削除する手順 7。</span><span class="sxs-lookup"><span data-stu-id="c531c-233">Step 7: Permanently delete the spilled data</span></span>

<span data-ttu-id="c531c-p130">収集され、ステップ 6 で作成され、こぼれたデータを含む電子メール メッセージを検索する手順 3 で改良された検索クエリを準備するメールボックスの場所を使用すると、これで完全にデータを削除できます、こぼれた。説明したようには、メールボックスのインポート エクスポートの役割を割り当てる Exchange オンライン、次の手順を使用してメッセージを削除するのにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c531c-p130">Using the mailbox locations that you collected and prepared in Step 6 and the search query that was created and refined in Step 3 to find email messages that contain the spilled data, you can now permanently delete the spilled data. As previously explained, you have to be assigned the Mailbox Import Export role in Exchange Online to delete messages using the following procedure.</span></span>
  
1. <span data-ttu-id="c531c-236">[オンライン PowerShell を Exchange に接続](https://go.microsoft.com/fwlink/?linkid=396554)します。</span><span class="sxs-lookup"><span data-stu-id="c531c-236">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>
    
2. <span data-ttu-id="c531c-237">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c531c-237">Run the following command:</span></span>
    
    ```
    Search-Mailbox -Identity <mailbox identity> -SearchDumpster -DeleteContent $true -SearchQuery <search query>
    ```
  
3. <span data-ttu-id="c531c-238">データを含む、こぼれた、Identity パラメーターの値に置き換えることによって各メールボックスの前のコマンドを再実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="c531c-238">Re-run the previous command for each mailbox that contains the spilled data, by replacing the value for the Identity parameter; for example:</span></span>

    ```
    Search-Mailbox -Identity sarad@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

    ```
    Search-Mailbox -Identity janets@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

   ```
   Search-Mailbox -Identity pilarp@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
   ```
  
<span data-ttu-id="c531c-239">前述したように、また[powershell スクリプト](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6)を作成し、スクリプトは、各メールボックスのこぼれたデータを削除するためのメールボックスの一覧に対して実行できます。</span><span class="sxs-lookup"><span data-stu-id="c531c-239">As previously stated, you can also create a [powershell script](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6) and run it against a list of mailboxes so that the script deletes the spilled data in each mailbox.</span></span>
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a><span data-ttu-id="c531c-240">手順 8: ことを確認、削除、テストを行うし、監査</span><span class="sxs-lookup"><span data-stu-id="c531c-240">Step 8: Verify, provide a proof of deletion, and audit</span></span>

<span data-ttu-id="c531c-p131">データこぼしたのインシデントを管理するワークフローの最後のステップは、こぼれたデータ完全にから削除されたこと、メールボックス、電子的証拠開示の場合に移動し、結果 ar はないことを確認するには、そのデータを削除するために使用されたのと同じ検索クエリを再実行することを確認するにはe が返されます。こぼれたデータを完全に削除を確認したら、レポートをエクスポートし、(元のレポートでは) および削除の証明として含めることできます。[閉じる場合](ediscovery-cases.md#optional-step-9-close-a-case)、再度ファイルを開いて参照する場合があること、将来的にすることがあることができます。さらに、戻すことができますもメールボックスを使用して、こぼれたデータを検索し、データこぼしたインシデントを管理するときに実行される監査タスクのレコードを検索する検索クエリを削除前の状態にします。</span><span class="sxs-lookup"><span data-stu-id="c531c-p131">The final step in the workflow to manage a data spillage incident is to verify that the spilled data was permanently removed from the mailbox by going to the eDiscovery case and re-running the same search query that was used to delete that data to confirm that no results are returned. After you confirm the spilled data has been permanently removed, you can export a report and include it (along with the original report) as a proof of deletion. Then you can [close the case](ediscovery-cases.md#optional-step-9-close-a-case), which will allow you to re-open it if you have refer to it in the future. Additionally, you can also revert mailboxes to their previous state, delete the search query used to find the spilled data, and search for auditing records of tasks performed when managing the data spillage incident.</span></span> 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a><span data-ttu-id="c531c-245">メールボックスが元の状態を元に戻す</span><span class="sxs-lookup"><span data-stu-id="c531c-245">Reverting the mailboxes to their previous state</span></span>

<span data-ttu-id="c531c-p132">こぼれたデータが削除される前に、メールボックスを準備するのには手順 6 で、メールボックスの構成を変更した場合は、以前の状態に戻したりする必要があります。参照してください"手順 5: 以前の状態のためのメールボックスを元に戻す」で[クラウド ベースのメールボックスのフォルダーを保持する回復可能な項目で項目を削除](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-5-revert-the-mailbox-to-its-previous-state)します。</span><span class="sxs-lookup"><span data-stu-id="c531c-p132">If you changed any mailbox configuration in Step 6 to prepare the mailboxes before the spilled data was deleted, you will need to revert them to their previous state. See "Step 5: Revert the mailbox to its previous state" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-5-revert-the-mailbox-to-its-previous-state).</span></span>
  
### <a name="deleting-the-search-query"></a><span data-ttu-id="c531c-248">検索クエリの削除</span><span class="sxs-lookup"><span data-stu-id="c531c-248">Deleting the search query</span></span>

<span data-ttu-id="c531c-249">こぼれたの実際のデータのすべてのいくつか作成し、手順 3 で使用した検索クエリにキーワードが含まれる場合は、データのこぼしたを回避するために検索クエリを削除してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-249">If the keywords in the search query that you created and used in Step 3 contains some of all of the actual spilled data, you should delete the search query to prevent further data spillage.</span></span>
  
1. <span data-ttu-id="c531c-250">セキュリティ/コンプライアンス ・ センターで、電子的証拠開示のサポート案件をオープン、[**検索**] ページに移動し、適切なコンテンツの検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="c531c-250">In the Security & Compliance Center, open the eDiscovery case, go to the **Search** page, and select the appropriate content search.</span></span>
    
2. <span data-ttu-id="c531c-251">[ポップアップ] ページで、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c531c-251">On the flyout page, click **Delete**.</span></span>

    ![検索を選択し、ポップアップ ページの削除をクリックしてください](media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a><span data-ttu-id="c531c-253">データこぼした調査プロセスの監査</span><span class="sxs-lookup"><span data-stu-id="c531c-253">Auditing the data spillage investigation process</span></span>

<span data-ttu-id="c531c-p133">調査中に実行された電子的証拠開示活動の Office 365 の監査ログを検索することができます。こぼれたデータを削除するのには**検索メールボックス DeleteContent**コマンドを実行したときに作成された監査レコードを取得するのには監査ログを検索することもできます。詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-p133">You can search the Office 365 audit log for the eDiscovery activities that were performed during the investigation. You can also search the audit log to return the audit records that were created when you ran the **Search-Mailbox -DeleteContent** command to delete the spilled data. For more information, see:</span></span>

- <span data-ttu-id="c531c-257">&amp;</span><span class="sxs-lookup"><span data-stu-id="c531c-257">[Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md)</span></span>

- [<span data-ttu-id="c531c-258">Office 365 の監査ログに電子的証拠開示活動を検索します。</span><span class="sxs-lookup"><span data-stu-id="c531c-258">Search for eDiscovery activities in the Office 365 audit log</span></span>](search-for-ediscovery-activities-in-the-audit-log.md)

- <span data-ttu-id="c531c-259">Exchange Online のコマンドレットを実行しているに関連する監査レコードを検索する方法に関するガイダンスについては[監査ログが Office 365 のセキュリティとコンプライアンス ・ センターの検索](search-the-audit-log-in-security-and-compliance.md#audited-activities)で「Exchange 管理者の監査ログのアクティビティを監査する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c531c-259">See the "Audited activities - Exchange admin audit log " section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities) for guidance about how to search for audit records related to running cmdlets in Exchange Online.</span></span>
  

