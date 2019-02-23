---
title: Office 365 ATP Safe Links を使用して、カスタムのブロックされた url リストを設定する
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
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection を使用して、組織でブロックされている url の一覧を設定する方法について説明します。受信拒否された url は、ATP の安全なリンクポリシーに従って、電子メールメッセージおよび Office ドキュメントに適用されます。
ms.openlocfilehash: ad9c613221b94e61022b11541ee068e35e47cc70
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213027"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="5a181-104">Office 365 ATP Safe Links を使用して、カスタムのブロックされた url リストを設定する</span><span class="sxs-lookup"><span data-stu-id="5a181-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a181-p102">この記事は、ビジネスのお客様を対象としています。Outlook の安全なリンクに関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a181-p102">This article is intended for business customers. If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="5a181-p103">[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) を使用すると、ブロックされる web サイトアドレス (url) のカスタムリストを組織に割り当てることができます。url がブロックされると、ブロックされた url へのリンクをクリックしたユーザーは、次のような[警告ページ](atp-safe-links-warning-pages.md)にジャンプします。</span><span class="sxs-lookup"><span data-stu-id="5a181-p103">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![このサイトはブロックされています](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="5a181-110">禁止された url の一覧は、組織の office 365 セキュリティチームによって定義されており、そのリストは、office 365 ATP Safe Links ポリシーでカバーされている組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5a181-110">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="5a181-111">この記事では、 [Office 365 で ATP の安全なリンク](atp-safe-links.md)のために組織のカスタムのブロックされた url リストを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a181-111">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="5a181-112">禁止された url のカスタムリストを表示または編集する</span><span class="sxs-lookup"><span data-stu-id="5a181-112">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="5a181-p104">[Office 365 の ATP の安全なリンク](atp-safe-links.md)では、組織のカスタムブロックされた url リストを含むいくつかのリストが使用されます。必要なアクセス許可がある場合は、組織のカスタムリストを設定できます。これを行うには、組織の既定の安全なリンクポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="5a181-p104">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="5a181-116">ATP ポリシーを編集 (または定義) するには、次の表に示すいずれかの役割を割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a181-116">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="5a181-117">役割</span><span class="sxs-lookup"><span data-stu-id="5a181-117">Role</span></span>  |<span data-ttu-id="5a181-118">場所/割り当て方法</span><span class="sxs-lookup"><span data-stu-id="5a181-118">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="5a181-119">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="5a181-119">Office 365 Global Administrator</span></span> |<span data-ttu-id="5a181-p105">Office 365 の購入にサインアップするユーザーは、既定ではグローバル管理者です。(詳細については、「 [Office 365 管理者の役割につい](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)て」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="5a181-p105">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="5a181-122">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="5a181-122">Security Administrator</span></span> |<span data-ttu-id="5a181-123">Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="5a181-123">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="5a181-124">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="5a181-124">Exchange Online Organization Management</span></span> |<span data-ttu-id="5a181-125">Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="5a181-125">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="5a181-126">または</span><span class="sxs-lookup"><span data-stu-id="5a181-126">or</span></span> <br>  <span data-ttu-id="5a181-127">powershell コマンドレット (「 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照)</span><span class="sxs-lookup"><span data-stu-id="5a181-127">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="5a181-128">役割とアクセス許可の詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a181-128">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="5a181-129">ブロックするカスタム url リストを表示または編集するには</span><span class="sxs-lookup"><span data-stu-id="5a181-129">To view or edit a custom blocked URLs list</span></span>
  
1. <span data-ttu-id="5a181-130">に[https://protection.office.com](https://protection.office.com)移動して、職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="5a181-130">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="5a181-131">左側のナビゲーションで、[**脅威の管理**] の下にある [**ポリシー** \> **セーフリンク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a181-131">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="5a181-132">[**組織全体に適用されるポリシー** ] セクションで、[**既定**] を選択し、[**編集**] を選択します (このボタンは鉛筆に似ています)。</span><span class="sxs-lookup"><span data-stu-id="5a181-132">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="5a181-133">![[編集] をクリックして、安全なリンクの保護のための既定のポリシーを編集します。](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="5a181-133">![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="5a181-p106">これにより、ブロックされた url の一覧を表示できます。最初に、url がここに表示されていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a181-p106">This enables you to view your list of blocked URLs. At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="5a181-136">![既定の安全なリンクポリシーのブロックされた url の一覧](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="5a181-136">![Blocked URLs list in the default Safe Links policy](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="5a181-137">[**有効な url を入力**してください] ボックスを選択し、url を入力し**+** て、プラス記号 () を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a181-137">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="5a181-138">url の追加が終了したら、画面の右下隅にある [**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a181-138">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="5a181-139">留意すべきこと</span><span class="sxs-lookup"><span data-stu-id="5a181-139">A few things to keep in mind</span></span>

<span data-ttu-id="5a181-140">リストに url を追加する際には、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5a181-140">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="5a181-p107">URL の末尾にスラッシュ ( **/**) を含めないでください。たとえば、 `http://www.contoso.com/`と入力する代わりに、 `http://www.contoso.com`を入力します。</span><span class="sxs-lookup"><span data-stu-id="5a181-p107">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
- <span data-ttu-id="5a181-p108">ドメインのみの URL (または`contoso.com` `tailspintoys.com`など) を指定できます。これにより、そのドメインを含む任意の URL のクリックがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="5a181-p108">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="5a181-p109">完全なドメインをブロックせず`toys.contoso.com*`にサブドメイン (like) を指定`contoso.com`することができます (like)。これにより、サブドメインを含む url がクリックによってブロックされますが、完全なドメインを含む url へのクリックはブロックされません。</span><span class="sxs-lookup"><span data-stu-id="5a181-p109">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`). This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="5a181-p110">URL ごとに最大3つのワイルドカード\*のアスタリスク () を含めることができます。次の表に、入力できる内容とそのエントリの影響について、いくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a181-p110">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="5a181-149">**エントリの例**</span><span class="sxs-lookup"><span data-stu-id="5a181-149">**Example Entry**</span></span>|<span data-ttu-id="5a181-150">**機能**</span><span class="sxs-lookup"><span data-stu-id="5a181-150">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5a181-151">`contoso.com`や`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="5a181-151">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="5a181-152">ドメイン、サブドメイン、およびパス (、、など`https://www.contoso.com`) `http://sub.contoso.com`をブロックします。`http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="5a181-152">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="5a181-153">サイト`http://contoso.com/a`をブロックしますが、次のような追加のサブパスはありません。`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="5a181-153">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="5a181-154">サイト`http://contoso.com/a`とその他のサブパスをブロックします。`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="5a181-154">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://toys.contoso.com*`  <br/> |<span data-ttu-id="5a181-155">サブドメイン (この場合は "玩具") をブロックしますが、他のドメインの`http://contoso.com` url `http://home.contoso.com`(またはなど) へのクリックを許可します。</span><span class="sxs-lookup"><span data-stu-id="5a181-155">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `http://contoso.com` or `http://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="5a181-156">組織内の特定のユーザーに対して例外を定義する方法</span><span class="sxs-lookup"><span data-stu-id="5a181-156">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="5a181-p111">特定のグループが他のユーザーに対してブロックされている可能性がある url を表示できるようにする場合は、特定の受信者に適用される ATP の安全なリンクポリシーを指定できます。「 [ATP Safe Links を使用して、ユーザー設定の "書き込み不可" url リストを設定する](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a181-p111">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

