---
title: 機密ラベルをコンテンツに自動的に適用する
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: 機密ラベルを作成する場合、ドキュメントまたは電子メールにラベルを自動的に割り当てるか、あるいは推奨するラベルを選択するようにユーザーに求めることができます。
ms.openlocfilehash: 8464847704b5e724b97b4af9b51397f2985311a8
ms.sourcegitcommit: d05a9937780d210b7ad48e721b947397ac5405a2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29610584"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="abeb2-103">機密ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="abeb2-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="abeb2-104">機密ラベルを作成する場合、機密情報を含むコンテンツにそのラベルを自動的に割り当てるか、あるいは推奨するラベルを適用するようにユーザーに求めることができます。</span><span class="sxs-lookup"><span data-stu-id="abeb2-104">When you create a sensitivity label, you can automatically assign that label to content containing sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="abeb2-105">機密ラベルを自動的にコンテンツに適用する機能が重要である理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="abeb2-105">The ability to apply labels to content automatically is important because:</span></span>

- <span data-ttu-id="abeb2-106">ユーザーのトレーニングは、一部の分類方法についてのみ必要。</span><span class="sxs-lookup"><span data-stu-id="abeb2-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="abeb2-107">ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="abeb2-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="abeb2-108">ユーザーはポリシーについて把握する必要がなくなり、自分たちの仕事に集中できる。</span><span class="sxs-lookup"><span data-stu-id="abeb2-108">Users no longer need to know about data governance policies - they can instead focus on their work.</span></span>

> [!NOTE]
> <span data-ttu-id="abeb2-p101">ラベルを自動的に適用する機能では、Azure Information Protection P2 サブスクリプションが必要になります。この機能を使用するには、[Azure Information Protection 統合ラベル付けクライアントをダウンロードしてインストールする](https://docs.microsoft.com/ja-JP/azure/information-protection/rms-client/install-unifiedlabelingclient-app)必要があります。Azure Information Protection 統合ラベル付けクライアントが不要になるように、Office アプリのこの機能のネイティブ サポートに取り組んでいます。また、統合ラベル付けクライアントは、Windows 上でのみ実行されるため、この機能は、Mac、iOS、Android ではまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="abeb2-p101">The capability to apply labels automatically requires an Azure Information Protection P2 subscription. To use this feature, you must [Download and install the Azure Information Protection unified labeling client](https://docs.microsoft.com/ja-JP/azure/information-protection/rms-client/install-unifiedlabelingclient-app). We're working on native support for this feature in Office apps, so that it won't require the Azure Information Protection unified labeling client. Also, the unified labeling client runs only on Windows, so this feature is not yet supported on Mac, iOS, and Android.</span></span>

![機密ラベルの自動ラベル付けオプション](media/Sensitivity_labels_Auto_labeling_options.png)

# <a name="apply-a-sensitivity-label-automatically-based-on-conditions"></a><span data-ttu-id="abeb2-114">条件に基づいた機密ラベルの自動適用</span><span class="sxs-lookup"><span data-stu-id="abeb2-114">Applying a label automatically based on conditions</span></span>

<span data-ttu-id="abeb2-p102">機密ラベルの最も強力な機能の 1 つは、特定の条件に一致したコンテンツにラベルを自動的に適用する機能です。この場合、機密ラベルは Office 365 によって適用されるため、組織内のユーザーがラベルを適用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="abeb2-p102">One of the most powerful features of labels is the ability to apply them automatically to content that matches certain conditions. In this case, people in your organization don't need to apply the labels - Office 365 does the work for them.</span></span>
   
<span data-ttu-id="abeb2-p103">コンテンツに特定の種類の機密情報が含まれている場合、そのコンテンツに機密ラベルを自動的に適用することを選択できます。機密ラベルを自動的に適用するように構成すると、データ損失防止 (DLP) ポリシーを作成する場合と同じ機密情報の種類のリストが表示されます。たとえば、クレジット カード番号や社会保障番号などの顧客の個人情報 (PII) が含まれるすべてのコンテンツに高機密ラベルを自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="abeb2-p103">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information. When you configure a sensitivity label to be applied automatically, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy. So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers.</span></span> 

![インスタンス数と一致精度のオプション](media/Sensitivity_labels_instance_count_match_accuracy.png)

<span data-ttu-id="abeb2-p104">機密情報の種類を選択した後は、インスタンス数または一致精度を変更して条件を絞り込むことができます。詳細については、「[一致の難易度を設定するためのルールの調整](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abeb2-p104">After you choose your sensitive informaton types, you can refine your condition by changing the instance count or match accuracy. For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="abeb2-p105">さらに、条件で検知する必要があるのは、機密情報の種類のすべてか、またはそのうちの 1 つだけかを選択できます。また、条件をより柔軟または複雑にするには、グループを追加し、グループ間で論理演算子を使用できます。詳細については、「[グループ化および論理演算子](data-loss-prevention-policies.md#grouping-and-logical-operators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abeb2-p105">Further, you can choose whether a condition must detect all of the sensitive infromation types, or just one of them. And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups. For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

<span data-ttu-id="abeb2-p106">機密ラベルが自動的に適用されると、ユーザーの Office アプリに通知が表示されます。**[OK]** をクリックして通知を閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="abeb2-p106">When a sensitivity label is automatically applied, the user sees a notification in their Office app. They can choose **OK** to dismiss the notification.</span></span>

![ドキュメントにラベルが自動適用されたという通知](media/sensitivity_labels_msg_doc_was_auto_labeled.PNG)

# <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="abeb2-129">ユーザーが機密ラベルを適用することを推奨</span><span class="sxs-lookup"><span data-stu-id="abeb2-129">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="abeb2-p107">状況に応じて、機密ラベルをコンテンツに自動的に適用する代わりに、ユーザーがラベルを適用することを推奨できます。このオプションでは、分類および関連する保護を受け入れるか、またはラベルがドキュメントや電子メールに適していない場合、推奨事項を無視するかをユーザーが柔軟に選択できます。</span><span class="sxs-lookup"><span data-stu-id="abeb2-p107">If you prefer, instead of applying a sensitivity label automatically to content, you can recommend to your users that they apply the label. This option provides your users the flexibility of accepting the classification and any associated protection, or dismissing the recommendation if the label is not suitable for their document or email.</span></span>

<span data-ttu-id="abeb2-p108">推奨ラベルは、Word、PowerPoint、Excel でサポートされていますが、Azure Information Protection 統合ラベル付けクライアントがインストールされている必要があることに注意してください。Outlook での推奨ラベルのサポートに取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="abeb2-p108">Note that recommended labels are supported in Word, PowerPoint, and Excel (and require that the Azure Information Proteciton unified labeling client is installed). We're working on support for recommended labels in Outlook.</span></span>

![機密ラベルをユーザーに推奨するためのオプション](media/Sensitivity_labels_Recommended_label_option.png)

<span data-ttu-id="abeb2-p109">ラベルを推奨される操作として適用するように条件を構成したときのプロンプトの例を、カスタム ポリシー ヒントと共に示します。ポリシー ヒントに表示するテキストを選択できます。</span><span class="sxs-lookup"><span data-stu-id="abeb2-p109">Here's an example of a prompt when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![推奨ラベルを適用するためのプロンプト](media/Sensitivity_label_Prompt_for_required_label.png)

# <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="abeb2-138">自動ラベルと推奨ラベルが適用されるしくみ</span><span class="sxs-lookup"><span data-stu-id="abeb2-138">How automatic or recommended labels are applied</span></span>

- <span data-ttu-id="abeb2-p110">自動ラベル付けは、Word、Excel、PowerPoint でドキュメントが保存されるときと、Outlook で電子メールが送信されるときに適用されます。これらの条件により、ドキュメントや電子メール内の本文、およびヘッダーとフッターに含まれる機密情報が検出されますが、件名や電子メールの添付ファイルのものは検知されません。</span><span class="sxs-lookup"><span data-stu-id="abeb2-p110">Automatic labeling applies to Word, Excel, and PowerPoint when documents are saved, and to Outlook when emails are sent. These conditions detect sensitive information in the body text in documents and emails, and to headers and footers -- but not in the subject line or attachments of email.</span></span>

- <span data-ttu-id="abeb2-p111">以前に手動でラベルが付けられているか、以前に上位の分類で自動的にラベルが付けられているドキュメントと電子メールには自動分類を使用できません。ドキュメントや電子メールに適用できる機密ラベルは (1 つの保持ラベルに加えて) 1 つだけであることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="abeb2-p111">You cannot use automatic classification for documents and emails that were previously manually labeled, or previously automatically labeled with a higher classification. Remember, a document or email can have only a single sensitivity label applied to it (in addition to a single retention label).</span></span>

- <span data-ttu-id="abeb2-p112">推奨分類は、Word、Excel、PowerPoint でドキュメントが保存されるときに適用されます。Outlook での推奨ラベルのサポートに取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="abeb2-p112">Recommended classification applies to Word, Excel, and PowerPoint when documents are saved. We're working on support for recommended labeling in Outlook.</span></span>

- <span data-ttu-id="abeb2-p113">以前に上位の分類でラベルが付けられているドキュメントには推奨分類を使用できません。この場合、コンテンツにすでに上位の分類でラベルが付けられていると、推奨事項とポリシー ヒントに関するプロンプトは、ユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="abeb2-p113">You cannot use recommended classification for documents that were previously labeled with a higher classification. In this case, when the content's already labeled with a higher classification, the user won't see the prompt with the recommendation and policy tip.</span></span>

# <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="abeb2-147">複数のラベルに適用するときの複数の条件の評価方法</span><span class="sxs-lookup"><span data-stu-id="abeb2-147">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="abeb2-p114">ラベルは、ポリシー内で指定した位置に従って評価の順序を決められます。先頭に配置したラベルが最下位 (機密性が最も低い) になり、最後に配置したラベルが最上位 (機密性が最も高い) になります。優先度に関する詳細については、「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abeb2-p114">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>