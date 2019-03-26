---
title: セキュリティ&amp; /コンプライアンスセンターで脅威エクスプローラーを使用する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/21/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: セキュリティ&amp; /コンプライアンスセンターのエクスプローラー (脅威エクスプローラーとも呼ばれます) について説明します。
ms.openlocfilehash: 202898873bb9611c747aed335d295c749c7cd0fa
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "30732260"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="851d9-103">セキュリティ&amp; /コンプライアンスセンターで脅威エクスプローラーを使用する</span><span class="sxs-lookup"><span data-stu-id="851d9-103">Use Threat Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="851d9-104">組織に[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md)があり、必要なアクセス許可を持っている場合は、脅威エクスプローラーを使用して脅威を特定して分析することができます。</span><span class="sxs-lookup"><span data-stu-id="851d9-104">If your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md), and you have the necessary permissions, you can use Threat Explorer to identify and analyze threats.</span></span> <span data-ttu-id="851d9-105">たとえば、配信された悪意のある電子メールを特定して削除したり、Office 365 セキュリティ機能によって検出されたマルウェアを確認したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="851d9-105">For example, you can identify and delete malicious email that was delivered, or see malware that was caught by Office 365 security features.</span></span> <span data-ttu-id="851d9-106">脅威エクスプローラー (エクスプローラーとも呼ばれます) は、セキュリティ運用チームがセキュリティ&amp;コンプライアンスセンターで脅威を調査して対応するのに役立つ、ほぼリアルタイムの強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="851d9-106">Threat Explorer (also referred to as Explorer) is a powerful near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span>
  
![[脅威管理\>エクスプローラー] に移動します。](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="851d9-108">エクスプローラーを使用するには、 &amp;セキュリティ/コンプライアンスセンターで、[**脅威管理** \> **エクスプローラー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="851d9-108">To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="851d9-109">office 365 脅威インテリジェンスは office 365 Advanced threat protection プラン2に加えて、追加の脅威保護機能と共に提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="851d9-109">Office 365 Threat Intelligence is now Office 365 Advanced Threat Protection Plan 2, along with additional threat protection capabilities.</span></span> <span data-ttu-id="851d9-110">詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="851d9-110">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
      
## <a name="explorer-overview"></a><span data-ttu-id="851d9-111">エクスプローラーの概要</span><span class="sxs-lookup"><span data-stu-id="851d9-111">Explorer overview</span></span>

<span data-ttu-id="851d9-112">組織に[Office 365 の脅威の調査と応答機能](office-365-ti.md)(ATP Plan 2 に含まれています) があり、必要なアクセス許可がある場合は、脅威エクスプローラー (エクスプローラーとも呼ばれます) を使用して脅威を識別して分析することができます。</span><span class="sxs-lookup"><span data-stu-id="851d9-112">If your organization has [Office 365 Threat investigation and response capabilities](office-365-ti.md) (this is included in ATP Plan 2), and you have the necessary permissions, you can use Threat Explorer (also referred to as Explorer) to identify and analyze threats.</span></span> <span data-ttu-id="851d9-113">(セキュリティ&amp;コンプライアンスセンターで、[**脅威管理** \> **エクスプローラー**] に移動します)。</span><span class="sxs-lookup"><span data-stu-id="851d9-113">(In the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.)</span></span>

![[脅威管理\>エクスプローラー] に移動します。](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="851d9-115">この記事では、エクスプローラーで実行できるいくつかの操作について説明します (多くの可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="851d9-115">This article describes a few things you can do with Explorer (there are many more possibilities):</span></span>

- <span data-ttu-id="851d9-116">[電子メールで検出されたマルウェアの種類](#see-malware-detected-in-email-by-technology)、および脅威保護テクノロジ (マルウェア対策保護、ATP の安全な添付ファイルなど) について説明します。</span><span class="sxs-lookup"><span data-stu-id="851d9-116">[See what kinds of malware were detected in email](#see-malware-detected-in-email-by-technology), and by threat protection technology (anti-malware protection, ATP Safe Attachments, etc.)</span></span>

- <span data-ttu-id="851d9-117">[フィッシングリンク (url) に関するデータ](#view-data-about-phishing-urls-and-click-verdict)、およびクリック verdicts がどのようなものか (警告が発生しても、ブロック、許可、またはアクセスした url) を表示します。</span><span class="sxs-lookup"><span data-stu-id="851d9-117">[View data about phishing links (URLs)](#view-data-about-phishing-urls-and-click-verdict), and what the click verdicts were (URLs blocked, allowed, or visited despite warnings)</span></span>

- <span data-ttu-id="851d9-118">迷惑[メール (迷惑メールではない) として報告された電子メールメッセージを確認](#review-email-messages-reported-by-users)し、傾向 (通常はフィッシングとして報告されるメッセージ数の大きいなど) を特定します。</span><span class="sxs-lookup"><span data-stu-id="851d9-118">[Review email messages that were reported as Junk, Not Junk, or Phishing](#review-email-messages-reported-by-users), and identify any trends (such as a larger than usual number of messages reported as Phish)</span></span> 

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="851d9-119">テクノロジによる電子メールで検出されたマルウェアを参照</span><span class="sxs-lookup"><span data-stu-id="851d9-119">See malware detected in email by technology</span></span>

<span data-ttu-id="851d9-120">電子メールで検出されたマルウェアと Office 365 のテクノロジについて確認する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="851d9-120">Suppose you want to see malware that was detected in email, and by what technology in Office 365.</span></span> <span data-ttu-id="851d9-121">これを行うには、エクスプローラーの [ [Email > マルウェア](threat-explorer-views.md#email--malware)] ビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="851d9-121">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer.</span></span>

1. <span data-ttu-id="851d9-122">Office 365[https://protection.office.com](https://protection.office.com)セキュリティ & コンプライアンスセンター () で、[**脅威管理** > **エクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="851d9-122">In the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="851d9-123">[**表示**] メニューで、[**電子メール** > **マルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="851d9-123">In the **View** menu, choose **Email** > **Malware**.</span></span><br/><span data-ttu-id="851d9-124">![エクスプローラーの [表示] メニュー](media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="851d9-124">![View menu for Explorer](media/ExplorerViewEmailMalwareMenu.png)</span></span><br/>
3. <span data-ttu-id="851d9-125">[**送信者**] をクリックし、[**基本** > **検出テクノロジ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="851d9-125">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span><br/><span data-ttu-id="851d9-126">これで、検出テクノロジがレポートのフィルターとして使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="851d9-126">Your detection technologies are now available as filters for the report.</span></span><br/><span data-ttu-id="851d9-127">![マルウェア検出テクノロジ](media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="851d9-127">![Malware detection technologies](media/ExplorerEmailMalwareDetectionTech.png)</span></span><br/> 
4. <span data-ttu-id="851d9-128">オプションを選択し、[更新] ボタンをクリックしてそのフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="851d9-128">Select an option, and then click the Refresh button to apply that filter.</span></span><br/>![選択されている検出テクノロジ](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

<span data-ttu-id="851d9-130">レポートが更新され、選択した [テクノロジ] オプションを使用して、電子メールで検出された結果のマルウェアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="851d9-130">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="851d9-131">ここから、さらに分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="851d9-131">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="851d9-132">フィッシング url に関するデータを表示し、[verdict] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="851d9-132">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="851d9-133">許可された url の一覧を含む電子メール内の url を使用して、許可され、ブロックされ、上書きされたフィッシングを表示する場合を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="851d9-133">Suppose you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="851d9-134">これを行うには、エクスプローラーの [ [Email > フィッシング](threat-explorer-views.md#email--phish)] ビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="851d9-134">To do this, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer.</span></span>

1. <span data-ttu-id="851d9-135">Office 365[https://protection.office.com](https://protection.office.com)セキュリティ & コンプライアンスセンター () で、[**脅威管理** > **エクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="851d9-135">In the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="851d9-136">[**表示**] メニューの [**電子メール** > **フィッシング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="851d9-136">In the **View** menu, choose **Email** > **Phish**.</span></span><br/><span data-ttu-id="851d9-137">![エクスプローラーの [表示] メニュー](media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="851d9-137">![View menu for Explorer](media/ExplorerViewEmailPhishMenu.png)</span></span><br/>
3. <span data-ttu-id="851d9-138">[**送信者**] をクリックし、[ **url** > ] を選択して、**[verdict] をクリック**します。</span><span class="sxs-lookup"><span data-stu-id="851d9-138">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>
4. <span data-ttu-id="851d9-139">1つ以上のオプション ([**ブロック**されてブロックされた**ブロック**] など) を選択し、[**更新**] ボタンをクリックしてそのフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="851d9-139">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button to apply that filter.</span></span><br/><span data-ttu-id="851d9-140">![url および [verdicts] をクリックします。](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="851d9-140">![URLs and click verdicts](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span><br/>

<span data-ttu-id="851d9-141">レポートが更新され、電子メールの配信状態と共に、検出された (または警告に関係していても表示されている) 電子メールで検出されたフィッシング url が表示されます</span><span class="sxs-lookup"><span data-stu-id="851d9-141">The report refreshes to show detected phishing URLs in email that were blocked (or visited despite a warning), along with email delivery status.</span></span> <span data-ttu-id="851d9-142">ここから、さらに分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="851d9-142">From here, you can conduct further analysis.</span></span> <span data-ttu-id="851d9-143">たとえば、グラフの下に、組織の電子メールでブロックされた上位の url が表示されます。</span><span class="sxs-lookup"><span data-stu-id="851d9-143">For example, below the chart, you can see the top URLs that were blocked in your organization's email.</span></span> 

![ブロックされたエクスプローラーの url](media/ExplorerPhishClickVerdictURLs.png) 

<span data-ttu-id="851d9-145">URL を選択して、詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="851d9-145">Select a URL to view more detailed information.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="851d9-146">ユーザーが報告した電子メールメッセージを確認する</span><span class="sxs-lookup"><span data-stu-id="851d9-146">Review email messages reported by users</span></span>

<span data-ttu-id="851d9-147">組織内のユーザーが、 [outlook 用のレポートメッセージアドインと web 上の outlook](enable-the-report-message-add-in.md)を使用して、迷惑メールではなく迷惑メールとして報告した電子メールメッセージを表示したいとします。</span><span class="sxs-lookup"><span data-stu-id="851d9-147">Suppose you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="851d9-148">これを行うには、> のエクスプローラーの[ユーザーレポート](threat-explorer-views.md#email--user-reported)ビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="851d9-148">To do this, use the [Email > User-reported](threat-explorer-views.md#email--user-reported) view of Explorer.</span></span>

1. <span data-ttu-id="851d9-149">Office 365[https://protection.office.com](https://protection.office.com)セキュリティ & コンプライアンスセンター () で、[**脅威管理** > **エクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="851d9-149">In the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="851d9-150">[**表示**] メニューで、[**電子メール** > **ユーザー-レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="851d9-150">In the **View** menu, choose **Email** > **User-reported**.</span></span><br/><span data-ttu-id="851d9-151">![エクスプローラーの [表示] メニュー](media/ExplorerViewMenuEmailUserReported.png)</span><span class="sxs-lookup"><span data-stu-id="851d9-151">![View menu for Explorer](media/ExplorerViewMenuEmailUserReported.png)</span></span><br/>
3. <span data-ttu-id="851d9-152">[**送信者**] をクリックし、[**基本** > **レポートの種類**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="851d9-152">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>
4. <span data-ttu-id="851d9-153">オプション (**フィッシング**など) を選択し、[**更新**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="851d9-153">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span> <br/><span data-ttu-id="851d9-154">![ユーザーによって報告されるフィッシング](media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="851d9-154">![User-reported phish](media/EmailUserReportedReportType.png)</span></span><br/> 

<span data-ttu-id="851d9-155">レポートが更新され、組織内のユーザーがフィッシングとして報告した電子メールメッセージに関するデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="851d9-155">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="851d9-156">この情報を使用して、さらに分析を行い、必要に応じて、 [ATP のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="851d9-156">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="theres-more"></a><span data-ttu-id="851d9-157">他にもまだあります！</span><span class="sxs-lookup"><span data-stu-id="851d9-157">There's more!</span></span>

<span data-ttu-id="851d9-158">この記事で説明されている3つのシナリオに加えて、多くのレポートシナリオをエクスプローラーで利用できます。</span><span class="sxs-lookup"><span data-stu-id="851d9-158">In addition to the three scenarios outlined in this article, you have many reporting scenarios available with Explorer.</span></span> <span data-ttu-id="851d9-159">その他の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="851d9-159">Here are a few more examples:</span></span>

- [<span data-ttu-id="851d9-160">配信された悪意のあるメールの検索と調査</span><span class="sxs-lookup"><span data-stu-id="851d9-160">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="851d9-161">SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="851d9-161">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

- [<span data-ttu-id="851d9-162">脅威エクスプローラーのビューの概要を取得する</span><span class="sxs-lookup"><span data-stu-id="851d9-162">Get an overview of the views in Threat Explorer</span></span>](threat-explorer-views.md)

## <a name="how-to-get-explorer"></a><span data-ttu-id="851d9-163">エクスプローラーを取得する方法</span><span class="sxs-lookup"><span data-stu-id="851d9-163">How to get Explorer</span></span>

<span data-ttu-id="851d9-164">Explorer は[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="851d9-164">Explorer is included in [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md).</span></span> 

<span data-ttu-id="851d9-165">エクスプローラーを表示して使用するには、セキュリティ管理者やセキュリティリーダーに付与されている権限など、適切なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="851d9-165">To view and use Explorer, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span> 

- <span data-ttu-id="851d9-166">セキュリティ&amp; /コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="851d9-166">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="851d9-167">組織の管理</span><span class="sxs-lookup"><span data-stu-id="851d9-167">Organization Management</span></span>
    - <span data-ttu-id="851d9-168">セキュリティ管理者 (Azure Active Directory 管理センター[https://aad.portal.azure.com](https://aad.portal.azure.com)で割り当て可能)</span><span class="sxs-lookup"><span data-stu-id="851d9-168">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="851d9-169">セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="851d9-169">Security Reader</span></span>

- <span data-ttu-id="851d9-170">exchange online の場合は、exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) または PowerShell コマンドレット (「 [exchange online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="851d9-170">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="851d9-171">組織の管理</span><span class="sxs-lookup"><span data-stu-id="851d9-171">Organization Management</span></span>
    - <span data-ttu-id="851d9-172">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="851d9-172">View-only Organization Management</span></span>
    - <span data-ttu-id="851d9-173">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="851d9-173">View-Only Recipients role</span></span>
    - <span data-ttu-id="851d9-174">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="851d9-174">Compliance Management</span></span>

<span data-ttu-id="851d9-175">詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="851d9-175">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="851d9-176">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="851d9-176">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="851d9-177">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="851d9-177">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
## <a name="related-topics"></a><span data-ttu-id="851d9-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="851d9-178">Related topics</span></span>

- [<span data-ttu-id="851d9-179">自動化された調査と応答 (AIR)</span><span class="sxs-lookup"><span data-stu-id="851d9-179">Automated Investigation and Response (AIR)</span></span>](automated-investigation-response-office.md)

- [<span data-ttu-id="851d9-180">脅威エクスプローラーのビュー</span><span class="sxs-lookup"><span data-stu-id="851d9-180">Threat Explorer views</span></span>](threat-explorer-views.md)

- [<span data-ttu-id="851d9-181">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="851d9-181">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
