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
description: Microsoft 365 コンプライアンスセンターの機能と同様に、ヘルプコンテンツは常に進化しています。 新しい記事を継続的に作成し、既存の記事を更新し、フィードバックに基づいて変更を加えています。 今月の新機能と更新された機能について説明します。
ms.openlocfilehash: e7600c2f84d0b591c6114c2a61c77d8e2c664056
ms.sourcegitcommit: 9fd606e8d912f4507fbcd9f1fcb9dfcfd20de08b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "36980803"
---
# <a name="recent-updates-to-microsoft-365-compliance-content"></a>Microsoft 365 コンプライアンスコンテンツの最新の更新プログラム

Microsoft 365 コンプライアンスセンターの機能と同様に、ヘルプコンテンツは常に進化しています。 新しい記事を継続的に作成し、既存の記事を更新し、フィードバックに基づいて変更を加えています。 今月の新機能と更新された機能を確認するには、次のようにします。

> [!TIP]
> Microsoft 365 コンプライアンスセンターで最新の機能の更新プログラムを最新の状態に保つには、「 [microsoft 365 コンプライアンスセンターの新](whats-new.md)機能」をご覧ください。

## <a name="august-2019"></a>2019年8月

### <a name="auditing"></a>監査

[メールボックスの監査を管理](enable-mailbox-auditing.md#more-information)するまし<br>E5 ライセンスを持つユーザー、またはメールボックスの監査が管理者によって手動で有効にされたメールボックスのユーザーに対してのみ、メールボックス監査ログイベントを利用可能にする方法の詳細を追加しました。また、 **「search-mailboxauditlog**コマンドレットを使用して Exchange Online PowerShell を使用して、E5 ライセンスを持たないユーザーのメールボックス監査ログを検索する方法についても新しいガイダンスを示します。

[Office 365 監査ログを検索して一般的なシナリオのトラブルシューティングを行う](auditing-troubleshooting-scenarios.md#investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization)まし<br>パススルー認証を使用して、外部ユーザーによる成功したログインを調べる方法についての新しいセクションです。

### <a name="content-search--ediscovery"></a>コンテンツ検索 & 電子情報開示

[コンテンツ検索のアクセス許可フィルターを構成する](permissions-filtering-for-content-search.md#using-a-filters-list-to-combine-filter-types)まし<br>フィルターリストの使用に関する詳細を追加しました。これにより、1つの検索アクセス許可フィルターにメールボックスフィルターとサイトフィルターを追加することができます。

[Office 365 でのコンテンツ検索](content-search.md#searching-disconnected-or-de-licensed-mailboxes)まし<br>切断されたメールボックスまたはライセンスの解除済みメールボックスの検索に関する詳細を追加しました。

[Office 365 でのコンテンツ検索](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment)まし<br>
[Office 365 で電子情報開示の調査のためのコンプライアンスの境界を設定する](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments)まし<br>SharePoint 複数地域環境でコンテンツを検索することに関する記事の詳細を両方に追加しました。

### <a name="data-governance"></a>データ ガバナンス

[Office 2010 での無制限アーカイブの概要 (](unlimited-archiving.md#how-auto-expanding-archiving-works)機械翻訳) 365まし<br>合計 1 TB の追加のストレージに対して、Office 365 が最大20個の補助アーカイブを追加する方法に関する詳細を追加しました。

### <a name="data-investigations"></a>データ調査

[元の場所からアイテムを削除](datainvestigations/delete-items-from-original-locations.md)する新規<br>プレビューで利用できるようになったので、証拠セット内の項目を選択してから、Exchange、SharePoint、OneDrive の元の場所からそれらを削除することができます。

[Microsoft 365 でデータ流出インシデントを管理する](datainvestigations/manage-data-spillage-incidents.md#step-4-delete-the-spilled-data)まし<br>新しい「元の場所からアイテムを削除する」機能を使用して、こぼれたデータを削除する方法の詳細を追加しました。

### <a name="permissions"></a>アクセス許可

[Microsoft 365 コンプライアンスセンターおよび microsoft 365 セキュリティセンターでのアクセス許可](permissions-microsoft-365-compliance-security.md)新規<br>新しい Azure Active Directory 役割グループはパブリックプレビューにリリースされました。

### <a name="records-management"></a>レコード管理

[ファイル計画マネージャーの概要 (更新)](file-plan-manager.md#export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews)<br>Excel テンプレートで使用される有効な値を一覧表示する表を追加しました。

### <a name="supervision"></a>マネージ

[Office 365 の監督ポリシー](supervision-policies.md)まし<br>Office 365 のグループと配布リストのサポートを明確化し、電子メールと添付ファイルの両方にキーワード一致のガイダンスを追加し、Teams チャネル内での Outlook サポートを明確化しました。

### <a name="windows-information-protection"></a>Windows 情報保護

[Windows 情報保護 (WIP) で使用するなり Microsoft アプリのリスト](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/enlightened-microsoft-apps-and-wip)まし <br>Microsoft 3D Viewer はなりアプリになりました。
