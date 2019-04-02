---
title: 調査のためのデータの高度なインデックス作成
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 9537cf743b89da7167ce3a37a5915027f4eb717a
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030310"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a>調査のためのデータの高度なインデックス作成

イメージの存在、サポートされていないファイルの種類、インデックスファイルサイズの制限が発生したなど、さまざまな理由で、ライブシステムのコンテンツを部分的にインデックス処理することができます。 リスクの高いデータのスピルを処理している場合は、調査する必要があるすべてのデータが検索によって取得されたことを確認する必要があります。 関心のある人物がデータ調査に追加されると、部分的にインデックスとして見なされた Office 365 のコンテンツはすべて、完全に検索可能になるように再処理されます。 このプロセスは、*高度なインデックス*と呼ばれます。 

Office 365 の処理サポートと、部分的にインデックスが作成されたアイテムの詳細については、以下を参照してください。

- [データ調査でサポートされているファイルの種類](supported-filetypes-datainvestigations.md)

- [Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)

- [Exchange Search によってインデックス処理されるファイル形式](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>高度なインデックス作成の結果を表示する

高度なインデックス処理が完了すると、再処理の有効性について理解することができます。  [インデックス作成] ビューのユーザーには、*ハイブリッドインデックス*に追加されたすべてのアイテムが表示されます。  ハイブリッドインデックスは、データ調査 (プレビュー) が再処理されたコンテンツを格納する場所です。

グラフには、修復が必要な項目の数と、ファイルの種類別のエラーのグラフも表示されます。 詳細については、「[データ処理時のエラー修復](error-remediation.md)」を参照してください。

## <a name="updating-advanced-indexes-for-people-of-interest"></a>関心のあるユーザーの高度なインデックスを更新する

関心のあるユーザーがデータ調査に追加されると、部分的にインデックスが作成されたすべてのアイテムが再処理されます。 ただし、時間が経過すると、インデックスが作成されたアイテムの数が多くなると、ユーザーのメールボックスまたは OneDrive アカウントに追加されることがあります。  必要に応じて、インデックスを更新できます。

> [!NOTE]
> 関心のあるインデックスを持つユーザーを更新する処理は、長時間実行されています。 調査では1日に1回のインデックスを更新しないことをお勧めします。
