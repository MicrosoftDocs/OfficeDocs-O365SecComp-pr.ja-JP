---
title: カストディアン データの詳細なインデックス処理
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: f8f1a92f001bf8f9e23f54bbb05fbbcf443bf4b9
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218667"
---
# <a name="advanced-indexing-of-custodian-data"></a>カストディアン データの詳細なインデックス処理

保管担当者が高度な電子情報開示 (プレビュー) ケースに追加されると、部分的にインデックスと見なされた Office 365 のコンテンツはすべて、完全に検索可能になるように再処理されます。 このプロセスは、*高度なインデックス*と呼ばれます。画像の存在、サポートされていないファイルの種類、インデックスファイルサイズの制限が発生したなど、さまざまな理由でコンテンツを部分的にインデックス処理することができます。 部分的にインデックスが作成されたアイテムの詳細については、「 [Office 365 のコンテンツ検索での一部インデックス付きアイテム](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)」を参照してください。

## <a name="viewing-advanced-indexing-results"></a>高度なインデックス作成の結果を表示する

高度なインデックス処理が完了すると、再処理の有効性について理解することができます。 [保管担当者 Indexing] ビューでは、*ハイブリッドインデックス*に追加されたすべてのアイテムがグラフに一覧表示されます。 ハイブリッドインデックスは、高度な電子情報開示 (プレビュー) が再処理されたコンテンツを格納する場所です。

グラフには、修復が必要な項目の数と、ファイルの種類別のエラーのグラフも表示されます。詳細については、「[データ処理時のエラー修復](error-remediation.md)」を参照してください。

## <a name="updating-advanced-indexes-for-custodians"></a>保管担当者の高度なインデックスを更新する

保管担当者が高度な電子情報開示 (プレビュー) ケースに追加されると、部分的にインデックスが作成されたすべてのアイテムが再処理されます。ただし、時間が経過すると、インデックスが作成されたアイテムの数が多くなると、ユーザーのメールボックスまたは OneDrive アカウントに追加されることがあります。 必要に応じて、インデックスを更新できます。

> [!NOTE]
> 保管担当者インデックスの更新は、長時間実行されるプロセスです。ケースでは、1日に1回のインデックスを更新しないことをお勧めします。
