---
title: ワーキング セット内のデータのクエリ
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
ms.openlocfilehash: 2523072181307cce510f0f318834329b2c70b376
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454989"
---
# <a name="query-the-data-in-a-working-set"></a>ワーキング セット内のデータのクエリ

ほとんどの場合、作業セットに含まれるものをより深く掘り下げて、より効率的にレビューできるように整理するのに役立ちます。 作業セット内のクエリを使用すると、一度に定義された条件を満たすドキュメントのサブセットに集中することができます。

## <a name="creating-and-running-a-query-within-a-working-set"></a>作業セット内でのクエリの作成と実行

作業セット内でクエリを作成して実行するには、ワーキングセット内の [新しいクエリ] をクリックします。 クエリの名前を指定して条件を定義したら、[保存] をクリックしてクエリを実行します。 以前に保存したクエリを実行するには、保存されているクエリをクリックします。 検索可能なメタデータの一覧については、「[ドキュメントメタデータ」フィールド](document-metadata-fields.md)を参照してください。

## <a name="building-your-query"></a>クエリを作成する

キーワード条件カードでは、条件カードとクエリ言語の組み合わせを使用してクエリを作成できます。

### <a name="condition-card"></a>条件カード

作業セット内のすべての検索可能なフィールドには、クエリの作成に使用できる対応する条件カードがあります。

複数の種類の条件カードがあります。
- freetext: freetext 条件カードは、subject などのテキストフィールドに使用されます。 複数の検索用語をコンマで区切ってリストすることができます。
- 日付: 日付の条件カードは、最終変更日などの日付フィールドに使用されます。
- 検索オプション: 検索オプション条件カードは、作業セットの特定のフィールドに使用可能な値の一覧を提供します。 これは、送信者などのフィールドに使用されます。これは、ワーキングセットに指定できる値が限定されている場合です。
- キーワード: キーワード条件カードは、用語を検索したり、で kql に似たクエリ言語を使用したりするために使用できる、freetext 条件カードの特定のインスタンスです。 詳細については、以下を参照してください。

### <a name="query-language"></a>クエリ言語

条件カードに加えて、キーワードカードで kql のようなクエリ言語を使用してクエリを作成できます。 クエリ言語は、and、OR、NOT、NEAR (n) などの標準の kql 構文をサポートしています。 また、1文字のワイルドカード (?) と複数文字のワイルドカード (*) もサポートしています。