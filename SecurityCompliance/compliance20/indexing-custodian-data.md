---
title: 保管担当者データのインデックス作成の詳細
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 158af8acf4acdb8ad6650c377a23b44ed28c6f54
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607990"
---
# <a name="advanced-indexing-of-custodian-data"></a>保管担当者データのインデックス作成の詳細

高度な電子的証拠開示 (プレビュー) の場合に、管理者が追加されると見なされる場合は Office 365 内のコンテンツが完全に検索できるようにするのには再処理が部分的にインデックスを作成します。 このプロセスは、*詳細なインデックス*と呼ばれます。コンテンツには、いくつかの画像、サポートされていないファイルの種類またはインデックス ファイルのサイズの制限が発生したときの存在を含む理由の部分的になインデックスを作成することができます。 部分的にインデックス付きの項目に関する詳細については、 [Office 365 でのコンテンツの検索でアイテムを部分的にインデックス](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)を参照してください。

## <a name="viewing-advanced-indexing-results"></a>高度なインデックス作成の結果を表示します。

高度なインデックス作成プロセスが完了したら、再処理の有効性に関する知識を取得できます。 管理者がインデックス ビューで、グラフには、*ハイブリッドのインデックス*に追加されたすべての項目が一覧表示されます。 ハイブリッド インデックスでは、高度な電子的証拠開示 (プレビュー) が再処理の内容を保存する場所です。

グラフには、修復を必要とする項目の数とファイルの種類ごとのエラーのもう 1 つのグラフも含まれています。詳細については、[データの処理中にエラーの修復](error-remediation.md)を参照してください。

## <a name="updating-advanced-indexes-for-custodians"></a>通告の高度なインデックスを更新します。

高度な電子的証拠開示 (プレビュー) の場合に、管理者が追加されると、部分的にインデックス付けされたすべてのアイテムは、再処理します。ただし、時間が経過すると部分的に複数のインデックス付きのアイテムをユーザーのメールボックスまたは OneDrive アカウントに追加することがあります。 必要な場合は、インデックスを更新できます。

> [!NOTE]
> 書インデックス更新は、長時間実行されるプロセスです。場合は 1 日あたりインデックスを 2 回以上更新しないことをお勧めします。
