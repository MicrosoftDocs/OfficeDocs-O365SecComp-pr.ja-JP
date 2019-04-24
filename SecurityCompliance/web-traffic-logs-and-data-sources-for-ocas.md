---
title: Office 365 Cloud App Security の ウェブ トラフィック ログとデータ ソース
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 290b02bf-a988-4fb9-88b2-34e408216ac8
description: Office 365 Cloud App Security はさまざまなプロバイダーからの web トラフィックログを使用して動作します。 この記事では、Office 365 Cloud App Security での web トラフィックログおよびサポートされているデータソースについて説明します。
ms.openlocfilehash: 67246ded0e3d39c81b5b906f753b91298309d1d8
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266852"
---
# <a name="web-traffic-logs-and-data-sources-for-office-365-cloud-app-security"></a>Office 365 Cloud App Security の ウェブ トラフィック ログとデータ ソース
  
|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|[評価の開始](office-365-cas-overview.md) <br/> |[計画を開始する](get-ready-for-office-365-cas.md) <br/> |[展開を開始する](turn-on-office-365-cas.md) <br/> |ここでは、  <br/> [次の手順](#next-steps) <br/> |
  
Office 365 Cloud App Security では、さまざまな web トラフィックログファイルとデータソースを使用できます。 ただし、web トラフィックログファイルには特定の情報が含まれている必要があり、Office 365 cloud app Security App discovery reports および Cloud discovery dashboard で機能するように特定の方法でフォーマットする必要があります。 この記事は、Office 365 Cloud App Security で使用する web トラフィックログおよびデータソースのリファレンスガイドとしてご利用ください。
  
> [!NOTE]
> セキュリティ&amp; /コンプライアンスセンターおよび Office 365 Cloud App security portal にアクセスするには、全体管理者、セキュリティ管理者、またはセキュリティ閲覧者である必要があります。 「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可」を](permissions-in-the-security-and-compliance-center.md)参照してください。 
  
## <a name="web-traffic-log-requirements"></a>Web トラフィックログの要件

Office 365 Cloud App Security では、web トラフィックログのデータを使用して、組織内のユーザーがどのアプリを使用しているかを理解するのに役立ちます。 ログファイルの詳細については、「ユーザーのアクティビティ」を参照してください。
  
次のセクションでは、Office 365 Cloud App Security で正しく動作するように、必要な属性と web トラフィックログの追加要件を示します。

### <a name="attributes"></a>属性

Office 365 Cloud App Security では、web トラフィックログに含まれていない属性を表示または分析することはできません。 たとえば、Cisco ASA ファイアウォールの標準ログ形式には、トランザクションあたりにアップロードされたバイト数、ユーザー名、またはターゲット URL (ターゲット IP のみ) がありません。 そのため、これらの属性はクラウド探索データには表示されず、クラウドアプリの表示が制限されます。 Cisco ASA ファイアウォールの場合、情報レベルを6に設定する必要があります。 

web トラフィックログには、次の属性が含まれている必要があります。

- トランザクションの日付
- 発信元 IP アドレス
- 移行元ユーザー (高推奨)
- 宛先 IP アドレス
- 宛先 URL (推奨、url を使用すると、IP アドレスよりもクラウドアプリを検出する場合の精度が高くなります)
- データの合計量 (推奨、データ情報が非常に重要)
- アップロードまたはダウンロードされたデータの量 (推奨、クラウドアプリの使用パターンに関する洞察)
- 実行されたアクション (許可またはブロック)

### <a name="additional-requirements"></a>追加要件 

この記事で前述した属性を含めることに加えて、web トラフィックログは次の要件を満たしている必要があります。

- ログファイルのデータソースがサポートされている必要があります。
- ログファイルで使用される形式は、標準の形式と一致している必要があります。 ファイルがアップロードされると、アプリの検出によってこれが確認されます。
- ログのイベントは、90日以内に実行される必要があります。
- ログファイルには、ネットワークアクティビティについて分析できる送信トラフィック情報が含まれている必要があります。
  
## <a name="data-attributes-for-different-vendors"></a>さまざまなベンダーのデータ属性

次の表は、さまざまなベンダーからの web トラフィックログの情報をまとめたものです。 **最新情報については、必ずベンダーに確認してください。**


|                 データ ソース                  |    ターゲットアプリの URL    |    ターゲットアプリの IP     |       ユーザー名       |      送信元 IP       |    合計トラフィック     |    アップロードされたバイト数    |
|----------------------------------------------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|
|                  Barracuda                   | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |          いいえ          |          いいえ          |
|                  青のコート                   | <strong>○</strong> |          ×          | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                  Checkpoint                  |          いいえ          | <strong>○</strong> |          ×          | <strong>○</strong> |          いいえ          |          いいえ          |
|              Cisco ASA (Syslog)              |          いいえ          | <strong>○</strong> |          ×          | <strong>はい</strong> | <strong>○</strong> |          ×          |
|           FirePOWER を使用する Cisco ASA           | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                  Cisco FWSM                  |          いいえ          | <strong>○</strong> |          ×          | <strong>はい</strong> | <strong>○</strong> |          ×          |
|              Cisco Ironport WSA              | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                 Cisco のおアキ                 | <strong>はい</strong> | <strong>○</strong> |          ×          | <strong>○</strong> |          いいえ          |          いいえ          |
|           clavister NGFW (Syslog)            | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                SonicWall (旧称デル)                | <strong>はい</strong> | <strong>○</strong> |          ×          | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> |
|            デジタルアート i フィルター             | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                  fortigate                   |          いいえ          | <strong>○</strong> |          ×          | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> |
|                 Juniper srx                  |          いいえ          | <strong>○</strong> |          ×          | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> |
|                 Juniper ssg                  |          いいえ          | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                  McAfee swg                  | <strong>○</strong> |          いいえ          |          いいえ          | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> |
|                    MS TMG                    | <strong>○</strong> |          ×          | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|              Palo Alto Networks              |          いいえ          | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                    Sophos                    | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |          ×          |
|                Squid (Common)                | <strong>○</strong> |          ×          | <strong>はい</strong> | <strong>○</strong> |          ×          | <strong>はい</strong> |
|                Squid (ネイティブ)                | <strong>○</strong> |          ×          | <strong>はい</strong> | <strong>○</strong> |          ×          | <strong>はい</strong> |
| websense-調査詳細レポート (CSV) | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|    websense-インターネットアクティビティログ (cef)    | <strong>はい</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
|                   Zscaler                    | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> | <strong>○</strong> |
   
## <a name="supported-vendor-firewalls-and-proxies"></a>サポートされているベンダーのファイアウォールとプロキシ

Office 365 Cloud App Security では、次のファイアウォールとプロキシがサポートされています。
  
- Barracuda-Web App Firewall (W3C)  
- ブルーコートプロキシ SG-アクセスログ (W3C)
- チェックポイント
- Cisco ASA ファイアウォール (情報レベルを6に設定することを確認してください)
- FirePOWER を使用する Cisco ASA   
- Cisco IronPort WSA
- Cisco scansafe
- Cisco Merkai-url ログ
- clavister NGFW (Syslog)
- デジタルアート i フィルター
- fortinet fortinet
- iboss のセキュリティで保護されたクラウドゲートウェイ
- Juniper srx
- Juniper ssg
- McAfee Secure Web Gateway
- Microsoft Forefront Threat Management Gateway (W3C)
- Palo Alto series ファイアウォール
- Sonicwall (旧称デル)   
- Sophos SG
- Sophos xg
- Sophos Cyberoam
- Squid (Common)
- Squid (ネイティブ)
- websense-Web セキュリティソリューション-調査の詳細レポート (CSV)
- websense-Web セキュリティソリューション-インターネットアクティビティログ (cef)
- Zscaler
    
> [!NOTE]
> 使用するデータソースがここに含まれていない場合は、アプリの検出に追加するように要求できます。 これを行うには、レポートを作成するときに、**データソース**に [**その他**] を選択します。 次に、アップロードしようとしているデータソースの名前を入力します。 ログを確認し、そのログの種類に対するサポートを追加するかどうかを確認します。 または、形式に一致する[カスタムパーサーを定義](https://docs.microsoft.com/cloud-app-security/custom-log-parser)することもできます。 
  
## <a name="troubleshoot-errors-when-log-files-are-uploaded"></a>ログファイルがアップロードされるときのエラーのトラブルシューティング

web トラフィックログファイルをアップロードしたら、ガバナンスログを調べて、エラーが発生していないかどうかを確認します。 エラーが発生した場合は、次の表の情報を使用してエラーを解決します。
  
|**Error**|**説明**|**解決策**|
|:-----|:-----|:-----|
|サポートされていないファイルの種類  <br/> |アップロードされたファイルは有効なログファイルではありません。 たとえば、イメージファイルです。  <br/> |ファイアウォールまたはプロキシから直接エクスポートされたテキスト、zip、または gzip ファイルをアップロードします。  <br/> |
|内部エラーです  <br/> |内部リソースエラーが検出されました。  <br/> |[**再試行**] をクリックして、タスクを再度実行します。  <br/> |
|ログ形式が一致しません  <br/> |アップロードしたログ形式が、このデータソースの予想されるログ形式と一致しません。  <br/> |
ログが破損していないことを確認します。 ログファイルの形式と、[アップロード] ページに表示されているサンプルの形式を比較します。 |
|トランザクションは90日を超えています。  <br/> |すべてのトランザクションは90日を超えているため、無視されます。  <br/> |最新のイベントを使用して新しいログをエクスポートし、再アップロードします。  <br/> |
|クラウドアプリをカタログするトランザクションがありません  <br/> |認識されたクラウドアプリへのトランザクションがログにありません。  <br/> |ログに送信トラフィック情報が含まれていることを確認します。  <br/> |
|サポートされていないログの種類  <br/> |[データソース] を選択した場合 (サポートされてい**ない)**、ログは解析されません。 その代わりに、レビューのために[Microsoft Cloud App Security](https://aka.ms/whatiscas) technical team に送信されます。  <br/> |[Microsoft Cloud App Security](https://aka.ms/whatiscas) technical team は、データソースごとに専用パーサーを構築します。 最もよく使用されるデータソースは、既にサポートされています。 サポートされていないデータソースがアップロードされると、それが確認され、潜在的な新しいデータソースパーサーのリストに追加されます。  <br/> 機能に新しいパーサーが追加されると、Microsoft Cloud App Security リリースノートに通知が追加されます。  <br/> |
   
## <a name="next-steps"></a>次のステップ

- [通知を確認して処理を実行する](review-office-365-cas-alerts.md)
    
- [アプリ検出レポートを作成する](create-app-discovery-reports-in-ocas.md)
    
- [アプリ検出の調査結果を確認する](review-app-discovery-findings-in-ocas.md)
    
- [Office 365 Cloud App Security の使用率のアクティビティを確認する](utilization-activities-for-ocas.md)
    

