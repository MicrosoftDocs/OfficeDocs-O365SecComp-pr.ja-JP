---
title: Exchange Online Protection でのレポート作成とメッセージ追跡
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 12/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online ・保護 (EOP) は、全体的なステータスと、組織の健全性を決定する際に役立つ多くのさまざまなレポートを提供します。(メッセージのない着信などを目的の受信者)、特定のイベントのトラブルシューティングに役立つツールもありますし、コンプライアンス要件を支援するためにレポートを監査します。次の表は、レポートおよび EOP の管理者に使用可能なトラブルシューティングのツールについて説明します。
ms.openlocfilehash: 01a09b2b4b72161352af3793686c6cc888e44e29
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027144"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Exchange Online Protection でのレポート作成とメッセージ追跡

Microsoft Exchange Online ・保護 (EOP) は、全体的なステータスと、組織の健全性を決定する際に役立つ多くのさまざまなレポートを提供します。(メッセージのない着信などを目的の受信者)、特定のイベントのトラブルシューティングに役立つツールもありますし、コンプライアンス要件を支援するためにレポートを監査します。 

## <a name="usage-reports"></a>利用状況レポート

**Office 365 グループ活動**作成され使用されている Office 365 のグループの数に関する情報を表示します。  

**電子メール活動**メッセージの送信、受信でき、組織全体で、特定のユーザーの数に関する情報を表示します。  

**電子メール アプリケーションの使用状況**使用されている電子メール アプリケーションについての情報を表示します。これには、各アプリケーションの接続の合計数と接続している Outlook のバージョンが含まれます。  

**メールボックスの使用状況**記憶域の使用に関する情報、クォータの使用量、アイテムの数、およびメールボックスの最後のアクティビティ (送信または読み取りアクティビティ) を表示します。

詳細については次のリソースを参照してください。

- [グループ管理センター - Office 365 の office 365 のレポートします。](https://go.microsoft.com/fwlink/p/?linkid=861610) 
- [Office 365 管理センター - 電子メールの利用状況レポート](https://go.microsoft.com/fwlink/p/?linkid=859706) 
- [Office 365 管理センター - 電子メール アプリケーションの使用状況レポート](https://go.microsoft.com/fwlink/p/?linkid=859707)
- [Office 365 管理センター - メールボックスの使用状況レポート](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security-amp-compliance-reports-in-the-office-365-admin-center"></a>セキュリティ&amp;Office 365 の管理センターでのコンプライアンス ・ レポート

これらの拡張されたレポートは EOP 管理者向けの対話型レポート エクスペリエンスを提供します。これには概要情報、および詳細についてドリルダウンする機能が含まれます。  

**(ATP) の脅威保護の詳細**安全なリンクと分析ツールの一部である安全な添付ファイルについての情報を表示します。  

**EOP**マルウェアの検出、スプーフィングされたメール、迷惑メールの検出、および組織との間のメール フローに関する情報を表示します。  

[脅威の高度な保護と Exchange のオンライン保護に関するレポートを表示](https://go.microsoft.com/fwlink/p/?linkid=852409) 

##<a name="custom-reports-using-microsoft-graph"></a>Microsoft Graph を使用してカスタム レポート

[Microsoft Graph で使用状況レポートを Office 365](https://go.microsoft.com/fwlink/p/?linkid=865135)のサブトピックで利用できる Office 365 の管理ページのグラフを参照してください Microsoft を使用してレポートをプログラムで作成します。 

##<a name="custom-reports-using-reporting-web-services"></a>レポート Web サービスを使用するカスタム レポート

プログラムを使用して、利用可能な Exchange オンライン保護 PowerShell コマンドレットを残りの部分と ODATA2 クエリのフィルター処理を使用して、レポートからレポートを作成します。

[Office 365 のレポート Web サービス](https://go.microsoft.com/fwlink/p/?LinkId=279926)を参照してください。 

##<a name="message-trace"></a>メッセージの追跡

EOP を通過する電子メール メッセージを追跡します。電子メール メッセージがサービスで受信、拒否、延期、配信されたか確認できます。メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。  

この情報を使用して、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。  

[電子メール メッセージのトレース](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)を参照してください。 

## <a name="audit-logging"></a>監査ログ

組織管理者が加えた変更を追跡します。これらのレポートは、構成に関する問題のトラブルシューティングを行うか、セキュリティやコンプライアンス関連の問題の原因を特定するのに役立ちます。 [EOP の監査レポート](auditing-reports-in-eop.md)を参照してください。 


## <a name="reporting-and-message-trace-data-availability-and-latency"></a>レポート機能とメッセージ トレース データの使用可能性と遅延

EOP のレポート機能とメッセージ トレース データが使用可能なタイミングと期間を次の表に示します。
  
||||
|:-----|:-----|:-----|
|**レポートの種類** <br/> |**データ使用可能期間 (遡及期間)** <br/> |**遅延時間** <br/> |
|メール保護概要レポート  <br/> |90 日  <br/> |メッセージ データの集計は 24 ～ 48 時間以内にほぼ完了します。最大 5 日間のマイナーな増分集計変更が実施される場合があります。  <br/> |
|メール保護詳細レポート  <br/> |90 日  <br/> |生成後 7 日未満の詳細データに関しては、24 時間以内に表示されるはずですが、48 時間まで完成しない場合があります。最大 5 日分のマイナーな増分変更が実施される場合があります。  <br/> 7 日以上前のメッセージに関する詳細レポートを表示するには、結果が出るまでに最大で数時間かかる場合があります。  <br/> |
|メッセージ追跡データ  <br/> |90 日  <br/> |生成後 7 日未満のメッセージのメッセージ追跡を実施した場合は、メッセージが 5 ～ 30 分で表示されるはずです。  <br/> 7 日以上前のメッセージのメッセージ追跡を実施した場合は、結果が出るまでに最大で数時間かかる場合があります。  <br/> |
   
> [!NOTE]
> データの可用性と待機時間は、Office 365 管理者センターやリモート PowerShell を使用して要求されたかどうか同じです。 
  

