---
title: Microsoft 365 コンプライアンスセンターの新機能
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Microsoft 365 コンプライアンスセンターに新機能を継続的に追加し、学習した問題を修正し、フィードバックに基づいて変更を加えています。 今月の内容を確認してください。
ms.openlocfilehash: c5abb71c21e6c65d46768d584101f6902c0422c2
ms.sourcegitcommit: 30fc793d3e77e223dee6c96a94e50cda2de34bb6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "37011719"
---
# <a name="whats-new-in-the-microsoft-365-compliance-center"></a>Microsoft 365 コンプライアンスセンターの新機能

[Microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md)に新機能を継続的に追加し、学習した問題を修正し、フィードバックに基づいて変更を加えています。 お客様が現在利用できるものを確認するには、次のようにしてください。 一部の機能は、お客様のさまざまなスピードでロールアウトされます。 機能がまだ表示されていない場合は、[対象のリリース](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)に追加してみてください。

> [!TIP]
> 他の管理センターでは何が起こっているのでしょうか。 次の記事をご覧ください。<br>[Microsoft 365 管理センターの新機能](https://docs.microsoft.com/office365/admin/whats-new-in-preview?view=o365-worldwide)<br>[SharePoint 管理センターの新機能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)

## <a name="august-2019"></a>2019年8月

今月リリースのリリース前に静かになる理由をご確認ください。 マイクロソフトは、11月に[Microsoft Ignite](https://www.microsoft.com/ignite)で最近される新しい革新的なコンプライアンスソリューションの構築に取り組んでいます。 引き続きご調整ください。

### <a name="data-investigations"></a>データ調査

データの調査を実行すると、元の場所からアイテムを削除できるようになります。 これは、組織全体の Exchange メールボックス、SharePoint サイト、および OneDrive アカウントからアイテムを削除できることを意味します。 アイテムを証拠として収集したため、証拠セットに保存されたアイテムのコピーが、さらに参考になるか、参照として保持することができます。 [詳細情報](datainvestigations/delete-items-from-original-locations.md)

## <a name="july-2019"></a>2019年7月

### <a name="new-admin-roles"></a>新しい管理者の役割

組織のセキュリティとコンプライアンスを管理するために、2つの新しい管理者の役割をリリースしました。すべての友人に連絡します。

- **コンプライアンスデータ管理者**。この役割を持つユーザーは、Microsoft 365 コンプライアンスセンター、Microsoft 365 管理センター、および Azure のデータを保護および追跡するためのアクセス許可を持っています。 また、Exchange 管理センター、コンプライアンスマネージャー、Teams & Skype for Business 管理センターを管理したり、Azure および Microsoft 365 のサポートチケットを作成したりすることもできます。
- **セキュリティオペレーター**。 この役割を持つユーザーは、通知を管理し、Microsoft 365 セキュリティセンター、Azure Active Directory、Id 保護、特権 Id 管理、Office 365 のすべてを含む、セキュリティ関連機能へのグローバルな読み取り専用アクセスを行うことができます。セキュリティ & コンプライアンスセンター。

[これらの役割の詳細情報](https://docs.microsoft.com/office365/securitycompliance/permissions-microsoft-365-compliance-security)

### <a name="search-and-filtering-for-reports"></a>レポートの検索とフィルター処理

必要なレポートを見つけるために、大量のレポートをスクロールする必要はありません。 これで、(タイトルに基づいて) レポートを検索し、「ラベル」や「コンプライアンス」、「Office 365」や「Microsoft Cloud App Security」などのソースのカテゴリにフィルターを適用することができます。

![適用されたフィルターを使用したレポートの検索とフィルターのボタンの画面キャプチャ](media/mcc_report_filtering.png)

### <a name="help-content"></a>ヘルプコンテンツ

椅子を引き上げ、コーヒーをつかんで、最新のコンプライアンスに関するドキュメントをすぐに使用できるようにします。

**Advanced eDiscovery**
- [高度な電子情報開示で会話を確認](compliance20/conversation-review-sets.md)する新規
- [Advanced eDiscovery での AzCopy のトラブルシューティング](compliance20/troubleshooting-azcopy.md)
- [レビュー セットに Office 365 以外のデータを読み込む](compliance20/load-non-office365-data.md)
- [データ処理中のエラー修復](compliance20/error-remediation.md)

**サードパーティのデータをアーカイブする**
- [Office 365 でインスタント Bloomberg データをアーカイブするためのコネクタを設定する](archive-instant-bloomberg-data.md)

**監査**
- [共有を監査して外部ユーザーと共有されているリソースを見つける](use-sharing-auditing.md)
- [Office 365 管理アクティビティ API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)
- [Office 365 管理アクティビティ API のトラブルシューティング](https://docs.microsoft.com/office/office-365-management-api/troubleshooting-the-office-365-management-activity-api)
- [セキュリティ & コンプライアンスセンターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)

**暗号化**
- [Office 365 Message Encryption の旧来の情報](legacy-information-for-message-encryption.md)

**部門**
- [正確なデータ一致に基づく分類を使用してカスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

**データガバナンス**
- [アイテム保持ポリシーの概要](retention-policies.md)

**マネージ**
- [Office 365 の監督ポリシー](supervision-policies.md)