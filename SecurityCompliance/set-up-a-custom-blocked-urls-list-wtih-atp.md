---
title: Office 365 の ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定します。
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection: M365-security-compliance
description: Office 365 の高度な脅威保護を使用して、組織のブロックされた Url の一覧を設定する方法について説明します。ブロックされた Url は、電子メール メッセージと、ATP の安全なリンク ポリシーに基づき、Office ドキュメントに適用されます。
ms.openlocfilehash: 261d85ce72de3a19ed4c2327d56fe1f32107781b
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995318"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="47544-104">Office 365 の ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定します。</span><span class="sxs-lookup"><span data-stu-id="47544-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47544-p102">この資料は、ビジネスのお客様向けです。ホーム ユーザーが Outlook での安全なリンクに関する情報を検索する場合は、 [Outlook.com の高度なセキュリティ](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47544-p102">This article is intended for business customers. If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="47544-p103">[Office 365 の高度な脅威保護](office-365-atp.md)(ATP)、組織はブロックされている web サイト アドレス (Url) のユーザー設定リストを持つことができます。URL がブロックされると、ブロックされた URL へのリンクをクリックするユーザーが次の図のような[警告ページ](atp-safe-links-warning-pages.md)に実行されます。</span><span class="sxs-lookup"><span data-stu-id="47544-p103">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![このサイトがブロックされています。](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="47544-110">組織の Office 365 のセキュリティ チームがブロックされている Url のリストが定義されているし、Office 365 の ATP の安全なリンク ポリシーの対象となる組織内の全員がそのリストが適用されます。</span><span class="sxs-lookup"><span data-stu-id="47544-110">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="47544-111">[Office 365 の安全なリンクを ATP](atp-safe-links.md)の組織のカスタム ブロックされた Url の一覧を設定する方法の詳細については、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47544-111">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="47544-112">表示またはブロックされた Url のカスタム リストを編集します。</span><span class="sxs-lookup"><span data-stu-id="47544-112">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="47544-p104">[Office 365 の ATP の安全なリンク](atp-safe-links.md)では、組織のカスタム ブロックされた Url の一覧を含む、いくつかのリストを使用します。必要な権限があれば、組織のユーザー設定リストを設定できます。組織の安全なリンクの既定のポリシーを編集することによってこれを行います。</span><span class="sxs-lookup"><span data-stu-id="47544-p104">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="47544-116">ATP のポリシーを編集 (または定義) を割り当てる必要があります、次の表に記載されている役割のいずれか。</span><span class="sxs-lookup"><span data-stu-id="47544-116">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="47544-117">役割</span><span class="sxs-lookup"><span data-stu-id="47544-117">Role</span></span>  |<span data-ttu-id="47544-118">場所と方法が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="47544-118">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="47544-119">Office 365 のグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="47544-119">Office 365 Global Administrator</span></span> |<span data-ttu-id="47544-p105">Office 365 を購入するのに署名した人は、既定でグローバル管理者です。( [Office 365 の管理者の役割](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)の詳細についてを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="47544-p105">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="47544-122">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="47544-122">Security Administrator</span></span> |<span data-ttu-id="47544-123">Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="47544-123">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="47544-124">Exchange オンライン組織の管理</span><span class="sxs-lookup"><span data-stu-id="47544-124">Exchange Online Organization Management</span></span> |<span data-ttu-id="47544-125">Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="47544-125">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="47544-126">または</span><span class="sxs-lookup"><span data-stu-id="47544-126">or</span></span> <br>  <span data-ttu-id="47544-127">PowerShell コマンドレット (を参照してください[Exchange オンライン PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="47544-127">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="47544-128">ロールとアクセス許可の詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="47544-128">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="47544-129">表示またはブロックされた Url のユーザー設定リストを編集するには</span><span class="sxs-lookup"><span data-stu-id="47544-129">To view or edit a custom blocked URLs list</span></span>
  
1. <span data-ttu-id="47544-130">[https://protection.office.com](https://protection.office.com)と、職場、学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="47544-130">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="47544-131">**脅威の管理**の下で、左側のナビゲーションで [**ポリシー** ] を選択します\>**安全なリンク**です。</span><span class="sxs-lookup"><span data-stu-id="47544-131">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="47544-132">**組織全体に適用されるポリシー** ] セクションで **[既定**] を選択しの**編集**([編集] ボタンのような鉛筆) します。</span><span class="sxs-lookup"><span data-stu-id="47544-132">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="47544-133">![安全なリンクの保護のため、既定のポリシーを編集するのにはの編集] をクリックします。](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="47544-133">![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="47544-p106">これにより、ブロックされた Url の一覧を表示することができます。最初は、ここで記載されているすべての Url をいない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47544-p106">This enables you to view your list of blocked URLs. At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="47544-136">![安全なリンクの既定のポリシーの Url] ボックスの一覧のブロック](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="47544-136">![Blocked URLs list in the default Safe Links policy](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="47544-137">**有効な URL を入力**] ボックスを選択、URL を入力し、プラス記号を選択し、(**+**)。</span><span class="sxs-lookup"><span data-stu-id="47544-137">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="47544-138">画面の右下隅で、Url の追加が完了したら、**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="47544-138">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="47544-139">点に留意してください。</span><span class="sxs-lookup"><span data-stu-id="47544-139">A few things to keep in mind</span></span>

<span data-ttu-id="47544-140">リストに Url を追加するときに、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="47544-140">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="47544-p107">スラッシュが含まれていない ( **/**)、URL の末尾にします。入力するのではなく、たとえば、 `http://www.contoso.com/`、入力`http://www.contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="47544-p107">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
- <span data-ttu-id="47544-p108">ドメイン専用の URL を指定することができます (のような`contoso.com`または`tailspintoys.com`)。クリック ノイズをブロックするこのドメインが含まれる任意の URL にします。</span><span class="sxs-lookup"><span data-stu-id="47544-p108">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="47544-p109">サブドメインを指定することができます (のような`toys.contoso.com*`)、完全なドメインをブロックすることがなく (と同様に`contoso.com`)。このブロックは、サブドメインを含む任意の URL をクリックすると、クリック ノイズをブロックしない、完全なドメインを含む URL にします。</span><span class="sxs-lookup"><span data-stu-id="47544-p109">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`). This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="47544-p110">最大 3 つのワイルドカードのアスタリスクを含めることができます (\*) あたりの URL です。入力することができ、どのような効果のこれらのエントリの例をいくつかが次の表の一覧です。</span><span class="sxs-lookup"><span data-stu-id="47544-p110">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="47544-149">**エントリの例**</span><span class="sxs-lookup"><span data-stu-id="47544-149">**Example Entry**</span></span>|<span data-ttu-id="47544-150">**何します。**</span><span class="sxs-lookup"><span data-stu-id="47544-150">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="47544-151">`contoso.com`または`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="47544-151">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="47544-152">ドメイン、サブドメイン、およびパスを次のようにブロック`https://www.contoso.com`、`http://sub.contoso.com`と`http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="47544-152">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="47544-153">サイトをブロックする`http://contoso.com/a`いない追加のサブパスのような`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="47544-153">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="47544-154">サイトをブロックする`http://contoso.com/a`などの他のサブパスを含めると`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="47544-154">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://toys.contoso.com*`  <br/> |<span data-ttu-id="47544-155">サブドメイン (この場合の「おもちゃ」)、ブロックは他のドメインの Url をクリックを許可する (のような`http://contoso.com`または`http://home.contoso.com`)。</span><span class="sxs-lookup"><span data-stu-id="47544-155">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `http://contoso.com` or `http://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="47544-156">組織で特定のユーザーに対して例外を定義する方法</span><span class="sxs-lookup"><span data-stu-id="47544-156">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="47544-p111">特定のグループが他のユーザーがブロックされている Url を表示できるようにする場合は、特定の受信者に適用される分析ツールの安全なリンクのポリシーを指定できます。[ATP の安全なリンクを使用してカスタム」を書き換えない"Url リストを設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47544-p111">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

