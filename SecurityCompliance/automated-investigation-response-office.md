---
title: Office 365 を使用した自動調査と応答 (AIR)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection の自動化された調査と応答機能について説明します。
ms.openlocfilehash: bb992a4ebd9bf10f2659929bab4357117ea1c254
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852621"
---
# <a name="automated-investigation-and-response-air-with-office-365"></a><span data-ttu-id="2aac0-103">Office 365 を使用した自動調査と応答 (AIR)</span><span class="sxs-lookup"><span data-stu-id="2aac0-103">Automated Investigation and Response (AIR) with Office 365</span></span>

<span data-ttu-id="2aac0-104">自動化された調査と応答 (AIR) (現在は、多くの[Office 365 脅威の調査および応答機能](office-365-ti.md)の1つとしてのパブリックプレビューで) を実行することで、現在存在している既知の脅威に対する自動化された調査と修復を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-104">Automated Investigation and Response (AIR) (currently in public preview as one of many [Office 365 Threat investigation and response capabilities](office-365-ti.md)) enables you to run automated investigation and remediation to well-known threats that exist today.</span></span> <span data-ttu-id="2aac0-105">この記事では、AIR の概要と、組織およびセキュリティ運用チームがより効果的かつ効率的に脅威を軽減する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-105">Read this article to get an overview of AIR and how it can help your organization and security operations teams mitigate threats more effectively and efficiently.</span></span> 

<span data-ttu-id="2aac0-106">空気の機能がいつ利用可能になるかの詳細については、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2aac0-106">To learn more about when  AIR features will be available, see the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="alerts"></a><span data-ttu-id="2aac0-107">アラート</span><span class="sxs-lookup"><span data-stu-id="2aac0-107">Alerts</span></span>

<span data-ttu-id="2aac0-108">[警告](alert-policies.md#viewing-alerts)は、インシデント対応のセキュリティ運用チームワークフローのトリガーを表します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-108">[Alerts](alert-policies.md#viewing-alerts) represent triggers for security operations team workflows for incident response.</span></span> <span data-ttu-id="2aac0-109">調査のための適切なアラートセットの優先順位付けを行い、対処されていない脅威がないことを確認するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="2aac0-109">Prioritizing the right set of alerts for investigation, while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="2aac0-110">アラートへの調査が手動で実行される場合、セキュリティ運用チームは脅威からのリスクでエンティティ (コンテンツ、デバイス、ユーザーなど) をハントして関連付けなければなりません。</span><span class="sxs-lookup"><span data-stu-id="2aac0-110">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (e.g. content, devices and users) at risk from threats.</span></span> <span data-ttu-id="2aac0-111">このようなタスクやワークフローは、非常に時間がかかり、複数のツールやシステムが関係しています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-111">Such tasks and workflows are very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="2aac0-112">エアの場合、調査と応答は、セキュリティ対応のプレイブックを自動的にトリガーする主要なセキュリティおよび脅威管理警告に自動化されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-112">With AIR, investigation and response are automated into key security and threat management alerts that trigger your security response playbooks automatically.</span></span> 

<span data-ttu-id="2aac0-113">2019年4月の最初のリリースでは、次の1つのイベントの警告ポリシーから生成されたアラートが自動的に調査されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-113">In the initial release of AIR in April 2019, alerts generated from following single events alert policies will be auto-investigated.</span></span> 

1. <span data-ttu-id="2aac0-114">潜在的に悪意のある URL のクリックが検出された</span><span class="sxs-lookup"><span data-stu-id="2aac0-114">A potentially malicious URL click was detected</span></span>
2. <span data-ttu-id="2aac0-115">ユーザーがフィッシングとして報告した電子メール \*</span><span class="sxs-lookup"><span data-stu-id="2aac0-115">Email reported by user as phish\*</span></span>
3. <span data-ttu-id="2aac0-116">配信後に削除されたマルウェアを含む電子メールメッセージ \*</span><span class="sxs-lookup"><span data-stu-id="2aac0-116">Email messages containing malware removed after delivery\*</span></span>
4. <span data-ttu-id="2aac0-117">配信後に削除されたフィッシング Url を含む電子メールメッセージ \*</span><span class="sxs-lookup"><span data-stu-id="2aac0-117">Email messages containing phish URLs removed after delivery\*</span></span>

<span data-ttu-id="2aac0-118">\***注**: これらのアラートには、電子メール通知がオフになっているセキュリティ & コンプライアンスセンター内のそれぞれのアラートポリシーに "情報" という重要度が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-118">\***Note**: These alerts have been assigned an "Informational" severity in the respective alert policies within the Security & Compliance Center with email notifications turned off.</span></span> <span data-ttu-id="2aac0-119">これらは、通知ポリシー構成を使用して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-119">These can be turned on through the Alert policy configuration.</span></span>

<span data-ttu-id="2aac0-120">通知を表示するには、セキュリティ & コンプライアンスセンターで\*\*\*\* > 、[警告の**表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-120">To view alerts, in the Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="2aac0-121">通知を選択して詳細を表示します。そこから、[**調査の表示**] リンクを使用して、対応する[調査](#investigation-graph)に移動します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-121">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](#investigation-graph).</span></span> <span data-ttu-id="2aac0-122">情報通知は、既定では通知ビューに表示されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2aac0-122">Note that informational alerts are hidden in the alert view by default.</span></span> <span data-ttu-id="2aac0-123">それらを表示するには、通知フィルターを変更して情報通知を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2aac0-123">To see them, you need to change the alert filtering to include informational alerts.</span></span>

<span data-ttu-id="2aac0-124">組織がアラート管理システム、サービス管理システム、またはセキュリティ情報およびイベント管理 (SIEM) システムを通じてセキュリティ警告を管理する場合は、電子メール通知またはを介し[てそのシステムに Office 365 通知を送信できます。Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="2aac0-124">If your organization manages your security alerts through a alert management system, service management system, or Security Information and Event Management (SIEM) system, you can send Office 365 alerts to that system via either email notification or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> <span data-ttu-id="2aac0-125">電子メールまたは API を使用した調査アラート通知には、セキュリティ & コンプライアンスセンターのアラートにアクセスするためのリンクが含まれています。これにより、割り当てられたセキュリティ管理者は、調査にすばやく移動できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2aac0-125">The investigation alert notifications via email or API will include links to access the alerts in the Security & Compliance Center, enabling the assigned security administrator to navigate quickly to the investigation.</span></span>

![調査にリンクされたアラート](media/air-alerts-page-details.png) 


## <a name="security-playbooks"></a><span data-ttu-id="2aac0-127">セキュリティプレイブック</span><span class="sxs-lookup"><span data-stu-id="2aac0-127">Security playbooks</span></span>

<span data-ttu-id="2aac0-128">セキュリティプレイブックは、Microsoft の脅威保護の中核となるバックエンドポリシーです。</span><span class="sxs-lookup"><span data-stu-id="2aac0-128">Security playbooks are back-end policies that are at the heart of automation in Microsoft Threat Protection.</span></span> <span data-ttu-id="2aac0-129">AIR で提供されるセキュリティプレイブックは、一般的な実際のセキュリティシナリオに基づいています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-129">The security playbooks provided in AIR are based on common real-world security scenarios.</span></span> <span data-ttu-id="2aac0-130">組織内でアラートがトリガーされると、セキュリティによるプレイブックが自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-130">A security playbook is launched automatically when an alert is triggered within your organization.</span></span> <span data-ttu-id="2aac0-131">アラートがトリガーされると、関連付けられたプレイブックが自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-131">Once the alert triggers, the associated playbook is run automatically.</span></span> <span data-ttu-id="2aac0-132">プレイブックは、すべての関連するメタデータ (電子メールメッセージ、ユーザー、件名、送信者などを含む) を調べて調査を実行します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-132">The playbook runs an investigation, looking at all the associated metadata (including email messages, users, subjects, senders, etc.).</span></span> <span data-ttu-id="2aac0-133">このプレイブックの調査結果に基づいて、組織のセキュリティチームが脅威を制御し、軽減するために実行できる一連のアクションを指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2aac0-133">Based on the playbook's findings, AIR recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="2aac0-134">空中で利用できるセキュリティプレイブックは、組織が現在直面している最も頻繁な脅威に取り組むように設計されています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-134">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations face today.</span></span> <span data-ttu-id="2aac0-135">これらは、Microsoft とお客様の資産を保護する手助けをしているユーザーを含む、セキュリティ運用チームとインシデント対応チームからの入力に基づいています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-135">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft and our customers assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="2aac0-136">セキュリティプレイブックは段階的に展開されています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-136">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="2aac0-137">航空の一環として、セキュリティプレイブックはフェーズに展開されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-137">As part of AIR, security playbooks are rolling out in phases</span></span>

- <span data-ttu-id="2aac0-138">**フェーズ 1 (2019 年4月)**: プレイブックには、セキュリティ管理者が確認および承認するアクションに関する推奨事項が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-138">**Phase 1 (April 2019)**: Playbooks include recommendations for actions that security administrators review and approve.</span></span> 

- <span data-ttu-id="2aac0-139">**フェーズ 2 (2019 年6月5日)**: プレイブックの改良点とセキュリティ管理者は、管理上の操作なしで何らかの操作を自動的に実行するようにセキュリティプレイブックを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-139">**Phase 2 (post-June 2019)**: Playbook improvements, plus security administrators will have the option to configure security playbooks to take some actions automatically without administrative interaction.</span></span>

<span data-ttu-id="2aac0-140">フェーズ1には、次のプレイブックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-140">Phase 1 will include the following playbooks:</span></span>
- <span data-ttu-id="2aac0-141">ユーザーによって報告されるフィッシングメッセージ</span><span class="sxs-lookup"><span data-stu-id="2aac0-141">User-reported phish message</span></span>
- <span data-ttu-id="2aac0-142">URL [verdict change] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2aac0-142">URL click verdict change</span></span> 
- <span data-ttu-id="2aac0-143">配信後のマルウェア検出 (マルウェア ZAP)</span><span class="sxs-lookup"><span data-stu-id="2aac0-143">Malware detected post-delivery (Malware ZAP)</span></span>
- <span data-ttu-id="2aac0-144">フィッシングは、配信後の ZAP (フィッシング ZAP) を検出しました</span><span class="sxs-lookup"><span data-stu-id="2aac0-144">Phish detected post-delivery ZAP (Phish ZAP)</span></span>
- <span data-ttu-id="2aac0-145">手動による電子メール調査 (脅威エクスプローラーを使用)</span><span class="sxs-lookup"><span data-stu-id="2aac0-145">Manual e-mail investigations (using Threat Explorer)</span></span>

<span data-ttu-id="2aac0-146">フェーズ2では、他のいくつかのプレイブックが計画されています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-146">Several other playbooks are planned for Phase 2.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="2aac0-147">プレイブックには、調査と推奨事項が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-147">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="2aac0-148">各プレイブックには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-148">Each playbook includes:</span></span> 
- <span data-ttu-id="2aac0-149">ルート調査、</span><span class="sxs-lookup"><span data-stu-id="2aac0-149">a root investigation,</span></span> 
- <span data-ttu-id="2aac0-150">他の潜在的な脅威を識別して相互に関連付けるために実行する手順</span><span class="sxs-lookup"><span data-stu-id="2aac0-150">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="2aac0-151">推奨される脅威修復アクション。</span><span class="sxs-lookup"><span data-stu-id="2aac0-151">recommended threat remediation actions.</span></span>

<span data-ttu-id="2aac0-152">各高度な手順には、脅威への深く、詳細、および完全な応答を提供するために実行される多くのサブステップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-152">Each high-level step includes many sub-steps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="2aac0-153">例: ユーザーによって報告されるフィッシングメッセージは、調査のプレイブックを起動します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-153">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="2aac0-154">組織内のユーザーが電子メールメッセージを送信して、 [outlook または Outlook Web Access 用のレポートメッセージアドイン](enable-the-report-message-add-in.md)を使用して Microsoft に報告すると、レポートはシステムにも送信され、ユーザーがレポートしたビューで Explorer に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-154">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web Access](enable-the-report-message-add-in.md), the report is also sent to your system and is visible in Explorer in the User-reported view.</span></span> <span data-ttu-id="2aac0-155">このユーザーによって報告されたメッセージは、システムベースの情報通知をトリガーします。これにより、調査のプレイブックが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-155">This user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="2aac0-156">ルート調査フェーズでは、電子メールのさまざまな側面を評価します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-156">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="2aac0-157">これらには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-157">These include:</span></span>
- <span data-ttu-id="2aac0-158">脅威の種類を決定すること。</span><span class="sxs-lookup"><span data-stu-id="2aac0-158">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="2aac0-159">送信者。</span><span class="sxs-lookup"><span data-stu-id="2aac0-159">Who sent it;</span></span>
- <span data-ttu-id="2aac0-160">電子メールの送信元 (インフラストラクチャの送信)</span><span class="sxs-lookup"><span data-stu-id="2aac0-160">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="2aac0-161">電子メールの他のインスタンスが配信またはブロックされたかどうか。</span><span class="sxs-lookup"><span data-stu-id="2aac0-161">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="2aac0-162">アナリストからの評価。</span><span class="sxs-lookup"><span data-stu-id="2aac0-162">An assessment from our analysts;</span></span>
- <span data-ttu-id="2aac0-163">電子メールが既知のキャンペーンと関連付けられているかどうか。</span><span class="sxs-lookup"><span data-stu-id="2aac0-163">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="2aac0-164">その他。</span><span class="sxs-lookup"><span data-stu-id="2aac0-164">and more.</span></span>

<span data-ttu-id="2aac0-165">ルート調査の完了後、元の電子メールと関連付けられているエンティティに対して実行する推奨アクションの一覧が、プレイブックに示されています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-165">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="2aac0-166">次に、いくつかの脅威の調査と探しの手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-166">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="2aac0-167">他の電子メールクラスター内の類似した電子メールメッセージが検索されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-167">Similar email messages in other email clusters are searched.</span></span>
- <span data-ttu-id="2aac0-168">シグナルは、 [Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)などの他のプラットフォームと共有されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-168">The signal is shared with other platforms, such as [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="2aac0-169">疑わしい電子メールメッセージ内の悪意のあるリンクをすべてのユーザーがクリックしたかどうかについての判断が行われます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-169">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="2aac0-170">チェックは、Office 365 Exchange Online Protection ([EOP](eop/exchange-online-protection-eop.md)) および Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) の間で行われ、ユーザーによって報告された他の類似メッセージがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-170">A check is done across Office 365 Exchange Online Protection ([EOP](eop/exchange-online-protection-eop.md)) and Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="2aac0-171">ユーザーが侵害されていないかどうかを確認するためのチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-171">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="2aac0-172">このチェックでは、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)と[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)の間の信号を活用し、関連するユーザーアクティビティの異常を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-172">This check leverages signals across [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span> 

<span data-ttu-id="2aac0-173">お探しの段階では、さまざまなお探しのステップにリスクと脅威が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-173">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="2aac0-174">修復は、プレイブックの最終段階です。</span><span class="sxs-lookup"><span data-stu-id="2aac0-174">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="2aac0-175">このフェーズでは、調査とお探しのフェーズに基づいて、修復手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-175">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="2aac0-176">例: セキュリティ管理者が脅威エクスプローラーから調査を開始する</span><span class="sxs-lookup"><span data-stu-id="2aac0-176">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="2aac0-177">通知によってトリガーされる自動調査に加えて、組織のセキュリティ運用チームは[脅威エクスプローラー](use-explorer-in-security-and-compliance.md)のビューから自動調査を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-177">In addition to automatic investigations that are triggered by an alert, your organization's security operations team can trigger an automatic investigation from a view in [Threat Explorer](use-explorer-in-security-and-compliance.md).</span></span>

<span data-ttu-id="2aac0-178">たとえば、ユーザーから報告されたメッセージについてのデータをエクスプローラーで表示しているとします。</span><span class="sxs-lookup"><span data-stu-id="2aac0-178">For example, suppose that you are viewing data in Explorer about user-reported messages.</span></span> <span data-ttu-id="2aac0-179">結果の一覧から項目を選択してから、[**調査**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2aac0-179">You can select an item in the list of results, and then click **Investigate**.</span></span>

![エクスプローラーで [調査] ボタンが表示されたユーザーレポートメッセージ](media/Explorer-UserReported-Investigate.png)

<span data-ttu-id="2aac0-181">もう1つの例として、マルウェアが含まれていると検出された電子メールメッセージに関するデータを表示していて、マルウェアを含む複数の電子メールメッセージが検出されたとします</span><span class="sxs-lookup"><span data-stu-id="2aac0-181">As another example, suppose you are viewing data about email messages detected as containing malware, and there are several email messages detected as containing malware.</span></span> <span data-ttu-id="2aac0-182">[**電子メール**] タブを選択し、1つ以上の電子メールメッセージを選択してから、[**操作**] メニューで [**調査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-182">You can select the **Email** tab, select one or more email messages, and then, on the **Actions** menu, select **Investigate**.</span></span> 

![エクスプローラーでのマルウェアの調査の開始](media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="2aac0-184">通知によってトリガーされるプレイブックに似ていますが、エクスプローラーのビューからトリガーされる自動調査には、ルート調査、脅威を識別して関連付けを行うための手順、およびそれらの脅威を軽減するための推奨措置が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-184">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="get-started"></a><span data-ttu-id="2aac0-185">作業の開始</span><span class="sxs-lookup"><span data-stu-id="2aac0-185">Get started</span></span>

<span data-ttu-id="2aac0-186">Office 365 のグローバル管理者、セキュリティ管理者、またはセキュリティリーダーとして調査にアクセスするには、セキュリティ &[https://protection.office.com](https://protection.office.com)コンプライアンスセンター () に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="2aac0-186">To access your investigations, as an Office 365 global administrator, security administrator, or security reader, go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span> <span data-ttu-id="2aac0-187">次に、以下のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2aac0-187">Then, do one of the following:</span></span>

- <span data-ttu-id="2aac0-188">左側のナビゲーションで、[アラート\*\*\*\* > **表示の通知**] に移動し、調査関連の通知の1つを開いてから、通知のポップアップの下部にある [**調査の表示**] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2aac0-188">In the left navigation, go to **Alerts** > **View alerts**, open one of the investigation related alerts, then click the **View investigation** link at the bottom of the alert flyout.</span></span> 

    <span data-ttu-id="2aac0-189">または</span><span class="sxs-lookup"><span data-stu-id="2aac0-189">or</span></span>

- <span data-ttu-id="2aac0-190">左側のナビゲーションで、[**脅威管理** > の**調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-190">In the left navigation, go to **Threat management** > **Investigations**.</span></span>

    <span data-ttu-id="2aac0-191">または</span><span class="sxs-lookup"><span data-stu-id="2aac0-191">or</span></span>

- <span data-ttu-id="2aac0-192">脅威管理ダッシュボード (セキュリティ & コンプライアンスセンターで、[**脅威管理** > **ダッシュボード**] に移動します) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2aac0-192">Visit the Threat management dashboard (In the Security & Compliance Center, go to **Threat management** > **Dashboard**).</span></span>

![エアウィジェット](media/air-widgets.png)

<span data-ttu-id="2aac0-194">エアウィジェットは、[セキュリティダッシュボード](security-dashboard.md)の上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-194">Your AIR widgets will appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="2aac0-195">開始するウィジェットを選択します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-195">Select a widget to get started.</span></span>

<span data-ttu-id="2aac0-196">また、関連するアラートから直接調査にアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-196">You may also access an investigation directly from the related Alerts.</span></span>

### <a name="automated-investigations"></a><span data-ttu-id="2aac0-197">自動調査</span><span class="sxs-lookup"><span data-stu-id="2aac0-197">Automated investigations</span></span>

<span data-ttu-id="2aac0-198">[自動調査] ページには、組織の調査とその現在の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-198">The automated investigations page shows your organization's investigations and their current states.</span></span>

![エアのメイン調査ページ](media/air-maininvestigationpage.png) 
  
<span data-ttu-id="2aac0-200">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-200">You can:</span></span>
- <span data-ttu-id="2aac0-201">調査に直接ナビゲートします (**調査 ID**を選択します)。</span><span class="sxs-lookup"><span data-stu-id="2aac0-201">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="2aac0-202">フィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-202">Apply filters.</span></span> <span data-ttu-id="2aac0-203">調査の**種類**、**時間の範囲**、**状態**、またはこれらの組み合わせから選択します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-203">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="2aac0-204">データを CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2aac0-204">Export the data to a CSV file.</span></span>

<span data-ttu-id="2aac0-205">調査の状態は、分析およびアクションの進行状況を示します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-205">The investigation status indicates the progress of the analysis and actions.</span></span> <span data-ttu-id="2aac0-206">調査を実行すると、脅威が検出されたかどうか、およびアクションが承認されたかどうかを示すように状態が変化します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-206">As the investigation runs, the status will change to indicate whether threats were found, as well as indicate whether actions have been approved.</span></span> 
- <span data-ttu-id="2aac0-207">**開始**: 間もなく開始されるように調査をキューに入れます</span><span class="sxs-lookup"><span data-stu-id="2aac0-207">**Starting**: The investigation is queued to begin soon</span></span>
- <span data-ttu-id="2aac0-208">**実行**: 調査が開始され、「分析」を行っています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-208">**Running**: The investigation has started and is conducting its' analysis</span></span>
- <span data-ttu-id="2aac0-209">**脅威が検出されません**でした: 調査は ' 分析を完了し、脅威が検出されませんでした</span><span class="sxs-lookup"><span data-stu-id="2aac0-209">**No Threats Found**: The investigation has completed its' analysis and no threats were found</span></span>
- <span data-ttu-id="2aac0-210">**システムによって終了**しました。調査は閉じられず、7日後に期限が切れました</span><span class="sxs-lookup"><span data-stu-id="2aac0-210">**Terminated By System**: The investigation was not closed and expired after 7 days</span></span>
- <span data-ttu-id="2aac0-211">**保留中のアクション**: 推奨されるアクションを含む脅威を検出しました</span><span class="sxs-lookup"><span data-stu-id="2aac0-211">**Pending Action**: The investigation found threats with actions recommended</span></span>
- <span data-ttu-id="2aac0-212">**検出された脅威**: 調査は脅威を検出しましたが、脅威には AIR 内で使用可能なアクションがありません</span><span class="sxs-lookup"><span data-stu-id="2aac0-212">**Threats Found**: The investigation found threats, but the threats do not have actions available within AIR</span></span>
- <span data-ttu-id="2aac0-213">**修復**済み: investgation が完了し、完全に修復されました (すべてのアクションが承認されました)</span><span class="sxs-lookup"><span data-stu-id="2aac0-213">**Remediated**: The investgation finished and was fully remediated (all actions were approved)</span></span>
- <span data-ttu-id="2aac0-214">**部分的な修復**: 調査が終了し、推奨されるアクションのいくつかが承認されました</span><span class="sxs-lookup"><span data-stu-id="2aac0-214">**Partially Remediated**: The investigation finished and some of the recommended actions were approved</span></span>
- <span data-ttu-id="2aac0-215">**ユーザーによる終了**: 管理者が調査を終了しました</span><span class="sxs-lookup"><span data-stu-id="2aac0-215">**Terminated By User**: An admin terminated the investigation</span></span>
- <span data-ttu-id="2aac0-216">**失敗**: 調査中にエラーが発生し、脅威の結論に達しませんでした</span><span class="sxs-lookup"><span data-stu-id="2aac0-216">**Failed**: An error occurred during the investigation that prevented it from reaching a conclusion on threats</span></span>
- <span data-ttu-id="2aac0-217">**スロットルでキューに入れら**れた: システム処理の制限のために調査を待機しています (サービスのパフォーマンスを保護するため)</span><span class="sxs-lookup"><span data-stu-id="2aac0-217">**Queued By Throttling**: The investigation is waiting for analysis due to system processing limitations (to protect service performance)</span></span>
- <span data-ttu-id="2aac0-218">**調整によって終了**: ボリュームとシステムの処理の制限により、調査は十分な時間で完了しませんでした。</span><span class="sxs-lookup"><span data-stu-id="2aac0-218">**Terminated By Throttling**: The investigation could not be completed in sufficient time due to investigation volume and system processing limitations.</span></span> <span data-ttu-id="2aac0-219">エクスプローラーで電子メールを選択して [調査] アクションを選択すると、調査を再始動できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-219">You can re-trigger the investigation by selecting the email in Explorer and selecting the Investigate action.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="2aac0-220">調査グラフ</span><span class="sxs-lookup"><span data-stu-id="2aac0-220">Investigation graph</span></span>

<span data-ttu-id="2aac0-221">特定の調査を開くと、[調査中] グラフページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-221">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="2aac0-222">このページには、発生した警告の一部として自動的に調査された、電子メールメッセージ、ユーザー (およびそのアクティビティ)、およびデバイスのすべての異なるエンティティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-222">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![AIR 調査グラフページ](media/air-investigationgraphpage.png)

<span data-ttu-id="2aac0-224">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-224">You can:</span></span>
- <span data-ttu-id="2aac0-225">現在の調査の視覚的な概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-225">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="2aac0-226">調査期間の概要を表示します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-226">View a summary of the investigation duration.</span></span>
- <span data-ttu-id="2aac0-227">ビジュアル化内のノードを選択して、そのノードの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-227">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="2aac0-228">上部にあるタブを選択すると、そのタブの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-228">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="2aac0-229">アラートの調査</span><span class="sxs-lookup"><span data-stu-id="2aac0-229">Alert investigation</span></span>

<span data-ttu-id="2aac0-230">調査の [**通知**] タブでは、調査に関連する警告を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-230">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="2aac0-231">詳細には、調査に関連する、危険なサインイン、大量ダウンロードなどのアラートをトリガーした通知が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-231">Details include the alert that triggered the investigation and other alerts, such as risky sign-in, mass download, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="2aac0-232">このページでは、セキュリティアナリストが個々の通知に関する追加情報を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-232">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![AIR alerts ページ](media/air-investigationalertspage.png)

<span data-ttu-id="2aac0-234">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-234">You can:</span></span>
- <span data-ttu-id="2aac0-235">現在のトリガー警告と関連付けられている警告の視覚的な概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-235">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="2aac0-236">リストから通知を選択して、完全な通知の詳細を表示するフライアウトページを開きます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-236">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="2aac0-237">電子メールの調査</span><span class="sxs-lookup"><span data-stu-id="2aac0-237">Email investigation</span></span>

<span data-ttu-id="2aac0-238">調査の [**電子メール**] タブでは、調査の一部として識別されたすべての電子メールのクラスターを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-238">On the **Email** tab for an investigation, you can see all the clusters of email identified as part of the investigation.</span></span> 

<span data-ttu-id="2aac0-239">ユーザーが組織内のユーザーによって送受信する、膨大な量の電子メールがあることを考えると、</span><span class="sxs-lookup"><span data-stu-id="2aac0-239">Given the sheer volume of email that users in an organization send and receive, the process of</span></span> 
- <span data-ttu-id="2aac0-240">メッセージヘッダー、本文、URL、および添付ファイルから類似した属性に基づいて電子メールメッセージをクラスタリングする。</span><span class="sxs-lookup"><span data-stu-id="2aac0-240">clustering email messages based on similar attributes from a message header, body, URL and attachments;</span></span> 
- <span data-ttu-id="2aac0-241">悪意のある電子メールを適切な電子メールから分離します。そして</span><span class="sxs-lookup"><span data-stu-id="2aac0-241">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="2aac0-242">悪意のある電子メールメッセージに対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="2aac0-242">taking action on malicious email messages</span></span> 

<span data-ttu-id="2aac0-243">数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2aac0-243">can take many hours.</span></span> <span data-ttu-id="2aac0-244">AIR でこのプロセスが自動化され、組織のセキュリティチームの時間と労力を節約できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2aac0-244">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="2aac0-245">電子メールの分析の手順では、2つの異なる種類の電子メールクラスター (類似性クラスター、およびインジケータークラスター) を識別できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-245">Two different types of email clusters may be identified during the email analysis step: similarity clusters, and indicator clusters.</span></span> 
- <span data-ttu-id="2aac0-246">類似性クラスターは、類似した送信者とコンテンツの属性を含む電子メールメッセージです。</span><span class="sxs-lookup"><span data-stu-id="2aac0-246">Similarity clusters are email messages that contain similar sender and content attributes.</span></span> <span data-ttu-id="2aac0-247">これらのクラスターは、元の検出結果に基づいて、悪意のあるコンテンツに対して評価されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-247">These clusters are evaluated for malicious content based on the original detection findings.</span></span> <span data-ttu-id="2aac0-248">十分な数の悪意のある検出を含む電子メールクラスターは、悪意のあるものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-248">Email clusters that contain enough malicious detections will be considered malicious.</span></span>
- <span data-ttu-id="2aac0-249">インジケータークラスターは、元の電子メールから同じインジケーターエンティティ (ファイルハッシュまたは URL) を含む電子メールメッセージです。</span><span class="sxs-lookup"><span data-stu-id="2aac0-249">Indicator clusters are email messages that contain the same indicator entity (file hash or URL) from the original email.</span></span> <span data-ttu-id="2aac0-250">元のファイルまたは URL エンティティが悪意のあるものとして識別されると、AIR はそのエンティティを含む電子メールメッセージのクラスター全体にインジケーター verdict を適用します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-250">When the original file/URL entity is identified as malicious, AIR will apply the indicator verdict to the entire cluster of email messages containing that entity.</span></span> <span data-ttu-id="2aac0-251">マルウェアとして識別されたファイルは、そのファイルを含む電子メールメッセージのクラスターがマルウェアの電子メールメッセージとして扱われることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-251">As a file identified as malware will mean that the cluster of email messages containing that file will be treated as malware email messages.</span></span>

<span data-ttu-id="2aac0-252">クラスタリングの目的は、攻撃またはキャンペーンの一部として同じ送信者によって送信されるその他の関連する電子メールメッセージを検索することです。</span><span class="sxs-lookup"><span data-stu-id="2aac0-252">The goal of clustering is to find other related email messages that are sent by the same sender as part of an attack or a campaign.</span></span>

<span data-ttu-id="2aac0-253">[**電子メール**] タブには、ユーザーが報告した電子メールの詳細、元の電子メール報告、マルウェア/フィッシングのための電子メールメッセージの zapped など、調査に関連する電子メールアイテムも表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-253">The **Email** tab will also show email items related to the investigation, such as the user-reported email details, the original email reported, the email message(s) zapped due to malware/phish, etc.</span></span>

<span data-ttu-id="2aac0-254">[電子メール] タブで特定された電子メールの数は、[**電子**メール] タブに表示されているすべての電子メールメッセージの合計数を表します。複数のクラスターに電子メールメッセージが表示されるため、識別された電子メールメッセージの実際の合計数 (および修復アクションの影響を受ける) は、すべてのクラスターと元の受信者の電子メールに含まれる一意の電子メールメッセージの数になります。メッセージ.</span><span class="sxs-lookup"><span data-stu-id="2aac0-254">The email count identified on the email tab currently represents the sum total of all email messages shown on the **Email** tab. Since email messages will be present in multiple clusters, the actual total count of email messages identified (and affected by remediation actions) will be the count of unique email messages present across all of the clusters and original recipients' email messages.</span></span> 

<span data-ttu-id="2aac0-255">セキュリティ verdicts、操作、および配信場所は受信者ごとに異なるため、Explorer と AIR count の両方の電子メールメッセージは受信者ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="2aac0-255">Both Explorer and AIR count email messages on a per recipient basis, since the security verdicts, actions, and delivery locations will vary on a per recipient basis.</span></span> <span data-ttu-id="2aac0-256">そのため、3人のユーザーに送信される元の電子メールは、1つの電子メールではなく、合計で3つの電子メールメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-256">Thus an original email sent to three users will count as a total of three email messages instead of one email.</span></span> <span data-ttu-id="2aac0-257">注メールが2回以上カウントされる場合があります。そのため、電子メールには複数のアクションがあり、すべてのアクションが実行された後に電子メールのコピーが複数存在する可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="2aac0-257">Note there may be cases where an email gets counted two or more times, since the email may have multiple actions on it and there may be multiple copies of the email once all actions occur.</span></span> <span data-ttu-id="2aac0-258">たとえば、配信時に検出されたマルウェア電子メールによって、ブロックされた (検疫された) 電子メールと、置き換えられた電子メール (脅威ファイルが警告ファイルに置き換えられ、ユーザーのメールボックスに配信される) の両方が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2aac0-258">For example a malware email that is detected at delivery may result in both a blocked (quarantined) email and a replaced email (threat file replaced with an warning file, then delivered to user's mailbox).</span></span> <span data-ttu-id="2aac0-259">システムに電子メールのコピーが文字どおり2つあるため、これらは両方ともクラスター数でカウントされます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-259">Since there are literally two copies of the email in the system - these may both be counted in cluster counts.</span></span> 

<span data-ttu-id="2aac0-260">メール数は調査時に計算され、調査 flyouts を開くと (基になるクエリに基づいて) いくつかのカウントが再計算されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-260">Email counts are calculated at the time of the investigation and some counts are re-calculated when you open investigation flyouts (based on an underlying query).</span></span> <span data-ttu-id="2aac0-261">[電子メール] タブの電子メールクラスターに表示される電子メール数と、調査時にクラスターポップアップに表示される電子メールの数量の値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-261">The email counts shown for the email clusters on the email tab and the email quantity value shown on cluster flyout are calculated at the time of investigation.</span></span> <span data-ttu-id="2aac0-262">クラスターポップアップの [電子メール] タブの下部に表示される電子メール数、およびエクスプローラーに表示される電子メールメッセージの数には、調査の最初の分析後に受信した電子メールメッセージが反映されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-262">The email count shown at the bottom of the email tab of the cluster flyout, as well as the count of email messages shown in Explorer will reflect email messages received after the investigation's initial analysis.</span></span> <span data-ttu-id="2aac0-263">したがって、元の10個の電子メールメッセージを表示する電子メールクラスターでは、調査分析フェーズ間に5つの電子メールメッセージが到着し、管理者が調査をレビューしたときに、電子メールリストの合計が15件表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-263">Thus an email cluster that shows an original quantity of 10 email messages would show an email list total of 15 when 5 more email messages arrive between the investigation analysis phase and when the admin reviews the investigation.</span></span> <span data-ttu-id="2aac0-264">異なるビューで両方のカウントを表示することによって、調査の時点での電子メールの影響を示すと共に、修復が実行されるまでの現在の影響を示します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-264">Showing both counts in different views is done to indicate the email impact at the time of investigation and the current impact up until the time that remediation is run.</span></span>

<span data-ttu-id="2aac0-265">例として、次のシナリオを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-265">As an example, consider the following scenario.</span></span> <span data-ttu-id="2aac0-266">3つの電子メールメッセージの最初のクラスターは、フィッシングであると見なされました。</span><span class="sxs-lookup"><span data-stu-id="2aac0-266">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="2aac0-267">同じ IP および件名を持つ類似メッセージの別のクラスターが検出され、悪意のあるものと見なされました。それらの一部は、初期検出時にフィッシングとして識別されています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-267">Another cluster of similar messages with the same IP and subject was found and considered malicious, as some of them were identified as phish during initial detection.</span></span> 

![航空電子メールの調査ページ](media/air-investigationemailpage.png)

<span data-ttu-id="2aac0-269">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-269">You can:</span></span>
- <span data-ttu-id="2aac0-270">現在のクラスター化の結果と脅威の視覚的な概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-270">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="2aac0-271">クラスターエンティティまたは脅威リストをクリックして、完全なアラート詳細を示すフライアウトページを開きます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-271">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>
- <span data-ttu-id="2aac0-272">[電子メールクラスターの詳細] タブの上部にある [エクスプローラーで開く] リンクをクリックして、電子メールクラスターをさらに調査します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-272">Further investigate the email cluster by clicking the 'Open in Explorer' link at the top of the 'Email cluster details' tab</span></span>

![フライアウトの詳細を含む電子メールの調査](media/air-investigationemailpageflyoutdetails.png)

<span data-ttu-id="2aac0-274">\* 注: 電子メールのコンテキストでは、調査の一環としてボリュームの異常な脅威が表面化することがあります。</span><span class="sxs-lookup"><span data-stu-id="2aac0-274">\*Note: In the context of email, you may see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="2aac0-275">ボリュームが異常である場合は、以前のタイムフレームと比較して、同様の電子メールメッセージの中で、調査のイベント時間に比べてスパイクがあることを示します</span><span class="sxs-lookup"><span data-stu-id="2aac0-275">A volume anomaly indicates a spike in similar email messages around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="2aac0-276">これと同様の特徴 (たとえば、件名や送信者ドメイン、本文の類似性、送信者の IP など) を含む電子メールトラフィックのスパイクは、電子メールのキャンペーンまたは攻撃の開始の一般的なものです。</span><span class="sxs-lookup"><span data-stu-id="2aac0-276">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span> <span data-ttu-id="2aac0-277">しかし、バルク、スパム、合法的な電子メールキャンペーンは、一般的にこれらの特性を共有しています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-277">However, bulk, spam, and legitimate email campaigns commonly share these characteristics.</span></span> <span data-ttu-id="2aac0-278">ボリュームの異常は潜在的な脅威を表し、ウイルス対策エンジン、分析、または悪意のある評価によって特定されたマルウェアまたはフィッシングの脅威と比較して、それほど深刻ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2aac0-278">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="2aac0-279">ユーザー調査</span><span class="sxs-lookup"><span data-stu-id="2aac0-279">User investigation</span></span>

<span data-ttu-id="2aac0-280">[**ユーザー** ] タブには、調査の一部として特定されたすべてのユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-280">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> <span data-ttu-id="2aac0-281">ユーザーが影響を受けたり、侵害された可能性があることを示すイベントが発生すると、調査でユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-281">Users will appear in the investigation when there is an event or indication that the user may be affected or compromised.</span></span>

<span data-ttu-id="2aac0-282">たとえば、次の画像では、AIR は、作成された新しい受信トレイルールに基づいて、侵害と異常のインジケーターを識別しています。</span><span class="sxs-lookup"><span data-stu-id="2aac0-282">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="2aac0-283">調査の詳細 (エビデンス) は、このタブ内の詳細なビューから利用できます。侵害と異常のインジケーターには、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)からの異常な検出が含まれることもあります。</span><span class="sxs-lookup"><span data-stu-id="2aac0-283">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies may also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![AIR 調査ユーザーページ](media/air-investigationuserspage.png)

<span data-ttu-id="2aac0-285">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-285">You can:</span></span>
- <span data-ttu-id="2aac0-286">検出されたユーザーの結果とリスクの視覚的な概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-286">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="2aac0-287">通知の詳細をすべて表示するユーザーを選択して、フライアウトページを開きます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-287">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="2aac0-288">コンピューターの調査</span><span class="sxs-lookup"><span data-stu-id="2aac0-288">Machine investigation</span></span>

<span data-ttu-id="2aac0-289">[**コンピューター** ] タブに、調査の一部として特定されたすべてのマシンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-289">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![AIR 調査のコンピューターページ](media/air-investigationmachinepage.png)

<span data-ttu-id="2aac0-291">調査の一環として、空気は電子メールの脅威をデバイスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-291">As part of the investigation, AIR correlates email threats to devices.</span></span> <span data-ttu-id="2aac0-292">たとえば、調査では、 [Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
)に対して悪意のあるファイルハッシュを渡して調査を行います。</span><span class="sxs-lookup"><span data-stu-id="2aac0-292">For example, an investigation passes a malicious file hash across to [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) to investigate.</span></span> <span data-ttu-id="2aac0-293">これにより、ユーザーにとって関連するコンピューターの自動調査が可能になり、クラウドとエンドポイントの両方で脅威に対処できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2aac0-293">This allows for automated investigation of relevant machines for your users, to help ensure that threats are addressed both in the cloud and across your endpoints.</span></span> 

<span data-ttu-id="2aac0-294">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-294">You can:</span></span>
- <span data-ttu-id="2aac0-295">現在のコンピューターと脅威の視覚的な概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-295">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="2aac0-296">Microsoft Defender セキュリティセンターの関連する[Microsoft DEFENDER ATP 調査](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)に含まれるビューを開くコンピューターを選択します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-296">Select a machine to open a view that into the related [Microsoft Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) in the Microsoft Defender Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="2aac0-297">エンティティの調査</span><span class="sxs-lookup"><span data-stu-id="2aac0-297">Entity investigation</span></span>

<span data-ttu-id="2aac0-298">[**エンティティ**] タブには、調査の一部として特定されたすべてのエンティティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-298">On the **Entities** tab, you can see all the entities identified as part of the investigation.</span></span> 

<span data-ttu-id="2aac0-299">ここでは、調査されたエンティティと、電子メールメッセージ、クラスター、IP アドレス、ユーザーなどのエンティティの種類の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-299">Here, you can see the investigated entities and details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="2aac0-300">また、分析されたエンティティの数と、それぞれに関連付けられている脅威も確認できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-300">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

![AIR 調査エンティティページ](media/air-investigationentitiespage.png)

<span data-ttu-id="2aac0-302">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-302">You can:</span></span>
- <span data-ttu-id="2aac0-303">検出されたエンティティと脅威の視覚的な概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-303">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="2aac0-304">エンティティを選択して、関連するエンティティの詳細を示すフライアウトページを開きます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-304">Select an entity to open a fly-out page that shows the related entity details.</span></span>

![エア調査エンティティの詳細](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="2aac0-306">プレイブックログ</span><span class="sxs-lookup"><span data-stu-id="2aac0-306">Playbook log</span></span>

<span data-ttu-id="2aac0-307">[**ログ**] タブには、調査中に発生したすべてのプレイブックステップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-307">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="2aac0-308">このログは、Office 365 の自動調査機能によって実行されたすべての操作の完全なインベントリを AIR の一部としてキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="2aac0-308">The log captures a complete inventory of all actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="2aac0-309">アクション自体、説明、および開始から終了までの実績の期間を含む、実行されたすべてのステップを明確に表示できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-309">It provides a clear view of all the steps taken, including the action itself, a description, and the duration of the actual from start to finish.</span></span> 

![AIR 調査ログページ](media/air-investigationlogpage.png)

<span data-ttu-id="2aac0-311">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-311">You can:</span></span>
- <span data-ttu-id="2aac0-312">「」では、実行されるプレイブックの手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-312">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="2aac0-313">結果を CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2aac0-313">Export the results to a CSV file.</span></span>
- <span data-ttu-id="2aac0-314">ビューをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-314">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="2aac0-315">推奨されるアクション</span><span class="sxs-lookup"><span data-stu-id="2aac0-315">Recommended actions</span></span>

<span data-ttu-id="2aac0-316">[ **Actions** ] タブには、調査の完了後に修復するために推奨されているすべてのプレイブックアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-316">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="2aac0-317">処置調査の最終段階で、Microsoft が推奨する手順をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="2aac0-317">Actions capture the steps Microsoft recommends you take at the end of a investigation.</span></span> <span data-ttu-id="2aac0-318">ここでは、1つ以上のアクションを選択することにより、修復のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-318">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="2aac0-319">[**承認**] をクリックすると、修復を開始できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-319">Clicking **Approve** will allow remediation to begin.</span></span> <span data-ttu-id="2aac0-320">(適切なアクセス許可が必要です-エクスプローラーと AIR からアクションを実行するには、「検索と削除」の役割が必要です。)</span><span class="sxs-lookup"><span data-stu-id="2aac0-320">(Appropriate permissions are needed - the 'Search And Purge' role is required to run actions from Explorer and AIR).</span></span> <span data-ttu-id="2aac0-321">たとえば、セキュリティ閲覧者はアクションを表示できますが、承認することはできません。</span><span class="sxs-lookup"><span data-stu-id="2aac0-321">For example, a Security Reader can view actions but not approve them.</span></span> <span data-ttu-id="2aac0-322">注: すべてのアクションを承認する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2aac0-322">Note - you do not have to approve every action.</span></span> <span data-ttu-id="2aac0-323">推奨されるアクションと一致しない場合、または組織で特定の種類のアクションが選択されていない場合は、アクションを**拒否**するか、無視して操作を行わないかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-323">If you do not agree with the recommended action or your organization does not choose certain types of actions - then you can either choose to **Reject** the actions or simply ignore them and take no action.</span></span> <span data-ttu-id="2aac0-324">すべてのアクションを承認または拒否すると、調査が完全に終了し、一部のアクションが不完全になるため、調査の状態が部分的に修復された状態に変化します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-324">Approving and/or rejecting all actions will let the investigation fully close, while leaving some actions incomplete will result in the investigation status changing to a partially remediated state.</span></span>

![AIR 調査アクションページ](media/air-investigationactionspage.png)

<span data-ttu-id="2aac0-326">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-326">You can:</span></span>
- <span data-ttu-id="2aac0-327">プレイブックの概要を表示します。推奨されるアクション。</span><span class="sxs-lookup"><span data-stu-id="2aac0-327">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="2aac0-328">1つまたは複数のアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-328">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="2aac0-329">コメントを含む推奨アクションを承認または拒否します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-329">Approve or reject recommended actions with comments.</span></span>
- <span data-ttu-id="2aac0-330">結果を CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2aac0-330">Export the results to a CSV file.</span></span>
- <span data-ttu-id="2aac0-331">ビューをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="2aac0-331">Filter the view.</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="2aac0-332">エアを入手する方法</span><span class="sxs-lookup"><span data-stu-id="2aac0-332">How to get AIR</span></span>

<span data-ttu-id="2aac0-333">現時点では、Office 365 AIR 機能はプレビュー段階にあります。</span><span class="sxs-lookup"><span data-stu-id="2aac0-333">Currently, Office 365 AIR features are in preview.</span></span> <span data-ttu-id="2aac0-334">一般公開されている場合、Office 365 AIR 機能は次のサブスクリプションに含まれます。</span><span class="sxs-lookup"><span data-stu-id="2aac0-334">When generally available, Office 365 AIR features will be included in the following subscriptions:</span></span>

- <span data-ttu-id="2aac0-335">Microsoft 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="2aac0-335">Microsoft 365 Enterprise E5</span></span>
- <span data-ttu-id="2aac0-336">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="2aac0-336">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="2aac0-337">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2aac0-337">Microsoft Threat Protection</span></span>
- <span data-ttu-id="2aac0-338">Office 365 Advanced Threat Protection プラン2</span><span class="sxs-lookup"><span data-stu-id="2aac0-338">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="2aac0-339">機能の可用性の詳細については、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2aac0-339">To learn more about feature availability, visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>
