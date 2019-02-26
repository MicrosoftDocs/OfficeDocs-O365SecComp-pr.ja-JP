---
title: Office 365 の ATP の安全なリンクを使用して、リライトしないカスタムの url リストを設定する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
description: ATP の安全なリンクポリシーを設定するときに、組織内の一部のユーザーがリストに含まれているサイトにアクセスできるようにするために、url の書き換え不可のリストを含めることができます。
ms.openlocfilehash: 006dab44054f9cb707bb13d158588ab6606fab5c
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2019
ms.locfileid: "30241979"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="2dbd8-103">Office 365 の ATP の安全なリンクを使用して、リライトしないカスタムの url リストを設定する</span><span class="sxs-lookup"><span data-stu-id="2dbd8-103">Set up a custom do-not-rewrite URLs list using Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2dbd8-p101">この記事は、企業のお客様を対象としています。自宅ユーザーで Outlook の安全なリンクに関する詳細情報をご覧になる場合は、「[Office 365 サブスクライバー用の Outlook.com の高度なセキュリティ](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-p101">This article is intended for business customers. If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="2dbd8-p102">[office 365 Advanced Threat Protection](office-365-atp.md) (ATP) を使用すると、組織に[カスタムのブロック](set-up-a-custom-blocked-urls-list-wtih-atp.md)された url を設定できます。これにより、ユーザーが電子メールメッセージや特定の Office ドキュメント内の web アドレス (url) をクリックしたときに、それらの url にアクセスできなくなります。組織では、組織内の特定のグループに対してカスタムの "書き換え不可" リストを作成することもできます。[書き換えない] リストを使用すると、一部のユーザーは、 [Office 365 で ATP の安全なリンク](atp-safe-links.md)によってブロックされている url にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-p102">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-wtih-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs. Your organization can also have custom "do not rewrite" lists for specific groups in your organization. A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span> 
  
<span data-ttu-id="2dbd8-109">この記事では、ATP の安全なリンクスキャンから除外する url の一覧を指定する方法と、注意すべき重要な点について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-109">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="2dbd8-110">「書き換えない」リストを設定する</span><span class="sxs-lookup"><span data-stu-id="2dbd8-110">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="2dbd8-p103">ATP の安全なリンク保護では、組織のブロックされた url のリストや例外の「書き換えない」リストを含むいくつかのリストを使用します。必要なアクセス許可を持っている場合は、カスタムの "書き換えない" リストを設定できます。この操作は、組織内の特定の受信者に適用する安全なリンクポリシーを追加または編集するときに行います。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-p103">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions. If you have the necessary permissions, you can set up your custom "do not rewrite" lists. You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span> 

<span data-ttu-id="2dbd8-114">ATP ポリシーを編集 (または定義) するには、次の表に示す役割の 1 つが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-114">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="2dbd8-115">役割</span><span class="sxs-lookup"><span data-stu-id="2dbd8-115">Role</span></span>  |<span data-ttu-id="2dbd8-116">参照先/割り当て方法</span><span class="sxs-lookup"><span data-stu-id="2dbd8-116">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="2dbd8-117">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="2dbd8-117">Office 365 Global Administrator</span></span> |<span data-ttu-id="2dbd8-p104">Office 365 の購入へのサインアップをする場合、既定ではグローバル管理者になります。詳細については、「[Office 365 の管理者の役割について](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-p104">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="2dbd8-120">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="2dbd8-120">Security Administrator</span></span> |<span data-ttu-id="2dbd8-121">Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="2dbd8-121">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="2dbd8-122">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="2dbd8-122">Exchange Online Organization Management</span></span> |<span data-ttu-id="2dbd8-123">Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="2dbd8-123">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="2dbd8-124">または</span><span class="sxs-lookup"><span data-stu-id="2dbd8-124">or</span></span> <br>  <span data-ttu-id="2dbd8-125">PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="2dbd8-125">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="2dbd8-126">役割とアクセス許可の詳細については、「[Office 365 セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-126">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="2dbd8-127">ユーザー設定の「リライトしない」 url リストを表示または編集するには</span><span class="sxs-lookup"><span data-stu-id="2dbd8-127">To view or edit a custom "do not rewrite" URLs list</span></span>
  
1. <span data-ttu-id="2dbd8-128">[https://protection.office.com](https://protection.office.com) に移動し、職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-128">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="2dbd8-129">左側のナビゲーションで、[**脅威管理** \> **ポリシー** \> **セーフリンク**] の下にあります。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-129">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="2dbd8-p105">[**特定の受信者に適用するポリシー** ] セクションで、[**新規**作成] (新しいボタンは**+** プラス記号 () に似ています) を選択して、新しいポリシーを作成します。(または、既存のポリシーを編集することもできます)。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-p105">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy. (Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="2dbd8-132">![[新規] を選択して、特定の電子メール受信者の安全なリンクポリシーを追加します。](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="2dbd8-132">![Choose New to add a Safe Links policy for specific email recipients](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>
  
4. <span data-ttu-id="2dbd8-133">ポリシーの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-133">Specify a name and description for your policy.</span></span>
    
5. <span data-ttu-id="2dbd8-134">[**次の url を書き換えない**] セクションで、[**有効な url を入力**してください] ボックスを選択し、url を入力して、プラス記号 (+) を選択します。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-134">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+).</span></span> 
    
6. <span data-ttu-id="2dbd8-p106">[**適用先**] セクションで、[**受信者が次のメンバー**である] を選択し、ポリシーに含めるグループを選択します。[**追加**] を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-p106">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
7. <span data-ttu-id="2dbd8-137">画面の右下隅で URL の追加が完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2dbd8-p107">組織の禁止された url のカスタムリストを必ず確認してください。「 [ATP Safe Links を使用してカスタムのブロックされた url リストをセットアップする](set-up-a-custom-blocked-urls-list-wtih-atp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-p107">Make sure to review your organization's custom list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span> 
  
## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="2dbd8-140">留意すべき重要な点</span><span class="sxs-lookup"><span data-stu-id="2dbd8-140">Important points to keep in mind</span></span>

- <span data-ttu-id="2dbd8-141">[書き換えない] ボックスの一覧で指定したすべての url は、指定した受信者の ATP の安全なリンクスキャンから除外されます。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-141">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>
 
- <span data-ttu-id="2dbd8-p108">ATP の安全なリンクポリシーの "書き込み不可" リストを指定する場合は、最大3つのワイルドカードのアスタリスク\*() を含めることができます。のよう\*に、ワイルドカード () は`contoso.com`、または`http://` `https://`のように、明示的にプレフィックスまたはサブドメインを含まないエントリに対して想定されます。これは、「書き換えない」 `contoso.com`リスト`*contoso.com*`のようなエントリを意味します。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-p108">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcard asterisks (\*). Wildcards (\*) are assumed for entries such as `contoso.com`, which do not explicitly include prefixes or subdomains, like `http://` or `https://`. This means an entry, such as `contoso.com` is similar to `*contoso.com*` for your "do not rewrite" list.</span></span>

- <span data-ttu-id="2dbd8-p109">「書き換えない」リスト内に既に url のリストがある場合は、そのリストを確認し、必要に応じてワイルドカードを追加してください。たとえば、既存のリストにそのよう`http://contoso.com/a`なエントリがあり、ポリシーにそのような`http://contoso.com/a/b`サブパスを含める場合は、エントリにワイルドカードを追加`http://contoso.com/a*`して、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-p109">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate. For example, if your existing list has an entry like `http://contoso.com/a` and you want to include subpaths like `http://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `http://contoso.com/a*`.</span></span>
    
- <span data-ttu-id="2dbd8-p110">「書き換えない」の一覧で指定した url にスラッシュ (/) を含めないでください。たとえば、「リライトしない`contoso.com/` 」の一覧で入力するのではなく`contoso.com`、を入力します。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-p110">Do not include a forward slash (/) in the URLs that you specify in your "do not rewrite" list. For example, rather than enter `contoso.com/` in your "do not rewrite" list, enter `contoso.com`.</span></span>
    
<span data-ttu-id="2dbd8-149">次の表に、入力できる内容と、それらのエントリの影響についての例を示します。</span><span class="sxs-lookup"><span data-stu-id="2dbd8-149">The following table lists examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="2dbd8-150">**エントリの例**</span><span class="sxs-lookup"><span data-stu-id="2dbd8-150">**Example Entry**</span></span>|<span data-ttu-id="2dbd8-151">**機能**</span><span class="sxs-lookup"><span data-stu-id="2dbd8-151">**What It Does**</span></span>|
|:-----|:-----|
|`*contoso.com*`  <br/> |<span data-ttu-id="2dbd8-152">特定の受信者が`http://www.contoso.com`、 `https://www.contoso.com` `https://maps.contoso.com`、、またはなどのドメイン、サブドメイン、およびパスにアクセスできるようにします。`http://www.contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="2dbd8-152">Allows specific recipients to visit a domain, subdomains, and paths, such as `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `http://www.contoso.com/a`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="2dbd8-153">特定の受信者が、次`http://contoso.com/a`のようなサブパスではなく、サイトにアクセスできるようにします。`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="2dbd8-153">Allows specific recipients to visit a site like `http://contoso.com/a`, but not subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="2dbd8-154">特定の受信者が、次`http://contoso.com/a`のようなサブパスでサイトにアクセスできるようにします。`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="2dbd8-154">Allows specific recipients to visit a site like `http://contoso.com/a` and subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
 