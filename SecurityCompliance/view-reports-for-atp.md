---
title: Office 365 Advanced Threat Protection のレポートを表示する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: セキュリティ&amp; /コンプライアンスセンターで Office 365 Advanced Threat Protection のレポートを検索して使用する方法について説明します。
ms.openlocfilehash: 3a128103d16ed03edb18becde96a5d20ee6eca9b
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692406"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection のレポートを表示する

組織に[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) があり、[必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、セキュリティ&amp;コンプライアンスセンターでいくつかの ATP レポートを使用できます。 ([**レポート** \> ]**ダッシュボード**に移動します。)
  
![セキュリティ&amp;コンプライアンスセンターのダッシュボードは、高度な脅威保護が機能している場所を確認するのに役立ちます。](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
atp レポートには、[脅威保護の状態レポート](#threat-protection-status-report)、 [atp ファイルの種類レポート](#atp-file-types-report)、 [atp メッセージ廃棄レポート](#atp-message-disposition-report)が含まれます。 この記事では、ATP レポートについて説明し、[表示する追加レポート](#additional-reports-to-view)へのリンクが含まれています。
  
## <a name="threat-protection-status-report"></a>脅威保護の状態レポート

**脅威保護の状態**レポートは、悪意のあるコンテンツや悪意のある電子メールに関する情報をまとめた1つのビューで、 [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) および[Office 365 ATP](office-365-atp.md)によって検出されブロックされます。 このレポートでは、悪意のあるコンテンツ (ファイルまたは web サイトアドレス (url)) を使用した一意の電子メールメッセージの集計数が提供されます。これには、非マルウェア対策エンジン、[ゼロ時間の自動削除 (ZAP](zero-hour-auto-purge.md))、atp の各機能 (atp の安全な[リンク](atp-safe-links.md)など) によるブロックがあります。 [添付ファイル](atp-safe-attachments.md)、および[ATP のフィッシング対策機能](atp-anti-phishing.md)。

> [!NOTE]
> 脅威保護の状態レポートは、 [Office 365 ATP](office-365-atp.md)または[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP) のいずれかを使用しているお客様が利用できます。ただし、ATP のお客様の脅威保護状態レポートに表示される情報には、EOP のお客様に表示されるものとは異なるデータが含まれている可能性があります。 たとえば、ATP のお客様向けの脅威保護状態レポートには、 [SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイル](atp-for-spo-odb-and-teams.md)に関する情報が含まれています。 このような情報は atp に固有のものなので、EOP を持たないお客様は脅威保護の状態レポートにこれらの詳細を表示しません。
  
脅威保護の状態レポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \>の**脅威保護の状態**] に移動します。
  
![ATP の脅威保護状態レポート](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
1日の詳細な状態を取得するには、グラフの上にポインターを移動します。
  
![1日の ATP の脅威保護状態データ](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
既定では、脅威保護の状態レポートには過去7日間のデータが表示されます。 ただし、**フィルター**を選択し、日付の範囲を変更して、最大90日間のデータを表示することができます。 
  
![ATP の脅威保護状態フィルター](media/4f703369-642b-402b-9758-b9c828283410.png)
  
[**データの表示**] メニューを使用して、レポートに表示される情報を変更することもできます。 
  
![ATP の脅威保護状態レポートの表示オプション](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a>ATP ファイルタイプレポート

**atp ファイルの種類**レポートには、 [atp の安全な添付](atp-safe-attachments.md)ファイルによって検出されたファイルの種類が表示されます。
  
このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **ATP**] [ファイルの種類] に移動します。
  
![ATP ファイルタイプレポート](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
特定の日の上にカーソルを移動すると、 [Office 365 で&amp; ](anti-spam-and-anti-malware-protection.md)、ATP の安全な[添付](atp-safe-attachments.md)ファイルとスパム対策のマルウェア対策保護によって検出された悪意のあるファイルの種類の分類を確認できます。
  
![1日の ATP ファイルタイプレポートデータ](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>ATP メッセージディスポジションレポート

**ATP メッセージディスポジション**レポートには、悪意のあるコンテンツが含まれていることが検出された電子メールメッセージに対して実行されたアクションが表示されます。 
  
このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **ATP メッセージ廃棄**] に移動します。
  
![ATP メッセージディスポジションレポート](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
グラフのバーの上にマウスカーソルを移動すると、その日に検出されたメールに対して実行されたアクションを確認できます。
  
![1日の ATP メッセージディスポジションレポートデータ](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>表示する追加レポート

この記事で説明されている ATP レポートに加えて、次の表に示すように、他にもいくつかのレポートを利用できます。

|レポートの種類  |詳細情報  |
|---------|---------|
|上位の送信者と受信者のレポート、スプーフィングメールレポート、スパム検出レポートなどの**電子メールセキュリティレポート**。 | [セキュリティ&amp; /コンプライアンスセンターで電子メールのセキュリティレポートを表示する](view-email-security-reports.md)        |
|**エクスプローラー**(脅威エクスプローラーとも呼ばれます)。これは[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md)に含まれています。     | [セキュリティ&amp; /コンプライアンスセンターのエクスプローラーを使用する](use-explorer-in-security-and-compliance.md)        |
|**EOP および ATP の結果**(これは、PowerShell を使用して生成するカスタムレポートです)。 このレポートには、ドメイン、日付、イベントの種類、方向、アクション、メッセージ数などの情報が含まれます。  | [get-mailtrafficatpreport コマンドレットリファレンス](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|**EOP および ATP の検出**(これは、PowerShell を使用して生成するカスタムレポートです)。 このレポートには、悪意のあるファイルまたは url、フィッシングの試行、偽装、その他の電子メールやファイルの潜在的な脅威に関する詳細が記載されています。   | [Get-maildetailatpreport コマンドレットリファレンス](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>ATP レポートを表示するには、どのようなアクセス許可が必要ですか。

この記事に記載されているレポートを表示して使用するには、**セキュリティ&amp;コンプライアンスセンターと Exchange 管理センターの両方に対して適切な役割が割り当てられている必要があり**ます。

- セキュリティ&amp; /コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。
    - 組織の管理
    - セキュリティ管理者 (Azure Active Directory 管理センター[https://aad.portal.azure.com](https://aad.portal.azure.com)で割り当て可能)
    - セキュリティリーダ

- exchange online の場合は、exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) または PowerShell コマンドレット (「 [exchange online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。
    - 組織の管理
    - 表示限定の組織管理
    - "View-Only Recipients/表示専用受信者" 役割
    - コンプライアンス管理

詳細については、以下のリソースを参照してください。

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online の機能アクセス許可](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a>レポートでデータが表示されない場合はどうなりますか。

ATP レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを再確認してください。 組織で atp の[安全なリンクポリシー](set-up-atp-safe-links-policies.md)と[atp の安全な添付ファイルのポリシー](set-up-atp-safe-attachments-policies.md)が定義されている必要があります。これは、atp 保護を適切に実行するためです。 また、「[スパム対策およびマルウェア対策保護 (Office 365](anti-spam-and-anti-malware-protection.md))」を参照してください。
  
## <a name="related-topics"></a>関連項目

[Office 365 セキュリティ&amp; /コンプライアンスセンターのレポートと分析情報](reports-and-insights-in-security-and-compliance.md)
  
[セキュリティ&amp; /コンプライアンスセンターでレポートのスケジュールを作成する](create-a-schedule-for-a-report.md)
  
[セキュリティ&amp; /コンプライアンスセンターでカスタムレポートを設定およびダウンロードする](set-up-and-download-a-custom-report.md)
  

