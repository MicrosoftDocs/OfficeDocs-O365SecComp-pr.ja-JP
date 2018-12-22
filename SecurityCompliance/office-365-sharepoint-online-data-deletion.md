---
title: Office 365 の SharePoint のオンライン ・ データの削除
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: SharePoint Online でのデータ削除の詳細については。
ms.openlocfilehash: 8a84859ce170a4c3ca713c751aef2b6d5b911c55
ms.sourcegitcommit: 29ba4c36af8e90ddc8d885863ef25bac2cffbe94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2018
ms.locfileid: "27411163"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a>Office 365 で SharePoint のオンライン ・ データの削除

SharePoint Online は、アプリケーション データベースの抽象化されたコードとオブジェクトを格納します。SharePoint Online にファイルをアップロードすると、そのファイルは分解し、アプリケーション コードに変換し、複数のデータベース間で複数のテーブルに格納されています。SharePoint Online では、お客様にアップロードするすべてのコンテンツが (可能性のある複数 AES の 256 ビットのキー) で暗号化されているチャンクに分割し、データ センターに分散します。チャンクに分割し、暗号化のプロセスに関する詳細については、[マイクロソフトのクラウドでの暗号化](office-365-encryption-in-the-microsoft-cloud-overview.md)を参照してください。 

SharePoint online では、アイテムは元の場所からそれらを削除する時間から 93 日間保持されます。ままサイトのごみ箱で全体の時間では、だれかがそこからそれらを削除または、[ごみ箱を空にしない限り、です。その場合は、項目は、サイト コレクションの 93 の日の残りの部分のまま、ごみ箱に移動します。削除済みアイテムを復元する方法の詳細情報は、 [SharePoint サイトのごみ箱のアイテムを復元](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
)し、[復元は、サイト コレクションのごみ箱からアイテムを削除](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)を参照してください。ごみ箱の保存期間は、SharePoint Online に設定可能ではありません。

サイト コレクションを削除する場合も、コレクション、およびその中のすべてのコンテンツ内のサイトの階層を削除しています。
- ドキュメントおよびドキュメント ライブラリ
- リストとリスト データ
- サイト構成の設定
- サイトまたはサブサイトに関連付けられているロールおよびセキュリティの情報
- サブサイト最上位の web サイト、コンテンツ、およびユーザー情報の

サイト コレクションを削除してしまった場合、復元できる、グローバルまたは SharePoint によって SharePoint 管理センターを使用して管理します。 

ハード削除は、保存とバックアップの期間が経過した場合、または管理者が完全に[削除 SPODeletedSite コマンドレット](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)を使用してサイト コレクションを削除すると、ユーザーがサイト コレクションのごみ箱から削除済みアイテムを削除するときに発生します。ハードのユーザーを削除すると、完全に削除 (パージ) SharePoint Online のコンテンツの削除されたチャンクのすべての暗号化キーも削除されます。以前削除されたチャンクを格納するディスク上のブロックは、使用されていないために使用できる再使用としてマークされます。
