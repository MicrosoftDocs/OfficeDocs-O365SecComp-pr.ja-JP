---
title: Office 365 監査ログを検索して一般的なシナリオのトラブルシューティングを行う
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
description: Office 365 監査ログ検索ツールを使用すると、侵害されたアカウントを調査する、メールボックスのメール転送を誰が設定したかを識別する、などの一般的な問題のトラブルシューティングに役立ちます。
ms.openlocfilehash: 301c8a19c5e268b1c4e3ff0e9633c85a31fd3f4d
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220877"
---
# <a name="search-the-office-365-audit-log-to-troubleshoot-common-scenarios"></a><span data-ttu-id="88b8b-103">Office 365 監査ログを検索して一般的なシナリオのトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="88b8b-103">Search the Office 365 audit log to troubleshoot common scenarios</span></span>

<span data-ttu-id="88b8b-p101">この記事では、一般的なサポート シナリオのトラブルシューティングに役立つ Office 365 監査ログ検索ツールの使用方法をご紹介します。監査ログを使用して、以下のことが可能です。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p101">This article describes how to use the Office 365 audit log search tool to help you troubleshoot common support scenarios. This includes using the audit log to:</span></span>

- <span data-ttu-id="88b8b-106">侵害されたアカウントにアクセスするために使用されたコンピューターの IP アドレスを見つける</span><span class="sxs-lookup"><span data-stu-id="88b8b-106">Find the IP address of the computer used to access a compromised account</span></span>
- <span data-ttu-id="88b8b-107">誰がメールボックスの電子メール転送を設定したかを判別する</span><span class="sxs-lookup"><span data-stu-id="88b8b-107">Determine who set up email forwarding for a mailbox</span></span>
- <span data-ttu-id="88b8b-108">あるユーザーが自分のメールボックスのメール項目を削除したかどうかを判別する</span><span class="sxs-lookup"><span data-stu-id="88b8b-108">Determine if a user deleted email items in their mailbox</span></span>
- <span data-ttu-id="88b8b-109">ユーザーが受信トレイ ルールを作成したかどうかを判別する</span><span class="sxs-lookup"><span data-stu-id="88b8b-109">Determine if a user created an inbox rule</span></span>

## <a name="using-the-office-365-audit-log-search-tool"></a><span data-ttu-id="88b8b-110">Office 365 監査ログ検索ツールを使用する</span><span class="sxs-lookup"><span data-stu-id="88b8b-110">Using the Office 365 audit log search tool</span></span>

<span data-ttu-id="88b8b-p102">この記事に示すトラブルシューティングの各シナリオは、Office 365 セキュリティ/コンプライアンス センターの監査ログ検索ツールを使用する場合に基づいています。このセクションでは、監査ログを検索するのに必要なアクセス許可を示し、監査ログ検索機能にアクセスして実行する手順を示します。各シナリオのセクションでは、監査ログの検索クエリを構成する方法と、検索条件に一致した監査レコードの詳細情報の中から何を探すべきかについて具体的に示します。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p102">Each of the troubleshooting scenarios described in this article are based on using the audit log search tool in the Office 365 Security & Compliance Center. This section lists the permissions required to search the audit log and describes the steps to access and run audit log searches. Each scenario section provides specific guidance about how to configure an audit log search query and what to look for in the detailed information in the audit records that match the search criteria.</span></span>

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a><span data-ttu-id="88b8b-114">監査ログ検索ツールを使用するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="88b8b-114">Permissions required to use the audit log search tool</span></span>

<span data-ttu-id="88b8b-p103">Office 365 監査ログを検索するには、Exchange Online で監査ログの役割、または監査ログ表示専用の役割を与えられている必要があります。既定で、これらの役割は Exchange 管理センターの [**アクセス許可**] ページで「コンプライアンス管理」および「組織の管理」役割グループに割り当てられます。詳しくは、「[Exchange Online の役割グループの管理](https://go.microsoft.com/fwlink/p/?LinkID=730688)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p103">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log. By default, these roles are assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. For more information, see [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).</span></span>

### <a name="running-audit-log-searches"></a><span data-ttu-id="88b8b-118">監査ログ検索の実行</span><span class="sxs-lookup"><span data-stu-id="88b8b-118">Running audit log searches</span></span>

<span data-ttu-id="88b8b-p104">このセクションでは、監査ログの検索を作成して実行する基本的な方法を示します。この記事のそれぞれのトラブルシューティング シナリオでは、下記の手順に従って操作を開始してください。手順ごとの詳しい説明については、「[Office 365 のセキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p104">This section describes the basics for creating and running audit log searches. Use these instructions as a starting point for each troubleshooting scenario in this article. For more detailed step-by-step instructions, see [Search the audit log in the Office 365 Security & Compliance Center ](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).</span></span>

1. <span data-ttu-id="88b8b-122">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="88b8b-122">Go to [https://protection.office.com](https://protection.office.com).</span></span>
  
2. <span data-ttu-id="88b8b-123">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="88b8b-123">Sign in to Office 365 using your work or school account.</span></span>

3. <span data-ttu-id="88b8b-124">セキュリティ センターとコンプライアンス センターの左側のウィンドウで、[**検索と調査**]  >  [**監査ログの検索**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="88b8b-124">In the left pane of the Security & Compliance Center, click **Search & investigation** > **Audit log search**.</span></span>
    
    <span data-ttu-id="88b8b-125">[**監査ログの検索**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88b8b-125">The **Audit log search** page is displayed.</span></span> 
    
    ![条件を設定し、[検索] をクリックして検索を実行します](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. <span data-ttu-id="88b8b-p105">次の検索条件を構成できます。なお、この記事のそれぞれのトラブルシューティング シナリオでは、これらのフィールドの推奨設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p105">You can configure the following search criteria. Note that each troubleshooting scenario in this article will recommend specific guidance for configuring these fields.</span></span>
    
    <span data-ttu-id="88b8b-p106">a. **アクティビティ** - ドロップダウン リストをクリックすると、検索可能なアクティビティが表示されます。検索の実行後、選択したアクティビティに関する監査レコードだけが表示されます。[**すべてのアクティビティの結果を表示**] を選択すると、その他の検索条件を満たすすべてのアクティビティに関する結果が表示されます。トラブルシューティング シナリオによっては、このフィールドを空白のままにすべき場合があります。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p106">a. **Activities** - Click the drop-down list to display the activities that you can search for. After you run the search, only the audit records for the selected activities are displayed. Selecting **Show results for all activities** will display results for all activities that meet the other search criteria. You'll also have to leave this field blank in some of the troubleshooting scenarios.</span></span>
    
    <span data-ttu-id="88b8b-p107">b. **開始日**と**終了日**。特定の期間内に発生したイベントを表示するには、その日付と時刻の範囲を選択します。既定では過去 7 日間が選択されています。日付と時刻は、協定世界時 (UTC) 形式で指定します。指定できる最大の日付範囲は 90 日間です。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p107">b. **Start date** and **End date** - Select a date and time range to display the events that occurred within that period. The last seven days are selected by default. The date and time are presented in Coordinated Universal Time (UTC) format. The maximum date range that you can specify is 90 days.</span></span>

    <span data-ttu-id="88b8b-p108">c. **ユーザー**。このボックスをクリックして、検索結果を表示する対象の 1 人以上のユーザーを選択します。このボックスで選択したユーザーによって実行された、選択されたアクティビティの監査レコードが結果の一覧に表示されます。組織のすべてのユーザー (およびサービス アカウント) のエントリを返すには、このボックスを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p108">c. **Users** - Click in this box and then select one or more users to display search results for. Audit records for the selected activity performed by the users you select in this box are displayed in the list of results. Leave this box blank to return entries for all users (and service accounts) in your organization.</span></span>
    
    <span data-ttu-id="88b8b-p109">d. **ファイル、フォルダー、サイトなど** - 特定のキーワードを含むファイルまたはフォルダーに関するアクティビティを検索するには、ファイルまたはフォルダー名の一部またはすべてを入力します。ファイルまたはフォルダーの URL を指定することもできます。URL を使用する場合、必ず全ての URL パスを入力してください。URL の一部だけを入力する場合は、特殊文字やスペースを含めることはできません。このボックスを空白のままにすると、組織のすべてのファイルとフォルダーに関する項目が返されます。なお、この記事のすべてのトラブルシューティング シナリオではこのフィールドを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p109">d. **File, folder, or site** - Type some or all of a file or folder name to search for activity related to the file of folder that contains the specified keyword. You can also specify a URL of a file or folder. If you use a URL, be sure the type the full URL path or if you just type a portion of the URL, don't include any special characters or spaces. Leave this box blank to return entries for all files and folders in your organization. Note that this field is left blank in all the troubleshooting scenarios in this article.</span></span>
    
5. <span data-ttu-id="88b8b-149">[**検索**] をクリックして、設定した検索条件で検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="88b8b-149">Click **Search** to run the search using your search criteria.</span></span> 
    
    <span data-ttu-id="88b8b-p110">検索結果が読み込まれ、少し待つと [**監査ログの検索**] ページの [**結果**] の下に結果が表示されます。以下の各セクションでは、特定のトラブルシューティング シナリオでどんな情報を探すべきかを説明します。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p110">The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page. Each to the following sections will provide guidance about things to look for the specific troubleshooting scenario.</span></span>

    <span data-ttu-id="88b8b-152">監査ログの検索結果の表示、フィルター処理、エクスポートに関する詳細は、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88b8b-152">For more information about viewing, filtering, or exporting audit log search results, see:</span></span>

    - [<span data-ttu-id="88b8b-153">検索結果を表示する</span><span class="sxs-lookup"><span data-stu-id="88b8b-153">View search results</span></span>](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [<span data-ttu-id="88b8b-154">検索結果をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="88b8b-154">Filter search results</span></span>](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [<span data-ttu-id="88b8b-155">検索結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="88b8b-155">Export search results</span></span>](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="finding-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a><span data-ttu-id="88b8b-156">侵害されたアカウントへのアクセスに使用されたコンピューターの IP アドレスを見つける</span><span class="sxs-lookup"><span data-stu-id="88b8b-156">Finding the IP address of the computer used to access a compromised account</span></span>

<span data-ttu-id="88b8b-p111">ほとんどの監査レコードには、任意のユーザーによって実行されたアクティビティに対応する IP アドレスが含まれています。また、使用されたクライアントについての情報も監査レコードにも含まれます。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p111">The IP address corresponding to an activity performed by any user is included in most audit records. Information about the client used is also included in the audit record.</span></span>

<span data-ttu-id="88b8b-159">このシナリオで監査ログの検索クエリを構成する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="88b8b-159">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="88b8b-p112">**アクティビティ** - 該当する場合は、検索対象となる具体的なアクティビティを選択します。侵害されたアカウントのトラブルシューティングの場合は、[**Exchange メールボックス アクティビティ**] の下の [**メールボックスへのユーザーのサインイン**] アクティビティを選択することを考慮してください。これにより、メールボックスへのサインインで使われた IP アドレスを含む監査レコードが返されます。あるいは、このフィールドを空白のままにすると、すべてのアクティビティに関するレコードが返されます。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p112">**Activities** - If relevant to your case, select a specific activity to search for. For troubleshooting compromised accounts, consider selecting the **User signed in to mailbox** activity under **Exchange mailbox activities**. This will return auditing records showing the IP address that was use when signing in to the mailbox. Otherwise, leave this field blank to return audit records for all activities.</span></span> 

> [!TIP]
> <span data-ttu-id="88b8b-p113">このフィールドを空白のままにしたときに返される **UserLoggedIn** アクティビティは、誰かが Office 365 ユーザー アカウントにサインインしたことを示す Azure Active Directory アクティビティです。検索結果でフィルターを使用すると、**UserLoggedIn** 監査レコードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p113">Leaving this field blank will  return **UserLoggedIn** activities, which is an Azure Active Directory activity that indicates that someone has signed in to an Office 365 user account. Use filtering in the search results to display the **UserLoggedIn** audit records.</span></span>

<span data-ttu-id="88b8b-166">**開始日**と**終了日** - 調査の対象となる日付範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="88b8b-166">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="88b8b-p114">**ユーザー** - 侵害されたアカウントを調査している場合は、アカウントが侵害されたユーザーを選択します。これにより、そのユーザー アカウントで実行されたアクティビティに関する監査レコードが返されます。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p114">**Users** - If you're investigating a compromised account, select the user whose account was compromised. This will return audit records for activities performed by that user account.</span></span>

<span data-ttu-id="88b8b-169">**ファイル、フォルダー、またはサイト** - このフィールドは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="88b8b-169">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="88b8b-p115">検索の実行後、各アクティビティの IP アドレスが検索結果の [**IP アドレス**] 列に表示されます。検索結果の中のレコードをクリックすると、より詳細な情報がポップアップ ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p115">After you run the search, the IP address for each activity is displayed in the **IP address** column in the search results. Click the record in the search results to view more detailed information on the flyout page.</span></span>

## <a name="determining-who-set-up-email-forwarding-for-a-mailbox"></a><span data-ttu-id="88b8b-172">メールボックスの電子メール転送を誰が設定したかを判別する</span><span class="sxs-lookup"><span data-stu-id="88b8b-172">Determining who set up email forwarding for a mailbox</span></span>

<span data-ttu-id="88b8b-p116">あるメールボックスの電子メール転送が構成されている場合、メールボックスに送られた電子メール メッセージは別のメールボックスに転送されます。組織の内部ユーザーと外部ユーザーのどちらにもメッセージが転送される可能性があります。メールボックスで電子メール転送が設定されると、基盤となる Exchange Online cmdlet の **Set-Mailbox** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p116">When email forwarding is configured for a mailbox, email messages that are sent to the mailbox are forwarded to another mailbox. Messages can be forwarded to users inside or outside of your organization. When email forwarding is set up on a mailbox, the underlying Exchange Online cmdlet that's used is **Set-Mailbox**.</span></span>

<span data-ttu-id="88b8b-176">このシナリオで監査ログの検索クエリを構成する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="88b8b-176">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="88b8b-p117">**アクティビティ** - このフィールドを空白のままにして、すべてのアクティビティの監査レコードが検索で返されるようにします。**Set-Mailbox** cmdlet に関連するすべての監査レコードを返すには、こうする必要があります。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p117">**Activities** - Leave this field blank so that the search returns audit records for all activities. This is necessary to return any audit records related to the **Set-Mailbox** cmdlet.</span></span>

<span data-ttu-id="88b8b-179">**開始日**と**終了日** - 調査の対象となる日付範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="88b8b-179">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="88b8b-p118">**ユーザー** - 特定の 1 ユーザーの電子メール転送の問題を調査している場合を除き、このフィールドは空白のままにします。これにより、いずれかのユーザーの電子メール転送が設定されたかどうか識別しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p118">**Users** - Unless you're investigating a email forwarding issue for a specific user, leave this field blank. This will help you identify if email forwarding was set up for any user.</span></span>

<span data-ttu-id="88b8b-182">**ファイル、フォルダー、またはサイト** - このフィールドは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="88b8b-182">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="88b8b-p119">検索の実行後、検索結果ページの [**結果をフィルター**] をクリックします。[**アクティビティ**] 列見出しの下のボックスで「**Set-Mailbox**」と入力すると、**Set-Mailbox** cmdlet に関連する監査レコードだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p119">After you run the search, click **Filter results** on the search results page. In the box under **Activity** column header, type **Set-Mailbox** so that only audit records related to the **Set-Mailbox** cmdlet are displayed.</span></span>

![監査ログの検索結果をフィルター処理する](media/emailforwarding1.png)

<span data-ttu-id="88b8b-p120">この時点で、それぞれの監査レコードの詳細を調べて、そのアクティビティが電子メール転送に関連しているかどうか判別する必要があります。監査レコードをクリックして [**詳細**] ポップアップ ページを表示させ、[**詳細情報**] をクリックしてください。以下のスクリーン ショットと説明は、メールボックスで電子メール転送が設定されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p120">At this point, you have to look at the details of each audit record to determine if the activity is related to email forwarding. Click the audit record to display the **Details** flyout page, and then click **More information**. The following screenshot and descriptions highlights the information that indicates email forwarding was set on the mailbox.</span></span>

![監査レコードから得られる詳細情報](media/emailforwarding2.png)

<span data-ttu-id="88b8b-p121">a. [**ObjectId**] フィールドに、電子メール転送が設定されたメールボックスのエイリアスが表示されます。また、このメールボックスは検索結果ページの [**項目**] 列にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p121">a. In the **ObjectId** field, the alias of the mailbox that email forwarding was set on is displayed. This mailbox is also displayed on the **Item** column in the search results page.</span></span>

<span data-ttu-id="88b8b-p122">b. [**パラメーター**] フィールドの値 *ForwardingSmtpAddress* は、メールボックスでメール転送が設定されていることを示します。この例では、alpinehouse.onmicrosoft.com 組織の外部にある mike@contoso.com というメール アドレスに電子メールが転送されています。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p122">b. In the **Parameters** field, The value *ForwardingSmtpAddress* indicates that email forward has been set on the mailbox. In this example, mail is being forwarded to the email address mike@contoso.com, which is outside of the alpinehouse.onmicrosoft.com organization.</span></span>

<span data-ttu-id="88b8b-p123">c. *DeliverToMailboxAndForward* パラメーターの値 *True* は、メッセージのコピーが sarad@alpinehouse.onmicrosoft.com に送信され、*しかも* *ForwardingSmtpAddress* パラメーターの電子メール アドレス (この例では mike@contoso.com) に転送されたことを示しています。*DeliverToMailboxAndForward* パラメーターの値が *False* に設定されている場合は、*ForwardingSmtpAddress* パラメーターのアドレスだけに電子メールが転送されます。つまり [**ObjectId**] フィールドで指定されたメールボックスには送信されません。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p123">c. The *True* value for the *DeliverToMailboxAndForward* parameter indicates that a copy of message delivered to sarad@alpinehouse.onmicrosoft.com *and* is forwarded to the email address specified by the *ForwardingSmtpAddress* parameter, which in this example is mike@contoso.com. If the value for the *DeliverToMailboxAndForward* parameter is set to *False*, then email is only forwarded to the address specified by the *ForwardingSmtpAddress* parameter. It's not delivered to the mailbox specified in the **ObjectId** field.</span></span>

<span data-ttu-id="88b8b-p124">d. [**UserId**] フィールドは、[**ObjectId**] フィールドで指定されたメールボックスの電子メール転送を設定したユーザーを示します。また、このユーザーは検索結果ページの [**ユーザー**] 列にも表示されます。このケースの場合、メールボックス所有者が自分のメールボックスのメール転送を設定したようです。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p124">d. The **UserId** field indicates the user who set email forwarding on the mailbox specified in the **ObjectId** field field. This user is also displayed in the **User** column on the search results page. In this case, it seems that the owner of the mailbox set email forwarding on her mailbox.</span></span>

<span data-ttu-id="88b8b-204">メールボックスのメール転送を設定すべきでないと判断される場合は、Exchange Online PowerShell で次のコマンドを実行して、この設定を削除できます:</span><span class="sxs-lookup"><span data-stu-id="88b8b-204">If you determine that email forwarding shouldn't be set on the mailbox, you can remove it by running the following command in Exchange Online PowerShell:</span></span>

```
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

<span data-ttu-id="88b8b-205">電子メール転送に関連するパラメーターの詳細については、[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="88b8b-205">See the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) article for more information about the parameters related to email forwarding.</span></span>

## <a name="determining-if-a-user-deleted-email-items"></a><span data-ttu-id="88b8b-206">ユーザーがメール項目を削除したかどうかを判別する</span><span class="sxs-lookup"><span data-stu-id="88b8b-206">Determining if a user deleted email items</span></span>

<span data-ttu-id="88b8b-p125">削除された電子メール項目についての監査ログ レコードを Office 365 監査ログに保存するには、その前に、組織の各ユーザー メールボックスに監査が有効になっている必要があります。さらに、メールボックス アクション SoftDelete と HardDelete の監査が有効になっている必要があります。その方法については、「[Office 365 でメールボックスの監査を有効にする](enable-mailbox-auditing.md)」を参照してください。ユーザーのメールボックスの監査がすでに有効になっている場合は、次の手順に従って、削除されたメール項目に関連するイベントを監査ログの中で探します。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p125">Before audit log records about deleted email items are saved to the Office 365 audit log, mailbox auditing has to be enabled for each user mailbox in your organization. Additionally, the SoftDelete and HardDelete mailbox actions have to be enabled for auditing. For instructions, see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). If mailbox auditing is already enabled for users, use the following steps to search the audit log for events related to deleted email items.</span></span>

<span data-ttu-id="88b8b-211">このシナリオで監査ログの検索クエリを構成する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="88b8b-211">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="88b8b-212">**アクティビティ** - [**Exchange メールボックスのアクティビティ**] の下で、次のアクティビティの 1 つまたは両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="88b8b-212">**Activities** - Under **Exchange mailbox activities**, select one or both of the following activities:</span></span>

- <span data-ttu-id="88b8b-p126">**削除済みアイテム フォルダーから削除されたメッセージ** - このアクティビティは、メールボックス監査アクション **SoftDelete** に対応しています。また、ユーザーがメール項目を選び **Shift+Delete** を押して完全に削除した場合にも、このアクティビティがログに記録されます。項目が完全に削除された後、削除済み項目の保存期間が切れるまでは、ユーザーがそれを回復できます。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p126">**Deleted messages from Deleted Items folder** -  This activity corresponds to the **SoftDelete** mailbox auditing action. This activity is also logged when a user permanently deletes an item by selecting it and pressing **Shift+Delete**. After an item is permanently deleted, the user can recover it until the deleted item retention period expires.</span></span>

- <span data-ttu-id="88b8b-p127">**メールボックスからパージされたメッセージ** - このアクティビティは、メールボックス監査アクション **HardDelete** に対応しています。これは、「回復可能なアイテム」フォルダーからユーザーが項目をパージしたときにログに記録されます。削除済み項目の保持期間が切れるまで (またはユーザーのメールボックスが保留中の場合はそれより長い期間にわたり)、管理者は Office 365 セキュリティ/コンプライアンス センターのコンテンツ検索ツールを使用して、バージ済み項目を検索し、回復することができます。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p127">**Purged messages from mailbox** - This activity corresponds to the **HardDelete** mailbox auditing action. This is logged when a user purges an item from the Recoverable Items folder. Admins can use the Content Search tool in the Office 365 Security & Compliance Center to search for and recover purged items until the deleted item retention period expires or longer if the user's mailbox is on hold.</span></span>

<span data-ttu-id="88b8b-219">**開始日**と**終了日** - 調査の対象となる日付範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="88b8b-219">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="88b8b-p128">**ユーザー** - このフィールドでユーザーを選択した場合、監査ログ検索ツールは、そのユーザーによって削除 (SoftDeleted または HardDeleted) されたメール項目に関する監査レコードを返します。場合によっては、電子メールを削除したユーザーがメールボックス所有者でないこともあります。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p128">**Users** - If you select a user in this field, the audit log search tool will return audit records for email items that were deleted (SoftDeleted or HardDeleted) by the user you specify. In some cases, the user who deletes an email might not be the mailbox owner.</span></span>

<span data-ttu-id="88b8b-222">**ファイル、フォルダー、またはサイト** - このフィールドは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="88b8b-222">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="88b8b-p129">検索の実行後、検索結果をフィルター処理して、ソフト削除された項目またはハード削除された項目の監査レコードを表示できます。監査レコードをクリックすると [**詳細**] ポップアップ ページが表示され、さらに [**詳細情報**] をクリックできます。件名行、項目が削除されたときの場所など、削除済み項目に関する追加情報が [**AffectedItems**] フィールドに表示されます。次のスクリーン ショットは、ソフト削除された項目とハード削除された項目の [**AffectedItems**] フィールドの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p129">After you run the search, you can filter the search results to display the audit records for soft-deleted items or for hard-deleted items. Click the audit record to display the **Details** flyout page, and then click **More information**. Additional information about the deleted item, such as the subject line and the location of the item when it was deleted, is displayed in the **AffectedItems** field. The following screenshots show an example of the **AffectedItems** field from a soft-deleted item and a hard-deleted item.</span></span>

<span data-ttu-id="88b8b-227">**ソフト削除された項目の AffectedItems フィールドの例**</span><span class="sxs-lookup"><span data-stu-id="88b8b-227">**Example of AffectedItems field for soft-deleted item**</span></span>

![ソフト削除された項目の監査レコード](media/softdeleteditem.png)

<span data-ttu-id="88b8b-229">**ハード削除された項目の AffectedItems フィールドの例**</span><span class="sxs-lookup"><span data-stu-id="88b8b-229">**Example of AffectedItems field for hard-deleted item**</span></span>

![ハード削除されたメール項目の監査レコード](media/harddeleteditem.png)

### <a name="recovering-deleted-email-items"></a><span data-ttu-id="88b8b-231">削除済み電子メール項目の回復</span><span class="sxs-lookup"><span data-stu-id="88b8b-231">Recovering deleted email items</span></span>

<span data-ttu-id="88b8b-p130">削除済みアイテムの保存期間の期限が切れていない場合、ユーザーは削除済みアイテムを回復できます。Exchange Online では、既定の削除済みアイテムの保存期間は14日ですが、管理者はこの設定を最大30日間に増やすことができます。削除済みアイテムを復元する手順については、「 [web 上の Outlook の削除済みアイテムまたは電子メールを復元する」](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p130">Users can recover soft-deleted items if the deleted items retention period has not expired. In Exchange Online, the default deleted items retention period is 14 days, but admins can increase this setting to a maximum of 30 days. Point users to the [Recover deleted items or email in Outlook on the web](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) article for instructions on recovering deleted items.</span></span>

<span data-ttu-id="88b8b-p131">すでに述べたように、削除済み項目の保持期間がまだ切れていない場合、またはメールボックスが保留中の場合に、管理者はハード削除された項目を回復できる可能性があります。後者の場合、保留期間が切れるまで項目が保持されます。コンテンツ検索を実行すると、「回復可能なアイテム」フォルダー内のソフト削除された項目とハード削除された項目が検索クエリに一致する場合、それらが検索結果に返されます。コンテンツ検索の実行の詳細については、「[Office 365 でのコンテンツ検索](content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p131">As previously explained, admins might be able to recover hard-deleted items if the deleted item retention period has not expired or if the mailbox is on hold, in which case items are retained until the hold duration expires. When you run a content search, soft-deleted and hard-deleted items in the Recoverable Items folder are returned in the search results if they match the search query. For more information about running content searches, see [Content Search in Office 365](content-search.md).</span></span>

> [!TIP]
> <span data-ttu-id="88b8b-238">削除済み電子メール項目を検索するには、監査レコードの [**AffectedItems**] フィールドに表示されている件名行の全体または一部を検索します。</span><span class="sxs-lookup"><span data-stu-id="88b8b-238">To search for deleted email items, search for all or part of the subject line that's displayed in the **AffectedItems** field in the audit record.</span></span>

## <a name="determining-if-a-user-created-an-inbox-rule"></a><span data-ttu-id="88b8b-239">ユーザーが受信トレイ ルールを作成したかどうかを判別する</span><span class="sxs-lookup"><span data-stu-id="88b8b-239">Determining if a user created an inbox rule</span></span>

<span data-ttu-id="88b8b-p132">ユーザーが自分の Exchange Online メールボックスの受信トレイ ルールを作成すると、それに対応する監査レコードが監査ログに保存されます。受信トレイ ルールの詳細については、次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="88b8b-p132">When users create an inbox rule for their Exchange Online mailbox, a corresponding audit record is saved to the audit log. For more information about inbox rules, see:</span></span>

- [<span data-ttu-id="88b8b-242">Web 上の Outlook で受信トレイ ルールを使用する</span><span class="sxs-lookup"><span data-stu-id="88b8b-242">Use inbox rules in Outlook on the web</span></span>](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [<span data-ttu-id="88b8b-243">Outlook でルールを使用してメール メッセージを管理する</span><span class="sxs-lookup"><span data-stu-id="88b8b-243">Manage email messages in Outlook by using rules</span></span>](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

<span data-ttu-id="88b8b-244">このシナリオで監査ログの検索クエリを構成する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="88b8b-244">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="88b8b-245">**アクティビティ** - [**Exchange メールボックスのアクティビティ**] の下で、[**New-InboxRule 受信トレイ ルールの作成/変更/有効化/無効化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="88b8b-245">**Activities** - Under **Exchange mailbox activities**, select **New-InboxRule Create/modify/enable/disable inbox rule**.</span></span>

<span data-ttu-id="88b8b-246">**開始日**と**終了日** - 調査の対象となる日付範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="88b8b-246">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="88b8b-p133">**ユーザー** - 特定の 1 ユーザーを調査している場合を除き、このフィールドは空白のままにします。これにより、いずれかのユーザーによって設定された新しい受信トレイ ルールを識別しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p133">**Users** - Unless you're investigating a specific user, leave this field blank. This will help you identify new inbox rules set up by any user.</span></span>

<span data-ttu-id="88b8b-249">**ファイル、フォルダー、またはサイト** - このフィールドは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="88b8b-249">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="88b8b-p134">検索の実行後、このアクティビティに関するすべての監査レコードが検索結果に表示されます。1 つの監査レコードをクリックすると [**詳細**] ポップアップ ページが表示され、さらに [**詳細情報**] をクリックできます。受信トレイ ルール設定に関する情報が [**パラメーター**] フィールドに表示されます。次のスクリーン ショットと説明は、受信トレイ ルールに関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p134">After you run the search, any audit records for this activity are displayed in the search results. Click an audit record to display the **Details** flyout page, and then click **More information**. Information about the inbox rule settings are displayed in the **Parameters** field. The following screenshot and descriptions highlights the information about inbox rules.</span></span>

![新しい受信トレイ ルールに関する監査レコード](media/NewInboxRuleRecord.png)

<span data-ttu-id="88b8b-p135">a. [**ObjectId**] フィールドに受信トレイ ルールの完全な名前が表示されます。この名前には、ユーザーのメールボックスのエイリアス (たとえば SaraD) と受信トレイ ルールの名前 (たとえば「管理者からのメッセージを移動」) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p135">a. In the **ObjectId** field, the full name of the inbox rule is displayed. This name includes the alias of the user's mailbox (for example, SaraD) and the name of the inbox rule (for example, "Move messages from admin").</span></span>

<span data-ttu-id="88b8b-p136">b. [**パラメーター**] フィールドには受信トレイ ルールの条件が表示されます。この例では、[*送信者*] パラメーターによって条件が指定されます。[*送信者*] パラメーターに定義された値は、admin@alpinehouse.onmicrosoft.com から送られた電子メールを受信トレイ ルールで処理することを示しています。受信トレイ ルールの条件の定義に使用できるパラメーターの完全なリストについては、「[New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p136">b. In the **Parameters** field, the condition of the inbox rule is displayed. In this example, the condition is specified by the *From* parameter. The value defined for the *From* parameter indicates that the inbox rule acts on email sent by admin@alpinehouse.onmicrosoft.com. For a complete list of the parameters that can be used to define conditions of inbox rules, see the [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) article.</span></span>

<span data-ttu-id="88b8b-p137">c. [*MoveToFolder*] パラメーターは、受信トレイ ルールのアクションを指定します。この例では、admin@alpinehouse.onmicrosoft.com から受け取ったメッセージを *AdminSearch* というフォルダーに移動します。さらに、受信トレイ ルールのアクションの定義に使用できるパラメーターの完全なリストについては「[New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p137">c. The *MoveToFolder* parameter specifies the action for the inbox rule; in this example, messages received from admin@alpinehouse.onmicrosoft.com are moved to the folder named *AdminSearch*. Also see the [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) article for a complete list of parameters that can used to define the action of an inbox rule.</span></span>

<span data-ttu-id="88b8b-p138">d. [**UserId**] フィールドは、[**ObjectId**] フィールドで指定された受信トレイ ルールを作成したユーザーを示します。また、このユーザーは検索結果ページの [**ユーザー**] 列にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="88b8b-p138">d. The **UserId** field indicate the user who created the inbox rule specified in the **ObjectId** field. This user is also displayed in the **User** column on the search results page.</span></span>