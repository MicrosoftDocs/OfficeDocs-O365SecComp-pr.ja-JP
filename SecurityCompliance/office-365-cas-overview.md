---
title: Overview of Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: 'office 365 Cloud App Security では、office 365 の不審なアクティビティについての洞察が得られるため、問題が発生する可能性があり、必要に応じて、セキュリティの問題に対処するための処置を取ることができます。 '
ms.openlocfilehash: 960e4c75a4da13e1a0365f75d290cd18587abd58
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263077"
---
# <a name="overview-of-office-365-cloud-app-security"></a>Overview of Office 365 Cloud App Security
  
|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|ここでは、  <br/> [次の手順](get-ready-for-office-365-cas.md) <br/> |[計画を開始する](get-ready-for-office-365-cas.md) <br/> |[展開を開始する](turn-on-office-365-cas.md) <br/> |[利用を開始する](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> office 365 Cloud App Security は office 365 Enterprise E5 で利用できます。 組織で別の office 365 Enterprise サブスクリプションを使用している場合、office 365 Cloud App Security をアドオンとして購入することができます。 (全体管理者として、Microsoft 365 管理センターで、[**課金** \>の**サブスクリプションの追加**] を選択します。)詳細については、「office 365 プラットフォームサービスの説明」を参照してください[。 office 365 セキュリティ&amp;コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)で、 [office 365 for business のアドオンを購入または編集](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)します。 
  
office 365 Cloud App Security では、office 365 の不審なアクティビティを把握しているため、問題が発生する可能性がある状況を調査し、必要に応じて、セキュリティの問題に対処するための処置を取ることができます。 office 365 Cloud App Security では、例外的または不審なアクティビティに対してトリガーされた通知の通知を受け取ることができます。組織のデータが office 365 にどのようにアクセスおよび使用されているかを確認し、ユーザーアカウントに疑わしいアクティビティが発生して中断し、通知がトリガーされた後、ユーザーが Office 365 アプリに再度ログインする。 この記事では、Office 365 Cloud App のセキュリティ機能の概要について説明します。
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a>Office 365 Cloud App Security ポータルを見つける方法

> [!NOTE]
> office 365 Cloud App Security ポータルにアクセスするには、office 365 全体管理者、セキュリティ管理者、またはセキュリティリーダである必要があります。 詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。 
  
Office 365 Cloud App Security ポータルにアクセスするには、に[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)移動してサインインします。 

Office 365 セキュリティ&amp;コンプライアンスセンターから入手することもできます。 そのためには、次のいずれかの方法をお勧めします。
  
1. に[https://protection.office.com](https://protection.office.com)移動して、Office 365 の職場または学校のアカウントを使用してサインインします。 (これにより、セキュリティ&amp;コンプライアンスセンターに移動できます。)
    
2. セキュリティ&amp; /コンプライアンスセンターで、[**警告** \>の**管理] [詳細通知の管理**] を選択します。 <br/>![Office 365 Cloud App Security に移動するには、[高度な通知の管理] を選択します。](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>(office 365 cloud app security がまだ有効になっておらず、全体管理者である場合は、 [office 365 Cloud app security を有効](turn-on-office-365-cas.md)にします。)
    
3. [ **Office 365 Cloud App Security に移動**] を選択します。 
    
## <a name="policies"></a>ポリシー

Office 365 Cloud App Security は、組織に対して定義されているポリシーを使用して動作します。 Office 365 Cloud App Security を使用すると、組織は多数の事前に定義された異常検出ポリシーとアクティビティポリシーのいくつかのテンプレートを取得します。 これらのポリシーは、一般的な異常を検出し、危険な IP アドレスからログインしているユーザーを識別し、ランサムウェアのアクティビティを検出し、企業以外の IP アドレスから管理者アクティビティを検出するなどの目的で設計されています。
  
![CAS ポータルで、[コントロール\>テンプレート] を選択してポリシーテンプレートを表示または作成します。](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
ポリシーテンプレートを表示または使用するには、Office 365 Cloud App Security ポータルで、[**コントロール** \> **テンプレート**] に移動します。 
  
![O365 CAS ポータルで、[コントロール] を選択します。](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
ポリシーの詳細については、以下のリソースを参照してください。
  
- [Office 365 Cloud App Security のアクティビティ ポリシーと警告](activity-policies-and-alerts.md)
    
- [Office 365 Cloud App Security の異常検出ポリシー](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a>アラート

ポリシーが定義されている場合、検出された疑わしいまたは例外的なアクティビティについて通知されます。 組織の通知を表示するには、画面上部のナビゲーションバーにある [**通知**] を選択します。 
  
![[通知] ページには、トリガーされた通知と実行されたアクションが表示されます。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
アラートがトリガーされたときに、その通知を確認して、何が起こっているのかについて詳しく知ることができます。 その後も、アクティビティが疑わしい場合は、アクションを実行できます。 たとえば、問題についてユーザーに通知したり、ユーザーの office 365 へのサインインを中断したり、office 365 アプリにサインインし直すようにユーザーに要求することができます。
  
通知の詳細については、次のリソースを参照してください。
  
- [Office 365 Cloud App Security のアクティビティ ポリシーと警告](activity-policies-and-alerts.md)
    
- [Office 365 Cloud App Security の異常検出ポリシー](anomaly-detection-policies-in-ocas.md)
    
- [Office 365 Cloud App Security alerts を確認してアクションを実行する](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a>アクティビティログ

Office 365 Cloud App Security のアクティビティログページにあるユーザーアクティビティに関する情報を表示します。
  
![O365 CAS ポータルで、[アクティビティログ\>の調査] を選択します。](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
このページを表示するには、Office 365 Cloud App Security ポータルで、[ **** \> **アクティビティログ**の調査] に移動します。 
  
![O365 CAS ポータルで、[調査] を選択します。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
web トラフィックログは Office 365 Cloud App Security でも使用できます。 これらのログファイルに含まれる詳細については、「ユーザーのアクティビティ」を参照してください。 ログファイルは、Barracuda、ブルーコート、チェックポイント、Cisco、clavister、Dell SonicWALL、for et、Juniper、McAfee、Microsoft、Palo Alto、Sophos、Squid、websence、Zscaler などから使用できます。
  
[Office 365 Cloud App Security の web トラフィックログとデータソースについて説明します。](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="oauth-apps"></a>OAuth アプリ

office 365 Cloud App Security では、組織内のユーザーが office 365 のデータにアクセスするサードパーティ製アプリを使用することを許可または禁止することができます。
  
![O365 CAS では、[調査] メニューから [OAuth アプリの管理] ページにアクセスできます。](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
このページを表示するには、「 **OAuth アプリ**を**調査** \>する」に移動します。 
  
![O365 CAS ポータルで、[調査] を選択します。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[Office 365 Cloud App Security を使用して OAuth アプリを管理する](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a>クラウド検出ダッシュボード

**クラウド検出ダッシュボード**(**生産性アプリの検出**とも呼ばれます) は、組織内でのクラウドアプリの使用に関する情報を示しています。 このダッシュボードを使用して、アプリ、ユーザー、トラフィック、トランザクションなどに関する情報を表示できます。 クラウド検出ダッシュボードは、次のようなイメージです。 
  
![Office 365 CAS ポータルで、[クラウド検出\>ダッシュボードの検出] を選択します。](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
このダッシュボードにアクセスするには、Office 365 cloud App Security ポータルで、[ **** \> **cloud Discovery dashboard**の検出] に移動します。 
  
![Office 365 CAS ポータルで、[検出] を選択します。](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[Office 365 Cloud App Security でアプリ検出結果を確認する](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a>次のステップ

- [Office 365 Cloud App Security の使用例と利用状況ガイド](https://aka.ms/O365CASGuide)を取得する
    
- [Office 365 Cloud App Security の使用準備](get-ready-for-office-365-cas.md)
    

