---
title: Office 365 の脅威インテリジェンスによる自動化された調査と応答 (AIR)
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
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection の自動化された調査と応答機能について説明します。
ms.openlocfilehash: c2d5acd0bf26dc28b30f26488adf47de2c834fb6
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "30736403"
---
# <a name="automated-investigation-and-response-air-with-office-365-threat-intelligence"></a><span data-ttu-id="27ca6-103">Office 365 の脅威インテリジェンスによる自動化された調査と応答 (AIR)</span><span class="sxs-lookup"><span data-stu-id="27ca6-103">Automated Investigation and Response (AIR) with Office 365 Threat Intelligence</span></span>

<span data-ttu-id="27ca6-104">自動化された調査と対応 (AIR) (近日中に[Office 365 の脅威の調査と応答機能](office-365-ti.md)) を使用すると、現在存在している既知の脅威に対する自動化された調査と修復を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-104">Automated Investigation and Response (AIR) (coming soon to [Office 365 Threat investigation and response capabilities](office-365-ti.md)) enables you to run automated investigation and remediation to well-known threats that exist today.</span></span> <span data-ttu-id="27ca6-105">この記事を読むと、AIR の概要と、組織がより効果的かつ効率的に脅威を軽減する方法について理解できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-105">Read this article to get an overview of AIR and how it can help your organization mitigate threats more effectively and efficiently.</span></span> <span data-ttu-id="27ca6-106">利用可能な空気の詳細については、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27ca6-106">Tolearn more about when AIR will be available, see the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="alerts"></a><span data-ttu-id="27ca6-107">アラート</span><span class="sxs-lookup"><span data-stu-id="27ca6-107">Alerts</span></span>

<span data-ttu-id="27ca6-108">[警告](alert-policies.md#viewing-alerts)は、インシデント対応のセキュリティ運用チームワークフローのトリガーを表します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-108">[Alerts](alert-policies.md#viewing-alerts) represent triggers for Security Operations team workflows for incident response.</span></span> <span data-ttu-id="27ca6-109">調査のための適切なアラートセットの優先順位付けを行い、対処されていない脅威がないことを確認するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="27ca6-109">Prioritizing the right set of alerts for investigation while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="27ca6-110">アラートへの調査が手動で実行される場合、セキュリティ運用チームは脅威からのリスクでエンティティ (コンテンツ、デバイス、ユーザーなど) をハントして関連付けなければなりません。</span><span class="sxs-lookup"><span data-stu-id="27ca6-110">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (e.g. content, devices and users) at risk from threats.</span></span> <span data-ttu-id="27ca6-111">このようなタスクやワークフローは、非常に時間がかかり、複数のツールやシステムが関係しています。</span><span class="sxs-lookup"><span data-stu-id="27ca6-111">Such tasks and workflows are very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="27ca6-112">エアの場合、調査と応答は、セキュリティ対応のプレイブックを自動的にトリガーする主要なセキュリティおよび脅威管理警告に自動化されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-112">With AIR, investigation and response are automated into key security and threat management alerts that trigger your security response playbooks automatically.</span></span> 

<span data-ttu-id="27ca6-113">通知を表示するには、Office 365 Security & コンプライアンスセンターで、[**通知** > ] [**警告を表示**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-113">To view alerts, in the Office 365 Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span>

![調査にリンクされたアラート](media/air-alerts-page-details.png) 

<span data-ttu-id="27ca6-115">通知を選択して詳細を表示します。そこから、[**調査の表示**] リンクを使用して、対応する[調査](#investigation-graph)に移動します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-115">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](#investigation-graph).</span></span>

## <a name="security-playbooks"></a><span data-ttu-id="27ca6-116">セキュリティプレイブック</span><span class="sxs-lookup"><span data-stu-id="27ca6-116">Security playbooks</span></span>

<span data-ttu-id="27ca6-117">セキュリティプレイブックは、Microsoft の脅威保護の中核となるバックエンドポリシーです。</span><span class="sxs-lookup"><span data-stu-id="27ca6-117">Security playbooks are back-end policies that are at the heart of automation in Microsoft Threat Protection.</span></span> <span data-ttu-id="27ca6-118">AIR で提供されるセキュリティプレイブックは、一般的な実際のセキュリティシナリオに基づいています。</span><span class="sxs-lookup"><span data-stu-id="27ca6-118">The security playbooks provided in AIR are based on common real-world security scenarios.</span></span> <span data-ttu-id="27ca6-119">組織内でアラートがトリガーされると、セキュリティによるプレイブックが自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-119">A security playbook is launched automatically when an alert is triggered within your organization.</span></span> <span data-ttu-id="27ca6-120">アラートがトリガーされると、関連付けられたプレイブックが自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-120">Once the alert triggers, the associated playbook is run automatically.</span></span> <span data-ttu-id="27ca6-121">プレイブックは、すべての関連するメタデータ (電子メールメッセージ、ユーザー、件名、送信者などを含む) を調べて調査を実行し、その結果に基づいて、組織のセキュリティチームが管理および軽減するために実行できる一連のアクションを推奨します。脅威。</span><span class="sxs-lookup"><span data-stu-id="27ca6-121">The playbook runs an investigation, looking at all the associated metadata (including email messages, users, subjects, senders, etc.) and, based on its findings, recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="27ca6-122">空中で利用できるセキュリティプレイブックは、組織が現在直面している最も頻繁な脅威に取り組むように設計されています。</span><span class="sxs-lookup"><span data-stu-id="27ca6-122">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations face today.</span></span> <span data-ttu-id="27ca6-123">これらは、Microsoft の資産を保護する手助けをしているユーザーを含む、セキュリティ運用チームとインシデント対応チームからの入力に基づいています。</span><span class="sxs-lookup"><span data-stu-id="27ca6-123">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="27ca6-124">セキュリティプレイブックは段階的に展開されています。</span><span class="sxs-lookup"><span data-stu-id="27ca6-124">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="27ca6-125">航空の一環として、セキュリティプレイブックはフェーズに展開されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-125">As part of AIR, security playbooks are rolling out in phases</span></span>

- <span data-ttu-id="27ca6-126">**フェーズ 1 (2019 年4月)**: プレイブックには、セキュリティ管理者が確認および承認する推奨事項が含まれています。</span><span class="sxs-lookup"><span data-stu-id="27ca6-126">**Phase 1 (April 2019)**: Playbooks include recommendations that security administrators review and approve.</span></span> 

- <span data-ttu-id="27ca6-127">**フェーズ 2 (2019 年6月)**: セキュリティ管理者は、管理上の操作を行わなくても、セキュリティのプレイブックが自動的にアクションを実行できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-127">**Phase 2 (June 2019)**: Security administrators will have the option to allow security playbooks to take action automatically, without administrative interaction.</span></span>

<span data-ttu-id="27ca6-128">フェーズ1には、次のプレイブックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-128">Phase 1 will include the following playbooks:</span></span>
- <span data-ttu-id="27ca6-129">ユーザーによって報告されるフィッシングメッセージ</span><span class="sxs-lookup"><span data-stu-id="27ca6-129">User-reported phish message</span></span>
- <span data-ttu-id="27ca6-130">[URL] [verdict の変更] および [ATP Safe Links block override] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27ca6-130">URL click verdict change and ATP Safe Links block override</span></span>
- <span data-ttu-id="27ca6-131">マルウェアの ZAP</span><span class="sxs-lookup"><span data-stu-id="27ca6-131">Malware ZAP</span></span>
- <span data-ttu-id="27ca6-132">フィッシング ZAP</span><span class="sxs-lookup"><span data-stu-id="27ca6-132">Phish ZAP</span></span>
- <span data-ttu-id="27ca6-133">手動調査 (エクスプローラーを使用)</span><span class="sxs-lookup"><span data-stu-id="27ca6-133">Manual investigations (using Explorer)</span></span>

<span data-ttu-id="27ca6-134">フェーズ2では、さらにいくつかのプレイブックが計画されています。</span><span class="sxs-lookup"><span data-stu-id="27ca6-134">Several more playbooks are planned for Phase 2.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="27ca6-135">プレイブックには、調査と推奨事項が含まれます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-135">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="27ca6-136">各プレイブックには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-136">Each playbook includes:</span></span> 
- <span data-ttu-id="27ca6-137">ルート調査、</span><span class="sxs-lookup"><span data-stu-id="27ca6-137">a root investigation,</span></span> 
- <span data-ttu-id="27ca6-138">その他の潜在的な脅威を探し出すための手順</span><span class="sxs-lookup"><span data-stu-id="27ca6-138">steps to hunt down other potential threats, and</span></span> 
- <span data-ttu-id="27ca6-139">推奨される脅威の修復。</span><span class="sxs-lookup"><span data-stu-id="27ca6-139">recommended threat remediation.</span></span>

<span data-ttu-id="27ca6-140">各高度な手順には、脅威への深く、詳細、および完全な応答を提供するために実行される多くのサブステップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="27ca6-140">Each high-level step includes many sub-steps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-user-reported-phish-message"></a><span data-ttu-id="27ca6-141">例: ユーザーによって報告されるフィッシングメッセージ</span><span class="sxs-lookup"><span data-stu-id="27ca6-141">Example: User-reported phish message</span></span>

<span data-ttu-id="27ca6-142">組織内のユーザーが電子メールメッセージを送信し、 [outlook または outlook Web Access 用のレポートメッセージアドイン](enable-the-report-message-add-in.md)を使用して Microsoft に報告したとき。</span><span class="sxs-lookup"><span data-stu-id="27ca6-142">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web Access](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="27ca6-143">これにより、調査のプレイブックが自動的に起動するシステムベースの情報アラートがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-143">This triggers a system-based informational alert that automatically launches the investigation playbook.</span></span>

<span data-ttu-id="27ca6-144">ルート調査フェーズでは、電子メールのさまざまな側面を評価します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-144">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="27ca6-145">これらには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-145">These include:</span></span>
- <span data-ttu-id="27ca6-146">脅威の種類を決定すること。</span><span class="sxs-lookup"><span data-stu-id="27ca6-146">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="27ca6-147">送信者。</span><span class="sxs-lookup"><span data-stu-id="27ca6-147">Who sent it;</span></span>
- <span data-ttu-id="27ca6-148">電子メールの送信元 (インフラストラクチャの送信)</span><span class="sxs-lookup"><span data-stu-id="27ca6-148">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="27ca6-149">電子メールの他のインスタンスが配信またはブロックされたかどうか。</span><span class="sxs-lookup"><span data-stu-id="27ca6-149">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="27ca6-150">アナリストからの評価。</span><span class="sxs-lookup"><span data-stu-id="27ca6-150">An assessment from our analysts;</span></span>
- <span data-ttu-id="27ca6-151">電子メールが既知のキャンペーンと関連付けられているかどうか。</span><span class="sxs-lookup"><span data-stu-id="27ca6-151">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="27ca6-152">その他。</span><span class="sxs-lookup"><span data-stu-id="27ca6-152">and more.</span></span>

<span data-ttu-id="27ca6-153">ルート調査の完了後、プレイブックは推奨されるアクションの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-153">After the root investigation is complete, the playbook provides a list of recommended actions to take.</span></span>
  
<span data-ttu-id="27ca6-154">次に、いくつかの探しの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-154">Next, several hunting steps are executed:</span></span>

- <span data-ttu-id="27ca6-155">他の電子メールクラスター内の類似した電子メールメッセージが検索されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-155">Similar email messages in other email clusters are searched.</span></span>
- <span data-ttu-id="27ca6-156">シグナルは、 [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)などの他のプラットフォームと共有されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-156">The signal is shared with other platforms, such as [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="27ca6-157">疑わしい電子メールメッセージでユーザーがクリックしたかどうかについての判断が行われます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-157">A determination is made on whether any users have clicked through on the suspicious email message.</span></span>
- <span data-ttu-id="27ca6-158">Office 365 [EOP](eop/exchange-online-protection-eop.md)と[ATP](office-365-atp.md)の間でチェックが行われ、ユーザーから報告された他の類似メッセージがあるかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-158">A check is done across Office 365 [EOP](eop/exchange-online-protection-eop.md) and [ATP](office-365-atp.md) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="27ca6-159">ユーザーが侵害されていないかどうかを確認するためのチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-159">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="27ca6-160">このチェックは、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)と[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)の間の信号を活用して、関連するすべてのイベントまたはアラートを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-160">This check leverages signals across [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related events or alerts.</span></span> 

<span data-ttu-id="27ca6-161">お探しの段階では、さまざまなお探しのステップにリスクと脅威が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-161">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span>  

<span data-ttu-id="27ca6-162">修復は、プレイブックの最終段階です。</span><span class="sxs-lookup"><span data-stu-id="27ca6-162">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="27ca6-163">このフェーズでは、調査とお探しのフェーズに基づいて、修復手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-163">During this phase, remediation steps are taken, based on theinvestigation and hunting phases.</span></span>  

## <a name="getting-started"></a><span data-ttu-id="27ca6-164">はじめに</span><span class="sxs-lookup"><span data-stu-id="27ca6-164">Getting started</span></span>

<span data-ttu-id="27ca6-165">office 365 のグローバル管理者またはセキュリティ管理者として調査にアクセスするには、office 365 security &[https://protection.office.com](https://protection.office.com)コンプライアンスセンター () に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="27ca6-165">To access your investigations, as an Office 365 global administrator or security administrator, Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span> <span data-ttu-id="27ca6-166">次に、以下のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="27ca6-166">Then, do one of the following:</span></span>

- <span data-ttu-id="27ca6-167">左側のナビゲーションで、[**脅威管理** > の**調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-167">In the left navigation, go to **Threat management** > **Investigations**.</span></span>

    <span data-ttu-id="27ca6-168">または</span><span class="sxs-lookup"><span data-stu-id="27ca6-168">or</span></span>

- <span data-ttu-id="27ca6-169">脅威管理ダッシュボード (セキュリティ & コンプライアンスセンターで、[**脅威管理** > ]**ダッシュボード**) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="27ca6-169">Visit the Threat management dashboard (In the Security & Compliance Center, go to **Threat management** > **Dashboard**).</span></span>

![エアウィジェット](media/air-widgets.png)

<span data-ttu-id="27ca6-171">エアウィジェットは、[セキュリティダッシュボード](security-dashboard.md)の上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-171">Your AIR widgets will appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="27ca6-172">開始するウィジェットを選択します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-172">Select a widget to get started.</span></span>

### <a name="automated-investigations"></a><span data-ttu-id="27ca6-173">自動調査</span><span class="sxs-lookup"><span data-stu-id="27ca6-173">Automated investigations</span></span>

<span data-ttu-id="27ca6-174">[自動調査] ページには、組織の調査とその現在の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-174">The automated investigations page shows your organization's investigations and their current states.</span></span>

![エアのメイン調査ページ](media/air-maininvestigationpage.png) 
  
<span data-ttu-id="27ca6-176">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-176">You can:</span></span>
- <span data-ttu-id="27ca6-177">調査に直接ナビゲートします (**調査 ID**を選択します)。</span><span class="sxs-lookup"><span data-stu-id="27ca6-177">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="27ca6-178">フィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-178">Apply filters.</span></span> <span data-ttu-id="27ca6-179">調査の**種類**、**時間の範囲**、**状態**、またはこれらの組み合わせから選択します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-179">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="27ca6-180">データを CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="27ca6-180">Export the data to a CSV file.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="27ca6-181">調査グラフ</span><span class="sxs-lookup"><span data-stu-id="27ca6-181">Investigation graph</span></span>

<span data-ttu-id="27ca6-182">特定の調査を開くと、[調査中] グラフページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-182">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="27ca6-183">このページには、発生した警告の一部として自動的に調査された、電子メールメッセージ、ユーザー (およびそのアクティビティ)、およびデバイスのすべての異なるエンティティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-183">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![AIR 調査グラフページ](media/air-investigationgraphpage.png)

<span data-ttu-id="27ca6-185">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-185">You can:</span></span>
- <span data-ttu-id="27ca6-186">現在の調査の視覚的な概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-186">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="27ca6-187">調査のタイミングの概要を表示します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-187">View a summary of the investigation timings.</span></span>
- <span data-ttu-id="27ca6-188">ビジュアル化内のノードを選択して、そのノードの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-188">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="27ca6-189">上部にあるタブを選択すると、そのタブの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-189">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="27ca6-190">アラートの調査</span><span class="sxs-lookup"><span data-stu-id="27ca6-190">Alert investigation</span></span>

<span data-ttu-id="27ca6-191">調査の [**通知**] タブでは、調査に関連するすべてのアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-191">On the **Alerts** tab for an investigation, you can see all of the alerts relevant to the investigation.</span></span> <span data-ttu-id="27ca6-192">詳細には、調査に関連する、危険なサインイン、大量ダウンロードなどのアラートをトリガーした通知が含まれています。</span><span class="sxs-lookup"><span data-stu-id="27ca6-192">Details include the alert that triggered the investigation and other alerts, such as risky sign-in, mass download, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="27ca6-193">このページでは、セキュリティアナリストが個々の通知に関する追加情報を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-193">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![AIR alerts ページ](media/air-investigationalertspage.png)

<span data-ttu-id="27ca6-195">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-195">You can:</span></span>
- <span data-ttu-id="27ca6-196">現在のトリガー警告と関連付けられている警告の視覚的な概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-196">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="27ca6-197">リストから通知を選択して、完全な通知の詳細を表示するフライアウトページを開きます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-197">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="27ca6-198">電子メールの調査</span><span class="sxs-lookup"><span data-stu-id="27ca6-198">Email investigation</span></span>

<span data-ttu-id="27ca6-199">調査の [**電子メール**] タブでは、調査の一部として識別されたすべてのメールクラスターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-199">On the **Email** tab for an investigation, you can see all the email clusters identified as part of the investigation.</span></span> 

<span data-ttu-id="27ca6-200">ユーザーが組織内のユーザーによって送受信する、膨大な量の電子メールがあることを考えると、</span><span class="sxs-lookup"><span data-stu-id="27ca6-200">Given the sheer volume of email that users in an organization send and receive, the process of</span></span> 
- <span data-ttu-id="27ca6-201">メッセージヘッダー、本文、URL、および添付ファイルから類似した属性に基づいて電子メールメッセージをクラスタリングする。</span><span class="sxs-lookup"><span data-stu-id="27ca6-201">clustering email messages based on similar attributes from a message header, body, URL and attachment;</span></span> 
- <span data-ttu-id="27ca6-202">悪意のある電子メールを適切な電子メールから分離します。そして</span><span class="sxs-lookup"><span data-stu-id="27ca6-202">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="27ca6-203">悪意のある電子メールメッセージに対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="27ca6-203">taking action on malicious email messages</span></span> 

<span data-ttu-id="27ca6-204">数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="27ca6-204">can take many hours.</span></span> <span data-ttu-id="27ca6-205">AIR でこのプロセスが自動化され、組織のセキュリティチームの時間と労力を節約できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="27ca6-205">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="27ca6-206">例として、次のようなイメージを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="27ca6-206">As an example, consider the following image.</span></span> <span data-ttu-id="27ca6-207">3つの電子メールメッセージの最初のクラスターは、フィッシングであると見なされました。</span><span class="sxs-lookup"><span data-stu-id="27ca6-207">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="27ca6-208">同じ IP および件名を持つ類似メッセージの別のクラスターが検出され、一部の一部はフィッシングとして最初の検出時に識別されたため、悪意のあるものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-208">Another cluster of similar messages with the same IP and subject was found and is considered to be malicious, as some of them were identified as phish during initial detection.</span></span> 

![航空電子メールの調査ページ](media/air-investigationemailpage.png)

<span data-ttu-id="27ca6-210">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-210">You can:</span></span>
- <span data-ttu-id="27ca6-211">現在のクラスター化の結果と脅威の視覚的な概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-211">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="27ca6-212">クラスターエンティティまたは脅威リストをクリックして、完全なアラート詳細を示すフライアウトページを開きます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-212">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>

![フライアウトの詳細を含む電子メールの調査](media/air-investigationemailpageflyoutdetails.png)

### <a name="user-investigation"></a><span data-ttu-id="27ca6-214">ユーザー調査</span><span class="sxs-lookup"><span data-stu-id="27ca6-214">User investigation</span></span>

<span data-ttu-id="27ca6-215">[**ユーザー** ] タブには、調査の一部として特定されたすべてのユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-215">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> 

<span data-ttu-id="27ca6-216">たとえば、次の画像では、AIR は、作成された新しい受信トレイルールに基づいて、侵害と異常のインジケーターを識別しています。</span><span class="sxs-lookup"><span data-stu-id="27ca6-216">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="27ca6-217">調査の追加の詳細 (エビデンス) は、このタブ内の詳細なビューから利用できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-217">Additional details (evidence) of the investigation are available through detailed views within this tab.</span></span>

![AIR 調査ユーザーページ](media/air-investigationuserspage.png)

<span data-ttu-id="27ca6-219">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-219">You can:</span></span>
- <span data-ttu-id="27ca6-220">検出されたユーザーの結果とリスクの視覚的な概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-220">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="27ca6-221">通知の詳細をすべて表示するユーザーを選択して、フライアウトページを開きます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-221">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="27ca6-222">コンピューターの調査</span><span class="sxs-lookup"><span data-stu-id="27ca6-222">Machine investigation</span></span>

<span data-ttu-id="27ca6-223">[**コンピューター** ] タブに、調査の一部として特定されたすべてのマシンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-223">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![AIR 調査のコンピューターページ](media/air-investigationmachinepage.png)

<span data-ttu-id="27ca6-225">調査の一環として、空気は電子メールの脅威をデバイスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-225">As part of the investigation, AIR correlates email threats to devices.</span></span> <span data-ttu-id="27ca6-226">たとえば、調査では、 [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)に対してファイルハッシュを渡して調査します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-226">For example, an investigation passes a file hash across to [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) to investigate.</span></span> <span data-ttu-id="27ca6-227">これにより、ユーザーにとって関連するコンピューターの自動調査が可能になり、クラウドとデバイスの両方で脅威に対処できるようになります。</span><span class="sxs-lookup"><span data-stu-id="27ca6-227">This allows for automated investigation of relevant machines for your users and helps to ensure that threats are addressed both in the cloud and across your devices.</span></span> 

<span data-ttu-id="27ca6-228">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-228">You can:</span></span>
- <span data-ttu-id="27ca6-229">現在のコンピューターと脅威の視覚的な概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-229">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="27ca6-230">関連する[Windows Defender ATP 調査](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)に対するビューを開くコンピューターを選択します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-230">Select a machine to open a view that into the related [Windows Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection).</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="27ca6-231">エンティティの調査</span><span class="sxs-lookup"><span data-stu-id="27ca6-231">Entity investigation</span></span>

<span data-ttu-id="27ca6-232">[**エンティティ**] タブには、調査の一部として特定されたすべてのコンピューターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-232">On the **Entities** tab, you can see all the machines identified as part of the investigation.</span></span> 

<span data-ttu-id="27ca6-233">ここでは、調査されたエンティティを確認できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-233">Here, you can see the investigated entities.</span></span> <span data-ttu-id="27ca6-234">電子メールメッセージ、クラスター、IP アドレス、ユーザーなど、エンティティの種類の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-234">You can see details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="27ca6-235">また、分析されたエンティティの数と、それぞれに関連付けられている脅威も確認できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-235">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

![AIR 調査エンティティページ](media/air-investigationentitiespage.png)

<span data-ttu-id="27ca6-237">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-237">You can:</span></span>
- <span data-ttu-id="27ca6-238">検出されたエンティティと脅威の視覚的な概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-238">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="27ca6-239">エンティティを選択して、関連するエンティティの詳細を示すフライアウトページを開きます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-239">Select an entity to open a fly-out page that shows the related entity detail.</span></span>

![エア調査エンティティの詳細](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="27ca6-241">プレイブックログ</span><span class="sxs-lookup"><span data-stu-id="27ca6-241">Playbook log</span></span>

<span data-ttu-id="27ca6-242">[**ログ**] タブには、調査中に発生したすべてのプレイブックステップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-242">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="27ca6-243">このログは、Office 365 の脅威インテリジェンス機能によって実行されたすべての操作の完全なインベントリを AIR の一部としてキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="27ca6-243">The log captures a complete inventory of all actions completed by Office 365 Threat Intelligence capabilities as part of AIR.</span></span> <span data-ttu-id="27ca6-244">アクション自体、説明、開始から終了までの実際の期間など、実行されたすべてのステップを明確に表示できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-244">It provides a clear view of all the steps taken, including the Action itself, a description and the duration of the actual from start to finish.</span></span> 

![AIR 調査ログページ](media/air-investigationlogpage.png)

<span data-ttu-id="27ca6-246">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-246">You can:</span></span>
- <span data-ttu-id="27ca6-247">「」では、実行されるプレイブックの手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-247">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="27ca6-248">結果を CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="27ca6-248">Export the results to a CSV file.</span></span>
- <span data-ttu-id="27ca6-249">ビューをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-249">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="27ca6-250">推奨されるアクション</span><span class="sxs-lookup"><span data-stu-id="27ca6-250">Recommended actions</span></span>

<span data-ttu-id="27ca6-251">[ **Actions** ] タブには、調査の完了後に修復するために推奨されているすべてのプレイブックアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-251">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="27ca6-252">[アクション] 調査の最後に、Microsoft が推奨するすべての手順の完全な一覧をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="27ca6-252">Actions capture a complete list of all the steps Microsoft recommends you take at the end of a investigation.</span></span> <span data-ttu-id="27ca6-253">ここでは、1つ以上のアクションを選択することにより、修復のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-253">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="27ca6-254">[**承認**] をクリックすると、修復を開始できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-254">Clicking **Approve** will allow remediation to begin.</span></span> <span data-ttu-id="27ca6-255">(適切なアクセス許可が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="27ca6-255">(Appropriate permissions might be required.</span></span> <span data-ttu-id="27ca6-256">たとえば、セキュリティ閲覧者はアクションを表示するが、承認することはできません。)</span><span class="sxs-lookup"><span data-stu-id="27ca6-256">For example, a Security Reader can view actions but not approve them.)</span></span>  

![AIR 調査アクションページ](media/air-investigationactionspage.png)

<span data-ttu-id="27ca6-258">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-258">You can:</span></span>
- <span data-ttu-id="27ca6-259">プレイブックの概要を表示します。推奨されるアクション。</span><span class="sxs-lookup"><span data-stu-id="27ca6-259">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="27ca6-260">1つまたは複数のアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-260">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="27ca6-261">推奨されるアクションを承認します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-261">Approve recommended actions.</span></span> <span data-ttu-id="27ca6-262">(コメント付きですぐに開始されます)。</span><span class="sxs-lookup"><span data-stu-id="27ca6-262">(These are started immediately with comments.)</span></span>
- <span data-ttu-id="27ca6-263">結果を CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="27ca6-263">Export the results to a CSV file.</span></span>
- <span data-ttu-id="27ca6-264">ビューをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="27ca6-264">Filter the view.</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="27ca6-265">エアを入手する方法</span><span class="sxs-lookup"><span data-stu-id="27ca6-265">How to get AIR</span></span>

<span data-ttu-id="27ca6-266">現時点では、空気はプレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="27ca6-266">Currently, AIR is in preview.</span></span> <span data-ttu-id="27ca6-267">リリース時に、AIR は次のサブスクリプションに含まれます。</span><span class="sxs-lookup"><span data-stu-id="27ca6-267">When released, AIR will be included in the following subscriptions:</span></span>

- <span data-ttu-id="27ca6-268">Microsoft 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="27ca6-268">Microsoft 365 Enterprise E5</span></span>
- <span data-ttu-id="27ca6-269">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="27ca6-269">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="27ca6-270">Microsoft の脅威保護</span><span class="sxs-lookup"><span data-stu-id="27ca6-270">Microsoft Threat Protection</span></span>
- <span data-ttu-id="27ca6-271">Office 365 Advanced Threat Protection プラン2</span><span class="sxs-lookup"><span data-stu-id="27ca6-271">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="27ca6-272">機能の可用性の詳細については、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27ca6-272">To learn more about feature availability, visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>
