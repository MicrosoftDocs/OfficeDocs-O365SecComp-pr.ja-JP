---
title: 機密ラベルの概要
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 10/22/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: Office 365 の機密ラベルを使用すると、機密コンテンツの分類が可能になり、機密コンテンツの保護に役立てることができます。このラベルの使用によって、共同作業の生産性や機能性が低下することはありません。機密ラベルは、ラベル付けされたコンテンツの暗号化や透かしなどの保護設定を強制適用するために使用できます。
ms.openlocfilehash: ad6137ad00fa2e7eb83a405e429d6c7826cf6a90
ms.sourcegitcommit: d7e87ce4b1579ac47af2e853ef59ef058c40191f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "26547219"
---
# <a name="overview-of-sensitivity-labels"></a><span data-ttu-id="8345c-104">機密ラベルの概要</span><span class="sxs-lookup"><span data-stu-id="8345c-104">Overview of sensitivity labels</span></span>

<span data-ttu-id="8345c-p102">業務を達成するために、組織の従業員は、組織の内外の関係者と共同作業する必要があります。そのため、コンテンツがファイアウォールの内側にとどまることはなくなりました。コンテンツは、デバイス、アプリ、およびサービスを通じて、どこにでもローミングされます。そこで、コンテンツのローミング時には、組織のビジネス ポリシーとコンプライアンス ポリシーを満たすように、コンテンツを安全な状態で保護することが必要になります。</span><span class="sxs-lookup"><span data-stu-id="8345c-p102">To get their work done, people in your organization need to collaborate with others both inside and outside the organization. This means that content no longer stays behind a firewall – it roams everywhere, across devices, apps, and services. And when it roams, you want it to do so in a secure, protected way that meets your organization’s business and compliance policies.</span></span>

<span data-ttu-id="8345c-108">Office 365 の機密ラベルを使用すると、機密コンテンツの分類が可能になり、機密コンテンツの保護に役立てることができます。このラベルの使用によって、共同作業の生産性や機能性が低下することはありません。</span><span class="sxs-lookup"><span data-stu-id="8345c-108">With sensitivity labels in Office 365, you can classify and help protect your sensitive content, while making sure that your people’s productivity and ability to collaborate isn’t hindered.</span></span>

![Excel のリボンおよびステータス バーに示された機密ラベル](media/Sensitivity_label_in_Excel.png)

<span data-ttu-id="8345c-110">機密ラベルは、次の目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-110">You can use sensitivity labels to:</span></span>
  
- <span data-ttu-id="8345c-p103">**ラベルが付けられたコンテンツに、暗号化や透かしなどの保護設定を強制適用します。** たとえば、ユーザーはドキュメントや電子メールに「社外秘」ラベルを適用できます。そのラベルによって、コンテンツを暗号化して「社外秘」の透かしを適用できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p103">**Enforce protection settings such as encryption or watermarks on labeled content.** For example, your users can apply a Confidential label to a document or email, and that label can encrypt the content and apply a Confidential watermark.</span></span>    

- <span data-ttu-id="8345c-p104">**各種のプラットフォームおよびデバイスを通じて Office アプリのコンテンツを保護します。** 機密ラベルは、Windows、Mac、iOS、および Android の Office アプリで機能します。近日中には、Office Web アプリケーションについてもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p104">**Protect content in Office apps across different platforms and devices.** Sensitivity labels work in Office apps on Windows, Mac, iOS, and Android. Support for Office web apps is coming soon.</span></span>
    
- <span data-ttu-id="8345c-p105">**Windows を実行するデバイスでは、機密コンテンツの組織外への流出を防止します。** これには、Microsoft Intune の Endpoint Protection を使用します。Windows デバイスに存在するコンテンツに機密ラベルが適用されていると、Endpoint Protection により、そのコンテンツがサード パーティ製アプリ (Twitter や Gmail など)、またはリムーバブル記憶域 (USB ドライブなど) にコピーされることを防止できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p105">**Prevent sensitive content from leaving your organization on devices running Windows**, by using endpoint protection in Microsoft Intune. After a sensitivity label has been applied to content that resides on a Windows device, endpoint protection can prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>

- <span data-ttu-id="8345c-p106">**サード パーティ製アプリおよびサービスに機密ラベルを拡張します。** Microsoft Information Protection SDK を使用すると、Windows、Mac、および Linux 上のサード パーティ製アプリは、機密ラベルを認識して、保護設定を適用できるようになります。近日中には、iOS および Android もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p106">**Extend sensitivity labels to third-party apps and services.** With the Microsoft Information Protection SDK, third-party apps on Windows, Mac, and Linux can read sensitivity labels and apply protection settings. Support for apps on iOS and Android is coming soon.</span></span>

- <span data-ttu-id="8345c-p107">**保護設定を使用することなくコンテンツを分類します。** コンテンツに分類のみを (ステッカーのように) 割り当てることもできます。この分類は、コンテンツの使用時や共有時にコンテンツに永続してローミングされます。この分類を使用することで、機密コンテンツの使用レポートを生成して、アクティビティ データを確認できます。この情報に基づいて、後からいつでも保護設定を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p107">**Classify content without using any protection settings.** You can also simply assign a classification to content (like a sticker) that persists and roams with the content as it's used and shared. You can use this classification to generate usage reports and see activity data for your sensitive content. Based on this information, you can always choose at a later time to apply protection settings.</span></span>
    
<span data-ttu-id="8345c-p108">いずれの場合も、Office 365 の機密ラベルは、そのコンテンツに相応しい措置を講じる際に役立ちます。機密ラベルを使用すると、組織全体のデータを分類して、その分類に応じた保護設定を強制適用できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p108">In all of these cases, sensitivity labels in Office 365 can help you take the right actions on the right content. With sensitivity labels, you can classify data across your organization and enforce protection settings based on that classification.</span></span>
  
<span data-ttu-id="8345c-p109">機密ラベルは、Office 365 セキュリティ/コンプライアンス センターで作成します。Azure Information Protection および Office 365 全体の機密ラベルの構成は、セキュリティ/コンプライアンス センターで一元的に構成できるようになりました。こうした機密ラベルは、Azure Information Protection、Office アプリ、および Office 365 サービスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p109">You create sensitivity labels in the Office 365 Security &amp; Compliance Center. The Security & Compliance Center is now the single place to configure sensitivity labels and policies across Azure Information Protection and Office 365. These sensitivity labels can be used by Azure Information Protection, Office apps, and Office 365 services.</span></span>

<span data-ttu-id="8345c-p110">Azure Information Protection のお客様は、セキュリティ/コンプライアンス センターで独自の Azure Information Protection ラベルを使用できます。また、追加の構成や高度な構成を実行する場合は、そのラベルを Azure portal に同期できます。**Azure Information Protection ラベルと Office 365 機密ラベルは、相互に完全な互換性があります。** そのため、たとえば、Azure Information Protection でラベル付けしたコンテンツがある場合は、そのコンテンツの分類やラベル付けをやり直す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8345c-p110">For Azure Information Protection customers, you can use your Azure Information Protection labels in the Security & Compliance center, and your labels will be synced with the Azure portal in case you choose to perform additional or advanced configuration. **Azure Information Protection labels and Office 365 sensitivity labels are fully compatible with each other.** This means, for example, if you have content labeled by Azure Information Protection, you won’t need to reclassify or relabel your content.</span></span>

![セキュリティ/コンプライアンス センターの [ラベル] ページにある [機密] タブ](media/Sensitivity_label_tab_on_Labels_page.png)

## <a name="what-a-sensitivity-label-is"></a><span data-ttu-id="8345c-134">機密ラベルとは</span><span class="sxs-lookup"><span data-stu-id="8345c-134">What a sensitivity label is</span></span>

<span data-ttu-id="8345c-135">機密ラベルをドキュメントや電子メールに割り当てると、そのラベルは次の特徴を持つタグのようになります。</span><span class="sxs-lookup"><span data-stu-id="8345c-135">When you assign a sensitivity label to a document or email, it’s simply like a tag that is:</span></span>

- <span data-ttu-id="8345c-p111">**カスタマイズ可能。** さまざまな機密レベルのコンテンツに対応する組織内での分類項目 (「個人」、「公開」、「一般」、「社外秘」、「極秘」など) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p111">**Customizable.** You can create categories for different levels of sensitive content in your organization, such as Personal, Public, General, Confidential, and Highly Confidential.</span></span>

- <span data-ttu-id="8345c-p112">**クリア テキスト。** ラベルはクリア テキストになっているため、サード パーティ製アプリおよびサービスで、ラベルが付けられたコンテンツに保護アクションを適用する際に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p112">**Clear text.** Because the label is in clear text, it’s available for third-party apps and services to apply protective actions to labeled content.</span></span>

- <span data-ttu-id="8345c-p113">**永続的。** コンテンツにラベルが適用されると、適用されたラベルは電子メールやドキュメントのメタデータに永続します。つまり、ラベルは保護設定も含めてコンテンツと共にローミングされ、ポリシーの適用と強制実施の際の基準になるということです。</span><span class="sxs-lookup"><span data-stu-id="8345c-p113">**Persistent.** After a sensitivity label is applied to content, it persists in the metadata of that email or document. This means the label roams with the content, including the protection settings, and becomes the basis for applying and enforcing policies.</span></span>

<span data-ttu-id="8345c-143">Office アプリでは、機密ラベルは単に電子メールやドキュメントのタグとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="8345c-143">In the Office apps, a sensitivity label simply appears as a tag on an email or document.</span></span>

<span data-ttu-id="8345c-p114">コンテンツの各アイテムには、単一の機密ラベルを適用できます。ただし、1 つのアイテムに 1 つの機密ラベルと 1 つの[保持ラベル](labels.md)の両方が適用可能である点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8345c-p114">Each item of content can have a single sensitivity label applied to it. But note that an item can have both a single sensitivity label and a single [retention label](labels.md) applied to it.</span></span>

![電子メールに適用された機密ラベル](media/Sensitivity_label_on_email.png)

## <a name="what-sensitivity-labels-can-do"></a><span data-ttu-id="8345c-147">機密ラベルでできること</span><span class="sxs-lookup"><span data-stu-id="8345c-147">What sensitivity labels can do</span></span>

<span data-ttu-id="8345c-p115">電子メールやドキュメントに機密ラベルが適用されると、そのラベルに応じた保護設定がコンテンツに強制適用されます。機密ラベルを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p115">After a sensitivity label is applied to an email or document, the protection settings for that label are enforced on the content. With a sensitivity label, you can:</span></span>

- <span data-ttu-id="8345c-p116">電子メールとドキュメントのどちらかまたは両方を**暗号化**します。どのユーザーまたはグループに、どれだけの期間、どのアクションを実行するためのアクセス許可を付与するかを選択できます。たとえば、組織外の特定のドメイン内のユーザーに、コンテンツにラベルを付けてから 7 日間のみコンテンツをレビューするためのアクセス許可を付与することができます。詳しくは、「[機密ラベルの暗号化を使用してコンテンツへのアクセスを制限する](encryption-sensitivity-labels.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8345c-p116">**Encrypt** email only or both email and documents. You can choose which users or group have permissions to perform which actions and for how long. For example, you can choose to allow users in a specific domain outside your organization to have permissions to review the content for only 7 days after the content is labeled.</span></span>

- <span data-ttu-id="8345c-p117">ラベルが適用された電子メールまたはドキュメントに、ユーザー設定の透かし、ヘッダー、またはフッターを追加して、**コンテンツにマークを付けます**。透かしを適用できるのはドキュメントのみで、電子メールには使用できません。透かしで使用できる文字数は、255 文字までです。また、ヘッダーとフッターに使用できる文字数は 1024 文字までとなります (Excel で使用できるのは 255 文字までとなり、ドキュメントにヘッダーやフッター、あるいは他の要因が含まれているかによって、使用できる文字数が異なります)。</span><span class="sxs-lookup"><span data-stu-id="8345c-p117">**Mark the content** by adding custom watermarks, headers, or footers to email or documents that have the label applied. Note that watermarks are applied only to documents, not email, and they're limited to 255 characters. Also, headers and footers are limited to 1024 characters (except in Excel, where they're limited to 255 characters or fewer, depending on whether the document contains other headers or footers and other factors.)</span></span>

    ![ドキュメントに適用されたヘッダーと透かし](media/Sensitivity_label_watermark_header.png)

- <span data-ttu-id="8345c-p118">Intune の Endpoint Protection を有効にすることで、**データ損失を防止します**。機密コンテンツがダウンロードされたときに、Windows デバイスからのデータ損失防止に利用できます。たとえば、ラベルが付けられたコンテンツは Dropbox、Gmail、または USB ドライブにコピーできなくなります。機密ラベルで Windows 情報保護 (WIP) が使用できるようになるまでは、最初に Azure portal でアプリ保護ポリシーを作成する必要があります。詳細については、「[Windows 情報保護で機密ラベル付きのファイルを保護する方法](https://docs.microsoft.com/en-us/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8345c-p118">**Prevent data loss** by turning on endpoint protection in Intune. If sensitive content gets downloaded, you can help prevent the loss of data from Windows devices. For example, you can’t copy labeled content into Dropbox, Gmail, or USB drive. Before your sensitivity labels can use Windows Information Protection (WIP), you first need to create an app protection policy in the Azure portal. For more information, see [How Windows Information Protection protects files with a sensitivity label](https://docs.microsoft.com/en-us/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553).</span></span>

<span data-ttu-id="8345c-163">これらすべてのオプションは、セキュリティ/コンプライアンス センターでラベルを作成した場合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-163">All of these options are available when you create a label in the Security & Compliance Center.</span></span>

![機密ラベルの作成時のオプション](media/Sensitivity_label_create_options.png)

### <a name="label-priority-order-matters"></a><span data-ttu-id="8345c-165">ラベルの優先度 (順序の問題)</span><span class="sxs-lookup"><span data-stu-id="8345c-165">Label priority (order matters)</span></span>

<span data-ttu-id="8345c-p119">セキュリティ/コンプライアンス センターで機密ラベルを作成すると、そのラベルは **[ラベル]** ページの **[機密]** タブに一覧表示されます。この一覧では、ラベルの順序が重要になります。その理由は、この順序がラベルの優先度を反映しているからです。最も制限の厳しい機密ラベル (「極秘」など) は一覧の**末尾**に表示されるようにして、制限の緩い機密ラベルは一覧の**先頭**に表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="8345c-p119">When you create your sensitivity labels in the Security & Compliance Center, they appear in a list on the **Sensitivity** tab on the **Labels** page. In this list, the order of the labels is important because it reflects their priority. You want your most restrictive sensitivity label, such as Highly Confidential, to appear at the **bottom** of the list, and your least restrictive sensitivity label, such as Public, to appear at the **top**.</span></span>

<span data-ttu-id="8345c-p120">ドキュメントや電子メールには、1 つの機密ラベルのみを適用できます。ラベルの分類を低く変更する場合の正当性を示すようにユーザーに要求す必要がある場合は、この一覧の順序によって、より低い分類を判断します。</span><span class="sxs-lookup"><span data-stu-id="8345c-p120">A document or email can have only a single sensitivity label applied to it. If you require your users to provide a justification for changing the label to a lower classification, the order of this list determines what's a lower classification.</span></span>

![サブラベルを作成するためのオプション](media/Sensitivity_label_sublabel_options.png)

### <a name="sublabels-grouping-labels"></a><span data-ttu-id="8345c-172">サブラベル (ラベルのグループ化)</span><span class="sxs-lookup"><span data-stu-id="8345c-172">Sublabels (grouping labels)</span></span>

<span data-ttu-id="8345c-p121">サブラベルを使用すると、Office アプリのヘッダーの下側でユーザーに表示される 1 つ以上のラベルをグループ化できます。たとえば、「社外秘」について、組織では、その分類の特定の種類ごとに複数の異なるラベルを使用できます。この例では、ラベル「社外秘」は保護設定のない単なるテキスト ラベルであり、サブラベルが存在するラベルのため、コンテンツに適用することができません。その代わりに、ユーザーが「社外秘」を選択してからサブラベルを表示して、コンテンツに適用するサブラベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p121">With sublabels, you can group one or more labels below a header that a user sees in an Office app. For example, under Confidential, your organization might use several different labels for specific types of that classification. In this example, the label Confidential is simply a text label with no protection settings, and because it has sublabels, it can’t be applied to content. Instead, users must choose Confidential to view the sublabels, and then they can choose a sublabel to apply to content.</span></span>

<span data-ttu-id="8345c-p122">サブラベルは、ユーザーに論的なグループでラベルを提示する簡単な方法です。サブラベルは、そのサブラベルの上位のラベルから設定を継承することはありません。</span><span class="sxs-lookup"><span data-stu-id="8345c-p122">Sublabels are simply a way to present labels to users in logical groups. Sublabels don’t inherit any settings from the label they’re under.</span></span>

![リボンでグループ化されたサブラベル](media/Sensitivity_label_grouped_labels.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a><span data-ttu-id="8345c-180">機密ラベルの編集または削除</span><span class="sxs-lookup"><span data-stu-id="8345c-180">Editing or deleting a sensitivity label</span></span>

<span data-ttu-id="8345c-181">セキュリティ/コンプライアンス センターで機密ラベルを削除しても、そのラベルがコンテンツから削除されることはなく、コンテンツに対する保護設定の強制適用が継続される点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8345c-181">If you delete a sensitivity label in the Security & Compliance Center, note that the label is not removed from content, and any protection settings continue to be enforced on the content.</span></span>

<span data-ttu-id="8345c-182">セキュリティ/コンプライアンス センターで機密ラベルを編集した場合は、コンテンツに適用されていたラベルのバージョンが、そのコンテンツに強制適用される内容になります。</span><span class="sxs-lookup"><span data-stu-id="8345c-182">If you edit a sensitivity label in the Security & Compliance Center, the version of the label that was applied to content is what’s enforced on that content.</span></span>

## <a name="what-label-policies-can-do"></a><span data-ttu-id="8345c-183">ラベル ポリシーでできること</span><span class="sxs-lookup"><span data-stu-id="8345c-183">What label policies can do</span></span>

<span data-ttu-id="8345c-p123">機密ラベルの作成後には、その機密ラベルを発行し、組織内のユーザーが機密ラベルを選択してコンテンツに適用できるようにする必要があります。すべての Exchange メールボックスなどの場所に発行される保持ラベルとは異なり、機密ラベルはユーザーやグループに発行されます。発行後に、機密ラベルは該当するユーザーとグループの Office アプリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p123">After you create your sensitivity labels, you need to publish them, to make them available to people in your organization, who can then apply the labels to content. Unlike retention labels, which are published to locations, such as all Exchange mailboxes, sensitivity labels are published to users or groups. Sensitivity labels then appear in Office apps for those users and groups.</span></span>

<span data-ttu-id="8345c-187">ラベル ポリシーを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="8345c-187">With a label policy, you can:</span></span>

- <span data-ttu-id="8345c-p124">**ラベルが表示されるユーザーとグループを選択します。** ラベルは、電子メールが有効なセキュリティ グループ、配布グループ、Office 365 グループ、または動的配布グループに発行できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p124">**Choose which users and groups see the labels.** Labels can be published to any email-enabled security group, distribution group, Office 365 group, or dynamic distribution group.</span></span>

- <span data-ttu-id="8345c-p125">ラベル ポリシーに含まれているユーザーとグループが作成したすべての新しいドキュメントと電子メールに**既定のラベルを適用します**。この既定のラベルにより、すべてのコンテンツに適用する保護設定の基本レベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p125">**Apply a default label** to all new documents and email created by the users and groups included in the label policy. This default label can set a base level of protection settings that you want applied to all your content.</span></span>

- <span data-ttu-id="8345c-p126">**ラベルの変更に対する正当性を要求します。** コンテンツに「社外秘」のマークが付けられているときに、そのラベルをユーザーが削除しようとした場合や低い分類 (ラベル名「公開」など) に置き換えようとした場合は、そのアクションの実行時に、ユーザーに正当性を提示するように要求できます。こうした正当性は、管理者が確認するために利用できます。Microsoft では、現在、管理者がユーザーの正当性を確認できるレポートの開発を進めています。</span><span class="sxs-lookup"><span data-stu-id="8345c-p126">**Require a justification for changing a label.** If content is marked Confidential and a user wants to remove that label or replace it with a lower classification, such as a label named Public, you can require that the user provide a justification when performing this action. These justifications will be available for the admin to review. We’re currently working on a report where admins can view the user justifications.</span></span>

    ![ユーザーに正当性を入力するように求めるダイアログ](media/Sensitivity_label_justification_required.png)

- <span data-ttu-id="8345c-p127">**カスタムのヘルプ ページへのヘルプ リンクを提示します。** ユーザーが機密ラベルの意味や使用方法について明確に理解できない場合に、Office アプリの機密ラベル メニューの末尾に表示される詳細な説明の URL を提供できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p127">**Provide help link to a custom help page.** If your users aren’t sure what your sensitivity labels mean or how they should be used, you can provide a Learn More URL that appears at the bottom of the Sensitivity label menu in the Office apps.</span></span>

    ![リボンの [機密] ボタンに示された詳細な説明のリンク](media/Sensitivity_label_learn_more.png)

<span data-ttu-id="8345c-200">ラベル ポリシーを作成して、ユーザーおよびグループに機密ラベルを割り当てると、そのユーザーおよびグループは、1 時間以内に Office アプリで使用できるラベルを確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8345c-200">After you create a label policy and assign sensitivity labels to users and groups, those people will see those labels available in the Office apps in an hour or less.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="8345c-201">始める方法</span><span class="sxs-lookup"><span data-stu-id="8345c-201">How to get started</span></span>

<span data-ttu-id="8345c-202">機密ラベルの使用は、簡単なプロセスで開始できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-202">Getting started with sensitivity labels is a quick process:</span></span>

1. <span data-ttu-id="8345c-p128">**ラベルを定義します。** まず、さまざまなレベルの機密コンテンツを定義するための分類を規定します。ユーザーが理解できるような、一般的な名前または用語を使用してください。たとえば、最初は「個人」、「公開」、「一般」、「社外秘」、「極秘」などのラベルを使用します。サブラベルを使用すると、同様のラベルをカテゴリごとにグループ化できます。また、ラベルの作成時には、ツール ヒントも必要になります。このツール ヒントは、ユーザーがリボンに示されるラベル オプションにポインターを重ねたときに Office アプリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p128">**Define the labels.** First, you want to establish your taxonomy for defining different levels of sensitive content. You should use common names or terms that make sense to your users. For example, you can start with labels such as Personal, Public, General, Confidential, and Highly Confidential. You can use sublabels to group similar labels by category. Also, when you create a label, a tool tip is required, which appears in the Office apps when a user hovers over a label option on the Ribbon.</span></span>

1. <span data-ttu-id="8345c-p129">**各ラベルで可能にすることを定義します。** 次に、各ラベルに関連付ける保護設定を定義します。たとえば、緩い機密コンテンツ (「一般」ラベル) には単にヘッダーやフッターを適用し、厳格な機密コンテンツ (「社外秘」ラベル) には透かし、暗号化、および WIP を適用します。これは、特権があるユーザーのみが機密コンテンツにアクセスできるようにするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p129">**Define what each label can do.** Then, configure the protection settings you want associated with each label. For example, lower sensitivity content (a “General” label) might simply have a header or footer applied to it, while higher sensitivity content (a “Confidential” label) may have a watermark, encryption, and WIP applied to it, to help ensure that only privileged users can access it.</span></span>
 
1. <span data-ttu-id="8345c-p130">**ラベルの対象になるユーザーを定義します。** 組織のラベルを定義したら、そのラベルをラベル ポリシーで発行します。このポリシーによって、どのユーザーおよびグループにラベルを表示するかを制御します。1 つのラベルを再使用できるため、一度定義したラベルは、さまざまなユーザーに割り当てる複数のラベル ポリシーに含めることができます。ただし、コンテンツにラベルを割り当てるには、まず、そのラベルを発行して Office アプリなどのサービスで使用できるようにしておく必要があります。開始したばかりのときには、少数のユーザーに機密ラベルを割り当てて試験運用してください。</span><span class="sxs-lookup"><span data-stu-id="8345c-p130">**Define who gets the labels.** After you define your organization’s labels, you publish them in a label policy that controls which users and groups see those labels. A single label is reusable – you define it once, and then you can include it in several label policies assigned to different users. But in order for a label to be assigned to content, you must first publish that label so that it’s available in Office apps and other services. When just starting out, you can pilot your sensitivity labels by assigning them to just a few people.</span></span>

<span data-ttu-id="8345c-217">機密ラベルが機能するために、管理者、ユーザー、Office アプリが実行する内容の基本的なフローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8345c-217">Here’s the basic flow of what the admin, user, and Office app do to make sensitivity labels work.</span></span>

![機密ラベルのワークフローを示す図](media/Sensitivity_label_flow.png)

## <a name="where-sensitivity-labels-can-appear"></a><span data-ttu-id="8345c-219">機密ラベルを表示できる場所</span><span class="sxs-lookup"><span data-stu-id="8345c-219">Where sensitivity labels can appear</span></span>

<span data-ttu-id="8345c-p131">機密ラベルは、Office アプリの UI に表示されます。現時点で利用可能な具体的なアプリとプラットフォームを確認するには、「**[現在、機能はどこで入手できますか?](https://support.office.com/ja-JP/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9?ad=US&ui=en-US&rs=en-US#bkmk_whereavailable)**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8345c-p131">Sensitivity labels appear in the UI of Office apps. To view the current availability for specific apps and platforms, see **[Where is the feature available today?](https://support.office.com/ja-JP/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9?ad=US&ui=en-US&rs=en-US#bkmk_whereavailable)**</span></span>

### <a name="office-apps-on-windows"></a><span data-ttu-id="8345c-222">Windows 上の Office アプリ</span><span class="sxs-lookup"><span data-stu-id="8345c-222">Office apps on Windows</span></span>

<span data-ttu-id="8345c-p132">Windows を実行するデバイス上の Office アプリでは、機密ラベルはリボンの **[ホーム]** タブにある **[機密]** ボタンに表示されます。適用されているラベルは、ウィンドウの下側にあるステータス バーにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p132">In Office apps on devices running Windows, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

<span data-ttu-id="8345c-225">Windows 上の Office アプリの機密ラベルは、近日中にネイティブ サポートされます。</span><span class="sxs-lookup"><span data-stu-id="8345c-225">Coming soon is native support for sensitivity labels in Office apps on Windows.</span></span>

<span data-ttu-id="8345c-p133">既に Azure Information Protection を使用しているお客様は、機密ラベルをサポートしている Azure Information Protection 統合ラベル付けクライアントを近日中に展開できるようになります。クライアントのダウンロードの詳細については「[Azure Information Protection 統合ラベル付けクライアント: バージョン リリース情報](https://docs.microsoft.com/ja-JP/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)」を参照してください。現在、Windows 上の Office アプリの機密ラベルに対するネイティブ サポートが開発中であり、今後は Azure Information Protection 統合ラベル付けクライアントは不要になります。</span><span class="sxs-lookup"><span data-stu-id="8345c-p133">If you're an existing Azure Information Protection customer, you can deploy the Azure Information Protection unified labeling client, which supports sensitivity labels. For more information about downloading the client, see [Azure Information Protection unified labeling client: Version release information](https://docs.microsoft.com/ja-JP/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history). We’re currently working on native support for sensitivity labels in Office apps on Windows, so that the Azure Information Protection unified labeling client will no longer be required.</span></span>

![Windows の Excel のリボンに示された [機密] ボタン](media/Sensitivity_label_Sensitivity_button.png)

### <a name="office-apps-on-mac"></a><span data-ttu-id="8345c-230">Mac 上の Office アプリ</span><span class="sxs-lookup"><span data-stu-id="8345c-230">Office apps on Mac</span></span>

<span data-ttu-id="8345c-p134">Mac デバイス上の Office アプリでは、機密ラベルはリボンの **[ホーム]** タブにある **[機密]** タブに表示されます。適用されているラベルは、ウィンドウの下側にあるステータス バーにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p134">In Office apps on Mac devices, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

![Mac 上の Office のリボンに示された [機密] ボタン](media/Sensitivity_label_on_Mac.png)

### <a name="office-apps-on-ios"></a><span data-ttu-id="8345c-234">iOS 上の Office アプリ</span><span class="sxs-lookup"><span data-stu-id="8345c-234">Office apps on iOS</span></span>

<span data-ttu-id="8345c-p135">iOS デバイス上の Office アプリでは、機密ラベルはリボンの **[ホーム]** タブにある **[機密]** ボタンに表示されます。適用されているラベルは、ウィンドウの下側にあるステータス バーにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p135">In Office apps on iOS devices, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

![iOS 上の Office のリボンに示された [機密] ボタン](media/Sensitivity_label_on_iOS.png)

### <a name="office-apps-on-android"></a><span data-ttu-id="8345c-238">Android 上の Office アプリ</span><span class="sxs-lookup"><span data-stu-id="8345c-238">Office apps on Android</span></span>

<span data-ttu-id="8345c-p136">Android デバイス上の Office アプリでは、機密ラベルはリボンの **[ホーム]** タブにある **[機密]** タブに表示されます。適用されているラベルは、ウィンドウの下側にあるステータス バーにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p136">In Office apps on Android devices, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

![Android 上の Office のリボンに示された [機密] ボタン](media/Sensitivity_label_on_Android.png)

### <a name="more-information-on-sensitivity-labels-in-office-apps"></a><span data-ttu-id="8345c-242">Office アプリの機密ラベルに関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="8345c-242">More information on sensitivity labels in Office apps</span></span>

- [<span data-ttu-id="8345c-243">Office 内の文書やメールに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="8345c-243">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/ja-JP/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
- [<span data-ttu-id="8345c-244">Office ファイルに機密ラベルを適用した場合の既知の問題</span><span class="sxs-lookup"><span data-stu-id="8345c-244">Known issues when you apply sensitivity labels to your Office files</span></span>](https://support.office.com/ja-JP/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)

## <a name="how-sensitivity-labels-work-with-existing-azure-information-protection-labels"></a><span data-ttu-id="8345c-245">機密ラベルが既存の Azure Information Protection ラベルと連動する方法</span><span class="sxs-lookup"><span data-stu-id="8345c-245">How sensitivity labels work with existing Azure Information Protection labels</span></span>

<span data-ttu-id="8345c-p137">Azure Information Protection のユーザーは、現在、Azure Information Protection 統合ラベル付けクライアントを使用することで、コンテンツの分類とラベル付けを実行できます。既存の Azure Information Protection ラベルは、新しい機密ラベルとシームレスに連動します。そのため、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p137">Azure Information Protection users are currently able to classify and label content on Windows by using the Azure Information Protection unified labeling client. Existing Azure Information Protection labels work seamlessly with new sensitivity labels. This means you can:</span></span>

- <span data-ttu-id="8345c-249">既存の Azure Information Protection ラベルをドキュメントと電子メールに保持する。</span><span class="sxs-lookup"><span data-stu-id="8345c-249">Keep your existing Azure Information Protection labels on documents and email.</span></span>
- <span data-ttu-id="8345c-250">既存の Azure Information Protection ラベル構成を保持する。</span><span class="sxs-lookup"><span data-stu-id="8345c-250">Keep your existing Azure Information Protection label configuration.</span></span>

<span data-ttu-id="8345c-p138">Azure Information Protection ラベルを使用している場合、今のところは移行が完了するまで、セキュリティ/コンプライアンス センターで新しいラベルを作成しないようにしてください。[Azure Information Protection の移行に関するトピック](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-policy-migrate-labels)には、重要な情報と補足説明が記載されています。実稼働テナントの機密ラベルへの移行準備が整っていない場合、懸念事項はありません。当分の間、ユーザーは引き続き Azure Information Protection クライアントを使用できます。また、管理者は引き続き管理に Azure portal を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p138">If you are using Azure Information Protection labels, for now we recommend that you avoid creating new labels in Security & Compliance Center until after you’ve completed your migration. The [Azure Information Protection migration topic](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-policy-migrate-labels) has important information and some specific caveats. If you are not yet ready to migrate your production tenants to sensitivity labels, there is no cause for concern: for the moment, your users can continue using the Azure Information Protection client, and admins can continue using the Azure portal for management.</span></span>

## <a name="protect-content-on-windows-devices-by-using-endpoint-protection-in-microsoft-intune"></a><span data-ttu-id="8345c-254">Microsoft Intune の Endpoint Protection を使用して Windows デバイス上のコンテンツを保護する</span><span class="sxs-lookup"><span data-stu-id="8345c-254">Protect content on Windows devices by using endpoint protection in Microsoft Intune</span></span>

<span data-ttu-id="8345c-p139">機密ラベルの作成時には、このラベルの付いたファイルは機密であり、Windows デバイスに保存する際にはデータ漏えいに対する保護が必要であることを Windows に通知するオプションを選択できます。このオプションを使用することで、このラベルが付いたコンテンツは、エンドポイントに保存されていたとしても、許可された場所でのみ共有およびコピーを許可することが可能になります。実質的に、このオプションを機密ラベルに対して有効にすることで、このデータは追加の使用制限が必要になる非常に重要なデータであることを Windows に通知します。</span><span class="sxs-lookup"><span data-stu-id="8345c-p139">When you create a sensitivity label, you have the option to tell Windows that files with this label are sensitive and need to be protected against data leakage when stored on Windows devices. This option can help ensure that content with this label can be shared or copied only to sanctioned locations, even when it’s stored on an endpoint. In essence, turning on this option for a sensitivity label tells Windows that this is extra critical data that warrants additional usage constraints.</span></span>

<span data-ttu-id="8345c-p140">このオプションを有効にすると、Windows はドキュメントの機密ラベルを読み取って、認識し、対処できるようになり、コンテンツに対して自動的に Windows 情報保護 (WIP) を適用します。そのコンテンツがマネージ Windows デバイスにどのように送られたかは関係ありません。これにより、暗号化適用の有無にかかわらず、ラベルが付けられたファイルの不用意な漏えいを防止できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8345c-p140">When you turn on this option, Windows can read, understand, and act on sensitivity labels in documents and automatically apply Windows Information Protection (WIP) on content, no matter how it reaches a managed Windows device. This helps protect labeled files from accidental leakage, with or without applying encryption.</span></span>

<span data-ttu-id="8345c-260">たとえば、Windows はユーザーのマシンに存在する Word 文書に「社外秘」ラベルが適用されていることを認識して、そのデバイスから業務に関係ない場所 (個人用 OneDrive、個人用電子メール アカウント、ソーシャル メディア、USB ドライブなど) にデータがコピーまたは共有されることを防止するために WIP を適用できます。</span><span class="sxs-lookup"><span data-stu-id="8345c-260">For example, Windows can understand that a Word document residing on a user’s machine has a Confidential label applied to it, and WIP can apply an app protection policy to prevent the copying or sharing of the data to any non-work location from that device (such as a personal ONeDrive, personal email accounts, social media, or USB drives).</span></span>

<span data-ttu-id="8345c-261">ユーザーがラベル付きのコンテンツを個人用の Gmail アカウントにアップロードしようとすると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8345c-261">If a user attempts to upload labeled content to a personal Gmail account, they see this message.</span></span>

![ラベル付きのコンテンツは Gmail にコピーできないことを示すメッセージ](media/Sensitivity_label_WIP_Gmail.png)

<span data-ttu-id="8345c-263">また、ユーザーがラベル付きのコンテンツを USB ドライブに保存しようとすると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8345c-263">And if a user attempts to save labeled content to a USB drive, they see this message.</span></span>

![ラベル付きのコンテンツは USB ドライブにコピーできないことを示すメッセージ](media/Sensitivity_label_WIP_USB_drive.png)

### <a name="important-prerequisites"></a><span data-ttu-id="8345c-265">重要な前提条件</span><span class="sxs-lookup"><span data-stu-id="8345c-265">Important prerequisites</span></span>

<span data-ttu-id="8345c-p141">機密ラベルで WIP が使用できるようにするには、まず、「[Windows 情報保護で機密ラベル付きのファイルを保護する方法](https://docs.microsoft.com/en-us/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)」で説明する前提条件を満たしておく必要があります。このトピックには、次の前提条件についての説明があります。</span><span class="sxs-lookup"><span data-stu-id="8345c-p141">Before your sensitivity labels can use WIP, you first need to do the prerequisites described here: [How Windows Information Protection protects files with a sensitivity label](https://docs.microsoft.com/en-us/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553). This topic describes the following prerequisites:</span></span>

- <span data-ttu-id="8345c-268">Windows 10 バージョン 1809 以降を実行していることを確認する。</span><span class="sxs-lookup"><span data-stu-id="8345c-268">Make sure you're running Windows 10, version 1809 or later.</span></span>
- <span data-ttu-id="8345c-p142">[Windows Defender Advanced Threat Protection (WDATP) をセットアップする。](https://docs.microsoft.com/ja-JP/windows/security/threat-protection/windows-defender-atp/get-started)これにより、ラベルについてコンテンツがスキャンされ、それに対応する WIP 保護が適用されます。ATP は、いくつかのアクション (異常の報告など) を WIP とは無関係に実行します。</span><span class="sxs-lookup"><span data-stu-id="8345c-p142">[Set up Windows Defender Advanced Threat Protection (WDATP)](https://docs.microsoft.com/ja-JP/windows/security/threat-protection/windows-defender-atp/get-started), which scans content for a label and applies the corresponding WIP protection. ATP performs some actions independently from WIP, such as reporting anomalies.</span></span>
- <span data-ttu-id="8345c-p143">エンドポイント デバイスに適用する Windows 情報保護 (WIP) ポリシーを作成する。次のいずれかの方法で作成することができます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p143">Create a Windows Information Protection (WIP) policy that applies to endpoint devices. You can do this in either of these locations:</span></span>
    - [<span data-ttu-id="8345c-273">Microsoft Intune の Azure portal を使用して MDM で Windows 情報保護 (WIP) ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="8345c-273">Create a Windows Information Protection (WIP) policy with MDM using the Azure portal for Microsoft Intune</span></span>](https://docs.microsoft.com/ja-JP/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)
    - [<span data-ttu-id="8345c-274">System Center Configuration Manager を使用した Windows 情報保護 (WIP) ポリシーの作成と展開</span><span class="sxs-lookup"><span data-stu-id="8345c-274">Create and deploy a Windows Information Protection (WIP) policy using System Center Configuration Manager</span></span>](https://docs.microsoft.com/ja-JP/windows/security/information-protection/windows-information-protection/create-wip-policy-using-sccm)

## <a name="extend-sensitivity-labels-to-third-party-apps-and-services-by-using-the-microsoft-information-protection-sdk"></a><span data-ttu-id="8345c-275">Microsoft Information Protection SDK を使用して機密ラベルをサード パーティ製アプリおよびサービスに拡張する</span><span class="sxs-lookup"><span data-stu-id="8345c-275">Extend sensitivity labels to third-party apps and services by using the Microsoft Information Protection SDK</span></span>

<span data-ttu-id="8345c-p144">機密ラベルはクリア テキストとしてドキュメントのメタデータ内に存在するため、そうしたラベルを含むコンテンツの識別と保護をサード パーティ製アプリとサービスでサポートすることもできます。その他のアプリとサービスでのサポートは常に拡張中です。</span><span class="sxs-lookup"><span data-stu-id="8345c-p144">Because a sensitivity label is persisted as clear text in the metadata of a document, third-party apps and services can choose to support identifying and protecting content that contains such a label. Support in other apps and services is always expanding.</span></span>

<span data-ttu-id="8345c-p145">[Microsoft Information Protection SDK](https://docs.microsoft.com/ja-JP/information-protection/develop/) を使用すると、サード パーティ製アプリおよびサービスで機密ラベルの読み取りおよび適用が可能になり、ドキュメントを保護できるようになります。近日中には、iOS および Android もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8345c-p145">With the [Microsoft Information Protection SDK](https://docs.microsoft.com/ja-JP/information-protection/develop/), third-party apps and services can read and apply sensitivity labels and protection to documents. The SDK supports apps on Windows, Mac, and Linux. Coming soon is support for apps on iOS and Android.</span></span>

<span data-ttu-id="8345c-p146">この SDK を使用することで、その他の Microsoft 情報保護アプリおよびサービス (Office アプリ、Office 365 サービス、Azure Information Protection スキャナー、Microsoft Cloud App Security などと、その他いくつかのパートナーのソリューション) での操作方法でコンテンツのラベル付けと保護が可能になります。その例として、[Adobe Acrobat での機密ラベルのサポート](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Starting-October-use-Adobe-Acrobat-Reader-for-PDFs-protected-by/ba-p/262738)について調べてください。</span><span class="sxs-lookup"><span data-stu-id="8345c-p146">Using the SDK, you can label and protect content in a way that works with other Microsoft Information Protection apps and services, such as Office apps, Office 365 services, the Azure Information Protection scanner, Microsoft Cloud App Security, and several other partner solutions. For example, learn more about [support for sensitivity labels in Adobe Acrobat](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Starting-October-use-Adobe-Acrobat-Reader-for-PDFs-protected-by/ba-p/262738).</span></span>

<span data-ttu-id="8345c-p147">Microsoft Information Protection SDK の詳細については、[Tech Community ブログでのお知らせ](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144)を参照してください。また、[Microsoft 情報保護に統合されているパートナー ソリューション](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657)についても調べてください。</span><span class="sxs-lookup"><span data-stu-id="8345c-p147">To learn more about the Microsoft Information Protection SDK, see the [announcement on the Tech Community blog](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144). You can also learn about [partner solutions that are integrated with Microsoft Information Protection](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657).</span></span>

## <a name="permissions"></a><span data-ttu-id="8345c-285">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="8345c-285">Permissions</span></span>

<span data-ttu-id="8345c-p148">機密ラベルを作成するコンプライアンス チームのメンバーには、セキュリティ/コンプライアンス センターへのアクセス許可が必要です。既定では、テナント管理者はこの場所へのアクセス許可を持っています。そのため、法令遵守責任者や他のユーザーに対し、テナント管理者のすべてのアクセス許可を付与せずに、セキュリティ/コンプライアンス センターへのアクセスを許可できます。これを行うには、セキュリティ/コンプライアンス センターの **[アクセス許可]** ページに移動して、**[コンプライアンス管理者]** 役割グループを編集し、メンバーをその役割グループに追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8345c-p148">Members of your compliance team who will create sensitivity labels need permissions to the Security & Compliance Center. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security & Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security & Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span>

<span data-ttu-id="8345c-288">詳細については、「ユーザーに Office 365 セキュリティ/コンプライアンス センターへのアクセス権を付与する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8345c-288">For more information, see Give users access to the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="8345c-p149">ラベルとラベル ポリシーを作成して適用するときにのみ、これらのアクセス許可が必要になります。ポリシーを適用する場合に、コンテンツへのアクセスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8345c-p149">These permissions are required only to create and apply labels and a label policy. Policy enforcement does not require access to the content.</span></span>
