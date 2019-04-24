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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: acfa0c635b361426542e91a55c8d75c315bfb831
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242805"
---
# <a name="create-a-legal-hold-notice"></a><span data-ttu-id="8c92f-102">法的情報保留通知を作成する</span><span class="sxs-lookup"><span data-stu-id="8c92f-102">Create a legal hold notice</span></span>

<span data-ttu-id="8c92f-103">高度な電子情報開示 (プレビュー) 保管担当者コミュニケーションを使用すると、組織は保管担当者との通信に関するワークフローを管理できます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-103">Using Advanced eDiscovery (Preview) custodian communications, organizations can manage their workflow around communicating with custodians.</span></span> <span data-ttu-id="8c92f-104">法務部門は、コミュニケーションツールを使用して、法的情報保留通知の送信、収集、追跡を系統的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-104">Through the Communications tool, legal teams can systematically send, collect, and track legal hold notifications.</span></span> <span data-ttu-id="8c92f-105">また、柔軟な作成プロセスでは、チームは、保留通知ワークフローと、保管担当者に送信される通知の内容をカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-105">The flexible creation process also allows teams to customize the hold notification workflow and the content in the notices sent to custodians.</span></span> 

![通信ページ](../media/CommunicationPage.PNG)

<span data-ttu-id="8c92f-107">この記事では、保留通知ワークフローの手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-107">The article outlines the steps in the hold notification workflow.</span></span>

## <a name="step-1-specify-communication-details"></a><span data-ttu-id="8c92f-108">手順 1: 通信の詳細を指定する</span><span class="sxs-lookup"><span data-stu-id="8c92f-108">Step 1: Specify communication details</span></span>

<span data-ttu-id="8c92f-109">最初の手順として、法的情報保留通知またはその他の保管担当者通信に関する適切な詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-109">The first step is to specify the appropriate details for legal hold notices or other custodian communications.</span></span> 

![名前の通信ページ](../media/NameCommunication.PNG)

1. <span data-ttu-id="8c92f-111">セキュリティ & コンプライアンスセンターで、[**電子情報開示 > Advanced eDiscovery (プレビュー)** ] に移動して、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-111">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery (Preview)** to display the list of cases in your organization.</span></span>
   
2. <span data-ttu-id="8c92f-112">[**通信**] タブをクリックし、[**新しい通信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c92f-112">Click the **Communications** tab, and then click **New communication**.</span></span>
   
3. <span data-ttu-id="8c92f-113">[**名前の通信**] ページで、次の (必須) 通信の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-113">On the **Name communication** page, specify the following (required) communication details.</span></span>

    - <span data-ttu-id="8c92f-114">**name**: これは通信の名前です。</span><span class="sxs-lookup"><span data-stu-id="8c92f-114">**Name**: This is the name for the communication.</span></span>
    
    - <span data-ttu-id="8c92f-115">**発行責任**者: ドロップダウンリストには、ケースメンバーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-115">**Issuing officer**: The dropdown list displays a list of a case members.</span></span> <span data-ttu-id="8c92f-116">保管担当者に送信される各通知は、指定された発行責任者の代理として送信されます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-116">Each notice sent to custodians will be sent on behalf of the specified issuing officer.</span></span>

4. <span data-ttu-id="8c92f-117">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c92f-117">Click **Next**.</span></span>

## <a name="step-2-define-the-portal-content"></a><span data-ttu-id="8c92f-118">手順 2: ポータルコンテンツを定義する</span><span class="sxs-lookup"><span data-stu-id="8c92f-118">Step 2: Define the portal content</span></span>

<span data-ttu-id="8c92f-119">次に、保留通知のコンテンツを作成して追加することができます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-119">Next, you can create and add the content of the hold notice.</span></span> <span data-ttu-id="8c92f-120">[**通信の作成**] ウィザードの [**ポータルコンテンツの定義**] ページで、保留通知の内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-120">On the **Define portal content** page in the **Create communication** wizard, specify the contents of the hold notice.</span></span> <span data-ttu-id="8c92f-121">このコンテンツは、発行、再発行、アラーム、エスカレーション通知に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-121">This content will be automatically appended to the Issuance, Re-Issue, Reminder, and Escalation notices.</span></span> <span data-ttu-id="8c92f-122">さらに、このコンテンツは保管担当者のコンプライアンスポータルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-122">Additionally, this content will appear in the custodian's Compliance Portal.</span></span> 

![ポータルコンテンツページ](../media/PortalContent.PNG)

<span data-ttu-id="8c92f-124">ポータルコンテンツを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8c92f-124">To create the portal content:</span></span>

1. <span data-ttu-id="8c92f-125">ポータルコンテンツのテキストボックスに、保留通知を入力します (または、別のドキュメントに切り取り、貼り付けを行います)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-125">Type (or cut and paste from another document) your hold notice in the textbox for the portal content.</span></span> 

2. <span data-ttu-id="8c92f-126">通知に差し込み変数を挿入して、通知をカスタマイズし、保管担当者コンプライアンスポータルを共有します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-126">Insert merge variables into your notice to customize the notice and share the Custodian Compliance Portal.</span></span>

3. <span data-ttu-id="8c92f-127">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c92f-127">Click **Next**.</span></span>

  >[!Tip]
  ><span data-ttu-id="8c92f-128">ポータルコンテンツのコンテンツと形式をカスタマイズする方法の詳細については、「 [Use the Communications Editor](using-communications-editor.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c92f-128">To learn more about how to can customize the content and format of the portal content, see [Use the Communications Editor](using-communications-editor.md).</span></span>

## <a name="step-3-set-the-required-notifications"></a><span data-ttu-id="8c92f-129">手順 3: 必要な通知を設定する</span><span class="sxs-lookup"><span data-stu-id="8c92f-129">Step 3: Set the required notifications</span></span>

<span data-ttu-id="8c92f-130">保留通知の内容を定義した後、通知プロセスを送信および管理するためのワークフローを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-130">After you've defined the contents of the hold notice, you can set up the workflows around sending and managing the notification process.</span></span> <span data-ttu-id="8c92f-131">通知は、保管担当者を使用して通知とフォローアップのために送信される電子メールメッセージです。</span><span class="sxs-lookup"><span data-stu-id="8c92f-131">Notifications are email messages that are sent to notify and follow-up with custodians.</span></span> <span data-ttu-id="8c92f-132">通信に追加されたすべての保管担当者は同じ通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8c92f-132">Every custodian added to the communication will receive the same notification.</span></span> 

<span data-ttu-id="8c92f-133">保留通知を設定して送信するには、発行、再発行、およびリリース通知を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c92f-133">To set up and send a hold notice, you must include Issuance, Re-Issuance, and Release notifications.</span></span>

### <a name="issuance-notification"></a><span data-ttu-id="8c92f-134">発行通知</span><span class="sxs-lookup"><span data-stu-id="8c92f-134">Issuance notification</span></span> 

<span data-ttu-id="8c92f-135">通信が作成されると、指定された発行責任者によって**発行通知**が開始されます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-135">After the communication is created, the **Issuance Notification** is initiated by the specified Issuing Officer.</span></span> <span data-ttu-id="8c92f-136">発行通知は、保管担当者に送信される最初の通信で、保持義務について通知します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-136">The Issuance notification is the first communication sent to the custodian to inform them about their preservation obligations.</span></span> 

<span data-ttu-id="8c92f-137">発行通知を作成するには:</span><span class="sxs-lookup"><span data-stu-id="8c92f-137">To create an issuance notification:</span></span>

1. <span data-ttu-id="8c92f-138">[**発行**] タイルで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c92f-138">In the **Issuance** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="8c92f-139">必要に応じて、[ **Cc** ] フィールドと [ **Bcc** ] フィールドにケースメンバーまたはスタッフを追加します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-139">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="8c92f-140">これらのフィールドに複数のユーザーを追加するには、電子メールアドレスをセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="8c92f-140">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>
   
3. <span data-ttu-id="8c92f-141">通知の**件名**を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-141">Specify the **Subject** for the notice (required).</span></span>
   
4. <span data-ttu-id="8c92f-142">保管担当者に提供するコンテンツまたは追加の手順を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-142">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="8c92f-143">手順2で定義したポータルコンテンツが、発行通知の最後に追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8c92f-143">Note that the portal content you defined in Step 2 is added to the end of the issuance notice.</span></span> 
   
5. <span data-ttu-id="8c92f-144">**[保存]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="8c92f-144">Click **Save**</span></span> 

### <a name="re-issuance-notification"></a><span data-ttu-id="8c92f-145">再発行の通知</span><span class="sxs-lookup"><span data-stu-id="8c92f-145">Re-Issuance notification</span></span> 

<span data-ttu-id="8c92f-146">ケースが進行するにつれて、保管担当者は、以前に指示されていたのとは別のデータを保持する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8c92f-146">As the case progresses, custodians may be required to preserve additional or less data than was previously instructed.</span></span> <span data-ttu-id="8c92f-147">保留通知の内容を更新した後、再発行の通知は、保存義務に対する変更について保管担当者に通知します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-147">After you update the contents of the hold notice, the re-issuance notification alerts the  custodians about the changes to their preservation obligations.</span></span>

<span data-ttu-id="8c92f-148">再発行の通知を作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8c92f-148">To create a re-issuance notification:</span></span> 

1. <span data-ttu-id="8c92f-149">[**再発行**] タイルで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c92f-149">In the **Reissue** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="8c92f-150">必要に応じて、[ **Cc** ] フィールドと [ **Bcc** ] フィールドにケースメンバーまたはスタッフを追加します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-150">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="8c92f-151">これらのフィールドに複数のユーザーを追加するには、電子メールアドレスをセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="8c92f-151">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>
   
3. <span data-ttu-id="8c92f-152">通知の**件名**を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-152">Specify the **Subject** for the notice (required).</span></span>
   
4. <span data-ttu-id="8c92f-153">保管担当者に提供するコンテンツまたは追加の手順を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-153">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="8c92f-154">手順2で定義したポータルコンテンツが再発行通知の最後に追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8c92f-154">Note that the portal content you defined in Step 2 is added to the end of the re-issuance notice.</span></span>
   
5. <span data-ttu-id="8c92f-155">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c92f-155">Click **Save**.</span></span>

>[!Note]
><span data-ttu-id="8c92f-156">保留通知が変更されると、その通知に割り当てられたすべての保管担当者に対して、再発行の通知が自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-156">If a hold notification is modified, the re-issuance notification will be automatically sent to all custodians assigned to the notice.</span></span> <span data-ttu-id="8c92f-157">通知が送信されると、保管担当者は保留通知を再認識するように求められます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-157">After the notification is sent, custodians will be asked to re-acknowledge their hold notice.</span></span> <span data-ttu-id="8c92f-158">通知またはエスカレーションワークフローを設定している場合は、それらも再起動されます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-158">If you have set up any reminder or escalation workflows, these will also re-start.</span></span> 

### <a name="release-notification"></a><span data-ttu-id="8c92f-159">リリース通知</span><span class="sxs-lookup"><span data-stu-id="8c92f-159">Release notification</span></span>

<span data-ttu-id="8c92f-160">問題が解決した場合や、保管担当者がコンテンツを保持する必要がなくなった場合は、ケースから保管担当者をリリースできます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-160">After a matter is resolved or if a custodian is no longer subject to preserve content, you can release the custodian from a case.</span></span> <span data-ttu-id="8c92f-161">保管担当者に以前に保留通知が発行されていた場合は、リリース通知を使用して、その義務から解放されたことを保管担当者に通知できます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-161">If the custodian was previously issued a hold notice, the release notification can be used to alert custodians that they have been released from their obligation.</span></span>

<span data-ttu-id="8c92f-162">リリース通知を作成するには:</span><span class="sxs-lookup"><span data-stu-id="8c92f-162">To create a release notification:</span></span> 

1. <span data-ttu-id="8c92f-163">[**リリース**タイル] で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c92f-163">In the **Release** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="8c92f-164">必要に応じて、[ **Cc** ] フィールドと [ **Bcc** ] フィールドにケースメンバーまたはスタッフを追加します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-164">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="8c92f-165">これらのフィールドに複数のユーザーを追加するには、電子メールアドレスをセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="8c92f-165">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>
   
3. <span data-ttu-id="8c92f-166">通知の**件名**を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-166">Specify the **Subject** for the notice (required).</span></span>
   
4. <span data-ttu-id="8c92f-167">保管担当者に提供するコンテンツまたは追加の手順を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-167">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span>
   
5. <span data-ttu-id="8c92f-168">[**保存**] をクリックして、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-168">Click **Save** and go to the next step.</span></span> 

## <a name="optional-step-4-set-the-optional-notifications"></a><span data-ttu-id="8c92f-169">オプション手順 4: オプションの通知を設定する</span><span class="sxs-lookup"><span data-stu-id="8c92f-169">(Optional) Step 4: Set the optional notifications</span></span>

<span data-ttu-id="8c92f-170">必要に応じて、自動化された通知およびエスカレーション通知を作成およびスケジュールすることによって、応答のない保管担当者をフォローアップするワークフローを簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-170">Optionally, you can simplify the workflow for following up with unresponsive custodians by creating and scheduling automated reminder and escalation notifications.</span></span>

![アラーム/エスカレーションページ](../media/ReminderEscalations.PNG)

### <a name="reminders"></a><span data-ttu-id="8c92f-172">Reminders</span><span class="sxs-lookup"><span data-stu-id="8c92f-172">Reminders</span></span>

<span data-ttu-id="8c92f-173">保留通知を送信した後は、通知ワークフローを定義することによって、応答のない保管担当者でフォローアップできます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-173">After you have sent a hold notification, you can follow-up with unresponsive custodians by defining a reminder workflow.</span></span> 

<span data-ttu-id="8c92f-174">アラームをスケジュールするには</span><span class="sxs-lookup"><span data-stu-id="8c92f-174">To schedule reminders:</span></span>

1. <span data-ttu-id="8c92f-175">[**通知**] タイルで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c92f-175">In the **Reminder** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="8c92f-176">**ステータス**切り替え (必須) をオンにして、**アラーム**ワークフローを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8c92f-176">Enable the **Reminder** workflow by turning on the **Status** toggle (required).</span></span>
   
3. <span data-ttu-id="8c92f-177">通知の**間隔 (日数)** を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-177">Specify the **Reminder interval (in days)** (required).</span></span> <span data-ttu-id="8c92f-178">これは、最初のアラーム通知とフォローアップリマインダー通知を送信するまでの日数です。</span><span class="sxs-lookup"><span data-stu-id="8c92f-178">This is the number of days to wait before sending the first and follow-up reminder notifications.</span></span> <span data-ttu-id="8c92f-179">たとえば、通知の間隔を7日に設定した場合、最初の通知は、保留通知が最初に発行されてから7日後に送信されます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-179">For example, if you set the reminder interval to 7 days, then the first reminder would be sent 7 days after the hold notification was initially issued.</span></span> <span data-ttu-id="8c92f-180">以降のすべてのアラームも7日ごとに送信されます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-180">All subsequent reminders would also be sent every 7 days.</span></span>
   
4. <span data-ttu-id="8c92f-181">**アラームの数**を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-181">Specify the **Number of reminders** (required).</span></span> <span data-ttu-id="8c92f-182">このフィールドには、応答のない保管担当者に送信される通知の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-182">This field specifies how many reminders to send to un-responsive custodians.</span></span> <span data-ttu-id="8c92f-183">たとえば、アラームの数を3に設定すると、保管担当者は最大3つのリマインダーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8c92f-183">For example, if you set the number of reminders to 3, then a custodian would receive a maximum of 3 reminders.</span></span> <span data-ttu-id="8c92f-184">保管担当者が保留通知を確認すると、そのユーザーに通知が送信されなくなります。</span><span class="sxs-lookup"><span data-stu-id="8c92f-184">After a custodian acknowledges the hold notification, reminders will no longer be sent to that user.</span></span>
   
5. <span data-ttu-id="8c92f-185">通知の**件名**を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-185">Specify the **Subject** for the notice (required).</span></span> 
   
6. <span data-ttu-id="8c92f-186">保管担当者に提供するコンテンツまたは追加の手順を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-186">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="8c92f-187">手順2で定義したポータルコンテンツがアラーム通知の最後に追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8c92f-187">Note that the portal content you defined in Step 2 is added to the end of the reminder notice.</span></span>
   
7. <span data-ttu-id="8c92f-188">[**保存**] をクリックして、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-188">Click **Save** and go the the next step.</span></span>

### <a name="escalations"></a><span data-ttu-id="8c92f-189">報告</span><span class="sxs-lookup"><span data-stu-id="8c92f-189">Escalations</span></span> 

<span data-ttu-id="8c92f-190">状況によっては、応答のない保管担当者でフォローアップするための別の方法が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="8c92f-190">In some situations, you may need additional ways to follow-up with unresponsive custodians.</span></span> <span data-ttu-id="8c92f-191">保管担当者が、指定された数のアラームを受信した後に保留通知を承認しない場合、法務チームは保管担当者とその上司にエスカレーション通知を自動的に送信するワークフローを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-191">If a custodian doesn't acknowledge a hold notification after receiving the specified number of reminders, the legal team can specify a workflow to automatically send an escalation notice to the custodian and their manager.</span></span>

<span data-ttu-id="8c92f-192">エスカレーションをスケジュールするには</span><span class="sxs-lookup"><span data-stu-id="8c92f-192">To schedule escalations:</span></span>

1. <span data-ttu-id="8c92f-193">**エスカレーション**タイルで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c92f-193">In the **Escalation** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="8c92f-194">**状態**の切り替えをオンにして、**エスカレーション**ワークフローを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8c92f-194">Enable the **Escalation** workflow by turning on the **Status** toggle.</span></span>
   
3. <span data-ttu-id="8c92f-195">エスカレーションの**間隔 (日数)** を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-195">Specify the **Escalation interval (in days)** (required).</span></span> 
   
4. <span data-ttu-id="8c92f-196">**エスカレーションの数**を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-196">Specify the **Number of escalations** (required).</span></span> <span data-ttu-id="8c92f-197">このフィールドには、応答のない保管担当者に送信するエスカレーションの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-197">This field specifies how many escalations to send to un-responsive custodians.</span></span> <span data-ttu-id="8c92f-198">たとえば、エスカレーション数を3に設定すると、エスカレーション通知が保管担当者に送信され、そのマネージャーは最大3回送信されます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-198">For example, if you set the number of escalations to 3, then an escalation notice would be sent to the custodian and their manager a maximum of 3 times.</span></span> <span data-ttu-id="8c92f-199">保管担当者が保留通知を確認すると、エスカレーションは送信されなくなります。</span><span class="sxs-lookup"><span data-stu-id="8c92f-199">After a custodian acknowledges the hold notification, escalations will no longer be sent.</span></span> 
   
5. <span data-ttu-id="8c92f-200">通知の**件名**を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-200">Specify the **Subject** for the notice (required).</span></span> 
   
6. <span data-ttu-id="8c92f-201">保管担当者に提供するコンテンツまたは追加の手順を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="8c92f-201">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="8c92f-202">手順2で定義したポータルコンテンツがエスカレーション通知の末尾に追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8c92f-202">Note that the portal content you defined in Step 2 is added to the end of the escalation notice.</span></span>
   
7. <span data-ttu-id="8c92f-203">[**保存**] をクリックして、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-203">Click **Save** and go the the next step.</span></span>
   
## <a name="step-5-assign-custodians"></a><span data-ttu-id="8c92f-204">手順 5: 保管担当者を割り当てる</span><span class="sxs-lookup"><span data-stu-id="8c92f-204">Step 5: Assign custodians</span></span> 

<span data-ttu-id="8c92f-205">通知の内容を完了したら、通知を送信する保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-205">After you have finalized the content for notifications, select the custodians that you would like to send the notifications.</span></span> 

![保管担当者ページの選択](../media/SelectCustodians.PNG)

<span data-ttu-id="8c92f-207">保管担当者を追加するには</span><span class="sxs-lookup"><span data-stu-id="8c92f-207">To add custodians:</span></span>

1. <span data-ttu-id="8c92f-208">名前の横にあるチェックボックスをオンにして、保管担当者を通信に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-208">Assign custodians to the communication by clicking the checkbox next to their name.</span></span>

    <span data-ttu-id="8c92f-209">通信が作成されると、選択した保管担当者に通知ワークフローが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-209">After the communication is created, the notification workflow will automatically apply to the selected custodians.</span></span>
   
2. <span data-ttu-id="8c92f-210">[**次**へ] をクリックして、通信設定と詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-210">Click **Next** to review the communication settings and details.</span></span>
 
>[!NOTE]
><span data-ttu-id="8c92f-211">保管担当者は、ケースに追加されていて、ケース内で別の通知が送信されていない場合にのみ追加できます。</span><span class="sxs-lookup"><span data-stu-id="8c92f-211">You can only add custodians who have been added to the case and haven't been sent another notification within the case.</span></span>

## <a name="step-6-review-settings"></a><span data-ttu-id="8c92f-212">手順 6: 設定を確認する</span><span class="sxs-lookup"><span data-stu-id="8c92f-212">Step 6: Review settings</span></span>

<span data-ttu-id="8c92f-213">設定を確認し、[**送信**] をクリックして通信を完了すると、システムは、発行通知を送信することによって、自動的に通信ワークフローを開始します。</span><span class="sxs-lookup"><span data-stu-id="8c92f-213">After you review the settings and click **Send** to complete the communication, the system will automatically start the communication workflow by sending the issuance notice.</span></span>
