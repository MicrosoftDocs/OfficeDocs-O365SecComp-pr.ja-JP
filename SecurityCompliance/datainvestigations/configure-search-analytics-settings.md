---
title: 検索と分析の設定を構成する
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
ms.openlocfilehash: 0456ee21087c7fe05c3ef96d517feb468c7cfe5e
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150999"
---
# <a name="configure-search-and-analytics-settings"></a>検索と分析の設定を構成する

## <a name="near-duplicates-and-email-threading"></a>ほぼ重複、電子メールスレッド

このセクションでは、重複データ検出、重複の検出、電子メールのスレッド処理のパラメーターを設定できます。

- Enable/disable: 重複データ検出、ほぼ重複検出、および電子メールスレッド処理を分析フローの一部として有効にします (有効にした場合)。 これらは互いの上に構築されているため、すべてを有効にするか、すべての設定を無効にする必要があります。

- しきい値: 2 つのドキュメントの類似性レベルがしきい値を超えている場合は、同じ近くにある重複セットに配置されます。

- 既定で重複を非表示にする: この設定をオンにすると、重複したドキュメントを非表示にするためのフィルターが既定で作業セットに適用されます。 必要に応じて、ワーキングセット内のフィルターを手動で削除できます。

- 最小/最大単語数: 重複および電子メールスレッド処理は、少なくとも単語の最小数が少なく、最大で単語数が多いドキュメントに対してのみ実行されます。
詳細については、「[重複の検出](near-duplicates.md)と[電子メールのスレッド処理](email-threading.md)」を参照してください。

## <a name="themes"></a>テーマ

このセクションでは、テーマのパラメーターを設定できます。

- Enable/disable: 有効になっている場合は、分析フローの一部としてテーマのクラスターを含めます。
- テーマの最大数を動的に調整する: 場合によっては、必要な数のテーマを作成するだけのドキュメントが存在しないことがあります。 この設定が有効になっている場合は、必要なテーマの最大数を強制するのではなく、テーマの最大数をシステムが動的に調整します。
- テーマの最大数: 必要なテーマの数
- テーマに数字を含める: 有効にすると、テーマを生成するときに数字が含まれます。  

## <a name="optical-character-recognition-ocr"></a>光学式文字認識 (OCR)

この設定が有効になっている場合は、ワークセットに取り込まれたされている画像に対して OCR が実行され、検索できるようになります。

## <a name="ignore-text"></a>テキストを無視する

特定のテキストに、電子メールの内容に関係なく特定の電子メールに追加される長い免責事項など、特定のテキストが分析の品質を低下させる場合があります。 そのような場合は、テキストを指定することによって、分析からこのテキストを除外することができます (RegEx はサポートされています)。また、テキストを除外するモジュールを指定することもできます。