---
title: Office 365 の攻撃シミュレータ
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: Office 365 のグローバル管理者として、攻撃シミュレータを使用して、組織内で現実的な攻撃シナリオを実行できます。 これは、実際の攻撃によってビジネスに遭遇する前に、脆弱性のあるユーザーを特定して見つけるのに役立ちます。
ms.openlocfilehash: e72350fb8ca3ef8d7ed0218934097d2383f5ad53
ms.sourcegitcommit: ff370e93b792204547694139ef99bc0848304570
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "36852779"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="dced0-104">Office 365 の攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="dced0-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="dced0-105">**概要**Office 365 の全体管理者またはセキュリティ管理者で、組織に Office 365 Advanced Threat Protection プラン2があり、[脅威の調査および応答機能](office-365-ti.md)が含まれている場合は、アタックシミュレータを使用して実行できます。組織内の現実的な攻撃シナリオ。</span><span class="sxs-lookup"><span data-stu-id="dced0-105">**Summary** If you are an Office 365 global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="dced0-106">これは、実際の攻撃が下の回線に影響を与える前に、脆弱性のあるユーザーを特定して見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dced0-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="dced0-107">詳細については、この記事をお読みください。</span><span class="sxs-lookup"><span data-stu-id="dced0-107">Read this article to learn more.</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="dced0-108">攻撃</span><span class="sxs-lookup"><span data-stu-id="dced0-108">The Attacks</span></span>

<span data-ttu-id="dced0-109">現在、次の3種類の攻撃のシミュレーションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="dced0-109">Three kinds of attack simulations are currently available:</span></span>
  
- [<span data-ttu-id="dced0-110">表示名スピアー-フィッシング攻撃</span><span class="sxs-lookup"><span data-stu-id="dced0-110">Display name spear-phishing attack</span></span>](#display-name-spear-phishing-attack)

- [<span data-ttu-id="dced0-111">パスワード-スプレー攻撃</span><span class="sxs-lookup"><span data-stu-id="dced0-111">Password-spray attack</span></span>](#password-spray-attack)

- [<span data-ttu-id="dced0-112">ブルートフォースパスワード攻撃</span><span class="sxs-lookup"><span data-stu-id="dced0-112">Brute-force password attack</span></span>](#brute-force-password-attack)
    
<span data-ttu-id="dced0-113">攻撃が正常に開始されるようにするには、シミュレートされた攻撃の実行に使用しているアカウントが多要素認証を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dced0-113">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="dced0-114">さらに、Office 365 の全体管理者またはセキュリティ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dced0-114">In addition, you must be an Office 365 global administrator or a security administrator.</span></span> <span data-ttu-id="dced0-115">役割とアクセス許可の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dced0-115">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>
    
<span data-ttu-id="dced0-116">アタックシミュレータにアクセスするには、 &amp;セキュリティ/コンプライアンスセンターで、[ **Threat management** \> **アタックシミュレータ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dced0-116">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="dced0-117">開始する前に</span><span class="sxs-lookup"><span data-stu-id="dced0-117">Before you begin...</span></span>

<span data-ttu-id="dced0-118">自分と組織が、次のアタックシミュレータの要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dced0-118">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
      
- <span data-ttu-id="dced0-119">組織の電子メールは Exchange Online でホストされています。</span><span class="sxs-lookup"><span data-stu-id="dced0-119">Your organization's email is hosted in Exchange Online.</span></span> <span data-ttu-id="dced0-120">(アタックシミュレータは、オンプレミスの電子メールサーバーでは使用できません)。</span><span class="sxs-lookup"><span data-stu-id="dced0-120">(Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="dced0-121">Office 365 の全体管理者またはセキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="dced0-121">You are an Office 365 global administrator or security administrator</span></span>
    
- <span data-ttu-id="dced0-122">少なくとも1人の Office 365 グローバル管理者アカウントおよびセキュリティ管理者がアタックシミュレータを使用する場合は、[多要素認証/条件付きアクセス](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="dced0-122">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide) is turned on, for at least the Office 365 global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="dced0-123">(理想的には、組織内のすべてのユーザーに対して多要素認証/条件付きアクセスが有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="dced0-123">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>
 
- <span data-ttu-id="dced0-124">組織に[Office 365 Advanced Threat Protection プラン 2](office-365-atp.md)があり、セキュリティ&amp;コンプライアンスセンターでアタックシミュレータが表示されている (**脅威管理** \>の**アタックシミュレータ**に移動)</span><span class="sxs-lookup"><span data-stu-id="dced0-124">Your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-atp.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span>

    ![脅威管理-アタックシミュレータ](media/ThreatMgmt-AttackSimulator.png)

## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="dced0-126">表示名スピアー-フィッシング攻撃</span><span class="sxs-lookup"><span data-stu-id="dced0-126">Display name spear-phishing attack</span></span>

<span data-ttu-id="dced0-127">フィッシングとは、ソーシャルエンジニアリングスタイルの攻撃として分類された広範な攻撃の一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="dced0-127">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="dced0-128">この攻撃は、スピアーフィッシングに重点を置いており、特定の個人または組織のグループを対象とした、より標的とされた攻撃に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="dced0-128">This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="dced0-129">通常、一部の偵察を実行し、組織内の役員からのメールメッセージなど、受信者の信頼を生成する表示名を使用して、カスタマイズされた攻撃を行います。</span><span class="sxs-lookup"><span data-stu-id="dced0-129">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="dced0-130">この攻撃は、表示名と送信元アドレスを変更することによって、メッセージの発信元の表示者を操作することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="dced0-130">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address.</span></span> <span data-ttu-id="dced0-131">スピアーフィッシング攻撃が成功すると、cyberattackers はユーザーの資格情報にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="dced0-131">When spear-phishing attacks are successful, cyberattackers gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="dced0-132">スピアーフィッシング攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="dced0-132">To simulate a spear-phishing attack</span></span>

![電子メール本文の作成](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="dced0-134">リッチ HTML エディターは、**電子メール本文**フィールド自体で直接作成することも、html ソースで操作することもできます。</span><span class="sxs-lookup"><span data-stu-id="dced0-134">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>
  
1. <span data-ttu-id="dced0-135">[セキュリティ&amp; /コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** \>の**アタックシミュレータ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dced0-135">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="dced0-136">攻撃に対して適切なキャンペーン名を指定するか、テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="dced0-136">Specify a meaningful campaign name for the attack or select a template.</span></span> 

    ![フィッシング開始ページ](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="dced0-138">対象の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="dced0-138">Specify the target recipients.</span></span> <span data-ttu-id="dced0-139">これは、組織内の個人またはグループにすることができます。</span><span class="sxs-lookup"><span data-stu-id="dced0-139">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="dced0-140">攻撃を成功させるには、各対象となる受信者に Exchange Online メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="dced0-140">Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span> 

    ![受信者の選択](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="dced0-142">フィッシング電子メールの詳細を構成します。</span><span class="sxs-lookup"><span data-stu-id="dced0-142">Configure the Phishing email details.</span></span> 

    ![電子メールの詳細を構成する](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)
    
    <span data-ttu-id="dced0-144">HTML 形式は、キャンペーンのニーズに合わせて複雑な書式にすることも、基本的なものにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dced0-144">The HTML formatting can be as complex or basic as your campaign needs.</span></span> <span data-ttu-id="dced0-145">電子メール形式は HTML であるため、画像とテキストを挿入して believability を強化できます。</span><span class="sxs-lookup"><span data-stu-id="dced0-145">As the email format is HTML, you can insert images and text to enhance believability.</span></span> <span data-ttu-id="dced0-146">受信したメッセージが受信側の電子メールクライアントでどのように表示されるかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="dced0-146">You have control on what the received message will look like in the receiving email client.</span></span>
    
5. <span data-ttu-id="dced0-147">[**差出人 (名前)** ] フィールドにテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="dced0-147">Specify text for the **From (Name)** field.</span></span> <span data-ttu-id="dced0-148">これは、受信側の電子メールクライアントの**表示名**に表示されるフィールドです。</span><span class="sxs-lookup"><span data-stu-id="dced0-148">This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
6. <span data-ttu-id="dced0-149">Text または**From**フィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="dced0-149">Specify text or the **From** field.</span></span> <span data-ttu-id="dced0-150">これは、受信側の電子メールクライアントの送信者の電子メールアドレスとして表示されるフィールドです。</span><span class="sxs-lookup"><span data-stu-id="dced0-150">This is the field that shows as the email address of the sender in the receiving email client.</span></span>

    <span data-ttu-id="dced0-151">組織内に既存の電子メール名前空間を入力できます (これにより、受信側クライアントで電子メールアドレスが実際に解決されるようになり、非常に高い信頼モデルを使用できるようになります)。または、外部電子メールアドレスを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="dced0-151">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address.</span></span> <span data-ttu-id="dced0-152">指定した電子メールアドレスは、実際に存在する必要はありませんが、などの有効な SMTP アドレスの形式に従う`user@domainname.extension`必要があります。</span><span class="sxs-lookup"><span data-stu-id="dced0-152">The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as `user@domainname.extension`.</span></span> 
  
7. <span data-ttu-id="dced0-153">ドロップダウンセレクターを使用して、攻撃の対象となるコンテンツの種類を反映するフィッシングのログインサーバーの URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="dced0-153">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack.</span></span> <span data-ttu-id="dced0-154">文書の配信、技術、給与など、さまざまなテーマを選択できるようにするための Url が用意されています。これは事実上、対象ユーザーがクリックするよう求められる URL です。</span><span class="sxs-lookup"><span data-stu-id="dced0-154">Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
8. <span data-ttu-id="dced0-155">カスタムのランディングページの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="dced0-155">Specify a custom landing page URL.</span></span> <span data-ttu-id="dced0-156">これを使用すると、成功した攻撃の終了時に指定した URL にユーザーがリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="dced0-156">Using this will redirect users to a URL you specify at the end of a successful attack.</span></span> <span data-ttu-id="dced0-157">たとえば、内部の認識トレーニングがある場合は、ここで指定できます。</span><span class="sxs-lookup"><span data-stu-id="dced0-157">If you have internal awareness training, for example, you can specify that here.</span></span>
    
9. <span data-ttu-id="dced0-158">[**件名**] フィールドのテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="dced0-158">Specify text for the **Subject** field.</span></span> <span data-ttu-id="dced0-159">これは、受信側の電子メールクライアントで**サブジェクト名**として表示されるフィールドです。</span><span class="sxs-lookup"><span data-stu-id="dced0-159">This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
10. <span data-ttu-id="dced0-160">ターゲットが受け取る**電子メール本文**を作成します。</span><span class="sxs-lookup"><span data-stu-id="dced0-160">Compose the **Email body** that the target will receive.</span></span> 

    <span data-ttu-id="dced0-161">`${username}`ターゲット名を電子メール本文に挿入します。</span><span class="sxs-lookup"><span data-stu-id="dced0-161">`${username}` inserts the targets name into the Email body.</span></span> 

    <span data-ttu-id="dced0-162">`${loginserverurl}`ターゲットユーザーがクリックする URL を挿入します。</span><span class="sxs-lookup"><span data-stu-id="dced0-162">`${loginserverurl}` inserts the URL we want target users to click</span></span> 
    
11. <span data-ttu-id="dced0-163">[**次へ**] を選択し、[**完了**] を選択して、攻撃を開始します。</span><span class="sxs-lookup"><span data-stu-id="dced0-163">Choose **Next,** then **Finish** to launch the attack.</span></span> <span data-ttu-id="dced0-164">スピアーフィッシングの電子メールメッセージは、移動先の受信者のメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="dced0-164">The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="dced0-165">パスワード-スプレー攻撃</span><span class="sxs-lookup"><span data-stu-id="dced0-165">Password-spray attack</span></span>

<span data-ttu-id="dced0-166">組織に対するパスワードスプレー攻撃は、通常、誤ったアクターがテナントから有効なユーザーの一覧を正常に取得した後に使用されます。</span><span class="sxs-lookup"><span data-stu-id="dced0-166">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant.</span></span> <span data-ttu-id="dced0-167">誤ったアクターは、ユーザーが使用する共通のパスワードを知っています。</span><span class="sxs-lookup"><span data-stu-id="dced0-167">The bad actor knows about common passwords that people use.</span></span> <span data-ttu-id="dced0-168">これは、実行される安価な攻撃であり、ブルートフォースアプローチよりも検出が困難なため、広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="dced0-168">This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="dced0-169">この攻撃は、ユーザーの大規模なターゲットベースに対して共通のパスワードを指定することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="dced0-169">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="dced0-170">パスワードスプレー攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="dced0-170">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="dced0-171">[セキュリティ&amp; /コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** \>の**アタックシミュレータ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dced0-171">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="dced0-172">攻撃に対して適切なキャンペーン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="dced0-172">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="dced0-173">対象の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="dced0-173">Specify the target recipients.</span></span> <span data-ttu-id="dced0-174">これは、組織内の個人またはグループにすることができます。</span><span class="sxs-lookup"><span data-stu-id="dced0-174">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="dced0-175">攻撃を成功させるには、対象の受信者が Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dced0-175">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="dced0-176">攻撃に使用するパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="dced0-176">Specify a password to use for the attack.</span></span> <span data-ttu-id="dced0-177">たとえば、よく使用される1つの関連パスワードと`Summer2019`して、を試してみることができます。</span><span class="sxs-lookup"><span data-stu-id="dced0-177">For example, one common, relevant password you could try is `Summer2019`.</span></span> <span data-ttu-id="dced0-178">別の方法`Fall2019`とし`Password1`て、またはの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="dced0-178">Another might be `Fall2019`, or `Password1`.</span></span>
    
5. <span data-ttu-id="dced0-179">[**完了**] を選択して、攻撃を開始します。</span><span class="sxs-lookup"><span data-stu-id="dced0-179">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="dced0-180">ブルートフォースパスワード攻撃</span><span class="sxs-lookup"><span data-stu-id="dced0-180">Brute-force password attack</span></span>

<span data-ttu-id="dced0-181">通常、組織に対するブルートフォースパスワード攻撃は、誤ったアクターがテナントからキーユーザーの一覧を正常に取得した後に使用されます。</span><span class="sxs-lookup"><span data-stu-id="dced0-181">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant.</span></span> <span data-ttu-id="dced0-182">この攻撃は、1人のユーザーのアカウントで一連のパスワードを試行することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="dced0-182">This attack focuses on trying a set of passwords on a single user's account.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="dced0-183">ブルートフォースパスワード攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="dced0-183">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="dced0-184">[セキュリティ&amp; /コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** \>の**アタックシミュレータ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dced0-184">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="dced0-185">攻撃に対して適切なキャンペーン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="dced0-185">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="dced0-186">ターゲットの受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="dced0-186">Specify the target recipient.</span></span> <span data-ttu-id="dced0-187">攻撃を成功させるには、対象の受信者が Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dced0-187">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="dced0-188">攻撃に使用するパスワードのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="dced0-188">Specify a set of passwords to use for the attack.</span></span> <span data-ttu-id="dced0-189">これを行うには、パスワードの一覧にテキスト (.txt) ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="dced0-189">To do this, you can use a text (.txt) file for your list of passwords.</span></span> <span data-ttu-id="dced0-190">このテキストファイルは、ファイルサイズが 10 MB を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="dced0-190">The text file cannot exceed 10 MB in file size.</span></span> <span data-ttu-id="dced0-191">1行に1つのパスワードを使用し、リスト内の最後のパスワードの後にハードリターンを含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="dced0-191">Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>
    
5. <span data-ttu-id="dced0-192">[**完了**] を選択して、攻撃を開始します。</span><span class="sxs-lookup"><span data-stu-id="dced0-192">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="dced0-193">アタックシミュレータの新機能</span><span class="sxs-lookup"><span data-stu-id="dced0-193">New features in Attack Simulator</span></span>

<span data-ttu-id="dced0-194">新しい機能が最近、アタックシミュレータに追加されました。</span><span class="sxs-lookup"><span data-stu-id="dced0-194">New features have recently been added to Attack Simulator.</span></span> <span data-ttu-id="dced0-195">これらには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dced0-195">These include:</span></span>

- <span data-ttu-id="dced0-196">高度なレポート機能。</span><span class="sxs-lookup"><span data-stu-id="dced0-196">Advanced reporting capabilities.</span></span> <span data-ttu-id="dced0-197">アタックシミュレーションの電子メールメッセージを開くための最も高速 (または最も遅く) 時間などのデータを表示する機能。メッセージのリンクをクリックすると、その時間が短縮され、視覚エフェクトが向上します。</span><span class="sxs-lookup"><span data-stu-id="dced0-197">The ability to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more visualizations.</span></span>

- <span data-ttu-id="dced0-198">電子メールテンプレートエディター。</span><span class="sxs-lookup"><span data-stu-id="dced0-198">Email template editor.</span></span> <span data-ttu-id="dced0-199">再利用可能なカスタム電子メールテンプレートを作成する機能。これは、今後の攻撃シミュレーションに使用できます。</span><span class="sxs-lookup"><span data-stu-id="dced0-199">The ability to create a custom, reusable email template's that you can use for future attack simulations.</span></span>

- <span data-ttu-id="dced0-200">CSV 受信者のインポート。</span><span class="sxs-lookup"><span data-stu-id="dced0-200">CSV Recipient Import.</span></span> <span data-ttu-id="dced0-201">Csv ファイルを使用して、アドレス帳ピッカーを使用する代わりに、対象となる受信者リストをインポートする機能。</span><span class="sxs-lookup"><span data-stu-id="dced0-201">The ability to use a .csv file to import your target recipient list instead of using the address book picker.</span></span>

<span data-ttu-id="dced0-202">より多くの新機能が、今後のアタックシミュレータに公開されています。</span><span class="sxs-lookup"><span data-stu-id="dced0-202">More new features are coming soon to Attack Simulator.</span></span> <span data-ttu-id="dced0-203">これらには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dced0-203">These include:</span></span>

- <span data-ttu-id="dced0-204">添付ファイルのペイロードのフィッシングシミュレーション。</span><span class="sxs-lookup"><span data-stu-id="dced0-204">Attachment payload phishing simulation.</span></span> <span data-ttu-id="dced0-205">URL の代わりに、添付ファイルをフィッシングシミュレーションのペイロードとして使用する機能。</span><span class="sxs-lookup"><span data-stu-id="dced0-205">The ability to use an attachment as the payload for phishing simulation in place of a URL.</span></span>

<span data-ttu-id="dced0-206">[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を参照して、開発中のもの、ロールアウトされているもの、および既に起動しているものを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dced0-206">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>

## <a name="see-also"></a><span data-ttu-id="dced0-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="dced0-207">See also</span></span>

[<span data-ttu-id="dced0-208">Office 365 Advanced Threat Protection サービスの説明</span><span class="sxs-lookup"><span data-stu-id="dced0-208">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[<span data-ttu-id="dced0-209">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="dced0-209">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)



