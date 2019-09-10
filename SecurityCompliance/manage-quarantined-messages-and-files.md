---
title: Office 365 の管理者として検疫済みメッセージおよびファイルを管理する
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 09/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: 管理者は、Office 365 セキュリティ & コンプライアンスセンターで検疫済みメッセージを表示および管理する方法について説明します。
ms.openlocfilehash: 0b67abe3dbf21650925b53d2882bc40096d6a646
ms.sourcegitcommit: 81b3bff27bc60235a38004c5b0297ac454331b25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "36822527"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a><span data-ttu-id="a5c9d-103">Office 365 の管理者として検疫済みメッセージおよびファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="a5c9d-103">Manage quarantined messages and files as an admin in Office 365</span></span>

<span data-ttu-id="a5c9d-104">管理者は、検疫済みメッセージを表示、解放、および削除し、Office 365 で誤検知された肯定メッセージを報告することができます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-104">As an admin, you can view, release, and delete quarantined messages, and report false positive quarantined messages in Office 365.</span></span> <span data-ttu-id="a5c9d-105">SharePoint Online、OneDrive for Business、Microsoft Teams の詳細な脅威保護 (ATP) によってキャプチャされた検疫済みファイルの表示、ダウンロード、削除を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-105">You can also view, download, and delete quarantined files captured by Advance Threat Protection (ATP) for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="a5c9d-106">Office 365 がメッセージをフィルター処理して、いくつかの理由で検疫にメッセージを送信するようにポリシーを設定できます。これは、スパム、バルクメール、フィッシングメール、マルウェアを含む、またはメールフロールールに一致したためです。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-106">You can set up policies so that Office 365 filters messages and sends them to quarantine for several reasons: Because they were identified as spam, bulk mail, phishing mail, containing malware, or because they matched a mail flow rule.</span></span>

<span data-ttu-id="a5c9d-107">既定では、Office 365 は、フィッシング詐欺メッセージとマルウェアを含むメッセージを検疫に直接送信します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-107">By default, Office 365 sends phishing messages and messages containing malware directly to quarantine.</span></span> <span data-ttu-id="a5c9d-108">その他のフィルター処理されたメッセージは、検疫に送信するポリシーを設定しない限り、ユーザーの迷惑メールフォルダーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-108">Other filtered messages are sent to users' Junk Email folder unless you set up a policy to send them to quarantine.</span></span>

<span data-ttu-id="a5c9d-109">セキュリティ & コンプライアンスセンターで検疫されたメッセージを表示して処理を行うには、アカウントに次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-109">To view and take action on quarantined messages in the Security & Compliance Center, your account needs one of the following permissions:</span></span>

<span data-ttu-id="a5c9d-110">[**表示のみの受信者の役割**]: 検疫されたメッセージの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-110">**View-Only Recipients role**: View the list of quarantined messages.</span></span>

<span data-ttu-id="a5c9d-111">**セキュリティリーダー役割**: 検疫されたメッセージとそのメッセージヘッダーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-111">**Security Reader role**: View the list of quarantined messages and their message headers.</span></span>

<span data-ttu-id="a5c9d-112">**セキュリティ管理者の役割**: 検疫済みメッセージとそのメッセージヘッダーの一覧を表示します。検疫済みメッセージをプレビュー、リリース、削除、およびダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-112">**Security Administrator role**: View the list of quarantined messages and their message headers; preview, release, delete, and download quarantined messages.</span></span>

<span data-ttu-id="a5c9d-113">既定では、セキュリティ & コンプライアンスセンターのセキュリティ管理者および組織の管理役割グループには、セキュリティ管理者の役割が割り当てられています (これにより、これらの役割グループのいずれかにメンバーシップが付与されます)。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-113">By default, the Security Administrator and Organization Management role groups in the Security & Compliance Center have the Security Administrator role assigned to them (so membership in one of those role groups gives you the permissions).</span></span> <span data-ttu-id="a5c9d-114">詳細については、「 [Office 365 セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-114">For more information, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5c9d-115">既定では、スパム、バルクメッセージ、およびフィッシングメッセージは、30日間検疫に保持されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-115">By default, spam, bulk and phishing messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="a5c9d-116">メールフロールールに一致したために検疫されたメッセージは、7日間検疫に保持されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-116">Messages that are quarantined because they matched a mail flow rule are kept in quarantine for 7 days.</span></span> <span data-ttu-id="a5c9d-117">マルウェアメッセージは、15日間検疫に保持されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-117">Malware messages are kept in quarantine for 15 days.</span></span> <span data-ttu-id="a5c9d-118">セキュリティ & コンプライアンスセンターのスパム対策設定でスパム検疫時間をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-118">You can customize the spam quarantine time in anti-spam settings in the Security & Compliance Center.</span></span> <span data-ttu-id="a5c9d-119">Office 365 では、検疫からメッセージを削除しても、それを取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-119">When Office 365 deletes a message from quarantine, you can't get it back.</span></span> <span data-ttu-id="a5c9d-120">必要に応じて、スパム対策フィルターポリシーの検疫済みメッセージの保持期間を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-120">If you like, you can change the retention period for quarantined messages in your anti-spam filter policies.</span></span> <span data-ttu-id="a5c9d-121">詳細については、このトピックの「[検疫の保存期間を設定](#set-the-quarantine-retention-period)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-121">For more information, see the [Set the quarantine retention period](#set-the-quarantine-retention-period) section in this topic.</span></span>

## <a name="view-your-organizations-quarantined-messages"></a><span data-ttu-id="a5c9d-122">組織の検疫済みメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="a5c9d-122">View your organization's quarantined messages</span></span>

1. <span data-ttu-id="a5c9d-123">[[セキュリティ & コンプライアンスセンター](go-to-the-securitycompliance-center.md) ] を開き、[**脅威管理** \> \*\*\*\* \> ] [**検疫**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-123">[Open the Security & Compliance Center](go-to-the-securitycompliance-center.md) and go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

   > [!TIP]
   > <span data-ttu-id="a5c9d-124">[**検疫**] ページに直接移動するには、次[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)の URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-124">To go directly to the **Quarantine** page, use this URL: [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine).</span></span>

   <span data-ttu-id="a5c9d-125">既定では、セキュリティ & コンプライアンスセンターには、スパムとして検疫されたすべての電子メールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-125">By default, the Security & Compliance Center displays all email messages that have been quarantined as spam.</span></span> <span data-ttu-id="a5c9d-126">メッセージは、メッセージが受信された**日付**に基づいて、降順から最古に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-126">The messages are sorted from newest to oldest based on the **Date** the message was received.</span></span> <span data-ttu-id="a5c9d-127">**送信者**、**件名**、および有効期限 (**有効**期限) は、メッセージごとにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-127">**Sender**, **Subject**, and the expiration date (under **Expires**) are also displayed for each message.</span></span> <span data-ttu-id="a5c9d-128">対応する列見出しをクリックすると、フィールドに対して並べ替えを行うことができます。並べ替え順序を逆にするには、列見出しをもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-128">You can sort on a field by clicking the corresponding column header; click a column header a second time to reverse the sort order.</span></span>

2. <span data-ttu-id="a5c9d-129">すべての検疫済みメッセージの一覧を表示したり、フィルター処理によって結果セットを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-129">You can view a list of all quarantined messages, or you can reduce the result set by filtering.</span></span> <span data-ttu-id="a5c9d-130">一括操作は最大100個のアイテムに対してのみ実行できます。そのため、フィルター処理を行うと、より多くの場合に結果セットを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-130">You can only do bulk operations on up to 100 items, so filtering can also help reduce your result set if you have more than that.</span></span> <span data-ttu-id="a5c9d-131">ページの上部にあるフィルタからオプションを選択することにより、1つの検査理由により、メッセージを簡単にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-131">You can quickly filter messages for a single quarantine reason by choosing an option from the filter at the top of the page.</span></span> <span data-ttu-id="a5c9d-132">次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-132">Options include:</span></span>

   - <span data-ttu-id="a5c9d-133">スパムとして識別されたメール</span><span class="sxs-lookup"><span data-stu-id="a5c9d-133">Mail identified as spam</span></span>

   - <span data-ttu-id="a5c9d-134">メールフロールール (トランスポートルールとも呼ばれる) によって設定されたポリシーに一致したため、メールが隔離されている</span><span class="sxs-lookup"><span data-stu-id="a5c9d-134">Mail quarantined because it matched a policy set by a mail flow rule (also known as a transport rule)</span></span>

   - <span data-ttu-id="a5c9d-135">バルクメールとして識別されたメール</span><span class="sxs-lookup"><span data-stu-id="a5c9d-135">Mail identified as bulk mail</span></span>

   - <span data-ttu-id="a5c9d-136">フィッシングメールとして識別されたメール</span><span class="sxs-lookup"><span data-stu-id="a5c9d-136">Mail identified as phishing mail</span></span>

   - <span data-ttu-id="a5c9d-137">マルウェアを含むメールの検疫</span><span class="sxs-lookup"><span data-stu-id="a5c9d-137">Mail quarantined because it contains malware</span></span>

<span data-ttu-id="a5c9d-138">管理者は、組織のすべてのメッセージをフィルター処理するか、自分に送信されたメッセージのみをフィルター処理するかを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-138">As an admin, you can also choose to filter all messages for your organization or only messages sent to you.</span></span> <span data-ttu-id="a5c9d-139">エンドユーザーは、それらに送信されたメッセージの表示と操作のみが可能です。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-139">End users can only view and work with messages that were sent to them.</span></span>

<span data-ttu-id="a5c9d-140">特定のメッセージを検索するために結果をフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-140">You can also filter your results to find specific messages.</span></span> <span data-ttu-id="a5c9d-141">ヒントについては、このトピックの「[結果をフィルター処理して、検疫済みメッセージおよびファイルを見つける](#filter-the-results-to-find-quarantined-messages-and-files)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-141">For tips, see the [Filter the results to find quarantined messages and files](#filter-the-results-to-find-quarantined-messages-and-files) section in this topic.</span></span>

<span data-ttu-id="a5c9d-142">特定の検疫済みメッセージを見つけた後、メッセージをクリックしてそのメッセージの詳細を表示し、他のユーザーのメールボックスにメッセージを解放するなどのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-142">After you find a specific quarantined message, click the message to view details about it, and take actions, like releasing the message to someone's mailbox.</span></span>

## <a name="view-your-organizations-quarantined-files"></a><span data-ttu-id="a5c9d-143">組織の検疫済みファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="a5c9d-143">View your organization's quarantined files</span></span>

1. <span data-ttu-id="a5c9d-144">[[セキュリティ & コンプライアンスセンター](go-to-the-securitycompliance-center.md) ] を開き、[**脅威管理** \> \*\*\*\* \> ] [**検疫**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-144">[Open the Security & Compliance Center](go-to-the-securitycompliance-center.md) and go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

   > [!TIP]
   > <span data-ttu-id="a5c9d-145">セキュリティ & コンプライアンスセンターの [**検疫**] ページに直接移動するには、次の URL を使用します。 >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="a5c9d-145">To go directly to the **Quarantine** page in the Security & Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>

   <span data-ttu-id="a5c9d-146">既定では、ページには検疫された電子メールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-146">By default, the page displays quarantined email messages.</span></span> <span data-ttu-id="a5c9d-147">検疫されたファイルを表示するには、ページの上部にあるフィルターを、**マルウェア**によって検疫された**ファイル**を表示するように設定します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-147">To view quarantined files, set the filters at the top of the page to show **Files**, quarantined due to **Malware**.</span></span>

   <span data-ttu-id="a5c9d-148">ファイルは、ファイルが検疫された日付に基づいて、最新から最古の順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-148">The files are sorted from newest to oldest based on the date the file was quarantined.</span></span> <span data-ttu-id="a5c9d-149">ファイルを最後に変更した**ユーザー** 、ファイルが投稿された**サービス**、ファイル**名**、**場所**、**ファイルのサイズ**、有効期限 (**有効**期限) は、各ファイルにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-149">The **User** who last modified the file, the **Service** to which the file was posted, the **File Name**, **Location**, **File Size**, and the expiration date ( **Expires**) are also listed for each file.</span></span> <span data-ttu-id="a5c9d-150">ヘッダーをクリックすることで、フィールドに対して並べ替えを行うことができます。並べ替え順序を逆にするには、列見出しをもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-150">You can sort on a field by clicking a header; click a column header a second time to reverse the sort order.</span></span>

2. <span data-ttu-id="a5c9d-151">検疫されたすべてのファイルの一覧を表示することも、フィルター処理によって特定のファイルを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-151">You can view a list of all quarantined files, or you can search for specific files by filtering.</span></span> <span data-ttu-id="a5c9d-152">メッセージと同様に、一括操作は最大100アイテムに対してのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-152">Just like messages, you can only do bulk operations on up to 100 items.</span></span> <span data-ttu-id="a5c9d-153">現在、セキュリティ & コンプライアンスセンターでは、マルウェアが含まれていると識別されるため、検疫内のファイルを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-153">Currently, the Security & Compliance Center lets you view and manage files that are in quarantine because they have been identified as containing malware.</span></span> <span data-ttu-id="a5c9d-154">ヒントについては、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-154">For tips, see the next section.</span></span>

## <a name="filter-the-results-to-find-quarantined-messages-and-files"></a><span data-ttu-id="a5c9d-155">結果をフィルター処理して、検疫済みのメッセージおよびファイルを検索する</span><span class="sxs-lookup"><span data-stu-id="a5c9d-155">Filter the results to find quarantined messages and files</span></span>

<span data-ttu-id="a5c9d-156">設定によっては、検疫されたメッセージとファイルが多数存在することがあります。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-156">Depending on your settings, there may be a lot of quarantined messages and files.</span></span> <span data-ttu-id="a5c9d-157">特定のメッセージまたはファイル、あるいは一連のメッセージまたはファイルを検索するには、さまざまな追加情報に基づいて検疫済みアイテムをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-157">To find a specific message or file or set of messages or files, you can filter quarantined items based on a variety of additional information.</span></span>

1. <span data-ttu-id="a5c9d-158">[**検疫**] ページで、フィルターの先頭行が、必要に応じてメッセージまたはファイルを表示するように設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-158">On the **Quarantine** page, ensure that the top row of filters is set to display messages or files as appropriate:</span></span>

   - <span data-ttu-id="a5c9d-159">ファイルを検索するには、**マルウェア**によって検疫された**ファイル**を表示するようにフィルターを設定します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-159">To search for files, set the filters to show **files** quarantined due to **malware**.</span></span>

     <span data-ttu-id="a5c9d-160">検疫されたファイルの場合、ページには、表示するように指示されているかどうかにかかわらず、自分だけでなく、すべての検疫済みファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-160">For quarantined files, the page displays all quarantined files, not just your own, regardless of what you tell it to show.</span></span>

   - <span data-ttu-id="a5c9d-161">検疫済みメッセージを検索する**には、** **すべて**の**メール**を表示するようにフィルターを設定します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-161">To search for quarantined messages, set filters to show **all** or **only my** **email**.</span></span> <span data-ttu-id="a5c9d-162">最後のフィルターの場合は、探している検疫済みメッセージの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-162">For the last filter choose the type of quarantined message that you're looking for.</span></span> <span data-ttu-id="a5c9d-163">メールフロールール (**トランスポートルール**)、**バルク**メール、**フィッシング**メール、または**マルウェア**を含むメールに一致するメッセージに対して、**スパム**として識別された検疫済みメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-163">You can search for quarantined messages that have been identified as **spam**, for messages that matched a mail flow rule (**transport rule**), **bulk** mail, **phishing** mail, or mail that contains **malware**.</span></span>

2. <span data-ttu-id="a5c9d-164">[**結果の並べ替え**] で、ドロップダウンリストから検索するために使用するフィルターを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-164">Under **Sort results by**, choose the filter or filters you want to use to search from the drop-down lists.</span></span> <span data-ttu-id="a5c9d-165">オプションは、ファイルまたはメッセージを検索するかどうかに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-165">The options vary based on whether you are searching for files or messages.</span></span> <span data-ttu-id="a5c9d-166">この時点では、検索フィールドではワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-166">Wildcards are not supported in search fields at this time.</span></span>

   <span data-ttu-id="a5c9d-167">ファイルとメッセージの両方について、メッセージまたはファイルが検疫に送信された日付によってフィルター処理することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-167">For both files and messages, you can choose to filter by the date the message or file was sent to quarantine.</span></span> <span data-ttu-id="a5c9d-168">時刻を含む日付または日付の範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-168">You can specify the date or a date range, including the time.</span></span> <span data-ttu-id="a5c9d-169">また、ファイルまたはメッセージが検疫から削除される有効期限の日付で検索結果をフィルター処理したり、フィルターの組み合わせを使用したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-169">You can also filter your search results by the expiration date on which the file or message will be deleted from quarantine, or you can use a combination of filters.</span></span> <span data-ttu-id="a5c9d-170">有効期限を指定して検索するには、[**高度なフィルター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-170">To search by expiration date, choose **Advanced filter**.</span></span> <span data-ttu-id="a5c9d-171">[**有効期限**] の下で、次の週に、今後24時間以内 (**今日**48)、次の週 (次の**7\*\*\*\*日)** 以内に削除するメッセージを選択できます。または、カスタムの時間間隔を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-171">Under **Expires**, you can select messages that will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval.</span></span>

   <span data-ttu-id="a5c9d-172">メッセージの場合は、次の追加オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-172">For messages, you have the following additional options:</span></span>

   - <span data-ttu-id="a5c9d-173">**メッセージ id**: メッセージ id がわかっている場合に、このメッセージを使用して特定のメッセージを特定します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-173">**Message ID**: Use this to identify a specific message when you know the message ID.</span></span>

     <span data-ttu-id="a5c9d-174">たとえば、特定のメッセージが組織内のユーザーによって送信された、または対象のユーザーに対して、その送信先に到達していない場合は、[メッセージの追跡](message-trace-scc.md)を使用してメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-174">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reached its destination, you can search for the message by using a [message trace](message-trace-scc.md).</span></span> <span data-ttu-id="a5c9d-175">メッセージが検疫に送信されたことがわかった場合は、メールフロールールと一致した、またはスパムとして識別されたために、メッセージ ID を指定することによって、このメッセージを検疫で簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-175">If you discover that the message was sent to quarantine, perhaps because it matched a mail flow rule or was identified as spam, you can then easily find this message in quarantine by specifying its message ID.</span></span> <span data-ttu-id="a5c9d-176">完全なメッセージ ID 文字列を含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-176">Be sure to include the full message ID string.</span></span> <span data-ttu-id="a5c9d-177">これには、例と\<\> `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`して、山かっこ () を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-177">This might include angle brackets (\<\>), for example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="a5c9d-178">[**送信者のメールアドレス**]: 1 つの送信者の電子メールアドレスでフィルター処理するように選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-178">**Sender email address**: Choose to filter by a single sender email address.</span></span>

   - <span data-ttu-id="a5c9d-179">[**受信者の電子メールアドレス**]: 1 人の受信者の電子メールアドレスでフィルター処理するように選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-179">**Recipient email address**: Choose to filter by a single recipient email address.</span></span>

   - <span data-ttu-id="a5c9d-180">**件名**。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-180">**Subject**.</span></span> <span data-ttu-id="a5c9d-181">検索するメールアドレスの件名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-181">Enter the subject of an email address you want to find.</span></span> <span data-ttu-id="a5c9d-182">ワイルドカード検索はサポートされていないため、検索でメッセージを結果に返すためには、メッセージの件名全体を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-182">Since wildcard searching is not supported, you must use the entire subject of the message in order for search to return the message in the results.</span></span> <span data-ttu-id="a5c9d-183">検索では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-183">The search is not case-sensitive.</span></span>

## <a name="view-details-about-quarantined-messages-and-files"></a><span data-ttu-id="a5c9d-184">検疫されたメッセージとファイルの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="a5c9d-184">View details about quarantined messages and files</span></span>

<span data-ttu-id="a5c9d-185">検疫リストに表示されているアイテムを選択すると、セキュリティ & コンプライアンスセンターの右側の**詳細**ウィンドウに、そのプロパティの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-185">When you select an item displayed in the quarantine list, you'll see a summary of its properties in the **Details** pane on the right side of the Security & Compliance Center.</span></span>

### <a name="details-displayed-for-quarantined-messages"></a><span data-ttu-id="a5c9d-186">検疫済みメッセージに関して表示される詳細情報</span><span class="sxs-lookup"><span data-stu-id="a5c9d-186">Details displayed for quarantined messages</span></span>

- <span data-ttu-id="a5c9d-187">[**メッセージ ID**: メッセージの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-187">**Message ID**: The unique identifier for the message.</span></span>

- <span data-ttu-id="a5c9d-188">**Sender Address**: メッセージの送信者。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-188">**Sender Address**: Who sent the message.</span></span>

- <span data-ttu-id="a5c9d-189">**Received**: メッセージが受信された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-189">**Received**: The date and time the message was received.</span></span>

- <span data-ttu-id="a5c9d-190">**Subject**: メッセージの件名行のテキスト。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-190">**Subject**: The text of the subject line of the message.</span></span>

- <span data-ttu-id="a5c9d-191">**型**: メッセージが**スパム**、 **Bulk**、**フィッシング**、またはメールフロールール (**トランスポートルール**) に一致したか、または**マルウェア**が含まれていると識別されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-191">**Type**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="a5c9d-192">[**有効期限**]: 検疫からメッセージが自動的に削除される日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-192">**Expires**: The date and time when the message will automatically be deleted from quarantine.</span></span>

- <span data-ttu-id="a5c9d-193">[**リリース先**]: メッセージがリリースされたすべての電子メールアドレス (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-193">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="a5c9d-194">まだリリースされて**いない**: メッセージがまだ解放されていないすべての電子メールアドレス (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-194">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="details-displayed-for-quarantined-files"></a><span data-ttu-id="a5c9d-195">検疫されたファイルの詳細情報</span><span class="sxs-lookup"><span data-stu-id="a5c9d-195">Details displayed for quarantined files</span></span>

- <span data-ttu-id="a5c9d-196">**ファイル名**: 検疫に含まれるファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-196">**File Name**: The name of the file in quarantine.</span></span>

- <span data-ttu-id="a5c9d-197">**サイトパス**: Office 365 でのファイルの場所を定義する URL。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-197">**Site path**: URL that defines the location of the file in Office 365.</span></span>

- <span data-ttu-id="a5c9d-198">[**検出された日付/時刻**]: ファイルが検疫された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-198">**Detected Date / Time**: The date and time the file was quarantined.</span></span>

- <span data-ttu-id="a5c9d-199">**Expires**: メッセージが検疫から削除される日付。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-199">**Expires**: The date when the message will be deleted from quarantine.</span></span>

- <span data-ttu-id="a5c9d-200">**検出者**: ファイル内のマルウェアを検出するために使用されるメソッド。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-200">**Detected By**: The method used to detect the malware in the file.</span></span> <span data-ttu-id="a5c9d-201">ATP (Advanced Threat Protection) または Microsoft のマルウェア対策エンジンのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-201">This can be either ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="a5c9d-202">**リリース**: ファイルがリリースされているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-202">**Released**: Describes whether or not the file has been released.</span></span>

- <span data-ttu-id="a5c9d-203">**マルウェア名**: ファイルで検出されたマルウェアのファミリと名前。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-203">**Malware Name**: Family and name of the malware detected in the file.</span></span>

- <span data-ttu-id="a5c9d-204">**ドキュメント ID**: ドキュメントの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-204">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="a5c9d-205">**ファイルサイズ**: ファイルのサイズ (KB 単位)。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-205">**File Size**: The size of the file in KB.</span></span>

- <span data-ttu-id="a5c9d-206">**組織**: Office 365 の組織の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-206">**Organization**: Your organization's unique ID in Office 365.</span></span>

- <span data-ttu-id="a5c9d-207">**更新者**: ファイルを最後に変更したユーザーの職場または学校のアカウント。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-207">**Modified By**: The work or school account of the user who last modified the file.</span></span>

- <span data-ttu-id="a5c9d-208">**ファイルサイズ**: ファイルのサイズ (KB 単位)。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-208">**File Size**: The size of the file in KB.</span></span>

- <span data-ttu-id="a5c9d-209">**SHA256 ハッシュ**: ファイルのハッシュ。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-209">**SHA256 Hash**: The hash of the file.</span></span> <span data-ttu-id="a5c9d-210">これを使用して、他の評価ストアを検索することもできます。または、ファイルが環境内に存在する可能性があることを調査します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-210">You can use this to look up other reputation stores you may have or investigate where else the file might be in your environment.</span></span>

## <a name="manage-messages-and-files-in-quarantine"></a><span data-ttu-id="a5c9d-211">検疫でメッセージとファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="a5c9d-211">Manage messages and files in quarantine</span></span>

<span data-ttu-id="a5c9d-212">検疫でメッセージまたはメッセージのグループを選択すると、メッセージの処理に関するいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-212">After you select a message or group of messages in quarantine, you have several options for what to do with the messages:</span></span>

- <span data-ttu-id="a5c9d-213">何もしないでください。何もしない場合は、有効期限が切れたときに Office 365 によってメッセージが自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-213">Do nothing: If you choose to do nothing, the message will be deleted by Office 365 automatically upon expiration.</span></span> <span data-ttu-id="a5c9d-214">既定では、メールフロールールに一致したために検疫されたスパム、バルク、マルウェア、フィッシング、メッセージは、30日間検疫に保存されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-214">By default, spam, bulk, malware, phishing, and messages quarantined because they matched a mail flow rule are kept in quarantine for 30 days.</span></span> <span data-ttu-id="a5c9d-215">Office 365 では、検疫からメッセージを削除しても、それを取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-215">When Office 365 deletes a message from quarantine, you can't get it back.</span></span> <span data-ttu-id="a5c9d-216">必要に応じて、スパム対策ポリシーの [**スパムを保持する (日)** ] の設定を構成することによって、検疫済みメッセージの保持期間を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-216">If you like, you can change the retention period for quarantined messages by configuring the **Retain spam for (days)** setting in your anti-spam policies.</span></span> <span data-ttu-id="a5c9d-217">詳細については、このトピックの「[検疫の保存期間を設定](#set-the-quarantine-retention-period)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-217">For more information, see the [Set the quarantine retention period](#set-the-quarantine-retention-period) section in this topic.</span></span>

- <span data-ttu-id="a5c9d-218">**メッセージヘッダーを表示**する: メッセージヘッダーのテキストを表示するには、このリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-218">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="a5c9d-219">ヘッダーを詳細に分析するには、メッセージヘッダーのテキストをクリップボードにコピーし、[ **Microsoft メッセージヘッダーアナライザー** ] を選択して、リモート接続アナライザーに移動します (Office を終了しない場合は、右クリックして [**新しいタブで開く]** を選択します)このタスクを完了するには、365。メッセージヘッダーを [メッセージヘッダーアナライザー] セクションのページに貼り付け、[**ヘッダーの分析**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-219">To analyze the header in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**.</span></span>

- <span data-ttu-id="a5c9d-220">[**メッセージのプレビュー**]: メッセージ本文の raw または HTML バージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-220">**Preview message**: Lets you see raw or HTML versions of the message body text.</span></span> <span data-ttu-id="a5c9d-221">HTML ビューでは、リンクは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-221">In the HTML view, links are disabled.</span></span>

- <span data-ttu-id="a5c9d-222">[**メッセージのダウンロード**またはファイルの**ダウンロード**]: このオプションを選択すると、メッセージまたはファイルのコピーがローカルデバイスにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-222">**Download message** or **Download file**: Choose this option to download a copy of the message or file to your local device.</span></span> <span data-ttu-id="a5c9d-223">許可する前に、検疫からのアイテムのダウンロードに関連するリスクを理解していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-223">You'll need to confirm that you understand the risks associated with downloading items from quarantine before you'll be allowed to do so.</span></span> <span data-ttu-id="a5c9d-224">メッセージは、指定したフォルダーに .eml 形式で保存されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-224">Messages are saved in .eml format to a folder you specify.</span></span> <span data-ttu-id="a5c9d-225">検疫済みファイルは、元の形式で保存されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-225">Quarantined files are saved in their original format.</span></span>

- <span data-ttu-id="a5c9d-226">**削除**: 必要に応じて、Office 365 で設定された有効期限を待つ代わりに、検疫されたアイテム (またはアイテムのセット) をすぐに削除できます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-226">**Delete**: If you want, you can immediately delete a quarantined item (or set of items) instead of waiting for the expiration date set by Office 365.</span></span> <span data-ttu-id="a5c9d-227">メッセージまたはファイルを削除するには、[検疫] ボックスの一覧でアイテムを選択し、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-227">To delete a message or file, in the quarantine list, select the item and then choose **Delete**.</span></span> <span data-ttu-id="a5c9d-228">一度に複数のアイテムを削除するには、[検疫] リスト内のアイテムの左側にあるチェックボックスをオンにし、表示される [**一括アクション**] ページで、[選択した**メッセージを削除**する] または [**選択したファイルを削除**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-228">To delete multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Delete selected messages** or **Delete selected files**.</span></span>

- <span data-ttu-id="a5c9d-229">**Release**: 検疫されたアイテム (またはアイテムのセット) を解放し、アイテムが誤って検疫された (誤検知) を Microsoft に報告します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-229">**Release**: Release a quarantined item (or set of items) and report the items as falsely quarantined (false positives) to Microsoft.</span></span>

  <span data-ttu-id="a5c9d-230">1つのメッセージまたはファイルを解放して報告するには、[検疫] の一覧でアイテムを選択し、[**ファイルの解放**] または [**メッセージの解放**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-230">To release and report a single message or file, in the quarantine list, select the item, choose **Release file** or **Release message**.</span></span> <span data-ttu-id="a5c9d-231">次のページで、[分析の**ために microsoft に**、または**ファイル**を分析用に microsoft に報告する] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-231">On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span>

  <span data-ttu-id="a5c9d-232">一度に複数のアイテムを解放するには、[検疫] リスト内のアイテムの左側にあるチェックボックスをオンにし、表示される [**一括アクション**] ページで、[**ファイルの解放**] または [**メッセージの解放**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-232">To release multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Release files** or **Release messages**.</span></span> <span data-ttu-id="a5c9d-233">次のページで、[分析の**ために microsoft に**、または**ファイル**を分析用に microsoft に報告する] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-233">On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span>

<span data-ttu-id="a5c9d-234">メッセージを解放するときは、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-234">When you're releasing messages, be aware of the following:</span></span>

- <span data-ttu-id="a5c9d-235">一度に複数のメッセージの一括リリースを実行すると、メッセージは元に識別されたすべての受信者に解放されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-235">When you perform a bulk release of multiple messages at once, the messages are released to all originally identified recipients.</span></span> <span data-ttu-id="a5c9d-236">特定の受信者にのみメッセージを解放する場合は、一度に1つずつメッセージを解放し、受信者を個別に特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-236">If you only want to release messages only to specific recipients, you need to release the messages one at a time and identify the recipients individually.</span></span>

- <span data-ttu-id="a5c9d-237">同じ受信者に2回以上メッセージを解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-237">A message cannot be released more than once to the same recipient.</span></span>

- <span data-ttu-id="a5c9d-238">複数の受信者にメッセージを解放すると、メッセージを受信していない受信者のみが、潜在的な受信者の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-238">When you're releasing a message to more than one recipient, only recipients who have not previously received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="a5c9d-239">誤検知を報告することを選択すると、解放されたメッセージまたはメッセージがスパム、バルク、フィッシング、またはマルウェアを含むものとして検疫された場合、そのメッセージも Microsoft スパム分析チームに報告されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-239">When you choose to report false positives, if the message or messages you release were quarantined as spam, bulk, phishing, or as containing malware, the message will also be reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="a5c9d-240">チームはメッセージの評価と分析を行い、分析結果によっては、サービス全体のスパムコンテンツフィルタールールを調整してメッセージを通過できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-240">The team will evaluate and analyze the message, and, depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>

## <a name="set-the-quarantine-retention-period"></a><span data-ttu-id="a5c9d-241">検疫の保存期間を設定する</span><span class="sxs-lookup"><span data-stu-id="a5c9d-241">Set the quarantine retention period</span></span>

<span data-ttu-id="a5c9d-242">期限切れになるまでに、メッセージおよびファイルを検疫に保持する期間を構成できます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-242">You can configure how long messages and files will remain in quarantine before they expire.</span></span> <span data-ttu-id="a5c9d-243">既定では、検疫済みアイテムは30日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-243">By default, quarantined items are kept for 30 days.</span></span> <span data-ttu-id="a5c9d-244">この設定は、作成するポリシーごとに構成します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-244">You configure this setting for each policy that you create.</span></span> <span data-ttu-id="a5c9d-245">この記事で説明されているように、既定のポリシーの値を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-245">You can also modify the value for the default policy as described in this article.</span></span>

### <a name="modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security--compliance-center"></a><span data-ttu-id="a5c9d-246">セキュリティ & コンプライアンスセンターで既定のスパムフィルターポリシーの検疫の保存期間を変更する</span><span class="sxs-lookup"><span data-stu-id="a5c9d-246">Modify the quarantine retention period for the default spam filter policy in the Security & Compliance Center</span></span>

1. <span data-ttu-id="a5c9d-247">[[セキュリティ & コンプライアンスセンター](go-to-the-securitycompliance-center.md) ] を開き、[**脅威管理** \> **ポリシー** \> **のスパム対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-247">[Open the Security & Compliance Center](go-to-the-securitycompliance-center.md) and go to **Threat Management** \> **Policy** \> **Anti-spam**.</span></span>

   > [!TIP]
   > <span data-ttu-id="a5c9d-248">[**スパム対策**] ページに直接移動するには、次の URL を使用します。[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span><span class="sxs-lookup"><span data-stu-id="a5c9d-248">To go directly to the **Anti-spam** page, use this URL: [https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span></span>

2. <span data-ttu-id="a5c9d-249">[**カスタム**] を選択して、[**カスタム設定**] タブを表示します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-249">Choose **Custom** to display the **Custom settings** tab.</span></span>

3. <span data-ttu-id="a5c9d-250">**[既定のスパムフィルターポリシー (always ON)** ] 行を展開します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-250">Expand the **Default spam filter policy (always ON)** row.</span></span>

4. <span data-ttu-id="a5c9d-251">[**ポリシーの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-251">Choose **Edit policy**.</span></span> <span data-ttu-id="a5c9d-252">既定のスパムフィルターポリシーの設定が新しいページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-252">The settings for the default spam filter policy appear in a new page.</span></span>

5. <span data-ttu-id="a5c9d-253">**[スパムと一括アクション] を**展開します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-253">Expand **Spam and bulk actions**.</span></span>

6. <span data-ttu-id="a5c9d-254">[**検疫**] の [以下**の期間スパムを保持する (日)** ] テキストボックスに、Office 365 でメッセージおよびファイルを検疫に保持する時間の長さを入力します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-254">Under **Quarantine**, in the **Retain spam for (days)** text box, enter the amount of time you want Office 365 to retain messages and files in quarantine.</span></span> <span data-ttu-id="a5c9d-255">既定値は 30 日です。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-255">The default is 30 days.</span></span> <span data-ttu-id="a5c9d-256">これは最大値でもあります。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-256">This is also the maximum.</span></span>

7. <span data-ttu-id="a5c9d-257">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5c9d-257">Choose **Save**.</span></span>
