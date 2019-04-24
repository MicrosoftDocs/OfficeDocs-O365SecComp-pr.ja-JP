---
title: Office 365 Cloud App Security でアプリ検出結果を確認する
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
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: Office アプリケーションの検出レポートを確認する 365 cloud app Security は、組織内のユーザーがクラウドアプリをどのように使用するかについて詳しく知るのに役立ちます。 ファイアウォールとプロキシからのログファイルを使用してアプリ探索レポートを作成した後、アプリ検出ダッシュボードで結果を確認します。
ms.openlocfilehash: f50ad372450b2a1404829eeb6f6964c1d954dccd
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264977"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a>Office 365 Cloud App Security でアプリ検出結果を確認する
  
|評価 * *\>**|計画 * *\>**|展開 * *\>**|使用率 * * * *|
|:-----|:-----|:-----|:-----|
|[評価の開始](office-365-cas-overview.md) <br/> |[計画を開始する](get-ready-for-office-365-cas.md) <br/> |[展開を開始する](turn-on-office-365-cas.md) <br/> |ここでは、  <br/> [次の手順](#next-steps) <br/> |
   
クラウド検出ダッシュボードは、組織の web トラフィックログと連携して、クラウドアプリの使用状況に関する詳細情報を提供します。 グローバル管理者、セキュリティ管理者、またはセキュリティリーダーで、組織が[Office 365 cloud app security でアプリ探索レポートを作成](create-app-discovery-reports-in-ocas.md)している場合は、クラウド検出ダッシュボードを使用して、ユーザーの組織は Office 365 とその他のクラウドアプリを使用しています。 (クラウド検出ダッシュボードは、生産性アプリの検出とも呼ばれます)。
  
 クラウド検出ダッシュボードを使用すると、組織内のユーザーが Office 365 およびその他のアプリをどのように使用しているかについての詳細情報を表示できます。 
  
![クラウド検出ダッシュボードが更新されました](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a>クラウド検出ダッシュボードに移動する

1. Cloud App Security ポータル ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) に移動し、サインインします。
    
2. [ **Cloud Discovery dashboard**の**検出** \> ] に移動します。
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a>上位ユーザー、IP アドレス、アプリ、およびリスクレベルを表示する

クラウド検出ダッシュボードには、組織内の Office 365 で使用されるアプリ、オープン通知、トップユーザー、およびリスクレベルの概要が示されています。
  
![クラウド検出のダッシュボート](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. [**ダッシュボード**] タブで、画面の上部にある [概要] セクションで、組織でのクラウドアプリ全体の使用法を確認します。 
    
2. 組織で使用されているアプリについては、「 **Office 365 カテゴリ**」を参照してください。 
    
3. 検出された**アプリ**ウィジェットを見て、Office 365 およびこのビュー内の他のアプリの使用状況を確認します。 
    
4. [**上位ユーザー** ] および [**上位 IP アドレス**] ウィジェットを参照して、組織内で Office 365 および cloud アプリを使用しているユーザーを特定します。 
    
5. 「**アプリの本部**」マップを使用して、ユーザーが使用しているアプリが地理的な場所によってどのように使用されるかを確認します。 
    
6. 「maps」領域の上にある「**リスクレベル**の概要」で、検出されたアプリのリスクスコアを確認します。 [検出された**アプリ**] 領域で使用したものと同じグループとカテゴリを使用して、リスクを確認できます。 たとえば、各グループのトラフィックのうち、高、中、低のリスクアプリからのトラフィックの量を確認できます。 
    
## <a name="dive-deeper-into-the-information"></a>情報を深く掘り下げる

クラウド検出を使用すると、アプリ、サブドメイン、IP アドレス、およびユーザーの詳細を確認できます。
  
1. クラウド検出ダッシュボードで、[検出された**アプリ**] タブを選択します。 
    
2. [フィルター] セクションを使用して、名前、カテゴリ、使用レベル、または最後に表示された日付でアプリを表示します。
    
3. 結果の一覧で、アプリ名の上にカーソルを移動して、[**サブドメインの表示**] リンクを表示します。<br/> ![アプリの横にカーソルを移動して、サブドメインの詳細を表示するリンクを表示する](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)<br/>選択したアプリに関する詳細情報が表示されます。
    
4. ip アドレスの詳細を表示するには、[ **ip アドレス**] タブを選択します。<br/>![クラウド検出では、IP アドレスに関する詳細情報が表示される](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)<br/>結果の一覧で、個別の IP アドレスを選択して、より詳細な情報を表示します。
    
5. 組織内の Office 365 ユーザーの詳細を表示するには、[**ユーザー** ] タブを選択します。<br/>![クラウド検出-ユーザー情報](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)
  
## <a name="exclude-entities"></a>エンティティを除外する

特定のシステムユーザーまたは IP アドレスを除外して、より具体的な情報に焦点を当てることができます。
  
1. [**設定** \> ] [**クラウド検出設定**] を選択します。
    
2. [**エンティティを除外**] を選択します。
    
3. 除外された**ユーザー**または除外された**IP アドレス**のいずれかを選択します。
    
4. ユーザーまたは ip アドレスを指定し、[**コメント**] ボックスに、それらのユーザーまたは ip アドレスを除外する理由についての情報を入力します。 
    
5. **[追加]** を選択します。
    
## <a name="next-steps"></a>次のステップ

- [通知を確認して処理を実行する](review-office-365-cas-alerts.md)
    
- [アプリ検出レポートを作成する](create-app-discovery-reports-in-ocas.md)
    
- [Office 365 Cloud App Security の使用率のアクティビティを](utilization-activities-for-ocas.md)確認する
    

