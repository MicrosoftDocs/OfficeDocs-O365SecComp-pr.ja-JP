---
title: 法的情報保留通知を作成する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 7d2746699a427fa3c7ad3afd7cf791c61cd55249
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213097"
---
# <a name="create-a-legal-hold-notice"></a><span data-ttu-id="0d7bc-102">法的情報保留通知を作成する</span><span class="sxs-lookup"><span data-stu-id="0d7bc-102">Create a legal hold notice</span></span>

<span data-ttu-id="0d7bc-p101">高度な電子情報開示 (プレビュー) 保管担当者コミュニケーションを使用すると、組織は保管担当者との通信に関するワークフローを管理できます。法務部門は、コミュニケーションツールを使用して、法的情報保留通知の送信、収集、追跡を系統的に行うことができます。また、柔軟な作成プロセスでは、チームは、保留通知ワークフローと、保管担当者に送信される通知の内容をカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p101">Using Advanced eDiscovery (Preview) custodian communications, organizations can manage their workflow around communicating with custodians. Through the Communications tool, legal teams can systematically send, collect, and track legal hold notifications. The flexible creation process also allows teams to customize the hold notification workflow and the content in the notices sent to custodians.</span></span> 

<span data-ttu-id="0d7bc-106">この記事では、保留通知ワークフローの手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-106">The article outlines the steps in the hold notification workflow.</span></span>

## <a name="step-1-specify-communication-details"></a><span data-ttu-id="0d7bc-107">手順 1: 通信の詳細を指定する</span><span class="sxs-lookup"><span data-stu-id="0d7bc-107">Step 1: Specify communication details</span></span>

<span data-ttu-id="0d7bc-108">最初の手順として、法的情報保留通知またはその他の保管担当者通信に関する適切な詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-108">The first step is to specify the appropriate details for legal hold notices or other custodian communications.</span></span> 

1. <span data-ttu-id="0d7bc-109">セキュリティ & コンプライアンスセンターで、[**電子情報開示 > Advanced eDiscovery (プレビュー)** ] に移動して、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-109">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery (Preview)** to display the list of cases in your organization.</span></span>
   
2. <span data-ttu-id="0d7bc-110">[**通信**] タブをクリックし、[**新しい通信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-110">Click the **Communications** tab, and then click **New communication**.</span></span>
   
3. <span data-ttu-id="0d7bc-111">[**名前の通信**] ページで、次の (必須) 通信の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-111">On the **Name communication** page, specify the following (required) communication details.</span></span>

    - <span data-ttu-id="0d7bc-112">**name**: これは通信の名前です。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-112">**Name**: This is the name for the communication.</span></span>
    
    - <span data-ttu-id="0d7bc-p102">**発行責任**者: ドロップダウンリストには、ケースメンバーの一覧が表示されます。保管担当者に送信される各通知は、指定された発行責任者の代理として送信されます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p102">**Issuing officer**: The dropdown list displays a list of a case members. Each notice sent to custodians will be sent on behalf of the specified issuing officer.</span></span>

4. <span data-ttu-id="0d7bc-115">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-115">Click **Next**.</span></span>

## <a name="step-2-define-the-portal-content"></a><span data-ttu-id="0d7bc-116">手順 2: ポータルコンテンツを定義する</span><span class="sxs-lookup"><span data-stu-id="0d7bc-116">Step 2: Define the portal content</span></span>

<span data-ttu-id="0d7bc-p103">次に、保留通知のコンテンツを作成して追加することができます。[**通信の作成**] ウィザードの [**ポータルコンテンツの定義**] ページで、保留通知の内容を指定します。このコンテンツは、発行、再発行、アラーム、エスカレーション通知に自動的に追加されます。さらに、このコンテンツは保管担当者のコンプライアンスポータルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p103">Next, you can create and add the content of the hold notice. On the **Define portal content** page in the **Create communication** wizard, specify the contents of the hold notice. This content will be automatically appended to the Issuance, Re-Issue, Reminder, and Escalation notices. Additionally, this content will appear in the custodian's Compliance Portal.</span></span> 

<span data-ttu-id="0d7bc-121">ポータルコンテンツを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-121">To create the portal content:</span></span>

1. <span data-ttu-id="0d7bc-122">ポータルコンテンツのテキストボックスに、保留通知を入力します (または、別のドキュメントから切り取り、または貼りを行います)。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-122">Type (or cut and paster from another document) your hold notice in the textbox for the portal content.</span></span> 

2. <span data-ttu-id="0d7bc-123">通知に差し込み変数を挿入して、通知をカスタマイズし、保管担当者コンプライアンスポータルを共有します。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-123">Insert merge variables into your notice to customize the notice and share the Custodian Compliance Portal.</span></span>

3. <span data-ttu-id="0d7bc-124">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-124">Click **Next**.</span></span>

  >[!Tip]
  ><span data-ttu-id="0d7bc-125">ポータルコンテンツのコンテンツと形式をカスタマイズする方法の詳細については、「 [Use the Communications Editor](using-communications-editor.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-125">To learn more about how to can customize the content and format of the portal content, see [Use the Communications Editor](using-communications-editor.md).</span></span>

## <a name="step-3-set-the-required-notifications"></a><span data-ttu-id="0d7bc-126">手順 3: 必要な通知を設定する</span><span class="sxs-lookup"><span data-stu-id="0d7bc-126">Step 3: Set the required notifications</span></span>

<span data-ttu-id="0d7bc-p104">保留通知の内容を定義した後、通知プロセスを送信および管理するためのワークフローを設定できます。通知は、保管担当者を使用して通知とフォローアップのために送信される電子メールメッセージです。通信に追加されたすべての保管担当者は同じ通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p104">After you've defined the contents of the hold notice, you can set up the workflows around sending and managing the notification process. Notifications are email messages that are sent to notify and follow-up with custodians. Every custodian added to the communication will receive the same notification.</span></span> 

<span data-ttu-id="0d7bc-130">保留通知を設定して送信するには、発行、再発行、およびリリース通知を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-130">To set up and send a hold notice, you must include Issuance, Re-Issuance, and Release notifications.</span></span>

### <a name="issuance-notification"></a><span data-ttu-id="0d7bc-131">発行通知</span><span class="sxs-lookup"><span data-stu-id="0d7bc-131">Issuance notification</span></span> 

<span data-ttu-id="0d7bc-p105">通信が作成されると、指定された発行責任者によって**発行通知**が開始されます。発行通知は、保管担当者に送信される最初の通信で、保持義務について通知します。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p105">After the communication is created, the **Issuance Notification** is initiated by the specified Issuing Officer. The Issuance notification is the first communication sent to the custodian to inform them about their preservation obligations.</span></span> 

<span data-ttu-id="0d7bc-134">発行通知を作成するには:</span><span class="sxs-lookup"><span data-stu-id="0d7bc-134">To create an issuance notification:</span></span>

1. <span data-ttu-id="0d7bc-135">[**発行**] タイルで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-135">In the **Issuance** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="0d7bc-p106">必要に応じて、[ **Cc** ] フィールドと [ **Bcc** ] フィールドにケースメンバーまたはスタッフを追加します。これらのフィールドに複数のユーザーを追加するには、電子メールアドレスをセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p106">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields. To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>
   
3. <span data-ttu-id="0d7bc-138">通知の**件名**を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-138">Specify the **Subject** for the notice (required).</span></span>
   
4. <span data-ttu-id="0d7bc-p107">保管担当者に提供するコンテンツまたは追加の手順を指定します (必須)。手順2で定義したポータルコンテンツが、発行通知の最後に追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p107">Specify the contents or additional instructions that you would like to provide to the custodian (required). Note that the portal content you defined in Step 2 is added to the end of the issuance notice.</span></span> 
   
5. <span data-ttu-id="0d7bc-141">**[保存]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="0d7bc-141">Click **Save**</span></span> 

### <a name="re-issuance-notification"></a><span data-ttu-id="0d7bc-142">再発行の通知</span><span class="sxs-lookup"><span data-stu-id="0d7bc-142">Re-Issuance notification</span></span> 

<span data-ttu-id="0d7bc-p108">ケースが進行するにつれて、保管担当者は、以前に指示されていたのとは別のデータを保持する必要がある場合があります。保留通知の内容を更新した後、再発行の通知は、保存義務に対する変更について保管担当者に通知します。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p108">As the case progresses, custodians may be required to preserve additional or less data than was previously instructed. After you update the contents of the hold notice, the re-issuance notification alerts the  custodians about the changes to their preservation obligations.</span></span>

<span data-ttu-id="0d7bc-145">再発行の通知を作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-145">To create a re-issuance notification:</span></span> 

1. <span data-ttu-id="0d7bc-146">[**再発行**] タイルで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-146">In the **Reissue** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="0d7bc-p109">必要に応じて、[ **Cc** ] フィールドと [ **Bcc** ] フィールドにケースメンバーまたはスタッフを追加します。これらのフィールドに複数のユーザーを追加するには、電子メールアドレスをセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p109">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields. To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>
   
3. <span data-ttu-id="0d7bc-149">通知の**件名**を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-149">Specify the **Subject** for the notice (required).</span></span>
   
4. <span data-ttu-id="0d7bc-p110">保管担当者に提供するコンテンツまたは追加の手順を指定します (必須)。手順2で定義したポータルコンテンツが再発行通知の最後に追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p110">Specify the contents or additional instructions that you would like to provide to the custodian (required). Note that the portal content you defined in Step 2 is added to the end of the re-issuance notice.</span></span>
   
5. <span data-ttu-id="0d7bc-152">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-152">Click **Save**.</span></span>

>[!Note]
><span data-ttu-id="0d7bc-p111">保留通知が変更されると、その通知に割り当てられたすべての保管担当者に対して、再発行の通知が自動的に送信されます。通知が送信されると、保管担当者は保留通知を再認識するように求められます。通知またはエスカレーションワークフローを設定している場合は、それらも再起動されます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p111">If a hold notification is modified, the re-issuance notification will be automatically sent to all custodians assigned to the notice. After the notification is sent, custodians will be asked to re-acknowledge their hold notice. If you have set up any reminder or escalation workflows, these will also re-start.</span></span> 

### <a name="release-notification"></a><span data-ttu-id="0d7bc-156">リリース通知</span><span class="sxs-lookup"><span data-stu-id="0d7bc-156">Release notification</span></span>

<span data-ttu-id="0d7bc-p112">問題が解決した場合や、保管担当者がコンテンツを保持する必要がなくなった場合は、ケースから保管担当者をリリースできます。保管担当者に以前に保留通知が発行されていた場合は、リリース通知を使用して、その義務から解放されたことを保管担当者に通知できます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p112">After a matter is resolved or if a custodian is no longer subject to preserve content, you can release the custodian from a case. If the custodian was previously issued a hold notice, the release notification can be used to alert custodians that they have been released from their obligation.</span></span>

<span data-ttu-id="0d7bc-159">リリース通知を作成するには:</span><span class="sxs-lookup"><span data-stu-id="0d7bc-159">To create a release notification:</span></span> 

1. <span data-ttu-id="0d7bc-160">[**リリース**タイル] で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-160">In the **Release** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="0d7bc-p113">必要に応じて、[ **Cc** ] フィールドと [ **Bcc** ] フィールドにケースメンバーまたはスタッフを追加します。これらのフィールドに複数のユーザーを追加するには、電子メールアドレスをセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p113">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields. To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>
   
3. <span data-ttu-id="0d7bc-163">通知の**件名**を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-163">Specify the **Subject** for the notice (required).</span></span>
   
4. <span data-ttu-id="0d7bc-164">保管担当者に提供するコンテンツまたは追加の手順を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-164">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span>
   
5. <span data-ttu-id="0d7bc-165">[**保存**] をクリックして、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-165">Click **Save** and go to the next step.</span></span> 

## <a name="optional-step-4-set-the-optional-notifications"></a><span data-ttu-id="0d7bc-166">オプション手順 4: オプションの通知を設定する</span><span class="sxs-lookup"><span data-stu-id="0d7bc-166">(Optional) Step 4: Set the optional notifications</span></span>

<span data-ttu-id="0d7bc-167">必要に応じて、自動化された通知およびエスカレーション通知を作成およびスケジュールすることによって、応答のない保管担当者をフォローアップするワークフローを簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-167">Optionally, you can simplify the workflow for following up with unresponsive custodians by creating and scheduling automated reminder and escalation notifications.</span></span>

### <a name="reminders"></a><span data-ttu-id="0d7bc-168">事前通知</span><span class="sxs-lookup"><span data-stu-id="0d7bc-168">Reminders</span></span>

<span data-ttu-id="0d7bc-169">保留通知を送信した後は、通知ワークフローを定義することによって、応答のない保管担当者でフォローアップできます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-169">After you have sent a hold notification, you can follow-up with unresponsive custodians by defining a reminder workflow.</span></span> 

<span data-ttu-id="0d7bc-170">アラームをスケジュールするには</span><span class="sxs-lookup"><span data-stu-id="0d7bc-170">To schedule reminders:</span></span>

1. <span data-ttu-id="0d7bc-171">[**通知**] タイルで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-171">In the **Reminder** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="0d7bc-172">**ステータス**切り替え (必須) をオンにして、**アラーム**ワークフローを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-172">Enable the **Reminder** workflow by turning on the **Status** toggle (required).</span></span>
   
3. <span data-ttu-id="0d7bc-p114">通知の**間隔 (日数)** を指定します (必須)。これは、最初のアラーム通知とフォローアップリマインダー通知を送信するまでの日数です。たとえば、通知の間隔を7日に設定した場合、最初の通知は、保留通知が最初に発行されてから7日後に送信されます。以降のすべてのアラームも7日ごとに送信されます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p114">Specify the **Reminder interval (in days)** (required). This is the number of days to wait before sending the first and follow-up reminder notifications. For example, if you set the reminder interval to 7 days, then the first reminder would be sent 7 days after the hold notification was initially issued. All subsequent reminders would also be sent every 7 days.</span></span>
   
4. <span data-ttu-id="0d7bc-p115">**アラームの数**を指定します (必須)。このフィールドには、応答のない保管担当者に送信される通知の数を指定します。たとえば、アラームの数を3に設定すると、保管担当者は最大3つのリマインダーを受け取ります。保管担当者が保留通知を確認すると、そのユーザーに通知が送信されなくなります。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p115">Specify the **Number of reminders** (required). This field specifies how many reminders to send to un-responsive custodians. For example, if you set the number of reminders to 3, then a custodian would receive a maximum of 3 reminders. After a custodian acknowledges the hold notification, reminders will no longer be sent to that user.</span></span>
   
5. <span data-ttu-id="0d7bc-181">通知の**件名**を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-181">Specify the **Subject** for the notice (required).</span></span> 
   
6. <span data-ttu-id="0d7bc-p116">保管担当者に提供するコンテンツまたは追加の手順を指定します (必須)。手順2で定義したポータルコンテンツがアラーム通知の最後に追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p116">Specify the contents or additional instructions that you would like to provide to the custodian (required). Note that the portal content you defined in Step 2 is added to the end of the reminder notice.</span></span>
   
7. <span data-ttu-id="0d7bc-184">[**保存**] をクリックして、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-184">Click **Save** and go the the next step.</span></span>

### <a name="escalations"></a><span data-ttu-id="0d7bc-185">報告</span><span class="sxs-lookup"><span data-stu-id="0d7bc-185">Escalations</span></span> 

<span data-ttu-id="0d7bc-p117">状況によっては、応答のない保管担当者でフォローアップするための別の方法が必要になることがあります。保管担当者が、指定された数のアラームを受信した後に保留通知を承認しない場合、法務チームは保管担当者とその上司にエスカレーション通知を自動的に送信するワークフローを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p117">In some situations, you may need additional ways to follow-up with unresponsive custodians. If a custodian doesn't acknowledge a hold notification after receiving the specified number of reminders, the legal team can specify a workflow to automatically send an escalation notice to the custodian and their manager.</span></span>

<span data-ttu-id="0d7bc-188">エスカレーションをスケジュールするには</span><span class="sxs-lookup"><span data-stu-id="0d7bc-188">To schedule escalations:</span></span>

1. <span data-ttu-id="0d7bc-189">**エスカレーション**タイルで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-189">In the **Escalation** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="0d7bc-190">**状態**の切り替えをオンにして、**エスカレーション**ワークフローを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-190">Enable the **Escalation** workflow by turning on the **Status** toggle.</span></span>
   
3. <span data-ttu-id="0d7bc-191">エスカレーションの**間隔 (日数)** を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-191">Specify the **Escalation interval (in days)** (required).</span></span> 
   
4. <span data-ttu-id="0d7bc-p118">**エスカレーションの数**を指定します (必須)。このフィールドには、応答のない保管担当者に送信するエスカレーションの数を指定します。たとえば、エスカレーション数を3に設定すると、エスカレーション通知が保管担当者に送信され、そのマネージャーは最大3回送信されます。保管担当者が保留通知を確認すると、エスカレーションは送信されなくなります。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p118">Specify the **Number of escalations** (required). This field specifies how many escalations to send to un-responsive custodians. For example, if you set the number of escalations to 3, then an escalation notice would be sent to the custodian and their manager a maximum of 3 times. After a custodian acknowledges the hold notification, escalations will no longer be sent.</span></span> 
   
5. <span data-ttu-id="0d7bc-196">通知の**件名**を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-196">Specify the **Subject** for the notice (required).</span></span> 
   
6. <span data-ttu-id="0d7bc-p119">保管担当者に提供するコンテンツまたは追加の手順を指定します (必須)。手順2で定義したポータルコンテンツがエスカレーション通知の末尾に追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-p119">Specify the contents or additional instructions that you would like to provide to the custodian (required). Note that the portal content you defined in Step 2 is added to the end of the escalation notice.</span></span>
   
7. <span data-ttu-id="0d7bc-199">[**保存**] をクリックして、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-199">Click **Save** and go the the next step.</span></span>
   
## <a name="step-5-assign-custodians"></a><span data-ttu-id="0d7bc-200">手順 5: 保管担当者を割り当てる</span><span class="sxs-lookup"><span data-stu-id="0d7bc-200">Step 5: Assign custodians</span></span> 

<span data-ttu-id="0d7bc-201">通知の内容を完了したら、通知を送信する保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-201">After you have finalized the content for notifications, select the custodians to send the notifications to.</span></span> 

<span data-ttu-id="0d7bc-202">保管担当者を追加するには</span><span class="sxs-lookup"><span data-stu-id="0d7bc-202">To add custodians:</span></span>

1. <span data-ttu-id="0d7bc-203">名前の横にあるチェックボックスをオンにして、保管担当者を通信に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-203">Assign custodians to the communication by clicking the checkbox next to their name.</span></span>

    <span data-ttu-id="0d7bc-204">通信が作成されると、選択した保管担当者に通知ワークフローが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-204">After the communication is created, the notification workflow will automatically apply to the selected custodians.</span></span>
   
2. <span data-ttu-id="0d7bc-205">[**次**へ] をクリックして、通信設定と詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-205">Click **Next** to review the communication settings and details.</span></span>
 
>[!NOTE]
><span data-ttu-id="0d7bc-206">保管担当者は、ケースに追加されていて、ケース内で別の通知が送信されていない場合にのみ追加できます。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-206">You can only add custodians who have been added to the case and haven't been sent another notification within the case.</span></span>

## <a name="step-6-review-settings"></a><span data-ttu-id="0d7bc-207">手順 6: 設定を確認する</span><span class="sxs-lookup"><span data-stu-id="0d7bc-207">Step 6: Review settings</span></span>

<span data-ttu-id="0d7bc-208">設定を確認し、[**送信**] をクリックして通信を完了すると、システムは、発行通知を送信することによって、自動的に通信ワークフローを開始します。</span><span class="sxs-lookup"><span data-stu-id="0d7bc-208">After you review the settings and click **Send** to complete the communication, the system will automatically start the communication workflow by sending the issuance notice.</span></span>