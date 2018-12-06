---
title: Office 365 で安全性のヒントを有効または無効にする
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
description: Office 365 および EOP の管理者に電子メール メッセージで安全性のヒントを無効にする方法を指示します。
ms.openlocfilehash: 8e5d8bf1d2f831b5d74ca3accd8b434519bfeaab
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180857"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a><span data-ttu-id="a6689-103">Office 365 で安全性のヒントを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="a6689-103">Enable or disable safety tips in Office 365</span></span>

<span data-ttu-id="a6689-p101">Exchange オンライン保護 (EOP) を追加、またはその電子メール メッセージにスタンプ、安全性のヒントです。メッセージがマークされている場合迷惑メールとして、Office 365 で、メッセージに、フィッシング詐欺などで不審なものが含まれている場合、または外部の画像がある場合、送信者を確認するこれらの安全性に関するヒントを確認するメッセージから安全で、簡単かつ視覚的方法で受信者を提供します。ブロックされています。Office 365 と EOP スタンドアロンの管理者は、迷惑メール ポリシー設定を有効にするか、Outlook およびその他のデスクトップの電子メール クライアントで電子メールに表示されているから安全性のヒントを無効にするを編集できます。</span><span class="sxs-lookup"><span data-stu-id="a6689-p101">Exchange Online Protection (EOP) adds, or stamps, a safety tip to email messages that it delivers. These safety tips provide recipients with a quick, visual way to determine if a message is from a safe, verified sender, if the message has been marked as spam by Office 365, if the message contains something suspicious such as a phishing scam, or if external images have been blocked. Office 365 and EOP-standalone admins can edit a spam policy setting to enable or disable safety tips from being displayed in email in Outlook and other desktop email clients.</span></span> 
  
<span data-ttu-id="a6689-p102">Office 365 は、既定では、組織の安全性のヒントを有効にし、スパムやフィッシング攻撃の戦闘を支援するを有効にしておくことをお勧めします。Web 上の Outlook の安全性のヒントを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a6689-p102">Office 365 enables safety tips by default for your organization and we recommend that you leave them enabled to help combat spam and phishing attacks. You can't disable safety tips for Outlook on the web.</span></span>
  
<span data-ttu-id="a6689-109">例を参照してくださいと、安全性のヒントに表示される情報の詳細についてを参照してください[Office 365 で電子メール メッセージでの安全性のヒントです](safety-tips-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a6689-109">To see examples and to learn about the information displayed in safety tips, see [Safety tips in email messages in Office 365.](safety-tips-in-office-365.md)</span></span>
  
<span data-ttu-id="a6689-110">このトピックの内容</span><span class="sxs-lookup"><span data-stu-id="a6689-110">In this topic:</span></span>
  
- [<span data-ttu-id="a6689-111">有効にするか、Office 365 のセキュリティを使用して安全性のヒントを無効にする&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="a6689-111">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [<span data-ttu-id="a6689-112">有効にするまたは PowerShell を使用して安全性のヒントを無効にするには</span><span class="sxs-lookup"><span data-stu-id="a6689-112">To enable or disable safety tips by using PowerShell</span></span>](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="a6689-113">有効にするか、Office 365 のセキュリティを使用して安全性のヒントを無効にする&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="a6689-113">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>
<span data-ttu-id="a6689-114"><a name="SandCCsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="a6689-114"></span></span>

1. <span data-ttu-id="a6689-115">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="a6689-115">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="a6689-116">職場または学校アカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="a6689-116">Sign in to Office 365 with your work or school account.</span></span>
    
3. <span data-ttu-id="a6689-117">**脅威の管理**を選択して\>**ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="a6689-117">Choose **Threat Management** \> **Policy**.</span></span> 
    
4. <span data-ttu-id="a6689-118">[**ポリシー** ] ページでは、**スパム対策**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6689-118">On the **Policy** page, choose **Anti-Spam**.</span></span>
    
    ![このスクリーン ショットは、スパム対策設定] ページで、セキュリティを取得する方法を示しています&amp;コンプライアンス センターです。](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. <span data-ttu-id="a6689-120">**スパム対策の設定**] ページで、[**ユーザー設定**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a6689-120">On the **Anti-spam settings** page choose the **Custom** tab.</span></span> 
    
    ![このスクリーン ショットのスパム対策設定] ページで、セキュリティ上のユーザー設定] タブの位置を示しています&amp;コンプライアンス センターです。](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. <span data-ttu-id="a6689-p103">必要に応じて、カスタム設定を有効にするのには**カスタム設定**スイッチを選択します。カスタム設定のスイッチは、**オフ**に設定されている場合迷惑メール フィルターのポリシーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6689-p103">If necessary, choose the **Custom settings** switch to turn on custom settings. If the custom settings switch is set to **Off**, you won't be able to modify spam filter policies.</span></span>
    
    ![このスクリーン ショットは、ポリシーの設定がオフになっている独自のスパム対策フィルターを示しています。](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. <span data-ttu-id="a6689-p104">迷惑メール ポリシーを変更し、[**ポリシーの編集**] をクリックするを展開します。たとえば、**ポリシーのフィルターを適用する既定の迷惑メール**の横にある下向きの矢印を選択します。または、**ポリシーの追加**] をクリックして新しいポリシーを作成する場合は、します。</span><span class="sxs-lookup"><span data-stu-id="a6689-p104">Expand the spam policy you want to modify and then choose **Edit policy**. For example, choose the down arrow next to **Default spam filter policy**. Or, if you want, you can create a new policy by choosing **Add a policy**.</span></span>
    
8. <span data-ttu-id="a6689-128">**スパムおよび一括**操作を展開します。</span><span class="sxs-lookup"><span data-stu-id="a6689-128">Expand **Spam and bulk** actions.</span></span> 
    
9. <span data-ttu-id="a6689-p105">**安全性のヒント**は、下の安全性に関するヒントを有効にするには、チェック ボックス**に**します。安全性のヒントを無効にするには、 **[** 保存] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a6689-p105">To enable safety tips, under **Safety Tips**, check the **On** checkbox. To disable safety tips, clear the **On** checkbox.</span></span> 
    
10. <span data-ttu-id="a6689-131">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a6689-131">Choose **Save**.</span></span>
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a><span data-ttu-id="a6689-132">有効にするまたは PowerShell を使用して安全性のヒントを無効にするには</span><span class="sxs-lookup"><span data-stu-id="a6689-132">To enable or disable safety tips by using PowerShell</span></span>
<span data-ttu-id="a6689-133"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="a6689-133"></span></span>

<span data-ttu-id="a6689-p106">管理者は、有効または安全性のヒントを無効にする、Exchange オンライン PowerShell を使用できます。セット HostedContentFilterPolicy コマンドレットを使用して、有効または迷惑メール フィルターのポリシーで安全性のヒントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="a6689-p106">Admins can use Exchange Online PowerShell to enable or disable safety tips. Use the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips in a spam filter policy.</span></span>
  
1. <span data-ttu-id="a6689-p107">オンライン PowerShell を交換するために接続します。については、 [Exchange オンライン PowerShell への接続](http://go.microsoft.com/fwlink/p/?LinkId=396554)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6689-p107">Connect to Exchange Online PowerShell. For information, see [Connect to Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="a6689-138">有効または安全性のヒントを無効にするセット HostedContentFilterPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6689-138">Run the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips:</span></span>
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

<span data-ttu-id="a6689-139">詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a6689-139">Where:</span></span>
    
  -  <span data-ttu-id="a6689-140">*ポリシー名*はなどの**既定値**を変更するポリシーの名前です。</span><span class="sxs-lookup"><span data-stu-id="a6689-140">*policy name*  is the name of the policy you want to modify, for example **default**.</span></span>
    
  -  <span data-ttu-id="a6689-141">`$true`スパム フィルター ポリシーの安全性のヒントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a6689-141">`$true` enables safety tips for the spam filter policy.</span></span> 
    
  -  <span data-ttu-id="a6689-142">`$false`スパム フィルター ポリシーの安全性のヒントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="a6689-142">`$false` disables safety tips for the spam filter policy.</span></span> 
    
    <span data-ttu-id="a6689-143">たとえば、迷惑メール フィルターの既定のポリシーの安全性のヒントを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6689-143">For example, to disable safety tips for the default spam filter policy, run the following command:</span></span>
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

<span data-ttu-id="a6689-144">このコマンドレットの詳細については、[一連の HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6689-144">For more information about this cmdlet, see [Set-HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx).</span></span>
    
## <a name="still-need-help"></a><span data-ttu-id="a6689-145">さらにサポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="a6689-145">Still need help?</span></span>
<span data-ttu-id="a6689-146"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="a6689-146"></span></span>

<span data-ttu-id="a6689-147">安全性のヒントを無効には、電子メール メッセージに表示する場合は、これらのことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6689-147">If you disabled safety tips but are still seeing them in your email messages, check these things:</span></span>
  
- <span data-ttu-id="a6689-p108">Web 上の Outlook の安全性のヒントを無効にすることはできません。Outlook などの別のクライアントに同じ電子メールを表示してみてください。</span><span class="sxs-lookup"><span data-stu-id="a6689-p108">You can't disable safety tips for Outlook on the web. Try viewing the same email in another client, such as Outlook.</span></span>
    
- <span data-ttu-id="a6689-p109">安全性のヒントは既定ではすべて 1 つの EOP を使用するには、すべての Office 365 ユーザーが含まれます。電子メールに表示されない安全性のヒントを無効にするのにはこのトピックで説明したように迷惑メール フィルターのポリシーを使用して無効にする必要があります。ポリシーを設定したら後、は、それが有効になっているを確認します。スパム フィルター ポリシーを有効にする方法の詳細については、[スパム フィルター ポリシーの構成](https://technet.microsoft.com/library/jj200684.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6689-p109">Safety tips are on by default for every one who uses EOP, this includes everyone who has Office 365. In order to disable safety tips from showing up in email, you must disable them by using a spam filter policy as described in this topic. Once you've set up the policy, ensure that it is enabled. For information on enabling spam filter policies, see [Configure your spam filter policies](https://technet.microsoft.com/library/jj200684.aspx).</span></span>
    
<span data-ttu-id="a6689-154">スパムやフィッシング詐欺に対抗するためのより多くの方法は、 [Office 365 の電子メール スパム対策の保護](anti-spam-protection.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6689-154">For more ways to combat spam and phishing, see [Office 365 Email Anti-Spam Protection](anti-spam-protection.md).</span></span>
  

