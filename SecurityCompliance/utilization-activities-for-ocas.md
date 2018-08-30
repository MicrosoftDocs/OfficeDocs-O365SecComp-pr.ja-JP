---
title: Office 365 Cloud App Security 展開後の利用に関する作業
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 86f414ad-81de-4703-b40a-c6615bbe9108
description: 設定すると、Office 365 のクラウド アプリケーションのセキュリティを展開すると、次のように、構成が正しいこと、および定期的な確認作業の準備ができなことを確認するのには、特定のタスクを実行する必要があります。
ms.openlocfilehash: bc8cfad8eb9d9444066c3193ec2978e9ffd9f56a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531918"
---
# <a name="utilization-activities-after-rolling-out-office-365-cloud-app-security"></a>Office 365 Cloud App Security 展開後の利用に関する作業
  
|評価 * *\>**|計画 * *\>**|配置 * *\>**|使用率。|
|:-----|:-----|:-----|:-----|
|[評価を開始します。](office-365-cas-overview.md) <br/> |[計画の開始します。](get-ready-for-office-365-cas.md) <br/> |[展開を開始します。](turn-on-office-365-cas.md) <br/> |コースです!  <br/> [次の手順](review-office-365-cas-alerts.md) <br/> |
   
> [!NOTE]
> Office 365 のクラウド アプリケーションのセキュリティは、Office 365 エンタープライズ E5 に使用できます。組織は、別の Office 365 エンタープライズ サブスクリプションで使用されている場合、Office 365 のクラウド アプリケーションのセキュリティがアドオンとして購入できます。(グローバル管理者は、Office 365 管理センターを選択して**請求** \> **サブスクリプションを追加**します)。詳細についてを参照してください[Office 365 のプラットフォーム サービスの説明: Office 365 のセキュリティ&amp;コンプライアンス センター](https://technet.microsoft.com/en-us/library/dn933793.aspx) [購入またはビジネスのための Office 365 のアドオンを編集](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)するとします。 
  
設定して、Office 365 のクラウド アプリケーションのセキュリティを構成することが後、に Office 365 のグローバル管理者または組織のセキュリティ管理者としての使用率、特定のタスクを実行します。 

これらのタスクを実行していることを確認 Office 365 のクラウド アプリケーションのセキュリティが正しく構成されている、ポリシーが最新で、組織が Office 365 の値を実現していますをしてみましょう。これらのタスクを計画するためのガイドとしてこの資料を使用します。
  
> [!NOTE]
> この資料で説明するタスクを実行するには、グローバル管理者またはセキュリティ管理者である必要があります。詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。 
    
## <a name="activities-after-the-initial-configuration-and-rollout-of-office-365-cloud-app-security"></a>初期設定と Office 365 のクラウド アプリケーションのセキュリティの展開後の活動

Office 365 のクラウド アプリケーションのセキュリティの構成し、展開、グローバル ・ アドミニストレーターまたはセキュリティ管理者として、考慮すべき点があります。
  
- どのような作業は、IT 部署の予定表に追加する必要があるでしょうか。
    
- どのように時間の経過とともに適切なポリシーが設定を使用する Office 365 のクラウド アプリケーションのセキュリティが構成されていることを確認しますか。
    
- IT 管理のチェーンを要約情報の種類を送信する必要がありますか。
    
次の表には、継続的なタスクを実行して、IT 部門のカレンダーに追加することを考慮する必要があります、定期的なタスクについて簡単にまとめたものです。
  
|**進行中のタスク**|**定期的なタスク**|
|:-----|:-----|
| 警告メッセージを送信する電子メール アカウントを監視します。  <br/>  新しいサイバー攻撃に関する最新情報については、業界 cybersecurity ニュース フィードを監視します。  <br/>  識別し、セキュリティの問題やリスクに対処するセキュリティ警告の動作します。  <br/>  各セキュリティ上の問題と、中央のログでの解像度を集計します。  <br/> | スポット異常に Office 365 のクラウド アプリケーションのセキュリティ警告の毎月または四半期ごとのレビューを行い、傾向の分析  <br/>  毎月または四半期ごとの拡張機能に含める Office 365 のクラウド アプリケーションのセキュリティとアドレスの新しい cyberattacks と cybersecurity の傾向を既存の Office 365 のクラウド アプリケーションのセキュリティ ポリシーのレビューを行う  <br/> |
   
によって、組織のサイズと目的の監視とセキュリティの名声を維持するのには、IT 管理のチェーンを含むの月ごとのサマリーをコンパイルできます。
  
- Office 365 のクラウド アプリケーションのセキュリティと識別される、セキュリティ インシデントの種類
    
- 検出されたインシデントの数など、セキュリティ インシデントへの対応、集中管理されたログからの情報
    
- 警告の傾向と、それらがどのように解決されました。
    
- Cybersecurity の最新の動向
    
- Office 365 のクラウド アプリケーションのセキュリティ ポリシーを変更し、エンド ・ ユーザーに与える影響に関する推奨事項
    
## <a name="activities-after-time-has-passed-since-rolling-out-office-365-cloud-app-security"></a>Office 365 のクラウド アプリケーションのセキュリティを展開してから時間が経過した後の活動

最初に構成されているか、Office 365 のクラウド アプリケーションのセキュリティ ポリシーを維持するため、時間のかかる時間が過ぎている場合は、組織のセキュリティ目標と現在の機能を反映した構成に戻るには、以下の手順を実行します。Office 365 のクラウド アプリケーションのセキュリティ。
  
1. Office 365 のクラウド アプリケーションのセキュリティの構成の最終変更の日付を決定します。
    
2. 現在の Office 365 のクラウド アプリケーションのセキュリティ構成を理解し、必要に応じて、これらのポリシーを調整します。たとえば、電子メールを通じて通知が送信される場所を知っているを確認します。
    
3. 最後に Office 365 のクラウド アプリケーションのセキュリティを構成した後は、[ [Office 365 のクラウド アプリケーションのセキュリティの新](new-in-office-365-cas.md)製品の変更を参照してください。 
    
4. Office 365 のクラウド アプリケーションのセキュリティの警告やスポットの異常ログの分析を実行し、傾向を分析します。
    
5. 最新のセキュリティ上の脅威を認識する業界の cybersecurity の傾向を確認してください。
    
6. Office 365 のクラウド アプリケーションのセキュリティ ポリシーの現在のセットにする必要がある変更の分析を実行します。Office 365 のクラウド アプリケーションのセキュリティ機能の変更、現在の異常、および cybersecurity の傾向を反映します。既存のポリシーまたは新しいポリシーの作成、変更をお勧めします。
    
7. ポリシーの変更を実装するための計画を作成します。通信 (交流) 必要に応じて、エンド ・ ユーザーに提案された変更の結果です。
    
8. Office 365 のクラウド アプリケーションのセキュリティ ポリシーの変更を実装します。
    
9. エンド ・ ユーザーからのフィードバックと Office 365 のクラウド アプリケーションのセキュリティの警告を監視し、時間の経過のポリシーを調整します。
    
## <a name="next-steps"></a>次の手順

- [アクティビティを調査します。](investigate-an-activity-in-office-365-cas.md)
    
- [サスペンド モードまたはユーザー アカウントを復元します。](suspend-or-restore-an-account-in-ocas.md)
    
- [アプリケーションのアクセス許可を管理します。](manage-app-permissions-in-ocas.md)
    
- [Office 365 Cloud App Security でアプリ検出結果を確認する](review-app-discovery-findings-in-ocas.md)
    
- サポートされている[Web トラフィックのログとデータ ソース](web-traffic-logs-and-data-sources-for-ocas.md)の一覧を表示します。
    

