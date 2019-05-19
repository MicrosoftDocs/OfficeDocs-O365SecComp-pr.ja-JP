---
title: 高度な電子情報開示での弁護士に対するクライアント特権の検出にスマートタグを設定する
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 5310acad1aa1bc2e01cbabee69dd7bb38084bd9a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153969"
---
# <a name="set-up-smart-tags-for-ml-assisted-review-in-advanced-ediscovery"></a>高度な電子情報開示での ML サポートのスマートタグの設定

高度な電子情報開示の機械学習機能は、ドキュメントの意思決定プロセスを効率化するために役立ちます。 スマートタグを使うと、決定事項を記録するための機械学習機能を、タグとタググループにまとめることができます。 スマートタググループを作成すると、グループにマッピングされた ML モデルの決定は、インラインでわかりやすく表示されるように、情報をインラインで表示するために、グループ内のタグと一緒に表示されます。

## <a name="how-to-set-up-a-smart-tag-group"></a>スマートタググループをセットアップする方法

1. レビューセットで、[レビューの**管理] セット** -> の [**タグの管理**] に移動します。

2. [**タググループの追加**] の横にあるドロップダウンをクリックして、[**スマートタググループの追加**] を選択します。

3. このグループにマップするモデルを選択します。 これにより、タグセクションと N 個の子タグが作成されます。ここで、N はモデルの可能な出力の数です。 たとえば、弁護士-クライアント特権検出モデルには、2つの出力があり、特権がなく、特権がありません。このモデルを選択すると、レビューセット内に2つの子タグが作成されます。各タグは、考えられる出力のいずれかに対応します。

4. 必要に応じて、タググループとタグの名前を変更します。

## <a name="how-to-use-a-smart-tag-group"></a>スマートタググループを使用する方法

ドキュメントのレビュー時に、モデルの結果が適切なタグ値の横に公開されます。 たとえば、弁護士側の権限を検出するためのスマートタググループがあり、そのモデルで決定されたドキュメントを確認した場合は、該当するタグの横にその理由が表示されます。 タグは自動的に適用されないことに注意することが重要です。すべての目的において、スマートタググループ内のタグは、通常のタグと同じように動作しますが、必要に応じて、その横にモデルの結果が表示される点が異なります。