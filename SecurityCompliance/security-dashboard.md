---
title: ダッシュ ボードのセキュリティの概要
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/07/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection: M365-security-compliance
description: Office 365 の脅威保護の状態を確認し、表示、およびセキュリティの警告の動作には、新しいセキュリティ ダッシュ ボードを使用します。
ms.openlocfilehash: 403c47ed09e9652a66abeafb93be02589c9b1702
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995128"
---
# <a name="security-dashboard"></a>セキュリティ ダッシュ ボード

## <a name="overview"></a>概要

[セキュリティ&amp;コンプライアンス センター](go-to-the-securitycompliance-center.md)データの保護とコンプライアンスを管理する組織を有効にします。必要な権限があると仮定した場合、セキュリティ ダッシュ ボードを使用すると同様に、脅威の保護状態を確認、表示、およびセキュリティの警告の動作です。 
  
、概要を説明するビデオを見るし、詳細については、この資料を読みます。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/3540b1f8-62d2-47fa-a07d-d7ad76f55b0f?autoplay=false]
  
セキュリティ ダッシュ ボードにはによって、どのような組織の Office 365 サブスクリプションが含まれている脅威の管理の概要、脅威保護の状態、週単位のグローバルの脅威検出、マルウェア、および詳細についてで説明したようなど、いくつかのウィジェットが含まれます、次のセクション。
  
セキュリティ ダッシュ ボードを表示するのには、 [Office 365 のセキュリティ&amp;コンプライアンス センター](go-to-the-securitycompliance-center.md)**脅威の管理**には、 \> **ダッシュ ボード**です。
  
> [!NOTE]
> セキュリティ ダッシュ ボードを表示するのには Office 365 のグローバル管理者、セキュリティ管理者は、またはセキュリティのリーダーである必要があります。一部のウィジェットでは、追加のアクセス許可を表示する必要があります。詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。 
  
## <a name="threat-management-summary"></a>脅威の管理の概要

脅威の管理の概要のウィジェットが一目でわかります組織が保護する方法の脅威から過去 7 (7) 日間にします。

![セキュリティ ダッシュ ボード ・ ウィジェットの脅威の管理の概要](media/SecDash-ThreatMgmtSummary.png)

については、脅威の管理の概要に表示するサブスクリプションが含まれていますによって異なります。次の表は、どのような情報は、Office 365 エンタープライズ E3 と Office 365 のエンタープライズ E5 に含まれているについて説明します。


|Office 365 Enterprise E3  |Office 365 Enterprise E5  |
|---------|---------|
|マルウェアのメッセージがブロックされています。<br/>フィッシング詐欺メッセージがブロックされています。<br>ユーザーから報告されたメッセージ<br><br><br><br> |マルウェアのメッセージがブロックされています。<br>フィッシング詐欺メッセージがブロックされています。<br>ユーザーから報告されたメッセージ<br>0 日マルウェアがブロックされています。<br>高度なフィッシング詐欺メッセージの検出<br>悪意のある Url がブロックされています。 |

表示または、脅威の管理の概要のウィジェットにアクセスするには、脅威保護の高度なレポートを表示するアクセス許可が必要です。詳細についてを参照してください[ATP のレポートを表示するのにはどのような権限が必要ですか?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)です。 

## <a name="threat-protection-status"></a>脅威保護の状態

脅威保護の状態のウィジェットは、フィッシングやマルウェアの傾向と詳細なビューを使用して脅威保護の有効性を示しています。 

![脅威保護の状態のウィジェット](media/tpswidget.png)

詳細によって異なるかどうか、Office 365 サブスクリプションにはでは[Office 365 の高度な脅威保護](office-365-atp.md)(ATP) の有無にかかわらず、 [Exchange のオンライン保護](eop/exchange-online-protection-eop.md)(EOP) が含まれています。


|サブスクリプションが含まれている場合. |これらの詳細が表示されます。 |
|---------|---------|
|EOP ですが、Office 365 ATP ではありません。     |検出され、EOP によってブロックされている悪意のある電子メール<br> [脅威保護の状態のレポート (EOP)](view-email-security-reports.md#threat-protection-status-report)を参照してください。| |
|Office 365 の ATP |悪意のあるコンテンツや悪意のある電子メール EOP と Office 365 の分析ツールによって検出されブロック<br>マルウェア対策エンジン、 [0 時間の自動削除](zero-hour-auto-purge.md)、および分析ツールの機能 ([安全なリンク](atp-safe-links.md)、[安全な添付ファイル](atp-safe-attachments.md)では、 [ATP のフィッシング対策](atp-anti-phishing.md)など) によってブロックされている、悪意のあるコンテンツに一意の電子メール メッセージの数を集計します。<br>[脅威保護の状態のレポート (ATP)](view-reports-for-atp.md#threat-protection-status-report)を参照してください。 | 

表示または脅威保護の状態のウィジェットにアクセスをするには、脅威保護の高度なレポートを表示するアクセス許可が必要です。詳細についてを参照してください[ATP のレポートを表示するのにはどのような権限が必要ですか?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)です。 

## <a name="global-weekly-threat-detections"></a>グローバル週 1 回の脅威の検出
 
週単位のグローバルの脅威検出のウィジェットでは、過去 7 (7) 日間の電子メール メッセージにどのように多くの脅威が検出されましたを示します。

![グローバルの脅威の検出を毎週ウィジェット](media/globalweeklythreatdetections.png)

メトリックは、次の表で説明するように計算されます。

|測定基準  |計算方法  |
|---------|---------|
|スキャンされたメッセージ |スキャンされた電子メール メッセージの数は、受信者の数を掛けた値 |
|停止の脅威  |マルウェアの受信者の数を掛けた値が含まれていると識別された電子メール メッセージの数 |
|[ATP](office-365-atp.md)によってブロックされています。 |ATP の受信者の数を掛けた値によってブロックされている電子メール メッセージの数 |
|配信された後に削除 |[がゼロの自動パージ](zero-hour-auto-purge.md)の受信者の数を掛けた値が削除されたメッセージの数 |

## <a name="malware"></a>マルウェア

マルウェアのウィジェットは、過去の 7 (7) 日の間にマルウェアの傾向やマルウェア ファミリの種類に関する詳細情報を表示します。

![マルウェアの傾向やファミリの種類](media/malwarewidgetatpe5.png)
 
## <a name="insights"></a>分析情報

洞察を確認する必要がある重要な問題を表面だけでなく、考慮すべき推奨事項と操作も含まれます。 

![スマート ・ インサイト](media/smartinsights.png)

たとえば、一部のユーザーは、迷惑メールのオプションを無効にしているためにフィッシング詐欺の電子メール メッセージが配信されているを参照してください可能性があります。見識のしくみに関する詳細についてを参照してください[のレポートと Office 365 のセキュリティ情報&amp;コンプライアンス センター](reports-and-insights-in-security-and-compliance.md)です。
  
## <a name="threat-intelligence"></a>脅威インテリジェンス

組織のサブスクリプションには、[脅威のインテリジェンス機能](office-365-ti.md)が含まれている場合、セキュリティ ダッシュ ボードには、高度なツールを含む**脅威インテリジェンス**セクションが含まれて。組織のセキュリティ チームは、新たなキャンペーンを理解し、脅威を調査し、インシデントを管理する、このセクションの情報を使用できます。 
  
![脅威インテリジェンスでは、組織を対象とした攻撃を理解できます。](media/threatintelwidget.png)
  
  
## <a name="trends"></a>傾向

セキュリティ ダッシュ ボードの下部にある**の傾向**] セクションは、組織のメール フローの傾向をまとめたものです。レポートでは、スパム、マルウェア、フィッシング詐欺、および適切な e メールとして分類されたメールに関する情報を提供します。レポートの詳細な情報を表示するタイルをクリックします。 
  
![傾向] セクションは、組織のメール フローの傾向をまとめたもの。](media/trends.png)
  
組織の Office 365 サブスクリプションには、[脅威のインテリジェンス機能](office-365-ti.md)が含まれている場合する必要があります、**最新の脅威の管理に関するアラート**レポートを表示して処理するには、セキュリティ チームはこのセクションでと、優先度の高いセキュリティの警告です。 

表示または送信および受信したメールのウィジェットにアクセスするには、脅威保護の高度なレポートを表示するアクセス許可が必要です。詳細についてを参照してください[ATP のレポートを表示するのにはどのような権限が必要ですか?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)です。 

表示または、最新の脅威に対する管理警告のウィジェットにアクセスするには、アラートを表示するアクセス許可が必要です。詳細については、[アラートを表示するために必要な RBAC 権限](alert-policies.md#rbac-permissions-required-to-view-alerts)を参照してください。
  
## <a name="related-topics"></a>関連項目

[セキュリティで電子メールのセキュリティ レポートを表示する&amp;コンプライアンス センター](view-email-security-reports.md)
  
[Office 365 の高度な脅威保護のためのレポートを表示します。](view-reports-for-atp.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Office 365 脅威インテリジェンス](office-365-ti.md)
  

