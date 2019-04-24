---
title: Office 365 Cloud App Security の使用の準備
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/15/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: Office 365 Cloud App Security の使用を開始する
ms.openlocfilehash: 89718adcbb7c77735db3009937d887e88d4a8bc3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254026"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a>Office 365 Cloud App Security の使用の準備
  
|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|[評価の開始](office-365-cas-overview.md) <br/> |ここでは、  <br/> [次の手順](turn-on-office-365-cas.md) <br/> |[展開を開始する](turn-on-office-365-cas.md) <br/> |[利用を開始する](utilization-activities-for-ocas.md) <br/> |
   
Office 365 Cloud App Security を組織に対して有効にして実装する準備ができたら、いくつかの点を考慮する必要があります。 この記事は、Office 365 Cloud App Security を計画する際のガイドとしてご利用ください。
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a>手順 1: グローバルおよびセキュリティ管理者アカウントを識別して保護する

グローバル管理者、セキュリティ管理者、およびセキュリティ閲覧者は、Office 365 Cloud App security ポータルにアクセスして、ポリシーの表示、通知の確認、およびレポートの使用を行うことができます。 グローバル管理者とセキュリティ管理者は、ポリシーを定義し、組織を保護するためのその他のアクションを実行できます。 (詳細については、「 [Office 365 セキュリティ&amp;センターコンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください)。安全性の高い権限を持つ組織のユーザーアカウントを確認します。 
  
 **[Office 365 のグローバル管理者アカウントを保護](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)** します。 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a>手順 2: 組織の監査ログを有効にする

Office 365 Cloud App Security を正しく動作させるには、監査ログを有効にする必要があります。 これは、通常、Exchange Online 管理者または全体管理者によって行われます。
  
 **[Office 365 監査ログの検索をオンまたはオフに](turn-audit-log-search-on-or-off.md)** します。 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a>手順 3: Office 365 Cloud App Security ポータルに移動する

Office 365 Cloud App Security ポータルにアクセスするには、に[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)移動してサインインします。 

Office 365 セキュリティ&amp;コンプライアンスセンターから入手することもできます。 そのためには、次のいずれかの方法をお勧めします。

1. に[https://protection.office.com](https://protection.office.com)移動し、サインインします。 (これにより、セキュリティ&amp;コンプライアンスセンターに移動できます。)
    
2. [**アラート** \> ] **[advanced alerts の管理**] に移動します。
    
3. [ **office 365 cloud app security に移動**] を選択して、office 365 Cloud app security ポータルに移動します。<br> ![Office 365 Cloud App Security に移動するには、[高度な通知の管理] を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br>Office 365 Cloud App Security ポータルに移動すると、最初に表示されるページは [ポリシー] ページになります。これは次の画像のようになります。<br>![Office 365 Cloud App Security ポータルに移動するときに、[ポリシー] ページから始めます。](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)<br>
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a>手順 4: ポリシーを定義し、通知&amp;アクションをセットアップする

グローバル管理者とセキュリティ管理者は、Office 365 Cloud App security でポリシーを定義します。 ポリシーの定義プロセスでは、アラートとアクションも設定されます。 通知は、ビューに表示される、または電子メール経由で送信される基準に基づく通知です。 
  
Office 365 Cloud App Security には2種類の通知があります。不審なアクティビティを検出する異常検出アラートと、組織にとって例外的なアクティビティに対して定義されたアクティビティアラートがあります。 通知は、組織にとって一般的でない Office 365 環境にアクティビティがある場合に、グローバル管理者とセキュリティ管理者に通知します。
  
詳細については、以下のリソースを参照してください。
  
- [Office 365 Cloud App Security のアクティビティ ポリシーと警告](activity-policies-and-alerts.md)
    
- [Office 365 Cloud App Security の異常検出ポリシー](anomaly-detection-policies-in-ocas.md)
    
- [Office 365 Cloud App Security alerts を確認してアクションを実行する](review-office-365-cas-alerts.md)
    

## <a name="step-5-set-up-conditional-access-app-control"></a>手順 5: 条件付きアクセスアプリコントロールを設定する

ユーザーがどのアプリを使用できるかなど、特定の条件に基づいて、組織のアプリでコントロールを設定して適用します。 機密性の高いドキュメントをダウンロードおよび暗号化できるかどうかを決定し、特定のアプリへのアクセスをブロックし、特定のアプリに対して読み取り専用モードを設定し、企業以外のネットワークからのユーザーセッションを制限します。

詳細については、以下のリソースを参照してください。

- [Office 365 Cloud App Security アプリの条件付きアクセス制御を使用してアプリを保護する](ocas-conditional-access-app-control.md)

- [Office 365 アプリ用のアプリの条件付きアクセス制御を展開する](ocas-deploy-conditional-access-app-control.md)

## <a name="step-6-learn-about-your-organizations-cloud-usage"></a>手順 6: 組織のクラウド使用状況について学びます。

グローバル管理者、セキュリティ管理者、またはセキュリティ閲覧者は、レポートとクラウド検出ダッシュボード (生産性アプリの検出とも呼ばれます) を使用して、組織のクラウド使用状況について理解することができます。 このダッシュボードには、ユーザー、アプリ、web トラフィック、およびリスクレベルに関する情報が表示されます。
  
![Office 365 CAS ポータルで、[クラウド検出\>ダッシュボードの検出] を選択します。](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
プロダクティビティアプリの探索ダッシュボードに移動するには、Office 365 cloud App Security ポータルで、[**クラウド検出ダッシュボード**の**検出** \> ] を選択します。
  
![Office 365 CAS ポータルで、[検出] を選択します。](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
レポートに必要な情報を設定するには、組織のファイアウォールとプロキシからログファイルをアップロードします。 詳細については、以下のリソースを参照してください。
  
- [Office 365 Cloud app Security でアプリ検出レポートを作成する](create-app-discovery-reports-in-ocas.md)
    
- [Office 365 Cloud App Security でアプリ検出結果を確認する](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-7-manage-apps-that-your-organization-is-using-to-access-office-365"></a>手順 7: 組織が Office 365 へのアクセスに使用しているアプリを管理する

グローバル管理者またはセキュリティ管理者として、組織内のユーザーが Office 365 を使用してデバイス上で使用している、カスタムアプリやサードパーティアプリなどのアプリを管理できます。 たとえば、ユーザーが Office 365 で使用するカスタムアプリをダウンロードしたとします。 ユーザーが使用しているアプリを確認したり、信頼されていないアプリを禁止したり、追跡の目的でアプリを承認済みとしてマークしたりすることができます。 [Office 365 Cloud App Security を使用して OAuth アプリを管理](manage-app-permissions-in-ocas.md)します。
  
## <a name="step-8-create-a-maintenance-plan"></a>手順 8: メンテナンス計画を作成する

office 365 Cloud App security をセットアップして構成した後、組織のために office 365 の全体管理者またはセキュリティ管理者として、特定の使用状況タスクを実行する必要があります。
これらのタスクを実行することにより、office 365 Cloud App Security が適切に構成され、ポリシーが最新のものであり、組織が office 365 の価値を実感していることを確認できます。 この記事を参考にして、これらのタスクを計画してください。 [Office 365 Cloud App Security をロールアウトした後の使用](utilization-activities-for-ocas.md)状況のアクティビティを参照してください。

## <a name="optional-step-9-use-your-siem-server-with-office-365-cloud-app-security"></a>オプション手順 9: SIEM サーバーを Office 365 Cloud App Security で使用する

組織はセキュリティ情報およびイベント管理 (SIEM) サーバーを使用していますか。 Office 365 Cloud App Security を SIEM サーバーと統合して、アラートの集中監視を有効にすることができるようになりました。 SIEM サービスとの統合により、通常のセキュリティワークフローを維持しながら、セキュリティ手順を自動化し、クラウドベースのイベントとオンプレミスのイベントとを関連付けることで、クラウドアプリケーションをより適切に保護することができます。 SIEM エージェントは、サーバー上で実行され、Office 365 Cloud App Security から通知を取得し、それらのアラートを SIEM サーバーに転送します。 「 [SIEM integration with Office 365 Cloud App Security」を](integrate-your-siem-server-with-office-365-cas.md)参照してください。
  
## <a name="next-steps"></a>次のステップ

- [Office 365 Cloud App Security を有効にする](turn-on-office-365-cas.md)
    
- Office 365 Cloud App Security の強力な機能をデモンストレーションし、概念実証を作成するための実践的な操作については、[テストラボガイド](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment)をご利用ください。 
    

