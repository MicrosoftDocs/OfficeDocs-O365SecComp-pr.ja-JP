---
title: レポート メッセージ アドインを有効にする
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 10/18/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: Outlook と Outlook は、個々 のユーザーまたは組織全体のメッセージのレポート アドインを有効にする方法を説明します。
ms.openlocfilehash: ad07d594a78b8134984b48f08898ad1ba697e03a
ms.sourcegitcommit: 49b565f6a57febe53f331b2605d6a06d11e2d0be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2018
ms.locfileid: "25638011"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="e3f7f-103">レポート メッセージ アドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="e3f7f-103">Enable the Report Message add-in</span></span>

## <a name="overview"></a><span data-ttu-id="e3f7f-104">概要</span><span class="sxs-lookup"><span data-stu-id="e3f7f-104">Overview</span></span>

<span data-ttu-id="e3f7f-p101">レポート メッセージを追加で、Outlook と Outlook Web 上で簡単に報告する misclassified メールは、安全なまたは悪意のあるかどうかマイクロソフトおよびその関連会社の分析のためにユーザーを使用できます。マイクロソフトでは、電子メール保護テクノロジの有効性を向上させるためにこれらの送信を使用します。さらに、 [Office 365 の高度な脅威保護](office-365-atp.md)または[Office 365 の脅威インテリジェンス](office-365-ti.md)組織を使用している場合、レポート メッセージを追加では、についての情報を確認および更新に使用できる、組織のセキュリティ チームセキュリティ ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-p101">The Report Message add-in for Outlook and Outlook on the Web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis. Microsoft uses these submissions to improve the effectiveness of email protection technologies. In addition, if your organization is using [Office 365 Advanced Threat Protection](office-365-atp.md) or [Office 365 Threat Intelligence](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="e3f7f-p102">たとえば、ユーザーがフィッシング メッセージの多くを報告するいるとします。この情報には、[ダッシュ ボードのセキュリティ](security-dashboard.md)およびその他のレポート内のサーフェスが。組織のセキュリティ チームは、フィッシング詐欺対策のポリシーを更新する必要がありますを示す値として、この情報を使用できます。または、ユーザーには、多くのメッセージのレポート アドインを使用して、迷惑メールと迷惑メールとしてフラグ付けされたメッセージが報告される場合、組織のセキュリティ チームが[迷惑メール対策ポリシー](configure-the-anti-spam-policies.md)を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-p102">For example, suppose that people are reporting a lot of messages as phishing. This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports. Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated. Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="e3f7f-112">レポート メッセージを追加では、Office 365 サブスクリプションと次の製品で動作します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-112">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="e3f7f-113">Web 上の outlook</span><span class="sxs-lookup"><span data-stu-id="e3f7f-113">Outlook on the Web</span></span>
 - <span data-ttu-id="e3f7f-114">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="e3f7f-114">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="e3f7f-115">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e3f7f-115">Outlook 2016</span></span>
 - <span data-ttu-id="e3f7f-116">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="e3f7f-116">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="e3f7f-117">Outlook を Office 365 用リソースに含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-117">Outlook included with Office 365 ProPlus</span></span>
  
<span data-ttu-id="e3f7f-118">個々 のユーザーの場合、[自分のメッセージのレポート アドインを有効に](#get-the-report-message-add-in-for-yourself)することができます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-118">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="e3f7f-119">オンラインの Exchange 管理者である、[組織のメッセージのレポート アドインを有効に](#get-and-enable-the-report-message-add-in-for-your-organization)できます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-119">If you're an Exchange Online administrator, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="e3f7f-120">自分用の追加のレポート メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-120">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="e3f7f-121">[Office を格納](https://appsource.microsoft.com/product/office/WA104381180?src=office)する、追加のレポート メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-121">In the [Office store](https://appsource.microsoft.com/product/office/WA104381180?src=office), get the Report Message add-in.</span></span>
    
2. <span data-ttu-id="e3f7f-122">選択**を取得ここでの IT**です。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-122">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="e3f7f-123">![メッセージを報告する-今すぐ](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="e3f7f-123">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="e3f7f-p103">使用およびプライバシー ポリシーの条件を確認します。**続行**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-p103">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="e3f7f-126">作業または学校アカウント (業務用) または Microsoft アカウント (個人向け) を使用して、Office 365 の電子メールにサインインします。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-126">Sign in to your Office 365 email using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    

<span data-ttu-id="e3f7f-127">アドインがインストールされており後、は、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-127">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="e3f7f-128">Outlook では、次のように、アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-128">In Outlook the icon looks like this:</span></span> <br/> ![Outlook 用アドインのメッセージのアイコンをレポート](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="e3f7f-130">Outlook Web App では、次のように、アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-130">In Outlook Web App the icon looks like this:</span></span><br/>![Outlook アドインの Web レポートのメッセージのアイコンを](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

<span data-ttu-id="e3f7f-132">については、次のステップとして[、レポート メッセージのアドインを使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)する方法です。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-132">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="e3f7f-133">取得し、レポート メッセージ用のアドインの組織を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-133">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3f7f-134">このタスクを完了するには、Office 365 のグローバル管理者またはオンラインの Exchange 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-134">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>

1. <span data-ttu-id="e3f7f-135">[https://portal.office.com](https://portal.office.com)し、職場、学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-135">Go to [https://portal.office.com](https://portal.office.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="e3f7f-136">管理センターにアクセスする**管理者**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-136">Choose **Admin** to go to the Admin center.</span></span> 
    
3. <span data-ttu-id="e3f7f-137">**管理センター**を選択して\> **Exchange**を Exchange 管理センター (EAC) に移動します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-137">Choose **Admin centers** \> **Exchange** to go to the Exchange admin center (EAC).</span></span> 
    
4. <span data-ttu-id="e3f7f-138">**組織**を選択して\>**のアドインを使用**します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-138">Choose **organization** \> **add-ins**.</span></span> 
    
5. <span data-ttu-id="e3f7f-139">選択**+**  >  **Office ストアから追加**します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-139">Choose **+** > **Add from the Office Store**.</span></span><br/><span data-ttu-id="e3f7f-140">![選択 Office ストアから追加](media/EAC-Org-AddFromOfficeStore.png)</span><span class="sxs-lookup"><span data-stu-id="e3f7f-140">![Choose Add from the Office Store](media/EAC-Org-AddFromOfficeStore.png)</span></span><br/><span data-ttu-id="e3f7f-141">Office ストア、web ブラウザーで開きます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-141">This opens the Office Store in your web browser.</span></span>
    
6. <span data-ttu-id="e3f7f-142">レポート メッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-142">Search for Report Message.</span></span><br/>![レポート メッセージの検索](media/ReportMessageSearchOfficeStore.png)<br/>
    
7. <span data-ttu-id="e3f7f-144">**アプリ**一覧で、**レポート メッセージ**を選択して、 **IT を取得するようになりました**。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-144">In the **Apps** list, select **Report Message**, and then choose **GET IT NOW**.</span></span><br/><span data-ttu-id="e3f7f-145">![取得を選択して IT のようになりました](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="e3f7f-145">![Choose GET IT NOW](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
8. <span data-ttu-id="e3f7f-p104">使用およびプライバシー ポリシーの条件を確認します。**続行**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-p104">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
    ![プライバシー ポリシーに同意して続行] をクリックします。](media/ReportMessageTermsAndConditions.png)
  
9. <span data-ttu-id="e3f7f-p105">レポート メッセージのアドインを確認の情報を構成し、続行するのには**次**に選択するためにウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-p105">A wizard opens to help you configure the Report Message add-in. Review the information, and choose **Next** to continue.</span></span><br/><span data-ttu-id="e3f7f-151">![Office 365 のアドイン ウィザードのメッセージを報告します。](media/ReportMessageAdminInstallUI.png)</span><span class="sxs-lookup"><span data-stu-id="e3f7f-151">![Report Message add-in wizard for Office 365](media/ReportMessageAdminInstallUI.png)</span></span><br/> 

10. <span data-ttu-id="e3f7f-152">ようにするが、レポート メッセージのアドインの既定の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-152">Specify the default setting you want users to have for the Report Message add-in.</span></span><br/>![レポート メッセージのアドインの既定の設定を指定します。](media/ReportMessageUserOptionsAdminsSet.png)<br/>
    
11. <span data-ttu-id="e3f7f-154">追加のレポート メッセージを取得するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-154">Specify who gets the Report Message add-in.</span></span> <br/>![追加のレポート メッセージを取得するを指定します。](media/ReportMessageChooseWhoGetsItAdminSettings.png)<br/>

12. <span data-ttu-id="e3f7f-156">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-156">Choose **Save**.</span></span> <br/>
> [!TIP]
> <span data-ttu-id="e3f7f-157">[ユーザーから報告された電子メール メッセージのコピーを取得するルールの設定](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)を推奨します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-157">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)</span></span>

<span data-ttu-id="e3f7f-p106">によってどのような選択したウィザードを使用して、組織内のユーザー[レポート メッセージのアドインを](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)使用できるがあります。組織内のユーザーは、次のアイコンで表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-p106">Depending on what you selected using the wizard, people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available. People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="e3f7f-160">Outlook では、次のように、アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-160">In Outlook the icon looks like this:</span></span> <br/> ![Outlook 用アドインのメッセージのアイコンをレポート](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="e3f7f-162">Outlook Web App では、次のように、アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-162">In Outlook Web App the icon looks like this:</span></span><br/>![Outlook アドインの Web レポートのメッセージのアイコンを](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="e3f7f-164">ルールの設定、ユーザーから報告された電子メール メッセージのコピーを取得するには</span><span class="sxs-lookup"><span data-stu-id="e3f7f-164">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3f7f-165">このタスクを実行するのには、Exchange にアクセスする権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-165">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="e3f7f-p107">ルールを設定するには、組織内のユーザーによって報告された電子メール メッセージのコピーを取得します。ダウンロードし、組織のメッセージのレポート アドインを有効にした後に行います。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-p107">You can set up a rule to get a copy of email messages reported by users in your organization. You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="e3f7f-168">**メール フロー**を選択して、EAC で\>**の規則**。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-168">In the EAC, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="e3f7f-169">選択**+** \> **新しい規則を作成**します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-169">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="e3f7f-170">**[名前**] ボックスで、提出書類などの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-170">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="e3f7f-171">**場合にこのルールを適用**] ボックスの一覧で、**受信者のアドレスが含まれています...** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-171">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="e3f7f-172">**単語または語句を指定する**画面で、junk@office365.microsoft.com と phish@office365.microsoft.com を追加し、[ **ok]** します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-172">In the **specify words or phrases** screen, add junk@office365.microsoft.com and phish@office365.microsoft.com, and then choose **OK**.</span></span> 
    
    ![ルールの迷惑メールおよびフィッシングの電子メール アドレスを指定します。](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)
  
6. <span data-ttu-id="e3f7f-174">**. 次の操作**の一覧の [ **、メッセージの [bcc] に...**。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-174">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="e3f7f-175">グローバル管理者、セキュリティ管理者は、またはセキュリティ リーダーいる人が、マイクロソフトに報告する各電子メール メッセージのコピーを受信する必要があり、[ **ok]** を追加します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-175">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span> 
    
    ![報告された各メッセージのコピーを受信するのにはグローバルまたはセキュリティ管理者を追加します。](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)
  
8. <span data-ttu-id="e3f7f-177">**監査の重大度レベルでは、この規則**を選択し、 **[中]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-177">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="e3f7f-178">[**この規則のモードの選択**を**強制する**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-178">Under **Choose a mode for this rule**, choose **Enforce**.</span></span> 
    
    ![報告された各メッセージのコピーを取得するルールを設定します。](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)
  
10. <span data-ttu-id="e3f7f-180">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-180">Choose **Save**.</span></span> 
    
<span data-ttu-id="e3f7f-p108">配置では、このルールが他の組織でアドインを使用して、レポート メッセージ、電子メール メッセージを報告するたびに、グローバル管理者、セキュリティ管理者、またはセキュリティ リーダーが表示されますがメッセージのコピー。この情報を使用して、セットアップまたは[Office 365 の ATP の安全なリンク](atp-safe-links.md)ポリシーなどのポリシーを調整することができます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-p108">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message. This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies.</span></span> 

## <a name="review-or-edit-the-default-settings-for-the-report-message-add-in"></a><span data-ttu-id="e3f7f-183">確認またはレポート メッセージを追加での既定の設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-183">Review or edit the default settings for the Report Message add-in</span></span>

<span data-ttu-id="e3f7f-184">確認し、管理センターを使用してメッセージのレポート アドインの既定の設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-184">You can review and edit the default settings for the Report Message add-in using the Admin Center.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e3f7f-185">このタスクを完了するには、Office 365 のグローバル管理者またはオンラインの Exchange 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-185">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="e3f7f-p109">だけをインストールするレポート メッセージを追加で、組織の場合は、既にになりますサービスおよびアドインのページです。それ以外の場合は、[ここで](https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns)し、職場、学校のアカウントを使用して Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-p109">If you've just installed the Report Message add-in for your organization, you'll already be on the Services & add-ins page. Otherwise, go [here](https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns) and sign in using your work or school account for Office 365.</span></span>

2. <span data-ttu-id="e3f7f-188">**レポート メッセージ**は、検索し、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-188">Search for **Report Message**, and then select it.</span></span><br/><span data-ttu-id="e3f7f-189">![サービスと Office 365 用のアドイン](media/ReportMessage-o365servicesaddins.png)</span><span class="sxs-lookup"><span data-stu-id="e3f7f-189">![Services and add-ins for Office 365](media/ReportMessage-o365servicesaddins.png)</span></span><br/> 
    
3. <span data-ttu-id="e3f7f-190">ウィンドウが開き、展開時にレポート メッセージを追加で選択された設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-190">A pane opens that displays the settings that were selected for the Report Message add-in during deployment.</span></span><br/>![レポート メッセージのアドインの設定](media/ReportMessage-reviewaddinsettings.png)<br/> 

4. <span data-ttu-id="e3f7f-192">確認し、必要な場合、レポート メッセージ アドインの設定を編集し、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-192">Review and if needed, edit settings for the Report Message add-in, and then save your changes.</span></span>
    
## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="e3f7f-193">レポート メッセージを追加で使用する方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-193">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="e3f7f-194">[レポート メッセージの追加の使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-194">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e3f7f-195">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e3f7f-195">Related topics</span></span>

[<span data-ttu-id="e3f7f-196">迷惑メール報告アドインを使用する</span><span class="sxs-lookup"><span data-stu-id="e3f7f-196">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="e3f7f-197">セキュリティで電子メールのセキュリティ レポートを表示する&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="e3f7f-197">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="e3f7f-198">Office 365 の高度な脅威保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="e3f7f-198">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="e3f7f-199">エクスプ ローラーを使用して、セキュリティで&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="e3f7f-199">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  

