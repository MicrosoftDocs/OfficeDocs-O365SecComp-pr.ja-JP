---
title: Office 365 の ATP の安全なリンクを使用してユーザー設定の再書き込みしない操作を行います Url のリストを設定します
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
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
description: ATP の安全なリンク ・ ポリシーを設定するときは、do not 書き換えを含めることができます ' 人、組織内のリストに含まれるサイトへのアクセスを有効にする Url の一覧です。
ms.openlocfilehash: 5eb2d09f1d1d77fa9d6ffdb9f14ba9e7522da287
ms.sourcegitcommit: d6a28c4f6db6a676ca960173e8ff8f17d4aa1c4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29755288"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="71d3f-103">Office 365 の ATP の安全なリンクを使用してユーザー設定の再書き込みしない操作を行います Url のリストを設定します</span><span class="sxs-lookup"><span data-stu-id="71d3f-103">Set up a custom do-not-rewrite URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="71d3f-p101">[Office 365 の高度な脅威保護](office-365-atp.md)(ATP)、組織が[ブロックされているユーザー設定の Url](set-up-a-custom-blocked-urls-list-wtih-atp.md)では、web 上をクリックしたときのアドレス (Url) を電子メール メッセージまたは特定の Office ドキュメントで、これらの Url へのアクセスを禁止することです。組織は、組織の特定のグループ」を書き換えない」独自のリストもあります。」を書き換えない」の一覧は、人によってはそれ以外の場合、 [Office 365 の ATP の安全なリンク](atp-safe-links.md)によってブロックされている Url にアクセスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="71d3f-p101">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-wtih-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs. Your organization can also have custom "do not rewrite" lists for specific groups in your organization. A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span> 
  
<span data-ttu-id="71d3f-107">この資料では、ATP の安全なリンクをスキャンして、いくつかの重要な点に注意してくださいから除外されている Url の一覧を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="71d3f-107">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="71d3f-108">「書き換えない」リストを設定します。</span><span class="sxs-lookup"><span data-stu-id="71d3f-108">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="71d3f-p102">ATP の安全なリンクの保護は、組織のブロックされた Url] ボックスの一覧「を書き換えない」の例外の一覧など、いくつかのリストを使用します。必要な権限があれば、「を書き換えない」のユーザー設定リストを設定できます。追加または組織内の特定の受信者に適用される安全なリンク ポリシーを編集する場合に実行します。</span><span class="sxs-lookup"><span data-stu-id="71d3f-p102">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions. If you have the necessary permissions, you can set up your custom "do not rewrite" lists. You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span> 

<span data-ttu-id="71d3f-112">ATP のポリシーを編集 (または定義) を割り当てる必要があります、次の表に記載されている役割のいずれか。</span><span class="sxs-lookup"><span data-stu-id="71d3f-112">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="71d3f-113">役割</span><span class="sxs-lookup"><span data-stu-id="71d3f-113">Role</span></span>  |<span data-ttu-id="71d3f-114">場所と方法が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="71d3f-114">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="71d3f-115">Office 365 のグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="71d3f-115">Office 365 Global Administrator</span></span> |<span data-ttu-id="71d3f-p103">Office 365 を購入するのに署名した人は、既定でグローバル管理者です。( [Office 365 の管理者の役割](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)の詳細についてを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="71d3f-p103">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="71d3f-118">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="71d3f-118">Security Administrator</span></span> |<span data-ttu-id="71d3f-119">Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="71d3f-119">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="71d3f-120">Exchange オンライン組織の管理</span><span class="sxs-lookup"><span data-stu-id="71d3f-120">Exchange Online Organization Management</span></span> |<span data-ttu-id="71d3f-121">Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="71d3f-121">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="71d3f-122">または</span><span class="sxs-lookup"><span data-stu-id="71d3f-122">or</span></span> <br>  <span data-ttu-id="71d3f-123">PowerShell コマンドレット (を参照してください[Exchange オンライン PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="71d3f-123">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="71d3f-124">ロールとアクセス許可の詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="71d3f-124">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="71d3f-125">表示またはカスタム」を書き換えない"Url リストを編集するには</span><span class="sxs-lookup"><span data-stu-id="71d3f-125">To view or edit a custom "do not rewrite" URLs list</span></span>
  
1. <span data-ttu-id="71d3f-126">[https://protection.office.com](https://protection.office.com)と、職場、学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="71d3f-126">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="71d3f-127">**脅威の管理**の下、左側のナビゲーションで\>**ポリシー** \> **安全なリンク**です。</span><span class="sxs-lookup"><span data-stu-id="71d3f-127">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="71d3f-p104">**特定の受信者に適用されるポリシー** ] セクションで [**新規**] をクリックして ([新規] ボタンのようなプラス記号 ( **+**)) 新しいポリシーを作成します。(または、することができます既存ポリシーを編集します。)</span><span class="sxs-lookup"><span data-stu-id="71d3f-p104">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy. (Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="71d3f-130">![特定の電子メールの受信者の安全なリンク ポリシーを追加するのには新規を選択します。](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="71d3f-130">![Choose New to add a Safe Links policy for specific email recipients](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>
  
4. <span data-ttu-id="71d3f-131">ポリシーの説明と名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="71d3f-131">Specify a name and description for your policy.</span></span>
    
5. <span data-ttu-id="71d3f-132">**次の Url の書き換えを行う**セクションでの**有効な URL を入力**] ボックスを選択し、URL を入力し、プラス記号 (+) を選択し。</span><span class="sxs-lookup"><span data-stu-id="71d3f-132">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+).</span></span> 
    
6. <span data-ttu-id="71d3f-p105">[**適用先**] セクションでは、**受信者のメンバーである**を選択し、ポリシーに追加するグループを選択し、します。**追加**を選択し、[ **ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71d3f-p105">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
7. <span data-ttu-id="71d3f-135">画面の右下隅で、Url の追加が完了したら、**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="71d3f-135">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="71d3f-p106">ブロックされた Url の組織のユーザー設定] ボックスの一覧を確認してください。[ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定する](set-up-a-custom-blocked-urls-list-wtih-atp.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71d3f-p106">Make sure to review your organization's custom list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span> 
  
## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="71d3f-138">重要な点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="71d3f-138">Important points to keep in mind</span></span>

- <span data-ttu-id="71d3f-139">「書き換えない」リストで指定したすべての Url は、ATP 安全なリンクを指定する受信者スキャンから除外されます。</span><span class="sxs-lookup"><span data-stu-id="71d3f-139">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>
 
- <span data-ttu-id="71d3f-p107">ATP の安全なリンク ・ ポリシー」を書き換えない」の一覧を指定する場合は、最大 3 つのワイルドカードのアスタリスクを含めることができます (\*)。ワイルドカード (\*) と見なされますエントリを次のように`contoso.com`、明示的に変数名は、プレフィックスまたはサブドメインでは、このような`http://`または`https://`。つまり、エントリを次のように`contoso.com`のような`*contoso.com*`「を書き換えない」リストにします。</span><span class="sxs-lookup"><span data-stu-id="71d3f-p107">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcard asterisks (\*). Wildcards (\*) are assumed for entries such as `contoso.com`, which do not explicitly include prefixes or subdomains, like `http://` or `https://`. This means an entry, such as `contoso.com` is similar to `*contoso.com*` for your "do not rewrite" list.</span></span>

- <span data-ttu-id="71d3f-p108">「を書き換えない」リストにある Url の一覧が場合に、その一覧を確認し、適切なワイルドカードを追加することを確認してください。などの場合は、既存のリストのエントリなどの`http://contoso.com/a`と同様のサブパスを含めると`http://contoso.com/a/b`で、ポリシーを追加ワイルドカード エントリに次のように`http://contoso.com/a*`。</span><span class="sxs-lookup"><span data-stu-id="71d3f-p108">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate. For example, if your existing list has an entry like `http://contoso.com/a` and you want to include subpaths like `http://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `http://contoso.com/a*`.</span></span>
    
- <span data-ttu-id="71d3f-p109">「を書き換えない」リストで指定した Url ではスラッシュ (/) を含めないでください。たとえば、入力するのではなく`contoso.com/`「を書き換えない」リストで、次のように入力します。 `contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="71d3f-p109">Do not include a forward slash (/) in the URLs that you specify in your "do not rewrite" list. For example, rather than enter `contoso.com/` in your "do not rewrite" list, enter `contoso.com`.</span></span>
    
<span data-ttu-id="71d3f-147">以下の表リストの例を入力することができ、どのような効果のこれらのエントリがあります。</span><span class="sxs-lookup"><span data-stu-id="71d3f-147">The following table lists examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="71d3f-148">**エントリの例**</span><span class="sxs-lookup"><span data-stu-id="71d3f-148">**Example Entry**</span></span>|<span data-ttu-id="71d3f-149">**何します。**</span><span class="sxs-lookup"><span data-stu-id="71d3f-149">**What It Does**</span></span>|
|:-----|:-----|
|`*contoso.com*`  <br/> |<span data-ttu-id="71d3f-150">特定の受信者を参照してください、ドメイン、サブドメインでは、パス、次のように`http://www.contoso.com`、 `https://www.contoso.com`、 `https://maps.contoso.com`、または`http://www.contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="71d3f-150">Allows specific recipients to visit a domain, subdomains, and paths, such as `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `http://www.contoso.com/a`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="71d3f-151">ようなサイトにアクセスするのには特定の受信者では、 `http://contoso.com/a`、サブパスではないようですが、`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="71d3f-151">Allows specific recipients to visit a site like `http://contoso.com/a`, but not subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="71d3f-152">ようなサイトにアクセスするのには特定の受信者では、`http://contoso.com/a`のサブパスを含めると`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="71d3f-152">Allows specific recipients to visit a site like `http://contoso.com/a` and subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
 