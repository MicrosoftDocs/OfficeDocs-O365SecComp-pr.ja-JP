---
title: SIEM サーバーと Office 365 Cloud App Security を統合する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dd6d2417-49c4-4de6-9294-67fdabbf8532
description: SIEM サーバーは、Office 365 のクラウド アプリケーションのセキュリティと統合できます。仕組みと、それを設定する方法の概要を取得するには、この資料を参照してください。
ms.openlocfilehash: 6b9d51d91d4b1ae55dd0dd16a92872daa4ecef90
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "23043265"
---
# <a name="integrate-your-siem-server-with-office-365-cloud-app-security"></a><span data-ttu-id="47526-104">SIEM サーバーと Office 365 Cloud App Security を統合する</span><span class="sxs-lookup"><span data-stu-id="47526-104">Integrate your SIEM server with Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="47526-105">評価 * *\>**</span><span class="sxs-lookup"><span data-stu-id="47526-105">****Evaluation** \>**</span></span>|<span data-ttu-id="47526-106">計画 * *\>**</span><span class="sxs-lookup"><span data-stu-id="47526-106">****Planning** \>**</span></span>|<span data-ttu-id="47526-107">配置 * *\>**</span><span class="sxs-lookup"><span data-stu-id="47526-107">****Deployment** \>**</span></span>|<span data-ttu-id="47526-108">使用率。</span><span class="sxs-lookup"><span data-stu-id="47526-108">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="47526-109">評価を開始します。</span><span class="sxs-lookup"><span data-stu-id="47526-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="47526-110">計画の開始します。</span><span class="sxs-lookup"><span data-stu-id="47526-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="47526-111">コースです!</span><span class="sxs-lookup"><span data-stu-id="47526-111">You are here!</span></span>  <br/> [<span data-ttu-id="47526-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="47526-112">Next step</span></span>](utilization-activities-for-ocas.md) <br/> |[<span data-ttu-id="47526-113">使用します。</span><span class="sxs-lookup"><span data-stu-id="47526-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="47526-p102">警告の集中型の監視を有効にするセキュリティ情報およびイベント管理 (SIEM) サーバーを使用して[Office 365 のクラウド アプリケーションのセキュリティ](get-ready-for-office-365-cas.md)を統合できます。これは、クラウド サービスを使用している組織で特に効果的とオンプレミスのサーバー アプリケーションです。SIEM サーバーとの統合により、セキュリティ チームは、特定のセキュリティ保護手順を自動化し、クラウド ・ ベースの間に相関関連づけることによって、セキュリティの一般的なワークフローを維持しながら、Office 365 アプリケーションの保護を強化して、設置型のイベントです。</span><span class="sxs-lookup"><span data-stu-id="47526-p102">You can integrate [Office 365 Cloud App Security](get-ready-for-office-365-cas.md) with your security information and event management (SIEM) server to enable centralized monitoring of alerts. This is especially beneficial for organizations who are using cloud services and on-premises server applications. Integrating with a SIEM server allows your security team to better protect your Office 365 applications while maintaining your usual security workflow, by automating certain security procedures and correlating between cloud-based and on-premises events.</span></span>  
  
<span data-ttu-id="47526-p103">とき、最初に、Office 365 のクラウド アプリケーションのセキュリティと、SIEM のサーバーを統合すると、最後の 2 日間からの通知から転送されます SIEM サーバーとすべてのアラートに後で (選択したフィルターに基づいて)。さらに、長期間、有効にすると、再度、この機能を無効にした場合、過去 2 日間の通知とし、すべてのアラートの後に転送します。</span><span class="sxs-lookup"><span data-stu-id="47526-p103">When you first integrate your SIEM server with Office 365 Cloud App Security, alerts from the last two days are forwarded to the SIEM server, as well as all alerts from then on (based on any filters you select). Additionally, if you disable this feature for an extended period, when you enable it again, it will forward the past two days of alerts and then all alerts from then on.</span></span>
 
## <a name="siem-integration-architecture"></a><span data-ttu-id="47526-119">SIEM の統合アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="47526-119">SIEM integration architecture</span></span>

<span data-ttu-id="47526-p104">SIEM のエージェントは、組織のネットワークに設定されます。SIEM エージェントが構成されているデータ型を取得を展開し、構成すると Office 365 クラウド アプリケーション セキュリティ RESTful Api を使用するように (警告)。トラフィックは、ポート 443 の HTTPS の暗号化されたチャネル経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="47526-p104">A SIEM agent is set up in your organization's network. When deployed and configured, the SIEM agent pulls the data types that were configured (alerts) using Office 365 Cloud App Security RESTful APIs. The traffic is then sent over an encrypted HTTPS channel on port 443.</span></span>
  
<span data-ttu-id="47526-123">SIEM エージェントでは、Office 365 のクラウド アプリケーションのセキュリティからデータを取得、Syslog メッセージを (TCP または UDP のカスタム ポート) のセットアップ中に提供されているネットワークの構成を使用して、ローカルの SIEM サーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="47526-123">When a SIEM agent retrieves data from Office 365 Cloud App Security, it sends the Syslog messages to your local SIEM server using the network configurations that are provided during setup (TCP or UDP with a custom port).</span></span>

![SIEM およびクラウド アプリケーションのセキュリティのアーキテクチャ](media/siem-architecture.png)

## <a name="supported-siem-servers"></a><span data-ttu-id="47526-125">SIEM サーバーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="47526-125">Supported SIEM servers</span></span>

<span data-ttu-id="47526-126">現在、office 365 のクラウド アプリケーションのセキュリティには、次の SIEM サーバーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="47526-126">Office 365 Cloud App Security currently supports the following SIEM servers:</span></span>
- <span data-ttu-id="47526-127">Arcsight 社のマイクロ フォーカス</span><span class="sxs-lookup"><span data-stu-id="47526-127">Micro Focus ArcSight</span></span>
- <span data-ttu-id="47526-128">汎用 CEF</span><span class="sxs-lookup"><span data-stu-id="47526-128">Generic CEF</span></span>

## <a name="prerequisites"></a><span data-ttu-id="47526-129">前提条件</span><span class="sxs-lookup"><span data-stu-id="47526-129">Prerequisites</span></span>

- <span data-ttu-id="47526-p105">この資料で説明するタスクを実行するには、グローバル管理者またはセキュリティ管理者である必要があります。参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="47526-p105">You must be a global administrator or security administrator to perform the tasks described in this article. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)</span></span>

- <span data-ttu-id="47526-132">組織の[Office 365 のクラウド アプリケーションのセキュリティを有効に](turn-on-office-365-cas.md)するが必要です。</span><span class="sxs-lookup"><span data-stu-id="47526-132">You must have [Office 365 Cloud App Security enabled](turn-on-office-365-cas.md) for your organization.</span></span>

- <span data-ttu-id="47526-133">Office 365 の[監査ログを記録](turn-audit-log-search-on-or-off.md)を有効する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47526-133">[Audit logging](turn-audit-log-search-on-or-off.md) must be turned on for Office 365</span></span>

- <span data-ttu-id="47526-134">SIEM サーバー統合を構成するのには次の要件を満たす標準的なサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="47526-134">You must have a standard server that meets the following requirements in order to configure SIEM server integration:</span></span>
    - <span data-ttu-id="47526-135">OS: Windows または Linux を (これは、仮想マシンを使用できます)</span><span class="sxs-lookup"><span data-stu-id="47526-135">OS: Windows or Linux (this can be a virtual machine)</span></span>
    - <span data-ttu-id="47526-136">CPU: 2</span><span class="sxs-lookup"><span data-stu-id="47526-136">CPU: 2</span></span>
    - <span data-ttu-id="47526-137">ディスクの空き容量: 20 GB</span><span class="sxs-lookup"><span data-stu-id="47526-137">Disk space: 20 GB</span></span>
    - <span data-ttu-id="47526-138">2 GB の RAM。</span><span class="sxs-lookup"><span data-stu-id="47526-138">RAM: 2 GB</span></span>
    - <span data-ttu-id="47526-139">インストールされている[oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html)</span><span class="sxs-lookup"><span data-stu-id="47526-139">[Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html) installed</span></span>
    - <span data-ttu-id="47526-140">ファイアウォールが[ネットワークの要件](https://docs.microsoft.com/cloud-app-security/network-requirements)に従って構成されています。</span><span class="sxs-lookup"><span data-stu-id="47526-140">Firewall configured as described in [Network requirements](https://docs.microsoft.com/cloud-app-security/network-requirements)</span></span>

- <span data-ttu-id="47526-p106">**リモートの syslog ホスト**と**ポート番号の Syslot**に関する詳細情報が必要です。ネットワーク管理者またはセキュリティ管理者はその情報を特定することがあります。</span><span class="sxs-lookup"><span data-stu-id="47526-p106">You must have details about your **Remote syslog host** and **Syslot port number**. A network administrator or security administrator should be able to help you locate that information.</span></span> 

- <span data-ttu-id="47526-143">[JAR ファイル](https://go.microsoft.com/fwlink/?linkid=838596)、SIEM のサーバーを統合する必要がありますをダウンロードするのには、[ソフトウェア ライセンス条項](https://go.microsoft.com/fwlink/?linkid=862491)に同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47526-143">You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) to download the [JAR file](https://go.microsoft.com/fwlink/?linkid=838596) you'll need to integrate your SIEM server.</span></span>
 
## <a name="integrate-office-365-cloud-app-security"></a><span data-ttu-id="47526-144">Office 365 のクラウド アプリケーションのセキュリティを統合します。</span><span class="sxs-lookup"><span data-stu-id="47526-144">Integrate Office 365 Cloud App Security</span></span>
    
### <a name="step-1-set-it-up-in-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="47526-145">手順 1: 設定 Office 365 のクラウド アプリケーションのセキュリティ関連ポータルに</span><span class="sxs-lookup"><span data-stu-id="47526-145">Step 1: Set it up in the Office 365 Cloud App Security portal</span></span>

1. <span data-ttu-id="47526-p107">[https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用して Office 365 にサインインします。(これで、セキュリティには、&amp;コンプライアンス センター)。</span><span class="sxs-lookup"><span data-stu-id="47526-p107">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="47526-148">**アラート**を参照して\>**詳細なアラートを管理**します。</span><span class="sxs-lookup"><span data-stu-id="47526-148">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="47526-p108">**Office 365 のクラウド アプリケーションのセキュリティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="47526-p108">Choose **Go to Office 365 Cloud App Security**. </span></span></br>
    <span data-ttu-id="47526-150">![セキュリティ&amp;コンプライアンス センターでは、Office 365 のクラウド アプリケーションのセキュリティに移動するのには高度な通知の管理を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="47526-150">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span>
  
4. <span data-ttu-id="47526-151">[**設定**] をクリックして\>**セキュリティ拡張機能**です。</span><span class="sxs-lookup"><span data-stu-id="47526-151">Click **Settings** \> **Security extensions**.</span></span></br>
<span data-ttu-id="47526-152">![設定 > セキュリティ拡張機能](media/Settings-SecurityExtensions.png)</span><span class="sxs-lookup"><span data-stu-id="47526-152">![Choose Settings > Security extensions](media/Settings-SecurityExtensions.png)</span></span>

5. <span data-ttu-id="47526-153">**SIEM の追加のエージェント**を選択します。</span><span class="sxs-lookup"><span data-stu-id="47526-153">Choose **Add SIEM agent**.</span></span></br><span data-ttu-id="47526-154">![SIEM の追加のエージェントを選択します。](media/SIEMAgents.png)</span><span class="sxs-lookup"><span data-stu-id="47526-154">![Choose Add SIEM agent.](media/SIEMAgents.png)</span></span>
    
6. <span data-ttu-id="47526-155">**ウィザードの開始**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="47526-155">Choose **Start wizard**.</span></span></br><span data-ttu-id="47526-156">![ヘルプを表示するか、ウィザードの開始](media/HelpOrWizard.png)</span><span class="sxs-lookup"><span data-stu-id="47526-156">![Get help or start the wizard](media/HelpOrWizard.png)</span></span> 
    
7. <span data-ttu-id="47526-p109">**全般**の手順では、名、および **、SIEM の形式を選択して**指定しの**詳細設定**は、その形式に関連するを設定します。**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="47526-p109">In the **General** step, specify a name, and **Select your SIEM format** and set any **Advanced settings** that are relevant to that format. Then choose **Next**.</span></span></br><span data-ttu-id="47526-159">![名前と種類を指定します。](media/ChooseAgentTypeAndName.png)</span><span class="sxs-lookup"><span data-stu-id="47526-159">![Specify a name and type](media/ChooseAgentTypeAndName.png)</span></span>
    
8. <span data-ttu-id="47526-p110">**リモートの Syslog**の手順で、IP アドレスまたは**リモートの syslog ホスト**と**ポート番号の Syslog**のホスト名を指定します。リモートの Syslog プロトコルとして TCP または UDP を選択します。(使用することがない場合、これらの詳細を取得するには、ネットワーク管理者またはセキュリティ管理者です。)**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="47526-p110">In the **Remote Syslog** step, specify the IP address or hostname of the **Remote syslog host** and the **Syslog port number**. Select TCP or UDP as the Remote Syslog protocol. (You can work with your network administrator or security administrator to get these details if you don't have them.) Then choose **Next**.</span></span></br><span data-ttu-id="47526-163">![リモートの Syslog の詳細を指定します。](media/ArcSightS1Syslog.png)</span><span class="sxs-lookup"><span data-stu-id="47526-163">![Specify Remote Syslog details](media/ArcSightS1Syslog.png)</span></span>
  
9. <span data-ttu-id="47526-164">ステップでは、**データ型**、次のいずれかを実行し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47526-164">In the **Data Types** step, do one of the following, and then click **Next**:</span></span>
    - <span data-ttu-id="47526-165">**すべてのアラート**の既定の設定をしてください。</span><span class="sxs-lookup"><span data-stu-id="47526-165">Keep the default setting of **All Alerts**</span></span></br><span data-ttu-id="47526-166">OR</span><span class="sxs-lookup"><span data-stu-id="47526-166">OR</span></span>
    - <span data-ttu-id="47526-p111">**すべてのアラート**をクリックし、[**特定のフィルター**を選択します。SIEM サーバーに送信するアラートの種類を選択するためのフィルターを定義します。</span><span class="sxs-lookup"><span data-stu-id="47526-p111">Click **All alerts**, and then choose **Specific filters**. Define filters to select the kinds of alerts you want to send to your SIEM server. </span></span></br><span data-ttu-id="47526-169">![ウィザードのデータの種類の手順](media/ArcSightS1ExportOptions.png)</span><span class="sxs-lookup"><span data-stu-id="47526-169">![Data Types step of the wizard](media/ArcSightS1ExportOptions.png)</span></span>
  
10. <span data-ttu-id="47526-170">[おめでとうございます] 画面で、トークンをコピーし、後にします。</span><span class="sxs-lookup"><span data-stu-id="47526-170">On the Congratulations screen, copy the token and save it for later.</span></span></br>![SIEM のエージェントの作成] 画面](media/SIEMAgentFinished.png) 

> [!IMPORTANT]
> <span data-ttu-id="47526-p112">この時点で、Office 365 クラウド アプリケーションのセキュリティで、SIEM のエージェントを設定しているが、SIEM のサーバの統合がまだ完了していません。SIEM のサーバの統合を続行するのには次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="47526-p112">At this point, you have set up a SIEM agent in Office 365 Cloud App Security, but your SIEM server integration is not yet finished. Proceed to the next step to continue your SIEM server integration.</span></span>

<span data-ttu-id="47526-p113">[閉じる] をクリックし、セキュリティ拡張機能の画面上に、ウィザードを終了すると、テーブルに追加する SIEM エージェントを表示できます。後で接続されていることになるまで**作成済**] ステータスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47526-p113">After you click Close and leave the wizard, on the Security extensions screen, you can see the SIEM agent you added in the table. It will show a status of **Created** until it's connected later.</span></span>

![SIEM エージェントの作成](media/SIEMAgentCreated.png)
    
### <a name="step-2-download-the-jar-file-and-run-it-on-your-server"></a><span data-ttu-id="47526-177">手順 2: の JAR ファイルをダウンロードし、サーバーで実行します。</span><span class="sxs-lookup"><span data-stu-id="47526-177">Step 2: Download the JAR file and run it on your server</span></span>

1. <span data-ttu-id="47526-p114">[マイクロソフト クラウド アプリケーションのセキュリティの SIEM エージェント](https://go.microsoft.com/fwlink/?linkid=838596)をダウンロードして、フォルダーに解凍します。[(する必要がありますソフトウェア ライセンス条項](https://go.microsoft.com/fwlink/?linkid=862491)に同意先に進む。)</span><span class="sxs-lookup"><span data-stu-id="47526-p114">Download the [Microsoft Cloud App Security SIEM Agent](https://go.microsoft.com/fwlink/?linkid=838596) and unzip the folder. (You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) in order to proceed.)</span></span> 
    
2. <span data-ttu-id="47526-180">.Jar ファイルを zip 形式のフォルダーから抽出し、サーバー上で実行します。</span><span class="sxs-lookup"><span data-stu-id="47526-180">Extract the .jar file from the zipped folder and run it on your server.</span></span>
    
3. <span data-ttu-id="47526-181">ファイルを実行すると、次の実行: コマンド。</span><span class="sxs-lookup"><span data-stu-id="47526-181">After running the file, run the following: command:</span></span></br>
  ```
  java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
  ```
#### <a name="important-notes"></a><span data-ttu-id="47526-182">重要事項</span><span class="sxs-lookup"><span data-stu-id="47526-182">Important notes</span></span>

- <span data-ttu-id="47526-183">SIEM エージェントのバージョンによってファイル名が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="47526-183">The file name may differ depending on the version of the SIEM agent.</span></span> 

- <span data-ttu-id="47526-184">サーバーのセットアップ中に、サーバー上で、JAR の塗りつぶしを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="47526-184">We recommend that you run the JAR fill on your server during server setup.</span></span>
    - <span data-ttu-id="47526-185">**Windows**:**ユーザーがログオンしているかどうかどうかを実行**するタスクを設定し**より長い場合にタスクを停止する**オプションをオフにすることを確認、スケジュールされたタスクとして実行します。</span><span class="sxs-lookup"><span data-stu-id="47526-185">**Windows**: Run as a scheduled task, making sure to configure the task to **Run whether the user is logged on or not** and clear the **Stop the task if it runs longer than** option.</span></span>

    - <span data-ttu-id="47526-186">**Linux**: を指定して実行コマンドを追加、**&** に、`rc.local`ファイルです。</span><span class="sxs-lookup"><span data-stu-id="47526-186">**Linux**: Add the run command with an **&** to the `rc.local` file.</span></span> </br><span data-ttu-id="47526-187">例:</span><span class="sxs-lookup"><span data-stu-id="47526-187">Example:</span></span></br> 
    ```
    java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &
    ```

- <span data-ttu-id="47526-p115">括弧内のパラメーターはオプションであり、該当する場合にのみ使用する必要があります。次の変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="47526-p115">Parameters in brackets [] are optional, and should be used only if relevant. Use the following variables:</span></span>
    - <span data-ttu-id="47526-190">**DIRNAME**は、デバッグ ログのローカル エージェントを使用するディレクトリへのパスです。</span><span class="sxs-lookup"><span data-stu-id="47526-190">**DIRNAME** is the path to the directory you want to use for local agent debug logs.</span></span>
    - <span data-ttu-id="47526-191">**アドレス [: ポート]** は、プロキシ サーバーのアドレスと、インターネットに接続するサーバーを使用するポートです。</span><span class="sxs-lookup"><span data-stu-id="47526-191">**ADDRESS[:PORT]** is the proxy server address and port that the server uses to connect to the Internet.</span></span>
    - <span data-ttu-id="47526-192">**トークン**は、最初の手順でコピーした SIEM エージェントのトークンです。</span><span class="sxs-lookup"><span data-stu-id="47526-192">**TOKEN** is the SIEM agent token you copied in the first procedure.</span></span>
    - <span data-ttu-id="47526-193">ヘルプを表示するには、次のように入力します。 `-h`。</span><span class="sxs-lookup"><span data-stu-id="47526-193">To get help, type `-h`.</span></span> 
  
### <a name="step-3-validate-that-the-siem-agent-is-working"></a><span data-ttu-id="47526-194">手順 3: SIEM エージェントが動作していることを検証します。</span><span class="sxs-lookup"><span data-stu-id="47526-194">Step 3: Validate that the SIEM agent is working</span></span>

1. <span data-ttu-id="47526-195">**接続エラー**と Office 365 のクラウド アプリケーションのセキュリティ関連ポータルの SIEM のエージェントの状態が設定されていないエージェントの通知がない**切断**していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="47526-195">Make sure the status of the SIEM agent in the Office 365 Cloud App Security portal is not displayed as **Connection error** or **Disconnected** and that there are no agent notifications.</span></span></br><span data-ttu-id="47526-196">たとえば、ご覧の SIEM サーバーが接続されています。</span><span class="sxs-lookup"><span data-stu-id="47526-196">For example, here we can see the SIEM server is connected:</span></span></br><span data-ttu-id="47526-197">![SIEM サーバーが接続されています。](media/siem-connected.png)</span><span class="sxs-lookup"><span data-stu-id="47526-197">![SIEM server connected](media/siem-connected.png)</span></span></br><span data-ttu-id="47526-198">ご覧の SIEM サーバー接続を切断します。</span><span class="sxs-lookup"><span data-stu-id="47526-198">And here, we can see the SIEM server is disconnected:</span></span></br><span data-ttu-id="47526-199">![SIEM サーバーが接続されていません](media/siem-not-connected.png)</span><span class="sxs-lookup"><span data-stu-id="47526-199">![SIEM server not connected](media/siem-not-connected.png)</span></span> 
  
2. <span data-ttu-id="47526-200">/SIEM の Syslog サーバーに Office 365 のクラウド アプリケーションのセキュリティの警告が届きましたと表示になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="47526-200">In your Syslog/SIEM server, make sure you see that alerts have arrived from Office 365 Cloud App Security.</span></span>
  
## <a name="regenerating-your-token"></a><span data-ttu-id="47526-201">ユーザーのトークンを再生成します。</span><span class="sxs-lookup"><span data-stu-id="47526-201">Regenerating your token</span></span>

<span data-ttu-id="47526-p116">ユーザーのトークンを紛失した場合常に再生できます。テーブルでは、SIEM エージェントの行を探します。、省略記号をクリックし、**トークンを再生成**します。</span><span class="sxs-lookup"><span data-stu-id="47526-p116">If you lose your token, you can always regenerate it. In the table, locate the row for the SIEM agent. Click the ellipses, and then choose **Regenerate token**.</span></span>

![SIEM エージェントの省略記号ボタンをクリックすると、トークンを再生成します。](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)
  
## <a name="editing-your-siem-agent"></a><span data-ttu-id="47526-206">SIEM エージェントを編集します。</span><span class="sxs-lookup"><span data-stu-id="47526-206">Editing your SIEM agent</span></span>

<span data-ttu-id="47526-p117">SIEM を編集するのには、エージェントのテーブルの SIEM エージェントの行を探します。、省略記号をクリックし、し、[**編集**] をクリックします。SIEM エージェントを編集する場合は、.jar ファイルを再実行する必要はありません。自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="47526-p117">To edit your SIEM agent, in the table, locate the row for the SIEM agent. Click the ellipses, and then choose **Edit**. If you edit the SIEM agent, you do not need to re-run the .jar file; it updates automatically.</span></span>

![SIEM エージェントを編集するのには、2 つの楕円を選択し、[編集します。](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)
  
## <a name="deleting-your-siem-agent"></a><span data-ttu-id="47526-211">SIEM のエージェントを削除します。</span><span class="sxs-lookup"><span data-stu-id="47526-211">Deleting your SIEM agent</span></span>

<span data-ttu-id="47526-p118">テーブルで、SIEM エージェントを削除するには、SIEM エージェントの行を探します。、省略記号をクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47526-p118">To delete your SIEM agent, in the table, locate the row for the SIEM agent. Click the ellipses, and then choose **Delete**.</span></span>

![SIEM エージェントを削除するのには、2 つの楕円を選択し、削除」を選択し、します。](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)

## <a name="sample-logfiles"></a><span data-ttu-id="47526-215">サンプル ログ ファイル</span><span class="sxs-lookup"><span data-stu-id="47526-215">Sample logfiles</span></span>

<span data-ttu-id="47526-216">SIEM のサーバーに送信される可能性があります警告ログ ファイルの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="47526-216">Here's an alerts logfile example that might be sent to a SIEM server:</span></span>

```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```

<span data-ttu-id="47526-217">CEF の形式の例は、</span><span class="sxs-lookup"><span data-stu-id="47526-217">And here's a sample in CEF format</span></span>


|<span data-ttu-id="47526-218">CEF のフィールド名</span><span class="sxs-lookup"><span data-stu-id="47526-218">CEF field name</span></span>  | <span data-ttu-id="47526-219">説明</span><span class="sxs-lookup"><span data-stu-id="47526-219">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="47526-220">開始</span><span class="sxs-lookup"><span data-stu-id="47526-220">start</span></span>     | <span data-ttu-id="47526-221">アラートのタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="47526-221">alert timestamp</span></span>        |
|<span data-ttu-id="47526-222">終わり</span><span class="sxs-lookup"><span data-stu-id="47526-222">end</span></span>     | <span data-ttu-id="47526-223">アラートのタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="47526-223">alert timestamp</span></span>        |
|<span data-ttu-id="47526-224">rt</span><span class="sxs-lookup"><span data-stu-id="47526-224">rt</span></span>     | <span data-ttu-id="47526-225">アラートのタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="47526-225">alert timestamp</span></span>        |
|<span data-ttu-id="47526-226">msg</span><span class="sxs-lookup"><span data-stu-id="47526-226">msg</span></span>     | <span data-ttu-id="47526-227">Office 365 のクラウド アプリケーションのセキュリティ関連ポータルに示すようにアラートの説明</span><span class="sxs-lookup"><span data-stu-id="47526-227">alert description as shown in the Office 365 Cloud App Security portal</span></span>        |
|<span data-ttu-id="47526-228">suser</span><span class="sxs-lookup"><span data-stu-id="47526-228">suser</span></span>     | <span data-ttu-id="47526-229">警告の対象ユーザー</span><span class="sxs-lookup"><span data-stu-id="47526-229">alert subject user</span></span>        |
|<span data-ttu-id="47526-230">destinationServiceName</span><span class="sxs-lookup"><span data-stu-id="47526-230">destinationServiceName</span></span>     | <span data-ttu-id="47526-231">元のアプリケーションでは、Office 365、SharePoint、または OneDrive などの警告</span><span class="sxs-lookup"><span data-stu-id="47526-231">alert originating app, such as Office 365, SharePoint, or OneDrive</span></span>        |
|<span data-ttu-id="47526-232">csLabel</span><span class="sxs-lookup"><span data-stu-id="47526-232">csLabel</span></span>     | <span data-ttu-id="47526-p119">異なります (ラベルでは、さまざまな意味を持っています)。通常、ラベルは、自明ですが、targetObjects のようにします。</span><span class="sxs-lookup"><span data-stu-id="47526-p119">Varies (labels have different meanings). Typically, labels are self-explanatory, like targetObjects.</span></span>        |
|<span data-ttu-id="47526-235">cs</span><span class="sxs-lookup"><span data-stu-id="47526-235">cs</span></span>     | <span data-ttu-id="47526-236">ラベル (ラベルの例に従って、アラートの対象ユーザー) などに対応する情報</span><span class="sxs-lookup"><span data-stu-id="47526-236">Information corresponding to a label (such as the target user of an alert as per the label example)</span></span>        |
  
## <a name="next-steps"></a><span data-ttu-id="47526-237">次の手順</span><span class="sxs-lookup"><span data-stu-id="47526-237">Next steps</span></span>

- [<span data-ttu-id="47526-238">Office 365 Cloud App Security 展開後の利用に関する作業</span><span class="sxs-lookup"><span data-stu-id="47526-238">Utilization activities after rolling out Office 365 Cloud App Security</span></span>](utilization-activities-for-ocas.md)
    
- [<span data-ttu-id="47526-239">確認し、アラート アクションを実行</span><span class="sxs-lookup"><span data-stu-id="47526-239">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="47526-240">管理を簡略化する IP アドレスをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="47526-240">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

