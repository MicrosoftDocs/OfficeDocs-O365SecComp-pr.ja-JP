---
title: レポート メッセージ アドインを有効にする
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/19/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: Outlook と Outlook は、個々 のユーザーまたは組織全体のメッセージのレポート アドインを有効にする方法を説明します。
ms.openlocfilehash: f35899d3f0be9ee07cb6dae5c5fec40395948340
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706371"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="03ee9-103">レポート メッセージ アドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="03ee9-103">Enable the Report Message add-in</span></span>

## <a name="overview"></a><span data-ttu-id="03ee9-104">概要</span><span class="sxs-lookup"><span data-stu-id="03ee9-104">Overview</span></span>

<span data-ttu-id="03ee9-p101">レポート メッセージを追加で、Outlook と Outlook Web 上で簡単に報告する misclassified メールは、安全なまたは悪意のあるかどうかマイクロソフトおよびその関連会社の分析のためにユーザーを使用できます。マイクロソフトでは、電子メール保護テクノロジの有効性を向上させるためにこれらの送信を使用します。さらに、 [Office 365 の高度な脅威保護](office-365-atp.md)または[Office 365 の脅威インテリジェンス](office-365-ti.md)組織を使用している場合、レポート メッセージを追加では、についての情報を確認および更新に使用できる、組織のセキュリティ チームセキュリティ ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="03ee9-p101">The Report Message add-in for Outlook and Outlook on the Web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis. Microsoft uses these submissions to improve the effectiveness of email protection technologies. In addition, if your organization is using [Office 365 Advanced Threat Protection](office-365-atp.md) or [Office 365 Threat Intelligence](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="03ee9-p102">たとえば、ユーザーがフィッシング メッセージの多くを報告するいるとします。この情報には、[ダッシュ ボードのセキュリティ](security-dashboard.md)およびその他のレポート内のサーフェスが。組織のセキュリティ チームは、フィッシング詐欺対策のポリシーを更新する必要がありますを示す値として、この情報を使用できます。または、ユーザーには、多くのメッセージのレポート アドインを使用して、迷惑メールと迷惑メールとしてフラグ付けされたメッセージが報告される場合、組織のセキュリティ チームが[迷惑メール対策ポリシー](configure-the-anti-spam-policies.md)を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03ee9-p102">For example, suppose that people are reporting a lot of messages as phishing. This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports. Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated. Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="03ee9-112">レポート メッセージを追加では、Office 365 サブスクリプションと次の製品で動作します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-112">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="03ee9-113">Web 上の outlook</span><span class="sxs-lookup"><span data-stu-id="03ee9-113">Outlook on the Web</span></span>
 - <span data-ttu-id="03ee9-114">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="03ee9-114">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="03ee9-115">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="03ee9-115">Outlook 2016</span></span>
 - <span data-ttu-id="03ee9-116">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="03ee9-116">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="03ee9-117">Outlook を Office 365 用リソースに含まれています。</span><span class="sxs-lookup"><span data-stu-id="03ee9-117">Outlook included with Office 365 ProPlus</span></span>
  
<span data-ttu-id="03ee9-118">個々 のユーザーの場合、[自分のメッセージのレポート アドインを有効に](#get-the-report-message-add-in-for-yourself)することができます。</span><span class="sxs-lookup"><span data-stu-id="03ee9-118">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="03ee9-p103">Office 365 のグローバル管理者または Exchange Online 管理者は、OAuth 認証を使用する Exchange が構成されている場合は[、レポート メッセージ用のアドインの組織を有効に](#get-and-enable-the-report-message-add-in-for-your-organization)することができます。レポート メッセージ アドインが[一元的な展開](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="03ee9-p103">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization). The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="03ee9-121">自分用の追加のレポート メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-121">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="03ee9-122">[マイクロソフトの AppSource](https://appsource.microsoft.com/marketplace/apps)、検索[レポート メッセージを追加で](https://appsource.microsoft.com/product/office/wa104381180)します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-122">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="03ee9-123">選択**を取得ここでの IT**です。</span><span class="sxs-lookup"><span data-stu-id="03ee9-123">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="03ee9-124">![メッセージを報告する-今すぐ](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="03ee9-124">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="03ee9-p104">使用およびプライバシー ポリシーの条件を確認します。**続行**を選択します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-p104">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="03ee9-127">作業または学校アカウント (業務用) または Microsoft アカウント (個人向け) を使用して、Office 365 の電子メールにサインインします。</span><span class="sxs-lookup"><span data-stu-id="03ee9-127">Sign in to your Office 365 email using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    
<span data-ttu-id="03ee9-128">アドインがインストールされており後、は、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="03ee9-128">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="03ee9-129">Outlook では、次のように、アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="03ee9-129">In Outlook the icon looks like this:</span></span> <br/> ![Outlook 用アドインのメッセージのアイコンをレポート](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="03ee9-131">Outlook Web App では、次のように、アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="03ee9-131">In Outlook Web App the icon looks like this:</span></span><br/>![Outlook アドインの Web レポートのメッセージのアイコンを](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

<span data-ttu-id="03ee9-133">については、次のステップとして[、レポート メッセージのアドインを使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)する方法です。</span><span class="sxs-lookup"><span data-stu-id="03ee9-133">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="03ee9-134">取得し、レポート メッセージ用のアドインの組織を有効にします。</span><span class="sxs-lookup"><span data-stu-id="03ee9-134">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03ee9-p105">このタスクを完了するには、Office 365 のグローバル管理者またはオンラインの Exchange 管理者である必要があります。さらに、 [Exchange 要件 (アドインの展開を一元的な)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements)を参照してください詳細については OAuth 認証を使用する Exchange を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03ee9-p105">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task. In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements).</span></span> 

1. <span data-ttu-id="03ee9-137">[サービスおよびアドインのページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)に新しい Microsoft 365 の管理ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-137">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the new Microsoft 365 admin center.</span></span><br/><span data-ttu-id="03ee9-138">![新しい 365 管理センターでのサービスとアドインのページ](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="03ee9-138">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/> 
    
2. <span data-ttu-id="03ee9-139">**アドインを配置 +** を選択します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-139">Choose **+ Deploy Add-in**.</span></span><br/><span data-ttu-id="03ee9-140">![選択アドインを配置](media/ServicesAddIns-ChooseDeployAddIn.png)</span><span class="sxs-lookup"><span data-stu-id="03ee9-140">![Choose Deploy Add-In](media/ServicesAddIns-ChooseDeployAddIn.png)</span></span><br/> 
    
3. <span data-ttu-id="03ee9-141">新しいアドイン] 画面で情報を確認してとし、[**次**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-141">In the New Add-In screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="03ee9-142">![新しいアドインの詳細情報](media/NewAddInScreen1.png)</span><span class="sxs-lookup"><span data-stu-id="03ee9-142">![New Add-In details](media/NewAddInScreen1.png)</span></span><br/>
    
4. <span data-ttu-id="03ee9-143">**Office ストアからアドインを追加する**にはを選択し、し、[**次**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-143">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span><br/><span data-ttu-id="03ee9-144">![新しいアドインを追加します。](media/NewAddInScreen2.png)</span><span class="sxs-lookup"><span data-stu-id="03ee9-144">![I want to add an new Add-In](media/NewAddInScreen2.png)</span></span><br/> 
    
5. <span data-ttu-id="03ee9-145">レポート メッセージ、およびレポート メッセージ アドインの横に、結果の一覧でを検索する場合、追加を選択します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-145">Search for Report Message, and in the list of results, next to the Report Message Add-In, choose Add.</span></span><br/>![レポート メッセージを検索し、[追加](media/NewAddInScreen3.png)<br/>
    
6. <span data-ttu-id="03ee9-147">レポート メッセージ画面で、情報を確認し、[**次**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-147">On the Report Message screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="03ee9-148">![レポート メッセージの詳細](media/ReportMessageAdd-InNewScreen4.png)</span><span class="sxs-lookup"><span data-stu-id="03ee9-148">![Report Message details](media/ReportMessageAdd-InNewScreen4.png)</span></span><br/>

7. <span data-ttu-id="03ee9-149">Outlook のユーザーの既定の設定を指定し、し、[**次**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-149">Specify the user default settings for Outlook, and  then choose **Next**.</span></span><br/><span data-ttu-id="03ee9-150">![Outlook のメッセージの既定の設定を報告します。](media/ReportMessageOptionsScreen5.png)</span><span class="sxs-lookup"><span data-stu-id="03ee9-150">![Report Message default settings for Outlook](media/ReportMessageOptionsScreen5.png)</span></span><br/>

8. <span data-ttu-id="03ee9-151">メッセージのレポート アドインを取得するかを指定し、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-151">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span> <br/><span data-ttu-id="03ee9-152">![追加のレポート メッセージを取得します。](media/ReportMessageOptionsScreen6.png)</span><span class="sxs-lookup"><span data-stu-id="03ee9-152">![Who gets the Report Message add-in](media/ReportMessageOptionsScreen6.png)</span></span><br/>

> [!TIP]
> <span data-ttu-id="03ee9-153">[ユーザーから報告された電子メール メッセージのコピーを取得するルールの設定](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)を推奨します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-153">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)</span></span>

<span data-ttu-id="03ee9-p106">によってどのような選択したウィザードを使用して、組織内のユーザー[レポート メッセージのアドインを](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)使用できるがあります。組織内のユーザーは、次のアイコンで表示されます。</span><span class="sxs-lookup"><span data-stu-id="03ee9-p106">Depending on what you selected using the wizard, people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available. People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="03ee9-156">Outlook では、次のように、アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="03ee9-156">In Outlook the icon looks like this:</span></span> <br/> ![Outlook 用アドインのメッセージのアイコンをレポート](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="03ee9-158">Outlook Web App では、次のように、アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="03ee9-158">In Outlook Web App the icon looks like this:</span></span><br/>![Outlook アドインの Web レポートのメッセージのアイコンを](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="03ee9-160">ルールの設定、ユーザーから報告された電子メール メッセージのコピーを取得するには</span><span class="sxs-lookup"><span data-stu-id="03ee9-160">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03ee9-161">このタスクを実行するのには、Exchange にアクセスする権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="03ee9-161">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="03ee9-p107">ルールを設定するには、組織内のユーザーによって報告された電子メール メッセージのコピーを取得します。ダウンロードし、組織のメッセージのレポート アドインを有効にした後に行います。</span><span class="sxs-lookup"><span data-stu-id="03ee9-p107">You can set up a rule to get a copy of email messages reported by users in your organization. You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="03ee9-164">Exchange 管理センターで、**メール フロー**を選択します\>**ルール**です。</span><span class="sxs-lookup"><span data-stu-id="03ee9-164">In the Exchange Admin Center, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="03ee9-165">選択**+** \> **新しい規則を作成**します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-165">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="03ee9-166">**[名前**] ボックスで、提出書類などの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-166">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="03ee9-167">**場合にこのルールを適用**] ボックスの一覧で、**受信者のアドレスが含まれています...** を選択します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-167">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="03ee9-168">**単語または語句を指定する**画面で、追加`junk@office365.microsoft.com`と`phish@office365.microsoft.com`、し、 **[ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-168">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span><br/><span data-ttu-id="03ee9-169">![ルールの迷惑メールおよびフィッシングの電子メール アドレスを指定します。](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span><span class="sxs-lookup"><span data-stu-id="03ee9-169">![Specify the junk and phish email addresses for the rule](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span></span><br/>
  
6. <span data-ttu-id="03ee9-170">**. 次の操作**の一覧の [ **、メッセージの [bcc] に...**。</span><span class="sxs-lookup"><span data-stu-id="03ee9-170">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="03ee9-171">グローバル管理者、セキュリティ管理者は、またはセキュリティ リーダーいる人が、マイクロソフトに報告する各電子メール メッセージのコピーを受信する必要があり、[ **ok]** を追加します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-171">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span><br/><span data-ttu-id="03ee9-172">![報告された各メッセージのコピーを受信するのにはグローバルまたはセキュリティ管理者を追加します。](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span><span class="sxs-lookup"><span data-stu-id="03ee9-172">![Add a global or security administrator to receive a copy of each reported message](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span></span><br/>
  
8. <span data-ttu-id="03ee9-173">**監査の重大度レベルでは、この規則**を選択し、 **[中]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-173">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="03ee9-174">[**この規則のモードの選択**を**強制する**を選択します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-174">Under **Choose a mode for this rule**, choose **Enforce**.</span></span><br/><span data-ttu-id="03ee9-175">![報告された各メッセージのコピーを取得するルールを設定します。](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span><span class="sxs-lookup"><span data-stu-id="03ee9-175">![Set up a rule to get a copy of each reported message](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span></span><br/>
  
10. <span data-ttu-id="03ee9-176">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="03ee9-176">Choose **Save**.</span></span> 
    
<span data-ttu-id="03ee9-p108">配置では、このルールが他の組織でアドインを使用して、レポート メッセージ、電子メール メッセージを報告するたびに、グローバル管理者、セキュリティ管理者、またはセキュリティ リーダーが表示されますがメッセージのコピー。この情報を使用して、セットアップまたは[Office 365 の ATP の安全なリンク](atp-safe-links.md)ポリシーなどのポリシーを調整することができます。</span><span class="sxs-lookup"><span data-stu-id="03ee9-p108">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message. This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies.</span></span> 

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="03ee9-179">確認またはレポート メッセージを追加の設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-179">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="03ee9-180">確認し、レポート メッセージ アドインの[サービスと [アドイン] ページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)で既定の設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="03ee9-180">You can review and edit the default settings for the Report Message Add-In in the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="03ee9-181">このタスクを完了するには、Office 365 のグローバル管理者またはオンラインの Exchange 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="03ee9-181">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="03ee9-182">[サービスおよびアドインのページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)に新しい Microsoft 365 の管理ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-182">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the new Microsoft 365 admin center.</span></span><br/><span data-ttu-id="03ee9-183">![新しい 365 管理センターでのサービスとアドインのページ](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="03ee9-183">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/>

2. <span data-ttu-id="03ee9-184">検索し、レポート メッセージ アドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-184">Find and select the Report Message Add-In.</span></span><br/>![検索し、レポート メッセージを追加で選択](media/FindReportMessageAddIn.png)<br/> 
    
3. <span data-ttu-id="03ee9-186">レポート メッセージ画面で、確認し、組織の必要に応じて設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-186">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span><br/>![レポート メッセージのアドインの設定](media/EditReportMessageAddIn.png)<br/> 

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="03ee9-188">レポート メッセージを追加で使用する方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-188">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="03ee9-189">[レポート メッセージの追加の使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03ee9-189">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="03ee9-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="03ee9-190">Related topics</span></span>

[<span data-ttu-id="03ee9-191">迷惑メール報告アドインを使用する</span><span class="sxs-lookup"><span data-stu-id="03ee9-191">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="03ee9-192">セキュリティで電子メールのセキュリティ レポートを表示する&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="03ee9-192">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="03ee9-193">Office 365 の高度な脅威保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="03ee9-193">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="03ee9-194">エクスプ ローラーを使用して、セキュリティで&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="03ee9-194">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  

