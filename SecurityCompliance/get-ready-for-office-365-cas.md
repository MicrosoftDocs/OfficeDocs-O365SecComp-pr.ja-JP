---
title: Office 365 Cloud App Security の使用準備
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: Office 365 のクラウド アプリケーションのセキュリティの使用を開始します。
ms.openlocfilehash: 906570c6607c70b63fa9d2059d56b50f7807124a
ms.sourcegitcommit: edf5db9357c0d34573f8cc406314525ef10d1eb9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23229989"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a>Office 365 Cloud App Security の使用準備
  
|評価 * *\>**|計画 * *\>**|配置 * *\>**|使用率。|
|:-----|:-----|:-----|:-----|
|[評価を開始します。](office-365-cas-overview.md) <br/> |コースです!  <br/> [次の手順](turn-on-office-365-cas.md) <br/> |[展開を開始します。](turn-on-office-365-cas.md) <br/> |[使用します。](utilization-activities-for-ocas.md) <br/> |
   
オンにし、組織の Office 365 のクラウド アプリケーション セキュリティ (高度なセキュリティ管理と呼ばれていました) の実装を準備するには考慮する点があります。ガイドとしてこの資料を使用して、Office 365 のクラウド アプリケーションのセキュリティを計画します。
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a>識別し、グローバル アカウントおよびセキュリティ管理者アカウントを保護する手順 1。

グローバル管理者、セキュリティ管理者、およびセキュリティのリーダーは、Office 365 のクラウド アプリケーションのセキュリティ ポリシーを表示、確認通知、およびレポートを使用してポータルにアクセスできます。グローバル管理者およびセキュリティ管理者は、ポリシーを定義し、組織を保護するために他のアクションを実行します。(詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md).)アクセス許可を高めた予防策として、組織のユーザー アカウントを確認します。 
  
 **[グローバル管理者アカウントを保護する、Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**。 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a>手順 2: は、監査、組織のログを有効にします。

正しく動作する Office 365 のクラウド アプリケーションのセキュリティのためには、監査ログを有効にする必要があります。これは通常、Exchange Online 管理者またはグローバル ・ アドミニストレーターが行います。
  
 **[オンまたはオフ、Office 365 を有効にする監査ログの検索](turn-audit-log-search-on-or-off.md)** をします。 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a>Office 365 のクラウド アプリケーションのセキュリティ関連ポータルには、手順 3。

1. [https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用して Office 365 にサインインします。(これで、セキュリティには、&amp;コンプライアンス センター)。 
    
2. **アラート**を参照して\>**詳細なアラートを管理**します。
    
3. Office 365 のクラウド アプリケーションのセキュリティ関連ポータルに移動する**には、Office 365 のクラウド アプリケーションのセキュリティ**を選択してください。 
    
    ![セキュリティ&amp;コンプライアンス センターでは、Office 365 のクラウド アプリケーションのセキュリティに移動するのには高度な通知の管理を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    Office 365 のクラウド アプリケーションのセキュリティ関連ポータルに移動すると、最初のページが表示は、[ポリシー] ページで次の図のようなです。
    
    ![ポリシー] ページで開始する場合、Office 365 のクラウド アプリケーションのセキュリティ関連ポータルに移動すると、](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a>ステップ 4: ポリシーを定義し、アラートを設定します&amp;アクション

グローバル管理者およびセキュリティ管理者は、Office 365 のクラウド アプリケーションのセキュリティのポリシーを定義します。ポリシーを定義する過程で、アラートとアクションも設定されています。アラートは、ビューに表示されますまたは電子メール経由で送信される条件に基づく通知です。 
  
Office 365 のクラウド アプリケーションのセキュリティの警告の 2 種類があります: 不審な活動を検出する異常検知して警告し、アクティビティのアラートは、組織の典型的な可能性のあるアクティビティに定義されています。アラートでは、グローバル管理者およびセキュリティ管理者、組織にとっても、通常の Office 365 環境内のアクティビティがある場合に通知します。
  
詳細については、次のリソースを参照してください。
  
- [Office 365 Cloud App Security のアクティビティ ポリシーと警告](activity-policies-and-alerts.md)
    
- [Office 365 Cloud App Security の異常検出ポリシー](anomaly-detection-policies-in-ocas.md)
    
- [Office 365 のクラウド アプリケーションのセキュリティの警告を確認して処理](review-office-365-cas-alerts.md)
    
## <a name="step-5-learn-about-your-organizations-cloud-usage"></a>組織のクラウドの使用方法について、手順 5。

グローバル管理者、セキュリティ管理者、またはセキュリティのリーダーとして、レポートとクラウドの探索のダッシュ ボード (生産性アプリケーションの検出とも呼ばれます) を通じて、組織のクラウドの使用方法について学習できます。このダッシュ ボードには、ユーザー、アプリケーション、web トラフィック、およびリスクのレベルについての情報が表示されます。
  
![検出を選択して、Office 365 の CA のポータルでは、\>クラウド探索のダッシュ ボード](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
生産性アプリケーションの検出のダッシュ ボード、Office 365 のクラウド アプリケーションのセキュリティ ・ ポータル内に移動するのには、**検出**を選択します\>**クラウド探索のダッシュ ボード**です。
  
![Office 365 CA ポータルでは、検出を選択します](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
必要な情報を含むレポートを作成するには、組織のファイアウォールやプロキシのログ ファイルをアップロードします。詳細については、次のリソースを参照してください。
  
- [Office 365 のクラウド アプリケーションのセキュリティでのアプリケーション検出レポートを作成します。](create-app-discovery-reports-in-ocas.md)
    
- [Office 365 Cloud App Security でアプリ検出結果を確認する](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-6-manage-apps-that-your-organization-is-using-to-access-office-365"></a>手順 6: 組織が Office 365 のアクセスに使用しているアプリケーションを管理します。

グローバル管理者またはセキュリティ管理者は、カスタム アプリケーションを Office 365 で、組織内のユーザーを使用しているサード ・ パーティ製のアプリケーションなどのアプリケーションを管理できます。たとえば、Office 365 を使用するカスタムのアプリケーションのダウンロードが他のこととします。ユーザーが使用してアプリケーションを確認する、信頼されていないアプリケーションは、アクセスを禁止したり、アプリケーションを追跡のための承認済みとしてマークできます。[Office 365 のクラウド アプリケーションのセキュリティを使用してアプリケーションのアクセス許可を管理](manage-app-permissions-in-ocas.md)します。
  
## <a name="step-7-use-your-siem-server-with-office-365-cloud-app-security"></a>手順 7: Office 365 のクラウド アプリケーションのセキュリティと SIEM サーバーを使用します。

セキュリティ情報およびイベント管理 (SIEM) サーバーを使用する組織ですか。Office 365 クラウド アプリケーションのセキュリティにアラートの一元的な監視を有効にするのには、SIEM のサーバーに統合できます。SIEM サービスと統合すること、セキュリティの一般的なワークフローを維持する、セキュリティ手順を自動化すること、およびクラウド ベースの間に相関関連づけることの中に、クラウド アプリケーションの保護を強化することができ、設置型のイベント。SIEM エージェントは、サーバー上で実行し、Office 365 のクラウド アプリケーションのセキュリティからのアラートを取得、SIEM サーバーにそれらのアラートをストリームします。[SIEM の統合 Office 365 のクラウド アプリケーションのセキュリティ](integrate-your-siem-server-with-office-365-cas.md)を参照してください。
  
## <a name="next-steps"></a>次の手順

- [Office 365 Cloud App Security を有効にする](turn-on-office-365-cas.md)
    
- [テスト ラボ ガイド](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment)を実際に体験した Office 365 のクラウド アプリケーションのセキュリティの強力な機能を紹介し、概念実証を作成してください。 
    

