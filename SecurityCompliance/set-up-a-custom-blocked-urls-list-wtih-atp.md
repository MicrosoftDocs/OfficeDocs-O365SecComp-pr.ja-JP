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
description: Office 365 の高度な脅威保護を使用して、組織のブロックされた Url の一覧を設定する方法について説明します。ブロックされた Url は、電子メール メッセージと、ATP の安全なリンク ポリシーに基づき、Office ドキュメントに適用されます。
ms.openlocfilehash: 4d8c9c669310137d3f491f5a79c93f4d6af71ac5
ms.sourcegitcommit: d6a28c4f6db6a676ca960173e8ff8f17d4aa1c4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29755318"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="b4c3d-104">Office 365 の ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定します。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="b4c3d-p102">[Office 365 の高度な脅威保護](office-365-atp.md)(ATP)、組織はブロックされている web サイト アドレス (Url) のユーザー設定リストを持つことができます。URL がブロックされると、ブロックされた URL へのリンクをクリックするユーザーが次の図のような[警告ページ](atp-safe-links-warning-pages.md)に実行されます。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-p102">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![このサイトがブロックされています。](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="b4c3d-108">組織の Office 365 のセキュリティ チームがブロックされている Url のリストが定義されているし、Office 365 の ATP の安全なリンク ポリシーの対象となる組織内の全員がそのリストが適用されます。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-108">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="b4c3d-109">[Office 365 の安全なリンクを ATP](atp-safe-links.md)の組織のカスタム ブロックされた Url の一覧を設定する方法の詳細については、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-109">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="b4c3d-110">表示またはブロックされた Url のカスタム リストを編集します。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-110">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="b4c3d-p103">[Office 365 の ATP の安全なリンク](atp-safe-links.md)では、組織のカスタム ブロックされた Url の一覧を含む、いくつかのリストを使用します。必要な権限があれば、組織のユーザー設定リストを設定できます。組織の安全なリンクの既定のポリシーを編集することによってこれを行います。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-p103">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="b4c3d-114">ATP のポリシーを編集 (または定義) を割り当てる必要があります、次の表に記載されている役割のいずれか。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-114">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="b4c3d-115">役割</span><span class="sxs-lookup"><span data-stu-id="b4c3d-115">Role</span></span>  |<span data-ttu-id="b4c3d-116">場所と方法が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-116">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="b4c3d-117">Office 365 のグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="b4c3d-117">Office 365 Global Administrator</span></span> |<span data-ttu-id="b4c3d-p104">Office 365 を購入するのに署名した人は、既定でグローバル管理者です。( [Office 365 の管理者の役割](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)の詳細についてを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-p104">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="b4c3d-120">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="b4c3d-120">Security Administrator</span></span> |<span data-ttu-id="b4c3d-121">Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="b4c3d-121">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="b4c3d-122">Exchange オンライン組織の管理</span><span class="sxs-lookup"><span data-stu-id="b4c3d-122">Exchange Online Organization Management</span></span> |<span data-ttu-id="b4c3d-123">Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="b4c3d-123">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="b4c3d-124">または</span><span class="sxs-lookup"><span data-stu-id="b4c3d-124">or</span></span> <br>  <span data-ttu-id="b4c3d-125">PowerShell コマンドレット (を参照してください[Exchange オンライン PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="b4c3d-125">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="b4c3d-126">ロールとアクセス許可の詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-126">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="b4c3d-127">表示またはブロックされた Url のユーザー設定リストを編集するには</span><span class="sxs-lookup"><span data-stu-id="b4c3d-127">To view or edit a custom blocked URLs list</span></span>
  
1. <span data-ttu-id="b4c3d-128">[https://protection.office.com](https://protection.office.com)と、職場、学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-128">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="b4c3d-129">**脅威の管理**の下で、左側のナビゲーションで [**ポリシー** ] を選択します\>**安全なリンク**です。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-129">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="b4c3d-130">**組織全体に適用されるポリシー** ] セクションで **[既定**] を選択しの**編集**([編集] ボタンのような鉛筆) します。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-130">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="b4c3d-131">![安全なリンクの保護のため、既定のポリシーを編集するのにはの編集] をクリックします。](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="b4c3d-131">![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="b4c3d-p105">これにより、ブロックされた Url の一覧を表示することができます。最初は、ここで記載されているすべての Url をいない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-p105">This enables you to view your list of blocked URLs. At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="b4c3d-134">![安全なリンクの既定のポリシーの Url] ボックスの一覧のブロック](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="b4c3d-134">![Blocked URLs list in the default Safe Links policy](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="b4c3d-135">**有効な URL を入力**] ボックスを選択、URL を入力し、プラス記号を選択し、(**+**)。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-135">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="b4c3d-136">画面の右下隅で、Url の追加が完了したら、**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-136">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="b4c3d-137">点に留意してください。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-137">A few things to keep in mind</span></span>

<span data-ttu-id="b4c3d-138">リストに Url を追加するときに、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-138">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="b4c3d-p106">スラッシュが含まれていない ( **/**)、URL の末尾にします。入力するのではなく、たとえば、 `http://www.contoso.com/`、入力`http://www.contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-p106">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
- <span data-ttu-id="b4c3d-p107">ドメイン専用の URL を指定することができます (のような`contoso.com`または`tailspintoys.com`)。クリック ノイズをブロックするこのドメインが含まれる任意の URL にします。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-p107">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="b4c3d-p108">サブドメインを指定することができます (のような`toys.contoso.com*`)、完全なドメインをブロックすることがなく (と同様に`contoso.com`)。このブロックは、サブドメインを含む任意の URL をクリックすると、クリック ノイズをブロックしない、完全なドメインを含む URL にします。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-p108">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`). This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="b4c3d-p109">最大 3 つのワイルドカードのアスタリスクを含めることができます (\*) あたりの URL です。入力することができ、どのような効果のこれらのエントリの例をいくつかが次の表の一覧です。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-p109">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="b4c3d-147">**エントリの例**</span><span class="sxs-lookup"><span data-stu-id="b4c3d-147">**Example Entry**</span></span>|<span data-ttu-id="b4c3d-148">**何します。**</span><span class="sxs-lookup"><span data-stu-id="b4c3d-148">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4c3d-149">`contoso.com`または`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="b4c3d-149">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="b4c3d-150">ドメイン、サブドメイン、およびパスを次のようにブロック`https://www.contoso.com`、`http://sub.contoso.com`と`http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="b4c3d-150">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="b4c3d-151">サイトをブロックする`http://contoso.com/a`いない追加のサブパスのような`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="b4c3d-151">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="b4c3d-152">サイトをブロックする`http://contoso.com/a`などの他のサブパスを含めると`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="b4c3d-152">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://toys.contoso.com*`  <br/> |<span data-ttu-id="b4c3d-153">サブドメイン (この場合の「おもちゃ」)、ブロックは他のドメインの Url をクリックを許可する (のような`http://contoso.com`または`http://home.contoso.com`)。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-153">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `http://contoso.com` or `http://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="b4c3d-154">組織で特定のユーザーに対して例外を定義する方法</span><span class="sxs-lookup"><span data-stu-id="b4c3d-154">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="b4c3d-p110">特定のグループが他のユーザーがブロックされている Url を表示できるようにする場合は、特定の受信者に適用される分析ツールの安全なリンクのポリシーを指定できます。[ATP の安全なリンクを使用してカスタム」を書き換えない"Url リストを設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4c3d-p110">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

