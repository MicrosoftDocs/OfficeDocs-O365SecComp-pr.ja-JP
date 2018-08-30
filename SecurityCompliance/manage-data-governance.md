---
title: Office 365 のデータ管理を管理します。
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 5/9/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 48064107-fed2-4db0-9e5c-aa5ddd5ccb09
description: データ ・ ガバナンスが必要なときにデータの管理と取得に関するすべてを削除しないとき。Office 365 のデータ ・ ガバナンスからインポートして保持し、最後にコンテンツを完全に削除するポリシーを作成するのには、最初にデータを格納する、完全なコンテンツのライフ サイクルを管理できます。
ms.openlocfilehash: ca3443c3b90a067bf171ddf89be604d262a7b9a4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532667"
---
# <a name="manage-data-governance-in-office-365"></a>Office 365 のデータ管理を管理します。

データ ・ ガバナンスが必要なときにデータの管理と取得に関するすべてを削除しないとき。Office 365 のデータ ・ ガバナンスからインポートして保持し、最後にコンテンツを完全に削除するポリシーを作成するのには、最初にデータを格納する、完全なコンテンツのライフ サイクルを管理できます。
  
## <a name="import"></a>インポート

クラウド、オンプレミスのサーバーと同様に、またはサード ・ パーティ製のアプリケーションでの外部の場所でいくつかのデータの格納されている可能性があります。インポート サービスでは、メッセージ、SharePoint、および OneDrive のビジネス データをネットワーク経由で直接アップロードすることに暗号化されたドライブを出荷するか、Office 365 に簡単です。インテリジェントなインポート機能を使用サービスのインポートの対象のメールボックスに実際にインポートを取得する PST ファイル内のアイテムをフィルター処理します。 
  
- [Office 365 の PST ファイルのインポートの概要](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)
    
- [ネットワーク アップロードを使用して PST ファイルを Office 365 にインポートする](use-network-upload-to-import-pst-files.md)
    
- [ドライブ送付を使用して PST ファイルを Office 365 にインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- [PST コレクション ツールを使用して、検索、コピー、および組織内の PST ファイルを削除するには](find-copy-and-delete-pst-files-in-your-organization.md)
    
- [Office 365 に PST ファイルをインポートするときにデータをフィルター処理します。](filter-data-when-importing-pst-files.md)
    
- [PowerShell コマンドレットを使用して、オンプレミス コンテンツを SharePoint Online にアップロードする](https://support.office.com/article/555049c6-15ef-45a6-9a1f-a1ef673b867c)
    
## <a name="govern-i-store-data"></a>I: ストアのデータを制御します。

データをインポートした後は、お客様のストレージを増やす必要があります。アーカイブ機能は、制限はありません (と呼ばれる自動拡張のアーカイブ)、Office 365 は、無制限の量のアーカイブ メールボックス内のストレージを提供します。
  
- [Office 365 のセキュリティ、アーカイブ メールボックスを有効にする&amp;コンプライアンス センター](enable-archive-mailboxes.md)

- [Office 365 の無制限のアーカイブの概要](unlimited-archiving.md)
    
- [Office 365 の無制限のアーカイブを有効にします。](enable-unlimited-archiving.md)
    

    
## <a name="govern-ii-create-policies-and-labels-to-retain-content"></a>ポリシーとコンテンツを保持するラベルを作成する II を制御します。

リテンション ・ ポリシーでは、限り必要がない場合よりもコンテンツを保持することを確保することにより業界の規制や社内ポリシーに準拠して積極的にできます。1 つの保持ポリシーは、組織全体をカバーできます。さらに、ガバナンス、組織全体にわたってデータのクラス分けと、その分類に基づく保存ルールを適用してファイル計画を実装するためにラベルを使用できます。
  
- [アイテム保持ポリシーの概要](retention-policies.md)
    
- [ラベルの概要](labels.md)
    
- [一括作成し、PowerShell を使用してラベルを発行します。](https://support.office.com/article/8986701b-ffa1-46ec-8fd0-8f7e81d5b25f.aspx)
    
- [廃棄レビューの概要](disposition-reviews.md)
    
- [イベント ベースの保持の概要](event-driven-retention.md)
    
## <a name="govern-iii-retain-the-email-of-former-employees"></a>退職した従業員の電子メール アドレスを保持する 3 世が制御されます。

人が組織を離れたときに非アクティブなメールボックスを作成することによって自分の電子メールを保持できます。メールボックス、証拠保全、Office 365 のリテンション ・ ポリシーと、使用頻度の低いまたは保留中の他の種類が適用されることになり、対応する Office 365 ユーザー アカウントが削除されます。非アクティブなメールボックス内のアイテムが非アクティブにされる前に、メールボックスに格納された、保留中または保存ポリシーの期間中保持されます。
  
- [Office 365 のメールボックスを非アクティブの概要](inactive-mailboxes-in-office-365.md)
    
- [作成し、Office 365 の非アクティブなメールボックスの管理](create-and-manage-inactive-mailboxes.md)

- [Office 365 での非アクティブなメールボックスの保持期間を変更します。](change-the-hold-duration-for-an-inactive-mailbox.md)
  
- [Office 365 で、非アクティブなメールボックスをリカバリします。](recover-an-inactive-mailbox.md)
 
- [Office 365 で、非アクティブなメールボックスを復元します。](restore-an-inactive-mailbox.md)

- [Office 365 で、非アクティブなメールボックスを削除します。](delete-an-inactive-mailbox.md)

## <a name="monitor"></a>監視

監督では、内部または外部の校閲者が調査できるように、電子メールや、組織内のサード パーティ製の通信をキャプチャするためのポリシーを定義することができます。校閲者これらの通信を分類、組織のポリシーに準拠しているかどうかを確認し、必要な場合は、問題のある材料をエスカレートします。
  
意図したとおりに、ラベルは、コンテンツに適用されているかを監視するのにデータ ・ ガバナンス ・ レポートとラベルのアクティビティのエクスプ ローラーを使用することもできます。
  
- [組織用に監督ポリシーを構成する](configure-supervision-policies.md)
    
- [監督レポート](supervision-reports.md)
    
- [ドキュメントのラベルのアクティビティを表示する](view-label-activity-for-documents.md)
    
- [データ ガバナンスのレポートを表示する](view-the-data-governance-reports.md)
    
## <a name="more-information"></a>詳細情報

- [Microsoft のデータ ガバナンス チームによるビデオを見る](https://go.microsoft.com/fwlink/?linkid=867039)
    
- [Office 365 のデータ管理の概要を見る](https://go.microsoft.com/fwlink/?linkid=852644)
    
- [Office 365 のセキュリティ&amp;コマンドレットのコンプライアンス センター](https://go.microsoft.com/fwlink/?linkid=852310)
    

