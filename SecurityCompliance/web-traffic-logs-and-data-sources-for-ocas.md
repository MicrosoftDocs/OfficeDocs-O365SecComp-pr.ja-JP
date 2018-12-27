---
title: Office 365 Cloud App Security の Web トラフィック ログとデータ ソース
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 290b02bf-a988-4fb9-88b2-34e408216ac8
description: Office 365 クラウド アプリケーションのセキュリティは、プロバイダーのさまざまな web トラフィックのログを使用して動作します。Web トラフィックのログの詳細については、この資料を参照し、Office 365 のクラウド アプリケーションのセキュリティをデータ ソースをサポートします。
ms.openlocfilehash: ab962e4a030d06c133ad9fc4aa62a60755793bc3
ms.sourcegitcommit: 25f72d20e76463c2f0a075dfc0116f00c934bd77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/27/2018
ms.locfileid: "27447055"
---
# <a name="web-traffic-logs-and-data-sources-for-office-365-cloud-app-security"></a>Office 365 Cloud App Security の Web トラフィック ログとデータ ソース
  
|評価 * *\>**|計画 * *\>**|配置 * *\>**|使用率。|
|:-----|:-----|:-----|:-----|
|[評価を開始します。](office-365-cas-overview.md) <br/> |[計画の開始します。](get-ready-for-office-365-cas.md) <br/> |[展開を開始します。](turn-on-office-365-cas.md) <br/> |コースです!  <br/> [次の手順](#next-steps) <br/> |
  
Office 365 のクラウド アプリケーションのセキュリティでは、web トラフィックのログ ファイルとデータ ソースのさまざまなを使用できます。ただし、web トラフィックのログ ファイルは、特定の情報を含める必要があります、Office 365 のクラウド アプリケーションのセキュリティ アプリケーションの検出のレポートとクラウドの探索のダッシュ ボードでは動作するように、特定の方法を書式設定します。Web トラフィックのログと Office 365 のクラウド アプリケーションのセキュリティを使用するデータ ソースのリファレンス ・ ガイドとしてこの資料を使用します。
  
> [!NOTE]
> セキュリティにアクセスするグローバル管理者、セキュリティ管理者、またはセキュリティのリーダーにする必要があります&amp;コンプライアンス センターと Office 365 のクラウド アプリケーションのセキュリティのポータルです。参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。 
  
## <a name="web-traffic-log-requirements"></a>Web トラフィックのログの要件

組織のユーザーがどのアプリケーションを理解するために、web トラフィックのログに office 365 のクラウド アプリケーションのセキュリティはデータを使用しています。詳細についてを正しく把握する必要がありますユーザーの利用状況のログ ファイルに含まれています。
  
次のセクションでは、Office 365 のクラウド アプリケーションのセキュリティと正常に動作する web トラフィック ログ用の追加の要件と必要な属性を一覧表示します。

### <a name="attributes"></a>属性

Office 365 クラウド アプリケーションのセキュリティを表示またはできません、web トラフィックのログに含まれていない属性を分析します。たとえば、Cisco ASA ファイアウォールの標準的なログ形式には、トランザクション、ユーザー名、またはターゲットの URL (ターゲット IP のみ) ごとのアップロードされたバイト数はありません。したがって、クラウドの探索データには、これらの属性は表示されていないし、クラウド アプリケーションの可視性は制限されます。Cisco ASA ファイアウォールについては、情報のレベルを 6 に設定する必要があります。 

Web のトラフィックのログは、次の属性を含める必要があります。

- トランザクションの日付
- 発信元 IP アドレス
- 移動元のユーザーが (強く推奨)
- 宛先 IP アドレス
- リンク先の URL (お勧めします。Url では、IP アドレスよりもクラウド アプリケーションの検出の精度を上げるを提供)
- データの総容量 (推奨されるデータの情報は非常に貴重な)。
- 量がアップロードまたはダウンロードされたデータ (推奨されるクラウドに関する洞察アプリケーションの使用パターンが用意されています)。
- (許可またはブロック) を実行するアクション

### <a name="additional-requirements"></a>追加要件 

この資料に記載されている属性を含む、他の web トラフィックのログは次の要件を満たす必要があります。

- ログ ファイルのデータ ソースをサポートする必要があります。
- ログ ファイルを使用する形式は、標準形式に一致しなければなりません。ファイルがアップロードされると、アプリケーションの検出はこれを確認します。
- ログにする必要があります発生したイベントは 90 日前です。
- ログ ファイルは、送信トラフィックについては、ネットワークの動作を分析することができますを含める必要があります。
  
## <a name="data-attributes-for-different-vendors"></a>さまざまなベンダーのデータ属性

次の表は、さまざまなベンダーの web トラフィックのログの情報をまとめたものです。**の最新情報については、ベンダーに確認してください**。


|                 データ ソース                  |    ターゲット アプリケーションの URL    |    対象アプリケーションの ip アドレス     |       ユーザー名       |      送信元 IP       |    トラフィックの合計     |    アップロードされたバイト数    |
|----------------------------------------------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|
|                  Barracuda                   | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |          ×          |          いいえ          |
|                  ブルー コート                   | <strong>○</strong> |          ×          | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                  チェックポイント                  |          いいえ          | <strong>○</strong> |          ×          | <strong>○</strong> |          ×          |          いいえ          |
|              Cisco ASA (Syslog)              |          いいえ          | <strong>○</strong> |          ×          | <strong>○</strong> | <strong>○</strong> |          ×          |
|           Cisco ASA 火力に           | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                  Cisco FWSM                  |          いいえ          | <strong>○</strong> |          ×          | <strong>○</strong> | <strong>○</strong> |          ×          |
|              Cisco Ironport WSA              | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                 Cisco Meraki                 | <strong>○</strong> | <strong>○</strong> |          ×          | <strong>○</strong> |          ×          |          いいえ          |
|           Clavister NGFW (Syslog)            | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                SonicWall (以前は Dell)                | <strong>○</strong> | <strong>○</strong> |          ×          | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|            デジタル アート i フィルター             | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                  Fortigate                   |          いいえ          | <strong>○</strong> |          ×          | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                 ビャクシン SRX                  |          いいえ          | <strong>○</strong> |          ×          | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                 ビャクシン SSG                  |          いいえ          | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                  McAfee SWG                  | <strong>○</strong> |          ×          |          いいえ          | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                    MS TMG                    | <strong>○</strong> |          ×          | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|              パロアルト ネットワーク              |          いいえ          | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                    Sophos                    | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |          ×          |
|                Squid (共通)                | <strong>○</strong> |          ×          | <strong>○</strong> | <strong>○</strong> |          ×          | <strong>○</strong> |
|                Squid (ネイティブ)                | <strong>○</strong> |          ×          | <strong>○</strong> | <strong>○</strong> |          ×          | <strong>○</strong> |
| Websense の調査の詳細レポート (CSV) | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|    Websense ・ インターネット ・ アクティビティ ・ ログ (CEF)    | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                   Zscaler                    | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
   
## <a name="supported-vendor-firewalls-and-proxies"></a>サポートされているベンダーのファイアウォールとプロキシ

Office 365 のクラウド アプリケーションのセキュリティには、次のファイアウォールやプロキシがサポートしています。
  
- Barracuda の Web アプリケーション ファイアウォール (W3C)  
- 青コートのプロキシ アクセスのログ (W3C) のストレージ ・ グループ
- チェック ポイント
- Cisco ASA ファイアウォール (情報のレベルを 6 に設定するのにしてください)
- Cisco ASA 火力に   
- Cisco IronPort WSA
- Cisco ScanSafe
- Cisco Merkai の Url のログ
- Clavister NGFW (Syslog)
- デジタル アート i フィルター
- Fortinet Fortigate
- iboss クラウド ゲートウェイのセキュリティで保護されました。
- ビャクシン SRX
- ビャクシン SSG
- McAfee のセキュリティで保護された Web ゲートウェイ
- Microsoft Forefront 脅威管理ゲートウェイ (W3C)
- パロアルト シリーズ ファイアウォール
- Sonicwall (以前は Dell)   
- Sophos SG
- Sophos XG
- Sophos Cyberoam
- Squid (共通)
- Squid (ネイティブ)
- Websense の Web セキュリティ ソリューションの調査の詳細レポート (CSV)
- Websense - Web セキュリティ ・ ソリューション ・ インターネット ・ アクティビティ ・ ログ (CEF)
- Zscaler
    
> [!NOTE]
> データ ソースを使用するには含まれていない場合は、ここでは、アプリケーションの検出に追加することを要求できます。レポートを作成する場合、[**その他**の**データ ソース**です。アップロードしようとしているデータ ソースの名前を入力します。ログを確認し、そのログの種類に対するサポートを追加して確認することはします。または、[カスタム パーサーを定義](https://docs.microsoft.com/cloud-app-security/custom-log-parser)の形式に一致することができます。 
  
## <a name="troubleshoot-errors-when-log-files-are-uploaded"></a>ログ ファイルをアップロードするとエラーをトラブルシューティングします。

Web トラフィックのログ ファイルをアップロードした後、エラーが発生したかどうかの管理ログを確認してください。エラーがある場合は、これらのエラーを解決するのには次の表に情報を使用します。
  
|**エラー**|**説明**|**解決法**|
|:-----|:-----|:-----|
|サポートされていないファイルの種類  <br/> |アップロードされたファイルは、ログ ファイルが有効ではありません。たとえば、イメージのファイルです。  <br/> |テキスト、郵便番号、または、ファイアウォールまたはプロキシから直接エクスポートされた gzip ファイルをアップロードします。  <br/> |
|内部エラー  <br/> |内部リソース エラーが検出されました。  <br/> |タスクを再実行するのには**再試行**をクリックします。  <br/> |
|ログの形式が一致しません  <br/> |アップロードしたログ形式では、このデータ ソースに必要なログの形式が一致しません。  <br/> |
ログが壊れていないことを確認します。比較し、[アップロード] ページで、サンプルの形式のログ ファイルの形式に一致します。 |
|トランザクションは、90 日以上経過  <br/> |すべてのトランザクションは、90 日以上経過で無視されているためです。  <br/> |最近のイベントで新しいログをエクスポートし、再度アップロードします。  <br/> |
|クラウド アプリケーションのカタログには、トランザクション  <br/> |ログに、認識されたクラウド アプリケーションにトランザクションが見つかりません。  <br/> |送信トラフィックの情報がログに含まれていることを確認します。  <br/> |
|サポートされていないログの種類  <br/> |選択すると**データ ソースその他の (サポートされていない) =**、ログを解析できません。代わりに、[マイクロソフトのクラウド アプリケーションのセキュリティ](https://aka.ms/whatiscas)技術チームに確認のために送られます。<br/> |[マイクロソフト クラウド アプリケーションのセキュリティ](https://aka.ms/whatiscas)技術チームは、データ ソースごとに専用のパーサーを作成します。最も人気のあるデータ ソースが既にサポートされています。サポートされていないデータ ソースがアップロードされると、確認および、潜在的な新しいデータ ソースのパーサーの一覧に追加します。<br/> 新しいパーサーをフィーチャーに追加すると、通知がマイクロソフトのクラウド アプリケーションのセキュリティのリリース ノートに含まれます。  <br/> |
   
## <a name="next-steps"></a>次の手順

- [確認し、アラート アクションを実行](review-office-365-cas-alerts.md)
    
- [アプリケーション検出レポートを作成します。](create-app-discovery-reports-in-ocas.md)
    
- [アプリケーションの検出結果を確認します。](review-app-discovery-findings-in-ocas.md)
    
- [Office 365 のクラウド アプリケーションのセキュリティの使用率のアクティビティを確認します。](utilization-activities-for-ocas.md)
    

