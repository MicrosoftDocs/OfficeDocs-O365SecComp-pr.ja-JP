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
ms.openlocfilehash: 1a0ecb9a6722deb50a491a15f720481a5bb7b0a4
ms.sourcegitcommit: e0c6f99d5514d8da8a70d9bd3616d1a1c0851254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2018
ms.locfileid: "25552335"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Office 365 の高度な脅威保護のためのレポートを表示します。

セキュリティ分析ツールのいくつかのレポートを使用するには、組織が[Office 365 の高度な脅威保護](office-365-atp.md)(ATP) には、[必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合、&amp;コンプライアンス センターです。(**レポート**には、 \> **ダッシュ ボード**です)。
  
![セキュリティ&amp;コンプライアンス センターのダッシュ ボードを使用して、脅威の高度な保護が作業しているを確認できます](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
ATP のレポートには、[脅威保護の状態のレポート](#threat-protection-status-report)は、[分析ツールのファイルの種類のレポート](#atp-file-types-report)、および[ATP メッセージ破棄レポート](#atp-message-disposition-report)が含まれます。この資料では、ATP のレポートについて説明し、[表示するのにはその他のレポート](#additional-reports-to-view)へのリンクが含まれています。
  
## <a name="threat-protection-status-report"></a>脅威保護の状態のレポート

**脅威保護の状態**レポートは、悪意のあるコンテンツや悪意のある電子メールによって、 [Exchange のオンライン保護](eop/exchange-online-protection-overview.md)(EOP) と[Office 365 の ATP](office-365-atp.md)検出されブロックに関する情報をまとめて 1 つのビューです。レポートには、悪意のあるコンテンツ (ファイルまたは web サイト アドレス (Url))、マルウェア対策エンジン、 [0 時間の自動 (ZAP) を削除する](zero-hour-auto-purge.md)、 [ATP の安全なリンク](atp-safe-links.md)、 [ATP の安全などの分析ツールの機能によってブロックされている一意の電子メール メッセージの集計の数が用意されています。添付ファイル](atp-safe-attachments.md)、および[分析ツール、フィッシング対策機能](atp-anti-phishing.md)です。

> [!NOTE]
> 脅威保護の状態レポートは、 [Office 365 の ATP](office-365-atp.md)または[Exchange のオンライン保護](eop/exchange-online-protection-eop.md)(EOP) は使用しているお客様に利用可能ですただし、ATP のお客様の脅威保護の状態レポートに表示される情報 EOP の顧客が表示とは異なるデータが含まれる予定です。たとえば、ATP のお客様の脅威保護の状態レポート[SharePoint のオンライン、OneDrive、またはマイクロソフトのチームで悪意のあるファイルの検出](atp-for-spo-odb-and-teams.md)に関する情報が含まれます。このような情報は ATP、EOP は分析ツールではない使用しているお客様の脅威保護のステータス レポートの詳細は表示されませんので。
  
セキュリティの脅威保護の状態レポートを表示するのには&amp;コンプライアンス センターでは、**レポート**に移動\>**ダッシュ ボード** \> **脅威保護の状態**です。
  
![ATP の脅威保護の状態のレポート](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
1 日の詳細なステータスを取得するのには、グラフ上に置きます。
  
![1 日の ATP の脅威保護の状態データ](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
既定では、脅威保護の状態レポートは、過去 7 日間のデータを示します。ただし、**フィルター**を選択し、最大 90 日間のデータを表示する日付範囲を変更できます。 
  
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

ATP レポートは、この資料に記載されている、だけでなく他のいくつかのレポートがある、次の表に示すよう。


|レポートの種類  |詳細情報  |
|---------|---------|
|**電子メール セキュリティのレポート**上位の送信者と受信者のレポート、なりすましメール レポート、スパム検出レポートなどです。 | [セキュリティで電子メールのセキュリティ レポートを表示する&amp;コンプライアンス センター](view-email-security-reports.md)        |
|**エクスプ ローラー**(脅威のエクスプ ローラーとも呼ばれ、これに含まれる[Office 365 の脅威インテリジェンス](office-365-ti.md))     | [エクスプ ローラーを使用して、セキュリティで&amp;コンプライアンス センター](use-explorer-in-security-and-compliance.md)        |
|**EOP と分析ツールの結果**これは、PowerShell を使用して生成するカスタムのレポート)。このレポートには、ドメイン、日付、イベントの種類、方向、操作、およびメッセージの数などの情報が含まれています。  | [Get MailTrafficATPReport コマンドレットのリファレンス](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|**EOP と ATP の検出**これは、PowerShell を使用して生成するカスタムのレポート)。このレポートには、悪意のあるファイルまたは Url、フィッシング詐欺、偽装、および電子メールやファイルでの他の潜在的な脅威に関する詳細情報が含まれています。   | [Get MailDetailATPReport コマンドレットのリファレンス](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>ATP のレポートを表示するのにはどのようなアクセス許可が必要か。

表示し、この資料に記載されているレポートを使用して、セキュリティの割り当て、適切なロールが必要&amp;コンプライアンス センターと、Exchange 管理センターで。
  
|**役割グループ**|**割り当てられている場合**|**詳細情報**|
|:-----|:-----|:-----|
| 以下のいずれか:  <br/><br/>-組織の管理  <br/>-セキュリティ管理者  <br/>--セキュリティ リーダー  <br/> |セキュリティ&amp;コンプライアンス センター  <br/> |[Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md) <br/> |
| 以下のいずれか:  <br/><br/>-組織の管理  <br/>--表示専用組織の管理  <br/>--参照受信者の役割  <br/>-コンプライアンス管理  <br/> |Exchange 管理センター  <br/> |[Exchange Online の機能アクセス許可](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a>場合、レポート データが表示されていないでしょうか。

ATP レポートにデータを表示されない場合、ポリシーが正しく設定されているを再確認してください。組織には、 [ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)および[分析ツールの安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)の ATP の保護のための順序で定義されている場所が必要です。[Office 365 のスパム対策およびマルウェア対策の保護](anti-spam-and-anti-malware-protection.md)を参照してください。
  
## <a name="related-topics"></a>関連項目

[レポートと Office 365 のセキュリティ情報&amp;コンプライアンス センター](reports-and-insights-in-security-and-compliance.md)
  
[セキュリティ レポートのスケジュールを作成する&amp;コンプライアンス センター](create-a-schedule-for-a-report.md)
  
[設定し、セキュリティでのカスタム レポートをダウンロード&amp;コンプライアンス センター](set-up-and-download-a-custom-report.md)
  

