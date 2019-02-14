---
title: レポート メッセージ アドインを有効にする
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/18/2019
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Outlook と Outlook は、個々 のユーザーまたは組織全体のメッセージのレポート アドインを有効にする方法を説明します。
ms.openlocfilehash: 8c061d14d11aa868567487186c5dcca534b86215
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995158"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="9b2ef-103">レポート メッセージ アドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="9b2ef-103">Enable the Report Message add-in</span></span>

## <a name="overview"></a><span data-ttu-id="9b2ef-104">概要</span><span class="sxs-lookup"><span data-stu-id="9b2ef-104">Overview</span></span>

<span data-ttu-id="9b2ef-p101">レポート メッセージを追加で、Outlook と Outlook web 上で簡単に報告する misclassified メールは、安全なまたは悪意のあるかどうかマイクロソフトおよびその関連会社の分析のためにユーザーを使用できます。マイクロソフトでは、電子メール保護テクノロジの有効性を向上させるためにこれらの送信を使用します。さらに、 [Office 365 の高度な脅威保護](office-365-atp.md)または[Office 365 の脅威インテリジェンス](office-365-ti.md)組織を使用している場合、レポート メッセージを追加では、についての情報を確認および更新に使用できる、組織のセキュリティ チームセキュリティ ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-p101">The Report Message add-in for Outlook and Outlook on the web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis. Microsoft uses these submissions to improve the effectiveness of email protection technologies. In addition, if your organization is using [Office 365 Advanced Threat Protection](office-365-atp.md) or [Office 365 Threat Intelligence](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="9b2ef-p102">たとえば、ユーザーがフィッシング メッセージの多くを報告するいるとします。この情報には、[ダッシュ ボードのセキュリティ](security-dashboard.md)およびその他のレポート内のサーフェスが。組織のセキュリティ チームは、フィッシング詐欺対策のポリシーを更新する必要がありますを示す値として、この情報を使用できます。または、ユーザーには、多くのメッセージのレポート アドインを使用して、迷惑メールと迷惑メールとしてフラグ付けされたメッセージが報告される場合、組織のセキュリティ チームが[迷惑メール対策ポリシー](configure-the-anti-spam-policies.md)を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-p102">For example, suppose that people are reporting a lot of messages as phishing. This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports. Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated. Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="9b2ef-112">レポート メッセージを追加では、Office 365 サブスクリプションと次の製品で動作します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-112">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="9b2ef-113">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="9b2ef-113">Outlook on the web</span></span>
 - <span data-ttu-id="9b2ef-114">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="9b2ef-114">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="9b2ef-115">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9b2ef-115">Outlook 2016</span></span>
 - <span data-ttu-id="9b2ef-116">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="9b2ef-116">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="9b2ef-117">Outlook を Office 365 用リソースに含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-117">Outlook included with Office 365 ProPlus</span></span>

> [!NOTE]
> <span data-ttu-id="9b2ef-p103">レポート メッセージ用のアドインの Outlook と web 上で Outlook は[Outlook 迷惑メール フィルター](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)と同じ迷惑メール、迷惑メールまたはフィッシング詐欺メールを開封するのには使用できますが、両方。レポート メッセージ用のアドインの Outlook と Outlook web Outlook 迷惑メール フィルターがユーザーのメールボックスに電子メール メッセージを整理するに対して、misclassified の電子メールについてマイクロソフトに通知します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-p103">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt. The Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span> 
  
<span data-ttu-id="9b2ef-120">個々 のユーザーの場合、[自分のメッセージのレポート アドインを有効に](#get-the-report-message-add-in-for-yourself)することができます。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-120">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="9b2ef-p104">Office 365 のグローバル管理者または Exchange Online 管理者は、OAuth 認証を使用する Exchange が構成されている場合は[、レポート メッセージ用のアドインの組織を有効に](#get-and-enable-the-report-message-add-in-for-your-organization)することができます。レポート メッセージ アドインが[一元的な展開](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-p104">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization). The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="9b2ef-123">自分用の追加のレポート メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-123">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="9b2ef-124">[マイクロソフトの AppSource](https://appsource.microsoft.com/marketplace/apps)、検索[レポート メッセージを追加で](https://appsource.microsoft.com/product/office/wa104381180)します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-124">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="9b2ef-125">選択**を取得ここでの IT**です。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-125">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="9b2ef-126">![メッセージを報告する-今すぐ](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="9b2ef-126">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="9b2ef-p105">使用およびプライバシー ポリシーの条件を確認します。**続行**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-p105">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="9b2ef-129">作業または学校アカウント (業務用) または Microsoft アカウント (個人向け) を使用して Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-129">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    
<span data-ttu-id="9b2ef-130">アドインがインストールされており後、は、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-130">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="9b2ef-131">Outlook では、次のようなアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-131">In Outlook, the icon looks like this:</span></span> <br/> ![Outlook のアイコンを追加でメッセージを報告します。](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="9b2ef-133">Outlook Web App (または、web 上で Outlook) では、次のように、アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-133">In Outlook Web App (or Outlook on the web), the icon looks like this:</span></span><br/>![Outlook web レポート メッセージの追加のアイコンを](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="9b2ef-135">については、次のステップとして[、レポート メッセージのアドインを使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)する方法です。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-135">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="9b2ef-136">取得し、レポート メッセージ用のアドインの組織を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-136">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b2ef-p106">このタスクを完了するには、Office 365 のグローバル管理者またはオンラインの Exchange 管理者である必要があります。さらに、 [Exchange 要件 (アドインの展開を一元的な)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements)を参照してください詳細については OAuth 認証を使用する Exchange を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-p106">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task. In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements).</span></span> 

1. <span data-ttu-id="9b2ef-139">Microsoft 365 管理センターの[サービスの & のアドインのページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)に移動します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-139">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="9b2ef-140">![新しい 365 管理センターでのサービスとアドインのページ](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="9b2ef-140">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/> 
    
2. <span data-ttu-id="9b2ef-141">**アドインを配置 +** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-141">Choose **+ Deploy Add-in**.</span></span><br/><span data-ttu-id="9b2ef-142">![選択アドインを配置](media/ServicesAddIns-ChooseDeployAddIn.png)</span><span class="sxs-lookup"><span data-stu-id="9b2ef-142">![Choose Deploy Add-In](media/ServicesAddIns-ChooseDeployAddIn.png)</span></span><br/> 
    
3. <span data-ttu-id="9b2ef-143">**新しいアドイン**] 画面で情報を確認してとし、[**次**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-143">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="9b2ef-144">![新しいアドインの詳細情報](media/NewAddInScreen1.png)</span><span class="sxs-lookup"><span data-stu-id="9b2ef-144">![New Add-In details](media/NewAddInScreen1.png)</span></span><br/>
    
4. <span data-ttu-id="9b2ef-145">**Office ストアからアドインを追加する**にはを選択し、し、[**次**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-145">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span><br/><span data-ttu-id="9b2ef-146">![新しいアドインを追加します。](media/NewAddInScreen2.png)</span><span class="sxs-lookup"><span data-stu-id="9b2ef-146">![I want to add an new Add-In](media/NewAddInScreen2.png)</span></span><br/> 
    
5. <span data-ttu-id="9b2ef-147">**レポート メッセージ**、および**レポート メッセージのアドイン**の横に、結果の一覧でを検索する場合、**追加**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-147">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span><br/><span data-ttu-id="9b2ef-148">![レポート メッセージを検索し、[追加](media/NewAddInScreen3.png)</span><span class="sxs-lookup"><span data-stu-id="9b2ef-148">![Search for Report Message and then choose Add](media/NewAddInScreen3.png)</span></span><br/>
    
6. <span data-ttu-id="9b2ef-149">**レポート メッセージ**画面で、情報を確認し、[**次**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-149">On the **Report Message** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="9b2ef-150">![レポート メッセージの詳細](media/ReportMessageAdd-InNewScreen4.png)</span><span class="sxs-lookup"><span data-stu-id="9b2ef-150">![Report Message details](media/ReportMessageAdd-InNewScreen4.png)</span></span><br/>

7. <span data-ttu-id="9b2ef-151">Outlook のユーザーの既定の設定を指定し、し、[**次**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-151">Specify the user default settings for Outlook, and  then choose **Next**.</span></span><br/><span data-ttu-id="9b2ef-152">![Outlook のメッセージの既定の設定を報告します。](media/ReportMessageOptionsScreen5.png)</span><span class="sxs-lookup"><span data-stu-id="9b2ef-152">![Report Message default settings for Outlook](media/ReportMessageOptionsScreen5.png)</span></span><br/>

8. <span data-ttu-id="9b2ef-153">メッセージのレポート アドインを取得するかを指定し、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-153">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span> <br/><span data-ttu-id="9b2ef-154">![追加のレポート メッセージを取得します。](media/ReportMessageOptionsScreen6.png)</span><span class="sxs-lookup"><span data-stu-id="9b2ef-154">![Who gets the Report Message add-in](media/ReportMessageOptionsScreen6.png)</span></span><br/>

> [!TIP]
> <span data-ttu-id="9b2ef-155">[ユーザーから報告された電子メール メッセージのコピーを取得するルールの設定](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)を推奨します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-155">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="9b2ef-p107">アドイン (手順 7-8 の上) を設定するときに選択した内容により、組織内のユーザー[レポート メッセージの追加に](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)使用できるがあります。組織内のユーザーは、次のアイコンで表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-p107">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available. People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="9b2ef-158">Outlook では、次のようなアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-158">In Outlook, the icon looks like this:</span></span> <br/> ![Outlook 用アドインのメッセージのアイコンをレポート](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="9b2ef-160">Outlook Web App (または、web 上で Outlook) では、次のように、アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-160">In Outlook Web App (or Outlook on the web), the icon looks like this:</span></span><br/>![Outlook アドインの Web レポートのメッセージのアイコンを](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="9b2ef-162">メッセージのレポート アドインをユーザーに通知するときに[、レポート メッセージのアドインの使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)へのリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-162">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="9b2ef-163">ルールの設定、ユーザーから報告された電子メール メッセージのコピーを取得するには</span><span class="sxs-lookup"><span data-stu-id="9b2ef-163">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b2ef-164">このタスクを実行するのには、Exchange にアクセスする権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-164">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="9b2ef-p108">ルールを設定するには、組織内のユーザーによって報告された電子メール メッセージのコピーを取得します。ダウンロードし、組織のメッセージのレポート アドインを有効にした後に行います。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-p108">You can set up a rule to get a copy of email messages reported by users in your organization. You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="9b2ef-167">Exchange 管理センターで、**メール フロー**を選択します\>**ルール**です。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-167">In the Exchange Admin Center, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="9b2ef-168">選択**+** \> **新しい規則を作成**します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-168">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="9b2ef-169">**[名前**] ボックスで、提出書類などの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-169">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="9b2ef-170">**場合にこのルールを適用**] ボックスの一覧で、**受信者のアドレスが含まれています...** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-170">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="9b2ef-171">**単語または語句を指定する**画面で、追加`junk@office365.microsoft.com`と`phish@office365.microsoft.com`、し、 **[ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-171">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span><br/><span data-ttu-id="9b2ef-172">![ルールの迷惑メールおよびフィッシングの電子メール アドレスを指定します。](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span><span class="sxs-lookup"><span data-stu-id="9b2ef-172">![Specify the junk and phish email addresses for the rule](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span></span><br/>
  
6. <span data-ttu-id="9b2ef-173">**. 次の操作**の一覧の [ **、メッセージの [bcc] に...**。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-173">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="9b2ef-174">グローバル管理者、セキュリティ管理者は、またはセキュリティ リーダーいる人が、マイクロソフトに報告する各電子メール メッセージのコピーを受信する必要があり、[ **ok]** を追加します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-174">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span><br/><span data-ttu-id="9b2ef-175">![報告された各メッセージのコピーを受信するのにはグローバルまたはセキュリティ管理者を追加します。](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span><span class="sxs-lookup"><span data-stu-id="9b2ef-175">![Add a global or security administrator to receive a copy of each reported message](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span></span><br/>
  
8. <span data-ttu-id="9b2ef-176">**監査の重大度レベルでは、この規則**を選択し、 **[中]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-176">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="9b2ef-177">[**この規則のモードの選択**を**強制する**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-177">Under **Choose a mode for this rule**, choose **Enforce**.</span></span><br/><span data-ttu-id="9b2ef-178">![報告された各メッセージのコピーを取得するルールを設定します。](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span><span class="sxs-lookup"><span data-stu-id="9b2ef-178">![Set up a rule to get a copy of each reported message](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span></span><br/>
  
10. <span data-ttu-id="9b2ef-179">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-179">Choose **Save**.</span></span> 
    
<span data-ttu-id="9b2ef-p109">配置では、このルールが他の組織でアドインを使用して、レポート メッセージ、電子メール メッセージを報告するたびに、グローバル管理者、セキュリティ管理者、またはセキュリティ リーダーが表示されますがメッセージのコピー。この情報を使用して、セットアップまたは[Office 365 の ATP の安全なリンク](atp-safe-links.md)ポリシー、または[スパム対策](anti-spam-protection.md)の設定などのポリシーを調整することができます。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-p109">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message. This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span> 

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="9b2ef-182">レポート メッセージを追加で使用する方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-182">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="9b2ef-183">[レポート メッセージの追加の使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-183">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="9b2ef-184">確認またはレポート メッセージを追加の設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-184">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="9b2ef-185">確認し、レポート メッセージを追加で、 [& [アドイン サービス] ページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)の既定の設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-185">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9b2ef-186">このタスクを完了するには、Office 365 のグローバル管理者またはオンラインの Exchange 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-186">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="9b2ef-187">Microsoft 365 管理センターの[サービスの & のアドインのページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)に移動します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-187">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="9b2ef-188">![新しい 365 管理センターでのサービスとアドインのページ](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="9b2ef-188">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/>

2. <span data-ttu-id="9b2ef-189">検索し、レポート メッセージを追加で選択します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-189">Find and select the Report Message add-in.</span></span><br/>![検索し、レポート メッセージを追加で選択](media/FindReportMessageAddIn.png)<br/> 
    
3. <span data-ttu-id="9b2ef-191">レポート メッセージ画面で、確認し、組織の必要に応じて設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-191">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span><br/>![レポート メッセージのアドインの設定](media/EditReportMessageAddIn.png)<br/> 
  
## <a name="related-topics"></a><span data-ttu-id="9b2ef-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b2ef-193">Related topics</span></span>

[<span data-ttu-id="9b2ef-194">迷惑メール報告アドインを使用する</span><span class="sxs-lookup"><span data-stu-id="9b2ef-194">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="9b2ef-195">セキュリティで電子メールのセキュリティ レポートを表示する&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="9b2ef-195">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="9b2ef-196">Office 365 の高度な脅威保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="9b2ef-196">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="9b2ef-197">エクスプ ローラーを使用して、セキュリティで&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="9b2ef-197">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  

