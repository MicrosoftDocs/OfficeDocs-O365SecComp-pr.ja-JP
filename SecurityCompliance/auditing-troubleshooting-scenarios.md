---
title: 一般的なシナリオのトラブルシューティングを行う Office 365 の監査ログを検索します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
description: Office 365 の監査ログの検索ツールを使用すると、侵害されたアカウントの調査、またはメールボックスの電子メールの転送を設定するなどの一般的な問題のトラブルシューティングに役立ちます。
ms.openlocfilehash: 930e311712e49214ca2a51e256c29e5f959deab8
ms.sourcegitcommit: c34f1a0d560117153fc9a7b8da8994bc6fc53791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2018
ms.locfileid: "27123900"
---
# <a name="search-the-office-365-audit-log-to-troubleshoot-common-scenarios"></a><span data-ttu-id="fd393-103">一般的なシナリオのトラブルシューティングを行う Office 365 の監査ログを検索します。</span><span class="sxs-lookup"><span data-stu-id="fd393-103">Search the Office 365 audit log to troubleshoot common scenarios</span></span>

<span data-ttu-id="fd393-p101">この資料では、サポートの一般的なシナリオのトラブルシューティングに役立つ Office 365 の監査ログの検索ツールを使用する方法について説明します。これは、監査ログを使用して含まれています。</span><span class="sxs-lookup"><span data-stu-id="fd393-p101">This article describes how to use the Office 365 audit log search tool to help you troubleshoot common support scenarios. This includes using the audit log to:</span></span>

- <span data-ttu-id="fd393-106">侵害されたアカウントのアクセスに使用するコンピューターの IP アドレスを検索します。</span><span class="sxs-lookup"><span data-stu-id="fd393-106">Find the IP address of the computer used to access a compromised account</span></span>
- <span data-ttu-id="fd393-107">メールボックスの電子メールの転送を設定するを決定します。</span><span class="sxs-lookup"><span data-stu-id="fd393-107">Determine who set up email forwarding for a mailbox</span></span>
- <span data-ttu-id="fd393-108">ユーザーが自分のメールボックス内の電子メール アイテムを削除するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fd393-108">Determine if a user deleted email items in their mailbox</span></span>
- <span data-ttu-id="fd393-109">ユーザーが受信トレイのルールを作成するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fd393-109">Determine if a user created an inbox rule</span></span>

## <a name="using-the-office-365-audit-log-search-tool"></a><span data-ttu-id="fd393-110">Office 365 の監査ログの検索ツールを使用してください。</span><span class="sxs-lookup"><span data-stu-id="fd393-110">Using the Office 365 audit log search tool</span></span>

<span data-ttu-id="fd393-p102">この資料に記載されているトラブルシューティングのシナリオは、Office 365 のセキュリティとコンプライアンス ・ センターの監査ログの検索ツールを使用するのに基づいています。このセクションでは、監査ログを検索するために必要なアクセス許可の一覧し、アクセスし、監査ログの検索を実行する手順について説明します。各シナリオのセクションでは、検索条件に一致する監査レコードの詳細な情報で検索して、監査ログの検索クエリを構成する方法に関する具体的なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fd393-p102">Each of the troubleshooting scenarios described in this article are based on using the audit log search tool in the Office 365 Security & Compliance Center. This section lists the permissions required to search the audit log and describes the steps to access and run audit log searches. Each scenario section provides specific guidance about how to configure an audit log search query and what to look for in the detailed information in the audit records that match the search criteria.</span></span>

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a><span data-ttu-id="fd393-114">監査ログの検索ツールを使用する必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fd393-114">Permissions required to use the audit log search tool</span></span>

<span data-ttu-id="fd393-p103">監査ログの参照、または監査ログの役割を割り当てる Exchange オンライン Office 365 の監査ログを検索する必要があります。既定では、これらの役割は Exchange 管理センターで [**アクセス許可**] ページでのコンプライアンスの管理と組織管理の役割グループに割り当てられます。詳細については、[管理役割グループの Exchange オンライン](https://go.microsoft.com/fwlink/p/?LinkID=730688)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd393-p103">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log. By default, these roles are assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. For more information, see [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).</span></span>

### <a name="running-audit-log-searches"></a><span data-ttu-id="fd393-118">実行中の監査ログの検索</span><span class="sxs-lookup"><span data-stu-id="fd393-118">Running audit log searches</span></span>

<span data-ttu-id="fd393-p104">このセクションを作成し、監査ログの検索を実行するための基本について説明します。この資料でトラブルシューティングのシナリオごとに、開始点として、次の手順を使用します。詳細な手順については、[監査ログが Office 365 のセキュリティとコンプライアンス センターで検索](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd393-p104">This section describes the basics for creating and running audit log searches. Use these instructions as a starting point for each troubleshooting scenario in this article. For more detailed step-by-step instructions, see [Search the audit log in the Office 365 Security & Compliance Center ](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).</span></span>

1. <span data-ttu-id="fd393-122">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="fd393-122">Go to [https://protection.office.com](https://protection.office.com).</span></span>
  
2. <span data-ttu-id="fd393-123">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="fd393-123">Sign in to Office 365 using your work or school account.</span></span>

3. <span data-ttu-id="fd393-124">セキュリティとコンプライアンスの中心の左側のペインで [**検索と調査** > **監査ログの検索**します。</span><span class="sxs-lookup"><span data-stu-id="fd393-124">In the left pane of the Security & Compliance Center, click **Search & investigation** > **Audit log search**.</span></span>
    
    <span data-ttu-id="fd393-125">**監査ログの検索**ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd393-125">The **Audit log search** page is displayed.</span></span> 
    
    ![条件を構成し、検索を実行する検索] をクリックしてください](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. <span data-ttu-id="fd393-p105">次の検索条件を構成することができます。各トラブルシューティングのシナリオでは、この資料でこれらのフィールドを構成するための特定のガイダンスをお勧めことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fd393-p105">You can configure the following search criteria. Note that each troubleshooting scenario in this article will recommend specific guidance for configuring these fields.</span></span>
    
    <span data-ttu-id="fd393-p106">a.**活動**- を検索することができる活動を表示するドロップダウン リストをクリックします。検索を実行すると、選択したアクティビティの監査レコードのみが表示されます。**すべての活動の結果を表示する**を選択すると、他の検索条件を満たすすべての活動の結果が表示されます。このフィールドが空白では、トラブルシューティングのシナリオをいくつか必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd393-p106">a. **Activities** - Click the drop-down list to display the activities that you can search for. After you run the search, only the audit records for the selected activities are displayed. Selecting **Show results for all activities** will display results for all activities that meet the other search criteria. You'll also have to leave this field blank in some of the troubleshooting scenarios.</span></span>
    
    <span data-ttu-id="fd393-p107">b. の**開始日**と**終了日**がその期間内に発生したイベントを表示する日付と時刻の範囲を選択します。過去 7 日間は、既定で選択されます。日付と時刻が世界協定時刻 (UTC) 形式で表示されます。最大日付範囲を指定することには、90 日間です。</span><span class="sxs-lookup"><span data-stu-id="fd393-p107">b. **Start date** and **End date** - Select a date and time range to display the events that occurred within that period. The last seven days are selected by default. The date and time are presented in Coordinated Universal Time (UTC) format. The maximum date range that you can specify is 90 days.</span></span>

    <span data-ttu-id="fd393-p108">結果、c.**ユーザー**の検索を表示するのには、このボックスで 1 つまたは複数のユーザーを選択します] をクリックします。このボックスで選択したユーザーによって実行される、選択したアクティビティの監査レコードは、結果の一覧に表示されます。このボックスは、組織内のユーザー (およびサービス アカウント) がすべてのエントリを返すには、空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="fd393-p108">c. **Users** - Click in this box and then select one or more users to display search results for. Audit records for the selected activity performed by the users you select in this box are displayed in the list of results. Leave this box blank to return entries for all users (and service accounts) in your organization.</span></span>
    
    <span data-ttu-id="fd393-p109">d.**ファイル、フォルダー、またはサイト**では、指定したキーワードが含まれているフォルダーのファイルに関連するアクティビティを検索するファイルまたはフォルダーの名前の一部または全部を入力します。ファイルまたはフォルダーの URL を指定することもできます。URL を使用する場合は、特殊文字や空白 URL の完全なパスの種類であることを確認、または URL の一部を入力するだけの場合は含まれます。このボックスは、組織内のすべてのファイルとフォルダーのエントリを返すには、空白のままにします。このフィールドは空白のままにすべてのトラブルシューティングのシナリオでこの資料に記載されている注意してください。</span><span class="sxs-lookup"><span data-stu-id="fd393-p109">d. **File, folder, or site** - Type some or all of a file or folder name to search for activity related to the file of folder that contains the specified keyword. You can also specify a URL of a file or folder. If you use a URL, be sure the type the full URL path or if you just type a portion of the URL, don't include any special characters or spaces. Leave this box blank to return entries for all files and folders in your organization. Note that this field is left blank in all the troubleshooting scenarios in this article.</span></span>
    
5. <span data-ttu-id="fd393-149">検索条件を使用して検索を実行する**検索**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd393-149">Click **Search** to run the search using your search criteria.</span></span> 
    
    <span data-ttu-id="fd393-p110">検索結果が読み込まれ、しばらくした後、[**結果**ページに表示されます、**監査ログの検索**します。次のセクションには、それぞれにより、特定のトラブルシューティング シナリオを検索することについてのガイダンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="fd393-p110">The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page. Each to the following sections will provide guidance about things to look for the specific troubleshooting scenario.</span></span>

    <span data-ttu-id="fd393-152">表示、フィルター処理、または監査ログの検索結果のエクスポートの詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd393-152">For more information about viewing, filtering, or exporting audit log search results, see:</span></span>

    - [<span data-ttu-id="fd393-153">検索結果の表示</span><span class="sxs-lookup"><span data-stu-id="fd393-153">View search results</span></span>](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [<span data-ttu-id="fd393-154">検索結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="fd393-154">Filter search results</span></span>](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [<span data-ttu-id="fd393-155">検索結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="fd393-155">Export search results</span></span>](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="finding-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a><span data-ttu-id="fd393-156">侵害されたアカウントのアクセスに使用するコンピューターの IP アドレスを検索します。</span><span class="sxs-lookup"><span data-stu-id="fd393-156">Finding the IP address of the computer used to access a compromised account</span></span>

<span data-ttu-id="fd393-p111">ほとんどの監査レコードのすべてのユーザーによって実行されるアクティビティに対応する IP アドレスが含まれます。使用するクライアントに関する情報が監査記録に含まれます。</span><span class="sxs-lookup"><span data-stu-id="fd393-p111">The IP address corresponding to an activity performed by any user is included in most audit records. Information about the client used is also included in the audit record.</span></span>

<span data-ttu-id="fd393-159">このシナリオでは、監査ログの検索クエリを構成する方法を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="fd393-159">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="fd393-p112">**活動**- 該当する場合、大文字と小文字を検索する特定のアクティビティを選択します。トラブルシューティングのセキュリティを侵害されたアカウントは、 **Exchange メールボックス アクティビティ**で**メールボックスにサインインしたユーザー**のアクティビティを選択することを検討してください。メールボックスへのサインイン時に使用された IP アドレスの表示、監査レコードが返されます。それ以外の場合、このフィールドをすべてのアクティビティの監査レコードを返すには、空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="fd393-p112">**Activities** - If relevant to your case, select a specific activity to search for. For troubleshooting compromised accounts, consider selecting the **User signed in to mailbox** activity under **Exchange mailbox activities**. This will return auditing records showing the IP address that was use when signing in to the mailbox. Otherwise, leave this field blank to return audit records for all activities.</span></span> 

> [!TIP]
> <span data-ttu-id="fd393-p113">このフィールドを空白のままを返します**UserLoggedIn**活動では、Azure Active Directory 活動を他のユーザーが署名されている Office 365 のユーザー アカウントを示します。**UserLoggedIn**監査レコードを表示するのにには、検索結果のフィルタ リングを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd393-p113">Leaving this field blank will  return **UserLoggedIn** activities, which is an Azure Active Directory activity that indicates that someone has signed in to an Office 365 user account. Use filtering in the search results to display the **UserLoggedIn** audit records.</span></span>

<span data-ttu-id="fd393-166">**開始日**と**終了日**の調査に適用される日付の範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd393-166">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="fd393-p114">**ユーザー**が侵害されたアカウントを調査している場合、は、アカウントが被害を受けたユーザーを選択します。そのユーザー アカウントで実行されるアクティビティの監査レコードが返されます。</span><span class="sxs-lookup"><span data-stu-id="fd393-p114">**Users** - If you're investigating a compromised account, select the user whose account was compromised. This will return audit records for activities performed by that user account.</span></span>

<span data-ttu-id="fd393-169">**ファイル、フォルダー、またはサイト**- このフィールドを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="fd393-169">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="fd393-p115">検索を実行した後、アクティビティごとに IP アドレスは検索結果に [ **IP アドレス**] 列に表示されます。フライアウトのページでより詳細な情報を表示するのには検索結果内のレコードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd393-p115">After you run the search, the IP address for each activity is displayed in the **IP address** column in the search results. Click the record in the search results to view more detailed information on the flyout page.</span></span>

## <a name="determining-who-set-up-email-forwarding-for-a-mailbox"></a><span data-ttu-id="fd393-172">メールボックスの電子メールの転送を設定するを決定します。</span><span class="sxs-lookup"><span data-stu-id="fd393-172">Determining who set up email forwarding for a mailbox</span></span>

<span data-ttu-id="fd393-p116">メールボックスの電子メールの転送を構成する場合は、メールボックスに送信される電子メール メッセージが別のメールボックスに転送されます。組織の内外のユーザーにメッセージを転送することができます。メールボックスの電子メールの転送が設定されている場合に使用される基になる Exchange Online のコマンドレットは、**セット-メールボックス**です。</span><span class="sxs-lookup"><span data-stu-id="fd393-p116">When email forwarding is configured for a mailbox, email messages that are sent to the mailbox are forwarded to another mailbox. Messages can be forwarded to users inside or outside of your organization. When email forwarding is set up on a mailbox, the underlying Exchange Online cmdlet that's used is **Set-Mailbox**.</span></span>

<span data-ttu-id="fd393-176">このシナリオでは、監査ログの検索クエリを構成する方法を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="fd393-176">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="fd393-p117">**活動**- このフィールドを検索にすべてのアクティビティの監査レコードが返されるように、空白のままにします。これは、いずれかを取得するために必要な**セット-メールボックス**コマンドレットに関連するレコードを監査します。</span><span class="sxs-lookup"><span data-stu-id="fd393-p117">**Activities** - Leave this field blank so that the search returns audit records for all activities. This is necessary to return any audit records related to the **Set-Mailbox** cmdlet.</span></span>

<span data-ttu-id="fd393-179">**開始日**と**終了日**の調査に適用される日付の範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd393-179">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="fd393-p118">**ユーザー**が特定のユーザーの問題を転送する電子メールを調査している、しない限り、空白のままにこのフィールドです。これからは、メールの転送設定がすべてのユーザーかどうか判断できます。</span><span class="sxs-lookup"><span data-stu-id="fd393-p118">**Users** - Unless you're investigating a email forwarding issue for a specific user, leave this field blank. This will help you identify if email forwarding was set up for any user.</span></span>

<span data-ttu-id="fd393-182">**ファイル、フォルダー、またはサイト**- このフィールドを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="fd393-182">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="fd393-p119">検索を実行した後、検索結果ページの [**結果のフィルター処理**] をクリックします。**アクティビティ**列ヘッダーの下にあるボックスでは、**セット-メールボックス**コマンドレットに関連する監査レコードだけが表示されるよう**セットのメールボックス**を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd393-p119">After you run the search, click **Filter results** on the search results page. In the box under **Activity** column header, type **Set-Mailbox** so that only audit records related to the **Set-Mailbox** cmdlet are displayed.</span></span>

![監査ログの検索結果をフィルタ リング](media/emailforwarding1.png)

<span data-ttu-id="fd393-p120">この時点では、アクティビティが電子メールの転送に関連しているかを判断するには、各監査レコードの詳細を確認する必要があります。フライアウトの**詳細**] ページを表示する監査記録] をクリックし、[**詳細**] をクリックします。次のスクリーン ショットと説明ハイライト メールの転送を示す情報は、メールボックスに設定されました。</span><span class="sxs-lookup"><span data-stu-id="fd393-p120">At this point, you have to look at the details of each audit record to determine if the activity is related to email forwarding. Click the audit record to display the **Details** flyout page, and then click **More information**. The following screenshot and descriptions highlights the information that indicates email forwarding was set on the mailbox.</span></span>

![監査レコードの詳細情報](media/emailforwarding2.png)

<span data-ttu-id="fd393-p121">a. [**オブジェクト Id** ] フィールドで、電子メールの転送先のメールボックスのエイリアスが設定されたが表示されます。このメールボックスは、[検索結果] ページで [**項目**] 列も表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd393-p121">a. In the **ObjectId** field, the alias of the mailbox that email forwarding was set on is displayed. This mailbox is also displayed on the **Item** column in the search results page.</span></span>

<span data-ttu-id="fd393-p122">b.**パラメーター** ] フィールドでは、 *ForwardingSmtpAddress*の値は、メールボックスに電子メールを転送が設定されていることを示します。この例では、alpinehouse.onmicrosoft.com 組織の外部にある電子メール アドレスの mike@contoso.com にメールが転送されます。</span><span class="sxs-lookup"><span data-stu-id="fd393-p122">b. In the **Parameters** field, The value *ForwardingSmtpAddress* indicates that email forward has been set on the mailbox. In this example, mail is being forwarded to the email address mike@contoso.com, which is outside of the alpinehouse.onmicrosoft.com organization.</span></span>

<span data-ttu-id="fd393-p123">c. *DeliverToMailboxAndForward*パラメーターの値が*True*では、sarad@alpinehouse.onmicrosoft.com*と*に配信されるメッセージのコピーが*ForwardingSmtpAddress で指定されたメール ・ アドレスに転送されることを示します*パラメーターにこの例では mike@contoso.com です。*DeliverToMailboxAndForward*パラメーターの値を*False*に設定されて、 *ForwardingSmtpAddress*パラメーターで指定されたアドレスに電子メールが転送のみです。**オブジェクト Id** ] フィールドで指定されたメールボックスに配信されません。</span><span class="sxs-lookup"><span data-stu-id="fd393-p123">c. The *True* value for the *DeliverToMailboxAndForward* parameter indicates that a copy of message delivered to sarad@alpinehouse.onmicrosoft.com *and* is forwarded to the email address specified by the *ForwardingSmtpAddress* parameter, which in this example is mike@contoso.com. If the value for the *DeliverToMailboxAndForward* parameter is set to *False*, then email is only forwarded to the address specified by the *ForwardingSmtpAddress* parameter. It's not delivered to the mailbox specified in the **ObjectId** field.</span></span>

<span data-ttu-id="fd393-p124">d.**ユーザー Id**フィールドは、**オブジェクト Id**のフィールドで指定されたメールボックスにメールの転送を設定したユーザーを示します。このユーザーは、検索結果ページの [**ユーザー** ] 列も表示されます。この例では、メールボックスの所有者が自分のメールボックスにメールの転送を設定することと思われます。</span><span class="sxs-lookup"><span data-stu-id="fd393-p124">d. The **UserId** field indicates the user who set email forwarding on the mailbox specified in the **ObjectId** field field. This user is also displayed in the **User** column on the search results page. In this case, it seems that the owner of the mailbox set email forwarding on her mailbox.</span></span>

<span data-ttu-id="fd393-204">メールボックスにメールの転送を設定するべきではないと判断した場合は、Exchange オンライン PowerShell で次のコマンドを実行することによって削除できます。</span><span class="sxs-lookup"><span data-stu-id="fd393-204">If you determine that email forwarding shouldn't be set on the mailbox, you can remove it by running the following command in Exchange Online PowerShell:</span></span>

```
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

<span data-ttu-id="fd393-205">電子メールの転送に関連するパラメーターの詳細については[複数のメールボックスに設定](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd393-205">See the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) article for more information about the parameters related to email forwarding.</span></span>

## <a name="determining-if-a-user-deleted-email-items"></a><span data-ttu-id="fd393-206">ユーザーが電子メール アイテムを削除するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fd393-206">Determining if a user deleted email items</span></span>

<span data-ttu-id="fd393-p125">に関する監査ログ レコードが削除される前に、電子メール アイテムは、Office 365 の監査ログに保存されます、組織の各ユーザーのメールボックスを有効にするにはメールボックスの監査します。さらに、SoftDelete と HardDelete のメールボックスの操作は監査を有効にする必要があります。手順については、[メールボックスを Office 365 で監査を有効にする](enable-mailbox-auditing.md)を参照してください。ユーザーのメールボックスの監査が有効になって場合は、削除したメール アイテムに関連するイベントの監査ログを検索するのには次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd393-p125">Before audit log records about deleted email items are saved to the Office 365 audit log, mailbox auditing has to be enabled for each user mailbox in your organization. Additionally, the SoftDelete and HardDelete mailbox actions have to be enabled for auditing. For instructions, see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). If mailbox auditing is already enabled for users, use the following steps to search the audit log for events related to deleted email items.</span></span>

<span data-ttu-id="fd393-211">このシナリオでは、監査ログの検索クエリを構成する方法を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="fd393-211">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="fd393-212">**アクティビティ**の [ **Exchange メールボックスの動作**、1 つまたは両方の次のアクティビティの選択:</span><span class="sxs-lookup"><span data-stu-id="fd393-212">**Activities** - Under **Exchange mailbox activities**, select one or both of the following activities:</span></span>

- <span data-ttu-id="fd393-p126">**削除済みアイテム フォルダーから削除されたメッセージ**をこのアクティビティは、アクションの監査**SoftDelete**メールボックスに対応します。このアクティビティは、ユーザーを選択し、 **Shift キーを押しながら Del キー**を押すと、アイテムを完全に削除するときにも記録されます。アイテムが完全に削除されると、削除済みアイテムの保存期間が終了するまで、ユーザーがそれを回復できます。</span><span class="sxs-lookup"><span data-stu-id="fd393-p126">**Deleted messages from Deleted Items folder** -  This activity corresponds to the **SoftDelete** mailbox auditing action. This activity is also logged when a user permanently deletes an item by selecting it and pressing **Shift+Delete**. After an item is permanently deleted, the user can recover it until the deleted item retention period expires.</span></span>

- <span data-ttu-id="fd393-p127">**メールボックスからメッセージをパージ済み**- この活動は、アクションの監査**HardDelete**メールボックスに対応します。これは、ユーザーが回復可能なアイテム] フォルダーからアイテムを削除するときに記録されます。管理者は Office 365 のセキュリティとコンプライアンス センターでコンテンツの検索ツールを使用して、検索し、保留中のユーザーのメールボックスは、リカバリがパージされたアイテムの削除済みアイテムの保存期間が終了するまで、またはより長い場合。</span><span class="sxs-lookup"><span data-stu-id="fd393-p127">**Purged messages from mailbox** - This activity corresponds to the **HardDelete** mailbox auditing action. This is logged when a user purges an item from the Recoverable Items folder. Admins can use the Content Search tool in the Office 365 Security & Compliance Center to search for and recover purged items until the deleted item retention period expires or longer if the user's mailbox is on hold.</span></span>

<span data-ttu-id="fd393-219">**開始日**と**終了日**の調査に適用される日付の範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd393-219">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="fd393-p128">**ユーザー**がこのフィールドにユーザーを選択した場合、監査ログの検索ツールにメールされた項目を削除 (SoftDeleted または HardDeleted) で指定したユーザーの監査レコードが返されます。場合によっては、電子メールを削除したユーザーにメールボックスの所有者可能性がありますできません。</span><span class="sxs-lookup"><span data-stu-id="fd393-p128">**Users** - If you select a user in this field, the audit log search tool will return audit records for email items that were deleted (SoftDeleted or HardDeleted) by the user you specify. In some cases, the user who deletes an email might not be the mailbox owner.</span></span>

<span data-ttu-id="fd393-222">**ファイル、フォルダー、またはサイト**- このフィールドを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="fd393-222">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="fd393-p129">検索を実行した後は、ソフト削除済みアイテムまたはハード削除済みアイテムの監査レコードを表示する検索結果をフィルターできます。フライアウトの**詳細**] ページを表示する監査記録] をクリックし、[**詳細**] をクリックします。[件名] 行が削除されると、アイテムの場所など、削除された項目に関する追加情報は、**オブジェクト**のフィールドに表示されます。次のスクリーン ショットでは、ソフト削除されたアイテムは、ハード削除の項目から、**オブジェクト**のフィールドの例を示します。</span><span class="sxs-lookup"><span data-stu-id="fd393-p129">After you run the search, you can filter the search results to display the audit records for soft-deleted items or for hard-deleted items. Click the audit record to display the **Details** flyout page, and then click **More information**. Additional information about the deleted item, such as the subject line and the location of the item when it was deleted, is displayed in the **AffectedItems** field. The following screenshots show an example of the **AffectedItems** field from a soft-deleted item and a hard-deleted item.</span></span>

<span data-ttu-id="fd393-227">**ソフト削除されたアイテムのオブジェクトのフィールドの例**</span><span class="sxs-lookup"><span data-stu-id="fd393-227">**Example of AffectedItems field for soft-deleted item**</span></span>

![ソフト削除された項目の記録を監査します。](media/softdeleteditem.png)

<span data-ttu-id="fd393-229">**ハード削除済みアイテムのオブジェクトのフィールドの例**</span><span class="sxs-lookup"><span data-stu-id="fd393-229">**Example of AffectedItems field for hard-deleted item**</span></span>

![ハード削除のメール アイテムのレコードを監査します。](media/harddeleteditem.png)

### <a name="recovering-deleted-email-items"></a><span data-ttu-id="fd393-231">電子メール アイテムを削除を回復します。</span><span class="sxs-lookup"><span data-stu-id="fd393-231">Recovering deleted email items</span></span>

<span data-ttu-id="fd393-p130">ユーザーは、削除済みアイテムの保持期間の有効期限が切れていない場合、ソフト削除済みアイテムを回復できます。Exchange online では、既定の削除済みアイテムの保存期間は 14 日、ですが、管理者は、最大 30 日以内にこの設定を増やすことができます。ユーザーは、[削除済みアイテムまたは Outlook Web App の電子メールを回復する](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4)削除済みアイテムを回復する方法についての記事をポイントします。</span><span class="sxs-lookup"><span data-stu-id="fd393-p130">Users can recover soft-deleted items if the deleted items retention period has not expired. In Exchange Online, the default deleted items retention period is 14 days, but admins can increase this setting to a maximum of 30 days. Point users to the [Recover deleted items or email in Outlook Web App](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) article for instructions on recovering deleted items.</span></span>

<span data-ttu-id="fd393-p131">説明したようには、管理者は、削除済みアイテムの保持期間の有効期限が切れていない場合は、ハード削除済みアイテムを回復するか、メールボックスが存在する場合にできる場合があります、保留期間が経過するまでにアイテムを保持する場合。コンテンツの検索を実行すると、検索クエリに一致した場合回復可能なアイテム フォルダー内のアイテムを削除し、ハード削除が検索結果に返されます。コンテンツの検索を実行する方法の詳細については、 [Office 365 でのコンテンツの検索](content-search.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd393-p131">As previously explained, admins might be able to recover hard-deleted items if the deleted item retention period has not expired or if the mailbox is on hold, in which case items are retained until the hold duration expires. When you run a content search, soft-deleted and hard-deleted items in the Recoverable Items folder are returned in the search results if they match the search query. For more information about running content searches, see [Content Search in Office 365](content-search.md).</span></span>

> [!TIP]
> <span data-ttu-id="fd393-238">削除された電子メール アイテムを検索するには、監査レコードの**オブジェクト**のフィールドに表示される件名の行の一部またはすべてを検索します。</span><span class="sxs-lookup"><span data-stu-id="fd393-238">To search for deleted email items, search for all or part of the subject line that's displayed in the **AffectedItems** field in the audit record.</span></span>

## <a name="determining-if-a-user-created-an-inbox-rule"></a><span data-ttu-id="fd393-239">ユーザーが受信トレイのルールを作成するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fd393-239">Determining if a user created an inbox rule</span></span>

<span data-ttu-id="fd393-p132">ユーザーは、Exchange Online のメールボックスの受信トレイのルールを作成するとき、対応する監査レコードは、監査ログに保存されます。受信トレイ ルールの詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd393-p132">When users create an inbox rule for their Exchange Online mailbox, a corresponding audit record is saved to the audit log. For more information about inbox rules, see:</span></span>

- [<span data-ttu-id="fd393-242">Web 上の Outlook の受信トレイ ルールを使用してください。</span><span class="sxs-lookup"><span data-stu-id="fd393-242">Use inbox rules in Outlook on the web</span></span>](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [<span data-ttu-id="fd393-243">ルールを使用して Outlook で電子メール メッセージを管理します。</span><span class="sxs-lookup"><span data-stu-id="fd393-243">Manage email messages in Outlook by using rules</span></span>](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

<span data-ttu-id="fd393-244">このシナリオでは、監査ログの検索クエリを構成する方法を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="fd393-244">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="fd393-245">**活動**- **Exchange メールボックスの動作**を選択 [**新しい InboxRule を作成/変更/有効にする/受信トレイ ルールを無効にする**。</span><span class="sxs-lookup"><span data-stu-id="fd393-245">**Activities** - Under **Exchange mailbox activities**, select **New-InboxRule Create/modify/enable/disable inbox rule**.</span></span>

<span data-ttu-id="fd393-246">**開始日**と**終了日**の調査に適用される日付の範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd393-246">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="fd393-p133">**ユーザー**が特定のユーザーを調査している、しない限り、空白のままにこのフィールドです。これからは、新しい受信トレイ ルールのすべてのユーザーが設定を識別できます。</span><span class="sxs-lookup"><span data-stu-id="fd393-p133">**Users** - Unless you're investigating a specific user, leave this field blank. This will help you identify new inbox rules set up by any user.</span></span>

<span data-ttu-id="fd393-249">**ファイル、フォルダー、またはサイト**- このフィールドを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="fd393-249">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="fd393-p134">検索を実行すると、このアクティビティの監査レコードが検索結果に表示されます。フライアウトの**詳細**] ページを表示するのには監査レコードをクリックし、[**詳細**] をクリックします。受信トレイ ルールの設定の詳細については、[**パラメーター** ] フィールドに表示されます。次のスクリーン ショットと説明は、受信トレイ ルールに関する情報を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="fd393-p134">After you run the search, any audit records for this activity are displayed in the search results. Click an audit record to display the **Details** flyout page, and then click **More information**. Information about the inbox rule settings are displayed in the **Parameters** field. The following screenshot and descriptions highlights the information about inbox rules.</span></span>

![新しい受信トレイ ルールの監査レコード](media/NewInboxRuleRecord.png)

<span data-ttu-id="fd393-p135">a. [**オブジェクト Id** ] フィールドで、受信トレイの規則の完全な名前が表示されます。この名前には、(たとえば、SaraD) のユーザーのメールボックスのエイリアスと、受信トレイのルール (たとえば、「からメッセージを移動管理」) の名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fd393-p135">a. In the **ObjectId** field, the full name of the inbox rule is displayed. This name includes the alias of the user's mailbox (for example, SaraD) and the name of the inbox rule (for example, "Move messages from admin").</span></span>

<span data-ttu-id="fd393-p136">b.**パラメーター** ] フィールドでは、受信トレイ ルールの条件が表示されます。この例では、条件はパラメーターで指定された*から*です。\*\* パラメーターに定義された値は、admin@alpinehouse.onmicrosoft.com によって送信される電子メールの受信トレイ ルールが機能しことを示します。受信トレイ ルールの条件を定義するのには使用できるパラメーターの一覧は、[新しい InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule)の資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd393-p136">b. In the **Parameters** field, the condition of the inbox rule is displayed. In this example, the condition is specified by the *From* parameter. The value defined for the *From* parameter indicates that the inbox rule acts on email sent by admin@alpinehouse.onmicrosoft.com. For a complete list of the parameters that can be used to define conditions of inbox rules, see the [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) article.</span></span>

<span data-ttu-id="fd393-p137">c. *MoveToFolder*パラメーターは、受信トレイ ルールのアクションを指定します。この例では、admin@alpinehouse.onmicrosoft.com から受信したメッセージが*AdminSearch*をという名前のフォルダーに移動されます。また、受信トレイのルールのアクションを定義するために使用するパラメーターの完全なリストの[新規 InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule)の資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd393-p137">c. The *MoveToFolder* parameter specifies the action for the inbox rule; in this example, messages received from admin@alpinehouse.onmicrosoft.com are moved to the folder named *AdminSearch*. Also see the [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) article for a complete list of parameters that can used to define the action of an inbox rule.</span></span>

<span data-ttu-id="fd393-p138">d.**ユーザー Id**フィールドは、**オブジェクト Id** ] フィールドで指定されている受信トレイ ルールを作成したユーザーを指定します。このユーザーは、検索結果ページの [**ユーザー** ] 列も表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd393-p138">d. The **UserId** field indicate the user who created the inbox rule specified in the **ObjectId** field. This user is also displayed in the **User** column on the search results page.</span></span>