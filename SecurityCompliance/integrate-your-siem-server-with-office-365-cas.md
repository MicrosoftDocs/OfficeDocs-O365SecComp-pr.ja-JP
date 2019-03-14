---
title: SIEM サーバーと Office 365 Cloud App Security を統合する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dd6d2417-49c4-4de6-9294-67fdabbf8532
description: SIEM サーバーを Office 365 Cloud App Security と統合することができます。 この記事では、機能の概要と設定方法について説明します。
ms.openlocfilehash: 82b5e0e6467bd42acba3c40d67e4e0363a7e0f72
ms.sourcegitcommit: 4abcc03497478abf1ae7fc84792f44360d8e59c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "30548587"
---
# <a name="integrate-your-siem-server-with-office-365-cloud-app-security"></a><span data-ttu-id="d02ee-104">SIEM サーバーと Office 365 Cloud App Security を統合する</span><span class="sxs-lookup"><span data-stu-id="d02ee-104">Integrate your SIEM server with Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="d02ee-105">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d02ee-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="d02ee-106">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d02ee-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="d02ee-107">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d02ee-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="d02ee-108">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="d02ee-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="d02ee-109">評価の開始</span><span class="sxs-lookup"><span data-stu-id="d02ee-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="d02ee-110">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="d02ee-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="d02ee-111">ここでは、</span><span class="sxs-lookup"><span data-stu-id="d02ee-111">You are here!</span></span>  <br/> [<span data-ttu-id="d02ee-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="d02ee-112">Next step</span></span>](utilization-activities-for-ocas.md) <br/> |[<span data-ttu-id="d02ee-113">利用を開始する</span><span class="sxs-lookup"><span data-stu-id="d02ee-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
## <a name="overview-and-prerequisites"></a><span data-ttu-id="d02ee-114">概要と前提条件</span><span class="sxs-lookup"><span data-stu-id="d02ee-114">Overview and prerequisites</span></span>

<span data-ttu-id="d02ee-115">[Office 365 Cloud App security](get-ready-for-office-365-cas.md)をセキュリティ情報およびイベント管理 (SIEM) サーバーと統合して、アラートの集中監視を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d02ee-115">You can integrate [Office 365 Cloud App Security](get-ready-for-office-365-cas.md) with your security information and event management (SIEM) server to enable centralized monitoring of alerts.</span></span> <span data-ttu-id="d02ee-116">これは、クラウドサービスとオンプレミスのサーバーアプリケーションを使用している組織に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="d02ee-116">This is especially beneficial for organizations who are using cloud services and on-premises server applications.</span></span> <span data-ttu-id="d02ee-117">SIEM サーバーを統合して、Office 365 Cloud App Security から SIEM サーバーに通知とアクティビティを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="d02ee-117">You can integrate your SIEM server to pull alerts and activities from Office 365 Cloud App Security into your SIEM server.</span></span> <span data-ttu-id="d02ee-118">SIEM サーバーとの統合により、セキュリティチームは、通常のセキュリティワークフローを維持しながら、特定のセキュリティの手順を自動化し、クラウドベースのイベントとオンプレミスのイベントを関連付けることにより、Office 365 アプリケーションをより適切に保護することができます。</span><span class="sxs-lookup"><span data-stu-id="d02ee-118">Integrating with a SIEM server allows your security team to better protect your Office 365 applications while maintaining your usual security workflow, by automating certain security procedures and correlating between cloud-based and on-premises events.</span></span>  
  
<span data-ttu-id="d02ee-119">最初に SIEM サーバーを Office 365 Cloud App Security と統合すると、過去2日以内の通知が SIEM サーバーに転送されます。さらに、選択したフィルターに基づいて、その後のすべての通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="d02ee-119">When you first integrate your SIEM server with Office 365 Cloud App Security, alerts from the last two days are forwarded to the SIEM server, as well as all alerts from then on (based on any filters you select).</span></span> <span data-ttu-id="d02ee-120">さらに、この機能を長期に対して無効にした場合、再度有効にすると、過去2日間の通知を転送した後、その後にすべての通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="d02ee-120">Additionally, if you disable this feature for an extended period, when you enable it again, it will forward the past two days of alerts and then all alerts from then on.</span></span>

### <a name="siem-integration-architecture"></a><span data-ttu-id="d02ee-121">SIEM 統合アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="d02ee-121">SIEM integration architecture</span></span>

<span data-ttu-id="d02ee-122">組織のネットワークに SIEM エージェントが設定されている。</span><span class="sxs-lookup"><span data-stu-id="d02ee-122">A SIEM agent is set up in your organization's network.</span></span> <span data-ttu-id="d02ee-123">SIEM エージェントは、を展開して構成すると、Office 365 Cloud App Security RESTful api を使用して構成されたデータ型 (警告) を取得します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-123">When deployed and configured, the SIEM agent pulls the data types that were configured (alerts) using Office 365 Cloud App Security RESTful APIs.</span></span> <span data-ttu-id="d02ee-124">その後、トラフィックはポート443上の暗号化された HTTPS チャネルを介して送信されます。</span><span class="sxs-lookup"><span data-stu-id="d02ee-124">The traffic is then sent over an encrypted HTTPS channel on port 443.</span></span>
  
<span data-ttu-id="d02ee-125">SIEM エージェントは、Office 365 Cloud App Security からデータを取得するときに、セットアップ時に提供されたネットワーク構成 (カスタムポートを使用する TCP または UDP) を使用して、Syslog メッセージをローカルの SIEM サーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-125">When a SIEM agent retrieves data from Office 365 Cloud App Security, it sends the Syslog messages to your local SIEM server using the network configurations that are provided during setup (TCP or UDP with a custom port).</span></span>

![SIEM および Cloud App Security architecture](media/siem-architecture.png)

### <a name="supported-siem-servers"></a><span data-ttu-id="d02ee-127">サポートされている SIEM サーバー</span><span class="sxs-lookup"><span data-stu-id="d02ee-127">Supported SIEM servers</span></span>

<span data-ttu-id="d02ee-128">Office 365 Cloud App Security は現在、次の SIEM サーバーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d02ee-128">Office 365 Cloud App Security currently supports the following SIEM servers:</span></span>
- <span data-ttu-id="d02ee-129">マイクロフォーカスの arcsight</span><span class="sxs-lookup"><span data-stu-id="d02ee-129">Micro Focus ArcSight</span></span>
- <span data-ttu-id="d02ee-130">汎用 cef</span><span class="sxs-lookup"><span data-stu-id="d02ee-130">Generic CEF</span></span>

### <a name="prerequisites"></a><span data-ttu-id="d02ee-131">前提条件</span><span class="sxs-lookup"><span data-stu-id="d02ee-131">Prerequisites</span></span>

- <span data-ttu-id="d02ee-132">この記事で説明されているタスクを実行するには、全体管理者またはセキュリティ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02ee-132">You must be a global administrator or security administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="d02ee-133">[Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可を参照する](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="d02ee-133">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)</span></span>

- <span data-ttu-id="d02ee-134">組織に対し[て Office 365 Cloud App Security が有効になっ](turn-on-office-365-cas.md)ている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02ee-134">You must have [Office 365 Cloud App Security enabled](turn-on-office-365-cas.md) for your organization.</span></span>

- <span data-ttu-id="d02ee-135">Office 365 の[監査ログ](turn-audit-log-search-on-or-off.md)を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02ee-135">[Audit logging](turn-audit-log-search-on-or-off.md) must be turned on for Office 365</span></span>

- <span data-ttu-id="d02ee-136">SIEM サーバーの統合を構成するためには、次の要件を満たす標準サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="d02ee-136">You must have a standard server that meets the following requirements in order to configure SIEM server integration:</span></span>
    - <span data-ttu-id="d02ee-137">OS: Windows または Linux (仮想マシンの場合があります)</span><span class="sxs-lookup"><span data-stu-id="d02ee-137">OS: Windows or Linux (this can be a virtual machine)</span></span>
    - <span data-ttu-id="d02ee-138">CPU: 2</span><span class="sxs-lookup"><span data-stu-id="d02ee-138">CPU: 2</span></span>
    - <span data-ttu-id="d02ee-139">ディスク容量:20 GB</span><span class="sxs-lookup"><span data-stu-id="d02ee-139">Disk space: 20 GB</span></span>
    - <span data-ttu-id="d02ee-140">RAM: 2 GB</span><span class="sxs-lookup"><span data-stu-id="d02ee-140">RAM: 2 GB</span></span>
    - <span data-ttu-id="d02ee-141">[Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html)のインストール</span><span class="sxs-lookup"><span data-stu-id="d02ee-141">[Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html) installed</span></span>
    - <span data-ttu-id="d02ee-142">「[ネットワーク要件](https://docs.microsoft.com/cloud-app-security/network-requirements)」の説明に従って構成されたファイアウォール</span><span class="sxs-lookup"><span data-stu-id="d02ee-142">Firewall configured as described in [Network requirements](https://docs.microsoft.com/cloud-app-security/network-requirements)</span></span>

- <span data-ttu-id="d02ee-143">**リモート syslog ホスト**および**syslot ポート番号**についての詳細を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02ee-143">You must have details about your **Remote syslog host** and **Syslot port number**.</span></span> <span data-ttu-id="d02ee-144">ネットワーク管理者またはセキュリティ管理者は、その情報を検索できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02ee-144">A network administrator or security administrator should be able to help you locate that information.</span></span> 

- <span data-ttu-id="d02ee-145">SIEM サーバーを統合するために必要な[JAR ファイル](https://go.microsoft.com/fwlink/?linkid=838596)をダウンロードするには、[ソフトウェアライセンス条項](https://go.microsoft.com/fwlink/?linkid=862491)に同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02ee-145">You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) to download the [JAR file](https://go.microsoft.com/fwlink/?linkid=838596) you'll need to integrate your SIEM server.</span></span>
 
## <a name="step-1-set-it-up-a-siem-agent-in-office-365-cloud-app-security"></a><span data-ttu-id="d02ee-146">手順 1: Office 365 Cloud App Security で SIEM エージェントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="d02ee-146">Step 1: Set it up a SIEM agent in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="d02ee-147">Cloud App Security ポータル ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="d02ee-147">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="d02ee-148">[**設定** \> ] [**セキュリティ拡張機能**] をクリックし、[SIEM エージェント] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-148">Click **Settings** \> **Security extensions**, and then choose SIEM agents.</span></span><br/>
<span data-ttu-id="d02ee-149">![設定 > のセキュリティ拡張機能を選択する](media/Settings-SecurityExtensions.png)</span><span class="sxs-lookup"><span data-stu-id="d02ee-149">![Choose Settings > Security extensions](media/Settings-SecurityExtensions.png)</span></span>

3. <span data-ttu-id="d02ee-150">[ **Add SIEM agent**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d02ee-150">Choose **Add SIEM agent**.</span></span><br/><span data-ttu-id="d02ee-151">![[Add SIEM agent] を選びます。](media/SIEMAgents.png)</span><span class="sxs-lookup"><span data-stu-id="d02ee-151">![Choose Add SIEM agent.](media/SIEMAgents.png)</span></span>
    
4. <span data-ttu-id="d02ee-152">[**ウィザードの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-152">Choose **Start wizard**.</span></span><br/><span data-ttu-id="d02ee-153">![ヘルプを表示する、またはウィザードを開始する](media/HelpOrWizard.png)</span><span class="sxs-lookup"><span data-stu-id="d02ee-153">![Get help or start the wizard](media/HelpOrWizard.png)</span></span> 
    
5. <span data-ttu-id="d02ee-154">**一般的**な手順で、名前を指定し、 **SIEM 形式を選択**して、その形式に関連する**詳細設定**を設定します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-154">In the **General** step, specify a name, and **Select your SIEM format** and set any **Advanced settings** that are relevant to that format.</span></span> <span data-ttu-id="d02ee-155">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-155">Then choose **Next**.</span></span><br/><span data-ttu-id="d02ee-156">![名前と種類を指定する](media/ChooseAgentTypeAndName.png)</span><span class="sxs-lookup"><span data-stu-id="d02ee-156">![Specify a name and type](media/ChooseAgentTypeAndName.png)</span></span>
    
6. <span data-ttu-id="d02ee-157">syslog の**リモート**ステップで、**リモート syslog ホスト**の IP アドレスまたはホスト名と**syslog ポート番号**を指定します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-157">In the **Remote Syslog** step, specify the IP address or hostname of the **Remote syslog host** and the **Syslog port number**.</span></span> <span data-ttu-id="d02ee-158">リモート Syslog プロトコルとして TCP または UDP を選択します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-158">Select TCP or UDP as the Remote Syslog protocol.</span></span> <span data-ttu-id="d02ee-159">(必要な場合は、ネットワーク管理者またはセキュリティ管理者と協力して、これらの詳細を取得することができます)。[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-159">(You can work with your network administrator or security administrator to get these details if you don't have them.) Then choose **Next**.</span></span><br/><span data-ttu-id="d02ee-160">![リモート Syslog の詳細を指定する](media/ArcSightS1Syslog.png)</span><span class="sxs-lookup"><span data-stu-id="d02ee-160">![Specify Remote Syslog details](media/ArcSightS1Syslog.png)</span></span>
  
7. <span data-ttu-id="d02ee-161">[**データ型**] ステップで、次のいずれかの操作を行い、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d02ee-161">In the **Data Types** step, do one of the following, and then click **Next**:</span></span>
    - <span data-ttu-id="d02ee-162">**すべての通知**の既定の設定を保持する</span><span class="sxs-lookup"><span data-stu-id="d02ee-162">Keep the default setting of **All Alerts**</span></span><br/><span data-ttu-id="d02ee-163">OR</span><span class="sxs-lookup"><span data-stu-id="d02ee-163">OR</span></span>
    - <span data-ttu-id="d02ee-164">[**すべての通知**] をクリックし、[**特定のフィルター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-164">Click **All alerts**, and then choose **Specific filters**.</span></span> <span data-ttu-id="d02ee-165">SIEM サーバーに送信する通知の種類を選択するためのフィルターを定義します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-165">Define filters to select the kinds of alerts you want to send to your SIEM server.</span></span>
<br/><span data-ttu-id="d02ee-166">![ウィザードの [データ型] の手順](media/ArcSightS1ExportOptions.png)</span><span class="sxs-lookup"><span data-stu-id="d02ee-166">![Data Types step of the wizard](media/ArcSightS1ExportOptions.png)</span></span>
  
8. <span data-ttu-id="d02ee-167">[完了] 画面で、トークンをコピーし、後で保存します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-167">On the Congratulations screen, copy the token and save it for later.</span></span><br/>![SIEM エージェント作成画面](media/SIEMAgentFinished.png) 

> [!IMPORTANT]
> <span data-ttu-id="d02ee-169">この時点で、Office 365 Cloud App Security で SIEM エージェントをセットアップしましたが、SIEM サーバーの統合はまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="d02ee-169">At this point, you have set up a SIEM agent in Office 365 Cloud App Security, but your SIEM server integration is not yet finished.</span></span> <span data-ttu-id="d02ee-170">次の手順に進んで、SIEM サーバーの統合を続行します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-170">Proceed to the next step to continue your SIEM server integration.</span></span>

<span data-ttu-id="d02ee-171">[閉じる] をクリックしてウィザードを終了すると、[セキュリティ拡張機能] 画面に、表に追加した SIEM エージェントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d02ee-171">After you click Close and leave the wizard, on the Security extensions screen, you can see the SIEM agent you added in the table.</span></span> <span data-ttu-id="d02ee-172">後で接続されるまで、[**作成済み**] の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d02ee-172">It will show a status of **Created** until it's connected later.</span></span>

![SIEM エージェントの作成](media/SIEMAgentCreated.png)
    
## <a name="step-2-download-a-jar-file-and-run-it-on-your-siem-server"></a><span data-ttu-id="d02ee-174">手順 2: JAR ファイルをダウンロードして、SIEM サーバー上で実行する</span><span class="sxs-lookup"><span data-stu-id="d02ee-174">Step 2: Download a JAR file and run it on your SIEM server</span></span>

1. <span data-ttu-id="d02ee-175">[Microsoft Cloud App Security SIEM エージェント](https://go.microsoft.com/fwlink/?linkid=838596)をダウンロードし、フォルダーを解凍します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-175">Download the [Microsoft Cloud App Security SIEM Agent](https://go.microsoft.com/fwlink/?linkid=838596) and unzip the folder.</span></span> <span data-ttu-id="d02ee-176">(続行するには、[ソフトウェアライセンス条項](https://go.microsoft.com/fwlink/?linkid=862491)に同意する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="d02ee-176">(You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) in order to proceed.)</span></span> 
    
2. <span data-ttu-id="d02ee-177">zip フォルダーから .jar ファイルを抽出し、SIEM サーバー上で実行します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-177">Extract the .jar file from the zipped folder and run it on your SIEM server.</span></span>
    
3. <span data-ttu-id="d02ee-178">ファイルを実行した後、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-178">After running the file, run the following: command:</span></span><br/>
  ```
  java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
  ```
### <a name="important-notes"></a><span data-ttu-id="d02ee-179">重要事項</span><span class="sxs-lookup"><span data-stu-id="d02ee-179">Important notes</span></span>

- <span data-ttu-id="d02ee-180">ファイル名は、SIEM エージェントのバージョンによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d02ee-180">The file name may differ depending on the version of the SIEM agent.</span></span> 

- <span data-ttu-id="d02ee-181">サーバーのセットアップ時に、SIEM サーバー上で JAR ファイルを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d02ee-181">We recommend that you run the JAR file on your SIEM server during server setup.</span></span>

    - <span data-ttu-id="d02ee-182">**Windows**: スケジュールされたタスクとして実行し、**ユーザーがログオンしているかどうか**を確認し、[**タスクの実行**時間が次の値を超えた場合は停止する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d02ee-182">**Windows**: Run as a scheduled task, making sure to configure the task to **Run whether the user is logged on or not** and clear the **Stop the task if it runs longer than** option.</span></span>

    - <span data-ttu-id="d02ee-183">**Linux**: **&** `rc.local`ファイルにを含む run コマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-183">**Linux**: Add the run command with an **&** to the `rc.local` file.</span></span> <br/><span data-ttu-id="d02ee-184">例:</span><span class="sxs-lookup"><span data-stu-id="d02ee-184">Example:</span></span><br/> 
    ```
    java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &
    ```

- <span data-ttu-id="d02ee-185">角かっこで囲まれたパラメーターはオプションであり、関連する場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="d02ee-185">Parameters in brackets [] are optional, and should be used only if relevant.</span></span> <span data-ttu-id="d02ee-186">次の変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-186">Use the following variables:</span></span>

    - <span data-ttu-id="d02ee-187">**DIRNAME**は、ローカルエージェントのデバッグログに使用するディレクトリへのパスです。</span><span class="sxs-lookup"><span data-stu-id="d02ee-187">**DIRNAME** is the path to the directory you want to use for local agent debug logs.</span></span>

    - <span data-ttu-id="d02ee-188">**ADDRESS [:P ort]** は、サーバーがインターネットに接続するために使用するプロキシサーバーのアドレスおよびポートです。</span><span class="sxs-lookup"><span data-stu-id="d02ee-188">**ADDRESS[:PORT]** is the proxy server address and port that the server uses to connect to the Internet.</span></span>

    - <span data-ttu-id="d02ee-189">**TOKEN**は、最初の手順でコピーした SIEM エージェントトークンです。</span><span class="sxs-lookup"><span data-stu-id="d02ee-189">**TOKEN** is the SIEM agent token you copied in the first procedure.</span></span>

    - <span data-ttu-id="d02ee-190">ヘルプを表示するに`-h`は、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-190">To get help, type `-h`.</span></span> 
  
## <a name="step-3-validate-that-the-siem-agent-is-working"></a><span data-ttu-id="d02ee-191">手順 3: SIEM エージェントが動作していることを検証する</span><span class="sxs-lookup"><span data-stu-id="d02ee-191">Step 3: Validate that the SIEM agent is working</span></span>

1. <span data-ttu-id="d02ee-192">Office 365 Cloud App Security portal の SIEM エージェントの状態が、**接続エラー**または**切断**されていないこと、およびエージェントの通知がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-192">Make sure the status of the SIEM agent in the Office 365 Cloud App Security portal is not displayed as **Connection error** or **Disconnected** and that there are no agent notifications.</span></span><br/><span data-ttu-id="d02ee-193">たとえば、次のように、SIEM サーバーが接続されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d02ee-193">For example, here we can see the SIEM server is connected:</span></span><br/><span data-ttu-id="d02ee-194">![SIEM サーバーの接続](media/siem-connected.png)</span><span class="sxs-lookup"><span data-stu-id="d02ee-194">![SIEM server connected](media/siem-connected.png)</span></span><br/><span data-ttu-id="d02ee-195">ここでは、SIEM サーバーが切断されています。</span><span class="sxs-lookup"><span data-stu-id="d02ee-195">And here, we can see the SIEM server is disconnected:</span></span><br/><span data-ttu-id="d02ee-196">![SIEM サーバーが接続されていません](media/siem-not-connected.png)</span><span class="sxs-lookup"><span data-stu-id="d02ee-196">![SIEM server not connected](media/siem-not-connected.png)</span></span> 
  
2. <span data-ttu-id="d02ee-197">Syslog/SIEM サーバーで、通知が Office 365 Cloud App Security から届いていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d02ee-197">In your Syslog/SIEM server, make sure you see that alerts have arrived from Office 365 Cloud App Security.</span></span>
  
## <a name="what-the-logfiles-look-like"></a><span data-ttu-id="d02ee-198">ログの内容は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d02ee-198">What the logfiles look like</span></span>

<span data-ttu-id="d02ee-199">SIEM サーバーに送信される可能性のある警告ログファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-199">Here's an alerts logfile example that might be sent to a SIEM server:</span></span>

```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```

<span data-ttu-id="d02ee-200">もう1つの例を次に示します。この時間は、cef 形式です。</span><span class="sxs-lookup"><span data-stu-id="d02ee-200">And here's another sample, this time in CEF format:</span></span>


|<span data-ttu-id="d02ee-201">cef フィールド名</span><span class="sxs-lookup"><span data-stu-id="d02ee-201">CEF field name</span></span>  | <span data-ttu-id="d02ee-202">説明</span><span class="sxs-lookup"><span data-stu-id="d02ee-202">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d02ee-203">開始</span><span class="sxs-lookup"><span data-stu-id="d02ee-203">start</span></span>     | <span data-ttu-id="d02ee-204">アラートのタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="d02ee-204">alert timestamp</span></span>        |
|<span data-ttu-id="d02ee-205">end</span><span class="sxs-lookup"><span data-stu-id="d02ee-205">end</span></span>     | <span data-ttu-id="d02ee-206">アラートのタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="d02ee-206">alert timestamp</span></span>        |
|<span data-ttu-id="d02ee-207">rt</span><span class="sxs-lookup"><span data-stu-id="d02ee-207">rt</span></span>     | <span data-ttu-id="d02ee-208">アラートのタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="d02ee-208">alert timestamp</span></span>        |
|<span data-ttu-id="d02ee-209">msg</span><span class="sxs-lookup"><span data-stu-id="d02ee-209">msg</span></span>     | <span data-ttu-id="d02ee-210">Office 365 Cloud App Security ポータルに表示されるアラートの説明</span><span class="sxs-lookup"><span data-stu-id="d02ee-210">alert description as shown in the Office 365 Cloud App Security portal</span></span>        |
|<span data-ttu-id="d02ee-211">suser</span><span class="sxs-lookup"><span data-stu-id="d02ee-211">suser</span></span>     | <span data-ttu-id="d02ee-212">通知対象ユーザー</span><span class="sxs-lookup"><span data-stu-id="d02ee-212">alert subject user</span></span>        |
|<span data-ttu-id="d02ee-213">destinationservicename</span><span class="sxs-lookup"><span data-stu-id="d02ee-213">destinationServiceName</span></span>     | <span data-ttu-id="d02ee-214">Office 365、SharePoint、OneDrive などの通知元アプリ</span><span class="sxs-lookup"><span data-stu-id="d02ee-214">alert originating app, such as Office 365, SharePoint, or OneDrive</span></span>        |
|<span data-ttu-id="d02ee-215">cslabel</span><span class="sxs-lookup"><span data-stu-id="d02ee-215">csLabel</span></span>     | <span data-ttu-id="d02ee-216">(ラベルの意味は異なります)。</span><span class="sxs-lookup"><span data-stu-id="d02ee-216">Varies (labels have different meanings).</span></span> <span data-ttu-id="d02ee-217">通常、ラベルは targetObjects のように、わかりやすいように記述されています。</span><span class="sxs-lookup"><span data-stu-id="d02ee-217">Typically, labels are self-explanatory, like targetObjects.</span></span>        |
|<span data-ttu-id="d02ee-218">cs</span><span class="sxs-lookup"><span data-stu-id="d02ee-218">cs</span></span>     | <span data-ttu-id="d02ee-219">ラベルに対応する情報 (ラベルの例に従って通知を行う対象ユーザーなど)</span><span class="sxs-lookup"><span data-stu-id="d02ee-219">Information corresponding to a label (such as the target user of an alert as per the label example)</span></span>        |

## <a name="additional-tasks-as-needed"></a><span data-ttu-id="d02ee-220">その他のタスク (必要な場合)</span><span class="sxs-lookup"><span data-stu-id="d02ee-220">Additional tasks (as needed)</span></span>

<span data-ttu-id="d02ee-221">SIEM サーバーを構成し、それを Office 365 Cloud App Security と統合した後で、トークンの再生成、SIEM エージェントの編集、または SIEM エージェントの削除が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d02ee-221">After you have configured your SIEM server and have integrated it with Office 365 Cloud App Security, you might need to regenerate a token, edit a SIEM agent, or delete a SIEM agent.</span></span> <span data-ttu-id="d02ee-222">次のセクションでは、これらのタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-222">The following sections describe how to perform these tasks.</span></span>

### <a name="regenerate-a-token"></a><span data-ttu-id="d02ee-223">トークンの再生成</span><span class="sxs-lookup"><span data-stu-id="d02ee-223">Regenerate a token</span></span>

<span data-ttu-id="d02ee-224">トークンを紛失した場合は1つを再生成できます。</span><span class="sxs-lookup"><span data-stu-id="d02ee-224">If you lose your token, you can regenerate one.</span></span> 

1. <span data-ttu-id="d02ee-225">[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)Office 365 Cloud App Security ポータル () で、[**設定** > ] [**セキュリティ拡張機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-225">In the Office 365 Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)), choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="d02ee-226">表で、SIEM エージェントの行を見つけます。</span><span class="sxs-lookup"><span data-stu-id="d02ee-226">In the table, locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="d02ee-227">省略記号をクリックし、[**トークンの再生成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-227">Click the ellipses, and then choose **Regenerate token**.</span></span><br/><span data-ttu-id="d02ee-228">![SIEM エージェントの省略記号をクリックしてトークンを再生成する](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)</span><span class="sxs-lookup"><span data-stu-id="d02ee-228">![Regenerate a token by clicking the ellipsis for your SIEM agent](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)</span></span>
  
### <a name="edit-a-siem-agent"></a><span data-ttu-id="d02ee-229">SIEM エージェントを編集する</span><span class="sxs-lookup"><span data-stu-id="d02ee-229">Edit a SIEM agent</span></span>

1. <span data-ttu-id="d02ee-230">[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)Office 365 Cloud App Security ポータル () で、[**設定** > ] [**セキュリティ拡張機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-230">In the Office 365 Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)), choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="d02ee-231">SIEM エージェントの行を見つけます。</span><span class="sxs-lookup"><span data-stu-id="d02ee-231">Locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="d02ee-232">省略記号をクリックしてから、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-232">Click the ellipses, and then choose **Edit**.</span></span> <span data-ttu-id="d02ee-233">(SIEM エージェントを編集する場合は、.jar ファイルを再実行する必要はありませんが、自動的に更新されます)。</span><span class="sxs-lookup"><span data-stu-id="d02ee-233">(If you edit the SIEM agent, you do not need to re-run the .jar file; it updates automatically.)</span></span> <br/><span data-ttu-id="d02ee-234">![SIEM エージェントを編集するには、省略記号を選択してから、[編集] を選択します。](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)</span><span class="sxs-lookup"><span data-stu-id="d02ee-234">![To edit your SIEM agent, choose the ellipses, and then choose Edit.](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)</span></span>
  
### <a name="delete-a-siem-agent"></a><span data-ttu-id="d02ee-235">SIEM エージェントを削除する</span><span class="sxs-lookup"><span data-stu-id="d02ee-235">Delete a SIEM agent</span></span>

1. <span data-ttu-id="d02ee-236">[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)Office 365 Cloud App Security ポータル () で、[**設定** > ] [**セキュリティ拡張機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-236">In the Office 365 Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)), choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="d02ee-237">SIEM エージェントの行を見つけます。</span><span class="sxs-lookup"><span data-stu-id="d02ee-237">Locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="d02ee-238">省略記号をクリックし、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d02ee-238">Click the ellipses, and then choose **Delete**.</span></span><br/><span data-ttu-id="d02ee-239">![SIEM エージェントを削除するには、省略記号を選択してから、[削除] を選択します。](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)</span><span class="sxs-lookup"><span data-stu-id="d02ee-239">![To delete a SIEM agent, choose the ellipses, and then choose Delete.](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)</span></span>

  
## <a name="next-steps"></a><span data-ttu-id="d02ee-240">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d02ee-240">Next steps</span></span>

- [<span data-ttu-id="d02ee-241">Office 365 Cloud App Security 展開後の利用に関する作業</span><span class="sxs-lookup"><span data-stu-id="d02ee-241">Utilization activities after rolling out Office 365 Cloud App Security</span></span>](utilization-activities-for-ocas.md)
    
- [<span data-ttu-id="d02ee-242">通知を確認して処理を実行する</span><span class="sxs-lookup"><span data-stu-id="d02ee-242">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="d02ee-243">IP アドレスをグループ化して管理を簡素化する</span><span class="sxs-lookup"><span data-stu-id="d02ee-243">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

