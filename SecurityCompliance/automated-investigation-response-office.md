---
title: Office 365 を使用した自動調査と応答 (AIR)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection の自動化された調査と応答機能について説明します。
ms.openlocfilehash: c6cfc03588e580382f673b2e9be8543bfcaf9ac1
ms.sourcegitcommit: f6073deec39a18581ed12abef18728417a52cdf4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2019
ms.locfileid: "30747563"
---
# <a name="automated-investigation-and-response-air-with-office-365"></a><span data-ttu-id="7ffbd-103">Office 365 を使用した自動調査と応答 (AIR)</span><span class="sxs-lookup"><span data-stu-id="7ffbd-103">Automated Investigation and Response (AIR) with Office 365</span></span>

<span data-ttu-id="7ffbd-104">自動化された調査と対応 (AIR) (近日中に[Office 365 の脅威の調査と応答機能](office-365-ti.md)) を使用すると、現在存在している既知の脅威に対する自動化された調査と修復を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-104">Automated Investigation and Response (AIR) (coming soon to [Office 365 Threat investigation and response capabilities](office-365-ti.md)) enables you to run automated investigation and remediation to well-known threats that exist today.</span></span> <span data-ttu-id="7ffbd-105">この記事では、AIR の概要と、組織およびセキュリティ運用チームがより効果的かつ効率的に脅威を軽減する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-105">Read this article to get an overview of AIR and how it can help your organization and security operations teams mitigate threats more effectively and efficiently.</span></span> <span data-ttu-id="7ffbd-106">AIR に追加機能が利用可能になるタイミングの詳細については、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-106">To learn more about when additional features in AIR will be available, see the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="alerts"></a><span data-ttu-id="7ffbd-107">アラート</span><span class="sxs-lookup"><span data-stu-id="7ffbd-107">Alerts</span></span>

<span data-ttu-id="7ffbd-108">[警告](alert-policies.md#viewing-alerts)は、インシデント対応のセキュリティ運用チームワークフローのトリガーを表します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-108">[Alerts](alert-policies.md#viewing-alerts) represent triggers for Security Operations team workflows for incident response.</span></span> <span data-ttu-id="7ffbd-109">調査のための適切なアラートセットの優先順位付けを行い、対処されていない脅威がないことを確認するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-109">Prioritizing the right set of alerts for investigation while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="7ffbd-110">アラートへの調査が手動で実行される場合、セキュリティ運用チームは脅威からのリスクでエンティティ (コンテンツ、デバイス、ユーザーなど) をハントして関連付けなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-110">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (e.g. content, devices and users) at risk from threats.</span></span> <span data-ttu-id="7ffbd-111">このようなタスクやワークフローは、非常に時間がかかり、複数のツールやシステムが関係しています。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-111">Such tasks and workflows are very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="7ffbd-112">エアの場合、調査と応答は、セキュリティ対応のプレイブックを自動的にトリガーする主要なセキュリティおよび脅威管理警告に自動化されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-112">With AIR, investigation and response are automated into key security and threat management alerts that trigger your security response playbooks automatically.</span></span> 

<span data-ttu-id="7ffbd-113">2019年4月の空気の最初のリリースでは、次のようなメッセージが表示された場合に生成されたアラートが自動的に調査されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-113">In the initial release of AIR in April 2019, alerts generated from following singel events alert policies will be auto-investigated.</span></span> 

1. <span data-ttu-id="7ffbd-114">潜在的に悪意のある URL のクリックが検出された</span><span class="sxs-lookup"><span data-stu-id="7ffbd-114">A potentially malicious URL click was detected</span></span>
2. <span data-ttu-id="7ffbd-115">ユーザーがフィッシングとして報告した電子メール \*</span><span class="sxs-lookup"><span data-stu-id="7ffbd-115">Email reported by user as phish\*</span></span>
3. <span data-ttu-id="7ffbd-116">配信後に削除されたマルウェアを含む電子メールメッセージ \*</span><span class="sxs-lookup"><span data-stu-id="7ffbd-116">Email messages containing malware removed after delivery\*</span></span>
4. <span data-ttu-id="7ffbd-117">配信後に削除されたフィッシング url を含む電子メールメッセージ \*</span><span class="sxs-lookup"><span data-stu-id="7ffbd-117">Email messages containing phish URLs removed after delivery\*</span></span>

<span data-ttu-id="7ffbd-118">\* 注: これらのアラートには、電子メール通知がオフにされた状態で、セキュリティ/コンプライアンスセンター内の各アラートポリシーの「情報」重要度が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-118">\*Note: These alerts have been assigned an "Informational" severity in the respective alert policies within the Security and Compliance Center with email notifications turned off.</span></span> <span data-ttu-id="7ffbd-119">これらは、通知ポリシー構成を使用して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-119">These can be turned on through the Alert policy configuration.</span></span>

<span data-ttu-id="7ffbd-120">通知を表示するには、Office 365 Security & コンプライアンスセンターで、[**通知** > ] [**警告を表示**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-120">To view alerts, in the Office 365 Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="7ffbd-121">通知を選択して詳細を表示します。そこから、[**調査の表示**] リンクを使用して、対応する[調査](#investigation-graph)に移動します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-121">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](#investigation-graph).</span></span>

![調査にリンクされたアラート](media/air-alerts-page-details.png) 


## <a name="security-playbooks"></a><span data-ttu-id="7ffbd-123">セキュリティプレイブック</span><span class="sxs-lookup"><span data-stu-id="7ffbd-123">Security playbooks</span></span>

<span data-ttu-id="7ffbd-124">セキュリティプレイブックは、Microsoft の脅威保護の中核となるバックエンドポリシーです。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-124">Security playbooks are back-end policies that are at the heart of automation in Microsoft Threat Protection.</span></span> <span data-ttu-id="7ffbd-125">AIR で提供されるセキュリティプレイブックは、一般的な実際のセキュリティシナリオに基づいています。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-125">The security playbooks provided in AIR are based on common real-world security scenarios.</span></span> <span data-ttu-id="7ffbd-126">組織内でアラートがトリガーされると、セキュリティによるプレイブックが自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-126">A security playbook is launched automatically when an alert is triggered within your organization.</span></span> <span data-ttu-id="7ffbd-127">アラートがトリガーされると、関連付けられたプレイブックが自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-127">Once the alert triggers, the associated playbook is run automatically.</span></span> <span data-ttu-id="7ffbd-128">プレイブックは、すべての関連するメタデータ (電子メールメッセージ、ユーザー、件名、送信者などを含む) を調べて調査を実行し、その結果に基づいて、組織のセキュリティチームが管理および軽減するために実行できる一連のアクションを推奨します。脅威。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-128">The playbook runs an investigation, looking at all the associated metadata (including email messages, users, subjects, senders, etc.) and, based on its findings, recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="7ffbd-129">空中で利用できるセキュリティプレイブックは、組織が現在直面している最も頻繁な脅威に取り組むように設計されています。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-129">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations face today.</span></span> <span data-ttu-id="7ffbd-130">これらは、Microsoft とお客様の資産を保護する手助けをしているユーザーを含む、セキュリティ運用チームとインシデント対応チームからの入力に基づいています。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-130">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft and our customers assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="7ffbd-131">セキュリティプレイブックは段階的に展開されています。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-131">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="7ffbd-132">航空の一環として、セキュリティプレイブックはフェーズに展開されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-132">As part of AIR, security playbooks are rolling out in phases</span></span>

- <span data-ttu-id="7ffbd-133">**フェーズ 1 (2019 年4月)**: プレイブックには、セキュリティ管理者が確認および承認するアクションに関する推奨事項が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-133">**Phase 1 (April 2019)**: Playbooks include recommendations for actions that security administrators review and approve.</span></span> 

- <span data-ttu-id="7ffbd-134">**フェーズ 2 (2019 年6月)**: セキュリティ管理者は、管理操作なしで自動的にアクションを実行するようにセキュリティプレイブックを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-134">**Phase 2 (June 2019)**: Security administrators will have the option to configure security playbooks to take action automatically, without administrative interaction.</span></span>

<span data-ttu-id="7ffbd-135">フェーズ1には、次のプレイブックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-135">Phase 1 will include the following playbooks:</span></span>
- <span data-ttu-id="7ffbd-136">ユーザーによって報告されるフィッシングメッセージ</span><span class="sxs-lookup"><span data-stu-id="7ffbd-136">User-reported phish message</span></span>
- <span data-ttu-id="7ffbd-137">URL [verdict change] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-137">URL click verdict change</span></span> 
- <span data-ttu-id="7ffbd-138">配信後のマルウェア検出 (マルウェア ZAP)</span><span class="sxs-lookup"><span data-stu-id="7ffbd-138">Malware detected post-delivery (Malware ZAP)</span></span>
- <span data-ttu-id="7ffbd-139">フィッシングは、配信後の zap (フィッシング zap) を検出しました</span><span class="sxs-lookup"><span data-stu-id="7ffbd-139">Phish detected post-delivery ZAP (Phish ZAP)</span></span>
- <span data-ttu-id="7ffbd-140">手動による電子メール調査 (脅威エクスプローラーを使用)</span><span class="sxs-lookup"><span data-stu-id="7ffbd-140">Manual e-mail investigations (using Threat Explorer)</span></span>

<span data-ttu-id="7ffbd-141">フェーズ2では、他のいくつかのプレイブックが計画されています。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-141">Several other playbooks are planned for Phase 2.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="7ffbd-142">プレイブックには、調査と推奨事項が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-142">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="7ffbd-143">各プレイブックには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-143">Each playbook includes:</span></span> 
- <span data-ttu-id="7ffbd-144">ルート調査、</span><span class="sxs-lookup"><span data-stu-id="7ffbd-144">a root investigation,</span></span> 
- <span data-ttu-id="7ffbd-145">他の潜在的な脅威を識別して相互に関連付けるために実行する手順</span><span class="sxs-lookup"><span data-stu-id="7ffbd-145">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="7ffbd-146">推奨される脅威修復アクション。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-146">recommended threat remediation actions.</span></span>

<span data-ttu-id="7ffbd-147">各高度な手順には、脅威への深く、詳細、および完全な応答を提供するために実行される多くのサブステップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-147">Each high-level step includes many sub-steps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-user-reported-phish-message"></a><span data-ttu-id="7ffbd-148">例: ユーザーによって報告されるフィッシングメッセージ</span><span class="sxs-lookup"><span data-stu-id="7ffbd-148">Example: User-reported phish message</span></span>

<span data-ttu-id="7ffbd-149">組織内のユーザーが電子メールメッセージを送信し、 [outlook または outlook Web Access 用のレポートメッセージアドイン](enable-the-report-message-add-in.md)を使用して Microsoft に報告したとき。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-149">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web Access](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="7ffbd-150">これにより、調査のプレイブックが自動的に起動するシステムベースの情報アラートがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-150">This triggers a system-based informational alert that automatically launches the investigation playbook.</span></span>

<span data-ttu-id="7ffbd-151">ルート調査フェーズでは、電子メールのさまざまな側面を評価します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-151">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="7ffbd-152">これらには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-152">These include:</span></span>
- <span data-ttu-id="7ffbd-153">脅威の種類を決定すること。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-153">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="7ffbd-154">送信者。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-154">Who sent it;</span></span>
- <span data-ttu-id="7ffbd-155">電子メールの送信元 (インフラストラクチャの送信)</span><span class="sxs-lookup"><span data-stu-id="7ffbd-155">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="7ffbd-156">電子メールの他のインスタンスが配信またはブロックされたかどうか。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-156">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="7ffbd-157">アナリストからの評価。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-157">An assessment from our analysts;</span></span>
- <span data-ttu-id="7ffbd-158">電子メールが既知のキャンペーンと関連付けられているかどうか。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-158">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="7ffbd-159">その他。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-159">and more.</span></span>

<span data-ttu-id="7ffbd-160">ルート調査の完了後、プレイブックは推奨されるアクションの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-160">After the root investigation is complete, the playbook provides a list of recommended actions to take.</span></span>
  
<span data-ttu-id="7ffbd-161">次に、いくつかの脅威の調査と探しの手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-161">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="7ffbd-162">他の電子メールクラスター内の類似した電子メールメッセージが検索されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-162">Similar email messages in other email clusters are searched.</span></span>
- <span data-ttu-id="7ffbd-163">シグナルは、 [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)などの他のプラットフォームと共有されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-163">The signal is shared with other platforms, such as [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="7ffbd-164">疑わしい電子メールメッセージ内のリンクをすべてのユーザーがクリックしたかどうかについての判断が行われます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-164">A determination is made on whether any users have clicked through any links in suspicious email messages.</span></span>
- <span data-ttu-id="7ffbd-165">チェックは、office 365 Exchange online protection ([EOP]) (EOP/exchange-Online-EOP) および office 365 Advanced ([ATP]) (office-365-atp.md) に対して実行され、ユーザーによって報告された他の類似メッセージがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-165">A check is done across Office 365 Exchange Online Protection ([EOP])(eop/exchange-online-protection-eop.md) and Office 365 Advanced Therat Protection ([ATP])(office-365-atp.md) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="7ffbd-166">ユーザーが侵害されていないかどうかを確認するためのチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-166">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="7ffbd-167">このチェックでは、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)と[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)の間の信号を活用し、関連するユーザーアクティビティの異常を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-167">This check leverages signals across [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span> 

<span data-ttu-id="7ffbd-168">お探しの段階では、さまざまなお探しのステップにリスクと脅威が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-168">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span>  

<span data-ttu-id="7ffbd-169">修復は、プレイブックの最終段階です。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-169">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="7ffbd-170">このフェーズでは、調査とお探しのフェーズに基づいて、修復手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-170">During this phase, remediation steps are taken, based on theinvestigation and hunting phases.</span></span>  

## <a name="getting-started"></a><span data-ttu-id="7ffbd-171">はじめに</span><span class="sxs-lookup"><span data-stu-id="7ffbd-171">Getting started</span></span>

<span data-ttu-id="7ffbd-172">office 365 のグローバル管理者、セキュリティ管理者、またはセキュリティリーダとして調査にアクセスするには、office 365 security &[https://protection.office.com](https://protection.office.com)コンプライアンスセンター () に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-172">To access your investigations, as an Office 365 global administrator, security administrator, or security reader, Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span> <span data-ttu-id="7ffbd-173">次に、以下のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-173">Then, do one of the following:</span></span>

- <span data-ttu-id="7ffbd-174">左側のナビゲーションで、[**脅威管理** > の**調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-174">In the left navigation, go to **Threat management** > **Investigations**.</span></span>

    <span data-ttu-id="7ffbd-175">または</span><span class="sxs-lookup"><span data-stu-id="7ffbd-175">or</span></span>

- <span data-ttu-id="7ffbd-176">脅威管理ダッシュボード (セキュリティ & コンプライアンスセンターで、[**脅威管理** > ]**ダッシュボード**) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-176">Visit the Threat management dashboard (In the Security & Compliance Center, go to **Threat management** > **Dashboard**).</span></span>

![エアウィジェット](media/air-widgets.png)

<span data-ttu-id="7ffbd-178">エアウィジェットは、[セキュリティダッシュボード](security-dashboard.md)の上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-178">Your AIR widgets will appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="7ffbd-179">開始するウィジェットを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-179">Select a widget to get started.</span></span>

<span data-ttu-id="7ffbd-180">関連するアラートから直接 invesitgation にアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-180">You may also access an invesitgation directly from the related Alerts.</span></span>

### <a name="automated-investigations"></a><span data-ttu-id="7ffbd-181">自動調査</span><span class="sxs-lookup"><span data-stu-id="7ffbd-181">Automated investigations</span></span>

<span data-ttu-id="7ffbd-182">[自動調査] ページには、組織の調査とその現在の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-182">The automated investigations page shows your organization's investigations and their current states.</span></span>

![エアのメイン調査ページ](media/air-maininvestigationpage.png) 
  
<span data-ttu-id="7ffbd-184">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-184">You can:</span></span>
- <span data-ttu-id="7ffbd-185">調査に直接ナビゲートします (**調査 ID**を選択します)。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-185">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="7ffbd-186">フィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-186">Apply filters.</span></span> <span data-ttu-id="7ffbd-187">調査の**種類**、**時間の範囲**、**状態**、またはこれらの組み合わせから選択します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-187">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="7ffbd-188">データを CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-188">Export the data to a CSV file.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="7ffbd-189">調査グラフ</span><span class="sxs-lookup"><span data-stu-id="7ffbd-189">Investigation graph</span></span>

<span data-ttu-id="7ffbd-190">特定の調査を開くと、[調査中] グラフページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-190">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="7ffbd-191">このページには、発生した警告の一部として自動的に調査された、電子メールメッセージ、ユーザー (およびそのアクティビティ)、およびデバイスのすべての異なるエンティティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-191">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![AIR 調査グラフページ](media/air-investigationgraphpage.png)

<span data-ttu-id="7ffbd-193">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-193">You can:</span></span>
- <span data-ttu-id="7ffbd-194">現在の調査の視覚的な概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-194">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="7ffbd-195">調査のタイミングの概要を表示します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-195">View a summary of the investigation timings.</span></span>
- <span data-ttu-id="7ffbd-196">ビジュアル化内のノードを選択して、そのノードの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-196">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="7ffbd-197">上部にあるタブを選択すると、そのタブの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-197">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="7ffbd-198">アラートの調査</span><span class="sxs-lookup"><span data-stu-id="7ffbd-198">Alert investigation</span></span>

<span data-ttu-id="7ffbd-199">調査の [**通知**] タブでは、調査に関連する警告を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-199">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="7ffbd-200">詳細には、調査に関連する、危険なサインイン、大量ダウンロードなどのアラートをトリガーした通知が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-200">Details include the alert that triggered the investigation and other alerts, such as risky sign-in, mass download, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="7ffbd-201">このページでは、セキュリティアナリストが個々の通知に関する追加情報を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-201">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![AIR alerts ページ](media/air-investigationalertspage.png)

<span data-ttu-id="7ffbd-203">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-203">You can:</span></span>
- <span data-ttu-id="7ffbd-204">現在のトリガー警告と関連付けられている警告の視覚的な概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-204">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="7ffbd-205">リストから通知を選択して、完全な通知の詳細を表示するフライアウトページを開きます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-205">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="7ffbd-206">電子メールの調査</span><span class="sxs-lookup"><span data-stu-id="7ffbd-206">Email investigation</span></span>

<span data-ttu-id="7ffbd-207">調査の [**電子メール**] タブでは、調査の一部として識別されたすべてのメールクラスターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-207">On the **Email** tab for an investigation, you can see all the email clusters identified as part of the investigation.</span></span> 

<span data-ttu-id="7ffbd-208">ユーザーが組織内のユーザーによって送受信する、膨大な量の電子メールがあることを考えると、</span><span class="sxs-lookup"><span data-stu-id="7ffbd-208">Given the sheer volume of email that users in an organization send and receive, the process of</span></span> 
- <span data-ttu-id="7ffbd-209">メッセージヘッダー、本文、URL、および添付ファイルから類似した属性に基づいて電子メールメッセージをクラスタリングする。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-209">clustering email messages based on similar attributes from a message header, body, URL and attachment;</span></span> 
- <span data-ttu-id="7ffbd-210">悪意のある電子メールを適切な電子メールから分離します。そして</span><span class="sxs-lookup"><span data-stu-id="7ffbd-210">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="7ffbd-211">悪意のある電子メールメッセージに対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="7ffbd-211">taking action on malicious email messages</span></span> 

<span data-ttu-id="7ffbd-212">数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-212">can take many hours.</span></span> <span data-ttu-id="7ffbd-213">AIR でこのプロセスが自動化され、組織のセキュリティチームの時間と労力を節約できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-213">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="7ffbd-214">例として、次のシナリオを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-214">As an example, consider the following scenario.</span></span> <span data-ttu-id="7ffbd-215">3つの電子メールメッセージの最初のクラスターは、フィッシングであると見なされました。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-215">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="7ffbd-216">同じ IP および件名を持つ類似メッセージの別のクラスターが検出され、悪意のあるものと見なされました。それらの一部は、初期検出時にフィッシングとして識別されています。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-216">Another cluster of similar messages with the same IP and subject was found and considered  malicious, as some of them were identified as phish during initial detection.</span></span> 

![航空電子メールの調査ページ](media/air-investigationemailpage.png)

<span data-ttu-id="7ffbd-218">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-218">You can:</span></span>
- <span data-ttu-id="7ffbd-219">現在のクラスター化の結果と脅威の視覚的な概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-219">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="7ffbd-220">クラスターエンティティまたは脅威リストをクリックして、完全なアラート詳細を示すフライアウトページを開きます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-220">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>

![フライアウトの詳細を含む電子メールの調査](media/air-investigationemailpageflyoutdetails.png)

<span data-ttu-id="7ffbd-222">\* 注: 電子メールのコンテキストでは、調査の一環としてボリュームの異常な脅威が表面化することがあります。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-222">\*Note: In the context of email, you may see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="7ffbd-223">ボリューム異常は、過去のタイムフレームと比較して、調査イベントの時間に関する類似した電子メールのスパイクがあることを示します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-223">A volume anomaly indicates a spike in similar emails around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="7ffbd-224">これと同様の特徴 (たとえば、件名や送信者ドメイン、本文の類似性、送信者の IP など) を含む電子メールトラフィックのスパイクは、電子メールのキャンペーンまたは攻撃の開始の一般的なものです。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-224">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span> <span data-ttu-id="7ffbd-225">ただし、バルクおよび spom 電子メールキャンペーンも、これらの特性を共有しています。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-225">However, bulk and spom email campaigns at times also share these characteristics.</span></span> <span data-ttu-id="7ffbd-226">ボリュームの異常は潜在的な脅威を表し、ウイルス対策エンジン、分析、または悪意のある評価によって特定されたマルウェアまたはフィッシングの脅威と比較して、それほど深刻ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-226">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="7ffbd-227">ユーザー調査</span><span class="sxs-lookup"><span data-stu-id="7ffbd-227">User investigation</span></span>

<span data-ttu-id="7ffbd-228">[**ユーザー** ] タブには、調査の一部として特定されたすべてのユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-228">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> 

<span data-ttu-id="7ffbd-229">たとえば、次の画像では、AIR は、作成された新しい受信トレイルールに基づいて、侵害と異常のインジケーターを識別しています。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-229">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="7ffbd-230">調査の詳細 (エビデンス) は、このタブ内の詳細なビューから利用できます。侵害と異常のインジケーターには、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)からの異常な検出が含まれることもあります。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-230">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies may also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![AIR 調査ユーザーページ](media/air-investigationuserspage.png)

<span data-ttu-id="7ffbd-232">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-232">You can:</span></span>
- <span data-ttu-id="7ffbd-233">検出されたユーザーの結果とリスクの視覚的な概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-233">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="7ffbd-234">通知の詳細をすべて表示するユーザーを選択して、フライアウトページを開きます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-234">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="7ffbd-235">コンピューターの調査</span><span class="sxs-lookup"><span data-stu-id="7ffbd-235">Machine investigation</span></span>

<span data-ttu-id="7ffbd-236">[**コンピューター** ] タブに、調査の一部として特定されたすべてのマシンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-236">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![AIR 調査のコンピューターページ](media/air-investigationmachinepage.png)

<span data-ttu-id="7ffbd-238">調査の一環として、空気は電子メールの脅威をデバイスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-238">As part of the investigation, AIR correlates email threats to devices.</span></span> <span data-ttu-id="7ffbd-239">たとえば、調査では、 [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)に対してファイルハッシュを渡して調査します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-239">For example, an investigation passes a file hash across to [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) to investigate.</span></span> <span data-ttu-id="7ffbd-240">これにより、ユーザーにとって関連するコンピューターの自動調査が可能になり、クラウドとデバイスの両方で脅威に対処できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-240">This allows for automated investigation of relevant machines for your users and helps to ensure that threats are addressed both in the cloud and across your devices.</span></span> 

<span data-ttu-id="7ffbd-241">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-241">You can:</span></span>
- <span data-ttu-id="7ffbd-242">現在のコンピューターと脅威の視覚的な概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-242">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="7ffbd-243">windows defender atp セキュリティセンターの関連する[windows defender atp 調査](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)に含まれるビューを開くコンピューターを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-243">Select a machine to open a view that into the related [Windows Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection) in the Windows Defender ATP Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="7ffbd-244">エンティティの調査</span><span class="sxs-lookup"><span data-stu-id="7ffbd-244">Entity investigation</span></span>

<span data-ttu-id="7ffbd-245">[**エンティティ**] タブには、調査の一部として特定されたすべてのコンピューターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-245">On the **Entities** tab, you can see all the machines identified as part of the investigation.</span></span> 

<span data-ttu-id="7ffbd-246">ここでは、調査されたエンティティを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-246">Here, you can see the investigated entities.</span></span> <span data-ttu-id="7ffbd-247">電子メールメッセージ、クラスター、IP アドレス、ユーザーなど、エンティティの種類の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-247">You can see details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="7ffbd-248">また、分析されたエンティティの数と、それぞれに関連付けられている脅威も確認できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-248">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

![AIR 調査エンティティページ](media/air-investigationentitiespage.png)

<span data-ttu-id="7ffbd-250">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-250">You can:</span></span>
- <span data-ttu-id="7ffbd-251">検出されたエンティティと脅威の視覚的な概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-251">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="7ffbd-252">エンティティを選択して、関連するエンティティの詳細を示すフライアウトページを開きます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-252">Select an entity to open a fly-out page that shows the related entity detail.</span></span>

![エア調査エンティティの詳細](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="7ffbd-254">プレイブックログ</span><span class="sxs-lookup"><span data-stu-id="7ffbd-254">Playbook log</span></span>

<span data-ttu-id="7ffbd-255">[**ログ**] タブには、調査中に発生したすべてのプレイブックステップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-255">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="7ffbd-256">このログは、Office 365 の自動調査機能によって実行されたすべての操作の完全なインベントリを AIR の一部としてキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-256">The log captures a complete inventory of all actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="7ffbd-257">アクション自体、説明、開始から終了までの実際の期間など、実行されたすべてのステップを明確に表示できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-257">It provides a clear view of all the steps taken, including the Action itself, a description and the duration of the actual from start to finish.</span></span> 

![AIR 調査ログページ](media/air-investigationlogpage.png)

<span data-ttu-id="7ffbd-259">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-259">You can:</span></span>
- <span data-ttu-id="7ffbd-260">「」では、実行されるプレイブックの手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-260">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="7ffbd-261">結果を CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-261">Export the results to a CSV file.</span></span>
- <span data-ttu-id="7ffbd-262">ビューをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-262">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="7ffbd-263">推奨されるアクション</span><span class="sxs-lookup"><span data-stu-id="7ffbd-263">Recommended actions</span></span>

<span data-ttu-id="7ffbd-264">[ **Actions** ] タブには、調査の完了後に修復するために推奨されているすべてのプレイブックアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-264">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="7ffbd-265">処置調査の最終段階で、Microsoft が推奨する手順をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-265">Actions capture the steps Microsoft recommends you take at the end of a investigation.</span></span> <span data-ttu-id="7ffbd-266">ここでは、1つ以上のアクションを選択することにより、修復のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-266">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="7ffbd-267">[**承認**] をクリックすると、修復を開始できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-267">Clicking **Approve** will allow remediation to begin.</span></span> <span data-ttu-id="7ffbd-268">(適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-268">(Appropriate permissions will be required.</span></span> <span data-ttu-id="7ffbd-269">たとえば、セキュリティ閲覧者はアクションを表示するが、承認することはできません。)</span><span class="sxs-lookup"><span data-stu-id="7ffbd-269">For example, a Security Reader can view actions but not approve them.)</span></span>  

![AIR 調査アクションページ](media/air-investigationactionspage.png)

<span data-ttu-id="7ffbd-271">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-271">You can:</span></span>
- <span data-ttu-id="7ffbd-272">プレイブックの概要を表示します。推奨されるアクション。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-272">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="7ffbd-273">1つまたは複数のアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-273">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="7ffbd-274">コメントを含む推奨アクションを承認または拒否します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-274">Approve or reject recommended actions with comments.</span></span>
- <span data-ttu-id="7ffbd-275">結果を CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-275">Export the results to a CSV file.</span></span>
- <span data-ttu-id="7ffbd-276">ビューをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-276">Filter the view.</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="7ffbd-277">エアを入手する方法</span><span class="sxs-lookup"><span data-stu-id="7ffbd-277">How to get AIR</span></span>

<span data-ttu-id="7ffbd-278">現時点では、Office 365 AIR はプレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-278">Currently, Office 365 AIR is in preview.</span></span> <span data-ttu-id="7ffbd-279">Office 365 AIR は次のサブスクリプションに含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-279">Office 365 AIR will be included in the following subscriptions:</span></span>

- <span data-ttu-id="7ffbd-280">Microsoft 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="7ffbd-280">Microsoft 365 Enterprise E5</span></span>
- <span data-ttu-id="7ffbd-281">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="7ffbd-281">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="7ffbd-282">Microsoft の脅威保護</span><span class="sxs-lookup"><span data-stu-id="7ffbd-282">Microsoft Threat Protection</span></span>
- <span data-ttu-id="7ffbd-283">Office 365 Advanced Threat Protection プラン2</span><span class="sxs-lookup"><span data-stu-id="7ffbd-283">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="7ffbd-284">機能の可用性の詳細については、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ffbd-284">To learn more about feature availability, visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>
