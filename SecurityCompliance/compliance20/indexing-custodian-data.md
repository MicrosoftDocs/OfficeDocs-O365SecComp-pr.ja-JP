---
title: カストディアン データの詳細なインデックス処理
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: be163d3272dbe027cb0f4b4b4fe379bf28fa5a85
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151759"
---
# <a name="advanced-indexing-of-custodian-data"></a>カストディアン データの詳細なインデックス処理

高度な電子情報開示ケースに保管担当者が追加されると、部分的にインデックスと見なされた Office 365 のコンテンツはすべて、完全に検索可能になるように再処理されます。  このプロセスは、*高度なインデックス*と呼ばれます。 画像の存在、サポートされていないファイルの種類、インデックスファイルサイズの制限が発生したなど、さまざまな理由でコンテンツを部分的にインデックス処理することができます。

Office 365 の処理サポートと、部分的にインデックスが作成されたアイテムの詳細については、以下を参照してください。

- [高度な電子情報開示でサポートされているファイルの種類](supported-filetypes-ediscovery20.md)
- [Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)
- [Exchange Search によってインデックス処理されるファイル形式](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>高度なインデックス作成の結果を表示する

高度なインデックス処理が完了すると、再処理の有効性について理解することができます。  [保管担当者 Indexing] ビューでは、*ハイブリッドインデックス*に追加されたすべてのアイテムがグラフに一覧表示されます。  ハイブリッドインデックスは、高度な電子情報開示が再処理されたコンテンツを格納する場所です。

グラフには、修復が必要な項目の数と、ファイルの種類別のエラーのグラフも表示されます。 詳細については、「[データ処理時のエラー修復](error-remediation.md)」を参照してください。

## <a name="updating-advanced-indexes-for-custodians"></a>保管担当者の高度なインデックスを更新する

高度な電子情報開示ケースに保管担当者が追加されると、部分的にインデックスが作成されたすべてのアイテムが再処理されます。 ただし、時間が経過すると、インデックスが作成されたアイテムの数が多くなると、ユーザーのメールボックスまたは OneDrive アカウントに追加されることがあります。  必要に応じて、インデックスを更新できます。

> [!NOTE]
> 保管担当者インデックスの更新は、長時間実行されるプロセスです。 ケースでは、1日に1回のインデックスを更新しないことをお勧めします。
