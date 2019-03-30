---
title: Office 365 Cloud App Security 展開後の利用に関する作業
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 86f414ad-81de-4703-b40a-c6615bbe9108
description: Office 365 Cloud App Security をセットアップしてロールアウトした後、特定のタスクを実行して構成が正しいことと、定期的なレビューの準備ができていることを確認してください。
ms.openlocfilehash: 232de4df1d1eb4debdddcee2c1d8672d1aeb4b21
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999950"
---
# <a name="utilization-activities-after-rolling-out-office-365-cloud-app-security"></a>Office 365 Cloud App Security 展開後の利用に関する作業
  
|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|[評価の開始](office-365-cas-overview.md) <br/> |[計画を開始する](get-ready-for-office-365-cas.md) <br/> |[展開を開始する](turn-on-office-365-cas.md) <br/> |ここでは、  <br/> [次の手順](review-office-365-cas-alerts.md) <br/> |
   
> [!NOTE]
> office 365 Cloud App Security は office 365 Enterprise E5 で利用できます。 組織で別の office 365 Enterprise サブスクリプションを使用している場合、office 365 Cloud App Security をアドオンとして購入することができます。 (全体管理者として、Microsoft 365 管理センターで、[**課金** \>の**サブスクリプションの追加**] を選択します。)詳細については、「office 365 プラットフォームサービスの説明」を参照してください[。 office 365 セキュリティ&amp;コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)で、 [office 365 for business のアドオンを購入または編集](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)します。 
  
office 365 Cloud App security をセットアップして構成した後、組織のために office 365 の全体管理者またはセキュリティ管理者として、特定の使用状況タスクを実行する必要があります。 

これらのタスクを実行することにより、office 365 Cloud App Security が適切に構成され、ポリシーが最新のものであり、組織が office 365 の価値を実感していることを確認できます。 この記事を参考にして、これらのタスクを計画してください。
  
> [!NOTE]
> この記事で説明されているタスクを実行するには、全体管理者またはセキュリティ管理者である必要があります。 詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。 
    
## <a name="activities-after-the-initial-configuration-and-rollout-of-office-365-cloud-app-security"></a>Office 365 Cloud App Security の初期構成とロールアウト後のアクティビティ

Office 365 Cloud App Security を構成してロールアウトした後、全体管理者またはセキュリティ管理者として、次の点を考慮する必要があります。
  
- IT 部門の予定表に追加する必要があるタスク
    
- Office 365 Cloud App Security が、時間の経過とともに適切なポリシーセットを使用するように構成されていることを確認するには、どうすればよいですか。
    
- IT 管理チェーンを送信する必要がある要約情報の種類は何ですか。
    
次の表に、実行する必要がある進行中のタスクと、IT 部門の予定表に追加する必要がある定期的なタスクを簡単にまとめています。
  
|**進行中のタスク**|**定期的なタスク**|
|:-----|:-----|
| 通知メッセージを送信する電子メールアカウントを監視する  <br/>  新しいサイバー攻撃に関する最新情報について業界 cybersecurity ニュースフィードを監視する  <br/>  セキュリティの警告に基づいてセキュリティインシデントとリスクを識別して解決する  <br/>  中央ログで各セキュリティインシデントと解決策を要約する  <br/> | Office 365 Cloud App Security alerts の月次または四半期のレビューを実行して、異常を発見し、傾向を分析する  <br/>  既存の office 365 cloud app security ポリシーの月次または四半期のレビューを実行して、office 365 cloud app security の機能強化を含み、cybersecurity の新しい cyberattacks およびトレンドを解決します。  <br/> |
   
組織の規模とセキュリティ stature の監視と保守に関する情報に応じて、次のものを含む IT 管理チェーンの月ごとのサマリーをコンパイルできます。
  
- Office 365 Cloud App security で識別されるさまざまな種類のセキュリティインシデント
    
- 検出されたインシデント数などの、セキュリティインシデントの中央ログからの概要情報
    
- アラートの傾向とその対処方法
    
- 最新の cybersecurity 傾向
    
- Office 365 Cloud App Security policy の変更点とエンドユーザーへの影響に関する推奨事項
    
## <a name="activities-after-time-has-passed-since-rolling-out-office-365-cloud-app-security"></a>Office 365 Cloud App Security を展開してから経過した後のアクティビティ

Office 365 Cloud App Security ポリシーを最初に構成または管理してから、protracted の時間が経過した場合は、次の手順を実行して、組織のセキュリティ目標および現在の機能を反映した構成に戻すことができます。Office 365 Cloud App Security の場合:
  
1. Office 365 Cloud App Security の最後の構成変更の日付を確認します。
    
2. 現在の Office 365 Cloud App Security の構成を理解し、必要に応じてそれらのポリシーを調整します。 たとえば、通知が電子メールで送信されている場所を確認してください。
    
3. 前回 office 365 cloud app security を構成した後の製品変更については、「 [office 365 cloud app security の新機能](new-in-office-365-cas.md)」を参照してください。 
    
4. Office 365 Cloud App Security の警告とログの分析を実行して、異常を発見し、傾向を分析します。
    
5. 業界 cybersecurity の傾向をチェックして、最新のセキュリティの脅威を認識します。
    
6. 現在の Office 365 Cloud App Security ポリシーセットに対して行う必要のある変更の分析を行います。 Office 365 Cloud App Security 機能の変更、現在の異常、cybersecurity の傾向を組み込みます。 既存のポリシーの変更または新しいポリシーの作成をお勧めします。
    
7. ポリシーの変更を実装するための計画を立ててください。 必要に応じて、提案された変更の結果をエンドユーザーに通知 (socialize) します。
    
8. Office 365 Cloud App Security policy の変更を実装します。
    
9. エンドユーザーのフィードバックと Office 365 Cloud App Security alerts を監視して、ポリシーを徐々に調整します。
    
## <a name="next-steps"></a>次の手順

- [アクティビティを調べる](investigate-an-activity-in-office-365-cas.md)
    
- [ユーザーアカウントを中断または復元する](suspend-or-restore-an-account-in-ocas.md)
    
- [OAuth アプリを管理する](manage-app-permissions-in-ocas.md)
    
- [Office 365 Cloud App Security でアプリ検出結果を確認する](review-app-discovery-findings-in-ocas.md)
    
- サポートされている[Web トラフィックログとデータソース](web-traffic-logs-and-data-sources-for-ocas.md)の一覧を表示する
    

