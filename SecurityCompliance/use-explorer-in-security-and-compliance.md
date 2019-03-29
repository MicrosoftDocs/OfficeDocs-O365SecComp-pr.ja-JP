---
title: セキュリティ&amp; /コンプライアンスセンターで脅威エクスプローラーを使用する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/28/2019
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
ms.openlocfilehash: e6177970edc67c8b9e1c0ae6144f4c37f116012f
ms.sourcegitcommit: 787a0fef671e5dc6f5e805b580321b2edbfad8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30989612"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="f1ee6-103">セキュリティ&amp; /コンプライアンスセンターで脅威エクスプローラーを使用する</span><span class="sxs-lookup"><span data-stu-id="f1ee6-103">Use Threat Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="f1ee6-104">組織に[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md) (ATP) があり、必要なアクセス許可がある場合は、脅威エクスプローラー (エクスプローラーとも呼ばれます) を使用して脅威を識別して分析できます。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-104">If your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md) (ATP), and you have the necessary permissions, you can use Threat Explorer (also referred to as Explorer) to identify and analyze threats.</span></span> <span data-ttu-id="f1ee6-105">(エクスプローラーを使用するには、 &amp;セキュリティ/コンプライアンスセンターで、[**脅威管理** \> **エクスプローラー**] に移動します)。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-105">(To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.)</span></span>

![[脅威管理\>エクスプローラー] に移動します。](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="f1ee6-107">エクスプローラーは、セキュリティ運用チームがセキュリティ&amp;コンプライアンスセンターで脅威を調査して対応するのに役立つ、強力でほぼリアルタイムのツールです。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-107">Explorer is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="f1ee6-108">実行できる操作の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-108">Here are some of the things you can do:</span></span>
- [<span data-ttu-id="f1ee6-109">Office 365 のセキュリティ機能によって検出されたマルウェアを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-109">See malware that was detected by Office 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- <span data-ttu-id="f1ee6-110">[フィッシング url に関するデータを表示し、[verdict] をクリックします。](#view-data-about-phishing-urls-and-click-verdict)</span><span class="sxs-lookup"><span data-stu-id="f1ee6-110">[View data about phishing URLs and click verdict](#view-data-about-phishing-urls-and-click-verdict)</span></span>
- [<span data-ttu-id="f1ee6-111">エクスプローラーのビューから自動化された調査と応答プロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="f1ee6-111">Start an automated investigation and response process from a view in Explorer</span></span>](#start-automated-investigation-and-response)
- <span data-ttu-id="f1ee6-112">...その[他](#more-ways-to-use-explorer)</span><span class="sxs-lookup"><span data-stu-id="f1ee6-112">... [and more](#more-ways-to-use-explorer)!</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="f1ee6-113">テクノロジによる電子メールで検出されたマルウェアを参照</span><span class="sxs-lookup"><span data-stu-id="f1ee6-113">See malware detected in email by technology</span></span>

<span data-ttu-id="f1ee6-114">電子メールで検出されたマルウェアと Office 365 のテクノロジについて確認する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-114">Suppose you want to see malware that was detected in email, and by what technology in Office 365.</span></span> <span data-ttu-id="f1ee6-115">これを行うには、エクスプローラーの [ [Email > マルウェア](threat-explorer-views.md#email--malware)] ビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-115">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer.</span></span>

1. <span data-ttu-id="f1ee6-116">セキュリティ &[https://protection.office.com](https://protection.office.com)コンプライアンスセンター () で、[**脅威管理** > **エクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-116">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="f1ee6-117">[**表示**] メニューで、[**電子メール** > **マルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-117">In the **View** menu, choose **Email** > **Malware**.</span></span><br/><span data-ttu-id="f1ee6-118">![エクスプローラーの [表示] メニュー](media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="f1ee6-118">![View menu for Explorer](media/ExplorerViewEmailMalwareMenu.png)</span></span><br/>
3. <span data-ttu-id="f1ee6-119">[**送信者**] をクリックし、[**基本** > **検出テクノロジ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-119">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span><br/><span data-ttu-id="f1ee6-120">これで、検出テクノロジがレポートのフィルターとして使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-120">Your detection technologies are now available as filters for the report.</span></span><br/><span data-ttu-id="f1ee6-121">![マルウェア検出テクノロジ](media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="f1ee6-121">![Malware detection technologies](media/ExplorerEmailMalwareDetectionTech.png)</span></span><br/> 
4. <span data-ttu-id="f1ee6-122">オプションを選択し、[更新] ボタンをクリックしてそのフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-122">Select an option, and then click the Refresh button to apply that filter.</span></span><br/>![選択されている検出テクノロジ](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

<span data-ttu-id="f1ee6-124">レポートが更新され、選択した [テクノロジ] オプションを使用して、電子メールで検出された結果のマルウェアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-124">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="f1ee6-125">ここから、さらに分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-125">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="f1ee6-126">フィッシング url に関するデータを表示し、[verdict] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-126">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="f1ee6-127">許可された url の一覧を含む電子メール内の url を使用して、許可され、ブロックされ、上書きされたフィッシングを表示する場合を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-127">Suppose you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="f1ee6-128">これを行うには、エクスプローラーの [ [Email > フィッシング](threat-explorer-views.md#email--phish)] ビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-128">To do this, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer.</span></span>

1. <span data-ttu-id="f1ee6-129">セキュリティ &[https://protection.office.com](https://protection.office.com)コンプライアンスセンター () で、[**脅威管理** > **エクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-129">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="f1ee6-130">[**表示**] メニューの [**電子メール** > **フィッシング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-130">In the **View** menu, choose **Email** > **Phish**.</span></span><br/><span data-ttu-id="f1ee6-131">![エクスプローラーの [表示] メニュー](media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="f1ee6-131">![View menu for Explorer](media/ExplorerViewEmailPhishMenu.png)</span></span><br/>
3. <span data-ttu-id="f1ee6-132">[**送信者**] をクリックし、[ **url** > ] を選択して、**[verdict] をクリック**します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-132">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>
4. <span data-ttu-id="f1ee6-133">1つ以上のオプション ([**ブロック**されてブロックされた**ブロック**] など) を選択し、[**更新**] ボタンをクリックしてそのフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-133">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button to apply that filter.</span></span><br/><span data-ttu-id="f1ee6-134">![url および [verdicts] をクリックします。](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="f1ee6-134">![URLs and click verdicts](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span><br/>

<span data-ttu-id="f1ee6-135">レポートが更新され、電子メールの配信状態と共に、検出された (または警告に関係していても表示されている) 電子メールで検出されたフィッシング url が表示されます</span><span class="sxs-lookup"><span data-stu-id="f1ee6-135">The report refreshes to show detected phishing URLs in email that were blocked (or visited despite a warning), along with email delivery status.</span></span> <span data-ttu-id="f1ee6-136">ここから、さらに分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-136">From here, you can conduct further analysis.</span></span> <span data-ttu-id="f1ee6-137">たとえば、グラフの下に、組織の電子メールでブロックされた上位の url が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-137">For example, below the chart, you can see the top URLs that were blocked in your organization's email.</span></span> 

![ブロックされたエクスプローラーの url](media/ExplorerPhishClickVerdictURLs.png) 

<span data-ttu-id="f1ee6-139">URL を選択して、詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-139">Select a URL to view more detailed information.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="f1ee6-140">ユーザーが報告した電子メールメッセージを確認する</span><span class="sxs-lookup"><span data-stu-id="f1ee6-140">Review email messages reported by users</span></span>

<span data-ttu-id="f1ee6-141">組織内のユーザーが、 [outlook 用のレポートメッセージアドインと web 上の outlook](enable-the-report-message-add-in.md)を使用して、迷惑メールではなく迷惑メールとして報告した電子メールメッセージを表示したいとします。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-141">Suppose you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="f1ee6-142">これを行うには、> のエクスプローラーの[ユーザーレポート](threat-explorer-views.md#email--user-reported)ビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-142">To do this, use the [Email > User-reported](threat-explorer-views.md#email--user-reported) view of Explorer.</span></span>

1. <span data-ttu-id="f1ee6-143">セキュリティ &[https://protection.office.com](https://protection.office.com)コンプライアンスセンター () で、[**脅威管理** > **エクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-143">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="f1ee6-144">[**表示**] メニューで、[**電子メール** > **ユーザー-レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-144">In the **View** menu, choose **Email** > **User-reported**.</span></span><br/><span data-ttu-id="f1ee6-145">![エクスプローラーの [表示] メニュー](media/ExplorerViewMenuEmailUserReported.png)</span><span class="sxs-lookup"><span data-stu-id="f1ee6-145">![View menu for Explorer](media/ExplorerViewMenuEmailUserReported.png)</span></span><br/>
3. <span data-ttu-id="f1ee6-146">[**送信者**] をクリックし、[**基本** > **レポートの種類**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-146">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>
4. <span data-ttu-id="f1ee6-147">オプション (**フィッシング**など) を選択し、[**更新**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-147">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span> <br/><span data-ttu-id="f1ee6-148">![ユーザーによって報告されるフィッシング](media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="f1ee6-148">![User-reported phish](media/EmailUserReportedReportType.png)</span></span><br/> 

<span data-ttu-id="f1ee6-149">レポートが更新され、組織内のユーザーがフィッシングとして報告した電子メールメッセージに関するデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-149">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="f1ee6-150">この情報を使用して、さらに分析を行い、必要に応じて、 [ATP のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-150">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="f1ee6-151">自動調査と応答の開始</span><span class="sxs-lookup"><span data-stu-id="f1ee6-151">Start automated investigation and response</span></span>

<span data-ttu-id="f1ee6-152">(新)ATP プラン2に追加された[自動調査と応答](automated-investigation-response-office.md)を使用すると、セキュリティ運用チームに多くの時間と労力をかけることができます。これにより、サイバー攻撃の調査と軽減が可能になります。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-152">(NEW!) [Automated investigation and response](automated-investigation-response-office.md), recently added to ATP Plan 2, can save your security operations team a lot of time and effort in investigating and mitigating cyber attacks.</span></span> <span data-ttu-id="f1ee6-153">セキュリティプレイブックをトリガーできる通知を構成するだけでなく、エクスプローラーのビューから自動化された調査および応答プロセスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-153">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> 

<span data-ttu-id="f1ee6-154">詳細については、「[例: セキュリティ管理者が脅威エクスプローラーから調査を開始する](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-154">For details on this, see [Example: A security administrator triggers an investigation from Threat Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer"></a><span data-ttu-id="f1ee6-155">エクスプローラーのその他の使用方法</span><span class="sxs-lookup"><span data-stu-id="f1ee6-155">More ways to use Explorer</span></span>

<span data-ttu-id="f1ee6-156">この記事で説明されているシナリオに加えて、エクスプローラーで利用できるレポートオプションが他にも多数あります。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-156">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer.</span></span> 
- [<span data-ttu-id="f1ee6-157">配信された悪意のあるメールの検索と調査</span><span class="sxs-lookup"><span data-stu-id="f1ee6-157">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="f1ee6-158">SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="f1ee6-158">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="f1ee6-159">脅威エクスプローラーのビューの概要を取得する</span><span class="sxs-lookup"><span data-stu-id="f1ee6-159">Get an overview of the views in Threat Explorer</span></span>](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="f1ee6-160">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f1ee6-160">Required licenses and permissions</span></span>

<span data-ttu-id="f1ee6-161">Explorer は[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-161">Explorer is included in [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md).</span></span> 

<span data-ttu-id="f1ee6-162">エクスプローラーを表示して使用するには、セキュリティ管理者やセキュリティリーダーに付与されている権限など、適切なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-162">To view and use Explorer, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span> 

- <span data-ttu-id="f1ee6-163">セキュリティ&amp; /コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-163">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="f1ee6-164">組織の管理</span><span class="sxs-lookup"><span data-stu-id="f1ee6-164">Organization Management</span></span>
    - <span data-ttu-id="f1ee6-165">セキュリティ管理者 (Azure Active Directory 管理センター[https://aad.portal.azure.com](https://aad.portal.azure.com)で割り当て可能)</span><span class="sxs-lookup"><span data-stu-id="f1ee6-165">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="f1ee6-166">セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="f1ee6-166">Security Reader</span></span>

- <span data-ttu-id="f1ee6-167">exchange online の場合は、exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) または PowerShell コマンドレット (「 [exchange online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-167">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="f1ee6-168">組織の管理</span><span class="sxs-lookup"><span data-stu-id="f1ee6-168">Organization Management</span></span>
    - <span data-ttu-id="f1ee6-169">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="f1ee6-169">View-only Organization Management</span></span>
    - <span data-ttu-id="f1ee6-170">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="f1ee6-170">View-Only Recipients role</span></span>
    - <span data-ttu-id="f1ee6-171">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="f1ee6-171">Compliance Management</span></span>

<span data-ttu-id="f1ee6-172">役割とアクセス許可の詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1ee6-172">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="f1ee6-173">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f1ee6-173">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="f1ee6-174">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f1ee6-174">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
