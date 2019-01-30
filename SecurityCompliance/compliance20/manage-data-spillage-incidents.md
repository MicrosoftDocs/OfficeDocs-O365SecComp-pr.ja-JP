---
title: Microsoft 365 のデータのこぼしたインシデントを管理します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: データこぼしたのインシデントを管理するために Office 365 のセキュリティ & コンプライアンス センター内の新しいデータ調査 (プレビュー) ツールを使用してこの資料で説明します。
ms.openlocfilehash: d863d87cc667b9695f9bf619c35575715dfa144e
ms.sourcegitcommit: 98ec28932ae20e848f9f489c3c78e4a7edab6d18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "29636630"
---
# <a name="managing-a-data-spillage-incident-in-microsoft-365"></a><span data-ttu-id="d7e02-103">Microsoft 365 のデータのこぼしたインシデントを管理します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-103">Managing a data spillage incident in Microsoft 365</span></span> 

<span data-ttu-id="d7e02-p101">こぼしたのデータは、機密性の高いドキュメントが信頼されていない環境にリリースされたときです。データこぼしたのインシデントが検出されると、することが重要、こぼしたの場所とサイズを迅速に評価、囲み、ユーザー アクティビティを確認してシステムからこぼれたデータを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p101">Data spillage is when a confidential document is released into an untrusted environment. When a data spillage incident is detected, it's important to quickly assess the size and locations of the spillage, examine user activities around it, and then permanently purge the spilled data from the system.</span></span>

## <a name="scope-of-this-article"></a><span data-ttu-id="d7e02-106">この資料の範囲</span><span class="sxs-lookup"><span data-stu-id="d7e02-106">Scope of this article</span></span>

<span data-ttu-id="d7e02-107">この資料でなくなったユーザーまたは管理者が回復したり、アクセスできるように、Office 365 のメールボックスからアイテムを完全に削除する方法の手順の一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-107">This article provides a list of instructions on how to permanently remove items from Office 365 mailboxes so they are no longer accessible or recoverable by users or admins.</span></span> 

> [!NOTE]
> <span data-ttu-id="d7e02-108">ビジネス サイトの SharePoint または OneDrive にある項目を削除するときは、元の場所からそれらを削除する時間から 93 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="d7e02-108">When you delete items located in a SharePoint or OneDrive for Business site, they are retained for 93 days from the time you delete them from their original location.</span></span>

## <a name="scenario"></a><span data-ttu-id="d7e02-109">シナリオ</span><span class="sxs-lookup"><span data-stu-id="d7e02-109">Scenario</span></span>

<span data-ttu-id="d7e02-p102">従業員知らずに共有されている機密性の高いドキュメント電子メールを通じて複数のユーザーとデータのこぼしたインシデントの通知します。このドキュメントは、組織の内外を受信したユーザーを迅速に評価する必要があります。インシデントを調査して後を確認して、Office 365 からこぼれたデータを完全に削除するその他の調査と調査結果を共有する場合します。調査の完了後、削除するすべての証拠。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p102">You're informed of a data spillage incident where an employee unknowingly shared a highly-confidential document with multiple people through email. You want to quickly assess who received this document, both inside and outside of your organization. After you've investigate the incident, you plan to share your findings with other investigators to review, and then permanently remove the spilled data from Office 365. After the investigation is complete, you want to remove all evidence.</span></span> 

## <a name="workflow"></a><span data-ttu-id="d7e02-114">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="d7e02-114">Workflow</span></span>

<span data-ttu-id="d7e02-115">データ調査 (プレビュー) を使用してデータのこぼしたインシデントを管理するためのワークフローを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-115">Here's the workflow for using Data Investigations (Preview) to manage a data spillage incident:</span></span>

1.  <span data-ttu-id="d7e02-116">データの調査を作成します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-116">Create a data investigation.</span></span>

2.  <span data-ttu-id="d7e02-117">こぼれたデータを検索します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-117">Search for the spilled data.</span></span>

3.  <span data-ttu-id="d7e02-118">確認し、問題を調査します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-118">Review and investigate the incident.</span></span>

4.  <span data-ttu-id="d7e02-119">こぼれたデータを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-119">Permanently delete the spilled data.</span></span>

5.  <span data-ttu-id="d7e02-120">閉じるか、調査を削除します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-120">Close or delete the investigation.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="d7e02-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="d7e02-121">Before you begin</span></span>

- <span data-ttu-id="d7e02-p103">Office 365 のセキュリティ & コンプライアンス センターで作成調査、こぼれたデータを検索し、レビュー、分析するデータの調査 (プレビュー) ツールを使用します。Office 365 からこぼれたデータを完全に削除するのにセキュリティ & コンプライアンス センター PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p103">You'll use the Data Investigations (Preview) tool in the Office 365 Security & Compliance Center to create an investigation, search for the spilled data, and review and analyze it. Then you'll use Security & Compliance Center PowerShell to permanently delete the spilled data from Office 365.</span></span> 

- <span data-ttu-id="d7e02-124">調査を作成するには、セキュリティ & コンプライアンス センターでのコンプライアンス管理者の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7e02-124">To create an investigation, you have to be a member of the Compliance Administrator role group in the Security & Compliance Center.</span></span>

- <span data-ttu-id="d7e02-p104">メッセージを削除するには、セキュリティ & コンプライアンス センターでの組織の管理役割グループのメンバーであるか、検索および削除の役割を割り当てる必要があります。ユーザーを役割グループに追加する方法の詳細については、[セキュリティ & コンプライアンス センターへのユーザー アクセス許可](../grant-access-to-the-security-and-compliance-center.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p104">To delete messages, you have to be a member of the Organization Management role group in the Security & Compliance Center or be assigned the Search and Purge role. For information about adding users to a role group, see [Give users access to the Security & Compliance Center](../grant-access-to-the-security-and-compliance-center.md).</span></span> 

- <span data-ttu-id="d7e02-p105">どのユーザーのメールボックスとを調査官が検索することができます OneDrive アカウントを制御するには、組織は、コンプライアンスの境界を設定できます。詳細については、[電子的証拠開示の調査のコンプライアンスの境界を設定](../set-up-compliance-boundaries.md)します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p105">To control which user mailboxes and OneDrive accounts an investigator can search, your organization can set up compliance boundaries. For more information, [Set up compliance boundaries for eDiscovery investigations](../set-up-compliance-boundaries.md).</span></span> 

## <a name="step-1-create-a-data-investigation"></a><span data-ttu-id="d7e02-129">ステップ 1: データの調査を作成します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-129">Step 1: Create a data investigation</span></span>

<span data-ttu-id="d7e02-130">データの調査を作成します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-130">To create a data investigation:</span></span>

1. <span data-ttu-id="d7e02-131">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-131">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="d7e02-132">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d7e02-132">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="d7e02-133">セキュリティ & コンプライアンス センターでは、**データの調査**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7e02-133">In the Security & Compliance Center, click **Data Investigations**.</span></span>
 
4. <span data-ttu-id="d7e02-134">**データ調査 (プレビュー)** ] ページで、**新しい調査の作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7e02-134">On the **Data Investigations (Preview)** page, click **Create a new investigation**.</span></span>
    
5. <span data-ttu-id="d7e02-p106">フライアウトの**新しいデータの調査**] ページで、[調査 (必須)、名前を付けるし、省略可能な調査の数と説明を入力します。名前が、組織内で一意である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p106">On the **New data investigation** flyout page, give the investigation a name (required), and then type an optional investigation number and description. Note that the name must be unique in your organization.</span></span>

6. <span data-ttu-id="d7e02-137">**この調査を作成した後、追加設定を構成するですか?**、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d7e02-137">Under **Do you want to configure additional settings after creating this investigation?**, do one of the following:</span></span>

    - <span data-ttu-id="d7e02-p107">**はい**調査を作成する] をクリックし、新規の場合は [**設定**] ページを表示します。調査にメンバーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p107">Click **Yes** to create the investigation, and display the **Settings** page in the new case. This allows you to add members to the investigation.</span></span>
    
    - <span data-ttu-id="d7e02-p108">**なし**だけ調査を作成し、[**データの調査 (プレビュー)** ] ページで、サポート案件の一覧に表示する] をクリックします。このオプションを選択した場合、調査し、既定の検索および分析の設定の唯一のメンバーが使用するとする追加されます。メンバーを追加したり、調査を作成した後は、いつでも設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p108">Click **No** to just create the investigation and display it in the list of cases on the **Data Investigations (Preview)** page. If you choose this option, you will be added as the only member of the investigation and the default search and analytics settings will be used. You can add members or change settings any time after the investigation is created.</span></span>

7. <span data-ttu-id="d7e02-143">調査を作成するのには**保存**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7e02-143">Click **Save** to create the investigation.</span></span>

    <span data-ttu-id="d7e02-144">新しい調査は、**データの調査 (プレビュー)** ] ページの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7e02-144">The new investigation is displayed in the list on the **Data Investigations (Preview)** page.</span></span> 

8. <span data-ttu-id="d7e02-145">調査を開くには、調査の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7e02-145">To open an investigation, click the name of the investigation.</span></span> 

    <span data-ttu-id="d7e02-146">調査のための [**ホーム**] タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7e02-146">The **Home** tab for the investigation is displayed.</span></span> 

> [!TIP]
> <span data-ttu-id="d7e02-147">調査の名前付け規則を確立することを検討しのように、名前と説明を検索しを参照してください、将来的に必要な場合は、できるだけ多くの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-147">Consider establishing a naming convention for investigations and provide as much information as you can in the name and description so you can locate and refer to in the future if necessary.</span></span>
 
## <a name="step-2-search-for-the-spilled-data"></a><span data-ttu-id="d7e02-148">こぼれたデータに対して手順 2: 検索</span><span class="sxs-lookup"><span data-stu-id="d7e02-148">Step 2: Search for the spilled data</span></span> 
 
<span data-ttu-id="d7e02-p109">こぼれたデータを検索するユーザーがわかっている場合は、調査、データ ソースにマップし、メールボックスと OneDrive のアカウントをすばやく検索する目的のユーザーとして追加できます。調査する対象のユーザーを追加するには、**目的の人**をクリックし、**目的のユーザーを追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p109">If you know which users you want to search for spilled data, you can add them as people of interest to map their data sources to the investigation and quickly search their mailbox and OneDrive account. To add people of interest to the investigation, click **People of interest**, and then click **Add people of interest**.</span></span> 

<span data-ttu-id="d7e02-p110">[**検索**] タブで、こぼれたデータを検索する検索を作成できます。こぼれた[手順 4](##step-4:-permanently-delete-the-spilled-data)で同じメッセージを削除するのにはデータの検索に使用したのと同じ検索クエリを使用します。サーチの作成の詳細については、[データを収集するために検索を作成する](create-search-to-collect-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p110">On the **Searches** tab, you can create searches to find the spilled data. You will use the same search query that you used to find the spilled data to delete those same messages in [Step 4](##step-4:-permanently-delete-the-spilled-data). For more information about creating searches, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="d7e02-p111">検索を実行した後、検索結果と検索クエリの有効性を評価するために検索の統計情報のビューのサンプルをプレビューできます。Office 365 から削除する項目を特定した後、[**インシデント**] タブをクリックしインシデントを作成し、それらのアイテムを含む検索結果を追加します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p111">After you run the search, you can preview samples of search results and view search statistics to evaluate the effectiveness of your search query. Once you identify the items that you want to delete from Office 365, you can click the **Incidents** tab, and then create an incident and add search results that contain those items.</span></span> 

<span data-ttu-id="d7e02-p112">これを行うには、調査する検索をクリックします。フライアウト] ページで、[**インシデントへの追加の結果**] をクリックし、指示に従います。事故でことができます個々 のドキュメントを確認、いたことが、ドキュメントへのアクセスを調査し、ドキュメントをエクスポートします。単にそれらを確認するのではなくドキュメントを削除するには、[手順 4](##step-4:-permanently-delete-the-spilled-data)に進みます。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p112">To do this, click the search that you want to investigate. On the flyout page, click **Add results to incident** and follow the instructions. Then in the incident, you can review individual documents, investigate who had access to documents, and export the documents. To simply delete the documents instead of reviewing them, go to [Step 4](##step-4:-permanently-delete-the-spilled-data).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d7e02-p113">検索クエリで使用するキーワードの検索を実行している実際のこぼれたデータがあります。など、検索クエリのキーワードとして使用し、社会保障番号を含むドキュメントを検索する場合は、さらにこぼしたを回避するには、後でクエリを削除してください。検索結果を削除するか、[手順 5](##step-5:-close-or-delete-investigation)では、全体の調査を削除できます。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p113">The keywords that you use in the search query may contain the actual spilled data that you're searching for. For example, if you searching for documents containing a social security number and you use it as a keyword in the search query, you must delete the query afterwards to avoid further spillage. You can delete search or delete the entire investigation in [Step 5](##step-5:-close-or-delete-investigation).</span></span> 

## <a name="step-3-review-and-investigate"></a><span data-ttu-id="d7e02-163">手順 3: を確認し、調査</span><span class="sxs-lookup"><span data-stu-id="d7e02-163">Step 3: Review and investigate</span></span> 

<span data-ttu-id="d7e02-p114">調査を進めるでは、**インシデント**] タブに移動し、前の手順で作成したインシデントをクリックします。処理ジョブが完了し、検索結果がインシデントに追加された、それぞれのネイティブ形式、テキスト形式またはネイティブに近い形式で個々 のドキュメントを確認できます。ドキュメント、および、調査で判明した内容を示すタグのドキュメントの一覧をさらに絞り、他のクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p114">In the investigation, go to **Incidents** tab and click on the incident that you created in the previous step. After the processing job is completed and the search results are added to the incident, you can review individual documents in their native format, text format, or a near-native format. You can create additional queries to further narrow the list of documents, and tag documents to indicate findings from your investigation.</span></span>

<span data-ttu-id="d7e02-p115">ドキュメントをグループ化し、確認のための複数の支援を受け、**インシデントの管理**] をクリックします。**分析**] タイルで [**分析**を] をクリックします。重複データ検出、電子メールのスレッド、およびテーマの分析などの高度な分析が実行されます。詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p115">To group documents and get more assistance for your review, click **Manage incident**. In the **Analytics** tile, click **Analyze**. This will run advanced analytics such as duplicate detection, email threading, and theme analysis. For more information, see:</span></span>

- [<span data-ttu-id="d7e02-171">重複データ検出の近く</span><span class="sxs-lookup"><span data-stu-id="d7e02-171">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="d7e02-172">電子メールのスレッド</span><span class="sxs-lookup"><span data-stu-id="d7e02-172">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="d7e02-173">テーマ</span><span class="sxs-lookup"><span data-stu-id="d7e02-173">Themes</span></span>](themes.md)

<span data-ttu-id="d7e02-p116">データこぼしたに関連するユーザーを確認するのには、事故で新しいクエリを作成し、送信者または作成者と受信者の条件を使用してできます。これにより、すべての送信者、受信者、およびインシデントに追加されたデータの収集については、著者のリストが作成されます。必ず一覧に外部ユーザーがあるかどうかを判断するのには一覧を確認してください。詳細については、[検索条件](../keyword-queries-and-search-conditions.md#search-conditions)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p116">To determine which users are involved in the data spillage, you can create a new query in the incident and then use the Sender/Author and Recipients conditions. This will create a list of all senders, recipients and authors found in collected data that was added to the incident. Be sure to examine the list to determine if there are any external users in the list. For more information, see [Search conditions](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>

## <a name="step-4-permanently-delete-the-spilled-data"></a><span data-ttu-id="d7e02-178">こぼれたデータを完全に削除する手順 4。</span><span class="sxs-lookup"><span data-stu-id="d7e02-178">Step 4: Permanently delete the spilled data</span></span>

### <a name="deleting-mailbox-items"></a><span data-ttu-id="d7e02-179">メールボックス アイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-179">Deleting mailbox items</span></span>

<span data-ttu-id="d7e02-p117">確認および、電子メール メッセージだけを削除する必要がありますが検索結果に含まれていることを検証すると、完全に削除するを実行して、 **New ComplianceSearchAction-PurgeType HardDelete を削除**セキュリティ & 準拠のコマンドPowerShell のセンターです。手順については、[検索および削除する電子メール メッセージ](../search-for-and-delete-messages-in-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p117">After you review and validate that the search results contain only the email messages that must be deleted, you can permanently delete them by running the **New-ComplianceSearchAction -Purge -PurgeType HardDelete** command in Security & Compliance Center PowerShell. For instructions, see [Search for and delete email messages](../search-for-and-delete-messages-in-your-organization.md).</span></span> 

<span data-ttu-id="d7e02-p118">組織内のメールボックスの単一アイテムの回復が有効になっている場合は、完全に削除済みアイテムをユーザーの回復可能なアイテム] フォルダーに保持されている (アクセス可能でなければ管理者によって)、削除済みアイテムの保存期間が終了する (既定では 14 日) までです。さらに、こぼれたデータが含まれているメールボックスのいずれかの法的保持義務には、リテンション ・ ポリシーに割り当てられている場合削除したメッセージは回復可能なアイテム] フォルダーにするまで保留される保留を削除または保持ポリシーからメールボックスが除外されています。ハード削除メッセージをすぐに、[追加のタスクを実行する必要があります。手順については、[クラウド ベースのメールボックスのフォルダーを保持する回復可能な項目で項目を削除する](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p118">Note that if single item recovery is enabled for mailboxes in your organization, permanently deleted items will be retained in the user's Recoverable items folder (and accessible by admins) until the deleted item retention period ends (default is 14 days). Additionally, if any of the mailboxes that contain spilled data are on a legal hold or assigned to a retention policy, purged message will be retained in Recoverable items folder until the hold is removed or the mailbox is excluded from retention policies. To hard delete messages immediately, you need to perform addition tasks. For instructions, see [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold ](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md).</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="d7e02-p119">保持または保持ポリシーを削除する前に、レコード管理または法務部門に確認してください。組織にメールボックスを保持するかどうかを定義するポリシーがありますか、データのこぼしたインシデントの優先します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p119">Check with your records management or legal departments before removing a hold or retention policy. Your organization may have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 

### <a name="deleting-site-items"></a><span data-ttu-id="d7e02-188">サイトのアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-188">Deleting site items</span></span>

<span data-ttu-id="d7e02-p120">ビジネス アカウントの OneDrive または SharePoint サイトからドキュメントを完全に削除、それを削除する必要しする必要があるサイトから削除し、サイト コレクションのごみ箱から削除します。手順については、 [SharePoint と OneDrive を削除するドキュメント](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p120">To permanently delete a document from a SharePoint site or OneDrive for Business account, you have to delete it and then you have to delete from the site and then delete it from the site collection Recycle Bin. For instructions, see [Deleting documents in SharePoint and OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business).</span></span>

<span data-ttu-id="d7e02-p121">また、こぼれたデータが含まれている可能性がありますが、全体のサイト コレクションを削除できます。手順については、[サイト コレクションを削除する](https://docs.microsoft.com/sharepoint/delete-site-collection)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p121">Alternatively, you can delete an entire site collection that might contained spilled data. For instructions, see [Delete a site collection](https://docs.microsoft.com/sharepoint/delete-site-collection).</span></span>

## <a name="step-5-close-or-delete-the-investigation"></a><span data-ttu-id="d7e02-193">手順 5: を閉じる、または調査を削除</span><span class="sxs-lookup"><span data-stu-id="d7e02-193">Step 5: Close or delete the investigation</span></span>

<span data-ttu-id="d7e02-p122">ソース コンテンツの場所 (メールボックスまたはサイト) 内のドキュメントを削除した後は、事故調査の一部として追加したこれらのドキュメントのコピーをまだがあります。データこぼしたを防ぐには、調査の削除を検討してください。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p122">After you delete documents in the source content locations (mailboxes or sites), you will still have copies of these documents that you added to incidents as part of your investigation. To avoid further data spillage, you should consider deleting the investigation.</span></span>

<span data-ttu-id="d7e02-196">調査を削除します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-196">To delete an investigation:</span></span>

1. <span data-ttu-id="d7e02-197">[**設定**] タブには、**調査情報**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7e02-197">On the **Settings** tab, click **Investigation information**.</span></span>
2. <span data-ttu-id="d7e02-198">**サポート案件を削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7e02-198">Click  **Delete case**.</span></span> 

<span data-ttu-id="d7e02-p123">調査を削除する必要はありませんを調査中に収集した情報を保存する場合や、**ケースのクローズ**をクリックすることができます。後で、開くことができます再調査を終了します。</span><span class="sxs-lookup"><span data-stu-id="d7e02-p123">If you don't need to delete the investigation or if you want to save the information that you collected during the investigation, you can click **Close case**. At a later date, you can re-open closed investigations.</span></span>