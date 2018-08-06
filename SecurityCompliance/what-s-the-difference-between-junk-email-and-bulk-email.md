---
title: 迷惑メールとバルク メールの違い
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/7/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
description: 顧客 askwhat の迷惑メールと大量の電子メール メッセージの違いのことがありますか。このトピックの目的は、違いを説明し、オンラインの Exchange および Exchange オンライン保護 (EOP) の両方で利用可能なさまざまなオプションに関する情報を提供します。
ms.openlocfilehash: 2cd9d9d91cf44af910983c045192ed7639d27417
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026244"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a><span data-ttu-id="b8385-103">迷惑メールとバルク メールの違い</span><span class="sxs-lookup"><span data-stu-id="b8385-103">What's the difference between junk email and bulk email?</span></span>

<span data-ttu-id="b8385-p101">お客様から「迷惑メール メッセージとバルク メール メッセージの違いは何ですか」という質問を受けることがよくあります。このトピックの目的は、この違いを説明することと、Exchange Online と Exchange Online Protection (EOP) の両方で使用可能なさまざまなオプションに関する情報を提供することです。</span><span class="sxs-lookup"><span data-stu-id="b8385-p101">Customers sometimes ask "what's the difference between junk email and bulk email messages?" The purpose of this topic is to explain the difference and to provide information about the different options that are available for both in Exchange Online and Exchange Online Protection (EOP).</span></span>
  
 <span data-ttu-id="b8385-106">**迷惑メールとは何か**</span><span class="sxs-lookup"><span data-stu-id="b8385-106">**What's junk email?**</span></span>
  
<span data-ttu-id="b8385-p102">迷惑メール メッセージは "スパム" メッセージで、サービスによってフィルター処理される未承諾 (かつ通常は不要な) 電子メール メッセージです。既定で、サービスは、送信元の IP アドレスの評価に基づいてスパム メッセージを拒否します。ただし、そのメッセージが IP 検査を通過しても、コンテンツ フィルターでスパムに分類された場合は、宛先になっている受信者の迷惑メール フォルダーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="b8385-p102">Junk email messages are "spam" messages, which are unsolicited (and typically unwanted) email messages that are filtered by the service. By default, the service rejects the spam message based on the reputation of the sending IP address. However, if it passes IP inspection but is classified as spam by the content filters, the message is sent to the Junk Email folder of the intended recipients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b8385-p103">「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」に記載されているように、コンテンツ フィルター処理されたメッセージに対して実行されるアクションは、Exchange 管理センター (EAC) のコンテンツ フィルター ポリシーを介して構成することができます。また、スパム分類に同意できない場合は、「[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」に記載されているように、スパムまたは非スパムであると思われるメッセージをいくつかの方法で Microsoft に報告することができます。</span><span class="sxs-lookup"><span data-stu-id="b8385-p103">The action performed on content-filtered messages is configurable via content filter policies in the Exchange admin center (EAC), as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md). Also, if you disagree with the spam classification, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> 
  
 <span data-ttu-id="b8385-112">**バルク メールとは何か**</span><span class="sxs-lookup"><span data-stu-id="b8385-112">**What's bulk email?**</span></span>
  
<span data-ttu-id="b8385-p104">グレー メールとも呼ばれるバルク メールは、分類がより困難な電子メール メッセージのことです。迷惑メールは「常にある脅威」であるのに対して、バルク メールは、通常、繰り返し送られてくるわけではない広告メッセージまたはマーケティング メッセージで構成されます。バルク メールは一部のユーザーによって要求されたものであり、事実、彼らは意図的にそれらのメッセージの受信を申し込んでいるのに対して、それ以外のユーザーはその種のメッセージをスパムと見なしています。たとえば、一部のユーザーは Contoso Corporation からの広告メールまたは次回のサイバー セキュリティに関するカンファレンスの招待状を受信したいと思っているのに対して、その他のユーザーはそのような電子メールをスパムと見なしている場合です。</span><span class="sxs-lookup"><span data-stu-id="b8385-p104">Bulk email, also referred to as gray mail, is a type of email message that's more difficult to classify. Whereas junk email is a constant threat, bulk email is typically comprised of an advertisement or marketing message that's not likely to get sent repeatedly. Bulk email is wanted by some users, and in fact they may have deliberately signed up to receive these messages, while other users may consider these types of messages to be spam. For example, some users want to receive advertising emails from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider such emails to be spam.</span></span>
  
## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="b8385-117">バルク メールの管理方法</span><span class="sxs-lookup"><span data-stu-id="b8385-117">How to manage bulk email</span></span>

<span data-ttu-id="b8385-p105">バルク メールの管理方法は簡単に結論を出すことができません。すべてのバルク メールをスパムとして分類した場合は、そのメールを必要とするユーザーがそれに反対して、間違ってスパムにマークされた誤検知 (非スパム) メッセージとして提出する可能性があります。一方、すべてのバルク メールを通過させた場合は、そのメールを必要としないユーザーがそれに反対して、間違って受信トレイに到着した、見逃されたスパム メッセージ (偽陰性) として提出する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b8385-p105">How to manage bulk email isn't a clear cut decision, because if all bulk email is classified as spam, the users that want it may complain and submit it as a false positive (non-spam) message that was wrongly marked as spam. On the other hand, if all bulk email is let through, the users that don't want it may complain and submit it as a missed spam message (false negative) that wrongly arrived in their inbox.</span></span>
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a><span data-ttu-id="b8385-120">コンテンツ フィルター ポリシーのバルク メールの秘密度の制御を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b8385-120">Enable bulk mail sensitivity control in the content filter policy</span></span>

<span data-ttu-id="b8385-p106">バルク メール メッセージに関する会社のポリシーに従って、管理者はバルク メールを割り当てるしきい値を選択できます。設定は、EAC のコンテンツ フィルター ポリシーを介して構成できます。手順については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。1 ～ 9 のしきい値の設定を選択できます。この場合、1 はほとんどのバルク メールをスパムとしてマークし、9 はほとんどのバルク メールの配信を許可します。その後、メッセージを受信者の迷惑メール フォルダーに送信するなどの構成されたアクションをサービスが実行します。</span><span class="sxs-lookup"><span data-stu-id="b8385-p106">Depending on your company's policy on bulk email messages, admins can select a threshold to assign the bulk email. The setting is is configurable via content filter policies in the EAC. Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md)) for the steps. You can choose a threshold setting from 1 - 9, where 1 marks most bulk email as spam, and 9 allows the most bulk email to be delivered. The service then performs the configured action, such as sending the message to the recipient's Junk Email folder.</span></span> 
  

