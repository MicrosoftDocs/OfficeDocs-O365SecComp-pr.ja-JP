---
title: Office 365 の脅威の調査と対応についての作業を開始する
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 38e9b67f-d188-490f-bc91-a1ae4b270441
ms.collection:
- M365-security-compliance
description: Office 365 の脅威の調査と応答、および開始する方法について説明します。
ms.openlocfilehash: 8bd5e68abfa036d1257fb08fb1dd2b730f7de821
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599253"
---
# <a name="get-started-with-threat-investigation-and-response-in-office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection での脅威の調査と応答の概要

組織のセキュリティチームに参加している場合は、Office 365 の脅威調査および応答機能を使用して、ユーザーを攻撃から保護することができます。 Office 365 Advanced Threat Protection プラン 2 (旧称 Office 365 Threat 知能) を使用すると、セキュリティアナリストと管理者は、洞察を得て、Office の365で何が起こっているかに基づいて操作を識別することによって、ユーザーの安全を確保することができます。environment. これらの洞察は、脅威インテリジェンスのデータとシステムの包括的なリポジトリに基づいています。これは、攻撃の動作や不審な動作に対応するパターンを見つけるためのものです。
  
脅威の調査と応答の詳細と、開始する方法については、この記事を参照してください。
  
## <a name="what-are-the-threat-investigation-and-response-capabilities-included-in-office-365"></a>Office 365 に含まれている脅威の調査および応答機能について

脅威の調査と応答の機能は、Office 365 セキュリティ&amp;コンプライアンスセンターで利用可能な脅威と、関連する応答アクションに関する洞察を促進します。 これらの洞察は、組織のセキュリティチームが電子メールやファイルベースの攻撃から Office 365 ユーザーを保護するのに役立ちます。 機能は、ユーザーアクティビティ、認証、電子メール、侵害された Pc、セキュリティインシデントなど、複数のソースからの信号を監視し、データを収集するのに役立ちます。 ビジネス意思決定者および Office 365 の全体管理者、セキュリティ管理者、およびセキュリティアナリストは、この情報を使用して、Office 365 ユーザーに対する脅威を理解し、それに対応し、知的財産を保護することができます。

## <a name="get-acquainted-with-the-threat-dashboard-explorer-and-incidents"></a>脅威ダッシュボード、エクスプローラー、インシデントについて理解する

これらの脅威の調査と応答能力は、 &amp;セキュリティコンプライアンスセンターで、[脅威ダッシュボード](#threat-dashboard)、[脅威エクスプローラ](#threat-explorer)、[インシデント](get-started-with-ti.md#incidents)、攻撃などの一連のツールと応答ワークフローとして、さまざまな機能を備えています。 [シミュレータ](attack-simulator.md)、および自動調査 & 応答。
  
### <a name="threat-dashboard"></a>脅威ダッシュボード

脅威ダッシュボード ([セキュリティダッシュボード](security-dashboard.md)とも呼ばれます) を使用して、どのような脅威が解決されたかをすばやく確認し、ビジネス意思決定者に対して Office 365 サービスがビジネスをどのようにセキュリティで保護しているかを視覚的に報告することができます。
  
![脅威ダッシュボード](media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
このダッシュボードを表示して使用するには&amp; 、セキュリティ/コンプライアンスセンターで、[**脅威管理** \> ]**ダッシュボード**に移動します。
  
### <a name="threat-explorer"></a>脅威エクスプローラー

脅威[エクスプローラー (およびリアルタイム検出)](threat-explorer.md)を使用して、脅威を分析し、時間の経過と共に攻撃の量を確認し、脅威ファミリ、攻撃インフラストラクチャなどによるデータの分析を行います。 脅威エクスプローラー (エクスプローラーとも呼ばれます) は、セキュリティアナリストの調査ワークフローの出発点です。
  
![脅威エクスプローラー](media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
このレポートを表示して使用するには&amp; 、セキュリティ/コンプライアンスセンターで、[**脅威管理** \> **エクスプローラー**] に移動します。
  
 ### <a name="incidents"></a>事件

インシデントリスト (調査とも呼ばれます) を使用して、フライトセキュリティインシデントの一覧を表示します。 インシデントは、不審な電子メールメッセージなどの脅威を追跡し、さらに調査と修復を行うために使用されます。
  
![Office 365 の現在の脅威インシデントの一覧](media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
組織の現在のインシデントの一覧を表示するには、セキュリティ&amp; /コンプライアンスセンターで、[**脅威管理** \>の**レビュー** \> **インシデント**] に移動します。
  
![セキュリティ&amp; /コンプライアンスセンターで、[脅威管理\>のレビュー] を選択します。](media/e0f46454-fa38-40f0-a120-b595614d1d22.png)
  
## <a name="learn-more-about-malware-amp-threats"></a>マルウェア&amp;の脅威の詳細情報

Office 365 Advanced Threat Protection プラン2のサービスの一部として、セキュリティアナリストは既知の脅威に関する詳細を確認できます。 これは、ユーザーを安全に保つために実行できる追加の予防策/手順があるかどうかを判断するのに役立ちます。
  
![最近の脅威に関する情報を示すセキュリティ傾向](media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-threat-investigation-and-response-capabilities"></a>これらの脅威の調査および応答機能をどのように入手できますか。

Office 365 の脅威 Invesigation および応答機能は、Office 365 Advanced Threat Protection プラン2および Enterprise E5 に含まれています。 

> [!TIP]
> これらの脅威の調査および応答機能を含まない Office 365 サブスクリプションが組織にある場合は、それらをアドオンとして Office 365 Advanced Threat Protection と共に購入することができます。 プランオプションの詳細については、「 [office 365 Platform Service Description: office &amp; 365 Security コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) 」および「[購入または編集 (office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on))」を参照してください。
  
1. Office 365 の全体管理者として[https://admin.microsoft.com](https://admin.microsoft.com) 、に移動して、office 365 の職場または学校のアカウントを使用してサインインします。 
    
2. [**管理者** \> **課金**] を選択して、現在のサブスクリプションに含まれる内容を確認します。 
    - **Office 365 Enterprise E5**が表示されている場合は、組織に Office 365 Advanced Threat Protection プラン2があります (脅威の調査と応答の機能を含みます)。 
    - **Office 365 Enterprise E3**または**Office 365 enterprise E1**などの別のサブスクリプションが表示される場合は、「Office 365 Advanced Threat Protection プラン2」を追加することを検討してください。 (これを行うには、[**サブスクリプションの追加**] を選択します。)
    
3. Microsoft 365 管理センターで、[**ユーザー** \>の**アクティブなユーザー**] を選択します。
    
5. Office 365 Advanced Threat Protection プラン2ライセンスをアクティブなすべてのユーザーに割り当てます。 (こののライセンスを持っているユーザーのみが、エクスプローラなどのレポートに表示されます)。
    
6. Office 365 Advanced Threat Protection を使用する組織内のユーザーに役割を割り当てます。 「[ユーザーに Office 365 セキュリティ&amp;コンプライアンスセンターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」を参照し、次の表を参照してください。<br/>

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
  
## <a name="additional-information"></a>ページの先頭へ

- [Office 365 Advanced Threat Protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection) 

- [Office 365 Advanced Threat Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
