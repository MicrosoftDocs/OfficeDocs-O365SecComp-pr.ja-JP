---
title: 作成、テスト、および DLP ポリシーを調整します。
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: 'DLP ポリシーを開始する最も簡単で最も一般的な方法では、Office 365 に含まれているテンプレートのいずれかを使用します。 '
ms.openlocfilehash: 1d4697811a5d8dd426fed80d3d60bcd2fbea6335
ms.sourcegitcommit: 42c7ad69f95fc4d2de13293b39cc44931b9f82e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2018
ms.locfileid: "26522789"
---
# <a name="create-test-and-tune-a-dlp-policy"></a><span data-ttu-id="6b2e8-103">作成、テスト、および DLP ポリシーを調整します。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-103">Create, test, and tune a DLP policy</span></span>

<span data-ttu-id="6b2e8-104">**プリンシパルの作成**</span><span class="sxs-lookup"><span data-stu-id="6b2e8-104">**Principal author**</span></span> </br>
<span data-ttu-id="6b2e8-105">Paul Cunningham、マイクロソフト MVP</span><span class="sxs-lookup"><span data-stu-id="6b2e8-105">Paul Cunningham, Microsoft MVP</span></span> </br>
[<span data-ttu-id="6b2e8-106">実用的な 365</span><span class="sxs-lookup"><span data-stu-id="6b2e8-106">Practical 365</span></span>](https://practical365.com/) </br>
[<span data-ttu-id="6b2e8-107">@Practical365</span><span class="sxs-lookup"><span data-stu-id="6b2e8-107">@Practical365</span></span>](https://twitter.com/practical365)</br>
__________________________________________________

<span data-ttu-id="6b2e8-p101">データ損失の防止は、不要な関係者に機密情報が意図的または偶発的な漏洩を防ぐため、組織のために設計されている Office 365 のコンプライアンス機能です。DLP は Exchange Server および Exchange Online では、そのルートには、SharePoint Online とビジネスの OneDrive に該当する場合もできます。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p101">Data loss prevention is a compliance feature of Office 365 that is designed to help your organization prevent the intentional or accidental exposure of sensitive information to unwanted parties. DLP has its roots in Exchange Server and Exchange Online, and is also applicable in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="6b2e8-p102">DLP では、コンテンツ分析エンジンを使用して、クレジット カード番号などの機密情報や個人を特定できる情報 (PII) をお求めに電子メール メッセージとファイルの内容を確認します。機密性の高い情報通常や禁止される、電子メールで送信される電子メール メッセージやファイルの暗号化などの追加の手順を実行しなくてもドキュメントに含まれています。DLP を使用して、機密情報の検出し、処理を次のように。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p102">DLP uses a content analysis engine to examine the contents of email messages and files, looking for sensitive information such as credit card numbers and personally identifiable information (PII). Sensitive information should typically not be sent in email, or included in documents, without taking additional steps such as encrypting the email message or files. Using DLP you can detect sensitive information, and take action such as:</span></span>

- <span data-ttu-id="6b2e8-113">監査のため、イベント ログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-113">Log the event for auditing purposes</span></span>
- <span data-ttu-id="6b2e8-114">電子メールを送信またはファイルの共有は、エンド ・ ユーザーに警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-114">Display a warning to the end user who is sending the email or sharing the file</span></span>
- <span data-ttu-id="6b2e8-115">電子メールまたはファイル共有が行われてからを積極的にブロックします。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-115">Actively block the email or file sharing from taking place</span></span>

<span data-ttu-id="6b2e8-p103">自体を保護する必要があるデータの種類を考慮していないために、お客様は DLP を無視します。医療記録や財務情報などの機密性の高いデータのみがある医療保険などの業界やオンライン ストアを実行している企業が前提とします。あらゆるビジネスは、そのことを認識しない場合でも、定期的に重要な情報を処理できます。スプレッドシートの従業員の名前と誕生日の日だけとして重要顧客の名前とクレジット カードの詳細のスプレッドシートです。この種の情報を従業員行き、日常のタスクのシステムから CSV ファイルをエクスポートの何も考えると、他のユーザーに電子メールで送信すると浮遊、期待したよりも大きくする傾向があります。驚いたかもしれませんどのくらいの頻度の従業員は、結果を検討して、クレジット_カード番号や銀行の詳細情報を含む電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p103">Sometimes customers dismiss DLP because they don't consider themselves to have the type of data that needs protecting. The assumption is that sensitive data, such as medical records or financial information, only exists for industries like health care or for companies that run online stores. But any business can handle sensitive information on a regular basis, even if they don't realize it. A spreadsheet of employee names and dates of birth is just as sensitive as a spreadsheet of customer names and credit card details. And this type of information tends to float around more than you might expect, as employees quietly go about their day to day tasks, thinking nothing of export a CSV file from a system and emailing it to someone. You might also be surprised how often employees send emails containing credit card or banking details without considering the consequences.</span></span>

## <a name="how-sensitive-information-is-detected-by-dlp"></a><span data-ttu-id="6b2e8-122">DLP による機密性の高い情報を検出する方法</span><span class="sxs-lookup"><span data-stu-id="6b2e8-122">How sensitive information is detected by DLP</span></span>

<span data-ttu-id="6b2e8-p104">機密情報は、正規表現 (RegEx) パターン照合することによって、一致するパターンを特定のキーワードの近くなど他のインジケーターとの組み合わせで識別されます。この例としては、クレジット カード番号です。VISA のクレジット カード番号には、16 桁の数字があります。ただし、これらの数字が記述する 1111-1111-1111-1111 など、さまざまな方法で 1111 1111 1111 1111、1111111111111111 か。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p104">Sensitive information is identified by regular expression (RegEx) pattern matching, in combination with with other indicators such as the proximity of certain keywords to the matching patterns. An example of this is credit card numbers. A VISA credit card number has 16 digits. However, those digits can be written in different ways, such as 1111-1111-1111-1111, 1111 1111 1111 1111, or 1111111111111111.</span></span>

<span data-ttu-id="6b2e8-p105">必ずしもクレジット カード番号が 16 桁の任意の文字列ではありません、ヘルプ デスク システム、またはハードウェアのシリアル番号からのチケット番号がある可能性があります。クレジット カード番号と、無害な 16 桁の文字列の間で違いを見分けるには、計算結果が実行されます (チェックサム) の数値がさまざまなクレジット カードのブランドからの既知のパターンと一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p105">Any 16 digit string is not necessarily a credit card number, it could be a ticket number from a help desk system, or a serial number of a piece of hardware. To tell the difference between a credit card number and a harmless 16-digit string, a calculation is performed (checksum) to confirm that the numbers match a known pattern from the various credit card brands.</span></span>

<span data-ttu-id="6b2e8-129">さらに、近くにクレジット カードの有効期限日、可能性のある日付の値に「VISA」や「日経平均」、近くに、などキーワードのもと見なされますかどうかのデータ、クレジット カード番号か判断を行います。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-129">Furthermore, the proximity of keywords such as “VISA” or “AMEX”, along with the proximity to date values that might be the credit card expiry date, is also considered to make a decision about whether the data is a credit card number or not.</span></span>

<span data-ttu-id="6b2e8-130">つまり、DLP は、通常電子メールでこれら 2 つのテキストの違いを認識できるほどです。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-130">In other words, DLP is usually smart enough to recognize the difference between these two texts in an email:</span></span>

- <span data-ttu-id="6b2e8-p106">"ことができますを注文する] 新しいラップトップ コンピューター。VISA 番号 1111-1111-1111-1111、11 月 22 日、有効期限を使用し、する必要がある場合、予定出荷日を送ってください。」</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p106">“Can you order me a new laptop. Use my VISA number 1111-1111-1111-1111, expiry 11/22, and send me the estimated delivery date when you have it.”</span></span>
- <span data-ttu-id="6b2e8-p107">「2222-2222-2222-2222 では、ラップトップのシリアル番号と 11/2010 で購入しました。ところで、visa の出張費が承認されたまだですか?」</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p107">“My laptop serial number is 2222-2222-2222-2222 and it was purchased on 11/2010. By the way, is my travel visa approved yet?”</span></span>

<span data-ttu-id="6b2e8-135">ブックマークを保存するのには適切な参照は、各情報の種類を検出する方法を説明するこの[機密性の高い情報の種類に関するトピック](what-the-sensitive-information-types-look-for.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-135">A good reference to keep bookmarked is this [topic on sensitive information types](what-the-sensitive-information-types-look-for.md) that explains how each information type is detected.</span></span>

## <a name="where-to-start-with-data-loss-prevention"></a><span data-ttu-id="6b2e8-136">データ損失の防止を開始する場所</span><span class="sxs-lookup"><span data-stu-id="6b2e8-136">Where to start with data loss prevention</span></span>

<span data-ttu-id="6b2e8-p108">データ漏洩のリスクが完全に明らかなされていないときにすることは困難を正確にする必要がありますを開始する DLP を実装するための作業です。幸いなことに、DLP ポリシーは、"テスト モードをオンにする前に、その有効性と正確性を測定することで実行できます。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p108">When the risks of data leakage aren't entirely obvious, it's difficult to work out where exactly you should start with implementing DLP. Fortunately, DLP policies can be run in “test mode”, allowing you to gauge their effectiveness and accuracy before you turn them on.</span></span>

<span data-ttu-id="6b2e8-p109">Exchange 管理センターでは、Exchange Online の DLP ポリシーを管理できます。セキュリティとコンプライアンスの中心からのすべての作業負荷の DLP ポリシーを構成するには、この資料のデモンストレーションを使用します。セキュリティとコンプライアンスの中心のことがわかります、DLP ポリシーの**データ損失の防止**[ > **ポリシー**です。**ポリシーの作成**を開始するをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p109">DLP policies for Exchange Online can be managed through the Exchange admin center. But you can configure DLP policies for all workloads through the Security & Compliance Center, so that's what I'll use for demonstrations in this article. In the Security & Compliance Center you'll find the DLP policies under **Data loss prevention** > **Policy**. Click on **Create a policy** to start.</span></span>

<span data-ttu-id="6b2e8-p110">Office 365 は、DLP ポリシーの作成に使用することができます[DLP ポリシー テンプレート](what-the-dlp-policy-templates-include.md)の範囲を提供します。オーストラリアのビジネスをしていることを考えてみましょう。財務、医療、健康、およびプライバシーの一般的なカテゴリに分類されるオーストラリアに関連するものだけを表示するのにはポリシー テンプレートをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p110">Office 365 provides a range of [DLP policy templates](what-the-dlp-policy-templates-include.md) you can use to create DLP policies. Let's say that you're an Australian business. You can filter the policy templates to display only those that are relevant to Australia, which fall into the general categories of Financial, Medical and Health, and Privacy.</span></span>

![国または地域を選択するオプション](media/DLP-create-test-tune-choose-country.png)

<span data-ttu-id="6b2e8-147">このデモでは選択するオーストラリア個人を特定できる情報 (PII) データは、オーストラリア税ファイル数 (TFN) とドライバーのライセンス番号の情報の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-147">For this demonstration I'll choose Australian Personally Identifiable Information (PII) Data, which includes the information types of Australian Tax File Number (TFN) and Driver's License Number.</span></span>

![ポリシー テンプレートを選択するオプション](media/DLP-create-test-tune-choose-policy-template.png)

<span data-ttu-id="6b2e8-p111">新しい DLP ポリシーに名前を付けます。既定の名前が DLP ポリシー テンプレートに一致しますが、同じテンプレートから複数のポリシーを作成することができますので、独自のわかりやすい名前を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p111">Give your new DLP policy a name. The default name will match the DLP policy template, but you should choose a more descriptive name of your own, because multiple policies can be created from the same template.</span></span>

![ポリシーの名前を指定するオプション](media/DLP-create-test-tune-name-policy.png)

<span data-ttu-id="6b2e8-p112">ポリシーを適用する場所を選択します。DLP ポリシーは、Exchange のオンライン、SharePoint Online では、およびビジネスのための OneDrive に適用できます。このポリシーをすべての場所に適用する構成のままにするつもりです。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p112">Choose the locations that the policy will apply to. DLP policies can apply to Exchange Online, SharePoint Online, and OneDrive for Business. I am going to leave this policy configured to apply to all locations.</span></span>

![すべての場所を選択するオプション](media/DLP-create-test-tune-choose-locations.png)

<span data-ttu-id="6b2e8-p113">だけで最初の**ポリシーの設定**手順をここでは既定値を受け入れます。非常に多くのカスタマイズは、DLP ポリシーで行うことができますが、デフォルトでは問題の場所を開始します。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p113">At the first **Policy Settings** step just accept the defaults for now. There is quite a lot of customization you can do in DLP policies, but the defaults are a fine place to start.</span></span>

![保護するコンテンツの種類をカスタマイズするオプション](media/DLP-create-test-tune-default-customization-settings.png)

<span data-ttu-id="6b2e8-p114">**次へ**をクリックした後がカスタマイズ オプションが他の**ポリシーの設定**ページに表示されます。テストするだけのポリシーの場合、ここでは、いくつかの調整を行う起動することができます。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p114">After clicking **Next** you'll be presented with an additional **Policy Settings** page with more customization options. For a policy that you are just testing, here's where you can start to make some adjustments.</span></span>

- <span data-ttu-id="6b2e8-p115">アウトのことをテストしているだけで、ユーザーにまだ何も表示しない場合に実行する適切な手順は、ポリシーのヒントをオフします。ポリシーのヒントは、DLP ポリシーに違反しようとしているユーザーに警告を表示します。たとえば、Outlook ユーザーはクレジット カード番号には添付するファイルが含まれている警告が表示され、自分の電子メールを拒否するのには。ポリシー ヒントの目的が起こる前に、非準拠の動作を停止するのには。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p115">I've turned off policy tips for now, which is a reasonable step to take if you're just testing things out and don't want to display anything to users yet. Policy tips display warnings to users that they're about to violate a DLP policy. For example, an Outlook user will see a warning that the file they've attached contains credit card numbers and will cause their email to be rejected. The goal of policy tips is to stop the non-compliant behaviour before it happens.</span></span>
- <span data-ttu-id="6b2e8-165">私も小さくなった 1、10 からのインスタンスの数いるため、このポリシーはないだけで一括データの共有、オーストラリアの個人情報データの共有を検出します。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-165">I've also decreased the number of instances from 10 to 1, so that this policy will detect any sharing of Australian PII data, not just bulk sharing of the data.</span></span>
- <span data-ttu-id="6b2e8-166">インシデント レポートの電子メールを他の受信者を追加しました。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-166">I've also added another recipient to the incident report email.</span></span>

![追加のポリシー設定](media/DLP-create-test-tune-more-policy-settings.png)

<span data-ttu-id="6b2e8-p116">最後に、最初にテスト モードで実行するには、このポリシーを設定しました。テスト モードでポリシーのヒントを無効にするオプションもあることを確認します。これにより、ポリシー ヒントが、ポリシーで有効になっていても、テスト中にそれらを非表示を切り替えるかどうかを決定し、柔軟にします。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p116">Finally, I've configured this policy to run in test mode initially. Notice there's also an option here to disable policy tips while in test mode. This gives you the flexibility to have policy tips enabled in the policy, but then decide whether to show or suppress them during your testing.</span></span>

![最初にポリシーをテストするにはオプション](media/DLP-create-test-tune-test-mode.png)

<span data-ttu-id="6b2e8-172">最終確認画面には、ポリシーの作成を完了するのには**作成**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-172">On the final review screen click **Create** to finish creating the policy.</span></span>

## <a name="test-a-dlp-policy"></a><span data-ttu-id="6b2e8-173">DLP ポリシーをテストします。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-173">Test a DLP policy</span></span>

<span data-ttu-id="6b2e8-p117">新しい DLP ポリシーは、約 1 時間内で有効にするために開始されます。放置して通常のユーザーのアクティビティがトリガーされるまで待つか、自分で実行しようとすることができます。以前のバージョンは、この[機密情報の種類に関するトピック](what-the-sensitive-information-types-look-for.md)DLP の一致を起動する方法に関する情報を提供するにリンクされています。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p117">Your new DLP policy will begin to take effect within about 1 hour. You can sit and wait for it to be triggered by normal user activity, or you can try to trigger it yourself. Earlier I linked to this [topic on sensitive information types](what-the-sensitive-information-types-look-for.md), which provides you with information about how to trigger DLP matches.</span></span>

<span data-ttu-id="6b2e8-p118">たとえば、DLP ポリシーを作成したこの資料のオーストラリアの税のファイル番号 (TFN) が検出されます。マニュアルによれば、一致は次の基準に基づいています。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p118">As an example, the DLP policy I created for this article will detect Australian tax file numbers (TFN). According to the documentation, the match is based on the following criteria.</span></span>

![オーストラリア税のファイル番号についてのドキュメント](media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
<span data-ttu-id="6b2e8-p119">TFN の検出ではなく矢印の反対の方法で示すために、「税のファイル番号」の文字を含む電子メールとの近くに 9 桁文字列セールズを問題なく。DLP ポリシーは実行されませんは、9 桁の文字列がチェックサムを示す有効な TFN とだけでなく、無害な数値文字列を渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p119">To demonstrate TFN detection in a rather blunt manner, an email with the words “Tax file number” and a 9 digit string in close proximity will sail through without any issues. The reason it does not trigger the DLP policy is that the 9-digit string must pass the checksum that indicates it is a valid TFN and not just a harmless string of numbers.</span></span>

![オーストラリア税のファイルの番号には、チェックサムを渡しません。](media/DLP-create-test-tune-email-test1.png)

<span data-ttu-id="6b2e8-p120">比較では、「税のファイル番号」の文字を含む電子メールとチェックサムを通過する有効な TFN ポリシーが発生します。ここでレコードの TFN を使用して撮影を生成する web サイトから有効ですが、非正規品 TFNs です。[有効ですが、偽のクレジット カード番号](http://www.fakecreditcardgenerator.net/)を生成するようなサイトがあります。このようなサイトは、DLP ポリシーをテストするときの最も一般的な間違いの 1 つは、偽の数字を有効ではありませんし、チェックサムが転送されません (ポリシーをトリガーしません) を使用しているために非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p120">In comparison, an email with the words “Tax file number” and a valid TFN that passes the checksum will trigger the policy. For the record here, the TFN I'm using was taken from a website that generates valid, but not genuine, TFNs. There are similar sites that generate [valid but fake credit card numbers](http://www.fakecreditcardgenerator.net/). Such sites are very useful because one of the most common mistakes when testing a DLP policy is using a fake number that's not valid and won't pass the checksum (and therefore won't trigger the policy).</span></span>

![オーストラリア税のファイルの番号には、チェックサムを渡されます。](media/DLP-create-test-tune-email-test2.png)

<span data-ttu-id="6b2e8-188">インシデント レポートの電子メールには、検出された機密性の高い情報の種類、インスタンスの数が検出されたと検出の信頼レベルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-188">The incident report email includes the type of sensitive information that was detected, how many instances were detected, and the confidence level of the detection.</span></span>

![税のファイル番号が表示されているインシデントのレポートが検出されました](media/DLP-create-test-tune-email-incident-report.png)

<span data-ttu-id="6b2e8-p121">テスト モードで、DLP ポリシーのままにインシデント レポートの電子メールを分析すると、DLP ポリシーとどのように効果的なことが強制されることの正確さの感触をつかむを開始できます。インシデント レポートには、他には、 [DLP のレポートを使用して](view-the-dlp-reports.md)テナント間でのポリシーと一致する集約的なビューを表示するにできます。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p121">If you leave your DLP policy in test mode and analyze the incident report emails, you can start to get a feel for the accuracy of the DLP policy and how effective it will be when it is enforced. In addition to the incident reports, you can [use the DLP reports](view-the-dlp-reports.md) to see an aggregated view of policy matches across your tenant.</span></span>

## <a name="tune-a-dlp-policy"></a><span data-ttu-id="6b2e8-192">DLP ポリシーを調整します。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-192">Tune a DLP policy</span></span>

<span data-ttu-id="6b2e8-p122">ポリシー、ヒット数を分析すると、ポリシーがどのように動作するいくつかの調整をすることも。単純な例では、として、電子メールで 1 つの TFN は、(と思うことも、ですが、デモンストレーションのためにしてみましょう) の問題ではありませんが 2 つ以上のインスタンスは問題を決定する場合があります。複数のインスタンスには、従業員、外部の会計サービスなど、外部のベンダーに、HR データベースから CSV エクスポートの電子メールを送信するように危険な可能性があります。間違いなく何かを検出し、ブロックをお望みです。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p122">As you analyze your policy hits you might want to make some adjustments to how the policies behave. As a simple example, you might determine that one TFN in email is not a problem (I think it still is, but let's go with it for the sake of demonstration), but two or more instances is a problem. Multiple instances could be a risky scenario such as an employee emailing a CSV export from the HR database to an external party, for example an external accounting service. Definitely something you would prefer to detect and block.</span></span>

<span data-ttu-id="6b2e8-197">セキュリティとコンプライアンス センターでの動作を調整するのには既存のポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-197">In the Security & Compliance Center you can edit an existing policy to adjust the behaviour.</span></span>

![ポリシーを編集するオプション](media/DLP-create-test-tune-edit-policy.png)
 
<span data-ttu-id="6b2e8-199">ポリシーは、特定のワークロードにのみ、または特定のサイトやアカウントに適用するための場所の設定を調整できます。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-199">You can adjust the location settings so that the policy is applied only to specific workloads, or to specific sites and accounts.</span></span>

![特定の場所を選択するオプション](media/DLP-create-test-tune-edit-locations.png)

<span data-ttu-id="6b2e8-201">ポリシーの設定を調整し、お客様のニーズにより適合するように規則を編集できます。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-201">You can also adjust the policy settings and edit the rules to better suit your needs.</span></span>

![規則を編集するオプション](media/DLP-create-test-tune-edit-rule.png)

<span data-ttu-id="6b2e8-203">DLP ポリシーに含まれるルールを編集するときに変更できます。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-203">When editing a rule within a DLP policy you can change:</span></span>

- <span data-ttu-id="6b2e8-204">などの条件の種類とルールをトリガーする機密性の高いデータのインスタンスの数です。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-204">The conditions, including the type and number of instances of sensitive data that will trigger the rule.</span></span>
- <span data-ttu-id="6b2e8-205">コンテンツへのアクセスを制限するなど、実行されるアクションです。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-205">The actions that are taken, such as restricting access to the content.</span></span>
- <span data-ttu-id="6b2e8-206">ユーザー通知は、ポリシーのヒントを電子メール クライアントまたは web ブラウザーでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-206">User notifications, which are policy tips that are displayed to the user in their email client or web browser.</span></span>
- <span data-ttu-id="6b2e8-207">ユーザーは、ユーザーが、電子メールやファイル共有をこのまま続行するのには選択できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-207">User overrides, which determines whether users can choose to proceed with their email or file sharing anyway.</span></span>
- <span data-ttu-id="6b2e8-208">インシデント レポートを管理者に通知します。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-208">Incident reports, to notify administrators.</span></span>

![ルールの部分を編集するためのオプション](media/DLP-create-test-tune-editing-options.png)

<span data-ttu-id="6b2e8-p123">このデモでは、(適切なユーザーの意識向上トレーニングしなくてもこの操作を行う注意が必要である)、ポリシーにユーザーの通知を追加して、業務の妥当性、または誤検知としてフラグを立てることで、ポリシーを無効にするユーザーを許可します。カスタマイズすることも、電子メールおよびポリシー ヒント テキスト、組織のポリシーに関する追加情報を含めるか、サポートにお問い合わせの質問がある場合にユーザーにメッセージを表示する場合に注意してください。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p123">For this demonstration I've added user notifications to the policy (be careful of doing this without adequate user awareness training), and allowed users to override the policy with a business justification or by flagging it as a false positive. Note that you can also customize the email and policy tip text if you want to include any additional information about your organization's policies, or prompt users to contact support if they have questions.</span></span>

![ユーザーの通知および上書きのオプション](media/DLP-create-test-tune-user-notifications.png)

<span data-ttu-id="6b2e8-p124">高いボリュームと低いボリュームの処理のための 2 つの規則がポリシーに含まれていますので、両方で使用するアクションを編集するのには。これは、その特性により異なる方法での場合を扱うことです。など、音量が小さい違反の上書きを許可するが、大量の違反の上書きを許可しないする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p124">The policy contains two rules for handling of high volume and low volume, so be sure to edit both with the actions that you want. This is an opportunity to treat cases differently depending on their characteristics. For example, you might allow overrides for low volume violations, but not allow overrides for high volume violations.</span></span>

![高いボリュームと低いボリュームの 1 つのルールの 1 つのルール](media/DLP-create-test-tune-two-rules.png)

<span data-ttu-id="6b2e8-217">実際にブロックまたはポリシーに違反しているコンテンツへのアクセスを制限する場合は、これを行うルールのアクションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-217">Also, if you want to actually block or restrict access to content that is in violation of policy, you need to configure an action on the rule to do so.</span></span>

![コンテンツへのアクセスを制限するオプション](media/DLP-create-test-tune-restrict-access-action.png)

<span data-ttu-id="6b2e8-p125">ポリシーの設定に加えた変更を保存して、またポリシーの主な設定ページに戻るし、ポリシーがテスト モードでは、ユーザーにポリシーのヒントを表示するオプションを有効にする必要があります。これは、エンド ・ ユーザ、DLP ポリシーを導入し、操作を行いますユーザーの意識向上トレーニングの生産性に影響を与える多くの偽陽性を危険にさらさずに効果的な方法です。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p125">After saving those changes to the policy settings, I also need to return to the main settings page for the policy and enable the option to show policy tips to users while the policy is in test mode. This is an effective way to introduce DLP policies to your end users, and do user awareness training, without risking too many false positives that impact their productivity.</span></span>

![テスト モードでポリシーのヒントを表示します](media/DLP-create-test-tune-show-policy-tips.png)

<span data-ttu-id="6b2e8-p126">サーバー側 (またはクラウドにある場合)、変更がすぐに反映されません、処理のさまざまな間隔のため。DLP ポリシーの変更、ユーザーに新しいポリシーのヒントを表示する場合、ユーザーが即座に 24 時間ごとにポリシーの変更をチェックする、Outlook クライアントの変更が表示されません。テストできるようにする場合は、 [PolicyNudges キーの最後のダウンロード時刻のスタンプをオフ](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)にするにはこのレジストリの修正プログラムを使用できます。ダウンロード最新ポリシー情報を次にそれを再起動して、電子メール メッセージの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p126">On the server side (or cloud side if you prefer), the change may not take effect immediately, due to various processing intervals. If you're making a DLP policy change that will display new policy tips to a user, the user may not see the changes take effect immediately in their Outlook client, which checks for policy changes every 24 hours. If you want to speed things up for testing, you can use this registry fix to [clear the last download time stamp from the PolicyNudges key](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451). Outlook will download the latest policy information the next time you restart it and begin composing an email message.</span></span>

<span data-ttu-id="6b2e8-226">ポリシー ヒントが有効になっている場合は、ユーザーが Outlook では、ヒントを参照してくださいになり、偽陽性に報告するが発生したとき。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-226">If you have policy tips enabled, the user will begin to see the tips in Outlook, and can report false positives to you when they occur.</span></span>

![レポートの誤検出オプションを使用してポリシーのヒント](media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a><span data-ttu-id="6b2e8-228">誤検出の調査します。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-228">Investigate false positives</span></span>

<span data-ttu-id="6b2e8-p127">DLP ポリシー テンプレートは、すんなり完成していません。わかります DLP 展開の方法を容易にするため非常に重要である理由は、自分の環境で発生しているいくつかの偽陽性にかかる時間が十分にテストし、ポリシーを調整することがあります。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p127">DLP policy templates are not perfect straight out of the box. It's likely that you'll find some false positives occurring in your environment, which is why it's so important to ease your way into a DLP deployment, taking the time to adequately test and tune your policies.</span></span>

<span data-ttu-id="6b2e8-p128">ここでは、偽陽性の例です。このメールは、まったく無害です。ユーザーは、他の人に自分の携帯電話番号を提供して、電子メールの署名を含みます。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p128">Here's an example of a false positive. This email is quite harmless. The user is providing their mobile phone number to someone, and including their email signature.</span></span>

![正偽の情報を表示する電子メール](media/DLP-create-test-tune-false-positive-email.png)
 
<span data-ttu-id="6b2e8-235">ユーザーに警告するメッセージを電子メールにはでの機密情報が含まれているポリシーに関するヒントが表示されるが、具体的には、オーストラリアの運転免許証の番号です。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-235">But the user sees a policy tip warning them that the email contains sensitive information, specifically, an Australian driver's license number.</span></span>

![ポリシー ヒントの誤検出をレポートするオプション](media/DLP-create-test-tune-policy-tip-closeup.png)

<span data-ttu-id="6b2e8-p129">ユーザーが、正の場合は false を報告しが発生した理由を管理者が確認できます。インシデント レポートの電子メール、電子メールのフラグが付けられて誤検知します。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p129">The user can report the false positive, and the administrator can look into why it has occurred. In the incident report email, the email is flagged as a false positive.</span></span>

![インシデント レポート表示の誤検知](media/DLP-create-test-tune-false-positive-incident-report.png)

<span data-ttu-id="6b2e8-p130">このドライバーのライセンスの場合は、詳しく説明する良い例です。この誤認をオーストラリアのドライバーのライセンスの種類は、(1 つでも、10 桁の文字列の一部である)、任意の 9 桁の数字文字列により実行されることは、内で発生しました「ニューサウスウェールズ州のシドニー」のキーワードの 300 文字近くの理由 (いない大文字小文字を区別)。ユーザーは、シドニーで行われるためにのみ、電話番号および電子メールの署名によってトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p130">This driver's license case is a good example to dig into. The reason this false positive has occurred is that the “Australian Driver's License” type will be triggered by any 9-digit string (even one that is part of a 10-digit string), within 300 characters proximity to the keywords “sydney nsw” (not case sensitive). So it's triggered by the phone number and email signature, only because the user happens to be in Sydney.</span></span>

<span data-ttu-id="6b2e8-p131">興味深いことに、シドニー、ニュー サウス ウェールズにコンマがある場合、DLP ポリシーは発生しません。あるないアイデアなぜコンマの違いをここもなぜオーストラリアのドライバーのライセンス情報の種類のキーワードで他の都市およびオーストラリアの状態が含まれていないが、ですね。では、どうすればそれについてでしょうか。いくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p131">Interestingly, if “Sydney, NSW” has a comma, the DLP policy is not triggered. I have no idea why a comma makes any difference here, nor why other cities and states in Australia aren't included in the keywords for the Australian driver's license information type, but there you go. So, what can we do about it? There's a couple of options.</span></span>

<span data-ttu-id="6b2e8-p132">1 つのオプションでは、ポリシーからオーストラリアのドライバーのライセンス情報の種類を削除します。DLP ポリシー テンプレートの一部であるためにはしているそれを使用する必要はありませんが。だけ税のファイル番号、運転免許証ではないに興味があるなら、のみ削除できます。たとえば、ポリシーで音量が小さいルールから削除はのままに大量のルールで複数のドライバーのライセンスのリストがまだ認識できるようにできます。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p132">One option is to remove the Australian driver's license information type from the policy. It's in there because it's part of the DLP policy template, but we're not forced to use it. If you're only interested in Tax File Numbers and not driver's licenses, you can just remove it. For example, you can remove it from the low volume rule in the policy, but leave it in the high volume rule so that lists of multiple drivers licenses are still detected.</span></span>

![ルールから機密性の高い情報の種類を削除するオプション](media/DLP-create-test-tune-delete-low-volume-rule.png)
 
<span data-ttu-id="6b2e8-252">別のオプションは単にインスタンスの数を大きくには複数のインスタンスがある場合に、運転免許証の音量が小さいが検出されるだけです。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-252">Another option is to simply increase the instance count, so that a low volume of driver's licenses is only detected when there are multiple instances.</span></span>

![インスタンスの数を編集するオプション](media/DLP-create-test-tune-edit-instance-count.png)

<span data-ttu-id="6b2e8-p133">インスタンスの数を変更するには、他は、一致の正確性、信頼度のレベル) を調整することもできます。機密性の高い情報の種類に複数のパターンがある場合は、ルールが特定のパターンと一致するよう、ルールの一致精度を調整できます。などの誤を削減するには、設定できます、ルールの一致精度で最高の信頼レベルでのみのパターンと一致するようにします。信頼度の計算方法を理解することが、少し注意が必要であり、この投稿の範囲外) が、適切に[ルールを調整するのには、信頼レベルを使用する方法](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy)の説明を次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p133">In addition to changing the instance count, you can also adjust the match accuracy (or confidence level). If your sensitive information type has multiple patterns, you can adjust the match accuracy in your rule, so that your rule matches only specific patterns. For example, to help reduce false positives, you can set the match accuracy of your rule so that it matches only the pattern with the highest confidence level. Understanding how confidence level is calculated is a bit tricky (and beyond the scope of this post), but here's a good explanation of [how to use confidence level to tune your rules](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy).</span></span>

<span data-ttu-id="6b2e8-p134">最後に、でももう少しを取得する場合は、高度なあらゆる種類の機密情報をカスタマイズすることができます--[オーストラリアの運転免許証](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number)誤認の上のトリガーを削除するためのキーワードのリストから「シドニー ニューサウスウェールズ州」を削除するなどです。これは、XML および PowerShell を使用する方法については、[組み込まれている機密性の高い情報の種類をカスタマイズする方法](customize-a-built-in-sensitive-information-type.md)のこのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p134">Finally, if you want to get even a bit more advanced, you can customize any sensitive information type -- for example, you can remove "Sydney NSW" from the list of keywords for [Australian Driver's License](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number), to eliminate the false positive triggered above. To learn how to do this by using XML and PowerShell, see this topic on [customizing a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

## <a name="turn-off-a-dlp-policy"></a><span data-ttu-id="6b2e8-260">DLP ポリシーを無効にする</span><span class="sxs-lookup"><span data-stu-id="6b2e8-260">Turn off a DLP policy</span></span>

<span data-ttu-id="6b2e8-261">決まったら、DLP ポリシーが正確には、機密性の高い情報の種類、および、エンド ・ ユーザーは配置されているポリシーを処理する準備ができたことを効果的に検出を有効にできます、ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-261">When you're happy that your DLP policy is accurately and effectively detecting sensitive information types, and that your end users are ready to deal with the policies being in place, then you can enable the policy.</span></span>

![ポリシーを有効にするオプション](media/DLP-create-test-tune-turn-on-policy.png)
 
<span data-ttu-id="6b2e8-263">場合は待っているときに、ポリシーが有効では、 [Office 365 のセキュリティとコンプライアンス センター PowerShell への接続](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)と、DistributionStatus を参照するのには、 [Get DlpCompliancePolicy コマンドレット](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps)を実行するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-263">If you're waiting to see when the policy will take effect, [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) and run the [Get-DlpCompliancePolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps) to see the DistributionStatus.</span></span>

![PowerShell のコマンドレットを実行します。](media/DLP-create-test-tune-PowerShell.png)

<span data-ttu-id="6b2e8-p135">DLP ポリシーの電源を入れた後、最終的なテストをいくつかに独自のポリシーの予想される動作が発生していることを確認を実行してください。クレジット カード データなどの情報をテストしようとしている場合は、web サイト オンライン クレジット カードのサンプルを生成する方法についての情報やその他の個人情報とチェックサムを渡すと、ポリシーのトリガーがあります。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p135">After turning on the DLP policy, you should run some final tests of your own to make sure that the expected policy actions are occurring. If you're trying to test things like credit card data, there are websites online with information on how to generate sample credit card or other personal information that will pass checksums and trigger your policies.</span></span>

<span data-ttu-id="6b2e8-267">ユーザーのオーバーライドを許可するポリシーは、そのオプションをポリシーのヒントの一部としてユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-267">Policies that allow user overrides will present that option to the user as part of the policy tip.</span></span>

![ユーザーのオーバーライドを許可するポリシーのヒント](media/DLP-create-test-tune-override-option.png)

<span data-ttu-id="6b2e8-269">コンテンツを制限するポリシーは、ポリシーのヒントの一部としてユーザーに警告を表示し、電子メールを送信しないようにします。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-269">Policies that restrict content will present the warning to the user as part of the policy tip, and prevent them from sending the email.</span></span>

![ポリシー ヒントのコンテンツが制限されます。](media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a><span data-ttu-id="6b2e8-271">概要</span><span class="sxs-lookup"><span data-stu-id="6b2e8-271">Summary</span></span>

<span data-ttu-id="6b2e8-p136">データ損失防止のポリシーは、あらゆる種類の組織に役立ちます。ポリシーのヒント、エンド ・ ユーザーの上書き、およびインシデント レポートのようなものである場合、コントロールのための危険度の低い練習は、DLP ポリシーをテストします。静かに違反の種類が、組織で既に発生しているを参照してくださいにいくつかの DLP ポリシーをテストすることと、特殊能力を持つポリシーを偽の肯定率が低いに許可し、許可されていないユーザーを教育し、DLP ポリシーを展開し、組織です。</span><span class="sxs-lookup"><span data-stu-id="6b2e8-p136">Data loss prevention policies are useful for organizations of all types. Testing some DLP policies is a low risk exercise due to the control you have over things like policy tips, end user overrides, and incident reports. You can quietly test some DLP policies to see what type of violations are already occurring in your organization, and then craft policies with low false positive rates, educate your users on what is allowed and not allowed, and then roll out your DLP policies to the organization.</span></span>
