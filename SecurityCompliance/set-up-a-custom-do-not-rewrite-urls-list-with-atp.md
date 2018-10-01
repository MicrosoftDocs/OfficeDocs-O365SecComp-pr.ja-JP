---
title: Office 365 の ATP の安全なリンクを使用してユーザー設定の再書き込みしない操作を行います Url のリストを設定します
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
description: ATP の安全なリンク ・ ポリシーを設定するときは、do not 書き換えを含めることができます ' 人、組織内のリストに含まれるサイトへのアクセスを有効にする Url の一覧です。
ms.openlocfilehash: 3ce783a3f783889bdc59ad8d412c80a79e7dd914
ms.sourcegitcommit: 7032830867eb3fc71760e04b8342aff174c5d757
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "25353263"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="e0ae0-103">Office 365 の ATP の安全なリンクを使用してユーザー設定の再書き込みしない操作を行います Url のリストを設定します</span><span class="sxs-lookup"><span data-stu-id="e0ae0-103">Set up a custom do-not-rewrite URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="e0ae0-p101">[Office 365 の高度な脅威保護](office-365-atp.md)(ATP)、組織が[ブロックされているユーザー設定の Url](set-up-a-custom-blocked-urls-list-wtih-atp.md)では、web 上をクリックしたときのアドレス (Url) を電子メール メッセージまたは特定の Office ドキュメントで、これらの Url へのアクセスを禁止することです。組織は、組織の特定のグループ」を書き換えない」独自のリストもあります。」を書き換えない」の一覧は、人によってはそれ以外の場合、 [Office 365 の ATP の安全なリンク](atp-safe-links.md)によってブロックされている Url にアクセスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-p101">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-wtih-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs. Your organization can also have custom "do not rewrite" lists for specific groups in your organization. A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span> 
  
<span data-ttu-id="e0ae0-107">この資料では、ATP の安全なリンクをスキャンして、いくつかの重要な点に注意してくださいから除外されている Url の一覧を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-107">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="e0ae0-108">「書き換えない」リストを設定します。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-108">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="e0ae0-p102">ATP の安全なリンクの保護は、組織のブロックされた Url] ボックスの一覧「を書き換えない」の例外の一覧など、いくつかのリストを使用します。必要な権限があれば、「を書き換えない」のユーザー設定リストを設定できます。追加または組織内の特定の受信者に適用される安全なリンク ポリシーを編集する場合に実行します。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-p102">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions. If you have the necessary permissions, you can set up your custom "do not rewrite" lists. You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span> 
  
1. <span data-ttu-id="e0ae0-112">[https://protection.office.com](https://protection.office.com)と、職場、学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-112">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="e0ae0-113">**脅威の管理**の下、左側のナビゲーションで\>**ポリシー** \> **安全なリンク**です。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-113">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="e0ae0-p103">**特定の受信者に適用されるポリシー** ] セクションで [**新規**] をクリックして ([新規] ボタンのようなプラス記号 ( **+**)) 新しいポリシーを作成します。(または、することができます既存ポリシーを編集します。)</span><span class="sxs-lookup"><span data-stu-id="e0ae0-p103">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy. (Alternatively, you can edit an existing policy.)</span></span>
    
    ![特定の電子メールの受信者の安全なリンク ポリシーを追加するのには新規を選択します。](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. <span data-ttu-id="e0ae0-117">ポリシーの説明と名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-117">Specify a name and description for your policy.</span></span>
    
5. <span data-ttu-id="e0ae0-118">**次の Url の書き換えを行う**セクションでの**有効な URL を入力**] ボックスを選択し、URL を入力し、プラス記号 (+) を選択し。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-118">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+).</span></span> 
    
6. <span data-ttu-id="e0ae0-p104">[**適用先**] セクションでは、**受信者のメンバーである**を選択し、ポリシーに追加するグループを選択し、します。**追加**を選択し、[ **ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-p104">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
7. <span data-ttu-id="e0ae0-121">画面の右下隅で、Url の追加が完了したら、**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-121">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e0ae0-p105">ブロックされた Url の組織のユーザー設定] ボックスの一覧を確認してください。[ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定する](set-up-a-custom-blocked-urls-list-wtih-atp.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-p105">Make sure to review your organization's custom list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span> 
  
## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="e0ae0-124">重要な点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-124">Important points to keep in mind</span></span>

- <span data-ttu-id="e0ae0-125">「書き換えない」リストで指定したすべての Url は、ATP 安全なリンクを指定する受信者スキャンから除外されます。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-125">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>
 
- <span data-ttu-id="e0ae0-p106">ATP の安全なリンク ・ ポリシー」を書き換えない」の一覧を指定する場合は、最大 3 つのワイルドカードのアスタリスクを含めることができます (\*)。ワイルドカード (\*) と見なされますエントリを次のように`contoso.com`、明示的に変数名は、プレフィックスまたはサブドメインでは、このような`http://`または`https://`。つまり、エントリを次のように`contoso.com`のような`*contoso.com*`「を書き換えない」リストにします。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-p106">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcard asterisks (\*). Wildcards (\*) are assumed for entries such as `contoso.com`, which do not explicitly include prefixes or subdomains, like `http://` or `https://`. This means an entry, such as `contoso.com` is similar to `*contoso.com*` for your "do not rewrite" list.</span></span>

- <span data-ttu-id="e0ae0-p107">「を書き換えない」リストにある Url の一覧が場合に、その一覧を確認し、適切なワイルドカードを追加することを確認してください。などの場合は、既存のリストのエントリなどの`http://contoso.com/a`と同様のサブパスを含めると`http://contoso.com/a/b`で、ポリシーを追加ワイルドカード エントリに次のように`http://contoso.com/a*`。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-p107">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate. For example, if your existing list has an entry like `http://contoso.com/a` and you want to include subpaths like `http://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `http://contoso.com/a*`.</span></span>
    
- <span data-ttu-id="e0ae0-p108">「を書き換えない」リストで指定した Url ではスラッシュ (/) を含めないでください。たとえば、入力するのではなく`contoso.com/`「を書き換えない」リストで、次のように入力します。 `contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-p108">Do not include a forward slash (/) in the URLs that you specify in your "do not rewrite" list. For example, rather than enter `contoso.com/` in your "do not rewrite" list, enter `contoso.com`.</span></span>
    
<span data-ttu-id="e0ae0-133">以下の表リストの例を入力することができ、どのような効果のこれらのエントリがあります。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-133">The following table lists examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="e0ae0-134">**エントリの例**</span><span class="sxs-lookup"><span data-stu-id="e0ae0-134">**Example Entry**</span></span>|<span data-ttu-id="e0ae0-135">**何します。**</span><span class="sxs-lookup"><span data-stu-id="e0ae0-135">**What It Does**</span></span>|
|:-----|:-----|
|`*contoso.com*`  <br/> |<span data-ttu-id="e0ae0-136">特定の受信者を参照してください、ドメイン、サブドメインでは、パス、次のように`http://www.contoso.com`、 `https://www.contoso.com`、 `https://maps.contoso.com`、または`http://www.contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="e0ae0-136">Allows specific recipients to visit a domain, subdomains, and paths, such as `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `http://www.contoso.com/a`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="e0ae0-137">ようなサイトにアクセスするのには特定の受信者では、 `http://contoso.com/a`、サブパスではないようですが、`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="e0ae0-137">Allows specific recipients to visit a site like `http://contoso.com/a`, but not subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="e0ae0-138">ようなサイトにアクセスするのには特定の受信者では、`http://contoso.com/a`のサブパスを含めると`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="e0ae0-138">Allows specific recipients to visit a site like `http://contoso.com/a` and subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
  

## <a name="related-topics"></a><span data-ttu-id="e0ae0-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0ae0-139">Related topics</span></span>

[<span data-ttu-id="e0ae0-140">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e0ae0-140">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="e0ae0-141">Office 365 で ATP の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="e0ae0-141">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="e0ae0-142">Office 365 の ATP の安全なリンクのポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="e0ae0-142">Set up ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="e0ae0-143">ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定します。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-143">Set up a custom blocked URLs list using ATP Safe Links</span></span>](set-up-a-custom-blocked-urls-list-wtih-atp.md)

[<span data-ttu-id="e0ae0-144">Office 365 の高度な脅威保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="e0ae0-144">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="e0ae0-145">Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="e0ae0-145">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

