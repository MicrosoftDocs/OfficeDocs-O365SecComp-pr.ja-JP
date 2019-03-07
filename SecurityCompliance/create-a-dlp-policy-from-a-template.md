---
title: テンプレートからの DLP ポリシーの作成
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 'DLP ポリシーの使用を開始する最も簡単で最も一般的な方法は、Office 365 に含まれるいずれかのテンプレートを使用することです。 '
ms.openlocfilehash: 7e07c79df8ff9b65e2b213b180c607008007550e
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455259"
---
# <a name="create-a-dlp-policy-from-a-template"></a><span data-ttu-id="ff93d-103">テンプレートから DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ff93d-103">Create a DLP policy from a template</span></span>

<span data-ttu-id="ff93d-p101">DLP ポリシーの使用を開始するにあたり、最も簡単かつ一般的な方法は、Office 365 に含まれているいずれかのテンプレートを使用することです。それらのテンプレートをそのまま使用することもできますし、組織の特定のコンプライアンス要件に合うようにルールをカスタマイズすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p101">The easiest, most common way to get started with DLP policies is to use one of the templates included in Office 365. You can use one of these templates as is, or customize the rules to meet your organization's specific compliance requirements.</span></span>
  
<span data-ttu-id="ff93d-p102">Office 365 には 40 を超えるすぐに使用可能なテンプレートが備わっていて、広範囲におよぶ一般的な規定やビジネス ポリシーのニーズに対応できます。たとえば、以下を対象とした DLP ポリシー テンプレートがあります。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p102">Office 365 includes over 40 ready-to-use templates that can help you meet a wide range of common regulatory and business policy needs. For example, there are DLP policy templates for:</span></span>
  
- <span data-ttu-id="ff93d-108">グラム リーチ ブライリー法 (GLBA)</span><span class="sxs-lookup"><span data-stu-id="ff93d-108">Gramm-Leach-Bliley Act (GLBA)</span></span>
    
- <span data-ttu-id="ff93d-109">クレジットカード業界のデータ セキュリティ スタンダード (PCI-DSS)</span><span class="sxs-lookup"><span data-stu-id="ff93d-109">Payment Card Industry Data Security Standard (PCI-DSS)</span></span>
    
- <span data-ttu-id="ff93d-110">米国の個人を特定できる情報 (米国 PII)</span><span class="sxs-lookup"><span data-stu-id="ff93d-110">United States Personally Identifiable Information (U.S. PII)</span></span>
    
- <span data-ttu-id="ff93d-111">米国の医療保険法 (HIPAA)</span><span class="sxs-lookup"><span data-stu-id="ff93d-111">United States Health Insurance Act (HIPAA)</span></span>
    
<span data-ttu-id="ff93d-p103">既存のルールのいずれかを変更したり新しいルールを追加したりして、テンプレートを細かく調整することができます。たとえば、新しい種類の機密情報をルールに追加する、トリガーしにくくするまたはトリガーしやすくするためにルール内のカウントを変更する、業務上の正当な理由を提供することでルール内のアクションをユーザーが無効にできるようにする、または通知およびインシデント レポートの送信先を変更することができます。DLP ポリシー テンプレートは、多くの一般的なコンプライアンス シナリオにとって柔軟性の高い開始点です。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p103">You can fine tune a template by modifying any of the existing rules or adding new ones. For example, you can add new types of sensitive information to a rule, modify the counts in a rule to make it harder or easier to trigger, allow people to override the actions in a rule by providing a business justification, or change who notifications and incident reports are sent to. A DLP policy template is a flexible starting point for many common compliance scenarios.</span></span>
  
<span data-ttu-id="ff93d-115">カスタム テンプレートを選択することもできます。カスタム テンプレートには既定のルールがなく、組織の特定のコンプライアンス要件を満たすようにゼロから DLP ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ff93d-115">You can also choose the Custom template, which has no default rules, and configure your DLP policy from scratch, to meet the specific compliance requirements for your organization.</span></span>
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a><span data-ttu-id="ff93d-116">例: すべての OneDrive for Business サイトにある機密情報を識別し、組織外のユーザー用によるアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="ff93d-116">Example: Identify sensitive information across all OneDrive for Business sites and restrict access for people outside your organization</span></span>

<span data-ttu-id="ff93d-p104">OneDrive for Business アカウントを使用すると、組織内のユーザーがドキュメントに関して共同作業を行ったり共有したりすることが簡単になります。ただし、コンプライアンス担当者は一般に、OneDrive for Business アカウントに格納されている機密情報が組織外のユーザーと誤って共有される事態について心配します。DLP ポリシーは、このリスクの軽減に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p104">OneDrive for Business accounts make it easy for people across your organization to collaborate and share documents. But a common concern for compliance officers is that sensitive information stored in OneDrive for Business accounts may be inadvertently shared with people outside your organization. A DLP policy can help mitigate this risk.</span></span>
  
<span data-ttu-id="ff93d-p105">この例では、個人納税者識別番号 (ITIN)、社会保障番号、および米国のパスポート番号が含まれている米国の個人情報データを識別する DLP ポリシーを作成します。テンプレートを使用して開始して、組織のコンプライアンス要件を満たすようにテンプレートを変更します。具体的には、以下の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p105">In this example, you'll create a DLP policy that identifies U.S. PII data, which includes Individual Taxpayer Identification Numbers (ITIN), Social Security Numbers, and U.S. passport numbers. You'll get started by using a template, and then you'll modify the template to meet your organization's compliance requirements—specifically, you'll:</span></span>
  
- <span data-ttu-id="ff93d-122">2 種類の機密情報 (米国の銀行口座番号および米国の運転免許番号) を追加し、DLP ポリシーがさらに多くの機密データを保護できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ff93d-122">Add a couple of types of sensitive information—U.S. bank account numbers and U.S. driver's license numbers—so that the DLP policy protects even more of your sensitive data.</span></span>
    
- <span data-ttu-id="ff93d-123">ポリシーの機密性をさらに高めて、機密情報が一度でも発生したら、外部ユーザーのアクセスを制限するようにします。</span><span class="sxs-lookup"><span data-stu-id="ff93d-123">Make the policy more sensitive, so that a single occurrence of sensitive information is enough to restrict access for external users.</span></span>
    
- <span data-ttu-id="ff93d-p106">業務上の理由を提供したり、誤検知のレポートを作成したりすることによって、ユーザーがアクションを上書きできるようにします。これにより、DLP ポリシーが作業の邪魔になり組織内のユーザーを妨害することがないようになります。その場合、ユーザーは機密情報を共有するための正当な業務上の理由を提供します。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p106">Allow users to override the actions by providing a business justification or reporting a false positive. This way, your DLP policy won't prevent people in your organization from getting their work done, provided they have a valid business reason for sharing the sensitive information.</span></span>
    
### <a name="create-a-dlp-policy-from-a-template"></a><span data-ttu-id="ff93d-126">テンプレートから DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ff93d-126">Create a DLP policy from a template</span></span>

1. <span data-ttu-id="ff93d-127">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="ff93d-127">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="ff93d-p107">職場または学校のアカウントを使用して、Office 365 にサインインします。これで、Office 365 セキュリティ/コンプライアンス センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p107">Sign in to Office 365 using your work or school account. You're now in the Office 365 Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="ff93d-130">セキュリティ/コンプライアンス センターの左側のナビゲーションで、**[データ損失防止]** \> **[ポリシー]** \> **[+ ポリシーの作成]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ff93d-130">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    ![[ポリシーの作成] ボタン](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="ff93d-132">必要な種類の機密情報を保護する DLP ポリシー テンプレートを選び、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff93d-132">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="ff93d-133">この例では、**[プライバシー]** \> **[米国の個人情報 (PII) データ]** と選択します。このテンプレートには、保護対象の機密情報のほとんどの種類が既に含まれており、後ほど 2 つだけ追加します。</span><span class="sxs-lookup"><span data-stu-id="ff93d-133">In this example, you'll select **Privacy** \> **U.S. Personally Identifiable Information ‎(PII)‎ Data** because it already includes most of the types of sensitive information that you want to protect—you'll add a couple later.</span></span> 
    
    <span data-ttu-id="ff93d-134">テンプレートを選択するときに、右側の説明を読んで、テンプレートが保護する機密情報の種類を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-134">When you select a template, you can read the description on the right to learn what types of sensitive information the template protects.</span></span>
    
    ![DLP ポリシー テンプレートを選択するためのページ](media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. <span data-ttu-id="ff93d-136">ポリシーの名前を設定し、**[次へ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-136">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="ff93d-137">DLP ポリシーで保護する場所を選ぶには、次のいずれかを行います。</span><span class="sxs-lookup"><span data-stu-id="ff93d-137">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
  - <span data-ttu-id="ff93d-138">**[Office 365 のすべての場所]** \> **[次へ]** と選びます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-138">Choose **All locations in Office 365** \> **Next**.</span></span>
    
  - <span data-ttu-id="ff93d-p108">**[自分で特定の場所を選択する]** \> **[次へ]** と選びます。この例では、これを選びます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p108">Choose **Let me choose specific locations** \> **Next**. For this example, choose this.</span></span>
    
    <span data-ttu-id="ff93d-141">すべての Exchange メールやすべての OneDrive アカウントなど、特定の場所全体を含めたり除外したりするには、その場所の **[状態]** をオンまたはオフに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-141">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
    <span data-ttu-id="ff93d-p109">特定の SharePoint サイトまたは OneDrive for Business アカウントだけを含めるには、**[状態]** をオンに切り替えた後、**[含める]** の下のリンクをクリックして、特定のサイトまたはアカウントを選びます。ポリシーをサイトに適用すると、そのポリシーに構成されたルールがそのサイトのすべてのサブサイトに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p109">To include only specific SharePoint sites or OneDrive for Business accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts. When you apply a policy to a site, the rules configured in that policy are automatically applied to all subsites of that site.</span></span> 
    
    ![DLP ポリシーを適用できる場所のオプション](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    <span data-ttu-id="ff93d-145">この例では、すべての OneDrive for Business アカウントに保存されている機密情報を保護するために、**Exchange メール**と **SharePoint サイト**の両方の **[状態]** をオフにし、**OneDrive アカウント**の **[状態]** はそのままにします。</span><span class="sxs-lookup"><span data-stu-id="ff93d-145">In this example, to protect sensitive information stored in all OneDrive for Business accounts, turn off the **Status** for both **Exchange email** and **SharePoint sites**, and leave the **Status** on for **OneDrive accounts**.</span></span>
    
7. <span data-ttu-id="ff93d-146">**[詳細設定を使う]** \> **[次へ]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-146">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="ff93d-p110">DLP ポリシー テンプレートには、条件付きの定義済みルールと、特定の種類の機密情報を検出して適用するアクションが含まれています。既存のルールのいずれかを編集、削除、またはオフにするか、新しいルールを追加できます。完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p110">A DLP policy template contains predefined rules with conditions and actions that detect and act upon specific types of sensitive information. You can edit, delete, or turn off any of the existing rules, or add new ones. When done, click **Next**.</span></span>
    
    ![米国 PII ポリシー テンプレートで展開されたルール](media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    <span data-ttu-id="ff93d-151">この例の場合、米国 PII データ テンプレートには、次の 2 つの定義済みルールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ff93d-151">In this example, the U.S. PII Data template includes two predefined rules:</span></span>
    
  - <span data-ttu-id="ff93d-p111">**少量のコンテンツを検出 - 米国の PII**: このルールは、3 種類の機密情報 (ITIN、SSN、米国のパスポート番号) の発生回数がそれぞれ 1 回から 10 回のファイルを検索し、ファイルが組織外の人と共有されている場所を検索します。検出されると、ルールに従って、プライマリ サイト コレクション管理者、ドキュメントの所有者、ドキュメントを最後に変更したユーザーにメール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p111">**Low volume of content detected U.S. PII** This rule looks for files containing between 1 and 10 occurrences of each of three types of sensitive information (ITIN, SSN, and U.S. passport numbers), where the files are shared with people outside the organization. If found, the rule sends an email notification to the primary site collection administrator, document owner, and person who last modified the document.</span></span> 
    
  - <span data-ttu-id="ff93d-p112">**大量のコンテンツで検出: 米国の PII**: このルールは、同じ 3 種類の機密情報の発生回数がそれぞれ 10 回を超えるファイルを検索し、ファイルが組織外の人と共有されている場所を検索します。検出されると、この場合もメール通知が送信され、さらに、ファイルへのアクセスが制限されます。OneDrive for Business アカウントのコンテンツの場合、これは、プライマリ サイト コレクション管理者、ドキュメントの所有者、ドキュメントを最後に変更したユーザーを除くすべてのユーザーについて、ドキュメントへのアクセス許可が制限されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p112">**High volume of content detected U.S. PII** This rule looks for files containing 10 or more occurrences of each of the same three sensitive information types, where the files are shared with people outside the organization. If found, this action also sends an email notification, plus it restricts access to the file. For content in a OneDrive for Business account, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> 
    
    <span data-ttu-id="ff93d-p113">組織の要件によっては、ルールが簡単にトリガーされるようにし、機密情報が一度出現するだけで外部ユーザーからのアクセスをブロックするようにできます。こうしたルールを調べた後、高カウントおよび低カウントのルールが不要で、必要となるのは、いずれかの機密情報が検出された場合にアクセスをブロックするというルール 1 つだけであることがわかる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p113">To meet your organization's specific requirements, you may want to make the rules easier to trigger, so that a single occurrence of sensitive information is enough to block access for external users. After looking at these rules, you understand that you don't need low and high count rules—you need only a single rule that blocks access if any occurrence of sensitive information is found.</span></span>
    
    <span data-ttu-id="ff93d-159">したがって、**[少量のコンテンツを検出 - 米国の PII]** という名前のルールを展開して、**[ルールの削除]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-159">So you expand the rule named **Low volume of content detected U.S. PII** \> **Delete rule**.</span></span>
    
    ![[ルールの削除] ボタン](media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. <span data-ttu-id="ff93d-p114">この例では、2 種類の機密情報 (米国の銀行口座番号と米国の運転免許証番号) を追加して、ユーザーがルールを無効にして、カウントを任意の発生回数に変更できるようにします。これは 1 つのルールを編集することですべて行えます。したがって、**[大量のコンテンツを検出 - 米国の PII]** \> **[ルールの編集]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p114">Now, in this example, you need to add two sensitive information types (U.S. bank account numbers and U.S. driver's license numbers), allow people to override a rule, and change the count to any occurrence. You can do all of this by editing one rule, so select **High volume of content detected U.S. PII** \> **Edit rule**.</span></span>
    
    ![[ルールの編集] ボタン](media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. <span data-ttu-id="ff93d-p115">機密情報の種類を追加するには、**[条件]** セクションで **[種類の追加または変更]** を選びます。次に、**[種類の追加または変更]** で、**[追加]**、**[米国の銀行口座番号]**、**[米国の運転免許番号]**、**[追加]**、**[完了]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p115">To add a sensitive information type, in the **Conditions** section \> **Add or change types**. Then, under **Add or change types** \> choose **Add** \> select **U.S. Bank Account Number** and **U.S. Driver's License Number** \> **Add** \> **Done**.</span></span>
    
    ![[種類の追加または変更] のオプション](media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![[種類の追加または変更] ウィンドウ](media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. <span data-ttu-id="ff93d-p116">カウント (ルールのトリガーに必要な機密情報のインスタンスの数) を変更するには、**[インスタンス数]** で、各種類に対して**最小**値を選び、1 を入力します。最小カウントを空にすることはできません。最大カウントは空でもかまいません。空の**最大**値は**すべて**に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p116">To change the count (the number of instances of sensitive information required to trigger the rule), under **Instance count** \> choose the **min** value for each type \> enter 1. The minimum count cannot be empty. The maximum count can be empty; an empty **max** value convert to **any**.</span></span>
    
    <span data-ttu-id="ff93d-p117">完了すると、すべての種類の機密情報の最小カウントが **1** になり、最大カウントが**すべて**になるはずです。つまり、この種類の機密情報が発生すると、この条件が満たされます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p117">When finished, the min count for all of the sensitive information types should be **1** and the max count should be **any**. In other words, any occurrence of this type of sensitive information will satisfy this condition.</span></span>
    
    ![機密情報の種類のインスタンス カウント](media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. <span data-ttu-id="ff93d-174">最終的なカスタマイズとして、ユーザーに業務上の正当な理由があるか、誤検知である場合に、DLP ポリシーがこれらのユーザーの業務の妨げにならないようにするには、ユーザー通知にブロック アクションを無効にするオプションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-174">For the final customization, you don't want your DLP policies to block people from doing their work when they have a valid business justification or encounter a false positive, so you want the user notification to include options to override the blocking action.</span></span>
    
    <span data-ttu-id="ff93d-175">**[ユーザー通知]** セクションでは、テンプレートのこのルールに対して、メール通知とポリシー ヒントが既定でオンになっていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="ff93d-175">In the **User notifications** section, you can see that email notifications and policy tips are turned on by default for this rule in the template.</span></span> 
    
    <span data-ttu-id="ff93d-p118">**[ユーザーによる上書き]** セクションでは、業務上の正当な理由に対して上書きはオンになっていますが、誤検知の報告に対しては上書きがオンになっていません。**[誤検知として報告された場合にルールを自動的に上書きします]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p118">In the **User overrides** section, you can see that overrides for a business justification are turned on, but overrides to report false positives are not. Choose **Override the rule automatically if they report it as a false positive**.</span></span>
    
    ![[ユーザー通知] セクションと [ユーザーによる上書き] セクション](media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. <span data-ttu-id="ff93d-179">ルール エディターの上部にあるこのルールの名前を既定の **[大量のコンテンツを検出 - 米国の PII]** から **[任意のコンテンツで検出: 米国の PII]** に変更します。これは、機密情報の種類が発生すればルールがトリガーされるようになったためです。</span><span class="sxs-lookup"><span data-stu-id="ff93d-179">At the top of the rule editor, change the name of this rule from the default **High volume of content detected U.S. PII** to **Any content detected with U.S. PII** because it's now triggered by any occurrence of its sensitive information types.</span></span> 
    
14. <span data-ttu-id="ff93d-180">ルール エディターの下部にある **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff93d-180">At the bottom of the rule editor \> **Save**.</span></span>
    
15. <span data-ttu-id="ff93d-181">このルールの条件とアクションを確認して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff93d-181">Review the conditions and actions for this rule \> **Next**.</span></span>
    
    <span data-ttu-id="ff93d-p119">右側のルールの **[状態]** の切り替えに注意してください。ポリシー全体をオフにすると、そのポリシーに含まれるすべてのルールもオフになります。しかしここでは、ポリシー全体をオフにすることなく、特定のルールをオフにできます。これは多数の誤検知を生成するルールを調査する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p119">On the right, notice the **Status** switch for the rule. If you turn off an entire policy, all rules contained in the policy are also turned off. However, here you can turn off a specific rule without turning off the entire policy. This can be useful when you need to investigate a rule that is generating a large number of false positives.</span></span> 
    
16. <span data-ttu-id="ff93d-186">次のページでは、以下の内容を読み、理解したうえで、ルールをオンにするか、最初にテストするかを選んで **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff93d-186">On the next page, read and understand the following, and then choose whether to turn on the rule or test it out first \> **Next**.</span></span>
    
     <span data-ttu-id="ff93d-p120">DLP ポリシーを作成する前に、段階的にロールアウトして、影響を評価して有効性をテストしてから、完全に適用することを検討してください。たとえば、ユーザーが業務を行うのに必要な数千のドキュメントへのアクセスを、新しい DLP ポリシーで意図せずブロックすることは望まないはずです。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p120">Before you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before you fully enforce them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require to get their work done.</span></span> 
    
    <span data-ttu-id="ff93d-189">大きな影響を与える可能性が高い DLP ポリシーを作成しているときは、次の順序に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ff93d-189">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
    
17. <span data-ttu-id="ff93d-p121">ポリシー ヒントなしのテスト モードで開始した後、DLP レポートを使用して影響を評価します。DLP レポートを使用すると、ポリシー一致の回数、場所、種類、および重要度を把握できます。その結果に基づいて、必要に応じてルールを細かく調整できます。テスト モードの DLP ポリシーは、組織の従業員の生産性に影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p121">Start in test mode without Policy Tips and then use the DLP reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
18. <span data-ttu-id="ff93d-p122">通知とポリシー ヒントを有効にしたテスト モードに移行し、コンプライアンス ポリシーについてのユーザーのトレーニングと、適用される予定のルールへの対応準備を開始できるようにします。この段階では、ルールをさらに適切にできるように、誤検知の報告をユーザーに要求できます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p122">Move to Test mode with notifications and Policy Tips so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span>
    
19. <span data-ttu-id="ff93d-p123">ポリシーを有効にし、ルールが適用されてコンテンツが保護されるようにします。DLP レポート、インシデント レポート、通知を引き続き監視して、結果が意図したとおりであるか確認します。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p123">Turn on the policies so that the rules are enforced and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
    ![テスト モードを使用しポリシーで有効化するオプション](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. <span data-ttu-id="ff93d-199">このポリシーの設定を確認して、**[作成]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-199">Review your settings for this policy \> choose **Create**.</span></span>
    
<span data-ttu-id="ff93d-200">DLP ポリシーを作成して有効にした後、SharePoint Online サイトや OneDrive for Business アカウントなどのコンテンツ ソースに展開すると、ポリシーによって対象コンテンツへのルールの適用が自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-200">After you create and turn on a DLP policy, it's deployed to any content sources that it includes, such as SharePoint Online sites or OneDrive for Business accounts, where the policy begins automatically enforcing its rules on that content.</span></span>
  
## <a name="view-the-status-of-a-dlp-policy"></a><span data-ttu-id="ff93d-201">DLP ポリシーの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="ff93d-201">View the status of a DLP policy</span></span>

<span data-ttu-id="ff93d-p124">セキュリティ/コンプライアンス センターの **[ポリシー]** ページの **[データ損失防止]** セクションでいつでも DLP ポリシーの状態を見ることができます。ここでは、ポリシーが正常に有効化または無効化されたかどうか、またはポリシーがテスト モードかどうかといった、重要な情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p124">At any time, you can view the status of your DLP policies on the **Policy** page in the **Data loss prevention** section of the Security &amp; Compliance Center. Here you can find important information, such as whether a policy was successfully enabled or disabled, or whether the policy is in test mode.</span></span> 
  
<span data-ttu-id="ff93d-204">以下に、さまざまな状態とその意味を示します。</span><span class="sxs-lookup"><span data-stu-id="ff93d-204">Here are the different statuses and what they mean.</span></span>
  
|<span data-ttu-id="ff93d-205">**状態**</span><span class="sxs-lookup"><span data-stu-id="ff93d-205">**Status**</span></span>|<span data-ttu-id="ff93d-206">**説明**</span><span class="sxs-lookup"><span data-stu-id="ff93d-206">**Explanation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ff93d-207">**オンにしています...**</span><span class="sxs-lookup"><span data-stu-id="ff93d-207">**Turning on…**</span></span> <br/> |<span data-ttu-id="ff93d-p125">ポリシーは、それに含まれるコンテンツ ソースに展開されています。ポリシーは、すべてのソースでまだ適用されていません。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p125">The policy is being deployed to the content sources that it includes. The policy is not yet enforced on all sources.</span></span>  <br/> |
|<span data-ttu-id="ff93d-210">**テスト中、通知あり**</span><span class="sxs-lookup"><span data-stu-id="ff93d-210">**Testing, with notifications**</span></span> <br/> |<span data-ttu-id="ff93d-p126">ポリシーはテスト モードです。ルール内のアクションは適用されませんが、ポリシーの一致は収集され、DLP レポートを使用して表示することができます。ポリシーの一致についての通知は、指定した受信者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p126">The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are sent to the specified recipients.</span></span>  <br/> |
|<span data-ttu-id="ff93d-214">**テスト中、通知なし**</span><span class="sxs-lookup"><span data-stu-id="ff93d-214">**Testing, without notifications**</span></span> <br/> |<span data-ttu-id="ff93d-p127">ポリシーはテスト モードです。ルール内のアクションは適用されませんが、ポリシーの一致は収集され、DLP レポートを使用して表示することができます。ポリシーの一致についての通知は、指定した受信者に送信されません。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p127">The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are not sent to the specified recipients.</span></span>  <br/> |
|<span data-ttu-id="ff93d-218">**オン**</span><span class="sxs-lookup"><span data-stu-id="ff93d-218">**On**</span></span> <br/> |<span data-ttu-id="ff93d-p128">ポリシーはアクティブであり、適用されています。ポリシーは、すべてのコンテンツ ソースに正常に展開されました。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p128">The policy is active and enforced. The policy was successfully deployed to all its content sources.</span></span>  <br/> |
|<span data-ttu-id="ff93d-221">**オフにしています...**</span><span class="sxs-lookup"><span data-stu-id="ff93d-221">**Turning off…**</span></span> <br/> |<span data-ttu-id="ff93d-p129">ポリシーは、それに含まれるコンテンツ ソースから削除されています。一部のソースでは、ポリシーがまだアクティブで適用されている可能性があります。ポリシーをオフにするには、最高 45 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p129">The policy is being removed from the content sources that it includes. The policy may still be active and enforced on some sources. Turning off a policy may take up to 45 minutes.</span></span>  <br/> |
|<span data-ttu-id="ff93d-225">**オフ**</span><span class="sxs-lookup"><span data-stu-id="ff93d-225">**Off**</span></span> <br/> |<span data-ttu-id="ff93d-p130">ポリシーはアクティブではなく、適用されていません。ポリシーの設定 (ソース、キーワード、期間など) は保存されています。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p130">The policy is not active and not enforced. The settings for the policy (sources, keywords, duration, etc) are saved.</span></span>  <br/> |
|<span data-ttu-id="ff93d-228">**削除しています...**</span><span class="sxs-lookup"><span data-stu-id="ff93d-228">**Deleting…**</span></span> <br/> |<span data-ttu-id="ff93d-p131">ポリシーは削除処理中です。ポリシーはアクティブではなく、適用されていません。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p131">The policy is in the process of being deleted. The policy is not active and not enforced.</span></span>  <br/> |
   
## <a name="turn-off-a-dlp-policy"></a><span data-ttu-id="ff93d-231">DLP ポリシーをオフにする</span><span class="sxs-lookup"><span data-stu-id="ff93d-231">Turn off a DLP policy</span></span>

<span data-ttu-id="ff93d-p132">いつでも DLP ポリシーを編集してオフにすることができます。ポリシーをオフにすると、ポリシーのすべてのルールが無効になります。</span><span class="sxs-lookup"><span data-stu-id="ff93d-p132">You can edit or turn off a DLP policy at any time. Turning off a policy disables all of the rules in the policy.</span></span>
  
<span data-ttu-id="ff93d-234">DLP ポリシーを編集またはオフにするには、**[ポリシー]** ページでポリシーを選び、**[ポリシーの編集]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-234">To edit or turn off a DLP policy, on the **Policy** page \> select the policy \> **Edit policy**.</span></span>
  
![[ポリシーの編集] ボタン](media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
<span data-ttu-id="ff93d-236">さらに、前述したように、ポリシーを編集してから、そのルールの **[状態]** をオフに切り替えることで、各ルールを個別にオフにできます。</span><span class="sxs-lookup"><span data-stu-id="ff93d-236">In addition, you can turn off each rule individually by editing the policy and then toggling off the **Status** of that rule, as described above.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="ff93d-237">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ff93d-237">More information</span></span>

- [<span data-ttu-id="ff93d-238">データ損失防止ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="ff93d-238">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="ff93d-239">通知を送信して、DLP ポリシーのポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="ff93d-239">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="ff93d-240">FCI または他のプロパティを含むドキュメントを保護するために DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ff93d-240">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="ff93d-241">DLP ポリシー テンプレートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="ff93d-241">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="ff93d-242">機密情報の種類インベントリ</span><span class="sxs-lookup"><span data-stu-id="ff93d-242">Sensitive information types inventory</span></span>](what-the-sensitive-information-types-look-for.md)
    

