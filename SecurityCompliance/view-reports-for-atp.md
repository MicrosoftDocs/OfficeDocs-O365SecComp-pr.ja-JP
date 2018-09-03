---
title: Office 365 の高度な脅威保護のためのレポートを表示します。
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: 検索し、Office 365 高度な脅威保護、セキュリティでのレポートを使用する方法を説明&amp;コンプライアンス センターです。
ms.openlocfilehash: 13b2a4c142a223a8a912c9017b6033b0b5a1548b
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782114"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Office 365 の高度な脅威保護のためのレポートを表示します。

セキュリティ分析ツールのいくつかのレポートを使用するには組織に[Office 365 の高度な脅威保護](office-365-atp.md)(ATP) があり、ユーザーが必要なアクセス許可を持っている場合は場合、&amp;コンプライアンス センターです。(**レポート**には、 \> **ダッシュ ボード**です)。
  
![セキュリティ&amp;コンプライアンス センターのダッシュ ボードを使用して、脅威の高度な保護が作業しているを確認できます](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
ATP のレポートには、脅威の保護ステータス レポート、分析ツールのファイルの種類のレポート、および ATP メッセージ破棄レポートが含まれます。この資料では、ATP のレポートについて説明し、表示するのにはその他のレポートへのリンクが含まれています。
  
## <a name="threat-protection-status-report"></a>脅威保護のステータス レポート

**脅威保護の状態**レポートは、悪意のあるコンテンツや悪意のある電子メールと Exchange のオンラインの脅威保護の高度なによって検出されブロックに関する情報をまとめて 1 つのビューです。レポートには、コンテンツを含む悪意のあるファイル (Url)、マルウェア対策エンジン、 [0 時間の自動 (ZAP) の削除](zero-hour-auto-purge.md)を[ATP の安全なリンク](atp-safe-links.md)、 [ATP などの高度な脅威保護機能によってブロックされている一意の電子メール メッセージの集計の数が用意されています。安全な添付ファイル](atp-safe-attachments.md)、および[Office 365 の ATP のフィッシング詐欺対策機能](atp-anti-phishing.md)です。
  
セキュリティの脅威保護のステータス レポートを表示するのには&amp;コンプライアンス センターでは、**レポート**に移動\>**ダッシュ ボード** \> **脅威保護の状態**です。
  
![ATP の脅威保護の状態のレポート](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
1 日の詳細なステータスを取得するのには、グラフ上に置きます。
  
![1 日の ATP の脅威保護の状態データ](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
既定では、脅威保護のステータス レポートは、過去 7 日間のデータを示します。ただし、**フィルター**を選択し、最大 90 日間のデータを表示する日付範囲を変更できます。 
  
![ATP の脅威保護の状態のフィルター](media/4f703369-642b-402b-9758-b9c828283410.png)
  
レポートに表示される情報を変更するのには **、データの表示**] メニューの [を使用することもできます。 
  
![ATP の脅威保護の状態レポートのオプションを表示します。](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a>分析ツール ファイルの種類のレポート

**分析ツール ファイルの種類**のレポートでは、 [ATP の安全な添付ファイル](atp-safe-attachments.md)が悪意のあるものとして検出されたファイルの種類を示します。
  
セキュリティで、このレポートを表示するのには&amp;コンプライアンス センターでは、**レポート**に移動\>**ダッシュ ボード** \> **分析ツール ファイルの種類**です。
  
![分析ツール ファイルの種類のレポート](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
特定の日の上に置くと、[安全な添付ファイルの分析ツール](atp-safe-attachments.md)で検出された悪意のあるファイルの種類の内訳を表示でき、[スパム対策&amp;Office 365 のマルウェア対策保護](anti-spam-and-anti-malware-protection.md)。
  
![1 日のレポート データの分析ツールのファイルの種類](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>ATP メッセージ破棄レポート

**ATP メッセージ破棄**レポートでは、悪意のあるコンテンツを持つものとして検出された電子メール メッセージのアクションを示します。 
  
セキュリティで、このレポートを表示するのには&amp;コンプライアンス センターでは、**レポート**に移動\>**ダッシュ ボード** \> **ATP メッセージ廃棄**します。
  
![ATP メッセージ破棄レポート](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
グラフのバーの上にマウス ポインターを移動するとき、どのような操作を行った電子メールで検出されたその日が確認できます。
  
![1 日の ATP メッセージ破棄レポート データ](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>追加のレポートを表示するには

だけでなく、この資料に記載されている ATP のレポートは[電子メール セキュリティのレポート](view-email-security-reports.md)は、セキュリティで利用可能な&amp;コンプライアンス センターです。電子メール セキュリティのレポート[上位の送信者と受信者のレポート](view-email-security-reports.md#top-senders-and-recipients-report)、[なりすましメールのレポート](view-email-security-reports.md#spoof-mail-report)は、[スパム検出レポート](view-email-security-reports.md#spam-detections-report)などが含まれます。
  
組織が[Office 365 の脅威インテリジェンス](office-365-ti.md)の場合することもでき、 [、セキュリティでエクスプ ローラーを使用して&amp;コンプライアンス センター](use-explorer-in-security-and-compliance.md)。
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a>これらのレポートを表示するのにはどのようなアクセス許可が必要か。

表示し、この資料に記載されている電子メールのセキュリティ レポートを使用して、セキュリティの割り当て、適切なロールが必要&amp;コンプライアンス センターと、Exchange 管理センターで。
  
|**役割グループ**|**割り当てられている場合**|**詳細情報**|
|:-----|:-----|:-----|
| 以下のいずれか:  <br/>  組織の管理  <br/>  セキュリティ管理者  <br/>  セキュリティ リーダー  <br/> |セキュリティ&amp;コンプライアンス センター  <br/> |[Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md) <br/> |
| 以下のいずれか:  <br/>  組織の管理  <br/>  表示限定の組織管理  <br/>  "View-Only Recipients/表示専用受信者" 役割  <br/>  Compliance Management  <br/> |Exchange 管理センター  <br/> |[Exchange Online の機能アクセス許可](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a>場合、レポート データが表示されていないでしょうか。

レポートにデータを表示されない場合、ポリシーが正しく設定されているを再確認してください。組織には、 [ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)および[分析ツールの安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)の ATP の保護のための順序で定義されている場所が必要です。[Office 365 のスパム対策およびマルウェア対策の保護](anti-spam-and-anti-malware-protection.md)を参照してください。
  
## <a name="related-topics"></a>関連項目

[レポートと Office 365 のセキュリティ情報&amp;コンプライアンス センター](reports-and-insights-in-security-and-compliance.md)
  
[セキュリティ レポートのスケジュールを作成する&amp;コンプライアンス センター](create-a-schedule-for-a-report.md)
  
[設定し、セキュリティでのカスタム レポートをダウンロード&amp;コンプライアンス センター](set-up-and-download-a-custom-report.md)
  

