---
title: Office 365 Cloud App Security の異常検出ポリシー
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 88935b4e-dcb1-47f1-8aca-1bf8fb069db6
description: '異常検出ポリシーを Office 365 のクラウド アプリケーションのセキュリティでは、潜在的な問題を明らかに、組み込みアルゴリズムを使用します。(作成) 時を調整するにはフィルターを使用して、1 つ以上の異常検出ポリシーが必要です。 '
ms.openlocfilehash: 8babe86dd5adb6c25a069096157cac121ad66ab1
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706341"
---
# <a name="anomaly-detection-policies-in-office-365-cloud-app-security"></a><span data-ttu-id="8fe1f-104">Office 365 Cloud App Security の異常検出ポリシー</span><span class="sxs-lookup"><span data-stu-id="8fe1f-104">Anomaly detection policies in Office 365 Cloud App Security</span></span>

<span data-ttu-id="8fe1f-105">セキュリティ管理の高度な office 365 は、Office 365 のクラウド アプリケーションのセキュリティをされます。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-105">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="8fe1f-106">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="8fe1f-106">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="8fe1f-107">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="8fe1f-107">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="8fe1f-108">配置 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="8fe1f-108">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="8fe1f-109">使用率。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-109">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="8fe1f-110">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-110">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="8fe1f-111">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-111">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="8fe1f-112">コースです!</span><span class="sxs-lookup"><span data-stu-id="8fe1f-112">You are here!</span></span>  <br/> [<span data-ttu-id="8fe1f-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="8fe1f-113">Next step</span></span>](integrate-your-siem-server-with-office-365-cas.md) <br/> |[<span data-ttu-id="8fe1f-114">使用します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-114">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="8fe1f-115">[マイクロソフト クラウド アプリケーションのセキュリティは、116 をリリース](https://docs.microsoft.com/cloud-app-security/release-notes)以降、Office 365 のクラウド アプリケーションのセキュリティには、いくつか定義済みの異常検出 (すぐ") を含むポリシー ユーザーとエンティティの動作分析 (UEBA) と機械学習 (ML) にはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-115">Beginning with [Microsoft Cloud App Security release 116](https://docs.microsoft.com/cloud-app-security/release-notes), Office 365 Cloud App Security includes several predefined anomaly detection policies ("out of the box") that include user and entity behavioral analytics (UEBA) and machine learning (ML).</span></span>
  
![異常検出ポリシーを表示するには、コントロールを選択\>のポリシーです。](media/9663baa5-98bf-45e0-9458-6e572b43ec72.png)
  
<span data-ttu-id="8fe1f-p102">これらの異常検出のポリシーは、ユーザーのコンピューターおよびネットワークに接続されたデバイス間でさまざまな動作異常を対象とする、迅速な検出を提供することですぐに結果を提供します。さらに、新しいポリシーは、継続的な脅威が含まれている調査のプロセスを高速化を支援するクラウド アプリケーションのセキュリティの検出エンジンからより多くのデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-p102">These anomaly detection policies provide immediate results by providing immediate detections, targeting numerous behavioral anomalies across your users and the machines and devices connected to your network. In addition, the new policies expose more data from the Cloud App Security detection engine to help you speed up the investigation process and contain ongoing threats.</span></span>
  
<span data-ttu-id="8fe1f-119">[グローバル アドミニストレーターまたはセキュリティ管理者](permissions-in-the-security-and-compliance-center.md)、確認、および必要に応じて、Office 365 のクラウド アプリケーションのセキュリティで使用可能な既定のポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-119">As a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), you can review, and if necessary, revise the default policies that are available with Office 365 Cloud App Security.</span></span>
  
 > [!IMPORTANT]
> <span data-ttu-id="8fe1f-p103">日数 7 (7) を異常な動作の警告は発生しません、初期の学習期間があります。異常検出アルゴリズムは、間違った警報の数を減らすために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-p103">There is an initial learning period of seven (7) days during which anomalous behavior alerts are not triggered. The anomaly detection algorithm is optimized to reduce the number of false positive alerts.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="8fe1f-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="8fe1f-122">Before you begin</span></span>

<span data-ttu-id="8fe1f-123">以下を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-123">Make sure that:</span></span>
  
- <span data-ttu-id="8fe1f-124">組織の[Office 365 のクラウド アプリケーションのセキュリティ](office-365-cas-overview.md)、およびサービスは、[有効に](turn-on-office-365-cas.md)します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-124">Your organization has [Office 365 Cloud App Security](office-365-cas-overview.md), and the service is [turned on](turn-on-office-365-cas.md).</span></span>
    
- <span data-ttu-id="8fe1f-125">[監査ログ](turn-audit-log-search-on-or-off.md)有効にする、Office 365 環境に。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-125">[Audit logging](turn-audit-log-search-on-or-off.md) is turned on for your Office 365 environment.</span></span> 
    
- <span data-ttu-id="8fe1f-126">グローバル アドミニストレーターまたはセキュリティ管理者は、Office 365 としています。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-126">You are a global administrator or security administrator for Office 365.</span></span>
    
## <a name="view-your-anomaly-detection-policies"></a><span data-ttu-id="8fe1f-127">異常検出ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-127">View your anomaly detection policies</span></span>

1. <span data-ttu-id="8fe1f-128">グローバル管理者またはセキュリティ管理者に移動します。[https://security.microsoft.com](https://security.microsoft.com)し、職場、学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-128">As a global administrator or security administrator, go to [https://security.microsoft.com](https://security.microsoft.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="8fe1f-129">セキュリティで&amp;コンプライアンス センターでは、**アラート**を選択して\>**管理警告の詳細**です。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-129">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="8fe1f-130">**Office 365 のクラウド アプリケーションのセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-130">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    <span data-ttu-id="8fe1f-131">Office 365 のクラウド アプリケーションのセキュリティ ポリシーのページに移動します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-131">This takes you to the Office 365 Cloud App Security Policies page.</span></span>
    
4. <span data-ttu-id="8fe1f-132">**種類**] ボックスの一覧では、**異常の検出ポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-132">In the **TYPE** list, choose **Anomaly detection policy**.</span></span>
    
    <span data-ttu-id="8fe1f-133">組織の既定値 (または既存の) 異常検出のポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-133">Your organization's default (or existing) anomaly detection policies are displayed.</span></span>
    
    ![異常検出のいくつかのポリシーは既定では Office 365 のクラウド アプリケーションのセキュリティで利用可能です](media/2e0ee770-787a-4d4a-bea8-389dc765d4c6.png)
  
5. <span data-ttu-id="8fe1f-135">確認または設定を編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-135">Select a policy to review or edit its settings.</span></span>
    
6. <span data-ttu-id="8fe1f-136">[ **Update**] を選んで、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-136">Choose **Update** to save your changes.</span></span> 
    
## <a name="learn-more-about-anomaly-detection-policies"></a><span data-ttu-id="8fe1f-137">異常検出のポリシーの詳細を表示します</span><span class="sxs-lookup"><span data-stu-id="8fe1f-137">Learn more about anomaly detection policies</span></span>

<span data-ttu-id="8fe1f-p104">異常検出のポリシーは自動的に有効にします。ただし、Office 365 のクラウド アプリケーションのセキュリティでは、検出のアラートが生成されるすべての異常の中に、7 日間の初期の学習期間があります。その後は、各セッションは、活動、ユーザーがアクティブだったときに、IP アドレス、デバイスなど、過去 1 か月とこれらのアクティビティのリスク ・ スコアを検出すると比較されます。これらの検出は、お客様の環境のプロファイルし、組織の活動で学習したことを基準計画を基準にアラートをトリガーするヒューリスティックの異常検出エンジンの一部です。これらの検出は、偽陽性を減らすためにユーザーとログインのパターンをプロファイルするように設計されたマシンの学習アルゴリズムを活用します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-p104">Anomaly detection policies are automatically enabled; however, Office 365 Cloud App Security has an initial learning period of seven days during which not all anomaly detection alerts are raised. After that, each session is compared to the activity, when users were active, IP addresses, devices, etc. detected over the past month and the risk score of these activities. These detections are part of the heuristic anomaly detection engine that profiles your environment and triggers alerts with respect to a baseline that was learned on your organization's activity. These detections also leverage machine learning algorithms designed to profile the users and log-in patterns to reduce false positives.</span></span>
  
<span data-ttu-id="8fe1f-p105">ユーザーの利用状況をスキャンすることで異常が検出されます。リスクは、危険な IP アドレス、ログインに失敗した、管理活動、非アクティブなアカウント、場所、不可能な旅行、デバイスとユーザー エージェントでは、アクティビティの速度など、複数のリスク要因に分け、30 以上のさまざまなリスク インジケーターを参照して評価されます。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-p105">Anomalies are detected by scanning user activity. The risk is evaluated by looking at over 30 different risk indicators, grouped into multiple risk factors, such as risky IP address, login failures, admin activity, inactive accounts, location, impossible travel, device and user agent, and activity rate.</span></span>
  
<span data-ttu-id="8fe1f-p106">ポリシーの結果に基づき、セキュリティの警告がトリガーされます。Office 365 のクラウド アプリケーションのセキュリティを使用して、Office 365 内のすべてのユーザー セッションを調べ、何かが発生した場合、組織のベースラインとは、ユーザーの通常の活動からさまざまなときに警告が表示します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-p106">Based on the policy results, security alerts are triggered. Office 365 Cloud App Security looks at every user session in Office 365, and alerts you whenever something happens that is different from the baseline of your organization or from a user's regular activity.</span></span>
  
<span data-ttu-id="8fe1f-146">次の表は、異常検出の既定のポリシー、, それらの動作し、その動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-146">The following table describes the default anomaly detection policies, what they do, and how they work.</span></span>
  
|<span data-ttu-id="8fe1f-147">**異常検出のポリシー名**</span><span class="sxs-lookup"><span data-stu-id="8fe1f-147">**Anomaly detection policy name**</span></span>|<span data-ttu-id="8fe1f-148">**動作のしくみ**</span><span class="sxs-lookup"><span data-stu-id="8fe1f-148">**How it works**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8fe1f-149">不可能な旅行</span><span class="sxs-lookup"><span data-stu-id="8fe1f-149">Impossible travel</span></span>  <br/> |<span data-ttu-id="8fe1f-p107">2 つのユーザー アクティビティを識別する (1 つまたは複数のセッションでは) 元の地理的に離れた場所からの時間よりも短い時間内になっていましたことを示す、2 番目の最初の位置から移動するのにはユーザー別ユーザーは、同じ資格情報を使用しています。この検出では、明らかな「偽陽性」Vpn および組織内の他のユーザーが定期的に使用される場所など、不可能な旅行条件の原因を無視するためのアルゴリズムを学習するコンピューターを活用します。検出には、初期の学習期間を 7 日に新しいユーザーの利用状況のパターンを学習します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-p107">Identifies two user activities (is a single or multiple sessions) originating from geographically distant locations within a time period shorter than the time it would have taken the user to travel from the first location to the second, indicating that a different user is using the same credentials. This detection leverages a machine learning algorithm that ignores obvious "false positives" contributing to the impossible travel condition, such as VPNs and locations regularly used by other users in the organization. The detection has an initial learning period of seven days during which it learns a new user's activity pattern.</span></span>  <br/> |
|<span data-ttu-id="8fe1f-153">頻度の低い国からの活動</span><span class="sxs-lookup"><span data-stu-id="8fe1f-153">Activity from infrequent country</span></span>  <br/> |<span data-ttu-id="8fe1f-p108">新しいと頻度の低い場所を決定するのには、過去の活動の場所と見なされます。異常検出エンジンは、組織内のユーザーによって使用される前の場所に関する情報を格納します。活動がないことはありませんか、最近訪れたユーザーまたは組織内のユーザーがいる場所から発生すると、警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-p108">Considers past activity locations to determine new and infrequent locations. The anomaly detection engine stores information about previous locations used by users in the organization. An alert is triggered when an activity occurs from a location that was not recently or never visited by the user or by any user in the organization.</span></span>  <br/> |
|<span data-ttu-id="8fe1f-157">匿名の IP アドレスからの活動</span><span class="sxs-lookup"><span data-stu-id="8fe1f-157">Activity from anonymous IP addresses</span></span>  <br/> |<span data-ttu-id="8fe1f-p109">匿名プロキシの IP アドレスとして識別されている、IP アドレスからアクティブなユーザーがいたことを識別します。人がそのデバイスの IP アドレスを非表示にして、悪意のある目的に使用できますが、これらのプロキシが使用されます。この検出は、「偽陽性」、組織内のユーザーによって広く使用されている IP アドレスが誤ってタグ付きなどを削減するアルゴリズムを学習するコンピューターを利用しています。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-p109">Identifies that users were active from an IP address that has been identified as an anonymous proxy IP address. These proxies are used by people who want to hide their device's IP address, and may be used for malicious intent. This detection leverages a machine learning algorithm that reduces "false positives", such as mis-tagged IP addresses that are widely used by users in the organization.</span></span>  <br/> |
|<span data-ttu-id="8fe1f-161">不審な IP アドレスからの活動</span><span class="sxs-lookup"><span data-stu-id="8fe1f-161">Activity from suspicious IP addresses</span></span>  <br/> |<span data-ttu-id="8fe1f-p110">Microsoft 脅威インテリジェンスで危険なものとして識別されている IP アドレスからアクティブなユーザーがいたことを識別します。これらの IP アドレスがボットネット C などの悪意のある活動に関与する&amp;C、侵害されたアカウントがある可能性があるとします。この検出は、「偽陽性」、組織内のユーザーによって広く使用されている IP アドレスが誤ってタグ付きなどを削減するアルゴリズムを学習するコンピューターを利用しています。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-p110">Identifies that users were active from an IP address that has been identified as risky by Microsoft Threat Intelligence. These IP addresses are involved in malicious activities, such as Botnet C&amp;C, and may indicate compromised account. This detection leverages a machine learning algorithm that reduces "false positives", such as mis-tagged IP addresses that are widely used by users in the organization.</span></span>  <br/> |
|<span data-ttu-id="8fe1f-165">(ユーザー) で異常な動作</span><span class="sxs-lookup"><span data-stu-id="8fe1f-165">Unusual activities (by user)</span></span>  <br/> | <span data-ttu-id="8fe1f-166">次のように、異常な動作を実行するユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-166">Identifies users who perform unusual activities, such as:</span></span>  <br/>  <span data-ttu-id="8fe1f-167">--複数のファイルのダウンロード</span><span class="sxs-lookup"><span data-stu-id="8fe1f-167">--Multiple file downloads</span></span>  <br/>  <span data-ttu-id="8fe1f-168">--ファイルのアクティビティを共有します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-168">--File sharing activities</span></span>  <br/>  <span data-ttu-id="8fe1f-169">--ファイル削除アクティビティ</span><span class="sxs-lookup"><span data-stu-id="8fe1f-169">--File deletion activities</span></span>  <br/>  <span data-ttu-id="8fe1f-170">-偽装活動</span><span class="sxs-lookup"><span data-stu-id="8fe1f-170">--Impersonation activities</span></span>  <br/>  <span data-ttu-id="8fe1f-171">--管理活動</span><span class="sxs-lookup"><span data-stu-id="8fe1f-171">--Administrative activities</span></span>  <br/>  <span data-ttu-id="8fe1f-p111">これらのポリシーを探します活動について学習するには、基準の 1 つのセッション内で違反の試みを示す。これらの検出では、パターンのプロファイル、ユーザーがログオンするためのアルゴリズムを学習するコンピューターを活用して、誤検出を減少します。これらの検出は、お客様の環境のプロファイルし、組織の活動で学習したことを基準計画を基準にアラートをトリガーするヒューリスティックの異常検出エンジンの一部です。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-p111">These policies look for activities within a single session with respect to the baseline learned, which could indicate on a breach attempt. These detections leverage a machine learning algorithm that profiles the users log on pattern and reduces false positives. These detections are part of the heuristic anomaly detection engine that profiles your environment and triggers alerts with respect to a baseline that was learned on your organization's activity.</span></span>  <br/> |
|<span data-ttu-id="8fe1f-175">複数ログイン試行の失敗</span><span class="sxs-lookup"><span data-stu-id="8fe1f-175">Multiple failed login attempts</span></span>  <br/> |<span data-ttu-id="8fe1f-176">1 つのセッションで複数のログイン試行が失敗したユーザーを識別する、学習した基準計画に関連する可能性があります違反の試行で。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-176">Identifies users that failed multiple login attempts in a single session with respect to the baseline learned, which could indicate on a breach attempt.</span></span>  <br/> |
   
## <a name="triage-anomaly-detection-alerts"></a><span data-ttu-id="8fe1f-177">トリアージの異常検出の警告</span><span class="sxs-lookup"><span data-stu-id="8fe1f-177">Triage anomaly detection alerts</span></span>
<span data-ttu-id="8fe1f-178"><a name="triage"> </a></span><span class="sxs-lookup"><span data-stu-id="8fe1f-178"></span></span>

<span data-ttu-id="8fe1f-p112">アラートが発生、それらのアラートをすばやく優先順位を決定し、どれを最初に処理を決定できます。アラートのコンテキストを使用すると、拡大画像の表示し、実際に発生している悪意のあるものかどうかを決定します。アラートの調査を開始するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-p112">As alerts come in, you can triage those alerts quickly and determine which ones to handle first. Having context for an alert enables you to see the bigger picture and determine whether something malicious is indeed happening. Use the following procedure to get started exploring an alert:</span></span>
  
1. <span data-ttu-id="8fe1f-182">グローバル管理者またはセキュリティ管理者に移動します。[https://security.microsoft.com](https://security.microsoft.com)し、職場、学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-182">As a global administrator or security administrator, go to [https://security.microsoft.com](https://security.microsoft.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="8fe1f-183">セキュリティで&amp;コンプライアンス センターでは、**アラート**を選択して\>**管理警告の詳細**です。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-183">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="8fe1f-184">**Office 365 のクラウド アプリケーションのセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-184">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
4. <span data-ttu-id="8fe1f-185">アラートを表示する**アラート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-185">Choose **Alerts** to view your alerts.</span></span> 
    
5. <span data-ttu-id="8fe1f-186">アラートのコンテキストを取得するのには以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-186">To get context for an alert, follow these steps:</span></span>
    
1. <span data-ttu-id="8fe1f-187">**調査**を選択して\>**のアクティビティのログ**です。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-187">Choose **Investigate** \> **Activity log**.</span></span>
    
2. <span data-ttu-id="8fe1f-p113">ユーザーまたは IP アドレスなどの項目を選択します。関連情報の引き出しが開きます。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-p113">Select an item, such as a user or IP address. This opens the relevant insights drawer.</span></span>
    
    ![アクティビティ ・ ログでは、IP アドレスを調べることができます。](media/32a727c5-e406-4fe2-9443-c1a7fb6628fc.png)
  
3. <span data-ttu-id="8fe1f-191">プラットフォームとして活用する給紙トレイのアイコン**を表示するのと同様**に記載など、利用可能なコマンドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-191">In the relevant insights drawer, click an available command, such as an icon in the **SHOW SIMILAR** section.</span></span> 
    
    ![プラットフォームとして活用する給紙トレイで選択したアクティビティの 48 時間以内に実行されるアクティビティを表示する時計のアイコンを選択できます。](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
4. <span data-ttu-id="8fe1f-193">その項目の詳細を表示し続けることにより、選択した項目について把握できます。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-193">Gain insight about the selected item by continuing to explore details for that item.</span></span>
    
<span data-ttu-id="8fe1f-p114">複数のログインの失敗に関するアラートは、不審な本当の意味で可能性があり、ブルート フォース攻撃の可能性を示すことができます。ただし、このような警告には、アプリケーションの構成の誤り、害のない正の場合は true を指定するアラート発生ことができます。他の不審な動作を持つ複数失敗したログインのアラートが表示された場合は、アカウントが侵害されている可能性が高くします。たとえば、ある複数失敗したログインのアラートが続く活動で、TOR の IP アドレスと不可能な旅行アクティビティでは、両方の強力なインジケーターが侵害されるとします。同じユーザーが攻撃者のデータの exfiltration を実行することを示すインジケーターは、多くの場合、大容量のダウンロードのアクティビティを実行する可能性がありますも参照してください。表示し、アラートの優先順位を決定して処理する Office 365 のクラウド アプリケーションのセキュリティを表示することがあるような作業の必要な場所です。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-p114">An alert on multiple failed logins might indeed be suspicious, and can indicate a potential brute-force attack. However, such an alert can also be an application misconfiguration, causing the alert to be a benign true positive. If you see a multiple-failed-logins alert with additional suspicious activities, then there is a higher probability that an account is compromised. For example, suppose that a multiple-failed-login alert is followed by activity from a TOR IP address and impossible travel activity, both strong indicators of compromise. You might even see that the same user performed a mass download activity, which is often an indicator of the attacker performing exfiltration of data. It's things like that that you can explore in Office 365 Cloud App Security to view and triage your alerts, and take action where needed.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="8fe1f-200">次の手順</span><span class="sxs-lookup"><span data-stu-id="8fe1f-200">Next steps</span></span>

- [<span data-ttu-id="8fe1f-201">SIEM サーバーを統合します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-201">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="8fe1f-202">確認し、アラート アクションを実行</span><span class="sxs-lookup"><span data-stu-id="8fe1f-202">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="8fe1f-203">管理を簡略化する IP アドレスをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="8fe1f-203">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

