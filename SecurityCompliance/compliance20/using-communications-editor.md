---
title: 通信エディターを使用する
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
ms.openlocfilehash: b148ff1a77cd9225a26f98e7612e9fb5b57331e3
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706058"
---
# <a name="use-the-communications-editor"></a>通信エディターを使用する

ポータル コンテンツの内容を定義すると、法的な通知、および関連する通知/エスカレーションの保持、通信エディターを使用して書式を設定し、コンテンツを動的にカスタマイズを活用することができます。

## <a name="rich-text-editor"></a>リッチ テキスト エディター 

通信エディターは、エディターのオプションを使用してテキストをカスタマイズするユーザーを許可します。たとえば、ユーザーは、フォントの種類を変更する、箇条書きリスト、強調表示のコンテンツを作成します。 

## <a name="merge-field-variables"></a>フィールド変数をマージします。

メール マージ変数通信の本文に管理者がカスタマイズした属性を埋め込むには、通信エディターからを利用できます。管理者に送信されると、差し込み印刷フィールドは対応するフィールドに入力されます。たとえば、John Smith の管理者に送信されると、差し込み印刷フィールドの [管理者名] 変換される対応する名前を持つ。 

電子メールの差し込み印刷フィールドを使用するには、リッチ テキスト エディター コントロールの上部に**差し込み印刷フィールド**のアイコンを選択します。プレース ホルダーは、ユーザーのカーソルの位置をベースに追加されます。 

### <a name="list-of-merge-field-variables"></a>差し込み印刷フィールドの変数のリスト

| フィールド名                  | フィールドの詳細 | 
| :------------------- | :------------------- |
| 表示名  | 書の名字と名前です。 | 
| 受信確認のリンク | 各管理者の承認を記録するためのカスタマイズされたリンクです。|                 |
| ポータル リンク     | コンプライアンス ・ ポータルの管理者のカスタマイズされたリンクです。|                |
| 発行責任者                   | 指定した発行責任者の電子メール アドレスです。|                   |
| 発行日                   | (UTC)、通知が発行された日付です。              |