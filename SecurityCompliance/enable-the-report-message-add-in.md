---
title: レポート メッセージ アドインを有効にする
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 03/26/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 個々のユーザーまたは組織全体で、Outlook および outlook on the web 用のレポートメッセージアドインを有効にする方法について説明します。
ms.openlocfilehash: 2c1fe3afd52afed17327a4ad2a5a493721b541fd
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599973"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="f261a-103">レポート メッセージ アドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="f261a-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="f261a-104">Outlook および outlook on the web 用のレポートメッセージアドインは、 [Outlook 迷惑メールフィルター](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)とまったく同じではありませんが、両方を使用して、電子メールを迷惑メール、迷惑メールではないメールとしてマークしたり、フィッシングを試行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f261a-104">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt.</span></span> <span data-ttu-id="f261a-105">違いは、Outlook 用のレポートメッセージアドインと web 上の Outlook は、分類された電子メールの誤通知を Microsoft に通知するのに対して、Outlook の迷惑メールフィルターを使用してユーザーのメールボックス内の電子メールメッセージを整理しています。</span><span class="sxs-lookup"><span data-stu-id="f261a-105">The difference is, the Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span> 

## <a name="overview"></a><span data-ttu-id="f261a-106">概要</span><span class="sxs-lookup"><span data-stu-id="f261a-106">Overview</span></span>

<span data-ttu-id="f261a-107">Outlook 用のレポートメッセージアドインと web 上の Outlook を使用すると、ユーザーは、安全であるか悪意のある電子メールであっても、分析のために Microsoft と関連会社に対して、誤った分類されたメールを簡単に報告できます。</span><span class="sxs-lookup"><span data-stu-id="f261a-107">The Report Message add-in for Outlook and Outlook on the web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="f261a-108">Microsoft では、これらの送信を使用して、電子メール保護テクノロジの有効性を向上させています。</span><span class="sxs-lookup"><span data-stu-id="f261a-108">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="f261a-109">さらに、組織で[Office 365 Advanced Threat Protection プラン 1](office-365-atp.md)または[Plan 2](office-365-ti.md)を使用している場合は、レポートメッセージアドインにより、組織のセキュリティチームに対して、セキュリティポリシーの確認と更新に使用できる有用な情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f261a-109">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="f261a-110">たとえば、ユーザーが大量のメッセージをフィッシングとして報告しているとします。</span><span class="sxs-lookup"><span data-stu-id="f261a-110">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="f261a-111">この情報は、[セキュリティダッシュボード](security-dashboard.md)やその他のレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f261a-111">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="f261a-112">組織のセキュリティチームは、この情報を、フィッシング対策ポリシーの更新が必要になる可能性があることを示すものとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="f261a-112">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="f261a-113">または、レポートメッセージアドインを使用して迷惑メールではないというフラグが付いたメッセージを多数報告している場合は、組織のセキュリティチームが[スパム対策ポリシー](configure-the-anti-spam-policies.md)を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f261a-113">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="f261a-114">レポートメッセージアドインは、Office 365 サブスクリプションと、次の製品で機能します。</span><span class="sxs-lookup"><span data-stu-id="f261a-114">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="f261a-115">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="f261a-115">Outlook on the web</span></span>
 - <span data-ttu-id="f261a-116">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="f261a-116">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="f261a-117">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f261a-117">Outlook 2016</span></span>
 - <span data-ttu-id="f261a-118">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="f261a-118">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="f261a-119">Office 365 ProPlus に含まれている Outlook</span><span class="sxs-lookup"><span data-stu-id="f261a-119">Outlook included with Office 365 ProPlus</span></span>

<span data-ttu-id="f261a-120">既存の web ブラウザーでは、レポートメッセージアドインが動作するように十分である必要があります。ただし、アドインが使用できない、または正常に動作しないことが判明した場合は、別のブラウザーを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="f261a-120">Your existing web browser should suffice for the Report Message add-in to work; however, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>
  
<span data-ttu-id="f261a-121">個人ユーザーの場合は、[レポートメッセージアドインを自分自身に対して有効に](#get-the-report-message-add-in-for-yourself)することができます。</span><span class="sxs-lookup"><span data-stu-id="f261a-121">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="f261a-122">Office 365 の全体管理者または Exchange Online 管理者であり、Exchange が OAuth 認証を使用するように構成されている場合は、[組織に対してレポートメッセージアドインを有効](#get-and-enable-the-report-message-add-in-for-your-organization)にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f261a-122">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="f261a-123">これで、レポートメッセージアドインが[一元展開](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)によって利用可能になりました。</span><span class="sxs-lookup"><span data-stu-id="f261a-123">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="f261a-124">自分用のレポートメッセージアドインを取得する</span><span class="sxs-lookup"><span data-stu-id="f261a-124">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="f261a-125">[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)で、[レポートメッセージアドイン](https://appsource.microsoft.com/product/office/wa104381180)を検索します。</span><span class="sxs-lookup"><span data-stu-id="f261a-125">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="f261a-126">[**今すぐ取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-126">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="f261a-127">![レポートメッセージ-今すぐ取得](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="f261a-127">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="f261a-128">使用条件とプライバシーポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="f261a-128">Review the terms of use and privacy policy.</span></span> <span data-ttu-id="f261a-129">[ **Continue**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f261a-129">Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="f261a-130">職場または学校アカウントを使用して Office 365 にサインインします (一般法人向け)。または Microsoft アカウント (個人使用)。</span><span class="sxs-lookup"><span data-stu-id="f261a-130">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    
<span data-ttu-id="f261a-131">アドインがインストールされて有効になると、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f261a-131">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="f261a-132">Outlook のアイコンは、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="f261a-132">In Outlook, the icon looks like this:</span></span> <br/> ![Outlook のレポートメッセージアドインアイコン](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="f261a-134">Web 上の Outlook (旧称 Outlook Web App) では、アイコンは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f261a-134">In Outlook on the web (formerly known as Outlook Web App), the icon looks like this:</span></span><br/>![Outlook on the web レポートメッセージアドインアイコン](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="f261a-136">次の手順として、[レポートメッセージアドインの使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f261a-136">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="f261a-137">組織のレポートメッセージアドインを取得して有効にする</span><span class="sxs-lookup"><span data-stu-id="f261a-137">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f261a-138">このタスクを完了するには、Office 365 の全体管理者または Exchange Online 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f261a-138">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span> <span data-ttu-id="f261a-139">また、詳細については、OAuth 認証を使用するように Exchange を構成する必要があります。詳細については、「 [exchange の要件 (アドインの一元展開)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f261a-139">In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span> 

1. <span data-ttu-id="f261a-140">Microsoft 365 管理センターの [[サービス & アドイン] ページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)に移動します。</span><span class="sxs-lookup"><span data-stu-id="f261a-140">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="f261a-141">![新しい Microsoft 365 管理センターの [サービスとアドイン] ページ](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="f261a-141">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/> 
    
2. <span data-ttu-id="f261a-142">[ **+ アドインの展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-142">Choose **+ Deploy Add-in**.</span></span><br/><span data-ttu-id="f261a-143">![[アドインの展開] を選択する](media/ServicesAddIns-ChooseDeployAddIn.png)</span><span class="sxs-lookup"><span data-stu-id="f261a-143">![Choose Deploy Add-In](media/ServicesAddIns-ChooseDeployAddIn.png)</span></span><br/> 
    
3. <span data-ttu-id="f261a-144">[**新しいアドイン**] 画面で情報を確認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-144">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="f261a-145">![新しいアドインの詳細](media/NewAddInScreen1.png)</span><span class="sxs-lookup"><span data-stu-id="f261a-145">![New Add-In details](media/NewAddInScreen1.png)</span></span><br/>
    
4. <span data-ttu-id="f261a-146">[ **Office ストアからアドインを追加**する] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-146">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span><br/><span data-ttu-id="f261a-147">![新しいアドインを追加する](media/NewAddInScreen2.png)</span><span class="sxs-lookup"><span data-stu-id="f261a-147">![I want to add an new Add-In](media/NewAddInScreen2.png)</span></span><br/> 
    
5. <span data-ttu-id="f261a-148">**レポートメッセージ**を検索し、結果の一覧で、[**レポートメッセージアドイン**] の横にある [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-148">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span><br/><span data-ttu-id="f261a-149">![レポートメッセージを検索し、[追加] を選択します。](media/NewAddInScreen3.png)</span><span class="sxs-lookup"><span data-stu-id="f261a-149">![Search for Report Message and then choose Add](media/NewAddInScreen3.png)</span></span><br/>
    
6. <span data-ttu-id="f261a-150">[**レポートメッセージ**] 画面で情報を確認し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-150">On the **Report Message** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="f261a-151">![レポートメッセージの詳細](media/ReportMessageAdd-InNewScreen4.png)</span><span class="sxs-lookup"><span data-stu-id="f261a-151">![Report Message details](media/ReportMessageAdd-InNewScreen4.png)</span></span><br/>

7. <span data-ttu-id="f261a-152">Outlook のユーザーの既定の設定を指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f261a-152">Specify the user default settings for Outlook, and  then choose **Next**.</span></span><br/><span data-ttu-id="f261a-153">![Outlook の既定のレポートメッセージ設定](media/ReportMessageOptionsScreen5.png)</span><span class="sxs-lookup"><span data-stu-id="f261a-153">![Report Message default settings for Outlook](media/ReportMessageOptionsScreen5.png)</span></span><br/>

8. <span data-ttu-id="f261a-154">レポートメッセージアドインを取得するユーザーを指定し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-154">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span> <br/><span data-ttu-id="f261a-155">![レポートメッセージアドインを取得するユーザー](media/ReportMessageOptionsScreen6.png)</span><span class="sxs-lookup"><span data-stu-id="f261a-155">![Who gets the Report Message add-in](media/ReportMessageOptionsScreen6.png)</span></span><br/>

> [!TIP]
> <span data-ttu-id="f261a-156">[ユーザーによって報告された電子メールメッセージのコピーを取得するルールを設定することを](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)お勧めします。</span><span class="sxs-lookup"><span data-stu-id="f261a-156">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="f261a-157">アドインのセットアップ時に選択した内容に応じて (上記の手順 7-8)、組織内のユーザーが[レポートメッセージアドイン](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f261a-157">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available.</span></span> <span data-ttu-id="f261a-158">組織内のユーザーには、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f261a-158">People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="f261a-159">Outlook のアイコンは、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="f261a-159">In Outlook, the icon looks like this:</span></span> <br/> ![Outlook のレポートメッセージアドインアイコン](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="f261a-161">Web 上の Outlook では、アイコンは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f261a-161">In Outlook on the web, the icon looks like this:</span></span><br/>![Outlook on the Web レポートメッセージアドインアイコン](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="f261a-163">レポートメッセージアドインについてユーザーに通知する場合は、[レポートメッセージアドインを使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)するためのリンクを含めます。</span><span class="sxs-lookup"><span data-stu-id="f261a-163">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="f261a-164">ユーザーによって報告された電子メールメッセージのコピーを取得するルールを設定する</span><span class="sxs-lookup"><span data-stu-id="f261a-164">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f261a-165">このタスクを実行するには、Exchange Online の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f261a-165">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="f261a-166">組織内のユーザーによって報告された電子メールメッセージのコピーを取得するルールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f261a-166">You can set up a rule to get a copy of email messages reported by users in your organization.</span></span> <span data-ttu-id="f261a-167">この操作は、組織でレポートメッセージアドインをダウンロードして有効にした後に行います。</span><span class="sxs-lookup"><span data-stu-id="f261a-167">You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="f261a-168">Exchange 管理センターで、[**メールフロー** \> **ルール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-168">In the Exchange admin center, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="f261a-169">[ **+** \> **新しいルールを作成する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-169">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="f261a-170">[**名前**] ボックスに、「送信」などの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f261a-170">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="f261a-171">[**このルールを適用する条件**] ボックスの一覧で、[**受信者のアドレス**を選択してください...] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-171">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="f261a-172">[**単語または語句の指定**] 画面`junk@office365.microsoft.com`で`phish@office365.microsoft.com`、とを追加し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-172">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span><br/><span data-ttu-id="f261a-173">![ルールの迷惑メールアドレスとフィッシングメールアドレスを指定する](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span><span class="sxs-lookup"><span data-stu-id="f261a-173">![Specify the junk and phish email addresses for the rule](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span></span><br/>
  
6. <span data-ttu-id="f261a-174">[**実行する処理...** ] の一覧で、[**メッセージの Bcc**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-174">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="f261a-175">ユーザーが Microsoft に報告する各電子メールメッセージのコピーを受信する必要のある全体管理者、セキュリティ管理者、およびセキュリティ閲覧者を追加し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-175">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span><br/><span data-ttu-id="f261a-176">![グローバルまたはセキュリティ管理者を追加して、報告された各メッセージのコピーを受信する](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span><span class="sxs-lookup"><span data-stu-id="f261a-176">![Add a global or security administrator to receive a copy of each reported message](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span></span><br/>
  
8. <span data-ttu-id="f261a-177">[**このルールを次の重大度レベルで監査**する] を選択し、[**中**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-177">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="f261a-178">[**このルールのモードの選択**] で、[**強制**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-178">Under **Choose a mode for this rule**, choose **Enforce**.</span></span><br/><span data-ttu-id="f261a-179">![レポートされた各メッセージのコピーを取得するルールを設定する](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span><span class="sxs-lookup"><span data-stu-id="f261a-179">![Set up a rule to get a copy of each reported message](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span></span><br/>
  
10. <span data-ttu-id="f261a-180">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-180">Choose **Save**.</span></span> 
    
<span data-ttu-id="f261a-181">このルールが設定されている場合、組織内のユーザーがレポートメッセージアドインを使用して電子メールメッセージを報告するたびに、全体管理者、セキュリティ管理者、セキュリティリーダがそのメッセージのコピーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f261a-181">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message.</span></span> <span data-ttu-id="f261a-182">この情報を使用すると、 [Office 365 の ATP の安全なリンク](atp-safe-links.md)ポリシー、または[スパム対策](anti-spam-protection.md)の設定などのポリシーを設定または調整することができます。</span><span class="sxs-lookup"><span data-stu-id="f261a-182">This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span> 

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="f261a-183">レポートメッセージアドインの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f261a-183">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="f261a-184">「[レポートメッセージアドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f261a-184">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="f261a-185">レポートメッセージアドインの設定を確認または編集する</span><span class="sxs-lookup"><span data-stu-id="f261a-185">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="f261a-186">[[サービス & アドイン] ページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)で、レポートメッセージアドインの既定の設定を確認および編集できます。</span><span class="sxs-lookup"><span data-stu-id="f261a-186">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="f261a-187">このタスクを完了するには、Office 365 の全体管理者または Exchange Online 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f261a-187">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="f261a-188">Microsoft 365 管理センターの [[サービス & アドイン] ページ](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)に移動します。</span><span class="sxs-lookup"><span data-stu-id="f261a-188">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="f261a-189">![新しい Microsoft 365 管理センターの [サービスとアドイン] ページ](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="f261a-189">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/>

2. <span data-ttu-id="f261a-190">レポートメッセージアドインを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="f261a-190">Find and select the Report Message add-in.</span></span><br/>![レポートメッセージアドインを検索して選択する](media/FindReportMessageAddIn.png)<br/> 
    
3. <span data-ttu-id="f261a-192">[レポートメッセージ] 画面で、組織に合わせて設定を確認して編集します。</span><span class="sxs-lookup"><span data-stu-id="f261a-192">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span><br/>![レポートメッセージアドインの設定](media/EditReportMessageAddIn.png)<br/> 

## <a name="related-topics"></a><span data-ttu-id="f261a-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="f261a-194">Related topics</span></span>

[<span data-ttu-id="f261a-195">レポートメッセージアドインを使用する</span><span class="sxs-lookup"><span data-stu-id="f261a-195">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="f261a-196">セキュリティ&amp; /コンプライアンスセンターで電子メールのセキュリティレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="f261a-196">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="f261a-197">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="f261a-197">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="f261a-198">セキュリティ&amp; /コンプライアンスセンターのエクスプローラーを使用する</span><span class="sxs-lookup"><span data-stu-id="f261a-198">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  

