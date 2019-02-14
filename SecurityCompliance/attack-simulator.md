---
title: Office 365 の攻撃シミュレータ
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: Office 365 グローバル管理者は、組織内で現実的な攻撃のシナリオを実行するのに攻撃のシミュレータを使用できます。これを識別し、実際の攻撃では、お客様のビジネスをヒットする前に、脆弱性のあるユーザーを検索することができます。
ms.openlocfilehash: 77de6af6546ae584e3bd25c0d1a59d9f26928f33
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995168"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="338aa-104">Office 365 の攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="338aa-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="338aa-p102">**概要**Office 365 のグローバル管理者、組織が[Office 365 の脅威のインテリジェンス](office-365-ti.md)を持つ場合は、組織内で現実的な攻撃のシナリオを実行する攻撃のシミュレータを使用できます。これを識別し、実際の攻撃で、一番下の行に影響を与える前に脆弱性のあるユーザーを検索することができます。詳細については、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="338aa-p102">**Summary** If you are an Office 365 global administrator and your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line. Read this article to learn more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="338aa-p103">2019 の 2 月に開始し、今後数か月にロールアウト、Office 365 の脅威インテリジェンスは Office 365 高度な脅威保護計画 2、あらたな脅威保護機能となりつつあります。詳細については、 [Office 365 の高度な脅威保護の計画と価格設定](https://products.office.com/exchange/advance-threat-protection)と[Office 365 高度な脅威保護サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="338aa-p103">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="338aa-110">攻撃</span><span class="sxs-lookup"><span data-stu-id="338aa-110">The Attacks</span></span>

<span data-ttu-id="338aa-111">3 種類の攻撃のシミュレーションは、現在使用できます。</span><span class="sxs-lookup"><span data-stu-id="338aa-111">Three kinds of attack simulations are currently available:</span></span>
  
- [<span data-ttu-id="338aa-112">スピアー フィッシング攻撃の名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="338aa-112">Display name spear-phishing attack</span></span>](attack-simulator.md#spearphish)
    
- [<span data-ttu-id="338aa-113">パスワード スプレー攻撃</span><span class="sxs-lookup"><span data-stu-id="338aa-113">Password-spray attack</span></span>](attack-simulator.md#passwordspray)
    
- [<span data-ttu-id="338aa-114">ブルート フォース パスワード攻撃</span><span class="sxs-lookup"><span data-stu-id="338aa-114">Brute-force password attack</span></span>](attack-simulator.md#bruteforce)
    
<span data-ttu-id="338aa-p104">正常に起動する攻撃は、攻撃のシミュレーションを実行しているアカウントの複数要素の認証を使用します。さらに、Office 365 グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="338aa-p104">For an attack to be successfully launched, you use multi-factor authentication on the account you are using to run simulated attacks. In addition, you must be an Office 365 global administrator.</span></span>
  
> [!NOTE]
> <span data-ttu-id="338aa-117">条件付きアクセスのサポートがもうすぐ完成です。</span><span class="sxs-lookup"><span data-stu-id="338aa-117">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="338aa-118">セキュリティでの攻撃のシミュレータにアクセスする&amp;コンプライアンス センターでは、**脅威の管理**を選択して\>**攻撃シミュレータ**です。</span><span class="sxs-lookup"><span data-stu-id="338aa-118">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="338aa-119">始める前にしています.</span><span class="sxs-lookup"><span data-stu-id="338aa-119">Before you begin...</span></span>

<span data-ttu-id="338aa-120">組織が攻撃のシミュレータの次の要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="338aa-120">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
      
- <span data-ttu-id="338aa-p105">組織の電子メールは、Exchange のオンラインでホストされています。(攻撃シミュレータは、オンプレミス メール サーバーの利用可能なない)。</span><span class="sxs-lookup"><span data-stu-id="338aa-p105">Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="338aa-123">Office 365 グローバル管理者であります。</span><span class="sxs-lookup"><span data-stu-id="338aa-123">You are an Office 365 global administrator</span></span>
    
- <span data-ttu-id="338aa-124">組織が[Office 365 のユーザーに対して多要素認証](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)を使用します。</span><span class="sxs-lookup"><span data-stu-id="338aa-124">Your organization is using [Multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)</span></span>
 
- <span data-ttu-id="338aa-125">組織が[Office 365 の脅威インテリジェンス](office-365-ti.md)セキュリティに表示されている攻撃のシミュレータでは、&amp;コンプライアンス センター (**脅威の管理**に移動\>**攻撃シミュレータ**)</span><span class="sxs-lookup"><span data-stu-id="338aa-125">Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span><br/><span data-ttu-id="338aa-126">![シミュレータの攻撃の脅威の管理](media/ThreatMgmt-AttackSimulator.png)</span><span class="sxs-lookup"><span data-stu-id="338aa-126">![Threat management - Attack Simulator](media/ThreatMgmt-AttackSimulator.png)</span></span>

    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="338aa-127">スピアー フィッシング攻撃の名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="338aa-127">Display name spear-phishing attack</span></span>

<span data-ttu-id="338aa-p106">フィッシングとは、広範なスイート クラス スタイル ソーシャル エンジニア リング攻撃と攻撃の一般的な用語です。この攻撃は、スピアー フィッシング詐欺、個人または組織の特定のグループの目的を絞った攻撃を重視されています。いくつかの予備調査を実行し、役員、組織内から送信されているように見える電子メール メッセージが受信者に信頼関係を生成する表示名を使用してカスタマイズされた攻撃では通常、します。</span><span class="sxs-lookup"><span data-stu-id="338aa-p106">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="338aa-p107">この攻撃では、表示名とソース アドレスを変更してから送信されたようにメッセージが表示されているを操作することに重点を置いています。スピアー フィッシング攻撃が成功した場合は、サイバー犯罪者はユーザーの資格情報へのアクセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="338aa-p107">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="338aa-133">スピアー フィッシング攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="338aa-133">To simulate a spear-phishing attack</span></span>

![電子メールの本文を作成します。](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="338aa-135">**電子メールの本文**のフィールド自体に直接リッチ HTML エディターを作成するか、HTML ソースを操作できます。</span><span class="sxs-lookup"><span data-stu-id="338aa-135">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>
  
1. <span data-ttu-id="338aa-136">[セキュリティ&amp;コンプライアンス センター](https://protection.office.com)、**脅威の管理**を選択して\>**攻撃のシミュレータ**です。</span><span class="sxs-lookup"><span data-stu-id="338aa-136">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="338aa-137">攻撃のキャンペーンのわかりやすい名前を指定するか、テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="338aa-137">Specify a meaningful campaign name for the attack or select a template.</span></span> <br/>![フィッシング スタート ページ](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="338aa-p108">対象の受信者を指定します。個人または組織内のグループを指定できます。各対象となる受信者は、Exchange オンライン メールボックスが成功するため、攻撃するために必要があります。</span><span class="sxs-lookup"><span data-stu-id="338aa-p108">Specify the target recipients. This can be individuals or groups in your organization. Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span> <br/>![受信者の選択](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="338aa-143">フィッシング詐欺メールの詳細を構成します。</span><span class="sxs-lookup"><span data-stu-id="338aa-143">Configure the Phishing email details.</span></span> <br/>![メールの詳細を構成します。](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/><span data-ttu-id="338aa-p109">HTML の書式と複雑なまたは基本的なキャンペーンが必要な。電子メールの形式は、HTML、イメージと信憑性を強化するためにテキストを挿入できます。受信側の電子メール クライアントで受信したメッセージの外観のコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="338aa-p109">The HTML formatting can be as complex or basic as your campaign needs. As the email format is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.</span></span>
    
5. <span data-ttu-id="338aa-p110">**(名)** フィールドの文字列を指定します。これは、受信側の電子メール クライアントでの**表示名**を表示するフィールドです。</span><span class="sxs-lookup"><span data-stu-id="338aa-p110">Specify text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
6. <span data-ttu-id="338aa-p111">テキストまたは **[差出人**] フィールドを指定します。これは、受信側の電子メール クライアントで送信者の電子メール アドレスとして表示するフィールドです。</span><span class="sxs-lookup"><span data-stu-id="338aa-p111">Specify text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client. </span></span><br/><span data-ttu-id="338aa-p112">組織内で既存の電子メールの名前空間を入力することができます (これにより、受信側のクライアントでは、非常に高い信頼モデルを容易にすることで解決するには実際に電子メール アドレス)、または、外部の電子メール アドレスを入力することができます。実際に存在する必要はありませんを指定した電子メール アドレスは有効な SMTP アドレス、user@domainname.extension の形式を次に説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="338aa-p112">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
7. <span data-ttu-id="338aa-p113">ドロップ ダウン セレクターを使用すると、攻撃ではコンテンツの種類を反映するフィッシング ログイン サーバーの URL を選択します。などドキュメントの配信、技術、給与などから、選択するには、いくつかのテーマが指定された Url が用意されています。これは、事実上、ユーザーを対象となるメッセージが表示されます] をクリックする URL です。</span><span class="sxs-lookup"><span data-stu-id="338aa-p113">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
8. <span data-ttu-id="338aa-p114">カスタムのランディング ・ ページの URL を指定します。これを使用して、攻撃の最後に指定した URL にユーザーをリダイレクトします。内部の意識向上トレーニングがあればなどのことをここで指定しました。</span><span class="sxs-lookup"><span data-stu-id="338aa-p114">Specify a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.</span></span>
    
9. <span data-ttu-id="338aa-p115">**[件名**] フィールドのテキストを指定します。これは、受信側の電子メール クライアント内の**サブジェクト名**として表示するフィールドです。</span><span class="sxs-lookup"><span data-stu-id="338aa-p115">Specify text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
10. <span data-ttu-id="338aa-161">ターゲットを受信する**電子メールの本文**を作成します。</span><span class="sxs-lookup"><span data-stu-id="338aa-161">Compose the **Email body** that the target will receive.</span></span> <br/><span data-ttu-id="338aa-162">`${username}`ターゲット名を電子メールの本文に挿入します。</span><span class="sxs-lookup"><span data-stu-id="338aa-162">`${username}` inserts the targets name into the Email body.</span></span> <br/><span data-ttu-id="338aa-163">`${loginserverurl}`をクリックするユーザーを対象と URL を挿入します。</span><span class="sxs-lookup"><span data-stu-id="338aa-163">`${loginserverurl}` inserts the URL we want target users to click</span></span> 
    
11. <span data-ttu-id="338aa-p116">**次へ**、**完了**攻撃を開始するを選択します。スピアー フィッシング詐欺の電子メール メッセージは、対象の受信者のメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="338aa-p116">Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="338aa-166">パスワード スプレー攻撃</span><span class="sxs-lookup"><span data-stu-id="338aa-166">Password-spray attack</span></span>

<span data-ttu-id="338aa-p117">組織に対してパスワード スプレー攻撃は通常、不正なアクターが正常にテナントからの有効なユーザーの一覧を取得された後に使用されます。使用される共通のパスワードの不正な出演者が認識しています。これは、広く使用されている攻撃では、低コストの攻撃を実行し、力ずくの方法よりも検出が困難になります。</span><span class="sxs-lookup"><span data-stu-id="338aa-p117">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant. The bad actor knows about common passwords that people use. This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="338aa-170">この攻撃は、ユーザーの大規模なターゲット ・ ベースに対して共通のパスワードを指定することに焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="338aa-170">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="338aa-171">パスワード スプレー攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="338aa-171">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="338aa-172">[セキュリティ&amp;コンプライアンス センター](https://protection.office.com)、**脅威の管理**を選択して\>**攻撃のシミュレータ**です。</span><span class="sxs-lookup"><span data-stu-id="338aa-172">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="338aa-173">攻撃のキャンペーンのわかりやすい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="338aa-173">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="338aa-p118">対象の受信者を指定します。個人または組織内のグループを指定できます。対象となる受信者は、Exchange オンライン メールボックスが成功するため、攻撃するために必要があります。</span><span class="sxs-lookup"><span data-stu-id="338aa-p118">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="338aa-p119">攻撃に使用するパスワードを指定します。しようとする可能性があります、1 つの一般的な関連するパスワードは、たとえば、 `Fall2017`。別可能性があります`Spring2018`、または`Password1`。</span><span class="sxs-lookup"><span data-stu-id="338aa-p119">Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="338aa-180">**完了**を攻撃を開始する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="338aa-180">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="338aa-181">ブルート フォース パスワード攻撃</span><span class="sxs-lookup"><span data-stu-id="338aa-181">Brute-force password attack</span></span>

<span data-ttu-id="338aa-p120">悪い俳優が正常にテナントからの主要なユーザーの一覧を取得した後、組織に対するブルート フォース パスワード攻撃が通常使用されます。この攻撃は、単一のユーザーのアカウントのパスワードの集合の中に焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="338aa-p120">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant. This attack focuses on trying a set of passwords on a single user's account.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="338aa-184">ブルート フォース パスワード攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="338aa-184">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="338aa-185">[セキュリティ&amp;コンプライアンス センター](https://protection.office.com)、**脅威の管理**を選択して\>**攻撃のシミュレータ**です。</span><span class="sxs-lookup"><span data-stu-id="338aa-185">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="338aa-186">攻撃のキャンペーンのわかりやすい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="338aa-186">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="338aa-p121">ターゲット受信者を指定します。対象となる受信者は、Exchange オンライン メールボックスが成功するため、攻撃するために必要があります。</span><span class="sxs-lookup"><span data-stu-id="338aa-p121">Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="338aa-p122">一連の攻撃に使用するパスワードを指定します。これを行うには、パスワードの一覧をテキスト (.txt) ファイルを使用できます。テキスト ファイルは、ファイル サイズが 10 MB を超えることはできません。1 行に 1 つのパスワードを使用し、最後のパスワードを一覧にした後、ハード リターンを含めることを確認します。</span><span class="sxs-lookup"><span data-stu-id="338aa-p122">Specify a set of passwords to use for the attack. To do this, you can use a text (.txt) file for your list of passwords. The text file cannot exceed 10 MB in file size. Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>
    
5. <span data-ttu-id="338aa-193">**完了**を攻撃を開始する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="338aa-193">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="338aa-194">攻撃シミュレータの新機能</span><span class="sxs-lookup"><span data-stu-id="338aa-194">New features in Attack Simulator</span></span>

<span data-ttu-id="338aa-p123">新機能は、攻撃のシミュレータに追加されています。これらは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="338aa-p123">New features are being added to Attack Simulator. These include:</span></span>
- <span data-ttu-id="338aa-p124">**レポート作成機能の詳細設定**します。攻撃シミュレーション電子メール メッセージを最も高速な (最も遅い) 時メッセージ、およびその他のリンクをクリックする最も高速な (最も遅い) の時刻などのデータを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="338aa-p124">**Advanced reporting capabilities**. You'll be able to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more.</span></span>
- <span data-ttu-id="338aa-p125">**電子メール テンプレート エディター**です。将来の攻撃のシミュレーションに使用できる再利用可能なカスタムの電子メール テンプレートを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="338aa-p125">**Email template editor**. You can create a custom, reusable email template that you can use for future attack simulations.</span></span>

<span data-ttu-id="338aa-201">開発ではどのような何がロールアウト、および何が既に起動して、 [Microsoft の 365 のロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="338aa-201">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>



