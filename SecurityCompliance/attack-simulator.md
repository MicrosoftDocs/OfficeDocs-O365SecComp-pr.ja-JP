---
title: Office 365 の攻撃シミュレータ
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: Office 365 のグローバル管理者として、攻撃シミュレータを使用して、組織内で現実的な攻撃シナリオを実行できます。これは、実際の攻撃によってビジネスに遭遇する前に、脆弱性のあるユーザーを特定して見つけるのに役立ちます。
ms.openlocfilehash: ba5658dfa9075b5779f8ca09ccad3547dbddcbb5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216277"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="b189a-104">Office 365 の攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="b189a-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="b189a-p102">**概要**office 365 のグローバル管理者であり、組織に[office 365 の脅威インテリジェンス](office-365-ti.md)がある場合は、攻撃シミュレータを使用して、組織内で現実的な攻撃シナリオを実行できます。これは、実際の攻撃が下の回線に影響を与える前に、脆弱性のあるユーザーを特定して見つけるのに役立ちます。詳細については、この記事をお読みください。</span><span class="sxs-lookup"><span data-stu-id="b189a-p102">**Summary** If you are an Office 365 global administrator and your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line. Read this article to learn more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b189a-p103">2019年2月から、次の数か月間に展開されています。 office 365 の脅威インテリジェンスは、追加の脅威保護機能を備えた office 365 Advanced threat protection プラン2になりつつあります。詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b189a-p103">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="b189a-110">攻撃</span><span class="sxs-lookup"><span data-stu-id="b189a-110">The Attacks</span></span>

<span data-ttu-id="b189a-111">現在、次の3種類の攻撃のシミュレーションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="b189a-111">Three kinds of attack simulations are currently available:</span></span>
  
- [<span data-ttu-id="b189a-112">表示名スピアー-フィッシング攻撃</span><span class="sxs-lookup"><span data-stu-id="b189a-112">Display name spear-phishing attack</span></span>](attack-simulator.md#spearphish)
    
- [<span data-ttu-id="b189a-113">パスワード-スプレー攻撃</span><span class="sxs-lookup"><span data-stu-id="b189a-113">Password-spray attack</span></span>](attack-simulator.md#passwordspray)
    
- [<span data-ttu-id="b189a-114">ブルートフォースパスワード攻撃</span><span class="sxs-lookup"><span data-stu-id="b189a-114">Brute-force password attack</span></span>](attack-simulator.md#bruteforce)
    
<span data-ttu-id="b189a-p104">攻撃が正常に開始されるようにするには、シミュレートされた攻撃を実行するために使用しているアカウントで多要素認証を使用します。さらに、Office 365 の全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b189a-p104">For an attack to be successfully launched, you use multi-factor authentication on the account you are using to run simulated attacks. In addition, you must be an Office 365 global administrator.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b189a-117">条件付きアクセスのサポートは近日に予定されています。</span><span class="sxs-lookup"><span data-stu-id="b189a-117">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="b189a-118">アタックシミュレータにアクセスするには、 &amp;セキュリティ/コンプライアンスセンターで、[ **Threat management** \> **アタックシミュレータ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b189a-118">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="b189a-119">開始する前に</span><span class="sxs-lookup"><span data-stu-id="b189a-119">Before you begin...</span></span>

<span data-ttu-id="b189a-120">自分と組織が、次のアタックシミュレータの要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b189a-120">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
      
- <span data-ttu-id="b189a-p105">組織の電子メールは Exchange Online でホストされています。(アタックシミュレータは、オンプレミスの電子メールサーバーでは使用できません)。</span><span class="sxs-lookup"><span data-stu-id="b189a-p105">Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="b189a-123">Office 365 の全体管理者である</span><span class="sxs-lookup"><span data-stu-id="b189a-123">You are an Office 365 global administrator</span></span>
    
- <span data-ttu-id="b189a-124">組織が[Office 365 ユーザーに多要素認証](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)を使用している</span><span class="sxs-lookup"><span data-stu-id="b189a-124">Your organization is using [Multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)</span></span>
 
- <span data-ttu-id="b189a-125">組織に[Office 365 の脅威インテリジェンス](office-365-ti.md)があり、セキュリティ&amp;コンプライアンスセンターにアタックシミュレータが表示されています (**脅威管理** \>の**アタックシミュレータ**に移動)。</span><span class="sxs-lookup"><span data-stu-id="b189a-125">Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span><br/><span data-ttu-id="b189a-126">![脅威管理-アタックシミュレータ](media/ThreatMgmt-AttackSimulator.png)</span><span class="sxs-lookup"><span data-stu-id="b189a-126">![Threat management - Attack Simulator](media/ThreatMgmt-AttackSimulator.png)</span></span>

    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="b189a-127">表示名スピアー-フィッシング攻撃</span><span class="sxs-lookup"><span data-stu-id="b189a-127">Display name spear-phishing attack</span></span>

<span data-ttu-id="b189a-p106">フィッシングとは、ソーシャルエンジニアリングスタイルの攻撃として分類された広範な攻撃の一般的な用語です。この攻撃は、スピアーフィッシングに重点を置いており、特定の個人または組織のグループを対象とした、より標的とされた攻撃に重点を置いています。通常、一部の偵察を実行し、組織内の役員からのメールメッセージなど、受信者の信頼を生成する表示名を使用して、カスタマイズされた攻撃を行います。</span><span class="sxs-lookup"><span data-stu-id="b189a-p106">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="b189a-p107">この攻撃は、表示名と送信元アドレスを変更することによって、メッセージの発信元の表示者を操作することに重点を置いています。スピアーフィッシング攻撃が成功すると、cybercriminals はユーザーの資格情報にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="b189a-p107">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="b189a-133">スピアーフィッシング攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="b189a-133">To simulate a spear-phishing attack</span></span>

![電子メール本文の作成](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="b189a-135">リッチ html エディターは、**電子メール本文**フィールド自体で直接作成することも、html ソースで操作することもできます。</span><span class="sxs-lookup"><span data-stu-id="b189a-135">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>
  
1. <span data-ttu-id="b189a-136">[セキュリティ&amp; /コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** \>の**アタックシミュレータ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b189a-136">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="b189a-137">攻撃に対して適切なキャンペーン名を指定するか、テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="b189a-137">Specify a meaningful campaign name for the attack or select a template.</span></span> <br/>![フィッシング開始ページ](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="b189a-p108">対象の受信者を指定します。これは、組織内の個人またはグループにすることができます。攻撃を成功させるには、各対象となる受信者に Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b189a-p108">Specify the target recipients. This can be individuals or groups in your organization. Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span> <br/>![受信者の選択](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="b189a-143">フィッシング電子メールの詳細を構成します。</span><span class="sxs-lookup"><span data-stu-id="b189a-143">Configure the Phishing email details.</span></span> <br/>![電子メールの詳細を構成する](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/><span data-ttu-id="b189a-p109">HTML 形式は、キャンペーンのニーズに合わせて複雑な書式にすることも、基本的なものにすることもできます。電子メール形式は HTML であるため、画像とテキストを挿入して believability を強化できます。受信したメッセージが受信側の電子メールクライアントでどのように表示されるかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="b189a-p109">The HTML formatting can be as complex or basic as your campaign needs. As the email format is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.</span></span>
    
5. <span data-ttu-id="b189a-p110">[**差出人 (名前)** ] フィールドにテキストを指定します。これは、受信側の電子メールクライアントの**表示名**に表示されるフィールドです。</span><span class="sxs-lookup"><span data-stu-id="b189a-p110">Specify text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
6. <span data-ttu-id="b189a-p111">text または**From**フィールドを指定します。これは、受信側の電子メールクライアントの送信者の電子メールアドレスとして表示されるフィールドです。</span><span class="sxs-lookup"><span data-stu-id="b189a-p111">Specify text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client. </span></span><br/><span data-ttu-id="b189a-p112">組織内に既存の電子メール名前空間を入力できます (これにより、受信側クライアントで電子メールアドレスが実際に解決されるようになり、非常に高い信頼モデルを使用できるようになります)。または、外部電子メールアドレスを入力することができます。指定した電子メールアドレスは実際に存在する必要はありませんが、有効な SMTP アドレスの形式 (user @ domainname など) の形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b189a-p112">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
7. <span data-ttu-id="b189a-p113">ドロップダウンセレクターを使用して、攻撃の対象となるコンテンツの種類を反映するフィッシングのログインサーバーの URL を選択します。文書の配信、技術、給与など、さまざまなテーマを選択できるようにするための url が用意されています。これは事実上、対象ユーザーがクリックするよう求められる URL です。</span><span class="sxs-lookup"><span data-stu-id="b189a-p113">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
8. <span data-ttu-id="b189a-p114">カスタムのランディングページの URL を指定します。これを使用すると、成功した攻撃の終了時に指定した URL にユーザーがリダイレクトされます。たとえば、内部の認識トレーニングがある場合は、ここで指定できます。</span><span class="sxs-lookup"><span data-stu-id="b189a-p114">Specify a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.</span></span>
    
9. <span data-ttu-id="b189a-p115">[**件名**] フィールドのテキストを指定します。これは、受信側の電子メールクライアントで**サブジェクト名**として表示されるフィールドです。</span><span class="sxs-lookup"><span data-stu-id="b189a-p115">Specify text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
10. <span data-ttu-id="b189a-161">ターゲットが受け取る**電子メール本文**を作成します。</span><span class="sxs-lookup"><span data-stu-id="b189a-161">Compose the **Email body** that the target will receive.</span></span> <br/><span data-ttu-id="b189a-162">`${username}`ターゲット名を電子メール本文に挿入します。</span><span class="sxs-lookup"><span data-stu-id="b189a-162">`${username}` inserts the targets name into the Email body.</span></span> <br/><span data-ttu-id="b189a-163">`${loginserverurl}`ターゲットユーザーがクリックする URL を挿入します。</span><span class="sxs-lookup"><span data-stu-id="b189a-163">`${loginserverurl}` inserts the URL we want target users to click</span></span> 
    
11. <span data-ttu-id="b189a-p116">[**次へ**] を選択し、[**完了**] を選択して、攻撃を開始します。スピアーフィッシングの電子メールメッセージは、移動先の受信者のメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="b189a-p116">Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="b189a-166">パスワード-スプレー攻撃</span><span class="sxs-lookup"><span data-stu-id="b189a-166">Password-spray attack</span></span>

<span data-ttu-id="b189a-p117">組織に対するパスワードスプレー攻撃は、通常、誤ったアクターがテナントから有効なユーザーの一覧を正常に取得した後に使用されます。誤ったアクターは、ユーザーが使用する共通のパスワードを知っています。これは、実行される安価な攻撃であり、ブルートフォースアプローチよりも検出が困難なため、広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="b189a-p117">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant. The bad actor knows about common passwords that people use. This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="b189a-170">この攻撃は、ユーザーの大規模なターゲットベースに対して共通のパスワードを指定することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="b189a-170">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="b189a-171">パスワードスプレー攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="b189a-171">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="b189a-172">[セキュリティ&amp; /コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** \>の**アタックシミュレータ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b189a-172">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="b189a-173">攻撃に対して適切なキャンペーン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b189a-173">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="b189a-p118">対象の受信者を指定します。これは、組織内の個人またはグループにすることができます。攻撃を成功させるには、対象の受信者が Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b189a-p118">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="b189a-p119">攻撃に使用するパスワードを指定します。たとえば、よく使用される1つの関連パスワードと`Fall2017`して、を試してみることができます。別の方法`Spring2018`とし`Password1`て、またはの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b189a-p119">Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="b189a-180">[**完了**] を選択して、攻撃を開始します。</span><span class="sxs-lookup"><span data-stu-id="b189a-180">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="b189a-181">ブルートフォースパスワード攻撃</span><span class="sxs-lookup"><span data-stu-id="b189a-181">Brute-force password attack</span></span>

<span data-ttu-id="b189a-p120">通常、組織に対するブルートフォースパスワード攻撃は、誤ったアクターがテナントからキーユーザーの一覧を正常に取得した後に使用されます。この攻撃は、1人のユーザーのアカウントで一連のパスワードを試行することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="b189a-p120">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant. This attack focuses on trying a set of passwords on a single user's account.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="b189a-184">ブルートフォースパスワード攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="b189a-184">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="b189a-185">[セキュリティ&amp; /コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** \>の**アタックシミュレータ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b189a-185">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="b189a-186">攻撃に対して適切なキャンペーン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b189a-186">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="b189a-p121">ターゲットの受信者を指定します。攻撃を成功させるには、対象の受信者が Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b189a-p121">Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="b189a-p122">攻撃に使用するパスワードのセットを指定します。これを行うには、パスワードの一覧にテキスト (.txt) ファイルを使用します。このテキストファイルは、ファイルサイズが 10 MB を超えることはできません。1行に1つのパスワードを使用し、リスト内の最後のパスワードの後にハードリターンを含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="b189a-p122">Specify a set of passwords to use for the attack. To do this, you can use a text (.txt) file for your list of passwords. The text file cannot exceed 10 MB in file size. Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>
    
5. <span data-ttu-id="b189a-193">[**完了**] を選択して、攻撃を開始します。</span><span class="sxs-lookup"><span data-stu-id="b189a-193">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="b189a-194">アタックシミュレータの新機能</span><span class="sxs-lookup"><span data-stu-id="b189a-194">New features in Attack Simulator</span></span>

<span data-ttu-id="b189a-p123">アタックシミュレータに新機能が追加されています。次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="b189a-p123">New features are being added to Attack Simulator. These include:</span></span>
- <span data-ttu-id="b189a-p124">**高度なレポート機能**。高速 (または最も低速) のデータを表示して、攻撃のシミュレーションの電子メールメッセージを開くことができます。また、メッセージ内のリンクをクリックすると、最も速く、または遅くなります。</span><span class="sxs-lookup"><span data-stu-id="b189a-p124">**Advanced reporting capabilities**. You'll be able to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more.</span></span>
- <span data-ttu-id="b189a-p125">**電子メールテンプレートエディター**。今後の攻撃のシミュレーションに使用できる、再利用可能なカスタム電子メールテンプレートを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="b189a-p125">**Email template editor**. You can create a custom, reusable email template that you can use for future attack simulations.</span></span>

<span data-ttu-id="b189a-201">[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を参照して、開発中のもの、ロールアウトされているもの、および既に起動しているものを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b189a-201">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>



