---
title: Office 365 の SharePoint のオンライン ・ データの削除
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: SharePoint Online でのデータ削除の詳細については。
ms.openlocfilehash: c281f6de9cd9e4978ac4a6997333d71d8835420f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531746"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a>Office 365 で SharePoint のオンライン ・ データの削除

SharePoint Online は、アプリケーション データベースの抽象化されたコードとオブジェクトを格納します。SharePoint Online にファイルをアップロードすると、そのファイルは分解し、アプリケーション コードに変換し、複数のデータベース間で複数のテーブルに格納されています。SharePoint Online では、お客様にアップロードするすべてのコンテンツが (可能性のある複数 AES の 256 ビットのキー) で暗号化されているチャンクに分割し、データ センターに分散します。チャンクに分割し、暗号化のプロセスに関する詳細については、[マイクロソフトのクラウドでの暗号化](office-365-encryption-in-the-microsoft-cloud-overview.md)を参照してください。データ保護サービスは、SharePoint Online のデータの損失を防ぐために提供されます。具体的には、バックアップは 12 時間ごとを実行し、14 日間保持されます。

SharePoint Online サイトからコンテンツを削除する場合は削除されませんすぐに。必要な場合は、サイトのごみ箱、復元することに送信されます。([削除済みのサイト コレクションのごみ箱からアイテムを復元](https://support.office.com/article/Restore-deleted-items-from-the-site-collection-recycle-bin-5fa924ee-16d7-487b-9a0a-021b9062d14b)の「復元の手順)既定のサイトのごみ箱の保存期間は、約 90 日です。コンテンツをサイトのごみ箱から削除する場合、サイト コレクションのごみ箱は保管期間は 30 日間に送信されます。管理者がごみ箱の内容を保持する時間の長さを構成することができますが、ことのない場合は、既定の保存期間は、約 90 日です。サイトのごみ箱の記憶域は、サイト コレクションの記憶域のクォータと[リスト ビューのしきい値](https://support.office.com/article/List-View-Threshold-b8588dae-9387-48c2-9248-c24122f07c59)に対してカウントされます。

サイト コレクションを削除するときもすべてのコンテンツおよびユーザー情報を含む、コレクション内のサイトの階層を削除しています。
- ドキュメントおよびドキュメント ライブラリ
- リストとリスト データ
- サイト構成の設定
- サイトまたはサブサイトに関連付けられているロールおよびセキュリティの情報
- サブサイト最上位の web サイト、コンテンツ、およびユーザー情報の

サイト コレクションを削除する前に、SharePoint のオンライン サービスの説明を確認する、計画では、SharePoint Online サイトはマイクロソフトが管理しているデータのバックアップ ・ スケジュールの概要を説明するをお勧めします。バックアップから復元できることを確認、専用のサイト コレクションまたはファイル、リスト、またはライブラリではなく、サブのサイトです。それらを回復する場合は、ごみ箱を使用します。

サイト コレクションを削除してしまった場合、復元できるサイト コレクションのごみ箱からサイト コレクションの管理者によって 30 日以内。30 日後に復元するサイト コレクションが必要な場合に復元できますマイクロソフト 30 日間有効期限からの 14 日以内、サービス ・ リクエストを使用してマイクロソフトに連絡しています。

ハード削除は、ユーザーがサイトのごみ箱から削除されたアイテムを削除し、保存とバックアップの期間が期限切れ、または管理者が完全に[削除 SPODeletedSite コマンドレット](https://docs.microsoft.com/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)を使用してサイト コレクションを削除するときに発生します。ハードのユーザーを削除すると、完全に削除 (パージ) SharePoint Online のコンテンツの削除されたチャンクのすべての暗号化キーも削除されます。以前削除されたチャンクを格納するディスク上のブロックは、使用されていないために使用できる再使用としてマークされます。
