---
title: メール フロー ルールを使用して一括メールが Exchange のオンライン保護でフィルタ リングを構成するには
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
description: 管理者には、Exchange のオンライン保護でバルク メールのフィルターのメール フロー ルールを使用する方法を学習できます。
ms.openlocfilehash: ce95872d3d80436dce4c62037caea9a5f735726d
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "27382808"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a><span data-ttu-id="a4690-103">メール フロー ルールを使用して一括メールが Exchange のオンライン保護でフィルタ リングを構成するには</span><span class="sxs-lookup"><span data-stu-id="a4690-103">Use mail flow rules to configure bulk email filtering in Exchange Online Protection</span></span>

<span data-ttu-id="a4690-p101">既定のスパム コンテンツ フィルター ポリシーを使用して、スパムやバルク メールに対して会社全体のコンテンツ フィルターを設定することができます。コンテンツ フィルター ポリシーを設定する方法については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」と「[Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a4690-p101">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies. Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) on how to set the content filter policies.</span></span> 
  
<span data-ttu-id="a4690-p102">他のオプションを大量のメッセージをフィルター処理する場合は、テキストのパターンまたは一括メールで頻繁に見られる語句を検索するのにはメール フロー ルール (トランスポート ルールでとも呼ばれます) を作成できます。これらの特性が含まれているすべてのメッセージは、スパムとしてマークされます。これらの規則を使用すると、組織を受信する不要な一括メールの量を削減できます。</span><span class="sxs-lookup"><span data-stu-id="a4690-p102">If you want to more options to filter bulk messages, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases frequently found in bulk emails. Any message containing these characteristics will be marked as spam. Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>
  
<span data-ttu-id="a4690-109">**注**:</span><span class="sxs-lookup"><span data-stu-id="a4690-109">**Notes**:</span></span>

- <span data-ttu-id="a4690-110">メール フロー ルールを作成するには、このトピックが記載されて、前に、目を通すことが勧め[迷惑メール、一括メールの違いは何ですか?](what-s-the-difference-between-junk-email-and-bulk-email.md)と[一括苦情レベルの値](bulk-complaint-level-values.md)です。</span><span class="sxs-lookup"><span data-stu-id="a4690-110">Before creating the mail flow rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span> 
  
- <span data-ttu-id="a4690-p103">以下の手順は、特定のメッセージを組織全体でスパムとしてマークします。ただし、別の条件を追加すれば、これらのルールを組織内の特定の受信者にだけ適用することができます。このように、積極的なバルク メール フィルター処理設定を注目すべき少数のユーザーにだけ適用することによって、他のユーザー (受信するもののほとんどが登録したバルク メール) には影響を与えないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a4690-p103">The following procedures mark a message as spam for your entire organization. However, you can add another condition to apply these rules only to specific recipients in your organization. This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span> 
  
### <a name="create-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="a4690-114">一括電子メール メッセージのテキストのパターンに基づいてフィルターを適用するのには、メール フロー ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a4690-114">Create mail flow rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="a4690-115">Exchange 管理センター (EAC) で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="a4690-115">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="a4690-116">**[追加]**![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4690-116">Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="a4690-117">ルールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4690-117">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="a4690-p104">**[その他のオプション]** をクリックします。 **[次の場合、このルールを適用する]** で、 **[件名または本文]** \> **[件名または本文が次のテキスト パターンと一致する]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a4690-p104">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>
    
5. <span data-ttu-id="a4690-120">**[単語または文字列の指定]** ダイアログ ボックスで、バルク メールでよく見られる以下の正規表現を一度に 1 つずつ追加して、終わったら **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4690-120">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - <span data-ttu-id="a4690-121">このメールの内容を表示することがないかどうかは\,してください</span><span class="sxs-lookup"><span data-stu-id="a4690-121">If you are unable to view the content of this email\, please</span></span>
    
   - <span data-ttu-id="a4690-122">\\>(安全な)?登録取り消し( はここから)?\\</a\\></span><span class="sxs-lookup"><span data-stu-id="a4690-122">\\>(safe )?unsubscribe( here)?\\</a\\></span></span>
    
   - <span data-ttu-id="a4690-123">次のようにそれ以上の通信を受信したくない場合は\,してください</span><span class="sxs-lookup"><span data-stu-id="a4690-123">If you do not wish to receive further communications like this\, please</span></span>
    
   - <span data-ttu-id="a4690-p105">\\<img height\="?1"? width\="?1"? src\=.?http\://</span><span class="sxs-lookup"><span data-stu-id="a4690-p105">\\<img height\="?1"? width\="?1"? src\=.?http\://</span></span>
    
   - <span data-ttu-id="a4690-127">これらの電子メールの受信を停止する\:http\://</span><span class="sxs-lookup"><span data-stu-id="a4690-127">To stop receiving these\s+emails\:http\://</span></span>
    
   - <span data-ttu-id="a4690-128">\w+ (e\-?レター|e?-?メール|ニュースレター) の登録を取り消すには</span><span class="sxs-lookup"><span data-stu-id="a4690-128">To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)</span></span>
    
   - <span data-ttu-id="a4690-129">今後\w+電子メールの(送信|受信)を(希望)?しない場合</span><span class="sxs-lookup"><span data-stu-id="a4690-129">no longer (wish )?(to )?(be sent|receive) \w+ email</span></span>
    
   - <span data-ttu-id="a4690-130">このメールの内容を表示することがないかどうかは\,は、ここをクリックしてください</span><span class="sxs-lookup"><span data-stu-id="a4690-130">If you are unable to view the content of this email\, please click here</span></span>
    
   - <span data-ttu-id="a4690-131">受信することを確認する (毎日商談 | 当社の e-?mails)\,を追加</span><span class="sxs-lookup"><span data-stu-id="a4690-131">To ensure you receive (your daily deals|our e-?mails)\, add</span></span>
    
   - <span data-ttu-id="a4690-132">これらの電子メールを今後受信したくない場合は、</span><span class="sxs-lookup"><span data-stu-id="a4690-132">If you no longer wish to receive these emails</span></span>
    
   - <span data-ttu-id="a4690-133">(登録設定変更|設定変更または登録解除)は</span><span class="sxs-lookup"><span data-stu-id="a4690-133">to change your (subscription preferences|preferences or unsubscribe)</span></span>
    
   - <span data-ttu-id="a4690-134">登録解除(するにはここ|アイコン)をクリックしてください</span><span class="sxs-lookup"><span data-stu-id="a4690-134">click (here to|the) unsubscribe</span></span>
    
   <span data-ttu-id="a4690-135">**注**:</span><span class="sxs-lookup"><span data-stu-id="a4690-135">**Notes**:</span></span>

   - <span data-ttu-id="a4690-p106">上記の一覧については、一括メールの場合は、正規表現のすべてを網羅した、セットのないです。複数のことができますを追加または削除、必要に応じてします。ただし、それはの開始点です。</span><span class="sxs-lookup"><span data-stu-id="a4690-p106">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
   - <span data-ttu-id="a4690-p107">単語または件名にテキスト パターンやその他のメッセージのヘッダ ・ フィールドの検索では、ASCII テキストで SMTP サーバーの間でバイナリ メッセージを送信するために使用されたエンコードの MIME コンテンツ転送からデコードされた*後*メッセージを発生します。生を検索する条件および例外条件を使用することはできません (通常は、base 64)、件名またはメッセージの場合は、他のヘッダー フィールドの値をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="a4690-p107">The search for words or text patterns in the subject or other header fields in the message occurs  *after*  the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span> 
    
6. <span data-ttu-id="a4690-140">**[実行する処理]** で、 **[メッセージのプロパティを変更する]** \> **[SCL (Spam Confidence Level) の設定]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a4690-140">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="a4690-141">**[SCL の指定]** ダイアログ ボックスで、SCL を **5**、 **6**、または **9** に設定して、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4690-141">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="a4690-p108">コンテンツ フィルター ポリシーの設定に従って、SCL を 5 または 6 に設定した場合は **スパム**のアクションを行い、SCL を 9 に設定した場合は **信頼度の高いスパム**のアクションを行います。サービスは、コンテンツ フィルター ポリシーで設定されたアクションを実行します。既定のアクションでは、メッセージを受信者の迷惑メール フォルダーに配信しますが、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」に説明するとおり、異なるアクションを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="a4690-p108">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="a4690-145">設定済みのアクションは、受信者の迷惑メール フォルダーに送信するのではなく、メッセージを検疫する場合とメール フロー ルールの一致、およびその使用可能なエンド ・ ユーザーのスパム検疫やエンド ・ ユーザー、管理者の検疫にメッセージを送信します。迷惑メールで通知</span><span class="sxs-lookup"><span data-stu-id="a4690-145">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="a4690-146">サービスの SCL 値の詳細については、「[Spam Confidence Level](spam-confidence-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4690-146">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="a4690-147">ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="a4690-147">Save the rule.</span></span>
    
### <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="a4690-148">語句に基づいて大量の電子メール メッセージにフィルターを適用するのには、メール フロー ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a4690-148">Create a mail flow rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="a4690-149">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="a4690-149">In the EAC, go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="a4690-150">**[追加]**![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4690-150">Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="a4690-151">ルールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4690-151">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="a4690-p109">**[その他のオプション]** をクリックします。 **[次の場合、このルールを適用する]** で、 **[件名または本文]** \> **[件名または本文に次のいずれかの単語を含む]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a4690-p109">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>
    
5. <span data-ttu-id="a4690-154">**[単語または文字列の指定]** ダイアログ ボックスで、バルク メールでよく見られる以下の語句を一度に 1 つずつ追加して、終わったら **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4690-154">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - <span data-ttu-id="a4690-155">設定を変更または購読登録を解除するには</span><span class="sxs-lookup"><span data-stu-id="a4690-155">to change your preferences or unsubscribe</span></span>
    
   - <span data-ttu-id="a4690-156">電子メールの設定の変更または購読登録の解除</span><span class="sxs-lookup"><span data-stu-id="a4690-156">Modify email preferences or unsubscribe</span></span>
    
   - <span data-ttu-id="a4690-157">これは広告メールです</span><span class="sxs-lookup"><span data-stu-id="a4690-157">This is a promotional email</span></span>
    
   - <span data-ttu-id="a4690-158">このメールは、購読を希望されたお客様に送信しています</span><span class="sxs-lookup"><span data-stu-id="a4690-158">You are receiving this email because you requested a subscription</span></span>
    
   - <span data-ttu-id="a4690-159">購読を停止するには、ここをクリックしてください</span><span class="sxs-lookup"><span data-stu-id="a4690-159">click here to unsubscribe</span></span>
    
   - <span data-ttu-id="a4690-160">このメールは、購読登録されているお客様にお送りしました</span><span class="sxs-lookup"><span data-stu-id="a4690-160">You have received this email because you are subscribed</span></span>
    
   - <span data-ttu-id="a4690-161">今後弊社の電子メール　ニュースレターをお受け取りになりたくない場合は</span><span class="sxs-lookup"><span data-stu-id="a4690-161">If you no longer wish to receive our email newsletter</span></span>
    
   - <span data-ttu-id="a4690-162">このニュースレターの購読登録を解除してください</span><span class="sxs-lookup"><span data-stu-id="a4690-162">to unsubscribe from this newsletter</span></span>
    
   - <span data-ttu-id="a4690-163">このメールが正しく表示されない場合は</span><span class="sxs-lookup"><span data-stu-id="a4690-163">If you have trouble viewing this email</span></span>
    
   - <span data-ttu-id="a4690-164">これは広告です</span><span class="sxs-lookup"><span data-stu-id="a4690-164">This is an advertisement</span></span>
    
   - <span data-ttu-id="a4690-165">購読登録解除または設定変更を希望</span><span class="sxs-lookup"><span data-stu-id="a4690-165">you would like to unsubscribe or change your</span></span>
    
   - <span data-ttu-id="a4690-166">このメールを Web ページとして表示</span><span class="sxs-lookup"><span data-stu-id="a4690-166">view this email as a webpage</span></span>
    
   - <span data-ttu-id="a4690-167">このメールは、購読登録されているお客様に送信しています</span><span class="sxs-lookup"><span data-stu-id="a4690-167">You are receiving this email because you are subscribed</span></span>
    
   <span data-ttu-id="a4690-p110">**注**: もう一度、このリストはありません、一括電子メール; であるフレーズのセットですべてを網羅しました。複数のことができますを追加または削除、必要に応じてします。ただし、それはの開始点です。</span><span class="sxs-lookup"><span data-stu-id="a4690-p110">**Note**: Once again, this list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
6. <span data-ttu-id="a4690-170">**[実行する処理]** で、 **[メッセージのプロパティを変更する]** \> **[SCL (Spam Confidence Level) の設定]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a4690-170">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="a4690-171">**[SCL の指定]** ダイアログ ボックスで、SCL を **5**、 **6**、または **9** に設定して、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4690-171">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="a4690-p111">コンテンツ フィルター ポリシーの設定に従って、SCL を 5 または 6 に設定した場合は **スパム**のアクションを行い、SCL を 9 に設定した場合は **信頼度の高いスパム**のアクションを行います。サービスは、コンテンツ フィルター ポリシーで設定されたアクションを実行します。既定のアクションでは、メッセージを受信者の迷惑メール フォルダーに配信しますが、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」に説明するとおり、異なるアクションを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="a4690-p111">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="a4690-175">設定済みのアクションは、受信者の迷惑メール フォルダーに送信するのではなく、メッセージを検疫する場合とメール フロー ルールの一致、およびその使用可能なエンド ・ ユーザーのスパム検疫やエンド ・ ユーザー、管理者の検疫にメッセージを送信します。迷惑メールで通知</span><span class="sxs-lookup"><span data-stu-id="a4690-175">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="a4690-176">サービスの SCL 値の詳細については、「[Spam Confidence Level](spam-confidence-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4690-176">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="a4690-177">ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="a4690-177">Save the rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="a4690-178">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a4690-178">For more information</span></span>

[<span data-ttu-id="a4690-179">迷惑メールとバルク メールの違い</span><span class="sxs-lookup"><span data-stu-id="a4690-179">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)

[<span data-ttu-id="a4690-180">バルク苦情レベルの値</span><span class="sxs-lookup"><span data-stu-id="a4690-180">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)

[<span data-ttu-id="a4690-181">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="a4690-181">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="a4690-182">高度な迷惑メールのフィルタ リングのオプション</span><span class="sxs-lookup"><span data-stu-id="a4690-182">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
