---
title: Office 365 の攻撃シミュレータ
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/19/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: 攻撃のシミュレータを使用して実行することができますサイバー攻撃の約 3 つのさまざまな種類について説明します。
ms.openlocfilehash: 364144c0b2f8109c67fb262ce879414088380ebe
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531884"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="50d30-103">Office 365 の攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="50d30-103">Attack Simulator in Office 365</span></span>

<span data-ttu-id="50d30-p101">攻撃シミュレータ ( [Office 365 の脅威インテリジェンス](office-365-ti.md)に含まれている) で、組織のセキュリティ チームのメンバーである場合を実行できます現実的な攻撃のシナリオ、組織内。これを識別し、実際の攻撃で、一番下の行に影響を与える前に脆弱性のあるユーザーを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="50d30-p101">With Attack Simulator (included in [Office 365 Threat Intelligence](office-365-ti.md)), if you are a member of your organization's security team, you can run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="50d30-106">攻撃</span><span class="sxs-lookup"><span data-stu-id="50d30-106">The Attacks</span></span>

<span data-ttu-id="50d30-107">プレビュー リリースでは、3 種類の攻撃のシミュレーションを実行することがあります。</span><span class="sxs-lookup"><span data-stu-id="50d30-107">At preview release we offer three kinds of attack simulations that you can run:</span></span>
  
- [<span data-ttu-id="50d30-108">スピアー フィッシング攻撃の名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="50d30-108">Display name spear-phishing attack</span></span>](attack-simulator.md#spearphish)
    
- [<span data-ttu-id="50d30-109">パスワード スプレー攻撃</span><span class="sxs-lookup"><span data-stu-id="50d30-109">Password-spray attack</span></span>](attack-simulator.md#passwordspray)
    
- [<span data-ttu-id="50d30-110">ブルート フォース パスワード攻撃</span><span class="sxs-lookup"><span data-stu-id="50d30-110">Brute-force password attack</span></span>](attack-simulator.md#bruteforce)
    
<span data-ttu-id="50d30-111">正常に起動する攻撃は、攻撃を実行しているログオン アカウントは多要素認証を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d30-111">For an attack to be successfully launched, the account that is running the attack and logged on must use multi-factor authentication.</span></span>
  
> [!NOTE]
> <span data-ttu-id="50d30-112">条件付きアクセスのサポートがもうすぐ完成です。</span><span class="sxs-lookup"><span data-stu-id="50d30-112">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="50d30-113">セキュリティでの攻撃のシミュレータにアクセスする&amp;コンプライアンス センターでは、**脅威の管理**を選択して\>**攻撃シミュレータ**です。</span><span class="sxs-lookup"><span data-stu-id="50d30-113">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="50d30-114">始める前にしています.</span><span class="sxs-lookup"><span data-stu-id="50d30-114">Before you begin...</span></span>

<span data-ttu-id="50d30-115">組織が攻撃のシミュレータの次の要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="50d30-115">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
  
- <span data-ttu-id="50d30-116">組織が[Office 365 の脅威インテリジェンス](office-365-ti.md)セキュリティに表示されている攻撃のシミュレータでは、&amp;コンプライアンス センター (**脅威の管理**に移動\>**攻撃シミュレータ**)</span><span class="sxs-lookup"><span data-stu-id="50d30-116">Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span>
    
- <span data-ttu-id="50d30-p102">組織の電子メールは、Exchange のオンラインでホストされています。(攻撃シミュレータは、オンプレミス メール サーバーの利用可能なない)。</span><span class="sxs-lookup"><span data-stu-id="50d30-p102">Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="50d30-119">Office 365 グローバル管理者であります。</span><span class="sxs-lookup"><span data-stu-id="50d30-119">You are an Office 365 global administrator</span></span>
    
- <span data-ttu-id="50d30-120">組織が[Office 365 のユーザーに対して多要素認証](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)を使用します。</span><span class="sxs-lookup"><span data-stu-id="50d30-120">Your organization is using [Multi-factor authentication for Office 365 users](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)</span></span>
    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="50d30-121">スピアー フィッシング攻撃の名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="50d30-121">Display name spear-phishing attack</span></span>

<span data-ttu-id="50d30-p103">フィッシングとは、広範なスイート クラス スタイル ソーシャル エンジニア リング攻撃と攻撃の一般的な用語です。この攻撃は、スピアー フィッシング詐欺、個人または組織の特定のグループの目的を絞った攻撃を重視されています。いくつかの予備調査を実行し、役員、組織内から送信されているように見える電子メール メッセージが受信者に信頼関係を生成する表示名を使用してカスタマイズされた攻撃では通常、します。</span><span class="sxs-lookup"><span data-stu-id="50d30-p103">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="50d30-p104">この攻撃では、表示名とソース アドレスを変更してから送信されたようにメッセージが表示されているを操作することに重点を置いています。スピアー フィッシング攻撃が成功した場合は、サイバー犯罪者はユーザーの資格情報へのアクセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="50d30-p104">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="50d30-127">スピアー フィッシング攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="50d30-127">To simulate a spear-phishing attack</span></span>

![電子メールの本文を作成します。](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="50d30-p105">**電子メールの本文**のフィールド自体に直接リッチ HTML エディターを作成するか、HTML ソースを操作できます。HTML に含めることの 2 つの重要なフィールドです。</span><span class="sxs-lookup"><span data-stu-id="50d30-p105">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source. There are two important fields for inclusion in the HTML:</span></span> 
  
1. <span data-ttu-id="50d30-131">セキュリティで&amp;コンプライアンス センターでは、**脅威の管理**を選択して\>**攻撃のシミュレータ**です。</span><span class="sxs-lookup"><span data-stu-id="50d30-131">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="50d30-132">攻撃のキャンペーンのわかりやすい名前を指定するか、テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="50d30-132">Specify a meaningful campaign name for the attack or select a template.</span></span>
    
    ![フィッシング スタート ページ](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="50d30-p106">対象の受信者を指定します。個人または組織内のグループを指定できます。対象となる受信者は、Exchange オンライン メールボックスが成功するため、攻撃するために必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d30-p106">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
    ![受信者の選択](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="50d30-138">フィッシング詐欺メールの詳細を構成します。</span><span class="sxs-lookup"><span data-stu-id="50d30-138">Configure the Phishing email details.</span></span>
    
    ![メールの詳細を構成します。](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)
  
    <span data-ttu-id="50d30-p107">HTML の書式と複雑なまたは基本的なキャンペーンが必要な。これは、HTML、イメージと信憑性を強化するためにテキストを挿入できます。受信側の電子メール クライアントで受信したメッセージの外観のコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="50d30-p107">The HTML formatting can be as complex or basic as your campaign needs. As it is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.</span></span>
    
1. <span data-ttu-id="50d30-p108">**(名) の**フィールドのテキストを入力します。これは、受信側の電子メール クライアントでの**表示名**を表示するフィールドです。</span><span class="sxs-lookup"><span data-stu-id="50d30-p108">Enter text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
2. <span data-ttu-id="50d30-p109">テキストまたは **[差出人**] フィールドを入力します。これは、受信側の電子メール クライアントで送信者の電子メール アドレスとして表示するフィールドです。</span><span class="sxs-lookup"><span data-stu-id="50d30-p109">Enter text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="50d30-p110">組織内で既存の電子メールの名前空間を入力することができます (これにより、受信側のクライアントでは、非常に高い信頼モデルを容易にすることで解決するには実際に電子メール アドレス)、または、外部の電子メール アドレスを入力することができます。実際に存在する必要はありませんを指定した電子メール アドレスは有効な SMTP アドレス、user@domainname.extension の形式を次に説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d30-p110">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
3. <span data-ttu-id="50d30-p111">ドロップ ダウン セレクターを使用すると、攻撃ではコンテンツの種類を反映するフィッシング ログイン サーバーの URL を選択します。などドキュメントの配信、技術、給与などから、選択するには、いくつかのテーマが指定された Url が用意されています。これは、事実上、ユーザーを対象となるメッセージが表示されます] をクリックする URL です。</span><span class="sxs-lookup"><span data-stu-id="50d30-p111">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
4. <span data-ttu-id="50d30-p112">カスタムのランディング ・ ページの URL を入力します。これを使用して、攻撃の最後に指定した URL にユーザーをリダイレクトします。内部の意識向上トレーニングがあればなどのことをここで指定しました。</span><span class="sxs-lookup"><span data-stu-id="50d30-p112">Enter a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.</span></span>
    
5. <span data-ttu-id="50d30-p113">**[件名**] フィールドのテキストを入力します。これは、受信側の電子メール クライアント内の**サブジェクト名**として表示するフィールドです。</span><span class="sxs-lookup"><span data-stu-id="50d30-p113">Enter text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
5. <span data-ttu-id="50d30-156">ターゲットを受信する**電子メールの本文**を作成します。</span><span class="sxs-lookup"><span data-stu-id="50d30-156">Compose the **Email body** that the target will receive.</span></span> 
  
 <span data-ttu-id="50d30-157">**${ユーザー名}** は、電子メールの本文にターゲット名を挿入します。</span><span class="sxs-lookup"><span data-stu-id="50d30-157">**${username}** inserts the targets name into the Email body</span></span> 
  
 <span data-ttu-id="50d30-158">**${loginserverurl}** ] をクリックするユーザーを対象と URL を挿入します。</span><span class="sxs-lookup"><span data-stu-id="50d30-158">**${loginserverurl}** inserts the URL we want target users to click</span></span> 
    
6. <span data-ttu-id="50d30-p114">**次へ**、**完了**攻撃を開始するを選択します。スピアー フィッシング詐欺の電子メール メッセージは、対象の受信者のメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="50d30-p114">Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="50d30-161">パスワード スプレー攻撃</span><span class="sxs-lookup"><span data-stu-id="50d30-161">Password-spray attack</span></span>

<span data-ttu-id="50d30-p115">組織に対してパスワード スプレー攻撃は通常、不正なアクターが正常に有効なユーザーが使用する一般的なパスワードの知識を利用して、テナントの一覧を列挙した後に使用されます。低コストの攻撃を実行するには、広く使用されているし、力ずくの方法よりも検出が困難になりますが。</span><span class="sxs-lookup"><span data-stu-id="50d30-p115">A password spray attack against an organization is typically used after a bad actor has successfully enumerated a list of valid users from the tenant, utilizing their knowledge of common passwords used. It is utilized widely as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="50d30-164">この攻撃は、ユーザーの大規模なターゲット ・ ベースに対して共通のパスワードを指定することに焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="50d30-164">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="50d30-165">パスワード スプレー攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="50d30-165">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="50d30-166">セキュリティで&amp;コンプライアンス センターでは、**脅威の管理**を選択して\>**攻撃のシミュレータ**です。</span><span class="sxs-lookup"><span data-stu-id="50d30-166">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="50d30-167">攻撃のキャンペーンのわかりやすい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="50d30-167">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="50d30-p116">対象の受信者を指定します。個人または組織内のグループを指定できます。対象となる受信者は、Exchange オンライン メールボックスが成功するため、攻撃するために必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d30-p116">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="50d30-p117">攻撃に使用するパスワードを指定します。しようとする可能性があります、1 つの一般的な関連するパスワードは、たとえば、 `Fall2017`。別可能性があります`Spring2018`、または`Password1`。</span><span class="sxs-lookup"><span data-stu-id="50d30-p117">Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="50d30-174">**完了**を攻撃を開始する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="50d30-174">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="50d30-175">ブルート フォース パスワード攻撃</span><span class="sxs-lookup"><span data-stu-id="50d30-175">Brute-force password attack</span></span>

<span data-ttu-id="50d30-p118">組織に対するブルート フォース パスワード攻撃は通常、不正なアクターが正常にテナントからの主要なユーザーの一覧を列挙した後に使用されます。この攻撃は、1 人のユーザーに対するパスワードのセットを指定することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="50d30-p118">A brute-force password attack against an organization is typically used after a bad actor has successfully enumerated a list of key users from the tenant. This attack focuses on letting you specify a set of passwords against a single user.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="50d30-178">ブルート フォース パスワード攻撃をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="50d30-178">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="50d30-179">セキュリティで&amp;コンプライアンス センターでは、**脅威の管理**を選択して\>**攻撃のシミュレータ**です。</span><span class="sxs-lookup"><span data-stu-id="50d30-179">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="50d30-180">攻撃のキャンペーンのわかりやすい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="50d30-180">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="50d30-p119">ターゲット受信者を指定します。対象となる受信者は、Exchange オンライン メールボックスが成功するため、攻撃するために必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d30-p119">Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="50d30-p120">一連の攻撃に使用するパスワードを指定します。しようとする可能性があります、1 つの一般的な関連するパスワードは、たとえば、 `Fall2017`。別可能性があります`Spring2018`、または`Password1`。</span><span class="sxs-lookup"><span data-stu-id="50d30-p120">Specify a set of passwords to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="50d30-186">**完了**を攻撃を開始する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="50d30-186">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="50d30-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="50d30-187">Related topics</span></span>

[<span data-ttu-id="50d30-188">Office 365 脅威インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="50d30-188">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  

