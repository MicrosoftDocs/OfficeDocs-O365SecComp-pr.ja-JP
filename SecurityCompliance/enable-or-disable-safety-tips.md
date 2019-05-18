---
title: Office 365 で安全性のヒントを有効または無効にする
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
ms.collection:
- M365-security-compliance
description: Office 365 と EOP admins に、電子メールメッセージの安全性に関するヒントを有効または無効にする方法を伝えます。
ms.openlocfilehash: a782c9a1eca874c2aa2128b6129257067c63219a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154759"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a><span data-ttu-id="73f11-103">Office 365 で安全性のヒントを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="73f11-103">Enable or disable safety tips in Office 365</span></span>

<span data-ttu-id="73f11-104">Exchange Online Protection (EOP) は、配信する電子メールメッセージに安全なヒントを追加またはスタンプします。</span><span class="sxs-lookup"><span data-stu-id="73f11-104">Exchange Online Protection (EOP) adds, or stamps, a safety tip to email messages that it delivers.</span></span> <span data-ttu-id="73f11-105">これらの安全なヒントにより、メッセージが安全であることを確認するための視覚的な方法、メッセージが Office 365 によってスパムとしてマークされている場合、メッセージにフィッシング詐欺などの疑わしいものが含まれている場合、または外部画像がある場合は、ブロックされています。</span><span class="sxs-lookup"><span data-stu-id="73f11-105">These safety tips provide recipients with a quick, visual way to determine if a message is from a safe, verified sender, if the message has been marked as spam by Office 365, if the message contains something suspicious such as a phishing scam, or if external images have been blocked.</span></span> <span data-ttu-id="73f11-106">Office 365 と EOP の管理者は、スパムポリシー設定を編集して、Outlook およびその他のデスクトップ電子メールクライアントでの安全なヒントの表示を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="73f11-106">Office 365 and EOP-standalone admins can edit a spam policy setting to enable or disable safety tips from being displayed in email in Outlook and other desktop email clients.</span></span> 
  
<span data-ttu-id="73f11-107">Office 365 では、組織のために既定で安全なヒントが有効になっており、スパムやフィッシング攻撃に対処できるようにしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="73f11-107">Office 365 enables safety tips by default for your organization and we recommend that you leave them enabled to help combat spam and phishing attacks.</span></span> <span data-ttu-id="73f11-108">Web 上の Outlook の安全性に関するヒントを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="73f11-108">You can't disable safety tips for Outlook on the web.</span></span>
  
<span data-ttu-id="73f11-109">例を確認し、安全なヒントに表示される情報について詳しくは、「 [Office 365 の電子メールメッセージの安全性に関するヒント](safety-tips-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73f11-109">To see examples and to learn about the information displayed in safety tips, see [Safety tips in email messages in Office 365.](safety-tips-in-office-365.md)</span></span>
  
<span data-ttu-id="73f11-110">このトピックの内容</span><span class="sxs-lookup"><span data-stu-id="73f11-110">In this topic:</span></span>
  
- [<span data-ttu-id="73f11-111">Office 365 セキュリティ&amp;コンプライアンスセンターを使用して安全性ヒントを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="73f11-111">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [<span data-ttu-id="73f11-112">PowerShell を使用して安全性ヒントを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="73f11-112">To enable or disable safety tips by using PowerShell</span></span>](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="73f11-113">Office 365 セキュリティ&amp;コンプライアンスセンターを使用して安全性ヒントを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="73f11-113">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>
<span data-ttu-id="73f11-114"><a name="SandCCsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="73f11-114"></span></span>

1. <span data-ttu-id="73f11-115">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="73f11-115">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="73f11-116">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="73f11-116">Sign in to Office 365 with your work or school account.</span></span>
    
3. <span data-ttu-id="73f11-117">[**脅威管理** \> **ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="73f11-117">Choose **Threat Management** \> **Policy**.</span></span> 
    
4. <span data-ttu-id="73f11-118">[**ポリシー** ] ページで、[**スパム対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="73f11-118">On the **Policy** page, choose **Anti-Spam**.</span></span>
    
    ![このスクリーンショットは、セキュリティ&amp; /コンプライアンスセンターの [スパム対策設定] ページにアクセスする方法を示しています。](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. <span data-ttu-id="73f11-120">[**スパム対策設定**] ページで、[**カスタム**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="73f11-120">On the **Anti-spam settings** page choose the **Custom** tab.</span></span> 
    
    ![このスクリーンショットは、セキュリティ&amp; /コンプライアンスセンターの [スパム対策設定] ページの [ユーザー設定] タブの場所を示しています。](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. <span data-ttu-id="73f11-122">必要に応じて、[**カスタム設定**] スイッチを選択して、カスタム設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="73f11-122">If necessary, choose the **Custom settings** switch to turn on custom settings.</span></span> <span data-ttu-id="73f11-123">カスタム設定スイッチが [**オフ**] に設定されている場合は、スパムフィルターポリシーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="73f11-123">If the custom settings switch is set to **Off**, you won't be able to modify spam filter policies.</span></span>
    
    ![このスクリーンショットは、カスタムのスパム対策フィルターポリシー設定をオフにした状態を示しています。](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. <span data-ttu-id="73f11-125">変更するスパムポリシーを展開し、[ポリシーの**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="73f11-125">Expand the spam policy you want to modify and then choose **Edit policy**.</span></span> <span data-ttu-id="73f11-126">たとえば、[**既定のスパムフィルターポリシー**] の横にある下矢印を選択します。</span><span class="sxs-lookup"><span data-stu-id="73f11-126">For example, choose the down arrow next to **Default spam filter policy**.</span></span> <span data-ttu-id="73f11-127">または、必要に応じて、[**ポリシーの追加**] を選択して、新しいポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="73f11-127">Or, if you want, you can create a new policy by choosing **Add a policy**.</span></span>
    
8. <span data-ttu-id="73f11-128">**[スパムと一括**アクション] を展開します。</span><span class="sxs-lookup"><span data-stu-id="73f11-128">Expand **Spam and bulk** actions.</span></span> 
    
9. <span data-ttu-id="73f11-129">安全のヒントを有効にするには、[**安全性のヒント**] の [**オン**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="73f11-129">To enable safety tips, under **Safety Tips**, check the **On** checkbox.</span></span> <span data-ttu-id="73f11-130">安全性のヒントを無効にするには、 **[オン**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="73f11-130">To disable safety tips, clear the **On** checkbox.</span></span> 
    
10. <span data-ttu-id="73f11-131">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="73f11-131">Choose **Save**.</span></span>
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a><span data-ttu-id="73f11-132">PowerShell を使用して安全性ヒントを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="73f11-132">To enable or disable safety tips by using PowerShell</span></span>
<span data-ttu-id="73f11-133"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="73f11-133"></span></span>

<span data-ttu-id="73f11-134">管理者は、Exchange Online PowerShell を使用して安全性のヒントを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="73f11-134">Admins can use Exchange Online PowerShell to enable or disable safety tips.</span></span> <span data-ttu-id="73f11-135">スパムフィルターポリシーの安全性に関するヒントを有効または無効にするには、Set-hostedcontentfilterpolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="73f11-135">Use the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips in a spam filter policy.</span></span>
  
1. <span data-ttu-id="73f11-136">Exchange Online PowerShell への接続。</span><span class="sxs-lookup"><span data-stu-id="73f11-136">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="73f11-137">詳細については、「 [Exchange Online PowerShell への接続](http://go.microsoft.com/fwlink/p/?LinkId=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73f11-137">For information, see [Connect to Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="73f11-138">Set-hostedcontentfilterpolicy コマンドレットを実行して、安全性に関するヒントを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="73f11-138">Run the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips:</span></span>
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

<span data-ttu-id="73f11-139">詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="73f11-139">Where:</span></span>
    
  -  <span data-ttu-id="73f11-140">[*ポリシー名*] は、変更するポリシーの名前です (例: **default**)。</span><span class="sxs-lookup"><span data-stu-id="73f11-140">*policy name*  is the name of the policy you want to modify, for example **default**.</span></span>
    
  -  <span data-ttu-id="73f11-141">`$true`スパムフィルターポリシーの安全性に関するヒントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="73f11-141">`$true` enables safety tips for the spam filter policy.</span></span> 
    
  -  <span data-ttu-id="73f11-142">`$false`スパムフィルターポリシーの安全性に関するヒントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="73f11-142">`$false` disables safety tips for the spam filter policy.</span></span> 
    
    <span data-ttu-id="73f11-143">たとえば、既定のスパムフィルターポリシーの安全性のヒントを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="73f11-143">For example, to disable safety tips for the default spam filter policy, run the following command:</span></span>
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

<span data-ttu-id="73f11-144">このコマンドレットの詳細については、「 [set-hostedcontentfilterpolicy](https://technet.microsoft.com/library/jj200781.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73f11-144">For more information about this cmdlet, see [Set-HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx).</span></span>
    
## <a name="still-need-help"></a><span data-ttu-id="73f11-145">さらにサポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="73f11-145">Still need help?</span></span>
<span data-ttu-id="73f11-146"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="73f11-146"></span></span>

<span data-ttu-id="73f11-147">安全のヒントを無効にしても、電子メールメッセージに表示されている場合は、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="73f11-147">If you disabled safety tips but are still seeing them in your email messages, check these things:</span></span>
  
- <span data-ttu-id="73f11-148">Web 上の Outlook の安全性に関するヒントを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="73f11-148">You can't disable safety tips for Outlook on the web.</span></span> <span data-ttu-id="73f11-149">Outlook などの別のクライアントで同じ電子メールを表示してみてください。</span><span class="sxs-lookup"><span data-stu-id="73f11-149">Try viewing the same email in another client, such as Outlook.</span></span>
    
- <span data-ttu-id="73f11-150">EOP を使用するすべてのユーザーについて、既定で安全性のヒントはオンになっています。これには、Office 365 を持つすべてのユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="73f11-150">Safety tips are on by default for every one who uses EOP, this includes everyone who has Office 365.</span></span> <span data-ttu-id="73f11-151">セーフヒントが電子メールで表示されないようにするには、このトピックで説明されているように、スパムフィルターポリシーを使用して、それらを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="73f11-151">In order to disable safety tips from showing up in email, you must disable them by using a spam filter policy as described in this topic.</span></span> <span data-ttu-id="73f11-152">ポリシーを設定したら、そのポリシーが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="73f11-152">Once you've set up the policy, ensure that it is enabled.</span></span> <span data-ttu-id="73f11-153">スパムフィルターポリシーの有効化の詳細については、「[スパムフィルターポリシーの構成](https://technet.microsoft.com/library/jj200684.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73f11-153">For information on enabling spam filter policies, see [Configure your spam filter policies](https://technet.microsoft.com/library/jj200684.aspx).</span></span>
    
<span data-ttu-id="73f11-154">スパムやフィッシングに対抗する方法については、「 [Office 365 電子メールのスパム対策保護](anti-spam-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73f11-154">For more ways to combat spam and phishing, see [Office 365 Email Anti-Spam Protection](anti-spam-protection.md).</span></span>
  

