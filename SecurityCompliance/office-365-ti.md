---
title: Office 365 脅威の調査および対応
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 08/23/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection の脅威インテリジェンス機能が、組織に対する脅威を調査し、マルウェア、フィッシング、および Office 365 がユーザーに代わって検出したその他の攻撃に対応し、脅威を検索する方法について説明します。切り替える.
ms.openlocfilehash: 1d31f3a464060f5b72730e15895d918e61aa09a1
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761653"
---
# <a name="office-365-threat-investigation-and-response"></a>Office 365 脅威の調査および対応

Office 365 の脅威の調査と応答機能[Advanced Threat Protection](office-365-atp.md)は、セキュリティアナリストおよび管理者が組織の office 365 ユーザーを保護するのに役立ちます。
  
- Cyberattacks の識別、監視、理解を容易にする
    
- Exchange Online、SharePoint Online、OneDrive for Business、および Microsoft Teams での脅威への迅速な対応
    
- 組織に対する cyberattacks を防止するためにセキュリティ操作を支援するための洞察と知識の提供

- 重要な電子メールベースの脅威に対する自動化された[調査と対応](automated-investigation-response-office.md)
    
脅威の調査と応答の機能は、Office 365 セキュリティ&amp;コンプライアンスセンターで利用可能な脅威と関連する応答アクションについての洞察を提供します。 これらの洞察は、組織のセキュリティチームが、電子メールまたはファイルベースの攻撃から Office 365 ユーザーを保護するのに役立ちます。 機能は、ユーザーアクティビティ、認証、電子メール、侵害された Pc、セキュリティインシデントなど、複数のソースからの信号を監視し、データを収集するのに役立ちます。 ビジネス意思決定者および Office 365 の全体管理者、セキュリティ管理者、およびセキュリティアナリストは、この情報を使用して Office 365 ユーザーに対する脅威を理解し、それに対処し、知的財産権を保護することができます。

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>脅威の調査と応答のツールについて理解する

脅威の調査と応答の機能は、 &amp;セキュリティコンプライアンスセンターにおいて、[脅威ダッシュボード](#threat-dashboard)、[エクスプローラー](#threat-explorer)、[インシデント](#incidents)、[アタックシミュレータ](#attack-simulator)を含む、一連のツールと応答のワークフローとして表示されます。[応答の自動調査 &](automated-investigation-response-office.md)。
  
### <a name="threat-dashboard"></a>脅威ダッシュボード

脅威ダッシュボード ([セキュリティダッシュボード](security-dashboard.md)とも呼ばれます) を使用して、どのような脅威が解決されたかをすばやく確認し、ビジネス意思決定者に対して Office 365 サービスがビジネスをどのようにセキュリティで保護しているかを視覚的に報告することができます。
  
![脅威ダッシュボード](media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
このダッシュボードを表示して使用するには&amp; 、セキュリティ/コンプライアンスセンターで、[**脅威管理** \> ]**ダッシュボード**に移動します。

詳細情報 
  
### <a name="threat-explorer"></a>脅威エクスプローラー

脅威[エクスプローラー (およびリアルタイム検出)](threat-explorer.md)を使用して脅威を分析し、時間の経過と共に攻撃の量を確認し、脅威ファミリ、攻撃インフラストラクチャなどによるデータの分析を行います。 脅威エクスプローラー (エクスプローラーとも呼ばれます) は、セキュリティアナリストの調査ワークフローの出発点です。
  
![脅威エクスプローラー](media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
このレポートを表示して使用するには&amp; 、セキュリティ/コンプライアンスセンターで、[**脅威管理** \> **エクスプローラー**] に移動します。
  
### <a name="incidents"></a>事件

インシデントリスト (調査とも呼ばれます) を使用して、フライトセキュリティインシデントの一覧を表示します。 インシデントは、不審な電子メールメッセージなどの脅威を追跡し、さらに調査と修復を行うために使用されます。
  
![Office 365 の現在の脅威インシデントの一覧](media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
組織の現在のインシデントの一覧を表示するには、セキュリティ&amp; /コンプライアンスセンターで、[**脅威管理** \>の**レビュー** \> **インシデント**] に移動します。
  
![セキュリティ&amp; /コンプライアンスセンターで、[脅威管理\>のレビュー] を選択します。](media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a>アタックシミュレータ

アタックシミュレータを使用して、組織内で現実的な cyberattacks を設定して実行し、実際の cyberattack がビジネスに影響を与える前に、脆弱性のある人物を特定します。 詳細については、「 [Office 365 のアタックシミュレータ](attack-simulator.md)」を参照してください。

### <a name="automated-investigation-and-response"></a>自動調査および対応

自動化された調査と応答 (AIR) 機能を使用して、コンテンツ、デバイス、およびユーザーを組織内の脅威から危険に関連付ける時間と労力を節約します。 AIR プロセスは、特定の警告がトリガーされたとき、またはセキュリティ操作チームによって開始されたときに開始できます。 詳細については、「 [Office 365 での自動調査と応答 (AIR)](automated-investigation-response-office.md)」を参照してください。 
  
## <a name="threat-intelligence-widgets"></a>脅威インテリジェンスウィジェット

Office 365 Advanced Threat Protection プラン2のサービスの一部として、セキュリティアナリストは既知の脅威に関する詳細を確認できます。 これは、ユーザーを安全に保つために実行できる追加の予防策/手順があるかどうかを判断するのに役立ちます。
  
![最近の脅威に関する情報を示すセキュリティ傾向](media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-capabilities"></a>これらの機能はどのように入手できますか?

Office 365 の脅威の調査と応答の機能は、Office 365 Advanced Threat Protection プラン2および Enterprise E5 に含まれています。 

> [!TIP]
> これらの脅威の調査および応答機能を備えていない Office 365 サブスクリプションが組織にある場合、Office 365 Advanced Threat Protection プラン2をアドオンとして購入する可能性があります。 プランオプションの詳細については、「 [office 365 Advanced Threat Protection サービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」および「[購入または編集 (office 365 for business)](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)」を参照してください。
  
1. Office 365 の全体管理者として[https://admin.microsoft.com](https://admin.microsoft.com) 、に移動して、office 365 の職場または学校のアカウントを使用してサインインします。 
    
2. [**管理者** \> **課金**] を選択して、現在のサブスクリプションに含まれる内容を確認します。 
    - **Office 365 Enterprise E5**が表示されている場合は、組織に Office 365 Advanced Threat Protection プラン2があります (脅威の調査と応答の機能を含みます)。 
    - **Office 365 Enterprise E3**または**Office 365 enterprise E1**などの別のサブスクリプションが表示される場合は、「Office 365 Advanced Threat Protection プラン2」を追加することを検討してください。 (これを行うには、[**サブスクリプションの追加**] を選択します。)
    
3. Microsoft 365 管理センターで、[**ユーザー** \>の**アクティブなユーザー**] を選択します。
    
4. Office 365 Advanced Threat Protection プラン2ライセンスをアクティブなすべてのユーザーに割り当てます。 (こののライセンスを持っているユーザーのみが、エクスプローラなどのレポートに表示されます)。
    
5. Office 365 Advanced Threat Protection を使用する組織内のユーザーに役割を割り当てます。 「[ユーザーに Office 365 セキュリティ&amp;コンプライアンスセンターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」を参照し、次の表を参照してください。<br/>

  |**実行する処理...** <br/> |**これらの役割の1つが必要です** <br/> |  
  |:-----|:-----|
  |脅威ダッシュボード (または新しい[セキュリティダッシュボード](security-dashboard.md)) を使用する<br/> 最近の脅威または現在の脅威に関する情報を表示する  <br/> |Office 365 グローバル管理者  <br/> セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)  <br/> セキュリティリーダ (セキュリティ&amp;センターコンプライアンスセンターで割り当てられたもの)  <br/> |
  |脅威[エクスプローラー (およびリアルタイム検出)](threat-explorer.md)を使用して脅威を分析する  <br/> |Office 365 グローバル管理者  <br/> セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)  <br/> セキュリティリーダ (セキュリティ&amp;センターコンプライアンスセンターで割り当てられたもの)  <br/> |
  |インシデント (調査とも呼ばれる) を表示する <br/> インシデントに電子メールメッセージを追加する  <br/> |Office 365 グローバル管理者  <br/> セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)  <br/> セキュリティリーダ (セキュリティ&amp;センターコンプライアンスセンターで割り当てられたもの)  <br/> |
  |インシデントで電子メールアクションをトリガーする  <br/> 疑わしい電子メールメッセージの検索と削除  <br/> |Office 365 の全体管理者またはセキュリティ管理者  <br/> 上記の役割の1つと検索と削除 (セキュリティ&amp;コンプライアンスセンターで割り当てられたもの)  <br/> |
  |Office 365 Advanced Threat Protection プラン2を Microsoft Defender ATP と統合する  <br/> Office 365 Advanced Threat Protection プラン2を SIEM サーバーと統合する  <br/> |Office 365 グローバル管理者  <br/> セキュリティ管理者 (セキュリティ&amp;コンプライアンスセンターで割り当てられている)  <br/> 追加のアプリケーション (Microsoft Defender セキュリティセンター、SIEM サーバーなど) で割り当てられる適切な役割  <br/> |
   
役割、役割グループ、およびアクセス許可の詳細については、「 [Office 365 &amp;セキュリティコンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。
    
## <a name="next-steps"></a>次のステップ

- [脅威のトラッカーについて-新知識と注目](threat-trackers.md)
    
- [配信された悪意のある電子メールを検索して調査する (Office 365 の脅威の調査と応答)](investigate-malicious-email-that-was-delivered.md)
    
- [Microsoft Defender Advanced Threat Protection を使用して Office 365 の脅威の調査と応答を統合する](integrate-office-365-ti-with-wdatp.md)
    
- [アタックシミュレータについて](attack-simulator.md)
  

