---
title: イベント ベースの保持を自動化する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: このトピックでは、Microsoft 365 REST API を使用して、イベントによってビジネス プロセス フローの自動化の保持をセットアップする方法について説明します。
ms.openlocfilehash: c89abc373a6c0a1de6b6528c638dbd34e586b6d7
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152279"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="49a9e-103">イベント ベースの保持を自動化する</span><span class="sxs-lookup"><span data-stu-id="49a9e-103">Automate event-based retention</span></span>

<span data-ttu-id="49a9e-p101">組織内のコンテンツの急増や、コンテンツが ROT (冗長、古い、無駄) になる可能性はビジネスにとって重大です。法、ビジネス、規制に関するコンプライアンスの課題に継続的に対応するには、企業は重要な情報を保持して保護し、関連性をすばやく見い出す必要があります。ビジネスを成功させるには、重要かつ適切な情報のみを保持することが鍵となります。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, businesses must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to a business’s success.</span></span>

<span data-ttu-id="49a9e-p102">そのため、組織は Office 365 セキュリティ/コンプライアンス センターの保持ソリューションを活用できます。保持は、[保持ラベル](labels.md)を使用してトリガーできます。保持ラベルには、[特定のイベントに基づいて保持期間を設定する](event-driven-retention.md)オプションがあります。通常、保持期間は、コンテンツの作成日や最終変更日など既知の日付に基づきます。ただし、組織で、ある従業員が組織から離れてから 7 年後などの特定のイベントに基づいてコンテンツを破棄するという要件が生じることもあります。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p102">Hence organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as 7 years after an employee leaves an organization.</span></span>

<span data-ttu-id="49a9e-p103">コンテンツの破棄に対応するには、イベントが生じた時期を把握することが不可欠です。コンテンツ量が急激に増えると、適切なタイミングで準拠した方法でコンテンツを保持したり破棄したりすることが課題となります。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p103">In order to ensure compliant disposal of content, it is imperative to know when an event takes place. With the volume of content increasing rapidly, it is becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="49a9e-p104">イベント ベースの保持はこの問題を解決できます。このトピックでは、Microsoft 365 REST API を使用して、イベントによりビジネス プロセス フローの保持の自動化をセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="49a9e-116">イベント ベースの保持について</span><span class="sxs-lookup"><span data-stu-id="49a9e-116">About event-based retention</span></span>

<span data-ttu-id="49a9e-p105">組織の規模は小、中、大とさまざまです。日常的に作成および管理されるビジネス文書、法的文書、従業員のファイル、契約、製品文書は劇的に増えていきます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day to day basis is increasing dramatically.</span></span>

<span data-ttu-id="49a9e-p106">たとえば、数十、数百単位の従業員が入社したり退社したりします。人事部はビジネス要件に基づいて従業員関連の文書を継続的に作成、更新、削除します。このプロセスは、会社で規定されている各種保持ポリシーの対象となります。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="49a9e-p107">**コンテンツの保持期間は既知の日付にすることことが可能です**。たとえば、コンテンツの作成日、最終変更日または最終ラベル設定日などです。文書を作成後 7 年間保持し、その後処分するなどが可能です。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="49a9e-p108">**またコンテンツの保持期間を不明な日付にすることもできます**。たとえば、保持ラベルを使用すると、従業員が組織を離れるなどの特定のイベントが生じる時点に基づいて保持期間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="49a9e-p109">イベントによって保持時間が開始され、対象種類のイベントに適用されるラベルが付いたすべてのコンテンツに、そのラベルの保持アクションが実行されます。これを、イベント ベースの保持と呼びます。詳しくは、[イベント適応型保持の概要](event-driven-retention.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention - to learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="49a9e-128">イベント ベースの保持をセットアップする</span><span class="sxs-lookup"><span data-stu-id="49a9e-128">Set up event-based retention</span></span>

<span data-ttu-id="49a9e-129">このセクションでは、コンテンツを保持する前に実行する必要がある事柄について取り上げます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-129">This section describes what needs to be done prior to retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="49a9e-130">役割を特定する</span><span class="sxs-lookup"><span data-stu-id="49a9e-130">Identify roles</span></span>

<span data-ttu-id="49a9e-131">ビジネス文書の有効かつ効率的な保持に関して責任を担うレコード管理タスクを実行する、組織内の各種役割を特定します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-131">Identify the different roles in an organization that perform Record Management tasks that would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="49a9e-132">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="49a9e-132">**Persona**</span></span>| <span data-ttu-id="49a9e-133">**役割**</span><span class="sxs-lookup"><span data-stu-id="49a9e-133">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="49a9e-134">管理者</span><span class="sxs-lookup"><span data-stu-id="49a9e-134">Admin</span></span> | <span data-ttu-id="49a9e-135">保持イベントの種類、保持ラベル、レコード リポジトリを SharePoint で作成します</span><span class="sxs-lookup"><span data-stu-id="49a9e-135">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="49a9e-136">レコード管理者</span><span class="sxs-lookup"><span data-stu-id="49a9e-136">Records Manager</span></span>                                  | <span data-ttu-id="49a9e-137">保持ポリシー、保持スケジュール ガイダンス、コンプライアンスの詳細を提供します</span><span class="sxs-lookup"><span data-stu-id="49a9e-137">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="49a9e-138">システム管理者 (会社)</span><span class="sxs-lookup"><span data-stu-id="49a9e-138">System Admin (business)</span></span>                          | <span data-ttu-id="49a9e-139">Microsoft 365 を扱う外部システムをセットアップして管理します</span><span class="sxs-lookup"><span data-stu-id="49a9e-139">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="49a9e-140">インフォメーション ワーカー</span><span class="sxs-lookup"><span data-stu-id="49a9e-140">Information Worker</span></span>                               | <span data-ttu-id="49a9e-141">(人事、財務、IT など) ビジネス プロセスのライフ サイクルを管理します</span><span class="sxs-lookup"><span data-stu-id="49a9e-141">Manages the lifecycle of their business process (HR, Finance, IT etc)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="49a9e-142">セキュリティ/コンプライアンス センターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="49a9e-142">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="49a9e-143">コンプライアンス管理者がイベントタイプの作成を行います - 例えば、従業員の解雇、契約の有効期限、製品の製造終了など（[イベント適応型保持](https://docs.microsoft.com/ja-JP/office365/securitycompliance/event-driven-retention)の段階的プロセスを参照してください）</span><span class="sxs-lookup"><span data-stu-id="49a9e-143">Compliance admin creates an event type – for example, Employee Termination or Contract Expiration or End of Product Manufacturing (Please refer to step by step process in [Event-driven retention](https://docs.microsoft.com/en-us/office365/securitycompliance/event-driven-retention).</span></span>
    
1. <span data-ttu-id="49a9e-144">コンプライアンス管理者は、業務内容に基づいて保持ラベルを作成し、そのラベルをイベントタイプに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-144">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
1. <span data-ttu-id="49a9e-145">保持ラベルをトリガーするには以下の 4 種類があります。</span><span class="sxs-lookup"><span data-stu-id="49a9e-145">There are 4 types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="49a9e-146">作成日</span><span class="sxs-lookup"><span data-stu-id="49a9e-146">Create date</span></span>
                
    1. <span data-ttu-id="49a9e-147">最終更新日時</span><span class="sxs-lookup"><span data-stu-id="49a9e-147">Last modified</span></span>
                
    1. <span data-ttu-id="49a9e-148">ラベル日付 (コンテンツがラベル付けされた日)</span><span class="sxs-lookup"><span data-stu-id="49a9e-148">Label date (when the content was labeled)</span></span>
                
    1. <span data-ttu-id="49a9e-149">イベント ベース</span><span class="sxs-lookup"><span data-stu-id="49a9e-149">Event-based</span></span>
    
1. <span data-ttu-id="49a9e-150">コンプライアンス管理者が保持ラベルを発行します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-150">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="49a9e-151">SharePoint をセットアップする</span><span class="sxs-lookup"><span data-stu-id="49a9e-151">Set up SharePoint</span></span>
   
<span data-ttu-id="49a9e-152">レコード リポジトリを作成するには、コンプライアンス管理者は次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="49a9e-152">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="49a9e-153">SharePoint サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-153">Creates a SharePoint site.</span></span>

1. <span data-ttu-id="49a9e-154">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-154">Does one of the following:</span></span>
        
    - <span data-ttu-id="49a9e-p110">SharePoint ライブラリを作成します。ライブラリ レベルでイベント ベースのラベルを設定します。詳しくは、[SharePoint ライブラリ、フォルダー、またはドキュメント セット内のすべてのコンテンツへの既定の保持ラベルの適用](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p110">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="49a9e-p111">SharePoint でドキュメント セットをセットアップします。詳しくは、[ドキュメント セットの概要](https://support.office.com/ja-JP/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p111">Sets up a Document set in SharePoint. For more information, see [Introduction to document sets](https://support.office.com/en-us/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
1. <span data-ttu-id="49a9e-p112">各従業員ドキュメント セットにアセット ID (アセット ID は組織が使用する製品名またはコードです。たとえば、従業員番号はアセット ID となります) を割り当てます。そのため、フォルダーにアセット ID を割り当て、そのフォルダー内のすべての項目が同じアセット ID を自動的に継承します。つまり、すべての項目に、同じイベントによってトリガーされた保持期間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p112">Assigns Asset Id (asset ID is a product name or code used by the organization, for example, Employee number can be an asset id) to each employee document set (By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID. This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="49a9e-161">イベント ベースの保持をトリガーする方法</span><span class="sxs-lookup"><span data-stu-id="49a9e-161">Ways to trigger event-based retention</span></span>

<span data-ttu-id="49a9e-162">イベント ベースの保持をトリガーするには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="49a9e-162">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="49a9e-p113">**管理センターのUIを使用する**これは、一度に保存するコンテンツを少なくするために使用できるプロセスで、保持をトリガーする頻度は、月ごと、年ごとなど、あまりありません。この方法について詳しくは、[イベント適応型保持の概要](event-driven-retention.md)を参照してください。ただし、この方法で保持をトリガーすると、時間がかかり、エラーが発生しやすくなるため、拡張性が妨げられます。したがって、保持をトリガーするための自動化された一枚岩のソリューションは、データのセキュリティとコンプライアンスを強化することができます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p113">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention is not often, such as monthly or yearly. For more information on this method, see [Overview of event-driven retention](event-driven-retention.md). However, this way to trigger retention can be time-consuming and prone to error, thus stunting scalability. Therefore, an automated, seamless solution to trigger retention can enhance the security and compliance of data.</span></span>

- <span data-ttu-id="49a9e-p114">**M365 REST API を使用する** このプロセスは、1 度に大量のコンテンツを保持したり、保持をトリガーする頻度が毎日や週ごとなど多い場合に使用できます。このフローによって基幹業務システムでイベントが生じたタイミングが検出され、セキュリティ/コンプライアンス センターで関連するイベントが自動的に作成されます。該当するイベントが生じるたびに UI でイベントを手動で作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p114">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="49a9e-170">REST API の使用に関して次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="49a9e-170">There are two options for using the REST API:</span></span>

- <span data-ttu-id="49a9e-p115">**Microsoft Flow または同様のアプリケーション**を使用して、イベントを自動的にトリガーできます。Microsoft Flow は他のシステムとの接続のオーケストレーターです。Microsoft Flow の使用に際して、カスタム ソリューションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p115">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically. Microsoft Flow is an orchestrator for connecting to other systems. Using Microsoft Flow does not require a custom solution.</span></span>

- <span data-ttu-id="49a9e-174">**PowerShell または HTTP クライアントを使用して REST API を呼び出す** PowerShell (バージョン 6 以降) を使用して Microsoft 365 REST API を呼び出してイベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-174">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="49a9e-p116">Rest API は一連の HTTP 操作 (メソッド) をサポートするサービス エンドポイントで、サービスのリソースに対する作成/取得/更新/削除のアクセス権を提供します。詳しくは、[REST API 要求/応答のコンポーネント](https://docs.microsoft.com/ja-JP/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)をご覧ください。この場合、Microsoft 365 REST API を使用することにより、POST および GET 操作 (メソッド) を使用してイベントを作成および取得できます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p116">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources - for more information, see [Components of a REST API request/response](https://docs.microsoft.com/en-us/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="49a9e-177">シナリオ例</span><span class="sxs-lookup"><span data-stu-id="49a9e-177">Example scenarios</span></span>

<span data-ttu-id="49a9e-178">次のシナリオについて考えます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-178">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="49a9e-179">シナリオ 1: 従業員が組織のメンバーでなくなる</span><span class="sxs-lookup"><span data-stu-id="49a9e-179">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="49a9e-p117">ある組織は、従業員ごとに多数の従業員関連文書を作成し、保管しています。これらの文書は、各従業員の雇用期間中、管理および保持されます。ただし、従業員が組織のメンバーでなくなったり、従業員が退職したりすると、法的および会社の要件に基づいて、規定された期間、その従業員の文書を保持する義務が組織にはあります。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p117">An organization creates and stores numerous employee related documents per employee. These documents are managed and retained during the employment of each employee. However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="49a9e-183">ここで、複数の従業員が毎日組織のメンバーでなくなるとすると、数千ではないものの数百もの文書の保持期間を毎日トリガーしなくてはなりません。</span><span class="sxs-lookup"><span data-stu-id="49a9e-183">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="49a9e-p118">また、各従業員に関して保持期間を計算する必要もあります。従業員の退社日に、従業員レコードの種類に応じて、日、月、年数を加算します。たとえば、従業員の報酬に関する文書と同じ従業員の福利厚生申請書類では保持期間が異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p118">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months or years based on the type of the employee record. For example, worker’s compensation of the employee vs benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="49a9e-p119">次の図には、1 つのイベントに複数のラベルを関連付けられることを示しています。「従業員の報酬 (Worker’s compensation)」の下のすべてのファイルと、「従業員の福利厚生 (Employee benefits)」ラベルのすべてのファイルがどちらも、従業員が組織のメンバーでなくなるときの単一のイベントに関連付けられています。これら別々のファイルの保持期間は異なります。そのため、従業員が組織のメンバーでなくなると、各ラベルのファイルには異なる保持期間が適用されます。異なる種類のラベルまたは各従業員のラベルに対して異なる保持期間すべてをトリガーするのは、たいへん難しい作業となります。しかも複数の従業員に対してそうしなければなりません。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p119">The diagram below shows how there can be multiple labels that are associated with a single event. Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event which is the employee leaving the organization. Each of these different files have different retention clocks. So, when an employee leaves the organization, these files within each label experience a different retention period. To trigger all these different retention clocks for each file type or label for each employee is a very challenging task. Imagine doing this for multiple employees.</span></span>

![イベントの種類、イベント、およびラベルの図](media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="49a9e-193">そのため、複数の従業員に対して異なる保持期間をトリガーするプロセスを自動化すると、時間の節約になり、エラーがなくなり、非常に効率的となります。</span><span class="sxs-lookup"><span data-stu-id="49a9e-193">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free and extremely efficient .</span></span>

<span data-ttu-id="49a9e-194">**このシナリオに関する自動化されたイベント ベースの保持を構成する:**</span><span class="sxs-lookup"><span data-stu-id="49a9e-194">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![従業員が組織のメンバーでなくなるシナリオに関する役割とアクションの図](media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="49a9e-196">管理者は Jane Doe、John Smith などの文書セットに従業員フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-196">Admin c reates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="49a9e-197">管理者は、福利厚生、給与、従業員報酬などの従業員ファイルを各従業員フォルダーに追加します</span><span class="sxs-lookup"><span data-stu-id="49a9e-197">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder</span></span>

  - <span data-ttu-id="49a9e-198">管理者は、各従業員フォルダーにアセット ID を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-198">Admin assigns Asset Id to each employee folder.</span></span> 

  - <span data-ttu-id="49a9e-199">SCC 管理者は</span><span class="sxs-lookup"><span data-stu-id="49a9e-199">SCC Admin l</span></span>

  - <span data-ttu-id="49a9e-200">セキュリティ＆コンプライアンスセンターにログインします。</span><span class="sxs-lookup"><span data-stu-id="49a9e-200">Logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="49a9e-201">SCC Adminは、「従業員解雇」、「従業員雇用」などの従業員関連のイベントタイプを作成します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-201">SCC Admin creates employee related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="49a9e-202">SCC Adminは、「従業員保持」ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-202">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="49a9e-203">この「従業員の保持」ラベルを SharePoint で公開し、従業員ファイルに手動または自動で適用します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-203">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint</span></span>

  - <span data-ttu-id="49a9e-204">Workday などの人事管理システムを Microsoft Flow と連携させ、従業員ファイルの管理を定期的に実行できます</span><span class="sxs-lookup"><span data-stu-id="49a9e-204">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files</span></span>

  - <span data-ttu-id="49a9e-205">従業員が組織のメンバーではなくなると、Flow によって M365 イベント ベースの保持 REST API がトリガーされ、特定の従業員ファイルの保持期間が開始されます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-205">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="49a9e-206">Microsoft Flow の使用</span><span class="sxs-lookup"><span data-stu-id="49a9e-206">Using Microsoft Flow</span></span>

<span data-ttu-id="49a9e-207">手順 1 - Microsoft 365 REST API を使用してイベントを作成するフローを作成します</span><span class="sxs-lookup"><span data-stu-id="49a9e-207">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Flow を使用してイベントを作成する](media/automate-event-driven-retention-flow-1.png)

![Flow を使用して REST API を呼び出す](media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="49a9e-210">イベントを作成する</span><span class="sxs-lookup"><span data-stu-id="49a9e-210">Create an event</span></span>

<span data-ttu-id="49a9e-211">REST API を呼び出すサンプル コード</span><span class="sxs-lookup"><span data-stu-id="49a9e-211">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="49a9e-212">メソッド</span><span class="sxs-lookup"><span data-stu-id="49a9e-212">Method</span></span></th>
<th><span data-ttu-id="49a9e-213">POST</span><span class="sxs-lookup"><span data-stu-id="49a9e-213">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="49a9e-214">URL</span><span class="sxs-lookup"><span data-stu-id="49a9e-214">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent)</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49a9e-215">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="49a9e-215">Headers</span></span></td>
<td><span data-ttu-id="49a9e-216">Content-Type</span><span class="sxs-lookup"><span data-stu-id="49a9e-216">Content-Type</span></span></td>
<td><span data-ttu-id="49a9e-217">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="49a9e-217">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="49a9e-218">本文</span><span class="sxs-lookup"><span data-stu-id="49a9e-218">Body</span></span></td>
<td><p><span data-ttu-id="49a9e-219">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-219">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="49a9e-220">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="49a9e-220">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="49a9e-221">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="49a9e-221">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="49a9e-222">xmlns='http://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-222">xmlns='http://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="49a9e-223">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-223">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="49a9e-224">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-224">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="49a9e-225">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-225">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="49a9e-226">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-226">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="49a9e-227">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-227">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="49a9e-228">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-228">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="49a9e-229">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-229">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="49a9e-230">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-230">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="49a9e-231">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-231">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="49a9e-232">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-232">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="49a9e-233">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-233">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49a9e-234">認証</span><span class="sxs-lookup"><span data-stu-id="49a9e-234">Authentication</span></span></td>
<td><span data-ttu-id="49a9e-235">基本</span><span class="sxs-lookup"><span data-stu-id="49a9e-235">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="49a9e-236">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="49a9e-236">Username</span></span></td>
<td><span data-ttu-id="49a9e-237">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="49a9e-237">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49a9e-238">パスワード</span><span class="sxs-lookup"><span data-stu-id="49a9e-238">Password</span></span></td>
<td><span data-ttu-id="49a9e-239">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="49a9e-239">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="49a9e-240">利用可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="49a9e-240">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="49a9e-241"><strong>パラメーター</strong></span><span class="sxs-lookup"><span data-stu-id="49a9e-241"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="49a9e-242"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="49a9e-242"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="49a9e-243"><strong>メモ</strong></span><span class="sxs-lookup"><span data-stu-id="49a9e-243"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="49a9e-244">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-244">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="49a9e-245">イベントの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-245">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="49a9e-p120">末尾にスペースおよび以下の文字を含めることはできません: % \* \ &amp; &lt; &gt; | # ? , : ;</span><span class="sxs-lookup"><span data-stu-id="49a9e-p120">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49a9e-248">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-248">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="49a9e-249">イベントの種類の名前 (または GUID) を入力します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-249">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="49a9e-p121">例: 「従業員の退職」というイベントの種類を保持ラベルに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p121">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="49a9e-252">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-252">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="49a9e-253">“ComplianceAssetId:” と従業員 ID を入力します</span><span class="sxs-lookup"><span data-stu-id="49a9e-253">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="49a9e-254">例: &quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="49a9e-254">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49a9e-255">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-255">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="49a9e-256">イベントの日時</span><span class="sxs-lookup"><span data-stu-id="49a9e-256">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="49a9e-257">形式: yyyy-MM-ddTHH:mm:ssZ。例:</span><span class="sxs-lookup"><span data-stu-id="49a9e-257">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="49a9e-258">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="49a9e-258">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="49a9e-259">応答コード</span><span class="sxs-lookup"><span data-stu-id="49a9e-259">Response codes</span></span>

| <span data-ttu-id="49a9e-260">**応答コード**</span><span class="sxs-lookup"><span data-stu-id="49a9e-260">**Response Code**</span></span> | <span data-ttu-id="49a9e-261">**説明**</span><span class="sxs-lookup"><span data-stu-id="49a9e-261">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="49a9e-262">302</span><span class="sxs-lookup"><span data-stu-id="49a9e-262">302</span></span>               | <span data-ttu-id="49a9e-263">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="49a9e-263">Redirect</span></span>              |
| <span data-ttu-id="49a9e-264">201</span><span class="sxs-lookup"><span data-stu-id="49a9e-264">201</span></span>               | <span data-ttu-id="49a9e-265">作成済み</span><span class="sxs-lookup"><span data-stu-id="49a9e-265">Created</span></span>               |
| <span data-ttu-id="49a9e-266">403</span><span class="sxs-lookup"><span data-stu-id="49a9e-266">403</span></span>               | <span data-ttu-id="49a9e-267">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="49a9e-267">Authorization Failed</span></span>  |
| <span data-ttu-id="49a9e-268">401</span><span class="sxs-lookup"><span data-stu-id="49a9e-268">401</span></span>               | <span data-ttu-id="49a9e-269">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="49a9e-269">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="49a9e-270">時間範囲に基づいてイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="49a9e-270">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="49a9e-271">メソッド</span><span class="sxs-lookup"><span data-stu-id="49a9e-271">Method</span></span></th>
<th><span data-ttu-id="49a9e-272">GET</span><span class="sxs-lookup"><span data-stu-id="49a9e-272">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="49a9e-273">URL</span><span class="sxs-lookup"><span data-stu-id="49a9e-273">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="49a9e-274">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span><span class="sxs-lookup"><span data-stu-id="49a9e-274">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49a9e-275">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="49a9e-275">Headers</span></span></td>
<td><span data-ttu-id="49a9e-276">Content-Type</span><span class="sxs-lookup"><span data-stu-id="49a9e-276">Content-Type</span></span></td>
<td><span data-ttu-id="49a9e-277">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="49a9e-277">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49a9e-278">認証</span><span class="sxs-lookup"><span data-stu-id="49a9e-278">Authentication</span></span></td>
<td><span data-ttu-id="49a9e-279">基本</span><span class="sxs-lookup"><span data-stu-id="49a9e-279">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="49a9e-280">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="49a9e-280">Username</span></span></td>
<td><span data-ttu-id="49a9e-281">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="49a9e-281">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49a9e-282">パスワード</span><span class="sxs-lookup"><span data-stu-id="49a9e-282">Password</span></span></td>
<td><span data-ttu-id="49a9e-283">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="49a9e-283">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="49a9e-284">応答コード</span><span class="sxs-lookup"><span data-stu-id="49a9e-284">Response codes</span></span>

| <span data-ttu-id="49a9e-285">**応答コード**</span><span class="sxs-lookup"><span data-stu-id="49a9e-285">**Response Code**</span></span> | <span data-ttu-id="49a9e-286">**説明**</span><span class="sxs-lookup"><span data-stu-id="49a9e-286">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="49a9e-287">200</span><span class="sxs-lookup"><span data-stu-id="49a9e-287">200</span></span>               | <span data-ttu-id="49a9e-288">問題ありません。イベントの一覧は atom+ xml 形式です</span><span class="sxs-lookup"><span data-stu-id="49a9e-288">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="49a9e-289">404</span><span class="sxs-lookup"><span data-stu-id="49a9e-289">404</span></span>               | <span data-ttu-id="49a9e-290">見つかりません</span><span class="sxs-lookup"><span data-stu-id="49a9e-290">Not found</span></span>                         |
| <span data-ttu-id="49a9e-291">302</span><span class="sxs-lookup"><span data-stu-id="49a9e-291">302</span></span>               | <span data-ttu-id="49a9e-292">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="49a9e-292">Redirect</span></span>                          |
| <span data-ttu-id="49a9e-293">401</span><span class="sxs-lookup"><span data-stu-id="49a9e-293">401</span></span>               | <span data-ttu-id="49a9e-294">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="49a9e-294">Authorization Failed</span></span>              |
| <span data-ttu-id="49a9e-295">403</span><span class="sxs-lookup"><span data-stu-id="49a9e-295">403</span></span>               | <span data-ttu-id="49a9e-296">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="49a9e-296">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="49a9e-297">ID でイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="49a9e-297">Get an event by ID</span></span>

| <span data-ttu-id="49a9e-298">メソッド</span><span class="sxs-lookup"><span data-stu-id="49a9e-298">Method</span></span>         | <span data-ttu-id="49a9e-299">GET</span><span class="sxs-lookup"><span data-stu-id="49a9e-299">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="49a9e-300">URL</span><span class="sxs-lookup"><span data-stu-id="49a9e-300">URL</span></span>            | <span data-ttu-id="49a9e-301">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="49a9e-301">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="49a9e-302">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="49a9e-302">Header</span></span>         | <span data-ttu-id="49a9e-303">Content-Type</span><span class="sxs-lookup"><span data-stu-id="49a9e-303">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="49a9e-304">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="49a9e-304">application/atom+xml</span></span> |
| <span data-ttu-id="49a9e-305">認証</span><span class="sxs-lookup"><span data-stu-id="49a9e-305">Authentication</span></span> | <span data-ttu-id="49a9e-306">基本</span><span class="sxs-lookup"><span data-stu-id="49a9e-306">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="49a9e-307">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="49a9e-307">Username</span></span>       | <span data-ttu-id="49a9e-308">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="49a9e-308">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="49a9e-309">パスワード</span><span class="sxs-lookup"><span data-stu-id="49a9e-309">Password</span></span>       | <span data-ttu-id="49a9e-310">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="49a9e-310">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="49a9e-311">応答コード</span><span class="sxs-lookup"><span data-stu-id="49a9e-311">Response codes</span></span>

| <span data-ttu-id="49a9e-312">**応答コード**</span><span class="sxs-lookup"><span data-stu-id="49a9e-312">**Response Code**</span></span> | <span data-ttu-id="49a9e-313">**説明**</span><span class="sxs-lookup"><span data-stu-id="49a9e-313">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="49a9e-314">200</span><span class="sxs-lookup"><span data-stu-id="49a9e-314">200</span></span>               | <span data-ttu-id="49a9e-315">問題ありません。応答本体に atom+xml 形式のイベントが含まれています</span><span class="sxs-lookup"><span data-stu-id="49a9e-315">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="49a9e-316">404</span><span class="sxs-lookup"><span data-stu-id="49a9e-316">404</span></span>               | <span data-ttu-id="49a9e-317">見つかりません</span><span class="sxs-lookup"><span data-stu-id="49a9e-317">Not found</span></span>                                            |
| <span data-ttu-id="49a9e-318">302</span><span class="sxs-lookup"><span data-stu-id="49a9e-318">302</span></span>               | <span data-ttu-id="49a9e-319">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="49a9e-319">Redirect</span></span>                                             |
| <span data-ttu-id="49a9e-320">401</span><span class="sxs-lookup"><span data-stu-id="49a9e-320">401</span></span>               | <span data-ttu-id="49a9e-321">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="49a9e-321">Authorization Failed</span></span>                                 |
| <span data-ttu-id="49a9e-322">403</span><span class="sxs-lookup"><span data-stu-id="49a9e-322">403</span></span>               | <span data-ttu-id="49a9e-323">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="49a9e-323">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="49a9e-324">名前でイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="49a9e-324">Get an event by name</span></span>

| <span data-ttu-id="49a9e-325">メソッド</span><span class="sxs-lookup"><span data-stu-id="49a9e-325">Method</span></span>         | <span data-ttu-id="49a9e-326">GET</span><span class="sxs-lookup"><span data-stu-id="49a9e-326">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="49a9e-327">URL</span><span class="sxs-lookup"><span data-stu-id="49a9e-327">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="49a9e-328">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="49a9e-328">Headers</span></span>        | <span data-ttu-id="49a9e-329">Content-Type</span><span class="sxs-lookup"><span data-stu-id="49a9e-329">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="49a9e-330">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="49a9e-330">application/atom+xml</span></span> |
| <span data-ttu-id="49a9e-331">認証</span><span class="sxs-lookup"><span data-stu-id="49a9e-331">Authentication</span></span> | <span data-ttu-id="49a9e-332">基本</span><span class="sxs-lookup"><span data-stu-id="49a9e-332">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="49a9e-333">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="49a9e-333">Username</span></span>       | <span data-ttu-id="49a9e-334">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="49a9e-334">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="49a9e-335">パスワード</span><span class="sxs-lookup"><span data-stu-id="49a9e-335">Password</span></span>       | <span data-ttu-id="49a9e-336">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="49a9e-336">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="49a9e-337">応答コード</span><span class="sxs-lookup"><span data-stu-id="49a9e-337">Response codes</span></span>

| <span data-ttu-id="49a9e-338">**応答コード**</span><span class="sxs-lookup"><span data-stu-id="49a9e-338">**Response Code**</span></span> | <span data-ttu-id="49a9e-339">**説明**</span><span class="sxs-lookup"><span data-stu-id="49a9e-339">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="49a9e-340">200</span><span class="sxs-lookup"><span data-stu-id="49a9e-340">200</span></span>               | <span data-ttu-id="49a9e-341">問題ありません。応答本体に atom+xml 形式のイベントが含まれています</span><span class="sxs-lookup"><span data-stu-id="49a9e-341">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="49a9e-342">404</span><span class="sxs-lookup"><span data-stu-id="49a9e-342">404</span></span>               | <span data-ttu-id="49a9e-343">見つかりません</span><span class="sxs-lookup"><span data-stu-id="49a9e-343">Not found</span></span>                                            |
| <span data-ttu-id="49a9e-344">302</span><span class="sxs-lookup"><span data-stu-id="49a9e-344">302</span></span>               | <span data-ttu-id="49a9e-345">リダイレクト</span><span class="sxs-lookup"><span data-stu-id="49a9e-345">Redirect</span></span>                                             |
| <span data-ttu-id="49a9e-346">401</span><span class="sxs-lookup"><span data-stu-id="49a9e-346">401</span></span>               | <span data-ttu-id="49a9e-347">承認に失敗しました</span><span class="sxs-lookup"><span data-stu-id="49a9e-347">Authorization Failed</span></span>                                 |
| <span data-ttu-id="49a9e-348">403</span><span class="sxs-lookup"><span data-stu-id="49a9e-348">403</span></span>               | <span data-ttu-id="49a9e-349">認証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="49a9e-349">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="49a9e-350">PowerShell (ver.6 以降) または任意の HTTP クライアントの使用</span><span class="sxs-lookup"><span data-stu-id="49a9e-350">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="49a9e-351">手順 1: PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-351">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="49a9e-352">手順 2: 次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-352">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49a9e-353">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="49a9e-353">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="49a9e-354">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="49a9e-354">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="49a9e-355">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="49a9e-355">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="49a9e-356">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="49a9e-356">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="49a9e-357">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="49a9e-357">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="49a9e-358">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="49a9e-358">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="49a9e-359">Write-Host &quot;Start to create an event with name: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="49a9e-359">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="49a9e-360">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-360">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="49a9e-361">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="49a9e-361">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="49a9e-362">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="49a9e-362">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="49a9e-363">xmlns='http://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-363">xmlns='http://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="49a9e-364">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-364">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="49a9e-365">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-365">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="49a9e-366">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-366">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="49a9e-367">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-367">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="49a9e-368">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-368">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="49a9e-369">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-369">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="49a9e-370">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-370">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="49a9e-371">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-371">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="49a9e-372">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="49a9e-372">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="49a9e-373">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="49a9e-373">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="49a9e-374">$event = $null</span><span class="sxs-lookup"><span data-stu-id="49a9e-374">$event = $null</span></span></p>
<p><span data-ttu-id="49a9e-375">try</span><span class="sxs-lookup"><span data-stu-id="49a9e-375">try</span></span></p>
<p><span data-ttu-id="49a9e-376">{</span><span class="sxs-lookup"><span data-stu-id="49a9e-376">{</span></span></p>
<p><span data-ttu-id="49a9e-377">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="49a9e-377">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="49a9e-378">}</span><span class="sxs-lookup"><span data-stu-id="49a9e-378">}</span></span></p>
<p><span data-ttu-id="49a9e-379">catch</span><span class="sxs-lookup"><span data-stu-id="49a9e-379">catch</span></span></p>
<p><span data-ttu-id="49a9e-380">{</span><span class="sxs-lookup"><span data-stu-id="49a9e-380">{</span></span></p>
<p><span data-ttu-id="49a9e-381">$response = $_.Exception.Response</span><span class="sxs-lookup"><span data-stu-id="49a9e-381">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="49a9e-382">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="49a9e-382">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="49a9e-383">{</span><span class="sxs-lookup"><span data-stu-id="49a9e-383">{</span></span></p>
<p><span data-ttu-id="49a9e-384">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="49a9e-384">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="49a9e-385">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="49a9e-385">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="49a9e-386">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="49a9e-386">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="49a9e-387">}</span><span class="sxs-lookup"><span data-stu-id="49a9e-387">}</span></span></p>
<p><span data-ttu-id="49a9e-388">}</span><span class="sxs-lookup"><span data-stu-id="49a9e-388">}</span></span></p>
<p><span data-ttu-id="49a9e-389">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="49a9e-389">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="49a9e-390">両方のオプションの結果を確認する</span><span class="sxs-lookup"><span data-stu-id="49a9e-390">Verify the outcome in both options</span></span>

<span data-ttu-id="49a9e-391">手順 1: セキュリティ/コンプライアンス センターに移動します</span><span class="sxs-lookup"><span data-stu-id="49a9e-391">Step 1: Go to Security & Compliance Center</span></span>

<span data-ttu-id="49a9e-392">手順 2: [データ ガバナンス] の [イベント] をクリックします</span><span class="sxs-lookup"><span data-stu-id="49a9e-392">Step 2: Click on Events under Data Governance</span></span>

<span data-ttu-id="49a9e-393">手順 3: イベントが作成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-393">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="49a9e-394">同様に、イベント ベースの保持を自動化する上記のオプションを以下のシナリオに使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-394">Similarly, the above options to automate event based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="49a9e-395">シナリオ 2: 契約の期限切れ</span><span class="sxs-lookup"><span data-stu-id="49a9e-395">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="49a9e-p122">組織には、顧客、ベンダー、パートナーとの単一の契約向けの複数のレコードが存在することがあります。こうした文書は、SharePoint などの文書ライブラリに格納できます。契約の終了は、対象の契約に関連付けられている文書の保持期間の開始時期に基づいて判別されます。たとえば、契約に関連するすべてのレコードは契約の有効期限後、5 年間は保持する必要があります。契約の期限切れは、5 年間の保持期間をトリガーするイベントとなります。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p122">An organization can have multiple records for a single contract with customers, vendors and partners. These documents can reside in a document library like SharePoint. The ending of a contract determines the start of the retention period of the documents associated with the contract. For example: all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="49a9e-401">顧客関係管理 (CRM) システムを Microsoft 365 と連携させ、契約文書の保持をトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-401">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="49a9e-402">**このシナリオに関する自動化されたイベント ベースの保持を構成する:**</span><span class="sxs-lookup"><span data-stu-id="49a9e-402">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![契約の有効期限シナリオの役割とタスクの図](media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="49a9e-404">管理者は、契約の種類ごとにさまざまなフォルダーを含む SharePoint ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-404">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="49a9e-405">管理者は、ライセンス契約書、開発契約などの契約ファイル意を各契約フォルダーに追加します</span><span class="sxs-lookup"><span data-stu-id="49a9e-405">Admin adds contract files such as License Contracts, Development Contracts to each contract folder</span></span>

  - <span data-ttu-id="49a9e-406">管理者は、各契約フォルダーにアセット ID を割り当てます</span><span class="sxs-lookup"><span data-stu-id="49a9e-406">Admin assigns Asset Id to each contract folder</span></span>

  - <span data-ttu-id="49a9e-407">SCC 管理者がセキュリティ/コンプライアンス センターにログインします</span><span class="sxs-lookup"><span data-stu-id="49a9e-407">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="49a9e-408">SCC Adminは、 「契約締結」、 「契約解消」イベントなどの契約関連イベントタイプを作成します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-408">SCC Admin creates contract related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="49a9e-409">SCC Adminは「契約解消」ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-409">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="49a9e-410">この「契約の有効期限」ラベルを SharePoint で公開し、契約ファイルに手動または自動で適用します</span><span class="sxs-lookup"><span data-stu-id="49a9e-410">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint</span></span>

  - <span data-ttu-id="49a9e-411">契約管理システムを Microsoft Flow または同様のアプリケーションと連携させ、契約ファイルの管理を定期的に実行できます</span><span class="sxs-lookup"><span data-stu-id="49a9e-411">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files</span></span>

  - <span data-ttu-id="49a9e-412">契約の期限が切れると、Microsoft Flow によって M365 イベント ベースの保持 REST API がトリガーされ、特定の契約ファイルの保持期間が開始されます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-412">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="49a9e-413">シナリオ 3: 製品製造の終了</span><span class="sxs-lookup"><span data-stu-id="49a9e-413">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="49a9e-p123">さまざまな製品群を生み出す製造企業は、多数の製造仕様と価格に関する文書を作成します。製品が製造されなくなると、その製品にリンクされているすべての仕様と文書は、製品のライフサイクル後、特定に期間にわたり保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49a9e-p123">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="49a9e-416">エンタープライズ リソース プランニング (ERP) システムを Microsoft 365 および Microsoft Flow と連携させ、保持をトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-416">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="49a9e-417">**このシナリオに関する自動化されたイベント ベースの保持を構成する:**</span><span class="sxs-lookup"><span data-stu-id="49a9e-417">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![製品のライフサイクル シナリオの役割とタスクの図](media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="49a9e-419">管理者は、製品 1、製品 2 などの製品フォルダーを文書セットに作成します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-419">Admin creates product folders in the Document set such as Product 1, Product 2, etc.</span></span>

  - <span data-ttu-id="49a9e-420">管理者は、「製造仕様」、「製品価格」、「製品ライセンス」などの製品ファイルを各製品フォルダーに追加します</span><span class="sxs-lookup"><span data-stu-id="49a9e-420">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder</span></span>

  - <span data-ttu-id="49a9e-421">管理者は、各製品フォルダーにアセット ID を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-421">Admin assigns Asset Id to each productfolder.</span></span>

  - <span data-ttu-id="49a9e-422">SCC 管理者がセキュリティ/コンプライアンス センターにログインします</span><span class="sxs-lookup"><span data-stu-id="49a9e-422">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="49a9e-423">SCC Adminは、「製造開始」、「製造終了」などの従業員関連のイベントタイプを作成します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-423">SCC Admin creates employee related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="49a9e-424">SCC Adminは「製造終了」ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-424">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="49a9e-425">この「製品製造の終了」ラベルを SharePoint で公開し、製品ファイルに手動または自動で適用します</span><span class="sxs-lookup"><span data-stu-id="49a9e-425">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint</span></span>

  - <span data-ttu-id="49a9e-426">ERP システムを Microsoft Flow または同様のアプリケーションと連携させ、製品ファイルの管理を定期的に実行できます</span><span class="sxs-lookup"><span data-stu-id="49a9e-426">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files</span></span>

  - <span data-ttu-id="49a9e-427">製品製造が終了すると、Microsoft Flow によって M365 イベント ベースの保持 REST API がトリガーされ、特定の製品ファイルの保持期間が開始されます。</span><span class="sxs-lookup"><span data-stu-id="49a9e-427">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="49a9e-428">付録</span><span class="sxs-lookup"><span data-stu-id="49a9e-428">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="49a9e-429">リダイレクト 302 応答結果を使用して REST API を呼び出す</span><span class="sxs-lookup"><span data-stu-id="49a9e-429">Using Redirect 302 response results to call the REST API</span></span>

1.  <span data-ttu-id="49a9e-430">REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> を使用して、POST 保持イベント呼び出しを実行します (全体管理者のアクセス許可が必要です)</span><span class="sxs-lookup"><span data-stu-id="49a9e-430">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2.  <span data-ttu-id="49a9e-p124">応答コードを確認し、302 の場合、応答ヘッダーの場所プロパティから、リダイレクトされた URL を取得します</span><span class="sxs-lookup"><span data-stu-id="49a9e-p124">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3.  <span data-ttu-id="49a9e-433">リダイレクトされた URL を使用して、もう一度 POST 保持イベント呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-433">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="49a9e-434">開発者情報</span><span class="sxs-lookup"><span data-stu-id="49a9e-434">Credits</span></span>

<span data-ttu-id="49a9e-435">このトピックの校閲者をご紹介します。</span><span class="sxs-lookup"><span data-stu-id="49a9e-435">This topic was reviewed by:</span></span>

<span data-ttu-id="49a9e-436">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="49a9e-436">Antonio Maio</span></span><br/><span data-ttu-id="49a9e-437">Microsoft Office アプリとサービスの MVP</span><span class="sxs-lookup"><span data-stu-id="49a9e-437">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="49a9e-438">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="49a9e-438">Antonio.Maio@Protiviti.com</span></span>
