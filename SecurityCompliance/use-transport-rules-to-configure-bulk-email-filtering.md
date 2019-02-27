---
title: メールフロールールを使用して Exchange Online Protection で一括メールフィルターを構成する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection でのメールフロールールをバルクメールフィルターに使用する方法について説明します。
ms.openlocfilehash: b7144f16df3e7b9f90a24f1ac224ccb20287d918
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275687"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a><span data-ttu-id="3562e-103">メールフロールールを使用して Exchange Online Protection で一括メールフィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="3562e-103">Use mail flow rules to configure bulk email filtering in Exchange Online Protection</span></span>

<span data-ttu-id="3562e-p101">既定のスパム コンテンツ フィルター ポリシーを使用して、スパムやバルク メールに対して会社全体のコンテンツ フィルターを設定することができます。コンテンツ フィルター ポリシーを設定する方法については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」と「[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3562e-p101">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies. Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) on how to set the content filter policies.</span></span> 
  
<span data-ttu-id="3562e-p102">バルクメッセージをフィルター処理するためのその他のオプションが必要な場合は、メールフロールール (トランスポートルールとも呼ばれます) を作成して、バルクメールでよく見られるテキストパターンや語句を検索することができます。これらの特性を含むメッセージは、スパムとしてマークされます。これらのルールを使用すると、組織が受信する不要なバルクメールの量を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="3562e-p102">If you want to more options to filter bulk messages, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases frequently found in bulk emails. Any message containing these characteristics will be marked as spam. Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3562e-109">このトピックに記載されているメールフロールールを作成する前に、「[迷惑メールとバルクメールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」および「[バルク苦情レベルの値](bulk-complaint-level-values.md)」を参照することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3562e-109">Before creating the mail flow rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span><br><span data-ttu-id="3562e-p103">以下の手順は、特定のメッセージを組織全体でスパムとしてマークします。ただし、別の条件を追加すれば、これらのルールを組織内の特定の受信者にだけ適用することができます。このように、積極的なバルク メール フィルター処理設定を注目すべき少数のユーザーにだけ適用することによって、他のユーザー (受信するもののほとんどが登録したバルク メール) には影響を与えないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3562e-p103"> The following procedures mark a message as spam for your entire organization. However, you can add another condition to apply these rules only to specific recipients in your organization. This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span> 
  
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="3562e-113">テキストパターンに基づいてバルクメールメッセージをフィルター処理するメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="3562e-113">Create a mail flow rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="3562e-114">Exchange 管理センター (EAC) で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="3562e-114">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="3562e-115">[追加] アイコン](media/ITPro-EAC-AddIcon.gif)をクリックし、[**新しいルールの作成**] を選択します。 \*\*\*\* ![</span><span class="sxs-lookup"><span data-stu-id="3562e-115">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="3562e-116">ルールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3562e-116">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="3562e-p104">**[その他のオプション]** をクリックします。 **[次の場合、このルールを適用する]** で、 **[件名または本文]** \> **[件名または本文が次のテキスト パターンと一致する]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3562e-p104">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>
    
5. <span data-ttu-id="3562e-119">**[単語または文字列の指定]** ダイアログ ボックスで、バルク メールでよく見られる以下の正規表現を一度に 1 つずつ追加して、終わったら **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3562e-119">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - `If you are unable to view the content of this email\, please`
    
   - `\>(safe )?unsubscribe( here)?\</a\>`
    
   - `If you do not wish to receive further communications like this\, please`
    
   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
    
   - `To stop receiving these+emails\:http\://`
    
   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
    
   - `no longer (wish )?(to )?(be sent|receive) w+ email`
    
   - `If you are unable to view the content of this email\, please click here`
    
   - `To ensure you receive (your daily deals|our e-?mails)\, add`
    
   - `If you no longer wish to receive these emails`
    
   - `to change your (subscription preferences|preferences or unsubscribe)`
    
   - `click (here to|the) unsubscribe`
    
   <span data-ttu-id="3562e-p105">上記のリストは、バルクメールで検出された正規表現の完全なセットではありません。必要に応じて、追加または削除することができます。ただし、開始点として適しています。</span><span class="sxs-lookup"><span data-stu-id="3562e-p105">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span><br><span data-ttu-id="3562e-p106">メッセージ内の件名フィールドまたは他のヘッダーフィールドに含まれる単語またはテキストパターンを検索すると、メッセージが ASCII テキスト形式の SMTP サーバー間でバイナリメッセージを送信するために使用された MIME コンテンツ転送エンコード方式からデコードされ*た後*に発生します。条件または例外を使用して、メッセージ内の subject またはその他のヘッダーフィールドの生 (通常は Base64) でエンコードされた値を検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="3562e-p106">The search for words or text patterns in the subject or other header fields in the message occurs  *after*  the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span> 
    
6. <span data-ttu-id="3562e-124">**[実行する処理]** で、 **[メッセージのプロパティを変更する]** \> **[SCL (Spam Confidence Level) の設定]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3562e-124">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="3562e-125">**[SCL の指定]** ダイアログ ボックスで、SCL を **5**、 **6**、または **9** に設定して、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3562e-125">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="3562e-p107">コンテンツ フィルター ポリシーの設定に従って、SCL を 5 または 6 に設定した場合は **スパム**のアクションを行い、SCL を 9 に設定した場合は **信頼度の高いスパム**のアクションを行います。サービスは、コンテンツ フィルター ポリシーで設定されたアクションを実行します。既定のアクションでは、メッセージを受信者の迷惑メール フォルダーに配信しますが、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」に説明するとおり、異なるアクションを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="3562e-p107">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   <span data-ttu-id="3562e-129">メッセージを受信者の迷惑メールフォルダーに送信するのではなく、メッセージを検疫するように構成されている場合は、メッセージはメールフロールールの一致として管理者検疫に送信されますが、エンドユーザーのスパム検疫時またはエンドユーザー経由で使用することはできません。スパム通知。</span><span class="sxs-lookup"><span data-stu-id="3562e-129">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="3562e-130">サービスの SCL 値の詳細については、「[Spam Confidence Level](spam-confidence-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3562e-130">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="3562e-131">ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="3562e-131">Save the rule.</span></span>
    
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="3562e-132">メールフロールールを作成して、語句に基づいてバルクメールメッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="3562e-132">Create a mail flow rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="3562e-133">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="3562e-133">In the EAC, go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="3562e-134">[追加] アイコン](media/ITPro-EAC-AddIcon.gif)をクリックし、[**新しいルールの作成**] を選択します。 \*\*\*\* ![</span><span class="sxs-lookup"><span data-stu-id="3562e-134">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="3562e-135">ルールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3562e-135">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="3562e-p108">**[その他のオプション]** をクリックします。 **[次の場合、このルールを適用する]** で、 **[件名または本文]** \> **[件名または本文に次のいずれかの単語を含む]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3562e-p108">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>
    
5. <span data-ttu-id="3562e-138">**[単語または文字列の指定]** ダイアログ ボックスで、バルク メールでよく見られる以下の語句を一度に 1 つずつ追加して、終わったら **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3562e-138">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - `to change your preferences or unsubscribe`
    
   - `Modify email preferences or unsubscribe`
    
   - `This is a promotional email`
    
   - `You are receiving this email because you requested a subscription`
    
   - `click here to unsubscribe`
    
   - `You have received this email because you are subscribed`
    
   - `If you no longer wish to receive our email newsletter`
    
   - `to unsubscribe from this newsletter`
    
   - `If you have trouble viewing this email`
    
   - `This is an advertisement`
    
   - `you would like to unsubscribe or change your`
    
   - `view this email as a webpage`
    
   - `You are receiving this email because you are subscribed`
    
   <span data-ttu-id="3562e-p109">このリストは、バルクメールで検出された一連の語句を網羅したものではありません。必要に応じて、追加または削除することができます。ただし、開始点として適しています。</span><span class="sxs-lookup"><span data-stu-id="3562e-p109">This list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
6. <span data-ttu-id="3562e-141">**[実行する処理]** で、 **[メッセージのプロパティを変更する]** \> **[SCL (Spam Confidence Level) の設定]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3562e-141">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="3562e-142">**[SCL の指定]** ダイアログ ボックスで、SCL を **5**、 **6**、または **9** に設定して、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3562e-142">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="3562e-p110">コンテンツ フィルター ポリシーの設定に従って、SCL を 5 または 6 に設定した場合は **スパム**のアクションを行い、SCL を 9 に設定した場合は **信頼度の高いスパム**のアクションを行います。サービスは、コンテンツ フィルター ポリシーで設定されたアクションを実行します。既定のアクションでは、メッセージを受信者の迷惑メール フォルダーに配信しますが、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」に説明するとおり、異なるアクションを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="3562e-p110">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   <span data-ttu-id="3562e-146">メッセージを受信者の迷惑メールフォルダーに送信するのではなく、メッセージを検疫するように構成されている場合は、メッセージはメールフロールールの一致として管理者検疫に送信されますが、エンドユーザーのスパム検疫時またはエンドユーザー経由で使用することはできません。スパム通知。</span><span class="sxs-lookup"><span data-stu-id="3562e-146">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="3562e-147">サービスの SCL 値の詳細については、「[Spam Confidence Level](spam-confidence-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3562e-147">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="3562e-148">ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="3562e-148">Save the rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="3562e-149">詳細情報</span><span class="sxs-lookup"><span data-stu-id="3562e-149">For more information</span></span>

[<span data-ttu-id="3562e-150">迷惑メールとバルク メールの違い</span><span class="sxs-lookup"><span data-stu-id="3562e-150">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)

[<span data-ttu-id="3562e-151">バルク苦情レベルの値</span><span class="sxs-lookup"><span data-stu-id="3562e-151">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)

[<span data-ttu-id="3562e-152">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="3562e-152">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="3562e-153">高度なスパム対策フィルターオプション</span><span class="sxs-lookup"><span data-stu-id="3562e-153">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
