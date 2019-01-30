---
title: 通信エディターを使用してください。
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
ms.openlocfilehash: 107f45510bcf70942c6f03bdfed0a9090f1d83c0
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608025"
---
# <a name="using-the-communications-editor"></a>通信エディターを使用してください。
ポータル コンテンツの内容を定義すると、法的な通知、および関連する通知/エスカレーションの保持、通信エディターを使用して書式を設定し、コンテンツを動的にカスタマイズを活用することができます。

## <a name="rich-text-editor"></a>リッチ テキスト エディター 

通信エディターは、エディターのオプションを使用してテキストをカスタマイズするユーザーを許可します。たとえば、ユーザーは、フォントの種類を変更する、箇条書きリスト、強調表示のコンテンツを作成します。 

<<include screenshot>>

## <a name="merge-field-variables"></a>フィールド変数をマージします。

メール マージ変数通信の本文に管理者がカスタマイズした属性を埋め込むには、通信エディターからを利用できます。管理者に送信されると、差し込み印刷フィールドは対応するフィールドに入力されます。たとえば、John Smith の管理者に送信されると、差し込み印刷フィールドの [管理者名] 変換される対応する名前を持つ。 

電子メールの差し込み印刷フィールドを使用するには、リッチ テキスト エディター コントロールの上部にある **[差し込みフィールド**のアイコンを選択します。プレース ホルダーは、ユーザーのカーソルの位置をベースに追加されます。 

### <a name="list-of-merge-field-variables"></a>差し込み印刷フィールドの変数のリスト
| フィールド名                  | フィールドの詳細 | 
| :------------------- | :-------------------: |
| 表示名  | 保管担当者の名字と名前 | 
| 受信確認のリンク                 | 各管理者の承認を記録するためのカスタマイズしたリンク                 |
| ポータル リンク     | コンプライアンス ・ ポータルの管理者のカスタマイズしたリンク                 |
| 発行責任者                   | 指定した発行責任者の電子メール アドレス                   |
| 発行日                   | (UTC)、通知が発行された日付              |