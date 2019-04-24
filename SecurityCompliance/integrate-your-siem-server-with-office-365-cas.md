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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254773"
---
# <a name="integrate-your-siem-server-with-office-365-cloud-app-security"></a>SIEM サーバーと Office 365 Cloud App Security を統合する
  
|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|[評価の開始](office-365-cas-overview.md) <br/> |[計画を開始する](get-ready-for-office-365-cas.md) <br/> |ここでは、  <br/> [次の手順](utilization-activities-for-ocas.md) <br/> |[利用を開始する](utilization-activities-for-ocas.md) <br/> |
   
## <a name="overview-and-prerequisites"></a>概要と前提条件

[Office 365 Cloud App security](get-ready-for-office-365-cas.md)をセキュリティ情報およびイベント管理 (SIEM) サーバーと統合して、アラートの集中監視を有効にすることができます。 これは、クラウドサービスとオンプレミスのサーバーアプリケーションを使用している組織に特に便利です。 SIEM サーバーを統合して、Office 365 Cloud App Security から SIEM サーバーに通知とアクティビティを取得することができます。 SIEM サーバーとの統合により、セキュリティチームは、通常のセキュリティワークフローを維持しながら、特定のセキュリティの手順を自動化し、クラウドベースのイベントとオンプレミスのイベントを関連付けることにより、Office 365 アプリケーションをより適切に保護することができます。  
  
最初に SIEM サーバーを Office 365 Cloud App Security と統合すると、過去2日以内の通知が SIEM サーバーに転送されます。さらに、選択したフィルターに基づいて、その後のすべての通知が送信されます。 さらに、この機能を長期に対して無効にした場合、再度有効にすると、過去2日間の通知を転送した後、その後にすべての通知が送信されます。

### <a name="siem-integration-architecture"></a>SIEM 統合アーキテクチャ

組織のネットワークに SIEM エージェントが設定されている。 SIEM エージェントは、を展開して構成すると、Office 365 Cloud App Security RESTful api を使用して構成されたデータ型 (警告) を取得します。 その後、トラフィックはポート443上の暗号化された HTTPS チャネルを介して送信されます。
  
SIEM エージェントは、Office 365 Cloud App Security からデータを取得するときに、セットアップ時に提供されたネットワーク構成 (カスタムポートを使用する TCP または UDP) を使用して、Syslog メッセージをローカルの SIEM サーバーに送信します。

![SIEM および Cloud App Security architecture](media/siem-architecture.png)

### <a name="supported-siem-servers"></a>サポートされている SIEM サーバー

Office 365 Cloud App Security は現在、次の SIEM サーバーをサポートしています。
- マイクロフォーカスの arcsight
- 汎用 cef

### <a name="prerequisites"></a>前提条件

- この記事で説明されているタスクを実行するには、全体管理者またはセキュリティ管理者である必要があります。 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可を参照する](permissions-in-the-security-and-compliance-center.md)

- 組織に対し[て Office 365 Cloud App Security が有効になっ](turn-on-office-365-cas.md)ている必要があります。

- Office 365 の[監査ログ](turn-audit-log-search-on-or-off.md)を有効にする必要があります。

- SIEM サーバーの統合を構成するためには、次の要件を満たす標準サーバーが必要です。
    - OS: Windows または Linux (仮想マシンの場合があります)
    - CPU: 2
    - ディスク容量:20 GB
    - RAM: 2 GB
    - [Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html)のインストール
    - 「[ネットワーク要件](https://docs.microsoft.com/cloud-app-security/network-requirements)」の説明に従って構成されたファイアウォール

- **リモート syslog ホスト**および**syslot ポート番号**についての詳細を確認する必要があります。 ネットワーク管理者またはセキュリティ管理者は、その情報を検索できるようにする必要があります。 

- SIEM サーバーを統合するために必要な[JAR ファイル](https://go.microsoft.com/fwlink/?linkid=838596)をダウンロードするには、[ソフトウェアライセンス条項](https://go.microsoft.com/fwlink/?linkid=862491)に同意する必要があります。
 
## <a name="step-1-set-it-up-a-siem-agent-in-office-365-cloud-app-security"></a>手順 1: Office 365 Cloud App Security で SIEM エージェントをセットアップする

1. Cloud App Security ポータル ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) に移動し、サインインします。
  
2. [**設定** \> ] [**セキュリティ拡張機能**] をクリックし、[SIEM エージェント] を選択します。<br/>
![設定 > のセキュリティ拡張機能を選択する](media/Settings-SecurityExtensions.png)

3. [ **Add SIEM agent**] を選びます。<br/>![[Add SIEM agent] を選びます。](media/SIEMAgents.png)
    
4. [**ウィザードの開始**] を選択します。<br/>![ヘルプを表示する、またはウィザードを開始する](media/HelpOrWizard.png) 
    
5. **一般的**な手順で、名前を指定し、 **SIEM 形式を選択**して、その形式に関連する**詳細設定**を設定します。 [**次へ**] を選択します。<br/>![名前と種類を指定する](media/ChooseAgentTypeAndName.png)
    
6. syslog の**リモート**ステップで、**リモート syslog ホスト**の IP アドレスまたはホスト名と**syslog ポート番号**を指定します。 リモート Syslog プロトコルとして TCP または UDP を選択します。 (必要な場合は、ネットワーク管理者またはセキュリティ管理者と協力して、これらの詳細を取得することができます)。[**次へ**] を選択します。<br/>![リモート Syslog の詳細を指定する](media/ArcSightS1Syslog.png)
  
7. [**データ型**] ステップで、次のいずれかの操作を行い、[**次へ**] をクリックします。
    - **すべての通知**の既定の設定を保持する<br/>OR
    - [**すべての通知**] をクリックし、[**特定のフィルター**] を選択します。 SIEM サーバーに送信する通知の種類を選択するためのフィルターを定義します。
<br/>![ウィザードの [データ型] の手順](media/ArcSightS1ExportOptions.png)
  
8. [完了] 画面で、トークンをコピーし、後で保存します。<br/>![SIEM エージェント作成画面](media/SIEMAgentFinished.png) 

> [!IMPORTANT]
> この時点で、Office 365 Cloud App Security で SIEM エージェントをセットアップしましたが、SIEM サーバーの統合はまだ完了していません。 次の手順に進んで、SIEM サーバーの統合を続行します。

[閉じる] をクリックしてウィザードを終了すると、[セキュリティ拡張機能] 画面に、表に追加した SIEM エージェントが表示されます。 後で接続されるまで、[**作成済み**] の状態が表示されます。

![SIEM エージェントの作成](media/SIEMAgentCreated.png)
    
## <a name="step-2-download-a-jar-file-and-run-it-on-your-siem-server"></a>手順 2: JAR ファイルをダウンロードして、SIEM サーバー上で実行する

1. [Microsoft Cloud App Security SIEM エージェント](https://go.microsoft.com/fwlink/?linkid=838596)をダウンロードし、フォルダーを解凍します。 (続行するには、[ソフトウェアライセンス条項](https://go.microsoft.com/fwlink/?linkid=862491)に同意する必要があります)。 
    
2. zip フォルダーから .jar ファイルを抽出し、SIEM サーバー上で実行します。
    
3. ファイルを実行した後、次のコマンドを実行します。<br/>
  ```
  java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
  ```
### <a name="important-notes"></a>重要事項

- ファイル名は、SIEM エージェントのバージョンによって異なる場合があります。 

- サーバーのセットアップ時に、SIEM サーバー上で JAR ファイルを実行することをお勧めします。

    - **Windows**: スケジュールされたタスクとして実行し、**ユーザーがログオンしているかどうか**を確認し、[**タスクの実行**時間が次の値を超えた場合は停止する] チェックボックスをオフにします。

    - **Linux**: **&** `rc.local`ファイルにを含む run コマンドを追加します。 <br/>例:<br/> 
    ```
    java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &
    ```

- 角かっこで囲まれたパラメーターはオプションであり、関連する場合にのみ使用してください。 次の変数を使用します。

    - **DIRNAME**は、ローカルエージェントのデバッグログに使用するディレクトリへのパスです。

    - **ADDRESS [:P ort]** は、サーバーがインターネットに接続するために使用するプロキシサーバーのアドレスおよびポートです。

    - **TOKEN**は、最初の手順でコピーした SIEM エージェントトークンです。

    - ヘルプを表示するに`-h`は、「」と入力します。 
  
## <a name="step-3-validate-that-the-siem-agent-is-working"></a>手順 3: SIEM エージェントが動作していることを検証する

1. Office 365 Cloud App Security portal の SIEM エージェントの状態が、**接続エラー**または**切断**されていないこと、およびエージェントの通知がないことを確認します。<br/>たとえば、次のように、SIEM サーバーが接続されていることを確認できます。<br/>![SIEM サーバーの接続](media/siem-connected.png)<br/>ここでは、SIEM サーバーが切断されています。<br/>![SIEM サーバーが接続されていません](media/siem-not-connected.png) 
  
2. Syslog/SIEM サーバーで、通知が Office 365 Cloud App Security から届いていることを確認してください。
  
## <a name="what-the-logfiles-look-like"></a>ログの内容は次のようになります。

SIEM サーバーに送信される可能性のある警告ログファイルの例を次に示します。

```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```

もう1つの例を次に示します。この時間は、cef 形式です。


|cef フィールド名  | 説明  |
|---------|---------|
|開始     | アラートのタイムスタンプ        |
|end     | アラートのタイムスタンプ        |
|rt     | アラートのタイムスタンプ        |
|msg     | Office 365 Cloud App Security ポータルに表示されるアラートの説明        |
|suser     | 通知対象ユーザー        |
|destinationservicename     | Office 365、SharePoint、OneDrive などの通知元アプリ        |
|cslabel     | (ラベルの意味は異なります)。 通常、ラベルは targetObjects のように、わかりやすいように記述されています。        |
|cs     | ラベルに対応する情報 (ラベルの例に従って通知を行う対象ユーザーなど)        |

## <a name="additional-tasks-as-needed"></a>その他のタスク (必要な場合)

SIEM サーバーを構成し、それを Office 365 Cloud App Security と統合した後で、トークンの再生成、SIEM エージェントの編集、または SIEM エージェントの削除が必要になる場合があります。 次のセクションでは、これらのタスクを実行する方法について説明します。

### <a name="regenerate-a-token"></a>トークンの再生成

トークンを紛失した場合は1つを再生成できます。 

1. [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)Office 365 Cloud App Security ポータル () で、[**設定** > ] [**セキュリティ拡張機能**] を選択します。

2. 表で、SIEM エージェントの行を見つけます。 

3. 省略記号をクリックし、[**トークンの再生成**] を選択します。<br/>![SIEM エージェントの省略記号をクリックしてトークンを再生成する](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)
  
### <a name="edit-a-siem-agent"></a>SIEM エージェントを編集する

1. [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)Office 365 Cloud App Security ポータル () で、[**設定** > ] [**セキュリティ拡張機能**] を選択します。

2. SIEM エージェントの行を見つけます。 

3. 省略記号をクリックしてから、[**編集**] を選択します。 (SIEM エージェントを編集する場合は、.jar ファイルを再実行する必要はありませんが、自動的に更新されます)。 <br/>![SIEM エージェントを編集するには、省略記号を選択してから、[編集] を選択します。](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)
  
### <a name="delete-a-siem-agent"></a>SIEM エージェントを削除する

1. [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)Office 365 Cloud App Security ポータル () で、[**設定** > ] [**セキュリティ拡張機能**] を選択します。

2. SIEM エージェントの行を見つけます。 

3. 省略記号をクリックし、[**削除**] を選択します。<br/>![SIEM エージェントを削除するには、省略記号を選択してから、[削除] を選択します。](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)

  
## <a name="next-steps"></a>次のステップ

- [Office 365 Cloud App Security 展開後の利用に関する作業](utilization-activities-for-ocas.md)
    
- [通知を確認して処理を実行する](review-office-365-cas-alerts.md)
    
- [IP アドレスをグループ化して管理を簡素化する](group-your-ip-addresses-in-ocas.md)
    

