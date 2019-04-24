---
title: 通信エディターを使用する
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
ms.openlocfilehash: c2957c88217bce4c9a34f8d3f9a9e291f1223cc9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241244"
---
# <a name="use-the-communications-editor"></a>通信エディターを使用する

ポータルコンテンツ、法的情報保留通知、および関連する事前通知/エスカレーションの内容を定義する際に、コミュニケーションエディターを活用して、コンテンツの書式設定や動的なカスタマイズを行うことができます。

## <a name="rich-text-editor"></a>リッチテキストエディター 

コミュニケーションエディターを使用すると、ユーザーはエディターのオプションを使用してテキストをカスタマイズできます。 たとえば、ユーザーはフォントの種類を変更したり、箇条書きのリストを作成したり、コンテンツを強調表示したりすることができます。 

## <a name="merge-field-variables"></a>差し込みフィールドの変数

コミュニケーションエディターから電子メールの宛名差し込み変数を活用して、カスタマイズされた保管担当者属性をコミュニケーションの本文テキストに埋め込むことができます。 保管担当者に送信されると、対応するフィールドが差し込み印刷フィールドに設定されます。 たとえば、保管担当者 John Smith に送信された場合、差し込み印刷フィールド [保管担当者 Name] は対応する名前に変換されます。 

電子メールの宛名差し込みフィールドを使用するには、リッチテキストエディターコントロールの上部にある**差し込み印刷フィールド**アイコンを選択します。 プレースホルダーは、ユーザーのカーソルの位置に基づいて追加されます。 

### <a name="list-of-merge-field-variables"></a>差し込みフィールドの変数の一覧

| フィールド名                  | フィールドの詳細 | 
| :------------------- | :------------------- |
| 表示名  | 保管担当者の姓と名。 | 
| 確認のリンク | 各保管担当者の受信確認を記録するためのカスタマイズされたリンク。|                 |
| ポータルリンク     | 保管担当者のコンプライアンスポータル用のカスタマイズされたリンク。|                |
| 発行責任者                   | 指定した発行担当者の電子メールアドレス。|                   |
| 発行日                   | 通知が発行された日付 (UTC)。              |